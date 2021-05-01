---
title: 手順 3. 最初のインシデントのインシデント後レビューを実行する
description: Defender で最初のインシデントのレビューを実行Microsoft 365します。
keywords: インシデント、アラート、調査、相関、攻撃、マシン、デバイス、ユーザー、複数の ID、ID、メールボックス、メール、365、Microsoft、M365
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
ms.openlocfilehash: 1ceea1dbdb3f9d149f4e5a0bd892eda2bb9128aa
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114780"
---
# <a name="step-3-perform-a-post-incident-review-of-your-first-incident"></a><span data-ttu-id="a62e3-105">手順 3.</span><span class="sxs-lookup"><span data-stu-id="a62e3-105">Step 3.</span></span> <span data-ttu-id="a62e3-106">最初のインシデントのインシデント後レビューを実行する</span><span class="sxs-lookup"><span data-stu-id="a62e3-106">Perform a post-incident review of your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="a62e3-107">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="a62e3-107">**Applies to:**</span></span>
- <span data-ttu-id="a62e3-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a62e3-108">Microsoft 365 Defender</span></span>

<span data-ttu-id="a62e3-109">国立標準技術研究所 (NIST) は、攻撃から回復するためにすべての手順が実行された後、組織はインシデントを確認して、そこから学び、セキュリティの態勢やプロセスを学び、改善する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a62e3-109">National Institute of Standards and Technology (NIST) recommends that once all steps have been taken to recover from the attack, organizations must review the incident to learn from it and learn and improve security posture or processes.</span></span> <span data-ttu-id="a62e3-110">インシデント処理のさまざまな側面を評価することが、次のインシデントの準備において重要になります。</span><span class="sxs-lookup"><span data-stu-id="a62e3-110">Assessing the different aspects of incident-handling becomes important in preparing for the next incident.</span></span>

<span data-ttu-id="a62e3-111">Microsoft 365Defender は[、MITRE ATT](https://attack.mitre.org/)および CK Framework に合ったアラートを組織に提供することで、インシデント発生後の&支援できます。</span><span class="sxs-lookup"><span data-stu-id="a62e3-111">Microsoft 365 Defender can assist in performing post-incident activities by providing an organization with alerts that align with [MITRE ATT&CK Framework](https://attack.mitre.org/).</span></span> <span data-ttu-id="a62e3-112">すべての Microsoft Defender ソリューションは、CK の戦術または手法に基&攻撃をラベル付けします。</span><span class="sxs-lookup"><span data-stu-id="a62e3-112">All Microsoft Defender solutions label attacks in accordance with an ATT&CK tactic or technique.</span></span> 

<span data-ttu-id="a62e3-113">この業界フレームワークにアラートをマッピングすると、次の機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a62e3-113">By mapping alerts to this industry framework, you can:</span></span>

- <span data-ttu-id="a62e3-114">セキュリティ 範囲のギャップの分析を実行します。</span><span class="sxs-lookup"><span data-stu-id="a62e3-114">Conduct an analysis of gaps in security coverage.</span></span>
- <span data-ttu-id="a62e3-115">敵対者とキャンペーンの属性を決定します。</span><span class="sxs-lookup"><span data-stu-id="a62e3-115">Determine adversary and campaign attribution.</span></span>
- <span data-ttu-id="a62e3-116">傾向分析を実行します。</span><span class="sxs-lookup"><span data-stu-id="a62e3-116">Perform trend analysis.</span></span>
- <span data-ttu-id="a62e3-117">攻撃方法の認識におけるスキルのギャップを特定します。</span><span class="sxs-lookup"><span data-stu-id="a62e3-117">Identify skill gaps in attack method awareness.</span></span>
- <span data-ttu-id="a62e3-118">修復を高速化Power Automate Playbook を作成します。</span><span class="sxs-lookup"><span data-stu-id="a62e3-118">Create a Power Automate Playbook for faster remediation.</span></span> 

<span data-ttu-id="a62e3-119">インシデント後のレビュー アクティビティによって、セキュリティ構成とセキュリティ チームのプロセスを微調整し、組織の対応機能を強化することもできます。</span><span class="sxs-lookup"><span data-stu-id="a62e3-119">Post-incident review activity can also result in fine-tuning your security configuration and security team's processes, enhancing your organization’s response capabilities.</span></span>

## <a name="next-step"></a><span data-ttu-id="a62e3-120">次の手順</span><span class="sxs-lookup"><span data-stu-id="a62e3-120">Next step</span></span>

<span data-ttu-id="a62e3-121">次の追加の調査パスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a62e3-121">See these additional investigation paths:</span></span>

- [<span data-ttu-id="a62e3-122">フィッシング詐欺メール</span><span class="sxs-lookup"><span data-stu-id="a62e3-122">Phishing email</span></span>](first-incident-path-phishing.md)
- [<span data-ttu-id="a62e3-123">ID ベースの攻撃</span><span class="sxs-lookup"><span data-stu-id="a62e3-123">Identity-based attack</span></span>](first-incident-path-identity.md)


## <a name="see-also"></a><span data-ttu-id="a62e3-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="a62e3-124">See also</span></span>

- [<span data-ttu-id="a62e3-125">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="a62e3-125">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="a62e3-126">インシデントを分析する</span><span class="sxs-lookup"><span data-stu-id="a62e3-126">Analyze incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="a62e3-127">インシデントの管理</span><span class="sxs-lookup"><span data-stu-id="a62e3-127">Manage incidents</span></span>](manage-incidents.md)
