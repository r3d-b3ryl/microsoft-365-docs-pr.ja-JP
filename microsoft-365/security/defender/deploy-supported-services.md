---
title: Defender でサポートされるサービスMicrosoft 365展開する
description: Defender、ライセンス要件、および展開手順によって統合Microsoft 365 Microsoft セキュリティ サービスについて説明します。
keywords: 展開、ライセンス、サポートされているサービス、プロビジョニング、構成 Microsoft 365 Defender、M365、ライセンス適格性、Microsoft Defender for Endpoint、microsoft Defender for Office 365、Microsoft Defender for Identity、Microsoft Cloud App Security、MCAS、E5、A5、EMS
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
ms.openlocfilehash: 4e1b36423974e46a485727f7e1f158dc6163d834
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935679"
---
# <a name="deploy-supported-services"></a><span data-ttu-id="2ba92-104">サポートされているサービスを展開する</span><span class="sxs-lookup"><span data-stu-id="2ba92-104">Deploy supported services</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2ba92-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="2ba92-105">**Applies to:**</span></span>
- <span data-ttu-id="2ba92-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2ba92-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="2ba92-107">[Microsoft 365 Defender は、](microsoft-365-defender.md)さまざまな Microsoft セキュリティ サービスを統合して、高度な攻撃に対する一元的な検出、防止、および調査機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="2ba92-107">[Microsoft 365 Defender](microsoft-365-defender.md) integrates various Microsoft security services to provide centralized detection, prevention, and investigation capabilities against sophisticated attacks.</span></span> <span data-ttu-id="2ba92-108">この記事では、サポートされているサービス、ライセンス要件、1 つ以上のサービスの展開に関連する利点と制限、およびそれらを個別に完全に展開する方法へのリンクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2ba92-108">This article describes the supported services, their licensing requirements, the advantages and limitations associated with deploying one or more services, and links to how you can fully deploy them individually.</span></span>

