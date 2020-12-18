---
title: テナント レベルでの Microsoft 365 のカスタマー キー (パブリック プレビュー)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/17/2020
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
description: Microsoft 365 テナント内のすべてのデータに対して顧客キーを設定する方法について説明します。
ms.openlocfilehash: eedf0e8c9d56131016bc798af8ae471df3005bdc
ms.sourcegitcommit: 0867495cb02d0b38b439b16bdce97e6eda483ba9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/18/2020
ms.locfileid: "49712529"
---
# <a name="overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview"></a><span data-ttu-id="ccddd-103">テナント レベルでの Microsoft 365 のカスタマー キーの概要 (パブリック プレビュー)</span><span class="sxs-lookup"><span data-stu-id="ccddd-103">Overview of Customer Key for Microsoft 365 at the tenant level (public preview)</span></span>

<span data-ttu-id="ccddd-104">入力したキーを使用して、データ暗号化ポリシー (DEP) を作成し、それをテナントに割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="ccddd-104">Using keys you provide, you can create a data encryption policy (DEP) and assign it to the tenant.</span></span> <span data-ttu-id="ccddd-105">DEP は、次のワークロードのデータをテナント全体で暗号化します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-105">The DEP encrypts data across the tenant for these workloads:</span></span>

- <span data-ttu-id="ccddd-106">Teams のチャット メッセージ (1 対 1 のチャット、グループ チャット、会議チャット、チャネル会話)</span><span class="sxs-lookup"><span data-stu-id="ccddd-106">Teams chat messages (1:1 chats, group chats, meeting chats and channel conversations)</span></span>
- <span data-ttu-id="ccddd-107">Teams のメディア メッセージ (画像、コード スニペット、ビデオ、Wiki 画像)</span><span class="sxs-lookup"><span data-stu-id="ccddd-107">Teams media messages (images, code snippets, videos, wiki images)</span></span>
- <span data-ttu-id="ccddd-108">Teams ストレージに保存された Teams の通話と会議のレコーディング</span><span class="sxs-lookup"><span data-stu-id="ccddd-108">Teams call and meeting recordings stored in Teams storage</span></span>
- <span data-ttu-id="ccddd-109">Teams のチャット通知</span><span class="sxs-lookup"><span data-stu-id="ccddd-109">Teams chat notifications</span></span>
- <span data-ttu-id="ccddd-110">Cortana による Teams チャットの提案</span><span class="sxs-lookup"><span data-stu-id="ccddd-110">Teams chat suggestions by Cortana</span></span>
- <span data-ttu-id="ccddd-111">Teams のステータス メッセージ</span><span class="sxs-lookup"><span data-stu-id="ccddd-111">Teams status messages</span></span>
- <span data-ttu-id="ccddd-112">Exchange Online のユーザー情報とシグナル情報</span><span class="sxs-lookup"><span data-stu-id="ccddd-112">User and signal information for Exchange Online</span></span>

<span data-ttu-id="ccddd-113">Microsoft Teams の場合、テナント レベルの顧客キーは、DEP がテナントに割り当てられた時点からの新しいデータを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-113">For Microsoft Teams, Customer Key at the tenant level encrypts new data from the time the DEP is assigned to the tenant.</span></span> <span data-ttu-id="ccddd-114">パブリック プレビューでは、過去のデータの暗号化はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ccddd-114">Public preview does not support encrypting past data.</span></span> <span data-ttu-id="ccddd-115">Exchange Online の場合、顧客キーは既存のデータと新しいデータのすべて暗号化を行います。</span><span class="sxs-lookup"><span data-stu-id="ccddd-115">For Exchange Online, Customer Key encrypts all existing and new data.</span></span>

<span data-ttu-id="ccddd-116">テナントごとに複数の DEP を作成できますが、任意の時点で割り当て可能な DEP は 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="ccddd-116">You can create multiple DEPs per tenant but can only assign one DEP at any point in time.</span></span> <span data-ttu-id="ccddd-117">DEP を割り当てると、暗号化は自動的に開始されますが、テナントのサイズによっては完了に時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ccddd-117">When you assign the DEP, encryption begins automatically but can take some time to complete depending on the size of your tenant.</span></span>

## <a name="tenant-level-policies-add-broader-control-to-customer-key-for-microsoft-365"></a><span data-ttu-id="ccddd-118">テナント レベルのポリシーにより、Microsoft 365 の顧客キーに対するより広範な制御が追加されます。</span><span class="sxs-lookup"><span data-stu-id="ccddd-118">Tenant level policies add broader control to Customer Key for Microsoft 365</span></span>

<span data-ttu-id="ccddd-119">Exchange Online と Sharepoint Online のカスタマー キーが既に設定されている場合は、新しいテナント レベルのパブリック プレビューがどのように適合しているかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-119">If you already have Customer Key set up for Exchange Online and Sharepoint Online, here's how the new tenant-level public preview fits in.</span></span>

<span data-ttu-id="ccddd-120">作成するテナント レベルの暗号化ポリシーは、Microsoft 365 の Microsoft Teams ワークロードと Exchange Online ワークロードのすべてのデータを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-120">The tenant-level encryption policy you create encrypts all data for the Microsoft Teams and Exchange Online workloads in Microsoft 365.</span></span> <span data-ttu-id="ccddd-121">このポリシーは、顧客キーで既に作成した微調整された DEP に干渉しません。</span><span class="sxs-lookup"><span data-stu-id="ccddd-121">This policy doesn't interfere with finely tuned DEPs you've already created in Customer Key.</span></span>

<span data-ttu-id="ccddd-122">例:</span><span class="sxs-lookup"><span data-stu-id="ccddd-122">Examples:</span></span>

<span data-ttu-id="ccddd-123">Microsoft Teams ファイルと、OneDrive for Business および SharePoint に保存されている一部の Teams 通話と会議のレコーディングは、SharePoint Online DEP によって暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="ccddd-123">Microsoft Teams files and some Teams call and meeting recordings that are saved in OneDrive for Business and SharePoint are encrypted by a SharePoint Online DEP.</span></span> <span data-ttu-id="ccddd-124">1 つの SharePoint Online DEP が単一の geo 内のコンテンツを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-124">A single SharePoint Online DEP encrypts content within a single geo.</span></span> <span data-ttu-id="ccddd-125">テナント レベルの DEP は、暗号化されたデータを新しいポリシーで再び暗号化します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-125">The tenant-level DEP will encrypt the encrypted data again with the new policy.</span></span>

<span data-ttu-id="ccddd-126">Exchange Online では、顧客キーを使用して 1 つ以上のユーザー メールボックスを暗号化する DEP を作成できます。</span><span class="sxs-lookup"><span data-stu-id="ccddd-126">For Exchange Online, you can create a DEP that encrypts one or more user mailboxes with Customer Key.</span></span> <span data-ttu-id="ccddd-127">テナント レベルのポリシーを作成する場合、そのポリシーは暗号化されたメールボックスを暗号化しなされません。</span><span class="sxs-lookup"><span data-stu-id="ccddd-127">When you create a tenant-level policy, that policy will not encrypt the encrypted mailboxes.</span></span> <span data-ttu-id="ccddd-128">ただし、テナント レベルのキーは、DEP の影響を受けしていないメールボックスを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-128">However,  the tenant-level key will encrypt the mailboxes that are not affected by a DEP already.</span></span>

## <a name="set-up-customer-key-at-the-tenant-level-public-preview"></a><span data-ttu-id="ccddd-129">テナント レベルで顧客キーを設定する (パブリック プレビュー)</span><span class="sxs-lookup"><span data-stu-id="ccddd-129">Set up Customer Key at the tenant level (public preview)</span></span>

<span data-ttu-id="ccddd-130">これらの手順は、アプリケーション レベルで顧客キーを設定する手順と似ていますが、同じではありません。</span><span class="sxs-lookup"><span data-stu-id="ccddd-130">These steps are similar but not identical to the steps for setting up Customer Key at the application level.</span></span> <span data-ttu-id="ccddd-131">このパブリック プレビューは、テスト テナントのテスト データでのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="ccddd-131">You should only use this public preview with test data in test tenants.</span></span> <span data-ttu-id="ccddd-132">このリリースは、実稼働データと一緒に使用したり、実稼働環境で使用したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ccddd-132">Do not use this release with production data or in your production environment.</span></span> <span data-ttu-id="ccddd-133">顧客キーの実稼働展開が既にある場合は、次の手順を使用して、テスト環境のテナント レベルで顧客キーを設定します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-133">If you already have a production deployment of Customer Key, use these steps to set up Customer Key at the tenant level in a test environment.</span></span>

