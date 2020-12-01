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
ms.openlocfilehash: bc191873b3bbdcd84122a5430adeffe2b8c29fb1
ms.sourcegitcommit: 5ce64d510b15c6e2df32b78e6086f77156731e3c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/30/2020
ms.locfileid: "49477615"
---
# <a name="manage-and-monitor-priority-accounts"></a><span data-ttu-id="af6f0-103">優先度アカウントを管理および監視する</span><span class="sxs-lookup"><span data-stu-id="af6f0-103">Manage and monitor priority accounts</span></span>

<span data-ttu-id="af6f0-104">Microsoft のすべての365組織には、経営幹部、リーダー、マネージャー、または機密性の高い、機密、または高優先度の情報にアクセスできるその他のユーザーなど、重要な人物がいます。</span><span class="sxs-lookup"><span data-stu-id="af6f0-104">In every Microsoft 365 organization, there are people that are essential, like executives, leaders, managers, or other users who have access to sensitive, proprietary, or high priority information.</span></span>

<span data-ttu-id="af6f0-105">組織でこれらのアカウントを保護するために、特定のユーザーを優先度のアカウントとして指定し、アプリ固有の機能を利用して、その他の保護を強化することができます。</span><span class="sxs-lookup"><span data-stu-id="af6f0-105">To help your organization protect these accounts, you can now designate specific users as priority accounts and leverage app-specific features that provide them with extra protection.</span></span> <span data-ttu-id="af6f0-106">将来的には、優先度の高いアカウントをサポートするアプリや機能が増え、次のように、 **優先度のアカウント保護** と **プレミアムメールフローの監視** という2つの機能が発表されました。</span><span class="sxs-lookup"><span data-stu-id="af6f0-106">In the future, more apps and features will support priority accounts, and to start with, we’ve announced two capabilities: **priority account protection** and **premium mail flow monitoring**.</span></span>

