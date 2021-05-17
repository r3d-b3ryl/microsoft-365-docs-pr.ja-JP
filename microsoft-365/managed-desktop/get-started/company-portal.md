---
title: Intune ポータル サイトをデバイスにインストールする
description: Microsoft Managed Desktop デバイスへのポータル サイト アプリのインストールに関する情報
keywords: Microsoft Managed Desktop, Microsoft 365, Company Portal
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f9f36d6ca14be610ce9374380349264439282a6a
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086687"
---
# <a name="install-intune-company-portal-on-devices"></a><span data-ttu-id="66b26-104">Intune ポータル サイトをデバイスにインストールする</span><span class="sxs-lookup"><span data-stu-id="66b26-104">Install Intune Company Portal on devices</span></span>

<span data-ttu-id="66b26-105">Microsoft Managed Desktop では、IT 管理者が Microsoft 管理デスクトップ デバイスを使用してユーザーの Intune ポータルをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="66b26-105">Microsoft Managed Desktop requires that IT administrators install Intune Company Portal for their users with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="66b26-106">組織の利点を次に示します。</span><span class="sxs-lookup"><span data-stu-id="66b26-106">Here are some benefits for your organization:</span></span>
- <span data-ttu-id="66b26-107">ユーザーは、使用可能なアプリケーションを参照してインストールする場所を 1 つ持っています。</span><span class="sxs-lookup"><span data-stu-id="66b26-107">Users have one place to browse and install available applications.</span></span> 
- <span data-ttu-id="66b26-108">IT 管理者は、ユーザーのカテゴリ別にアプリケーションを整理できます。</span><span class="sxs-lookup"><span data-stu-id="66b26-108">IT administrators can organize applications by categories for their users.</span></span>  
- <span data-ttu-id="66b26-109">一部のアプリケーション (Microsoft Project や Microsoft Visio など) では、Microsoft Managed Desktop を使用してポータル サイトを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66b26-109">Some applications (like Microsoft Project and Microsoft Visio) require Company Portal to deploy with Microsoft Managed Desktop.</span></span>
- <span data-ttu-id="66b26-110">IT 管理者は、組織のポータル サイトをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="66b26-110">IT administrators can customize Company Portal for their organization.</span></span> <span data-ttu-id="66b26-111">これには、ブランドイメージング、ローカル サポート連絡先の追加などです。</span><span class="sxs-lookup"><span data-stu-id="66b26-111">This includes brand imaging, adding in local support contacts, and more.</span></span> <span data-ttu-id="66b26-112">詳細については、「How to Configure the [Microsoft Intune Company Portal app」を参照してください](/intune/company-portal-app)。</span><span class="sxs-lookup"><span data-stu-id="66b26-112">For more information, see [How to Configure the Microsoft Intune Company Portal app](/intune/company-portal-app).</span></span>   

