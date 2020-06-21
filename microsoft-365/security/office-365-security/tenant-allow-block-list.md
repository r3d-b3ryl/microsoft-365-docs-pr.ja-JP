---
title: 許可または禁止する Url とファイルをテナントの許可/ブロックリストで管理する
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
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: 管理者は、セキュリティ & コンプライアンスセンターのテナントの許可/ブロックリストで URL とファイルエントリを構成する方法について説明します。
ms.openlocfilehash: 742a44c7ed63c8a3037e2ada295c94f89afa9c93
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726815"
---
# <a name="manage-urls-and-files-in-the-tenant-allowblock-list"></a>テナントの許可/ブロックリストで Url とファイルを管理する

> [!NOTE]
> このトピックで説明する機能はプレビュー段階にあり、変更される可能性があり、組織によっては利用できません。

Exchange online または exchange online メールボックスを使用しない exchange online またはスタンドアロンの Exchange Online Protection (EOP) 組織内にメールボックスを持つ Microsoft 365 組織では、EOP フィルター verdict の使用に同意しない場合があります。 たとえば、良好なメッセージが不良 (誤検知) としてマークされている場合や、無効なメッセージが表示される場合があります (誤検知)。

セキュリティ & コンプライアンスセンターのテナントの許可/禁止リストにより、Microsoft 365 filtering verdicts を手動で上書きすることができます。 テナントの許可/ブロックリストは、メールフローおよびユーザークリック時に使用されます。 テナントの許可/ブロックリストで許可またはブロックする Url とファイルを指定できます。

このトピックでは、セキュリティ & コンプライアンスセンターまたは PowerShell (exchange online にメールボックスがある Microsoft 365 組織の場合は exchange Online PowerShell、exchange online メールボックスを使用しない組織の場合は、スタンドアロン EOP PowerShell) で、テナントの許可/ブロックリストのエントリを構成する方法について説明します。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 [**テナントの許可/ブロックリスト**] ページに直接移動するには、を使用 <https://protection.office.com/tenantAllowBlockList> します。

- ファイルの SHA256 ハッシュ値を使用してファイルを指定します。 Windows でファイルの SHA256 ハッシュ値を検索するには、コマンドプロンプトで次のコマンドを実行します。

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  値の例を次に示し `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` ます。 知覚ハッシュ (pHash) の値は使用できません。

- 使用可能な URL 値については、このトピックで後述する「[テナントの許可/ブロックリスト」セクションの url 構文](#url-syntax-for-the-tenant-allowblock-list)で説明されています。

- テナントの許可/ブロックリストでは、Url に最大500エントリ、ファイルハッシュには500エントリを使用できます。

- エントリは15分以内にアクティブである必要があります。

- 禁止エントリは、許可エントリよりも優先されます。

- 既定では、テナントの許可/ブロックリストのエントリは30日後に期限切れになります。 日付を指定するか、期限切れにならないように設定できます。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「 [Exchange Online Protection の powershell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- このトピックの手順を実行する前に、アクセス許可を割り当てる必要があります。

  - テナントの許可/禁止リストの値を追加および削除するには、次のいずれかの役割グループのメンバーである必要があります。

    - [セキュリティ & コンプライアンスセンター](permissions-in-the-security-and-compliance-center.md)の**組織管理**または**セキュリティ管理者**。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)での**組織の管理**または**検疫の管理**。

  - テナントの許可/禁止リストに対する読み取り専用アクセスの場合は、次のいずれかの役割グループのメンバーである必要があります。

    - [セキュリティ & コンプライアンスセンター](permissions-in-the-security-and-compliance-center.md)の**セキュリティリーダ**。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)での**表示のみの組織の管理**。

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a>セキュリティ & コンプライアンスセンターを使用して、テナントの許可/ブロックリストで URL エントリを作成する

