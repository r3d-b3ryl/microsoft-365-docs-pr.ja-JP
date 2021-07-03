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
ms.openlocfilehash: ba4f1b0e4b2e00334dbffb4bf0aa9edb1b8c5622
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286923"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a><span data-ttu-id="7ac49-104">管理ポータルで、管理者の連絡先を、追加および確認する</span><span class="sxs-lookup"><span data-stu-id="7ac49-104">Add and verify admin contacts in the Admin portal</span></span>

<span data-ttu-id="7ac49-105">サービスが顧客とMicrosoft マネージド デスクトップする方法は複数あります。</span><span class="sxs-lookup"><span data-stu-id="7ac49-105">There are several ways that Microsoft Managed Desktop service communicates with customers.</span></span> <span data-ttu-id="7ac49-106">コミュニケーションを合理化し、適切なユーザーと確認するには、一連の管理者連絡先を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ac49-106">To streamline communication and ensure we’re checking with the right people, you need to provide a set of admin contacts.</span></span> <span data-ttu-id="7ac49-107">Microsoft マネージド デスクトップIT 運用は、テナントのトラブルシューティングに関する問題について、これらのユーザーに問い合わせています。</span><span class="sxs-lookup"><span data-stu-id="7ac49-107">Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7ac49-108">管理ポータルにこれらの連絡先を既に追加している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7ac49-108">You might have already added these contacts in the Admin portal.</span></span> <span data-ttu-id="7ac49-109">その場合は、重大なインシデントが発生した場合Microsoft マネージド デスクトップ連絡先 **リストが正確** である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ac49-109">If so, take a moment now to double-check that the contact list is accurate, since Microsoft Managed Desktop **must** be able to reach them if a severe incident occurs.</span></span>

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="7ac49-110">Azure Active Directory管理ポータルMicrosoft マネージド デスクトップアクセス権</span><span class="sxs-lookup"><span data-stu-id="7ac49-110">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="7ac49-111">Microsoft マネージド デスクトップ管理ポータルでは、ポータルにアクセスするユーザーに次のいずれかの役割 (Azure Active Directory) AD必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ac49-111">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>

- <span data-ttu-id="7ac49-112">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="7ac49-112">Global Administrator</span></span>
- <span data-ttu-id="7ac49-113">Intune サービス管理者</span><span class="sxs-lookup"><span data-stu-id="7ac49-113">Intune Service Administrator</span></span>
- <span data-ttu-id="7ac49-114">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="7ac49-114">Global Reader</span></span>
- <span data-ttu-id="7ac49-115">サービス サポート管理者</span><span class="sxs-lookup"><span data-stu-id="7ac49-115">Service Support Administrator</span></span>

