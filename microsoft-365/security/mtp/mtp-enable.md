---
title: Microsoft 365 セキュリティ センターで Microsoft 365 Defender を有効にする
description: Microsoft 365 Defender を有効にして、セキュリティ インシデントと対応の統合を開始する方法について説明します。
keywords: 開始, MTP を有効にする, Microsoft Threat Protection, M365, セキュリティ, データの場所, 必要なアクセス許可, ライセンスの利用資格, 設定ページ
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
ms.openlocfilehash: b052f70c1b618adef12c4f70c2b3fe55741697d5
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760508"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="08097-104">Microsoft 365 Defender を有効にする</span><span class="sxs-lookup"><span data-stu-id="08097-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="08097-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="08097-105">**Applies to:**</span></span>
- <span data-ttu-id="08097-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="08097-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="08097-107">[Microsoft 365 Defender](microsoft-threat-protection.md) は、Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Cloud App Security、および Microsoft Defender for Identity を統合することで、インシデント対応プロセスを統合します。</span><span class="sxs-lookup"><span data-stu-id="08097-107">[Microsoft 365 Defender](microsoft-threat-protection.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="08097-108">この統合されたエクスペリエンスにより、Microsoft 365 セキュリティ センターでアクセスできる強力な機能が追加されました。</span><span class="sxs-lookup"><span data-stu-id="08097-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="08097-109">必要なアクセス許可を持つ対象ユーザーが Microsoft 365 セキュリティ センターにアクセスすると、Microsoft 365 Defender が自動的にオンになります。</span><span class="sxs-lookup"><span data-stu-id="08097-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="08097-110">この記事では、さまざまな前提条件と Microsoft 365 Defender のプロビジョニング方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="08097-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="08097-111">ライセンスの利用資格と必要なアクセス許可を確認する</span><span class="sxs-lookup"><span data-stu-id="08097-111">Check license eligibility and required permissions</span></span>

<span data-ttu-id="08097-112">Microsoft 365 セキュリティ製品のライセンスは、通常、追加のライセンス コストなしで Microsoft 365 セキュリティ センターで Microsoft 365 Defender を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="08097-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="08097-113">Microsoft 365 E5、E5 Security、A5、または A5 Security ライセンスを取得するか、サポートされているサービスへのアクセスを提供するライセンスの有効な組み合わせを取得することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="08097-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="08097-114">ライセンスの詳細については、ライセンス [要件を参照してください](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="08097-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="08097-115">ロールを確認する</span><span class="sxs-lookup"><span data-stu-id="08097-115">Check your role</span></span>

<span data-ttu-id="08097-116">Microsoft 365 Defenderを **有効** にする場合は、Azure Active Directory のグローバル管理者またはセキュリティ管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="08097-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="08097-117">Azure AD でロールを表示する</span><span class="sxs-lookup"><span data-stu-id="08097-117">View your roles in Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="08097-118">サポートされているサービス</span><span class="sxs-lookup"><span data-stu-id="08097-118">Supported services</span></span>

<span data-ttu-id="08097-119">Microsoft 365 Defender は、既に展開済みのサポートされているさまざまなサービスからデータを集約します。</span><span class="sxs-lookup"><span data-stu-id="08097-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="08097-120">データを一元的に処理して保存し、新しい分析情報を特定し、一元的な応答ワークフローを可能にします。</span><span class="sxs-lookup"><span data-stu-id="08097-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="08097-121">これは、統合サービスに関連付けられている既存の展開、設定、またはデータに影響を与えることなく行います。</span><span class="sxs-lookup"><span data-stu-id="08097-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="08097-122">最適な保護を得て Microsoft 365 Defender を最適化するには、該当するサポート対象のすべてのサービスをネットワークに展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="08097-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="08097-123">詳細については、サポート [されているサービスの展開に関する記事を参照してください](deploy-supported-services.md)。</span><span class="sxs-lookup"><span data-stu-id="08097-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="before-starting-the-service"></a><span data-ttu-id="08097-124">サービスを開始する前に</span><span class="sxs-lookup"><span data-stu-id="08097-124">Before starting the service</span></span>

<span data-ttu-id="08097-125">サービスを有効にする前に、ナビゲーション ウィンドウから [インシデント]、[アクション センター]、または [ハンティング] を選択すると、Microsoft 365 セキュリティセンター[(security.microsoft.com)](https://security.microsoft.com)に Microsoft 365 Defender 設定ページが表示されます。 </span><span class="sxs-lookup"><span data-stu-id="08097-125">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft 365 Defender settings page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="08097-126">Microsoft 365 Defender を使用できない場合、これらのナビゲーション項目は表示されません。</span><span class="sxs-lookup"><span data-stu-id="08097-126">These navigation items are not shown if you are not eligible to use Microsoft 365 Defender.</span></span>

<span data-ttu-id="08097-127">![Microsoft 365 セキュリティ センターで Microsoft 365 Defender が Microsoft 365 Defender 設定をオンにしていない場合に表示される ](../../media/mtp-enable/mtp-settings.png)
 *Microsoft 365 Defender* 設定ページの画像</span><span class="sxs-lookup"><span data-stu-id="08097-127">![Image of the Microsoft 365 Defender settings page shown if Microsoft 365 Defender has not been turned on](../../media/mtp-enable/mtp-settings.png)
*Microsoft 365 Defender settings in Microsoft 365 security center*</span></span>

## <a name="starting-the-service"></a><span data-ttu-id="08097-128">サービスの開始</span><span class="sxs-lookup"><span data-stu-id="08097-128">Starting the service</span></span>

<span data-ttu-id="08097-129">Microsoft 365 Defender を有効にする場合は **、Microsoft 365 Defender** をオンにし、変更を適用します。</span><span class="sxs-lookup"><span data-stu-id="08097-129">To turn on Microsoft 365 Defender, simply select **Turn on Microsoft 365 Defender** and apply the change.</span></span> <span data-ttu-id="08097-130">このオプションにアクセスするには、ナビゲーション ウィンドウで [ **設定(** [security.microsoft.com/settings](https://security.microsoft.com/settings)) を選択し **、Microsoft 365 Defender** を選択します。</span><span class="sxs-lookup"><span data-stu-id="08097-130">You can also access this option by selecting **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and then selecting **Microsoft 365 Defender**.</span></span>

> [!NOTE]
> <span data-ttu-id="08097-131">ナビゲーション ウィンドウに [設定] **が表示** されていない場合や、ページにアクセスできなかった場合は、アクセス許可とライセンスを確認します。</span><span class="sxs-lookup"><span data-stu-id="08097-131">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="data-center-location"></a><span data-ttu-id="08097-132">データ センターの場所</span><span class="sxs-lookup"><span data-stu-id="08097-132">Data center location</span></span>

<span data-ttu-id="08097-133">Microsoft 365 Defender は、Microsoft Defender for Endpoint と同じ場所に [データを保存して処理します](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)。</span><span class="sxs-lookup"><span data-stu-id="08097-133">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="08097-134">Microsoft Defender for Endpoint をお持ちない場合は、アクティブな Microsoft 365 セキュリティ サービスの場所に基づいて、新しいデータ センターの場所が自動的に選択されます。</span><span class="sxs-lookup"><span data-stu-id="08097-134">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="08097-135">選択したデータ センターの場所が画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="08097-135">The selected data center location is shown in the screen.</span></span>

<span data-ttu-id="08097-136">Microsoft  365 セキュリティ センターで[ヘルプが必要ですか?] を選び、Microsoft サポートに連絡して、別のデータ センターの場所で Microsoft 365 Defender をプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="08097-136">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span>

> [!NOTE]
> <span data-ttu-id="08097-137">Microsoft Defender for Endpoint は、Azure Defender を通じて有効になっている場合、欧州連合 (EU) データ センターで自動的にプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="08097-137">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="08097-138">Microsoft 365 Defender は、この方法でエンドポイント用 Defender をプロビジョニングしたお客様に対して、同じ EU データ センターで自動的にプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="08097-138">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="08097-139">サービスが有効になっていることを確認する</span><span class="sxs-lookup"><span data-stu-id="08097-139">Confirm that the service is on</span></span>

<span data-ttu-id="08097-140">サービスがプロビジョニングされると、次の機能が追加されます。</span><span class="sxs-lookup"><span data-stu-id="08097-140">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="08097-141">イベント管理</span><span class="sxs-lookup"><span data-stu-id="08097-141">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="08097-142">[自動化された調査と対応](mtp-autoir.md)を管理するアクション センター</span><span class="sxs-lookup"><span data-stu-id="08097-142">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="08097-143">[高度な検索](advanced-hunting-overview.md) 機能</span><span class="sxs-lookup"><span data-stu-id="08097-143">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="08097-144">![インシデント管理などの Microsoft 365 Defender 機能を備えた Microsoft 365 Defender の Microsoft 365 セキュリティ センター機能を備えた ](../../media/mtp-enable/mtp-on.png)
 *Microsoft 365* セキュリティ センター ナビゲーション ウィンドウの画像</span><span class="sxs-lookup"><span data-stu-id="08097-144">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="08097-145">Id データ用の Microsoft Defender の取得</span><span class="sxs-lookup"><span data-stu-id="08097-145">Getting Microsoft Defender for Identity data</span></span>

<span data-ttu-id="08097-146">Id データ用の Microsoft Defender を Microsoft 365 Defender と共有するには、Microsoft Cloud App Security と Id 統合のための Microsoft Defender がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="08097-146">To share Microsoft Defender for Identity data with Microsoft 365 Defender, ensure that Microsoft Cloud App Security and Microsoft Defender for Identity integration is turned on.</span></span> <span data-ttu-id="08097-147">[この統合について詳しくは、次のリンクを参照してください](https://docs.microsoft.com/cloud-app-security/mdi-integration)。</span><span class="sxs-lookup"><span data-stu-id="08097-147">[Learn more about this integration](https://docs.microsoft.com/cloud-app-security/mdi-integration).</span></span>

## <a name="get-assistance"></a><span data-ttu-id="08097-148">サポートを利用する</span><span class="sxs-lookup"><span data-stu-id="08097-148">Get assistance</span></span>

<span data-ttu-id="08097-149">Microsoft 365 Defender をオンに関してよく寄せられる質問に対する回答については [、FAQ をお読みください](mtp-enable-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="08097-149">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](mtp-enable-faq.md).</span></span>

<span data-ttu-id="08097-150">Microsoft サポート スタッフは、テナントのサービスと関連リソースのプロビジョニングまたはプロビジョニング解除を支援できます。</span><span class="sxs-lookup"><span data-stu-id="08097-150">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="08097-151">サポートが必要な場合 **は、Microsoft** 365 セキュリティ センターで [サポートが必要ですか? ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="08097-151">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="08097-152">サポートに問い合わせがある場合は、Microsoft 365 Defender に言及してください。</span><span class="sxs-lookup"><span data-stu-id="08097-152">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="08097-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="08097-153">Related topics</span></span>

- [<span data-ttu-id="08097-154">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="08097-154">Frequently asked questions</span></span>](mtp-enable-faq.md)
- [<span data-ttu-id="08097-155">ライセンス要件およびその他の前提条件</span><span class="sxs-lookup"><span data-stu-id="08097-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="08097-156">サポートされているサービスを展開する</span><span class="sxs-lookup"><span data-stu-id="08097-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="08097-157">Microsoft 365 Defender の概要</span><span class="sxs-lookup"><span data-stu-id="08097-157">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="08097-158">Microsoft Defender for Endpoint の概要</span><span class="sxs-lookup"><span data-stu-id="08097-158">Microsoft Defender for Endpoint overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="08097-159">Defender for Office 365 の概要</span><span class="sxs-lookup"><span data-stu-id="08097-159">Defender for Office 365 overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="08097-160">Microsoft Cloud App Security の概要</span><span class="sxs-lookup"><span data-stu-id="08097-160">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="08097-161">Id 用 Microsoft Defender の概要</span><span class="sxs-lookup"><span data-stu-id="08097-161">Microsoft Defender for Identity overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="08097-162">Microsoft Defender for Endpoint データ ストレージ</span><span class="sxs-lookup"><span data-stu-id="08097-162">Microsoft Defender for Endpoint data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
