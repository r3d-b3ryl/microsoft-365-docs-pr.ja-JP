---
title: Microsoft Project または microsoft Visio を Microsoft マネージドデスクトップデバイスにインストールする
description: Microsoft Project または microsoft Visio を Microsoft マネージドデスクトップデバイスにインストールするための情報
keywords: Microsoft マネージドデスクトップ、Microsoft 365、microsoft Project、Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: c04bcdf846bafaa7838ef5932c8de595f5035992
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950534"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="2f611-104">Microsoft Project または microsoft Visio を Microsoft マネージドデスクトップデバイスにインストールする</span><span class="sxs-lookup"><span data-stu-id="2f611-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="2f611-105">Microsoft Project および Microsoft Visio では、Microsoft マネージドデスクトップデバイスに特定の手順をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f611-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="2f611-106">このトピックでは、これらのアプリケーションの前提条件とインストールプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2f611-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2f611-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="2f611-107">Prerequisites</span></span>

<span data-ttu-id="2f611-108">管理者は、これらの前提条件を満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f611-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="2f611-109">**ライセンス** 数-ユーザーが使用できる microsoft Project と microsoft Visio のライセンスの正確な量が必要です。</span><span class="sxs-lookup"><span data-stu-id="2f611-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="2f611-110">現在、Microsoft マネージドデスクトップでは、これらのアプリケーションの64ビットバージョンのみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2f611-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="2f611-111">**ライセンス名** -これらのアプリケーションの適切なライセンス名は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2f611-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="2f611-112">**Microsoft project** -Project online Professional または Project online Premium</span><span class="sxs-lookup"><span data-stu-id="2f611-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="2f611-113">**Microsoft visio** -Visio Online プラン2</span><span class="sxs-lookup"><span data-stu-id="2f611-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="2f611-114">**ポータルサイト** -ユーザーがこれらのアプリケーションをインストールできるようにするには、テナントで会社のポータルを使用できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f611-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="2f611-115">テナントに会社のポータルが展開されていない場合は、「 [Company portal](company-portal.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f611-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="2f611-116">Microsoft マネージドデスクトップデバイス用に Project および Visio を展開する</span><span class="sxs-lookup"><span data-stu-id="2f611-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="2f611-117">Microsoft マネージドデスクトップでは、microsoft Project と Microsoft Visio を2つの Win32 アプリケーションとして Microsoft Intune に追加します。</span><span class="sxs-lookup"><span data-stu-id="2f611-117">Microsoft Managed Desktop will add Microsoft Project and Microsoft Visio as two Win32 Applications in Microsoft Intune.</span></span> <span data-ttu-id="2f611-118">また、「使用可能」の目的で対応するアプリケーションに割り当てられる、Azure Active Directory で2つのグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="2f611-118">We will also create two groups in Azure Active Directory which will be assigned to the corresponding application with the "Available" intent.</span></span> 

<span data-ttu-id="2f611-119">**Project と Visio を展開するには** ユーザーを適切なグループに追加すると、アプリケーションが会社のポータルで利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2f611-119">**To deploy Project and Visio** Add the user to the appropriate group and the application will become available in the Company Portal.</span></span> <span data-ttu-id="2f611-120">同期には数分かかる場合がありますが、ユーザーは会社のポータルからアプリをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="2f611-120">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

<span data-ttu-id="2f611-121">Azure AD グループ名</span><span class="sxs-lookup"><span data-stu-id="2f611-121">Azure AD Group name</span></span> | <span data-ttu-id="2f611-122">割り当てるユーザー</span><span class="sxs-lookup"><span data-stu-id="2f611-122">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="2f611-123">モダンワークプレース-Office-Project_Install</span><span class="sxs-lookup"><span data-stu-id="2f611-123">Modern Workplace-Office-Project_Install</span></span> | <span data-ttu-id="2f611-124">プロジェクトを必要とするユーザー</span><span class="sxs-lookup"><span data-stu-id="2f611-124">Users needing Project</span></span>
<span data-ttu-id="2f611-125">モダンワークプレース-Office-Visio_Install</span><span class="sxs-lookup"><span data-stu-id="2f611-125">Modern Workplace-Office-Visio_Install</span></span> | <span data-ttu-id="2f611-126">Visio を必要とするユーザー</span><span class="sxs-lookup"><span data-stu-id="2f611-126">Users needing Visio</span></span>

## <a name="communicate-changes"></a><span data-ttu-id="2f611-127">変更の伝達</span><span class="sxs-lookup"><span data-stu-id="2f611-127">Communicate changes</span></span>
<span data-ttu-id="2f611-128">IT 管理者は、プロジェクトと Visio をインストールする方法をユーザーに知らせることが重要です。</span><span class="sxs-lookup"><span data-stu-id="2f611-128">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="2f611-129">次のようなシナリオが考えられます。</span><span class="sxs-lookup"><span data-stu-id="2f611-129">This includes:</span></span> 
- <span data-ttu-id="2f611-130">これらのアプリケーションが利用可能な場合にユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="2f611-130">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="2f611-131">これらのアプリケーションをポータルサイトからインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2f611-131">Instructions on how to install these applications from the Company Portal.</span></span>
