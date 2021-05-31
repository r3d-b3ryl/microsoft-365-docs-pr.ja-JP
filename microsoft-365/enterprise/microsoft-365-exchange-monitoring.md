---
title: Microsoft 365 の Exchange Online の監視
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/03/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- NOCSH
description: Exchange Online の監視を使用して、Microsoft 365 でのメールのインシデントや勧告の情報について確認します。
ms.openlocfilehash: ee31f8e152d7c54e37b850563bea57971e07f61c
ms.sourcegitcommit: 76c91e7b0d3172de57988eb4576d2b91c2f9ce18
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2021
ms.locfileid: "52707298"
---
# <a name="exchange-online-monitoring-for-microsoft-365"></a><span data-ttu-id="3dd20-103">Microsoft 365 の Exchange Online の監視</span><span class="sxs-lookup"><span data-stu-id="3dd20-103">Exchange Online monitoring for Microsoft 365</span></span>

<span data-ttu-id="3dd20-104">Microsoft 365 管理センターで Exchange Online の監視を使用して、組織の Microsoft 365 サブスクリプションの Exchange サービスの正常性を監視できます。</span><span class="sxs-lookup"><span data-stu-id="3dd20-104">You can use Exchange Online monitoring in the Microsoft 365 admin center to monitor the health of the Exchange service for your organization’s Microsoft 365 subscription.</span></span> <span data-ttu-id="3dd20-105">Exchange Online の監視は、以下のカテゴリに収集されたインシデントと勧告についての情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="3dd20-105">Exchange Online monitoring provides you with information about incidents and advisories that are collected in these categories:</span></span>

- <span data-ttu-id="3dd20-106">**インフラストラクチャ**: 定期的な更新を提供し、問題を解決するために Microsoft が所有する Microsoft 365 のインフラストラクチャで問題が検出されます。</span><span class="sxs-lookup"><span data-stu-id="3dd20-106">**Infrastructure**: Issue is detected in the Microsoft 365 infrastructure that Microsoft owns for providing regular updates and resolving the issue.</span></span> <span data-ttu-id="3dd20-107">たとえば、Exchange または他の Microsoft 365 のクラウド インフラストラクチャの問題のため、ユーザーが Exchange Online にアクセスできない場合などです。</span><span class="sxs-lookup"><span data-stu-id="3dd20-107">For example, users cannot access Exchange Online because of issues with Exchange or other Microsoft 365 cloud infrastructure.</span></span>
- <span data-ttu-id="3dd20-108">**サードパーティのインフラストラクチャ**: 組織が依存関係にあるサードパーティのインフラストラクチャで問題が検出され、解決するには所属の組織によるアクションが必要です。</span><span class="sxs-lookup"><span data-stu-id="3dd20-108">**Third-party infrastructure**: Issue is detected in third-party infrastructure on which your organization has taken a dependency and requires action from your organization for resolution.</span></span> <span data-ttu-id="3dd20-109">たとえば、ユーザー認証のトランザクションが、ユーザーが Exchange Online にアクセスできないようにするサードパーティのセキュリティ トークン サービス (STS) プロバイダーによって調整される場合などです。</span><span class="sxs-lookup"><span data-stu-id="3dd20-109">For example, user authentication transactions are getting throttled by a third-party security token service (STS) provider that prevents users from connecting to Exchange Online.</span></span>
- <span data-ttu-id="3dd20-110">**顧客のインフラストラクチャ**: 組織のインフラストラクチャで問題が検出され、解決するには所属の組織によるアクションが必要です。</span><span class="sxs-lookup"><span data-stu-id="3dd20-110">**Customer infrastructure**: Issue is detected in your organization's infrastructure and requires action from your organization for resolution.</span></span> <span data-ttu-id="3dd20-111">たとえば、組織によってホストされている STS プロバイダーから承認トークンを取得できないため、ユーザーが Exchange Online にアクセスできない場合などです。</span><span class="sxs-lookup"><span data-stu-id="3dd20-111">For example, users cannot access Exchange Online because they are unable to obtain an authentication token from STS provider hosted by your organization because of an expired certificate.</span></span>

<span data-ttu-id="3dd20-112">以下は、Microsoft 365 管理センターの **[サービス正常性]** ページの例です。これは、**[正常性] > [サービス正常性]** から利用できます。</span><span class="sxs-lookup"><span data-stu-id="3dd20-112">Here is an example of the **Service health** page in the Microsoft 365 admin center, available from **Health > Service health**.</span></span>

