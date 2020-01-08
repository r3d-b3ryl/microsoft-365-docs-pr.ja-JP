---
title: 高度な電子情報開示で、弁護士クライアント特権の検出を設定する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ROBOTS: NOINDEX, NOFOLLOW
description: 上級電子情報開示ケースのコンテンツを確認するときに、権限のあるコンテンツのマシン学習ベースの検出を使用するには、「弁護士クライアント特権検出モデル」を使用します。
ms.openlocfilehash: bf1b2112c47019c59f955ace21a25b099f91128f
ms.sourcegitcommit: af7950d9674f0eab3aee03f9afccff9ca2f4709a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40970865"
---
# <a name="set-up-attorney-client-privilege-detection-in-advanced-ediscovery"></a><span data-ttu-id="23dbd-103">高度な電子情報開示で、弁護士クライアント特権の検出を設定する</span><span class="sxs-lookup"><span data-stu-id="23dbd-103">Set up attorney-client privilege detection in Advanced eDiscovery</span></span>

<span data-ttu-id="23dbd-104">電子情報開示プロセスのレビューフェーズの主な重要な側面は、権限のあるコンテンツのドキュメントをレビューすることです。</span><span class="sxs-lookup"><span data-stu-id="23dbd-104">A major and costly aspect of the review phase of any eDiscovery process is reviewing documents for privileged content.</span></span> <span data-ttu-id="23dbd-105">Advanced eDiscovery は、このプロセスをより効率的にするために、権限のあるコンテンツの機械学習ベースの検出を行います。</span><span class="sxs-lookup"><span data-stu-id="23dbd-105">Advanced eDiscovery provides machine learning-based detection of privileged content to make this process more efficient.</span></span> <span data-ttu-id="23dbd-106">この機能は *、"委任状-クライアント特権の検出*" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="23dbd-106">This feature is called *attorney-client privilege detection*.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="23dbd-107">どのような仕組みなのか。</span><span class="sxs-lookup"><span data-stu-id="23dbd-107">How does it work?</span></span>

<span data-ttu-id="23dbd-108">委任状の特権の検出が有効になっている場合、レビューセット内のすべてのドキュメントは、レビューセット内のデータを[分析](analyzing-data-in-review-set.md)するときに、弁護士クライアント特権検出モデルによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="23dbd-108">When attorney-client privilege detection is enabled, all documents in a review set will be processed by the attorney-client privilege detection model when you [analyze the data](analyzing-data-in-review-set.md) in the review set.</span></span> <span data-ttu-id="23dbd-109">このモデルでは、次の2つのことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="23dbd-109">The model looks for two things:</span></span>

- <span data-ttu-id="23dbd-110">権限のあるコンテンツ–モデルでは、機械学習を使用して、ドキュメントに実際の法律上の内容が含まれている可能性を判断します。</span><span class="sxs-lookup"><span data-stu-id="23dbd-110">Privileged content – The model uses machine learning to determine the likelihood that the document contains content that is legal in nature.</span></span>

- <span data-ttu-id="23dbd-111">参加者–弁護士クライアント特権検出の設定の一環として、組織の弁護士の一覧を提出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23dbd-111">Participants – As part of setting up attorney-client privilege detection, you have to submit a list of attorneys for your organization.</span></span> <span data-ttu-id="23dbd-112">次に、ドキュメントの参加者と弁護士リストを比較して、ドキュメントに1人以上の弁護士参加者がいるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="23dbd-112">The model then compares the participants of the document with the attorney list to determine if a document has at least one attorney participant.</span></span>

<span data-ttu-id="23dbd-113">このモデルでは、すべてのドキュメントに対して次の3つのプロパティが生成されます。</span><span class="sxs-lookup"><span data-stu-id="23dbd-113">The model produces the following three properties for every document:</span></span>

- <span data-ttu-id="23dbd-114">**AttorneyClientPrivilegeScore** –ドキュメントが合法的である可能性。スコアの値は**0**から**1**です。</span><span class="sxs-lookup"><span data-stu-id="23dbd-114">**AttorneyClientPrivilegeScore** – The likelihood the document is legal in nature; the values for the score are between **0** and **1**.</span></span>

