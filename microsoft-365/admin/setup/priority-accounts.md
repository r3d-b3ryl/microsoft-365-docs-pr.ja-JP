---
title: 優先アカウントを管理および監視する
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
description: ビジネスに大きな影響を与えるアカウントとの間で送信される、失敗したメールメッセージと遅延メール メッセージを監視します。
ms.openlocfilehash: f67b9c6f0eaa229b650026670cf1b2adf88ab3c0
ms.sourcegitcommit: 58fbcfd6437bfb08966b79954ca09556e636ff4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2021
ms.locfileid: "51632182"
---
# <a name="manage-and-monitor-priority-accounts"></a><span data-ttu-id="b8b50-103">優先アカウントを管理および監視する</span><span class="sxs-lookup"><span data-stu-id="b8b50-103">Manage and monitor priority accounts</span></span>

<span data-ttu-id="b8b50-104">すべての Microsoft 365 組織には、機密情報、専有情報、または優先度の高い情報にアクセスできるエグゼクティブ、リーダー、マネージャー、その他のユーザーなど、不可欠なユーザーがいます。</span><span class="sxs-lookup"><span data-stu-id="b8b50-104">In every Microsoft 365 organization, there are people that are essential, like executives, leaders, managers, or other users who have access to sensitive, proprietary, or high priority information.</span></span>

<span data-ttu-id="b8b50-105">組織がこれらのアカウントを保護するために、特定のユーザーを優先度アカウントとして指定し、追加の保護を提供するアプリ固有の機能を活用できます。</span><span class="sxs-lookup"><span data-stu-id="b8b50-105">To help your organization protect these accounts, you can now designate specific users as priority accounts and leverage app-specific features that provide them with extra protection.</span></span> <span data-ttu-id="b8b50-106">今後、より多くのアプリと機能が優先アカウントをサポートし、まず、優先度アカウント保護とプレミアム メール フロー監視の 2 つの機能を **発表しました**。</span><span class="sxs-lookup"><span data-stu-id="b8b50-106">In the future, more apps and features will support priority accounts, and to start with, we've announced two capabilities: **priority account protection** and **premium mail flow monitoring**.</span></span>

