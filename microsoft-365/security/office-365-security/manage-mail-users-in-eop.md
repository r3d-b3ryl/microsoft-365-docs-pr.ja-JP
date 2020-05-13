---
title: メールユーザーをスタンドアロン EOP で管理する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: ディレクトリ同期、EAC、PowerShell を使用してユーザーを管理するなど、Exchange Online Protection (EOP) でメールユーザーを管理する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e40465901747bcbd006d437fa527a9803aad1e24
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208647"
---
# <a name="manage-mail-users-in-standalone-eop"></a>メールユーザーをスタンドアロン EOP で管理する

Exchange Online メールボックスを持たないスタンドアロンの Exchange Online Protection (EOP) 組織では、メールユーザーは基本的な種類のユーザーアカウントです。 メールユーザーは、スタンドアロンの EOP 組織内にアカウントの資格情報を持ち、リソースにアクセスできます (アクセス許可が割り当てられている)。 メールユーザーの電子メールアドレスが外部にある (たとえば、オンプレミスの電子メール環境で)。

> [!NOTE]
> メールユーザーを作成すると、対応するユーザーアカウントが Microsoft 365 管理センターで利用可能になります。 Microsoft 365 管理センターでユーザーアカウントを作成する場合、そのアカウントを使用してメールユーザーを作成することはできません。

スタンドアロン EOP でメールユーザーを作成および管理するために推奨される方法は、このトピックで後述する「[ディレクトリ同期を使用してメールユーザーを管理する](#use-directory-synchronization-to-manage-mail-users)」の説明に従ってディレクトリ同期を使用することです。

ユーザー数が少ないスタンドアロンの EOP 組織では、このトピックで説明されているように、Exchange 管理センター (EAC) またはスタンドアロン EOP PowerShell でメールユーザーを追加および管理できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- Exchange 管理センター (EAC) を開くには、「 [exchange admin center in STANDALONE EOP](exchange-admin-center-in-exchange-online-protection-eop.md)」を参照してください。

- スタンドアロンの EOP PowerShell に接続するには、「 [Exchange Online Protection の powershell への接続](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)」を参照してください。

- EOP PowerShell でメールユーザーを作成するときに、調整が発生することがあります。 また、EOP PowerShell コマンドレットはバッチ処理方法を使用して、コマンドの結果が表示されるまでに数分の伝達遅延が発生するようになります。

- これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。 具体的には、既定では、組織の管理 (グローバル管理者) および受信者管理役割グループに割り当てられているメール受信者作成 (作成) とメール受信者 (変更) の役割が必要です。 詳細については、「 [Permissions in STANDALONE EOP](feature-permissions-in-eop.md) 」を参照して、EAC を使用して、[役割グループのメンバーの一覧を変更](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)します。

- このトピックの手順に適用されるキーボードショートカットについては、「exchange [Online の exchange 管理センターのキーボードショートカット](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)」を参照してください。

> [!TIP]
> 問題がある場合は、 Exchange のフォーラムで質問してください。 「 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)フォーラム」を参照してください。

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a>Exchange 管理センターを使用してメールユーザーを管理する

### <a name="use-the-eac-to-create-mail-users"></a>EAC を使用してメールユーザーを作成する

1. EAC で、[受信者の**Recipients** \> **連絡先**] に移動します。

2. [**新しい** ![ 新規作成] アイコンをクリックし ](../../media/ITPro-EAC-AddIcon.png) ます。 [**新しいメールユーザー** ] ページが開いたら、次の設定を構成します。 でマークされた設定 <sup>\*</sup> は必須です。

   - **名**

   - **イニシャル**: ユーザーのミドルネームのイニシャル。

   - **姓**

   - <sup>\*</sup>[**表示名**]: 既定では、このボックスには、[**名**]、[**イニシャル**]、[**姓**] ボックスの値が表示されます。 この値を受け入れるか、または変更することができます。 この値は一意である必要があり、最大長は64文字です。

   - <sup>\*</sup>**エイリアス**: ユーザーに対して、最大64文字の一意のエイリアスを入力します。

   - **外部電子メールアドレス**: ユーザーの電子メールアドレスを入力します。 ドメインは、クラウドベースの組織の外部にある必要があります。

   - <sup>\*</sup>**ユーザー ID**: ユーザーがサービスにサインインするために使用するアカウントを入力します。 ユーザー ID は、アットマーク記号 (@) の左側のユーザー名と右側のドメインで構成されます。

   - <sup>\*</sup>[**新しいパスワード**] と [ <sup>\*</sup> **パスワードの確認**]: アカウントのパスワードを入力して再入力します。 パスワードが組織のパスワードの長さ、複雑さ、および履歴に関する要件を満たしていることを確認します。

