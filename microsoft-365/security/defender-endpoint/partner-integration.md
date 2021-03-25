---
title: Microsoft Defender ATP パートナーの機会とシナリオ
ms.reviewer: ''
description: Microsoft Defender ATP との拡張機能と統合を構築するために、開いているフレームワークと豊富な API の上に既存のセキュリティ サービスを拡張する方法について説明します。
keywords: API、パートナー、拡張、オープン フレームワーク、API、拡張機能、統合、検出、管理、応答、脆弱性、インテリジェンス
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1db82afa06fd0b6b3d7228aaf3020c5496ed69e7
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186895"
---
# <a name="microsoft-defender-for-endpoint-partner-opportunities-and-scenarios"></a><span data-ttu-id="bb79a-104">Microsoft Defender for Endpoint パートナーの機会とシナリオ</span><span class="sxs-lookup"><span data-stu-id="bb79a-104">Microsoft Defender for Endpoint partner opportunities and scenarios</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bb79a-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="bb79a-105">**Applies to:**</span></span>
- [<span data-ttu-id="bb79a-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="bb79a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bb79a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bb79a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="bb79a-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="bb79a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="bb79a-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="bb79a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="bb79a-110">パートナーは、オープン フレームワークと豊富で完全な API の上に既存のセキュリティ サービスを簡単に拡張して、Defender for Endpoint との拡張機能と統合を構築できます。</span><span class="sxs-lookup"><span data-stu-id="bb79a-110">Partners can easily extend their existing security offerings on top of the open framework and a rich and complete set of APIs to build extensions and integrations with Defender for Endpoint.</span></span> 

<span data-ttu-id="bb79a-111">API は、検出、管理、対応、脆弱性、インテリジェンスの幅広い使用例などの機能領域にまたがっています。</span><span class="sxs-lookup"><span data-stu-id="bb79a-111">The APIs span functional areas including detection, management, response, vulnerabilities, and intelligence-wide range of use cases.</span></span> <span data-ttu-id="bb79a-112">使用例と必要性に基づいて、パートナーは Defender for Endpoint からデータをストリームまたはクエリできます。</span><span class="sxs-lookup"><span data-stu-id="bb79a-112">Based on the use case and need, partners can either stream or query data from Defender for Endpoint.</span></span> 


## <a name="scenario-1-external-alert-correlation-and-automated-investigation-and-remediation"></a><span data-ttu-id="bb79a-113">シナリオ 1: 外部アラートの相関関係と自動調査と修復</span><span class="sxs-lookup"><span data-stu-id="bb79a-113">Scenario 1: External alert correlation and Automated investigation and remediation</span></span>
<span data-ttu-id="bb79a-114">Defender for Endpoint は、インシデント対応を大規模に駆動する独自の自動調査および修復機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="bb79a-114">Defender for Endpoint offers unique automated investigation and remediation capabilities to drive incident response at scale.</span></span> 

<span data-ttu-id="bb79a-115">自動調査と対応機能をネットワーク セキュリティ製品や他のエンドポイント セキュリティ製品などの他のソリューションと統合すると、アラートに対処できます。</span><span class="sxs-lookup"><span data-stu-id="bb79a-115">Integrating the automated investigation and response capability with other solutions such as network security products or other endpoint security products will help to address alerts.</span></span> <span data-ttu-id="bb79a-116">また、この統合により、ネットワークとデバイス信号の相関関係を取り巻く複雑さを最小限に抑え、デバイスの調査と脅威の修復アクションを効率的に合理化できます。</span><span class="sxs-lookup"><span data-stu-id="bb79a-116">The integration also minimizes the complexities surrounding network and device signal correlation, effectively streamlining the investigation and threat remediation actions on devices.</span></span>

<span data-ttu-id="bb79a-117">Defender for Endpoint は、次の形式でこのシナリオのサポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="bb79a-117">Defender for Endpoint adds support for this scenario in the following forms:</span></span>

- <span data-ttu-id="bb79a-118">外部アラートを Defender for Endpoint にプッシュし、Defender for Endpoint からの追加のデバイス ベースのアラートを並べて表示できます。</span><span class="sxs-lookup"><span data-stu-id="bb79a-118">External alerts can be pushed into Defender for Endpoint and presented side by side with additional device-based alerts from Defender for Endpoint.</span></span> <span data-ttu-id="bb79a-119">このビューは、アラートの完全なコンテキスト (実際のプロセスと攻撃の完全なストーリー) を提供します。</span><span class="sxs-lookup"><span data-stu-id="bb79a-119">This view provides the full context of the alert - with the real process and the full story of attack.</span></span>

- <span data-ttu-id="bb79a-120">アラートが生成されると、企業内のすべての Defender for Endpoint 保護エンドポイント間で信号が共有されます。</span><span class="sxs-lookup"><span data-stu-id="bb79a-120">Once an alert is generated, the signal is shared across all Defender for Endpoint protected endpoints in the enterprise.</span></span> <span data-ttu-id="bb79a-121">Defender for Endpoint は、アラートに対処するために、直ちに自動化された応答またはオペレーター支援応答を受け取る。</span><span class="sxs-lookup"><span data-stu-id="bb79a-121">Defender for Endpoint takes immediate automated or operator-assisted response to address the alert.</span></span>

## <a name="scenario-2-security-orchestration-and-automation-response-soar-integration"></a><span data-ttu-id="bb79a-122">シナリオ 2: セキュリティ オーケストレーションとオートメーション応答 (SOAR) の統合</span><span class="sxs-lookup"><span data-stu-id="bb79a-122">Scenario 2: Security orchestration and automation response (SOAR) integration</span></span>
<span data-ttu-id="bb79a-123">オーケストレーション ソリューションは、プレイブックを構築し、Defender for Endpoint API がデバイス データのクエリ、デバイス分離のトリガー、ブロック/許可、アラートの解決などの応答を調整するために公開するリッチ データ モデルとアクションを統合するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bb79a-123">Orchestration solutions can help build playbooks and integrate the rich data model and actions that Defender for Endpoint APIs expose to orchestrate responses, such as query for device data, trigger device isolation, block/allow, resolve alert and others.</span></span>

## <a name="scenario-3-indicators-matching"></a><span data-ttu-id="bb79a-124">シナリオ 3: インジケーターの一致</span><span class="sxs-lookup"><span data-stu-id="bb79a-124">Scenario 3: Indicators matching</span></span> 
<span data-ttu-id="bb79a-125">侵害の指標 (IoC) 照合は、すべてのエンドポイント保護ソリューションに不可欠な機能です。</span><span class="sxs-lookup"><span data-stu-id="bb79a-125">Indicator of compromise (IoCs) matching is an essential feature in every endpoint protection solution.</span></span> <span data-ttu-id="bb79a-126">この機能は Defender for Endpoint で使用できます。エンティティの予防、検出、除外のインジケーターの一覧を設定できます。</span><span class="sxs-lookup"><span data-stu-id="bb79a-126">This capability is available in Defender for Endpoint and gives the ability to set a list of indicators for prevention, detection, and exclusion of entities.</span></span> <span data-ttu-id="bb79a-127">1 つは、実行するアクションと、アクションを適用する期間を定義できます。</span><span class="sxs-lookup"><span data-stu-id="bb79a-127">One can define the action to be taken as well as the duration for when to apply the action.</span></span>

<span data-ttu-id="bb79a-128">上記のシナリオは、プラットフォームの拡張性の例として機能します。</span><span class="sxs-lookup"><span data-stu-id="bb79a-128">The above scenarios serve as examples of the extensibility of the platform.</span></span> <span data-ttu-id="bb79a-129">例に限定されるのではなく、オープン フレームワークを活用して他のシナリオを発見し、探索してください。</span><span class="sxs-lookup"><span data-stu-id="bb79a-129">You are not limited to the examples and we certainly encourage you to leverage the open framework to discover and explore other scenarios.</span></span>

<span data-ttu-id="bb79a-130">「エンドポイント向け Microsoft Defender パートナーになる」の手順に従 [って、Defender](get-started-partner-integration.md) for Endpoint にソリューションを統合します。</span><span class="sxs-lookup"><span data-stu-id="bb79a-130">Follow the steps in [Become a Microsoft Defender for Endpoint partner](get-started-partner-integration.md) to integrate your solution in Defender for Endpoint.</span></span>

## <a name="related-topic"></a><span data-ttu-id="bb79a-131">関連トピック</span><span class="sxs-lookup"><span data-stu-id="bb79a-131">Related topic</span></span>
- [<span data-ttu-id="bb79a-132">管理と API の概要</span><span class="sxs-lookup"><span data-stu-id="bb79a-132">Overview of management and APIs</span></span>](management-apis.md)
