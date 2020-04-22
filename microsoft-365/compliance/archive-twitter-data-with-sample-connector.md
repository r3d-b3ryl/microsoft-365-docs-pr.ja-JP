---
title: コネクタセットアップしてTwitter のデータをアーカイブする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 管理者は、Twitter データを Microsoft 365 にインポートするためのネイティブコネクタをセットアップできます。 これにより、Microsoft 365 でサードパーティのデータソースのデータをアーカイブできるようになるため、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティデータのガバナンスを管理することができます。
ms.openlocfilehash: 866bd61c40aa998bcb612ee1d82f8275f075bb8e
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630614"
---
# <a name="set-up-a-connector-to-archive-twitter-data"></a><span data-ttu-id="c4be8-104">コネクタセットアップしてTwitter のデータをアーカイブする</span><span class="sxs-lookup"><span data-stu-id="c4be8-104">Set up a connector to archive Twitter data</span></span>

<span data-ttu-id="c4be8-105">Microsoft 365 コンプライアンスセンターのコネクタを使用して、Twitter から Microsoft 365 にデータをインポートおよびアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="c4be8-105">Use a connector in the Microsoft 365 compliance center to import and archive data from Twitter to Microsoft 365.</span></span> <span data-ttu-id="c4be8-106">コネクタをセットアップして構成すると、組織の Twitter アカウントに (スケジュールに従って) 接続され、アイテムのコンテンツが電子メールメッセージの形式に変換されてから、それらのアイテムを Microsoft 365 のメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="c4be8-106">After you set up and configure the connector, it connects to your organization's Twitter account (on a scheduled basis), converts the content of an item to an email message format, and then imports those items to a mailbox in Microsoft 365.</span></span>

<span data-ttu-id="c4be8-107">Twitter データがインポートされたら、訴訟ホールド、コンテンツ検索、インプレースアーカイブ、監査、Microsoft 365 保持ポリシーなどの Microsoft 365 コンプライアンス機能を Twitter データに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="c4be8-107">After the Twitter data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Microsoft 365 retention policies to the Twitter data.</span></span> <span data-ttu-id="c4be8-108">たとえば、メールボックスが訴訟ホールドの対象となっている場合、またはアイテム保持ポリシーに割り当てられている場合、Twitter データは保持されます。</span><span class="sxs-lookup"><span data-stu-id="c4be8-108">For example, when a mailbox is placed on Litigation Hold or assigned to a retention policy, the Twitter data is preserved.</span></span> <span data-ttu-id="c4be8-109">高度な電子情報開示ケースでは、コンテンツ検索を使用してサードパーティのデータを検索したり、Twitter データが格納されているメールボックスを保管担当者に関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="c4be8-109">You can search third-party data using Content Search or associate the mailbox where the Twitter data is stored with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="c4be8-110">コネクタを使用して、Microsoft 365 で Twitter データをインポートおよびアーカイブすることにより、組織は政府および規制ポリシーに準拠し続けることができます。</span><span class="sxs-lookup"><span data-stu-id="c4be8-110">Using a connector to import and archive Twitter data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

<span data-ttu-id="c4be8-111">Twitter データがインポートされたら、メールボックスに格納されているデータに、訴訟ホールド、コンテンツ検索、インプレースアーカイブ、監査、通信コンプライアンス、Microsoft 365 保持ポリシーなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="c4be8-111">After Twitter data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, Communication compliance, and Microsoft 365 retention policies to the data stored in the mailbox.</span></span> <span data-ttu-id="c4be8-112">たとえば、コンテンツ検索を使用して Twitter データを検索したり、保管担当者でデータが格納されているメールボックスを、高度な電子情報開示ケースに関連付けたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="c4be8-112">For example, you can search Twitter data using Content Search or associate the mailbox where the data is stored with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="c4be8-113">コネクタを使用して、Microsoft 365 で Twitter データをインポートおよびアーカイブすることにより、組織は政府および規制ポリシーに準拠し続けることができます。</span><span class="sxs-lookup"><span data-stu-id="c4be8-113">Using a connector to import and archive Twitter data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="prerequisites-for-setting-up-a-connector-for-twitter"></a><span data-ttu-id="c4be8-114">Twitter 用のコネクタを設定するための前提条件</span><span class="sxs-lookup"><span data-stu-id="c4be8-114">Prerequisites for setting up a connector for Twitter</span></span>

