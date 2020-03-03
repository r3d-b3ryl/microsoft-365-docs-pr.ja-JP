---
title: メンバーがグループに代わって送信または送信できるようにする
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: メンバーが Office 365 グループとしてメールを送信できるようにする方法、または Office 365 グループの代理としてメールを送信できるようにする方法について説明します。
ms.openlocfilehash: 0179dbd2e3093ce80929f6c5f9e689aece845a40
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2020
ms.locfileid: "42352758"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a><span data-ttu-id="b24e2-103">メンバーがグループに代わって送信または送信できるようにする</span><span class="sxs-lookup"><span data-stu-id="b24e2-103">Allow members to send as or send on behalf of a Group</span></span>

<span data-ttu-id="b24e2-104">**メールボックス所有者として送信する**アクセス許可または **代理人として送信する**アクセス許可が付与されている Office 365 グループのメンバーは、グループとして、またはグループに代わってメールを送信できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b24e2-104">A member of an Office 365 Group who has been granted **Send as** or **Send on behalf** permissions can now send email as the group, or on behalf of the group.</span></span> <span data-ttu-id="b24e2-105">このトピックでは、管理者がこれらのアクセス許可を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b24e2-105">This topic explains how an admin can set these permissions.</span></span>
  
<span data-ttu-id="b24e2-106">たとえば、Megan Bowen が**トレーニング**Office 365 グループの一部であり、グループに対して**送信**者アクセス許可を持っている場合、グループとしてメールを送信すると、その電子メールを送信した**トレーニング**グループのように表示されます。</span><span class="sxs-lookup"><span data-stu-id="b24e2-106">For example, if Megan Bowen is part of the **Training** Office 365 Group, and has **Send as** permissions on the group, if she sends an email as the Group, it will look like the **Training** group sent the email.</span></span> 
  
<span data-ttu-id="b24e2-107">**代理人として送信する**アクセス許可は、ユーザーが Office 365 グループに代わってメールを送信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="b24e2-107">The **Send on Behalf** permission lets a user send email on behalf of an Office 365 Group.</span></span> <span data-ttu-id="b24e2-108">たとえば、Alex が**マーケティング**Office 365 グループに含まれていて、**代理人**として送信するアクセス許可を持ち、グループとして電子メールを送信する場合、電子メールは、**マーケティングの代理**として Alex によって送信されたように見えます。</span><span class="sxs-lookup"><span data-stu-id="b24e2-108">For example, if Alex Wilber is a part of the **Marketing** Office 365 Group, and has **Send on Behalf** permissions and sends an email as the group, the email looks like it was sent by **Alex Wilber on behalf of Marketing**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b24e2-109">特定のユーザーに対し**て [送信**] または **[代理送信**] を構成できますが、両方を構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="b24e2-109">You can configure **Send as** or **Send on behalf** for a given user, but not both.</span></span> <span data-ttu-id="b24e2-110">両方を構成した場合、既定では**として送信**されます。</span><span class="sxs-lookup"><span data-stu-id="b24e2-110">If you configure both, it will default to **Send as**.</span></span>

> [!TIP]
> <span data-ttu-id="b24e2-111">Outlook および Outlook on the Web を使用してグループからメールを送信する方法については、「 [Office 365 グループの代理としてメールを送信](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx)する」の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b24e2-111">Check the out the steps in [Send email from or on behalf of an Office 365 group](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx) to learn how to use Outlook and Outlook on the Web to send email from a Group.</span></span>
    
## <a name="allow-members-to-send-email-as-a-group"></a><span data-ttu-id="b24e2-112">メンバーがグループとしてメールを送信できるようにする</span><span class="sxs-lookup"><span data-stu-id="b24e2-112">Allow members to send email as a Group</span></span>

<span data-ttu-id="b24e2-113">このセクションでは、exchange Online の[exchange 管理センター](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) でユーザーがグループとしてメールを送信できるようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b24e2-113">This section explains how to allow users to send email as a Group in the [Exchange admin center](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="b24e2-114"><a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a> で、[**受信者**]、[**グループ**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="b24e2-114">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="b24e2-115">ユーザーが送信者とし](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png)て送信できるようにするグループの [編集グループの編集] アイコンを選択します。 \*\*\*\*![  </span><span class="sxs-lookup"><span data-stu-id="b24e2-115">Select **Edit**  ![Edit group icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on Group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="b24e2-116">[ **グループ委任**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b24e2-116">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="b24e2-117">[**送信**] セクションで、グループと**+** して送信するユーザーを追加するための署名を選択します。</span><span class="sxs-lookup"><span data-stu-id="b24e2-117">In the **Send As** section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![プラス記号を選択して、Office 365 グループとして送信するユーザーを追加します。](../../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. <span data-ttu-id="b24e2-119">ユーザーを入力して検索するか、一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b24e2-119">Type to search or pick a user from the list.</span></span> <span data-ttu-id="b24e2-120">[ **OK]** を選択して、**保存**します。</span><span class="sxs-lookup"><span data-stu-id="b24e2-120">Select **OK** and **Save**.</span></span>
    
    ![リストからユーザーを検索または選択するには、「」と入力します。](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a><span data-ttu-id="b24e2-122">メンバーがグループに代わって電子メールを送信することを許可する</span><span class="sxs-lookup"><span data-stu-id="b24e2-122">Allow members to send email on behalf of a Group</span></span>

<span data-ttu-id="b24e2-123">このセクションでは、exchange Online の Exchange 管理センター (EAC) で、ユーザーがグループに代わって電子メールを送信できるようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b24e2-123">This section explains how to allow users to send email on behalf of a Group in the Exchange admin center (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="b24e2-124"><a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a> で、[**受信者**]、[**グループ**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="b24e2-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="b24e2-125">ユーザーが送信者とし](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png)て送信できるようにするグループの [編集グループ**の編集] アイコンを選択し**ます。 ![</span><span class="sxs-lookup"><span data-stu-id="b24e2-125">Select **Edit** ![Edit group icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the Group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="b24e2-126">[ **グループ委任**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b24e2-126">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="b24e2-127">[代理人として送信する] **+** セクションで、グループとして送信するユーザーを追加するための署名を選択します。</span><span class="sxs-lookup"><span data-stu-id="b24e2-127">In the Send on Behalf section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![プラス記号を選択して、Office 365 グループとして送信するユーザーを追加します。](../../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. <span data-ttu-id="b24e2-129">ユーザーを入力して検索するか、一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b24e2-129">Type to search or pick a user from the list.</span></span> <span data-ttu-id="b24e2-130">[ **OK]** を選択して、**保存**します。</span><span class="sxs-lookup"><span data-stu-id="b24e2-130">Select **OK** and **Save**.</span></span>
    
    ![リストからユーザーを検索または選択するには、「」と入力します。](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a><span data-ttu-id="b24e2-132">関連記事</span><span class="sxs-lookup"><span data-stu-id="b24e2-132">Related articles</span></span>

[<span data-ttu-id="b24e2-133">Office 365 グループの詳細について</span><span class="sxs-lookup"><span data-stu-id="b24e2-133">Learn more about Office 365 Groups</span></span>](https://support.office.com/article/3f780e8e-61aa-4287-830d-ff6209cbc192.aspx)

<span data-ttu-id="b24e2-134">[[受信者の追加] アクセス許可](https://go.microsoft.com/fwlink/p/?LinkId=723960)</span><span class="sxs-lookup"><span data-stu-id="b24e2-134">[Add-RecipientPermission](https://go.microsoft.com/fwlink/p/?LinkId=723960)</span></span>

[<span data-ttu-id="b24e2-135">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="b24e2-135">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189)
