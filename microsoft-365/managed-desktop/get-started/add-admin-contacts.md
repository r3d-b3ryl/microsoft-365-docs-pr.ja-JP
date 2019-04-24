---
title: Microsoft Managed Desktop 管理ポータルで管理者の連絡先を追加する
description: フォーカスされている領域ごとに、連絡先の情報をお伝えください。
keywords: microsoft マネージドデスクトップ、microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 014404ab38ff5871289be186dec150115c3be6ec
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277546"
---
# <a name="add-admin-contacts-in-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="2ffee-104">Microsoft Managed Desktop 管理ポータルで管理者の連絡先を追加する</span><span class="sxs-lookup"><span data-stu-id="2ffee-104">Add Admin contacts in Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="2ffee-105">Microsoft Managed Desktop service がお客様と通信するには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="2ffee-105">There are several ways that Microsoft Managed Desktop service communicates with customers.</span></span> <span data-ttu-id="2ffee-106">コミュニケーションを効率化して、最適な連絡先を確認するには、一連の管理者の連絡先を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ffee-106">To streamline communication and ensure we’re checking with the best contacts, you need to provide a set of admin contacts.</span></span> <span data-ttu-id="2ffee-107">Microsoft マネージドデスクトップ IT 操作は、テナントの問題のトラブルシューティングについて、これらのユーザーに連絡します。</span><span class="sxs-lookup"><span data-stu-id="2ffee-107">Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span> 

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="2ffee-108">Microsoft Managed Desktop 管理ポータルの Azure Active Directory アクセス</span><span class="sxs-lookup"><span data-stu-id="2ffee-108">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="2ffee-109">Microsoft Managed Desktop 管理ポータルでは、ポータルにアクセスするユーザーが次のいずれかの Azure Active Directory (AD) の役割を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ffee-109">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>
- <span data-ttu-id="2ffee-110">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="2ffee-110">Global Administrator</span></span>
- <span data-ttu-id="2ffee-111">Intune サービス管理者</span><span class="sxs-lookup"><span data-stu-id="2ffee-111">Intune Service Administrator</span></span>
- <span data-ttu-id="2ffee-112">課金管理者</span><span class="sxs-lookup"><span data-stu-id="2ffee-112">Billing Administrator</span></span>
- <span data-ttu-id="2ffee-113">サービスサポート管理者</span><span class="sxs-lookup"><span data-stu-id="2ffee-113">Service Support Administrator</span></span>

<span data-ttu-id="2ffee-114">グローバル管理者は、Microsoft マネージドデスクトップにお客様を登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ffee-114">The Global Administrator must be the one to enroll the customer in Microsoft Managed Desktop.</span></span>  <span data-ttu-id="2ffee-115">すべての5つの役割は、タスクを開始して表示するために、管理ポータル内で同じアクセス権を持ちます。</span><span class="sxs-lookup"><span data-stu-id="2ffee-115">All five roles have the same access within the Admin portal to initiate and view tasks.</span></span>  <span data-ttu-id="2ffee-116">これらの役割を azure AD に割り当てる方法の詳細については、「 [azure Active Directory での管理者ロールのアクセス許可](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ffee-116">For more information on assigning these roles in Azure AD, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> 

## <a name="admin-contact-focus-areas"></a><span data-ttu-id="2ffee-117">管理者の連絡先のフォーカス領域</span><span class="sxs-lookup"><span data-stu-id="2ffee-117">Admin contact focus areas</span></span>

<span data-ttu-id="2ffee-118">管理者の連絡先は、質問に回答したり、さまざまなフォーカスエリアの意思決定を行ったりできるベストのユーザーまたはグループである必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ffee-118">Admin contacts should be the best person or group that can answer questions and make decisions for different focus areas.</span></span>  <span data-ttu-id="2ffee-119">Microsoft マネージドデスクトップの操作は、お客様が提出したサポート要求に関する質問について、これらの管理者の連絡先に連絡します。</span><span class="sxs-lookup"><span data-stu-id="2ffee-119">Microsoft Managed Desktop Operations will contact these Admin contacts for questions involving support requests filed by the customer.</span></span>  <span data-ttu-id="2ffee-120">これらの管理者の連絡先は、サポート要求の更新と新しいメッセージに関する通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="2ffee-120">These Admin contacts will receive notifications for support request updates and new messages.</span></span>  <span data-ttu-id="2ffee-121">次のような領域があります。</span><span class="sxs-lookup"><span data-stu-id="2ffee-121">These areas include:</span></span>

