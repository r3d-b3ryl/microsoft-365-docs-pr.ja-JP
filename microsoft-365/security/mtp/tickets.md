---
title: ServiceNow を使用してチケットを作成および追跡する
description: Microsoft 365 セキュリティセンターは、ServiceNow でチケットをネイティブに作成および追跡する機能によって強化されています。 セキュリティ管理者は、セキュリティで保護されたスコアの推奨事項を ServiceNow に直接送信し、チケットを作成できます。
keywords: security, Microsoft 365, M365, secure score, security center, ServiceNow, チケット, tasks
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 904c1a019c55cabce6856a7caaca73d08d6db3f7
ms.sourcegitcommit: 841c06a5d566d404c35d5e9c0c7de5088daab976
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2020
ms.locfileid: "42836882"
---
# <a name="manage-tickets-through-servicenow"></a><span data-ttu-id="2d946-105">ServiceNow を介してチケットを管理する</span><span class="sxs-lookup"><span data-stu-id="2d946-105">Manage tickets through ServiceNow</span></span>

<span data-ttu-id="2d946-106">Microsoft 365 セキュリティセンターは、ServiceNow でチケットをネイティブに作成および追跡する機能によって強化されています。</span><span class="sxs-lookup"><span data-stu-id="2d946-106">Microsoft 365 security center is being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> <span data-ttu-id="2d946-107">セキュリティ管理者は、 [Microsoft のセキュリティで保護されたスコア](microsoft-secure-score.md)向上アクションを ServiceNow に直接送信して、チケットを作成できます。</span><span class="sxs-lookup"><span data-stu-id="2d946-107">Security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="2d946-108">インシデント管理チケットと変更管理チケットの両方を作成できます。</span><span class="sxs-lookup"><span data-stu-id="2d946-108">Both incident management and change management tickets can be created.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2d946-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="2d946-109">Prerequisites</span></span>

<span data-ttu-id="2d946-110">次のものを使用して、Microsoft 365 セキュリティセンターおよび ServiceNow インスタンスへのアクセス権を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d946-110">Have access to the Microsoft 365 security center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="2d946-111">キングストンまたはそれ以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="2d946-111">Kingston or higher version</span></span>
* <span data-ttu-id="2d946-112">管理者の HI 資格情報</span><span class="sxs-lookup"><span data-stu-id="2d946-112">Have admin HI credentials</span></span>
* <span data-ttu-id="2d946-113">ターゲットベンダーインスタンスに対する管理者権限を持っている</span><span class="sxs-lookup"><span data-stu-id="2d946-113">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="2d946-114">ServiceNow では、ユーザーが ServiceNow インスタンスに既定の設定を保持することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2d946-114">ServiceNow recommends that users keep default settings in your ServiceNow instance.</span></span> <span data-ttu-id="2d946-115">カスタマイズを行うと、インストールチェックリストと Microsoft 365 セキュリティセンターとの統合を完了する際にエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2d946-115">Having customizations could cause errors when completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="2d946-116">データ交換</span><span class="sxs-lookup"><span data-stu-id="2d946-116">Data exchange</span></span>

<span data-ttu-id="2d946-117">Microsoft 365 セキュリティセンターを ServiceNow に接続すると、Microsoft は次の追加データを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="2d946-117">When you connect the Microsoft 365 security center to ServiceNow, Microsoft receives the following additional data:</span></span>

