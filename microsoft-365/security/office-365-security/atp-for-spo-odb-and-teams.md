---
title: SharePoint、OneDrive、Microsoft Teams 用の ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: SharePoint Online、OneDrive for Business、Microsoft Teams のファイルの Office 365 Advanced Threat Protection について説明します。
ms.openlocfilehash: 95557e99817f7e7d3fe678c1966e4e04fd3753d7
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350891"
---
# <a name="atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="76f5c-103">SharePoint、OneDrive、Microsoft Teams 用の ATP</span><span class="sxs-lookup"><span data-stu-id="76f5c-103">ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="76f5c-104">ATP for SharePoint, OneDrive, and Microsoft Teams in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) は、 [Microsoft 365 の一般的なウイルス検出エンジン](virus-detection-in-spo.md)によってアップロード時に既にスキャンされているファイルに対して、追加の保護レイヤーを提供します。</span><span class="sxs-lookup"><span data-stu-id="76f5c-104">ATP for SharePoint, OneDrive, and Microsoft Teams in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) provides an additional layer of protection for files that have already been scanned at upload time by the [common virus detection engine in Microsoft 365](virus-detection-in-spo.md).</span></span> <span data-ttu-id="76f5c-105">SharePoint、OneDrive、Microsoft Teams 用の ATP は、チームサイトやドキュメントライブラリに悪意のあるファイルとして識別された既存のファイルを検出してブロックするのに便利です。</span><span class="sxs-lookup"><span data-stu-id="76f5c-105">ATP for SharePoint, OneDrive, and Microsoft Teams helps detect and block existing files that are identified as malicious in team sites and document libraries.</span></span>

