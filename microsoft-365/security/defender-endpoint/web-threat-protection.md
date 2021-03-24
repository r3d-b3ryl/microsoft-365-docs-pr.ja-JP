---
title: Web の脅威から組織を保護する
description: Microsoft Defender ATP の Web 保護と、組織を保護する方法について説明します。
keywords: Web 保護、Web 脅威保護、Web 閲覧、セキュリティ、フィッシング、マルウェア、悪用、Web サイト、ネットワーク保護、エッジ、Internet Explorer、Chrome、Firefox、Web ブラウザー
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3376308988213b84bc7badb96ebacdf706d1ca5f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063635"
---
# <a name="protect-your-organization-against-web-threats"></a><span data-ttu-id="6df35-104">Web の脅威から組織を保護する</span><span class="sxs-lookup"><span data-stu-id="6df35-104">Protect your organization against web threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6df35-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="6df35-105">**Applies to:**</span></span>
- [<span data-ttu-id="6df35-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6df35-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="6df35-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6df35-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="6df35-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="6df35-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6df35-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="6df35-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="6df35-110">Web 脅威保護は [、Defender](web-protection-overview.md) for Endpoint の Web 保護の一部です。</span><span class="sxs-lookup"><span data-stu-id="6df35-110">Web threat protection is part of [Web protection](web-protection-overview.md) in Defender for Endpoint.</span></span> <span data-ttu-id="6df35-111">ネットワーク保護 [を使用して](network-protection.md) 、Web の脅威からデバイスを保護します。</span><span class="sxs-lookup"><span data-stu-id="6df35-111">It uses [network protection](network-protection.md) to secure your devices against web threats.</span></span> <span data-ttu-id="6df35-112">Microsoft Edge や Chrome や Firefox のような一般的なサード パーティ製ブラウザーと統合することで、Web 脅威保護は Web プロキシなしで Web の脅威を停止し、離れた場所やオンプレミスの間にデバイスを保護できます。</span><span class="sxs-lookup"><span data-stu-id="6df35-112">By integrating with Microsoft Edge and popular third-party browsers like Chrome and Firefox, web threat protection stops web threats without a web proxy and can protect devices while they are away or on premises.</span></span> <span data-ttu-id="6df35-113">Web 脅威保護は、フィッシング サイト、マルウェア ベクター、悪用サイト、信頼されていないサイトまたは低評価サイト、カスタム インジケーター リストでブロックしたサイトへのアクセスを [停止します](manage-indicators.md)。</span><span class="sxs-lookup"><span data-stu-id="6df35-113">Web threat protection stops access to phishing sites, malware vectors, exploit sites, untrusted or low-reputation sites, as well as sites that you have blocked in your [custom indicator list](manage-indicators.md).</span></span>

>[!Note]
><span data-ttu-id="6df35-114">デバイスが新しい顧客インジケーターを受信するには、最大で 1 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6df35-114">It can take up to an hour for devices to receive new customer indicators.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6df35-115">前提条件</span><span class="sxs-lookup"><span data-stu-id="6df35-115">Prerequisites</span></span>
<span data-ttu-id="6df35-116">Web 保護は、ネットワーク保護を使用して、Microsoft Edge およびサードパーティの Web ブラウザーで Web 閲覧のセキュリティを提供します。</span><span class="sxs-lookup"><span data-stu-id="6df35-116">Web protection uses network protection to provide web browsing security on Microsoft Edge and third-party web browsers.</span></span>

<span data-ttu-id="6df35-117">デバイスでネットワーク保護を有効にする方法:</span><span class="sxs-lookup"><span data-stu-id="6df35-117">To turn on network protection on your devices:</span></span>
- <span data-ttu-id="6df35-118">展開または再展開する前に **、ネットワーク保護を有効&、Web** ネットワーク保護の下で Defender for Endpoint セキュリティ ベースラインを編集します。</span><span class="sxs-lookup"><span data-stu-id="6df35-118">Edit the Defender for Endpoint security baseline under **Web & Network Protection** to enable network protection before deploying or redeploying it.</span></span> [<span data-ttu-id="6df35-119">Defender for Endpoint セキュリティ ベースラインの確認と割り当てについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6df35-119">Learn about reviewing and assigning the Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline)
- <span data-ttu-id="6df35-120">Intune デバイス構成、SCCM、グループ ポリシー、または MDM ソリューションを使用してネットワーク保護を有効にします。</span><span class="sxs-lookup"><span data-stu-id="6df35-120">Turn network protection on using Intune device configuration, SCCM, Group Policy, or your MDM solution.</span></span> [<span data-ttu-id="6df35-121">ネットワーク保護の有効化の詳細</span><span class="sxs-lookup"><span data-stu-id="6df35-121">Read more about enabling network protection</span></span>](enable-network-protection.md)  

>[!Note]
><span data-ttu-id="6df35-122">ネットワーク保護を [監査のみ] **に設定すると**、ブロックは使用できません。</span><span class="sxs-lookup"><span data-stu-id="6df35-122">If you set network protection to **Audit only**, blocking will be unavailable.</span></span> <span data-ttu-id="6df35-123">また、悪意のある Web サイトや望ましくない Web サイトへのアクセスを検出してログに記録できるのは、Microsoft Edge のみです。</span><span class="sxs-lookup"><span data-stu-id="6df35-123">Also, you will be able to detect and log attempts to access malicious and unwanted websites on Microsoft Edge only.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6df35-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="6df35-124">Related topics</span></span>

- [<span data-ttu-id="6df35-125">Web 保護の概要</span><span class="sxs-lookup"><span data-stu-id="6df35-125">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="6df35-126">Web 脅威保護</span><span class="sxs-lookup"><span data-stu-id="6df35-126">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="6df35-127">Web セキュリティの監視</span><span class="sxs-lookup"><span data-stu-id="6df35-127">Monitor web security</span></span>](web-protection-monitoring.md)
- [<span data-ttu-id="6df35-128">Web の脅威に対応する</span><span class="sxs-lookup"><span data-stu-id="6df35-128">Respond to web threats</span></span>](web-protection-response.md)
- [<span data-ttu-id="6df35-129">ネットワーク保護</span><span class="sxs-lookup"><span data-stu-id="6df35-129">Network protection</span></span>](network-protection.md)
