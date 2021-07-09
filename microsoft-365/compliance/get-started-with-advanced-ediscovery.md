---
title: '[Advanced eDiscovery] でMicrosoft 365'
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
description: この記事では、ケースの作成と管理を開始Advanced eDiscoveryを設定する方法について説明します。 また、必要な Microsoft サブスクリプションとライセンスも説明します。 いくつかの簡単な手順を完了すると、Advanced eDiscoveryツールを使用する準備が整いました。
ms.openlocfilehash: be5e5aea03950d28889590004bd796455a71c5be
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341450"
---
# <a name="set-up-microsoft-365-advanced-ediscovery"></a><span data-ttu-id="02bfd-105">設定Microsoft 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="02bfd-105">Set up Microsoft 365 Advanced eDiscovery</span></span>

<span data-ttu-id="02bfd-106">Advanced eDiscovery Microsoft 365では、組織の内部および外部調査に対応するデータを保存、収集、レビュー、分析、およびエクスポートするためのエンドツーエンドのワークフローを提供します。</span><span class="sxs-lookup"><span data-stu-id="02bfd-106">Advanced eDiscovery in Microsoft 365 provides an end-to-end workflow to preserve, collect, review, analyze, and export data that's responsive to your organization's internal and external investigations.</span></span> <span data-ttu-id="02bfd-107">Advanced eDiscovery を展開するために必要なタスクは何もありませんが、組織が Advanced eDiscovery ケースの作成と使用を開始して調査を管理するには、IT 管理者と電子情報開示マネージャーが完了する必要があるいくつかの前提条件タスクがあります。</span><span class="sxs-lookup"><span data-stu-id="02bfd-107">Nothing is needed to deploy Advanced eDiscovery, but there are some prerequisite tasks that an IT admin and eDiscovery manager have to complete before your organization can start to create and use Advanced eDiscovery cases to manage your investigations.</span></span>

<span data-ttu-id="02bfd-108">この記事では、セットアップに必要な以下の手順について説明Advanced eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="02bfd-108">This article discusses the following steps necessary to set up Advanced eDiscovery.</span></span>

![ユーザー設定のAdvanced eDiscovery](../media/set-up-advanced-ediscovery.png)

<span data-ttu-id="02bfd-110">これには、Advanced eDiscovery にアクセスしてケースにカストディアンを追加するために必要な適切なライセンスを確保し、ケースにアクセスして管理するための権限を法務および調査チームに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="02bfd-110">This includes ensuring the proper licensing required to access Advanced eDiscovery and add custodians to cases, and assigning permissions to your legal and investigation team so they can access and manage cases.</span></span>

## <a name="step-1-verify-and-assign-appropriate-licenses"></a><span data-ttu-id="02bfd-111">手順 1: 適切なライセンスを確認して割り当てる</span><span class="sxs-lookup"><span data-stu-id="02bfd-111">Step 1: Verify and assign appropriate licenses</span></span>

