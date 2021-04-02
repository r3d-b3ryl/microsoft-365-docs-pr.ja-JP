---
title: Web 保護
description: Microsoft Defender ATP の Web 保護と組織を保護する方法について説明します。
keywords: Web 保護、Web 脅威保護、Web 閲覧、セキュリティ、フィッシング、マルウェア、悪用、Web サイト、ネットワーク保護、エッジ、Internet Explorer、Chrome、Firefox、Web ブラウザー、悪意のある Web サイト
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4c04ce3479ac995e59c3bdfa9a2bdcca87eca17b
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499920"
---
# <a name="web-protection"></a><span data-ttu-id="e9511-104">Web 保護</span><span class="sxs-lookup"><span data-stu-id="e9511-104">Web protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e9511-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="e9511-105">**Applies to:**</span></span>
- [<span data-ttu-id="e9511-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e9511-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e9511-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e9511-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="e9511-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="e9511-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e9511-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="e9511-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="e9511-110">Microsoft Defender for Endpoint の Web 保護は [、Web](web-threat-protection.md) 脅威保護と Web コンテンツ フィルターで構成 [される機能です](web-content-filtering.md)。</span><span class="sxs-lookup"><span data-stu-id="e9511-110">Web protection in Microsoft Defender for Endpoint is a capability made up of [Web threat protection](web-threat-protection.md) and [Web content filtering](web-content-filtering.md).</span></span> <span data-ttu-id="e9511-111">Web 保護を使用すると、Web の脅威からデバイスを保護し、望ましくないコンテンツを規制できます。</span><span class="sxs-lookup"><span data-stu-id="e9511-111">Web protection lets you secure your devices against web threats and helps you regulate unwanted content.</span></span> <span data-ttu-id="e9511-112">Microsoft Defender セキュリティ センターで Web 保護レポートを見つけるには、Web 保護に関するレポート> **行います**。</span><span class="sxs-lookup"><span data-stu-id="e9511-112">You can find Web protection reports in the Microsoft Defender Security Center by going to **Reports > Web protection**.</span></span>

![すべての Web 保護カードのイメージ](images/web-protection.png)

## <a name="web-threat-protection"></a><span data-ttu-id="e9511-114">Web の脅威に対する保護</span><span class="sxs-lookup"><span data-stu-id="e9511-114">Web threat protection</span></span>

<span data-ttu-id="e9511-115">Web 脅威保護を構成するカードは、時間の過ぎた Web 脅威検出 **と** **Web 脅威の概要です**。</span><span class="sxs-lookup"><span data-stu-id="e9511-115">The cards that make up web threat protection are **Web threat detections over time** and **Web threat summary**.</span></span>

<span data-ttu-id="e9511-116">Web 脅威保護には、次の機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e9511-116">Web threat protection includes:</span></span>
- <span data-ttu-id="e9511-117">組織に影響を与える Web 脅威に対する包括的な可視性</span><span class="sxs-lookup"><span data-stu-id="e9511-117">Comprehensive visibility into web threats affecting your organization</span></span>
- <span data-ttu-id="e9511-118">アラートと URL およびこれらの URL にアクセスするデバイスの包括的なプロファイルによる Web 関連の脅威アクティビティに対する調査機能</span><span class="sxs-lookup"><span data-stu-id="e9511-118">Investigation capabilities over web-related threat activity through alerts and comprehensive profiles of URLs and the devices that access these URLs</span></span>
- <span data-ttu-id="e9511-119">悪意のある Web サイトや望ましくない Web サイトへの一般的なアクセス傾向を追跡する一連のセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="e9511-119">A full set of security features that track general access trends to malicious and unwanted websites</span></span>

## <a name="web-content-filtering"></a><span data-ttu-id="e9511-120">Web コンテンツ フィルタリング</span><span class="sxs-lookup"><span data-stu-id="e9511-120">Web content filtering</span></span>

<span data-ttu-id="e9511-121">Web コンテンツ フィルターを構成するカードは、 **カテゴリ別の Web** アクティビティ **、Web コンテンツ** フィルターの概要、および Web アクティビティ **の概要です**。</span><span class="sxs-lookup"><span data-stu-id="e9511-121">The cards that comprise web content filtering are **Web activity by category**, **Web content filtering summary**, and **Web activity summary**.</span></span>

<span data-ttu-id="e9511-122">Web コンテンツ フィルターには、次の機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e9511-122">Web content filtering includes:</span></span>
- <span data-ttu-id="e9511-123">ユーザーが、オンプレミスまたは離れた場所を閲覧している場合でも、ブロックされたカテゴリの Web サイトにアクセスするのを防ぐ</span><span class="sxs-lookup"><span data-stu-id="e9511-123">Users are prevented from accessing websites in blocked categories, whether they are browsing on-premises or away</span></span>
- <span data-ttu-id="e9511-124">Microsoft Defender for Endpoint の役割ベースのアクセス制御設定で定義されているデバイス グループを使用して、さまざまなポリシーをさまざまなユーザーセットに簡単に [展開できます。](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac)</span><span class="sxs-lookup"><span data-stu-id="e9511-124">You can conveniently deploy varied policies to various sets of users using the device groups defined in the [Microsoft Defender for Endpoint role-based access control settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac)</span></span>
- <span data-ttu-id="e9511-125">同じ中央の場所にある Web レポートにアクセスし、実際のブロックと Web 使用状況を可視化できます。</span><span class="sxs-lookup"><span data-stu-id="e9511-125">You can access web reports in the same central location, with visibility over actual blocks and web usage</span></span>

## <a name="in-this-section"></a><span data-ttu-id="e9511-126">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e9511-126">In this section</span></span>

<span data-ttu-id="e9511-127">トピック</span><span class="sxs-lookup"><span data-stu-id="e9511-127">Topic</span></span> | <span data-ttu-id="e9511-128">説明</span><span class="sxs-lookup"><span data-stu-id="e9511-128">Description</span></span>
:---|:---
[<span data-ttu-id="e9511-129">Web の脅威に対する保護</span><span class="sxs-lookup"><span data-stu-id="e9511-129">Web threat protection</span></span>](web-threat-protection.md) | <span data-ttu-id="e9511-130">フィッシング サイト、マルウェア ベクター、悪用サイト、信頼されていないサイトまたは低評価サイト、ブロックしたサイトへのアクセスを停止します。</span><span class="sxs-lookup"><span data-stu-id="e9511-130">Stop access to phishing sites, malware vectors, exploit sites, untrusted or low-reputation sites, as well as sites that you have blocked.</span></span>
[<span data-ttu-id="e9511-131">Web コンテンツ フィルタリング</span><span class="sxs-lookup"><span data-stu-id="e9511-131">Web content filtering</span></span>](web-content-filtering.md) | <span data-ttu-id="e9511-132">コンテンツ カテゴリに基づいて Web サイトへのアクセスを追跡および調整します。</span><span class="sxs-lookup"><span data-stu-id="e9511-132">Track and regulate access to websites based on their content categories.</span></span>
