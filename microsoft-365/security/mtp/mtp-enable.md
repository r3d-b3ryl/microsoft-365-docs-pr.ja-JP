---
title: Microsoft 365 セキュリティ センターで Microsoft Threat Protection を有効にする
description: Microsoft Threat Protection を有効にし、セキュリティ インシデントと応答の統合を開始する方法について説明します。
keywords: 作業の開始、MTP の有効化、Microsoft Threat Protection、M365、セキュリティ、データの場所、必要なアクセス許可、ライセンスの資格情報のページ
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
ms.openlocfilehash: 73f76dee8a59229138f906e593a84220c7f70aee
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42235216"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="07267-104">Microsoft Threat Protection を有効にする</span><span class="sxs-lookup"><span data-stu-id="07267-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="07267-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="07267-105">**Applies to:**</span></span>
- <span data-ttu-id="07267-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="07267-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="07267-107">Microsoft Threat Protection は、Microsoft Defender Advanced Threat Protection (ATP)、Office 365 ATP、Microsoft Cloud App Security、および Azure ATP の主要機能を統合することで、インシデント対応プロセスを統合します。</span><span class="sxs-lookup"><span data-stu-id="07267-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="07267-108">この統合されたエクスペリエンスにより、Microsoft 365 セキュリティ センターでアクセスできる強力な機能が追加されました。</span><span class="sxs-lookup"><span data-stu-id="07267-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="07267-109">ライセンスの利用資格と必要なアクセス許可を確認する</span><span class="sxs-lookup"><span data-stu-id="07267-109">Check license eligibility and required permissions</span></span>
<span data-ttu-id="07267-110">Microsoft 365 E5、Microsoft 365 E5 セキュリティ、またはそれと同等のライセンスの組み合わせを使用しているお客様は、Microsoft の脅威保護を使用できます。</span><span class="sxs-lookup"><span data-stu-id="07267-110">Customers with Microsoft 365 E5, Microsoft 365 E5 Security, or an equivalent combination of licenses can use Microsoft Threat Protection.</span></span> <span data-ttu-id="07267-111">詳細については、[ライセンス要件を参照してください](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="07267-111">For more information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

<span data-ttu-id="07267-112">Microsoft の脅威保護を有効にするには、 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)の**グローバル管理者**または**セキュリティ管理者**である必要があります。</span><span class="sxs-lookup"><span data-stu-id="07267-112">You must be a **global administrator** or a **security administrator** in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to turn on Microsoft Threat Protection.</span></span>

## <a name="start-using-the-service"></a><span data-ttu-id="07267-113">サービスの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="07267-113">Start using the service</span></span>
<span data-ttu-id="07267-114">Microsoft の脅威保護は、さまざまな統合サービスからのデータを集約します。</span><span class="sxs-lookup"><span data-stu-id="07267-114">Microsoft Threat Protection aggregates data from the various integrated services.</span></span> <span data-ttu-id="07267-115">データを一元的に処理および保存して、新しい洞察を識別し、集中管理された応答ワークフローを実現できるようにします。</span><span class="sxs-lookup"><span data-stu-id="07267-115">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span>

