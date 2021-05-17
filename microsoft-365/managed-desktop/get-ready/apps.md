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
ms.openlocfilehash: 571acc9c240fc0243998050ac3013258a2f85a3e
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2021
ms.locfileid: "52028946"
---
# <a name="apps-in-microsoft-managed-desktop"></a><span data-ttu-id="81ba5-104">Microsoft マネージド デスクトップのアプリ</span><span class="sxs-lookup"><span data-stu-id="81ba5-104">Apps in Microsoft Managed Desktop</span></span>

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a><span data-ttu-id="81ba5-105">一般にアプリ</span><span class="sxs-lookup"><span data-stu-id="81ba5-105">Apps generally</span></span>

<span data-ttu-id="81ba5-106">Microsoft には、Microsoft Managed Desktop への参加に必要な Microsoft 365 E3 または E5 ライセンスと共に、特定の主要アプリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="81ba5-106">Microsoft includes certain key apps along with the Microsoft 365 E3 or E5 license needed to participate in Microsoft Managed Desktop.</span></span> <span data-ttu-id="81ba5-107">ただし、これらのアプリを提供する場合でも、実行する一定の責任とアクションがあります。</span><span class="sxs-lookup"><span data-stu-id="81ba5-107">However, even though we provide these apps, you still have certain responsibilities and actions to complete.</span></span>

<span data-ttu-id="81ba5-108">また、Microsoft Intune の展開パイプラインを使用して、追加の Microsoft 以外のアプリをセルフサービス用にユーザーに展開したり、必要なバックグラウンド インストールを実行したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="81ba5-108">You can also deploy additional non-Microsoft apps to your users for self-service through the Company Portal or a required background installation, all using Microsoft Intune’s deployment pipeline.</span></span> 

## <a name="apps-provided-by-microsoft"></a><span data-ttu-id="81ba5-109">Microsoft が提供するアプリ</span><span class="sxs-lookup"><span data-stu-id="81ba5-109">Apps provided by Microsoft</span></span>

<span data-ttu-id="81ba5-110">Microsoft Managed Desktop ライセンスには、Microsoft 365 Apps for enterprise Standard Suite (Word、Excel、PowerPoint、Outlook、Publisher、Access、Skype for Business、OneNote) の 64 ビット バージョンのアプリが含まれています。クイック実行バージョンの Microsoft Project と Visioは既定では含まれていませんが、追加を要求できます。</span><span class="sxs-lookup"><span data-stu-id="81ba5-110">Included with your Microsoft Managed Desktop license are 64-bit versions of the apps in the Microsoft 365 Apps for enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, and OneNote.) Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but you can request them to be added.</span></span> <span data-ttu-id="81ba5-111">これらのアプリの詳細については、「Microsoft マネージ デスクトップ デバイスに Microsoft Project または Microsoft Visio をインストールする [」を参照してください](../get-started/project-visio.md)。</span><span class="sxs-lookup"><span data-stu-id="81ba5-111">For more information about these apps, see [Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices](../get-started/project-visio.md).</span></span>

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a><span data-ttu-id="81ba5-112">Microsoft が提供するアプリをサポートするために行う機能</span><span class="sxs-lookup"><span data-stu-id="81ba5-112">What Microsoft does to support the apps we provide</span></span>

<span data-ttu-id="81ba5-113">Microsoft は、付属の Microsoft 365 Apps for enterprise Apps の展開、更新、およびサポートのためのフル サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="81ba5-113">Microsoft will provide full service for the deployment, update, and support for the included Microsoft 365 Apps for enterprise apps.</span></span> <span data-ttu-id="81ba5-114">クイック実行バージョンの Microsoft Project と Visioは既定では含まれていませんが、Microsoft Managed Desktop には展開グループが提供され、IT 管理者はライセンスを管理し、組織に合わせてこれらのアプリケーションを適切に展開できます。</span><span class="sxs-lookup"><span data-stu-id="81ba5-114">Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but Microsoft Managed Desktop will provide deployment groups allowing your IT administrator to manage licenses and deploy these applications appropriately for your organization.</span></span> <span data-ttu-id="81ba5-115">Microsoft は、Microsoft Managed Desktop サポート チャネルを通じてこれらのアプリケーションのユーザーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="81ba5-115">Microsoft will support users of these applications through the Microsoft Managed Desktop support channels.</span></span>

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a><span data-ttu-id="81ba5-116">提供するアプリをサポートするために必要な操作</span><span class="sxs-lookup"><span data-stu-id="81ba5-116">What you need to do to support the apps we provide</span></span>

<span data-ttu-id="81ba5-117">これらのアプリで行う必要がある特定の操作がまだ存在します。</span><span class="sxs-lookup"><span data-stu-id="81ba5-117">There are still certain things you need to do with these apps:</span></span>

- <span data-ttu-id="81ba5-118">**ライセンスの割り** 当て - Microsoft 365 Apps for enterprise のユーザーに適切なライセンスを取得して割り当てる責任があります。</span><span class="sxs-lookup"><span data-stu-id="81ba5-118">**Assign licenses** - You are responsible for obtaining and assigning the appropriate licenses to users for Microsoft 365 Apps for enterprise.</span></span>
- <span data-ttu-id="81ba5-119">**セキュリティ グループにユーザーを追加** する - Microsoft Project または Visio を使用している場合、IT 管理者はそれらのユーザーを適切な展開グループに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81ba5-119">**Add users to security groups** - If you're using Microsoft Project or Visio, your IT administrator must add those users to the appropriate deployment groups.</span></span> <span data-ttu-id="81ba5-120">IT 管理者は、会社を離れた場合にそれらのユーザーからライセンスを再利用する責任も負います。</span><span class="sxs-lookup"><span data-stu-id="81ba5-120">IT administrators are also responsible for reclaiming licenses from those users if they leave the company.</span></span>
- <span data-ttu-id="81ba5-121">**Microsoft 365** アドオンを展開する - エンタープライズ アプリ用の Microsoft 365 アプリのアドオンが必要な場合は、他の Windows 32 アプリと同様に一中心に展開します。</span><span class="sxs-lookup"><span data-stu-id="81ba5-121">**Deploy Microsoft 365 Add-ons** - If you need any Add-ons for any of the Microsoft 365 Apps for enterprise apps, deploy them centrally like any other Windows 32 app.</span></span> 

