---
title: ServiceNow を使用してチケットを作成および追跡する
description: Microsoft 365 セキュリティセンターは、ServiceNow でチケットをネイティブに作成および追跡する機能によって強化されています。 これにより、セキュリティ管理者は、セキュリティで保護されたスコアを ServiceNow に直接送信して、チケットを作成することができます。
keywords: security, Microsoft 365, M365, secure score, security center, ServiceNow, チケット, tasks
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: b0b8cda81bb6cec3958e7b2a758da191d803a0ed
ms.sourcegitcommit: acf29701bfba3e4843e49a79fde012f3c7a7024a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "37350334"
---
# <a name="manage-tickets-through-servicenow"></a><span data-ttu-id="e6b9b-105">ServiceNow によるチケットの管理</span><span class="sxs-lookup"><span data-stu-id="e6b9b-105">Manage tickets through ServiceNow</span></span>

<span data-ttu-id="e6b9b-106">Microsoft 365 セキュリティセンターは、ServiceNow でチケットをネイティブに作成および追跡する機能によって強化されています。</span><span class="sxs-lookup"><span data-stu-id="e6b9b-106">Microsoft 365 security center is being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> <span data-ttu-id="e6b9b-107">これにより、セキュリティ管理者は、 [Microsoft のセキュリティで保護されたスコア](microsoft-secure-score.md)向上アクションを ServiceNow に直接送信して、チケットを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="e6b9b-107">This allows security administrators to send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="e6b9b-108">インシデント管理チケットと変更管理チケットの両方を作成できます。</span><span class="sxs-lookup"><span data-stu-id="e6b9b-108">Both incident management and change management tickets can be created.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e6b9b-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="e6b9b-109">Prerequisites</span></span>

<span data-ttu-id="e6b9b-110">次のものを使用して、Microsoft 365 セキュリティセンターおよび ServiceNow インスタンスへのアクセス権を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6b9b-110">Have access to the Microsoft 365 security center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="e6b9b-111">キングストンまたはそれ以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="e6b9b-111">Kingston or higher version</span></span>
* <span data-ttu-id="e6b9b-112">管理者の HI 資格情報</span><span class="sxs-lookup"><span data-stu-id="e6b9b-112">Have admin HI credentials</span></span>
* <span data-ttu-id="e6b9b-113">ターゲットベンダーインスタンスに対する管理者権限を持っている</span><span class="sxs-lookup"><span data-stu-id="e6b9b-113">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="e6b9b-114">ServiceNow では、ServiceNow インスタンスのボックス設定 (既定値) を保持することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e6b9b-114">ServiceNow recommends users keep out of the box settings (default) in your ServiceNow instance.</span></span>  <span data-ttu-id="e6b9b-115">カスタマイズを行うと、インストールチェックリストと Microsoft 365 セキュリティセンターとの統合を完了する際にエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e6b9b-115">Having customizations could cause errors in completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="e6b9b-116">データ交換</span><span class="sxs-lookup"><span data-stu-id="e6b9b-116">Data exchange</span></span>

<span data-ttu-id="e6b9b-117">Microsoft 365 セキュリティセンターを ServiceNow に接続すると、Microsoft は次の追加データを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="e6b9b-117">When you connect the Microsoft 365 security center to ServiceNow, Microsoft will be receiving the following additional data:</span></span>

