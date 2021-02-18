---
title: 自動調査と対応により、侵害されたユーザー アカウントに対処する
keywords: AIR, autoIR, ATP, 自動化, 調査, 対応, 修復, 脅威, 高度な, 脅威, 保護, 侵害
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
ms.date: 02/25/2020
description: microsoft Defender for Office 365 プラン 2 の自動調査および対応機能を使用して、侵害されたユーザー アカウントを検出して対処するプロセスを高速化する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1dda8c9b4aec30fd35efa153aaf032eee23b5e8a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288743"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a><span data-ttu-id="e8f11-104">自動調査と対応により、侵害されたユーザー アカウントに対処する</span><span class="sxs-lookup"><span data-stu-id="e8f11-104">Address compromised user accounts with automated investigation and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e8f11-105">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="e8f11-105">**Applies to**</span></span>
- [<span data-ttu-id="e8f11-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e8f11-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e8f11-107">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="e8f11-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="e8f11-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e8f11-108">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)


<span data-ttu-id="e8f11-109">[Microsoft Defender for Office 365 プラン 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) には、強力な自動調査および対応 [(AIR)](office-365-air.md) 機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e8f11-109">[Microsoft Defender for Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) includes powerful [automated investigation and response](office-365-air.md) (AIR) capabilities.</span></span> <span data-ttu-id="e8f11-110">このような機能により、セキュリティ運用チームは脅威に対処するために多くの時間と労力を節約できます。</span><span class="sxs-lookup"><span data-stu-id="e8f11-110">Such capabilities can save your security operations team a lot of time and effort dealing with threats.</span></span> <span data-ttu-id="e8f11-111">Microsoft は引き続きセキュリティ機能を強化しています。</span><span class="sxs-lookup"><span data-stu-id="e8f11-111">Microsoft continues to improve security capabilities.</span></span> <span data-ttu-id="e8f11-112">最近、AIR の機能が強化され、セキュリティが侵害されたユーザー セキュリティ プレイブック (現在プレビュー中) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e8f11-112">Recently, AIR capabilities were enhanced to include a compromised user security playbook (currently in preview).</span></span> <span data-ttu-id="e8f11-113">侵害されたユーザー セキュリティ プレイブックの詳細については、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8f11-113">Read this article to learn more about the compromised user security playbook.</span></span> <span data-ttu-id="e8f11-114">さらに詳細については、Microsoft Defender for [Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) でユーザーの侵害を検出して対応し、侵害の範囲を制限する時間の高速化に関するブログ投稿をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e8f11-114">And see the blog post [Speed up time to detect and respond to user compromise and limit breach scope with Microsoft Defender for Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) for additional details.</span></span>

![侵害されたユーザーの自動調査](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

<span data-ttu-id="e8f11-116">侵害されたユーザー セキュリティ プレイブックにより、組織のセキュリティ チームは次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="e8f11-116">The compromised user security playbook enables your organization's security team to:</span></span>

- <span data-ttu-id="e8f11-117">侵害されたユーザー アカウントの検出を高速化します。</span><span class="sxs-lookup"><span data-stu-id="e8f11-117">Speed up detection of compromised user accounts;</span></span>

- <span data-ttu-id="e8f11-118">アカウントが侵害された場合に、侵害の範囲を制限する。そして</span><span class="sxs-lookup"><span data-stu-id="e8f11-118">Limit the scope of a breach when an account is compromised; and</span></span>

- <span data-ttu-id="e8f11-119">侵害されたユーザーに対して、より効果的かつ効率的に対応します。</span><span class="sxs-lookup"><span data-stu-id="e8f11-119">Respond to compromised users more effectively and efficiently.</span></span>

## <a name="compromised-user-alerts"></a><span data-ttu-id="e8f11-120">侵害されたユーザーアラート</span><span class="sxs-lookup"><span data-stu-id="e8f11-120">Compromised user alerts</span></span>

<span data-ttu-id="e8f11-121">ユーザー アカウントが侵害された場合、異常または異常な動作が発生します。</span><span class="sxs-lookup"><span data-stu-id="e8f11-121">When a user account is compromised, atypical or anomalous behaviors occur.</span></span> <span data-ttu-id="e8f11-122">たとえば、フィッシングメッセージやスパム メッセージは、信頼できるユーザー アカウントから内部的に送信される場合があります。</span><span class="sxs-lookup"><span data-stu-id="e8f11-122">For example, phishing and spam messages might be sent internally from a trusted user account.</span></span> <span data-ttu-id="e8f11-123">Defender for Office 365 は、365 内のメール パターンやコラボレーション アクティビティでこのような異常Officeできます。</span><span class="sxs-lookup"><span data-stu-id="e8f11-123">Defender for Office 365 can detect such anomalies in email patterns and collaboration activity within Office 365.</span></span> <span data-ttu-id="e8f11-124">この場合、アラートがトリガーされ、脅威軽減プロセスが開始されます。</span><span class="sxs-lookup"><span data-stu-id="e8f11-124">When this happens, alerts are triggered, and the threat mitigation process begins.</span></span>

<span data-ttu-id="e8f11-125">たとえば、不審な電子メール送信のためにトリガーされたアラートを次に示します。</span><span class="sxs-lookup"><span data-stu-id="e8f11-125">For example, here's an alert that was triggered because of suspicious email sending:</span></span>

![不審な電子メール送信のためにトリガーされたアラート](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

<span data-ttu-id="e8f11-127">次に、ユーザーの送信制限に達するとトリガーされたアラートの例を示します。</span><span class="sxs-lookup"><span data-stu-id="e8f11-127">And here's an example of an alert that was triggered when a sending limit was reached for a user:</span></span>

![送信制限に達した場合にトリガーされるアラート](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a><span data-ttu-id="e8f11-129">侵害されたユーザーを調査して対応する</span><span class="sxs-lookup"><span data-stu-id="e8f11-129">Investigate and respond to a compromised user</span></span>

<span data-ttu-id="e8f11-130">ユーザー アカウントが侵害されると、アラートがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="e8f11-130">When a user account is compromised, alerts are triggered.</span></span> <span data-ttu-id="e8f11-131">場合によっては、組織のセキュリティ運用チームによって問題が解決されるまで、そのユーザー アカウントがブロックされ、それ以上電子メール メッセージを送信できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="e8f11-131">And in some cases, that user account is blocked and prevented from sending any further email messages until the issue is resolved by your organization's security operations team.</span></span> <span data-ttu-id="e8f11-132">それ以外の場合は、自動調査が開始され、セキュリティ チームが推奨するアクションが実行される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e8f11-132">In other cases, an automated investigation begins which can result in recommended actions that your security team should take.</span></span>

- [<span data-ttu-id="e8f11-133">制限されたユーザーの表示と調査</span><span class="sxs-lookup"><span data-stu-id="e8f11-133">View and investigate restricted users</span></span>](#view-and-investigate-restricted-users)

- [<span data-ttu-id="e8f11-134">自動調査に関する詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="e8f11-134">View details about automated investigations</span></span>](#view-details-about-automated-investigations)

> [!IMPORTANT]
> <span data-ttu-id="e8f11-135">次のタスクを実行するには、適切なアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="e8f11-135">You must have appropriate permissions to perform the following tasks.</span></span> <span data-ttu-id="e8f11-136">AIR [機能を使用するために必要なアクセス許可を参照してください](office-365-air.md#required-permissions-to-use-air-capabilities)。</span><span class="sxs-lookup"><span data-stu-id="e8f11-136">See [Required permissions to use AIR capabilities](office-365-air.md#required-permissions-to-use-air-capabilities).</span></span>

### <a name="view-and-investigate-restricted-users"></a><span data-ttu-id="e8f11-137">制限されたユーザーの表示と調査</span><span class="sxs-lookup"><span data-stu-id="e8f11-137">View and investigate restricted users</span></span>

<span data-ttu-id="e8f11-138">制限されたユーザーの一覧に移動するには、いくつかのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="e8f11-138">You have a few options for navigating to a list of restricted users.</span></span> <span data-ttu-id="e8f11-139">たとえば、セキュリティ/コンプライアンス センター&、脅威管理の [制限されたユーザー  ] \> **のレビューに** \> **移動できます**。</span><span class="sxs-lookup"><span data-stu-id="e8f11-139">For example, in the Security & Compliance Center, you can go to **Threat management** \> **Review** \> **Restricted Users**.</span></span> <span data-ttu-id="e8f11-140">次の手順では、アラート ダッシュボードを使用したナビゲーションについて説明します。これは、トリガーされた可能性があるさまざまな種類のアラートを確認するための優れた方法です。</span><span class="sxs-lookup"><span data-stu-id="e8f11-140">The following procedure describes navigation using the **Alerts** dashboard, which is a good way to see various kinds of alerts that might have been triggered.</span></span>

1. <span data-ttu-id="e8f11-141"><https://protection.office.com> に移動し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="e8f11-141">Go to <https://protection.office.com> and sign in.</span></span>

2. <span data-ttu-id="e8f11-142">ナビゲーション ウィンドウで、[通知ダッシュボード] **を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e8f11-142">In the navigation pane, choose **Alerts** \> **Dashboard**.</span></span>

3. <span data-ttu-id="e8f11-143">[その他の **通知] ウィジェットで** 、[制限付きユーザー **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e8f11-143">In the **Other alerts** widget, choose **Restricted Users**.</span></span>

   ![その他の通知ウィジェット](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   <span data-ttu-id="e8f11-145">これにより、制限されたユーザーの一覧が開きます。</span><span class="sxs-lookup"><span data-stu-id="e8f11-145">This opens the list of restricted users.</span></span>

   ![Office 365 での制限付きユーザー](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. <span data-ttu-id="e8f11-147">制限されたユーザーの解放など、詳細を表示してアクションを実行するには、一覧でユーザー [アカウントを選択します](removing-user-from-restricted-users-portal-after-spam.md)。</span><span class="sxs-lookup"><span data-stu-id="e8f11-147">Select a user account in the list to view details and take action, such as [releasing the restricted user](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="view-details-about-automated-investigations"></a><span data-ttu-id="e8f11-148">自動調査に関する詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="e8f11-148">View details about automated investigations</span></span>

<span data-ttu-id="e8f11-149">自動調査が開始すると、セキュリティ/コンプライアンス センターで、その詳細と結果&確認できます。</span><span class="sxs-lookup"><span data-stu-id="e8f11-149">When an automated investigation has begun, you can see its details and results in the Security & Compliance Center.</span></span> <span data-ttu-id="e8f11-150">[脅威 **管理の** \> **調査] に移動** し、調査を選択して詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="e8f11-150">Go to **Threat management** \> **Investigations**, and then select an investigation to view its details.</span></span>

<span data-ttu-id="e8f11-151">詳細については、「調査の [詳細を表示する」を参照してください](air-view-investigation-results.md)。</span><span class="sxs-lookup"><span data-stu-id="e8f11-151">To learn more, see [View details of an investigation](air-view-investigation-results.md).</span></span>

## <a name="keep-the-following-points-in-mind"></a><span data-ttu-id="e8f11-152">次の点に気を付ける</span><span class="sxs-lookup"><span data-stu-id="e8f11-152">Keep the following points in mind</span></span>

- <span data-ttu-id="e8f11-153">**アラートを最新の情報に残します**。</span><span class="sxs-lookup"><span data-stu-id="e8f11-153">**Stay on top of your alerts**.</span></span> <span data-ttu-id="e8f11-154">ご存知のように、侵害が検出されなくなるほど、組織、顧客、パートナーに広範な影響とコストが発生する可能性が大きくなります。</span><span class="sxs-lookup"><span data-stu-id="e8f11-154">As you know, the longer a compromise goes undetected, the larger the potential for widespread impact and cost to your organization, customers, and partners.</span></span> <span data-ttu-id="e8f11-155">脅威を軽減するために、特にユーザーのアカウントが侵害された場合は、早期検出と適切な対応が重要です。</span><span class="sxs-lookup"><span data-stu-id="e8f11-155">Early detection and timely response are critical to mitigate threats, and especially when a user's account is compromised.</span></span>

- <span data-ttu-id="e8f11-156">**自動化は、セキュリティ運用チームを支援しますが、置き換わるのではありません**。</span><span class="sxs-lookup"><span data-stu-id="e8f11-156">**Automation assists, but does not replace, your security operations team**.</span></span> <span data-ttu-id="e8f11-157">調査と対応の自動化機能は、セキュリティが侵害されたユーザーを早期に検出できますが、セキュリティ運用チームは調査と修復を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8f11-157">Automated investigation and response capabilities can detect a compromised user early on, but your security operations team will likely need to engage and do some investigation and remediation.</span></span> <span data-ttu-id="e8f11-158">サポートが必要な場合</span><span class="sxs-lookup"><span data-stu-id="e8f11-158">Need some help with this?</span></span> <span data-ttu-id="e8f11-159">「アクション [の確認と承認」を参照してください](air-review-approve-pending-completed-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="e8f11-159">See [Review and approve actions](air-review-approve-pending-completed-actions.md).</span></span>

- <span data-ttu-id="e8f11-160">**不審なログインアラートを唯一のインジケーターとして使用していけな 。**</span><span class="sxs-lookup"><span data-stu-id="e8f11-160">**Don't rely on a suspicious login alert as your only indicator**.</span></span> <span data-ttu-id="e8f11-161">ユーザー アカウントが侵害されると、疑わしいログインアラートがトリガーされる場合とトリガーされない場合があります。</span><span class="sxs-lookup"><span data-stu-id="e8f11-161">When a user account is compromised, it might or might not trigger a suspicious login alert.</span></span> <span data-ttu-id="e8f11-162">アカウントが侵害された後に発生し、アラートをトリガーする一連のアクティビティである場合があります。</span><span class="sxs-lookup"><span data-stu-id="e8f11-162">Sometimes it's the series of activities that occur after an account is compromised that triggers an alert.</span></span> <span data-ttu-id="e8f11-163">アラートについて詳しくは、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8f11-163">Want to know more about alerts?</span></span> <span data-ttu-id="e8f11-164">アラート [ポリシーを参照してください](../../compliance/alert-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e8f11-164">See [Alert policies](../../compliance/alert-policies.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="e8f11-165">次の手順</span><span class="sxs-lookup"><span data-stu-id="e8f11-165">Next steps</span></span>

- [<span data-ttu-id="e8f11-166">AIR 機能を使用するために必要なアクセス許可を確認する</span><span class="sxs-lookup"><span data-stu-id="e8f11-166">Review the required permissions to use AIR capabilities</span></span>](office-365-air.md#required-permissions-to-use-air-capabilities)

- [<span data-ttu-id="e8f11-167">Office 365 で悪意のあるメールを検索して調査する</span><span class="sxs-lookup"><span data-stu-id="e8f11-167">Find and investigate malicious email in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)

- [<span data-ttu-id="e8f11-168">Microsoft Defender for Endpoint の AIR について</span><span class="sxs-lookup"><span data-stu-id="e8f11-168">Learn about AIR in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="e8f11-169">Microsoft 365 ロードマップにアクセスして、近日公開予定の機能を確認する</span><span class="sxs-lookup"><span data-stu-id="e8f11-169">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)
