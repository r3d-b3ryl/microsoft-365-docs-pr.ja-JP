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
description: パートナー組織の管理ゲストと B2B エクストラネット サイトまたはチームを作成する方法について説明します。
ms.openlocfilehash: f9b8d9326f302233ed85c9d168fdf6f343dc6cbf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904758"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a><span data-ttu-id="8f8cd-103">管理されたゲストで B2B エクストラネットを作成する</span><span class="sxs-lookup"><span data-stu-id="8f8cd-103">Create a B2B extranet with managed guests</span></span>

<span data-ttu-id="8f8cd-104">Azure Active Directory のエンタイトルメント [管理を使用](/azure/active-directory/governance/entitlement-management-overview) して、B2B エクストラネットを作成して、Azure Active Directory を使用するパートナー組織と共同作業できます。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-104">You can use [Azure Active Directory Entitlement Management](/azure/active-directory/governance/entitlement-management-overview) to create a B2B extranet to collaborate with a partner organization that uses Azure Active Directory.</span></span> <span data-ttu-id="8f8cd-105">これにより、ユーザーはエクストラネット サイトまたはチームに自己登録し、承認ワークフローを介してアクセスを受け取るできます。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-105">This allows users to self-enroll in the extranet site or team and receive access via an approval workflow.</span></span>

<span data-ttu-id="8f8cd-106">このグループ作業のリソースを共有する方法により、パートナー組織はゲストの維持と承認を支援し、IT 部門の負担を軽減し、コラボレーション契約に精通しているユーザーがユーザー アクセスを管理できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-106">With this method of sharing resources for collaboration, the partner organization can help maintain and approve the guests on their end, reducing the burden on your IT department and allowing those most familiar with the collaboration agreement to manage user access.</span></span>

<span data-ttu-id="8f8cd-107">この記事では、セルフサービス アクセス登録モデルを使用してパートナー組織と共有できるリソースのパッケージ (この場合はサイトまたはチーム) を作成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-107">This article walks through the steps to create a package of resources (in this case, a site or team) that you can share with a partner organization through a self-service access registration model.</span></span> 

<span data-ttu-id="8f8cd-108">開始する前に、パートナー組織と共有するサイトまたはチームを作成し、ゲスト共有のために有効にします。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-108">Before you begin, create the site or team that you want to share with the partner organization and enable it for guest sharing.</span></span> <span data-ttu-id="8f8cd-109">詳細 [については、「サイトのゲストと共同作業する」](collaborate-in-site.md) または「チーム内のゲストと共同作業 [する](collaborate-as-team.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-109">See [Collaborate with guests in a site](collaborate-in-site.md) or [Collaborate with guests in a team](collaborate-as-team.md) for more information.</span></span> <span data-ttu-id="8f8cd-110">また、ゲストと共同作業する[](create-secure-guest-sharing-environment.md)際にガバナンス ポリシーの維持に役立つセキュリティ機能とコンプライアンス機能に関する情報については、「セキュリティで保護されたゲスト共有環境を作成する」を参照することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-110">We also recommend that you review [Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) for information about security and compliance features that you can use to help maintain your governance policies when collaborating with guests.</span></span>

## <a name="license-requirements"></a><span data-ttu-id="8f8cd-111">ライセンス要件</span><span class="sxs-lookup"><span data-stu-id="8f8cd-111">License requirements</span></span>

<span data-ttu-id="8f8cd-112">この機能を使用するには、Azure ADプレミアム P2 ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-112">Using this feature requires an Azure AD Premium P2 license.</span></span> 

<span data-ttu-id="8f8cd-113">Azure Germany や Azure China 21Vianet などの特殊なクラウドは、現在使用できません。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-113">Specialized clouds, such as Azure Germany and Azure China 21Vianet, are not currently available for use.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="8f8cd-114">ビデオ デモンストレーション</span><span class="sxs-lookup"><span data-stu-id="8f8cd-114">Video demonstration</span></span>

<span data-ttu-id="8f8cd-115">このビデオでは、この記事で説明する手順を示します。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-115">This video demonstrates the procedures covered in this article.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wKUj?autoplay=false]

