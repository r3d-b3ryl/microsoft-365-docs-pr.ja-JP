---
title: SharePoint Online、OneDrive、Microsoft Teams の組み込みのウイルス保護
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
description: SharePoint Online が、ユーザーがアップロードするファイル内のウイルスを検出し、ユーザーがファイルをダウンロードまたは同期する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dd38b196c106a36fb1a1bfc0a441620b1c5b8ba5
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205333"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a><span data-ttu-id="4f96a-103">SharePoint Online、OneDrive、Microsoft Teams の組み込みのウイルス保護</span><span class="sxs-lookup"><span data-stu-id="4f96a-103">Built-in virus protection in SharePoint Online, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4f96a-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="4f96a-104">**Applies to**</span></span>
- [<span data-ttu-id="4f96a-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="4f96a-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="4f96a-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="4f96a-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)

<span data-ttu-id="4f96a-107">Microsoft 365 は、ユーザーが SharePoint Online、OneDrive、および Microsoft Teams にアップロードするファイルをスキャンするために、一般的なウイルス検出エンジンを使用します。</span><span class="sxs-lookup"><span data-stu-id="4f96a-107">Microsoft 365 uses a common virus detection engine for scanning files that users upload to SharePoint Online, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="4f96a-108">この保護は、SharePoint Online、OneDrive、Microsoft Teams を含むすべてのサブスクリプションに含まれています。</span><span class="sxs-lookup"><span data-stu-id="4f96a-108">This protection is included with all subscriptions that include SharePoint Online, OneDrive, and Microsoft Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4f96a-109">組み込みのウイルス対策機能は、ウイルスを含むのに役立つ方法です。</span><span class="sxs-lookup"><span data-stu-id="4f96a-109">The built-in anti-virus capabilities are a way to help contain viruses.</span></span> <span data-ttu-id="4f96a-110">これだけで、お客様の環境がマルウェアから保護されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="4f96a-110">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="4f96a-111">すべてのお客様に対して、さまざまな層でマルウェア対策保護を調査および実装し、企業インフラストラクチャを保護するためのベスト プラクティスを適用してください。</span><span class="sxs-lookup"><span data-stu-id="4f96a-111">We encourage all customers to investigate and implement anti-malware protection at various layers and apply best practices for securing their enterprise infrastructure.</span></span> <span data-ttu-id="4f96a-112">戦略とベスト プラクティスの詳細については、「セキュリティ ロードマップ」 [を参照してください](security-roadmap.md)。</span><span class="sxs-lookup"><span data-stu-id="4f96a-112">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-if-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="4f96a-113">感染したファイルが SharePoint Online にアップロードされた場合は、どうなるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="4f96a-113">What happens if an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="4f96a-114">Microsoft 365 ウイルス検出エンジンは、SharePoint Online 内で (ファイルのアップロードとは独立して) 非同期的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="4f96a-114">The Microsoft 365 virus detection engine runs asynchronously (independent from file uploads) within SharePoint Online.</span></span> <span data-ttu-id="4f96a-115">**すべてのファイルは自動的にスキャンされません**。</span><span class="sxs-lookup"><span data-stu-id="4f96a-115">**All files are not automatically scanned**.</span></span> <span data-ttu-id="4f96a-116">ヒューリスティックは、スキャンするファイルを決定します。</span><span class="sxs-lookup"><span data-stu-id="4f96a-116">Heuristics determine the files to scan.</span></span> <span data-ttu-id="4f96a-117">ファイルにウイルスが含まれていると検出された場合、ファイルにフラグが設定されます。</span><span class="sxs-lookup"><span data-stu-id="4f96a-117">When a file is found to contain a virus, the file is flagged.</span></span> <span data-ttu-id="4f96a-118">2018 年 4 月に、スキャンしたファイルの 25 MB の制限が削除されました。</span><span class="sxs-lookup"><span data-stu-id="4f96a-118">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="4f96a-119">動作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4f96a-119">Here's what happens:</span></span>

1. <span data-ttu-id="4f96a-120">ユーザーがファイルを SharePoint Online にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="4f96a-120">A user uploads a file to SharePoint Online.</span></span>
2. <span data-ttu-id="4f96a-121">SharePoint Online は、ウイルス スキャン プロセスの一環として、ファイルがスキャンの条件を満たしたかどうかを後で判断します。</span><span class="sxs-lookup"><span data-stu-id="4f96a-121">SharePoint Online, as part of its virus scanning processes, later determines if the file meets the criteria for a scan.</span></span>
3. <span data-ttu-id="4f96a-122">ファイルがスキャンの条件を満たしている場合、ウイルス検出エンジンはファイルをスキャンします。</span><span class="sxs-lookup"><span data-stu-id="4f96a-122">If the file meets the criteria for a scan, the virus detection engine scans the file.</span></span>
4. <span data-ttu-id="4f96a-123">スキャンしたファイル内でウイルスが検出された場合、ウイルス エンジンはファイルに感染したことを示すプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="4f96a-123">If a virus is found within the scanned file, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="4f96a-124">ブラウザーを使って感染したファイルをダウンロードしようとしても、</span><span class="sxs-lookup"><span data-stu-id="4f96a-124">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="4f96a-125">ファイルが感染している場合、ユーザーはブラウザーを使用して SharePoint Online からファイルをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="4f96a-125">If a file is infected, users can't download the file from SharePoint Online by using a browser.</span></span>

