---
title: Microsoft Viva ラーニング (プレビュー) の学習コンテンツ ソースを構成Microsoft 365 管理センター
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 05/12/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Microsoft Viva ラーニング (Preview) の学習コンテンツ ソースを構成する方法については、Microsoft 365 管理センター。
ms.openlocfilehash: ac9ec6196f758d3ed02d3a102fef80b8a7adeeaa
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288925"
---
# <a name="configure-learning-content-sources-for-microsoft-viva-learning-preview-in-the-microsoft-365-admin-center"></a><span data-ttu-id="5ec4e-103">Microsoft Viva ラーニング (プレビュー) の学習コンテンツ ソースを構成Microsoft 365 管理センター</span><span class="sxs-lookup"><span data-stu-id="5ec4e-103">Configure learning content sources for Microsoft Viva Learning (Preview) in the Microsoft 365 admin center</span></span>

> [!NOTE]
> <span data-ttu-id="5ec4e-104">この記事の情報は、商用リリース前に大幅に変更される可能性があるプレビュー製品に関連しています。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> 

<span data-ttu-id="5ec4e-105">Microsoft 365 管理センター の管理者は、組織内の選択した個人にナレッジ管理者の役割を割り当てるかによって、ビバ ラーニング (プレビュー) に関連する設定を管理し、学習コンテンツ ソースを構成できます。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-105">The administrators for the Microsoft 365 admin center—either by themselves or by assigning the knowledge admin role to selected individuals in your organization—can manage settings related to Viva Learning (Preview) and can configure the learning content sources.</span></span>

<span data-ttu-id="5ec4e-106">管理者は、他のラーニング コンテンツ ソース (SharePoint またはサポートされているサード パーティコンテンツ プロバイダー ソースなど) を選択して、ビバ ラーニング (Preview) のユーザーが利用できます。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-106">The administrator selects which other learning content sources (for example, SharePoint or supported third-party content provider sources) will be available to users of Viva Learning (Preview).</span></span> <span data-ttu-id="5ec4e-107">次に、管理者はそれらのソースを構成して、コンテンツが検索と検出に使用可能であり、ビバ グループ (プレビュー) を使用する従業員が参照ラーニングします。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-107">The admin then configures those sources to make sure the content is available for search and discovery and can be browsed by the employees who use Viva Learning (Preview).</span></span>

> [!NOTE]
>  <span data-ttu-id="5ec4e-108">ユーザーは、ブラウザーまたは埋め込みビューアーで学習ラーニング Pro Microsoft および LinkedIn 以外のユーザーにサインインします。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-108">Users sign in to non-Microsoft and LinkedIn Learning Pro learnings in a browser or embedded viewer.</span></span> <span data-ttu-id="5ec4e-109">この構成済みの学習は、組織と第三者の間の個別のライセンス、プライバシー、およびサービス条件の対象であり、ビバ ラーニング (プレビュー) の用語には適用されません。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-109">This configured learning is subject to the separate license, privacy and service terms between your organization and the third party, and not the Viva Learning (Preview) terms.</span></span> <span data-ttu-id="5ec4e-110">この種類の学習を選択する前に、組織とユーザーに契約があることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-110">Before selecting this type of learning, verify you have an agreement in place for your organization and users.</span></span>

## <a name="assign-the-knowledge-admin-role-optional"></a><span data-ttu-id="5ec4e-111">ナレッジ管理者の役割を割り当てる (オプション)</span><span class="sxs-lookup"><span data-stu-id="5ec4e-111">Assign the knowledge admin role (Optional)</span></span>

<span data-ttu-id="5ec4e-112">これらのタスクを実行するにはMicrosoft 365管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-112">You must be a Microsoft 365 global administrator to perform these tasks.</span></span>

