---
title: Microsoft 365 セキュリティセンターでの id の監視とレポート
description: 組織内のユーザーを監視し、疑わしいまたは危険な動作を追跡する方法について説明します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティセンター、モニター、レポート、id、ユーザー
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: 921ea91934900550c8b0c54f334ed7e34f70aa22
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2019
ms.locfileid: "39910172"
---
# <a name="identity-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="133fd-104">Microsoft 365 セキュリティセンターでの id の監視とレポート</span><span class="sxs-lookup"><span data-stu-id="133fd-104">Identity monitoring and reporting in the Microsoft 365 security center</span></span>

<span data-ttu-id="133fd-105">組織内の id を監視し、疑わしいまたは危険な動作を追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="133fd-105">You can monitor the identities in your organization and keep track of suspicious or risky behaviors.</span></span> <span data-ttu-id="133fd-106">**レポート**の [ **id** ] カテゴリでは、次のものを追跡できます。</span><span class="sxs-lookup"><span data-stu-id="133fd-106">In the **Identities** category of **Reports**, you can track:</span></span>

* <span data-ttu-id="133fd-107">異常が最も多く検出されたユーザー</span><span class="sxs-lookup"><span data-stu-id="133fd-107">Users with the most detected anomalies</span></span>
* <span data-ttu-id="133fd-108">条件付きアクセス ポリシーによって危険性が高いと報告されたユーザーの数</span><span class="sxs-lookup"><span data-stu-id="133fd-108">How many users are reported at risk by conditional access policies</span></span>
* <span data-ttu-id="133fd-109">組織内のグローバル管理者の数</span><span class="sxs-lookup"><span data-stu-id="133fd-109">The number of global admins in your org</span></span>

![レポートページの id カテゴリ](../images/identities.png)

<span data-ttu-id="133fd-111">特定の検出があるユーザーについては、Microsoft Defender セキュリティセンターで特定の警告を調べて調査することができます。</span><span class="sxs-lookup"><span data-stu-id="133fd-111">For users with specific detections, you can explore the specific alert and investigate in Microsoft Defender Security Center.</span></span> <span data-ttu-id="133fd-112">検出には、未知の場所からサインインしたユーザーなどの異常が含まれます。</span><span class="sxs-lookup"><span data-stu-id="133fd-112">Detections include anomalies such as users who sign in from unfamiliar locations.</span></span>

<span data-ttu-id="133fd-113">リスクイベントの完全なセットについては、「 [Azure Active Directory のリスクイベント](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-risk-events)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="133fd-113">For a complete set of risk events, see [Azure Active Directory risk events](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-risk-events).</span></span>