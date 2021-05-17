---
title: Microsoft 365 エンドポイント
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: トラフィックの宛先 IP アドレスと URL Microsoft 365、異なるクラウドのインターネット エンドポイントに関する記事のMicrosoft 365してください。
ms.openlocfilehash: 159c8e7dea6fe241ab44b283b1193397c3ad70e3
ms.sourcegitcommit: a76de3d1604d755b29053e7bf557c0008be6ad23
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2021
ms.locfileid: "49787905"
---
# <a name="microsoft-365-endpoints"></a><span data-ttu-id="4d2fb-103">Microsoft 365 エンドポイント</span><span class="sxs-lookup"><span data-stu-id="4d2fb-103">Microsoft 365 endpoints</span></span>

<span data-ttu-id="4d2fb-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="4d2fb-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="4d2fb-105">エンドポイントは、インターネット上のトラフィックにDNS ドメイン IP アドレス、Microsoft 365 URL のセットです。</span><span class="sxs-lookup"><span data-stu-id="4d2fb-105">Endpoints are the set of destination IP addresses, DNS domain names, and URLs for Microsoft 365 traffic on the Internet.</span></span> 

<span data-ttu-id="4d2fb-106">クラウドベースのサービスMicrosoft 365パフォーマンスを最適化するには、クライアント ブラウザーとエッジ ネットワーク内のデバイスによる特別な処理が必要です。</span><span class="sxs-lookup"><span data-stu-id="4d2fb-106">To optimize performance to Microsoft 365 cloud-based services, these endpoints need special handling by your client browsers and the devices in your edge network.</span></span> <span data-ttu-id="4d2fb-107">これらのデバイスには、ファイアウォール、SSL Break and Inspect and Inspect and packet inspection devices、およびデータ損失防止システムが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4d2fb-107">These devices include firewalls, SSL Break and Inspect and packet inspection devices, and data loss prevention systems.</span></span>