- <span data-ttu-id="af6f0-107">**Priority account protection** -Microsoft Defender for office 365 (旧称 Office 365 Advanced Threat protection) は、警告、レポート、および調査のフィルターで使用できるタグとして、優先度アカウントをサポートします。</span><span class="sxs-lookup"><span data-stu-id="af6f0-107">**Priority account protection** - Microsoft Defender for Office 365 (formerly Office 365 Advanced Threat Protection) supports priority accounts as tags that can be used in filters in alerts, reports, and investigations.</span></span> <span data-ttu-id="af6f0-108">詳細については、「 [Microsoft Defender For Office 365」の「User tags」](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af6f0-108">For more information, check out [User tags in Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide).</span></span>
- <span data-ttu-id="af6f0-109">**プレミアムメールフローの監視** -正常なメールフローがビジネスの成功にとって重要であり、配信の遅延または失敗がビジネスに悪影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="af6f0-109">**Premium Mail Flow Monitoring** - Healthy mail flow can be critical to business success, and delivery delays or failures can have a negative impact on the business.</span></span> <span data-ttu-id="af6f0-110">失敗または遅延しているメールのしきい値を選択し、しきい値を超えたときに通知を受信し、優先度アカウントの電子メールの問題に関するレポートを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="af6f0-110">You can choose a threshold for failed or delayed emails, receive alerts when that threshold is exceeded, and view a report of email issues for priority accounts.</span></span> <span data-ttu-id="af6f0-111">詳細については、 [モダン EAC で、優先アカウントレポートに関するメールの問題](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="af6f0-111">For more information, check out [Email issues for priority accounts report in the modern EAC](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="af6f0-112">開始する前に</span><span class="sxs-lookup"><span data-stu-id="af6f0-112">Before you begin</span></span>

<span data-ttu-id="af6f0-113">このトピックに記載されている **優先度のアカウント保護** 機能は、次の要件を満たす組織でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="af6f0-113">The **Priority account protection** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="af6f0-114">Microsoft Defender for Office 365 プラン 2 (Office 365 E3、Office 365 E5、Microsoft 365 E5、Microsoft 365 E5 セキュリティを含む)。</span><span class="sxs-lookup"><span data-stu-id="af6f0-114">Microsoft Defender for Office 365 Plan 2, including those with Office 365 E3, Office 365 E5, Microsoft 365 E5, or Microsoft 365 E5 Security.</span></span>

<span data-ttu-id="af6f0-115">このトピックに記載されている **プレミアムメールフロー監視** 機能は、次の要件を満たしている組織にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="af6f0-115">The **Premium Mail Flow Monitoring** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="af6f0-116">組織のライセンス数は、少なくとも1万である必要があります。これは、Office 365 E3、Microsoft 365 E3、Office 365 E5、Microsoft 365 E5 のいずれかまたは両方から構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="af6f0-116">Your organization needs to have a license count of at least 10,000, from either one of, or a combination of the following products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> <span data-ttu-id="af6f0-117">たとえば、組織は 3000 Office 365 E3 ライセンスと 8500 Microsoft 365 E5 を持つことができます。これには、正規の製品に対する合計の11500ライセンスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="af6f0-117">For example, your organization can have 3000 Office 365 E3 licenses and 8500 Microsoft 365 E5, for a total of 11,500 licenses from the qualifying products.</span></span>
- <span data-ttu-id="af6f0-118">組織には、少なくとも50のアクティブな Exchange Online ユーザーが必要です。</span><span class="sxs-lookup"><span data-stu-id="af6f0-118">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

> [!NOTE]
> <span data-ttu-id="af6f0-119">最大250の優先度のアカウントを監視できます。</span><span class="sxs-lookup"><span data-stu-id="af6f0-119">You can monitor up to 250 priority accounts.</span></span>

### <a name="add-priority-accounts-from-the-setup-page"></a><span data-ttu-id="af6f0-120">セットアップページから優先度アカウントを追加する</span><span class="sxs-lookup"><span data-stu-id="af6f0-120">Add priority accounts from the Setup page</span></span>

<span data-ttu-id="af6f0-121">[ **セットアップ] ページ** で、優先度の高いアカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="af6f0-121">Add priority accounts from the **Setup page**.</span></span>

1. <span data-ttu-id="af6f0-122">Microsoft 365 管理センター () に移動 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> します。</span><span class="sxs-lookup"><span data-stu-id="af6f0-122">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="af6f0-123">[**セットアップ**  >  **の組織ナレッジ**] に移動して、[**最も重要なアカウントを監視** する] の下にある [**表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="af6f0-123">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="af6f0-124">[ **開始** ] または [ **管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="af6f0-124">Select **Get Started** or **Manage**.</span></span>

4. <span data-ttu-id="af6f0-125">[ **優先度アカウントの追加** ] ページで、検索フィールドに、優先度アカウントリストに追加するユーザーの名前または電子メールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="af6f0-125">On the **Add Priority accounts** page, in the search field, type the name or email address of the person you want to add to the priority accounts list.</span></span> <span data-ttu-id="af6f0-126">また、失敗したメールまたは遅延したメールのメールのしきい値を設定して、優先度アカウントの問題の週単位のレポートを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="af6f0-126">You can also set your email threshold for failed or delayed emails and get a weekly report of issues for priority accounts.</span></span>

5. <span data-ttu-id="af6f0-127">ユーザーを選択して、[ **保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="af6f0-127">Select the user and choose **Save**.</span></span>

<span data-ttu-id="af6f0-128">[アクティブなユーザー] ページから優先度の高いアカウントを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="af6f0-128">You can also add priority accounts from the Active users page.</span></span>

### <a name="add-priority-accounts-from-active-users-page"></a><span data-ttu-id="af6f0-129">[アクティブなユーザー] ページから優先度のアカウントを追加する</span><span class="sxs-lookup"><span data-stu-id="af6f0-129">Add priority accounts from Active users page</span></span>

<span data-ttu-id="af6f0-130">[アクティブなユーザー] ページから優先度の高いアカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="af6f0-130">Add priority accounts from the Active users page.</span></span>

1. <span data-ttu-id="af6f0-131"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> で管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="af6f0-131">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="af6f0-132">[アクティブ **なユーザー] に移動** して、  >  **Active users** ページの上部にある [.. **.** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="af6f0-132">Go to **Users** > **Active users** and choose **...** at the top of the page.</span></span> <span data-ttu-id="af6f0-133">[ **優先度アカウントの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="af6f0-133">Select **Manage priority accounts**.</span></span>

3. <span data-ttu-id="af6f0-134">[ **アカウントの追加**] を選択し、[ **優先度アカウントの追加** ] ページの検索フィールドに、優先度のアカウント一覧に追加するユーザーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="af6f0-134">Select **Add accounts**, and on the **Add Priority accounts** page, in the search field, type the name of the person you want to add to the priority accounts list.</span></span>

4. <span data-ttu-id="af6f0-135">ユーザーを選択して、[ **保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="af6f0-135">Select the user and choose **Save**.</span></span>

## <a name="remove-a-user-from-the-priority-accounts-list"></a><span data-ttu-id="af6f0-136">優先順位のアカウントリストからユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="af6f0-136">Remove a user from the priority accounts list</span></span>

1. <span data-ttu-id="af6f0-137">Microsoft 365 管理センター () に移動 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> します。</span><span class="sxs-lookup"><span data-stu-id="af6f0-137">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="af6f0-138">[**セットアップ**  >  **の組織ナレッジ**] に移動して、[**最も重要なアカウントを監視** する] の下にある [**表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="af6f0-138">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="af6f0-139">[**大部分のアカウントの監視**] ページで、[**この機能の管理**] の [**優先度の高いアカウント**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="af6f0-139">On the **Monitor your most accounts** page, choose **Priority accounts** under **Manage this feature**.</span></span>

4. <span data-ttu-id="af6f0-140">[ **優先度アカウント** ] ページで、リストから削除するユーザーを選択し、[ **アカウントの削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="af6f0-140">On the **Priority accounts** page, select the user or users you want to remove from the list and choose, **Remove accounts**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="af6f0-141">関連トピック</span><span class="sxs-lookup"><span data-stu-id="af6f0-141">Related topics</span></span>

[<span data-ttu-id="af6f0-142">Microsoft 365 での優先度アカウントの使用</span><span class="sxs-lookup"><span data-stu-id="af6f0-142">Using Priority Accounts in Microsoft 365</span></span>](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)