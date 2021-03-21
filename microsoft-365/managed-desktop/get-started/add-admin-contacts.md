---
title: 管理ポータルで、管理者の連絡先を、追加および確認する
description: フォーカス領域ごとに問い合わせ先を教えて下さい。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 18823db8ca8d4bfa82b8ab6265ee8a0902a13e79
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925894"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a><span data-ttu-id="614f0-104">管理ポータルで、管理者の連絡先を、追加および確認する</span><span class="sxs-lookup"><span data-stu-id="614f0-104">Add and verify admin contacts in the Admin portal</span></span>

<span data-ttu-id="614f0-105">Microsoft Managed Desktop サービスが顧客と通信する方法は複数あります。</span><span class="sxs-lookup"><span data-stu-id="614f0-105">There are several ways that Microsoft Managed Desktop service communicates with customers.</span></span> <span data-ttu-id="614f0-106">コミュニケーションを合理化し、適切なユーザーと確認するには、一連の管理者連絡先を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="614f0-106">To streamline communication and ensure we’re checking with the right people, you need to provide a set of admin contacts.</span></span> <span data-ttu-id="614f0-107">Microsoft Managed Desktop IT Operations は、テナントのトラブルシューティングに関する問題についてこれらのユーザーに問い合わせています。</span><span class="sxs-lookup"><span data-stu-id="614f0-107">Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="614f0-108">管理ポータルにこれらの連絡先を既に追加している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="614f0-108">You might have already added these contacts in the Admin portal.</span></span> <span data-ttu-id="614f0-109">その場合は、重大なインシデントが発生した場合に Microsoft Managed **Desktop** が連絡先リストにアクセスできる必要がありますので、連絡先リストが正確か確認してください。</span><span class="sxs-lookup"><span data-stu-id="614f0-109">If so, take a moment now to double-check that the contact list is accurate, since Microsoft Managed Desktop **must** be able to reach them if a severe incident occurs.</span></span>

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="614f0-110">Microsoft Managed Desktop Admin ポータルの Azure Active Directory アクセス</span><span class="sxs-lookup"><span data-stu-id="614f0-110">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="614f0-111">Microsoft Managed Desktop Admin ポータルでは、ポータルにアクセスするユーザーが次の Azure Active Directory (AD) の役割のいずれかを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="614f0-111">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>
- <span data-ttu-id="614f0-112">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="614f0-112">Global Administrator</span></span>
- <span data-ttu-id="614f0-113">Intune サービス管理者</span><span class="sxs-lookup"><span data-stu-id="614f0-113">Intune Service Administrator</span></span>
- <span data-ttu-id="614f0-114">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="614f0-114">Global Reader</span></span>
- <span data-ttu-id="614f0-115">サービス サポート管理者</span><span class="sxs-lookup"><span data-stu-id="614f0-115">Service Support Administrator</span></span>

