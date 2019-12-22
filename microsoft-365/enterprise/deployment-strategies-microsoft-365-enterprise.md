---
title: Microsoft 365 Enterprise の基盤インフラストラクチャ展開戦略
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/24/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 Enterprise の基盤インフラストラクチャの各フェーズを展開するいくつかの方法について説明します。
ms.openlocfilehash: 354ce1a30b91f602049143dc0e93fe01629e6b04
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801892"
---
# <a name="microsoft-365-for-enterprise-foundation-infrastructure-deployment-strategies"></a><span data-ttu-id="d6266-103">Microsoft 365 Enterprise の基盤インフラストラクチャ展開戦略</span><span class="sxs-lookup"><span data-stu-id="d6266-103">Microsoft 365 Enterprise foundation infrastructure deployment strategies</span></span>

<span data-ttu-id="d6266-p101">Microsoft 365 Enterprise の[基盤インフラストラクチャ](deploy-foundation-infrastructure.md)の各フェーズを展開し、その機能、ソフトウェア、サービスをユーザーにロールアウトする方法は数多くあります。この仕事のプロジェクト管理に取り掛かることは、組織および既存のインフラストラクチャの規模によっては大がかりで複雑な作業になる可能性があるので、以下のような展開戦略を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="d6266-p101">There are many ways you can deploy the phases of the [foundation infrastructure](deploy-foundation-infrastructure.md) of Microsoft 365 Enterprise and roll out its capabilities, software, and services to your users. To get you started on the project management of this undertaking, which can be large and complex depending on the size of your organization and its existing infrastructure, consider the following deployment strategies:</span></span>

- <span data-ttu-id="d6266-106">順次展開</span><span class="sxs-lookup"><span data-stu-id="d6266-106">Serial deployment</span></span>
- <span data-ttu-id="d6266-107">ユーザー ロールアウトが重複しない並列展開</span><span class="sxs-lookup"><span data-stu-id="d6266-107">Parallel deployment with non-overlapping user rollout</span></span>
- <span data-ttu-id="d6266-108">ユーザー ロールアウトが重複する並列展開</span><span class="sxs-lookup"><span data-stu-id="d6266-108">Parallel deployment with overlapping user rollout</span></span>
- <span data-ttu-id="d6266-109">事前のインフラストラクチャとエンド ツー エンド構成のロールアウト</span><span class="sxs-lookup"><span data-stu-id="d6266-109">Up-front infrastructure and rollout of the end-to-end configuration</span></span>

<span data-ttu-id="d6266-110">プロジェクト全体を管理し、より迅速に Microsoft 365 Enterprise のビジネス上のメリットを実現する方法について着想を得るために、これらの戦略を使用します。</span><span class="sxs-lookup"><span data-stu-id="d6266-110">Use these strategies for ideas on how to manage the overall project and more quickly realize the business benefits of Microsoft 365 Enterprise.</span></span>

>[!Note]
><span data-ttu-id="d6266-p102">この記事には、展開戦略を一貫した方法で説明するための想定と簡略化が含まれています。これらの展開戦略は一般論を述べたものであり、何らかの特定の時間枠を示唆したり、すべての組織と状況に適用したりすることを意図してはいません。</span><span class="sxs-lookup"><span data-stu-id="d6266-p102">This article contains assumptions and simplifications for a consistent way to describe the deployment strategies. These deployment strategies are generalized and are not meant to imply any specific timeframes, nor are they meant to apply to all organizations and situations.</span></span>
>

## <a name="elements-of-it-project-management-for-typical-enterprise-organizations"></a><span data-ttu-id="d6266-113">一般的な企業組織向けの IT プロジェクト管理の要素</span><span class="sxs-lookup"><span data-stu-id="d6266-113">Elements of IT project management for typical enterprise organizations</span></span>

<span data-ttu-id="d6266-p103">IT インフラストラクチャには、バックエンド サービスと、新しい機能や改善された機能またはインストールされたソフトウェアのエンド ユーザーへのロールアウトの両方が含まれています。通常、IT 部門は、系統的な方法で IT インフラストラクチャの各要素を展開します。IT インフラストラクチャの各要素の展開を成功させる方法の 1 つは、次のように構成されます。</span><span class="sxs-lookup"><span data-stu-id="d6266-p103">IT infrastructure includes both backend services and the rollout of new or improved capabilities or installed software to end users. IT departments typically deploy elements of an IT infrastructure in a methodical way. One approach to the successful deployment of an element of IT infrastructure consists of:</span></span>

