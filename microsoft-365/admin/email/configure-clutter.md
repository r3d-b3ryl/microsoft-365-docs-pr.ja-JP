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
description: 'PowerShell を使用して、組織内のすべてのユーザーまたは特定のユーザーに対してクラッター機能を有効または無効Exchangeします。 '
ms.openlocfilehash: ac68893bc0aeea5ab214698c54524921e2b1921d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915904"
---
# <a name="configure-clutter-for-your-organization"></a><span data-ttu-id="1b98e-103">組織での低優先メールの構成</span><span class="sxs-lookup"><span data-stu-id="1b98e-103">Configure Clutter for your organization</span></span>

> [!TIP]
> <span data-ttu-id="1b98e-104">[優先受信トレイ](../setup/configure-focused-inbox.md) が低優先メールに置き換わります。</span><span class="sxs-lookup"><span data-stu-id="1b98e-104">[Focused Inbox](../setup/configure-focused-inbox.md) is going to replace Clutter.</span></span> <span data-ttu-id="1b98e-105">詳細: [集中受信トレイの更新とクラッターのプラン](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span><span class="sxs-lookup"><span data-stu-id="1b98e-105">Learn more: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span></span>
  
<span data-ttu-id="1b98e-106">管理者は、ユーザーの管理でクラッター機能を管理するMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="1b98e-106">As an admin, you may have to manage the Clutter feature in Microsoft 365.</span></span> <span data-ttu-id="1b98e-107">組織内のユーザーに対してクラッター機能のオン/オフを切り替えするには、PowerShell でExchange必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b98e-107">To turn the Clutter feature on/off for users in your organization, you must use Exchange PowerShell.</span></span> <span data-ttu-id="1b98e-108">(個人は、次の手順を使用してオン/オフを切り替[Outlook。](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)</span><span class="sxs-lookup"><span data-stu-id="1b98e-108">(Individuals can turn it on/off using these instructions: [Turn off/on Clutter in Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c).</span></span>
  
<span data-ttu-id="1b98e-109">PowerShell[の使用](/powershell/exchange/exchange-online-powershell)の詳細については、「PowerShell と Exchange OnlineをConnectをExchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)を使用する」を参照Exchangeしてください。</span><span class="sxs-lookup"><span data-stu-id="1b98e-109">Check out [Using PowerShell with Exchange Online](/powershell/exchange/exchange-online-powershell) and [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) for details on using Exchange PowerShell.</span></span> <span data-ttu-id="1b98e-110">少なくともサービス管理者の役割と PowerShell Exchangeに接続できるアカウントExchange Online必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b98e-110">You need to have an account that has at least the Exchange Service administrator role and the ability to connect to Exchange Online with PowerShell.</span></span> 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a><span data-ttu-id="1b98e-111">Exchange PowerShell を使用して低優先メール機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="1b98e-111">Turn Clutter on using Exchange PowerShell</span></span>

<span data-ttu-id="1b98e-p104">[Set-Clutter](/powershell/module/exchange/set-clutter) コマンドレットを実行することで、メールボックスの低優先メールを手動で有効にできます。組織のメールボックスの低優先メール設定を表示することもできます。 [Get-Clutter](/powershell/module/exchange/get-clutter) コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="1b98e-p104">You can enable Clutter manually for a mailbox by running the [Set-Clutter](/powershell/module/exchange/set-clutter) cmdlet. You can also view Clutter settings for mailboxes in your organization by running the [Get-Clutter](/powershell/module/exchange/get-clutter) cmdlet.</span></span> 
  
<span data-ttu-id="1b98e-114">アリー ベリューという名前のユーザーの低優先メールをオンにする</span><span class="sxs-lookup"><span data-stu-id="1b98e-114">Turn on Clutter for a single user named Allie Bellew</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a><span data-ttu-id="1b98e-115">Exchange PowerShell を使用して低優先メールをオフにする</span><span class="sxs-lookup"><span data-stu-id="1b98e-115">Turn Clutter off using Exchange PowerShell</span></span>

<span data-ttu-id="1b98e-p105">[Set-Clutter](/powershell/module/exchange/set-clutter) コマンドレットを実行することで、メールボックスの低優先メールを手動で無効にできます。組織のメールボックスの **低優先メール** 設定を表示することもできます。[Get-Clutter](/powershell/module/exchange/get-clutter) コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="1b98e-p105">You can disable Clutter manually for a mailbox by running the [Set-Clutter](/powershell/module/exchange/set-clutter) cmdlet. You can also view **Clutter** settings for mailboxes in your organization by running the [Get-Clutter](/powershell/module/exchange/get-clutter) cmdlet.</span></span> 
  
<span data-ttu-id="1b98e-118">アリー ベリューという名前のユーザーの低優先メールをオフにする</span><span class="sxs-lookup"><span data-stu-id="1b98e-118">Turn off Clutter for a single user named Allie Bellew:</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

