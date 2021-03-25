---
title: Microsoft 365 Defender がサポートするサービスを展開する
description: Microsoft 365 Defender によって統合できる Microsoft セキュリティ サービス、ライセンス要件、展開手順について説明します。
keywords: 展開、ライセンス、サポートされるサービス、プロビジョニング、構成 Microsoft Threat Protection、M365、ライセンス適格性、Microsoft Defender ATP、MDATP、Office 365 ATP、Azure ATP、Microsoft Cloud App Security、MCAS、Advanced Threat Protection、E5、A5、EMS
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
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
ms.openlocfilehash: 434c318be404ffb04cac7a05664c8f001bb46507
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198863"
---
# <a name="deploy-supported-services"></a><span data-ttu-id="0efe0-104">サポートされているサービスを展開する</span><span class="sxs-lookup"><span data-stu-id="0efe0-104">Deploy supported services</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0efe0-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="0efe0-105">**Applies to:**</span></span>
- <span data-ttu-id="0efe0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0efe0-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="0efe0-107">[Microsoft 365 Defender は](microsoft-365-defender.md) 、さまざまな Microsoft セキュリティ サービスを統合して、高度な攻撃に対する一元的な検出、防止、および調査機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="0efe0-107">[Microsoft 365 Defender](microsoft-365-defender.md) integrates various Microsoft security services to provide centralized detection, prevention, and investigation capabilities against sophisticated attacks.</span></span> <span data-ttu-id="0efe0-108">この記事では、サポートされているサービス、ライセンス要件、1 つ以上のサービスの展開に関連する利点と制限、およびそれらを個別に完全に展開する方法へのリンクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="0efe0-108">This article describes the supported services, their licensing requirements, the advantages and limitations associated with deploying one or more services, and links to how you can fully deploy them individually.</span></span>

