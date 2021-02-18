---
title: SharePoint Online、OneDrive、Microsoft Teams の組み込みウイルス対策
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
description: SharePoint Online が、ユーザーがアップロードするファイル内のウイルスを検出し、ユーザーがファイルをダウンロードまたは同期するのを防ぐ方法について説明します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f0eafb9e5e2f0c9d86791fe83931276e420afcd9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286503"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a><span data-ttu-id="c0d99-103">SharePoint Online、OneDrive、Microsoft Teams の組み込みウイルス対策</span><span class="sxs-lookup"><span data-stu-id="c0d99-103">Built-in virus protection in SharePoint Online, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c0d99-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="c0d99-104">**Applies to**</span></span>
- [<span data-ttu-id="c0d99-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c0d99-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c0d99-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="c0d99-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)

<span data-ttu-id="c0d99-107">Microsoft 365 は、ユーザーが SharePoint Online、OneDrive、および Microsoft Teams にアップロードするファイルをスキャンするために一般的なウイルス検出エンジンを使用します。</span><span class="sxs-lookup"><span data-stu-id="c0d99-107">Microsoft 365 uses a common virus detection engine for scanning files that users upload to SharePoint Online, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="c0d99-108">この保護は、SharePoint Online、OneDrive、Microsoft Teams を含むすべてのサブスクリプションに含まれています。</span><span class="sxs-lookup"><span data-stu-id="c0d99-108">This protection is included with all subscriptions that include SharePoint Online, OneDrive, and Microsoft Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c0d99-109">組み込みのウイルス対策機能は、ウイルスを含むのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c0d99-109">The built-in anti-virus capabilities are a way to help contain viruses.</span></span> <span data-ttu-id="c0d99-110">これだけで、お客様の環境がマルウェアから保護されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="c0d99-110">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="c0d99-111">すべてのお客様に対して、さまざまなレイヤーでマルウェア対策保護を調査および実装し、企業インフラストラクチャをセキュリティ保護するためのベスト プラクティスを適用してください。</span><span class="sxs-lookup"><span data-stu-id="c0d99-111">We encourage all customers to investigate and implement anti-malware protection at various layers and apply best practices for securing their enterprise infrastructure.</span></span> <span data-ttu-id="c0d99-112">戦略とベスト プラクティスの詳細については、「セキュリティ ロードマップ」 [を参照してください](security-roadmap.md)。</span><span class="sxs-lookup"><span data-stu-id="c0d99-112">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="c0d99-113">感染したファイルが SharePoint Online にアップロードされたとき</span><span class="sxs-lookup"><span data-stu-id="c0d99-113">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="c0d99-114">Microsoft 365 ウイルス検出エンジンは、SharePoint Online 内で非同期的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="c0d99-114">The Microsoft 365 virus detection engine runs asynchronously within SharePoint Online.</span></span> <span data-ttu-id="c0d99-115">**すべてのファイルは、アップロード時に自動的にスキャンされません**。</span><span class="sxs-lookup"><span data-stu-id="c0d99-115">**All files are not automatically scanned on upload**.</span></span> <span data-ttu-id="c0d99-116">ヒューリスティックは、スキャンするファイルを決定します。</span><span class="sxs-lookup"><span data-stu-id="c0d99-116">Heuristics determine the files to scan.</span></span> <span data-ttu-id="c0d99-117">ファイルにウイルスが含まれていると見つかると、そのファイルにフラグが付けられているので、再びダウンロードできません。</span><span class="sxs-lookup"><span data-stu-id="c0d99-117">When a file is found to contain a virus, the file is flagged so it can't be downloaded again.</span></span> <span data-ttu-id="c0d99-118">2018 年 4 月に、スキャンされたファイルの 25 MB の制限が削除されました。</span><span class="sxs-lookup"><span data-stu-id="c0d99-118">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="c0d99-119">動作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c0d99-119">Here's what happens:</span></span>

1. <span data-ttu-id="c0d99-120">ユーザーがファイルを SharePoint Online にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="c0d99-120">A user uploads a file to SharePoint Online.</span></span>
2. <span data-ttu-id="c0d99-121">SharePoint Online は、ファイルがスキャンの条件を満たしたかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="c0d99-121">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>
3. <span data-ttu-id="c0d99-122">ウイルス検出エンジンによってファイルがスキャンされます。</span><span class="sxs-lookup"><span data-stu-id="c0d99-122">The virus detection engine scans the file.</span></span>
4. <span data-ttu-id="c0d99-123">ウイルスが見つかった場合、ウイルス エンジンは、ウイルスに感染したことを示すプロパティをファイルに設定します。</span><span class="sxs-lookup"><span data-stu-id="c0d99-123">If a virus is found, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="c0d99-124">ブラウザーを使って感染したファイルをダウンロードしようとしても、</span><span class="sxs-lookup"><span data-stu-id="c0d99-124">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="c0d99-125">ファイルが感染している場合、ユーザーはブラウザーを使用して SharePoint Online からファイルをダウンロードできない。</span><span class="sxs-lookup"><span data-stu-id="c0d99-125">If a file is infected, users can't download the file from SharePoint Online by using a browser.</span></span>

