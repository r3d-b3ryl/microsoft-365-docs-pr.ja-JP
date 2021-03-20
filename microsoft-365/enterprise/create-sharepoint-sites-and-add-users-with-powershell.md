---
title: PowerShell を使用して SharePoint Online サイトを作成し、ユーザーを追加する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
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
ms.openlocfilehash: eb6c2817c8760ca222da8a7c2b14cbfcda4eb4b8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907620"
---
# <a name="create-sharepoint-online-sites-and-add-users-with-powershell"></a><span data-ttu-id="12862-103">PowerShell を使用して SharePoint Online サイトを作成し、ユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="12862-103">Create SharePoint Online sites and add users with PowerShell</span></span>

<span data-ttu-id="12862-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="12862-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="12862-105">PowerShell for Microsoft 365 を使用して SharePoint Online サイトを作成し、ユーザーを追加する場合、Microsoft 365 管理センターで実行できるよりもはるかに高速かつ繰り返しタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="12862-105">When you use PowerShell for Microsoft 365 to create SharePoint Online sites and add users, you can quickly and repeatedly perform tasks much faster than you can in the Microsoft 365 admin center.</span></span> <span data-ttu-id="12862-106">Microsoft 365 管理センターでは実行できないタスクを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="12862-106">You can also perform tasks that are not possible to perform in the Microsoft 365 admin center.</span></span> 

## <a name="connect-to-sharepoint-online"></a><span data-ttu-id="12862-107">SharePoint Online に接続する</span><span class="sxs-lookup"><span data-stu-id="12862-107">Connect to SharePoint Online</span></span>

<span data-ttu-id="12862-108">このトピックの手順では、SharePoint Online に接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12862-108">The procedures in this topic require you to connect to SharePoint Online.</span></span> <span data-ttu-id="12862-109">手順については [、「Connect to SharePoint Online PowerShell」を参照してください。](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="12862-109">For instructions, see [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span></span>

## <a name="step-1-create-new-site-collections-using-powershell"></a><span data-ttu-id="12862-110">手順 1: PowerShell を使用して新しいサイト コレクションを作成する</span><span class="sxs-lookup"><span data-stu-id="12862-110">Step 1: Create new site collections using PowerShell</span></span>

<span data-ttu-id="12862-111">PowerShell と、提供されているサンプル コードとメモ帳を使用して作成する .csv ファイルを使用して、複数のサイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="12862-111">Create multiple sites using PowerShell and a .csv file that you create using the example code provided and Notepad.</span></span> <span data-ttu-id="12862-112">この手順では、角かっこで示されているプレースホルダー情報を、独自のサイトおよびテナント固有の情報に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="12862-112">For this procedure, you’ll be replacing the placeholder information shown in brackets with your own site- and tenant-specific information.</span></span> <span data-ttu-id="12862-113">このプロセスでは、1 つのファイルを作成し、そのファイルを使用する 1 つの PowerShell コマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="12862-113">This process lets you create a single file and run a single PowerShell command that uses that file.</span></span> <span data-ttu-id="12862-114">これにより、繰り返し可能な操作と移植可能な操作の両方が実行され、長いコマンドを SharePoint Online 管理シェルに入力した場合に発生するエラーが多くなくなってくる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="12862-114">This makes the actions taken both repeatable and portable and eliminates many, if not all, errors that can come from typing long commands into the SharePoint Online Management Shell.</span></span> <span data-ttu-id="12862-115">この手順には 2 つの部分があります。</span><span class="sxs-lookup"><span data-stu-id="12862-115">There are two parts to this procedure.</span></span> <span data-ttu-id="12862-116">最初に .csv ファイルを作成し、その .csv ファイルを PowerShell を使用して参照します。その内容を使用してサイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="12862-116">First you’ll create a .csv file, and then you’ll reference that .csv file using PowerShell, which will use its contents to create the sites.</span></span>

<span data-ttu-id="12862-117">PowerShell コマンドレットは、.csv ファイルをインポートし、ファイルの最初の行を列ヘッダーとして読み取る中かっこ内のループにパイプ処理します。</span><span class="sxs-lookup"><span data-stu-id="12862-117">The PowerShell cmdlet imports the .csv file and pipes it to a loop inside the curly brackets that reads the first line of the file as column headers.</span></span> <span data-ttu-id="12862-118">PowerShell コマンドレットは、残りのレコードを反復処理し、レコードごとに新しいサイト コレクションを作成し、列ヘッダーに従ってサイト コレクションのプロパティを割り当てします。</span><span class="sxs-lookup"><span data-stu-id="12862-118">The PowerShell cmdlet then iterates through the remaining records, creates a new site collection for each record, and assigns properties of the site collection according to the column headers.</span></span>

