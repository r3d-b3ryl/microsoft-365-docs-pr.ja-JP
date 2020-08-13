---
title: 自動調査と応答によって侵害されたユーザーアカウントに対処する
keywords: AIR、自動赤外線、ATP、自動化、調査、応答、修復、脅威、高度、脅威、保護、侵害
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.date: 02/25/2020
description: Office 365 Advanced Threat Protection プラン2の自動調査および応答機能を使用して、侵害されたユーザーアカウントを検出して対処するプロセスを高速化する方法について説明します。
ms.openlocfilehash: 5a1dd64a0b30bb230af0d96432ae9542ce0370d8
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656911"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a><span data-ttu-id="8d88f-104">自動調査と応答によって侵害されたユーザーアカウントに対処する</span><span class="sxs-lookup"><span data-stu-id="8d88f-104">Address compromised user accounts with automated investigation and response</span></span>

<span data-ttu-id="8d88f-105">[Office 365 Advanced Threat Protection プラン 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2)には、自動化された強力な[調査および応答](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)(AIR) 機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8d88f-105">[Office 365 Advanced Threat Protection Plan 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2) includes powerful [automated investigation and response](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR) capabilities.</span></span> <span data-ttu-id="8d88f-106">このような機能を使用すると、セキュリティ運用チームに大きな脅威に対処するための時間と労力を大幅に節約できます。</span><span class="sxs-lookup"><span data-stu-id="8d88f-106">Such capabilities can save your security operations team a lot of time and effort dealing with threats.</span></span> <span data-ttu-id="8d88f-107">Microsoft は、セキュリティ機能を引き続き強化しています。</span><span class="sxs-lookup"><span data-stu-id="8d88f-107">Microsoft continues to improve security capabilities.</span></span> <span data-ttu-id="8d88f-108">最近では、安全なユーザーセキュリティプレイブックを含めるように、空気機能が強化されています (現在プレビュー中)。</span><span class="sxs-lookup"><span data-stu-id="8d88f-108">Recently, AIR capabilities were enhanced to include a compromised user security playbook (currently in preview).</span></span> <span data-ttu-id="8d88f-109">侵害されたユーザーセキュリティのプレイブックの詳細については、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d88f-109">Read this article to learn more about the compromised user security playbook.</span></span> <span data-ttu-id="8d88f-110">その他の詳細については、ブログの投稿速度を確認して、 [Office 365 ATP を使用してユーザーが侵害されるのを検出し、違反の範囲を制限](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053)します。</span><span class="sxs-lookup"><span data-stu-id="8d88f-110">And see the blog post [Speed up time to detect and respond to user compromise and limit breach scope with Office 365 ATP](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) for additional details.</span></span>

