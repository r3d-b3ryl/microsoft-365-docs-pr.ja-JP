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
ms.date: 05/10/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: 0a8e1f11cdb9d7363e6b47d1e671c546e5eac9b4
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327504"
---
# <a name="make-the-switch-from-a-non-microsoft-endpoint-solution-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="92ac1-105">Microsoft 以外のエンドポイント ソリューションから Microsoft Defender for Endpoint への切り替え</span><span class="sxs-lookup"><span data-stu-id="92ac1-105">Make the switch from a non-Microsoft endpoint solution to Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="92ac1-106">Microsoft 以外のエンドポイント保護ソリューションから Microsoft Defender for [Endpoint](microsoft-defender-endpoint.md) (Defender for Endpoint) に切り替える予定の場合は、適切な場所にいます。</span><span class="sxs-lookup"><span data-stu-id="92ac1-106">If you are planning to switch from a non-Microsoft endpoint protection solution to [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) (Defender for Endpoint), you're in the right place.</span></span> <span data-ttu-id="92ac1-107">この記事をガイドとして使用します。</span><span class="sxs-lookup"><span data-stu-id="92ac1-107">Use this article as a guide.</span></span>

:::image type="content" source="images/nonms-mde-migration.png" alt-text="Defender for Endpoint への移行の概要":::

<span data-ttu-id="92ac1-109">Defender for Endpoint に切り替える場合は、Microsoft 以外のソリューションをアクティブ モードで開始し、パッシブ モードで Defender for Endpoint を構成し、Defender for Endpoint にオンボードし、Defender for Endpoint をアクティブ モードに設定し、Microsoft 以外のソリューションを削除します。</span><span class="sxs-lookup"><span data-stu-id="92ac1-109">When you make the switch to Defender for Endpoint, you begin with your non-Microsoft solution in active mode, configure Defender for Endpoint in passive mode, onboard to Defender for Endpoint, and then set Defender for Endpoint to active mode and remove the non-Microsoft solution.</span></span>

