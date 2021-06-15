---
title: グループの代理として送信または送信するメンバーを許可する
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
recommendations: false
description: グループ メンバーがグループとして電子メールを送信したり、Microsoft 365グループに代わって電子メールを送信Microsoft 365する方法についてMicrosoft 365します。
ms.openlocfilehash: 437040700361c6a09b107a87d8228d2a156375d1
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926141"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a><span data-ttu-id="05b94-103">グループの代理として送信または送信するメンバーを許可する</span><span class="sxs-lookup"><span data-stu-id="05b94-103">Allow members to send as or send on behalf of a group</span></span>

<span data-ttu-id="05b94-104">Send **as** または send onhalf permissions が付与されているMicrosoft 365 グループのメンバーは、グループとして、またはグループの代わりに電子メールを送信できます。</span><span class="sxs-lookup"><span data-stu-id="05b94-104">A member of a Microsoft 365 group who has been granted **Send as** or **Send on behalf** permissions can send email as the group, or on behalf of the group.</span></span> <span data-ttu-id="05b94-105">(グループ内のゲストにこれらのアクセス許可を付与することはできません)。</span><span class="sxs-lookup"><span data-stu-id="05b94-105">(Guests in the group cannot be granted these permissions.)</span></span>

<span data-ttu-id="05b94-106">この記事では、グローバル管理者または管理者がExchangeアクセス許可を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="05b94-106">This article explains how a global or Exchange administrator can set these permissions.</span></span>
  
<span data-ttu-id="05b94-107">たとえば、Megan Bowen が Training **Microsoft 365** グループの一部であり、グループに対するアクセス許可として送信を持つ場合、そのユーザーがグループとして電子メールを送信すると、トレーニング グループが電子メールを送信したのようになります。</span><span class="sxs-lookup"><span data-stu-id="05b94-107">For example, if Megan Bowen is part of the **Training** Microsoft 365 group, and has **Send as** permissions on the group, if she sends an email as the group, it will look like the **Training** group sent the email.</span></span> 
  
<span data-ttu-id="05b94-108">[**代理で送信] アクセス** 許可を使用すると、ユーザーはユーザーグループに代わって電子Microsoft 365できます。</span><span class="sxs-lookup"><span data-stu-id="05b94-108">The **Send on Behalf** permission lets a user send email on behalf of a Microsoft 365 group.</span></span> <span data-ttu-id="05b94-109">たとえば、Alex Wilber がマーケティング Microsoft 365グループの一部であり、Send **on Behalf** アクセス許可を持ち、グループとして電子メールを送信する場合、電子メールは、マーケティングに代わって **Alex Wilber** によって送信されたように見えます。</span><span class="sxs-lookup"><span data-stu-id="05b94-109">For example, if Alex Wilber is a part of the **Marketing** Microsoft 365 group, and has **Send on Behalf** permissions and sends an email as the group, the email looks like it was sent by **Alex Wilber on behalf of Marketing**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="05b94-110">指定したユーザー **に代わって** [送信] **または** [代理送信] を構成できますが、両方は構成できません。</span><span class="sxs-lookup"><span data-stu-id="05b94-110">You can configure **Send as** or **Send on behalf** for a given user, but not both.</span></span> <span data-ttu-id="05b94-111">両方を構成すると、既定で [として送信] **になります**。</span><span class="sxs-lookup"><span data-stu-id="05b94-111">If you configure both, it will default to **Send as**.</span></span>

> [!TIP]
> <span data-ttu-id="05b94-112">[グループから電子](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b)メールを送信する方法については、「Microsoft 365 グループから電子メールを送信する」を参照してください。web 上で Outlook と Outlook を使用してグループから電子メールを送信する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="05b94-112">See [Send email from or on behalf of a Microsoft 365 group](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) to learn how to use Outlook and Outlook on the Web to send email from a group.</span></span>
    
