---
title: 管理ポータルで管理者の連絡先を追加および確認する
description: フォーカスされている領域ごとに、連絡先の情報をお伝えください。
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: d34d7082150b4131634fb695ce6664ded50e6f9d
ms.sourcegitcommit: 6ae69c40bafa6aef633789c3df0fa20590bdcf40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/20/2019
ms.locfileid: "40823839"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a><span data-ttu-id="667ee-104">管理ポータルで管理者の連絡先を追加および確認する</span><span class="sxs-lookup"><span data-stu-id="667ee-104">Add and verify admin contacts in the Admin portal</span></span>

<span data-ttu-id="667ee-105">Microsoft Managed Desktop service がお客様と通信するには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="667ee-105">There are several ways that Microsoft Managed Desktop service communicates with customers.</span></span> <span data-ttu-id="667ee-106">コミュニケーションを効率化し、適切な人物との関係を確認するには、一連の管理者の連絡先を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="667ee-106">To streamline communication and ensure we’re checking with the right people, you need to provide a set of admin contacts.</span></span> <span data-ttu-id="667ee-107">Microsoft マネージドデスクトップ IT 操作は、テナントの問題のトラブルシューティングについて、これらのユーザーに連絡します。</span><span class="sxs-lookup"><span data-stu-id="667ee-107">Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="667ee-108">これらの連絡先は、管理ポータルに既に追加されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="667ee-108">You might have already added these contacts in the Admin portal.</span></span> <span data-ttu-id="667ee-109">その場合は、Microsoft 管理デスクトップが深刻なインシデントが発生した場合に、連絡先リストが正確**であること**を、すぐに確認してください。</span><span class="sxs-lookup"><span data-stu-id="667ee-109">If so, take a moment now to double-check that the contact list is accurate, since Microsoft Managed Desktop **must** be able to reach them if a severe incident occurs.</span></span>

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="667ee-110">Microsoft Managed Desktop 管理ポータルの Azure Active Directory アクセス</span><span class="sxs-lookup"><span data-stu-id="667ee-110">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="667ee-111">Microsoft Managed Desktop 管理ポータルでは、ポータルにアクセスするユーザーが次のいずれかの Azure Active Directory (AD) の役割を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="667ee-111">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>
- <span data-ttu-id="667ee-112">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="667ee-112">Global Administrator</span></span>
- <span data-ttu-id="667ee-113">Intune サービス管理者</span><span class="sxs-lookup"><span data-stu-id="667ee-113">Intune Service Administrator</span></span>
- <span data-ttu-id="667ee-114">課金管理者</span><span class="sxs-lookup"><span data-stu-id="667ee-114">Billing Administrator</span></span>
- <span data-ttu-id="667ee-115">サービスサポート管理者</span><span class="sxs-lookup"><span data-stu-id="667ee-115">Service Support Administrator</span></span>

