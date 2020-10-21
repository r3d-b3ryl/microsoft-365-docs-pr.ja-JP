---
title: 優先度アカウントを管理および監視する
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
ms.custom: AdminSurgePortfolio
description: ビジネスへの影響が大きいアカウントによって送受信された、失敗した電子メールメッセージと遅延した電子メールメッセージを監視します。
ms.openlocfilehash: ce78316290f18f06337adc0e78a1b8992be7b425
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644593"
---
# <a name="manage-and-monitor-priority-accounts"></a><span data-ttu-id="c429a-103">優先度アカウントを管理および監視する</span><span class="sxs-lookup"><span data-stu-id="c429a-103">Manage and monitor priority accounts</span></span>

<span data-ttu-id="c429a-104">Microsoft 365 組織の管理者として、CEO のようなビジネスへの影響が大きいユーザーに送信された、失敗したまたは遅延した電子メールメッセージを監視できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c429a-104">As the admin of a Microsoft 365 organization, you can now monitor failed or delayed email messages sent to your users who have a high business impact, like your CEO.</span></span> <span data-ttu-id="c429a-105">この機能を有効にするには、優先度のアカウントの一覧にユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="c429a-105">You can enable this by adding users to your priority accounts list.</span></span> <span data-ttu-id="c429a-106">優先度のアカウントは、組織の実行に不可欠なアカウントです。</span><span class="sxs-lookup"><span data-stu-id="c429a-106">Priority accounts are accounts that are essential to running your organization.</span></span> <span data-ttu-id="c429a-107">経営幹部、リーダー、マネージャー、または機密または高優先度の情報にアクセスできる他のユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="c429a-107">Add executives, leaders, managers or other users who have access to sensitive or high priority information.</span></span>

## <a name="access-priority-accounts"></a><span data-ttu-id="c429a-108">アクセス優先度のアカウント</span><span class="sxs-lookup"><span data-stu-id="c429a-108">Access priority accounts</span></span>

<span data-ttu-id="c429a-109">このトピックに記載されている優先順位のアカウント機能は、次の両方の要件を満たす組織にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c429a-109">The priority accounts feature that's described in this topic is available only to organizations that meet both of the following requirements:</span></span>

- <span data-ttu-id="c429a-110">Office 365 E3 または Microsoft 365 E3、あるいは Office 365 E5 または Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="c429a-110">Office 365 E3 or Microsoft 365 E3, or Office 365 E5 or Microsoft 365 E5.</span></span>
- <span data-ttu-id="c429a-111">少なくとも1万のライセンスと、少なくとも50のアクティブな Exchange Online ユーザー。</span><span class="sxs-lookup"><span data-stu-id="c429a-111">At least 10,000 licenses and at least 50 monthly active Exchange Online users.</span></span>

## <a name="add-priority-accounts-from-the-setup-page"></a><span data-ttu-id="c429a-112">セットアップページから優先度アカウントを追加する</span><span class="sxs-lookup"><span data-stu-id="c429a-112">Add priority accounts from the Setup page</span></span>

<span data-ttu-id="c429a-113">[ **セットアップ] ページ**で、優先度の高いアカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="c429a-113">Add priority accounts from the **Setup page**.</span></span>

