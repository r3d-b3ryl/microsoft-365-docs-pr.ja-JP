---
title: 組織での低優先メールの構成
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: 'Exchange PowerShell を使用して、組織内のすべてまたは特定のユーザーの低優先メール機能を有効または無効にする方法について説明します。 '
ms.openlocfilehash: 069cf7569ebb3654e979100291f6754693b24def
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400138"
---
# <a name="configure-clutter-for-your-organization"></a><span data-ttu-id="34c1f-103">組織での低優先メールの構成</span><span class="sxs-lookup"><span data-stu-id="34c1f-103">Configure Clutter for your organization</span></span>

> [!TIP]
> <span data-ttu-id="34c1f-104">[優先受信トレイ](../setup/configure-focused-inbox.md) が低優先メールに置き換わります。</span><span class="sxs-lookup"><span data-stu-id="34c1f-104">[Focused Inbox](../setup/configure-focused-inbox.md) is going to replace Clutter.</span></span> <span data-ttu-id="34c1f-105">詳細については[、「優先受信トレイに関する更新」および「低優先メール](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)機能」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34c1f-105">Learn more: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span></span>
  
<span data-ttu-id="34c1f-106">管理者は、Microsoft 365 の低優先メール機能を管理する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="34c1f-106">As an admin, you may have to manage the Clutter feature in Microsoft 365.</span></span> <span data-ttu-id="34c1f-107">組織内のユーザーに低優先メール機能を有効/無効にするには、Exchange PowerShell を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34c1f-107">To turn the Clutter feature on/off for users in your organization, you must use Exchange PowerShell.</span></span> <span data-ttu-id="34c1f-108">(以下の手順を使用して、この機能をオン/オフにすることができます。 [Outlook での低優先/低優先メール機能](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx))</span><span class="sxs-lookup"><span data-stu-id="34c1f-108">(Individuals can turn it on/off using these instructions: [Turn off/on Clutter in Outlook](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx).)</span></span> 
  