- <span data-ttu-id="23dbd-115">**Hasattorney** –ドキュメントの参加者のいずれかが弁護士リストに記載されている場合は、このプロパティを**true**に設定します。それ以外の場合、値は**false**になります。</span><span class="sxs-lookup"><span data-stu-id="23dbd-115">**HasAttorney** – This property is set to **true** if one of the document participants is listed in the attorney list; otherwise the value is **false**.</span></span> <span data-ttu-id="23dbd-116">組織が弁護士リストをアップロードしていない場合も、値は**false**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="23dbd-116">The value is also set to **false** if your organization didn't upload an attorney list.</span></span>

- <span data-ttu-id="23dbd-117">**IsPrivilege** – **AttorneyClientPrivilegeScore**の値がしきい値を超える場合、*または*ドキュメントに弁護士が参加している場合は、このプロパティを**true**に設定します。それ以外の場合、値は**false**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="23dbd-117">**IsPrivilege** – This property is set to **true** if the value for **AttorneyClientPrivilegeScore** is above the threshold *or* if the document has an attorney participant; otherwise the value is set to **false**.</span></span>

<span data-ttu-id="23dbd-118">次のスクリーンショットに示すように、これらのプロパティ (および対応する値) は、レビューセット内のドキュメントのファイルメタデータに追加されます。</span><span class="sxs-lookup"><span data-stu-id="23dbd-118">These properties (and their corresponding values) are added to the file metadata of the documents in a review set, as shown in the following screenshot:</span></span>

![ファイルメタデータに表示される、委任状のクライアント権限のプロパティ](media/AeDAttorneyClientPrivilegeMetadata.png)