* <span data-ttu-id="e6b9b-118">ServiceNow インスタンス名</span><span class="sxs-lookup"><span data-stu-id="e6b9b-118">ServiceNow instance name</span></span>
* <span data-ttu-id="e6b9b-119">ServiceNow クライアント ID</span><span class="sxs-lookup"><span data-stu-id="e6b9b-119">ServiceNow client ID</span></span>
* <span data-ttu-id="e6b9b-120">ServiceNow クライアントシークレット</span><span class="sxs-lookup"><span data-stu-id="e6b9b-120">ServiceNow client secret</span></span>
* <span data-ttu-id="e6b9b-121">ServiceNow アクセス & 更新トークン</span><span class="sxs-lookup"><span data-stu-id="e6b9b-121">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="e6b9b-122">Microsoft 365 セキュリティセンターから ServiceNow チケットを作成すると、次のデータが ServiceNow に送信されます。</span><span class="sxs-lookup"><span data-stu-id="e6b9b-122">When you create a ServiceNow ticket from the Microsoft 365 security center the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="e6b9b-123">チケット作成を開始するユーザー ID</span><span class="sxs-lookup"><span data-stu-id="e6b9b-123">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="e6b9b-124">タスク名</span><span class="sxs-lookup"><span data-stu-id="e6b9b-124">Task name</span></span>
* <span data-ttu-id="e6b9b-125">タスクの説明</span><span class="sxs-lookup"><span data-stu-id="e6b9b-125">Task description</span></span>
* <span data-ttu-id="e6b9b-126">優先度</span><span class="sxs-lookup"><span data-stu-id="e6b9b-126">Priority</span></span>
* <span data-ttu-id="e6b9b-127">期限</span><span class="sxs-lookup"><span data-stu-id="e6b9b-127">Due date</span></span>
* <span data-ttu-id="e6b9b-128">推奨ソース (ユーザーの推奨事項または Microsoft 推奨)</span><span class="sxs-lookup"><span data-stu-id="e6b9b-128">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="e6b9b-129">推奨カテゴリ (デバイス、データ、アプリ、Id、インフラストラクチャ)</span><span class="sxs-lookup"><span data-stu-id="e6b9b-129">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="e6b9b-130">Microsoft 365 セキュリティセンターを ServiceNow に接続する</span><span class="sxs-lookup"><span data-stu-id="e6b9b-130">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="e6b9b-131">Microsoft 365 セキュリティセンターのホームページに移動します。これには、ServiceNow を使用しているかどうかを確認するカードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6b9b-131">Navigate to the Microsoft 365 security center home page, where you will see a card asking if you use ServiceNow.</span></span>

![ServiceNow を使用していますか](../images/do-you-use-servicenow-250.png)

<span data-ttu-id="e6b9b-133">その後、ServiceNow set up ページに送信されます。ここでは、Microsoft 365 Connector アプリを承認する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="e6b9b-133">From there you will be sent to the ServiceNow set up page where you'll follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

<span data-ttu-id="e6b9b-134">Microsoft 365 セキュリティセンターと ServiceNow 間の接続を認証するときは、個人の資格情報ではなく、インストール手順で作成した統合ユーザーログインとパスワードを使用してください。</span><span class="sxs-lookup"><span data-stu-id="e6b9b-134">When authorizing the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps and not your personal credentials.</span></span>

<span data-ttu-id="e6b9b-135">指示に従って接続を承認した後、Microsoft 365 セキュリティセンター接続ページと ServiceNow Microsoft 365 のチケットコネクタアプリの両方の接続状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="e6b9b-135">After following the directions and authorizing the connection, you can view the connection status on both the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="e6b9b-136">これで、タスクの作成を開始するための設定が完了しました。</span><span class="sxs-lookup"><span data-stu-id="e6b9b-136">Now you are all set to start creating tasks!</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="e6b9b-137">タスクを作成して ServiceNow に共有する</span><span class="sxs-lookup"><span data-stu-id="e6b9b-137">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="e6b9b-138">統合がセットアップされると、特定の Microsoft セキュリティスコア向上アクションに基づいて ServiceNow タスクを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e6b9b-138">Once the integration is set up, you can create ServiceNow tasks based on specific Microsoft Secure Score improvement actions.</span></span> <span data-ttu-id="e6b9b-139">Microsoft 365 セキュリティセンターポータルで、[セキュリティで保護されたスコア] のすべての改善アクションに移動し、[共有] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="e6b9b-139">Go to any improvement action in Secure Score in the Microsoft 365 security center portal, and select the “share” icon.</span></span> <span data-ttu-id="e6b9b-140">ドロップダウンオプションの1つは ServiceNow です。</span><span class="sxs-lookup"><span data-stu-id="e6b9b-140">One of the dropdown options is ServiceNow.</span></span>