- <span data-ttu-id="b8b50-107">**優先度アカウント** 保護 - Microsoft Defender for Office 365 (以前は Office 365 Advanced Threat Protection) は、アラート、レポート、調査のフィルターで使用できるタグとして優先度アカウントをサポートします。</span><span class="sxs-lookup"><span data-stu-id="b8b50-107">**Priority account protection** - Microsoft Defender for Office 365 (formerly Office 365 Advanced Threat Protection) supports priority accounts as tags that can be used in filters in alerts, reports, and investigations.</span></span> <span data-ttu-id="b8b50-108">詳細については [、「Microsoft Defender の User tags for Office 365」を参照してください](../../security/office-365-security/user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="b8b50-108">For more information, check out [User tags in Microsoft Defender for Office 365](../../security/office-365-security/user-tags.md).</span></span>

  <span data-ttu-id="b8b50-109">自然な質問は、「すべてのユーザーが優先事項ではありませんか?</span><span class="sxs-lookup"><span data-stu-id="b8b50-109">A natural question is, "Aren't all users a priority?</span></span> <span data-ttu-id="b8b50-110">すべてのユーザーを優先アカウントとして指定しない理由</span><span class="sxs-lookup"><span data-stu-id="b8b50-110">Why not designate all users as priority accounts?"</span></span> <span data-ttu-id="b8b50-111">はい、すべてのユーザーが優先事項ですが、優先度アカウント保護には次のような追加の利点があります。</span><span class="sxs-lookup"><span data-stu-id="b8b50-111">Yes, all users are a priority, but priority account protection offers the following additional benefits:</span></span>

  - <span data-ttu-id="b8b50-112">**その他のヒューリスティック**: Microsoft データセンター内のメール フローの分析は、会社の役員のメール フロー パターンが平均的な従業員とは異なっているという点を示しています。</span><span class="sxs-lookup"><span data-stu-id="b8b50-112">**Additional heuristics**: Our analysis of mail flow in the Microsoft datacenters indicates that mail flow patterns for company executives are different than the average employee.</span></span> <span data-ttu-id="b8b50-113">優先度アカウント保護は、通常の従業員に利益を得ない会社の役員に合わせて特別に調整された追加のヒューリスティックを提供します。</span><span class="sxs-lookup"><span data-stu-id="b8b50-113">Priority account protection offers additional heuristics that are specifically tailored to company executives that wouldn't benefit a regular employee.</span></span>
  - <span data-ttu-id="b8b50-114">**レポートのその他の可視性**: 実際には、すべてのユーザー (または影響を受けるすべてのユーザー) の情報は、アラート、レポート、および調査で既に利用できます。</span><span class="sxs-lookup"><span data-stu-id="b8b50-114">**Additional visibility in reporting**: In effect, information for all users (or all affected users) is already available in alerts, reports, and investigations.</span></span> <span data-ttu-id="b8b50-115">優先度アカウント タグをフィルターとして使用すると、調査を具体的にターゲットに設定できます。</span><span class="sxs-lookup"><span data-stu-id="b8b50-115">The priority accounts tag as a filter allows you to specifically target your investigations.</span></span>

- <span data-ttu-id="b8b50-116">**Premium Mail Flow Monitoring** - 正常なメール フローはビジネスの成功にとって重要であり、配信の遅延や失敗はビジネスに悪影響を及ぼす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b8b50-116">**Premium Mail Flow Monitoring** - Healthy mail flow can be critical to business success, and delivery delays or failures can have a negative impact on the business.</span></span> <span data-ttu-id="b8b50-117">失敗または遅延メールのしきい値を選択し、そのしきい値を超えたときにアラートを受信し、優先アカウントの電子メールの問題のレポートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="b8b50-117">You can choose a threshold for failed or delayed emails, receive alerts when that threshold is exceeded, and view a report of email issues for priority accounts.</span></span> <span data-ttu-id="b8b50-118">詳細については、「最新の EAC で優先度アカウントの電子メールの [問題」レポートを参照してください。](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</span><span class="sxs-lookup"><span data-stu-id="b8b50-118">For more information, check out [Email issues for priority accounts report in the modern EAC](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</span></span>

<span data-ttu-id="b8b50-119">優先度アカウントのセキュリティのベスト プラクティスについては、「優先度アカウント [のセキュリティに関する推奨事項」を参照してください](../../security/office-365-security/security-recommendations-for-priority-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="b8b50-119">For security best practices for priority accounts, see [Security recommendations for priority accounts](../../security/office-365-security/security-recommendations-for-priority-accounts.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b8b50-120">はじめに</span><span class="sxs-lookup"><span data-stu-id="b8b50-120">Before you begin</span></span>

<span data-ttu-id="b8b50-121">この **トピックで説明する** 優先度アカウント保護機能は、次の要件を満たす組織でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b8b50-121">The **Priority account protection** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="b8b50-122">microsoft Defender for Office 365 Plan 2(Office 365 E3、Office 365 E5、Microsoft 365 E5、または Microsoft 365 E5 Security を含む)。</span><span class="sxs-lookup"><span data-stu-id="b8b50-122">Microsoft Defender for Office 365 Plan 2, including those with Office 365 E3, Office 365 E5, Microsoft 365 E5, or Microsoft 365 E5 Security.</span></span>

<span data-ttu-id="b8b50-123">この **トピックで説明するプレミアム** メール フロー監視機能は、次の要件を満たす組織でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b8b50-123">The **Premium Mail Flow Monitoring** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="b8b50-124">組織では、Office 365 E3、Microsoft 365 E3、Office 365 E5、Microsoft 365 E5 のいずれか、または組み合わせのいずれかからのライセンス数が 10,000 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8b50-124">Your organization needs to have a license count of at least 10,000, from either one of, or a combination of the following products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> <span data-ttu-id="b8b50-125">たとえば、組織で 3000 Office 365 E3 ライセンスと 8500 Microsoft 365 E5 を持つ場合、対象製品から合計 11,500 ライセンスを取得できます。</span><span class="sxs-lookup"><span data-stu-id="b8b50-125">For example, your organization can have 3000 Office 365 E3 licenses and 8500 Microsoft 365 E5, for a total of 11,500 licenses from the qualifying products.</span></span>
- <span data-ttu-id="b8b50-126">組織に月間 50 人以上のアクティブな Exchange Online ユーザーが必要です。</span><span class="sxs-lookup"><span data-stu-id="b8b50-126">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

> [!NOTE]
> <span data-ttu-id="b8b50-127">最大 250 の優先度アカウントを監視できます。</span><span class="sxs-lookup"><span data-stu-id="b8b50-127">You can monitor up to 250 priority accounts.</span></span>

<span data-ttu-id="b8b50-128">メールボックスに優先度アカウント保護を適用する場合は、メールボックスにアクセスできるユーザー (CEO や CEO の予定表を管理する CEO のエグゼクティブ アシスタントなど) にも優先度アカウント保護を適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8b50-128">When you apply priority account protection to a mailbox, you should also apply priority account protection to users who have access to the mailbox (for example, the CEO and the CEO's executive assistant who manages the CEO's calendar).</span></span>

### <a name="add-priority-accounts-from-the-setup-page"></a><span data-ttu-id="b8b50-129">[セットアップ] ページから優先度アカウントを追加する</span><span class="sxs-lookup"><span data-stu-id="b8b50-129">Add priority accounts from the Setup page</span></span>

<span data-ttu-id="b8b50-130">[セットアップ] ページから優先度アカウント **を追加します**。</span><span class="sxs-lookup"><span data-stu-id="b8b50-130">Add priority accounts from the **Setup page**.</span></span>

1. <span data-ttu-id="b8b50-131">で Microsoft 365 管理センターに移動します <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。</span><span class="sxs-lookup"><span data-stu-id="b8b50-131">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="b8b50-132">[組織の **ナレッジの**  >  **セットアップ] に移動** し、[最も **重要** なアカウントの監視] で [表示 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b8b50-132">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="b8b50-133">[スタート **] または [管理]** を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="b8b50-133">Select **Get Started** or **Manage**.</span></span>

4. <span data-ttu-id="b8b50-134">[優先度 **アカウントの追加** ] ページの検索フィールドに、優先度アカウントリストに追加するユーザーの名前または電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="b8b50-134">On the **Add Priority accounts** page, in the search field, type the name or email address of the person you want to add to the priority accounts list.</span></span> <span data-ttu-id="b8b50-135">また、失敗または遅延メールのメールしきい値を設定し、優先アカウントの問題に関する週次レポートを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="b8b50-135">You can also set your email threshold for failed or delayed emails and get a weekly report of issues for priority accounts.</span></span>

5. <span data-ttu-id="b8b50-136">ユーザーを選択し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="b8b50-136">Select the user and choose **Save**.</span></span>

<span data-ttu-id="b8b50-137">[アクティブ ユーザー] ページから優先度アカウントを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="b8b50-137">You can also add priority accounts from the Active users page.</span></span>

### <a name="add-priority-accounts-from-active-users-page"></a><span data-ttu-id="b8b50-138">[アクティブ ユーザー] ページから優先度アカウントを追加する</span><span class="sxs-lookup"><span data-stu-id="b8b50-138">Add priority accounts from Active users page</span></span>

<span data-ttu-id="b8b50-139">[アクティブ ユーザー] ページから優先度アカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="b8b50-139">Add priority accounts from the Active users page.</span></span>

1. <span data-ttu-id="b8b50-140"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> で管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="b8b50-140">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="b8b50-141">[ユーザー ]  >  **[アクティブなユーザー** ] に移動し、ページの上部にある **[...]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b8b50-141">Go to **Users** > **Active users** and choose **...** at the top of the page.</span></span> <span data-ttu-id="b8b50-142">[優先度 **アカウントの管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b8b50-142">Select **Manage priority accounts**.</span></span>

3. <span data-ttu-id="b8b50-143">[**アカウントの追加]** を選択し、[優先度アカウントの追加] ページの検索フィールドに、優先度アカウントリストに追加するユーザーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b8b50-143">Select **Add accounts**, and on the **Add Priority accounts** page, in the search field, type the name of the person you want to add to the priority accounts list.</span></span>

4. <span data-ttu-id="b8b50-144">ユーザーを選択し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="b8b50-144">Select the user and choose **Save**.</span></span>

## <a name="remove-a-user-from-the-priority-accounts-list"></a><span data-ttu-id="b8b50-145">優先度アカウントリストからユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="b8b50-145">Remove a user from the priority accounts list</span></span>

1. <span data-ttu-id="b8b50-146">で Microsoft 365 管理センターに移動します <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。</span><span class="sxs-lookup"><span data-stu-id="b8b50-146">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="b8b50-147">[組織の **ナレッジの**  >  **セットアップ] に移動** し、[最も **重要** なアカウントの監視] で [表示 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b8b50-147">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="b8b50-148">[最も **多くのアカウントを監視する** ] ページで、[この機能の管理] **で** [優先度アカウント **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b8b50-148">On the **Monitor your most accounts** page, choose **Priority accounts** under **Manage this feature**.</span></span>

4. <span data-ttu-id="b8b50-149">[優先度アカウント **] ページ** で、リストから削除するユーザーまたはユーザーを選択し、[アカウントの削除] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b8b50-149">On the **Priority accounts** page, select the user or users you want to remove from the list and choose, **Remove accounts**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b8b50-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="b8b50-150">Related topics</span></span>

[<span data-ttu-id="b8b50-151">Microsoft 365 での優先度アカウントの使用</span><span class="sxs-lookup"><span data-stu-id="b8b50-151">Using Priority Accounts in Microsoft 365</span></span>](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)
