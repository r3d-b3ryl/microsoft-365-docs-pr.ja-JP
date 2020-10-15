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
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: SharePoint Online、OneDrive for Business、Microsoft Teams でのファイル用 Office 365 Advanced Threat Protection についての詳細情報。
ms.openlocfilehash: e536809c74abbe87e1250acda3f3922180cfae97
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446265"
---
# <a name="atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="8d485-103">SharePoint、OneDrive、Microsoft Teams 用の ATP</span><span class="sxs-lookup"><span data-stu-id="8d485-103">ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8d485-104">[Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) での SharePoint、OneDrive、Microsoft Teams の ATP は、[Microsoft 365 の共通のウイルス検出エンジン](virus-detection-in-spo.md) によってアップロード時に既にスキャンされているファイルに対して、追加の保護レイヤーを提供します。</span><span class="sxs-lookup"><span data-stu-id="8d485-104">ATP for SharePoint, OneDrive, and Microsoft Teams in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) provides an additional layer of protection for files that have already been scanned at upload time by the [common virus detection engine in Microsoft 365](virus-detection-in-spo.md).</span></span> <span data-ttu-id="8d485-105">SharePoint、OneDrive、および Microsoft Teams 用の ATP は、チーム サイトとドキュメント ライブラリに悪意があると特定されたファイルを検出してブロックします。</span><span class="sxs-lookup"><span data-stu-id="8d485-105">ATP for SharePoint, OneDrive, and Microsoft Teams helps detect and block existing files that are identified as malicious in team sites and document libraries.</span></span>

