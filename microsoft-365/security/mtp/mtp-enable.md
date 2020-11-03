---
title: Microsoft 365 セキュリティセンターで Microsoft 365 Defender をオンにする
description: Microsoft 365 Defender を有効にし、セキュリティインシデントと応答の統合を開始する方法について説明します。
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
ms.openlocfilehash: b5bb99ed4b8cee7ea920679e20f69c7a0e002d26
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843638"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="874fe-104">Microsoft 365 Defender をオンにする</span><span class="sxs-lookup"><span data-stu-id="874fe-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="874fe-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="874fe-105">**Applies to:**</span></span>
- <span data-ttu-id="874fe-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="874fe-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="874fe-107">[Microsoft 365 Defender](microsoft-threat-protection.md) では、エンドポイントの microsoft defender、microsoft Defender for Office 365、Microsoft Cloud App Security、および id の microsoft defender で主要な機能を統合することにより、インシデント対応プロセスを統一しています。</span><span class="sxs-lookup"><span data-stu-id="874fe-107">[Microsoft 365 Defender](microsoft-threat-protection.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="874fe-108">この統合されたエクスペリエンスにより、Microsoft 365 セキュリティ センターでアクセスできる強力な機能が追加されました。</span><span class="sxs-lookup"><span data-stu-id="874fe-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="874fe-109">Microsoft 365 Defender は、必要なアクセス許可を持つ対象ユーザーが Microsoft 365 セキュリティセンターにアクセスしたときに自動的にオンになります。</span><span class="sxs-lookup"><span data-stu-id="874fe-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="874fe-110">この記事を読むと、さまざまな前提条件と、Microsoft 365 Defender のプロビジョニング方法を理解できます。</span><span class="sxs-lookup"><span data-stu-id="874fe-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="874fe-111">ライセンスの利用資格と必要なアクセス許可を確認する</span><span class="sxs-lookup"><span data-stu-id="874fe-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="874fe-112">Microsoft 365 セキュリティ製品のライセンスでは、通常、追加のライセンス費用を必要とせずに microsoft 365 セキュリティセンターの Microsoft 365 Defender を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="874fe-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="874fe-113">マイクロソフトは、サポートされているすべてのサービスへのアクセスを提供する、Microsoft 365 E5、E5 セキュリティ、A5、または A5 セキュリティライセンスまたはライセンスの有効な組み合わせを取得することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="874fe-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="874fe-114">ライセンスの詳細については、 [ライセンス要件を参照して](prerequisites.md#licensing-requirements)ください。</span><span class="sxs-lookup"><span data-stu-id="874fe-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="874fe-115">役割を確認する</span><span class="sxs-lookup"><span data-stu-id="874fe-115">Check your role</span></span>
<span data-ttu-id="874fe-116">Microsoft 365 Defender を有効にするには、Azure Active Directory の **グローバル管理者** または **セキュリティ管理者** である必要があります。</span><span class="sxs-lookup"><span data-stu-id="874fe-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="874fe-117">Azure AD でのロールの表示</span><span class="sxs-lookup"><span data-stu-id="874fe-117">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="874fe-118">サポートされるサービス</span><span class="sxs-lookup"><span data-stu-id="874fe-118">Supported services</span></span>
<span data-ttu-id="874fe-119">Microsoft 365 Defender は、既に展開したさまざまなサポートされているサービスからデータを集約します。</span><span class="sxs-lookup"><span data-stu-id="874fe-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="874fe-120">データを一元的に処理および保存して、新しい洞察を識別し、集中管理された応答ワークフローを実現できるようにします。</span><span class="sxs-lookup"><span data-stu-id="874fe-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="874fe-121">これは、統合サービスに関連付けられている既存の展開、設定、またはデータに影響を与えることなく実行されます。</span><span class="sxs-lookup"><span data-stu-id="874fe-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="874fe-122">最適な保護を得るために、Microsoft 365 Defender を最適化するには、ネットワーク上に該当するすべてのサポートされているサービスを展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="874fe-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="874fe-123">詳細については、「 [サポートされるサービスの展開について](deploy-supported-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="874fe-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="before-starting-the-service"></a><span data-ttu-id="874fe-124">サービスを開始する前に</span><span class="sxs-lookup"><span data-stu-id="874fe-124">Before starting the service</span></span>
<span data-ttu-id="874fe-125">サービスを有効にする前に、Microsoft 365 セキュリティセンター ( [security.microsoft.com](https://security.microsoft.com)) で、[ **インシデント** ]、[ **アクションセンター** ]、または [ナビゲーション] ウィンドウから **探し** ているものを選択すると、[microsoft 365 Defender 設定] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="874fe-125">Before you turn on the service, the Microsoft 365 security center ( [security.microsoft.com](https://security.microsoft.com)) shows the Microsoft 365 Defender settings page when you select **Incidents** , **Action center** , or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="874fe-126">これらのナビゲーション項目は、Microsoft 365 Defender を使用する資格がない場合は表示されません。</span><span class="sxs-lookup"><span data-stu-id="874fe-126">These navigation items are not shown if you are not eligible to use Microsoft 365 Defender.</span></span>

<span data-ttu-id="874fe-127">![Microsoft 365 Defender が microsoft ](../../media/mtp-enable/mtp-settings.png)
 *365 セキュリティセンターの Microsoft 365 defender 設定* で有効になっていない場合に表示される microsoft 365 defender 設定ページのイメージ</span><span class="sxs-lookup"><span data-stu-id="874fe-127">![Image of the Microsoft 365 Defender settings page shown if Microsoft 365 Defender has not been turned on](../../media/mtp-enable/mtp-settings.png)
*Microsoft 365 Defender settings in Microsoft 365 security center*</span></span>

## <a name="starting-the-service"></a><span data-ttu-id="874fe-128">サービスを開始する</span><span class="sxs-lookup"><span data-stu-id="874fe-128">Starting the service</span></span>
<span data-ttu-id="874fe-129">Microsoft 365 Defender をオンにするには、[ **microsoft 365 defender をオン** にする] を選択して変更を適用します。</span><span class="sxs-lookup"><span data-stu-id="874fe-129">To turn on Microsoft 365 Defender, simply select **Turn on Microsoft 365 Defender** and apply the change.</span></span> <span data-ttu-id="874fe-130">このオプションにアクセスするには、ナビゲーションウィンドウで [ **設定** ] ( [security.microsoft.com/settings](https://security.microsoft.com/settings)) を選択してから、[ **microsoft 365 Defender** ] を選択する方法もあります。</span><span class="sxs-lookup"><span data-stu-id="874fe-130">You can also access this option by selecting **Settings** ( [security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and then selecting **Microsoft 365 Defender**.</span></span>

>[!NOTE]
><span data-ttu-id="874fe-131">ナビゲーションウィンドウに **設定** が表示されない場合や、ページにアクセスできなかった場合は、アクセス許可とライセンスを確認してください。</span><span class="sxs-lookup"><span data-stu-id="874fe-131">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="data-center-location"></a><span data-ttu-id="874fe-132">データセンターの場所</span><span class="sxs-lookup"><span data-stu-id="874fe-132">Data center location</span></span>
<span data-ttu-id="874fe-133">Microsoft 365 Defender は、 [エンドポイントとして Microsoft Defender で使用されて](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)いるのと同じ場所にデータを格納し、処理します。</span><span class="sxs-lookup"><span data-stu-id="874fe-133">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="874fe-134">エンドポイントに Microsoft Defender がインストールされていない場合は、アクティブな Microsoft 365 セキュリティサービスの場所に基づいて、新しいデータセンターの場所が自動的に選択されます。</span><span class="sxs-lookup"><span data-stu-id="874fe-134">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="874fe-135">選択したデータセンターの場所が画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="874fe-135">The selected data center location is shown in the screen.</span></span> 

<span data-ttu-id="874fe-136">Microsoft 365 セキュリティセンターの microsoft サポートに連絡して、異なるデータセンターの場所に Microsoft 365 Defender をプロビジョニングする方法については、[ **ヘルプが必要ですか?** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="874fe-136">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span> 

>[!NOTE]
><span data-ttu-id="874fe-137">エンドポイントの Microsoft Defender は、Azure Defender \* を使用してオンにした場合に、欧州連合 (EU) のデータセンターで自動的にプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="874fe-137">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender\*.</span></span> <span data-ttu-id="874fe-138">Microsoft 365 Defender は、この方法でエンドポイント用の Defender をプロビジョニングしたお客様に対して、同じ EU データセンターで自動的にプロビジョニングを行います。</span><span class="sxs-lookup"><span data-stu-id="874fe-138">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner.</span></span> 

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="874fe-139">サービスが有効になっていることを確認する</span><span class="sxs-lookup"><span data-stu-id="874fe-139">Confirm that the service is on</span></span>
<span data-ttu-id="874fe-140">サービスがプロビジョニングされると、次の機能が追加されます。</span><span class="sxs-lookup"><span data-stu-id="874fe-140">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="874fe-141">イベント管理</span><span class="sxs-lookup"><span data-stu-id="874fe-141">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="874fe-142">[自動化された調査と対応](mtp-autoir.md)を管理するアクション センター</span><span class="sxs-lookup"><span data-stu-id="874fe-142">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="874fe-143">[高度な](advanced-hunting-overview.md) 検索機能</span><span class="sxs-lookup"><span data-stu-id="874fe-143">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="874fe-144">![Microsoft 365 セキュリティセンターのナビゲーションウィンドウのイメージ Microsoft 365 Defender 機能 ](../../media/mtp-enable/mtp-on.png)
 *microsoft 365 セキュリティセンターとインシデント管理およびその他の Microsoft 365 Defender 機能*</span><span class="sxs-lookup"><span data-stu-id="874fe-144">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="874fe-145">Id データの Microsoft Defender を取得する</span><span class="sxs-lookup"><span data-stu-id="874fe-145">Getting Microsoft Defender for Identity data</span></span>
<span data-ttu-id="874fe-146">Microsoft 365 Defender を使用して Id データの Microsoft Defender を共有するには、Id 統合のための microsoft Cloud App Security と Microsoft Defender が有効になっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="874fe-146">To share Microsoft Defender for Identity data with Microsoft 365 Defender, ensure that Microsoft Cloud App Security and Microsoft Defender for Identity integration is turned on.</span></span> [<span data-ttu-id="874fe-147">この統合に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="874fe-147">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-365-defender"></a><span data-ttu-id="874fe-148">Microsoft 365 Defender をオフにする</span><span class="sxs-lookup"><span data-stu-id="874fe-148">Turn off Microsoft 365 Defender</span></span>
<span data-ttu-id="874fe-149">Microsoft 365 defender の使用を停止するには、microsoft 365 セキュリティセンターの [ **設定** ] の [microsoft  >  **365 Defender**  >  **オプトイン/オプトアウト** ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="874fe-149">To stop using Microsoft 365 Defender, go to **Settings** > **Microsoft 365 Defender** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="874fe-150">選択解除 **Microsoft 365 Defender をオンに** して、変更を適用します。</span><span class="sxs-lookup"><span data-stu-id="874fe-150">Unselect **Turn on Microsoft 365 Defender** and apply the changes.</span></span>

<span data-ttu-id="874fe-151">対応する機能は、Microsoft 365 セキュリティセンターから削除されます。</span><span class="sxs-lookup"><span data-stu-id="874fe-151">Corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="874fe-152">サポートを利用する</span><span class="sxs-lookup"><span data-stu-id="874fe-152">Get assistance</span></span>

<span data-ttu-id="874fe-153">Microsoft 365 Defender を有効にする方法に関してよく寄せられる質問への回答を得るには、 [FAQ を参照](mtp-enable-faq.md)してください。</span><span class="sxs-lookup"><span data-stu-id="874fe-153">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](mtp-enable-faq.md).</span></span>

<span data-ttu-id="874fe-154">Microsoft サポートスタッフは、テナントのサービスおよび関連するリソースのプロビジョニングまたはプロビジョニング解除に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="874fe-154">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="874fe-155">詳細については、「Microsoft 365 セキュリティセンターで **ヘルプが必要ですか?** 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="874fe-155">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="874fe-156">サポートに連絡する際は、Microsoft 365 Defender にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="874fe-156">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="874fe-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="874fe-157">Related topics</span></span>

- [<span data-ttu-id="874fe-158">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="874fe-158">Frequently asked questions</span></span>](mtp-enable-faq.md)
- [<span data-ttu-id="874fe-159">ライセンス要件およびその他の前提条件</span><span class="sxs-lookup"><span data-stu-id="874fe-159">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="874fe-160">サポートされるサービスを展開する</span><span class="sxs-lookup"><span data-stu-id="874fe-160">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="874fe-161">Microsoft 365 Defender の概要</span><span class="sxs-lookup"><span data-stu-id="874fe-161">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="874fe-162">エンドポイントの Microsoft Defender の概要</span><span class="sxs-lookup"><span data-stu-id="874fe-162">Microsoft Defender for Endpoint overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="874fe-163">Office 365 の Defender の概要</span><span class="sxs-lookup"><span data-stu-id="874fe-163">Defender for Office 365 overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="874fe-164">Microsoft Cloud App Security の概要</span><span class="sxs-lookup"><span data-stu-id="874fe-164">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="874fe-165">Id の Microsoft Defender の概要</span><span class="sxs-lookup"><span data-stu-id="874fe-165">Microsoft Defender for Identity overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="874fe-166">エンドポイントのデータストレージの Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="874fe-166">Microsoft Defender for Endpoint data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