<span data-ttu-id="76f5c-106">既定では、SharePoint、OneDrive、Microsoft Teams 用の ATP は有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="76f5c-106">ATP for SharePoint, OneDrive, and Microsoft Teams is not enabled by default.</span></span> <span data-ttu-id="76f5c-107">これをオンにするには、「 [SharePoint、OneDrive、Microsoft Teams の ATP を有効](turn-on-atp-for-spo-odb-and-teams.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76f5c-107">To turn it on, see [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

## <a name="how-atp-for-sharepoint-onedrive-and-microsoft-teams-works"></a><span data-ttu-id="76f5c-108">SharePoint、OneDrive、Microsoft Teams の ATP のしくみ</span><span class="sxs-lookup"><span data-stu-id="76f5c-108">How ATP for SharePoint, OneDrive, and Microsoft Teams works</span></span>

<span data-ttu-id="76f5c-109">SharePoint、OneDrive、Microsoft Teams 用の ATP を有効にし、ファイルを悪意のあるものとして識別すると、ファイルはファイルストアと直接統合してロックされます。</span><span class="sxs-lookup"><span data-stu-id="76f5c-109">When ATP for SharePoint, OneDrive, and Microsoft Teams is enabled and identifies a file as malicious, the file is locked using direct integration with the file stores.</span></span> <span data-ttu-id="76f5c-110">次の図は、ライブラリ内で検出された悪意のあるファイルの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="76f5c-110">The following image shows an example of a malicious file detected in a library.</span></span>

![悪意のあるものとして検出された OneDrive for Business のファイル](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

<span data-ttu-id="76f5c-112">ブロックされたファイルは、ドキュメントライブラリと web、モバイル、またはデスクトップの各アプリケーションに表示されていますが、ユーザーはファイルを開く、コピー、移動、または共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="76f5c-112">Although the blocked file is still listed in the document library and in web, mobile, or desktop applications, people can't open, copy, move, or share the file.</span></span> <span data-ttu-id="76f5c-113">ただし、ブロックされたファイルを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="76f5c-113">But they can delete the blocked file.</span></span>

<span data-ttu-id="76f5c-114">次に、モバイルデバイスでブロックされるファイルの外観を示します。</span><span class="sxs-lookup"><span data-stu-id="76f5c-114">Here's an example of what a blocked file looks like on a mobile device:</span></span>

![Onedrive モバイルアプリから OneDrive for business からブロックされたファイルを削除する](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

<span data-ttu-id="76f5c-116">既定では、ユーザーはブロックされたファイルをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="76f5c-116">By default, people can download a blocked file.</span></span> <span data-ttu-id="76f5c-117">ブロックされたファイルをダウンロードする方法を次に示します。モバイルデバイスでは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="76f5c-117">Here's what downloading a blocked file looks like on a mobile device:</span></span>

![OneDrive for Business でブロックされたファイルをダウンロードする](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

<span data-ttu-id="76f5c-119">SharePoint Online 管理者は、悪意のあるファイルをユーザーがダウンロードできないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="76f5c-119">SharePoint Online admins can prevent people from downloading malicious files.</span></span> <span data-ttu-id="76f5c-120">手順については、「 [SharePoint Online PowerShell を使用してユーザーが悪意のあるファイルをダウンロードするのを防ぐ](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76f5c-120">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>

<span data-ttu-id="76f5c-121">ファイルが悪意のあるものとして検出された場合のユーザーの操作の詳細については、「 [SharePoint Online、OneDrive、または Microsoft Teams で悪意のあるファイルが検出された場合の対処](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76f5c-121">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span>

## <a name="view-information-about-malicious-files-detected-by-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="76f5c-122">SharePoint、OneDrive、Microsoft Teams の ATP によって検出された悪意のあるファイルに関する情報を表示する</span><span class="sxs-lookup"><span data-stu-id="76f5c-122">View information about malicious files detected by ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="76f5c-123">ATP で悪意があると識別されたファイルは、 [Office 365 Advanced Threat Protection](view-reports-for-atp.md) および [エクスプローラ (およびリアルタイム検出)](threat-explorer.md)のレポートで表示されます。</span><span class="sxs-lookup"><span data-stu-id="76f5c-123">Files that are identified as malicious by ATP will show up in [reports for Office 365 Advanced Threat Protection](view-reports-for-atp.md) and in [Explorer (and real-time detections)](threat-explorer.md).</span></span>

<span data-ttu-id="76f5c-124">2018年5月の時点で、ファイルが ATP によって悪意のあるものと識別されると、ファイルは検疫でも利用できます。</span><span class="sxs-lookup"><span data-stu-id="76f5c-124">As of May 2018, when a file is identified as malicious by ATP, the file is also available in quarantine.</span></span> <span data-ttu-id="76f5c-125">詳細については、「 [セキュリティ & コンプライアンスセンターを使用して検疫済みファイルを管理する](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76f5c-125">For more information, see [Use the Security & Compliance Center to manage quarantined files](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files).</span></span>

## <a name="keep-these-points-in-mind"></a><span data-ttu-id="76f5c-126">これらの点を念頭に置いてください。</span><span class="sxs-lookup"><span data-stu-id="76f5c-126">Keep these points in mind</span></span>

- <span data-ttu-id="76f5c-127">ATP では、SharePoint Online、OneDrive for Business、または Microsoft Teams のすべてのファイルがスキャンされるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="76f5c-127">ATP will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="76f5c-128">この動作は仕様です。</span><span class="sxs-lookup"><span data-stu-id="76f5c-128">This is by design.</span></span> <span data-ttu-id="76f5c-129">ファイルは非同期でスキャンされます。</span><span class="sxs-lookup"><span data-stu-id="76f5c-129">Files are scanned asynchronously.</span></span> <span data-ttu-id="76f5c-130">このプロセスでは、スマートヒューリスティックおよび脅威信号と共に、共有とゲストのアクティビティイベントを使用して、悪意のあるファイルを特定します。</span><span class="sxs-lookup"><span data-stu-id="76f5c-130">The process uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="76f5c-131">SharePoint サイトが [モダンな環境](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience)を使用するように構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="76f5c-131">Make sure your SharePoint sites are configured to use the [Modern experience](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience).</span></span> <span data-ttu-id="76f5c-132">ATP 保護は、モダンな表示とクラシック表示のどちらを使用するかに適用されます。ただし、ファイルがブロックされているという視覚インジケーターは、モダンな環境でのみ利用可能です。</span><span class="sxs-lookup"><span data-stu-id="76f5c-132">ATP protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are available only in the Modern experience.</span></span>

- <span data-ttu-id="76f5c-133">SharePoint、OneDrive、Microsoft Teams 用の ATP は、組織の全体的な脅威保護戦略に含まれています。これには、Exchange Online Protection (EOP) のスパム対策とマルウェア対策保護、および Office 365 ATP の安全なリンクと安全な添付ファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="76f5c-133">ATP for SharePoint, OneDrive, and Microsoft Teams is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection in Exchange Online Protection (EOP), as well as Safe Links and Safe Attachments in Office 365 ATP.</span></span> <span data-ttu-id="76f5c-134">詳細については、「 [Office 365 の脅威から保護](protect-against-threats.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76f5c-134">To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>
