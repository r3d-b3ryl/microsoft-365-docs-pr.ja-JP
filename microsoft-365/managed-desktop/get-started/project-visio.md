---
title: microsoft Project または microsoft Visio を microsoft マネージドデスクトップデバイスにインストールする
description: microsoft Project または microsoft Visio を microsoft マネージドデスクトップデバイスにインストールするための情報
keywords: microsoft マネージドデスクトップ、microsoft 365、microsoft Project、microsoft Visio
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5c820e36b7b397fe770216ee229e38a1da5b034d
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288998"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="4f562-104">microsoft Project または microsoft Visio を microsoft マネージドデスクトップデバイスにインストールする</span><span class="sxs-lookup"><span data-stu-id="4f562-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="4f562-105">microsoft Project および microsoft Visio では、microsoft マネージドデスクトップデバイスに特定の手順をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f562-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="4f562-106">このトピックでは、これらのアプリケーションの前提条件とインストールプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4f562-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4f562-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="4f562-107">Prerequisites</span></span>

<span data-ttu-id="4f562-108">管理者は、これらの前提条件を満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f562-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="4f562-109">**ライセンス**数-ユーザーが使用できる microsoft Project と microsoft Visio のライセンスの正確な量が必要です。</span><span class="sxs-lookup"><span data-stu-id="4f562-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="4f562-110">現在、Microsoft マネージドデスクトップでは、これらのアプリケーションの64ビットバージョンのみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4f562-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="4f562-111">**ライセンス名**-これらのアプリケーションの適切なライセンス名は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4f562-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="4f562-112">**Microsoft project** -project online Professional または project online Premium</span><span class="sxs-lookup"><span data-stu-id="4f562-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="4f562-113">**Microsoft visio** -visio Online プラン2</span><span class="sxs-lookup"><span data-stu-id="4f562-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="4f562-114">**ポータルサイト**-ユーザーがこれらのアプリケーションをインストールできるようにするには、テナントで会社のポータルを使用できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f562-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="4f562-115">テナントに会社のポータルが展開されていない場合は、「 [company portal](company-portal.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f562-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="4f562-116">Microsoft マネージドデスクトップデバイス用に Project および Visio を展開する</span><span class="sxs-lookup"><span data-stu-id="4f562-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="4f562-117">サポート要求を送信した後、microsoft Managed Desktop は、microsoft Intune によって3つの Azure AD グループと3つのアプリケーション展開を作成し、アプリをテナントに展開します。</span><span class="sxs-lookup"><span data-stu-id="4f562-117">After you submit your support request, Microsoft Managed Desktop will create three Azure AD groups and three application deployments through Microsoft Intune to deploy the apps to your tenant.</span></span>  

<span data-ttu-id="4f562-118">**Project と Visio を展開するには**</span><span class="sxs-lookup"><span data-stu-id="4f562-118">**To deploy Project and Visio**</span></span>
1. <span data-ttu-id="4f562-119">**サポート要求のファイル**IT 管理者は、このようなアプリケーションをユーザーが使用できるようにするためにサポート要求をファイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f562-119">**File a support request** IT administrators need to file a support request to make these applications available their users.</span></span> <span data-ttu-id="4f562-120">microsoft の管理されたデスクトップにアクセスする方法については、「 [microsoft マネージドデスクトップの管理者サポート](../working-with-managed-desktop/admin-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f562-120">For information on contacting Microsoft Managed Desktop, see [Admin support for Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).</span></span>
2. <span data-ttu-id="4f562-121">**新しい Azure AD グループへのユーザーの割り当て**Microsoft マネージドデスクトップは、テナントに3つの Azure AD グループと、それに対応する3つのアプリケーション展開を作成します。</span><span class="sxs-lookup"><span data-stu-id="4f562-121">**Assign users to new Azure AD groups** Microsoft Managed Desktop will create 3 Azure AD groups in your tenant and 3 corresponding application deployments.</span></span> <span data-ttu-id="4f562-122">IT 管理者は、ユーザーを適切なグループに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f562-122">IT admins need to assign the users to the appropriate groups.</span></span>

>[!NOTE]
><span data-ttu-id="4f562-123">ユーザーは、これらのいずれかの Azure AD グループにのみ割り当ててください。</span><span class="sxs-lookup"><span data-stu-id="4f562-123">Assign users to only one of these Azure AD groups.</span></span> 

<span data-ttu-id="4f562-124">Azure AD グループ名</span><span class="sxs-lookup"><span data-stu-id="4f562-124">Azure AD Group name</span></span> | <span data-ttu-id="4f562-125">割り当てるユーザー</span><span class="sxs-lookup"><span data-stu-id="4f562-125">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="4f562-126">Microsoft-Office-Project-インストール</span><span class="sxs-lookup"><span data-stu-id="4f562-126">Microsoft-Office-Project-Install</span></span> | <span data-ttu-id="4f562-127">プロジェクトのみを必要とするユーザー</span><span class="sxs-lookup"><span data-stu-id="4f562-127">Users needing only Project</span></span>
<span data-ttu-id="4f562-128">Microsoft-Office-Visio-インストール</span><span class="sxs-lookup"><span data-stu-id="4f562-128">Microsoft-Office-Visio-Install</span></span> | <span data-ttu-id="4f562-129">Visio のみを必要とするユーザー</span><span class="sxs-lookup"><span data-stu-id="4f562-129">Users needing only Visio</span></span>
<span data-ttu-id="4f562-130">Microsoft-Office-Project および Visio-インストール</span><span class="sxs-lookup"><span data-stu-id="4f562-130">Microsoft-Office-Project and Visio-Install</span></span> | <span data-ttu-id="4f562-131">Project と Visio の両方を必要とするユーザー</span><span class="sxs-lookup"><span data-stu-id="4f562-131">Users needing both Project and Visio</span></span>

<span data-ttu-id="4f562-132">これらのグループに割り当てられると、アプリケーションは会社のポータルで利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="4f562-132">Once assigned to these groups, applications will be available in the Company Portal.</span></span> <span data-ttu-id="4f562-133">同期には数分かかる場合がありますが、ユーザーは会社のポータルからアプリをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="4f562-133">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

## <a name="communicate-changes"></a><span data-ttu-id="4f562-134">変更の伝達</span><span class="sxs-lookup"><span data-stu-id="4f562-134">Communicate changes</span></span>
<span data-ttu-id="4f562-135">it 管理者は、プロジェクトと Visio をインストールする方法をユーザーに知らせることが重要です。</span><span class="sxs-lookup"><span data-stu-id="4f562-135">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="4f562-136">これには以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4f562-136">This includes:</span></span> 
- <span data-ttu-id="4f562-137">これらのアプリケーションが利用可能な場合にユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="4f562-137">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="4f562-138">これらのアプリケーションをポータルサイトからインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4f562-138">Instructions on how to install these applications from the Company Portal.</span></span>

>[!NOTE]
><span data-ttu-id="4f562-139">ユーザーは、microsoft Project または会社のポータルから microsoft Visio をインストールする前に、すべての Office アプリケーションを閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f562-139">Users must close all Office applications before installing Microsoft Project or Microsoft Visio from Company Portal.</span></span> 
