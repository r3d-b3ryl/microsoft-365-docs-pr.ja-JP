---
title: 顧客キーの設定
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
description: Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business、および Teams のファイルに Microsoft 365 のカスタマー キーをセットアップする方法について説明します。
ms.openlocfilehash: 87c18c1695d2963fc8a0c064d34d2b6cdc14199c
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845835"
---
# <a name="set-up-customer-key"></a><span data-ttu-id="c3eff-103">顧客キーの設定</span><span class="sxs-lookup"><span data-stu-id="c3eff-103">Set up Customer Key</span></span>

<span data-ttu-id="c3eff-104">顧客キーを使用すると、組織の暗号化キーを制御し、Microsoft のデータ センターに保存中のデータを暗号化するためにその暗号化キーを使用する Microsoft 365 を構成できます。</span><span class="sxs-lookup"><span data-stu-id="c3eff-104">With Customer Key, you control your organization's encryption keys and then configure Microsoft 365 to use them to encrypt your data at rest in Microsoft's data centers.</span></span> <span data-ttu-id="c3eff-105">つまり、顧客キーを使用すると、顧客キーを使用して、ユーザーは属している暗号化のレイヤーをキーと共に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="c3eff-105">In other words, Customer Key allows customers to add a layer of encryption that belongs to them, with their keys.</span></span> <span data-ttu-id="c3eff-106">保存データには、メールボックスに保存されている Exchange Online および Skype for Business からのデータと、SharePoint Online および OneDrive for Business に保存されているファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c3eff-106">Data at rest includes data from Exchange Online and Skype for Business that is stored in mailboxes and files that are stored in SharePoint Online and OneDrive for Business.</span></span>

