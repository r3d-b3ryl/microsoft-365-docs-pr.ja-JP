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
description: Microsoft 365 for Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business、および Teams ファイルのカスタマー キーを設定する方法について説明します。
ms.openlocfilehash: a89b5cb4144de3b548c7ac328f0be775b4262cdc
ms.sourcegitcommit: 8a6540df9d63db1ffb69711381dc44fc2fdaf547
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/29/2020
ms.locfileid: "49736066"
---
# <a name="set-up-customer-key-at-the-application-level"></a><span data-ttu-id="dfeb2-103">アプリケーション レベルで顧客キーを設定する</span><span class="sxs-lookup"><span data-stu-id="dfeb2-103">Set up Customer Key at the application level</span></span>

<span data-ttu-id="dfeb2-104">顧客キーを使用すると、組織の暗号化キーを制御し、Microsoft のデータ センターで保存されているデータを暗号化するために使用する Microsoft 365 を構成します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-104">With Customer Key, you control your organization's encryption keys and then configure Microsoft 365 to use them to encrypt your data at rest in Microsoft's data centers.</span></span> <span data-ttu-id="dfeb2-105">つまり、顧客キーを使用すると、顧客は自分のキーを使用して、顧客に属する暗号化のレイヤーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-105">In other words, Customer Key allows customers to add a layer of encryption that belongs to them, with their keys.</span></span> <span data-ttu-id="dfeb2-106">保存データには、メールボックスに保存されている Exchange Online および Skype for Business からのデータと、SharePoint Online および OneDrive for Business に保存されているファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-106">Data at rest includes data from Exchange Online and Skype for Business that is stored in mailboxes and files that are stored in SharePoint Online and OneDrive for Business.</span></span>

<span data-ttu-id="dfeb2-107">顧客キーを 365 用に使用する前に、Azure をOfficeがあります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-107">You must set up Azure before you can use Customer Key for Office 365.</span></span> <span data-ttu-id="dfeb2-108">このトピックでは、必要な Azure リソースを作成および構成するために従う必要がある手順について説明し、Office 365 で顧客キーを設定する手順を示します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-108">This topic describes the steps you need to follow to create and configure the required Azure resources and then provides the steps for setting up Customer Key in Office 365.</span></span> <span data-ttu-id="dfeb2-109">Azure のセットアップが完了したら、組織内のメールボックスとファイルに割り当てるポリシーとキーを決定します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-109">After you have completed Azure setup, you determine which policy, and therefore, which keys, to assign to mailboxes and files in your organization.</span></span> <span data-ttu-id="dfeb2-110">ポリシーを割り当てないメールボックスとファイルは、Microsoft によって制御および管理される暗号化ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-110">Mailboxes and files for which you don't assign a policy will use encryption policies that are controlled and managed by Microsoft.</span></span> <span data-ttu-id="dfeb2-111">顧客キーの詳細、または一般的な概要については、「顧客キーを使用したサービスの暗号化」を参照してください。Office [365](customer-key-overview.md).</span><span class="sxs-lookup"><span data-stu-id="dfeb2-111">For more information about Customer Key, or for a general overview, see [Service encryption with Customer Key in Office 365](customer-key-overview.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="dfeb2-112">このトピックのベスト プラクティスに従ってください。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-112">We strongly recommend that you follow the best practices in this topic.</span></span> <span data-ttu-id="dfeb2-113">これらはヒントと **重要として呼** び **出されます**。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-113">These are called out as **TIP** and **IMPORTANT**.</span></span> <span data-ttu-id="dfeb2-114">顧客キーを使用すると、組織全体と同じ大きなスコープを持つルート暗号化キーを制御できます。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-114">Customer Key gives you control over root encryption keys whose scope can be as large as your entire organization.</span></span> <span data-ttu-id="dfeb2-115">つまり、これらのキーの間違いは広範な影響を与える可能性があります。サービスが中断したり、データが取り消し可能な損失を引き起こす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-115">This means that mistakes made with these keys can have a broad impact and may result in service interruptions or irrevocable loss of your data.</span></span>
  
## <a name="before-you-set-up-customer-key"></a><span data-ttu-id="dfeb2-116">顧客キーを設定する前に</span><span class="sxs-lookup"><span data-stu-id="dfeb2-116">Before you set up Customer Key</span></span>

<span data-ttu-id="dfeb2-117">開始する前に、組織に適したライセンスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-117">Before you get started, ensure that you have the appropriate licensing for your organization.</span></span> <span data-ttu-id="dfeb2-118">サブスクリプションまたはクラウド サービス プロバイダーを使用して、有料マイクロソフトエンタープライズ契約 Azure サブスクリプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-118">Use a paid, invoiced Azure Subscription using either an Enterprise Agreement or a Cloud Service Provider.</span></span> <span data-ttu-id="dfeb2-119">[お支払い方法] プランまたはクレジット カードを使用して購入した Azure サブスクリプションは、カスタマー キーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-119">Azure Subscriptions purchased using Pay As You Go plans or using a credit card aren't supported for Customer Key.</span></span> <span data-ttu-id="dfeb2-120">Office 365 のカスタマー キーは、2020 年 4 月 1 日から Office 365 E5、M365 E5、M365 E5 コンプライアンス、M365 E5 情報保護 & ガバナンス SKU で提供されます。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-120">Starting April 1, 2020, Customer Key in Office 365 is offered in Office 365 E5, M365 E5, M365 E5 Compliance, and M365 E5 Information Protection & Governance SKUs.</span></span> <span data-ttu-id="dfeb2-121">Office 365 Advanced Compliance SKU は、新しいライセンスの調達には使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-121">Office 365 Advanced Compliance SKU is no longer available for procuring new licenses.</span></span> <span data-ttu-id="dfeb2-122">既存の Office 365 Advanced Compliance ライセンスは引き続きサポートされます。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-122">Existing Office 365 Advanced Compliance licenses will continue to be supported.</span></span>

