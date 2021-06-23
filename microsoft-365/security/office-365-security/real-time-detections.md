---
title: Microsoft Defender の脅威エクスプローラーとリアルタイム検出の基本Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: エクスプローラーまたはリアルタイム検出を使用して、脅威を効率的に調査して対応します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4d0a9ba7ee40c8ad97df745a20d6b5b3314bb3d8
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083190"
---
# <a name="explorer-and-real-time-detections-basics"></a><span data-ttu-id="01f51-103">エクスプローラーとリアルタイム検出の基本</span><span class="sxs-lookup"><span data-stu-id="01f51-103">Explorer and Real-time detections basics</span></span>

<span data-ttu-id="01f51-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="01f51-104">**Applies to**</span></span>
- [<span data-ttu-id="01f51-105">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="01f51-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="01f51-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="01f51-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="01f51-107">この記事の内容:</span><span class="sxs-lookup"><span data-stu-id="01f51-107">In this article:</span></span>

- [<span data-ttu-id="01f51-108">エクスプローラーとリアルタイムの検出の違い</span><span class="sxs-lookup"><span data-stu-id="01f51-108">Differences between Explorer and Real-time detections</span></span>](#differences-between-explorer-and-real-time-detections)
- [<span data-ttu-id="01f51-109">必要なライセンスとアクセス許可</span><span class="sxs-lookup"><span data-stu-id="01f51-109">Required licenses and permissions</span></span>](#required-licenses-and-permissions)

> [!NOTE]
> <span data-ttu-id="01f51-110">これは **、Explorer (** 脅威エクスプローラーとも呼ばれる) 、電子メール セキュリティ、**エクスプローラー** とリアルタイム検出の基本 (ツールの違い、操作に必要なアクセス許可など) の **3** 記事シリーズの一部です。</span><span class="sxs-lookup"><span data-stu-id="01f51-110">This is part of a **3-article series** on **Explorer (also known as Threat Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="01f51-111">このシリーズの他の 2 つの記事は [、Explorer での](threat-hunting-in-threat-explorer.md) 脅威の検出とエクスプローラー [を使用したメール セキュリティです](email-security-in-microsoft-defender.md)。</span><span class="sxs-lookup"><span data-stu-id="01f51-111">The other two articles in this series are [Threat hunting in Explorer](threat-hunting-in-threat-explorer.md) and [Email security with Explorer](email-security-in-microsoft-defender.md).</span></span>

<span data-ttu-id="01f51-112">この記事では、エクスプローラーとリアルタイム検出レポートの違い、および必要なライセンスとアクセス許可について説明します。</span><span class="sxs-lookup"><span data-stu-id="01f51-112">This article explains the difference between Explorer and real-time detections reporting, and the licenses and permissions that are required.</span></span>

<span data-ttu-id="01f51-113">組織に microsoft [Defender for Office 365](defender-for-office-365.md)がある場合、アクセス許可 [](#required-licenses-and-permissions)がある場合は、エクスプローラー **(脅威\*\*\*\*エクスプローラーとも呼** ばれる) またはリアルタイム検出を使用して、脅威を検出して修復できます。</span><span class="sxs-lookup"><span data-stu-id="01f51-113">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [permissions](#required-licenses-and-permissions), you can use **Explorer** (also known as **Threat Explorer**) or **Real-time detections** to detect and remediate threats.</span></span>

<span data-ttu-id="01f51-114">[ポータル( Microsoft 365 Defender] で、[電子メール グループ&] に移動し、[エクスプローラー] または [リアルタイム検出] <https://security.microsoft.com> **を選択します**。 </span><span class="sxs-lookup"><span data-stu-id="01f51-114">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), go to **Email & collaboration**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>

<span data-ttu-id="01f51-115">これらのツールで以下のことができます。</span><span class="sxs-lookup"><span data-stu-id="01f51-115">With these tools, you can:</span></span>

- <span data-ttu-id="01f51-116">セキュリティ機能によって検出されたマルウェアMicrosoft 365参照してください。</span><span class="sxs-lookup"><span data-stu-id="01f51-116">See malware detected by Microsoft 365 security features.</span></span>
- <span data-ttu-id="01f51-117">フィッシング URL を表示し、[評決データ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01f51-117">View phishing URL and click verdict data.</span></span>
- <span data-ttu-id="01f51-118">エクスプローラーでビューから自動調査と応答プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="01f51-118">Start an automated investigation and response process from a view in Explorer.</span></span>
- <span data-ttu-id="01f51-119">悪意のあるメールなどについて調査します。</span><span class="sxs-lookup"><span data-stu-id="01f51-119">Investigate malicious email, and more.</span></span>

<span data-ttu-id="01f51-120">詳細については、「Explorer を使用 [したメール セキュリティ」を参照してください](email-security-in-microsoft-defender.md)。</span><span class="sxs-lookup"><span data-stu-id="01f51-120">For more information, see [Email security with Explorer](email-security-in-microsoft-defender.md).</span></span>

## <a name="differences-between-explorer-and-real-time-detections"></a><span data-ttu-id="01f51-121">エクスプローラーとリアルタイムの検出の違い</span><span class="sxs-lookup"><span data-stu-id="01f51-121">Differences between Explorer and Real-time detections</span></span>

- <span data-ttu-id="01f51-122">*リアルタイム検出は、Defender* でプラン 1 で使用できるレポート Office 365ツールです。</span><span class="sxs-lookup"><span data-stu-id="01f51-122">*Real-time detections* is a reporting tool available in Defender for Office 365 Plan 1.</span></span> <span data-ttu-id="01f51-123">*Threat Explorer* は、Defender で利用可能な脅威の検出と修復ツールで、Office 365 2 です。</span><span class="sxs-lookup"><span data-stu-id="01f51-123">*Threat Explorer* is a threat hunting and remediation tool available in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="01f51-124">リアルタイム検出レポートを使用すると、リアルタイムで検出を表示できます。</span><span class="sxs-lookup"><span data-stu-id="01f51-124">The Real-time detections report allows you to view detections in real time.</span></span> <span data-ttu-id="01f51-125">脅威エクスプローラーも同様にこれを実行しますが、攻撃キャンペーンの強調表示など、特定の攻撃に関する追加の詳細を提供し、セキュリティ運用チームに脅威を修復する機能 (自動調査[](automated-investigation-response-office.md)と応答調査のトリガーを含む) を提供します。</span><span class="sxs-lookup"><span data-stu-id="01f51-125">Threat Explorer does this as well, but it provides additional details for a given attack, such as highlighting attack campaigns, and gives security operations teams the ability to remediate threats (including triggering an [Automated Investigation and Response investigation](automated-investigation-response-office.md)).</span></span>
- <span data-ttu-id="01f51-126">すべての *電子メール ビュー* は脅威エクスプローラーで使用できますが、リアルタイム検出レポートには含まれません。</span><span class="sxs-lookup"><span data-stu-id="01f51-126">An *All email* view is available in Threat Explorer, but not included in the Real-time detections report.</span></span>
- <span data-ttu-id="01f51-127">豊富なフィルター機能と修復アクションは、Threat Explorer に含まれています。</span><span class="sxs-lookup"><span data-stu-id="01f51-127">Rich filtering capabilities and remediation actions are included in Threat Explorer.</span></span> <span data-ttu-id="01f51-128">詳細については[、「Microsoft Defender for Office 365 サービスの説明:](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)Defender 全体の機能の可用性」を参照してください。Office 365してください。</span><span class="sxs-lookup"><span data-stu-id="01f51-128">For more information, see [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="01f51-129">必要なライセンスとアクセス許可</span><span class="sxs-lookup"><span data-stu-id="01f51-129">Required licenses and permissions</span></span>

<span data-ttu-id="01f51-130">エクスプローラーまたは[リアルタイム検出のいずれかをOffice 365](defender-for-office-365.md)するには、Microsoft Defender が必要です。</span><span class="sxs-lookup"><span data-stu-id="01f51-130">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use either of Explorer or Real-time detections:</span></span>

- <span data-ttu-id="01f51-131">エクスプローラーは、プラン 2 の Defender にのみOffice 365されます。</span><span class="sxs-lookup"><span data-stu-id="01f51-131">Explorer is only included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="01f51-132">リアルタイム検出レポートは、Defender for Office 365プラン 1 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="01f51-132">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>

<span data-ttu-id="01f51-133">セキュリティ運用チームは、Office 365 の Defender によって保護される必要があるすべてのユーザーにライセンスを割り当て、エクスプローラーとリアルタイムの検出では、ライセンスを持つユーザーの検出データが表示される点に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01f51-133">Security Operations teams need to assign licenses for all users who should be protected by Defender for Office 365 and be aware that Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="01f51-134">エクスプローラーまたはリアルタイム検出を *表示* および使用するには、次のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="01f51-134">To view and use Explorer *or* Real-time detections, you need the following permissions:</span></span>

- <span data-ttu-id="01f51-135">[Defender for Office 365:</span><span class="sxs-lookup"><span data-stu-id="01f51-135">In Defender for Office 365:</span></span>
  - <span data-ttu-id="01f51-136">組織管理</span><span class="sxs-lookup"><span data-stu-id="01f51-136">Organization Management</span></span>
  - <span data-ttu-id="01f51-137">セキュリティ管理者 (この管理者は、管理者センター Azure Active Directory割り当てることができます ( <https://aad.portal.azure.com> )</span><span class="sxs-lookup"><span data-stu-id="01f51-137">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="01f51-138">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="01f51-138">Security Reader</span></span>
- <span data-ttu-id="01f51-139">次のExchange Online。</span><span class="sxs-lookup"><span data-stu-id="01f51-139">In Exchange Online:</span></span>
  - <span data-ttu-id="01f51-140">組織の管理</span><span class="sxs-lookup"><span data-stu-id="01f51-140">Organization Management</span></span>
  - <span data-ttu-id="01f51-141">表示専用組織の管理</span><span class="sxs-lookup"><span data-stu-id="01f51-141">View-Only Organization Management</span></span>
  - <span data-ttu-id="01f51-142">"View-Only Recipients/表示専用受信者"</span><span class="sxs-lookup"><span data-stu-id="01f51-142">View-Only Recipients</span></span>
  - <span data-ttu-id="01f51-143">コンプライアンス管理</span><span class="sxs-lookup"><span data-stu-id="01f51-143">Compliance Management</span></span>

<span data-ttu-id="01f51-144">役割とアクセス許可の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01f51-144">To learn more about roles and permissions, see the following articles:</span></span>

- [<span data-ttu-id="01f51-145">Microsoft 365 Defender ポータルのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="01f51-145">Permissions in the Microsoft 365 Defender portal</span></span>](permissions-microsoft-365-security-center.md)
- [<span data-ttu-id="01f51-146">Exchange Online のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="01f51-146">Permissions in Exchange Online</span></span>](/e/exchange/permissions-exo/permissions-exo)

## <a name="more-information"></a><span data-ttu-id="01f51-147">詳細</span><span class="sxs-lookup"><span data-stu-id="01f51-147">More information</span></span>

- [<span data-ttu-id="01f51-148">脅威エクスプローラーは、電子メール エンティティ ページで電子メールの詳細を収集します。</span><span class="sxs-lookup"><span data-stu-id="01f51-148">Threat Explorer collect email details on the email entity page</span></span>](mdo-email-entity-page.md)
- [<span data-ttu-id="01f51-149">配信された悪意のあるメールの検索と調査</span><span class="sxs-lookup"><span data-stu-id="01f51-149">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="01f51-150">オンライン、オンライン、SharePoint、およびOneDriveで検出された悪意のあるMicrosoft Teams</span><span class="sxs-lookup"><span data-stu-id="01f51-150">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md)
- [<span data-ttu-id="01f51-151">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="01f51-151">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="01f51-152">Microsoft Threat Protection での自動調査および対応</span><span class="sxs-lookup"><span data-stu-id="01f51-152">Automated investigation and response in Microsoft Threat Protection</span></span>](automated-investigation-response-office.md)
