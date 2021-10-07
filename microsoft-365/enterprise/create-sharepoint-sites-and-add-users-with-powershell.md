---
title: PowerShell を使用して SharePoint Online サイトを作成し、ユーザーを追加する
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: hub-page
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
description: '概要: PowerShell を使用して、オンライン サイトSharePoint新しいサイトを作成し、それらのサイトにユーザーとグループを追加します。'
ms.openlocfilehash: 76411621c0c313a31e4c92417b4472d6fd34ddac
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60152684"
---
# <a name="create-sharepoint-online-sites-and-add-users-with-powershell"></a>PowerShell を使用して SharePoint Online サイトを作成し、ユーザーを追加する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

powerShell を Microsoft 365 で使用して SharePoint Online サイトを作成し、ユーザーを追加すると、Microsoft 365 管理センター で実行できるよりもはるかに高速で繰り返しタスクを実行できます。 また、アプリケーションで実行できないタスクを実行Microsoft 365 管理センター。

## <a name="connect-to-sharepoint-online"></a>SharePoint Online に接続する

このトピックの手順では、オンラインのユーザーに接続SharePointします。 手順については、「オンライン[PowerShell ConnectをSharePointする」を参照してください。](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

## <a name="step-1-create-new-site-collections-using-powershell"></a>手順 1: PowerShell を使用して新しいサイト コレクションを作成する

PowerShell を使用して複数のサイトを作成し、.csvコード例を使用して作成するファイルを作成メモ帳。 この手順では、角かっこで示されているプレースホルダー情報を、独自のサイトおよびテナント固有の情報に置き換える必要があります。 このプロセスでは、1 つのファイルを作成し、そのファイルを使用する 1 つの PowerShell コマンドを実行できます。 これにより、繰り返し可能な操作と移植可能な操作の両方が実行され、長いコマンドを SharePoint Online 管理シェルに入力した場合に発生するエラーの多くが排除されます。 この手順には 2 つの部分があります。 最初に、.csv ファイルを作成し、その .csv ファイルを PowerShell を使用して参照し、その内容を使用してサイトを作成します。

PowerShell コマンドレットは、.csv ファイルをインポートし、ファイルの最初の行を列ヘッダーとして読み取る中かっこ内のループにパイプ処理します。 PowerShell コマンドレットは、残りのレコードを反復処理し、レコードごとに新しいサイト コレクションを作成し、列ヘッダーに従ってサイト コレクションのプロパティを割り当てします。

### <a name="create-a-csv-file"></a>.csv ファイルの作成

> [!NOTE]
> リソース クォータ パラメーターは、従来のサイトでのみ機能します。 モダン サイトでこのパラメーターを使用すると、廃止されたという警告メッセージが表示されることがあります。

1. メモ帳を開き、次のテキスト ブロックを貼り付けます。

   ```powershell
   Owner,StorageQuota,Url,ResourceQuota,Template,TimeZoneID,Name
   owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/TeamSite01,25,EHS#1,10,Contoso Team Site
   owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/Blog01,25,BLOG#0,10,Contoso Blog
   owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Project01,25,PROJECTSITE#0,10,Project Alpha
   owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Community01,25,COMMUNITY#0,10,Community Site
   ```

   テナント *は* テナントの名前であり、所有者はプライマリサイト コレクション管理者の役割を付与するテナントのユーザーのユーザー名です。

   (Ctrl キーを押しながら H キーを押すと、メモ帳置き換えの速度が速くなります)。

2. デスクトップにファイルを [ファイル名] **SiteCollections.csv。**

> [!TIP]
> このスクリプト ファイルまたは他の .csv または Windows PowerShell スクリプト ファイルを使用する前に、余分な文字や印刷されていない文字が含まれるのを確認してください。 Word でファイルを開き、リボンで [段落] アイコンをクリックすると、印刷されない文字が表示されます。 印刷されない余分の文字がないようにしてください。 たとえば、ファイルの末尾の最後の文字の後ろに段落記号があってはなりません。

### <a name="run-the-windows-powershell-command"></a>Windows PowerShell コマンドの実行

1. プロンプトにWindows PowerShell、次のコマンドを入力またはコピーして貼り付け、Enter キーを押します。

   ```powershell
   Import-Csv C:\users\MyAlias\desktop\SiteCollections.csv | ForEach-Object {New-SPOSite -Owner $_.Owner -StorageQuota $_.StorageQuota -Url $_.Url -NoWait -ResourceQuota $_.ResourceQuota -Template $_.Template -TimeZoneID $_.TimeZoneID -Title $_.Name}
   ```

   *MyAlias がユーザー* エイリアスと等しい場合。

2. WindowsPowerShell プロンプトが再度表示されるまで待機します。これには 1 - 2 分かかる場合があります。

3. Windows PowerShell プロンプトで、次のコマンドレットを入力するか、コピーして貼り付け、Enter キーを押します。

   ```powershell
   Get-SPOSite -Detailed | Format-Table -AutoSize
   ```

4. リスト内の新しいサイト コレクションに注意してください。 この例の CSV ファイルを使用すると、次のサイト コレクションが表示されます **。TeamSite01** **、Blog01、Project01、****および Community01** 

これで完了です。 作成したファイルファイルと 1 つの .csvコマンドを使用して、複数のサイト コレクションWindows PowerShellしました。 これで、ユーザーを作成してこれらのサイトに割り当てる準備ができました。

## <a name="step-2-add-users-and-groups"></a>手順 2:ユーザーおよびグループの追加

ここでは、ユーザーを作成し、サイト コレクションのグループに追加します。次に、.csv ファイルを使用して、新しいグループとユーザーを一括アップロードします。

次の手順では、例のサイト TeamSite01、Blog01、Project01、および Community01 を引き続き使用します。

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

   テナント *がテナント* 名と等しい場所。

2. ファイルをデスクトップに保存します **GroupsAndPermissions.csv。**

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

   テナント *がテナント* 名と等しく、ユーザー *名が* 既存のユーザーのユーザー名と等しい場合。

4. ファイルをデスクトップに保存します **Users.csv。**

5. メモ帳の新しいインスタンスを開き、次のテキストのブロックを貼り付けます。

   ```powershell
   Import-Csv C:\users\MyAlias\desktop\GroupsAndPermissions.csv | ForEach-Object {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
   Import-Csv C:\users\MyAlias\desktop\Users.csv | where {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
   ```

   ここで、MyAlias は現在ログオンしているユーザーのユーザー名と等しくなります。

6. ファイルをデスクトップに保存します **UsersAndGroups.ps1。** これは、単純な Windows PowerShell スクリプトです。

これで、UsersAndGroup.ps1 スクリプトを実行して複数のサイト コレクションにユーザーとグループを追加する準備ができました。

### <a name="run-usersandgroupsps1-script"></a>UsersAndGroups.ps1 スクリプトの実行

1. SharePoint Online 管理シェルに戻ります。

2. Windows PowerShell プロンプトで、次の行を入力するか、コピーして貼り付け、Enter キーを押します。

   ```powershell
   Set-ExecutionPolicy Bypass
   ```

3. 確認プロンプトで **、Y キーを押します**。

4. Windows PowerShell プロンプトで、次のコマンドを入力するか、コピーして貼り付け、Enter キーを押します。

   ```powershell
   c:\users\MyAlias\desktop\UsersAndGroups.ps1
   ```

   *MyAlias がユーザー* 名と等しい場所。

5. プロンプトが戻るまで待機してから、次に進みます。最初に、作成したとおりにグループが表示されます。次に、ユーザーを追加するたびに、グループの一覧が繰り返し表示されます。

## <a name="see-also"></a>関連項目

[SharePoint Online PowerShell に接続する](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

[PowerShell を使用して SharePoint Online サイト グループを管理する](manage-sharepoint-site-groups-with-powershell.md)

[PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)

[Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)
