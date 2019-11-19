---
title: デバイスに Intune Company Portal をインストールする
description: Microsoft マネージドデスクトップデバイスへのポータルサイトアプリのインストールに関する情報
keywords: Microsoft マネージドデスクトップ、Microsoft 365、ポータルサイト
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 4e83983ae7b8b936b639382f025f1f88eeca0762
ms.sourcegitcommit: 0ceb79a633f7004e82b80e69b6f7a7329ccec7ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/18/2019
ms.locfileid: "38699677"
---
# <a name="install-intune-company-portal-on-on-devices"></a><span data-ttu-id="045f7-104">デバイスに Intune ポータルサイトをインストールする</span><span class="sxs-lookup"><span data-stu-id="045f7-104">Install Intune Company Portal on on devices</span></span>

<span data-ttu-id="045f7-105">Microsoft マネージドデスクトップでは、IT 管理者が Microsoft マネージドデスクトップデバイスを使用してユーザーに Intune ポータルサイトをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="045f7-105">Microsoft Managed Desktop requires that IT administrators install Intune Company Portal for their users with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="045f7-106">組織にとって次のような利点があります。</span><span class="sxs-lookup"><span data-stu-id="045f7-106">Here are some benefits for your organization:</span></span>
- <span data-ttu-id="045f7-107">ユーザーは、利用可能なアプリケーションを参照してインストールする場所が1つあります。</span><span class="sxs-lookup"><span data-stu-id="045f7-107">Users have one place to browse and install available applications.</span></span> 
- <span data-ttu-id="045f7-108">IT 管理者は、ユーザーのカテゴリ別にアプリケーションを編成できます。</span><span class="sxs-lookup"><span data-stu-id="045f7-108">IT administrators can organize applications by categories for their users.</span></span>  
- <span data-ttu-id="045f7-109">Microsoft Project や Microsoft Visio などの一部のアプリケーションでは、Microsoft マネージドデスクトップを使用して、会社のポータルを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="045f7-109">Some applications (like Microsoft Project and Microsoft Visio) require Company Portal to deploy with Microsoft Managed Desktop.</span></span>
- <span data-ttu-id="045f7-110">IT 管理者は、組織のためにポータルサイトをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="045f7-110">IT administrators can customize Company Portal for their organization.</span></span> <span data-ttu-id="045f7-111">これには、ブランドイメージング、ローカルサポート連絡先での追加などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="045f7-111">This includes brand imaging, adding in local support contacts, and more.</span></span> <span data-ttu-id="045f7-112">詳細については、「 [Microsoft Intune ポータルサイトアプリを構成する方法](https://docs.microsoft.com/intune/company-portal-app)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="045f7-112">For more information, see [How to Configure the Microsoft Intune Company Portal app](https://docs.microsoft.com/intune/company-portal-app).</span></span>   

<span data-ttu-id="045f7-113">このトピックでは、Intune Company Portal を Microsoft Managed Desktop ユーザーに展開するプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="045f7-113">This topic documents the process for deploying the Intune Company Portal to your Microsoft Managed Desktop users.</span></span> <span data-ttu-id="045f7-114">全体的なプロセスは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="045f7-114">The overall process looks like this:</span></span>
1. <span data-ttu-id="045f7-115">ビジネス向け Microsoft Store からの会社ポータルの購入と Intune との同期</span><span class="sxs-lookup"><span data-stu-id="045f7-115">Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
2. <span data-ttu-id="045f7-116">ユーザーへの会社ポータルの割り当て</span><span class="sxs-lookup"><span data-stu-id="045f7-116">Assign Company Portal to your users</span></span>
3. <span data-ttu-id="045f7-117">ユーザーに対する変更を連絡する</span><span class="sxs-lookup"><span data-stu-id="045f7-117">Communicate change to your users</span></span>

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a><span data-ttu-id="045f7-118">手順 1-ビジネス向け Microsoft Store から会社のポータルを購入し、Intune と同期する</span><span class="sxs-lookup"><span data-stu-id="045f7-118">Step 1 - Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
<span data-ttu-id="045f7-119">アプリを購入して Intune と同期する方法の詳細については、「microsoft [Store For Business apps](deploy-apps.md#msfb-apps) In *microsoft Managed Desktop devices*」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="045f7-119">For info on how to purchase the apps and sync with Intune, see [Microsoft Store for Business apps](deploy-apps.md#msfb-apps) in *Deploy apps to Microsoft Managed Desktop devices*.</span></span>

<span data-ttu-id="045f7-120">このトピックでは、次の方法に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="045f7-120">This topic provides info on how to:</span></span> 
- <span data-ttu-id="045f7-121">ビジネス向け Microsoft Store からの会社ポータルの購入</span><span class="sxs-lookup"><span data-stu-id="045f7-121">Purchase Company Portal from Microsoft Store for Business</span></span> 
- <span data-ttu-id="045f7-122">ビジネス向けの Intune と Microsoft Store の同期を強制する</span><span class="sxs-lookup"><span data-stu-id="045f7-122">Force sync between Intune and Microsoft Store for Business</span></span>
- <span data-ttu-id="045f7-123">ビジネス向けの Intune と Microsoft Store 間のアクティブな同期を確認する</span><span class="sxs-lookup"><span data-stu-id="045f7-123">Verify active sync between Intune and Microsoft Store for Business</span></span> 

## <a name="step-2---assign-company-portal-to-your-users"></a><span data-ttu-id="045f7-124">手順 2-ユーザーに会社のポータルを割り当てる</span><span class="sxs-lookup"><span data-stu-id="045f7-124">Step 2 - Assign Company Portal to your users</span></span>
<span data-ttu-id="045f7-125">Microsoft マネージドデスクトップ管理ポータルを使用して、Microsoft マネージドデスクトップ操作に対するサポート要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="045f7-125">Submit a support request to Microsoft Managed Desktop Operations through the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="045f7-126">サポート要求で、ユーザーに割り当てられている会社のポータルを要求します。</span><span class="sxs-lookup"><span data-stu-id="045f7-126">In the support request, request that Company Portal be assigned to your users.</span></span> <span data-ttu-id="045f7-127">Microsoft マネージドデスクトップは、会社のポータルをテナントに展開し、組織内の Microsoft マネージドデスクトップデバイスにアプリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="045f7-127">Microsoft Managed Desktop will deploy Company Portal to your tenant and install the app on Microsoft Managed Desktop devices in your organization.</span></span>

<span data-ttu-id="045f7-128">Microsoft マネージドデスクトップでのサポート要求の送信の詳細については、「 [Microsoft マネージドデスクトップの管理者サポート](../working-with-managed-desktop/admin-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="045f7-128">For more information on submitting support requests with Microsoft Managed Desktop, see [Admin support for Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).</span></span>

## <a name="step-3---communicate-change-to-your-users"></a><span data-ttu-id="045f7-129">手順 3-ユーザーに変更を伝達する</span><span class="sxs-lookup"><span data-stu-id="045f7-129">Step 3 - Communicate change to your users</span></span>
<span data-ttu-id="045f7-130">組織の IT 管理者として、組織内の会社のポータルの使用方法をユーザーに知らせることが重要です。</span><span class="sxs-lookup"><span data-stu-id="045f7-130">As the IT administrator for your organization, it’s important to let your users know how to use Company Portal in your organization.</span></span> <span data-ttu-id="045f7-131">Microsoft マネージドデスクトップの推奨事項:</span><span class="sxs-lookup"><span data-stu-id="045f7-131">Microsoft Managed Desktop recommends:</span></span>
- <span data-ttu-id="045f7-132">会社のポータルからアプリケーションをインストールする手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="045f7-132">Steps on installing applications from the Company Portal.</span></span> <span data-ttu-id="045f7-133">詳細については、「[デバイスにアプリをインストールして共有](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="045f7-133">For more information, see [Install and share apps on your device](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows).</span></span>
- <span data-ttu-id="045f7-134">現在利用できないアプリケーションについて、IT 管理者に要求を送信する方法。</span><span class="sxs-lookup"><span data-stu-id="045f7-134">How to send requests to IT administrators for applications that are not currently available.</span></span> <span data-ttu-id="045f7-135">詳細については、「 [app for 職場または学校を要求する](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="045f7-135">For more information, see [Request an app for work or school](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school).</span></span>  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="045f7-136">Microsoft マネージドデスクトップの使用を開始する手順</span><span class="sxs-lookup"><span data-stu-id="045f7-136">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="045f7-137">管理ポータルで管理者の連絡先を追加および確認する</span><span class="sxs-lookup"><span data-stu-id="045f7-137">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="045f7-138">条件付きアクセスを調整する</span><span class="sxs-lookup"><span data-stu-id="045f7-138">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="045f7-139">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="045f7-139">Assign licenses</span></span>](assign-licenses.md)
4. <span data-ttu-id="045f7-140">Intune ポータルサイトを展開する (このトピック)</span><span class="sxs-lookup"><span data-stu-id="045f7-140">Deploy Intune Company Portal (this topic)</span></span>
5. [<span data-ttu-id="045f7-141">Enterprise State Roaming を有効にする</span><span class="sxs-lookup"><span data-stu-id="045f7-141">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="045f7-142">デバイスをセットアップする</span><span class="sxs-lookup"><span data-stu-id="045f7-142">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="045f7-143">ユーザーがデバイスを使えるようにする</span><span class="sxs-lookup"><span data-stu-id="045f7-143">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="045f7-144">アプリを展開する</span><span class="sxs-lookup"><span data-stu-id="045f7-144">Deploy apps</span></span>](deploy-apps.md)
