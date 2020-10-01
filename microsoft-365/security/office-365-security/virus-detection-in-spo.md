---
title: SharePoint Online、OneDrive、Microsoft Teams の組み込みのウイルス対策
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
ms.openlocfilehash: 38d6111fe665e0af79cbd93f534b1058881ff76c
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327989"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a><span data-ttu-id="632ff-103">SharePoint Online、OneDrive、Microsoft Teams の組み込みのウイルス対策</span><span class="sxs-lookup"><span data-stu-id="632ff-103">Built-in virus protection in SharePoint Online, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="632ff-104">Microsoft 365 では、ユーザーが SharePoint Online、OneDrive、Microsoft Teams にアップロードするファイルをスキャンするための共通のウイルス検出エンジンを使用しています。</span><span class="sxs-lookup"><span data-stu-id="632ff-104">Microsoft 365 uses a common virus detection engine for scanning files that users upload to SharePoint Online, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="632ff-105">この保護は、SharePoint Online、OneDrive、Microsoft Teams を含むすべてのサブスクリプションに含まれています。</span><span class="sxs-lookup"><span data-stu-id="632ff-105">This protection is included with all subscriptions that include SharePoint Online, OneDrive, and Microsoft Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="632ff-106">組み込みのウイルス対策機能を使用すると、ウイルスを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="632ff-106">The built-in anti-virus capabilities are a way to help contain viruses.</span></span> <span data-ttu-id="632ff-107">これだけで、お客様の環境がマルウェアから保護されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="632ff-107">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="632ff-108">すべてのお客様に対して、さまざまな層でマルウェア対策保護を調査して実装し、企業インフラストラクチャを保護するためのベストプラクティスを適用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="632ff-108">We encourage all customers to investigate and implement anti-malware protection at various layers and apply best practices for securing their enterprise infrastructure.</span></span> <span data-ttu-id="632ff-109">戦略とベストプラクティスの詳細については、「 [セキュリティロードマップ](security-roadmap.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="632ff-109">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="632ff-110">感染したファイルが SharePoint Online にアップロードされたとき</span><span class="sxs-lookup"><span data-stu-id="632ff-110">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="632ff-111">Microsoft 365 ウイルス検出エンジンは、SharePoint Online 内で非同期的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="632ff-111">The Microsoft 365 virus detection engine runs asynchronously within SharePoint Online.</span></span> <span data-ttu-id="632ff-112">**アップロード時にすべてのファイルが自動的にスキャンされることはありません**。</span><span class="sxs-lookup"><span data-stu-id="632ff-112">**All files are not automatically scanned on upload**.</span></span> <span data-ttu-id="632ff-113">ヒューリスティックはスキャンするファイルを決定します。</span><span class="sxs-lookup"><span data-stu-id="632ff-113">Heuristics determine the files to scan.</span></span> <span data-ttu-id="632ff-114">ファイルにウイルスが含まれていることが検出されると、ファイルはフラグが付けられ、再度ダウンロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="632ff-114">When a file is found to contain a virus, the file is flagged so it can't be downloaded again.</span></span> <span data-ttu-id="632ff-115">2018年4月に、スキャンされたファイルの 25 MB の制限を削除しました。</span><span class="sxs-lookup"><span data-stu-id="632ff-115">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="632ff-116">動作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="632ff-116">Here's what happens:</span></span>

1. <span data-ttu-id="632ff-117">ユーザーがファイルを SharePoint Online にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="632ff-117">A user uploads a file to SharePoint Online.</span></span>
2. <span data-ttu-id="632ff-118">SharePoint Online は、ファイルがスキャンの条件を満たしているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="632ff-118">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>
3. <span data-ttu-id="632ff-119">ウイルス検出エンジンによってファイルがスキャンされます。</span><span class="sxs-lookup"><span data-stu-id="632ff-119">The virus detection engine scans the file.</span></span>
4. <span data-ttu-id="632ff-120">ウイルスが検出された場合、ウイルスエンジンはそのファイルが感染していることを示すプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="632ff-120">If a virus is found, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="632ff-121">ブラウザーを使って感染したファイルをダウンロードしようとしても、</span><span class="sxs-lookup"><span data-stu-id="632ff-121">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="632ff-122">ファイルが感染している場合、ユーザーはブラウザーを使用して SharePoint Online からファイルをダウンロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="632ff-122">If a file is infected, users can't download the file from SharePoint Online by using a browser.</span></span>

