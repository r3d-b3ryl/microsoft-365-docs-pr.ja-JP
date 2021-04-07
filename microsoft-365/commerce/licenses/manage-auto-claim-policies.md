---
title: 自動請求ポリシーを管理する
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
description: 特定のアプリのユーザーにライセンスを自動的に割り当てる自動クレーム ポリシーを作成および管理する方法について説明します。
ms.custom:
- AdminSurgePortfolio
- commerce
search.appverid:
- MET150
ms.openlocfilehash: 001b612820bb13873ec18733d68828837fcecd78
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599453"
---
# <a name="manage-auto-claim-policies"></a><span data-ttu-id="b5ece-103">自動請求ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="b5ece-103">Manage auto-claim policies</span></span>

<span data-ttu-id="b5ece-104">自動クレーム ポリシーを使用すると、ユーザーはアプリに初めてサインインした製品のライセンスを自動的に要求できます。</span><span class="sxs-lookup"><span data-stu-id="b5ece-104">An auto-claim policy lets users automatically claim a license for a product the first time that they sign into an app.</span></span> <span data-ttu-id="b5ece-105">管理者は、通常、手動で、またはグループ ベースのライセンスを使用して、ユーザーにライセンスを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="b5ece-105">As an admin, you typically assign licenses to users either manually, or by using group-based licensing.</span></span> <span data-ttu-id="b5ece-106">自動クレーム ポリシーを使用して、ユーザーがライセンスを自動的に要求できる製品を管理します。</span><span class="sxs-lookup"><span data-stu-id="b5ece-106">By using auto-claim policies, you manage the products for which users can automatically claim licenses.</span></span> <span data-ttu-id="b5ece-107">また、これらのライセンスが提供する製品を制御できます。</span><span class="sxs-lookup"><span data-stu-id="b5ece-107">You can also control which products those licenses come from.</span></span>

<span data-ttu-id="b5ece-108">自動クレーム ポリシーを作成した後、次のタスクを実行してポリシーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="b5ece-108">After you create an auto-claim policy, you can do the following tasks to manage the policy:</span></span>

