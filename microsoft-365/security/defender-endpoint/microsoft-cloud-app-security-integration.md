---
title: Microsoft Cloud App Security の統合の概要
ms.reviewer: ''
description: Microsoft Defender for Endpoint は、すべてのクラウド アプリのネットワーク アクティビティを転送することで、クラウド アプリ セキュリティと統合します。
keywords: クラウド、アプリ、ネットワーク、可視性、使用状況
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
ms.date: 10/18/2018
ms.technology: mde
ms.openlocfilehash: d756c738f9f61638a9e7424aa3fdf639f8f02f2a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185601"
---
# <a name="microsoft-cloud-app-security-in-defender-for-endpoint-overview"></a><span data-ttu-id="be93f-104">Defender for Endpoint の Microsoft Cloud App Security の概要</span><span class="sxs-lookup"><span data-stu-id="be93f-104">Microsoft Cloud App Security in Defender for Endpoint overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="be93f-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="be93f-105">**Applies to:**</span></span>
- [<span data-ttu-id="be93f-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="be93f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="be93f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="be93f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="be93f-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="be93f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="be93f-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="be93f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="be93f-110">Microsoft Cloud App Security (Cloud App Security) は、クラウド アプリへのアクセスを制御および制限しながら、クラウドに保存されているデータに対するコンプライアンス要件を適用することで、クラウド アプリとサービスを可視化する包括的なソリューションです。</span><span class="sxs-lookup"><span data-stu-id="be93f-110">Microsoft Cloud App Security (Cloud App Security) is a comprehensive solution that gives visibility into cloud apps and services by allowing you to control and limit access to cloud apps, while enforcing compliance requirements on data stored in the cloud.</span></span> <span data-ttu-id="be93f-111">詳細については [、「Cloud App Security」を参照してください](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)。</span><span class="sxs-lookup"><span data-stu-id="be93f-111">For more information, see [Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security).</span></span>

>[!NOTE]
><span data-ttu-id="be93f-112">この機能は、Windows 10 バージョン 1809 以降を実行しているデバイスのエンタープライズ モビリティ [+](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) セキュリティの E5 ライセンスで使用できます。</span><span class="sxs-lookup"><span data-stu-id="be93f-112">This feature is available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10 version 1809 or later.</span></span>

## <a name="microsoft-defender-for-endpoint-and-cloud-app-security-integration"></a><span data-ttu-id="be93f-113">Microsoft Defender for Endpoint and Cloud App Security の統合</span><span class="sxs-lookup"><span data-stu-id="be93f-113">Microsoft Defender for Endpoint and Cloud App Security integration</span></span> 

<span data-ttu-id="be93f-114">Cloud App Security の検出は、エンタープライズ ファイアウォールおよびプロキシ サーバーからクラウド トラフィック ログに転送されるログに依存します。</span><span class="sxs-lookup"><span data-stu-id="be93f-114">Cloud App Security discovery relies on cloud traffic logs being forwarded to it from enterprise firewall and proxy servers.</span></span> <span data-ttu-id="be93f-115">Microsoft Defender for Endpoint は、すべてのクラウド アプリ のネットワーク アクティビティを収集および転送することで、クラウド アプリのセキュリティと統合し、クラウド アプリの使用状況を比類のない可視性を提供します。</span><span class="sxs-lookup"><span data-stu-id="be93f-115">Microsoft Defender for Endpoint integrates with Cloud App Security by collecting and forwarding all cloud app networking activities, providing unparalleled visibility to cloud app usage.</span></span> <span data-ttu-id="be93f-116">監視機能はデバイスに組み込み、ネットワーク アクティビティを完全にカバーします。</span><span class="sxs-lookup"><span data-stu-id="be93f-116">The monitoring functionality is built into the device, providing complete coverage of network activity.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4yQ]


<span data-ttu-id="be93f-117">この統合は、既存のクラウド アプリ セキュリティ検出に次のような大きな改善点を提供します。</span><span class="sxs-lookup"><span data-stu-id="be93f-117">The integration provides the following major improvements to the existing Cloud App Security discovery:</span></span> 

- <span data-ttu-id="be93f-118">すべての場所で利用できる - ネットワーク アクティビティはエンドポイントから直接収集されます。企業ネットワークのオンとオフのデバイスは、エンタープライズ ファイアウォールまたはプロキシ サーバー経由でルーティングされるトラフィックに依存しなくなったので、デバイスがオンまたはオフの場所で利用できます。</span><span class="sxs-lookup"><span data-stu-id="be93f-118">Available everywhere - Since the network activity is collected directly from the endpoint, it's available wherever the device is, on or off corporate network, as it's no longer depended on traffic routed through the enterprise firewall or proxy servers.</span></span> 

- <span data-ttu-id="be93f-119">クラウド トラフィック ログを Cloud App Security に転送するには、ファイアウォールとプロキシ サーバーの構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="be93f-119">Works out of the box, no configuration required - Forwarding cloud traffic logs to Cloud App Security requires firewall and proxy server configuration.</span></span> <span data-ttu-id="be93f-120">Defender for Endpoint と Cloud App Security の統合により、構成は不要です。</span><span class="sxs-lookup"><span data-stu-id="be93f-120">With the Defender for Endpoint and Cloud App Security integration, there's no configuration required.</span></span> <span data-ttu-id="be93f-121">Microsoft Defender セキュリティ センターの設定でオンにし、行くのが良いです。</span><span class="sxs-lookup"><span data-stu-id="be93f-121">Just switch it on in Microsoft Defender Security Center settings and you're good to go.</span></span> 

- <span data-ttu-id="be93f-122">デバイス コンテキスト - クラウド トラフィック ログにデバイス コンテキストが不足しています。</span><span class="sxs-lookup"><span data-stu-id="be93f-122">Device context - Cloud traffic logs lack device context.</span></span> <span data-ttu-id="be93f-123">Defender for Endpoint ネットワーク アクティビティは、デバイス コンテキスト (クラウド アプリにアクセスしたデバイス) で報告されます。そのため、ネットワーク アクティビティが行われた場所 (デバイス) と、ネットワーク アクティビティを実行したユーザー (ユーザー) を正確に理解できます。</span><span class="sxs-lookup"><span data-stu-id="be93f-123">Defender for Endpoint network activity is reported with the device context (which device accessed the cloud app), so you are able to understand exactly where (device) the network activity took place, in addition to who (user) performed it.</span></span> 

<span data-ttu-id="be93f-124">クラウド検出の詳細については、「検出されたアプリを操作 [する」を参照してください](https://docs.microsoft.com/cloud-app-security/discovered-apps)。</span><span class="sxs-lookup"><span data-stu-id="be93f-124">For more information about cloud discovery, see [Working with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>

## <a name="related-topic"></a><span data-ttu-id="be93f-125">関連トピック</span><span class="sxs-lookup"><span data-stu-id="be93f-125">Related topic</span></span>

- [<span data-ttu-id="be93f-126">Microsoft Cloud App Security の統合を構成する</span><span class="sxs-lookup"><span data-stu-id="be93f-126">Configure Microsoft Cloud App Security integration</span></span>](microsoft-cloud-app-security-config.md)
