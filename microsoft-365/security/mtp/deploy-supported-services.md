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
ms.openlocfilehash: b19907517f94cc8b6dbf041cccf56f1d8e232f2f
ms.sourcegitcommit: 0df099d2e1028bbba8b6371dc5fcd021dddc902b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/03/2020
ms.locfileid: "42374207"
---
# <a name="deploy-supported-services"></a><span data-ttu-id="815e5-104">サポートされているサービスを展開する</span><span class="sxs-lookup"><span data-stu-id="815e5-104">Deploy supported services</span></span>

<span data-ttu-id="815e5-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="815e5-105">**Applies to:**</span></span>
- <span data-ttu-id="815e5-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="815e5-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="815e5-107">[Microsoft の脅威保護](microsoft-threat-protection.md)では、さまざまな microsoft セキュリティサービスが統合され、高度な攻撃に対する一元的な検出、防止、調査の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="815e5-107">[Microsoft Threat Protection](microsoft-threat-protection.md) integrates various Microsoft security services to provide centralized detection, prevention, and investigation capabilities against sophisticated attacks.</span></span> <span data-ttu-id="815e5-108">この記事では、サポートされるサービス、ライセンス要件、1つ以上のサービスの展開に関連する利点と制限事項、およびそれらを個別に完全に展開する方法へのリンクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="815e5-108">This article describes the supported services, their licensing requirements, the advantages and limitations associated with deploying one or more services, and links to how you can fully deploy them individually.</span></span>

