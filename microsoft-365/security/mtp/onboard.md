---
title: エンドポイント向け Microsoft Defender の機能を構成および管理する
ms.reviewer: ''
description: 攻撃表面の縮小や次世代の保護など、エンドポイント向け Microsoft Defender の機能を構成および管理する
keywords: 構成, 管理, 機能, 攻撃表面の縮小, 次世代の保護, セキュリティ 制御, エンドポイントの検出と対応, 自動調査と修復, セキュリティ コントロール, コントロール
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: d04177ef38c1bd04b0b73e29de9d8ab6fc0893ce
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930128"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="79d50-104">エンドポイント向け Microsoft Defender の機能を構成および管理する</span><span class="sxs-lookup"><span data-stu-id="79d50-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="79d50-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="79d50-105">**Applies to:**</span></span>

- [<span data-ttu-id="79d50-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="79d50-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2069559)

<span data-ttu-id="79d50-107">組織に最適なセキュリティ保護を実現するために、すべての Microsoft Defender for Endpoint 機能を構成および管理します。</span><span class="sxs-lookup"><span data-stu-id="79d50-107">Configure and manage all the Microsoft Defender for Endpoint capabilities to get the best security protection for your organization.</span></span> 


## <a name="in-this-section"></a><span data-ttu-id="79d50-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="79d50-108">In this section</span></span> 
<span data-ttu-id="79d50-109">トピック</span><span class="sxs-lookup"><span data-stu-id="79d50-109">Topic</span></span> | <span data-ttu-id="79d50-110">説明</span><span class="sxs-lookup"><span data-stu-id="79d50-110">Description</span></span> 
:---|:---
[<span data-ttu-id="79d50-111">攻撃表面の縮小機能を構成する</span><span class="sxs-lookup"><span data-stu-id="79d50-111">Configure attack surface reduction capabilities</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-attack-surface-reduction) |  <span data-ttu-id="79d50-112">構成設定が適切に設定され、悪用の軽減策の手法が適用されていることを確認することで、これらの一連の機能は攻撃や悪用に抵抗します。</span><span class="sxs-lookup"><span data-stu-id="79d50-112">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span> 
[<span data-ttu-id="79d50-113">次世代の保護を構成する</span><span class="sxs-lookup"><span data-stu-id="79d50-113">Configure next generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) | <span data-ttu-id="79d50-114">次世代の保護を構成して、すべての種類の新たな脅威をキャッチします。</span><span class="sxs-lookup"><span data-stu-id="79d50-114">Configure next generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="79d50-115">Microsoft Threat Experts の機能を構成する</span><span class="sxs-lookup"><span data-stu-id="79d50-115">Configure Microsoft Threat Experts capabilities</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-microsoft-threat-experts) | <span data-ttu-id="79d50-116">Microsoft Threat Experts からサイバーセキュリティ脅威インテリジェンスを取得する方法を構成および管理します。</span><span class="sxs-lookup"><span data-stu-id="79d50-116">Configure and manage how you would like to get cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="79d50-117">Microsoft 365 Defender 統合を構成する</span><span class="sxs-lookup"><span data-stu-id="79d50-117">Configure Microsoft 365 Defender integration</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-protection-integration)| <span data-ttu-id="79d50-118">Microsoft Defender for Endpoint と統合する他のソリューションを構成します。</span><span class="sxs-lookup"><span data-stu-id="79d50-118">Configure other solutions that integrate with Microsoft Defender for Endpoint.</span></span>
[<span data-ttu-id="79d50-119">管理と API のサポート</span><span class="sxs-lookup"><span data-stu-id="79d50-119">Management and API support</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis)| <span data-ttu-id="79d50-120">SIEM にアラートをプルするか、API を使用してカスタム アラートを作成します。</span><span class="sxs-lookup"><span data-stu-id="79d50-120">Pull alerts to your SIEM or use APIs to create custom alerts.</span></span> <span data-ttu-id="79d50-121">Power BI レポートを作成して構築します。</span><span class="sxs-lookup"><span data-stu-id="79d50-121">Create and build Power BI reports.</span></span> 
[<span data-ttu-id="79d50-122">Microsoft Defender セキュリティ センターの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="79d50-122">Configure Microsoft Defender Security Center settings</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/preferences-setup) |  <span data-ttu-id="79d50-123">全般設定、高度な機能などのポータル関連の設定を構成し、プレビュー エクスペリエンスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="79d50-123">Configure portal-related settings such as general settings, advanced features, enable the preview experience and others.</span></span>



