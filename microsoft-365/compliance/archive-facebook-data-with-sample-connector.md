---
title: コネクタをセットアップしてFacebook のデータをアーカイブする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: Microsoft 365 コンプライアンス センター&を使用して、Facebook Business ページから Microsoft 365 に & アーカイブ データをインポートする方法について説明します。
ms.openlocfilehash: 616466a3af83c1558184526aa463f68c10ef9e70
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921737"
---
# <a name="set-up-a-connector-to-archive-facebook-data-preview"></a><span data-ttu-id="81232-103">Facebook データをアーカイブするコネクタをセットアップする (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="81232-103">Set up a connector to archive Facebook data (preview)</span></span>

<span data-ttu-id="81232-104">Microsoft 365 コンプライアンス センターのコネクタを使用して、Facebook Business ページから Microsoft 365 にデータをインポートおよびアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="81232-104">Use a connector in the Microsoft 365 compliance center to import and archive data from Facebook Business pages to Microsoft 365.</span></span> <span data-ttu-id="81232-105">コネクタをセットアップして構成した後、(スケジュールに基づいて) Facebook Business ページに接続し、Facebook アイテムのコンテンツを電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="81232-105">After you set up and configure the connector, it connects to the Facebook Business page (on a scheduled basis), converts the content of Facebook items to an email message format, and then imports those items to a mailbox in Microsoft 365.</span></span>

<span data-ttu-id="81232-106">Facebook データをインポートした後、訴訟ホールド、コンテンツ検索、In-Place アーカイブ、監査、通信コンプライアンス、Microsoft 365 保持ポリシーなどの Microsoft 365 コンプライアンス機能を Facebook データに適用できます。</span><span class="sxs-lookup"><span data-stu-id="81232-106">After the Facebook data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, Communication compliance, and Microsoft 365 retention policies to the Facebook data.</span></span> <span data-ttu-id="81232-107">たとえば、メールボックスが訴訟ホールドに置かれたり、アイテム保持ポリシーに割り当てられたりすると、Facebook データは保持されます。</span><span class="sxs-lookup"><span data-stu-id="81232-107">For example, when a mailbox is placed on Litigation Hold or assigned to a retention policy, the Facebook data is preserved.</span></span> <span data-ttu-id="81232-108">コンテンツ検索を使用してサード パーティのデータを検索するか、Facebook データが保存されているメールボックスを高度な電子情報開示ケースの保管担当者に関連付けできます。</span><span class="sxs-lookup"><span data-stu-id="81232-108">You can search third-party data using Content Search or associate the mailbox where the Facebook data is stored with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="81232-109">コネクタを使用して Microsoft 365 で Facebook データをインポートおよびアーカイブすると、組織が政府および規制ポリシーに準拠しつ付けるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="81232-109">Using a connector to import and archive Facebook data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a><span data-ttu-id="81232-110">Facebook Business ページのコネクタを設定するための前提条件</span><span class="sxs-lookup"><span data-stu-id="81232-110">Prerequisites for setting up a connector for Facebook Business pages</span></span>

<span data-ttu-id="81232-111">Microsoft 365 コンプライアンス センターでコネクタをセットアップして構成し、組織の Facebook Business ページからデータをインポートおよびアーカイブするには、以下の前提条件を満たしてください。</span><span class="sxs-lookup"><span data-stu-id="81232-111">Complete the following prerequisites before you can set up and configure a connector in the Microsoft 365 compliance center to import and archive data from your organization's Facebook Business pages.</span></span> 

- <span data-ttu-id="81232-112">組織のビジネス ページ用の Facebook アカウントが必要です (コネクタをセットアップする場合は、このアカウントにサインインする必要があります)。</span><span class="sxs-lookup"><span data-stu-id="81232-112">You need a Facebook account for your organization's business pages (you need to sign in to this account when setting up the connector).</span></span> <span data-ttu-id="81232-113">現時点では、Facebook Business ページからのみデータをアーカイブできます。個々の Facebook プロファイルからデータをアーカイブできない。</span><span class="sxs-lookup"><span data-stu-id="81232-113">Currently, you can only archive data from Facebook Business pages; you can't archive data from individual Facebook profiles.</span></span>

