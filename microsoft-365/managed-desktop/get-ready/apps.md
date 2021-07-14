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
ms.openlocfilehash: 37f533f34753d66d975cb557239b2b168ac78f8e
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430770"
---
# <a name="apps-in-microsoft-managed-desktop"></a><span data-ttu-id="dc2b8-104">Microsoft マネージド デスクトップのアプリ</span><span class="sxs-lookup"><span data-stu-id="dc2b8-104">Apps in Microsoft Managed Desktop</span></span>

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a><span data-ttu-id="dc2b8-105">一般にアプリ</span><span class="sxs-lookup"><span data-stu-id="dc2b8-105">Apps generally</span></span>

<span data-ttu-id="dc2b8-106">Microsoft には、特定の主要なアプリと、Microsoft 365 E3または E5 ライセンスが含Microsoft マネージド デスクトップ。</span><span class="sxs-lookup"><span data-stu-id="dc2b8-106">Microsoft includes certain key apps along with the Microsoft 365 E3 or E5 license needed to participate in Microsoft Managed Desktop.</span></span> <span data-ttu-id="dc2b8-107">ただし、これらのアプリを提供する場合でも、実行する一定の責任とアクションがあります。</span><span class="sxs-lookup"><span data-stu-id="dc2b8-107">However, even though we provide these apps, you still have certain responsibilities and actions to complete.</span></span>

<span data-ttu-id="dc2b8-108">また、ポータル サイト Microsoft Intune または必要なバックグラウンド インストールを通じて、ポータル サイト の展開パイプラインを使用して、ユーザーに追加の Microsoft 以外のアプリを展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="dc2b8-108">You can also deploy additional non-Microsoft apps to your users for self-service through the Company Portal or a required background installation, all using Microsoft Intune’s deployment pipeline.</span></span> 

## <a name="apps-provided-by-microsoft"></a><span data-ttu-id="dc2b8-109">Microsoft が提供するアプリ</span><span class="sxs-lookup"><span data-stu-id="dc2b8-109">Apps provided by Microsoft</span></span>

<span data-ttu-id="dc2b8-110">Microsoft マネージド デスクトップ ライセンスには、Microsoft 365 Apps for enterprise Standard Suite の 64 ビット バージョンのアプリ (Word、Excel、PowerPoint、PowerPoint、Outlook、Publisher、Access、Teams、OneNote) が含まれています。クイック実行のMicrosoft ProjectおよびVisioは既定では含まれませんが、追加を要求できます。 </span><span class="sxs-lookup"><span data-stu-id="dc2b8-110">Included with your Microsoft Managed Desktop license are 64-bit versions of the apps in the Microsoft 365 Apps for enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Teams, and OneNote.) Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but you can request them to be added.</span></span> <span data-ttu-id="dc2b8-111">これらのアプリの詳細については、「デバイスにインストールMicrosoft Project[または Microsoft Visio」をMicrosoft マネージド デスクトップしてください](../get-started/project-visio.md)。</span><span class="sxs-lookup"><span data-stu-id="dc2b8-111">For more information about these apps, see [Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices](../get-started/project-visio.md).</span></span>

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a><span data-ttu-id="dc2b8-112">Microsoft が提供するアプリをサポートするために行う機能</span><span class="sxs-lookup"><span data-stu-id="dc2b8-112">What Microsoft does to support the apps we provide</span></span>

