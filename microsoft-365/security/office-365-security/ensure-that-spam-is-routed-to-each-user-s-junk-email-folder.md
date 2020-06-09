---
title: ハイブリッド環境で EOP を迷惑メールに構成する
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online Protection ハイブリッド環境でスパムをユーザーの迷惑メールフォルダーにルーティングする方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dcfee309e532256a71511c3f6de019b22f5db093
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "44617056"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a>ハイブリッド環境で迷惑メールフォルダーにスパムを配信するようにスタンドアロン EOP を構成する

> [!IMPORTANT]
> このトピックは、ハイブリッド環境のスタンドアロン EOP のお客様のみを対象としています。 このトピックは、Exchange Online メールボックスを使用している Microsoft 365 のお客様には適用されません。

ハイブリッド環境でのスタンドアロンの Exchange Online Protection (EOP) のお客様の場合は、オンプレミスの Exchange 組織を構成して、EOP のスパムフィルタリング verdicts を認識して変換する必要があります。このため、社内メールボックスの迷惑メールルールは、メッセージを [迷惑メール] フォルダーに移動することができます。

具体的には、オンプレミスの Exchange 組織内のメールフロールール (トランスポートルールとも呼ばれます) を、次の EOP スパム対策のヘッダーおよび値のいずれかで検索する条件と、それらのメッセージのスパム信頼レベル (SCL) を6に設定するアクションを使用して作成する必要があります。

- `X-Forefront-Antispam-Report: SFV:SPM`(スパムフィルターでスパムとしてマークされたメッセージ)

- `X-Forefront-Antispam-Report: SFV:SKS`(スパムフィルター処理の前に EOP のメールフロールールによってスパムとしてマークされたメッセージ)

- `X-Forefront-Antispam-Report: SFV:SKB`(送信者の電子メールアドレスまたは電子メールドメインが EOP のブロックされた送信者の一覧または禁止ドメインの一覧に含まれているため、スパムフィルターによってスパムとしてマークされたメッセージ)

これらのヘッダー値の詳細については、「[スパム対策メッセージヘッダー](anti-spam-message-headers.md)」を参照してください。

このトピックでは、Exchange 管理センター (EAC) および社内 Exchange 組織の Exchange 管理シェル (Exchange PowerShell) で、これらのメールフロールールを作成する方法について説明します。