3. 完了したら、 **[保存]** をクリックしてメール ユーザーを作成します。

### <a name="use-the-eac-to-modify-mail-users"></a>EAC を使用してメールユーザーを変更する

1. EAC で、[受信者の**Recipients** \> **連絡先**] に移動します。

2. 変更するメールユーザーを選択し、[編集アイコンの**編集**] をクリックし ![ ](../../media/ITPro-EAC-AddIcon.png) ます。

3. 開いたメールユーザーのプロパティページで、次のタブのいずれかをクリックして、プロパティを表示または変更します。

   完了したら、**[保存]** をクリックします。

#### <a name="general"></a>全般

**[全般**] タブを使用して、メールユーザーの基本情報を表示または変更します。

- **名**

- **頭文字**

- **姓**

- [**表示名**]: この名前は、組織のアドレス帳、電子メールの宛先行と差出人行、および EAC 内の連絡先の一覧に表示されます。 この名前は、表示名の前または後に空のスペースを含めることはできません。

- **ユーザー ID**: これは、Microsoft 365 のユーザーアカウントです。 ここでは、この値を変更できません。

#### <a name="contact-information"></a>連絡先情報

[**連絡先の情報**] タブを使用して、ユーザーの連絡先情報を表示または変更します。 このページの情報がアドレス帳に表示されます。

- **所在**
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
  - **メモ**

#### <a name="organization"></a>組織

[**組織**] タブを使用して、組織内のユーザーの役割に関する詳細情報を記録します。

- **役職**
- **部署**
- **Company**

### <a name="use-the-eac-to-remove-mail-users"></a>EAC を使用してメールユーザーを削除する

1. EAC で、[受信者の**Recipients** \> **連絡先**] に移動します。

2. 削除するメールユーザーを選択し、[削除] [削除] アイコン**をクリックし** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) ます。

## <a name="use-powershell-to-manage-mail-users"></a>PowerShell を使用してメールユーザーを管理する

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a>スタンドアロンの EOP PowerShell を使用してメールユーザーを表示する

スタンドアロン EOP PowerShell のすべてのメールユーザーの要約リストを返すには、次のコマンドを実行します。

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

特定のメールユーザーについての詳細情報を表示するには、 \< mailuseridentity を \> メールユーザーの名前、エイリアス、またはアカウント名に置き換えて、次のコマンドを実行します。

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

構文およびパラメーターの詳細については、「[取得-受信者](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient)と[取得ユーザー](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user)」を参照してください。

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a>スタンドアロンの EOP PowerShell を使用してメールユーザーを作成する

スタンドアロン EOP PowerShell でメールユーザーを作成するには、次の構文を使用します。

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

**注**:

- _Name_パラメーターは必須で、最大長は64文字で、一意である必要があります。 _DisplayName_パラメーターを使用しない場合、 _name_パラメーターの値が表示名として使用されます。
- _Alias_パラメーターを使用しない場合、 _MicrosoftOnlneServicesID_パラメーターの左側がエイリアスに使用されます。
- _ExternalEmailAddress_パラメーターを使用しない場合、 _MicrosoftOnlineServicesID_の値が外部の電子メールアドレスに使用されます。

この例では、次の設定を使用してメールユーザーを作成します。

- 名前は JeffreyZeng で、表示名は Jeffrey Zeng です。
- 名は Jeffrey で、姓は Zeng です。
- エイリアスは jeffreyz です。
- 外部の電子メール アドレスは jzeng@tailspintoys.com です。
- アカウント名は jeffreyz@contoso.onmicrosoft.com です。
- パスワードは Pa$$word1 です。

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

構文およびパラメーターの詳細については、「 [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-eopmailuser)」を参照してください。

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a>スタンドアロンの EOP PowerShell を使用してメールユーザーを変更する

スタンドアロン EOP PowerShell で既存のメールユーザーを変更するには、次の構文を使用します。

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Textg>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
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

構文およびパラメーターの詳細については、「 [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopmailuser)」を参照してください。

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a>スタンドアロンの EOP PowerShell を使用してメールユーザーを削除する

スタンドアロン EOP PowerShell でメールユーザーを削除するには、 \< mailuseridentity を \> メールユーザーの名前、エイリアス、またはアカウント名に置き換えて、次のコマンドを実行します。

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

この例では、Jeffrey Zeng のメールユーザーを削除します。

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