### <a name="create-a-csv-file"></a><span data-ttu-id="12862-119">.csv ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="12862-119">Create a .csv file</span></span>

> [!NOTE]
> <span data-ttu-id="12862-120">リソース クォータ パラメーターは、従来のサイトでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="12862-120">The resource quota parameter works only on classic sites.</span></span> <span data-ttu-id="12862-121">モダン サイトでこのパラメーターを使用すると、廃止されたという警告メッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="12862-121">If you use this parameter on a modern site, you may receive a warning message that it has been deprecated.</span></span> 

1. <span data-ttu-id="12862-122">メモ帳を開き、次のテキスト ブロックを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="12862-122">Open Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Owner,StorageQuota,Url,ResourceQuota,Template,TimeZoneID,Name
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/TeamSite01,25,EHS#1,10,Contoso Team Site
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/Blog01,25,BLOG#0,10,Contoso Blog
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Project01,25,PROJECTSITE#0,10,Project Alpha
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Community01,25,COMMUNITY#0,10,Community Site
```
<br/><span data-ttu-id="12862-123">テナント *は* テナントの名前であり、所有者はプライマリサイト コレクション管理者の役割を付与するテナントのユーザーのユーザー名です。</span><span class="sxs-lookup"><span data-stu-id="12862-123">Where *tenant* is the name of your tenant, and *owner* is the user name of the user on your tenant to whom you want to grant the role of primary site collection administrator.</span></span><br/><span data-ttu-id="12862-124">(メモ帳を使用して一括置換を高速に行う場合は、Ctrl + H キーを押します)。</span><span class="sxs-lookup"><span data-stu-id="12862-124">(You can press Ctrl+H when you use Notepad to bulk replace faster.)</span></span><br/>

2. <span data-ttu-id="12862-125">デスクトップにファイルを [ファイル名] **SiteCollections.csv。**</span><span class="sxs-lookup"><span data-stu-id="12862-125">Save the file on your desktop as **SiteCollections.csv**.</span></span><br/>

> [!TIP]
> <span data-ttu-id="12862-126">このスクリプト ファイルまたは他の .csv または Windows PowerShell スクリプト ファイルを使用する前に、余分な文字や印刷されていない文字が含まれるのを確認してください。</span><span class="sxs-lookup"><span data-stu-id="12862-126">Before you use this or any other .csv or Windows PowerShell script file, it's a good practice to make sure that there are no extraneous or nonprinting characters.</span></span> <span data-ttu-id="12862-127">Word でファイルを開き、リボンで [段落] アイコンをクリックすると、印刷されない文字が表示されます。</span><span class="sxs-lookup"><span data-stu-id="12862-127">Open the file in Word, and in the ribbon, click the paragraph icon to show nonprinting characters.</span></span> <span data-ttu-id="12862-128">印刷されない余分の文字がないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="12862-128">There should be no extraneous nonprinting characters.</span></span> <span data-ttu-id="12862-129">たとえば、ファイルの末尾の最後の文字の後ろに段落記号があってはなりません。</span><span class="sxs-lookup"><span data-stu-id="12862-129">For example, there should be no paragraph marks beyond the final one at the end of the file.</span></span>

### <a name="run-the-windows-powershell-command"></a><span data-ttu-id="12862-130">Windows PowerShell コマンドの実行</span><span class="sxs-lookup"><span data-stu-id="12862-130">Run the Windows PowerShell command</span></span>

1. <span data-ttu-id="12862-131">プロンプトにWindows PowerShell、次のコマンドを入力またはコピーして貼り付け、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="12862-131">At the Windows PowerShell prompt, type or copy and paste the following command, and press Enter:</span></span><br/>
```powershell
Import-Csv C:\users\MyAlias\desktop\SiteCollections.csv | ForEach-Object {New-SPOSite -Owner $_.Owner -StorageQuota $_.StorageQuota -Url $_.Url -NoWait -ResourceQuota $_.ResourceQuota -Template $_.Template -TimeZoneID $_.TimeZoneID -Title $_.Name}
```
<br/><span data-ttu-id="12862-132">*MyAlias がユーザー* エイリアスと等しい場合。</span><span class="sxs-lookup"><span data-stu-id="12862-132">Where *MyAlias* equals your user alias.</span></span><br/>

2. <span data-ttu-id="12862-p107">WindowsPowerShell プロンプトが再度表示されるまで待機します。これには 1 - 2 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="12862-p107">Wait for the Windows PowerShell prompt to reappear. It might take a minute or two.</span></span><br/>

3. <span data-ttu-id="12862-135">Windows PowerShell プロンプトで、次のコマンドレットを入力するか、コピーして貼り付け、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="12862-135">At the Windows PowerShell prompt, type or copy and paste the following cmdlet, and press Enter:</span></span><br/>

```powershell
Get-SPOSite -Detailed | Format-Table -AutoSize
```
<br/>

4. <span data-ttu-id="12862-136">リスト内の新しいサイト コレクションに注意してください。</span><span class="sxs-lookup"><span data-stu-id="12862-136">Note the new site collections in the list.</span></span> <span data-ttu-id="12862-137">この例の CSV ファイルを使用すると、次のサイト コレクションが表示されます **。TeamSite01** **、Blog01、Project01、\*\*\*\*および Community01** </span><span class="sxs-lookup"><span data-stu-id="12862-137">Using our example CSV file, you would see the following site collections: **TeamSite01**, **Blog01**, **Project01**, and **Community01**</span></span>

<span data-ttu-id="12862-138">これで完了です。</span><span class="sxs-lookup"><span data-stu-id="12862-138">That’s it.</span></span> <span data-ttu-id="12862-139">作成した .csv ファイルと 1 つのコマンドを使用して、複数のサイト コレクションWindows PowerShellしました。</span><span class="sxs-lookup"><span data-stu-id="12862-139">You’ve created multiple site collections using the .csv file you created and a single Windows PowerShell command.</span></span> <span data-ttu-id="12862-140">これで、ユーザーを作成してこれらのサイトに割り当てる準備ができました。</span><span class="sxs-lookup"><span data-stu-id="12862-140">You’re now ready to create and assign users to these sites.</span></span>

## <a name="step-2-add-users-and-groups"></a><span data-ttu-id="12862-141">手順 2:ユーザーおよびグループの追加</span><span class="sxs-lookup"><span data-stu-id="12862-141">Step 2: Add users and groups</span></span>

<span data-ttu-id="12862-p110">ここでは、ユーザーを作成し、サイト コレクションのグループに追加します。次に、.csv ファイルを使用して、新しいグループとユーザーを一括アップロードします。</span><span class="sxs-lookup"><span data-stu-id="12862-p110">Now you’re going to create users and add them to a site collection group. You will then use a .csv file to bulk upload new groups and users.</span></span>

<span data-ttu-id="12862-144">次の手順では、例のサイト TeamSite01、Blog01、Project01、および Community01 を引き続き使用します。</span><span class="sxs-lookup"><span data-stu-id="12862-144">The following procedures continue using the example sites TeamSite01, Blog01, Project01, and Community01.</span></span>

### <a name="create-csv-and-ps1-files"></a><span data-ttu-id="12862-145">.csv ファイルおよび .ps1 ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="12862-145">Create .csv and .ps1 files</span></span>

1. <span data-ttu-id="12862-146">メモ帳を開き、次のテキスト ブロックを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="12862-146">Open Notepad, and paste the following text block into it:</span></span><br/>

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
<br/><span data-ttu-id="12862-147">テナント *がテナント* 名と等しい場所。</span><span class="sxs-lookup"><span data-stu-id="12862-147">Where *tenant* equals your tenant name.</span></span><br/>

2. <span data-ttu-id="12862-148">ファイルをデスクトップに保存します **GroupsAndPermissions.csv。**</span><span class="sxs-lookup"><span data-stu-id="12862-148">Save the file to your desktop as **GroupsAndPermissions.csv**.</span></span><br/>

3. <span data-ttu-id="12862-149">メモ帳の新しいインスタンスを開き、次のテキストのブロックを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="12862-149">Open a new instance of Notepad, and paste the following text block into it:</span></span><br/>

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
<br/><span data-ttu-id="12862-150">テナント *がテナント* 名と等しく、ユーザー *名が* 既存のユーザーのユーザー名と等しい場合。</span><span class="sxs-lookup"><span data-stu-id="12862-150">Where *tenant* equals your tenant name, and *username* equals the user name of an existing user.</span></span><br/>

4. <span data-ttu-id="12862-151">ファイルをデスクトップに保存します **Users.csv。**</span><span class="sxs-lookup"><span data-stu-id="12862-151">Save the file to your desktop as **Users.csv**.</span></span><br/>

5. <span data-ttu-id="12862-152">メモ帳の新しいインスタンスを開き、次のテキストのブロックを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="12862-152">Open a new instance of Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Import-Csv C:\users\MyAlias\desktop\GroupsAndPermissions.csv | ForEach-Object {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\users\MyAlias\desktop\Users.csv | where {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```
<br/><span data-ttu-id="12862-153">ここで、MyAlias は現在ログオンしているユーザーのユーザー名と等しくなります。</span><span class="sxs-lookup"><span data-stu-id="12862-153">Where MyAlias equals the user name of the user that is currently logged on.</span></span><br/>

