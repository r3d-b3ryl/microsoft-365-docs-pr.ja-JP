---
title: Microsoft 365 サービス正常性を確認する方法
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365P_ServiceHealthModern
- O365M_ServiceHealthModern
- O365E_ViewStatusServices
- O365E_ServiceHealthModern
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- BCS160
- IWA160
ms.assetid: 932ad3ad-533c-418a-b938-6e44e8bc33b0
description: アクティブ サービスが中断していないかどうかを確認するため、サポートに連絡する前に、Microsoft 365 サービスの正常性状態を表示します。
ms.openlocfilehash: 95ab260b4950d261eed1288b8fdf1f59883ff15f
ms.sourcegitcommit: 17d82e5617f0466eb825e15ab88594afcdaf4437
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2021
ms.locfileid: "53300407"
---
# <a name="how-to-check-microsoft-365-service-health"></a><span data-ttu-id="101d0-103">Microsoft 365 サービス正常性を確認する方法</span><span class="sxs-lookup"><span data-stu-id="101d0-103">How to check Microsoft 365 service health</span></span>

<span data-ttu-id="101d0-104">[![管理センターについて知らせるラベルが変更されていますので、詳細については、aka.ms/aboutM365preview を参照してください。](../media/O365-Admin-AdminCenterChanging.png)](/office365/admin/microsoft-365-admin-center-preview?preserve-view=true&view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="101d0-104">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](../media/O365-Admin-AdminCenterChanging.png)](/office365/admin/microsoft-365-admin-center-preview?preserve-view=true&view=o365-worldwide)</span></span>

