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
ms.openlocfilehash: 7ffa9a8148a8ae699711b62da48cd2c856d48cac
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727480"
---
# <a name="overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview"></a><span data-ttu-id="abff3-103">テナント レベルでの Microsoft 365 のカスタマー キーの概要 (パブリック プレビュー)</span><span class="sxs-lookup"><span data-stu-id="abff3-103">Overview of Customer Key for Microsoft 365 at the tenant level (public preview)</span></span>

<span data-ttu-id="abff3-104">指定したキーを使用して、データ暗号化ポリシー (DEP) を作成し、テナントに割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="abff3-104">Using keys you provide, you can create a data encryption policy (DEP) and assign it to the tenant.</span></span> <span data-ttu-id="abff3-105">DEP は、次のワークロードのテナント全体のデータを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="abff3-105">The DEP encrypts data across the tenant for these workloads:</span></span>

- <span data-ttu-id="abff3-106">Teams チャット メッセージ (1:1 チャット、グループ チャット、会議チャット、チャネル会話)</span><span class="sxs-lookup"><span data-stu-id="abff3-106">Teams chat messages (1:1 chats, group chats, meeting chats and channel conversations)</span></span>
- <span data-ttu-id="abff3-107">Teams メディア メッセージ (画像、コード スニペット、ビデオ メッセージ、オーディオ メッセージ、Wiki イメージ)</span><span class="sxs-lookup"><span data-stu-id="abff3-107">Teams media messages (images, code snippets, video messages, audio messages, wiki images)</span></span>
- <span data-ttu-id="abff3-108">Teams の通話と Teams ストレージに保存されている会議の記録</span><span class="sxs-lookup"><span data-stu-id="abff3-108">Teams call and meeting recordings stored in Teams storage</span></span>
- <span data-ttu-id="abff3-109">Teams チャット通知</span><span class="sxs-lookup"><span data-stu-id="abff3-109">Teams chat notifications</span></span>
- <span data-ttu-id="abff3-110">Cortana による Teams チャットの提案</span><span class="sxs-lookup"><span data-stu-id="abff3-110">Teams chat suggestions by Cortana</span></span>
- <span data-ttu-id="abff3-111">Teams の状態メッセージ</span><span class="sxs-lookup"><span data-stu-id="abff3-111">Teams status messages</span></span>
- <span data-ttu-id="abff3-112">Exchange Online のユーザー情報とシグナル情報</span><span class="sxs-lookup"><span data-stu-id="abff3-112">User and signal information for Exchange Online</span></span>
- <span data-ttu-id="abff3-113">アプリケーション レベルでまだ暗号化されていない Exchange Online メールボックス</span><span class="sxs-lookup"><span data-stu-id="abff3-113">Exchange Online mailboxes that aren't already encrypted Customer Key DEPs at the application level</span></span>

<span data-ttu-id="abff3-114">Microsoft Teams の場合、テナント レベルの顧客キーは、DEP がテナントに割り当てられた時点から新しいデータを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="abff3-114">For Microsoft Teams, Customer Key at the tenant level encrypts new data from the time the DEP is assigned to the tenant.</span></span> <span data-ttu-id="abff3-115">パブリック プレビューでは、過去のデータの暗号化はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="abff3-115">Public preview does not support encrypting past data.</span></span> <span data-ttu-id="abff3-116">Exchange Online の場合、顧客キーは既存のデータと新しいデータを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="abff3-116">For Exchange Online, Customer Key encrypts all existing and new data.</span></span>

<span data-ttu-id="abff3-117">テナントごとに複数の DEP を作成できますが、任意の時点で 1 つの DEP のみを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="abff3-117">You can create multiple DEPs per tenant but can only assign one DEP at any point in time.</span></span> <span data-ttu-id="abff3-118">DEP を割り当てると、暗号化は自動的に開始されますが、テナントのサイズによっては完了に時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="abff3-118">When you assign the DEP, encryption begins automatically but can take some time to complete depending on the size of your tenant.</span></span>

## <a name="tenant-level-policies-add-broader-control-to-customer-key-for-microsoft-365"></a><span data-ttu-id="abff3-119">テナント レベルのポリシーは、Microsoft 365 の顧客キーに広範な制御を追加します。</span><span class="sxs-lookup"><span data-stu-id="abff3-119">Tenant level policies add broader control to Customer Key for Microsoft 365</span></span>

<span data-ttu-id="abff3-120">Exchange Online と Sharepoint Online 用に顧客キーが既に設定されている場合は、新しいテナント レベルのパブリック プレビューがどのように適合しているかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="abff3-120">If you already have Customer Key set up for Exchange Online and Sharepoint Online, here's how the new tenant-level public preview fits in.</span></span>

<span data-ttu-id="abff3-121">作成するテナント レベルの暗号化ポリシーは、Microsoft 365 の Microsoft Teams ワークロードおよび Exchange Online ワークロードのすべてのデータを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="abff3-121">The tenant-level encryption policy you create encrypts all data for the Microsoft Teams and Exchange Online workloads in Microsoft 365.</span></span> <span data-ttu-id="abff3-122">ただし、Exchange Online では、顧客キー DEP を個々のメールボックスに既に割り当て済みの場合、テナント レベルのポリシーはそれらの DEP を上書きされません。</span><span class="sxs-lookup"><span data-stu-id="abff3-122">However, for Exchange Online, if you have already assigned Customer Key DEPs to individual mailboxes, the tenant-level policy won't override those DEPs.</span></span> <span data-ttu-id="abff3-123">テナント レベルのポリシーは、メールボックス レベルの Customer Key DEP が既に割り当てられていないメールボックスのみを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="abff3-123">The tenant-level policy will only encrypt mailboxes that aren't assigned a mailbox level Customer Key DEP already.</span></span>

<span data-ttu-id="abff3-124">たとえば、Microsoft Teams ファイルと、OneDrive for Business および SharePoint に保存されている一部の Teams 呼び出しおよび会議記録は、SharePoint Online DEP によって暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="abff3-124">For example, Microsoft Teams files and some Teams call and meeting recordings that are saved in OneDrive for Business and SharePoint are encrypted by a SharePoint Online DEP.</span></span> <span data-ttu-id="abff3-125">単一の SharePoint Online DEP は、1 つの geo 内のコンテンツを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="abff3-125">A single SharePoint Online DEP encrypts content within a single geo.</span></span>

## <a name="set-up-customer-key-at-the-tenant-level-public-preview"></a><span data-ttu-id="abff3-126">テナント レベルで顧客キーを設定する (パブリック プレビュー)</span><span class="sxs-lookup"><span data-stu-id="abff3-126">Set up Customer Key at the tenant level (public preview)</span></span>

<span data-ttu-id="abff3-127">これらの手順は類似していますが、アプリケーション レベルで顧客キーを設定する手順と同じではありません。</span><span class="sxs-lookup"><span data-stu-id="abff3-127">These steps are similar but not identical to the steps for setting up Customer Key at the application level.</span></span> <span data-ttu-id="abff3-128">このパブリック プレビューは、テスト テナントのテスト データでのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="abff3-128">You should only use this public preview with test data in test tenants.</span></span> <span data-ttu-id="abff3-129">このリリースは、実稼働データや実稼働環境では使用しない。</span><span class="sxs-lookup"><span data-stu-id="abff3-129">Do not use this release with production data or in your production environment.</span></span> <span data-ttu-id="abff3-130">顧客キーの実稼働展開が既にある場合は、次の手順を使用して、テスト環境のテナント レベルで顧客キーを設定します。</span><span class="sxs-lookup"><span data-stu-id="abff3-130">If you already have a production deployment of Customer Key, use these steps to set up Customer Key at the tenant level in a test environment.</span></span>

<span data-ttu-id="abff3-131">これらのほとんどのタスクは、Azure PowerShell にリモートで接続して完了します。</span><span class="sxs-lookup"><span data-stu-id="abff3-131">You'll complete most of these tasks by remotely connecting to Azure PowerShell.</span></span> <span data-ttu-id="abff3-132">最適な結果を得る場合は、バージョン 4.4.0 以降の Azure PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="abff3-132">For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>

<span data-ttu-id="abff3-133">開始する前に、次の情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="abff3-133">Before you get started, make sure of the following:</span></span>