## <a name="supported-services"></a><span data-ttu-id="2ba92-109">サポートされているサービス</span><span class="sxs-lookup"><span data-stu-id="2ba92-109">Supported services</span></span>
<span data-ttu-id="2ba92-110">Microsoft 365 E5、E5 Security、A5、または A5 セキュリティ ライセンス、またはライセンスの有効な組み合わせにより、以下のサポートされているサービスにアクセスし、Microsoft 365 セキュリティ センターで Microsoft 365 Defender を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2ba92-110">A Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses provides access to the following supported services and entitles you to use Microsoft 365 Defender in Microsoft 365 security center.</span></span> [<span data-ttu-id="2ba92-111">「ライセンス要件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ba92-111">See licensing requirements</span></span>](prerequisites.md#licensing-requirements)

| <span data-ttu-id="2ba92-112">サポートされているサービス</span><span class="sxs-lookup"><span data-stu-id="2ba92-112">Supported service</span></span> | <span data-ttu-id="2ba92-113">説明</span><span class="sxs-lookup"><span data-stu-id="2ba92-113">Description</span></span> |
| ------ | ------ |
| <span data-ttu-id="2ba92-114">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2ba92-114">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="2ba92-115">強力な行動センサー、クラウド分析、脅威インテリジェンスを中心に構築されたエンドポイント保護スイート</span><span class="sxs-lookup"><span data-stu-id="2ba92-115">Endpoint protection suite built around powerful behavioral sensors, cloud analytics, and threat intelligence</span></span> |
|<span data-ttu-id="2ba92-116">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="2ba92-116">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="2ba92-117">メールなどのコラボレーション ツールを含む、Office 365データの高度な保護</span><span class="sxs-lookup"><span data-stu-id="2ba92-117">Advanced protection for your apps and data in Office 365, including email and other collaboration tools</span></span> |
| <span data-ttu-id="2ba92-118">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="2ba92-118">Microsoft Defender for Identity</span></span> | <span data-ttu-id="2ba92-119">関連付けされた Active Directory シグナルを使用して、高度な脅威、侵害された ID、悪意のあるインサイダーから防御する</span><span class="sxs-lookup"><span data-stu-id="2ba92-119">Defend against advanced threats, compromised identities, and malicious insiders using correlated Active Directory signals</span></span> |
| <span data-ttu-id="2ba92-120">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2ba92-120">Microsoft Cloud App Security</span></span> | <span data-ttu-id="2ba92-121">Microsoft およびサード パーティのクラウド サービス全体でサイバー脅威を特定して対処する</span><span class="sxs-lookup"><span data-stu-id="2ba92-121">Identify and combat cyberthreats across your Microsoft and third-party cloud services</span></span> |

## <a name="deployed-services-and-functionality"></a><span data-ttu-id="2ba92-122">展開されたサービスと機能</span><span class="sxs-lookup"><span data-stu-id="2ba92-122">Deployed services and functionality</span></span>
<span data-ttu-id="2ba92-123">Microsoft 365Defender は、サポートされているサービスの展開に合って、より良い可視性、相関関係、修復を提供します。</span><span class="sxs-lookup"><span data-stu-id="2ba92-123">Microsoft 365 Defender provides better visibility, correlation, and remediation as you deploy more supported services.</span></span>

### <a name="benefits-of-full-deployment"></a><span data-ttu-id="2ba92-124">完全展開の利点</span><span class="sxs-lookup"><span data-stu-id="2ba92-124">Benefits of full deployment</span></span>
<span data-ttu-id="2ba92-125">Defender の完全な利点を得Microsoft 365サポートされているサービスを展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2ba92-125">To get the complete benefits of Microsoft 365 Defender, we recommend deploying all supported services.</span></span> <span data-ttu-id="2ba92-126">完全展開の主な利点を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2ba92-126">Here are some of the key benefits of full deployment:</span></span>
- <span data-ttu-id="2ba92-127">インシデントは、使用可能なすべてのセンサーとサービス固有の分析機能からのアラートとイベント信号に基づいて識別され、関連付けされます。</span><span class="sxs-lookup"><span data-stu-id="2ba92-127">Incidents are identified and correlated based on alerts and event signals from all available sensors and service-specific analysis capabilities</span></span>
- <span data-ttu-id="2ba92-128">自動調査と修復 (AIR) プレイブックは、デバイス、メールボックス、ユーザー アカウントなど、さまざまなエンティティの種類に適用されます。</span><span class="sxs-lookup"><span data-stu-id="2ba92-128">Automated investigation and remediation (AIR) playbooks apply across various entity types, including devices, mailboxes, and user accounts</span></span>
- <span data-ttu-id="2ba92-129">デバイス、メールボックス、その他のエンティティからのイベントおよびエンティティ データに対して、より包括的な高度なハンティング スキーマを照会できます。</span><span class="sxs-lookup"><span data-stu-id="2ba92-129">A more comprehensive advanced hunting schema can be queried for event and entity data from devices, mailboxes, and other entities</span></span>

### <a name="limited-deployment-scenarios"></a><span data-ttu-id="2ba92-130">限られた展開シナリオ</span><span class="sxs-lookup"><span data-stu-id="2ba92-130">Limited deployment scenarios</span></span>
<span data-ttu-id="2ba92-131">展開するサポートされている各サービスは、生の信号と関連情報の非常に豊富なセットを提供します。</span><span class="sxs-lookup"><span data-stu-id="2ba92-131">Each supported service that you deploy provides an extremely rich set of raw signals as well as correlated information.</span></span> <span data-ttu-id="2ba92-132">限定的な展開では、Microsoft 365 Defender の機能は無効にされませんが、エンドポイント、アプリ、データ、および ID 全体で包括的な可視性を提供する機能が影響を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2ba92-132">While limited deployment doesn’t cause Microsoft 365 Defender functionality to turn off, its ability to provide comprehensive visibility across your endpoints, apps, data, and identities is affected.</span></span> <span data-ttu-id="2ba92-133">同時に、修復機能は、展開したサービスによって管理できるエンティティにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="2ba92-133">At the same time, any remediation capabilities only apply to entities that can be managed by the services you’ve deployed.</span></span>

<span data-ttu-id="2ba92-134">次の表に、サポートされている各サービスが追加のデータを提供する方法、データを関連付けて追加の分析情報を取得する機会、および改善と対応の機能を示します。</span><span class="sxs-lookup"><span data-stu-id="2ba92-134">The table below lists how each supported service provides additional data, opportunities to obtain additional insight by correlating the data, and better remediation and response capabilities.</span></span>

| <span data-ttu-id="2ba92-135">サービス</span><span class="sxs-lookup"><span data-stu-id="2ba92-135">Service</span></span> | <span data-ttu-id="2ba92-136">データ (関連情報&シグナル)</span><span class="sxs-lookup"><span data-stu-id="2ba92-136">Data (signals & correlated info)</span></span> | <span data-ttu-id="2ba92-137">応答スコープ&修復</span><span class="sxs-lookup"><span data-stu-id="2ba92-137">Remediation & response scope</span></span> |
| ------ | ------ | ------ |
| <span data-ttu-id="2ba92-138">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2ba92-138">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="2ba92-139">- エンドポイントの状態と生のイベント</span><span class="sxs-lookup"><span data-stu-id="2ba92-139">- Endpoint states and raw events</span></span><br /><span data-ttu-id="2ba92-140">- ウイルス対策、ウイルス対策、脅威、攻撃EDRを含むエンドポイントの検出とアラート</span><span class="sxs-lookup"><span data-stu-id="2ba92-140">- Endpoint detections and alerts, including antivirus, EDR, attack surface reduction</span></span><br /><span data-ttu-id="2ba92-141">- エンドポイントで観察されたファイルや他のエンティティに関する情報</span><span class="sxs-lookup"><span data-stu-id="2ba92-141">- Info on files and other entities observed on endpoints</span></span> | <span data-ttu-id="2ba92-142">エンドポイント</span><span class="sxs-lookup"><span data-stu-id="2ba92-142">Endpoints</span></span> |
|<span data-ttu-id="2ba92-143">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="2ba92-143">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="2ba92-144">- メールとメールボックスの状態と生のイベント</span><span class="sxs-lookup"><span data-stu-id="2ba92-144">- Mail and mailbox states and raw events</span></span><br /><span data-ttu-id="2ba92-145">- メール、添付ファイル、およびリンクの検出</span><span class="sxs-lookup"><span data-stu-id="2ba92-145">- Email, attachment, and link detections</span></span> | <span data-ttu-id="2ba92-146">- メールボックス</span><span class="sxs-lookup"><span data-stu-id="2ba92-146">- Mailboxes</span></span><br /><span data-ttu-id="2ba92-147">- Microsoft 365アカウント</span><span class="sxs-lookup"><span data-stu-id="2ba92-147">- Microsoft 365 accounts</span></span> |
| <span data-ttu-id="2ba92-148">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="2ba92-148">Microsoft Defender for Identity</span></span> | <span data-ttu-id="2ba92-149">- Active Directory 信号 (認証イベントを含む)</span><span class="sxs-lookup"><span data-stu-id="2ba92-149">- Active Directory signals, including authentication events</span></span><br /><span data-ttu-id="2ba92-150">- ID 関連の動作の検出</span><span class="sxs-lookup"><span data-stu-id="2ba92-150">- Identity-related behavioral detections</span></span> | <span data-ttu-id="2ba92-151">ID</span><span class="sxs-lookup"><span data-stu-id="2ba92-151">Identities</span></span> |
| <span data-ttu-id="2ba92-152">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2ba92-152">Microsoft Cloud App Security</span></span> | <span data-ttu-id="2ba92-153">- 非許可のクラウド アプリとサービスの検出 (シャドウ IT)</span><span class="sxs-lookup"><span data-stu-id="2ba92-153">- Detection of unsanctioned cloud apps and services (shadow IT)</span></span><br /><span data-ttu-id="2ba92-154">- クラウド アプリへのデータの露出</span><span class="sxs-lookup"><span data-stu-id="2ba92-154">- Exposure of data to cloud apps</span></span><br /><span data-ttu-id="2ba92-155">- クラウド アプリに関連付けられた脅威アクティビティ</span><span class="sxs-lookup"><span data-stu-id="2ba92-155">- Threat activity associated with cloud apps</span></span> | <span data-ttu-id="2ba92-156">クラウド アプリ</span><span class="sxs-lookup"><span data-stu-id="2ba92-156">Cloud apps</span></span> |

## <a name="deploy-the-services"></a><span data-ttu-id="2ba92-157">サービスの展開</span><span class="sxs-lookup"><span data-stu-id="2ba92-157">Deploy the services</span></span>
<span data-ttu-id="2ba92-158">通常、各サービスを展開するには、テナントへのプロビジョニングと初期構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="2ba92-158">Deploying each service typically requires provisioning to your tenant and some initial configuration.</span></span> <span data-ttu-id="2ba92-159">これらの各サービスの展開方法については、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ba92-159">See the following table to understand how each of these services are deployed.</span></span>

| <span data-ttu-id="2ba92-160">サービス</span><span class="sxs-lookup"><span data-stu-id="2ba92-160">Service</span></span> | <span data-ttu-id="2ba92-161">プロビジョニング手順</span><span class="sxs-lookup"><span data-stu-id="2ba92-161">Provisioning instructions</span></span> | <span data-ttu-id="2ba92-162">初期構成</span><span class="sxs-lookup"><span data-stu-id="2ba92-162">Initial configuration</span></span> |
| ------ | ------ | ------ |
| <span data-ttu-id="2ba92-163">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2ba92-163">Microsoft Defender for Endpoint</span></span> | [<span data-ttu-id="2ba92-164">Microsoft Defender for Endpoint 展開ガイド</span><span class="sxs-lookup"><span data-stu-id="2ba92-164">Microsoft Defender for Endpoint deployment guide</span></span>](../defender-endpoint/deployment-phases.md) | <span data-ttu-id="2ba92-165">*「プロビジョニングの手順」を参照してください。*</span><span class="sxs-lookup"><span data-stu-id="2ba92-165">*See provisioning instructions*</span></span> |
|<span data-ttu-id="2ba92-166">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="2ba92-166">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="2ba92-167">*None、プロビジョニングは、Office 365*</span><span class="sxs-lookup"><span data-stu-id="2ba92-167">*None, provisioned with Office 365*</span></span> | [<span data-ttu-id="2ba92-168">Microsoft Defender for Office 365 のポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="2ba92-168">Configure Microsoft Defender for Office 365 policies</span></span>](/microsoft-365/security/office-365-security/defender-for-office-365#configure-atp-policies) |
| <span data-ttu-id="2ba92-169">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="2ba92-169">Microsoft Defender for Identity</span></span> | [<span data-ttu-id="2ba92-170">クイック スタート: Microsoft Defender for Identity インスタンスを作成する</span><span class="sxs-lookup"><span data-stu-id="2ba92-170">Quickstart: Create your Microsoft Defender for Identity instance</span></span>](/azure-advanced-threat-protection/install-atp-step1) | <span data-ttu-id="2ba92-171">*「プロビジョニングの手順」を参照してください。*</span><span class="sxs-lookup"><span data-stu-id="2ba92-171">*See provisioning instructions*</span></span> |
| <span data-ttu-id="2ba92-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2ba92-172">Microsoft Cloud App Security</span></span> | <span data-ttu-id="2ba92-173">*なし*</span><span class="sxs-lookup"><span data-stu-id="2ba92-173">*None*</span></span> | [<span data-ttu-id="2ba92-174">クイック スタート: クイック スタートMicrosoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2ba92-174">Quickstart: Get started with Microsoft Cloud App Security</span></span>](/cloud-app-security/getting-started-with-cloud-app-security) |

<span data-ttu-id="2ba92-175">サポートされているサービスを展開したら、Defender のMicrosoft 365[します](m365d-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="2ba92-175">Once you’ve deployed the supported services, [turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2ba92-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ba92-176">Related topics</span></span>

- [<span data-ttu-id="2ba92-177">Microsoft 365Defender の概要</span><span class="sxs-lookup"><span data-stu-id="2ba92-177">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="2ba92-178">Microsoft 365 Defender を有効にする</span><span class="sxs-lookup"><span data-stu-id="2ba92-178">Turn on Microsoft 365 Defender</span></span>](m365d-enable.md)
- [<span data-ttu-id="2ba92-179">Microsoft Defender for Endpoint の概要</span><span class="sxs-lookup"><span data-stu-id="2ba92-179">Microsoft Defender for Endpoint overview</span></span>](../defender-endpoint/microsoft-defender-endpoint.md)
- [<span data-ttu-id="2ba92-180">Microsoft Defender for Office 365概要</span><span class="sxs-lookup"><span data-stu-id="2ba92-180">Microsoft Defender for Office 365 overview</span></span>](../office-365-security/defender-for-office-365.md)
- [<span data-ttu-id="2ba92-181">Microsoft Cloud App Security の概要</span><span class="sxs-lookup"><span data-stu-id="2ba92-181">Microsoft Cloud App Security overview</span></span>](/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="2ba92-182">Microsoft Defender for Identity の概要</span><span class="sxs-lookup"><span data-stu-id="2ba92-182">Microsoft Defender for Identity overview</span></span>](/azure-advanced-threat-protection/what-is-atp)
