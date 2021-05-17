---
title: Microsoft マネージ デスクトップ デバイスに Microsoft Project または Microsoft Visio をインストールする
description: Microsoft マネージ デスクトップ デバイスへの Microsoft Project または Microsoft Visio のインストールに関する情報
keywords: Microsoft Managed Desktop, Microsoft 365, Microsoft Project, Microsoft Visio
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
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="abc5f-104">Microsoft マネージ デスクトップ デバイスに Microsoft Project または Microsoft Visio をインストールする</span><span class="sxs-lookup"><span data-stu-id="abc5f-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="abc5f-105">Microsoft Project と Microsoft Visio では、Microsoft Managed Desktop デバイスにインストールする特定の手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="abc5f-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="abc5f-106">このトピックでは、これらのアプリケーションの前提条件とインストール プロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="abc5f-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="abc5f-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="abc5f-107">Prerequisites</span></span>

<span data-ttu-id="abc5f-108">管理者は、次の前提条件を満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abc5f-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="abc5f-109">**ライセンスの数量** - ユーザーが使用できる Microsoft Project ライセンスと Microsoft Visio ライセンスの正しい量が必要です。</span><span class="sxs-lookup"><span data-stu-id="abc5f-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="abc5f-110">Microsoft Managed Desktop は現在、これらのアプリケーションの 64 ビット バージョンのみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="abc5f-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="abc5f-111">**ライセンス名** - これらのアプリケーションの適切なライセンス名は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="abc5f-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="abc5f-112">**Microsoft Project** - Project Online Professional または Project Online Premium</span><span class="sxs-lookup"><span data-stu-id="abc5f-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="abc5f-113">**Microsoft Visio** - Visio Online プラン 2</span><span class="sxs-lookup"><span data-stu-id="abc5f-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="abc5f-114">**ポータル サイト** - ユーザーがこれらのアプリケーションをインストールするには、テナントでポータル サイトを使用できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="abc5f-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="abc5f-115">ポータル サイトがテナントに展開されていない場合は、「ポータル サイト」を [参照してください](company-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="abc5f-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="abc5f-116">Microsoft Managed Desktop デバイス用の Project と Visio の展開</span><span class="sxs-lookup"><span data-stu-id="abc5f-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="abc5f-117">Microsoft Managed Desktop は、Microsoft Project と Microsoft Visio を Microsoft Intune で 2 つの Win32 アプリケーションとして追加します。</span><span class="sxs-lookup"><span data-stu-id="abc5f-117">Microsoft Managed Desktop will add Microsoft Project and Microsoft Visio as two Win32 Applications in Microsoft Intune.</span></span> <span data-ttu-id="abc5f-118">また、Azure Active Directory に 2 つのグループを作成し、"Available" インテントを使用して対応するアプリケーションに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="abc5f-118">We will also create two groups in Azure Active Directory which will be assigned to the corresponding application with the "Available" intent.</span></span> 

<span data-ttu-id="abc5f-119">**Project と Visio を展開するには** ユーザーを適切なグループに追加すると、アプリケーションはポータル サイトで使用できます。</span><span class="sxs-lookup"><span data-stu-id="abc5f-119">**To deploy Project and Visio** Add the user to the appropriate group and the application will become available in the Company Portal.</span></span> <span data-ttu-id="abc5f-120">同期に数分かかる場合がありますが、ユーザーはポータル サイトからアプリをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="abc5f-120">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

<span data-ttu-id="abc5f-121">Azure AD グループ名</span><span class="sxs-lookup"><span data-stu-id="abc5f-121">Azure AD Group name</span></span> | <span data-ttu-id="abc5f-122">どのユーザーを割り当てるか。</span><span class="sxs-lookup"><span data-stu-id="abc5f-122">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="abc5f-123">モダン Workplace-Office-Project_Install</span><span class="sxs-lookup"><span data-stu-id="abc5f-123">Modern Workplace-Office-Project_Install</span></span> | <span data-ttu-id="abc5f-124">Project が必要なユーザー</span><span class="sxs-lookup"><span data-stu-id="abc5f-124">Users needing Project</span></span>
<span data-ttu-id="abc5f-125">モダン Workplace-Office-Visio_Install</span><span class="sxs-lookup"><span data-stu-id="abc5f-125">Modern Workplace-Office-Visio_Install</span></span> | <span data-ttu-id="abc5f-126">Visio が必要なユーザー</span><span class="sxs-lookup"><span data-stu-id="abc5f-126">Users needing Visio</span></span>

## <a name="communicate-changes"></a><span data-ttu-id="abc5f-127">変更を伝える</span><span class="sxs-lookup"><span data-stu-id="abc5f-127">Communicate changes</span></span>
<span data-ttu-id="abc5f-128">IT 管理者は、Project と Visio のインストール方法をユーザーに知らせすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="abc5f-128">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="abc5f-129">これには、次の内容が含まれます。</span><span class="sxs-lookup"><span data-stu-id="abc5f-129">This includes:</span></span> 
- <span data-ttu-id="abc5f-130">これらのアプリケーションが使用可能な場合にユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="abc5f-130">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="abc5f-131">ポータル サイトからこれらのアプリケーションをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="abc5f-131">Instructions on how to install these applications from the Company Portal.</span></span>
