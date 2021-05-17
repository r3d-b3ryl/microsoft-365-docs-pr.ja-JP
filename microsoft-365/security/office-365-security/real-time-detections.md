---
title: Microsoft Defender の脅威エクスプローラーとリアルタイム検出Office 365
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
ms.openlocfilehash: 7ab7b5731d121106d930868b03330d4ac7befd77
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300157"
---
# <a name="threat-explorer-and-real-time-detections-basics"></a><span data-ttu-id="2fb3a-103">脅威エクスプローラーおよびリアルタイムの検出の基本</span><span class="sxs-lookup"><span data-stu-id="2fb3a-103">Threat Explorer and Real-time detections basics</span></span>

<span data-ttu-id="2fb3a-104">この記事の内容:</span><span class="sxs-lookup"><span data-stu-id="2fb3a-104">In this article:</span></span>

- [<span data-ttu-id="2fb3a-105">脅威エクスプローラーとリアルタイム検出の違い</span><span class="sxs-lookup"><span data-stu-id="2fb3a-105">Differences between Threat Explorer and Real-time detections</span></span>](#differences-between-threat-explorer-and-real-time-detections)<br/>
- [<span data-ttu-id="2fb3a-106">必要なライセンスとアクセス許可</span><span class="sxs-lookup"><span data-stu-id="2fb3a-106">Required licenses and permissions</span></span>](#required-licenses-and-permissions)

> [!NOTE]
> <span data-ttu-id="2fb3a-107">これは、Threat **Explorer (Explorer)** 、電子メール セキュリティ、**エクスプローラー** とリアルタイム検出の基本 (ツールの違い、操作に必要なアクセス許可など) に関する **3** 記事シリーズの一部です。</span><span class="sxs-lookup"><span data-stu-id="2fb3a-107">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="2fb3a-108">このシリーズの他の 2 つの記事は、Threat Explorer での脅威の検出と [、](threat-hunting-in-threat-explorer.md) 脅威エクスプローラーを [使用したメール セキュリティです](email-security-in-microsoft-defender.md)。</span><span class="sxs-lookup"><span data-stu-id="2fb3a-108">The other two articles in this series are [Threat hunting in Threat Explorer](threat-hunting-in-threat-explorer.md) and [Email security with Threat Explorer](email-security-in-microsoft-defender.md).</span></span>

<span data-ttu-id="2fb3a-109">この記事では、脅威の調査とリアルタイムの検出レポートの違い、および必要なライセンスとアクセス許可について説明します。</span><span class="sxs-lookup"><span data-stu-id="2fb3a-109">This article explains the difference between threat exploration and real-time detections reporting, and the licenses and permissions that are required.</span></span>

<span data-ttu-id="2fb3a-110">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="2fb3a-110">**Applies to**</span></span>
- [<span data-ttu-id="2fb3a-111">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="2fb3a-111">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="2fb3a-112">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2fb3a-112">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="2fb3a-113">組織に Office [365](defender-for-office-365.md)用の Microsoft Defender を使用 [](#required-licenses-and-permissions)し、アクセス許可がある場合は、脅威エクスプローラー **(エクスプローラー** と **呼** ばれる) またはリアルタイム検出を使用して、脅威を検出して修復できます。</span><span class="sxs-lookup"><span data-stu-id="2fb3a-113">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [permissions](#required-licenses-and-permissions), you can use **Threat Explorer** (called **Explorer**) or **Real-time detections** to detect and remediate threats.</span></span>

<span data-ttu-id="2fb3a-114">[セキュリティ **& コンプライアンス** センター] で、[脅威の管理] に移動し、[**エクスプローラー**  ] または [リアルタイム検出]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="2fb3a-114">In the **Security & Compliance Center**, go to **Threat management**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>

<br>

****

|<span data-ttu-id="2fb3a-115">Microsoft Defender for Office 365 プラン 2 では、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2fb3a-115">With Microsoft Defender for Office 365 Plan 2, you see:</span></span>|<span data-ttu-id="2fb3a-116">Microsoft Defender for Office 365 プラン 1 では、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2fb3a-116">With Microsoft Defender for Office 365 Plan 1, you see:</span></span>|
|---|---|
|![脅威エクスプローラー](../../media/threatmgmt-explorer.png)|![リアルタイムの検出](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="2fb3a-119">これらのツールで以下のことができます。</span><span class="sxs-lookup"><span data-stu-id="2fb3a-119">With these tools, you can:</span></span>

- <span data-ttu-id="2fb3a-120">Microsoft 365 のセキュリティ機能によって検出されたマルウェアを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fb3a-120">See malware detected by Microsoft 365 security features.</span></span>
- <span data-ttu-id="2fb3a-121">フィッシング URL を表示し、[評決データ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2fb3a-121">View phishing URL and click verdict data.</span></span>
- <span data-ttu-id="2fb3a-122">エクスプローラーでビューから自動調査と応答プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="2fb3a-122">Start an automated investigation and response process from a view in Explorer.</span></span>
- <span data-ttu-id="2fb3a-123">悪意のあるメールなどについて調査します。</span><span class="sxs-lookup"><span data-stu-id="2fb3a-123">Investigate malicious email, and more.</span></span>

<span data-ttu-id="2fb3a-124">詳細については、「Threat [Explorer を使用したメール セキュリティ」を参照してください](email-security-in-microsoft-defender.md)。</span><span class="sxs-lookup"><span data-stu-id="2fb3a-124">For more information, see [Email security with Threat Explorer](email-security-in-microsoft-defender.md).</span></span>

## <a name="differences-between-threat-explorer-and-real-time-detections"></a><span data-ttu-id="2fb3a-125">脅威エクスプローラーとリアルタイム検出の違い</span><span class="sxs-lookup"><span data-stu-id="2fb3a-125">Differences between Threat Explorer and Real-time detections</span></span>

- <span data-ttu-id="2fb3a-126">*リアルタイム検出は、Defender* で 365 プラン 1 で使用Officeツールです。</span><span class="sxs-lookup"><span data-stu-id="2fb3a-126">*Real-time detections* is a reporting tool available in Defender for Office 365 Plan 1.</span></span> <span data-ttu-id="2fb3a-127">*Threat Explorer* は、Defender で 365 プラン 2 の脅威Office修復ツールです。</span><span class="sxs-lookup"><span data-stu-id="2fb3a-127">*Threat Explorer* is a threat hunting and remediation tool available in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="2fb3a-128">リアルタイム検出レポートを使用すると、リアルタイムで検出を表示できます。</span><span class="sxs-lookup"><span data-stu-id="2fb3a-128">The Real-time detections report allows you to view detections in real time.</span></span> <span data-ttu-id="2fb3a-129">脅威エクスプローラーも同様にこれを実行しますが、攻撃キャンペーンの強調表示など、特定の攻撃に関する追加の詳細を提供し、セキュリティ運用チームに脅威を修復する機能 (自動調査[](automated-investigation-response-office.md)と応答調査のトリガーを含む) を提供します。</span><span class="sxs-lookup"><span data-stu-id="2fb3a-129">Threat Explorer does this as well, but it provides additional details for a given attack, such as highlighting attack campaigns, and gives security operations teams the ability to remediate threats (including triggering an [Automated Investigation and Response investigation](automated-investigation-response-office.md)).</span></span>
- <span data-ttu-id="2fb3a-130">すべての *電子メール ビュー* は脅威エクスプローラーで使用できますが、リアルタイム検出レポートには含まれません。</span><span class="sxs-lookup"><span data-stu-id="2fb3a-130">An *All email* view is available in Threat Explorer, but not included in the Real-time detections report.</span></span>
- <span data-ttu-id="2fb3a-131">豊富なフィルター機能と修復アクションは、Threat Explorer に含まれています。</span><span class="sxs-lookup"><span data-stu-id="2fb3a-131">Rich filtering capabilities and remediation actions are included in Threat Explorer.</span></span> <span data-ttu-id="2fb3a-132">詳細については [、「Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 プラン」を参照してください](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。</span><span class="sxs-lookup"><span data-stu-id="2fb3a-132">For more information, see [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="2fb3a-133">必要なライセンスとアクセス許可</span><span class="sxs-lookup"><span data-stu-id="2fb3a-133">Required licenses and permissions</span></span>

<span data-ttu-id="2fb3a-134">エクスプローラーまたは [リアルタイム検出のいずれかを使用するには、Office 365](defender-for-office-365.md) 用の Microsoft Defender が必要です。</span><span class="sxs-lookup"><span data-stu-id="2fb3a-134">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use either of Explorer or Real-time detections:</span></span>

- <span data-ttu-id="2fb3a-135">ただし、エクスプローラーは、365 プラン 2 Office Defender にのみ含まれます。</span><span class="sxs-lookup"><span data-stu-id="2fb3a-135">But Explorer is only included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="2fb3a-136">リアルタイム検出レポートは、Defender for Office 365 プラン 1 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="2fb3a-136">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>

<span data-ttu-id="2fb3a-137">セキュリティ運用チームは、Office 365 の Defender によって保護される必要があるすべてのユーザーにライセンスを割り当て、エクスプローラーとリアルタイムの検出では、ライセンスを持つユーザーの検出データが表示される点に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fb3a-137">Security Operations teams need to assign licenses for all users who should be protected by Defender for Office 365 and be aware that Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="2fb3a-138">エクスプローラーまたはリアルタイムの検出 *を* 表示および使用するには、次の情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="2fb3a-138">To view and use Explorer *or* Real-time detections, you must have the following:</span></span>

- <span data-ttu-id="2fb3a-139">セキュリティ コンプライアンス センター&:</span><span class="sxs-lookup"><span data-stu-id="2fb3a-139">For the Security & Compliance Center:</span></span>

  - <span data-ttu-id="2fb3a-140">組織の管理</span><span class="sxs-lookup"><span data-stu-id="2fb3a-140">Organization Management</span></span>
  - <span data-ttu-id="2fb3a-141">セキュリティ管理者 (これは Azure Active Directory 管理センター ( ) で割り当 <https://aad.portal.azure.com> てることができます。</span><span class="sxs-lookup"><span data-stu-id="2fb3a-141">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="2fb3a-142">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="2fb3a-142">Security Reader</span></span>

- <span data-ttu-id="2fb3a-143">Exchange Online の場合:</span><span class="sxs-lookup"><span data-stu-id="2fb3a-143">For Exchange Online:</span></span>

  - <span data-ttu-id="2fb3a-144">組織の管理</span><span class="sxs-lookup"><span data-stu-id="2fb3a-144">Organization Management</span></span>
  - <span data-ttu-id="2fb3a-145">表示専用組織の管理</span><span class="sxs-lookup"><span data-stu-id="2fb3a-145">View-Only Organization Management</span></span>
  - <span data-ttu-id="2fb3a-146">"View-Only Recipients/表示専用受信者"</span><span class="sxs-lookup"><span data-stu-id="2fb3a-146">View-Only Recipients</span></span>
  - <span data-ttu-id="2fb3a-147">コンプライアンス管理</span><span class="sxs-lookup"><span data-stu-id="2fb3a-147">Compliance Management</span></span>

<span data-ttu-id="2fb3a-148">役割とアクセス許可の詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fb3a-148">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="2fb3a-149">セキュリティ/コンプライアンス センターのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="2fb3a-149">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="2fb3a-150">Exchange Online の機能アクセス許可</span><span class="sxs-lookup"><span data-stu-id="2fb3a-150">Feature permissions in Exchange Online</span></span>](/exchange/permissions-exo/feature-permissions)
- [<span data-ttu-id="2fb3a-151">Exchange Online の PowerShell</span><span class="sxs-lookup"><span data-stu-id="2fb3a-151">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a><span data-ttu-id="2fb3a-152">詳細情報</span><span class="sxs-lookup"><span data-stu-id="2fb3a-152">More information</span></span>
- [<span data-ttu-id="2fb3a-153">脅威エクスプローラーは、電子メール エンティティ ページで電子メールの詳細を収集します。</span><span class="sxs-lookup"><span data-stu-id="2fb3a-153">Threat Explorer collect email details on the email entity page</span></span>](mdo-email-entity-page.md)
- [<span data-ttu-id="2fb3a-154">配信された悪意のあるメールの検索と調査</span><span class="sxs-lookup"><span data-stu-id="2fb3a-154">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="2fb3a-155">SharePoint Online、OneDrive、Microsoft Teams で検出された悪意のあるファイルを表示する</span><span class="sxs-lookup"><span data-stu-id="2fb3a-155">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md)
- [<span data-ttu-id="2fb3a-156">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="2fb3a-156">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="2fb3a-157">Microsoft Threat Protection での自動調査および対応</span><span class="sxs-lookup"><span data-stu-id="2fb3a-157">Automated investigation and response in Microsoft Threat Protection</span></span>](automated-investigation-response-office.md)