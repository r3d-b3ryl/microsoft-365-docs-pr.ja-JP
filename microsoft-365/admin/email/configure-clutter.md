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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: 'PowerShell を使用して、組織内のすべてのユーザーまたは特定のユーザーに対してクラッター機能を有効または無効Exchangeします。 '
ms.openlocfilehash: 91098047bdf2ab8190283990bdc6b0292e3e57ba
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393981"
---
# <a name="configure-clutter-for-your-organization"></a><span data-ttu-id="30e19-103">組織での低優先メールの構成</span><span class="sxs-lookup"><span data-stu-id="30e19-103">Configure Clutter for your organization</span></span>

> [!TIP]
> <span data-ttu-id="30e19-104">[優先受信トレイ](../setup/configure-focused-inbox.md) が低優先メールに置き換わります。</span><span class="sxs-lookup"><span data-stu-id="30e19-104">[Focused Inbox](../setup/configure-focused-inbox.md) is going to replace Clutter.</span></span> <span data-ttu-id="30e19-105">詳細: [集中受信トレイの更新とクラッターのプラン](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span><span class="sxs-lookup"><span data-stu-id="30e19-105">Learn more: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span></span>
  
<span data-ttu-id="30e19-106">管理者は、ユーザーの管理でクラッター機能を管理するMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="30e19-106">As an admin, you may have to manage the Clutter feature in Microsoft 365.</span></span> <span data-ttu-id="30e19-107">組織内のユーザーに対してクラッター機能のオン/オフを切り替えするには、PowerShell でExchange必要があります。</span><span class="sxs-lookup"><span data-stu-id="30e19-107">To turn the Clutter feature on/off for users in your organization, you must use Exchange PowerShell.</span></span> <span data-ttu-id="30e19-108">(個人は、次の手順を使用してオン/オフを切り替[Outlook。](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)</span><span class="sxs-lookup"><span data-stu-id="30e19-108">(Individuals can turn it on/off using these instructions: [Turn off/on Clutter in Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c).</span></span>
  
<span data-ttu-id="30e19-109">PowerShell[の使用](/powershell/exchange/exchange-online-powershell)の詳細については、「PowerShell と Exchange OnlineをConnectをExchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)を使用する」を参照Exchangeしてください。</span><span class="sxs-lookup"><span data-stu-id="30e19-109">Check out [Using PowerShell with Exchange Online](/powershell/exchange/exchange-online-powershell) and [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) for details on using Exchange PowerShell.</span></span> <span data-ttu-id="30e19-110">少なくともサービス管理者の役割と PowerShell Exchangeに接続できるアカウントExchange Online必要があります。</span><span class="sxs-lookup"><span data-stu-id="30e19-110">You need to have an account that has at least the Exchange Service administrator role and the ability to connect to Exchange Online with PowerShell.</span></span> 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a><span data-ttu-id="30e19-111">Exchange PowerShell を使用して低優先メール機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="30e19-111">Turn Clutter on using Exchange PowerShell</span></span>

<span data-ttu-id="30e19-p104">[Set-Clutter](/powershell/module/exchange/set-clutter) コマンドレットを実行することで、メールボックスの低優先メールを手動で有効にできます。組織のメールボックスの低優先メール設定を表示することもできます。 [Get-Clutter](/powershell/module/exchange/get-clutter) コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="30e19-p104">You can enable Clutter manually for a mailbox by running the [Set-Clutter](/powershell/module/exchange/set-clutter) cmdlet. You can also view Clutter settings for mailboxes in your organization by running the [Get-Clutter](/powershell/module/exchange/get-clutter) cmdlet.</span></span> 
  
<span data-ttu-id="30e19-114">アリー ベリューという名前のユーザーの低優先メールをオンにする</span><span class="sxs-lookup"><span data-stu-id="30e19-114">Turn on Clutter for a single user named Allie Bellew</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a><span data-ttu-id="30e19-115">Exchange PowerShell を使用して低優先メールをオフにする</span><span class="sxs-lookup"><span data-stu-id="30e19-115">Turn Clutter off using Exchange PowerShell</span></span>

<span data-ttu-id="30e19-p105">[Set-Clutter](/powershell/module/exchange/set-clutter) コマンドレットを実行することで、メールボックスの低優先メールを手動で無効にできます。組織のメールボックスの **低優先メール** 設定を表示することもできます。[Get-Clutter](/powershell/module/exchange/get-clutter) コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="30e19-p105">You can disable Clutter manually for a mailbox by running the [Set-Clutter](/powershell/module/exchange/set-clutter) cmdlet. You can also view **Clutter** settings for mailboxes in your organization by running the [Get-Clutter](/powershell/module/exchange/get-clutter) cmdlet.</span></span> 
  
<span data-ttu-id="30e19-118">アリー ベリューという名前のユーザーの低優先メールをオフにする</span><span class="sxs-lookup"><span data-stu-id="30e19-118">Turn off Clutter for a single user named Allie Bellew:</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

<span data-ttu-id="30e19-119">PowerShell を使用してユーザーを一括作成する場合、各ユーザーのメールボックスに [Set-Clutter](/powershell/module/exchange/set-clutter) を実行し、低優先メールを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="30e19-119">If you use PowerShell to bulk create your users, then you'll need to run [Set-Clutter](/powershell/module/exchange/set-clutter) against each user's mailbox to manage Clutter.</span></span> 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a><span data-ttu-id="30e19-120">低優先メールのオン/オフ スイッチはどのような場合に、Outlook on the web のユーザーに表示されますか?</span><span class="sxs-lookup"><span data-stu-id="30e19-120">When does the Clutter on/off switch appear to users in Outlook on the web?</span></span>
<span data-ttu-id="30e19-121"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="30e19-121"><a name="bkmk_onoff"> </a></span></span>

<span data-ttu-id="30e19-122">管理者は、PowerShell を使用してクラッターをExchangeできます。</span><span class="sxs-lookup"><span data-stu-id="30e19-122">As an admin, you can re-enable Clutter using Exchange PowerShell.</span></span> <span data-ttu-id="30e19-123">この操作が行われると、優先受信トレイは無効になり、低優先メールが再び有効になります。</span><span class="sxs-lookup"><span data-stu-id="30e19-123">Once this is done, Focused Inbox will be turned off and Clutter will be active again.</span></span> 
  
 <span data-ttu-id="30e19-124">**サブスクリプションと一緒にOutlook on the webする場合Microsoft 365 Business Premium:**</span><span class="sxs-lookup"><span data-stu-id="30e19-124">**If you're using Outlook on the web with a Microsoft 365 Business Premium subscription:**</span></span>
  
- <span data-ttu-id="30e19-125">ユーザーの低優先メールが現在有効になっている場合:</span><span class="sxs-lookup"><span data-stu-id="30e19-125">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="30e19-126">低優先メールの設定は表示されます。</span><span class="sxs-lookup"><span data-stu-id="30e19-126">Clutter settings appear</span></span>
    
- <span data-ttu-id="30e19-127">ユーザーの優先受信トレイが現在有効になっている場合:</span><span class="sxs-lookup"><span data-stu-id="30e19-127">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="30e19-128">低優先メールの設定は表示されません。</span><span class="sxs-lookup"><span data-stu-id="30e19-128">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="30e19-129">低優先メールも優先受信トレイも有効になっていない場合:</span><span class="sxs-lookup"><span data-stu-id="30e19-129">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="30e19-130">ユーザーの [メールの設定] にオプションとして低優先メールと優先受信トレイの両方が表示されます。</span><span class="sxs-lookup"><span data-stu-id="30e19-130">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
 <span data-ttu-id="30e19-131">**Outlook.com を使用している場合:**</span><span class="sxs-lookup"><span data-stu-id="30e19-131">**If you're using Outlook.com:**</span></span>
  
- <span data-ttu-id="30e19-132">ユーザーの低優先メールが現在有効になっている場合:</span><span class="sxs-lookup"><span data-stu-id="30e19-132">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="30e19-133">低優先メールの設定は表示されます。</span><span class="sxs-lookup"><span data-stu-id="30e19-133">Clutter settings appear</span></span>
    
- <span data-ttu-id="30e19-134">ユーザーの優先受信トレイが現在有効になっている場合:</span><span class="sxs-lookup"><span data-stu-id="30e19-134">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="30e19-135">低優先メールの設定は表示されません。</span><span class="sxs-lookup"><span data-stu-id="30e19-135">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="30e19-136">低優先メールも優先受信トレイも有効になっていない場合:</span><span class="sxs-lookup"><span data-stu-id="30e19-136">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="30e19-137">ユーザーの [メールの設定] にオプションとして低優先メールと優先受信トレイの両方が表示されます。</span><span class="sxs-lookup"><span data-stu-id="30e19-137">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
- <span data-ttu-id="30e19-138">ユーザーが過去のある時点で優先受信トレイを有効にした場合:</span><span class="sxs-lookup"><span data-stu-id="30e19-138">If user enabled Focused Inbox at some point in the past:</span></span>
    
  - <span data-ttu-id="30e19-139">低優先メールの設定は表示されません。</span><span class="sxs-lookup"><span data-stu-id="30e19-139">Clutter settings will never appear</span></span>
    
    <span data-ttu-id="30e19-140">それ以外の場合:</span><span class="sxs-lookup"><span data-stu-id="30e19-140">Otherwise,</span></span> 
    
  - <span data-ttu-id="30e19-141">低優先メールの設定は表示されます。</span><span class="sxs-lookup"><span data-stu-id="30e19-141">Clutter settings will appear</span></span>
    
## <a name="related-content"></a><span data-ttu-id="30e19-142">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="30e19-142">Related content</span></span>

<span data-ttu-id="30e19-143">[低優先度のメッセージを並べ替える場合は、クラッターを使用Outlook](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0) (記事)</span><span class="sxs-lookup"><span data-stu-id="30e19-143">[Use Clutter to sort low priority messages in Outlook](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0) (article)</span></span>\
<span data-ttu-id="30e19-144">[低優先度のメッセージを OWA で並べ替える](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce) 場合は、クラッターを使用します (記事)</span><span class="sxs-lookup"><span data-stu-id="30e19-144">[Use Clutter to sort low priority messages in OWA](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce) (article)</span></span>\
<span data-ttu-id="30e19-145">[[クラッター] をOutlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)する (記事)</span><span class="sxs-lookup"><span data-stu-id="30e19-145">[Turn off Clutter in Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c) (article)</span></span>
