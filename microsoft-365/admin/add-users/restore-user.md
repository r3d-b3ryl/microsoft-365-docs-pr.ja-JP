---
title: ユーザーを復元する
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c261e42-5dd1-48b0-845f-2a016d29cfc1
description: 削除されたユーザー アカウントとすべての関連データを復元する方法について学習します。
ms.openlocfilehash: d14995c8ee2d62c1d722ef0bcc7577745a747082
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "50113999"
---
# <a name="restore-a-user"></a><span data-ttu-id="70639-103">ユーザーを復元する</span><span class="sxs-lookup"><span data-stu-id="70639-103">Restore a user</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="70639-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="70639-104">The admin center is changing.</span></span> <span data-ttu-id="70639-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70639-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end
   
<span data-ttu-id="70639-p102">ユーザー アカウントを削除してから 30 日以内に復元すると、そのアカウントと関連するすべてのデータが復元されます。ユーザーは同じ職場や学校のアカウントでサインインできます。ユーザーのメールボックスは完全に復元されます。特定のユーザー アカウントを復元できなくなるまでの残り時間を知るには、[サポートにお問い合わせください](../contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="70639-p102">When you restore a user account within 30 days after deleting it, the account and all associated data are restored. The user can sign in with the same work or school account. Their mailbox will be fully restored. To find out how much time remains before a specific user account can no longer be restored, [contact us](../contact-support-for-business-products.md).</span></span>
  
<span data-ttu-id="70639-110">いくつかのヒントをご紹介します。</span><span class="sxs-lookup"><span data-stu-id="70639-110">Here are a couple of tips:</span></span>
  
- <span data-ttu-id="70639-111">アカウントに割り当て可能なライセンスを確認します。</span><span class="sxs-lookup"><span data-stu-id="70639-111">Make sure licenses are available to assign to the account.</span></span>
    
- <span data-ttu-id="70639-112">Active Directory を使用している場合、ユーザー アカウントを復元する手順については、「[Office 365、Azure、Intune で削除済みのユーザー アカウントをトラブルシューティングする方法](https://support.microsoft.com/kb/2619308)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70639-112">If your business uses Active Directory, see [How to troubleshoot deleted user accounts in Office 365](https://support.microsoft.com/kb/2619308) for instructions on restoring a user account.</span></span> 
    
## <a name="restore-one-or-more-user-accounts"></a><span data-ttu-id="70639-113">1 つ以上のユーザー アカウントを復元する</span><span class="sxs-lookup"><span data-stu-id="70639-113">Restore one or more user accounts</span></span>

<span data-ttu-id="70639-114">これらの手順を実行するには、Microsoft 365 のグローバル管理者またはユーザー管理管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="70639-114">You must be a Microsoft 365 global admin or user management admin to do these steps.</span></span> 
  
 
::: moniker range="o365-worldwide"

1. <span data-ttu-id="70639-115">管理センターで、[削除されたユーザー]ページ \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">に移動</a>します。</span><span class="sxs-lookup"><span data-stu-id="70639-115">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="70639-116">管理センターに [移動し、[](https://go.microsoft.com/fwlink/p/?linkid=848041)削除されたユーザー  ] \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="70639-116">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="70639-117">管理センターに [移動し、[](https://go.microsoft.com/fwlink/p/?linkid=850627)削除されたユーザー  ] \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="70639-117">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

2. <span data-ttu-id="70639-118">[削除 **済みユーザー]** ページで、復元するユーザーの名前を選択し、[復元] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="70639-118">On the **Deleted users** page, select the names of the users who you want to restore, and then select **Restore**.</span></span>
    
 
3. <span data-ttu-id="70639-119">プロンプトに従ってパスワードを設定し、[復元] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="70639-119">Follow the prompts to set their password, and then select **Restore**.</span></span>
    
4. <span data-ttu-id="70639-120">ユーザーが正常に復元された場合は、[メールを送信して閉じる **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="70639-120">If the user is successfully restored, select **Send email and close**.</span></span> <span data-ttu-id="70639-121">名前の競合またはプロキシ アドレスの競合が発生した場合は、これらのアカウントの復元方法については、以下の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70639-121">If you encounter a name conflict or proxy address conflict, see the instructions below for how to restore those accounts.</span></span>
    
<span data-ttu-id="70639-122">ユーザーを復元した後、ユーザーのパスワードが変更されたと通知し、ユーザーをフォローアップします。</span><span class="sxs-lookup"><span data-stu-id="70639-122">After you've restored a user, make sure you notify them that their password changed and you follow up with them.</span></span>
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a><span data-ttu-id="70639-123">ユーザー名が競合するユーザーを復元する</span><span class="sxs-lookup"><span data-stu-id="70639-123">Restore a user that has a user name conflict</span></span>
<span data-ttu-id="70639-124"><a name="RestoreUserNameConflict"> </a></span><span class="sxs-lookup"><span data-stu-id="70639-124"><a name="RestoreUserNameConflict"> </a></span></span>

<span data-ttu-id="70639-125">ユーザー アカウントを削除し、同じユーザー名で (同じユーザーの、または名前が似ている別のユーザーの) ユーザー アカウントを新しく作成した後、削除したアカウントを復元しようとすると、ユーザー名の競合が発生します。</span><span class="sxs-lookup"><span data-stu-id="70639-125">A user name conflict occurs when you delete a user account, create a new user account with the same user name (either for the same user or another user with a similar name), and later try to restore the deleted account.</span></span>
  
<span data-ttu-id="70639-p104">この問題を修正するには、アクティブなユーザー アカウントを復元しているアカウントに置き換えます。または、復元しているアカウントに別のユーザー名を割り当てて、同じユーザー名で複数のアカウントが存在しないようにします。次のように行います。</span><span class="sxs-lookup"><span data-stu-id="70639-p104">To fix this, replace the active user account with the one that you are restoring. Or, assign a different user name to the account that you are restoring so that there aren't two accounts with the same user name. Here are the steps.</span></span>
  

::: moniker range="o365-worldwide"

1. <span data-ttu-id="70639-129">管理センターで、[削除されたユーザー]ページ \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">に移動</a>します。</span><span class="sxs-lookup"><span data-stu-id="70639-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="70639-130">管理センターに [移動し、[](https://go.microsoft.com/fwlink/p/?linkid=848041)削除されたユーザー  ] \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="70639-130">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="70639-131">管理センターに [移動し、[](https://go.microsoft.com/fwlink/p/?linkid=850627)削除されたユーザー  ] \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="70639-131">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

  
2. <span data-ttu-id="70639-132">[削除 **済みユーザー]** ページで、復元するユーザーの名前を選択し、[復元] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="70639-132">On the **Deleted users** page, select the names of the users that you want to restore, and then select **Restore**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="70639-p105">2 人以上のユーザーの復元が失敗した場合、エラー メッセージで一部のユーザーの復元操作が失敗したことが示されます。ログを見て復元されなかったユーザーを確認し、失敗したアカウントを 1 つずつ復元します。</span><span class="sxs-lookup"><span data-stu-id="70639-p105">If two or more users fail to be restored, an error message advises you that the restore operation failed for some users. View the log to see which users were not restored, and then restore the failed accounts one at a time.</span></span> 
  
3. <span data-ttu-id="70639-135">プロンプトに従ってパスワードを設定し、[復元] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="70639-135">Follow the prompts to set the password and select **Restore**.</span></span>
    
4. <span data-ttu-id="70639-p106">アカウントの復元に問題があったことを示すメッセージが表示されます。次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="70639-p106">A message pops up that says there was a problem restoring the account. Do one of the following:</span></span>
    
  - <span data-ttu-id="70639-p107">復元をキャンセルし、現在のアクティブなユーザーの名前を変更します。もう一度復元を試みます。</span><span class="sxs-lookup"><span data-stu-id="70639-p107">Cancel the restore and rename the current active user. Then attempt the restore again.</span></span>
    
  - <span data-ttu-id="70639-140">または、ユーザーの新しいプライマリ メール アドレスを入力し、[復元] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="70639-140">OR, type a new primary email address for the user and select **Restore**.</span></span>
    
5. <span data-ttu-id="70639-141">結果を確認し、[ **閉じる**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="70639-141">Review the results, and then select **Close**.</span></span>
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a><span data-ttu-id="70639-142">プロキシ アドレスが競合するユーザーを復元する</span><span class="sxs-lookup"><span data-stu-id="70639-142">Restore a user that has a proxy address conflict</span></span>

<span data-ttu-id="70639-p108">プロキシ アドレスを含むユーザー アカウントを削除し、同じプロキシ アドレスを別のアカウントに割り当てた後、削除したアカウントを復元しようとすると、プロキシ アドレスの競合が発生します。この問題を解決するには、次の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="70639-p108">A proxy address conflict occurs when you delete a user account that contains a proxy address, assign the same proxy address to another account, and then try to restore the deleted account. Follow the steps below to fix this issue.</span></span>
  
<span data-ttu-id="70639-145">これを行うには [、Microsoft](about-admin-roles.md) 365 の管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="70639-145">You must have [admin permissions](about-admin-roles.md) in Microsoft 365 to do this.</span></span> 
  

::: moniker range="o365-worldwide"

1. <span data-ttu-id="70639-146">管理センターで、[削除されたユーザー]ページ \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">に移動</a>します。</span><span class="sxs-lookup"><span data-stu-id="70639-146">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="70639-147">管理センターに [移動し、[](https://go.microsoft.com/fwlink/p/?linkid=848041)削除されたユーザー  ] \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="70639-147">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="70639-148">管理センターに [移動し、[](https://go.microsoft.com/fwlink/p/?linkid=850627)削除されたユーザー  ] \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="70639-148">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

2. <span data-ttu-id="70639-149">[ **削除済みのユーザー**] ページで、復元するユーザーを選択して、[ **復元**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="70639-149">On the **Deleted users** page, select the user that you want to restore, and then select **Restore**.</span></span> 
    
3. <span data-ttu-id="70639-150">[復元 **] ページで** 、指示に従ってパスワードを設定し、[復元] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="70639-150">On the **Restore** page, follow the instructions to set the password and select **Restore**.</span></span> <span data-ttu-id="70639-151">競合しているプロキシ アドレスは、復元したユーザーから自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="70639-151">Any conflicting proxy addresses are automatically removed from the user you are restoring.</span></span>
    
4. <span data-ttu-id="70639-152">結果を確認し、[ **閉じる**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="70639-152">Review the results, and then select **Close**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="70639-153">関連記事</span><span class="sxs-lookup"><span data-stu-id="70639-153">Related articles</span></span>

[<span data-ttu-id="70639-154">ユーザーの削除</span><span class="sxs-lookup"><span data-stu-id="70639-154">Delete a user</span></span>](delete-a-user.md)
  
