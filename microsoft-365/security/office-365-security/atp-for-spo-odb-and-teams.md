---
title: SPO、OneDrive、Teams 用の安全な添付ファイル機能
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Microsoft Defender for Office 365 for files in SharePoint Online, OneDrive for Business, and Microsoft Teams について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 640867cb38dab650bca990fe36c0b7cea7f6a0d8
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175729"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="6df12-103">SPO、OneDrive、Teams 用の安全な添付ファイル機能</span><span class="sxs-lookup"><span data-stu-id="6df12-103">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6df12-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="6df12-104">**Applies to**</span></span>
- [<span data-ttu-id="6df12-105">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="6df12-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="6df12-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6df12-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="6df12-107">[Microsoft Defender for Office 365](office-365-atp.md)の SharePoint、OneDrive、Microsoft Teams の安全な添付ファイルは[、Microsoft 365](virus-detection-in-spo.md)の一般的なウイルス検出エンジンによってアップロード時に既にスキャンされたファイルに対する保護層を追加します。</span><span class="sxs-lookup"><span data-stu-id="6df12-107">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams in [Microsoft Defender for Office 365](office-365-atp.md) provides an additional layer of protection for files that have already been scanned at upload time by the [common virus detection engine in Microsoft 365](virus-detection-in-spo.md).</span></span> <span data-ttu-id="6df12-108">SharePoint、OneDrive、Microsoft Teams の安全な添付ファイルは、チーム サイトやドキュメント ライブラリで悪意のあるファイルとして識別された既存のファイルを検出してブロックするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6df12-108">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams helps detect and block existing files that are identified as malicious in team sites and document libraries.</span></span>

<span data-ttu-id="6df12-109">SharePoint、OneDrive、Microsoft Teams の安全な添付ファイルは、既定では有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="6df12-109">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is not enabled by default.</span></span> <span data-ttu-id="6df12-110">有効にする方法については [、「SharePoint、OneDrive、Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)の安全な添付ファイルを有効にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6df12-110">To turn it on, see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a><span data-ttu-id="6df12-111">SharePoint、OneDrive、Microsoft Teams の安全な添付ファイルのしくみ</span><span class="sxs-lookup"><span data-stu-id="6df12-111">How Safe Attachments for SharePoint, OneDrive, and Microsoft Teams works</span></span>

<span data-ttu-id="6df12-112">SharePoint、OneDrive、および Microsoft Teams の安全な添付ファイルが有効で、ファイルが悪意のあるファイルとして識別される場合、ファイル ストアとの直接統合を使用してファイルがロックされます。</span><span class="sxs-lookup"><span data-stu-id="6df12-112">When Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is enabled and identifies a file as malicious, the file is locked using direct integration with the file stores.</span></span> <span data-ttu-id="6df12-113">次の画像は、ライブラリで検出された悪意のあるファイルの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="6df12-113">The following image shows an example of a malicious file detected in a library.</span></span>

![悪意のあるファイルとして検出された OneDrive for Business のファイル](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

<span data-ttu-id="6df12-115">ブロックするファイルは引き続きドキュメント ライブラリと Web アプリケーション、モバイル アプリケーション、またはデスクトップ アプリケーションに表示されます。ただし、ユーザーはファイルを開く、コピーする、移動する、または共有できません。</span><span class="sxs-lookup"><span data-stu-id="6df12-115">Although the blocked file is still listed in the document library and in web, mobile, or desktop applications, people can't open, copy, move, or share the file.</span></span> <span data-ttu-id="6df12-116">ただし、ブロックするファイルは削除できます。</span><span class="sxs-lookup"><span data-stu-id="6df12-116">But they can delete the blocked file.</span></span>

<span data-ttu-id="6df12-117">モバイル デバイスでブロックされるファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6df12-117">Here's an example of what a blocked file looks like on a mobile device:</span></span>

![OneDrive モバイル アプリから OneDrive for Business からブロックされたファイルを削除する](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

<span data-ttu-id="6df12-119">既定では、ユーザーはブロックされたファイルをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="6df12-119">By default, people can download a blocked file.</span></span> <span data-ttu-id="6df12-120">ブロックするファイルをモバイル デバイスでダウンロードする方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6df12-120">Here's what downloading a blocked file looks like on a mobile device:</span></span>

![OneDrive for Business でブロックされたファイルをダウンロードする](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

<span data-ttu-id="6df12-122">SharePoint Online 管理者は、悪意のあるファイルをダウンロードするユーザーを防止できます。</span><span class="sxs-lookup"><span data-stu-id="6df12-122">SharePoint Online admins can prevent people from downloading malicious files.</span></span> <span data-ttu-id="6df12-123">手順については [、「SharePoint Online PowerShell を使用して、ユーザーが悪意のあるファイルをダウンロードするのを防ぐ」を参照してください](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)。</span><span class="sxs-lookup"><span data-stu-id="6df12-123">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>

<span data-ttu-id="6df12-124">ファイルが悪意のあるファイルとして検出された場合のユーザー エクスペリエンスの詳細については [、「SharePoint Online、OneDrive、または Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)で悪意のあるファイルが見つかった場合の対応方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6df12-124">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span>

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="6df12-125">SharePoint、OneDrive、Microsoft Teams の安全な添付ファイルで検出された悪意のあるファイルに関する情報を表示する</span><span class="sxs-lookup"><span data-stu-id="6df12-125">View information about malicious files detected by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="6df12-126">Office 365 の Microsoft Defender によって悪意のあるファイルとして識別されたファイルは [、microsoft Defender for Office 365](view-reports-for-atp.md) およびエクスプローラー (およびリアルタイムの検出 [)](threat-explorer.md)のレポートに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6df12-126">Files that are identified as malicious by Microsoft Defender for Office 365 will show up in [reports for Microsoft Defender for Office 365](view-reports-for-atp.md) and in [Explorer (and real-time detections)](threat-explorer.md).</span></span>

<span data-ttu-id="6df12-127">2018 年 5 月現在、ファイルが Office 365 の Microsoft Defender によって悪意のあるファイルとして識別された場合、そのファイルは検疫でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="6df12-127">As of May 2018, when a file is identified as malicious by Microsoft Defender for Office 365, the file is also available in quarantine.</span></span> <span data-ttu-id="6df12-128">詳細については、「セキュリティ/コンプライアンス センター [を使用して&ファイルを管理する」を参照してください](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)。</span><span class="sxs-lookup"><span data-stu-id="6df12-128">For more information, see [Use the Security & Compliance Center to manage quarantined files](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files).</span></span>

## <a name="keep-these-points-in-mind"></a><span data-ttu-id="6df12-129">以下の点を念頭に置く</span><span class="sxs-lookup"><span data-stu-id="6df12-129">Keep these points in mind</span></span>

- <span data-ttu-id="6df12-130">Defender for Office 365 は、SharePoint Online、OneDrive for Business、または Microsoft Teams のすべてのファイルをスキャンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6df12-130">Defender for Office 365 will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="6df12-131">この動作は仕様です。</span><span class="sxs-lookup"><span data-stu-id="6df12-131">This is by design.</span></span> <span data-ttu-id="6df12-132">ファイルは非同期的にスキャンされます。</span><span class="sxs-lookup"><span data-stu-id="6df12-132">Files are scanned asynchronously.</span></span> <span data-ttu-id="6df12-133">このプロセスでは、共有イベントとゲスト アクティビティ イベントをスマート ヒューリスティックや脅威シグナルと共に使用して、悪意のあるファイルを特定します。</span><span class="sxs-lookup"><span data-stu-id="6df12-133">The process uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="6df12-134">SharePoint サイトがモダン エクスペリエンスを使用するように構成されていることを [確認します](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience)。</span><span class="sxs-lookup"><span data-stu-id="6df12-134">Make sure your SharePoint sites are configured to use the [Modern experience](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience).</span></span> <span data-ttu-id="6df12-135">Defender for Office 365 保護は、モダン エクスペリエンスとクラシック ビューの使用に関して適用されます。ただし、ファイルがブロックされている視覚的なインジケーターは、モダン エクスペリエンスでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="6df12-135">Defender for Office 365 protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are available only in the Modern experience.</span></span>

- <span data-ttu-id="6df12-136">SharePoint、OneDrive、および Microsoft Teams の安全な添付ファイルは、Exchange Online Protection (EOP) のスパム対策とマルウェア対策保護、Microsoft Defender for Office 365 の安全なリンクと安全な添付ファイルを含む、組織の全体的な脅威保護戦略の一部です。</span><span class="sxs-lookup"><span data-stu-id="6df12-136">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection in Exchange Online Protection (EOP), as well as Safe Links and Safe Attachments in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="6df12-137">詳細については、「Office [365」を参照](protect-against-threats.md)してください。</span><span class="sxs-lookup"><span data-stu-id="6df12-137">To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>
