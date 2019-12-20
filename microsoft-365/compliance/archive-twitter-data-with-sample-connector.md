---
title: サンプルコネクタを使用して Twitter データをアーカイブする (プレビュー)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 管理者は、Office 365 に Twitter データをインポートするためのネイティブコネクタをセットアップできます。 これにより、Office 365 でサードパーティのデータソースのデータをアーカイブできるため、組織のサードパーティデータのガバナンスを管理するために、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用できます。
ms.openlocfilehash: 77f0a0615a177c0bfd6179a6a5ce1a58b024dcdc
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2019
ms.locfileid: "40807486"
---
# <a name="use-a-sample-connector-to-archive-twitter-data-preview"></a><span data-ttu-id="e05b4-104">サンプルコネクタを使用して Twitter データをアーカイブする (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="e05b4-104">Use a sample connector to archive Twitter data (Preview)</span></span>

<span data-ttu-id="e05b4-105">Office 365 で Twitter データをアーカイブするためのサンプルコネクタ機能は、プレビュー段階にあります。</span><span class="sxs-lookup"><span data-stu-id="e05b4-105">The sample connector feature to archive Twitter data in Office 365 is in Preview.</span></span>

<span data-ttu-id="e05b4-106">Office 365 のセキュリティ & コンプライアンスセンターのサンプルコネクタを使用して、Twitter からデータをインポートおよびアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="e05b4-106">Use a sample connector in the Security & Compliance Center in Office 365 to import and archive data from Twitter.</span></span> <span data-ttu-id="e05b4-107">サンプルコネクタをセットアップして構成すると、組織の Twitter アカウントに (スケジュールに従って) 接続され、アイテムのコンテンツが電子メールメッセージの形式に変換されてから、それらのアイテムを Office 365 のメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="e05b4-107">After you set up and configure a sample connector, it connects to your organization's Twitter account (on a scheduled basis), converts the content of an item to an email message format, and then imports those items to a mailbox in Office 365.</span></span>

<span data-ttu-id="e05b4-108">Twitter データをインポートすると、メールボックスに格納されているデータに、訴訟ホールド、コンテンツ検索、インプレースアーカイブ、監査、[通信コンプライアンス](communication-compliance.md)、office 365 アイテム保持ポリシーなどの office 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="e05b4-108">After Twitter data is imported, you can apply Office 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, [Communication compliance](communication-compliance.md), and Office 365 retention policies to the data stored in the mailbox.</span></span> <span data-ttu-id="e05b4-109">たとえば、コンテンツ検索を使用して Twitter データを検索したり、保管担当者でデータが格納されているメールボックスを、高度な電子情報開示ケースに関連付けたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="e05b4-109">For example, you can search Twitter data using Content Search or associate the mailbox where the data is stored with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="e05b4-110">サンプルコネクタを使用して Office 365 で Twitter データをインポートおよびアーカイブすることにより、組織は政府および規制ポリシーに準拠し続けることができます。</span><span class="sxs-lookup"><span data-stu-id="e05b4-110">Using a sample connector to import and archive Twitter data in Office 365 can help your organization stay compliant with government and regulatory policies.</span></span>

> [!NOTE]
> <span data-ttu-id="e05b4-111">現時点では、Twitter および[Facebook のビジネスページ](archive-facebook-data-with-sample-connector.md)用のサンプルコネクタのみをプレビューで利用できます。</span><span class="sxs-lookup"><span data-stu-id="e05b4-111">Currently, only the sample connectors for Twitter and [Facebook Business pages](archive-facebook-data-with-sample-connector.md) are available for Preview.</span></span> <span data-ttu-id="e05b4-112">その他のサンプルコネクタは近日中に公開されます。</span><span class="sxs-lookup"><span data-stu-id="e05b4-112">More sample connectors are coming soon.</span></span>


## <a name="prerequisites-for-setting-up-a-connector-for-twitter"></a><span data-ttu-id="e05b4-113">Twitter 用のコネクタを設定するための前提条件</span><span class="sxs-lookup"><span data-stu-id="e05b4-113">Prerequisites for setting up a connector for Twitter</span></span>

