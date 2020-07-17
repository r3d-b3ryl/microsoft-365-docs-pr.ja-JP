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
ms.openlocfilehash: b6ac30f7e32bbec80952ad4f2104032886b11503
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016345"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="09a94-104">Microsoft Threat Protection を有効にする</span><span class="sxs-lookup"><span data-stu-id="09a94-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="09a94-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="09a94-105">**Applies to:**</span></span>
- <span data-ttu-id="09a94-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="09a94-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="09a94-107">[Microsoft の脅威保護](microsoft-threat-protection.md)は、Microsoft Defender Advanced Threat PROTECTION (ATP)、OFFICE 365 ATP、Microsoft Cloud App Security、および Azure ATP 全体で主要な機能を統合することによって、インシデント対応プロセスを統一します。</span><span class="sxs-lookup"><span data-stu-id="09a94-107">[Microsoft Threat Protection](microsoft-threat-protection.md) unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="09a94-108">この統合されたエクスペリエンスにより、Microsoft 365 セキュリティ センターでアクセスできる強力な機能が追加されました。</span><span class="sxs-lookup"><span data-stu-id="09a94-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="09a94-109">必要なアクセス許可を持つ対象ユーザーが Microsoft 365 セキュリティセンターにアクセスすると、microsoft の脅威保護が自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="09a94-109">Microsoft Threat Protection automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="09a94-110">この記事では、さまざまな前提条件と、Microsoft の脅威の保護をプロビジョニングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="09a94-110">Read this article to understand various prerequisites and how Microsoft Threat Protection is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="09a94-111">ライセンスの利用資格と必要なアクセス許可を確認する</span><span class="sxs-lookup"><span data-stu-id="09a94-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="09a94-112">Microsoft 365 セキュリティ製品のライセンスでは、通常、追加のライセンス費用を必要とせずに microsoft 365 セキュリティセンターで Microsoft の脅威保護を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="09a94-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft Threat Protection in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="09a94-113">マイクロソフトは、サポートされているすべてのサービスへのアクセスを提供する、Microsoft 365 E5、E5 セキュリティ、A5、または A5 セキュリティライセンスまたはライセンスの有効な組み合わせを取得することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="09a94-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="09a94-114">ライセンスの詳細については、[ライセンス要件を参照して](prerequisites.md#licensing-requirements)ください。</span><span class="sxs-lookup"><span data-stu-id="09a94-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="09a94-115">役割を確認する</span><span class="sxs-lookup"><span data-stu-id="09a94-115">Check your role</span></span>
<span data-ttu-id="09a94-116">Microsoft の脅威保護を有効にするには、Azure Active Directory の**グローバル管理者**または**セキュリティ管理者**である必要があります。</span><span class="sxs-lookup"><span data-stu-id="09a94-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft Threat Protection.</span></span> [<span data-ttu-id="09a94-117">Azure AD でのロールの表示</span><span class="sxs-lookup"><span data-stu-id="09a94-117">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="09a94-118">サポートされるサービス</span><span class="sxs-lookup"><span data-stu-id="09a94-118">Supported services</span></span>
<span data-ttu-id="09a94-119">Microsoft の脅威保護は、既に展開したさまざまなサポートされているサービスからデータを集約します。</span><span class="sxs-lookup"><span data-stu-id="09a94-119">Microsoft Threat Protection aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="09a94-120">データを一元的に処理および保存して、新しい洞察を識別し、集中管理された応答ワークフローを実現できるようにします。</span><span class="sxs-lookup"><span data-stu-id="09a94-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="09a94-121">これは、統合サービスに関連付けられている既存の展開、設定、またはデータに影響を与えることなく実行されます。</span><span class="sxs-lookup"><span data-stu-id="09a94-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="09a94-122">最適な保護を実現し、Microsoft の脅威保護を最適化するには、ネットワークにすべての該当するサポートされているサービスを展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="09a94-122">To get the best protection and optimize Microsoft Threat Protection, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="09a94-123">詳細については、「[サポートされるサービスの展開について](deploy-supported-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09a94-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="before-starting-the-service"></a><span data-ttu-id="09a94-124">サービスを開始する前に</span><span class="sxs-lookup"><span data-stu-id="09a94-124">Before starting the service</span></span>
<span data-ttu-id="09a94-125">サービスを有効にする前に、Microsoft 365 セキュリティセンター ([security.microsoft.com](https://security.microsoft.com)) で、[**インシデント**]、[**アクションセンター**]、または [ナビゲーション] ウィンドウから**探し**ているものを選択すると、[microsoft Threat Protection の設定] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="09a94-125">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft Threat Protection settings page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="09a94-126">これらのナビゲーション項目は、Microsoft の脅威保護を使用する資格がない場合は表示されません。</span><span class="sxs-lookup"><span data-stu-id="09a94-126">These navigation items are not shown if you are not eligible to use Microsoft Threat Protection.</span></span>

<span data-ttu-id="09a94-127">![Microsoft ](../../media/mtp-enable/mtp-settings.png)
 *365 セキュリティセンターの*microsoft threat protection 設定で microsoft threat protection が有効になっていない場合に表示される [microsoft threat protection の設定] ページの画像</span><span class="sxs-lookup"><span data-stu-id="09a94-127">![Image of the Microsoft Threat Protection settings page shown if Microsoft Threat Protection has not been turned on](../../media/mtp-enable/mtp-settings.png)
*Microsoft Threat Protection settings in Microsoft 365 security center*</span></span>

## <a name="starting-the-service"></a><span data-ttu-id="09a94-128">サービスを開始する</span><span class="sxs-lookup"><span data-stu-id="09a94-128">Starting the service</span></span>
<span data-ttu-id="09a94-129">Microsoft の脅威保護を有効にするには、[ **microsoft の脅威保護を有効**にする] を選択して変更を適用します。</span><span class="sxs-lookup"><span data-stu-id="09a94-129">To turn on Microsoft Threat Protection, simply select **Turn on Microsoft Threat Protection** and apply the change.</span></span> <span data-ttu-id="09a94-130">このオプションにアクセスするには、ナビゲーションウィンドウで [**設定**] ([security.microsoft.com/settings](https://security.microsoft.com/settings)) を選択してから、[ **microsoft Threat Protection**] を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="09a94-130">You can also access this option by selecting **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and then selecting **Microsoft Threat Protection**.</span></span>

>[!NOTE]
><span data-ttu-id="09a94-131">ナビゲーションウィンドウに**設定**が表示されない場合や、ページにアクセスできなかった場合は、アクセス許可とライセンスを確認してください。</span><span class="sxs-lookup"><span data-stu-id="09a94-131">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="data-center-location"></a><span data-ttu-id="09a94-132">データセンターの場所</span><span class="sxs-lookup"><span data-stu-id="09a94-132">Data center location</span></span>
<span data-ttu-id="09a94-133">Microsoft の脅威保護は、 [Microsoft DEFENDER ATP で使用されて](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)いるのと同じ場所にデータを保存して処理します。</span><span class="sxs-lookup"><span data-stu-id="09a94-133">Microsoft Threat Protection will store and process data in the [same location used by Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="09a94-134">Microsoft Defender ATP を使用していない場合は、アクティブな Microsoft 365 セキュリティサービスの場所に基づいて、新しいデータセンターの場所が自動的に選択されます。</span><span class="sxs-lookup"><span data-stu-id="09a94-134">If you don't have Microsoft Defender ATP, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="09a94-135">選択したデータセンターの場所が画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="09a94-135">The selected data center location is shown in the screen.</span></span> 

<span data-ttu-id="09a94-136">Microsoft 365 セキュリティセンターの microsoft サポートに連絡して、別のデータセンターの場所に Microsoft の脅威保護をプロビジョニングする方法については、[**ヘルプが必要ですか?** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="09a94-136">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft Threat Protection in a different data center location.</span></span> 

>[!NOTE]
><span data-ttu-id="09a94-137">Microsoft Defender ATP は、Azure セキュリティセンターを使用してオンにした場合に、欧州連合 (EU) のデータセンターで自動的にプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="09a94-137">Microsoft Defender ATP automatically provisions in European Union (EU) data centers when turned on through Azure Security Center.</span></span> <span data-ttu-id="09a94-138">Microsoft の脅威保護は、Microsoft Defender ATP をこの方法でプロビジョニングしたお客様に対して、同じ EU データセンターで自動的にプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="09a94-138">Microsoft Threat Protection will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender ATP in this manner.</span></span> 

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="09a94-139">サービスが有効になっていることを確認する</span><span class="sxs-lookup"><span data-stu-id="09a94-139">Confirm that the service is on</span></span>
<span data-ttu-id="09a94-140">サービスがプロビジョニングされると、次の機能が追加されます。</span><span class="sxs-lookup"><span data-stu-id="09a94-140">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="09a94-141">イベント管理</span><span class="sxs-lookup"><span data-stu-id="09a94-141">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="09a94-142">[自動化された調査と対応](mtp-autoir.md)を管理するアクション センター</span><span class="sxs-lookup"><span data-stu-id="09a94-142">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="09a94-143">[高度な](advanced-hunting-overview.md)検索機能</span><span class="sxs-lookup"><span data-stu-id="09a94-143">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="09a94-144">![Microsoft 365 セキュリティセンターのナビゲーションウィンドウと Microsoft の脅威保護機能のイメージ microsoft ](../../media/mtp-enable/mtp-on.png)
 *365 セキュリティセンターとインシデント管理およびその他の Microsoft の脅威保護機能*</span><span class="sxs-lookup"><span data-stu-id="09a94-144">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="09a94-145">Azure ATP データを取得する</span><span class="sxs-lookup"><span data-stu-id="09a94-145">Getting Azure ATP data</span></span>
<span data-ttu-id="09a94-146">Azure ATP データを Microsoft Threat Protection と共有するには、Microsoft Cloud App Security と Azure ATP の統合を有効にします。</span><span class="sxs-lookup"><span data-stu-id="09a94-146">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="09a94-147">この統合に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="09a94-147">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="09a94-148">Microsoft Threat Protection を無効にする</span><span class="sxs-lookup"><span data-stu-id="09a94-148">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="09a94-149">Microsoft Threat Protection を使用しない場合、Microsoft 365 セキュリティ センターの [**設定**]  >  [**Microsoft Threat Protection**]  >  [**オプトイン/オプトアウト**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="09a94-149">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="09a94-150">選択解除**Microsoft の脅威保護を有効**にして変更を適用します。</span><span class="sxs-lookup"><span data-stu-id="09a94-150">Unselect **Turn on Microsoft Threat Protection** and apply the changes.</span></span>

<span data-ttu-id="09a94-151">対応する機能は、Microsoft 365 セキュリティセンターから削除されます。</span><span class="sxs-lookup"><span data-stu-id="09a94-151">Corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="09a94-152">サポートを利用する</span><span class="sxs-lookup"><span data-stu-id="09a94-152">Get assistance</span></span>

<span data-ttu-id="09a94-153">Microsoft の脅威保護を有効にすることに関してよく寄せられる質問への回答を得るには、 [FAQ を参照](mtp-enable-faq.md)してください。</span><span class="sxs-lookup"><span data-stu-id="09a94-153">To get answers to the most commonly asked questions about turning on Microsoft Threat Protection, [read the FAQ](mtp-enable-faq.md).</span></span>

<span data-ttu-id="09a94-154">Microsoft サポートスタッフは、テナントのサービスおよび関連するリソースのプロビジョニングまたはプロビジョニング解除に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="09a94-154">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="09a94-155">詳細については、「Microsoft 365 セキュリティセンターで**ヘルプが必要ですか?** 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09a94-155">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="09a94-156">サポートに連絡するときは、「Microsoft Threat Protection」をお伝えください。</span><span class="sxs-lookup"><span data-stu-id="09a94-156">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="09a94-157">関連トピック</span><span class="sxs-lookup"><span data-stu-id="09a94-157">Related topics</span></span>

- [<span data-ttu-id="09a94-158">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="09a94-158">Frequently asked questions</span></span>](mtp-enable-faq.md)
- [<span data-ttu-id="09a94-159">ライセンス要件およびその他の前提条件</span><span class="sxs-lookup"><span data-stu-id="09a94-159">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="09a94-160">サポートされるサービスを展開する</span><span class="sxs-lookup"><span data-stu-id="09a94-160">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="09a94-161">Microsoft Threat Protection の概要</span><span class="sxs-lookup"><span data-stu-id="09a94-161">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="09a94-162">Microsoft Defender ATP の概要</span><span class="sxs-lookup"><span data-stu-id="09a94-162">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="09a94-163">Office 365 ATP の概要</span><span class="sxs-lookup"><span data-stu-id="09a94-163">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="09a94-164">Microsoft Cloud App Security の概要</span><span class="sxs-lookup"><span data-stu-id="09a94-164">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="09a94-165">Azure ATP の概要</span><span class="sxs-lookup"><span data-stu-id="09a94-165">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="09a94-166">Microsoft Defender ATP のデーター ストレージ</span><span class="sxs-lookup"><span data-stu-id="09a94-166">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)