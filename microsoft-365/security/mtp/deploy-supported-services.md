---
title: Microsoft の脅威保護によってサポートされるサービスを展開する
description: Microsoft の脅威保護、ライセンスの要件、および展開手順によって統合できる Microsoft セキュリティサービスについて説明します。
keywords: 展開、ライセンス、サポートされているサービス、プロビジョニング、構成 Microsoft Threat Protection、M365、ライセンス資格、Microsoft Defender ATP、MDATP、Office 365 ATP、Azure ATP、Microsoft Cloud App Security、MCAS、advanced Threat Protection、E5、A5、EMS
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: c29027bb641530ba2d3c7a22c578770c098f53ba
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633473"
---
# <a name="deploy-supported-services"></a><span data-ttu-id="1c101-104">サポートされるサービスを展開する</span><span class="sxs-lookup"><span data-stu-id="1c101-104">Deploy supported services</span></span>

<span data-ttu-id="1c101-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="1c101-105">**Applies to:**</span></span>
- <span data-ttu-id="1c101-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="1c101-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="1c101-107">[Microsoft の脅威保護](microsoft-threat-protection.md)では、さまざまな microsoft セキュリティサービスが統合され、高度な攻撃に対する一元的な検出、防止、調査の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="1c101-107">[Microsoft Threat Protection](microsoft-threat-protection.md) integrates various Microsoft security services to provide centralized detection, prevention, and investigation capabilities against sophisticated attacks.</span></span> <span data-ttu-id="1c101-108">この記事では、サポートされるサービス、ライセンス要件、1つ以上のサービスの展開に関連する利点と制限事項、およびそれらを個別に完全に展開する方法へのリンクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1c101-108">This article describes the supported services, their licensing requirements, the advantages and limitations associated with deploying one or more services, and links to how you can fully deploy them individually.</span></span>

