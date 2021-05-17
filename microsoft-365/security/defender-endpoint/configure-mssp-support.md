---
title: マネージ セキュリティ サービス プロバイダーのサポートを構成する
description: エンドポイント用 Microsoft Defender との MSSP 統合を構成するために必要な手順を実行する
keywords: マネージド セキュリティ サービス プロバイダー、mssp、構成、統合
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6786d423d20ec90c12d2ea712003acc787ed599d
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165251"
---
# <a name="configure-managed-security-service-provider-integration"></a><span data-ttu-id="ca1b7-104">マネージド セキュリティ サービス プロバイダーの統合を構成する</span><span class="sxs-lookup"><span data-stu-id="ca1b7-104">Configure managed security service provider integration</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ca1b7-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="ca1b7-105">**Applies to:**</span></span>
- [<span data-ttu-id="ca1b7-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ca1b7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ca1b7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ca1b7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="ca1b7-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="ca1b7-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ca1b7-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="ca1b7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)
 
[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="ca1b7-110">管理セキュリティ サービス プロバイダー (MSSP) の統合を有効にするには、次の構成手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca1b7-110">You'll need to take the following configuration steps to enable the managed security service provider (MSSP) integration.</span></span>

>[!NOTE]
><span data-ttu-id="ca1b7-111">この記事では、サービス プロバイダーとサービス コンシューマーを区別するために、次の用語を使用します。</span><span class="sxs-lookup"><span data-stu-id="ca1b7-111">The following terms are used in this article to distinguish between the service provider and service consumer:</span></span>
> - <span data-ttu-id="ca1b7-112">MSSP: 組織のセキュリティ デバイスの監視と管理を提供するセキュリティ組織。</span><span class="sxs-lookup"><span data-stu-id="ca1b7-112">MSSPs: Security organizations that offer to monitor and manage security devices for an organization.</span></span>
> - <span data-ttu-id="ca1b7-113">MSSP のお客様: MSSP のサービスを利用する組織。</span><span class="sxs-lookup"><span data-stu-id="ca1b7-113">MSSP customers: Organizations that engage the services of MSSPs.</span></span>

<span data-ttu-id="ca1b7-114">統合により、MSSP は次のアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="ca1b7-114">The integration will allow MSSPs to take the following actions:</span></span>

- <span data-ttu-id="ca1b7-115">MSSP カスタマー のポータルへのアクセスMicrosoft Defender セキュリティ センターする</span><span class="sxs-lookup"><span data-stu-id="ca1b7-115">Get access to MSSP customer's Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="ca1b7-116">電子メール通知を取得し、</span><span class="sxs-lookup"><span data-stu-id="ca1b7-116">Get email notifications, and</span></span> 
- <span data-ttu-id="ca1b7-117">セキュリティ情報とイベント管理 (SIEM) ツールを使用してアラートを取得する</span><span class="sxs-lookup"><span data-stu-id="ca1b7-117">Fetch alerts through security information and event management (SIEM) tools</span></span>

<span data-ttu-id="ca1b7-118">MSSP がこれらのアクションを実行する前に、MSSP のお客様は、MSSP がポータルにアクセスできるよう、Defender for Endpoint テナントへのアクセスを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca1b7-118">Before MSSPs can take these actions, the MSSP customer will need to grant access to their Defender for Endpoint tenant so that the MSSP can access the portal.</span></span> 
 

<span data-ttu-id="ca1b7-119">通常、MSSP のお客様は初期構成手順を実行して、MSSP にセキュリティ セントラル テナントへのアクセス権Windows Defender付与します。</span><span class="sxs-lookup"><span data-stu-id="ca1b7-119">Typically, MSSP customers take the initial configuration steps to grant MSSPs access to their Windows Defender Security Central tenant.</span></span> <span data-ttu-id="ca1b7-120">アクセスが許可された後、他の構成手順は、MSSP カスタマーまたは MSSP によって実行できます。</span><span class="sxs-lookup"><span data-stu-id="ca1b7-120">After access is granted, other configuration steps can be done by either the MSSP customer or the MSSP.</span></span>


<span data-ttu-id="ca1b7-121">一般に、次の構成手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca1b7-121">In general, the following configuration steps need to be taken:</span></span>


- <span data-ttu-id="ca1b7-122">**MSSP にアクセス権を付与Microsoft Defender セキュリティ センター**</span><span class="sxs-lookup"><span data-stu-id="ca1b7-122">**Grant the MSSP access to Microsoft Defender Security Center**</span></span> <br>
<span data-ttu-id="ca1b7-123">このアクションは、MSSP のお客様が行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca1b7-123">This action needs to be done by the MSSP customer.</span></span> <span data-ttu-id="ca1b7-124">MSSP のお客様の Defender for Endpoint テナントへの MSSP アクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="ca1b7-124">It grants the MSSP access to the MSSP customer's Defender for Endpoint tenant.</span></span>
 

- <span data-ttu-id="ca1b7-125">**MSSP に送信されるアラート通知を構成する**</span><span class="sxs-lookup"><span data-stu-id="ca1b7-125">**Configure alert notifications sent to MSSPs**</span></span> <br>
<span data-ttu-id="ca1b7-126">このアクションは、MSSP カスタマーまたは MSSP によって実行できます。</span><span class="sxs-lookup"><span data-stu-id="ca1b7-126">This action can be taken by either the MSSP customer or MSSP.</span></span> <span data-ttu-id="ca1b7-127">これにより、MSSP は、MSSP のお客様に対処する必要があるアラートを知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca1b7-127">This lets the MSSPs know what alerts they need to address for the MSSP customer.</span></span>

- <span data-ttu-id="ca1b7-128">**MSSP 顧客のテナントから SIEM システムへのアラートの取得**</span><span class="sxs-lookup"><span data-stu-id="ca1b7-128">**Fetch alerts from MSSP customer's tenant into SIEM system**</span></span> <br> <span data-ttu-id="ca1b7-129">このアクションは MSSP によって実行されます。</span><span class="sxs-lookup"><span data-stu-id="ca1b7-129">This action is taken by the MSSP.</span></span> <span data-ttu-id="ca1b7-130">これにより、MSSP は SIEM ツールでアラートをフェッチできます。</span><span class="sxs-lookup"><span data-stu-id="ca1b7-130">It allows MSSPs to fetch alerts in SIEM tools.</span></span>

- <span data-ttu-id="ca1b7-131">**API を使用して MSSP 顧客のテナントからアラートを取得する**</span><span class="sxs-lookup"><span data-stu-id="ca1b7-131">**Fetch alerts from MSSP customer's tenant using APIs**</span></span> <br>
<span data-ttu-id="ca1b7-132">このアクションは MSSP によって実行されます。</span><span class="sxs-lookup"><span data-stu-id="ca1b7-132">This action is taken by the MSSP.</span></span> <span data-ttu-id="ca1b7-133">これにより、MSSP は API を使用してアラートをフェッチできます。</span><span class="sxs-lookup"><span data-stu-id="ca1b7-133">It allows MSSPs to fetch alerts using APIs.</span></span>

## <a name="multi-tenant-access-for-mssps"></a><span data-ttu-id="ca1b7-134">MSSP のマルチテナント アクセス</span><span class="sxs-lookup"><span data-stu-id="ca1b7-134">Multi-tenant access for MSSPs</span></span>
<span data-ttu-id="ca1b7-135">マルチテナント委任アクセスを実装する方法については [、「Managed Security Service Providers](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440)のマルチテナント アクセス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca1b7-135">For information on how to implement a multi-tenant delegated access, see [Multi-tenant access for Managed Security Service Providers](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440).</span></span>



## <a name="related-topics"></a><span data-ttu-id="ca1b7-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="ca1b7-136">Related topics</span></span>
- [<span data-ttu-id="ca1b7-137">ポータルへの MSSP アクセスを許可する</span><span class="sxs-lookup"><span data-stu-id="ca1b7-137">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="ca1b7-138">MSSP カスタマー ポータルにアクセスする</span><span class="sxs-lookup"><span data-stu-id="ca1b7-138">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="ca1b7-139">アラート通知を構成する</span><span class="sxs-lookup"><span data-stu-id="ca1b7-139">Configure alert notifications</span></span>](configure-mssp-notifications.md)
- [<span data-ttu-id="ca1b7-140">顧客テナントからアラートを取得する</span><span class="sxs-lookup"><span data-stu-id="ca1b7-140">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)

