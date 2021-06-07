---
title: 管理と API の概要
ms.reviewer: ''
description: Microsoft Defender for Endpoint の管理ツールと API カテゴリについて説明します。
keywords: オンボーディング、api、siem、rbac、access、portal、統合、調査、応答、エンティティ、エンティティ、ユーザー コンテキスト、アプリケーション コンテキスト、ストリーミング
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
ms.openlocfilehash: 34fb58c2e32f69cda064bb6db4b180c78ba5d451
ms.sourcegitcommit: f0118e61e490496cb23189cc5c73b23e2ba939be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2021
ms.locfileid: "52780155"
---
# <a name="overview-of-management-and-apis"></a><span data-ttu-id="b9aa6-104">管理と API の概要</span><span class="sxs-lookup"><span data-stu-id="b9aa6-104">Overview of management and APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b9aa6-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="b9aa6-105">**Applies to:**</span></span>
- [<span data-ttu-id="b9aa6-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b9aa6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b9aa6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b9aa6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b9aa6-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="b9aa6-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b9aa6-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="b9aa6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mgt-apis-abovefoldlink)


<span data-ttu-id="b9aa6-110">Defender for Endpoint は、お客様がプラットフォームを簡単に採用できるよう、さまざまなオプションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b9aa6-110">Defender for Endpoint supports a wide variety of options to ensure that customers can easily adopt the platform.</span></span> 

<span data-ttu-id="b9aa6-111">お客様の環境や構造が異なることがあります。 Defender for Endpoint は、さまざまなお客様の要件に合わせて柔軟性ときめ細かな制御で作成されました。</span><span class="sxs-lookup"><span data-stu-id="b9aa6-111">Acknowledging that customer environments and structures can vary, Defender for Endpoint was created with flexibility and granular control to fit varying customer requirements.</span></span> 

## <a name="endpoint-onboarding-and-portal-access"></a><span data-ttu-id="b9aa6-112">エンドポイントのオンボーディングとポータル アクセス</span><span class="sxs-lookup"><span data-stu-id="b9aa6-112">Endpoint onboarding and portal access</span></span> 

<span data-ttu-id="b9aa6-113">デバイスオンボーディングは、クライアント デバイス用の Microsoft エンドポイント マネージャー と Microsoft Intune、サーバー デバイス用の Azure Defender に完全に統合され、構成、展開、監視の完全なエンドツーエンドエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="b9aa6-113">Device onboarding is fully integrated into Microsoft Endpoint Manager and Microsoft Intune for client devices and Azure Defender for server devices, providing complete end-to-end experience of configuration, deployment, and monitoring.</span></span> <span data-ttu-id="b9aa6-114">さらに、Microsoft Defender for Endpoint では、デバイス管理に使用されるグループ ポリシーや他のサード パーティ製ツールもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b9aa6-114">In addition, Microsoft Defender for Endpoint supports Group Policy and other third-party tools used for devices management.</span></span>

<span data-ttu-id="b9aa6-115">Defender for Endpoint は、役割ベースのアクセス制御 (RBAC) の柔軟性を通じて、ポータルにアクセスできるユーザーが見て実行できる機能を詳細に制御します。</span><span class="sxs-lookup"><span data-stu-id="b9aa6-115">Defender for Endpoint provides fine-grained control over what users with access to the portal can see and do through the flexibility of role-based access control (RBAC).</span></span> <span data-ttu-id="b9aa6-116">RBAC モデルは、セキュリティ チーム構造のすべての機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="b9aa6-116">The RBAC model supports all flavors of security teams structure:</span></span>
- <span data-ttu-id="b9aa6-117">グローバルに分散した組織とセキュリティ チーム</span><span class="sxs-lookup"><span data-stu-id="b9aa6-117">Globally distributed organizations and security teams</span></span>
- <span data-ttu-id="b9aa6-118">階層モデルのセキュリティ運用チーム</span><span class="sxs-lookup"><span data-stu-id="b9aa6-118">Tiered model security operations teams</span></span>
- <span data-ttu-id="b9aa6-119">単一のグローバル セキュリティ運用チームによる完全に分離された部門</span><span class="sxs-lookup"><span data-stu-id="b9aa6-119">Fully segregated divisions with single centralized global security operations teams</span></span> 

## <a name="available-apis"></a><span data-ttu-id="b9aa6-120">使用可能な API</span><span class="sxs-lookup"><span data-stu-id="b9aa6-120">Available APIs</span></span>
<span data-ttu-id="b9aa6-121">Microsoft Defender for Endpoint ソリューションは、統合対応プラットフォームの上に構築されています。</span><span class="sxs-lookup"><span data-stu-id="b9aa6-121">The Microsoft Defender for Endpoint solution is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="b9aa6-122">Defender for Endpoint は、一連のプログラム API を使用して、そのデータとアクションの多くを公開します。</span><span class="sxs-lookup"><span data-stu-id="b9aa6-122">Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="b9aa6-123">これらの API を使用すると、Defender for Endpoint の機能に基づいてワークフローを自動化し、革新することができます。</span><span class="sxs-lookup"><span data-stu-id="b9aa6-123">Those APIs will enable you to automate workflows and innovate based on Defender for Endpoint capabilities.</span></span>

![使用可能な API のイメージと Microsoft Defender for Endpoint での統合](images/mdatp-apis.png)  

<span data-ttu-id="b9aa6-125">Defender for Endpoint API は、次の 3 つのグループにグループ化できます。</span><span class="sxs-lookup"><span data-stu-id="b9aa6-125">The Defender for Endpoint APIs can be grouped into three:</span></span>
- <span data-ttu-id="b9aa6-126">エンドポイント API 用 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b9aa6-126">Microsoft Defender for Endpoint APIs</span></span> 
- <span data-ttu-id="b9aa6-127">生データ ストリーミング API</span><span class="sxs-lookup"><span data-stu-id="b9aa6-127">Raw data streaming API</span></span>
- <span data-ttu-id="b9aa6-128">SIEM 統合</span><span class="sxs-lookup"><span data-stu-id="b9aa6-128">SIEM integration</span></span>

## <a name="microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="b9aa6-129">エンドポイント API 用 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b9aa6-129">Microsoft Defender for Endpoint APIs</span></span>

<span data-ttu-id="b9aa6-130">Defender for Endpoint は、構造化された、明確で使いやすいモデルのデータと機能を公開する、ユーザーまたは SaaS アプリケーションのコンテキストでのアクセスを許可する標準の Azure AD ベースの認証および承認モデルを通じて公開される、レイヤー化された API モデルを提供します。</span><span class="sxs-lookup"><span data-stu-id="b9aa6-130">Defender for Endpoint offers a layered API model exposing data and capabilities in a structured, clear, and easy to use model, exposed through a standard Azure  AD-based authentication and authorization model allowing access in context of users or SaaS applications.</span></span> <span data-ttu-id="b9aa6-131">API モデルは、エンティティと機能を一貫性のある形式で公開するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="b9aa6-131">The API model was designed to expose entities and capabilities in a consistent form.</span></span> 

<span data-ttu-id="b9aa6-132">Defender for Endpoint の API の概要については、このビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b9aa6-132">Watch this video for a quick overview of Defender for Endpoint's APIs.</span></span> 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

<span data-ttu-id="b9aa6-133">Investigation **API** は、Defender for Endpoint の豊富さを公開します。計算エンティティまたは 'profiled' エンティティ (デバイス、ユーザー、ファイルなど) と、エンティティに関連する動作を記述する個別イベント (プロセスの作成やファイルの作成など) を公開し、クエリ ベースのデータへのアクセスを許可する調査インターフェイスを介してデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b9aa6-133">The **Investigation API** exposes the richness of Defender for Endpoint - exposing calculated or 'profiled' entities (for example, device, user, and file) and discrete events (for example, process creation and file creation) which typically describes a behavior related to an entity, enabling access to data via investigation interfaces allowing a query-based access to data.</span></span> <span data-ttu-id="b9aa6-134">詳細については、「サポートされている [API」を参照してください](exposed-apis-list.md)。</span><span class="sxs-lookup"><span data-stu-id="b9aa6-134">For more information, see [Supported APIs](exposed-apis-list.md).</span></span>

<span data-ttu-id="b9aa6-135">応答 **API** では、サービスとデバイスでアクションを実行する機能が公開され、顧客はインジケーターの取り込み、設定の管理、アラートの状態の管理、デバイスの応答アクション (ネットワークからのデバイスの分離、ファイルの検疫など) をプログラムで実行できます。</span><span class="sxs-lookup"><span data-stu-id="b9aa6-135">The **Response API** exposes the ability to take actions in the service and on devices, enabling customers to ingest indicators, manage settings, alert status, as well as take response actions on devices programmatically such as isolate devices from the network, quarantine files, and others.</span></span> 

## <a name="raw-data-streaming-api"></a><span data-ttu-id="b9aa6-136">生データ ストリーミング API</span><span class="sxs-lookup"><span data-stu-id="b9aa6-136">Raw data streaming API</span></span> 
<span data-ttu-id="b9aa6-137">Defender for Endpoint raw data streaming API は、お客様が単一のデータ ストリーム内で発生するリアルタイム イベントとアラートをインスタンスから出荷する機能を提供し、低遅延で高スループットの配信メカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="b9aa6-137">Defender for Endpoint raw data streaming API provides the ability for customers to ship real-time events and alerts from their instances as they occur within a single data stream, providing a low latency, high throughput delivery mechanism.</span></span>

<span data-ttu-id="b9aa6-138">Defender for Endpoint イベント情報は、長期的なデータ保持のために Azure ストレージに直接プッシュされ、視覚化サービスや追加のデータ処理エンジンによって使用される Azure Event Hubs にプッシュされます。</span><span class="sxs-lookup"><span data-stu-id="b9aa6-138">The Defender for Endpoint event information is pushed directly to Azure storage for long-term data retention, or to Azure Event Hubs for consumption by visualization services or additional data processing engines.</span></span> 

<span data-ttu-id="b9aa6-139">詳細については、「Raw [data streaming API」を参照してください](raw-data-export.md)。</span><span class="sxs-lookup"><span data-stu-id="b9aa6-139">For more information, see [Raw data streaming API](raw-data-export.md).</span></span>

<span data-ttu-id="b9aa6-140">Defender Streaming API Microsoft 365新しい機能には、デバイス イベントに加えて、電子メールイベントとアラート イベントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b9aa6-140">The new Microsoft 365 Defender Streaming API includes email and alert events in addition to device events.</span></span> <span data-ttu-id="b9aa6-141">詳細については、「Defender[ストリーミング API Microsoft 365を参照してください](../defender/streaming-api.md)。</span><span class="sxs-lookup"><span data-stu-id="b9aa6-141">For more information, see [Microsoft 365 Defender Streaming API](../defender/streaming-api.md).</span></span>


## <a name="siem-api"></a><span data-ttu-id="b9aa6-142">SIEM API</span><span class="sxs-lookup"><span data-stu-id="b9aa6-142">SIEM API</span></span>
<span data-ttu-id="b9aa6-143">セキュリティ情報とイベント管理 (SIEM) 統合を有効にした場合、SIEM ソリューションを使用するか、検出 REST API に直接接続することで、Microsoft Defender セキュリティ センター から検出を取得できます。</span><span class="sxs-lookup"><span data-stu-id="b9aa6-143">When you enable security information and event management (SIEM) integration, it allows you to pull detections from Microsoft Defender Security Center using your SIEM solution or by connecting directly to the detections REST API.</span></span> <span data-ttu-id="b9aa6-144">これにより、値が事前に設定された SIEM コネクタ アクセスの詳細セクションがアクティブ化され、アプリケーションが Azure Active Directory (Azure AD) テナントの下に作成されます。</span><span class="sxs-lookup"><span data-stu-id="b9aa6-144">This activates the SIEM connector access details section with pre-populated values and an application is created under your Azure Active Directory (Azure AD) tenant.</span></span> <span data-ttu-id="b9aa6-145">詳細については [、「SIEM 統合」を参照してください](enable-siem-integration.md)。</span><span class="sxs-lookup"><span data-stu-id="b9aa6-145">For more information, see [SIEM integration](enable-siem-integration.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b9aa6-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="b9aa6-146">Related topics</span></span>
- [<span data-ttu-id="b9aa6-147">エンドポイント API 用 Microsoft Defender にアクセスする </span><span class="sxs-lookup"><span data-stu-id="b9aa6-147">Access the Microsoft Defender for Endpoint APIs </span></span>](apis-intro.md)
- [<span data-ttu-id="b9aa6-148">サポートされている API</span><span class="sxs-lookup"><span data-stu-id="b9aa6-148">Supported APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="b9aa6-149">テクニカル パートナーの機会</span><span class="sxs-lookup"><span data-stu-id="b9aa6-149">Technical partner opportunities</span></span>](partner-integration.md)

