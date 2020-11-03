---
title: エンドポイント機能の Microsoft Defender を構成および管理する
ms.reviewer: ''
description: 攻撃対象領域の削減、次世代の保護などのエンドポイント機能のために Microsoft Defender を構成および管理する
keywords: 構成、管理、機能、攻撃対象領域の削減、次世代保護、セキュリティ制御、エンドポイントの検出と応答、自動調査および修復、セキュリティ制御、制御
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.openlocfilehash: b202b30e218448794eac7588078ff3ac9cfe9ee3
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844814"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="06a68-104">エンドポイント機能の Microsoft Defender を構成および管理する</span><span class="sxs-lookup"><span data-stu-id="06a68-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="06a68-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="06a68-105">**Applies to:**</span></span>

- [<span data-ttu-id="06a68-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="06a68-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2069559)

<span data-ttu-id="06a68-107">エンドポイント機能のすべての Microsoft Defender を構成および管理して、組織に最適なセキュリティ保護を実現します。</span><span class="sxs-lookup"><span data-stu-id="06a68-107">Configure and manage all the Microsoft Defender for Endpoint capabilities to get the best security protection for your organization.</span></span> 


## <a name="in-this-section"></a><span data-ttu-id="06a68-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="06a68-108">In this section</span></span> 
<span data-ttu-id="06a68-109">トピック</span><span class="sxs-lookup"><span data-stu-id="06a68-109">Topic</span></span> | <span data-ttu-id="06a68-110">説明</span><span class="sxs-lookup"><span data-stu-id="06a68-110">Description</span></span> 
:---|:---
[<span data-ttu-id="06a68-111">攻撃対象領域の削減機能を構成する</span><span class="sxs-lookup"><span data-stu-id="06a68-111">Configure attack surface reduction capabilities</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-attack-surface-reduction) |  <span data-ttu-id="06a68-112">構成設定が適切に設定され、攻略対策の手法が適用されることにより、これらの機能セットによって攻撃と悪用が緩和されます。</span><span class="sxs-lookup"><span data-stu-id="06a68-112">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span> 
[<span data-ttu-id="06a68-113">次世代の保護を構成する</span><span class="sxs-lookup"><span data-stu-id="06a68-113">Configure next generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) | <span data-ttu-id="06a68-114">次世代の保護を構成して、新しい脅威の種類をすべてキャッチします。</span><span class="sxs-lookup"><span data-stu-id="06a68-114">Configure next generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="06a68-115">Microsoft Threat の専門家の機能を構成する</span><span class="sxs-lookup"><span data-stu-id="06a68-115">Configure Microsoft Threat Experts capabilities</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-microsoft-threat-experts) | <span data-ttu-id="06a68-116">Microsoft の脅威の専門家から cybersecurity の脅威インテリジェンスを取得する方法を構成および管理します。</span><span class="sxs-lookup"><span data-stu-id="06a68-116">Configure and manage how you would like to get cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="06a68-117">Microsoft 365 Defender の統合を構成する</span><span class="sxs-lookup"><span data-stu-id="06a68-117">Configure Microsoft 365 Defender integration</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-protection-integration)| <span data-ttu-id="06a68-118">エンドポイントの Microsoft Defender と統合されるその他のソリューションを構成します。</span><span class="sxs-lookup"><span data-stu-id="06a68-118">Configure other solutions that integrate with Microsoft Defender for Endpoint.</span></span>
[<span data-ttu-id="06a68-119">管理と API のサポート</span><span class="sxs-lookup"><span data-stu-id="06a68-119">Management and API support</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis)| <span data-ttu-id="06a68-120">通知を SIEM にプルするか、Api を使用してカスタム通知を作成します。</span><span class="sxs-lookup"><span data-stu-id="06a68-120">Pull alerts to your SIEM or use APIs to create custom alerts.</span></span> <span data-ttu-id="06a68-121">Power BI レポートを作成して構築します。</span><span class="sxs-lookup"><span data-stu-id="06a68-121">Create and build Power BI reports.</span></span> 
[<span data-ttu-id="06a68-122">Microsoft Defender セキュリティセンターの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="06a68-122">Configure Microsoft Defender Security Center settings</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/preferences-setup) |  <span data-ttu-id="06a68-123">[全般設定]、[高度な機能] などのポータル関連の設定を構成し、プレビュー環境やその他を有効にします。</span><span class="sxs-lookup"><span data-stu-id="06a68-123">Configure portal-related settings such as general settings, advanced features, enable the preview experience and others.</span></span>



