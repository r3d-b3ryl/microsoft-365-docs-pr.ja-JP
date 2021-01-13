---
title: テナントの許可/ブロックリストで許可とブロックを管理する
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
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 管理者は、セキュリティ ポータルのテナントの許可/ブロックリストで許可とブロックを構成する方法について学習できます。
ms.openlocfilehash: c789b09224d00f5bb41ae29d6d2a6efa64d23a8d
ms.sourcegitcommit: 495b66b77d6dbe6d69e5b06b304089e4e476e568
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799715"
---
# <a name="managing-allows-and-blocks-in-the-tenant-allowblock-list"></a>テナントの許可/ブロックリストでの許可とブロックの管理

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> この記事で説明する機能はプレビューであり、変更される可能性があります。また、すべての組織で利用できるではありません。

Exchange Online または Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織にメールボックスがある Microsoft 365 組織では、EOP フィルターの条件に同意しない可能性があります。 たとえば、良いメッセージが悪い (誤検知) とマークされている場合や、悪いメッセージが許可されている (検出誤検知) 場合があります。

セキュリティ/コンプライアンス センターのテナントの許可/ブロックリスト&、Microsoft 365 フィルターの条件を手動で上書きする方法が提供されます。 テナントの許可/ブロックリストは、メール フロー中およびユーザーがクリックした時点で使用されます。 テナントの許可/ブロックリストで許可またはブロックする URL を指定できます。

このトピックでは、セキュリティ & コンプライアンス センターまたは PowerShell (Exchange Online のメールボックスを持つ Microsoft 365 組織向け Exchange Online PowerShell、Exchange Online メールボックスのない組織のスタンドアロン EOP PowerShell) のテナント許可/ブロック一覧のエントリを構成する方法について説明します。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 [テナントの許可/ブロック **リスト] ページに直接移動するには** 、次の値を使用します <https://protection.office.com/tenantAllowBlockList> 。