<span data-ttu-id="dc2b8-113">Microsoft は、付属のアプリの展開、更新、およびサポートのためのフル サービスMicrosoft 365 Apps for enterpriseします。</span><span class="sxs-lookup"><span data-stu-id="dc2b8-113">Microsoft will provide full service for the deployment, update, and support for the included Microsoft 365 Apps for enterprise apps.</span></span> <span data-ttu-id="dc2b8-114">クイック実行 Microsoft Project と Visio のバージョンは既定では含まれていませんが、Microsoft マネージド デスクトップ には展開グループが提供され、IT 管理者はライセンスを管理し、組織に合わせてこれらのアプリケーションを適切に展開できます。</span><span class="sxs-lookup"><span data-stu-id="dc2b8-114">Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but Microsoft Managed Desktop will provide deployment groups allowing your IT administrator to manage licenses and deploy these applications appropriately for your organization.</span></span> <span data-ttu-id="dc2b8-115">Microsoft は、これらのアプリケーションのユーザーをサポートチャネルを通Microsoft マネージド デスクトップサポートします。</span><span class="sxs-lookup"><span data-stu-id="dc2b8-115">Microsoft will support users of these applications through the Microsoft Managed Desktop support channels.</span></span>

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a><span data-ttu-id="dc2b8-116">提供するアプリをサポートするために必要な操作</span><span class="sxs-lookup"><span data-stu-id="dc2b8-116">What you need to do to support the apps we provide</span></span>

<span data-ttu-id="dc2b8-117">これらのアプリで行う必要がある特定の操作がまだ存在します。</span><span class="sxs-lookup"><span data-stu-id="dc2b8-117">There are still certain things you need to do with these apps:</span></span>

