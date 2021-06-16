---
title: オンライン、SharePoint、およびOneDriveに組み込Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: ユーザーがアップロードSharePointファイル内のウイルスをオンラインで検出し、ユーザーがファイルをダウンロードまたは同期する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2ab11d4c1e2a064ad0717e6619f72a38b0cbc831
ms.sourcegitcommit: ac3e9ccb7b43a42e600af8f44e6f30019533faeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/15/2021
ms.locfileid: "52932832"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a><span data-ttu-id="a9786-103">オンライン、SharePoint、およびOneDriveに組み込Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a9786-103">Built-in virus protection in SharePoint Online, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a9786-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="a9786-104">**Applies to**</span></span>
- [<span data-ttu-id="a9786-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a9786-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a9786-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="a9786-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)

<span data-ttu-id="a9786-107">Microsoft 365は SharePoint、ユーザーがオンライン、OneDrive、およびファイルにアップロードするファイルをスキャンするために、一般的なOneDriveを使用Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="a9786-107">Microsoft 365 uses a common virus detection engine for scanning files that users upload to SharePoint Online, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="a9786-108">この保護は、オンライン、オンライン、SharePoint、およびOneDrive含Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="a9786-108">This protection is included with all subscriptions that include SharePoint Online, OneDrive, and Microsoft Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a9786-109">組み込みのウイルス対策機能は、ウイルスを含むのに役立つ方法です。</span><span class="sxs-lookup"><span data-stu-id="a9786-109">The built-in anti-virus capabilities are a way to help contain viruses.</span></span> <span data-ttu-id="a9786-110">これだけで、お客様の環境がマルウェアから保護されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="a9786-110">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="a9786-111">すべてのお客様に対して、さまざまな層でマルウェア対策保護を調査および実装し、企業インフラストラクチャを保護するためのベスト プラクティスを適用してください。</span><span class="sxs-lookup"><span data-stu-id="a9786-111">We encourage all customers to investigate and implement anti-malware protection at various layers and apply best practices for securing their enterprise infrastructure.</span></span> <span data-ttu-id="a9786-112">戦略とベスト プラクティスの詳細については、「セキュリティ ロードマップ」 [を参照してください](security-roadmap.md)。</span><span class="sxs-lookup"><span data-stu-id="a9786-112">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-if-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="a9786-113">感染したファイルがオンラインにアップロードされた場合SharePointされますか?</span><span class="sxs-lookup"><span data-stu-id="a9786-113">What happens if an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="a9786-114">ウイルスMicrosoft 365検出エンジンは、オンライン内で (ファイルのアップロードとは独立して) 非同期SharePointします。</span><span class="sxs-lookup"><span data-stu-id="a9786-114">The Microsoft 365 virus detection engine runs asynchronously (independent from file uploads) within SharePoint Online.</span></span> <span data-ttu-id="a9786-115">**すべてのファイルは自動的にスキャンされません**。</span><span class="sxs-lookup"><span data-stu-id="a9786-115">**All files are not automatically scanned**.</span></span> <span data-ttu-id="a9786-116">ヒューリスティックは、スキャンするファイルを決定します。</span><span class="sxs-lookup"><span data-stu-id="a9786-116">Heuristics determine the files to scan.</span></span> <span data-ttu-id="a9786-117">ファイルにウイルスが含まれていると検出された場合、ファイルにフラグが設定されます。</span><span class="sxs-lookup"><span data-stu-id="a9786-117">When a file is found to contain a virus, the file is flagged.</span></span> <span data-ttu-id="a9786-118">2018 年 4 月に、スキャンしたファイルの 25 MB の制限が削除されました。</span><span class="sxs-lookup"><span data-stu-id="a9786-118">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="a9786-119">動作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a9786-119">Here's what happens:</span></span>

1. <span data-ttu-id="a9786-120">ユーザーがファイルを SharePoint Online にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="a9786-120">A user uploads a file to SharePoint Online.</span></span>
2. <span data-ttu-id="a9786-121">SharePointオンラインでは、ウイルススキャンプロセスの一環として、ファイルがスキャンの条件を満たしたかどうかを後で判断します。</span><span class="sxs-lookup"><span data-stu-id="a9786-121">SharePoint Online, as part of its virus scanning processes, later determines if the file meets the criteria for a scan.</span></span>
3. <span data-ttu-id="a9786-122">ファイルがスキャンの条件を満たしている場合、ウイルス検出エンジンはファイルをスキャンします。</span><span class="sxs-lookup"><span data-stu-id="a9786-122">If the file meets the criteria for a scan, the virus detection engine scans the file.</span></span>
4. <span data-ttu-id="a9786-123">スキャンしたファイル内でウイルスが検出された場合、ウイルス エンジンはファイルに感染したことを示すプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="a9786-123">If a virus is found within the scanned file, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="a9786-124">ブラウザーを使って感染したファイルをダウンロードしようとしても、</span><span class="sxs-lookup"><span data-stu-id="a9786-124">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="a9786-125">ファイルが感染している場合、ユーザーはブラウザーを使用して SharePointオンラインからファイルをダウンロードできない。</span><span class="sxs-lookup"><span data-stu-id="a9786-125">If a file is infected, users can't download the file from SharePoint Online by using a browser.</span></span>