- <span data-ttu-id="d6266-117">パイロット ロールアウト</span><span class="sxs-lookup"><span data-stu-id="d6266-117">A pilot rollout</span></span> 

  <span data-ttu-id="d6266-118">これには、初期のインフラストラクチャ構成と、一連のパイロット ユーザーへのロールアウト、インフラストラクチャ構成のテストとそれ以降の変更が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d6266-118">This includes initial infrastructure configuration and rollout to a pilot set of users, testing, and subsequent modifications to the infrastructure configuration.</span></span>

- <span data-ttu-id="d6266-119">ユーザー ロールアウト</span><span class="sxs-lookup"><span data-stu-id="d6266-119">A user rollout</span></span>

  <span data-ttu-id="d6266-120">これには、地域、部門、グループ、または他の種類の、構成やソフトウェアの体系的な伝達経路に基づく、組織の残りの部分への展開が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d6266-120">This includes the rollout to the rest of your organization based on regions, departments, groups, or other types of systematic propagation of configuration or software.</span></span>

<span data-ttu-id="d6266-121">パイロット ロールアウト内のユーザーのセットは、ユーザー ロールアウト内のユーザーのセットとは異なります。</span><span class="sxs-lookup"><span data-stu-id="d6266-121">The set of users in the pilot rollout are not the same as those in the user rollout.</span></span>

<span data-ttu-id="d6266-122">この資料では、次の図を使用して、これらの定義を示します。</span><span class="sxs-lookup"><span data-stu-id="d6266-122">This article uses the following graphics to depict these definitions:</span></span> 

![パイロットおよびユーザー ロールアウトの定義を示すグラフィックス](./media/deployment-strategies-microsoft-365-enterprise/definitions.png) 

<span data-ttu-id="d6266-124">ユーザー ロールアウトの図の網かけは、グループ、部門、地域などの構造化または系統的アプローチを使用する、組織全体におけるパーセンテージ (0% から 100%) を示します。</span><span class="sxs-lookup"><span data-stu-id="d6266-124">The shading for the user rollout graphic indicates the percentage across your organization from 0% to 100% using a structured or methodical approach such as groups, departments, or regions.</span></span>

## <a name="deployment-strategies"></a><span data-ttu-id="d6266-125">展開戦略</span><span class="sxs-lookup"><span data-stu-id="d6266-125">Deployment strategies</span></span>

<span data-ttu-id="d6266-126">以下の展開戦略を考慮します。</span><span class="sxs-lookup"><span data-stu-id="d6266-126">Consider the following deployment strategies:</span></span>

- <span data-ttu-id="d6266-127">順次展開</span><span class="sxs-lookup"><span data-stu-id="d6266-127">Serial deployment</span></span>
- <span data-ttu-id="d6266-128">ユーザー ロールアウトが重複しない並列展開</span><span class="sxs-lookup"><span data-stu-id="d6266-128">Parallel deployment with non-overlapping user rollout</span></span>
- <span data-ttu-id="d6266-129">ユーザー ロールアウトが重複する並列展開</span><span class="sxs-lookup"><span data-stu-id="d6266-129">Parallel deployment with overlapping user rollout</span></span>
- <span data-ttu-id="d6266-130">事前のインフラストラクチャとエンド ツー エンド構成のロールアウト</span><span class="sxs-lookup"><span data-stu-id="d6266-130">Up-front infrastructure and rollout of the end-to-end configuration</span></span>

### <a name="serial-deployment"></a><span data-ttu-id="d6266-131">順次展開</span><span class="sxs-lookup"><span data-stu-id="d6266-131">Serial deployment</span></span>

<span data-ttu-id="d6266-p104">順次展開では、次のフェーズに移る前にすべてのユーザーへの展開が 100% 完了に達するように、1 フェーズを完全にロールアウトします。この方法で展開を行う理由としては、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="d6266-p104">With a serial deployment, you completely roll out a phase, allowing the phase to reach 100% completion of deployment to all of your users, before moving on to the next one. Here are some of the reasons why you might deploy this way:</span></span>