<span data-ttu-id="dfeb2-123">このトピックの概念と手順を理解するには [、Azure Key Vault のドキュメントを確認](https://docs.microsoft.com/azure/key-vault/) してください。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-123">To understand the concepts and procedures in this topic, review the [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/) documentation.</span></span> <span data-ttu-id="dfeb2-124">また [、Azure](https://docs.microsoft.com/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant)テナントなど、Azure で使用される用語ADします。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-124">Also, become familiar with the terms used in Azure, for example, [Azure AD tenant](https://docs.microsoft.com/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant).</span></span>

<span data-ttu-id="dfeb2-125">FastTrack は、顧客キーの登録に使用される必要なテナントおよびサービス構成情報の収集にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-125">FastTrack is only used to collect the required tenant and service configuration information used to register for Customer Key.</span></span> <span data-ttu-id="dfeb2-126">顧客キーオファーは FastTrack 経由で公開され、お客様とパートナーが同じ方法で必要な情報を送信する際に便利です。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-126">The Customer Key Offers are published via FastTrack so that it is convenient for you and our partners to submit the required information using the same method.</span></span> <span data-ttu-id="dfeb2-127">FastTrack では、オファーで提供するデータを簡単にアーカイブできます。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-127">FastTrack also makes it easy to archive the data that you provide in the Offer.</span></span>
  
<span data-ttu-id="dfeb2-128">ドキュメント以外のサポートが必要な場合は、Microsoft Consulting Services (MCS)、Premier Field Engineering (PFE)、または Microsoft パートナーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-128">If you need additional support beyond the documentation, contact Microsoft Consulting Services (MCS), Premier Field Engineering (PFE), or a Microsoft partner for assistance.</span></span> <span data-ttu-id="dfeb2-129">ドキュメントを含む顧客キーに関するフィードバックを提供するには、アイデア、提案、視点を顧客にcustomerkeyfeedback@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-129">To provide feedback on Customer Key, including the documentation, send your ideas, suggestions, and perspectives to customerkeyfeedback@microsoft.com.</span></span>
  
## <a name="overview-of-steps-to-set-up-customer-key"></a><span data-ttu-id="dfeb2-130">顧客キーを設定する手順の概要</span><span class="sxs-lookup"><span data-stu-id="dfeb2-130">Overview of steps to set up Customer Key</span></span>

<span data-ttu-id="dfeb2-131">顧客キーを設定するには、これらのタスクを記載されている順序で完了します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-131">To set up Customer Key, complete these tasks in the listed order.</span></span> <span data-ttu-id="dfeb2-132">この記事の残りの部分では、各タスクの詳細な手順を示します。または、プロセスの各手順に関する詳細な情報にリンクします。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-132">The rest of this article provides detailed instructions for each task, or links out to more information for each step in the process.</span></span>
  
<span data-ttu-id="dfeb2-133">**Azure と Microsoft FastTrack の場合:**</span><span class="sxs-lookup"><span data-stu-id="dfeb2-133">**In Azure and Microsoft FastTrack:**</span></span>
  
<span data-ttu-id="dfeb2-134">これらのタスクの大部分は、Azure PowerShell にリモートで接続することで完了します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-134">You will complete most of these tasks by remotely connecting to Azure PowerShell.</span></span> <span data-ttu-id="dfeb2-135">最適な結果を得る場合は、Azure PowerShell のバージョン 4.4.0 以降を使用してください。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-135">For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>
  
- [<span data-ttu-id="dfeb2-136">2 つの新しい Azure サブスクリプションを作成する</span><span class="sxs-lookup"><span data-stu-id="dfeb2-136">Create two new Azure subscriptions</span></span>](#create-two-new-azure-subscriptions)

- [<span data-ttu-id="dfeb2-137">Azure サブスクリプションを登録して必須の保持期間を使用する</span><span class="sxs-lookup"><span data-stu-id="dfeb2-137">Register Azure subscriptions to use a mandatory retention period</span></span>](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  <span data-ttu-id="dfeb2-138">登録には 1 ~ 5 営業日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-138">Registration can take from one to five business days.</span></span>

- [<span data-ttu-id="dfeb2-139">顧客キーをアクティブ化する要求を 365 Office送信する</span><span class="sxs-lookup"><span data-stu-id="dfeb2-139">Submit a request to activate Customer Key for Office 365</span></span>](#submit-a-request-to-activate-customer-key-for-office-365)

<span data-ttu-id="dfeb2-140">2 つの新しい Azure サブスクリプションを作成したら、Microsoft FastTrack ポータルでホストされている Web フォームを完成して、適切な顧客キーの提供要求を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-140">Once you've created the two new Azure subscriptions, you'll need to submit the appropriate Customer Key offer request by completing a web form that is hosted in the Microsoft FastTrack portal.</span></span> <span data-ttu-id="dfeb2-141">**FastTrack チームは、カスタマー キーのサポートを提供します。Office FastTrack** ポータルを使用するだけで、フォームを提出し、顧客キーの関連するオファーを追跡するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-141">**The FastTrack team doesn't provide assistance with Customer Key. Office simply uses the FastTrack portal to allow you to submit the form and to help us track the relevant offers for Customer Key**.</span></span>

- [<span data-ttu-id="dfeb2-142">各サブスクリプションにプレミアム Azure Key Vault を作成する</span><span class="sxs-lookup"><span data-stu-id="dfeb2-142">Create a premium Azure Key Vault in each subscription</span></span>](#create-a-premium-azure-key-vault-in-each-subscription)

- [<span data-ttu-id="dfeb2-143">各キー コンテナーにアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="dfeb2-143">Assign permissions to each key vault</span></span>](#assign-permissions-to-each-key-vault)

- [<span data-ttu-id="dfeb2-144">キー コンテナーで回復可能な削除を有効にして確認する</span><span class="sxs-lookup"><span data-stu-id="dfeb2-144">Enable and then confirm soft delete on your key vaults</span></span>](#enable-and-then-confirm-soft-delete-on-your-key-vaults)

- [<span data-ttu-id="dfeb2-145">キーを作成またはインポートして、各キー コンテナーにキーを追加する</span><span class="sxs-lookup"><span data-stu-id="dfeb2-145">Add a key to each key vault either by creating or importing a key</span></span>](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [<span data-ttu-id="dfeb2-146">キーの回復レベルを確認する</span><span class="sxs-lookup"><span data-stu-id="dfeb2-146">Check the recovery level of your keys</span></span>](#check-the-recovery-level-of-your-keys)

- [<span data-ttu-id="dfeb2-147">Azure Key Vault をバックアップする</span><span class="sxs-lookup"><span data-stu-id="dfeb2-147">Back up Azure Key Vault</span></span>](#back-up-azure-key-vault)

- [<span data-ttu-id="dfeb2-148">Azure Key Vault の構成設定を検証する</span><span class="sxs-lookup"><span data-stu-id="dfeb2-148">Validate Azure Key Vault configuration settings</span></span>](#validate-azure-key-vault-configuration-settings)

- [<span data-ttu-id="dfeb2-149">各 Azure Key Vault キーの URI を取得する</span><span class="sxs-lookup"><span data-stu-id="dfeb2-149">Obtain the URI for each Azure Key Vault key</span></span>](#obtain-the-uri-for-each-azure-key-vault-key)

<span data-ttu-id="dfeb2-150">**Office 365:**</span><span class="sxs-lookup"><span data-stu-id="dfeb2-150">**In Office 365:**</span></span>
  
<span data-ttu-id="dfeb2-151">Exchange Online と Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="dfeb2-151">Exchange Online and Skype for Business:</span></span>
  
- [<span data-ttu-id="dfeb2-152">Exchange Online および Skype for Business で使用するデータ暗号化ポリシー (DEP) を作成する</span><span class="sxs-lookup"><span data-stu-id="dfeb2-152">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>](#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)

- [<span data-ttu-id="dfeb2-153">メールボックスに DEP を割り当てる</span><span class="sxs-lookup"><span data-stu-id="dfeb2-153">Assign a DEP to a mailbox</span></span>](#assign-a-dep-to-a-mailbox)

- [<span data-ttu-id="dfeb2-154">メールボックスの暗号化を検証する</span><span class="sxs-lookup"><span data-stu-id="dfeb2-154">Validate mailbox encryption</span></span>](#validate-mailbox-encryption)

<span data-ttu-id="dfeb2-155">SharePoint Online と OneDrive for Business:</span><span class="sxs-lookup"><span data-stu-id="dfeb2-155">SharePoint Online and OneDrive for Business:</span></span>
  
- [<span data-ttu-id="dfeb2-156">SharePoint Online および OneDrive for Business 地域ごとにデータ暗号化ポリシー (DEP) を作成する</span><span class="sxs-lookup"><span data-stu-id="dfeb2-156">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>](#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)

- [<span data-ttu-id="dfeb2-157">SharePoint Online、OneDrive for Business、および Teams ファイルのファイル暗号化を検証する</span><span class="sxs-lookup"><span data-stu-id="dfeb2-157">Validate file encryption for SharePoint Online, OneDrive for Business, and Teams files</span></span>](#validate-file-encryption)

## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a><span data-ttu-id="dfeb2-158">顧客キーの Azure Key Vault と Microsoft FastTrack のタスクを完了する</span><span class="sxs-lookup"><span data-stu-id="dfeb2-158">Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key</span></span>

<span data-ttu-id="dfeb2-159">Azure Key Vault でこれらのタスクを完了します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-159">Complete these tasks in Azure Key Vault.</span></span> <span data-ttu-id="dfeb2-160">これらの手順は、Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business、Teams のファイル、または Office 365 でサポートされているサービスのカスタマー キーを設定する予定かどうかに関係なく実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-160">You'll need to complete these steps regardless of whether you intend to set up Customer Key for Exchange Online and Skype for Business or for SharePoint Online, OneDrive for Business, and Teams files, or for all supported services in Office 365.</span></span>
  
### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="dfeb2-161">2 つの新しい Azure サブスクリプションを作成する</span><span class="sxs-lookup"><span data-stu-id="dfeb2-161">Create two new Azure subscriptions</span></span>

<span data-ttu-id="dfeb2-162">顧客キーには 2 つの Azure サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-162">Customer Key requires two Azure subscriptions.</span></span> <span data-ttu-id="dfeb2-163">ベスト プラクティスとして、Microsoft では、顧客キーで使用する新しい Azure サブスクリプションを作成するようにお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-163">As a best practice, Microsoft recommends that you create new Azure subscriptions for use with Customer Key.</span></span> <span data-ttu-id="dfeb2-164">Azure Key Vault キーは、同じ Azure Active Directory (Microsoft Azure Active Directory) テナント内のアプリケーションにのみ承認できます。DEP が割り当てられる組織と同じ Azure AD テナントを使用して、新しいサブスクリプションを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-164">Azure Key Vault keys can only be authorized for applications in the same Azure Active Directory (Microsoft Azure Active Directory) tenant, you must create the new subscriptions using the same Azure AD tenant used with your organization where the DEPs will be assigned.</span></span> <span data-ttu-id="dfeb2-165">たとえば、組織内のグローバル管理者特権を持つ、仕事用または学校用のアカウントを使用する場合などです。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-165">For example, using your work or school account that has global administrator privileges in your organization.</span></span> <span data-ttu-id="dfeb2-166">詳細な手順については、「 [組織として Azure にサインアップする」を参照してください](https://azure.microsoft.com/documentation/articles/sign-up-organization/)。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-166">For detailed steps, see [Sign up for Azure as an organization](https://azure.microsoft.com/documentation/articles/sign-up-organization/).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="dfeb2-167">顧客キーには、データ暗号化ポリシー (DEP) ごとに 2 つのキーが必要です。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-167">Customer Key requires two keys for each data encryption policy (DEP).</span></span> <span data-ttu-id="dfeb2-168">これを実現するには、2 つの Azure サブスクリプションを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-168">In order to achieve this, you must create two Azure subscriptions.</span></span> <span data-ttu-id="dfeb2-169">ベスト プラクティスとして、組織の個別のメンバーがサブスクリプションごとに 1 つのキーを構成する方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-169">As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription.</span></span> <span data-ttu-id="dfeb2-170">これらの Azure サブスクリプションは、365 年 365 日の暗号化キーを管理Officeしてください。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-170">You should only use these Azure subscriptions to administer encryption keys for Office 365.</span></span> <span data-ttu-id="dfeb2-171">これにより、オペレーターの 1 人が誤って、意図的に、または悪意を持って削除したり、責任を負うキーを誤って管理したりした場合に、組織を保護します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-171">This protects your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible.</span></span>
>

<span data-ttu-id="dfeb2-172">組織で作成できる Azure サブスクリプションの数に実際的な制限はありません。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-172">There is no practical limit to the number of Azure subscriptions that you can create for your organization.</span></span> <span data-ttu-id="dfeb2-173">これらのベスト プラクティスに従って、カスタマー キーで使用されるリソースを管理しながら、人的エラーの影響を最小限に抑えます。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-173">Following these best practices will minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span>
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a><span data-ttu-id="dfeb2-174">顧客キーをアクティブ化する要求を 365 Office送信する</span><span class="sxs-lookup"><span data-stu-id="dfeb2-174">Submit a request to activate Customer Key for Office 365</span></span>

<span data-ttu-id="dfeb2-175">Azure の手順を完了したら、Microsoft FastTrack ポータルでオファー要求を [送信する必要があります](https://fasttrack.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-175">Once you've completed the Azure steps, you'll need to submit an offer request in the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span> <span data-ttu-id="dfeb2-176">FastTrack Web ポータルから要求を送信すると、Microsoft は指定した Azure Key Vault 構成データと連絡先情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-176">Once you have submitted a request through the FastTrack web portal, Microsoft verifies the Azure Key Vault configuration data and contact information you provided.</span></span> <span data-ttu-id="dfeb2-177">組織の承認された責任者に関するオファー フォームでの選択は、顧客キーの登録を完了するために重要で必要です。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-177">The selections that you make in the offer form regarding the authorized officers of your organization is critical and necessary for completion of Customer Key registration.</span></span> <span data-ttu-id="dfeb2-178">フォームで選択した組織の責任者は、顧客キーデータの暗号化ポリシーで使用されるキーを取り消して破棄する要求の信頼性を確保するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-178">The officers of your organization that you select in the form will be the used to ensure the authenticity of any request to revoke and destroy all keys used with a Customer Key data encryption policy.</span></span> <span data-ttu-id="dfeb2-179">この手順は、Exchange Online および Skype for Business の対象範囲の顧客キーをアクティブ化するために 1 回だけ行い、もう 1 回は SharePoint Online と OneDrive for Business のカスタマー キーをアクティブ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-179">You'll need to do this step once to activate Customer Key for Exchange Online and Skype for Business coverage and a second time to activate Customer Key for SharePoint Online and OneDrive for Business.</span></span>
  
<span data-ttu-id="dfeb2-180">顧客キーをアクティブ化するオファーを提出するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-180">To submit an offer to activate Customer Key, complete these steps:</span></span>
  
1. <span data-ttu-id="dfeb2-181">組織のグローバル管理者アクセス許可を持つ、仕事または学校のアカウントを使用して [、Microsoft FastTrack ポータルにログインします](https://fasttrack.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-181">Using a work or school account that has global administrator permissions in your organization, log in to the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span>

2. <span data-ttu-id="dfeb2-182">ログインしたら、ダッシュボードを参照 **します**。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-182">Once you're logged in, browse to the **Dashboard**.</span></span>

3. <span data-ttu-id="dfeb2-183">ナビゲーション **バーから [展開**]を選択 **するか、[** 情報カードの展開] ですべての展開リソースを表示するを選択し、現在のオファーの一覧を確認します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-183">Choose **Deploy** from the navigation bar **OR** select **View all deployment resources** on the **Deploy** information card, and review the list of current offers.</span></span>

4. <span data-ttu-id="dfeb2-184">該当するオファーの情報カードを選択します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-184">Choose the information card for the offer that applies to you:</span></span>

   - <span data-ttu-id="dfeb2-185">**Exchange Online と Skype for Business:** Exchange オンライン オファー **の暗号化キーのヘルプを要求するを選択** します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-185">**Exchange Online and Skype for Business:** Choose the **Request encryption key help for Exchange online** offer.</span></span>

   - <span data-ttu-id="dfeb2-186">**SharePoint Online、OneDrive、および Teams のファイル:\*\*\*\*Sharepoint と OneDrive の提供の暗号化キーのヘルプを要求するを選択** します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-186">**SharePoint Online, OneDrive, and Teams files:** Choose the **Request encryption key help for Sharepoint and OneDrive** offer.</span></span>

5. <span data-ttu-id="dfeb2-187">オファーの詳細を確認したら、[手順 2 に進む] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-187">Once you've reviewed the offer details, choose **Continue to step 2**.</span></span>

6. <span data-ttu-id="dfeb2-188">すべての該当する詳細情報と要求された情報をオファー フォームに入力します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-188">Fill out all applicable details and requested information on the offer form.</span></span> <span data-ttu-id="dfeb2-189">暗号化キーとデータの永続的で取り返しのつまらない破棄を承認するために承認する組織の役員の選択に特に注意を払います。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-189">Pay particular attention to your selections for which officers of your organization you want to authorize to approve the permanent and irreversible destruction of encryption keys and data.</span></span> <span data-ttu-id="dfeb2-190">フォームが完成したら、[送信] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-190">Once you've completed the form, choose **Submit**.</span></span>

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="dfeb2-191">Azure サブスクリプションを登録して必須の保持期間を使用する</span><span class="sxs-lookup"><span data-stu-id="dfeb2-191">Register Azure subscriptions to use a mandatory retention period</span></span>

<span data-ttu-id="dfeb2-192">ルート暗号化キーが一時的または永続的に失われると、サービス操作が非常に破壊的または致命的になる可能性があります。データが失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-192">The temporary or permanent loss of root encryption keys can be very disruptive or even catastrophic to service operation and can result in data loss.</span></span> <span data-ttu-id="dfeb2-193">このため、顧客キーで使用されるリソースには強力な保護が必要です。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-193">For this reason, the resources used with Customer Key require strong protection.</span></span> <span data-ttu-id="dfeb2-194">顧客キーと一緒に使用される Azure リソースはすべて、既定の構成を超える保護メカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-194">All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration.</span></span> <span data-ttu-id="dfeb2-195">Azure サブスクリプションは、すぐに取り消し可能な取り消しを防ぐ方法でタグ付けまたは登録できます。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-195">Azure subscriptions can be tagged or registered in a way that will prevent immediate and irrevocable cancellation.</span></span> <span data-ttu-id="dfeb2-196">これは、必須の保持期間の登録と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-196">This is referred to as registering for a mandatory retention period.</span></span> <span data-ttu-id="dfeb2-197">必須の保持期間に Azure サブスクリプションを登録するために必要な手順には、Microsoft 365 チームとの共同作業が必要です。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-197">The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Microsoft 365 team.</span></span> <span data-ttu-id="dfeb2-198">このプロセスには 1 ~ 5 営業日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-198">This process can take from one to five business days.</span></span> <span data-ttu-id="dfeb2-199">以前は、これは "キャンセルしない" と呼ばれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-199">Previously, this was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="dfeb2-200">Microsoft 365 チームに連絡する前に、顧客キーで使用する Azure サブスクリプションごとに次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-200">Before contacting the Microsoft 365 team, you must perform the following steps for each Azure subscription that you use with Customer Key.</span></span> <span data-ttu-id="dfeb2-201">開始する前に [、Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) モジュールがインストールされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-201">Ensure that you have the [Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) module installed before you start.</span></span>
  
1. <span data-ttu-id="dfeb2-202">Azure PowerShell でサインインします。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-202">Sign in with Azure PowerShell.</span></span> <span data-ttu-id="dfeb2-203">手順については [、「Azure PowerShell でサインインする」を参照してください](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-203">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="dfeb2-204">Register-AzProviderFeatureコマンドレットを実行して、必須の保持期間を使用するためにサブスクリプションを登録します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-204">Run the Register-AzProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span> <span data-ttu-id="dfeb2-205">サブスクリプションごとにこのアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-205">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. <span data-ttu-id="dfeb2-206">プロセスの最終処理については、Microsoft にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-206">Contact Microsoft to have the process finalized.</span></span> <span data-ttu-id="dfeb2-207">SharePoint および OneDrive for Business チームの場合は、お問い[合spock@microsoft.com。](mailto:spock@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="dfeb2-207">For the SharePoint and OneDrive for Business team, contact [spock@microsoft.com](mailto:spock@microsoft.com).</span></span> <span data-ttu-id="dfeb2-208">Exchange Online および Skype for Business の場合は、お問い[合exock@microsoft.com。](mailto:exock@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="dfeb2-208">For Exchange Online and Skype for Business, contact [exock@microsoft.com](mailto:exock@microsoft.com).</span></span> <span data-ttu-id="dfeb2-209">メールに次の情報を含める:</span><span class="sxs-lookup"><span data-stu-id="dfeb2-209">Include the following in your email:</span></span>

   <span data-ttu-id="dfeb2-210">**件名**: 顧客キー \<*Your tenant's fully-qualified domain name*\></span><span class="sxs-lookup"><span data-stu-id="dfeb2-210">**Subject**: Customer Key for \<*Your tenant's fully-qualified domain name*\></span></span>

   <span data-ttu-id="dfeb2-211">**Body**: 必須の保持期間を確定するサブスクリプションの ID です。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-211">**Body**: Subscription IDs for which you want to have the mandatory retention period finalized.</span></span>
   <span data-ttu-id="dfeb2-212">各サブスクリプションのGet-AzProviderFeature出力。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-212">The output of Get-AzProviderFeature for each subscription.</span></span>

   <span data-ttu-id="dfeb2-213">このプロセスを完了するサービス レベル 契約 (SLA) は、サブスクリプションを登録して必須の保持期間を使用したという通知 (および確認) が Microsoft に送信された 5 営業日後です。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-213">The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period.</span></span>

4. <span data-ttu-id="dfeb2-214">登録が完了したという通知を Microsoft から受け取った後、次のように Get-AzProviderFeature コマンドを実行して、登録の状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-214">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzProviderFeature command as follows.</span></span> <span data-ttu-id="dfeb2-215">確認された場合、Get-AzProviderFeatureコマンドは Registration State プロパティの **Registered** の値 **を返** します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-215">If verified, the Get-AzProviderFeature command returns a value of **Registered** for the **Registration State** property.</span></span> <span data-ttu-id="dfeb2-216">サブスクリプションごとにこのアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-216">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. <span data-ttu-id="dfeb2-217">このプロセスを完了するには、次のコマンドRegister-AzResourceProviderします。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-217">To complete the process, run the Register-AzResourceProvider command.</span></span> <span data-ttu-id="dfeb2-218">サブスクリプションごとにこのアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-218">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="dfeb2-219">各サブスクリプションにプレミアム Azure Key Vault を作成する</span><span class="sxs-lookup"><span data-stu-id="dfeb2-219">Create a premium Azure Key Vault in each subscription</span></span>

<span data-ttu-id="dfeb2-220">キー コンテナーを作成する手順については [、「Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)の使用を開始する」に記載されています。この手順では、Azure PowerShell のインストールと起動、Azure サブスクリプションへの接続、リソース グループの作成、そのリソース グループでのキー コンテナーの作成について説明します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-220">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="dfeb2-221">キー コンテナーを作成する場合は、SKU (Standard または Premium) を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-221">When you create a key vault, you must choose a SKU: either Standard or Premium.</span></span> <span data-ttu-id="dfeb2-222">Standard SKU を使用すると、Azure Key Vault キーをソフトウェアで保護できます。ハードウェア セキュリティ モジュール (HS) キー保護はありません。また、Premium SKU では、キー コンテナー キーの保護に HSM を使用できます。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-222">The Standard SKU allows Azure Key Vault keys to be protected with software - there is no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys.</span></span> <span data-ttu-id="dfeb2-223">カスタマー キーは、いずれかの SKU を使用するキー コンテナーを受け入れるが、Premium SKU のみを使用する方法を強く推奨している。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-223">Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU.</span></span> <span data-ttu-id="dfeb2-224">どちらの種類のキーも操作のコストは同じなので、コストの唯一の違いは、各HSM で保護されたキーの 1 か月あたりのコストです。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-224">The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key.</span></span> <span data-ttu-id="dfeb2-225">詳細 [については、Key Vault の価格を](https://azure.microsoft.com/pricing/details/key-vault/) 参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-225">See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="dfeb2-226">実稼働データには Premium SKU キー コンテナーと SKU で保護されたキーを使用し、テストと検証の目的には Standard SKU キー コンテナーとキーのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-226">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span>
  
<span data-ttu-id="dfeb2-227">顧客キーを使用する Microsoft 365 サービスごとに、作成した 2 つの Azure サブスクリプションのそれぞれにキー コンテナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-227">For each Microsoft 365 service with which you will use Customer Key, create a key vault in each of the two Azure subscriptions that you created.</span></span> <span data-ttu-id="dfeb2-228">たとえば、Exchange Online と Skype for Business のみ、SharePoint Online と OneDrive for Business の場合は、1 組のコンテナーのみを作成します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-228">For example, for Exchange Online and Skype for Business only or SharePoint Online and OneDrive for Business only, you will create only one pair of vaults.</span></span> <span data-ttu-id="dfeb2-229">Exchange Online と SharePoint Online の両方で顧客キーを有効にするには、キー コンテナーの 2 つのペアを作成します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-229">To enable Customer Key for both Exchange Online and SharePoint Online, you will create two pairs of key vaults.</span></span>
  
<span data-ttu-id="dfeb2-230">コンテナーを関連付けるデータ暗号化ポリシーの意図した使用を反映するキー コンテナーの名前付け規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-230">Use a naming convention for key vaults that reflects the intended use of the data encryption policy with which you will associate the vaults.</span></span> <span data-ttu-id="dfeb2-231">名前付け規則の推奨事項については、以下のベスト プラクティスセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-231">See the Best Practices section below for naming convention recommendations.</span></span>
  
<span data-ttu-id="dfeb2-232">データ暗号化ポリシーごとに、個別のペアのコンテナーのセットを作成します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-232">Create a separate, paired set of vaults for each data encryption policy.</span></span> <span data-ttu-id="dfeb2-233">Exchange Online では、ポリシーをメールボックスに割り当てるときに、データ暗号化ポリシーのスコープが選択されます。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-233">For Exchange Online, the scope of a data encryption policy is chosen by you when you assign the policy to mailbox.</span></span> <span data-ttu-id="dfeb2-234">メールボックスに割り当て可能なポリシーは 1 つだけで、最大 50 個のポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-234">A mailbox can have only one policy assigned, and you can create up to fifty policies.</span></span> <span data-ttu-id="dfeb2-235">SharePoint Online の場合、ポリシーの範囲は、地理的な場所 _(geo)_ にある組織内のすべてのデータです。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-235">For SharePoint Online the scope of a policy is all of the data within an organization in a geographic location, or _geo_.</span></span>

<span data-ttu-id="dfeb2-236">キー コンテナーを作成するには Azure リソース グループの作成も必要です。キー コンテナーにはストレージ容量 (非常に小さい場合) と Key Vault ログ (有効な場合) も保存データが生成される必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-236">The creation of key vaults also requires the creation of Azure resource groups, since key vaults need storage capacity (though very small) and Key Vault logging, if enabled, also generates stored data.</span></span> <span data-ttu-id="dfeb2-237">ベスト プラクティスとして、関連する顧客キー リソースを管理する管理者のセットに合わせて管理を行い、個別の管理者を使用して各リソース グループを管理します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-237">As a best practice Microsoft recommends using separate administrators to manage each resource group, with the administration aligned with the set of administrators that will manage all related Customer Key resources.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="dfeb2-238">可用性を最大限に高め、キー コンテナーは Microsoft 365 サービスに近い地域に保管する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-238">To maximize availability, your key vaults should be in regions close to your Microsoft 365 service.</span></span> <span data-ttu-id="dfeb2-239">たとえば、Exchange Online 組織が北米にある場合は、キー コンテナーを北米に配置します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-239">For example, if your Exchange Online organization is in North America, place your key vaults in North America.</span></span> <span data-ttu-id="dfeb2-240">Exchange Online 組織がヨーロッパにある場合は、主要なコンテナーをヨーロッパに配置します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-240">If your Exchange Online organization is in Europe, place your key vaults in Europe.</span></span>
> 
> <span data-ttu-id="dfeb2-241">キー コンテナーに共通のプレフィックスを使用し、キー コンテナーとキーの使用とスコープの省略形を含める (たとえば、コンテナーが北アメリカに置く Contoso SharePoint サービスの場合、名前の可能なペアは Contoso-O365SP-NA-VaultA1 と Contoso-O365SP-NA-VaultA2 です)。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-241">Use a common prefix for key vaults, and include an abbreviation of the use and scope of the key vault and keys (e.g., for the Contoso SharePoint service where the vaults will be located in North America, a possible pair of names is Contoso-O365SP-NA-VaultA1 and Contoso-O365SP-NA-VaultA2.</span></span> <span data-ttu-id="dfeb2-242">コンテナー名は Azure 内でグローバルに一意の文字列なので、目的の名前が他の Azure ユーザーによって既に要求されている場合に、目的の名前のバリエーションを試す必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-242">Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers.</span></span> <span data-ttu-id="dfeb2-243">2017 年 7 月現在、コンテナー名は変更できないので、ベスト プラクティスは、セットアップの計画を作成し、2 番目のユーザーを使用して計画が正しく実行されていることを確認する方法です。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-243">As of July 2017 vault names cannot be changed, so a best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span>
> 
> <span data-ttu-id="dfeb2-244">可能であれば、ペアでない地域にコンテナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-244">If possible, create your vaults in non-paired regions.</span></span> <span data-ttu-id="dfeb2-245">ペアの Azure リージョンは、サービス 障害ドメイン間で高可用性を提供します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-245">Paired Azure regions provide high availability across service failure domains.</span></span> <span data-ttu-id="dfeb2-246">したがって、地域のペアは互いにバックアップ地域と考え合う可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-246">Therefore, regional pairs can be thought of as each other's backup region.</span></span> <span data-ttu-id="dfeb2-247">つまり、1 つの地域に配置された Azure リソースは、ペアリングされた地域を通じて自動的にフォールト トレランスを取得します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-247">This means that an Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region.</span></span> <span data-ttu-id="dfeb2-248">このため、地域がペアのデータ暗号化ポリシーで使用される 2 つのコンテナーに対して地域を選択すると、合計で 2 つの可用性の地域だけが使用されます。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-248">For this reason, choosing regions for two vaults used in a data encryption policy where the regions are paired means that only a total of two regions of availability are in use.</span></span> <span data-ttu-id="dfeb2-249">ほとんどの地域には 2 つの地域しか存在しないので、ペアリングされていない地域をまだ選択できません。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-249">Most geographies only have two regions, so it's not yet possible to select non-paired regions.</span></span> <span data-ttu-id="dfeb2-250">可能であれば、データ暗号化ポリシーで使用する 2 つのコンテナーに対して、ペアではない 2 つの地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-250">If possible, choose two non-paired regions for the two vaults used with a data encryption policy.</span></span> <span data-ttu-id="dfeb2-251">これは、合計で 4 つの可用性の領域から恩恵を受ける場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-251">This benefits from a total of four regions of availability.</span></span> <span data-ttu-id="dfeb2-252">詳細については、「ビジネス継続性と障害復旧 [(BCDR): 地域](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) ペアの現在の一覧については、Azure のペアリングされた地域」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-252">For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span>
  
### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="dfeb2-253">各キー コンテナーにアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="dfeb2-253">Assign permissions to each key vault</span></span>

<span data-ttu-id="dfeb2-254">キー コンテナーごとに、実装に応じて、顧客キーに対する 3 つの個別のアクセス許可セットを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-254">For each key vault, you will need to define three separate sets of permissions for Customer Key, depending on your implementation.</span></span> <span data-ttu-id="dfeb2-255">たとえば、次のそれぞれに対して 1 つのアクセス許可セットを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-255">For example, you will need to define one set of permissions for each of the following:</span></span>
  
- <span data-ttu-id="dfeb2-256">**組織のキー** コンテナーの毎日の管理を実行するキー コンテナー管理者。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-256">**Key vault administrators** that will perform day-to-day management of your key vault for your organization.</span></span> <span data-ttu-id="dfeb2-257">これらのタスクには、バックアップ、作成、取得、インポート、リスト、および復元が含まれます。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-257">These tasks include backup, create, get, import, list, and restore.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="dfeb2-258">キー コンテナー管理者に割り当てられた一連のアクセス許可には、キーを削除するアクセス許可は含められていない。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-258">The set of permissions assigned to key vault administrators does not include the permission to delete keys.</span></span> <span data-ttu-id="dfeb2-259">これは意図的で重要な方法です。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-259">This is intentional and an important practice.</span></span> <span data-ttu-id="dfeb2-260">暗号化キーを削除すると、データが完全に破棄されるので、通常は削除しません。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-260">Deleting encryption keys is not typically done, since doing so permanently destroys data.</span></span> <span data-ttu-id="dfeb2-261">ベスト プラクティスとして、この権限をキー コンテナー管理者に既定で付与することはお使いください。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-261">As a best practice, do not grant this permission to key vault administrators by default.</span></span> <span data-ttu-id="dfeb2-262">代わりに、主要なコンテナーの投稿者のためにこれを予約し、結果の明確な理解が得られると、短期的に管理者に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-262">Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span>
  
  <span data-ttu-id="dfeb2-263">組織内のユーザーにこれらのアクセス許可を割り当てるには、Azure PowerShell を使用して Azure サブスクリプションにログインします。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-263">To assign these permissions to a user in your organization, log in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="dfeb2-264">手順については [、「Azure PowerShell でサインインする」を参照してください](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-264">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

- <span data-ttu-id="dfeb2-265">必要なアクセスSet-AzKeyVaultAccessPolicy割り当てるには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-265">Run the Set-AzKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   <span data-ttu-id="dfeb2-266">例:</span><span class="sxs-lookup"><span data-stu-id="dfeb2-266">For example:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- <span data-ttu-id="dfeb2-267">Azure **Key Vault 自体** のアクセス許可を変更できる主要なコンテナーの投稿者。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-267">**Key vault contributors** that can change permissions on the Azure Key Vault itself.</span></span> <span data-ttu-id="dfeb2-268">従業員がチームを離れる、またはチームに参加する場合、またはキー コンテナー管理者がキーを削除または復元するためのアクセス許可を正当に必要とする非常にまれな状況では、これらのアクセス許可を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-268">You'll need to change these permissions as employees leave or join your team, or in the extremely rare situation that the key vault administrators legitimately need permission to delete or restore a key.</span></span> <span data-ttu-id="dfeb2-269">この一連の主要なコンテナー投稿者には、キー コンテナーに **対する共同作成者** の役割を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-269">This set of key vault contributors needs to be granted the **Contributor** role on your key vault.</span></span> <span data-ttu-id="dfeb2-270">このロールは、Azure リソース マネージャーを使用して割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-270">You can assign this role by using Azure Resource Manager.</span></span> <span data-ttu-id="dfeb2-271">詳細な手順については、「Role-Based Access Control を使用して Azure サブスクリプション リソースへのアクセス [を管理する」を参照してください](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure)。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-271">For detailed steps, see [Use Role-Based Access Control to manage access to your Azure subscription resources](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure).</span></span> <span data-ttu-id="dfeb2-272">サブスクリプションを作成する管理者は、暗黙的にこのアクセス権を持ち、他の管理者を投稿者の役割に割り当てる機能を持っています。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-272">The administrator who creates a subscription has this access implicitly, as well as the ability to assign other administrators to the Contributor role.</span></span>

- <span data-ttu-id="dfeb2-273">Exchange Online および Skype for Business で顧客キーを使用する場合は、Exchange Online と Skype for Business の代わりにキー コンテナーを使用するためのアクセス許可を Microsoft 365 に付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-273">If you intend to use Customer Key with Exchange Online and Skype for Business, you need to give permission to Microsoft 365 to use the key vault on behalf of Exchange Online and Skype for Business.</span></span> <span data-ttu-id="dfeb2-274">同様に、SharePoint Online と OneDrive for Business で顧客キーを使用する場合は、Microsoft 365 が SharePoint Online と OneDrive for Business の代わりにキー コンテナーを使用するためのアクセス許可を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-274">Likewise, if you intend to use Customer Key with SharePoint Online and OneDrive for Business, you need to add permission for the Microsoft 365 to use the key vault on behalf of SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="dfeb2-275">Microsoft 365 へのアクセス許可を付与するには、次の構文を使用して **Set-AzKeyVaultAccessPolicy** コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-275">To give permission to Microsoft 365, run the **Set-AzKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span> 

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   <span data-ttu-id="dfeb2-276">ここで、</span><span class="sxs-lookup"><span data-stu-id="dfeb2-276">Where:</span></span>

    - <span data-ttu-id="dfeb2-277">*コンテナー名* は、作成したキー コンテナーの名前です。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-277">*vault name* is the name of the key vault you created.</span></span>

    - <span data-ttu-id="dfeb2-278">Exchange Online と Skype for Business の場合は、Office  *365 appID* を `00000002-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="dfeb2-278">For Exchange Online and Skype for Business, replace  *Office 365 appID* with `00000002-0000-0ff1-ce00-000000000000`</span></span>

    - <span data-ttu-id="dfeb2-279">SharePoint Online、OneDrive for Business、Teams のファイルの場合は  *、365 appID* Office置き換える `00000003-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="dfeb2-279">For SharePoint Online, OneDrive for Business, and Teams files, replace  *Office 365 appID* with `00000003-0000-0ff1-ce00-000000000000`</span></span>

  <span data-ttu-id="dfeb2-280">例: Exchange Online と Skype for Business のアクセス許可の設定:</span><span class="sxs-lookup"><span data-stu-id="dfeb2-280">Example: Setting permissions for Exchange Online and Skype for Business:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  <span data-ttu-id="dfeb2-281">例: SharePoint Online、OneDrive for Business、および Teams ファイルのアクセス許可の設定:</span><span class="sxs-lookup"><span data-stu-id="dfeb2-281">Example: Setting permissions for SharePoint Online, OneDrive for Business, and Teams files:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a><span data-ttu-id="dfeb2-282">キー コンテナーで回復可能な削除を有効にして確認する</span><span class="sxs-lookup"><span data-stu-id="dfeb2-282">Enable and then confirm soft delete on your key vaults</span></span>

<span data-ttu-id="dfeb2-283">キーをすばやく回復できると、誤ってまたは悪意を持って削除されたキーが原因でサービスの停止が延長される可能性は低い可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-283">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys.</span></span> <span data-ttu-id="dfeb2-284">顧客キーでキーを使用する前に、この構成 (回復可能な削除と呼ばれる) を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-284">You need to enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key.</span></span> <span data-ttu-id="dfeb2-285">回復可能な削除を有効にすると、削除から 90 日以内にキーまたはコンテナーを復元できます。バックアップから復元する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-285">Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="dfeb2-286">キー コンテナーで回復可能な削除を有効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-286">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="dfeb2-287">Azure サブスクリプションにサインインするには、次のWindows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-287">Sign in to your Azure subscription with Windows PowerShell.</span></span> <span data-ttu-id="dfeb2-288">手順については [、「Azure PowerShell でサインインする」を参照してください](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-288">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="dfeb2-289">[Get-AzKeyVault コマンドレットを実行](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault)します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-289">Run the [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet.</span></span> <span data-ttu-id="dfeb2-290">この例では、 *コンテナー名* は、回復可能な削除を有効にするキー コンテナーの名前です。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-290">In this example, *vault name* is the name of the key vault for which you are enabling soft delete:</span></span>

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. <span data-ttu-id="dfeb2-291">**Get-AzKeyVault** コマンドレットを実行して、キー コンテナーの回復可能な削除が構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-291">Confirm soft delete is configured for the key vault by running the **Get-AzKeyVault** cmdlet.</span></span> <span data-ttu-id="dfeb2-292">回復可能な削除がキー コンテナーに対して適切に構成されている場合 _、Soft Delete Enabled_ プロパティは True の値を返 **します**。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-292">If soft delete is configured properly for the key vault, then the _Soft Delete Enabled_ property returns a value of **True**:</span></span>

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="dfeb2-293">キーを作成またはインポートして、各キー コンテナーにキーを追加する</span><span class="sxs-lookup"><span data-stu-id="dfeb2-293">Add a key to each key vault either by creating or importing a key</span></span>

<span data-ttu-id="dfeb2-294">Azure Key Vault にキーを追加するには 2 つの方法があります。Key Vault で直接キーを作成するか、キーをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-294">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key.</span></span> <span data-ttu-id="dfeb2-295">キーコンテナーで直接キーを作成する方法は複雑では少なく、キーをインポートすると、キーの生成方法を完全に制御できます。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-295">Creating a key directly in Key Vault is the less complicated method, while importing a key provides total control over how the key is generated.</span></span> <span data-ttu-id="dfeb2-296">RSA キーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-296">You need to use the RSA keys.</span></span> <span data-ttu-id="dfeb2-297">Azure Key Vault では、楕円曲線キーでの折り返しと折り返しの解除はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-297">Azure Key Vault doesn't support wrapping and unwrapping with elliptical curve keys.</span></span>
  
<span data-ttu-id="dfeb2-298">キー コンテナーにキーを直接作成するには、次のように [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-298">To create a key directly in your key vault, run the [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="dfeb2-299">ここで、</span><span class="sxs-lookup"><span data-stu-id="dfeb2-299">Where:</span></span>

- <span data-ttu-id="dfeb2-300">*コンテナー名* は、キーを作成するキー コンテナーの名前です。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-300">*vault name* is the name of the key vault in which you want to create the key.</span></span>

- <span data-ttu-id="dfeb2-301">*キー名* は、新しいキーを指定する名前です。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-301">*key name* is the name you want to give the new key.</span></span>

  > [!TIP]
  > <span data-ttu-id="dfeb2-302">キー コンテナーの場合は、上記と同様の名前付け規則を使用してキーに名前を付ける。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-302">Name keys using a similar naming convention as described above for key vaults.</span></span> <span data-ttu-id="dfeb2-303">これにより、キー名のみを表示するツールでは、文字列は自己記述型です。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-303">This way, in tools that show only the key name, the string is self-describing.</span></span>
  
<span data-ttu-id="dfeb2-304">キーを必ず _DESTINATION_ パラメーターの値として指定し、**それ** 以外の場合は **Software** を指定します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-304">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the _Destination_ parameter, otherwise, specify **Software**.</span></span>

<span data-ttu-id="dfeb2-305">例えば、</span><span class="sxs-lookup"><span data-stu-id="dfeb2-305">For example,</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="dfeb2-306">キー コンテナーにキーを直接インポートするには、nCipher nShield ハードウェア セキュリティ モジュールが必要です。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-306">To import a key directly into your key vault, you need to have a nCipher nShield Hardware Security Module.</span></span>
  
<span data-ttu-id="dfeb2-307">一部の組織では、キーの証明を確立するためにこの方法を選択し、次の方法も提供します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-307">Some organizations prefer this approach to establish the provenance of their keys, and then this method also provides the following:</span></span>
  
- <span data-ttu-id="dfeb2-308">インポートに使用するツールセットには、生成するキーの暗号化に使用されるキー交換キー (KEK) がエクスポート可能ではなく、nCipher によって製造された正規の THE</span><span class="sxs-lookup"><span data-stu-id="dfeb2-308">The toolset used for import includes attestation from nCipher that the Key Exchange Key (KEK) that is used to encrypt the key you generate is not exportable and is generated inside a genuine HSM that was manufactured by nCipher.</span></span>

- <span data-ttu-id="dfeb2-309">このツールセットには、nCipher によって製造された正規の VAULT で Azure Key Vault セキュリティワールドも生成されたという nCipher からの構成証明が含まれています。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-309">The toolset includes attestation from nCipher that the Azure Key Vault security world was also generated on a genuine HSM manufactured by nCipher.</span></span> <span data-ttu-id="dfeb2-310">この構成証明は、Microsoft が正規の nCipher ハードウェアも使用しているという証明です。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-310">This attestation proves to you that Microsoft is also using genuine nCipher hardware.</span></span>

<span data-ttu-id="dfeb2-311">セキュリティ グループに確認して、上記の構成証明が必要かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-311">Check with your security group to determine if the above attestations are required.</span></span> <span data-ttu-id="dfeb2-312">オンプレミスでキーを作成し、キー コンテナーにインポートする詳細な手順については [、「Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/)用に、VAULT で保護されたキーを生成して転送する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-312">For detailed steps to create a key on-premises and import it into your key vault, see [How to generate and transfer HSM-protected keys for Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/).</span></span> <span data-ttu-id="dfeb2-313">Azure の手順を使用して、各キー コンテナーにキーを作成します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-313">Use the Azure instructions to create a key in each key vault.</span></span>
  
### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="dfeb2-314">キーの回復レベルを確認する</span><span class="sxs-lookup"><span data-stu-id="dfeb2-314">Check the recovery level of your keys</span></span>

<span data-ttu-id="dfeb2-315">Microsoft 365 では、Azure Key Vault サブスクリプションが [キャンセルしない] に設定され、顧客キーで使用されるキーの削除 (回復可能) が有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-315">Microsoft 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled.</span></span> <span data-ttu-id="dfeb2-316">これを確認するには、キーの回復レベルを確認します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-316">You can confirm this by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="dfeb2-317">キーの回復レベルを確認するには、Azure PowerShell で次Get-AzKeyVaultKeyコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-317">To check the recovery level of a key, in Azure PowerShell, run the Get-AzKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

<span data-ttu-id="dfeb2-318">回復レベルのプロパティが **Recoverable+ProtectedSubscription** の値以外の値を返す場合は、この記事を確認し、サブスクリプションを取り消し不可リストに入れるすべての手順を実行し、各キー コンテナーで回復可能な削除が有効になっていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-318">If the _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, you will need to review this article and ensure that you have followed all of the steps to put the subscription on the Do Not Cancel list and that you have soft delete enabled on each of your key vaults.</span></span>
  
### <a name="back-up-azure-key-vault"></a><span data-ttu-id="dfeb2-319">Azure Key Vault をバックアップする</span><span class="sxs-lookup"><span data-stu-id="dfeb2-319">Back up Azure Key Vault</span></span>

<span data-ttu-id="dfeb2-320">キーの作成または変更の直後に、バックアップを実行し、バックアップのコピーをオンラインとオフラインの両方で保存します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-320">Immediately following creation or any change to a key, perform a backup and store copies of the backup, both online and offline.</span></span> <span data-ttu-id="dfeb2-321">オフライン コピーは、物理的な安全なストレージ機能や商用ストレージ機能など、どのネットワークにも接続できません。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-321">Offline copies should not be connected to any network, such as in a physical safe or commercial storage facility.</span></span> <span data-ttu-id="dfeb2-322">障害が発生した場合にアクセスできる場所に、バックアップの少なくとも 1 つのコピーを格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-322">At least one copy of the backup should be stored in a location that will be accessible in the event of a disaster.</span></span> <span data-ttu-id="dfeb2-323">バックアップ BLOB は、Key Vault キーが完全に破棄された場合や、他の方法で操作できない場合にキー マテリアルを復元する唯一の手段です。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-323">The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable.</span></span> <span data-ttu-id="dfeb2-324">Azure Key Vault の外部に存在し、Azure Key Vault にインポートされたキーは、顧客キーでキーを使用するために必要なメタデータが外部キーと一緒に存在しないので、バックアップとして修飾されません。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-324">Keys that are external to Azure Key Vault and were imported to Azure Key Vault do not qualify as a backup because the metadata necessary for Customer Key to use the key does not exist with the external key.</span></span> <span data-ttu-id="dfeb2-325">顧客キーを使用した復元操作には、Azure Key Vault から取得したバックアップのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-325">Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key.</span></span> <span data-ttu-id="dfeb2-326">したがって、キーをアップロードまたは作成したら、Azure Key Vault のバックアップを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-326">Therefore, it is essential that a backup of Azure Key Vault be made once a key is uploaded or created.</span></span>
  
<span data-ttu-id="dfeb2-327">Azure Key Vault キーのバックアップを作成するには、 [次のように Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-327">To create a backup of an Azure Key Vault key, run the [Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet as follows:</span></span>

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

<span data-ttu-id="dfeb2-328">出力ファイルでサフィックスが使用されている必要があります `.backup` 。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-328">Ensure that your output file uses the suffix `.backup`.</span></span>
  
<span data-ttu-id="dfeb2-329">このコマンドレットによって生成された出力ファイルは暗号化され、Azure Key Vault の外部では使用できません。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-329">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault.</span></span> <span data-ttu-id="dfeb2-330">バックアップは、バックアップの取得元の Azure サブスクリプションにのみ復元できます。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-330">The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
> [!TIP]
> <span data-ttu-id="dfeb2-331">出力ファイルの場合は、コンテナー名とキー名の組み合わせを選択します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-331">For the output file, choose a combination of your vault name and key name.</span></span> <span data-ttu-id="dfeb2-332">これにより、ファイル名が自己記述的に記述されます。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-332">This will make the file name self-describing.</span></span> <span data-ttu-id="dfeb2-333">また、バックアップ ファイル名が衝突しないことです。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-333">It will also ensure that backup file names do not collide.</span></span>
  
<span data-ttu-id="dfeb2-334">例:</span><span class="sxs-lookup"><span data-stu-id="dfeb2-334">For example:</span></span>
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="dfeb2-335">Azure Key Vault の構成設定を検証する</span><span class="sxs-lookup"><span data-stu-id="dfeb2-335">Validate Azure Key Vault configuration settings</span></span>

<span data-ttu-id="dfeb2-336">DEP でキーを使用する前に検証を実行する方法はオプションですが、強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-336">Performing validation before using keys in a DEP is optional, but highly recommended.</span></span> <span data-ttu-id="dfeb2-337">特に、このトピックで説明する手順以外のキーとコンテナーをセットアップする手順を使用する場合は、顧客キーを構成する前に Azure Key Vault リソースの正常性を検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-337">In particular, if you use steps to set up your keys and vaults other than the ones described in this topic, you should validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="dfeb2-338">キーで get、wrapKey、および unwrapKey 操作が有効になっているか確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-338">To verify that your keys have get, wrapKey, and unwrapKey operations enabled:</span></span>
  
<span data-ttu-id="dfeb2-339">[Get-AzKeyVault コマンドレットを次](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault)のように実行します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-339">Run the [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="dfeb2-340">出力で、アクセス ポリシーと、Exchange Online ID (GUID) または SharePoint Online ID (GUID) を必要に応じて探します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-340">In the output, look for the Access Policy and for the Exchange Online identity (GUID) or the SharePoint Online identity (GUID) as appropriate.</span></span> <span data-ttu-id="dfeb2-341">上記の 3 つのアクセス許可はすべて、キーへのアクセス許可の下に表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-341">All three of the above permissions must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="dfeb2-342">アクセス ポリシーの構成が正しくない場合は、次Set-AzKeyVaultAccessPolicyコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-342">If the access policy configuration is incorrect, run the Set-AzKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

<span data-ttu-id="dfeb2-343">たとえば、Exchange Online および Skype for Business の場合:</span><span class="sxs-lookup"><span data-stu-id="dfeb2-343">For example, for Exchange Online and Skype for Business:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="dfeb2-344">たとえば、SharePoint Online および OneDrive for Business の場合:</span><span class="sxs-lookup"><span data-stu-id="dfeb2-344">For example, for SharePoint Online and OneDrive for Business:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="dfeb2-345">キーに有効期限が設定されていないことを確認するには、次のように [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-345">To verify that an expiration date is not set for your keys run the [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

<span data-ttu-id="dfeb2-346">期限切れのキーを顧客キーで使用することはできません。また、期限切れのキーを使用して試行された操作は失敗し、サービスが停止する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-346">An expired key cannot be used by Customer Key and operations attempted with an expired key will fail, and possibly result in a service outage.</span></span> <span data-ttu-id="dfeb2-347">顧客キーで使用するキーには有効期限日を設定することを強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-347">We strongly recommend that keys used with Customer Key do not have an expiration date.</span></span> <span data-ttu-id="dfeb2-348">有効期限を設定すると削除できませんが、別の日付に変更できます。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-348">An expiration date, once set, cannot be removed, but can be changed to a different date.</span></span> <span data-ttu-id="dfeb2-349">有効期限が設定されているキーを使用する必要がある場合は、有効期限の値を 9999 年 12 月 31 日に変更します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-349">If a key must be used that has an expiration date set, change the expiration value to 12/31/9999.</span></span> <span data-ttu-id="dfeb2-350">有効期限が 9999 年 12 月 31 日以外の日付に設定されているキーは、Microsoft 365 検証に合格しません。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-350">Keys with an expiration date set to a date other than 12/31/9999 will not pass Microsoft 365 validation.</span></span>
  
<span data-ttu-id="dfeb2-351">12/31/9999 以外の値に設定されている有効期限を変更するには [、Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) コマンドレットを次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-351">To change an expiration date that has been set to any value other than 12/31/9999, run the [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> <span data-ttu-id="dfeb2-352">顧客キーで使用する暗号化キーに有効期限を設定しません。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-352">Don't set expiration dates on encryption keys you use with Customer Key.</span></span>
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="dfeb2-353">各 Azure Key Vault キーの URI を取得する</span><span class="sxs-lookup"><span data-stu-id="dfeb2-353">Obtain the URI for each Azure Key Vault key</span></span>

<span data-ttu-id="dfeb2-354">Azure のすべての手順を完了してキー コンテナーをセットアップし、キーを追加したら、次のコマンドを実行して各キー コンテナーのキーの URI を取得します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-354">Once you've completed all the steps in Azure to set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault.</span></span> <span data-ttu-id="dfeb2-355">これらの URI は、後で各 DEP を作成して割り当てる際に使用する必要があります。そのため、この情報は安全な場所に保存してください。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-355">You will need to use these URIs when you create and assign each DEP later, so save this information in a safe place.</span></span> <span data-ttu-id="dfeb2-356">このコマンドは、キー コンテナーごとに 1 回だけ実行してください。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-356">Remember to run this command once for each key vault.</span></span>
  
<span data-ttu-id="dfeb2-357">Azure PowerShell の場合:</span><span class="sxs-lookup"><span data-stu-id="dfeb2-357">In Azure PowerShell:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="dfeb2-358">Office 365: Exchange Online と Skype for Business の顧客キーの設定</span><span class="sxs-lookup"><span data-stu-id="dfeb2-358">Office 365: Setting up Customer Key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="dfeb2-359">始める前に、Azure Key Vault のセットアップに必要なタスクを完了してください。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-359">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="dfeb2-360">詳細 [については、「顧客キーの Azure Key Vault と Microsoft FastTrack のタスクを完了する」](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-360">See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) for information.</span></span>
  
<span data-ttu-id="dfeb2-361">Exchange Online と Skype for Business のカスタマー キーをセットアップするには、Exchange Online にリモートで接続して、次の手順を実行する必要Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-361">To set up Customer Key for Exchange Online and Skype for Business, you will need to perform these steps by remotely connecting to Exchange Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a><span data-ttu-id="dfeb2-362">Exchange Online および Skype for Business で使用するデータ暗号化ポリシー (DEP) を作成する</span><span class="sxs-lookup"><span data-stu-id="dfeb2-362">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>

<span data-ttu-id="dfeb2-363">DEP は、Azure Key Vault に格納されている一連のキーに関連付けられる。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-363">A DEP is associated with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="dfeb2-364">DEP を Microsoft 365 のメールボックスに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-364">You assign a DEP to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="dfeb2-365">その後、Microsoft 365 はポリシーで識別されたキーを使用してメールボックスを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-365">Microsoft 365 will then use the keys identified in the policy to encrypt the mailbox.</span></span> <span data-ttu-id="dfeb2-366">DEP を作成するには、前に取得したキー コンテナー URI が必要です。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-366">To create the DEP, you need the Key Vault URIs you obtained earlier.</span></span> <span data-ttu-id="dfeb2-367">手順 [については、「Azure Key Vault キーごとに URI](#obtain-the-uri-for-each-azure-key-vault-key) を取得する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-367">See [Obtain the URI for each Azure Key Vault key](#obtain-the-uri-for-each-azure-key-vault-key) for instructions.</span></span>
  
<span data-ttu-id="dfeb2-368">覚えておいてください。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-368">Remember!</span></span> <span data-ttu-id="dfeb2-369">DEP を作成する場合は、2 つの異なる Azure Key Vault に存在する 2 つのキーを指定します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-369">When you create a DEP, you specify two keys that reside in two different Azure Key Vaults.</span></span> <span data-ttu-id="dfeb2-370">地理的冗長性を確保するために、これらのキーが 2 つの別々の Azure リージョンに含めらたものにします。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-370">Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="dfeb2-371">DEP を作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-371">To create the DEP, follow these steps:</span></span>
  
1. <span data-ttu-id="dfeb2-372">ローカル コンピューターで、組織のグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用して、次のウィンドウで [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) Windows PowerShellします。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-372">On your local computer, using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="dfeb2-373">DEP を作成するには、次のコマンドをNew-DataEncryptionPolicyコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-373">To create a DEP, use the New-DataEncryptionPolicy cmdlet by typing the following command.</span></span>

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   <span data-ttu-id="dfeb2-374">ここで、</span><span class="sxs-lookup"><span data-stu-id="dfeb2-374">Where:</span></span>

   - <span data-ttu-id="dfeb2-375">*PolicyName* は、ポリシーに使用する名前です。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-375">*PolicyName* is the name you want to use for the policy.</span></span> <span data-ttu-id="dfeb2-376">名前にスペースを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-376">Names cannot contain spaces.</span></span> <span data-ttu-id="dfeb2-377">たとえば、USA_mailboxes。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-377">For example, USA_mailboxes.</span></span>

   - <span data-ttu-id="dfeb2-378">*ポリシーの* 説明は、ポリシーの内容を思い出すのに役立つ、ポリシーのユーザー フレンドリーな説明です。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-378">*Policy Description* is a user friendly description of the policy that will help you remember what the policy is for.</span></span> <span data-ttu-id="dfeb2-379">説明にはスペースを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-379">You can include spaces in the description.</span></span> <span data-ttu-id="dfeb2-380">たとえば、"米国とその地域のメールボックスのルート キー" などです。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-380">For example, "Root key for mailboxes in USA and its territories".</span></span>

   - <span data-ttu-id="dfeb2-381">*KeyVaultURI1* は、ポリシーの最初のキーの URI です。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-381">*KeyVaultURI1* is the URI for the first key in the policy.</span></span> <span data-ttu-id="dfeb2-382">たとえば、<https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01> などです。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-382">For example, <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.</span></span>

   - <span data-ttu-id="dfeb2-383">*KeyVaultURI2* は、ポリシー内の 2 番目のキーの URI です。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-383">*KeyVaultURI2* is the URI for the second key in the policy.</span></span> <span data-ttu-id="dfeb2-384">たとえば、<https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02> などです。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-384">For example, <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>.</span></span> <span data-ttu-id="dfeb2-385">2 つの URI はコンマとスペースで区切ります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-385">Separate the two URIs by a comma and a space.</span></span>

   <span data-ttu-id="dfeb2-386">例:</span><span class="sxs-lookup"><span data-stu-id="dfeb2-386">Example:</span></span>
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

<span data-ttu-id="dfeb2-387">構文およびパラメーターの詳細については [、「New-DataEncryptionPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/new-data-encryptionpolicy)。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-387">For detailed syntax and parameter information, see [New-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/new-data-encryptionpolicy).</span></span>

### <a name="assign-a-dep-to-a-mailbox"></a><span data-ttu-id="dfeb2-388">メールボックスに DEP を割り当てる</span><span class="sxs-lookup"><span data-stu-id="dfeb2-388">Assign a DEP to a mailbox</span></span>

<span data-ttu-id="dfeb2-389">メールボックスに DEP を割り当てるには、次のコマンドレットSet-Mailboxします。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-389">Assign the DEP to a mailbox by using the Set-Mailbox cmdlet.</span></span> <span data-ttu-id="dfeb2-390">ポリシーを割り当てると、Microsoft 365 は DEP で指定されたキーを使用してメールボックスを暗号化できます。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-390">Once you assign the policy, Microsoft 365 can encrypt the mailbox with the key designated in the DEP.</span></span>
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="dfeb2-391">*MailboxIdParameter はメールボックス* を指定します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-391">Where *MailboxIdParameter* specifies a mailbox.</span></span> <span data-ttu-id="dfeb2-392">このコマンドレットの詳細については [、「Set-Mailbox-Mailbox 」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-392">For more information about the Set-Mailbox cmdlet, see [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox).</span></span>

<span data-ttu-id="dfeb2-393">ハイブリッドのモダン認証を使用する [iOS](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)および Android 用の Outlook を使用するオンプレミスのメールボックスの場合、Exchange Online テナントに同期されるオンプレミスのメールボックス データは、Set-MailUser コマンドレットを使用して DEP を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-393">For [on-premises mailboxes using Outlook for iOS and Android with hybrid Modern Authentication](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth), the on-premises mailbox data that is synchronized into your Exchange Online tenant can have DEP assigned using the Set-MailUser cmdlet.</span></span>

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="dfeb2-394">*MailUserIdParameter は、* メール ユーザー (メールが有効なユーザーとも呼ばれる) を指定します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-394">Where *MailUserIdParameter* specifies a mail user (also known as a mail-enabled user).</span></span> <span data-ttu-id="dfeb2-395">このコマンドレットの詳細についてはSet-MailUser [Set-MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-395">For more information about the Set-MailUser cmdlet, see [Set-MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser).</span></span>
  
### <a name="validate-mailbox-encryption"></a><span data-ttu-id="dfeb2-396">メールボックスの暗号化を検証する</span><span class="sxs-lookup"><span data-stu-id="dfeb2-396">Validate mailbox encryption</span></span>

<span data-ttu-id="dfeb2-397">メールボックスの暗号化には時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-397">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="dfeb2-398">ポリシーの割り当てを初めて行う場合は、サービスがメールボックスを暗号化する前に、メールボックスをあるデータベースから別のデータベースに完全に移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-398">For first time policy assignment, the mailbox must also completely move from one database to another before the service can encrypt the mailbox.</span></span> <span data-ttu-id="dfeb2-399">DEP を変更した後、または初めて DEP をメールボックスに割り当てる場合は、暗号化の検証を試みる前に 72 時間待機することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-399">We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="dfeb2-400">メールボックスがGet-MailboxStatisticsを確認するには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-400">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="dfeb2-401">IsEncrypted プロパティは、メールボックスが暗号化されている場合は **true、** メールボックスが暗号化されていない場合は **値 false** を返します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-401">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span>

<span data-ttu-id="dfeb2-402">メールボックスの移動が完了する時間は、初めて DEP を割り当てるメールボックスの数とメールボックスのサイズによって異なります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-402">The time to complete mailbox moves depends on the number of mailboxes to which you assign a DEP for the first time, as well as the size of the mailboxes.</span></span> <span data-ttu-id="dfeb2-403">DEP を割り当てた 1 週間後にメールボックスが暗号化されていない場合は、Microsoft にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-403">If the mailboxes have not been encrypted after a week from the time you assigned the DEP, contact Microsoft.</span></span>

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="dfeb2-404">Office 365: SharePoint Online、OneDrive for Business、および Teams ファイルの顧客キーの設定</span><span class="sxs-lookup"><span data-stu-id="dfeb2-404">Office 365: Setting up Customer Key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="dfeb2-405">始める前に、Azure Key Vault のセットアップに必要なタスクを完了してください。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-405">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="dfeb2-406">詳細 [については、「顧客キーの Azure Key Vault と Microsoft FastTrack のタスクを完了する」](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-406">See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) for information.</span></span>
  
<span data-ttu-id="dfeb2-407">SharePoint Online、OneDrive for Business、および Teams ファイルのカスタマー キーをセットアップするには、SharePoint Online にリモートで Windows PowerShell に接続して、これらの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-407">To set up Customer Key for SharePoint Online, OneDrive for Business, and Teams files you will need to perform these steps by remotely connecting to SharePoint Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a><span data-ttu-id="dfeb2-408">SharePoint Online および OneDrive for Business 地域ごとにデータ暗号化ポリシー (DEP) を作成する</span><span class="sxs-lookup"><span data-stu-id="dfeb2-408">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>

<span data-ttu-id="dfeb2-409">DEP を Azure Key Vault に格納されているキーのセットに関連付ける。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-409">You associate a DEP with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="dfeb2-410">DEP は、地域とも呼ばれる 1 つの地理的な場所のすべてのデータに適用します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-410">You apply a DEP to all of your data in one geographic location, also called a geo.</span></span> <span data-ttu-id="dfeb2-411">Office 365 の複数地域機能を使用する場合、geo ごとに異なるキーを使用する機能を持つ DEP を geo ごとに 1 つ作成できます。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-411">If you use the multi-geo feature of Office 365, you can create one DEP per geo with the capability to use different keys per geo.</span></span> <span data-ttu-id="dfeb2-412">複数地域を使用していない場合は、SharePoint Online、OneDrive for Business、および Teams ファイルで使用する DEP を組織内に 1 つ作成できます。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-412">If you are not using multi-geo, you can create one DEP in your organization for use with SharePoint Online, OneDrive for Business, and Teams files.</span></span> <span data-ttu-id="dfeb2-413">Microsoft 365 は、DEP で識別されたキーを使用して、その geo 内のデータを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-413">Microsoft 365 uses the keys identified in the DEP to encrypt your data in that geo.</span></span> <span data-ttu-id="dfeb2-414">DEP を作成するには、前に取得したキー コンテナー URI が必要です。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-414">To create the DEP, you need the Key Vault URIs you obtained earlier.</span></span> <span data-ttu-id="dfeb2-415">手順 [については、「Azure Key Vault キーごとに URI](#obtain-the-uri-for-each-azure-key-vault-key) を取得する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-415">See [Obtain the URI for each Azure Key Vault key](#obtain-the-uri-for-each-azure-key-vault-key) for instructions.</span></span>
  
<span data-ttu-id="dfeb2-416">覚えておいてください。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-416">Remember!</span></span> <span data-ttu-id="dfeb2-417">DEP を作成する場合は、2 つの異なる Azure Key Vault に存在する 2 つのキーを指定します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-417">When you create a DEP, you specify two keys that reside in two different Azure Key Vaults.</span></span> <span data-ttu-id="dfeb2-418">地理的冗長性を確保するために、これらのキーが 2 つの別々の Azure リージョンに含めらたものにします。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-418">Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="dfeb2-419">DEP を作成するには、次のコマンドを使用して SharePoint Online にリモートWindows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-419">To create a DEP, you need to remotely connect to SharePoint Online by using Windows PowerShell.</span></span>
  
1. <span data-ttu-id="dfeb2-420">ローカル コンピューターで、組織内のグローバル管理者のアクセス許可を持つ仕事または学校のアカウントを使用して [、SharePoint Online PowerShell に接続します](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps&preserve-view=true)。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-420">On your local computer, using a work or school account that has global administrator permissions in your organization, [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps&preserve-view=true).</span></span>

2. <span data-ttu-id="dfeb2-421">Microsoft SharePoint Online 管理シェルで、次のようにRegister-SPODataEncryptionPolicyコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-421">In the Microsoft SharePoint Online Management Shell, run the Register-SPODataEncryptionPolicy cmdlet as follows:</span></span>

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <adminSiteCollectionURL> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   <span data-ttu-id="dfeb2-422">例:</span><span class="sxs-lookup"><span data-stu-id="dfeb2-422">Example:</span></span>
  
   ```powershell
   Register-SPODataEncryptionPolicy -Identity https://contoso.sharepoint.com -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a’
   ```

   <span data-ttu-id="dfeb2-423">DEP を登録すると、geo 内のデータに対して暗号化が開始されます。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-423">When you register the DEP, encryption begins on the data in the geo.</span></span> <span data-ttu-id="dfeb2-424">これには時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-424">This can take some time.</span></span> <span data-ttu-id="dfeb2-425">このパラメーターの使用の詳細については [、「Register-SPODataEncryptionPolicy」を参照してください](https://docs.microsoft.com/powershell/module/sharepoint-online/register-spodataencryptionpolicy?view=sharepoint-ps&preserve-view=true)。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-425">For more information on using this parameter, see [Register-SPODataEncryptionPolicy](https://docs.microsoft.com/powershell/module/sharepoint-online/register-spodataencryptionpolicy?view=sharepoint-ps&preserve-view=true).</span></span>

### <a name="validate-file-encryption"></a><span data-ttu-id="dfeb2-426">ファイルの暗号化を検証する</span><span class="sxs-lookup"><span data-stu-id="dfeb2-426">Validate file encryption</span></span>

 <span data-ttu-id="dfeb2-427">SharePoint Online、OneDrive for Business、および Teams ファイルの暗号化を検証するには [、SharePoint Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)に接続し、Get-SPODataEncryptionPolicy コマンドレットを使用してテナントの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-427">To validate encryption of SharePoint Online, OneDrive for Business, and Teams files, [connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell), and then use the Get-SPODataEncryptionPolicy cmdlet to check the status of your tenant.</span></span> <span data-ttu-id="dfeb2-428">State _プロパティ_ は、顧客キーの暗号化が有効で、すべてのサイトのすべてのファイルが暗号化されている場合に、登録された値を返します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-428">The _State_ property returns a value of **registered** if Customer Key encryption is enabled and all files in all sites have been encrypted.</span></span> <span data-ttu-id="dfeb2-429">暗号化がまだ進行中の場合、このコマンドレットは完了したサイトの割合に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="dfeb2-429">If encryption is still in progress, this cmdlet provides information on what percentage of sites is complete.</span></span>

## <a name="related-articles"></a><span data-ttu-id="dfeb2-430">関連記事</span><span class="sxs-lookup"><span data-stu-id="dfeb2-430">Related articles</span></span>

- [<span data-ttu-id="dfeb2-431">カスタマー キーによるサービスの暗号化</span><span class="sxs-lookup"><span data-stu-id="dfeb2-431">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="dfeb2-432">顧客キーの管理</span><span class="sxs-lookup"><span data-stu-id="dfeb2-432">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="dfeb2-433">カスタマー キーまたは可用性キーをローリングまたはローテーションする</span><span class="sxs-lookup"><span data-stu-id="dfeb2-433">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="dfeb2-434">可用性キーの詳細</span><span class="sxs-lookup"><span data-stu-id="dfeb2-434">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="dfeb2-435">サービスの暗号化</span><span class="sxs-lookup"><span data-stu-id="dfeb2-435">Service Encryption</span></span>](office-365-service-encryption.md)