<span data-ttu-id="23dbd-120">これら3つのプロパティは、レビューセット内でも検索できます。</span><span class="sxs-lookup"><span data-stu-id="23dbd-120">These three properties are also searchable within a review set.</span></span> <span data-ttu-id="23dbd-121">詳細については、「 [review set でデータを照会する](review-set-search.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23dbd-121">For more information, see [Query the data in a review set](review-set-search.md).</span></span>

## <a name="set-up-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="23dbd-122">弁護士クライアント特権検出モデルを設定する</span><span class="sxs-lookup"><span data-stu-id="23dbd-122">Set up the attorney-client privilege detection model</span></span>

<span data-ttu-id="23dbd-123">弁護士クライアントの特権検出モデルを有効にするには、組織でそれを有効にしてから、弁護士リストをアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="23dbd-123">To enable the attorney-client privilege detection model, your organization has to turn it on and then upload an attorney list.</span></span>

### <a name="step-1-turn-on-attorney-client-privilege-detection"></a><span data-ttu-id="23dbd-124">手順 1: 弁護士クライアント特権の検出を有効にする</span><span class="sxs-lookup"><span data-stu-id="23dbd-124">Step 1: Turn on attorney-client privilege detection</span></span>

<span data-ttu-id="23dbd-125">組織内の電子情報開示管理者 (電子情報開示マネージャーの役割グループの電子情報開示管理者サブグループのメンバー) であるユーザーは、高度な電子情報開示ケースでそのモデルを利用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="23dbd-125">A person who is an eDiscovery Administrator in your organization (a member of the eDiscovery Administrator subgroup in the eDiscovery Manager role group) must make the model available in your Advanced eDiscovery cases.</span></span>

1. <span data-ttu-id="23dbd-126">セキュリティ & コンプライアンスセンターで、[**電子情報開示 > Advanced ediscovery**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="23dbd-126">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery**.</span></span>

2. <span data-ttu-id="23dbd-127">[**高度な電子情報開示**ホーム] ページの [**設定**] タイルで、[**実験的な実験機能を構成する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="23dbd-127">On the **Advanced eDiscovery** home page, in the **Settings** tile, select **Configure experimental features**.</span></span>

   ![[実験的な機能の構成] を選択します。](media/AeDExperimentalFeatures.png)

3. <span data-ttu-id="23dbd-129">[**実験的な機能**] タブで、[**委任状の管理-クライアント特権の設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="23dbd-129">On the **Experimental features** tab, select **Manage attorney-client privilege setting**.</span></span>

4. <span data-ttu-id="23dbd-130">[**委任状-クライアント特権**のポップアップ] ページで、切り替えを使用して機能を有効にし、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="23dbd-130">On the **Attorney-client privilege** flyout page, use the toggle to turn on the feature and then select **Save**.</span></span>

### <a name="step-2-upload-a-list-of-attorneys-optional"></a><span data-ttu-id="23dbd-131">手順 2: 弁護士の一覧をアップロードする (オプション)</span><span class="sxs-lookup"><span data-stu-id="23dbd-131">Step 2: Upload a list of attorneys (optional)</span></span>

<span data-ttu-id="23dbd-132">事前に説明されている弁護士と法務担当者のための電子メールアドレスの一覧をアップロードすることをお勧めします。これまでに説明し**た、弁護士**および**権限**のあるユーザー権限検出モデルを十分に活用するには、組織で働いている弁護士および法務担当者の電子メールアドレスの一覧をアップロードすることをお勧めします</span><span class="sxs-lookup"><span data-stu-id="23dbd-132">To take full advantage of the attorney-client privilege detection model and use the results of the **Has Attorney** or **Potentially Privileged** detection that was previously described, we recommend that you upload a list of email addresses for the lawyers and legal personnel who work for your organization.</span></span> 

<span data-ttu-id="23dbd-133">弁護士側の特権検出モデルで使用する弁護士リストをアップロードするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="23dbd-133">To upload an attorney list for use by the attorney-client privilege detection model:</span></span>

1. <span data-ttu-id="23dbd-134">.Csv ファイル (ヘッダー行なし) を作成し、適切な各ユーザーの電子メールアドレスを別の行に追加します。</span><span class="sxs-lookup"><span data-stu-id="23dbd-134">Create a .csv file (without a header row) and add the email address for each appropriate person on a separate line.</span></span> <span data-ttu-id="23dbd-135">このファイルをローカルコンピューターに保存します。</span><span class="sxs-lookup"><span data-stu-id="23dbd-135">Save this file to your local computer.</span></span>

2. <span data-ttu-id="23dbd-136">[**高度な電子情報開示**ホーム] ページの [**設定**] タイルで、[**実験的な実験機能を構成する**] を選択してから、[**弁護士-クライアント特権設定の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="23dbd-136">On the **Advanced eDiscovery** home page, in the **Settings** tile, select **Configure experimental features**, and then select **Manage attorney-client privilege setting**.</span></span>

   <span data-ttu-id="23dbd-137">[**委任状-クライアント権限**] ページが表示され、**弁護士クライアント特権検出**トグルがオンになっています。</span><span class="sxs-lookup"><span data-stu-id="23dbd-137">The **Attorney-client privilege** page is displayed, and the **Attorney-client privilege detection** toggle is turned on.</span></span>

   ![委任状-クライアント特権のポップアップページ](media/AeDUploadAttorneyList.png)

3. <span data-ttu-id="23dbd-139">[**参照**] を選択し、手順1で作成した .csv ファイルを見つけて選択します。</span><span class="sxs-lookup"><span data-stu-id="23dbd-139">Select **Browse** and then find and select the .csv file that you created in step 1.</span></span>

4. <span data-ttu-id="23dbd-140">[**保存**] を選択して、弁護士リストをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="23dbd-140">Select **Save** to upload the attorney list.</span></span>

## <a name="use-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="23dbd-141">弁護士クライアント特権検出モデルを使用する</span><span class="sxs-lookup"><span data-stu-id="23dbd-141">Use the attorney-client privilege detection model</span></span>

<span data-ttu-id="23dbd-142">このセクションの手順に従って、レビューセットのドキュメントに対して、弁護士クライアント特権検出を使用します。</span><span class="sxs-lookup"><span data-stu-id="23dbd-142">Follow the steps in this section to use attorney-client privilege detection for documents in a review set.</span></span>

### <a name="step-1-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a><span data-ttu-id="23dbd-143">手順 1: 弁護士クライアント特権検出モデルを使用してスマートタググループを作成する</span><span class="sxs-lookup"><span data-stu-id="23dbd-143">Step 1: Create a smart tag group with attorney-client privilege detection model</span></span>

<span data-ttu-id="23dbd-144">レビュープロセスにおいて、弁護士クライアント特権の検出結果を確認する主な方法の1つは、スマートタググループを使用することです。</span><span class="sxs-lookup"><span data-stu-id="23dbd-144">One of the primary ways to see the results of attorney-client privilege detection in your review process is by using a smart tag group.</span></span> <span data-ttu-id="23dbd-145">スマートタググループは、弁護士クライアント特権検出の結果を示し、スマートタググループ内のタグの横に、結果をインラインで表示します。</span><span class="sxs-lookup"><span data-stu-id="23dbd-145">A smart tag group indicates the results of the attorney-client privilege detection and shows the results in-line next to the tags in a smart tag group.</span></span> <span data-ttu-id="23dbd-146">これにより、ドキュメントのレビュー中に潜在的な権限のあるドキュメントをすばやく識別できます。</span><span class="sxs-lookup"><span data-stu-id="23dbd-146">This lets you quickly identify potentially privileged documents during document review.</span></span> <span data-ttu-id="23dbd-147">また、スマートタググループ内のタグを使用して、特権または特権のないドキュメントにタグを付けることもできます。</span><span class="sxs-lookup"><span data-stu-id="23dbd-147">Additionally, you can also use the tags in the smart tag group to tag documents as privileged or non-privileged.</span></span> <span data-ttu-id="23dbd-148">スマートタグの詳細については、「 [Advanced eDiscovery でスマートタグを設定](smart-tags.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23dbd-148">For more information about smart tags, see [Set up smart tags in Advanced eDiscovery](smart-tags.md).</span></span>

1. <span data-ttu-id="23dbd-149">手順1で分析したドキュメントを含むレビューセットで、[**レビューセットの管理**] を選択し、[**タグの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="23dbd-149">In the review set that contains the documents that you analyzed in Step 1, select **Manage review set** and then select **Manage tags**.</span></span>
 
2. <span data-ttu-id="23dbd-150">[**タグ**] で、[**グループの追加**] の横にあるプルダウンを選択し、[**スマートタググループの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="23dbd-150">Under **Tags**, select the pull-down next to **Add group** and then select **Add smart tag group**.</span></span>

   ![[スマートタググループの追加] を選択します。](media/AeDCreateSmartTag.png)

3. <span data-ttu-id="23dbd-152">[**スマートタグのモデルを選択**します] ページで、[**弁護士-クライアント権限**] の横にある **[選択]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="23dbd-152">On the **Choose a model for your smart tag** page, choose **Select** next to **Attorney-client privilege**.</span></span>

   <span data-ttu-id="23dbd-153">"**弁護士-クライアント" 特権**という名前のタググループが表示されます。</span><span class="sxs-lookup"><span data-stu-id="23dbd-153">A tag group named **Attorney-client privilege** is displayed.</span></span> <span data-ttu-id="23dbd-154">これには、モデルによって生成される結果に対応する、**正**と**負**の2つの子タグがあります。</span><span class="sxs-lookup"><span data-stu-id="23dbd-154">It contains two child tags named **Positive** and **Negative**, which correspond to the possible results produced by the model.</span></span>

   ![弁護士-クライアント特権スマートタググループ](media/AeDAttorneyClientSmartTagGroup.png)

3. <span data-ttu-id="23dbd-156">確認には、必要に応じて、タググループとタグの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="23dbd-156">Rename the tag group and tags as appropriate for your review.</span></span> <span data-ttu-id="23dbd-157">たとえば、**正**の値を**Privileged**に、**負の値**を**特権を持たない**名前に変更できます。</span><span class="sxs-lookup"><span data-stu-id="23dbd-157">For example, you can rename **Positive** to **Privileged** and **Negative** to **Not privileged**.</span></span>

### <a name="step-2-analyze-a-review-set"></a><span data-ttu-id="23dbd-158">手順 2: レビューセットを分析する</span><span class="sxs-lookup"><span data-stu-id="23dbd-158">Step 2: Analyze a review set</span></span>

<span data-ttu-id="23dbd-159">レビューセット内のドキュメントを分析する場合は、弁護士クライアント特権検出モデルも実行され、対応するプロパティ (「[操作方法](#how-does-it-work)」で説明されています) がレビューセットのすべてのドキュメントに追加されます。</span><span class="sxs-lookup"><span data-stu-id="23dbd-159">When you analyze the documents in a review set, the attorney-client privilege detection model will also run and the corresponding properties (described in [How does it work?](#how-does-it-work) will be added to every document in the review set.</span></span> <span data-ttu-id="23dbd-160">レビューセットでのデータの分析の詳細については、「 [Advanced eDiscovery でデータを分析セットに分析する](analyzing-data-in-review-set.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23dbd-160">For more information about analyzing data in review set, see [Analyze data in a review set in Advanced eDiscovery](analyzing-data-in-review-set.md).</span></span>

### <a name="step-3-use-the-smart-tag-group-for-review-of-privileged-content"></a><span data-ttu-id="23dbd-161">手順 3: スマートタググループを使用して権限のあるコンテンツを確認する</span><span class="sxs-lookup"><span data-stu-id="23dbd-161">Step 3: Use the smart tag group for review of privileged content</span></span>

<span data-ttu-id="23dbd-162">レビューセットを分析し、スマートタグを設定したら、次の手順でドキュメントをレビューします。</span><span class="sxs-lookup"><span data-stu-id="23dbd-162">After analyzing the review set and setting up smart tags, the next step is to review the documents.</span></span> <span data-ttu-id="23dbd-163">モデルでドキュメントが潜在的な特権を持っていると判断された場合、**タグ付けパネル**内の対応するスマートタグは、弁護士クライアント特権検出によって生成される次の結果を示します。</span><span class="sxs-lookup"><span data-stu-id="23dbd-163">If the model has determined the document is potentially privileged, the corresponding smart tag in the **Tagging panel** will indicate the following results produced by the attorney-client privilege detection:</span></span>

- <span data-ttu-id="23dbd-164">ドキュメントに有効なコンテンツが含まれている場合は、対応するスマートタグ (この例では既定の**肯定**タグ) の横にラベル**リーガルコンテンツ**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="23dbd-164">If the document has content that may be legal in nature, the label **Legal content** is displayed next to the corresponding smart tag (which in this case is the default **Positive** tag).</span></span>

- <span data-ttu-id="23dbd-165">組織の委任状リストに含まれている参加者がドキュメントにある場合、対応するスマートタグ (この場合は、既定の**正数**タグ) の横にラベル**弁護士**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="23dbd-165">If the document has a participant who is found in your organization's attorney list, the label **Attorney** is displayed next to the corresponding smart tag (which in this case is also the default **Positive** tag).</span></span>

- <span data-ttu-id="23dbd-166">ドキュメントのコンテンツが実際には法律上、弁護士リストに含まれ*て*いる可能性があるコンテンツがある場合、**法的コンテンツ**と**弁護士**の両方のラベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="23dbd-166">If the document has content that may be legal in nature *and* has a participant found in the attorney list, both the **Legal content**  and **Attorney** labels are displayed.</span></span> 

<span data-ttu-id="23dbd-167">ドキュメントに法律上の正当なコンテンツが含まれていないか、または弁護士リストからの参加者が含まれていないことがモデルによって判断された場合は、タグ付けパネルにラベルは表示されません。</span><span class="sxs-lookup"><span data-stu-id="23dbd-167">If the model determines that a document doesn't contain content that is legal in nature or doesn't contain a participant from the attorney list, then neither label is displayed in the tagging panel.</span></span>

<span data-ttu-id="23dbd-168">たとえば、次のスクリーンショットは2つのドキュメントを示しています。</span><span class="sxs-lookup"><span data-stu-id="23dbd-168">For example, the following screenshots show two documents.</span></span> <span data-ttu-id="23dbd-169">最初のものには、実際には法律上、法律の一覧に含まれている参加者が存在するコンテンツが含まれています。</span><span class="sxs-lookup"><span data-stu-id="23dbd-169">The first one contains content that is legal in nature and has a participant found in the list of attorneys.</span></span> <span data-ttu-id="23dbd-170">2番目には、ラベルは表示されません。</span><span class="sxs-lookup"><span data-stu-id="23dbd-170">The second contains neither and therefore doesn't display any labels.</span></span>

![弁護士および法的コンテンツラベルを含むドキュメント](media/AeDTaggingPanelLegalContentAttorney.png)

![ラベルなしのドキュメント](media/AeDTaggingPanelNegative.png)

<span data-ttu-id="23dbd-173">ドキュメントに権限のあるコンテンツが含まれているかどうかを確認したら、適切なタグでドキュメントにタグを付けます。</span><span class="sxs-lookup"><span data-stu-id="23dbd-173">After you review a document to see if it contains privileged content, you can tag the document with the appropriate tag.</span></span>
