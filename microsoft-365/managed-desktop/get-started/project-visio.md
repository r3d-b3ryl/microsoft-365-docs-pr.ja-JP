---
title: デバイスにMicrosoft Projectまたは Microsoft VisioをMicrosoft マネージド デスクトップする
description: デバイスへのMicrosoft Projectまたは Microsoft VisioのMicrosoft マネージド デスクトップ情報
keywords: Microsoft マネージド デスクトップ、Microsoft 365、Microsoft Project、Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9fd46410877012d92e847ba7ff8b60cd5acceb1e
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925541"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="fa53f-104">デバイスにMicrosoft Projectまたは Microsoft VisioをMicrosoft マネージド デスクトップする</span><span class="sxs-lookup"><span data-stu-id="fa53f-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="fa53f-105">Microsoft Project Microsoft Visioデバイスにインストールするには、特定の手順Microsoft マネージド デスクトップ必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa53f-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="fa53f-106">このトピックでは、これらのアプリケーションの前提条件とインストール プロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="fa53f-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fa53f-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="fa53f-107">Prerequisites</span></span>

<span data-ttu-id="fa53f-108">管理者は、次の前提条件を満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa53f-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="fa53f-109">**ライセンスの数量**- ユーザーが使用できるMicrosoft Projectライセンスと Microsoft Visioライセンスの正しい量を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa53f-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="fa53f-110">Microsoft マネージド デスクトップ現在、これらのアプリケーションの 64 ビット バージョンのみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="fa53f-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="fa53f-111">**ライセンス名** - これらのアプリケーションの適切なライセンス名は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fa53f-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="fa53f-112">**Microsoft Project** - Project Online ProfessionalまたはProject Online Premium</span><span class="sxs-lookup"><span data-stu-id="fa53f-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="fa53f-113">**Microsoft Visio** - Visio オンライン プラン 2</span><span class="sxs-lookup"><span data-stu-id="fa53f-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="fa53f-114">**ポータル サイト**- ユーザーポータル サイトこれらのアプリケーションをインストールするには、テナントで使用できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa53f-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="fa53f-115">テナントにポータル サイト展開されていない場合は、「ポータル サイト」[を参照してください](company-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="fa53f-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="fa53f-116">デバイスProjectのVisioとMicrosoft マネージド デスクトップ展開</span><span class="sxs-lookup"><span data-stu-id="fa53f-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="fa53f-117">Microsoft マネージド デスクトップは、Microsoft Project Win32 アプリケーションVisio Win32 アプリケーションとして追加Microsoft Intune。</span><span class="sxs-lookup"><span data-stu-id="fa53f-117">Microsoft Managed Desktop will add Microsoft Project and Microsoft Visio as two Win32 Applications in Microsoft Intune.</span></span> <span data-ttu-id="fa53f-118">また、"Available" インテントAzure Active Directory対応するアプリケーションに割り当てられる 2 つのグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="fa53f-118">We will also create two groups in Azure Active Directory which will be assigned to the corresponding application with the "Available" intent.</span></span> 

<span data-ttu-id="fa53f-119">**サーバーとProjectを展開Visio** ユーザーを適切なグループに追加すると、アプリケーションがアプリケーションで使用ポータル サイト。</span><span class="sxs-lookup"><span data-stu-id="fa53f-119">**To deploy Project and Visio** Add the user to the appropriate group and the application will become available in the Company Portal.</span></span> <span data-ttu-id="fa53f-120">同期に数分かかる場合がありますが、ユーザーはアプリをアプリからインストールポータル サイト。</span><span class="sxs-lookup"><span data-stu-id="fa53f-120">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

<span data-ttu-id="fa53f-121">Azure AD グループ名</span><span class="sxs-lookup"><span data-stu-id="fa53f-121">Azure AD Group name</span></span> | <span data-ttu-id="fa53f-122">どのユーザーを割り当てるか。</span><span class="sxs-lookup"><span data-stu-id="fa53f-122">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="fa53f-123">モダン Workplace-Office-Project_Install</span><span class="sxs-lookup"><span data-stu-id="fa53f-123">Modern Workplace-Office-Project_Install</span></span> | <span data-ttu-id="fa53f-124">必要なユーザー Project</span><span class="sxs-lookup"><span data-stu-id="fa53f-124">Users needing Project</span></span>
<span data-ttu-id="fa53f-125">モダン Workplace-Office-Visio_Install</span><span class="sxs-lookup"><span data-stu-id="fa53f-125">Modern Workplace-Office-Visio_Install</span></span> | <span data-ttu-id="fa53f-126">必要なユーザー Visio</span><span class="sxs-lookup"><span data-stu-id="fa53f-126">Users needing Visio</span></span>

## <a name="communicate-changes"></a><span data-ttu-id="fa53f-127">変更を伝える</span><span class="sxs-lookup"><span data-stu-id="fa53f-127">Communicate changes</span></span>
<span data-ttu-id="fa53f-128">IT 管理者は、ユーザーにインストール方法とインストール方法をユーザーに知Project重要Visio。</span><span class="sxs-lookup"><span data-stu-id="fa53f-128">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="fa53f-129">保持されるデータには以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="fa53f-129">This includes:</span></span> 
- <span data-ttu-id="fa53f-130">これらのアプリケーションが使用可能な場合にユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="fa53f-130">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="fa53f-131">これらのアプリケーションをインストールする方法については、ポータル サイト。</span><span class="sxs-lookup"><span data-stu-id="fa53f-131">Instructions on how to install these applications from the Company Portal.</span></span>
