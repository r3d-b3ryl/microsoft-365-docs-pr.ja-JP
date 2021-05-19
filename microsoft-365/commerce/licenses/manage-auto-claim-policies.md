---
title: 自動請求ポリシーを管理する
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.review: yinggiy, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_licensing
description: 特定のアプリのライセンスをユーザーに自動的に割り当てる自動請求ポリシーを作成して管理する方法について説明します。
search.appverid: MET150
ms.date: 04/06/2021
ms.openlocfilehash: b104700905b3753466036411368951f12a7012d8
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2021
ms.locfileid: "52331648"
---
# <a name="manage-auto-claim-policies"></a><span data-ttu-id="7ba95-103">自動請求ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="7ba95-103">Manage auto-claim policies</span></span>

<span data-ttu-id="7ba95-104">自動要求ポリシーを使用すると、ユーザーがアプリに初めてサインインすると、自動的に製品のライセンスを要求することができます。</span><span class="sxs-lookup"><span data-stu-id="7ba95-104">An auto-claim policy lets users automatically claim a license for a product the first time that they sign into an app.</span></span> <span data-ttu-id="7ba95-105">通常、管理者は手動で、またはグループ ベースのライセンスを使用して、ライセンスをユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ba95-105">As an admin, you typically assign licenses to users either manually, or by using group-based licensing.</span></span> <span data-ttu-id="7ba95-106">自動要求ポリシーを使用すると、ユーザーが自動的にライセンスを要求できる製品を管理します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-106">By using auto-claim policies, you manage the products for which users can automatically claim licenses.</span></span> <span data-ttu-id="7ba95-107">これらのライセンスの取得先の製品を制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="7ba95-107">You can also control which products those licenses come from.</span></span>

<span data-ttu-id="7ba95-108">自動請求ポリシーを作成した後は、次のタスクを実行してポリシーを管理できます:</span><span class="sxs-lookup"><span data-stu-id="7ba95-108">After you create an auto-claim policy, you can do the following tasks to manage the policy:</span></span>

