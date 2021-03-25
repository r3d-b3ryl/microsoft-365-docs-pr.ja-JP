---
title: McAfee から Microsoft Defender for Endpoint への移行
description: McAfee から Microsoft Defender for Endpoint に切り替えます。 概要については、この記事をお読みください。
keywords: 移行、 Windows Defender Advanced Threat Protection, atp, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-mcafeemigrate
- m365solution-overview
ms.topic: article
ms.custom: migrationguides
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: f46fb354537b61630172d3d735ce6b24f25ab39a
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198835"
---
# <a name="migrate-from-mcafee-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="113e5-105">McAfee から Microsoft Defender for Endpoint への移行</span><span class="sxs-lookup"><span data-stu-id="113e5-105">Migrate from McAfee to Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="113e5-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="113e5-106">**Applies to:**</span></span>
- [<span data-ttu-id="113e5-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="113e5-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="113e5-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="113e5-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="113e5-109">McAfee Endpoint Security (McAfee) から Microsoft [Defender for](https://docs.microsoft.com/windows/security/threat-protection) Endpoint (Microsoft Defender for Endpoint) に切り替える予定の場合は、適切な場所にいます。</span><span class="sxs-lookup"><span data-stu-id="113e5-109">If you are planning to switch from McAfee Endpoint Security (McAfee) to [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft Defender for Endpoint), you're in the right place.</span></span> <span data-ttu-id="113e5-110">この記事をガイドとして使用します。</span><span class="sxs-lookup"><span data-stu-id="113e5-110">Use this article as a guide.</span></span>


:::image type="content" source="images/mcafee-mde-migration.png" alt-text="McAfee から Defender for Endpoint への移行の概要":::

<span data-ttu-id="113e5-112">McAfee から Defender for Endpoint に切り替える場合は、アクティブ モードでマカフィー ソリューションを開始し、パッシブ モードで Defender for Endpoint を構成し、Defender for Endpoint にオンボードし、Defender for Endpoint をアクティブ モードに設定し、McAfee を削除します。</span><span class="sxs-lookup"><span data-stu-id="113e5-112">When you make the switch from McAfee to Defender for Endpoint, you begin with your McAfee solution in active mode, configure Defender for Endpoint in passive mode, onboard to Defender for Endpoint, and then set Defender for Endpoint to active mode and remove McAfee.</span></span>

## <a name="the-migration-process"></a><span data-ttu-id="113e5-113">移行プロセス</span><span class="sxs-lookup"><span data-stu-id="113e5-113">The migration process</span></span>

<span data-ttu-id="113e5-114">McAfee から Microsoft Defender for Endpoint に切り替える場合は、準備、セットアップ、オンボードの 3 つのフェーズに分かれるプロセスに従います。</span><span class="sxs-lookup"><span data-stu-id="113e5-114">When you switch from McAfee to Microsoft Defender for Endpoint, you follow a process that can be divided into three phases: Prepare, Setup, and Onboard.</span></span> 

![移行フェーズ - セットアップをオンボードで準備する](images/phase-diagrams/migration-phases.png)

|<span data-ttu-id="113e5-116">段階</span><span class="sxs-lookup"><span data-stu-id="113e5-116">Phase</span></span> |<span data-ttu-id="113e5-117">説明</span><span class="sxs-lookup"><span data-stu-id="113e5-117">Description</span></span> |
|--|--|
|[<span data-ttu-id="113e5-118">移行の準備</span><span class="sxs-lookup"><span data-stu-id="113e5-118">Prepare for your migration</span></span>](mcafee-to-microsoft-defender-prepare.md) |<span data-ttu-id="113e5-119">準備フェーズ [**では**](mcafee-to-microsoft-defender-prepare.md) 、組織のデバイスを更新し、Microsoft Defender for Endpoint を取得し、役割とアクセス許可を計画し、Microsoft Defender セキュリティ センターへのアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="113e5-119">During the [**Prepare**](mcafee-to-microsoft-defender-prepare.md) phase, you update your organization's devices, get Microsoft Defender for Endpoint, plan your roles and permissions, and grant access to the Microsoft Defender Security Center.</span></span> <span data-ttu-id="113e5-120">また、デバイス プロキシとインターネット設定を構成して、組織のデバイスと Microsoft Defender for Endpoint 間の通信を有効にします。</span><span class="sxs-lookup"><span data-stu-id="113e5-120">You also configure your device proxy and internet settings to enable communication between your organization's devices and Microsoft Defender for Endpoint.</span></span> |
|[<span data-ttu-id="113e5-121">エンドポイント用 Microsoft Defender のセットアップ</span><span class="sxs-lookup"><span data-stu-id="113e5-121">Set up Microsoft Defender for Endpoint</span></span>](mcafee-to-microsoft-defender-setup.md) |<span data-ttu-id="113e5-122">セットアップ フェーズ [**では**](mcafee-to-microsoft-defender-setup.md) 、Microsoft Defender ウイルス対策を有効にしてパッシブ モードに設定し、Microsoft Defender ウイルス対策、Microsoft Defender for Endpoint、McAfee の設定 & 除外を構成します。</span><span class="sxs-lookup"><span data-stu-id="113e5-122">During the [**Setup**](mcafee-to-microsoft-defender-setup.md) phase, you enable Microsoft Defender Antivirus and make sure it's in passive mode, and you configure settings & exclusions for Microsoft Defender Antivirus, Microsoft Defender for Endpoint, and McAfee.</span></span> <span data-ttu-id="113e5-123">デバイス グループ、コレクション、および組織単位も作成します。</span><span class="sxs-lookup"><span data-stu-id="113e5-123">You also create device groups, collections, and organizational units.</span></span> <span data-ttu-id="113e5-124">最後に、マルウェア対策ポリシーとリアルタイム保護設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="113e5-124">Finally, you configure your antimalware policies and real-time protection settings.</span></span>|
|[<span data-ttu-id="113e5-125">エンドポイント用 Microsoft Defender にオンボード</span><span class="sxs-lookup"><span data-stu-id="113e5-125">Onboard to Microsoft Defender for Endpoint</span></span>](mcafee-to-microsoft-defender-onboard.md) |<span data-ttu-id="113e5-126">オンボード フェーズ [**中に**](mcafee-to-microsoft-defender-onboard.md) 、デバイスを Microsoft Defender for Endpoint にオンボードし、それらのデバイスが Microsoft Defender for Endpoint と通信しているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="113e5-126">During the [**Onboard**](mcafee-to-microsoft-defender-onboard.md) phase, you onboard your devices to Microsoft Defender for Endpoint and verify that those devices are communicating with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="113e5-127">最後に、McAfee をアンインストールし、Microsoft Defender ウイルス対策ツールを使用した保護& Microsoft Defender for Endpoint がアクティブ モードに設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="113e5-127">Last, you uninstall McAfee and make sure that protection through Microsoft Defender Antivirus & Microsoft Defender for Endpoint is in active mode.</span></span> |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="113e5-128">Microsoft Defender for Endpoint に含まれるもの</span><span class="sxs-lookup"><span data-stu-id="113e5-128">What's included in Microsoft Defender for Endpoint?</span></span>

<span data-ttu-id="113e5-129">この移行ガイドでは、Microsoft Defender [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) for Endpoint[](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)への移行の開始点として、次世代の保護とエンドポイントの検出および応答機能に重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="113e5-129">In this migration guide, we focus on [next-generation protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) and [endpoint detection and response](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) capabilities as a starting point for moving to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="113e5-130">ただし、Microsoft Defender for Endpoint には、ウイルス対策やエンドポイント保護以外の機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="113e5-130">However, Microsoft Defender for Endpoint includes much more than antivirus and endpoint protection.</span></span> <span data-ttu-id="113e5-131">Microsoft Defender for Endpoint は、予防的な保護、侵害後の検出、自動調査、対応のための統一されたプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="113e5-131">Microsoft Defender for Endpoint is a unified platform for preventative protection, post-breach detection, automated investigation, and response.</span></span> <span data-ttu-id="113e5-132">次の表に、Microsoft Defender for Endpoint の機能の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="113e5-132">The following table summarizes features and capabilities in Microsoft Defender for Endpoint.</span></span> 

| <span data-ttu-id="113e5-133">機能/機能</span><span class="sxs-lookup"><span data-stu-id="113e5-133">Feature/Capability</span></span> | <span data-ttu-id="113e5-134">説明</span><span class="sxs-lookup"><span data-stu-id="113e5-134">Description</span></span> |
|---|---|
| [<span data-ttu-id="113e5-135">脅威&の管理</span><span class="sxs-lookup"><span data-stu-id="113e5-135">Threat & vulnerability management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) | <span data-ttu-id="113e5-136">脅威&管理機能は、エンドポイント (デバイスなど) 全体の弱点を特定、評価、修復するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="113e5-136">Threat & vulnerability management capabilities help identify, assess, and remediate weaknesses across your endpoints (such as devices).</span></span> |
| [<span data-ttu-id="113e5-137">攻撃面の縮小</span><span class="sxs-lookup"><span data-stu-id="113e5-137">Attack surface reduction</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-attack-surface-reduction) | <span data-ttu-id="113e5-138">攻撃表面の縮小ルールは、組織のデバイスとアプリケーションをサイバー脅威や攻撃から保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="113e5-138">Attack surface reduction rules help protect your organization's devices and applications from cyberthreats and attacks.</span></span> |
| [<span data-ttu-id="113e5-139">次世代の保護</span><span class="sxs-lookup"><span data-stu-id="113e5-139">Next-generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) | <span data-ttu-id="113e5-140">次世代の保護には、脅威やマルウェアのブロックに役立つ Microsoft Defender ウイルス対策が含まれています。</span><span class="sxs-lookup"><span data-stu-id="113e5-140">Next-generation protection includes Microsoft Defender Antivirus to help block threats and malware.</span></span> |
| [<span data-ttu-id="113e5-141">エンドポイントの検出および応答</span><span class="sxs-lookup"><span data-stu-id="113e5-141">Endpoint detection and response</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) | <span data-ttu-id="113e5-142">エンドポイントの検出および応答機能は、侵入の試みとアクティブな侵害を検出、調査、および対応します。</span><span class="sxs-lookup"><span data-stu-id="113e5-142">Endpoint detection and response capabilities detect, investigate, and respond to intrusion attempts and active breaches.</span></span>  |
| [<span data-ttu-id="113e5-143">高度な検出</span><span class="sxs-lookup"><span data-stu-id="113e5-143">Advanced hunting</span></span>](advanced-hunting-overview.md) | <span data-ttu-id="113e5-144">高度な検出機能により、セキュリティ運用チームは既知または潜在的な脅威のインジケーターとエンティティを検索できます。</span><span class="sxs-lookup"><span data-stu-id="113e5-144">Advanced hunting capabilities enable your security operations team to locate indicators and entities of known or potential threats.</span></span> |
| [<span data-ttu-id="113e5-145">動作のブロックと格納</span><span class="sxs-lookup"><span data-stu-id="113e5-145">Behavioral blocking and containment</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) | <span data-ttu-id="113e5-146">動作のブロックと格納機能は、脅威の実行が開始された場合でも、その動作に基づいて脅威を特定し、停止し、ツリーを処理するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="113e5-146">Behavioral blocking and containment capabilities help identify and stop threats, based on their behaviors and process trees even when the threat has started execution.</span></span> |
| [<span data-ttu-id="113e5-147">調査と修復の自動化</span><span class="sxs-lookup"><span data-stu-id="113e5-147">Automated investigation and remediation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations) | <span data-ttu-id="113e5-148">自動調査および応答機能は、アラートを調べ、侵害を解決するために直ちに修復アクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="113e5-148">Automated investigation and response capabilities examine alerts and take immediate remediation action to resolve breaches.</span></span> |
| <span data-ttu-id="113e5-149">[脅威の検出サービス](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-threat-experts) (Microsoft Threat Experts)</span><span class="sxs-lookup"><span data-stu-id="113e5-149">[Threat hunting service](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-threat-experts) (Microsoft Threat Experts)</span></span> | <span data-ttu-id="113e5-150">脅威検出サービスは、セキュリティ運用チームに専門家レベルの監視と分析を提供し、重要な脅威を見逃しなくするために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="113e5-150">Threat hunting services provide security operations teams with expert level monitoring and analysis, and to help ensure that critical threats aren't missed.</span></span> |

<span data-ttu-id="113e5-151">**詳細については、次の情報を参照してください。「Microsoft [Defender for Endpoint」を参照してください](https://docs.microsoft.com/windows/security/threat-protection)。**</span><span class="sxs-lookup"><span data-stu-id="113e5-151">**Want to learn more? See [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection).**</span></span>

## <a name="next-step"></a><span data-ttu-id="113e5-152">次の手順</span><span class="sxs-lookup"><span data-stu-id="113e5-152">Next step</span></span>

- <span data-ttu-id="113e5-153">移行の [準備に進みます](mcafee-to-microsoft-defender-prepare.md)。</span><span class="sxs-lookup"><span data-stu-id="113e5-153">Proceed to [Prepare for your migration](mcafee-to-microsoft-defender-prepare.md).</span></span>
