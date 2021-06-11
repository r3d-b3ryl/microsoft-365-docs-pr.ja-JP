---
title: 調査と対応を自動化して、侵害されたユーザー アカウントに対処する
keywords: AIR、autoIR、Microsoft Defender for Endpoint、自動化、調査、対応、修復、脅威、高度、脅威、保護、侵害
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.date: 06/10/2021
description: Microsoft Defender for Office 365 プラン 2 の自動調査と対応機能を使用して、侵害されたユーザー アカウントを検出して対処するプロセスをスピードアップする方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cd84617230e774b92902ef3d11a365c1965ac814
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904142"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a><span data-ttu-id="7e93f-104">調査と対応を自動化して、侵害されたユーザー アカウントに対処する</span><span class="sxs-lookup"><span data-stu-id="7e93f-104">Address compromised user accounts with automated investigation and response</span></span>

<span data-ttu-id="7e93f-105">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="7e93f-105">**Applies to**</span></span>
- [<span data-ttu-id="7e93f-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="7e93f-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="7e93f-107">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="7e93f-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="7e93f-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7e93f-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)


<span data-ttu-id="7e93f-109">[Microsoft Defender for Office 365プラン 2 には](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)、強力な自動調査と応答[(AIR)](office-365-air.md)機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7e93f-109">[Microsoft Defender for Office 365 Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) includes powerful [automated investigation and response](office-365-air.md) (AIR) capabilities.</span></span> <span data-ttu-id="7e93f-110">このような機能により、セキュリティ運用チームが脅威に対処するために多くの時間と労力を節約できます。</span><span class="sxs-lookup"><span data-stu-id="7e93f-110">Such capabilities can save your security operations team a lot of time and effort dealing with threats.</span></span> <span data-ttu-id="7e93f-111">Microsoft は引き続きセキュリティ機能を強化しています。</span><span class="sxs-lookup"><span data-stu-id="7e93f-111">Microsoft continues to improve security capabilities.</span></span> <span data-ttu-id="7e93f-112">最近、AIR の機能が強化され、セキュリティが侵害されたユーザー セキュリティ プレイブック (現在プレビュー中) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7e93f-112">Recently, AIR capabilities were enhanced to include a compromised user security playbook (currently in preview).</span></span> <span data-ttu-id="7e93f-113">侵害されたユーザー セキュリティ プレイブックの詳細については、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e93f-113">Read this article to learn more about the compromised user security playbook.</span></span> <span data-ttu-id="7e93f-114">また、詳細については、[ブログの投稿「Microsoft Defender](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053)を使用してユーザーの侵害を検出して対応する時間をOffice 365を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e93f-114">And see the blog post [Speed up time to detect and respond to user compromise and limit breach scope with Microsoft Defender for Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) for additional details.</span></span>

