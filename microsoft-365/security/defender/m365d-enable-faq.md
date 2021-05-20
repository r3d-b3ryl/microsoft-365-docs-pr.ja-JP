---
title: ディフェンダーをオンにする際によくある質問Microsoft 365
description: ライセンス、アクセス許可、初期設定、およびMicrosoft 365 Defender の有効化に関連するその他の製品やサービスに関する最も一般的な質問への回答を得る
keywords: よく寄せられる質問, FAQ, GCC, 開始, Microsoft 365ディフェンダーを有効にします, Microsoft 365 ディフェンダー, M365, セキュリティ, データの場所, 必要な権限, ライセンスの適格性, 設定ページ
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
ms.openlocfilehash: 008e3cc6ee65597a032aa932b74a64ac591927f2
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572767"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a><span data-ttu-id="adbb4-104">ディフェンダーをオンにする際によくある質問Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="adbb4-104">Frequently asked questions when turning on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="adbb4-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="adbb4-105">**Applies to:**</span></span>
- <span data-ttu-id="adbb4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="adbb4-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="adbb4-107">必要なライセンスとアクセス許可、サポート サービスの展開、初期設定など、最も一般的な質問に対する回答[をMicrosoft 365 Defender](microsoft-365-defender.md)に関する質問を参照してください。</span><span class="sxs-lookup"><span data-stu-id="adbb4-107">Read responses to the most commonly asked questions about turning on [Microsoft 365 Defender](microsoft-365-defender.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="adbb4-108">サービスを有効にする方法については[、「defender を有効にする」Microsoft 365参照](m365d-enable.md)してください。</span><span class="sxs-lookup"><span data-stu-id="adbb4-108">For instructions on how to turn on the service, [read Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a><span data-ttu-id="adbb4-109">私はMicrosoft 365 E5ライセンスを持っていません。</span><span class="sxs-lookup"><span data-stu-id="adbb4-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="adbb4-110">ディフェンダー Microsoft 365使用できますか?</span><span class="sxs-lookup"><span data-stu-id="adbb4-110">Can I still use Microsoft 365 Defender?</span></span>

<span data-ttu-id="adbb4-111">次の非 E5 ライセンスをお持ちのお客様は、Microsoft 365 Defender を使用できます。</span><span class="sxs-lookup"><span data-stu-id="adbb4-111">Customers with the following non-E5 licenses can use Microsoft 365 Defender:</span></span>

- <span data-ttu-id="adbb4-112">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="adbb4-112">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="adbb4-113">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="adbb4-113">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="adbb4-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="adbb4-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="adbb4-115">Defender for Office 365 (プラン 2)</span><span class="sxs-lookup"><span data-stu-id="adbb4-115">Defender for Office 365 (Plan 2)</span></span>
 
<span data-ttu-id="adbb4-116">サポートされているライセンスの完全なリストについては、 [ライセンス要件を参照](prerequisites.md#licensing-requirements)してください。</span><span class="sxs-lookup"><span data-stu-id="adbb4-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a><span data-ttu-id="adbb4-117">Microsoft 365 Defender の使用を開始するには、何かをインストールまたは展開する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="adbb4-117">Do I need to install or deploy anything to start using Microsoft 365 Defender?</span></span>

<span data-ttu-id="adbb4-118">いいえ、Microsoft 365 Defender は、既に展開されているセキュリティ サービスMicrosoft 365データを統合します。</span><span class="sxs-lookup"><span data-stu-id="adbb4-118">No, Microsoft 365 Defender consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="adbb4-119">電源を入れると、インシデント、自動化、および狩猟のエクスペリエンスが、デプロイされた製品の範囲内で作業を開始します。</span><span class="sxs-lookup"><span data-stu-id="adbb4-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="adbb4-120">これらの製品がいずれも適切に展開されていない場合、Microsoft 365 Defender はデータを表示せず、何も操作を実行できません。</span><span class="sxs-lookup"><span data-stu-id="adbb4-120">If none of these products are properly deployed, Microsoft 365 Defender will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="adbb4-121">Microsoft 365 Defender のエクスペリエンスを最適化するために *、サポートされているすべての*[Microsoft 365セキュリティ製品とサービス](deploy-supported-services.md)を展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="adbb4-121">To optimize your Microsoft 365 Defender experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a><span data-ttu-id="adbb4-122">Microsoft 365ディフェンダーはどこでデータを処理して保存しますか?</span><span class="sxs-lookup"><span data-stu-id="adbb4-122">Where does Microsoft 365 Defender process and store my data?</span></span>
<span data-ttu-id="adbb4-123">Microsoft 365Defender は、統合データが処理され、保存されるデータセンターに最適な場所を自動的に選択します。</span><span class="sxs-lookup"><span data-stu-id="adbb4-123">Microsoft 365 Defender automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="adbb4-124">エンドポイントの Microsoft Defender がある場合は、エンドポイントの Defender で使用されるのと同じ場所が選択されます。</span><span class="sxs-lookup"><span data-stu-id="adbb4-124">If you have Microsoft Defender for Endpoint, it selects the same location used by Defender for Endpoint.</span></span>

>[!NOTE]
><span data-ttu-id="adbb4-125">エンドポイントのマイクロソフトディフェンダーは、Azure Defender を使用してオンにすると、欧州連合 (EU) のデータ センターで自動的にプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="adbb4-125">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="adbb4-126">Microsoft 365Defender は、この方法でエンドポイント用の Microsoft Defender をプロビジョニングした顧客に対して、同じ EU データ センターで自動的にプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="adbb4-126">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender for Endpoint in this manner.</span></span> 

<span data-ttu-id="adbb4-127">データセンターの場所は、サービスがプロビジョニングされる前と後に、Microsoft 365 Defender ( 設定 > Microsoft 365 **Defender**) の設定ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="adbb4-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft 365 Defender (**Settings > Microsoft 365 Defender**).</span></span> <span data-ttu-id="adbb4-128">別のデータ センターの場所を使用する場合は、Microsoft 365 セキュリティ センターで [**ヘルプが必要ですか?**</span><span class="sxs-lookup"><span data-stu-id="adbb4-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-365-defender"></a><span data-ttu-id="adbb4-129">ディフェンダー Microsoft 365どこでアクセスできますか?</span><span class="sxs-lookup"><span data-stu-id="adbb4-129">Where can I access Microsoft 365 Defender?</span></span>

<span data-ttu-id="adbb4-130">Microsoft 365保護機能はMicrosoft 365セキュリティ センターで利用できます。</span><span class="sxs-lookup"><span data-stu-id="adbb4-130">Microsoft 365 Defender is available in Microsoft 365 security center.</span></span> <span data-ttu-id="adbb4-131">セキュリティ センターに移動するには、 URL を参照 [https://security.microsoft.com](https://security.microsoft.com) します。</span><span class="sxs-lookup"><span data-stu-id="adbb4-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a><span data-ttu-id="adbb4-132">セキュリティ センターの Microsoft 365 Defender にアクセスするには、どのようなアクセス許可Microsoft 365必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="adbb4-132">What permissions do I need to access Microsoft 365 Defender in Microsoft 365 security center?</span></span>

<span data-ttu-id="adbb4-133">次の Azure Active Directory (Azure AD) ロールが割り当てられたアカウントは、Microsoft 365 Defender 機能とデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="adbb4-133">Accounts assigned the following Azure Active Directory (Azure AD) roles can access Microsoft 365 Defender functionality and data:</span></span>

- <span data-ttu-id="adbb4-134">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="adbb4-134">Global administrator</span></span>
- <span data-ttu-id="adbb4-135">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="adbb4-135">Security administrator</span></span>
- <span data-ttu-id="adbb4-136">セキュリティ オペレーター</span><span class="sxs-lookup"><span data-stu-id="adbb4-136">Security Operator</span></span>
- <span data-ttu-id="adbb4-137">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="adbb4-137">Global Reader</span></span>
- <span data-ttu-id="adbb4-138">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="adbb4-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="adbb4-139">エンドポイントの Microsoft Defender のロール ベースのアクセス制御設定は、データへのアクセスに影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="adbb4-139">Role-based access control settings in Microsoft Defender for Endpoint influence access to data.</span></span> <span data-ttu-id="adbb4-140">詳細については、「 defender Microsoft 365[へのアクセスの管理](m365d-permissions.md)について」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="adbb4-140">For more information, read about [managing access to Microsoft 365 Defender](m365d-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a><span data-ttu-id="adbb4-141">ディフェンダーのデフォルトのタイムゾーンMicrosoft 365?</span><span class="sxs-lookup"><span data-stu-id="adbb4-141">What time zone does Microsoft 365 Defender default to?</span></span>
<span data-ttu-id="adbb4-142">既定では、Microsoft 365 Defender は UTC タイム ゾーンに時刻情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="adbb4-142">By default, Microsoft 365 Defender displays time information in the UTC time zone.</span></span> <span data-ttu-id="adbb4-143">この設定を変更して、ローカル タイム ゾーンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="adbb4-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="adbb4-144">タイムゾーンの設定の詳細</span><span class="sxs-lookup"><span data-stu-id="adbb4-144">Learn about setting the time zone</span></span>](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a><span data-ttu-id="adbb4-145">新しいMicrosoft 365 Defender 機能と UI の更新について学習するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="adbb4-145">How can I learn about new Microsoft 365 Defender feature and UI updates?</span></span>

<span data-ttu-id="adbb4-146">マイクロソフトは、次のチャネルを通じて定期的に情報を提供しています。</span><span class="sxs-lookup"><span data-stu-id="adbb4-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="adbb4-147">管理[センターのメッセージ センター](../../admin/manage/message-center.md) Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="adbb4-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="adbb4-148">[Microsoft 365セキュリティ&コンプライアンス技術コミュニティ](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)のブログ記事</span><span class="sxs-lookup"><span data-stu-id="adbb4-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="adbb4-149">[プレビュー機能](preview.md)を有効にして、最新の公開エクスペリエンスを取得する 。</span><span class="sxs-lookup"><span data-stu-id="adbb4-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="adbb4-150">Microsoft 365ディフェンダーは米国Government Community Cloud(GCC)またはGCCハイで利用可能ですか?</span><span class="sxs-lookup"><span data-stu-id="adbb4-150">Is Microsoft 365 Defender available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="adbb4-151">現時点では、使用できません。</span><span class="sxs-lookup"><span data-stu-id="adbb4-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="adbb4-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="adbb4-152">Related topics</span></span>

- [<span data-ttu-id="adbb4-153">Microsoft 365ディフェンダーの概要</span><span class="sxs-lookup"><span data-stu-id="adbb4-153">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- <span data-ttu-id="adbb4-154">[Microsoft 365ディフェンダーをオンに](m365d-enable.md)します。</span><span class="sxs-lookup"><span data-stu-id="adbb4-154">[Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>
- [<span data-ttu-id="adbb4-155">ライセンス要件およびその他の前提条件</span><span class="sxs-lookup"><span data-stu-id="adbb4-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="adbb4-156">サポートされているサービスを展開する</span><span class="sxs-lookup"><span data-stu-id="adbb4-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="adbb4-157">プレビュー機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="adbb4-157">Turn on preview features</span></span>](preview.md)
