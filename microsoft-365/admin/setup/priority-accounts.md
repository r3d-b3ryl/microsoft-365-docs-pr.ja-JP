---
title: 優先度アカウントの管理と監視
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
description: ビジネスに大きな影響を与えるアカウントとの間で送信された電子メール メッセージと遅延したメッセージを監視します。
ms.openlocfilehash: dbdd692a41d341564376960788054e70623daf5a
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233364"
---
# <a name="manage-and-monitor-priority-accounts"></a><span data-ttu-id="736d9-103">優先度アカウントの管理と監視</span><span class="sxs-lookup"><span data-stu-id="736d9-103">Manage and monitor priority accounts</span></span>

<span data-ttu-id="736d9-104">すべての Microsoft 365 組織には、役員、リーダー、マネージャー、機密性の高い、独自の情報、または優先度の高い情報にアクセスできるその他のユーザーなど、重要なユーザーがいます。</span><span class="sxs-lookup"><span data-stu-id="736d9-104">In every Microsoft 365 organization, there are people that are essential, like executives, leaders, managers, or other users who have access to sensitive, proprietary, or high priority information.</span></span>

<span data-ttu-id="736d9-105">組織でこれらのアカウントを保護するために、特定のユーザーを優先度アカウントとして指定し、追加の保護を提供するアプリ固有の機能を活用できます。</span><span class="sxs-lookup"><span data-stu-id="736d9-105">To help your organization protect these accounts, you can now designate specific users as priority accounts and leverage app-specific features that provide them with extra protection.</span></span> <span data-ttu-id="736d9-106">今後、より多くのアプリと機能が優先度アカウントをサポートし、最初に、優先度アカウント保護とプレミアム メールフロー監視の 2 つの機能を **発表しました**。</span><span class="sxs-lookup"><span data-stu-id="736d9-106">In the future, more apps and features will support priority accounts, and to start with, we’ve announced two capabilities: **priority account protection** and **premium mail flow monitoring**.</span></span>

