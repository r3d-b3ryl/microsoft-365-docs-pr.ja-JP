---
title: Microsoft Defender for Identity のパイロット、構成ベンチマーク、標準、ガイドラインの設定、および偵察、資格情報の侵害、横方向の移動、ドメインの支配、および外用アラートなど、さまざまな Identity の脅威の検出と修復に関するチュートリアルを実行し、ユーザー、コンピューター、エンティティ、および横方向の移動パスの調査を実行します。
description: パイロット Microsoft Defender for Identity, set benchmarks, take tutorials on reconnaissance, 侵害された資格情報, 横方向の動き, ドメインの支配, および外用アラート, とりわけ.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 14c5b9252e980d1f693139393d26b9405cb1b812
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458054"
---
# <a name="pilot-microsoft-defender-for-identity"></a><span data-ttu-id="8f9a4-103">Id の Microsoft Defender のパイロット</span><span class="sxs-lookup"><span data-stu-id="8f9a4-103">Pilot Microsoft Defender for Identity</span></span>


<span data-ttu-id="8f9a4-104">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="8f9a4-104">**Applies to:**</span></span>
- <span data-ttu-id="8f9a4-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8f9a4-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="8f9a4-106">この記事は、Microsoft Defender for Identity の評価環境をセットアップするプロセスの手順 [3/3](eval-defender-identity-overview.md) です。</span><span class="sxs-lookup"><span data-stu-id="8f9a4-106">This article is [Step 3 of 3](eval-defender-identity-overview.md) in the process of setting up the evaluation environment for Microsoft Defender for Identity.</span></span> <span data-ttu-id="8f9a4-107">このプロセスの詳細については、「概要」の記事を [参照してください](eval-defender-identity-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="8f9a4-107">For more information about this process, see the [overview article](eval-defender-identity-overview.md).</span></span>

<span data-ttu-id="8f9a4-108">次の手順を使用して、Microsoft Defender のパイロットを ID 用にセットアップして構成します。</span><span class="sxs-lookup"><span data-stu-id="8f9a4-108">Use the following steps to setup and configure the pilot for Microsoft Defender for identity.</span></span> <span data-ttu-id="8f9a4-109">推奨事項には、パイロット グループの設定は含めかねない点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="8f9a4-109">Note that the recommendations don't include setting up a pilot group.</span></span> <span data-ttu-id="8f9a4-110">ベスト プラクティスは、Active Directory ドメイン サービス (AD DS) および Active Directory フェデレーション サービス (AD FS) を実行しているすべてのサーバーにセンサーをインストールする方法です。</span><span class="sxs-lookup"><span data-stu-id="8f9a4-110">The best practice is to go ahead and install the sensor on all of your servers running Active Directory Domain Services (AD DS) and Active Directory Federated Services (AD FS).</span></span>

![Defender 評価環境に Microsoft Defender for Identity を追加する手順](../../media/defender/m365-defender-identity-pilot-steps.png)

<span data-ttu-id="8f9a4-112">次の表に、図の手順を示します。</span><span class="sxs-lookup"><span data-stu-id="8f9a4-112">The following table describes the steps in the illustration.</span></span>

