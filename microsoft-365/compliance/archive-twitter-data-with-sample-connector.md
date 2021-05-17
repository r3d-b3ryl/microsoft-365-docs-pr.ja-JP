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
description: 管理者がネイティブ コネクタをセットアップして使用して、Twitter データをユーザーにインポートする方法Microsoft 365。
ms.openlocfilehash: 277af8ea7367936c4c9528a8ca50ccd678745bf6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922259"
---
# <a name="set-up-a-connector-to-archive-twitter-data-preview"></a><span data-ttu-id="5fc98-103">Twitter データをアーカイブするコネクタをセットアップする (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="5fc98-103">Set up a connector to archive Twitter data (preview)</span></span>

<span data-ttu-id="5fc98-104">コンプライアンス センターのコネクタを使用Microsoft 365 Twitter からデータのインポートとアーカイブを行Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="5fc98-104">Use a connector in the Microsoft 365 compliance center to import and archive data from Twitter to Microsoft 365.</span></span> <span data-ttu-id="5fc98-105">コネクタをセットアップして構成した後、組織の Twitter アカウントに (スケジュールに基づいて) 接続し、アイテムのコンテンツを電子メール メッセージ形式に変換し、Microsoft 365 のメールボックスにそれらのアイテムをインポートします。</span><span class="sxs-lookup"><span data-stu-id="5fc98-105">After you set up and configure the connector, it connects to your organization's Twitter account (on a scheduled basis), converts the content of an item to an email message format, and then imports those items to a mailbox in Microsoft 365.</span></span>

<span data-ttu-id="5fc98-106">Twitter データをインポートした後、訴訟ホールド、コンテンツ検索、In-Place アーカイブ、監査、Microsoft 365 保持ポリシーなどの Microsoft 365 コンプライアンス機能を Twitter データに適用できます。</span><span class="sxs-lookup"><span data-stu-id="5fc98-106">After the Twitter data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Microsoft 365 retention policies to the Twitter data.</span></span> <span data-ttu-id="5fc98-107">たとえば、メールボックスが訴訟ホールドに置かれたり、保持ポリシーに割り当てられたりすると、Twitter データは保持されます。</span><span class="sxs-lookup"><span data-stu-id="5fc98-107">For example, when a mailbox is placed on Litigation Hold or assigned to a retention policy, the Twitter data is preserved.</span></span> <span data-ttu-id="5fc98-108">コンテンツ検索を使用してサード パーティのデータを検索するか、Twitter データが保存されているメールボックスを管理者に関連付Advanced eDiscoveryできます。</span><span class="sxs-lookup"><span data-stu-id="5fc98-108">You can search third-party data using Content Search or associate the mailbox where the Twitter data is stored with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="5fc98-109">コネクタを使用して Twitter データをインポートおよびアーカイブMicrosoft 365、組織が政府および規制ポリシーに準拠しつ付けるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5fc98-109">Using a connector to import and archive Twitter data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

<span data-ttu-id="5fc98-110">Twitter データをインポートした後、訴訟ホールド、コンテンツ検索、In-Place アーカイブ、監査、通信コンプライアンス、Microsoft 365 保持ポリシーなどの Microsoft 365 コンプライアンス機能をメールボックスに格納されているデータに適用できます。</span><span class="sxs-lookup"><span data-stu-id="5fc98-110">After Twitter data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, Communication compliance, and Microsoft 365 retention policies to the data stored in the mailbox.</span></span> <span data-ttu-id="5fc98-111">たとえば、コンテンツ検索を使用して Twitter データを検索したり、データが保管担当者に保存されているメールボックスを特定のケースに関連付Advanced eDiscoveryできます。</span><span class="sxs-lookup"><span data-stu-id="5fc98-111">For example, you can search Twitter data using Content Search or associate the mailbox where the data is stored with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="5fc98-112">コネクタを使用して Twitter データをインポートおよびアーカイブMicrosoft 365、組織が政府および規制ポリシーに準拠しつ付けるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5fc98-112">Using a connector to import and archive Twitter data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="5fc98-113">コネクタをセットアップする前に</span><span class="sxs-lookup"><span data-stu-id="5fc98-113">Before you set up a connector</span></span>