- <span data-ttu-id="736d9-107">**優先度アカウント** 保護 - microsoft Defender for Office 365 (以前の Office 365 Advanced Threat Protection) は、アラート、レポート、調査のフィルターで使用できるタグとして優先度アカウントをサポートします。</span><span class="sxs-lookup"><span data-stu-id="736d9-107">**Priority account protection** - Microsoft Defender for Office 365 (formerly Office 365 Advanced Threat Protection) supports priority accounts as tags that can be used in filters in alerts, reports, and investigations.</span></span> <span data-ttu-id="736d9-108">詳細については [、Microsoft Defender の User タグで 365 Office確認](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags)してください。</span><span class="sxs-lookup"><span data-stu-id="736d9-108">For more information, check out [User tags in Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags).</span></span>
- <span data-ttu-id="736d9-109">**プレミアム メール フロー監視** - 正常なメール フローはビジネスの成功に不可欠であり、配信の遅延や失敗はビジネスに悪影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="736d9-109">**Premium Mail Flow Monitoring** - Healthy mail flow can be critical to business success, and delivery delays or failures can have a negative impact on the business.</span></span> <span data-ttu-id="736d9-110">失敗または遅延したメールのしきい値を選択し、そのしきい値を超えた場合にアラートを受信し、優先度アカウントのメールの問題のレポートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="736d9-110">You can choose a threshold for failed or delayed emails, receive alerts when that threshold is exceeded, and view a report of email issues for priority accounts.</span></span> <span data-ttu-id="736d9-111">詳細については、最新の [EAC で優先度アカウント レポートのメールの問題を確認してください。](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</span><span class="sxs-lookup"><span data-stu-id="736d9-111">For more information, check out [Email issues for priority accounts report in the modern EAC](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</span></span>

<span data-ttu-id="736d9-112">優先度アカウントのセキュリティのベスト プラクティスについては、「優先度アカウントの [セキュリティに関する推奨事項」を参照してください](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-recommendations-for-priority-accounts)。</span><span class="sxs-lookup"><span data-stu-id="736d9-112">For security best practices for priority accounts, see [Security recommendations for priority accounts](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-recommendations-for-priority-accounts).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="736d9-113">はじめに</span><span class="sxs-lookup"><span data-stu-id="736d9-113">Before you begin</span></span>

<span data-ttu-id="736d9-114">この **トピックで説明する** 優先度アカウント保護機能は、次の要件を満たす組織でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="736d9-114">The **Priority account protection** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="736d9-115">Office 365 E3、Office 365 E5、Microsoft 365 E5、または Microsoft 365 E5 Security を含む Office 365 プラン 2 用の Microsoft Defender。</span><span class="sxs-lookup"><span data-stu-id="736d9-115">Microsoft Defender for Office 365 Plan 2, including those with Office 365 E3, Office 365 E5, Microsoft 365 E5, or Microsoft 365 E5 Security.</span></span>

<span data-ttu-id="736d9-116">この **トピックで説明する** プレミアム メール フロー監視機能は、次の要件を満たす組織でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="736d9-116">The **Premium Mail Flow Monitoring** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="736d9-117">組織のライセンス数が 10,000 以上である必要があります。ライセンス数は、Office 365 E3、Microsoft 365 E3、Office 365 E5、Microsoft 365 E5 のいずれか、または組み合わせのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="736d9-117">Your organization needs to have a license count of at least 10,000, from either one of, or a combination of the following products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> <span data-ttu-id="736d9-118">たとえば、対象となる製品から合計 11,500 ライセンスの場合、組織は 3000 Office 365 E3 ライセンスと 8500 Microsoft 365 E5 を持ちます。</span><span class="sxs-lookup"><span data-stu-id="736d9-118">For example, your organization can have 3000 Office 365 E3 licenses and 8500 Microsoft 365 E5, for a total of 11,500 licenses from the qualifying products.</span></span>
- <span data-ttu-id="736d9-119">組織に月間 50 人以上のアクティブな Exchange Online ユーザーが必要です。</span><span class="sxs-lookup"><span data-stu-id="736d9-119">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

> [!NOTE]
> <span data-ttu-id="736d9-120">最大 250 の優先度アカウントを監視できます。</span><span class="sxs-lookup"><span data-stu-id="736d9-120">You can monitor up to 250 priority accounts.</span></span>

### <a name="add-priority-accounts-from-the-setup-page"></a><span data-ttu-id="736d9-121">[セットアップ] ページから優先度アカウントを追加する</span><span class="sxs-lookup"><span data-stu-id="736d9-121">Add priority accounts from the Setup page</span></span>

<span data-ttu-id="736d9-122">[セットアップ] ページから優先度アカウント **を追加します**。</span><span class="sxs-lookup"><span data-stu-id="736d9-122">Add priority accounts from the **Setup page**.</span></span>

1. <span data-ttu-id="736d9-123">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="736d9-123">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="736d9-124">[組織の知識  >  **のセットアップ]** に移動し、[最も重要なアカウントの監視] で [**表示] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="736d9-124">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="736d9-125">[開始 **] または [管理]** を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="736d9-125">Select **Get Started** or **Manage**.</span></span>

4. <span data-ttu-id="736d9-126">[優先度 **アカウントの追加** ] ページの検索フィールドに、優先度アカウントリストに追加するユーザーの名前または電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="736d9-126">On the **Add Priority accounts** page, in the search field, type the name or email address of the person you want to add to the priority accounts list.</span></span> <span data-ttu-id="736d9-127">メールの失敗または遅延に関するしきい値を設定し、優先度アカウントの問題に関する週単位のレポートを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="736d9-127">You can also set your email threshold for failed or delayed emails and get a weekly report of issues for priority accounts.</span></span>

5. <span data-ttu-id="736d9-128">ユーザーを選択し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="736d9-128">Select the user and choose **Save**.</span></span>

<span data-ttu-id="736d9-129">[アクティブなユーザー] ページから優先度アカウントを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="736d9-129">You can also add priority accounts from the Active users page.</span></span>

### <a name="add-priority-accounts-from-active-users-page"></a><span data-ttu-id="736d9-130">[アクティブ なユーザー] ページから優先度アカウントを追加する</span><span class="sxs-lookup"><span data-stu-id="736d9-130">Add priority accounts from Active users page</span></span>

<span data-ttu-id="736d9-131">[アクティブなユーザー] ページから優先度アカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="736d9-131">Add priority accounts from the Active users page.</span></span>

1. <span data-ttu-id="736d9-132"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> で管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="736d9-132">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="736d9-133">[アクティブ **なユーザー**  >  **] に移動し**、ページの上部にある **[...]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="736d9-133">Go to **Users** > **Active users** and choose **...** at the top of the page.</span></span> <span data-ttu-id="736d9-134">[優先度アカウント **の管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="736d9-134">Select **Manage priority accounts**.</span></span>

3. <span data-ttu-id="736d9-135">[**アカウントの追加**] を選択し、[優先度アカウントの追加] ページの検索フィールドに、優先度アカウントの一覧に追加するユーザーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="736d9-135">Select **Add accounts**, and on the **Add Priority accounts** page, in the search field, type the name of the person you want to add to the priority accounts list.</span></span>

4. <span data-ttu-id="736d9-136">ユーザーを選択し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="736d9-136">Select the user and choose **Save**.</span></span>

## <a name="remove-a-user-from-the-priority-accounts-list"></a><span data-ttu-id="736d9-137">優先度アカウントの一覧からユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="736d9-137">Remove a user from the priority accounts list</span></span>

1. <span data-ttu-id="736d9-138">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="736d9-138">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="736d9-139">[組織の知識  >  **のセットアップ]** に移動し、[最も重要なアカウントの監視] で [**表示] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="736d9-139">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="736d9-140">On the **Monitor your most accounts** page, choose Priority **accounts** under Manage **this feature**.</span><span class="sxs-lookup"><span data-stu-id="736d9-140">On the **Monitor your most accounts** page, choose **Priority accounts** under **Manage this feature**.</span></span>

4. <span data-ttu-id="736d9-141">[優先度 **アカウント] ページ** で、一覧から削除するユーザーを選択し、[アカウントの削除] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="736d9-141">On the **Priority accounts** page, select the user or users you want to remove from the list and choose, **Remove accounts**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="736d9-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="736d9-142">Related topics</span></span>

[<span data-ttu-id="736d9-143">Microsoft 365 での優先度アカウントの使用</span><span class="sxs-lookup"><span data-stu-id="736d9-143">Using Priority Accounts in Microsoft 365</span></span>](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)