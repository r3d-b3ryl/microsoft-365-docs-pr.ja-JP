---
title: Microsoft 以外のエンドポイント ソリューションから Microsoft Defender for Endpoint への切り替え
description: Microsoft Defender for Endpoint に切り替えます。 概要については、この記事をお読みください。
keywords: 移行、 Windows Defender Advanced endpoint protection, for Endpoint, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
- m365solution-migratetomdatp
- m365solution-overview
ms.topic: conceptual
ms.custom: migrationguides
ms.date: 05/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: 013205a1b5b9db204f626a6fe6ab76ad07378558
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538005"
---
# <a name="make-the-switch-from-a-non-microsoft-endpoint-solution-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="c996e-105">Microsoft 以外のエンドポイント ソリューションから Microsoft Defender for Endpoint への切り替え</span><span class="sxs-lookup"><span data-stu-id="c996e-105">Make the switch from a non-Microsoft endpoint solution to Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="c996e-106">Microsoft 以外のエンドポイント保護ソリューションから Microsoft Defender for [Endpoint](microsoft-defender-endpoint.md) (Defender for Endpoint) に切り替える予定の場合は、適切な場所にいます。</span><span class="sxs-lookup"><span data-stu-id="c996e-106">If you are planning to switch from a non-Microsoft endpoint protection solution to [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) (Defender for Endpoint), you're in the right place.</span></span> <span data-ttu-id="c996e-107">この記事をガイドとして使用します。</span><span class="sxs-lookup"><span data-stu-id="c996e-107">Use this article as a guide.</span></span>

:::image type="content" source="images/nonms-mde-migration.png" alt-text="Defender for Endpoint への移行の概要":::

<span data-ttu-id="c996e-109">Defender for Endpoint に切り替える場合は、Microsoft 以外のソリューションをアクティブ モードで開始し、パッシブ モードで Defender for Endpoint を構成し、Defender for Endpoint にオンボードし、Defender for Endpoint をアクティブ モードに設定し、Microsoft 以外のソリューションを削除します。</span><span class="sxs-lookup"><span data-stu-id="c996e-109">When you make the switch to Defender for Endpoint, you begin with your non-Microsoft solution in active mode, configure Defender for Endpoint in passive mode, onboard to Defender for Endpoint, and then set Defender for Endpoint to active mode and remove the non-Microsoft solution.</span></span>