URL エントリの構文の詳細については、このトピックで後述する「[テナントの許可/ブロックリスト」セクションの url 構文](#url-syntax-for-the-tenant-allowblock-list)を参照してください。

1. [セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー**の \> **テナントの許可/ブロックリスト**] に移動します。

2. [**テナントの許可/ブロックリスト**] ページで、[ **url** ] タブが選択されていることを確認し、[**追加**] をクリックします。

3. 表示される [**新しい url の追加**] ポップアップで、次の設定を構成します。

   - **ワイルドカードを使用して url を追加**します。1行に1つの url を入力します。最大値は20です。

   - [**ブロック/許可**]: 指定した Url を**許可**または**ブロック**するかどうかを選択します。

   - **無期限: 次**のいずれかの手順を実行します。

     - 設定がオフ (トグルオフ) になっていることを確認 ![ ](../../media/scc-toggle-off.png) し、 **[有効期限**] ボックスを使用して、エントリの有効期限を指定します。

     または

     - 右にトグルを移動して、期限切れにならないようにエントリを構成します。 ![オンに切り替え](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **オプションのメモ**: エントリの説明テキストを入力します。

4. 完了したら、[**追加**] をクリックします。

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a>セキュリティ & コンプライアンスセンターを使用して、テナントの許可/ブロックリストでファイルエントリを作成する

1. [セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー**の \> **テナントの許可/ブロックリスト**] に移動します。

2. [**テナントの許可/ブロックリスト**] ページで、[**ファイル**] タブを選択し、[**追加**] をクリックします。

3. 表示される [**新しいファイルの追加**] ポップアップで、次の設定を構成します。

   - **ファイルハッシュの追加**: 行ごとに1つの SHA256 ハッシュ値を入力します (最大数は 20)。

   - [**ブロック/許可**]: 指定したファイルを**許可**または**ブロック**するかどうかを選択します。

   - **無期限: 次**のいずれかの手順を実行します。

     - 設定がオフ (トグルオフ) になっていることを確認 ![ ](../../media/scc-toggle-off.png) し、 **[有効期限**] ボックスを使用して、エントリの有効期限を指定します。

     または

     - 右にトグルを移動して、期限切れにならないようにエントリを構成します。 ![オンに切り替え](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **オプションのメモ**: エントリの説明テキストを入力します。

4. 完了したら、[**追加**] をクリックします。

## <a name="use-the-security--compliance-center-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a>セキュリティ & コンプライアンスセンターを使用して、URL およびファイルエントリをテナントの許可/ブロックリストに表示する

1. [セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー**の \> **テナントの許可/ブロックリスト**] に移動します。

2. [ **Url** ] タブまたは [**ファイル**] タブを選択します。

次の列見出しをクリックすると、昇順または降順で並べ替えられます。

- **値**: URL またはファイルハッシュ。
- **アクション**:**ブロック**または**許可**。
- **最終更新日**
- **有効期限**
- **注**

[**グループ化**] をクリックして、エントリを**アクション**(**ブロック**または**許可**) または**なし**とグループ化します。

[**検索**] をクリックし、URL またはファイル値の全体または一部を入力してから、enter キーを押して特定の値を検索します。 完了したら、[検索のクリア検索の**クリア**] をクリックし ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) ます。

[**フィルター**] をクリックします。 表示される**フィルター**のポップアップで、次のいずれかの設定を構成します。

- **アクション**: **Allow**、 **Block** 、または both を選択します。

- **無期限: オフ**(オフ ![ ](../../media/scc-toggle-off.png) ) またはオン ( ![ トグルオン ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) )。

- **最終更新**日時: 開始日 (開始**日)、** 終了日 (**To**)、またはその両方を選択します。

- [**有効期限**]: 開始日 (開始**日)、** 終了日 (**To**)、またはその両方を選択します。

完了したら、[**適用**] をクリックします。

既存のフィルターをクリアするには、[**フィルター**] をクリックし、表示される**フィルター**のポップアップで [**フィルターのクリア**] をクリックします。

## <a name="use-the-security--compliance-center-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a>セキュリティ & コンプライアンスセンターを使用して、テナントの許可/ブロックリスト内の URL とファイルエントリを変更する

URL またはファイルの値自体を変更することはできません。 代わりに、エントリを削除して再作成する必要があります。

1. [セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー**の \> **テナントの許可/ブロックリスト**] に移動します。

2. [ **Url** ] タブまたは [**ファイル**] タブを選択します。

3. 変更するエントリを選択し、[編集アイコンの**編集**] をクリックし ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) ます。

4. 表示されたポップアップで、次の設定を構成します。

   - [**ブロック/許可**]: [**許可**] または [**ブロック**] を選択します。

   - **無期限: 次**のいずれかの手順を実行します。

     - 設定がオフ (トグルオフ) になっていることを確認 ![ ](../../media/scc-toggle-off.png) し、 **[有効期限**] ボックスを使用して、エントリの有効期限を指定します。

     または

     - この設定を右に移動して、期限切れにならないようにエントリを構成します。 ![オンに切り替え](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **オプションのメモ**: エントリの説明テキストを入力します。

5. 完了したら、**[保存]** をクリックします。

## <a name="use-the-security--compliance-center-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a>セキュリティ & コンプライアンスセンターを使用して、URL とファイルのエントリをテナントの許可/禁止リストから削除する

1. [セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー**の \> **テナントの許可/ブロックリスト**] に移動します。

2. [ **Url** ] タブまたは [**ファイル**] タブを選択します。

3. 削除するエントリを選択し、[削除] [削除] アイコン**をクリックし** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) ます。

4. 表示される警告ダイアログで、[**削除**] をクリックします。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>Exchange Online PowerShell またはスタンドアロンの EOP PowerShell を使用して、テナントの許可/ブロックリストを構成する

### <a name="use-powershell-to-add-url-and-file-entries-in-the-tenant-allowblock-list"></a>PowerShell を使用して、テナントの許可/ブロックリストに URL とファイルエントリを追加する

テナントの許可/ブロックリストに URL とファイルエントリを追加するには、次の構文を使用します。

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

この例では、contoso.com およびすべてのサブドメイン (たとえば、contoso.com、www.contoso.com、および xyz.abc.contoso.com) の URL ブロックエントリを追加します。 ExpirationDate パラメーターまたは NoExpiration パラメーターを使用していなかったため、エントリは30日後に有効期限が切れます。

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Action Allow -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

この例では、指定したファイルの有効期限が切れないファイルの許可エントリを追加します。

構文およびパラメーターの詳細については、「 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)」を参照してください。