- 使用可能な URL 値については、この記事で後述する「テナントの許可/ブロックリスト」セクションの [URL](#url-syntax-for-the-tenant-allowblock-list) 構文で説明します。

- テナントの許可/ブロックリストでは、URL に最大 500 エントリを許可します。

- エントリは 15 分以内にアクティブになります。

- 許可エントリよりもブロック エントリが優先されます。

- 既定では、テナントの許可/ブロックリストのエントリは 30 日後に期限切れになります。 日付を指定するか、有効期限が切れない日付に設定できます。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- この記事に記載の手順を行うには、セキュリティ/コンプライアンス センターのアクセス許可が割り当てられている必要があります。
  - テナントの許可/ブロックリストに値を追加および削除するには、組織の管理役割グループまたはセキュリティ管理者役割グループのメンバー **である** 必要があります。
  - テナントの許可/ブロックリストへの読み取り専用アクセスの場合、グローバル閲覧者またはセキュリティ閲覧者の役割グループのメンバー **である必要があります**。

  詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

  **注**:

  - Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、セキュリティ/コンプライアンス センター の必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。 詳細については、「[管理者の役割について](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)」を参照してください。
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a>セキュリティ/コンプライアンス センター&使用して、テナントの許可/ブロックリストに URL エントリを作成する

URL エントリの構文の詳細については、後の「テナントの許可/ブロックリスト」セクションの [URL](#url-syntax-for-the-tenant-allowblock-list) 構文を参照してください。

1. セキュリティ/コンプライアンス センター&、脅威 **管理ポリシー** のテナントの許可 \>  \> **/ブロックリストに移動します**。

2. [テナント **の許可/ブロックリスト** ] ページで **、[URL]** タブが選択されているのを確認し、[追加] をクリック **します。**

3. 表示される **[新しい URL の追加** ] フライアウトで、次の設定を構成します。

   - **ワイルドカードを使用して URL を追加** する : 1 行に 1 つの URL を入力し、最大 20 文字まで入力します。

   - **ブロック/許可**: 指定した URLを許可またはブロック **するかどうかを** 選択します。

   - **有効期限が切れる** ことはありません: 次のいずれかの手順を実行します。

     - 設定がオフ (トグル オフ) になっていることを確認し、[有効期限] ボックスを使用してエントリの有効期限 ![ ](../../media/scc-toggle-off.png) を指定します。 

     または

     - 切り替えは右に移動して、有効期限が切れなさらないエントリを構成します。 ![オンに切り替え](../../media/scc-toggle-on.png).

   - **省略可能な** メモ : エントリの説明テキストを入力します。

4. 完了したら、[追加] をクリック **します**。

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a>セキュリティ/コンプライアンス センター&使用して、テナントの許可/ブロックの一覧のエントリを表示する

1. セキュリティ/コンプライアンス センター&、脅威 **管理ポリシー** のテナントの許可 \>  \> **/ブロックリストに移動します**。

2. **[URL] タブを選択** します。

次の列見出しをクリックして、昇順または降順で並べ替えます。

- **値**
- **Action**: **Block** or **Allow**.
- **最終更新日**
- **有効期限**
- **注**

[**グループ]** をクリックして、**操作 (** ブロックまたは **許可)** または [なし] で **エントリをグループ****化します**。

[ **検索]** をクリックし、値のすべてまたは一部を入力し、Enter キーを押して特定の値を検索します。 完了したら、[検索のクリア] **アイコン** ![ をクリックします ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 。

[フィルター **] をクリックします**。 表示される **フィルター** フライアウトで、次の設定を構成します。

- **操作**: [許可 **] または [ブロック****] または**[両方] を選択します。

- **Never expire**: Select off: ![ Toggle off or ](../../media/scc-toggle-off.png) on: Toggle on ![ ](../../media/scc-toggle-on.png) .

- **Last updated**: Select a start date (**From),** an end date (**To**) or both.

- **有効期限**: 開始日 **(開始日**)、終了日 (**終了日**) または両方を選択します。

完了したら、[適用] をクリック **します**。

既存のフィルターをクリアするには、[フィルター]**を** クリックし、表示される [フィルター] フライアウトで [フィルターのクリア]**をクリックします**。

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a>セキュリティ/コンプライアンス センター&使用して、テナントの許可/ブロックリストのエントリを変更する

URL 値自体は変更できない。 代わりに、エントリを削除して再作成する必要があります。

1. セキュリティ/コンプライアンス センター&、脅威 **管理ポリシー** のテナントの許可 \>  \> **/ブロックリストに移動します**。

2. **[URL] タブを選択** します。

3. 変更するエントリを選択し、[編集] アイコン **を** ![ クリックします ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 。

4. 表示されるフライアウトで、次の設定を構成します。

   - **ブロック/許可**: 許可または **ブロックを** 選択 **します**。

   - **有効期限が切れる** ことはありません: 次のいずれかの手順を実行します。

     - 設定がオフ (トグル オフ) になっていることを確認し、[有効期限] ボックスを使用してエントリの ![ ](../../media/scc-toggle-off.png) 有効期限を指定します。 

     または

     - トグルを右に移動して、有効期限が切れなさらないエントリを構成します。 ![オンに切り替え](../../media/scc-toggle-on.png).

   - **省略可能なメモ**: エントリの説明文を入力します。

5. 完了したら、**[保存]** をクリックします。

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a>セキュリティ/コンプライアンス センター&使用して、テナントの許可/ブロックの一覧からエントリを削除する

1. セキュリティ/コンプライアンス センター&、脅威 **管理ポリシー** のテナントの許可 \>  \> **/ブロックリストに移動します**。

2. **[URL] タブを選択** します。

3. 削除するエントリを選択し、[削除] アイコン **を** ![ クリックします ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 。

4. 警告ダイアログが表示されたら、[削除] を **クリックします**。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>Exchange Online PowerShell またはスタンドアロンの EOP PowerShell を使用してテナントの許可/ブロックリストを構成する

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a>PowerShell を使用してテナントの許可/ブロックリストにエントリを追加する

テナントの許可/ブロックリストにエントリを追加するには、次の構文を使用します。

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

この例では、contoso.com およびすべてのサブドメイン (contoso.com、www.contoso.com、および xyz.abc.contoso.com) の URL ブロック エントリを追加します。 ExpirationDate パラメーターまたは NoExpiration パラメーターを使用しなかったため、エントリは 30 日後に期限切れになります。

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

構文およびパラメーターの詳細については [、「New-TenantAllowBlockListItems」を参照してください](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)。

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a>PowerShell を使用してテナントの許可/ブロックリストのエントリを表示する

テナントの許可/ブロックリストのエントリを表示するには、次の構文を使用します。

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

この例では、すべてのブロックされた URL を返します。

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

構文およびパラメーターの詳細については [、「Get-TenantAllowBlockListItems」を参照してください](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)。

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a>PowerShell を使用してテナントの許可/ブロックリストのエントリを変更する

URL 値自体は変更できない。 代わりに、エントリを削除して再作成する必要があります。

テナントの許可/ブロックリストのエントリを変更するには、次の構文を使用します。

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

次の使用例は、指定したエントリの有効期限を変更します。

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

構文およびパラメーターの詳細については [、「Set-TenantAllowBlockListItems」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)。

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a>PowerShell を使用してテナントの許可/ブロックリストからエントリを削除する

テナントの許可/ブロックリストからエントリを削除するには、次の構文を使用します。

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

この例では、指定した URL エントリをテナントの許可/ブロックリストから削除します。

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

構文およびパラメーターの詳細については [、「Remove-TenantAllowBlockListItems」を参照してください](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)。

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>テナントの許可/ブロックリストの URL 構文

- IP4v および IPv6 アドレスは許可されますが、TCP/UDP ポートは許可されません。

- ファイル名拡張子は許可されません (たとえば、test.pdf)。

- Unicode はサポートされていませんが、Punycode はサポートされています。

- ホスト名は、次のステートメントのすべてが当てはまる場合に使用できます。

  - ホスト名にはピリオドが含まれている。
  - ピリオドの左側に少なくとも 1 つの文字があります。
  - ピリオドの右側に 2 文字以上あります。

  たとえば、 `t.co` 許可されている、または `.com` `contoso.` 許可されていない。

- サブパスは暗黙的ではありません。

  たとえば、 `contoso.com` `contoso.com/a` .

- ワイルドカード (*) は、次のシナリオで使用できます。

  - サブドメインを指定するには、左ワイルドカードの後にピリオドを付けなければならない。

    たとえば、 `*.contoso.com` 許可されます。 `*contoso.com` 許可されません。

  - パスを指定するには、右のワイルドカードがスラッシュ (/) の後に続く必要があります。

    たとえば、 `contoso.com/*` 許可されている、または `contoso.com*` `contoso.com/ab*` 許可されていない。

  - すべてのサブパスは、適切なワイルドカードによって暗黙的に示されるものではありません。

    たとえば、 `contoso.com/*` `contoso.com/a` .

  - `*.com*` は無効です (解決可能なドメインではなく、右のワイルドカードがスラッシュに従う必要があります)。

  - IP アドレスではワイルドカードを使用できません。

- チルダ (~) 文字は、次のシナリオで使用できます。

  - 左チルダは、ドメインとすべてのサブドメインを意味します。

    次に例 `~contoso.com` を示 `contoso.com` します `*.contoso.com` 。

- URL エントリは、すべてのプロトコルに適用されるので、プロトコルを含む URL エントリ (たとえば、,, `http://` `https://` `ftp://` または) は失敗します。

- ユーザー名またはパスワードはサポートされていないか、必須です。

- 引用符 (' または ") は無効な文字です。

- URL には、可能な限りすべてのリダイレクトを含める必要があります。

### <a name="url-entry-scenarios"></a>URL エントリのシナリオ

有効な URL エントリとその結果については、次のセクションで説明します。

#### <a name="scenario-no-wildcards"></a>シナリオ: ワイルドカードなし

**エントリ**: `contoso.com`

- **一致を許可** する : contoso.com

- **Allow not matched**:

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

- **ブロックが一致しません**: abc-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>シナリオ: 左ワイルドカード (サブドメイン)

**エントリ**: `*.contoso.com`

- **一致とブロック** の一 **致を許可する**:

  - www.contoso.com
  - xyz.abc.contoso.com

- **Allow not matched** and **Block not matched**:

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-at-top-of-path"></a>シナリオ: パスの上部に右のワイルドカード

**エントリ**: `contoso.com/a/*`

- **一致とブロック** の一 **致を許可する**:

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso.com/a/?q=joe@t.com

- **Allow not matched** and **Block not matched**:

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

#### <a name="scenario-left-tilde"></a>シナリオ: 左チルダ

**エントリ**: `~contoso.com`

- **一致とブロック** の一 **致を許可する**:

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **Allow not matched** and **Block not matched**:

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>シナリオ: 右ワイルドカード サフィックス

**エントリ**: `contoso.com/*`

- **一致とブロック** の一 **致を許可する**:

  - contoso.com/?q=whatever@fabrikam.com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **Allow not matched** and **Block not matched**: contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>シナリオ: 左ワイルドカード サブドメインと右のワイルドカード サフィックス

**エントリ**: `*.contoso.com/*`

- **一致とブロック** の一 **致を許可する**:

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **Allow not matched** and **Block not matched**: contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>シナリオ: 左右のチルダ

**エントリ**: `~contoso.com~`

- **一致とブロック** の一 **致を許可する**:

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- **Allow not matched** and **Block not matched**:

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>シナリオ: IP アドレス

**エントリ**: `1.2.3.4`

- **マッチを許可** し **、マッチを** ブロックする : 1.2.3.4

- **Allow not matched** and **Block not matched**:

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>右ワイルドカードを使用した IP アドレス

**エントリ**: `1.2.3.4/*`

- **一致とブロック** の一 **致を許可する**:

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>無効なエントリの例

次のエントリは無効です。

- **ドメイン値が見つからないか無効です**。

  - contoso
  - \*.contoso.\*
  - \*.com
  - \*.pdf

- **テキストに対するワイルドカード、またはスペースを使用しない文字**:

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

- **中のワイルドカード**:

  - conto \* so.com
  - conto~so.com

- **二重ワイルドカード**

  - contoso.com/\*\*
  - contoso.com/\*/\*
