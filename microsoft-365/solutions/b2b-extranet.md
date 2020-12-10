---
title: 管理されたゲストで B2B エクストラネットを作成する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom: ''
localization_priority: Normal
f1.keywords: NOCSH
description: パートナー組織から管理されたゲストを使用して、B2B エクストラネットのサイトまたはチームを作成する方法について説明します。
ms.openlocfilehash: cfb7cc4310cb83f9ce7761c95f021724b7d75faf
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613598"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a><span data-ttu-id="53bb7-103">管理されたゲストで B2B エクストラネットを作成する</span><span class="sxs-lookup"><span data-stu-id="53bb7-103">Create a B2B extranet with managed guests</span></span>

<span data-ttu-id="53bb7-104">Azure active [Directory 受給管理](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) を使用して、Azure active directory を使用するパートナー組織と共同作業する B2B エクストラネットを作成できます。</span><span class="sxs-lookup"><span data-stu-id="53bb7-104">You can use [Azure Active Directory Entitlement Management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) to create a B2B extranet to collaborate with a partner organization that uses Azure Active Directory.</span></span> <span data-ttu-id="53bb7-105">これにより、ユーザーは、エクストラネットサイトまたはチームで自分を登録し、承認ワークフローを使用してアクセスを受信することができます。</span><span class="sxs-lookup"><span data-stu-id="53bb7-105">This allows users to self-enroll in the extranet site or team and receive access via an approval workflow.</span></span>

<span data-ttu-id="53bb7-106">グループ作業のためにリソースを共有するためのこの方法を使用すると、パートナー組織は、IT 部門の負担を軽減し、ユーザーアクセスを管理するためのコラボレーション契約に精通していることを許可することができます。</span><span class="sxs-lookup"><span data-stu-id="53bb7-106">With this method of sharing resources for collaboration, the partner organization can help maintain and approve the guests on their end, reducing the burden on your IT department and allowing those most familiar with the collaboration agreement to manage user access.</span></span>

<span data-ttu-id="53bb7-107">この記事では、セルフサービスアクセス登録モデルを使用してパートナー組織と共有できるリソース (この場合は、サイトまたはチーム) のパッケージを作成するための手順を順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="53bb7-107">This article walks through the steps to create a package of resources (in this case, a site or team) that you can share with a partner organization through a self-service access registration model.</span></span> 

<span data-ttu-id="53bb7-108">開始する前に、パートナー組織と共有するサイトまたはチームを作成し、ゲスト共有に対して有効にします。</span><span class="sxs-lookup"><span data-stu-id="53bb7-108">Before you begin, create the site or team that you want to share with the partner organization and enable it for guest sharing.</span></span> <span data-ttu-id="53bb7-109">詳細については [、「サイト内のゲストを使用した共同作業](collaborate-in-site.md) 」または「 [チーム内のゲストによる共同作業](collaborate-as-team.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53bb7-109">See [Collaborate with guests in a site](collaborate-in-site.md) or [Collaborate with guests in a team](collaborate-as-team.md) for more information.</span></span> <span data-ttu-id="53bb7-110">また、ゲストを使用して共同作業を行う場合に、ガバナンスポリシーを維持するために使用できるセキュリティとコンプライアンスの機能については、「セキュリティ [保護されたゲスト共有環境を作成](create-secure-guest-sharing-environment.md) する」を参照することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="53bb7-110">We also recommend that you review [Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) for information about security and compliance features that you can use to help maintain your governance policies when collaborating with guests.</span></span>

## <a name="license-requirements"></a><span data-ttu-id="53bb7-111">ライセンス要件</span><span class="sxs-lookup"><span data-stu-id="53bb7-111">License requirements</span></span>

<span data-ttu-id="53bb7-112">この機能を使用するには、Azure AD Premium P2 ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="53bb7-112">Using this feature requires an Azure AD Premium P2 license.</span></span> 

<span data-ttu-id="53bb7-113">Azure ドイツおよび Azure 中国21Vianet などの専門クラウドは現在使用できません。</span><span class="sxs-lookup"><span data-stu-id="53bb7-113">Specialized clouds, such as Azure Germany and Azure China 21Vianet, are not currently available for use.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="53bb7-114">ビデオ デモンストレーション</span><span class="sxs-lookup"><span data-stu-id="53bb7-114">Video demonstration</span></span>

<span data-ttu-id="53bb7-115">このビデオでは、この記事で説明する手順を示します。</span><span class="sxs-lookup"><span data-stu-id="53bb7-115">This video demonstrates the procedures covered in this article.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wKUj?autoplay=false]