<span data-ttu-id="2ffee-122">フォーカスエリア</span><span class="sxs-lookup"><span data-stu-id="2ffee-122">Focus area</span></span> | <span data-ttu-id="2ffee-123">に関する質問</span><span class="sxs-lookup"><span data-stu-id="2ffee-123">For questions about</span></span>
--- | ---
<span data-ttu-id="2ffee-124">アプリ</span><span class="sxs-lookup"><span data-stu-id="2ffee-124">Apps</span></span> | <span data-ttu-id="2ffee-125">アプリのパッケージ化のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="2ffee-125">Troubleshooting App Packaging</span></span>
<span data-ttu-id="2ffee-126">デバイス</span><span class="sxs-lookup"><span data-stu-id="2ffee-126">Devices</span></span> | <span data-ttu-id="2ffee-127">デバイスの正常性、Microsoft マネージドデスクトップデバイスのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="2ffee-127">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="2ffee-128">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="2ffee-128">Security</span></span> | <span data-ttu-id="2ffee-129">Microsoft マネージドデスクトップデバイスに関するセキュリティ上の問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="2ffee-129">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="2ffee-130">その他</span><span class="sxs-lookup"><span data-stu-id="2ffee-130">Other</span></span> | <span data-ttu-id="2ffee-131">他の領域でカバーされない問題の場合</span><span class="sxs-lookup"><span data-stu-id="2ffee-131">For issues not covered by other areas</span></span>

<span data-ttu-id="2ffee-132">これらの連絡先に対して選択するユーザーは、Microsoft マネージドデスクトップ環境を決定するための知識と権限を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ffee-132">Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment.</span></span> <span data-ttu-id="2ffee-133">Microsoft マネージドデスクトップ環境をオンにすると、ローカルのヘルプデスクおよびセキュリティのための連絡先を追加するように求められます。</span><span class="sxs-lookup"><span data-stu-id="2ffee-133">When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="2ffee-134">[サポートリクエストを送信](../working-with-managed-desktop/support.md)する場合は、管理者の連絡先が必要です。</span><span class="sxs-lookup"><span data-stu-id="2ffee-134">Admin contacts are required when you [submit a Support request](../working-with-managed-desktop/support.md).</span></span> <span data-ttu-id="2ffee-135">サポート要求のフォーカス領域に対する管理者の連絡先が必要です。</span><span class="sxs-lookup"><span data-stu-id="2ffee-135">You’ll need to have an admin contact for the focus area of the Support request.</span></span> 

<span data-ttu-id="2ffee-136">**管理者の連絡先を追加するには**</span><span class="sxs-lookup"><span data-stu-id="2ffee-136">**To add admin contacts**</span></span>

1.  <span data-ttu-id="2ffee-137">[Microsoft Managed Desktop 管理ポータル](http://aka.ms/mwaasportal)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="2ffee-137">Sign in to [Microsoft Managed Desktop admin portal](http://aka.ms/mwaasportal).</span></span> 

2.  <span data-ttu-id="2ffee-138">[**サポート**] で、[管理者の**連絡先**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2ffee-138">Under **Support**, select **Admin contacts**.</span></span> 

    ![サポートメニュー、管理者の連絡先](images/admincontacts.png)

3. <span data-ttu-id="2ffee-140">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2ffee-140">Select **Add**.</span></span>

    ![管理ポータルの [追加] ボタン](images/adminadd.png)

4.  <span data-ttu-id="2ffee-142">**フォーカスの領域**を選択し、連絡先の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="2ffee-142">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![フォーカス領域のリスト](images/areaoffocus.png)

5. <span data-ttu-id="2ffee-144">フォーカスの領域ごとに繰り返します。</span><span class="sxs-lookup"><span data-stu-id="2ffee-144">Repeat for each area of focus.</span></span> 