<span data-ttu-id="02bfd-112">ユーザーのライセンスAdvanced eDiscovery適切な組織のサブスクリプションとユーザーごとのライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="02bfd-112">Licensing for Advanced eDiscovery requires the appropriate organization subscription and per-user licensing.</span></span> <span data-ttu-id="02bfd-113">ライセンス要件の一覧については、「サブスクリプションAdvanced eDiscoveryライセンス」[を参照してください](overview-ediscovery-20.md#subscriptions-and-licensing)。</span><span class="sxs-lookup"><span data-stu-id="02bfd-113">For a list of licensing requirements for Advanced eDiscovery, see [Subscriptions and licensing](overview-ediscovery-20.md#subscriptions-and-licensing).</span></span>

## <a name="step-2-assign-ediscovery-permissions"></a><span data-ttu-id="02bfd-114">手順 2: 電子情報開示のアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="02bfd-114">Step 2: Assign eDiscovery permissions</span></span>

<span data-ttu-id="02bfd-115">ケースのAdvanced eDiscoveryメンバーとしてアクセスまたは追加するにはAdvanced eDiscovery適切なアクセス許可をユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="02bfd-115">To access Advanced eDiscovery or added as a member of an Advanced eDiscovery case, a user must be assigned the appropriate permissions.</span></span> <span data-ttu-id="02bfd-116">具体的には、ユーザーをセキュリティ コンプライアンス センターの電子情報開示マネージャー役割グループのメンバー&する必要があります。</span><span class="sxs-lookup"><span data-stu-id="02bfd-116">Specifically, a user must be added as a member of the eDiscovery Manager role group in the Security & Compliance Center.</span></span> <span data-ttu-id="02bfd-117">この役割グループのメンバーは、すべてのケースを作成Advanced eDiscovery管理できます。</span><span class="sxs-lookup"><span data-stu-id="02bfd-117">Members of this role group can create and manage Advanced eDiscovery cases.</span></span> <span data-ttu-id="02bfd-118">メンバーの追加と削除、保管担当者とコンテンツの場所の保留、法的保留通知の管理、ケースに関連付けられた検索の作成と編集、レビュー セットへの検索結果の追加、レビュー セット内のデータの分析、Advanced eDiscovery ケースからのエクスポートとダウンロードを行います。</span><span class="sxs-lookup"><span data-stu-id="02bfd-118">They can add and remove members, place custodians and content locations on hold, manage legal hold notifications, create and edit searches associated in a case, add search results to a review set, analyze data in a review set, and export and download from an Advanced eDiscovery case.</span></span>

<span data-ttu-id="02bfd-119">電子情報開示マネージャーの役割グループにユーザーを追加するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="02bfd-119">Complete the following steps to add users to the eDiscovery Manager role group:</span></span>

1. <span data-ttu-id="02bfd-120">組織の <https://compliance.microsoft.com/permissions> 管理者アカウントの資格情報を使用して、アクセスしてサインインMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="02bfd-120">Go to <https://compliance.microsoft.com/permissions> and sign in using the credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="02bfd-121">[アクセス許可 **] ページで** 、電子情報開示マネージャー **の役割グループを** 選択します。</span><span class="sxs-lookup"><span data-stu-id="02bfd-121">On the **Permissions** page, select the **eDiscovery Manager** role group.</span></span>

3. <span data-ttu-id="02bfd-122">[電子情報開示マネージャー] フライアウト ページで、[電子情報開示マネージャー] セクション **の横** にある [ **編集] をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="02bfd-122">On the eDiscovery Manager flyout page, click **Edit** next to the **eDiscovery Manager** section.</span></span>

4. <span data-ttu-id="02bfd-123">役割グループ **の編集ウィザードの [電子情報開示マネージャー** の選択] ページで、[電子情報開示マネージャーの選択] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="02bfd-123">On the **Choose eDiscovery Manager** page in the edit role group wizard, click **Choose eDiscovery Manager**.</span></span>

5. <span data-ttu-id="02bfd-124">[ **追加]** をクリックし、役割グループに追加するすべてのユーザーのチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="02bfd-124">Click **Add** then select the checkbox for all users you want to add to the role group.</span></span>

6. <span data-ttu-id="02bfd-125">[追加 **] を** クリックして選択したユーザーを追加し、[完了] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="02bfd-125">Click **Add** to add the selected users, and then click **Done**.</span></span>

7. <span data-ttu-id="02bfd-126">[ **保存]** をクリックしてユーザーを役割グループに追加し、[閉じる] をクリック **して** 手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="02bfd-126">Click **Save** to add the users to the role group, and then click **Close** to complete the step.</span></span>

### <a name="more-information-about-the-ediscovery-manager-role-group"></a><span data-ttu-id="02bfd-127">電子情報開示マネージャー役割グループの詳細</span><span class="sxs-lookup"><span data-stu-id="02bfd-127">More information about the eDiscovery Manager role group</span></span>

<span data-ttu-id="02bfd-128">電子情報開示マネージャーの役割グループには、2 つのサブグループがあります。</span><span class="sxs-lookup"><span data-stu-id="02bfd-128">There are two subgroups in the eDiscovery Manager role group.</span></span> <span data-ttu-id="02bfd-129">これらのサブグループの違いは、スコープに基づきます。</span><span class="sxs-lookup"><span data-stu-id="02bfd-129">The difference between these subgroups is based on scope.</span></span>

- <span data-ttu-id="02bfd-130">**電子情報開示マネージャー**: ユーザーが作成またはメンバー Advanced eDiscoveryケースを表示および管理できます。</span><span class="sxs-lookup"><span data-stu-id="02bfd-130">**eDiscovery Manager**: Can view and manage the Advanced eDiscovery cases they create or are a member of.</span></span> <span data-ttu-id="02bfd-131">別の電子情報開示マネージャーがケースを作成しても、そのケースのメンバーとして 2 番目の電子情報開示マネージャーを追加しない場合、2 番目の電子情報開示マネージャーはコンプライアンス センターの Advanced eDiscovery ページでケースを表示または開くことができません。</span><span class="sxs-lookup"><span data-stu-id="02bfd-131">If another eDiscovery Manager creates a case but doesn't add a second eDiscovery Manager as a member of that case, the second eDiscovery Manager won't be able to view or open the case on the Advanced eDiscovery page in the compliance center.</span></span> <span data-ttu-id="02bfd-132">一般に、組織内のほとんどのユーザーは、電子情報開示マネージャー サブグループに追加できます。</span><span class="sxs-lookup"><span data-stu-id="02bfd-132">In general, most people in your organization can be added to the eDiscovery Manager subgroup.</span></span>

- <span data-ttu-id="02bfd-133">**電子情報開示管理者**: 電子情報開示マネージャーが実行できるすべてのケース管理タスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="02bfd-133">**eDiscovery Administrator**: Can perform all case management tasks that an eDiscovery Manager can do.</span></span> <span data-ttu-id="02bfd-134">さらに、電子情報開示管理者は、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="02bfd-134">Additionally, an eDiscovery Administrator can:</span></span>

  - <span data-ttu-id="02bfd-135">[Advanced eDiscovery] ページにリストされたすべてのケースを表示します。</span><span class="sxs-lookup"><span data-stu-id="02bfd-135">View all cases that are listed on the Advanced eDiscovery page.</span></span>
  
  - <span data-ttu-id="02bfd-136">自分自身をケースのメンバーとして追加した後、組織のすべてのケースを管理します。</span><span class="sxs-lookup"><span data-stu-id="02bfd-136">Manage any case in the organization after they add themselves as a member of the case.</span></span>

  - <span data-ttu-id="02bfd-137">組織内のすべてのケースのケース データにアクセスしてエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="02bfd-137">Access and export case data for any case in the organization.</span></span>

  <span data-ttu-id="02bfd-138">アクセス範囲が広いため、電子情報開示管理者のサブグループのメンバーになっている管理者は少数です。</span><span class="sxs-lookup"><span data-stu-id="02bfd-138">Because of the broad scope of access, an organization should have only a few admins who are members of the eDiscovery Administrators subgroup.</span></span>

<span data-ttu-id="02bfd-139">電子情報開示のアクセス許可と、電子情報開示マネージャー役割グループに割り当てられている各役割の説明の詳細については、「Assign [eDiscovery permissions」を参照してください](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="02bfd-139">For more information about eDiscovery permissions and a description of each role that's assigned to the eDiscovery Manager role group, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a><span data-ttu-id="02bfd-140">手順 3: サーバーのグローバル設定を構成Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="02bfd-140">Step 3: Configure global settings for Advanced eDiscovery</span></span>

<span data-ttu-id="02bfd-141">組織のユーザーがケースの作成と使用を開始する前に完了する最後の手順は、組織内のすべてのケースに適用されるグローバル設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="02bfd-141">The last step to complete before people in your organization start to create and use cases is to configure global settings that apply to all cases in your organization.</span></span> <span data-ttu-id="02bfd-142">現時点では、唯一のグローバル設定は *、弁護士とクライアントの* 特権の検出です (今後、より多くのグローバル設定が利用可能になります)。</span><span class="sxs-lookup"><span data-stu-id="02bfd-142">At this time, the only global setting is *attorney-client privilege detection* (more global settings will be available in the future).</span></span> <span data-ttu-id="02bfd-143">この設定を使用すると、レビュー セット内のデータを分析するときに、弁護士とクライアントの特権モデルを実行できます。</span><span class="sxs-lookup"><span data-stu-id="02bfd-143">This setting enables the attorney-client privilege model to run when you analyze data in a review set.</span></span> <span data-ttu-id="02bfd-144">モデルでは、機械学習を使用して、ドキュメントに実際に合法なコンテンツが含まれている可能性を判断します。</span><span class="sxs-lookup"><span data-stu-id="02bfd-144">The model uses machine learning to determine the likelihood that a document contains content that is legal in nature.</span></span> <span data-ttu-id="02bfd-145">また、ドキュメントの参加者と弁護士リスト (モデルのセットアップ時に提出する) を比較して、ドキュメントに弁護士である参加者が少なくとも 1 人いるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="02bfd-145">It also compares the participants of documents with an attorney list (that you submit when setting up the model) to determine if a document has at least one participant who is an attorney.</span></span>

<span data-ttu-id="02bfd-146">弁護士クライアント特権検出モデルのセットアップと使用の詳細については、「管理者向けアプリケーションでの弁護士とクライアントの特権の検出のセットアップ」[を参照Advanced eDiscovery。](attorney-privilege-detection.md)</span><span class="sxs-lookup"><span data-stu-id="02bfd-146">For more information about setting up and using the attorney-client privilege detection model, see [Set up attorney-client privilege detection in Advanced eDiscovery](attorney-privilege-detection.md).</span></span>

> [!NOTE]
> <span data-ttu-id="02bfd-147">これは、いつでも実行できるオプションの手順です。</span><span class="sxs-lookup"><span data-stu-id="02bfd-147">This is an optional step that you can perform anytime.</span></span> <span data-ttu-id="02bfd-148">弁護士クライアント特権検出モデルを実装しない場合でも、ユーザーが特定のケースを作成して使用Advanced eDiscoveryではありません。</span><span class="sxs-lookup"><span data-stu-id="02bfd-148">Not implementing the attorney-client privilege detection model doesn't prevent you from creating and using Advanced eDiscovery cases.</span></span>

## <a name="next-steps"></a><span data-ttu-id="02bfd-149">次の手順</span><span class="sxs-lookup"><span data-stu-id="02bfd-149">Next steps</span></span>

<span data-ttu-id="02bfd-150">ファイルを設定Advanced eDiscovery、ケースを[作成する準備ができました](create-and-manage-advanced-ediscoveryv2-case.md)。</span><span class="sxs-lookup"><span data-stu-id="02bfd-150">After you set up Advanced eDiscovery, you're ready to [create a case](create-and-manage-advanced-ediscoveryv2-case.md).</span></span>