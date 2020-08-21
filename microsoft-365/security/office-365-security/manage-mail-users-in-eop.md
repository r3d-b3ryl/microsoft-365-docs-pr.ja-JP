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
description: ユーザーの管理でのディレクトリ同期、EAC、PowerShell の使用など、Exchange Online Protection (EOP) でメール ユーザーを管理する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 64b7effadd96b6dc025677139c4303acd538dadb
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827077"
---
# <a name="manage-mail-users-in-standalone-eop"></a>スタンドアロン EOP でメール ユーザーを管理する

Exchange Online メールボックスを使用しているスタンドアロン Exchange Online Protection (EOP) 組織の場合、メール ユーザーは基本タイプのユーザー アカウントです。 メール ユーザーは、スタンドアロン EOP 組織のアカウント資格情報を持っており、リソースにアクセスできます (アクセス許可の割り当てが付与されている)。 メール ユーザーの電子メール アドレスが外部 (社内の電子メール環境など) である。

> [!NOTE]
> メール ユーザーを作成する場合、対応するユーザー アカウントは Microsoft 365 管理センターで使用できます。 Microsoft 365 管理センターでユーザー アカウントを作成する際、そのアカウントを使用してメール ユーザーを作成することはできません。

スタンドアロン EOP でメール ユーザーを作成および管理する方法として、このトピックの後半のセクションで説明している「ディレクトリ同期を使用する [」で説明](#use-directory-synchronization-to-manage-mail-users) されているとおりに、ディレクトリ同期を使用する方法が推奨されています。

ユーザー数がわずかで組織の場合は、このトピックで説明されている方法で、Exchange 管理センター (EAC) またはスタンドアロン EOP PowerShell でメール ユーザーを追加して管理できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- Exchange 管理センター (EAC) を開くには、スタンドアロン [EOP の Exchange 管理センターを参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。

- スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- EOP PowerShell でメール ユーザーを作成する場合、調整が発生する可能性があります。 また、EOP PowerShell コマンドレットはバッチ処理方法を使用します。この方法では、コマンドの結果が表示されるまで数分の送信遅延がかかることがあります。

- これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。 具体的には、メール受信者の作成 (作成) 役割とメール受信者 (変更) 役割が必要です。既定で OrganizationManagement (グローバル管理者) 役割と RecipientManagement 役割グループに割り当てます。 詳細については、「スタンドアロン [EOP のアクセス許可」を参照し、EAC](feature-permissions-in-eop.md) [を使用して役割グループ内のメンバーの一覧を変更します](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。

- このトピックの手順で使用可能なキーボード ショートカットについては [、Exchange Online の Exchange 管理センターのキーボード ショートカットを参照してください](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。

> [!TIP]
> 問題がある場合は、 Exchange のフォーラムで質問してください。 [Exchange Online Protection フォーラム](https://go.microsoft.com/fwlink/p/?linkId=285351)にアクセスします。

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a>Exchange 管理センターを使用してメール ユーザーを管理する

### <a name="use-the-eac-to-create-mail-users"></a>EAC を使用してメール ユーザーを作成する

1. EAC で、受信者の連絡先に **移動** \> **します。**

2. 新規作成 **アイコンを** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。 表示される **[新しいメール ユーザー** ] ページで、以下の設定を構成します。 必須のマークが付いいい <sup>\*</sup> いの設定は、必須です。

   - **名**

   - **イニシャ**ル : 人物のミドル ネームのイニシャル。

   - **姓**

   - <sup>\*</sup>**表示名**: 既定では、このボックスには [名]、[イニシャル **]、[姓]****ボックス**の値**が表示**されます。 この値をその値の入れ、変更を行う。 値は一意で、最大で 64 文字です。

   - <sup>\*</sup>**エイリア**ス: ユーザーに対しては、最大 64 文字で一意のエイリアスを入力します

   - **[外部の電子メール**アドレス]: ユーザーの電子メール アドレスを入力します。 ドメインはクラウドベース組織の外部ドメインである必要があります。

   - <sup>\*</sup>**[ユーザー ID]:** ユーザーがサービスにサインインするために使用するアカウントを入力します。 ユーザー ID は、アットマーク (@) の左側のユーザー名と右側のドメインで構成されます。

   - <sup>\*</sup>**[New password]** (新 <sup>\*</sup> **しいパスワード) とパスワード**の確認: アカウントのパスワードを入力し、再入力します。 パスワードが組織のパスワードの長さ、複雑さ、および履歴に関する要件に準拠していることを確認してください。

3. 完了したら、 **[保存]** をクリックしてメール ユーザーを作成します。

### <a name="use-the-eac-to-modify-mail-users"></a>EAC を使用してメール ユーザーを変更する

1. EAC で、[受信者の連絡先] **に移動** \> **します**。

2. 変更するメール ユーザーを選択し、[編集] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。

3. 表示されるメール ユーザーのプロパティ ページで、次のいずれかのタブをクリックして、プロパティを表示または変更します。

   完了したら、**[保存]** をクリックします。

#### <a name="general"></a>全般

[全般 **]** タブを使用して、メール ユーザーに関する基本情報を表示または変更します。

- **名**

- **頭文字**

- **姓**

- **表示名**: この名前は組織のアドレス帳、電子メールの "送信先行" 行と "From: /外部アドレス" 行、および EAC の連絡先の一覧に表示されます。 この名前は、表示名の前または後に空のスペースを含めることはできません。

- **[ユーザー ID]:** Microsoft 365 でのユーザーのアカウントです。 ここで、この値は変更できません。

#### <a name="contact-information"></a>連絡先情報

[連絡先 **情報] タブ** を使用して、ユーザーの連絡先情報を表示または変更します。 このページの情報がアドレス帳に表示されます。

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

[組織 **]** タブを使用すると、組織内のユーザーの役割に関する詳細情報を記録できます。

- **役職**
- **部署**
- **Company**

### <a name="use-the-eac-to-remove-mail-users"></a>EAC を使用してメール ユーザーを削除する

1. EAC で、[受信者の連絡先] **に移動** \> **します**。

2. 削除するメール ユーザーを選び、[削除] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。

## <a name="use-powershell-to-manage-mail-users"></a>PowerShell を使用してメール ユーザーを管理する

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a>スタンドアロン EOP PowerShell を使用してメール ユーザーを表示する

スタンドアロン EOP PowerShell 内のすべてのメール ユーザーの要約リストを返すには、次のコマンドを実行します。

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

特定のメール ユーザーに関する詳細情報を表示するには、メール \<MailUserIdentity\> ユーザーの名前、エイリアス、またはアカウント名に置き換え、次のコマンドを実行します。

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

構文およびパラメーターの詳細については[、「Get-Recipient」と「Get-User」](https://docs.microsoft.com/powershell/module/exchange/get-recipient)[を参照してください](https://docs.microsoft.com/powershell/module/exchange/get-user)。

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a>スタンドアロン EOP PowerShell を使用してメール ユーザーを作成する

スタンドアロン EOP PowerShell でメール ユーザーを作成するには、次の構文を使用します。

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

**注**:

- _Name パラメーターは_必須で、最大長は 64 文字で、一意である必要があります。 DisplayName パラメーターを使用し_なけら__、Name パラメーターの値_が表示名として使用されます。
- _Alias_パラメーターを使用しない場合は _、MicrosoftOnlineServicesID パラメーターの左側_がエイリアスに使用されます。
- ExternalEmailAddress パラメーターを使用 _しない場合は_ 、 _外部電子メール アドレスに MicrosoftOnlineServicesID_ の値が使用されます。

この例では、次の設定でメール ユーザーを作成します。

- 名前は JeffreyZeng で、表示名は Jeffrey Zeng です。
- 名は Jeffrey で、姓は Zeng です。
- エイリアスは jeffreyz です。
- 外部の電子メール アドレスは jzeng@tailspintoys.com です。
- アカウント名は次jeffreyz@contoso.onmicrosoft.com。
- パスワードは Pa$$word1 です。

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

構文およびパラメーターの詳細については [、「New-EOPMailUser」を参照してください](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser)。

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a>スタンドアロン EOP PowerShell を使用してメール ユーザーを変更する

スタンドアロン EOP PowerShell で既存のメール ユーザーを変更するには、次の構文を使用します。

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

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a>スタンドアロン EOP PowerShell を使用してメール ユーザーを削除する

スタンドアロン EOP PowerShell 内のメール ユーザーを削除するには、メール \<MailUserIdentity\> ユーザーの名前、エイリアス、またはアカウント名に置き換え、次のコマンドを実行します。

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

この例では、Jeffrey Zeng のメール ユーザーを削除します。

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

構文およびパラメーターの詳細については [、「Remove-EOPMailUser」を参照してください](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser)。

## <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

スタンドアロン EOP でメール ユーザーの作成、変更、または削除が正常に行化されたことを確認するには、次のいずれかの手順を使用します。

- EAC で、[受信者の連絡先] **に移動** \> **します**。 メール ユーザーが一覧に表示されている (または一覧に表示されていない) ことを確認します。 メール ユーザーを選択して詳細ウィンドウに情報を表示するか、設定を **表示するには [** ![ 編集] アイコン ](../../media/ITPro-EAC-AddIcon.png) をクリックします。

- スタンドアロン EOP PowerShell で、次のコマンドを実行して、メール ユーザーが一覧に表示されている (または一覧にない) ことを確認します。

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- メール \<MailUserIdentity\> ユーザーの名前、エイリアス、またはアカウント名に置き換え、次のコマンドを実行して設定を確認します。

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a>ディレクトリ同期を使用してメール ユーザーを管理する

スタンドアロン EOP では、オンプレミスの Active Directory を使用しているお客様はディレクトリ同期を利用できます。 アカウントのコピーがクラウドに格納される Azure Active Directory (Azure AD) にこれらのアカウントを同期できます。 既存のユーザー アカウントを Azure Active Directory に同期するときには、Exchange**Recipients**管理センター (EAC) の受信者ウィンドウまたはスタンドアロン EOP PowerShell で該当するユーザーを表示できます。

**注**:

- ディレクトリ同期を使って受信者を管理する場合でも、Microsoft 365 管理センター でユーザーの追加と管理は可能ですが、これらのユーザーは社内 Active Directory を使う同期の設定が行なされません。 これは、ディレクトリ同期では社内 Active Directory からクラウドへの受信者の同期だけが実行されるためです。

- 次の機能によるディレクトリ同期の使用をお勧めします。

  - **Outlook の差出人セーフ リスト**と受信拒否リスト: サービスに同期すると、これらのリストはサービスのスパム フィルターより優先されます。 これにより、ユーザーは個々の差出人とドメイン エントリを使って、独自の信頼できる差出人のリストと受信拒否リストを管理できます。 詳細については、「[Exchange Online のメールボックスの迷惑メール設定を構成する](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes)」を参照してください。

  - **ディレクトリ ベースのエッジ ブロック (DBEB):** DBEB の詳細については、「ディレクトリ [ベースのエッジ ブロックを使用して無効な受信者に送信されたメッセージを拒否する」を参照してください](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)。

  - **検疫へのエンド ユーザー アクセス**: 検疫済みメッセージにアクセスするには、受信者はサービスに有効なユーザー ID とパスワードを持っていなけれなけれなけれないでください。 検疫の詳細については、「ユーザーが検 [疫済みメッセージを検索して解放する」を参照してください](https://docs.microsoft.com/microsoft-365/security/office-365-security/find-and-release-quarantined-messages-as-a-user)。

  - **メール フロー ルール (トランスポート ルールとも呼ばれる):** ディレクトリ同期を使用すると、既存の Active Directory のユーザーとグループが自動的にクラウドにアップロードされ、サービスに手動で追加しなくても特定のユーザーやグループを対象とするメール フロー ルールを作成できます。 動的配布 [グループをディレクトリ](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) 同期によって同期することはできません。

Azure Active Directory とのハイブリッド ID についての説明に説明されているように、必要なアクセス [許可を取得し、ディレクトリ同期を準備します](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity)。

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a>Azure Active Directory Connect (AAD Connect) とディレクトリを同期する

1. Azure の同期の詳細に説明されている [ようにAD、同期の理解とカスタマイズ](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)。

2. Azure AD Connect の前提条件に関する説明に基づいて AAD Connect を実行するオンプレミス [のコンピューターをインストールしてADします](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)。

3. [Azure の Connect で使用するインストールの種類ADします](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation)。

   - [Express](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [Custom](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [パススルー認証](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> Azure Active Directory 同期ツール構成ウィザードを終了すると、Active Directory フォレストに **MSOL_AD_SYNC** アカウントが作成されます。このアカウントは、社内 Active Directory 情報の読み取りと同期に使われます。ディレクトリ同期が正しく行われるように、ローカル ディレクトリ同期サーバー上の TCP 443 が開いていることを確認してください。

同期を構成した後は、AAD Connect が正しく同期することを確認してください。 EAC で、 **[受信者]** \> **[連絡先]** に移動し、ユーザーの一覧が社内環境から同期されていることを確認します。
