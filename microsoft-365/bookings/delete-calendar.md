---
title: 予約カレンダーを削除する
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 8c3a913c-2247-4519-894d-b6263eeb9920
description: 管理センターまたはMicrosoft 365を使用して、Windows PowerShellカレンダーを削除します。
ms.openlocfilehash: 21fc7b9994ffd7f76ed04000a50bd0ee8f7f167e
ms.sourcegitcommit: 8998f70d3f7bd673f93f8d1cf12ce981b1b771c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51034093"
---
# <a name="delete-a-booking-calendar-in-bookings"></a><span data-ttu-id="c80dd-103">Bookings で予約カレンダーを削除する</span><span class="sxs-lookup"><span data-stu-id="c80dd-103">Delete a booking calendar in Bookings</span></span>

<span data-ttu-id="c80dd-104">この記事では、不要な予約カレンダーを削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c80dd-104">This article explains how you can delete an unwanted booking calendar.</span></span> <span data-ttu-id="c80dd-105">予約カレンダーは、管理センターのMicrosoft 365削除するか、PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c80dd-105">You can delete the booking calendar in the Microsoft 365 admin center or you can use PowerShell.</span></span> <span data-ttu-id="c80dd-106">Bookings 予定表は、予約Exchange Online削除するために、対応するユーザー アカウントを削除するメールボックスです。</span><span class="sxs-lookup"><span data-stu-id="c80dd-106">The Bookings calendar is a mailbox in Exchange Online so you delete the corresponding user account to delete the booking calendar.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c80dd-107">2017 以前に作成した予約カレンダーはすべて、このトピックの PowerShell の手順を使用して削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c80dd-107">All booking calendars that you created in 2017 or before must be deleted using the PowerShell instructions on this topic.</span></span> <span data-ttu-id="c80dd-108">2018 以降で作成された予約カレンダーはすべて、管理センター Microsoft 365できます。</span><span class="sxs-lookup"><span data-stu-id="c80dd-108">All booking calendars created in 2018 or after can be deleted in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="c80dd-109">予約カレンダーには、その予約カレンダーとデータに関するすべての関連情報が保存されます。以下を含む。</span><span class="sxs-lookup"><span data-stu-id="c80dd-109">The booking calendar is where all relevant information about that booking calendar and data are stored, including:</span></span>

- <span data-ttu-id="c80dd-110">予約カレンダーの作成時に追加されたビジネス情報、ロゴ、および勤務時間</span><span class="sxs-lookup"><span data-stu-id="c80dd-110">Business information, logo, and working hours added when the booking calendar was created</span></span>
- <span data-ttu-id="c80dd-111">予約カレンダーの作成時に追加された関連するスタッフとサービス</span><span class="sxs-lookup"><span data-stu-id="c80dd-111">Relevant staff and services added when the booking calendar was created</span></span>
- <span data-ttu-id="c80dd-112">作成後に予約カレンダーに追加されたすべての予約と休み予定。</span><span class="sxs-lookup"><span data-stu-id="c80dd-112">All bookings and time off appointments added to the booking calendar once it was created.</span></span>