構文およびパラメーターの詳細については、「 [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopmailuser)」を参照してください。

## <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

メールユーザーの作成、変更、または削除が正常に完了したことを確認するには、次のいずれかの手順を使用します。

- EAC で、[受信者の**Recipients** \> **連絡先**] に移動します。 メールユーザーが一覧に表示されている (または一覧に表示されていない) ことを確認します。 メールユーザーを選択して、詳細ウィンドウに情報を表示するか、[編集アイコンの**編集**] をクリックして ![ 設定を表示し ](../../media/ITPro-EAC-AddIcon.png) ます。

- スタンドアロン EOP PowerShell で、次のコマンドを実行して、メールユーザーが一覧に表示されている (または一覧に表示されていない) ことを確認します。

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- \<Mailuseridentity を \> メールユーザーの名前、エイリアス、またはアカウント名に置き換え、次のコマンドを実行して設定を確認します。

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a>ディレクトリ同期を使用してメール ユーザーを管理する

スタンドアロン EOP では、オンプレミスの Active Directory を使用しているお客様はディレクトリ同期を利用できます。 これらのアカウントを Azure Active Directory (Azure AD) と同期することができます。これにより、アカウントのコピーがクラウドに保存されます。 既存のユーザーアカウントを Azure Active Directory と同期する場合は、Exchange 管理センター (EAC) またはスタンドアロン EOP PowerShell の [**受信者**] ウィンドウで、これらのユーザーを表示できます。

**注**:

- ディレクトリ同期を使用して受信者を管理している場合でも、Microsoft 365 管理センターでユーザーを追加および管理することはできますが、オンプレミスの Active Directory と同期されることはありません。 これは、ディレクトリ同期では社内 Active Directory からクラウドへの受信者の同期だけが実行されるためです。

- 次の機能によるディレクトリ同期の使用をお勧めします。

  - **Outlook の差出人セーフリストと受信拒否リスト**: サービスに同期すると、これらのリストはサービスのスパムフィルタリングよりも優先されます。 これにより、ユーザーは、個々の送信者およびドメインエントリを使用して、自分の差出人セーフリストと受信拒否リストを管理できます。 詳細については、「 [Exchange Online メールボックスで迷惑メールの設定を構成する](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes)」を参照してください。

  - **ディレクトリベースのエッジブロック (dbeb)**: DBEB の詳細については、「[ディレクトリベースのエッジブロックを使用して無効な受信者に送信されたメッセージを拒否する](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)」を参照してください。

  - **エンドユーザーによる検疫へのアクセス**: 検疫されたメッセージにアクセスするには、受信者がサービスに有効なユーザー ID とパスワードを持っている必要があります。 検疫の詳細については、「[ユーザーとして検疫済みメッセージを検索して解放する](https://docs.microsoft.com/microsoft-365/security/office-365-security/find-and-release-quarantined-messages-as-a-user)」を参照してください。

  - **メールフロールール (トランスポートルールとも呼ばれる)**: ディレクトリ同期を使用すると、既存の Active directory ユーザーとグループがクラウドに自動的にアップロードされます。その後、特定のユーザーやグループを対象とするメールフロールールを作成して、それらをサービスに手動で追加する必要はありません。 [動的配布グループ](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups)はディレクトリ同期を使用して同期できないことに注意してください。

必要なアクセス許可を取得し、ディレクトリ同期を準備します (「 [Azure Active directory でのハイブリッド id とは](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity)」を参照)。

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a>ディレクトリを Azure Active Directory Connect (AAD Connect) と同期する

1. 「 [AZURE AD Connect 同期: 同期の理解とカスタマイズ](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)」の説明に従って、ディレクトリ同期をアクティブ化します。

2. [AZURE AD Connect の前提条件](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)に従って、AAD Connect を実行するようにオンプレミスのコンピューターをインストールして構成します。

3. [AZURE AD Connect に使用するインストールの種類を選択し](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation)ます。

   - [ニュース](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [Custom](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [パススルー認証](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> Azure Active Directory 同期ツール構成ウィザードを終了すると、Active Directory フォレストに **MSOL_AD_SYNC** アカウントが作成されます。このアカウントは、社内 Active Directory 情報の読み取りと同期に使われます。ディレクトリ同期が正しく行われるように、ローカル ディレクトリ同期サーバー上の TCP 443 が開いていることを確認してください。

同期を構成した後、AAD Connect が正しく同期されていることを確認してください。 EAC で、 **[受信者]** \> **[連絡先]** に移動し、ユーザーの一覧が社内環境から同期されていることを確認します。