<span data-ttu-id="8d485-106">規定では、SharePoint、OneDrive、Microsoft Teams の ATP は有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="8d485-106">ATP for SharePoint, OneDrive, and Microsoft Teams is not enabled by default.</span></span> <span data-ttu-id="8d485-107">有効にするには、[[SharePoint、OneDrive、および Microsoft Teams 用の ATP を有効にする]](turn-on-atp-for-spo-odb-and-teams.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d485-107">To turn it on, see [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

## <a name="how-atp-for-sharepoint-onedrive-and-microsoft-teams-works"></a><span data-ttu-id="8d485-108">SharePoint、OneDrive、Microsoft Teams 用の ATP を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="8d485-108">How ATP for SharePoint, OneDrive, and Microsoft Teams works</span></span>

<span data-ttu-id="8d485-109">SharePoint、OneDrive、Microsoft Teams 用 ATP が有効になっていて、ファイルが悪意のあるものと認識されると、ファイルはファイル ストアと直接統合してロックされます。</span><span class="sxs-lookup"><span data-stu-id="8d485-109">When ATP for SharePoint, OneDrive, and Microsoft Teams is enabled and identifies a file as malicious, the file is locked using direct integration with the file stores.</span></span> <span data-ttu-id="8d485-110">次の画像は、ライブラリで検出された悪意のあるファイルの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="8d485-110">The following image shows an example of a malicious file detected in a library.</span></span>

![悪意があることが検出された OneDrive for Business のファイル](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

<span data-ttu-id="8d485-112">ブロックされたファイルは、ドキュメント ライブラリおよび Web、モバイル、もしくはデスクトップ アプリケーションにまだ表示されていますが、ファイルを開く、コピー、移動、または共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="8d485-112">Although the blocked file is still listed in the document library and in web, mobile, or desktop applications, people can't open, copy, move, or share the file.</span></span> <span data-ttu-id="8d485-113">ただし、ブロックされたファイルは削除できます。</span><span class="sxs-lookup"><span data-stu-id="8d485-113">But they can delete the blocked file.</span></span>

<span data-ttu-id="8d485-114">次に、モバイル デバイスでブロックされたファイルがどのように表示されるかという例を示します。</span><span class="sxs-lookup"><span data-stu-id="8d485-114">Here's an example of what a blocked file looks like on a mobile device:</span></span>

![OneDrive モバイル アプリで OneDrive for Business からブロックされたファイルを削除する](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

<span data-ttu-id="8d485-116">規定では、ユーザーはブロックされたファイルをダウンロードすることが可能です。</span><span class="sxs-lookup"><span data-stu-id="8d485-116">By default, people can download a blocked file.</span></span> <span data-ttu-id="8d485-117">次に、モバイル デバイスで、ブロックされたファイルをダウンロードするのはどのように表示されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="8d485-117">Here's what downloading a blocked file looks like on a mobile device:</span></span>

![OneDrive for Business でブロックされたファイルをダウンロードする](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

<span data-ttu-id="8d485-119">SharePoint Online 管理者は、ユーザーが悪意のあるファイルをダウンロードできないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="8d485-119">SharePoint Online admins can prevent people from downloading malicious files.</span></span> <span data-ttu-id="8d485-120">手順については、「[SharePoint Online PowerShell を使用して悪意のあるファイルをユーザーがダウンロードできないようにする ](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d485-120">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>

<span data-ttu-id="8d485-121">ファイルが悪意のあるものであることが検出された場合のユーザー エクスペリエンスの詳細については、「[SharePoint Online、OneDrive、または Microsoft Teams に悪意のあるファイルが見つかった場合の対処方法](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d485-121">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span>

## <a name="view-information-about-malicious-files-detected-by-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="8d485-122">SharePoint、OneDrive、Microsoft Teams 用の ATP によって検出された悪意のあるファイルに関する情報を表示する</span><span class="sxs-lookup"><span data-stu-id="8d485-122">View information about malicious files detected by ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="8d485-123">ATP によって悪意があると識別されたファイルは、「[Office 365 Advanced Threat Protection のレポート](view-reports-for-atp.md)」と、「[エクスプローラー (およびリアルタイム検出) ](threat-explorer.md) に表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d485-123">Files that are identified as malicious by ATP will show up in [reports for Office 365 Advanced Threat Protection](view-reports-for-atp.md) and in [Explorer (and real-time detections)](threat-explorer.md).</span></span>

<span data-ttu-id="8d485-124">2018 年 5 月の時点では、ファイルが ATP によって悪意のあるものと識別されると、ファイルは検疫でも利用することができます。</span><span class="sxs-lookup"><span data-stu-id="8d485-124">As of May 2018, when a file is identified as malicious by ATP, the file is also available in quarantine.</span></span> <span data-ttu-id="8d485-125">詳細については、「[セキュリティ/コンプライアンス センターを使用して検疫済みファイルを管理する](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d485-125">For more information, see [Use the Security & Compliance Center to manage quarantined files](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files).</span></span>

## <a name="keep-these-points-in-mind"></a><span data-ttu-id="8d485-126">留意事項</span><span class="sxs-lookup"><span data-stu-id="8d485-126">Keep these points in mind</span></span>

- <span data-ttu-id="8d485-127">ATP は、SharePoint Online、OneDrive for Business、または Microsoft Teams のすべてのファイルを 1 つずつスキャンするわけではありません。</span><span class="sxs-lookup"><span data-stu-id="8d485-127">ATP will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="8d485-128">これは仕様によるものです。</span><span class="sxs-lookup"><span data-stu-id="8d485-128">This is by design.</span></span> <span data-ttu-id="8d485-129">ファイルは非同期でスキャンされます。</span><span class="sxs-lookup"><span data-stu-id="8d485-129">Files are scanned asynchronously.</span></span> <span data-ttu-id="8d485-130">このプロセスは、スマート ヒューリスティックおよび脅威のシグナルと共に、共有とゲストのアクティビティ イベントを使用して、悪質なファイルを特定します。 </span><span class="sxs-lookup"><span data-stu-id="8d485-130">The process uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="8d485-131">SharePoint サイトが[モダンな環境](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience)を使用するために構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8d485-131">Make sure your SharePoint sites are configured to use the [Modern experience](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience).</span></span> <span data-ttu-id="8d485-132">ATP 保護は、モダンな環境、またはクラシック表示のどちらかが使用されるように適用しますが、ファイルがブロックされている視覚的インジケーターは、モダンな環境でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="8d485-132">ATP protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are available only in the Modern experience.</span></span>

- <span data-ttu-id="8d485-133">SharePoint、OneDrive、Microsoft Teams 用の ATP は、組織の全体的な脅威保護戦略の一部であり、Exchange Online Protection (EOP) でスパム対策やマルウェア保護対策、そしておよび Office 365 ATP の安全なリンクと安全な添付ファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8d485-133">ATP for SharePoint, OneDrive, and Microsoft Teams is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection in Exchange Online Protection (EOP), as well as Safe Links and Safe Attachments in Office 365 ATP.</span></span> <span data-ttu-id="8d485-134">詳細については、「[Office 365 で脅威から保護する](protect-against-threats.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8d485-134">To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>
