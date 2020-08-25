---
title: 顧客キーを設定する
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
description: Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business、および Teams の各ファイルに対して Microsoft 365 の顧客キーを設定する方法について説明します。
ms.openlocfilehash: 0743b4339dae8e70960293f51a7869dc61fea606
ms.sourcegitcommit: 22dab0f7604cc057a062698005ff901d40771692
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "46868892"
---
# <a name="set-up-customer-key"></a><span data-ttu-id="89adf-103">顧客キーを設定する</span><span class="sxs-lookup"><span data-stu-id="89adf-103">Set up Customer Key</span></span>

<span data-ttu-id="89adf-104">顧客キーを使用して、組織の暗号化キーを制御し、microsoft 365 を使用して Microsoft のデータセンターで保存されているデータを暗号化するように構成します。</span><span class="sxs-lookup"><span data-stu-id="89adf-104">With Customer Key, you control your organization's encryption keys and then configure Microsoft 365 to use them to encrypt your data at rest in Microsoft's data centers.</span></span> <span data-ttu-id="89adf-105">言い換えると、顧客キーを使用すると、そのキーを使用して、ユーザーに属する暗号化の層を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="89adf-105">In other words, Customer Key allows customers to add a layer of encryption that belongs to them, with their keys.</span></span> <span data-ttu-id="89adf-106">保存データには、メールボックスに保存されている Exchange Online および Skype for Business からのデータと、SharePoint Online および OneDrive for Business に保存されているファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="89adf-106">Data at rest includes data from Exchange Online and Skype for Business that is stored in mailboxes and files that are stored in SharePoint Online and OneDrive for Business.</span></span>

<span data-ttu-id="89adf-107">Office 365 の顧客キーを使用するには、事前に Azure をセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="89adf-107">You must set up Azure before you can use Customer Key for Office 365.</span></span> <span data-ttu-id="89adf-108">このトピックでは、必要な Azure リソースを作成して構成するために従う必要のある手順について説明し、Office 365 で顧客キーを設定する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="89adf-108">This topic describes the steps you need to follow to create and configure the required Azure resources and then provides the steps for setting up Customer Key in Office 365.</span></span> <span data-ttu-id="89adf-109">Azure のセットアップを完了した後、組織内のメールボックスとファイルに割り当てるポリシーとそのためのキーを決定します。</span><span class="sxs-lookup"><span data-stu-id="89adf-109">After you have completed Azure setup, you determine which policy, and therefore, which keys, to assign to mailboxes and files in your organization.</span></span> <span data-ttu-id="89adf-110">ポリシーを割り当てていないメールボックスとファイルでは、Microsoft によって制御および管理されている暗号化ポリシーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="89adf-110">Mailboxes and files for which you don't assign a policy will use encryption policies that are controlled and managed by Microsoft.</span></span> <span data-ttu-id="89adf-111">顧客キーの詳細、または一般的な概要については、「 [Office 2010 での顧客キーを使用したサービスの暗号化 365](customer-key-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89adf-111">For more information about Customer Key, or for a general overview, see [Service encryption with Customer Key in Office 365](customer-key-overview.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="89adf-112">このトピックのベストプラクティスに従うことを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="89adf-112">We strongly recommend that you follow the best practices in this topic.</span></span> <span data-ttu-id="89adf-113">これらは、 **TIP** と **重要**と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="89adf-113">These are called out as **TIP** and **IMPORTANT**.</span></span> <span data-ttu-id="89adf-114">顧客キーを使用すると、組織全体でスコープが大きくなる可能性があるルート暗号化キーを制御できます。</span><span class="sxs-lookup"><span data-stu-id="89adf-114">Customer Key gives you control over root encryption keys whose scope can be as large as your entire organization.</span></span> <span data-ttu-id="89adf-115">このため、これらのキーに誤りが発生しても、サービスが中断したり、データが irrevocable 失われたりする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="89adf-115">This means that mistakes made with these keys can have a broad impact and may result in service interruptions or irrevocable loss of your data.</span></span>
  
## <a name="before-you-set-up-customer-key"></a><span data-ttu-id="89adf-116">顧客キーを設定する前に</span><span class="sxs-lookup"><span data-stu-id="89adf-116">Before you set up Customer Key</span></span>

