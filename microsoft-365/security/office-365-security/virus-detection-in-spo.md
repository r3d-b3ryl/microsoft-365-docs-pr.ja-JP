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
ms.openlocfilehash: 60d696769ea402e6e2d0e52a1f6633e7962b8329
ms.sourcegitcommit: f2275d2fbc17a8b5b5da723c7353d3f36c6fb2a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "45029610"
---
# <a name="virus-detection-in-sharepoint-online"></a><span data-ttu-id="51e0e-103">SharePoint Online のウイルス検出</span><span class="sxs-lookup"><span data-stu-id="51e0e-103">Virus detection in SharePoint Online</span></span>

<span data-ttu-id="51e0e-104">Microsoft 365 は、ユーザーが SharePoint Online にアップロードするファイルでウイルスを検出することによって、マルウェアから環境を保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="51e0e-104">Microsoft 365 can help protect your environment from malware by detecting viruses in files that users upload to SharePoint Online.</span></span> <span data-ttu-id="51e0e-105">アップロードされたファイルはウイルススキャンされることがあります。</span><span class="sxs-lookup"><span data-stu-id="51e0e-105">Files may be scanned for viruses after they are uploaded.</span></span> <span data-ttu-id="51e0e-106">ファイルで感染が見つかると、プロパティが設定されて、そのファイルをダウンロードしたり、同期したりできなくなります。</span><span class="sxs-lookup"><span data-stu-id="51e0e-106">If a file is found to be infected, a property is set so that users can't download or sync the file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="51e0e-107">SharePoint Online のウイルス対策機能は、ウイルスを封じ込める 1 つの方法にすぎません。</span><span class="sxs-lookup"><span data-stu-id="51e0e-107">These antivirus capabilities in SharePoint Online are a way to contain viruses.</span></span> <span data-ttu-id="51e0e-108">これだけで、お客様の環境がマルウェアから保護されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="51e0e-108">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="51e0e-109">すべてのお客様が、マルウェア対策保護を評価してさまざまなレイヤーに実装し、ベスト プラクティスを適用してエンタープライズ インフラストラクチャを保護することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="51e0e-109">We encourage all customers to assess and implement antimalware protection at various layers and apply best practices for securing your enterprise infrastructure.</span></span> <span data-ttu-id="51e0e-110">戦略とベストプラクティスの詳細については、「[セキュリティロードマップ](security-roadmap.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51e0e-110">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="51e0e-111">感染したファイルが SharePoint Online にアップロードされたとき</span><span class="sxs-lookup"><span data-stu-id="51e0e-111">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="51e0e-112">Microsoft 365 では、一般的なウイルス検出エンジンを使用しています。</span><span class="sxs-lookup"><span data-stu-id="51e0e-112">Microsoft 365 uses a common virus detection engine.</span></span> <span data-ttu-id="51e0e-113">エンジンは SharePoint Online 内で非同期に実行され、アップロードされたファイルをスキャンします。</span><span class="sxs-lookup"><span data-stu-id="51e0e-113">The engine runs asynchronously within SharePoint Online, and scans some files after they're uploaded.</span></span> <span data-ttu-id="51e0e-114">ヒューリスティックは、スキャンするファイルを決定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="51e0e-114">Heuristics are used to determine which files are scanned.</span></span> <span data-ttu-id="51e0e-115">ファイルでウイルスが見つかると、フラグが設定されて、そのファイルはダウンロードできなくなります。</span><span class="sxs-lookup"><span data-stu-id="51e0e-115">When a file is found to contain a virus, it's flagged so that it can't be downloaded again.</span></span> <span data-ttu-id="51e0e-116">2018年4月に、スキャンされたファイルの 25 MB の制限を削除しました。</span><span class="sxs-lookup"><span data-stu-id="51e0e-116">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="51e0e-117">動作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="51e0e-117">Here's what happens:</span></span>

1. <span data-ttu-id="51e0e-118">ユーザーがファイルを SharePoint Online にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="51e0e-118">A user uploads a file to SharePoint Online.</span></span>

2. <span data-ttu-id="51e0e-119">SharePoint Online は、ファイルがスキャンの条件を満たしているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="51e0e-119">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>

3. <span data-ttu-id="51e0e-120">ウイルス検出エンジンによってファイルがスキャンされます。</span><span class="sxs-lookup"><span data-stu-id="51e0e-120">The virus detection engine scans the file.</span></span>

4. <span data-ttu-id="51e0e-121">ウイルスが検出された場合、ウイルスエンジンはそのファイルが感染していることを示すプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="51e0e-121">If a virus is found, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="51e0e-122">ブラウザーを使って感染したファイルをダウンロードしようとしても、</span><span class="sxs-lookup"><span data-stu-id="51e0e-122">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="51e0e-123">ファイルが感染している場合、ユーザーはブラウザーを使用して SharePoint Online からファイルをダウンロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="51e0e-123">If a file is infected, users can't download the file from SharePoint Online by using the browser.</span></span>

<span data-ttu-id="51e0e-124">動作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="51e0e-124">Here's what happens:</span></span>

1. <span data-ttu-id="51e0e-125">Web ブラウザーを開き、感染したファイルを SharePoint Online からダウンロードしようとすると、</span><span class="sxs-lookup"><span data-stu-id="51e0e-125">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>

2. <span data-ttu-id="51e0e-126">ウイルスが検出されたという警告がユーザーに提示されます。</span><span class="sxs-lookup"><span data-stu-id="51e0e-126">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="51e0e-127">ユーザーには、ファイルをダウンロードして、独自のウイルス対策ソフトウェアを使用して駆除を試行するオプションが与えられます。</span><span class="sxs-lookup"><span data-stu-id="51e0e-127">The user is given the option to download the file and attempt to clean it using their own antivirus software.</span></span>

> [!NOTE]
> <span data-ttu-id="51e0e-128">SharePoint Online PowerShell の[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)コマンドレットで*DisallowInfectedFileDownload*パラメーターを使用して、ウイルス対策の警告ウィンドウであっても、感染したファイルをユーザーがダウンロードできないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="51e0e-128">You can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading an infected file, even in the anti-virus warning window.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="51e0e-129">感染したファイルを OneDrive の同期クライアントが同期しようとするとどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="51e0e-129">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="51e0e-p105">ファイルの同期を 新しい OneDrive の同期クライアント (OneDrive.exe) と前の OneDrive for Business 同期クライアント (Groove.exe) のどちらを使用して行っても、そのファイルにウイルスが含まれている場合には同期クライアントでダウンロードができません。ファイルを同期できないという通知が同期クライアントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="51e0e-p105">Whether users sync files with the new OneDrive sync client (OneDrive.exe) or the previous OneDrive for Business sync client (Groove.exe), if a file contains a virus, the sync client won't download it. The sync client will display a notification that the file can't be synced.</span></span>

## <a name="more-information"></a><span data-ttu-id="51e0e-132">詳細情報</span><span class="sxs-lookup"><span data-stu-id="51e0e-132">More information</span></span>

<span data-ttu-id="51e0e-133">SharePoint Online のウイルス対策を構成する方法の詳細については、「[脅威からの保護](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide#requirements)」および「 [sharepoint、OneDrive、Microsoft TEAMS 用の ATP を有効](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams?view=o365-worldwide)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51e0e-133">See [Protect against threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide#requirements) and [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams?view=o365-worldwide) for more information on how to configure SharePoint Online antivirus.</span></span>


