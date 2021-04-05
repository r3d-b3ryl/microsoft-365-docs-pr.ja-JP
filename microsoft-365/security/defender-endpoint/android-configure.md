---
title: Android 機能用に Microsoft Defender for Endpoint を構成する
description: Android 用エンドポイント用 Microsoft Defender を構成する方法について説明します。
keywords: microsoft、 defender, atp, mde, android, configuration
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
ms.openlocfilehash: c395aafc8a468cfdeaea973ab02421212870192a
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587217"
---
# <a name="configure-defender-for-endpoint-for-android-features"></a><span data-ttu-id="bcf63-104">Android の機能用に Defender for Endpoint を構成する</span><span class="sxs-lookup"><span data-stu-id="bcf63-104">Configure Defender for Endpoint for Android features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bcf63-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="bcf63-105">**Applies to:**</span></span>
- [<span data-ttu-id="bcf63-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="bcf63-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bcf63-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bcf63-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-for-android"></a><span data-ttu-id="bcf63-108">Android 用エンドポイントの Defender を使用した条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="bcf63-108">Conditional Access with Defender for Endpoint for Android</span></span>  
<span data-ttu-id="bcf63-109">Microsoft Defender for Endpoint for Android と Microsoft Intune、Azure Active Directory を組み合わせ、デバイスのリスク レベルに基づいてデバイスコンプライアンスと条件付きアクセス ポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="bcf63-109">Microsoft Defender for Endpoint for Android along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk levels.</span></span> <span data-ttu-id="bcf63-110">Defender for Endpoint は、Intune を介してこの機能を活用するために展開できるモバイル脅威防御 (MTD) ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="bcf63-110">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="bcf63-111">Defender for Endpoint for Android および条件付きアクセスをセットアップする方法の詳細については [、「Defender for Endpoint and Intune」を参照してください](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="bcf63-111">For more information about how to set up Defender for Endpoint for Android and Conditional Access, see [Defender for Endpoint and Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="bcf63-112">カスタム インジケーターの構成</span><span class="sxs-lookup"><span data-stu-id="bcf63-112">Configure custom indicators</span></span>  

> [!NOTE]
> <span data-ttu-id="bcf63-113">Defender for Endpoint for Android では、IP アドレスと URL/ドメインのカスタム インジケーターの作成のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="bcf63-113">Defender for Endpoint for Android only supports creating custom indicators for IP addresses and URLs/domains.</span></span>

<span data-ttu-id="bcf63-114">Defender for Endpoint for Android を使用すると、管理者は Android デバイスをサポートするカスタム インジケーターを構成できます。</span><span class="sxs-lookup"><span data-stu-id="bcf63-114">Defender for Endpoint for Android enables admins to configure custom indicators to support Android devices as well.</span></span> <span data-ttu-id="bcf63-115">カスタム インジケーターを構成する方法の詳細については、「指標の管理」 [を参照してください](manage-indicators.md)。</span><span class="sxs-lookup"><span data-stu-id="bcf63-115">For more information on how to configure custom indicators, see [Manage indicators](manage-indicators.md).</span></span>

## <a name="configure-web-protection"></a><span data-ttu-id="bcf63-116">Web 保護の構成</span><span class="sxs-lookup"><span data-stu-id="bcf63-116">Configure web protection</span></span>
<span data-ttu-id="bcf63-117">Defender for Endpoint for Android では、IT 管理者は Web 保護機能を構成できます。</span><span class="sxs-lookup"><span data-stu-id="bcf63-117">Defender for Endpoint for Android allows IT Administrators the ability to configure the web protection feature.</span></span> <span data-ttu-id="bcf63-118">この機能は、Microsoft Endpoint Manager 管理センター内で使用できます。</span><span class="sxs-lookup"><span data-stu-id="bcf63-118">This capability is available within the Microsoft Endpoint Manager Admin center.</span></span>

> [!NOTE]
> <span data-ttu-id="bcf63-119">Android 用エンドポイントの Defender は、Web 保護機能を提供するために VPN を使用します。</span><span class="sxs-lookup"><span data-stu-id="bcf63-119">Defender for Endpoint for Android would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="bcf63-120">これは通常の VPN ではなく、デバイス外のトラフィックを受け取らないローカル/自己ループ VPN です。</span><span class="sxs-lookup"><span data-stu-id="bcf63-120">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span> <span data-ttu-id="bcf63-121">詳細については、「Android を実行 [するデバイスで Web 保護を構成する」を参照してください](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android)。</span><span class="sxs-lookup"><span data-stu-id="bcf63-121">For more information, see [Configure web protection on devices that run Android](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android).</span></span>

## <a name="related-topics"></a><span data-ttu-id="bcf63-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="bcf63-122">Related topics</span></span>
- [<span data-ttu-id="bcf63-123">Android 用 Microsoft Defender for Endpoint の概要</span><span class="sxs-lookup"><span data-stu-id="bcf63-123">Overview of Microsoft Defender for Endpoint for Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="bcf63-124">Microsoft Intune を使用した Android 用 Microsoft Defender for Endpoint の展開</span><span class="sxs-lookup"><span data-stu-id="bcf63-124">Deploy Microsoft Defender for Endpoint for Android with Microsoft Intune</span></span>](android-intune.md)
