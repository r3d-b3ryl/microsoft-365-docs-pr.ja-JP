---
title: 最初のインシデントへの対応の概要
description: Microsoft 365 Defender での最初のインシデントへの対応の基本。
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
ms.openlocfilehash: 5ea847e822e094049dd8f0b941f22f3bb4f7eff4
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297178"
---
# <a name="introduction-to-responding-to-your-first-incident"></a><span data-ttu-id="34e6d-104">最初のインシデントへの対応の概要</span><span class="sxs-lookup"><span data-stu-id="34e6d-104">Introduction to responding to your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="34e6d-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="34e6d-105">**Applies to:**</span></span>
- <span data-ttu-id="34e6d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="34e6d-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="34e6d-107">組織のインシデント対応戦略は、ますます破壊的なセキュリティ インシデントやサイバー犯罪に対処する能力を決定します。</span><span class="sxs-lookup"><span data-stu-id="34e6d-107">An organization's incident response strategy determines its ability to deal with increasingly disruptive security incidents and cybercrime.</span></span> <span data-ttu-id="34e6d-108">予防措置を講じすることは重要ですが、検出されたインシデントを迅速に取り込み、根絶し、復旧する能力は、損害とビジネス上の損失を最小限に抑える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="34e6d-108">While taking preventative measures is important, the ability to act quickly to contain, eradicate, and recover from detected incidents can minimize damage and business losses.</span></span>

<span data-ttu-id="34e6d-109">このインシデント対応のチュートリアルでは、セキュリティ運用チームの一員として、Microsoft 365 Defender 内の主要なインシデント対応手順のほとんどを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="34e6d-109">This incident response walkthrough shows how you, as part of a security operations team, can perform most of the key incident response steps within Microsoft 365 Defender.</span></span> <span data-ttu-id="34e6d-110">それらのステップは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="34e6d-110">Here are the steps:</span></span>

- <span data-ttu-id="34e6d-111">セキュリティ態勢の準備</span><span class="sxs-lookup"><span data-stu-id="34e6d-111">Preparation of your security posture</span></span>
- <span data-ttu-id="34e6d-112">インシデントごとに次の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="34e6d-112">For each incident:</span></span>
  - <span data-ttu-id="34e6d-113">手順 1: トリアージと分析</span><span class="sxs-lookup"><span data-stu-id="34e6d-113">Step 1: Triage and analysis</span></span>
  - <span data-ttu-id="34e6d-114">手順 2: 修復 (格納、根絶、および回復)</span><span class="sxs-lookup"><span data-stu-id="34e6d-114">Step 2: Remediation (containment, eradication, and recovery)</span></span>
  - <span data-ttu-id="34e6d-115">手順 3: インシデント後のレビュー</span><span class="sxs-lookup"><span data-stu-id="34e6d-115">Step 3: Post-incident review</span></span>

<span data-ttu-id="34e6d-116">セキュリティ インシデントは、国立標準技術研究所 (NIST) によって「情報システムの機密性、整合性、または可用性を実際または潜在的に危険にさらす発生」と定義されます。またはシステムが処理、保存、または送信する情報。または、セキュリティ ポリシー、セキュリティ手順、または許容される使用ポリシーに対する違反または差し迫った脅威を構成します。</span><span class="sxs-lookup"><span data-stu-id="34e6d-116">A security incident is defined by National Institute of Standards and Technology (NIST) as "an occurrence that actually or potentially jeopardizes the confidentiality, integrity, or availability of an information system; or the information the system processes, stores, or transmits; or that constitutes a violation or imminent threat of violation of security policies, security procedures, or acceptable use policies."</span></span>

<span data-ttu-id="34e6d-117">Microsoft 365 Defender のインシデントは、分析とインシデント対応の論理的な開始点です。</span><span class="sxs-lookup"><span data-stu-id="34e6d-117">Incidents in Microsoft 365 Defender are the logical starting points for analysis and incident response.</span></span> <span data-ttu-id="34e6d-118">インシデントの分析と修復は、通常、ほとんどのセキュリティ運用チームのタスクを構成します。</span><span class="sxs-lookup"><span data-stu-id="34e6d-118">Analyzing and remediating incidents typically makes up most of a security operations team's tasks.</span></span>

## <a name="next-step"></a><span data-ttu-id="34e6d-119">次の手順</span><span class="sxs-lookup"><span data-stu-id="34e6d-119">Next step</span></span>

<span data-ttu-id="34e6d-120">[![組織と Microsoft 365 テナントを準備する](../../media/first-incident-overview/first-incident-path.png)](first-incident-prepare.md)</span><span class="sxs-lookup"><span data-stu-id="34e6d-120">[![Prepare your organization and Microsoft 365 tenant](../../media/first-incident-overview/first-incident-path.png)](first-incident-prepare.md)</span></span>

<span data-ttu-id="34e6d-121">組織と Microsoft 365 テナントがインシデント処理の [準備ができているか確認します](first-incident-prepare.md)。</span><span class="sxs-lookup"><span data-stu-id="34e6d-121">Make sure your organization and Microsoft 365 tenant is [prepared for incident handling](first-incident-prepare.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="34e6d-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="34e6d-122">See also</span></span>

<span data-ttu-id="34e6d-123">Microsoft 365 Defender のインシデント対応ガイダンス:</span><span class="sxs-lookup"><span data-stu-id="34e6d-123">Incident response guidance for Microsoft 365 Defender:</span></span>

- [<span data-ttu-id="34e6d-124">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="34e6d-124">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="34e6d-125">インシデントの調査</span><span class="sxs-lookup"><span data-stu-id="34e6d-125">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="34e6d-126">インシデントの管理</span><span class="sxs-lookup"><span data-stu-id="34e6d-126">Manage incidents</span></span>](manage-incidents.md)

<span data-ttu-id="34e6d-127">最初のインシデント対応のその他の例:</span><span class="sxs-lookup"><span data-stu-id="34e6d-127">Additional examples of first incident responses:</span></span>

- [<span data-ttu-id="34e6d-128">フィッシング詐欺メール</span><span class="sxs-lookup"><span data-stu-id="34e6d-128">Phishing email</span></span>](first-incident-path-phishing.md)
- [<span data-ttu-id="34e6d-129">IDENTITY-base 攻撃</span><span class="sxs-lookup"><span data-stu-id="34e6d-129">Identity-base attack</span></span>](first-incident-path-identity.md)

[<span data-ttu-id="34e6d-130">インシデント対応の詳細なプレイブック</span><span class="sxs-lookup"><span data-stu-id="34e6d-130">Detailed incident response playbooks</span></span>](https://docs.microsoft.com/security/compass/incident-response-playbooks)


