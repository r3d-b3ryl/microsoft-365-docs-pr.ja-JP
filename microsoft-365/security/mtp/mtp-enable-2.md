---
title: Microsoft 365 セキュリティ センターで Microsoft Threat Protection を有効にする
description: Microsoft Threat Protection を有効にし、セキュリティ インシデントと応答の統合を開始する方法について説明します。
keywords: 作業の開始、MTP の有効化、Microsoft Threat Protection、M365、セキュリティ、データの場所、必要なアクセス許可、ライセンスの資格を取得します。
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
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
ms.openlocfilehash: a024a261d216342cebfc3c28fcd159389ea422ec
ms.sourcegitcommit: a7ce1e9041d27aa85b825368887f41ea8e823541
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2020
ms.locfileid: "41165539"
---
# <a name="turn-on-microsoft-threat-protection-test-copy"></a><span data-ttu-id="5c4f0-104">Microsoft の脅威保護テストコピーを有効にする</span><span class="sxs-lookup"><span data-stu-id="5c4f0-104">Turn on Microsoft Threat Protection TEST COPY</span></span>

<span data-ttu-id="5c4f0-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="5c4f0-105">**Applies to:**</span></span>
- <span data-ttu-id="5c4f0-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="5c4f0-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="5c4f0-107">Microsoft Threat Protection は、Microsoft Defender Advanced Threat Protection (ATP)、Office 365 ATP、Microsoft Cloud App Security、および Azure ATP の主要機能を統合することで、インシデント対応プロセスを統合します。</span><span class="sxs-lookup"><span data-stu-id="5c4f0-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="5c4f0-108">この統合されたエクスペリエンスにより、Microsoft 365 セキュリティ センターでアクセスできる強力な機能が追加されました。</span><span class="sxs-lookup"><span data-stu-id="5c4f0-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="5c4f0-109">ライセンスの利用資格と必要なアクセス許可を確認する</span><span class="sxs-lookup"><span data-stu-id="5c4f0-109">Check license eligibility and required permissions</span></span>
<span data-ttu-id="5c4f0-110">Microsoft 365 E5 または同等のライセンスをお持ちのお客様は、Microsoft Threat Protection を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5c4f0-110">Customers with a Microsoft 365 E5 or equivalent license can use Microsoft Threat Protection.</span></span> <span data-ttu-id="5c4f0-111">詳細については、[ライセンス要件を参照してください](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="5c4f0-111">For more information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

 <span data-ttu-id="5c4f0-112">Microsoft の脅威保護を有効にするには、 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)の**全体管理**者または**セキュリティ管理者**である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c4f0-112">To be able to turn on Microsoft Threat Protection, you need to be a **global administrator** or a **security administrator** in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).</span></span>

## <a name="start-using-the-service"></a><span data-ttu-id="5c4f0-113">サービスの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="5c4f0-113">Start using the service</span></span>
<span data-ttu-id="5c4f0-114">Microsoft Threat Protection サービスを有効にすると、さまざまな統合サービスからのデータが集約されます。</span><span class="sxs-lookup"><span data-stu-id="5c4f0-114">Turning on the Microsoft Threat Protection service aggregates data from the various integrated services.</span></span> <span data-ttu-id="5c4f0-115">データは一元的に処理および保存され、新しい分析情報が特定され、一元化された応答ワークフローが可能になります。</span><span class="sxs-lookup"><span data-stu-id="5c4f0-115">The data will be processed and stored centrally to identify new insights and to make centralized response workflows possible.</span></span>