## <a name="supported-services"></a><span data-ttu-id="0efe0-109">サポートされているサービス</span><span class="sxs-lookup"><span data-stu-id="0efe0-109">Supported services</span></span>
<span data-ttu-id="0efe0-110">Microsoft 365 E5、E5 Security、A5、または A5 セキュリティ ライセンス、またはライセンスの有効な組み合わせにより、次のサポートされているサービスにアクセスし、Microsoft 365 セキュリティ センターで Microsoft 365 Defender を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0efe0-110">A Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses provides access to the following supported services and entitles you to use Microsoft 365 Defender in Microsoft 365 security center.</span></span> [<span data-ttu-id="0efe0-111">「ライセンス要件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0efe0-111">See licensing requirements</span></span>](prerequisites.md#licensing-requirements)

| <span data-ttu-id="0efe0-112">サポートされているサービス</span><span class="sxs-lookup"><span data-stu-id="0efe0-112">Supported service</span></span> | <span data-ttu-id="0efe0-113">説明</span><span class="sxs-lookup"><span data-stu-id="0efe0-113">Description</span></span> |
| ------ | ------ |
| <span data-ttu-id="0efe0-114">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0efe0-114">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="0efe0-115">強力な行動センサー、クラウド分析、脅威インテリジェンスを中心に構築されたエンドポイント保護スイート</span><span class="sxs-lookup"><span data-stu-id="0efe0-115">Endpoint protection suite built around powerful behavioral sensors, cloud analytics, and threat intelligence</span></span> |
|<span data-ttu-id="0efe0-116">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="0efe0-116">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="0efe0-117">メールなどのコラボレーション ツールを含む、Office 365 でのアプリとデータの高度な保護</span><span class="sxs-lookup"><span data-stu-id="0efe0-117">Advanced protection for your apps and data in Office 365, including email and other collaboration tools</span></span> |
| <span data-ttu-id="0efe0-118">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="0efe0-118">Microsoft Defender for Identity</span></span> | <span data-ttu-id="0efe0-119">関連付けされた Active Directory シグナルを使用して、高度な脅威、侵害された ID、悪意のあるインサイダーから防御する</span><span class="sxs-lookup"><span data-stu-id="0efe0-119">Defend against advanced threats, compromised identities, and malicious insiders using correlated Active Directory signals</span></span> |
| <span data-ttu-id="0efe0-120">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="0efe0-120">Microsoft Cloud App Security</span></span> | <span data-ttu-id="0efe0-121">Microsoft およびサード パーティのクラウド サービス全体でサイバー脅威を特定して対処する</span><span class="sxs-lookup"><span data-stu-id="0efe0-121">Identify and combat cyberthreats across your Microsoft and third-party cloud services</span></span> |

## <a name="deployed-services-and-functionality"></a><span data-ttu-id="0efe0-122">展開されたサービスと機能</span><span class="sxs-lookup"><span data-stu-id="0efe0-122">Deployed services and functionality</span></span>
<span data-ttu-id="0efe0-123">Microsoft 365 Defender は、サポートされるサービスの展開に合って、可視性、相関関係、修復を向上します。</span><span class="sxs-lookup"><span data-stu-id="0efe0-123">Microsoft 365 Defender provides better visibility, correlation, and remediation as you deploy more supported services.</span></span>

### <a name="benefits-of-full-deployment"></a><span data-ttu-id="0efe0-124">完全展開の利点</span><span class="sxs-lookup"><span data-stu-id="0efe0-124">Benefits of full deployment</span></span>
<span data-ttu-id="0efe0-125">Microsoft 365 Defender の完全な利点を得る場合は、サポートされているサービスを展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0efe0-125">To get the complete benefits of Microsoft 365 Defender, we recommend deploying all supported services.</span></span> <span data-ttu-id="0efe0-126">完全展開の主な利点を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0efe0-126">Here are some of the key benefits of full deployment:</span></span>
- <span data-ttu-id="0efe0-127">インシデントは、使用可能なすべてのセンサーとサービス固有の分析機能からのアラートとイベント信号に基づいて識別され、関連付けされます。</span><span class="sxs-lookup"><span data-stu-id="0efe0-127">Incidents are identified and correlated based on alerts and event signals from all available sensors and service-specific analysis capabilities</span></span>
- <span data-ttu-id="0efe0-128">自動調査と修復 (AIR) プレイブックは、デバイス、メールボックス、ユーザー アカウントなど、さまざまなエンティティの種類に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0efe0-128">Automated investigation and remediation (AIR) playbooks apply across various entity types, including devices, mailboxes, and user accounts</span></span>
- <span data-ttu-id="0efe0-129">デバイス、メールボックス、その他のエンティティからのイベントおよびエンティティ データに対して、より包括的な高度なハンティング スキーマを照会できます。</span><span class="sxs-lookup"><span data-stu-id="0efe0-129">A more comprehensive advanced hunting schema can be queried for event and entity data from devices, mailboxes, and other entities</span></span>

### <a name="limited-deployment-scenarios"></a><span data-ttu-id="0efe0-130">限られた展開シナリオ</span><span class="sxs-lookup"><span data-stu-id="0efe0-130">Limited deployment scenarios</span></span>
<span data-ttu-id="0efe0-131">展開するサポートされている各サービスは、生の信号と関連情報の非常に豊富なセットを提供します。</span><span class="sxs-lookup"><span data-stu-id="0efe0-131">Each supported service that you deploy provides an extremely rich set of raw signals as well as correlated information.</span></span> <span data-ttu-id="0efe0-132">限定的な展開では Microsoft 365 Defender の機能がオフにされませんが、エンドポイント、アプリ、データ、および ID 全体で包括的な可視性を提供する機能が影響を受ける。</span><span class="sxs-lookup"><span data-stu-id="0efe0-132">While limited deployment doesn’t cause Microsoft 365 Defender functionality to turn off, its ability to provide comprehensive visibility across your endpoints, apps, data, and identities is affected.</span></span> <span data-ttu-id="0efe0-133">同時に、修復機能は、展開したサービスによって管理できるエンティティにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="0efe0-133">At the same time, any remediation capabilities only apply to entities that can be managed by the services you’ve deployed.</span></span>

<span data-ttu-id="0efe0-134">次の表に、サポートされている各サービスが追加のデータを提供する方法、データを関連付けて追加の分析情報を取得する機会、および改善と対応の機能を示します。</span><span class="sxs-lookup"><span data-stu-id="0efe0-134">The table below lists how each supported service provides additional data, opportunities to obtain additional insight by correlating the data, and better remediation and response capabilities.</span></span>

| <span data-ttu-id="0efe0-135">サービス</span><span class="sxs-lookup"><span data-stu-id="0efe0-135">Service</span></span> | <span data-ttu-id="0efe0-136">データ (関連情報&シグナル)</span><span class="sxs-lookup"><span data-stu-id="0efe0-136">Data (signals & correlated info)</span></span> | <span data-ttu-id="0efe0-137">応答スコープ&修復</span><span class="sxs-lookup"><span data-stu-id="0efe0-137">Remediation & response scope</span></span> |
| ------ | ------ | ------ |
| <span data-ttu-id="0efe0-138">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0efe0-138">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="0efe0-139">- エンドポイントの状態と生のイベント</span><span class="sxs-lookup"><span data-stu-id="0efe0-139">- Endpoint states and raw events</span></span><br /><span data-ttu-id="0efe0-140">- ウイルス対策、EDR、攻撃表面の縮小などのエンドポイントの検出とアラート</span><span class="sxs-lookup"><span data-stu-id="0efe0-140">- Endpoint detections and alerts, including antivirus, EDR, attack surface reduction</span></span><br /><span data-ttu-id="0efe0-141">- エンドポイントで観察されたファイルや他のエンティティに関する情報</span><span class="sxs-lookup"><span data-stu-id="0efe0-141">- Info on files and other entities observed on endpoints</span></span> | <span data-ttu-id="0efe0-142">エンドポイント</span><span class="sxs-lookup"><span data-stu-id="0efe0-142">Endpoints</span></span> |
|<span data-ttu-id="0efe0-143">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="0efe0-143">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="0efe0-144">- メールとメールボックスの状態と生のイベント</span><span class="sxs-lookup"><span data-stu-id="0efe0-144">- Mail and mailbox states and raw events</span></span><br /><span data-ttu-id="0efe0-145">- メール、添付ファイル、およびリンクの検出</span><span class="sxs-lookup"><span data-stu-id="0efe0-145">- Email, attachment, and link detections</span></span> | <span data-ttu-id="0efe0-146">- メールボックス</span><span class="sxs-lookup"><span data-stu-id="0efe0-146">- Mailboxes</span></span><br /><span data-ttu-id="0efe0-147">- Microsoft 365 アカウント</span><span class="sxs-lookup"><span data-stu-id="0efe0-147">- Microsoft 365 accounts</span></span> |
| <span data-ttu-id="0efe0-148">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="0efe0-148">Microsoft Defender for Identity</span></span> | <span data-ttu-id="0efe0-149">- Active Directory 信号 (認証イベントを含む)</span><span class="sxs-lookup"><span data-stu-id="0efe0-149">- Active Directory signals, including authentication events</span></span><br /><span data-ttu-id="0efe0-150">- ID 関連の動作の検出</span><span class="sxs-lookup"><span data-stu-id="0efe0-150">- Identity-related behavioral detections</span></span> | <span data-ttu-id="0efe0-151">ID</span><span class="sxs-lookup"><span data-stu-id="0efe0-151">Identities</span></span> |
| <span data-ttu-id="0efe0-152">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="0efe0-152">Microsoft Cloud App Security</span></span> | <span data-ttu-id="0efe0-153">- 非許可のクラウド アプリとサービスの検出 (シャドウ IT)</span><span class="sxs-lookup"><span data-stu-id="0efe0-153">- Detection of unsanctioned cloud apps and services (shadow IT)</span></span><br /><span data-ttu-id="0efe0-154">- クラウド アプリへのデータの露出</span><span class="sxs-lookup"><span data-stu-id="0efe0-154">- Exposure of data to cloud apps</span></span><br /><span data-ttu-id="0efe0-155">- クラウド アプリに関連付けられた脅威アクティビティ</span><span class="sxs-lookup"><span data-stu-id="0efe0-155">- Threat activity associated with cloud apps</span></span> | <span data-ttu-id="0efe0-156">クラウド アプリ</span><span class="sxs-lookup"><span data-stu-id="0efe0-156">Cloud apps</span></span> |

## <a name="deploy-the-services"></a><span data-ttu-id="0efe0-157">サービスの展開</span><span class="sxs-lookup"><span data-stu-id="0efe0-157">Deploy the services</span></span>
<span data-ttu-id="0efe0-158">通常、各サービスを展開するには、テナントへのプロビジョニングと初期構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="0efe0-158">Deploying each service typically requires provisioning to your tenant and some initial configuration.</span></span> <span data-ttu-id="0efe0-159">これらの各サービスの展開方法については、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0efe0-159">See the following table to understand how each of these services are deployed.</span></span>

| <span data-ttu-id="0efe0-160">サービス</span><span class="sxs-lookup"><span data-stu-id="0efe0-160">Service</span></span> | <span data-ttu-id="0efe0-161">プロビジョニング手順</span><span class="sxs-lookup"><span data-stu-id="0efe0-161">Provisioning instructions</span></span> | <span data-ttu-id="0efe0-162">初期構成</span><span class="sxs-lookup"><span data-stu-id="0efe0-162">Initial configuration</span></span> |
| ------ | ------ | ------ |
| <span data-ttu-id="0efe0-163">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0efe0-163">Microsoft Defender for Endpoint</span></span> | [<span data-ttu-id="0efe0-164">Microsoft Defender for Endpoint 展開ガイド</span><span class="sxs-lookup"><span data-stu-id="0efe0-164">Microsoft Defender for Endpoint deployment guide</span></span>](../defender-endpoint/deployment-phases.md) | <span data-ttu-id="0efe0-165">*「プロビジョニングの手順」を参照してください。*</span><span class="sxs-lookup"><span data-stu-id="0efe0-165">*See provisioning instructions*</span></span> |
|<span data-ttu-id="0efe0-166">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="0efe0-166">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="0efe0-167">*None(365 Officeプロビジョニング)*</span><span class="sxs-lookup"><span data-stu-id="0efe0-167">*None, provisioned with Office 365*</span></span> | [<span data-ttu-id="0efe0-168">Microsoft Defender for Office 365 のポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="0efe0-168">Configure Microsoft Defender for Office 365 policies</span></span>](/microsoft-365/security/office-365-security/defender-for-office-365#configure-atp-policies) |
| <span data-ttu-id="0efe0-169">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="0efe0-169">Microsoft Defender for Identity</span></span> | [<span data-ttu-id="0efe0-170">クイック スタート: Microsoft Defender for Identity インスタンスを作成する</span><span class="sxs-lookup"><span data-stu-id="0efe0-170">Quickstart: Create your Microsoft Defender for Identity instance</span></span>](/azure-advanced-threat-protection/install-atp-step1) | <span data-ttu-id="0efe0-171">*「プロビジョニングの手順」を参照してください。*</span><span class="sxs-lookup"><span data-stu-id="0efe0-171">*See provisioning instructions*</span></span> |
| <span data-ttu-id="0efe0-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="0efe0-172">Microsoft Cloud App Security</span></span> | <span data-ttu-id="0efe0-173">*なし*</span><span class="sxs-lookup"><span data-stu-id="0efe0-173">*None*</span></span> | [<span data-ttu-id="0efe0-174">クイック スタート: Microsoft Cloud App Security の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="0efe0-174">Quickstart: Get started with Microsoft Cloud App Security</span></span>](/cloud-app-security/getting-started-with-cloud-app-security) |

<span data-ttu-id="0efe0-175">サポートされているサービスを展開したら [、Microsoft 365 Defender をオンにしてください](m365d-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="0efe0-175">Once you’ve deployed the supported services, [turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="0efe0-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="0efe0-176">Related topics</span></span>

- [<span data-ttu-id="0efe0-177">Microsoft 365 Defender の概要</span><span class="sxs-lookup"><span data-stu-id="0efe0-177">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="0efe0-178">Microsoft 365 Defender を有効にする</span><span class="sxs-lookup"><span data-stu-id="0efe0-178">Turn on Microsoft 365 Defender</span></span>](m365d-enable.md)
- [<span data-ttu-id="0efe0-179">Microsoft Defender for Endpoint の概要</span><span class="sxs-lookup"><span data-stu-id="0efe0-179">Microsoft Defender for Endpoint overview</span></span>](../defender-endpoint/microsoft-defender-endpoint.md)
- [<span data-ttu-id="0efe0-180">Microsoft Defender for Office 365 の概要</span><span class="sxs-lookup"><span data-stu-id="0efe0-180">Microsoft Defender for Office 365 overview</span></span>](../office-365-security/defender-for-office-365.md)
- [<span data-ttu-id="0efe0-181">Microsoft Cloud App Security の概要</span><span class="sxs-lookup"><span data-stu-id="0efe0-181">Microsoft Cloud App Security overview</span></span>](/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="0efe0-182">Microsoft Defender for Identity の概要</span><span class="sxs-lookup"><span data-stu-id="0efe0-182">Microsoft Defender for Identity overview</span></span>](/azure-advanced-threat-protection/what-is-atp)