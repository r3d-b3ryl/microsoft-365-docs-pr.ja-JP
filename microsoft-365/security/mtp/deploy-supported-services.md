---
title: Microsoft 365 Defender でサポートされているサービスを展開する
description: Microsoft 365 Defender によって統合できる Microsoft セキュリティ サービス、ライセンス要件、展開手順について説明します。
keywords: 展開, ライセンス, サポートされているサービス, プロビジョニング, 構成 Microsoft Threat Protection, M365, ライセンスの利用資格, Microsoft Defender ATP, MDATP, Office 365 ATP, Azure ATP, Microsoft Cloud App Security, MCAS, Advanced Threat Protection, E5, A5, EMS
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 5af58a1c6850619ca08960997a30fe4a81158446
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928964"
---
# <a name="deploy-supported-services"></a><span data-ttu-id="c3462-104">サポートされているサービスを展開する</span><span class="sxs-lookup"><span data-stu-id="c3462-104">Deploy supported services</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c3462-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="c3462-105">**Applies to:**</span></span>
- <span data-ttu-id="c3462-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c3462-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="c3462-107">[Microsoft 365 Defender](microsoft-threat-protection.md) は、さまざまな Microsoft セキュリティ サービスを統合して、高度な攻撃に対する一元的な検出、防止、調査機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="c3462-107">[Microsoft 365 Defender](microsoft-threat-protection.md) integrates various Microsoft security services to provide centralized detection, prevention, and investigation capabilities against sophisticated attacks.</span></span> <span data-ttu-id="c3462-108">この記事では、サポートされるサービス、ライセンス要件、1 つ以上のサービスの展開に関連する利点と制限事項、およびそれらを個別に完全に展開する方法へのリンクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c3462-108">This article describes the supported services, their licensing requirements, the advantages and limitations associated with deploying one or more services, and links to how you can fully deploy them individually.</span></span>