## <a name="connect-the-partner-organization"></a><span data-ttu-id="53bb7-116">パートナー組織を接続する</span><span class="sxs-lookup"><span data-stu-id="53bb7-116">Connect the partner organization</span></span>

<span data-ttu-id="53bb7-117">パートナー組織からゲストを招待するには、パートナーのドメインを Azure Active Directory に接続された組織として追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53bb7-117">In order to invite guests from a partner organization, you need to add the partner's domain as a connected organization in Azure Active Directory.</span></span>

<span data-ttu-id="53bb7-118">接続された組織を追加するには</span><span class="sxs-lookup"><span data-stu-id="53bb7-118">To add a connected organization</span></span>
1. <span data-ttu-id="53bb7-119">[Azure Active Directory](https://aad.portal.azure.com)で、[ **id ガバナンス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bb7-119">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="53bb7-120">[ **接続組織**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bb7-120">Click **Connected organizations**.</span></span>
4. <span data-ttu-id="53bb7-121">[ **接続組織の追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bb7-121">Click **Add connected organization**.</span></span>
5. <span data-ttu-id="53bb7-122">組織の名前と説明を入力し、[ **次へ: ディレクトリ + ドメイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bb7-122">Type a name and description for the organization, and then click **Next: Directory + domain**.</span></span>
6. <span data-ttu-id="53bb7-123">[ **ディレクトリ + ドメインの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bb7-123">Click **Add directory + domain**.</span></span>
7. <span data-ttu-id="53bb7-124">接続する組織のドメインを入力し、[ **追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bb7-124">Type the domain for the organization that you want to connect, and then click **Add**.</span></span>
8. <span data-ttu-id="53bb7-125">[ **接続**] をクリックし、[ **次へ: スポンサー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bb7-125">Click **Connect**, and then click **Next: Sponsors**.</span></span>
9. <span data-ttu-id="53bb7-126">組織内のユーザーまたは接続している組織から、ゲストのアクセスを承認するユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="53bb7-126">Add people from your organization or the organization that you're connecting to who you want to approve access for guests.</span></span>
10. <span data-ttu-id="53bb7-127">[ **Next: Review + Create**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bb7-127">Click **Next: Review + Create**.</span></span>
11. <span data-ttu-id="53bb7-128">選択した設定を確認し、[ **作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bb7-128">Review the settings that you've chosen and then click **Create**.</span></span>

    ![Azure Active Directory の [接続されている組織] ページのスクリーンショット](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a><span data-ttu-id="53bb7-130">共有するリソースを選択する</span><span class="sxs-lookup"><span data-stu-id="53bb7-130">Choose the resources to share</span></span>

<span data-ttu-id="53bb7-131">パートナー組織と共有するリソースを選択する最初の手順は、それらを含めるためのカタログを作成することです。</span><span class="sxs-lookup"><span data-stu-id="53bb7-131">The first step in selecting resources to share with a partner organization is to create a catalog to contain them.</span></span>

<span data-ttu-id="53bb7-132">カタログを作成するには</span><span class="sxs-lookup"><span data-stu-id="53bb7-132">To create a catalog</span></span>
1. <span data-ttu-id="53bb7-133">[Azure Active Directory](https://aad.portal.azure.com)で、[ **id ガバナンス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bb7-133">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="53bb7-134">[ **カタログ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bb7-134">Click **Catalogs**.</span></span>
3. <span data-ttu-id="53bb7-135">[ **新しいカタログ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bb7-135">Click **New catalog**.</span></span>
4. <span data-ttu-id="53bb7-136">カタログの名前と説明を入力し、[ **有効** ] と [ **外部ユーザーが有効** ] と [有効] の両方が **[はい]** に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="53bb7-136">Type a name and description for the catalog and ensure that **Enabled** and **Enabled for external users** are both set to **Yes**.</span></span>
5. <span data-ttu-id="53bb7-137">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bb7-137">Click **Create**.</span></span>

   ![Azure Active Directory Id ガバナンスの [カタログ] ページのスクリーンショット](../media/identity-governance-catalogs.png)

<span data-ttu-id="53bb7-139">カタログを作成したら、パートナー組織と共有する SharePoint サイトまたはチームを追加します。</span><span class="sxs-lookup"><span data-stu-id="53bb7-139">Once the catalog has been created, you add the SharePoint site or team that you want to share with the partner organization.</span></span>

<span data-ttu-id="53bb7-140">リソースをカタログに追加するには</span><span class="sxs-lookup"><span data-stu-id="53bb7-140">To add resources to a catalog</span></span>
1. <span data-ttu-id="53bb7-141">Azure AD Identity ガバナンスで、[ **カタログ**] をクリックし、リソースを追加するカタログをクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bb7-141">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to add resources.</span></span>
2. <span data-ttu-id="53bb7-142">[ **リソース** ] をクリックし、[ **リソースの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bb7-142">Click **Resources** and then click **Add resources**.</span></span>
3. <span data-ttu-id="53bb7-143">エクストラネットに含める teams または SharePoint サイトを選択し、[ **追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bb7-143">Select the teams or SharePoint sites that you want to include in your extranet, and then click **Add**.</span></span>

   ![Azure Active Directory Id ガバナンスの [カタログリソース] ページのスクリーンショット](../media/identity-governance-catalog-resource.png)

<span data-ttu-id="53bb7-145">共有するリソースを定義したら、次の手順として、アクセスパッケージを作成します。これにより、パートナーユーザーに付与されるアクセスの種類、およびアクセスを要求する新しいパートナーユーザーの承認プロセスが定義されます。</span><span class="sxs-lookup"><span data-stu-id="53bb7-145">Once you've defined the resources that you want to share, the next step is to create an access package, which defines the type of access that partner users are granted and the approval process for new partner users requesting access.</span></span>

<span data-ttu-id="53bb7-146">アクセスパッケージを作成するには</span><span class="sxs-lookup"><span data-stu-id="53bb7-146">To create an access package</span></span>
1. <span data-ttu-id="53bb7-147">Azure AD Identity ガバナンスで、[ **カタログ**] をクリックし、アクセスパッケージを作成するカタログをクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bb7-147">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to create an access package.</span></span>
2. <span data-ttu-id="53bb7-148">[ **Access パッケージ**] をクリックし、[ **新しいアクセスパッケージ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bb7-148">Click **Access packages**, and then click **New access package**.</span></span>
3. <span data-ttu-id="53bb7-149">アクセスパッケージの名前と説明を入力し、[ **次へ: リソースロール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bb7-149">Type a name and description for the access package, and then click **Next: Resource roles**.</span></span>
4. <span data-ttu-id="53bb7-150">エクストラネットに使用するリソースをカタログから選択します。</span><span class="sxs-lookup"><span data-stu-id="53bb7-150">Choose the resources from the catalog that you want to use for your extranet.</span></span>
5. <span data-ttu-id="53bb7-151">各リソースの [ **役割** ] 列で、エクストラネットを使用するゲストに付与するユーザーの役割を選択します。</span><span class="sxs-lookup"><span data-stu-id="53bb7-151">For each resource, in the **Role** column, choose the user role you want to grant to the guests who use the extranet.</span></span>
6. <span data-ttu-id="53bb7-152">[ **次へ: 要求**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bb7-152">Click **Next: Requests**.</span></span>
7. <span data-ttu-id="53bb7-153">[ **アクセスを要求できるユーザー**] で、 **ディレクトリ以外のユーザーに対して**[] を選択します。</span><span class="sxs-lookup"><span data-stu-id="53bb7-153">Under **Users who can request access**, choose **For users not in your directory**.</span></span>
8. <span data-ttu-id="53bb7-154">[特定の **接続組織** ] オプションが選択されていることを確認し、[ **ディレクトリの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bb7-154">Ensure that the **Specific connected organizations** option is selected, and then click **Add directories**.</span></span>
9. <span data-ttu-id="53bb7-155">以前に追加した接続済み組織を選択し、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bb7-155">Choose the connected organization that you add earlier, and then click **Select**</span></span>
10. <span data-ttu-id="53bb7-156">[**承認**] で、[**承認を必須** にする] で [**はい]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="53bb7-156">Under **Approval**, choose **Yes** for **Require approval**.</span></span>
11. <span data-ttu-id="53bb7-157">[ **最初の承認者**] で、前に追加したスポンサのいずれかを選択するか、特定のユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="53bb7-157">Under **First approver**, choose one of the sponsors that you added earlier or choose a specific user.</span></span>
12. <span data-ttu-id="53bb7-158">[ **フォールバックの追加** ] をクリックし、フォールバック承認者を選択します。</span><span class="sxs-lookup"><span data-stu-id="53bb7-158">Click **Add fallback** and select a fallback approver.</span></span>
13. <span data-ttu-id="53bb7-159">[ **有効にする**] で、[ **はい]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="53bb7-159">Under **Enable**, choose **Yes**.</span></span>
14. <span data-ttu-id="53bb7-160">[ **次へ: ライフサイクル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bb7-160">Click **Next: Lifecycle**.</span></span>
15. <span data-ttu-id="53bb7-161">使用する有効期限とアクセスレビューの設定を選択し、[次へ] をクリックします。 [ **確認 + 作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bb7-161">Choose the expiration and access review settings that you want to use, and then click **Next: Review + Create**.</span></span>
16. <span data-ttu-id="53bb7-162">設定内容を確認し、[ **作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bb7-162">Review your settings, and then click **Create**.</span></span>

    ![Azure Active Directory Id ガバナンスの [access パッケージ] 画面のスクリーンショット](../media/identity-governance-access-packages.png)

<span data-ttu-id="53bb7-164">大規模な組織と提携している場合は、アクセスパッケージを非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="53bb7-164">If you're partnering with a large organization, you may want to hide the access package.</span></span> <span data-ttu-id="53bb7-165">パッケージが非表示の場合、パートナー組織のユーザーには、 *自分のアクセス* ポータルにパッケージが表示されません。</span><span class="sxs-lookup"><span data-stu-id="53bb7-165">If the package is hidden, then users in the partner organization will not see the package on their *My Access* portal.</span></span> <span data-ttu-id="53bb7-166">代わりに、そのパッケージにサインアップするための直接リンクを送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53bb7-166">Instead, they must be sent a direct link to sign up for the package.</span></span> <span data-ttu-id="53bb7-167">アクセスパッケージを非表示にすると、不適切なアクセス要求の数を減らすことができます。また、パートナー組織のポータルで利用できるアクセスパッケージを保持するのにも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="53bb7-167">Hiding the access package can reduce the number of inappropriate access requests and can also help keep available access packages organized in the partner organization's portal.</span></span>

<span data-ttu-id="53bb7-168">アクセスパッケージを非表示に設定するには</span><span class="sxs-lookup"><span data-stu-id="53bb7-168">To set an access package to hidden</span></span>
1. <span data-ttu-id="53bb7-169">[Azure AD Identity ガバナンス] で、[ **アクセスパッケージ**] をクリックし、アクセスパッケージをクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bb7-169">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="53bb7-170">[ **概要** ] ページで、[ **編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bb7-170">On the **Overview** page, click **Edit**.</span></span>
3. <span data-ttu-id="53bb7-171">[**プロパティ**] で [**非表示** の場合は **はい]** を選択し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bb7-171">Under **Properties**, choose **Yes** for **Hidden**, and then click **Save**.</span></span>

   ![[Access パッケージの編集のプロパティ] 画面のスクリーンショット](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a><span data-ttu-id="53bb7-173">パートナーユーザーの招待</span><span class="sxs-lookup"><span data-stu-id="53bb7-173">Invite partner users</span></span>

<span data-ttu-id="53bb7-174">アクセスパッケージを非表示に設定した場合は、パートナー組織への直接リンクを送信して、サイトまたはチームへのアクセスを要求できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="53bb7-174">If you set the access package to hidden, you need to send a direct link to the partner organization so that they can request access to your site or team.</span></span>

<span data-ttu-id="53bb7-175">アクセスポータルのリンクを見つけるには</span><span class="sxs-lookup"><span data-stu-id="53bb7-175">To find the access portal link</span></span>
1. <span data-ttu-id="53bb7-176">[Azure AD Identity ガバナンス] で、[ **アクセスパッケージ**] をクリックし、アクセスパッケージをクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bb7-176">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="53bb7-177">[**概要**] ページで、[ **My Access ポータル] リンク** の [**クリップボードにコピー** ] リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bb7-177">On the **Overview** page, click **Copy to clipboard** link for the **My Access portal link**.</span></span>

   ![Access ポータルリンクを使用した access パッケージプロパティのスクリーンショット](../media/identity-governance-access-portal-link.png)

<span data-ttu-id="53bb7-179">リンクをコピーしたら、パートナー組織の連絡先と共有することができます。また、そのリンクをコラボレーションチームのユーザーに送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="53bb7-179">Once you have copied the link, you can share it with your contact at the partner organization and they can send it to the users on their collaboration team.</span></span>

## <a name="see-also"></a><span data-ttu-id="53bb7-180">関連項目</span><span class="sxs-lookup"><span data-stu-id="53bb7-180">See Also</span></span>

[<span data-ttu-id="53bb7-181">セキュリティで保護されたゲスト共有の環境を作成する</span><span class="sxs-lookup"><span data-stu-id="53bb7-181">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)
