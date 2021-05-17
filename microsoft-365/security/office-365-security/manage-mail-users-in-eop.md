---
title: スタンドアロン EOP でメール ユーザーを管理する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: ディレクトリ同期、EAC、PowerShell を使用してユーザーを管理するExchange Online Protection (EOP) でメール ユーザーを管理する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 863bde5ef860ee980f768ddc085379180e6a71aa
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205046"
---
# <a name="manage-mail-users-in-standalone-eop"></a>スタンドアロン EOP でメール ユーザーを管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
-  [Exchange Online Protectionスタンドアロン](exchange-online-protection-overview.md)

メールボックスをExchange Online Protectionスタンドアロン Exchange Online (EOP) 組織では、メール ユーザーは基本的な種類のユーザー アカウントです。 メール ユーザーは、スタンドアロンの EOP 組織にアカウント資格情報を持ち、リソースにアクセスできます (アクセス許可が割り当て済み)。 メール ユーザーの電子メール アドレスは外部 (オンプレミスのメール環境など) です。

> [!NOTE]
> メール ユーザーを作成すると、対応するユーザー アカウントが管理センター Microsoft 365できます。 管理センターでユーザー アカウントをMicrosoft 365、そのアカウントを使用してメール ユーザーを作成することはできません。

スタンドアロン EOP でメール ユーザーを作成および管理する推奨される方法は、この記事の[](#use-directory-synchronization-to-manage-mail-users)後半の「ディレクトリ同期を使用してメール ユーザーを管理する」セクションで説明されているディレクトリ同期を使用する方法です。

ユーザー数が少ないスタンドアロン EOP 組織では、この記事で説明するように、Exchange 管理センター (EAC) またはスタンドアロン EOP PowerShell でメール ユーザーを追加および管理できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- 管理センター (EAC Exchange開く場合は、「スタンドアロン[EOP Exchange管理センター」を参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。

- スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- EOP PowerShell でメール ユーザーを作成すると、調整が発生する可能性があります。 また、EOP PowerShell コマンドレットはバッチ処理メソッドを使用して、コマンドの結果が表示される数分前に伝達遅延が発生します。

- この記事の手順を実行するには、Exchange Online Protectionにアクセス許可を割り当てる必要があります。 具体的には、既定で組織 **管理 (グローバル** 管理者) および受信者管理役割グループに割り当てられているメール受信者の **作成 (作成**) およびメール受信者 **(変更**) の役割が必要です。 詳細については、「スタンドアロン [EOP のアクセス](feature-permissions-in-eop.md) 許可」および「役割グループのメンバーの一覧を [変更する EAC](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)を使用する」を参照してください。

- この記事の手順 Exchangeに適用されるキーボード ショートカットの詳細については、「Exchange Online の管理センターのキーボード ショートカット」[を参照Exchange Online。](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> 問題がある場合は、 Exchange のフォーラムで質問してください。 [ユーザー][フォーラムExchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)アクセスします。

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a>メール ユーザーを管理Exchange管理センターを使用する

### <a name="use-the-eac-to-create-mail-users"></a>EAC を使用してメール ユーザーを作成する

1. EAC で、[受信者の **連絡先] に移動** \> **します。**

2. [新 **しい新規]** ![ アイコンをクリック ](../../media/ITPro-EAC-AddIcon.png) します。 開く **[新しいメール ユーザー]** ページで、次の設定を構成します。 <sup>\*</sup> の付いた設定は必須項目です。

   - **名**

   - **イニシャル**: ユーザーの中間イニシャル。

   - **姓**

   - <sup>\*</sup>**表示名**: 既定では、このボックスには、名、イニシャル、および名の **各ボックスの値が** 表示されます。 この値を受け入れるか、変更できます。 値は一意で、最大長は 64 文字です。

   - <sup>\*</sup>**Alias**: ユーザーに対して最大 64 文字を使用して、一意のエイリアスを入力します。

   - **外部メール アドレス**: ユーザーの電子メール アドレスを入力します。 ドメインはクラウドベースの組織の外部である必要があります。

   - <sup>\*</sup>**ユーザー ID:** ユーザーがサービスへのサインインに使用するアカウントを入力します。 ユーザー ID は、at (@) 記号 (@) の左側のユーザー名と右側のドメインで構成されます。

   - <sup>\*</sup>**新しいパスワード** <sup>\*</sup> **とパスワードの確認**: アカウント のパスワードを入力して再入力します。 パスワードが組織のパスワードの長さ、複雑さ、および履歴の要件に準拠していることを確認します。

3. 完了したら、 **[保存]** をクリックしてメール ユーザーを作成します。

### <a name="use-the-eac-to-modify-mail-users"></a>EAC を使用してメール ユーザーを変更する

1. EAC で、[受信者の連絡先 **] に** \> **移動します**。

2. 変更するメール ユーザーを選択し、[編集] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。

3. 開くメール ユーザーのプロパティ ページで、次のいずれかのタブをクリックしてプロパティを表示または変更します。

   完了したら、**[保存]** をクリックします。

#### <a name="general"></a>全般

[全般] **タブ** を使用して、メール ユーザーに関する基本情報を表示または変更します。

- **名**

- **頭文字**

- **姓**

- **表示名**: この名前は、組織のアドレス帳、電子メールの [To:] 行と [From:] 行、および EAC の連絡先の一覧に表示されます。 この名前は、表示名の前または後に空のスペースを含めることはできません。

- **ユーザー ID**: このアカウントは、ユーザーのアカウントMicrosoft 365。 この値はここで変更できます。

#### <a name="contact-information"></a>連絡先情報

[連絡先情報 **] タブを** 使用して、ユーザーの連絡先情報を表示または変更します。 このページの情報がアドレス帳に表示されます。

- **Street**
- **市区町村**
- **都道府県**
- **郵便番号**
- **国/地域設定**
- **勤務先の電話番号**
- **携帯電話**
- **Fax**
- **[その他のオプション]**

  - **Office**
  - **自宅電話**
  - **Web ページ**
  - **注**

#### <a name="organization"></a>組織

[組織 **] タブ** を使用して、組織内のユーザーの役割に関する詳細情報を記録します。

- **役職**
- **部署**
- **Company**

### <a name="use-the-eac-to-remove-mail-users"></a>EAC を使用してメール ユーザーを削除する

1. EAC で、[受信者の連絡先 **] に** \> **移動します**。

2. 削除するメール ユーザーを選択し、[削除] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。

## <a name="use-powershell-to-manage-mail-users"></a>PowerShell を使用してメール ユーザーを管理する

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a>スタンドアロン EOP PowerShell を使用してメール ユーザーを表示する

スタンドアロン EOP PowerShell のすべてのメール ユーザーの概要リストを取得するには、次のコマンドを実行します。

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

特定のメール ユーザーに関する詳細情報を表示するには、メール ユーザーの名前、エイリアス、またはアカウント名に置き換えて、次の \<MailUserIdentity\> コマンドを実行します。

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

構文とパラメーターの詳細については [、「Get-Recipient](/powershell/module/exchange/get-recipient) and [Get-User」を参照してください](/powershell/module/exchange/get-user)。

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a>スタンドアロン EOP PowerShell を使用してメール ユーザーを作成する

スタンドアロン EOP PowerShell でメール ユーザーを作成するには、次の構文を使用します。

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

**注**:

- _Name パラメーター_ は必須で、最大長は 64 文字で、一意である必要があります。 DisplayName パラメーターを使用しない場合は _、Name_ パラメーターの値が表示名に使用されます。
- _Alias_ パラメーターを使用しない場合は _、MicrosoftOnlineServicesID_ パラメーターの左側がエイリアスに使用されます。
- _ExternalEmailAddress_ パラメーターを使用しない場合は、外部メール アドレスに _MicrosoftOnlineServicesID_ 値が使用されます。

この例では、次の設定を使用してメール ユーザーを作成します。

- 名前は JeffreyZeng で、表示名は Jeffrey Zeng です。
- 名は Jeffrey で、姓は Zeng です。
- エイリアスは jeffreyz です。
- 外部の電子メール アドレスは jzeng@tailspintoys.com です。
- アカウント名は jeffreyz@contoso.onmicrosoft.com。
- パスワードは Pa$$word1 です。

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

構文とパラメーターの詳細については [、「New-EOPMailUser」を参照してください](/powershell/module/exchange/new-eopmailuser)。

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a>スタンドアロン EOP PowerShell を使用してメール ユーザーを変更する

スタンドアロン EOP PowerShell の既存のメール ユーザーを変更するには、次の構文を使用します。

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Text>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

この例では、Pilar Pinilla の外部電子メール アドレスを設定します。

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

この例では、すべてのメール ユーザーの [会社] プロパティを Contoso に設定します。

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

構文とパラメーターの詳細については [、「Set-EOPMailUser」を参照してください](/powershell/module/exchange/set-eopmailuser)。

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a>スタンドアロン EOP PowerShell を使用してメール ユーザーを削除する

スタンドアロン EOP PowerShell でメール ユーザーを削除するには、メール ユーザーの名前、エイリアス、またはアカウント名に置き換え、次の \<MailUserIdentity\> コマンドを実行します。

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

この例では、Jeffrey Zeng のメール ユーザーを削除します。

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

構文とパラメーターの詳細については [、「Remove-EOPMailUser」を参照してください](/powershell/module/exchange/remove-eopmailuser)。

## <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

スタンドアロン EOP でメール ユーザーが正常に作成、変更、または削除されたことを確認するには、次の手順を使用します。

- EAC で、[受信者の連絡先 **] に** \> **移動します**。 メール ユーザーが一覧に表示されている (または一覧に表示されていない) か確認します。 メール ユーザーを選択し、[詳細] ウィンドウで情報を表示するか、[ **編集]** アイコンをクリックして設定 ![ ](../../media/ITPro-EAC-AddIcon.png) を表示します。

- スタンドアロン EOP PowerShell で、次のコマンドを実行して、メール ユーザーが一覧に表示されている (または一覧に表示されていない) のを確認します。

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- メール ユーザーの名前、エイリアス、またはアカウント名に置き換え、次のコマンドを実行して設定 \<MailUserIdentity\> を確認します。

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a>ディレクトリ同期を使用してメール ユーザーを管理する

スタンドアロン EOP では、オンプレミスの Active Directory をお持ちのお客様にディレクトリ同期を利用できます。 これらのアカウントをクラウドにAzure Active Directory (Azure AD) に同期できます。 既存のユーザー アカウントを Azure Active Directory に同期すると、それらのユーザーを Exchange 管理センター  (EAC) の [受信者] ウィンドウまたはスタンドアロンの EOP PowerShell で表示できます。

**注**:

- ディレクトリ同期を使用して受信者を管理する場合でも、Microsoft 365 管理センターでユーザーを追加および管理できますが、ユーザーはオンプレミスの Active Directory と同期されません。 これは、ディレクトリ同期では社内 Active Directory からクラウドへの受信者の同期だけが実行されるためです。

- 次の機能によるディレクトリ同期の使用をお勧めします。

  - **Outlook セーフ送信者リスト** と受信拒否リスト : サービスに同期すると、これらのリストはサービスのスパム フィルター処理よりも優先されます。 これにより、ユーザーは個々の送信者とセーフを使用して、送信者リストと受信拒否リストを管理できます。 詳細については、「[Exchange Online のメールボックスの迷惑メール設定を構成する](configure-junk-email-settings-on-exo-mailboxes.md)」を参照してください。

  - **ディレクトリ ベースのエッジ ブロック (DBEB)**: DBEB の詳細については、「Use Directory Based Edge Blocking to [reject messages to invalid recipients](/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)」 を参照してください。

  - **検疫へのエンド ユーザー アクセス**: 検疫済みメッセージにアクセスするには、受信者がサービスに有効なユーザー ID とパスワードを持っている必要があります。 検疫の詳細については、「検疫済みメッセージをユーザーとして検索 [して解放する」を参照してください](find-and-release-quarantined-messages-as-a-user.md)。

  - **メール フロー** ルール (トランスポート ルールとも呼ばれる) : ディレクトリ同期を使用すると、既存の Active Directory ユーザーとグループがクラウドに自動的にアップロードされ、サービスに手動で追加することなく、特定のユーザーまたはグループを対象とするメール フロー ルールを作成できます。 動的配布 [グループはディレクトリ](/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) 同期では同期できない点に注意してください。

必要なアクセス許可を取得し、ディレクトリ同期の準備を行います(「ハイブリッド ID とハイブリッド ID は何ですか[Azure Active Directory?](/azure/active-directory/hybrid/whatis-hybrid-identity)

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a>ディレクトリを Azure Active Directory Connectと同期する (AAD Connect)

1. Azure の同期の説明に従ってディレクトリ[同期AD Connect同期を確認し、カスタマイズします](/azure/active-directory/hybrid/how-to-connect-sync-whatis)。

2. 「Azure の前提条件」の説明に従って、AAD Connectを実行するようにオンプレミス コンピューターをインストールして[構成AD Connect。](/azure/active-directory/hybrid/how-to-connect-install-prerequisites)

3. [Azure アプリケーションで使用するインストールの種類を選択AD Connect。](/azure/active-directory/hybrid/how-to-connect-install-select-installation)

   - [Express](/azure/active-directory/hybrid/how-to-connect-install-express)

   - [Custom](/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [パススルー認証](/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> Azure Active Directory 同期ツール構成ウィザードを終了すると、Active Directory フォレストに **MSOL_AD_SYNC** アカウントが作成されます。このアカウントは、社内 Active Directory 情報の読み取りと同期に使われます。ディレクトリ同期が正しく行われるように、ローカル ディレクトリ同期サーバー上の TCP 443 が開いていることを確認してください。

同期を構成したら、AAD が正しく同期Connect確認してください。 EAC で、 **[受信者]** \> **[連絡先]** に移動し、ユーザーの一覧が社内環境から同期されていることを確認します。