- [<span data-ttu-id="8f9a4-113">手順 1: ID 環境のベンチマーク推奨事項を構成する</span><span class="sxs-lookup"><span data-stu-id="8f9a4-113">Step 1: Configure benchmark recommendations for your identity environment</span></span>](#step-1-configure-benchmark-recommendations-for-your-identity-environment)
- [<span data-ttu-id="8f9a4-114">手順 2: 機能を試す - さまざまな攻撃の種類を特定して修復するためのチュートリアルを参照してください </span><span class="sxs-lookup"><span data-stu-id="8f9a4-114">Step 2: Try out capabilities — Walk through tutorials for identifying and remediating different attack types </span></span>](#step-2-try-out-capabilities--walk-through-tutorials-for-identifying-and-remediating-different-attack-types)

## <a name="step-1-configure-benchmark-recommendations-for-your-identity-environment"></a><span data-ttu-id="8f9a4-115">手順 1.</span><span class="sxs-lookup"><span data-stu-id="8f9a4-115">Step 1.</span></span> <span data-ttu-id="8f9a4-116">ID 環境のベンチマーク推奨事項を構成する</span><span class="sxs-lookup"><span data-stu-id="8f9a4-116">Configure benchmark recommendations for your identity environment</span></span>

<span data-ttu-id="8f9a4-117">Microsoft は、Microsoft Cloud サービスを使用しているお客様にセキュリティ ベンチマークの推奨事項を提供します。</span><span class="sxs-lookup"><span data-stu-id="8f9a4-117">Microsoft provides security benchmark recommendations for customers using Microsoft Cloud services.</span></span> <span data-ttu-id="8f9a4-118">[Azure セキュリティ ベンチマーク](/security/benchmark/azure/overview)(ASB) は、Azure 上のワークロード、データ、およびサービスのセキュリティを向上させるのに役立つ、スクリプト的なベスト プラクティスと推奨事項を提供します。</span><span class="sxs-lookup"><span data-stu-id="8f9a4-118">The [Azure Security Benchmark](/security/benchmark/azure/overview) (ASB) provides prescriptive best practices and recommendations to help improve the security of workloads, data, and services on Azure.</span></span>

<span data-ttu-id="8f9a4-119">これらのベンチマーク推奨事項には、Microsoft Defender for [Identity の Azure セキュリティ ベースラインが含まれます](/security/benchmark/azure/baselines/defender-for-identity-security-baseline)。</span><span class="sxs-lookup"><span data-stu-id="8f9a4-119">These benchmark recommendations include [Azure security baseline for Microsoft Defender for Identity](/security/benchmark/azure/baselines/defender-for-identity-security-baseline).</span></span> <span data-ttu-id="8f9a4-120">これらの推奨事項を実装すると、計画と実装に時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8f9a4-120">Implementing these recommendations can take some time to plan and implement.</span></span> <span data-ttu-id="8f9a4-121">これらは ID 環境のセキュリティを大幅に向上しますが、Microsoft Defender for Identity の評価と実装を継続して行うのを防ぐ必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f9a4-121">While these will greatly increase the security of your identity environment, they shouldn't prevent you from continuing to evaluate and implement Microsoft Defender for Identity.</span></span> <span data-ttu-id="8f9a4-122">これらは、お客様の認識のためにここに提供されています。</span><span class="sxs-lookup"><span data-stu-id="8f9a4-122">These are provided here for your awareness.</span></span>

## <a name="step-2-try-out-capabilities--walk-through-tutorials-for-identifying-and-remediating-different-attack-types"></a><span data-ttu-id="8f9a4-123">手順 2.</span><span class="sxs-lookup"><span data-stu-id="8f9a4-123">Step 2.</span></span> <span data-ttu-id="8f9a4-124">機能を試す - さまざまな攻撃の種類を特定して修復するためのチュートリアルの詳細</span><span class="sxs-lookup"><span data-stu-id="8f9a4-124">Try out capabilities — Walk through tutorials for identifying and remediating different attack types</span></span>

<span data-ttu-id="8f9a4-125">Microsoft Defender for Identity のドキュメントには、さまざまな攻撃の種類を特定して修復するプロセスを説明する一連のチュートリアルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8f9a4-125">The Microsoft Defender for Identity documentation includes a series of tutorials that walk through the process of identifying and remediating various attack types.</span></span>

<span data-ttu-id="8f9a4-126">Defender for Identity のチュートリアルを試してみてください。</span><span class="sxs-lookup"><span data-stu-id="8f9a4-126">Try out Defender for Identity tutorials:</span></span>
- [<span data-ttu-id="8f9a4-127">偵察アラート</span><span class="sxs-lookup"><span data-stu-id="8f9a4-127">Reconnaissance alerts</span></span>](/defender-for-identity/reconnaissance-alerts)
- [<span data-ttu-id="8f9a4-128">資格情報の侵害に関する通知</span><span class="sxs-lookup"><span data-stu-id="8f9a4-128">Compromised credential alerts</span></span>](/defender-for-identity/compromised-credentials-alerts)
- [<span data-ttu-id="8f9a4-129">横方向の移動通知</span><span class="sxs-lookup"><span data-stu-id="8f9a4-129">Lateral movement alerts</span></span>](/defender-for-identity/lateral-movement-alerts)
- [<span data-ttu-id="8f9a4-130">ドメインの支配に関するアラート</span><span class="sxs-lookup"><span data-stu-id="8f9a4-130">Domain dominance alerts</span></span>](/defender-for-identity/domain-dominance-alerts)
- [<span data-ttu-id="8f9a4-131">Exfiltration アラート</span><span class="sxs-lookup"><span data-stu-id="8f9a4-131">Exfiltration alerts</span></span>](/defender-for-identity/exfiltration-alerts)
- [<span data-ttu-id="8f9a4-132">ユーザーを調査する</span><span class="sxs-lookup"><span data-stu-id="8f9a4-132">Investigate a user</span></span>](/defender-for-identity/investigate-a-user)
- [<span data-ttu-id="8f9a4-133">コンピューターを調査する</span><span class="sxs-lookup"><span data-stu-id="8f9a4-133">Investigate a computer</span></span>](/defender-for-identity/investigate-a-computer)
- [<span data-ttu-id="8f9a4-134">横方向の移動パスを調査する</span><span class="sxs-lookup"><span data-stu-id="8f9a4-134">Investigate lateral movement paths</span></span>](/defender-for-identity/investigate-lateral-movement-path)
- [<span data-ttu-id="8f9a4-135">エンティティの調査</span><span class="sxs-lookup"><span data-stu-id="8f9a4-135">Investigate entities</span></span>](/defender-for-identity/investigate-entity)

## <a name="next-steps"></a><span data-ttu-id="8f9a4-136">次の手順</span><span class="sxs-lookup"><span data-stu-id="8f9a4-136">Next steps</span></span>

[<span data-ttu-id="8f9a4-137">Microsoft Defender のセキュリティ評価Office 365</span><span class="sxs-lookup"><span data-stu-id="8f9a4-137">Evaluate Microsoft Defender for Office 365</span></span>](eval-defender-office-365-overview.md)

<span data-ttu-id="8f9a4-138">[Microsoft Defender for Office 365 の評価[] の概要に戻Office 365](eval-defender-office-365-overview.md)</span><span class="sxs-lookup"><span data-stu-id="8f9a4-138">Return to the overview for [Evaluate Microsoft Defender for Office 365](eval-defender-office-365-overview.md)</span></span>

<span data-ttu-id="8f9a4-139">[評価とパイロット][の概要に戻Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="8f9a4-139">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>