<span data-ttu-id="101d0-105">[[Microsoft 365 管理センター](https://go.microsoft.com/fwlink/p/?linkid=2024339)] の [**サービス正常性**] ページで、Office on the web、Yammer、Microsoft Dynamics CRM、モバイル デバイス管理クラウド サービスなどの Microsoft サービスの正常性を表示できます。</span><span class="sxs-lookup"><span data-stu-id="101d0-105">You can view the health of your Microsoft services, including Office on the web, Yammer, Microsoft Dynamics CRM, and mobile device management cloud services, on the **Service health** page in the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339).</span></span> <span data-ttu-id="101d0-106">クラウド サービスの問題が発生している場合は、サポートに連絡するかトラブルシューティングに時間を費やす前に、サービス正常性を確認することで、解決に向けて取り組み中の既知の問題であるかどうかを判別できます。</span><span class="sxs-lookup"><span data-stu-id="101d0-106">If you are experiencing problems with a cloud service, you can check the service health to determine whether this is a known issue with a resolution in progress before you call support or spend time troubleshooting.</span></span>

<span data-ttu-id="101d0-107">管理センターにサインインできない場合は、[[サービスの状態] ページ](https://status.office365.com)を使用して、テナントへのログインを妨げている既知の問題を確認できます。</span><span class="sxs-lookup"><span data-stu-id="101d0-107">If you are unable to sign in to the admin center, you can use the [service status page](https://status.office365.com) to check for known issues preventing you from logging into your tenant.</span></span>  <span data-ttu-id="101d0-108">また、サインアップして Twitter で [@MSFT365status](https://twitter.com/MSFT365Status) をフォローすると、特定のイベントの情報をご覧いただけます。</span><span class="sxs-lookup"><span data-stu-id="101d0-108">Also sign up to follow us at [@MSFT365status](https://twitter.com/MSFT365Status) on Twitter to see information on certain events.</span></span>

## <a name="how-to-check-service-health"></a><span data-ttu-id="101d0-109">サービス正常性の確認方法</span><span class="sxs-lookup"><span data-stu-id="101d0-109">How to check service health</span></span>

1. <span data-ttu-id="101d0-110">[https://admin.microsoft.com](https://go.microsoft.com/fwlink/p/?linkid=2024339) の Microsoft 365 管理センターに移動し、管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="101d0-110">Go to the Microsoft 365 admin center at [https://admin.microsoft.com](https://go.microsoft.com/fwlink/p/?linkid=2024339), and sign in with an admin account.</span></span>

    > [!NOTE]
    > <span data-ttu-id="101d0-111">グローバル 管理者またはサービス サポート管理者の役割が割り当てられているユーザーは、サービスの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="101d0-111">People who are assigned the global admin or service support admin role can view service health.</span></span> <span data-ttu-id="101d0-112">Exchange、SharePoint、および Skype for Business の管理者がサービス正常性を表示できるようにする場合も、ユーザーにはサービス管理者の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="101d0-112">To allow Exchange, SharePoint, and Skype for Business admins to view service health, they must also be assigned the Service admin role.</span></span> <span data-ttu-id="101d0-113">サービス正常性を表示できる役割の詳細については、「[管理者の役割について](../admin/add-users/about-admin-roles.md?preserve-view=true&view=o365-worldwide#commonly-used-microsoft-365-admin-center-roles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="101d0-113">For more information about roles that can view service health, see [About admin roles](../admin/add-users/about-admin-roles.md?preserve-view=true&view=o365-worldwide#commonly-used-microsoft-365-admin-center-roles).</span></span>

2. <span data-ttu-id="101d0-114">サービス正常性を開くには、管理センターで [**正常性**]  >  [**サービス正常性**] の順に移動するか、[**ホーム ダッシュボード**] の [**サービス正常性**] カードを選択します。</span><span class="sxs-lookup"><span data-stu-id="101d0-114">To view service health, in the admin center, go to **Health** > **Service health**, or select the **Service health** card on the **Home dashboard**.</span></span> <span data-ttu-id="101d0-115">[ダッシュボード] カードでは、アクティブなサービスの問題があるかどうかが示され、詳細な [**サービス正常性**] ページへのリンクが提供されます。</span><span class="sxs-lookup"><span data-stu-id="101d0-115">The dashboard card indicates whether there is an active service issue and links to the detailed **Service health** page.</span></span>

3. <span data-ttu-id="101d0-116">[**サービス正常性**] ページでは、それぞれのクラウド サービスの正常性の状態は表形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="101d0-116">On the **Service health** page, the health state of each cloud service is shown in a table format.</span></span>

   ![サービス正常性の現在の問題のビュー](../media/service-health-all-services.png)

<span data-ttu-id="101d0-118">[ **すべてのサービス]** タブ (既定のビュー) には、すべてのサービス、現在の正常性状態、アクティブなインシデントまたはアドバイザリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="101d0-118">The **All services** tab (the default view) shows all services, their current health state, and any active incidents or advisories.</span></span> <span data-ttu-id="101d0-119">[正常性] 列のアイコン **と状態** は、各サービスの状態を示します。</span><span class="sxs-lookup"><span data-stu-id="101d0-119">An icon and status in the **Health** column indicate the state of each service.</span></span>

<span data-ttu-id="101d0-120">サービスに対してアクティブなインシデントまたはアドバイザリがある場合、入れ子になったテーブルのサービス名の下に直接表示されます。</span><span class="sxs-lookup"><span data-stu-id="101d0-120">If there is an active incident or advisory for a service they will be listed directly under the service name in a nested table.</span></span> <span data-ttu-id="101d0-121">入れ子になったテーブルを折りたたみ、サービス名の左側にあるシェブロン アイコンをクリックすると、このビューのインシデントまたはアドバイザリを非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="101d0-121">You can collapse the nested table to hide the incidents or advisories in this view by clicking on the chevron icon to the left of the service name.</span></span>   

<span data-ttu-id="101d0-122">ビューをフィルター処理してすべてのアクティブなインシデントのみを表示するには、ページの上部にある [ **インシデント** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="101d0-122">To filter your view to only show all the active incidents, select the **Incidents** tab at the top of the page.</span></span> <span data-ttu-id="101d0-123">[アドバイザリ] **タブを選択** すると、投稿されたアクティブなアドバイザリすべてが表示されます。</span><span class="sxs-lookup"><span data-stu-id="101d0-123">Selecting the **Advisories** tab will only show all the active advisories posted.</span></span>

<span data-ttu-id="101d0-124">[ **履歴]** タブには、過去 7 日または 30 日以内に解決されたすべてのインシデントとアドバイザリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="101d0-124">The **History** tab shows all incidents and advisories that have been resolved within the last seven or 30 days.</span></span>

<span data-ttu-id="101d0-125">Microsoft 365 サービスで問題が発生し、それが [**サービス正常性**] ページに一覧表示されない場合は、[**問題を報告する**] を選択して短いフォームに記入してください。</span><span class="sxs-lookup"><span data-stu-id="101d0-125">If you're experiencing an issue with a Microsoft 365 service and you don’t see it listed on the **Service health** page, tell us about it by selecting **Report an issue**, and completing the short form.</span></span> <span data-ttu-id="101d0-126">他の組織からの関連データとレポートを調べて、問題がどの程度広がっているか、およびそれがサービスに起因しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="101d0-126">We’ll look at related data and reports from other organizations to see how widespread the issue is, and if it originated with our service.</span></span> <span data-ttu-id="101d0-127">該当する場合、[**サービス正常性**] ページに新しいインシデントまたは勧告として追加し、その解決を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="101d0-127">If it did, we’ll add it as a new incident or advisory on the **Service health** page, where you can track its resolution.</span></span> <span data-ttu-id="101d0-128">[ **報告された問題] ページ** には、テナントがこのフォームから報告したすべての問題と状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="101d0-128">The **Reported Issues** page will show all issues your tenant has reported from this form and the status.</span></span>

<span data-ttu-id="101d0-129">ダッシュボードに表示されるサービスのビューをカスタマイズするには、[基本設定]カスタム ビューを選択し、サービス正常性ダッシュボード ビューからフィルター処理するサービスのチェック ボックスをオフ  >  にします。</span><span class="sxs-lookup"><span data-stu-id="101d0-129">To customize your view of which services show up on the dashboard, select **Preferences** > **Custom view**,  and clear the checkboxes for the services you want to filter out of your Service health dashboard view.</span></span> <span data-ttu-id="101d0-130">監視するサービスごとにチェック ボックスがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="101d0-130">Make sure that the checkbox is selected for each service that you want to monitor.</span></span>

<span data-ttu-id="101d0-131">テナントに影響する新しいインシデントや、アクティブなインシデントの状態変更をメールで通知するように登録するには、[**環境設定**] > >  [**メール**] の順に選択し、[**サービス正常性の通知をメールで送る**] をクリックして、指定します。</span><span class="sxs-lookup"><span data-stu-id="101d0-131">To sign up for email notifications of new incidents that affect your tenant and status changes for an active incident, select **Preferences** > **Email**, click **Send me service heath notifications in email**, and then specify:</span></span>

- <span data-ttu-id="101d0-132">メールアドレスは最大 2 つです。</span><span class="sxs-lookup"><span data-stu-id="101d0-132">Up to two email addresses.</span></span>
- <span data-ttu-id="101d0-133">インシデントや警告の通知を希望するかどうか</span><span class="sxs-lookup"><span data-stu-id="101d0-133">Whether you want notifications for incidents or advisories</span></span>
- <span data-ttu-id="101d0-134">通知を希望するサービス</span><span class="sxs-lookup"><span data-stu-id="101d0-134">The services for which you want notification</span></span>

<span data-ttu-id="101d0-135">また、サービスのすべてのイベントではなく、個々のイベントに関する電子メール通知をサブスクライブすることもできます。</span><span class="sxs-lookup"><span data-stu-id="101d0-135">You can also subscribe to email notifications for individual events instead of every event for a service.</span></span> <span data-ttu-id="101d0-136">これを行うには、電子メール通知の更新プログラムを受信するアクティブな問題を選択し、[この問題の通知の管理] を選択し、次の **項目を指定** します。</span><span class="sxs-lookup"><span data-stu-id="101d0-136">To do so, select the active issue you want to receive email notification updates for, select **Manage notifications for this issue**, and then specify:</span></span> 
- <span data-ttu-id="101d0-137">メールアドレスは最大 2 つです。</span><span class="sxs-lookup"><span data-stu-id="101d0-137">Up to two email addresses.</span></span>

> [!NOTE]
> <span data-ttu-id="101d0-138">管理者ごとにユーザー設定を行うことができ、上記の 2 つのメールアドレスの制限は管理者アカウントごとに行われます。</span><span class="sxs-lookup"><span data-stu-id="101d0-138">Each admin can have their Preferences set and the above limit of two email address is per admin account.</span></span>

> [!TIP]
> <span data-ttu-id="101d0-139">モバイル デバイスで [Microsoft Admin アプリ](https://go.microsoft.com/fwlink/p/?linkid=627216)を使って、サービス正常性を表示することもできます。これはプッシュ通知により、常に最新情報を入手する優れた手段です。</span><span class="sxs-lookup"><span data-stu-id="101d0-139">You can also use the [Microsoft 365 Admin app](https://go.microsoft.com/fwlink/p/?linkid=627216) on your mobile device to view Service health, which is a great way to stay current with push notifications.</span></span>

### <a name="view-details-of-posted-service-health"></a><span data-ttu-id="101d0-140">投稿されたサービス正常性の詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="101d0-140">View details of posted service health</span></span>

<span data-ttu-id="101d0-141">[すべての **サービス]** ビューで、問題のタイトルを選択して問題の詳細ページを表示します。このページには、ソリューションの作業中に投稿されたメッセージのフィードなど、問題に関する詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="101d0-141">On the **All services** view, select the issue title to see the issue detail page, which shows more information about the issue, including a feed of all the messages posted while we work on a solution.</span></span> 

<span data-ttu-id="101d0-142">[![サービスの勧告を表示するスクリーンショット](../media/service-health-advisory.png)](../media/service-health-advisory.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="101d0-142">[ ![A screenshot showing the service advisory](../media/service-health-advisory.png) ](../media/service-health-advisory.png#lightbox)</span></span>

<span data-ttu-id="101d0-143">勧告またはインシデントの概要では、以下の情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="101d0-143">The advisory or incident summary provides the following information:</span></span>

- <span data-ttu-id="101d0-144">**タイトル** - 問題の概要。</span><span class="sxs-lookup"><span data-stu-id="101d0-144">**Title** - A summary of the problem.</span></span>
- <span data-ttu-id="101d0-145">**ID** - 問題の数値識別子。</span><span class="sxs-lookup"><span data-stu-id="101d0-145">**ID** - A numeric identifier for the problem.</span></span>
- <span data-ttu-id="101d0-146">**サービス** - 影響を受けるサービスの名前。</span><span class="sxs-lookup"><span data-stu-id="101d0-146">**Service** - The name of the affected service.</span></span>
- <span data-ttu-id="101d0-147">**最終更新時刻** - サービス正常性メッセージの最後の更新時刻。</span><span class="sxs-lookup"><span data-stu-id="101d0-147">**Last updated** - The last time that the service health message was updated.</span></span>
- <span data-ttu-id="101d0-148">**[推定開始時刻]** - 問題が開始された推定時間。</span><span class="sxs-lookup"><span data-stu-id="101d0-148">**Estimated Start time** - The estimated time when the issue started.</span></span>
- <span data-ttu-id="101d0-149">**状態** - この問題がサービスに与える影響。</span><span class="sxs-lookup"><span data-stu-id="101d0-149">**Status** - How this problem affects the service.</span></span>
- <span data-ttu-id="101d0-150">**ユーザーへの影響** - この問題がエンド ユーザーに与える影響の簡単な説明。</span><span class="sxs-lookup"><span data-stu-id="101d0-150">**User Impact** - A brief description of the impact this issue has on the end user.</span></span>
- <span data-ttu-id="101d0-151">**すべての更新** プログラム - 頻繁にメッセージを投稿して、ソリューションの適用に関する進捗状況をお知らせします。</span><span class="sxs-lookup"><span data-stu-id="101d0-151">**All Updates** - We post frequent messages to let you know the progress that we're making in applying a solution.</span></span>

![[問題の詳細] を表示するスクリーンショット](../media/service-health-advisory-detail.png)

### <a name="translate-service-health-details"></a><span data-ttu-id="101d0-153">サービス正常性の詳細を翻訳する</span><span class="sxs-lookup"><span data-stu-id="101d0-153">Translate service health details</span></span>

<span data-ttu-id="101d0-p111">機械翻訳を利用し、ユーザーの優先言語でメッセージを自動表示しています。言語の設定方法については、「[メッセージ センターの投稿の言語の翻訳](/microsoft-365/admin/manage/language-translation-for-message-center-posts)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="101d0-p111">We use machine translation to automatically display messages in your preferred language. Read [Language translation for Message center posts](/microsoft-365/admin/manage/language-translation-for-message-center-posts) for more information on how to set your language.</span></span>

### <a name="definitions"></a><span data-ttu-id="101d0-156">定義</span><span class="sxs-lookup"><span data-stu-id="101d0-156">Definitions</span></span>

<span data-ttu-id="101d0-157">ほとんどの場合、サービスは正常として表示され、それ以上の情報は示されません。</span><span class="sxs-lookup"><span data-stu-id="101d0-157">Most of the time, services will appear as healthy with no further information.</span></span> <span data-ttu-id="101d0-158">サービスに問題がある場合、問題は勧告またはインシデントとして認識され、現在の状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="101d0-158">When a service is having a problem, the issue is identified as either an advisory or an incident and shows a current status.</span></span>

> [!TIP]
> <span data-ttu-id="101d0-159">計画済みメンテナンス イベントはサービス正常性には表示されません。</span><span class="sxs-lookup"><span data-stu-id="101d0-159">Planned maintenance events aren't shown in service health.</span></span> <span data-ttu-id="101d0-160">常に **メッセージ センター** を確認することで、計画済みメンテナンス イベントを追跡できます。</span><span class="sxs-lookup"><span data-stu-id="101d0-160">You can track planned maintenance events by staying up to date with the **Message center**.</span></span> <span data-ttu-id="101d0-161">フィルタリングして [変更の計画] として分類されたメッセージに絞り込み、変更が発生する時期、その影響、およびそのための準備方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="101d0-161">Filter to messages categorized as Plan for change to find out when the change is going to happen, its effect, and how to prepare for it.</span></span> <span data-ttu-id="101d0-162">詳細については、「[Microsoft 365 のメッセージ センター](https://support.office.com/article/38fb3333-bfcc-4340-a37b-deda509c2093)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="101d0-162">See [Message center in Microsoft 365](https://support.office.com/article/38fb3333-bfcc-4340-a37b-deda509c2093) for more details.</span></span>

### <a name="incidents-and-advisories"></a><span data-ttu-id="101d0-163">インシデントおよび勧告</span><span class="sxs-lookup"><span data-stu-id="101d0-163">Incidents and advisories</span></span>

| <span data-ttu-id="101d0-164">アイコン</span><span class="sxs-lookup"><span data-stu-id="101d0-164">Icon</span></span> | <span data-ttu-id="101d0-165">説明</span><span class="sxs-lookup"><span data-stu-id="101d0-165">Description</span></span> |
|:-----|:-----|
|![勧告の情報アイコン](../media/a7f5fd21-c760-4948-9bc1-50f7c8070e28.png)|<span data-ttu-id="101d0-p114">サービスが勧告と示された場合、一部のユーザーに影響する問題が認識されています。ただし、サービスは引き続き使用可能です。勧告では、多くの場合、回避策があり、問題は一時的なものである可能性があるか、または範囲およびユーザーへの影響は限られます。</span><span class="sxs-lookup"><span data-stu-id="101d0-p114">If a service has an advisory shown, we are aware of a problem that is affecting some users, but the service is still available. In an advisory, there is often a workaround to the problem and the problem may be intermittent or is limited in scope and user impact.</span></span>  <br/> |
|![インシデントの感嘆符アイコン](../media/a636db57-6083-44dc-bbd5-556850804f17.png)|<span data-ttu-id="101d0-p115">サービスがアクティブ インシデントと示された場合、重大な問題であり、サービスまたはサービスの主な機能は使用できません。たとえば、ユーザーはメールの送受信やサインインができない可能性があります。インシデントはユーザーに顕著な影響を与えます。進行中にインシデントが発生した場合は、サービス正常性ダッシュボードで調査、軽減への取り組み、解決策の確認に関する更新プログラムを提供します。</span><span class="sxs-lookup"><span data-stu-id="101d0-p115">If a service has an active incident shown, it's a critical issue and the service or a major function of the service is unavailable. For example, users may be unable to send and receive email or unable to sign-in. Incidents will have noticeable impact to users. When there is an incident in progress, we will provide updates regarding the investigation, mitigation efforts, and confirmation of resolution in the Service health dashboard.</span></span>  <br/> |

### <a name="status-definitions"></a><span data-ttu-id="101d0-174">状態の定義</span><span class="sxs-lookup"><span data-stu-id="101d0-174">Status definitions</span></span>

| <span data-ttu-id="101d0-175">状態</span><span class="sxs-lookup"><span data-stu-id="101d0-175">Status</span></span> | <span data-ttu-id="101d0-176">定義</span><span class="sxs-lookup"><span data-stu-id="101d0-176">Definition</span></span> |
|:-----|:-----|
|<span data-ttu-id="101d0-177">**調査中**</span><span class="sxs-lookup"><span data-stu-id="101d0-177">**Investigating**</span></span> | <span data-ttu-id="101d0-178">潜在的な問題は認識されており、現状と影響範囲に関する詳細情報を収集中です。</span><span class="sxs-lookup"><span data-stu-id="101d0-178">We're aware of a potential issue and are gathering more information about what's going on and the scope of impact.</span></span> |
|<span data-ttu-id="101d0-179">**サービスの低下**</span><span class="sxs-lookup"><span data-stu-id="101d0-179">**Service degradation**</span></span> | <span data-ttu-id="101d0-p116">サービスまたは機能の使用に影響する可能性のある問題があることが確認されています。サービスの実行に通常より長い時間がかかる場合、一時的に中断している場合、機能が動作していない場合などにこの状態が示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="101d0-p116">We've confirmed that there is an issue that may affect use of a service or feature. You might see this status if a service is performing more slowly than usual, there are intermittent interruptions, or if a feature isn't working, for example.</span></span> |
|<span data-ttu-id="101d0-182">**サービスの中断**</span><span class="sxs-lookup"><span data-stu-id="101d0-182">**Service interruption**</span></span> | <span data-ttu-id="101d0-p117">問題がサービスへのアクセスを妨げると判断された場合にこの状態が示されます。この場合、問題は重要なものであり、常に再現できます。</span><span class="sxs-lookup"><span data-stu-id="101d0-p117">You'll see this status if we determine that an issue affects the ability for users to access the service. In this case, the issue is significant and can be reproduced consistently.</span></span> |
|<span data-ttu-id="101d0-185">**サービスの復元**</span><span class="sxs-lookup"><span data-stu-id="101d0-185">**Restoring service**</span></span> | <span data-ttu-id="101d0-186">問題の原因は特定されており、対応策はわかっています。また、サービスを正常な状態に戻している段階です。</span><span class="sxs-lookup"><span data-stu-id="101d0-186">The cause of the issue has been identified, we know what corrective action to take, and are in the process of bringing the service back to a healthy state.</span></span> |
|<span data-ttu-id="101d0-187">**拡張復旧**</span><span class="sxs-lookup"><span data-stu-id="101d0-187">**Extended recovery**</span></span> | <span data-ttu-id="101d0-p118">この状態は、ほとんどのユーザーに対するサービスを復元するための対応策が進行中ですが、影響を受けるすべてのシステムに適用されるまでは時間がかかることを示します。また、永続的な修正プログラムが適用されるのを待機する間に、一時的な修正プログラムで影響を減らした場合、この状態が表示されることもあります。</span><span class="sxs-lookup"><span data-stu-id="101d0-p118">This status indicates that corrective action is in progress to restore service to most users but will take some time to reach all the affected systems. You might also see this status if we've made a temporary fix to reduce impact while we wait to apply a permanent fix.</span></span> |
|<span data-ttu-id="101d0-190">**調査の中断**</span><span class="sxs-lookup"><span data-stu-id="101d0-190">**Investigation suspended**</span></span> | <span data-ttu-id="101d0-p119">潜在的な問題の詳細な調査で、さらに調査できるようにお客様からの追加情報を要求する場合は、この状態が示されます。お客様にアクションを求める場合は、必要なデータまたはログをお知らせします。</span><span class="sxs-lookup"><span data-stu-id="101d0-p119">If our detailed investigation of a potential issue results in a request for additional information from customers to allow us to investigate further, you'll see this status. If we need you to act, we'll let you know what data or logs we need.</span></span> |
|<span data-ttu-id="101d0-193">**サービスが復元されました**</span><span class="sxs-lookup"><span data-stu-id="101d0-193">**Service restored**</span></span> | <span data-ttu-id="101d0-p120">対応策によって根本的な問題が解決され、サービスが正常な状態に復元されたことが確認されています。原因を確認するには、問題の詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="101d0-p120">We've confirmed that corrective action has resolved the underlying problem and the service has been restored to a healthy state. To find out what went wrong, view the issue details.</span></span> |
|<span data-ttu-id="101d0-196">**誤検知**</span><span class="sxs-lookup"><span data-stu-id="101d0-196">**False positive**</span></span> | <span data-ttu-id="101d0-197">詳細な調査の結果、サービスが正常であり、設計どおりに動作していることを確認しました。</span><span class="sxs-lookup"><span data-stu-id="101d0-197">After a detailed investigation, we’ve confirmed the service is healthy and operating as designed.</span></span> <span data-ttu-id="101d0-198">サービスへの影響が観察されなかったか、インシデントの原因がサービス外に起因するものでした。</span><span class="sxs-lookup"><span data-stu-id="101d0-198">No impact to the service was observed or the cause of the incident originated outside of the service.</span></span> |
|<span data-ttu-id="101d0-199">**インシデントの事後レポートを発行済み**</span><span class="sxs-lookup"><span data-stu-id="101d0-199">**Post-incident report published**</span></span> | <span data-ttu-id="101d0-200">根本原因情報および同様の問題が再発しないようにするための次の手順を含む特定の問題についてのインシデントの事後レポートを発行しました。</span><span class="sxs-lookup"><span data-stu-id="101d0-200">We’ve published a Post Incident Report for a specific issue that includes root cause information and next steps to ensure a similar issue doesn’t reoccur.</span></span> |

### <a name="message-post-types"></a><span data-ttu-id="101d0-201">メッセージ投稿の種類</span><span class="sxs-lookup"><span data-stu-id="101d0-201">Message Post Types</span></span>

| <span data-ttu-id="101d0-202">種類</span><span class="sxs-lookup"><span data-stu-id="101d0-202">Type</span></span> | <span data-ttu-id="101d0-203">定義</span><span class="sxs-lookup"><span data-stu-id="101d0-203">Definition</span></span> |
|:-----|:-----|
|<span data-ttu-id="101d0-204">**クイック更新**</span><span class="sxs-lookup"><span data-stu-id="101d0-204">**Quick Update**</span></span> | <span data-ttu-id="101d0-205">すべてのお客様が利用できる、大まかに影響を与えるインシデントに対する短く頻繁な増分更新。</span><span class="sxs-lookup"><span data-stu-id="101d0-205">Short and frequent incremental updates for broadly impacting incidents, available to all customers.</span></span> |
|<span data-ttu-id="101d0-206">**その他の詳細**</span><span class="sxs-lookup"><span data-stu-id="101d0-206">**Additional Details**</span></span> | <span data-ttu-id="101d0-207">これらの追加の投稿は、インシデントの処理に関するより深い可視性を提供するために、より豊富な技術的および解決策の詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="101d0-207">These additional posts will provide richer technical and resolution details to offer deeper visibility into the handling of incidents.</span></span> <span data-ttu-id="101d0-208">これは、監視の概要と同じ要件を満たす[テナントExchange Online使用できます](/microsoft-365/enterprise/microsoft-365-exchange-monitoring?view=o365-worldwide#requirements)。</span><span class="sxs-lookup"><span data-stu-id="101d0-208">This is available for tenants that meet the same requirements outlined for [Exchange Online monitoring](/microsoft-365/enterprise/microsoft-365-exchange-monitoring?view=o365-worldwide#requirements),</span></span> |

### <a name="history"></a><span data-ttu-id="101d0-209">履歴</span><span class="sxs-lookup"><span data-stu-id="101d0-209">History</span></span>

<span data-ttu-id="101d0-210">サービス正常性を使用すると、現在の正常性状態を確認し、過去 30 日間にテナントに影響を与えたサービス アドバイザリとインシデントの履歴を表示できます。</span><span class="sxs-lookup"><span data-stu-id="101d0-210">Service health lets you look at your current health status and view the history of any service advisories and incidents that have affected your tenant in the past 30 days.</span></span> <span data-ttu-id="101d0-211">すべてのサービスの過去の正常性を表示するには、[履歴] ビュー **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="101d0-211">To view the past health of all services, select **History** view.</span></span>

<span data-ttu-id="101d0-212">稼働率への取り組みの詳細については、「[Microsoft 365 による透明性のある運用](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="101d0-212">For more information about our commitment to uptime, see [Transparent operations from Microsoft 365](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity).</span></span>

## <a name="related-topics"></a><span data-ttu-id="101d0-213">関連項目</span><span class="sxs-lookup"><span data-stu-id="101d0-213">Related topics</span></span>

[<span data-ttu-id="101d0-214">Microsoft 365 管理センターのアクティビティ レポート</span><span class="sxs-lookup"><span data-stu-id="101d0-214">Activity Reports in the Microsoft 365 admin center</span></span>](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

[<span data-ttu-id="101d0-215">メッセージ センターの基本設定</span><span class="sxs-lookup"><span data-stu-id="101d0-215">Message center Preferences</span></span>](../admin/manage/message-center.md?preserve-view=true&view=o365-worldwide#preferences)

[<span data-ttu-id="101d0-216">管理センターで Windows リリースの状態を確認する方法</span><span class="sxs-lookup"><span data-stu-id="101d0-216">How to check Windows release health on admin center</span></span>](/windows/deployment/update/check-release-health)
