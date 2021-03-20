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
description: 管理者は、Exchange Online Protection ハイブリッド環境のユーザー迷惑メール フォルダーにスパムをルーティングする方法について説明します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ae6ee551d04b242891c9638d6d99d79240480d27
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910860"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a>ハイブリッド環境の迷惑メール フォルダーにスパムを配信するスタンドアロン EOP を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
-  [Exchange Online Protection スタンドアロン](exchange-online-protection-overview.md)

> [!IMPORTANT]
> このトピックは、ハイブリッド環境のスタンドアロン EOP のお客様専用です。 このトピックは、Exchange Online メールボックスを使用している Microsoft 365 のお客様には適用されません。

ハイブリッド環境でスタンドアロンの Exchange Online Protection (EOP) のお客様である場合は、EOP のスパム フィルターの評決を認識して翻訳するようにオンプレミスの Exchange 組織を構成する必要があります。そのため、オンプレミスメールボックスの迷惑メール ルールはメッセージを迷惑メール フォルダーに移動できます。

具体的には、次の EOP スパム対策ヘッダーと値を含むメッセージを検索する条件、およびこれらのメッセージのスパム信頼レベル (SCL) を 6 に設定するアクションを使用して、オンプレミスの Exchange 組織にメール フロー ルール (トランスポート ルールとも呼ばれる) を作成する必要があります。

- `X-Forefront-Antispam-Report: SFV:SPM` (スパム フィルターによってスパムとしてマークされたメッセージ)

- `X-Forefront-Antispam-Report: SFV:SKS` (スパム フィルター処理の前に EOP でメール フロー ルールによってスパムとしてマークされたメッセージ)

- `X-Forefront-Antispam-Report: SFV:SKB` (送信者の電子メール アドレスまたは電子メール ドメインがブロックされた送信者リストまたは EOP のブロックされたドメイン リストに含め、スパム フィルターによってスパムとしてマークされたメッセージ)

これらのヘッダー値の詳細については、「スパム対策メッセージ [ヘッダー」を参照してください](anti-spam-message-headers.md)。

このトピックでは、Exchange 管理センター (EAC) およびオンプレミス Exchange 組織の Exchange 管理シェル (Exchange PowerShell) で、これらのメール フロー ルールを作成する方法について説明します。

