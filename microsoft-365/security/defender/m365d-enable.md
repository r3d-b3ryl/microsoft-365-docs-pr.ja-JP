---
title: Microsoft 365 セキュリティ センターで Microsoft 365 Defender を有効にする
description: Microsoft 365 Defender を有効にして、セキュリティ インシデントと対応の統合を開始する方法について説明します。
keywords: 開始する、MTP、Microsoft Threat Protection、M365、セキュリティ、データの場所、必要なアクセス許可、ライセンスの適格性、設定ページを有効にする
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 399da6fd54145f73ac72fdac04e8d25148f76507
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186751"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="c451c-104">Microsoft 365 Defender を有効にする</span><span class="sxs-lookup"><span data-stu-id="c451c-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c451c-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="c451c-105">**Applies to:**</span></span>
- <span data-ttu-id="c451c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c451c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="c451c-107">[Microsoft 365 Defender](microsoft-365-defender.md) は、Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Cloud App Security、Microsoft Defender for Identity を統合することで、インシデント対応プロセスを統合します。</span><span class="sxs-lookup"><span data-stu-id="c451c-107">[Microsoft 365 Defender](microsoft-365-defender.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="c451c-108">この統合されたエクスペリエンスにより、Microsoft 365 セキュリティ センターでアクセスできる強力な機能が追加されました。</span><span class="sxs-lookup"><span data-stu-id="c451c-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="c451c-109">必要なアクセス許可を持つ対象ユーザーが Microsoft 365 セキュリティ センターにアクセスすると、Microsoft 365 Defender が自動的にオンになります。</span><span class="sxs-lookup"><span data-stu-id="c451c-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="c451c-110">この記事では、さまざまな前提条件と Microsoft 365 Defender のプロビジョニング方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c451c-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="c451c-111">ライセンスの適格性と必要なアクセス許可を確認する</span><span class="sxs-lookup"><span data-stu-id="c451c-111">Check license eligibility and required permissions</span></span>

<span data-ttu-id="c451c-112">Microsoft 365 セキュリティ製品のライセンスでは、通常、追加のライセンスコストなしで Microsoft 365 セキュリティ センターで Microsoft 365 Defender を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c451c-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="c451c-113">Microsoft 365 E5、E5 Security、A5、または A5 セキュリティ ライセンス、またはサポートされているサービスへのアクセスを提供するライセンスの有効な組み合わせを取得することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c451c-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="c451c-114">ライセンスの詳細については、「ライセンス [要件」を参照してください](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="c451c-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="c451c-115">役割を確認する</span><span class="sxs-lookup"><span data-stu-id="c451c-115">Check your role</span></span>

<span data-ttu-id="c451c-116">Microsoft 365 Defenderを有効 **にするには**、Azure Active Directory のグローバル管理者またはセキュリティ管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c451c-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="c451c-117">Azure AD でロールを表示AD</span><span class="sxs-lookup"><span data-stu-id="c451c-117">View your roles in Azure AD</span></span>](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="c451c-118">サポートされているサービス</span><span class="sxs-lookup"><span data-stu-id="c451c-118">Supported services</span></span>

<span data-ttu-id="c451c-119">Microsoft 365 Defender は、既に展開したさまざまなサポートされているサービスのデータを集計します。</span><span class="sxs-lookup"><span data-stu-id="c451c-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="c451c-120">データを一元的に処理して保存し、新しい分析情報を特定し、一元的な応答ワークフローを可能にします。</span><span class="sxs-lookup"><span data-stu-id="c451c-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="c451c-121">これは、統合サービスに関連付けられている既存の展開、設定、またはデータに影響を与えることなく行います。</span><span class="sxs-lookup"><span data-stu-id="c451c-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="c451c-122">Microsoft 365 Defender の最適な保護と最適化を行う場合は、該当するサポート対象のすべてのサービスをネットワークに展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c451c-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="c451c-123">詳細については、「サポート [されているサービスの展開」を参照してください](deploy-supported-services.md)。</span><span class="sxs-lookup"><span data-stu-id="c451c-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="onboard-to-the-service"></a><span data-ttu-id="c451c-124">サービスにオンボードする</span><span class="sxs-lookup"><span data-stu-id="c451c-124">Onboard to the service</span></span>
<span data-ttu-id="c451c-125">Microsoft 365 Defender へのオンボーディングは簡単です。</span><span class="sxs-lookup"><span data-stu-id="c451c-125">Onboarding to Microsoft 365 Defender is simple.</span></span> <span data-ttu-id="c451c-126">ナビゲーション メニューから、[エンドポイント] セクションの下のアイテム (インシデント、ハンティング、アクション センター、脅威分析など) を選択してオンボーディング プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="c451c-126">From the navigation menu, select any item under the Endpoints section, such as Incidents, Hunting, Action center, or Threat analytics to initiate the onboarding process.</span></span> 

### <a name="data-center-location"></a><span data-ttu-id="c451c-127">データ センターの場所</span><span class="sxs-lookup"><span data-stu-id="c451c-127">Data center location</span></span>

<span data-ttu-id="c451c-128">Microsoft 365 Defender は、Microsoft Defender for Endpoint で使用されるのと同じ場所にデータを格納 [して処理します](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)。</span><span class="sxs-lookup"><span data-stu-id="c451c-128">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="c451c-129">Microsoft Defender for Endpoint を使用しない場合は、アクティブな Microsoft 365 セキュリティ サービスの場所に基づいて、新しいデータ センターの場所が自動的に選択されます。</span><span class="sxs-lookup"><span data-stu-id="c451c-129">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="c451c-130">選択したデータ センターの場所が画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c451c-130">The selected data center location is shown in the screen.</span></span>

<span data-ttu-id="c451c-131">Microsoft  365 セキュリティ センターで [ヘルプが必要ですか] を選択して、Microsoft 365 Defender を別のデータ センターの場所にプロビジョニングする方法について Microsoft サポートに問い合わせします。</span><span class="sxs-lookup"><span data-stu-id="c451c-131">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span>

> [!NOTE]
> <span data-ttu-id="c451c-132">Microsoft Defender for Endpoint は、Azure Defender を使用してオンにした場合、EU (EU) データ センターで自動的にプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="c451c-132">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="c451c-133">Microsoft 365 Defender は、この方法で Defender for Endpoint をプロビジョニングしたお客様に対して、同じ EU データ センターで自動的にプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="c451c-133">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="c451c-134">サービスが有効になっていることを確認する</span><span class="sxs-lookup"><span data-stu-id="c451c-134">Confirm that the service is on</span></span>

<span data-ttu-id="c451c-135">サービスがプロビジョニングされると、次の機能が追加されます。</span><span class="sxs-lookup"><span data-stu-id="c451c-135">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="c451c-136">イベント管理</span><span class="sxs-lookup"><span data-stu-id="c451c-136">Incidents management</span></span>](incidents-overview.md)
- [<span data-ttu-id="c451c-137">アラート キュー</span><span class="sxs-lookup"><span data-stu-id="c451c-137">Alerts queue</span></span>](investigate-alerts.md)
- <span data-ttu-id="c451c-138">[自動化された調査と対応](m365d-autoir.md)を管理するアクション センター</span><span class="sxs-lookup"><span data-stu-id="c451c-138">An action center for managing [automated investigation and response](m365d-autoir.md)</span></span>
- <span data-ttu-id="c451c-139">[高度なハンティング](advanced-hunting-overview.md) 機能</span><span class="sxs-lookup"><span data-stu-id="c451c-139">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>
- <span data-ttu-id="c451c-140">脅威の分析</span><span class="sxs-lookup"><span data-stu-id="c451c-140">Threat analytics</span></span>

