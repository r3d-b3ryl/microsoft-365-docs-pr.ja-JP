---
title: コネクタセットアップしてTwitter のデータをアーカイブする
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
description: 管理者がネイティブ コネクタをセットアップして使用して Twitter データを Microsoft 365 にインポートする方法について説明します。
ms.openlocfilehash: 5b35259985664ac47b9d1f6265c8ca4282a4cd31
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790065"
---
# <a name="set-up-a-connector-to-archive-twitter-data-preview"></a><span data-ttu-id="d329f-103">コネクタを設定して Twitter データをアーカイブする (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="d329f-103">Set up a connector to archive Twitter data (preview)</span></span>

<span data-ttu-id="d329f-104">Microsoft 365 コンプライアンス センターのコネクタを使用して、Twitter から Microsoft 365 にデータをインポートしてアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="d329f-104">Use a connector in the Microsoft 365 compliance center to import and archive data from Twitter to Microsoft 365.</span></span> <span data-ttu-id="d329f-105">コネクタを設定して構成した後、組織の Twitter アカウントに (スケジュールに基づいて) 接続し、アイテムのコンテンツを電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="d329f-105">After you set up and configure the connector, it connects to your organization's Twitter account (on a scheduled basis), converts the content of an item to an email message format, and then imports those items to a mailbox in Microsoft 365.</span></span>

<span data-ttu-id="d329f-106">Twitter データをインポートした後、訴訟ホールド、コンテンツ検索、In-Place アーカイブ、監査、Microsoft 365 アイテム保持ポリシーなどの Microsoft 365 コンプライアンス機能を Twitter データに適用できます。</span><span class="sxs-lookup"><span data-stu-id="d329f-106">After the Twitter data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Microsoft 365 retention policies to the Twitter data.</span></span> <span data-ttu-id="d329f-107">たとえば、メールボックスが訴訟ホールドの対象にされた場合、またはアイテム保持ポリシーに割り当てられた場合、Twitter データは保持されます。</span><span class="sxs-lookup"><span data-stu-id="d329f-107">For example, when a mailbox is placed on Litigation Hold or assigned to a retention policy, the Twitter data is preserved.</span></span> <span data-ttu-id="d329f-108">コンテンツ検索を使用してサード パーティのデータを検索したり、Twitter データが保存されているメールボックスを Advanced eDiscovery ケースの保管担当者に関連付けできます。</span><span class="sxs-lookup"><span data-stu-id="d329f-108">You can search third-party data using Content Search or associate the mailbox where the Twitter data is stored with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="d329f-109">コネクタを使用して Microsoft 365 で Twitter データをインポートおよびアーカイブすると、組織が政府や規制のポリシーに準拠しつながっているのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d329f-109">Using a connector to import and archive Twitter data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

<span data-ttu-id="d329f-110">Twitter データをインポートした後、メールボックスに保存されているデータに、訴訟ホールド、コンテンツ検索、In-Place アーカイブ、監査、通信コンプライアンス、Microsoft 365 アイテム保持ポリシーなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="d329f-110">After Twitter data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, Communication compliance, and Microsoft 365 retention policies to the data stored in the mailbox.</span></span> <span data-ttu-id="d329f-111">たとえば、コンテンツ検索を使用して Twitter データを検索したり、Advanced eDiscovery ケースでデータが保管されているメールボックスを保管担当者に関連付けできます。</span><span class="sxs-lookup"><span data-stu-id="d329f-111">For example, you can search Twitter data using Content Search or associate the mailbox where the data is stored with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="d329f-112">コネクタを使用して Microsoft 365 で Twitter データをインポートおよびアーカイブすると、組織が政府や規制のポリシーに準拠しつながっているのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d329f-112">Using a connector to import and archive Twitter data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="d329f-113">コネクタを設定する前に</span><span class="sxs-lookup"><span data-stu-id="d329f-113">Before you set up a connector</span></span>

<span data-ttu-id="d329f-114">Microsoft 365 コンプライアンス センターでコネクタをセットアップして構成し、組織の Twitter アカウントからデータをインポートおよびアーカイブする前に、次の前提条件を満たします。</span><span class="sxs-lookup"><span data-stu-id="d329f-114">Complete the following prerequisites before you can set up and configure a connector in the Microsoft 365 compliance center to import and archive data from your organization's Twitter account.</span></span>