<span data-ttu-id="e05b4-114">セキュリティ & コンプライアンスセンターでサンプルコネクタを設定および構成するには、次の前提条件を満たしている必要があります。組織の Twitter アカウントからデータをインポートおよびアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="e05b4-114">Complete the following prerequisites before you can set up and configure a sample connector in the Security & Compliance Center to import and archive data from your organization's Twitter account.</span></span> 

- <span data-ttu-id="e05b4-115">組織のために Twitter アカウントが必要です。コネクタを設定するときに、このアカウントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e05b4-115">You need a Twitter account for your organization; you need to sign in to this account when setting up the connector.</span></span>

- <span data-ttu-id="e05b4-116">組織が有効な Azure サブスクリプションを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e05b4-116">Your organization must have a valid Azure subscription.</span></span> <span data-ttu-id="e05b4-117">既存の Azure サブスクリプションがない場合は、次のオプションのいずれかにサインアップできます。</span><span class="sxs-lookup"><span data-stu-id="e05b4-117">If you don't have an existing Azure subscription, you can sign up for one of these options:</span></span>

    - [<span data-ttu-id="e05b4-118">無料の1年間の Azure サブスクリプションにサインアップする</span><span class="sxs-lookup"><span data-stu-id="e05b4-118">Sign up for a free one year Azure subscription</span></span>](https://azure.microsoft.com/free) 

    - [<span data-ttu-id="e05b4-119">Azure へのご購入のサブスクリプションへのサインアップ</span><span class="sxs-lookup"><span data-stu-id="e05b4-119">Sign up for a Pay-As-You-Go Azure subscription</span></span>](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > <span data-ttu-id="e05b4-120">Office 365 サブスクリプションに含まれている[無料の Azure Active Directory サブスクリプション](use-your-free-azure-ad-subscription-in-office-365.md)は、セキュリティ & コンプライアンスセンターのサンプルコネクタをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="e05b4-120">The [free Azure Active Directory subscription](use-your-free-azure-ad-subscription-in-office-365.md) that's included with your Office 365 subscription doesn't support the sample connectors in the Security & Compliance Center.</span></span>

- <span data-ttu-id="e05b4-121">組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。</span><span class="sxs-lookup"><span data-stu-id="e05b4-121">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="e05b4-122">この要求に同意するには、[このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)に移動して、Office 365 グローバル管理者の資格情報でサインインし、要求を承諾します。</span><span class="sxs-lookup"><span data-stu-id="e05b4-122">To consent to this request, go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), sign in with the credentials of an Office 365 global admin, and then accept the request.</span></span>

- <span data-ttu-id="e05b4-123">セキュリティ & コンプライアンス (手順 7) でカスタムコネクタをセットアップするユーザーに、Exchange Online のメールボックスのインポートのエクスポート役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e05b4-123">The user who sets up the custom connector in the Security & Compliance (in Step 7) must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="e05b4-124">既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="e05b4-124">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="e05b4-125">Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="e05b4-125">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="e05b4-126">または、新しい役割グループを作成し、メールボックスインポートエクスポートの役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="e05b4-126">Or you can create a new role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="e05b4-127">詳細については、記事「Manage role groups in Exchange Online」の「[役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)」または「[役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e05b4-127">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-download-the-pre-built-connector-app-package-from-github"></a><span data-ttu-id="e05b4-128">手順 1: GitHub から事前に作成されたコネクタアプリパッケージをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="e05b4-128">Step 1: Download the pre-built connector app package from GitHub</span></span>

<span data-ttu-id="e05b4-129">最初の手順として、twitter API を使用して twitter アカウントに接続し、データを抽出して Office 365 にインポートできるようにする Twitter サンプルコネクタアプリのソースコードをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e05b4-129">The first step is to download the source code for the Twitter sample connector app that will use a Twitter API to connect to your Twitter account and extract data so you can import it to Office 365.</span></span>

1. <span data-ttu-id="e05b4-130">[この GitHub サイト](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases)に移動します。</span><span class="sxs-lookup"><span data-stu-id="e05b4-130">Go to [this GitHub site](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases).</span></span> 
2. <span data-ttu-id="e05b4-131">最新リリースの下で、 **SampleConnector**ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="e05b4-131">Under the latest release, select the **SampleConnector.zip** file.</span></span>
3. <span data-ttu-id="e05b4-132">ZIP ファイルをローカルコンピューターの場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="e05b4-132">Save the ZIP file to a location on your local computer.</span></span> <span data-ttu-id="e05b4-133">この zip ファイルを手順4で Azure にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="e05b4-133">You upload this zip file to Azure in Step 4.</span></span>

## <a name="step-2-create-an-app-in-azure-active-directory"></a><span data-ttu-id="e05b4-134">手順 2: Azure Active Directory でアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="e05b4-134">Step 2: Create an app in Azure Active Directory</span></span>

<span data-ttu-id="e05b4-135">次の手順では、Azure Active Directory (AAD) に新しいアプリを登録します。</span><span class="sxs-lookup"><span data-stu-id="e05b4-135">The next step is to register a new app in Azure Active Directory (AAD).</span></span> <span data-ttu-id="e05b4-136">このアプリは、Twitter connector の手順4で実装した web app リソースに対応します。</span><span class="sxs-lookup"><span data-stu-id="e05b4-136">This app corresponds to the web app resource that you implement in Step 4 for the Twitter connector.</span></span> 

<span data-ttu-id="e05b4-137">詳細な手順については、「[手順 2: Azure Active Directory でアプリを作成](deploy-twitter-connector.md#step-2-create-an-app-in-azure-active-directory)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e05b4-137">For step-by-step instructions, see [Step 2: Create an app in Azure Active Directory](deploy-twitter-connector.md#step-2-create-an-app-in-azure-active-directory).</span></span>

<span data-ttu-id="e05b4-138">この手順が完了すると (手順に従って)、次の情報がテキストファイルに保存されます。</span><span class="sxs-lookup"><span data-stu-id="e05b4-138">During the completion of this step (by following the step-by-step instructions), you'll save the following information to a text file.</span></span> <span data-ttu-id="e05b4-139">これらの値は、展開プロセスの後の手順で使用されます。</span><span class="sxs-lookup"><span data-stu-id="e05b4-139">These values will be used in later steps in the deployment process.</span></span>

- <span data-ttu-id="e05b4-140">AAD アプリケーション ID</span><span class="sxs-lookup"><span data-stu-id="e05b4-140">AAD application ID</span></span>
- <span data-ttu-id="e05b4-141">AAD アプリケーションシークレット</span><span class="sxs-lookup"><span data-stu-id="e05b4-141">AAD application secret</span></span>
- <span data-ttu-id="e05b4-142">AAD アプリケーション Uri</span><span class="sxs-lookup"><span data-stu-id="e05b4-142">AAD application Uri</span></span>
- <span data-ttu-id="e05b4-143">テナント Id</span><span class="sxs-lookup"><span data-stu-id="e05b4-143">Tenant Id</span></span>

## <a name="step-3-create-an-azure-storage-account"></a><span data-ttu-id="e05b4-144">手順 3: Azure Storage アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="e05b4-144">Step 3: Create an Azure Storage account</span></span>

<span data-ttu-id="e05b4-145">組織用に展開する Twitter コネクタは、Twitter から、この手順で作成した Azure ストレージの場所にアイテムをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="e05b4-145">The Twitter connector that you deploy for your organization uploads the items from Twitter to the Azure Storage location that you create in this step.</span></span> <span data-ttu-id="e05b4-146">セキュリティ & コンプライアンスセンター (手順 7) でカスタムコネクタを作成すると、Office 365 インポートサービスによって、Azure ストレージの場所から Office 365 のメールボックスに Twitter データがコピーされます。</span><span class="sxs-lookup"><span data-stu-id="e05b4-146">After you create a custom connector in the Security & Compliance Center (in Step 7), the Office 365 Import service will copy the Twitter data from the Azure Storage location to a mailbox in Office 365.</span></span> <span data-ttu-id="e05b4-147">前述の「[前提条件](#prerequisites-for-setting-up-a-connector-for-twitter)」セクションで説明したように、azure Storage アカウントを作成するには、有効な azure サブスクリプションを用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e05b4-147">As previous explained in the [Prerequisites](#prerequisites-for-setting-up-a-connector-for-twitter) section, you must have a valid Azure subscription to create an Azure Storage account.</span></span>

<span data-ttu-id="e05b4-148">詳細な手順については、「[手順 3: Azure ストレージアカウントを作成する](deploy-twitter-connector.md#step-3-create-an-azure-storage-account)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e05b4-148">For step-by-step instructions, see [Step 3: Create an Azure Storage account](deploy-twitter-connector.md#step-3-create-an-azure-storage-account).</span></span>

<span data-ttu-id="e05b4-149">この手順が完了したら (手順に従って)、生成された接続文字列 Uri を保存します。</span><span class="sxs-lookup"><span data-stu-id="e05b4-149">During the completion of this step (by following the step-by-step instructions), you save the connection string Uri that is generated.</span></span> <span data-ttu-id="e05b4-150">この文字列は、手順4で Azure で web app リソースを作成するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="e05b4-150">You use this string when creating a web app resource in Azure in Step 4.</span></span>

## <a name="step-4-create-a-web-app-resource-in-azure"></a><span data-ttu-id="e05b4-151">手順 4: Azure で web app リソースを作成する</span><span class="sxs-lookup"><span data-stu-id="e05b4-151">Step 4: Create a web app resource in Azure</span></span>

<span data-ttu-id="e05b4-152">次の手順では、Twitter コネクタ用に Azure で web app リソースを作成します。</span><span class="sxs-lookup"><span data-stu-id="e05b4-152">The next step is to create a web app resource in Azure for the Twitter connector.</span></span> 

<span data-ttu-id="e05b4-153">詳細な手順については、「 [step 4: Create a new web app resource In Azure](deploy-twitter-connector.md#step-4-create-a-new-web-app-resource-in-azure)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e05b4-153">For step-by-step instructions, see [Step 4: Create a new web app resource in Azure](deploy-twitter-connector.md#step-4-create-a-new-web-app-resource-in-azure).</span></span>

<span data-ttu-id="e05b4-154">この手順が完了すると (手順に従って)、次の情報が提供されます (前の手順を完了した後、テキストファイルにコピーしたもの) web app リソースを作成します。</span><span class="sxs-lookup"><span data-stu-id="e05b4-154">During the completion of this step (by following the step-by-step instructions), you'll provide the following information (that you've copied to a text file after completing the previous steps) when creating the web app resource.</span></span>

- <span data-ttu-id="e05b4-155">APISecretKey –この手順の完了時にこのシークレットを作成します。手順7で使用します。</span><span class="sxs-lookup"><span data-stu-id="e05b4-155">APISecretKey – You create this secret during the completion of this step; it's used in Step 7.</span></span>
- <span data-ttu-id="e05b4-156">StorageAccountConnectionString –手順3で Azure Storage アカウントを作成した後にコピーした接続文字列 Uri。</span><span class="sxs-lookup"><span data-stu-id="e05b4-156">StorageAccountConnectionString – The connection string Uri that you copied after creating the Azure Storage account in Step 3.</span></span>
- <span data-ttu-id="e05b4-157">tenantId –手順2で、Azure Active Directory で Twitter connector アプリを作成した後にコピーした Office 365 組織のテナント ID。</span><span class="sxs-lookup"><span data-stu-id="e05b4-157">tenantId – The tenant ID of your Office 365 organization that you copied after creating the Twitter connector app in Azure Active Directory in Step 2.</span></span>

<span data-ttu-id="e05b4-158">また、この手順で SampleConnector ファイル (手順1でダウンロードした) をアップロードして、Twitter connector アプリのソースコードを展開します。</span><span class="sxs-lookup"><span data-stu-id="e05b4-158">Also, you upload the SampleConnector.zip file (that you downloaded in Step 1) in this step to deploy the source code for the Twitter connector app.</span></span>

<span data-ttu-id="e05b4-159">この手順を完了したら、必ず Azure app service の URL (たとえば、 `https://twitterconnector.azurewebsites.net`) をコピーしてください。</span><span class="sxs-lookup"><span data-stu-id="e05b4-159">After completing this step, be sure to copy the Azure app service URL (for example, `https://twitterconnector.azurewebsites.net`).</span></span> <span data-ttu-id="e05b4-160">手順5、手順6、手順7を完了するには、この URL を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e05b4-160">You need to use this URL to complete Step 5, Step 6, and Step 7).</span></span>

## <a name="step-5-create-developer-app-on-twitter"></a><span data-ttu-id="e05b4-161">手順 5: Twitter で開発者用アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="e05b4-161">Step 5: Create developer app on Twitter</span></span>

<span data-ttu-id="e05b4-162">次の手順では、Twitter で開発者用アプリを作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="e05b4-162">The next step is to create and configure a developer app on Twitter.</span></span> <span data-ttu-id="e05b4-163">手順7で作成したカスタムコネクタは、twitter アプリを使用して、組織の Twitter アカウントからデータを取得する Twitter API と対話します。</span><span class="sxs-lookup"><span data-stu-id="e05b4-163">The custom connector that you create in Step 7 uses the Twitter app to interact with the Twitter API to obtain data from your organization's Twitter account.</span></span>

<span data-ttu-id="e05b4-164">詳細な手順については、「[手順 5: Twitter アプリを作成](deploy-twitter-connector.md#step-5-create-the-twitter-app)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e05b4-164">For step-by-step instructions, see [Step 5: Create the Twitter app](deploy-twitter-connector.md#step-5-create-the-twitter-app).</span></span>

<span data-ttu-id="e05b4-165">この手順が完了したら (手順に従って)、次の情報をテキストファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="e05b4-165">During the completion of this step (by following the step-by-step instructions), you save the following information to a text file.</span></span> <span data-ttu-id="e05b4-166">これらの値は、手順6で Twitter connector アプリを構成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e05b4-166">These values will be used to configure the Twitter connector app in Step 6.</span></span>

- <span data-ttu-id="e05b4-167">Twitter API キー</span><span class="sxs-lookup"><span data-stu-id="e05b4-167">Twitter API Key</span></span>
- <span data-ttu-id="e05b4-168">Twitter API の秘密キー</span><span class="sxs-lookup"><span data-stu-id="e05b4-168">Twitter API Secret Key</span></span>
- <span data-ttu-id="e05b4-169">Twitter アクセストークン</span><span class="sxs-lookup"><span data-stu-id="e05b4-169">Twitter Access Token</span></span>
- <span data-ttu-id="e05b4-170">Twitter アクセストークンシークレット</span><span class="sxs-lookup"><span data-stu-id="e05b4-170">Twitter Access Token Secret</span></span>

## <a name="step-6-configure-the-twitter-connector-app"></a><span data-ttu-id="e05b4-171">手順 6: Twitter connector アプリを構成する</span><span class="sxs-lookup"><span data-stu-id="e05b4-171">Step 6: Configure the Twitter connector app</span></span>

<span data-ttu-id="e05b4-172">次の手順では、手順4で Azure web app リソースの作成時にアップロードした Twitter connector アプリに構成設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="e05b4-172">The next step is to add configurations settings to the Twitter connector app that you uploaded when you created the Azure web app resource in Step 4.</span></span> <span data-ttu-id="e05b4-173">これを行うには、コネクタアプリのホームページにアクセスして構成します。</span><span class="sxs-lookup"><span data-stu-id="e05b4-173">You do this by going to the home page of your connector app and configuring it.</span></span>

<span data-ttu-id="e05b4-174">詳細な手順については、「 [step 6: Configure the connector web app](deploy-twitter-connector.md#step-6-configure-the-connector-web-app)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e05b4-174">For step-by-step instructions, see [Step 6: Configure the connector web app](deploy-twitter-connector.md#step-6-configure-the-connector-web-app).</span></span>

<span data-ttu-id="e05b4-175">この手順が完了すると (手順に従って)、次の情報が提供されます (前の手順を完了した後、テキストファイルにコピーしたことになります)。</span><span class="sxs-lookup"><span data-stu-id="e05b4-175">During the completion of this step (by following the step-by-step instructions), you'll provide the following information (that you've copied to a text file after completing the previous steps):</span></span>

- <span data-ttu-id="e05b4-176">Twitter API キー (手順5で取得)</span><span class="sxs-lookup"><span data-stu-id="e05b4-176">Twitter API Key (obtained in Step 5)</span></span>
- <span data-ttu-id="e05b4-177">Twitter API の秘密キー (手順5で取得)</span><span class="sxs-lookup"><span data-stu-id="e05b4-177">Twitter API Secret Key (obtained in Step 5)</span></span>
- <span data-ttu-id="e05b4-178">Twitter アクセストークン (手順5で取得)</span><span class="sxs-lookup"><span data-stu-id="e05b4-178">Twitter Access Token (obtained in Step 5)</span></span>
- <span data-ttu-id="e05b4-179">Twitter アクセストークンシークレット (手順5で取得)</span><span class="sxs-lookup"><span data-stu-id="e05b4-179">Twitter Access Token Secret (obtained in Step 5)</span></span>
- <span data-ttu-id="e05b4-180">Azure Active Directory アプリケーション ID (手順2で取得した AAD アプリケーション ID)</span><span class="sxs-lookup"><span data-stu-id="e05b4-180">Azure Active Directory application ID (the AAD application ID obtained in Step 2)</span></span>
- <span data-ttu-id="e05b4-181">Azure Active Directory アプリケーションシークレット (手順2で取得した AAD アプリケーションシークレット)</span><span class="sxs-lookup"><span data-stu-id="e05b4-181">Azure Active Directory application secret (the AAD application secret obtained in Step 2)</span></span>
- <span data-ttu-id="e05b4-182">Azure Active Directory アプリケーション Uri (手順2で取得した AAD アプリケーション Uri、たとえば、`https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213)`</span><span class="sxs-lookup"><span data-stu-id="e05b4-182">Azure Active Directory application Uri (the AAD application Uri obtained in Step 2; for example, `https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213)`</span></span>

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a><span data-ttu-id="e05b4-183">手順 7: セキュリティ & コンプライアンスセンターでカスタムコネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="e05b4-183">Step 7: Set up a custom connector in the Security & Compliance Center</span></span>

<span data-ttu-id="e05b4-184">最後の手順として、セキュリティ & コンプライアンスセンターでカスタムコネクタを設定して、組織の Twitter アカウントから Office 365 の指定したメールボックスにデータをインポートします。</span><span class="sxs-lookup"><span data-stu-id="e05b4-184">The final step is to set up the custom connector in the Security & Compliance Center that imports data from your organization's Twitter account to a specified mailbox in Office 365.</span></span> <span data-ttu-id="e05b4-185">この手順が正常に完了すると、Office 365 インポートサービスは Twitter から Office 365 へのデータのインポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="e05b4-185">After you successfully complete this step, the Office 365 Import service will start importing data from Twitter to Office 365.</span></span> 

<span data-ttu-id="e05b4-186">詳細な手順については、「[手順 7: セキュリティ/コンプライアンスセンターでカスタムコネクタを設定する](deploy-twitter-connector.md#step-7-set-up-a-custom-connector-in-the-security-and-compliance-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e05b4-186">For step-by-step instructions, see [Step 7: Set up a custom connector in the security and compliance center](deploy-twitter-connector.md#step-7-set-up-a-custom-connector-in-the-security-and-compliance-center).</span></span> 

<span data-ttu-id="e05b4-187">この手順が完了すると (手順に従って)、次の情報が提供されます (手順を完了したら、テキストファイルにコピーしたことになります)。</span><span class="sxs-lookup"><span data-stu-id="e05b4-187">During the completion of this step (by following the step-by-step instructions), you'll provide the following information (that you've copied to a text file after completing the steps).</span></span>

- <span data-ttu-id="e05b4-188">Azure app service の URL (手順4で取得`https://twitterconnector.azurewebsites.net`) (例:)</span><span class="sxs-lookup"><span data-stu-id="e05b4-188">Azure app service URL (obtained in Step 4; for example, `https://twitterconnector.azurewebsites.net`)</span></span>
- <span data-ttu-id="e05b4-189">APISecretKey (手順4で作成したもの)</span><span class="sxs-lookup"><span data-stu-id="e05b4-189">APISecretKey (that you created in Step 4)</span></span>
