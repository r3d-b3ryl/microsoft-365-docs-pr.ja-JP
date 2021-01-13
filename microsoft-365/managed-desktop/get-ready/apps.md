---
title: Microsoft マネージド デスクトップのアプリ
description: アプリのパッケージ化、展開、サポートの方法など、アプリの処理方法について説明します。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 20d68ec007ccda82816ad2288428016019f6d4b2
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840695"
---
# <a name="apps-in-microsoft-managed-desktop"></a><span data-ttu-id="3bed1-104">Microsoft マネージド デスクトップのアプリ</span><span class="sxs-lookup"><span data-stu-id="3bed1-104">Apps in Microsoft Managed Desktop</span></span>

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a><span data-ttu-id="3bed1-105">一般的なアプリ</span><span class="sxs-lookup"><span data-stu-id="3bed1-105">Apps generally</span></span>

<span data-ttu-id="3bed1-106">Microsoft には、Microsoft マネージド デスクトップへの参加に必要な Microsoft 365 E3 または E5 ライセンスと共に、特定の主要なアプリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3bed1-106">Microsoft includes certain key apps along with the Microsoft 365 E3 or E5 license needed to participate in Microsoft Managed Desktop.</span></span> <span data-ttu-id="3bed1-107">ただし、これらのアプリが提供されている場合でも、お客様には完了する特定の責任とアクションがあります。</span><span class="sxs-lookup"><span data-stu-id="3bed1-107">However, even though we provide these apps, you still have certain responsibilities and actions to complete.</span></span>

<span data-ttu-id="3bed1-108">また、Microsoft Intune の展開パイプラインを使用して、セルフサービス用の追加の Microsoft 以外のアプリをユーザーに展開したり、必要なバックグラウンド インストールを使用したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="3bed1-108">You can also deploy additional non-Microsoft apps to your users for self-service through the Company Portal or a required background installation, all using Microsoft Intune’s deployment pipeline.</span></span> <span data-ttu-id="3bed1-109">専門知識を持っている場合は、自分で必要なアプリを移行できます。または、Microsoft コンサルティング サービス (MCS) または Microsoft 以外のベンダーが、パッケージ化と移行プロジェクトを支援します。</span><span class="sxs-lookup"><span data-stu-id="3bed1-109">If you have the expertise, you can migrate those apps you need yourself; alternatively, Microsoft Consulting Services (MCS) or non-Microsoft vendors will be happy to help you with a packaging and migration project.</span></span> <span data-ttu-id="3bed1-110">MCS の操作の詳細については、「Microsoft Consulting Services を使用する [」を参照してください](apps-MCS.md)。</span><span class="sxs-lookup"><span data-stu-id="3bed1-110">For more information about working with MCS, see [Working with Microsoft Consulting Services](apps-MCS.md).</span></span>


## <a name="apps-provided-by-microsoft"></a><span data-ttu-id="3bed1-111">Microsoft が提供するアプリ</span><span class="sxs-lookup"><span data-stu-id="3bed1-111">Apps provided by Microsoft</span></span>

<span data-ttu-id="3bed1-112">Microsoft マネージド デスクトップ ライセンスには、Microsoft 365 Apps for enterprise Standard Suite (Word、Excel、PowerPoint、Outlook、Publisher、Access、Skype for Business、OneNote) の 64 ビット バージョンのアプリが含まれています。Microsoft Project および Visio のクリック実行バージョンは既定では含まれていませんが、追加を要求できます。</span><span class="sxs-lookup"><span data-stu-id="3bed1-112">Included with your Microsoft Managed Desktop license are 64-bit versions of the apps in the Microsoft 365 Apps for enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, and OneNote.) Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but you can request them to be added.</span></span> <span data-ttu-id="3bed1-113">これらのアプリの詳細については、「Microsoft マネージ デスクトップ デバイスへの [Microsoft Project または Microsoft Visio のインストール」を参照してください](../get-started/project-visio.md)。</span><span class="sxs-lookup"><span data-stu-id="3bed1-113">For more information about these apps, see [Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices](../get-started/project-visio.md).</span></span>

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a><span data-ttu-id="3bed1-114">Microsoft が提供するアプリをサポートするために行う機能</span><span class="sxs-lookup"><span data-stu-id="3bed1-114">What Microsoft does to support the apps we provide</span></span>