<span data-ttu-id="7ac49-116">グローバル管理者は、組織を登録する管理者である必要Microsoft マネージド デスクトップ。</span><span class="sxs-lookup"><span data-stu-id="7ac49-116">The Global Administrator must be the one to enroll your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="7ac49-117">5 つの役割はすべて、タスクを開始および表示するための管理ポータル内で同じアクセス権を持ちます。</span><span class="sxs-lookup"><span data-stu-id="7ac49-117">All five roles have the same access within the Admin portal to initiate and view tasks.</span></span> <span data-ttu-id="7ac49-118">Azure AD でこれらのロールを割り当てる方法の詳細については、「管理者ロールのアクセス許可」を[参照](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="7ac49-118">For more information on assigning these roles in Azure AD, see [Administrator role permissions in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

## <a name="admin-contact-areas-of-focus"></a><span data-ttu-id="7ac49-119">管理者の連絡先のフォーカス領域</span><span class="sxs-lookup"><span data-stu-id="7ac49-119">Admin contact areas of focus</span></span>

<span data-ttu-id="7ac49-120">管理者の連絡先は、質問に答え、さまざまな分野で決定を下す最適な人物またはグループである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ac49-120">Admin contacts should be the best person or group that can answer questions and make decisions for different areas of focus.</span></span> <span data-ttu-id="7ac49-121">**Microsoft マネージド デスクトップ操作は、顧客が要求したサポート要求に関する質問について、これらの管理者の連絡先に連絡します。**</span><span class="sxs-lookup"><span data-stu-id="7ac49-121">**Microsoft Managed Desktop Operations will contact these Admin contacts for questions involving support requests filed by the customer.**</span></span> <span data-ttu-id="7ac49-122">これらの管理者の連絡先は、サポート要求の更新と新しいメッセージに関する通知を受け取る。</span><span class="sxs-lookup"><span data-stu-id="7ac49-122">These Admin contacts will receive notifications for support request updates and new messages.</span></span> <span data-ttu-id="7ac49-123">これらの領域には、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7ac49-123">These areas include:</span></span>

<span data-ttu-id="7ac49-124">フォーカス領域</span><span class="sxs-lookup"><span data-stu-id="7ac49-124">Area of focus</span></span> | <span data-ttu-id="7ac49-125">に関する質問</span><span class="sxs-lookup"><span data-stu-id="7ac49-125">For questions about</span></span>
--- | ---
<span data-ttu-id="7ac49-126">アプリのパッケージ化</span><span class="sxs-lookup"><span data-stu-id="7ac49-126">App packaging</span></span> | <span data-ttu-id="7ac49-127">アプリのパッケージ化のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="7ac49-127">Troubleshooting app packaging</span></span>
<span data-ttu-id="7ac49-128">デバイス</span><span class="sxs-lookup"><span data-stu-id="7ac49-128">Devices</span></span> | <span data-ttu-id="7ac49-129">デバイスの正常性、デバイスとデバイスMicrosoft マネージド デスクトップトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="7ac49-129">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="7ac49-130">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="7ac49-130">Security</span></span> | <span data-ttu-id="7ac49-131">デバイスのセキュリティに関するMicrosoft マネージド デスクトップトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="7ac49-131">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="7ac49-132">IT ヘルプ デスク</span><span class="sxs-lookup"><span data-stu-id="7ac49-132">IT help desk</span></span> | <span data-ttu-id="7ac49-133">サポートスタッフがサポートエリア外でユーザーチケットを引き渡Microsoft マネージド デスクトップ場合</span><span class="sxs-lookup"><span data-stu-id="7ac49-133">in cases where our Support staff hands over user tickets outside of Microsoft Managed Desktop support areas</span></span> 
<span data-ttu-id="7ac49-134">その他</span><span class="sxs-lookup"><span data-stu-id="7ac49-134">Other</span></span> | <span data-ttu-id="7ac49-135">他の領域でカバーされていない問題の場合</span><span class="sxs-lookup"><span data-stu-id="7ac49-135">For issues not covered by other areas</span></span>

<span data-ttu-id="7ac49-136">**これらの連絡先に対して選択するユーザーは、自分の環境に関する意思決定を行う知識と権限を持Microsoft マネージド デスクトップです。**</span><span class="sxs-lookup"><span data-stu-id="7ac49-136">**Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment.**</span></span> <span data-ttu-id="7ac49-137">アプリ環境をオンボードMicrosoft マネージド デスクトップ、ローカル のヘルプデスクとセキュリティの連絡先を追加するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ac49-137">When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="7ac49-138">サポート要求を送信する場合は、 [管理者の連絡先が必要です](../service-description/support.md)。</span><span class="sxs-lookup"><span data-stu-id="7ac49-138">Admin contacts are required when you [submit a Support request](../service-description/support.md).</span></span> <span data-ttu-id="7ac49-139">サポート要求のフォーカス領域の管理者連絡先が必要です。</span><span class="sxs-lookup"><span data-stu-id="7ac49-139">You’ll need to have an admin contact for the focus area of the Support request.</span></span>

<span data-ttu-id="7ac49-140">**管理者連絡先を追加するには**</span><span class="sxs-lookup"><span data-stu-id="7ac49-140">**To add admin contacts**</span></span>

1. <span data-ttu-id="7ac49-141">サインインして [Microsoft エンドポイント マネージャー][をクリックします](https://endpoint.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="7ac49-141">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com).</span></span>

2. <span data-ttu-id="7ac49-142">[**テナントの管理]** で、[連絡先] セクションを探 **Microsoft マネージド デスクトップ[** 管理者連絡先]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7ac49-142">Under **Tenant administration**, look for the **Microsoft Managed Desktop** section then select **Admin contacts**.</span></span>

3. <span data-ttu-id="7ac49-143">[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7ac49-143">Select **Add**.</span></span>

4. <span data-ttu-id="7ac49-144">[フォーカスエリア **] を選択** し、連絡先の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="7ac49-144">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![その他、アプリ、セキュリティなどのフォーカス領域の一覧](../../media/areaoffocus.png)

5. <span data-ttu-id="7ac49-146">フォーカス領域ごとに繰り返します。</span><span class="sxs-lookup"><span data-stu-id="7ac49-146">Repeat for each area of focus.</span></span>

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="7ac49-147">データの使用を開始するMicrosoft マネージド デスクトップ</span><span class="sxs-lookup"><span data-stu-id="7ac49-147">Steps to get started with Microsoft Managed Desktop</span></span>

1. <span data-ttu-id="7ac49-148">管理ポータルで管理者連絡先を追加して確認する (このトピック)</span><span class="sxs-lookup"><span data-stu-id="7ac49-148">Add and verify admin contacts in the Admin portal (this topic)</span></span>
2. [<span data-ttu-id="7ac49-149">条件付きアクセスを調整する</span><span class="sxs-lookup"><span data-stu-id="7ac49-149">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="7ac49-150">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="7ac49-150">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="7ac49-151">Intune ポータル サイトをデバイスにインストールする</span><span class="sxs-lookup"><span data-stu-id="7ac49-151">Install Intune Company Portal on on devices</span></span>](company-portal.md)
5. [<span data-ttu-id="7ac49-152">Enterprise State Roaming を有効にする</span><span class="sxs-lookup"><span data-stu-id="7ac49-152">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="7ac49-153">Microsoft マネージド デスクトップのデバイスをセットアップする</span><span class="sxs-lookup"><span data-stu-id="7ac49-153">Set up Microsoft Managed Desktop devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="7ac49-154">ユーザーがデバイスを使えるようにする</span><span class="sxs-lookup"><span data-stu-id="7ac49-154">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="7ac49-155">アプリをデバイスに展開する</span><span class="sxs-lookup"><span data-stu-id="7ac49-155">Deploy apps to devices</span></span>](deploy-apps.md)
