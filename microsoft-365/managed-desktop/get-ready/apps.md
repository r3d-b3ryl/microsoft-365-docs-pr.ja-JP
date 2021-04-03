---
title: Microsoft マネージド デスクトップのアプリ
description: アプリのパッケージ化、展開、サポート方法など、アプリの処理方法について説明します。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: d970ac1a28c62703f648e4fbf6f66e2f825a6188
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574621"
---
# <a name="apps-in-microsoft-managed-desktop"></a><span data-ttu-id="f31b8-104">Microsoft マネージド デスクトップのアプリ</span><span class="sxs-lookup"><span data-stu-id="f31b8-104">Apps in Microsoft Managed Desktop</span></span>

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a><span data-ttu-id="f31b8-105">一般にアプリ</span><span class="sxs-lookup"><span data-stu-id="f31b8-105">Apps generally</span></span>

<span data-ttu-id="f31b8-106">Microsoft には、Microsoft Managed Desktop への参加に必要な Microsoft 365 E3 または E5 ライセンスと共に、特定の主要アプリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f31b8-106">Microsoft includes certain key apps along with the Microsoft 365 E3 or E5 license needed to participate in Microsoft Managed Desktop.</span></span> <span data-ttu-id="f31b8-107">ただし、これらのアプリを提供する場合でも、実行する一定の責任とアクションがあります。</span><span class="sxs-lookup"><span data-stu-id="f31b8-107">However, even though we provide these apps, you still have certain responsibilities and actions to complete.</span></span>

<span data-ttu-id="f31b8-108">また、Microsoft Intune の展開パイプラインを使用して、追加の Microsoft 以外のアプリをセルフサービス用にユーザーに展開したり、必要なバックグラウンド インストールを実行したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f31b8-108">You can also deploy additional non-Microsoft apps to your users for self-service through the Company Portal or a required background installation, all using Microsoft Intune’s deployment pipeline.</span></span> <span data-ttu-id="f31b8-109">専門知識を持っている場合は、自分で必要なアプリを移行できます。または、Microsoft コンサルティング サービス (MCS) または Microsoft 以外のベンダーが、パッケージ化と移行プロジェクトを支援します。</span><span class="sxs-lookup"><span data-stu-id="f31b8-109">If you have the expertise, you can migrate those apps you need yourself; alternatively, Microsoft Consulting Services (MCS) or non-Microsoft vendors will be happy to help you with a packaging and migration project.</span></span> <span data-ttu-id="f31b8-110">MCS の操作の詳細については、「Microsoft コンサルティング サービスの使用 [」を参照してください](apps-MCS.md)。</span><span class="sxs-lookup"><span data-stu-id="f31b8-110">For more information about working with MCS, see [Working with Microsoft Consulting Services](apps-MCS.md).</span></span>


## <a name="apps-provided-by-microsoft"></a><span data-ttu-id="f31b8-111">Microsoft が提供するアプリ</span><span class="sxs-lookup"><span data-stu-id="f31b8-111">Apps provided by Microsoft</span></span>

<span data-ttu-id="f31b8-112">Microsoft Managed Desktop ライセンスには、Microsoft 365 Apps for enterprise Standard Suite (Word、Excel、PowerPoint、Outlook、Publisher、Access、Skype for Business、OneNote) の 64 ビット バージョンのアプリが含まれています。クイック実行バージョンの Microsoft Project と Visioは既定では含まれていませんが、追加を要求できます。</span><span class="sxs-lookup"><span data-stu-id="f31b8-112">Included with your Microsoft Managed Desktop license are 64-bit versions of the apps in the Microsoft 365 Apps for enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, and OneNote.) Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but you can request them to be added.</span></span> <span data-ttu-id="f31b8-113">これらのアプリの詳細については、「Microsoft マネージ デスクトップ デバイスに Microsoft Project または Microsoft Visio をインストールする [」を参照してください](../get-started/project-visio.md)。</span><span class="sxs-lookup"><span data-stu-id="f31b8-113">For more information about these apps, see [Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices](../get-started/project-visio.md).</span></span>

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a><span data-ttu-id="f31b8-114">Microsoft が提供するアプリをサポートするために行う機能</span><span class="sxs-lookup"><span data-stu-id="f31b8-114">What Microsoft does to support the apps we provide</span></span>

