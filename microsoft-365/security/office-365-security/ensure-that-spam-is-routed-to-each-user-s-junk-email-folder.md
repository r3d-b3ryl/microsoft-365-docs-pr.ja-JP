---
title: ハイブリッド環境で迷惑メールに EOP を構成する
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online Protection ハイブリッド環境でユーザーの迷惑メール フォルダーにスパムをルーティングする方法について説明します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b8fbc1b065e348f759806d80fd85421eb9d66098
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288875"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a>ハイブリッド環境で迷惑メール フォルダーにスパムを配信するスタンドアロン EOP を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
-  [Exchange Online Protection スタンドアロン](exchange-online-protection-overview.md)

> [!IMPORTANT]
> このトピックは、ハイブリッド環境のスタンドアロン EOP のお客様向けです。 このトピックは、Exchange Online メールボックスを使用している Microsoft 365 のお客様には適用されません。

ハイブリッド環境でスタンドアロンの Exchange Online Protection (EOP) を使用している場合は、EOP のスパム フィルターの判断を認識して翻訳するようにオンプレミスの Exchange 組織を構成する必要があります。そのため、オンプレミスのメールボックスの迷惑メール ルールはメッセージを [迷惑メール] フォルダーに移動できます。

具体的には、次の EOP スパム対策ヘッダーと値を含むメッセージを検索する条件、およびそれらのメッセージの Spam Confidence Level (SCL) を 6 に設定するアクションを使用して、オンプレミスの Exchange 組織にメール フロー ルール (トランスポート ルールとも呼ばれる) を作成する必要があります。

- `X-Forefront-Antispam-Report: SFV:SPM` (スパム フィルタリングによってスパムとしてマークされたメッセージ)

- `X-Forefront-Antispam-Report: SFV:SKS` (スパム フィルタリングの前に EOP のメール フロー ルールによってスパムとしてマークされたメッセージ)

- `X-Forefront-Antispam-Report: SFV:SKB` (送信者の電子メール アドレスまたは電子メール ドメインが受信拒否リストまたは EOP のブロックされたドメインの一覧にある場合に、スパム フィルターによってスパムとしてマークされたメッセージ)

これらのヘッダー値の詳細については、「スパム対策メッセージ ヘッダー [」を参照してください](anti-spam-message-headers.md)。

このトピックでは、Exchange 管理センター (EAC) およびオンプレミスの Exchange 組織の Exchange 管理シェル (Exchange PowerShell) でこれらのメール フロー ルールを作成する方法について説明します。

