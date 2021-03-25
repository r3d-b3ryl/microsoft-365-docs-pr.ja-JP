---
title: Microsoft Defender ATP の機能を構成および管理する
ms.reviewer: ''
description: 攻撃表面の縮小、次世代保護などの Microsoft Defender ATP 機能の構成と管理
keywords: 構成、管理、機能、攻撃表面の縮小、次世代保護、セキュリティ制御、エンドポイントの検出と応答、自動調査と修復、セキュリティ制御、コントロール
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
ms.openlocfilehash: a0872de9774773c136bca6febd621daba5b2d7d3
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186379"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="fb016-104">Microsoft Defender for Endpoint の機能を構成および管理する</span><span class="sxs-lookup"><span data-stu-id="fb016-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fb016-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="fb016-105">**Applies to:**</span></span>
- [<span data-ttu-id="fb016-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="fb016-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fb016-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fb016-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="fb016-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="fb016-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="fb016-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="fb016-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="fb016-110">組織に最適なセキュリティ保護を実現するために、すべての Defender for Endpoint 機能を構成および管理します。</span><span class="sxs-lookup"><span data-stu-id="fb016-110">Configure and manage all the Defender for Endpoint capabilities to get the best security protection for your organization.</span></span> 


## <a name="in-this-section"></a><span data-ttu-id="fb016-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="fb016-111">In this section</span></span> 
<span data-ttu-id="fb016-112">トピック</span><span class="sxs-lookup"><span data-stu-id="fb016-112">Topic</span></span> | <span data-ttu-id="fb016-113">説明</span><span class="sxs-lookup"><span data-stu-id="fb016-113">Description</span></span> 
:---|:---
[<span data-ttu-id="fb016-114">攻撃表面の縮小機能を構成する</span><span class="sxs-lookup"><span data-stu-id="fb016-114">Configure attack surface reduction capabilities</span></span>](configure-attack-surface-reduction.md) |  <span data-ttu-id="fb016-115">構成設定が適切に設定され、悪用の軽減手法が適用されていることを確認することで、これらの一連の機能は攻撃と悪用に抵抗します。</span><span class="sxs-lookup"><span data-stu-id="fb016-115">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span> 
[<span data-ttu-id="fb016-116">次世代の保護を構成する</span><span class="sxs-lookup"><span data-stu-id="fb016-116">Configure next-generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) | <span data-ttu-id="fb016-117">次世代の保護を構成して、すべての種類の新しい脅威をキャッチします。</span><span class="sxs-lookup"><span data-stu-id="fb016-117">Configure next-generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="fb016-118">Microsoft Threat Experts の機能を構成する</span><span class="sxs-lookup"><span data-stu-id="fb016-118">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md) | <span data-ttu-id="fb016-119">Microsoft Threat Experts からサイバーセキュリティ脅威インテリジェンスを取得する方法を構成および管理します。</span><span class="sxs-lookup"><span data-stu-id="fb016-119">Configure and manage how you would like to get cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="fb016-120">Microsoft Threat Protection の統合を構成する</span><span class="sxs-lookup"><span data-stu-id="fb016-120">Configure Microsoft Threat Protection integration</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/threat-protection-integration)| <span data-ttu-id="fb016-121">Defender for Endpoint と統合する他のソリューションを構成します。</span><span class="sxs-lookup"><span data-stu-id="fb016-121">Configure other solutions that integrate with Defender for Endpoint.</span></span>
[<span data-ttu-id="fb016-122">管理と API のサポート</span><span class="sxs-lookup"><span data-stu-id="fb016-122">Management and API support</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/management-apis)| <span data-ttu-id="fb016-123">SIEM にアラートをプルするか、API を使用してカスタム アラートを作成します。</span><span class="sxs-lookup"><span data-stu-id="fb016-123">Pull alerts to your SIEM or use APIs to create custom alerts.</span></span> <span data-ttu-id="fb016-124">Power BI レポートを作成およびビルドします。</span><span class="sxs-lookup"><span data-stu-id="fb016-124">Create and build Power BI reports.</span></span> 
[<span data-ttu-id="fb016-125">Microsoft Defender セキュリティ センターの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="fb016-125">Configure Microsoft Defender Security Center settings</span></span>](preferences-setup.md) |  <span data-ttu-id="fb016-126">一般的な設定、高度な機能などのポータル関連の設定を構成し、プレビュー エクスペリエンスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="fb016-126">Configure portal-related settings such as general settings, advanced features, enable the preview experience and others.</span></span>