* <span data-ttu-id="2d946-118">ServiceNow インスタンス名</span><span class="sxs-lookup"><span data-stu-id="2d946-118">ServiceNow instance name</span></span>
* <span data-ttu-id="2d946-119">ServiceNow クライアント ID</span><span class="sxs-lookup"><span data-stu-id="2d946-119">ServiceNow client ID</span></span>
* <span data-ttu-id="2d946-120">ServiceNow クライアントシークレット</span><span class="sxs-lookup"><span data-stu-id="2d946-120">ServiceNow client secret</span></span>
* <span data-ttu-id="2d946-121">ServiceNow アクセス & 更新トークン</span><span class="sxs-lookup"><span data-stu-id="2d946-121">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="2d946-122">Microsoft 365 セキュリティセンターから ServiceNow チケットを作成すると、次のデータが ServiceNow に送信されます。</span><span class="sxs-lookup"><span data-stu-id="2d946-122">When you create a ServiceNow ticket from the Microsoft 365 security center, the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="2d946-123">チケット作成を開始するユーザー ID</span><span class="sxs-lookup"><span data-stu-id="2d946-123">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="2d946-124">タスク名</span><span class="sxs-lookup"><span data-stu-id="2d946-124">Task name</span></span>
* <span data-ttu-id="2d946-125">タスクの説明</span><span class="sxs-lookup"><span data-stu-id="2d946-125">Task description</span></span>
* <span data-ttu-id="2d946-126">優先度</span><span class="sxs-lookup"><span data-stu-id="2d946-126">Priority</span></span>
* <span data-ttu-id="2d946-127">期限</span><span class="sxs-lookup"><span data-stu-id="2d946-127">Due date</span></span>
* <span data-ttu-id="2d946-128">推奨ソース (ユーザーの推奨事項または Microsoft 推奨)</span><span class="sxs-lookup"><span data-stu-id="2d946-128">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="2d946-129">推奨カテゴリ (デバイス、データ、アプリ、Id、インフラストラクチャ)</span><span class="sxs-lookup"><span data-stu-id="2d946-129">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="2d946-130">Microsoft 365 セキュリティセンターを ServiceNow に接続する</span><span class="sxs-lookup"><span data-stu-id="2d946-130">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="2d946-131">Microsoft 365 セキュリティセンターのホームページに移動して、ServiceNow 接続カードを表示します。</span><span class="sxs-lookup"><span data-stu-id="2d946-131">Navigate to the Microsoft 365 security center home page to see the ServiceNow connection card.</span></span>

![ServiceNow を使用していますか](../../media/do-you-use-servicenow-250.png)