![Microsoft 365 管理センターの [サービス正常性] ページ](../media/microsoft-365-exchange-monitoring/service-health-dashboard-example.png)

<span data-ttu-id="3dd20-114">**[状態]** 列の値は、サービスが正常な状態にあるか、Microsoft が維持するクラウド サービスに基づいて勧告やインシデントがあるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="3dd20-114">The value of the **Status** column indicates whether the service is healthy or has advisories or incidents based on the cloud services that Microsoft maintains.</span></span> 

<span data-ttu-id="3dd20-115">**[組織とサード パーティの問題]** 列の値は、組織のインフラストラクチャまたはサードパーティ製のソフトウェアが、Exchange Online のユーザーのサービス正常性のエクスペリエンスに影響を与えるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="3dd20-115">The value of the **Your org and 3rd party issues** column indicates that your organization's infrastructure or third-party software affects your users service health experience with Exchange Online.</span></span> <span data-ttu-id="3dd20-116">勧告やインシデントを解決するには、*ユーザー* のアクションが必要です。</span><span class="sxs-lookup"><span data-stu-id="3dd20-116">Advisories or incidents require *your* actions to resolve.</span></span>

<span data-ttu-id="3dd20-117">以下は、Microsoft 365 管理センターの **Exchange Online** の監視ページです。これは、**[正常性] > [サービス正常性] > [Exchange Online]** から利用できます。</span><span class="sxs-lookup"><span data-stu-id="3dd20-117">Here is an example of the **Exchange Online** monitoring page in the Microsoft 365 admin center, available from **Health > Service health > Exchange Online**.</span></span>

![Microsoft 365 管理センターの Exchange Online の監視ページ](../media/microsoft-365-exchange-monitoring/exhange-monitoring-example.png)

<span data-ttu-id="3dd20-119">**Exchange Online** の監視ページで、Exchange Online サービスが正常な状態かどうか、関連するインシデントや勧告がないかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="3dd20-119">With the **Exchange Online** monitoring page, you can see whether the Exchange Online service is healthy or not and whether there are any associated incidents or advisories.</span></span> <span data-ttu-id="3dd20-120">Exchange Online の監視で、特定のメールのシナリオにおけるサービス正常性を確認し、リアルタイムに近い信号を表示してシナリオごとに影響を特定できます。</span><span class="sxs-lookup"><span data-stu-id="3dd20-120">With Exchange Online monitoring, you can look at the service health for specific email scenarios and view near real-time signals to determine the impact by scenario.</span></span> 

## <a name="requirements"></a><span data-ttu-id="3dd20-121">要件</span><span class="sxs-lookup"><span data-stu-id="3dd20-121">Requirements</span></span>

<span data-ttu-id="3dd20-122">このプレビューは、次の要件を満たしているお客様に対して有効になっています。</span><span class="sxs-lookup"><span data-stu-id="3dd20-122">This preview is enabled for customers who meet these requirements:</span></span> 

- <span data-ttu-id="3dd20-123">組織に Office 365 E3、Microsoft 365 E3、Office 365 E5、Microsoft 365 E5 の製品のいずれか 1 つまたは組み合わせから 5,000 個以上のライセンス数が必要です。</span><span class="sxs-lookup"><span data-stu-id="3dd20-123">Your organization needs to have a license count of at least 5,000, from one or a combination of these products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> 

  <span data-ttu-id="3dd20-124">たとえば、組織は Office 365 E3 のライセンスを 3,000 個と Microsoft 365 E5 のライセンスを 2,500 個持つことで、条件を満たす製品から合計 5,500 個のライセンスを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="3dd20-124">For example, your organization can have 3,000 Office 365 E3 licenses and 2,500 Microsoft 365 E5, for a total of 5,500 licenses from the qualifying products.</span></span>

- <span data-ttu-id="3dd20-125">組織に月間 50 人以上のアクティブな Exchange Online ユーザーが必要です。</span><span class="sxs-lookup"><span data-stu-id="3dd20-125">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

<span data-ttu-id="3dd20-126">Exchange Online の監視で、次のメール クライアントの正常性をメールの読み取りアクティビティに基づいて表示できます。</span><span class="sxs-lookup"><span data-stu-id="3dd20-126">With Exchange Online monitoring you can view the health for the following email clients based on email read activity:</span></span>

