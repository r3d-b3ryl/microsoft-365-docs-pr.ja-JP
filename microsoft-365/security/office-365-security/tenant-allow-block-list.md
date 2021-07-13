---
title: テナント許可/ブロック一覧で許可とブロックを管理する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 管理者は、セキュリティ ポータルのテナント許可/ブロック一覧で許可とブロックを構成する方法について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dbd4694a7442b3898d24304dc78fc95c28c9a905
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394955"
---
# <a name="manage-the-tenant-allowblock-list"></a>テナントの許可/禁止リストの URL を管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> この記事で説明する機能はプレビューで、変更される可能性があります。一部の組織では利用できません。  この記事で説明するスプーフィング機能が組織に存在しない場合は [、「EOP](walkthrough-spoof-intelligence-insight.md)のスプーフィング インテリジェンス ポリシーとスプーフィング インテリジェンスインサイトを使用してスプーフィング送信者を管理する」で、以前のスプーフィング管理エクスペリエンスを参照してください。
>
> 現時点 **では、テナント** 許可/ブロック一覧で許可された URL またはファイル アイテムを構成できません。

Microsoft 365 Exchange Online またはスタンドアロン Exchange Online Protection (EOP) 組織に Exchange Online メールボックスがない組織では、EOP フィルターの評決に同意しない可能性があります。 たとえば、メッセージが正しい (誤検知) とマークされている場合や、悪いメッセージが許可される場合があります (偽陰性)。

ポータルのテナント許可/ブロックリストMicrosoft 365 Defender、フィルター処理の評決を手動で上書Microsoft 365できます。 テナント許可/ブロック一覧は、受信メッセージのメール フロー (組織内メッセージには適用されません) およびユーザーのクリック時に使用されます。 次の種類のオーバーライドを指定できます。

- ブロックする URL。
- ブロックするファイル。
- 許可またはブロックするスプーフィングされた送信者。 スプーフィング インテリジェンスインサイトで許可またはブロックの[](learn-about-spoof-intelligence.md)評決を上書きすると、スプーフィングされた送信者は、テナント許可/ブロック一覧の [スプーフィング] タブにのみ表示される手動の許可またはブロックエントリになります。 スプーフィング インテリジェンスによって検出される前に、スプーフィングされた送信者のエントリを手動で作成またはブロックすることもできます。

この記事では、Microsoft 365 Defender ポータルまたは PowerShell (Exchange Online のメールボックスを持つ Microsoft 365 組織の Exchange Online PowerShell、Exchange Online メールボックスのない組織のスタンドアロン EOP PowerShell) でエントリを構成する方法について説明します。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://security.microsoft.com/> で Microsoft 365 Defender ポータルを開きます。 [テナントの許可/ブロックリスト **] ページに直接移動するには** 、 を使用します <https://security.microsoft.com/tenantAllowBlockList> 。

- ファイルを指定するには、ファイルの SHA256 ハッシュ値を使用します。 ファイルの SHA256 ハッシュ値をWindowsコマンド プロンプトで次のコマンドを実行します。

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  値の例は、 です `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` 。 知覚ハッシュ (pHash) の値はサポートされていません。