<span data-ttu-id="07267-116">サービスを有効にする前に、Microsoft 365 セキュリティセンター ([security.microsoft.com](https://security.microsoft.com)) では、ナビゲーションウィンドウの [**インシデント**] および [**アクションセンター** ] オプションが表示されません。</span><span class="sxs-lookup"><span data-stu-id="07267-116">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) doesn't show the **Incidents** and the **Action center** options in the navigation pane.</span></span>

<span data-ttu-id="07267-117">![Microsoft 365 セキュリティセンターのナビゲーションウィンドウのイメージ microsoft の脅威保護](../../media/mtp-off.png)
機能のない microsoft*365 セキュリティセンターと microsoft の脅威保護がオフになっている*</span><span class="sxs-lookup"><span data-stu-id="07267-117">![Image of Microsoft 365 security center navigation pane without Microsoft Threat Protection features](../../media/mtp-off.png)
*Microsoft 365 security center with Microsoft Threat Protection turned off*</span></span>

<span data-ttu-id="07267-118">Microsoft の脅威保護を有効にするには、ナビゲーションウィンドウで [**設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="07267-118">To turn on Microsoft Threat Protection, select **Settings** in the navigation pane.</span></span> <span data-ttu-id="07267-119">[\*\*[設定] ページ](https://security.microsoft.com/settings)\*\* で、[ **Microsoft Threat Protection** > **オプトイン/オプトアウト**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="07267-119">In the **[Settings page](https://security.microsoft.com/settings)**, go to **Microsoft Threat Protection** > **Opt-in / Opt-out**.</span></span>

>[!NOTE]
><span data-ttu-id="07267-120">ナビゲーションウィンドウに**設定**が表示されない場合や、ページにアクセスできなかった場合は、アクセス許可とライセンスを確認してください。</span><span class="sxs-lookup"><span data-stu-id="07267-120">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="select-data-center-location"></a><span data-ttu-id="07267-121">データセンターの場所を選択する</span><span class="sxs-lookup"><span data-stu-id="07267-121">Select data center location</span></span>
<span data-ttu-id="07267-122">Microsoft Defender ATP が組織にプロビジョニングされている場合、データは、[Microsoft Defender ATP データ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)用に選択した同じデータ センターの場所に保存および処理されます。</span><span class="sxs-lookup"><span data-stu-id="07267-122">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="07267-123">Microsoft Defender ATP がない場合は、Microsoft Threat Protection 専用の新しいデータ センターの場所を選択するよう求められます。</span><span class="sxs-lookup"><span data-stu-id="07267-123">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> 

<span data-ttu-id="07267-124">サービス間でデータを共有し、集約する前に、同意を得る必要があります。</span><span class="sxs-lookup"><span data-stu-id="07267-124">You need to provide consent before data is shared between services and aggregated.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="07267-125">サービスが有効になっていることを確認する</span><span class="sxs-lookup"><span data-stu-id="07267-125">Confirm that the service is on</span></span>
<span data-ttu-id="07267-126">サービスがプロビジョニングされると、次の機能が追加されます。</span><span class="sxs-lookup"><span data-stu-id="07267-126">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="07267-127">イベント管理</span><span class="sxs-lookup"><span data-stu-id="07267-127">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="07267-128">[自動化された調査と対応](mtp-autoir.md)を管理するアクション センター</span><span class="sxs-lookup"><span data-stu-id="07267-128">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="07267-129">既存の [**捜索**] ページへの[高度な捜索](advanced-hunting-overview.md)機能</span><span class="sxs-lookup"><span data-stu-id="07267-129">[Advanced hunting](advanced-hunting-overview.md) capabilities to the existing **Hunting** page</span></span>

<span data-ttu-id="07267-130">![Microsoft 365 セキュリティセンターのナビゲーションウィンドウと microsoft の脅威保護機能](../../media/mtp-on.png)
のイメージ microsoft*365 セキュリティセンターとインシデント管理およびその他の microsoft の脅威保護機能*</span><span class="sxs-lookup"><span data-stu-id="07267-130">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="07267-131">Azure ATP データを取得する</span><span class="sxs-lookup"><span data-stu-id="07267-131">Getting Azure ATP data</span></span>
<span data-ttu-id="07267-132">Azure ATP データを Microsoft Threat Protection と共有するには、Microsoft Cloud App Security と Azure ATP の統合を有効にします。</span><span class="sxs-lookup"><span data-stu-id="07267-132">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="07267-133">この統合に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="07267-133">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="07267-134">Microsoft Threat Protection を無効にする</span><span class="sxs-lookup"><span data-stu-id="07267-134">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="07267-135">Microsoft Threat Protection を使用しない場合、Microsoft 365 セキュリティ センターの [**設定**]  >  [**Microsoft Threat Protection**]  >  [**オプトイン/オプトアウト**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="07267-135">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="07267-136">[**Microsoft Threat Protection を有効にする**] の選択を解除し、変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="07267-136">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="07267-137">データは完全に削除され、対応する機能は Microsoft 365 セキュリティセンターから削除されます。</span><span class="sxs-lookup"><span data-stu-id="07267-137">Data will be permanently deleted and corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="07267-138">サポートを利用する</span><span class="sxs-lookup"><span data-stu-id="07267-138">Get assistance</span></span>

<span data-ttu-id="07267-139">Microsoft サポートスタッフは、テナントのサービスおよび関連するリソースのプロビジョニングまたはプロビジョニング解除に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="07267-139">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="07267-140">詳細については、「Microsoft 365 セキュリティセンターで**ヘルプが必要ですか?** 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07267-140">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="07267-141">サポートに連絡するときは、「Microsoft Threat Protection」をお伝えください。</span><span class="sxs-lookup"><span data-stu-id="07267-141">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="07267-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="07267-142">Related topics</span></span>

- [<span data-ttu-id="07267-143">Microsoft Threat Protection の概要</span><span class="sxs-lookup"><span data-stu-id="07267-143">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="07267-144">ライセンス要件およびその他の前提条件</span><span class="sxs-lookup"><span data-stu-id="07267-144">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="07267-145">Microsoft Defender ATP の概要</span><span class="sxs-lookup"><span data-stu-id="07267-145">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="07267-146">Office 365 ATP の概要</span><span class="sxs-lookup"><span data-stu-id="07267-146">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="07267-147">Microsoft Cloud App Security の概要</span><span class="sxs-lookup"><span data-stu-id="07267-147">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="07267-148">Azure ATP の概要</span><span class="sxs-lookup"><span data-stu-id="07267-148">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="07267-149">Microsoft Defender ATP のデーター ストレージ</span><span class="sxs-lookup"><span data-stu-id="07267-149">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
