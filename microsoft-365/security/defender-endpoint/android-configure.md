---
title: Android 機能用に Microsoft Defender for Endpoint を構成する
description: Android のエンドポイント用 Microsoft Defender を構成する方法について説明します。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, mde, android, configuration
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 462fa6177ee35d5d988efa985422b499e2339ff4
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935319"
---
# <a name="configure-defender-for-endpoint-on-android-features"></a><span data-ttu-id="ed0a2-104">Android の機能でエンドポイント用 Defender を構成する</span><span class="sxs-lookup"><span data-stu-id="ed0a2-104">Configure Defender for Endpoint on Android features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ed0a2-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="ed0a2-105">**Applies to:**</span></span>
- [<span data-ttu-id="ed0a2-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ed0a2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ed0a2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ed0a2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-on-android"></a><span data-ttu-id="ed0a2-108">Android 上のエンドポイント用 Defender を使用した条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="ed0a2-108">Conditional Access with Defender for Endpoint on Android</span></span>  
<span data-ttu-id="ed0a2-109">Android 上のエンドポイント用 Microsoft Defender と Microsoft Intune および Azure Active Directory を使用すると、デバイスのリスク レベルに基づいてデバイスコンプライアンスと条件付きアクセス ポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="ed0a2-109">Microsoft Defender for Endpoint on Android along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk levels.</span></span> <span data-ttu-id="ed0a2-110">Defender for Endpoint は、Intune を介してこの機能を活用するために展開できるモバイル脅威防御 (MTD) ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="ed0a2-110">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="ed0a2-111">Android および条件付きアクセスで Defender for Endpoint をセットアップする方法の詳細については [、「Defender for Endpoint and Intune」を参照してください](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="ed0a2-111">For more information about how to set up Defender for Endpoint on Android and Conditional Access, see [Defender for Endpoint and Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="ed0a2-112">カスタム インジケーターの構成</span><span class="sxs-lookup"><span data-stu-id="ed0a2-112">Configure custom indicators</span></span>  

> [!NOTE]
> <span data-ttu-id="ed0a2-113">Defender for Endpoint on Android では、IP アドレスと URL/ドメインのカスタム インジケーターの作成のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ed0a2-113">Defender for Endpoint on Android only supports creating custom indicators for IP addresses and URLs/domains.</span></span>

<span data-ttu-id="ed0a2-114">Defender for Endpoint on Android を使用すると、管理者は Android デバイスをサポートするカスタム インジケーターを構成できます。</span><span class="sxs-lookup"><span data-stu-id="ed0a2-114">Defender for Endpoint on Android enables admins to configure custom indicators to support Android devices as well.</span></span> <span data-ttu-id="ed0a2-115">カスタム インジケーターを構成する方法の詳細については、「指標の管理」 [を参照してください](manage-indicators.md)。</span><span class="sxs-lookup"><span data-stu-id="ed0a2-115">For more information on how to configure custom indicators, see [Manage indicators](manage-indicators.md).</span></span>

## <a name="configure-web-protection"></a><span data-ttu-id="ed0a2-116">Web 保護の構成</span><span class="sxs-lookup"><span data-stu-id="ed0a2-116">Configure web protection</span></span>
<span data-ttu-id="ed0a2-117">Defender for Endpoint on Android では、IT 管理者は Web 保護機能を構成できます。</span><span class="sxs-lookup"><span data-stu-id="ed0a2-117">Defender for Endpoint on Android allows IT Administrators the ability to configure the web protection feature.</span></span> <span data-ttu-id="ed0a2-118">この機能は、管理センター Microsoft エンドポイント マネージャー使用できます。</span><span class="sxs-lookup"><span data-stu-id="ed0a2-118">This capability is available within the Microsoft Endpoint Manager Admin center.</span></span>

> [!NOTE]
> <span data-ttu-id="ed0a2-119">Android 上のエンドポイントの Defender は、Web Protection 機能を提供するために VPN を使用します。</span><span class="sxs-lookup"><span data-stu-id="ed0a2-119">Defender for Endpoint on Android would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="ed0a2-120">これは通常の VPN ではなく、デバイス外のトラフィックを受け取らないローカル/自己ループ VPN です。</span><span class="sxs-lookup"><span data-stu-id="ed0a2-120">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span> <span data-ttu-id="ed0a2-121">詳細については、「Android を実行 [するデバイスで Web 保護を構成する」を参照してください](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android)。</span><span class="sxs-lookup"><span data-stu-id="ed0a2-121">For more information, see [Configure web protection on devices that run Android](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ed0a2-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed0a2-122">Related topics</span></span>
- [<span data-ttu-id="ed0a2-123">Android 用 Microsoft Defender for Endpoint の概要</span><span class="sxs-lookup"><span data-stu-id="ed0a2-123">Overview of Microsoft Defender for Endpoint on Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="ed0a2-124">Microsoft Intune を使用した Android 用 Microsoft Defender for Endpoint の展開</span><span class="sxs-lookup"><span data-stu-id="ed0a2-124">Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune</span></span>](android-intune.md)