> [!TIP]
> オンプレミスのユーザーの迷惑メールフォルダーにメッセージを配信する代わりに、EOP でスパム対策ポリシーを構成して、EOP でスパムメッセージを検疫することができます。 詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- これらの手順を実行する前に、オンプレミスの Exchange 環境でアクセス許可を割り当てる必要があります。 具体的には、既定では、**組織の管理**、**コンプライアンス管理**、および**レコード管理**の役割に割り当てられている**トランスポートルール**の役割が割り当てられている必要があります。 詳細については、「[役割グループにメンバーを追加する](https://docs.microsoft.com/Exchange/permissions/role-group-members?view=exchserver-2019#add-members-to-a-role-group)」を参照してください。

- オンプレミスの Exchange 組織の迷惑メールフォルダーにメッセージを配信する場合は、次の設定の組み合わせによって制御されます。

  - Exchange 管理シェルの_SCLJunkThreshold_コマンド[レットのパラメーター](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig)の値。 既定値は4で、SCL が5以上の場合は、ユーザーの迷惑メールフォルダーにメッセージを配信する必要があります。

  - Exchange 管理シェルの[メールボックス](https://docs.microsoft.com/powershell/module/exchange/set-mailbox)の_SCLJunkThreshold_コマンドレットのパラメーター値。 既定値は空白 ($null) で、組織の設定が使用されることを意味します。

  詳細については、「 [Exchange スパム信頼レベル (SCL) のしきい値](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl)」を参照してください。

  - メールボックスで迷惑メールルールが有効になっているかどうか ( _enabled_パラメーターの値は、Exchange 管理シェルの[set-mailboxjunkemailconfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration)コマンドレットでは $true。 これは、配信後にメッセージを [迷惑メール] フォルダーに実際に移動する迷惑メールルールです。 既定では、メールボックスで迷惑メールルールが有効になっています。 詳細については、「[Configure Exchange antispam settings on mailboxes](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings)」を参照してください。
  
- Exchange サーバー上の EAC を開くには、「exchange [server の exchange 管理センター](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center)」を参照してください。 Exchange 管理シェルを開くには、「」を参照してください [https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell) 。

- オンプレミスの Exchange のメールフロールールの詳細については、以下のトピックを参照してください。

  - [Exchange Server のメールフロールール](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Exchange Server のメールフロールールの条件と例外 (述語)](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Exchange Server でのメールフロールールのアクション](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>EAC を使用して、EOP スパムメッセージの SCL を設定するメールフロールールを作成する

1. EAC で、 **[メール フロー]** \> **[ルール]** に移動します。

2. [追加] アイコン**をクリックし** ![ ](../../media/ITPro-EAC-AddIcon.png) 、表示されるドロップダウンで [**新しいルールの作成**] を選択します。

3. **[新しいルール]** のページが開いたら、以下の設定を行ってください:

   - [**名前**]: わかりやすい一意のルールの名前を入力します。 例:

     - EOP SFV: SPM から SCL 6

     - EOP SFV: SFV から SCL 6

     - EOP SFV: SKB から SCL 6

   - [**その他のオプション**] をクリックします。

   - [次の**場合、このルールを適用**する]:**メッセージヘッダーを選択すると**、 \> **これらの単語のいずれかが含まれ**ます。

     [**テキストのヘッダーに語句を入力**してください] が表示されている場合は、次の手順を実行します。

     - [**テキストの入力] を**クリックします。 表示される [**ヘッダー名の指定**] ダイアログで、「 **X-スパム対策-Report** 」と入力し、[ **OK**] をクリックします。

     - [**単語の入力] を**クリックします。 表示された [**単語または語句の指定**] ダイアログボックスで、EOP スパムヘッダー値 (**SFV: SPM**、 **sfv: Sfv**、または**sfv: SKB**) のいずれかを入力し、 **[追加**] アイコンをクリックして、[ ![ ](../../media/ITPro-EAC-AddIcon.png) **OK]** をクリックします。

   - **次の操作を行い**ます。 [**メッセージのプロパティを変更する**] [ \> **スパム信頼レベル (SCL) を設定**する] を選択します。

     表示される [ **SCL の指定**] ダイアログで、[ **6** ] (既定値は**5**) を選択します。

   完了したら、[**保存**] をクリックします。

残りの EOP spam verdict 値 (**Sfv: SPM**、 **SFV: sfv**、または**sfv: SKB**) に対して、これらの手順を繰り返します。

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Exchange 管理シェルを使用して、EOP スパムメッセージの SCL を設定するメールフロールールを作成する

3つのメールフロールールを作成するには、次の構文を使用します。

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

ハイブリッド環境で迷惑メールフォルダーにスパムを配信するようにスタンドアロン EOP が正常に構成されたことを確認するには、次のいずれかの手順を実行します。

- EAC で、[**メールフロー**ルール] に移動し、 \> **Rules**ルールを選択して**Edit**から、[edit ![ edit] アイコンをクリックし ](../../media/ITPro-EAC-EditIcon.png) て設定を確認します。

- Exchange 管理シェルで、を \<RuleName\> メールフロールールの名前に置き換え、次のコマンドを使用して設定を確認します。

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- **スパムの送信メッセージをスキャンしない**外部電子メールシステムでは、要求されていないバルクメール (gtube) メッセージの汎用テストを、影響を受ける受信者に送信し、迷惑メールフォルダーに配信されることを確認します。 GTUBE メッセージは、マルウェア設定をテストするための European Institute for Computer Antivirus Research (EICAR) テキスト ファイルと似ています。

  GTUBE メッセージを送信するには、電子メールメッセージの本文に、スペースや改行を含めずに、次のテキストを1行で入力します。

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```