> [!TIP]
> メッセージをオンプレミスユーザーの迷惑メール フォルダーに配信する代わりに、EOP でスパムメッセージを検疫するスパム対策ポリシーを EOP で構成できます。 詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- これらの手順を実行するには、オンプレミスの Exchange 環境でアクセス許可を割り当てる必要があります。 具体的には、既定で組織の管理、コンプライアンス管理、およびレコード管理の役割に割り当てられているトランスポート ルールの役割を割り当てる必要があります。  詳細については、「役割グループに [メンバーを追加する」を参照してください](/Exchange/permissions/role-group-members#add-members-to-a-role-group)。

- オンプレミスの Exchange 組織の迷惑メール フォルダーにメッセージが配信される場合と配信される場合は、次の設定の組み合わせによって制御されます。

  - Exchange 管理シェルの [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig)コマンドレットの _SCLJunkThreshold_ パラメーター値。 既定値は 4 です。つまり、SCL が 5 以上の場合は、ユーザーの迷惑メール フォルダーにメッセージを配信する必要があります。

  - Exchange 管理シェルの [Set-Mailbox](/powershell/module/exchange/set-mailbox)コマンドレットの _SCLJunkThreshold_ パラメーター値。 既定値は空白 ($null) で、組織の設定が使用されます。

  詳細については [、「Exchange スパム信頼レベル (SCL) のしきい値」を参照してください](/Exchange/antispam-and-antimalware/antispam-protection/scl)。

  - メールボックスで迷惑メール ルールが有効になっているかどうか (Exchange管理シェルの[Set-MailboxJunkEmailConfiguration](/powershell/module/exchange/set-mailboxjunkemailconfiguration)コマンドレットの Enabled パラメーター値は $true です)。 配信後にメッセージを迷惑メール フォルダーに実際に移動する迷惑メール ルールです。 既定では、迷惑メール ルールはメールボックスで有効になっています。 詳細については、「[Configure Exchange antispam settings on mailboxes](/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings)」を参照してください。

- EAC を開く方法については、「Exchange Server Exchange[管理センター」を参照Exchange Server。](/Exchange/architecture/client-access/exchange-admin-center) Exchange 管理シェル を開くには、「[Open the Exchange Management Shell](/powershell/exchange/open-the-exchange-management-shell)」を参照してください。

- オンプレミス Exchange のメール フロー ルールの詳細については、次のトピックを参照してください。

  - [メール フロー ルール (Exchange Server](/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [メール フロー ルールの条件と例外 (述語) Exchange Server](/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [メール フロー ルールのアクション (Exchange Server](/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>EAC を使用して、EOP スパム メッセージの SCL を設定するメール フロー ルールを作成する

1. EAC で、 **[メール フロー]** \> **[ルール]** に移動します。

2. [**追加]** ![ アイコンをクリックし、表示されるドロップダウンで [新しいルールを作成 ](../../media/ITPro-EAC-AddIcon.png) する] を選択します。 

3. **[新しいルール]** のページが開いたら、以下の設定を行ってください:

   - **名前**: ルールの一意でわかりやすい名前を入力します。 次に例を示します。

     - EOP SFV:SPM to SCL 6

     - EOP SFV:SKS to SCL 6

     - EOP SFV:SKB to SCL 6

   - [**その他のオプション**] をクリックします。

   - **[メッセージ ヘッダーに次** の単語が **含** まれる] の \> **場合は、このルールを適用します**。

     [Enter **text] ヘッダーに表示される Enter words 文** が含まれています。次の手順を実行します。

     - [テキスト **の入力] をクリックします**。 表示される **[ヘッダー名の指定]** ダイアログで **、「X-Forefront-Antispam-Report」** と入力し **、[OK] をクリックします**。

     - [単語  **の入力] をクリックします**。 表示される [単語または語句の指定] ダイアログで、EOP スパム ヘッダー値 **(SFV:SPM、SFV:SKS、** または **SFV:SKB)** のいずれかを入力し、[追加] アイコンをクリックし ![ ](../../media/ITPro-EAC-AddIcon.png) **、[OK]** をクリックします。

   - **[メッセージのプロパティを** 変更 **する]** [ \> **スパム信頼レベル (SCL) の設定] を選択します**。

     表示される **[SCL の指定** ] ダイアログで **、[6]** (既定値は **5) を選択します**。

   完了したら、[保存] を **クリックします。**

残りの EOP スパムの評決値 **(SFV:SPM、SFV:SKS、****または SFV:SKB)** に対して、次の手順を繰り返します。 

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Exchange 管理シェルを使用して、EOP スパム メッセージの SCL を設定するメール フロー ルールを作成する

次の構文を使用して、3 つのメール フロー ルールを作成します。

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

次に例を示します。

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

詳細な構文とパラメーターについては、「[New-TransportRule](/powershell/module/exchange/new-transportrule)」を参照してください。

## <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

ハイブリッド環境の迷惑メール フォルダーにスパムを配信するようにスタンドアロン EOP が正常に構成されたことを確認するには、次の手順を実行します。

- EAC で、[メールフロールール] に移動し、ルールを選択し、[編集] アイコンをクリックして設定 \>  ![ ](../../media/ITPro-EAC-EditIcon.png) を確認します。

- Exchange 管理シェルで、メール フロー ルールの名前に置き換え、次のコマンドを実行して設定 \<RuleName\> を確認します。

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- スパムの送信メッセージをスキャンしない外部電子メール システムで、影響を受ける受信者に一般一括メール (GTUBE) メッセージを送信し、そのメッセージが迷惑メール フォルダーに配信されたのを確認します。 GTUBE メッセージは、マルウェア設定をテストするための European Institute for Computer Antivirus Research (EICAR) テキスト ファイルと似ています。

  GTUBE メッセージを送信するには、1 行の電子メール メッセージの本文に、スペースや改行を含めずに、次のテキストを含める必要があります。

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```