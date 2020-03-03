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
ms.openlocfilehash: 73c4c9864713432d318b0b3cec9fbaf395deff45
ms.sourcegitcommit: 0df099d2e1028bbba8b6371dc5fcd021dddc902b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/03/2020
ms.locfileid: "42374148"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="efdfb-104">Microsoft Threat Protection を有効にする</span><span class="sxs-lookup"><span data-stu-id="efdfb-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="efdfb-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="efdfb-105">**Applies to:**</span></span>
- <span data-ttu-id="efdfb-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="efdfb-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="efdfb-107">Microsoft Threat Protection は、Microsoft Defender Advanced Threat Protection (ATP)、Office 365 ATP、Microsoft Cloud App Security、および Azure ATP の主要機能を統合することで、インシデント対応プロセスを統合します。</span><span class="sxs-lookup"><span data-stu-id="efdfb-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="efdfb-108">この統合されたエクスペリエンスにより、Microsoft 365 セキュリティ センターでアクセスできる強力な機能が追加されました。</span><span class="sxs-lookup"><span data-stu-id="efdfb-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="efdfb-109">最適な保護を実現し、Microsoft の脅威保護を最適化するには、ネットワークにすべての該当するサポートされているサービスを展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="efdfb-109">To get the best protection and optimize Microsoft Threat Protection, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="efdfb-110">詳細については、「[サポートされるサービスの展開について](deploy-supported-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efdfb-110">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="efdfb-111">ライセンスの利用資格と必要なアクセス許可を確認する</span><span class="sxs-lookup"><span data-stu-id="efdfb-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="efdfb-112">Microsoft 365 E5、E5 セキュリティ、A5、または A5 セキュリティライセンス、あるいはライセンスの有効な組み合わせは、サポートされるサービスへのアクセスを提供し、Microsoft 365 セキュリティセンターで Microsoft の脅威保護を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="efdfb-112">A Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses provides access to supported services and entitles you to use Microsoft Threat Protection in Microsoft 365 security center.</span></span>

<span data-ttu-id="efdfb-113">ライセンスの詳細については、[ライセンス要件を参照して](prerequisites.md#licensing-requirements)ください。</span><span class="sxs-lookup"><span data-stu-id="efdfb-113">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="efdfb-114">役割を確認する</span><span class="sxs-lookup"><span data-stu-id="efdfb-114">Check your role</span></span>
<span data-ttu-id="efdfb-115">Microsoft の脅威保護を有効にするには、Azure Active Directory の**グローバル管理者**または**セキュリティ管理者**である必要があります。</span><span class="sxs-lookup"><span data-stu-id="efdfb-115">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft Threat Protection.</span></span> [<span data-ttu-id="efdfb-116">Azure AD でのロールの表示</span><span class="sxs-lookup"><span data-stu-id="efdfb-116">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="start-using-the-service"></a><span data-ttu-id="efdfb-117">サービスの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="efdfb-117">Start using the service</span></span>
<span data-ttu-id="efdfb-118">Microsoft の脅威保護は、さまざまな統合サービスからのデータを集約します。</span><span class="sxs-lookup"><span data-stu-id="efdfb-118">Microsoft Threat Protection aggregates data from the various integrated services.</span></span> <span data-ttu-id="efdfb-119">データを一元的に処理および保存して、新しい洞察を識別し、集中管理された応答ワークフローを実現できるようにします。</span><span class="sxs-lookup"><span data-stu-id="efdfb-119">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span>

<span data-ttu-id="efdfb-120">サービスを有効にする前に、「Microsoft 365 セキュリティセンター ([security.microsoft.com](https://security.microsoft.com))」では、[**インシデント**]、[**アクションセンター**]、または\*\*\*\* [ナビゲーション] ウィンドウから選択したときに microsoft Threat Protection のウェルカムページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="efdfb-120">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft Threat Protection welcome page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="efdfb-121">これらのナビゲーションオプションは、Microsoft の脅威保護を使用する資格がない場合は表示されません。</span><span class="sxs-lookup"><span data-stu-id="efdfb-121">These navigation options are not shown if you are not eligible to use Microsoft Threat Protection.</span></span>

<span data-ttu-id="efdfb-122">![Microsoft](../../media/mtp-welcome.png)
*365 セキュリティセンター*の microsoft threat protection のウェルカムページに microsoft threat protection が有効になっていない場合に表示される、microsoft threat protection のウェルカムページの画像</span><span class="sxs-lookup"><span data-stu-id="efdfb-122">![Image of the Microsoft Threat Protection welcome page shown if Microsoft Threat Protection has not been turned on](../../media/mtp-welcome.png)
*Microsoft Threat Protection welcome page in Microsoft 365 security center*</span></span>

<span data-ttu-id="efdfb-123">Microsoft の脅威保護を有効にするには、単にウェルカムページからプロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="efdfb-123">To turn on Microsoft Threat Protection, simply complete the process from the welcome page.</span></span> <span data-ttu-id="efdfb-124">ナビゲーションウィンドウで [**設定**] ([security.microsoft.com/settings](https://security.microsoft.com/settings)) にアクセスし、[ **microsoft threat protection**] を選択することによって、microsoft の脅威保護を有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="efdfb-124">You can also turn on Microsoft Threat Protection by accessing **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and selecting **Microsoft Threat Protection**.</span></span>

>[!NOTE]
><span data-ttu-id="efdfb-125">ナビゲーションウィンドウに**設定**が表示されない場合や、ページにアクセスできなかった場合は、アクセス許可とライセンスを確認してください。</span><span class="sxs-lookup"><span data-stu-id="efdfb-125">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="select-data-center-location"></a><span data-ttu-id="efdfb-126">データセンターの場所を選択する</span><span class="sxs-lookup"><span data-stu-id="efdfb-126">Select data center location</span></span>
<span data-ttu-id="efdfb-127">Microsoft Defender ATP が組織にプロビジョニングされている場合、データは、[Microsoft Defender ATP データ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)用に選択した同じデータ センターの場所に保存および処理されます。</span><span class="sxs-lookup"><span data-stu-id="efdfb-127">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="efdfb-128">Microsoft Defender ATP がない場合は、Microsoft Threat Protection 専用の新しいデータ センターの場所を選択するよう求められます。</span><span class="sxs-lookup"><span data-stu-id="efdfb-128">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> 

<span data-ttu-id="efdfb-129">サービス間でデータを共有し、集約する前に、同意を得る必要があります。</span><span class="sxs-lookup"><span data-stu-id="efdfb-129">You need to provide consent before data is shared between services and aggregated.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="efdfb-130">サービスが有効になっていることを確認する</span><span class="sxs-lookup"><span data-stu-id="efdfb-130">Confirm that the service is on</span></span>
<span data-ttu-id="efdfb-131">サービスがプロビジョニングされると、次の機能が追加されます。</span><span class="sxs-lookup"><span data-stu-id="efdfb-131">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="efdfb-132">イベント管理</span><span class="sxs-lookup"><span data-stu-id="efdfb-132">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="efdfb-133">[自動化された調査と対応](mtp-autoir.md)を管理するアクション センター</span><span class="sxs-lookup"><span data-stu-id="efdfb-133">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="efdfb-134">[高度な](advanced-hunting-overview.md)検索機能</span><span class="sxs-lookup"><span data-stu-id="efdfb-134">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="efdfb-135">![Microsoft 365 セキュリティセンターのナビゲーションウィンドウと microsoft の脅威保護機能](../../media/mtp-on.png)
のイメージ microsoft*365 セキュリティセンターとインシデント管理およびその他の microsoft の脅威保護機能*</span><span class="sxs-lookup"><span data-stu-id="efdfb-135">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="efdfb-136">Azure ATP データを取得する</span><span class="sxs-lookup"><span data-stu-id="efdfb-136">Getting Azure ATP data</span></span>
<span data-ttu-id="efdfb-137">Azure ATP データを Microsoft Threat Protection と共有するには、Microsoft Cloud App Security と Azure ATP の統合を有効にします。</span><span class="sxs-lookup"><span data-stu-id="efdfb-137">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="efdfb-138">この統合に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="efdfb-138">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="efdfb-139">Microsoft Threat Protection を無効にする</span><span class="sxs-lookup"><span data-stu-id="efdfb-139">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="efdfb-140">Microsoft Threat Protection を使用しない場合、Microsoft 365 セキュリティ センターの [**設定**]  >  [**Microsoft Threat Protection**]  >  [**オプトイン/オプトアウト**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="efdfb-140">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="efdfb-141">[**Microsoft Threat Protection を有効にする**] の選択を解除し、変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="efdfb-141">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="efdfb-142">対応する機能は、Microsoft 365 セキュリティセンターから削除されます。</span><span class="sxs-lookup"><span data-stu-id="efdfb-142">Corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="efdfb-143">サポートを利用する</span><span class="sxs-lookup"><span data-stu-id="efdfb-143">Get assistance</span></span>

<span data-ttu-id="efdfb-144">Microsoft サポートスタッフは、テナントのサービスおよび関連するリソースのプロビジョニングまたはプロビジョニング解除に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="efdfb-144">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="efdfb-145">詳細については、「Microsoft 365 セキュリティセンターで**ヘルプが必要ですか?** 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efdfb-145">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="efdfb-146">サポートに連絡するときは、「Microsoft Threat Protection」をお伝えください。</span><span class="sxs-lookup"><span data-stu-id="efdfb-146">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="efdfb-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="efdfb-147">Related topics</span></span>

- [<span data-ttu-id="efdfb-148">Microsoft Threat Protection の概要</span><span class="sxs-lookup"><span data-stu-id="efdfb-148">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="efdfb-149">ライセンス要件およびその他の前提条件</span><span class="sxs-lookup"><span data-stu-id="efdfb-149">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="efdfb-150">サポートされているサービスを展開する</span><span class="sxs-lookup"><span data-stu-id="efdfb-150">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="efdfb-151">Microsoft Defender ATP の概要</span><span class="sxs-lookup"><span data-stu-id="efdfb-151">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="efdfb-152">Office 365 ATP の概要</span><span class="sxs-lookup"><span data-stu-id="efdfb-152">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="efdfb-153">Microsoft Cloud App Security の概要</span><span class="sxs-lookup"><span data-stu-id="efdfb-153">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="efdfb-154">Azure ATP の概要</span><span class="sxs-lookup"><span data-stu-id="efdfb-154">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="efdfb-155">Microsoft Defender ATP のデーター ストレージ</span><span class="sxs-lookup"><span data-stu-id="efdfb-155">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