- <span data-ttu-id="3dd20-127">Outlook デスクトップ</span><span class="sxs-lookup"><span data-stu-id="3dd20-127">Outlook Desktop</span></span>
- <span data-ttu-id="3dd20-128">Outlook on the Web</span><span class="sxs-lookup"><span data-stu-id="3dd20-128">Outlook on the Web</span></span>
- <span data-ttu-id="3dd20-129">iOS と Android のネイティブのメール クライアント</span><span class="sxs-lookup"><span data-stu-id="3dd20-129">Native mail clients of iOS and Android</span></span> 
- <span data-ttu-id="3dd20-130">iOS と Android の Outlook モバイル アプリ</span><span class="sxs-lookup"><span data-stu-id="3dd20-130">Outlook Mobile app in iOS and Android</span></span> 
- <span data-ttu-id="3dd20-131">Outlook Mac クライアント</span><span class="sxs-lookup"><span data-stu-id="3dd20-131">Outlook Mac client</span></span>

<span data-ttu-id="3dd20-132">これらのクライアントについては、メールを読んでいるユーザーに基づいて過去 30 分間のアクティブ ユーザー数を表示すると共に、ダッシュボードのインシデントと勧告の数も表示できます。</span><span class="sxs-lookup"><span data-stu-id="3dd20-132">For these clients, you can see the number of active users in the last 30 minutes based on users reading an email, along with number of incidents and advisories in the dashboard.</span></span> <span data-ttu-id="3dd20-133">問題がないか確認するため、このデータは前週と同じ間隔と比較されます。</span><span class="sxs-lookup"><span data-stu-id="3dd20-133">This data is compared to the same interval for the previous week to see if there’s an issue.</span></span> 

>[!Note]
> <span data-ttu-id="3dd20-134">アクティブ ユーザー数は、ユーザーがメールを読むときなど、1 つのアクティビティによって測定されます。</span><span class="sxs-lookup"><span data-stu-id="3dd20-134">Active user count is measured by a single activity, for example, when a user reads an email.</span></span> <span data-ttu-id="3dd20-135">過去 30 分間のアクティビティだけを把握しています。</span><span class="sxs-lookup"><span data-stu-id="3dd20-135">It only accounts for the last 30 minutes of activity.</span></span>
>

<span data-ttu-id="3dd20-136">また、次のシナリオでも Exchange Online の正常性を監視することができます。</span><span class="sxs-lookup"><span data-stu-id="3dd20-136">You can also monitor Exchange Online health for the following scenarios:</span></span>

- <span data-ttu-id="3dd20-137">**メール フロー**: メッセージが Microsoft 365 ネットワークに配信された後に直ちに受信トレイに送信されたメッセージの数。</span><span class="sxs-lookup"><span data-stu-id="3dd20-137">**Mail flow**: The number of messages successfully delivered to a mailbox without any delay after the message reached the Microsoft 365 network.</span></span> 
- <span data-ttu-id="3dd20-138">**基本認証と先進認証**: Exchange Online サービスで正常に検証されたユーザー数。</span><span class="sxs-lookup"><span data-stu-id="3dd20-138">**Basic Authentication and Modern Authentication**: The number of users successfully validated in the Exchange Online service.</span></span>

![メール配信における Exchange の正常性を監視する例](../media/microsoft-365-exchange-monitoring/exhange-monitoring-scenario-example.png)

<span data-ttu-id="3dd20-140">これらすべてのシナリオにおいて、鍵となる数字はメイン ダッシュボードでの過去 30 分間のものです。</span><span class="sxs-lookup"><span data-stu-id="3dd20-140">For all these scenarios, the key numbers are for the last 30 minutes in the main dashboard.</span></span> <span data-ttu-id="3dd20-141">これらの各シナリオの詳細表示には、7 日間のほぼリアルタイムの傾向が、前週との比較された 30 分間の集計関数と共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="3dd20-141">Detailed views for each of these scenarios shows the near real-time trend for seven days with the 30-minute aggregate compared with the previous week.</span></span> 

## <a name="send-us-feedback"></a><span data-ttu-id="3dd20-142">フィードバックを送信する</span><span class="sxs-lookup"><span data-stu-id="3dd20-142">Send us feedback</span></span>

<span data-ttu-id="3dd20-143">フィードバックは 2 つの方法でお寄せいただけます。</span><span class="sxs-lookup"><span data-stu-id="3dd20-143">There are two ways you can provide feedback:</span></span>