> [!TIP]
> - <span data-ttu-id="c996e-110">現在 McAfee Endpoint Security (McAfee) を使用している場合は、「Migrate from McAfee to [Defender for Endpoint」を参照してください](mcafee-to-microsoft-defender-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="c996e-110">If you're currently using McAfee Endpoint Security (McAfee), see [Migrate from McAfee to Defender for Endpoint](mcafee-to-microsoft-defender-migration.md).</span></span>
> - <span data-ttu-id="c996e-111">現在 Symantec Endpoint Protection (Symantec) を使用している場合は、「Migrate from Defender for Endpoint 」[を参照してください](symantec-to-microsoft-defender-endpoint-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="c996e-111">If you're currently using Symantec Endpoint Protection (Symantec), see [Migrate from Symantec to Defender for Endpoint](symantec-to-microsoft-defender-endpoint-migration.md).</span></span>

## <a name="the-migration-process"></a><span data-ttu-id="c996e-112">移行プロセス</span><span class="sxs-lookup"><span data-stu-id="c996e-112">The migration process</span></span>

<span data-ttu-id="c996e-113">Defender for Endpoint に切り替える場合は、次の表で説明するように、3 つのフェーズに分割できるプロセスに従います。</span><span class="sxs-lookup"><span data-stu-id="c996e-113">When you switch to Defender for Endpoint, you follow a process that can be divided into three phases, as described in the following table:</span></span>

![移行フェーズ - 準備、セットアップ、オンボード](images/phase-diagrams/migration-phases.png)

|<span data-ttu-id="c996e-115">段階</span><span class="sxs-lookup"><span data-stu-id="c996e-115">Phase</span></span> |<span data-ttu-id="c996e-116">説明</span><span class="sxs-lookup"><span data-stu-id="c996e-116">Description</span></span> |
|--|--|
|[<span data-ttu-id="c996e-117">移行の準備</span><span class="sxs-lookup"><span data-stu-id="c996e-117">Prepare for your migration</span></span>](switch-to-microsoft-defender-prepare.md) |<span data-ttu-id="c996e-118">準備 [フェーズ **では**、](switch-to-microsoft-defender-prepare.md)組織のデバイスを更新し、Defender for Endpoint を取得し、役割とアクセス許可を計画し、組織のデバイスへのアクセスを許可Microsoft Defender セキュリティ センター。</span><span class="sxs-lookup"><span data-stu-id="c996e-118">During [the **Prepare** phase](switch-to-microsoft-defender-prepare.md), you update your organization's devices, get Defender for Endpoint, plan your roles and permissions, and grant access to the Microsoft Defender Security Center.</span></span> <span data-ttu-id="c996e-119">また、デバイス プロキシとインターネット設定を構成して、組織のデバイスと Defender for Endpoint 間の通信を有効にします。</span><span class="sxs-lookup"><span data-stu-id="c996e-119">You also configure your device proxy and internet settings to enable communication between your organization's devices and Defender for Endpoint.</span></span> |
|[<span data-ttu-id="c996e-120">エンドポイントの Defender のセットアップ</span><span class="sxs-lookup"><span data-stu-id="c996e-120">Set up Defender for Endpoint</span></span>](switch-to-microsoft-defender-setup.md) |<span data-ttu-id="c996e-121">セットアップ [フェーズ **では、**](switch-to-microsoft-defender-setup.md)この設定を有効Microsoft Defender ウイルス対策パッシブ モードに設定します。</span><span class="sxs-lookup"><span data-stu-id="c996e-121">During [the **Setup** phase](switch-to-microsoft-defender-setup.md), you enable Microsoft Defender Antivirus and set it to passive mode.</span></span> <span data-ttu-id="c996e-122">また、既存のエンドポイント&ソリューションMicrosoft Defender ウイルス対策の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="c996e-122">You also configure settings & exclusions for Microsoft Defender Antivirus and your existing endpoint protection solution.</span></span> <span data-ttu-id="c996e-123">次に、デバイス グループ、コレクション、および組織単位を作成します。</span><span class="sxs-lookup"><span data-stu-id="c996e-123">Then, you create your device groups, collections, and organizational units.</span></span> <span data-ttu-id="c996e-124">最後に、マルウェア対策ポリシーとリアルタイム保護設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="c996e-124">Finally, you configure your antimalware policies and real-time protection settings.</span></span>|
|[<span data-ttu-id="c996e-125">Defender for Endpoint へのオンボード</span><span class="sxs-lookup"><span data-stu-id="c996e-125">Onboard to Defender for Endpoint</span></span>](switch-to-microsoft-defender-onboard.md) |<span data-ttu-id="c996e-126">オンボード [フェーズ **中**](switch-to-microsoft-defender-onboard.md)に、デバイスを Defender for Endpoint にオンボードし、Microsoft Defender ウイルス対策 がパッシブ モードで実行されているのを確認し、エンドポイントが Defender for Endpoint と通信しているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="c996e-126">During [the **Onboard** phase](switch-to-microsoft-defender-onboard.md), you onboard your devices to Defender for Endpoint, confirm that Microsoft Defender Antivirus is running in passive mode, and verify that your endpoints are communicating with Defender for Endpoint.</span></span> <span data-ttu-id="c996e-127">次に、既存のエンドポイント保護ソリューションをアンインストールし、Defender for Endpoint が正しく動作するようにします。</span><span class="sxs-lookup"><span data-stu-id="c996e-127">Then, you uninstall your existing endpoint protection solution and make sure that Defender for Endpoint working correctly.</span></span> |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="c996e-128">Microsoft Defender for Endpoint に含まれるもの</span><span class="sxs-lookup"><span data-stu-id="c996e-128">What's included in Microsoft Defender for Endpoint?</span></span>

<span data-ttu-id="c996e-129">この移行ガイドでは、Defender for [](microsoft-defender-antivirus-in-windows-10.md) Endpoint への移行[](overview-endpoint-detection-response.md)の開始点として、次世代の保護とエンドポイントの検出および応答機能に重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="c996e-129">In this migration guide, we focus on [next-generation protection](microsoft-defender-antivirus-in-windows-10.md) and [endpoint detection and response](overview-endpoint-detection-response.md) capabilities as a starting point for moving to Defender for Endpoint.</span></span> <span data-ttu-id="c996e-130">ただし、Defender for Endpoint には、ウイルス対策やエンドポイント保護以外の機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c996e-130">However, Defender for Endpoint includes much more than antivirus and endpoint protection.</span></span> <span data-ttu-id="c996e-131">Defender for Endpoint は、予防保護、侵害後の検出、自動調査、および対応のための統合プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="c996e-131">Defender for Endpoint is a unified platform for preventative protection, post-breach detection, automated investigation, and response.</span></span> <span data-ttu-id="c996e-132">次の表に、Defender for Endpoint の機能の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="c996e-132">The following table summarizes features and capabilities in Defender for Endpoint.</span></span> 

| <span data-ttu-id="c996e-133">機能/機能</span><span class="sxs-lookup"><span data-stu-id="c996e-133">Feature/Capability</span></span> | <span data-ttu-id="c996e-134">説明</span><span class="sxs-lookup"><span data-stu-id="c996e-134">Description</span></span> |
|---|---|
| [<span data-ttu-id="c996e-135">脅威と脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="c996e-135">Threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md) | <span data-ttu-id="c996e-136">脅威& 脆弱性の管理機能は、エンドポイント (デバイスなど) 全体の弱点を特定、評価、修復するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c996e-136">Threat & vulnerability management capabilities help identify, assess, and remediate weaknesses across your endpoints (such as devices).</span></span> |
| [<span data-ttu-id="c996e-137">攻撃面の減少</span><span class="sxs-lookup"><span data-stu-id="c996e-137">Attack surface reduction</span></span>](overview-attack-surface-reduction.md) | <span data-ttu-id="c996e-138">攻撃表面の縮小ルールは、組織のデバイスとアプリケーションをサイバー脅威や攻撃から保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c996e-138">Attack surface reduction rules help protect your organization's devices and applications from cyberthreats and attacks.</span></span> |
| [<span data-ttu-id="c996e-139">次世代の保護</span><span class="sxs-lookup"><span data-stu-id="c996e-139">Next-generation protection</span></span>](microsoft-defender-antivirus-in-windows-10.md) | <span data-ttu-id="c996e-140">次世代の保護には、脅威Microsoft Defender ウイルス対策マルウェアをブロックする機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c996e-140">Next-generation protection includes Microsoft Defender Antivirus to help block threats and malware.</span></span> |
| [<span data-ttu-id="c996e-141">エンドポイントでの検出と対応</span><span class="sxs-lookup"><span data-stu-id="c996e-141">Endpoint detection and response</span></span>](overview-endpoint-detection-response.md) | <span data-ttu-id="c996e-142">エンドポイントの検出および応答機能は、侵入の試みとアクティブな侵害を検出、調査、および対応します。</span><span class="sxs-lookup"><span data-stu-id="c996e-142">Endpoint detection and response capabilities detect, investigate, and respond to intrusion attempts and active breaches.</span></span>  |
| [<span data-ttu-id="c996e-143">高度な追求</span><span class="sxs-lookup"><span data-stu-id="c996e-143">Advanced hunting</span></span>](advanced-hunting-overview.md) | <span data-ttu-id="c996e-144">高度な検出機能により、セキュリティ運用チームは既知または潜在的な脅威のインジケーターとエンティティを検索できます。</span><span class="sxs-lookup"><span data-stu-id="c996e-144">Advanced hunting capabilities enable your security operations team to locate indicators and entities of known or potential threats.</span></span> |
| [<span data-ttu-id="c996e-145">動作ブロックと封じ込め</span><span class="sxs-lookup"><span data-stu-id="c996e-145">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md) | <span data-ttu-id="c996e-146">動作のブロックと格納機能は、脅威の実行が開始された場合でも、その動作に基づいて脅威を特定し、停止し、ツリーを処理するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c996e-146">Behavioral blocking and containment capabilities help identify and stop threats, based on their behaviors and process trees even when the threat has started execution.</span></span> |
| [<span data-ttu-id="c996e-147">調査と修復の自動化</span><span class="sxs-lookup"><span data-stu-id="c996e-147">Automated investigation and remediation</span></span>](automated-investigations.md) | <span data-ttu-id="c996e-148">自動調査および応答機能は、アラートを調べ、侵害を解決するために直ちに修復アクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="c996e-148">Automated investigation and response capabilities examine alerts and take immediate remediation action to resolve breaches.</span></span> |
| <span data-ttu-id="c996e-149">[脅威の検出サービス](microsoft-threat-experts.md)(Microsoft 脅威エキスパート)</span><span class="sxs-lookup"><span data-stu-id="c996e-149">[Threat hunting service](microsoft-threat-experts.md) (Microsoft Threat Experts)</span></span> | <span data-ttu-id="c996e-150">脅威検出サービスは、セキュリティ運用チームに専門家レベルの監視と分析を提供し、重要な脅威を見逃しなくするために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c996e-150">Threat hunting services provide security operations teams with expert level monitoring and analysis, and to help ensure that critical threats aren't missed.</span></span> |

<span data-ttu-id="c996e-151">**詳細については、次の情報を参照してください。「Defender [for Endpoint」を参照してください](microsoft-defender-endpoint.md)。**</span><span class="sxs-lookup"><span data-stu-id="c996e-151">**Want to learn more? See [Defender for Endpoint](microsoft-defender-endpoint.md).**</span></span>

## <a name="next-step"></a><span data-ttu-id="c996e-152">次の手順</span><span class="sxs-lookup"><span data-stu-id="c996e-152">Next step</span></span>

- <span data-ttu-id="c996e-153">移行の [準備に進みます](switch-to-microsoft-defender-prepare.md)。</span><span class="sxs-lookup"><span data-stu-id="c996e-153">Proceed to [Prepare for your migration](switch-to-microsoft-defender-prepare.md).</span></span>