<span data-ttu-id="f31b8-115">Microsoft は、付属の Microsoft 365 Apps for enterprise Apps の展開、更新、およびサポートのためのフル サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="f31b8-115">Microsoft will provide full service for the deployment, update, and support for the included Microsoft 365 Apps for enterprise apps.</span></span> <span data-ttu-id="f31b8-116">クイック実行バージョンの Microsoft Project と Visioは既定では含まれていませんが、Microsoft Managed Desktop には展開グループが提供され、IT 管理者はライセンスを管理し、組織に合わせてこれらのアプリケーションを適切に展開できます。</span><span class="sxs-lookup"><span data-stu-id="f31b8-116">Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but Microsoft Managed Desktop will provide deployment groups allowing your IT administrator to manage licenses and deploy these applications appropriately for your organization.</span></span> <span data-ttu-id="f31b8-117">Microsoft は、Microsoft Managed Desktop サポート チャネルを通じてこれらのアプリケーションのユーザーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="f31b8-117">Microsoft will support users of these applications through the Microsoft Managed Desktop support channels.</span></span>

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a><span data-ttu-id="f31b8-118">提供するアプリをサポートするために必要な操作</span><span class="sxs-lookup"><span data-stu-id="f31b8-118">What you need to do to support the apps we provide</span></span>

<span data-ttu-id="f31b8-119">これらのアプリで行う必要がある特定の操作がまだ存在します。</span><span class="sxs-lookup"><span data-stu-id="f31b8-119">There are still certain things you need to do with these apps:</span></span>

- <span data-ttu-id="f31b8-120">**ライセンスの割り** 当て - Microsoft 365 Apps for enterprise のユーザーに適切なライセンスを取得して割り当てる責任があります。</span><span class="sxs-lookup"><span data-stu-id="f31b8-120">**Assign licenses** - You are responsible for obtaining and assigning the appropriate licenses to users for Microsoft 365 Apps for enterprise.</span></span>
- <span data-ttu-id="f31b8-121">**セキュリティ グループにユーザーを追加** する - Microsoft Project または Visio を使用している場合、IT 管理者はそれらのユーザーを適切な展開グループに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f31b8-121">**Add users to security groups** - If you're using Microsoft Project or Visio, your IT administrator must add those users to the appropriate deployment groups.</span></span> <span data-ttu-id="f31b8-122">IT 管理者は、会社を離れた場合にそれらのユーザーからライセンスを再利用する責任も負います。</span><span class="sxs-lookup"><span data-stu-id="f31b8-122">IT administrators are also responsible for reclaiming licenses from those users if they leave the company.</span></span>
- <span data-ttu-id="f31b8-123">**Microsoft 365** アドオンを展開する - エンタープライズ アプリ用の Microsoft 365 アプリのアドオンが必要な場合は、他の Windows 32 アプリと同様に一中心に展開します。</span><span class="sxs-lookup"><span data-stu-id="f31b8-123">**Deploy Microsoft 365 Add-ons** - If you need any Add-ons for any of the Microsoft 365 Apps for enterprise apps, deploy them centrally like any other Windows 32 app.</span></span> 

## <a name="apps-you-provide"></a><span data-ttu-id="f31b8-124">提供するアプリ</span><span class="sxs-lookup"><span data-stu-id="f31b8-124">Apps you provide</span></span>