- <span data-ttu-id="dc2b8-118">**ライセンスの割り** 当て - ユーザーに適切なライセンスを取得し、ユーザーに割り当てるMicrosoft 365 Apps for enterprise。</span><span class="sxs-lookup"><span data-stu-id="dc2b8-118">**Assign licenses** - You are responsible for obtaining and assigning the appropriate licenses to users for Microsoft 365 Apps for enterprise.</span></span>
- <span data-ttu-id="dc2b8-119">**セキュリティ グループにユーザー** を追加する - Microsoft Project または Visioを使用している場合、IT 管理者はそれらのユーザーを適切な展開グループに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc2b8-119">**Add users to security groups** - If you're using Microsoft Project or Visio, your IT administrator must add those users to the appropriate deployment groups.</span></span> <span data-ttu-id="dc2b8-120">IT 管理者は、会社を離れた場合にそれらのユーザーからライセンスを再利用する責任も負います。</span><span class="sxs-lookup"><span data-stu-id="dc2b8-120">IT administrators are also responsible for reclaiming licenses from those users if they leave the company.</span></span>
- <span data-ttu-id="dc2b8-121">**[Microsoft 365 アドオン** を展開する - Microsoft 365 Apps for enterprise アプリのアドオンが必要な場合は、他の Windows 32 アプリと同様に一Windows展開します。</span><span class="sxs-lookup"><span data-stu-id="dc2b8-121">**Deploy Microsoft 365 Add-ons** - If you need any Add-ons for any of the Microsoft 365 Apps for enterprise apps, deploy them centrally like any other Windows 32 app.</span></span> 

## <a name="apps-you-provide"></a><span data-ttu-id="dc2b8-122">提供するアプリ</span><span class="sxs-lookup"><span data-stu-id="dc2b8-122">Apps you provide</span></span>

<span data-ttu-id="dc2b8-123">ビジネス操作に必要な他のアプリがある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dc2b8-123">You probably have other apps you need for your business operations.</span></span> <span data-ttu-id="dc2b8-124">これらのアプリは、アプリの展開パイプラインMicrosoft マネージド デスクトップ使用して、Microsoft Intuneデバイスにのみ展開できます。</span><span class="sxs-lookup"><span data-stu-id="dc2b8-124">These apps can only be deployed to Microsoft Managed Desktop devices by using Microsoft Intune’s deployment pipeline.</span></span> <span data-ttu-id="dc2b8-125">アプリケーションの展開の詳細については、「アプリをデバイスに展開する」[のMicrosoft マネージド デスクトップします](../get-started/deploy-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="dc2b8-125">For more information about application deployment follow the steps in [Deploy apps to Microsoft Managed Desktop devices](../get-started/deploy-apps.md).</span></span>

### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a><span data-ttu-id="dc2b8-126">アプリに含める独自のアプリを準備Microsoft マネージド デスクトップ</span><span class="sxs-lookup"><span data-stu-id="dc2b8-126">Preparing your own apps for inclusion in Microsoft Managed Desktop</span></span>
<span data-ttu-id="dc2b8-127">アプリを確認し、次のチェックを行います。</span><span class="sxs-lookup"><span data-stu-id="dc2b8-127">Review your apps, checking:</span></span>

- <span data-ttu-id="dc2b8-128">「アプリの要件」で説明されているとおり、どのアプリも禁止または制限[Microsoft マネージド デスクトップはありません](../service-description/mmd-app-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dc2b8-128">None of the apps are prohibited or have restricted behavior, as described in [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).</span></span>
- <span data-ttu-id="dc2b8-129">アプリは、ユーザーが管理できる状態Microsoft Intune。</span><span class="sxs-lookup"><span data-stu-id="dc2b8-129">Apps must be ready for management by Microsoft Intune.</span></span> <span data-ttu-id="dc2b8-130">このトピックの詳細については、「アプリを使用[Windows 10アプリ](/intune/apps-windows-10-app-deploy)の展開Microsoft Intune」および「アプリの追加」[を参照](/intune/apps-add)Microsoft Intune。</span><span class="sxs-lookup"><span data-stu-id="dc2b8-130">For more about this topic, see [Windows 10 app deployment using Microsoft Intune](/intune/apps-windows-10-app-deploy) and [Add apps to Microsoft Intune](/intune/apps-add).</span></span>
- <span data-ttu-id="dc2b8-131">ライセンス キーの提供、ライセンス条項との契約、サーバー接続の事前設定など、その他の事前パッケージ化要件。</span><span class="sxs-lookup"><span data-stu-id="dc2b8-131">Other pre-packaging requirements such as providing license keys, agreement with license terms, and pre-setting server connections.</span></span>

## <a name="steps-to-get-ready"></a><span data-ttu-id="dc2b8-132">準備の手順</span><span class="sxs-lookup"><span data-stu-id="dc2b8-132">Steps to get ready</span></span>

1. <span data-ttu-id="dc2b8-133">詳細については[、「前提条件」をMicrosoft マネージド デスクトップ。](prerequisites.md)</span><span class="sxs-lookup"><span data-stu-id="dc2b8-133">Review [Prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="dc2b8-134">準備 [状況評価ツールを使用します](readiness-assessment-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="dc2b8-134">Use [Readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. [<span data-ttu-id="dc2b8-135">ゲスト アカウントの前提条件</span><span class="sxs-lookup"><span data-stu-id="dc2b8-135">Prerequisites for guest accounts</span></span>](guest-accounts.md)
4. [<span data-ttu-id="dc2b8-136">Microsoft マネージド デスクトップのネットワーク構成</span><span class="sxs-lookup"><span data-stu-id="dc2b8-136">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. [<span data-ttu-id="dc2b8-137">Microsoft マネージド デスクトップ用に証明書とネットワーク プロファイルを準備する</span><span class="sxs-lookup"><span data-stu-id="dc2b8-137">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>](certs-wifi-lan.md)
6. [<span data-ttu-id="dc2b8-138">Microsoft マネージド デスクトップ用にオンプレミス リソース アクセスを準備する</span><span class="sxs-lookup"><span data-stu-id="dc2b8-138">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. <span data-ttu-id="dc2b8-139">[アプリのMicrosoft マネージド デスクトップ](apps.md)(この記事)</span><span class="sxs-lookup"><span data-stu-id="dc2b8-139">[Apps in Microsoft Managed Desktop](apps.md) (This article)</span></span>
8. [<span data-ttu-id="dc2b8-140">Microsoft マネージド デスクトップ用に、マップされたドライブを準備する</span><span class="sxs-lookup"><span data-stu-id="dc2b8-140">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. [<span data-ttu-id="dc2b8-141">Microsoft マネージド デスクトップ用に、印刷リソースを準備する</span><span class="sxs-lookup"><span data-stu-id="dc2b8-141">Prepare printing resources for Microsoft Managed Desktop</span></span>](printing.md)
