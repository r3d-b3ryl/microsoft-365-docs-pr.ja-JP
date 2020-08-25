---
title: ServiceNow チケットを Microsoft 365 セキュリティセンターおよびコンプライアンスセンターに統合する
description: Microsoft 365 セキュリティセンターおよびコンプライアンスセンターから ServiceNow のチケットを作成および追跡する方法について説明します。
keywords: security, Microsoft 365, M365, コンプライアンス, コンプライアンスセンター, セキュリティセンター, ServiceNow, チケット, tasks, 雪, connection
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
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: 12ac7d0a3d07749e16443e645f50de8fda185658
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2020
ms.locfileid: "46866781"
---
# <a name="integrate-servicenow-tickets-into-the-microsoft-365-security-center-and-compliance-center"></a><span data-ttu-id="0ee6c-104">ServiceNow チケットを Microsoft 365 セキュリティセンターおよびコンプライアンスセンターに統合する</span><span class="sxs-lookup"><span data-stu-id="0ee6c-104">Integrate ServiceNow tickets into the Microsoft 365 security center and compliance center</span></span>

[!include[Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="0ee6c-105">ServiceNow は、企業がエンタープライズ運用のためにデジタルワークフローを管理するのに役立つ、よく使用されるクラウドコンピューティングプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-105">ServiceNow is a popular cloud computing platform that helps companies manage digital workflows for enterprise operations.</span></span> <span data-ttu-id="0ee6c-106">現在、プラットフォームは IT ワークフロー、従業員ワークフロー、および顧客ワークフローを備えています。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-106">Their Now platform has IT workflows, employee workflows, and customer workflows.</span></span> [<span data-ttu-id="0ee6c-107">ServiceNow の詳細情報</span><span class="sxs-lookup"><span data-stu-id="0ee6c-107">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="0ee6c-108">Microsoft は、お客様が ServiceNow と提携して、IT 管理者が両方のプラットフォームでチケットとタスクを簡単に管理できるようにしています。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-108">Microsoft has partnered with ServiceNow to make it easier for IT admins to manage their tickets and tasks in both platforms.</span></span> <span data-ttu-id="0ee6c-109">[Microsoft 365 セキュリティセンター](overview-security-center.md) と [microsoft 365 コンプライアンスセンター](https://docs.microsoft.commicrosoft-365/compliance/microsoft-365-compliance-center) では、ServiceNow でチケットをネイティブに作成および追跡する機能が強化されています。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-109">[Microsoft 365 security center](overview-security-center.md) and the [Microsoft 365 compliance center](https://docs.microsoft.commicrosoft-365/compliance/microsoft-365-compliance-center) are being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span>

- [<span data-ttu-id="0ee6c-110">**セキュリティセンターで ServiceNow チケットを管理する**</span><span class="sxs-lookup"><span data-stu-id="0ee6c-110">**Manage ServiceNow tickets in the security center**</span></span>](tickets-security-center.md)
- <span data-ttu-id="0ee6c-111">**コンプライアンスセンターで ServiceNow チケットを管理する** (近日中)</span><span class="sxs-lookup"><span data-stu-id="0ee6c-111">**Manage ServiceNow tickets in the compliance center** (coming soon)</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0ee6c-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="0ee6c-112">Prerequisites</span></span>

<span data-ttu-id="0ee6c-113">Microsoft 365 セキュリティセンターまたはコンプライアンスセンターと、次のものを含む ServiceNow インスタンスへのアクセス権を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-113">Have access to the Microsoft 365 security center or compliance center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="0ee6c-114">キングストンまたはそれ以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="0ee6c-114">Kingston or higher version</span></span>
* <span data-ttu-id="0ee6c-115">管理者の HI 資格情報</span><span class="sxs-lookup"><span data-stu-id="0ee6c-115">Have admin HI credentials</span></span>
* <span data-ttu-id="0ee6c-116">ターゲットベンダーインスタンスに対する管理者権限を持っている</span><span class="sxs-lookup"><span data-stu-id="0ee6c-116">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="0ee6c-117">ServiceNow では、ユーザーが ServiceNow インスタンスに既定の設定を保持することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-117">ServiceNow recommends that users keep default settings in your ServiceNow instance.</span></span> <span data-ttu-id="0ee6c-118">カスタマイズを行うと、インストールチェックリストと Microsoft 365 セキュリティセンターとの統合を完了する際にエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-118">Having customizations could cause errors when completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="0ee6c-119">データ交換</span><span class="sxs-lookup"><span data-stu-id="0ee6c-119">Data exchange</span></span>

<span data-ttu-id="0ee6c-120">Microsoft 365 セキュリティセンターまたはコンプライアンスセンターを ServiceNow に接続すると、Microsoft は次の追加データを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-120">When you connect the Microsoft 365 security center or compliance center to ServiceNow, Microsoft receives the following additional data:</span></span>

* <span data-ttu-id="0ee6c-121">ServiceNow インスタンス名</span><span class="sxs-lookup"><span data-stu-id="0ee6c-121">ServiceNow instance name</span></span>
* <span data-ttu-id="0ee6c-122">ServiceNow クライアント ID</span><span class="sxs-lookup"><span data-stu-id="0ee6c-122">ServiceNow client ID</span></span>
* <span data-ttu-id="0ee6c-123">ServiceNow クライアントシークレット</span><span class="sxs-lookup"><span data-stu-id="0ee6c-123">ServiceNow client secret</span></span>
* <span data-ttu-id="0ee6c-124">ServiceNow アクセス & 更新トークン</span><span class="sxs-lookup"><span data-stu-id="0ee6c-124">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="0ee6c-125">Microsoft 365 セキュリティセンターまたはコンプライアンスセンターから ServiceNow チケットを作成すると、次のデータが ServiceNow に送信されます。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-125">When you create a ServiceNow ticket from the Microsoft 365 security center or compliance center, the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="0ee6c-126">チケット作成を開始するユーザー ID</span><span class="sxs-lookup"><span data-stu-id="0ee6c-126">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="0ee6c-127">タスク名</span><span class="sxs-lookup"><span data-stu-id="0ee6c-127">Task name</span></span>
* <span data-ttu-id="0ee6c-128">タスクの説明</span><span class="sxs-lookup"><span data-stu-id="0ee6c-128">Task description</span></span>
* <span data-ttu-id="0ee6c-129">優先度</span><span class="sxs-lookup"><span data-stu-id="0ee6c-129">Priority</span></span>
* <span data-ttu-id="0ee6c-130">期限</span><span class="sxs-lookup"><span data-stu-id="0ee6c-130">Due date</span></span>
* <span data-ttu-id="0ee6c-131">推奨ソース (ユーザーの推奨事項または Microsoft 推奨)</span><span class="sxs-lookup"><span data-stu-id="0ee6c-131">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="0ee6c-132">推奨カテゴリ (デバイス、データ、アプリ、Id、インフラストラクチャ)</span><span class="sxs-lookup"><span data-stu-id="0ee6c-132">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-to-servicenow"></a><span data-ttu-id="0ee6c-133">ServiceNow への接続</span><span class="sxs-lookup"><span data-stu-id="0ee6c-133">Connect to ServiceNow</span></span>

<span data-ttu-id="0ee6c-134">[Microsoft 365 セキュリティセンターで servicenow チケットを作成および追跡](tickets-security-center.md)するには、servicenow に接続する方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-134">Go to [Create and track ServiceNow tickets in the Microsoft 365 security center](tickets-security-center.md) to learn how to connect to ServiceNow.</span></span> <span data-ttu-id="0ee6c-135">Microsoft 365 コンプライアンスセンターからの接続は近日に予定されています。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-135">Connecting from the Microsoft 365 compliance center is coming soon.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="0ee6c-136">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="0ee6c-136">Troubleshooting</span></span>

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="0ee6c-137">インストールチェックリストの最初のステップでエラーが表示される (OAuth の作成)</span><span class="sxs-lookup"><span data-stu-id="0ee6c-137">You receive an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="0ee6c-138">**エラーメッセージ**: 範囲 ' x_mioms_m365ticket ' から ' oauth_entity ' に対する読み取り操作が拒否されました。テーブルのスコープ間のアクセスポリシーが原因です。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-138">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused because of the table's cross-scope access policy</span></span>

<span data-ttu-id="0ee6c-139">アプリでは、ServiceNow インスタンスの管理者が OAuth エンティティを作成して読み取ることができると想定しています。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-139">The app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="0ee6c-140">このエラーは、OAuth エンティティを作成または読み取ることができるユーザーを制限する ServiceNow のインスタンスのカスタマイズによって発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-140">This error could be caused by a customization in your instance of ServiceNow that restricts who can create or read OAuth entities.</span></span>

<span data-ttu-id="0ee6c-141">**ServiceNow では、ユーザーが既定の機能を維持することをお勧めします。**</span><span class="sxs-lookup"><span data-stu-id="0ee6c-141">**ServiceNow recommends that users keep default functionality.**</span></span>

<span data-ttu-id="0ee6c-142">"Application レジストリ" テーブルの構成を既定に設定します。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-142">Set the "application registries" table configurations to default:</span></span>

* <span data-ttu-id="0ee6c-143">Label = Application Registeries</span><span class="sxs-lookup"><span data-stu-id="0ee6c-143">Label = Application Registeries</span></span>
* <span data-ttu-id="0ee6c-144">Name = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="0ee6c-144">Name = oauth_entity</span></span>
* <span data-ttu-id="0ee6c-145">= すべてのアプリケーションスコープからアクセス可能</span><span class="sxs-lookup"><span data-stu-id="0ee6c-145">Accessible from = All application scopes</span></span>
* <span data-ttu-id="0ee6c-146">読み取り可能 = チェックボックスが選択されている</span><span class="sxs-lookup"><span data-stu-id="0ee6c-146">Can read = check box selected</span></span>

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="0ee6c-147">Microsoft 365 Security & コンプライアンスコネクタ用に作成された OAuth エンティティを検証する方法</span><span class="sxs-lookup"><span data-stu-id="0ee6c-147">How to validate the OAuth entity created for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="0ee6c-148">ServiceNow で、[アプリケーション**レジストリ] テーブル (メニュー > System OAuth > アプリケーションレジストリ**) に移動します。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-148">Go to application registries table (**Menu > System OAuth > Application Registry**) in ServiceNow.</span></span> <span data-ttu-id="0ee6c-149">自分で作成した OAuth エンティティを、割り当てた名前で検索します。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-149">Find the OAuth entity created by you, with the name that you assigned it.</span></span>

### <a name="signing-in-as-the-integration-user"></a><span data-ttu-id="0ee6c-150">統合ユーザーとしてのサインイン</span><span class="sxs-lookup"><span data-stu-id="0ee6c-150">Signing in as the integration user</span></span>

<span data-ttu-id="0ee6c-151">Microsoft 365 セキュリティセンターと ServiceNow 間の接続を承認する前に、インストール手順で作成した統合ユーザーのサインインとパスワードを使用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-151">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user sign in and password you created in the installation steps.</span></span> <span data-ttu-id="0ee6c-152">個人の資格情報は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-152">Don't use your personal credentials.</span></span>

1. <span data-ttu-id="0ee6c-153">ServiceNow の [認証] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-153">Go the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="0ee6c-154">個人の資格情報を使用してサインインしている場合は、右上隅にある [リンクし **ない** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-154">If you're signed in with your personal credentials, select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="0ee6c-155">インストールチェックリストから、以前に作成した統合ユーザーとして ServiceNow にサインインします。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-155">Sign in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="0ee6c-156">セキュリティ + コンプライアンスコネクタが ServiceNow アカウントに接続できるかどうかを確認する、ServiceNow ページの [ **許可** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-156">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="0ee6c-157">セットアップの手順を続行します。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-157">Continue with the setup steps.</span></span>

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="0ee6c-158">Microsoft 365 Security & コンプライアンスコネクタのインストールチェックリストで作成した統合ユーザーを検証する方法</span><span class="sxs-lookup"><span data-stu-id="0ee6c-158">How to validate the Integration User created with the installation checklist for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="0ee6c-159">ServiceNow でユーザーテーブル **(メニュー > ユーザー管理 > ユーザー**) に移動し、自分で作成した統合ユーザーを割り当てた名前で検索します。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-159">Go to Users Table **(Menu > User Administration > Users**) in ServiceNow and find the Integration user created by you, with the name that you assigned it.</span></span>

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a><span data-ttu-id="0ee6c-160">お客様の会社では、シングルサインオンが有効になっています。これにより、Microsoft 365 セキュリティセンターから ServiceNow に接続できなくなります。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-160">Your company has single sign-on enabled which prevents you from connecting to ServiceNow through the Microsoft 365 security center</span></span>

<span data-ttu-id="0ee6c-161">会社でシングルサインオンが有効になっていて、エラーが発生するかサインインに失敗した場合は、2つのソリューションのいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-161">If your company has enabled single sign-on and you receive an error or sign in is unsuccessful, follow one of the two solutions.</span></span>

#### <a name="sign-in-to-servicenow-as-the-integration-user"></a><span data-ttu-id="0ee6c-162">統合ユーザーとして ServiceNow にサインインする</span><span class="sxs-lookup"><span data-stu-id="0ee6c-162">Sign in to ServiceNow as the integration user</span></span>

1. <span data-ttu-id="0ee6c-163">ServiceNow の [認証] ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-163">Navigate back to the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="0ee6c-164">右上隅にある [リンクし **ない** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-164">Select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="0ee6c-165">インストールチェックリストから、以前に作成した統合ユーザーとして ServiceNow にサインインします。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-165">Sign in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="0ee6c-166">セキュリティ + コンプライアンスコネクタが ServiceNow アカウントに接続できるかどうかを確認する、ServiceNow ページの [ **許可** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-166">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="0ee6c-167">セットアップの手順を続行します。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-167">Continue with the setup steps.</span></span>

#### <a name="create-a-security-admin-user"></a><span data-ttu-id="0ee6c-168">セキュリティ管理者ユーザーを作成する</span><span class="sxs-lookup"><span data-stu-id="0ee6c-168">Create a security admin user</span></span>

1. <span data-ttu-id="0ee6c-169">Azure Active Directory のセキュリティ管理者特権を持つユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-169">Create a user with security admin privileges in Azure Active Directory.</span></span> <span data-ttu-id="0ee6c-170">ユーザーは、インストールチェックリストから作成した統合ユーザーと同じ名前とメールアドレスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-170">The user needs to have the same name and email address as the integration user you created from the Installation Checklist.</span></span> <span data-ttu-id="0ee6c-171">サインインして接続が完了したら、セキュリティ管理者の役割を削除できます。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-171">You can remove the security admin role once sign-in and connection has been completed.</span></span>
2. <span data-ttu-id="0ee6c-172">このユーザーとして Microsoft 365 セキュリティセンターにサインインし、セットアップ手順に従います。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-172">Sign in to the Microsoft 365 security center as this user and follow the setup steps.</span></span>

### <a name="ip-filtering"></a><span data-ttu-id="0ee6c-173">IP フィルタリング</span><span class="sxs-lookup"><span data-stu-id="0ee6c-173">IP filtering</span></span>

<span data-ttu-id="0ee6c-174">IP フィルタリングを有効にしている場合は、IP アドレスを明示的に許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-174">If you have enabled IP filtering, you may need to explicitly allow IP addresses.</span></span> <span data-ttu-id="0ee6c-175">ServiceNow で IP 範囲を許可する方法については、「 [Ip アドレスのアクセス制御](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-175">See [IP Address Access Control](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) for information on how to allow IP ranges in ServiceNow.</span></span> <span data-ttu-id="0ee6c-176">許可する IP アドレスの一覧については、「 [AZURE ip の範囲とサービスタグ-パブリッククラウド](https://www.microsoft.com/en-us/download/details.aspx?id=56519) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-176">See [Azure IP Ranges and Service Tags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) for a list of IP addresses to allow.</span></span>

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a><span data-ttu-id="0ee6c-177">インストールは完了しましたが、チケットが表示されず、共有できません</span><span class="sxs-lookup"><span data-stu-id="0ee6c-177">Installation is complete but don't see tickets and can't share</span></span>

<span data-ttu-id="0ee6c-178">インストールとセットアップの手順が完了していても、ユーザーがホームページに ServiceNow カードを表示せず、Microsoft のセキュリティスコアから ServiceNow に共有できない場合は、の「プロビジョニング」ページの状態を確認して https://security.microsoft.com/ticketProvisioning ください。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-178">If the installation and setup steps have been completed, but you don't see the ServiceNow cards on the home page and can't share to ServiceNow from Microsoft Secure Score, check the status of the provisioning page at https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="0ee6c-179">[ **承認** ] を選択して、ホームページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-179">Select **Authorize** and return to the home page.</span></span> <span data-ttu-id="0ee6c-180">カードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ee6c-180">The cards should appear.</span></span>

## <a name="resources"></a><span data-ttu-id="0ee6c-181">リソース</span><span class="sxs-lookup"><span data-stu-id="0ee6c-181">Resources</span></span>

- [<span data-ttu-id="0ee6c-182">セキュリティセンターで ServiceNow チケットを管理する</span><span class="sxs-lookup"><span data-stu-id="0ee6c-182">Manage ServiceNow tickets in the security center</span></span>](tickets-security-center.md)