<span data-ttu-id="c0d99-126">動作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c0d99-126">Here's what happens:</span></span>

1. <span data-ttu-id="c0d99-127">Web ブラウザーを開き、感染したファイルを SharePoint Online からダウンロードしようとすると、</span><span class="sxs-lookup"><span data-stu-id="c0d99-127">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
2. <span data-ttu-id="c0d99-128">ウイルスが検出されたという警告がユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c0d99-128">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="c0d99-129">既定では、ユーザーはファイルをダウンロードして、自分のデバイス上のウイルス対策ソフトウェアを使用してファイルのクリーンアップを試みるオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c0d99-129">By default, the user is given the option to download the file and attempt to clean it using the anti-virus software on their own device.</span></span>

> [!NOTE]
>
> <span data-ttu-id="c0d99-130">管理者は、SharePoint Online PowerShell の [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)コマンドレットで *DisallowInfectedFileDownload* パラメーターを使用して、ウイルス対策警告ウィンドウでも、ユーザーがウイルスに感染したファイルをダウンロードするのを防止できます。</span><span class="sxs-lookup"><span data-stu-id="c0d99-130">Admins can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading infected files, even in the anti-virus warning window.</span></span> <span data-ttu-id="c0d99-131">手順については [、「SharePoint Online PowerShell を使用して、ユーザーが悪意のあるファイルをダウンロードするのを防ぐ」を参照してください](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)。</span><span class="sxs-lookup"><span data-stu-id="c0d99-131">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>
>
> <span data-ttu-id="c0d99-132">*DisallowInfectedFileDownload* パラメーターを有効にしたとすぐに、検出またはブロックされたファイルへのアクセスは、ユーザーと管理者に対して完全にブロックされます。</span><span class="sxs-lookup"><span data-stu-id="c0d99-132">As soon as you enable the *DisallowInfectedFileDownload* parameter, access to the detected/blocked files is completely blocked for users and admins.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="c0d99-133">感染したファイルを OneDrive の同期クライアントが同期しようとするとどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="c0d99-133">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="c0d99-134">OneDrive 同期クライアントは、ウイルスを含むファイルをダウンロードしません。</span><span class="sxs-lookup"><span data-stu-id="c0d99-134">OneDrive sync clients will not download files that contain viruses.</span></span> <span data-ttu-id="c0d99-135">ファイルを同期できないという通知が同期クライアントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c0d99-135">The sync client will display a notification that the file can't be synced.</span></span>

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a><span data-ttu-id="c0d99-136">Microsoft Defender for Office 365 の拡張機能</span><span class="sxs-lookup"><span data-stu-id="c0d99-136">Extended capabilities with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="c0d99-137">Microsoft Defender for Office [365](office-365-atp.md) をサブスクリプションに含めるか、アドオンとして購入した Microsoft 365 組織では、レポートと保護を強化するために SharePoint、OneDrive、Microsoft Teams の安全な添付ファイルを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="c0d99-137">Microsoft 365 organizations that have [Microsoft Defender for Office 365](office-365-atp.md) included in their subscription or purchased as an add-on can enable Safe Attachments for SharePoint, OneDrive, and Microsoft Teams for enhanced reporting and protection.</span></span> <span data-ttu-id="c0d99-138">詳細については [、「SharePoint、OneDrive、Microsoft Teams の安全な添付ファイル」を参照してください](atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="c0d99-138">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="c0d99-139">関連記事</span><span class="sxs-lookup"><span data-stu-id="c0d99-139">Related Articles</span></span>

[<span data-ttu-id="c0d99-140">Microsoft 365 のマルウェアとランサムウェアからの保護</span><span class="sxs-lookup"><span data-stu-id="c0d99-140">Malware and ransomware protection in Microsoft 365</span></span>](https://docs.microsoft.com/compliance/assurance/assurance-malware-and-ransomware-protection)

<span data-ttu-id="c0d99-141">SharePoint Online、OneDrive、および Microsoft Teams のウイルス対策の詳細については[](protect-against-threats.md)、「脅威からの保護」および[「SharePoint、OneDrive、Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)の安全な添付ファイルを有効にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0d99-141">For more information about anti-virus in SharePoint Online, OneDrive, and Microsoft Teams, see [Protect against threats](protect-against-threats.md) and [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>