<span data-ttu-id="c3eff-107">顧客キーを 365 の顧客キーを使用する前に、Azure Officeがあります。</span><span class="sxs-lookup"><span data-stu-id="c3eff-107">You must set up Azure before you can use Customer Key for Office 365.</span></span> <span data-ttu-id="c3eff-108">このトピックでは、必要な Azure リソースを作成して構成するために必要な手順について説明し、Office 365 の顧客キーをセットアップする手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-108">This topic describes the steps you need to follow to create and configure the required Azure resources and then provides the steps for setting up Customer Key in Office 365.</span></span> <span data-ttu-id="c3eff-109">Azure のセットアップを完了すると、組織内のメールボックスとファイルに割り当てるポリシーとそのキーを確認します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-109">After you have completed Azure setup, you determine which policy, and therefore, which keys, to assign to mailboxes and files in your organization.</span></span> <span data-ttu-id="c3eff-110">ポリシーを割り当てないメールボックスおよびファイルは、Microsoft により制御され管理される暗号化ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-110">Mailboxes and files for which you don't assign a policy will use encryption policies that are controlled and managed by Microsoft.</span></span> <span data-ttu-id="c3eff-111">顧客キーまたは一般的な概要については、「顧客キーによるサービスの暗号化 [」(Officeを参照してください](customer-key-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c3eff-111">For more information about Customer Key, or for a general overview, see [Service encryption with Customer Key in Office 365](customer-key-overview.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c3eff-112">このトピックのベスト プラクティスに従うことを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c3eff-112">We strongly recommend that you follow the best practices in this topic.</span></span> <span data-ttu-id="c3eff-113">これらはヒントと重要**と呼\*\*\*\*ばれれれです**。</span><span class="sxs-lookup"><span data-stu-id="c3eff-113">These are called out as **TIP** and **IMPORTANT**.</span></span> <span data-ttu-id="c3eff-114">顧客キーを使用すると、スコープを組織全体の大きくすることができます、ルート暗号化キーを制御できます。</span><span class="sxs-lookup"><span data-stu-id="c3eff-114">Customer Key gives you control over root encryption keys whose scope can be as large as your entire organization.</span></span> <span data-ttu-id="c3eff-115">つまり、これらのキーを使った間間の悪い影響は、広範な影響を与える可能性があるため、サービスが中断したり、データの取り戻しもしなおになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c3eff-115">This means that mistakes made with these keys can have a broad impact and may result in service interruptions or irrevocable loss of your data.</span></span>
  
## <a name="before-you-set-up-customer-key"></a><span data-ttu-id="c3eff-116">顧客キーを設定する前に</span><span class="sxs-lookup"><span data-stu-id="c3eff-116">Before you set up Customer Key</span></span>

<span data-ttu-id="c3eff-117">開始する前に、組織に適したライセンスが設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c3eff-117">Before you get started, ensure that you have the appropriate licensing for your organization.</span></span> <span data-ttu-id="c3eff-118">Microsoft 365 のカスタマー キーは、Office 365 E5 または高度な Compliance SKU で提供されています。</span><span class="sxs-lookup"><span data-stu-id="c3eff-118">Customer Key in Microsoft 365 is offered in Office 365 E5 or the Advanced Compliance SKU.</span></span> <span data-ttu-id="c3eff-119">このトピックの概念と手順を理解するには [、Azure Key Vault のドキュメントを確認](https://docs.microsoft.com/azure/key-vault/) してください。</span><span class="sxs-lookup"><span data-stu-id="c3eff-119">To understand the concepts and procedures in this topic, review the [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/) documentation.</span></span> <span data-ttu-id="c3eff-120">また、テナントなど、Azure で使用されている用語についても理解 [しておきましょう](https://docs.microsoft.com/previous-versions/azure/azure-services/jj573650(v=azure.100))。</span><span class="sxs-lookup"><span data-stu-id="c3eff-120">Also, become familiar with the terms used in Azure, for example, [tenant](https://docs.microsoft.com/previous-versions/azure/azure-services/jj573650(v=azure.100)).</span></span>

<span data-ttu-id="c3eff-121">FastTrack は、カスタマー キーの登録に使用される必要なテナントとサービス構成情報を収集するためにのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="c3eff-121">FastTrack is only used to collect the required tenant and service configuration information used to register for Customer Key.</span></span> <span data-ttu-id="c3eff-122">カスタマー キー オファーは FastTrack を介して公開されるため、お客様およびパートナーは同じ方法で必要な情報を送信しに使います。</span><span class="sxs-lookup"><span data-stu-id="c3eff-122">The Customer Key Offers are published via FastTrack so that it is convenient for you and our partners to submit the required information using the same method.</span></span> <span data-ttu-id="c3eff-123">FastTrack を使用すると、提供されたデータを容易にプランにアーカイブできます。</span><span class="sxs-lookup"><span data-stu-id="c3eff-123">FastTrack also makes it easy to archive the data that you provide in the Offer.</span></span>
  
<span data-ttu-id="c3eff-124">ドキュメントを追加購入する必要がある場合は、Microsoft Consulting Services (MCS)、プレミア フィールド エンジニアリング (PFE)、または Microsoft パートナーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="c3eff-124">If you need additional support beyond the documentation, contact Microsoft Consulting Services (MCS), Premier Field Engineering (PFE), or a Microsoft partner for assistance.</span></span> <span data-ttu-id="c3eff-125">ドキュメントなど、顧客キーに関するフィードバックを提供するには、アイデア、提案、およびドキュメントに視点customerkeyfeedback@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="c3eff-125">To provide feedback on Customer Key, including the documentation, send your ideas, suggestions, and perspectives to customerkeyfeedback@microsoft.com.</span></span>
  
## <a name="overview-of-steps-to-set-up-customer-key"></a><span data-ttu-id="c3eff-126">顧客キーの設定手順の概要</span><span class="sxs-lookup"><span data-stu-id="c3eff-126">Overview of steps to set up Customer Key</span></span>

<span data-ttu-id="c3eff-127">顧客キーを設定するには、これらのタスクを一覧された順番で実行します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-127">To set up Customer Key, complete these tasks in the listed order.</span></span> <span data-ttu-id="c3eff-128">この記事の残りの部分では、各タスクの詳細な手順を示したり、プロセスの各手順に関する詳細な情報へのリンクを示したりします。</span><span class="sxs-lookup"><span data-stu-id="c3eff-128">The rest of this article provides detailed instructions for each task, or links out to more information for each step in the process.</span></span>
  
<span data-ttu-id="c3eff-129">**Azure および Microsoft FastTrack 内:**</span><span class="sxs-lookup"><span data-stu-id="c3eff-129">**In Azure and Microsoft FastTrack:**</span></span>
  
<span data-ttu-id="c3eff-130">ここに示すタスクの大部分は、Azure PowerShell にリモートで接続して完了します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-130">You will complete most of these tasks by remotely connecting to Azure PowerShell.</span></span> <span data-ttu-id="c3eff-131">最良の結果を返すには、Azure PowerShell のバージョン 4.4.0 以降を使用してください。</span><span class="sxs-lookup"><span data-stu-id="c3eff-131">For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>
  
- [<span data-ttu-id="c3eff-132">2 つの新しい Azure サブスクリプションを作成する</span><span class="sxs-lookup"><span data-stu-id="c3eff-132">Create two new Azure subscriptions</span></span>](#create-two-new-azure-subscriptions)

- [<span data-ttu-id="c3eff-133">必須の保持期間を使用するために Azure サブスクリプションを登録する</span><span class="sxs-lookup"><span data-stu-id="c3eff-133">Register Azure subscriptions to use a mandatory retention period</span></span>](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  <span data-ttu-id="c3eff-134">登録には、1 から 5 名の業日をかかります。</span><span class="sxs-lookup"><span data-stu-id="c3eff-134">Registration can take from one to five business days.</span></span>

- [<span data-ttu-id="c3eff-135">顧客キーをアクティブ化する要求を、65 日Office送信する</span><span class="sxs-lookup"><span data-stu-id="c3eff-135">Submit a request to activate Customer Key for Office 365</span></span>](#submit-a-request-to-activate-customer-key-for-office-365)

<span data-ttu-id="c3eff-136">2 つの新しい Azure サブスクリプションを作成したら、Microsoft FastTrack ポータルでホストされる Web フォームを入力して、適切なカスタマー キー オファー要求を提出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3eff-136">Once you've created the two new Azure subscriptions, you'll need to submit the appropriate Customer Key offer request by completing a web form that is hosted in the Microsoft FastTrack portal.</span></span> <span data-ttu-id="c3eff-137">**FastTrack チームはカスタマー キーのサポートを提供していません。Office、FastTrack ポータルを使用するだけでフォームを送信できるようになると、カスタマー キーの関連オファーの追跡に役立ちます**。</span><span class="sxs-lookup"><span data-stu-id="c3eff-137">**The FastTrack team doesn't provide assistance with Customer Key. Office simply uses the FastTrack portal to allow you to submit the form and to help us track the relevant offers for Customer Key**.</span></span>

- [<span data-ttu-id="c3eff-138">各サブスクリプションにプレミアム Azure Key Vault を作成する</span><span class="sxs-lookup"><span data-stu-id="c3eff-138">Create a premium Azure Key Vault in each subscription</span></span>](#create-a-premium-azure-key-vault-in-each-subscription)

- [<span data-ttu-id="c3eff-139">それぞれの主要なキーが含含けたユーザーにアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="c3eff-139">Assign permissions to each key vault</span></span>](#assign-permissions-to-each-key-vault)

- [<span data-ttu-id="c3eff-140">Key Vaults で soft 削除を有効にしてから確認する</span><span class="sxs-lookup"><span data-stu-id="c3eff-140">Enable and then confirm soft delete on your key vaults</span></span>](#enable-and-then-confirm-soft-delete-on-your-key-vaults)

- [<span data-ttu-id="c3eff-141">キーを作成またはインポートして各キー インベールにキーを追加する</span><span class="sxs-lookup"><span data-stu-id="c3eff-141">Add a key to each key vault either by creating or importing a key</span></span>](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [<span data-ttu-id="c3eff-142">キーの回復レベルを確認する</span><span class="sxs-lookup"><span data-stu-id="c3eff-142">Check the recovery level of your keys</span></span>](#check-the-recovery-level-of-your-keys)

- [<span data-ttu-id="c3eff-143">Azure Key Vault のバックアップ</span><span class="sxs-lookup"><span data-stu-id="c3eff-143">Back up Azure Key Vault</span></span>](#back-up-azure-key-vault)

- [<span data-ttu-id="c3eff-144">Azure Key Vault 構成設定の検証</span><span class="sxs-lookup"><span data-stu-id="c3eff-144">Validate Azure Key Vault configuration settings</span></span>](#validate-azure-key-vault-configuration-settings)

- [<span data-ttu-id="c3eff-145">各 Azure Key Vault キーの URI を取得する</span><span class="sxs-lookup"><span data-stu-id="c3eff-145">Obtain the URI for each Azure Key Vault key</span></span>](#obtain-the-uri-for-each-azure-key-vault-key)

<span data-ttu-id="c3eff-146">**Office 365:**</span><span class="sxs-lookup"><span data-stu-id="c3eff-146">**In Office 365:**</span></span>
  
<span data-ttu-id="c3eff-147">Exchange Online と Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="c3eff-147">Exchange Online and Skype for Business:</span></span>
  
- [<span data-ttu-id="c3eff-148">Exchange Online および Skype for Business で使用するためのデータ暗号化ポリシー (DEP) を作成する</span><span class="sxs-lookup"><span data-stu-id="c3eff-148">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>](#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)

- [<span data-ttu-id="c3eff-149">DEP をメールボックスに割り当てる</span><span class="sxs-lookup"><span data-stu-id="c3eff-149">Assign a DEP to a mailbox</span></span>](#assign-a-dep-to-a-mailbox)

- [<span data-ttu-id="c3eff-150">メールボックスの暗号化の検証</span><span class="sxs-lookup"><span data-stu-id="c3eff-150">Validate mailbox encryption</span></span>](#validate-mailbox-encryption)

<span data-ttu-id="c3eff-151">SharePoint Online と OneDrive for Business:</span><span class="sxs-lookup"><span data-stu-id="c3eff-151">SharePoint Online and OneDrive for Business:</span></span>
  
- [<span data-ttu-id="c3eff-152">SharePoint Online および OneDrive for Business の地域ごとにデータの暗号化ポリシー (DEP) を作成する</span><span class="sxs-lookup"><span data-stu-id="c3eff-152">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>](#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)

- [<span data-ttu-id="c3eff-153">SharePoint Online、OneDrive for Business、および Teams のファイルの暗号化を検証する</span><span class="sxs-lookup"><span data-stu-id="c3eff-153">Validate file encryption for SharePoint Online, OneDrive for Business, and Teams files</span></span>](#validate-file-encryption)

## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a><span data-ttu-id="c3eff-154">顧客キー用の Azure Key Vault と Microsoft FastTrack 内のタスクを完了する</span><span class="sxs-lookup"><span data-stu-id="c3eff-154">Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key</span></span>

<span data-ttu-id="c3eff-155">Azure Key Vault でこれらのタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-155">Complete these tasks in Azure Key Vault.</span></span> <span data-ttu-id="c3eff-156">Exchange Online および Skype for Business 向け、または SharePoint Online、OneDrive for Business、Teams ファイル用のカスタマー キーをセットアップするのか、または Office 365 でサポートされているサービスのいずれに対してカスタマー キーをセットアップするのかに関係なく、これらの手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3eff-156">You will need to complete these steps regardless of whether you intend to set up Customer Key for Exchange Online and Skype for Business or for SharePoint Online, OneDrive for Business, and Teams files, or for all supported services in Office 365.</span></span>
  
### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="c3eff-157">2 つの新しい Azure サブスクリプションを作成する</span><span class="sxs-lookup"><span data-stu-id="c3eff-157">Create two new Azure subscriptions</span></span>

<span data-ttu-id="c3eff-158">カスタマー キーには 2 つの Azure サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="c3eff-158">Customer Key requires two Azure subscriptions.</span></span> <span data-ttu-id="c3eff-159">ベスト プラクティスとして、カスタマー キーと使用する新しい Azure サブスクリプションを作成するのが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="c3eff-159">As a best practice, Microsoft recommends that you create new Azure subscriptions for use with Customer Key.</span></span> <span data-ttu-id="c3eff-160">Azure Key Vault Keys は、同じ Azure Active Directory (AAD) テナントのアプリケーションに対してのみ承認可能です。DEP を割り当てる組織で使うものと同じ Azure AD テナントを使用して新しいサブスクリプションを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3eff-160">Azure Key Vault keys can only be authorized for applications in the same Azure Active Directory (AAD) tenant, you must create the new subscriptions using the same Azure AD tenant used with your organization where the DEPs will be assigned.</span></span> <span data-ttu-id="c3eff-161">たとえば、組織のグローバル管理者特権を持つ職場または学校のアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-161">For example, using your work or school account that has global administrator privileges in your organization.</span></span> <span data-ttu-id="c3eff-162">詳細な手順については、組織 [としての Azure 用登録に関するページをご覧ください](https://azure.microsoft.com/documentation/articles/sign-up-organization/)。</span><span class="sxs-lookup"><span data-stu-id="c3eff-162">For detailed steps, see [Sign up for Azure as an organization](https://azure.microsoft.com/documentation/articles/sign-up-organization/).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c3eff-163">顧客キーには、データの暗号化ポリシー (DEP) ごとに 2 つのキーが必要です。</span><span class="sxs-lookup"><span data-stu-id="c3eff-163">Customer Key requires two keys for each data encryption policy (DEP).</span></span> <span data-ttu-id="c3eff-164">これを実現するには、2 つの Azure サブスクリプションを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3eff-164">In order to achieve this, you must create two Azure subscriptions.</span></span> <span data-ttu-id="c3eff-165">ベスト プラクティスとして、サブスクリプションごとに 1 つのキーを組織のメンバーに個別に構成するのがベスト プラクティスです。</span><span class="sxs-lookup"><span data-stu-id="c3eff-165">As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription.</span></span> <span data-ttu-id="c3eff-166">また、これらの Azure サブスクリプションは、現在のアプリケーションの暗号化キーを管理する場合Officeしてください。</span><span class="sxs-lookup"><span data-stu-id="c3eff-166">In addition, these Azure subscriptions should only be used to administer encryption keys for Office 365.</span></span> <span data-ttu-id="c3eff-167">これは、オペレーターの 1 つが意図的に削除したり、悪意をとって削除したり、責を必要とするキーを不正に削除したりした場合に組織を保護します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-167">This protects your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible.</span></span> <br/> <span data-ttu-id="c3eff-168">新しい Azure サブスクリプションを設定する場合、Azure Key Vault リソースの管理に関して、顧客キーと共に使用するのみで使用する新しい Azure サブスクリプションを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3eff-168">We recommend that you set up new Azure subscriptions that are solely used for managing Azure Key Vault resources for use with Customer Key.</span></span> <span data-ttu-id="c3eff-169">組織用に作成できる Azure サブスクリプションの数に対する実用的な制限はありません。</span><span class="sxs-lookup"><span data-stu-id="c3eff-169">There is no practical limit to the number of Azure subscriptions that you can create for your organization.</span></span> <span data-ttu-id="c3eff-170">これらのベスト プラクティスに従うと、顧客キーで使用されるリソースを管理しながら、人的エラーによる影響を最小限に抑えます。</span><span class="sxs-lookup"><span data-stu-id="c3eff-170">Following these best practices will minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span>
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a><span data-ttu-id="c3eff-171">顧客キーをアクティブ化する要求を、65 日Office送信する</span><span class="sxs-lookup"><span data-stu-id="c3eff-171">Submit a request to activate Customer Key for Office 365</span></span>

<span data-ttu-id="c3eff-172">Azure の手順を完了したら [、Microsoft FastTrack](https://fasttrack.microsoft.com/)ポータルでプラン要求を提出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3eff-172">Once you've completed the Azure steps, you'll need to submit an offer request in the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span> <span data-ttu-id="c3eff-173">FastTrack Web ポータルから要求を送信すると、Microsoft は Azure Key Vault 構成データと入力した連絡先情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-173">Once you have submitted a request through the FastTrack web portal, Microsoft verifies the Azure Key Vault configuration data and contact information you provided.</span></span> <span data-ttu-id="c3eff-174">組織の承認されているオファーに関するプラン形式での選択は重要で、カスタマー キーの登録を完了するために必要なものが重要です。</span><span class="sxs-lookup"><span data-stu-id="c3eff-174">The selections that you make in the offer form regarding the authorized officers of your organization is critical and necessary for completion of Customer Key registration.</span></span> <span data-ttu-id="c3eff-175">フォームで選択した組織のオフイスは、顧客キー データの暗号化ポリシーで使用されるすべてのキーの取り消し要求の信頼性を確認するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c3eff-175">The officers of your organization that you select in the form will be the used to ensure the authenticity of any request to revoke and destroy all keys used with a Customer Key data encryption policy.</span></span> <span data-ttu-id="c3eff-176">このステップでは、Exchange Online および Skype for Business のカスタマー キーをアクティブ化し、SharePoint Online および OneDrive for Business の顧客キーをアクティブ化するために、2 回目の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3eff-176">You'll need to do this step once to activate Customer Key for Exchange Online and Skype for Business coverage and a second time to activate Customer Key for SharePoint Online and OneDrive for Business.</span></span>
  
<span data-ttu-id="c3eff-177">顧客キーをアクタクト化するためにオファーを提出するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-177">To submit an offer to activate Customer Key, complete these steps:</span></span>
  
1. <span data-ttu-id="c3eff-178">組織のグローバル管理者権限を持つ職場または学校のアカウントを使用して [、Microsoft FastTrack ポータルにログインします](https://fasttrack.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="c3eff-178">Using a work or school account that has global administrator permissions in your organization, log in to the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span>

2. <span data-ttu-id="c3eff-179">ログインした後、ダッシュボードを参照 **します**。</span><span class="sxs-lookup"><span data-stu-id="c3eff-179">Once you're logged in, browse to the **Dashboard**.</span></span>

3. <span data-ttu-id="c3eff-180">ナビゲーション **バーから** [展開] を選 **むか、展開** 情報 **カードで [** 展開用リソース **を** すべて表示] を選び、現在のプランの一覧を確認します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-180">Choose **Deploy** from the navigation bar **OR** select **View all deployment resources** on the **Deploy** information card, and review the list of current offers.</span></span>

4. <span data-ttu-id="c3eff-181">適用するプランの情報カードを選択します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-181">Choose the information card for the offer that applies to you:</span></span>

   - <span data-ttu-id="c3eff-182">**Exchange Online と Skype for Business:** Exchange Online **プランの [暗号化を要求する] ヘルプを選択** します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-182">**Exchange Online and Skype for Business:** Choose the **Request encryption key help for Exchange online** offer.</span></span>

   - <span data-ttu-id="c3eff-183">**SharePoint Online、OneDrive、および Teams のファイル:\*\*\*\*SharePoint と OneDrive オファーに対する [要求暗号化キーのヘルプ] を選択**します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-183">**SharePoint Online, OneDrive, and Teams files:** Choose the **Request encryption key help for Sharepoint and OneDrive** offer.</span></span>

5. <span data-ttu-id="c3eff-184">プランの詳細を確認したら、[続行] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="c3eff-184">Once you've reviewed the offer details, choose **Continue to step 2**.</span></span>

6. <span data-ttu-id="c3eff-185">該当する詳細情報や要求された情報をすべてプラン フォームに入力します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-185">Fill out all applicable details and requested information on the offer form.</span></span> <span data-ttu-id="c3eff-186">暗号化キーやデータの完全および元に戻す破損を承認する必要がある組織のユーザーが選択内容を特に注意しておき、注意してください。</span><span class="sxs-lookup"><span data-stu-id="c3eff-186">Pay particular attention to your selections for which officers of your organization you want to authorize to approve the permanent and irreversible destruction of encryption keys and data.</span></span> <span data-ttu-id="c3eff-187">フォームが完成したら、[送信] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="c3eff-187">Once you've completed the form, choose **Submit**.</span></span>

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="c3eff-188">必須の保持期間を使用するために Azure サブスクリプションを登録する</span><span class="sxs-lookup"><span data-stu-id="c3eff-188">Register Azure subscriptions to use a mandatory retention period</span></span>

<span data-ttu-id="c3eff-189">ルート暗号化キーの一時的なまたは完全な切り損失は、サービスの操作に大きな破壊的な場合があります。その結果、データが失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c3eff-189">The temporary or permanent loss of root encryption keys can be very disruptive or even catastrophic to service operation and can result in data loss.</span></span> <span data-ttu-id="c3eff-190">このため、顧客キーと使用されるリソースでは強力な保護が必要です。</span><span class="sxs-lookup"><span data-stu-id="c3eff-190">For this reason, the resources used with Customer Key require strong protection.</span></span> <span data-ttu-id="c3eff-191">カスタマー キーと共に使うすべての Azure リソースは、既定の構成を上書きする保護メカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-191">All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration.</span></span> <span data-ttu-id="c3eff-192">Azure サブスクリプションにタグを付けたり登録したりすることができます。このようにすると、即時にキャンセルできない取り消しを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="c3eff-192">Azure subscriptions can be tagged or registered in a way that will prevent immediate and irrevocable cancellation.</span></span> <span data-ttu-id="c3eff-193">これは、必須の保持期間の登録と呼ばれることをいう。</span><span class="sxs-lookup"><span data-stu-id="c3eff-193">This is referred to as registering for a mandatory retention period.</span></span> <span data-ttu-id="c3eff-194">必須の保持期間用に Azure サブスクリプションを登録するために必要な手順では、Microsoft 365 チームとのコラボレーションが必要です。</span><span class="sxs-lookup"><span data-stu-id="c3eff-194">The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Microsoft 365 team.</span></span> <span data-ttu-id="c3eff-195">このプロセスには、1 から 5 日の間でかかります。</span><span class="sxs-lookup"><span data-stu-id="c3eff-195">This process can take from one to five business days.</span></span> <span data-ttu-id="c3eff-196">以前は、これを "取り消し不可能" と呼じことでした。</span><span class="sxs-lookup"><span data-stu-id="c3eff-196">Previously, this was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="c3eff-197">Microsoft 365 チームに問い合わせる前に、顧客キーで使用する各 Azure サブスクリプションについて、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3eff-197">Before contacting the Microsoft 365 team, you must perform the following steps for each Azure subscription that you use with Customer Key.</span></span> <span data-ttu-id="c3eff-198">開始する前に [、Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) モジュールがインストール済みです。</span><span class="sxs-lookup"><span data-stu-id="c3eff-198">Ensure that you have the [Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) module installed before you start.</span></span>
  
1. <span data-ttu-id="c3eff-199">Azure PowerShell を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="c3eff-199">Sign in with Azure PowerShell.</span></span> <span data-ttu-id="c3eff-200">手順については [、「Azure PowerShell を使用してサインインする」を参照してください](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="c3eff-200">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="c3eff-201">Register-AzProviderFeature コマンドレットを実行してサブスクリプションを登録し、必須の保持期間を使用します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-201">Run the Register-AzProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span> <span data-ttu-id="c3eff-202">サブスクリプションごとにこのアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-202">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. <span data-ttu-id="c3eff-203">プロセスの最終処理については、マイクロソフトにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="c3eff-203">Contact Microsoft to have the process finalized.</span></span> <span data-ttu-id="c3eff-204">SharePoint および OneDrive for Business チームの場合、メール アドレス [spock@microsoft.com](mailto:spock@microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="c3eff-204">For the SharePoint and OneDrive for Business team, contact [spock@microsoft.com](mailto:spock@microsoft.com).</span></span> <span data-ttu-id="c3eff-205">Exchange Online および Skype for Business の場合は、連絡先プロパティ[のexock@microsoft.com。](mailto:exock@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="c3eff-205">For Exchange Online and Skype for Business, contact [exock@microsoft.com](mailto:exock@microsoft.com).</span></span> <span data-ttu-id="c3eff-206">電子メールに次のものを含めると、以下の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3eff-206">Include the following in your email:</span></span>

   <span data-ttu-id="c3eff-207">**Subject**: Customer Key \<*Your tenant's fully-qualified domain name*\></span><span class="sxs-lookup"><span data-stu-id="c3eff-207">**Subject**: Customer Key for \<*Your tenant's fully-qualified domain name*\></span></span>

   <span data-ttu-id="c3eff-208">**本文**: 必須の保持期間を設定する必要があるサブスクリプション ID。</span><span class="sxs-lookup"><span data-stu-id="c3eff-208">**Body**: Subscription IDs for which you want to have the mandatory retention period finalized.</span></span>
   <span data-ttu-id="c3eff-209">各サブスクリプションの Get-AzProviderFeature の出力。</span><span class="sxs-lookup"><span data-stu-id="c3eff-209">The output of Get-AzProviderFeature for each subscription.</span></span>

   <span data-ttu-id="c3eff-210">Microsoft に通知 (および検証済み) がサブスクリプションの必須の保持期間を登録した後、このプロセスを完了するためのサービス レベル アグリーメント (SLA) は 5 週間になります。</span><span class="sxs-lookup"><span data-stu-id="c3eff-210">The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period.</span></span>

4. <span data-ttu-id="c3eff-211">登録が完了したことを Microsoft に通知したら、Get-AzProviderFeature コマンドを次のように実行して登録の状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-211">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzProviderFeature command as follows.</span></span> <span data-ttu-id="c3eff-212">確認すると、Get-AzProviderFeature コマンドは登録状態プロパティの **Registered** の値 **を返** します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-212">If verified, the Get-AzProviderFeature command returns a value of **Registered** for the **Registration State** property.</span></span> <span data-ttu-id="c3eff-213">サブスクリプションごとにこのアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-213">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. <span data-ttu-id="c3eff-214">処理を完了するには、Register-AzResourceProvider コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-214">To complete the process, run the Register-AzResourceProvider command.</span></span> <span data-ttu-id="c3eff-215">サブスクリプションごとにこのアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-215">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="c3eff-216">各サブスクリプションにプレミアム Azure Key Vault を作成する</span><span class="sxs-lookup"><span data-stu-id="c3eff-216">Create a premium Azure Key Vault in each subscription</span></span>

<span data-ttu-id="c3eff-217">キー コンベートを作成する手順は [、Azure Key Vault の](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)概要に説明されています。このドキュメントでは、Azure PowerShell のインストールと起動、Azure サブスクリプションへの接続、リソース グループの作成、そのリソース グループのキー バールトの作成について説明しています。</span><span class="sxs-lookup"><span data-stu-id="c3eff-217">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="c3eff-218">キー バウルトを作成するときには、Standard または Premium のどちらかの SKU を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3eff-218">When you create a key vault, you must choose a SKU: either Standard or Premium.</span></span> <span data-ttu-id="c3eff-219">標準の SKU では、Azure Key Vault キーをソフトウェアで保護することができます。ハードウェア セキュリティ モジュール (HSM) キー保護がないため、Premium SKU を使用することで Key Vault Key を保護できます。</span><span class="sxs-lookup"><span data-stu-id="c3eff-219">The Standard SKU allows Azure Key Vault keys to be protected with software - there is no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys.</span></span> <span data-ttu-id="c3eff-220">顧客キーは、どちらの SKU を使用するキー ブラルトを受け入れますが、プレミアム SKU のみを使用するを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c3eff-220">Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU.</span></span> <span data-ttu-id="c3eff-221">どちらの種類のキーを使用した操作のコストも同じなので、コストの違いは、HSM で保護された各キーに対するコストだけです。</span><span class="sxs-lookup"><span data-stu-id="c3eff-221">The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key.</span></span> <span data-ttu-id="c3eff-222">詳細 [については、「Key Vault の価格」を](https://azure.microsoft.com/pricing/details/key-vault/) 参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3eff-222">See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c3eff-223">Premium SKU キーの書き込みキーに対しては、運用環境のデータに対して Standard SKU キーのベールトおよび HSM で保護されたキーを使用し、テストと検証を目的として標準の SKU キーのベールトおよびキーのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-223">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span>
  
<span data-ttu-id="c3eff-224">顧客キーを使用する Microsoft 365 の各サービスについて、作成した 2 つの Azure サブスクリプションのそれぞれに、キー ブラルトを作成します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-224">For each Microsoft 365 service with which you will use Customer Key, create a key vault in each of the two Azure subscriptions that you created.</span></span> <span data-ttu-id="c3eff-225">たとえば、Exchange Online と Skype for Business のみ、または SharePoint Online と OneDrive for Business のみでは、1 つのキーを作成するだけで作成されます。</span><span class="sxs-lookup"><span data-stu-id="c3eff-225">For example, for Exchange Online and Skype for Business only or SharePoint Online and OneDrive for Business only, you will create only one pair of vaults.</span></span> <span data-ttu-id="c3eff-226">Exchange Online と SharePoint Online の両方に対して顧客キーを有効にするには、キー コンテナーの 2 つのペアを作成します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-226">To enable Customer Key for both Exchange Online and SharePoint Online, you will create two pairs of key vaults.</span></span>
  
<span data-ttu-id="c3eff-227">キーの読み取りに使用する、書き込み可能なキーのポリシーを使用するキー ストアには、命名規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-227">Use a naming convention for key vaults that reflects the intended use of the data encryption policy with which you will associate the vaults.</span></span> <span data-ttu-id="c3eff-228">規則に関する推奨事項については、以下のベスト プラクティスのセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3eff-228">See the Best Practices section below for naming convention recommendations.</span></span>
  
<span data-ttu-id="c3eff-229">データの暗号化ポリシーごとに、別のコンテルのセットを作成します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-229">Create a separate, paired set of vaults for each data encryption policy.</span></span> <span data-ttu-id="c3eff-230">Exchange Online では、ポリシーをメールボックスに割り当てるときにデータの暗号化ポリシーのスコープが選択されます。</span><span class="sxs-lookup"><span data-stu-id="c3eff-230">For Exchange Online, the scope of a data encryption policy is chosen by you when you assign the policy to mailbox.</span></span> <span data-ttu-id="c3eff-231">メールボックスに割り当てられるポリシーは 1 つだけで、最大 10 つのポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c3eff-231">A mailbox can have only one policy assigned, and you can create up to fifty policies.</span></span> <span data-ttu-id="c3eff-232">SharePoint Online の場合、ポリシーのスコープは、地理的な場所、または geo 内の組織内のすべてのデータ _です_。</span><span class="sxs-lookup"><span data-stu-id="c3eff-232">For SharePoint Online the scope of a policy is all of the data within an organization in a geographic location, or _geo_.</span></span>

<span data-ttu-id="c3eff-233">キー コンテナーの作成では、Azure リソース グループを作成する必要もあります。Vault は、ストレージ容量 (非常に小さい場合) と Key Vault ログが有効な場合は、保存されたデータも生成します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-233">The creation of key vaults also requires the creation of Azure resource groups, since key vaults need storage capacity (though very small) and Key Vault logging, if enabled, also generates stored data.</span></span> <span data-ttu-id="c3eff-234">ベスト プラクティスとしては、すべての関連するカスタマー キー リソースを管理する管理者のセットに合う管理方法を使用して、各リソース グループの管理に個別の管理者を使用してください。</span><span class="sxs-lookup"><span data-stu-id="c3eff-234">As a best practice Microsoft recommends using separate administrators to manage each resource group, with the administration aligned with the set of administrators that will manage all related Customer Key resources.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c3eff-235">最大限の可用性を実現するために、お使いのキー ウォールトは Microsoft 365 サービスに近い地域に収まっていないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="c3eff-235">To maximize availability, your key vaults should be in regions close to your Microsoft 365 service.</span></span> <span data-ttu-id="c3eff-236">たとえば、Exchange Online 組織が北アメリカにいなってきは、キー ブラルトを北米に配置します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-236">For example, if your Exchange Online organization is in North America, place your key vaults in North America.</span></span> <span data-ttu-id="c3eff-237">Exchange Online 組織が 3E におりかない場合は、キー ウェールテットを Europe に配置します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-237">If your Exchange Online organization is in Europe, place your key vaults in Europe.</span></span><br/><span data-ttu-id="c3eff-238">キーのバルテの共通プレフィックスを使います。 キー コンテナーとキーのキーの使用範囲 (たとえば、北米に保存される Contoso SharePoint サービスの場合、名前のペアは Contoso-O365SP-NA-VaultA1 と Contoso-O365SP-NA-VaultA2 です) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c3eff-238">Use a common prefix for key vaults, and include an abbreviation of the use and scope of the key vault and keys (e.g., for the Contoso SharePoint service where the vaults will be located in North America, a possible pair of names is Contoso-O365SP-NA-VaultA1 and Contoso-O365SP-NA-VaultA2.</span></span> <span data-ttu-id="c3eff-239">Vault 名は Azure 内でグローバルに一意の文字列であるため、必要な名前が他の Azure 顧客から既に要求されている場合に、必要な名前のバリエーションを試してみてください。</span><span class="sxs-lookup"><span data-stu-id="c3eff-239">Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers.</span></span> <span data-ttu-id="c3eff-240">2017 年 7 月のベールト名は変更できないため、ベスト プラクティスはセットアップ用の計画を作成し、2 人目の担当者を使用して計画が正しく実行することを確認することです。</span><span class="sxs-lookup"><span data-stu-id="c3eff-240">As of July 2017 vault names cannot be changed, so a best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span><br/><span data-ttu-id="c3eff-241">可能であれば、ペアリングされていない領域にあいつもお使いのブルトを作成します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-241">If possible, create your vaults in non-paired regions.</span></span> <span data-ttu-id="c3eff-242">ペアリングされた Azure 地域は、サービス障害ドメイン間の高可用性を提供します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-242">Paired Azure regions provide high availability across service failure domains.</span></span> <span data-ttu-id="c3eff-243">そのため、地域のペアは、おそらいのバックアップ地域といえます。</span><span class="sxs-lookup"><span data-stu-id="c3eff-243">Therefore, regional pairs can be thought of as each other's backup region.</span></span> <span data-ttu-id="c3eff-244">つまり、1 つの地域に配置された Azure リソースは、ペアリングされた領域を通じてフォールト トレランスを自動的に取得します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-244">This means that an Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region.</span></span> <span data-ttu-id="c3eff-245">このため、地域がペアリングされている、データの暗号化ポリシーで使用される 2 つのコンテナーの地域を選択すると、2 つの地域の合計使用地域のみが使用されていることを意味しています。</span><span class="sxs-lookup"><span data-stu-id="c3eff-245">For this reason, choosing regions for two vaults used in a data encryption policy where the regions are paired means that only a total of two regions of availability are in use.</span></span> <span data-ttu-id="c3eff-246">ほとんどの地域には 2 つの地域しかないため、ペアリングされていない地域を選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="c3eff-246">Most geographies only have two regions, so it's not yet possible to select non-paired regions.</span></span> <span data-ttu-id="c3eff-247">可能な場合は、データの暗号化ポリシーで使用される 2 つのコンテナーに対して、ペアリングされていない 2 つの地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-247">If possible, choose two non-paired regions for the two vaults used with a data encryption policy.</span></span> <span data-ttu-id="c3eff-248">この場合、可用性の合計で 4 つの領域から得できると、この利点があります。</span><span class="sxs-lookup"><span data-stu-id="c3eff-248">This benefits from a total of four regions of availability.</span></span> <span data-ttu-id="c3eff-249">詳細については、ビジネスの [連続性と障害復旧 (BCDR): 現在の](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) 地域ペアのリストのための Azure Paired Regions をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c3eff-249">For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span>
  
### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="c3eff-250">それぞれの主要なキーが含含けたユーザーにアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="c3eff-250">Assign permissions to each key vault</span></span>

<span data-ttu-id="c3eff-251">実装に応じて、キー コントラルタごとに、カスタマー キーに対して 3 つの異なるアクセス許可セットを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3eff-251">For each key vault, you will need to define three separate sets of permissions for Customer Key, depending on your implementation.</span></span> <span data-ttu-id="c3eff-252">たとえば、次のそれぞれに対して 1 セットのアクセス許可を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3eff-252">For example, you will need to define one set of permissions for each of the following:</span></span>
  
- <span data-ttu-id="c3eff-253">**組織の Key Vault** の日常的な管理を行う Key Vault 管理者。</span><span class="sxs-lookup"><span data-stu-id="c3eff-253">**Key vault administrators** that will perform day-to-day management of your key vault for your organization.</span></span> <span data-ttu-id="c3eff-254">これらのタスクには、バックアップ、作成、取得、インポート、リスト、復元が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c3eff-254">These tasks include backup, create, get, import, list, and restore.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="c3eff-255">キー を削除するためのアクセス許可は、キーを削除するために必要なアクセス許可のセットには含まれません。</span><span class="sxs-lookup"><span data-stu-id="c3eff-255">The set of permissions assigned to key vault administrators does not include the permission to delete keys.</span></span> <span data-ttu-id="c3eff-256">これは意図的な方法で、重要な方法です。</span><span class="sxs-lookup"><span data-stu-id="c3eff-256">This is intentional and an important practice.</span></span> <span data-ttu-id="c3eff-257">暗号化キーの削除は、データを完全に破破し破破し、通常は行われません。</span><span class="sxs-lookup"><span data-stu-id="c3eff-257">Deleting encryption keys is not typically done, since doing so permanently destroys data.</span></span> <span data-ttu-id="c3eff-258">ベスト プラクティスとして、既定ではキーの設定を主な管理者にこのアクセス許可を付与しないでください。</span><span class="sxs-lookup"><span data-stu-id="c3eff-258">As a best practice, do not grant this permission to key vault administrators by default.</span></span> <span data-ttu-id="c3eff-259">代わりに、キー資格情報の投稿者にこれを予約し、このことは、この後、その後、わかりやすいうえで短期的に管理者に割り当ててください。</span><span class="sxs-lookup"><span data-stu-id="c3eff-259">Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span>
  
  <span data-ttu-id="c3eff-260">これらのアクセス許可を組織内のユーザーに割り当てるには、Azure PowerShell を使って Azure サブスクリプションにログインします。</span><span class="sxs-lookup"><span data-stu-id="c3eff-260">To assign these permissions to a user in your organization, log in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="c3eff-261">手順については [、「Azure PowerShell を使用してサインインする」を参照してください](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="c3eff-261">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

- <span data-ttu-id="c3eff-262">Set-AzKeyVaultAccessPolicy コマンドレットを実行して、必要なアクセス許可を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c3eff-262">Run the Set-AzKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   <span data-ttu-id="c3eff-263">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-263">For example:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- <span data-ttu-id="c3eff-264">Azure Key **Vault 自体のアクセス許可**を変更できる Key Vault 投稿者。</span><span class="sxs-lookup"><span data-stu-id="c3eff-264">**Key vault contributors** that can change permissions on the Azure Key Vault itself.</span></span> <span data-ttu-id="c3eff-265">従業員がチームを脱退したりチームに参加したりする場合や、キーキーの削除や復元にクォールト管理者がアクセス許可をうまく必要としていない状況では、多少ない状況で変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3eff-265">You'll need to change these permissions as employees leave or join your team, or in the extremely rare situation that the key vault administrators legitimately need permission to delete or restore a key.</span></span> <span data-ttu-id="c3eff-266">キーの書き込み元のこのセットには、Key Vault の **Contributor** ロールが付与されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3eff-266">This set of key vault contributors needs to be granted the **Contributor** role on your key vault.</span></span> <span data-ttu-id="c3eff-267">Azure リソース マネージャーを使用してこのロールを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="c3eff-267">You can assign this role by using Azure Resource Manager.</span></span> <span data-ttu-id="c3eff-268">詳細な手順については、「役割ベースのアクセス [制御を使用した Azure サブスクリプション リソースへのアクセスの管理」を参照してください](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure)。</span><span class="sxs-lookup"><span data-stu-id="c3eff-268">For detailed steps, see [Use Role-Based Access Control to manage access to your Azure subscription resources](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure).</span></span> <span data-ttu-id="c3eff-269">サブスクリプションを作成する管理者には、暗黙的にこのアクセス権と、他の管理者を投稿者ロールに割り当てる機能が付与されます。</span><span class="sxs-lookup"><span data-stu-id="c3eff-269">The administrator who creates a subscription has this access implicitly, as well as the ability to assign other administrators to the Contributor role.</span></span>

- <span data-ttu-id="c3eff-270">Exchange Online と Skype for Business でカスタマー キーを使用する場合、Exchange Online と Skype for Business の代わりに主要な取り消しを使用するためのアクセス許可を Microsoft 365 に与えなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="c3eff-270">If you intend to use Customer Key with Exchange Online and Skype for Business, you need to give permission to Microsoft 365 to use the key vault on behalf of Exchange Online and Skype for Business.</span></span> <span data-ttu-id="c3eff-271">同様に、SharePoint Online と OneDrive for Business でカスタマー キーを使用する場合は、Microsoft 365 で SharePoint Online と OneDrive for Business の代わりにキー ウェールトを使用するためのアクセス許可を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3eff-271">Likewise, if you intend to use Customer Key with SharePoint Online and OneDrive for Business, you need to add permission for the Microsoft 365 to use the key vault on behalf of SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="c3eff-272">Microsoft 365 にアクセス許可を付与するには、次の **構文を使用して Set-AzKeyVaultAccessPolicy** コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-272">To give permission to Microsoft 365, run the **Set-AzKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span> 

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   <span data-ttu-id="c3eff-273">ここで、</span><span class="sxs-lookup"><span data-stu-id="c3eff-273">Where:</span></span>

    - <span data-ttu-id="c3eff-274">*Vault name* は、作成したキー フォルダーの名前です。</span><span class="sxs-lookup"><span data-stu-id="c3eff-274">*vault name* is the name of the key vault you created.</span></span>

    - <span data-ttu-id="c3eff-275">Exchange Online および Skype for Business の場合は、*アプリ ID Officeで置換*`00000002-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="c3eff-275">For Exchange Online and Skype for Business, replace  *Office 365 appID* with `00000002-0000-0ff1-ce00-000000000000`</span></span>

    - <span data-ttu-id="c3eff-276">SharePoint Online、OneDrive for Business、および Teams の各ファイルの場合 *、Office 365 アプリ ID に置き換え*`00000003-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="c3eff-276">For SharePoint Online, OneDrive for Business, and Teams files, replace  *Office 365 appID* with `00000003-0000-0ff1-ce00-000000000000`</span></span>

  <span data-ttu-id="c3eff-277">例: Exchange Online と Skype for Business のアクセス許可の設定:</span><span class="sxs-lookup"><span data-stu-id="c3eff-277">Example: Setting permissions for Exchange Online and Skype for Business:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  <span data-ttu-id="c3eff-278">例: SharePoint Online、OneDrive for Business、および Teams ファイルのアクセス許可の設定:</span><span class="sxs-lookup"><span data-stu-id="c3eff-278">Example: Setting permissions for SharePoint Online, OneDrive for Business, and Teams files:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a><span data-ttu-id="c3eff-279">Key Vaults で soft 削除を有効にしてから確認する</span><span class="sxs-lookup"><span data-stu-id="c3eff-279">Enable and then confirm soft delete on your key vaults</span></span>

<span data-ttu-id="c3eff-280">キーをすばやく回復できると、削除が終了したり、悪意によって削除されたキーが発生したりしたために、延長サービスの停止が発生する可能性は低くなります。</span><span class="sxs-lookup"><span data-stu-id="c3eff-280">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys.</span></span> <span data-ttu-id="c3eff-281">カスタマー キーでキーを使用する前に、削除削除と呼ばれるこの構成を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3eff-281">You need to enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key.</span></span> <span data-ttu-id="c3eff-282">削除後 90 日以内にキーまたは休日を復元できます。キーまたはキーをバックアップから復元する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c3eff-282">Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="c3eff-283">キー ウォールトで Soft Delete を有効にするには、次の手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-283">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="c3eff-284">Windows PowerShell を使用して Azure サブスクリプションにサインインします。</span><span class="sxs-lookup"><span data-stu-id="c3eff-284">Sign in to your Azure subscription with Windows Powershell.</span></span> <span data-ttu-id="c3eff-285">手順については [、「Azure PowerShell を使用してサインインする」を参照してください](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="c3eff-285">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="c3eff-286">[Get-AzKeyVault コマンドレットを実行](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault)します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-286">Run the [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet.</span></span> <span data-ttu-id="c3eff-287">この例では *、キー キー名* は、削除済みアイテム フォルダーへの削除を有効にしているキー バールの名前です。</span><span class="sxs-lookup"><span data-stu-id="c3eff-287">In this example, *vault name* is the name of the key vault for which you are enabling soft delete:</span></span>

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. <span data-ttu-id="c3eff-288">**Get-AzKeyVault**コマンドレットを実行して、キー ビルトに対して行う削除が構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-288">Confirm soft delete is configured for the key vault by running the **Get-AzKeyVault** cmdlet.</span></span> <span data-ttu-id="c3eff-289">キー コンテナーに対して正しく構成されている場合 _、[Soft Delete Enabled] プロパティ_ は値 True を返 **します**。</span><span class="sxs-lookup"><span data-stu-id="c3eff-289">If soft delete is configured properly for the key vault, then the _Soft Delete Enabled_ property returns a value of **True**:</span></span>

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="c3eff-290">キーを作成またはインポートして各キー インベールにキーを追加する</span><span class="sxs-lookup"><span data-stu-id="c3eff-290">Add a key to each key vault either by creating or importing a key</span></span>

<span data-ttu-id="c3eff-291">Azure Key Vault にキーを追加する方法は 2 つあります。キーをキー ブレールに直接作成するか、またはキーをインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="c3eff-291">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key.</span></span> <span data-ttu-id="c3eff-292">Key Vault で直接キーを作成するのは複雑な方法な方法なので、キーをインポートすることによって、キーの生成方法を総したコントロールを制御できます。</span><span class="sxs-lookup"><span data-stu-id="c3eff-292">Creating a key directly in Key Vault is the less complicated method, while importing a key provides total control over how the key is generated.</span></span>
  
<span data-ttu-id="c3eff-293">キー キーを直接作成するには、次のように [Add-AzKeyVaultKey コマンドレット](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) を実行します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-293">To create a key directly in your key vault, run the [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="c3eff-294">ここで、</span><span class="sxs-lookup"><span data-stu-id="c3eff-294">Where:</span></span>

- <span data-ttu-id="c3eff-295">*Vault 名* は、キーを作成するキー キーの名前です。</span><span class="sxs-lookup"><span data-stu-id="c3eff-295">*vault name* is the name of the key vault in which you want to create the key.</span></span>

- <span data-ttu-id="c3eff-296">*key name* is the name you want to give the new key.</span><span class="sxs-lookup"><span data-stu-id="c3eff-296">*key name* is the name you want to give the new key.</span></span>

  > [!TIP]
  > <span data-ttu-id="c3eff-297">前述のように、キーに似命名規則を使った名前キーを使います。</span><span class="sxs-lookup"><span data-stu-id="c3eff-297">Name keys using a similar naming convention as described above for key vaults.</span></span> <span data-ttu-id="c3eff-298">これにより、キー名だけが表示されるツールで文字列を説明します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-298">This way, in tools that show only the key name, the string is self-describing.</span></span>
  
- <span data-ttu-id="c3eff-299">HSM でキーを保護する場合は _、Destination_パラメーターの値として**HSM**を指定し、指定しない場合は Software を指定**してください**。</span><span class="sxs-lookup"><span data-stu-id="c3eff-299">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the _Destination_ parameter, otherwise, specify **Software**.</span></span>

<span data-ttu-id="c3eff-300">例えば、</span><span class="sxs-lookup"><span data-stu-id="c3eff-300">For example,</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="c3eff-301">キー バルテに直接キーをインポートするには、nCipher nShield ハードウェア セキュリティ モジュールが必要です。</span><span class="sxs-lookup"><span data-stu-id="c3eff-301">To import a key directly into your key vault, you need to have a nCipher nShield Hardware Security Module.</span></span>
  
<span data-ttu-id="c3eff-302">組織によっては、キーの証明を確立するためにこの方法を使用している場合もあるので、この方法で次の機能も提供します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-302">Some organizations prefer this approach to establish the provenance of their keys, and then this method also provides the following:</span></span>
  
- <span data-ttu-id="c3eff-303">インポートに使うツールセットには、生成するキーを暗号化するために使用されるキー交換キー (KEK) はエクスポート不可能で、nCipher によって製造された正当な HSM 内部に生成された nCipher からの証明が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c3eff-303">The toolset used for import includes attestation from nCipher that the Key Exchange Key (KEK) that is used to encrypt the key you generate is not exportable and is generated inside a genuine HSM that was manufactured by nCipher.</span></span>

- <span data-ttu-id="c3eff-304">nCipher が製造した Genuine HSM 製造上でも Azure Key Vault のセキュリティの世界で生成された nCipher からの構成証明が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c3eff-304">The toolset includes attestation from nCipher that the Azure Key Vault security world was also generated on a genuine HSM manufactured by nCipher.</span></span> <span data-ttu-id="c3eff-305">この構成証明は、Microsoft がジェネレーター ハードウェアも使用しているかどうかを証明します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-305">This attestation proves to you that Microsoft is also using genuine nCipher hardware.</span></span>

<span data-ttu-id="c3eff-306">セキュリティ グループに確認し、上記の構成証明が必要かどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c3eff-306">Check with your security group to determine if the above attestations are required.</span></span> <span data-ttu-id="c3eff-307">オンプレミスでキーを作成し、キー バルテにインポートする詳細な手順については、Azure Key Vault の HSM で保護されたキーを生成し [転送する方法を参照してください](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/)。</span><span class="sxs-lookup"><span data-stu-id="c3eff-307">For detailed steps to create a key on-premises and import it into your key vault, see [How to generate and transfer HSM-protected keys for Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/).</span></span> <span data-ttu-id="c3eff-308">Azure の手順を使用して、各キー ブォールトにキーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-308">Use the Azure instructions to create a key in each key vault.</span></span>
  
### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="c3eff-309">キーの回復レベルを確認する</span><span class="sxs-lookup"><span data-stu-id="c3eff-309">Check the recovery level of your keys</span></span>

<span data-ttu-id="c3eff-310">Microsoft 365 では、Azure Key Vault サブスクリプションが [取り消し不可能] に設定され、Customer Key が使うキーで削除済みアイテムへの削除が有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3eff-310">Microsoft 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled.</span></span> <span data-ttu-id="c3eff-311">キーの回復レベルを確認するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c3eff-311">You can confirm this by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="c3eff-312">キーの回復レベルを確認するには、Azure PowerShell で Get-AzKeyVaultKey コマンドレットを以下のように実行します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-312">To check the recovery level of a key, in Azure PowerShell, run the Get-AzKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

<span data-ttu-id="c3eff-313">回復レベル _のプロパティが_ **Recoverable + ProtectedSubscription**の値以外の値を返す場合は、このトピックを確認した後、サブスクリプションを [キャンセルしない] リストに登録するすべての手順を実行したことと、キー キービルトごとに回復可能な削除を有効にしたことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3eff-313">If the _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, you will need to review this topic and ensure that you have followed all of the steps to put the subscription on the Do Not Cancel list and that you have soft delete enabled on each of your key vaults.</span></span>
  
### <a name="back-up-azure-key-vault"></a><span data-ttu-id="c3eff-314">Azure Key Vault のバックアップ</span><span class="sxs-lookup"><span data-stu-id="c3eff-314">Back up Azure Key Vault</span></span>

<span data-ttu-id="c3eff-315">キーの作成または変更の直後に、バックアップと保存のコピーをオンラインとオフラインの両方で実行します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-315">Immediately following creation or any change to a key, perform a backup and store copies of the backup, both online and offline.</span></span> <span data-ttu-id="c3eff-316">物理的な安全または商用記憶域など、オフライン コピーはネットワークに接続してはなりません。</span><span class="sxs-lookup"><span data-stu-id="c3eff-316">Offline copies should not be connected to any network, such as in a physical safe or commercial storage facility.</span></span> <span data-ttu-id="c3eff-317">障害が発生した場合にアクセスできる場所に、少なくとも 1 つのバックアップのコピーを格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3eff-317">At least one copy of the backup should be stored in a location that will be accessible in the event of a disaster.</span></span> <span data-ttu-id="c3eff-318">バックアップ BLOB は、キー コンテナーのキーを完全に破悪したり、レンダリング不可能にする必要がある、キー コンテナー型の復元方法の単に使用される方法です。</span><span class="sxs-lookup"><span data-stu-id="c3eff-318">The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable.</span></span> <span data-ttu-id="c3eff-319">Azure Key Vault の外部にあり、Azure Key Vault にインポートされたキーは、カスタマー キーがキーを使用するために必要なメタデータは外部キーとの間に存在しないので、バックアップとして認られることはありません。</span><span class="sxs-lookup"><span data-stu-id="c3eff-319">Keys that are external to Azure Key Vault and were imported to Azure Key Vault do not qualify as a backup because the metadata necessary for Customer Key to use the key does not exist with the external key.</span></span> <span data-ttu-id="c3eff-320">カスタマー キーによる復元操作には、Azure Key Vault から行されたバックアップのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c3eff-320">Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key.</span></span> <span data-ttu-id="c3eff-321">したがって、キーがアップロードまたは作成された後に Azure Key Vault のバックアップを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3eff-321">Therefore, it is essential that a backup of Azure Key Vault be made once a key is uploaded or created.</span></span>
  
<span data-ttu-id="c3eff-322">Azure Key VaultKey キーのバックアップを作成するには [、Backup-AzKeyVaultKey コマンドレット](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) を次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-322">To create a backup of an Azure Key Vault key, run the [Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet as follows:</span></span>

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

<span data-ttu-id="c3eff-323">出力ファイルにサフィックスが使用されていることを確認してください `.backup` 。</span><span class="sxs-lookup"><span data-stu-id="c3eff-323">Ensure that your output file uses the suffix `.backup`.</span></span>
  
<span data-ttu-id="c3eff-324">このコマンドレットによって出力される出力ファイルは暗号化されているため、Azure Key Vault 以外では使用できません。</span><span class="sxs-lookup"><span data-stu-id="c3eff-324">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault.</span></span> <span data-ttu-id="c3eff-325">バックアップは、バックアップの取得元の Azure サブスクリプションにのみ復元できます。</span><span class="sxs-lookup"><span data-stu-id="c3eff-325">The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
> [!TIP]
> <span data-ttu-id="c3eff-326">出力ファイルでは、ベールト名とキー名の組み合わせを選択します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-326">For the output file, choose a combination of your vault name and key name.</span></span> <span data-ttu-id="c3eff-327">これにより、ファイル名が自動的に説明されます。</span><span class="sxs-lookup"><span data-stu-id="c3eff-327">This will make the file name self-describing.</span></span> <span data-ttu-id="c3eff-328">また、バックアップ ファイル名が調整されないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-328">It will also ensure that backup file names do not collide.</span></span>
  
<span data-ttu-id="c3eff-329">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-329">For example:</span></span>
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="c3eff-330">Azure Key Vault 構成設定の検証</span><span class="sxs-lookup"><span data-stu-id="c3eff-330">Validate Azure Key Vault configuration settings</span></span>

<span data-ttu-id="c3eff-331">DEP でキーを使用する前に検証を実行するオプションはオプションですが、強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c3eff-331">Performing validation before using keys in a DEP is optional, but highly recommended.</span></span> <span data-ttu-id="c3eff-332">特に、このトピックで説明されているキーと保書以外のものをセットアップする手順を使用する場合、カスタマー キーを構成する前に Azure Key Vault リソースの正常性を検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3eff-332">In particular, if you use steps to set up your keys and vaults other than the ones described in this topic, you should validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="c3eff-333">キーの取得、ラップ キー、および unwrapKey 操作が有効になっていることを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-333">To verify that your keys have get, wrapKey, and unwrapKey operations enabled:</span></span>
  
<span data-ttu-id="c3eff-334">[Get-AzKeyVault コマンドレットを次](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault)のように実行します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-334">Run the [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="c3eff-335">出力で、アクセス ポリシー、Exchange Online ID (GUID)、または SharePoint Online ID (GUID) を適当に検索します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-335">In the output, look for the Access Policy and for the Exchange Online identity (GUID) or the SharePoint Online identity (GUID) as appropriate.</span></span> <span data-ttu-id="c3eff-336">上記 3 つのアクセス許可のうち、上記の 3 つすべてが [キーへのアクセス許可] 下に表示されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3eff-336">All three of the above permissions must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="c3eff-337">アクセス ポリシー構成が正しくない場合は、Set-AzKeyVaultAccessPolicy コマンドレットを次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-337">If the access policy configuration is incorrect, run the Set-AzKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

<span data-ttu-id="c3eff-338">たとえば、Exchange Online および Skype for Business の場合:</span><span class="sxs-lookup"><span data-stu-id="c3eff-338">For example, for Exchange Online and Skype for Business:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="c3eff-339">たとえば、SharePoint Online と OneDrive for Business の場合:</span><span class="sxs-lookup"><span data-stu-id="c3eff-339">For example, for SharePoint Online and OneDrive for Business:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="c3eff-340">キーに有効期限日が設定されていないことを確認するには、次のように [Get-AzKeyVaultKey コマンドレット](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) を実行します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-340">To verify that an expiration date is not set for your keys run the [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

<span data-ttu-id="c3eff-341">期限切れのキーを顧客キーで使用すると、有効期限が切れたキーを使用しようとすると失敗し、場合によってサービスが停止します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-341">An expired key cannot be used by Customer Key and operations attempted with an expired key will fail, and possibly result in a service outage.</span></span> <span data-ttu-id="c3eff-342">カスタマー キーと使用されるキーに有効期限がないことを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c3eff-342">We strongly recommend that keys used with Customer Key do not have an expiration date.</span></span> <span data-ttu-id="c3eff-343">設定すると、有効期限は削除できませんが、別の日付に変更できます。</span><span class="sxs-lookup"><span data-stu-id="c3eff-343">An expiration date, once set, cannot be removed, but can be changed to a different date.</span></span> <span data-ttu-id="c3eff-344">有効期限日が設定されているキーを使用する必要がある場合は、有効期限の値を 12/31/9999 に変更します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-344">If a key must be used that has an expiration date set, change the expiration value to 12/31/9999.</span></span> <span data-ttu-id="c3eff-345">有効期限が 9999 年 12 月 31 日を超える日付に設定されたキーは、Microsoft 365 の検証に合格しません。</span><span class="sxs-lookup"><span data-stu-id="c3eff-345">Keys with an expiration date set to a date other than 12/31/9999 will not pass Microsoft 365 validation.</span></span>
  
<span data-ttu-id="c3eff-346">12/31/9999 以外の値に設定されている有効期限日を変更するには [、Update-AzKeyVaultKey コマンドレット](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) を次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-346">To change an expiration date that has been set to any value other than 12/31/9999, run the [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> <span data-ttu-id="c3eff-347">カスタマー キーで使用する暗号化キーに有効期限を設定しない。</span><span class="sxs-lookup"><span data-stu-id="c3eff-347">Don't set expiration dates on encryption keys you use with Customer Key.</span></span>
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="c3eff-348">各 Azure Key Vault キーの URI を取得する</span><span class="sxs-lookup"><span data-stu-id="c3eff-348">Obtain the URI for each Azure Key Vault key</span></span>

<span data-ttu-id="c3eff-349">Azure ですべての手順を完了し、キー バールをセットアップしてキーを追加したら、次のコマンドを実行して、キーの URI を各キー ビルトに取得します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-349">Once you've completed all the steps in Azure to set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault.</span></span> <span data-ttu-id="c3eff-350">後で各 DEP を作成して割り当てるときにこれらの URI を使用する必要があるため、この情報を安全な場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-350">You will need to use these URIs when you create and assign each DEP later, so save this information in a safe place.</span></span> <span data-ttu-id="c3eff-351">このコマンドは、キーの読み取りごとに 1 回実行してください。</span><span class="sxs-lookup"><span data-stu-id="c3eff-351">Remember to run this command once for each key vault.</span></span>
  
<span data-ttu-id="c3eff-352">Azure PowerShell で、</span><span class="sxs-lookup"><span data-stu-id="c3eff-352">In Azure PowerShell:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="c3eff-353">Office 365: Exchange Online および Skype for Business の顧客キーのセットアップ</span><span class="sxs-lookup"><span data-stu-id="c3eff-353">Office 365: Setting up Customer Key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="c3eff-354">始める前に、Azure Key Vault のセットアップに必要なタスクを完了していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-354">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="c3eff-355">詳細 [については、Azure Key Vault と Microsoft FastTrack のタスクの一覧](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3eff-355">See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) for information.</span></span>
  
<span data-ttu-id="c3eff-356">Exchange Online と Skype for Business のカスタマー キーをセットアップするには、Windows PowerShell と Exchange Online にリモート接続してこれらの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3eff-356">To set up Customer Key for Exchange Online and Skype for Business, you will need to perform these steps by remotely connecting to Exchange Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a><span data-ttu-id="c3eff-357">Exchange Online および Skype for Business で使用するためのデータ暗号化ポリシー (DEP) を作成する</span><span class="sxs-lookup"><span data-stu-id="c3eff-357">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>

<span data-ttu-id="c3eff-358">DEP は、Azure Key Vault に保存されている一連のキーに関連付けられていいます。</span><span class="sxs-lookup"><span data-stu-id="c3eff-358">A DEP is associated with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="c3eff-359">Microsoft 365 のメールボックスに DEP を割り当てる。</span><span class="sxs-lookup"><span data-stu-id="c3eff-359">You assign a DEP to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="c3eff-360">次に、Microsoft 365 はポリシーで特定されたキーを使用してメールボックスを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-360">Microsoft 365 will then use the keys identified in the policy to encrypt the mailbox.</span></span> <span data-ttu-id="c3eff-361">DEP を作成するには、前の手順で取得した Key Vault URI が必要です。</span><span class="sxs-lookup"><span data-stu-id="c3eff-361">To create the DEP, you need the Key Vault URIs you obtained earlier.</span></span> <span data-ttu-id="c3eff-362">手順 [については、「Azure Key Vault key」の URI の取得](#obtain-the-uri-for-each-azure-key-vault-key) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3eff-362">See [Obtain the URI for each Azure Key Vault key](#obtain-the-uri-for-each-azure-key-vault-key) for instructions.</span></span>
  
<span data-ttu-id="c3eff-363">注意してください。</span><span class="sxs-lookup"><span data-stu-id="c3eff-363">Remember!</span></span> <span data-ttu-id="c3eff-364">DEP を作成するときに、2 つの異なる Azure Key Vault に含む 2 つのキーを指定します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-364">When you create a DEP, you specify two keys that reside in two different Azure Key Vaults.</span></span> <span data-ttu-id="c3eff-365">これらのキーを地域冗長性を確実に確実にするために、これらのキーが 2 つの別個の Azure リージョンにあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-365">Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="c3eff-366">DEP を作成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="c3eff-366">To create the DEP, follow these steps:</span></span>
  
1. <span data-ttu-id="c3eff-367">ローカル コンピューターで、組織のグローバル管理者アクセス許可を持つ職場または学校のアカウントを使用して [、ローカル ウィンドウで Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) にWindows PowerShellします。</span><span class="sxs-lookup"><span data-stu-id="c3eff-367">On your local computer, using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="c3eff-368">DEP を作成するには、次のコマンドを入力して New-DataEncryptionPolicy コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-368">To create a DEP, use the New-DataEncryptionPolicy cmdlet by typing the following command.</span></span>

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   <span data-ttu-id="c3eff-369">ここで、</span><span class="sxs-lookup"><span data-stu-id="c3eff-369">Where:</span></span>

   - <span data-ttu-id="c3eff-370">*PolicyName* は、ポリシーに使用する名前です。</span><span class="sxs-lookup"><span data-stu-id="c3eff-370">*PolicyName* is the name you want to use for the policy.</span></span> <span data-ttu-id="c3eff-371">名前にスペースを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="c3eff-371">Names cannot contain spaces.</span></span> <span data-ttu-id="c3eff-372">たとえば、次の USA_mailboxes。</span><span class="sxs-lookup"><span data-stu-id="c3eff-372">For example, USA_mailboxes.</span></span>

   - <span data-ttu-id="c3eff-373">*ポリシーの説明* は、このポリシーの目的をわかりやすく説明するポリシーのわかりやすい説明です。</span><span class="sxs-lookup"><span data-stu-id="c3eff-373">*Policy Description* is a user friendly description of the policy that will help you remember what the policy is for.</span></span> <span data-ttu-id="c3eff-374">説明にはスペースを含めることが可能です。</span><span class="sxs-lookup"><span data-stu-id="c3eff-374">You can include spaces in the description.</span></span> <span data-ttu-id="c3eff-375">たとえば、「USA とそのトリーフリストのルート キー」とします。</span><span class="sxs-lookup"><span data-stu-id="c3eff-375">For example, "Root key for mailboxes in USA and its territories".</span></span>

   - <span data-ttu-id="c3eff-376">*KeyVaultURI1* は、ポリシーの最初のキーの URI です。</span><span class="sxs-lookup"><span data-stu-id="c3eff-376">*KeyVaultURI1* is the URI for the first key in the policy.</span></span> <span data-ttu-id="c3eff-377">たとえば、<https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01> などです。</span><span class="sxs-lookup"><span data-stu-id="c3eff-377">For example, <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.</span></span>

   - <span data-ttu-id="c3eff-378">*KeyVaultURI2 は* 、ポリシー内の 2 番目のキーの URI です。</span><span class="sxs-lookup"><span data-stu-id="c3eff-378">*KeyVaultURI2* is the URI for the second key in the policy.</span></span> <span data-ttu-id="c3eff-379">たとえば、<https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02> などです。</span><span class="sxs-lookup"><span data-stu-id="c3eff-379">For example, <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>.</span></span> <span data-ttu-id="c3eff-380">2 つの URI はカンマとスペースで区切ります。</span><span class="sxs-lookup"><span data-stu-id="c3eff-380">Separate the two URIs by a comma and a space.</span></span>

   <span data-ttu-id="c3eff-381">例:</span><span class="sxs-lookup"><span data-stu-id="c3eff-381">Example:</span></span>
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

<span data-ttu-id="c3eff-382">構文およびパラメーターの詳細については [、New-DataEncryptionPolicy を参照してください](https://docs.microsoft.com/powershell/module/exchange/new-data-encryptionpolicy)。</span><span class="sxs-lookup"><span data-stu-id="c3eff-382">For detailed syntax and parameter information, see [New-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/new-data-encryptionpolicy).</span></span>

### <a name="assign-a-dep-to-a-mailbox"></a><span data-ttu-id="c3eff-383">DEP をメールボックスに割り当てる</span><span class="sxs-lookup"><span data-stu-id="c3eff-383">Assign a DEP to a mailbox</span></span>

<span data-ttu-id="c3eff-384">Set-Mailbox コマンドレットを使用して、DEP をメールボックスに割り当て。</span><span class="sxs-lookup"><span data-stu-id="c3eff-384">Assign the DEP to a mailbox by using the Set-Mailbox cmdlet.</span></span> <span data-ttu-id="c3eff-385">ポリシーを割り当てると、Microsoft 365 は DEP で指定されたキーを使ってメールボックスを暗号化できます。</span><span class="sxs-lookup"><span data-stu-id="c3eff-385">Once you assign the policy, Microsoft 365 can encrypt the mailbox with the key designated in the DEP.</span></span>
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="c3eff-386">*MailboxIdParameter が*メールボックスを指定する場所。</span><span class="sxs-lookup"><span data-stu-id="c3eff-386">Where *MailboxIdParameter* specifies a mailbox.</span></span> <span data-ttu-id="c3eff-387">Set-Mailbox コマンドレットの詳細については [、「Set-Mailbox」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="c3eff-387">For more information about the Set-Mailbox cmdlet, see [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox).</span></span>

<span data-ttu-id="c3eff-388">iOS および Android 用の Outlook とハイブリッド先進認証で Outlook を使用する [オンプレミスのメールボックスの場合、Exchange](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)Online テナントに同期されるオンプレミスのメールボックス データに Set-MailUser コマンドレットを使用して DEP を割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="c3eff-388">For [on-premises mailboxes using Outlook for iOS and Android with hybrid Modern Authentication](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth), the on-premises mailbox data that is synchronized into your Exchange Online tenant can have DEP assigned using the Set-MailUser cmdlet.</span></span>

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="c3eff-389">*MailUserIdParameter は*メール ユーザー (メールが有効なユーザーとも呼ばれる) を指定します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-389">Where *MailUserIdParameter* specifies a mail user (also known as a mail-enabled user).</span></span> <span data-ttu-id="c3eff-390">Set-MailUser コマンドレットの詳細については [、「Set-MailUser」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-mailuser)。</span><span class="sxs-lookup"><span data-stu-id="c3eff-390">For more information about the Set-MailUser cmdlet, see [Set-MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser).</span></span>
  
### <a name="validate-mailbox-encryption"></a><span data-ttu-id="c3eff-391">メールボックスの暗号化の検証</span><span class="sxs-lookup"><span data-stu-id="c3eff-391">Validate mailbox encryption</span></span>

<span data-ttu-id="c3eff-392">メールボックスの暗号化にはしらくらく時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c3eff-392">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="c3eff-393">ポリシーの割り当てが初めて実行される場合、サービスがメールボックスを暗号化する前に、メールボックスを 1 つのデータベースから別のデータベースに完全に移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3eff-393">For first time policy assignment, the mailbox must also completely move from one database to another before the service can encrypt the mailbox.</span></span> <span data-ttu-id="c3eff-394">DEP を変更した後、または最初にメールボックスに DEP を割り当てる場合は、72 時間待ってから暗号化を検証できるようにしておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c3eff-394">We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="c3eff-395">Get-MailboxStatistics コマンドレットを使用して、メールボックスが暗号化されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-395">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="c3eff-396">IsEncrypted プロパティは、メールボックスが暗号化されている場合 **は true** の値を返し、メールボックスが暗号化されていない **場合は false** の値を返します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-396">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span>

<span data-ttu-id="c3eff-397">メールボックスの移動が完了する時間は、初めて DEP を割り当てたメールボックスの数と、メールボックスのサイズによって異なります。</span><span class="sxs-lookup"><span data-stu-id="c3eff-397">The time to complete mailbox moves depends on the number of mailboxes to which you assign a DEP for the first time, as well as the size of the mailboxes.</span></span> <span data-ttu-id="c3eff-398">DEP を割り当ててから 1 週間後にメールボックスが暗号化されていない場合は、Microsoft にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="c3eff-398">If the mailboxes have not been encrypted after a week from the time you assigned the DEP, contact Microsoft.</span></span>

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="c3eff-399">Office 365: SharePoint Online、OneDrive for Business、Teams ファイルのカスタマー キーのセットアップ</span><span class="sxs-lookup"><span data-stu-id="c3eff-399">Office 365: Setting up Customer Key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="c3eff-400">始める前に、Azure Key Vault のセットアップに必要なタスクを完了していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-400">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="c3eff-401">詳細 [については、Azure Key Vault と Microsoft FastTrack のタスクの一覧](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3eff-401">See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) for information.</span></span>
  
<span data-ttu-id="c3eff-402">SharePoint Online、OneDrive for Business、Teams の各ファイルのカスタマー キーをセットアップするには、これらの手順を実行する必要があります。これらの手順は、クラウドで SharePoint Online にリモート接続Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c3eff-402">To set up Customer Key for SharePoint Online, OneDrive for Business, and Teams files you will need to perform these steps by remotely connecting to SharePoint Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a><span data-ttu-id="c3eff-403">SharePoint Online および OneDrive for Business の地域ごとにデータの暗号化ポリシー (DEP) を作成する</span><span class="sxs-lookup"><span data-stu-id="c3eff-403">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>

<span data-ttu-id="c3eff-404">DEP は、Azure Key Vault に格納されているキーのセットに関連付けけれます。</span><span class="sxs-lookup"><span data-stu-id="c3eff-404">You associate a DEP with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="c3eff-405">GEO とも呼ばれる、1 つの地理的な場所にあるすべてのデータに DEP を適用します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-405">You apply a DEP to all of your data in one geographic location, also called a geo.</span></span> <span data-ttu-id="c3eff-406">Office 365 の複数地域機能を使用する場合は、geo ごとに異なるキーを使用する機能を持つ、geo ごとに 1 つの DEP を作成できます。</span><span class="sxs-lookup"><span data-stu-id="c3eff-406">If you use the multi-geo feature of Office 365, you can create one DEP per geo with the capability to use different keys per geo.</span></span> <span data-ttu-id="c3eff-407">複数地域を使用していない場合は、SharePoint Online、OneDrive for Business、および Teams のファイルと連用する DEP を組織内に 1 つ作成できます。</span><span class="sxs-lookup"><span data-stu-id="c3eff-407">If you are not using multi-geo, you can create one DEP in your organization for use with SharePoint Online, OneDrive for Business, and Teams files.</span></span> <span data-ttu-id="c3eff-408">Microsoft 365 は DEP で特定されたキーを使用して、その geo でデータを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-408">Microsoft 365 uses the keys identified in the DEP to encrypt your data in that geo.</span></span> <span data-ttu-id="c3eff-409">DEP を作成するには、前の手順で取得した Key Vault URI が必要です。</span><span class="sxs-lookup"><span data-stu-id="c3eff-409">To create the DEP, you need the Key Vault URIs you obtained earlier.</span></span> <span data-ttu-id="c3eff-410">手順 [については、「Azure Key Vault key」の URI の取得](#obtain-the-uri-for-each-azure-key-vault-key) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3eff-410">See [Obtain the URI for each Azure Key Vault key](#obtain-the-uri-for-each-azure-key-vault-key) for instructions.</span></span>
  
<span data-ttu-id="c3eff-411">注意してください。</span><span class="sxs-lookup"><span data-stu-id="c3eff-411">Remember!</span></span> <span data-ttu-id="c3eff-412">DEP を作成するときに、2 つの異なる Azure Key Vault に含む 2 つのキーを指定します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-412">When you create a DEP, you specify two keys that reside in two different Azure Key Vaults.</span></span> <span data-ttu-id="c3eff-413">これらのキーを地域冗長性を確実に確実にするために、これらのキーが 2 つの別個の Azure リージョンにあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-413">Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="c3eff-414">DEP を作成するには、リモートから次のコマンドを使用して SharePoint Online にリモート接続Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c3eff-414">To create a DEP, you need to remotely connect to SharePoint Online by using Windows PowerShell.</span></span>
  
1. <span data-ttu-id="c3eff-415">ローカル コンピューターで、組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを [使用して、SharePoint Online Powershell に接続します](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)。</span><span class="sxs-lookup"><span data-stu-id="c3eff-415">On your local computer, using a work or school account that has global administrator permissions in your organization, [Connect to SharePoint Online Powershell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

2. <span data-ttu-id="c3eff-416">Microsoft SharePoint Online 管理シェルで、Register-SPODataEncryptionPolicy コマンドレットを次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-416">In the Microsoft SharePoint Online Management Shell, run the Register-SPODataEncryptionPolicy cmdlet as follows:</span></span>

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   <span data-ttu-id="c3eff-417">DEP を登録すると、暗号化は geo 内のデータから開始されます。</span><span class="sxs-lookup"><span data-stu-id="c3eff-417">When you register the DEP, encryption begins on the data in the geo.</span></span> <span data-ttu-id="c3eff-418">この処理には時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c3eff-418">This can take some time.</span></span>

### <a name="validate-file-encryption"></a><span data-ttu-id="c3eff-419">ファイルの暗号化の検証</span><span class="sxs-lookup"><span data-stu-id="c3eff-419">Validate file encryption</span></span>

 <span data-ttu-id="c3eff-420">SharePoint Online、OneDrive for Business、および Teams ファイルの暗号化を検証するには [、SharePoint Online PowerShell に接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)し、Get-SPODataEncryptionPolicy コマンドレットを使用してテナントの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-420">To validate encryption of SharePoint Online, OneDrive for Business, and Teams files, [connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps), and then use the Get-SPODataEncryptionPolicy cmdlet to check the status of your tenant.</span></span> <span data-ttu-id="c3eff-421">_State プロパティは_、顧客キーの暗号化**が有効で**、すべてのサイト内のすべてのファイルが暗号化されている場合に、登録された値を返します。</span><span class="sxs-lookup"><span data-stu-id="c3eff-421">The _State_ property returns a value of **registered** if Customer Key encryption is enabled and all files in all sites have been encrypted.</span></span> <span data-ttu-id="c3eff-422">暗号化が進行中の場合は、サイトのどのパーセンテージが完了したかに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3eff-422">If encryption is still in progress, this cmdlet provides information on what percentage of sites is complete.</span></span>

## <a name="related-articles"></a><span data-ttu-id="c3eff-423">関連記事</span><span class="sxs-lookup"><span data-stu-id="c3eff-423">Related articles</span></span>

- [<span data-ttu-id="c3eff-424">カスタマー キーによるサービスの暗号化</span><span class="sxs-lookup"><span data-stu-id="c3eff-424">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="c3eff-425">顧客キーの管理</span><span class="sxs-lookup"><span data-stu-id="c3eff-425">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="c3eff-426">カスタマー キーまたは可用性キーをローリングまたはローテーションする</span><span class="sxs-lookup"><span data-stu-id="c3eff-426">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="c3eff-427">可用性キーの詳細</span><span class="sxs-lookup"><span data-stu-id="c3eff-427">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="c3eff-428">サービスの暗号化</span><span class="sxs-lookup"><span data-stu-id="c3eff-428">Service Encryption</span></span>](office-365-service-encryption.md)
