---
title: アプリケーション レベルで顧客キーを設定する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Microsoft 365 for Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business、Teams ファイルのカスタマー キーをセットアップする方法について説明します。
ms.openlocfilehash: a7a0c807b8778960d423d6b7d8afc20430ba89ad
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922721"
---
# <a name="set-up-customer-key-at-the-application-level"></a><span data-ttu-id="5a404-103">アプリケーション レベルで顧客キーを設定する</span><span class="sxs-lookup"><span data-stu-id="5a404-103">Set up Customer Key at the application level</span></span>

<span data-ttu-id="5a404-104">顧客キーを使用すると、組織の暗号化キーを制御し、Microsoft 365 を構成して、Microsoft のデータ センターで保存されているデータを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="5a404-104">With Customer Key, you control your organization's encryption keys and then configure Microsoft 365 to use them to encrypt your data at rest in Microsoft's data centers.</span></span> <span data-ttu-id="5a404-105">つまり、顧客キーを使用すると、顧客は自分のキーを使用して、自分に属する暗号化の層を追加できます。</span><span class="sxs-lookup"><span data-stu-id="5a404-105">In other words, Customer Key allows customers to add a layer of encryption that belongs to them, with their keys.</span></span> <span data-ttu-id="5a404-106">保存データには、メールボックスに保存されている Exchange Online および Skype for Business からのデータと、SharePoint Online および OneDrive for Business に保存されているファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5a404-106">Data at rest includes data from Exchange Online and Skype for Business that is stored in mailboxes and files that are stored in SharePoint Online and OneDrive for Business.</span></span>

<span data-ttu-id="5a404-107">顧客キーを 365 に使用するには、Azure をOfficeがあります。</span><span class="sxs-lookup"><span data-stu-id="5a404-107">You must set up Azure before you can use Customer Key for Office 365.</span></span> <span data-ttu-id="5a404-108">この記事では、必要な Azure リソースを作成および構成するために従う必要がある手順について説明し、365 でカスタマー キーを設定する手順Officeします。</span><span class="sxs-lookup"><span data-stu-id="5a404-108">This article describes the steps you need to follow to create and configure the required Azure resources and then provides the steps for setting up Customer Key in Office 365.</span></span> <span data-ttu-id="5a404-109">Azure のセットアップが完了したら、組織内のメールボックスとファイルに割り当てるポリシー、つまりどのキーを割り当てるか決定します。</span><span class="sxs-lookup"><span data-stu-id="5a404-109">After you have completed Azure setup, you determine which policy, and therefore, which keys, to assign to mailboxes and files in your organization.</span></span> <span data-ttu-id="5a404-110">ポリシーを割り当てないメールボックスとファイルは、Microsoft によって制御および管理される暗号化ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="5a404-110">Mailboxes and files for which you don't assign a policy will use encryption policies that are controlled and managed by Microsoft.</span></span> <span data-ttu-id="5a404-111">顧客キーの詳細、または一般的な概要については、「Service Encryption with Customer Key in customer Key in Office [365」を参照してください](customer-key-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="5a404-111">For more information about Customer Key, or for a general overview, see [Service encryption with Customer Key in Office 365](customer-key-overview.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5a404-112">この記事のベスト プラクティスに従ってください。</span><span class="sxs-lookup"><span data-stu-id="5a404-112">We strongly recommend that you follow the best practices in this article.</span></span> <span data-ttu-id="5a404-113">これらは TIP および **IMPORTANT** として呼び **出されます**。</span><span class="sxs-lookup"><span data-stu-id="5a404-113">These are called out as **TIP** and **IMPORTANT**.</span></span> <span data-ttu-id="5a404-114">顧客キーを使用すると、組織全体と同じ規模のスコープを持つルート暗号化キーを制御できます。</span><span class="sxs-lookup"><span data-stu-id="5a404-114">Customer Key gives you control over root encryption keys whose scope can be as large as your entire organization.</span></span> <span data-ttu-id="5a404-115">つまり、これらのキーの間違いは大きな影響を与え、サービスの中断やデータの取り消しできない損失を引き起こす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5a404-115">This means that mistakes made with these keys can have a broad impact and may result in service interruptions or irrevocable loss of your data.</span></span>
  
## <a name="before-you-set-up-customer-key"></a><span data-ttu-id="5a404-116">顧客キーを設定する前に</span><span class="sxs-lookup"><span data-stu-id="5a404-116">Before you set up Customer Key</span></span>

<span data-ttu-id="5a404-117">開始する前に、組織に適切なライセンスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a404-117">Before you get started, ensure that you have the appropriate licensing for your organization.</span></span> <span data-ttu-id="5a404-118">クラウド サービス プロバイダーまたはクラウド サービス プロバイダーを使用して、支払マイクロソフトエンタープライズ契約 Azure サブスクリプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="5a404-118">Use a paid, invoiced Azure Subscription using either an Enterprise Agreement or a Cloud Service Provider.</span></span> <span data-ttu-id="5a404-119">Pay As You Go プランまたはクレジット カードを使用して購入した Azure サブスクリプションは、顧客キーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5a404-119">Azure Subscriptions purchased using Pay As You Go plans or using a credit card aren't supported for Customer Key.</span></span> <span data-ttu-id="5a404-120">2020 年 4 月 1 日より、Office 365 のカスタマー キーは、Office 365 E5、M365 E5、M365 E5 コンプライアンス、M365 E5 情報保護 & ガバナンス SKU で提供されます。</span><span class="sxs-lookup"><span data-stu-id="5a404-120">Starting April 1, 2020, Customer Key in Office 365 is offered in Office 365 E5, M365 E5, M365 E5 Compliance, and M365 E5 Information Protection & Governance SKUs.</span></span> <span data-ttu-id="5a404-121">Office 365 Advanced Compliance SKU は、新しいライセンスの調達に使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="5a404-121">Office 365 Advanced Compliance SKU is no longer available for procuring new licenses.</span></span> <span data-ttu-id="5a404-122">既存のOffice 365 Advanced Compliance ライセンスは引き続きサポートされます。</span><span class="sxs-lookup"><span data-stu-id="5a404-122">Existing Office 365 Advanced Compliance licenses will continue to be supported.</span></span>

<span data-ttu-id="5a404-123">この記事の概念と手順については [、Azure Key Vault のドキュメントを参照](/azure/key-vault/) してください。</span><span class="sxs-lookup"><span data-stu-id="5a404-123">To understand the concepts and procedures in this article, review the [Azure Key Vault](/azure/key-vault/) documentation.</span></span> <span data-ttu-id="5a404-124">また、Azure で使用される用語 (Azure テナントなど) [をADします](/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant)。</span><span class="sxs-lookup"><span data-stu-id="5a404-124">Also, become familiar with the terms used in Azure, for example, [Azure AD tenant](/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant).</span></span>

<span data-ttu-id="5a404-125">FastTrack は、顧客キーの登録に使用される必要なテナントおよびサービス構成情報を収集するためにのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="5a404-125">FastTrack is only used to collect the required tenant and service configuration information used to register for Customer Key.</span></span> <span data-ttu-id="5a404-126">顧客キーオファーは FastTrack 経由で公開され、お客様とパートナーが同じ方法で必要な情報を提出する際に便利です。</span><span class="sxs-lookup"><span data-stu-id="5a404-126">The Customer Key Offers are published via FastTrack so that it is convenient for you and our partners to submit the required information using the same method.</span></span> <span data-ttu-id="5a404-127">FastTrack を使用すると、オファーで提供するデータを簡単にアーカイブできます。</span><span class="sxs-lookup"><span data-stu-id="5a404-127">FastTrack also makes it easy to archive the data that you provide in the Offer.</span></span>
  
<span data-ttu-id="5a404-128">ドキュメント以外のサポートが必要な場合は、Microsoft コンサルティング サービス (MCS)、プレミア フィールド エンジニアリング (PFE)、または Microsoft パートナーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="5a404-128">If you need more support beyond the documentation, contact Microsoft Consulting Services (MCS), Premier Field Engineering (PFE), or a Microsoft partner for assistance.</span></span> <span data-ttu-id="5a404-129">ドキュメントを含む顧客キーに関するフィードバックを提供するには、アイデア、提案、および視点をユーザーに customerkeyfeedback@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="5a404-129">To provide feedback on Customer Key, including the documentation, send your ideas, suggestions, and perspectives to customerkeyfeedback@microsoft.com.</span></span>
  
## <a name="overview-of-steps-to-set-up-customer-key"></a><span data-ttu-id="5a404-130">顧客キーを設定する手順の概要</span><span class="sxs-lookup"><span data-stu-id="5a404-130">Overview of steps to set up Customer Key</span></span>

<span data-ttu-id="5a404-131">顧客キーを設定するには、これらのタスクを一覧表示された順序で実行します。</span><span class="sxs-lookup"><span data-stu-id="5a404-131">To set up Customer Key, complete these tasks in the listed order.</span></span> <span data-ttu-id="5a404-132">この記事の残りの部分では、各タスクの詳細な手順を説明するか、プロセスの各ステップの詳細情報にリンクします。</span><span class="sxs-lookup"><span data-stu-id="5a404-132">The rest of this article provides detailed instructions for each task, or links out to more information for each step in the process.</span></span>
  
<span data-ttu-id="5a404-133">**Azure および Microsoft FastTrack では、次の情報を使用します。**</span><span class="sxs-lookup"><span data-stu-id="5a404-133">**In Azure and Microsoft FastTrack:**</span></span>
  
<span data-ttu-id="5a404-134">これらのほとんどのタスクは、Azure PowerShell にリモートで接続して完了します。</span><span class="sxs-lookup"><span data-stu-id="5a404-134">You will complete most of these tasks by remotely connecting to Azure PowerShell.</span></span> <span data-ttu-id="5a404-135">最適な結果を得る場合は、バージョン 4.4.0 以降の Azure PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="5a404-135">For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>
  