<span data-ttu-id="c451c-141">![Microsoft 365 Defender を備えた Microsoft 365 セキュリティ センター ナビゲーション ウィンドウのイメージインシデント管理などの Microsoft 365 Defender 機能を備えた ](../../media/mtp-enable/mtp-on.png)
 *Microsoft 365* セキュリティ センター</span><span class="sxs-lookup"><span data-stu-id="c451c-141">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="c451c-142">Id データの Microsoft Defender の取得</span><span class="sxs-lookup"><span data-stu-id="c451c-142">Getting Microsoft Defender for Identity data</span></span> 
<span data-ttu-id="c451c-143">Microsoft Cloud App Security との統合を有効にするには、少なくとも 1 回は Microsoft Cloud App Security にログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c451c-143">To enable the integration with Microsoft Cloud App Security, you'll need to login to the Microsoft Cloud App Security at least once.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="c451c-144">サポートを利用する</span><span class="sxs-lookup"><span data-stu-id="c451c-144">Get assistance</span></span>

<span data-ttu-id="c451c-145">Microsoft 365 Defender のオンに関する最も一般的な質問に対する回答を取得するには、FAQ [を参照してください](m365d-enable-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="c451c-145">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](m365d-enable-faq.md).</span></span>

<span data-ttu-id="c451c-146">Microsoft サポート スタッフは、テナントのサービスおよび関連リソースのプロビジョニングまたはプロビジョニング解除を支援できます。</span><span class="sxs-lookup"><span data-stu-id="c451c-146">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="c451c-147">サポートについては、Microsoft 365 **セキュリティ** センターで [ヘルプが必要か] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c451c-147">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="c451c-148">サポートに連絡する場合は、Microsoft 365 Defender について説明します。</span><span class="sxs-lookup"><span data-stu-id="c451c-148">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c451c-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="c451c-149">Related topics</span></span>

- [<span data-ttu-id="c451c-150">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="c451c-150">Frequently asked questions</span></span>](m365d-enable-faq.md)
- [<span data-ttu-id="c451c-151">ライセンス要件およびその他の前提条件</span><span class="sxs-lookup"><span data-stu-id="c451c-151">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="c451c-152">サポートされているサービスを展開する</span><span class="sxs-lookup"><span data-stu-id="c451c-152">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="c451c-153">Microsoft 365 Defender の概要</span><span class="sxs-lookup"><span data-stu-id="c451c-153">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="c451c-154">Microsoft Defender for Endpoint の概要</span><span class="sxs-lookup"><span data-stu-id="c451c-154">Microsoft Defender for Endpoint overview</span></span>](../defender-endpoint/microsoft-defender-endpoint.md)
- [<span data-ttu-id="c451c-155">Defender for Office 365 の概要</span><span class="sxs-lookup"><span data-stu-id="c451c-155">Defender for Office 365 overview</span></span>](../defender-365-security/defender-for-office-365.md)
- [<span data-ttu-id="c451c-156">Microsoft Cloud App Security の概要</span><span class="sxs-lookup"><span data-stu-id="c451c-156">Microsoft Cloud App Security overview</span></span>](/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="c451c-157">Microsoft Defender for Identity の概要</span><span class="sxs-lookup"><span data-stu-id="c451c-157">Microsoft Defender for Identity overview</span></span>](/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="c451c-158">Microsoft Defender for Endpoint data storage</span><span class="sxs-lookup"><span data-stu-id="c451c-158">Microsoft Defender for Endpoint data storage</span></span>](../defender-endpoint/data-storage-privacy.md)