<span data-ttu-id="a9786-126">動作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a9786-126">Here's what happens:</span></span>

1. <span data-ttu-id="a9786-127">Web ブラウザーを開き、感染したファイルを SharePoint Online からダウンロードしようとすると、</span><span class="sxs-lookup"><span data-stu-id="a9786-127">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
2. <span data-ttu-id="a9786-128">ユーザーには、ウイルスが検出されたという警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a9786-128">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="a9786-129">既定では、ユーザーはファイルをダウンロードし、自分のデバイスでウイルス対策ソフトウェアを使用してファイルをクリーンアップするオプションを与えられます。</span><span class="sxs-lookup"><span data-stu-id="a9786-129">By default, the user is given the option to download the file and attempt to clean it using the anti-virus software on their own device.</span></span>

> [!NOTE]
>
> <span data-ttu-id="a9786-130">管理者は、SharePoint Online PowerShell の [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)コマンドレットの *DisallowInfectedFileDownload* パラメーターを使用して、ウイルス対策の警告ウィンドウでも、ユーザーが感染したファイルをダウンロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a9786-130">Admins can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading infected files, even in the anti-virus warning window.</span></span> <span data-ttu-id="a9786-131">手順については、「ユーザーが悪意のある[ファイルをダウンロードSharePointオンライン PowerShell を使用する」を参照してください](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)。</span><span class="sxs-lookup"><span data-stu-id="a9786-131">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>
>
> <span data-ttu-id="a9786-132">*DisallowInfectedFileDownload* パラメーターを有効にしたとすぐに、検出またはブロックされたファイルへのアクセスは、ユーザーと管理者に対して完全にブロックされます。</span><span class="sxs-lookup"><span data-stu-id="a9786-132">As soon as you enable the *DisallowInfectedFileDownload* parameter, access to the detected/blocked files is completely blocked for users and admins.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="a9786-133">感染したファイルを OneDrive の同期クライアントが同期しようとするとどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="a9786-133">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="a9786-134">悪意のあるファイルがマルウェアにアップロードOneDrive、マルウェアとしてマークされる前にローカル コンピューターに同期されます。</span><span class="sxs-lookup"><span data-stu-id="a9786-134">When a malicious file is uploaded to OneDrive, it will be synced to the local machine before it's marked as malware.</span></span> <span data-ttu-id="a9786-135">マルウェアとしてマークされた後、ユーザーはローカル コンピューターから同期されたファイルを開くことができません。</span><span class="sxs-lookup"><span data-stu-id="a9786-135">After it's marked as malware, the user can't open the synced file anymore from their local machine.</span></span>

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a><span data-ttu-id="a9786-136">Microsoft Defender を使用した機能の拡張Office 365</span><span class="sxs-lookup"><span data-stu-id="a9786-136">Extended capabilities with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="a9786-137">Microsoft 365 Office 365 用[Microsoft Defender](defender-for-office-365.md)をサブスクリプションに含める組織、またはアドオンとして購入した組織では、セーフ 添付ファイルを SharePoint、OneDrive、および Microsoft Teams に対して有効にして、レポートと保護を強化できます。</span><span class="sxs-lookup"><span data-stu-id="a9786-137">Microsoft 365 organizations that have [Microsoft Defender for Office 365](defender-for-office-365.md) included in their subscription or purchased as an add-on can enable Safe Attachments for SharePoint, OneDrive, and Microsoft Teams for enhanced reporting and protection.</span></span> <span data-ttu-id="a9786-138">詳細については、「[SharePoint、OneDrive、Microsoft Teams の安全な添付ファイル](mdo-for-spo-odb-and-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9786-138">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="a9786-139">関連記事</span><span class="sxs-lookup"><span data-stu-id="a9786-139">Related Articles</span></span>

[<span data-ttu-id="a9786-140">マルウェアとランサムウェアのMicrosoft 365</span><span class="sxs-lookup"><span data-stu-id="a9786-140">Malware and ransomware protection in Microsoft 365</span></span>](/compliance/assurance/assurance-malware-and-ransomware-protection)

<span data-ttu-id="a9786-141">SharePoint Online、OneDrive、および Microsoft Teams のウイルス対策の詳細については、「脅威から保護する」および「SharePoint、OneDrive、および Microsoft Teams の セーフ 添付ファイルを有効にする」を[参照してください](turn-on-mdo-for-spo-odb-and-teams.md)。 [](protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="a9786-141">For more information about anti-virus in SharePoint Online, OneDrive, and Microsoft Teams, see [Protect against threats](protect-against-threats.md) and [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).</span></span>