> [!TIP]
> オンプレミス ユーザーの迷惑メール フォルダーにメッセージを配信する代わりに、EOP でスパム対策ポリシーを構成して、EOP でスパム メッセージを検疫できます。 詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- これらの手順を実行する前に、オンプレミスの Exchange 環境でアクセス許可を割り当てる必要があります。 具体的には、既定で組織の管理、コンプライアンス管理、およびレコード管理の役割に割り当てられるトランスポート ルールの役割を割り当てる必要があります。  詳細については、「役割グループに [メンバーを追加する」を参照してください](https://docs.microsoft.com/Exchange/permissions/role-group-members#add-members-to-a-role-group)。

- メッセージがオンプレミスの Exchange 組織の迷惑メール フォルダーに配信される場合と配信される場合は、次の設定の組み合わせによって制御されます。

  - Exchange 管理シェル の [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig)コマンドレットの _SCLJunkThreshold_ パラメーター値。 既定値は 4 で、SCL が 5 以上の場合はユーザーの迷惑メール フォルダーにメッセージを配信する必要があります。

  - Exchange 管理シェル の [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox)コマンドレットの _SCLJunkThreshold_ パラメーター値。 既定値は空白 ($null) で、組織の設定が使用されます。

  詳細については [、「Exchange Spam Confidence Level (SCL) のしきい値」を参照してください](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl)。

  - メールボックスで迷惑メール ルールが有効になっているかどうか _(Enabled_ パラメーターの値は、Exchange 管理シェル の [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) コマンドレットで $true です)。 配信後に実際にメッセージを [迷惑メール] フォルダーに移動する迷惑メール ルールです。 既定では、迷惑メール ルールはメールボックスで有効になっています。 詳細については、「[Configure Exchange antispam settings on mailboxes](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings)」を参照してください。

- Exchange 管理センターで EAC を開Exchange Server Exchange[管理センターを参照Exchange Server。](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center) Exchange 管理シェル を開くには、「[Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell)」を参照してください。

- オンプレミスの Exchange のメール フロー ルールの詳細については、次のトピックを参照してください。

  - [Exchange Server のメール フロー ルール](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [メール フロー ルールの条件と例外 (述語) Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [メール フロー ルールのアクション (Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>EAC を使用して、EOP スパム メッセージの SCL を設定するメール フロー ルールを作成する

1. EAC で、 **[メール フロー]** \> **[ルール]** に移動します。

2. [**追加]** アイコンをクリックし、表示されるドロップダウンで [新しいルールの ![ ](../../media/ITPro-EAC-AddIcon.png) 作成]を選択します。

3. **[新しいルール]** のページが開いたら、以下の設定を行ってください:

   - **[名前**]: ルールのわかりやすい一意の名前を入力します。 例:

     - EOP SFV:SPM から SCL 6

     - EOP SFV:SKS から SCL 6

     - EOP SFV:SKB から SCL 6

   - [**その他のオプション**] をクリックします。

   - **[メッセージ ヘッダーを選択]** に **次の単語が含** まれる場合 \> **に、このルールを適用します**。

     Enter テキスト **ヘッダーに表示される Enter 語** 文が含まれる場合は、次の手順を実行します。

     - [テキスト **の入力] をクリックします**。 表示される **[ヘッダー名の** 指定] ダイアログで **、「X-Forefront-Antispam-Report」** と入力し **、[OK]** をクリックします。

     - [単語  **の入力] をクリックします**。 表示される[単語または語句の指定] ダイアログで、EOP スパム ヘッダー値 (**SFV:SPM、SFV:SKS、** または **SFV:SKB)** の 1 つを入力し、[追加] アイコンをクリックし ![ ](../../media/ITPro-EAC-AddIcon.png) **、[OK]** をクリックします。

   - **[メッセージのプロパティの** 変更] を選択 **して** \> **、Spam Confidence Level (SCL) を設定します**。

     表示される **[SCL の** 指定] ダイアログで **、6** (既定値は **5) を選択します**。

   完了したら、[保存] をクリック **します。**

残りの EOP スパム判断値 **(SFV:SPM、SFV:SKS、****または SFV:SKB)** に対して、これらの手順を繰り返します。 

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Exchange 管理シェル を使用して、EOP スパム メッセージの SCL を設定するメール フロー ルールを作成する

次の構文を使用して、3 つのメール フロー ルールを作成します。

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

例:

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

詳細な構文とパラメーターについては、「[New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)」を参照してください。

## <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

ハイブリッド環境の迷惑メール フォルダーにスパムを配信するようにスタンドアロン EOP が正常に構成されたことを確認するには、次の手順を実行します。

- EAC で、[メールフロー ルール] に移動し、ルールを選択し、[編集] アイコンをクリックして設定 \>  ![ ](../../media/ITPro-EAC-EditIcon.png) を確認します。

- Exchange 管理シェル で、メール フロー ルールの名前に置き換え、次のコマンドを使用して設定 \<RuleName\> を確認します。

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- スパムの送信メッセージをスキャンしない外部電子メール システムで、影響を受ける受信者に迷惑メール (GTUBE) メッセージの汎用テストを送信し、迷惑メール フォルダーに配信されるのを確認します。 GTUBE メッセージは、マルウェア設定をテストするための European Institute for Computer Antivirus Research (EICAR) テキスト ファイルと似ています。

  GTUBE メッセージを送信するには、スペースや改行を使用せずに、電子メール メッセージの本文に次のテキストを 1 行に含める必要があります。

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```