## <a name="apps-you-provide"></a><span data-ttu-id="81ba5-122">提供するアプリ</span><span class="sxs-lookup"><span data-stu-id="81ba5-122">Apps you provide</span></span>

<span data-ttu-id="81ba5-123">ビジネス操作に必要な他のアプリがある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="81ba5-123">You probably have other apps you need for your business operations.</span></span> <span data-ttu-id="81ba5-124">これらのアプリは、Microsoft Intune の展開パイプラインを使用して Microsoft Managed Desktop デバイスにのみ展開できます。</span><span class="sxs-lookup"><span data-stu-id="81ba5-124">These apps can only be deployed to Microsoft Managed Desktop devices by using Microsoft Intune’s deployment pipeline.</span></span> <span data-ttu-id="81ba5-125">アプリケーションの展開の詳細については、「アプリを Microsoft Managed Desktop デバイスに展開 [する」の手順に従います](../get-started/deploy-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="81ba5-125">For more information about application deployment follow the steps in [Deploy apps to Microsoft Managed Desktop devices](../get-started/deploy-apps.md).</span></span>

### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a><span data-ttu-id="81ba5-126">Microsoft Managed Desktop に含める独自のアプリを準備する</span><span class="sxs-lookup"><span data-stu-id="81ba5-126">Preparing your own apps for inclusion in Microsoft Managed Desktop</span></span>
<span data-ttu-id="81ba5-127">アプリを確認し、次のチェックを行います。</span><span class="sxs-lookup"><span data-stu-id="81ba5-127">Review your apps, checking:</span></span>

- <span data-ttu-id="81ba5-128">Microsoft [Managed Desktop](../service-description/mmd-app-requirements.md)アプリの要件で説明されているとおり、禁止または制限された動作を持つアプリはありません。</span><span class="sxs-lookup"><span data-stu-id="81ba5-128">None of the apps are prohibited or have restricted behavior, as described in [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).</span></span>
- <span data-ttu-id="81ba5-129">アプリは、Microsoft Intune による管理の準備ができている必要があります。</span><span class="sxs-lookup"><span data-stu-id="81ba5-129">Apps must be ready for management by Microsoft Intune.</span></span> <span data-ttu-id="81ba5-130">このトピックの詳細については、「Microsoft Intune を使用した [Windows 10 アプリ](/intune/apps-windows-10-app-deploy) の展開」および「Microsoft Intune にアプリを追加する」 [を参照してください](/intune/apps-add)。</span><span class="sxs-lookup"><span data-stu-id="81ba5-130">For more about this topic, see [Windows 10 app deployment using Microsoft Intune](/intune/apps-windows-10-app-deploy) and [Add apps to Microsoft Intune](/intune/apps-add).</span></span>
- <span data-ttu-id="81ba5-131">ライセンス キーの提供、ライセンス条項との契約、サーバー接続の事前設定など、その他の事前パッケージ化要件。</span><span class="sxs-lookup"><span data-stu-id="81ba5-131">Other pre-packaging requirements such as providing license keys, agreement with license terms, and pre-setting server connections.</span></span>

## <a name="steps-to-get-ready"></a><span data-ttu-id="81ba5-132">準備の手順</span><span class="sxs-lookup"><span data-stu-id="81ba5-132">Steps to get ready</span></span>

1. <span data-ttu-id="81ba5-133">「Microsoft [Managed Desktop の前提条件」を参照してください](prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="81ba5-133">Review [Prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="81ba5-134">準備 [状況評価ツールを使用します](readiness-assessment-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="81ba5-134">Use [Readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. [<span data-ttu-id="81ba5-135">ゲスト アカウントの前提条件</span><span class="sxs-lookup"><span data-stu-id="81ba5-135">Prerequisites for guest accounts</span></span>](guest-accounts.md)
4. [<span data-ttu-id="81ba5-136">Microsoft マネージド デスクトップのネットワーク構成</span><span class="sxs-lookup"><span data-stu-id="81ba5-136">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. [<span data-ttu-id="81ba5-137">Microsoft マネージド デスクトップ用に証明書とネットワーク プロファイルを準備する</span><span class="sxs-lookup"><span data-stu-id="81ba5-137">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>](certs-wifi-lan.md)
6. [<span data-ttu-id="81ba5-138">Microsoft マネージド デスクトップ用にオンプレミス リソース アクセスを準備する</span><span class="sxs-lookup"><span data-stu-id="81ba5-138">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. <span data-ttu-id="81ba5-139">[Microsoft Managed Desktop のアプリ](apps.md) (この記事)</span><span class="sxs-lookup"><span data-stu-id="81ba5-139">[Apps in Microsoft Managed Desktop](apps.md) (This article)</span></span>
8. [<span data-ttu-id="81ba5-140">Microsoft マネージド デスクトップ用に、マップされたドライブを準備する</span><span class="sxs-lookup"><span data-stu-id="81ba5-140">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. [<span data-ttu-id="81ba5-141">Microsoft マネージド デスクトップ用に、印刷リソースを準備する</span><span class="sxs-lookup"><span data-stu-id="81ba5-141">Prepare printing resources for Microsoft Managed Desktop</span></span>](printing.md)