6. <span data-ttu-id="12862-154">ファイルをデスクトップに保存します **UsersAndGroups.ps1。**</span><span class="sxs-lookup"><span data-stu-id="12862-154">Save the file to your desktop as **UsersAndGroups.ps1**.</span></span> <span data-ttu-id="12862-155">これは、単純な Windows PowerShell スクリプトです。</span><span class="sxs-lookup"><span data-stu-id="12862-155">This is a simple Windows PowerShell script.</span></span>

<span data-ttu-id="12862-156">これで、UsersAndGroup.ps1 スクリプトを実行して複数のサイト コレクションにユーザーとグループを追加する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="12862-156">You’re now ready to run the UsersAndGroup.ps1 script to add users and groups to multiple site collections.</span></span>

### <a name="run-usersandgroupsps1-script"></a><span data-ttu-id="12862-157">UsersAndGroups.ps1 スクリプトの実行</span><span class="sxs-lookup"><span data-stu-id="12862-157">Run UsersAndGroups.ps1 script</span></span>

1. <span data-ttu-id="12862-158">SharePoint Online 管理シェルに戻ります。</span><span class="sxs-lookup"><span data-stu-id="12862-158">Return to the SharePoint Online Management Shell.</span></span><br/>
2. <span data-ttu-id="12862-159">Windows PowerShell プロンプトで、次の行を入力するか、コピーして貼り付け、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="12862-159">At the Windows PowerShell prompt, type or copy and paste the following line, and press Enter:</span></span><br/>
```powershell
Set-ExecutionPolicy Bypass
```
<br/>

