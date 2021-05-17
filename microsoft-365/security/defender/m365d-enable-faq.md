---
title: Defender をオンにするときによく寄せられるMicrosoft 365質問
description: ライセンス、アクセス許可、初期設定、および Defender の有効化に関連するその他の製品およびサービスに関する最も一般的な質問に対する回答をMicrosoft 365する
keywords: よく寄せられる質問、FAQ、GCC、開始、Microsoft 365 Defender、Microsoft 365 Defender、M365、セキュリティ、データの場所、必要なアクセス許可、ライセンスの適格性、設定ページの有効化
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
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a><span data-ttu-id="f1a1b-104">Defender をオンにするときによく寄せられるMicrosoft 365質問</span><span class="sxs-lookup"><span data-stu-id="f1a1b-104">Frequently asked questions when turning on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f1a1b-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="f1a1b-105">**Applies to:**</span></span>
- <span data-ttu-id="f1a1b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f1a1b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f1a1b-107">[Microsoft 365 Defender](microsoft-365-defender.md)の有効に関する最も一般的な質問 (必要なライセンスとアクセス許可、サポート サービスの展開、初期設定など) に対する回答を読み取る。</span><span class="sxs-lookup"><span data-stu-id="f1a1b-107">Read responses to the most commonly asked questions about turning on [Microsoft 365 Defender](microsoft-365-defender.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="f1a1b-108">サービスを有効にする方法については、「Defender を有効にする」[をMicrosoft 365してください](m365d-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="f1a1b-108">For instructions on how to turn on the service, [read Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a><span data-ttu-id="f1a1b-109">ライセンスを持Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="f1a1b-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="f1a1b-110">Defender で引き続きMicrosoft 365できますか?</span><span class="sxs-lookup"><span data-stu-id="f1a1b-110">Can I still use Microsoft 365 Defender?</span></span>

<span data-ttu-id="f1a1b-111">次の E5 以外のライセンスをお持ちのお客様は、Defender Microsoft 365使用できます。</span><span class="sxs-lookup"><span data-stu-id="f1a1b-111">Customers with the following non-E5 licenses can use Microsoft 365 Defender:</span></span>

- <span data-ttu-id="f1a1b-112">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f1a1b-112">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="f1a1b-113">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="f1a1b-113">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="f1a1b-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f1a1b-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="f1a1b-115">Defender for Office 365 (プラン 2)</span><span class="sxs-lookup"><span data-stu-id="f1a1b-115">Defender for Office 365 (Plan 2)</span></span>
 
<span data-ttu-id="f1a1b-116">サポートされているライセンスの完全な一覧については、ライセンス [要件を参照してください](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="f1a1b-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a><span data-ttu-id="f1a1b-117">Defender の使用を開始するには、何かをインストールまたは展開するMicrosoft 365ですか?</span><span class="sxs-lookup"><span data-stu-id="f1a1b-117">Do I need to install or deploy anything to start using Microsoft 365 Defender?</span></span>

<span data-ttu-id="f1a1b-118">いいえ、Microsoft 365 Defender は、既に展開Microsoft 365サービスからのデータを統合します。</span><span class="sxs-lookup"><span data-stu-id="f1a1b-118">No, Microsoft 365 Defender consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="f1a1b-119">オンにした後、インシデント、オートメーション、およびハンティング エクスペリエンスは、展開された製品の範囲内で動作し始めるでしょう。</span><span class="sxs-lookup"><span data-stu-id="f1a1b-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="f1a1b-120">これらの製品が適切に展開されていない場合、Microsoft 365 Defender はデータを表示し、何も実行できません。</span><span class="sxs-lookup"><span data-stu-id="f1a1b-120">If none of these products are properly deployed, Microsoft 365 Defender will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="f1a1b-121">Defender エクスペリエンスを最適化Microsoft 365、サポートされているセキュリティ製品とサービスMicrosoft 365[展開することをお勧めします](deploy-supported-services.md)。</span><span class="sxs-lookup"><span data-stu-id="f1a1b-121">To optimize your Microsoft 365 Defender experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a><span data-ttu-id="f1a1b-122">Defender のプロセスMicrosoft 365保存する場所</span><span class="sxs-lookup"><span data-stu-id="f1a1b-122">Where does Microsoft 365 Defender process and store my data?</span></span>
<span data-ttu-id="f1a1b-123">Microsoft 365Defender は、統合データが処理および保存されるデータ センターの最適な場所を自動的に選択します。</span><span class="sxs-lookup"><span data-stu-id="f1a1b-123">Microsoft 365 Defender automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="f1a1b-124">Microsoft Defender for Endpoint を使用している場合は、Defender for Endpoint で使用される場所と同じ場所が選択されます。</span><span class="sxs-lookup"><span data-stu-id="f1a1b-124">If you have Microsoft Defender for Endpoint, it selects the same location used by Defender for Endpoint.</span></span>

>[!NOTE]
><span data-ttu-id="f1a1b-125">Microsoft Defender for Endpoint は、Azure Defender を使用してオンにした場合、EU (EU) データ センターで自動的にプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="f1a1b-125">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="f1a1b-126">Microsoft 365Defender は、この方法で Microsoft Defender for Endpoint をプロビジョニングしたお客様に対して、同じ EU データ センターで自動的にプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="f1a1b-126">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender for Endpoint in this manner.</span></span> 

<span data-ttu-id="f1a1b-127">データ センターの場所は、サービスがプロビジョニングされる前と後に、Defender (Defender) の設定ページMicrosoft 365表示設定 > Microsoft 365 **されます**。</span><span class="sxs-lookup"><span data-stu-id="f1a1b-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft 365 Defender (**Settings > Microsoft 365 Defender**).</span></span> <span data-ttu-id="f1a1b-128">別のデータ センターの場所を使用する場合は、Microsoft サポートに問い合Microsoft 365セキュリティ センターで [ヘルプが必要か] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f1a1b-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-365-defender"></a><span data-ttu-id="f1a1b-129">Defender へのアクセス先Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="f1a1b-129">Where can I access Microsoft 365 Defender?</span></span>

<span data-ttu-id="f1a1b-130">Microsoft 365Defender はセキュリティ センター Microsoft 365利用できます。</span><span class="sxs-lookup"><span data-stu-id="f1a1b-130">Microsoft 365 Defender is available in Microsoft 365 security center.</span></span> <span data-ttu-id="f1a1b-131">セキュリティ センターに移動するには、URL を参照します [https://security.microsoft.com](https://security.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="f1a1b-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a><span data-ttu-id="f1a1b-132">セキュリティ センターで Defender にアクセスMicrosoft 365アクセスするにはMicrosoft 365必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="f1a1b-132">What permissions do I need to access Microsoft 365 Defender in Microsoft 365 security center?</span></span>

<span data-ttu-id="f1a1b-133">次の役割 (Azure Active Directory) AD割り当てられたアカウントは、Defender のMicrosoft 365データにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f1a1b-133">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft 365 Defender functionality and data:</span></span>

- <span data-ttu-id="f1a1b-134">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="f1a1b-134">Global administrator</span></span>
- <span data-ttu-id="f1a1b-135">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="f1a1b-135">Security administrator</span></span>
- <span data-ttu-id="f1a1b-136">セキュリティ オペレーター</span><span class="sxs-lookup"><span data-stu-id="f1a1b-136">Security Operator</span></span>
- <span data-ttu-id="f1a1b-137">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="f1a1b-137">Global Reader</span></span>
- <span data-ttu-id="f1a1b-138">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="f1a1b-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="f1a1b-139">Microsoft Defender for Endpoint の役割ベースのアクセス制御設定は、データへのアクセスに影響を与える。</span><span class="sxs-lookup"><span data-stu-id="f1a1b-139">Role-based access control settings in Microsoft Defender for Endpoint influence access to data.</span></span> <span data-ttu-id="f1a1b-140">詳細については、「Defender へのアクセス[の管理」をMicrosoft 365してください](m365d-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="f1a1b-140">For more information, read about [managing access to Microsoft 365 Defender](m365d-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a><span data-ttu-id="f1a1b-141">Defender の既定のMicrosoft 365タイム ゾーンは何ですか?</span><span class="sxs-lookup"><span data-stu-id="f1a1b-141">What time zone does Microsoft 365 Defender default to?</span></span>
<span data-ttu-id="f1a1b-142">既定では、Microsoft 365 Defender は UTC タイム ゾーンに時刻情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="f1a1b-142">By default, Microsoft 365 Defender displays time information in the UTC time zone.</span></span> <span data-ttu-id="f1a1b-143">この設定を変更して、ローカル タイム ゾーンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f1a1b-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="f1a1b-144">タイム ゾーンの設定の詳細</span><span class="sxs-lookup"><span data-stu-id="f1a1b-144">Learn about setting the time zone</span></span>](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a><span data-ttu-id="f1a1b-145">Defender 機能と UI の更新プログラムMicrosoft 365方法を学ぶには?</span><span class="sxs-lookup"><span data-stu-id="f1a1b-145">How can I learn about new Microsoft 365 Defender feature and UI updates?</span></span>

<span data-ttu-id="f1a1b-146">Microsoft は、以下を含むさまざまなチャネルを通じて定期的に情報を提供しています。</span><span class="sxs-lookup"><span data-stu-id="f1a1b-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="f1a1b-147">管理[センターの](../../admin/manage/message-center.md)Microsoft 365センター</span><span class="sxs-lookup"><span data-stu-id="f1a1b-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="f1a1b-148">コンプライアンス 技術コミュニティMicrosoft 365[セキュリティ&ブログ投稿](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span><span class="sxs-lookup"><span data-stu-id="f1a1b-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="f1a1b-149">プレビュー機能をオンにして、一般に公開されている最新のエクスペリエンス [を取得します](preview.md)。</span><span class="sxs-lookup"><span data-stu-id="f1a1b-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="f1a1b-150">米国Microsoft 365 (Government Community Cloud) または GCC High で Defender をGCCか。</span><span class="sxs-lookup"><span data-stu-id="f1a1b-150">Is Microsoft 365 Defender available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="f1a1b-151">現時点では、使用できません。</span><span class="sxs-lookup"><span data-stu-id="f1a1b-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f1a1b-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1a1b-152">Related topics</span></span>

- [<span data-ttu-id="f1a1b-153">Microsoft 365Defender の概要</span><span class="sxs-lookup"><span data-stu-id="f1a1b-153">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- <span data-ttu-id="f1a1b-154">[Defender を有効Microsoft 365します](m365d-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="f1a1b-154">[Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>
- [<span data-ttu-id="f1a1b-155">ライセンス要件およびその他の前提条件</span><span class="sxs-lookup"><span data-stu-id="f1a1b-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="f1a1b-156">サポートされているサービスを展開する</span><span class="sxs-lookup"><span data-stu-id="f1a1b-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="f1a1b-157">プレビュー機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="f1a1b-157">Turn on preview features</span></span>](preview.md)