![侵害されたユーザーの自動調査](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

<span data-ttu-id="7e93f-116">侵害されたユーザー セキュリティ プレイブックを使用すると、組織のセキュリティ チームは次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="7e93f-116">The compromised user security playbook enables your organization's security team to:</span></span>

- <span data-ttu-id="7e93f-117">侵害されたユーザー アカウントの検出を高速化します。</span><span class="sxs-lookup"><span data-stu-id="7e93f-117">Speed up detection of compromised user accounts;</span></span>

- <span data-ttu-id="7e93f-118">アカウントが侵害された場合に侵害の範囲を制限する。そして</span><span class="sxs-lookup"><span data-stu-id="7e93f-118">Limit the scope of a breach when an account is compromised; and</span></span>

- <span data-ttu-id="7e93f-119">侵害されたユーザーに対して、より効果的かつ効率的に対応します。</span><span class="sxs-lookup"><span data-stu-id="7e93f-119">Respond to compromised users more effectively and efficiently.</span></span>

## <a name="compromised-user-alerts"></a><span data-ttu-id="7e93f-120">侵害されたユーザー通知</span><span class="sxs-lookup"><span data-stu-id="7e93f-120">Compromised user alerts</span></span>

<span data-ttu-id="7e93f-121">ユーザー アカウントが侵害された場合、異常または異常な動作が発生します。</span><span class="sxs-lookup"><span data-stu-id="7e93f-121">When a user account is compromised, atypical or anomalous behaviors occur.</span></span> <span data-ttu-id="7e93f-122">たとえば、フィッシングメッセージとスパム メッセージは、信頼できるユーザー アカウントから内部的に送信される場合があります。</span><span class="sxs-lookup"><span data-stu-id="7e93f-122">For example, phishing and spam messages might be sent internally from a trusted user account.</span></span> <span data-ttu-id="7e93f-123">Defender for Office 365は、メール パターンやグループ内での共同作業のアクティビティでこのような異常をOffice 365。</span><span class="sxs-lookup"><span data-stu-id="7e93f-123">Defender for Office 365 can detect such anomalies in email patterns and collaboration activity within Office 365.</span></span> <span data-ttu-id="7e93f-124">この場合、アラートがトリガーされ、脅威の軽減プロセスが開始されます。</span><span class="sxs-lookup"><span data-stu-id="7e93f-124">When this happens, alerts are triggered, and the threat mitigation process begins.</span></span>

<span data-ttu-id="7e93f-125">たとえば、疑わしいメール送信のためにトリガーされたアラートを次に示します。</span><span class="sxs-lookup"><span data-stu-id="7e93f-125">For example, here's an alert that was triggered because of suspicious email sending:</span></span>

![不審なメール送信が発生した場合に発生するアラート](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

<span data-ttu-id="7e93f-127">次に、ユーザーの送信制限に達した際にトリガーされたアラートの例を示します。</span><span class="sxs-lookup"><span data-stu-id="7e93f-127">And here's an example of an alert that was triggered when a sending limit was reached for a user:</span></span>

![送信制限に達した場合にトリガーされるアラート](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a><span data-ttu-id="7e93f-129">侵害されたユーザーを調査して対応する</span><span class="sxs-lookup"><span data-stu-id="7e93f-129">Investigate and respond to a compromised user</span></span>

<span data-ttu-id="7e93f-130">ユーザー アカウントが侵害されると、アラートがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="7e93f-130">When a user account is compromised, alerts are triggered.</span></span> <span data-ttu-id="7e93f-131">場合によっては、組織のセキュリティ運用チームによって問題が解決されるまで、そのユーザー アカウントがブロックされ、それ以上の電子メール メッセージの送信がブロックされ、防止されます。</span><span class="sxs-lookup"><span data-stu-id="7e93f-131">And in some cases, that user account is blocked and prevented from sending any further email messages until the issue is resolved by your organization's security operations team.</span></span> <span data-ttu-id="7e93f-132">それ以外の場合は、自動調査が開始され、セキュリティ チームが推奨するアクションが実行される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7e93f-132">In other cases, an automated investigation begins which can result in recommended actions that your security team should take.</span></span>

- [<span data-ttu-id="7e93f-133">制限付きユーザーの表示と調査</span><span class="sxs-lookup"><span data-stu-id="7e93f-133">View and investigate restricted users</span></span>](#view-and-investigate-restricted-users)

- [<span data-ttu-id="7e93f-134">自動調査の詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="7e93f-134">View details about automated investigations</span></span>](#view-details-about-automated-investigations)

> [!IMPORTANT]
> <span data-ttu-id="7e93f-135">次のタスクを実行するには、適切なアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="7e93f-135">You must have appropriate permissions to perform the following tasks.</span></span> <span data-ttu-id="7e93f-136">「AIR [機能を使用するために必要なアクセス許可」を参照してください](office-365-air.md#required-permissions-to-use-air-capabilities)。</span><span class="sxs-lookup"><span data-stu-id="7e93f-136">See [Required permissions to use AIR capabilities](office-365-air.md#required-permissions-to-use-air-capabilities).</span></span>

### <a name="view-and-investigate-restricted-users"></a><span data-ttu-id="7e93f-137">制限付きユーザーの表示と調査</span><span class="sxs-lookup"><span data-stu-id="7e93f-137">View and investigate restricted users</span></span>

<span data-ttu-id="7e93f-138">制限付きユーザーの一覧に移動するためのいくつかのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="7e93f-138">You have a few options for navigating to a list of restricted users.</span></span> <span data-ttu-id="7e93f-139">たとえば、セキュリティ コンプライアンス センター&、脅威管理の [制限付きユーザーの確認 \> **]** \> **に移動できます**。</span><span class="sxs-lookup"><span data-stu-id="7e93f-139">For example, in the Security & Compliance Center, you can go to **Threat management** \> **Review** \> **Restricted Users**.</span></span> <span data-ttu-id="7e93f-140">次の手順では、アラート ダッシュボードを使用したナビゲーションについて説明します。これは、トリガーされた可能性があるさまざまな種類のアラートを確認するための良い方法です。</span><span class="sxs-lookup"><span data-stu-id="7e93f-140">The following procedure describes navigation using the **Alerts** dashboard, which is a good way to see various kinds of alerts that might have been triggered.</span></span>

1. <span data-ttu-id="7e93f-141">[https://protection.office.com](https://protection.office.com) に移動し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="7e93f-141">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span>

2. <span data-ttu-id="7e93f-142">ナビゲーション ウィンドウで、[アラート ダッシュボード] **を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="7e93f-142">In the navigation pane, choose **Alerts** \> **Dashboard**.</span></span>

3. <span data-ttu-id="7e93f-143">[その他 **の通知] ウィジェットで** 、[制限付きユーザー **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7e93f-143">In the **Other alerts** widget, choose **Restricted Users**.</span></span>

   ![その他のアラート ウィジェット](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   <span data-ttu-id="7e93f-145">これにより、制限付きユーザーの一覧が開きます。</span><span class="sxs-lookup"><span data-stu-id="7e93f-145">This opens the list of restricted users.</span></span>

   ![ユーザーの制限付きOffice 365](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. <span data-ttu-id="7e93f-147">リストでユーザー アカウントを選択して詳細を表示し、制限付きユーザーを解放するなどの [アクションを実行します](removing-user-from-restricted-users-portal-after-spam.md)。</span><span class="sxs-lookup"><span data-stu-id="7e93f-147">Select a user account in the list to view details and take action, such as [releasing the restricted user](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="view-details-about-automated-investigations"></a><span data-ttu-id="7e93f-148">自動調査の詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="7e93f-148">View details about automated investigations</span></span>

<span data-ttu-id="7e93f-149">自動調査が開始すると、その詳細と結果をセキュリティ コンプライアンス センター&確認できます。</span><span class="sxs-lookup"><span data-stu-id="7e93f-149">When an automated investigation has begun, you can see its details and results in the Security & Compliance Center.</span></span> <span data-ttu-id="7e93f-150">[脅威管理 **の** \> **調査] に** 移動し、調査を選択して詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="7e93f-150">Go to **Threat management** \> **Investigations**, and then select an investigation to view its details.</span></span>

<span data-ttu-id="7e93f-151">詳細については、「調査の詳細 [を表示する」を参照してください](air-view-investigation-results.md)。</span><span class="sxs-lookup"><span data-stu-id="7e93f-151">To learn more, see [View details of an investigation](air-view-investigation-results.md).</span></span>

## <a name="keep-the-following-points-in-mind"></a><span data-ttu-id="7e93f-152">以下の点に気を付ける</span><span class="sxs-lookup"><span data-stu-id="7e93f-152">Keep the following points in mind</span></span>

- <span data-ttu-id="7e93f-153">**アラートの上に滞在します**。</span><span class="sxs-lookup"><span data-stu-id="7e93f-153">**Stay on top of your alerts**.</span></span> <span data-ttu-id="7e93f-154">ご存知のように、妥協点が検出されなくなるほど、組織、顧客、パートナーに対する広範な影響とコストの可能性が大きくなります。</span><span class="sxs-lookup"><span data-stu-id="7e93f-154">As you know, the longer a compromise goes undetected, the larger the potential for widespread impact and cost to your organization, customers, and partners.</span></span> <span data-ttu-id="7e93f-155">脅威を軽減するために、特にユーザーのアカウントが侵害された場合は、早期の検出と適切な対応が重要です。</span><span class="sxs-lookup"><span data-stu-id="7e93f-155">Early detection and timely response are critical to mitigate threats, and especially when a user's account is compromised.</span></span>

- <span data-ttu-id="7e93f-156">**オートメーションは、セキュリティ運用チームを支援しますが、置き換えは行ないます**。</span><span class="sxs-lookup"><span data-stu-id="7e93f-156">**Automation assists, but does not replace, your security operations team**.</span></span> <span data-ttu-id="7e93f-157">調査と対応の自動化機能は、侵害されたユーザーを早期に検出できますが、セキュリティ運用チームは調査と修復を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e93f-157">Automated investigation and response capabilities can detect a compromised user early on, but your security operations team will likely need to engage and do some investigation and remediation.</span></span> <span data-ttu-id="7e93f-158">これにはいくつかのヘルプが必要ですか?</span><span class="sxs-lookup"><span data-stu-id="7e93f-158">Need some help with this?</span></span> <span data-ttu-id="7e93f-159">「アクション [の確認と承認」を参照してください](air-review-approve-pending-completed-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="7e93f-159">See [Review and approve actions](air-review-approve-pending-completed-actions.md).</span></span>

- <span data-ttu-id="7e93f-160">**疑わしいログインアラートを唯一のインジケーターとして使用しない**。</span><span class="sxs-lookup"><span data-stu-id="7e93f-160">**Don't rely on a suspicious login alert as your only indicator**.</span></span> <span data-ttu-id="7e93f-161">ユーザー アカウントが侵害されると、疑わしいログイン 通知がトリガーされる場合と、トリガーされない場合があります。</span><span class="sxs-lookup"><span data-stu-id="7e93f-161">When a user account is compromised, it might or might not trigger a suspicious login alert.</span></span> <span data-ttu-id="7e93f-162">アカウントが侵害された後に発生する一連のアクティビティがアラートをトリガーする場合があります。</span><span class="sxs-lookup"><span data-stu-id="7e93f-162">Sometimes it's the series of activities that occur after an account is compromised that triggers an alert.</span></span> <span data-ttu-id="7e93f-163">アラートについて詳しくは、お知りください。</span><span class="sxs-lookup"><span data-stu-id="7e93f-163">Want to know more about alerts?</span></span> <span data-ttu-id="7e93f-164">「 [アラート ポリシー」を参照してください](../../compliance/alert-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="7e93f-164">See [Alert policies](../../compliance/alert-policies.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="7e93f-165">次の手順</span><span class="sxs-lookup"><span data-stu-id="7e93f-165">Next steps</span></span>

- [<span data-ttu-id="7e93f-166">AIR 機能を使用するために必要なアクセス許可を確認する</span><span class="sxs-lookup"><span data-stu-id="7e93f-166">Review the required permissions to use AIR capabilities</span></span>](office-365-air.md#required-permissions-to-use-air-capabilities)

- [<span data-ttu-id="7e93f-167">悪意のあるメールを検索して調査Office 365</span><span class="sxs-lookup"><span data-stu-id="7e93f-167">Find and investigate malicious email in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)

- [<span data-ttu-id="7e93f-168">エンドポイント向け Microsoft Defender の AIR について説明します。</span><span class="sxs-lookup"><span data-stu-id="7e93f-168">Learn about AIR in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="7e93f-169">Microsoft 365 ロードマップにアクセスして、近日公開予定の機能を確認する</span><span class="sxs-lookup"><span data-stu-id="7e93f-169">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)