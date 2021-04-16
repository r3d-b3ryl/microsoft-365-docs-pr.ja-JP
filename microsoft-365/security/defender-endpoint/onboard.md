---
title: Microsoft Defender for Endpoint の機能を構成および管理する
ms.reviewer: ''
description: 攻撃表面の縮小や次世代保護などの Microsoft Defender for Endpoint 機能の構成と管理
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 3ad23e030048506784edd8f1988fa33263a085ae
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861337"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="55b3d-104">Microsoft Defender for Endpoint の機能を構成および管理する</span><span class="sxs-lookup"><span data-stu-id="55b3d-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="55b3d-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="55b3d-105">**Applies to:**</span></span>

- [<span data-ttu-id="55b3d-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="55b3d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="55b3d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="55b3d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="55b3d-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="55b3d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="55b3d-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="55b3d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="55b3d-110">Defender for Endpoint の機能を構成および管理し、組織に最適なセキュリティ保護を得る方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="55b3d-110">Learn how to configure and manage Defender for Endpoint features, to get the best security protection for your organization.</span></span>

<span data-ttu-id="55b3d-111">組織内の新しいデバイスの接続に関する実用的なアドバイスについては、「デバイスを Microsoft Defender for Endpoint Service にオンボードする」 [を参照してください](./onboard-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="55b3d-111">For practical advice on connecting new devices in your organization, see [Onboard devices to the Microsoft Defender for Endpoint service](./onboard-configure.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="55b3d-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="55b3d-112">In this section</span></span>

<span data-ttu-id="55b3d-113">トピック</span><span class="sxs-lookup"><span data-stu-id="55b3d-113">Topic</span></span> | <span data-ttu-id="55b3d-114">説明</span><span class="sxs-lookup"><span data-stu-id="55b3d-114">Description</span></span>
:---|:---
[<span data-ttu-id="55b3d-115">Microsoft Defender セキュリティ センターの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="55b3d-115">Configure Microsoft Defender Security Center settings</span></span>](preferences-setup.md) | <span data-ttu-id="55b3d-116">一般的な設定、高度な機能などのポータル関連の設定を構成するか、プレビュー エクスペリエンスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="55b3d-116">Configure portal-related settings such as general settings, advanced features, or enable the preview experience.</span></span>
[<span data-ttu-id="55b3d-117">攻撃表面の縮小機能を構成する</span><span class="sxs-lookup"><span data-stu-id="55b3d-117">Configure attack surface reduction capabilities</span></span>](configure-attack-surface-reduction.md) | <span data-ttu-id="55b3d-118">攻撃表面の縮小機能を構成し、設定が適切に適用され、悪用の軽減方法が設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="55b3d-118">Configure attack surface reduction capabilities, to ensure that settings are properly applied, and exploit mitigation techniques are set.</span></span>
[<span data-ttu-id="55b3d-119">次世代の保護を構成する</span><span class="sxs-lookup"><span data-stu-id="55b3d-119">Configure next-generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) | <span data-ttu-id="55b3d-120">次世代の保護を構成して、すべての種類の新しい脅威をキャッチします。</span><span class="sxs-lookup"><span data-stu-id="55b3d-120">Configure next-generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="55b3d-121">Microsoft Threat Experts の機能を構成する</span><span class="sxs-lookup"><span data-stu-id="55b3d-121">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md) | <span data-ttu-id="55b3d-122">Microsoft Threat Experts のサイバーセキュリティ脅威インテリジェンスを構成および管理します。</span><span class="sxs-lookup"><span data-stu-id="55b3d-122">Configure and manage cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="55b3d-123">Microsoft Threat Protection の統合を構成する</span><span class="sxs-lookup"><span data-stu-id="55b3d-123">Configure Microsoft Threat Protection integration</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/threat-protection-integration) | <span data-ttu-id="55b3d-124">Defender for Endpoint と統合する他のソリューションを構成します。</span><span class="sxs-lookup"><span data-stu-id="55b3d-124">Configure other solutions that integrate with Defender for Endpoint.</span></span>
[<span data-ttu-id="55b3d-125">管理と API のサポート</span><span class="sxs-lookup"><span data-stu-id="55b3d-125">Management and API support</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/management-apis) | <span data-ttu-id="55b3d-126">セキュリティ情報とイベント管理 (SIEM) にアラートをプルするか、API を使用してカスタム アラートを作成します。</span><span class="sxs-lookup"><span data-stu-id="55b3d-126">Pull alerts to your Security Information and Event Management (SIEM) or use APIs to create custom alerts.</span></span> <span data-ttu-id="55b3d-127">Power BI レポートを作成およびビルドします。</span><span class="sxs-lookup"><span data-stu-id="55b3d-127">Create and build Power BI reports.</span></span>