- 使用可能な URL 値については、この記事の後半の「 [テナント許可/](#url-syntax-for-the-tenant-allowblock-list) ブロック一覧」セクションの URL 構文で説明します。

- テナント許可/ブロック一覧では、URL に対して最大 500 エントリ、ファイル ハッシュのエントリを 500 エントリまで使用できます。

- 各エントリの最大文字数は次の値です。
  - ファイル ハッシュ = 64
  - URL = 250

- エントリは 30 分以内にアクティブである必要があります。

- 既定では、テナント許可/ブロック一覧のエントリは 30 日後に期限切れになります。 日付を指定するか、有効期限が切れることはありません。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- この記事の手順を実行する際には、あらかじめExchange Online でアクセス許可を割り当てる必要があります。
  - **URL とファイル**:
    - テナント許可/ブロック一覧の値を追加および削除するには、組織の管理またはセキュリティ管理者の役割グループのメンバー **である** 必要があります。
    - テナント許可/ブロック一覧への読み取り専用アクセスでは、グローバル リーダーまたはセキュリティリーダーの役割グループの **メンバーである** 必要があります。
  - **スプーフィン** グ: 次のいずれかの組み合わせ。
    - **組織の管理**
    - **セキュリティ管理者**<u>と</u>**表示のみ構成または****表示のみ可能な組織の管理**。

  詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。

  > [!NOTE]
  >
  > - Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。
  >
  > - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

## <a name="use-the-microsoft-365-defender-portal-to-create-block-url-entries-in-the-tenant-allowblock-list"></a>テナント許可/Microsoft 365 Defenderリストにブロック URL エントリを作成するには、ポータルを使用します。

1. このポータルMicrosoft 365 Defender、[ポリシー] & **[** 脅威ポリシー ルール] セクションの [テナントの許可/ブロックリスト \>  \>  \> **] に移動します**。

2. [テナントの **許可/ブロック一覧** ] ページで **、[URL]** タブが選択されているのを確認し、[ブロック] アイコン [ブロック] ![ を ](../../media/m365-cc-sc-create-icon.png) **クリックします**。

3. 表示される **[URL のブロック]** フライアウトで、次の設定を構成します。
   - **ワイルドカードを含む URL を追加する**: 1 行に 1 つの URL を入力し、最大 20 を入力します。 URL エントリの構文の詳細については、この記事の後半の「テナント許可/ブロック一覧」セクションの [URL](#url-syntax-for-the-tenant-allowblock-list) 構文を参照してください。
   - **有効期限が切れる** ことはありません: 次のいずれかの手順を実行します。
     - 設定がオフ (トグルオフ) になっていることを確認し、[削除] ボックスを使用してエントリの有効期限 ![ ](../../media/scc-toggle-off.png) を指定します。 

       または

     - 切り替えボタンを右に移動して、有効期限が切れなきエントリを構成します。 ![オンに切り替え](../../media/scc-toggle-on.png).
   - **省略可能な** メモ: エントリの説明テキストを入力します。

4. 完了したら、**[追加]** をクリックします。

## <a name="use-the-microsoft-365-defender-portal-to-create-block-file-entries-in-the-tenant-allowblock-list"></a>テナント許可/Microsoft 365 Defenderリストにブロック ファイル エントリを作成するには、このポータルを使用します。

1. このポータルMicrosoft 365 Defender、[ポリシー] & **[** 脅威ポリシー ルール] セクションの [テナントの許可/ブロックリスト \>  \>  \> **] に移動します**。

2. [テナントの **許可/ブロック一覧**] ページで、[ファイル] タブを選択し、[ブロック] アイコン [ブロック] ![ を ](../../media/m365-cc-sc-create-icon.png) **クリックします**。

3. 表示される **[ファイルのブロック** ] フライアウトで、次の設定を構成します。
   - **ファイル ハッシュの追加**: 1 行に 1 つの SHA256 ハッシュ値を入力し、最大 20 を入力します。
   - **有効期限が切れる** ことはありません: 次のいずれかの手順を実行します。
     - 設定がオフ (トグルオフ) になっていることを確認し、[削除] ボックスを使用してエントリの有効期限 ![ ](../../media/scc-toggle-off.png) を指定します。 

     または

     - 切り替えボタンを右に移動して、有効期限が切れなきエントリを構成します。 ![オンに切り替え](../../media/scc-toggle-on.png).
   - **省略可能な** メモ: エントリの説明テキストを入力します。

4. 完了したら、**[追加]** をクリックします。

## <a name="use-the-microsoft-365-defender-portal-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>テナント許可Microsoft 365 Defenderリストでスプーフィングされた送信者エントリを作成またはブロックするには、Microsoft 365 Defender ポータルを使用します。

**注意**:

- スプー _フィング_ されたユーザーと、ドメイン ペアで定義されている送信インフラストラクチャの組み合わせだけが、スプーフィングを許可またはブロックされます。
- ドメイン ペアの許可エントリまたはブロック エントリを構成すると、そのドメイン ペアからのメッセージはスプーフィング インテリジェンスインサイトに表示されなくなりました。
- スプーフィングされた送信者のエントリは有効期限が切れることはありません。

1. このポータルMicrosoft 365 Defender、[ポリシー] & **[** 脅威ポリシー ルール] セクションの [テナントの許可/ブロックリスト \>  \>  \> **] に移動します**。

2. [テナントの **許可/ブロックリスト] ページで** 、[スプーフィング] タブ **を選択** し、[ブロック] アイコン ![ [追加] を ](../../media/m365-cc-sc-create-icon.png) **クリックします**。

3. 表示される **[新しいドメイン ペアの追加** ] フライアウトで、次の設定を構成します。
   - **ワイルドカードを使用して新しいドメイン ペア** を追加する: 1 行に 1 つのドメイン ペアを入力し、最大 20 まで入力します。 スプーフィングされた送信者エントリの構文の詳細については、この記事の後半の「テナント許可 [/](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) ブロックリスト」セクションの「スプーフィングされた送信者エントリのドメインペア構文」を参照してください。
   - **スプーフィング** の種類: 次のいずれかの値を選択します。
     - **内部**: スプーフィングされた送信者は、組織 (受け入れドメイン) に属する [ドメイン内にいます](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。
     - **外部**: スプーフィングされた送信者が外部ドメイン内にある。
   - **アクション**: [許可] **または [ブロック]** **を選択します**。

4. 完了したら、**[追加]** をクリックします。

## <a name="use-the-microsoft-365-defender-portal-to-view-entries-in-the-tenant-allowblock-list"></a>テナント許可/Microsoft 365 Defenderリストのエントリを表示するには、ポータルを使用します。

1. このポータルMicrosoft 365 Defender、[ポリシー] & **[** 脅威ポリシー ルール] セクションの [テナントの許可/ブロックリスト \>  \>  \> **] に移動します**。

2. 必要なタブを選択します。 使用可能な列は、選択したタブによって異なる。

   - **URL**:
     - **値**: URL。
     - **Action**: 値 **Block**.
     - **最終更新日時**
     - **Remove on**
     - **注**
   - **Files**
     - **値**: ファイル ハッシュ。
     - **Action**: 値 **Block**.
     - **最終更新日時**
     - **Remove on**
     - **注**
   - 「**スプーフィング**」
     - **スプーフィングされたユーザー**
     - **インフラストラクチャの送信**
     - **スプーフィングの** 種類 : **値 Internal または** **External** です。
     - **Action**: 値 Block **or** **Allow**.

   列見出しをクリックすると、昇順または降順で並べ替えます。

   [グループ化] **をクリック** すると、結果をグループ化できます。 使用可能な値は、選択したタブによって異なる。

   - **URL :** アクションで結果をグループ化 **できます**。
   - **ファイル**: アクションで結果をグループ **化できます**。
   - **スプーフィン** グ : アクションまたはスプーフィングの種類 **で結果** を **グループ化できます**。

   [ **検索]** をクリックし、値のすべてまたは一部を入力し、Enter キーを押して特定の値を検索します。 完了したら、[検索のクリア] アイコン [検索のクリア] ![ ](../../media/m365-cc-sc-close-icon.png) **をクリックします**。

   [フィルター **] をクリック** して結果をフィルター処理します。 表示されるフィルター フライアウト **で** 使用できる値は、選択したタブによって異なる。

   - **URL**
     - **Action**
     - **有効期限が切れることはありません**
     - **最終更新日**
     - **Remove on**
   - **Files**
     - **Action**
     - **有効期限が切れることはありません**
     - **最終更新日時**
     - **Remove on**
   - 「**スプーフィング**」
     - **Action**
     - **スプーフィングの種類**

   完了したら、[適用] を **クリックします**。 既存のフィルターをクリアするには、[**フィルター**] をクリックし、表示される [フィルター] フライアウトで 、[フィルターのクリア]**をクリックします**。

## <a name="use-the-microsoft-365-defender-portal-to-modify-entries-in-the-tenant-allowblock-list"></a>テナント許可/Microsoft 365 Defenderリストのエントリを変更するには、ポータルを使用します。

1. このポータルMicrosoft 365 Defender、[ポリシー] & **[** 脅威ポリシー ルール] セクションの [テナントの許可/ブロックリスト \>  \>  \> **] に移動します**。

2. 変更するエントリの種類を含むタブを選択します。
   - **URL**
   - **Files**
   - 「**スプーフィング**」

3. 変更するエントリを選択し、[編集] アイコン [編集] ![ を ](../../media/m365-cc-sc-edit-icon.png) **クリックします**。 表示されるフライアウトで変更できる値は、前の手順で選択したタブによって異なっています。
   - **URL**
     - **有効期限や有効期限** はありません。
     - **省略可能なメモ**
   - **Files**
     - **有効期限や有効期限** はありません。
     - **省略可能なメモ**
   - 「**スプーフィング**」
     - **アクション**: 値を [許可] または [ブロック **] に****変更できます**。
4. 完了したら、**[保存]** をクリックします。

## <a name="use-the-microsoft-365-defender-portal-to-remove-entries-from-the-tenant-allowblock-list"></a>テナント許可/Microsoft 365 Defenderリストからエントリを削除するには、ポータルポータルを使用します。

1. このポータルMicrosoft 365 Defender、[ポリシー] & **[** 脅威ポリシー ルール] セクションの [テナントの許可/ブロックリスト \>  \>  \> **] に移動します**。

2. 削除するエントリの種類を含むタブを選択します。
   - **URL**
   - **Files**
   - 「**スプーフィング**」

3. 削除するエントリを選択し、[削除] アイコン [削除] ![ を ](../../media/m365-cc-sc-delete-icon.png) **クリックします**。

4. 表示される警告ダイアログで、[削除] を **クリックします**。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>PowerShell Exchange Onlineスタンドアロン EOP PowerShell を使用してテナント許可/ブロック一覧を構成する

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a>PowerShell を使用して、テナントの許可/ブロックリストにブロック ファイルまたは URL エントリを追加する

テナント許可/ブロック一覧にブロック ファイルまたは URL エントリを追加するには、次の構文を使用します。

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

次の使用例は、有効期限が切れることはありません指定したファイルのブロック ファイル エントリを追加します。

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

次の使用例は、contoso.com およびすべてのサブドメイン (contoso.com、www.contoso.com、および xyz.abc.contoso.com) のブロック URL エントリを追加します。 ExpirationDate パラメーターまたは NoExpiration パラメーターを使用しないので、エントリは 30 日後に期限切れになります。

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

構文とパラメーターの詳細については [、「New-TenantAllowBlockListItems」を参照してください](/powershell/module/exchange/new-tenantallowblocklistitems)。

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a>PowerShell を使用して、スプーフィングされた送信者エントリをテナント許可/ブロックリストに追加またはブロックする

テナント許可/ブロック一覧にスプーフィングされた送信者エントリを追加するには、次の構文を使用します。

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

構文とパラメーターの詳細については [、「New-TenantAllowBlockListSpoofItems」を参照してください](/powershell/module/exchange/new-tenantallowblocklistspoofitems)。

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a>PowerShell を使用して、テナント許可/ブロック一覧のブロック ファイルまたは URL エントリを表示する

テナント許可/ブロック一覧でブロック ファイルまたは URL エントリを表示するには、次の構文を使用します。

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

次の使用例は、指定したファイル ハッシュ値の情報を返します。

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

この例では、ブロックされているすべての URL を返します。

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

構文とパラメーターの詳細については [、「Get-TenantAllowBlockListItems」を参照してください](/powershell/module/exchange/get-tenantallowblocklistitems)。

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>PowerShell を使用して、テナント許可/ブロック一覧でスプーフィングされた送信者エントリを表示またはブロックする

テナント許可/ブロック一覧でスプーフィングされた送信者エントリを表示するには、次の構文を使用します。

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

この例では、テナント許可/ブロック一覧のすべてのスプーフィングされた送信者エントリを返します。

```powershell
Get-TenantAllowBlockListSpoofItems
```

次の使用例は、内部のスプーフィングされた送信者エントリをすべて返します。

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

次の使用例は、外部のすべてのスプーフィングされた送信者エントリを返します。

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

構文とパラメーターの詳細については [、「Get-TenantAllowBlockListSpoofItems」を参照してください](/powershell/module/exchange/get-tenantallowblocklistspoofitems)。

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a>PowerShell を使用して、テナント許可/ブロック一覧のブロック ファイルと URL エントリを変更する

テナント許可/ブロック一覧のブロック ファイルと URL エントリを変更するには、次の構文を使用します。

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

次の使用例は、指定したブロック URL エントリの有効期限を変更します。

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

構文とパラメーターの詳細については [、「Set-TenantAllowBlockListItems」を参照してください](/powershell/module/exchange/set-tenantallowblocklistitems)。

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>PowerShell を使用して、テナント許可/ブロック一覧のスプーフィングされた送信者エントリを変更またはブロックする

テナント許可/ブロック一覧でスプーフィングされた送信者エントリの許可またはブロックを変更するには、次の構文を使用します。

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

次の使用例は、スプーフィングされた送信者エントリを許可からブロックに変更します。

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

構文とパラメーターの詳細については [、「Set-TenantAllowBlockListSpoofItems」を参照してください](/powershell/module/exchange/set-tenantallowblocklistspoofitems)。

### <a name="use-powershell-to-remove-url-or-file-entries-from-the-tenant-allowblock-list"></a>PowerShell を使用してテナント許可/ブロック一覧から URL またはファイル エントリを削除する

テナント許可/ブロック一覧からファイルエントリと URL エントリを削除するには、次の構文を使用します。

```powershell
Remove-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

次の使用例は、指定したブロック URL エントリをテナント許可/ブロック一覧から削除します。

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

構文とパラメーターの詳細については [、「Remove-TenantAllowBlockListItems」を参照してください](/powershell/module/exchange/remove-tenantallowblocklistitems)。

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a>PowerShell を使用して、テナント許可/ブロック一覧からスプーフィングされた送信者エントリの許可またはブロックを削除する

テナント許可/ブロック一覧からスプーフィング送信者エントリを許可またはブロックするには、次の構文を使用します。

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

構文とパラメーターの詳細については [、「Remove-TenantAllowBlockListSpoofItems」を参照してください](/powershell/module/exchange/remove-tenantallowblocklistspoofitems)。

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>テナント許可/ブロック一覧の URL 構文

- IP4v および IPv6 アドレスは許可されますが、TCP/UDP ポートは許可されません。

- ファイル名の拡張子は許可されません (たとえば、test.pdf)。

- Unicode はサポートされていませんが、Punycode はです。

- ホスト名は、次のすべてのステートメントが true の場合に許可されます。
  - ホスト名にはピリオドが含まれる。
  - ピリオドの左側に少なくとも 1 つの文字があります。
  - ピリオドの右側には、少なくとも 2 つの文字があります。

  たとえば、 `t.co` 許可されている、または `.com` `contoso.` 許可されない。

- サブパスは暗黙的ではありません。

  たとえば、 `contoso.com` は含めではありません `contoso.com/a` 。

- ワイルドカード (*) は、次のシナリオで使用できます。

  - サブドメインを指定するには、左のワイルドカードの後にピリオドを指定する必要があります。

    たとえば、 `*.contoso.com` 許可されます。 `*contoso.com` 許可されません。

  - パスを指定するには、右のワイルドカードがスラッシュ (/) に従う必要があります。

    たとえば、 `contoso.com/*` 許可されている、または `contoso.com*` `contoso.com/ab*` 許可されない。

  - すべてのサブパスは、適切なワイルドカードによって暗示されるものではありません。

    たとえば、 `contoso.com/*` は含めではありません `contoso.com/a` 。

  - `*.com*` は無効です (解決可能なドメインではなく、右のワイルドカードはスラッシュに従います)。

  - IP アドレスではワイルドカードは使用できません。

- チルダ (~) 文字は、次のシナリオで使用できます。

  - 左チルダは、ドメインとすべてのサブドメインを意味します。

    たとえば `~contoso.com` 、includes `contoso.com` と `*.contoso.com` .

- URL エントリは、すべてのプロトコルに適用されるので、プロトコルを含む URL エントリ (たとえば `http://` `https://` `ftp://` 、) は失敗します。

- ユーザー名またはパスワードはサポートされていないか、必須ではありません。

- 引用符 (' または ") は無効な文字です。

- URL には、可能な限りすべてのリダイレクトが含まれる必要があります。

### <a name="url-entry-scenarios"></a>URL エントリのシナリオ

有効な URL エントリとその結果については、次のセクションで説明します。

#### <a name="scenario-no-wildcards"></a>シナリオ: ワイルドカードなし

**エントリ**: `contoso.com`

- **一致を許可** する : contoso.com

- **[一致しない] を許可します**。

  - abc-contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **ブロック一致**:

  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **ブロックが一致しない**: abc-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>シナリオ: 左ワイルドカード (サブドメイン)

**エントリ**: `*.contoso.com`

- **一致とブロック** の **一致を許可する**:

  - www.contoso.com
  - xyz.abc.contoso.com

- **[一致しない] と** [ **ブロックが一致しない] を許可します**。

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-at-top-of-path"></a>シナリオ: パスの上部にある右のワイルドカード

**エントリ**: `contoso.com/a/*`

- **一致とブロック** の **一致を許可する**:

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso.com/a/?q=joe@t.com

- **[一致しない] と** [ **ブロックが一致しない] を許可します**。

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

#### <a name="scenario-left-tilde"></a>シナリオ: 左チルダ

**エントリ**: `~contoso.com`

- **一致とブロック** の **一致を許可する**:

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **[一致しない] と** [ **ブロックが一致しない] を許可します**。

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>シナリオ: 右のワイルドカード サフィックス

**エントリ**: `contoso.com/*`

- **一致とブロック** の **一致を許可する**:

  - contoso.com/?q=whatever@fabrikam.com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **[一致しない] と** **[ブロックが一致しない**] : contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>シナリオ: 左ワイルドカード サブドメインと右のワイルドカード サフィックス

**エントリ**: `*.contoso.com/*`

- **一致とブロック** の **一致を許可する**:

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **[一致しない] と** **[ブロックが一致しない**] : contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>シナリオ: 左右のチルダ

**エントリ**: `~contoso.com~`

- **一致とブロック** の **一致を許可する**:

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- **[一致しない] と** [ **ブロックが一致しない] を許可します**。

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>シナリオ: IP アドレス

**エントリ**: `1.2.3.4`

- **一致と****ブロックの一** 致を許可する : 1.2.3.4

- **[一致しない] と** [ **ブロックが一致しない] を許可します**。

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>適切なワイルドカードを持つ IP アドレス

**エントリ**: `1.2.3.4/*`

- **一致とブロック** の **一致を許可する**:

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>無効なエントリの例

次のエントリが無効です。

- **ドメイン値が見つからないか無効です**。

  - contoso
  - \*.contoso.\*
  - \*.com
  - \*.pdf

- **テキストまたはスペース文字なしのワイルドカード**:

  - \*contoso.com
  - contoso.com\*
  - \*1.2.3.4
  - 1.2.3.4\*
  - contoso.com/a\*
  - contoso.com/ab\*

- **ポートを含む IP アドレス**:

  - contoso.com:443
  - abc.contoso.com:25

- **説明的でないワイルドカード**:

  - \*
  - \*.\*

- **中央のワイルドカード**:

  - conto \* so.com
  - conto~so.com

- **2 つのワイルドカード**

  - contoso.com/\*\*
  - contoso.com/\*/\*

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>テナント許可/ブロック一覧のスプーフィングされた送信者エントリのドメインペア構文

テナント許可/ブロック一覧のスプーフィング送信者のドメイン ペアは、次の構文を使用します `<Spoofed user>, <Sending infrastructure>` 。

- **スプーフィングされた** ユーザー: この値には、メール クライアントの [From] ボックスに表示されるスプーフィングされたユーザーの電子メール アドレスが含まれる。 このアドレスは、アドレスとも呼 `5322.From` ばれる。 有効な値は次のとおりです。
  - 個々の電子メール アドレス (たとえば、chris@contoso.com)。
  - 電子メール ドメイン (たとえば、contoso.com)。
  - ワイルドカード文字 (たとえば \* )。

- **送信インフラストラクチャ**: この値は、スプーフィングされたユーザーからのメッセージのソースを示します。 有効な値は次のとおりです。
  - 送信元電子メール サーバーの IP アドレスの逆引き DNS 参照 (PTR レコード) で見つかったドメイン (たとえば、fabrikam.com)。
  - 送信元 IP アドレスに PTR レコードがない場合、送信インフラストラクチャは \<source IP\> /24 として識別されます (たとえば、192.168.100.100/24 など)。

スプーフィングされた送信者を識別するための有効なドメイン ペアの例を次に示します。

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

スプーフィングされた送信者エントリの最大数は 1000 です。

ドメイン ペアを追加すると、スプーフィングされたユーザーと送信インフラストラクチャの組み合わせだけが許可またはブロックされます。 スプーフィングされたユーザーからのメールを任意のソースから許可したり、スプーフィングされたユーザーに対して送信インフラストラクチャ ソースからのメールを許可したりはしない。 

たとえば、次のドメインペアの許可エントリを追加します。

- **ドメイン**: gmail.com
- **インフラストラクチャ**: tms.mx.com

スプーフィングを許可できるのは、そのドメインと送信インフラストラクチャ のペアからのメッセージのみです。 スプーフィングを試みる gmail.com 送信者は許可されません。 ユーザーから発信される他のドメインの送信者からの tms.mx.com スプーフィング インテリジェンスによってチェックされます。
