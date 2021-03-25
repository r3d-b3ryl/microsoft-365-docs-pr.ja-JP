---
title: Microsoft Defender for Endpoint の機能を構成および管理する
ms.reviewer: ''
description: 攻撃表面の縮小や次世代保護などの Microsoft Defender for Endpoint 機能の構成と管理
keywords: 構成、管理、機能、攻撃表面の縮小、次世代の保護、セキュリティ制御、エンドポイントの検出と応答、自動調査と修復、セキュリティ制御、コントロール
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 95c462829b43ae41c1fe664b2313a716078baea7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064596"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="9d1fc-104">Microsoft Defender for Endpoint の機能を構成および管理する</span><span class="sxs-lookup"><span data-stu-id="9d1fc-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="9d1fc-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="9d1fc-105">**Applies to:**</span></span>

- [<span data-ttu-id="9d1fc-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9d1fc-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2069559)

<span data-ttu-id="9d1fc-107">組織に最適なセキュリティ保護を実現するために、すべての Microsoft Defender for Endpoint 機能を構成および管理します。</span><span class="sxs-lookup"><span data-stu-id="9d1fc-107">Configure and manage all the Microsoft Defender for Endpoint capabilities to get the best security protection for your organization.</span></span> 


## <a name="in-this-section"></a><span data-ttu-id="9d1fc-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="9d1fc-108">In this section</span></span> 
<span data-ttu-id="9d1fc-109">トピック</span><span class="sxs-lookup"><span data-stu-id="9d1fc-109">Topic</span></span> | <span data-ttu-id="9d1fc-110">説明</span><span class="sxs-lookup"><span data-stu-id="9d1fc-110">Description</span></span> 
:---|:---
[<span data-ttu-id="9d1fc-111">攻撃表面の縮小機能を構成する</span><span class="sxs-lookup"><span data-stu-id="9d1fc-111">Configure attack surface reduction capabilities</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-attack-surface-reduction) |  <span data-ttu-id="9d1fc-112">構成設定が適切に設定され、悪用の軽減手法が適用されていることを確認することで、これらの一連の機能は攻撃と悪用に抵抗します。</span><span class="sxs-lookup"><span data-stu-id="9d1fc-112">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span> 
[<span data-ttu-id="9d1fc-113">次世代保護の構成</span><span class="sxs-lookup"><span data-stu-id="9d1fc-113">Configure next generation protection</span></span>](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) | <span data-ttu-id="9d1fc-114">すべての種類の新しい脅威をキャッチするために、次世代の保護を構成します。</span><span class="sxs-lookup"><span data-stu-id="9d1fc-114">Configure next generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="9d1fc-115">Microsoft Threat Experts の機能を構成する</span><span class="sxs-lookup"><span data-stu-id="9d1fc-115">Configure Microsoft Threat Experts capabilities</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-microsoft-threat-experts) | <span data-ttu-id="9d1fc-116">Microsoft Threat Experts からサイバーセキュリティ脅威インテリジェンスを取得する方法を構成および管理します。</span><span class="sxs-lookup"><span data-stu-id="9d1fc-116">Configure and manage how you would like to get cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="9d1fc-117">Microsoft 365 Defender 統合の構成</span><span class="sxs-lookup"><span data-stu-id="9d1fc-117">Configure Microsoft 365 Defender integration</span></span>](/windows/security/threat-protection/microsoft-defender-atp/threat-protection-integration)| <span data-ttu-id="9d1fc-118">Microsoft Defender for Endpoint と統合する他のソリューションを構成します。</span><span class="sxs-lookup"><span data-stu-id="9d1fc-118">Configure other solutions that integrate with Microsoft Defender for Endpoint.</span></span>
[<span data-ttu-id="9d1fc-119">管理と API のサポート</span><span class="sxs-lookup"><span data-stu-id="9d1fc-119">Management and API support</span></span>](/windows/security/threat-protection/microsoft-defender-atp/management-apis)| <span data-ttu-id="9d1fc-120">SIEM にアラートをプルするか、API を使用してカスタム アラートを作成します。</span><span class="sxs-lookup"><span data-stu-id="9d1fc-120">Pull alerts to your SIEM or use APIs to create custom alerts.</span></span> <span data-ttu-id="9d1fc-121">Power BI レポートを作成およびビルドします。</span><span class="sxs-lookup"><span data-stu-id="9d1fc-121">Create and build Power BI reports.</span></span> 
[<span data-ttu-id="9d1fc-122">Microsoft Defender セキュリティ センターの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="9d1fc-122">Configure Microsoft Defender Security Center settings</span></span>](/windows/security/threat-protection/microsoft-defender-atp/preferences-setup) |  <span data-ttu-id="9d1fc-123">一般的な設定、高度な機能などのポータル関連の設定を構成し、プレビュー エクスペリエンスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="9d1fc-123">Configure portal-related settings such as general settings, advanced features, enable the preview experience and others.</span></span>