## <a name="supported-services"></a><span data-ttu-id="c3462-109">サポートされているサービス</span><span class="sxs-lookup"><span data-stu-id="c3462-109">Supported services</span></span>
<span data-ttu-id="c3462-110">Microsoft 365 E5、E5 Security、A5、または A5 Security ライセンス、またはライセンスの有効な組み合わせにより、次のサポートされているサービスにアクセスできます。また、Microsoft 365 セキュリティ センターで Microsoft 365 Defender を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="c3462-110">A Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses provides access to the following supported services and entitles you to use Microsoft 365 Defender in Microsoft 365 security center.</span></span> [<span data-ttu-id="c3462-111">ライセンス要件を確認する</span><span class="sxs-lookup"><span data-stu-id="c3462-111">See licensing requirements</span></span>](prerequisites.md#licensing-requirements)

| <span data-ttu-id="c3462-112">サポートされているサービス</span><span class="sxs-lookup"><span data-stu-id="c3462-112">Supported service</span></span> | <span data-ttu-id="c3462-113">説明</span><span class="sxs-lookup"><span data-stu-id="c3462-113">Description</span></span> |
| ------ | ------ |
| <span data-ttu-id="c3462-114">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c3462-114">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="c3462-115">強力な動作センサー、クラウド分析、脅威インテリジェンスを中心に構築されたエンドポイント保護スイート</span><span class="sxs-lookup"><span data-stu-id="c3462-115">Endpoint protection suite built around powerful behavioral sensors, cloud analytics, and threat intelligence</span></span> |
|<span data-ttu-id="c3462-116">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="c3462-116">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="c3462-117">Office 365 のアプリとデータの高度な保護 (メールなどのコラボレーション ツールを含む)</span><span class="sxs-lookup"><span data-stu-id="c3462-117">Advanced protection for your apps and data in Office 365, including email and other collaboration tools</span></span> |
| <span data-ttu-id="c3462-118">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="c3462-118">Microsoft Defender for Identity</span></span> | <span data-ttu-id="c3462-119">関連付けされた Active Directory シグナルを使用して、高度な脅威、侵害された ID、悪意のあるインサイダーから防御する</span><span class="sxs-lookup"><span data-stu-id="c3462-119">Defend against advanced threats, compromised identities, and malicious insiders using correlated Active Directory signals</span></span> |
| <span data-ttu-id="c3462-120">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c3462-120">Microsoft Cloud App Security</span></span> | <span data-ttu-id="c3462-121">Microsoft およびサード パーティのクラウド サービス全体でサイバー脅威を特定し、対処する</span><span class="sxs-lookup"><span data-stu-id="c3462-121">Identify and combat cyberthreats across your Microsoft and third-party cloud services</span></span> |

## <a name="deployed-services-and-functionality"></a><span data-ttu-id="c3462-122">展開されたサービスと機能</span><span class="sxs-lookup"><span data-stu-id="c3462-122">Deployed services and functionality</span></span>
<span data-ttu-id="c3462-123">Microsoft 365 Defender は、より多くのサポートされるサービスを展開するに当たって、可視性、相関関係、修復を向上します。</span><span class="sxs-lookup"><span data-stu-id="c3462-123">Microsoft 365 Defender provides better visibility, correlation, and remediation as you deploy more supported services.</span></span>

### <a name="benefits-of-full-deployment"></a><span data-ttu-id="c3462-124">完全展開の利点</span><span class="sxs-lookup"><span data-stu-id="c3462-124">Benefits of full deployment</span></span>
<span data-ttu-id="c3462-125">Microsoft 365 Defender の完全なメリットを得る場合は、サポートされているサービスを展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c3462-125">To get the complete benefits of Microsoft 365 Defender, we recommend deploying all supported services.</span></span> <span data-ttu-id="c3462-126">完全展開の主な利点を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c3462-126">Here are some of the key benefits of full deployment:</span></span>
- <span data-ttu-id="c3462-127">インシデントは、利用可能なすべてのセンサーとサービス固有の分析機能からのアラートとイベント シグナルに基づいて識別され、関連付けされます。</span><span class="sxs-lookup"><span data-stu-id="c3462-127">Incidents are identified and correlated based on alerts and event signals from all available sensors and service-specific analysis capabilities</span></span>
- <span data-ttu-id="c3462-128">自動調査と修復 (AIR) プレイブックは、デバイス、メールボックス、ユーザー アカウントなど、さまざまなエンティティの種類に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c3462-128">Automated investigation and remediation (AIR) playbooks apply across various entity types, including devices, mailboxes, and user accounts</span></span>
- <span data-ttu-id="c3462-129">より包括的な高度な検索スキーマを使用して、デバイス、メールボックス、その他のエンティティからのイベント データとエンティティ データを照会できます。</span><span class="sxs-lookup"><span data-stu-id="c3462-129">A more comprehensive advanced hunting schema can be queried for event and entity data from devices, mailboxes, and other entities</span></span>

### <a name="limited-deployment-scenarios"></a><span data-ttu-id="c3462-130">限定的な展開シナリオ</span><span class="sxs-lookup"><span data-stu-id="c3462-130">Limited deployment scenarios</span></span>
<span data-ttu-id="c3462-131">展開するサポートされている各サービスは、豊富な生信号と関連情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c3462-131">Each supported service that you deploy provides an extremely rich set of raw signals as well as correlated information.</span></span> <span data-ttu-id="c3462-132">限定的な展開によって Microsoft 365 Defender の機能が無効にされるのとは限らないが、エンドポイント、アプリ、データ、ID 全体を包括的に可視化する機能は影響を受ける。</span><span class="sxs-lookup"><span data-stu-id="c3462-132">While limited deployment doesn’t cause Microsoft 365 Defender functionality to turn off, its ability to provide comprehensive visibility across your endpoints, apps, data, and identities is affected.</span></span> <span data-ttu-id="c3462-133">同時に、修復機能は、展開したサービスによって管理できるエンティティにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="c3462-133">At the same time, any remediation capabilities only apply to entities that can be managed by the services you’ve deployed.</span></span>

<span data-ttu-id="c3462-134">次の表は、サポートされている各サービスが追加のデータを提供する方法、データを関連付けて追加の洞察を得る機会、および改善と対応の機能を示しています。</span><span class="sxs-lookup"><span data-stu-id="c3462-134">The table below lists how each supported service provides additional data, opportunities to obtain additional insight by correlating the data, and better remediation and response capabilities.</span></span>

| <span data-ttu-id="c3462-135">サービス</span><span class="sxs-lookup"><span data-stu-id="c3462-135">Service</span></span> | <span data-ttu-id="c3462-136">データ (シグナル&情報)</span><span class="sxs-lookup"><span data-stu-id="c3462-136">Data (signals & correlated info)</span></span> | <span data-ttu-id="c3462-137">応答&の修復</span><span class="sxs-lookup"><span data-stu-id="c3462-137">Remediation & response scope</span></span> |
| ------ | ------ | ------ |
| <span data-ttu-id="c3462-138">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c3462-138">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="c3462-139">- エンドポイントの状態と生のイベント</span><span class="sxs-lookup"><span data-stu-id="c3462-139">- Endpoint states and raw events</span></span><br /><span data-ttu-id="c3462-140">- ウイルス対策、EDR、攻撃表面の縮小など、エンドポイントの検出とアラート</span><span class="sxs-lookup"><span data-stu-id="c3462-140">- Endpoint detections and alerts, including antivirus, EDR, attack surface reduction</span></span><br /><span data-ttu-id="c3462-141">- エンドポイントで観察されたファイルと他のエンティティに関する情報</span><span class="sxs-lookup"><span data-stu-id="c3462-141">- Info on files and other entities observed on endpoints</span></span> | <span data-ttu-id="c3462-142">エンドポイント</span><span class="sxs-lookup"><span data-stu-id="c3462-142">Endpoints</span></span> |
|<span data-ttu-id="c3462-143">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="c3462-143">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="c3462-144">- メールとメールボックスの状態と生のイベント</span><span class="sxs-lookup"><span data-stu-id="c3462-144">- Mail and mailbox states and raw events</span></span><br /><span data-ttu-id="c3462-145">- 電子メール、添付ファイル、およびリンクの検出</span><span class="sxs-lookup"><span data-stu-id="c3462-145">- Email, attachment, and link detections</span></span> | <span data-ttu-id="c3462-146">- メールボックス</span><span class="sxs-lookup"><span data-stu-id="c3462-146">- Mailboxes</span></span><br /><span data-ttu-id="c3462-147">- Microsoft 365 アカウント</span><span class="sxs-lookup"><span data-stu-id="c3462-147">- Microsoft 365 accounts</span></span> |
| <span data-ttu-id="c3462-148">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="c3462-148">Microsoft Defender for Identity</span></span> | <span data-ttu-id="c3462-149">- Active Directory 信号 (認証イベントを含む)</span><span class="sxs-lookup"><span data-stu-id="c3462-149">- Active Directory signals, including authentication events</span></span><br /><span data-ttu-id="c3462-150">- ID 関連の動作検出</span><span class="sxs-lookup"><span data-stu-id="c3462-150">- Identity-related behavioral detections</span></span> | <span data-ttu-id="c3462-151">ID</span><span class="sxs-lookup"><span data-stu-id="c3462-151">Identities</span></span> |
| <span data-ttu-id="c3462-152">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c3462-152">Microsoft Cloud App Security</span></span> | <span data-ttu-id="c3462-153">- 未指定のクラウド アプリとサービスの検出 (シャドウ IT)</span><span class="sxs-lookup"><span data-stu-id="c3462-153">- Detection of unsanctioned cloud apps and services (shadow IT)</span></span><br /><span data-ttu-id="c3462-154">- クラウド アプリへのデータの露出</span><span class="sxs-lookup"><span data-stu-id="c3462-154">- Exposure of data to cloud apps</span></span><br /><span data-ttu-id="c3462-155">- クラウド アプリに関連付けられている脅威アクティビティ</span><span class="sxs-lookup"><span data-stu-id="c3462-155">- Threat activity associated with cloud apps</span></span> | <span data-ttu-id="c3462-156">クラウド アプリ</span><span class="sxs-lookup"><span data-stu-id="c3462-156">Cloud apps</span></span> |

## <a name="deploy-the-services"></a><span data-ttu-id="c3462-157">サービスを展開する</span><span class="sxs-lookup"><span data-stu-id="c3462-157">Deploy the services</span></span>
<span data-ttu-id="c3462-158">各サービスを展開するには、通常、テナントへのプロビジョニングと初期構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="c3462-158">Deploying each service typically requires provisioning to your tenant and some initial configuration.</span></span> <span data-ttu-id="c3462-159">これらの各サービスの展開方法については、次の表をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c3462-159">See the following table to understand how each of these services are deployed.</span></span>

| <span data-ttu-id="c3462-160">サービス</span><span class="sxs-lookup"><span data-stu-id="c3462-160">Service</span></span> | <span data-ttu-id="c3462-161">プロビジョニング手順</span><span class="sxs-lookup"><span data-stu-id="c3462-161">Provisioning instructions</span></span> | <span data-ttu-id="c3462-162">初期構成</span><span class="sxs-lookup"><span data-stu-id="c3462-162">Initial configuration</span></span> |
| ------ | ------ | ------ |
| <span data-ttu-id="c3462-163">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c3462-163">Microsoft Defender for Endpoint</span></span> | [<span data-ttu-id="c3462-164">Microsoft Defender for Endpoint 展開ガイド</span><span class="sxs-lookup"><span data-stu-id="c3462-164">Microsoft Defender for Endpoint deployment guide</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases) | <span data-ttu-id="c3462-165">*プロビジョニング手順を参照する*</span><span class="sxs-lookup"><span data-stu-id="c3462-165">*See provisioning instructions*</span></span> |
|<span data-ttu-id="c3462-166">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="c3462-166">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="c3462-167">*なし (Office 365 でプロビジョニング)*</span><span class="sxs-lookup"><span data-stu-id="c3462-167">*None, provisioned with Office 365*</span></span> | [<span data-ttu-id="c3462-168">Microsoft Defender for Office 365 のポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="c3462-168">Configure Microsoft Defender for Office 365 policies</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| <span data-ttu-id="c3462-169">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="c3462-169">Microsoft Defender for Identity</span></span> | [<span data-ttu-id="c3462-170">クイック スタート: Id インスタンス用に Microsoft Defender を作成する</span><span class="sxs-lookup"><span data-stu-id="c3462-170">Quickstart: Create your Microsoft Defender for Identity instance</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | <span data-ttu-id="c3462-171">*プロビジョニング手順を参照する*</span><span class="sxs-lookup"><span data-stu-id="c3462-171">*See provisioning instructions*</span></span> |
| <span data-ttu-id="c3462-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c3462-172">Microsoft Cloud App Security</span></span> | <span data-ttu-id="c3462-173">*なし*</span><span class="sxs-lookup"><span data-stu-id="c3462-173">*None*</span></span> | [<span data-ttu-id="c3462-174">クイック スタート: Microsoft Cloud App Security の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="c3462-174">Quickstart: Get started with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

<span data-ttu-id="c3462-175">サポートされているサービスを展開したら [、Microsoft 365 Defender を有効にしてください](mtp-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="c3462-175">Once you’ve deployed the supported services, [turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c3462-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="c3462-176">Related topics</span></span>

- [<span data-ttu-id="c3462-177">Microsoft 365 Defender の概要</span><span class="sxs-lookup"><span data-stu-id="c3462-177">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="c3462-178">Microsoft 365 Defender を有効にする</span><span class="sxs-lookup"><span data-stu-id="c3462-178">Turn on Microsoft 365 Defender</span></span>](mtp-enable.md)
- [<span data-ttu-id="c3462-179">Microsoft Defender for Endpoint の概要</span><span class="sxs-lookup"><span data-stu-id="c3462-179">Microsoft Defender for Endpoint overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="c3462-180">Microsoft Defender for Office 365 の概要</span><span class="sxs-lookup"><span data-stu-id="c3462-180">Microsoft Defender for Office 365 overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="c3462-181">Microsoft Cloud App Security の概要</span><span class="sxs-lookup"><span data-stu-id="c3462-181">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="c3462-182">Id 用 Microsoft Defender の概要</span><span class="sxs-lookup"><span data-stu-id="c3462-182">Microsoft Defender for Identity overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