<span data-ttu-id="5c4f0-116">サービスを有効にする前に、Microsoft 365 セキュリティセンター ([security.microsoft.com](https://security.microsoft.com)) では、[**インシデント**] および [**アクションセンター** ] オプションがメニューに表示されません。</span><span class="sxs-lookup"><span data-stu-id="5c4f0-116">Before you turn the service on, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) does not show the **Incidents** and the **Action center** options on the menu.</span></span>

<span data-ttu-id="5c4f0-117">![Microsoft Threat Protection 機能を使用しない Microsoft 365 セキュリティ センター メニューの画像](../images/mtp-off.png)
*Microsoft Threat Protection を無効にした Microsoft 365 セキュリティ センター*</span><span class="sxs-lookup"><span data-stu-id="5c4f0-117">![Image of Microsoft 365 security center menu without Microsoft Threat Protection features](../images/mtp-off.png)
*Microsoft 365 security center with Microsoft Threat Protection turned off*</span></span>

<span data-ttu-id="5c4f0-118">Microsoft Threat Protection サービスを有効にするには、Microsoft 365 セキュリティ センターの [**設定**]  >  [**Microsoft Threat Protection**]  >  [**オプトイン/オプトアウト**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="5c4f0-118">To turn the Microsoft Threat Protection service on, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span>

<span data-ttu-id="5c4f0-119">Microsoft Defender ATP が組織にプロビジョニングされている場合、データは、[Microsoft Defender ATP データ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)用に選択した同じデータ センターの場所に保存および処理されます。</span><span class="sxs-lookup"><span data-stu-id="5c4f0-119">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="5c4f0-120">Microsoft Defender ATP がない場合は、Microsoft Threat Protection 専用の新しいデータ センターの場所を選択するよう求められます。</span><span class="sxs-lookup"><span data-stu-id="5c4f0-120">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> <span data-ttu-id="5c4f0-121">データがサービス間で共有され、集計される前に、同意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c4f0-121">You will need to provide consent before data is shared between services and aggregated.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="5c4f0-122">サービスが有効になっていることを確認する</span><span class="sxs-lookup"><span data-stu-id="5c4f0-122">Confirm that the service is on</span></span>
<span data-ttu-id="5c4f0-123">サービスがプロビジョニングされると、次の機能が追加されます。</span><span class="sxs-lookup"><span data-stu-id="5c4f0-123">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="5c4f0-124">イベント管理</span><span class="sxs-lookup"><span data-stu-id="5c4f0-124">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="5c4f0-125">[自動化された調査と対応](mtp-autoir.md)を管理するアクション センター</span><span class="sxs-lookup"><span data-stu-id="5c4f0-125">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="5c4f0-126">既存の [**捜索**] ページへの[高度な捜索](advanced-hunting-overview.md)機能</span><span class="sxs-lookup"><span data-stu-id="5c4f0-126">[Advanced hunting](advanced-hunting-overview.md) capabilities to the existing **Hunting** page</span></span>

<span data-ttu-id="5c4f0-127">![Microsoft Threat Protection 機能を使用する Microsoft 365 セキュリティ センター メニューの画像](../images/mtp-on.png)
*インシデント管理およびその他の Microsoft Threat Protection 機能を備えた Microsoft 365 セキュリティ センター*</span><span class="sxs-lookup"><span data-stu-id="5c4f0-127">![Image of Microsoft 365 security center menu with Microsoft Threat Protection features](../images/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection features*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="5c4f0-128">Azure ATP データを取得する</span><span class="sxs-lookup"><span data-stu-id="5c4f0-128">Getting Azure ATP data</span></span>
<span data-ttu-id="5c4f0-129">Azure ATP データを Microsoft Threat Protection と共有するには、Microsoft Cloud App Security と Azure ATP の統合を有効にします。</span><span class="sxs-lookup"><span data-stu-id="5c4f0-129">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="5c4f0-130">この統合に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="5c4f0-130">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="5c4f0-131">Microsoft Threat Protection を無効にする</span><span class="sxs-lookup"><span data-stu-id="5c4f0-131">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="5c4f0-132">Microsoft Threat Protection を使用しない場合、Microsoft 365 セキュリティ センターの [**設定**]  >  [**Microsoft Threat Protection**]  >  [**オプトイン/オプトアウト**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="5c4f0-132">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="5c4f0-133">[**Microsoft Threat Protection を有効にする**] の選択を解除し、変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="5c4f0-133">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="5c4f0-134">データは完全に削除され、対応する機能は Microsoft 365 セキュリティセンターから削除されます。</span><span class="sxs-lookup"><span data-stu-id="5c4f0-134">Data will be permanently deleted and corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="5c4f0-135">サポートを利用する</span><span class="sxs-lookup"><span data-stu-id="5c4f0-135">Get assistance</span></span>

<span data-ttu-id="5c4f0-136">Microsoft のスタッフは、テナントのサービスおよび関連リソースのプロビジョニングまたはプロビジョニング解除を支援できます。</span><span class="sxs-lookup"><span data-stu-id="5c4f0-136">Microsoft staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="5c4f0-137">詳細については、「Microsoft 365 セキュリティセンターで**ヘルプが必要ですか?** 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c4f0-137">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="5c4f0-138">懸念事項を説明する際には、「Microsoft Threat Protection」をお伝えください。</span><span class="sxs-lookup"><span data-stu-id="5c4f0-138">When describing your concerns, mention "Microsoft Threat Protection".</span></span>

## <a name="related-topics"></a><span data-ttu-id="5c4f0-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c4f0-139">Related topics</span></span>

- [<span data-ttu-id="5c4f0-140">Microsoft Threat Protection の概要</span><span class="sxs-lookup"><span data-stu-id="5c4f0-140">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="5c4f0-141">ライセンス要件およびその他の前提条件</span><span class="sxs-lookup"><span data-stu-id="5c4f0-141">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="5c4f0-142">Microsoft Defender ATP の概要</span><span class="sxs-lookup"><span data-stu-id="5c4f0-142">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="5c4f0-143">Office 365 ATP の概要</span><span class="sxs-lookup"><span data-stu-id="5c4f0-143">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="5c4f0-144">Microsoft Cloud App Security の概要</span><span class="sxs-lookup"><span data-stu-id="5c4f0-144">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="5c4f0-145">Azure ATP の概要</span><span class="sxs-lookup"><span data-stu-id="5c4f0-145">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="5c4f0-146">Microsoft Defender ATP のデーター ストレージ</span><span class="sxs-lookup"><span data-stu-id="5c4f0-146">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