- <span data-ttu-id="3dd20-144">Microsoft 365 管理センターのすべてのページに表示されている **[フィードバックの送信]** オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="3dd20-144">Use the **Give feedback** option available on every page of the Microsoft 365 admin center.</span></span>
- <span data-ttu-id="3dd20-145">特定のインシデントや勧告の場合、**[この投稿は役に立ちましたか?]** のリンクを使用してフィードバックを送信します。</span><span class="sxs-lookup"><span data-stu-id="3dd20-145">Submit feedback using the **Is this post helpful?** link for a specific incident or advisory.</span></span>

![特定のインシデントや勧告の場合に使用する](../media/microsoft-365-exchange-monitoring/exhange-monitoring-example-incident-feedback.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="3dd20-148">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="3dd20-148">Frequently asked questions</span></span>

#### <a name="1-why-dont-i-see-exchange-online-monitoring-under-health-in-the-microsoft-365-admin-center"></a><span data-ttu-id="3dd20-149">1. Microsoft 365 管理センターの [正常性] で [Exchange Online の監視] が表示されないのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="3dd20-149">1. Why don’t I see “Exchange Online monitoring” under Health in the Microsoft 365 admin center?</span></span> 

<span data-ttu-id="3dd20-150">まず、Microsoft 365 管理センターの **[ホーム]** ページで新しい管理センターが有効になっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3dd20-150">First, make sure you’ve enabled the new admin center on the **Home** page of the Microsoft 365 admin center.</span></span> 

<span data-ttu-id="3dd20-151">次に、次の両方の要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3dd20-151">Then make sure you meet both of the following requirements:</span></span> 

- <span data-ttu-id="3dd20-152">組織に Office 365 E3、Microsoft 365 E3、Office 365 E5、Microsoft 365 E5 の製品のいずれか 1 つまたは組み合わせから 5,000 個以上のライセンス数が必要です。</span><span class="sxs-lookup"><span data-stu-id="3dd20-152">Your organization needs to have a license count of at least 5,000, from one or a combination of these products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> 
- <span data-ttu-id="3dd20-153">組織に月間 50 人以上のアクティブな Exchange Online ユーザーが必要です。</span><span class="sxs-lookup"><span data-stu-id="3dd20-153">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

<span data-ttu-id="3dd20-154">組織のライセンス数が 5,000 ユーザー未満であり、月間アクティブ ユーザー数が 50 未満である場合、この要件が満たされるまで Exchange Online の監視は有効になりません。</span><span class="sxs-lookup"><span data-stu-id="3dd20-154">If the license count for your organization goes below 5,000 users and the monthly active users goes below 50 users, Exchange Online monitoring won’t be enabled until these requirements are met.</span></span>

#### <a name="2-the-active-user-count-in-the-dashboard-for-each-client-appears-to-be-low-we-have-a-lot-of-active-licenses-assigned-to-users-what-does-this-mean"></a><span data-ttu-id="3dd20-155">2. 各クライアントのダッシュボードのアクティブ ユーザー数が少なく表示されます。</span><span class="sxs-lookup"><span data-stu-id="3dd20-155">2. The active user count in the dashboard for each client appears to be low.</span></span> <span data-ttu-id="3dd20-156">しかし、多くの有効なライセンスがユーザーにアサインされています。</span><span class="sxs-lookup"><span data-stu-id="3dd20-156">We have a lot of active licenses assigned to users.</span></span> <span data-ttu-id="3dd20-157">これはどういうことですか?</span><span class="sxs-lookup"><span data-stu-id="3dd20-157">What does this mean?</span></span> 

<span data-ttu-id="3dd20-158">監視に表示されるアクティブ ユーザー数は、機能が呼び出したアクティビティをユーザーが実行した 30 分間のウィンドウに基づいています。</span><span class="sxs-lookup"><span data-stu-id="3dd20-158">The active user count shown in monitoring is based on a 30-minute window where users have performed the activity called out in the feature.</span></span> <span data-ttu-id="3dd20-159">これは、使用数とは異なることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3dd20-159">This shouldn’t be confused with usage numbers.</span></span> <span data-ttu-id="3dd20-160">使用数を表示するには、Microsoft 365 管理センターでアクティビティ レポートを使用してください (**[レポート] > [使用状況]**)。</span><span class="sxs-lookup"><span data-stu-id="3dd20-160">To view usage numbers, use activity reports in the Microsoft 365 admin center (**Reports > Usage**).</span></span>

#### <a name="3-will-there-be-other-monitoring-scenarios-for-other-services-such-as-teams-and-sharepoint"></a><span data-ttu-id="3dd20-161">3. Teams や SharePoint などの他のサービスに対する他の監視シナリオは追加されますか?</span><span class="sxs-lookup"><span data-stu-id="3dd20-161">3. Will there be other monitoring scenarios for other services such as Teams and SharePoint?</span></span> 

<span data-ttu-id="3dd20-162">Microsoft は、このエクスペリエンスを Microsoft 365 管理センターのサービス正常性ダッシュボード内に直接統合しています。</span><span class="sxs-lookup"><span data-stu-id="3dd20-162">Microsoft is integrating this experience directly inside the Service Health dashboard in the Microsoft 365 admin center.</span></span> <span data-ttu-id="3dd20-163">これにより、Microsoft は監視シナリオを他のサービスにも拡張できるようになります。お知らせするニュースがある場合は発表されます。</span><span class="sxs-lookup"><span data-stu-id="3dd20-163">This will provide opportunities for Microsoft to extend monitoring scenarios for other services, which will be announced when there is news to share.</span></span> 

#### <a name="4-what-is-the-plan-for-general-availability-of-this-experience"></a><span data-ttu-id="3dd20-164">4. このエクスペリエンスの一般提供予定について教えてください。</span><span class="sxs-lookup"><span data-stu-id="3dd20-164">4. What is the plan for general availability of this experience?</span></span> 

<span data-ttu-id="3dd20-165">Microsoft は、Exchange Online の監視を Microsoft 365 管理センターの **[サービス正常性]** ダッシュボードに直接統合しました。</span><span class="sxs-lookup"><span data-stu-id="3dd20-165">Microsoft has integrated Exchange Online monitoring directly on the **Service Health** dashboard in the Microsoft 365 admin center.</span></span> 

<span data-ttu-id="3dd20-166">新しくなった統合エクスペリエンスにより、Microsoft はユーザーからのフィードバックを収集し、一般提供の計画を定義する予定です。</span><span class="sxs-lookup"><span data-stu-id="3dd20-166">With this new integrated experience, Microsoft's plan is to collect your feedback and then define our plan for general availability.</span></span>

#### <a name="5-is-this-a-free-included-or-paid-extra-feature"></a><span data-ttu-id="3dd20-167">5. この機能は無料 (ライセンス付属) と有料 (追加コンテンツ) のどちらですか?</span><span class="sxs-lookup"><span data-stu-id="3dd20-167">5. Is this a free (included) or paid (extra) feature?</span></span> 

<span data-ttu-id="3dd20-168">この機能はパブリック プレビューの段階にあり、質問 1 での要件を満たしたユーザーのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="3dd20-168">This feature is in Public preview and only available for customers that meet the requirements in question 1.</span></span>

<!--
>[!Note]
>INTERNAL: That decision is pending
>
--> 

#### <a name="6-how-do-i-provide-feedback"></a><span data-ttu-id="3dd20-169">6. フィードバックを送信するにはどうすればいいですか?</span><span class="sxs-lookup"><span data-stu-id="3dd20-169">6. How do I provide feedback?</span></span> 

<span data-ttu-id="3dd20-170">一般的なフィードバックについては、**Exchange Online** の監視ページの右下隅にある **[フィードバックの送信]** アイコンを使用してください。</span><span class="sxs-lookup"><span data-stu-id="3dd20-170">For general feedback, use the **Give feedback** icon on the bottom-right corner of the **Exchange Online** monitoring page.</span></span> 

<span data-ttu-id="3dd20-171">インシデントや勧告のフィードバックについては、**[この投稿は役に立ちましたか?]** リンクを使用します。</span><span class="sxs-lookup"><span data-stu-id="3dd20-171">For feedback on incidents or advisories, use the **Is this post helpful?** link.</span></span>

#### <a name="7-where-is-the-data-instrumented-for-the-scenarios-that-show-activity-trends"></a><span data-ttu-id="3dd20-172">7. アクティビティの傾向を示すシナリオのインストルメント化されたデータはどこにありますか?</span><span class="sxs-lookup"><span data-stu-id="3dd20-172">7. Where is the data instrumented for the scenarios that show activity trends?</span></span>

<span data-ttu-id="3dd20-p114">データは Exchange Online サービスにインストルメント化されています。要求が Exchange Online に到達する前に障害が発生するか、Exchange Online に障害がある場合、アクティビティ信号の降下が確認できます。</span><span class="sxs-lookup"><span data-stu-id="3dd20-p114">The data is instrumented in the Exchange Online service. If there is a failure that happens before the request reaches Exchange Online or there is a failure in Exchange Online, you will see a drop in the activity signal.</span></span>