<span data-ttu-id="f31b8-125">ビジネス操作に必要な他のアプリがある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f31b8-125">You probably have other apps you need for your business operations.</span></span> <span data-ttu-id="f31b8-126">これらのアプリは、Microsoft Intune の展開パイプラインを使用して Microsoft Managed Desktop デバイスにのみ展開できます。</span><span class="sxs-lookup"><span data-stu-id="f31b8-126">These apps can only be deployed to Microsoft Managed Desktop devices by using Microsoft Intune’s deployment pipeline.</span></span> <span data-ttu-id="f31b8-127">アプリが必要とする場合は、ベンダー (Microsoft 以外のベンダーまたは Microsoft コンサルティング サービス (MCS) の場合) によってパッケージ化するか、手段がある場合は、自分でパッケージ化できます。</span><span class="sxs-lookup"><span data-stu-id="f31b8-127">If the app needs it you can have them packaged by a vendor (which could be a non-Microsoft vendor or Microsoft Consulting Services (MCS)) or if you have the means, you can package them yourself.</span></span> <span data-ttu-id="f31b8-128">次に、これらのパッケージを Microsoft Managed Desktop ポータルに追加し、それらを Azure Active Directory グループに割り当て、展開をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="f31b8-128">You then add these packages to the Microsoft Managed Desktop portal and assign them to Azure Active Directory groups to trigger the deployment.</span></span> 

<span data-ttu-id="f31b8-129">現在、Microsoft Endpoint Configuration Manager を使用してアプリを展開している場合、Microsoft Managed Desktop は、アプリを評価し、Microsoft Intune に移行する準備ができているアプリと、調整が必要になる可能性のあるアプリを検出するためのクエリを提供できます。</span><span class="sxs-lookup"><span data-stu-id="f31b8-129">If you currently deploy your apps by using Microsoft Endpoint Configuration Manager, Microsoft Managed Desktop can provide you with a query to assess your apps and discover which ones are ready for to migrate to Microsoft Intune and which ones might require some adjustment.</span></span>


### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a><span data-ttu-id="f31b8-130">Microsoft Managed Desktop に含める独自のアプリを準備する</span><span class="sxs-lookup"><span data-stu-id="f31b8-130">Preparing your own apps for inclusion in Microsoft Managed Desktop</span></span>
<span data-ttu-id="f31b8-131">アプリを確認し、次のチェックを行います。</span><span class="sxs-lookup"><span data-stu-id="f31b8-131">Review your apps, checking:</span></span>

- <span data-ttu-id="f31b8-132">Microsoft [Managed Desktop](../service-description/mmd-app-requirements.md)アプリの要件で説明されているとおり、禁止または制限された動作を持つアプリはありません。</span><span class="sxs-lookup"><span data-stu-id="f31b8-132">None of the apps are prohibited or have restricted behavior, as described in [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).</span></span>
- <span data-ttu-id="f31b8-133">アプリは、Microsoft Intune による管理の準備ができている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f31b8-133">Apps must be ready for management by Microsoft Intune.</span></span> <span data-ttu-id="f31b8-134">このトピックの詳細については、「Microsoft Intune を使用した [Windows 10 アプリ](/intune/apps-windows-10-app-deploy) の展開」および「Microsoft Intune にアプリを追加する」 [を参照してください](/intune/apps-add)。</span><span class="sxs-lookup"><span data-stu-id="f31b8-134">For more about this topic, see [Windows 10 app deployment using Microsoft Intune](/intune/apps-windows-10-app-deploy) and [Add apps to Microsoft Intune](/intune/apps-add).</span></span>
- <span data-ttu-id="f31b8-135">ライセンス キーの提供、ライセンス条項との契約、サーバー接続の事前設定など、その他の事前パッケージ化要件。</span><span class="sxs-lookup"><span data-stu-id="f31b8-135">Other pre-packaging requirements such as providing license keys, agreement with license terms, and pre-setting server connections.</span></span>

### <a name="decide-how-to-package-apps"></a><span data-ttu-id="f31b8-136">アプリをパッケージ化する方法を決定する</span><span class="sxs-lookup"><span data-stu-id="f31b8-136">Decide how to package apps</span></span>

<span data-ttu-id="f31b8-137">独立したソフトウェア発行元によっては、アプリを一元的に展開する前にパッケージ化する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="f31b8-137">Some independent software publishers might require that your apps are packaged before they are centrally deployed.</span></span> <span data-ttu-id="f31b8-138">"パッケージ化" とは、アプリをバックグラウンドでインストールできるよう、アプリのインストーラーがライセンス キー、リモート サーバーの場所、デスクトップ ショートカットのような設定で構成されていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="f31b8-138">“Packaging” means that the app’s installer is configured with settings like license keys, remote server locations, or desktop shortcuts so that the app can be installed in the background.</span></span>