<span data-ttu-id="4d2fb-108">詳細[については、「Microsoft 365エンドポイントの管理」](managing-office-365-endpoints.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d2fb-108">See [Managing Microsoft 365 endpoints](managing-office-365-endpoints.md) for the details.</span></span>

<span data-ttu-id="4d2fb-109">現在、5 つの異なるMicrosoft 365があります。</span><span class="sxs-lookup"><span data-stu-id="4d2fb-109">There are currently five different Microsoft 365 clouds.</span></span> <span data-ttu-id="4d2fb-110">次の表では、各エンドポイントの一覧にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="4d2fb-110">This table takes you to the list of endpoints for each one.</span></span>

| <span data-ttu-id="4d2fb-111">クラウド</span><span class="sxs-lookup"><span data-stu-id="4d2fb-111">Cloud</span></span> | <span data-ttu-id="4d2fb-112">説明</span><span class="sxs-lookup"><span data-stu-id="4d2fb-112">Description</span></span> |
|:-------|:-----|
| [<span data-ttu-id="4d2fb-113">世界中のエンドポイント</span><span class="sxs-lookup"><span data-stu-id="4d2fb-113">Worldwide endpoints</span></span>](urls-and-ip-address-ranges.md) | <span data-ttu-id="4d2fb-114">米国のサブスクリプション (Microsoft 365) を含む、世界中のサブスクリプションGovernment Community CloudエンドポイントGCC。</span><span class="sxs-lookup"><span data-stu-id="4d2fb-114">The endpoints for worldwide Microsoft 365 subscriptions, which include the United States Government Community Cloud (GCC).</span></span> |
| [<span data-ttu-id="4d2fb-115">米国政府の DoD エンドポイント</span><span class="sxs-lookup"><span data-stu-id="4d2fb-115">U.S. Government DoD endpoints</span></span>](microsoft-365-u-s-government-dod-endpoints.md) | <span data-ttu-id="4d2fb-116">米国国防総省 (DoD) のサブスクリプションのエンドポイント。</span><span class="sxs-lookup"><span data-stu-id="4d2fb-116">The endpoints for United States Department of Defense (DoD) subscriptions.</span></span> |
| [<span data-ttu-id="4d2fb-117">米国政府の GCC High エンドポイント</span><span class="sxs-lookup"><span data-stu-id="4d2fb-117">U.S. Government GCC High endpoints</span></span>](microsoft-365-u-s-government-gcc-high-endpoints.md) | <span data-ttu-id="4d2fb-118">米国政府機関向けコミュニティ クラウド High (GCC High) サブスクリプションのエンドポイント。</span><span class="sxs-lookup"><span data-stu-id="4d2fb-118">The endpoints for United States Government Community Cloud High (GCC High) subscriptions.</span></span> |
| [<span data-ttu-id="4d2fb-119">Microsoft 365 21Vianet エンドポイントによって動作する場合</span><span class="sxs-lookup"><span data-stu-id="4d2fb-119">Microsoft 365 operated by 21Vianet endpoints</span></span>](urls-and-ip-address-ranges-21vianet.md) | <span data-ttu-id="4d2fb-120">21Vianet がMicrosoft 365するエンドポイントは、中国でのサービスのニーズを満たMicrosoft 365設計されています。</span><span class="sxs-lookup"><span data-stu-id="4d2fb-120">The endpoints for Microsoft 365 operated by 21Vianet, which is designed to meet the needs for Microsoft 365 in China.</span></span> |
| [<span data-ttu-id="4d2fb-121">Microsoft 365ドイツのエンドポイント</span><span class="sxs-lookup"><span data-stu-id="4d2fb-121">Microsoft 365 Germany endpoints</span></span>](microsoft-365-germany-endpoints.md) | <span data-ttu-id="4d2fb-122">ヨーロッパにある、規制が最も厳しいドイツ、欧州連合 (EU)、および欧州自由貿易連合 (EFTA) のお客様向けの特別なクラウドのエンドポイント。</span><span class="sxs-lookup"><span data-stu-id="4d2fb-122">The endpoints for a separate cloud in Europe for the most regulated customers in Germany, the European Union (EU), and the European Free Trade Association (EFTA).</span></span> |
|||

<span data-ttu-id="4d2fb-123">クラウドのエンドポイントの最新リストの取得を自動化するには、「Microsoft 365 IP アドレスと URL Web サービスOffice 365[を参照してください](microsoft-365-ip-web-service.md)。</span><span class="sxs-lookup"><span data-stu-id="4d2fb-123">To automate getting the latest list of endpoints for your Microsoft 365 cloud, see the [Office 365 IP Address and URL Web service](microsoft-365-ip-web-service.md).</span></span>

<span data-ttu-id="4d2fb-124">その他のエンドポイントについては次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d2fb-124">For additional endpoints, see these articles:</span></span>

- [<span data-ttu-id="4d2fb-125">Web サービスに含まれていないその他のエンドポイント</span><span class="sxs-lookup"><span data-stu-id="4d2fb-125">Additional endpoints not included in the Web service</span></span>](additional-office365-ip-addresses-and-urls.md)
- [<span data-ttu-id="4d2fb-126">Office 2016 for Mac でのネットワーク要求</span><span class="sxs-lookup"><span data-stu-id="4d2fb-126">Network requests in Office 2016 for Mac</span></span>](network-requests-in-office-2016-for-mac.md)

<span data-ttu-id="4d2fb-127">ネットワーク機器ベンダーの場合は、ネットワーク機器ベンダーに[Office 365 ネットワーク パートナー プログラム。](microsoft-365-networking-partner-program.md)</span><span class="sxs-lookup"><span data-stu-id="4d2fb-127">If you are a network equipment vendor, join the [Office 365 Networking Partner Program](microsoft-365-networking-partner-program.md).</span></span> <span data-ttu-id="4d2fb-128">プログラムに登録して、ネットワークMicrosoft 365原則を製品とソリューションに組み込みます。</span><span class="sxs-lookup"><span data-stu-id="4d2fb-128">Enroll in the program to build Microsoft 365 network connectivity principles into your products and solutions.</span></span> 