> [!TIP]
> <span data-ttu-id="5ec4e-113">知識管理者は、適度に技術的で、SharePoint 管理者の資格情報を持っている必要があります。できれば、組織の教育、学習、トレーニング、または従業員エクスペリエンスの一部に精通しているユーザーが必要です。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-113">The knowledge admin should be moderately technical and have existing SharePoint admin credentials, preferably someone who is well-versed in the education, learning, training, or employee experience part of the organization.</span></span>

### <a name="add-a-knowledge-admin"></a><span data-ttu-id="5ec4e-114">ナレッジ管理者の追加</span><span class="sxs-lookup"><span data-stu-id="5ec4e-114">Add a knowledge admin</span></span>

<span data-ttu-id="5ec4e-115">Viva ラーニング (プレビュー) のナレッジ管理者を追加するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-115">To add a knowledge admin for Viva Learning (Preview), follow these steps:</span></span>

1. <span data-ttu-id="5ec4e-116">左側のナビゲーションで、[ロール] Microsoft 365 管理センター移動 **します**。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-116">In the left navigation of the Microsoft 365 admin center, go to **Roles**.</span></span>

2. <span data-ttu-id="5ec4e-117">[ロール **] ページ** の **[Azure** AD] タブで、[ナレッジ管理者] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-117">On the **Roles** page, on the **Azure AD** tab, select **Knowledge Administrator**.</span></span>
 
3. <span data-ttu-id="5ec4e-118">[ナレッジ管理者 **] パネルで** 、[割り当てられた管理者] **を** 選択し、[追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-118">On the **Knowledge Administrator** panel, select **Assigned admins**, and then select **Add**.</span></span>

     ![[ナレッジ管理者] パネルがMicrosoft 365 管理センターユーザーを追加する役割] ページが表示されます。](../media/learning/learning-add-knowledge-admin-1.png)

3. <span data-ttu-id="5ec4e-120">[管理者 **の追加] パネル** で、役割に選択したユーザーを選択し、[追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-120">On the **Add admins** panel, select the person you choose for the role, and then select **Add**.</span></span>

     ![[管理者の追加] Microsoft 365 管理センターユーザーを追加する役割] ページが表示されます。](../media/learning/learning-add-knowledge-admin-2.png)

### <a name="remove-a-knowledge-admin"></a><span data-ttu-id="5ec4e-122">ナレッジ管理者を削除する</span><span class="sxs-lookup"><span data-stu-id="5ec4e-122">Remove a knowledge admin</span></span>

<span data-ttu-id="5ec4e-123">Viva ラーニング (プレビュー) のナレッジ管理者を削除するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-123">To remove a knowledge admin for Viva Learning (Preview), follow these steps:</span></span>

1. <span data-ttu-id="5ec4e-124">左側のナビゲーションで、[ロール] Microsoft 365 管理センター移動 **します**。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-124">In the left navigation of the Microsoft 365 admin center, go to **Roles**.</span></span>

2. <span data-ttu-id="5ec4e-125">[ロール **] ページ** の **[Azure** AD] タブで、[ナレッジ管理者] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-125">On the **Roles** page, on the **Azure AD** tab, and then select **Knowledge Administrator**.</span></span>
 
3. <span data-ttu-id="5ec4e-126">[ナレッジ **管理者] パネル** の[割り当てられた管理者] タブで、[削除] を選択し、役割から削除するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-126">On the **Knowledge Administrator** panel, on the **Assigned Admins** tab, select **Remove**, and then select the person you want to remove from the role.</span></span> <span data-ttu-id="5ec4e-127">確認するには、[削除] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-127">To confirm, select **Remove**.</span></span>

     ![[割り当てられた管理者] Microsoft 365 管理センターユーザーを削除する役割] ページが表示されます。](../media/learning/learning-remove-knowledge-admin-1.png)

## <a name="configure-settings-for-the-learning-content-sources"></a><span data-ttu-id="5ec4e-129">学習コンテンツ ソースの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="5ec4e-129">Configure settings for the learning content sources</span></span>