<span data-ttu-id="66b26-113">このトピックでは、Intune ポータル サイトを Microsoft Managed Desktop ユーザーに展開するプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="66b26-113">This topic documents the process for deploying the Intune Company Portal to your Microsoft Managed Desktop users.</span></span> <span data-ttu-id="66b26-114">全体的なプロセスは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="66b26-114">The overall process looks like this:</span></span>
1. <span data-ttu-id="66b26-115">ビジネス向け Microsoft Store からポータル サイトを購入し、Intune と同期する</span><span class="sxs-lookup"><span data-stu-id="66b26-115">Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
2. <span data-ttu-id="66b26-116">ユーザーにポータル サイトを割り当てる</span><span class="sxs-lookup"><span data-stu-id="66b26-116">Assign Company Portal to your users</span></span>
3. <span data-ttu-id="66b26-117">変更をユーザーに伝える</span><span class="sxs-lookup"><span data-stu-id="66b26-117">Communicate change to your users</span></span>

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a><span data-ttu-id="66b26-118">手順 1 - ビジネス向け Microsoft Store からポータル サイトを購入し、Intune と同期する</span><span class="sxs-lookup"><span data-stu-id="66b26-118">Step 1 - Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
<span data-ttu-id="66b26-119">アプリを購入して Intune と同期する方法については、「Deploy apps to Microsoft Managed Desktop デバイス」の [「Microsoft Store for Business](deploy-apps.md#msfb-apps) アプリ」 *を参照してください*。</span><span class="sxs-lookup"><span data-stu-id="66b26-119">For info on how to purchase the apps and sync with Intune, see [Microsoft Store for Business apps](deploy-apps.md#msfb-apps) in *Deploy apps to Microsoft Managed Desktop devices*.</span></span>

<span data-ttu-id="66b26-120">このトピックでは、次の方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="66b26-120">This topic provides info on how to:</span></span> 
- <span data-ttu-id="66b26-121">ビジネス向け Microsoft Store からポータル サイトを購入する</span><span class="sxs-lookup"><span data-stu-id="66b26-121">Purchase Company Portal from Microsoft Store for Business</span></span> 
- <span data-ttu-id="66b26-122">Intune と Microsoft Store for Business の間で強制的に同期する</span><span class="sxs-lookup"><span data-stu-id="66b26-122">Force sync between Intune and Microsoft Store for Business</span></span>
- <span data-ttu-id="66b26-123">Intune と Microsoft Store for Business の間のアクティブな同期を確認する</span><span class="sxs-lookup"><span data-stu-id="66b26-123">Verify active sync between Intune and Microsoft Store for Business</span></span> 

## <a name="step-2---assign-company-portal-to-your-users"></a><span data-ttu-id="66b26-124">手順 2 - ユーザーにポータル サイトを割り当てる</span><span class="sxs-lookup"><span data-stu-id="66b26-124">Step 2 - Assign Company Portal to your users</span></span>
<span data-ttu-id="66b26-125">Microsoft Managed Desktop への登録後、テナントにポータル サイトを自動的に展開し、組織の Microsoft 管理デスクトップ デバイスにアプリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="66b26-125">Following your enrollment in Microsoft Managed Desktop, we will automatically deploy Company Portal to your tenant and install the app on Microsoft Managed Desktop devices in your organization.</span></span>

## <a name="step-3---communicate-change-to-your-users"></a><span data-ttu-id="66b26-126">手順 3 - ユーザーに変更を伝える</span><span class="sxs-lookup"><span data-stu-id="66b26-126">Step 3 - Communicate change to your users</span></span>
<span data-ttu-id="66b26-127">組織の IT 管理者として、組織でポータル サイトを使用する方法をユーザーに知らせすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="66b26-127">As the IT administrator for your organization, it’s important to let your users know how to use Company Portal in your organization.</span></span> <span data-ttu-id="66b26-128">Microsoft Managed Desktop では、次の方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="66b26-128">Microsoft Managed Desktop recommends:</span></span>
- <span data-ttu-id="66b26-129">ポータル サイトからアプリケーションをインストールする手順。</span><span class="sxs-lookup"><span data-stu-id="66b26-129">Steps on installing applications from the Company Portal.</span></span> <span data-ttu-id="66b26-130">詳細については、「デバイスにアプリ [をインストールして共有する」を参照してください](/intune-user-help/install-apps-cpapp-windows)。</span><span class="sxs-lookup"><span data-stu-id="66b26-130">For more information, see [Install and share apps on your device](/intune-user-help/install-apps-cpapp-windows).</span></span>
- <span data-ttu-id="66b26-131">現在利用できないアプリケーションの要求を IT 管理者に送信する方法。</span><span class="sxs-lookup"><span data-stu-id="66b26-131">How to send requests to IT administrators for applications that are not currently available.</span></span> <span data-ttu-id="66b26-132">詳細については、「アプリを [仕事または学校に依頼する」を参照してください](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)。</span><span class="sxs-lookup"><span data-stu-id="66b26-132">For more information, see [Request an app for work or school](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school).</span></span>  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="66b26-133">Microsoft Managed Desktop の使用を開始する手順</span><span class="sxs-lookup"><span data-stu-id="66b26-133">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="66b26-134">管理ポータルで管理者の連絡先を追加および確認する</span><span class="sxs-lookup"><span data-stu-id="66b26-134">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="66b26-135">条件付きアクセスを調整する</span><span class="sxs-lookup"><span data-stu-id="66b26-135">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="66b26-136">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="66b26-136">Assign licenses</span></span>](assign-licenses.md)
4. <span data-ttu-id="66b26-137">Intune ポータル サイトの展開 (このトピック)</span><span class="sxs-lookup"><span data-stu-id="66b26-137">Deploy Intune Company Portal (this topic)</span></span>
5. [<span data-ttu-id="66b26-138">Enterprise State Roaming を有効にする</span><span class="sxs-lookup"><span data-stu-id="66b26-138">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="66b26-139">デバイスをセットアップする</span><span class="sxs-lookup"><span data-stu-id="66b26-139">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="66b26-140">ユーザーがデバイスを使えるようにする</span><span class="sxs-lookup"><span data-stu-id="66b26-140">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="66b26-141">アプリを展開する</span><span class="sxs-lookup"><span data-stu-id="66b26-141">Deploy apps</span></span>](deploy-apps.md)