- <span data-ttu-id="abff3-134">テナント レベルで顧客キーを設定するには、コンプライアンス管理者の役割を持つ仕事または学校のアカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abff3-134">You'll need to use a work or school account that has the compliance admin role to set up Customer Key at the tenant level.</span></span>
- <span data-ttu-id="abff3-135">組織に適切なライセンスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="abff3-135">Ensure that you have the appropriate licensing for your organization.</span></span> <span data-ttu-id="abff3-136">クラウド サービス プロバイダーまたはクラウド サービス プロバイダーを使用して、支払マイクロソフトエンタープライズ契約 Azure サブスクリプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="abff3-136">Use a paid, invoiced Azure Subscription using either an Enterprise Agreement or a Cloud Service Provider.</span></span> <span data-ttu-id="abff3-137">Pay As You Go プランまたはクレジット カードを使用して購入した Azure サブスクリプションは、顧客キーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="abff3-137">Azure Subscriptions purchased using Pay As You Go plans or using a credit card aren't supported for Customer Key.</span></span> <span data-ttu-id="abff3-138">2020 年 4 月 1 日より、Office 365 のカスタマー キーは、Office 365 E5、M365 E5、M365 E5 コンプライアンス、M365 E5 情報保護 & ガバナンス SKU で提供されます。</span><span class="sxs-lookup"><span data-stu-id="abff3-138">Starting April 1, 2020, Customer Key in Office 365 is offered in Office 365 E5, M365 E5, M365 E5 Compliance, and M365 E5 Information Protection & Governance SKUs.</span></span> <span data-ttu-id="abff3-139">Office 365 Advanced Compliance SKU は、新しいライセンスの調達に使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="abff3-139">Office 365 Advanced Compliance SKU is no longer available for procuring new licenses.</span></span> <span data-ttu-id="abff3-140">既存のOffice 365 Advanced Compliance ライセンスは引き続きサポートされます。</span><span class="sxs-lookup"><span data-stu-id="abff3-140">Existing Office 365 Advanced Compliance licenses will continue to be supported.</span></span> <span data-ttu-id="abff3-141">適切なライセンスを持つテナントの下で少なくとも 1 つのライセンスでサービスを有効にできますが、サービスの恩恵を受けるすべてのユーザーが適切なライセンスを持つことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abff3-141">While the service can be enabled with a minimum of one license under the tenant having the appropriate license, you should still make sure all users that benefit from the service have appropriate licenses.</span></span>

### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="abff3-142">2 つの新しい Azure サブスクリプションを作成する</span><span class="sxs-lookup"><span data-stu-id="abff3-142">Create two new Azure subscriptions</span></span>

<span data-ttu-id="abff3-143">顧客キーには、データ暗号化ポリシー (DEP) ごとに 2 つのキーが必要です。</span><span class="sxs-lookup"><span data-stu-id="abff3-143">Customer Key requires two keys for each data encryption policy (DEP).</span></span> <span data-ttu-id="abff3-144">これを実現するには、2 つの Azure サブスクリプションを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abff3-144">To achieve this, you must create two Azure subscriptions.</span></span> <span data-ttu-id="abff3-145">ベスト プラクティスとして、組織の個別のメンバーが各サブスクリプションで 1 つのキーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abff3-145">As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription.</span></span> <span data-ttu-id="abff3-146">Microsoft 365 の暗号化キーを管理するには、これらの Azure サブスクリプションのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="abff3-146">Only use these Azure subscriptions to administer encryption keys for Microsoft 365.</span></span> <span data-ttu-id="abff3-147">これにより、オペレーターの 1 人が誤って、意図的に、または悪意を持って削除したり、責任を負うキーを誤って管理したりした場合に、組織が保護されます。</span><span class="sxs-lookup"><span data-stu-id="abff3-147">This protects your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible.</span></span>

<span data-ttu-id="abff3-148">組織に対して作成できる Azure サブスクリプションの数に実際的な制限はありません。</span><span class="sxs-lookup"><span data-stu-id="abff3-148">There is no practical limit to the number of Azure subscriptions that you can create for your organization.</span></span> <span data-ttu-id="abff3-149">このベスト プラクティスに従って、カスタマー キーで使用されるリソースを管理しながら、人的エラーの影響を最小限に抑えるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="abff3-149">Following this best practice helps minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span>

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="abff3-150">必須の保持期間を使用するように Azure サブスクリプションを登録する</span><span class="sxs-lookup"><span data-stu-id="abff3-150">Register Azure subscriptions to use a mandatory retention period</span></span>

<span data-ttu-id="abff3-151">ルート暗号化キーが一時的または永続的に失われると、サービス操作が中断したり、壊滅的な操作を受け入れ、データが失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="abff3-151">The temporary or permanent loss of root encryption keys can be disruptive or even catastrophic to service operation and can result in data loss.</span></span> <span data-ttu-id="abff3-152">このため、Customer Key で使用されるリソースには強力な保護が必要です。</span><span class="sxs-lookup"><span data-stu-id="abff3-152">For this reason, the resources used with Customer Key require strong protection.</span></span> <span data-ttu-id="abff3-153">Customer Key で使用される Azure リソースはすべて、既定の構成を超える保護メカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="abff3-153">All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration.</span></span> <span data-ttu-id="abff3-154">Azure サブスクリプションは、即時で取り消し可能な取り消しを防ぐ方法でタグ付けまたは登録できます。</span><span class="sxs-lookup"><span data-stu-id="abff3-154">Azure subscriptions can be tagged or registered in a way that will prevent immediate and irrevocable cancellation.</span></span> <span data-ttu-id="abff3-155">これは、必須の保持期間の登録と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="abff3-155">This is referred to as registering for a mandatory retention period.</span></span> <span data-ttu-id="abff3-156">必須の保持期間に Azure サブスクリプションを登録するために必要な手順では、Microsoft とのコラボレーションが必要です。</span><span class="sxs-lookup"><span data-stu-id="abff3-156">The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Microsoft.</span></span> <span data-ttu-id="abff3-157">このプロセスには最大 5 営業日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="abff3-157">This process can take up to five business days.</span></span> <span data-ttu-id="abff3-158">以前は、これは "キャンセルしない" と呼ばれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="abff3-158">Previously, this was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="abff3-159">Microsoft 365 チームに連絡する前に、カスタマー キーで使用する Azure サブスクリプションごとに次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abff3-159">Before contacting the Microsoft 365 team, you must perform the following steps for each Azure subscription that you use with Customer Key.</span></span> <span data-ttu-id="abff3-160">開始する前に [、Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) モジュールがインストールされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="abff3-160">Ensure that you have the [Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) module installed before you start.</span></span>

