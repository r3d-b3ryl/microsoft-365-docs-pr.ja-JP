---
title: コネクタをセットアップしてFacebook のデータをアーカイブする
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
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: Microsoft 365 コンプライアンスセンターでコネクタを使用 & て、Facebook のビジネスページのアーカイブデータを Microsoft 365 にインポート & をセットアップする方法について説明します。
ms.openlocfilehash: 79f3c3914476a20c07a1c3ab4418b918c8f22c3e
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818466"
---
# <a name="set-up-a-connector-to-archive-facebook-data-preview"></a><span data-ttu-id="99e96-103">Facebook データをアーカイブするコネクタを設定する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="99e96-103">Set up a connector to archive Facebook data (preview)</span></span>

<span data-ttu-id="99e96-104">Microsoft 365 コンプライアンスセンターのコネクタを使用して、Facebook のビジネスページから Microsoft 365 にデータをインポートし、アーカイブします。</span><span class="sxs-lookup"><span data-stu-id="99e96-104">Use a connector in the Microsoft 365 compliance center to import and archive data from Facebook Business pages to Microsoft 365.</span></span> <span data-ttu-id="99e96-105">コネクタをセットアップして構成すると、そのコネクタは Facebook のビジネスページに接続し (スケジュールに従って)、Facebook のアイテムのコンテンツを電子メールメッセージの形式に変換し、それらのアイテムを Microsoft 365 のメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="99e96-105">After you set up and configure the connector, it connects to the Facebook Business page (on a scheduled basis), converts the content of Facebook items to an email message format, and then imports those items to a mailbox in Microsoft 365.</span></span>

<span data-ttu-id="99e96-106">Facebook データのインポート後、訴訟ホールド、コンテンツ検索、インプレースアーカイブ、監査、通信コンプライアンス、Microsoft 365 保持ポリシーなどの Microsoft 365 コンプライアンス機能を Facebook データに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="99e96-106">After the Facebook data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, Communication compliance, and Microsoft 365 retention policies to the Facebook data.</span></span> <span data-ttu-id="99e96-107">たとえば、メールボックスが訴訟ホールドの対象となっている場合、またはアイテム保持ポリシーに割り当てられている場合、Facebook データは保持されます。</span><span class="sxs-lookup"><span data-stu-id="99e96-107">For example, when a mailbox is placed on Litigation Hold or assigned to a retention policy, the Facebook data is preserved.</span></span> <span data-ttu-id="99e96-108">高度な電子情報開示ケースでは、コンテンツ検索を使用してサードパーティのデータを検索するか、または保管担当者に Facebook データが格納されているメールボックスを関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="99e96-108">You can search third-party data using Content Search or associate the mailbox where the Facebook data is stored with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="99e96-109">コネクタを使用して、Microsoft 365 で Facebook データをインポートおよびアーカイブすることにより、組織は政府および規制ポリシーに準拠し続けることができます。</span><span class="sxs-lookup"><span data-stu-id="99e96-109">Using a connector to import and archive Facebook data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a><span data-ttu-id="99e96-110">Facebook ビジネスページ用のコネクタを設定するための前提条件</span><span class="sxs-lookup"><span data-stu-id="99e96-110">Prerequisites for setting up a connector for Facebook Business pages</span></span>

<span data-ttu-id="99e96-111">Microsoft 365 コンプライアンスセンターでコネクタを設定および構成して、組織の Facebook ビジネスページからデータをインポートおよびアーカイブする前に、次の前提条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="99e96-111">Complete the following prerequisites before you can set up and configure a connector in the Microsoft 365 compliance center to import and archive data from your organization's Facebook Business pages.</span></span> 

- <span data-ttu-id="99e96-112">組織のビジネスページ用の Facebook アカウントが必要です (コネクタを設定するときに、このアカウントにサインインする必要があります)。</span><span class="sxs-lookup"><span data-stu-id="99e96-112">You need a Facebook account for your organization's business pages (you need to sign in to this account when setting up the connector).</span></span> <span data-ttu-id="99e96-113">現時点では、Facebook のビジネスページのデータのみをアーカイブできます。個別の Facebook プロファイルからデータをアーカイブすることはできません。</span><span class="sxs-lookup"><span data-stu-id="99e96-113">Currently, you can only archive data from Facebook Business pages; you can't archive data from individual Facebook profiles.</span></span>