<span data-ttu-id="ccddd-134">これらのタスクの大部分は、Azure PowerShell にリモートで接続することで完了します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-134">You'll complete most of these tasks by remotely connecting to Azure PowerShell.</span></span> <span data-ttu-id="ccddd-135">最善の結果を得る場合は、Azure PowerShell のバージョン 4.4.0 以降を使用してください。</span><span class="sxs-lookup"><span data-stu-id="ccddd-135">For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>

<span data-ttu-id="ccddd-136">開始する前に、次の情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="ccddd-136">Before you get started, make sure of the following:</span></span>

- <span data-ttu-id="ccddd-137">テナント レベルで顧客キーを設定するには、コンプライアンス管理者の役割を持つ、仕事または学校のアカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccddd-137">You'll need to use a work or school account that has the compliance admin role to set up Customer Key at the tenant level.</span></span>
- <span data-ttu-id="ccddd-138">組織に適したライセンスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccddd-138">Ensure that you have the appropriate licensing for your organization.</span></span> <span data-ttu-id="ccddd-139">サブスクリプションまたはクラウド サービス プロバイダーを使用して、有料マイクロソフトエンタープライズ契約 Azure サブスクリプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-139">Use a paid, invoiced Azure Subscription using either an Enterprise Agreement or a Cloud Service Provider.</span></span> <span data-ttu-id="ccddd-140">[お支払い方法] プランまたはクレジット カードを使用して購入した Azure サブスクリプションは、顧客キーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ccddd-140">Azure Subscriptions purchased using Pay As You Go plans or using a credit card aren't supported for Customer Key.</span></span> <span data-ttu-id="ccddd-141">2020 年 4 月 1 日から、Office 365 のカスタマー キーは、Office 365 E5、M365 E5、M365 E5 コンプライアンス、M365 E5 情報保護 & ガバナンス SKU で提供されます。</span><span class="sxs-lookup"><span data-stu-id="ccddd-141">Starting April 1, 2020, Customer Key in Office 365 is offered in Office 365 E5, M365 E5, M365 E5 Compliance, and M365 E5 Information Protection & Governance SKUs.</span></span> <span data-ttu-id="ccddd-142">Office 365 Advanced Compliance SKU は、新しいライセンスの調達には使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="ccddd-142">Office 365 Advanced Compliance SKU is no longer available for procuring new licenses.</span></span> <span data-ttu-id="ccddd-143">既存の Office 365 Advanced Compliance ライセンスは引き続きサポートされます。</span><span class="sxs-lookup"><span data-stu-id="ccddd-143">Existing Office 365 Advanced Compliance licenses will continue to be supported.</span></span> <span data-ttu-id="ccddd-144">適切なライセンスを持つテナントの下で少なくとも 1 つのライセンスでサービスを有効にできる一方で、サービスの恩恵を受けるすべてのユーザーが適切なライセンスを持つことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccddd-144">While the service can be enabled with a minimum of one license under the tenant having the appropriate license, you should still make sure all users that benefit from the service have appropriate licenses.</span></span> <span data-ttu-id="ccddd-145">次のいずれかのライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="ccddd-145">You'll need one of the following licenses:</span></span>

### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="ccddd-146">2 つの新しい Azure サブスクリプションを作成する</span><span class="sxs-lookup"><span data-stu-id="ccddd-146">Create two new Azure subscriptions</span></span>

<span data-ttu-id="ccddd-147">顧客キーには、データ暗号化ポリシー (DEP) ごとに 2 つのキーが必要です。</span><span class="sxs-lookup"><span data-stu-id="ccddd-147">Customer Key requires two keys for each data encryption policy (DEP).</span></span> <span data-ttu-id="ccddd-148">これを実現するには、2 つの Azure サブスクリプションを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccddd-148">To achieve this, you must create two Azure subscriptions.</span></span> <span data-ttu-id="ccddd-149">ベスト プラクティスとして、組織の個別のメンバーがサブスクリプションごとに 1 つのキーを構成する方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ccddd-149">As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription.</span></span> <span data-ttu-id="ccddd-150">これらの Azure サブスクリプションのみを使用して、Microsoft 365 の暗号化キーを管理します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-150">Only use these Azure subscriptions to administer encryption keys for Microsoft 365.</span></span> <span data-ttu-id="ccddd-151">これにより、オペレーターの 1 人が誤って、意図的に、または悪意を持って削除したり、責任を負うキーを誤って管理したりした場合に、組織を保護します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-151">This protects your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible.</span></span>

<span data-ttu-id="ccddd-152">組織で作成できる Azure サブスクリプションの数に実際的な制限はありません。</span><span class="sxs-lookup"><span data-stu-id="ccddd-152">There is no practical limit to the number of Azure subscriptions that you can create for your organization.</span></span> <span data-ttu-id="ccddd-153">このベスト プラクティスに従って、カスタマー キーで使用されるリソースを管理しながら、人的エラーの影響を最小限に抑えるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ccddd-153">Following this best practice helps minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span>

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="ccddd-154">Azure サブスクリプションを登録して必須の保持期間を使用する</span><span class="sxs-lookup"><span data-stu-id="ccddd-154">Register Azure subscriptions to use a mandatory retention period</span></span>

<span data-ttu-id="ccddd-155">ルート暗号化キーが一時的または永続的に失われると、サービス操作が中断したり、致命的な障害が発生したり、データが失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ccddd-155">The temporary or permanent loss of root encryption keys can be disruptive or even catastrophic to service operation and can result in data loss.</span></span> <span data-ttu-id="ccddd-156">このため、顧客キーで使用されるリソースには強力な保護が必要です。</span><span class="sxs-lookup"><span data-stu-id="ccddd-156">For this reason, the resources used with Customer Key require strong protection.</span></span> <span data-ttu-id="ccddd-157">顧客キーと一緒に使用される Azure リソースはすべて、既定の構成を超える保護メカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-157">All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration.</span></span> <span data-ttu-id="ccddd-158">Azure サブスクリプションは、すぐに取り消し可能な取り消しを防ぐ方法でタグ付けまたは登録できます。</span><span class="sxs-lookup"><span data-stu-id="ccddd-158">Azure subscriptions can be tagged or registered in a way that will prevent immediate and irrevocable cancellation.</span></span> <span data-ttu-id="ccddd-159">これは、必須の保持期間の登録と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="ccddd-159">This is referred to as registering for a mandatory retention period.</span></span> <span data-ttu-id="ccddd-160">必須の保持期間に Azure サブスクリプションを登録するために必要な手順には、Microsoft とのコラボレーションが必要です。</span><span class="sxs-lookup"><span data-stu-id="ccddd-160">The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Microsoft.</span></span> <span data-ttu-id="ccddd-161">このプロセスには、最大 5 営業日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ccddd-161">This process can take up to five business days.</span></span> <span data-ttu-id="ccddd-162">以前は、これは "キャンセルしない" と呼ばれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ccddd-162">Previously, this was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="ccddd-163">Microsoft 365 チームに連絡する前に、顧客キーで使用する Azure サブスクリプションごとに次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccddd-163">Before contacting the Microsoft 365 team, you must perform the following steps for each Azure subscription that you use with Customer Key.</span></span> <span data-ttu-id="ccddd-164">開始する前に [、Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) モジュールがインストールされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ccddd-164">Ensure that you have the [Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) module installed before you start.</span></span>

