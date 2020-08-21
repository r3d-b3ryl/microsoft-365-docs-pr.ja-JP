---
title: テナント許可/ブロック一覧で許可される URL とブロックされる URL を管理する
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
description: 管理者は、セキュリティ コンプライアンス センターのテナントの許可/ブロック リストの URL エントリを構成する方法&できます。
ms.openlocfilehash: 888a96f23daf2cf47847466ad4080f310be7f9b4
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845944"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a>テナントの許可/禁止リストの URL を管理する

> [!NOTE]
> このトピックで説明する機能はプレビュー段階であり、変更される可能性があります。すべての組織で利用できるものもあります。

Exchange Online にメールボックスがある Microsoft 365 組織や、Exchange Online メールボックスを使用しないスタンドアロン Exchange Online Protection (EOP) 組織では、EOP フィルター処理について同意する場合があります。 たとえば、優れたメッセージが悪か (誤検知) としてマークされている、または無効なメッセージが許可されている (検知漏れ) などです。

セキュリティ センターのテナント許可/ブロック リストには、&のフィルター操作について手動でオーバーライドする方法が用いました。 テナント許可/禁止一覧は、メール フロー時と、ユーザーがクリックした時に使用されます。 テナントの許可/ブロックリストで、許可またはブロックする URL を指定できます。

このトピックでは、セキュリティ &/コンプライアンス センターまたは PowerShell (Exchange Online のメールボックスを使用する Microsoft 365 組織の場合は Exchange Online PowerShell、Exchange Online メールボックスを持つ組織の場合はスタンドアロン EOP PowerShell) のエントリの構成方法について説明します。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 テナント許可/ブロック リスト **ページに直接移動するには、** 次のコマンドを使用します <https://protection.office.com/tenantAllowBlockList> 。

