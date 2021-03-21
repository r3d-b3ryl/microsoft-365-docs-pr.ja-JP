---
title: Microsoft 365 での高度な電子情報開示のセットアップ
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: この記事では、ケースの作成と管理を開始するために高度な電子情報開示をセットアップする方法について説明します。 また、必要な Microsoft サブスクリプションとライセンスも説明します。 いくつかの簡単な手順を完了すると、高度な電子情報開示ツールを使用する準備が整いました。
ms.openlocfilehash: 6c6aed482da8f203154d94313ec04519d6a330ea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919749"
---
# <a name="set-up-microsoft-365-advanced-ediscovery"></a><span data-ttu-id="dc42c-105">Microsoft 365 Advanced eDiscovery のセットアップ</span><span class="sxs-lookup"><span data-stu-id="dc42c-105">Set up Microsoft 365 Advanced eDiscovery</span></span>

<span data-ttu-id="dc42c-106">Microsoft 365 の高度な電子情報開示は、組織の内部および外部調査に対応するデータを保存、収集、レビュー、分析、エクスポートするためのエンドツーエンドのワークフローを提供します。</span><span class="sxs-lookup"><span data-stu-id="dc42c-106">Advanced eDiscovery in Microsoft 365 provides an end-to-end workflow to preserve, collect, review, analyze, and export data that's responsive to your organization's internal and external investigations.</span></span> <span data-ttu-id="dc42c-107">Advanced eDiscovery を展開するために必要なタスクは何もありませんが、組織が Advanced eDiscovery ケースの作成と使用を開始して調査を管理するには、IT 管理者と電子情報開示マネージャーが完了する必要があるいくつかの前提条件タスクがあります。</span><span class="sxs-lookup"><span data-stu-id="dc42c-107">Nothing is needed to deploy Advanced eDiscovery, but there are some prerequisite tasks that an IT admin and eDiscovery manager have to complete before your organization can start to create and use Advanced eDiscovery cases to manage your investigations.</span></span>

<span data-ttu-id="dc42c-108">この記事では、Advanced eDiscovery のセットアップに必要な以下の手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="dc42c-108">This article discusses the following steps necessary to set up Advanced eDiscovery.</span></span>

![高度な電子情報開示をセットアップする手順](../media/set-up-advanced-ediscovery.png)

<span data-ttu-id="dc42c-110">これには、Advanced eDiscovery にアクセスし、ケースにカストディアンを追加するために必要な適切なライセンスを確保し、ケースにアクセスして管理するための権限を法務および調査チームに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc42c-110">This includes ensuring the proper licensing required to access Advanced eDiscovery and add custodians to cases, and assigning permissions to your legal and investigation team so they can access and manage cases.</span></span>

## <a name="step-1-verify-and-assign-appropriate-licenses"></a><span data-ttu-id="dc42c-111">手順 1: 適切なライセンスを確認して割り当てる</span><span class="sxs-lookup"><span data-stu-id="dc42c-111">Step 1: Verify and assign appropriate licenses</span></span>