![侵害されたユーザーの自動化された調査](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

<span data-ttu-id="8d88f-112">侵害されたユーザーセキュリティのプレイブックにより、組織のセキュリティチームは次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8d88f-112">The compromised user security playbook enables your organization's security team to:</span></span>

- <span data-ttu-id="8d88f-113">侵害されたユーザーアカウントの検出を高速化します。</span><span class="sxs-lookup"><span data-stu-id="8d88f-113">Speed up detection of compromised user accounts;</span></span>

- <span data-ttu-id="8d88f-114">アカウントが侵害された場合に、違反の範囲を制限します。そして</span><span class="sxs-lookup"><span data-stu-id="8d88f-114">Limit the scope of a breach when an account is compromised; and</span></span>

- <span data-ttu-id="8d88f-115">侵害されたユーザーにより効果的かつ効率的に対応します。</span><span class="sxs-lookup"><span data-stu-id="8d88f-115">Respond to compromised users more effectively and efficiently.</span></span>

## <a name="compromised-user-alerts"></a><span data-ttu-id="8d88f-116">侵害されたユーザー通知</span><span class="sxs-lookup"><span data-stu-id="8d88f-116">Compromised user alerts</span></span>

<span data-ttu-id="8d88f-117">ユーザーアカウントが侵害されると、例外的または異常な動作が発生します。</span><span class="sxs-lookup"><span data-stu-id="8d88f-117">When a user account is compromised, atypical or anomalous behaviors occur.</span></span> <span data-ttu-id="8d88f-118">たとえば、フィッシングおよびスパムメッセージは、信頼できるユーザーアカウントから内部で送信される場合があります。</span><span class="sxs-lookup"><span data-stu-id="8d88f-118">For example, phishing and spam messages might be sent internally from a trusted user account.</span></span> <span data-ttu-id="8d88f-119">Office 365 Advanced Threat Protection は、Office 365 の電子メールパターンやコラボレーション作業でこのような異常を検出することがあります。</span><span class="sxs-lookup"><span data-stu-id="8d88f-119">Office 365 Advanced Threat Protection can detect such anomalies in email patterns and collaboration activity within Office 365.</span></span> <span data-ttu-id="8d88f-120">これが発生すると、アラートがトリガーされ、脅威の軽減プロセスが開始されます。</span><span class="sxs-lookup"><span data-stu-id="8d88f-120">When this happens, alerts are triggered, and the threat mitigation process begins.</span></span>

<span data-ttu-id="8d88f-121">たとえば、不審な電子メールの送信によってトリガーされた警告は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8d88f-121">For example, here's an alert that was triggered because of suspicious email sending:</span></span>

![疑わしい電子メールの送信によってトリガーされたアラート](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

<span data-ttu-id="8d88f-123">また、ユーザーの送信の制限に達したときにトリガーされた警告の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8d88f-123">And here's an example of an alert that was triggered when a sending limit was reached for a user:</span></span>

![送信制限に達したときにトリガーされるアラート](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a><span data-ttu-id="8d88f-125">侵害されたユーザーの調査と対応</span><span class="sxs-lookup"><span data-stu-id="8d88f-125">Investigate and respond to a compromised user</span></span>

<span data-ttu-id="8d88f-126">ユーザーアカウントが侵害されると、警告がトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="8d88f-126">When a user account is compromised, alerts are triggered.</span></span> <span data-ttu-id="8d88f-127">場合によっては、ユーザーアカウントがブロックされ、組織のセキュリティ運用チームによって問題が解決されるまで、以降の電子メールメッセージを送信できなくなります。</span><span class="sxs-lookup"><span data-stu-id="8d88f-127">And in some cases, that user account is blocked and prevented from sending any further email messages until the issue is resolved by your organization's security operations team.</span></span> <span data-ttu-id="8d88f-128">その他の場合は、自動化された調査が開始され、セキュリティチームにとって推奨されるアクションが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8d88f-128">In other cases, an automated investigation begins which can result in recommended actions that your security team should take.</span></span>

- [<span data-ttu-id="8d88f-129">制限されたユーザーの表示と調査</span><span class="sxs-lookup"><span data-stu-id="8d88f-129">View and investigate restricted users</span></span>](#view-and-investigate-restricted-users)

- [<span data-ttu-id="8d88f-130">自動調査に関する詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="8d88f-130">View details about automated investigations</span></span>](#view-details-about-automated-investigations)

> [!IMPORTANT]
> <span data-ttu-id="8d88f-131">次のタスクを実行するには、適切なアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d88f-131">You must have appropriate permissions to perform the following tasks.</span></span> <span data-ttu-id="8d88f-132">[AIR 機能を使用するには、必要なアクセス許可を](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air?view=o365-worldwide#required-permissions-to-use-air-capabilities)参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d88f-132">See [Required permissions to use AIR capabilities](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air?view=o365-worldwide#required-permissions-to-use-air-capabilities).</span></span>

### <a name="view-and-investigate-restricted-users"></a><span data-ttu-id="8d88f-133">制限されたユーザーの表示と調査</span><span class="sxs-lookup"><span data-stu-id="8d88f-133">View and investigate restricted users</span></span>

<span data-ttu-id="8d88f-134">制限されたユーザーのリストに移動するためのいくつかのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="8d88f-134">You have a few options for navigating to a list of restricted users.</span></span> <span data-ttu-id="8d88f-135">たとえば、セキュリティ & コンプライアンスセンターでは、[**脅威の管理**] [  >  **Review**  >  **制限付きユーザー**のレビュー] に移動できます。</span><span class="sxs-lookup"><span data-stu-id="8d88f-135">For example, in the Security & Compliance Center, you can go to **Threat management** > **Review** > **Restricted Users**.</span></span> <span data-ttu-id="8d88f-136">次の手順では、**通知**ダッシュボードを使用したナビゲーションについて説明します。これは、トリガーされた可能性のあるさまざまな種類の通知を確認するための適切な方法です。</span><span class="sxs-lookup"><span data-stu-id="8d88f-136">The following procedure describes navigation using the **Alerts** dashboard, which is a good way to see various kinds of alerts that might have been triggered.</span></span>

1. <span data-ttu-id="8d88f-137">[https://protection.office.com](https://protection.office.com) に移動し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="8d88f-137">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span>

2. <span data-ttu-id="8d88f-138">ナビゲーションウィンドウで、[**通知**ダッシュボード] を選択し  >  **Dashboard**ます。</span><span class="sxs-lookup"><span data-stu-id="8d88f-138">In the navigation pane, choose **Alerts** > **Dashboard**.</span></span>

3. <span data-ttu-id="8d88f-139">[**その他の通知**] ウィジェットで、[制限された**ユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d88f-139">In the **Other alerts** widget, choose **Restricted Users**.</span></span>

   ![その他の通知ウィジェット](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   <span data-ttu-id="8d88f-141">これにより、制限されたユーザーの一覧が開きます。</span><span class="sxs-lookup"><span data-stu-id="8d88f-141">This opens the list of restricted users.</span></span><br/>![Office 365 で制限されたユーザー](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. <span data-ttu-id="8d88f-143">リストでユーザーアカウントを選択して、制限され[たユーザーを解放](https://docs.microsoft.com/microsoft-365/security/office-365-security/removing-user-from-restricted-users-portal-after-spam)するなどの詳細情報を表示し、アクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="8d88f-143">Select a user account in the list to view details and take action, such as [releasing the restricted user](https://docs.microsoft.com/microsoft-365/security/office-365-security/removing-user-from-restricted-users-portal-after-spam).</span></span>

### <a name="view-details-about-automated-investigations"></a><span data-ttu-id="8d88f-144">自動調査に関する詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="8d88f-144">View details about automated investigations</span></span>

<span data-ttu-id="8d88f-145">自動調査が開始されたら、セキュリティ & コンプライアンスセンターでその詳細と結果を確認できます。</span><span class="sxs-lookup"><span data-stu-id="8d88f-145">When an automated investigation has begun, you can see its details and results in the Security & Compliance Center.</span></span> <span data-ttu-id="8d88f-146">[**脅威管理**  >  の**調査**] に移動し、詳細を表示する調査を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d88f-146">Go to **Threat management** > **Investigations**, and then select an investigation to view its details.</span></span>

<span data-ttu-id="8d88f-147">詳細については、「[調査の詳細を表示](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d88f-147">To learn more, see [View details of an investigation](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results).</span></span>

## <a name="keep-the-following-points-in-mind"></a><span data-ttu-id="8d88f-148">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="8d88f-148">Keep the following points in mind</span></span>

- <span data-ttu-id="8d88f-149">**通知を常に手前に**移動します。</span><span class="sxs-lookup"><span data-stu-id="8d88f-149">**Stay on top of your alerts**.</span></span> <span data-ttu-id="8d88f-150">ご存知のように、危険にさらされている時間が長くなるほど、組織、顧客、パートナーに対して広範な影響とコストが発生する可能性が大きくなります。</span><span class="sxs-lookup"><span data-stu-id="8d88f-150">As you know, the longer a compromise goes undetected, the larger the potential for widespread impact and cost to your organization, customers, and partners.</span></span> <span data-ttu-id="8d88f-151">事前の検出と適時の応答は、脅威を軽減するために重要であり、特にユーザーのアカウントが侵害された場合に非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="8d88f-151">Early detection and timely response are critical to mitigate threats, and especially when a user's account is compromised.</span></span>

- <span data-ttu-id="8d88f-152">**自動化は、セキュリティ運用チームを支援しますが、置き換えはしません**。</span><span class="sxs-lookup"><span data-stu-id="8d88f-152">**Automation assists, but does not replace, your security operations team**.</span></span> <span data-ttu-id="8d88f-153">自動化された調査および応答機能により、危険にさらされているユーザーが早いうちに検出されることがありますが、セキュリティ運用チームは、多くの場合、調査と修復を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d88f-153">Automated investigation and response capabilities can detect a compromised user early on, but your security operations team will likely need to engage and do some investigation and remediation.</span></span> <span data-ttu-id="8d88f-154">この点については、いくつかのヘルプが必要ですか?</span><span class="sxs-lookup"><span data-stu-id="8d88f-154">Need some help with this?</span></span> <span data-ttu-id="8d88f-155">「[レビューと承認のアクション」を](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air#review-and-approve-actions)参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d88f-155">See [Review and approve actions](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air#review-and-approve-actions).</span></span>

- <span data-ttu-id="8d88f-156">**疑わしいログインの警告は、唯一の指標としては利用しないで**ください。</span><span class="sxs-lookup"><span data-stu-id="8d88f-156">**Don't rely on a suspicious login alert as your only indicator**.</span></span> <span data-ttu-id="8d88f-157">ユーザーアカウントが侵害された場合、疑わしいログイン警告が発生するか、またはトリガーされない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8d88f-157">When a user account is compromised, it might or might not trigger a suspicious login alert.</span></span> <span data-ttu-id="8d88f-158">場合によっては、警告をトリガーするアカウントが侵害された後に発生する一連のアクティビティになることがあります。</span><span class="sxs-lookup"><span data-stu-id="8d88f-158">Sometimes it's the series of activities that occur after an account is compromised that triggers an alert.</span></span> <span data-ttu-id="8d88f-159">アラートの詳細を知りたいですか。</span><span class="sxs-lookup"><span data-stu-id="8d88f-159">Want to know more about alerts?</span></span> <span data-ttu-id="8d88f-160">「 [Alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d88f-160">See [Alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).</span></span>

## <a name="next-steps"></a><span data-ttu-id="8d88f-161">次のステップ</span><span class="sxs-lookup"><span data-stu-id="8d88f-161">Next steps</span></span>

- [<span data-ttu-id="8d88f-162">空気機能を使用するために必要なアクセス許可を確認する</span><span class="sxs-lookup"><span data-stu-id="8d88f-162">Review the required permissions to use AIR capabilities</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air?view=o365-worldwide#required-permissions-to-use-air-capabilities)

- [<span data-ttu-id="8d88f-163">Office 365 で悪意のある電子メールを検索して調査する</span><span class="sxs-lookup"><span data-stu-id="8d88f-163">Find and investigate malicious email in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered?view=o365-worldwide)

- [<span data-ttu-id="8d88f-164">Microsoft Defender ATP の AIR についての詳細情報</span><span class="sxs-lookup"><span data-stu-id="8d88f-164">Learn about AIR in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="8d88f-165">Microsoft 365 ロードマップにアクセスして、近日公開予定の機能を確認する</span><span class="sxs-lookup"><span data-stu-id="8d88f-165">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)

