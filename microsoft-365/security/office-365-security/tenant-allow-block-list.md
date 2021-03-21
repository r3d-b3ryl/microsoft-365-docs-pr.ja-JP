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
ms.openlocfilehash: 2f97308bfc3600e4e85f5ac92d951b12d9a50f24
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928534"
---
# <a name="manage-the-tenant-allowblock-list"></a>テナントの許可/禁止リストの URL を管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!NOTE]
>
> この記事で説明する機能はプレビューで、変更される可能性があります。一部の組織では利用できません。
>
> 現時点 **では、テナント** 許可/ブロック一覧で許可アイテムを構成できません。

Exchange Online またはスタンドアロンの Exchange Online Protection (EOP) 組織に Exchange Online メールボックスがない Microsoft 365 組織では、EOP フィルターの評決に同意しない可能性があります。 たとえば、メッセージが正しい (誤検知) とマークされている場合や、悪いメッセージが許可される場合があります (偽陰性)。

セキュリティ コンプライアンス センターのテナント許可/ブロック一覧&、Microsoft 365 フィルターの評決を手動で上書きする方法が提供されます。 テナント許可/ブロック一覧は、メール フロー中およびユーザークリック時に使用されます。 常にブロックする URL またはファイルを指定できます。

この記事では、セキュリティ & コンプライアンス センターまたは PowerShell (Exchange Online のメールボックスを持つ Microsoft 365 組織向け Exchange Online PowerShell、Exchange Online メールボックスのない組織のスタンドアロン EOP PowerShell) のテナント許可/ブロック一覧のエントリを構成する方法について説明します。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 [テナントの許可/ブロック **リスト] ページに直接移動するには** 、 を使用します <https://protection.office.com/tenantAllowBlockList> 。

- ファイルを指定するには、ファイルの SHA256 ハッシュ値を使用します。 Windows でファイルの SHA256 ハッシュ値を検索するには、コマンド プロンプトで次のコマンドを実行します。

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

- この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。
  - テナント許可/ブロック一覧の値を追加および削除するには、組織の管理またはセキュリティ管理者の役割グループのメンバー **である** 必要があります。
  - テナント許可/ブロック一覧への読み取り専用アクセスでは、グローバル リーダーまたはセキュリティリーダーの役割グループの **メンバーである** 必要があります。

  詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。

  > [!NOTE]
  > 
  > - Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。
  > - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a>テナント許可/&リストに URL エントリを作成するには、セキュリティ コンプライアンス センターを使用します。