1. <span data-ttu-id="c429a-114">Microsoft 365 管理センター () に移動 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> します。</span><span class="sxs-lookup"><span data-stu-id="c429a-114">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="c429a-115">[**セットアップ**  >  **の組織ナレッジ**] に移動して、[**最も重要なアカウントを監視**する] の下にある [**表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c429a-115">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="c429a-116">[ **開始** ] または [ **管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c429a-116">Select **Get Started** or **Manage**.</span></span>

4. <span data-ttu-id="c429a-117">[ **優先度アカウントの追加** ] ページで、検索フィールドに、優先度アカウントリストに追加するユーザーの名前または電子メールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="c429a-117">On the **Add Priority accounts** page, in the search field, type the name or email address of the person you want to add to the priority accounts list.</span></span> <span data-ttu-id="c429a-118">また、失敗したメールまたは遅延したメールのメールのしきい値を設定して、優先度アカウントの問題の週単位のレポートを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="c429a-118">You can also set your email threshold for failed or delayed emails and get a weekly report of issues for priority accounts.</span></span>

5. <span data-ttu-id="c429a-119">ユーザーを選択して、[ **保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c429a-119">Select the user and choose **Save**.</span></span>

<span data-ttu-id="c429a-120">[アクティブなユーザー] ページから優先度の高いアカウントを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="c429a-120">You can also add priority accounts from the Active users page.</span></span>

### <a name="add-priority-accounts-from-active-users-page"></a><span data-ttu-id="c429a-121">[アクティブなユーザー] ページから優先度のアカウントを追加する</span><span class="sxs-lookup"><span data-stu-id="c429a-121">Add priority accounts from Active users page</span></span>

<span data-ttu-id="c429a-122">[アクティブなユーザー] ページから優先度の高いアカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="c429a-122">Add priority accounts from the Active users page.</span></span>

1. <span data-ttu-id="c429a-123"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> で管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="c429a-123">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="c429a-124">[**ユーザー**の  >  **アクティブなユーザー**] に移動し、ページの上部にある [.. **.** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c429a-124">Go to **Users** > **Active users**, and choose **...** at the top of the page.</span></span> <span data-ttu-id="c429a-125">[ **優先度アカウントの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c429a-125">Select **Manage priority accounts**.</span></span>

3. <span data-ttu-id="c429a-126">[ **アカウントの追加**] を選択し、[ **優先度アカウントの追加** ] ページの検索フィールドに、優先度のアカウント一覧に追加するユーザーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c429a-126">Select **Add accounts**, and on the **Add Priority accounts** page, in the search field, type the name of the person you want to add to the priority accounts list.</span></span>

4. <span data-ttu-id="c429a-127">ユーザーを選択して、[ **保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c429a-127">Select the user and choose **Save**.</span></span>

## <a name="monitor-your-priority-accounts"></a><span data-ttu-id="c429a-128">優先度の高いアカウントを監視する</span><span class="sxs-lookup"><span data-stu-id="c429a-128">Monitor your priority accounts</span></span>

<span data-ttu-id="c429a-129">[ **セットアップ** ] ページの Microsoft 365 管理センターで、優先度の高いアカウントの電子メールの状態を監視できます。</span><span class="sxs-lookup"><span data-stu-id="c429a-129">You can monitor the email status of your priority accounts in the Microsoft 365 admin center on the **Setup** page.</span></span> <span data-ttu-id="c429a-130">最大250のアカウントをアクティブに監視できます。</span><span class="sxs-lookup"><span data-stu-id="c429a-130">You can actively monitor up to 250 accounts.</span></span>

1. <span data-ttu-id="c429a-131"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> で管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="c429a-131">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="c429a-132">[**セットアップ**] を選択し、[**プレミアム監視**] の横にある [**表示**] を選択して、優先度アカウントの状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="c429a-132">Select **Setup** and choose **View** next to **Premium Monitoring** to see the status of your priority accounts.</span></span>

## <a name="email-issues-for-priority-accounts"></a><span data-ttu-id="c429a-133">優先度アカウントの電子メールの問題</span><span class="sxs-lookup"><span data-stu-id="c429a-133">Email issues for priority accounts</span></span>

<span data-ttu-id="c429a-134">優先度の高いアカウントの電子メールの問題を追跡するには、Exchange 管理センターで [ **優先度の高いアカウントの電子メールの問題点** レポートにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="c429a-134">You can track email issues for priority accounts by going to the the **Email issues for priority accounts** report in the Exchange admin center.</span></span> <span data-ttu-id="c429a-135">詳細については、「 [優先度のアカウントの電子メールの問題](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c429a-135">For more info, check out [Email issues for priority accounts](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report).</span></span>

## <a name="remove-a-user-from-the-priority-accounts-list"></a><span data-ttu-id="c429a-136">優先順位のアカウントリストからユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="c429a-136">Remove a user from the priority accounts list</span></span>

1. <span data-ttu-id="c429a-137">Microsoft 365 管理センター () に移動 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> します。</span><span class="sxs-lookup"><span data-stu-id="c429a-137">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="c429a-138">[**セットアップ**  >  **の組織ナレッジ**] に移動して、[**最も重要なアカウントを監視**する] の下にある [**表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c429a-138">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="c429a-139">[**大部分のアカウントの監視**] ページで、[**この機能の管理**] の [**優先度の高いアカウント**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c429a-139">On the **Monitor your most accounts** page, choose **Priority accounts** under **Manage this feature**.</span></span>

4. <span data-ttu-id="c429a-140">[ **優先度アカウント** ] ページで、リストから削除するユーザーを選択し、[ **アカウントの削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c429a-140">On the **Priority accounts** page, select the user or users you want to remove from the list and choose, **Remove accounts**.</span></span>