## <a name="supported-services"></a><span data-ttu-id="815e5-109">サポートされるサービス</span><span class="sxs-lookup"><span data-stu-id="815e5-109">Supported services</span></span>
<span data-ttu-id="815e5-110">[Microsoft 365 E5、E5 セキュリティ、a5、または A5 セキュリティ、またはライセンスの有効な組み合わせ](prerequisites.md#licensing-requirements)により、次のサポートされているサービスへのアクセスが可能になり、microsoft 365 セキュリティセンターで Microsoft の脅威保護を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="815e5-110">A [Microsoft 365 E5, E5 Security, A5, or A5 Security or a valid combination of licenses](prerequisites.md#licensing-requirements) provides access to the following supported services and entitles you to use Microsoft Threat Protection in Microsoft 365 security center.</span></span>

| <span data-ttu-id="815e5-111">サポートされるサービス</span><span class="sxs-lookup"><span data-stu-id="815e5-111">Supported service</span></span> | <span data-ttu-id="815e5-112">説明</span><span class="sxs-lookup"><span data-stu-id="815e5-112">Description</span></span> |
| ------ | ------ |
| <span data-ttu-id="815e5-113">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="815e5-113">Microsoft Defender ATP</span></span> | <span data-ttu-id="815e5-114">強力な動作センサー、クラウド分析、脅威インテリジェンスに基づいて構築されたエンドポイント保護スイート</span><span class="sxs-lookup"><span data-stu-id="815e5-114">Endpoint protection suite built around powerful behavioral sensors, cloud analytics, and threat intelligence</span></span> |
| <span data-ttu-id="815e5-115">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="815e5-115">Office 365 ATP</span></span> | <span data-ttu-id="815e5-116">Office 365 でのアプリとデータの高度な保護 (電子メールやその他のコラボレーションツールを含む)</span><span class="sxs-lookup"><span data-stu-id="815e5-116">Advanced protection for your apps and data in Office 365, including email and other collaboration tools</span></span> |
| <span data-ttu-id="815e5-117">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="815e5-117">Azure ATP</span></span> | <span data-ttu-id="815e5-118">高度な脅威、侵害された id、および悪意のある内部者からの保護された Active Directory シグナルを使用した保護</span><span class="sxs-lookup"><span data-stu-id="815e5-118">Safeguard against advanced threats, compromised identities, and malicious insiders using correlated Active Directory signals</span></span> |
| <span data-ttu-id="815e5-119">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="815e5-119">Microsoft Cloud App Security</span></span> | <span data-ttu-id="815e5-120">Microsoft およびサードパーティのクラウドサービスにわたって脅威を識別し、combats ます。</span><span class="sxs-lookup"><span data-stu-id="815e5-120">Identifies and combats cyberthreats across your Microsoft and third-party cloud services</span></span> |

## <a name="deployed-services-and-functionality"></a><span data-ttu-id="815e5-121">展開されたサービスと機能</span><span class="sxs-lookup"><span data-stu-id="815e5-121">Deployed services and functionality</span></span>
<span data-ttu-id="815e5-122">Microsoft の脅威保護では、より多くのサポートされるサービスを展開することにより、可視性、相互関係、および修復が向上します。</span><span class="sxs-lookup"><span data-stu-id="815e5-122">Microsoft Threat Protection provides better visibility, correlation, and remediation as you deploy more supported services.</span></span>

### <a name="benefits-of-full-deployment"></a><span data-ttu-id="815e5-123">完全な展開の利点</span><span class="sxs-lookup"><span data-stu-id="815e5-123">Benefits of full deployment</span></span>
<span data-ttu-id="815e5-124">Microsoft の脅威保護の完全なメリットを得るために、サポートされているすべてのサービスを展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="815e5-124">To get the complete benefits of Microsoft Threat Protection, we recommend deploying all supported services.</span></span> <span data-ttu-id="815e5-125">完全な展開の主な利点は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="815e5-125">Here are some of the key benefits of full deployment:</span></span>
- <span data-ttu-id="815e5-126">インシデントは、利用可能なすべてのセンサーおよびサービス固有の分析機能からのアラートとイベント信号に基づいて識別され、関連しています。</span><span class="sxs-lookup"><span data-stu-id="815e5-126">Incidents are identified and correlated based on alerts and event signals from all available sensors and service-specific analysis capabilities</span></span>
- <span data-ttu-id="815e5-127">自動化された調査と修復 (AIR) のプレイブックは、デバイス、メールボックス、ユーザーアカウントなどのさまざまなエンティティの種類に適用されます。</span><span class="sxs-lookup"><span data-stu-id="815e5-127">Automated investigation and remediation (AIR) playbooks apply across various entity types, including devices, mailboxes, and user accounts</span></span>
- <span data-ttu-id="815e5-128">デバイス、メールボックス、およびその他のエンティティのイベントおよびエンティティデータについて、より詳細な検索スキーマを照会することができます。</span><span class="sxs-lookup"><span data-stu-id="815e5-128">A more comprehensive advanced hunting schema can be queried for event and entity data from devices, mailboxes, and other entities</span></span>

### <a name="limited-deployment-scenarios"></a><span data-ttu-id="815e5-129">限定的な展開シナリオ</span><span class="sxs-lookup"><span data-stu-id="815e5-129">Limited deployment scenarios</span></span>
<span data-ttu-id="815e5-130">展開するサポートされているサービスごとに、非常に豊富な未加工の信号と、相関情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="815e5-130">Each supported service that you deploy provides an extremely rich set of raw signals as well as correlated information.</span></span> <span data-ttu-id="815e5-131">制限のある展開では、Microsoft の脅威保護機能がオフになることはありませんが、エンドポイント間で包括的な可視性を提供する機能、アプリ、データ、および id が影響を受けることはありません。</span><span class="sxs-lookup"><span data-stu-id="815e5-131">While limited deployment doesn’t cause Microsoft Threat Protection functionality to turn off, its ability to provide comprehensive visibility across your endpoints, apps, data, and identities is affected.</span></span> <span data-ttu-id="815e5-132">同時に、すべての修復機能は、展開したサービスで管理できるエンティティにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="815e5-132">At the same time, any remediation capabilities only apply to entities that can be managed by the services you’ve deployed.</span></span>

<span data-ttu-id="815e5-133">次の表に、サポートされている各サービスが追加データを提供する方法、データを関連付けることによってさらに詳細な情報を得る方法、および改善と応答の機能を示します。</span><span class="sxs-lookup"><span data-stu-id="815e5-133">The table below lists how each supported service provides additional data, opportunities to obtain additional insight by correlating the data, and better remediation and response capabilities.</span></span>

| <span data-ttu-id="815e5-134">サービス</span><span class="sxs-lookup"><span data-stu-id="815e5-134">Service</span></span> | <span data-ttu-id="815e5-135">データ (& 関連付けられる情報)</span><span class="sxs-lookup"><span data-stu-id="815e5-135">Data (signals & correlated info)</span></span> | <span data-ttu-id="815e5-136">修復 & 応答の範囲</span><span class="sxs-lookup"><span data-stu-id="815e5-136">Remediation & response scope</span></span> |
| ------ | ------ | ------ |
| <span data-ttu-id="815e5-137">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="815e5-137">Microsoft Defender ATP</span></span> | <span data-ttu-id="815e5-138">-エンドポイントの状態と生のイベント</span><span class="sxs-lookup"><span data-stu-id="815e5-138">- Endpoint states and raw events</span></span><br /><span data-ttu-id="815e5-139">-ウイルス対策、EDR、攻撃対象領域の削減を含むエンドポイントの検出と通知</span><span class="sxs-lookup"><span data-stu-id="815e5-139">- Endpoint detections and alerts, including antivirus, EDR, attack surface reduction</span></span><br /><span data-ttu-id="815e5-140">-エンドポイントで監視されたファイルやその他のエンティティに関する情報</span><span class="sxs-lookup"><span data-stu-id="815e5-140">- Info on files and other entities observed on endpoints</span></span> | <span data-ttu-id="815e5-141">エンドポイント</span><span class="sxs-lookup"><span data-stu-id="815e5-141">Endpoints</span></span> |
| <span data-ttu-id="815e5-142">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="815e5-142">Office 365 ATP</span></span> | <span data-ttu-id="815e5-143">-メールとメールボックスの状態および生のイベント</span><span class="sxs-lookup"><span data-stu-id="815e5-143">- Mail and mailbox states and raw events</span></span><br /><span data-ttu-id="815e5-144">-電子メール、添付ファイル、およびリンクの検出</span><span class="sxs-lookup"><span data-stu-id="815e5-144">- Email, attachment, and link detections</span></span> | <span data-ttu-id="815e5-145">-メールボックス</span><span class="sxs-lookup"><span data-stu-id="815e5-145">- Mailboxes</span></span><br /><span data-ttu-id="815e5-146">-Office 365 アカウント</span><span class="sxs-lookup"><span data-stu-id="815e5-146">- Office 365 accounts</span></span> |
| <span data-ttu-id="815e5-147">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="815e5-147">Azure ATP</span></span> | <span data-ttu-id="815e5-148">-Active Directory シグナル (認証イベントを含む)</span><span class="sxs-lookup"><span data-stu-id="815e5-148">- Active Directory signals, including authentication events</span></span><br /><span data-ttu-id="815e5-149">-Id 関連の動作の検出</span><span class="sxs-lookup"><span data-stu-id="815e5-149">- Identity-related behavioral detections</span></span> | <span data-ttu-id="815e5-150">ID</span><span class="sxs-lookup"><span data-stu-id="815e5-150">Identities</span></span> |
| <span data-ttu-id="815e5-151">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="815e5-151">Microsoft Cloud App Security</span></span> | <span data-ttu-id="815e5-152">-承認されていないクラウドアプリ & サービスの検出 (シャドウ IT)</span><span class="sxs-lookup"><span data-stu-id="815e5-152">- Detection of unsanctioned cloud apps & services (shadow IT)</span></span><br /><span data-ttu-id="815e5-153">-クラウドアプリへのデータの公開</span><span class="sxs-lookup"><span data-stu-id="815e5-153">- Exposure of data to cloud apps</span></span><br /><span data-ttu-id="815e5-154">-脅威アクティビティに関連するクラウドアプリ</span><span class="sxs-lookup"><span data-stu-id="815e5-154">- Threat activity associated cloud apps</span></span> | <span data-ttu-id="815e5-155">クラウド アプリ</span><span class="sxs-lookup"><span data-stu-id="815e5-155">Cloud apps</span></span> |

## <a name="deploy-the-services"></a><span data-ttu-id="815e5-156">サービスを展開する</span><span class="sxs-lookup"><span data-stu-id="815e5-156">Deploy the services</span></span>
<span data-ttu-id="815e5-157">通常、各サービスを展開するには、テナントに対するプロビジョニングと、いくつかの初期構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="815e5-157">Deploying each service typically requires provisioning to your tenant and some initial configuration.</span></span> <span data-ttu-id="815e5-158">これらの各サービスの展開方法については、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="815e5-158">See the following table to understand how each of these services are deployed.</span></span>

| <span data-ttu-id="815e5-159">サービス</span><span class="sxs-lookup"><span data-stu-id="815e5-159">Service</span></span> | <span data-ttu-id="815e5-160">プロビジョニング手順</span><span class="sxs-lookup"><span data-stu-id="815e5-160">Provisioning instructions</span></span> | <span data-ttu-id="815e5-161">初期構成</span><span class="sxs-lookup"><span data-stu-id="815e5-161">Initial configuration</span></span> |
| ------ | ------ | ------ |
| <span data-ttu-id="815e5-162">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="815e5-162">Microsoft Defender ATP</span></span> | [<span data-ttu-id="815e5-163">ライセンスのプロビジョニングを検証し、Microsoft Defender ATP のセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="815e5-163">Validate licensing provisioning and complete set up for Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/licensing) | <span data-ttu-id="815e5-164">*プロビジョニングの手順を参照してください。*</span><span class="sxs-lookup"><span data-stu-id="815e5-164">*See provisioning instructions*</span></span> |
| <span data-ttu-id="815e5-165">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="815e5-165">Office 365 ATP</span></span> | <span data-ttu-id="815e5-166">*なし。 Office 365 でプロビジョニングされます。*</span><span class="sxs-lookup"><span data-stu-id="815e5-166">*None, provisioned with Office 365*</span></span> | [<span data-ttu-id="815e5-167">ATP ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="815e5-167">Configure ATP policies</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| <span data-ttu-id="815e5-168">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="815e5-168">Azure ATP</span></span> | [<span data-ttu-id="815e5-169">クイックスタート: Azure ATP インスタンスを作成する</span><span class="sxs-lookup"><span data-stu-id="815e5-169">Quickstart: Create your Azure ATP instance</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | <span data-ttu-id="815e5-170">*プロビジョニングの手順を参照してください。*</span><span class="sxs-lookup"><span data-stu-id="815e5-170">*See provisioning instructions*</span></span> |
| <span data-ttu-id="815e5-171">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="815e5-171">Microsoft Cloud App Security</span></span> | <span data-ttu-id="815e5-172">*なし*</span><span class="sxs-lookup"><span data-stu-id="815e5-172">*None*</span></span> | [<span data-ttu-id="815e5-173">クイックスタート: Microsoft Cloud App Security を使い始める</span><span class="sxs-lookup"><span data-stu-id="815e5-173">Quickstart: Get started with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

<span data-ttu-id="815e5-174">サポートされているサービスを展開したら、 [Microsoft の脅威保護を有効](mtp-enable.md)にします。</span><span class="sxs-lookup"><span data-stu-id="815e5-174">Once you’ve deployed the supported services, [turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="815e5-175">関連項目</span><span class="sxs-lookup"><span data-stu-id="815e5-175">Related topics</span></span>

- [<span data-ttu-id="815e5-176">Microsoft Threat Protection の概要</span><span class="sxs-lookup"><span data-stu-id="815e5-176">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="815e5-177">Microsoft Threat Protection を有効にする</span><span class="sxs-lookup"><span data-stu-id="815e5-177">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
- [<span data-ttu-id="815e5-178">Microsoft Defender ATP の概要</span><span class="sxs-lookup"><span data-stu-id="815e5-178">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="815e5-179">Office 365 ATP の概要</span><span class="sxs-lookup"><span data-stu-id="815e5-179">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="815e5-180">Microsoft Cloud App Security の概要</span><span class="sxs-lookup"><span data-stu-id="815e5-180">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="815e5-181">Azure ATP の概要</span><span class="sxs-lookup"><span data-stu-id="815e5-181">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
