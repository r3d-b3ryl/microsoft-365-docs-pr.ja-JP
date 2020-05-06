---
title: SharePoint Online のウイルス検出
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
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
description: ユーザーがアップロードするファイルで、SharePoint Online がウイルスを検出し、ユーザーがファイルをダウンロードまたは同期できないようにする方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6a47f52a30f90d7a19cc01dc9e14eb9b534ec244
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034952"
---
# <a name="virus-detection-in-sharepoint-online"></a><span data-ttu-id="40ae5-103">SharePoint Online のウイルス検出</span><span class="sxs-lookup"><span data-stu-id="40ae5-103">Virus detection in SharePoint Online</span></span>

<span data-ttu-id="40ae5-104">Microsoft 365 は、ユーザーが SharePoint Online にアップロードするファイルでウイルスを検出することによって、マルウェアから環境を保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="40ae5-104">Microsoft 365 can help protect your environment from malware by detecting viruses in files that users upload to SharePoint Online.</span></span> <span data-ttu-id="40ae5-105">アップロードされたファイルはウイルススキャンされることがあります。</span><span class="sxs-lookup"><span data-stu-id="40ae5-105">Files may be scanned for viruses after they are uploaded.</span></span> <span data-ttu-id="40ae5-106">ファイルで感染が見つかると、プロパティが設定されて、そのファイルをダウンロードしたり、同期したりできなくなります。</span><span class="sxs-lookup"><span data-stu-id="40ae5-106">If a file is found to be infected, a property is set so that users can't download or sync the file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="40ae5-107">SharePoint Online のウイルス対策機能は、ウイルスを封じ込める 1 つの方法にすぎません。</span><span class="sxs-lookup"><span data-stu-id="40ae5-107">These antivirus capabilities in SharePoint Online are a way to contain viruses.</span></span> <span data-ttu-id="40ae5-108">これだけで、お客様の環境がマルウェアから保護されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="40ae5-108">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="40ae5-109">すべてのお客様が、マルウェア対策保護を評価してさまざまなレイヤーに実装し、ベスト プラクティスを適用してエンタープライズ インフラストラクチャを保護することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="40ae5-109">We encourage all customers to assess and implement antimalware protection at various layers and apply best practices for securing your enterprise infrastructure.</span></span> <span data-ttu-id="40ae5-110">戦略とベストプラクティスの詳細については、「[セキュリティロードマップ](security-roadmap.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40ae5-110">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="40ae5-111">感染したファイルが SharePoint Online にアップロードされたとき</span><span class="sxs-lookup"><span data-stu-id="40ae5-111">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="40ae5-112">Microsoft 365 では、一般的なウイルス検出エンジンを使用しています。</span><span class="sxs-lookup"><span data-stu-id="40ae5-112">Microsoft 365 uses a common virus detection engine.</span></span> <span data-ttu-id="40ae5-113">エンジンは SharePoint Online 内で非同期に実行され、アップロードされたファイルをスキャンします。</span><span class="sxs-lookup"><span data-stu-id="40ae5-113">The engine runs asynchronously within SharePoint Online, and scans some files after they're uploaded.</span></span> <span data-ttu-id="40ae5-114">ヒューリスティックは、スキャンするファイルを決定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="40ae5-114">Heuristics are used to determine which files are scanned.</span></span> <span data-ttu-id="40ae5-115">ファイルでウイルスが見つかると、フラグが設定されて、そのファイルはダウンロードできなくなります。</span><span class="sxs-lookup"><span data-stu-id="40ae5-115">When a file is found to contain a virus, it's flagged so that it can't be downloaded again.</span></span> <span data-ttu-id="40ae5-116">2018年4月に、スキャンされたファイルの 25 MB の制限を削除しました。</span><span class="sxs-lookup"><span data-stu-id="40ae5-116">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="40ae5-117">動作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="40ae5-117">Here's what happens:</span></span>

1. <span data-ttu-id="40ae5-118">ユーザーがファイルを SharePoint Online にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="40ae5-118">A user uploads a file to SharePoint Online.</span></span>

2. <span data-ttu-id="40ae5-119">SharePoint Online は、ファイルがスキャンの条件を満たしているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="40ae5-119">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>

3. <span data-ttu-id="40ae5-120">ウイルス検出エンジンによってファイルがスキャンされます。</span><span class="sxs-lookup"><span data-stu-id="40ae5-120">The virus detection engine scans the file.</span></span>

4. <span data-ttu-id="40ae5-121">ウイルスが検出された場合、ウイルスエンジンはそのファイルが感染していることを示すプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="40ae5-121">If a virus is found, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="40ae5-122">ブラウザーを使って感染したファイルをダウンロードしようとしても、</span><span class="sxs-lookup"><span data-stu-id="40ae5-122">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="40ae5-123">ファイルが感染している場合、ユーザーはブラウザーを使用して SharePoint Online からファイルをダウンロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="40ae5-123">If a file is infected, users can't download the file from SharePoint Online by using the browser.</span></span>

<span data-ttu-id="40ae5-124">動作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="40ae5-124">Here's what happens:</span></span>

1. <span data-ttu-id="40ae5-125">Web ブラウザーを開き、感染したファイルを SharePoint Online からダウンロードしようとすると、</span><span class="sxs-lookup"><span data-stu-id="40ae5-125">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>

2. <span data-ttu-id="40ae5-126">ウイルスが検出されたという警告がユーザーに提示されます。</span><span class="sxs-lookup"><span data-stu-id="40ae5-126">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="40ae5-127">ユーザーには、ファイルをダウンロードして、独自のウイルス対策ソフトウェアを使用して駆除を試行するオプションが与えられます。</span><span class="sxs-lookup"><span data-stu-id="40ae5-127">The user is given the option to download the file and attempt to clean it using their own antivirus software.</span></span>

> [!NOTE]
> <span data-ttu-id="40ae5-128">SharePoint Online PowerShell の[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)コマンドレットで*DisallowInfectedFileDownload*パラメーターを使用して、ウイルス対策の警告ウィンドウであっても、感染したファイルをユーザーがダウンロードできないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="40ae5-128">You can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading an infected file, even in the anti-virus warning window.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="40ae5-129">感染したファイルを OneDrive の同期クライアントが同期しようとするとどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="40ae5-129">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="40ae5-p105">ファイルの同期を 新しい OneDrive の同期クライアント (OneDrive.exe) と前の OneDrive for Business 同期クライアント (Groove.exe) のどちらを使用して行っても、そのファイルにウイルスが含まれている場合には同期クライアントでダウンロードができません。ファイルを同期できないという通知が同期クライアントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="40ae5-p105">Whether users sync files with the new OneDrive sync client (OneDrive.exe) or the previous OneDrive for Business sync client (Groove.exe), if a file contains a virus, the sync client won't download it. The sync client will display a notification that the file can't be synced.</span></span>