- <span data-ttu-id="99e96-114">組織が有効な Azure サブスクリプションを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="99e96-114">Your organization must have a valid Azure subscription.</span></span> <span data-ttu-id="99e96-115">既存の Azure サブスクリプションがない場合は、次のオプションのいずれかにサインアップできます。</span><span class="sxs-lookup"><span data-stu-id="99e96-115">If you don't have an existing Azure subscription, you can sign up for one of these options:</span></span>

    - [<span data-ttu-id="99e96-116">無料の1年間の Azure サブスクリプションにサインアップする</span><span class="sxs-lookup"><span data-stu-id="99e96-116">Sign up for a free one year Azure subscription</span></span>](https://azure.microsoft.com/free) 

    - [<span data-ttu-id="99e96-117">Azure へのご購入のサブスクリプションへのサインアップ</span><span class="sxs-lookup"><span data-stu-id="99e96-117">Sign up for a Pay-As-You-Go Azure subscription</span></span>](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > <span data-ttu-id="99e96-118">Microsoft 365 サブスクリプションに含まれている[無料の Azure Active Directory サブスクリプション](use-your-free-azure-ad-subscription-in-office-365.md)は、セキュリティ & コンプライアンスセンターのコネクタをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="99e96-118">The [free Azure Active Directory subscription](use-your-free-azure-ad-subscription-in-office-365.md) that's included with your Microsoft 365 subscription doesn't support the connectors in the Security & Compliance Center.</span></span>

- <span data-ttu-id="99e96-119">組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。</span><span class="sxs-lookup"><span data-stu-id="99e96-119">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="99e96-120">この要求に同意するには、[このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)に移動して、グローバル管理者の資格情報でサインインし、要求を承諾します。</span><span class="sxs-lookup"><span data-stu-id="99e96-120">To consent to this request, go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), sign in with the credentials of a global admin, and then accept the request.</span></span>

- <span data-ttu-id="99e96-121">Microsoft 365 コンプライアンスセンター (手順 5) でカスタムコネクタをセットアップするユーザーは、Exchange Online でメールボックスのインポートのエクスポート役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="99e96-121">The user who sets up the custom connector in the Microsoft 365 compliance center (in Step 5) must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="99e96-122">既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="99e96-122">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="99e96-123">Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="99e96-123">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="99e96-124">または、役割グループを作成し、メールボックスインポートエクスポート役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="99e96-124">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="99e96-125">詳細については、記事「Manage role groups in Exchange Online」の「[役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)」または「[役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="99e96-125">For more information, see the  [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="99e96-126">手順 1: Azure Active Directory でアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="99e96-126">Step 1: Create an app in Azure Active Directory</span></span>

<span data-ttu-id="99e96-127">最初の手順として、Azure Active Directory (AAD) に新しいアプリを登録します。</span><span class="sxs-lookup"><span data-stu-id="99e96-127">The first step is to register a new app in Azure Active Directory (AAD).</span></span> <span data-ttu-id="99e96-128">このアプリは、手順4および Facebook コネクタの手順5で実装した web app リソースに対応しています。</span><span class="sxs-lookup"><span data-stu-id="99e96-128">This app corresponds to the web app resource that you implement in Step 4 and Step 5 for the Facebook connector.</span></span> 

<span data-ttu-id="99e96-129">詳細な手順については、「 [Azure Active Directory でアプリを作成](deploy-facebook-connector.md#step-1-create-an-app-in-azure-active-directory)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99e96-129">For step-by-step instructions, see [Create an app in Azure Active Directory](deploy-facebook-connector.md#step-1-create-an-app-in-azure-active-directory).</span></span>

<span data-ttu-id="99e96-130">この手順が完了すると (前述の手順に従って)、次の情報がテキストファイルに保存されます。</span><span class="sxs-lookup"><span data-stu-id="99e96-130">During the completion of this step (by using the previous step-by-step instructions), you'll save the following information to a text file.</span></span> <span data-ttu-id="99e96-131">これらの値は、展開プロセスの後の手順で使用します。</span><span class="sxs-lookup"><span data-stu-id="99e96-131">These values are used in later steps in the deployment process.</span></span>

- <span data-ttu-id="99e96-132">AAD アプリケーション ID</span><span class="sxs-lookup"><span data-stu-id="99e96-132">AAD application ID</span></span>

- <span data-ttu-id="99e96-133">AAD アプリケーションシークレット</span><span class="sxs-lookup"><span data-stu-id="99e96-133">AAD application secret</span></span>

- <span data-ttu-id="99e96-134">テナント Id</span><span class="sxs-lookup"><span data-stu-id="99e96-134">Tenant Id</span></span>

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="99e96-135">手順 2: GitHub から Azure アカウントにコネクタ web サービスを展開する</span><span class="sxs-lookup"><span data-stu-id="99e96-135">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

<span data-ttu-id="99e96-136">次の手順では、facebook API を使用して facebook アカウントに接続し、データを抽出して Microsoft 365 にインポートできるようにする facebook Business pages コネクタアプリのソースコードを展開します。</span><span class="sxs-lookup"><span data-stu-id="99e96-136">The next step is to deploy the source code for the Facebook Business pages connector app that will use the Facebook API to connect to your Facebook account and extract data so you can import it to Microsoft 365.</span></span> <span data-ttu-id="99e96-137">組織用に展開する Facebook コネクタは、Facebook ビジネスページから、この手順で作成された Azure ストレージの場所にアイテムをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="99e96-137">The Facebook connector that you deploy for your organization will upload the items from your Facebook Business pages to the Azure Storage location that is created in this step.</span></span> <span data-ttu-id="99e96-138">Microsoft 365 コンプライアンスセンター (手順 5) で Facebook business pages コネクタを作成すると、インポートサービスによって Azure のストレージの場所から Microsoft 365 組織のメールボックスに Facebook ビジネスページのデータがコピーされます。</span><span class="sxs-lookup"><span data-stu-id="99e96-138">After you create a Facebook business pages connector in the Microsoft 365 compliance center (in Step 5), the Import service will copy the Facebook business pages data from the Azure Storage location to a mailbox in your Microsoft 365 organization.</span></span> <span data-ttu-id="99e96-139">前述の「[前提条件](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages)」セクションで説明したように、azure Storage アカウントを作成するには、有効な azure サブスクリプションを用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99e96-139">As previous explained in the [Prerequisites](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages) section, you must have a valid Azure subscription to create an Azure Storage account.</span></span>

<span data-ttu-id="99e96-140">詳細な手順については、「 [connector web service を GitHub から Azure アカウントに展開する](deploy-facebook-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99e96-140">For step-by-step instructions, see [Deploy the connector web service from GitHub to your Azure account](deploy-facebook-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account).</span></span>

<span data-ttu-id="99e96-141">この手順を完了するための手順については、次の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="99e96-141">In the step-by-step instructions to complete this step, you'll provide the following information:</span></span>

- <span data-ttu-id="99e96-142">APISecretKey: この手順の完了時にこのシークレットを作成します。</span><span class="sxs-lookup"><span data-stu-id="99e96-142">APISecretKey: You create this secret during the completion of this step.</span></span> <span data-ttu-id="99e96-143">手順5で使用します。</span><span class="sxs-lookup"><span data-stu-id="99e96-143">It's used in Step 5.</span></span>

- <span data-ttu-id="99e96-144">TenantId: 手順1で Azure Active Directory で Facebook connector アプリを作成した後にコピーした Microsoft 365 組織のテナント ID。</span><span class="sxs-lookup"><span data-stu-id="99e96-144">TenantId: The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 1.</span></span>

<span data-ttu-id="99e96-145">この手順を完了したら、Azure app service の URL (たとえば、) を必ずコピーしてください https://fbconnector.azurewebsites.net) 。</span><span class="sxs-lookup"><span data-stu-id="99e96-145">After completing this step, be sure to copy the Azure app service URL (for example, https://fbconnector.azurewebsites.net).</span></span> <span data-ttu-id="99e96-146">手順3、手順4、および手順5を完了するには、この URL を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99e96-146">You need to use this URL to complete Step 3, Step 4, and Step 5).</span></span>

## <a name="step-3-register-the-web-app-on-facebook"></a><span data-ttu-id="99e96-147">手順 3: Facebook で web アプリを登録する</span><span class="sxs-lookup"><span data-stu-id="99e96-147">Step 3: Register the web app on Facebook</span></span>

<span data-ttu-id="99e96-148">次の手順では、Facebook で新しいアプリを作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="99e96-148">The next step is to create and configure a new app on Facebook.</span></span> <span data-ttu-id="99e96-149">手順5で作成した Facebook business pages コネクタは、facebook web アプリを使用して、組織の Facebook ビジネスページからデータを取得する Facebook API と対話します。</span><span class="sxs-lookup"><span data-stu-id="99e96-149">The Facebook business pages connector that you create in Step 5 uses the Facebook web app to interact with the Facebook API to obtain data from your organization's Facebook Business pages.</span></span>

<span data-ttu-id="99e96-150">詳細な手順については、「 [Facebook アプリを登録する](deploy-facebook-connector.md#step-3-register-the-facebook-app)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99e96-150">For step-by-step instructions, see [Register the Facebook app](deploy-facebook-connector.md#step-3-register-the-facebook-app).</span></span>

<span data-ttu-id="99e96-151">この手順が完了したら (手順に従って)、次の情報をテキストファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="99e96-151">During the completion of this step (by following the step-by-step instructions), you save the following information to a text file.</span></span> <span data-ttu-id="99e96-152">これらの値は、手順4で Facebook connector アプリを構成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="99e96-152">These values are used to configure the Facebook connector app in Step 4.</span></span>

- <span data-ttu-id="99e96-153">Facebook アプリケーション ID</span><span class="sxs-lookup"><span data-stu-id="99e96-153">Facebook application ID</span></span>

- <span data-ttu-id="99e96-154">Facebook アプリケーションシークレット</span><span class="sxs-lookup"><span data-stu-id="99e96-154">Facebook application secret</span></span>

- <span data-ttu-id="99e96-155">Facebook webhook でトークンを確認する</span><span class="sxs-lookup"><span data-stu-id="99e96-155">Facebook webhooks verify token</span></span>

## <a name="step-4-configure-the-facebook-connector-app"></a><span data-ttu-id="99e96-156">手順 4: Facebook connector アプリを構成する</span><span class="sxs-lookup"><span data-stu-id="99e96-156">Step 4: Configure the Facebook connector app</span></span>

<span data-ttu-id="99e96-157">次の手順では、手順1で Azure web app リソースの作成時にアップロードした Facebook connector アプリに構成設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="99e96-157">The next step is to add configuration settings to the Facebook connector app that you uploaded when you created the Azure web app resource in Step 1.</span></span> <span data-ttu-id="99e96-158">これを行うには、コネクタアプリのホームページにアクセスして構成します。</span><span class="sxs-lookup"><span data-stu-id="99e96-158">You do this by going to the home page of your connector app and configuring it.</span></span>

<span data-ttu-id="99e96-159">詳細な手順については、「 [Facebook connector アプリを構成する](archive-facebook-data-with-sample-connector.md#step-4-configure-the-facebook-connector-app)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99e96-159">For step-by-step instructions, see [Configure the Facebook connector app](archive-facebook-data-with-sample-connector.md#step-4-configure-the-facebook-connector-app).</span></span>

<span data-ttu-id="99e96-160">この手順が完了すると (手順に従って)、次の情報が提供されます (前の手順を完了した後、テキストファイルにコピーしたことになります)。</span><span class="sxs-lookup"><span data-stu-id="99e96-160">During the completion of this step (by following the step-by-step instructions), you provide the following information (that you've copied to a text file after completing the previous steps):</span></span>

- <span data-ttu-id="99e96-161">Facebook アプリケーション ID (手順3で取得)</span><span class="sxs-lookup"><span data-stu-id="99e96-161">Facebook application ID (obtained in Step 3)</span></span>

- <span data-ttu-id="99e96-162">Facebook アプリケーションシークレット (手順3で取得)</span><span class="sxs-lookup"><span data-stu-id="99e96-162">Facebook application secret (obtained in Step 3)</span></span>

- <span data-ttu-id="99e96-163">Facebook webhook でトークンを確認する (手順3で取得)</span><span class="sxs-lookup"><span data-stu-id="99e96-163">Facebook webhooks verify token (obtained in Step 3)</span></span>

- <span data-ttu-id="99e96-164">Azure Active Directory アプリケーション ID (手順1で取得した AAD アプリケーション ID)</span><span class="sxs-lookup"><span data-stu-id="99e96-164">Azure Active Directory application ID (the AAD application ID obtained in Step 1)</span></span>

- <span data-ttu-id="99e96-165">Azure Active Directory アプリケーションシークレット (手順1で取得した AAD アプリケーションシークレット)</span><span class="sxs-lookup"><span data-stu-id="99e96-165">Azure Active Directory application secret (the AAD application secret obtained in Step 1)</span></span>

## <a name="step-5-set-up-a-facebook-business-pages-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="99e96-166">手順 5: Microsoft 365 コンプライアンスセンターで Facebook Business pages コネクタを設定する</span><span class="sxs-lookup"><span data-stu-id="99e96-166">Step 5: Set up a Facebook Business pages connector in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="99e96-167">最後の手順では、Microsoft 365 コンプライアンスセンターで、ユーザーが Facebook のビジネスページから Microsoft 365 の指定したメールボックスにデータをインポートするようにコネクタを設定します。</span><span class="sxs-lookup"><span data-stu-id="99e96-167">The final step is to set up the connector in the Microsoft 365 compliance center that will import data from your Facebook Business pages to a specified mailbox in Microsoft 365.</span></span> <span data-ttu-id="99e96-168">この手順を完了すると、Office 365 インポートサービスは、Facebook のビジネスページから Microsoft 365 へのデータのインポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="99e96-168">After you complete this step, the Office 365 Import service will start importing data from your Facebook Business pages to Microsoft 365.</span></span>

<span data-ttu-id="99e96-169">詳細な手順については、「 [Microsoft 365 コンプライアンスセンターで手順 5: Facebook コネクタを設定する](deploy-facebook-connector.md#step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99e96-169">For step-by-step instructions, see [Step 5: Set up a Facebook connector in the Microsoft 365 compliance center](deploy-facebook-connector.md#step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center).</span></span> 

<span data-ttu-id="99e96-170">この手順が完了すると (手順に従って)、次の情報が提供されます (手順を完了した後、テキストファイルにコピーしたことになります)。</span><span class="sxs-lookup"><span data-stu-id="99e96-170">During the completion of this step (by following the step-by-step instructions), you provide the following information (that you've copied to a text file after completing the steps).</span></span>

- <span data-ttu-id="99e96-171">AAD アプリケーション ID (手順1で取得)</span><span class="sxs-lookup"><span data-stu-id="99e96-171">AAD application ID (obtained in Step 1)</span></span>

- <span data-ttu-id="99e96-172">Azure app service の URL (手順1で取得) (例:https://fbconnector.azurewebsites.net)</span><span class="sxs-lookup"><span data-stu-id="99e96-172">Azure app service URL (obtained in Step 1; for example, https://fbconnector.azurewebsites.net)</span></span>

- <span data-ttu-id="99e96-173">APISecretKey (手順2で作成したもの)</span><span class="sxs-lookup"><span data-stu-id="99e96-173">APISecretKey (that you created in Step 2)</span></span>