![セキュリティで保護されたスコアでの ServiceNow 共有](../images/servicenow-share.png)

<span data-ttu-id="e6b9b-142">タスクが生成されます。ここで、優先度を設定して、名前、説明、または期限を編集できます。</span><span class="sxs-lookup"><span data-stu-id="e6b9b-142">A task will then be generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="e6b9b-143">すべての必須フィールドが入力されたら、そのタスクを ServiceNow に送信できます。</span><span class="sxs-lookup"><span data-stu-id="e6b9b-143">Once all the required fields are filled in, you can send the task to ServiceNow.</span></span>

<span data-ttu-id="e6b9b-144">タスクは、Microsoft 365 のセキュリティおよび構成変更要求として ServiceNow に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6b9b-144">The task will be visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="e6b9b-145">チケットを追跡する</span><span class="sxs-lookup"><span data-stu-id="e6b9b-145">Track tickets</span></span>

<span data-ttu-id="e6b9b-146">ServiceNow 変更管理およびインシデント管理チケットが作成されると、Microsoft 365 セキュリティセンターのホームページのカードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6b9b-146">Once ServiceNow change management and incident management tickets have been created, they will be displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="e6b9b-147">これらのカードから、チケットの作成、すべてのチケットの表示、または ServiceNow 構成の管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e6b9b-147">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![ServiceNow 変更管理チケット](../images/change-management-375.png)  ![ServiceNow インシデント管理チケット](../images/incident-management-375.png)

<span data-ttu-id="e6b9b-150">Microsoft 365 セキュリティセンターで ServiceNow 統合を再プロビジョニングまたは管理するには、いずれかのカードで**servicenow 構成を管理**するを選択します。</span><span class="sxs-lookup"><span data-stu-id="e6b9b-150">To re-provision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="e6b9b-151">その後、現在の ServiceNow 接続を削除して、チケットの状態名をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="e6b9b-151">From there you can  remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="e6b9b-152">Microsoft 365 セキュリティセンターに ServiceNow チケットが表示されている場合は、自分のタスクが、他のセキュリティダッシュボードアイテムと一緒に追跡および処理される場で有効になります。</span><span class="sxs-lookup"><span data-stu-id="e6b9b-152">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks will live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="e6b9b-153">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="e6b9b-153">Frequently asked questions</span></span>

### <a name="i-am-receiving-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="e6b9b-154">インストールチェックリストの最初のステップでエラーが表示される (OAuth の作成)</span><span class="sxs-lookup"><span data-stu-id="e6b9b-154">I am receiving an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="e6b9b-155">**エラーメッセージ**: スコープ ' x_mioms_m365ticket ' から ' oauth_entity ' に対する読み取り操作が拒否されました。テーブルのスコープ間のアクセスポリシーが原因です。</span><span class="sxs-lookup"><span data-stu-id="e6b9b-155">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused due to the table's cross-scope access policy</span></span>

<span data-ttu-id="e6b9b-156">アプリでは、ServiceNow インスタンスの管理者が OAuth エンティティを作成して読み取ることができると想定しています。</span><span class="sxs-lookup"><span data-stu-id="e6b9b-156">Our app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="e6b9b-157">このエラーは、ServiceNow のインスタンスのカスタマイズによって発生する可能性があります。これにより、OAuth エンティティを作成または読み取ることができるユーザーが制限されます。</span><span class="sxs-lookup"><span data-stu-id="e6b9b-157">This error could be caused due to a customization on your instance of ServiceNow, which restricts who can create/read OAuth entities.</span></span> <span data-ttu-id="e6b9b-158">ServiceNow では、ユーザーが既定の機能を使い続けることが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="e6b9b-158">ServiceNow recommends users keep out of the box functionality (default).</span></span>

<span data-ttu-id="e6b9b-159">"Application レジストリ" テーブルの構成を既定に設定します。</span><span class="sxs-lookup"><span data-stu-id="e6b9b-159">Set the “application registries” table configurations to default:</span></span>