<span data-ttu-id="f31b8-139">アプリをパッケージ化するには、次の 3 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="f31b8-139">There are three options to get your apps packaged:</span></span> 


- <span data-ttu-id="f31b8-140">自分でアプリをパッケージ化できます</span><span class="sxs-lookup"><span data-stu-id="f31b8-140">You can package apps yourself</span></span>
- <span data-ttu-id="f31b8-141">Microsoft 以外のベンダーと作業できます</span><span class="sxs-lookup"><span data-stu-id="f31b8-141">You can work with a non-Microsoft vendor</span></span>
- <span data-ttu-id="f31b8-142">MCS に参加してアプリをパッケージ化できます。</span><span class="sxs-lookup"><span data-stu-id="f31b8-142">You can engage with MCS to package your apps.</span></span> <span data-ttu-id="f31b8-143">Microsoft アカウント担当者と一緒に作業します。</span><span class="sxs-lookup"><span data-stu-id="f31b8-143">Work with your Microsoft account representative.</span></span> <span data-ttu-id="f31b8-144">詳細については [、「Microsoft コンサルティング サービスの操作」を参照してください](apps-MCS.md)。</span><span class="sxs-lookup"><span data-stu-id="f31b8-144">For more information, see [Working with Microsoft Consulting Services](apps-MCS.md).</span></span>



## <a name="deploying-apps"></a><span data-ttu-id="f31b8-145">アプリの展開</span><span class="sxs-lookup"><span data-stu-id="f31b8-145">Deploying apps</span></span>

<span data-ttu-id="f31b8-146">アプリをパッケージ化するために使用する方法が何であれ、完了したら、「アプリを Microsoft Managed Desktop デバイスに展開する」の手順に従 [う準備ができました](../get-started/deploy-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="f31b8-146">Whatever method you use to get apps packaged, once that is complete, you're ready to follow the steps in [Deploy apps to Microsoft Managed Desktop devices](../get-started/deploy-apps.md).</span></span>


## <a name="steps-to-get-ready"></a><span data-ttu-id="f31b8-147">準備の手順</span><span class="sxs-lookup"><span data-stu-id="f31b8-147">Steps to get ready</span></span>

1. <span data-ttu-id="f31b8-148">「Microsoft [Managed Desktop の前提条件」を参照してください](prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="f31b8-148">Review [Prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="f31b8-149">準備 [状況評価ツールを使用します](readiness-assessment-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="f31b8-149">Use [Readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. [<span data-ttu-id="f31b8-150">ゲスト アカウントの前提条件</span><span class="sxs-lookup"><span data-stu-id="f31b8-150">Prerequisites for guest accounts</span></span>](guest-accounts.md)
4. [<span data-ttu-id="f31b8-151">Microsoft マネージド デスクトップのネットワーク構成</span><span class="sxs-lookup"><span data-stu-id="f31b8-151">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. [<span data-ttu-id="f31b8-152">Microsoft マネージド デスクトップ用に証明書とネットワーク プロファイルを準備する</span><span class="sxs-lookup"><span data-stu-id="f31b8-152">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>](certs-wifi-lan.md)
6. [<span data-ttu-id="f31b8-153">Microsoft マネージド デスクトップ用にオンプレミス リソースアクセスを準備する</span><span class="sxs-lookup"><span data-stu-id="f31b8-153">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. <span data-ttu-id="f31b8-154">[Microsoft Managed Desktop のアプリ](apps.md) (この記事)</span><span class="sxs-lookup"><span data-stu-id="f31b8-154">[Apps in Microsoft Managed Desktop](apps.md) (This article)</span></span>
8. [<span data-ttu-id="f31b8-155">Microsoft マネージド デスクトップ用に、マップされたドライブを準備する</span><span class="sxs-lookup"><span data-stu-id="f31b8-155">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. [<span data-ttu-id="f31b8-156">Microsoft マネージド デスクトップ用に、印刷リソースを準備する</span><span class="sxs-lookup"><span data-stu-id="f31b8-156">Prepare printing resources for Microsoft Managed Desktop</span></span>](printing.md)
