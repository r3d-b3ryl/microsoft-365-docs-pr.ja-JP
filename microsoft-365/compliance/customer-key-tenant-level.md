---
title: テナント レベルの Microsoft 365 の [カスタマー]キー (パブリック プレビュー)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 2/17/2021
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
description: Microsoft 365 テナント内のすべてのデータに顧客キーを設定する方法について説明します。
ms.openlocfilehash: f50986b4e72808d4a1cd4dc8ee0182eb9c0a2455
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922691"
---
# <a name="overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview"></a><span data-ttu-id="22dce-103">テナント レベルでの Microsoft 365 のカスタマー キーの概要 (パブリック プレビュー)</span><span class="sxs-lookup"><span data-stu-id="22dce-103">Overview of Customer Key for Microsoft 365 at the tenant level (public preview)</span></span>

<span data-ttu-id="22dce-104">指定したキーを使用して、データ暗号化ポリシー (DEP) を作成し、テナントに割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="22dce-104">Using keys you provide, you can create a data encryption policy (DEP) and assign it to the tenant.</span></span> <span data-ttu-id="22dce-105">DEP は、次のワークロードのテナント全体のデータを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="22dce-105">The DEP encrypts data across the tenant for these workloads:</span></span>

- <span data-ttu-id="22dce-106">Teams チャット メッセージ (1:1 チャット、グループ チャット、会議チャット、チャネル会話)</span><span class="sxs-lookup"><span data-stu-id="22dce-106">Teams chat messages (1:1 chats, group chats, meeting chats and channel conversations)</span></span>
- <span data-ttu-id="22dce-107">Teams メディア メッセージ (画像、コード スニペット、ビデオ メッセージ、オーディオ メッセージ、Wiki イメージ)</span><span class="sxs-lookup"><span data-stu-id="22dce-107">Teams media messages (images, code snippets, video messages, audio messages, wiki images)</span></span>
- <span data-ttu-id="22dce-108">Teams の通話と Teams ストレージに保存されている会議の記録</span><span class="sxs-lookup"><span data-stu-id="22dce-108">Teams call and meeting recordings stored in Teams storage</span></span>
- <span data-ttu-id="22dce-109">Teams チャット通知</span><span class="sxs-lookup"><span data-stu-id="22dce-109">Teams chat notifications</span></span>
- <span data-ttu-id="22dce-110">Cortana による Teams チャットの提案</span><span class="sxs-lookup"><span data-stu-id="22dce-110">Teams chat suggestions by Cortana</span></span>
- <span data-ttu-id="22dce-111">Teams の状態メッセージ</span><span class="sxs-lookup"><span data-stu-id="22dce-111">Teams status messages</span></span>
- <span data-ttu-id="22dce-112">Exchange Online のユーザー情報とシグナル情報</span><span class="sxs-lookup"><span data-stu-id="22dce-112">User and signal information for Exchange Online</span></span>
- <span data-ttu-id="22dce-113">アプリケーション レベルでまだ暗号化されていない Exchange Online メールボックス</span><span class="sxs-lookup"><span data-stu-id="22dce-113">Exchange Online mailboxes that aren't already encrypted Customer Key DEPs at the application level</span></span>

<span data-ttu-id="22dce-114">Microsoft Teams の場合、テナント レベルの顧客キーは、DEP がテナントに割り当てられた時点から新しいデータを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="22dce-114">For Microsoft Teams, Customer Key at the tenant level encrypts new data from the time the DEP is assigned to the tenant.</span></span> <span data-ttu-id="22dce-115">パブリック プレビューでは、過去のデータの暗号化はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="22dce-115">Public preview does not support encrypting past data.</span></span> <span data-ttu-id="22dce-116">Exchange Online の場合、顧客キーは既存のデータと新しいデータを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="22dce-116">For Exchange Online, Customer Key encrypts all existing and new data.</span></span>

<span data-ttu-id="22dce-117">テナントごとに複数の DEP を作成できますが、任意の時点で 1 つの DEP のみを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="22dce-117">You can create multiple DEPs per tenant but can only assign one DEP at any point in time.</span></span> <span data-ttu-id="22dce-118">DEP を割り当てると、暗号化は自動的に開始されますが、テナントのサイズによっては完了に時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="22dce-118">When you assign the DEP, encryption begins automatically but can take some time to complete depending on the size of your tenant.</span></span>

## <a name="tenant-level-policies-add-broader-control-to-customer-key-for-microsoft-365"></a><span data-ttu-id="22dce-119">テナント レベルのポリシーは、Microsoft 365 の顧客キーに広範な制御を追加します。</span><span class="sxs-lookup"><span data-stu-id="22dce-119">Tenant level policies add broader control to Customer Key for Microsoft 365</span></span>

<span data-ttu-id="22dce-120">Exchange Online と Sharepoint Online 用に顧客キーが既に設定されている場合は、新しいテナント レベルのパブリック プレビューがどのように適合しているかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="22dce-120">If you already have Customer Key set up for Exchange Online and Sharepoint Online, here's how the new tenant-level public preview fits in.</span></span>

<span data-ttu-id="22dce-121">作成するテナント レベルの暗号化ポリシーは、Microsoft 365 の Microsoft Teams ワークロードおよび Exchange Online ワークロードのすべてのデータを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="22dce-121">The tenant-level encryption policy you create encrypts all data for the Microsoft Teams and Exchange Online workloads in Microsoft 365.</span></span> <span data-ttu-id="22dce-122">ただし、Exchange Online では、顧客キー DEP を個々のメールボックスに既に割り当て済みの場合、テナント レベルのポリシーはそれらの DEP を上書きされません。</span><span class="sxs-lookup"><span data-stu-id="22dce-122">However, for Exchange Online, if you have already assigned Customer Key DEPs to individual mailboxes, the tenant-level policy won't override those DEPs.</span></span> <span data-ttu-id="22dce-123">テナント レベルのポリシーは、メールボックス レベルの Customer Key DEP が既に割り当てられていないメールボックスのみを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="22dce-123">The tenant-level policy will only encrypt mailboxes that aren't assigned a mailbox level Customer Key DEP already.</span></span>

<span data-ttu-id="22dce-124">たとえば、Microsoft Teams ファイルと、OneDrive for Business および SharePoint に保存されている一部の Teams 呼び出しおよび会議記録は、SharePoint Online DEP によって暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="22dce-124">For example, Microsoft Teams files and some Teams call and meeting recordings that are saved in OneDrive for Business and SharePoint are encrypted by a SharePoint Online DEP.</span></span> <span data-ttu-id="22dce-125">単一の SharePoint Online DEP は、1 つの geo 内のコンテンツを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="22dce-125">A single SharePoint Online DEP encrypts content within a single geo.</span></span>

## <a name="set-up-customer-key-at-the-tenant-level-public-preview"></a><span data-ttu-id="22dce-126">テナント レベルで顧客キーを設定する (パブリック プレビュー)</span><span class="sxs-lookup"><span data-stu-id="22dce-126">Set up Customer Key at the tenant level (public preview)</span></span>