- [<span data-ttu-id="5a404-136">2 つの新しい Azure サブスクリプションを作成する</span><span class="sxs-lookup"><span data-stu-id="5a404-136">Create two new Azure subscriptions</span></span>](#create-two-new-azure-subscriptions)

- [<span data-ttu-id="5a404-137">必須の保持期間を使用するように Azure サブスクリプションを登録する</span><span class="sxs-lookup"><span data-stu-id="5a404-137">Register Azure subscriptions to use a mandatory retention period</span></span>](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  <span data-ttu-id="5a404-138">登録には 1 ~ 5 営業日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5a404-138">Registration can take from one to five business days.</span></span>

- [<span data-ttu-id="5a404-139">顧客キーをアクティブ化する要求を 365 Officeする</span><span class="sxs-lookup"><span data-stu-id="5a404-139">Submit a request to activate Customer Key for Office 365</span></span>](#submit-a-request-to-activate-customer-key-for-office-365)

<span data-ttu-id="5a404-140">2 つの新しい Azure サブスクリプションを作成したら、Microsoft FastTrack ポータルでホストされている Web フォームを完了して、適切な顧客キー オファー要求を提出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a404-140">Once you've created the two new Azure subscriptions, you'll need to submit the appropriate Customer Key offer request by completing a web form that is hosted in the Microsoft FastTrack portal.</span></span> <span data-ttu-id="5a404-141">**FastTrack チームは顧客キーのサポートを提供しない。Office FastTrack** ポータルを使用してフォームを送信し、顧客キーに関する関連するオファーを追跡するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5a404-141">**The FastTrack team doesn't provide assistance with Customer Key. Office simply uses the FastTrack portal to allow you to submit the form and to help us track the relevant offers for Customer Key**.</span></span>

- [<span data-ttu-id="5a404-142">各サブスクリプションにプレミアム Azure Key Vault を作成する</span><span class="sxs-lookup"><span data-stu-id="5a404-142">Create a premium Azure Key Vault in each subscription</span></span>](#create-a-premium-azure-key-vault-in-each-subscription)

- [<span data-ttu-id="5a404-143">各キー コンテナーにアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="5a404-143">Assign permissions to each key vault</span></span>](#assign-permissions-to-each-key-vault)

- [<span data-ttu-id="5a404-144">キー コンテナーでソフト削除を有効にして確認する</span><span class="sxs-lookup"><span data-stu-id="5a404-144">Enable and then confirm soft delete on your key vaults</span></span>](#enable-and-then-confirm-soft-delete-on-your-key-vaults)

- [<span data-ttu-id="5a404-145">キーを作成またはインポートして、各キー コンテナーにキーを追加する</span><span class="sxs-lookup"><span data-stu-id="5a404-145">Add a key to each key vault either by creating or importing a key</span></span>](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [<span data-ttu-id="5a404-146">キーの回復レベルを確認する</span><span class="sxs-lookup"><span data-stu-id="5a404-146">Check the recovery level of your keys</span></span>](#check-the-recovery-level-of-your-keys)

- [<span data-ttu-id="5a404-147">Azure Key Vault のバックアップ</span><span class="sxs-lookup"><span data-stu-id="5a404-147">Back up Azure Key Vault</span></span>](#back-up-azure-key-vault)

- [<span data-ttu-id="5a404-148">Azure Key Vault 構成設定の検証</span><span class="sxs-lookup"><span data-stu-id="5a404-148">Validate Azure Key Vault configuration settings</span></span>](#validate-azure-key-vault-configuration-settings)

- [<span data-ttu-id="5a404-149">各 Azure Key Vault キーの URI を取得する</span><span class="sxs-lookup"><span data-stu-id="5a404-149">Obtain the URI for each Azure Key Vault key</span></span>](#obtain-the-uri-for-each-azure-key-vault-key)

<span data-ttu-id="5a404-150">**Office 365:**</span><span class="sxs-lookup"><span data-stu-id="5a404-150">**In Office 365:**</span></span>
  
<span data-ttu-id="5a404-151">Exchange Online と Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="5a404-151">Exchange Online and Skype for Business:</span></span>
  
- [<span data-ttu-id="5a404-152">Exchange Online および Skype for Business で使用するデータ暗号化ポリシー (DEP) を作成する</span><span class="sxs-lookup"><span data-stu-id="5a404-152">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>](#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)

- [<span data-ttu-id="5a404-153">メールボックスへの DEP の割り当て</span><span class="sxs-lookup"><span data-stu-id="5a404-153">Assign a DEP to a mailbox</span></span>](#assign-a-dep-to-a-mailbox)

- [<span data-ttu-id="5a404-154">メールボックスの暗号化を検証する</span><span class="sxs-lookup"><span data-stu-id="5a404-154">Validate mailbox encryption</span></span>](#validate-mailbox-encryption)

<span data-ttu-id="5a404-155">SharePoint Online および OneDrive for Business:</span><span class="sxs-lookup"><span data-stu-id="5a404-155">SharePoint Online and OneDrive for Business:</span></span>
  
- [<span data-ttu-id="5a404-156">SharePoint Online および OneDrive for Business geo ごとにデータ暗号化ポリシー (DEP) を作成する</span><span class="sxs-lookup"><span data-stu-id="5a404-156">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>](#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)

- [<span data-ttu-id="5a404-157">SharePoint Online、OneDrive for Business、Teams ファイルのファイル暗号化を検証する</span><span class="sxs-lookup"><span data-stu-id="5a404-157">Validate file encryption for SharePoint Online, OneDrive for Business, and Teams files</span></span>](#validate-file-encryption)

## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a><span data-ttu-id="5a404-158">Azure Key Vault および Microsoft FastTrack for Customer Key のタスクを完了する</span><span class="sxs-lookup"><span data-stu-id="5a404-158">Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key</span></span>

<span data-ttu-id="5a404-159">Azure Key Vault でこれらのタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a404-159">Complete these tasks in Azure Key Vault.</span></span> <span data-ttu-id="5a404-160">Exchange Online および Skype for Business または SharePoint Online、OneDrive for Business、Teams ファイル、または Office 365 でサポートされているすべてのサービスに対してカスタマー キーを設定する場合は、これらの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a404-160">You'll need to complete these steps regardless of whether you intend to set up Customer Key for Exchange Online and Skype for Business or for SharePoint Online, OneDrive for Business, and Teams files, or for all supported services in Office 365.</span></span>
  
### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="5a404-161">2 つの新しい Azure サブスクリプションを作成する</span><span class="sxs-lookup"><span data-stu-id="5a404-161">Create two new Azure subscriptions</span></span>

<span data-ttu-id="5a404-162">顧客キーには、2 つの Azure サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="5a404-162">Customer Key requires two Azure subscriptions.</span></span> <span data-ttu-id="5a404-163">ベスト プラクティスとして、顧客キーで使用する新しい Azure サブスクリプションを作成するようにお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5a404-163">As a best practice, Microsoft recommends that you create new Azure subscriptions for use with Customer Key.</span></span> <span data-ttu-id="5a404-164">Azure Key Vault キーは、同じ Azure Active Directory (Microsoft Azure Active Directory) テナント内のアプリケーションにのみ承認できます。DEP が割り当てられる組織で使用されるのと同じ Azure AD テナントを使用して新しいサブスクリプションを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a404-164">Azure Key Vault keys can only be authorized for applications in the same Azure Active Directory (Microsoft Azure Active Directory) tenant, you must create the new subscriptions using the same Azure AD tenant used with your organization where the DEPs will be assigned.</span></span> <span data-ttu-id="5a404-165">たとえば、組織でグローバル管理者特権を持つ仕事用または学校用のアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="5a404-165">For example, using your work or school account that has global administrator privileges in your organization.</span></span> <span data-ttu-id="5a404-166">詳細な手順については、「組織として [Azure にサインアップする」を参照してください](/azure/active-directory/fundamentals/sign-up-organization)。</span><span class="sxs-lookup"><span data-stu-id="5a404-166">For detailed steps, see [Sign up for Azure as an organization](/azure/active-directory/fundamentals/sign-up-organization).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5a404-167">顧客キーには、データ暗号化ポリシー (DEP) ごとに 2 つのキーが必要です。</span><span class="sxs-lookup"><span data-stu-id="5a404-167">Customer Key requires two keys for each data encryption policy (DEP).</span></span> <span data-ttu-id="5a404-168">これを実現するには、2 つの Azure サブスクリプションを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a404-168">In order to achieve this, you must create two Azure subscriptions.</span></span> <span data-ttu-id="5a404-169">ベスト プラクティスとして、組織の個別のメンバーが各サブスクリプションで 1 つのキーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a404-169">As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription.</span></span> <span data-ttu-id="5a404-170">これらの Azure サブスクリプションは、365 の暗号化キーを管理する場合にのみOffice必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a404-170">You should only use these Azure subscriptions to administer encryption keys for Office 365.</span></span> <span data-ttu-id="5a404-171">これにより、オペレーターの 1 人が誤って、意図的に、または悪意を持って削除したり、責任を負うキーを誤って管理したりした場合に、組織が保護されます。</span><span class="sxs-lookup"><span data-stu-id="5a404-171">This protects your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible.</span></span>
>

<span data-ttu-id="5a404-172">組織に対して作成できる Azure サブスクリプションの数に実際的な制限はありません。</span><span class="sxs-lookup"><span data-stu-id="5a404-172">There is no practical limit to the number of Azure subscriptions that you can create for your organization.</span></span> <span data-ttu-id="5a404-173">これらのベスト プラクティスに従って、カスタマー キーで使用されるリソースを管理しながら、人的エラーの影響を最小限に抑えます。</span><span class="sxs-lookup"><span data-stu-id="5a404-173">Following these best practices will minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span>
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a><span data-ttu-id="5a404-174">顧客キーをアクティブ化する要求を 365 Officeする</span><span class="sxs-lookup"><span data-stu-id="5a404-174">Submit a request to activate Customer Key for Office 365</span></span>

<span data-ttu-id="5a404-175">Azure の手順を完了したら、Microsoft FastTrack ポータルでオファー要求を送信 [する必要があります](https://fasttrack.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="5a404-175">Once you've completed the Azure steps, you'll need to submit an offer request in the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span> <span data-ttu-id="5a404-176">FastTrack Web ポータルから要求を送信すると、Microsoft は、指定した Azure Key Vault 構成データと連絡先情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="5a404-176">Once you've submitted a request through the FastTrack web portal, Microsoft verifies the Azure Key Vault configuration data and contact information you provided.</span></span> <span data-ttu-id="5a404-177">組織の承認された役員に関するオファー フォームで行う選択は重要であり、顧客キー登録の完了に必要です。</span><span class="sxs-lookup"><span data-stu-id="5a404-177">The selections that you make in the offer form about the authorized officers of your organization is critical and necessary for completion of Customer Key registration.</span></span> <span data-ttu-id="5a404-178">組織の役員は、顧客キーデータ暗号化ポリシーで使用されるすべてのキーを取り消して破棄する要求の信頼性を保証します。</span><span class="sxs-lookup"><span data-stu-id="5a404-178">The officers of your organization ensure the authenticity of any request to revoke and destroy all keys used with a Customer Key data encryption policy.</span></span> <span data-ttu-id="5a404-179">この手順を 1 回実行して、Exchange Online および Skype for Business カバレッジのカスタマー キーをアクティブ化し、もう 1 回は SharePoint Online と OneDrive for Business のカスタマー キーをアクティブにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a404-179">You'll need to do this step once to activate Customer Key for Exchange Online and Skype for Business coverage and a second time to activate Customer Key for SharePoint Online and OneDrive for Business.</span></span>
  
<span data-ttu-id="5a404-180">顧客キーをアクティブ化するオファーを送信するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5a404-180">To submit an offer to activate Customer Key, complete these steps:</span></span>
  
1. <span data-ttu-id="5a404-181">組織でグローバル管理者のアクセス許可を持つ仕事または学校のアカウントを使用して [、Microsoft FastTrack ポータルにサインインします](https://fasttrack.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="5a404-181">Using a work or school account that has global administrator permissions in your organization, sign in to the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span>

2. <span data-ttu-id="5a404-182">ログインしたら、ダッシュボードを参照 **します**。</span><span class="sxs-lookup"><span data-stu-id="5a404-182">Once you're logged in, browse to the **Dashboard**.</span></span>

3. <span data-ttu-id="5a404-183">ナビゲーション **バーから [展開**] を選択するか **、[** 展開 **情報カード** のすべての展開リソースを表示する] を選択し、現在のオファーの一覧を確認します。</span><span class="sxs-lookup"><span data-stu-id="5a404-183">Choose **Deploy** from the navigation bar **OR** select **View all deployment resources** on the **Deploy** information card, and review the list of current offers.</span></span>

4. <span data-ttu-id="5a404-184">該当するオファーの情報カードを選択します。</span><span class="sxs-lookup"><span data-stu-id="5a404-184">Choose the information card for the offer that applies to you:</span></span>

   - <span data-ttu-id="5a404-185">**Exchange Online と Skype for Business:** Exchange オンライン **オファーの暗号化キーの要求ヘルプを選択** します。</span><span class="sxs-lookup"><span data-stu-id="5a404-185">**Exchange Online and Skype for Business:** Choose the **Request encryption key help for Exchange online** offer.</span></span>

   - <span data-ttu-id="5a404-186">**SharePoint Online、OneDrive、Teams ファイル:** Sharepoint および **OneDrive オファーの暗号化キーの要求ヘルプを選択** します。</span><span class="sxs-lookup"><span data-stu-id="5a404-186">**SharePoint Online, OneDrive, and Teams files:** Choose the **Request encryption key help for Sharepoint and OneDrive** offer.</span></span>

5. <span data-ttu-id="5a404-187">オファーの詳細を確認したら、[手順 2 に進む] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5a404-187">Once you've reviewed the offer details, choose **Continue to step 2**.</span></span>

6. <span data-ttu-id="5a404-188">オファー フォームに該当する詳細情報と要求された情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="5a404-188">Fill out all applicable details and requested information on the offer form.</span></span> <span data-ttu-id="5a404-189">暗号化キーとデータの永続的で不可逆的な破壊を承認するために承認する組織の役員の選択に特に注意を払います。</span><span class="sxs-lookup"><span data-stu-id="5a404-189">Pay particular attention to your selections for which officers of your organization you want to authorize to approve the permanent and irreversible destruction of encryption keys and data.</span></span> <span data-ttu-id="5a404-190">フォームが完成したら、[送信] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="5a404-190">Once you've completed the form, choose **Submit**.</span></span>

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="5a404-191">必須の保持期間を使用するように Azure サブスクリプションを登録する</span><span class="sxs-lookup"><span data-stu-id="5a404-191">Register Azure subscriptions to use a mandatory retention period</span></span>

<span data-ttu-id="5a404-192">ルート暗号化キーが一時的または永続的に失われると、サービス操作が中断したり、壊滅的な操作を受け入れ、データが失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5a404-192">The temporary or permanent loss of root encryption keys can be disruptive or even catastrophic to service operation and can result in data loss.</span></span> <span data-ttu-id="5a404-193">このため、Customer Key で使用されるリソースには強力な保護が必要です。</span><span class="sxs-lookup"><span data-stu-id="5a404-193">For this reason, the resources used with Customer Key require strong protection.</span></span> <span data-ttu-id="5a404-194">Customer Key で使用される Azure リソースはすべて、既定の構成を超える保護メカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="5a404-194">All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration.</span></span> <span data-ttu-id="5a404-195">必須の保持期間の Azure サブスクリプションにタグを付 *けまたは登録できます*。</span><span class="sxs-lookup"><span data-stu-id="5a404-195">You can tag or register Azure subscriptions for a *mandatory retention period*.</span></span> <span data-ttu-id="5a404-196">必須の保持期間によって、Azure サブスクリプションの即時および取り消し不可の取り消しが防止されます。</span><span class="sxs-lookup"><span data-stu-id="5a404-196">A mandatory retention period prevents immediate and irrevocable cancellation of your Azure subscription.</span></span> <span data-ttu-id="5a404-197">必須の保持期間に Azure サブスクリプションを登録するために必要な手順では、Microsoft 365 チームとの共同作業が必要です。</span><span class="sxs-lookup"><span data-stu-id="5a404-197">The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Microsoft 365 team.</span></span> <span data-ttu-id="5a404-198">このプロセスには、1 ~ 5 営業日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5a404-198">This process can take from one to five business days.</span></span> <span data-ttu-id="5a404-199">以前は、必須の保持期間を "キャンセルしない" と呼ばれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5a404-199">Previously, mandatory retention period was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="5a404-200">Microsoft 365 チームに連絡する前に、カスタマー キーで使用する Azure サブスクリプションごとに次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a404-200">Before contacting the Microsoft 365 team, you must do the following steps for each Azure subscription that you use with Customer Key.</span></span> <span data-ttu-id="5a404-201">開始する前に [、Azure PowerShell Az](/powershell/azure/new-azureps-module-az) モジュールがインストールされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5a404-201">Ensure that you have the [Azure PowerShell Az](/powershell/azure/new-azureps-module-az) module installed before you start.</span></span>
  
1. <span data-ttu-id="5a404-202">Azure PowerShell でサインインします。</span><span class="sxs-lookup"><span data-stu-id="5a404-202">Sign in with Azure PowerShell.</span></span> <span data-ttu-id="5a404-203">手順については [、「Azure PowerShell でサインインする」を参照してください](/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="5a404-203">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="5a404-204">必須の保持Register-AzProviderFeature使用するサブスクリプションを登録するには、Register-AzProviderFeatureコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a404-204">Run the Register-AzProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span> <span data-ttu-id="5a404-205">サブスクリプションごとにこのアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a404-205">Complete this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. <span data-ttu-id="5a404-206">プロセスを完了するには、Microsoft にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="5a404-206">Contact Microsoft to complete the process.</span></span> <span data-ttu-id="5a404-207">SharePoint および OneDrive for Business チームの場合は、次の[spock@microsoft.com。](mailto:spock@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="5a404-207">For the SharePoint and OneDrive for Business team, contact [spock@microsoft.com](mailto:spock@microsoft.com).</span></span> <span data-ttu-id="5a404-208">Exchange Online および Skype for Business の場合は、 [次の](mailto:exock@microsoft.com)exock@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="5a404-208">For Exchange Online and Skype for Business, contact [exock@microsoft.com](mailto:exock@microsoft.com).</span></span> <span data-ttu-id="5a404-209">メールに次の情報を含める。</span><span class="sxs-lookup"><span data-stu-id="5a404-209">Include the following information in your email:</span></span>

   <span data-ttu-id="5a404-210">**件名**: 顧客キー \<*Your tenant's fully qualified domain name*\></span><span class="sxs-lookup"><span data-stu-id="5a404-210">**Subject**: Customer Key for \<*Your tenant's fully qualified domain name*\></span></span>

   <span data-ttu-id="5a404-211">**本文**: 必須の保持期間を完了するサブスクリプションの Get-AzProviderFeatureを含める。</span><span class="sxs-lookup"><span data-stu-id="5a404-211">**Body**: Include the subscription IDs for which you want to complete the mandatory retention period  and the output of Get-AzProviderFeature for each subscription.</span></span>

   <span data-ttu-id="5a404-212">このプロセスを完了するサービス レベル契約 (SLA) は、Microsoft がサブスクリプションを登録して必須の保持期間を使用すると通知 (および確認) された後、5 営業日です。</span><span class="sxs-lookup"><span data-stu-id="5a404-212">The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period.</span></span>

4. <span data-ttu-id="5a404-213">登録が完了したという通知を Microsoft から受け取った後、次のように Get-AzProviderFeature コマンドを実行して、登録の状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="5a404-213">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzProviderFeature command as follows.</span></span> <span data-ttu-id="5a404-214">確認された場合、Get-AzProviderFeatureコマンドは、Registration State プロパティの **[登録済** み] **の値を返** します。</span><span class="sxs-lookup"><span data-stu-id="5a404-214">If verified, the Get-AzProviderFeature command returns a value of **Registered** for the **Registration State** property.</span></span> <span data-ttu-id="5a404-215">サブスクリプションごとにこの手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="5a404-215">Complete this step for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. <span data-ttu-id="5a404-216">プロセスを完了するには、次のコマンドRegister-AzResourceProviderします。</span><span class="sxs-lookup"><span data-stu-id="5a404-216">To complete the process, run the Register-AzResourceProvider command.</span></span> <span data-ttu-id="5a404-217">サブスクリプションごとにこの手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="5a404-217">Complete this step for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="5a404-218">各サブスクリプションにプレミアム Azure Key Vault を作成する</span><span class="sxs-lookup"><span data-stu-id="5a404-218">Create a premium Azure Key Vault in each subscription</span></span>

<span data-ttu-id="5a404-219">キー コンテナーを作成する手順については、「Azure Key Vault の使用を開始する」に記載されています。このガイドでは [、Azure](/azure/key-vault/general/overview)PowerShell のインストールと起動、Azure サブスクリプションへの接続、リソース グループの作成、そのリソース グループ内のキー コンテナーの作成について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a404-219">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](/azure/key-vault/general/overview), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="5a404-220">キー コンテナーを作成する場合は、SKU (Standard または Premium) を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a404-220">When you create a key vault, you must choose a SKU: either Standard or Premium.</span></span> <span data-ttu-id="5a404-221">Standard SKU を使用すると、Azure Key Vault キーをソフトウェアで保護できます 。ハードウェア セキュリティ モジュール (HSM) キー保護はありません。また、Premium SKU では、キー コンテナー キーの保護のために HSM を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5a404-221">The Standard SKU allows Azure Key Vault keys to be protected with software - there's no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys.</span></span> <span data-ttu-id="5a404-222">カスタマー キーは、いずれかの SKU を使用するキー コンテナーを受け入れ、プレミアム SKU のみを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a404-222">Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU.</span></span> <span data-ttu-id="5a404-223">どちらの種類のキーを使用する操作のコストも同じなので、コストの唯一の違いは、各 HSM で保護されたキーの 1 か月あたりのコストです。</span><span class="sxs-lookup"><span data-stu-id="5a404-223">The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key.</span></span> <span data-ttu-id="5a404-224">詳細については [、「Key Vault の価格」](https://azure.microsoft.com/pricing/details/key-vault/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a404-224">See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5a404-225">実稼働データには Premium SKU キー コンテナーと HSM で保護されたキーを使用し、テストおよび検証の目的で標準 SKU キー コンテナーとキーのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="5a404-225">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span>
  
<span data-ttu-id="5a404-226">顧客キーを使用する Microsoft 365 サービスごとに、作成した 2 つの Azure サブスクリプションのそれぞれにキー コンテナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="5a404-226">For each Microsoft 365 service with which you will use Customer Key, create a key vault in each of the two Azure subscriptions that you created.</span></span> <span data-ttu-id="5a404-227">たとえば、Exchange Online と Skype for Business のみ、または SharePoint Online と OneDrive for Business の場合は、1 組のコンテナーのみを作成します。</span><span class="sxs-lookup"><span data-stu-id="5a404-227">For example, for Exchange Online and Skype for Business only or SharePoint Online and OneDrive for Business only, you'll create only one pair of vaults.</span></span> <span data-ttu-id="5a404-228">Exchange Online と SharePoint Online の両方で顧客キーを有効にするには、2 組のキー コンテナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="5a404-228">To enable Customer Key for both Exchange Online and SharePoint Online, you will create two pairs of key vaults.</span></span>
  
<span data-ttu-id="5a404-229">コンテナーを関連付ける DEP の使用目的を反映するキー コンテナーの名前付け規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="5a404-229">Use a naming convention for key vaults that reflects the intended use of the DEP with which you will associate the vaults.</span></span> <span data-ttu-id="5a404-230">名前付け規則の推奨事項については、以下の「ベスト プラクティス」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a404-230">See the Best Practices section below for naming convention recommendations.</span></span>
  
<span data-ttu-id="5a404-231">データ暗号化ポリシーごとに、ペアにされた個別のコンテナー セットを作成します。</span><span class="sxs-lookup"><span data-stu-id="5a404-231">Create a separate, paired set of vaults for each data encryption policy.</span></span> <span data-ttu-id="5a404-232">Exchange Online では、ポリシーをメールボックスに割り当てるときに、データ暗号化ポリシーのスコープが選択されます。</span><span class="sxs-lookup"><span data-stu-id="5a404-232">For Exchange Online, the scope of a data encryption policy is chosen by you when you assign the policy to mailbox.</span></span> <span data-ttu-id="5a404-233">メールボックスには 1 つのポリシーのみを割り当て、最大 50 のポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5a404-233">A mailbox can have only one policy assigned, and you can create up to 50 policies.</span></span> <span data-ttu-id="5a404-234">SharePoint Online ポリシーの範囲には、地理的な場所または地理的な場所にある組織内のすべてのデータが含 _まれます_。</span><span class="sxs-lookup"><span data-stu-id="5a404-234">The scope of a SharePoint Online policy includes all of the data within an organization in a geographic location, or _geo_.</span></span>

<span data-ttu-id="5a404-235">キー コンテナーの作成には Azure リソース グループの作成も必要です。キー コンテナーにはストレージ容量 (小さいですが) が必要で、有効にした場合は Key Vault ログも保存されたデータが生成されます。</span><span class="sxs-lookup"><span data-stu-id="5a404-235">The creation of key vaults also requires the creation of Azure resource groups, since key vaults need storage capacity (though small) and Key Vault logging, if enabled, also generates stored data.</span></span> <span data-ttu-id="5a404-236">ベスト プラクティスとして、Microsoft は個別の管理者を使用して各リソース グループを管理し、関連する顧客キー リソースを管理する一連の管理者に対応した管理を推奨します。</span><span class="sxs-lookup"><span data-stu-id="5a404-236">As a best practice Microsoft recommends using separate administrators to manage each resource group, with the administration that's aligned with the set of administrators that will manage all related Customer Key resources.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5a404-237">可用性を最大化するには、キー コンテナーが Microsoft 365 サービスに近い地域にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a404-237">To maximize availability, your key vaults should be in regions close to your Microsoft 365 service.</span></span> <span data-ttu-id="5a404-238">たとえば、Exchange Online 組織が北米にある場合は、キー コンテナーを北米に配置します。</span><span class="sxs-lookup"><span data-stu-id="5a404-238">For example, if your Exchange Online organization is in North America, place your key vaults in North America.</span></span> <span data-ttu-id="5a404-239">Exchange Online 組織がヨーロッパにある場合は、キー コンテナーをヨーロッパに配置します。</span><span class="sxs-lookup"><span data-stu-id="5a404-239">If your Exchange Online organization is in Europe, place your key vaults in Europe.</span></span>
> 
> <span data-ttu-id="5a404-240">キー コンテナーに共通のプレフィックスを使用し、キー コンテナーとキーの使用と範囲の省略形を含める (たとえば、コンテナーが北アメリカにある Contoso SharePoint サービスの場合、名前の可能なペアは Contoso-O365SP-NA-VaultA1 と Contoso-O365SP-NA-VaultA2 です。</span><span class="sxs-lookup"><span data-stu-id="5a404-240">Use a common prefix for key vaults, and include an abbreviation of the use and scope of the key vault and keys (e.g., for the Contoso SharePoint service where the vaults will be located in North America, a possible pair of names is Contoso-O365SP-NA-VaultA1 and Contoso-O365SP-NA-VaultA2.</span></span> <span data-ttu-id="5a404-241">コンテナー名は Azure 内でグローバルに一意の文字列なので、目的の名前が既に他の Azure ユーザーによって要求されている場合に、目的の名前のバリエーションを試す必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="5a404-241">Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers.</span></span> <span data-ttu-id="5a404-242">2017 年 7 月現在、コンテナー名は変更できません。ベスト プラクティスは、セットアップの計画を作成し、2 人目を使用して計画が正しく実行されていることを確認する方法です。</span><span class="sxs-lookup"><span data-stu-id="5a404-242">As of July 2017 vault names cannot be changed, so a best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span>
> 
> <span data-ttu-id="5a404-243">可能であれば、ペア以外の領域にコンテナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="5a404-243">If possible, create your vaults in non-paired regions.</span></span> <span data-ttu-id="5a404-244">ペアリングされた Azure リージョンは、サービス障害ドメイン全体で高可用性を提供します。</span><span class="sxs-lookup"><span data-stu-id="5a404-244">Paired Azure regions provide high availability across service failure domains.</span></span> <span data-ttu-id="5a404-245">したがって、地域のペアは、互いにバックアップ領域と見なされます。</span><span class="sxs-lookup"><span data-stu-id="5a404-245">Therefore, regional pairs can be thought of as each other's backup region.</span></span> <span data-ttu-id="5a404-246">つまり、1 つの地域に配置された Azure リソースは、ペアリングされた地域を通じて自動的にフォールト トレランスを取得します。</span><span class="sxs-lookup"><span data-stu-id="5a404-246">This means that an Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region.</span></span> <span data-ttu-id="5a404-247">このため、データ暗号化ポリシーで使用される 2 つのコンテナーに対してリージョンを選択すると、領域がペアになります。つまり、可用性の合計 2 つの領域だけが使用されます。</span><span class="sxs-lookup"><span data-stu-id="5a404-247">For this reason, choosing regions for two vaults used in a data encryption policy where the regions are paired means that only a total of two regions of availability are in use.</span></span> <span data-ttu-id="5a404-248">ほとんどの地域には 2 つの地域しか存在しないので、ペアリングされていない地域をまだ選択できません。</span><span class="sxs-lookup"><span data-stu-id="5a404-248">Most geographies only have two regions, so it's not yet possible to select non-paired regions.</span></span> <span data-ttu-id="5a404-249">可能であれば、データ暗号化ポリシーで使用する 2 つのコンテナーに対して、ペアリングされていない 2 つの領域を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a404-249">If possible, choose two non-paired regions for the two vaults used with a data encryption policy.</span></span> <span data-ttu-id="5a404-250">これは、可用性の合計 4 つの地域の恩恵を受ける。</span><span class="sxs-lookup"><span data-stu-id="5a404-250">This benefits from a total of four regions of availability.</span></span> <span data-ttu-id="5a404-251">詳細については [、「Business continuity and disaster recovery (BCDR): Azure Paired Regions](/azure/best-practices-availability-paired-regions) for current list of region pairs」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a404-251">For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span>
  
### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="5a404-252">各キー コンテナーにアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="5a404-252">Assign permissions to each key vault</span></span>

<span data-ttu-id="5a404-253">実装に応じて、キー コンテナーごとに 3 つのアクセス許可セットを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a404-253">You'll need to define three separate sets of permissions for each key vault, depending on your implementation.</span></span> <span data-ttu-id="5a404-254">たとえば、次のそれぞれに 1 つのアクセス許可セットを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a404-254">For example, you will need to define one set of permissions for each of the following:</span></span>
  
- <span data-ttu-id="5a404-255">**組織のキー** コンテナーの毎日の管理を行うキー コンテナー管理者。</span><span class="sxs-lookup"><span data-stu-id="5a404-255">**Key vault administrators** that do day-to-day management of your key vault for your organization.</span></span> <span data-ttu-id="5a404-256">これらのタスクには、バックアップ、作成、取得、インポート、リスト、復元が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5a404-256">These tasks include backup, create, get, import, list, and restore.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="5a404-257">キー コンテナー管理者に割り当てられた一連のアクセス許可には、キーを削除するアクセス許可は含められていない。</span><span class="sxs-lookup"><span data-stu-id="5a404-257">The set of permissions assigned to key vault administrators does not include the permission to delete keys.</span></span> <span data-ttu-id="5a404-258">これは意図的で重要なプラクティスです。</span><span class="sxs-lookup"><span data-stu-id="5a404-258">This is intentional and an important practice.</span></span> <span data-ttu-id="5a404-259">暗号化キーを削除すると、データが完全に破棄されるので、通常は実行しません。</span><span class="sxs-lookup"><span data-stu-id="5a404-259">Deleting encryption keys is not typically done, since doing so permanently destroys data.</span></span> <span data-ttu-id="5a404-260">ベスト プラクティスとして、このアクセス許可をキー コンテナー管理者に既定で付与しない。</span><span class="sxs-lookup"><span data-stu-id="5a404-260">As a best practice, do not grant this permission to key vault administrators by default.</span></span> <span data-ttu-id="5a404-261">代わりに、これを重要なコンテナーの投稿者に予約し、結果の明確な理解が得られると、短期間で管理者に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a404-261">Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span>
  
  <span data-ttu-id="5a404-262">これらのアクセス許可を組織内のユーザーに割り当てるには、Azure PowerShell を使用して Azure サブスクリプションにサインインします。</span><span class="sxs-lookup"><span data-stu-id="5a404-262">To assign these permissions to a user in your organization, sign in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="5a404-263">手順については [、「Azure PowerShell でサインインする」を参照してください](/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="5a404-263">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

- <span data-ttu-id="5a404-264">必要なアクセスSet-AzKeyVaultAccessPolicy割り当てるには、このコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a404-264">Run the Set-AzKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   <span data-ttu-id="5a404-265">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="5a404-265">For example:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- <span data-ttu-id="5a404-266">Azure **Key Vault 自体の** アクセス許可を変更できるキー コンテナーの投稿者。</span><span class="sxs-lookup"><span data-stu-id="5a404-266">**Key vault contributors** that can change permissions on the Azure Key Vault itself.</span></span> <span data-ttu-id="5a404-267">従業員がチームを離れるか、チームに参加する場合は、これらのアクセス許可を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a404-267">You'll need to change these permissions as employees leave or join your team.</span></span> <span data-ttu-id="5a404-268">キー コンテナー管理者がキーを削除または復元するためのアクセス許可を正当に必要とするまれな状況では、アクセス許可を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a404-268">In the rare situation that the key vault administrators legitimately need permission to delete or restore a key you'll also need to change the permissions.</span></span> <span data-ttu-id="5a404-269">この一連のキー コンテナー投稿者には、キー コンテナーの **共同作成者** ロールを付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a404-269">This set of key vault contributors needs to be granted the **Contributor** role on your key vault.</span></span> <span data-ttu-id="5a404-270">このロールは、Azure リソース マネージャーを使用して割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="5a404-270">You can assign this role by using Azure Resource Manager.</span></span> <span data-ttu-id="5a404-271">詳細な手順については、「Use Role-Based Access Control を使用して Azure サブスクリプション リソースへの [アクセスを管理する」を参照してください](/azure/active-directory/role-based-access-control-configure)。</span><span class="sxs-lookup"><span data-stu-id="5a404-271">For detailed steps, see [Use Role-Based Access Control to manage access to your Azure subscription resources](/azure/active-directory/role-based-access-control-configure).</span></span> <span data-ttu-id="5a404-272">サブスクリプションを作成する管理者は、暗黙的にこのアクセス権を持ち、他の管理者を共同作成者ロールに割り当てる機能を持っています。</span><span class="sxs-lookup"><span data-stu-id="5a404-272">The administrator who creates a subscription has this access implicitly, and the ability to assign other administrators to the Contributor role.</span></span>

- <span data-ttu-id="5a404-273">Exchange Online と Skype for Business で顧客キーを使用する場合は、Exchange Online および Skype for Business に代わってキー コンテナーを使用するアクセス許可を Microsoft 365 に付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a404-273">If you intend to use Customer Key with Exchange Online and Skype for Business, you need to give permission to Microsoft 365 to use the key vault on behalf of Exchange Online and Skype for Business.</span></span> <span data-ttu-id="5a404-274">同様に、SharePoint Online および OneDrive for Business で顧客キーを使用する場合は、SharePoint Online および OneDrive for Business に代わってキー コンテナーを使用するアクセス許可を Microsoft 365 に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a404-274">Likewise, if you intend to use Customer Key with SharePoint Online and OneDrive for Business, you need to add permission for the Microsoft 365 to use the key vault on behalf of SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="5a404-275">Microsoft 365 にアクセス許可を付与するには、次の構文を使用して **Set-AzKeyVaultAccessPolicy** コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a404-275">To give permission to Microsoft 365, run the **Set-AzKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   <span data-ttu-id="5a404-276">ここで、</span><span class="sxs-lookup"><span data-stu-id="5a404-276">Where:</span></span>

    - <span data-ttu-id="5a404-277">*コンテナー名* は、作成したキー コンテナーの名前です。</span><span class="sxs-lookup"><span data-stu-id="5a404-277">*vault name* is the name of the key vault you created.</span></span>

    - <span data-ttu-id="5a404-278">Exchange Online および Skype for Business の場合は、Office  *365 appID* を `00000002-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="5a404-278">For Exchange Online and Skype for Business, replace  *Office 365 appID* with `00000002-0000-0ff1-ce00-000000000000`</span></span>

    - <span data-ttu-id="5a404-279">SharePoint Online、OneDrive for Business、Teams ファイルの場合は  *、365 appID Officeに置き換* える `00000003-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="5a404-279">For SharePoint Online, OneDrive for Business, and Teams files, replace  *Office 365 appID* with `00000003-0000-0ff1-ce00-000000000000`</span></span>

  <span data-ttu-id="5a404-280">例: Exchange Online と Skype for Business のアクセス許可の設定:</span><span class="sxs-lookup"><span data-stu-id="5a404-280">Example: Setting permissions for Exchange Online and Skype for Business:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  <span data-ttu-id="5a404-281">例: SharePoint Online、OneDrive for Business、Teams ファイルのアクセス許可を設定します。</span><span class="sxs-lookup"><span data-stu-id="5a404-281">Example: Setting permissions for SharePoint Online, OneDrive for Business, and Teams files:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a><span data-ttu-id="5a404-282">キー コンテナーでソフト削除を有効にして確認する</span><span class="sxs-lookup"><span data-stu-id="5a404-282">Enable and then confirm soft delete on your key vaults</span></span>

<span data-ttu-id="5a404-283">キーをすばやく回復できると、誤ってまたは悪意を持って削除されたキーが原因で、サービスの停止が長く発生する可能性が低い。</span><span class="sxs-lookup"><span data-stu-id="5a404-283">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys.</span></span> <span data-ttu-id="5a404-284">顧客キーでキーを使用するには、この構成 (Soft Delete と呼ばれる) を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a404-284">You need to enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key.</span></span> <span data-ttu-id="5a404-285">Soft Delete を有効にすると、削除から 90 日以内にキーまたはコンテナーをバックアップから復元せずに復元できます。</span><span class="sxs-lookup"><span data-stu-id="5a404-285">Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="5a404-286">キー コンテナーで Soft Delete を有効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5a404-286">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="5a404-287">Azure サブスクリプションにサインインし、Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="5a404-287">Sign in to your Azure subscription with Windows PowerShell.</span></span> <span data-ttu-id="5a404-288">手順については [、「Azure PowerShell でサインインする」を参照してください](/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="5a404-288">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="5a404-289">[Get-AzKeyVault コマンドレットを実行](/powershell/module/az.keyvault/get-azkeyvault)します。</span><span class="sxs-lookup"><span data-stu-id="5a404-289">Run the [Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet.</span></span> <span data-ttu-id="5a404-290">この例では、 *コンテナー名* は、ソフト削除を有効にするキー コンテナーの名前です。</span><span class="sxs-lookup"><span data-stu-id="5a404-290">In this example, *vault name* is the name of the key vault for which you are enabling soft delete:</span></span>

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. <span data-ttu-id="5a404-291">**Get-AzKeyVault** コマンドレットを実行して、キー コンテナーに対してソフト削除が構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5a404-291">Confirm soft delete is configured for the key vault by running the **Get-AzKeyVault** cmdlet.</span></span> <span data-ttu-id="5a404-292">キー コンテナーに対してソフト削除が適切に構成されている場合 _、Soft Delete Enabled_ プロパティは True の値を返 **します**。</span><span class="sxs-lookup"><span data-stu-id="5a404-292">If soft delete is configured properly for the key vault, then the _Soft Delete Enabled_ property returns a value of **True**:</span></span>

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="5a404-293">キーを作成またはインポートして、各キー コンテナーにキーを追加する</span><span class="sxs-lookup"><span data-stu-id="5a404-293">Add a key to each key vault either by creating or importing a key</span></span>

<span data-ttu-id="5a404-294">Azure Key Vault にキーを追加するには、2 つの方法があります。Key Vault で直接キーを作成するか、キーをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="5a404-294">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key.</span></span> <span data-ttu-id="5a404-295">Key Vault で直接キーを作成する方法は複雑ではありません。一方で、キーをインポートすると、キーの生成方法を完全に制御できます。</span><span class="sxs-lookup"><span data-stu-id="5a404-295">Creating a key directly in Key Vault is the less complicated method, while importing a key provides total control over how the key is generated.</span></span> <span data-ttu-id="5a404-296">RSA キーを使用します。</span><span class="sxs-lookup"><span data-stu-id="5a404-296">Use the RSA keys.</span></span> <span data-ttu-id="5a404-297">Azure Key Vault では、楕円曲線キーを使用した折り返しとラップ解除はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5a404-297">Azure Key Vault doesn't support wrapping and unwrapping with elliptical curve keys.</span></span>
  
<span data-ttu-id="5a404-298">キー コンテナーにキーを直接作成するには、次のように [Add-AzKeyVaultKey コマンドレット](/powershell/module/az.keyvault/add-azkeyvaultkey) を実行します。</span><span class="sxs-lookup"><span data-stu-id="5a404-298">To create a key directly in your key vault, run the [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="5a404-299">ここで、</span><span class="sxs-lookup"><span data-stu-id="5a404-299">Where:</span></span>

- <span data-ttu-id="5a404-300">*コンテナー名* は、キーを作成するキー コンテナーの名前です。</span><span class="sxs-lookup"><span data-stu-id="5a404-300">*vault name* is the name of the key vault in which you want to create the key.</span></span>

- <span data-ttu-id="5a404-301">*キー名* は、新しいキーを指定する名前です。</span><span class="sxs-lookup"><span data-stu-id="5a404-301">*key name* is the name you want to give the new key.</span></span>

  > [!TIP]
  > <span data-ttu-id="5a404-302">キー コンテナーの上記と同様の名前付け規則を使用してキーに名前を付ける。</span><span class="sxs-lookup"><span data-stu-id="5a404-302">Name keys using a similar naming convention as described above for key vaults.</span></span> <span data-ttu-id="5a404-303">この方法では、キー名のみを表示するツールでは、文字列は自己記述型です。</span><span class="sxs-lookup"><span data-stu-id="5a404-303">This way, in tools that show only the key name, the string is self-describing.</span></span>
  
<span data-ttu-id="5a404-304">キーを HSM で保護する場合は、必ず **、Destination** パラメーターの値としてHSM を指定し、それ以外の場合は[ソフトウェア] を指定 **します**。</span><span class="sxs-lookup"><span data-stu-id="5a404-304">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the _Destination_ parameter, otherwise, specify **Software**.</span></span>

<span data-ttu-id="5a404-305">例えば、</span><span class="sxs-lookup"><span data-stu-id="5a404-305">For example,</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="5a404-306">キーをキー コンテナーに直接インポートするには、nCipher nShield ハードウェア セキュリティ モジュールが必要です。</span><span class="sxs-lookup"><span data-stu-id="5a404-306">To import a key directly into your key vault, you need to have a nCipher nShield Hardware Security Module.</span></span>
  
<span data-ttu-id="5a404-307">一部の組織では、キーの証明を確立するためにこのアプローチを好み、次の構成証明も提供します。</span><span class="sxs-lookup"><span data-stu-id="5a404-307">Some organizations prefer this approach to establish the provenance of their keys, and then this method also provides the following attestations:</span></span>
  
- <span data-ttu-id="5a404-308">インポートに使用されるツールセットには、生成するキーの暗号化に使用されるキー Exchange キー (KEK) がエクスポート可能ではなく、nCipher によって製造された正規の HSM 内で生成される nCipher からの構成証明が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5a404-308">The toolset used for import includes attestation from nCipher that the Key Exchange Key (KEK) that is used to encrypt the key you generate is not exportable and is generated inside a genuine HSM that was manufactured by nCipher.</span></span>

- <span data-ttu-id="5a404-309">ツールセットには、nCipher によって製造された正規の HSM で Azure Key Vault セキュリティの世界も生成されたという nCipher からの構成証明が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5a404-309">The toolset includes attestation from nCipher that the Azure Key Vault security world was also generated on a genuine HSM manufactured by nCipher.</span></span> <span data-ttu-id="5a404-310">この構成証明は、Microsoft が本物の nCipher ハードウェアも使用しているという証明です。</span><span class="sxs-lookup"><span data-stu-id="5a404-310">This attestation proves to you that Microsoft is also using genuine nCipher hardware.</span></span>

<span data-ttu-id="5a404-311">セキュリティ グループに確認して、上記の構成証明が必要かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="5a404-311">Check with your security group to determine if the above attestations are required.</span></span> <span data-ttu-id="5a404-312">オンプレミスでキーを作成し、キー コンテナーにインポートする詳細な手順については [、「Azure Key Vault](/azure/key-vault/keys/hsm-protected-keys)の HSM で保護されたキーを生成および転送する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a404-312">For detailed steps to create a key on-premises and import it into your key vault, see [How to generate and transfer HSM-protected keys for Azure Key Vault](/azure/key-vault/keys/hsm-protected-keys).</span></span> <span data-ttu-id="5a404-313">Azure の手順を使用して、各キー コンテナーにキーを作成します。</span><span class="sxs-lookup"><span data-stu-id="5a404-313">Use the Azure instructions to create a key in each key vault.</span></span>
  
### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="5a404-314">キーの回復レベルを確認する</span><span class="sxs-lookup"><span data-stu-id="5a404-314">Check the recovery level of your keys</span></span>

<span data-ttu-id="5a404-315">Microsoft 365 では、Azure Key Vault サブスクリプションが [キャンセルしない] に設定され、顧客キーで使用されるキーの削除が有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a404-315">Microsoft 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled.</span></span> <span data-ttu-id="5a404-316">サブスクリプションの設定を確認するには、キーの回復レベルを確認します。</span><span class="sxs-lookup"><span data-stu-id="5a404-316">You can confirm you subscriptions settings by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="5a404-317">キーの回復レベルを確認するには、Azure PowerShell で、次のように Get-AzKeyVaultKeyコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a404-317">To check the recovery level of a key, in Azure PowerShell, run the Get-AzKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

<span data-ttu-id="5a404-318">Recovery _Level_ プロパティが **Recoverable+ProtectedSubscription** の値以外の値を返す場合は、サブスクリプションを [キャンセルしない] リストに入れ、各キー コンテナーでソフト削除が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5a404-318">If the _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, ensure that you have put the subscription on the Do Not Cancel list and that you have soft delete enabled on each of your key vaults.</span></span>
  
### <a name="back-up-azure-key-vault"></a><span data-ttu-id="5a404-319">Azure Key Vault のバックアップ</span><span class="sxs-lookup"><span data-stu-id="5a404-319">Back up Azure Key Vault</span></span>

<span data-ttu-id="5a404-320">作成直後またはキーに対する変更の直後に、バックアップを実行し、バックアップのコピーをオンラインとオフラインの両方で保存します。</span><span class="sxs-lookup"><span data-stu-id="5a404-320">Immediately following creation or any change to a key, perform a backup and store copies of the backup, both online and offline.</span></span> <span data-ttu-id="5a404-321">オフライン コピーは、物理的な安全な保管場所や商用ストレージ施設など、ネットワークに接続できません。</span><span class="sxs-lookup"><span data-stu-id="5a404-321">Offline copies should not be connected to any network, such as in a physical safe or commercial storage facility.</span></span> <span data-ttu-id="5a404-322">障害が発生した場合にアクセスできる場所に、バックアップの少なくとも 1 つのコピーを保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a404-322">At least one copy of the backup should be stored in a location that will be accessible in the event of a disaster.</span></span> <span data-ttu-id="5a404-323">バックアップ BLOB は、Key Vault キーを完全に破棄するか、操作不能にレンダリングする場合にキー マテリアルを復元する唯一の手段です。</span><span class="sxs-lookup"><span data-stu-id="5a404-323">The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable.</span></span> <span data-ttu-id="5a404-324">Azure Key Vault の外部であり、Azure Key Vault にインポートされたキーは、顧客キーがキーを使用するために必要なメタデータが外部キーと一緒に存在しないので、バックアップとして修飾されません。</span><span class="sxs-lookup"><span data-stu-id="5a404-324">Keys that are external to Azure Key Vault and were imported to Azure Key Vault do not qualify as a backup because the metadata necessary for Customer Key to use the key does not exist with the external key.</span></span> <span data-ttu-id="5a404-325">顧客キーを使用した復元操作には、Azure Key Vault から取得したバックアップのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5a404-325">Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key.</span></span> <span data-ttu-id="5a404-326">したがって、キーのアップロードまたは作成後に Azure Key Vault のバックアップを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a404-326">Therefore, you must create a backup of Azure Key Vault after you upload or create a key.</span></span>
  
<span data-ttu-id="5a404-327">Azure Key Vault キーのバックアップを作成するには [、Backup-AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) コマンドレットを次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="5a404-327">To create a backup of an Azure Key Vault key, run the [Backup-AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet as follows:</span></span>

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

<span data-ttu-id="5a404-328">出力ファイルで接尾辞を使用してください `.backup` 。</span><span class="sxs-lookup"><span data-stu-id="5a404-328">Ensure that your output file uses the suffix `.backup`.</span></span>
  
<span data-ttu-id="5a404-329">このコマンドレットから生成された出力ファイルは暗号化され、Azure Key Vault の外部では使用できません。</span><span class="sxs-lookup"><span data-stu-id="5a404-329">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault.</span></span> <span data-ttu-id="5a404-330">バックアップは、バックアップの取得元の Azure サブスクリプションにのみ復元できます。</span><span class="sxs-lookup"><span data-stu-id="5a404-330">The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
> [!TIP]
> <span data-ttu-id="5a404-331">出力ファイルの場合は、コンテナー名とキー名の組み合わせを選択します。</span><span class="sxs-lookup"><span data-stu-id="5a404-331">For the output file, choose a combination of your vault name and key name.</span></span> <span data-ttu-id="5a404-332">これにより、ファイル名が自己記述的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="5a404-332">This will make the file name self-describing.</span></span> <span data-ttu-id="5a404-333">また、バックアップ ファイル名が衝突しないことです。</span><span class="sxs-lookup"><span data-stu-id="5a404-333">It will also ensure that backup file names do not collide.</span></span>
  
<span data-ttu-id="5a404-334">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="5a404-334">For example:</span></span>
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="5a404-335">Azure Key Vault 構成設定の検証</span><span class="sxs-lookup"><span data-stu-id="5a404-335">Validate Azure Key Vault configuration settings</span></span>

<span data-ttu-id="5a404-336">DEP でキーを使用する前の検証はオプションですが、強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5a404-336">Validating before using keys in a DEP is optional, but highly recommended.</span></span> <span data-ttu-id="5a404-337">この記事で説明する以外のキーとコンテナーをセットアップする手順を使用する場合は、カスタマー キーを構成する前に、Azure Key Vault リソースの正常性を検証してください。</span><span class="sxs-lookup"><span data-stu-id="5a404-337">If you use steps to set up your keys and vaults other than the ones described in this article, validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="5a404-338">キーに 、および操作 `get` が有効 `wrapKey` になっている `unwrapKey` か確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5a404-338">To verify that your keys have `get`, `wrapKey`, and `unwrapKey` operations enabled:</span></span>
  
<span data-ttu-id="5a404-339">[Get-AzKeyVault コマンドレットを次](/powershell/module/az.keyvault/get-azkeyvault)のように実行します。</span><span class="sxs-lookup"><span data-stu-id="5a404-339">Run the [Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="5a404-340">出力で、アクセス ポリシーと Exchange Online ID (GUID) または SharePoint Online ID (GUID) を必要に応じて探します。</span><span class="sxs-lookup"><span data-stu-id="5a404-340">In the output, look for the Access Policy and for the Exchange Online identity (GUID) or the SharePoint Online identity (GUID) as appropriate.</span></span> <span data-ttu-id="5a404-341">上記の 3 つのアクセス許可はすべて[キーへのアクセス許可] の下に表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a404-341">All three of the above permissions must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="5a404-342">アクセス ポリシーの構成が正しくない場合は、次のように Set-AzKeyVaultAccessPolicyコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a404-342">If the access policy configuration is incorrect, run the Set-AzKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

<span data-ttu-id="5a404-343">たとえば、Exchange Online と Skype for Business の場合:</span><span class="sxs-lookup"><span data-stu-id="5a404-343">For example, for Exchange Online and Skype for Business:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="5a404-344">たとえば、SharePoint Online および OneDrive for Business の場合、</span><span class="sxs-lookup"><span data-stu-id="5a404-344">For example, for SharePoint Online and OneDrive for Business:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="5a404-345">キーに有効期限が設定されていないことを確認するには [、Get-AzKeyVaultKey](/powershell/module/az.keyvault/get-azkeyvault) コマンドレットを次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="5a404-345">To verify that an expiration date isn't set for your keys, run the [Get-AzKeyVaultKey](/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

<span data-ttu-id="5a404-346">顧客キーは有効期限が切れたキーを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="5a404-346">Customer Key can't use an expired key.</span></span> <span data-ttu-id="5a404-347">有効期限が切れたキーで試行された操作は失敗し、サービスが停止する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5a404-347">Operations attempted with an expired key will fail, and possibly result in a service outage.</span></span> <span data-ttu-id="5a404-348">顧客キーで使用するキーには有効期限が設定されていないことを強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="5a404-348">We strongly recommend that keys used with Customer Key do not have an expiration date.</span></span> <span data-ttu-id="5a404-349">有効期限を設定すると、削除できませんが、別の日付に変更できます。</span><span class="sxs-lookup"><span data-stu-id="5a404-349">An expiration date, once set, cannot be removed, but can be changed to a different date.</span></span> <span data-ttu-id="5a404-350">有効期限が設定されているキーを使用する必要がある場合は、有効期限の値を 12/31/9999 に変更します。</span><span class="sxs-lookup"><span data-stu-id="5a404-350">If a key must be used that has an expiration date set, change the expiration value to 12/31/9999.</span></span> <span data-ttu-id="5a404-351">有効期限が 12/31/9999 以外の日付に設定されているキーは、Microsoft 365 検証に合格しません。</span><span class="sxs-lookup"><span data-stu-id="5a404-351">Keys with an expiration date set to a date other than 12/31/9999 will not pass Microsoft 365 validation.</span></span>
  
<span data-ttu-id="5a404-352">12/31/9999 以外の値に設定されている有効期限を変更するには、次のように [Update-AzKeyVaultKey](/powershell/module/az.keyvault/update-azkeyvaultkey) コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a404-352">To change an expiration date that has been set to any value other than 12/31/9999, run the [Update-AzKeyVaultKey](/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> <span data-ttu-id="5a404-353">顧客キーで使用する暗号化キーに有効期限を設定しません。</span><span class="sxs-lookup"><span data-stu-id="5a404-353">Don't set expiration dates on encryption keys you use with Customer Key.</span></span>
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="5a404-354">各 Azure Key Vault キーの URI を取得する</span><span class="sxs-lookup"><span data-stu-id="5a404-354">Obtain the URI for each Azure Key Vault key</span></span>

<span data-ttu-id="5a404-355">キー コンテナーをセットアップしてキーを追加したら、次のコマンドを実行して、各キー コンテナーのキーの URI を取得します。</span><span class="sxs-lookup"><span data-stu-id="5a404-355">Once you've set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault.</span></span> <span data-ttu-id="5a404-356">後で各 DEP を作成して割り当てる場合は、これらの URI を使用する必要があります。そのため、この情報を安全な場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="5a404-356">You'll need to use these URIs when you create and assign each DEP later, so save this information in a safe place.</span></span> <span data-ttu-id="5a404-357">キー コンテナーごとにこのコマンドを 1 回実行します。</span><span class="sxs-lookup"><span data-stu-id="5a404-357">Run this command once for each key vault.</span></span>
  
<span data-ttu-id="5a404-358">Azure PowerShell では、次の情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="5a404-358">In Azure PowerShell:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="5a404-359">Office 365: Exchange Online と Skype for Business のカスタマー キーの設定</span><span class="sxs-lookup"><span data-stu-id="5a404-359">Office 365: Setting up Customer Key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="5a404-360">開始する前に、Azure Key Vault のセットアップに必要なタスクが完了している必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a404-360">Before you begin, ensure that you've completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="5a404-361">詳細 [については、「Azure Key Vault および Microsoft FastTrack for Customer Key のタスクを完了する」](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a404-361">See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) for information.</span></span>
  
<span data-ttu-id="5a404-362">Exchange Online と Skype for Business のカスタマー キーをセットアップするには、Exchange Online にリモートで接続して、次の手順をWindows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="5a404-362">To set up Customer Key for Exchange Online and Skype for Business, you'll complete these steps by remotely connecting to Exchange Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a><span data-ttu-id="5a404-363">Exchange Online および Skype for Business で使用するデータ暗号化ポリシー (DEP) を作成する</span><span class="sxs-lookup"><span data-stu-id="5a404-363">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>

<span data-ttu-id="5a404-364">DEP は、Azure Key Vault に格納されている一連のキーに関連付けられる。</span><span class="sxs-lookup"><span data-stu-id="5a404-364">A DEP is associated with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="5a404-365">DEP を Microsoft 365 のメールボックスに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="5a404-365">You assign a DEP to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="5a404-366">その後、Microsoft 365 はポリシーで識別されたキーを使用してメールボックスを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="5a404-366">Microsoft 365 will then use the keys identified in the policy to encrypt the mailbox.</span></span> <span data-ttu-id="5a404-367">DEP を作成するには、前に取得した Key Vault URI が必要です。</span><span class="sxs-lookup"><span data-stu-id="5a404-367">To create the DEP, you need the Key Vault URIs you obtained earlier.</span></span> <span data-ttu-id="5a404-368">手順 [については、「各 Azure Key Vault キーの URI を取得する」](#obtain-the-uri-for-each-azure-key-vault-key) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a404-368">See [Obtain the URI for each Azure Key Vault key](#obtain-the-uri-for-each-azure-key-vault-key) for instructions.</span></span>
  
<span data-ttu-id="5a404-369">覚えておいてください!</span><span class="sxs-lookup"><span data-stu-id="5a404-369">Remember!</span></span> <span data-ttu-id="5a404-370">DEP を作成する場合は、2 つの異なる Azure キー コンテナーに 2 つのキーを指定します。</span><span class="sxs-lookup"><span data-stu-id="5a404-370">When you create a DEP, you specify two keys in two different Azure Key Vaults.</span></span> <span data-ttu-id="5a404-371">地理的冗長性を確保するために、これらのキーを 2 つの別個の Azure リージョンに作成します。</span><span class="sxs-lookup"><span data-stu-id="5a404-371">Create these keys in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="5a404-372">DEP を作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5a404-372">To create the DEP, follow these steps:</span></span>
  
1. <span data-ttu-id="5a404-373">ローカル コンピューターで、組織内のグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用して、別のウィンドウで [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) にWindows PowerShellします。</span><span class="sxs-lookup"><span data-stu-id="5a404-373">On your local computer, using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="5a404-374">DEP を作成するには、次のコマンドNew-DataEncryptionPolicyコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="5a404-374">To create a DEP, use the New-DataEncryptionPolicy cmdlet by typing the following command.</span></span>

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   <span data-ttu-id="5a404-375">ここで、</span><span class="sxs-lookup"><span data-stu-id="5a404-375">Where:</span></span>

   - <span data-ttu-id="5a404-376">*PolicyName* は、ポリシーに使用する名前です。</span><span class="sxs-lookup"><span data-stu-id="5a404-376">*PolicyName* is the name you want to use for the policy.</span></span> <span data-ttu-id="5a404-377">名前にスペースを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="5a404-377">Names can't contain spaces.</span></span> <span data-ttu-id="5a404-378">たとえば、USA_mailboxes。</span><span class="sxs-lookup"><span data-stu-id="5a404-378">For example, USA_mailboxes.</span></span>

   - <span data-ttu-id="5a404-379">*ポリシーの* 説明は、ポリシーの内容を思い出すのに役立つ、ユーザーフレンドリーなポリシーの説明です。</span><span class="sxs-lookup"><span data-stu-id="5a404-379">*Policy Description* is a user-friendly description of the policy that will help you remember what the policy is for.</span></span> <span data-ttu-id="5a404-380">説明にスペースを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="5a404-380">You can include spaces in the description.</span></span> <span data-ttu-id="5a404-381">たとえば、「米国とその地域のメールボックスのルート キー」です。</span><span class="sxs-lookup"><span data-stu-id="5a404-381">For example, "Root key for mailboxes in USA and its territories".</span></span>

   - <span data-ttu-id="5a404-382">*KeyVaultURI1 は* 、ポリシーの最初のキーの URI です。</span><span class="sxs-lookup"><span data-stu-id="5a404-382">*KeyVaultURI1* is the URI for the first key in the policy.</span></span> <span data-ttu-id="5a404-383">たとえば、<https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01> などです。</span><span class="sxs-lookup"><span data-stu-id="5a404-383">For example, <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.</span></span>

   - <span data-ttu-id="5a404-384">*KeyVaultURI2* は、ポリシー内の 2 番目のキーの URI です。</span><span class="sxs-lookup"><span data-stu-id="5a404-384">*KeyVaultURI2* is the URI for the second key in the policy.</span></span> <span data-ttu-id="5a404-385">たとえば、<https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02> などです。</span><span class="sxs-lookup"><span data-stu-id="5a404-385">For example, <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>.</span></span> <span data-ttu-id="5a404-386">2 つの URI をコンマとスペースで区切ります。</span><span class="sxs-lookup"><span data-stu-id="5a404-386">Separate the two URIs by a comma and a space.</span></span>

   <span data-ttu-id="5a404-387">例:</span><span class="sxs-lookup"><span data-stu-id="5a404-387">Example:</span></span>
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

<span data-ttu-id="5a404-388">構文とパラメーターの詳細については [、「New-DataEncryptionPolicy」を参照してください](/powershell/module/exchange/new-data-encryptionpolicy)。</span><span class="sxs-lookup"><span data-stu-id="5a404-388">For detailed syntax and parameter information, see [New-DataEncryptionPolicy](/powershell/module/exchange/new-data-encryptionpolicy).</span></span>

### <a name="assign-a-dep-to-a-mailbox"></a><span data-ttu-id="5a404-389">メールボックスへの DEP の割り当て</span><span class="sxs-lookup"><span data-stu-id="5a404-389">Assign a DEP to a mailbox</span></span>

<span data-ttu-id="5a404-390">DEP をメールボックスに割り当てるには、このコマンドレットSet-Mailboxします。</span><span class="sxs-lookup"><span data-stu-id="5a404-390">Assign the DEP to a mailbox by using the Set-Mailbox cmdlet.</span></span> <span data-ttu-id="5a404-391">ポリシーを割り当てると、Microsoft 365 は DEP で識別されたキーを使用してメールボックスを暗号化できます。</span><span class="sxs-lookup"><span data-stu-id="5a404-391">Once you assign the policy, Microsoft 365 can encrypt the mailbox with the key identified in the DEP.</span></span>
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="5a404-392">*MailboxIdParameter はユーザー* メールボックスを指定します。</span><span class="sxs-lookup"><span data-stu-id="5a404-392">Where *MailboxIdParameter* specifies a user mailbox.</span></span> <span data-ttu-id="5a404-393">このコマンドレットの詳細についてはSet-Mailbox [Set-Mailbox を参照してください](/powershell/module/exchange/set-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="5a404-393">For more information about the Set-Mailbox cmdlet, see [Set-Mailbox](/powershell/module/exchange/set-mailbox).</span></span>

<span data-ttu-id="5a404-394">ハイブリッド環境では、Exchange Online テナントに同期されているオンプレミスのメールボックス データに DEP を割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="5a404-394">In hybrid environments, you can assign a DEP to the on-premises mailbox data that is synchronized into your Exchange Online tenant.</span></span> <span data-ttu-id="5a404-395">この同期されたメールボックス データに DEP を割り当てるには、次のコマンドレットSet-MailUserします。</span><span class="sxs-lookup"><span data-stu-id="5a404-395">To assign a DEP to this synchronized mailbox data, you'll use the Set-MailUser cmdlet.</span></span> <span data-ttu-id="5a404-396">ハイブリッド環境のメールボックス データの詳細については、「ハイブリッドモダン認証を使用した Outlook for iOS および Android を使用するオンプレミスメールボックス」 [を参照してください](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)。</span><span class="sxs-lookup"><span data-stu-id="5a404-396">For more information about mailbox data in the hybrid environment, see [on-premises mailboxes using Outlook for iOS and Android with hybrid Modern Authentication](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth).</span></span>

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="5a404-397">*MailUserIdParameter はメール* ユーザー (メールが有効なユーザーとも呼ばれる) を指定します。</span><span class="sxs-lookup"><span data-stu-id="5a404-397">Where *MailUserIdParameter* specifies a mail user (also known as a mail-enabled user).</span></span> <span data-ttu-id="5a404-398">このコマンドレットの詳細についてはSet-MailUser [Set-MailUser を参照してください](/powershell/module/exchange/set-mailuser)。</span><span class="sxs-lookup"><span data-stu-id="5a404-398">For more information about the Set-MailUser cmdlet, see [Set-MailUser](/powershell/module/exchange/set-mailuser).</span></span>
  
### <a name="validate-mailbox-encryption"></a><span data-ttu-id="5a404-399">メールボックスの暗号化を検証する</span><span class="sxs-lookup"><span data-stu-id="5a404-399">Validate mailbox encryption</span></span>

<span data-ttu-id="5a404-400">メールボックスの暗号化には時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5a404-400">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="5a404-401">初めてのポリシー割り当てでは、サービスがメールボックスを暗号化する前に、メールボックスをあるデータベースから別のデータベースに完全に移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a404-401">For first-time policy assignment, the mailbox must also completely move from one database to another before the service can encrypt the mailbox.</span></span> <span data-ttu-id="5a404-402">DEP を変更した後、または初めてメールボックスに DEP を割り当てると、暗号化の検証を試行するまで 72 時間待機することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5a404-402">We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="5a404-403">メールボックスが暗号化Get-MailboxStatisticsを判断するには、このコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5a404-403">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="5a404-404">IsEncrypted プロパティは、メールボックスが暗号化されている場合は true、メールボックスが暗号化されていない場合は **false** の値を返します。</span><span class="sxs-lookup"><span data-stu-id="5a404-404">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox isn't encrypted.</span></span> <span data-ttu-id="5a404-405">メールボックスの移動を完了する時間は、初めて DEP を割り当てるメールボックスの数と、メールボックスのサイズによって異なります。</span><span class="sxs-lookup"><span data-stu-id="5a404-405">The time to complete mailbox moves depends on the number of mailboxes to which you assign a DEP for the first time, and the size of the mailboxes.</span></span> <span data-ttu-id="5a404-406">DEP を割り当てた時刻から 1 週間後にメールボックスが暗号化されていない場合は、Microsoft にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="5a404-406">If the mailboxes haven't been encrypted after a week from the time you assigned the DEP, contact Microsoft.</span></span>

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="5a404-407">Office 365: SharePoint Online、OneDrive for Business、Teams ファイルのカスタマー キーの設定</span><span class="sxs-lookup"><span data-stu-id="5a404-407">Office 365: Setting up Customer Key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="5a404-408">開始する前に、Azure Key Vault のセットアップに必要なタスクが完了している必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a404-408">Before you begin, ensure that you've completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="5a404-409">詳細 [については、「Azure Key Vault および Microsoft FastTrack for Customer Key のタスクを完了する」](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a404-409">See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) for information.</span></span>
  
<span data-ttu-id="5a404-410">SharePoint Online、OneDrive for Business、Teams ファイルのカスタマー キーを設定するには、SharePoint Online にリモートで接続して、これらの手順をWindows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="5a404-410">To set up Customer Key for SharePoint Online, OneDrive for Business, and Teams files you complete these steps by remotely connecting to SharePoint Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a><span data-ttu-id="5a404-411">SharePoint Online および OneDrive for Business geo ごとにデータ暗号化ポリシー (DEP) を作成する</span><span class="sxs-lookup"><span data-stu-id="5a404-411">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>

<span data-ttu-id="5a404-412">DEP を Azure Key Vault に格納されている一連のキーに関連付ける。</span><span class="sxs-lookup"><span data-stu-id="5a404-412">You associate a DEP with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="5a404-413">DEP は、地理と呼ばれる 1 つの地理的な場所のすべてのデータに適用します。</span><span class="sxs-lookup"><span data-stu-id="5a404-413">You apply a DEP to all of your data in one geographic location, also called a geo.</span></span> <span data-ttu-id="5a404-414">Office 365 の複数地域機能を使用する場合は、geo ごとに異なるキーを使用する機能を使用して、地域ごとに 1 つの DEP を作成できます。</span><span class="sxs-lookup"><span data-stu-id="5a404-414">If you use the multi-geo feature of Office 365, you can create one DEP per geo with the capability to use different keys per geo.</span></span> <span data-ttu-id="5a404-415">複数地域を使用していない場合は、SharePoint Online、OneDrive for Business、Teams ファイルで使用するために、組織内に 1 つの DEP を作成できます。</span><span class="sxs-lookup"><span data-stu-id="5a404-415">If you aren't using multi-geo, you can create one DEP in your organization for use with SharePoint Online, OneDrive for Business, and Teams files.</span></span> <span data-ttu-id="5a404-416">Microsoft 365 では、DEP で識別されたキーを使用して、その地域のデータを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="5a404-416">Microsoft 365 uses the keys identified in the DEP to encrypt your data in that geo.</span></span> <span data-ttu-id="5a404-417">DEP を作成するには、前に取得した Key Vault URI が必要です。</span><span class="sxs-lookup"><span data-stu-id="5a404-417">To create the DEP, you need the Key Vault URIs you obtained earlier.</span></span> <span data-ttu-id="5a404-418">手順 [については、「各 Azure Key Vault キーの URI を取得する」](#obtain-the-uri-for-each-azure-key-vault-key) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a404-418">See [Obtain the URI for each Azure Key Vault key](#obtain-the-uri-for-each-azure-key-vault-key) for instructions.</span></span>
  
<span data-ttu-id="5a404-419">覚えておいてください!</span><span class="sxs-lookup"><span data-stu-id="5a404-419">Remember!</span></span> <span data-ttu-id="5a404-420">DEP を作成する場合は、2 つの異なる Azure キー コンテナーに 2 つのキーを指定します。</span><span class="sxs-lookup"><span data-stu-id="5a404-420">When you create a DEP, you specify two keys in two different Azure Key Vaults.</span></span> <span data-ttu-id="5a404-421">地理的冗長性を確保するために、これらのキーを 2 つの別個の Azure リージョンに作成します。</span><span class="sxs-lookup"><span data-stu-id="5a404-421">Create these keys in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="5a404-422">DEP を作成するには、サーバーを使用して SharePoint Online にリモートWindows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="5a404-422">To create a DEP, you need to remotely connect to SharePoint Online by using Windows PowerShell.</span></span>
  
1. <span data-ttu-id="5a404-423">ローカル コンピューターで、組織内でグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用して [、SharePoint Online PowerShell に接続します](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps)。</span><span class="sxs-lookup"><span data-stu-id="5a404-423">On your local computer, using a work or school account that has global administrator permissions in your organization, [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps).</span></span>

2. <span data-ttu-id="5a404-424">Microsoft SharePoint Online 管理シェルで、次のように Register-SPODataEncryptionPolicyコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a404-424">In the Microsoft SharePoint Online Management Shell, run the Register-SPODataEncryptionPolicy cmdlet as follows:</span></span>

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <adminSiteCollectionURL> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   <span data-ttu-id="5a404-425">例:</span><span class="sxs-lookup"><span data-stu-id="5a404-425">Example:</span></span>
  
   ```powershell
   Register-SPODataEncryptionPolicy -Identity https://contoso.sharepoint.com -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a’
   ```

   <span data-ttu-id="5a404-426">DEP を登録すると、geo のデータで暗号化が開始されます。</span><span class="sxs-lookup"><span data-stu-id="5a404-426">When you register the DEP, encryption begins on the data in the geo.</span></span> <span data-ttu-id="5a404-427">暗号化には時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5a404-427">Encryption can take some time.</span></span> <span data-ttu-id="5a404-428">このパラメーターの使用の詳細については [、「Register-SPODataEncryptionPolicy」を参照してください](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps)。</span><span class="sxs-lookup"><span data-stu-id="5a404-428">For more information on using this parameter, see [Register-SPODataEncryptionPolicy](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps).</span></span>

### <a name="validate-file-encryption"></a><span data-ttu-id="5a404-429">ファイルの暗号化を検証する</span><span class="sxs-lookup"><span data-stu-id="5a404-429">Validate file encryption</span></span>

 <span data-ttu-id="5a404-430">SharePoint Online、OneDrive for Business、Teams ファイルの暗号化を検証するには [、SharePoint Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)に接続し、Get-SPODataEncryptionPolicy コマンドレットを使用してテナントの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="5a404-430">To validate encryption of SharePoint Online, OneDrive for Business, and Teams files, [connect to SharePoint Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell), and then use the Get-SPODataEncryptionPolicy cmdlet to check the status of your tenant.</span></span> <span data-ttu-id="5a404-431">State _プロパティ_ は、顧客キーの暗号化が有効で、すべてのサイト内のすべてのファイルが暗号化されている場合に、登録済みの値を返します。</span><span class="sxs-lookup"><span data-stu-id="5a404-431">The _State_ property returns a value of **registered** if Customer Key encryption is enabled and all files in all sites have been encrypted.</span></span> <span data-ttu-id="5a404-432">暗号化がまだ進行中の場合、このコマンドレットは登録の値を **返します**。</span><span class="sxs-lookup"><span data-stu-id="5a404-432">If encryption is still in progress, this cmdlet returns a value of **registering**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="5a404-433">関連記事</span><span class="sxs-lookup"><span data-stu-id="5a404-433">Related articles</span></span>

- [<span data-ttu-id="5a404-434">カスタマー キーによるサービスの暗号化</span><span class="sxs-lookup"><span data-stu-id="5a404-434">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="5a404-435">顧客キーの管理</span><span class="sxs-lookup"><span data-stu-id="5a404-435">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="5a404-436">カスタマー キーまたは可用性キーをローリングまたはローテーションする</span><span class="sxs-lookup"><span data-stu-id="5a404-436">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="5a404-437">可用性キーの詳細</span><span class="sxs-lookup"><span data-stu-id="5a404-437">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="5a404-438">サービスの暗号化</span><span class="sxs-lookup"><span data-stu-id="5a404-438">Service Encryption</span></span>](office-365-service-encryption.md)