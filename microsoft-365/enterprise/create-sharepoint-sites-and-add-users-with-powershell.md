---
title: PowerShell を使用して SharePoint Online サイトを作成し、ユーザーを追加する
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.topic: landing-page
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- SPO_Content
- seo-marvel-apr2020
ms.assetid: d0d3877a-831f-4744-96b0-d8167f06cca2
description: '概要: PowerShell を使用して新しい SharePoint Online サイトを作成し、それらのサイトにユーザーとグループを追加します。'
ms.openlocfilehash: 9d99f98825d88e2d2e63f106a7b5704c773c8be1
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65101339"
---
# <a name="create-sharepoint-online-sites-and-add-users-with-powershell"></a>PowerShell を使用して SharePoint Online サイトを作成し、ユーザーを追加する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

PowerShell for Microsoft 365を使用してSharePoint Online サイトを作成し、ユーザーを追加する場合、Microsoft 365 管理センターで実行できるよりもはるかに高速にタスクをすばやく繰り返し実行できます。 Microsoft 365 管理センターでは実行できないタスクを実行することもできます。

## <a name="connect-to-sharepoint-online"></a>SharePoint Online に接続する

このトピックの手順では、SharePoint Online に接続する必要があります。 手順については、「[オンライン PowerShell をSharePointするConnect」を](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)参照してください。

## <a name="step-1-create-new-site-collections-using-powershell"></a>手順 1: PowerShell を使用して新しいサイト コレクションを作成する

PowerShell を使用して複数のサイトを作成し、メモ帳サンプル コードを使用して作成する.csv ファイルを作成します。 この手順では、角かっこで囲まれたプレースホルダー情報を、独自のサイトおよびテナント固有の情報に置き換えます。 このプロセスでは、1 つのファイルを作成し、そのファイルを使用する 1 つの PowerShell コマンドを実行できます。 これにより、繰り返し可能な操作と移植可能な操作の両方が実行され、すべてではないにしても、SharePoint Online Management Shell に長いコマンドを入力することで発生する可能性のある多くのエラーが解消されます。 この手順には 2 つの部分があります。 最初に.csv ファイルを作成し、PowerShell を使用してその.csv ファイルを参照します。このファイルは、その内容を使用してサイトを作成します。

PowerShell コマンドレットは、.csv ファイルをインポートし、ファイルの最初の行を列ヘッダーとして読み取る中かっこ内のループにパイプします。 その後、PowerShell コマンドレットは残りのレコードを反復処理し、レコードごとに新しいサイト コレクションを作成し、列ヘッダーに従ってサイト コレクションのプロパティを割り当てます。

### <a name="create-a-csv-file"></a>.csv ファイルの作成

> [!NOTE]
> リソース クォータ パラメーターは、クラシック サイトでのみ機能します。 モダン サイトでこのパラメーターを使用すると、非推奨になったという警告メッセージが表示される場合があります。

1. メモ帳を開き、次のテキスト ブロックを貼り付けます。

   ```powershell
   Owner,StorageQuota,Url,ResourceQuota,Template,TimeZoneID,Name
   owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/TeamSite01,25,EHS#1,10,Contoso Team Site
   owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/Blog01,25,BLOG#0,10,Contoso Blog
   owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Project01,25,PROJECTSITE#0,10,Project Alpha
   owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Community01,25,COMMUNITY#0,10,Community Site
   ```

   *テナントはテナント* の名前であり、*所有者* はプライマリ サイト コレクション管理者のロールを付与するテナント上のユーザーのユーザー名です。

   (メモ帳を使用して一括置換を高速化する場合は、Ctrl + H キーを押すことができます)。

2. デスクトップにファイルを **SiteCollections.csv** として保存します。

> [!TIP]
> このスクリプト ファイルまたはその他の.csvまたはWindows PowerShell スクリプト ファイルを使用する前に、余分な文字や非印刷文字がないことを確認することをお勧めします。 Word でファイルを開き、リボンで [段落] アイコンをクリックすると、印刷されない文字が表示されます。 印刷されない余分の文字がないようにしてください。 たとえば、ファイルの末尾の最後の文字の後ろに段落記号があってはなりません。

### <a name="run-the-windows-powershell-command"></a>Windows PowerShell コマンドの実行

1. Windows PowerShell プロンプトで、次のコマンドを入力またはコピーして貼り付け、Enter キーを押します。

   ```powershell
   Import-Csv C:\users\MyAlias\desktop\SiteCollections.csv | ForEach-Object {New-SPOSite -Owner $_.Owner -StorageQuota $_.StorageQuota -Url $_.Url -NoWait -ResourceQuota $_.ResourceQuota -Template $_.Template -TimeZoneID $_.TimeZoneID -Title $_.Name}
   ```

   *ここで、MyAlias は* ユーザーエイリアスと等しくなります。