## <a name="connect-the-partner-organization"></a><span data-ttu-id="8f8cd-116">パートナー組織を接続する</span><span class="sxs-lookup"><span data-stu-id="8f8cd-116">Connect the partner organization</span></span>

<span data-ttu-id="8f8cd-117">パートナー組織からゲストを招待するには、パートナーのドメインを Azure Active Directory の接続組織として追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-117">In order to invite guests from a partner organization, you need to add the partner's domain as a connected organization in Azure Active Directory.</span></span>

<span data-ttu-id="8f8cd-118">接続された組織を追加するには</span><span class="sxs-lookup"><span data-stu-id="8f8cd-118">To add a connected organization</span></span>
1. <span data-ttu-id="8f8cd-119">[Azure Active Directory で、[ID ガバナンス](https://aad.portal.azure.com)]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-119">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="8f8cd-120">[接続 **された組織] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-120">Click **Connected organizations**.</span></span>
4. <span data-ttu-id="8f8cd-121">[接続 **された組織の追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-121">Click **Add connected organization**.</span></span>
5. <span data-ttu-id="8f8cd-122">組織の名前と説明を入力し、[次へ **: ディレクトリとドメイン] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-122">Type a name and description for the organization, and then click **Next: Directory + domain**.</span></span>
6. <span data-ttu-id="8f8cd-123">[ディレクトリ **とドメインの追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-123">Click **Add directory + domain**.</span></span>
7. <span data-ttu-id="8f8cd-124">接続する組織のドメインを入力し、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-124">Type the domain for the organization that you want to connect, and then click **Add**.</span></span>
8. <span data-ttu-id="8f8cd-125">[ **接続] を** クリックし、[次へ **: スポンサー] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-125">Click **Connect**, and then click **Next: Sponsors**.</span></span>
9. <span data-ttu-id="8f8cd-126">ゲストのアクセスを承認するユーザーに接続する組織または組織のユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-126">Add people from your organization or the organization that you're connecting to who you want to approve access for guests.</span></span>
10. <span data-ttu-id="8f8cd-127">**[次へ: 確認 + 作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-127">Click **Next: Review + Create**.</span></span>
11. <span data-ttu-id="8f8cd-128">選択した設定を確認し、[作成] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-128">Review the settings that you've chosen and then click **Create**.</span></span>

    ![Azure Active Directory の接続組織ページのスクリーンショット](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a><span data-ttu-id="8f8cd-130">共有するリソースを選択する</span><span class="sxs-lookup"><span data-stu-id="8f8cd-130">Choose the resources to share</span></span>

<span data-ttu-id="8f8cd-131">パートナー組織と共有するリソースを選択する最初の手順は、それらを含むカタログを作成します。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-131">The first step in selecting resources to share with a partner organization is to create a catalog to contain them.</span></span>

<span data-ttu-id="8f8cd-132">カタログを作成するには</span><span class="sxs-lookup"><span data-stu-id="8f8cd-132">To create a catalog</span></span>
1. <span data-ttu-id="8f8cd-133">[Azure Active Directory で、[ID ガバナンス](https://aad.portal.azure.com)]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-133">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="8f8cd-134">[カタログ **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-134">Click **Catalogs**.</span></span>
3. <span data-ttu-id="8f8cd-135">[新 **しいカタログ] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-135">Click **New catalog**.</span></span>
4. <span data-ttu-id="8f8cd-136">カタログの名前と説明を入力し、外部ユーザーに対して **有効** と有効の両方が [はい]**に設定されています**。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-136">Type a name and description for the catalog and ensure that **Enabled** and **Enabled for external users** are both set to **Yes**.</span></span>
5. <span data-ttu-id="8f8cd-137">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-137">Click **Create**.</span></span>

   ![Azure Active Directory Identity Governance のカタログ ページのスクリーンショット](../media/identity-governance-catalogs.png)

<span data-ttu-id="8f8cd-139">カタログを作成したら、パートナー組織と共有する SharePoint サイトまたはチームを追加します。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-139">Once the catalog has been created, you add the SharePoint site or team that you want to share with the partner organization.</span></span>

<span data-ttu-id="8f8cd-140">カタログにリソースを追加するには</span><span class="sxs-lookup"><span data-stu-id="8f8cd-140">To add resources to a catalog</span></span>
1. <span data-ttu-id="8f8cd-141">Azure AD ID ガバナンスで、[カタログ] をクリックし、リソースを追加するカタログをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-141">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to add resources.</span></span>
2. <span data-ttu-id="8f8cd-142">[リソース **] をクリック** し、[リソースの **追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-142">Click **Resources** and then click **Add resources**.</span></span>
3. <span data-ttu-id="8f8cd-143">エクストラネットに含めるチームまたは SharePoint サイトを選択し、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-143">Select the teams or SharePoint sites that you want to include in your extranet, and then click **Add**.</span></span>

   ![Azure Active Directory Identity Governance のカタログ リソース ページのスクリーンショット](../media/identity-governance-catalog-resource.png)

<span data-ttu-id="8f8cd-145">共有するリソースを定義したら、次に、パートナー ユーザーに付与されるアクセスの種類と、アクセスを要求する新しいパートナー ユーザーの承認プロセスを定義するアクセス パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-145">Once you've defined the resources that you want to share, the next step is to create an access package, which defines the type of access that partner users are granted and the approval process for new partner users requesting access.</span></span>

<span data-ttu-id="8f8cd-146">アクセス パッケージを作成するには</span><span class="sxs-lookup"><span data-stu-id="8f8cd-146">To create an access package</span></span>
1. <span data-ttu-id="8f8cd-147">Azure AD ID ガバナンスで、[カタログ] をクリックし、アクセス パッケージを作成するカタログをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-147">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to create an access package.</span></span>
2. <span data-ttu-id="8f8cd-148">[Access **パッケージ] を** クリックし、[新しいアクセス **パッケージ] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-148">Click **Access packages**, and then click **New access package**.</span></span>
3. <span data-ttu-id="8f8cd-149">アクセス パッケージの名前と説明を入力し、[次へ: リソースの役割 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-149">Type a name and description for the access package, and then click **Next: Resource roles**.</span></span>
4. <span data-ttu-id="8f8cd-150">エクストラネットに使用するカタログからリソースを選択します。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-150">Choose the resources from the catalog that you want to use for your extranet.</span></span>
5. <span data-ttu-id="8f8cd-151">リソースごとに、[役割] **列で** 、エクストラネットを使用するゲストに付与するユーザー ロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-151">For each resource, in the **Role** column, choose the user role you want to grant to the guests who use the extranet.</span></span>
6. <span data-ttu-id="8f8cd-152">[次 **へ: 要求] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-152">Click **Next: Requests**.</span></span>
7. <span data-ttu-id="8f8cd-153">[ **アクセスを要求できるユーザー] で**、[ディレクトリ **に含めないユーザー] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-153">Under **Users who can request access**, choose **For users not in your directory**.</span></span>
8. <span data-ttu-id="8f8cd-154">[特定の接続 **組織] オプション** が選択されていることを確認し、[ディレクトリの追加] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-154">Ensure that the **Specific connected organizations** option is selected, and then click **Add directories**.</span></span>
9. <span data-ttu-id="8f8cd-155">前に追加した接続組織を選択し、[選択] をクリック **します。**</span><span class="sxs-lookup"><span data-stu-id="8f8cd-155">Choose the connected organization that you add earlier, and then click **Select**</span></span>
10. <span data-ttu-id="8f8cd-156">[承認 **] で**、[承認の **要求] で [は\*\*\*\*い] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-156">Under **Approval**, choose **Yes** for **Require approval**.</span></span>
11. <span data-ttu-id="8f8cd-157">[ **最初の承認者]** で、前に追加したスポンサーのいずれかを選択するか、特定のユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-157">Under **First approver**, choose one of the sponsors that you added earlier or choose a specific user.</span></span>
12. <span data-ttu-id="8f8cd-158">[フォールバック **の追加] を** クリックし、フォールバック承認者を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-158">Click **Add fallback** and select a fallback approver.</span></span>
13. <span data-ttu-id="8f8cd-159">[有効 **] で**、[はい] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-159">Under **Enable**, choose **Yes**.</span></span>
14. <span data-ttu-id="8f8cd-160">[次 **へ: ライフサイクル] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-160">Click **Next: Lifecycle**.</span></span>
15. <span data-ttu-id="8f8cd-161">使用する有効期限とアクセスレビュー設定を選択し、[次へ: レビュー+ 作成] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-161">Choose the expiration and access review settings that you want to use, and then click **Next: Review + Create**.</span></span>
16. <span data-ttu-id="8f8cd-162">設定を確認し、[作成] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-162">Review your settings, and then click **Create**.</span></span>

    ![Azure Active Directory Identity Governance の [アクセス パッケージ] 画面のスクリーンショット](../media/identity-governance-access-packages.png)

<span data-ttu-id="8f8cd-164">大規模な組織と提携している場合は、アクセス パッケージを非表示にできます。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-164">If you're partnering with a large organization, you may want to hide the access package.</span></span> <span data-ttu-id="8f8cd-165">パッケージが非表示の場合、パートナー組織のユーザーは自分のマイ アクセス ポータルにパッケージ *を表示* されません。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-165">If the package is hidden, then users in the partner organization will not see the package on their *My Access* portal.</span></span> <span data-ttu-id="8f8cd-166">代わりに、パッケージにサインアップするために直接リンクを送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-166">Instead, they must be sent a direct link to sign up for the package.</span></span> <span data-ttu-id="8f8cd-167">アクセス パッケージを非表示にすると、不適切なアクセス要求の数が減り、パートナー組織のポータルで利用可能なアクセス パッケージを整理し続けるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-167">Hiding the access package can reduce the number of inappropriate access requests and can also help keep available access packages organized in the partner organization's portal.</span></span>

<span data-ttu-id="8f8cd-168">アクセス パッケージを非表示に設定するには</span><span class="sxs-lookup"><span data-stu-id="8f8cd-168">To set an access package to hidden</span></span>
1. <span data-ttu-id="8f8cd-169">Azure AD ID ガバナンスで、[Access パッケージ] を **クリック** し、アクセス パッケージをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-169">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="8f8cd-170">[概要] **ページで** 、[編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-170">On the **Overview** page, click **Edit**.</span></span>
3. <span data-ttu-id="8f8cd-171">[プロパティ **] で**、[非表示] で **[は** い] **を** 選択し、[保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-171">Under **Properties**, choose **Yes** for **Hidden**, and then click **Save**.</span></span>

   ![[アクセス パッケージのプロパティの編集] 画面のスクリーンショット](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a><span data-ttu-id="8f8cd-173">パートナー ユーザーの招待</span><span class="sxs-lookup"><span data-stu-id="8f8cd-173">Invite partner users</span></span>

<span data-ttu-id="8f8cd-174">アクセス パッケージを非表示に設定した場合は、パートナー組織に直接リンクを送信して、サイトまたはチームへのアクセスを要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-174">If you set the access package to hidden, you need to send a direct link to the partner organization so that they can request access to your site or team.</span></span>

<span data-ttu-id="8f8cd-175">アクセス ポータルリンクを見つけるには</span><span class="sxs-lookup"><span data-stu-id="8f8cd-175">To find the access portal link</span></span>
1. <span data-ttu-id="8f8cd-176">Azure AD ID ガバナンスで、[Access パッケージ] を **クリック** し、アクセス パッケージをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-176">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="8f8cd-177">[概要] **ページで** 、[ **マイ** アクセス ポータル] リンクの [クリップボードにコピー] **リンクをクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-177">On the **Overview** page, click **Copy to clipboard** link for the **My Access portal link**.</span></span>

   ![アクセス ポータル リンクを使用したアクセス パッケージのプロパティのスクリーンショット](../media/identity-governance-access-portal-link.png)

<span data-ttu-id="8f8cd-179">リンクをコピーしたら、パートナー組織の連絡先と共有し、そのリンクをコラボレーション チームのユーザーに送信できます。</span><span class="sxs-lookup"><span data-stu-id="8f8cd-179">Once you have copied the link, you can share it with your contact at the partner organization and they can send it to the users on their collaboration team.</span></span>

## <a name="see-also"></a><span data-ttu-id="8f8cd-180">関連項目</span><span class="sxs-lookup"><span data-stu-id="8f8cd-180">See Also</span></span>

[<span data-ttu-id="8f8cd-181">セキュリティで保護されたゲスト共有の環境を作成する</span><span class="sxs-lookup"><span data-stu-id="8f8cd-181">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)