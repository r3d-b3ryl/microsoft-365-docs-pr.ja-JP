---
title: 手順 1 - 従業員がユーザーにログインMicrosoft 365
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
description: 元従業員のログインをブロックし、サービスへのアクセスMicrosoft 365します。
ms.openlocfilehash: 58b65a0a886460e8be01635c857433773cfc9059
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177119"
---
# <a name="step-1---prevent-a-former-employee-from-logging-in-and-block-access-to-microsoft-365-services"></a><span data-ttu-id="6bbd6-103">手順 1 - 元従業員のログインを防止し、サービスへのアクセスMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="6bbd6-103">Step 1 - Prevent a former employee from logging in and block access to Microsoft 365 services</span></span>

<span data-ttu-id="6bbd6-104">ユーザーのサインイン アクセスを直ちに防止する必要がある場合は、パスワードをリセットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6bbd6-104">If you need to immediately prevent a user's sign-in access, you should reset their password.</span></span> <span data-ttu-id="6bbd6-105">この手順では、ユーザーから強制的にサインアウトMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="6bbd6-105">In this step, force a sign out of the user from Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="6bbd6-106">他の管理者のサインアウトを開始するには、グローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6bbd6-106">You need to be a global administrator to initiate sign-out for other administrators.</span></span> <span data-ttu-id="6bbd6-107">管理者以外のユーザーの場合は、ユーザー管理者またはヘルプデスク管理者ユーザーを使用してこのアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="6bbd6-107">For non administrator users, you can use a User Administrator or a Helpdesk Administrator user to perform this action.</span></span> [<span data-ttu-id="6bbd6-108">管理者ロールの詳細</span><span class="sxs-lookup"><span data-stu-id="6bbd6-108">Learn more about the Admin Roles</span></span>](about-admin-roles.md)