<span data-ttu-id="667ee-116">グローバル管理者は、組織を Microsoft マネージドデスクトップに登録するためのものである必要があります。</span><span class="sxs-lookup"><span data-stu-id="667ee-116">The Global Administrator must be the one to enroll your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="667ee-117">すべての5つの役割は、タスクを開始して表示するために、管理ポータル内で同じアクセス権を持ちます。</span><span class="sxs-lookup"><span data-stu-id="667ee-117">All five roles have the same access within the Admin portal to initiate and view tasks.</span></span> <span data-ttu-id="667ee-118">これらの役割を Azure AD に割り当てる方法の詳細については、「 [Azure Active Directory での管理者ロールのアクセス許可](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="667ee-118">For more information on assigning these roles in Azure AD, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> 

## <a name="admin-contact-areas-of-focus"></a><span data-ttu-id="667ee-119">フォーカスのある管理者の連絡先領域</span><span class="sxs-lookup"><span data-stu-id="667ee-119">Admin contact areas of focus</span></span>

<span data-ttu-id="667ee-120">管理者の連絡先は、質問に回答したり、フォーカスの異なる領域を決定するための最適なユーザーまたはグループである必要があります。</span><span class="sxs-lookup"><span data-stu-id="667ee-120">Admin contacts should be the best person or group that can answer questions and make decisions for different areas of focus.</span></span> <span data-ttu-id="667ee-121">**Microsoft マネージドデスクトップの操作は、お客様が提出したサポート要求に関する質問について、これらの管理者の連絡先に連絡します。**</span><span class="sxs-lookup"><span data-stu-id="667ee-121">**Microsoft Managed Desktop Operations will contact these Admin contacts for questions involving support requests filed by the customer.**</span></span> <span data-ttu-id="667ee-122">これらの管理者の連絡先は、サポート要求の更新と新しいメッセージに関する通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="667ee-122">These Admin contacts will receive notifications for support request updates and new messages.</span></span> <span data-ttu-id="667ee-123">次のような領域があります。</span><span class="sxs-lookup"><span data-stu-id="667ee-123">These areas include:</span></span>

<span data-ttu-id="667ee-124">フォーカスの領域</span><span class="sxs-lookup"><span data-stu-id="667ee-124">Area of focus</span></span> | <span data-ttu-id="667ee-125">に関する質問</span><span class="sxs-lookup"><span data-stu-id="667ee-125">For questions about</span></span>
--- | ---
<span data-ttu-id="667ee-126">アプリのパッケージ化</span><span class="sxs-lookup"><span data-stu-id="667ee-126">App packaging</span></span> | <span data-ttu-id="667ee-127">アプリのパッケージ化のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="667ee-127">Troubleshooting app packaging</span></span>
<span data-ttu-id="667ee-128">デバイス</span><span class="sxs-lookup"><span data-stu-id="667ee-128">Devices</span></span> | <span data-ttu-id="667ee-129">デバイスの正常性、Microsoft マネージドデスクトップデバイスのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="667ee-129">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="667ee-130">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="667ee-130">Security</span></span> | <span data-ttu-id="667ee-131">Microsoft マネージドデスクトップデバイスに関するセキュリティ上の問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="667ee-131">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="667ee-132">IT ヘルプデスク</span><span class="sxs-lookup"><span data-stu-id="667ee-132">IT help desk</span></span> | <span data-ttu-id="667ee-133">サポートスタッフが Microsoft マネージドデスクトップサポート領域外のエンドユーザーのチケットを渡している場合は、</span><span class="sxs-lookup"><span data-stu-id="667ee-133">in cases where our Support staff hands over end-user tickets outside of Microsoft Managed Desktop support areas</span></span> 
<span data-ttu-id="667ee-134">その他</span><span class="sxs-lookup"><span data-stu-id="667ee-134">Other</span></span> | <span data-ttu-id="667ee-135">他の領域でカバーされない問題の場合</span><span class="sxs-lookup"><span data-stu-id="667ee-135">For issues not covered by other areas</span></span>

<span data-ttu-id="667ee-136">**これらの連絡先に対して選択するユーザーは、Microsoft マネージドデスクトップ環境を決定するための知識と権限を持っている必要があります。**</span><span class="sxs-lookup"><span data-stu-id="667ee-136">**Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment.**</span></span> <span data-ttu-id="667ee-137">Microsoft マネージドデスクトップ環境をオンにすると、ローカルのヘルプデスクおよびセキュリティのための連絡先を追加するように求められます。</span><span class="sxs-lookup"><span data-stu-id="667ee-137">When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="667ee-138">[サポートリクエストを送信](../service-description/support.md)する場合は、管理者の連絡先が必要です。</span><span class="sxs-lookup"><span data-stu-id="667ee-138">Admin contacts are required when you [submit a Support request](../service-description/support.md).</span></span> <span data-ttu-id="667ee-139">サポート要求のフォーカス領域に対する管理者の連絡先が必要です。</span><span class="sxs-lookup"><span data-stu-id="667ee-139">You’ll need to have an admin contact for the focus area of the Support request.</span></span> 

<span data-ttu-id="667ee-140">**管理者の連絡先を追加するには**</span><span class="sxs-lookup"><span data-stu-id="667ee-140">**To add admin contacts**</span></span>

1.  <span data-ttu-id="667ee-141">[Microsoft Managed Desktop 管理ポータル](https://aka.ms/mwaasportal)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="667ee-141">Sign in to [Microsoft Managed Desktop admin portal](https://aka.ms/mwaasportal).</span></span> 

2.  <span data-ttu-id="667ee-142">[**サポート**] で、[管理者の**連絡先**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="667ee-142">Under **Support**, select **Admin contacts**.</span></span> 

    ![選択されている上部付近のサポートメニュー、管理者の連絡先](images/admincontacts.png)

3. <span data-ttu-id="667ee-144">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="667ee-144">Select **Add**.</span></span>

    ![管理ポータル、[追加] ボタン、[エクスポートと更新] の左側に](images/adminadd.png)

4.  <span data-ttu-id="667ee-146">**フォーカスの領域**を選択し、連絡先の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="667ee-146">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![他の、アプリ、セキュリティなど、フォーカスがある領域のリスト](images/areaoffocus.png)

5. <span data-ttu-id="667ee-148">フォーカスの領域ごとに繰り返します。</span><span class="sxs-lookup"><span data-stu-id="667ee-148">Repeat for each area of focus.</span></span> 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="667ee-149">Microsoft マネージドデスクトップの使用を開始する手順</span><span class="sxs-lookup"><span data-stu-id="667ee-149">Steps to get started with Microsoft Managed Desktop</span></span>

1. <span data-ttu-id="667ee-150">管理ポータルで管理者の連絡先を追加および確認する (このトピック)</span><span class="sxs-lookup"><span data-stu-id="667ee-150">Add and verify admin contacts in the Admin portal (this topic)</span></span>
2. [<span data-ttu-id="667ee-151">条件付きアクセスを調整する</span><span class="sxs-lookup"><span data-stu-id="667ee-151">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="667ee-152">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="667ee-152">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="667ee-153">デバイスに Intune ポータルサイトをインストールする</span><span class="sxs-lookup"><span data-stu-id="667ee-153">Install Intune Company Portal on on devices</span></span>](company-portal.md)
5. [<span data-ttu-id="667ee-154">Enterprise State Roaming を有効にする</span><span class="sxs-lookup"><span data-stu-id="667ee-154">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="667ee-155">Microsoft マネージドデスクトップデバイスをセットアップする</span><span class="sxs-lookup"><span data-stu-id="667ee-155">Set up Microsoft Managed Desktop devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="667ee-156">ユーザーがデバイスを使えるようにする</span><span class="sxs-lookup"><span data-stu-id="667ee-156">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="667ee-157">アプリをデバイスに展開する</span><span class="sxs-lookup"><span data-stu-id="667ee-157">Deploy apps to devices</span></span>](deploy-apps.md)