- <span data-ttu-id="d6266-134">リスクの軽減</span><span class="sxs-lookup"><span data-stu-id="d6266-134">Risk mitigation</span></span>
- <span data-ttu-id="d6266-135">リソースの制約</span><span class="sxs-lookup"><span data-stu-id="d6266-135">Resourcing constraints</span></span>
- <span data-ttu-id="d6266-136">IT 部門の予算サイクル</span><span class="sxs-lookup"><span data-stu-id="d6266-136">IT department funding cycles</span></span>
- <span data-ttu-id="d6266-137">IT テクノロジの依存関係</span><span class="sxs-lookup"><span data-stu-id="d6266-137">IT technology dependencies</span></span>
- <span data-ttu-id="d6266-138">ビジネスの変更管理とエンド ユーザーからの抵抗</span><span class="sxs-lookup"><span data-stu-id="d6266-138">Business change management and end-user resistance</span></span>

<span data-ttu-id="d6266-139">このガント チャートは、Microsoft 365 Enterprise の基盤インフラストラクチャのフェーズ 2 〜 6 の簡略化された順次展開を示しています。</span><span class="sxs-lookup"><span data-stu-id="d6266-139">This Gantt chart shows a simplified serial deployment of phases 2-6 of the foundation infrastructure for Microsoft 365 Enterprise.</span></span>

![基盤インフラストラクチャのフェーズ 2 から 6 のシリアル展開](./media/deployment-strategies-microsoft-365-enterprise/serial.png) 
 
<span data-ttu-id="d6266-141">説明と例を簡単にするために、各フェーズと、各フェーズ内の展開セグメントは、同じ時間がかかると想定しています。</span><span class="sxs-lookup"><span data-stu-id="d6266-141">To simplify the discussion and example, each phase and deployment segment within each phase are assumed to take the same amount of time.</span></span>

>[!Note]
><span data-ttu-id="d6266-p105">フェーズ 1: Microsoft 365 Enterprise 基盤インフラストラクチャのネットワーキングは、IT 部門専用のフェーズです。ユーザーは Microsoft のクラウド リソースへと最適化された接続のメリットを享受しますが、その達成が強制されることはありません。</span><span class="sxs-lookup"><span data-stu-id="d6266-p105">Phase 1: Networking of the Microsoft 365 Enterprise Foundation Infrastructure is an IT department-only phase. Users reap the benefits of optimized connectivity to Microsoft’s cloud resources but are not imposed upon to achieve it.</span></span>
>

<span data-ttu-id="d6266-144">例として、簡素化されたパイロット ユーザー エクスペリエンスを次に示します。</span><span class="sxs-lookup"><span data-stu-id="d6266-144">Here’s a simplified pilot user experience as an example:</span></span>