1. <span data-ttu-id="6bbd6-109">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="6bbd6-109">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="6bbd6-110">ユーザーの名前の横にあるボックスを選択し、[パスワードのリセット] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="6bbd6-110">Select the box next to the user's name, and then select **Reset password**.</span></span>
3. <span data-ttu-id="6bbd6-111">新しいパスワードを入力し、[リセット] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="6bbd6-111">Enter a new password, and then select **Reset**.</span></span> <span data-ttu-id="6bbd6-112">(送信しない。</span><span class="sxs-lookup"><span data-stu-id="6bbd6-112">(Don't send it to them.)</span></span>
4. <span data-ttu-id="6bbd6-113">ユーザーの名前を選択してプロパティ ウィンドウに移動し、[アカウント]タブで [すべてのセッションからサインアウト]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="6bbd6-113">Select the user's name to go to their properties pane, and on the **Account** tab, select **Sign out of all sessions**.</span></span>

<span data-ttu-id="6bbd6-114">1 時間以内に、または現在のページを離Microsoft 365後に、もう一度サインインするように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6bbd6-114">Within an hour - or after they leave the current Microsoft 365 page they are on - they're prompted to sign in again.</span></span> <span data-ttu-id="6bbd6-115">アクセス トークンは 1 時間有効なので、タイムラインは、そのトークンに残されている時間と、現在の Web ページから移動するかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="6bbd6-115">An access token is good for an hour, so the timeline depends on how much time is left on that token, and whether they navigate out of their current webpage.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6bbd6-116">ユーザーがメールボックス内Outlook on the webクリックした場合、すぐには追い出されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6bbd6-116">If the user is in Outlook on the web, just clicking around in their mailbox, they may not be kicked out immediately.</span></span> <span data-ttu-id="6bbd6-117">ユーザーが別のタイル (OneDriveを選択したり、ブラウザーを更新したりすると、すぐにサインアウトが開始されます。</span><span class="sxs-lookup"><span data-stu-id="6bbd6-117">As soon as they select a different tile, such as OneDrive, or refresh their browser, the sign-out is initiated.</span></span>
  
<span data-ttu-id="6bbd6-118">PowerShell を使用してユーザーをすぐにサインアウトするには [、Revoke-AzureADUserAllRefreshToken コマンドレットを参照](/powershell/module/azuread/revoke-azureaduserallrefreshtoken) してください。</span><span class="sxs-lookup"><span data-stu-id="6bbd6-118">To use PowerShell to sign out a user immediately, see the [Revoke-AzureADUserAllRefreshToken](/powershell/module/azuread/revoke-azureaduserallrefreshtoken) cmdlet.</span></span>
  
<span data-ttu-id="6bbd6-119">ユーザーのメールの使用を終了するのにどれくらいかかるかの詳細については、「[従業員のメール セッションの終了について知っておく必要があること](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6bbd6-119">For more information about how long it takes to get someone out of email, see [What you need to know about terminating an employee's email session](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session).</span></span>

## <a name="block-a-former-employees-access-to-microsoft-365-services"></a><span data-ttu-id="6bbd6-120">元従業員のサービスへのアクセスをMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="6bbd6-120">Block a former employee's access to Microsoft 365 services</span></span>

> [!IMPORTANT]
 > <span data-ttu-id="6bbd6-121">アカウントをブロックすると、有効に 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6bbd6-121">Blocking an account can take up to 24 hours to take effect.</span></span> <span data-ttu-id="6bbd6-122">ユーザーのサインイン アクセスを直ちに防止する必要がある場合は、上記の手順に従ってパスワードをリセットします。</span><span class="sxs-lookup"><span data-stu-id="6bbd6-122">If you need to immediately prevent a user's sign-in access, follow the steps above and reset their password.</span></span>

1. <span data-ttu-id="6bbd6-123">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="6bbd6-123">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="6bbd6-124">ブロックする従業員の名前を選択し、ユーザーの名前の下にある [このユーザーをブロックする] の記号 **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="6bbd6-124">Select the name of the employee that you want to block, and under the user's name, select the symbol for **Block this user**.</span></span>
3. <span data-ttu-id="6bbd6-125">[ **ユーザーのサインインをブロックする**] を選択し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="6bbd6-125">Select **Block the user from signing in**, and then select **Save**.</span></span>

## <a name="block-a-former-employees-access-to-email-exchange-online"></a><span data-ttu-id="6bbd6-126">元従業員の電子メール (Exchange Online) へのアクセスをブロックする</span><span class="sxs-lookup"><span data-stu-id="6bbd6-126">Block a former employee's access to email (Exchange Online)</span></span>

<span data-ttu-id="6bbd6-127">Microsoft 365 サブスクリプションの一部としてメールがある場合は、Exchange 管理センターにサインインし、次の手順に従って、元従業員のメールへのアクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="6bbd6-127">If you have email as part of your Microsoft 365 subscription, sign in to the Exchange admin center and follow these steps to block your former employee from accessing their email.</span></span>
  
1. <span data-ttu-id="6bbd6-128"><a href="https://admin.exchange.microsoft.com/" target="_blank">Exchange 管理センター</a>に移動します。</span><span class="sxs-lookup"><span data-stu-id="6bbd6-128">Go to the <a href="https://admin.exchange.microsoft.com/" target="_blank">Exchange admin center</a>.</span></span>
2. <span data-ttu-id="6bbd6-129">In the Exchange admin center, navigate to **Recipients** \> **Mailboxes**.</span><span class="sxs-lookup"><span data-stu-id="6bbd6-129">In the Exchange admin center, navigate to **Recipients** \> **Mailboxes**.</span></span>
3. <span data-ttu-id="6bbd6-130">ユーザーをダブルクリックし、[メール アプリ] の [メール アプリ **の設定の管理** ] **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="6bbd6-130">Double-click the user and go to **Manage email apps settings** under **Email apps**.</span></span> <span data-ttu-id="6bbd6-131">すべての **オプション** のスライダーをオフにします。**モバイル (Exchange ActiveSync)** **、Outlook on the web**、Outlook **デスクトップ (MAPI)** **、Exchange Web** サービス **、POP3、\*\*\*\*および IMAP** です。</span><span class="sxs-lookup"><span data-stu-id="6bbd6-131">Turn **Off** the slider for all the options; **Mobile (Exchange ActiveSync)**, **Outlook on the web**, **Outlook desktop (MAPI)**, **Exchange web services**, **POP3**, and **IMAP**.</span></span>
4. <span data-ttu-id="6bbd6-132">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6bbd6-132">Select **Save**.</span></span>