* <span data-ttu-id="e6b9b-160">Label = Application Registeries</span><span class="sxs-lookup"><span data-stu-id="e6b9b-160">Label = Application Registeries</span></span>
* <span data-ttu-id="e6b9b-161">Name = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="e6b9b-161">Name = oauth_entity</span></span>
* <span data-ttu-id="e6b9b-162">= すべてのアプリケーションスコープからアクセス可能</span><span class="sxs-lookup"><span data-stu-id="e6b9b-162">Accessible from = All application scopes</span></span>
* <span data-ttu-id="e6b9b-163">読み取り可能 = チェックボックスが選択されている</span><span class="sxs-lookup"><span data-stu-id="e6b9b-163">Can read = check box selected</span></span>

<span data-ttu-id="e6b9b-164">**ServiceNow では、ユーザーが既定の機能を使い続けることが推奨されます。**</span><span class="sxs-lookup"><span data-stu-id="e6b9b-164">**ServiceNow recommends users keep out of the box functionality (default).**</span></span>

### <a name="how-do-i-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="e6b9b-165">Microsoft 365 Security & コンプライアンスコネクタ用に作成された OAuth エンティティを検証するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="e6b9b-165">How do I validate the OAuth entity created for Microsoft 365 Security & Compliance connector?</span></span>

<span data-ttu-id="e6b9b-166">ServiceNow で、アプリケーションのレジストリテーブル (メニュー > System OAuth > アプリケーションレジストリ) に移動し、自分が作成した OAuth エンティティ (割り当てた名前) を見つけます。</span><span class="sxs-lookup"><span data-stu-id="e6b9b-166">Go to application registries table (Menu > System OAuth > Application Registry) in ServiceNow and find the OAuth entity created by you (name that you assigned it).</span></span>

### <a name="how-do-i-validate-the-integration-user-created-in-step-two-of-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="e6b9b-167">Microsoft 365 Security & コンプライアンスコネクタのインストールチェックリストの手順2で作成した統合ユーザーを検証するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="e6b9b-167">How do I validate the Integration User created in step two of installation checklist for Microsoft 365 Security & Compliance connector?</span></span>

<span data-ttu-id="e6b9b-168">ServiceNow で [ユーザー] テーブル (> [ユーザー管理 > ユーザー)] を選び、自分で作成した統合ユーザー (割り当てられた名前) を見つけます。</span><span class="sxs-lookup"><span data-stu-id="e6b9b-168">Go to Users Table (Menu > User Administration > Users) in ServiceNow and find the Integration user created by you (name that you assigned it).</span></span>

<span data-ttu-id="e6b9b-169">Microsoft 365 セキュリティセンターと ServiceNow 間の接続を認証するときは、個人の資格情報ではなく、インストール手順で作成した統合ユーザーログインとパスワードを使用してください。</span><span class="sxs-lookup"><span data-stu-id="e6b9b-169">When authorizing the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps and not your personal credentials.</span></span>

### <a name="i-have-completed-the-installation-and-set-up-steps-but-i-am-unable-to-see-the-servicenow-cards-on-the-home-page-and-cannot-see-the-share-icon-in-microsoft-secure-score"></a><span data-ttu-id="e6b9b-170">インストールを完了し、手順をセットアップしましたが、そのホームページに ServiceNow カードが表示されず、Microsoft Secure Score の [共有] アイコンが表示されません</span><span class="sxs-lookup"><span data-stu-id="e6b9b-170">I have completed the installation and set up steps, but I am unable to see the ServiceNow cards on the home page and cannot see the Share icon in Microsoft Secure Score</span></span>

<span data-ttu-id="e6b9b-171">にhttps://security.microsoft.com/ticketProvisioningアクセスして、[プロビジョニング] ページの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="e6b9b-171">Check the status of the provisioning page by going to https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="e6b9b-172">[**保存**してホームページに戻る] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e6b9b-172">Select **Save** and return to the home page.</span></span> <span data-ttu-id="e6b9b-173">カードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6b9b-173">The cards should appear.</span></span>
