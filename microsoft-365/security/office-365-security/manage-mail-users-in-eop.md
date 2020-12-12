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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: ディレクトリ同期、EAC、PowerShell を使用してユーザーを管理する方法など、Exchange Online Protection (EOP) でメール ユーザーを管理する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a8258a63fe0fbf4a6b5641fbdef213f25de2e4dd
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658835"
---
# <a name="manage-mail-users-in-standalone-eop"></a>スタンドアロン EOP でメール ユーザーを管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織では、メール ユーザーは基本的な種類のユーザー アカウントです。 メール ユーザーは、スタンドアロン EOP 組織のアカウント資格情報を持ち、リソースにアクセスできます (アクセス許可が割り当てられている)。 メール ユーザーの電子メール アドレスは外部 (たとえば、オンプレミスのメール環境) です。

> [!NOTE]
> メール ユーザーを作成すると、対応するユーザー アカウントが Microsoft 365 管理センターで利用できます。 Microsoft 365 管理センターでユーザー アカウントを作成する場合、そのアカウントを使用してメール ユーザーを作成することはできません。

スタンドアロン EOP でメール ユーザーを作成および管理するには、この記事で後述する「ディレクトリ[](#use-directory-synchronization-to-manage-mail-users)同期を使用してメール ユーザーを管理する」セクションで説明するように、ディレクトリ同期を使用する方法をお勧めします。

ユーザー数が少ないスタンドアロン EOP 組織の場合は、この記事で説明するように、Exchange 管理センター (EAC) またはスタンドアロンの EOP PowerShell でメール ユーザーを追加および管理できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- Exchange 管理センター (EAC) を開く方法については、スタンドアロン EOP の [Exchange 管理センターを参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。

- スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- EOP PowerShell でメール ユーザーを作成すると、調整が発生する可能性があります。 また、EOP PowerShell コマンドレットはバッチ処理方法を使用して、コマンドの結果が表示される数分前に伝達遅延が発生します。

- この記事の手順を実行する前に、Exchange Online Protection でアクセス許可を割り当てる必要があります。 具体的には、既定で組織の管理 **(グローバル** 管理者) 役割グループと受信者管理役割グループに割り当てられる、メール受信者の作成 **(** 作成) 役割とメール受信者 **(変更**) 役割が必要です。 詳細については、「スタンドアロン [EOP のアクセス](feature-permissions-in-eop.md) 許可」および「EAC を使用して役割グループのメンバーの一覧 [を変更する」を参照してください](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。

- この記事の手順に適用できるキーボード ショートカットの詳細については [、Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)の Exchange 管理センターのキーボード ショートカットを参照してください。

> [!TIP]
> 問題がある場合は、 Exchange のフォーラムで質問してください。 Exchange [Online Protection フォーラムにアクセス](https://go.microsoft.com/fwlink/p/?linkId=285351) します。

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a>Exchange 管理センターを使用してメール ユーザーを管理する

### <a name="use-the-eac-to-create-mail-users"></a>EAC を使用してメール ユーザーを作成する

1. EAC で、受信者の **連絡先に移動** \> **します。**

2. [新 **しい新規]** ![ アイコンをクリックします ](../../media/ITPro-EAC-AddIcon.png) 。 開く **[新しいメール ユーザー** ] ページで、次の設定を構成します。 an が付いている設定 <sup>\*</sup> は必須です。

   - **名**

   - **イニシャル**: 人物の中間イニシャル。

   - **姓**

   - <sup>\*</sup>**表示名**: 既定では、このボックスには [名]、[イニシャル]、および [氏名] ボックス **の値が** 表示されます。  この値を受け入れるか、変更することができます。 値は一意で、最大長は 64 文字です。

   - <sup>\*</sup>**エイリアス**: ユーザーに対して最大 64 文字を使用して一意のエイリアスを入力します。

   - **外部電子メール アドレス**: ユーザーの電子メール アドレスを入力します。 ドメインはクラウドベースの組織の外部である必要があります。

   - <sup>\*</sup>**ユーザー ID**: ユーザーがサービスにサインインするために使用するアカウントを入力します。 ユーザー ID は、at (@) 記号 (@) の左側のユーザー名と右側のドメインで構成されます。

   - <sup>\*</sup>**新しいパスワード** と <sup>\*</sup> **パスワードの確認**: アカウントパスワードを入力して再入力します。 パスワードが組織のパスワードの長さ、複雑さ、履歴の要件に準拠していることを確認します。

3. 完了したら、 **[保存]** をクリックしてメール ユーザーを作成します。

### <a name="use-the-eac-to-modify-mail-users"></a>EAC を使用してメール ユーザーを変更する

1. EAC で、受信者の連絡先 **に移動** \> **します**。

2. 変更するメール ユーザーを選択し、[編集] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。

3. 表示されたメール ユーザーのプロパティ ページで、次のいずれかのタブをクリックしてプロパティを表示または変更します。

   完了したら、**[保存]** をクリックします。

#### <a name="general"></a>全般

[全般 **] タブを** 使用して、メール ユーザーに関する基本情報を表示または変更します。

- **名**

- **頭文字**

- **姓**

- **表示名**: この名前は、組織のアドレス帳、電子メールの [To:] 行と [From:] 行、および EAC の連絡先の一覧に表示されます。 この名前は、表示名の前または後に空のスペースを含めることはできません。

- **ユーザー ID**: Microsoft 365 のユーザーのアカウントです。 この値はここで変更できます。

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

[組織 **] タブ** を使用して、組織内でのユーザーの役割に関する詳細情報を記録します。

- **役職**
- **部署**
- **Company**

### <a name="use-the-eac-to-remove-mail-users"></a>EAC を使用してメール ユーザーを削除する

1. EAC で、受信者の連絡先 **に移動** \> **します**。

2. 削除するメール ユーザーを選択し、[削除] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。

## <a name="use-powershell-to-manage-mail-users"></a>PowerShell を使用してメール ユーザーを管理する

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a>スタンドアロンの EOP PowerShell を使用してメール ユーザーを表示する

スタンドアロンの EOP PowerShell ですべてのメール ユーザーの要約リストを返す場合は、次のコマンドを実行します。

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

構文およびパラメーターの詳細については [、「Get-Recipient」](https://docs.microsoft.com/powershell/module/exchange/get-recipient) および [「Get-User」を参照してください](https://docs.microsoft.com/powershell/module/exchange/get-user)。

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a>スタンドアロンの EOP PowerShell を使用してメール ユーザーを作成する

スタンドアロンの EOP PowerShell でメール ユーザーを作成するには、次の構文を使用します。

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

**注**:

- Name _パラメーター_ は必須で、最大長は 64 文字で、一意である必要があります。 _DisplayName_ パラメーターを使用しない場合 _、Name_ パラメーターの値が表示名に使用されます。
- _Alias_ パラメーターを使用しない場合は _、MicrosoftOnlineServicesID_ パラメーターの左側がエイリアスに使用されます。
- _ExternalEmailAddress_ パラメーターを使用しない場合は _、MicrosoftOnlineServicesID_ 値が外部電子メール アドレスに使用されます。

この例では、次の設定でメール ユーザーを作成します。

- 名前は JeffreyZeng、表示名は Jeffrey Zeng です。
- 名は Jeffrey で、姓は Zeng です。
- エイリアスは jeffreyz です。
- 外部の電子メール アドレスは jzeng@tailspintoys.com です。
- アカウント名がjeffreyz@contoso.onmicrosoft.com。
- パスワードは Pa$$word1 です。

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

構文およびパラメーターの詳細については [、「New-EOPMailUser」を参照してください](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser)。

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a>スタンドアロンの EOP PowerShell を使用してメール ユーザーを変更する

スタンドアロンの EOP PowerShell で既存のメール ユーザーを変更するには、次の構文を使用します。

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

構文およびパラメーターの詳細については [、「Set-EOPMailUser」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser)。

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a>スタンドアロンの EOP PowerShell を使用してメール ユーザーを削除する

スタンドアロンの EOP PowerShell でメール ユーザーを削除するには、メール ユーザーの名前、エイリアス、またはアカウント名に置き換え、次の \<MailUserIdentity\> コマンドを実行します。

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

この例では、Jeffrey Zeng のメール ユーザーを削除します。

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

構文およびパラメーターの詳細については [、「Remove-EOPMailUser」を参照してください](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser)。

## <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

スタンドアロン EOP でメール ユーザーが正常に作成、変更、または削除されたことを確認するには、次の手順を使用します。

- EAC で、受信者の連絡先 **に移動** \> **します**。 メール ユーザーが一覧に表示されている (または一覧に表示されていない) か確認します。 メール ユーザーを選択し、[詳細] ウィンドウに情報を表示するか、[編集] アイコンをクリックして設定 ![ ](../../media/ITPro-EAC-AddIcon.png) を表示します。

- スタンドアロンの EOP PowerShell で、次のコマンドを実行して、メール ユーザーが一覧に表示されている (または一覧に表示されていない) か確認します。

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- メール ユーザーの名前、エイリアス、またはアカウント名に置き換え、次のコマンドを実行して \<MailUserIdentity\> 設定を確認します。

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a>ディレクトリ同期を使用してメール ユーザーを管理する

スタンドアロン EOP では、オンプレミスの Active Directory を使用しているお客様がディレクトリ同期を利用できます。 これらのアカウントを Azure Active Directory (Azure AD) に同期し、アカウントのコピーがクラウドに保存されます。 既存のユーザー アカウントを Azure Active Directory に同期する場合は、Exchange管理センター (EAC) の [受信者] ウィンドウまたはスタンドアロンの EOP PowerShell でそれらのユーザーを表示できます。

**注**:

- ディレクトリ同期を使用して受信者を管理する場合でも、Microsoft 365 管理センターでユーザーを追加および管理できますが、ユーザーはオンプレミスの Active Directory と同期されません。 これは、ディレクトリ同期では社内 Active Directory からクラウドへの受信者の同期だけが実行されるためです。

- 次の機能によるディレクトリ同期の使用をお勧めします。

  - **Outlook の差出** 人セーフ リストと受信拒否リスト : サービスに同期すると、これらのリストはサービスでのスパム フィルターよりも優先されます。 これにより、ユーザーは個々の送信者およびドメイン エントリを使用して、自分の差出人セーフ リストと受信拒否リストを管理できます。 詳細については、「[Exchange Online のメールボックスの迷惑メール設定を構成する](configure-junk-email-settings-on-exo-mailboxes.md)」を参照してください。

  - **ディレクトリ ベースのエッジ ブロック (DBEB)**: DBEB の詳細については、「ディレクトリ ベースのエッジ ブロックを使用して無効な受信者に送信されたメッセージを拒否する」を [参照してください](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)。

  - **エンド ユーザーの検疫への** アクセス : 検疫済みメッセージにアクセスするには、受信者がサービスに有効なユーザー ID とパスワードを持っている必要があります。 検疫の詳細については、「ユーザーとして検疫済み [メッセージを検索して解放する」を参照してください](find-and-release-quarantined-messages-as-a-user.md)。

  - メール フロー ルール (トランスポート ルールとも呼ばれる **)**: ディレクトリ同期を使用すると、既存の Active Directory ユーザーとグループが自動的にクラウドにアップロードされ、サービスに手動で追加することなく、特定のユーザーやグループを対象とするメール フロー ルールを作成できます。 動的配布 [グループは、](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) ディレクトリ同期では同期できない点に注意してください。

Azure Active Directory とのハイブリッド ID の説明に従って、必要なアクセス許可を取得し、 [ディレクトリ同期を準備します](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity)。

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a>ディレクトリを Azure Active Directory Connect (AAD Connect) と同期する

1. Azure AD Connect 同期の説明に従って、ディレクトリ [同期をアクティブ化します。同期について理解し、カスタマイズします](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)。

2. 「Azure AD Connect の前提条件」の説明に従って、AAD Connect を実行するようにオンプレミス [のコンピューターをインストールしてADします](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)。

3. Azure AD Connect に使用する[インストールの種類を選択します](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation)。

   - [Express](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [Custom](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [パススルー認証](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> Azure Active Directory 同期ツール構成ウィザードを終了すると、Active Directory フォレストに **MSOL_AD_SYNC** アカウントが作成されます。このアカウントは、社内 Active Directory 情報の読み取りと同期に使われます。ディレクトリ同期が正しく行われるように、ローカル ディレクトリ同期サーバー上の TCP 443 が開いていることを確認してください。

同期を構成したら、AAD Connect が正しく同期されていることを確認してください。 EAC で、 **[受信者]** \> **[連絡先]** に移動し、ユーザーの一覧が社内環境から同期されていることを確認します。