1. <span data-ttu-id="abff3-161">Azure PowerShell でサインインします。</span><span class="sxs-lookup"><span data-stu-id="abff3-161">Sign in with Azure PowerShell.</span></span> <span data-ttu-id="abff3-162">手順については [、「Azure PowerShell でサインインする」を参照してください](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="abff3-162">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="abff3-163">必須の保持Register-AzProviderFeature使用するサブスクリプションを登録するには、Register-AzProviderFeatureコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="abff3-163">Run the Register-AzProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span> <span data-ttu-id="abff3-164">サブスクリプションごとにこのアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="abff3-164">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. <span data-ttu-id="abff3-165">Microsoft に問い合わせ、プロセスを完了[m365ck@microsoft.com。](mailto:m365ck@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="abff3-165">Contact Microsoft to have the process finalized at [m365ck@microsoft.com](mailto:m365ck@microsoft.com).</span></span> <span data-ttu-id="abff3-166">メールに次の情報を含める。</span><span class="sxs-lookup"><span data-stu-id="abff3-166">Include the following in your email:</span></span>

   <span data-ttu-id="abff3-167">**件名**: 顧客キー \<*Your tenant's fully-qualified domain name*\></span><span class="sxs-lookup"><span data-stu-id="abff3-167">**Subject**: Customer Key for \<*Your tenant's fully-qualified domain name*\></span></span>

   <span data-ttu-id="abff3-168">**本文**: 必須の保持期間を確定するサブスクリプションの ID。</span><span class="sxs-lookup"><span data-stu-id="abff3-168">**Body**: Subscription IDs for which you want to have the mandatory retention period finalized.</span></span>
   <span data-ttu-id="abff3-169">各サブスクリプションのGet-AzProviderFeature出力。</span><span class="sxs-lookup"><span data-stu-id="abff3-169">The output of Get-AzProviderFeature for each subscription.</span></span>

   <span data-ttu-id="abff3-170">このプロセスを完了するサービス レベル契約 (SLA) は、Microsoft がサブスクリプションを登録して必須の保持期間を使用すると通知 (および確認) された後、5 営業日です。</span><span class="sxs-lookup"><span data-stu-id="abff3-170">The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period.</span></span>

4. <span data-ttu-id="abff3-171">登録が完了したという通知を Microsoft から受け取った後、次のように Get-AzProviderFeature コマンドを実行して、登録の状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="abff3-171">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzProviderFeature command as follows.</span></span> <span data-ttu-id="abff3-172">確認された場合、Get-AzProviderFeatureコマンドは、Registration State プロパティの **[登録済** み] **の値を返** します。</span><span class="sxs-lookup"><span data-stu-id="abff3-172">If verified, the Get-AzProviderFeature command returns a value of **Registered** for the **Registration State** property.</span></span> <span data-ttu-id="abff3-173">サブスクリプションごとにこのアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="abff3-173">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. <span data-ttu-id="abff3-174">プロセスを完了するには、次のコマンドRegister-AzResourceProviderします。</span><span class="sxs-lookup"><span data-stu-id="abff3-174">To complete the process, run the Register-AzResourceProvider command.</span></span> <span data-ttu-id="abff3-175">サブスクリプションごとにこのアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="abff3-175">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="abff3-176">各サブスクリプションにプレミアム Azure Key Vault を作成する</span><span class="sxs-lookup"><span data-stu-id="abff3-176">Create a premium Azure Key Vault in each subscription</span></span>

<span data-ttu-id="abff3-177">キー コンテナーを作成する手順については、「Azure Key Vault の使用を開始する」に記載されています。このガイドでは [、Azure](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)PowerShell のインストールと起動、Azure サブスクリプションへの接続、リソース グループの作成、そのリソース グループ内のキー コンテナーの作成について説明します。</span><span class="sxs-lookup"><span data-stu-id="abff3-177">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="abff3-178">キー コンテナーを作成する場合は、SKU (Standard または Premium) を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abff3-178">When you create a key vault, you must choose a SKU: either Standard or Premium.</span></span> <span data-ttu-id="abff3-179">Standard SKU を使用すると、Azure Key Vault キーをソフトウェアで保護できます 。ハードウェア セキュリティ モジュール (HSM) キー保護はありません。また、Premium SKU では、キー コンテナー キーの保護のために HSM を使用できます。</span><span class="sxs-lookup"><span data-stu-id="abff3-179">The Standard SKU allows Azure Key Vault keys to be protected with software - there is no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys.</span></span> <span data-ttu-id="abff3-180">カスタマー キーは、いずれかの SKU を使用するキー コンテナーを受け入れ、プレミアム SKU のみを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abff3-180">Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU.</span></span> <span data-ttu-id="abff3-181">どちらの種類のキーを使用する操作のコストも同じなので、コストの唯一の違いは、各 HSM で保護されたキーの 1 か月あたりのコストです。</span><span class="sxs-lookup"><span data-stu-id="abff3-181">The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key.</span></span> <span data-ttu-id="abff3-182">詳細については [、「Key Vault の価格」](https://azure.microsoft.com/pricing/details/key-vault/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abff3-182">See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="abff3-183">実稼働データには Premium SKU キー コンテナーと HSM で保護されたキーを使用し、テストおよび検証の目的で標準 SKU キー コンテナーとキーのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="abff3-183">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span>

<span data-ttu-id="abff3-184">キー コンテナーに共通のプレフィックスを使用し、キー コンテナーとキーの使用とスコープの省略形を含める。</span><span class="sxs-lookup"><span data-stu-id="abff3-184">Use a common prefix for key vaults and include an abbreviation of the use and scope of the key vault and keys.</span></span> <span data-ttu-id="abff3-185">たとえば、コンテナーが北アメリカにある Contoso サービスの場合、名前の可能なペアは Contoso-O365-NA-VaultA1 と Contoso-O365-NA-VaultA2 です。</span><span class="sxs-lookup"><span data-stu-id="abff3-185">For example, for the Contoso service where the vaults will be located in North America, a possible pair of names is Contoso-O365-NA-VaultA1 and Contoso-O365-NA-VaultA2.</span></span> <span data-ttu-id="abff3-186">コンテナー名は Azure 内でグローバルに一意の文字列なので、目的の名前が既に他の Azure ユーザーによって要求されている場合に、目的の名前のバリエーションを試す必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="abff3-186">Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers.</span></span> <span data-ttu-id="abff3-187">構成が完了すると、コンテナー名を変更できないので、ベスト プラクティスは、セットアップ用の計画を作成し、2 人目を使用して計画が正しく実行されていることを確認する方法です。</span><span class="sxs-lookup"><span data-stu-id="abff3-187">Once configured, vault names cannot be changed, so the best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span>

<span data-ttu-id="abff3-188">可能であれば、ペア以外の領域にコンテナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="abff3-188">If possible, create your vaults in non-paired regions.</span></span> <span data-ttu-id="abff3-189">ペアリングされた Azure リージョンは、サービス障害ドメイン全体で高可用性を提供します。</span><span class="sxs-lookup"><span data-stu-id="abff3-189">Paired Azure regions provide high availability across service failure domains.</span></span> <span data-ttu-id="abff3-190">したがって、地域のペアは、互いにバックアップ領域と見なされます。</span><span class="sxs-lookup"><span data-stu-id="abff3-190">Therefore, regional pairs can be thought of as each other's backup region.</span></span> <span data-ttu-id="abff3-191">つまり、1 つの地域に配置された Azure リソースは、ペアリングされた地域を通じて自動的にフォールト トレランスを取得します。</span><span class="sxs-lookup"><span data-stu-id="abff3-191">This means that an Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region.</span></span> <span data-ttu-id="abff3-192">このため、データ暗号化ポリシーで使用される 2 つのコンテナーに対してリージョンを選択すると、領域がペアになります。つまり、可用性の合計 2 つの領域だけが使用されます。</span><span class="sxs-lookup"><span data-stu-id="abff3-192">For this reason, choosing regions for two vaults used in a data encryption policy where the regions are paired means that only a total of two regions of availability are in use.</span></span> <span data-ttu-id="abff3-193">ほとんどの地域には 2 つの地域しか存在しないので、ペアリングされていない地域をまだ選択できません。</span><span class="sxs-lookup"><span data-stu-id="abff3-193">Most geographies only have two regions, so it's not yet possible to select non-paired regions.</span></span> <span data-ttu-id="abff3-194">可能であれば、データ暗号化ポリシーで使用する 2 つのコンテナーに対して、ペアリングされていない 2 つの領域を選択します。</span><span class="sxs-lookup"><span data-stu-id="abff3-194">If possible, choose two non-paired regions for the two vaults used with a data encryption policy.</span></span> <span data-ttu-id="abff3-195">これは、可用性の合計 4 つの地域の恩恵を受ける。</span><span class="sxs-lookup"><span data-stu-id="abff3-195">This benefits from a total of four regions of availability.</span></span> <span data-ttu-id="abff3-196">詳細については [、「Business continuity and disaster recovery (BCDR): Azure Paired Regions](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) for current list of region pairs」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abff3-196">For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span>

### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="abff3-197">各キー コンテナーにアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="abff3-197">Assign permissions to each key vault</span></span>

<span data-ttu-id="abff3-198">キー コンテナーごとに、実装に応じて、顧客キーに対して 3 つの個別のアクセス許可セットを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abff3-198">For each key vault, you will need to define three separate sets of permissions for Customer Key, depending on your implementation.</span></span> <span data-ttu-id="abff3-199">たとえば、次のそれぞれに 1 つのアクセス許可セットを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abff3-199">For example, you will need to define one set of permissions for each of the following:</span></span>
  
- <span data-ttu-id="abff3-200">**組織のキー** コンテナーの毎日の管理を実行するキー コンテナー管理者。</span><span class="sxs-lookup"><span data-stu-id="abff3-200">**Key vault administrators** that will perform day-to-day management of your key vault for your organization.</span></span> <span data-ttu-id="abff3-201">これらのタスクには、バックアップ、作成、取得、インポート、リスト、復元が含まれます。</span><span class="sxs-lookup"><span data-stu-id="abff3-201">These tasks include backup, create, get, import, list, and restore.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="abff3-202">キー コンテナー管理者に割り当てられた一連のアクセス許可には、キーを削除するアクセス許可は含められていない。</span><span class="sxs-lookup"><span data-stu-id="abff3-202">The set of permissions assigned to key vault administrators does not include the permission to delete keys.</span></span> <span data-ttu-id="abff3-203">これは意図的で重要なプラクティスです。</span><span class="sxs-lookup"><span data-stu-id="abff3-203">This is intentional and an important practice.</span></span> <span data-ttu-id="abff3-204">暗号化キーを削除すると、データが完全に破棄されるので、通常は実行しません。</span><span class="sxs-lookup"><span data-stu-id="abff3-204">Deleting encryption keys is not typically done, since doing so permanently destroys data.</span></span> <span data-ttu-id="abff3-205">ベスト プラクティスとして、このアクセス許可をキー コンテナー管理者に既定で付与しない。</span><span class="sxs-lookup"><span data-stu-id="abff3-205">As a best practice, do not grant this permission to key vault administrators by default.</span></span> <span data-ttu-id="abff3-206">代わりに、これを重要なコンテナーの投稿者に予約し、結果の明確な理解が得られると、短期間で管理者に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="abff3-206">Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span>
  
  <span data-ttu-id="abff3-207">これらのアクセス許可を組織内のユーザーに割り当てるには、Azure PowerShell を使用して Azure サブスクリプションにログインします。</span><span class="sxs-lookup"><span data-stu-id="abff3-207">To assign these permissions to a user in your organization, log in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="abff3-208">手順については [、「Azure PowerShell でサインインする」を参照してください](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="abff3-208">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

   <span data-ttu-id="abff3-209">必要なアクセスSet-AzKeyVaultAccessPolicy割り当てるには、このコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="abff3-209">Run the Set-AzKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   <span data-ttu-id="abff3-210">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="abff3-210">For example:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- <span data-ttu-id="abff3-211">Azure **Key Vault 自体の** アクセス許可を変更できるキー コンテナーの投稿者。</span><span class="sxs-lookup"><span data-stu-id="abff3-211">**Key vault contributors** that can change permissions on the Azure Key Vault itself.</span></span> <span data-ttu-id="abff3-212">従業員がチームを離れる、またはチームに参加する場合、またはキー コンテナー管理者がキーを削除または復元するためのアクセス許可を正当に必要とするまれな状況では、これらのアクセス許可を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abff3-212">You'll need to change these permissions as employees leave or join your team, or in the rare situation that the key vault administrators legitimately need permission to delete or restore a key.</span></span> <span data-ttu-id="abff3-213">この一連のキー コンテナー投稿者には、キー コンテナーの共同作成者ロールを付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abff3-213">This set of key vault contributors needs to be granted the Contributor role on your key vault.</span></span> <span data-ttu-id="abff3-214">このロールは、Azure リソース マネージャーを使用して割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="abff3-214">You can assign this role by using Azure Resource Manager.</span></span> <span data-ttu-id="abff3-215">詳細な手順については [、「Use Role-Based アクセス制御を使用](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure) して Azure サブスクリプション リソースへのアクセスを管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abff3-215">For detailed steps, see [Use Role-Based Access Control](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure) to manage access to your Azure subscription resources.</span></span> <span data-ttu-id="abff3-216">サブスクリプションを作成する管理者は、既定でこのアクセス権を持ち、他の管理者を共同作成者ロールに割り当てる機能を持っています。</span><span class="sxs-lookup"><span data-stu-id="abff3-216">The administrator who creates a subscription has this access by default, and the ability to assign other administrators to the Contributor role.</span></span>

- <span data-ttu-id="abff3-217">**テナント レベルで顧客キーの** 作業を行う、保存時の Microsoft 365 データ暗号化サービス。</span><span class="sxs-lookup"><span data-stu-id="abff3-217">**Microsoft 365 data at rest encryption service** that does the work of Customer Key at the tenant level.</span></span> <span data-ttu-id="abff3-218">Microsoft 365 にアクセス許可を付与するには、次の構文を使用して **Set-AzKeyVaultAccessPolicy** コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="abff3-218">To give permission to Microsoft 365, run the **Set-AzKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
   ```

  <span data-ttu-id="abff3-219">ここで、</span><span class="sxs-lookup"><span data-stu-id="abff3-219">Where:</span></span>

  - <span data-ttu-id="abff3-220">*コンテナー名* は、作成したキー コンテナーの名前です。</span><span class="sxs-lookup"><span data-stu-id="abff3-220">*vault name* is the name of the key vault you created.</span></span>

  <span data-ttu-id="abff3-221">例: 保存時の Microsoft 365 データ暗号化サービスの場合は  *、Microsoft 365 appID* を `c066d759-24ae-40e7-a56f-027002b5d3e4`</span><span class="sxs-lookup"><span data-stu-id="abff3-221">Example: For the Microsoft 365 Data at Rest Encryption service, replace  *Microsoft 365 appID* with `c066d759-24ae-40e7-a56f-027002b5d3e4`</span></span>

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a><span data-ttu-id="abff3-222">キー コンテナーでソフト削除を有効にして確認する</span><span class="sxs-lookup"><span data-stu-id="abff3-222">Enable and then confirm soft delete on your key vaults</span></span>

<span data-ttu-id="abff3-223">キーをすばやく回復できると、誤ってまたは悪意を持って削除されたキーが原因で、サービスの停止が長く発生する可能性が低い。</span><span class="sxs-lookup"><span data-stu-id="abff3-223">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys.</span></span> <span data-ttu-id="abff3-224">顧客キーでキーを使用する前に、Soft Delete と呼ばれるこの構成を有効にします。</span><span class="sxs-lookup"><span data-stu-id="abff3-224">Enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key.</span></span> <span data-ttu-id="abff3-225">Soft Delete を有効にすると、削除から 90 日以内にキーまたはコンテナーをバックアップから復元せずに復元できます。</span><span class="sxs-lookup"><span data-stu-id="abff3-225">Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="abff3-226">キー コンテナーで Soft Delete を有効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="abff3-226">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="abff3-227">Azure サブスクリプションにサインインし、Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="abff3-227">Sign in to your Azure subscription with Windows PowerShell.</span></span> <span data-ttu-id="abff3-228">手順については [、「Azure PowerShell でサインインする」を参照してください](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="abff3-228">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="abff3-229">[Get-AzKeyVault コマンドレットを実行](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault)します。</span><span class="sxs-lookup"><span data-stu-id="abff3-229">Run the [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet.</span></span> <span data-ttu-id="abff3-230">この例では、 *コンテナー名* は、ソフト削除を有効にするキー コンテナーの名前です。</span><span class="sxs-lookup"><span data-stu-id="abff3-230">In this example, *vault name* is the name of the key vault for which you are enabling soft delete:</span></span>

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. <span data-ttu-id="abff3-231">**Get-AzKeyVault** コマンドレットを実行して、キー コンテナーに対してソフト削除が構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="abff3-231">Confirm soft delete is configured for the key vault by running the **Get-AzKeyVault** cmdlet.</span></span> <span data-ttu-id="abff3-232">キー コンテナーに対してソフト削除が適切に構成されている場合 _、Soft Delete Enabled_ プロパティは True の値を返 **します**。</span><span class="sxs-lookup"><span data-stu-id="abff3-232">If soft delete is configured properly for the key vault, then the _Soft Delete Enabled_ property returns a value of **True**:</span></span>

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="abff3-233">キーを作成またはインポートして、各キー コンテナーにキーを追加する</span><span class="sxs-lookup"><span data-stu-id="abff3-233">Add a key to each key vault either by creating or importing a key</span></span>

<span data-ttu-id="abff3-234">Azure Key Vault にキーを追加するには、2 つの方法があります。Key Vault で直接キーを作成するか、キーをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="abff3-234">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key.</span></span> <span data-ttu-id="abff3-235">Key Vault で直接キーを作成する方法は複雑ではありません。一方で、キーをインポートすると、キーの生成方法を完全に制御できます。</span><span class="sxs-lookup"><span data-stu-id="abff3-235">Creating a key directly in Key Vault is the less complicated method, while importing a key provides total control over how the key is generated.</span></span> <span data-ttu-id="abff3-236">RSA キーを使用します。</span><span class="sxs-lookup"><span data-stu-id="abff3-236">Use the RSA keys.</span></span> <span data-ttu-id="abff3-237">Azure Key Vault では、楕円曲線キーを使用した折り返しとラップ解除はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="abff3-237">Azure Key Vault doesn't support wrapping and unwrapping with elliptical curve keys.</span></span>
  
<span data-ttu-id="abff3-238">キー コンテナーにキーを直接作成するには、次のように [Add-AzKeyVaultKey コマンドレット](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) を実行します。</span><span class="sxs-lookup"><span data-stu-id="abff3-238">To create a key directly in your key vault, run the [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="abff3-239">ここで、</span><span class="sxs-lookup"><span data-stu-id="abff3-239">Where:</span></span>

- <span data-ttu-id="abff3-240">*コンテナー名* は、キーを作成するキー コンテナーの名前です。</span><span class="sxs-lookup"><span data-stu-id="abff3-240">*vault name* is the name of the key vault in which you want to create the key.</span></span>

- <span data-ttu-id="abff3-241">*キー名* は、新しいキーを指定する名前です。</span><span class="sxs-lookup"><span data-stu-id="abff3-241">*key name* is the name you want to give the new key.</span></span>

  > [!TIP]
  > <span data-ttu-id="abff3-242">キー コンテナーの上記と同様の名前付け規則を使用してキーに名前を付ける。</span><span class="sxs-lookup"><span data-stu-id="abff3-242">Name keys using a similar naming convention as described above for key vaults.</span></span> <span data-ttu-id="abff3-243">この方法では、キー名のみを表示するツールでは、文字列は自己記述型です。</span><span class="sxs-lookup"><span data-stu-id="abff3-243">This way, in tools that show only the key name, the string is self-describing.</span></span>
  
<span data-ttu-id="abff3-244">キーを HSM で保護する場合は、必ず **、Destination** パラメーターの値としてHSM を指定し、それ以外の場合は[ソフトウェア] を指定 **します**。</span><span class="sxs-lookup"><span data-stu-id="abff3-244">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the _Destination_ parameter, otherwise, specify **Software**.</span></span>

<span data-ttu-id="abff3-245">例えば、</span><span class="sxs-lookup"><span data-stu-id="abff3-245">For example,</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="abff3-246">キーの回復レベルを確認する</span><span class="sxs-lookup"><span data-stu-id="abff3-246">Check the recovery level of your keys</span></span>

<span data-ttu-id="abff3-247">Microsoft 365 では、Azure Key Vault サブスクリプションが [キャンセルしない] に設定され、顧客キーで使用されるキーの削除が有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="abff3-247">Microsoft 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled.</span></span> <span data-ttu-id="abff3-248">これを確認するには、キーの回復レベルを確認します。</span><span class="sxs-lookup"><span data-stu-id="abff3-248">You can confirm this by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="abff3-249">キーの回復レベルを確認するには、Azure PowerShell で、次のように Get-AzKeyVaultKeyコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="abff3-249">To check the recovery level of a key, in Azure PowerShell, run the Get-AzKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

<span data-ttu-id="abff3-250">Recovery _Level_ プロパティが **Recoverable+ProtectedSubscription** の値以外の値を返す場合は、この記事を確認し、サブスクリプションをキャンセルしないリストに入れる手順のすべてと、各キー コンテナーで "soft delete" を有効にしたことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abff3-250">If the _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, you will need to review this article and ensure that you have followed all of the steps to put the subscription on the Do Not Cancel list and that you enabled "soft delete" on each of your key vaults.</span></span> <span data-ttu-id="abff3-251">次に、電子メールの出力のスクリーンショット `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` を電子メールに送信m365ck@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="abff3-251">Next, send a screenshot of the output of `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` in email to m365ck@microsoft.com.</span></span>

### <a name="back-up-azure-key-vault"></a><span data-ttu-id="abff3-252">Azure Key Vault のバックアップ</span><span class="sxs-lookup"><span data-stu-id="abff3-252">Back up Azure Key Vault</span></span>

<span data-ttu-id="abff3-253">作成直後またはキーに対する変更の直後に、バックアップを実行し、バックアップのコピーをオンラインとオフラインの両方で保存します。</span><span class="sxs-lookup"><span data-stu-id="abff3-253">Immediately following creation or any change to a key, perform a backup and store copies of the backup, both online and offline.</span></span> <span data-ttu-id="abff3-254">オフライン コピーを任意のネットワークに接続しない。</span><span class="sxs-lookup"><span data-stu-id="abff3-254">Don't connect offline copies to any network.</span></span> <span data-ttu-id="abff3-255">代わりに、物理的な安全または商用のストレージ施設に格納します。</span><span class="sxs-lookup"><span data-stu-id="abff3-255">Instead, store them in a physical safe or commercial storage facility.</span></span> <span data-ttu-id="abff3-256">障害が発生した場合にアクセスできる場所に、バックアップの少なくとも 1 つのコピーを格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abff3-256">At least one copy of the backup should be stored in a location that will be accessible if a disaster happens.</span></span> <span data-ttu-id="abff3-257">バックアップ BLOB は、Key Vault キーを完全に破棄するか、操作不能にレンダリングする場合にキー マテリアルを復元する唯一の手段です。</span><span class="sxs-lookup"><span data-stu-id="abff3-257">The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable.</span></span> <span data-ttu-id="abff3-258">Azure Key Vault の外部であり、Azure Key Vault にインポートされたキーは、顧客キーがキーを使用するために必要なメタデータが外部キーと一緒に存在しないので、バックアップとして修飾されません。</span><span class="sxs-lookup"><span data-stu-id="abff3-258">Keys that are external to Azure Key Vault and were imported to Azure Key Vault do not qualify as a backup because the metadata necessary for Customer Key to use the key does not exist with the external key.</span></span> <span data-ttu-id="abff3-259">顧客キーを使用した復元操作には、Azure Key Vault から取得したバックアップのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="abff3-259">Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key.</span></span> <span data-ttu-id="abff3-260">したがって、キーをアップロードまたは作成したら、Azure Key Vault のバックアップを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abff3-260">Therefore, it is essential that you make a backup of Azure Key Vault once a key is uploaded or created.</span></span>
  
<span data-ttu-id="abff3-261">Azure Key Vault キーのバックアップを作成するには [、Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) コマンドレットを次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="abff3-261">To create a backup of an Azure Key Vault key, run the [Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet as follows:</span></span>

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

<span data-ttu-id="abff3-262">出力ファイルで接尾辞を使用してください `.backup` 。</span><span class="sxs-lookup"><span data-stu-id="abff3-262">Ensure that your output file uses the suffix `.backup`.</span></span>
  
<span data-ttu-id="abff3-263">このコマンドレットから生成された出力ファイルは暗号化され、Azure Key Vault の外部では使用できません。</span><span class="sxs-lookup"><span data-stu-id="abff3-263">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault.</span></span> <span data-ttu-id="abff3-264">バックアップは、バックアップの取得元の Azure サブスクリプションにのみ復元できます。</span><span class="sxs-lookup"><span data-stu-id="abff3-264">The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
<span data-ttu-id="abff3-265">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="abff3-265">For example:</span></span>
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="abff3-266">Azure Key Vault 構成設定の検証</span><span class="sxs-lookup"><span data-stu-id="abff3-266">Validate Azure Key Vault configuration settings</span></span>

<span data-ttu-id="abff3-267">DEP でキーを使用する前に検証を実行する方法はオプションですが、強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="abff3-267">Performing validation before using keys in a DEP is optional, but highly recommended.</span></span> <span data-ttu-id="abff3-268">特に、このトピックで説明する以外のキーとコンテナーをセットアップする手順を使用する場合は、カスタマー キーを構成する前に Azure Key Vault リソースの正常性を検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abff3-268">In particular, if you use steps to set up your keys and vaults other than the ones described in this topic, you should validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="abff3-269">キーに get、wrapKey、および unwrapKey 操作が有効になっているか確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="abff3-269">To verify that your keys have get, wrapKey, and unwrapKey operations enabled:</span></span>
  
<span data-ttu-id="abff3-270">[Get-AzKeyVault コマンドレットを次](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault)のように実行します。</span><span class="sxs-lookup"><span data-stu-id="abff3-270">Run the [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="abff3-271">出力で、アクセス ポリシーと、必要に応じて Microsoft 365 アプリ ID (GUID) を探します。</span><span class="sxs-lookup"><span data-stu-id="abff3-271">In the output, look for the Access Policy and for the Microsoft 365 app ID (GUID) as appropriate.</span></span> <span data-ttu-id="abff3-272">get、wrapKey、unwrapKey の 3 つの操作はすべて、[キーへのアクセス許可] の下に表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abff3-272">All three operations, get, wrapKey, and unwrapKey, must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="abff3-273">アクセス ポリシーの構成が正しくない場合は、次のように Set-AzKeyVaultAccessPolicyコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="abff3-273">If the access policy configuration is incorrect, run the Set-AzKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
```

<span data-ttu-id="abff3-274">例: 保存時の Microsoft 365 データ暗号化サービスの場合は  *、Microsoft 365 appID* を `c066d759-24ae-40e7-a56f-027002b5d3e4`</span><span class="sxs-lookup"><span data-stu-id="abff3-274">Example: For the Microsoft 365 Data at Rest Encryption service, replace  *Microsoft 365 appID* with `c066d759-24ae-40e7-a56f-027002b5d3e4`</span></span>

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

<span data-ttu-id="abff3-275">キーに有効期限が設定されていないことを確認するには [、Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) コマンドレットを次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="abff3-275">To verify that an expiration date is not set for your keys, run the [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

<span data-ttu-id="abff3-276">期限切れのキーは顧客キーでは使用できません。また、期限切れのキーで試行された操作は失敗し、サービスが停止する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="abff3-276">An expired key cannot be used by Customer Key and operations attempted with an expired key will fail and possibly result in a service outage.</span></span> <span data-ttu-id="abff3-277">顧客キーで使用するキーには有効期限が設定されていないことを強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="abff3-277">We strongly recommend that keys used with Customer Key do not have an expiration date.</span></span> <span data-ttu-id="abff3-278">有効期限を設定すると、削除できませんが、別の日付に変更できます。</span><span class="sxs-lookup"><span data-stu-id="abff3-278">An expiration date, once set, cannot be removed, but can be changed to a different date.</span></span> <span data-ttu-id="abff3-279">有効期限が設定されているキーを使用する必要がある場合は、有効期限の値を 12/31/9999 に変更します。</span><span class="sxs-lookup"><span data-stu-id="abff3-279">If a key must be used that has an expiration date set, change the expiration value to 12/31/9999.</span></span> <span data-ttu-id="abff3-280">有効期限が 12/31/9999 以外の日付に設定されているキーは、Microsoft 365 検証に合格しません。</span><span class="sxs-lookup"><span data-stu-id="abff3-280">Keys with an expiration date set to a date other than 12/31/9999 won't pass Microsoft 365 validation.</span></span>
  
<span data-ttu-id="abff3-281">12/31/9999 以外の値に設定されている有効期限を変更するには、次のように [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="abff3-281">To change an expiration date that has been set to any value other than 12/31/9999, run the [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="abff3-282">各 Azure Key Vault キーの URI を取得する</span><span class="sxs-lookup"><span data-stu-id="abff3-282">Obtain the URI for each Azure Key Vault key</span></span>

<span data-ttu-id="abff3-283">Azure のすべての手順を完了してキー コンテナーをセットアップし、キーを追加したら、次のコマンドを実行して、各キー コンテナーのキーの URI を取得します。</span><span class="sxs-lookup"><span data-stu-id="abff3-283">Once you've completed all the steps in Azure to set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault.</span></span> <span data-ttu-id="abff3-284">後で各 DEP を作成して割り当てる場合は、これらの URI を使用する必要があります。そのため、この情報を安全な場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="abff3-284">You will need to use these URIs when you create and assign each DEP later, so save this information in a safe place.</span></span> <span data-ttu-id="abff3-285">キー コンテナーごとにこのコマンドを 1 回実行してください。</span><span class="sxs-lookup"><span data-stu-id="abff3-285">Remember to run this command once for each key vault.</span></span>
  
<span data-ttu-id="abff3-286">Azure PowerShell では、次の情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="abff3-286">In Azure PowerShell:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="set-up-the-customer-key-encryption-policy-for-your-tenant"></a><span data-ttu-id="abff3-287">テナントの顧客キー暗号化ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="abff3-287">Set up the Customer Key encryption policy for your tenant</span></span>

<span data-ttu-id="abff3-288">これらのコマンドレットを実行するには、アクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="abff3-288">You need to be assigned permissions before you can run these cmdlets.</span></span> <span data-ttu-id="abff3-289">この記事ではコマンドレットのすべてのパラメーターを一覧表示しますが、割り当てられたアクセス許可にパラメーターが含まれていない場合は、一部のパラメーターにアクセスできない場合があります。</span><span class="sxs-lookup"><span data-stu-id="abff3-289">Although this article lists all parameters for the cmdlets, you may not have access to some parameters if they're not included in the permissions assigned to you.</span></span> <span data-ttu-id="abff3-290">コマンドレットを組織内で実行するために必要になるアクセス許可とパラメーターを調べるには、「 [Find the permissions required to run any Exchange cmdlet](https://docs.microsoft.com/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abff3-290">To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://docs.microsoft.com/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions).</span></span>

### <a name="create-policy"></a><span data-ttu-id="abff3-291">ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="abff3-291">Create policy</span></span>

```powershell
   New-M365DataAtRestEncryptionPolicy [-Name] <String> -AzureKeyIDs <MultiValuedProperty> [-Description <String>]
```

<span data-ttu-id="abff3-292">説明: コンプライアンス管理者を有効にして、2 つの AKV ルート キーを使用して新しいデータ暗号化ポリシー (DEP) を作成します。</span><span class="sxs-lookup"><span data-stu-id="abff3-292">Description: Enable compliance admin to create a new data encryption policy (DEP) using two AKV root keys.</span></span> <span data-ttu-id="abff3-293">作成したポリシーは、このコマンドレットを使用してSet-M365DataAtRestEncryptionPolicyAssignmentできます。</span><span class="sxs-lookup"><span data-stu-id="abff3-293">Once created, a policy can then be assigned using Set-M365DataAtRestEncryptionPolicyAssignment cmdlet.</span></span> <span data-ttu-id="abff3-294">キーを最初に割り当て、またはキーを回転した後、新しいキーを有効にするには最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="abff3-294">Upon first assignment of keys or after you rotate keys, it can take up to 24 hours for the new keys to take effect.</span></span> <span data-ttu-id="abff3-295">新しい DEP の有効時間が 24 時間を超える場合は、Microsoft にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="abff3-295">If the new DEP takes more than 24 hours to take effect, contact Microsoft.</span></span>

<span data-ttu-id="abff3-296">例:</span><span class="sxs-lookup"><span data-stu-id="abff3-296">Example:</span></span>

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Default_Policy" -AzureKeyIDs "https://contosoWestUSvault01.vault.azure.net/keys/Key_01","https://contosoEastUSvault01.vault.azure.net/keys/Key_02" -Description "Tenant default policy"
```

<span data-ttu-id="abff3-297">パラメータ :</span><span class="sxs-lookup"><span data-stu-id="abff3-297">Parameters:</span></span>

| <span data-ttu-id="abff3-298">名前</span><span class="sxs-lookup"><span data-stu-id="abff3-298">Name</span></span> | <span data-ttu-id="abff3-299">説明</span><span class="sxs-lookup"><span data-stu-id="abff3-299">Description</span></span> | <span data-ttu-id="abff3-300">オプション (Y/N)</span><span class="sxs-lookup"><span data-stu-id="abff3-300">Optional (Y/N)</span></span> |
|----------|----------|---------|
|<span data-ttu-id="abff3-301">名前</span><span class="sxs-lookup"><span data-stu-id="abff3-301">Name</span></span>|<span data-ttu-id="abff3-302">データ暗号化ポリシーの表示名</span><span class="sxs-lookup"><span data-stu-id="abff3-302">Friendly name of the data encryption policy</span></span>|<span data-ttu-id="abff3-303">×</span><span class="sxs-lookup"><span data-stu-id="abff3-303">N</span></span>|
|<span data-ttu-id="abff3-304">AzureKeyIDs</span><span class="sxs-lookup"><span data-stu-id="abff3-304">AzureKeyIDs</span></span>|<span data-ttu-id="abff3-305">データ暗号化ポリシーに関連付ける Azure Key Vault キーの 2 つの URI 値をコンマで区切って指定します。</span><span class="sxs-lookup"><span data-stu-id="abff3-305">Specifies two URI values of the Azure Key Vault keys, separated by a comma, to associate with the data encryption policy</span></span>|<span data-ttu-id="abff3-306">×</span><span class="sxs-lookup"><span data-stu-id="abff3-306">N</span></span>|
|<span data-ttu-id="abff3-307">説明</span><span class="sxs-lookup"><span data-stu-id="abff3-307">Description</span></span>|<span data-ttu-id="abff3-308">データ暗号化ポリシーの説明</span><span class="sxs-lookup"><span data-stu-id="abff3-308">Description of the data encryption policy</span></span>|<span data-ttu-id="abff3-309">×</span><span class="sxs-lookup"><span data-stu-id="abff3-309">N</span></span>|

### <a name="assign-policy"></a><span data-ttu-id="abff3-310">ポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="abff3-310">Assign policy</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy “<Default_PolicyName or Default_PolicyID>”
```

<span data-ttu-id="abff3-311">説明: このコマンドレットは、既定のデータ暗号化ポリシーの構成に使用されます。</span><span class="sxs-lookup"><span data-stu-id="abff3-311">Description: This cmdlet is used for configuring default Data Encryption Policy.</span></span> <span data-ttu-id="abff3-312">このポリシーは、すべてのサポート ワークロードでデータを暗号化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="abff3-312">This policy will be used to then encrypt data across all support workloads.</span></span> 

<span data-ttu-id="abff3-313">例:</span><span class="sxs-lookup"><span data-stu-id="abff3-313">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy “Default_PolicyName”
```

<span data-ttu-id="abff3-314">パラメータ :</span><span class="sxs-lookup"><span data-stu-id="abff3-314">Parameters:</span></span>

| <span data-ttu-id="abff3-315">名前</span><span class="sxs-lookup"><span data-stu-id="abff3-315">Name</span></span> | <span data-ttu-id="abff3-316">説明</span><span class="sxs-lookup"><span data-stu-id="abff3-316">Description</span></span> | <span data-ttu-id="abff3-317">オプション (Y/N)</span><span class="sxs-lookup"><span data-stu-id="abff3-317">Optional (Y/N)</span></span> |
|----------|----------|---------|
<span data-ttu-id="abff3-318">-DataEncryptionPolicy</span><span class="sxs-lookup"><span data-stu-id="abff3-318">-DataEncryptionPolicy</span></span>|<span data-ttu-id="abff3-319">割り当てる必要があるデータ暗号化ポリシーを指定します。ポリシー名またはポリシー ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="abff3-319">Specifies the data encryption policy that needs to be assigned; specify either the Policy Name or the Policy ID.</span></span>|<span data-ttu-id="abff3-320">×</span><span class="sxs-lookup"><span data-stu-id="abff3-320">N</span></span>|

### <a name="modify-or-refresh-policy"></a><span data-ttu-id="abff3-321">ポリシーの変更または更新</span><span class="sxs-lookup"><span data-stu-id="abff3-321">Modify or Refresh policy</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy [-Identity] <M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter> -Refresh [-Enabled <Boolean>] [-Name <String>] [-Description <String>]
```

<span data-ttu-id="abff3-322">説明: コマンドレットを使用して、既存のポリシーを変更または更新できます。</span><span class="sxs-lookup"><span data-stu-id="abff3-322">Description: The cmdlet can be used either to modify or refresh an existing policy.</span></span> <span data-ttu-id="abff3-323">また、ポリシーを有効または無効にするためにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="abff3-323">It can also be used to enable or disable a policy.</span></span> <span data-ttu-id="abff3-324">キーを最初に割り当て、またはキーを回転した後、新しいキーを有効にするには最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="abff3-324">Upon first assignment of keys or after you rotate keys, it can take up to 24 hours for the new keys to take effect.</span></span> <span data-ttu-id="abff3-325">新しい DEP の有効時間が 24 時間を超える場合は、Microsoft にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="abff3-325">If the new DEP takes more than 24 hours to take effect, contact Microsoft.</span></span>

<span data-ttu-id="abff3-326">例:</span><span class="sxs-lookup"><span data-stu-id="abff3-326">Examples:</span></span>

<span data-ttu-id="abff3-327">データ暗号化ポリシーを無効にします。</span><span class="sxs-lookup"><span data-stu-id="abff3-327">Disable a data encryption policy.</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "NAM Policy" -Enabled $false
```

<span data-ttu-id="abff3-328">データ暗号化ポリシーを更新します。</span><span class="sxs-lookup"><span data-stu-id="abff3-328">Refresh a data encryption policy.</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity “EUR Policy” -Refresh
```

<span data-ttu-id="abff3-329">パラメータ :</span><span class="sxs-lookup"><span data-stu-id="abff3-329">Parameters:</span></span>

| <span data-ttu-id="abff3-330">名前</span><span class="sxs-lookup"><span data-stu-id="abff3-330">Name</span></span> | <span data-ttu-id="abff3-331">説明</span><span class="sxs-lookup"><span data-stu-id="abff3-331">Description</span></span> | <span data-ttu-id="abff3-332">オプション (Y/N)</span><span class="sxs-lookup"><span data-stu-id="abff3-332">Optional (Y/N)</span></span> |
|----------|----------|---------|
|<span data-ttu-id="abff3-333">-Identity</span><span class="sxs-lookup"><span data-stu-id="abff3-333">-Identity</span></span>|<span data-ttu-id="abff3-334">変更するデータ暗号化ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="abff3-334">Specifies the data encryption policy that you want to modify.</span></span>|<span data-ttu-id="abff3-335">×</span><span class="sxs-lookup"><span data-stu-id="abff3-335">N</span></span>|
|<span data-ttu-id="abff3-336">-Refresh</span><span class="sxs-lookup"><span data-stu-id="abff3-336">-Refresh</span></span>|<span data-ttu-id="abff3-337">Azure Key Vault で関連付けられたキーを回転した後、更新スイッチを使用してデータ暗号化ポリシーを更新します。</span><span class="sxs-lookup"><span data-stu-id="abff3-337">Use the Refresh switch to update the data encryption policy after you rotate any of the associated keys in the Azure Key Vault.</span></span> <span data-ttu-id="abff3-338">このスイッチで値を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="abff3-338">You don't need to specify a value with this switch.</span></span>|<span data-ttu-id="abff3-339">Y</span><span class="sxs-lookup"><span data-stu-id="abff3-339">Y</span></span>|
|<span data-ttu-id="abff3-340">-Enabled</span><span class="sxs-lookup"><span data-stu-id="abff3-340">-Enabled</span></span>|<span data-ttu-id="abff3-341">Enabled パラメーターは、データ暗号化ポリシーを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="abff3-341">The Enabled parameter enables or disable the data encryption policy.</span></span> <span data-ttu-id="abff3-342">ポリシーを無効にする前に、テナントからの割り当てを解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abff3-342">Before you disable a policy, you must unassign it from your tenant.</span></span> <span data-ttu-id="abff3-343">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="abff3-343">Valid values are:</span></span></br > <span data-ttu-id="abff3-344">$true: ポリシーが有効になっている</span><span class="sxs-lookup"><span data-stu-id="abff3-344">$true: The policy is enabled</span></span></br > <span data-ttu-id="abff3-345">$true: ポリシーを有効にします。これが既定値です。</span><span class="sxs-lookup"><span data-stu-id="abff3-345">$false: The policy is disabled.</span></span>|<span data-ttu-id="abff3-346">Y</span><span class="sxs-lookup"><span data-stu-id="abff3-346">Y</span></span>|
|<span data-ttu-id="abff3-347">-Name</span><span class="sxs-lookup"><span data-stu-id="abff3-347">-Name</span></span>|<span data-ttu-id="abff3-348">Name パラメーターは、データの暗号化ポリシーの一意の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="abff3-348">The Name parameter specifies the unique name for the data encryption policy.</span></span>|<span data-ttu-id="abff3-349">Y</span><span class="sxs-lookup"><span data-stu-id="abff3-349">Y</span></span>|
|<span data-ttu-id="abff3-350">-Description</span><span class="sxs-lookup"><span data-stu-id="abff3-350">-Description</span></span>|<span data-ttu-id="abff3-351">Description パラメーターは、データの暗号化ポリシーの省略可能な説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="abff3-351">The Description parameter specifies an optional description for the data encryption policy.</span></span>|<span data-ttu-id="abff3-352">Y</span><span class="sxs-lookup"><span data-stu-id="abff3-352">Y</span></span>|

### <a name="get-policy-details"></a><span data-ttu-id="abff3-353">ポリシーの詳細を取得する</span><span class="sxs-lookup"><span data-stu-id="abff3-353">Get policy details</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy [-Identity] <M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter>
```

<span data-ttu-id="abff3-354">説明: このコマンドレットは、テナント用に作成された M365DataAtRest 暗号化ポリシーのすべて、または特定のポリシーに関する詳細を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="abff3-354">Description: This cmdlet lists all of M365DataAtRest encryption policies that are created for the tenant or details about a specific policy.</span></span>

<span data-ttu-id="abff3-355">例:</span><span class="sxs-lookup"><span data-stu-id="abff3-355">Examples:</span></span>

<span data-ttu-id="abff3-356">この例では、組織内の M365DatAtRest 暗号化ポリシーの概要リストを返します。</span><span class="sxs-lookup"><span data-stu-id="abff3-356">This example returns a summary list of M365DatAtRest Encryption policies in the organization.</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy
```

<span data-ttu-id="abff3-357">この例では、"NAM Policy" という名前のデータ暗号化ポリシーの詳細情報を返します。</span><span class="sxs-lookup"><span data-stu-id="abff3-357">This example returns detailed information for the data encryption policy named "NAM Policy".</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy -Identity "NAM Policy"
```

<span data-ttu-id="abff3-358">パラメータ :</span><span class="sxs-lookup"><span data-stu-id="abff3-358">Parameters:</span></span>

| <span data-ttu-id="abff3-359">名前</span><span class="sxs-lookup"><span data-stu-id="abff3-359">Name</span></span> | <span data-ttu-id="abff3-360">説明</span><span class="sxs-lookup"><span data-stu-id="abff3-360">Description</span></span> | <span data-ttu-id="abff3-361">オプション (Y/N)</span><span class="sxs-lookup"><span data-stu-id="abff3-361">Optional (Y/N)</span></span> |
|----------|----------|---------|
|<span data-ttu-id="abff3-362">-Identity</span><span class="sxs-lookup"><span data-stu-id="abff3-362">-Identity</span></span>|<span data-ttu-id="abff3-363">詳細を一覧表示するデータ暗号化ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="abff3-363">Specifies the data encryption policy that you want to list the details for.</span></span>|<span data-ttu-id="abff3-364">Y</span><span class="sxs-lookup"><span data-stu-id="abff3-364">Y</span></span>|

### <a name="get-policy-assignment-info"></a><span data-ttu-id="abff3-365">ポリシーの割り当て情報を取得する</span><span class="sxs-lookup"><span data-stu-id="abff3-365">Get policy assignment info</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicyAssignment
```

<span data-ttu-id="abff3-366">説明: このコマンドレットには、現在テナントに割り当てられているポリシーが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="abff3-366">Description: This cmdlet lists the policy that’s currently assigned to the tenant.</span></span>

## <a name="offboarding-from-customer-key"></a><span data-ttu-id="abff3-367">顧客キーからのオフボード</span><span class="sxs-lookup"><span data-stu-id="abff3-367">Offboarding from Customer Key</span></span>

<span data-ttu-id="abff3-368">Microsoft で管理されているキーに戻す必要がある場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="abff3-368">If you need to revert back to Microsoft-managed keys, you can.</span></span> <span data-ttu-id="abff3-369">オフボードの場合、データは、個々のワークロードでサポートされる既定の暗号化を使用して再暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="abff3-369">When you offboard, your data is re-encrypted using default encryption supported by each individual workload.</span></span> <span data-ttu-id="abff3-370">たとえば、Exchange Online では、Microsoft 管理キーを使用した既定の暗号化がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="abff3-370">For example, Exchange Online supports default encryption using Microsoft-managed keys.</span></span>

<span data-ttu-id="abff3-371">テナント レベルで顧客キーからテナントをオフボードすることを決定した場合は、m365ck@microsoft.com でテナントのサービスを "無効にする" という電子メールによる要求で [Microsoft に連絡します](mailto:m365ck@microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="abff3-371">If you decided to offboard your tenant from Customer Key at the tenant level, reach out to Microsoft with a request through email to “disable” the service for the tenant at [m365ck@microsoft.com](mailto:m365ck@microsoft.com).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="abff3-372">オフボードは、データ削除と同じではありません。</span><span class="sxs-lookup"><span data-stu-id="abff3-372">Offboarding is not the same as a data purge.</span></span> <span data-ttu-id="abff3-373">データの削除は、Microsoft 365 から組織のデータを完全に暗号化削除しますが、オフボードは削除を行います。</span><span class="sxs-lookup"><span data-stu-id="abff3-373">A data purge permanently crypto-deletes your organization's data from Microsoft 365, offboarding does not.</span></span> <span data-ttu-id="abff3-374">テナント レベルのポリシーに対してデータ削除を実行できません。</span><span class="sxs-lookup"><span data-stu-id="abff3-374">You can't perform a data purge for a tenant-level policy.</span></span> <span data-ttu-id="abff3-375">データ削除パスの詳細については、「キーを取り消して、データ削除パス [プロセスを開始する」を参照してください](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)。</span><span class="sxs-lookup"><span data-stu-id="abff3-375">For information about data purge path, see [Revoke your keys and start the data purge path process](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process).</span></span>

## <a name="about-the-availability-key"></a><span data-ttu-id="abff3-376">可用性キーについて</span><span class="sxs-lookup"><span data-stu-id="abff3-376">About the availability key</span></span>

<span data-ttu-id="abff3-377">可用性キーの詳細については、「可用性キーについて [」を参照してください](customer-key-availability-key-understand.md)。</span><span class="sxs-lookup"><span data-stu-id="abff3-377">For information about the availability key, see [Learn about the availability key](customer-key-availability-key-understand.md).</span></span>

## <a name="key-rotation"></a><span data-ttu-id="abff3-378">キーの回転</span><span class="sxs-lookup"><span data-stu-id="abff3-378">Key rotation</span></span>

<span data-ttu-id="abff3-379">顧客キーで使用されるキーの回転またはローリングの詳細については、「顧客キーまたは可用性キーのロールまたはローテーション」 [を参照してください](customer-key-availability-key-roll.md)。</span><span class="sxs-lookup"><span data-stu-id="abff3-379">For information about rotating or rolling keys used with Customer Key, see [Roll or rotate a Customer Key or an availability key](customer-key-availability-key-roll.md).</span></span> <span data-ttu-id="abff3-380">DEP を更新して新しいバージョンのキーを使用する場合は、この記事で前述したように、Set-M365DataAtRestEncryptionPolicy コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="abff3-380">When you update the DEP to use the new version of the keys, you'll run the Set-M365DataAtRestEncryptionPolicy cmdlet as described earlier in this article.</span></span>

## <a name="related-articles"></a><span data-ttu-id="abff3-381">関連記事:</span><span class="sxs-lookup"><span data-stu-id="abff3-381">Related articles:</span></span>

- [<span data-ttu-id="abff3-382">カスタマー キーによるサービスの暗号化</span><span class="sxs-lookup"><span data-stu-id="abff3-382">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="abff3-383">カスタマー キーまたは可用性キーをローリングまたはローテーションする</span><span class="sxs-lookup"><span data-stu-id="abff3-383">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="abff3-384">可用性キーの詳細</span><span class="sxs-lookup"><span data-stu-id="abff3-384">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="abff3-385">サービスの暗号化</span><span class="sxs-lookup"><span data-stu-id="abff3-385">Service Encryption</span></span>](office-365-service-encryption.md)