## <a name="supported-services"></a><span data-ttu-id="1c101-109">サポートされるサービス</span><span class="sxs-lookup"><span data-stu-id="1c101-109">Supported services</span></span>
<span data-ttu-id="1c101-110">Microsoft 365 E5、E5 セキュリティ、A5、または A5 セキュリティライセンス、あるいはライセンスの有効な組み合わせにより、次のサポートされているサービスへのアクセスが可能になり、microsoft 365 セキュリティセンターで Microsoft の脅威保護を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1c101-110">A Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses provides access to the following supported services and entitles you to use Microsoft Threat Protection in Microsoft 365 security center.</span></span> [<span data-ttu-id="1c101-111">ライセンス要件を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c101-111">See licensing requirements</span></span>](prerequisites.md#licensing-requirements)

| <span data-ttu-id="1c101-112">サポートされるサービス</span><span class="sxs-lookup"><span data-stu-id="1c101-112">Supported service</span></span> | <span data-ttu-id="1c101-113">説明</span><span class="sxs-lookup"><span data-stu-id="1c101-113">Description</span></span> |
| ------ | ------ |
| <span data-ttu-id="1c101-114">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="1c101-114">Microsoft Defender ATP</span></span> | <span data-ttu-id="1c101-115">強力な動作センサー、クラウド分析、脅威インテリジェンスに基づいて構築されたエンドポイント保護スイート</span><span class="sxs-lookup"><span data-stu-id="1c101-115">Endpoint protection suite built around powerful behavioral sensors, cloud analytics, and threat intelligence</span></span> |
| <span data-ttu-id="1c101-116">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="1c101-116">Office 365 ATP</span></span> | <span data-ttu-id="1c101-117">Office 365 でのアプリとデータの高度な保護 (電子メールやその他のコラボレーションツールを含む)</span><span class="sxs-lookup"><span data-stu-id="1c101-117">Advanced protection for your apps and data in Office 365, including email and other collaboration tools</span></span> |
| <span data-ttu-id="1c101-118">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="1c101-118">Azure ATP</span></span> | <span data-ttu-id="1c101-119">高度な脅威、侵害された id、および悪意のある内部者に対して、関連付けられた Active Directory シグナルを使用した防御</span><span class="sxs-lookup"><span data-stu-id="1c101-119">Defend against advanced threats, compromised identities, and malicious insiders using correlated Active Directory signals</span></span> |
| <span data-ttu-id="1c101-120">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="1c101-120">Microsoft Cloud App Security</span></span> | <span data-ttu-id="1c101-121">Microsoft およびサードパーティ製のクラウドサービスの脅威を特定し、戦闘する</span><span class="sxs-lookup"><span data-stu-id="1c101-121">Identify and combat cyberthreats across your Microsoft and third-party cloud services</span></span> |

## <a name="deployed-services-and-functionality"></a><span data-ttu-id="1c101-122">展開されたサービスと機能</span><span class="sxs-lookup"><span data-stu-id="1c101-122">Deployed services and functionality</span></span>
<span data-ttu-id="1c101-123">Microsoft の脅威保護では、より多くのサポートされるサービスを展開することにより、可視性、相互関係、および修復が向上します。</span><span class="sxs-lookup"><span data-stu-id="1c101-123">Microsoft Threat Protection provides better visibility, correlation, and remediation as you deploy more supported services.</span></span>

### <a name="benefits-of-full-deployment"></a><span data-ttu-id="1c101-124">完全な展開の利点</span><span class="sxs-lookup"><span data-stu-id="1c101-124">Benefits of full deployment</span></span>
<span data-ttu-id="1c101-125">Microsoft の脅威保護の完全なメリットを得るために、サポートされているすべてのサービスを展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1c101-125">To get the complete benefits of Microsoft Threat Protection, we recommend deploying all supported services.</span></span> <span data-ttu-id="1c101-126">完全な展開の主な利点は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1c101-126">Here are some of the key benefits of full deployment:</span></span>
- <span data-ttu-id="1c101-127">インシデントは、利用可能なすべてのセンサーおよびサービス固有の分析機能からのアラートとイベント信号に基づいて識別され、関連しています。</span><span class="sxs-lookup"><span data-stu-id="1c101-127">Incidents are identified and correlated based on alerts and event signals from all available sensors and service-specific analysis capabilities</span></span>
- <span data-ttu-id="1c101-128">自動化された調査と修復 (AIR) のプレイブックは、デバイス、メールボックス、ユーザーアカウントなどのさまざまなエンティティの種類に適用されます。</span><span class="sxs-lookup"><span data-stu-id="1c101-128">Automated investigation and remediation (AIR) playbooks apply across various entity types, including devices, mailboxes, and user accounts</span></span>
- <span data-ttu-id="1c101-129">デバイス、メールボックス、およびその他のエンティティのイベントおよびエンティティデータについて、より詳細な検索スキーマを照会することができます。</span><span class="sxs-lookup"><span data-stu-id="1c101-129">A more comprehensive advanced hunting schema can be queried for event and entity data from devices, mailboxes, and other entities</span></span>

### <a name="limited-deployment-scenarios"></a><span data-ttu-id="1c101-130">限定的な展開シナリオ</span><span class="sxs-lookup"><span data-stu-id="1c101-130">Limited deployment scenarios</span></span>
<span data-ttu-id="1c101-131">展開するサポートされているサービスごとに、非常に豊富な未加工の信号と、相関情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="1c101-131">Each supported service that you deploy provides an extremely rich set of raw signals as well as correlated information.</span></span> <span data-ttu-id="1c101-132">制限のある展開では、Microsoft の脅威保護機能がオフになることはありませんが、エンドポイント間で包括的な可視性を提供する機能、アプリ、データ、および id が影響を受けることはありません。</span><span class="sxs-lookup"><span data-stu-id="1c101-132">While limited deployment doesn’t cause Microsoft Threat Protection functionality to turn off, its ability to provide comprehensive visibility across your endpoints, apps, data, and identities is affected.</span></span> <span data-ttu-id="1c101-133">同時に、すべての修復機能は、展開したサービスで管理できるエンティティにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="1c101-133">At the same time, any remediation capabilities only apply to entities that can be managed by the services you’ve deployed.</span></span>

<span data-ttu-id="1c101-134">次の表に、サポートされている各サービスが追加データを提供する方法、データを関連付けることによってさらに詳細な情報を得る方法、および改善と応答の機能を示します。</span><span class="sxs-lookup"><span data-stu-id="1c101-134">The table below lists how each supported service provides additional data, opportunities to obtain additional insight by correlating the data, and better remediation and response capabilities.</span></span>

| <span data-ttu-id="1c101-135">サービス</span><span class="sxs-lookup"><span data-stu-id="1c101-135">Service</span></span> | <span data-ttu-id="1c101-136">データ (& 関連付けられる情報)</span><span class="sxs-lookup"><span data-stu-id="1c101-136">Data (signals & correlated info)</span></span> | <span data-ttu-id="1c101-137">修復 & 応答の範囲</span><span class="sxs-lookup"><span data-stu-id="1c101-137">Remediation & response scope</span></span> |
| ------ | ------ | ------ |
| <span data-ttu-id="1c101-138">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="1c101-138">Microsoft Defender ATP</span></span> | <span data-ttu-id="1c101-139">-エンドポイントの状態と生のイベント</span><span class="sxs-lookup"><span data-stu-id="1c101-139">- Endpoint states and raw events</span></span><br /><span data-ttu-id="1c101-140">-ウイルス対策、EDR、攻撃対象領域の削減を含むエンドポイントの検出と通知</span><span class="sxs-lookup"><span data-stu-id="1c101-140">- Endpoint detections and alerts, including antivirus, EDR, attack surface reduction</span></span><br /><span data-ttu-id="1c101-141">-エンドポイントで監視されたファイルやその他のエンティティに関する情報</span><span class="sxs-lookup"><span data-stu-id="1c101-141">- Info on files and other entities observed on endpoints</span></span> | <span data-ttu-id="1c101-142">エンドポイント</span><span class="sxs-lookup"><span data-stu-id="1c101-142">Endpoints</span></span> |
| <span data-ttu-id="1c101-143">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="1c101-143">Office 365 ATP</span></span> | <span data-ttu-id="1c101-144">-メールとメールボックスの状態および生のイベント</span><span class="sxs-lookup"><span data-stu-id="1c101-144">- Mail and mailbox states and raw events</span></span><br /><span data-ttu-id="1c101-145">-電子メール、添付ファイル、およびリンクの検出</span><span class="sxs-lookup"><span data-stu-id="1c101-145">- Email, attachment, and link detections</span></span> | <span data-ttu-id="1c101-146">-メールボックス</span><span class="sxs-lookup"><span data-stu-id="1c101-146">- Mailboxes</span></span><br /><span data-ttu-id="1c101-147">-Microsoft 365 アカウント</span><span class="sxs-lookup"><span data-stu-id="1c101-147">- Microsoft 365 accounts</span></span> |
| <span data-ttu-id="1c101-148">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="1c101-148">Azure ATP</span></span> | <span data-ttu-id="1c101-149">-Active Directory シグナル (認証イベントを含む)</span><span class="sxs-lookup"><span data-stu-id="1c101-149">- Active Directory signals, including authentication events</span></span><br /><span data-ttu-id="1c101-150">-Id 関連の動作の検出</span><span class="sxs-lookup"><span data-stu-id="1c101-150">- Identity-related behavioral detections</span></span> | <span data-ttu-id="1c101-151">ID</span><span class="sxs-lookup"><span data-stu-id="1c101-151">Identities</span></span> |
| <span data-ttu-id="1c101-152">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="1c101-152">Microsoft Cloud App Security</span></span> | <span data-ttu-id="1c101-153">-承認されていないクラウドアプリおよびサービスの検出 (シャドウ IT)</span><span class="sxs-lookup"><span data-stu-id="1c101-153">- Detection of unsanctioned cloud apps and services (shadow IT)</span></span><br /><span data-ttu-id="1c101-154">-クラウドアプリへのデータの公開</span><span class="sxs-lookup"><span data-stu-id="1c101-154">- Exposure of data to cloud apps</span></span><br /><span data-ttu-id="1c101-155">-クラウドアプリに関連付けられている脅威アクティビティ</span><span class="sxs-lookup"><span data-stu-id="1c101-155">- Threat activity associated with cloud apps</span></span> | <span data-ttu-id="1c101-156">クラウド アプリ</span><span class="sxs-lookup"><span data-stu-id="1c101-156">Cloud apps</span></span> |

## <a name="deploy-the-services"></a><span data-ttu-id="1c101-157">サービスを展開する</span><span class="sxs-lookup"><span data-stu-id="1c101-157">Deploy the services</span></span>
<span data-ttu-id="1c101-158">通常、各サービスを展開するには、テナントに対するプロビジョニングと、いくつかの初期構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="1c101-158">Deploying each service typically requires provisioning to your tenant and some initial configuration.</span></span> <span data-ttu-id="1c101-159">これらの各サービスの展開方法については、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c101-159">See the following table to understand how each of these services are deployed.</span></span>

| <span data-ttu-id="1c101-160">サービス</span><span class="sxs-lookup"><span data-stu-id="1c101-160">Service</span></span> | <span data-ttu-id="1c101-161">プロビジョニング手順</span><span class="sxs-lookup"><span data-stu-id="1c101-161">Provisioning instructions</span></span> | <span data-ttu-id="1c101-162">初期構成</span><span class="sxs-lookup"><span data-stu-id="1c101-162">Initial configuration</span></span> |
| ------ | ------ | ------ |
| <span data-ttu-id="1c101-163">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="1c101-163">Microsoft Defender ATP</span></span> | [<span data-ttu-id="1c101-164">Microsoft Defender ATP 展開ガイド</span><span class="sxs-lookup"><span data-stu-id="1c101-164">Microsoft Defender ATP deployment guide</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases) | <span data-ttu-id="1c101-165">*プロビジョニングの手順を参照してください。*</span><span class="sxs-lookup"><span data-stu-id="1c101-165">*See provisioning instructions*</span></span> |
| <span data-ttu-id="1c101-166">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="1c101-166">Office 365 ATP</span></span> | <span data-ttu-id="1c101-167">*なし。 Office 365 でプロビジョニングされます。*</span><span class="sxs-lookup"><span data-stu-id="1c101-167">*None, provisioned with Office 365*</span></span> | [<span data-ttu-id="1c101-168">ATP ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="1c101-168">Configure ATP policies</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| <span data-ttu-id="1c101-169">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="1c101-169">Azure ATP</span></span> | [<span data-ttu-id="1c101-170">クイックスタート: Azure ATP インスタンスを作成する</span><span class="sxs-lookup"><span data-stu-id="1c101-170">Quickstart: Create your Azure ATP instance</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | <span data-ttu-id="1c101-171">*プロビジョニングの手順を参照してください。*</span><span class="sxs-lookup"><span data-stu-id="1c101-171">*See provisioning instructions*</span></span> |
| <span data-ttu-id="1c101-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="1c101-172">Microsoft Cloud App Security</span></span> | <span data-ttu-id="1c101-173">*なし*</span><span class="sxs-lookup"><span data-stu-id="1c101-173">*None*</span></span> | [<span data-ttu-id="1c101-174">クイックスタート: Microsoft Cloud App Security を使い始める</span><span class="sxs-lookup"><span data-stu-id="1c101-174">Quickstart: Get started with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

<span data-ttu-id="1c101-175">サポートされているサービスを展開したら、 [Microsoft の脅威保護を有効](mtp-enable.md)にします。</span><span class="sxs-lookup"><span data-stu-id="1c101-175">Once you’ve deployed the supported services, [turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="1c101-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="1c101-176">Related topics</span></span>

- [<span data-ttu-id="1c101-177">Microsoft Threat Protection の概要</span><span class="sxs-lookup"><span data-stu-id="1c101-177">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="1c101-178">Microsoft Threat Protection を有効にする</span><span class="sxs-lookup"><span data-stu-id="1c101-178">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
- [<span data-ttu-id="1c101-179">Microsoft Defender ATP の概要</span><span class="sxs-lookup"><span data-stu-id="1c101-179">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="1c101-180">Office 365 ATP の概要</span><span class="sxs-lookup"><span data-stu-id="1c101-180">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="1c101-181">Microsoft Cloud App Security の概要</span><span class="sxs-lookup"><span data-stu-id="1c101-181">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="1c101-182">Azure ATP の概要</span><span class="sxs-lookup"><span data-stu-id="1c101-182">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