<span data-ttu-id="632ff-123">動作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="632ff-123">Here's what happens:</span></span>

1. <span data-ttu-id="632ff-124">Web ブラウザーを開き、感染したファイルを SharePoint Online からダウンロードしようとすると、</span><span class="sxs-lookup"><span data-stu-id="632ff-124">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
2. <span data-ttu-id="632ff-125">ウイルスが検出されたという警告がユーザーに提示されます。</span><span class="sxs-lookup"><span data-stu-id="632ff-125">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="632ff-126">既定では、ユーザーはファイルをダウンロードし、自分のデバイスでウイルス対策ソフトウェアを使用してウイルス対策ソフトウェアを使用してクリーニングを試みることができます。</span><span class="sxs-lookup"><span data-stu-id="632ff-126">By default, the user is given the option to download the file and attempt to clean it using the anti-virus software on their own device.</span></span>

> [!NOTE]
>
> <span data-ttu-id="632ff-127">管理者は、SharePoint Online PowerShell の[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)コマンドレットの*DisallowInfectedFileDownload*パラメーターを使用して、ウイルス対策の警告ウィンドウであっても、感染したファイルをユーザーがダウンロードできないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="632ff-127">Admins can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading infected files, even in the anti-virus warning window.</span></span> <span data-ttu-id="632ff-128">手順については、「 [SharePoint Online PowerShell を使用してユーザーが悪意のあるファイルをダウンロードするのを防ぐ](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="632ff-128">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>
>
> <span data-ttu-id="632ff-129">*DisallowInfectedFileDownload*パラメーターを有効にすると、ユーザーと管理者に対して、検出/ブロックされたファイルへのアクセスが完全にブロックされます。</span><span class="sxs-lookup"><span data-stu-id="632ff-129">As soon as you enable the *DisallowInfectedFileDownload* parameter, access to the detected/blocked files is completely blocked for users and admins.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="632ff-130">感染したファイルを OneDrive の同期クライアントが同期しようとするとどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="632ff-130">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="632ff-131">OneDrive 同期クライアントでは、ウイルスが含まれているファイルはダウンロードされません。</span><span class="sxs-lookup"><span data-stu-id="632ff-131">OneDrive sync clients will not download files that contain viruses.</span></span> <span data-ttu-id="632ff-132">ファイルを同期できないという通知が同期クライアントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="632ff-132">The sync client will display a notification that the file can't be synced.</span></span>

## <a name="extended-capabilities-with-office-365-advanced-threat-protection"></a><span data-ttu-id="632ff-133">Office 365 の高度な脅威保護の拡張機能</span><span class="sxs-lookup"><span data-stu-id="632ff-133">Extended capabilities with Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="632ff-134">Microsoft 365 の [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) をサブスクリプションに含めるか、またはアドオンとして購入することにより、SharePoint、OneDrive、microsoft TEAMS で atp を使用して、レポートと保護を強化することができます。</span><span class="sxs-lookup"><span data-stu-id="632ff-134">Microsoft 365 organizations that have [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) included in their subscription or purchased as an add-on can enable ATP for SharePoint, OneDrive, and Microsoft Teams for enhanced reporting and protection.</span></span> <span data-ttu-id="632ff-135">詳細については、「 [SharePoint、OneDrive、Microsoft Teams 用の ATP](atp-for-spo-odb-and-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="632ff-135">For more information, see [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

## <a name="more-information"></a><span data-ttu-id="632ff-136">詳細情報</span><span class="sxs-lookup"><span data-stu-id="632ff-136">More information</span></span>

<span data-ttu-id="632ff-137">SharePoint Online、OneDrive、Microsoft Teams のウイルス対策の詳細については、「 [脅威から保護](protect-against-threats.md) する」と「 [sharepoint、Onedrive、microsoft TEAMS 用の ATP を有効にする](turn-on-atp-for-spo-odb-and-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="632ff-137">For more information about anti-virus in SharePoint Online, OneDrive, and Microsoft Teams, see [Protect against threats](protect-against-threats.md) and [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>