<span data-ttu-id="22dce-127">これらの手順は類似していますが、アプリケーション レベルで顧客キーを設定する手順と同じではありません。</span><span class="sxs-lookup"><span data-stu-id="22dce-127">These steps are similar but not identical to the steps for setting up Customer Key at the application level.</span></span> <span data-ttu-id="22dce-128">このパブリック プレビューは、テスト テナントのテスト データでのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="22dce-128">You should only use this public preview with test data in test tenants.</span></span> <span data-ttu-id="22dce-129">このリリースは、実稼働データや実稼働環境では使用しない。</span><span class="sxs-lookup"><span data-stu-id="22dce-129">Do not use this release with production data or in your production environment.</span></span> <span data-ttu-id="22dce-130">顧客キーの実稼働展開が既にある場合は、次の手順を使用して、テスト環境のテナント レベルで顧客キーを設定します。</span><span class="sxs-lookup"><span data-stu-id="22dce-130">If you already have a production deployment of Customer Key, use these steps to set up Customer Key at the tenant level in a test environment.</span></span> <span data-ttu-id="22dce-131">テナント レベルの DEP をテナントに割り当てたら、検証プロセスを開始し、質問や懸念事項を m365ck@microsoft.com に問い合わせできます。</span><span class="sxs-lookup"><span data-stu-id="22dce-131">Once you have assigned a tenant level DEP to your tenant, you can start the validation process and reach out to m365ck@microsoft.com with any questions or concerns.</span></span> <span data-ttu-id="22dce-132">ドキュメントの検証手順については [、「Microsoft 365](https://aka.ms/CustomerKey/PublicPreviewValidation)のデータ保存時暗号化の検証手順」のパブリック プレビューで確認できます。</span><span class="sxs-lookup"><span data-stu-id="22dce-132">You can also find documented validation steps in the public preview of [Validation Instructions for Data-at-rest Encryption for Microsoft 365](https://aka.ms/CustomerKey/PublicPreviewValidation).</span></span>

<span data-ttu-id="22dce-133">これらのほとんどのタスクは、Azure PowerShell にリモートで接続して完了します。</span><span class="sxs-lookup"><span data-stu-id="22dce-133">You'll complete most of these tasks by remotely connecting to Azure PowerShell.</span></span> <span data-ttu-id="22dce-134">最適な結果を得る場合は、バージョン 4.4.0 以降の Azure PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="22dce-134">For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>

<span data-ttu-id="22dce-135">開始する前に、次の情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="22dce-135">Before you get started, make sure of the following:</span></span>

- <span data-ttu-id="22dce-136">テナント レベルで顧客キーを設定するには、コンプライアンス管理者の役割を持つ仕事または学校のアカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22dce-136">You'll need to use a work or school account that has the compliance admin role to set up Customer Key at the tenant level.</span></span>
- <span data-ttu-id="22dce-137">組織に適切なライセンスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="22dce-137">Ensure that you have the appropriate licensing for your organization.</span></span> <span data-ttu-id="22dce-138">クラウド サービス プロバイダーまたはクラウド サービス プロバイダーを使用して、支払マイクロソフトエンタープライズ契約 Azure サブスクリプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="22dce-138">Use a paid, invoiced Azure Subscription using either an Enterprise Agreement or a Cloud Service Provider.</span></span> <span data-ttu-id="22dce-139">Pay As You Go プランまたはクレジット カードを使用して購入した Azure サブスクリプションは、顧客キーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="22dce-139">Azure Subscriptions purchased using Pay As You Go plans or using a credit card aren't supported for Customer Key.</span></span> <span data-ttu-id="22dce-140">2020 年 4 月 1 日より、Office 365 のカスタマー キーは、Office 365 E5、M365 E5、M365 E5 コンプライアンス、M365 E5 情報保護 & ガバナンス SKU で提供されます。</span><span class="sxs-lookup"><span data-stu-id="22dce-140">Starting April 1, 2020, Customer Key in Office 365 is offered in Office 365 E5, M365 E5, M365 E5 Compliance, and M365 E5 Information Protection & Governance SKUs.</span></span> <span data-ttu-id="22dce-141">Office 365 Advanced Compliance SKU は、新しいライセンスの調達に使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="22dce-141">Office 365 Advanced Compliance SKU is no longer available for procuring new licenses.</span></span> <span data-ttu-id="22dce-142">既存のOffice 365 Advanced Compliance ライセンスは引き続きサポートされます。</span><span class="sxs-lookup"><span data-stu-id="22dce-142">Existing Office 365 Advanced Compliance licenses will continue to be supported.</span></span> <span data-ttu-id="22dce-143">適切なライセンスを持つテナントの下で少なくとも 1 つのライセンスでサービスを有効にできますが、サービスの恩恵を受けるすべてのユーザーが適切なライセンスを持つことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22dce-143">While the service can be enabled with a minimum of one license under the tenant having the appropriate license, you should still make sure all users that benefit from the service have appropriate licenses.</span></span>

### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="22dce-144">2 つの新しい Azure サブスクリプションを作成する</span><span class="sxs-lookup"><span data-stu-id="22dce-144">Create two new Azure subscriptions</span></span>

<span data-ttu-id="22dce-145">顧客キーには、データ暗号化ポリシー (DEP) ごとに 2 つのキーが必要です。</span><span class="sxs-lookup"><span data-stu-id="22dce-145">Customer Key requires two keys for each data encryption policy (DEP).</span></span> <span data-ttu-id="22dce-146">これを実現するには、2 つの Azure サブスクリプションを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22dce-146">To achieve this, you must create two Azure subscriptions.</span></span> <span data-ttu-id="22dce-147">ベスト プラクティスとして、組織の個別のメンバーが各サブスクリプションで 1 つのキーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22dce-147">As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription.</span></span> <span data-ttu-id="22dce-148">Microsoft 365 の暗号化キーを管理するには、これらの Azure サブスクリプションのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="22dce-148">Only use these Azure subscriptions to administer encryption keys for Microsoft 365.</span></span> <span data-ttu-id="22dce-149">これにより、オペレーターの 1 人が誤って、意図的に、または悪意を持って削除したり、責任を負うキーを誤って管理したりした場合に、組織が保護されます。</span><span class="sxs-lookup"><span data-stu-id="22dce-149">This protects your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible.</span></span>

<span data-ttu-id="22dce-150">組織に対して作成できる Azure サブスクリプションの数に実際的な制限はありません。</span><span class="sxs-lookup"><span data-stu-id="22dce-150">There is no practical limit to the number of Azure subscriptions that you can create for your organization.</span></span> <span data-ttu-id="22dce-151">このベスト プラクティスに従って、カスタマー キーで使用されるリソースを管理しながら、人的エラーの影響を最小限に抑えるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="22dce-151">Following this best practice helps minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span>

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="22dce-152">必須の保持期間を使用するように Azure サブスクリプションを登録する</span><span class="sxs-lookup"><span data-stu-id="22dce-152">Register Azure subscriptions to use a mandatory retention period</span></span>

<span data-ttu-id="22dce-153">ルート暗号化キーが一時的または永続的に失われると、サービス操作が中断したり、壊滅的な操作を受け入れ、データが失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="22dce-153">The temporary or permanent loss of root encryption keys can be disruptive or even catastrophic to service operation and can result in data loss.</span></span> <span data-ttu-id="22dce-154">このため、Customer Key で使用されるリソースには強力な保護が必要です。</span><span class="sxs-lookup"><span data-stu-id="22dce-154">For this reason, the resources used with Customer Key require strong protection.</span></span> <span data-ttu-id="22dce-155">Customer Key で使用される Azure リソースはすべて、既定の構成を超える保護メカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="22dce-155">All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration.</span></span> <span data-ttu-id="22dce-156">Azure サブスクリプションは、即時で取り消し可能な取り消しを防ぐ方法でタグ付けまたは登録できます。</span><span class="sxs-lookup"><span data-stu-id="22dce-156">Azure subscriptions can be tagged or registered in a way that will prevent immediate and irrevocable cancellation.</span></span> <span data-ttu-id="22dce-157">これは、必須の保持期間の登録と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="22dce-157">This is referred to as registering for a mandatory retention period.</span></span> <span data-ttu-id="22dce-158">必須の保持期間に Azure サブスクリプションを登録するために必要な手順では、Microsoft とのコラボレーションが必要です。</span><span class="sxs-lookup"><span data-stu-id="22dce-158">The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Microsoft.</span></span> <span data-ttu-id="22dce-159">このプロセスには最大 5 営業日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="22dce-159">This process can take up to five business days.</span></span> <span data-ttu-id="22dce-160">以前は、これは "キャンセルしない" と呼ばれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="22dce-160">Previously, this was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="22dce-161">Microsoft 365 チームに連絡する前に、カスタマー キーで使用する Azure サブスクリプションごとに次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22dce-161">Before contacting the Microsoft 365 team, you must perform the following steps for each Azure subscription that you use with Customer Key.</span></span> <span data-ttu-id="22dce-162">開始する前に [、Azure PowerShell Az](/powershell/azure/new-azureps-module-az) モジュールがインストールされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="22dce-162">Ensure that you have the [Azure PowerShell Az](/powershell/azure/new-azureps-module-az) module installed before you start.</span></span>

1. <span data-ttu-id="22dce-163">Azure PowerShell でサインインします。</span><span class="sxs-lookup"><span data-stu-id="22dce-163">Sign in with Azure PowerShell.</span></span> <span data-ttu-id="22dce-164">手順については [、「Azure PowerShell でサインインする」を参照してください](/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="22dce-164">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="22dce-165">必須の保持Register-AzProviderFeature使用するサブスクリプションを登録するには、Register-AzProviderFeatureコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="22dce-165">Run the Register-AzProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span> <span data-ttu-id="22dce-166">サブスクリプションごとにこのアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="22dce-166">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. <span data-ttu-id="22dce-167">Microsoft に問い合わせ、プロセスを完了[m365ck@microsoft.com。](mailto:m365ck@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="22dce-167">Contact Microsoft to have the process finalized at [m365ck@microsoft.com](mailto:m365ck@microsoft.com).</span></span> <span data-ttu-id="22dce-168">メールに次の情報を含める。</span><span class="sxs-lookup"><span data-stu-id="22dce-168">Include the following in your email:</span></span>

   <span data-ttu-id="22dce-169">**件名**: 顧客キー \<*Your tenant's fully-qualified domain name*\></span><span class="sxs-lookup"><span data-stu-id="22dce-169">**Subject**: Customer Key for \<*Your tenant's fully-qualified domain name*\></span></span>

   <span data-ttu-id="22dce-170">**本文**: 必須の保持期間を確定するサブスクリプションの ID。</span><span class="sxs-lookup"><span data-stu-id="22dce-170">**Body**: Subscription IDs for which you want to have the mandatory retention period finalized.</span></span>
   <span data-ttu-id="22dce-171">各サブスクリプションのGet-AzProviderFeature出力。</span><span class="sxs-lookup"><span data-stu-id="22dce-171">The output of Get-AzProviderFeature for each subscription.</span></span>

   <span data-ttu-id="22dce-172">このプロセスを完了するサービス レベル契約 (SLA) は、Microsoft がサブスクリプションを登録して必須の保持期間を使用すると通知 (および確認) された後、5 営業日です。</span><span class="sxs-lookup"><span data-stu-id="22dce-172">The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period.</span></span>

4. <span data-ttu-id="22dce-173">登録が完了したという通知を Microsoft から受け取った後、次のように Get-AzProviderFeature コマンドを実行して、登録の状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="22dce-173">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzProviderFeature command as follows.</span></span> <span data-ttu-id="22dce-174">確認された場合、Get-AzProviderFeatureコマンドは、Registration State プロパティの **[登録済** み] **の値を返** します。</span><span class="sxs-lookup"><span data-stu-id="22dce-174">If verified, the Get-AzProviderFeature command returns a value of **Registered** for the **Registration State** property.</span></span> <span data-ttu-id="22dce-175">サブスクリプションごとにこのアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="22dce-175">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. <span data-ttu-id="22dce-176">プロセスを完了するには、次のコマンドRegister-AzResourceProviderします。</span><span class="sxs-lookup"><span data-stu-id="22dce-176">To complete the process, run the Register-AzResourceProvider command.</span></span> <span data-ttu-id="22dce-177">サブスクリプションごとにこのアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="22dce-177">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="22dce-178">各サブスクリプションにプレミアム Azure Key Vault を作成する</span><span class="sxs-lookup"><span data-stu-id="22dce-178">Create a premium Azure Key Vault in each subscription</span></span>

<span data-ttu-id="22dce-179">キー コンテナーを作成する手順については、「Azure Key Vault の使用を開始する」に記載されています。このガイドでは [、Azure](/azure/key-vault/general/overview)PowerShell のインストールと起動、Azure サブスクリプションへの接続、リソース グループの作成、そのリソース グループ内のキー コンテナーの作成について説明します。</span><span class="sxs-lookup"><span data-stu-id="22dce-179">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](/azure/key-vault/general/overview), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="22dce-180">キー コンテナーを作成する場合は、SKU (Standard または Premium) を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22dce-180">When you create a key vault, you must choose a SKU: either Standard or Premium.</span></span> <span data-ttu-id="22dce-181">Standard SKU を使用すると、Azure Key Vault キーをソフトウェアで保護できます 。ハードウェア セキュリティ モジュール (HSM) キー保護はありません。また、Premium SKU では、キー コンテナー キーの保護のために HSM を使用できます。</span><span class="sxs-lookup"><span data-stu-id="22dce-181">The Standard SKU allows Azure Key Vault keys to be protected with software - there is no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys.</span></span> <span data-ttu-id="22dce-182">カスタマー キーは、いずれかの SKU を使用するキー コンテナーを受け入れ、プレミアム SKU のみを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22dce-182">Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU.</span></span> <span data-ttu-id="22dce-183">どちらの種類のキーを使用する操作のコストも同じなので、コストの唯一の違いは、各 HSM で保護されたキーの 1 か月あたりのコストです。</span><span class="sxs-lookup"><span data-stu-id="22dce-183">The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key.</span></span> <span data-ttu-id="22dce-184">詳細については [、「Key Vault の価格」](https://azure.microsoft.com/pricing/details/key-vault/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22dce-184">See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="22dce-185">実稼働データには Premium SKU キー コンテナーと HSM で保護されたキーを使用し、テストおよび検証の目的で標準 SKU キー コンテナーとキーのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="22dce-185">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span>

<span data-ttu-id="22dce-186">キー コンテナーに共通のプレフィックスを使用し、キー コンテナーとキーの使用とスコープの省略形を含める。</span><span class="sxs-lookup"><span data-stu-id="22dce-186">Use a common prefix for key vaults and include an abbreviation of the use and scope of the key vault and keys.</span></span> <span data-ttu-id="22dce-187">たとえば、コンテナーが北アメリカにある Contoso サービスの場合、名前の可能なペアは Contoso-O365-NA-VaultA1 と Contoso-O365-NA-VaultA2 です。</span><span class="sxs-lookup"><span data-stu-id="22dce-187">For example, for the Contoso service where the vaults will be located in North America, a possible pair of names is Contoso-O365-NA-VaultA1 and Contoso-O365-NA-VaultA2.</span></span> <span data-ttu-id="22dce-188">コンテナー名は Azure 内でグローバルに一意の文字列なので、目的の名前が既に他の Azure ユーザーによって要求されている場合に、目的の名前のバリエーションを試す必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="22dce-188">Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers.</span></span> <span data-ttu-id="22dce-189">構成が完了すると、コンテナー名を変更できないので、ベスト プラクティスは、セットアップ用の計画を作成し、2 人目を使用して計画が正しく実行されていることを確認する方法です。</span><span class="sxs-lookup"><span data-stu-id="22dce-189">Once configured, vault names cannot be changed, so the best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span>

<span data-ttu-id="22dce-190">可能であれば、ペア以外の領域にコンテナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="22dce-190">If possible, create your vaults in non-paired regions.</span></span> <span data-ttu-id="22dce-191">ペアリングされた Azure リージョンは、サービス障害ドメイン全体で高可用性を提供します。</span><span class="sxs-lookup"><span data-stu-id="22dce-191">Paired Azure regions provide high availability across service failure domains.</span></span> <span data-ttu-id="22dce-192">したがって、地域のペアは、互いにバックアップ領域と見なされます。</span><span class="sxs-lookup"><span data-stu-id="22dce-192">Therefore, regional pairs can be thought of as each other's backup region.</span></span> <span data-ttu-id="22dce-193">つまり、1 つの地域に配置された Azure リソースは、ペアリングされた地域を通じて自動的にフォールト トレランスを取得します。</span><span class="sxs-lookup"><span data-stu-id="22dce-193">This means that an Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region.</span></span> <span data-ttu-id="22dce-194">このため、データ暗号化ポリシーで使用される 2 つのコンテナーに対してリージョンを選択すると、領域がペアになります。つまり、可用性の合計 2 つの領域だけが使用されます。</span><span class="sxs-lookup"><span data-stu-id="22dce-194">For this reason, choosing regions for two vaults used in a data encryption policy where the regions are paired means that only a total of two regions of availability are in use.</span></span> <span data-ttu-id="22dce-195">ほとんどの地域には 2 つの地域しか存在しないので、ペアリングされていない地域をまだ選択できません。</span><span class="sxs-lookup"><span data-stu-id="22dce-195">Most geographies only have two regions, so it's not yet possible to select non-paired regions.</span></span> <span data-ttu-id="22dce-196">可能であれば、データ暗号化ポリシーで使用する 2 つのコンテナーに対して、ペアリングされていない 2 つの領域を選択します。</span><span class="sxs-lookup"><span data-stu-id="22dce-196">If possible, choose two non-paired regions for the two vaults used with a data encryption policy.</span></span> <span data-ttu-id="22dce-197">これは、可用性の合計 4 つの地域の恩恵を受ける。</span><span class="sxs-lookup"><span data-stu-id="22dce-197">This benefits from a total of four regions of availability.</span></span> <span data-ttu-id="22dce-198">詳細については [、「Business continuity and disaster recovery (BCDR): Azure Paired Regions](/azure/best-practices-availability-paired-regions) for current list of region pairs」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22dce-198">For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span>

### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="22dce-199">各キー コンテナーにアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="22dce-199">Assign permissions to each key vault</span></span>

<span data-ttu-id="22dce-200">キー コンテナーごとに、実装に応じて、顧客キーに対して 3 つの個別のアクセス許可セットを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22dce-200">For each key vault, you will need to define three separate sets of permissions for Customer Key, depending on your implementation.</span></span> <span data-ttu-id="22dce-201">たとえば、次のそれぞれに 1 つのアクセス許可セットを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22dce-201">For example, you will need to define one set of permissions for each of the following:</span></span>
  
- <span data-ttu-id="22dce-202">**組織のキー** コンテナーの毎日の管理を実行するキー コンテナー管理者。</span><span class="sxs-lookup"><span data-stu-id="22dce-202">**Key vault administrators** that will perform day-to-day management of your key vault for your organization.</span></span> <span data-ttu-id="22dce-203">これらのタスクには、バックアップ、作成、取得、インポート、リスト、復元が含まれます。</span><span class="sxs-lookup"><span data-stu-id="22dce-203">These tasks include backup, create, get, import, list, and restore.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="22dce-204">キー コンテナー管理者に割り当てられた一連のアクセス許可には、キーを削除するアクセス許可は含められていない。</span><span class="sxs-lookup"><span data-stu-id="22dce-204">The set of permissions assigned to key vault administrators does not include the permission to delete keys.</span></span> <span data-ttu-id="22dce-205">これは意図的で重要なプラクティスです。</span><span class="sxs-lookup"><span data-stu-id="22dce-205">This is intentional and an important practice.</span></span> <span data-ttu-id="22dce-206">暗号化キーを削除すると、データが完全に破棄されるので、通常は実行しません。</span><span class="sxs-lookup"><span data-stu-id="22dce-206">Deleting encryption keys is not typically done, since doing so permanently destroys data.</span></span> <span data-ttu-id="22dce-207">ベスト プラクティスとして、このアクセス許可をキー コンテナー管理者に既定で付与しない。</span><span class="sxs-lookup"><span data-stu-id="22dce-207">As a best practice, do not grant this permission to key vault administrators by default.</span></span> <span data-ttu-id="22dce-208">代わりに、これを重要なコンテナーの投稿者に予約し、結果の明確な理解が得られると、短期間で管理者に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="22dce-208">Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span>
  
  <span data-ttu-id="22dce-209">これらのアクセス許可を組織内のユーザーに割り当てるには、Azure PowerShell を使用して Azure サブスクリプションにログインします。</span><span class="sxs-lookup"><span data-stu-id="22dce-209">To assign these permissions to a user in your organization, log in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="22dce-210">手順については [、「Azure PowerShell でサインインする」を参照してください](/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="22dce-210">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

   <span data-ttu-id="22dce-211">必要なアクセスSet-AzKeyVaultAccessPolicy割り当てるには、このコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="22dce-211">Run the Set-AzKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   <span data-ttu-id="22dce-212">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="22dce-212">For example:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- <span data-ttu-id="22dce-213">Azure **Key Vault 自体の** アクセス許可を変更できるキー コンテナーの投稿者。</span><span class="sxs-lookup"><span data-stu-id="22dce-213">**Key vault contributors** that can change permissions on the Azure Key Vault itself.</span></span> <span data-ttu-id="22dce-214">従業員がチームを離れる、またはチームに参加する場合、またはキー コンテナー管理者がキーを削除または復元するためのアクセス許可を正当に必要とするまれな状況では、これらのアクセス許可を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22dce-214">You'll need to change these permissions as employees leave or join your team, or in the rare situation that the key vault administrators legitimately need permission to delete or restore a key.</span></span> <span data-ttu-id="22dce-215">この一連のキー コンテナー投稿者には、キー コンテナーの共同作成者ロールを付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22dce-215">This set of key vault contributors needs to be granted the Contributor role on your key vault.</span></span> <span data-ttu-id="22dce-216">このロールは、Azure リソース マネージャーを使用して割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="22dce-216">You can assign this role by using Azure Resource Manager.</span></span> <span data-ttu-id="22dce-217">詳細な手順については [、「Use Role-Based アクセス制御を使用](/azure/active-directory/role-based-access-control-configure) して Azure サブスクリプション リソースへのアクセスを管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22dce-217">For detailed steps, see [Use Role-Based Access Control](/azure/active-directory/role-based-access-control-configure) to manage access to your Azure subscription resources.</span></span> <span data-ttu-id="22dce-218">サブスクリプションを作成する管理者は、既定でこのアクセス権を持ち、他の管理者を共同作成者ロールに割り当てる機能を持っています。</span><span class="sxs-lookup"><span data-stu-id="22dce-218">The administrator who creates a subscription has this access by default, and the ability to assign other administrators to the Contributor role.</span></span>

- <span data-ttu-id="22dce-219">**テナント レベルで顧客キーの** 作業を行う、保存時の Microsoft 365 データ暗号化サービス。</span><span class="sxs-lookup"><span data-stu-id="22dce-219">**Microsoft 365 data at rest encryption service** that does the work of Customer Key at the tenant level.</span></span> <span data-ttu-id="22dce-220">Microsoft 365 にアクセス許可を付与するには、次の構文を使用して **Set-AzKeyVaultAccessPolicy** コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="22dce-220">To give permission to Microsoft 365, run the **Set-AzKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
   ```

  <span data-ttu-id="22dce-221">ここで、</span><span class="sxs-lookup"><span data-stu-id="22dce-221">Where:</span></span>

  - <span data-ttu-id="22dce-222">*コンテナー名* は、作成したキー コンテナーの名前です。</span><span class="sxs-lookup"><span data-stu-id="22dce-222">*vault name* is the name of the key vault you created.</span></span>

  <span data-ttu-id="22dce-223">例: 保存時の Microsoft 365 データ暗号化サービスの場合は  *、Microsoft 365 appID* を `c066d759-24ae-40e7-a56f-027002b5d3e4`</span><span class="sxs-lookup"><span data-stu-id="22dce-223">Example: For the Microsoft 365 Data at Rest Encryption service, replace  *Microsoft 365 appID* with `c066d759-24ae-40e7-a56f-027002b5d3e4`</span></span>

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a><span data-ttu-id="22dce-224">キー コンテナーでソフト削除を有効にして確認する</span><span class="sxs-lookup"><span data-stu-id="22dce-224">Enable and then confirm soft delete on your key vaults</span></span>

<span data-ttu-id="22dce-225">キーをすばやく回復できると、誤ってまたは悪意を持って削除されたキーが原因で、サービスの停止が長く発生する可能性が低い。</span><span class="sxs-lookup"><span data-stu-id="22dce-225">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys.</span></span> <span data-ttu-id="22dce-226">顧客キーでキーを使用する前に、Soft Delete と呼ばれるこの構成を有効にします。</span><span class="sxs-lookup"><span data-stu-id="22dce-226">Enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key.</span></span> <span data-ttu-id="22dce-227">Soft Delete を有効にすると、削除から 90 日以内にキーまたはコンテナーをバックアップから復元せずに復元できます。</span><span class="sxs-lookup"><span data-stu-id="22dce-227">Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="22dce-228">キー コンテナーで Soft Delete を有効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="22dce-228">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="22dce-229">Azure サブスクリプションにサインインし、Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="22dce-229">Sign in to your Azure subscription with Windows PowerShell.</span></span> <span data-ttu-id="22dce-230">手順については [、「Azure PowerShell でサインインする」を参照してください](/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="22dce-230">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="22dce-231">[Get-AzKeyVault コマンドレットを実行](/powershell/module/az.keyvault/get-azkeyvault)します。</span><span class="sxs-lookup"><span data-stu-id="22dce-231">Run the [Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet.</span></span> <span data-ttu-id="22dce-232">この例では、 *コンテナー名* は、ソフト削除を有効にするキー コンテナーの名前です。</span><span class="sxs-lookup"><span data-stu-id="22dce-232">In this example, *vault name* is the name of the key vault for which you are enabling soft delete:</span></span>

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. <span data-ttu-id="22dce-233">**Get-AzKeyVault** コマンドレットを実行して、キー コンテナーに対してソフト削除が構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="22dce-233">Confirm soft delete is configured for the key vault by running the **Get-AzKeyVault** cmdlet.</span></span> <span data-ttu-id="22dce-234">キー コンテナーに対してソフト削除が適切に構成されている場合 _、Soft Delete Enabled_ プロパティは True の値を返 **します**。</span><span class="sxs-lookup"><span data-stu-id="22dce-234">If soft delete is configured properly for the key vault, then the _Soft Delete Enabled_ property returns a value of **True**:</span></span>

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="22dce-235">キーを作成またはインポートして、各キー コンテナーにキーを追加する</span><span class="sxs-lookup"><span data-stu-id="22dce-235">Add a key to each key vault either by creating or importing a key</span></span>

<span data-ttu-id="22dce-236">Azure Key Vault にキーを追加するには、2 つの方法があります。Key Vault で直接キーを作成するか、キーをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="22dce-236">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key.</span></span> <span data-ttu-id="22dce-237">Key Vault で直接キーを作成する方法は複雑ではありません。一方で、キーをインポートすると、キーの生成方法を完全に制御できます。</span><span class="sxs-lookup"><span data-stu-id="22dce-237">Creating a key directly in Key Vault is the less complicated method, while importing a key provides total control over how the key is generated.</span></span> <span data-ttu-id="22dce-238">RSA キーを使用します。</span><span class="sxs-lookup"><span data-stu-id="22dce-238">Use the RSA keys.</span></span> <span data-ttu-id="22dce-239">Azure Key Vault では、楕円曲線キーを使用した折り返しとラップ解除はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="22dce-239">Azure Key Vault doesn't support wrapping and unwrapping with elliptical curve keys.</span></span>
  
<span data-ttu-id="22dce-240">キー コンテナーにキーを直接作成するには、次のように [Add-AzKeyVaultKey コマンドレット](/powershell/module/az.keyvault/add-azkeyvaultkey) を実行します。</span><span class="sxs-lookup"><span data-stu-id="22dce-240">To create a key directly in your key vault, run the [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="22dce-241">ここで、</span><span class="sxs-lookup"><span data-stu-id="22dce-241">Where:</span></span>

- <span data-ttu-id="22dce-242">*コンテナー名* は、キーを作成するキー コンテナーの名前です。</span><span class="sxs-lookup"><span data-stu-id="22dce-242">*vault name* is the name of the key vault in which you want to create the key.</span></span>

- <span data-ttu-id="22dce-243">*キー名* は、新しいキーを指定する名前です。</span><span class="sxs-lookup"><span data-stu-id="22dce-243">*key name* is the name you want to give the new key.</span></span>

  > [!TIP]
  > <span data-ttu-id="22dce-244">キー コンテナーの上記と同様の名前付け規則を使用してキーに名前を付ける。</span><span class="sxs-lookup"><span data-stu-id="22dce-244">Name keys using a similar naming convention as described above for key vaults.</span></span> <span data-ttu-id="22dce-245">この方法では、キー名のみを表示するツールでは、文字列は自己記述型です。</span><span class="sxs-lookup"><span data-stu-id="22dce-245">This way, in tools that show only the key name, the string is self-describing.</span></span>
  
<span data-ttu-id="22dce-246">キーを HSM で保護する場合は、必ず **、Destination** パラメーターの値としてHSM を指定し、それ以外の場合は[ソフトウェア] を指定 **します**。</span><span class="sxs-lookup"><span data-stu-id="22dce-246">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the _Destination_ parameter, otherwise, specify **Software**.</span></span>

<span data-ttu-id="22dce-247">例えば、</span><span class="sxs-lookup"><span data-stu-id="22dce-247">For example,</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="22dce-248">キーの回復レベルを確認する</span><span class="sxs-lookup"><span data-stu-id="22dce-248">Check the recovery level of your keys</span></span>

<span data-ttu-id="22dce-249">Microsoft 365 では、Azure Key Vault サブスクリプションが [キャンセルしない] に設定され、顧客キーで使用されるキーの削除が有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="22dce-249">Microsoft 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled.</span></span> <span data-ttu-id="22dce-250">これを確認するには、キーの回復レベルを確認します。</span><span class="sxs-lookup"><span data-stu-id="22dce-250">You can confirm this by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="22dce-251">キーの回復レベルを確認するには、Azure PowerShell で、次のように Get-AzKeyVaultKeyコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="22dce-251">To check the recovery level of a key, in Azure PowerShell, run the Get-AzKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

<span data-ttu-id="22dce-252">Recovery _Level_ プロパティが **Recoverable+ProtectedSubscription** の値以外の値を返す場合は、この記事を確認し、サブスクリプションをキャンセルしないリストに入れる手順のすべてと、各キー コンテナーで "soft delete" を有効にしたことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22dce-252">If the _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, you will need to review this article and ensure that you have followed all of the steps to put the subscription on the Do Not Cancel list and that you enabled "soft delete" on each of your key vaults.</span></span> <span data-ttu-id="22dce-253">次に、電子メールの出力のスクリーンショット `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` を電子メールに送信 m365ck@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="22dce-253">Next, send a screenshot of the output of `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` in email to m365ck@microsoft.com.</span></span>

### <a name="back-up-azure-key-vault"></a><span data-ttu-id="22dce-254">Azure Key Vault のバックアップ</span><span class="sxs-lookup"><span data-stu-id="22dce-254">Back up Azure Key Vault</span></span>

<span data-ttu-id="22dce-255">作成直後またはキーに対する変更の直後に、バックアップを実行し、バックアップのコピーをオンラインとオフラインの両方で保存します。</span><span class="sxs-lookup"><span data-stu-id="22dce-255">Immediately following creation or any change to a key, perform a backup and store copies of the backup, both online and offline.</span></span> <span data-ttu-id="22dce-256">オフライン コピーを任意のネットワークに接続しない。</span><span class="sxs-lookup"><span data-stu-id="22dce-256">Don't connect offline copies to any network.</span></span> <span data-ttu-id="22dce-257">代わりに、物理的な安全または商用のストレージ施設に格納します。</span><span class="sxs-lookup"><span data-stu-id="22dce-257">Instead, store them in a physical safe or commercial storage facility.</span></span> <span data-ttu-id="22dce-258">障害が発生した場合にアクセスできる場所に、バックアップの少なくとも 1 つのコピーを格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22dce-258">At least one copy of the backup should be stored in a location that will be accessible if a disaster happens.</span></span> <span data-ttu-id="22dce-259">バックアップ BLOB は、Key Vault キーを完全に破棄するか、操作不能にレンダリングする場合にキー マテリアルを復元する唯一の手段です。</span><span class="sxs-lookup"><span data-stu-id="22dce-259">The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable.</span></span> <span data-ttu-id="22dce-260">Azure Key Vault の外部であり、Azure Key Vault にインポートされたキーは、顧客キーがキーを使用するために必要なメタデータが外部キーと一緒に存在しないので、バックアップとして修飾されません。</span><span class="sxs-lookup"><span data-stu-id="22dce-260">Keys that are external to Azure Key Vault and were imported to Azure Key Vault do not qualify as a backup because the metadata necessary for Customer Key to use the key does not exist with the external key.</span></span> <span data-ttu-id="22dce-261">顧客キーを使用した復元操作には、Azure Key Vault から取得したバックアップのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="22dce-261">Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key.</span></span> <span data-ttu-id="22dce-262">したがって、キーをアップロードまたは作成したら、Azure Key Vault のバックアップを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22dce-262">Therefore, it is essential that you make a backup of Azure Key Vault once a key is uploaded or created.</span></span>
  
<span data-ttu-id="22dce-263">Azure Key Vault キーのバックアップを作成するには [、Backup-AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) コマンドレットを次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="22dce-263">To create a backup of an Azure Key Vault key, run the [Backup-AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet as follows:</span></span>

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

<span data-ttu-id="22dce-264">出力ファイルで接尾辞を使用してください `.backup` 。</span><span class="sxs-lookup"><span data-stu-id="22dce-264">Ensure that your output file uses the suffix `.backup`.</span></span>
  
<span data-ttu-id="22dce-265">このコマンドレットから生成された出力ファイルは暗号化され、Azure Key Vault の外部では使用できません。</span><span class="sxs-lookup"><span data-stu-id="22dce-265">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault.</span></span> <span data-ttu-id="22dce-266">バックアップは、バックアップの取得元の Azure サブスクリプションにのみ復元できます。</span><span class="sxs-lookup"><span data-stu-id="22dce-266">The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
<span data-ttu-id="22dce-267">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="22dce-267">For example:</span></span>
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="22dce-268">Azure Key Vault 構成設定の検証</span><span class="sxs-lookup"><span data-stu-id="22dce-268">Validate Azure Key Vault configuration settings</span></span>

<span data-ttu-id="22dce-269">DEP でキーを使用する前に検証を実行する方法はオプションですが、強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="22dce-269">Performing validation before using keys in a DEP is optional, but highly recommended.</span></span> <span data-ttu-id="22dce-270">特に、このトピックで説明する以外のキーとコンテナーをセットアップする手順を使用する場合は、カスタマー キーを構成する前に Azure Key Vault リソースの正常性を検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22dce-270">In particular, if you use steps to set up your keys and vaults other than the ones described in this topic, you should validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="22dce-271">キーに get、wrapKey、および unwrapKey 操作が有効になっているか確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="22dce-271">To verify that your keys have get, wrapKey, and unwrapKey operations enabled:</span></span>
  
<span data-ttu-id="22dce-272">[Get-AzKeyVault コマンドレットを次](/powershell/module/az.keyvault/get-azkeyvault)のように実行します。</span><span class="sxs-lookup"><span data-stu-id="22dce-272">Run the [Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="22dce-273">出力で、アクセス ポリシーと、必要に応じて Microsoft 365 アプリ ID (GUID) を探します。</span><span class="sxs-lookup"><span data-stu-id="22dce-273">In the output, look for the Access Policy and for the Microsoft 365 app ID (GUID) as appropriate.</span></span> <span data-ttu-id="22dce-274">get、wrapKey、unwrapKey の 3 つの操作はすべて、[キーへのアクセス許可] の下に表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22dce-274">All three operations, get, wrapKey, and unwrapKey, must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="22dce-275">アクセス ポリシーの構成が正しくない場合は、次のように Set-AzKeyVaultAccessPolicyコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="22dce-275">If the access policy configuration is incorrect, run the Set-AzKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
```

<span data-ttu-id="22dce-276">例: 保存時の Microsoft 365 データ暗号化サービスの場合は  *、Microsoft 365 appID* を `c066d759-24ae-40e7-a56f-027002b5d3e4`</span><span class="sxs-lookup"><span data-stu-id="22dce-276">Example: For the Microsoft 365 Data at Rest Encryption service, replace  *Microsoft 365 appID* with `c066d759-24ae-40e7-a56f-027002b5d3e4`</span></span>

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

<span data-ttu-id="22dce-277">キーに有効期限が設定されていないことを確認するには [、Get-AzKeyVaultKey](/powershell/module/az.keyvault/get-azkeyvault) コマンドレットを次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="22dce-277">To verify that an expiration date is not set for your keys, run the [Get-AzKeyVaultKey](/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

<span data-ttu-id="22dce-278">期限切れのキーは顧客キーでは使用できません。また、期限切れのキーで試行された操作は失敗し、サービスが停止する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="22dce-278">An expired key cannot be used by Customer Key and operations attempted with an expired key will fail and possibly result in a service outage.</span></span> <span data-ttu-id="22dce-279">顧客キーで使用するキーには有効期限が設定されていないことを強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="22dce-279">We strongly recommend that keys used with Customer Key do not have an expiration date.</span></span> <span data-ttu-id="22dce-280">有効期限を設定すると、削除できませんが、別の日付に変更できます。</span><span class="sxs-lookup"><span data-stu-id="22dce-280">An expiration date, once set, cannot be removed, but can be changed to a different date.</span></span> <span data-ttu-id="22dce-281">有効期限が設定されているキーを使用する必要がある場合は、有効期限の値を 12/31/9999 に変更します。</span><span class="sxs-lookup"><span data-stu-id="22dce-281">If a key must be used that has an expiration date set, change the expiration value to 12/31/9999.</span></span> <span data-ttu-id="22dce-282">有効期限が 12/31/9999 以外の日付に設定されているキーは、Microsoft 365 検証に合格しません。</span><span class="sxs-lookup"><span data-stu-id="22dce-282">Keys with an expiration date set to a date other than 12/31/9999 won't pass Microsoft 365 validation.</span></span>
  
<span data-ttu-id="22dce-283">12/31/9999 以外の値に設定されている有効期限を変更するには、次のように [Update-AzKeyVaultKey](/powershell/module/az.keyvault/update-azkeyvaultkey) コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="22dce-283">To change an expiration date that has been set to any value other than 12/31/9999, run the [Update-AzKeyVaultKey](/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="22dce-284">各 Azure Key Vault キーの URI を取得する</span><span class="sxs-lookup"><span data-stu-id="22dce-284">Obtain the URI for each Azure Key Vault key</span></span>

<span data-ttu-id="22dce-285">Azure のすべての手順を完了してキー コンテナーをセットアップし、キーを追加したら、次のコマンドを実行して、各キー コンテナーのキーの URI を取得します。</span><span class="sxs-lookup"><span data-stu-id="22dce-285">Once you've completed all the steps in Azure to set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault.</span></span> <span data-ttu-id="22dce-286">後で各 DEP を作成して割り当てる場合は、これらの URI を使用する必要があります。そのため、この情報を安全な場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="22dce-286">You will need to use these URIs when you create and assign each DEP later, so save this information in a safe place.</span></span> <span data-ttu-id="22dce-287">キー コンテナーごとにこのコマンドを 1 回実行してください。</span><span class="sxs-lookup"><span data-stu-id="22dce-287">Remember to run this command once for each key vault.</span></span>
  
<span data-ttu-id="22dce-288">Azure PowerShell では、次の情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="22dce-288">In Azure PowerShell:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="set-up-the-customer-key-encryption-policy-for-your-tenant"></a><span data-ttu-id="22dce-289">テナントの顧客キー暗号化ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="22dce-289">Set up the Customer Key encryption policy for your tenant</span></span>

<span data-ttu-id="22dce-290">これらのコマンドレットを実行するには、アクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="22dce-290">You need to be assigned permissions before you can run these cmdlets.</span></span> <span data-ttu-id="22dce-291">この記事ではコマンドレットのすべてのパラメーターを一覧表示しますが、割り当てられたアクセス許可にパラメーターが含まれていない場合は、一部のパラメーターにアクセスできない場合があります。</span><span class="sxs-lookup"><span data-stu-id="22dce-291">Although this article lists all parameters for the cmdlets, you may not have access to some parameters if they're not included in the permissions assigned to you.</span></span> <span data-ttu-id="22dce-292">コマンドレットを組織内で実行するために必要になるアクセス許可とパラメーターを調べるには、「 [Find the permissions required to run any Exchange cmdlet](/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22dce-292">To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions).</span></span>

### <a name="create-policy"></a><span data-ttu-id="22dce-293">ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="22dce-293">Create policy</span></span>

```powershell
   New-M365DataAtRestEncryptionPolicy [-Name] <String> -AzureKeyIDs <MultiValuedProperty> [-Description <String>]
```

<span data-ttu-id="22dce-294">説明: コンプライアンス管理者を有効にして、2 つの AKV ルート キーを使用して新しいデータ暗号化ポリシー (DEP) を作成します。</span><span class="sxs-lookup"><span data-stu-id="22dce-294">Description: Enable compliance admin to create a new data encryption policy (DEP) using two AKV root keys.</span></span> <span data-ttu-id="22dce-295">作成したポリシーは、このコマンドレットを使用してSet-M365DataAtRestEncryptionPolicyAssignmentできます。</span><span class="sxs-lookup"><span data-stu-id="22dce-295">Once created, a policy can then be assigned using Set-M365DataAtRestEncryptionPolicyAssignment cmdlet.</span></span> <span data-ttu-id="22dce-296">キーを最初に割り当て、またはキーを回転した後、新しいキーを有効にするには最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="22dce-296">Upon first assignment of keys or after you rotate keys, it can take up to 24 hours for the new keys to take effect.</span></span> <span data-ttu-id="22dce-297">新しい DEP の有効時間が 24 時間を超える場合は、Microsoft にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="22dce-297">If the new DEP takes more than 24 hours to take effect, contact Microsoft.</span></span>

<span data-ttu-id="22dce-298">例:</span><span class="sxs-lookup"><span data-stu-id="22dce-298">Example:</span></span>

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Default_Policy" -AzureKeyIDs "https://contosoWestUSvault01.vault.azure.net/keys/Key_01","https://contosoEastUSvault01.vault.azure.net/keys/Key_02" -Description "Tenant default policy"
```

<span data-ttu-id="22dce-299">パラメータ :</span><span class="sxs-lookup"><span data-stu-id="22dce-299">Parameters:</span></span>

| <span data-ttu-id="22dce-300">名前</span><span class="sxs-lookup"><span data-stu-id="22dce-300">Name</span></span> | <span data-ttu-id="22dce-301">説明</span><span class="sxs-lookup"><span data-stu-id="22dce-301">Description</span></span> | <span data-ttu-id="22dce-302">オプション (Y/N)</span><span class="sxs-lookup"><span data-stu-id="22dce-302">Optional (Y/N)</span></span> |
|----------|----------|---------|
|<span data-ttu-id="22dce-303">名前</span><span class="sxs-lookup"><span data-stu-id="22dce-303">Name</span></span>|<span data-ttu-id="22dce-304">データ暗号化ポリシーの表示名</span><span class="sxs-lookup"><span data-stu-id="22dce-304">Friendly name of the data encryption policy</span></span>|<span data-ttu-id="22dce-305">×</span><span class="sxs-lookup"><span data-stu-id="22dce-305">N</span></span>|
|<span data-ttu-id="22dce-306">AzureKeyIDs</span><span class="sxs-lookup"><span data-stu-id="22dce-306">AzureKeyIDs</span></span>|<span data-ttu-id="22dce-307">データ暗号化ポリシーに関連付ける Azure Key Vault キーの 2 つの URI 値をコンマで区切って指定します。</span><span class="sxs-lookup"><span data-stu-id="22dce-307">Specifies two URI values of the Azure Key Vault keys, separated by a comma, to associate with the data encryption policy</span></span>|<span data-ttu-id="22dce-308">×</span><span class="sxs-lookup"><span data-stu-id="22dce-308">N</span></span>|
|<span data-ttu-id="22dce-309">説明</span><span class="sxs-lookup"><span data-stu-id="22dce-309">Description</span></span>|<span data-ttu-id="22dce-310">データ暗号化ポリシーの説明</span><span class="sxs-lookup"><span data-stu-id="22dce-310">Description of the data encryption policy</span></span>|<span data-ttu-id="22dce-311">×</span><span class="sxs-lookup"><span data-stu-id="22dce-311">N</span></span>|

### <a name="assign-policy"></a><span data-ttu-id="22dce-312">ポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="22dce-312">Assign policy</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "<Default_PolicyName or Default_PolicyID>"
```

<span data-ttu-id="22dce-313">説明: このコマンドレットは、既定のデータ暗号化ポリシーの構成に使用されます。</span><span class="sxs-lookup"><span data-stu-id="22dce-313">Description: This cmdlet is used for configuring default Data Encryption Policy.</span></span> <span data-ttu-id="22dce-314">このポリシーは、すべてのサポート ワークロードでデータを暗号化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="22dce-314">This policy will be used to then encrypt data across all support workloads.</span></span> 

<span data-ttu-id="22dce-315">例:</span><span class="sxs-lookup"><span data-stu-id="22dce-315">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "Default_PolicyName"
```

<span data-ttu-id="22dce-316">パラメータ :</span><span class="sxs-lookup"><span data-stu-id="22dce-316">Parameters:</span></span>

| <span data-ttu-id="22dce-317">名前</span><span class="sxs-lookup"><span data-stu-id="22dce-317">Name</span></span> | <span data-ttu-id="22dce-318">説明</span><span class="sxs-lookup"><span data-stu-id="22dce-318">Description</span></span> | <span data-ttu-id="22dce-319">オプション (Y/N)</span><span class="sxs-lookup"><span data-stu-id="22dce-319">Optional (Y/N)</span></span> |
|----------|----------|---------|
<span data-ttu-id="22dce-320">-DataEncryptionPolicy</span><span class="sxs-lookup"><span data-stu-id="22dce-320">-DataEncryptionPolicy</span></span>|<span data-ttu-id="22dce-321">割り当てる必要があるデータ暗号化ポリシーを指定します。ポリシー名またはポリシー ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="22dce-321">Specifies the data encryption policy that needs to be assigned; specify either the Policy Name or the Policy ID.</span></span>|<span data-ttu-id="22dce-322">×</span><span class="sxs-lookup"><span data-stu-id="22dce-322">N</span></span>|

### <a name="modify-or-refresh-policy"></a><span data-ttu-id="22dce-323">ポリシーの変更または更新</span><span class="sxs-lookup"><span data-stu-id="22dce-323">Modify or Refresh policy</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy [-Identity] <M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter> -Refresh [-Enabled <Boolean>] [-Name <String>] [-Description <String>]
```

<span data-ttu-id="22dce-324">説明: コマンドレットを使用して、既存のポリシーを変更または更新できます。</span><span class="sxs-lookup"><span data-stu-id="22dce-324">Description: The cmdlet can be used either to modify or refresh an existing policy.</span></span> <span data-ttu-id="22dce-325">また、ポリシーを有効または無効にするためにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="22dce-325">It can also be used to enable or disable a policy.</span></span> <span data-ttu-id="22dce-326">キーを最初に割り当て、またはキーを回転した後、新しいキーを有効にするには最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="22dce-326">Upon first assignment of keys or after you rotate keys, it can take up to 24 hours for the new keys to take effect.</span></span> <span data-ttu-id="22dce-327">新しい DEP の有効時間が 24 時間を超える場合は、Microsoft にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="22dce-327">If the new DEP takes more than 24 hours to take effect, contact Microsoft.</span></span>

<span data-ttu-id="22dce-328">例:</span><span class="sxs-lookup"><span data-stu-id="22dce-328">Examples:</span></span>

<span data-ttu-id="22dce-329">データ暗号化ポリシーを無効にします。</span><span class="sxs-lookup"><span data-stu-id="22dce-329">Disable a data encryption policy.</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "NAM Policy" -Enabled $false
```

<span data-ttu-id="22dce-330">データ暗号化ポリシーを更新します。</span><span class="sxs-lookup"><span data-stu-id="22dce-330">Refresh a data encryption policy.</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "EUR Policy" -Refresh
```

<span data-ttu-id="22dce-331">パラメータ :</span><span class="sxs-lookup"><span data-stu-id="22dce-331">Parameters:</span></span>

| <span data-ttu-id="22dce-332">名前</span><span class="sxs-lookup"><span data-stu-id="22dce-332">Name</span></span> | <span data-ttu-id="22dce-333">説明</span><span class="sxs-lookup"><span data-stu-id="22dce-333">Description</span></span> | <span data-ttu-id="22dce-334">オプション (Y/N)</span><span class="sxs-lookup"><span data-stu-id="22dce-334">Optional (Y/N)</span></span> |
|----------|----------|---------|
|<span data-ttu-id="22dce-335">-Identity</span><span class="sxs-lookup"><span data-stu-id="22dce-335">-Identity</span></span>|<span data-ttu-id="22dce-336">変更するデータ暗号化ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="22dce-336">Specifies the data encryption policy that you want to modify.</span></span>|<span data-ttu-id="22dce-337">×</span><span class="sxs-lookup"><span data-stu-id="22dce-337">N</span></span>|
|<span data-ttu-id="22dce-338">-Refresh</span><span class="sxs-lookup"><span data-stu-id="22dce-338">-Refresh</span></span>|<span data-ttu-id="22dce-339">Azure Key Vault で関連付けられたキーを回転した後、更新スイッチを使用してデータ暗号化ポリシーを更新します。</span><span class="sxs-lookup"><span data-stu-id="22dce-339">Use the Refresh switch to update the data encryption policy after you rotate any of the associated keys in the Azure Key Vault.</span></span> <span data-ttu-id="22dce-340">このスイッチで値を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="22dce-340">You don't need to specify a value with this switch.</span></span>|<span data-ttu-id="22dce-341">Y</span><span class="sxs-lookup"><span data-stu-id="22dce-341">Y</span></span>|
|<span data-ttu-id="22dce-342">-Enabled</span><span class="sxs-lookup"><span data-stu-id="22dce-342">-Enabled</span></span>|<span data-ttu-id="22dce-343">Enabled パラメーターは、データ暗号化ポリシーを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="22dce-343">The Enabled parameter enables or disable the data encryption policy.</span></span> <span data-ttu-id="22dce-344">ポリシーを無効にする前に、テナントからの割り当てを解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22dce-344">Before you disable a policy, you must unassign it from your tenant.</span></span> <span data-ttu-id="22dce-345">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="22dce-345">Valid values are:</span></span></br > <span data-ttu-id="22dce-346">$true: ポリシーが有効になっている</span><span class="sxs-lookup"><span data-stu-id="22dce-346">$true: The policy is enabled</span></span></br > <span data-ttu-id="22dce-347">$true: ポリシーを有効にします。これが既定値です。</span><span class="sxs-lookup"><span data-stu-id="22dce-347">$false: The policy is disabled.</span></span>|<span data-ttu-id="22dce-348">Y</span><span class="sxs-lookup"><span data-stu-id="22dce-348">Y</span></span>|
|<span data-ttu-id="22dce-349">-Name</span><span class="sxs-lookup"><span data-stu-id="22dce-349">-Name</span></span>|<span data-ttu-id="22dce-350">Name パラメーターは、データの暗号化ポリシーの一意の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="22dce-350">The Name parameter specifies the unique name for the data encryption policy.</span></span>|<span data-ttu-id="22dce-351">Y</span><span class="sxs-lookup"><span data-stu-id="22dce-351">Y</span></span>|
|<span data-ttu-id="22dce-352">-Description</span><span class="sxs-lookup"><span data-stu-id="22dce-352">-Description</span></span>|<span data-ttu-id="22dce-353">Description パラメーターは、データの暗号化ポリシーの省略可能な説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="22dce-353">The Description parameter specifies an optional description for the data encryption policy.</span></span>|<span data-ttu-id="22dce-354">Y</span><span class="sxs-lookup"><span data-stu-id="22dce-354">Y</span></span>|

### <a name="get-policy-details"></a><span data-ttu-id="22dce-355">ポリシーの詳細を取得する</span><span class="sxs-lookup"><span data-stu-id="22dce-355">Get policy details</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy [-Identity] <M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter>
```

<span data-ttu-id="22dce-356">説明: このコマンドレットは、テナント用に作成された M365DataAtRest 暗号化ポリシーのすべて、または特定のポリシーに関する詳細を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="22dce-356">Description: This cmdlet lists all of M365DataAtRest encryption policies that are created for the tenant or details about a specific policy.</span></span>

<span data-ttu-id="22dce-357">例:</span><span class="sxs-lookup"><span data-stu-id="22dce-357">Examples:</span></span>

<span data-ttu-id="22dce-358">この例では、組織内の M365DatAtRest 暗号化ポリシーの概要リストを返します。</span><span class="sxs-lookup"><span data-stu-id="22dce-358">This example returns a summary list of M365DatAtRest Encryption policies in the organization.</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy
```

<span data-ttu-id="22dce-359">この例では、"NAM Policy" という名前のデータ暗号化ポリシーの詳細情報を返します。</span><span class="sxs-lookup"><span data-stu-id="22dce-359">This example returns detailed information for the data encryption policy named "NAM Policy".</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy -Identity "NAM Policy"
```

<span data-ttu-id="22dce-360">パラメータ :</span><span class="sxs-lookup"><span data-stu-id="22dce-360">Parameters:</span></span>

| <span data-ttu-id="22dce-361">名前</span><span class="sxs-lookup"><span data-stu-id="22dce-361">Name</span></span> | <span data-ttu-id="22dce-362">説明</span><span class="sxs-lookup"><span data-stu-id="22dce-362">Description</span></span> | <span data-ttu-id="22dce-363">オプション (Y/N)</span><span class="sxs-lookup"><span data-stu-id="22dce-363">Optional (Y/N)</span></span> |
|----------|----------|---------|
|<span data-ttu-id="22dce-364">-Identity</span><span class="sxs-lookup"><span data-stu-id="22dce-364">-Identity</span></span>|<span data-ttu-id="22dce-365">詳細を一覧表示するデータ暗号化ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="22dce-365">Specifies the data encryption policy that you want to list the details for.</span></span>|<span data-ttu-id="22dce-366">Y</span><span class="sxs-lookup"><span data-stu-id="22dce-366">Y</span></span>|

### <a name="get-policy-assignment-info"></a><span data-ttu-id="22dce-367">ポリシーの割り当て情報を取得する</span><span class="sxs-lookup"><span data-stu-id="22dce-367">Get policy assignment info</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicyAssignment
```

<span data-ttu-id="22dce-368">説明: このコマンドレットには、現在テナントに割り当てられているポリシーが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="22dce-368">Description: This cmdlet lists the policy that’s currently assigned to the tenant.</span></span>

## <a name="offboarding-from-customer-key"></a><span data-ttu-id="22dce-369">顧客キーからのオフボード</span><span class="sxs-lookup"><span data-stu-id="22dce-369">Offboarding from Customer Key</span></span>

<span data-ttu-id="22dce-370">Microsoft で管理されているキーに戻す必要がある場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="22dce-370">If you need to revert back to Microsoft-managed keys, you can.</span></span> <span data-ttu-id="22dce-371">オフボードの場合、データは、個々のワークロードでサポートされる既定の暗号化を使用して再暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="22dce-371">When you offboard, your data is re-encrypted using default encryption supported by each individual workload.</span></span> <span data-ttu-id="22dce-372">たとえば、Exchange Online では、Microsoft 管理キーを使用した既定の暗号化がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="22dce-372">For example, Exchange Online supports default encryption using Microsoft-managed keys.</span></span>

<span data-ttu-id="22dce-373">テナント レベルで顧客キーからテナントをオフボードすることを決定した場合は、m365ck@microsoft.com でテナントのサービスを "無効にする" という電子メールによる要求で [Microsoft に連絡します](mailto:m365ck@microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="22dce-373">If you decided to offboard your tenant from Customer Key at the tenant level, reach out to Microsoft with a request through email to "disable" the service for the tenant at [m365ck@microsoft.com](mailto:m365ck@microsoft.com).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="22dce-374">オフボードは、データ削除と同じではありません。</span><span class="sxs-lookup"><span data-stu-id="22dce-374">Offboarding is not the same as a data purge.</span></span> <span data-ttu-id="22dce-375">データの削除は、Microsoft 365 から組織のデータを完全に暗号化削除しますが、オフボードは削除を行います。</span><span class="sxs-lookup"><span data-stu-id="22dce-375">A data purge permanently crypto-deletes your organization's data from Microsoft 365, offboarding does not.</span></span> <span data-ttu-id="22dce-376">テナント レベルのポリシーに対してデータ削除を実行できません。</span><span class="sxs-lookup"><span data-stu-id="22dce-376">You can't perform a data purge for a tenant-level policy.</span></span> <span data-ttu-id="22dce-377">データ削除パスの詳細については、「キーを取り消して、データ削除パス [プロセスを開始する」を参照してください](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)。</span><span class="sxs-lookup"><span data-stu-id="22dce-377">For information about data purge path, see [Revoke your keys and start the data purge path process](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process).</span></span>

## <a name="about-the-availability-key"></a><span data-ttu-id="22dce-378">可用性キーについて</span><span class="sxs-lookup"><span data-stu-id="22dce-378">About the availability key</span></span>

<span data-ttu-id="22dce-379">可用性キーの詳細については、「可用性キーについて [」を参照してください](customer-key-availability-key-understand.md)。</span><span class="sxs-lookup"><span data-stu-id="22dce-379">For information about the availability key, see [Learn about the availability key](customer-key-availability-key-understand.md).</span></span>

## <a name="key-rotation"></a><span data-ttu-id="22dce-380">キーの回転</span><span class="sxs-lookup"><span data-stu-id="22dce-380">Key rotation</span></span>

<span data-ttu-id="22dce-381">顧客キーで使用されるキーの回転またはローリングの詳細については、「顧客キーまたは可用性キーのロールまたはローテーション」 [を参照してください](customer-key-availability-key-roll.md)。</span><span class="sxs-lookup"><span data-stu-id="22dce-381">For information about rotating or rolling keys used with Customer Key, see [Roll or rotate a Customer Key or an availability key](customer-key-availability-key-roll.md).</span></span> <span data-ttu-id="22dce-382">DEP を更新して新しいバージョンのキーを使用する場合は、この記事で前述したように、Set-M365DataAtRestEncryptionPolicy コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="22dce-382">When you update the DEP to use the new version of the keys, you'll run the Set-M365DataAtRestEncryptionPolicy cmdlet as described earlier in this article.</span></span>

## <a name="related-articles"></a><span data-ttu-id="22dce-383">関連記事:</span><span class="sxs-lookup"><span data-stu-id="22dce-383">Related articles:</span></span>

- [<span data-ttu-id="22dce-384">カスタマー キーによるサービスの暗号化</span><span class="sxs-lookup"><span data-stu-id="22dce-384">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="22dce-385">カスタマー キーまたは可用性キーをローリングまたはローテーションする</span><span class="sxs-lookup"><span data-stu-id="22dce-385">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="22dce-386">可用性キーの詳細</span><span class="sxs-lookup"><span data-stu-id="22dce-386">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="22dce-387">サービスの暗号化</span><span class="sxs-lookup"><span data-stu-id="22dce-387">Service Encryption</span></span>](office-365-service-encryption.md)