<span data-ttu-id="4f96a-126">動作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4f96a-126">Here's what happens:</span></span>

1. <span data-ttu-id="4f96a-127">Web ブラウザーを開き、感染したファイルを SharePoint Online からダウンロードしようとすると、</span><span class="sxs-lookup"><span data-stu-id="4f96a-127">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
2. <span data-ttu-id="4f96a-128">ユーザーには、ウイルスが検出されたという警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4f96a-128">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="4f96a-129">既定では、ユーザーはファイルをダウンロードし、自分のデバイスでウイルス対策ソフトウェアを使用してファイルをクリーンアップするオプションを与えられます。</span><span class="sxs-lookup"><span data-stu-id="4f96a-129">By default, the user is given the option to download the file and attempt to clean it using the anti-virus software on their own device.</span></span>

> [!NOTE]
>
> <span data-ttu-id="4f96a-130">管理者は、SharePoint Online PowerShell の [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)コマンドレットの *DisallowInfectedFileDownload* パラメーターを使用して、ウイルス対策の警告ウィンドウでも、ユーザーが感染したファイルをダウンロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="4f96a-130">Admins can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading infected files, even in the anti-virus warning window.</span></span> <span data-ttu-id="4f96a-131">手順については、「Use SharePoint Online PowerShell を使用して、ユーザーが悪意のある [ファイルをダウンロードするのを防ぐ」を参照してください](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)。</span><span class="sxs-lookup"><span data-stu-id="4f96a-131">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>
>
> <span data-ttu-id="4f96a-132">*DisallowInfectedFileDownload* パラメーターを有効にしたとすぐに、検出またはブロックされたファイルへのアクセスは、ユーザーと管理者に対して完全にブロックされます。</span><span class="sxs-lookup"><span data-stu-id="4f96a-132">As soon as you enable the *DisallowInfectedFileDownload* parameter, access to the detected/blocked files is completely blocked for users and admins.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="4f96a-133">感染したファイルを OneDrive の同期クライアントが同期しようとするとどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="4f96a-133">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="4f96a-134">OneDrive 同期クライアントは、ウイルスを含むファイルをダウンロードしません。</span><span class="sxs-lookup"><span data-stu-id="4f96a-134">OneDrive sync clients will not download files that contain viruses.</span></span> <span data-ttu-id="4f96a-135">ファイルを同期できないという通知が同期クライアントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4f96a-135">The sync client will display a notification that the file can't be synced.</span></span>

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a><span data-ttu-id="4f96a-136">Microsoft Defender 365 用の拡張Office機能</span><span class="sxs-lookup"><span data-stu-id="4f96a-136">Extended capabilities with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="4f96a-137">Microsoft Defender for Office [365](defender-for-office-365.md) がサブスクリプションに含まれているか、アドオンとして購入されている Microsoft 365 組織では、レポートと保護を強化するために SharePoint、OneDrive、および Microsoft Teams の安全な添付ファイルを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="4f96a-137">Microsoft 365 organizations that have [Microsoft Defender for Office 365](defender-for-office-365.md) included in their subscription or purchased as an add-on can enable Safe Attachments for SharePoint, OneDrive, and Microsoft Teams for enhanced reporting and protection.</span></span> <span data-ttu-id="4f96a-138">詳細については [、「SharePoint、OneDrive、Microsoft Teams](mdo-for-spo-odb-and-teams.md)の安全な添付ファイル」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f96a-138">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="4f96a-139">関連記事</span><span class="sxs-lookup"><span data-stu-id="4f96a-139">Related Articles</span></span>

[<span data-ttu-id="4f96a-140">Microsoft 365 のマルウェアとランサムウェアの保護</span><span class="sxs-lookup"><span data-stu-id="4f96a-140">Malware and ransomware protection in Microsoft 365</span></span>](/compliance/assurance/assurance-malware-and-ransomware-protection)

<span data-ttu-id="4f96a-141">SharePoint Online、OneDrive、および Microsoft Teams のウイルス対策の詳細については[](protect-against-threats.md)、「脅威から保護する」および[「SharePoint、OneDrive、](turn-on-mdo-for-spo-odb-and-teams.md)および Microsoft Teams の安全な添付ファイルを有効にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f96a-141">For more information about anti-virus in SharePoint Online, OneDrive, and Microsoft Teams, see [Protect against threats](protect-against-threats.md) and [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).</span></span>
