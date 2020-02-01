---
title: SharePoint Online のウイルス検出
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 01/14/2019
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Office 365 では、ユーザーが SharePoint Online にアップロードするファイルのウイルスが検出されるため、お客様の環境をマルウェアから保護できます。ファイルをアップロードすると、そのファイルがスキャンされてウイルスが検出されます。ファイルで感染が見つかると、プロパティが設定されて、そのファイルをダウンロードしたり、同期したりできなくなります。
ms.openlocfilehash: 1a41c5bb00e7169878206be2db076af0b0745e30
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598004"
---
# <a name="virus-detection-in-sharepoint-online"></a><span data-ttu-id="d874c-105">SharePoint Online のウイルス検出</span><span class="sxs-lookup"><span data-stu-id="d874c-105">Virus detection in SharePoint Online</span></span>

<span data-ttu-id="d874c-106">Office 365 では、ユーザーが SharePoint Online にアップロードするファイルのウイルスが検出されるため、お客様の環境をマルウェアから保護できます。</span><span class="sxs-lookup"><span data-stu-id="d874c-106">Office 365 can help protect your environment from malware by detecting viruses in files that users upload to SharePoint Online.</span></span> <span data-ttu-id="d874c-107">アップロードされたファイルはウイルススキャンされることがあります。</span><span class="sxs-lookup"><span data-stu-id="d874c-107">Files may be scanned for viruses after they are uploaded.</span></span> <span data-ttu-id="d874c-108">ファイルで感染が見つかると、プロパティが設定されて、そのファイルをダウンロードしたり、同期したりできなくなります。</span><span class="sxs-lookup"><span data-stu-id="d874c-108">If a file is found to be infected, a property is set so that users can't download or sync the file.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d874c-109">SharePoint Online のウイルス対策機能は、ウイルスを封じ込める 1 つの方法にすぎません。</span><span class="sxs-lookup"><span data-stu-id="d874c-109">These antivirus capabilities in SharePoint Online are a way to contain viruses.</span></span> <span data-ttu-id="d874c-110">これだけで、お客様の環境がマルウェアから保護されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="d874c-110">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="d874c-111">すべてのお客様が、マルウェア対策保護を評価してさまざまなレイヤーに実装し、ベスト プラクティスを適用してエンタープライズ インフラストラクチャを保護することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d874c-111">We encourage all customers to assess and implement antimalware protection at various layers and apply best practices for securing your enterprise infrastructure.</span></span> <span data-ttu-id="d874c-112">戦略とベストプラクティスの詳細については、「[セキュリティロードマップ](security-roadmap.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d874c-112">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span> 
  
## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="d874c-113">感染したファイルが SharePoint Online にアップロードされたとき</span><span class="sxs-lookup"><span data-stu-id="d874c-113">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="d874c-114">Office 365 では一般的なウイルス検出エンジンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d874c-114">Office 365 uses a common virus detection engine.</span></span> <span data-ttu-id="d874c-115">エンジンは SharePoint Online 内で非同期に実行され、アップロードされたファイルをスキャンします。</span><span class="sxs-lookup"><span data-stu-id="d874c-115">The engine runs asynchronously within SharePoint Online, and scans some files after they're uploaded.</span></span> <span data-ttu-id="d874c-116">ヒューリスティックは、スキャンするファイルを決定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d874c-116">Heuristics are used to determine which files are scanned.</span></span> <span data-ttu-id="d874c-117">ファイルでウイルスが見つかると、フラグが設定されて、そのファイルはダウンロードできなくなります。</span><span class="sxs-lookup"><span data-stu-id="d874c-117">When a file is found to contain a virus, it's flagged so that it can't be downloaded again.</span></span> <span data-ttu-id="d874c-118">2018年4月に、スキャンされたファイルの 25 MB の制限を削除しました。</span><span class="sxs-lookup"><span data-stu-id="d874c-118">In April 2018, we removed the 25 MB limit for scanned files.</span></span>
  
<span data-ttu-id="d874c-119">動作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d874c-119">Here's what happens:</span></span>
  
1. <span data-ttu-id="d874c-120">ユーザーがファイルを SharePoint Online にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="d874c-120">A user uploads a file to SharePoint Online.</span></span>

2. <span data-ttu-id="d874c-121">SharePoint Online は、ファイルがスキャンの条件を満たしているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="d874c-121">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>

3. <span data-ttu-id="d874c-122">ウイルス検出エンジンによってファイルがスキャンされます。</span><span class="sxs-lookup"><span data-stu-id="d874c-122">The virus detection engine scans the file.</span></span>
    
4. <span data-ttu-id="d874c-123">ウイルスが見つかると、ウイルス エンジンによって、感染していることを示すプロパティがファイルに設定されます。</span><span class="sxs-lookup"><span data-stu-id="d874c-123">If a virus is found, the virus engine sets a property on the file indicating that it is infected.</span></span>
    
## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="d874c-124">ブラウザーを使って感染したファイルをダウンロードしようとしても、</span><span class="sxs-lookup"><span data-stu-id="d874c-124">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="d874c-125">SharePoint Online からファイルをダウンロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d874c-125">If a file is infected with a virus, users can't download the file from SharePoint Online by using the browser.</span></span>
  
<span data-ttu-id="d874c-126">動作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d874c-126">Here's what happens:</span></span>
  
1. <span data-ttu-id="d874c-127">Web ブラウザーを開き、感染したファイルを SharePoint Online からダウンロードしようとすると、</span><span class="sxs-lookup"><span data-stu-id="d874c-127">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
    
2. <span data-ttu-id="d874c-128">ウイルスが検出されたという警告がユーザーに提示されます。</span><span class="sxs-lookup"><span data-stu-id="d874c-128">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="d874c-129">ユーザーには、ファイルをダウンロードして、独自のウイルスソフトウェアを使用して駆除を試行するオプションが与えられます。</span><span class="sxs-lookup"><span data-stu-id="d874c-129">The user is given the option to download the file and attempt to clean it using their own virus software.</span></span>

> [!NOTE]
> <span data-ttu-id="d874c-130">Set-spotenant コマンドレットを**DisallowInfectedFileDownload**パラメーターと共に使用して、ウイルス対策の警告ウィンドウであっても、検出されたファイルをダウンロードできないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="d874c-130">You can use the Set-SPOTenant cmdlet with the **DisallowInfectedFileDownload** parameter to not allow users to download a detected file, even in the anti-virus warning window.</span></span> <span data-ttu-id="d874c-131">「[DisallowInfectedFileDownload] (https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d874c-131">See [DisallowInfectedFileDownload] (https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>
    
## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="d874c-132">感染したファイルを OneDrive の同期クライアントが同期しようとするとどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="d874c-132">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="d874c-p107">ファイルの同期を 新しい OneDrive の同期クライアント (OneDrive.exe) と前の OneDrive for Business 同期クライアント (Groove.exe) のどちらを使用して行っても、そのファイルにウイルスが含まれている場合には同期クライアントでダウンロードができません。ファイルを同期できないという通知が同期クライアントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d874c-p107">Whether users sync files with the new OneDrive sync client (OneDrive.exe) or the previous OneDrive for Business sync client (Groove.exe), if a file contains a virus, the sync client won't download it. The sync client will display a notification that the file can't be synced.</span></span>
  