<span data-ttu-id="89adf-117">開始する前に、組織に適したライセンスを持っていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="89adf-117">Before you get started, ensure that you have the appropriate licensing for your organization.</span></span> <span data-ttu-id="89adf-118">Microsoft 365 の顧客キーは、Office 365 E5 または Advanced コンプライアンス SKU で提供されます。</span><span class="sxs-lookup"><span data-stu-id="89adf-118">Customer Key in Microsoft 365 is offered in Office 365 E5 or the Advanced Compliance SKU.</span></span> <span data-ttu-id="89adf-119">このトピックの概念と手順を理解するには、「 [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/) 」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="89adf-119">To understand the concepts and procedures in this topic, review the [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/) documentation.</span></span> <span data-ttu-id="89adf-120">また、「 [テナント](https://docs.microsoft.com/previous-versions/azure/azure-services/jj573650(v=azure.100))」など、Azure で使用される用語について理解しておいてください。</span><span class="sxs-lookup"><span data-stu-id="89adf-120">Also, become familiar with the terms used in Azure, for example, [tenant](https://docs.microsoft.com/previous-versions/azure/azure-services/jj573650(v=azure.100)).</span></span>

<span data-ttu-id="89adf-121">FastTrack は、顧客キーの登録に使用する必要なテナントおよびサービス構成情報を収集するためにのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="89adf-121">FastTrack is only used to collect the required tenant and service configuration information used to register for Customer Key.</span></span> <span data-ttu-id="89adf-122">カスタマーキー提供は FastTrack を通じて公開されるため、パートナーは同じ方法で必要な情報を送信することができます。</span><span class="sxs-lookup"><span data-stu-id="89adf-122">The Customer Key Offers are published via FastTrack so that it is convenient for you and our partners to submit the required information using the same method.</span></span> <span data-ttu-id="89adf-123">FastTrack を使用すると、提供されているデータのアーカイブも容易になります。</span><span class="sxs-lookup"><span data-stu-id="89adf-123">FastTrack also makes it easy to archive the data that you provide in the Offer.</span></span>
  
<span data-ttu-id="89adf-124">ドキュメント以外のサポートが必要な場合は、Microsoft コンサルティングサービス (MCS)、プレミアフィールドエンジニアリング (PFE)、または Microsoft パートナーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="89adf-124">If you need additional support beyond the documentation, contact Microsoft Consulting Services (MCS), Premier Field Engineering (PFE), or a Microsoft partner for assistance.</span></span> <span data-ttu-id="89adf-125">ドキュメントなど、顧客キーに関するフィードバックを提供するために、アイデア、提案、および展望を customerkeyfeedback@microsoft.com に送信します。</span><span class="sxs-lookup"><span data-stu-id="89adf-125">To provide feedback on Customer Key, including the documentation, send your ideas, suggestions, and perspectives to customerkeyfeedback@microsoft.com.</span></span>
  
## <a name="overview-of-steps-to-set-up-customer-key"></a><span data-ttu-id="89adf-126">顧客キーを設定する手順の概要</span><span class="sxs-lookup"><span data-stu-id="89adf-126">Overview of steps to set up Customer Key</span></span>

<span data-ttu-id="89adf-127">顧客キーを設定するには、リストされている順序でこれらのタスクを完了します。</span><span class="sxs-lookup"><span data-stu-id="89adf-127">To set up Customer Key, complete these tasks in the listed order.</span></span> <span data-ttu-id="89adf-128">この記事の残りの部分では、各タスクの詳細な手順を説明します。または、プロセスの各手順に関する詳細情報へのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="89adf-128">The rest of this article provides detailed instructions for each task, or links out to more information for each step in the process.</span></span>
  
<span data-ttu-id="89adf-129">**Azure と Microsoft FastTrack の場合:**</span><span class="sxs-lookup"><span data-stu-id="89adf-129">**In Azure and Microsoft FastTrack:**</span></span>
  
<span data-ttu-id="89adf-130">これらのタスクのほとんどは、Azure PowerShell にリモートで接続することで完了します。</span><span class="sxs-lookup"><span data-stu-id="89adf-130">You will complete most of these tasks by remotely connecting to Azure PowerShell.</span></span> <span data-ttu-id="89adf-131">最良の結果を得るには、Azure PowerShell のバージョン4.4.0 以降を使用します。</span><span class="sxs-lookup"><span data-stu-id="89adf-131">For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>
  
- [<span data-ttu-id="89adf-132">2つの新しい Azure サブスクリプションを作成する</span><span class="sxs-lookup"><span data-stu-id="89adf-132">Create two new Azure subscriptions</span></span>](#create-two-new-azure-subscriptions)

- [<span data-ttu-id="89adf-133">Azure サブスクリプションを登録して必須の保持期間を使用する</span><span class="sxs-lookup"><span data-stu-id="89adf-133">Register Azure subscriptions to use a mandatory retention period</span></span>](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  <span data-ttu-id="89adf-134">登録には 1 ~ 5 営業日かかります。</span><span class="sxs-lookup"><span data-stu-id="89adf-134">Registration can take from one to five business days.</span></span>

- [<span data-ttu-id="89adf-135">Office 365 の顧客キーを有効にするための要求を送信する</span><span class="sxs-lookup"><span data-stu-id="89adf-135">Submit a request to activate Customer Key for Office 365</span></span>](#submit-a-request-to-activate-customer-key-for-office-365)

<span data-ttu-id="89adf-136">2つの新しい Azure サブスクリプションを作成したら、Microsoft FastTrack ポータルでホストされている web フォームに入力して、適切な顧客キー提示要求を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89adf-136">Once you've created the two new Azure subscriptions, you'll need to submit the appropriate Customer Key offer request by completing a web form that is hosted in the Microsoft FastTrack portal.</span></span> <span data-ttu-id="89adf-137">**FastTrack チームは、顧客キーについてサポートを提供していません。Office では、FastTrack ポータルを使用**してフォームを送信することができます。また、顧客キーの関連する提供を追跡するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="89adf-137">**The FastTrack team doesn't provide assistance with Customer Key. Office simply uses the FastTrack portal to allow you to submit the form and to help us track the relevant offers for Customer Key**.</span></span>

- [<span data-ttu-id="89adf-138">各サブスクリプションにプレミアム Azure キーコンテナーを作成する</span><span class="sxs-lookup"><span data-stu-id="89adf-138">Create a premium Azure Key Vault in each subscription</span></span>](#create-a-premium-azure-key-vault-in-each-subscription)

- [<span data-ttu-id="89adf-139">各キーコンテナーにアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="89adf-139">Assign permissions to each key vault</span></span>](#assign-permissions-to-each-key-vault)

- [<span data-ttu-id="89adf-140">キーコンテナーでの論理削除を有効にして、確認します。</span><span class="sxs-lookup"><span data-stu-id="89adf-140">Enable and then confirm soft delete on your key vaults</span></span>](#enable-and-then-confirm-soft-delete-on-your-key-vaults)

- [<span data-ttu-id="89adf-141">キーを作成またはインポートすることによって、各キーコンテナーにキーを追加する</span><span class="sxs-lookup"><span data-stu-id="89adf-141">Add a key to each key vault either by creating or importing a key</span></span>](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [<span data-ttu-id="89adf-142">キーの回復レベルを確認する</span><span class="sxs-lookup"><span data-stu-id="89adf-142">Check the recovery level of your keys</span></span>](#check-the-recovery-level-of-your-keys)

- [<span data-ttu-id="89adf-143">Azure Key Vault をバックアップする</span><span class="sxs-lookup"><span data-stu-id="89adf-143">Back up Azure Key Vault</span></span>](#back-up-azure-key-vault)

- [<span data-ttu-id="89adf-144">Azure Key Vault 構成設定を検証する</span><span class="sxs-lookup"><span data-stu-id="89adf-144">Validate Azure Key Vault configuration settings</span></span>](#validate-azure-key-vault-configuration-settings)

- [<span data-ttu-id="89adf-145">各 Azure Key Vault キーの URI を取得する</span><span class="sxs-lookup"><span data-stu-id="89adf-145">Obtain the URI for each Azure Key Vault key</span></span>](#obtain-the-uri-for-each-azure-key-vault-key)

<span data-ttu-id="89adf-146">**Office 365:**</span><span class="sxs-lookup"><span data-stu-id="89adf-146">**In Office 365:**</span></span>
  
<span data-ttu-id="89adf-147">Exchange Online と Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="89adf-147">Exchange Online and Skype for Business:</span></span>
  
- [<span data-ttu-id="89adf-148">Exchange Online と Skype for Business で使用するデータ暗号化ポリシー (DEP) を作成する</span><span class="sxs-lookup"><span data-stu-id="89adf-148">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>](#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)

- [<span data-ttu-id="89adf-149">メールボックスに DEP を割り当てる</span><span class="sxs-lookup"><span data-stu-id="89adf-149">Assign a DEP to a mailbox</span></span>](#assign-a-dep-to-a-mailbox)

- [<span data-ttu-id="89adf-150">メールボックスの暗号化を検証する</span><span class="sxs-lookup"><span data-stu-id="89adf-150">Validate mailbox encryption</span></span>](#validate-mailbox-encryption)

<span data-ttu-id="89adf-151">SharePoint Online と OneDrive for Business:</span><span class="sxs-lookup"><span data-stu-id="89adf-151">SharePoint Online and OneDrive for Business:</span></span>
  
- [<span data-ttu-id="89adf-152">SharePoint Online と OneDrive for business の各 geo にデータ暗号化ポリシー (DEP) を作成する</span><span class="sxs-lookup"><span data-stu-id="89adf-152">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>](#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)

- [<span data-ttu-id="89adf-153">SharePoint Online、OneDrive for Business、および Teams ファイルのファイル暗号化を検証する</span><span class="sxs-lookup"><span data-stu-id="89adf-153">Validate file encryption for SharePoint Online, OneDrive for Business, and Teams files</span></span>](#validate-file-encryption)

## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a><span data-ttu-id="89adf-154">Azure Key Vault のタスクを完了し、顧客キーの Microsoft FastTrack を管理する</span><span class="sxs-lookup"><span data-stu-id="89adf-154">Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key</span></span>

<span data-ttu-id="89adf-155">Azure Key Vault でこれらのタスクを完了します。</span><span class="sxs-lookup"><span data-stu-id="89adf-155">Complete these tasks in Azure Key Vault.</span></span> <span data-ttu-id="89adf-156">これらの手順は、Exchange Online と Skype for business のどちらを使用するか、または Office 365 でサポートされているすべてのサービスに対して、顧客キーを設定するかどうかにかかわらず実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89adf-156">You'll need to complete these steps regardless of whether you intend to set up Customer Key for Exchange Online and Skype for Business or for SharePoint Online, OneDrive for Business, and Teams files, or for all supported services in Office 365.</span></span>
  
### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="89adf-157">2つの新しい Azure サブスクリプションを作成する</span><span class="sxs-lookup"><span data-stu-id="89adf-157">Create two new Azure subscriptions</span></span>

<span data-ttu-id="89adf-158">顧客キーには2つの Azure サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="89adf-158">Customer Key requires two Azure subscriptions.</span></span> <span data-ttu-id="89adf-159">ベストプラクティスとして、Microsoft では、顧客キーと共に使用するために新しい Azure サブスクリプションを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="89adf-159">As a best practice, Microsoft recommends that you create new Azure subscriptions for use with Customer Key.</span></span> <span data-ttu-id="89adf-160">Azure Key Vault キーは、同じ Azure Active Directory (Microsoft Azure Active Directory) テナント内のアプリケーションに対してのみ承認できます。 DEPs が割り当てられている組織で使用されているものと同じ Azure AD テナントを使用して、新しいサブスクリプションを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89adf-160">Azure Key Vault keys can only be authorized for applications in the same Azure Active Directory (Microsoft Azure Active Directory) tenant, you must create the new subscriptions using the same Azure AD tenant used with your organization where the DEPs will be assigned.</span></span> <span data-ttu-id="89adf-161">たとえば、組織内のグローバル管理者権限を持つ職場または学校のアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="89adf-161">For example, using your work or school account that has global administrator privileges in your organization.</span></span> <span data-ttu-id="89adf-162">詳細な手順については、「 [組織としての Azure へのサインアップ](https://azure.microsoft.com/documentation/articles/sign-up-organization/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89adf-162">For detailed steps, see [Sign up for Azure as an organization](https://azure.microsoft.com/documentation/articles/sign-up-organization/).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="89adf-163">顧客キーには、データ暗号化ポリシー (DEP) ごとに2つのキーが必要です。</span><span class="sxs-lookup"><span data-stu-id="89adf-163">Customer Key requires two keys for each data encryption policy (DEP).</span></span> <span data-ttu-id="89adf-164">これを実現するためには、2つの Azure サブスクリプションを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89adf-164">In order to achieve this, you must create two Azure subscriptions.</span></span> <span data-ttu-id="89adf-165">ベストプラクティスとして、組織のメンバーごとに、各サブスクリプションで1つのキーを構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="89adf-165">As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription.</span></span> <span data-ttu-id="89adf-166">さらに、これらの Azure サブスクリプションは、Office 365 の暗号化キーを管理するためにのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="89adf-166">In addition, these Azure subscriptions should only be used to administer encryption keys for Office 365.</span></span> <span data-ttu-id="89adf-167">これにより、オペレーターのいずれかが偶然、故意、または悪意によって削除された場合や、自分が責任を持つキーを誤って管理した場合に、組織が保護されます。</span><span class="sxs-lookup"><span data-stu-id="89adf-167">This protects your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible.</span></span> <br/> <span data-ttu-id="89adf-168">顧客キーで使用するために Azure Key Vault リソースの管理にのみ使用される新しい Azure サブスクリプションをセットアップすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="89adf-168">We recommend that you set up new Azure subscriptions that are solely used for managing Azure Key Vault resources for use with Customer Key.</span></span> <span data-ttu-id="89adf-169">組織に対して作成できる Azure サブスクリプションの数に実際に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="89adf-169">There is no practical limit to the number of Azure subscriptions that you can create for your organization.</span></span> <span data-ttu-id="89adf-170">これらのベストプラクティスに従うことで、顧客キーによって使用されるリソースの管理を支援しながら、人的エラーの影響を最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="89adf-170">Following these best practices will minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span>
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a><span data-ttu-id="89adf-171">Office 365 の顧客キーを有効にするための要求を送信する</span><span class="sxs-lookup"><span data-stu-id="89adf-171">Submit a request to activate Customer Key for Office 365</span></span>

<span data-ttu-id="89adf-172">Azure の手順を完了したら、 [Microsoft FastTrack ポータル](https://fasttrack.microsoft.com/)で提供要求を提出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89adf-172">Once you've completed the Azure steps, you'll need to submit an offer request in the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span> <span data-ttu-id="89adf-173">FastTrack web ポータルを通じて要求を送信すると、Microsoft は、提供された Azure Key Vault 構成データと連絡先情報を検証します。</span><span class="sxs-lookup"><span data-stu-id="89adf-173">Once you have submitted a request through the FastTrack web portal, Microsoft verifies the Azure Key Vault configuration data and contact information you provided.</span></span> <span data-ttu-id="89adf-174">組織の承認済みの担当者に関する提供フォームで行う選択は、重要であり、顧客のキーの登録を完了するために必要です。</span><span class="sxs-lookup"><span data-stu-id="89adf-174">The selections that you make in the offer form regarding the authorized officers of your organization is critical and necessary for completion of Customer Key registration.</span></span> <span data-ttu-id="89adf-175">フォームで選択する組織の責任者は、顧客キーデータ暗号化ポリシーで使用されているすべてのキーを取り消して破棄するためのすべての要求の信頼性を確保するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="89adf-175">The officers of your organization that you select in the form will be the used to ensure the authenticity of any request to revoke and destroy all keys used with a Customer Key data encryption policy.</span></span> <span data-ttu-id="89adf-176">この手順を1回実行する必要があります。これを行うには、Exchange Online と Skype for business の使用をサポートするための顧客キーを有効にし、SharePoint Online と OneDrive for business の顧客キーを再度アクティブにします。</span><span class="sxs-lookup"><span data-stu-id="89adf-176">You'll need to do this step once to activate Customer Key for Exchange Online and Skype for Business coverage and a second time to activate Customer Key for SharePoint Online and OneDrive for Business.</span></span>
  
<span data-ttu-id="89adf-177">顧客キーを有効にするオファーを提出するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="89adf-177">To submit an offer to activate Customer Key, complete these steps:</span></span>
  
1. <span data-ttu-id="89adf-178">組織で全体管理者のアクセス許可を持つ職場または学校のアカウントを使用して、 [Microsoft FastTrack ポータル](https://fasttrack.microsoft.com/)にログインします。</span><span class="sxs-lookup"><span data-stu-id="89adf-178">Using a work or school account that has global administrator permissions in your organization, log in to the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span>

2. <span data-ttu-id="89adf-179">ログインしたら、 **ダッシュボード**を参照します。</span><span class="sxs-lookup"><span data-stu-id="89adf-179">Once you're logged in, browse to the **Dashboard**.</span></span>

3. <span data-ttu-id="89adf-180">ナビゲーションバーから [**展開**] を選択する**か、また**は**展開**情報カードの [**すべての展開リソースを表示**する] を選択して、現在のサービスの一覧を確認します。</span><span class="sxs-lookup"><span data-stu-id="89adf-180">Choose **Deploy** from the navigation bar **OR** select **View all deployment resources** on the **Deploy** information card, and review the list of current offers.</span></span>

4. <span data-ttu-id="89adf-181">適用するオファーの情報カードを選択します。</span><span class="sxs-lookup"><span data-stu-id="89adf-181">Choose the information card for the offer that applies to you:</span></span>

   - <span data-ttu-id="89adf-182">**Exchange Online と Skype For business:\*\*\*\*Exchange online オファーの要求暗号化キーのヘルプ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="89adf-182">**Exchange Online and Skype for Business:** Choose the **Request encryption key help for Exchange online** offer.</span></span>

   - <span data-ttu-id="89adf-183">**SharePoint Online、OneDrive、Teams の各ファイル:** [ **Sharepoint および OneDrive オファーの要求の暗号化キーのヘルプ** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="89adf-183">**SharePoint Online, OneDrive, and Teams files:** Choose the **Request encryption key help for Sharepoint and OneDrive** offer.</span></span>

5. <span data-ttu-id="89adf-184">オファーの詳細を確認したら、 **手順2に進み**ます。</span><span class="sxs-lookup"><span data-stu-id="89adf-184">Once you've reviewed the offer details, choose **Continue to step 2**.</span></span>

6. <span data-ttu-id="89adf-185">提供フォームで該当するすべての詳細と要求された情報を記入します。</span><span class="sxs-lookup"><span data-stu-id="89adf-185">Fill out all applicable details and requested information on the offer form.</span></span> <span data-ttu-id="89adf-186">暗号化キーとデータを永続的に、元に戻れないように承認する組織の責任者に対して、特定の選択について特に注目してください。</span><span class="sxs-lookup"><span data-stu-id="89adf-186">Pay particular attention to your selections for which officers of your organization you want to authorize to approve the permanent and irreversible destruction of encryption keys and data.</span></span> <span data-ttu-id="89adf-187">フォームが完成したら、[ **送信**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="89adf-187">Once you've completed the form, choose **Submit**.</span></span>

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="89adf-188">Azure サブスクリプションを登録して必須の保持期間を使用する</span><span class="sxs-lookup"><span data-stu-id="89adf-188">Register Azure subscriptions to use a mandatory retention period</span></span>

<span data-ttu-id="89adf-189">ルート暗号化キーが一時的または完全に失われると、非常に破壊的または重大な操作によってデータが失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="89adf-189">The temporary or permanent loss of root encryption keys can be very disruptive or even catastrophic to service operation and can result in data loss.</span></span> <span data-ttu-id="89adf-190">このため、顧客キーで使用されるリソースには強力な保護が必要です。</span><span class="sxs-lookup"><span data-stu-id="89adf-190">For this reason, the resources used with Customer Key require strong protection.</span></span> <span data-ttu-id="89adf-191">顧客キーと共に使用されるすべての Azure リソースは、既定の構成を超える保護メカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="89adf-191">All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration.</span></span> <span data-ttu-id="89adf-192">Azure サブスクリプションは、即時および irrevocable のキャンセルを防止するようにタグ付けまたは登録することができます。</span><span class="sxs-lookup"><span data-stu-id="89adf-192">Azure subscriptions can be tagged or registered in a way that will prevent immediate and irrevocable cancellation.</span></span> <span data-ttu-id="89adf-193">これは、必須の保持期間の登録と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="89adf-193">This is referred to as registering for a mandatory retention period.</span></span> <span data-ttu-id="89adf-194">必須の保持期間に Azure サブスクリプションを登録するために必要な手順については、Microsoft 365 チームとの共同作業が必要です。</span><span class="sxs-lookup"><span data-stu-id="89adf-194">The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Microsoft 365 team.</span></span> <span data-ttu-id="89adf-195">このプロセスには、1 ~ 5 営業日かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="89adf-195">This process can take from one to five business days.</span></span> <span data-ttu-id="89adf-196">以前は、これは「キャンセルしない」と呼ばれることがありました。</span><span class="sxs-lookup"><span data-stu-id="89adf-196">Previously, this was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="89adf-197">Microsoft 365 チームに連絡する前に、顧客キーで使用する Azure サブスクリプションごとに以下の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89adf-197">Before contacting the Microsoft 365 team, you must perform the following steps for each Azure subscription that you use with Customer Key.</span></span> <span data-ttu-id="89adf-198">開始する前に、 [Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) モジュールがインストールされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="89adf-198">Ensure that you have the [Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) module installed before you start.</span></span>
  
1. <span data-ttu-id="89adf-199">Azure PowerShell でサインインします。</span><span class="sxs-lookup"><span data-stu-id="89adf-199">Sign in with Azure PowerShell.</span></span> <span data-ttu-id="89adf-200">手順については、「 [Azure PowerShell を使用](https://docs.microsoft.com/powershell/azure/authenticate-azureps)してサインインする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89adf-200">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="89adf-201">Register-AzProviderFeature コマンドレットを実行して、必須の保持期間を使用するサブスクリプションを登録します。</span><span class="sxs-lookup"><span data-stu-id="89adf-201">Run the Register-AzProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span> <span data-ttu-id="89adf-202">各サブスクリプションに対してこの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="89adf-202">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. <span data-ttu-id="89adf-203">プロセスを完了させるために、Microsoft にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="89adf-203">Contact Microsoft to have the process finalized.</span></span> <span data-ttu-id="89adf-204">SharePoint および OneDrive for Business チームについては、 [spock@microsoft.com](mailto:spock@microsoft.com)にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="89adf-204">For the SharePoint and OneDrive for Business team, contact [spock@microsoft.com](mailto:spock@microsoft.com).</span></span> <span data-ttu-id="89adf-205">Exchange Online と Skype for Business の場合は、 [exock@microsoft.com](mailto:exock@microsoft.com)にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="89adf-205">For Exchange Online and Skype for Business, contact [exock@microsoft.com](mailto:exock@microsoft.com).</span></span> <span data-ttu-id="89adf-206">メールに次のものを含めます。</span><span class="sxs-lookup"><span data-stu-id="89adf-206">Include the following in your email:</span></span>

   <span data-ttu-id="89adf-207">**件名**: の顧客キー \<*Your tenant's fully-qualified domain name*\></span><span class="sxs-lookup"><span data-stu-id="89adf-207">**Subject**: Customer Key for \<*Your tenant's fully-qualified domain name*\></span></span>

   <span data-ttu-id="89adf-208">**本文**: 必須の保持期間を最終処理するサブスクリプション id。</span><span class="sxs-lookup"><span data-stu-id="89adf-208">**Body**: Subscription IDs for which you want to have the mandatory retention period finalized.</span></span>
   <span data-ttu-id="89adf-209">各サブスクリプションのための、-AzProviderFeature の出力。</span><span class="sxs-lookup"><span data-stu-id="89adf-209">The output of Get-AzProviderFeature for each subscription.</span></span>

   <span data-ttu-id="89adf-210">このプロセスを完了するためのサービスレベル契約 (SLA) は、Microsoft が事前通知 (および検証) した後で、サブスクリプションを必須の保持期間を使用するように登録した後、5営業日です。</span><span class="sxs-lookup"><span data-stu-id="89adf-210">The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period.</span></span>

4. <span data-ttu-id="89adf-211">登録が完了したことを Microsoft から通知されたら、次のようにして、「Get-AzProviderFeature」コマンドを実行し、登録の状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="89adf-211">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzProviderFeature command as follows.</span></span> <span data-ttu-id="89adf-212">検証された場合、取得した AzProviderFeature コマンドは、**登録状態**プロパティに**登録さ**れている値を返します。</span><span class="sxs-lookup"><span data-stu-id="89adf-212">If verified, the Get-AzProviderFeature command returns a value of **Registered** for the **Registration State** property.</span></span> <span data-ttu-id="89adf-213">各サブスクリプションに対してこの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="89adf-213">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. <span data-ttu-id="89adf-214">プロセスを完了するには、AzResourceProvider コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="89adf-214">To complete the process, run the Register-AzResourceProvider command.</span></span> <span data-ttu-id="89adf-215">各サブスクリプションに対してこの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="89adf-215">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="89adf-216">各サブスクリプションにプレミアム Azure キーコンテナーを作成する</span><span class="sxs-lookup"><span data-stu-id="89adf-216">Create a premium Azure Key Vault in each subscription</span></span>

<span data-ttu-id="89adf-217">キーコンテナーを作成する手順については、「azure [キーコンテナー](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)の概要」で説明されています。このガイドでは、azure PowerShell のインストールと起動、azure サブスクリプションへの接続、リソースグループの作成、およびそのリソースグループでのキーコンテナーの作成を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="89adf-217">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="89adf-218">キーコンテナーを作成する場合、SKU: Standard または Premium のどちらかを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89adf-218">When you create a key vault, you must choose a SKU: either Standard or Premium.</span></span> <span data-ttu-id="89adf-219">標準 SKU を使用すると、Azure Key Vault キーがソフトウェアで保護されます。ハードウェアセキュリティモジュール (HSM) キー保護はありません。また、Premium SKU では、重要な資格情報のキーを保護するために Hsm を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="89adf-219">The Standard SKU allows Azure Key Vault keys to be protected with software - there is no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys.</span></span> <span data-ttu-id="89adf-220">顧客キーは、いずれかの SKU を使用するキーコンテナーを受け入れますが、Microsoft は Premium SKU のみを使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="89adf-220">Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU.</span></span> <span data-ttu-id="89adf-221">どちらの種類のキーを使用する操作のコストも同じであるため、コストの唯一の違いは、各 HSM で保護されたキーの月ごとのコストです。</span><span class="sxs-lookup"><span data-stu-id="89adf-221">The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key.</span></span> <span data-ttu-id="89adf-222">詳細については、「 [主要な資格情報](https://azure.microsoft.com/pricing/details/key-vault/) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89adf-222">See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="89adf-223">プレミアム SKU キーコンテナーおよび HSM で保護された、運用データ用のキーを使用して、テストおよび検証の目的で標準的な SKU キーボルトとキーのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="89adf-223">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span>
  
<span data-ttu-id="89adf-224">顧客キーを使用する Microsoft 365 サービスごとに、作成した2つの Azure サブスクリプションのそれぞれにキーコンテナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="89adf-224">For each Microsoft 365 service with which you will use Customer Key, create a key vault in each of the two Azure subscriptions that you created.</span></span> <span data-ttu-id="89adf-225">たとえば、Exchange Online と Skype for business のみ、または SharePoint Online と OneDrive for business の場合のみ、ボルトのペアを1つだけ作成します。</span><span class="sxs-lookup"><span data-stu-id="89adf-225">For example, for Exchange Online and Skype for Business only or SharePoint Online and OneDrive for Business only, you will create only one pair of vaults.</span></span> <span data-ttu-id="89adf-226">Exchange Online と SharePoint Online の両方で顧客キーを有効にするには、キーコンテナーの2つのペアを作成します。</span><span class="sxs-lookup"><span data-stu-id="89adf-226">To enable Customer Key for both Exchange Online and SharePoint Online, you will create two pairs of key vaults.</span></span>
  
<span data-ttu-id="89adf-227">資格情報コンテナーを関連付けるためのデータ暗号化ポリシーの使用目的を反映する、キーコンテナーの名前付け規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="89adf-227">Use a naming convention for key vaults that reflects the intended use of the data encryption policy with which you will associate the vaults.</span></span> <span data-ttu-id="89adf-228">命名規則の推奨事項については、以下の「ベストプラクティス」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="89adf-228">See the Best Practices section below for naming convention recommendations.</span></span>
  
<span data-ttu-id="89adf-229">各データ暗号化ポリシーに対して、独立したコンテナーのセットを作成します。</span><span class="sxs-lookup"><span data-stu-id="89adf-229">Create a separate, paired set of vaults for each data encryption policy.</span></span> <span data-ttu-id="89adf-230">Exchange Online の場合、データ暗号化ポリシーの範囲は、そのポリシーをメールボックスに割り当てるときに選択されます。</span><span class="sxs-lookup"><span data-stu-id="89adf-230">For Exchange Online, the scope of a data encryption policy is chosen by you when you assign the policy to mailbox.</span></span> <span data-ttu-id="89adf-231">メールボックスに割り当てることのできるポリシーは1つだけで、最大50のポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="89adf-231">A mailbox can have only one policy assigned, and you can create up to fifty policies.</span></span> <span data-ttu-id="89adf-232">SharePoint Online では、ポリシーの範囲として、組織内のすべてのデータが地理的な場所または _geo_に含まれます。</span><span class="sxs-lookup"><span data-stu-id="89adf-232">For SharePoint Online the scope of a policy is all of the data within an organization in a geographic location, or _geo_.</span></span>

<span data-ttu-id="89adf-233">キーコンテナーの作成には、Azure リソースグループの作成も必要です。これは、キーコンテナーにはストレージ容量が必要です (非常に小さい)。また、キーヴォールトログが有効になっている場合は、保存されたデータも生成します。</span><span class="sxs-lookup"><span data-stu-id="89adf-233">The creation of key vaults also requires the creation of Azure resource groups, since key vaults need storage capacity (though very small) and Key Vault logging, if enabled, also generates stored data.</span></span> <span data-ttu-id="89adf-234">ベストプラクティスとして、Microsoft では、個別の管理者を使用して各リソースグループを管理することをお勧めします。管理者は、関連するすべての顧客キーリソースを管理する一連の管理者と連携しています。</span><span class="sxs-lookup"><span data-stu-id="89adf-234">As a best practice Microsoft recommends using separate administrators to manage each resource group, with the administration aligned with the set of administrators that will manage all related Customer Key resources.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="89adf-235">可用性を最大限にするには、Microsoft 365 サービスに近い地域にキーコンテナーが必要です。</span><span class="sxs-lookup"><span data-stu-id="89adf-235">To maximize availability, your key vaults should be in regions close to your Microsoft 365 service.</span></span> <span data-ttu-id="89adf-236">たとえば、北米に Exchange Online 組織がある場合は、北アメリカにキーコンテナーを配置します。</span><span class="sxs-lookup"><span data-stu-id="89adf-236">For example, if your Exchange Online organization is in North America, place your key vaults in North America.</span></span> <span data-ttu-id="89adf-237">Exchange Online 組織がヨーロッパの場合は、重要な資格を欧州に配置します。</span><span class="sxs-lookup"><span data-stu-id="89adf-237">If your Exchange Online organization is in Europe, place your key vaults in Europe.</span></span><br/><span data-ttu-id="89adf-238">キーコンテナーに共通のプレフィックスを使用します。また、重要な資格情報の使用およびスコープの省略形を含みます (たとえば、コンテナーが北米に配置される Contoso SharePoint サービスの場合は、名前の組み合わせが O365SP-NA-VaultA1 および O365SP-NA-VaultA2 になります。</span><span class="sxs-lookup"><span data-stu-id="89adf-238">Use a common prefix for key vaults, and include an abbreviation of the use and scope of the key vault and keys (e.g., for the Contoso SharePoint service where the vaults will be located in North America, a possible pair of names is Contoso-O365SP-NA-VaultA1 and Contoso-O365SP-NA-VaultA2.</span></span> <span data-ttu-id="89adf-239">コンテナー名は Azure 内のグローバルに一意の文字列なので、目的の名前が他の Azure のお客様によって既に要求されている場合は、目的の名前のバリエーションを試す必要があります。</span><span class="sxs-lookup"><span data-stu-id="89adf-239">Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers.</span></span> <span data-ttu-id="89adf-240">2017年7月の資格情報を変更することはできません。そのため、セットアップに関する計画を作成し、2番目のユーザーを使用して計画が正常に実行されることを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="89adf-240">As of July 2017 vault names cannot be changed, so a best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span><br/><span data-ttu-id="89adf-241">可能な場合は、ペアになっていない地域にコンテナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="89adf-241">If possible, create your vaults in non-paired regions.</span></span> <span data-ttu-id="89adf-242">ペアになっている Azure 領域は、サービス障害ドメイン間で高可用性を提供します。</span><span class="sxs-lookup"><span data-stu-id="89adf-242">Paired Azure regions provide high availability across service failure domains.</span></span> <span data-ttu-id="89adf-243">そのため、地域のペアは、互いのバックアップ地域と考えることができます。</span><span class="sxs-lookup"><span data-stu-id="89adf-243">Therefore, regional pairs can be thought of as each other's backup region.</span></span> <span data-ttu-id="89adf-244">これは、1つの領域に配置されている Azure リソースが、ペア化された領域を通じて自動的にフォールトトレランスを獲得することを意味します。</span><span class="sxs-lookup"><span data-stu-id="89adf-244">This means that an Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region.</span></span> <span data-ttu-id="89adf-245">このため、領域がペアになっているデータ暗号化ポリシーで使用される2つの資格情報領域を選択すると、2つの空き領域が使用されることになります。</span><span class="sxs-lookup"><span data-stu-id="89adf-245">For this reason, choosing regions for two vaults used in a data encryption policy where the regions are paired means that only a total of two regions of availability are in use.</span></span> <span data-ttu-id="89adf-246">ほとんどの地域には2つの地域があるため、ペアになっていない地域を選択することはまだできません。</span><span class="sxs-lookup"><span data-stu-id="89adf-246">Most geographies only have two regions, so it's not yet possible to select non-paired regions.</span></span> <span data-ttu-id="89adf-247">可能であれば、データ暗号化ポリシーで使用する2つの資格情報に対して2つのペアでない地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="89adf-247">If possible, choose two non-paired regions for the two vaults used with a data encryption policy.</span></span> <span data-ttu-id="89adf-248">これは、合計4つの可用性の領域からメリットを得られます。</span><span class="sxs-lookup"><span data-stu-id="89adf-248">This benefits from a total of four regions of availability.</span></span> <span data-ttu-id="89adf-249">詳細については、「 [Business 継続性と障害復旧 (BCDR)](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) 」を参照してください。現在の地域のペアの一覧については、「Azure ペアリング領域」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89adf-249">For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span>
  
### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="89adf-250">各キーコンテナーにアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="89adf-250">Assign permissions to each key vault</span></span>

<span data-ttu-id="89adf-251">各キーコンテナーについて、お客様の実装に応じて、顧客キーに対して3つの個別のアクセス許可セットを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89adf-251">For each key vault, you will need to define three separate sets of permissions for Customer Key, depending on your implementation.</span></span> <span data-ttu-id="89adf-252">たとえば、次のいずれかのアクセス許可のセットを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89adf-252">For example, you will need to define one set of permissions for each of the following:</span></span>
  
- <span data-ttu-id="89adf-253">組織のために主要な資格情報コンテナーの日常の管理を実行する**主要な資格情報コンテナー管理者**。</span><span class="sxs-lookup"><span data-stu-id="89adf-253">**Key vault administrators** that will perform day-to-day management of your key vault for your organization.</span></span> <span data-ttu-id="89adf-254">これらのタスクには、backup、create、get、import、list、restore があります。</span><span class="sxs-lookup"><span data-stu-id="89adf-254">These tasks include backup, create, get, import, list, and restore.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="89adf-255">キーコンテナー管理者に割り当てられているアクセス許可のセットには、キーを削除するためのアクセス許可は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="89adf-255">The set of permissions assigned to key vault administrators does not include the permission to delete keys.</span></span> <span data-ttu-id="89adf-256">これは意図的で重要な手法です。</span><span class="sxs-lookup"><span data-stu-id="89adf-256">This is intentional and an important practice.</span></span> <span data-ttu-id="89adf-257">暗号化キーの削除は、通常、データを完全に破棄するため、通常は行われません。</span><span class="sxs-lookup"><span data-stu-id="89adf-257">Deleting encryption keys is not typically done, since doing so permanently destroys data.</span></span> <span data-ttu-id="89adf-258">ベストプラクティスとして、既定では、このアクセス許可を主要な資格情報管理者に付与しないでください。</span><span class="sxs-lookup"><span data-stu-id="89adf-258">As a best practice, do not grant this permission to key vault administrators by default.</span></span> <span data-ttu-id="89adf-259">その代わりに、主要な資格情報投稿者に対してこれを予約し、その結果を明確に理解した後に、短い期間のみ管理者に割り当てるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="89adf-259">Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span>
  
  <span data-ttu-id="89adf-260">これらのアクセス許可を組織内のユーザーに割り当てるには、azure PowerShell を使用して Azure サブスクリプションにログインします。</span><span class="sxs-lookup"><span data-stu-id="89adf-260">To assign these permissions to a user in your organization, log in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="89adf-261">手順については、「 [Azure PowerShell を使用](https://docs.microsoft.com/powershell/azure/authenticate-azureps)してサインインする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89adf-261">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

- <span data-ttu-id="89adf-262">必要なアクセス許可を割り当てるには、AzKeyVaultAccessPolicy コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="89adf-262">Run the Set-AzKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   <span data-ttu-id="89adf-263">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="89adf-263">For example:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- <span data-ttu-id="89adf-264">Azure Key Vault 自体に対する権限を変更できる**重要な資格情報投稿**者。</span><span class="sxs-lookup"><span data-stu-id="89adf-264">**Key vault contributors** that can change permissions on the Azure Key Vault itself.</span></span> <span data-ttu-id="89adf-265">これらのアクセス許可を変更する必要があるのは、従業員がチームを脱退するか、チームに参加するか、重要な資格情報管理者がキーを削除または復元するためのアクセス許可を必要とする非常にまれな状況です。</span><span class="sxs-lookup"><span data-stu-id="89adf-265">You'll need to change these permissions as employees leave or join your team, or in the extremely rare situation that the key vault administrators legitimately need permission to delete or restore a key.</span></span> <span data-ttu-id="89adf-266">この一連の主要なコンテナー投稿者は、キーコンテナーに対して **投稿者** の役割を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89adf-266">This set of key vault contributors needs to be granted the **Contributor** role on your key vault.</span></span> <span data-ttu-id="89adf-267">この役割は、Azure リソースマネージャーを使用して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="89adf-267">You can assign this role by using Azure Resource Manager.</span></span> <span data-ttu-id="89adf-268">詳細な手順については、「 [役割ベースのアクセス制御を使用して Azure サブスクリプションリソースへのアクセスを管理する](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89adf-268">For detailed steps, see [Use Role-Based Access Control to manage access to your Azure subscription resources](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure).</span></span> <span data-ttu-id="89adf-269">サブスクリプションを作成する管理者は、このアクセス権と、他の管理者を共同作成者の役割に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="89adf-269">The administrator who creates a subscription has this access implicitly, as well as the ability to assign other administrators to the Contributor role.</span></span>

- <span data-ttu-id="89adf-270">顧客キーを Exchange Online と Skype for business で使用する場合は、Exchange Online と Skype for business の代わりにキーコンテナーを使用するためのアクセス許可を Microsoft 365 に付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89adf-270">If you intend to use Customer Key with Exchange Online and Skype for Business, you need to give permission to Microsoft 365 to use the key vault on behalf of Exchange Online and Skype for Business.</span></span> <span data-ttu-id="89adf-271">同様に、SharePoint Online と OneDrive for business で顧客キーを使用する場合は、SharePoint Online と OneDrive for business の代わりにキーコンテナーを使用するために、Microsoft 365 のアクセス許可を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89adf-271">Likewise, if you intend to use Customer Key with SharePoint Online and OneDrive for Business, you need to add permission for the Microsoft 365 to use the key vault on behalf of SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="89adf-272">Microsoft 365 にアクセス許可を付与するには、次の構文を使用して **AzKeyVaultAccessPolicy** コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="89adf-272">To give permission to Microsoft 365, run the **Set-AzKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span> 

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   <span data-ttu-id="89adf-273">ここで、</span><span class="sxs-lookup"><span data-stu-id="89adf-273">Where:</span></span>

    - <span data-ttu-id="89adf-274">[*コンテナー名*は、作成したキーコンテナーの名前です。</span><span class="sxs-lookup"><span data-stu-id="89adf-274">*vault name* is the name of the key vault you created.</span></span>

    - <span data-ttu-id="89adf-275">Exchange Online と Skype for Business の場合は、  *Office 365 appID* をに置き換えます。 `00000002-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="89adf-275">For Exchange Online and Skype for Business, replace  *Office 365 appID* with `00000002-0000-0ff1-ce00-000000000000`</span></span>

    - <span data-ttu-id="89adf-276">SharePoint Online、OneDrive for Business、Teams の各ファイルについては、  *Office 365 appID* をに置き換えます。 `00000003-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="89adf-276">For SharePoint Online, OneDrive for Business, and Teams files, replace  *Office 365 appID* with `00000003-0000-0ff1-ce00-000000000000`</span></span>

  <span data-ttu-id="89adf-277">例: Exchange Online と Skype for Business のアクセス許可を設定する:</span><span class="sxs-lookup"><span data-stu-id="89adf-277">Example: Setting permissions for Exchange Online and Skype for Business:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  <span data-ttu-id="89adf-278">例: SharePoint Online、OneDrive for Business、Teams の各ファイルに対する権限の設定:</span><span class="sxs-lookup"><span data-stu-id="89adf-278">Example: Setting permissions for SharePoint Online, OneDrive for Business, and Teams files:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a><span data-ttu-id="89adf-279">キーコンテナーでの論理削除を有効にして、確認します。</span><span class="sxs-lookup"><span data-stu-id="89adf-279">Enable and then confirm soft delete on your key vaults</span></span>

<span data-ttu-id="89adf-280">キーをすばやく回復できると、偶然または悪意によって削除されたキーによってサービスの停止が発生する可能性が低くなります。</span><span class="sxs-lookup"><span data-stu-id="89adf-280">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys.</span></span> <span data-ttu-id="89adf-281">ユーザーキーでキーを使用する前に、この構成を (ソフト削除と呼ばれる) 有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="89adf-281">You need to enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key.</span></span> <span data-ttu-id="89adf-282">ソフト削除を有効にすると、バックアップからの復元を行わずに、削除から90日以内にキーまたは資格を回復できます。</span><span class="sxs-lookup"><span data-stu-id="89adf-282">Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="89adf-283">キーコンテナーでの論理削除を有効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="89adf-283">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="89adf-284">Windows Powershell を使用して、Azure サブスクリプションにサインインします。</span><span class="sxs-lookup"><span data-stu-id="89adf-284">Sign in to your Azure subscription with Windows Powershell.</span></span> <span data-ttu-id="89adf-285">手順については、「 [Azure PowerShell を使用](https://docs.microsoft.com/powershell/azure/authenticate-azureps)してサインインする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89adf-285">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="89adf-286">[-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault)コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="89adf-286">Run the [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet.</span></span> <span data-ttu-id="89adf-287">この例では、次のように、ソフトウェアの削除を有効にするキーコンテナーの名前を *vault name* にします。</span><span class="sxs-lookup"><span data-stu-id="89adf-287">In this example, *vault name* is the name of the key vault for which you are enabling soft delete:</span></span>

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. <span data-ttu-id="89adf-288">**-AzKeyVault**コマンドレットを実行して、重要なコンテナーに対して論理削除が構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="89adf-288">Confirm soft delete is configured for the key vault by running the **Get-AzKeyVault** cmdlet.</span></span> <span data-ttu-id="89adf-289">重要なコンテナーに対して論理削除が適切に構成されている場合、 _ソフト削除が有効_ なプロパティは **True**の値を返します。</span><span class="sxs-lookup"><span data-stu-id="89adf-289">If soft delete is configured properly for the key vault, then the _Soft Delete Enabled_ property returns a value of **True**:</span></span>

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="89adf-290">キーを作成またはインポートすることによって、各キーコンテナーにキーを追加する</span><span class="sxs-lookup"><span data-stu-id="89adf-290">Add a key to each key vault either by creating or importing a key</span></span>

<span data-ttu-id="89adf-291">Azure Key Vault にキーを追加するには、2つの方法があります。キーを直接キーコンテナーに作成することも、キーをインポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="89adf-291">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key.</span></span> <span data-ttu-id="89adf-292">キーコンテナーに直接キーを作成することは、より単純な方法ですが、キーのインポートでは、キーの生成方法を完全に制御できます。</span><span class="sxs-lookup"><span data-stu-id="89adf-292">Creating a key directly in Key Vault is the less complicated method, while importing a key provides total control over how the key is generated.</span></span>
  
<span data-ttu-id="89adf-293">キーコンテナーに直接キーを作成するには、次のように [AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="89adf-293">To create a key directly in your key vault, run the [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="89adf-294">ここで、</span><span class="sxs-lookup"><span data-stu-id="89adf-294">Where:</span></span>

- <span data-ttu-id="89adf-295">"*コンテナー名*" は、キーを作成するキーコンテナーの名前です。</span><span class="sxs-lookup"><span data-stu-id="89adf-295">*vault name* is the name of the key vault in which you want to create the key.</span></span>

- <span data-ttu-id="89adf-296">[*キー名*には、新しいキーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="89adf-296">*key name* is the name you want to give the new key.</span></span>

  > [!TIP]
  > <span data-ttu-id="89adf-297">キーコンテナーの場合と同様の命名規則を使用して、名前付きキーを指定します。</span><span class="sxs-lookup"><span data-stu-id="89adf-297">Name keys using a similar naming convention as described above for key vaults.</span></span> <span data-ttu-id="89adf-298">このようにすると、キー名のみを表示するツールでは、文字列が自己記述されます。</span><span class="sxs-lookup"><span data-stu-id="89adf-298">This way, in tools that show only the key name, the string is self-describing.</span></span>
  
- <span data-ttu-id="89adf-299">キーを HSM で保護する場合は、 _Destination_パラメーターの値として**hsm**を指定する必要があります。そうでない場合は、**ソフトウェア**を指定します。</span><span class="sxs-lookup"><span data-stu-id="89adf-299">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the _Destination_ parameter, otherwise, specify **Software**.</span></span>

<span data-ttu-id="89adf-300">例えば、</span><span class="sxs-lookup"><span data-stu-id="89adf-300">For example,</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="89adf-301">キーを直接キーコンテナーにインポートするには、nCipher nShield ハードウェアセキュリティモジュールを用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89adf-301">To import a key directly into your key vault, you need to have a nCipher nShield Hardware Security Module.</span></span>
  
<span data-ttu-id="89adf-302">一部の組織では、この方法を使用してキーの機能を確立し、次に示すこともできます。</span><span class="sxs-lookup"><span data-stu-id="89adf-302">Some organizations prefer this approach to establish the provenance of their keys, and then this method also provides the following:</span></span>
  
- <span data-ttu-id="89adf-303">インポートに使用されるツールセットには、nCipher からの構成証明が含まれています。生成するキー交換キー (KEK) はエクスポート可能ではないため、nCipher によって製造された正規の HSM の内部で生成されます。</span><span class="sxs-lookup"><span data-stu-id="89adf-303">The toolset used for import includes attestation from nCipher that the Key Exchange Key (KEK) that is used to encrypt the key you generate is not exportable and is generated inside a genuine HSM that was manufactured by nCipher.</span></span>

- <span data-ttu-id="89adf-304">ツールセットには、nCipher からの構成証明が含まれています。これは、Azure Key Vault セキュリティ world が nCipher で製造された正規の HSM でも生成されたことです。</span><span class="sxs-lookup"><span data-stu-id="89adf-304">The toolset includes attestation from nCipher that the Azure Key Vault security world was also generated on a genuine HSM manufactured by nCipher.</span></span> <span data-ttu-id="89adf-305">この構成証明は、Microsoft が正規の nCipher ハードウェアを使用していることを証明します。</span><span class="sxs-lookup"><span data-stu-id="89adf-305">This attestation proves to you that Microsoft is also using genuine nCipher hardware.</span></span>

<span data-ttu-id="89adf-306">セキュリティグループに確認して、上記の attestations が必要かどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="89adf-306">Check with your security group to determine if the above attestations are required.</span></span> <span data-ttu-id="89adf-307">オンプレミスのキーを作成してキーコンテナーにインポートする詳細な手順については、「 [Azure Key vault 用に HSM で保護されたキーを生成して転送する方法](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89adf-307">For detailed steps to create a key on-premises and import it into your key vault, see [How to generate and transfer HSM-protected keys for Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/).</span></span> <span data-ttu-id="89adf-308">各キーコンテナーにキーを作成するには、Azure の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="89adf-308">Use the Azure instructions to create a key in each key vault.</span></span>
  
### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="89adf-309">キーの回復レベルを確認する</span><span class="sxs-lookup"><span data-stu-id="89adf-309">Check the recovery level of your keys</span></span>

<span data-ttu-id="89adf-310">Microsoft 365 では、Azure Key Vault サブスクリプションがキャンセルされないように設定されており、顧客キーによって使用されるキーには、ソフト削除が有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="89adf-310">Microsoft 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled.</span></span> <span data-ttu-id="89adf-311">このことを確認するには、キーの回復レベルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="89adf-311">You can confirm this by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="89adf-312">キーの復旧レベルを確認するには、Azure PowerShell で、次のように AzKeyVaultKey コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="89adf-312">To check the recovery level of a key, in Azure PowerShell, run the Get-AzKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

<span data-ttu-id="89adf-313">_回復レベル_のプロパティが、回復**可能 + ProtectedSubscription**の値以外を返す場合は、このトピックを確認して、サブスクリプションを [キャンセルしない] 一覧に追加し、各キーコンテナーでソフト削除が有効になっていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89adf-313">If the _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, you will need to review this topic and ensure that you have followed all of the steps to put the subscription on the Do Not Cancel list and that you have soft delete enabled on each of your key vaults.</span></span>
  
### <a name="back-up-azure-key-vault"></a><span data-ttu-id="89adf-314">Azure Key Vault をバックアップする</span><span class="sxs-lookup"><span data-stu-id="89adf-314">Back up Azure Key Vault</span></span>

<span data-ttu-id="89adf-315">作成またはキーへの変更の直後に、バックアップを実行し、オンラインとオフラインの両方でバックアップとストアのコピーを行います。</span><span class="sxs-lookup"><span data-stu-id="89adf-315">Immediately following creation or any change to a key, perform a backup and store copies of the backup, both online and offline.</span></span> <span data-ttu-id="89adf-316">オフラインコピーは、物理的な安全または商用ストレージ機能などのネットワークに接続することはできません。</span><span class="sxs-lookup"><span data-stu-id="89adf-316">Offline copies should not be connected to any network, such as in a physical safe or commercial storage facility.</span></span> <span data-ttu-id="89adf-317">バックアップの少なくとも1つは、障害が発生した場合にアクセスできる場所に格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89adf-317">At least one copy of the backup should be stored in a location that will be accessible in the event of a disaster.</span></span> <span data-ttu-id="89adf-318">バックアップ blob はキーマテリアルを復元するための唯一の手段です。キーコンテナーキーを完全に破棄するか、またはその他の方法で操作できないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="89adf-318">The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable.</span></span> <span data-ttu-id="89adf-319">Azure key vault の外部にあるキーは、キーを使用するために必要なメタデータが外部キーに存在しないため、バックアップとして認定されません。</span><span class="sxs-lookup"><span data-stu-id="89adf-319">Keys that are external to Azure Key Vault and were imported to Azure Key Vault do not qualify as a backup because the metadata necessary for Customer Key to use the key does not exist with the external key.</span></span> <span data-ttu-id="89adf-320">顧客キーを使用した復元操作には、Azure Key Vault から取得したバックアップのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="89adf-320">Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key.</span></span> <span data-ttu-id="89adf-321">したがって、キーをアップロードまたは作成した後に、Azure Key Vault のバックアップを作成することが重要です。</span><span class="sxs-lookup"><span data-stu-id="89adf-321">Therefore, it is essential that a backup of Azure Key Vault be made once a key is uploaded or created.</span></span>
  
<span data-ttu-id="89adf-322">Azure Key Vault キーのバックアップを作成するには、次のように [AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="89adf-322">To create a backup of an Azure Key Vault key, run the [Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet as follows:</span></span>

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

<span data-ttu-id="89adf-323">出力ファイルがサフィックスを使用していることを確認し `.backup` ます。</span><span class="sxs-lookup"><span data-stu-id="89adf-323">Ensure that your output file uses the suffix `.backup`.</span></span>
  
<span data-ttu-id="89adf-324">このコマンドレットから得られる出力ファイルは暗号化されており、Azure Key Vault の外部では使用できません。</span><span class="sxs-lookup"><span data-stu-id="89adf-324">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault.</span></span> <span data-ttu-id="89adf-325">バックアップは、バックアップが実行された Azure サブスクリプションにのみ復元できます。</span><span class="sxs-lookup"><span data-stu-id="89adf-325">The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
> [!TIP]
> <span data-ttu-id="89adf-326">出力ファイルに対して、コンテナー名とキー名の組み合わせを選択します。</span><span class="sxs-lookup"><span data-stu-id="89adf-326">For the output file, choose a combination of your vault name and key name.</span></span> <span data-ttu-id="89adf-327">これにより、ファイル名が自己記述されます。</span><span class="sxs-lookup"><span data-stu-id="89adf-327">This will make the file name self-describing.</span></span> <span data-ttu-id="89adf-328">バックアップファイルの名前が競合しないようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="89adf-328">It will also ensure that backup file names do not collide.</span></span>
  
<span data-ttu-id="89adf-329">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="89adf-329">For example:</span></span>
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="89adf-330">Azure Key Vault 構成設定を検証する</span><span class="sxs-lookup"><span data-stu-id="89adf-330">Validate Azure Key Vault configuration settings</span></span>

<span data-ttu-id="89adf-331">DEP でキーを使用する前に検証を実行することはオプションですが、強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="89adf-331">Performing validation before using keys in a DEP is optional, but highly recommended.</span></span> <span data-ttu-id="89adf-332">特に、手順を使用して、このトピックで説明されているもの以外のキーとボルトを設定する場合は、顧客キーを構成する前に、Azure Key Vault のリソースの状態を検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89adf-332">In particular, if you use steps to set up your keys and vaults other than the ones described in this topic, you should validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="89adf-333">キーに get、wrapKey、および unwrapKey 操作が有効になっていることを確認するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="89adf-333">To verify that your keys have get, wrapKey, and unwrapKey operations enabled:</span></span>
  
<span data-ttu-id="89adf-334">次のようにして、次 [のコマンドレットを実行](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) します。</span><span class="sxs-lookup"><span data-stu-id="89adf-334">Run the [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="89adf-335">出力で、必要に応じて、アクセスポリシーと Exchange Online id (GUID) または SharePoint Online id (GUID) を探します。</span><span class="sxs-lookup"><span data-stu-id="89adf-335">In the output, look for the Access Policy and for the Exchange Online identity (GUID) or the SharePoint Online identity (GUID) as appropriate.</span></span> <span data-ttu-id="89adf-336">上記の3つのアクセス許可のすべてを [キーへのアクセス許可] の下に表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89adf-336">All three of the above permissions must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="89adf-337">アクセスポリシーの構成が正しくない場合は、次のように AzKeyVaultAccessPolicy コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="89adf-337">If the access policy configuration is incorrect, run the Set-AzKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

<span data-ttu-id="89adf-338">たとえば、Exchange Online と Skype for Business の場合は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="89adf-338">For example, for Exchange Online and Skype for Business:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="89adf-339">たとえば、SharePoint Online と OneDrive for business の場合は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="89adf-339">For example, for SharePoint Online and OneDrive for Business:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="89adf-340">キーの有効期限が設定されていないことを確認するには、 [AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) コマンドレットを次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="89adf-340">To verify that an expiration date is not set for your keys run the [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

<span data-ttu-id="89adf-341">期限切れのキーを顧客キーで使用することはできず、期限切れのキーを使用して実行しようとした操作は失敗し、サービスが停止する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="89adf-341">An expired key cannot be used by Customer Key and operations attempted with an expired key will fail, and possibly result in a service outage.</span></span> <span data-ttu-id="89adf-342">顧客キーと一緒に使用するキーに有効期限がないことを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="89adf-342">We strongly recommend that keys used with Customer Key do not have an expiration date.</span></span> <span data-ttu-id="89adf-343">有効期限日を設定すると、削除することはできませんが、別の日付に変更することができます。</span><span class="sxs-lookup"><span data-stu-id="89adf-343">An expiration date, once set, cannot be removed, but can be changed to a different date.</span></span> <span data-ttu-id="89adf-344">有効期限日が設定されているキーを使用する必要がある場合は、有効期限の値を12/31/9999 に変更します。</span><span class="sxs-lookup"><span data-stu-id="89adf-344">If a key must be used that has an expiration date set, change the expiration value to 12/31/9999.</span></span> <span data-ttu-id="89adf-345">有効期限が12/31/9999 以外の日付に設定されているキーは、Microsoft 365 検証に合格しません。</span><span class="sxs-lookup"><span data-stu-id="89adf-345">Keys with an expiration date set to a date other than 12/31/9999 will not pass Microsoft 365 validation.</span></span>
  
<span data-ttu-id="89adf-346">12/31/9999 以外の値に設定されている有効期限を変更するには、 [AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) コマンドレットを次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="89adf-346">To change an expiration date that has been set to any value other than 12/31/9999, run the [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> <span data-ttu-id="89adf-347">顧客キーで使用する暗号化キーに有効期限を設定しないようにします。</span><span class="sxs-lookup"><span data-stu-id="89adf-347">Don't set expiration dates on encryption keys you use with Customer Key.</span></span>
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="89adf-348">各 Azure Key Vault キーの URI を取得する</span><span class="sxs-lookup"><span data-stu-id="89adf-348">Obtain the URI for each Azure Key Vault key</span></span>

<span data-ttu-id="89adf-349">キーボルトを設定してキーを追加するために Azure のすべての手順を完了したら、次のコマンドを実行して、各キーコンテナーのキーの URI を取得します。</span><span class="sxs-lookup"><span data-stu-id="89adf-349">Once you've completed all the steps in Azure to set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault.</span></span> <span data-ttu-id="89adf-350">後で各 DEP を作成して割り当てるときにこれらの Uri を使用する必要があるので、この情報は安全な場所に保存しておいてください。</span><span class="sxs-lookup"><span data-stu-id="89adf-350">You will need to use these URIs when you create and assign each DEP later, so save this information in a safe place.</span></span> <span data-ttu-id="89adf-351">このコマンドは、キーヴォールトごとに1回実行してください。</span><span class="sxs-lookup"><span data-stu-id="89adf-351">Remember to run this command once for each key vault.</span></span>
  
<span data-ttu-id="89adf-352">Azure PowerShell の場合:</span><span class="sxs-lookup"><span data-stu-id="89adf-352">In Azure PowerShell:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="89adf-353">Office 365: Exchange Online と Skype for Business の顧客キーの設定</span><span class="sxs-lookup"><span data-stu-id="89adf-353">Office 365: Setting up Customer Key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="89adf-354">開始する前に、Azure Key Vault をセットアップするために必要なタスクを完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="89adf-354">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="89adf-355">詳細については [、「Azure Key Vault でタスクを完了する」および「Microsoft FastTrack For Customer key](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89adf-355">See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) for information.</span></span>
  
<span data-ttu-id="89adf-356">Exchange Online と Skype for Business の顧客キーを設定するには、Windows PowerShell を使用して Exchange Online にリモートで接続することにより、これらの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89adf-356">To set up Customer Key for Exchange Online and Skype for Business, you will need to perform these steps by remotely connecting to Exchange Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a><span data-ttu-id="89adf-357">Exchange Online と Skype for Business で使用するデータ暗号化ポリシー (DEP) を作成する</span><span class="sxs-lookup"><span data-stu-id="89adf-357">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>

<span data-ttu-id="89adf-358">DEP は、Azure Key Vault に格納されているキーのセットに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="89adf-358">A DEP is associated with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="89adf-359">Microsoft 365 のメールボックスに DEP を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="89adf-359">You assign a DEP to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="89adf-360">その後、Microsoft 365 は、ポリシーで識別されたキーを使用して、メールボックスを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="89adf-360">Microsoft 365 will then use the keys identified in the policy to encrypt the mailbox.</span></span> <span data-ttu-id="89adf-361">DEP を作成するには、前の手順で取得したキーの資格情報 Uri が必要です。</span><span class="sxs-lookup"><span data-stu-id="89adf-361">To create the DEP, you need the Key Vault URIs you obtained earlier.</span></span> <span data-ttu-id="89adf-362">手順については [、「Azure Key Vault キーごとに URI を取得](#obtain-the-uri-for-each-azure-key-vault-key) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89adf-362">See [Obtain the URI for each Azure Key Vault key](#obtain-the-uri-for-each-azure-key-vault-key) for instructions.</span></span>
  
<span data-ttu-id="89adf-363">念頭!</span><span class="sxs-lookup"><span data-stu-id="89adf-363">Remember!</span></span> <span data-ttu-id="89adf-364">DEP を作成するときには、2つの異なる Azure キーボルトに存在する2つのキーを指定します。</span><span class="sxs-lookup"><span data-stu-id="89adf-364">When you create a DEP, you specify two keys that reside in two different Azure Key Vaults.</span></span> <span data-ttu-id="89adf-365">これらのキーが、地理的冗長性を確保するために2つの独立した Azure 領域に配置されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="89adf-365">Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="89adf-366">DEP を作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="89adf-366">To create the DEP, follow these steps:</span></span>
  
1. <span data-ttu-id="89adf-367">ローカルコンピューターで、組織内のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell ウィンドウで [Exchange Online powershell に接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) します。</span><span class="sxs-lookup"><span data-stu-id="89adf-367">On your local computer, using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="89adf-368">DEP を作成するには、次のコマンドを入力して、新しい-DataEncryptionPolicy コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="89adf-368">To create a DEP, use the New-DataEncryptionPolicy cmdlet by typing the following command.</span></span>

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   <span data-ttu-id="89adf-369">ここで、</span><span class="sxs-lookup"><span data-stu-id="89adf-369">Where:</span></span>

   - <span data-ttu-id="89adf-370">*PolicyName* は、ポリシーに使用する名前です。</span><span class="sxs-lookup"><span data-stu-id="89adf-370">*PolicyName* is the name you want to use for the policy.</span></span> <span data-ttu-id="89adf-371">名前にスペースを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="89adf-371">Names cannot contain spaces.</span></span> <span data-ttu-id="89adf-372">たとえば、USA_mailboxes のようにします。</span><span class="sxs-lookup"><span data-stu-id="89adf-372">For example, USA_mailboxes.</span></span>

   - <span data-ttu-id="89adf-373">ポリシーの*説明*は、ポリシーの目的を記憶するのに役立つユーザーフレンドリなポリシーの説明です。</span><span class="sxs-lookup"><span data-stu-id="89adf-373">*Policy Description* is a user friendly description of the policy that will help you remember what the policy is for.</span></span> <span data-ttu-id="89adf-374">説明にはスペースを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="89adf-374">You can include spaces in the description.</span></span> <span data-ttu-id="89adf-375">たとえば、「米国およびその領土のメールボックスのルートキー」と入力します。</span><span class="sxs-lookup"><span data-stu-id="89adf-375">For example, "Root key for mailboxes in USA and its territories".</span></span>

   - <span data-ttu-id="89adf-376">*KeyVaultURI1* は、ポリシー内の最初のキーの URI です。</span><span class="sxs-lookup"><span data-stu-id="89adf-376">*KeyVaultURI1* is the URI for the first key in the policy.</span></span> <span data-ttu-id="89adf-377">たとえば、<https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01> などです。</span><span class="sxs-lookup"><span data-stu-id="89adf-377">For example, <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.</span></span>

   - <span data-ttu-id="89adf-378">*KeyVaultURI2* は、ポリシーの2番目のキーの URI です。</span><span class="sxs-lookup"><span data-stu-id="89adf-378">*KeyVaultURI2* is the URI for the second key in the policy.</span></span> <span data-ttu-id="89adf-379">たとえば、<https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02> などです。</span><span class="sxs-lookup"><span data-stu-id="89adf-379">For example, <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>.</span></span> <span data-ttu-id="89adf-380">2つの Uri をコンマとスペースで区切ります。</span><span class="sxs-lookup"><span data-stu-id="89adf-380">Separate the two URIs by a comma and a space.</span></span>

   <span data-ttu-id="89adf-381">例:</span><span class="sxs-lookup"><span data-stu-id="89adf-381">Example:</span></span>
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

<span data-ttu-id="89adf-382">構文およびパラメーターの詳細については、「 [New-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/new-data-encryptionpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89adf-382">For detailed syntax and parameter information, see [New-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/new-data-encryptionpolicy).</span></span>

### <a name="assign-a-dep-to-a-mailbox"></a><span data-ttu-id="89adf-383">メールボックスに DEP を割り当てる</span><span class="sxs-lookup"><span data-stu-id="89adf-383">Assign a DEP to a mailbox</span></span>

<span data-ttu-id="89adf-384">メールボックスの設定コマンドレットを使用して、メールボックスに DEP を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="89adf-384">Assign the DEP to a mailbox by using the Set-Mailbox cmdlet.</span></span> <span data-ttu-id="89adf-385">ポリシーを割り当てた後、Microsoft 365 は DEP で指定されたキーを使用してメールボックスを暗号化することができます。</span><span class="sxs-lookup"><span data-stu-id="89adf-385">Once you assign the policy, Microsoft 365 can encrypt the mailbox with the key designated in the DEP.</span></span>
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="89adf-386">ここで、 *MailboxIdParameter* はメールボックスを指定します。</span><span class="sxs-lookup"><span data-stu-id="89adf-386">Where *MailboxIdParameter* specifies a mailbox.</span></span> <span data-ttu-id="89adf-387">メールボックスの設定コマンドレットの詳細については、「 [メールボックスの設定](https://docs.microsoft.com/powershell/module/exchange/set-mailbox)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89adf-387">For more information about the Set-Mailbox cmdlet, see [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox).</span></span>

<span data-ttu-id="89adf-388">[ハイブリッド先進認証を使用する iOS および Android 用の Outlook を使用しているオンプレミスのメールボックス](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)の場合、Exchange Online テナントに同期される社内メールボックスのデータは、Set-mailuser コマンドレットを使用して DEP に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="89adf-388">For [on-premises mailboxes using Outlook for iOS and Android with hybrid Modern Authentication](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth), the on-premises mailbox data that is synchronized into your Exchange Online tenant can have DEP assigned using the Set-MailUser cmdlet.</span></span>

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="89adf-389">ここで、 *Mailuseridparameter* はメールユーザー (メールが有効なユーザーとも呼ばれます) を指定します。</span><span class="sxs-lookup"><span data-stu-id="89adf-389">Where *MailUserIdParameter* specifies a mail user (also known as a mail-enabled user).</span></span> <span data-ttu-id="89adf-390">Set-mailuser コマンドレットの詳細については、「 [set-mailuser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89adf-390">For more information about the Set-MailUser cmdlet, see [Set-MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser).</span></span>
  
### <a name="validate-mailbox-encryption"></a><span data-ttu-id="89adf-391">メールボックスの暗号化を検証する</span><span class="sxs-lookup"><span data-stu-id="89adf-391">Validate mailbox encryption</span></span>

<span data-ttu-id="89adf-392">メールボックスを暗号化するには、しばらく時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="89adf-392">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="89adf-393">初めてのポリシーの割り当ての場合、メールボックスは、サービスがメールボックスを暗号化する前に、あるデータベースから別のデータベースに完全に移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89adf-393">For first time policy assignment, the mailbox must also completely move from one database to another before the service can encrypt the mailbox.</span></span> <span data-ttu-id="89adf-394">DEP を変更した後、または初めてメールボックスに DEP を割り当てるときに、暗号化の検証を試行する前に、72時間待つことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="89adf-394">We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="89adf-395">メールボックスが暗号化されているかどうかを確認するには、Get-mailboxstatistics コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="89adf-395">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="89adf-396">IsEncrypted プロパティは、メールボックスが暗号化されている場合は **true** の値を返し、メールボックスが暗号化されていない場合は **false** の値を返します。</span><span class="sxs-lookup"><span data-stu-id="89adf-396">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span>

<span data-ttu-id="89adf-397">メールボックスの移動が完了するまでの時間は、最初に DEP を割り当てるメールボックスの数、およびメールボックスのサイズによって異なります。</span><span class="sxs-lookup"><span data-stu-id="89adf-397">The time to complete mailbox moves depends on the number of mailboxes to which you assign a DEP for the first time, as well as the size of the mailboxes.</span></span> <span data-ttu-id="89adf-398">DEP を割り当てたときから1週間後にメールボックスが暗号化されていない場合は、Microsoft にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="89adf-398">If the mailboxes have not been encrypted after a week from the time you assigned the DEP, contact Microsoft.</span></span>

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="89adf-399">Office 365: SharePoint Online、OneDrive for Business、および Teams ファイルの顧客キーの設定</span><span class="sxs-lookup"><span data-stu-id="89adf-399">Office 365: Setting up Customer Key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="89adf-400">開始する前に、Azure Key Vault をセットアップするために必要なタスクを完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="89adf-400">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="89adf-401">詳細については [、「Azure Key Vault でタスクを完了する」および「Microsoft FastTrack For Customer key](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89adf-401">See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) for information.</span></span>
  
<span data-ttu-id="89adf-402">SharePoint Online、OneDrive for Business、および Teams ファイル用の顧客キーを設定するには、Windows PowerShell を使用して SharePoint Online にリモートで接続することにより、これらの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89adf-402">To set up Customer Key for SharePoint Online, OneDrive for Business, and Teams files you will need to perform these steps by remotely connecting to SharePoint Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a><span data-ttu-id="89adf-403">SharePoint Online と OneDrive for business の各 geo にデータ暗号化ポリシー (DEP) を作成する</span><span class="sxs-lookup"><span data-stu-id="89adf-403">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>

<span data-ttu-id="89adf-404">DEP は、Azure Key Vault に格納されているキーのセットに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="89adf-404">You associate a DEP with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="89adf-405">1つの地理的な場所 (geo とも呼ばれます) 内のすべてのデータに DEP を適用します。</span><span class="sxs-lookup"><span data-stu-id="89adf-405">You apply a DEP to all of your data in one geographic location, also called a geo.</span></span> <span data-ttu-id="89adf-406">Office 365 の複数地域機能を使用する場合は、geo ごとに1つの DEP を作成して、各 geo ごとに異なるキーを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="89adf-406">If you use the multi-geo feature of Office 365, you can create one DEP per geo with the capability to use different keys per geo.</span></span> <span data-ttu-id="89adf-407">複数地域を使用していない場合は、SharePoint Online、OneDrive for Business、および Teams の各ファイルで使用するために、組織内に1人の DEP を作成できます。</span><span class="sxs-lookup"><span data-stu-id="89adf-407">If you are not using multi-geo, you can create one DEP in your organization for use with SharePoint Online, OneDrive for Business, and Teams files.</span></span> <span data-ttu-id="89adf-408">Microsoft 365 は、DEP で識別されたキーを使用して、その地域のデータを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="89adf-408">Microsoft 365 uses the keys identified in the DEP to encrypt your data in that geo.</span></span> <span data-ttu-id="89adf-409">DEP を作成するには、前の手順で取得したキーの資格情報 Uri が必要です。</span><span class="sxs-lookup"><span data-stu-id="89adf-409">To create the DEP, you need the Key Vault URIs you obtained earlier.</span></span> <span data-ttu-id="89adf-410">手順については [、「Azure Key Vault キーごとに URI を取得](#obtain-the-uri-for-each-azure-key-vault-key) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89adf-410">See [Obtain the URI for each Azure Key Vault key](#obtain-the-uri-for-each-azure-key-vault-key) for instructions.</span></span>
  
<span data-ttu-id="89adf-411">念頭!</span><span class="sxs-lookup"><span data-stu-id="89adf-411">Remember!</span></span> <span data-ttu-id="89adf-412">DEP を作成するときには、2つの異なる Azure キーボルトに存在する2つのキーを指定します。</span><span class="sxs-lookup"><span data-stu-id="89adf-412">When you create a DEP, you specify two keys that reside in two different Azure Key Vaults.</span></span> <span data-ttu-id="89adf-413">これらのキーが、地理的冗長性を確保するために2つの独立した Azure 領域に配置されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="89adf-413">Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="89adf-414">DEP を作成するには、Windows PowerShell を使用して SharePoint Online にリモートで接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89adf-414">To create a DEP, you need to remotely connect to SharePoint Online by using Windows PowerShell.</span></span>
  
1. <span data-ttu-id="89adf-415">ローカルコンピューターで、組織内のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、 [SharePoint Online Powershell に接続](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)します。</span><span class="sxs-lookup"><span data-stu-id="89adf-415">On your local computer, using a work or school account that has global administrator permissions in your organization, [Connect to SharePoint Online Powershell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

2. <span data-ttu-id="89adf-416">Microsoft SharePoint Online 管理シェルで、Get-spodataencryptionpolicy コマンドレットを次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="89adf-416">In the Microsoft SharePoint Online Management Shell, run the Register-SPODataEncryptionPolicy cmdlet as follows:</span></span>

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   <span data-ttu-id="89adf-417">DEP を登録すると、暗号化は geo のデータに対して開始されます。</span><span class="sxs-lookup"><span data-stu-id="89adf-417">When you register the DEP, encryption begins on the data in the geo.</span></span> <span data-ttu-id="89adf-418">これには、しばらく時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="89adf-418">This can take some time.</span></span>

### <a name="validate-file-encryption"></a><span data-ttu-id="89adf-419">ファイルの暗号化を検証する</span><span class="sxs-lookup"><span data-stu-id="89adf-419">Validate file encryption</span></span>

 <span data-ttu-id="89adf-420">SharePoint Online、OneDrive for Business、および Teams ファイルの暗号化を検証するには、 [Sharepoint Online PowerShell に接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)し、get-spodataencryptionpolicy コマンドレットを使用してテナントの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="89adf-420">To validate encryption of SharePoint Online, OneDrive for Business, and Teams files, [connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps), and then use the Get-SPODataEncryptionPolicy cmdlet to check the status of your tenant.</span></span> <span data-ttu-id="89adf-421">Customer キーの暗号化が有効になっており、すべてのサイトのすべてのファイルが暗号化されている場合、 _State_ プロパティは、 **登録** された値を返します。</span><span class="sxs-lookup"><span data-stu-id="89adf-421">The _State_ property returns a value of **registered** if Customer Key encryption is enabled and all files in all sites have been encrypted.</span></span> <span data-ttu-id="89adf-422">暗号化がまだ実行中の場合、このコマンドレットは、完了したサイトの割合に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="89adf-422">If encryption is still in progress, this cmdlet provides information on what percentage of sites is complete.</span></span>

## <a name="related-articles"></a><span data-ttu-id="89adf-423">関連記事</span><span class="sxs-lookup"><span data-stu-id="89adf-423">Related articles</span></span>

- [<span data-ttu-id="89adf-424">カスタマー キーによるサービスの暗号化</span><span class="sxs-lookup"><span data-stu-id="89adf-424">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="89adf-425">顧客キーを管理する</span><span class="sxs-lookup"><span data-stu-id="89adf-425">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="89adf-426">カスタマー キーまたは可用性キーをローリングまたはローテーションする</span><span class="sxs-lookup"><span data-stu-id="89adf-426">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="89adf-427">可用性キーについて</span><span class="sxs-lookup"><span data-stu-id="89adf-427">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="89adf-428">サービス暗号化</span><span class="sxs-lookup"><span data-stu-id="89adf-428">Service Encryption</span></span>](office-365-service-encryption.md)
