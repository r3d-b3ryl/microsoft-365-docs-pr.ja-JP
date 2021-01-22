---
title: Microsoft 365 Defender をオンにするときによく寄せられる質問
description: ライセンス、アクセス許可、初期設定、Microsoft 365 Defender の有効化に関連するその他の製品とサービスに関してよく質問される質問に対する回答を提供します。
keywords: よく寄せられる質問, FAQ, GCC, 開始, MTP の有効化, Microsoft Threat Protection, M365, セキュリティ, データの場所, 必要なアクセス許可, ライセンスの利用資格, 設定ページ
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 2cb9aed070959644e3660188835386118d5f4d9b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930188"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a><span data-ttu-id="ac10f-104">Microsoft 365 Defender をオンにするときによく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="ac10f-104">Frequently asked questions when turning on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ac10f-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="ac10f-105">**Applies to:**</span></span>
- <span data-ttu-id="ac10f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ac10f-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="ac10f-107">必要なライセンスとアクセス許可、サポート サービスの展開、初期設定など [、Microsoft 365 Defender](microsoft-threat-protection.md)のオンに関してよく尋ねらた質問に対する回答をお読みください。</span><span class="sxs-lookup"><span data-stu-id="ac10f-107">Read responses to the most commonly asked questions about turning on [Microsoft 365 Defender](microsoft-threat-protection.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="ac10f-108">サービスを有効にする方法については [、「Microsoft 365 Defender](mtp-enable.md)を有効にする」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ac10f-108">For instructions on how to turn on the service, [read Turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a><span data-ttu-id="ac10f-109">Microsoft 365 E5 ライセンスを持ってない。</span><span class="sxs-lookup"><span data-stu-id="ac10f-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="ac10f-110">Microsoft 365 Defender を引き続き使用できますか?</span><span class="sxs-lookup"><span data-stu-id="ac10f-110">Can I still use Microsoft 365 Defender?</span></span>

<span data-ttu-id="ac10f-111">次の E5 以外のライセンスをお持ちのお客様は、Microsoft 365 Defender を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ac10f-111">Customers with the following non-E5 licenses can use Microsoft 365 Defender:</span></span>

- <span data-ttu-id="ac10f-112">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ac10f-112">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="ac10f-113">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="ac10f-113">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="ac10f-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ac10f-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="ac10f-115">Defender for Office 365 (プラン 2)</span><span class="sxs-lookup"><span data-stu-id="ac10f-115">Defender for Office 365 (Plan 2)</span></span>
 
<span data-ttu-id="ac10f-116">サポートされているライセンスの完全な一覧については、ライセンス [要件を参照してください](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="ac10f-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a><span data-ttu-id="ac10f-117">Microsoft 365 Defender の使用を開始するには、何かをインストールまたは展開する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="ac10f-117">Do I need to install or deploy anything to start using Microsoft 365 Defender?</span></span>

<span data-ttu-id="ac10f-118">いいえ。Microsoft 365 Defender は、展開済みの Microsoft 365 セキュリティ サービスからのデータを統合します。</span><span class="sxs-lookup"><span data-stu-id="ac10f-118">No, Microsoft 365 Defender consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="ac10f-119">この機能を有効にした後は、インシデント、自動化、および検索のエクスペリエンスが展開された製品の範囲内で動作し始めるでしょう。</span><span class="sxs-lookup"><span data-stu-id="ac10f-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="ac10f-120">これらの製品が適切に展開されていない場合、Microsoft 365 Defender はデータを表示しません。また、何も実行できません。</span><span class="sxs-lookup"><span data-stu-id="ac10f-120">If none of these products are properly deployed, Microsoft 365 Defender will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="ac10f-121">Microsoft 365 Defender のエクスペリエンスを最適化するには、サポートされている[Microsoft 365](deploy-supported-services.md)セキュリティ製品とサービスを展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ac10f-121">To optimize your Microsoft 365 Defender experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a><span data-ttu-id="ac10f-122">Microsoft 365 Defender はどこでデータを処理して保存しますか?</span><span class="sxs-lookup"><span data-stu-id="ac10f-122">Where does Microsoft 365 Defender process and store my data?</span></span>
<span data-ttu-id="ac10f-123">Microsoft 365 Defender は、統合データが処理および保存されるデータ センターの最適な場所を自動的に選択します。</span><span class="sxs-lookup"><span data-stu-id="ac10f-123">Microsoft 365 Defender automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="ac10f-124">Microsoft Defender for Endpoint を使用している場合は、Defender for Endpoint で使用されているのと同じ場所が選択されます。</span><span class="sxs-lookup"><span data-stu-id="ac10f-124">If you have Microsoft Defender for Endpoint, it selects the same location used by Defender for Endpoint.</span></span>

>[!NOTE]
><span data-ttu-id="ac10f-125">Microsoft Defender for Endpoint は、Azure Defender を通じて有効になっている場合、欧州連合 (EU) データ センターで自動的にプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="ac10f-125">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="ac10f-126">Microsoft 365 Defender は、この方法で Microsoft Defender for Endpoint をプロビジョニングしたお客様に対して、同じ EU データ センターで自動的にプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="ac10f-126">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender for Endpoint in this manner.</span></span> 

<span data-ttu-id="ac10f-127">データ センターの場所は、サービスがプロビジョニングされる前と後に、Microsoft 365 Defender の設定ページに表示されます **(Microsoft 365 Defender**>設定)。</span><span class="sxs-lookup"><span data-stu-id="ac10f-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft 365 Defender (**Settings > Microsoft 365 Defender**).</span></span> <span data-ttu-id="ac10f-128">別のデータ センターの場所を使用する場合は、Microsoft 365 セキュリティ センターで [サポートが必要ですか? ] を選択して、Microsoft サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="ac10f-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-365-defender"></a><span data-ttu-id="ac10f-129">Microsoft 365 Defender にアクセスできる場所</span><span class="sxs-lookup"><span data-stu-id="ac10f-129">Where can I access Microsoft 365 Defender?</span></span>

<span data-ttu-id="ac10f-130">Microsoft 365 Defender は、Microsoft 365 セキュリティ センターで利用できます。</span><span class="sxs-lookup"><span data-stu-id="ac10f-130">Microsoft 365 Defender is available in Microsoft 365 security center.</span></span> <span data-ttu-id="ac10f-131">セキュリティ センターに移動するには、URL を参照します [https://security.microsoft.com](https://security.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="ac10f-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a><span data-ttu-id="ac10f-132">Microsoft 365 セキュリティ センターで Microsoft 365 Defender にアクセスするには、どのようなアクセス許可が必要ですか?</span><span class="sxs-lookup"><span data-stu-id="ac10f-132">What permissions do I need to access Microsoft 365 Defender in Microsoft 365 security center?</span></span>

<span data-ttu-id="ac10f-133">次の Azure Active Directory (AD) ロールが割り当てられているアカウントは、Microsoft 365 Defender の機能とデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ac10f-133">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft 365 Defender functionality and data:</span></span>

- <span data-ttu-id="ac10f-134">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="ac10f-134">Global administrator</span></span>
- <span data-ttu-id="ac10f-135">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="ac10f-135">Security administrator</span></span>
- <span data-ttu-id="ac10f-136">セキュリティ オペレーター</span><span class="sxs-lookup"><span data-stu-id="ac10f-136">Security Operator</span></span>
- <span data-ttu-id="ac10f-137">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="ac10f-137">Global Reader</span></span>
- <span data-ttu-id="ac10f-138">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="ac10f-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="ac10f-139">Microsoft Defender for Endpoint の役割ベースのアクセス制御設定は、データへのアクセスに影響します。</span><span class="sxs-lookup"><span data-stu-id="ac10f-139">Role-based access control settings in Microsoft Defender for Endpoint influence access to data.</span></span> <span data-ttu-id="ac10f-140">詳細については [、Microsoft 365 Defender へのアクセスの管理に関する記事を参照してください](mtp-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="ac10f-140">For more information, read about [managing access to Microsoft 365 Defender](mtp-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a><span data-ttu-id="ac10f-141">Microsoft 365 Defender は既定でどのタイム ゾーンに設定されていますか?</span><span class="sxs-lookup"><span data-stu-id="ac10f-141">What time zone does Microsoft 365 Defender default to?</span></span>
<span data-ttu-id="ac10f-142">既定では、Microsoft 365 Defender は UTC タイム ゾーンで時刻情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="ac10f-142">By default, Microsoft 365 Defender displays time information in the UTC time zone.</span></span> <span data-ttu-id="ac10f-143">この設定は、ローカル タイム ゾーンを使用するために変更できます。</span><span class="sxs-lookup"><span data-stu-id="ac10f-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="ac10f-144">タイム ゾーンの設定について</span><span class="sxs-lookup"><span data-stu-id="ac10f-144">Learn about setting the time zone</span></span>](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a><span data-ttu-id="ac10f-145">Microsoft 365 Defender の新しい機能と UI の更新プログラムについて知る方法</span><span class="sxs-lookup"><span data-stu-id="ac10f-145">How can I learn about new Microsoft 365 Defender feature and UI updates?</span></span>

<span data-ttu-id="ac10f-146">Microsoft は、次に示すさまざまなチャネルを通じて定期的に情報を提供しています。</span><span class="sxs-lookup"><span data-stu-id="ac10f-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="ac10f-147">Microsoft [](../../admin/manage/message-center.md) 365 管理センターのメッセージ センター</span><span class="sxs-lookup"><span data-stu-id="ac10f-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="ac10f-148">[Microsoft 365 セキュリティ/コンプライアンス 技術コミュニティ&ブログ記事](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span><span class="sxs-lookup"><span data-stu-id="ac10f-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="ac10f-149">プレビュー機能をオンにして、最新の一般公開エクスペリエンス [を取得します](preview.md)。</span><span class="sxs-lookup"><span data-stu-id="ac10f-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="ac10f-150">Microsoft 365 Defender は、米国政府機関向けコミュニティ クラウド (GCC) または GCC High で利用できますか?</span><span class="sxs-lookup"><span data-stu-id="ac10f-150">Is Microsoft 365 Defender available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="ac10f-151">現時点では、使用できません。</span><span class="sxs-lookup"><span data-stu-id="ac10f-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ac10f-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="ac10f-152">Related topics</span></span>

- [<span data-ttu-id="ac10f-153">Microsoft 365 Defender の概要</span><span class="sxs-lookup"><span data-stu-id="ac10f-153">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- <span data-ttu-id="ac10f-154">[Microsoft 365 Defender を有効にする](mtp-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="ac10f-154">[Turn on Microsoft 365 Defender](mtp-enable.md).</span></span>
- [<span data-ttu-id="ac10f-155">ライセンス要件およびその他の前提条件</span><span class="sxs-lookup"><span data-stu-id="ac10f-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="ac10f-156">サポートされているサービスを展開する</span><span class="sxs-lookup"><span data-stu-id="ac10f-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="ac10f-157">プレビュー機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="ac10f-157">Turn on preview features</span></span>](preview.md)
