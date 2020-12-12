---
title: メンバーがグループとして送信またはグループの代わりに送信を許可する
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: メンバーが Microsoft 365 グループとしてメールを送信したり、Microsoft 365 グループの代わりにメールを送信したりする方法について説明します。
ms.openlocfilehash: 6dff559eceec1b719f31d577d7fff8f604636a47
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663585"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a><span data-ttu-id="2b879-103">メンバーがグループとして送信またはグループの代わりに送信を許可する</span><span class="sxs-lookup"><span data-stu-id="2b879-103">Allow members to send as or send on behalf of a group</span></span>

<span data-ttu-id="2b879-104">[送信者] または [代理送信] アクセス許可が付与されているMicrosoft 365 グループのメンバーは、グループとして、またはグループの代理として電子メールを送信できます。</span><span class="sxs-lookup"><span data-stu-id="2b879-104">A member of a Microsoft 365 group who has been granted **Send as** or **Send on behalf** permissions can send email as the group, or on behalf of the group.</span></span> <span data-ttu-id="2b879-105">この記事では、グローバル管理者または Exchange 管理者がこれらのアクセス許可を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2b879-105">This article explains how a global or Exchange administrator can set these permissions.</span></span>
  
<span data-ttu-id="2b879-106">たとえば、Megan Bowen が **Training** Microsoft 365 グループの一部であり、グループに対する送信アクセス許可を持つ場合、そのユーザーがグループとしてメールを送信すると、そのメールを送信したトレーニング グループのようになります。</span><span class="sxs-lookup"><span data-stu-id="2b879-106">For example, if Megan Bowen is part of the **Training** Microsoft 365 group, and has **Send as** permissions on the group, if she sends an email as the group, it will look like the **Training** group sent the email.</span></span> 
  
<span data-ttu-id="2b879-107">[ **代理送信] アクセス** 許可を使用すると、ユーザーは Microsoft 365 グループの代わりにメールを送信できます。</span><span class="sxs-lookup"><span data-stu-id="2b879-107">The **Send on Behalf** permission lets a user send email on behalf of a Microsoft 365 group.</span></span> <span data-ttu-id="2b879-108">たとえば、Alex Wilber が **Marketing** Microsoft 365 グループの一部であり、代理送信のアクセス許可を持ち、グループとしてメールを送信する場合、電子メールはマーケティングの代わりに **Alex Wilber** によって送信されたように見えます。</span><span class="sxs-lookup"><span data-stu-id="2b879-108">For example, if Alex Wilber is a part of the **Marketing** Microsoft 365 group, and has **Send on Behalf** permissions and sends an email as the group, the email looks like it was sent by **Alex Wilber on behalf of Marketing**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2b879-109">指定したユーザー **の [ユーザーとして送信]** または [ **代理** 送信] を構成できますが、両方を構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="2b879-109">You can configure **Send as** or **Send on behalf** for a given user, but not both.</span></span> <span data-ttu-id="2b879-110">両方を構成する場合は、既定で [次のように **送信] が設定されます**。</span><span class="sxs-lookup"><span data-stu-id="2b879-110">If you configure both, it will default to **Send as**.</span></span>

> [!TIP]
> <span data-ttu-id="2b879-111">Outlook と Outlook on the Web を使用してグループからメールを送信する方法については [、「Microsoft 365](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) グループからメールを送信する」または「Microsoft 365 グループの代理でメールを送信する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b879-111">See [Send email from or on behalf of a Microsoft 365 group](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) to learn how to use Outlook and Outlook on the Web to send email from a group.</span></span>
    
## <a name="allow-members-to-send-email-as-a-group"></a><span data-ttu-id="2b879-112">メンバーがグループとしてメールを送信する</span><span class="sxs-lookup"><span data-stu-id="2b879-112">Allow members to send email as a group</span></span>

<span data-ttu-id="2b879-113">このセクションでは、ユーザーが Exchange Online の [Exchange](https://go.microsoft.com/fwlink/p/?linkid=2059104) 管理センター (EAC) でグループとしてメールを送信する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2b879-113">This section explains how to allow users to send email as a group in the [Exchange admin center](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="2b879-114"><a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a> で、[**受信者**]、[**グループ**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="2b879-114">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="2b879-115">ユーザー **に送信** を許可するグループの [グループの編集] ![ ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) アイコンを選択します。  </span><span class="sxs-lookup"><span data-stu-id="2b879-115">Select **Edit**  ![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="2b879-116">[ **グループ委任**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="2b879-116">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="2b879-117">[送信 **者] セクション** で、署名を選択して、グループとして送信 **+** するユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="2b879-117">In the **Send As** section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![[送信] ダイアログ ボックスのスクリーンショット](../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. <span data-ttu-id="2b879-119">ユーザーを入力して検索するか、一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="2b879-119">Type to search or pick a user from the list.</span></span> <span data-ttu-id="2b879-120">**[OK] を選択** し、[保存 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="2b879-120">Select **OK** and **Save**.</span></span>
    
    ![一覧からユーザーを検索または選択する入力](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a><span data-ttu-id="2b879-122">グループの代わりにメンバーが電子メールを送信できる</span><span class="sxs-lookup"><span data-stu-id="2b879-122">Allow members to send email on behalf of a group</span></span>

<span data-ttu-id="2b879-123">このセクションでは、ユーザーが Exchange Online の Exchange 管理センター (EAC) でグループの代理として電子メールを送信する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2b879-123">This section explains how to allow users to send email on behalf of a group in the Exchange admin center (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="2b879-124"><a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a> で、[**受信者**]、[**グループ**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="2b879-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="2b879-125">ユーザー **に送信** を許可するグループの [グループの編集] ![ ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="2b879-125">Select **Edit** ![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="2b879-126">[ **グループ委任**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="2b879-126">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="2b879-127">[代理送信] セクションで、署名を選択して、グループとして送信 **+** するユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="2b879-127">In the Send on Behalf section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![[代理送信] ダイアログのスクリーンショット](../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. <span data-ttu-id="2b879-129">ユーザーを入力して検索するか、一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="2b879-129">Type to search or pick a user from the list.</span></span> <span data-ttu-id="2b879-130">**[OK] を選択** し、[保存 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="2b879-130">Select **OK** and **Save**.</span></span>
    
    ![一覧からユーザーを検索または選択する入力](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a><span data-ttu-id="2b879-132">関連記事</span><span class="sxs-lookup"><span data-stu-id="2b879-132">Related articles</span></span>

[<span data-ttu-id="2b879-133">グループコラボレーション ガバナンスの計画のステップ バイ ステップ</span><span class="sxs-lookup"><span data-stu-id="2b879-133">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="2b879-134">コラボレーション ガバナンス計画を作成する</span><span class="sxs-lookup"><span data-stu-id="2b879-134">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="2b879-135">Microsoft 365 グループの詳細</span><span class="sxs-lookup"><span data-stu-id="2b879-135">Learn more about Microsoft 365 groups</span></span>](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[<span data-ttu-id="2b879-136">Add-RecipientPermission</span><span class="sxs-lookup"><span data-stu-id="2b879-136">Add-RecipientPermission</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[<span data-ttu-id="2b879-137">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="2b879-137">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189)