<span data-ttu-id="c4be8-115">Microsoft 365 コンプライアンスセンターでコネクタを設定および構成して、組織の Twitter アカウントからデータをインポートおよびアーカイブする前に、次の前提条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4be8-115">Complete the following prerequisites before you can set up and configure a connector in the Microsoft 365 compliance center to import and archive data from your organization's Twitter account.</span></span>

- <span data-ttu-id="c4be8-116">組織のために Twitter アカウントが必要です。コネクタを設定するときに、このアカウントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4be8-116">You need a Twitter account for your organization; you need to sign in to this account when setting up the connector.</span></span>

- <span data-ttu-id="c4be8-117">組織が有効な Azure サブスクリプションを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4be8-117">Your organization must have a valid Azure subscription.</span></span> <span data-ttu-id="c4be8-118">既存の Azure サブスクリプションがない場合は、次のオプションのいずれかにサインアップできます。</span><span class="sxs-lookup"><span data-stu-id="c4be8-118">If you don't have an existing Azure subscription, you can sign up for one of these options:</span></span>

    - [<span data-ttu-id="c4be8-119">無料の1年間の Azure サブスクリプションにサインアップする</span><span class="sxs-lookup"><span data-stu-id="c4be8-119">Sign up for a free one year Azure subscription</span></span>](https://azure.microsoft.com/free) 

    - [<span data-ttu-id="c4be8-120">Azure へのご購入のサブスクリプションへのサインアップ</span><span class="sxs-lookup"><span data-stu-id="c4be8-120">Sign up for a Pay-As-You-Go Azure subscription</span></span>](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > <span data-ttu-id="c4be8-121">Microsoft 365 サブスクリプションに含まれている[無料の Azure Active Directory サブスクリプション](use-your-free-azure-ad-subscription-in-office-365.md)は、セキュリティ & コンプライアンスセンターのコネクタをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="c4be8-121">The [free Azure Active Directory subscription](use-your-free-azure-ad-subscription-in-office-365.md) that's included with your Microsoft 365 subscription doesn't support the connectors in the Security & Compliance Center.</span></span>

- <span data-ttu-id="c4be8-122">組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4be8-122">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="c4be8-123">この要求に同意するには、[このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)に移動して、グローバル管理者の資格情報でサインインし、要求を承諾します。</span><span class="sxs-lookup"><span data-stu-id="c4be8-123">To consent to this request, go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), sign in with the credentials of a global admin, and then accept the request.</span></span>

- <span data-ttu-id="c4be8-124">Microsoft 365 コンプライアンスセンター (手順 5) で Twitter connector をセットアップするユーザーは、Exchange Online でメールボックスのインポートのエクスポート役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4be8-124">The user who sets up the Twitter connector in the Microsoft 365 compliance center (in Step 5) must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="c4be8-125">既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="c4be8-125">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="c4be8-126">Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="c4be8-126">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="c4be8-127">または、役割グループを作成し、メールボックスインポートエクスポート役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="c4be8-127">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="c4be8-128">詳細については、記事「Manage role groups in Exchange Online」の「[役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)」または「[役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4be8-128">For more information, see the  [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="c4be8-129">手順 1: Azure Active Directory でアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="c4be8-129">Step 1: Create an app in Azure Active Directory</span></span>

<span data-ttu-id="c4be8-130">最初の手順として、Azure Active Directory (AAD) に新しいアプリを登録します。</span><span class="sxs-lookup"><span data-stu-id="c4be8-130">The first step is to register a new app in Azure Active Directory (AAD).</span></span> <span data-ttu-id="c4be8-131">このアプリは、Twitter connector の手順2で実装した web app リソースに対応します。</span><span class="sxs-lookup"><span data-stu-id="c4be8-131">This app corresponds to the web app resource that you implement in Step 2 for the Twitter connector.</span></span>

<span data-ttu-id="c4be8-132">詳細な手順については、「 [Azure Active Directory でアプリを作成](deploy-twitter-connector.md#step-1-create-an-app-in-azure-active-directory)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4be8-132">For step-by-step instructions, see [Create an app in Azure Active Directory](deploy-twitter-connector.md#step-1-create-an-app-in-azure-active-directory).</span></span>

<span data-ttu-id="c4be8-133">この手順が完了すると (手順に従って)、次の情報がテキストファイルに保存されます。</span><span class="sxs-lookup"><span data-stu-id="c4be8-133">During the completion of this step (by following the step-by-step instructions), you'll save the following information to a text file.</span></span> <span data-ttu-id="c4be8-134">これらの値は、展開プロセスの後の手順で使用されます。</span><span class="sxs-lookup"><span data-stu-id="c4be8-134">These values will be used in later steps in the deployment process.</span></span>

- <span data-ttu-id="c4be8-135">AAD アプリケーション ID</span><span class="sxs-lookup"><span data-stu-id="c4be8-135">AAD application ID</span></span>

- <span data-ttu-id="c4be8-136">AAD アプリケーションシークレット</span><span class="sxs-lookup"><span data-stu-id="c4be8-136">AAD application secret</span></span>

- <span data-ttu-id="c4be8-137">テナント Id</span><span class="sxs-lookup"><span data-stu-id="c4be8-137">Tenant Id</span></span>

## <a name="step-2-deploy-connector-web-service-from-github-repository-to-your-azure-account"></a><span data-ttu-id="c4be8-138">手順 2: GitHub リポジトリから Azure アカウントに connector web サービスを展開する</span><span class="sxs-lookup"><span data-stu-id="c4be8-138">Step 2: Deploy connector web service from GitHub repository to your Azure account</span></span>

<span data-ttu-id="c4be8-139">次の手順では、twitter API を使用して twitter アカウントに接続し、データを抽出して Microsoft 365 にインポートできるようにするための twitter コネクタアプリのソースコードを展開します。</span><span class="sxs-lookup"><span data-stu-id="c4be8-139">The next step is to deploy the source code for the Twitter connector app that will use Twitter API to connect to your Twitter account and extract data so you can import it to Microsoft 365.</span></span> <span data-ttu-id="c4be8-140">組織用に展開する Twitter コネクタは、組織の Twitter アカウントから、この手順で作成された Azure ストレージの場所にアイテムをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="c4be8-140">The Twitter connector that you deploy for your organization will upload the items from your organization's Twitter account to the Azure Storage location that is created in this step.</span></span> <span data-ttu-id="c4be8-141">Microsoft 365 コンプライアンスセンター (手順 5) で Twitter コネクタを作成した後、Office 365 インポートサービスは、Azure ストレージの場所から Twitter データを Microsoft 365 のメールボックスにコピーします。</span><span class="sxs-lookup"><span data-stu-id="c4be8-141">After you create a Twitter connector in the Microsoft 365 compliance center (in Step 5), the Office 365 Import service will copy the Twitter data from the Azure Storage location to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="c4be8-142">前述の「[前提条件](#prerequisites-for-setting-up-a-connector-for-twitter)」セクションで説明したように、azure Storage アカウントを作成するには、有効な azure サブスクリプションを用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4be8-142">As previous explained in the [Prerequisites](#prerequisites-for-setting-up-a-connector-for-twitter) section, you must have a valid Azure subscription to create an Azure Storage account.</span></span>

<span data-ttu-id="c4be8-143">Twitter connector アプリのソースコードを展開するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="c4be8-143">To deploy the source code for the Twitter connector app:</span></span>

1. <span data-ttu-id="c4be8-144">[この GitHub サイト](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet)に移動します。</span><span class="sxs-lookup"><span data-stu-id="c4be8-144">Go to [this GitHub site](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet).</span></span>

2. <span data-ttu-id="c4be8-145">[ **Azure への展開] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="c4be8-145">Click **Deploy to Azure**.</span></span>

<span data-ttu-id="c4be8-146">詳細な手順については、「 [connector web service を GitHub から Azure アカウントに展開する](deploy-twitter-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4be8-146">For step-by-step instructions, see [Deploy the connector web service from GitHub to your Azure account](deploy-twitter-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account).</span></span>

<span data-ttu-id="c4be8-147">手順に従ってこの手順を完了すると、次の情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="c4be8-147">While you follow the step-by-step instructions to complete this step, you provide the following information</span></span>

- <span data-ttu-id="c4be8-148">APISecretKey: この手順の完了時にこのシークレットを作成します。</span><span class="sxs-lookup"><span data-stu-id="c4be8-148">APISecretKey: You create this secret during the completion of this step.</span></span> <span data-ttu-id="c4be8-149">手順5で使用します。</span><span class="sxs-lookup"><span data-stu-id="c4be8-149">It's used in Step 5.</span></span>

- <span data-ttu-id="c4be8-150">tenantId: 手順1で作成した、Azure Active Directory で Twitter アプリを作成した後にコピーした Microsoft 365 組織のテナント ID。</span><span class="sxs-lookup"><span data-stu-id="c4be8-150">tenantId: The tenant ID of your Microsoft 365 organization that you copied after creating the Twitter app in Azure Active Directory in Step 1.</span></span>

<span data-ttu-id="c4be8-151">この手順を完了したら、必ず app Service の URL (例: `https://twitterconnector.azurewebsites.net`) をコピーしてください。</span><span class="sxs-lookup"><span data-stu-id="c4be8-151">After completing this step, be sure to copy the app Service URL (for example, `https://twitterconnector.azurewebsites.net`).</span></span> <span data-ttu-id="c4be8-152">手順3、手順4、および手順5を完了するには、この URL を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4be8-152">You need to use this URL to complete Step 3, Step 4, and Step 5).</span></span>

## <a name="step-3-create-developer-app-on-twitter"></a><span data-ttu-id="c4be8-153">手順 3: Twitter で開発者用アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="c4be8-153">Step 3: Create developer app on Twitter</span></span>

<span data-ttu-id="c4be8-154">次の手順では、Twitter で開発者用アプリを作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="c4be8-154">The next step is to create and configure a developer app on Twitter.</span></span> <span data-ttu-id="c4be8-155">手順7で作成したカスタムコネクタは、twitter アプリを使用して、組織の Twitter アカウントからデータを取得する Twitter API と対話します。</span><span class="sxs-lookup"><span data-stu-id="c4be8-155">The custom connector that you create in Step 7 uses the Twitter app to interact with the Twitter API to obtain data from your organization's Twitter account.</span></span>

<span data-ttu-id="c4be8-156">詳細な手順については、「 [Twitter アプリを作成](deploy-twitter-connector.md#step-3-create-the-twitter-app)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4be8-156">For step-by-step instructions, see [Create the Twitter app](deploy-twitter-connector.md#step-3-create-the-twitter-app).</span></span>

<span data-ttu-id="c4be8-157">この手順が完了したら (手順に従って)、次の情報をテキストファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="c4be8-157">During the completion of this step (by following the step-by-step instructions), you save the following information to a text file.</span></span> <span data-ttu-id="c4be8-158">これらの値は、手順4で Twitter connector アプリを構成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c4be8-158">These values will be used to configure the Twitter connector app in Step 4.</span></span>

- <span data-ttu-id="c4be8-159">Twitter API キー</span><span class="sxs-lookup"><span data-stu-id="c4be8-159">Twitter API Key</span></span>

- <span data-ttu-id="c4be8-160">Twitter API の秘密キー</span><span class="sxs-lookup"><span data-stu-id="c4be8-160">Twitter API Secret Key</span></span>

- <span data-ttu-id="c4be8-161">Twitter アクセストークン</span><span class="sxs-lookup"><span data-stu-id="c4be8-161">Twitter Access Token</span></span>

- <span data-ttu-id="c4be8-162">Twitter アクセストークンシークレット</span><span class="sxs-lookup"><span data-stu-id="c4be8-162">Twitter Access Token Secret</span></span>

## <a name="step-4-configure-the-twitter-connector-app"></a><span data-ttu-id="c4be8-163">手順 4: Twitter connector アプリを構成する</span><span class="sxs-lookup"><span data-stu-id="c4be8-163">Step 4: Configure the Twitter connector app</span></span>

<span data-ttu-id="c4be8-164">次の手順では、手順2で展開した Twitter connector アプリに構成設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="c4be8-164">The next step is to add configurations settings to the Twitter connector app that you deployed in Step 2.</span></span> <span data-ttu-id="c4be8-165">これを行うには、コネクタアプリのホームページにアクセスして構成します。</span><span class="sxs-lookup"><span data-stu-id="c4be8-165">You do this by going to the home page of your connector app and configuring it.</span></span>

<span data-ttu-id="c4be8-166">詳細な手順については、「 [Configure the connector web app](deploy-twitter-connector.md#step-4-configure-the-connector-web-app)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4be8-166">For step-by-step instructions, see [Configure the connector web app](deploy-twitter-connector.md#step-4-configure-the-connector-web-app).</span></span>

<span data-ttu-id="c4be8-167">この手順が完了すると (手順に従って)、次の情報が提供されます (前の手順を完了した後、テキストファイルにコピーしたことになります)。</span><span class="sxs-lookup"><span data-stu-id="c4be8-167">During the completion of this step (by following the step-by-step instructions), you'll provide the following information (that you've copied to a text file after completing the previous steps):</span></span>

- <span data-ttu-id="c4be8-168">Twitter API キー (手順3で取得)</span><span class="sxs-lookup"><span data-stu-id="c4be8-168">Twitter API Key (obtained in Step 3)</span></span>

- <span data-ttu-id="c4be8-169">Twitter API の秘密キー (手順3で取得)</span><span class="sxs-lookup"><span data-stu-id="c4be8-169">Twitter API Secret Key (obtained in Step 3)</span></span>

- <span data-ttu-id="c4be8-170">Twitter アクセストークン (手順3で取得)</span><span class="sxs-lookup"><span data-stu-id="c4be8-170">Twitter Access Token (obtained in Step 3)</span></span>

- <span data-ttu-id="c4be8-171">Twitter アクセストークンシークレット (手順3で取得)</span><span class="sxs-lookup"><span data-stu-id="c4be8-171">Twitter Access Token Secret (obtained in Step 3)</span></span>

- <span data-ttu-id="c4be8-172">Azure Active Directory アプリケーション ID (手順1で取得した AAD アプリケーション ID)</span><span class="sxs-lookup"><span data-stu-id="c4be8-172">Azure Active Directory application ID (the AAD application ID obtained in Step 1)</span></span>

- <span data-ttu-id="c4be8-173">Azure Active Directory アプリケーションシークレット (手順1で取得した AAD アプリケーションシークレット)</span><span class="sxs-lookup"><span data-stu-id="c4be8-173">Azure Active Directory application secret (the AAD application secret obtained in Step 1)</span></span>

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="c4be8-174">手順 5: Microsoft 365 コンプライアンスセンターで Twitter connector をセットアップする</span><span class="sxs-lookup"><span data-stu-id="c4be8-174">Step 5: Set up a Twitter connector in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="c4be8-175">最後の手順として、Microsoft 365 コンプライアンスセンターで、組織の Twitter アカウントから Microsoft 365 の指定したメールボックスにデータをインポートする Twitter コネクタを設定します。</span><span class="sxs-lookup"><span data-stu-id="c4be8-175">The final step is to set up the Twitter connector in the Microsoft 365 compliance center that will import data from your organization's Twitter account to a specified mailbox in Microsoft 365.</span></span> <span data-ttu-id="c4be8-176">この手順を完了すると、Office 365 インポートサービスは、組織の Twitter アカウントから Microsoft 365 へのデータのインポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="c4be8-176">After you complete this step, the Office 365 Import service will start importing data from your organization's Twitter account to Microsoft 365.</span></span>

<span data-ttu-id="c4be8-177">詳細な手順については、「 [Microsoft 365 コンプライアンスセンターでの Twitter コネクタの設定](deploy-twitter-connector.md#step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4be8-177">For step-by-step instructions, see [Set up a Twitter connector in the Microsoft 365 compliance center](deploy-twitter-connector.md#step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center).</span></span> 

<span data-ttu-id="c4be8-178">この手順が完了すると (手順に従って)、次の情報が提供されます (手順を完了したら、テキストファイルにコピーしたことになります)。</span><span class="sxs-lookup"><span data-stu-id="c4be8-178">During the completion of this step (by following the step-by-step instructions), you'll provide the following information (that you've copied to a text file after completing the steps).</span></span>

- <span data-ttu-id="c4be8-179">Azure app service の URL (手順2で取得`https://twitterconnector.azurewebsites.net`) (例:)</span><span class="sxs-lookup"><span data-stu-id="c4be8-179">Azure app service URL (obtained in Step 2; for example, `https://twitterconnector.azurewebsites.net`)</span></span>

- <span data-ttu-id="c4be8-180">APISecretKey (手順2で作成したもの)</span><span class="sxs-lookup"><span data-stu-id="c4be8-180">APISecretKey (that you created in Step 2)</span></span>
