---
title: Microsoft 365 Defender をオンにするときによく寄せられる質問
description: Microsoft 365 Defender の有効化に関連するライセンス、アクセス許可、初期設定、その他の製品およびサービスに関する最も一般的な質問に対する回答を取得する
keywords: よく寄せられる質問、FAQ、GCC、開始、有効にする Microsoft 365 Defender、Microsoft 365 Defender、M365、セキュリティ、データの場所、必要なアクセス許可、ライセンスの適格性、設定ページ
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
ms.openlocfilehash: 55c1a3807fe8e28ca12f4f638c1ab2ca717523ed
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933435"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a><span data-ttu-id="89d61-104">Microsoft 365 Defender をオンにするときによく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="89d61-104">Frequently asked questions when turning on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="89d61-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="89d61-105">**Applies to:**</span></span>
- <span data-ttu-id="89d61-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="89d61-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="89d61-107">必要なライセンスとアクセス許可、サポート サービスの展開、初期設定など [、Microsoft 365 Defender](microsoft-365-defender.md)の有効に関する最も一般的な質問に対する回答を読み取る。</span><span class="sxs-lookup"><span data-stu-id="89d61-107">Read responses to the most commonly asked questions about turning on [Microsoft 365 Defender](microsoft-365-defender.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="89d61-108">サービスを有効にする方法については [、「Microsoft 365 Defender](m365d-enable.md)を有効にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d61-108">For instructions on how to turn on the service, [read Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a><span data-ttu-id="89d61-109">Microsoft 365 E5 ライセンスを持ってない。</span><span class="sxs-lookup"><span data-stu-id="89d61-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="89d61-110">Microsoft 365 Defender は引き続き使用できますか?</span><span class="sxs-lookup"><span data-stu-id="89d61-110">Can I still use Microsoft 365 Defender?</span></span>

<span data-ttu-id="89d61-111">次の E5 以外のライセンスをお持ちのお客様は、Microsoft 365 Defender を使用できます。</span><span class="sxs-lookup"><span data-stu-id="89d61-111">Customers with the following non-E5 licenses can use Microsoft 365 Defender:</span></span>

- <span data-ttu-id="89d61-112">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="89d61-112">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="89d61-113">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="89d61-113">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="89d61-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="89d61-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="89d61-115">Defender for Office 365 (プラン 2)</span><span class="sxs-lookup"><span data-stu-id="89d61-115">Defender for Office 365 (Plan 2)</span></span>
 
<span data-ttu-id="89d61-116">サポートされているライセンスの完全な一覧については、ライセンス [要件を参照してください](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="89d61-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a><span data-ttu-id="89d61-117">Microsoft 365 Defender の使用を開始するには、何かをインストールまたは展開する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="89d61-117">Do I need to install or deploy anything to start using Microsoft 365 Defender?</span></span>

<span data-ttu-id="89d61-118">いいえ、Microsoft 365 Defender は、既に展開した Microsoft 365 セキュリティ サービスのデータを統合します。</span><span class="sxs-lookup"><span data-stu-id="89d61-118">No, Microsoft 365 Defender consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="89d61-119">オンにした後、インシデント、オートメーション、およびハンティング エクスペリエンスは、展開された製品の範囲内で動作し始めるでしょう。</span><span class="sxs-lookup"><span data-stu-id="89d61-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="89d61-120">これらの製品が適切に展開されていない場合、Microsoft 365 Defender はデータを表示し、何も実行できません。</span><span class="sxs-lookup"><span data-stu-id="89d61-120">If none of these products are properly deployed, Microsoft 365 Defender will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="89d61-121">Microsoft 365 Defender エクスペリエンスを最適化するには、サポートされている[Microsoft 365](deploy-supported-services.md)セキュリティ製品とサービスを展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="89d61-121">To optimize your Microsoft 365 Defender experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a><span data-ttu-id="89d61-122">Microsoft 365 Defender はどこで自分のデータを処理して保存しますか?</span><span class="sxs-lookup"><span data-stu-id="89d61-122">Where does Microsoft 365 Defender process and store my data?</span></span>
<span data-ttu-id="89d61-123">Microsoft 365 Defender は、統合データが処理および保存されるデータ センターに最適な場所を自動的に選択します。</span><span class="sxs-lookup"><span data-stu-id="89d61-123">Microsoft 365 Defender automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="89d61-124">Microsoft Defender for Endpoint を使用している場合は、Defender for Endpoint で使用される場所と同じ場所が選択されます。</span><span class="sxs-lookup"><span data-stu-id="89d61-124">If you have Microsoft Defender for Endpoint, it selects the same location used by Defender for Endpoint.</span></span>

>[!NOTE]
><span data-ttu-id="89d61-125">Microsoft Defender for Endpoint は、Azure Defender を使用してオンにした場合、EU (EU) データ センターで自動的にプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="89d61-125">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="89d61-126">Microsoft 365 Defender は、この方法で Microsoft Defender for Endpoint をプロビジョニングしたお客様に対して、同じ EU データ センターで自動的にプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="89d61-126">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender for Endpoint in this manner.</span></span> 

<span data-ttu-id="89d61-127">データ センターの場所は、Microsoft 365 Defender の設定ページ (Microsoft 365 Defender の設定ページ) でサービスを準備する前>**表示されます**。</span><span class="sxs-lookup"><span data-stu-id="89d61-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft 365 Defender (**Settings > Microsoft 365 Defender**).</span></span> <span data-ttu-id="89d61-128">別のデータ センターの場所を使用する場合は、Microsoft 365 セキュリティ センターで [ヘルプが必要か] を選択して、Microsoft サポートに問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="89d61-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-365-defender"></a><span data-ttu-id="89d61-129">Microsoft 365 Defender にアクセスできる場所</span><span class="sxs-lookup"><span data-stu-id="89d61-129">Where can I access Microsoft 365 Defender?</span></span>

<span data-ttu-id="89d61-130">Microsoft 365 Defender は、Microsoft 365 セキュリティ センターで利用できます。</span><span class="sxs-lookup"><span data-stu-id="89d61-130">Microsoft 365 Defender is available in Microsoft 365 security center.</span></span> <span data-ttu-id="89d61-131">セキュリティ センターに移動するには、URL を参照します [https://security.microsoft.com](https://security.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="89d61-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a><span data-ttu-id="89d61-132">Microsoft 365 セキュリティ センターで Microsoft 365 Defender にアクセスするには、どのようなアクセス許可が必要ですか?</span><span class="sxs-lookup"><span data-stu-id="89d61-132">What permissions do I need to access Microsoft 365 Defender in Microsoft 365 security center?</span></span>

<span data-ttu-id="89d61-133">次の Azure Active Directory (AD) ロールが割り当てられているアカウントは、Microsoft 365 Defender の機能とデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="89d61-133">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft 365 Defender functionality and data:</span></span>

- <span data-ttu-id="89d61-134">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="89d61-134">Global administrator</span></span>
- <span data-ttu-id="89d61-135">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="89d61-135">Security administrator</span></span>
- <span data-ttu-id="89d61-136">セキュリティ オペレーター</span><span class="sxs-lookup"><span data-stu-id="89d61-136">Security Operator</span></span>
- <span data-ttu-id="89d61-137">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="89d61-137">Global Reader</span></span>
- <span data-ttu-id="89d61-138">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="89d61-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="89d61-139">Microsoft Defender for Endpoint の役割ベースのアクセス制御設定は、データへのアクセスに影響を与える。</span><span class="sxs-lookup"><span data-stu-id="89d61-139">Role-based access control settings in Microsoft Defender for Endpoint influence access to data.</span></span> <span data-ttu-id="89d61-140">詳細については [、「Microsoft 365 Defender](m365d-permissions.md)へのアクセスの管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d61-140">For more information, read about [managing access to Microsoft 365 Defender](m365d-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a><span data-ttu-id="89d61-141">Microsoft 365 Defender の既定のタイム ゾーンは何ですか?</span><span class="sxs-lookup"><span data-stu-id="89d61-141">What time zone does Microsoft 365 Defender default to?</span></span>
<span data-ttu-id="89d61-142">既定では、Microsoft 365 Defender は UTC タイム ゾーンに時刻情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="89d61-142">By default, Microsoft 365 Defender displays time information in the UTC time zone.</span></span> <span data-ttu-id="89d61-143">この設定を変更して、ローカル タイム ゾーンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="89d61-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="89d61-144">タイム ゾーンの設定の詳細</span><span class="sxs-lookup"><span data-stu-id="89d61-144">Learn about setting the time zone</span></span>](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a><span data-ttu-id="89d61-145">Microsoft 365 Defender の新しい機能と UI の更新プログラムについて、どのように確認できますか?</span><span class="sxs-lookup"><span data-stu-id="89d61-145">How can I learn about new Microsoft 365 Defender feature and UI updates?</span></span>

<span data-ttu-id="89d61-146">Microsoft は、以下を含むさまざまなチャネルを通じて定期的に情報を提供しています。</span><span class="sxs-lookup"><span data-stu-id="89d61-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="89d61-147">Microsoft [](../../admin/manage/message-center.md) 365 管理センターのメッセージ センター</span><span class="sxs-lookup"><span data-stu-id="89d61-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="89d61-148">コンプライアンス 技術コミュニティ [の Microsoft 365 セキュリティ &ブログ投稿](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span><span class="sxs-lookup"><span data-stu-id="89d61-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="89d61-149">プレビュー機能をオンにして、一般に公開されている最新のエクスペリエンス [を取得します](preview.md)。</span><span class="sxs-lookup"><span data-stu-id="89d61-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="89d61-150">Microsoft 365 Defender は米国政府機関コミュニティ クラウド (GCC) または GCC High で利用できますか?</span><span class="sxs-lookup"><span data-stu-id="89d61-150">Is Microsoft 365 Defender available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="89d61-151">現時点では、使用できません。</span><span class="sxs-lookup"><span data-stu-id="89d61-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="89d61-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="89d61-152">Related topics</span></span>

- [<span data-ttu-id="89d61-153">Microsoft 365 Defender の概要</span><span class="sxs-lookup"><span data-stu-id="89d61-153">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- <span data-ttu-id="89d61-154">[Microsoft 365 Defender を有効にする](m365d-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="89d61-154">[Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>
- [<span data-ttu-id="89d61-155">ライセンス要件およびその他の前提条件</span><span class="sxs-lookup"><span data-stu-id="89d61-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="89d61-156">サポートされているサービスを展開する</span><span class="sxs-lookup"><span data-stu-id="89d61-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="89d61-157">プレビュー機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="89d61-157">Turn on preview features</span></span>](preview.md)
