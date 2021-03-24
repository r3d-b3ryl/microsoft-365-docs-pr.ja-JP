---
title: Symantec から Microsoft Defender for Endpoint への移行
description: Symantec から Microsoft Defender for Endpoint への切り替え方法の概要を確認する
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
- m365solution-symantecmigrate
- m365solution-overview
ms.topic: conceptual
ms.date: 03/03/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 6cab09547501da9b533c49b7096389e13dbf1f87
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060838"
---
# <a name="migrate-from-symantec-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="c04bc-104">Symantec から Microsoft Defender for Endpoint への移行</span><span class="sxs-lookup"><span data-stu-id="c04bc-104">Migrate from Symantec to Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="c04bc-105">シマンテック エンドポイント保護 (Symantec) から [Microsoft Defender for](https://docs.microsoft.com/windows/security/threat-protection) Endpoint (Microsoft Defender for Endpoint) に切り替える予定の場合は、適切な場所にいます。</span><span class="sxs-lookup"><span data-stu-id="c04bc-105">If you are planning to switch from Symantec Endpoint Protection (Symantec) to [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft Defender for Endpoint), you're in the right place.</span></span> <span data-ttu-id="c04bc-106">この記事をガイドとして使用します。</span><span class="sxs-lookup"><span data-stu-id="c04bc-106">Use this article as a guide.</span></span>