1. <span data-ttu-id="ccddd-165">Azure PowerShell でサインインします。</span><span class="sxs-lookup"><span data-stu-id="ccddd-165">Sign in with Azure PowerShell.</span></span> <span data-ttu-id="ccddd-166">手順については [、「Azure PowerShell でサインインする」を参照してください](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="ccddd-166">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="ccddd-167">Register-AzProviderFeatureコマンドレットを実行して、必須の保持期間を使用するためにサブスクリプションを登録します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-167">Run the Register-AzProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span> <span data-ttu-id="ccddd-168">サブスクリプションごとにこのアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-168">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. <span data-ttu-id="ccddd-169">プロセスを完了するには、Microsoft にお問い [合](mailto:m365ck@microsoft.com)m365ck@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="ccddd-169">Contact Microsoft to have the process finalized at [m365ck@microsoft.com](mailto:m365ck@microsoft.com).</span></span> <span data-ttu-id="ccddd-170">メールに次の情報を含める:</span><span class="sxs-lookup"><span data-stu-id="ccddd-170">Include the following in your email:</span></span>

   <span data-ttu-id="ccddd-171">**件名**: 顧客キー \<*Your tenant's fully-qualified domain name*\></span><span class="sxs-lookup"><span data-stu-id="ccddd-171">**Subject**: Customer Key for \<*Your tenant's fully-qualified domain name*\></span></span>

   <span data-ttu-id="ccddd-172">**Body**: 必須の保持期間を確定するサブスクリプションの ID です。</span><span class="sxs-lookup"><span data-stu-id="ccddd-172">**Body**: Subscription IDs for which you want to have the mandatory retention period finalized.</span></span>
   <span data-ttu-id="ccddd-173">各サブスクリプションのGet-AzProviderFeature出力。</span><span class="sxs-lookup"><span data-stu-id="ccddd-173">The output of Get-AzProviderFeature for each subscription.</span></span>

   <span data-ttu-id="ccddd-174">このプロセスを完了するサービス レベル 契約 (SLA) は、サブスクリプションを登録して必須の保持期間を使用したと Microsoft に通知 (および検証) が完了した 5 営業日後です。</span><span class="sxs-lookup"><span data-stu-id="ccddd-174">The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period.</span></span>

4. <span data-ttu-id="ccddd-175">登録が完了したという通知を Microsoft から受け取った後、次のように Get-AzProviderFeature コマンドを実行して、登録の状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-175">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzProviderFeature command as follows.</span></span> <span data-ttu-id="ccddd-176">確認された場合、Get-AzProviderFeatureコマンドは Registration State プロパティの **Registered** の値 **を返** します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-176">If verified, the Get-AzProviderFeature command returns a value of **Registered** for the **Registration State** property.</span></span> <span data-ttu-id="ccddd-177">サブスクリプションごとにこのアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-177">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. <span data-ttu-id="ccddd-178">このプロセスを完了するには、次のコマンドRegister-AzResourceProviderします。</span><span class="sxs-lookup"><span data-stu-id="ccddd-178">To complete the process, run the Register-AzResourceProvider command.</span></span> <span data-ttu-id="ccddd-179">サブスクリプションごとにこのアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-179">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="ccddd-180">各サブスクリプションにプレミアム Azure Key Vault を作成する</span><span class="sxs-lookup"><span data-stu-id="ccddd-180">Create a premium Azure Key Vault in each subscription</span></span>

<span data-ttu-id="ccddd-181">キー コンテナーを作成する手順については [、「Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)の使用を開始する」に記載されています。この手順では、Azure PowerShell のインストールと起動、Azure サブスクリプションへの接続、リソース グループの作成、そのリソース グループでのキー コンテナーの作成について説明します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-181">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="ccddd-182">キー コンテナーを作成する場合は、SKU (Standard または Premium) を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccddd-182">When you create a key vault, you must choose a SKU: either Standard or Premium.</span></span> <span data-ttu-id="ccddd-183">Standard SKU を使用すると、Azure Key Vault キーをソフトウェアで保護できます。ハードウェア セキュリティ モジュール (HS) キー保護はありません。また、Premium SKU では、キー コンテナー キーの保護に HSM を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ccddd-183">The Standard SKU allows Azure Key Vault keys to be protected with software - there is no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys.</span></span> <span data-ttu-id="ccddd-184">カスタマー キーは、いずれかの SKU を使用するキー コンテナーを受け入れるが、Premium SKU のみを使用する方法を強く推奨している。</span><span class="sxs-lookup"><span data-stu-id="ccddd-184">Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU.</span></span> <span data-ttu-id="ccddd-185">どちらの種類のキーも操作のコストは同じなので、コストの唯一の違いは、各HSM で保護されたキーの 1 か月あたりのコストです。</span><span class="sxs-lookup"><span data-stu-id="ccddd-185">The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key.</span></span> <span data-ttu-id="ccddd-186">詳細 [については、Key Vault の価格を](https://azure.microsoft.com/pricing/details/key-vault/) 参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccddd-186">See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ccddd-187">実稼働データには Premium SKU キー コンテナーと SKU で保護されたキーを使用し、テストと検証の目的には Standard SKU キー コンテナーとキーのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-187">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span>

<span data-ttu-id="ccddd-188">キー コンテナーに共通のプレフィックスを使用し、キー コンテナーとキーの使用とスコープの省略形を含める。</span><span class="sxs-lookup"><span data-stu-id="ccddd-188">Use a common prefix for key vaults and include an abbreviation of the use and scope of the key vault and keys.</span></span> <span data-ttu-id="ccddd-189">たとえば、コンテナーが北米に位置する Contoso サービスの場合、名前のペアとして Contoso-O365-NA-VaultA1 と Contoso-O365-NA-VaultA2 を指定できます。</span><span class="sxs-lookup"><span data-stu-id="ccddd-189">For example, for the Contoso service where the vaults will be located in North America, a possible pair of names is Contoso-O365-NA-VaultA1 and Contoso-O365-NA-VaultA2.</span></span> <span data-ttu-id="ccddd-190">コンテナー名は Azure 内でグローバルに一意の文字列なので、目的の名前が他の Azure ユーザーによって既に要求されている場合に、目的の名前のバリエーションを試す必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="ccddd-190">Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers.</span></span> <span data-ttu-id="ccddd-191">構成したコンテナー名は変更できないので、ベスト プラクティスは、セットアップの計画を作成し、2 番目のユーザーを使用して計画が正しく実行されていることを確認する方法です。</span><span class="sxs-lookup"><span data-stu-id="ccddd-191">Once configured, vault names cannot be changed, so the best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span>

<span data-ttu-id="ccddd-192">可能であれば、ペアでない地域にコンテナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-192">If possible, create your vaults in non-paired regions.</span></span> <span data-ttu-id="ccddd-193">ペアの Azure リージョンは、サービス 障害ドメイン間で高可用性を提供します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-193">Paired Azure regions provide high availability across service failure domains.</span></span> <span data-ttu-id="ccddd-194">したがって、地域のペアは互いにバックアップ地域と考え合う可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ccddd-194">Therefore, regional pairs can be thought of as each other's backup region.</span></span> <span data-ttu-id="ccddd-195">つまり、1 つの地域に配置された Azure リソースは、ペアリングされた地域を通じて自動的にフォールト トレランスを取得します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-195">This means that an Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region.</span></span> <span data-ttu-id="ccddd-196">このため、地域がペアのデータ暗号化ポリシーで使用される 2 つのコンテナーに対して地域を選択すると、合計で 2 つの可用性の地域だけが使用されます。</span><span class="sxs-lookup"><span data-stu-id="ccddd-196">For this reason, choosing regions for two vaults used in a data encryption policy where the regions are paired means that only a total of two regions of availability are in use.</span></span> <span data-ttu-id="ccddd-197">ほとんどの地域には 2 つの地域しか存在しないので、ペアリングされていない地域をまだ選択できません。</span><span class="sxs-lookup"><span data-stu-id="ccddd-197">Most geographies only have two regions, so it's not yet possible to select non-paired regions.</span></span> <span data-ttu-id="ccddd-198">可能であれば、データ暗号化ポリシーで使用する 2 つのコンテナーに対して、ペアではない 2 つの地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-198">If possible, choose two non-paired regions for the two vaults used with a data encryption policy.</span></span> <span data-ttu-id="ccddd-199">これにより、合計で 4 つの可用性の領域を利用できます。</span><span class="sxs-lookup"><span data-stu-id="ccddd-199">This benefits from a total of four regions of availability.</span></span> <span data-ttu-id="ccddd-200">詳細については、「ビジネス継続性と障害復旧 [(BCDR): 地域](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) ペアの現在の一覧については、Azure のペアリングされた地域」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccddd-200">For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span>

### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="ccddd-201">各キー コンテナーにアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="ccddd-201">Assign permissions to each key vault</span></span>

<span data-ttu-id="ccddd-202">キー コンテナーごとに、実装に応じて、顧客キーに対する 3 つの個別のアクセス許可セットを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccddd-202">For each key vault, you will need to define three separate sets of permissions for Customer Key, depending on your implementation.</span></span> <span data-ttu-id="ccddd-203">たとえば、次のそれぞれに対して 1 つのアクセス許可セットを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccddd-203">For example, you will need to define one set of permissions for each of the following:</span></span>
  
- <span data-ttu-id="ccddd-204">**組織のキー** コンテナーの毎日の管理を実行するキー コンテナー管理者。</span><span class="sxs-lookup"><span data-stu-id="ccddd-204">**Key vault administrators** that will perform day-to-day management of your key vault for your organization.</span></span> <span data-ttu-id="ccddd-205">これらのタスクには、バックアップ、作成、取得、インポート、リスト、および復元が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ccddd-205">These tasks include backup, create, get, import, list, and restore.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="ccddd-206">キー コンテナー管理者に割り当てられた一連のアクセス許可には、キーを削除するアクセス許可は含められていない。</span><span class="sxs-lookup"><span data-stu-id="ccddd-206">The set of permissions assigned to key vault administrators does not include the permission to delete keys.</span></span> <span data-ttu-id="ccddd-207">これは意図的で重要な方法です。</span><span class="sxs-lookup"><span data-stu-id="ccddd-207">This is intentional and an important practice.</span></span> <span data-ttu-id="ccddd-208">暗号化キーを削除すると、データが完全に破棄されるので、通常は削除しません。</span><span class="sxs-lookup"><span data-stu-id="ccddd-208">Deleting encryption keys is not typically done, since doing so permanently destroys data.</span></span> <span data-ttu-id="ccddd-209">ベスト プラクティスとして、この権限をキー コンテナー管理者に既定で付与することはお使いください。</span><span class="sxs-lookup"><span data-stu-id="ccddd-209">As a best practice, do not grant this permission to key vault administrators by default.</span></span> <span data-ttu-id="ccddd-210">代わりに、主要なコンテナーの投稿者のためにこれを予約し、結果の明確な理解が得られると、短期的に管理者に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccddd-210">Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span>
  
  <span data-ttu-id="ccddd-211">組織内のユーザーにこれらのアクセス許可を割り当てるには、Azure PowerShell を使用して Azure サブスクリプションにログインします。</span><span class="sxs-lookup"><span data-stu-id="ccddd-211">To assign these permissions to a user in your organization, log in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="ccddd-212">手順については [、「Azure PowerShell でサインインする」を参照してください](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="ccddd-212">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

   <span data-ttu-id="ccddd-213">必要なアクセスSet-AzKeyVaultAccessPolicy割り当てるには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-213">Run the Set-AzKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   <span data-ttu-id="ccddd-214">例:</span><span class="sxs-lookup"><span data-stu-id="ccddd-214">For example:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- <span data-ttu-id="ccddd-215">Azure **Key Vault 自体** のアクセス許可を変更できる主要なコンテナーの投稿者。</span><span class="sxs-lookup"><span data-stu-id="ccddd-215">**Key vault contributors** that can change permissions on the Azure Key Vault itself.</span></span> <span data-ttu-id="ccddd-216">従業員がチームを離れる、またはチームに参加する場合、またはキー コンテナー管理者がキーを削除または復元するためのアクセス許可を正当に必要とするまれな状況では、これらのアクセス許可を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccddd-216">You'll need to change these permissions as employees leave or join your team, or in the rare situation that the key vault administrators legitimately need permission to delete or restore a key.</span></span> <span data-ttu-id="ccddd-217">この一連の主要なコンテナー投稿者には、キー コンテナーの共同作成者ロールが付与されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccddd-217">This set of key vault contributors needs to be granted the Contributor role on your key vault.</span></span> <span data-ttu-id="ccddd-218">このロールは、Azure リソース マネージャーを使用して割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="ccddd-218">You can assign this role by using Azure Resource Manager.</span></span> <span data-ttu-id="ccddd-219">詳細な手順については、「Role-Based [Access Control](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure) を使用して Azure サブスクリプション リソースへのアクセスを管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccddd-219">For detailed steps, see [Use Role-Based Access Control](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure) to manage access to your Azure subscription resources.</span></span> <span data-ttu-id="ccddd-220">サブスクリプションを作成する管理者は、既定でこのアクセス権を持ち、他の管理者を投稿者の役割に割り当てる機能を持っています。</span><span class="sxs-lookup"><span data-stu-id="ccddd-220">The administrator who creates a subscription has this access by default, and the ability to assign other administrators to the Contributor role.</span></span>

- <span data-ttu-id="ccddd-221">テナント レベルで顧客キーの処理を行う、保存中の **Microsoft 365** データ暗号化サービス。</span><span class="sxs-lookup"><span data-stu-id="ccddd-221">**Microsoft 365 data at rest encryption service** that does the work of Customer Key at the tenant level.</span></span> <span data-ttu-id="ccddd-222">Microsoft 365 へのアクセス許可を付与するには、次の構文を使用して **Set-AzKeyVaultAccessPolicy** コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-222">To give permission to Microsoft 365, run the **Set-AzKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
   ```

  <span data-ttu-id="ccddd-223">ここで、</span><span class="sxs-lookup"><span data-stu-id="ccddd-223">Where:</span></span>

  - <span data-ttu-id="ccddd-224">*コンテナー名* は、作成したキー コンテナーの名前です。</span><span class="sxs-lookup"><span data-stu-id="ccddd-224">*vault name* is the name of the key vault you created.</span></span>

  <span data-ttu-id="ccddd-225">例: Rest Encryption サービスの Microsoft 365 データの場合  *、Microsoft 365 appID* を次の値に置き換える `c066d759-24ae-40e7-a56f-027002b5d3e4`</span><span class="sxs-lookup"><span data-stu-id="ccddd-225">Example: For the Microsoft 365 Data at Rest Encryption service, replace  *Microsoft 365 appID* with `c066d759-24ae-40e7-a56f-027002b5d3e4`</span></span>

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a><span data-ttu-id="ccddd-226">キー コンテナーで回復可能な削除を有効にして確認する</span><span class="sxs-lookup"><span data-stu-id="ccddd-226">Enable and then confirm soft delete on your key vaults</span></span>

<span data-ttu-id="ccddd-227">キーをすばやく回復できると、誤ってまたは悪意を持って削除されたキーが原因でサービスの停止が延長される可能性は低い可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ccddd-227">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys.</span></span> <span data-ttu-id="ccddd-228">顧客キーでキーを使用する前に、この構成 (回復可能な削除と呼ばれる) を有効にします。</span><span class="sxs-lookup"><span data-stu-id="ccddd-228">Enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key.</span></span> <span data-ttu-id="ccddd-229">回復可能な削除を有効にすると、削除から 90 日以内にキーまたはコンテナーを復元できます。バックアップから復元する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ccddd-229">Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="ccddd-230">キー コンテナーで回復可能な削除を有効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-230">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="ccddd-231">Azure サブスクリプションにサインインするには、次のWindows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="ccddd-231">Sign in to your Azure subscription with Windows PowerShell.</span></span> <span data-ttu-id="ccddd-232">手順については [、「Azure PowerShell でサインインする」を参照してください](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="ccddd-232">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="ccddd-233">[Get-AzKeyVault コマンドレットを実行](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault)します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-233">Run the [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet.</span></span> <span data-ttu-id="ccddd-234">この例では、 *コンテナー名* は、回復可能な削除を有効にするキー コンテナーの名前です。</span><span class="sxs-lookup"><span data-stu-id="ccddd-234">In this example, *vault name* is the name of the key vault for which you are enabling soft delete:</span></span>

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. <span data-ttu-id="ccddd-235">**Get-AzKeyVault** コマンドレットを実行して、キー コンテナーの回復可能な削除が構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-235">Confirm soft delete is configured for the key vault by running the **Get-AzKeyVault** cmdlet.</span></span> <span data-ttu-id="ccddd-236">回復可能な削除がキー コンテナーに対して適切に構成されている場合 _、Soft Delete Enabled_ プロパティは True の値を返 **します**。</span><span class="sxs-lookup"><span data-stu-id="ccddd-236">If soft delete is configured properly for the key vault, then the _Soft Delete Enabled_ property returns a value of **True**:</span></span>

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="ccddd-237">キーを作成またはインポートして、各キー コンテナーにキーを追加する</span><span class="sxs-lookup"><span data-stu-id="ccddd-237">Add a key to each key vault either by creating or importing a key</span></span>

<span data-ttu-id="ccddd-238">Azure Key Vault にキーを追加するには 2 つの方法があります。Key Vault で直接キーを作成するか、キーをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="ccddd-238">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key.</span></span> <span data-ttu-id="ccddd-239">キーコンテナーで直接キーを作成する方法は複雑では少なく、キーをインポートすると、キーの生成方法を完全に制御できます。</span><span class="sxs-lookup"><span data-stu-id="ccddd-239">Creating a key directly in Key Vault is the less complicated method, while importing a key provides total control over how the key is generated.</span></span> <span data-ttu-id="ccddd-240">RSA キーを使用します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-240">Use the RSA keys.</span></span> <span data-ttu-id="ccddd-241">Azure Key Vault では、楕円曲線キーでの折り返しと折り返しの解除はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ccddd-241">Azure Key Vault doesn't support wrapping and unwrapping with elliptical curve keys.</span></span>
  
<span data-ttu-id="ccddd-242">キー コンテナーにキーを直接作成するには、次のように [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-242">To create a key directly in your key vault, run the [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="ccddd-243">ここで、</span><span class="sxs-lookup"><span data-stu-id="ccddd-243">Where:</span></span>

- <span data-ttu-id="ccddd-244">*コンテナー名* は、キーを作成するキー コンテナーの名前です。</span><span class="sxs-lookup"><span data-stu-id="ccddd-244">*vault name* is the name of the key vault in which you want to create the key.</span></span>

- <span data-ttu-id="ccddd-245">*キー名* は、新しいキーを指定する名前です。</span><span class="sxs-lookup"><span data-stu-id="ccddd-245">*key name* is the name you want to give the new key.</span></span>

  > [!TIP]
  > <span data-ttu-id="ccddd-246">キー コンテナーの場合は、上記と同様の名前付け規則を使用してキーに名前を付ける。</span><span class="sxs-lookup"><span data-stu-id="ccddd-246">Name keys using a similar naming convention as described above for key vaults.</span></span> <span data-ttu-id="ccddd-247">これにより、キー名のみを表示するツールでは、文字列は自己記述型になります。</span><span class="sxs-lookup"><span data-stu-id="ccddd-247">This way, in tools that show only the key name, the string is self-describing.</span></span>
  
<span data-ttu-id="ccddd-248">キーを必ず _DESTINATION_ パラメーターの値として指定し、**それ** 以外の場合は **Software** を指定します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-248">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the _Destination_ parameter, otherwise, specify **Software**.</span></span>

<span data-ttu-id="ccddd-249">例えば、</span><span class="sxs-lookup"><span data-stu-id="ccddd-249">For example,</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="ccddd-250">キーの回復レベルを確認する</span><span class="sxs-lookup"><span data-stu-id="ccddd-250">Check the recovery level of your keys</span></span>

<span data-ttu-id="ccddd-251">Microsoft 365 では、Azure Key Vault サブスクリプションが [キャンセルしない] に設定され、顧客キーで使用されるキーの削除 (回復可能) が有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccddd-251">Microsoft 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled.</span></span> <span data-ttu-id="ccddd-252">これを確認するには、キーの回復レベルを確認します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-252">You can confirm this by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="ccddd-253">キーの回復レベルを確認するには、Azure PowerShell で次Get-AzKeyVaultKeyコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-253">To check the recovery level of a key, in Azure PowerShell, run the Get-AzKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

<span data-ttu-id="ccddd-254">回復レベルのプロパティが **Recoverable+ProtectedSubscription** の値以外の値を返す場合は、この記事を確認し、サブスクリプションを取り消し不可リストに入れるすべての手順を実行し、各キー コンテナーで "回復可能な削除" を有効にした必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccddd-254">If the _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, you will need to review this article and ensure that you have followed all of the steps to put the subscription on the Do Not Cancel list and that you enabled "soft delete" on each of your key vaults.</span></span> <span data-ttu-id="ccddd-255">次に、電子メールの出力のスクリーンショット `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` を送信して、m365ck@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="ccddd-255">Next, send a screenshot of the output of `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` in email to m365ck@microsoft.com.</span></span>

### <a name="back-up-azure-key-vault"></a><span data-ttu-id="ccddd-256">Azure Key Vault をバックアップする</span><span class="sxs-lookup"><span data-stu-id="ccddd-256">Back up Azure Key Vault</span></span>

<span data-ttu-id="ccddd-257">キーの作成または変更の直後に、バックアップを実行し、バックアップのコピーをオンラインとオフラインの両方で保存します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-257">Immediately following creation or any change to a key, perform a backup and store copies of the backup, both online and offline.</span></span> <span data-ttu-id="ccddd-258">オフライン コピーをネットワークに接続しない。</span><span class="sxs-lookup"><span data-stu-id="ccddd-258">Don't connect offline copies to any network.</span></span> <span data-ttu-id="ccddd-259">代わりに、物理的な安全なストレージまたは商用のストレージ機能に保存します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-259">Instead, store them in a physical safe or commercial storage facility.</span></span> <span data-ttu-id="ccddd-260">障害が発生した場合にアクセスできる場所に、バックアップの少なくとも 1 つのコピーを格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccddd-260">At least one copy of the backup should be stored in a location that will be accessible if a disaster happens.</span></span> <span data-ttu-id="ccddd-261">バックアップ BLOB は、Key Vault キーが完全に破棄された場合や、他の方法で操作できない場合にキー マテリアルを復元する唯一の手段です。</span><span class="sxs-lookup"><span data-stu-id="ccddd-261">The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable.</span></span> <span data-ttu-id="ccddd-262">Azure Key Vault の外部に存在し、Azure Key Vault にインポートされたキーは、顧客キーでキーを使用するために必要なメタデータが外部キーと一緒に存在しないので、バックアップとして修飾されません。</span><span class="sxs-lookup"><span data-stu-id="ccddd-262">Keys that are external to Azure Key Vault and were imported to Azure Key Vault do not qualify as a backup because the metadata necessary for Customer Key to use the key does not exist with the external key.</span></span> <span data-ttu-id="ccddd-263">顧客キーを使用した復元操作には、Azure Key Vault から取得したバックアップのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ccddd-263">Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key.</span></span> <span data-ttu-id="ccddd-264">したがって、キーをアップロードまたは作成したら、Azure Key Vault のバックアップを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccddd-264">Therefore, it is essential that you make a backup of Azure Key Vault once a key is uploaded or created.</span></span>
  
<span data-ttu-id="ccddd-265">Azure Key Vault キーのバックアップを作成するには、 [次のように Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-265">To create a backup of an Azure Key Vault key, run the [Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet as follows:</span></span>

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

<span data-ttu-id="ccddd-266">出力ファイルでサフィックスが使用されている必要があります `.backup` 。</span><span class="sxs-lookup"><span data-stu-id="ccddd-266">Ensure that your output file uses the suffix `.backup`.</span></span>
  
<span data-ttu-id="ccddd-267">このコマンドレットによって生成された出力ファイルは暗号化され、Azure Key Vault の外部では使用できません。</span><span class="sxs-lookup"><span data-stu-id="ccddd-267">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault.</span></span> <span data-ttu-id="ccddd-268">バックアップは、バックアップの取得元の Azure サブスクリプションにのみ復元できます。</span><span class="sxs-lookup"><span data-stu-id="ccddd-268">The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
<span data-ttu-id="ccddd-269">例:</span><span class="sxs-lookup"><span data-stu-id="ccddd-269">For example:</span></span>
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="ccddd-270">Azure Key Vault の構成設定を検証する</span><span class="sxs-lookup"><span data-stu-id="ccddd-270">Validate Azure Key Vault configuration settings</span></span>

<span data-ttu-id="ccddd-271">DEP でキーを使用する前に検証を実行する方法はオプションですが、強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ccddd-271">Performing validation before using keys in a DEP is optional, but highly recommended.</span></span> <span data-ttu-id="ccddd-272">特に、このトピックで説明する手順以外の手順でキーとコンテナーをセットアップする場合は、顧客キーを構成する前に Azure Key Vault リソースの正常性を検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccddd-272">In particular, if you use steps to set up your keys and vaults other than the ones described in this topic, you should validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="ccddd-273">キーで get、wrapKey、および unwrapKey 操作が有効になっているか確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-273">To verify that your keys have get, wrapKey, and unwrapKey operations enabled:</span></span>
  
<span data-ttu-id="ccddd-274">[Get-AzKeyVault コマンドレットを次](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault)のように実行します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-274">Run the [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="ccddd-275">出力で、アクセス ポリシーと、必要に応じて Microsoft 365 アプリ ID (GUID) を探します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-275">In the output, look for the Access Policy and for the Microsoft 365 app ID (GUID) as appropriate.</span></span> <span data-ttu-id="ccddd-276">Get、wrapKey、unwrapKey の 3 つの操作はすべて、[キーへのアクセス許可] の下に表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccddd-276">All three operations, get, wrapKey, and unwrapKey, must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="ccddd-277">アクセス ポリシーの構成が正しくない場合は、次Set-AzKeyVaultAccessPolicyコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-277">If the access policy configuration is incorrect, run the Set-AzKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
```

<span data-ttu-id="ccddd-278">例: Rest Encryption サービスの Microsoft 365 データの場合  *、Microsoft 365 appID* を次の値に置き換える `c066d759-24ae-40e7-a56f-027002b5d3e4`</span><span class="sxs-lookup"><span data-stu-id="ccddd-278">Example: For the Microsoft 365 Data at Rest Encryption service, replace  *Microsoft 365 appID* with `c066d759-24ae-40e7-a56f-027002b5d3e4`</span></span>

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

<span data-ttu-id="ccddd-279">キーに有効期限が設定されていないことを確認するには、次のように [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-279">To verify that an expiration date is not set for your keys, run the [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

<span data-ttu-id="ccddd-280">期限切れのキーを顧客キーで使用することはできません。また、期限切れのキーを使用して試行された操作は失敗し、サービスが停止する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ccddd-280">An expired key cannot be used by Customer Key and operations attempted with an expired key will fail and possibly result in a service outage.</span></span> <span data-ttu-id="ccddd-281">顧客キーで使用するキーには有効期限日を設定することを強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-281">We strongly recommend that keys used with Customer Key do not have an expiration date.</span></span> <span data-ttu-id="ccddd-282">有効期限を設定すると削除できませんが、別の日付に変更できます。</span><span class="sxs-lookup"><span data-stu-id="ccddd-282">An expiration date, once set, cannot be removed, but can be changed to a different date.</span></span> <span data-ttu-id="ccddd-283">有効期限が設定されているキーを使用する必要がある場合は、有効期限の値を 9999 年 12 月 31 日に変更します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-283">If a key must be used that has an expiration date set, change the expiration value to 12/31/9999.</span></span> <span data-ttu-id="ccddd-284">有効期限が 12/31/9999 以外の日付に設定されているキーは、Microsoft 365 検証に合格しません。</span><span class="sxs-lookup"><span data-stu-id="ccddd-284">Keys with an expiration date set to a date other than 12/31/9999 will not pass Microsoft 365 validation.</span></span>
  
<span data-ttu-id="ccddd-285">12/31/9999 以外の値に設定されている有効期限を変更するには [、Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) コマンドレットを次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-285">To change an expiration date that has been set to any value other than 12/31/9999, run the [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="ccddd-286">各 Azure Key Vault キーの URI を取得する</span><span class="sxs-lookup"><span data-stu-id="ccddd-286">Obtain the URI for each Azure Key Vault key</span></span>

<span data-ttu-id="ccddd-287">Azure のすべての手順を完了してキー コンテナーをセットアップし、キーを追加したら、次のコマンドを実行して各キー コンテナーのキーの URI を取得します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-287">Once you've completed all the steps in Azure to set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault.</span></span> <span data-ttu-id="ccddd-288">これらの URI は、後で各 DEP を作成して割り当てる際に使用する必要があります。そのため、この情報は安全な場所に保存してください。</span><span class="sxs-lookup"><span data-stu-id="ccddd-288">You will need to use these URIs when you create and assign each DEP later, so save this information in a safe place.</span></span> <span data-ttu-id="ccddd-289">このコマンドは、キー コンテナーごとに 1 回だけ実行してください。</span><span class="sxs-lookup"><span data-stu-id="ccddd-289">Remember to run this command once for each key vault.</span></span>
  
<span data-ttu-id="ccddd-290">Azure PowerShell の場合:</span><span class="sxs-lookup"><span data-stu-id="ccddd-290">In Azure PowerShell:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="set-up-the-customer-key-encryption-policy-for-your-tenant"></a><span data-ttu-id="ccddd-291">テナントの顧客キーの暗号化ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="ccddd-291">Set up the Customer Key encryption policy for your tenant</span></span>

<span data-ttu-id="ccddd-292">これらのコマンドレットを実行する前に、アクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccddd-292">You need to be assigned permissions before you can run these cmdlets.</span></span> <span data-ttu-id="ccddd-293">この記事ではコマンドレットのすべてのパラメーターの一覧を示しますが、割り当てられたアクセス許可にパラメーターが含まれていない場合は、一部のパラメーターにアクセスできない場合があります。</span><span class="sxs-lookup"><span data-stu-id="ccddd-293">Although this article lists all parameters for the cmdlets, you may not have access to some parameters if they're not included in the permissions assigned to you.</span></span> <span data-ttu-id="ccddd-294">コマンドレットを組織内で実行するために必要になるアクセス許可とパラメーターを調べるには、「 [Find the permissions required to run any Exchange cmdlet](https://docs.microsoft.com/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccddd-294">To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://docs.microsoft.com/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions).</span></span>

### <a name="create-policy"></a><span data-ttu-id="ccddd-295">ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="ccddd-295">Create policy</span></span>

```powershell
   New-M365DataAtRestEncryptionPolicy [-Name] <String> -AzureKeyIDs <MultiValuedProperty> [-Description <String>] [-Enabled <Boolean>]
```

<span data-ttu-id="ccddd-296">説明: コンプライアンス管理者が 2 つの AROOT ルート キーを使用して新しいデータ暗号化ポリシー (DEP) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="ccddd-296">Description: Enable compliance admin to create a new data encryption policy (DEP) using two AKV root keys.</span></span> <span data-ttu-id="ccddd-297">作成されたポリシーは、このコマンドレットを使用Set-M365DataAtRestEncryptionPolicyできます。</span><span class="sxs-lookup"><span data-stu-id="ccddd-297">Once created, a policy can then be assigned using Set-M365DataAtRestEncryptionPolicy cmdlet.</span></span> <span data-ttu-id="ccddd-298">キーを最初に割り当て、またはキーを回転した後に、新しいキーが有効にな最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ccddd-298">Upon first assignment of keys or after you rotate keys, it can take up to 24 hours for the new keys to take effect.</span></span> <span data-ttu-id="ccddd-299">新しい DEP が有効にするのに 24 時間以上かかる場合は、Microsoft にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="ccddd-299">If the new DEP takes more than 24 hours to take effect, contact Microsoft.</span></span>

<span data-ttu-id="ccddd-300">例:</span><span class="sxs-lookup"><span data-stu-id="ccddd-300">Example:</span></span>

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Default_Policy" -AzureKeyIDs "https://contosoWestUSvault01.vault.azure.net/keys/Key_01","https://contosoEastUSvault01.vault.azure.net/keys/Key_02" -Description "Tenant default policy"
```

<span data-ttu-id="ccddd-301">パラメータ :</span><span class="sxs-lookup"><span data-stu-id="ccddd-301">Parameters:</span></span>

| <span data-ttu-id="ccddd-302">Name</span><span class="sxs-lookup"><span data-stu-id="ccddd-302">Name</span></span> | <span data-ttu-id="ccddd-303">説明</span><span class="sxs-lookup"><span data-stu-id="ccddd-303">Description</span></span> | <span data-ttu-id="ccddd-304">省略可能 (Y/N)</span><span class="sxs-lookup"><span data-stu-id="ccddd-304">Optional (Y/N)</span></span> |
|--|--|--|
|<span data-ttu-id="ccddd-305">Name</span><span class="sxs-lookup"><span data-stu-id="ccddd-305">Name</span></span>|<span data-ttu-id="ccddd-306">データ暗号化ポリシーの表示名</span><span class="sxs-lookup"><span data-stu-id="ccddd-306">Friendly name of the data encryption policy</span></span>|<span data-ttu-id="ccddd-307">×</span><span class="sxs-lookup"><span data-stu-id="ccddd-307">N</span></span>|
|<span data-ttu-id="ccddd-308">AzureKeyIDs</span><span class="sxs-lookup"><span data-stu-id="ccddd-308">AzureKeyIDs</span></span>|<span data-ttu-id="ccddd-309">データ暗号化ポリシーに関連付ける Azure Key Vault キーの 2 つの URI 値をコンマで区切って指定します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-309">Specifies two URI values of the Azure Key Vault keys, separated by a comma, to associate with the data encryption policy</span></span>|<span data-ttu-id="ccddd-310">×</span><span class="sxs-lookup"><span data-stu-id="ccddd-310">N</span></span>|
|<span data-ttu-id="ccddd-311">説明</span><span class="sxs-lookup"><span data-stu-id="ccddd-311">Description</span></span>|<span data-ttu-id="ccddd-312">データ暗号化ポリシーの説明</span><span class="sxs-lookup"><span data-stu-id="ccddd-312">Description of the data encryption policy</span></span>|<span data-ttu-id="ccddd-313">×</span><span class="sxs-lookup"><span data-stu-id="ccddd-313">N</span></span>|

### <a name="assign-policy"></a><span data-ttu-id="ccddd-314">ポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="ccddd-314">Assign policy</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -Policy “<Default_PolicyName or Default_PolicyID>”
```

<span data-ttu-id="ccddd-315">説明 : このコマンドレットは、既定のデータ暗号化ポリシーの構成に使用されます。</span><span class="sxs-lookup"><span data-stu-id="ccddd-315">Description: This cmdlet is used for configuring default Data Encryption Policy.</span></span> <span data-ttu-id="ccddd-316">このポリシーは、すべてのサポート ワークロードでデータを暗号化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ccddd-316">This policy will be used to then encrypt data across all support workloads.</span></span> 

<span data-ttu-id="ccddd-317">例:</span><span class="sxs-lookup"><span data-stu-id="ccddd-317">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -Policy “Tenant default policy”
```

<span data-ttu-id="ccddd-318">パラメータ :</span><span class="sxs-lookup"><span data-stu-id="ccddd-318">Parameters:</span></span>
| <span data-ttu-id="ccddd-319">Name</span><span class="sxs-lookup"><span data-stu-id="ccddd-319">Name</span></span> | <span data-ttu-id="ccddd-320">説明</span><span class="sxs-lookup"><span data-stu-id="ccddd-320">Description</span></span> | <span data-ttu-id="ccddd-321">省略可能 (Y/N)</span><span class="sxs-lookup"><span data-stu-id="ccddd-321">Optional (Y/N)</span></span> |
|--|--|--|
<span data-ttu-id="ccddd-322">-Policy</span><span class="sxs-lookup"><span data-stu-id="ccddd-322">-Policy</span></span>|<span data-ttu-id="ccddd-323">割り当てる必要があるデータ暗号化ポリシーを指定します。ポリシー名またはポリシー ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-323">Specifies the data encryption policy that needs to be assigned; specify either the Policy Name or the Policy ID.</span></span>|<span data-ttu-id="ccddd-324">×</span><span class="sxs-lookup"><span data-stu-id="ccddd-324">N</span></span>|

### <a name="modify-or-refresh-policy"></a><span data-ttu-id="ccddd-325">ポリシーの変更または更新</span><span class="sxs-lookup"><span data-stu-id="ccddd-325">Modify or Refresh policy</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy [-Identity] < M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter> -Refresh [-Enabled <Boolean>] [-Name <String>] [-Description <String>]
```

<span data-ttu-id="ccddd-326">説明 : このコマンドレットを使用して、既存のポリシーを変更または更新できます。</span><span class="sxs-lookup"><span data-stu-id="ccddd-326">Description: The cmdlet can be used either to modify or refresh an existing policy.</span></span> <span data-ttu-id="ccddd-327">また、ポリシーを有効または無効にする場合にも使用できます。</span><span class="sxs-lookup"><span data-stu-id="ccddd-327">It can also be used to enable or disable a policy.</span></span> <span data-ttu-id="ccddd-328">キーを最初に割り当て、またはキーを回転した後に、新しいキーが有効にな最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ccddd-328">Upon first assignment of keys or after you rotate keys, it can take up to 24 hours for the new keys to take effect.</span></span> <span data-ttu-id="ccddd-329">新しい DEP が有効にするのに 24 時間以上かかる場合は、Microsoft にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="ccddd-329">If the new DEP takes more than 24 hours to take effect, contact Microsoft.</span></span>

<span data-ttu-id="ccddd-330">例:</span><span class="sxs-lookup"><span data-stu-id="ccddd-330">Examples:</span></span>

<span data-ttu-id="ccddd-331">データ暗号化ポリシーを無効にします。</span><span class="sxs-lookup"><span data-stu-id="ccddd-331">Disable a data encryption policy.</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "NAM Policy" -Enabled $false
```

<span data-ttu-id="ccddd-332">データ暗号化ポリシーを更新します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-332">Refresh a data encryption policy.</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity “EUR Policy” -Refresh
```

<span data-ttu-id="ccddd-333">パラメータ :</span><span class="sxs-lookup"><span data-stu-id="ccddd-333">Parameters:</span></span>
| <span data-ttu-id="ccddd-334">Name</span><span class="sxs-lookup"><span data-stu-id="ccddd-334">Name</span></span> | <span data-ttu-id="ccddd-335">説明</span><span class="sxs-lookup"><span data-stu-id="ccddd-335">Description</span></span> | <span data-ttu-id="ccddd-336">省略可能 (Y/N)</span><span class="sxs-lookup"><span data-stu-id="ccddd-336">Optional (Y/N)</span></span> |
|--|--|--|
|<span data-ttu-id="ccddd-337">-Identity</span><span class="sxs-lookup"><span data-stu-id="ccddd-337">-Identity</span></span>|<span data-ttu-id="ccddd-338">変更するデータ暗号化ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-338">Specifies the data encryption policy that you want to modify.</span></span>|<span data-ttu-id="ccddd-339">×</span><span class="sxs-lookup"><span data-stu-id="ccddd-339">N</span></span>|
|<span data-ttu-id="ccddd-340">-Refresh</span><span class="sxs-lookup"><span data-stu-id="ccddd-340">-Refresh</span></span>|<span data-ttu-id="ccddd-341">Azure Key Vault で関連付けられたキーを回転した後、Refresh スイッチを使用してデータ暗号化ポリシーを更新します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-341">Use the Refresh switch to update the data encryption policy after you rotate any of the associated keys in the Azure Key Vault.</span></span> <span data-ttu-id="ccddd-342">このスイッチで値を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ccddd-342">You don't need to specify a value with this switch.</span></span>|<span data-ttu-id="ccddd-343">Y</span><span class="sxs-lookup"><span data-stu-id="ccddd-343">Y</span></span>|
|<span data-ttu-id="ccddd-344">-Enabled</span><span class="sxs-lookup"><span data-stu-id="ccddd-344">-Enabled</span></span>|<span data-ttu-id="ccddd-345">Enabled パラメーターは、データ暗号化ポリシーを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="ccddd-345">The Enabled parameter enables or disable the data encryption policy.</span></span> <span data-ttu-id="ccddd-346">ポリシーを無効にする前に、テナントからポリシーの割り当てを解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccddd-346">Before you disable a policy, you must unassign it from your tenant.</span></span> <span data-ttu-id="ccddd-347">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ccddd-347">Valid values are:</span></span></br > <span data-ttu-id="ccddd-348">$true: ポリシーが有効になっている</span><span class="sxs-lookup"><span data-stu-id="ccddd-348">$true: The policy is enabled</span></span></br > <span data-ttu-id="ccddd-349">$true: ポリシーを有効にします。これが既定値です。</span><span class="sxs-lookup"><span data-stu-id="ccddd-349">$false: The policy is disabled.</span></span>|<span data-ttu-id="ccddd-350">Y</span><span class="sxs-lookup"><span data-stu-id="ccddd-350">Y</span></span>|
|<span data-ttu-id="ccddd-351">-Name</span><span class="sxs-lookup"><span data-stu-id="ccddd-351">-Name</span></span>|<span data-ttu-id="ccddd-352">Name パラメーターは、データの暗号化ポリシーの一意の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-352">The Name parameter specifies the unique name for the data encryption policy.</span></span>|<span data-ttu-id="ccddd-353">Y</span><span class="sxs-lookup"><span data-stu-id="ccddd-353">Y</span></span>
|<span data-ttu-id="ccddd-354">-Description</span><span class="sxs-lookup"><span data-stu-id="ccddd-354">-Description</span></span>|<span data-ttu-id="ccddd-355">Description パラメーターは、データの暗号化ポリシーの省略可能な説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-355">The Description parameter specifies an optional description for the data encryption policy.</span></span>|<span data-ttu-id="ccddd-356">Y</span><span class="sxs-lookup"><span data-stu-id="ccddd-356">Y</span></span>|

### <a name="get-policy-details"></a><span data-ttu-id="ccddd-357">ポリシーの詳細を取得する</span><span class="sxs-lookup"><span data-stu-id="ccddd-357">Get policy details</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy [-Identity] < M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter>
```

<span data-ttu-id="ccddd-358">説明 : このコマンドレットは、テナント用に作成された M365DataAtRest 暗号化ポリシーの一覧、または特定のポリシーに関する詳細を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-358">Description: This cmdlet lists all of M365DataAtRest encryption policies that are created for the tenant or details about a specific policy.</span></span>

<span data-ttu-id="ccddd-359">例:</span><span class="sxs-lookup"><span data-stu-id="ccddd-359">Examples:</span></span>

<span data-ttu-id="ccddd-360">この例では、組織内の M365DatAtRest Encryption ポリシーの要約リストを返します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-360">This example returns a summary list of M365DatAtRest Encryption policies in the organization.</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy
```

<span data-ttu-id="ccddd-361">この例では、"NAM Policy" という名前のデータ暗号化ポリシーの詳細情報を返します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-361">This example returns detailed information for the data encryption policy named "NAM Policy".</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy -Identity "NAM Policy"
```

<span data-ttu-id="ccddd-362">パラメータ :</span><span class="sxs-lookup"><span data-stu-id="ccddd-362">Parameters:</span></span>

| <span data-ttu-id="ccddd-363">Name</span><span class="sxs-lookup"><span data-stu-id="ccddd-363">Name</span></span> | <span data-ttu-id="ccddd-364">説明</span><span class="sxs-lookup"><span data-stu-id="ccddd-364">Description</span></span> | <span data-ttu-id="ccddd-365">省略可能 (Y/N)</span><span class="sxs-lookup"><span data-stu-id="ccddd-365">Optional (Y/N)</span></span> |
|--|--|--|
|<span data-ttu-id="ccddd-366">-Identity</span><span class="sxs-lookup"><span data-stu-id="ccddd-366">-Identity</span></span>|<span data-ttu-id="ccddd-367">詳細を一覧表示するデータ暗号化ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-367">Specifies the data encryption policy that you want to list the details for.</span></span>|<span data-ttu-id="ccddd-368">Y</span><span class="sxs-lookup"><span data-stu-id="ccddd-368">Y</span></span>|

### <a name="get-policy-assignment-info"></a><span data-ttu-id="ccddd-369">ポリシー割り当て情報を取得する</span><span class="sxs-lookup"><span data-stu-id="ccddd-369">Get policy assignment info</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicyAssignment
```

<span data-ttu-id="ccddd-370">説明 : このコマンドレットは、テナントに現在割り当てられているポリシーを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-370">Description: This cmdlet lists the policy that’s currently assigned to the tenant.</span></span>

## <a name="offboarding-from-customer-key"></a><span data-ttu-id="ccddd-371">顧客キーからのオフボード</span><span class="sxs-lookup"><span data-stu-id="ccddd-371">Offboarding from Customer Key</span></span>

<span data-ttu-id="ccddd-372">Microsoft で管理されているキーに戻す必要がある場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ccddd-372">If you need to revert back to Microsoft-managed keys, you can.</span></span> <span data-ttu-id="ccddd-373">オフボードすると、個々のワークロードでサポートされている既定の暗号化を使用してデータが再暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="ccddd-373">When you offboard, your data is re-encrypted using default encryption supported by each individual workload.</span></span> <span data-ttu-id="ccddd-374">たとえば、Exchange Online は、Microsoft が管理するキーを使用した既定の暗号化をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ccddd-374">For example, Exchange Online supports default encryption using Microsoft-managed keys.</span></span>

<span data-ttu-id="ccddd-375">テナント レベルで顧客キーからテナントをオフボードすることを決定した場合は、m365ck@microsoft.com でテナントのサービスを "無効にする" 要求を電子メールで Microsoft [に連絡します](mailto:m365ck@microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="ccddd-375">If you decided to offboard your tenant from Customer Key at the tenant level, reach out to Microsoft with a request through email to “disable” the service for the tenant at [m365ck@microsoft.com](mailto:m365ck@microsoft.com).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ccddd-376">オフボードは、データ消去と同じではありません。</span><span class="sxs-lookup"><span data-stu-id="ccddd-376">Offboarding is not the same as a data purge.</span></span> <span data-ttu-id="ccddd-377">データの削除は、Microsoft 365 から組織のデータを完全に暗号化して削除しますが、オフボードは削除を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccddd-377">A data purge permanently crypto-deletes your organization's data from Microsoft 365, offboarding does not.</span></span> <span data-ttu-id="ccddd-378">テナント レベルのポリシーのデータ消去は実行できません。</span><span class="sxs-lookup"><span data-stu-id="ccddd-378">You can't perform a data purge for a tenant-level policy.</span></span> <span data-ttu-id="ccddd-379">データ削除パスの詳細については、「キーを取り消す」を [参照し、データ消去パスプロセスを開始します](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)。</span><span class="sxs-lookup"><span data-stu-id="ccddd-379">For information about data purge path, see [Revoke your keys and start the data purge path process](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process).</span></span>

## <a name="about-the-availability-key"></a><span data-ttu-id="ccddd-380">可用性キーについて</span><span class="sxs-lookup"><span data-stu-id="ccddd-380">About the availability key</span></span>

<span data-ttu-id="ccddd-381">可用性キーの詳細については、「可用性キー [の詳細」を参照してください](customer-key-availability-key-understand.md)。</span><span class="sxs-lookup"><span data-stu-id="ccddd-381">For information about the availability key, see [Learn about the availability key](customer-key-availability-key-understand.md).</span></span>

## <a name="key-rotation"></a><span data-ttu-id="ccddd-382">キーの回転</span><span class="sxs-lookup"><span data-stu-id="ccddd-382">Key rotation</span></span>

<span data-ttu-id="ccddd-383">顧客キーで使用されるキーの回転またはローリングについては、「顧客キーまたは利用可能なキーをロールまたは回転 [する」を参照してください](customer-key-availability-key-roll.md)。</span><span class="sxs-lookup"><span data-stu-id="ccddd-383">For information about rotating or rolling keys used with Customer Key, see [Roll or rotate a Customer Key or an availability key](customer-key-availability-key-roll.md).</span></span> <span data-ttu-id="ccddd-384">DEP を更新してキーの新しいバージョンを使用する場合は、この記事で前述したように Set-M365DataAtRestEncryptionPolicy コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="ccddd-384">When you update the DEP to use the new version of the keys, you'll run the Set-M365DataAtRestEncryptionPolicy cmdlet as described earlier in this article.</span></span>

## <a name="related-articles"></a><span data-ttu-id="ccddd-385">関連記事:</span><span class="sxs-lookup"><span data-stu-id="ccddd-385">Related articles:</span></span>

- [<span data-ttu-id="ccddd-386">カスタマー キーによるサービスの暗号化</span><span class="sxs-lookup"><span data-stu-id="ccddd-386">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="ccddd-387">カスタマー キーまたは可用性キーをローリングまたはローテーションする</span><span class="sxs-lookup"><span data-stu-id="ccddd-387">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="ccddd-388">可用性キーの詳細</span><span class="sxs-lookup"><span data-stu-id="ccddd-388">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="ccddd-389">サービスの暗号化</span><span class="sxs-lookup"><span data-stu-id="ccddd-389">Service Encryption</span></span>](office-365-service-encryption.md)