<span data-ttu-id="1b98e-119">PowerShell を使用してユーザーを一括作成する場合、各ユーザーのメールボックスに [Set-Clutter](/powershell/module/exchange/set-clutter) を実行し、低優先メールを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b98e-119">If you use PowerShell to bulk create your users, then you'll need to run [Set-Clutter](/powershell/module/exchange/set-clutter) against each user's mailbox to manage Clutter.</span></span> 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a><span data-ttu-id="1b98e-120">低優先メールのオン/オフ スイッチはどのような場合に、Outlook on the web のユーザーに表示されますか?</span><span class="sxs-lookup"><span data-stu-id="1b98e-120">When does the Clutter on/off switch appear to users in Outlook on the web?</span></span>
<span data-ttu-id="1b98e-121"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="1b98e-121"><a name="bkmk_onoff"> </a></span></span>

<span data-ttu-id="1b98e-122">管理者は、PowerShell を使用してクラッターをExchangeできます。</span><span class="sxs-lookup"><span data-stu-id="1b98e-122">As an admin, you can re-enable Clutter using Exchange PowerShell.</span></span> <span data-ttu-id="1b98e-123">この操作が行われると、優先受信トレイは無効になり、低優先メールが再び有効になります。</span><span class="sxs-lookup"><span data-stu-id="1b98e-123">Once this is done, Focused Inbox will be turned off and Clutter will be active again.</span></span> 
  
 <span data-ttu-id="1b98e-124">**サブスクリプションを使用して web Outlookを使用している場合はMicrosoft 365 Business Premiumします。**</span><span class="sxs-lookup"><span data-stu-id="1b98e-124">**If you're using Outlook on the web with a Microsoft 365 Business Premium subscription:**</span></span>
  
- <span data-ttu-id="1b98e-125">ユーザーの低優先メールが現在有効になっている場合:</span><span class="sxs-lookup"><span data-stu-id="1b98e-125">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="1b98e-126">低優先メールの設定は表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b98e-126">Clutter settings appear</span></span>
    
- <span data-ttu-id="1b98e-127">ユーザーの優先受信トレイが現在有効になっている場合:</span><span class="sxs-lookup"><span data-stu-id="1b98e-127">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="1b98e-128">低優先メールの設定は表示されません。</span><span class="sxs-lookup"><span data-stu-id="1b98e-128">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="1b98e-129">低優先メールも優先受信トレイも有効になっていない場合:</span><span class="sxs-lookup"><span data-stu-id="1b98e-129">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="1b98e-130">ユーザーの [メールの設定] にオプションとして低優先メールと優先受信トレイの両方が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b98e-130">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
 <span data-ttu-id="1b98e-131">**Outlook.com を使用している場合:**</span><span class="sxs-lookup"><span data-stu-id="1b98e-131">**If you're using Outlook.com:**</span></span>
  
- <span data-ttu-id="1b98e-132">ユーザーの低優先メールが現在有効になっている場合:</span><span class="sxs-lookup"><span data-stu-id="1b98e-132">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="1b98e-133">低優先メールの設定は表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b98e-133">Clutter settings appear</span></span>
    
- <span data-ttu-id="1b98e-134">ユーザーの優先受信トレイが現在有効になっている場合:</span><span class="sxs-lookup"><span data-stu-id="1b98e-134">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="1b98e-135">低優先メールの設定は表示されません。</span><span class="sxs-lookup"><span data-stu-id="1b98e-135">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="1b98e-136">低優先メールも優先受信トレイも有効になっていない場合:</span><span class="sxs-lookup"><span data-stu-id="1b98e-136">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="1b98e-137">ユーザーの [メールの設定] にオプションとして低優先メールと優先受信トレイの両方が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b98e-137">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
- <span data-ttu-id="1b98e-138">ユーザーが過去のある時点で優先受信トレイを有効にした場合:</span><span class="sxs-lookup"><span data-stu-id="1b98e-138">If user enabled Focused Inbox at some point in the past:</span></span>
    
  - <span data-ttu-id="1b98e-139">低優先メールの設定は表示されません。</span><span class="sxs-lookup"><span data-stu-id="1b98e-139">Clutter settings will never appear</span></span>
    
    <span data-ttu-id="1b98e-140">それ以外の場合:</span><span class="sxs-lookup"><span data-stu-id="1b98e-140">Otherwise,</span></span> 
    
  - <span data-ttu-id="1b98e-141">低優先メールの設定は表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b98e-141">Clutter settings will appear</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="1b98e-142">関連記事</span><span class="sxs-lookup"><span data-stu-id="1b98e-142">Related articles</span></span>
<span data-ttu-id="1b98e-143"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="1b98e-143"><a name="bkmk_onoff"> </a></span></span>

[<span data-ttu-id="1b98e-144">Outlook で低優先メール機能を使って優先度の低いメッセージを並べ替える</span><span class="sxs-lookup"><span data-stu-id="1b98e-144">Use Clutter to sort low priority messages in Outlook</span></span>](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0)
    
[<span data-ttu-id="1b98e-145">低優先度のメッセージを OWA で並べ替える場合は、クラッターを使用する</span><span class="sxs-lookup"><span data-stu-id="1b98e-145">Use Clutter to sort low priority messages in OWA</span></span>](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce)
    
[<span data-ttu-id="1b98e-146">Outlook の低優先メール機能をオフにする</span><span class="sxs-lookup"><span data-stu-id="1b98e-146">Turn off Clutter in Outlook</span></span>](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)