URL エントリの構文の詳細については、この記事の後半の「テナント許可/ブロック一覧」セクションの [URL](#url-syntax-for-the-tenant-allowblock-list) 構文を参照してください。

1. セキュリティ 管理コンプライアンス センター&、[**脅威管理ポリシー** ] [テナントの許可 \>  \> **/ブロックリスト] に移動します**。

2. [テナントの **許可/ブロック一覧** ] ページで **、[URL]** タブが選択されているのを確認し、[ブロック] を **クリックします。**

3. 表示される **[URL のブロック]** フライアウトで、次の設定を構成します。

   - **ブロックする URL を追加する**: 1 行に 1 つの URL を入力し、最大 20 を入力します。

   - **有効期限が切れる** ことはありません: 次のいずれかの手順を実行します。

     - 設定がオフ (トグルオフ) になっていることを確認し、[有効期限] ボックスを使用してエントリの有効期限 ![ ](../../media/scc-toggle-off.png) を指定します。 

       または

     - 切り替えボタンを右に移動して、有効期限が切れなきエントリを構成します。 ![オンに切り替え](../../media/scc-toggle-on.png).

   - **省略可能な** メモ: エントリの説明テキストを入力します。

4. 完了したら、**[追加]** をクリックします。

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a>テナント許可/&リストにファイル エントリを作成するには、セキュリティ コンプライアンス センターを使用します。

1. セキュリティ 管理コンプライアンス センター&、[**脅威管理ポリシー** ] [テナントの許可 \>  \> **/ブロックリスト] に移動します**。

2. [テナントの **許可/ブロックリスト] ページで** 、[ **ファイル]** タブを選択し、[ブロック] を **クリックします**。

3. 表示される **[ファイルを追加してブロック** する] フライアウトで、次の設定を構成します。

   - **ファイル ハッシュの追加**: 1 行に 1 つの SHA256 ハッシュ値を入力し、最大 20 を入力します。

   - **有効期限が切れる** ことはありません: 次のいずれかの手順を実行します。

     - 設定がオフ (トグルオフ) になっていることを確認し、[有効期限] ボックスを使用してエントリの有効期限 ![ ](../../media/scc-toggle-off.png) を指定します。 

     または

     - 切り替えボタンを右に移動して、有効期限が切れなきエントリを構成します。 ![オンに切り替え](../../media/scc-toggle-on.png).

   - **省略可能な** メモ: エントリの説明テキストを入力します。

4. 完了したら、**[追加]** をクリックします。

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a>テナント許可/&リストのエントリを表示するには、セキュリティ コンプライアンス センターを使用します。

1. セキュリティ 管理コンプライアンス センター&、[**脅威管理ポリシー** ] [テナントの許可 \>  \> **/ブロックリスト] に移動します**。

2. **[URL] タブまたは [** ファイル] タブ **を選択** します。

昇順または降順で並べ替えるには、次の列見出しをクリックします。

- **値**: URL またはファイル ハッシュ。
- **最終更新日**
- **有効期限**
- **注**

[ **検索]** をクリックし、値のすべてまたは一部を入力し、Enter キーを押して特定の値を検索します。 完了したら、[検索のクリア] **アイコン** ![ をクリックします ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 。

[フィルター **] をクリックします**。 表示される **[フィルター** ] フライアウトで、次の設定を構成します。

- **有効期限が切** れることはありません: [オフ] を ![ 選択します。オフ ](../../media/scc-toggle-off.png) またはオンに切り替えます。 ![ ](../../media/scc-toggle-on.png)

- **最終更新日 :** 開始日 ( From **)**、終了日 (**To**) または両方を選択します。

- **有効期限 :** 開始日 **(** From ) 、終了日 (**To**) または両方を選択します。

完了したら、[適用] を **クリックします**。

既存のフィルターをクリアするには、[**フィルター**] をクリックし、表示される [フィルター] フライアウトで 、[フィルターのクリア]**をクリックします**。

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a>テナント許可/&リストのブロック エントリを変更するには、セキュリティ コンプライアンス センターを使用します。

エントリ内の既存のブロックされた URL またはファイル値を変更できない。 これらの値を変更するには、エントリを削除して再作成する必要があります。

1. セキュリティ 管理コンプライアンス センター&、[**脅威管理ポリシー** ] [テナントの許可 \>  \> **/ブロックリスト] に移動します**。

2. **[URL] タブまたは [** ファイル] タブ **を選択** します。

3. 変更するブロック エントリを選択し、[編集] アイコン **を** ![ クリックします ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 。

4. 表示されるフライアウトで、次の設定を構成します。

   - **有効期限が切れる** ことはありません: 次のいずれかの手順を実行します。

     - 設定がオフ (トグルオフ) になっていることを確認し、[有効期限] ボックスを使用してエントリの ![ ](../../media/scc-toggle-off.png) 有効期限を指定します。 

       または

     - 切り替えボタンを右に移動して、有効期限が切れなきエントリを構成します。 ![オンに切り替え](../../media/scc-toggle-on.png).

   - **省略可能なメモ**: エントリの説明テキストを入力します。

5. 完了したら、**[保存]** をクリックします。

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a>テナント許可/&リストからブロック エントリを削除するには、セキュリティ コンプライアンス センターを使用します。

1. セキュリティ 管理コンプライアンス センター&、[**脅威管理ポリシー** ] [テナントの許可 \>  \> **/ブロックリスト] に移動します**。

2. **[URL] タブまたは [** ファイル] タブ **を選択** します。

3. 削除するブロック エントリを選択し、[削除] アイコン **を** ![ クリックします ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 。

4. 表示される警告ダイアログで、[削除] を **クリックします**。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>Exchange Online PowerShell またはスタンドアロン EOP PowerShell を使用してテナントの許可/ブロックリストを構成する

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a>PowerShell を使用してテナント許可/ブロック一覧にブロック エントリを追加する

テナント許可/ブロック一覧にブロック エントリを追加するには、次の構文を使用します。

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

次の使用例は、contoso.com およびすべてのサブドメイン (contoso.com、www.contoso.com、および xyz.abc.contoso.com) のブロック URL エントリを追加します。 ExpirationDate パラメーターまたは NoExpiration パラメーターを使用しないので、エントリは 30 日後に期限切れになります。

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

次の使用例は、有効期限が切れることはありません指定したファイルのブロック ファイル エントリを追加します。

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

構文とパラメーターの詳細については [、「New-TenantAllowBlockListItems」を参照してください](/powershell/module/exchange/new-tenantallowblocklistitems)。

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a>PowerShell を使用してテナント許可/ブロック一覧のエントリを表示する

テナント許可/ブロック一覧のエントリを表示するには、次の構文を使用します。

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

この例では、ブロックされているすべての URL を返します。

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

次の使用例は、指定したファイル ハッシュ値の情報を返します。

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

構文とパラメーターの詳細については [、「Get-TenantAllowBlockListItems」を参照してください](/powershell/module/exchange/get-tenantallowblocklistitems)。

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a>PowerShell を使用してテナント許可/ブロック一覧のブロック エントリを変更する

ブロック エントリ内の既存の URL またはファイル値を変更できない。 これらの値を変更するには、エントリを削除して再作成する必要があります。

テナント許可/ブロック一覧のブロック エントリを変更するには、次の構文を使用します。

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

次の使用例は、指定したブロック エントリの有効期限を変更します。

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

構文とパラメーターの詳細については [、「Set-TenantAllowBlockListItems」を参照してください](/powershell/module/exchange/set-tenantallowblocklistitems)。

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a>PowerShell を使用してテナント許可/ブロック一覧からブロック エントリを削除する

テナント許可/ブロック一覧からブロック エントリを削除するには、次の構文を使用します。

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

次の使用例は、指定したブロック URL エントリをテナント許可/ブロック一覧から削除します。

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

構文とパラメーターの詳細については [、「Remove-TenantAllowBlockListItems」を参照してください](/powershell/module/exchange/remove-tenantallowblocklistitems)。

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