- <span data-ttu-id="81232-114">組織に有効な Azure サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="81232-114">Your organization must have a valid Azure subscription.</span></span> <span data-ttu-id="81232-115">既存の Azure サブスクリプションがない場合は、次のいずれかのオプションにサインアップできます。</span><span class="sxs-lookup"><span data-stu-id="81232-115">If you don't have an existing Azure subscription, you can sign up for one of these options:</span></span>

    - [<span data-ttu-id="81232-116">無料の 1 年間 Azure サブスクリプションにサインアップする</span><span class="sxs-lookup"><span data-stu-id="81232-116">Sign up for a free one year Azure subscription</span></span>](https://azure.microsoft.com/free)

    - [<span data-ttu-id="81232-117">Pay-As-Go Azure サブスクリプションにサインアップする</span><span class="sxs-lookup"><span data-stu-id="81232-117">Sign up for a Pay-As-You-Go Azure subscription</span></span>](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > <span data-ttu-id="81232-118">Microsoft 365 サブスクリプションに含まれる無料の Azure [Active Directory](use-your-free-azure-ad-subscription-in-office-365.md) サブスクリプションは、セキュリティ コンプライアンス センター&サポートしていません。</span><span class="sxs-lookup"><span data-stu-id="81232-118">The [free Azure Active Directory subscription](use-your-free-azure-ad-subscription-in-office-365.md) that's included with your Microsoft 365 subscription doesn't support the connectors in the Security & Compliance Center.</span></span>

- <span data-ttu-id="81232-119">Facebook Business ページのコネクタは、1 日に合計 200,000 アイテムをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="81232-119">The connector for Facebook Business pages can import a total of 200,000 items in a single day.</span></span> <span data-ttu-id="81232-120">1 日に 200,000 件を超える Facebook Business アイテムがある場合、それらのアイテムはいずれも Microsoft 365 にインポートされません。</span><span class="sxs-lookup"><span data-stu-id="81232-120">If there are more than 200,000 Facebook Business items in a day, none of those items will be imported to Microsoft 365.</span></span>

- <span data-ttu-id="81232-121">Microsoft 365 コンプライアンス センター (手順 5) でカスタム コネクタを設定するユーザーには、Exchange Online のメールボックスインポートエクスポートの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="81232-121">The user who sets up the custom connector in the Microsoft 365 compliance center (in Step 5) must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="81232-122">既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="81232-122">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="81232-123">Exchange Online の [組織の管理] 役割グループにメールボックスインポートエクスポート役割を追加できます。</span><span class="sxs-lookup"><span data-stu-id="81232-123">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="81232-124">または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="81232-124">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="81232-125">詳細については、「Exchange Online[で役割](/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の記事の「役割グループの作成」または「役割グループの変更」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="81232-125">For more information, see the  [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="81232-126">手順 1: Azure Active Directory でアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="81232-126">Step 1: Create an app in Azure Active Directory</span></span>

<span data-ttu-id="81232-127">最初の手順は、Azure Active Directory (AAD) に新しいアプリを登録します。</span><span class="sxs-lookup"><span data-stu-id="81232-127">The first step is to register a new app in Azure Active Directory (AAD).</span></span> <span data-ttu-id="81232-128">このアプリは、Facebook コネクタの手順 4 と手順 5 で実装する Web アプリ リソースに対応します。</span><span class="sxs-lookup"><span data-stu-id="81232-128">This app corresponds to the web app resource that you implement in Step 4 and Step 5 for the Facebook connector.</span></span> 

<span data-ttu-id="81232-129">手順については、「Azure Active Directory で [アプリを作成する」を参照してください](deploy-facebook-connector.md#step-1-create-an-app-in-azure-active-directory)。</span><span class="sxs-lookup"><span data-stu-id="81232-129">For step-by-step instructions, see [Create an app in Azure Active Directory](deploy-facebook-connector.md#step-1-create-an-app-in-azure-active-directory).</span></span>

<span data-ttu-id="81232-130">この手順が完了すると (前の手順を使用して)、次の情報をテキスト ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="81232-130">During the completion of this step (by using the previous step-by-step instructions), you'll save the following information to a text file.</span></span> <span data-ttu-id="81232-131">これらの値は、展開プロセスの後の手順で使用されます。</span><span class="sxs-lookup"><span data-stu-id="81232-131">These values are used in later steps in the deployment process.</span></span>

- <span data-ttu-id="81232-132">AAD アプリケーション ID</span><span class="sxs-lookup"><span data-stu-id="81232-132">AAD application ID</span></span>

- <span data-ttu-id="81232-133">AAD アプリケーション シークレット</span><span class="sxs-lookup"><span data-stu-id="81232-133">AAD application secret</span></span>

- <span data-ttu-id="81232-134">テナント ID</span><span class="sxs-lookup"><span data-stu-id="81232-134">Tenant Id</span></span>

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="81232-135">手順 2: GitHub から Azure アカウントにコネクタ Web サービスを展開する</span><span class="sxs-lookup"><span data-stu-id="81232-135">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

<span data-ttu-id="81232-136">次の手順では、Facebook API を使用して Facebook アカウントに接続し、データを抽出して Microsoft 365 にインポートできる Facebook Business ページ コネクタ アプリのソース コードを展開します。</span><span class="sxs-lookup"><span data-stu-id="81232-136">The next step is to deploy the source code for the Facebook Business pages connector app that will use the Facebook API to connect to your Facebook account and extract data so you can import it to Microsoft 365.</span></span> <span data-ttu-id="81232-137">組織に展開する Facebook コネクタは、この手順で作成した Azure Storage の場所に、Facebook Business ページからアイテムをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="81232-137">The Facebook connector that you deploy for your organization will upload the items from your Facebook Business pages to the Azure Storage location that is created in this step.</span></span> <span data-ttu-id="81232-138">Microsoft 365 コンプライアンス センター (手順 5) で Facebook ビジネス ページ コネクタを作成すると、インポート サービスは、Azure Storage の場所から Microsoft 365 組織のメールボックスに Facebook ビジネス ページ データをコピーします。</span><span class="sxs-lookup"><span data-stu-id="81232-138">After you create a Facebook business pages connector in the Microsoft 365 compliance center (in Step 5), the Import service will copy the Facebook business pages data from the Azure Storage location to a mailbox in your Microsoft 365 organization.</span></span> <span data-ttu-id="81232-139">「前提条件」セクションで [説明したように](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages) 、Azure ストレージ アカウントを作成するには、有効な Azure サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="81232-139">As previous explained in the [Prerequisites](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages) section, you must have a valid Azure subscription to create an Azure Storage account.</span></span>

<span data-ttu-id="81232-140">詳細な手順については、「コネクタ Web サービスを GitHub から Azure アカウントに展開 [する」を参照してください](deploy-facebook-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)。</span><span class="sxs-lookup"><span data-stu-id="81232-140">For step-by-step instructions, see [Deploy the connector web service from GitHub to your Azure account](deploy-facebook-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account).</span></span>

<span data-ttu-id="81232-141">この手順を完了する手順では、次の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="81232-141">In the step-by-step instructions to complete this step, you'll provide the following information:</span></span>

- <span data-ttu-id="81232-142">APISecretKey: この手順の完了時に、このシークレットを作成します。</span><span class="sxs-lookup"><span data-stu-id="81232-142">APISecretKey: You create this secret during the completion of this step.</span></span> <span data-ttu-id="81232-143">手順 5 で使用します。</span><span class="sxs-lookup"><span data-stu-id="81232-143">It's used in Step 5.</span></span>

- <span data-ttu-id="81232-144">TenantId: 手順 1 の Azure Active Directory で Facebook コネクタ アプリを作成した後にコピーした Microsoft 365 組織のテナント ID。</span><span class="sxs-lookup"><span data-stu-id="81232-144">TenantId: The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 1.</span></span>

<span data-ttu-id="81232-145">この手順を完了した後は、必ず Azure アプリ サービスの URL (など) をコピーしてください https://fbconnector.azurewebsites.net) 。</span><span class="sxs-lookup"><span data-stu-id="81232-145">After completing this step, be sure to copy the Azure app service URL (for example, https://fbconnector.azurewebsites.net).</span></span> <span data-ttu-id="81232-146">この URL を使用して、手順 3、手順 4、および手順 5) を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81232-146">You need to use this URL to complete Step 3, Step 4, and Step 5).</span></span>

## <a name="step-3-register-the-web-app-on-facebook"></a><span data-ttu-id="81232-147">手順 3: Facebook に Web アプリを登録する</span><span class="sxs-lookup"><span data-stu-id="81232-147">Step 3: Register the web app on Facebook</span></span>

<span data-ttu-id="81232-148">次の手順では、Facebook で新しいアプリを作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="81232-148">The next step is to create and configure a new app on Facebook.</span></span> <span data-ttu-id="81232-149">手順 5 で作成した Facebook ビジネス ページ コネクタは、Facebook Web アプリを使用して Facebook API と対話し、組織の Facebook Business ページからデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="81232-149">The Facebook business pages connector that you create in Step 5 uses the Facebook web app to interact with the Facebook API to obtain data from your organization's Facebook Business pages.</span></span>

<span data-ttu-id="81232-150">手順については、「Facebook アプリの登録 [」を参照してください](deploy-facebook-connector.md#step-3-register-the-facebook-app)。</span><span class="sxs-lookup"><span data-stu-id="81232-150">For step-by-step instructions, see [Register the Facebook app](deploy-facebook-connector.md#step-3-register-the-facebook-app).</span></span>

<span data-ttu-id="81232-151">この手順の完了時 (手順に従って)、次の情報をテキスト ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="81232-151">During the completion of this step (by following the step-by-step instructions), you save the following information to a text file.</span></span> <span data-ttu-id="81232-152">これらの値は、手順 4 で Facebook コネクタ アプリを構成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="81232-152">These values are used to configure the Facebook connector app in Step 4.</span></span>

- <span data-ttu-id="81232-153">Facebook アプリケーション ID</span><span class="sxs-lookup"><span data-stu-id="81232-153">Facebook application ID</span></span>

- <span data-ttu-id="81232-154">Facebook アプリケーション シークレット</span><span class="sxs-lookup"><span data-stu-id="81232-154">Facebook application secret</span></span>

- <span data-ttu-id="81232-155">Facebook Webhooks のトークンの確認</span><span class="sxs-lookup"><span data-stu-id="81232-155">Facebook webhooks verify token</span></span>

## <a name="step-4-configure-the-facebook-connector-app"></a><span data-ttu-id="81232-156">手順 4: Facebook コネクタ アプリを構成する</span><span class="sxs-lookup"><span data-stu-id="81232-156">Step 4: Configure the Facebook connector app</span></span>

<span data-ttu-id="81232-157">次の手順では、手順 1 で Azure Web アプリ リソースを作成した際にアップロードした Facebook コネクタ アプリに構成設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="81232-157">The next step is to add configuration settings to the Facebook connector app that you uploaded when you created the Azure web app resource in Step 1.</span></span> <span data-ttu-id="81232-158">これを行うには、コネクタ アプリのホーム ページに移動して構成します。</span><span class="sxs-lookup"><span data-stu-id="81232-158">You do this by going to the home page of your connector app and configuring it.</span></span>

<span data-ttu-id="81232-159">詳細な手順については [、「Configure the Facebook Connector app」を参照してください](archive-facebook-data-with-sample-connector.md#step-4-configure-the-facebook-connector-app)。</span><span class="sxs-lookup"><span data-stu-id="81232-159">For step-by-step instructions, see [Configure the Facebook connector app](archive-facebook-data-with-sample-connector.md#step-4-configure-the-facebook-connector-app).</span></span>

<span data-ttu-id="81232-160">この手順の完了時 (手順に従って)、次の情報 (前の手順を完了した後にテキスト ファイルにコピーした情報) を指定します。</span><span class="sxs-lookup"><span data-stu-id="81232-160">During the completion of this step (by following the step-by-step instructions), you provide the following information (that you've copied to a text file after completing the previous steps):</span></span>

- <span data-ttu-id="81232-161">Facebook アプリケーション ID (手順 3 で取得)</span><span class="sxs-lookup"><span data-stu-id="81232-161">Facebook application ID (obtained in Step 3)</span></span>

- <span data-ttu-id="81232-162">Facebook アプリケーション シークレット (手順 3 で取得)</span><span class="sxs-lookup"><span data-stu-id="81232-162">Facebook application secret (obtained in Step 3)</span></span>

- <span data-ttu-id="81232-163">Facebook Webhooks verify token (手順 3 で取得)</span><span class="sxs-lookup"><span data-stu-id="81232-163">Facebook webhooks verify token (obtained in Step 3)</span></span>

- <span data-ttu-id="81232-164">Azure Active Directory アプリケーション ID (手順 1 で取得した AAD アプリケーション ID)</span><span class="sxs-lookup"><span data-stu-id="81232-164">Azure Active Directory application ID (the AAD application ID obtained in Step 1)</span></span>

- <span data-ttu-id="81232-165">Azure Active Directory アプリケーション シークレット (手順 1 で取得した AAD アプリケーション シークレット)</span><span class="sxs-lookup"><span data-stu-id="81232-165">Azure Active Directory application secret (the AAD application secret obtained in Step 1)</span></span>

## <a name="step-5-set-up-a-facebook-business-pages-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="81232-166">手順 5: Microsoft 365 コンプライアンス センターで Facebook Business ページ コネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="81232-166">Step 5: Set up a Facebook Business pages connector in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="81232-167">最後の手順は、Microsoft 365 コンプライアンス センターでコネクタをセットアップし、Facebook Business ページから Microsoft 365 の指定されたメールボックスにデータをインポートすることです。</span><span class="sxs-lookup"><span data-stu-id="81232-167">The final step is to set up the connector in the Microsoft 365 compliance center that will import data from your Facebook Business pages to a specified mailbox in Microsoft 365.</span></span> <span data-ttu-id="81232-168">この手順を完了すると、Microsoft 365 インポート サービスは、Facebook Business ページから Microsoft 365 へのデータのインポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="81232-168">After you complete this step, the Microsoft 365 Import service will start importing data from your Facebook Business pages to Microsoft 365.</span></span>

<span data-ttu-id="81232-169">手順については、「 [手順 5: Microsoft 365](deploy-facebook-connector.md#step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center)コンプライアンス センターで Facebook コネクタをセットアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81232-169">For step-by-step instructions, see [Step 5: Set up a Facebook connector in the Microsoft 365 compliance center](deploy-facebook-connector.md#step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center).</span></span> 

<span data-ttu-id="81232-170">この手順の完了時 (手順の手順に従って) は、次の情報 (手順の完了後にテキスト ファイルにコピーした情報) を提供します。</span><span class="sxs-lookup"><span data-stu-id="81232-170">During the completion of this step (by following the step-by-step instructions), you provide the following information (that you've copied to a text file after completing the steps).</span></span>

- <span data-ttu-id="81232-171">AAD アプリケーション ID (手順 1 で取得)</span><span class="sxs-lookup"><span data-stu-id="81232-171">AAD application ID (obtained in Step 1)</span></span>

- <span data-ttu-id="81232-172">Azure アプリ サービスの URL (手順 1 で取得されます。たとえば、 https://fbconnector.azurewebsites.net)</span><span class="sxs-lookup"><span data-stu-id="81232-172">Azure app service URL (obtained in Step 1; for example, https://fbconnector.azurewebsites.net)</span></span>

- <span data-ttu-id="81232-173">APISecretKey (手順 2 で作成した)</span><span class="sxs-lookup"><span data-stu-id="81232-173">APISecretKey (that you created in Step 2)</span></span>