### <a name="use-powershell-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a>PowerShell を使用して、テナントの許可/ブロックリスト内の URL とファイルエントリを表示する

テナントの許可/ブロックの一覧で URL とファイルエントリを表示するには、次の構文を使用します。

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

この例では、すべてのブロックされた Url を返します。

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

この例では、指定したファイルハッシュ値に関する情報を返します。

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

構文およびパラメーターの詳細については、「 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)」を参照してください。

### <a name="use-powershell-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a>PowerShell を使用して、テナントの許可/ブロックリスト内の URL とファイルエントリを変更する

URL またはファイルの値自体を変更することはできません。 代わりに、エントリを削除して再作成する必要があります。

テナントの許可/ブロックの一覧で URL とファイルエントリを変更するには、次の構文を使用します。

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

次の使用例は、指定された項目の有効期限を変更します。

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

構文およびパラメーターの詳細については、「 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)」を参照してください。

### <a name="use-powershell-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a>PowerShell を使用して、テナントの許可/ブロックリストから URL とファイルエントリを削除する

URL とファイルエントリをテナントの許可/禁止リストから削除するには、次の構文を使用します。

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

この例では、指定した URL エントリをテナントの許可/禁止リストから削除します。

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

構文およびパラメーターの詳細については、「 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)」を参照してください。

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>テナントの許可/ブロックリストの URL 構文

- IP4v および IPv6 アドレスは許可されますが、TCP/UDP ポートは許可されません。

- ファイル名拡張子を使用することはできません (test.pdf など)。

- Unicode はサポートされていませんが、Punycode はです。

- 次のすべてのステートメントが true の場合、ホスト名が許可されます。

  - ホスト名にはピリオドが含まれています。
  - ピリオドの左側には、少なくとも1つの文字があります。
  - ピリオドの右側には、少なくとも2つの文字があります。

  たとえば、は許可されて `t.co` `.com` いるか、許可され `contoso.` ていません。

- サブパスは黙示的ではありません。

  たとえば、にはを `contoso.com` 含めません `contoso.com/a` 。

- 次のシナリオでは、ワイルドカード (*) を使用できます。

  - サブドメインを指定するには、左のワイルドカードの後にピリオドを置く必要があります。

    たとえば、 `*.contoso.com` は許可され `*contoso.com` ていません。許可されていません。

  - 右のワイルドカードは、スラッシュ (/) に続けてパスを指定する必要があります。

    たとえば、は許可されて `contoso.com/*` `contoso.com*` いるか、許可され `contoso.com/ab*` ていません。

  - すべてのサブパスは、右のワイルドカードでは暗黙的には含まれません。

    たとえば、にはを `contoso.com/*` 含めません `contoso.com/a` 。

  - `*.com*`は無効です (解決可能なドメインではなく、右のワイルドカードはスラッシュに従っていません)。

  - IP アドレスにワイルドカードを使用することはできません。