2. WindowsPowerShell プロンプトが再度表示されるまで待機します。これには 1 - 2 分かかる場合があります。

3. Windows PowerShell プロンプトで、次のコマンドレットを入力するか、コピーして貼り付け、Enter キーを押します。

   ```powershell
   Get-SPOSite -Detailed | Format-Table -AutoSize
   ```

4. 一覧の新しいサイト コレクションに注目してください。 この CSV ファイルの例を使用すると、**TeamSite01、Blog01**、**Project01**、**Community01** というサイト コレクションが表示されます。

これで完了です。 作成した.csv ファイルと 1 つのWindows PowerShell コマンドを使用して、複数のサイト コレクションを作成しました。 これで、ユーザーを作成してこれらのサイトに割り当てる準備ができました。

## <a name="step-2-add-users-and-groups"></a>手順 2:ユーザーおよびグループの追加

ここでは、ユーザーを作成し、サイト コレクションのグループに追加します。次に、.csv ファイルを使用して、新しいグループとユーザーを一括アップロードします。

次の手順では、TeamSite01、Blog01、Project01、Community01 のサンプル サイトを引き続き使用します。

### <a name="create-csv-and-ps1-files"></a>.csv ファイルおよび .ps1 ファイルの作成

1. メモ帳を開き、次のテキスト ブロックを貼り付けます。

   ```powershell
   Site,Group,PermissionLevels
   https://tenant.sharepoint.com/sites/Community01,Contoso Project Leads,Full Control
   https://tenant.sharepoint.com/sites/Community01,Contoso Auditors,View Only
   https://tenant.sharepoint.com/sites/Community01,Contoso Designers,Design
   https://tenant.sharepoint.com/sites/TeamSite01,XT1000 Team Leads,Full Control
   https://tenant.sharepoint.com/sites/TeamSite01,XT1000 Advisors,Edit
   https://tenant.sharepoint.com/sites/Blog01,Contoso Blog Designers,Design
   https://tenant.sharepoint.com/sites/Blog01,Contoso Blog Editors,Edit
   https://tenant.sharepoint.com/sites/Project01,Project Alpha Approvers,Full Control
   ```

   *テナントがテナント* 名と等しい場合。

2. ファイルをデスクトップに **GroupsAndPermissions.csv** として保存します。

3. メモ帳の新しいインスタンスを開き、次のテキストのブロックを貼り付けます。

   ```powershell
   Group,LoginName,Site
   Contoso Project Leads,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
   Contoso Auditors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
   Contoso Designers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
   XT1000 Team Leads,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/TeamSite01
   XT1000 Advisors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/TeamSite01
   Contoso Blog Designers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Blog01
   Contoso Blog Editors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Blog01
   Project Alpha Approvers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Project01
   ```

   *テナントがテナント* 名と等しく、*ユーザー名* が既存のユーザーのユーザー名と等しい場合。

4. ファイルをデスクトップに **Users.csv** として保存します。

5. メモ帳の新しいインスタンスを開き、次のテキストのブロックを貼り付けます。

   ```powershell
   Import-Csv C:\users\MyAlias\desktop\GroupsAndPermissions.csv | ForEach-Object {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
   Import-Csv C:\users\MyAlias\desktop\Users.csv | where {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
   ```

   ここで、MyAlias は、現在ログオンしているユーザーのユーザー名と等しくなります。

6. ファイルをデスクトップに **UsersAndGroups.ps1** として保存します。 これは、単純な Windows PowerShell スクリプトです。

これで、UsersAndGroup.ps1 スクリプトを実行して複数のサイト コレクションにユーザーとグループを追加する準備ができました。

### <a name="run-usersandgroupsps1-script"></a>UsersAndGroups.ps1 スクリプトの実行

1. SharePoint Online 管理シェルに戻ります。

2. Windows PowerShell プロンプトで、次の行を入力するか、コピーして貼り付け、Enter キーを押します。

   ```powershell
   Set-ExecutionPolicy Bypass
   ```

3. 確認プロンプトで Y キーを押 **します**。

4. Windows PowerShell プロンプトで、次のコマンドを入力するか、コピーして貼り付け、Enter キーを押します。

   ```powershell
   c:\users\MyAlias\desktop\UsersAndGroups.ps1
   ```

   ここで *、MyAlias は* ユーザー名と等しくなります。

5. プロンプトが戻るまで待機してから、次に進みます。最初に、作成したとおりにグループが表示されます。次に、ユーザーを追加するたびに、グループの一覧が繰り返し表示されます。

## <a name="see-also"></a>関連項目

[SharePoint Online PowerShell に接続する](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

[PowerShell を使用して SharePoint Online サイト グループを管理する](manage-sharepoint-site-groups-with-powershell.md)

[PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)

[Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)