<span data-ttu-id="614f0-116">組織を Microsoft Managed Desktop に登録するには、グローバル管理者が必要です。</span><span class="sxs-lookup"><span data-stu-id="614f0-116">The Global Administrator must be the one to enroll your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="614f0-117">5 つの役割はすべて、タスクを開始および表示するための管理ポータル内で同じアクセス権を持ちます。</span><span class="sxs-lookup"><span data-stu-id="614f0-117">All five roles have the same access within the Admin portal to initiate and view tasks.</span></span> <span data-ttu-id="614f0-118">Azure Active Directory でのこれらのロールの割り当てAD詳細については [、「Administrator role permissions in Azure Active Directory」を参照してください](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="614f0-118">For more information on assigning these roles in Azure AD, see [Administrator role permissions in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> 

## <a name="admin-contact-areas-of-focus"></a><span data-ttu-id="614f0-119">管理者の連絡先のフォーカス領域</span><span class="sxs-lookup"><span data-stu-id="614f0-119">Admin contact areas of focus</span></span>

<span data-ttu-id="614f0-120">管理者の連絡先は、質問に答え、さまざまな分野で決定を下す最適な人物またはグループである必要があります。</span><span class="sxs-lookup"><span data-stu-id="614f0-120">Admin contacts should be the best person or group that can answer questions and make decisions for different areas of focus.</span></span> <span data-ttu-id="614f0-121">**Microsoft Managed Desktop Operations は、お客様から送信されたサポート要求に関する質問について、管理者の連絡先に問い合わせします。**</span><span class="sxs-lookup"><span data-stu-id="614f0-121">**Microsoft Managed Desktop Operations will contact these Admin contacts for questions involving support requests filed by the customer.**</span></span> <span data-ttu-id="614f0-122">これらの管理者の連絡先は、サポート要求の更新と新しいメッセージに関する通知を受け取る。</span><span class="sxs-lookup"><span data-stu-id="614f0-122">These Admin contacts will receive notifications for support request updates and new messages.</span></span> <span data-ttu-id="614f0-123">これらの領域には、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="614f0-123">These areas include:</span></span>

<span data-ttu-id="614f0-124">フォーカス領域</span><span class="sxs-lookup"><span data-stu-id="614f0-124">Area of focus</span></span> | <span data-ttu-id="614f0-125">に関する質問</span><span class="sxs-lookup"><span data-stu-id="614f0-125">For questions about</span></span>
--- | ---
<span data-ttu-id="614f0-126">アプリのパッケージ化</span><span class="sxs-lookup"><span data-stu-id="614f0-126">App packaging</span></span> | <span data-ttu-id="614f0-127">アプリのパッケージ化のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="614f0-127">Troubleshooting app packaging</span></span>
<span data-ttu-id="614f0-128">デバイス</span><span class="sxs-lookup"><span data-stu-id="614f0-128">Devices</span></span> | <span data-ttu-id="614f0-129">デバイスの正常性、Microsoft Managed Desktop デバイスでのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="614f0-129">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="614f0-130">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="614f0-130">Security</span></span> | <span data-ttu-id="614f0-131">Microsoft Managed Desktop デバイスに関するセキュリティの問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="614f0-131">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="614f0-132">IT ヘルプ デスク</span><span class="sxs-lookup"><span data-stu-id="614f0-132">IT help desk</span></span> | <span data-ttu-id="614f0-133">Microsoft Managed Desktop サポート領域外でサポート スタッフがユーザー チケットを引き渡す場合</span><span class="sxs-lookup"><span data-stu-id="614f0-133">in cases where our Support staff hands over user tickets outside of Microsoft Managed Desktop support areas</span></span> 
<span data-ttu-id="614f0-134">その他</span><span class="sxs-lookup"><span data-stu-id="614f0-134">Other</span></span> | <span data-ttu-id="614f0-135">他の領域でカバーされていない問題の場合</span><span class="sxs-lookup"><span data-stu-id="614f0-135">For issues not covered by other areas</span></span>

<span data-ttu-id="614f0-136">**これらの連絡先を選択するユーザーは、Microsoft Managed Desktop 環境に関する意思決定を行う知識と権限を持っている必要があります。**</span><span class="sxs-lookup"><span data-stu-id="614f0-136">**Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment.**</span></span> <span data-ttu-id="614f0-137">Microsoft Managed Desktop 環境をオンボードすると、ローカルのヘルプデスクとセキュリティの連絡先を追加するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="614f0-137">When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="614f0-138">サポート要求を送信する場合は、 [管理者の連絡先が必要です](../service-description/support.md)。</span><span class="sxs-lookup"><span data-stu-id="614f0-138">Admin contacts are required when you [submit a Support request](../service-description/support.md).</span></span> <span data-ttu-id="614f0-139">サポート要求のフォーカス領域の管理者連絡先が必要です。</span><span class="sxs-lookup"><span data-stu-id="614f0-139">You’ll need to have an admin contact for the focus area of the Support request.</span></span> 

<span data-ttu-id="614f0-140">**管理者連絡先を追加するには**</span><span class="sxs-lookup"><span data-stu-id="614f0-140">**To add admin contacts**</span></span>

1.  <span data-ttu-id="614f0-141">[Microsoft Managed Desktop 管理ポータルにサインインします](https://aka.ms/mwaasportal)。</span><span class="sxs-lookup"><span data-stu-id="614f0-141">Sign in to [Microsoft Managed Desktop admin portal](https://aka.ms/mwaasportal).</span></span> 

2.  <span data-ttu-id="614f0-142">[サポート **] で**、[管理者連絡先] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="614f0-142">Under **Support**, select **Admin contacts**.</span></span> 

    ![[サポート] メニューの [選択した上部の近くの管理者の連絡先]](../../media/admincontacts.png)

3. <span data-ttu-id="614f0-144">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="614f0-144">Select **Add**.</span></span>

    ![[エクスポートと更新] の左側にある管理ポータルの [追加] ボタン](../../media/adminadd.png)

4.  <span data-ttu-id="614f0-146">[フォーカスエリア **] を選択** し、連絡先の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="614f0-146">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![その他、アプリ、セキュリティなどのフォーカス領域の一覧](../../media/areaoffocus.png)

5. <span data-ttu-id="614f0-148">フォーカス領域ごとに繰り返します。</span><span class="sxs-lookup"><span data-stu-id="614f0-148">Repeat for each area of focus.</span></span> 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="614f0-149">Microsoft Managed Desktop の使用を開始する手順</span><span class="sxs-lookup"><span data-stu-id="614f0-149">Steps to get started with Microsoft Managed Desktop</span></span>

1. <span data-ttu-id="614f0-150">管理ポータルで管理者連絡先を追加して確認する (このトピック)</span><span class="sxs-lookup"><span data-stu-id="614f0-150">Add and verify admin contacts in the Admin portal (this topic)</span></span>
2. [<span data-ttu-id="614f0-151">条件付きアクセスを調整する</span><span class="sxs-lookup"><span data-stu-id="614f0-151">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="614f0-152">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="614f0-152">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="614f0-153">Intune ポータル サイトをデバイスにインストールする</span><span class="sxs-lookup"><span data-stu-id="614f0-153">Install Intune Company Portal on on devices</span></span>](company-portal.md)
5. [<span data-ttu-id="614f0-154">Enterprise State Roaming を有効にする</span><span class="sxs-lookup"><span data-stu-id="614f0-154">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="614f0-155">Microsoft マネージド デスクトップのデバイスをセットアップする</span><span class="sxs-lookup"><span data-stu-id="614f0-155">Set up Microsoft Managed Desktop devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="614f0-156">ユーザーがデバイスを使えるようにする</span><span class="sxs-lookup"><span data-stu-id="614f0-156">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="614f0-157">アプリをデバイスに展開する</span><span class="sxs-lookup"><span data-stu-id="614f0-157">Deploy apps to devices</span></span>](deploy-apps.md)