---
title: Microsoft 365 Defender をオンにする際によく寄せられる質問
description: Microsoft 365 Defender を有効にするためのライセンス、アクセス許可、初期設定、その他の製品およびサービスに関してよく寄せられる質問への回答を取得します。
keywords: よく寄せられる質問、FAQ、GCC、作業の開始、MTP の有効化、Microsoft Threat Protection、M365、セキュリティ、データの場所、必要なアクセス許可、ライセンス資格情報、設定ページ
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
ms.openlocfilehash: bfb58cb043f2bc641245814c41e389ddcdbfdefa
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842418"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a><span data-ttu-id="2a0bf-104">Microsoft 365 Defender をオンにする際によく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="2a0bf-104">Frequently asked questions when turning on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2a0bf-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="2a0bf-105">**Applies to:**</span></span>
- <span data-ttu-id="2a0bf-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2a0bf-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="2a0bf-107">必要なライセンスとアクセス許可、サポートサービスの展開、初期設定など、 [Microsoft 365 Defender](microsoft-threat-protection.md)の有効化に関してよく寄せられる質問に対する回答を確認します。</span><span class="sxs-lookup"><span data-stu-id="2a0bf-107">Read responses to the most commonly asked questions about turning on [Microsoft 365 Defender](microsoft-threat-protection.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="2a0bf-108">サービスを有効にする方法については、「 [Microsoft 365 Defender を有効](mtp-enable.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a0bf-108">For instructions on how to turn on the service, [read Turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a><span data-ttu-id="2a0bf-109">Microsoft 365 E5 ライセンスがありません。</span><span class="sxs-lookup"><span data-stu-id="2a0bf-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="2a0bf-110">Microsoft 365 Defender を引き続き使用できますか?</span><span class="sxs-lookup"><span data-stu-id="2a0bf-110">Can I still use Microsoft 365 Defender?</span></span>

<span data-ttu-id="2a0bf-111">次の E5 以外のライセンスを持つお客様は、Microsoft 365 Defender を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2a0bf-111">Customers with the following non-E5 licenses can use Microsoft 365 Defender:</span></span>

- <span data-ttu-id="2a0bf-112">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2a0bf-112">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="2a0bf-113">Id の Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2a0bf-113">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="2a0bf-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2a0bf-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="2a0bf-115">Office 365 の Defender (プラン 2)</span><span class="sxs-lookup"><span data-stu-id="2a0bf-115">Defender for Office 365 (Plan 2)</span></span>
 
<span data-ttu-id="2a0bf-116">サポートされているライセンスの完全な一覧については、 [ライセンス要件を参照](prerequisites.md#licensing-requirements)してください。</span><span class="sxs-lookup"><span data-stu-id="2a0bf-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a><span data-ttu-id="2a0bf-117">Microsoft 365 Defender の使用を開始するには、何をインストールまたは展開する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="2a0bf-117">Do I need to install or deploy anything to start using Microsoft 365 Defender?</span></span>

<span data-ttu-id="2a0bf-118">いいえ。 Microsoft 365 Defender は、既に展開されている Microsoft 365 セキュリティサービスからのデータを統合します。</span><span class="sxs-lookup"><span data-stu-id="2a0bf-118">No, Microsoft 365 Defender consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="2a0bf-119">オンにすると、インシデント、自動化、および検索のエクスペリエンスは、展開された製品の範囲内で動作し始めます。</span><span class="sxs-lookup"><span data-stu-id="2a0bf-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="2a0bf-120">これらの製品のいずれも適切に展開されていない場合、Microsoft 365 Defender はデータを一切表示せず、操作を行うこともできません。</span><span class="sxs-lookup"><span data-stu-id="2a0bf-120">If none of these products are properly deployed, Microsoft 365 Defender will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="2a0bf-121">Microsoft 365 Defender エクスペリエンスを最適化するために、サポートされている *すべて* の [microsoft 365 セキュリティ製品とサービス](deploy-supported-services.md)を展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2a0bf-121">To optimize your Microsoft 365 Defender experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a><span data-ttu-id="2a0bf-122">Microsoft 365 Defender でのデータの処理と保存場所</span><span class="sxs-lookup"><span data-stu-id="2a0bf-122">Where does Microsoft 365 Defender process and store my data?</span></span>
<span data-ttu-id="2a0bf-123">Microsoft 365 Defender は、統合データを処理および保存するデータセンターの最適な場所を自動的に選択します。</span><span class="sxs-lookup"><span data-stu-id="2a0bf-123">Microsoft 365 Defender automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="2a0bf-124">エンドポイントに Microsoft Defender がある場合は、エンドポイントとして Defender で使用されているものと同じ場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="2a0bf-124">If you have Microsoft Defender for Endpoint, it selects the same location used by Defender for Endpoint.</span></span>

>[!NOTE]
><span data-ttu-id="2a0bf-125">エンドポイントの Microsoft Defender は、Azure Defender \* を使用してオンにした場合に、欧州連合 (EU) のデータセンターで自動的にプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="2a0bf-125">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender\*.</span></span> <span data-ttu-id="2a0bf-126">Microsoft 365 Defender は、この方法でエンドポイントとして Microsoft Defender をプロビジョニングしたお客様に対して、同じ EU データセンターで自動的にプロビジョニングを行います。</span><span class="sxs-lookup"><span data-stu-id="2a0bf-126">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender for Endpoint in this manner.</span></span> 

<span data-ttu-id="2a0bf-127">データセンターの場所は、Microsoft 365 Defender の [設定] ページでサービスが準備される前と後に表示されます ( **設定 > microsoft 365 defender** )。</span><span class="sxs-lookup"><span data-stu-id="2a0bf-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft 365 Defender ( **Settings > Microsoft 365 Defender** ).</span></span> <span data-ttu-id="2a0bf-128">別のデータセンターの場所を使用する場合は、microsoft 365 セキュリティセンターの microsoft サポートに問い合わせて、[ **ヘルプが必要ですか?** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2a0bf-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-365-defender"></a><span data-ttu-id="2a0bf-129">Microsoft 365 Defender にはどこにアクセスできますか?</span><span class="sxs-lookup"><span data-stu-id="2a0bf-129">Where can I access Microsoft 365 Defender?</span></span>

<span data-ttu-id="2a0bf-130">Microsoft 365 Defender は、Microsoft 365 セキュリティセンターで利用できます。</span><span class="sxs-lookup"><span data-stu-id="2a0bf-130">Microsoft 365 Defender is available in Microsoft 365 security center.</span></span> <span data-ttu-id="2a0bf-131">セキュリティセンターに移動するには、URL を参照し [https://security.microsoft.com](https://security.microsoft.com) ます。</span><span class="sxs-lookup"><span data-stu-id="2a0bf-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a><span data-ttu-id="2a0bf-132">Microsoft 365 セキュリティセンターの Microsoft 365 Defender にアクセスするために必要なアクセス許可はどのようなものですか?</span><span class="sxs-lookup"><span data-stu-id="2a0bf-132">What permissions do I need to access Microsoft 365 Defender in Microsoft 365 security center?</span></span>

<span data-ttu-id="2a0bf-133">次の Azure Active Directory (AD) の役割が割り当てられているアカウントは、Microsoft 365 Defender の機能とデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2a0bf-133">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft 365 Defender functionality and data:</span></span>

- <span data-ttu-id="2a0bf-134">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="2a0bf-134">Global administrator</span></span>
- <span data-ttu-id="2a0bf-135">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="2a0bf-135">Security administrator</span></span>
- <span data-ttu-id="2a0bf-136">セキュリティ オペレーター</span><span class="sxs-lookup"><span data-stu-id="2a0bf-136">Security Operator</span></span>
- <span data-ttu-id="2a0bf-137">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="2a0bf-137">Global Reader</span></span>
- <span data-ttu-id="2a0bf-138">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="2a0bf-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="2a0bf-139">エンドポイント用の Microsoft Defender の役割ベースのアクセス制御の設定は、データへのアクセスに影響します。</span><span class="sxs-lookup"><span data-stu-id="2a0bf-139">Role-based access control settings in Microsoft Defender for Endpoint influence access to data.</span></span> <span data-ttu-id="2a0bf-140">詳細については、「 [Microsoft 365 Defender へのアクセスの管理](mtp-permissions.md)について」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a0bf-140">For more information, read about [managing access to Microsoft 365 Defender](mtp-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a><span data-ttu-id="2a0bf-141">Microsoft 365 Defender の既定のタイムゾーンは何ですか。</span><span class="sxs-lookup"><span data-stu-id="2a0bf-141">What time zone does Microsoft 365 Defender default to?</span></span>
<span data-ttu-id="2a0bf-142">既定では、Microsoft 365 Defender は UTC タイムゾーンで時間情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="2a0bf-142">By default, Microsoft 365 Defender displays time information in the UTC time zone.</span></span> <span data-ttu-id="2a0bf-143">この設定を変更して、ローカルタイムゾーンを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="2a0bf-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="2a0bf-144">タイムゾーンの設定について</span><span class="sxs-lookup"><span data-stu-id="2a0bf-144">Learn about setting the time zone</span></span>](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a><span data-ttu-id="2a0bf-145">Microsoft 365 Defender の新機能と UI の更新の詳細についてはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="2a0bf-145">How can I learn about new Microsoft 365 Defender feature and UI updates?</span></span>

<span data-ttu-id="2a0bf-146">Microsoft では、次のようなさまざまなチャネルで情報を定期的に提供しています。</span><span class="sxs-lookup"><span data-stu-id="2a0bf-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="2a0bf-147">Microsoft 365 管理センターの[メッセージセンター](../../admin/manage/message-center.md)</span><span class="sxs-lookup"><span data-stu-id="2a0bf-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="2a0bf-148">[Microsoft 365 security & コンプライアンスの技術コミュニティ](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)におけるブログ投稿</span><span class="sxs-lookup"><span data-stu-id="2a0bf-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="2a0bf-149">[プレビュー機能](preview.md)を有効にして、一般公開されている最新のエクスペリエンスを取得できます。</span><span class="sxs-lookup"><span data-stu-id="2a0bf-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="2a0bf-150">Microsoft 365 Defender は米国政府機関向けコミュニティクラウド (GCC) または GCC 高で利用できますか?</span><span class="sxs-lookup"><span data-stu-id="2a0bf-150">Is Microsoft 365 Defender available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="2a0bf-151">現時点では、使用できません。</span><span class="sxs-lookup"><span data-stu-id="2a0bf-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2a0bf-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a0bf-152">Related topics</span></span>

- [<span data-ttu-id="2a0bf-153">Microsoft 365 Defender の概要</span><span class="sxs-lookup"><span data-stu-id="2a0bf-153">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- <span data-ttu-id="2a0bf-154">[Microsoft 365 Defender をオンに](mtp-enable.md)します。</span><span class="sxs-lookup"><span data-stu-id="2a0bf-154">[Turn on Microsoft 365 Defender](mtp-enable.md).</span></span>
- [<span data-ttu-id="2a0bf-155">ライセンス要件およびその他の前提条件</span><span class="sxs-lookup"><span data-stu-id="2a0bf-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="2a0bf-156">サポートされるサービスを展開する</span><span class="sxs-lookup"><span data-stu-id="2a0bf-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="2a0bf-157">プレビュー機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="2a0bf-157">Turn on preview features</span></span>](preview.md)
