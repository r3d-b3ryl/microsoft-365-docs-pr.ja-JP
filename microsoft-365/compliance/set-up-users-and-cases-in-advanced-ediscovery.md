---
title: 高度な電子情報開示でユーザーとケースをセットアップする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 60ffd80b-4376-419d-b6e4-a72029b9907c
description: '高度な電子情報開示でユーザーの役割を構成し、ケースを作成し、ユーザーをケースに割り当てる方法について説明します。  '
ms.openlocfilehash: 386be1201b30e6b0e7a46c9de47dd6cf2fc4b53c
ms.sourcegitcommit: 5c96d06496d40d2523edbea336f7355c3c77cc80
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2020
ms.locfileid: "44412806"
---
# <a name="set-up-users-and-cases-in-advanced-ediscovery-classic"></a><span data-ttu-id="2dd7b-103">上級電子情報開示でユーザーおよびケースをセットアップする (クラシック)</span><span class="sxs-lookup"><span data-stu-id="2dd7b-103">Set up users and cases in Advanced eDiscovery (classic)</span></span>

<span data-ttu-id="2dd7b-104">このトピックでは、上級電子情報開示 (クラシック) のユーザーとケースをセットアップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2dd7b-104">This topic describes how to set up users and cases for Advanced eDiscovery (classic).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2dd7b-105">新しいバージョンの Advanced eDiscovery に投資し続ける中で、Advanced eDiscovery (*Advanced eDiscovery (クラッシック)* または *Advanced eDiscovery v1.0* とも呼ばれる) のサポート終了を発表しました。</span><span class="sxs-lookup"><span data-stu-id="2dd7b-105">As we continue to invest in newer versions of Advanced eDiscovery, we are announcing the retirement of Advanced eDiscovery, also known as *Advanced eDiscovery (classic)* or *Advanced eDiscovery v1.0*.</span></span> <span data-ttu-id="2dd7b-106">まだ Advanced eDiscovery v1.0 を使用している場合は、できるだけ早く [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (*Microsoft 365 では Advanced eDiscovery ソリューション*とも呼ばれる) に移行してください。</span><span class="sxs-lookup"><span data-stu-id="2dd7b-106">If you're still using Advanced eDiscovery v1.0, please transition to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible.</span></span> <span data-ttu-id="2dd7b-107">Advanced eDiscovery 2.0 には Advanced eDiscovery v1.0 の同様の機能が搭載されていますが、保管担当者管理、通信管理、レビュー セットなど、多くの新機能も搭載されています。</span><span class="sxs-lookup"><span data-stu-id="2dd7b-107">Advanced eDiscovery 2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets.</span></span> <span data-ttu-id="2dd7b-108">Advanced eDiscovery v1.0 のサポート終了の詳細については、「[従来版の電子情報開示ツールのサポート終了](legacy-ediscovery-retirement.md#advanced-ediscovery-v10)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dd7b-108">To learn more about the retirement of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="2dd7b-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="2dd7b-109">Prerequisites</span></span>

<span data-ttu-id="2dd7b-110">Advanced eDiscovery でケースとユーザーを設定する前に、次のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="2dd7b-110">Before setting up cases and users in Advanced eDiscovery, the following is required:</span></span>
  
- <span data-ttu-id="2dd7b-p102">Advanced eDiscovery を使用してユーザーのデータを分析するには、ユーザー (データの保管担当者) に Office365 E5 ライセンスが割り当てられている必要があります。または、Office365 E1 または E3 ライセンスを持つユーザーに Advanced eDiscovery 単体のライセンスを割り当てることもできます。ケースに割り当てられ、Advanced eDiscovery を使用してデータを分析する管理者および法令遵守責任者には E5 ライセンスは不要です。</span><span class="sxs-lookup"><span data-stu-id="2dd7b-p102">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license. Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license. Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span> 
    
- <span data-ttu-id="2dd7b-114">&amp;電子情報開示ケースを作成してメンバーを追加するには、セキュリティコンプライアンスセンターの電子情報開示マネージャーの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="2dd7b-114">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to create an eDiscovery case and add members to it.</span></span> <span data-ttu-id="2dd7b-115">セキュリティ/コンプライアンスセンターの電子情報開示マネージャーの役割グループに自分を追加するには &amp; 、組織の全体管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2dd7b-115">To add yourself to the eDiscovery Manager role group in Security &amp; Compliance Center, you have to be a global administrator in your organization.</span></span> <span data-ttu-id="2dd7b-116">全体管理者ではない場合は、電子情報開示マネージャーの役割グループに追加するように全体管理者に依頼する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2dd7b-116">If you're not a global administrator, you 'll have to ask a global administrator to add you to the eDiscovery Manager role group.</span></span> <span data-ttu-id="2dd7b-117">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dd7b-117">For more information, see:</span></span>
    
  - [<span data-ttu-id="2dd7b-118">Microsoft 365 セキュリティコンプライアンスセンターのアクセス許可 &amp;</span><span class="sxs-lookup"><span data-stu-id="2dd7b-118">Permissions in the Microsoft 365 Security &amp; Compliance Center</span></span>](~/security/office-365-security/protect-against-threats.md)
    
  - [<span data-ttu-id="2dd7b-119">Microsoft 365 セキュリティコンプライアンスセンターで電子情報開示のアクセス許可を割り当てる &amp;</span><span class="sxs-lookup"><span data-stu-id="2dd7b-119">Assign eDiscovery permissions in the Microsoft‍ 365 Security &amp; Compliance Center</span></span>](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a><span data-ttu-id="2dd7b-120">手順 1: ユーザーに電子情報開示のアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="2dd7b-120">Step 1: Assign users eDiscovery permissions</span></span>

<span data-ttu-id="2dd7b-121">最初の手順は、ユーザー &amp; が電子情報開示ケースのメンバーとして追加できるように、セキュリティコンプライアンスセンターで必要なアクセス許可をユーザーに割り当てることです。</span><span class="sxs-lookup"><span data-stu-id="2dd7b-121">The first step is to assign users the requirement permissions in the Security &amp; Compliance Center so that they can me added as a member of an eDiscovery case.</span></span> <span data-ttu-id="2dd7b-122">セキュリティ/コンプライアンスセンターでユーザーをケースのメンバーとして追加すると、 &amp; 上級電子情報開示のケースにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="2dd7b-122">After a user is added as a member of a case in the Security &amp; Compliance Center, they'll be able to access the case in Advanced eDiscovery.</span></span>
  
<span data-ttu-id="2dd7b-123">電子情報開示ケースのメンバーとして追加できるように、必要なアクセス許可をユーザーに割り当てるには、 [Microsoft 365 セキュリティ &amp; コンプライアンスセンターの「電子情報開示のケース](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members)」のステップ1を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dd7b-123">To assign a user the necessary permissions so they can be added as a member of an eDiscovery case, see Step 1 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span></span>
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a><span data-ttu-id="2dd7b-124">手順 2: 電子情報開示ケースを作成し、メンバーを追加する</span><span class="sxs-lookup"><span data-stu-id="2dd7b-124">Step 2: Create an eDiscovery case and add members</span></span>

<span data-ttu-id="2dd7b-125">次の手順では、セキュリティ & コンプライアンスセンターで新しい電子情報開示ケースを作成し、メンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="2dd7b-125">The next step is to create a new eDiscovery case in the Security & Compliance Center and add members.</span></span> <span data-ttu-id="2dd7b-126">そのケースのメンバーは、高度な電子情報開示のケースにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="2dd7b-126">Members of the case will then be able to access the case in Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="2dd7b-127">新しい電子情報開示ケースを作成するには、「 [Core ediscovery の概要](get-started-core-ediscovery.md#step-3-create-a-core-ediscovery-case)」のステップ3を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dd7b-127">To create a new eDiscovery case, see Step 3 in [Get started with Core eDiscovery](get-started-core-ediscovery.md#step-3-create-a-core-ediscovery-case).</span></span>

2. <span data-ttu-id="2dd7b-128">電子情報開示ケースにメンバーを追加するには、「 [Core ediscovery の概要](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-core-ediscovery-case)」のステップ4を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dd7b-128">To add members to an eDiscovery case, see Step 4 in [Get started with Core eDiscovery](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-core-ediscovery-case)</span></span>

## <a name="step-3-go-a-case-in-advanced-ediscovery"></a><span data-ttu-id="2dd7b-129">手順 3: 高度な電子情報開示でケースを進める</span><span class="sxs-lookup"><span data-stu-id="2dd7b-129">Step 3: Go a case in Advanced eDiscovery</span></span>

<span data-ttu-id="2dd7b-130">電子情報開示ケースを作成してメンバーを追加すると、そのユーザー (またはケースのメンバー) は、高度な電子情報開示で対応するケースにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="2dd7b-130">After you create an eDiscovery case and add members, you (or any member of the case) can access the corresponding case in Advanced eDiscovery.</span></span> <span data-ttu-id="2dd7b-131">上級電子情報開示のケースにアクセスするには、「 [Advanced ediscovery でのケース](quick-setup-for-advanced-ediscovery.md#accessing-a-case-in-advanced-ediscovery)へのアクセス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dd7b-131">To access a case in Advanced eDiscovery, see [Accessing a case in Advanced eDiscovery](quick-setup-for-advanced-ediscovery.md#accessing-a-case-in-advanced-ediscovery).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2dd7b-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="2dd7b-132">See also</span></span>

[<span data-ttu-id="2dd7b-133">Advanced eDiscovery (クラシック)</span><span class="sxs-lookup"><span data-stu-id="2dd7b-133">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="2dd7b-134">高度な電子情報開示のためのデータの準備 (クラシック)</span><span class="sxs-lookup"><span data-stu-id="2dd7b-134">Preparing data for Advanced eDiscovery (classic)</span></span>](prepare-data-for-advanced-ediscovery.md)
 