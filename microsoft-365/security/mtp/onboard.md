---
title: Microsoft Defender ATP 機能を構成および管理する
ms.reviewer: ''
description: Attack surface reduction、次世代保護、セキュリティ制御などの Microsoft Defender ATP の機能を構成および管理する
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
- m365-initiative-m365-defender
ms.topic: conceptual
ms.openlocfilehash: 774f3af001800f01ce956097f6b7441df2c0ddac
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413474"
---
# <a name="configure-and-manage-microsoft-defender-atp-capabilities"></a><span data-ttu-id="71d8d-104">Microsoft Defender ATP 機能を構成および管理する</span><span class="sxs-lookup"><span data-stu-id="71d8d-104">Configure and manage Microsoft Defender ATP capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="71d8d-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="71d8d-105">**Applies to:**</span></span>

- [<span data-ttu-id="71d8d-106">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP) </span><span class="sxs-lookup"><span data-stu-id="71d8d-106">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2069559)

<span data-ttu-id="71d8d-107">Microsoft Defender ATP のすべての機能を構成および管理して、組織にとって最適なセキュリティ保護を実現します。</span><span class="sxs-lookup"><span data-stu-id="71d8d-107">Configure and manage all the Microsoft Defender ATP capabilities to get the best security protection for your organization.</span></span> 


## <a name="in-this-section"></a><span data-ttu-id="71d8d-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="71d8d-108">In this section</span></span> 
<span data-ttu-id="71d8d-109">トピック</span><span class="sxs-lookup"><span data-stu-id="71d8d-109">Topic</span></span> | <span data-ttu-id="71d8d-110">説明</span><span class="sxs-lookup"><span data-stu-id="71d8d-110">Description</span></span> 
:---|:---
[<span data-ttu-id="71d8d-111">攻撃対象領域の削減機能を構成する</span><span class="sxs-lookup"><span data-stu-id="71d8d-111">Configure attack surface reduction capabilities</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-attack-surface-reduction) |  <span data-ttu-id="71d8d-112">構成設定が適切に設定され、攻略対策の手法が適用されることにより、これらの機能セットが攻撃や exploitations に抵抗されます。</span><span class="sxs-lookup"><span data-stu-id="71d8d-112">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitations.</span></span> 
[<span data-ttu-id="71d8d-113">次世代の保護を構成する</span><span class="sxs-lookup"><span data-stu-id="71d8d-113">Configure next generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) | <span data-ttu-id="71d8d-114">次世代の保護を構成して、新しい脅威の種類をすべてキャッチします。</span><span class="sxs-lookup"><span data-stu-id="71d8d-114">Configure next generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="71d8d-115">Microsoft Threat の専門家の機能を構成する</span><span class="sxs-lookup"><span data-stu-id="71d8d-115">Configure Microsoft Threat Experts capabilities</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-microsoft-threat-experts) | <span data-ttu-id="71d8d-116">Microsoft の脅威の専門家から cybersecurity の脅威インテリジェンスを取得する方法を構成および管理します。</span><span class="sxs-lookup"><span data-stu-id="71d8d-116">Configure and manage how you would like to get cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="71d8d-117">Microsoft の脅威保護の統合を構成する</span><span class="sxs-lookup"><span data-stu-id="71d8d-117">Configure Microsoft Threat Protection integration</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-protection-integration)| <span data-ttu-id="71d8d-118">Microsoft Defender ATP に統合されたその他のソリューションを構成します。</span><span class="sxs-lookup"><span data-stu-id="71d8d-118">Configure other solutions that integrate with Microsoft Defender ATP.</span></span>
[<span data-ttu-id="71d8d-119">管理と API のサポート</span><span class="sxs-lookup"><span data-stu-id="71d8d-119">Management and API support</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis)| <span data-ttu-id="71d8d-120">通知を SIEM にプルするか、Api を使用してカスタム通知を作成します。</span><span class="sxs-lookup"><span data-stu-id="71d8d-120">Pull alerts to your SIEM or use APIs to create custom alerts.</span></span> <span data-ttu-id="71d8d-121">Power BI レポートを作成して構築します。</span><span class="sxs-lookup"><span data-stu-id="71d8d-121">Create and build Power BI reports.</span></span> 
[<span data-ttu-id="71d8d-122">Microsoft Defender セキュリティセンターの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="71d8d-122">Configure Microsoft Defender Security Center settings</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/preferences-setup) |  <span data-ttu-id="71d8d-123">[全般設定]、[高度な機能] などのポータル関連の設定を構成し、プレビュー画面やその他の設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="71d8d-123">Configure portal related settings such as general settings, advanced features, enable the preview experience and others.</span></span>