<span data-ttu-id="3bed1-115">Microsoft は、付属の Microsoft 365 Apps for enterprise アプリの展開、更新、サポートに関する完全なサービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="3bed1-115">Microsoft will provide full service for the deployment, update, and support for the included Microsoft 365 Apps for enterprise apps.</span></span> <span data-ttu-id="3bed1-116">既定では、Microsoft Project および Visio のClick-to-Run バージョンは含まれていませんが、Microsoft マネージド デスクトップには展開グループが提供され、IT 管理者はライセンスを管理し、これらのアプリケーションを組織に適した方法で展開できます。</span><span class="sxs-lookup"><span data-stu-id="3bed1-116">Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but Microsoft Managed Desktop will provide deployment groups allowing your IT administrator to manage licenses and deploy these applications appropriately for your organization.</span></span> <span data-ttu-id="3bed1-117">Microsoft は、Microsoft マネージド デスクトップ のサポート チャネルを通じて、これらのアプリケーションのユーザーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="3bed1-117">Microsoft will support users of these applications through the Microsoft Managed Desktop support channels.</span></span>

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a><span data-ttu-id="3bed1-118">提供するアプリをサポートするために必要な操作</span><span class="sxs-lookup"><span data-stu-id="3bed1-118">What you need to do to support the apps we provide</span></span>

<span data-ttu-id="3bed1-119">これらのアプリで行う必要のある特定の操作がまだ存在します。</span><span class="sxs-lookup"><span data-stu-id="3bed1-119">There are still certain things you need to do with these apps:</span></span>

- <span data-ttu-id="3bed1-120">**ライセンスの割** り当て - Microsoft 365 Apps for enterprise のユーザーに適切なライセンスを取得して割り当てる責任があります。</span><span class="sxs-lookup"><span data-stu-id="3bed1-120">**Assign licenses** - You are responsible for obtaining and assigning the appropriate licenses to users for Microsoft 365 Apps for enterprise.</span></span>
- <span data-ttu-id="3bed1-121">**セキュリティ グループに** ユーザーを追加する - Microsoft Project または Visio を使用している場合、IT 管理者はそれらのユーザーを適切な展開グループに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3bed1-121">**Add users to security groups** - If you're using Microsoft Project or Visio, your IT administrator must add those users to the appropriate deployment groups.</span></span> <span data-ttu-id="3bed1-122">IT 管理者は、離社したユーザーからライセンスを解放する責任も負います。</span><span class="sxs-lookup"><span data-stu-id="3bed1-122">IT administrators are also responsible for reclaiming licenses from those users if they leave the company.</span></span>
- <span data-ttu-id="3bed1-123">**Microsoft 365** アドオンの展開 - Microsoft 365 Apps for enterprise アプリのアドオンが必要な場合は、他の Windows 32 アプリと同じ方法で一中心に展開します。</span><span class="sxs-lookup"><span data-stu-id="3bed1-123">**Deploy Microsoft 365 Add-ons** - If you need any Add-ons for any of the Microsoft 365 Apps for enterprise apps, deploy them centrally like any other Windows 32 app.</span></span> 

## <a name="apps-you-provide"></a><span data-ttu-id="3bed1-124">提供するアプリ</span><span class="sxs-lookup"><span data-stu-id="3bed1-124">Apps you provide</span></span>

<span data-ttu-id="3bed1-125">業務に必要な他のアプリがある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3bed1-125">You probably have other apps you need for your business operations.</span></span> <span data-ttu-id="3bed1-126">これらのアプリは、Microsoft Intune の展開パイプラインを使用して、Microsoft マネージド デスクトップ デバイスにのみ展開できます。</span><span class="sxs-lookup"><span data-stu-id="3bed1-126">These apps can only be deployed to Microsoft Managed Desktop devices by using Microsoft Intune’s deployment pipeline.</span></span> <span data-ttu-id="3bed1-127">アプリに必要な場合は、ベンダー (Microsoft 以外のベンダーまたは Microsoft Consulting Services (MCS) の可能性があります) によってパッケージ化するか、または手段がある場合は、自分でパッケージ化することができます。</span><span class="sxs-lookup"><span data-stu-id="3bed1-127">If the app needs it you can have them packaged by a vendor (which could be a non-Microsoft vendor or Microsoft Consulting Services (MCS)) or if you have the means, you can package them yourself.</span></span> <span data-ttu-id="3bed1-128">次に、これらのパッケージを Microsoft マネージド デスクトップ ポータルに追加し、Azure Active Directory グループに割り当て、展開をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="3bed1-128">You then add these packages to the Microsoft Managed Desktop portal and assign them to Azure Active Directory groups to trigger the deployment.</span></span> 

<span data-ttu-id="3bed1-129">現在 Microsoft Endpoint Configuration Manager を使用してアプリを展開している場合、Microsoft マネージド デスクトップでは、アプリを評価し、Microsoft Intune に移行する準備ができているアプリと調整が必要なアプリを検出するためのクエリを提供できます。</span><span class="sxs-lookup"><span data-stu-id="3bed1-129">If you currently deploy your apps by using Microsoft Endpoint Configuration Manager, Microsoft Managed Desktop can provide you with a query to assess your apps and discover which ones are ready for to migrate to Microsoft Intune and which ones might require some adjustment.</span></span>


### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a><span data-ttu-id="3bed1-130">Microsoft マネージド デスクトップに含める独自のアプリの準備</span><span class="sxs-lookup"><span data-stu-id="3bed1-130">Preparing your own apps for inclusion in Microsoft Managed Desktop</span></span>
<span data-ttu-id="3bed1-131">アプリを確認し、次のチェックを行います。</span><span class="sxs-lookup"><span data-stu-id="3bed1-131">Review your apps, checking:</span></span>

- <span data-ttu-id="3bed1-132">Microsoft マネージド デスクトップ アプリの要件に記載されているとおり、どのアプリも禁止も動作 [も制限されません](https://aka.ms/app-req)。</span><span class="sxs-lookup"><span data-stu-id="3bed1-132">None of the apps are prohibited or have restricted behavior, as described in [Microsoft Managed Desktop app requirements](https://aka.ms/app-req).</span></span>
- <span data-ttu-id="3bed1-133">アプリは、Microsoft Intune による管理の準備ができている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3bed1-133">Apps must be ready for management by Microsoft Intune.</span></span> <span data-ttu-id="3bed1-134">このトピックの詳細については、「Microsoft Intune を使用した [Windows 10 アプリ](https://docs.microsoft.com/intune/apps-windows-10-app-deploy) の展開」と「Microsoft Intune にアプリを追加する」を [参照してください](https://docs.microsoft.com/intune/apps-add)。</span><span class="sxs-lookup"><span data-stu-id="3bed1-134">For more about this topic, see [Windows 10 app deployment using Microsoft Intune](https://docs.microsoft.com/intune/apps-windows-10-app-deploy) and [Add apps to Microsoft Intune](https://docs.microsoft.com/intune/apps-add).</span></span>
- <span data-ttu-id="3bed1-135">ライセンス キーの提供、ライセンス条項との合意、サーバー接続の事前設定など、パッケージ化前のその他の要件。</span><span class="sxs-lookup"><span data-stu-id="3bed1-135">Other pre-packaging requirements such as providing license keys, agreement with license terms, and pre-setting server connections.</span></span>

### <a name="decide-how-to-package-apps"></a><span data-ttu-id="3bed1-136">アプリをパッケージ化する方法を決定する</span><span class="sxs-lookup"><span data-stu-id="3bed1-136">Decide how to package apps</span></span>

<span data-ttu-id="3bed1-137">一部の独立系ソフトウェア発行元では、アプリを一元的に展開する前にパッケージ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3bed1-137">Some independent software publishers might require that your apps are packaged before they are centrally deployed.</span></span> <span data-ttu-id="3bed1-138">"パッケージ化" とは、アプリをバックグラウンドでインストールできるよう、ライセンス キー、リモート サーバーの場所、デスクトップ ショートカットのような設定でアプリのインストーラーが構成されていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="3bed1-138">“Packaging” means that the app’s installer is configured with settings like license keys, remote server locations, or desktop shortcuts so that the app can be installed in the background.</span></span>

<span data-ttu-id="3bed1-139">アプリをパッケージ化するには、次の 3 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="3bed1-139">There are three options to get your apps packaged:</span></span> 


- <span data-ttu-id="3bed1-140">自分でアプリをパッケージ化できます</span><span class="sxs-lookup"><span data-stu-id="3bed1-140">You can package apps yourself</span></span>
- <span data-ttu-id="3bed1-141">Microsoft 以外のベンダーと一緒に作業できます</span><span class="sxs-lookup"><span data-stu-id="3bed1-141">You can work with a non-Microsoft vendor</span></span>
- <span data-ttu-id="3bed1-142">MCS を使ってアプリをパッケージ化できます。</span><span class="sxs-lookup"><span data-stu-id="3bed1-142">You can engage with MCS to package your apps.</span></span> <span data-ttu-id="3bed1-143">Microsoft アカウントの担当者と一緒に作業します。</span><span class="sxs-lookup"><span data-stu-id="3bed1-143">Work with your Microsoft account representative.</span></span> <span data-ttu-id="3bed1-144">詳細については [、「Microsoft Consulting Services の使用」を参照してください](apps-MCS.md)。</span><span class="sxs-lookup"><span data-stu-id="3bed1-144">For more information, see [Working with Microsoft Consulting Services](apps-MCS.md).</span></span>



## <a name="deploying-apps"></a><span data-ttu-id="3bed1-145">アプリの展開</span><span class="sxs-lookup"><span data-stu-id="3bed1-145">Deploying apps</span></span>

<span data-ttu-id="3bed1-146">アプリのパッケージ化に使用する方法は何でも、完了したら、「Microsoft マネージド デスクトップ デバイスにアプリを展開する」の手順 [に従う準備が整います](../get-started/deploy-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="3bed1-146">Whatever method you use to get apps packaged, once that is complete, you're ready to follow the steps in [Deploy apps to Microsoft Managed Desktop devices](../get-started/deploy-apps.md).</span></span>


