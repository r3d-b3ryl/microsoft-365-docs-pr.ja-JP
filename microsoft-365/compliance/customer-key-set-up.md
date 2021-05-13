---
title: 顧客キーの設定
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 顧客キーを設定する方法についてMicrosoft 365。
ms.openlocfilehash: e187c01a355cc9b926e892cb3326b5a527c714a4
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2021
ms.locfileid: "52344676"
---
# <a name="set-up-customer-key"></a><span data-ttu-id="54652-103">顧客キーの設定</span><span class="sxs-lookup"><span data-stu-id="54652-103">Set up Customer Key</span></span>

<span data-ttu-id="54652-104">顧客キーを使用すると、組織の暗号化キーを制御し、Microsoft 365を使用して Microsoft のデータ センターで保存されているデータを暗号化する構成を行います。</span><span class="sxs-lookup"><span data-stu-id="54652-104">With Customer Key, you control your organization's encryption keys and then configure Microsoft 365 to use them to encrypt your data at rest in Microsoft's data centers.</span></span> <span data-ttu-id="54652-105">つまり、顧客キーを使用すると、顧客は自分のキーを使用して、自分に属する暗号化の層を追加できます。</span><span class="sxs-lookup"><span data-stu-id="54652-105">In other words, Customer Key allows customers to add a layer of encryption that belongs to them, with their keys.</span></span>