- 使用できる URL 値については、このトピックの [後半にある「テナントの許可/ブロックリスト」の](#url-syntax-for-the-tenant-allowblock-list) URL 構文で説明します。

- テナント許可/ブロック リストでは、URL のエントリ数を最大で 500 個に設定できます。

- エントリは 15 分以内にアクティブである必要があります。

- ブロック エントリは、許可エントリより優先されます。

- 既定では、テナント許可/禁止一覧のエントリは 30 日後に期限切れになります。 日付を指定したり、期限を切れないように設定したりすることができます。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- このトピックの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。

  - テナント許可/禁止一覧に対して値を追加および削除するには、次の役割グループのいずれかのメンバーである必要があります。

    - **組織の管理**または[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ管理者**。
    - **組織の管理**または [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**検疫管理**。

  - テナントの許可/禁止一覧に対する読み取り専用アクセス権を持つには、次の役割グループのいずれかのメンバーである必要があります。

    - [セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ閲覧者**。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**表示限定の組織管理**。

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a>セキュリティ/コンプライアンス &使用して、テナント許可/ブロック リスト内に URL エントリを作成する

URL エントリの構文の詳細については、このトピックで後述 [する「テナントの許可/ブロックリスト」の](#url-syntax-for-the-tenant-allowblock-list) URL 構文を参照してください。

1. コンプライアンス センター内&で、[脅威管理ポリシー **のテナント** \> **の許可/** \> **ブロック リスト] に移動します**。

2. [テナント許可 **/ブロック一覧] ページ** で、[URL] タブが **選択** されたことを確認し、[追加] をクリック **します。**

3. 表示される **新しい URL の** 追加ポップアップで、次の設定を構成します。

   - **ワイルドカードを使用して URL を追加します**。1 行に 1 つの URL を入力し、最大 20 の URL を入力します。

   - **[Block/Allow]:** 指定した URL を**許可するか****ブロック**するかを選択します。

   - **無期限 :** 次のいずれかの手順を実行します。

     - 設定がオフになっていること (オフに ![ 切り替 ](../../media/scc-toggle-off.png) え) を確認 **し、Expires ボックスを使用** してエントリの有効期限を指定します。

     または

     - エントリを有効期限切れにしないように設定するには、右に切り替えを移動します。 ![オンに切り替え](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **オプション メモ**: エントリの説明テキストを入力します。

4. 完了したら、[追加] を **クリックします**。

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a>セキュリティ/コンプライアンス センター&を使用して、テナントの許可/ブロック リストのエントリを表示する

1. コンプライアンス センター内&で、[脅威管理ポリシー **のテナント** \> **の許可/** \> **ブロック リスト] に移動します**。

2. **[URL] タブを選**びます。

次の列見出しをクリックすると、昇順または昇順で並べ替えられます。

- **値**
- **操作**:**ブロックまたは****許可**。
- **最終更新日**
- **有効期限**
- **注**

[ **グループ化]** をクリックし、[ **アクション** (ブロックまたは**許可)]** または [なし] **にして**エントリを **グループ化します**。

[ **検索]** をクリックし、値の全体または一部を入力して、Enter キーを押して特定の値を検索します。 完了したら、[検索のクリア] **アイコンを** ![ クリックします ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 。

フィルター を **クリックします**。 表示される **[フィルター** ] ポップアップで、次の設定を構成します。

- **操作**: 許可 **、ブロック****、またはその両方**を選択します。

- **有効期限を切れない**: オン (トグ ![ ル ](../../media/scc-toggle-off.png) オフ) またはオン ( ![ トオン) をオンにします ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) 。

- **Last updated:** Select a start date (**From),** an end date (**To**) or both.

- **有効期限:** 開始日 ([開始**日])、** 終了日 **(To)、またはその**両方を選択します。

完了したら、[適用] をクリック **します**。

既存のフィルターをクリアするには **、[フィルター**] をクリックし、表示される **フィルター** ポップアップで [フィルターのクリア] **をクリックします**。

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a>セキュリティ コンプライアンス センター&、テナントの許可/ブロック リスト内のエントリを変更する

URL 値自体は変更できません。 代わりに、入力を削除して再作成する必要があります。

1. コンプライアンス センター内&で、[脅威管理ポリシー **のテナント** \> **の許可/** \> **ブロック リスト] に移動します**。

2. **[URL] タブを選**びます。

3. 変更するエントリを選択し、[編集] アイコン **を** ![ クリックします ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 。

4. 表示されるポップアップで、次の設定を構成します。

   - **Block/Allow**: Select **Allow** or **Block**.

   - **無期限 :** 次のいずれかの手順を実行します。

     - 設定がオフになっていること (オフに ![ 切り替 ](../../media/scc-toggle-off.png) え) を確認 **し、Expires ボックスを使用** してエントリに有効期限を指定します。

     または

     - エントリを有効期限切れにしないように設定するには、右に切り替えを切り替えて入力します。 ![オンに切り替え](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **オプション メモ**: エントリの説明テキストを入力します。

5. 完了したら、**[保存]** をクリックします。

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a>セキュリティ/コンプライアンス センター&を使用して、テナント許可/ブロック リストからエントリを削除する

1. コンプライアンス センター内&で、[脅威管理ポリシー **のテナント** \> **の許可/** \> **ブロック リスト] に移動します**。

2. **[URL] タブを選**びます。

3. 削除するエントリを選択し、[削除] アイコンを **クリック** ![ します ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 。

4. 警告ダイアログが表示されたら、[削除] をクリック **します**。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>Exchange Online PowerShell またはスタンドアロン EOP PowerShell を使用してテナントの許可/ブロック一覧を構成する

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a>PowerShell を使用してテナントの許可/ブロック リストにエントリを追加する

テナント許可/ブロック リストにエントリを追加するには、次の構文を使用します。

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

この例では、メールボックス コレクションとすべてのサブドメインcontoso.com (たとえば、contoso.com、www.contoso.com) の URL ブロック エントリを xyz.abc.contoso.com追加します。 ExpirationDate パラメーターまたは NoExpiration パラメーターを使用しないため、30 日後にエントリの有効期限が切れます。

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

構文およびパラメーターの詳細については [、「New-TenantAllowBlockListItems」を参照してください](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)。

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a>PowerShell を使用してテナントの許可/ブロック リスト内のエントリを表示する

テナント許可/ブロック リストのエントリを表示するには、次の構文を使用します。

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

この例では、ブロックされているすべての URL を返します。

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

構文およびパラメーターの詳細については [、「Get-TenantAllowBlockListItems」を参照してください](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)。

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a>PowerShell を使用してテナントの許可/ブロック リスト内のエントリを変更する

URL 値自体は変更できません。 代わりに、入力を削除して再作成する必要があります。

テナント許可/ブロック リストのエントリを変更するには、次の構文を使用します。

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

この例では、指定したエントリの有効期限を変更します。

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

構文およびパラメーターの詳細については [、「Set-TenantAllowBlockListItems」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)。

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a>PowerShell を使用してテナント許可/ブロック リストからエントリを削除する

テナント許可/ブロック リストからエントリを削除するには、次の構文を使用します。

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

この例では、指定した URL エントリをテナント許可/ブロック一覧から削除します。

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

構文およびパラメーターの詳細については [、Remove-TenantAllowBlockListItems を参照してください](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)。

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>テナント許可/ブロック リストの URL 構文

- IP4v アドレスおよび IPv6 アドレスは使用できますが、TCP/UDP ポートは使用できません。

- ファイル名拡張子は許可されません (たとえば、test.pdf)。

- Unicode はサポートされていませんが、Punycode はサポートされます。

- 次の説明がすべて当たる場合、ホスト名を使用できます。

  - ホスト名にピリオドが含まれている場合。
  - ピリオドの左側には 1 文字以上が必要です。
  - ピリオドの右側には 2 文字以上があります。

  たとえば、許可 `t.co` されている、 `.com` または `contoso.` 許可されていない場合です。

- サブパスは暗黙的にはされません。

  たとえば、何も `contoso.com` 含まれていません `contoso.com/a` 。

- 以下のシナリオでは、ワイルドカード (*) を使用できます。

  - ワイルドカードを左のワイルドカードの後にピリオドで指定する必要があります。

    たとえば、許可 `*.contoso.com` されていますが `*contoso.com` 、許可されていません。

  - ワイルドカードを指定するには、シャープ (/) の後に適切なワイルドカードを指定する必要があります。

    たとえば、許可 `contoso.com/*` されている、 `contoso.com*` または `contoso.com/ab*` 許可されていない場合です。

  - すべてのサブパスは、右のワイルドカードによって示されるものでない。

    たとえば、何も `contoso.com/*` 含まれていません `contoso.com/a` 。

  - `*.com*` 無効なドメインです (解決可能なドメインではありません)。また、右のワイルドカードがスラッシュに従いません)。

  - IP アドレスではワイルドカードは使用できません。

- 切り記号 (~) は、次のシナリオで利用できます。

  - 左のタイルを指定すると、ドメインとすべてのサブドメインが適用されます。

    たとえば `~contoso.com` 、includes や `contoso.com` `*.contoso.com` .

- URL エントリはすべてのプロトコルに適用されているため、プロトコル ( `http://` たとえば `https://` 、, など) を含む URL エントリ `ftp://` は失敗します。

- ユーザー名やパスワードはサポートされていないか、必須ではありません。

- かつ正しくない文字 (' または ") です。

- URL には、可能な限り、すべてのリダイレクトを含める必要があります。

### <a name="url-entry-scenarios"></a>URL 入力のシナリオ

有効な URL エントリとその結果については、以下のセクションで説明します。

#### <a name="scenario-no-wildcards"></a>シナリオ: ワイルドカードなし

**エントリ**: `contoso.com`

- **マッチを許可**する : contoso.com

- **許可しない**:

  - abc-contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com
  
- **ブロックの一致**:

  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **ブロックが見つかりません**: abc-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>シナリオ: 左ワイルドカード (サブドメイン)

**エントリ**: `*.contoso.com`

- **マッチとブロック** の **マッチを許可します**:

  - www.contoso.com
  - xyz.abc.contoso.com

- **一致およびブロック**禁止**Block not matched**

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a>シナリオ: パスの上部にワイルドカード文字をワイルドカード

**エントリ**: `contoso.com/a/*`

- **マッチとブロック** の **マッチを許可します**:

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso.com/a/?q=joe@t.com

- **一致およびブロック**禁止**Block not matched**

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com
  
#### <a name="scenario-left-tilde"></a>シナリオ: 左揃え

**エントリ**: `~contoso.com`

- **マッチとブロック** の **マッチを許可します**:

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **一致およびブロック**禁止**Block not matched**

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>シナリオ: 右のワイルドカード サフィックス

**エントリ**: `contoso.com/*`

- **マッチとブロック** の **マッチを許可します**:

  - contoso.com/?q=whatever@fabrikam.com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **一致禁止およびブロック****の禁止**: contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>シナリオ: 左ワイルドカード サブドメインと、右ワイルドカード サフィックス

**エントリ**: `*.contoso.com/*`

- **マッチとブロック** の **マッチを許可します**:

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **一致しない、または****ブロックを禁止する**: contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>シナリオ: 左右のシルード

**エントリ**: `~contoso.com~`

- **マッチとブロック** の **マッチを許可します**:

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- **一致およびブロック**禁止**Block not matched**

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>シナリオ: IP アドレス

**エントリ**: `1.2.3.4`

- **一致を許可****する一致を許可**する : 1.2.3.4

- **一致およびブロック**禁止**Block not matched**

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>適切なワイルドカードを使用した IP アドレス

**エントリ**: `1.2.3.4/*`

- **マッチとブロック** の **マッチを許可します**:

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>無効なエントリの例

次のエントリは無効です。

- **ドメインの値が見つからないか、無効です**。

  - contoso
  - \*.contoso.\*
  - \*.com
  - \*.pdf

- **テキスト上のワイルドカードまたは間隔文字なし**:

  - \*contoso.com
  - contoso.com\*
  - \*1.2.3.4
  - 1.2.3.4\*
  - contoso.com/a\*
  - contoso.com/ab\*

- **ポートを使用した IP アドレス**:

  - contoso.com:443
  - abc.contoso.com:25

- **非説明のワイルドカード**:

  - \*
  - \*.\*

- **中間ワイルドカード**:

  - conto \* so.com
  - conto~so.com

- **二重ワイルドカード**

  - contoso.com/\*\*
  - contoso.com/\*/\*