- [<span data-ttu-id="b5ece-109">ポリシーを有効またはオフにする</span><span class="sxs-lookup"><span data-stu-id="b5ece-109">Turn the policy on or off</span></span>](#turn-a-policy-on-or-off)
- [<span data-ttu-id="b5ece-110">ポリシーの表示名を編集する</span><span class="sxs-lookup"><span data-stu-id="b5ece-110">Edit the policy friendly name</span></span>](#edit-the-policy-friendly-name)
- [<span data-ttu-id="b5ece-111">バックアップ製品の追加または削除</span><span class="sxs-lookup"><span data-stu-id="b5ece-111">Add or remove backup products</span></span>](#add-or-remove-backup-products)
- [<span data-ttu-id="b5ece-112">割り当てアプリとサービスを管理する</span><span class="sxs-lookup"><span data-stu-id="b5ece-112">Manage the assigning apps and services</span></span>](#change-the-assigning-apps-and-services)
- [<span data-ttu-id="b5ece-113">割り当て順序の変更</span><span class="sxs-lookup"><span data-stu-id="b5ece-113">Change the assigning order</span></span>](#change-the-assigning-order-for-backup-products)
- [<span data-ttu-id="b5ece-114">ポリシー レポートの表示</span><span class="sxs-lookup"><span data-stu-id="b5ece-114">View a policy report</span></span>](#view-an-auto-claim-policy-report)

> [!IMPORTANT]
> <span data-ttu-id="b5ece-115">自動クレーム ポリシーは現在、Microsoft Teams でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b5ece-115">Auto-claim policies are currently only available for Microsoft Teams.</span></span> <span data-ttu-id="b5ece-116">今後、より多くの製品を使用できる予定です。</span><span class="sxs-lookup"><span data-stu-id="b5ece-116">More products will be available to use in the future.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b5ece-117">はじめに</span><span class="sxs-lookup"><span data-stu-id="b5ece-117">Before you begin</span></span>

<span data-ttu-id="b5ece-118">自動クレーム ポリシーを作成および管理するには、グローバル管理者、ユーザー管理者、またはライセンス管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5ece-118">You must be a Global, User, or License admin to create and manage auto-claim policies.</span></span> <span data-ttu-id="b5ece-119">詳細については、「[Microsoft 365 の管理者の役割](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5ece-119">For more information, see [About Microsoft 365 admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="turn-the-auto-claim-policy-feature-on-or-off"></a><span data-ttu-id="b5ece-120">自動クレーム ポリシー機能を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="b5ece-120">Turn the auto-claim policy feature on or off</span></span>

<span data-ttu-id="b5ece-121">既定では、自動クレーム ポリシー機能はオフになっています。</span><span class="sxs-lookup"><span data-stu-id="b5ece-121">By default, the auto-claim policy feature is turned off.</span></span> <span data-ttu-id="b5ece-122">機能を使用する前に、最初に有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5ece-122">Before you can use the feature, you must first turn it on.</span></span> <span data-ttu-id="b5ece-123">機能を有効にした後、自動クレーム ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b5ece-123">After you turn on the feature, you can create an auto-claim policy.</span></span>

### <a name="turn-on-auto-claim-policies"></a><span data-ttu-id="b5ece-124">自動クレーム ポリシーを有効にする</span><span class="sxs-lookup"><span data-stu-id="b5ece-124">Turn on auto-claim policies</span></span>

1. <span data-ttu-id="b5ece-125">管理センターで、[課金ライセンス] ページ **に** 移動し、[自動請求ポリシー] タブ \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">を選択</a>します。</span><span class="sxs-lookup"><span data-stu-id="b5ece-125">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="b5ece-126">ページの中央で、[設定を有効にする **] ボタンを選択** します。</span><span class="sxs-lookup"><span data-stu-id="b5ece-126">In the center of the page, select the **Turn on setting** button.</span></span>

### <a name="turn-off-auto-claim-policies"></a><span data-ttu-id="b5ece-127">自動クレーム ポリシーを無効にする</span><span class="sxs-lookup"><span data-stu-id="b5ece-127">Turn off auto-claim policies</span></span>

<span data-ttu-id="b5ece-128">自動クレーム ポリシー設定をオフにできるのは、グローバル管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="b5ece-128">Only a Global admin can turn off an auto-claim policy setting.</span></span>

1. <span data-ttu-id="b5ece-129">管理センターで、[設定組織の設定 **]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">ページに移動</a> します。</span><span class="sxs-lookup"><span data-stu-id="b5ece-129">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Org settings</a> page.</span></span>
2. <span data-ttu-id="b5ece-130">表の下部付近で、[ユーザーが所有 **するアプリとサービス] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b5ece-130">Near the bottom of the table, select **User owned apps and services**.</span></span>
3. <span data-ttu-id="b5ece-131">右側のウィンドウで、[ユーザーが初めてサインインする場合にライセンスを自動要求する] のボックス **をオフにします**。</span><span class="sxs-lookup"><span data-stu-id="b5ece-131">In the right pane, clear the box for **Let users auto-claim licenses the first time they sign in**.</span></span>

<span data-ttu-id="b5ece-132">既にアクティブ なポリシーを持っているが、それ以上のユーザーにライセンスの要求を行いたくない場合は、ポリシー [をオフにします](#turn-a-policy-on-or-off)。</span><span class="sxs-lookup"><span data-stu-id="b5ece-132">If you already have an active policy, but you don't want any more users to claim licenses, [turn off the policy](#turn-a-policy-on-or-off).</span></span> <span data-ttu-id="b5ece-133">自動クレーム ポリシーをオフにした場合、その時点からライセンスを要求できるユーザーはもういなになります。</span><span class="sxs-lookup"><span data-stu-id="b5ece-133">When you turn off an auto-claim policy, no more users can claim a license from that point on.</span></span> <span data-ttu-id="b5ece-134">ライセンスを既に申し立て済みのユーザーは、ライセンスを失う必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5ece-134">Users who already claimed a license don't lose their license.</span></span>

## <a name="create-an-auto-claim-policy"></a><span data-ttu-id="b5ece-135">自動クレーム ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="b5ece-135">Create an auto-claim policy</span></span>

<span data-ttu-id="b5ece-136">[ <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自動要求ポリシー] タブには</a> 、作成するポリシーが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5ece-136">The <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab lists the policies that you create.</span></span> <span data-ttu-id="b5ece-137">このタブには、ポリシーの名前、ポリシーに関連付けられているアプリ、ポリシーに割り当てられている製品、使用可能なライセンスの数、ポリシーの状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5ece-137">On this tab, you can see: the name of the policy, the app that is associated with the policy, the product that's assigned to the policy, the number of available licenses, and the status of the policy.</span></span>

<span data-ttu-id="b5ece-138">自動クレーム ポリシーを作成するときに、バックアップ製品を追加できます。</span><span class="sxs-lookup"><span data-stu-id="b5ece-138">When you create an auto-claim policy, you can add a backup product to it.</span></span> <span data-ttu-id="b5ece-139">プライマリ製品がライセンス外の場合、バックアップ製品を使用してライセンスをユーザーに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="b5ece-139">If the primary product is out of licenses, the backup product is used to assign licenses to users.</span></span> <span data-ttu-id="b5ece-140">最大 4 つのバックアップ製品を追加し、使用する [順序を変更できます](#change-the-assigning-order-for-backup-products)。</span><span class="sxs-lookup"><span data-stu-id="b5ece-140">You can add up to four backup products and [change the order in which they're used](#change-the-assigning-order-for-backup-products).</span></span> <span data-ttu-id="b5ece-141">詳細については、「バックアップ製品を [追加または削除する」を参照してください](#add-or-remove-backup-products)。</span><span class="sxs-lookup"><span data-stu-id="b5ece-141">To learn more, see [Add or remove backup products](#add-or-remove-backup-products).</span></span>

> [!NOTE]
> <span data-ttu-id="b5ece-142">現在、作成できる自動クレーム ポリシーは 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="b5ece-142">Currently, you can only create one auto-claim policy.</span></span> <span data-ttu-id="b5ece-143">作成できるポリシーの数は、この機能を使用できる製品が増えるほど増加します。</span><span class="sxs-lookup"><span data-stu-id="b5ece-143">The number of policies you can create will increase as more products are able to use this feature.</span></span>

1. <span data-ttu-id="b5ece-144">管理センターで、[課金ライセンス] ページ **に** 移動し、[自動請求ポリシー] タブ \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">を選択</a>します。</span><span class="sxs-lookup"><span data-stu-id="b5ece-144">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="b5ece-145">[ポリシー **の追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b5ece-145">Select **Add a policy**.</span></span>
3. <span data-ttu-id="b5ece-146">[この **自動要求ポリシーに名前を付** け] ページで、ポリシーの名前を入力し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="b5ece-146">On the **Name this auto-claim policy** page, enter a name for the policy, then select **Next**.</span></span>
4. <span data-ttu-id="b5ece-147">[自動 **クレーム アプリと製品の設定** ] ページで、ライセンスを割り当てるアプリとサブスクリプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="b5ece-147">On the **Set an auto-claim app and product** page, select an app and the subscription to assign licenses from.</span></span>
5. <span data-ttu-id="b5ece-148">バックアップ製品を追加する場合は、[このポリシーにバックアップ製品を追加する] を選択し、一覧から製品を選択します。</span><span class="sxs-lookup"><span data-stu-id="b5ece-148">If you want to add a backup product, select **Add a backup product to this policy**, then select the product from the list.</span></span>
6. <span data-ttu-id="b5ece-149">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b5ece-149">Select **Next**.</span></span>
7. <span data-ttu-id="b5ece-150">[アプリ **の選択] ページ** で、ライセンスを除外または含めるアプリのボックスをオフまたは選択し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="b5ece-150">On the **Select apps** page, clear or select the boxes for the apps to exclude or include with the license, then select **Next**.</span></span>
8. <span data-ttu-id="b5ece-151">1 つ以上のバックアップ製品を追加した場合は、製品ごとに手順 7 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="b5ece-151">If you added one or more backup products, repeat step 7 for each product.</span></span> <span data-ttu-id="b5ece-152">それ以外の場合は、手順 9 に進みます。</span><span class="sxs-lookup"><span data-stu-id="b5ece-152">Otherwise, go to step 9.</span></span>
9. <span data-ttu-id="b5ece-153">[確認と **完了] ページ** で、新しいポリシー情報を確認し、必要な変更を加え、[ポリシーの作成] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b5ece-153">On the **Review and finish** page, verify the new policy information, make any necessary changes, then select **Create policy**.</span></span>
10. <span data-ttu-id="b5ece-154">**[閉じる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b5ece-154">Select **Close**.</span></span>

## <a name="turn-a-policy-on-or-off"></a><span data-ttu-id="b5ece-155">ポリシーを有効またはオフにする</span><span class="sxs-lookup"><span data-stu-id="b5ece-155">Turn a policy on or off</span></span>

<span data-ttu-id="b5ece-156">ポリシーをオフにした場合、そのポリシーでライセンスを要求できるユーザーは他にはありません。</span><span class="sxs-lookup"><span data-stu-id="b5ece-156">When you turn off a policy, no more users can claim licenses under that policy.</span></span> <span data-ttu-id="b5ece-157">この変更は、そのポリシーで既にライセンスを要求したユーザーには影響しません。</span><span class="sxs-lookup"><span data-stu-id="b5ece-157">The change doesn't affect users who already claimed licenses under that policy.</span></span>

1. <span data-ttu-id="b5ece-158">管理センターで、[課金ライセンス] ページ **に** 移動し、[自動請求ポリシー] タブ \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">を選択</a>します。</span><span class="sxs-lookup"><span data-stu-id="b5ece-158">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="b5ece-159">編集するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b5ece-159">Select the policy that you want to edit.</span></span>
3. <span data-ttu-id="b5ece-160">詳細ウィンドウの [このポリシー **を有効またはオフ** にする] で、チェック ボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="b5ece-160">In the details pane, under **Turn this policy on or off**, select or clear the check box.</span></span>
4. <span data-ttu-id="b5ece-161">[保存 **] を** 選択して詳細ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="b5ece-161">Select **Save** to close the details pane.</span></span>

## <a name="edit-the-policy-friendly-name"></a><span data-ttu-id="b5ece-162">ポリシーの表示名を編集する</span><span class="sxs-lookup"><span data-stu-id="b5ece-162">Edit the policy friendly name</span></span>

1. <span data-ttu-id="b5ece-163">管理センターで、[課金ライセンス] ページ **に** 移動し、[自動請求ポリシー] タブ \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">を選択</a>します。</span><span class="sxs-lookup"><span data-stu-id="b5ece-163">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="b5ece-164">編集するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b5ece-164">Select the policy that you want to edit.</span></span>
3. <span data-ttu-id="b5ece-165">詳細ウィンドウの [ポリシー名] セクション **で** 、[編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="b5ece-165">In the details pane, in the **Policy name** section, select **Edit**.</span></span>
4. <span data-ttu-id="b5ece-166">新しいポリシー名を入力し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="b5ece-166">Enter a new policy name, then select **Save**.</span></span>
5. <span data-ttu-id="b5ece-167">[保存 **] を** 選択して詳細ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="b5ece-167">Select **Save** to close the details pane.</span></span>

## <a name="add-or-remove-backup-products"></a><span data-ttu-id="b5ece-168">バックアップ製品の追加または削除</span><span class="sxs-lookup"><span data-stu-id="b5ece-168">Add or remove backup products</span></span>

<span data-ttu-id="b5ece-169">ポリシーを作成すると、そのポリシーに製品を追加します。</span><span class="sxs-lookup"><span data-stu-id="b5ece-169">When you create a policy, you add a product to it.</span></span> <span data-ttu-id="b5ece-170">その後、ライセンスはそのプールのライセンスからユーザーに自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b5ece-170">Licenses are then automatically assigned to users from that pool of licenses.</span></span> <span data-ttu-id="b5ece-171">自動クレーム ポリシーの製品は、いつでも追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="b5ece-171">You can add or remove products for an auto-claim policy at any time.</span></span> <span data-ttu-id="b5ece-172">ポリシーに関連付けられている製品が既に 1 つある場合、追加する製品はバックアップ製品と見なされます。</span><span class="sxs-lookup"><span data-stu-id="b5ece-172">If you already have one product associated with the policy, any products that you add are considered backup products.</span></span> <span data-ttu-id="b5ece-173">最初の製品の使用可能なライセンス数が使用されている場合、ポリシーはリストの次のバックアップ製品を使用してライセンスを割り当てします。</span><span class="sxs-lookup"><span data-stu-id="b5ece-173">When the available number of licenses from the first product are used up, the policy uses the next backup product on the list to assign licenses from.</span></span> <span data-ttu-id="b5ece-174">製品 [のリストは、好きな方法で](#change-the-assigning-apps-and-services) 並べ替えできます。</span><span class="sxs-lookup"><span data-stu-id="b5ece-174">You [can reorder the list of products](#change-the-assigning-apps-and-services) as you like.</span></span>

<span data-ttu-id="b5ece-175">バックアップ製品を削除すると、ライセンスの割り当てには使用されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="b5ece-175">When you remove a backup product, it's no longer used to assign licenses.</span></span> <span data-ttu-id="b5ece-176">既存のライセンスを持つユーザーは引き続きそのライセンスを持っていますが、その製品のライセンスを新しいユーザーが受け取る権限はありません。</span><span class="sxs-lookup"><span data-stu-id="b5ece-176">Users with an existing license still have that license, but no new users can receive licenses for that product.</span></span>

> [!NOTE]
> <span data-ttu-id="b5ece-177">自動クレーム ポリシーには、少なくとも 1 つの製品が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5ece-177">An auto-claim policy must contain at least one product.</span></span> <span data-ttu-id="b5ece-178">ポリシーからすべての製品を削除できない。</span><span class="sxs-lookup"><span data-stu-id="b5ece-178">You can't remove all products from a policy.</span></span> <span data-ttu-id="b5ece-179">特定の自動クレーム ポリシーからライセンスを割り当てたくない場合は、ポリシー [をオフにします](#view-an-auto-claim-policy-report)。</span><span class="sxs-lookup"><span data-stu-id="b5ece-179">If you don't want to assign licenses from a specific auto-claim policy anymore, [turn off the policy](#view-an-auto-claim-policy-report).</span></span>

### <a name="add-a-backup-product"></a><span data-ttu-id="b5ece-180">バックアップ製品の追加</span><span class="sxs-lookup"><span data-stu-id="b5ece-180">Add a backup product</span></span>

1. <span data-ttu-id="b5ece-181">管理センターで、[課金ライセンス] ページ **に** 移動し、[自動請求ポリシー] タブ \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">を選択</a>します。</span><span class="sxs-lookup"><span data-stu-id="b5ece-181">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="b5ece-182">編集するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b5ece-182">Select the policy that you want to edit.</span></span>
3. <span data-ttu-id="b5ece-183">詳細ウィンドウの下部で、[このポリシーに **バックアップ製品を追加する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b5ece-183">In the details pane, at the bottom, select **Add a backup product to this policy**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="b5ece-184">このリンクが表示されていない場合は、アカウントに関連付けられている製品が 1 つのみだからです。</span><span class="sxs-lookup"><span data-stu-id="b5ece-184">If you don't see this link, it's because you only have one product associated with your account.</span></span>
4. <span data-ttu-id="b5ece-185">[製品 **の追加] ウィンドウ** で、ドロップダウンを使用してポリシーに追加する製品を選択し、[追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="b5ece-185">In the **Add a product** pane, use the drop-down to choose a product to add to the policy, then select **Add**.</span></span>
5. <span data-ttu-id="b5ece-186">[保存 **] を** 選択して詳細ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="b5ece-186">Select **Save** to close the details pane.</span></span>

### <a name="remove-a-backup-product"></a><span data-ttu-id="b5ece-187">バックアップ製品の削除</span><span class="sxs-lookup"><span data-stu-id="b5ece-187">Remove a backup product</span></span>

1. <span data-ttu-id="b5ece-188">管理センターで、[課金ライセンス] ページ **に** 移動し、[自動請求ポリシー] タブ \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">を選択</a>します。</span><span class="sxs-lookup"><span data-stu-id="b5ece-188">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="b5ece-189">編集するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b5ece-189">Select the policy that you want to edit.</span></span>
3. <span data-ttu-id="b5ece-190">詳細ウィンドウの下部にある [製品の削除] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b5ece-190">In the details pane, at the bottom, select **Remove a product**.</span></span>
4. <span data-ttu-id="b5ece-191">[ポリシー **から製品を削除する** ] ウィンドウで、削除するポリシーのボックスを選択し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="b5ece-191">In the **Remove a product from the policy** pane, select the box for the policy that you want to remove, then select **Save**.</span></span>
5. <span data-ttu-id="b5ece-192">詳細ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="b5ece-192">Close the details pane.</span></span>

## <a name="change-the-assigning-apps-and-services"></a><span data-ttu-id="b5ece-193">割り当てアプリとサービスを変更する</span><span class="sxs-lookup"><span data-stu-id="b5ece-193">Change the assigning apps and services</span></span>

<span data-ttu-id="b5ece-194">各製品には、アプリとサービスのコレクションが関連付けられている。</span><span class="sxs-lookup"><span data-stu-id="b5ece-194">Each product has a collection of apps and services associated with it.</span></span>
<span data-ttu-id="b5ece-195">自動クレーム ポリシーの各製品について、ユーザーが自動的にライセンスをその製品に割り当てるときに含めるアプリとサービスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b5ece-195">For each product in your auto-claim policy, you can specify which apps and services to include when a user is automatically assigned a license to that product.</span></span>

1. <span data-ttu-id="b5ece-196">管理センターで、[課金ライセンス] ページ **に** 移動し、[自動請求ポリシー] タブ \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">を選択</a>します。</span><span class="sxs-lookup"><span data-stu-id="b5ece-196">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="b5ece-197">編集するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b5ece-197">Select the policy that you want to edit.</span></span>
3. <span data-ttu-id="b5ece-198">詳細ウィンドウの [アプリとサービス] **で、[** 編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="b5ece-198">In the details pane, under **Apps and services**, select **Edit**.</span></span>
4. <span data-ttu-id="b5ece-199">[アプリ **とサービス] ウィンドウ** の[製品] ドロップダウンから、1 つの製品を選択するか、[すべての製品]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b5ece-199">In the **Apps and services** pane, from the **Product** drop-down, select a single product, or select **All products**.</span></span>
5. <span data-ttu-id="b5ece-200">ユーザーがアクセス権を持つ、またはアクセスできないアプリやサービスのチェック ボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="b5ece-200">Check or clear the boxes for apps and services that you want users to have or not have access to.</span></span>
6. <span data-ttu-id="b5ece-201">完了したら、[保存] を選択 **し**、詳細ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="b5ece-201">When you're finished, select **Save**, then close the details pane.</span></span>

## <a name="change-the-assigning-order-for-backup-products"></a><span data-ttu-id="b5ece-202">バックアップ製品の割り当て順序を変更する</span><span class="sxs-lookup"><span data-stu-id="b5ece-202">Change the assigning order for backup products</span></span>

<span data-ttu-id="b5ece-203">ポリシーにバックアップ製品が割り当てられている場合は、ユーザーがアプリにサインインするときにライセンスの割り当てに使用する順序を変更できます。</span><span class="sxs-lookup"><span data-stu-id="b5ece-203">If you have backup products assigned to the policy, you can change the order in which they're used to assign licenses when users sign in to the app.</span></span>

1. <span data-ttu-id="b5ece-204">管理センターで、[課金ライセンス] ページ **に** 移動し、[自動請求ポリシー] タブ \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">を選択</a>します。</span><span class="sxs-lookup"><span data-stu-id="b5ece-204">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="b5ece-205">編集するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b5ece-205">Select the policy that you want to edit.</span></span>
3. <span data-ttu-id="b5ece-206">詳細ウィンドウの [製品ライセンス] セクションで、移動する製品の横にあるボックスを選択し、[上へ移動] または [下へ移動]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b5ece-206">In the details pane, in the **Product licenses** section, select the box next to the product that you want to move, then select **Move up** or **Move down**.</span></span>
4. <span data-ttu-id="b5ece-207">並べ替える製品ごとに手順 3 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="b5ece-207">Repeat step 3 for each product that you want to reorder.</span></span>
5. <span data-ttu-id="b5ece-208">製品の並べ替えを完了したら、[保存] を選択 **して** 詳細ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="b5ece-208">When you're finished reordering the products, select **Save** to close the details pane.</span></span>

## <a name="view-an-auto-claim-policy-report"></a><span data-ttu-id="b5ece-209">自動クレーム ポリシー レポートの表示</span><span class="sxs-lookup"><span data-stu-id="b5ece-209">View an auto-claim policy report</span></span>

1. <span data-ttu-id="b5ece-210">管理センターで、[課金ライセンス] ページ **に** 移動し、[自動請求ポリシー] タブ \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">を選択</a>します。</span><span class="sxs-lookup"><span data-stu-id="b5ece-210">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="b5ece-211">[レポート **の表示] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b5ece-211">Select **View report**.</span></span> <span data-ttu-id="b5ece-212">[ **自動要求ポリシー レポート] ページには** 、過去 90 日間に各ポリシーから割り当てられたすべてのライセンスが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5ece-212">The **Auto-claim policy report** page lists all licenses assigned from each policy in the last 90 days.</span></span> <span data-ttu-id="b5ece-213">既定では、ページには過去 90 日間が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5ece-213">By default, the page shows the past 90 days.</span></span>
3. <span data-ttu-id="b5ece-214">表示される期間を変更するには、[過去 **30** 日間] ドロップダウン リストを選択します。</span><span class="sxs-lookup"><span data-stu-id="b5ece-214">To change the time period shown, select the **Past 30 days** drop-down list.</span></span> <span data-ttu-id="b5ece-215">過去 1 日、7 日、30 日、90 日間のレポートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="b5ece-215">You can view reports for the past 1, 7, 30, and 90 days.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b5ece-216">次の手順</span><span class="sxs-lookup"><span data-stu-id="b5ece-216">Next steps</span></span>

<span data-ttu-id="b5ece-217">[自動要求ポリシー] **タブに** 定期的に戻って、作成したポリシーの下にライセンスを要求したユーザーの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="b5ece-217">You can periodically return to the **Auto-claim policy** tab to see a list of users who have claimed licenses under the policies you created.</span></span>

## <a name="related-content"></a><span data-ttu-id="b5ece-218">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="b5ece-218">Related content</span></span>

<span data-ttu-id="b5ece-219">[ユーザーにライセンスを割り当てる](../../admin/manage/assign-licenses-to-users.md)(記事)</span><span class="sxs-lookup"><span data-stu-id="b5ece-219">[Assign licenses to users](../../admin/manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="b5ece-220">[サブスクリプション ライセンスの購入または削除](buy-licenses.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="b5ece-220">[Buy or remove subscription licenses](buy-licenses.md) (article)</span></span>\
<span data-ttu-id="b5ece-221">[サブスクリプションとライセンスについて](subscriptions-and-licenses.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="b5ece-221">[Understand subscriptions and licenses](subscriptions-and-licenses.md) (article)</span></span>