<span data-ttu-id="54652-106">顧客キーを使用する前に Azure をOffice 365。</span><span class="sxs-lookup"><span data-stu-id="54652-106">Set up Azure before you can use Customer Key for Office 365.</span></span> <span data-ttu-id="54652-107">この記事では、必要な Azure リソースを作成および構成するために従う必要がある手順について説明し、次に、Azure リソースで顧客キーを設定する手順をOffice 365。</span><span class="sxs-lookup"><span data-stu-id="54652-107">This article describes the steps you need to follow to create and configure the required Azure resources and then provides the steps for setting up Customer Key in Office 365.</span></span> <span data-ttu-id="54652-108">Azure をセットアップした後で、組織内のさまざまなワークロード間でデータを暗号化するために割り当てるポリシーと、どのキーを割り当てるMicrosoft 365決定します。</span><span class="sxs-lookup"><span data-stu-id="54652-108">After you set up Azure, you determine which policy, and therefore, which keys, to assign to encrypt data across various Microsoft 365 workloads in your organization.</span></span> <span data-ttu-id="54652-109">顧客キーの詳細、または一般的な概要については、「サービスの暗号化と顧客キーの暗号化」を参照[Office 365。](customer-key-overview.md)</span><span class="sxs-lookup"><span data-stu-id="54652-109">For more information about Customer Key, or for a general overview, see [Service encryption with Customer Key in Office 365](customer-key-overview.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="54652-110">この記事のベスト プラクティスに従ってください。</span><span class="sxs-lookup"><span data-stu-id="54652-110">We strongly recommend that you follow the best practices in this article.</span></span> <span data-ttu-id="54652-111">これらは TIP および **IMPORTANT** として呼び **出されます**。</span><span class="sxs-lookup"><span data-stu-id="54652-111">These are called out as **TIP** and **IMPORTANT**.</span></span> <span data-ttu-id="54652-112">顧客キーを使用すると、組織全体と同じ規模のスコープを持つルート暗号化キーを制御できます。</span><span class="sxs-lookup"><span data-stu-id="54652-112">Customer Key gives you control over root encryption keys whose scope can be as large as your entire organization.</span></span> <span data-ttu-id="54652-113">つまり、これらのキーの間違いは大きな影響を与え、サービスの中断やデータの取り消しできない損失を引き起こす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="54652-113">This means that mistakes made with these keys can have a broad impact and may result in service interruptions or irrevocable loss of your data.</span></span>
  
## <a name="before-you-set-up-customer-key"></a><span data-ttu-id="54652-114">顧客キーを設定する前に</span><span class="sxs-lookup"><span data-stu-id="54652-114">Before you set up Customer Key</span></span>

<span data-ttu-id="54652-115">開始する前に、組織に適切な Azure サブスクリプションとライセンスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="54652-115">Before you get started, ensure that you have the appropriate Azure subscriptions and licensing for your organization.</span></span> <span data-ttu-id="54652-116">有料の Azure サブスクリプションを使用するには、Enterprise Agreementまたはクラウド サービス プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="54652-116">Use paid Azure Subscriptions using either an Enterprise Agreement or a Cloud Service Provider.</span></span> <span data-ttu-id="54652-117">クレジット カードベースの支払いは受け付けておかねない。</span><span class="sxs-lookup"><span data-stu-id="54652-117">Credit Card based payments are not accepted.</span></span> <span data-ttu-id="54652-118">請求に必要なアカウントを承認して設定します。</span><span class="sxs-lookup"><span data-stu-id="54652-118">Approve and set up the account needs for invoicing.</span></span> <span data-ttu-id="54652-119">無料、試用版、スポンサーシップ、MSDN サブスクリプション、および従来のサポートで取得したサブスクリプションは対象外です。</span><span class="sxs-lookup"><span data-stu-id="54652-119">Subscriptions you got through Free, Trial, Sponsorships, MSDN Subscriptions, and those under Legacy Support are not eligible.</span></span>

<span data-ttu-id="54652-120">Office 365E5、Microsoft 365 E5、Microsoft 365 E5 Compliance、Microsoft 365 E5ガバナンス SKU は&顧客キーを提供します。</span><span class="sxs-lookup"><span data-stu-id="54652-120">Office 365 E5, Microsoft 365 E5, Microsoft 365 E5 Compliance, and Microsoft 365 E5 Information Protection & Governance SKUs offer Customer Key.</span></span> <span data-ttu-id="54652-121">Office 365 Advanced ComplianceSKU は、新しいライセンスの調達に使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="54652-121">Office 365 Advanced Compliance SKU is no longer available for procuring new licenses.</span></span> <span data-ttu-id="54652-122">既存のOffice 365 Advanced Complianceライセンスは引き続きサポートされます。</span><span class="sxs-lookup"><span data-stu-id="54652-122">Existing Office 365 Advanced Compliance licenses will continue to be supported.</span></span>

<span data-ttu-id="54652-123">この記事の概念と手順については [、Azure Key Vault のドキュメントを参照](/azure/key-vault/) してください。</span><span class="sxs-lookup"><span data-stu-id="54652-123">To understand the concepts and procedures in this article, review the [Azure Key Vault](/azure/key-vault/) documentation.</span></span> <span data-ttu-id="54652-124">また、Azure で使用される用語 (Azure テナントなど) [をADします](/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant)。</span><span class="sxs-lookup"><span data-stu-id="54652-124">Also, become familiar with the terms used in Azure, for example, [Azure AD tenant](/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant).</span></span>
  
<span data-ttu-id="54652-125">ドキュメント以外のサポートが必要な場合は、Microsoft コンサルティング サービス (MCS)、プレミア フィールド エンジニアリング (PFE)、または Microsoft パートナーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="54652-125">If you need more support beyond the documentation, contact Microsoft Consulting Services (MCS), Premier Field Engineering (PFE), or a Microsoft partner for assistance.</span></span> <span data-ttu-id="54652-126">ドキュメントを含む顧客キーに関するフィードバックを提供するには、アイデア、提案、および視点をユーザーに customerkeyfeedback@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="54652-126">To provide feedback on Customer Key, including the documentation, send your ideas, suggestions, and perspectives to customerkeyfeedback@microsoft.com.</span></span>
  
## <a name="overview-of-steps-to-set-up-customer-key"></a><span data-ttu-id="54652-127">顧客キーを設定する手順の概要</span><span class="sxs-lookup"><span data-stu-id="54652-127">Overview of steps to set up Customer Key</span></span>

<span data-ttu-id="54652-128">顧客キーを設定するには、これらのタスクを一覧表示された順序で実行します。</span><span class="sxs-lookup"><span data-stu-id="54652-128">To set up Customer Key, complete these tasks in the listed order.</span></span> <span data-ttu-id="54652-129">この記事の残りの部分では、各タスクの詳細な手順を説明するか、プロセスの各ステップの詳細情報にリンクします。</span><span class="sxs-lookup"><span data-stu-id="54652-129">The rest of this article provides detailed instructions for each task, or links out to more information for each step in the process.</span></span>
  
<span data-ttu-id="54652-130">**Azure および Microsoft FastTrack では、次の情報を使用します。**</span><span class="sxs-lookup"><span data-stu-id="54652-130">**In Azure and Microsoft FastTrack:**</span></span>
  
<span data-ttu-id="54652-131">これらのタスクのほとんどを完了するには、リモートでユーザーに接続Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="54652-131">You'll complete most of these tasks by remotely connecting to Azure PowerShell.</span></span> <span data-ttu-id="54652-132">最適な結果を得る場合は、バージョン 4.4.0 以降のバージョンを使用Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="54652-132">For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>
  
- [<span data-ttu-id="54652-133">2 つの新しい Azure サブスクリプションを作成する</span><span class="sxs-lookup"><span data-stu-id="54652-133">Create two new Azure subscriptions</span></span>](#create-two-new-azure-subscriptions)

- [<span data-ttu-id="54652-134">顧客キーをアクティブ化する要求を送信Office 365</span><span class="sxs-lookup"><span data-stu-id="54652-134">Submit a request to activate Customer Key for Office 365</span></span>](#submit-a-request-to-activate-customer-key-for-office-365)
 
- [<span data-ttu-id="54652-135">必須の保持期間を使用するように Azure サブスクリプションを登録する</span><span class="sxs-lookup"><span data-stu-id="54652-135">Register Azure subscriptions to use a mandatory retention period</span></span>](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  <span data-ttu-id="54652-136">登録には 1 ~ 5 営業日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="54652-136">Registration can take from one to five business days.</span></span>

- [<span data-ttu-id="54652-137">各サブスクリプションにプレミアム Azure Key Vault を作成する</span><span class="sxs-lookup"><span data-stu-id="54652-137">Create a premium Azure Key Vault in each subscription</span></span>](#create-a-premium-azure-key-vault-in-each-subscription)

- [<span data-ttu-id="54652-138">各キー コンテナーにアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="54652-138">Assign permissions to each key vault</span></span>](#assign-permissions-to-each-key-vault)

- [<span data-ttu-id="54652-139">キー コンテナーでソフト削除が有効になっているか確認する</span><span class="sxs-lookup"><span data-stu-id="54652-139">Make sure soft delete is enabled on your key vaults</span></span>](#make-sure-soft-delete-is-enabled-on-your-key-vaults)

- [<span data-ttu-id="54652-140">キーを作成またはインポートして、各キー コンテナーにキーを追加する</span><span class="sxs-lookup"><span data-stu-id="54652-140">Add a key to each key vault either by creating or importing a key</span></span>](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [<span data-ttu-id="54652-141">キーの回復レベルを確認する</span><span class="sxs-lookup"><span data-stu-id="54652-141">Check the recovery level of your keys</span></span>](#check-the-recovery-level-of-your-keys)

- [<span data-ttu-id="54652-142">Azure Key Vault のバックアップ</span><span class="sxs-lookup"><span data-stu-id="54652-142">Back up Azure Key Vault</span></span>](#back-up-azure-key-vault)

- [<span data-ttu-id="54652-143">Azure Key Vault 構成設定の検証</span><span class="sxs-lookup"><span data-stu-id="54652-143">Validate Azure Key Vault configuration settings</span></span>](#validate-azure-key-vault-configuration-settings)

- [<span data-ttu-id="54652-144">各 Azure Key Vault キーの URI を取得する</span><span class="sxs-lookup"><span data-stu-id="54652-144">Obtain the URI for each Azure Key Vault key</span></span>](#obtain-the-uri-for-each-azure-key-vault-key)
  
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a><span data-ttu-id="54652-145">Azure Key Vault および Microsoft FastTrack for Customer Key のタスクを完了する</span><span class="sxs-lookup"><span data-stu-id="54652-145">Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key</span></span>

<span data-ttu-id="54652-146">Azure Key Vault でこれらのタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="54652-146">Complete these tasks in Azure Key Vault.</span></span> <span data-ttu-id="54652-147">顧客キーで使用するすべての DEP に対して、以下の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54652-147">You'll need to complete these steps for all DEPs you use with Customer Key.</span></span>
  
### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="54652-148">2 つの新しい Azure サブスクリプションを作成する</span><span class="sxs-lookup"><span data-stu-id="54652-148">Create two new Azure subscriptions</span></span>

<span data-ttu-id="54652-149">顧客キーには、2 つの Azure サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="54652-149">Customer Key requires two Azure subscriptions.</span></span> <span data-ttu-id="54652-150">ベスト プラクティスとして、顧客キーで使用する新しい Azure サブスクリプションを作成するようにお勧めします。</span><span class="sxs-lookup"><span data-stu-id="54652-150">As a best practice, Microsoft recommends that you create new Azure subscriptions for use with Customer Key.</span></span> <span data-ttu-id="54652-151">Azure Key Vault キーは、同じ Azure Active Directory (Microsoft Azure Active Directory) テナント内のアプリケーションにのみ承認できます。DEP が割り当てられる組織で使用されるのと同じ Azure AD テナントを使用して新しいサブスクリプションを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54652-151">Azure Key Vault keys can only be authorized for applications in the same Azure Active Directory (Microsoft Azure Active Directory) tenant, you must create the new subscriptions using the same Azure AD tenant used with your organization where the DEPs will be assigned.</span></span> <span data-ttu-id="54652-152">たとえば、組織でグローバル管理者特権を持つ仕事用または学校用のアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="54652-152">For example, using your work or school account that has global administrator privileges in your organization.</span></span> <span data-ttu-id="54652-153">詳細な手順については、「組織として [Azure にサインアップする」を参照してください](/azure/active-directory/fundamentals/sign-up-organization)。</span><span class="sxs-lookup"><span data-stu-id="54652-153">For detailed steps, see [Sign up for Azure as an organization](/azure/active-directory/fundamentals/sign-up-organization).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="54652-154">顧客キーには、データ暗号化ポリシー (DEP) ごとに 2 つのキーが必要です。</span><span class="sxs-lookup"><span data-stu-id="54652-154">Customer Key requires two keys for each data encryption policy (DEP).</span></span> <span data-ttu-id="54652-155">これを実現するには、2 つの Azure サブスクリプションを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54652-155">In order to achieve this, you must create two Azure subscriptions.</span></span> <span data-ttu-id="54652-156">ベスト プラクティスとして、組織の個別のメンバーが各サブスクリプションで 1 つのキーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54652-156">As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription.</span></span> <span data-ttu-id="54652-157">これらの Azure サブスクリプションを使用して、暗号化キーを管理する必要Office 365。</span><span class="sxs-lookup"><span data-stu-id="54652-157">You should only use these Azure subscriptions to administer encryption keys for Office 365.</span></span> <span data-ttu-id="54652-158">これにより、オペレーターの 1 人が誤って、意図的に、または悪意を持って削除したり、責任を負うキーを誤って管理したりした場合に、組織が保護されます。</span><span class="sxs-lookup"><span data-stu-id="54652-158">This protects your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible.</span></span>

<span data-ttu-id="54652-159">組織に対して作成できる Azure サブスクリプションの数に実際的な制限はありません。</span><span class="sxs-lookup"><span data-stu-id="54652-159">There is no practical limit to the number of Azure subscriptions that you can create for your organization.</span></span> <span data-ttu-id="54652-160">これらのベスト プラクティスに従って、カスタマー キーで使用されるリソースを管理しながら、人的エラーの影響を最小限に抑えます。</span><span class="sxs-lookup"><span data-stu-id="54652-160">Following these best practices will minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span>
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a><span data-ttu-id="54652-161">顧客キーをアクティブ化する要求を送信Office 365</span><span class="sxs-lookup"><span data-stu-id="54652-161">Submit a request to activate Customer Key for Office 365</span></span>

<span data-ttu-id="54652-162">2 つの新しい Azure サブスクリプションを作成したら、Microsoft FastTrack ポータルで適切な顧客キーオファー要求を [提出する必要があります](https://fasttrack.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="54652-162">Once you've created the two new Azure subscriptions, you'll need to submit the appropriate Customer Key offer request in the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span> <span data-ttu-id="54652-163">組織内の承認された指定に関してオファー フォームで行う選択は重要であり、顧客キー登録の完了に必要です。</span><span class="sxs-lookup"><span data-stu-id="54652-163">The selections that you make in the offer form about the authorized designations within your organization are critical and necessary for completion of Customer Key registration.</span></span> <span data-ttu-id="54652-164">組織内で選択された役割の役員は、顧客キーデータ暗号化ポリシーで使用されるすべてのキーを取り消して破棄する要求の信頼性を保証します。</span><span class="sxs-lookup"><span data-stu-id="54652-164">The officers in those selected roles within your organization ensure the authenticity of any request to revoke and destroy all keys used with a Customer Key data encryption policy.</span></span> <span data-ttu-id="54652-165">組織で使用するカスタマー キー DEP の種類ごとに、この手順を 1 回実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54652-165">You'll need to do this step once for each Customer Key DEP type that you intend to use for your organization.</span></span>

<span data-ttu-id="54652-166">**FastTrack チームは顧客キーのサポートを提供しない。Office 365 FastTrack ポータルを使用してフォームを送信し、顧客キーに関する関連するオファーを追跡するのに役立ちます。FastTrack 要求を送信したら、対応する顧客キーオンボーディング チームに連絡してオンボーディング プロセスを開始します。**</span><span class="sxs-lookup"><span data-stu-id="54652-166">**The FastTrack team doesn't provide assistance with Customer Key. Office 365 simply uses the FastTrack portal to allow you to submit the form and to help us track the relevant offers for Customer Key. Once you've submitted the FastTrack request, reach out to the corresponding Customer Key onboarding team to start the onboarding process.**</span></span>
  
<span data-ttu-id="54652-167">顧客キーをアクティブ化するオファーを送信するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="54652-167">To submit an offer to activate Customer Key, complete these steps:</span></span>
  
1. <span data-ttu-id="54652-168">組織でグローバル管理者のアクセス許可を持つ仕事または学校のアカウントを使用して [、Microsoft FastTrack ポータルにサインインします](https://fasttrack.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="54652-168">Using a work or school account that has global administrator permissions in your organization, sign in to the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span>

2. <span data-ttu-id="54652-169">ログインしたら、適切なドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="54652-169">Once you're logged in, select the appropriate domain.</span></span>

3. <span data-ttu-id="54652-170">選択したドメインで、 **上部のナビゲーション** バーから [サービスの要求] を選択し、利用可能なオファーの一覧を確認します。</span><span class="sxs-lookup"><span data-stu-id="54652-170">For the selected domain, choose **Request services** from the top navigation bar, and review the list of available offers.</span></span>

4. <span data-ttu-id="54652-171">該当するオファーの情報カードを選択します。</span><span class="sxs-lookup"><span data-stu-id="54652-171">Choose the information card for the offer that applies to you:</span></span>

   - <span data-ttu-id="54652-172">**複数のMicrosoft 365ワークロード:**[暗号化キー **の要求] ヘルプを選択Microsoft 365** します。</span><span class="sxs-lookup"><span data-stu-id="54652-172">**Multiple Microsoft 365 workloads:** Choose the **Request encryption key help for Microsoft 365** offer.</span></span>

   - <span data-ttu-id="54652-173">**Exchange OnlineとSkype for Business:**[暗号化キー **の要求] のヘルプを選択Exchange** します。</span><span class="sxs-lookup"><span data-stu-id="54652-173">**Exchange Online and Skype for Business:** Choose the **Request encryption key help for Exchange** offer.</span></span>

   - <span data-ttu-id="54652-174">**SharePoint、オンライン、OneDrive、およびTeamsします。**[暗号化キー **の要求] ヘルプを選択して、SharePointとOneDrive for Business** します。</span><span class="sxs-lookup"><span data-stu-id="54652-174">**SharePoint Online, OneDrive, and Teams files:** Choose the **Request encryption key help for SharePoint and OneDrive for Business** offer.</span></span>

5. <span data-ttu-id="54652-175">オファーの詳細を確認したら、[手順 2 に進む] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="54652-175">Once you've reviewed the offer details, choose **Continue to step 2**.</span></span>

6. <span data-ttu-id="54652-176">オファー フォームに該当する詳細情報と要求された情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="54652-176">Fill out all applicable details and requested information on the offer form.</span></span> <span data-ttu-id="54652-177">暗号化キーとデータの永続的で不可逆的な破壊を承認するために承認する組織の役員の選択に特に注意を払います。</span><span class="sxs-lookup"><span data-stu-id="54652-177">Pay particular attention to your selections for which officers of your organization you want to authorize to approve the permanent and irreversible destruction of encryption keys and data.</span></span> <span data-ttu-id="54652-178">フォームが完成したら、[送信] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="54652-178">Once you've completed the form, choose **Submit**.</span></span>

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="54652-179">必須の保持期間を使用するように Azure サブスクリプションを登録する</span><span class="sxs-lookup"><span data-stu-id="54652-179">Register Azure subscriptions to use a mandatory retention period</span></span>

<span data-ttu-id="54652-180">ルート暗号化キーが一時的または永続的に失われると、サービス操作が中断したり、壊滅的な操作を受け入れ、データが失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="54652-180">The temporary or permanent loss of root encryption keys can be disruptive or even catastrophic to service operation and can result in data loss.</span></span> <span data-ttu-id="54652-181">このため、Customer Key で使用されるリソースには強力な保護が必要です。</span><span class="sxs-lookup"><span data-stu-id="54652-181">For this reason, the resources used with Customer Key require strong protection.</span></span> <span data-ttu-id="54652-182">Customer Key で使用される Azure リソースはすべて、既定の構成を超える保護メカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="54652-182">All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration.</span></span> <span data-ttu-id="54652-183">必須の保持期間の Azure サブスクリプションにタグを付 *けまたは登録できます*。</span><span class="sxs-lookup"><span data-stu-id="54652-183">You can tag or register Azure subscriptions for a *mandatory retention period*.</span></span> <span data-ttu-id="54652-184">必須の保持期間によって、Azure サブスクリプションの即時および取り消し不可の取り消しが防止されます。</span><span class="sxs-lookup"><span data-stu-id="54652-184">A mandatory retention period prevents immediate and irrevocable cancellation of your Azure subscription.</span></span> <span data-ttu-id="54652-185">必須の保持期間に Azure サブスクリプションを登録するために必要な手順では、管理者チームとのMicrosoft 365必要です。</span><span class="sxs-lookup"><span data-stu-id="54652-185">The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Microsoft 365 team.</span></span> <span data-ttu-id="54652-186">このプロセスには、1 ~ 5 営業日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="54652-186">This process can take from one to five business days.</span></span> <span data-ttu-id="54652-187">以前は、必須の保持期間を "キャンセルしない" と呼ばれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="54652-187">Previously, mandatory retention period was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="54652-188">チームに連絡するMicrosoft 365、顧客キーで使用する Azure サブスクリプションごとに次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54652-188">Before contacting the Microsoft 365 team, you must do the following steps for each Azure subscription that you use with Customer Key.</span></span> <span data-ttu-id="54652-189">開始する前に、Azure PowerShell [Az](/powershell/azure/new-azureps-module-az)モジュールがインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="54652-189">Ensure that you have the [Azure PowerShell Az](/powershell/azure/new-azureps-module-az) module installed before you start.</span></span>
  
1. <span data-ttu-id="54652-190">サインインするには、Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="54652-190">Sign in with Azure PowerShell.</span></span> <span data-ttu-id="54652-191">手順については、「サインインする」[を参照Azure PowerShell。](/powershell/azure/authenticate-azureps)</span><span class="sxs-lookup"><span data-stu-id="54652-191">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="54652-192">必須の保持Register-AzProviderFeature使用するサブスクリプションを登録するには、Register-AzProviderFeatureコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="54652-192">Run the Register-AzProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span> <span data-ttu-id="54652-193">サブスクリプションごとにこのアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="54652-193">Complete this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. <span data-ttu-id="54652-194">プロセスを完了するには、Microsoft にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="54652-194">Contact Microsoft to complete the process.</span></span>

   - <span data-ttu-id="54652-195">個々のメールボックスに DEP を割り当てる顧客キーを有効Exchange Online、お問い[合 exock@microsoft.com。](mailto:exock@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="54652-195">For enabling Customer Key for assigning DEP to individual Exchange Online mailboxes, contact [exock@microsoft.com](mailto:exock@microsoft.com).</span></span>

   - <span data-ttu-id="54652-196">すべてのテナント ユーザーに対して SharePoint Online および OneDrive for Business コンテンツ (Teams ファイルを含む) を暗号化するために DEP を割り当てる顧客キーを有効にする場合は、spock@microsoft.com に[問い合 spock@microsoft.com。](mailto:spock@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="54652-196">For enabling Customer Key for assigning DEPs to encrypt SharePoint Online and OneDrive for Business content (including Teams files) for all tenant users, contact [spock@microsoft.com](mailto:spock@microsoft.com).</span></span>

   - <span data-ttu-id="54652-197">すべてのテナント ユーザーに対して複数の Microsoft 365 ワークロード (Exchange Online、Teams、MIP EDM) でコンテンツを暗号化するために DEP を割り当てる顧客キーを有効にする場合は、m365-ck@service.microsoft.com に[問い合 m365-ck@service.microsoft.com に問い合 m365-ck@service.microsoft.com。](mailto:m365-ck@service.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="54652-197">For enabling Customer Key for assigning DEPs to encrypt content across multiple Microsoft 365 workloads (Exchange Online, Teams, MIP EDM) for all tenant users, contact [m365-ck@service.microsoft.com](mailto:m365-ck@service.microsoft.com).</span></span>

- <span data-ttu-id="54652-198">メールに次の情報を含める。</span><span class="sxs-lookup"><span data-stu-id="54652-198">Include the following information in your email:</span></span>

   <span data-ttu-id="54652-199">**件名**: 顧客キー \<*Your tenant's fully qualified domain name*\></span><span class="sxs-lookup"><span data-stu-id="54652-199">**Subject**: Customer Key for \<*Your tenant's fully qualified domain name*\></span></span>

   <span data-ttu-id="54652-200">**本文**: 必須の保持期間を完了するサブスクリプションの Get-AzProviderFeatureを含める。</span><span class="sxs-lookup"><span data-stu-id="54652-200">**Body**:  Include the subscription IDs for which you want to complete the mandatory retention period  and the output of Get-AzProviderFeature for each subscription.</span></span>

   <span data-ttu-id="54652-201">このプロセスを完了するサービス レベル契約 (SLA) は、Microsoft がサブスクリプションを登録して必須の保持期間を使用すると通知 (および確認) された後、5 営業日です。</span><span class="sxs-lookup"><span data-stu-id="54652-201">The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period.</span></span>

4. <span data-ttu-id="54652-202">登録が完了したという通知を Microsoft から受け取った後、次のように Get-AzProviderFeature コマンドを実行して、登録の状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="54652-202">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzProviderFeature command as follows.</span></span> <span data-ttu-id="54652-203">確認された場合、Get-AzProviderFeatureコマンドは、Registration State プロパティの **[登録済** み] **の値を返** します。</span><span class="sxs-lookup"><span data-stu-id="54652-203">If verified, the Get-AzProviderFeature command returns a value of **Registered** for the **Registration State** property.</span></span> <span data-ttu-id="54652-204">サブスクリプションごとにこの手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="54652-204">Complete this step for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. <span data-ttu-id="54652-205">プロセスを完了するには、次のコマンドRegister-AzResourceProviderします。</span><span class="sxs-lookup"><span data-stu-id="54652-205">To complete the process, run the Register-AzResourceProvider command.</span></span> <span data-ttu-id="54652-206">サブスクリプションごとにこの手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="54652-206">Complete this step for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="54652-207">各サブスクリプションにプレミアム Azure Key Vault を作成する</span><span class="sxs-lookup"><span data-stu-id="54652-207">Create a premium Azure Key Vault in each subscription</span></span>

<span data-ttu-id="54652-208">キー コンテナーを作成する手順については[、「Azure Key Vault](/azure/key-vault/general/overview)の使用を開始する」に記載されています。このガイドでは、Azure PowerShell のインストールと起動、Azure サブスクリプションへの接続、リソース グループの作成、そのリソース グループ内のキー コンテナーの作成について説明します。</span><span class="sxs-lookup"><span data-stu-id="54652-208">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](/azure/key-vault/general/overview), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="54652-209">キー コンテナーを作成する場合は、SKU (標準または標準) を選択プレミアム。</span><span class="sxs-lookup"><span data-stu-id="54652-209">When you create a key vault, you must choose a SKU: either Standard or Premium.</span></span> <span data-ttu-id="54652-210">標準 SKU を使用すると、Azure Key Vault キーをソフトウェアで保護できます 。ハードウェア セキュリティ モジュール (HSM) キー保護はありません。また、プレミアム SKU では、キー コンテナー キーの保護のために HSM を使用できます。</span><span class="sxs-lookup"><span data-stu-id="54652-210">The Standard SKU allows Azure Key Vault keys to be protected with software - there's no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys.</span></span> <span data-ttu-id="54652-211">顧客キーは、いずれかの SKU を使用するキー コンテナーを受け入れるが、MICROSOFT では、SKU の一部のみを使用プレミアム強く推奨しています。</span><span class="sxs-lookup"><span data-stu-id="54652-211">Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU.</span></span> <span data-ttu-id="54652-212">どちらの種類のキーを使用する操作のコストも同じなので、コストの唯一の違いは、各 HSM で保護されたキーの 1 か月あたりのコストです。</span><span class="sxs-lookup"><span data-stu-id="54652-212">The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key.</span></span> <span data-ttu-id="54652-213">詳細については [、「Key Vault の価格」](https://azure.microsoft.com/pricing/details/key-vault/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54652-213">See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="54652-214">実稼働データプレミアム SKU キー コンテナーと HSM で保護されたキーを使用し、テストおよび検証の目的で標準 SKU キー コンテナーとキーのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="54652-214">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span>
  
<span data-ttu-id="54652-215">顧客キー Microsoft 365使用するサービスごとに、作成した 2 つの Azure サブスクリプションのそれぞれにキー コンテナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="54652-215">For each Microsoft 365 service with which you will use Customer Key, create a key vault in each of the two Azure subscriptions that you created.</span></span> <span data-ttu-id="54652-216">たとえば、カスタマー キーで Exchange Online、SharePoint Online、および複数ワークロードのシナリオで DEP を使用するには、3 組のキー コンテナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="54652-216">For example, to enable Customer Key to use DEPs for Exchange Online, SharePoint Online, and multi-workload scenarios, you'll create three pairs of key vaults.</span></span>
  
<span data-ttu-id="54652-217">コンテナーを関連付ける DEP の使用目的を反映するキー コンテナーの名前付け規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="54652-217">Use a naming convention for key vaults that reflects the intended use of the DEP with which you will associate the vaults.</span></span> <span data-ttu-id="54652-218">名前付け規則の推奨事項については、以下の「ベスト プラクティス」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="54652-218">See the Best Practices section below for naming convention recommendations.</span></span>
  
<span data-ttu-id="54652-219">データ暗号化ポリシーごとに、ペアにされた個別のコンテナー セットを作成します。</span><span class="sxs-lookup"><span data-stu-id="54652-219">Create a separate, paired set of vaults for each data encryption policy.</span></span> <span data-ttu-id="54652-220">たとえばExchange Onlineポリシーをメールボックスに割り当てるときに、データ暗号化ポリシーのスコープが選択されます。</span><span class="sxs-lookup"><span data-stu-id="54652-220">For Exchange Online, the scope of a data encryption policy is chosen by you when you assign the policy to mailbox.</span></span> <span data-ttu-id="54652-221">メールボックスには 1 つのポリシーのみを割り当て、最大 50 のポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="54652-221">A mailbox can have only one policy assigned, and you can create up to 50 policies.</span></span> <span data-ttu-id="54652-222">オンライン ポリシーのSharePointには、地理的な場所または地理的な場所にある組織内のすべてのデータが含 _まれます_。</span><span class="sxs-lookup"><span data-stu-id="54652-222">The scope of a SharePoint Online policy includes all of the data within an organization in a geographic location, or _geo_.</span></span> <span data-ttu-id="54652-223">複数ワークロード ポリシーのスコープには、すべてのユーザーでサポートされているワークロード全体のすべてのデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="54652-223">The scope for a multi-workload policy includes all of the data across the supported workloads for all users.</span></span>

<span data-ttu-id="54652-224">キー コンテナーの作成には Azure リソース グループの作成も必要です。キー コンテナーにはストレージ容量 (小さいですが) が必要で、有効にした場合は Key Vault ログも保存されたデータが生成されます。</span><span class="sxs-lookup"><span data-stu-id="54652-224">The creation of key vaults also requires the creation of Azure resource groups, since key vaults need storage capacity (though small) and Key Vault logging, if enabled, also generates stored data.</span></span> <span data-ttu-id="54652-225">ベスト プラクティスとして、Microsoft は個別の管理者を使用して各リソース グループを管理し、関連する顧客キー リソースを管理する一連の管理者に対応した管理を推奨します。</span><span class="sxs-lookup"><span data-stu-id="54652-225">As a best practice Microsoft recommends using separate administrators to manage each resource group, with the administration that's aligned with the set of administrators that will manage all related Customer Key resources.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="54652-226">可用性を最大化するには、Microsoft 365 サービスに近い地域にキー コンテナーを配置します。たとえば、Exchange Online 組織が北米にある場合は、キー コンテナーを北米に配置します。</span><span class="sxs-lookup"><span data-stu-id="54652-226">To maximize availability, place your key vaults in regions close to your Microsoft 365 service For example, if your Exchange Online organization is in North America, place your key vaults in North America.</span></span> <span data-ttu-id="54652-227">組織がExchange Onlineしている場合は、キー コンテナーをヨーロッパに配置します。</span><span class="sxs-lookup"><span data-stu-id="54652-227">If your Exchange Online organization is in Europe, place your key vaults in Europe.</span></span>
>
> <span data-ttu-id="54652-228">キー コンテナーに共通のプレフィックスを使用し、キー コンテナーとキーの使用と範囲の省略形を含める (たとえば、コンテナーが北アメリカにある Contoso SharePoint サービスの場合は、Contoso-CK-SP-NA-VaultA1 と Contoso-CK-SP-NA-VaultA2 の名前のペアを指定できます。</span><span class="sxs-lookup"><span data-stu-id="54652-228">Use a common prefix for key vaults, and include an abbreviation of the use and scope of the key vault and keys (e.g., for the Contoso SharePoint service where the vaults will be located in North America, a possible pair of names is Contoso-CK-SP-NA-VaultA1 and Contoso-CK-SP-NA-VaultA2.</span></span> <span data-ttu-id="54652-229">コンテナー名は Azure 内でグローバルに一意の文字列なので、目的の名前が既に他の Azure ユーザーによって要求されている場合に、目的の名前のバリエーションを試す必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="54652-229">Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers.</span></span> <span data-ttu-id="54652-230">2017 年 7 月現在、コンテナー名は変更できません。ベスト プラクティスは、セットアップの計画を作成し、2 人目を使用して計画が正しく実行されていることを確認する方法です。</span><span class="sxs-lookup"><span data-stu-id="54652-230">As of July 2017 vault names cannot be changed, so a best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span>
>
> <span data-ttu-id="54652-231">可能であれば、ペア以外の領域にコンテナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="54652-231">If possible, create your vaults in non-paired regions.</span></span> <span data-ttu-id="54652-232">ペアリングされた Azure リージョンは、サービス障害ドメイン全体で高可用性を提供します。</span><span class="sxs-lookup"><span data-stu-id="54652-232">Paired Azure regions provide high availability across service failure domains.</span></span> <span data-ttu-id="54652-233">したがって、地域のペアは、互いにバックアップ領域と見なされます。</span><span class="sxs-lookup"><span data-stu-id="54652-233">Therefore, regional pairs can be thought of as each other's backup region.</span></span> <span data-ttu-id="54652-234">つまり、1 つの地域に配置された Azure リソースは、ペアリングされた地域を通じて自動的にフォールト トレランスを取得します。</span><span class="sxs-lookup"><span data-stu-id="54652-234">This means that an Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region.</span></span> <span data-ttu-id="54652-235">このため、データ暗号化ポリシーで使用される 2 つのコンテナーに対してリージョンを選択すると、領域がペアになります。つまり、可用性の合計 2 つの領域だけが使用されます。</span><span class="sxs-lookup"><span data-stu-id="54652-235">For this reason, choosing regions for two vaults used in a data encryption policy where the regions are paired means that only a total of two regions of availability are in use.</span></span> <span data-ttu-id="54652-236">ほとんどの地域には 2 つの地域しか存在しないので、ペアリングされていない地域をまだ選択できません。</span><span class="sxs-lookup"><span data-stu-id="54652-236">Most geographies only have two regions, so it's not yet possible to select non-paired regions.</span></span> <span data-ttu-id="54652-237">可能であれば、データ暗号化ポリシーで使用する 2 つのコンテナーに対して、ペアリングされていない 2 つの領域を選択します。</span><span class="sxs-lookup"><span data-stu-id="54652-237">If possible, choose two non-paired regions for the two vaults used with a data encryption policy.</span></span> <span data-ttu-id="54652-238">これは、可用性の合計 4 つの地域の恩恵を受ける。</span><span class="sxs-lookup"><span data-stu-id="54652-238">This benefits from a total of four regions of availability.</span></span> <span data-ttu-id="54652-239">詳細については [、「Business continuity and disaster recovery (BCDR): Azure Paired Regions](/azure/best-practices-availability-paired-regions) for current list of region pairs」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54652-239">For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span>
  
### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="54652-240">各キー コンテナーにアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="54652-240">Assign permissions to each key vault</span></span>

<span data-ttu-id="54652-241">実装に応じて、キー コンテナーごとに 3 つのアクセス許可セットを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54652-241">You'll need to define three separate sets of permissions for each key vault, depending on your implementation.</span></span> <span data-ttu-id="54652-242">たとえば、次のそれぞれに 1 つのアクセス許可セットを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54652-242">For example, you will need to define one set of permissions for each of the following:</span></span>
  
- <span data-ttu-id="54652-243">**組織のキー** コンテナーの毎日の管理を行うキー コンテナー管理者。</span><span class="sxs-lookup"><span data-stu-id="54652-243">**Key vault administrators** that do day-to-day management of your key vault for your organization.</span></span> <span data-ttu-id="54652-244">これらのタスクには、バックアップ、作成、取得、インポート、リスト、復元が含まれます。</span><span class="sxs-lookup"><span data-stu-id="54652-244">These tasks include backup, create, get, import, list, and restore.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="54652-245">キー コンテナー管理者に割り当てられた一連のアクセス許可には、キーを削除するアクセス許可は含められていない。</span><span class="sxs-lookup"><span data-stu-id="54652-245">The set of permissions assigned to key vault administrators does not include the permission to delete keys.</span></span> <span data-ttu-id="54652-246">これは意図的で重要なプラクティスです。</span><span class="sxs-lookup"><span data-stu-id="54652-246">This is intentional and an important practice.</span></span> <span data-ttu-id="54652-247">暗号化キーを削除すると、データが完全に破棄されるので、通常は実行しません。</span><span class="sxs-lookup"><span data-stu-id="54652-247">Deleting encryption keys is not typically done, since doing so permanently destroys data.</span></span> <span data-ttu-id="54652-248">ベスト プラクティスとして、このアクセス許可をキー コンテナー管理者に既定で付与しない。</span><span class="sxs-lookup"><span data-stu-id="54652-248">As a best practice, do not grant this permission to key vault administrators by default.</span></span> <span data-ttu-id="54652-249">代わりに、これを重要なコンテナーの投稿者に予約し、結果の明確な理解が得られると、短期間で管理者に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="54652-249">Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span>
  
  <span data-ttu-id="54652-250">これらのアクセス許可を組織内のユーザーに割り当てるには、Azure サブスクリプションにサインインし、Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="54652-250">To assign these permissions to a user in your organization, sign in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="54652-251">手順については、「サインインする」[を参照Azure PowerShell。](/powershell/azure/authenticate-azureps)</span><span class="sxs-lookup"><span data-stu-id="54652-251">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

- <span data-ttu-id="54652-252">必要なアクセスSet-AzKeyVaultAccessPolicy割り当てるには、このコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="54652-252">Run the Set-AzKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   <span data-ttu-id="54652-253">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="54652-253">For example:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- <span data-ttu-id="54652-254">Azure **Key Vault 自体の** アクセス許可を変更できるキー コンテナーの投稿者。</span><span class="sxs-lookup"><span data-stu-id="54652-254">**Key vault contributors** that can change permissions on the Azure Key Vault itself.</span></span> <span data-ttu-id="54652-255">従業員がチームを離れるか、チームに参加する場合は、これらのアクセス許可を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54652-255">You'll need to change these permissions as employees leave or join your team.</span></span> <span data-ttu-id="54652-256">キー コンテナー管理者がキーを削除または復元するためのアクセス許可を正当に必要とするまれな状況では、アクセス許可を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54652-256">In the rare situation that the key vault administrators legitimately need permission to delete or restore a key you'll also need to change the permissions.</span></span> <span data-ttu-id="54652-257">この一連のキー コンテナー投稿者には、キー コンテナーの **共同作成者** ロールを付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54652-257">This set of key vault contributors needs to be granted the **Contributor** role on your key vault.</span></span> <span data-ttu-id="54652-258">このロールは、Azure リソース マネージャーを使用して割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="54652-258">You can assign this role by using Azure Resource Manager.</span></span> <span data-ttu-id="54652-259">詳細な手順については、「Use Role-Based Access Control を使用して Azure サブスクリプション リソースへの [アクセスを管理する」を参照してください](/azure/active-directory/role-based-access-control-configure)。</span><span class="sxs-lookup"><span data-stu-id="54652-259">For detailed steps, see [Use Role-Based Access Control to manage access to your Azure subscription resources](/azure/active-directory/role-based-access-control-configure).</span></span> <span data-ttu-id="54652-260">サブスクリプションを作成する管理者は、暗黙的にこのアクセス権を持ち、他の管理者を共同作成者ロールに割り当てる機能を持っています。</span><span class="sxs-lookup"><span data-stu-id="54652-260">The administrator who creates a subscription has this access implicitly, and the ability to assign other administrators to the Contributor role.</span></span>

- <span data-ttu-id="54652-261">顧客 **キー Microsoft 365** 使用するキー コンテナーごとにアプリケーションを管理するためのアクセス許可は、wrapKey、unwrapKey、および対応する Microsoft 365 サービス プリンシパルへのアクセス許可を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54652-261">**Permissions to Microsoft 365 applications** for every key vault that you use for Customer Key, you need to give wrapKey, unwrapKey, and get permissions to the corresponding Microsoft 365 Service Principal.</span></span> 

<span data-ttu-id="54652-262">サービス プリンシパルへのアクセスMicrosoft 365するには、次の構文を使用して **Set-AzKeyVaultAccessPolicy** コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="54652-262">To give permission to Microsoft 365 Service Principal, run the **Set-AzKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   <span data-ttu-id="54652-263">ここで、</span><span class="sxs-lookup"><span data-stu-id="54652-263">Where:</span></span>

   - <span data-ttu-id="54652-264">*コンテナー名* は、作成したキー コンテナーの名前です。</span><span class="sxs-lookup"><span data-stu-id="54652-264">*vault name* is the name of the key vault you created.</span></span>
   - <span data-ttu-id="54652-265">アプリExchange OnlineとSkype for Business、appID *Office 365置き換* える`00000002-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="54652-265">For Exchange Online and Skype for Business, replace  *Office 365 appID* with `00000002-0000-0ff1-ce00-000000000000`</span></span>
   - <span data-ttu-id="54652-266">[オンラインSharePoint、OneDrive for Business、Teamsファイルの場合は、appID Office 365 *置き換* える`00000003-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="54652-266">For SharePoint Online, OneDrive for Business, and Teams files, replace  *Office 365 appID* with `00000003-0000-0ff1-ce00-000000000000`</span></span>
   - <span data-ttu-id="54652-267">すべてのテナント ユーザーに適用されるマルチワークロード ポリシー (Exchange、Teams、MIP EDM) の場合は、appID Office 365 *に置き換* えてください。`c066d759-24ae-40e7-a56f-027002b5d3e4`</span><span class="sxs-lookup"><span data-stu-id="54652-267">For multi-workload policy (Exchange, Teams, MIP EDM) that applies to all tenant users, replace *Office 365 appID* with `c066d759-24ae-40e7-a56f-027002b5d3e4`</span></span>

  <span data-ttu-id="54652-268">例: ユーザーとユーザーのアクセス許可Exchange Online設定Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="54652-268">Example: Setting permissions for Exchange Online and Skype for Business:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  <span data-ttu-id="54652-269">例: オンライン、SharePoint、OneDrive for BusinessファイルTeams設定します。</span><span class="sxs-lookup"><span data-stu-id="54652-269">Example: Setting permissions for SharePoint Online, OneDrive for Business, and Teams files:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="make-sure-soft-delete-is-enabled-on-your-key-vaults"></a><span data-ttu-id="54652-270">キー コンテナーでソフト削除が有効になっているか確認する</span><span class="sxs-lookup"><span data-stu-id="54652-270">Make sure soft delete is enabled on your key vaults</span></span>

<span data-ttu-id="54652-271">キーをすばやく回復できると、誤ってまたは悪意を持って削除されたキーが原因で、サービスの停止が長く発生する可能性が低い。</span><span class="sxs-lookup"><span data-stu-id="54652-271">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys.</span></span> <span data-ttu-id="54652-272">顧客キーでキーを使用する前に、Soft Delete と呼ばれるこの構成を有効にします。</span><span class="sxs-lookup"><span data-stu-id="54652-272">Enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key.</span></span> <span data-ttu-id="54652-273">Soft Delete を有効にすると、削除から 90 日以内にキーまたはコンテナーをバックアップから復元せずに復元できます。</span><span class="sxs-lookup"><span data-stu-id="54652-273">Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="54652-274">キー コンテナーで Soft Delete を有効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="54652-274">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="54652-275">Azure サブスクリプションにサインインするには、Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="54652-275">Sign in to your Azure subscription with Windows PowerShell.</span></span> <span data-ttu-id="54652-276">手順については、「サインインする」[を参照Azure PowerShell。](/powershell/azure/authenticate-azureps)</span><span class="sxs-lookup"><span data-stu-id="54652-276">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="54652-277">[Get-AzKeyVault コマンドレットを実行](/powershell/module/az.keyvault/get-azkeyvault)します。</span><span class="sxs-lookup"><span data-stu-id="54652-277">Run the [Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet.</span></span> <span data-ttu-id="54652-278">この例では、 *コンテナー名* は、ソフト削除を有効にするキー コンテナーの名前です。</span><span class="sxs-lookup"><span data-stu-id="54652-278">In this example, *vault name* is the name of the key vault for which you're enabling soft delete:</span></span>

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. <span data-ttu-id="54652-279">**Get-AzKeyVault** コマンドレットを実行して、キー コンテナーに対してソフト削除が構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="54652-279">Confirm soft delete is configured for the key vault by running the **Get-AzKeyVault** cmdlet.</span></span> <span data-ttu-id="54652-280">キー コンテナーに対してソフト削除が適切に構成されている場合 _、Soft Delete Enabled_ プロパティは True の値を返 **します**。</span><span class="sxs-lookup"><span data-stu-id="54652-280">If soft delete is configured properly for the key vault, then the _Soft Delete Enabled_ property returns a value of **True**:</span></span>

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="54652-281">キーを作成またはインポートして、各キー コンテナーにキーを追加する</span><span class="sxs-lookup"><span data-stu-id="54652-281">Add a key to each key vault either by creating or importing a key</span></span>

<span data-ttu-id="54652-282">Azure Key Vault にキーを追加するには、2 つの方法があります。Key Vault で直接キーを作成するか、キーをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="54652-282">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key.</span></span> <span data-ttu-id="54652-283">Key Vault で直接キーを作成する方法は複雑ですが、キーをインポートすると、キーの生成方法を完全に制御できます。</span><span class="sxs-lookup"><span data-stu-id="54652-283">Creating a key directly in Key Vault is less complicated, but importing a key provides total control over how the key is generated.</span></span> <span data-ttu-id="54652-284">RSA キーを使用します。</span><span class="sxs-lookup"><span data-stu-id="54652-284">Use the RSA keys.</span></span> <span data-ttu-id="54652-285">Azure Key Vault では、楕円曲線キーを使用した折り返しとラップ解除はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="54652-285">Azure Key Vault doesn't support wrapping and unwrapping with elliptical curve keys.</span></span>
  
<span data-ttu-id="54652-286">キー コンテナーにキーを直接作成するには、次のように [Add-AzKeyVaultKey コマンドレット](/powershell/module/az.keyvault/add-azkeyvaultkey) を実行します。</span><span class="sxs-lookup"><span data-stu-id="54652-286">To create a key directly in your key vault, run the [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="54652-287">ここで、</span><span class="sxs-lookup"><span data-stu-id="54652-287">Where:</span></span>

- <span data-ttu-id="54652-288">*コンテナー名* は、キーを作成するキー コンテナーの名前です。</span><span class="sxs-lookup"><span data-stu-id="54652-288">*vault name* is the name of the key vault in which you want to create the key.</span></span>

- <span data-ttu-id="54652-289">*キー名* は、新しいキーを指定する名前です。</span><span class="sxs-lookup"><span data-stu-id="54652-289">*key name* is the name you want to give the new key.</span></span>

  > [!TIP]
  > <span data-ttu-id="54652-290">キー コンテナーの上記と同様の名前付け規則を使用してキーに名前を付ける。</span><span class="sxs-lookup"><span data-stu-id="54652-290">Name keys using a similar naming convention as described above for key vaults.</span></span> <span data-ttu-id="54652-291">この方法では、キー名のみを表示するツールでは、文字列は自己記述型です。</span><span class="sxs-lookup"><span data-stu-id="54652-291">This way, in tools that show only the key name, the string is self-describing.</span></span>
  
<span data-ttu-id="54652-292">キーを HSM で保護する場合は、必ず **、Destination** パラメーターの値としてHSM を指定し、それ以外の場合は[ソフトウェア] を指定 **します**。</span><span class="sxs-lookup"><span data-stu-id="54652-292">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the _Destination_ parameter, otherwise, specify **Software**.</span></span>

<span data-ttu-id="54652-293">例えば、</span><span class="sxs-lookup"><span data-stu-id="54652-293">For example,</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="54652-294">キーをキー コンテナーに直接インポートするには、nCipher nShield ハードウェア セキュリティ モジュールが必要です。</span><span class="sxs-lookup"><span data-stu-id="54652-294">To import a key directly into your key vault, you need to have a nCipher nShield Hardware Security Module.</span></span>
  
<span data-ttu-id="54652-295">一部の組織では、キーの証明を確立するためにこのアプローチを好み、次の構成証明も提供します。</span><span class="sxs-lookup"><span data-stu-id="54652-295">Some organizations prefer this approach to establish the provenance of their keys, and then this method also provides the following attestations:</span></span>
  
- <span data-ttu-id="54652-296">インポートに使用されるツールセットには、生成するキーの暗号化に使用されるキー Exchange キー (KEK) がエクスポート可能ではなく、nCipher によって製造された正規の HSM 内で生成される nCipher からの構成証明が含まれます。</span><span class="sxs-lookup"><span data-stu-id="54652-296">The toolset used for import includes attestation from nCipher that the Key Exchange Key (KEK) that is used to encrypt the key you generate is not exportable and is generated inside a genuine HSM that was manufactured by nCipher.</span></span>

- <span data-ttu-id="54652-297">ツールセットには、nCipher によって製造された正規の HSM で Azure Key Vault セキュリティの世界も生成されたという nCipher からの構成証明が含まれています。</span><span class="sxs-lookup"><span data-stu-id="54652-297">The toolset includes attestation from nCipher that the Azure Key Vault security world was also generated on a genuine HSM manufactured by nCipher.</span></span> <span data-ttu-id="54652-298">この構成証明は、Microsoft が本物の nCipher ハードウェアも使用しているという証明です。</span><span class="sxs-lookup"><span data-stu-id="54652-298">This attestation proves that Microsoft is also using genuine nCipher hardware.</span></span>

<span data-ttu-id="54652-299">セキュリティ グループに確認して、上記の構成証明が必要かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="54652-299">Check with your security group to determine if the above attestations are required.</span></span> <span data-ttu-id="54652-300">オンプレミスでキーを作成し、キー コンテナーにインポートする詳細な手順については [、「Azure Key Vault](/azure/key-vault/keys/hsm-protected-keys)の HSM で保護されたキーを生成および転送する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54652-300">For detailed steps to create a key on-premises and import it into your key vault, see [How to generate and transfer HSM-protected keys for Azure Key Vault](/azure/key-vault/keys/hsm-protected-keys).</span></span> <span data-ttu-id="54652-301">Azure の手順を使用して、各キー コンテナーにキーを作成します。</span><span class="sxs-lookup"><span data-stu-id="54652-301">Use the Azure instructions to create a key in each key vault.</span></span>
  
### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="54652-302">キーの回復レベルを確認する</span><span class="sxs-lookup"><span data-stu-id="54652-302">Check the recovery level of your keys</span></span>

<span data-ttu-id="54652-303">Microsoft 365 Azure Key Vault サブスクリプションが [キャンセルしない] に設定され、顧客キーで使用されるキーの削除が有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="54652-303">Microsoft 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled.</span></span> <span data-ttu-id="54652-304">サブスクリプションの設定を確認するには、キーの回復レベルを確認します。</span><span class="sxs-lookup"><span data-stu-id="54652-304">You can confirm you subscriptions settings by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="54652-305">キーの回復レベルを確認するには、次Azure PowerShell、Get-AzKeyVaultKeyコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="54652-305">To check the recovery level of a key, in Azure PowerShell, run the Get-AzKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

<span data-ttu-id="54652-306">Recovery _Level_ プロパティが **Recoverable+ProtectedSubscription** の値以外の値を返す場合は、サブスクリプションを [キャンセルしない] リストに入れ、各キー コンテナーでソフト削除が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="54652-306">If the _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, ensure that you have put the subscription on the Do Not Cancel list and that you have soft delete enabled on each of your key vaults.</span></span>
  
### <a name="back-up-azure-key-vault"></a><span data-ttu-id="54652-307">Azure Key Vault のバックアップ</span><span class="sxs-lookup"><span data-stu-id="54652-307">Back up Azure Key Vault</span></span>

<span data-ttu-id="54652-308">作成直後またはキーに対する変更の直後に、バックアップを実行し、バックアップのコピーをオンラインとオフラインの両方で保存します。</span><span class="sxs-lookup"><span data-stu-id="54652-308">Immediately following creation or any change to a key, perform a backup and store copies of the backup, both online and offline.</span></span> <span data-ttu-id="54652-309">オフライン コピーを任意のネットワークに接続しない。</span><span class="sxs-lookup"><span data-stu-id="54652-309">Don't connect offline copies to any network.</span></span> <span data-ttu-id="54652-310">代わりに、物理的な安全な保管場所や商用ストレージ施設など、オフラインの場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="54652-310">Instead store them in an offline location, such as in a physical safe or commercial storage facility.</span></span> <span data-ttu-id="54652-311">障害が発生した場合にアクセスできる場所に、バックアップの少なくとも 1 つのコピーを保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54652-311">At least one copy of the backup should be stored in a location that will be accessible if a disaster occurs.</span></span> <span data-ttu-id="54652-312">バックアップ BLOB は、Key Vault キーを完全に破棄するか、操作不能にレンダリングする場合にキー マテリアルを復元する唯一の手段です。</span><span class="sxs-lookup"><span data-stu-id="54652-312">The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable.</span></span> <span data-ttu-id="54652-313">Azure Key Vault の外部であり、Azure Key Vault にインポートされたキーは、顧客キーがキーを使用するために必要なメタデータが外部キーと一緒に存在しないので、バックアップとして修飾されません。</span><span class="sxs-lookup"><span data-stu-id="54652-313">Keys that are external to Azure Key Vault and imported to Azure Key Vault don't qualify as a backup because the metadata necessary for Customer Key to use the key doesn't exist with the external key.</span></span> <span data-ttu-id="54652-314">顧客キーを使用した復元操作には、Azure Key Vault から取得したバックアップのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="54652-314">Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key.</span></span> <span data-ttu-id="54652-315">したがって、キーのアップロードまたは作成後に Azure Key Vault のバックアップを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54652-315">Therefore, you must create a backup of Azure Key Vault after you upload or create a key.</span></span>
  
<span data-ttu-id="54652-316">Azure Key Vault キーのバックアップを作成するには [、Backup-AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) コマンドレットを次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="54652-316">To create a backup of an Azure Key Vault key, run the [Backup-AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet as follows:</span></span>

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

<span data-ttu-id="54652-317">出力ファイルで接尾辞を使用してください `.backup` 。</span><span class="sxs-lookup"><span data-stu-id="54652-317">Ensure that your output file uses the suffix `.backup`.</span></span>
  
<span data-ttu-id="54652-318">このコマンドレットから生成された出力ファイルは暗号化され、Azure Key Vault の外部では使用できません。</span><span class="sxs-lookup"><span data-stu-id="54652-318">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault.</span></span> <span data-ttu-id="54652-319">バックアップは、バックアップの取得元の Azure サブスクリプションにのみ復元できます。</span><span class="sxs-lookup"><span data-stu-id="54652-319">The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
> [!TIP]
> <span data-ttu-id="54652-320">出力ファイルの場合は、コンテナー名とキー名の組み合わせを選択します。</span><span class="sxs-lookup"><span data-stu-id="54652-320">For the output file, choose a combination of your vault name and key name.</span></span> <span data-ttu-id="54652-321">これにより、ファイル名が自己記述的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="54652-321">This will make the file name self-describing.</span></span> <span data-ttu-id="54652-322">また、バックアップ ファイル名が衝突しないことです。</span><span class="sxs-lookup"><span data-stu-id="54652-322">It will also ensure that backup file names do not collide.</span></span>
  
<span data-ttu-id="54652-323">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="54652-323">For example:</span></span>
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -OutputFile Contoso-CK-EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="54652-324">Azure Key Vault 構成設定の検証</span><span class="sxs-lookup"><span data-stu-id="54652-324">Validate Azure Key Vault configuration settings</span></span>

<span data-ttu-id="54652-325">DEP でキーを使用する前の検証はオプションですが、強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="54652-325">Validating before using keys in a DEP is optional, but highly recommended.</span></span> <span data-ttu-id="54652-326">この記事で説明する以外のキーとコンテナーをセットアップする手順を使用する場合は、カスタマー キーを構成する前に、Azure Key Vault リソースの正常性を検証してください。</span><span class="sxs-lookup"><span data-stu-id="54652-326">If you use steps to set up your keys and vaults other than the ones described in this article, validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="54652-327">キーに 、および操作 `get` が有効 `wrapKey` になっている `unwrapKey` か確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="54652-327">To verify that your keys have `get`, `wrapKey`, and `unwrapKey` operations enabled:</span></span>
  
<span data-ttu-id="54652-328">[Get-AzKeyVault コマンドレットを次](/powershell/module/az.keyvault/get-azkeyvault)のように実行します。</span><span class="sxs-lookup"><span data-stu-id="54652-328">Run the [Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="54652-329">出力で、アクセス ポリシーを探し、必要に応じて Exchange Online ID (GUID) または SharePoint オンライン ID (GUID) を探します。</span><span class="sxs-lookup"><span data-stu-id="54652-329">In the output, look for the Access Policy and for the Exchange Online identity (GUID) or the SharePoint Online identity (GUID) as appropriate.</span></span> <span data-ttu-id="54652-330">上記の 3 つのアクセス許可はすべて[キーへのアクセス許可] の下に表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54652-330">All three of the above permissions must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="54652-331">アクセス ポリシーの構成が正しくない場合は、次のように Set-AzKeyVaultAccessPolicyコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="54652-331">If the access policy configuration is incorrect, run the Set-AzKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

<span data-ttu-id="54652-332">たとえば、次のExchange OnlineとSkype for Business。</span><span class="sxs-lookup"><span data-stu-id="54652-332">For example, for Exchange Online and Skype for Business:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="54652-333">たとえば、[オンライン] と [SharePoint] のOneDrive for Business。</span><span class="sxs-lookup"><span data-stu-id="54652-333">For example, for SharePoint Online and OneDrive for Business:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-SP-NA-VaultA1
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="54652-334">キーに有効期限が設定されていないことを確認するには [、Get-AzKeyVaultKey](/powershell/module/az.keyvault/get-azkeyvault) コマンドレットを次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="54652-334">To verify that an expiration date isn't set for your keys, run the [Get-AzKeyVaultKey](/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

<span data-ttu-id="54652-335">顧客キーは有効期限が切れたキーを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="54652-335">Customer Key can't use an expired key.</span></span> <span data-ttu-id="54652-336">有効期限が切れたキーで試行された操作は失敗し、サービスが停止する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="54652-336">Operations attempted with an expired key will fail, and possibly result in a service outage.</span></span> <span data-ttu-id="54652-337">顧客キーで使用するキーには有効期限が設定されません。</span><span class="sxs-lookup"><span data-stu-id="54652-337">We strongly recommend that keys used with Customer Key don't have an expiration date.</span></span> <span data-ttu-id="54652-338">有効期限を設定すると、削除できませんが、別の日付に変更できます。</span><span class="sxs-lookup"><span data-stu-id="54652-338">An expiration date, once set, cannot be removed, but can be changed to a different date.</span></span> <span data-ttu-id="54652-339">有効期限が設定されているキーを使用する必要がある場合は、有効期限の値を 12/31/9999 に変更します。</span><span class="sxs-lookup"><span data-stu-id="54652-339">If a key must be used that has an expiration date set, change the expiration value to 12/31/9999.</span></span> <span data-ttu-id="54652-340">有効期限が 12/31/9999 以外の日付に設定されているキーは、Microsoft 365渡しません。</span><span class="sxs-lookup"><span data-stu-id="54652-340">Keys with an expiration date set to a date other than 12/31/9999 won't pass Microsoft 365 validation.</span></span>
  
<span data-ttu-id="54652-341">12/31/9999 以外の値に設定されている有効期限を変更するには、次のように [Update-AzKeyVaultKey](/powershell/module/az.keyvault/update-azkeyvaultkey) コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="54652-341">To change an expiration date that has been set to any value other than 12/31/9999, run the [Update-AzKeyVaultKey](/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> <span data-ttu-id="54652-342">顧客キーで使用する暗号化キーに有効期限を設定しません。</span><span class="sxs-lookup"><span data-stu-id="54652-342">Don't set expiration dates on encryption keys you use with Customer Key.</span></span>
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="54652-343">各 Azure Key Vault キーの URI を取得する</span><span class="sxs-lookup"><span data-stu-id="54652-343">Obtain the URI for each Azure Key Vault key</span></span>

<span data-ttu-id="54652-344">キー コンテナーをセットアップしてキーを追加したら、次のコマンドを実行して、各キー コンテナーのキーの URI を取得します。</span><span class="sxs-lookup"><span data-stu-id="54652-344">Once you've set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault.</span></span> <span data-ttu-id="54652-345">これらの URI は、後で各 DEP を作成して割り当てるときに使用します。したがって、この情報を安全な場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="54652-345">You'll use these URIs when you create and assign each DEP later, so save this information in a safe place.</span></span> <span data-ttu-id="54652-346">キー コンテナーごとにこのコマンドを 1 回実行します。</span><span class="sxs-lookup"><span data-stu-id="54652-346">Run this command once for each key vault.</span></span>
  
<span data-ttu-id="54652-347">次のAzure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="54652-347">In Azure PowerShell:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="next-steps"></a><span data-ttu-id="54652-348">次の手順</span><span class="sxs-lookup"><span data-stu-id="54652-348">Next steps</span></span>

<span data-ttu-id="54652-349">この記事の手順を完了したら、DEP を作成して割り当てる準備ができました。</span><span class="sxs-lookup"><span data-stu-id="54652-349">Once you've completed the steps in this article, you're ready to create and assign DEPs.</span></span> <span data-ttu-id="54652-350">手順については、「顧客キーの [管理」を参照してください](customer-key-manage.md)。</span><span class="sxs-lookup"><span data-stu-id="54652-350">For instructions, see [Manage Customer Key](customer-key-manage.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="54652-351">関連記事</span><span class="sxs-lookup"><span data-stu-id="54652-351">Related articles</span></span>

- [<span data-ttu-id="54652-352">カスタマー キーによるサービスの暗号化</span><span class="sxs-lookup"><span data-stu-id="54652-352">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="54652-353">顧客キーの管理</span><span class="sxs-lookup"><span data-stu-id="54652-353">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="54652-354">カスタマー キーまたは可用性キーをローリングまたはローテーションする</span><span class="sxs-lookup"><span data-stu-id="54652-354">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="54652-355">可用性キーの詳細</span><span class="sxs-lookup"><span data-stu-id="54652-355">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="54652-356">サービスの暗号化</span><span class="sxs-lookup"><span data-stu-id="54652-356">Service Encryption</span></span>](office-365-service-encryption.md)