- チルダ (~) 文字は、次のシナリオで使用できます。

  - 左チルダは、1つのドメインとすべてのサブドメインを意味します。

    たとえば `~contoso.com` `contoso.com` 、とを含み `*.contoso.com` ます。

- `http://` `https://` Url エントリはすべてのプロトコルに適用されるため、プロトコル (たとえば、など) を含む url エントリ `ftp://` は失敗します。

- ユーザー名またはパスワードがサポートされていないか、または必要です。

- 引用符 (' または ") は無効な文字です。

- 可能な場合は、URL にすべてのリダイレクトを含める必要があります。

### <a name="url-entry-scenarios"></a>URL エントリのシナリオ

次のセクションでは、有効な URL エントリとその結果について説明します。

#### <a name="scenario-no-wildcards"></a>シナリオ: ワイルドカードがありません

**Entry**:`contoso.com`

- **Match の許可**: contoso.com

- **許可しない**:

  - abc-contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www. .com/q = a@contoso
  
- **ブロック一致**:

  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www. .com/q = a@contoso

- **ブロックが一致しません**: abc-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>シナリオ: 左ワイルドカード (サブドメイン)

**Entry**:`*.contoso.com`

- 一致と**ブロックの一致**を**許可する**:

  - www.contoso.com
  - xyz.abc.contoso.com

- [一致しない] と [**ブロックが一致**し**ません**] を許可します。

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a>シナリオ: パスの上部にあるワイルドカード (右)

**Entry**:`contoso.com/a/*`

- 一致と**ブロックの一致**を**許可する**:

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso .com/a/? q = joe@t

- [一致しない] と [**ブロックが一致**し**ません**] を許可します。

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www. .com/q = a@contoso
  
#### <a name="scenario-left-tilde"></a>シナリオ: 左チルダ

**Entry**:`~contoso.com`

- 一致と**ブロックの一致**を**許可する**:

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- [一致しない] と [**ブロックが一致**し**ません**] を許可します。

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>シナリオ: 右ワイルドカードサフィックス

**Entry**:`contoso.com/*`

- 一致と**ブロックの一致**を**許可する**:

  - contoso .com/? q = whatever@fabrikam
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **Allow not 一致**と**ブロック not 一致**: contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>シナリオ: 左ワイルドカードサブドメインと右ワイルドカードサフィックス

**Entry**:`*.contoso.com/*`

- 一致と**ブロックの一致**を**許可する**:

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **Allow not 一致**と**ブロック not 一致**: contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>シナリオ: 左と右のチルダ

**Entry**:`~contoso.com~`

- 一致と**ブロックの一致**を**許可する**:

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- [一致しない] と [**ブロックが一致**し**ません**] を許可します。

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>シナリオ: IP アドレス

**Entry**:`1.2.3.4`

- Match と**Block match**を**許可する**: 1.2.3.4

- [一致しない] と [**ブロックが一致**し**ません**] を許可します。

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>右ワイルドカードを使用した IP アドレス

**Entry**:`1.2.3.4/*`

- 一致と**ブロックの一致**を**許可する**:

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>無効なエントリの例

次のエントリは無効です。

- **ドメイン値がないか、または無効**です。

  - 拠点
  - \*拠点.\*
  - \*.com
  - \*.pdf

- **文字列の場合はワイルドカード、文字間隔は使用しませ**ん。

  - \*contoso.com
  - contoso.com\*
  - \*1.2.3.4
  - 1.2.3.4\*
  - contoso.com/a\*
  - contoso.com/ab\*

- **ポートを使用した IP アドレス**:

  - contoso.com:443
  - abc.contoso.com:25

- **説明のないワイルドカード**:

  - \*
  - \*.\*

- **中央のワイルドカード**:

  - conto \* so.com
  - ~ so ~ .com

- **2文字のワイルドカード**

  - contoso.com/\*\*
  - contoso.com/\*/\*
