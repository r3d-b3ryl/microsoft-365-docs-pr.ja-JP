---
title: Microsoft 365 Multi-Geo
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: seo-marvel-apr2020
ms.collection: Strat_SP_gtc
localization_priority: Normal
f1.keywords:
- NOCSH
description: この記事では、Microsoft 365 Multi-Geo を使用して、複数の地域に Microsoft 365 のプレゼンスを展開する方法について説明します。
ms.openlocfilehash: 17fc2645f69a0d91c71c91718f321e5932d31bd2
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362764"
---
# <a name="microsoft-365-multi-geo"></a><span data-ttu-id="4c8ef-103">Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="4c8ef-103">Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="4c8ef-104">Microsoft 365 Multi-Geo を使用すれば、組織はその組織の Microsoft 365 のプレゼンスを、その既存のテナント内の複数の地域または国に対して展開することができます。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-104">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span> <span data-ttu-id="4c8ef-105">Microsoft アカウント チームと連絡を取り、お客様の多国籍企業を Microsoft 365 Multi-Geo にサインアップしましょう。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-105">Reach out to your Microsoft Account Team to sign up your Multi-National Company for Microsoft 365 Multi-Geo.</span></span>
  
<span data-ttu-id="4c8ef-106">Microsoft 365 Multi-Geo を使用すると、データ所在地に関連する要件を満たすために選択した地域の場所で保存データのプロビジョニングと保存を行うことができ、同時に、モダンな生産性向上エクスペリエンスを従業員に対してグローバルに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-106">With Microsoft 365 Multi-Geo, you can provision and store data at rest in the geo locations that you've chosen to meet data residency requirements, and at the same time unlock your global roll out of modern productivity experiences to your workforce.</span></span>