<span data-ttu-id="34c1f-109">Exchange PowerShell の使用の詳細については、 [「Powershell を使用](https://go.microsoft.com/fwlink/?LinkID=402831)して exchange online と Exchange [Online powershell に接続する](https://go.microsoft.com/fwlink/?LinkID=722415)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="34c1f-109">Check out [Using PowerShell with Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831) and [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?LinkID=722415) for details on using Exchange PowerShell.</span></span> <span data-ttu-id="34c1f-110">少なくとも Exchange サービス管理者の役割を持ち、PowerShell を使用して Exchange Online に接続できるアカウントを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="34c1f-110">You need to have an account that has at least the Exchange Service administrator role and the ability to connect to Exchange Online with PowerShell.</span></span> 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a><span data-ttu-id="34c1f-111">Exchange PowerShell を使用して低優先メール機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="34c1f-111">Turn Clutter on using Exchange PowerShell</span></span>

<span data-ttu-id="34c1f-p104">[Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) コマンドレットを実行することで、メールボックスの低優先メールを手動で有効にできます。組織のメールボックスの低優先メール設定を表示することもできます。 [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="34c1f-p104">You can enable Clutter manually for a mailbox by running the [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet. You can also view Clutter settings for mailboxes in your organization by running the [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet.</span></span> 
  
<span data-ttu-id="34c1f-114">アリー ベリューという名前のユーザーの低優先メールをオンにする</span><span class="sxs-lookup"><span data-stu-id="34c1f-114">Turn on Clutter for a single user named Allie Bellew</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a><span data-ttu-id="34c1f-115">Exchange PowerShell を使用して低優先メールをオフにする</span><span class="sxs-lookup"><span data-stu-id="34c1f-115">Turn Clutter off using Exchange PowerShell</span></span>

<span data-ttu-id="34c1f-p105">[Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) コマンドレットを実行することで、メールボックスの低優先メールを手動で無効にできます。組織のメールボックスの **低優先メール**設定を表示することもできます。[Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="34c1f-p105">You can disable Clutter manually for a mailbox by running the [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet. You can also view **Clutter** settings for mailboxes in your organization by running the [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet.</span></span> 
  
<span data-ttu-id="34c1f-118">アリー ベリューという名前のユーザーの低優先メールをオフにする</span><span class="sxs-lookup"><span data-stu-id="34c1f-118">Turn off Clutter for a single user named Allie Bellew:</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

<span data-ttu-id="34c1f-119">PowerShell を使用してユーザーを一括作成する場合、各ユーザーのメールボックスに [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) を実行し、低優先メールを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34c1f-119">If you use PowerShell to bulk create your users, then you'll need to run [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) against each user's mailbox to manage Clutter.</span></span> 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a><span data-ttu-id="34c1f-120">低優先メールのオン/オフ スイッチはどのような場合に、Outlook on the web のユーザーに表示されますか?</span><span class="sxs-lookup"><span data-stu-id="34c1f-120">When does the Clutter on/off switch appear to users in Outlook on the web?</span></span>
<span data-ttu-id="34c1f-121"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="34c1f-121"><a name="bkmk_onoff"> </a></span></span>

<span data-ttu-id="34c1f-122">管理者は、Exchange PowerShell を使用して低優先メール機能を再度有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="34c1f-122">As an admin, you can re-enable Clutter using Exchange PowerShell.</span></span> <span data-ttu-id="34c1f-123">この操作が行われると、優先受信トレイは無効になり、低優先メールが再び有効になります。</span><span class="sxs-lookup"><span data-stu-id="34c1f-123">Once this is done, Focused Inbox will be turned off and Clutter will be active again.</span></span> 
  
 <span data-ttu-id="34c1f-124">**Microsoft 365 Business Premium サブスクリプションを使用して web 上の Outlook を使用している場合:**</span><span class="sxs-lookup"><span data-stu-id="34c1f-124">**If you're using Outlook on the web with a Microsoft 365 Business Premium subscription:**</span></span>
  
- <span data-ttu-id="34c1f-125">ユーザーの低優先メールが現在有効になっている場合:</span><span class="sxs-lookup"><span data-stu-id="34c1f-125">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="34c1f-126">低優先メールの設定は表示されます。</span><span class="sxs-lookup"><span data-stu-id="34c1f-126">Clutter settings appear</span></span>
    
- <span data-ttu-id="34c1f-127">ユーザーの優先受信トレイが現在有効になっている場合:</span><span class="sxs-lookup"><span data-stu-id="34c1f-127">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="34c1f-128">低優先メールの設定は表示されません。</span><span class="sxs-lookup"><span data-stu-id="34c1f-128">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="34c1f-129">低優先メールも優先受信トレイも有効になっていない場合:</span><span class="sxs-lookup"><span data-stu-id="34c1f-129">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="34c1f-130">ユーザーの [メールの設定] にオプションとして低優先メールと優先受信トレイの両方が表示されます。</span><span class="sxs-lookup"><span data-stu-id="34c1f-130">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
 <span data-ttu-id="34c1f-131">**Outlook.com を使用している場合:**</span><span class="sxs-lookup"><span data-stu-id="34c1f-131">**If you're using Outlook.com:**</span></span>
  
- <span data-ttu-id="34c1f-132">ユーザーの低優先メールが現在有効になっている場合:</span><span class="sxs-lookup"><span data-stu-id="34c1f-132">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="34c1f-133">低優先メールの設定は表示されます。</span><span class="sxs-lookup"><span data-stu-id="34c1f-133">Clutter settings appear</span></span>
    
- <span data-ttu-id="34c1f-134">ユーザーの優先受信トレイが現在有効になっている場合:</span><span class="sxs-lookup"><span data-stu-id="34c1f-134">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="34c1f-135">低優先メールの設定は表示されません。</span><span class="sxs-lookup"><span data-stu-id="34c1f-135">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="34c1f-136">低優先メールも優先受信トレイも有効になっていない場合:</span><span class="sxs-lookup"><span data-stu-id="34c1f-136">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="34c1f-137">ユーザーの [メールの設定] にオプションとして低優先メールと優先受信トレイの両方が表示されます。</span><span class="sxs-lookup"><span data-stu-id="34c1f-137">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
- <span data-ttu-id="34c1f-138">ユーザーが過去のある時点で優先受信トレイを有効にした場合:</span><span class="sxs-lookup"><span data-stu-id="34c1f-138">If user enabled Focused Inbox at some point in the past:</span></span>
    
  - <span data-ttu-id="34c1f-139">低優先メールの設定は表示されません。</span><span class="sxs-lookup"><span data-stu-id="34c1f-139">Clutter settings will never appear</span></span>
    
    <span data-ttu-id="34c1f-140">それ以外の場合:</span><span class="sxs-lookup"><span data-stu-id="34c1f-140">Otherwise,</span></span> 
    
  - <span data-ttu-id="34c1f-141">低優先メールの設定は表示されます。</span><span class="sxs-lookup"><span data-stu-id="34c1f-141">Clutter settings will appear</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="34c1f-142">関連記事</span><span class="sxs-lookup"><span data-stu-id="34c1f-142">Related articles</span></span>
<span data-ttu-id="34c1f-143"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="34c1f-143"><a name="bkmk_onoff"> </a></span></span>

[<span data-ttu-id="34c1f-144">Outlook で低優先メール機能を使って優先度の低いメッセージを並べ替える</span><span class="sxs-lookup"><span data-stu-id="34c1f-144">Use Clutter to sort low priority messages in Outlook</span></span>](https://support.office.com/article/use-clutter-to-sort-low-priority-messages-in-outlook-7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0)
    
[<span data-ttu-id="34c1f-145">低優先メール機能を使用して OWA で優先度の低いメッセージを並べ替える</span><span class="sxs-lookup"><span data-stu-id="34c1f-145">Use Clutter to sort low priority messages in OWA</span></span>](https://support.office.com/article/fe4d64ca-bf73-48f1-91b4-9a659e008bce.aspx)
    
[<span data-ttu-id="34c1f-146">Outlook の低優先メール機能をオフにする</span><span class="sxs-lookup"><span data-stu-id="34c1f-146">Turn off Clutter in Outlook</span></span>](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx)
    