> [!TIP]
> - <span data-ttu-id="92ac1-110">現在 McAfee Endpoint Security (McAfee) を使用している場合は、「Migrate from McAfee to [Microsoft Defender for Endpoint」を参照してください](mcafee-to-microsoft-defender-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="92ac1-110">If you're currently using McAfee Endpoint Security (McAfee), see [Migrate from McAfee to Microsoft Defender for Endpoint](mcafee-to-microsoft-defender-migration.md).</span></span>
> - <span data-ttu-id="92ac1-111">現在 Symantec Endpoint Protection (Symantec) を使用している場合は、「Symantec から Microsoft Defender for Endpoint への移行」[を参照してください](symantec-to-microsoft-defender-endpoint-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="92ac1-111">If you're currently using Symantec Endpoint Protection (Symantec), see [Migrate from Symantec to Microsoft Defender for Endpoint](symantec-to-microsoft-defender-endpoint-migration.md).</span></span>

## <a name="the-migration-process"></a><span data-ttu-id="92ac1-112">移行プロセス</span><span class="sxs-lookup"><span data-stu-id="92ac1-112">The migration process</span></span>

<span data-ttu-id="92ac1-113">Microsoft Defender for Endpoint に切り替える場合は、次の表で説明するように、3 つのフェーズに分割できるプロセスに従います。</span><span class="sxs-lookup"><span data-stu-id="92ac1-113">When you switch to Microsoft Defender for Endpoint, you follow a process that can be divided into three phases, as described in the following table:</span></span>

![移行フェーズ - 準備、セットアップ、オンボード](images/phase-diagrams/migration-phases.png)

|<span data-ttu-id="92ac1-115">段階</span><span class="sxs-lookup"><span data-stu-id="92ac1-115">Phase</span></span> |<span data-ttu-id="92ac1-116">説明</span><span class="sxs-lookup"><span data-stu-id="92ac1-116">Description</span></span> |
|--|--|
|[<span data-ttu-id="92ac1-117">移行の準備</span><span class="sxs-lookup"><span data-stu-id="92ac1-117">Prepare for your migration</span></span>](switch-to-microsoft-defender-prepare.md) |<span data-ttu-id="92ac1-118">準備 [フェーズ **では**、](switch-to-microsoft-defender-prepare.md)組織のデバイスを更新し、Microsoft Defender for Endpoint を取得し、役割とアクセス許可を計画し、ユーザーにアクセス権を付与Microsoft Defender セキュリティ センター。</span><span class="sxs-lookup"><span data-stu-id="92ac1-118">During [the **Prepare** phase](switch-to-microsoft-defender-prepare.md), you update your organization's devices, get Microsoft Defender for Endpoint, plan your roles and permissions, and grant access to the Microsoft Defender Security Center.</span></span> <span data-ttu-id="92ac1-119">また、デバイス プロキシとインターネット設定を構成して、組織のデバイスと Microsoft Defender for Endpoint 間の通信を有効にします。</span><span class="sxs-lookup"><span data-stu-id="92ac1-119">You also configure your device proxy and internet settings to enable communication between your organization's devices and Microsoft Defender for Endpoint.</span></span> |
|[<span data-ttu-id="92ac1-120">エンドポイント用 Microsoft Defender のセットアップ</span><span class="sxs-lookup"><span data-stu-id="92ac1-120">Set up Microsoft Defender for Endpoint</span></span>](switch-to-microsoft-defender-setup.md) |<span data-ttu-id="92ac1-121">セットアップ [フェーズ **の間**](switch-to-microsoft-defender-setup.md)に、Microsoft Defender ウイルス対策を有効にし、パッシブ モードに設定します。</span><span class="sxs-lookup"><span data-stu-id="92ac1-121">During [the **Setup** phase](switch-to-microsoft-defender-setup.md), you enable Microsoft Defender Antivirus and make sure it's in passive mode.</span></span> <span data-ttu-id="92ac1-122">また、既存のエンドポイント&ソリューションMicrosoft Defender ウイルス対策の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="92ac1-122">You also configure settings & exclusions for Microsoft Defender Antivirus and your existing endpoint protection solution.</span></span> <span data-ttu-id="92ac1-123">次に、デバイス グループ、コレクション、および組織単位を作成します。</span><span class="sxs-lookup"><span data-stu-id="92ac1-123">Then, you create your device groups, collections, and organizational units.</span></span> <span data-ttu-id="92ac1-124">最後に、マルウェア対策ポリシーとリアルタイム保護設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="92ac1-124">Finally, you configure your antimalware policies and real-time protection settings.</span></span>|
|[<span data-ttu-id="92ac1-125">エンドポイント用 Microsoft Defender にオンボード</span><span class="sxs-lookup"><span data-stu-id="92ac1-125">Onboard to Microsoft Defender for Endpoint</span></span>](switch-to-microsoft-defender-onboard.md) |<span data-ttu-id="92ac1-126">オンボード [フェーズ **中に** 、](switch-to-microsoft-defender-onboard.md)デバイスを Microsoft Defender for Endpoint にオンボードし、それらのデバイスが Microsoft Defender for Endpoint と通信しているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="92ac1-126">During [the **Onboard** phase](switch-to-microsoft-defender-onboard.md), you onboard your devices to Microsoft Defender for Endpoint and verify that those devices are communicating with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="92ac1-127">最後に、既存のエンドポイント保護ソリューションをアンインストールし、Microsoft Defender for Endpoint を通Microsoft Defender ウイルス対策 &保護がアクティブ モードに設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="92ac1-127">Last, you uninstall your existing endpoint protection solution and make sure that protection through Microsoft Defender Antivirus & Microsoft Defender for Endpoint is in active mode.</span></span> |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="92ac1-128">Microsoft Defender for Endpoint に含まれるもの</span><span class="sxs-lookup"><span data-stu-id="92ac1-128">What's included in Microsoft Defender for Endpoint?</span></span>

<span data-ttu-id="92ac1-129">この移行ガイドでは、Microsoft Defender [](microsoft-defender-antivirus-in-windows-10.md) for Endpoint[](overview-endpoint-detection-response.md)への移行の開始点として、次世代の保護とエンドポイントの検出および応答機能に重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="92ac1-129">In this migration guide, we focus on [next-generation protection](microsoft-defender-antivirus-in-windows-10.md) and [endpoint detection and response](overview-endpoint-detection-response.md) capabilities as a starting point for moving to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="92ac1-130">ただし、Microsoft Defender for Endpoint には、ウイルス対策やエンドポイント保護以外の機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="92ac1-130">However, Microsoft Defender for Endpoint includes much more than antivirus and endpoint protection.</span></span> <span data-ttu-id="92ac1-131">Microsoft Defender for Endpoint は、予防的な保護、侵害後の検出、自動調査、対応のための統一されたプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="92ac1-131">Microsoft Defender for Endpoint is a unified platform for preventative protection, post-breach detection, automated investigation, and response.</span></span> <span data-ttu-id="92ac1-132">次の表に、Microsoft Defender for Endpoint の機能の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="92ac1-132">The following table summarizes features and capabilities in Microsoft Defender for Endpoint.</span></span> 

| <span data-ttu-id="92ac1-133">機能/機能</span><span class="sxs-lookup"><span data-stu-id="92ac1-133">Feature/Capability</span></span> | <span data-ttu-id="92ac1-134">説明</span><span class="sxs-lookup"><span data-stu-id="92ac1-134">Description</span></span> |
|---|---|
| [<span data-ttu-id="92ac1-135">脅威と脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="92ac1-135">Threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md) | <span data-ttu-id="92ac1-136">脅威& 脆弱性の管理機能は、エンドポイント (デバイスなど) 全体の弱点を特定、評価、修復するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="92ac1-136">Threat & vulnerability management capabilities help identify, assess, and remediate weaknesses across your endpoints (such as devices).</span></span> |
| [<span data-ttu-id="92ac1-137">攻撃面の減少</span><span class="sxs-lookup"><span data-stu-id="92ac1-137">Attack surface reduction</span></span>](overview-attack-surface-reduction.md) | <span data-ttu-id="92ac1-138">攻撃表面の縮小ルールは、組織のデバイスとアプリケーションをサイバー脅威や攻撃から保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="92ac1-138">Attack surface reduction rules help protect your organization's devices and applications from cyberthreats and attacks.</span></span> |
| [<span data-ttu-id="92ac1-139">次世代の保護</span><span class="sxs-lookup"><span data-stu-id="92ac1-139">Next-generation protection</span></span>](microsoft-defender-antivirus-in-windows-10.md) | <span data-ttu-id="92ac1-140">次世代の保護には、脅威Microsoft Defender ウイルス対策マルウェアをブロックする機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="92ac1-140">Next-generation protection includes Microsoft Defender Antivirus to help block threats and malware.</span></span> |
| [<span data-ttu-id="92ac1-141">エンドポイントでの検出と対応</span><span class="sxs-lookup"><span data-stu-id="92ac1-141">Endpoint detection and response</span></span>](overview-endpoint-detection-response.md) | <span data-ttu-id="92ac1-142">エンドポイントの検出および応答機能は、侵入の試みとアクティブな侵害を検出、調査、および対応します。</span><span class="sxs-lookup"><span data-stu-id="92ac1-142">Endpoint detection and response capabilities detect, investigate, and respond to intrusion attempts and active breaches.</span></span>  |
| [<span data-ttu-id="92ac1-143">高度な追求</span><span class="sxs-lookup"><span data-stu-id="92ac1-143">Advanced hunting</span></span>](advanced-hunting-overview.md) | <span data-ttu-id="92ac1-144">高度な検出機能により、セキュリティ運用チームは既知または潜在的な脅威のインジケーターとエンティティを検索できます。</span><span class="sxs-lookup"><span data-stu-id="92ac1-144">Advanced hunting capabilities enable your security operations team to locate indicators and entities of known or potential threats.</span></span> |
| [<span data-ttu-id="92ac1-145">動作ブロックと封じ込め</span><span class="sxs-lookup"><span data-stu-id="92ac1-145">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md) | <span data-ttu-id="92ac1-146">動作のブロックと格納機能は、脅威の実行が開始された場合でも、その動作に基づいて脅威を特定し、停止し、ツリーを処理するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="92ac1-146">Behavioral blocking and containment capabilities help identify and stop threats, based on their behaviors and process trees even when the threat has started execution.</span></span> |
| [<span data-ttu-id="92ac1-147">調査と修復の自動化</span><span class="sxs-lookup"><span data-stu-id="92ac1-147">Automated investigation and remediation</span></span>](automated-investigations.md) | <span data-ttu-id="92ac1-148">自動調査および応答機能は、アラートを調べ、侵害を解決するために直ちに修復アクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="92ac1-148">Automated investigation and response capabilities examine alerts and take immediate remediation action to resolve breaches.</span></span> |
| <span data-ttu-id="92ac1-149">[脅威の検出サービス](microsoft-threat-experts.md)(Microsoft 脅威エキスパート)</span><span class="sxs-lookup"><span data-stu-id="92ac1-149">[Threat hunting service](microsoft-threat-experts.md) (Microsoft Threat Experts)</span></span> | <span data-ttu-id="92ac1-150">脅威検出サービスは、セキュリティ運用チームに専門家レベルの監視と分析を提供し、重要な脅威を見逃しなくするために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="92ac1-150">Threat hunting services provide security operations teams with expert level monitoring and analysis, and to help ensure that critical threats aren't missed.</span></span> |

<span data-ttu-id="92ac1-151">**詳細については、次の情報を参照してください。「Microsoft [Defender for Endpoint」を参照してください](microsoft-defender-endpoint.md)。**</span><span class="sxs-lookup"><span data-stu-id="92ac1-151">**Want to learn more? See [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md).**</span></span>

## <a name="next-step"></a><span data-ttu-id="92ac1-152">次の手順</span><span class="sxs-lookup"><span data-stu-id="92ac1-152">Next step</span></span>

- <span data-ttu-id="92ac1-153">移行の [準備に進みます](switch-to-microsoft-defender-prepare.md)。</span><span class="sxs-lookup"><span data-stu-id="92ac1-153">Proceed to [Prepare for your migration](switch-to-microsoft-defender-prepare.md).</span></span>