<span data-ttu-id="5fc98-114">組織の Twitter アカウントからデータをインポートおよびアーカイブするために、Microsoft 365 コンプライアンス センターでコネクタを設定および構成する前に、次の前提条件を満たしてください。</span><span class="sxs-lookup"><span data-stu-id="5fc98-114">Complete the following prerequisites before you can set up and configure a connector in the Microsoft 365 compliance center to import and archive data from your organization's Twitter account.</span></span>

- <span data-ttu-id="5fc98-115">組織の Twitter アカウントが必要です。コネクタのセットアップ時に、このアカウントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fc98-115">You need a Twitter account for your organization; you need to sign in to this account when setting up the connector.</span></span>

- <span data-ttu-id="5fc98-116">組織に有効な Azure サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="5fc98-116">Your organization must have a valid Azure subscription.</span></span> <span data-ttu-id="5fc98-117">既存の Azure サブスクリプションがない場合は、次のいずれかのオプションにサインアップできます。</span><span class="sxs-lookup"><span data-stu-id="5fc98-117">If you don't have an existing Azure subscription, you can sign up for one of these options:</span></span>

    - [<span data-ttu-id="5fc98-118">無料の 1 年間 Azure サブスクリプションにサインアップする</span><span class="sxs-lookup"><span data-stu-id="5fc98-118">Sign up for a free one year Azure subscription</span></span>](https://azure.microsoft.com/free) 

    - [<span data-ttu-id="5fc98-119">Pay-As-Go Azure サブスクリプションにサインアップする</span><span class="sxs-lookup"><span data-stu-id="5fc98-119">Sign up for a Pay-As-You-Go Azure subscription</span></span>](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > <span data-ttu-id="5fc98-120">Azure Active Directory[サブスクリプション](use-your-free-azure-ad-subscription-in-office-365.md)に含まれる無料のサブスクリプションMicrosoft 365は、セキュリティ コンプライアンス センターのコネクタ&しません。</span><span class="sxs-lookup"><span data-stu-id="5fc98-120">The [free Azure Active Directory subscription](use-your-free-azure-ad-subscription-in-office-365.md) that's included with your Microsoft 365 subscription doesn't support the connectors in the Security & Compliance Center.</span></span>

- <span data-ttu-id="5fc98-121">Twitter コネクタは、1 日に合計 200,000 アイテムをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="5fc98-121">The Twitter connector can import a total of 200,000 items in a single day.</span></span> <span data-ttu-id="5fc98-122">1 日に 200,000 件を超える Twitter アイテムがある場合、それらのアイテムはいずれも 1 日にインポートMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="5fc98-122">If there are more than 200,000 Twitter items in a day, none of those items will be imported to Microsoft 365.</span></span>

- <span data-ttu-id="5fc98-123">コンプライアンス センター (手順 5) で Twitter コネクタMicrosoft 365セットアップするユーザーには、ユーザーにメールボックスインポートエクスポートの役割が割り当てられている必要Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="5fc98-123">The user who sets up the Twitter connector in the Microsoft 365 compliance center (in Step 5) must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="5fc98-124">既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="5fc98-124">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="5fc98-125">[メールボックスのインポートエクスポート] 役割は、組織の [組織の管理] 役割グループに追加Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="5fc98-125">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="5fc98-126">または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="5fc98-126">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="5fc98-127">詳細については、「グループ内の[役割グループを](/Exchange/permissions-exo/role-groups#create-role-groups)管理[](/Exchange/permissions-exo/role-groups#modify-role-groups)する」の「役割グループの作成」または「役割グループの変更」セクションを参照Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="5fc98-127">For more information, see the  [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="5fc98-128">手順 1: アプリをアプリで作成Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="5fc98-128">Step 1: Create an app in Azure Active Directory</span></span>

<span data-ttu-id="5fc98-129">最初の手順は、新しいアプリをアプリ (AAD) Azure Active Directory登録します。</span><span class="sxs-lookup"><span data-stu-id="5fc98-129">The first step is to register a new app in Azure Active Directory (AAD).</span></span> <span data-ttu-id="5fc98-130">このアプリは、Twitter コネクタの手順 2 で実装する Web アプリ リソースに対応します。</span><span class="sxs-lookup"><span data-stu-id="5fc98-130">This app corresponds to the web app resource that you implement in Step 2 for the Twitter connector.</span></span>

<span data-ttu-id="5fc98-131">手順については、「アプリを作成する[」](deploy-twitter-connector.md#step-1-create-an-app-in-azure-active-directory)を参照Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="5fc98-131">For step-by-step instructions, see [Create an app in Azure Active Directory](deploy-twitter-connector.md#step-1-create-an-app-in-azure-active-directory).</span></span>

<span data-ttu-id="5fc98-132">この手順が完了すると (手順の手順に従って)、次の情報をテキスト ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="5fc98-132">During the completion of this step (by following the step-by-step instructions), you'll save the following information to a text file.</span></span> <span data-ttu-id="5fc98-133">これらの値は、展開プロセスの後の手順で使用されます。</span><span class="sxs-lookup"><span data-stu-id="5fc98-133">These values will be used in later steps in the deployment process.</span></span>

- <span data-ttu-id="5fc98-134">AAD アプリケーション ID</span><span class="sxs-lookup"><span data-stu-id="5fc98-134">AAD application ID</span></span>

- <span data-ttu-id="5fc98-135">AAD アプリケーション シークレット</span><span class="sxs-lookup"><span data-stu-id="5fc98-135">AAD application secret</span></span>

- <span data-ttu-id="5fc98-136">テナント ID</span><span class="sxs-lookup"><span data-stu-id="5fc98-136">Tenant Id</span></span>

## <a name="step-2-deploy-connector-web-service-from-github-repository-to-your-azure-account"></a><span data-ttu-id="5fc98-137">手順 2: コネクタ Web サービスを azure GitHubリポジトリから Azure アカウントに展開する</span><span class="sxs-lookup"><span data-stu-id="5fc98-137">Step 2: Deploy connector web service from GitHub repository to your Azure account</span></span>

<span data-ttu-id="5fc98-138">次の手順では、Twitter API を使用して Twitter アカウントに接続し、データを抽出する Twitter コネクタ アプリのソース コードを展開し、データを Microsoft 365 にインポートします。</span><span class="sxs-lookup"><span data-stu-id="5fc98-138">The next step is to deploy the source code for the Twitter connector app that will use Twitter API to connect to your Twitter account and extract data so you can import it to Microsoft 365.</span></span> <span data-ttu-id="5fc98-139">組織に展開する Twitter コネクタは、組織の Twitter アカウントからこの手順で作成Azure Storage場所にアイテムをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="5fc98-139">The Twitter connector that you deploy for your organization will upload the items from your organization's Twitter account to the Azure Storage location that is created in this step.</span></span> <span data-ttu-id="5fc98-140">Microsoft 365 コンプライアンス センター (手順 5) で Twitter コネクタを作成すると、Microsoft 365 インポート サービスは Azure Storage の場所から Microsoft 365 のメールボックスに Twitter データをコピーします。</span><span class="sxs-lookup"><span data-stu-id="5fc98-140">After you create a Twitter connector in the Microsoft 365 compliance center (in Step 5), the Microsoft 365 Import service will copy the Twitter data from the Azure Storage location to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="5fc98-141">前の「コネクタをセットアップ[する](#before-you-set-up-a-connector)前に」セクションで説明したように、有効な Azure Storage Azure サブスクリプションを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fc98-141">As previous explained in the [Before you set up a connector](#before-you-set-up-a-connector) section, you must have a valid Azure subscription to create an Azure Storage account.</span></span>

<span data-ttu-id="5fc98-142">Twitter コネクタ アプリのソース コードを展開するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="5fc98-142">To deploy the source code for the Twitter connector app:</span></span>

1. <span data-ttu-id="5fc98-143">このサイト[に移動GitHubします](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet)。</span><span class="sxs-lookup"><span data-stu-id="5fc98-143">Go to [this GitHub site](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet).</span></span>

2. <span data-ttu-id="5fc98-144">[Azure **に展開する] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5fc98-144">Click **Deploy to Azure**.</span></span>

<span data-ttu-id="5fc98-145">詳細な手順については、「コネクタ Web サービスを Azure アカウントに展開する」を参照GitHub[を参照してください](deploy-twitter-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)。</span><span class="sxs-lookup"><span data-stu-id="5fc98-145">For step-by-step instructions, see [Deploy the connector web service from GitHub to your Azure account](deploy-twitter-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account).</span></span>

<span data-ttu-id="5fc98-146">手順に従ってこの手順を完了する場合は、次の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="5fc98-146">While you follow the step-by-step instructions to complete this step, you provide the following information</span></span>

- <span data-ttu-id="5fc98-147">APISecretKey: この手順の完了時に、このシークレットを作成します。</span><span class="sxs-lookup"><span data-stu-id="5fc98-147">APISecretKey: You create this secret during the completion of this step.</span></span> <span data-ttu-id="5fc98-148">手順 5 で使用します。</span><span class="sxs-lookup"><span data-stu-id="5fc98-148">It's used in Step 5.</span></span>

- <span data-ttu-id="5fc98-149">tenantId: 手順 1 で Twitter アプリMicrosoft 365作成した後にコピーした組織のテナント ID Azure Active Directory ID です。</span><span class="sxs-lookup"><span data-stu-id="5fc98-149">tenantId: The tenant ID of your Microsoft 365 organization that you copied after creating the Twitter app in Azure Active Directory in Step 1.</span></span>

<span data-ttu-id="5fc98-150">この手順を完了した後、必ずアプリのサービス URL (たとえば) をコピーしてください `https://twitterconnector.azurewebsites.net` 。</span><span class="sxs-lookup"><span data-stu-id="5fc98-150">After completing this step, be sure to copy the app Service URL (for example, `https://twitterconnector.azurewebsites.net`).</span></span> <span data-ttu-id="5fc98-151">この URL を使用して、手順 3、手順 4、および手順 5) を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fc98-151">You need to use this URL to complete Step 3, Step 4, and Step 5).</span></span>

## <a name="step-3-create-developer-app-on-twitter"></a><span data-ttu-id="5fc98-152">手順 3: Twitter で開発者アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="5fc98-152">Step 3: Create developer app on Twitter</span></span>

<span data-ttu-id="5fc98-153">次の手順では、Twitter で開発者アプリを作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="5fc98-153">The next step is to create and configure a developer app on Twitter.</span></span> <span data-ttu-id="5fc98-154">手順 7 で作成するカスタム コネクタは、Twitter アプリを使用して Twitter API を操作し、組織の Twitter アカウントからデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="5fc98-154">The custom connector that you create in Step 7 uses the Twitter app to interact with the Twitter API to obtain data from your organization's Twitter account.</span></span>

<span data-ttu-id="5fc98-155">手順については [、「Create the Twitter app」を参照してください](deploy-twitter-connector.md#step-3-create-the-twitter-app)。</span><span class="sxs-lookup"><span data-stu-id="5fc98-155">For step-by-step instructions, see [Create the Twitter app](deploy-twitter-connector.md#step-3-create-the-twitter-app).</span></span>

<span data-ttu-id="5fc98-156">この手順の完了時 (手順に従って)、次の情報をテキスト ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="5fc98-156">During the completion of this step (by following the step-by-step instructions), you save the following information to a text file.</span></span> <span data-ttu-id="5fc98-157">これらの値は、手順 4 で Twitter コネクタ アプリを構成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="5fc98-157">These values will be used to configure the Twitter connector app in Step 4.</span></span>

- <span data-ttu-id="5fc98-158">Twitter API キー</span><span class="sxs-lookup"><span data-stu-id="5fc98-158">Twitter API Key</span></span>

- <span data-ttu-id="5fc98-159">Twitter API シークレット キー</span><span class="sxs-lookup"><span data-stu-id="5fc98-159">Twitter API Secret Key</span></span>

- <span data-ttu-id="5fc98-160">Twitter アクセス トークン</span><span class="sxs-lookup"><span data-stu-id="5fc98-160">Twitter Access Token</span></span>

- <span data-ttu-id="5fc98-161">Twitter アクセス トークン シークレット</span><span class="sxs-lookup"><span data-stu-id="5fc98-161">Twitter Access Token Secret</span></span>

## <a name="step-4-configure-the-twitter-connector-app"></a><span data-ttu-id="5fc98-162">手順 4: Twitter コネクタ アプリを構成する</span><span class="sxs-lookup"><span data-stu-id="5fc98-162">Step 4: Configure the Twitter connector app</span></span>

<span data-ttu-id="5fc98-163">次の手順では、手順 2 で展開した Twitter コネクタ アプリに構成設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="5fc98-163">The next step is to add configurations settings to the Twitter connector app that you deployed in Step 2.</span></span> <span data-ttu-id="5fc98-164">これを行うには、コネクタ アプリのホーム ページに移動して構成します。</span><span class="sxs-lookup"><span data-stu-id="5fc98-164">You do this by going to the home page of your connector app and configuring it.</span></span>

<span data-ttu-id="5fc98-165">手順については、「コネクタ Web アプリの [構成」を参照してください](deploy-twitter-connector.md#step-4-configure-the-connector-web-app)。</span><span class="sxs-lookup"><span data-stu-id="5fc98-165">For step-by-step instructions, see [Configure the connector web app](deploy-twitter-connector.md#step-4-configure-the-connector-web-app).</span></span>

<span data-ttu-id="5fc98-166">この手順の完了時 (手順に従って)、次の情報 (前の手順を完了した後にテキスト ファイルにコピーした情報) を提供します。</span><span class="sxs-lookup"><span data-stu-id="5fc98-166">During the completion of this step (by following the step-by-step instructions), you'll provide the following information (that you've copied to a text file after completing the previous steps):</span></span>

- <span data-ttu-id="5fc98-167">Twitter API キー (手順 3 で取得)</span><span class="sxs-lookup"><span data-stu-id="5fc98-167">Twitter API Key (obtained in Step 3)</span></span>

- <span data-ttu-id="5fc98-168">Twitter API シークレット キー (手順 3 で取得)</span><span class="sxs-lookup"><span data-stu-id="5fc98-168">Twitter API Secret Key (obtained in Step 3)</span></span>

- <span data-ttu-id="5fc98-169">Twitter アクセス トークン (手順 3 で取得)</span><span class="sxs-lookup"><span data-stu-id="5fc98-169">Twitter Access Token (obtained in Step 3)</span></span>

- <span data-ttu-id="5fc98-170">Twitter Access Token Secret (手順 3 で取得)</span><span class="sxs-lookup"><span data-stu-id="5fc98-170">Twitter Access Token Secret (obtained in Step 3)</span></span>

- <span data-ttu-id="5fc98-171">Azure Active Directory ID (手順 1 で取得した AAD アプリケーション ID)</span><span class="sxs-lookup"><span data-stu-id="5fc98-171">Azure Active Directory application ID (the AAD application ID obtained in Step 1)</span></span>

- <span data-ttu-id="5fc98-172">Azure Active Directory アプリケーション シークレット (手順 1 で取得した AAD アプリケーション シークレット)</span><span class="sxs-lookup"><span data-stu-id="5fc98-172">Azure Active Directory application secret (the AAD application secret obtained in Step 1)</span></span>

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="5fc98-173">手順 5: コンプライアンス センターで Twitter コネクタをMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="5fc98-173">Step 5: Set up a Twitter connector in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="5fc98-174">最後の手順は、Microsoft 365 コンプライアンス センターで Twitter コネクタをセットアップし、組織の Twitter アカウントから、Microsoft 365 で指定されたメールボックスにデータをインポートします。</span><span class="sxs-lookup"><span data-stu-id="5fc98-174">The final step is to set up the Twitter connector in the Microsoft 365 compliance center that will import data from your organization's Twitter account to a specified mailbox in Microsoft 365.</span></span> <span data-ttu-id="5fc98-175">この手順を完了すると、Microsoft 365インポート サービスは組織の Twitter アカウントからデータのインポートを開始Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="5fc98-175">After you complete this step, the Microsoft 365 Import service will start importing data from your organization's Twitter account to Microsoft 365.</span></span>

<span data-ttu-id="5fc98-176">手順については、「コンプライアンス センターで Twitter コネクタをセットアップする」を参照Microsoft 365[してください](deploy-twitter-connector.md#step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="5fc98-176">For step-by-step instructions, see [Set up a Twitter connector in the Microsoft 365 compliance center](deploy-twitter-connector.md#step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center).</span></span> 

<span data-ttu-id="5fc98-177">この手順の完了時 (手順の手順に従って)、次の情報 (手順を完了した後にテキスト ファイルにコピーした情報) を提供します。</span><span class="sxs-lookup"><span data-stu-id="5fc98-177">During the completion of this step (by following the step-by-step instructions), you'll provide the following information (that you've copied to a text file after completing the steps).</span></span>

- <span data-ttu-id="5fc98-178">Azure アプリ サービスの URL (手順 2 で取得、たとえば `https://twitterconnector.azurewebsites.net` )</span><span class="sxs-lookup"><span data-stu-id="5fc98-178">Azure app service URL (obtained in Step 2; for example, `https://twitterconnector.azurewebsites.net`)</span></span>

- <span data-ttu-id="5fc98-179">APISecretKey (手順 2 で作成した)</span><span class="sxs-lookup"><span data-stu-id="5fc98-179">APISecretKey (that you created in Step 2)</span></span>