- [<span data-ttu-id="7ba95-109">このポリシーをオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="7ba95-109">Turn the policy on or off</span></span>](#turn-a-policy-on-or-off)
- [<span data-ttu-id="7ba95-110">ポリシーのフレンドリ名を編集する</span><span class="sxs-lookup"><span data-stu-id="7ba95-110">Edit the policy friendly name</span></span>](#edit-the-policy-friendly-name)
- [<span data-ttu-id="7ba95-111">バックアップ製品を追加または削除する</span><span class="sxs-lookup"><span data-stu-id="7ba95-111">Add or remove backup products</span></span>](#add-or-remove-backup-products)
- [<span data-ttu-id="7ba95-112">割り当て中のアプリとサービスを管理する</span><span class="sxs-lookup"><span data-stu-id="7ba95-112">Manage the assigning apps and services</span></span>](#change-the-assigning-apps-and-services)
- [<span data-ttu-id="7ba95-113">割り当て順序を変更する</span><span class="sxs-lookup"><span data-stu-id="7ba95-113">Change the assigning order</span></span>](#change-the-assigning-order-for-backup-products)
- [<span data-ttu-id="7ba95-114">ポリシー レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="7ba95-114">View a policy report</span></span>](#view-an-auto-claim-policy-report)

> [!IMPORTANT]
> <span data-ttu-id="7ba95-115">現在、自動請求ポリシーは Microsoft Teams でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="7ba95-115">Auto-claim policies are currently only available for Microsoft Teams.</span></span> <span data-ttu-id="7ba95-116">今後もさらに多くの製品でも使用できるようになる予定です。</span><span class="sxs-lookup"><span data-stu-id="7ba95-116">More products will be available to use in the future.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7ba95-117">始める前に</span><span class="sxs-lookup"><span data-stu-id="7ba95-117">Before you begin</span></span>

<span data-ttu-id="7ba95-118">自動請求ポリシーを作成および管理するには、グローバル管理者、ユーザー管理者、またはライセンス管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ba95-118">You must be a Global, User, or License admin to create and manage auto-claim policies.</span></span> <span data-ttu-id="7ba95-119">詳細については、「[Microsoft 365 の管理者の役割](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ba95-119">For more information, see [About Microsoft 365 admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="turn-the-auto-claim-policy-feature-on-or-off"></a><span data-ttu-id="7ba95-120">自動請求ポリシー機能のオンとオフを切り替える</span><span class="sxs-lookup"><span data-stu-id="7ba95-120">Turn the auto-claim policy feature on or off</span></span>

<span data-ttu-id="7ba95-121">既定では、自動請求ポリシー機能はオフになっています。</span><span class="sxs-lookup"><span data-stu-id="7ba95-121">By default, the auto-claim policy feature is turned off.</span></span> <span data-ttu-id="7ba95-122">この機能を使用するには、まずこの機能をオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ba95-122">Before you can use the feature, you must first turn it on.</span></span> <span data-ttu-id="7ba95-123">オンにした後、自動請求ポリシーを作成できるようにまります。</span><span class="sxs-lookup"><span data-stu-id="7ba95-123">After you turn on the feature, you can create an auto-claim policy.</span></span>

### <a name="turn-on-auto-claim-policies"></a><span data-ttu-id="7ba95-124">自動請求ポリシーをオンにする</span><span class="sxs-lookup"><span data-stu-id="7ba95-124">Turn on auto-claim policies</span></span>

1. <span data-ttu-id="7ba95-125">管理センターで、**[課金]** \> **[ライセンス]** のページの順に移動し、<a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">[自動請求ポリシー]</a> のタブを選択します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-125">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="7ba95-126">ページの中央で、**[設定をオンにする]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-126">In the center of the page, select the **Turn on setting** button.</span></span>

### <a name="turn-off-auto-claim-policies"></a><span data-ttu-id="7ba95-127">自動請求ポリシーをオフにする</span><span class="sxs-lookup"><span data-stu-id="7ba95-127">Turn off auto-claim policies</span></span>

<span data-ttu-id="7ba95-128">自動請求ポリシー設定をオフにできるのはグローバル管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="7ba95-128">Only a Global admin can turn off an auto-claim policy setting.</span></span>

1. <span data-ttu-id="7ba95-129">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">[組織の設定]</a> のページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-129">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Org settings</a> page.</span></span>
2. <span data-ttu-id="7ba95-130">表の下部にある **[ユーザー所有のアプリとサービス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-130">Near the bottom of the table, select **User owned apps and services**.</span></span>
3. <span data-ttu-id="7ba95-131">右側のウィンドウで、**[ユーザーが初めてサインインするときに、ライセンスを自動請求させる]** のチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="7ba95-131">In the right pane, clear the box for **Let users auto-claim licenses the first time they sign in**.</span></span>

<span data-ttu-id="7ba95-132">既にアクティブなポリシーがあるが、今後ユーザーにライセンスを請求させたくない場合は、[ポリシーをオフ](#turn-a-policy-on-or-off) にします。</span><span class="sxs-lookup"><span data-stu-id="7ba95-132">If you already have an active policy, but you don't want any more users to claim licenses, [turn off the policy](#turn-a-policy-on-or-off).</span></span> <span data-ttu-id="7ba95-133">自動請求ポリシーをオフにした場合、それ以上ユーザーは、その時点からライセンスを請求できません。</span><span class="sxs-lookup"><span data-stu-id="7ba95-133">When you turn off an auto-claim policy, no more users can claim a license from that point on.</span></span> <span data-ttu-id="7ba95-134">既にライセンスを請求しているユーザーは、ライセンスを失うことはありません。</span><span class="sxs-lookup"><span data-stu-id="7ba95-134">Users who already claimed a license don't lose their license.</span></span>

## <a name="create-an-auto-claim-policy"></a><span data-ttu-id="7ba95-135">自動要求ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="7ba95-135">Create an auto-claim policy</span></span>

<span data-ttu-id="7ba95-136"><a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">[自動請求ポリシー]</a> タブには作成したポリシーの一覧が表示されています。</span><span class="sxs-lookup"><span data-stu-id="7ba95-136">The <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab lists the policies that you create.</span></span> <span data-ttu-id="7ba95-137">このタブには、ポリシーの名前、ポリシーに関連付けられているアプリ、ポリシーに割り当てられている製品、使用可能なライセンスの数、ポリシーの状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ba95-137">On this tab, you can see: the name of the policy, the app that is associated with the policy, the product that's assigned to the policy, the number of available licenses, and the status of the policy.</span></span>

<span data-ttu-id="7ba95-138">自動請求ポリシーを作成するときに、バックアップ製品を追加できます。</span><span class="sxs-lookup"><span data-stu-id="7ba95-138">When you create an auto-claim policy, you can add a backup product to it.</span></span> <span data-ttu-id="7ba95-139">プライマリ製品がライセンス切れの場合、バックアップ製品を使ってユーザーにライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="7ba95-139">If the primary product is out of licenses, the backup product is used to assign licenses to users.</span></span> <span data-ttu-id="7ba95-140">最大 4 つのバックアップ製品を追加し [使用する順序を変更できます](#change-the-assigning-order-for-backup-products)。</span><span class="sxs-lookup"><span data-stu-id="7ba95-140">You can add up to four backup products and [change the order in which they're used](#change-the-assigning-order-for-backup-products).</span></span> <span data-ttu-id="7ba95-141">詳細については、「[バックアップ製品を追加または削除する](#add-or-remove-backup-products)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ba95-141">To learn more, see [Add or remove backup products](#add-or-remove-backup-products).</span></span>

> [!NOTE]
> <span data-ttu-id="7ba95-142">現在、作成できる自動請求ポリシーは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="7ba95-142">Currently, you can only create one auto-claim policy.</span></span> <span data-ttu-id="7ba95-143">この機能を使用できる製品が増えるに従って、作成できるポリシーの数は増加します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-143">The number of policies you can create will increase as more products are able to use this feature.</span></span>

1. <span data-ttu-id="7ba95-144">管理センターで、**[課金]** \> **[ライセンス]** のページの順に移動し、<a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">[自動請求ポリシー]</a> のタブを選択します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-144">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="7ba95-145">**[プロファイルの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-145">Select **Add a policy**.</span></span>
3. <span data-ttu-id="7ba95-146">**[この自動請求ポリシーに名前を付ける]** ページで、ポリシーの名前を入力し、**[次へ]** を 選びます。</span><span class="sxs-lookup"><span data-stu-id="7ba95-146">On the **Name this auto-claim policy** page, enter a name for the policy, then select **Next**.</span></span>
4. <span data-ttu-id="7ba95-147">**[自動請求アプリと製品の設定]** ページで、ライセンスを割り当てるアプリとサブスクリプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-147">On the **Set an auto-claim app and product** page, select an app and the subscription to assign licenses from.</span></span>
5. <span data-ttu-id="7ba95-148">バックアップ製品を追加する場合は、**[このポリシーにバックアップ製品を追加する]** を選択し、リストから製品を選択します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-148">If you want to add a backup product, select **Add a backup product to this policy**, then select the product from the list.</span></span>
6. <span data-ttu-id="7ba95-149">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-149">Select **Next**.</span></span>
7. <span data-ttu-id="7ba95-150">**[アプリ の選択]** ページで、ライセンスに含めるアプリまたはライセンスから外すアプリのチェック ボックスをオンまたはオフにして、**[次へ]** を 選びます。</span><span class="sxs-lookup"><span data-stu-id="7ba95-150">On the **Select apps** page, clear or select the boxes for the apps to exclude or include with the license, then select **Next**.</span></span>
8. <span data-ttu-id="7ba95-151">1 つ以上のバックアップ製品を追加した場合は、製品ごとに手順 7 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-151">If you added one or more backup products, repeat step 7 for each product.</span></span> <span data-ttu-id="7ba95-152">それ以外の場合は、手順 9. に進んでください。</span><span class="sxs-lookup"><span data-stu-id="7ba95-152">Otherwise, go to step 9.</span></span>
9. <span data-ttu-id="7ba95-153">**[確認と完了]** ページで、新しいポリシー情報を確認し、必要な変更を加えた後、**[ポリシーの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-153">On the **Review and finish** page, verify the new policy information, make any necessary changes, then select **Create policy**.</span></span>
10. <span data-ttu-id="7ba95-154">**[閉じる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-154">Select **Close**.</span></span>

## <a name="turn-a-policy-on-or-off"></a><span data-ttu-id="7ba95-155">このポリシーをオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="7ba95-155">Turn a policy on or off</span></span>

<span data-ttu-id="7ba95-156">ポリシーをオフにした場合、そのポリシーでライセンスを請求できるユーザーはいなくなります。</span><span class="sxs-lookup"><span data-stu-id="7ba95-156">When you turn off a policy, no more users can claim licenses under that policy.</span></span> <span data-ttu-id="7ba95-157">この変更は、そのポリシーで既にライセンスを請求しているユーザーには影響しません。</span><span class="sxs-lookup"><span data-stu-id="7ba95-157">The change doesn't affect users who already claimed licenses under that policy.</span></span>

1. <span data-ttu-id="7ba95-158">管理センターで、**[課金]** \> **[ライセンス]** のページの順に移動し、<a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">[自動請求ポリシー]</a> のタブを選択します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-158">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="7ba95-159">編集するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-159">Select the policy that you want to edit.</span></span>
3. <span data-ttu-id="7ba95-160">詳細ウィンドウで **[このポリシーをオンまたはオフにする]** のチェック ボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="7ba95-160">In the details pane, under **Turn this policy on or off**, select or clear the check box.</span></span>
4. <span data-ttu-id="7ba95-161">**[保存]** を選択して、詳細ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7ba95-161">Select **Save** to close the details pane.</span></span>

## <a name="edit-the-policy-friendly-name"></a><span data-ttu-id="7ba95-162">ポリシーのフレンドリ名を編集する</span><span class="sxs-lookup"><span data-stu-id="7ba95-162">Edit the policy friendly name</span></span>

1. <span data-ttu-id="7ba95-163">管理センターで、**[課金]** \> **[ライセンス]** のページの順に移動し、<a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">[自動請求ポリシー]</a> のタブを選択します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-163">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="7ba95-164">編集するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-164">Select the policy that you want to edit.</span></span>
3. <span data-ttu-id="7ba95-165">詳細ウィンドウの **[ポリシー名]** セクションで、**[グループ 編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-165">In the details pane, in the **Policy name** section, select **Edit**.</span></span>
4. <span data-ttu-id="7ba95-166">新しいファイル名を入力し、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-166">Enter a new policy name, then select **Save**.</span></span>
5. <span data-ttu-id="7ba95-167">**[保存]** を選択して、詳細ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7ba95-167">Select **Save** to close the details pane.</span></span>

## <a name="add-or-remove-backup-products"></a><span data-ttu-id="7ba95-168">バックアップ製品を追加または削除する</span><span class="sxs-lookup"><span data-stu-id="7ba95-168">Add or remove backup products</span></span>

<span data-ttu-id="7ba95-169">ポリシーを作成するときに、製品をポリシーに追加します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-169">When you create a policy, you add a product to it.</span></span> <span data-ttu-id="7ba95-170">ライセンスはそのライセンス プールからユーザーに自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="7ba95-170">Licenses are then automatically assigned to users from that pool of licenses.</span></span> <span data-ttu-id="7ba95-171">自動請求ポリシー用の製品は、いつでも追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="7ba95-171">You can add or remove products for an auto-claim policy at any time.</span></span> <span data-ttu-id="7ba95-172">ポリシーに関連付けられた 1 つの製品が既に存在する場合、追加する製品はバックアップ製品と見なされます。</span><span class="sxs-lookup"><span data-stu-id="7ba95-172">If you already have one product associated with the policy, any products that you add are considered backup products.</span></span> <span data-ttu-id="7ba95-173">最初の製品から利用可能なライセンス数を使い切った場合、ポリシーでは、一覧にある次のバックアップ製品を使用してそこからライセンスを割り当てします。</span><span class="sxs-lookup"><span data-stu-id="7ba95-173">When the available number of licenses from the first product are used up, the policy uses the next backup product on the list to assign licenses from.</span></span> <span data-ttu-id="7ba95-174">好みに応じて [製品リストを並べ替えられます](#change-the-assigning-apps-and-services)。</span><span class="sxs-lookup"><span data-stu-id="7ba95-174">You [can reorder the list of products](#change-the-assigning-apps-and-services) as you like.</span></span>

<span data-ttu-id="7ba95-175">バックアップ製品を削除すると、ライセンスの割り当てには使用されません。</span><span class="sxs-lookup"><span data-stu-id="7ba95-175">When you remove a backup product, it's no longer used to assign licenses.</span></span> <span data-ttu-id="7ba95-176">既存のライセンスを持つユーザーは引き続きそのライセンスを保持しますが、新たにその製品のライセンスを受け取るユーザーはいなくなります。</span><span class="sxs-lookup"><span data-stu-id="7ba95-176">Users with an existing license still have that license, but no new users can receive licenses for that product.</span></span>

> [!NOTE]
> <span data-ttu-id="7ba95-177">自動請求ポリシーには、少なくとも 1 つの製品が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ba95-177">An auto-claim policy must contain at least one product.</span></span> <span data-ttu-id="7ba95-178">ポリシーからすべての製品を削除できません。</span><span class="sxs-lookup"><span data-stu-id="7ba95-178">You can't remove all products from a policy.</span></span> <span data-ttu-id="7ba95-179">特定の自動請求ポリシーからライセンスを割り当てたくない場合は [ポリシーをオフ](#view-an-auto-claim-policy-report) にします。</span><span class="sxs-lookup"><span data-stu-id="7ba95-179">If you don't want to assign licenses from a specific auto-claim policy anymore, [turn off the policy](#view-an-auto-claim-policy-report).</span></span>

### <a name="add-a-backup-product"></a><span data-ttu-id="7ba95-180">バックアップ製品の追加</span><span class="sxs-lookup"><span data-stu-id="7ba95-180">Add a backup product</span></span>

1. <span data-ttu-id="7ba95-181">管理センターで、**[課金]** \> **[ライセンス]** のページの順に移動し、<a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">[自動請求ポリシー]</a> のタブを選択します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-181">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="7ba95-182">編集するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-182">Select the policy that you want to edit.</span></span>
3. <span data-ttu-id="7ba95-183">詳細ウィンドウの下部にある **[このポリシーバックアップ 製品を追加する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-183">In the details pane, at the bottom, select **Add a backup product to this policy**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="7ba95-184">このリンクが表示されていないのは、アカウントに関連付けられた製品が 1 つだけのためです。</span><span class="sxs-lookup"><span data-stu-id="7ba95-184">If you don't see this link, it's because you only have one product associated with your account.</span></span>
4. <span data-ttu-id="7ba95-185">**[製品 の追加]** ウィンドウで、ドロップダウンを使用して、ポリシーに追加する製品を選択し、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-185">In the **Add a product** pane, use the drop-down to choose a product to add to the policy, then select **Add**.</span></span>
5. <span data-ttu-id="7ba95-186">**[保存]** を選択して、詳細ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7ba95-186">Select **Save** to close the details pane.</span></span>

### <a name="remove-a-backup-product"></a><span data-ttu-id="7ba95-187">バックアップ製品の削除</span><span class="sxs-lookup"><span data-stu-id="7ba95-187">Remove a backup product</span></span>

1. <span data-ttu-id="7ba95-188">管理センターで、**[課金]** \> **[ライセンス]** のページの順に移動し、<a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">[自動請求ポリシー]</a> のタブを選択します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-188">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="7ba95-189">編集するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-189">Select the policy that you want to edit.</span></span>
3. <span data-ttu-id="7ba95-190">詳細ウィンドウの下部にある **[製品の削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-190">In the details pane, at the bottom, select **Remove a product**.</span></span>
4. <span data-ttu-id="7ba95-191">**[ポリシーから製品を削除する]** ウィンドウで、削除するポリシーのボックスをオンにし、**[保存]** 選択します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-191">In the **Remove a product from the policy** pane, select the box for the policy that you want to remove, then select **Save**.</span></span>
5. <span data-ttu-id="7ba95-192">詳細ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7ba95-192">Close the details pane.</span></span>

## <a name="change-the-assigning-apps-and-services"></a><span data-ttu-id="7ba95-193">割り当て中のアプリとサービスを変更する</span><span class="sxs-lookup"><span data-stu-id="7ba95-193">Change the assigning apps and services</span></span>

<span data-ttu-id="7ba95-194">各製品には、製品に関連付けられたアプリとサービスのコレクションがあります。</span><span class="sxs-lookup"><span data-stu-id="7ba95-194">Each product has a collection of apps and services associated with it.</span></span>
<span data-ttu-id="7ba95-195">自動請求ポリシーの製品ごとに、ユーザーに製品のライセンスが自動的に割り当てられるときに含めるアプリとサービスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="7ba95-195">For each product in your auto-claim policy, you can specify which apps and services to include when a user is automatically assigned a license to that product.</span></span>

1. <span data-ttu-id="7ba95-196">管理センターで、**[課金]** \> **[ライセンス]** のページの順に移動し、<a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">[自動請求ポリシー]</a> のタブを選択します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-196">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="7ba95-197">編集するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-197">Select the policy that you want to edit.</span></span>
3. <span data-ttu-id="7ba95-198">詳細ウィンドウの **[アプリとサービス]** で、**[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-198">In the details pane, under **Apps and services**, select **Edit**.</span></span>
4. <span data-ttu-id="7ba95-199">**[アプリとサービス]** ウィンドウで、**[ 製品]** ドロップダウンで、1 つの製品を選択するか、**[すべての製品]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-199">In the **Apps and services** pane, from the **Product** drop-down, select a single product, or select **All products**.</span></span>
5. <span data-ttu-id="7ba95-200">ユーザーにアクセス権を持たせるアプリとサービスと、アクセス権を持たせないアプリとサービスのチェック ボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="7ba95-200">Check or clear the boxes for apps and services that you want users to have or not have access to.</span></span>
6. <span data-ttu-id="7ba95-201">完了したら、**[保存]** を選択し、詳細ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7ba95-201">When you're finished, select **Save**, then close the details pane.</span></span>

## <a name="change-the-assigning-order-for-backup-products"></a><span data-ttu-id="7ba95-202">バックアップ製品の割り当て順序を変更する</span><span class="sxs-lookup"><span data-stu-id="7ba95-202">Change the assigning order for backup products</span></span>

<span data-ttu-id="7ba95-203">ポリシーにバックアップ製品が割り当てられている場合、ユーザーがアプリにサインインするときにライセンスを割り当てるときに使用する順序を変更できます。</span><span class="sxs-lookup"><span data-stu-id="7ba95-203">If you have backup products assigned to the policy, you can change the order in which they're used to assign licenses when users sign in to the app.</span></span>

1. <span data-ttu-id="7ba95-204">管理センターで、**[課金]** \> **[ライセンス]** のページの順に移動し、<a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">[自動請求ポリシー]</a> のタブを選択します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-204">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="7ba95-205">編集するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-205">Select the policy that you want to edit.</span></span>
3. <span data-ttu-id="7ba95-206">詳細ウィンドウの **[製品ライセンス]** セクションで、移動する製品の横にあるボックスをオンにし、**[上へ移動]** または **[下へ移動]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-206">In the details pane, in the **Product licenses** section, select the box next to the product that you want to move, then select **Move up** or **Move down**.</span></span>
4. <span data-ttu-id="7ba95-207">並べ替える製品ごとに手順 3 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-207">Repeat step 3 for each product that you want to reorder.</span></span>
5. <span data-ttu-id="7ba95-208">製品の並べ替えが完了したら、**[保存]** を選択して詳細ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7ba95-208">When you're finished reordering the products, select **Save** to close the details pane.</span></span>

## <a name="view-an-auto-claim-policy-report"></a><span data-ttu-id="7ba95-209">自動要求ポリシー レポートの表示</span><span class="sxs-lookup"><span data-stu-id="7ba95-209">View an auto-claim policy report</span></span>

1. <span data-ttu-id="7ba95-210">管理センターで、**[課金]** \> **[ライセンス]** のページの順に移動し、<a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">[自動請求ポリシー]</a> のタブを選択します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-210">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="7ba95-211">**[レポートを表示]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="7ba95-211">Select **View report**.</span></span> <span data-ttu-id="7ba95-212">この **[自動請求ポリシー レポート]** には、過去 90 日に各ポリシーから割り当てられたすべてのライセンスが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ba95-212">The **Auto-claim policy report** page lists all licenses assigned from each policy in the last 90 days.</span></span> <span data-ttu-id="7ba95-213">既定では、このページに過去 90 日間分が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ba95-213">By default, the page shows the past 90 days.</span></span>
3. <span data-ttu-id="7ba95-214">表示される期間を変更するには、**[過去 30日]** のドロップダウン リストを選択します。</span><span class="sxs-lookup"><span data-stu-id="7ba95-214">To change the time period shown, select the **Past 30 days** drop-down list.</span></span> <span data-ttu-id="7ba95-215">過去 1日間、7 日間、30 日間、および 90 日間のレポートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="7ba95-215">You can view reports for the past 1, 7, 30, and 90 days.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7ba95-216">次の手順</span><span class="sxs-lookup"><span data-stu-id="7ba95-216">Next steps</span></span>

<span data-ttu-id="7ba95-217">**[自動要求ポリシー]** タブに定期的に戻って、作成したポリシーでライセンスを請求したユーザーの一覧を表示させることができます。</span><span class="sxs-lookup"><span data-stu-id="7ba95-217">You can periodically return to the **Auto-claim policy** tab to see a list of users who have claimed licenses under the policies you created.</span></span>

## <a name="related-content"></a><span data-ttu-id="7ba95-218">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="7ba95-218">Related content</span></span>

<span data-ttu-id="7ba95-219">[ユーザーにライセンスを割り当てる](../../admin/manage/assign-licenses-to-users.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="7ba95-219">[Assign licenses to users](../../admin/manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="7ba95-220">[サブスクリプション ライセンスを購入または削除する](buy-licenses.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="7ba95-220">[Buy or remove subscription licenses](buy-licenses.md) (article)</span></span>\
<span data-ttu-id="7ba95-221">[サブスクリプションとライセンスを理解する](subscriptions-and-licenses.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="7ba95-221">[Understand subscriptions and licenses](subscriptions-and-licenses.md) (article)</span></span>