- <span data-ttu-id="d329f-115">組織用の Twitter アカウントが必要です。コネクタを設定するときに、このアカウントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d329f-115">You need a Twitter account for your organization; you need to sign in to this account when setting up the connector.</span></span>

- <span data-ttu-id="d329f-116">組織には有効な Azure サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="d329f-116">Your organization must have a valid Azure subscription.</span></span> <span data-ttu-id="d329f-117">既存の Azure サブスクリプションがない場合は、次のいずれかのオプションにサインアップできます。</span><span class="sxs-lookup"><span data-stu-id="d329f-117">If you don't have an existing Azure subscription, you can sign up for one of these options:</span></span>

    - [<span data-ttu-id="d329f-118">1 年間無料の Azure サブスクリプションにサインアップする</span><span class="sxs-lookup"><span data-stu-id="d329f-118">Sign up for a free one year Azure subscription</span></span>](https://azure.microsoft.com/free) 

    - [<span data-ttu-id="d329f-119">Pay-As-You-Go Azure サブスクリプションにサインアップする</span><span class="sxs-lookup"><span data-stu-id="d329f-119">Sign up for a Pay-As-You-Go Azure subscription</span></span>](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > <span data-ttu-id="d329f-120">Microsoft 365 サブスクリプションに含まれている無料の [Azure Active Directory](use-your-free-azure-ad-subscription-in-office-365.md) サブスクリプションは、セキュリティ/コンプライアンス センターのコネクタ&サポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d329f-120">The [free Azure Active Directory subscription](use-your-free-azure-ad-subscription-in-office-365.md) that's included with your Microsoft 365 subscription doesn't support the connectors in the Security & Compliance Center.</span></span>

- <span data-ttu-id="d329f-121">Twitter コネクタは、1 日に合計 200,000 アイテムをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="d329f-121">The Twitter connector can import a total of 200,000 items in a single day.</span></span> <span data-ttu-id="d329f-122">1 日に 200,000 を超える Twitter アイテムがある場合、それらのアイテムは Microsoft 365 にインポートされません。</span><span class="sxs-lookup"><span data-stu-id="d329f-122">If there are more than 200,000 Twitter items in a day, none of those items will be imported to Microsoft 365.</span></span>

- <span data-ttu-id="d329f-123">Microsoft 365 コンプライアンス センター (手順 5 で) で Twitter コネクタをセットアップするユーザーには、Exchange Online の "Mailbox Import Export/メールボックスのインポートエクスポート" 役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d329f-123">The user who sets up the Twitter connector in the Microsoft 365 compliance center (in Step 5) must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="d329f-124">既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="d329f-124">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="d329f-125">"Mailbox Import Export/メールボックスのインポートとエクスポート" 役割は、Exchange Online の "Organization Management/組織の管理" 役割グループに追加できます。</span><span class="sxs-lookup"><span data-stu-id="d329f-125">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="d329f-126">または、役割グループを作成し、Mailbox Import Export 役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="d329f-126">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="d329f-127">詳細については、「Exchange Online[で役割](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の「役割グループの作成」または「役割グループの変更」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d329f-127">For more information, see the  [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="d329f-128">手順 1: Azure Active Directory でアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="d329f-128">Step 1: Create an app in Azure Active Directory</span></span>

<span data-ttu-id="d329f-129">最初の手順では、Azure Active Directory (AAD) に新しいアプリを登録します。</span><span class="sxs-lookup"><span data-stu-id="d329f-129">The first step is to register a new app in Azure Active Directory (AAD).</span></span> <span data-ttu-id="d329f-130">このアプリは、Twitter コネクタの手順 2 で実装する Web アプリ リソースに対応しています。</span><span class="sxs-lookup"><span data-stu-id="d329f-130">This app corresponds to the web app resource that you implement in Step 2 for the Twitter connector.</span></span>

<span data-ttu-id="d329f-131">詳しい手順については、「Azure Active Directory でアプリを作成 [する」を参照してください](deploy-twitter-connector.md#step-1-create-an-app-in-azure-active-directory)。</span><span class="sxs-lookup"><span data-stu-id="d329f-131">For step-by-step instructions, see [Create an app in Azure Active Directory](deploy-twitter-connector.md#step-1-create-an-app-in-azure-active-directory).</span></span>

<span data-ttu-id="d329f-132">この手順が完了すると (詳しい手順に従って)、次の情報をテキスト ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="d329f-132">During the completion of this step (by following the step-by-step instructions), you'll save the following information to a text file.</span></span> <span data-ttu-id="d329f-133">これらの値は、展開プロセスの後の手順で使用されます。</span><span class="sxs-lookup"><span data-stu-id="d329f-133">These values will be used in later steps in the deployment process.</span></span>

- <span data-ttu-id="d329f-134">AAD アプリケーション ID</span><span class="sxs-lookup"><span data-stu-id="d329f-134">AAD application ID</span></span>

- <span data-ttu-id="d329f-135">AAD アプリケーション シークレット</span><span class="sxs-lookup"><span data-stu-id="d329f-135">AAD application secret</span></span>

- <span data-ttu-id="d329f-136">テナント ID</span><span class="sxs-lookup"><span data-stu-id="d329f-136">Tenant Id</span></span>

## <a name="step-2-deploy-connector-web-service-from-github-repository-to-your-azure-account"></a><span data-ttu-id="d329f-137">手順 2: コネクタ Web サービスを GitHub リポジトリから Azure アカウントに展開する</span><span class="sxs-lookup"><span data-stu-id="d329f-137">Step 2: Deploy connector web service from GitHub repository to your Azure account</span></span>

<span data-ttu-id="d329f-138">次の手順では、Twitter API を使用して Twitter アカウントに接続し、データを抽出して Microsoft 365 にインポートする Twitter コネクタ アプリのソース コードを展開します。</span><span class="sxs-lookup"><span data-stu-id="d329f-138">The next step is to deploy the source code for the Twitter connector app that will use Twitter API to connect to your Twitter account and extract data so you can import it to Microsoft 365.</span></span> <span data-ttu-id="d329f-139">組織に展開する Twitter コネクタは、組織の Twitter アカウントから、この手順で作成された Azure Storage の場所にアイテムをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="d329f-139">The Twitter connector that you deploy for your organization will upload the items from your organization's Twitter account to the Azure Storage location that is created in this step.</span></span> <span data-ttu-id="d329f-140">Microsoft 365 コンプライアンス センター (手順 5 で) で Twitter コネクタを作成すると、Microsoft 365 インポート サービスは Azure Storage の場所から Microsoft 365 のメールボックスに Twitter データをコピーします。</span><span class="sxs-lookup"><span data-stu-id="d329f-140">After you create a Twitter connector in the Microsoft 365 compliance center (in Step 5), the Microsoft 365 Import service will copy the Twitter data from the Azure Storage location to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="d329f-141">「コネクタをセットアップする [前](#before-you-set-up-a-connector) に」セクションで説明したように、Azure ストレージ アカウントを作成するには、有効な Azure サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="d329f-141">As previous explained in the [Before you set up a connector](#before-you-set-up-a-connector) section, you must have a valid Azure subscription to create an Azure Storage account.</span></span>

<span data-ttu-id="d329f-142">Twitter コネクタ アプリのソース コードを展開するには、</span><span class="sxs-lookup"><span data-stu-id="d329f-142">To deploy the source code for the Twitter connector app:</span></span>

1. <span data-ttu-id="d329f-143">この [GitHub サイトに移動します](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet)。</span><span class="sxs-lookup"><span data-stu-id="d329f-143">Go to [this GitHub site](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet).</span></span>

2. <span data-ttu-id="d329f-144">[Azure **に展開] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="d329f-144">Click **Deploy to Azure**.</span></span>

<span data-ttu-id="d329f-145">詳しい手順については、「GitHub から Azure アカウントにコネクタ Web サービスを展開 [する」を参照してください](deploy-twitter-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)。</span><span class="sxs-lookup"><span data-stu-id="d329f-145">For step-by-step instructions, see [Deploy the connector web service from GitHub to your Azure account](deploy-twitter-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account).</span></span>

<span data-ttu-id="d329f-146">ステップ バイ ステップの手順に従ってこの手順を完了する場合は、次の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="d329f-146">While you follow the step-by-step instructions to complete this step, you provide the following information</span></span>

- <span data-ttu-id="d329f-147">APISecretKey: この手順の完了時にこのシークレットを作成します。</span><span class="sxs-lookup"><span data-stu-id="d329f-147">APISecretKey: You create this secret during the completion of this step.</span></span> <span data-ttu-id="d329f-148">手順 5 で使用します。</span><span class="sxs-lookup"><span data-stu-id="d329f-148">It's used in Step 5.</span></span>

- <span data-ttu-id="d329f-149">tenantId: 手順 1 で Azure Active Directory で Twitter アプリを作成した後にコピーした Microsoft 365 組織のテナント ID。</span><span class="sxs-lookup"><span data-stu-id="d329f-149">tenantId: The tenant ID of your Microsoft 365 organization that you copied after creating the Twitter app in Azure Active Directory in Step 1.</span></span>

<span data-ttu-id="d329f-150">この手順を完了した後、必ずアプリのサービス URL (たとえば) をコピーします `https://twitterconnector.azurewebsites.net` 。</span><span class="sxs-lookup"><span data-stu-id="d329f-150">After completing this step, be sure to copy the app Service URL (for example, `https://twitterconnector.azurewebsites.net`).</span></span> <span data-ttu-id="d329f-151">この URL を使用して、手順 3、手順 4、および手順 5 を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d329f-151">You need to use this URL to complete Step 3, Step 4, and Step 5).</span></span>

## <a name="step-3-create-developer-app-on-twitter"></a><span data-ttu-id="d329f-152">手順 3: Twitter で開発者アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="d329f-152">Step 3: Create developer app on Twitter</span></span>

<span data-ttu-id="d329f-153">次の手順では、Twitter で開発者アプリを作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="d329f-153">The next step is to create and configure a developer app on Twitter.</span></span> <span data-ttu-id="d329f-154">手順 7 で作成したカスタム コネクタは、Twitter アプリを使用して Twitter API と対話し、組織の Twitter アカウントからデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="d329f-154">The custom connector that you create in Step 7 uses the Twitter app to interact with the Twitter API to obtain data from your organization's Twitter account.</span></span>

<span data-ttu-id="d329f-155">詳しい手順については、「Twitter アプリの作成 [」を参照してください](deploy-twitter-connector.md#step-3-create-the-twitter-app)。</span><span class="sxs-lookup"><span data-stu-id="d329f-155">For step-by-step instructions, see [Create the Twitter app](deploy-twitter-connector.md#step-3-create-the-twitter-app).</span></span>

<span data-ttu-id="d329f-156">この手順が完了すると (詳しい手順に従って)、次の情報をテキスト ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="d329f-156">During the completion of this step (by following the step-by-step instructions), you save the following information to a text file.</span></span> <span data-ttu-id="d329f-157">これらの値は、手順 4 で Twitter コネクタ アプリを構成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d329f-157">These values will be used to configure the Twitter connector app in Step 4.</span></span>

- <span data-ttu-id="d329f-158">Twitter API キー</span><span class="sxs-lookup"><span data-stu-id="d329f-158">Twitter API Key</span></span>

- <span data-ttu-id="d329f-159">Twitter API の秘密キー</span><span class="sxs-lookup"><span data-stu-id="d329f-159">Twitter API Secret Key</span></span>

- <span data-ttu-id="d329f-160">Twitter アクセス トークン</span><span class="sxs-lookup"><span data-stu-id="d329f-160">Twitter Access Token</span></span>

- <span data-ttu-id="d329f-161">Twitter アクセス トークン シークレット</span><span class="sxs-lookup"><span data-stu-id="d329f-161">Twitter Access Token Secret</span></span>

## <a name="step-4-configure-the-twitter-connector-app"></a><span data-ttu-id="d329f-162">手順 4: Twitter コネクタ アプリを構成する</span><span class="sxs-lookup"><span data-stu-id="d329f-162">Step 4: Configure the Twitter connector app</span></span>

<span data-ttu-id="d329f-163">次の手順では、手順 2 で展開した Twitter コネクタ アプリに構成設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="d329f-163">The next step is to add configurations settings to the Twitter connector app that you deployed in Step 2.</span></span> <span data-ttu-id="d329f-164">これを行うには、コネクタ アプリのホーム ページに移動して構成します。</span><span class="sxs-lookup"><span data-stu-id="d329f-164">You do this by going to the home page of your connector app and configuring it.</span></span>

<span data-ttu-id="d329f-165">詳しい手順については、「コネクタ Web アプリを構成 [する」を参照してください](deploy-twitter-connector.md#step-4-configure-the-connector-web-app)。</span><span class="sxs-lookup"><span data-stu-id="d329f-165">For step-by-step instructions, see [Configure the connector web app](deploy-twitter-connector.md#step-4-configure-the-connector-web-app).</span></span>

<span data-ttu-id="d329f-166">この手順の完了時に (詳しい手順に従って) 次の情報を入力します (前の手順を完了した後にテキスト ファイルにコピーした情報)。</span><span class="sxs-lookup"><span data-stu-id="d329f-166">During the completion of this step (by following the step-by-step instructions), you'll provide the following information (that you've copied to a text file after completing the previous steps):</span></span>

- <span data-ttu-id="d329f-167">Twitter API キー (手順 3 で取得)</span><span class="sxs-lookup"><span data-stu-id="d329f-167">Twitter API Key (obtained in Step 3)</span></span>

- <span data-ttu-id="d329f-168">Twitter API 秘密キー (手順 3 で取得)</span><span class="sxs-lookup"><span data-stu-id="d329f-168">Twitter API Secret Key (obtained in Step 3)</span></span>

- <span data-ttu-id="d329f-169">Twitter アクセス トークン (手順 3 で取得)</span><span class="sxs-lookup"><span data-stu-id="d329f-169">Twitter Access Token (obtained in Step 3)</span></span>

- <span data-ttu-id="d329f-170">Twitter アクセス トークン シークレット (手順 3 で取得)</span><span class="sxs-lookup"><span data-stu-id="d329f-170">Twitter Access Token Secret (obtained in Step 3)</span></span>

- <span data-ttu-id="d329f-171">Azure Active Directory アプリケーション ID (手順 1 で取得した AAD アプリケーション ID)</span><span class="sxs-lookup"><span data-stu-id="d329f-171">Azure Active Directory application ID (the AAD application ID obtained in Step 1)</span></span>

- <span data-ttu-id="d329f-172">Azure Active Directory アプリケーション シークレット (手順 1 で取得した AAD アプリケーション シークレット)</span><span class="sxs-lookup"><span data-stu-id="d329f-172">Azure Active Directory application secret (the AAD application secret obtained in Step 1)</span></span>

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="d329f-173">手順 5: Microsoft 365 コンプライアンス センターで Twitter コネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="d329f-173">Step 5: Set up a Twitter connector in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="d329f-174">最後の手順では、組織の Twitter アカウントから Microsoft 365 の指定されたメールボックスにデータをインポートする Microsoft 365 コンプライアンス センターで Twitter コネクタを設定します。</span><span class="sxs-lookup"><span data-stu-id="d329f-174">The final step is to set up the Twitter connector in the Microsoft 365 compliance center that will import data from your organization's Twitter account to a specified mailbox in Microsoft 365.</span></span> <span data-ttu-id="d329f-175">この手順を完了すると、Microsoft 365 インポート サービスは組織の Twitter アカウントから Microsoft 365 へのデータのインポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="d329f-175">After you complete this step, the Microsoft 365 Import service will start importing data from your organization's Twitter account to Microsoft 365.</span></span>

<span data-ttu-id="d329f-176">詳しい手順については [、「Microsoft 365](deploy-twitter-connector.md#step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center)コンプライアンス センターで Twitter コネクタをセットアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d329f-176">For step-by-step instructions, see [Set up a Twitter connector in the Microsoft 365 compliance center](deploy-twitter-connector.md#step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center).</span></span> 

<span data-ttu-id="d329f-177">この手順の完了時に (詳しい手順に従って) 次の情報を入力します (手順を完了した後にテキスト ファイルにコピーした情報)。</span><span class="sxs-lookup"><span data-stu-id="d329f-177">During the completion of this step (by following the step-by-step instructions), you'll provide the following information (that you've copied to a text file after completing the steps).</span></span>

- <span data-ttu-id="d329f-178">Azure アプリ サービスの URL (手順 2 で取得(例 `https://twitterconnector.azurewebsites.net` : )</span><span class="sxs-lookup"><span data-stu-id="d329f-178">Azure app service URL (obtained in Step 2; for example, `https://twitterconnector.azurewebsites.net`)</span></span>

- <span data-ttu-id="d329f-179">APISecretKey (手順 2 で作成したキー)</span><span class="sxs-lookup"><span data-stu-id="d329f-179">APISecretKey (that you created in Step 2)</span></span>
