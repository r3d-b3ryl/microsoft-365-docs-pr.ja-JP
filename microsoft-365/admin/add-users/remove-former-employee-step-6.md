---
title: 手順 6 - 元従業員からMicrosoft 365ライセンスを削除および削除する
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
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 次の手順に従って、元Microsoft 365ライセンスを削除します。
ms.openlocfilehash: ed86eb28cc6d4996f7def8cb567f0e4085e67624
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244214"
---
# <a name="step-6---remove-the-microsoft-365-license-from-a-former-employee"></a><span data-ttu-id="2622f-103">手順 6 - 元従業員Microsoft 365ライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="2622f-103">Step 6 - Remove the Microsoft 365 license from a former employee</span></span>

<span data-ttu-id="2622f-104">他のユーザーが組織を離れた後にライセンスの支払いを行わない場合は、そのユーザーのライセンスを削除Microsoft 365サブスクリプションから削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2622f-104">If you don't want to pay for a license after someone leaves your organization, you need to remove their Microsoft 365 license and then delete it from your subscription.</span></span> <span data-ttu-id="2622f-105">ライセンスを削除しない場合は、別のユーザーにライセンスを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="2622f-105">You can assign a license to another user if you don't delete it.</span></span>
  
<span data-ttu-id="2622f-106">ライセンスの削除後、そのユーザーのすべてのデータが 30 日間保持されます。</span><span class="sxs-lookup"><span data-stu-id="2622f-106">When you remove the license, all that user's data is held for 30 days.</span></span> <span data-ttu-id="2622f-107">データに[アクセス](get-access-to-and-back-up-a-former-user-s-data.md)したり、ユーザーが復帰した場合にアカウントを[復元](restore-user.md)したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="2622f-107">You can [access](get-access-to-and-back-up-a-former-user-s-data.md) the data, or [restore](restore-user.md) the account if the user comes back.</span></span> <span data-ttu-id="2622f-108">30 日後、すべてのユーザーのデータ (SharePoint Online に保存されているドキュメントを除く) は Microsoft 365 から完全に削除され、回復できません。</span><span class="sxs-lookup"><span data-stu-id="2622f-108">After 30 days, all the user's data (except for documents stored on SharePoint Online) is permanently deleted from Microsoft 365 and can't be recovered.</span></span>

1. <span data-ttu-id="2622f-109">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="2622f-109">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="2622f-110">ブロックする従業員の名前を選択し、[ライセンスとアプリ] **タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="2622f-110">Select the name of the employee that you want to block, and then select the **Licenses and Apps** tab.</span></span>
3. <span data-ttu-id="2622f-111">削除するライセンスのチェック ボックスをオフにし、[変更の保存] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="2622f-111">Clear the check boxes for the license(s) you want to remove, and then select **Save changes**.</span></span>

<span data-ttu-id="2622f-112">**他のユーザーを雇うまで** 支払うライセンスの数を減らすには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2622f-112">**To reduce the number of licenses you're paying for** until you hire another person, do the following steps:</span></span>

1. <span data-ttu-id="2622f-113">管理センターで、[製品の請求] ページ **に** 移動し、[ \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank"></a>製品] タブ **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="2622f-113">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page, and select the **Products** tab.</span></span>
2. <span data-ttu-id="2622f-114">ライセンスを削除するサブスクリプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="2622f-114">Select the subscription from which you want to remove licenses.</span></span>
3. <span data-ttu-id="2622f-115">詳細ページで、[ライセンスの削除] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="2622f-115">On the details page, select **Remove licenses**.</span></span>
4. <span data-ttu-id="2622f-116">[ライセンス **の削除]** ウィンドウの [新しい数量] の [ライセンスの合計] **ボックスに、** このサブスクリプションに必要なライセンスの総数を入力します。</span><span class="sxs-lookup"><span data-stu-id="2622f-116">In the **Remove licenses** pane, under New quantity, in the **Total licenses** box, enter the total number of licenses that you want for this subscription.</span></span> <span data-ttu-id="2622f-117">たとえば、25 のライセンスを持ち、そのうちの 1 つを削除する場合は、「24」と入力します。</span><span class="sxs-lookup"><span data-stu-id="2622f-117">For example, if you have 25 licenses and you want to remove one of them, enter 24.</span></span>
5. <span data-ttu-id="2622f-118">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2622f-118">Select **Save**.</span></span>

<span data-ttu-id="2622f-119">ビジネスに [別のユーザー](add-users.md) を追加すると、1 つの手順でライセンスを同時に購入するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2622f-119">When you [add another person](add-users.md) to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

<span data-ttu-id="2622f-120">Microsoft 365 for business のユーザー ライセンスの管理の詳細については、「ビジネス向け[Microsoft 365](../manage/assign-licenses-to-users.md)のユーザーにライセンスを割り当てる」および「Microsoft 365 for business のユーザーからのライセンス[の割り当て解除」を](../manage/remove-licenses-from-users.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="2622f-120">For more information about managing user licenses for Microsoft 365 for business, see [Assign licenses to users in Microsoft 365 for business](../manage/assign-licenses-to-users.md), and [Unassign licenses from users in Microsoft 365 for business](../manage/remove-licenses-from-users.md).</span></span>
  
## <a name="how-the-deleted-employee-account-affects-skype-for-business"></a><span data-ttu-id="2622f-121">削除した従業員のアカウントが Skype for Business に与える影響</span><span class="sxs-lookup"><span data-stu-id="2622f-121">How the deleted employee account affects Skype for Business</span></span>

<span data-ttu-id="2622f-p104">Office 365 からユーザーのライセンスを削除すると、ユーザーに関連付けられている PSTN 通話番号が解放されます。この番号を別のユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="2622f-p104">When you remove a user's license from Office 365, the PSTN calling number associated with the user will be released. You can assign it to another user.</span></span>
  
<span data-ttu-id="2622f-p105">ユーザーがキュー グループに属している場合、ユーザーは呼び出しキューのエージェントの実行可能な対象にならなくなります。そのため、呼び出しキューに関連付けられているグループからもユーザーを削除することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2622f-p105">If the user belongs to a queue group, they will no longer be a viable target of the call queue agents. So, we recommend also removing the user from the groups associated with the call queue.</span></span>

## <a name="set-up-call-forwarding-to-people-in-your-organization"></a><span data-ttu-id="2622f-126">組織内のユーザーへの通話転送を設定する</span><span class="sxs-lookup"><span data-stu-id="2622f-126">Set up call forwarding to people in your organization</span></span>

<span data-ttu-id="2622f-127">終了した従業員の電話番号の通話転送を設定する必要がある場合は、通話ポリシーの下の通話転送設定で、着信通話を他のユーザーに転送したり、同時に他のユーザーを呼び出したりできる転送を設定できます。</span><span class="sxs-lookup"><span data-stu-id="2622f-127">If you need to set up call forwarding for the terminated employee's phone number, the call forwarding setting under calling policies can set up forwarding where incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> <span data-ttu-id="2622f-128">詳細については、「通話ポリシー」[を参照Microsoft Teams。](/microsoftteams/teams-calling-policy)</span><span class="sxs-lookup"><span data-stu-id="2622f-128">For more information, see [Calling policies in Microsoft Teams](/microsoftteams/teams-calling-policy).</span></span>