- <span data-ttu-id="d6266-p106">12 月に、MFA 用にスマート フォンを使用する必要があります。(ユーザー情報)</span><span class="sxs-lookup"><span data-stu-id="d6266-p106">In December, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="d6266-p107">3 月に、Windows 8.1 デスクトップに Windows 10 Enterprise がインストールされます。(Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="d6266-p107">In March, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="d6266-p108">6 月に、Office 2013 に代わって Office 365 ProPlus がインストールされます。(Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="d6266-p108">In June, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="d6266-151">9 月に、デバイス登録を受け、アプリ ポリシーとデバイス ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="d6266-151">In September, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="d6266-152">(モバイル デバイス管理)</span><span class="sxs-lookup"><span data-stu-id="d6266-152">(Mobile device management)</span></span>
- <span data-ttu-id="d6266-p110">12 月には Azure Information Protection クライアントがインストールされて、ドキュメントにラベルを適用する方法のトレーニングを受けます。(情報の保護)</span><span class="sxs-lookup"><span data-stu-id="d6266-p110">In December, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="d6266-155">結果は、連続するパイロット ロールアウトの間で 90 日間の間隔になります。</span><span class="sxs-lookup"><span data-stu-id="d6266-155">The result is a 90-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="d6266-156">例として、簡素化されたエンドユーザー エクスペリエンスを次に示します。</span><span class="sxs-lookup"><span data-stu-id="d6266-156">Here’s a simplified end-user experience as an example:</span></span>

- <span data-ttu-id="d6266-p111">1 月に、MFA 用にスマート フォンを使用する必要があります。(ユーザー情報)</span><span class="sxs-lookup"><span data-stu-id="d6266-p111">In January, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="d6266-p112">4 月に、Windows 8.1 デスクトップに Windows 10 Enterprise がインストールされます。(Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="d6266-p112">In April, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="d6266-p113">7 月に、Office 2013 に代わって Office 365 ProPlus がインストールされます。(Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="d6266-p113">In July, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="d6266-163">10 月に、デバイス登録を受け、アプリ ポリシーとデバイス ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="d6266-163">In October, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="d6266-164">(モバイル デバイス管理)</span><span class="sxs-lookup"><span data-stu-id="d6266-164">(Mobile device management)</span></span>
- <span data-ttu-id="d6266-p115">翌年の 1 月には Azure Information Protection クライアントがインストールされて、ドキュメントにラベルを適用する方法のトレーニングを受けます。(情報の保護)</span><span class="sxs-lookup"><span data-stu-id="d6266-p115">In January of the following year, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="d6266-167">結果は、連続するユーザー ロールアウトの間で 90 日間の間隔になります。</span><span class="sxs-lookup"><span data-stu-id="d6266-167">The result is a 90-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="d6266-168">この展開戦略の欠点は、Microsoft 365 Enterprise 基盤インフラストラクチャを完全に展開するのに時間がかかることです。</span><span class="sxs-lookup"><span data-stu-id="d6266-168">The disadvantage to this deployment strategy is that it can take a long time to fully deploy the Microsoft 365 Enterprise foundation infrastructure.</span></span>

### <a name="parallel-deployment-with-non-overlapping-user-rollout-parallel-1"></a><span data-ttu-id="d6266-169">ユーザー ロールアウトが重複しない並列展開 (並列 1)</span><span class="sxs-lookup"><span data-stu-id="d6266-169">Parallel deployment with non-overlapping user rollout (Parallel 1)</span></span>

<span data-ttu-id="d6266-p116">この展開戦略では、ユーザー ロールアウトの現在のフェーズの最後の部分の間に、次のフェーズのパイロット ロールアウトを開始します。前のフェーズのユーザー ロールアウトと重なる形でパイロット ロールアウトが発生する場合の、フェーズ 2 から 6 の展開を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="d6266-p116">For this deployment strategy, you start the pilot rollout of the next phase during the last part of the user rollout of the current phase. Here is the deployment of phases 2-6 when the pilot rollout occurs as the user rollout of the previous phase is wrapping up.</span></span>

![ユーザー ロールアウトが重複しないフェーズ 2 から 6 の並列展開](./media/deployment-strategies-microsoft-365-enterprise/parallel1.png) 
 
<span data-ttu-id="d6266-p117">最終結果としては、次のフェーズが始まる前に、組織全体で現在のフェーズのユーザー ロールアウトが完了します。パイロット ロールアウトに含まれないユーザーは、同時に複数のフェーズのロールアウトで処理されることはありませんが、パイロット ロールアウトはユーザー ロールアウトと並行して処理されます。</span><span class="sxs-lookup"><span data-stu-id="d6266-p117">The end result is that user rollout for the current phase completes across your organization before the next one starts. Users that are not in pilot rollouts are not dealing with the rollouts of multiple phases at the same time, but pilot rollouts are done in parallel with user rollouts.</span></span>

<span data-ttu-id="d6266-175">例として、簡素化されたパイロット ユーザー エクスペリエンスを次に示します。</span><span class="sxs-lookup"><span data-stu-id="d6266-175">Here’s a simplified pilot user experience as an example:</span></span>

- <span data-ttu-id="d6266-p118">12 月に、MFA 用にスマート フォンを使用する必要があります。(ユーザー情報)</span><span class="sxs-lookup"><span data-stu-id="d6266-p118">In December, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="d6266-p119">2 月に、Windows 8.1 デスクトップに Windows 10 Enterprise がインストールされます。(Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="d6266-p119">In February, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="d6266-p120">4 月に、Office 2013 に代わって Office 365 ProPlus がインストールされます。(Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="d6266-p120">In April, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="d6266-182">6 月に、デバイス登録を受け、アプリ ポリシーとデバイス ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="d6266-182">In June, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="d6266-183">(モバイル デバイス管理)</span><span class="sxs-lookup"><span data-stu-id="d6266-183">(Mobile device management)</span></span>
- <span data-ttu-id="d6266-p122">8 月には Azure Information Protection クライアントがインストールされて、ドキュメントにラベルを適用する方法のトレーニングを受けます。(情報の保護)</span><span class="sxs-lookup"><span data-stu-id="d6266-p122">In August, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="d6266-186">結果は、連続するパイロット ロールアウトの間で 60 日間の間隔になります。</span><span class="sxs-lookup"><span data-stu-id="d6266-186">The result is a 60-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="d6266-187">例として、簡素化されたエンドユーザー エクスペリエンスを次に示します。</span><span class="sxs-lookup"><span data-stu-id="d6266-187">Here’s a simplified end-user experience as an example:</span></span>

- <span data-ttu-id="d6266-p123">1 月に、MFA 用にスマート フォンを使用する必要があります。(ユーザー情報)</span><span class="sxs-lookup"><span data-stu-id="d6266-p123">In January, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="d6266-p124">3 月に、Windows 8.1 デスクトップに Windows 10 Enterprise がインストールされます。(Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="d6266-p124">In March, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="d6266-p125">5 月に、Office 2013 に代わって Office 365 ProPlus がインストールされます。(Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="d6266-p125">In May, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="d6266-194">7 月に、デバイス登録を受け、アプリ ポリシーとデバイス ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="d6266-194">In July, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="d6266-195">(モバイル デバイス管理)</span><span class="sxs-lookup"><span data-stu-id="d6266-195">(Mobile device management)</span></span>
- <span data-ttu-id="d6266-p127">9 月には Azure Information Protection クライアントがインストールされて、ドキュメントにラベルを適用する方法のトレーニングを受けます。(情報の保護)</span><span class="sxs-lookup"><span data-stu-id="d6266-p127">In September, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="d6266-198">結果は、連続するユーザー ロールアウトの間で 60 日間の間隔になります。</span><span class="sxs-lookup"><span data-stu-id="d6266-198">The result is a 60-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="d6266-199">この展開戦略の利点は、IT 部門およびユーザーが同時に複数のロールアウトに対処する必要がなく、Microsoft 365 Enterprise 基盤インフラストラクチャを完全に展開するのにかかる時間が短いことです。</span><span class="sxs-lookup"><span data-stu-id="d6266-199">The advantage to this deployment strategy is that it can take less time to fully deploy the Microsoft 365 Enterprise foundation infrastructure, without having your IT department and users deal with multiple rollouts the same time.</span></span>

### <a name="parallel-deployment-with-overlapping-user-rollout-parallel-2"></a><span data-ttu-id="d6266-200">ユーザー ロールアウトが重複する並列展開 (並列 2)</span><span class="sxs-lookup"><span data-stu-id="d6266-200">Parallel deployment with overlapping user rollout (Parallel 2)</span></span>

<span data-ttu-id="d6266-201">この展開戦略では、以下の要領で開始します。</span><span class="sxs-lookup"><span data-stu-id="d6266-201">For this deployment strategy, you start the:</span></span>

- <span data-ttu-id="d6266-202">ユーザー ロールアウトの現在のフェーズの最後の部分の間に、次のフェーズのパイロット ロールアウトを開始します。</span><span class="sxs-lookup"><span data-stu-id="d6266-202">Pilot rollout of the next phase during the last part of the user rollout of the current phase.</span></span>
- <span data-ttu-id="d6266-203">現在のフェーズのユーザー ロールアウト中に、次のフェーズのユーザー ロールアウトを開始します。ただし、どのユーザーも同時に複数のフェーズのロールアウトを処理することがないようにします。</span><span class="sxs-lookup"><span data-stu-id="d6266-203">User rollout of the next phase during the user rollout of the current phase in such a way that no user is dealing with the rollouts of multiple phases at the same time.</span></span> <span data-ttu-id="d6266-204">これは、基盤インフラストラクチャの各フェーズのロールアウトを同じ方法で (地域、部門、その他のグループ化を使用して) 行うことが前提となります。</span><span class="sxs-lookup"><span data-stu-id="d6266-204">This assumes that you are rolling out each phase of the foundation infrastructure in the same way, using regions, departments, or other groupings.</span></span>

<span data-ttu-id="d6266-205">各種の展開戦略の簡単な比較を示します。</span><span class="sxs-lookup"><span data-stu-id="d6266-205">Here is a simplified comparison between the different deployment strategies.</span></span>

![ユーザー ロールアウトが重複するフェーズ 2 から 6 の並列展開](./media/deployment-strategies-microsoft-365-enterprise/parallel2.png) 

<span data-ttu-id="d6266-207">最終結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d6266-207">The end result is that:</span></span>

- <span data-ttu-id="d6266-208">パイロット ロールアウトは、1 つのフェーズから次のフェーズへ休みなく移行します。</span><span class="sxs-lookup"><span data-stu-id="d6266-208">Pilot rollouts go from one phase to the next without a pause.</span></span>
- <span data-ttu-id="d6266-209">あるフェーズのユーザー ロールアウトは、前のフェーズのユーザー ロールアウトの完了前に開始しますが、個々のユーザーが同時に複数のフェーズをロールアウトすることはありません。</span><span class="sxs-lookup"><span data-stu-id="d6266-209">The user rollout for a phase begins before the completion of the user rollout of the previous phase, but no individual user is rolling out more than one phase at a time.</span></span>

<span data-ttu-id="d6266-210">例として、簡素化されたパイロット ユーザー エクスペリエンスを次に示します。</span><span class="sxs-lookup"><span data-stu-id="d6266-210">Here’s a simplified pilot user experience as an example:</span></span>

- <span data-ttu-id="d6266-p129">12 月に、MFA 用にスマート フォンを使用する必要があります。(ユーザー情報)</span><span class="sxs-lookup"><span data-stu-id="d6266-p129">In December, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="d6266-p130">1 月に、Windows 8.1 デスクトップに Windows 10 Enterprise がインストールされます。(Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="d6266-p130">In January, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="d6266-p131">2 月に、Office 2013 に代わって Office 365 ProPlus がインストールされます。(Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="d6266-p131">In February, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="d6266-217">3 月に、デバイス登録を受け、アプリ ポリシーとデバイス ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="d6266-217">In March, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="d6266-218">(モバイル デバイス管理)</span><span class="sxs-lookup"><span data-stu-id="d6266-218">(Mobile device management)</span></span>
- <span data-ttu-id="d6266-p133">4 月には Azure Information Protection クライアントがインストールされて、ドキュメントにラベルを適用する方法のトレーニングを受けます。(情報の保護)</span><span class="sxs-lookup"><span data-stu-id="d6266-p133">In April, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="d6266-221">結果は、連続するパイロット ロールアウトの間で 30 日間の間隔になります。</span><span class="sxs-lookup"><span data-stu-id="d6266-221">The result is a 30-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="d6266-222">例として、簡素化されたエンドユーザー エクスペリエンスを次に示します。</span><span class="sxs-lookup"><span data-stu-id="d6266-222">Here’s a simplified end-user experience as an example:</span></span>

- <span data-ttu-id="d6266-p134">1 月に、MFA 用にスマート フォンを使用する必要があります。(ユーザー情報)</span><span class="sxs-lookup"><span data-stu-id="d6266-p134">In January, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="d6266-p135">2 月に、Windows 8.1 デスクトップに Windows 10 Enterprise がインストールされます。(Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="d6266-p135">In February, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="d6266-p136">3 月に、Office 2013 に代わって Office 365 ProPlus がインストールされます。(Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="d6266-p136">In March, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="d6266-229">4 月に、デバイス登録を受け、アプリ ポリシーとデバイス ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="d6266-229">In April, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="d6266-230">(モバイル デバイス管理)</span><span class="sxs-lookup"><span data-stu-id="d6266-230">(Mobile device management)</span></span>
- <span data-ttu-id="d6266-p138">5 月には Azure Information Protection クライアントがインストールされて、ドキュメントにラベルを適用する方法のトレーニングを受けます。(情報の保護)</span><span class="sxs-lookup"><span data-stu-id="d6266-p138">In May, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="d6266-233">結果は、連続するユーザー ロールアウトの間で 30 日間の間隔になります。</span><span class="sxs-lookup"><span data-stu-id="d6266-233">The result is a 30-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="d6266-234">この展開戦略の利点は、Microsoft 365 Enterprise 基盤インフラストラクチャの完全に展開にかかる時間がさらに短くなることです。エンドユーザーが同時に複数のロールアウトに対処する必要もありません。</span><span class="sxs-lookup"><span data-stu-id="d6266-234">The advantage to this deployment strategy is that it can take even less time to fully deploy the Microsoft 365 Enterprise foundation infrastructure, still without having end-users deal with multiple rollouts the same time.</span></span> <span data-ttu-id="d6266-235">ただし、ユーザーは連続するフェーズ間で休憩を取ることはできません。</span><span class="sxs-lookup"><span data-stu-id="d6266-235">However, users don’t get a break between successive phases.</span></span>

### <a name="up-front-infrastructure-and-rollout-of-the-end-to-end-configuration"></a><span data-ttu-id="d6266-236">事前のインフラストラクチャとエンド ツー エンド構成のロールアウト</span><span class="sxs-lookup"><span data-stu-id="d6266-236">Up-front infrastructure and rollout of the end-to-end configuration</span></span>

<span data-ttu-id="d6266-237">フェーズ 2 から 6 を 1 つの展開セグメントに圧縮することができる、小規模な組織の場合、結果の展開は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d6266-237">For smaller organizations with the ability to compress phases 2-6 into a single deployment segment, the resulting deployment looks like this:</span></span>
 
![事前のインフラストラクチャとエンド ツー エンド構成のロールアウト](./media/deployment-strategies-microsoft-365-enterprise/up-front.png) 

<span data-ttu-id="d6266-p140">IT 部門はフェーズ 2 から 6 のインフラストラクチャを構成してから、エンド ツー エンド機能を確認するためにパイロット ユーザーにロールアウトします。たとえば、パイロット ユーザーは以下のすべての機能を同時に取得します。</span><span class="sxs-lookup"><span data-stu-id="d6266-p140">The IT department configures the infrastructure for phases 2-6, then rolls out to the pilot users to check for the end-to-end functionality. For example, pilot users get all of this functionality at the same time:</span></span>

- <span data-ttu-id="d6266-241">MFA とその他の ID 機能 (ユーザー情報)</span><span class="sxs-lookup"><span data-stu-id="d6266-241">MFA and other identity features (Identity)</span></span>
- <span data-ttu-id="d6266-242">Windows デバイス上の Windows 10 Enterprise (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="d6266-242">Windows 10 Enterprise on Windows devices (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="d6266-243">Office スイート用の Office 365 ProPlus (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="d6266-243">Office 365 ProPlus for the Office suite (Office 365 ProPlus)</span></span>
- <span data-ttu-id="d6266-244">アプリ ポリシーとデバイス ポリシー (モバイル デバイス管理)</span><span class="sxs-lookup"><span data-stu-id="d6266-244">App and device policies (Mobile device management)</span></span>
- <span data-ttu-id="d6266-245">Azure Information Protection クライアントのインストールと、ドキュメントにラベルを適用する方法のトレーニング (情報の保護)</span><span class="sxs-lookup"><span data-stu-id="d6266-245">Azure Information Protection client installed and training on how to apply labels to documents (Information protection)</span></span>

<span data-ttu-id="d6266-246">パイロット ロールアウトが終了したら、ユーザーのロールアウトを開始します。その際、各ユーザーがすべての機能を同時に取得します。</span><span class="sxs-lookup"><span data-stu-id="d6266-246">Once the pilot rollout is concluded, the user rollout begins in which each user gets all the functionality the same time.</span></span>

## <a name="next-step"></a><span data-ttu-id="d6266-247">次の手順</span><span class="sxs-lookup"><span data-stu-id="d6266-247">Next step</span></span>

<span data-ttu-id="d6266-248">[基盤インフラストラクチャ](deploy-foundation-infrastructure.md)を使用して Microsoft 365 Enterprise の展開を開始します。</span><span class="sxs-lookup"><span data-stu-id="d6266-248">Start your deployment of Microsoft 365 Enterprise with the [foundation infrastructure](deploy-foundation-infrastructure.md).</span></span>