3. <span data-ttu-id="12862-160">確認プロンプトで **、Y キーを押します**。</span><span class="sxs-lookup"><span data-stu-id="12862-160">At the confirmation prompt, press **Y**.</span></span><br/>

4. <span data-ttu-id="12862-161">Windows PowerShell プロンプトで、次のコマンドを入力するか、コピーして貼り付け、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="12862-161">At the Windows PowerShell prompt, type or copy and paste the following, and press Enter:</span></span><br/>

```powershell
c:\users\MyAlias\desktop\UsersAndGroups.ps1
```
<br/><span data-ttu-id="12862-162">*MyAlias がユーザー* 名と等しい場所。</span><span class="sxs-lookup"><span data-stu-id="12862-162">Where *MyAlias* equals your user name.</span></span><br/>

5. <span data-ttu-id="12862-p112">プロンプトが戻るまで待機してから、次に進みます。最初に、作成したとおりにグループが表示されます。次に、ユーザーを追加するたびに、グループの一覧が繰り返し表示されます。</span><span class="sxs-lookup"><span data-stu-id="12862-p112">Wait for the prompt to return before moving on. You will first see the groups appear as they are created. Then you will see the group list repeated as users are added.</span></span>

## <a name="see-also"></a><span data-ttu-id="12862-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="12862-166">See also</span></span>

[<span data-ttu-id="12862-167">SharePoint Online PowerShell に接続する</span><span class="sxs-lookup"><span data-stu-id="12862-167">Connect to SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[<span data-ttu-id="12862-168">PowerShell を使用して SharePoint Online サイト グループを管理する</span><span class="sxs-lookup"><span data-stu-id="12862-168">Manage SharePoint Online site groups with PowerShell</span></span>](manage-sharepoint-site-groups-with-powershell.md)

[<span data-ttu-id="12862-169">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="12862-169">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="12862-170">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="12862-170">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)