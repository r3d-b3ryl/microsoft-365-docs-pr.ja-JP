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
description: Microsoft Defender for Office 365オンライン、SharePoint、OneDrive for Business、およびMicrosoft Teams。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7aa375020ce05ca1d484bb7ed18b8cf7a6e7d04e
ms.sourcegitcommit: ac3e9ccb7b43a42e600af8f44e6f30019533faeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/15/2021
ms.locfileid: "52932844"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="ecb9a-103">SPO、OneDrive、Teams 用の安全な添付ファイル機能</span><span class="sxs-lookup"><span data-stu-id="ecb9a-103">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ecb9a-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="ecb9a-104">**Applies to**</span></span>
- [<span data-ttu-id="ecb9a-105">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="ecb9a-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ecb9a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ecb9a-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="ecb9a-107">セーフ[microsoft Defender](whats-new-in-defender-for-office-365.md) for Office 365 の SharePoint、OneDrive、および Microsoft Teams の添付ファイルは、Microsoft 365 の一般的なウイルス検出エンジンによってアップロード時に既にスキャンされているファイルに対する追加の保護層を[提供](virus-detection-in-spo.md)します。</span><span class="sxs-lookup"><span data-stu-id="ecb9a-107">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams in [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md) provides an additional layer of protection for files that have already been scanned at upload time by the [common virus detection engine in Microsoft 365](virus-detection-in-spo.md).</span></span> <span data-ttu-id="ecb9a-108">セーフSharePoint、OneDrive、Microsoft Teamsの添付ファイルは、チーム サイトやドキュメント ライブラリで悪意のあるファイルとして識別される既存のファイルを検出およびブロックするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ecb9a-108">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams helps detect and block existing files that are identified as malicious in team sites and document libraries.</span></span>

<span data-ttu-id="ecb9a-109">セーフ既定ではSharePoint、OneDrive、Microsoft Teamsの添付ファイルは有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="ecb9a-109">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is not enabled by default.</span></span> <span data-ttu-id="ecb9a-110">有効にする方法については、「添付ファイルを[有効にするセーフ」をSharePoint、OneDrive、およびMicrosoft Teams。](turn-on-mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="ecb9a-110">To turn it on, see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).</span></span>

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a><span data-ttu-id="ecb9a-111">セーフ、SharePoint、およびOneDriveの添付ファイルのMicrosoft Teams方法</span><span class="sxs-lookup"><span data-stu-id="ecb9a-111">How Safe Attachments for SharePoint, OneDrive, and Microsoft Teams works</span></span>

<span data-ttu-id="ecb9a-112">SharePoint セーフ、OneDrive、Microsoft Teams の添付ファイルを有効にし、ファイルを悪意のあるファイルとして識別すると、ファイルストアとの直接統合を使用してファイルがロックされます。</span><span class="sxs-lookup"><span data-stu-id="ecb9a-112">When Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is enabled and identifies a file as malicious, the file is locked using direct integration with the file stores.</span></span> <span data-ttu-id="ecb9a-113">次の画像は、ライブラリで検出された悪意のあるファイルの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="ecb9a-113">The following image shows an example of a malicious file detected in a library.</span></span>

![悪意のあるファイルOneDrive for Business検出されたファイルを含むファイル](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

<span data-ttu-id="ecb9a-115">ブロックされたファイルは、ドキュメント ライブラリと Web、モバイル、またはデスクトップ アプリケーションに引き続き表示されますが、ユーザーはファイルを開く、コピー、移動、または共有できません。</span><span class="sxs-lookup"><span data-stu-id="ecb9a-115">Although the blocked file is still listed in the document library and in web, mobile, or desktop applications, people can't open, copy, move, or share the file.</span></span> <span data-ttu-id="ecb9a-116">ただし、ブロックされたファイルは削除できます。</span><span class="sxs-lookup"><span data-stu-id="ecb9a-116">But they can delete the blocked file.</span></span>

<span data-ttu-id="ecb9a-117">モバイル デバイスでブロックされたファイルの外観の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ecb9a-117">Here's an example of what a blocked file looks like on a mobile device:</span></span>

![ブロックされたファイルをモバイル アプリOneDrive for BusinessからOneDrive削除する](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

<span data-ttu-id="ecb9a-119">既定では、ユーザーはブロックされたファイルをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="ecb9a-119">By default, people can download a blocked file.</span></span> <span data-ttu-id="ecb9a-120">ブロックされたファイルをモバイル デバイスでダウンロードする方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ecb9a-120">Here's what downloading a blocked file looks like on a mobile device:</span></span>

![ブロックされたファイルをダウンロードする方法OneDrive for Business](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

<span data-ttu-id="ecb9a-122">SharePointオンライン管理者は、悪意のあるファイルをダウンロードするユーザーを防ぐ可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ecb9a-122">SharePoint Online admins can prevent people from downloading malicious files.</span></span> <span data-ttu-id="ecb9a-123">手順については、「ユーザーが悪意のある[ファイルをダウンロードSharePointオンライン PowerShell を使用する」を参照してください](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)。</span><span class="sxs-lookup"><span data-stu-id="ecb9a-123">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>

<span data-ttu-id="ecb9a-124">ファイルが悪意のあるファイルとして検出された場合のユーザー エクスペリエンスの詳細については[、「SharePoint Online、OneDrive、](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)または Microsoft Teams で悪意のあるファイルが見つかった場合の操作」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ecb9a-124">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span>

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="ecb9a-125">[添付ファイル] で検出された悪意のあるファイルセーフ、SharePoint、OneDrive、Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ecb9a-125">View information about malicious files detected by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="ecb9a-126">SharePoint、OneDrive、および Microsoft Teams の セーフ 添付ファイルによって悪意のあるファイルとして識別されたファイルは[、microsoft Defender](view-reports-for-mdo.md) for Office 365 および Explorer (およびリアルタイム検出[)](threat-explorer.md)のレポートに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ecb9a-126">Files that are identified as malicious by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams will show up in [reports for Microsoft Defender for Office 365](view-reports-for-mdo.md) and in [Explorer (and real-time detections)](threat-explorer.md).</span></span>

<span data-ttu-id="ecb9a-127">SharePoint、OneDrive、および Microsoft Teams の セーフ 添付ファイルによってファイルが悪意のあるファイルとして識別された 2018 年 5 月現在、ファイルは検疫でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="ecb9a-127">As of May 2018, when a file is identified as malicious by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, the file is also available in quarantine.</span></span> <span data-ttu-id="ecb9a-128">詳細については、「Defender[で検疫済みファイルを管理する」を参照Office 365。](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="ecb9a-128">For more information, see [Manage quarantined files in Defender for Office 365](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365).</span></span>

## <a name="keep-these-points-in-mind"></a><span data-ttu-id="ecb9a-129">これらの点に気を付ける</span><span class="sxs-lookup"><span data-stu-id="ecb9a-129">Keep these points in mind</span></span>

- <span data-ttu-id="ecb9a-130">Defender for Office 365は、オンライン、オンライン、OneDrive for Business、またはSharePointのすべてのファイルをMicrosoft Teams。</span><span class="sxs-lookup"><span data-stu-id="ecb9a-130">Defender for Office 365 will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="ecb9a-131">この動作は仕様です。</span><span class="sxs-lookup"><span data-stu-id="ecb9a-131">This is by design.</span></span> <span data-ttu-id="ecb9a-132">ファイルは非同期的にスキャンされます。</span><span class="sxs-lookup"><span data-stu-id="ecb9a-132">Files are scanned asynchronously.</span></span> <span data-ttu-id="ecb9a-133">このプロセスでは、共有およびゲスト アクティビティ イベントとスマート ヒューリスティックと脅威シグナルを使用して、悪意のあるファイルを識別します。</span><span class="sxs-lookup"><span data-stu-id="ecb9a-133">The process uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="ecb9a-134">モダン エクスペリエンスを使用SharePointサイトが構成されていることを[確認します](/sharepoint/guide-to-sharepoint-modern-experience)。</span><span class="sxs-lookup"><span data-stu-id="ecb9a-134">Make sure your SharePoint sites are configured to use the [Modern experience](/sharepoint/guide-to-sharepoint-modern-experience).</span></span> <span data-ttu-id="ecb9a-135">モダン Office 365クラシック ビューを使用するかどうかは、セキュリティ保護用の Defender が適用されます。ただし、ファイルがブロックされている視覚的なインジケーターは、モダン エクスペリエンスでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ecb9a-135">Defender for Office 365 protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are available only in the Modern experience.</span></span>

- <span data-ttu-id="ecb9a-136">セーフSharePoint、OneDrive、および Microsoft Teams の添付ファイルは、Exchange Online Protection (EOP) のスパム対策とマルウェア対策保護、および microsoft Defender for Office 365 の セーフ リンクと セーフ 添付ファイルを含む、組織の全体的な脅威保護戦略の一部です。</span><span class="sxs-lookup"><span data-stu-id="ecb9a-136">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection in Exchange Online Protection (EOP), as well as Safe Links and Safe Attachments in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="ecb9a-137">詳細については、「脅威から[保護する」を参照Office 365。](protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="ecb9a-137">To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>
