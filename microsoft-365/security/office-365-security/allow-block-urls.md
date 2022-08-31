---
title: テナント許可/禁止リストを使用して URL を許可またはブロックする
f1.keywords:
- NOCSH
ms.author: chrisda
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150manage-tenant-allows.md
ms.collection:
- M365-security-compliance
description: 管理者は、セキュリティ ポータルのテナント許可/ブロックリストで URL を許可またはブロックする方法について説明します。
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 4160bb2351f0096dafb189d63a9b0498c141fdde
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67467033"
---
# <a name="allow-or-block-urls-using-the-tenant-allowblock-list"></a>テナント許可/禁止リストを使用して URL を許可またはブロックする

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

この記事では、テナント許可/ブロック リストで使用できる URL 許可とブロック エントリを作成および管理する方法について説明します。 テナント許可/ブロックリストの詳細については、「テナント許可/ブロック一 [覧で許可とブロックを管理する」を参照してください](manage-tenant-allow-block-list.md)。

URL の許可とブロックのエントリは、Microsoft 365 Defender ポータルまたは powerShell Exchange Onlineで管理します。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。 **[テナントの許可/ブロック一覧**] ページに直接移動するには、 <https://security.microsoft.com/tenantAllowBlockList>. **[申請]** ページに直接移動するには、 <https://security.microsoft.com/reportsubmission>.

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- URL エントリの構文については、この記事の後半の [「テナント許可/ブロックリスト](#url-syntax-for-the-tenant-allowblock-list) 」セクションの URL 構文を参照してください。

- URL の場合、許可エントリの最大数は 500 で、ブロック エントリの最大数は 500 (合計 1,000 URL エントリ) です。

- URL エントリには最大 250 文字を入力できます。

- エントリは 30 分以内にアクティブにする必要がありますが、エントリがアクティブになるまでに最大で 24 時間かかる場合があります。

- この記事の手順を実行する際には、あらかじめExchange Online でアクセス許可を割り当てる必要があります。
  - テナント許可/ブロック リストの値を追加および削除するには、次のいずれかの役割グループのメンバーである必要があります。
    - **組織の管理** または **セキュリティ管理者** の役割グループ (**セキュリティ管理者ロール**)
    - **Security Operator** ロール グループ (**テナント AllowBlockList Manager**)。
  - テナント許可/ブロック リストへの読み取り専用アクセスの場合は、次のいずれかの役割グループのメンバーである必要があります。
    - **グローバル リーダー**  の役割グループ
    - **セキュリティ 閲覧者** の役割グループ
    - **ビューのみの構成** 役割グループ

  詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。

  **注**:

  - Microsoft 365 管理センターで、対応する Azure Active Directory のロールにユーザーを追加すると、ユーザーには、必要なアクセス許可 *および* Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。詳しくは、「[管理者のロールについて](../../admin/add-users/about-admin-roles.md)」を参照してください。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

## <a name="create-block-entries-for-urls"></a>URL のブロック エントリを作成する

URL のブロック エントリを作成するには、次のオプションがあります。

- [Microsoft 365 Defender ポータルの [申請] ページ](#use-the-microsoft-365-defender-portal-to-create-block-entries-for-urls-in-the-submissions-portal)
- [Microsoft 365 Defender ポータル](#use-the-microsoft-365-defender-portal-to-create-block-entries-for-urls-in-the-tenant-allowblock-list)または [PowerShell](#use-powershell-to-create-block-entries-for-urls-in-the-tenant-allowblock-list) のテナント許可/ブロックリスト

### <a name="use-the-microsoft-365-defender-portal-to-create-block-entries-for-urls-in-the-submissions-portal"></a>Microsoft 365 Defender ポータルを使用して、申請ポータルで URL のブロック エントリを作成する

申請ポータルを <https://security.microsoft.com/reportsubmission> 使用して URL を **[ブロックされている必要があります ] (False negative)** として報告する場合は、[ **このファイルをブロックする** ] を選択して、テナント許可/ブロック リスト内の URL のブロック エントリを追加できます。

手順については、「 [問題のある URL を Microsoft に報告する」を参照してください](admin-submission.md#report-questionable-urls-to-microsoft)。

### <a name="use-the-microsoft-365-defender-portal-to-create-block-entries-for-urls-in-the-tenant-allowblock-list"></a>Microsoft 365 Defender ポータルを使用して、テナント許可/ブロック リスト内の URL のブロック エントリを作成する

テナント許可/ブロック 一覧で URL のブロック エントリを直接作成します。

> [!NOTE]
> これらのブロックされた URL を含むEmail メッセージは、*高信頼フィッシング* としてブロックされます。

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**ポリシー&ルール****脅威ポリシー** \> **ルール**\>] セクション\>**の [テナント許可/ブロック リスト**] に移動します。 または、 **テナント許可/ブロック リスト** ページに直接移動するには、 <https://security.microsoft.com/tenantAllowBlockList>.

2. [ **テナントの許可/ブロック一覧** ] ページで、[ **URL** ] タブを選択します。

3. [URL] タブ **で** 、[ブロック] アイコンをクリックします ![。](../../media/m365-cc-sc-create-icon.png) **ブロック**。

4. 表示される **[ブロック URL]** ポップアップで、次の設定を構成します。

   - **ワイルドカードを使用して URL を追加する**: 1 行に 1 つの URL を入力し、最大 20 個まで入力します。 URL エントリの構文の詳細については、この記事の後半の [「テナント許可/ブロック一覧](#url-syntax-for-the-tenant-allowblock-list) 」セクションの URL 構文を参照してください。

   - **ブロック エントリの削除後**: 既定値は **30 日** ですが、次の値から選択できます。
     - **有効期限が切れない**
     - **1 日**
     - **7 日間**
     - **30 日間**
     - **特定の日付**: 最大値は今日から 90 日です。

   - **省略可能な注**: エントリの説明テキストを入力します。

5. 完了したら、**[追加]** をクリックします。

#### <a name="use-powershell-to-create-block-entries-for-urls-in-the-tenant-allowblock-list"></a>PowerShell を使用して、テナント許可/ブロック リスト内の URL のブロック エントリを作成する

[powerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)で、次の構文を使用します。

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate <Date> | -NoExpiration> [-Notes <String>]
```

この例では、contoso.com とすべてのサブドメイン (contoso.com や xyz.abc.contoso.com など) のブロック URL エントリを追加します。 ExpirationDate パラメーターまたは NoExpiration パラメーターを使用していないため、エントリは 30 日後に期限切れになります。

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

構文とパラメーターの詳細については、「 [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems)」を参照してください。

## <a name="use-the-microsoft-365-defender-portal-to-create-allow-entries-for-urls-in-the-submissions-portal"></a>Microsoft 365 Defender ポータルを使用して、申請ポータルで URL の許可エントリを作成する

テナント許可/ブロック リストに URL 許可エントリを直接作成することはできません。 代わりに、送信ポータルを <https://security.microsoft.com/reportsubmission> 使用して、メッセージを誤検知として報告します。 管理者の提出の詳細については、「 [申請ポータルを使用して、疑わしいスパム、フィッシング、URL、ブロックされる正当な電子メール、および電子メールの添付ファイルを Microsoft に送信する」を参照してください](admin-submission.md)。

**[申請]** ページで URL を誤検知として報告すると、テナントの許可/ブロックリストに URL の許可エントリが追加されます。

> [!IMPORTANT]
> Microsoft が許可エントリを管理するため、不要な URL 許可エントリは削除されます。 この動作により、組織が保護され、構成の誤った許可エントリを防ぐことができます。 判定に同意しない場合は、URL がまだ不適切と見なされる理由を特定するためにサポート ケースを開く必要がある場合があります。

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[アクション] & **[申請**] の [**申請]** ページ **に**\>移動します。 **[申請]** ページに直接移動するには、 <https://security.microsoft.com/reportsubmission>.

2. [ **申請] ページで** 、[ **URL** ] タブを選択します。

3. [ **URL] タブで** 、[分析のために Microsoft に送信] アイコンをクリックします ![。](../../media/m365-cc-sc-create-icon.png) **分析のために Microsoft に送信します**。

4. 表示される **分析ポップアップの [Microsoft に送信]** に、次の情報を入力します。

   - **送信の種類を選択します**。値の **URL** が選択されていることを確認します。

   - **URL**: 完全な URL (たとえば) を入力し、 `https://www.fabrikam.com/marketing.html`表示されるボックスで選択します。

   - **Microsoft に送信する理由を選択** します: [ **ブロックされていない必要があります (False positive)]**、[次の設定の構成] の順に選択します。

     - **この URL を許可** する: この設定 ![をオンに切り替えます](../../media/scc-toggle-on.png)。.

         - **許可エントリの削除後**: 既定値は **30 日** ですが、次の値から選択できます。
           - **1 日**
           - **7 日間**
           - **30 日間**
           - **特定の日付**: 最大値は今日から 30 日です。

         - **入力を許可する注**: この URL を許可する理由に関する省略可能な情報を入力します。

   完了したら、[ **送信]** をクリックし、[完了] をクリック **します**。

   :::image type="content" source="../../media/admin-submission-url-allow.png" alt-text="Defender ポータルの [提出] ページで、分析のために Microsoft に偽陽性 (適切な) URL を送信します。" lightbox="../../media/admin-submission-url-allow.png":::

5. しばらくすると、[**テナント許可/ブロック リスト**] ページの **[URL**] タブに URL 許可エントリが表示されます。

> [!NOTE]
>
> - URL が再び検出されると、 [安全なリンク](safe-links.md) の起爆や URL の評価チェックには送信されず、他のすべての URL ベースのフィルターはスキップされます。
> - メール フロー中に、URL を含むメッセージがフィルター 処理スタック内の他の URL 以外のチェックに合格した場合、メッセージは配信されます。

## <a name="use-the-microsoft-365-defender-portal-to-view-allow-or-block-entries-for-urls-in-the-tenant-allowblock-list"></a>Microsoft 365 Defender ポータルを使用して、テナント許可/ブロック リスト内の URL の許可エントリまたはブロック エントリを表示する

1. Microsoft 365 Defender ポータルの [ルール **] セクションの** <https://security.microsoft.com>[**ポリシー&ルール** \> **脅威ポリシー** \> **テナント許可/ブロック リスト**] に移動します。 または、 **テナント許可/ブロック リスト** ページに直接移動するには、 <https://security.microsoft.com/tenantAllowBlockList>.

2. [ **URL** ] タブを選択します。次の列を使用できます。

   - **値**: URL。
   - **アクション**: 値 **Allow** または **Block**。
   - **変更者**
   - **最終更新日時**
   - **[削除日**]: 有効期限。
   - **注**

   列見出しをクリックして、昇順または降順で並べ替えます。

   [グループ] アイコンをクリック ![します。](../../media/m365-cc-sc-group-icon.png) **結果** を **[なし]** または **[アクション**] でグループ化します。

   [検索] アイコンをクリック ![します。](../../media/m365-cc-sc-search-icon.png) **値** のすべてまたは一部を検索して入力し、Enter キーを押して特定の値を検索します。 完了したら、[検索のクリア] アイコンをクリックします ![。](../../media/m365-cc-sc-close-icon.png) を選択して検索をクリアします。

   [フィルター] アイコンをクリック ![します。](../../media/m365-cc-sc-filter-icon.png) **フィルター処理** して結果をフィルター処理します。 次の値は、表示される **フィルター** ポップアップで使用できます。

   - **アクション**: **許可** と **ブロック**。
   - **期限切れになることはありません**: ![オンに切り替えます。](../../media/scc-toggle-on.png) または ![トグルオフにします。](../../media/scc-toggle-off.png)
   - **最終更新日**: **[開始日** ] と [ **終了日]** を選択します。
   - **[削除日**]: **[開始日** ] と [ **終了日]** を選択します。

   完了したら、**[適用]** をクリックします。 既存のフィルターをクリアするには、[フィルター] ポップアップで [フィルターのクリア] アイコンの **[フィルターのクリア****] を**](../../media/m365-cc-sc-clear-filters-icon.png)クリック![します。

### <a name="use-powershell-to-view-allow-or-block-entries-for-urls-in-the-tenant-allowblock-list"></a>PowerShell を使用して、テナント許可/ブロックリスト内の URL の許可エントリまたはブロック エントリを表示する

[powerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)で、次の構文を使用します。

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Allow] [-Block] [-Entry <URLValue>] [<-ExpirationDate <Date> | -NoExpiration>]
```

次の使用例は、許可されている URL とブロックされたすべての URL を返します。

```powershell
Get-TenantAllowBlockListItems -ListType Url
```

次の使用例は、ブロックされた URL によって結果をフィルター処理します。

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

構文とパラメーターの詳細については、「 [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems)」を参照してください。

## <a name="use-the-microsoft-365-defender-portal-to-modify-allow-or-block-entries-for-urls-in-the-tenant-allowblock-list"></a>Microsoft 365 Defender ポータルを使用して、テナント許可/ブロック リスト内の URL の許可エントリまたはブロック エントリを変更する

テナントの許可/ブロックの一覧で許可またはブロック URL エントリを変更する場合は、有効期限とメモのみを変更できます。

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**ポリシー&ルール****脅威ポリシー** \> **ルール**\>] セクション\>**の [テナント許可/ブロック リスト**] に移動します。 または、 **テナント許可/ブロック リスト** ページに直接移動するには、 <https://security.microsoft.com/tenantAllowBlockList>.

2. [URL] タブ **を** 選択する

3. [ **URL** ] タブで、変更するエントリのチェック ボックスをオンにし、[編集] アイコンを ![クリックします。](../../media/m365-cc-sc-edit-icon.png) **表示される [編集]** ボタン。

4. 次の値は、表示される **[URL の編集]** ポップアップで使用できます。

   - **許可エントリを削除した後に削除** するか **、ブロック エントリを削除します。**
     - 許可エントリは、作成日から最大 30 日間延長できます。
     - ブロック エントリは、作成日から最大 90 日間延長することも、 **期限切れにならないように** 設定することもできます。

   - **省略可能なメモ**

   完了したら、**[保存]** をクリックします。

> [!NOTE]
> エントリを許可する場合にのみ、チェック ボックス以外の行の任意の場所をクリックしてエントリを選択した場合は、[提出の表示] アイコンを選択 ![できます。](../../media/m365-cc-sc-view-submission-icon.png) **[申請]** ページ<https://security.microsoft.com/reportsubmission>に移動するように表示される詳細ポップアップで **提出を** 表示します。

### <a name="use-powershell-to-modify-allow-or-block-entries-for-urls-in-the-tenant-allowblock-list"></a>PowerShell を使用して、テナント許可/ブロック一覧の URL の許可エントリまたはブロック エントリを変更する

[powerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)で、次の構文を使用します。

```powershell
Set-TenantAllowBlockListItems -ListType Url <-Ids <Identity value> | -Entries <Value value>> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

この例では、指定したブロック URL エントリの有効期限を変更します。

```powershell
Set-TenantAllowBlockListItems -ListType Url -Entries "~contoso.com" -ExpirationDate "9/1/2022"
```

構文とパラメーターの詳細については、「 [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems)」を参照してください。

## <a name="use-the-microsoft-365-defender-portal-to-remove-allow-or-block-entries-for-urls-from-the-tenant-allowblock-list"></a>Microsoft 365 Defender ポータルを使用して、テナント許可/ブロック リストから URL の許可エントリまたはブロック エントリを削除する

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**ポリシー&ルール****脅威ポリシー** \> **ルール**\>] セクション\>**の [テナント許可/ブロック リスト**] に移動します。 または、 **テナント許可/ブロック リスト** ページに直接移動するには、 <https://security.microsoft.com/tenantAllowBlockList>.

2. [URL] タブ **を** 選択します。

3. [ **URL]** タブで、次のいずれかの手順を実行します。

   - 削除するエントリのチェック ボックスをオンにし、[削除] アイコンを ![クリックします。](../../media/m365-cc-sc-delete-icon.png) **表示される削除** アイコン。
   - チェック ボックス以外の行の任意の場所をクリックして、削除するエントリを選択します。 表示される詳細ポップアップで、[削除] アイコンをクリックします ![。](../../media/m365-cc-sc-delete-icon.png) **Delete**

4. 表示される警告ダイアログで、[削除] をクリック **します**。

> [!NOTE]
> 複数のエントリを選択するには、各チェック ボックスをオンにするか、 **値** 列ヘッダーの横にあるチェック ボックスをオンにしてすべてのエントリを選択します。

### <a name="use-powershell-to-remove-allow-or-block-entries-for-urls-from-the-tenant-allowblock-list"></a>PowerShell を使用して、テナント許可/ブロック リストから URL の許可エントリまたはブロック エントリを削除する

[powerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)で、次の構文を使用します。

```powershell
Remove-TenantAllowBlockListItems -ListType Url <-Ids <Identity value> | -Entries <Value value>>
```

次の使用例は、指定したブロック URL エントリをテナント許可/ブロック リストから削除します。

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Entries "~cohovineyard.com
```

構文とパラメーターの詳細については、「 [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems)」を参照してください。

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>テナント許可/ブロック リストの URL 構文

- IPv4 アドレスと IPv6 アドレスは許可されますが、TCP/UDP ポートは許可されません。

- ファイル名拡張子は許可されません (test.pdfなど)。

- Unicode はサポートされていませんが、Punycode はサポートされています。

- ホスト名は、次のすべてのステートメントに該当する場合に許可されます。
  - ホスト名にはピリオドが含まれています。
  - ピリオドの左側に少なくとも 1 つの文字があります。
  - ピリオドの右側には少なくとも 2 文字あります。

  たとえば、 `t.co` 許可されているか、 `.com` 許可されていないか `contoso.` などです。

- サブパスは許可に対して暗示されません。

  たとえば、. `contoso.com` `contoso.com/a`

- ワイルドカード (*) は、次のシナリオで使用できます。

  - サブドメインを指定するには、左側のワイルドカードの後にピリオドが続く必要があります。 (ブロックにのみ適用)

    たとえば、 `*.contoso.com` 許可されます。 `*contoso.com` 許可されません。

  - パスを指定するには、右のワイルドカードをスラッシュ (/) に従う必要があります。

    たとえば、 `contoso.com/*` 許可されているか、 `contoso.com*` 許可されていないか `contoso.com/ab*` などです。

  - `*.com*` が無効です (解決可能なドメインではなく、正しいワイルドカードがスラッシュに従っていません)。

  - IP アドレスではワイルドカードは使用できません。

- チルダ (~) 文字は、次のシナリオで使用できます。

  - 左側のチルダは、ドメインとすべてのサブドメインを意味します。

    たとえば`~contoso.com`、次のものが含まれます`contoso.com`。`*.contoso.com`

- ユーザー名またはパスワードはサポートされていないか、必須ではありません。

- 引用符 (' または ") は無効な文字です。

- URL には、可能な限りすべてのリダイレクトを含める必要があります。

### <a name="url-entry-scenarios"></a>URL エントリのシナリオ

有効な URL エントリとその結果については、次のセクションで説明します。

#### <a name="scenario-no-wildcards"></a>シナリオ: ワイルドカードなし

**エントリ**: `contoso.com`

- **一致を許可** する: contoso.com

- **一致しない許可**:
  - abc-contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - contoso.com
  - contoso.com/q=a@contoso.com

- **ブロックの一致**:
  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - contoso.com
  - contoso.com/q=a@contoso.com

- **一致しないブロック**: abc-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>シナリオ: 左ワイルドカード (サブドメイン)

> [!NOTE]
> このシナリオは、ブロックにのみ適用されます。

**エントリ**: `*.contoso.com`

- **ブロックの一致**:
  - contoso.com
  - xyz.abc.contoso.com

- **一致しないブロック**:
  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - contoso.com/abc

#### <a name="scenario-right-wildcard-at-top-of-path"></a>シナリオ: パスの上部にある右のワイルドカード

**エントリ**: `contoso.com/a/*`

- **一致** と **ブロックの一致** を許可する:
  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso.com/a/?q=joe@t.com

- **[一致しない]** と [ **ブロックが一致しない]** を許可します。
  - contoso.com
  - contoso.com/a
  - contoso.com
  - contoso.com/q=a@contoso.com

#### <a name="scenario-left-tilde"></a>シナリオ: 左チルダ

**エントリ**: `~contoso.com`

- **一致** と **ブロックの一致** を許可する:
  - contoso.com
  - contoso.com
  - xyz.abc.contoso.com

- **[一致しない]** と [ **ブロックが一致しない]** を許可します。
  - 123contoso.com
  - contoso.com/abc
  - contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>シナリオ: 右ワイルドカード サフィックス

**エントリ**: `contoso.com/*`

- **一致** と **ブロックの一致** を許可する:
  - contoso.com/?q=whatever@fabrikam.com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **一致しない** 許可と **一致しないブロック**: contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>シナリオ: 左ワイルドカード サブドメインと右ワイルドカード サフィックス

> [!NOTE]
> このシナリオは、ブロックにのみ適用されます。

**エントリ**: `*.contoso.com/*`

- **ブロックの一致**:
  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - contoso.com/a
  - contoso.com/b/a/c
  - xyz.contoso.com/ba

- **一致しないブロック**: contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>シナリオ: 左右のチルダ

**エントリ**: `~contoso.com~`

- **一致** と **ブロックの一致** を許可する:

  - contoso.com
  - contoso.com/a
  - contoso.com
  - contoso.com/b
  - xyz.abc.contoso.com

- **[一致しない]** と [ **ブロックが一致しない]** を許可します。

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>シナリオ: IP アドレス

**エントリ**: `1.2.3.4`

- **一致** と **ブロックの一致** を許可する: 1.2.3.4

- **[一致しない]** と [ **ブロックが一致しない]** を許可します。

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>右のワイルドカードを含む IP アドレス

**エントリ**: `1.2.3.4/*`

- **一致** と **ブロックの一致** を許可する:

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>無効なエントリの例

次のエントリは無効です。

- **ドメイン値が見つからないか無効です**。

  - Contoso
  - \*.contoso.\*
  - \*.com
  - \*.pdf

- **テキストのワイルドカードまたは空白文字なし**:

  - \*contoso.com
  - contoso.com\*
  - \*1.2.3.4
  - 1.2.3.4\*
  - contoso.com/a\*
  - contoso.com/ab\*

- **ポートを含む IP アドレス**:

  - contoso.com:443
  - abc.contoso.com:25

- **説明以外のワイルドカード**:

  - \*
  - \*.\*

- **中央のワイルドカード**:

  - conto\*so.com
  - conto~so.com

- **二重ワイルドカード**

  - contoso.com/\*\*
  - contoso.com/\*/\*

## <a name="related-articles"></a>関連記事

- [送信ポータルを使用して、疑わしいスパム、フィッシング、URL、ブロックされる正当なメール、および電子メールの添付ファイルを Microsoft に送信する](admin-submission.md)
- [誤検知と偽陰性を報告する](report-false-positives-and-false-negatives.md)
- [テナント許可/ブロック一覧で許可とブロックを管理する](manage-tenant-allow-block-list.md)
- [テナント許可/ブロック リスト内のファイルを許可またはブロックする](allow-block-files.md)
- [テナントの許可/ブロック一覧で電子メールを許可またはブロックする](allow-block-email-spoof.md)