> [!WARNING]
> <span data-ttu-id="c80dd-113">予約カレンダーが削除された後、この追加情報も完全に削除され、回復できません。</span><span class="sxs-lookup"><span data-stu-id="c80dd-113">Once a booking calendar is deleted, this additional information is also permanently deleted and can't be recovered.</span></span>

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a><span data-ttu-id="c80dd-114">管理センターで予約カレンダーをMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="c80dd-114">Delete a booking calendar in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="c80dd-115">Microsoft 365 管理センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="c80dd-115">Go to the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="c80dd-116">管理センターで、[ **ユーザー** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c80dd-116">In the Admin center, select **Users**.</span></span>

   ![管理センターのユーザー UI Microsoft 365イメージ](../media/bookings-admin-center-users.png)

1. <span data-ttu-id="c80dd-118">[ **アクティブ ユーザー**] ページで、削除するユーザー名を選択して、[ **ユーザーの削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c80dd-118">On the **Active Users** page, choose the names of the users that you want to delete, and then select **Delete user**.</span></span>

   ![管理センターでのユーザー UI のMicrosoft 365イメージ](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a><span data-ttu-id="c80dd-120">PowerShell を使用して予約カレンダー Exchange Onlineする</span><span class="sxs-lookup"><span data-stu-id="c80dd-120">Delete a booking calendar using Exchange Online PowerShell</span></span>

<span data-ttu-id="c80dd-121">PowerShell Connect接続Exchange Onlineの前提条件とガイダンスについては[、「PowerShell](/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps)を使用する方法Exchange Online参照してください。</span><span class="sxs-lookup"><span data-stu-id="c80dd-121">See [Connect to Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) for prerequisites and guidance for connecting to Exchange Online PowerShell.</span></span>

<span data-ttu-id="c80dd-122">これらの手順を実行するには、[管理者として実行] オプションを選択して実行したアクティブな Microsoft PowerShell コマンド ウィンドウを使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="c80dd-122">To perform these steps, you must be using an active Microsoft PowerShell command window that you ran by choosing the “Run as administrator” option.</span></span>

1. <span data-ttu-id="c80dd-123">PowerShell ウィンドウで、次のコマンドを実行して EXO V2 モジュールを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="c80dd-123">In a PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

   > [!NOTE]
   > <span data-ttu-id="c80dd-124">すでに、[EXO V2 モジュールをインストール](/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exo-v2-module)している場合は、前のコマンドは表示のとおり機能します。</span><span class="sxs-lookup"><span data-stu-id="c80dd-124">If you've already [installed the EXO V2 module](/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exo-v2-module), the previous command will work as written.</span></span>
   
2. <span data-ttu-id="c80dd-125">実行する必要があるコマンドでは、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c80dd-125">The command that you need to run uses the following syntax:</span></span>

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName <UPN> 
   ```

   - <span data-ttu-id="c80dd-126">_\<UPN\>_ は、ユーザー プリンシパル名の形式 (`john@contoso.com`など) のアカウントです。</span><span class="sxs-lookup"><span data-stu-id="c80dd-126">_\<UPN\>_ is your account in user principal name format (for example, `john@contoso.com`).</span></span>

3. <span data-ttu-id="c80dd-127">メッセージが表示されたら、完全に削除する予約カレンダーをホストする Microsoft 365 テナントにテナント管理者の資格情報でログオンします。</span><span class="sxs-lookup"><span data-stu-id="c80dd-127">When you are prompted, log on with tenant administrator credentials to the Microsoft 365 tenant that hosts the booking calendar you want to permanently delete.</span></span>

4. <span data-ttu-id="c80dd-128">このコマンドの処理が終わったら、次のコマンドを入力して、テナントの予約メールボックスの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="c80dd-128">Once this command is done processing, enter the following command to get a list of the booking mailboxes in your tenant:</span></span>

   ```powershell
   Get-EXOMailbox -RecipientTypeDetails SchedulingMailbox
   ```

5. <span data-ttu-id="c80dd-129">次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="c80dd-129">Type the following command:</span></span>

   ```powershell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > <span data-ttu-id="c80dd-130">完全に削除する予約メールボックス エイリアスの正確な名前を入力してください。</span><span class="sxs-lookup"><span data-stu-id="c80dd-130">Be careful to type the exact name of the booking mailbox alias that you want to permanently delete.</span></span>

6. <span data-ttu-id="c80dd-131">予定表が削除されたと確認するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="c80dd-131">To verify that the calendar has been deleted, enter the following command:</span></span>

   ```powershell
    Get-EXOMailbox -RecipientTypeDetails SchedulingMailbox
   ```

   <span data-ttu-id="c80dd-132">削除された予定表は出力に表示されません。</span><span class="sxs-lookup"><span data-stu-id="c80dd-132">The deleted calendar will not appear in the output.</span></span>