<span data-ttu-id="2d946-133">[ServiceNow に接続] を選択して、[ServiceNow セットアップ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="2d946-133">Select "Connect to ServiceNow" to go to the ServiceNow setup page.</span></span> <span data-ttu-id="2d946-134">指示に従って、Microsoft 365 Connector アプリを承認します。</span><span class="sxs-lookup"><span data-stu-id="2d946-134">Follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

> [!NOTE]
> <span data-ttu-id="2d946-135">Microsoft 365 セキュリティセンターと ServiceNow 間の接続を承認する前に、インストール手順で作成した統合ユーザーログインとパスワードを使用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2d946-135">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="2d946-136">個人の資格情報は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="2d946-136">Do not use your personal credentials.</span></span>

<span data-ttu-id="2d946-137">指示に従って接続を承認した後、Microsoft 365 セキュリティセンター接続ページと ServiceNow Microsoft 365 のチケットコネクタアプリの両方の接続状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="2d946-137">After you have followed the directions and authorizing the connection, view the connection status on both the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="2d946-138">これで、タスクの作成を開始するための設定が完了しました。</span><span class="sxs-lookup"><span data-stu-id="2d946-138">Now you are all set to start creating tasks!</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="2d946-139">タスクを作成して ServiceNow に共有する</span><span class="sxs-lookup"><span data-stu-id="2d946-139">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="2d946-140">統合がセットアップされたら、特定の Microsoft セキュリティスコア向上アクションに基づいて ServiceNow タスクを作成します。</span><span class="sxs-lookup"><span data-stu-id="2d946-140">Once the integration is set up, create ServiceNow tasks based on specific Microsoft Secure Score improvement actions.</span></span> <span data-ttu-id="2d946-141">Microsoft 365 セキュリティセンターポータルで、[セキュリティで保護されたスコア] のすべての改善アクションに移動し、[共有] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="2d946-141">Go to any improvement action in Secure Score in the Microsoft 365 security center portal, and select the "share" icon.</span></span> <span data-ttu-id="2d946-142">ドロップダウンオプションの1つは ServiceNow です。</span><span class="sxs-lookup"><span data-stu-id="2d946-142">One of the dropdown options is ServiceNow.</span></span>

![セキュリティで保護されたスコアでの ServiceNow 共有](../../media/servicenow-share.png)

<span data-ttu-id="2d946-144">タスクが生成され、優先度を設定して、名前、説明、または期限を編集できます。</span><span class="sxs-lookup"><span data-stu-id="2d946-144">A task is generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="2d946-145">すべての必須フィールドが入力されたら、そのタスクを ServiceNow に送信します。</span><span class="sxs-lookup"><span data-stu-id="2d946-145">Once all the required fields are filled in, send the task to ServiceNow.</span></span>

<span data-ttu-id="2d946-146">タスクは、Microsoft 365 のセキュリティおよび構成変更要求として ServiceNow に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2d946-146">The task is visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="2d946-147">チケットを追跡する</span><span class="sxs-lookup"><span data-stu-id="2d946-147">Track tickets</span></span>

<span data-ttu-id="2d946-148">ServiceNow 変更管理およびインシデント管理チケットが作成されると、Microsoft 365 セキュリティセンターのホームページのカードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2d946-148">Once ServiceNow change management and incident management tickets have been created, they are displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="2d946-149">これらのカードから、チケットの作成、すべてのチケットの表示、または ServiceNow 構成の管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2d946-149">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![ServiceNow 変更管理チケット](../../media/change-management-375.png)  ![ServiceNow インシデント管理チケット](../../media/incident-management-375.png)

<span data-ttu-id="2d946-152">Microsoft 365 セキュリティセンターで ServiceNow 統合を再プロビジョニングまたは管理するには、いずれかのカードで**servicenow 構成を管理**するを選択します。</span><span class="sxs-lookup"><span data-stu-id="2d946-152">To re-provision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="2d946-153">そこから、現在の ServiceNow 接続を削除し、チケットの状態名をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="2d946-153">From there, remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="2d946-154">Microsoft 365 セキュリティセンターで ServiceNow チケットが表示されている場合は、自分のタスクが、他のセキュリティダッシュボードアイテムと一緒に追跡および操作できる場所に存在します。</span><span class="sxs-lookup"><span data-stu-id="2d946-154">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="2d946-155">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="2d946-155">Troubleshooting</span></span>

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="2d946-156">インストールチェックリストの最初のステップでエラーが表示される (OAuth の作成)</span><span class="sxs-lookup"><span data-stu-id="2d946-156">You receive an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="2d946-157">**エラーメッセージ**: 範囲 ' x_mioms_m365ticket ' から ' oauth_entity ' に対する読み取り操作が拒否されました。テーブルのスコープ間のアクセスポリシーが原因です。</span><span class="sxs-lookup"><span data-stu-id="2d946-157">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused due to the table's cross-scope access policy</span></span>

<span data-ttu-id="2d946-158">アプリでは、ServiceNow インスタンスの管理者が OAuth エンティティを作成して読み取ることができると想定しています。</span><span class="sxs-lookup"><span data-stu-id="2d946-158">The app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="2d946-159">このエラーは、ServiceNow のインスタンスのカスタマイズによって発生する可能性があります。これにより、OAuth エンティティを作成または読み取ることができるユーザーが制限されます。</span><span class="sxs-lookup"><span data-stu-id="2d946-159">This error could be caused due to a customization on your instance of ServiceNow, which restricts who can create/read OAuth entities.</span></span>

<span data-ttu-id="2d946-160">**ServiceNow では、ユーザーが既定の機能を維持することをお勧めします。**</span><span class="sxs-lookup"><span data-stu-id="2d946-160">**ServiceNow recommends that users keep default functionality.**</span></span>

<span data-ttu-id="2d946-161">"Application レジストリ" テーブルの構成を既定に設定します。</span><span class="sxs-lookup"><span data-stu-id="2d946-161">Set the "application registries" table configurations to default:</span></span>

* <span data-ttu-id="2d946-162">Label = Application Registeries</span><span class="sxs-lookup"><span data-stu-id="2d946-162">Label = Application Registeries</span></span>
* <span data-ttu-id="2d946-163">Name = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="2d946-163">Name = oauth_entity</span></span>
* <span data-ttu-id="2d946-164">= すべてのアプリケーションスコープからアクセス可能</span><span class="sxs-lookup"><span data-stu-id="2d946-164">Accessible from = All application scopes</span></span>
* <span data-ttu-id="2d946-165">読み取り可能 = チェックボックスが選択されている</span><span class="sxs-lookup"><span data-stu-id="2d946-165">Can read = check box selected</span></span>

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="2d946-166">Microsoft 365 Security & コンプライアンスコネクタ用に作成された OAuth エンティティを検証する方法</span><span class="sxs-lookup"><span data-stu-id="2d946-166">How to validate the OAuth entity created for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="2d946-167">ServiceNow で、アプリケーションのレジストリテーブル (**メニュー > System OAuth > アプリケーションレジストリ**) に移動し、自分で作成した OAuth エンティティを割り当てた名前で検索します。</span><span class="sxs-lookup"><span data-stu-id="2d946-167">Go to application registries table (**Menu > System OAuth > Application Registry**) in ServiceNow and find the OAuth entity created by you, with the name that you assigned it.</span></span>

### <a name="logging-in-as-the-integration-user"></a><span data-ttu-id="2d946-168">統合ユーザーとしてログインする</span><span class="sxs-lookup"><span data-stu-id="2d946-168">Logging in as the integration user</span></span>

<span data-ttu-id="2d946-169">Microsoft 365 セキュリティセンターと ServiceNow 間の接続を承認する前に、インストール手順で作成した統合ユーザーログインとパスワードを使用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2d946-169">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="2d946-170">個人の資格情報は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="2d946-170">Do not use your personal credentials.</span></span>

1. <span data-ttu-id="2d946-171">ServiceNow の [認証] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="2d946-171">Go the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="2d946-172">個人の資格情報を使用してサインインしている場合は、右上隅にある [リンクし**ない**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2d946-172">If you are signed in with your personal credentials, select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="2d946-173">インストールチェックリストから、以前に作成した統合ユーザーとして ServiceNow にログインします。</span><span class="sxs-lookup"><span data-stu-id="2d946-173">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="2d946-174">セキュリティ + コンプライアンスコネクタが ServiceNow アカウントに接続できるかどうかを確認する、ServiceNow ページの [**許可**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2d946-174">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="2d946-175">セットアップの手順を続行します。</span><span class="sxs-lookup"><span data-stu-id="2d946-175">Proceed with the setup steps.</span></span>

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="2d946-176">Microsoft 365 Security & コンプライアンスコネクタのインストールチェックリストで作成した統合ユーザーを検証する方法</span><span class="sxs-lookup"><span data-stu-id="2d946-176">How to validate the Integration User created with the installation checklist for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="2d946-177">ServiceNow でユーザーテーブル **(メニュー > ユーザー管理 > ユーザー**) に移動し、自分で作成した統合ユーザーを割り当てた名前で検索します。</span><span class="sxs-lookup"><span data-stu-id="2d946-177">Go to Users Table **(Menu > User Administration > Users**) in ServiceNow and find the Integration user created by you, with the name that you assigned it.</span></span>

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a><span data-ttu-id="2d946-178">お客様の会社では、シングルサインオンが有効になっています。これにより、Microsoft 365 セキュリティセンターから ServiceNow に接続できなくなります。</span><span class="sxs-lookup"><span data-stu-id="2d946-178">Your company has single sign-on enabled which prevents you from connecting to ServiceNow through the Microsoft 365 security center</span></span>

<span data-ttu-id="2d946-179">会社でシングルサインオンが有効になっていて、エラーが発生するかログインが失敗した場合は、2つのソリューションのいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="2d946-179">If your company has enabled single sign-on and you receive an error or login is unsuccessful, follow one of the two solutions.</span></span>

#### <a name="log-into-servicenow-as-the-integration-user"></a><span data-ttu-id="2d946-180">ServiceNow に統合ユーザーとしてログインします。</span><span class="sxs-lookup"><span data-stu-id="2d946-180">Log into ServiceNow as the integration user</span></span>

1. <span data-ttu-id="2d946-181">ServiceNow の [認証] ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="2d946-181">Navigate back to the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="2d946-182">右上隅にある [リンクし**ない**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2d946-182">Select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="2d946-183">インストールチェックリストから、以前に作成した統合ユーザーとして ServiceNow にログインします。</span><span class="sxs-lookup"><span data-stu-id="2d946-183">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="2d946-184">セキュリティ + コンプライアンスコネクタが ServiceNow アカウントに接続できるかどうかを確認する、ServiceNow ページの [**許可**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2d946-184">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="2d946-185">セットアップの手順を続行します。</span><span class="sxs-lookup"><span data-stu-id="2d946-185">Proceed with the setup steps.</span></span>

#### <a name="create-a-security-admin-user"></a><span data-ttu-id="2d946-186">セキュリティ管理者ユーザーを作成する</span><span class="sxs-lookup"><span data-stu-id="2d946-186">Create a security admin user</span></span>

1. <span data-ttu-id="2d946-187">Azure Active Directory のセキュリティ管理者特権を持つユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2d946-187">Create a user with security admin privileges in Azure Active Directory.</span></span> <span data-ttu-id="2d946-188">ユーザーは、インストールチェックリストから作成した統合ユーザーと同じ名前とメールアドレスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d946-188">The user needs to have the same name and email address as the integration user you created from the Installation Checklist.</span></span> <span data-ttu-id="2d946-189">ログインして接続が完了したら、セキュリティ管理者の役割を削除できます。</span><span class="sxs-lookup"><span data-stu-id="2d946-189">You can remove the security admin role once login and connection has been completed.</span></span>
2. <span data-ttu-id="2d946-190">このユーザーとして Microsoft 365 セキュリティセンターにログインし、セットアップ手順に従います。</span><span class="sxs-lookup"><span data-stu-id="2d946-190">Log in to the Microsoft 365 security center as this user and follow the setup steps.</span></span>

### <a name="ip-filtering"></a><span data-ttu-id="2d946-191">IP フィルタリング</span><span class="sxs-lookup"><span data-stu-id="2d946-191">IP filtering</span></span>

<span data-ttu-id="2d946-192">IP フィルタリングを有効にしている場合は、IP アドレスを明示的に許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d946-192">If you have enabled IP filtering, you may need to explicitly allow IP addresses.</span></span> <span data-ttu-id="2d946-193">ServiceNow で IP 範囲を許可する方法については、「 [Ip アドレスのアクセス制御](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d946-193">See [IP Address Access Control](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) for information on how to allow IP ranges in ServiceNow.</span></span> <span data-ttu-id="2d946-194">許可する IP アドレスの一覧については、「 [AZURE ip の範囲とサービスタグ-パブリッククラウド](https://www.microsoft.com/en-us/download/details.aspx?id=56519)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d946-194">See [Azure IP Ranges and Service Tags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) for a list of IP addresses to allow.</span></span>

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a><span data-ttu-id="2d946-195">インストールは完了しましたが、チケットが表示されず、共有できません</span><span class="sxs-lookup"><span data-stu-id="2d946-195">Installation is complete but don't see tickets and can't share</span></span>

<span data-ttu-id="2d946-196">インストールとセットアップの手順が完了していても、ユーザーがホームページに ServiceNow カードを表示せず、Microsoft のセキュリティスコアから ServiceNow に共有できない場合は、のhttps://security.microsoft.com/ticketProvisioning「プロビジョニング」ページの状態を確認してください。</span><span class="sxs-lookup"><span data-stu-id="2d946-196">If the installation and setup steps have been completed, but you don't see the ServiceNow cards on the home page and can't share to ServiceNow from Microsoft Secure Score, check the status of the provisioning page at https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="2d946-197">[**承認**] を選択して、ホームページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="2d946-197">Select **Authorize** and return to the home page.</span></span> <span data-ttu-id="2d946-198">カードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2d946-198">The cards should appear.</span></span>

