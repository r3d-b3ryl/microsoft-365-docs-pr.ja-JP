---
title: 最初のインシデントへの対応の概要
description: Defender の最初のインシデントに対応するMicrosoft 365。
keywords: インシデント、アラート、調査、相関関係、攻撃、デバイス、ユーザー、ID、ID、メールボックス、電子メール、365、microsoft、m365、インシデント対応、サイバー攻撃
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: f66c9821e5db00cc3da5718f52b8aaaeff5a431e
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114756"
---
# <a name="introduction-to-responding-to-your-first-incident"></a><span data-ttu-id="4a6c3-104">最初のインシデントへの対応の概要</span><span class="sxs-lookup"><span data-stu-id="4a6c3-104">Introduction to responding to your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="4a6c3-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="4a6c3-105">**Applies to:**</span></span>
- <span data-ttu-id="4a6c3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4a6c3-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="4a6c3-107">組織のインシデント対応戦略は、ますます破壊的なセキュリティ インシデントやサイバー犯罪に対処する能力を決定します。</span><span class="sxs-lookup"><span data-stu-id="4a6c3-107">An organization's incident response strategy determines its ability to deal with increasingly disruptive security incidents and cybercrime.</span></span> <span data-ttu-id="4a6c3-108">予防措置を講じすることは重要ですが、検出されたインシデントを迅速に取り込み、根絶し、復旧する能力は、損害とビジネス上の損失を最小限に抑える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4a6c3-108">While taking preventative measures is important, the ability to act quickly to contain, eradicate, and recover from detected incidents can minimize damage and business losses.</span></span>

<span data-ttu-id="4a6c3-109">このインシデント対応のチュートリアルでは、セキュリティ運用チームの一員として、Defender 内の主要なインシデント対応手順のほとんどを実行Microsoft 365します。</span><span class="sxs-lookup"><span data-stu-id="4a6c3-109">This incident response walkthrough shows how you, as part of a security operations team, can perform most of the key incident response steps within Microsoft 365 Defender.</span></span> <span data-ttu-id="4a6c3-110">それらのステップは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4a6c3-110">Here are the steps:</span></span>

- <span data-ttu-id="4a6c3-111">セキュリティ態勢の準備</span><span class="sxs-lookup"><span data-stu-id="4a6c3-111">Preparation of your security posture</span></span>
- <span data-ttu-id="4a6c3-112">インシデントごとに次の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="4a6c3-112">For each incident:</span></span>
  - <span data-ttu-id="4a6c3-113">手順 1: トリアージと分析</span><span class="sxs-lookup"><span data-stu-id="4a6c3-113">Step 1: Triage and analysis</span></span>
  - <span data-ttu-id="4a6c3-114">手順 2: 修復 (格納、根絶、および回復)</span><span class="sxs-lookup"><span data-stu-id="4a6c3-114">Step 2: Remediation (containment, eradication, and recovery)</span></span>
  - <span data-ttu-id="4a6c3-115">手順 3: インシデント後のレビュー</span><span class="sxs-lookup"><span data-stu-id="4a6c3-115">Step 3: Post-incident review</span></span>

<span data-ttu-id="4a6c3-116">セキュリティ インシデントは、国立標準技術研究所 (NIST) によって「情報システムの機密性、整合性、または可用性を実際または潜在的に危険にさらす発生」と定義されます。またはシステムが処理、保存、または送信する情報。または、セキュリティ ポリシー、セキュリティ手順、または許容される使用ポリシーに対する違反または差し迫った脅威を構成します。</span><span class="sxs-lookup"><span data-stu-id="4a6c3-116">A security incident is defined by National Institute of Standards and Technology (NIST) as "an occurrence that actually or potentially jeopardizes the confidentiality, integrity, or availability of an information system; or the information the system processes, stores, or transmits; or that constitutes a violation or imminent threat of violation of security policies, security procedures, or acceptable use policies."</span></span>

<span data-ttu-id="4a6c3-117">Defender のインシデントMicrosoft 365分析とインシデント対応の論理的な開始点です。</span><span class="sxs-lookup"><span data-stu-id="4a6c3-117">Incidents in Microsoft 365 Defender are the logical starting points for analysis and incident response.</span></span> <span data-ttu-id="4a6c3-118">インシデントの分析と修復は、通常、ほとんどのセキュリティ運用チームのタスクを構成します。</span><span class="sxs-lookup"><span data-stu-id="4a6c3-118">Analyzing and remediating incidents typically makes up most of a security operations team's tasks.</span></span>

## <a name="next-step"></a><span data-ttu-id="4a6c3-119">次の手順</span><span class="sxs-lookup"><span data-stu-id="4a6c3-119">Next step</span></span>

<span data-ttu-id="4a6c3-120">[![組織とテナントをMicrosoft 365する](../../media/first-incident-overview/first-incident-path.png)](first-incident-prepare.md)</span><span class="sxs-lookup"><span data-stu-id="4a6c3-120">[![Prepare your organization and Microsoft 365 tenant](../../media/first-incident-overview/first-incident-path.png)](first-incident-prepare.md)</span></span>

<span data-ttu-id="4a6c3-121">組織と組織のテナントMicrosoft 365インシデント[処理の準備ができているか確認します](first-incident-prepare.md)。</span><span class="sxs-lookup"><span data-stu-id="4a6c3-121">Make sure your organization and Microsoft 365 tenant is [prepared for incident handling](first-incident-prepare.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4a6c3-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="4a6c3-122">See also</span></span>

- [<span data-ttu-id="4a6c3-123">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="4a6c3-123">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="4a6c3-124">インシデントを分析する</span><span class="sxs-lookup"><span data-stu-id="4a6c3-124">Analyze incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="4a6c3-125">インシデントの管理</span><span class="sxs-lookup"><span data-stu-id="4a6c3-125">Manage incidents</span></span>](manage-incidents.md)
