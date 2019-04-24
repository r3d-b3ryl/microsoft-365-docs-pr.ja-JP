---
title: Intune ポータルサイトの Microsoft 管理デスクトップデバイスをインストールする
description: Microsoft マネージドデスクトップデバイスへのポータルサイトアプリのインストールに関する情報
keywords: microsoft マネージドデスクトップ、microsoft 365、ポータルサイト
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 03/08/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: d533de7b68d9fa55ff0a108373d9621068c8fb1e
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289112"
---
# <a name="install-intune-company-portal-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="09aa8-104">Microsoft マネージドデスクトップデバイスに Intune Company Portal をインストールする</span><span class="sxs-lookup"><span data-stu-id="09aa8-104">Install Intune Company Portal on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="09aa8-105">microsoft マネージドデスクトップでは、IT 管理者が microsoft マネージドデスクトップデバイスを使用してユーザーに Intune ポータルサイトをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="09aa8-105">Microsoft Managed Desktop requires that IT administrators install Intune Company Portal for their users with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="09aa8-106">組織にとって次のような利点があります。</span><span class="sxs-lookup"><span data-stu-id="09aa8-106">Here are some benefits for your organization:</span></span>
- <span data-ttu-id="09aa8-107">ユーザーは、利用可能なアプリケーションを参照してインストールする場所が1つあります。</span><span class="sxs-lookup"><span data-stu-id="09aa8-107">Users have one place to browse and install available applications.</span></span> 
- <span data-ttu-id="09aa8-108">IT 管理者は、ユーザーのカテゴリ別にアプリケーションを編成できます。</span><span class="sxs-lookup"><span data-stu-id="09aa8-108">IT administrators can organize applications by categories for their users.</span></span>  
- <span data-ttu-id="09aa8-109">microsoft Project や microsoft Visio などの一部のアプリケーションでは、microsoft マネージドデスクトップを使用して、会社のポータルを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09aa8-109">Some applications (like Microsoft Project and Microsoft Visio) require Company Portal to deploy with Microsoft Managed Desktop.</span></span>
- <span data-ttu-id="09aa8-110">IT 管理者は、組織のためにポータルサイトをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="09aa8-110">IT administrators can customize Company Portal for their organization.</span></span> <span data-ttu-id="09aa8-111">これには、ブランドイメージング、ローカルサポート連絡先での追加などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="09aa8-111">This includes brand imaging, adding in local support contacts, and more.</span></span> <span data-ttu-id="09aa8-112">詳細については、「 [Microsoft Intune ポータルサイトアプリを構成する方法](https://docs.microsoft.com/intune/company-portal-app)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09aa8-112">For more information, see [How to Configure the Microsoft Intune Company Portal app](https://docs.microsoft.com/intune/company-portal-app).</span></span>   

<span data-ttu-id="09aa8-113">このトピックでは、Intune Company Portal を Microsoft Managed Desktop ユーザーに展開するプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="09aa8-113">This topic documents the process for deploying the Intune Company Portal to your Microsoft Managed Desktop users.</span></span> <span data-ttu-id="09aa8-114">全体的なプロセスは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="09aa8-114">The overall process looks like this:</span></span>
1. <span data-ttu-id="09aa8-115">ビジネス向け Microsoft Store からの会社ポータルの購入と Intune との同期</span><span class="sxs-lookup"><span data-stu-id="09aa8-115">Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
2. <span data-ttu-id="09aa8-116">ユーザーへの会社ポータルの割り当て</span><span class="sxs-lookup"><span data-stu-id="09aa8-116">Assign Company Portal to your users</span></span>
3. <span data-ttu-id="09aa8-117">ユーザーに対する変更を連絡する</span><span class="sxs-lookup"><span data-stu-id="09aa8-117">Communicate change to your users</span></span>

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a><span data-ttu-id="09aa8-118">手順 1-ビジネス向け Microsoft Store から会社のポータルを購入し、Intune と同期する</span><span class="sxs-lookup"><span data-stu-id="09aa8-118">Step 1 - Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
<span data-ttu-id="09aa8-119">アプリを購入して Intune と同期する方法の詳細については、「microsoft [Store for Business apps](deploy-apps.md#msfb-apps) in *microsoft Managed Desktop devices*」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09aa8-119">For info on how to purchase the apps and sync with Intune, see [Microsoft Store for Business apps](deploy-apps.md#msfb-apps) in *Deploy apps to Microsoft Managed Desktop devices*.</span></span>

<span data-ttu-id="09aa8-120">このトピックでは、次の方法に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="09aa8-120">This topic provides info on how to:</span></span> 
- <span data-ttu-id="09aa8-121">ビジネス向け Microsoft Store からの会社ポータルの購入</span><span class="sxs-lookup"><span data-stu-id="09aa8-121">Purchase Company Portal from Microsoft Store for Business</span></span> 
- <span data-ttu-id="09aa8-122">ビジネス向けの Intune と Microsoft Store の同期を強制する</span><span class="sxs-lookup"><span data-stu-id="09aa8-122">Force sync between Intune and Microsoft Store for Business</span></span>
- <span data-ttu-id="09aa8-123">ビジネス向けの Intune と Microsoft Store 間のアクティブな同期を確認する</span><span class="sxs-lookup"><span data-stu-id="09aa8-123">Verify active sync between Intune and Microsoft Store for Business</span></span> 

## <a name="step-2---assign-company-portal-to-your-users"></a><span data-ttu-id="09aa8-124">手順 2-ユーザーに会社のポータルを割り当てる</span><span class="sxs-lookup"><span data-stu-id="09aa8-124">Step 2 - Assign Company Portal to your users</span></span>
<span data-ttu-id="09aa8-125">microsoft マネージドデスクトップ管理ポータルを使用して、microsoft マネージドデスクトップ操作に対するサポート要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="09aa8-125">Submit a support request to Microsoft Managed Desktop Operations through the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="09aa8-126">サポート要求で、ユーザーに割り当てられている会社のポータルを要求します。</span><span class="sxs-lookup"><span data-stu-id="09aa8-126">In the support request, request that Company Portal be assigned to your users.</span></span> <span data-ttu-id="09aa8-127">microsoft マネージドデスクトップは、会社のポータルをテナントに展開し、組織内の Microsoft マネージドデスクトップデバイスにアプリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="09aa8-127">Microsoft Managed Desktop will deploy Company Portal to your tenant and install the app on Microsoft Managed Desktop devices in your organization.</span></span>

<span data-ttu-id="09aa8-128">microsoft マネージドデスクトップでのサポート要求の送信の詳細については、「 [microsoft マネージドデスクトップの管理者サポート](../working-with-managed-desktop/admin-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09aa8-128">For more information on submitting support requests with Microsoft Managed Desktop, see [Admin support for Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).</span></span>

## <a name="step-3---communicate-change-to-your-users"></a><span data-ttu-id="09aa8-129">手順 3-ユーザーに変更を伝達する</span><span class="sxs-lookup"><span data-stu-id="09aa8-129">Step 3 - Communicate change to your users</span></span>
<span data-ttu-id="09aa8-130">組織の IT 管理者として、組織内の会社のポータルの使用方法をユーザーに知らせることが重要です。</span><span class="sxs-lookup"><span data-stu-id="09aa8-130">As the IT administrator for your organization, it’s important to let your users know how to use Company Portal in your organization.</span></span> <span data-ttu-id="09aa8-131">Microsoft マネージドデスクトップの推奨事項:</span><span class="sxs-lookup"><span data-stu-id="09aa8-131">Microsoft Managed Desktop recommends:</span></span>
- <span data-ttu-id="09aa8-132">会社のポータルからアプリケーションをインストールする手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="09aa8-132">Steps on installing applications from the Company Portal.</span></span> <span data-ttu-id="09aa8-133">詳細については、「[デバイスにアプリをインストールして共有](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09aa8-133">For more information, see [Install and share apps on your device](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows).</span></span>
- <span data-ttu-id="09aa8-134">現在利用できないアプリケーションについて、IT 管理者に要求を送信する方法。</span><span class="sxs-lookup"><span data-stu-id="09aa8-134">How to send requests to IT administrators for applications that are not currently available.</span></span>