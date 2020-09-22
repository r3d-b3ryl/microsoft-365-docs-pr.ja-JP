---
title: Microsoft の脅威保護を有効にする際によく寄せられる質問
description: Microsoft の脅威保護を有効にするためのライセンス、アクセス許可、初期設定、その他の製品およびサービスに関してよく寄せられる質問に対する回答を取得します。
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
ms.openlocfilehash: 6b0d8d9be0cc84e61a3228f79fc14f1bfc9f8a83
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198841"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-threat-protection"></a><span data-ttu-id="a9c75-104">Microsoft の脅威保護を有効にする際によく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="a9c75-104">Frequently asked questions when turning on Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a9c75-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="a9c75-105">**Applies to:**</span></span>
- <span data-ttu-id="a9c75-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a9c75-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="a9c75-107">必要なライセンスとアクセス許可、サポートサービスの展開、初期設定など、 [Microsoft の脅威保護](microsoft-threat-protection.md)を有効にすることに関してよく寄せられる質問に対する回答を確認できます。</span><span class="sxs-lookup"><span data-stu-id="a9c75-107">Read responses to the most commonly asked questions about turning on [Microsoft Threat Protection](microsoft-threat-protection.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="a9c75-108">サービスを有効にする方法については、「 [Microsoft Threat Protection を有効](mtp-enable.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9c75-108">For instructions on how to turn on the service, [read Turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-threat-protection"></a><span data-ttu-id="a9c75-109">Microsoft 365 E5 ライセンスがありません。</span><span class="sxs-lookup"><span data-stu-id="a9c75-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="a9c75-110">Microsoft の脅威保護を引き続き使用できますか。</span><span class="sxs-lookup"><span data-stu-id="a9c75-110">Can I still use Microsoft Threat Protection?</span></span>

<span data-ttu-id="a9c75-111">次の E5 以外のライセンスを持つお客様は、Microsoft の脅威保護を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a9c75-111">Customers with the following non-E5 licenses can use Microsoft Threat Protection:</span></span>

- <span data-ttu-id="a9c75-112">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a9c75-112">Microsoft Defender Advanced Threat Protection</span></span>
- <span data-ttu-id="a9c75-113">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a9c75-113">Azure Advanced Threat Protection</span></span>
- <span data-ttu-id="a9c75-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="a9c75-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="a9c75-115">Office 365 Advanced Threat Protection (プラン 2)</span><span class="sxs-lookup"><span data-stu-id="a9c75-115">Office 365 Advanced Threat Protection (Plan 2)</span></span>
 
<span data-ttu-id="a9c75-116">サポートされているライセンスの完全な一覧については、 [ライセンス要件を参照](prerequisites.md#licensing-requirements)してください。</span><span class="sxs-lookup"><span data-stu-id="a9c75-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-threat-protection"></a><span data-ttu-id="a9c75-117">Microsoft の脅威保護の使用を開始するには、何をインストールまたは展開する必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="a9c75-117">Do I need to install or deploy anything to start using Microsoft Threat Protection?</span></span>

<span data-ttu-id="a9c75-118">いいえ。 Microsoft の脅威保護は、既に展開されている Microsoft 365 セキュリティサービスからのデータを統合します。</span><span class="sxs-lookup"><span data-stu-id="a9c75-118">No, Microsoft Threat Protection consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="a9c75-119">オンにすると、インシデント、自動化、および検索のエクスペリエンスは、展開された製品の範囲内で動作し始めます。</span><span class="sxs-lookup"><span data-stu-id="a9c75-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="a9c75-120">これらの製品のいずれも適切に展開されていない場合、Microsoft の脅威保護ではデータは表示されず、操作を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="a9c75-120">If none of these products are properly deployed, Microsoft Threat Protection will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="a9c75-121">Microsoft の脅威保護エクスペリエンスを最適化するために、サポートされている *すべて* の [microsoft 365 セキュリティ製品とサービス](deploy-supported-services.md)を展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a9c75-121">To optimize your Microsoft Threat Protection experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-threat-protection-process-and-store-my-data"></a><span data-ttu-id="a9c75-122">Microsoft の脅威保護のプロセスとデータの保存場所</span><span class="sxs-lookup"><span data-stu-id="a9c75-122">Where does Microsoft Threat Protection process and store my data?</span></span>
<span data-ttu-id="a9c75-123">Microsoft の脅威保護は、統合されたデータを処理および保存するデータセンターの最適な場所を自動的に選択します。</span><span class="sxs-lookup"><span data-stu-id="a9c75-123">Microsoft Threat Protection automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="a9c75-124">Microsoft Defender ATP がある場合は、Microsoft Defender ATP で使用されているものと同じ場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="a9c75-124">If you have Microsoft Defender ATP, it selects the same location used by Microsoft Defender ATP.</span></span>

>[!NOTE]
><span data-ttu-id="a9c75-125">Microsoft Defender ATP は、Azure セキュリティセンターを使用してオンにした場合に、欧州連合 (EU) のデータセンターで自動的にプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="a9c75-125">Microsoft Defender ATP automatically provisions in European Union (EU) data centers when turned on through Azure Security Center.</span></span> <span data-ttu-id="a9c75-126">Microsoft の脅威保護は、Microsoft Defender ATP をこの方法でプロビジョニングしたお客様に対して、同じ EU データセンターで自動的にプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="a9c75-126">Microsoft Threat Protection will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender ATP in this manner.</span></span> 

<span data-ttu-id="a9c75-127">データセンターの場所は、Microsoft Threat Protection (**設定 > Microsoft Threat protection**) の設定ページで、サービスの準備が完了する前と後に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a9c75-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft Threat Protection (**Settings > Microsoft Threat Protection**).</span></span> <span data-ttu-id="a9c75-128">別のデータセンターの場所を使用する場合は、microsoft 365 セキュリティセンターの microsoft サポートに問い合わせて、[ **ヘルプが必要ですか?** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a9c75-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-threat-protection"></a><span data-ttu-id="a9c75-129">Microsoft の脅威保護にはどこでアクセスできますか?</span><span class="sxs-lookup"><span data-stu-id="a9c75-129">Where can I access Microsoft Threat Protection?</span></span>

<span data-ttu-id="a9c75-130">Microsoft の脅威保護は、Microsoft 365 セキュリティセンターで利用できます。</span><span class="sxs-lookup"><span data-stu-id="a9c75-130">Microsoft Threat Protection is available in Microsoft 365 security center.</span></span> <span data-ttu-id="a9c75-131">セキュリティセンターに移動するには、URL を参照し [https://security.microsoft.com](https://security.microsoft.com) ます。</span><span class="sxs-lookup"><span data-stu-id="a9c75-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-threat-protection-in-microsoft-365-security-center"></a><span data-ttu-id="a9c75-132">Microsoft 365 セキュリティセンターの Microsoft 脅威保護にアクセスするために必要なアクセス許可は何ですか。</span><span class="sxs-lookup"><span data-stu-id="a9c75-132">What permissions do I need to access Microsoft Threat Protection in Microsoft 365 security center?</span></span>

<span data-ttu-id="a9c75-133">次の Azure Active Directory (AD) のロールが割り当てられているアカウントは、Microsoft Threat Protection の機能とデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a9c75-133">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft Threat Protection functionality and data:</span></span>

- <span data-ttu-id="a9c75-134">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="a9c75-134">Global administrator</span></span>
- <span data-ttu-id="a9c75-135">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="a9c75-135">Security administrator</span></span>
- <span data-ttu-id="a9c75-136">セキュリティ オペレーター</span><span class="sxs-lookup"><span data-stu-id="a9c75-136">Security Operator</span></span>
- <span data-ttu-id="a9c75-137">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="a9c75-137">Global Reader</span></span>
- <span data-ttu-id="a9c75-138">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="a9c75-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="a9c75-139">Microsoft Defender ATP の役割ベースのアクセス制御の設定は、データへのアクセスに影響します。</span><span class="sxs-lookup"><span data-stu-id="a9c75-139">Role-based access control settings in Microsoft Defender ATP influence access to data.</span></span> <span data-ttu-id="a9c75-140">詳細については、「 [Microsoft の脅威保護へのアクセスの管理](mtp-permissions.md)について」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9c75-140">For more information, read about [managing access to Microsoft Threat Protection](mtp-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-threat-protection-default-to"></a><span data-ttu-id="a9c75-141">Microsoft の脅威保護の既定のタイムゾーンは何ですか。</span><span class="sxs-lookup"><span data-stu-id="a9c75-141">What time zone does Microsoft Threat Protection default to?</span></span>
<span data-ttu-id="a9c75-142">既定では、Microsoft Threat Protection は UTC タイムゾーンで時間情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="a9c75-142">By default, Microsoft Threat Protection displays time information in the UTC time zone.</span></span> <span data-ttu-id="a9c75-143">この設定を変更して、ローカルタイムゾーンを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="a9c75-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="a9c75-144">タイムゾーンの設定について</span><span class="sxs-lookup"><span data-stu-id="a9c75-144">Learn about setting the time zone</span></span>](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-threat-protection-feature-and-ui-updates"></a><span data-ttu-id="a9c75-145">Microsoft の新しい脅威保護機能と UI 更新プログラムについて調べるにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="a9c75-145">How can I learn about new Microsoft Threat Protection feature and UI updates?</span></span>

<span data-ttu-id="a9c75-146">Microsoft では、次のようなさまざまなチャネルで情報を定期的に提供しています。</span><span class="sxs-lookup"><span data-stu-id="a9c75-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="a9c75-147">Microsoft 365 管理センターの[メッセージセンター](../../admin/manage/message-center.md)</span><span class="sxs-lookup"><span data-stu-id="a9c75-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="a9c75-148">[Microsoft 365 security & コンプライアンスの技術コミュニティ](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)におけるブログ投稿</span><span class="sxs-lookup"><span data-stu-id="a9c75-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="a9c75-149">[プレビュー機能](preview.md)を有効にして、一般公開されている最新のエクスペリエンスを取得できます。</span><span class="sxs-lookup"><span data-stu-id="a9c75-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="a9c75-150">Microsoft Threat Protection は、米国政府機関向けコミュニティ クラウド (GCC) または GCC High で使用できますか?</span><span class="sxs-lookup"><span data-stu-id="a9c75-150">Is Microsoft Threat Protection available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="a9c75-151">現時点では、使用できません。</span><span class="sxs-lookup"><span data-stu-id="a9c75-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a9c75-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="a9c75-152">Related topics</span></span>

- [<span data-ttu-id="a9c75-153">Microsoft Threat Protection の概要</span><span class="sxs-lookup"><span data-stu-id="a9c75-153">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- <span data-ttu-id="a9c75-154">[Microsoft の脅威保護を有効](mtp-enable.md)にします。</span><span class="sxs-lookup"><span data-stu-id="a9c75-154">[Turn on Microsoft Threat Protection](mtp-enable.md).</span></span>
- [<span data-ttu-id="a9c75-155">ライセンス要件およびその他の前提条件</span><span class="sxs-lookup"><span data-stu-id="a9c75-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="a9c75-156">サポートされるサービスを展開する</span><span class="sxs-lookup"><span data-stu-id="a9c75-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="a9c75-157">プレビュー機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="a9c75-157">Turn on preview features</span></span>](preview.md)