<span data-ttu-id="5ec4e-130">これらのタスクを実行するにはMicrosoft 365管理者またはナレッジ管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-130">You must be a Microsoft 365 global administrator or knowledge admin to perform these tasks.</span></span>

<span data-ttu-id="5ec4e-131">Viva ラーニングで学習コンテンツ ソースの設定を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-131">To configure settings for learning content sources in Viva Learning, follow these steps:</span></span>

1. <span data-ttu-id="5ec4e-132">[組織の設定] の左側Microsoft 365 管理センター[組織の設定]**設定**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-132">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>

2. <span data-ttu-id="5ec4e-133">[組織の **設定] ページ** の [サービス]**タブで、[** ビバ の設定] ラーニング **(プレビュー) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-133">On the **Org settings** page, on the **Services** tab, select **Viva Learning (Preview)**.</span></span>

     ![設定アプリが表示Microsoft 365 管理センターページラーニング表示されます。](../media/learning/learning-sharepoint-configure1.png)

3. <span data-ttu-id="5ec4e-135">[ビバ **ラーニング (プレビュー)** パネルで、組織用に構成する学習コンテンツ ソースを選択し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-135">On the **Viva Learning (Preview)** panel, select the learning content sources you want to configure for the organization, and then select **Save**.</span></span>

     ![ラーニングオプションを表示するMicrosoft 365 管理センターパネルをクリックします。](../media/learning/learning-sharepoint-configure2.png)

<span data-ttu-id="5ec4e-137">存在するすべての学習ソースの中で、既定で有効になっているものがあります。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-137">Among all the learning sources that exist, some will be enabled by default.</span></span> <span data-ttu-id="5ec4e-138">これらの学習ソースには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-138">These learning sources include:</span></span>

- <span data-ttu-id="5ec4e-139">LinkedIn ラーニング (無料コンテンツ)</span><span class="sxs-lookup"><span data-stu-id="5ec4e-139">LinkedIn Learning (free content)</span></span>
- <span data-ttu-id="5ec4e-140">Microsoft Learn</span><span class="sxs-lookup"><span data-stu-id="5ec4e-140">Microsoft Learn</span></span>
- <span data-ttu-id="5ec4e-141">Microsoft 365トレーニング</span><span class="sxs-lookup"><span data-stu-id="5ec4e-141">Microsoft 365 Training</span></span>

> [!NOTE]
> <span data-ttu-id="5ec4e-142">LinkedIn の無料コンテンツは、LinkedIn プライバシー ポリシーとユーザー契約に基いてユーザーに提供されます。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-142">LinkedIn free content is provided to users under the LinkedIn privacy policies and user agreement.</span></span> <span data-ttu-id="5ec4e-143">LinkedIn は、ユーザーの IP アドレス、LinkedIn によって以前に設定された Cookie を受け取り、無料コンテンツの使用を追跡するために新しい Cookie を設定します。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-143">LinkedIn will receive the user’s IP address, any cookies previously set by LinkedIn, and will set a new cookie to track use of free content.</span></span> <span data-ttu-id="5ec4e-144">ユーザーは、無料のコンテンツを受信するために LinkedIn でサインインする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-144">Users are not required to sign in with LinkedIn to receive free content.</span></span><br><br>
<span data-ttu-id="5ec4e-145">LinkedIn プレミアム コンテンツの場合、組織はチームがコンテンツにアクセスするサブスクリプションを必要とします。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-145">For LinkedIn premium content, your organization needs a subscription for your team to access that content.</span></span> <span data-ttu-id="5ec4e-146">ユーザーは LinkedIn にサインインして、その学習にアクセスする必要があります。これは、組織の用語と LinkedIn のユーザー用語の条件に従って提供されます。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-146">Users will need to sign into LinkedIn to access that learning, which is provided under the terms of your organization’s and user terms with LinkedIn.</span></span><br><br> <span data-ttu-id="5ec4e-147">Microsoft 以外のコンテンツ (無料の LinkedIn コンテンツを除く) の場合は、ユーザーが仕事用アカウントを使用してそのコンテンツにアクセスするためのサブスクリプションを組織に用意してから、ビバ ラーニング (Preview) に接続してください。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-147">For non-Microsoft content (except free LinkedIn content), ensure your organization has a subscription for your users to access that content using a work account before connecting it to Viva Learning (Preview).</span></span> <span data-ttu-id="5ec4e-148">Microsoft 以外のラーニング プロバイダーに対するユーザーの個人サブスクリプションは、Viva ラーニング (Preview) と統合されません。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-148">Users’ personal subscriptions to non-Microsoft learning providers will not be integrated with Viva Learning (Preview).</span></span> <span data-ttu-id="5ec4e-149">ユーザーは、ブラウザーまたは埋め込みビューアーで学習ラーニング Pro Microsoft および LinkedIn 以外のユーザーにサインインします。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-149">Users sign in to non-Microsoft and LinkedIn Learning Pro learnings in a browser or embedded viewer.</span></span> <span data-ttu-id="5ec4e-150">ユーザーが組織のサブスクリプションを持つコンテンツに移動すると、個々のサブスクリプションにサインアップできるプロバイダー ページが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-150">If users navigate to content where they do not have an organizational subscription, they may see a provider page where they could sign up for an individual subscription.</span></span> <span data-ttu-id="5ec4e-151">Microsoft 以外のすべての学習は、Microsoft 以外のプロバイダーの条項に基いて提供され、ビバ サービスの一部ラーニング。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-151">All non-Microsoft learning is provided under the non-Microsoft provider’s terms and not as part of Viva Learning.</span></span> 

<span data-ttu-id="5ec4e-152">学習コンテンツ ソースを有効または無効にするには、ソースの横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-152">To enable or disable a learning content source, select the check box next to the source.</span></span> <span data-ttu-id="5ec4e-153">ソースが有効になっている場合は、チェック マークが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-153">If a source is enabled, a check mark will be visible.</span></span>

## <a name="third-party-content-providers"></a><span data-ttu-id="5ec4e-154">サード パーティのコンテンツ プロバイダー</span><span class="sxs-lookup"><span data-stu-id="5ec4e-154">Third-party content providers</span></span> 

<span data-ttu-id="5ec4e-155">利用可能な接続学習プロバイダーのセットは、いつでも変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-155">The set of available connected learning providers might change at any time.</span></span> <span data-ttu-id="5ec4e-156">プログラムの成長に合って、より多くのプロバイダーが参加します。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-156">More providers will join as the program grows.</span></span> <span data-ttu-id="5ec4e-157">利用可能なプロバイダーは、Viva ラーニング (Preview) との接続を中止する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-157">Available providers might also choose to discontinue their connection with Viva Learning (Preview).</span></span>

### <a name="skillsoft-as-a-content-source"></a><span data-ttu-id="5ec4e-158">コンテンツ ソースとしての Skillsoft</span><span class="sxs-lookup"><span data-stu-id="5ec4e-158">Skillsoft as a content source</span></span>  

<span data-ttu-id="5ec4e-159">Viva ラーニング (プレビュー) の場合、Skillsoft を有効にし、Skillsoft コンテンツの表示を選択したユーザーは、組織の Percipio サイト名の入力を求める Percipio ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-159">For Viva Learning (Preview), users who have Skillsoft enabled and choose to view Skillsoft content will land on a Percipio page that asks them to input your organization's Percipio site name.</span></span> <span data-ttu-id="5ec4e-160">ユーザーが組織のサイト名を入力すると、組織の Percipio サイトにサインインするページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-160">After users input your organization's site name, they will be directed to page to sign in to your organization's Percipio site.</span></span> <span data-ttu-id="5ec4e-161">ユーザーは、既存の資格情報を使用してサインインし、最初に選択したコンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-161">Users will sign in by using their existing credentials and see the content they originally selected.</span></span> <span data-ttu-id="5ec4e-162">ブラウザー キャッシュがクリアされるまで、ユーザーは Percipio サイト名の入力を 1 回だけ求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-162">Users will be asked to input the Percipio site name only once, until their browser cache is cleared.</span></span> <span data-ttu-id="5ec4e-163">ユーザー向けこのエクスペリエンスを合理化するために、Viva ラーニング (Preview) に送信する内部通信に Percipio サイト名を含ラーニング勧めします。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-163">To streamline this experience for your users, we recommend including your Percipio site name in internal communications you send about Viva Learning (Preview).</span></span>

<span data-ttu-id="5ec4e-164">これはプレビューの一時的なエクスペリエンスを目的とします。また、スキルソフトと連携してテナント固有の統合を一般提供可能にしています。これにより、ユーザーが組織の Percipio サイト名を提供する必要がある手順はバイパスされます。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-164">This is intended to be a temporary experience for preview, and we are working with Skillsoft to enable tenant-specific integration for general availability, which will bypass the step that requires users to provide your organization's Percipio site name.</span></span> 

### <a name="details-on-microsoft-substrate"></a><span data-ttu-id="5ec4e-165">Microsoft の基体の詳細</span><span class="sxs-lookup"><span data-stu-id="5ec4e-165">Details on Microsoft substrate</span></span>  

<span data-ttu-id="5ec4e-166">Microsoft 以外のサービス (ラーニング プロバイダーまたは学習管理システム) から Viva ラーニング (Preview) にコピーするデータの場合、そのデータをビバ ラーニング (プレビュー) で直接抽出、修正、または削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-166">For data that you copy to Viva Learning (Preview) from a non-Microsoft service (learning provider or learning management system), you are not able to directly extract, correct, or delete that data in Viva Learning (Preview).</span></span> <span data-ttu-id="5ec4e-167">Microsoft 以外のプロバイダーからインポートしたデータは、Microsoft 以外のソース データの変更と削除を反映するように、速やかに更新されます。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-167">We refresh the data you import from non-Microsoft providers promptly to reflect changes and deletions in the non-Microsoft source data.</span></span>

<span data-ttu-id="5ec4e-168">Microsoft 以外のサービスの提供者と一緒に作業し、Microsoft 以外のサービスのライセンス、サービス、またはプライバシー条件に従ってデータにアクセス、修正、削除、または抽出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-168">You need to work with the supplier of the non-Microsoft service to access, correct, delete or extract data under the license, service, or privacy terms of the non-Microsoft service.</span></span> <span data-ttu-id="5ec4e-169">そこで行われた変更は、Microsoft 以外のサービスとビバ ラーニング (プレビュー) のデータ更新サイクルが完了すると、ビバ ラーニング (プレビュー) で使用するために処理されたデータに反映されます。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-169">The changes made there will be reflected in the data processed for your use in Viva Learning (Preview) upon completion of the data update cycles of the non-Microsoft service and Viva Learning (Preview).</span></span> <span data-ttu-id="5ec4e-170">Viva ラーニング (プレビュー) と Microsoft 以外のサービスとの間の接続をオフにした場合、そのサービスから以前にインポートしたデータはすべて削除されます。</span><span class="sxs-lookup"><span data-stu-id="5ec4e-170">If you turn off the connection between Viva Learning (Preview) and a non-Microsoft service, all data you had previously imported from that service will be deleted.</span></span> 

## <a name="next-step"></a><span data-ttu-id="5ec4e-171">次の手順</span><span class="sxs-lookup"><span data-stu-id="5ec4e-171">Next step</span></span>

[<span data-ttu-id="5ec4e-172">Microsoft Viva SharePointのラーニング コンテンツ ソースとしてラーニング構成する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="5ec4e-172">Configure SharePoint as a learning content source for Microsoft Viva Learning (Preview)</span></span>](configure-sharepoint-content-source.md)