---
title: PowerShell を使用して SharePoint Online サイト グループを管理する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/17/2019
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
description: この記事では、PowerShell for Microsoft 365 を使用して SharePoint Online サイト グループを管理する手順について説明します。
ms.openlocfilehash: bcc7a00a6114a6fa2ba8aa02520267bd03a0abf5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909540"
---
# <a name="manage-sharepoint-online-site-groups-with-powershell"></a><span data-ttu-id="ac470-103">PowerShell を使用して SharePoint Online サイト グループを管理する</span><span class="sxs-lookup"><span data-stu-id="ac470-103">Manage SharePoint Online site groups with PowerShell</span></span>

<span data-ttu-id="ac470-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="ac470-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="ac470-105">Microsoft 365 管理センターを使用することもできますが、PowerShell for Microsoft 365 を使用して SharePoint Online サイト グループを管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="ac470-105">Although you can use the Microsoft 365 admin center, you can also use PowerShell for Microsoft 365 to manage your SharePoint Online site groups.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ac470-106">はじめに</span><span class="sxs-lookup"><span data-stu-id="ac470-106">Before you begin</span></span>

<span data-ttu-id="ac470-107">この記事の手順では、SharePoint Online に接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac470-107">The procedures in this article require you to connect to SharePoint Online.</span></span> <span data-ttu-id="ac470-108">手順については、「[Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac470-108">For instructions, see [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

## <a name="view-sharepoint-online-with-powershell-for-microsoft-365"></a><span data-ttu-id="ac470-109">Microsoft 365 用 PowerShell を使用して SharePoint Online を表示する</span><span class="sxs-lookup"><span data-stu-id="ac470-109">View SharePoint Online with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="ac470-110">SharePoint Online 管理センターには、サイト グループを管理するための使いやすい方法があります。</span><span class="sxs-lookup"><span data-stu-id="ac470-110">The SharePoint Online admin center has some easy-to-use methods for managing site groups.</span></span> <span data-ttu-id="ac470-111">たとえば、サイトのグループとグループ メンバーを確認すると `https://litwareinc.sharepoint.com/sites/finance` します。</span><span class="sxs-lookup"><span data-stu-id="ac470-111">For example, suppose you want to look at the groups, and the group members, for the `https://litwareinc.sharepoint.com/sites/finance` site.</span></span> <span data-ttu-id="ac470-112">次の操作を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac470-112">Here's what you have to do to:</span></span>

1. <span data-ttu-id="ac470-113">SharePoint 管理センターで [アクティブ なサイト] **をクリック** し、サイトの URL をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac470-113">From the SharePoint admin center, click **Active sites**, and then click the URL of the site.</span></span>
2. <span data-ttu-id="ac470-114">サイト ページで、[設定]アイコン (ページの右上隅にあります) をクリックし、[サイトのアクセス許可]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="ac470-114">On the site page, click the **Settings** icon (located in the upper right-hand corner of the page), and then click **Site permissions**.</span></span>

<span data-ttu-id="ac470-115">参照する次のサイトでも、このプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="ac470-115">And then repeat the process for the next site you want to look at.</span></span>

<span data-ttu-id="ac470-116">PowerShell for Microsoft 365 のグループの一覧を取得するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="ac470-116">To get a list of the groups with PowerShell for Microsoft 365, you can use the following commands:</span></span>

```powershell
$siteURL = "https://litwareinc.sharepoint.com/sites/finance"
$x = Get-SPOSiteGroup -Site $siteURL
foreach ($y in $x)
    {
        Write-Host $y.Title -ForegroundColor "Yellow"
        Get-SPOSiteGroup -Site $siteURL -Group $y.Title | Select-Object -ExpandProperty Users
        Write-Host
    }
```

<span data-ttu-id="ac470-117">SharePoint Online 管理シェル コマンド プロンプトでこのコマンド セットを実行するには、次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="ac470-117">There are two ways to run this command set in the SharePoint Online Management Shell command prompt:</span></span>

- <span data-ttu-id="ac470-118">メモ帳 (または別のテキスト エディター) にコマンドをコピーし **、$siteURL** 変数の値を変更し、コマンドを選択し、SharePoint Online 管理シェル コマンド プロンプトに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="ac470-118">Copy the commands into Notepad (or another text editor), modify the value of the **$siteURL** variable, select the commands, and then paste them into the SharePoint Online Management Shell command prompt.</span></span> <span data-ttu-id="ac470-119">この操作を行うと、PowerShell はプロンプトで停止 **>>** します。</span><span class="sxs-lookup"><span data-stu-id="ac470-119">When you do, PowerShell will stop at a **>>** prompt.</span></span> <span data-ttu-id="ac470-120">Enter キーを押してコマンドを `foreach` 実行します。</span><span class="sxs-lookup"><span data-stu-id="ac470-120">Press Enter to execute the `foreach` command.</span></span><br/>
- <span data-ttu-id="ac470-121">コマンドをメモ帳 (または別のテキスト エディター) にコピーし、**$siteURL** 変数の値を変更してから、このテキスト ファイルを .ps1 という拡張子の付いた名前で適切なフォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="ac470-121">Copy the commands into Notepad (or another text editor), modify the value of the **$siteURL** variable, and then save this text file with a name and the .ps1 extension in a suitable folder.</span></span> <span data-ttu-id="ac470-122">次に、パスとファイル名を指定して、SharePoint Online 管理シェル コマンド プロンプトからスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="ac470-122">Next, run the script from the SharePoint Online Management Shell command prompt by specifying its path and file name.</span></span> <span data-ttu-id="ac470-123">コマンド例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ac470-123">Here is an example command:</span></span>

```powershell
C:\Scripts\SiteGroupsAndUsers.ps1
```

<span data-ttu-id="ac470-124">どちらの場合も、次のように表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="ac470-124">In both cases, you should see something similar to this:</span></span>

![SharePoint Online サイト グループ](../media/SPO-site-groups.png)

<span data-ttu-id="ac470-126">これらは、サイト用に作成されたグループすべて、およびそれらのグループに割り当てられている `https://litwareinc.sharepoint.com/sites/finance` すべてのユーザーです。</span><span class="sxs-lookup"><span data-stu-id="ac470-126">These are all the groups that have been created for the site `https://litwareinc.sharepoint.com/sites/finance`, and all the users assigned to those groups.</span></span> <span data-ttu-id="ac470-127">グループ名とメンバーの見分けがつくように、グループ名は黄色で表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac470-127">The group names are in yellow to help you separate group names from their members.</span></span>

<span data-ttu-id="ac470-128">別の例として、すべての SharePoint Online サイトのグループとすべてのグループ メンバーシップを一覧表示するコマンド セットを次に示します。</span><span class="sxs-lookup"><span data-stu-id="ac470-128">As another example, here is a command set that lists the groups, and all the group memberships, for all of your SharePoint Online sites.</span></span>

```powershell
$x = Get-SPOSite
foreach ($y in $x)
    {
        Write-Host $y.Url -ForegroundColor "Yellow"
        $z = Get-SPOSiteGroup -Site $y.Url
        foreach ($a in $z)
            {
                 $b = Get-SPOSiteGroup -Site $y.Url -Group $a.Title 
                 Write-Host $b.Title -ForegroundColor "Cyan"
                 $b | Select-Object -ExpandProperty Users
                 Write-Host
            }
    }
```
    
## <a name="see-also"></a><span data-ttu-id="ac470-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="ac470-129">See also</span></span>

[<span data-ttu-id="ac470-130">SharePoint Online PowerShell に接続する</span><span class="sxs-lookup"><span data-stu-id="ac470-130">Connect to SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[<span data-ttu-id="ac470-131">PowerShell を使用して SharePoint Online サイトを作成し、ユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="ac470-131">Create SharePoint Online sites and add users with PowerShell</span></span>](create-sharepoint-sites-and-add-users-with-powershell.md)

[<span data-ttu-id="ac470-132">PowerShell を使用して SharePoint Online のユーザーとグループを管理する</span><span class="sxs-lookup"><span data-stu-id="ac470-132">Manage SharePoint Online users and groups with PowerShell</span></span>](manage-sharepoint-users-and-groups-with-powershell.md)

[<span data-ttu-id="ac470-133">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="ac470-133">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="ac470-134">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="ac470-134">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)