## <a name="allow-members-to-send-email-as-a-group"></a><span data-ttu-id="05b94-113">メンバーがグループとして電子メールを送信するを許可する</span><span class="sxs-lookup"><span data-stu-id="05b94-113">Allow members to send email as a group</span></span>

<span data-ttu-id="05b94-114">このセクションでは、ユーザーがグループとして電子メールを送信する方法について、Exchange管理センター [](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) でExchange Online。</span><span class="sxs-lookup"><span data-stu-id="05b94-114">This section explains how to allow users to send email as a group in the [Exchange admin center](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="05b94-115"><a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a> で、[**受信者**]、[**グループ**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="05b94-115">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="05b94-116">ユーザー **に送信** を許可するグループの [グループの編集] アイコン ![ ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) を選択します。  </span><span class="sxs-lookup"><span data-stu-id="05b94-116">Select **Edit**  ![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="05b94-117">[ **グループ委任**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="05b94-117">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="05b94-118">[Send **As] セクション** で、サインを選択して、送信 **+** するユーザーをグループとして追加します。</span><span class="sxs-lookup"><span data-stu-id="05b94-118">In the **Send As** section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![[送信のスクリーンショット] ダイアログ ボックス](../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. <span data-ttu-id="05b94-120">ユーザーを入力して検索するか、一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="05b94-120">Type to search or pick a user from the list.</span></span> <span data-ttu-id="05b94-121">**[OK] と [** 保存]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="05b94-121">Select **OK** and **Save**.</span></span>
    
    ![リストからユーザーを検索または選択する入力](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a><span data-ttu-id="05b94-123">メンバーがグループに代わって電子メールを送信するを許可する</span><span class="sxs-lookup"><span data-stu-id="05b94-123">Allow members to send email on behalf of a group</span></span>

<span data-ttu-id="05b94-124">このセクションでは、ユーザーが組織の管理センター (EAC) のグループに代わって電子メールを送信Exchangeする方法についてExchange Online。</span><span class="sxs-lookup"><span data-stu-id="05b94-124">This section explains how to allow users to send email on behalf of a group in the Exchange admin center (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="05b94-125"><a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a> で、[**受信者**]、[**グループ**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="05b94-125">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="05b94-126">ユーザー **に送信** を許可するグループの [グループの編集] アイコン ![ ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) を選択します。</span><span class="sxs-lookup"><span data-stu-id="05b94-126">Select **Edit** ![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="05b94-127">[ **グループ委任**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="05b94-127">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="05b94-128">[代理で送信] セクションで、署名を選択して、グループとして送信する **+** ユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="05b94-128">In the Send on Behalf section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![ダイアログの代わりに送信のスクリーンショット](../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. <span data-ttu-id="05b94-130">ユーザーを入力して検索するか、一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="05b94-130">Type to search or pick a user from the list.</span></span> <span data-ttu-id="05b94-131">**[OK] と [** 保存]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="05b94-131">Select **OK** and **Save**.</span></span>
    
    ![リストからユーザーを検索または選択する入力](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a><span data-ttu-id="05b94-133">関連資料</span><span class="sxs-lookup"><span data-stu-id="05b94-133">Related articles</span></span>

[<span data-ttu-id="05b94-134">コラボレーション ガバナンス計画のステップ バイ ステップ</span><span class="sxs-lookup"><span data-stu-id="05b94-134">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="05b94-135">コラボレーション ガバナンス 計画の作成</span><span class="sxs-lookup"><span data-stu-id="05b94-135">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="05b94-136">グループの詳細Microsoft 365する</span><span class="sxs-lookup"><span data-stu-id="05b94-136">Learn more about Microsoft 365 groups</span></span>](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[<span data-ttu-id="05b94-137">Add-RecipientPermission</span><span class="sxs-lookup"><span data-stu-id="05b94-137">Add-RecipientPermission</span></span>](/powershell/module/exchange/add-recipientpermission)

[<span data-ttu-id="05b94-138">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="05b94-138">Set-UnifiedGroup</span></span>](/powershell/module/exchange/set-unifiedgroup)