<span data-ttu-id="c04bc-107">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="c04bc-107">**Applies to:**</span></span>
- [<span data-ttu-id="c04bc-108">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c04bc-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="c04bc-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c04bc-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

:::image type="content" source="images/symantec-mde-migration.png" alt-text="Symantec から Defender for Endpoint への移行の概要":::

<span data-ttu-id="c04bc-111">シマンテックから Defender for Endpoint に切り替える場合は、アクティブ モードのシマンテック ソリューションから始まり、パッシブ モードで Defender for Endpoint を構成し、Defender for Endpoint にオンボードし、Defender for Endpoint をアクティブ モードに設定し、シマンテックを削除します。</span><span class="sxs-lookup"><span data-stu-id="c04bc-111">When you make the switch from Symantec to Defender for Endpoint, you begin with your Symantec solution in active mode, configure Defender for Endpoint in passive mode, onboard to Defender for Endpoint, and then set Defender for Endpoint to active mode and remove Symantec.</span></span>

## <a name="the-migration-process"></a><span data-ttu-id="c04bc-112">移行プロセス</span><span class="sxs-lookup"><span data-stu-id="c04bc-112">The migration process</span></span>

<span data-ttu-id="c04bc-113">シマンテックから Microsoft Defender for Endpoint に切り替える場合は、次の表で説明するように、3 つのフェーズに分け可能なプロセスに従います。</span><span class="sxs-lookup"><span data-stu-id="c04bc-113">When you switch from Symantec to Microsoft Defender for Endpoint, you follow a process that can be divided into three phases, as described in the following table:</span></span>

![移行フェーズ - 準備、セットアップ、オンボード](images/phase-diagrams/migration-phases.png)

|<span data-ttu-id="c04bc-115">段階</span><span class="sxs-lookup"><span data-stu-id="c04bc-115">Phase</span></span> |<span data-ttu-id="c04bc-116">説明</span><span class="sxs-lookup"><span data-stu-id="c04bc-116">Description</span></span> |
|--|--|
|[<span data-ttu-id="c04bc-117">移行の準備</span><span class="sxs-lookup"><span data-stu-id="c04bc-117">Prepare for your migration</span></span>](symantec-to-microsoft-defender-atp-prepare.md) |<span data-ttu-id="c04bc-118">準備フェーズ **では** 、Microsoft Defender for Endpoint を取得し、役割とアクセス許可を計画し、Microsoft Defender セキュリティ センターへのアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="c04bc-118">During the **Prepare** phase, you get Microsoft Defender for Endpoint, plan your roles and permissions, and grant access to the Microsoft Defender Security Center.</span></span> <span data-ttu-id="c04bc-119">また、デバイス プロキシとインターネット設定を構成して、組織のデバイスと Microsoft Defender for Endpoint 間の通信を有効にします。</span><span class="sxs-lookup"><span data-stu-id="c04bc-119">You also configure your device proxy and internet settings to enable communication between your organization's devices and Microsoft Defender for Endpoint.</span></span> |
|[<span data-ttu-id="c04bc-120">エンドポイント用 Microsoft Defender のセットアップ</span><span class="sxs-lookup"><span data-stu-id="c04bc-120">Set up Microsoft Defender for Endpoint</span></span>](symantec-to-microsoft-defender-atp-setup.md) |<span data-ttu-id="c04bc-121">セットアップ フェーズ **では** 、Microsoft Defender Antivirus、Microsoft Defender for Endpoint、および Symantec Endpoint Protection の設定と除外を構成します。</span><span class="sxs-lookup"><span data-stu-id="c04bc-121">During the **Setup** phase, you configure settings and exclusions for Microsoft Defender Antivirus, Microsoft Defender for Endpoint, and Symantec Endpoint Protection.</span></span> <span data-ttu-id="c04bc-122">デバイス グループ、コレクション、および組織単位も作成します。</span><span class="sxs-lookup"><span data-stu-id="c04bc-122">You also create device groups, collections, and organizational units.</span></span> <span data-ttu-id="c04bc-123">最後に、マルウェア対策ポリシーとリアルタイム保護設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="c04bc-123">Finally, you configure your antimalware policies and real-time protection settings.</span></span>|
|[<span data-ttu-id="c04bc-124">エンドポイント用 Microsoft Defender にオンボード</span><span class="sxs-lookup"><span data-stu-id="c04bc-124">Onboard to Microsoft Defender for Endpoint</span></span>](symantec-to-microsoft-defender-atp-onboard.md) |<span data-ttu-id="c04bc-125">オンボード フェーズ **中に** 、デバイスを Microsoft Defender for Endpoint にオンボードし、それらのデバイスが Microsoft Defender for Endpoint と通信しているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="c04bc-125">During the **Onboard** phase, you onboard your devices to Microsoft Defender for Endpoint and verify that those devices are communicating with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="c04bc-126">最後に、Symantec をアンインストールし、Microsoft Defender for Endpoint を通じた保護がアクティブ モードに設定されています。</span><span class="sxs-lookup"><span data-stu-id="c04bc-126">Last, you uninstall Symantec and make sure protection through Microsoft Defender for Endpoint is in active mode.</span></span> |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="c04bc-127">Microsoft Defender for Endpoint に含まれるもの</span><span class="sxs-lookup"><span data-stu-id="c04bc-127">What's included in Microsoft Defender for Endpoint?</span></span>

<span data-ttu-id="c04bc-128">この移行ガイドでは、Microsoft Defender [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) for Endpoint[](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)への移行の開始点として、次世代の保護とエンドポイントの検出および応答機能に重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="c04bc-128">In this migration guide, we focus on [next-generation protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) and [endpoint detection and response](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) capabilities as a starting point for moving to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="c04bc-129">ただし、Microsoft Defender for Endpoint には、ウイルス対策やエンドポイント保護以外の機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c04bc-129">However, Microsoft Defender for Endpoint includes much more than antivirus and endpoint protection.</span></span> <span data-ttu-id="c04bc-130">Microsoft Defender for Endpoint は、予防的な保護、侵害後の検出、自動調査、対応のための統一されたプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="c04bc-130">Microsoft Defender for Endpoint is a unified platform for preventative protection, post-breach detection, automated investigation, and response.</span></span> <span data-ttu-id="c04bc-131">次の表に、Microsoft Defender for Endpoint の機能の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="c04bc-131">The following table summarizes features and capabilities in Microsoft Defender for Endpoint.</span></span> 

| <span data-ttu-id="c04bc-132">機能/機能</span><span class="sxs-lookup"><span data-stu-id="c04bc-132">Feature/Capability</span></span> | <span data-ttu-id="c04bc-133">説明</span><span class="sxs-lookup"><span data-stu-id="c04bc-133">Description</span></span> |
|---|---|
| [<span data-ttu-id="c04bc-134">脅威&の管理</span><span class="sxs-lookup"><span data-stu-id="c04bc-134">Threat & vulnerability management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) | <span data-ttu-id="c04bc-135">脅威&管理機能は、エンドポイント (デバイスなど) 全体の弱点を特定、評価、修復するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c04bc-135">Threat & vulnerability management capabilities help identify, assess, and remediate weaknesses across your endpoints (such as devices).</span></span> |
| [<span data-ttu-id="c04bc-136">攻撃面の縮小</span><span class="sxs-lookup"><span data-stu-id="c04bc-136">Attack surface reduction</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-attack-surface-reduction) | <span data-ttu-id="c04bc-137">攻撃表面の縮小ルールは、組織のデバイスとアプリケーションをサイバー脅威や攻撃から保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c04bc-137">Attack surface reduction rules help protect your organization's devices and applications from cyberthreats and attacks.</span></span> |
| [<span data-ttu-id="c04bc-138">次世代の保護</span><span class="sxs-lookup"><span data-stu-id="c04bc-138">Next-generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) | <span data-ttu-id="c04bc-139">次世代の保護には、脅威やマルウェアのブロックに役立つ Microsoft Defender ウイルス対策が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c04bc-139">Next-generation protection includes Microsoft Defender Antivirus to help block threats and malware.</span></span> |
| [<span data-ttu-id="c04bc-140">エンドポイントの検出および応答</span><span class="sxs-lookup"><span data-stu-id="c04bc-140">Endpoint detection and response</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) | <span data-ttu-id="c04bc-141">エンドポイントの検出および応答機能は、侵入の試みとアクティブな侵害を検出、調査、および対応します。</span><span class="sxs-lookup"><span data-stu-id="c04bc-141">Endpoint detection and response capabilities detect, investigate, and respond to intrusion attempts and active breaches.</span></span>  |
| [<span data-ttu-id="c04bc-142">高度な検出</span><span class="sxs-lookup"><span data-stu-id="c04bc-142">Advanced hunting</span></span>](advanced-hunting-overview.md) | <span data-ttu-id="c04bc-143">高度な検出機能により、セキュリティ運用チームは既知または潜在的な脅威のインジケーターとエンティティを検索できます。</span><span class="sxs-lookup"><span data-stu-id="c04bc-143">Advanced hunting capabilities enable your security operations team to locate indicators and entities of known or potential threats.</span></span> |
| [<span data-ttu-id="c04bc-144">動作のブロックと格納</span><span class="sxs-lookup"><span data-stu-id="c04bc-144">Behavioral blocking and containment</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) | <span data-ttu-id="c04bc-145">動作のブロックと格納機能は、脅威の実行が開始された場合でも、その動作に基づいて脅威を特定し、停止し、ツリーを処理するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c04bc-145">Behavioral blocking and containment capabilities help identify and stop threats, based on their behaviors and process trees even when the threat has started execution.</span></span> |
| [<span data-ttu-id="c04bc-146">調査と修復の自動化</span><span class="sxs-lookup"><span data-stu-id="c04bc-146">Automated investigation and remediation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations) | <span data-ttu-id="c04bc-147">自動調査および応答機能は、アラートを調べ、侵害を解決するために直ちに修復アクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="c04bc-147">Automated investigation and response capabilities examine alerts and take immediate remediation action to resolve breaches.</span></span> |
| <span data-ttu-id="c04bc-148">[脅威の検出サービス](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-threat-experts) (Microsoft Threat Experts)</span><span class="sxs-lookup"><span data-stu-id="c04bc-148">[Threat hunting service](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-threat-experts) (Microsoft Threat Experts)</span></span> | <span data-ttu-id="c04bc-149">脅威検出サービスは、セキュリティ運用チームに専門家レベルの監視と分析を提供し、重要な脅威を見逃しなくするために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c04bc-149">Threat hunting services provide security operations teams with expert level monitoring and analysis, and to help ensure that critical threats aren't missed.</span></span> |

<span data-ttu-id="c04bc-150">**詳細については、次の情報を参照してください。「Microsoft [Defender for Endpoint」を参照してください](https://docs.microsoft.com/windows/security/threat-protection)。**</span><span class="sxs-lookup"><span data-stu-id="c04bc-150">**Want to learn more? See [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection).**</span></span>

## <a name="next-step"></a><span data-ttu-id="c04bc-151">次の手順</span><span class="sxs-lookup"><span data-stu-id="c04bc-151">Next step</span></span>

- <span data-ttu-id="c04bc-152">移行の [準備に進みます](symantec-to-microsoft-defender-atp-prepare.md)。</span><span class="sxs-lookup"><span data-stu-id="c04bc-152">Proceed to [Prepare for your migration](symantec-to-microsoft-defender-atp-prepare.md).</span></span>