<span data-ttu-id="dc42c-112">Advanced eDiscovery のライセンスには、適切な組織のサブスクリプションとユーザーごとのライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="dc42c-112">Licensing for Advanced eDiscovery requires the appropriate organization subscription and per-user licensing.</span></span> <span data-ttu-id="dc42c-113">Advanced eDiscovery のライセンス要件の一覧については、「サブスクリプションとライセンス」 [を参照してください](overview-ediscovery-20.md#subscriptions-and-licensing)。</span><span class="sxs-lookup"><span data-stu-id="dc42c-113">For a list of licensing requirements for Advanced eDiscovery, see [Subscriptions and licensing](overview-ediscovery-20.md#subscriptions-and-licensing).</span></span>

## <a name="step-2-assign-ediscovery-permissions"></a><span data-ttu-id="dc42c-114">手順 2: 電子情報開示のアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="dc42c-114">Step 2: Assign eDiscovery permissions</span></span>

<span data-ttu-id="dc42c-115">高度な電子情報開示にアクセスしたり、高度な電子情報開示ケースのメンバーとして追加したりするには、ユーザーに適切なアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc42c-115">To access Advanced eDiscovery or added as a member of an Advanced eDiscovery case, a user must be assigned the appropriate permissions.</span></span> <span data-ttu-id="dc42c-116">具体的には、ユーザーをセキュリティ コンプライアンス センターの電子情報開示マネージャー役割グループのメンバー&する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc42c-116">Specifically, a user must be added as a member of the eDiscovery Manager role group in the Security & Compliance Center.</span></span> <span data-ttu-id="dc42c-117">この役割グループのメンバーは、高度な電子情報開示ケースを作成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="dc42c-117">Members of this role group can create and manage Advanced eDiscovery cases.</span></span> <span data-ttu-id="dc42c-118">メンバーの追加と削除、保管担当者とコンテンツの場所の保留、法的保留通知の管理、ケースに関連付けられた検索の作成と編集、レビュー セットへの検索結果の追加、レビュー セット内のデータの分析、Advanced eDiscovery ケースからのエクスポートとダウンロードを行います。</span><span class="sxs-lookup"><span data-stu-id="dc42c-118">They can add and remove members, place custodians and content locations on hold, manage legal hold notifications, create and edit searches associated in a case, add search results to a review set, analyze data in a review set, and export and download from an Advanced eDiscovery case.</span></span>

<span data-ttu-id="dc42c-119">電子情報開示マネージャーの役割グループにユーザーを追加するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="dc42c-119">Complete the following steps to add users to the eDiscovery Manager role group:</span></span>

1. <span data-ttu-id="dc42c-120">Microsoft 365 組織の管理者アカウントの資格情報を使用して、 <https://protection.office.com/permissions> アクセスしてサインインします。</span><span class="sxs-lookup"><span data-stu-id="dc42c-120">Go to <https://protection.office.com/permissions> and sign in using the credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="dc42c-121">[アクセス許可 **] ページで** 、電子情報開示マネージャー **の役割グループを** 選択します。</span><span class="sxs-lookup"><span data-stu-id="dc42c-121">On the **Permissions** page, select the **eDiscovery Manager** role group.</span></span>

3. <span data-ttu-id="dc42c-122">[電子情報開示マネージャー] フライアウト ページで、[電子情報開示マネージャー] セクション **の横** にある [ **編集] をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="dc42c-122">On the eDiscovery Manager flyout page, click **Edit** next to the **eDiscovery Manager** section.</span></span>

4. <span data-ttu-id="dc42c-123">役割グループ **の編集ウィザードの [電子情報開示マネージャー** の選択] ページで、[電子情報開示マネージャーの選択] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="dc42c-123">On the **Choose eDiscovery Manager** page in the edit role group wizard, click **Choose eDiscovery Manager**.</span></span>

5. <span data-ttu-id="dc42c-124">[ **追加]** をクリックし、役割グループに追加するすべてのユーザーのチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="dc42c-124">Click **Add** then select the checkbox for all users you want to add to the role group.</span></span>

6. <span data-ttu-id="dc42c-125">[追加 **] を** クリックして選択したユーザーを追加し、[完了] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="dc42c-125">Click **Add** to add the selected users, and then click **Done**.</span></span>

7. <span data-ttu-id="dc42c-126">[ **保存]** をクリックしてユーザーを役割グループに追加し、[閉じる] をクリック **して** 手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="dc42c-126">Click **Save** to add the users to the role group, and then click **Close** to complete the step.</span></span>

### <a name="more-information-about-the-ediscovery-manager-role-group"></a><span data-ttu-id="dc42c-127">電子情報開示マネージャー役割グループの詳細</span><span class="sxs-lookup"><span data-stu-id="dc42c-127">More information about the eDiscovery Manager role group</span></span>

<span data-ttu-id="dc42c-128">電子情報開示マネージャーの役割グループには、2 つのサブグループがあります。</span><span class="sxs-lookup"><span data-stu-id="dc42c-128">There are two subgroups in the eDiscovery Manager role group.</span></span> <span data-ttu-id="dc42c-129">これらのサブグループの違いは、スコープに基づきます。</span><span class="sxs-lookup"><span data-stu-id="dc42c-129">The difference between these subgroups is based on scope.</span></span>

- <span data-ttu-id="dc42c-130">**電子情報開示マネージャー**: 作成またはメンバーである高度な電子情報開示ケースを表示および管理できます。</span><span class="sxs-lookup"><span data-stu-id="dc42c-130">**eDiscovery Manager**: Can view and manage the Advanced eDiscovery cases they create or are a member of.</span></span> <span data-ttu-id="dc42c-131">別の電子情報開示マネージャーがケースを作成しても、そのケースのメンバーとして 2 番目の電子情報開示マネージャーを追加しない場合、2 番目の電子情報開示マネージャーは、コンプライアンス センターの [高度な電子情報開示] ページでケースを表示または開くことができません。</span><span class="sxs-lookup"><span data-stu-id="dc42c-131">If another eDiscovery Manager creates a case but doesn't add a second eDiscovery Manager as a member of that case, the second eDiscovery Manager won't be able to view or open the case on the Advanced eDiscovery page in the compliance center.</span></span> <span data-ttu-id="dc42c-132">一般に、組織内のほとんどのユーザーは、電子情報開示マネージャー サブグループに追加できます。</span><span class="sxs-lookup"><span data-stu-id="dc42c-132">In general, most people in your organization can be added to the eDiscovery Manager subgroup.</span></span>

- <span data-ttu-id="dc42c-133">**電子情報開示管理者**: 電子情報開示マネージャーが実行できるすべてのケース管理タスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="dc42c-133">**eDiscovery Administrator**: Can perform all case management tasks that an eDiscovery Manager can do.</span></span> <span data-ttu-id="dc42c-134">さらに、電子情報開示管理者は、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="dc42c-134">Additionally, an eDiscovery Administrator can:</span></span>

  - <span data-ttu-id="dc42c-135">[Advanced eDiscovery] ページにリストされたすべてのケースを表示します。</span><span class="sxs-lookup"><span data-stu-id="dc42c-135">View all cases that are listed on the Advanced eDiscovery page.</span></span>
  
  - <span data-ttu-id="dc42c-136">自分自身をケースのメンバーとして追加した後、組織のすべてのケースを管理します。</span><span class="sxs-lookup"><span data-stu-id="dc42c-136">Manage any case in the organization after they add themselves as a member of the case.</span></span>

  - <span data-ttu-id="dc42c-137">組織内のすべてのケースのケース データにアクセスしてエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="dc42c-137">Access and export case data for any case in the organization.</span></span>

  <span data-ttu-id="dc42c-138">アクセス範囲が広いため、電子情報開示管理者のサブグループのメンバーになっている管理者は少数です。</span><span class="sxs-lookup"><span data-stu-id="dc42c-138">Because of the broad scope of access, an organization should have only a few admins who are members of the eDiscovery Administrators subgroup.</span></span>

<span data-ttu-id="dc42c-139">電子情報開示のアクセス許可と、電子情報開示マネージャー役割グループに割り当てられている各役割の説明の詳細については、「Assign [eDiscovery permissions」を参照してください](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="dc42c-139">For more information about eDiscovery permissions and a description of each role that's assigned to the eDiscovery Manager role group, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a><span data-ttu-id="dc42c-140">手順 3: 高度な電子情報開示のグローバル設定を構成する</span><span class="sxs-lookup"><span data-stu-id="dc42c-140">Step 3: Configure global settings for Advanced eDiscovery</span></span>

<span data-ttu-id="dc42c-141">組織のユーザーがケースの作成と使用を開始する前に完了する最後の手順は、組織内のすべてのケースに適用されるグローバル設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="dc42c-141">The last step to complete before people in your organization start to create and use cases is to configure global settings that apply to all cases in your organization.</span></span> <span data-ttu-id="dc42c-142">現時点では、唯一のグローバル設定は *、弁護士とクライアントの* 特権の検出です (今後、より多くのグローバル設定が利用可能になります)。</span><span class="sxs-lookup"><span data-stu-id="dc42c-142">At this time, the only global setting is *attorney-client privilege detection* (more global settings will be available in the future).</span></span> <span data-ttu-id="dc42c-143">この設定を使用すると、レビュー セット内のデータを分析するときに、弁護士とクライアントの特権モデルを実行できます。</span><span class="sxs-lookup"><span data-stu-id="dc42c-143">This setting enables the attorney-client privilege model to run when you analyze data in a review set.</span></span> <span data-ttu-id="dc42c-144">モデルでは、機械学習を使用して、ドキュメントに実際に合法なコンテンツが含まれている可能性を判断します。</span><span class="sxs-lookup"><span data-stu-id="dc42c-144">The model uses machine learning to determine the likelihood that a document contains content that is legal in nature.</span></span> <span data-ttu-id="dc42c-145">また、ドキュメントの参加者と弁護士リスト (モデルのセットアップ時に提出する) を比較して、ドキュメントに弁護士である参加者が少なくとも 1 人いるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="dc42c-145">It also compares the participants of documents with an attorney list (that you submit when setting up the model) to determine if a document has at least one participant who is an attorney.</span></span>

<span data-ttu-id="dc42c-146">弁護士クライアント特権検出モデルのセットアップと使用の詳細については [、「Advanced eDiscovery](attorney-privilege-detection.md)での弁護士とクライアントの特権の検出のセットアップ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc42c-146">For more information about setting up and using the attorney-client privilege detection model, see [Set up attorney-client privilege detection in Advanced eDiscovery](attorney-privilege-detection.md).</span></span>

> [!NOTE]
> <span data-ttu-id="dc42c-147">これは、いつでも実行できるオプションの手順です。</span><span class="sxs-lookup"><span data-stu-id="dc42c-147">This is an optional step that you can perform anytime.</span></span> <span data-ttu-id="dc42c-148">弁護士クライアント特権検出モデルを実装しても、高度な電子情報開示ケースを作成して使用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="dc42c-148">Not implementing the attorney-client privilege detection model doesn't prevent you from creating and using Advanced eDiscovery cases.</span></span>

## <a name="next-steps"></a><span data-ttu-id="dc42c-149">次の手順</span><span class="sxs-lookup"><span data-stu-id="dc42c-149">Next steps</span></span>

<span data-ttu-id="dc42c-150">Advanced eDiscovery を設定した後、ケースを [作成する準備が整いました](create-and-manage-advanced-ediscoveryv2-case.md)。</span><span class="sxs-lookup"><span data-stu-id="dc42c-150">After you set up Advanced eDiscovery, you're ready to [create a case](create-and-manage-advanced-ediscoveryv2-case.md).</span></span>