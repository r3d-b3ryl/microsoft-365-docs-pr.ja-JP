---
title: Microsoft 365ネットワーク接続位置情報サービス
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365ネットワーク接続位置情報サービス
ms.openlocfilehash: ed78d7ba48cd9666ce1aae1af5478e3b7536e1e1
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470450"
---
# <a name="microsoft-365-network-connectivity-location-services"></a><span data-ttu-id="59358-103">Microsoft 365ネットワーク接続位置情報サービス</span><span class="sxs-lookup"><span data-stu-id="59358-103">Microsoft 365 Network Connectivity Location Services</span></span>

<span data-ttu-id="59358-104">[Microsoft 365管理センターには、ネットワークインサイトとパフォーマンスに関する推奨事項が表示されます。これは、テナントから収集されたライブ パフォーマンスMicrosoft 365です。</span><span class="sxs-lookup"><span data-stu-id="59358-104">The Microsoft 365 Admin Center now shows **Network Insights and performance recommendations**, which are live performance metrics that are collected from your Microsoft 365 tenant.</span></span> <span data-ttu-id="59358-105">これらの指標は、テナントの管理ユーザーだけが表示できます。</span><span class="sxs-lookup"><span data-stu-id="59358-105">These metrics can be viewed only by administrative users in your tenant.</span></span> <span data-ttu-id="59358-106">組織のネットワーク接続は、インターネットへのネットワーク出力場所を介して、オフィスの場所ごとに設計されています。</span><span class="sxs-lookup"><span data-stu-id="59358-106">Organizational network connectivity is designed per office location through a network egress location to the Internet.</span></span> <span data-ttu-id="59358-107">Microsoft 365接続では、そのルートを使用し、インターネットを通して Microsoft サービスのフロント ドア サーバーに接続します。</span><span class="sxs-lookup"><span data-stu-id="59358-107">Microsoft 365 client connectivity uses that route and then across the Internet to Microsoft service front door servers.</span></span> <span data-ttu-id="59358-108">これらのネットワークインサイトを表示するには、オフィスの場所を特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59358-108">Identifying office locations is key to being able to show these network insights.</span></span>

## <a name="location-in-network-measurements"></a><span data-ttu-id="59358-109">ネットワーク測定値の場所</span><span class="sxs-lookup"><span data-stu-id="59358-109">Location in network measurements</span></span>

<span data-ttu-id="59358-110">組織の管理者は、この機能で使用されるネットワーク測定値に含める場所を選択できます。</span><span class="sxs-lookup"><span data-stu-id="59358-110">An organization's administrator can opt in for location to be included in the network measurements used by this feature.</span></span> <span data-ttu-id="59358-111">これにより、各オフィスがある都市の自動検出が可能です。</span><span class="sxs-lookup"><span data-stu-id="59358-111">This enables auto-discovery of the city where each office is located.</span></span> <span data-ttu-id="59358-112">位置情報は正確ではなく、300m に難読化され、都市別に分類されます。</span><span class="sxs-lookup"><span data-stu-id="59358-112">Location information is not precise and is obfuscated to 300m and categorized by city.</span></span> <span data-ttu-id="59358-113">デバイスで場所がキャプチャされた時点Windowsツール トレイに [場所の使用] アイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="59358-113">At the time when location is captured on a Windows device, the device will show a **Location In-Use** icon in the tool tray.</span></span> <span data-ttu-id="59358-114">管理者は、このアイコンの外観をユーザーに通知することができます。</span><span class="sxs-lookup"><span data-stu-id="59358-114">Administrators may want to notify users of the appearance of this icon.</span></span> <span data-ttu-id="59358-115">この処理では、場所は組織のオフィスの場所として扱われるので、人やデバイスの場所として扱われるのではありません。</span><span class="sxs-lookup"><span data-stu-id="59358-115">With this processing, the location is treated as the organization office location and not the location of a person or a device.</span></span> <span data-ttu-id="59358-116">ネットワークの分析情報は、これらの検出されたオフィスの場所の都市で表示できます。</span><span class="sxs-lookup"><span data-stu-id="59358-116">Network insights can be shown at these discovered office location cities.</span></span> <span data-ttu-id="59358-117">推奨事項の精度を高くする場合は、特定のオフィスの場所の住所を入力できます。</span><span class="sxs-lookup"><span data-stu-id="59358-117">If you want higher accuracy in the recommendations, you can enter specific office location addresses.</span></span> <span data-ttu-id="59358-118">ネットワークインサイトは、代わりにそれらの場所に集約されます。</span><span class="sxs-lookup"><span data-stu-id="59358-118">The network insights will be aggregated to those locations instead.</span></span> <span data-ttu-id="59358-119">Office 300 メートルを超える場所を集計することはできません。</span><span class="sxs-lookup"><span data-stu-id="59358-119">Office locations cannot be aggregated more closely than 300 meters.</span></span>

## <a name="location-in-the-microsoft-365-admin-center"></a><span data-ttu-id="59358-120">管理センター Microsoft 365場所</span><span class="sxs-lookup"><span data-stu-id="59358-120">Location in the Microsoft 365 Admin Center</span></span>

<span data-ttu-id="59358-121">管理センター Microsoft 365、Bingマップ コントロールを使用して、組織のオフィスの場所を表示します。</span><span class="sxs-lookup"><span data-stu-id="59358-121">In the Microsoft 365 Admin Center, Bing map controls are used to show where organization office locations are.</span></span> <span data-ttu-id="59358-122">コントロールには、選択したオフィスの場所のネットワーク境界トポロジも表示されます。</span><span class="sxs-lookup"><span data-stu-id="59358-122">The controls also show network perimeter topology for a selected office location.</span></span> <span data-ttu-id="59358-123">管理者がオフィスの場所に特定の住所の詳細を追加すると、Bing地図を提案してデータ入力を容易にするためにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="59358-123">When an administrator adds specific address details for office locations, Bing Maps is also used to suggest addresses to make data entry easier.</span></span>

## <a name="terms-of-use"></a><span data-ttu-id="59358-124">使用条件</span><span class="sxs-lookup"><span data-stu-id="59358-124">Terms of Use</span></span>

<span data-ttu-id="59358-125">ジオコードを含むBing地図提供されるコンテンツは、コンテンツが提供される製品内でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="59358-125">Any content provided through Bing Maps, including geocodes, can only be used within the product through which the content is provided.</span></span> <span data-ttu-id="59358-126">Bing地図 を利用した Microsoft 365 管理センターの位置情報サービス機能の使用は、Bing地図 End-User で利用可能な _Bing地図 End-User_ 利用規約および Microsoft プライバシーに関する声明によって <https://go.microsoft.com/?linkid=9710837> [管理されます](https://go.microsoft.com/fwlink/?LinkID=248686)。</span><span class="sxs-lookup"><span data-stu-id="59358-126">Customer's use of the Microsoft 365 Admin Center Location Services feature, powered by Bing Maps, is governed by the _Bing Maps End-User Terms of Use_ available at <https://go.microsoft.com/?linkid=9710837> and the [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?LinkID=248686).</span></span>

<span data-ttu-id="59358-127">この機能は **、tomTom** Bing地図によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="59358-127">This feature, provided through Bing Maps, is also supported by **TomTom**.</span></span> <span data-ttu-id="59358-128">TomTom の製品とサービスの詳細については、以下を参照してください [https://www.tomtom.com/legal](https://www.tomtom.com/legal) 。</span><span class="sxs-lookup"><span data-stu-id="59358-128">More information about TomTom's products and services may be found at [https://www.tomtom.com/legal](https://www.tomtom.com/legal).</span></span>

## <a name="related-topics"></a><span data-ttu-id="59358-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="59358-129">Related topics</span></span>

[<span data-ttu-id="59358-130">管理センターでのネットワークMicrosoft 365 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="59358-130">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="59358-131">Microsoft 365パフォーマンス分析情報 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="59358-131">Microsoft 365 network performance insights (preview)</span></span>](office-365-network-mac-perf-insights.md)

[<span data-ttu-id="59358-132">Microsoft 365評価 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="59358-132">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="59358-133">Microsoft 365管理センターでの接続Microsoft 365テスト (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="59358-133">Microsoft 365 connectivity test in the Microsoft 365 admin center (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)