<span data-ttu-id="4c8ef-107">Microsoft 365 のMulti-Geo の導入ビデオについては、「[SharePoint Online と OneDrive を使用してデータの保存場所を制御する](https://www.youtube.com/watch?v=Do9U3JuROhk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-107">For a video introduction to Microsoft 365 Multi-Geo, see [SharePoint Online and OneDrive Multi-Geo to control where your data resides](https://www.youtube.com/watch?v=Do9U3JuROhk).</span></span>

## <a name="multi-geo-architecture"></a><span data-ttu-id="4c8ef-108">Multi-Geo アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="4c8ef-108">Multi-Geo architecture</span></span>

<span data-ttu-id="4c8ef-109">Multi-Geo 環境では、Microsoft 365 テナントは中央の場所 (Microsoft 365 サブスクリプションが最初にプロビジョニングされた場所) と 1 つ以上のサテライトの場所で構成されています。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-109">In a Multi-Geo environment, your Microsoft 365 tenant consists of a central location (where your Microsoft 365 subscription was originally provisioned) and one or more satellite locations.</span></span> <span data-ttu-id="4c8ef-110">複数地域テナント内では、地理的な場所、グループ、およびユーザー情報に関する情報が、Azure Active Directory (Azure AD) 内でマスター管理されます。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-110">In a multi-geo tenant, the information about geo locations, groups, and user information, is mastered in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="4c8ef-111">テナント情報が集中的にマスター管理され、個々の地理的な場所に同期されるので、その企業のすべてのユーザーが関わる共有とエクスペリエンスにグローバルな情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-111">Because your tenant information is mastered centrally and synchronized into each geo location, sharing and experiences involving anyone from your company contain global awareness.</span></span>

![SharePoint 管理センター メニューの複数地域マップのスクリーンショット](../media/multi-geo-world-map.png)

<span data-ttu-id="4c8ef-113">Microsoft 365 Multi-Geo は、パフォーマンスの最適化を目的とした設計ではなく、データ所在地に関する要件を満たすように設計されていることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-113">Note that Microsoft 365 Multi-Geo is not designed for performance optimization, it is designed to meet data residency requirements.</span></span> <span data-ttu-id="4c8ef-114">Microsoft 365 のパフォーマンスを最適化する方法については、「[Microsoft 365 のネットワーク計画とパフォーマンス チューニング](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848)」を参照するか、サポート グループにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-114">For information about performance optimization for Microsoft 365, see [Network planning and performance tuning for Microsoft 365](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) or contact your support group.</span></span>

## <a name="terminology"></a><span data-ttu-id="4c8ef-115">用語</span><span class="sxs-lookup"><span data-stu-id="4c8ef-115">Terminology</span></span>

<span data-ttu-id="4c8ef-116">Office 365 Multi-Geo の説明に使用される重要な用語を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-116">Here are the key terms used in describing Microsoft 365 Multi-Geo:</span></span>

- <span data-ttu-id="4c8ef-117">**中央の場所** のテナントが最初にプロビジョニングされた地域の場所です。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-117">**Central location** - the geo location where your tenant was originally provisioned.</span></span>
- <span data-ttu-id="4c8ef-118">**地域管理者** - 指定された 1 つ以上のサテライトの場所を管理できる管理者。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-118">**Geo administrator** - An administrator who can administer one or more specified satellite locations.</span></span>
- <span data-ttu-id="4c8ef-119">**地域コード** - 特定の地域の場所を表す 3 文字のコード。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-119">**Geo code** - a three-letter code for a given geo location.</span></span>
- <span data-ttu-id="4c8ef-120">**地域の場所** - Exchange メールボックス、OneDrive サイト、SharePoint サイトなど、データをホストする複数地域テナントで使用できる地理的な場所。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-120">**Geo location** – A geographic location that can be used in a multi-geo tenant to host data, including Exchange mailboxes and OneDrive and SharePoint sites.</span></span>
- <span data-ttu-id="4c8ef-121">**優先されるデータの場所 (PDL)** - 管理者が設定したユーザー プロパティであり、ユーザーの Exchange メールボックスと OneDrive がプロビジョニングされる地域の場所を示します。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-121">**Preferred Data Location (PDL)** – A user property set by the administrator that indicates where the geo location where the users Exchange mailbox and OneDrive should be provisioned.</span></span> <span data-ttu-id="4c8ef-122">PDL では、ユーザーによって作成された SharePoint サイトのプロビジョニング場所も決定されます。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-122">The PDL also determines where SharePoint sites that are created by the user are provisioned.</span></span>
- <span data-ttu-id="4c8ef-123">**サテライトの場所** - 地理機能に対応している Microsoft 365 ワークロード (SharePoint、OneDrive、Exchange) が複数地域テナントで有効になっている地域の場所。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-123">**Satellite location** – The geo locations where the geo-aware Microsoft 365 workloads (SharePoint, OneDrive, and Exchange) are enabled in a multi-geo tenant.</span></span>
- <span data-ttu-id="4c8ef-124">**テナント** - Microsoft 365 における組織の表現。通常、1 つ以上のドメインが関連付けられています (例: contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-124">**Tenant** – An organization's representation in Microsoft 365 which typically has one or more domains associated with it (for example, contoso.com).</span></span>

## <a name="licensing"></a><span data-ttu-id="4c8ef-125">ライセンス</span><span class="sxs-lookup"><span data-stu-id="4c8ef-125">Licensing</span></span>

<span data-ttu-id="4c8ef-126">Microsoft 365マルチジオは、テナント内に少なくとも 250 Microsoft 365 シートを持ち、複数地域を使用しているシートの 5% 以上を持つ Enterprise Agreement のお客様に対して、次の Microsoft 365 サブスクリプション プランのアドオンとして利用できます。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-126">Microsoft 365 Multi-Geo is available as an add-on to the following Microsoft 365 subscription plans for Enterprise Agreement customers with a minimum of 250 Microsoft 365 seats in their tenant, and a minimum of 5% of those seats using multi-geo.</span></span> <span data-ttu-id="4c8ef-127">ユーザー サブスクリプション ライセンスは、複数地域サービス Enterprise Agreementと同じライセンス上にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-127">User subscription licenses must be on the same Enterprise Agreement as the Multi-Geo Services licenses.</span></span> <span data-ttu-id="4c8ef-128">詳細については、Microsoft アカウント チームにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-128">Please contact your Microsoft account team for details.</span></span>

- <span data-ttu-id="4c8ef-129">Microsoft 365 F1、F3、E3、または E5</span><span class="sxs-lookup"><span data-stu-id="4c8ef-129">Microsoft 365 F1, F3, E3, or E5</span></span>
- <span data-ttu-id="4c8ef-130">Office 365 F3、 E1、 E3、または E5</span><span class="sxs-lookup"><span data-stu-id="4c8ef-130">Office 365 F3, E1, E3, or E5</span></span>
- <span data-ttu-id="4c8ef-131">Exchange Online プラン 1 またはプラン 2</span><span class="sxs-lookup"><span data-stu-id="4c8ef-131">Exchange Online Plan 1 or Plan 2</span></span>
- <span data-ttu-id="4c8ef-132">OneDrive for Business プラン 1 またはプラン 2</span><span class="sxs-lookup"><span data-stu-id="4c8ef-132">OneDrive for Business Plan 1 or Plan 2</span></span>
- <span data-ttu-id="4c8ef-133">SharePoint Online プラン 1 またはプラン 2</span><span class="sxs-lookup"><span data-stu-id="4c8ef-133">SharePoint Online Plan 1 or Plan 2</span></span>

<span data-ttu-id="4c8ef-134">ライセンスがユーザーに割り当てられた後で削除された場合、Teamsのチャット データがキューに登録され、中央の場所に戻されます。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-134">If a license is assigned to a user and later removed, Teams user chat data is queued to be moved back to the central location.</span></span> <span data-ttu-id="4c8ef-135">SharePointおよびExchangeデータは移動されません。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-135">SharePoint and Exchange data is not moved.</span></span>

## <a name="microsoft-365-multi-geo-availability"></a><span data-ttu-id="4c8ef-136">Microsoft 365 Multi-Geo の利用可能地域</span><span class="sxs-lookup"><span data-stu-id="4c8ef-136">Microsoft 365 Multi-Geo availability</span></span>

<span data-ttu-id="4c8ef-137">現在、Microsoft 365 Multi-Geo は次の地域と国で提供されています。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-137">Microsoft 365 Multi-Geo is currently offered in these regions and countries:</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="getting-started"></a><span data-ttu-id="4c8ef-138">はじめに</span><span class="sxs-lookup"><span data-stu-id="4c8ef-138">Getting started</span></span>

<span data-ttu-id="4c8ef-139">以下の手順に従って複数地域を開始しましょう。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-139">Follow these steps to get started with multi-geo:</span></span>

1. <span data-ttu-id="4c8ef-140">アカウント チームと協力して、_Microsoft 365 の複数地域機能_ をサービス プランに追加します。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-140">Work with your account team to add the _Multi-Geo Capabilities in Microsoft 365_ service plan.</span></span> <span data-ttu-id="4c8ef-141">必要なライセンス数の追加方法を説明いたします。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-141">They will guide you to add the number of licenses needed.</span></span> <span data-ttu-id="4c8ef-142">Multi-Geo 機能は、250 以上の Microsoft 365 サブスクリプションを使用している EA のお客様が利用できます。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-142">Multi-Geo feature is available to EA customers with a minimum of 250 Microsoft 365 subscriptions.</span></span>

   <span data-ttu-id="4c8ef-143">Microsoft 365 Multi-Geo の使用を開始するには、事前に Microsoft が複数地域サポート用に Exchange Online テナントを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-143">Before you can start using Microsoft 365 Multi-Geo, Microsoft needs to configure your Exchange Online tenant for multi-geo support.</span></span> <span data-ttu-id="4c8ef-144">この 1 回限りの構成プロセスは、*Microsoft 365 の複数地域機能* サービス プランを注文し、ライセンスがテナントに表示された後にトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-144">This one-time configuration process is triggered after you order the *Multi-Geo Capabilities in Microsoft 365* service plan and the licenses show up in your tenant.</span></span> <span data-ttu-id="4c8ef-145">テナントが各ワークロードの構成プロセスを完了すると[、Microsoft 365](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093)メッセージ センターでワークロード固有の通知を受け取り、Microsoft 365 Multi-Geo 機能の構成と使用を開始できます。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-145">You will receive workload-specific notifications in the [Microsoft 365 message center](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093) once your tenant has completed the configuration process for each workload, and you then may begin configuring and using your Microsoft 365 Multi-Geo capabilities.</span></span> <span data-ttu-id="4c8ef-146">Multi-Geo サポート用にテナントを構成するために必要な時間は、テナントによって異なりますが、多くのテナントは機能ライセンスの受信後 1か月以内に終了します。 </span><span class="sxs-lookup"><span data-stu-id="4c8ef-146">The time required to configure a tenant for Multi-Geo support varies from tenant to tenant, but most tenants finish within a month after receipt of the feature licenses.</span></span> <span data-ttu-id="4c8ef-147">大型または複雑なテナントの場合は、構成プロセスの完了により多くの時間が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-147">Larger or more complex tenants may require more time to complete the configuration process.</span></span> <span data-ttu-id="4c8ef-148">必要な場合は、特定のテナントの詳細をお客様のアカウント チームにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-148">Please contact your account team for details on your specific tenant should you require it.</span></span>

2. <span data-ttu-id="4c8ef-149">「[OneDrive for Business 複数地域の計画](plan-for-multi-geo.md)」を参照します。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-149">Read [Plan your multi-geo environment](plan-for-multi-geo.md).</span></span>

3. <span data-ttu-id="4c8ef-150">[複数地域環境の管理](administering-a-multi-geo-environment.md)および[環境でのユーザー エクスペリエンス](multi-geo-user-experience.md)について確認します。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-150">Learn about [administering a multi-geo environment](administering-a-multi-geo-environment.md) and [how your users will experience the environment](multi-geo-user-experience.md).</span></span>

4. <span data-ttu-id="4c8ef-151">Microsoft 365 Multi-Geo のセットアップ準備ができたら、[複数地域用のテナントを構成します](multi-geo-tenant-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-151">When you are ready to set up Microsoft 365 Multi-Geo, [configure your tenant for multi-geo](multi-geo-tenant-configuration.md).</span></span>

5. <span data-ttu-id="4c8ef-152">[検索を設定します](configure-search-for-multi-geo.md)。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-152">[Set up search](configure-search-for-multi-geo.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4c8ef-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="4c8ef-153">See also</span></span>

[<span data-ttu-id="4c8ef-154">Exchange OnlineとOneDriveでの複数地域機能</span><span class="sxs-lookup"><span data-stu-id="4c8ef-154">Multi-Geo in Exchange Online and OneDrive</span></span>](https://Aka.ms/GoMultiGeo)

[<span data-ttu-id="4c8ef-155">OneDrive および SharePoint Online の複数地域機能</span><span class="sxs-lookup"><span data-stu-id="4c8ef-155">Multi-Geo Capabilities in OneDrive and SharePoint Online</span></span>](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)

[<span data-ttu-id="4c8ef-156">Exchange Online の複数地域機能</span><span class="sxs-lookup"><span data-stu-id="4c8ef-156">Multi-Geo Capabilities in Exchange Online</span></span>](multi-geo-capabilities-in-exchange-online.md)

[<span data-ttu-id="4c8ef-157">複数地域環境での Teams エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="4c8ef-157">Teams experience in a multi-geo environment</span></span>](/microsoftteams/teams-experience-o365odb-spo-multi-geo)