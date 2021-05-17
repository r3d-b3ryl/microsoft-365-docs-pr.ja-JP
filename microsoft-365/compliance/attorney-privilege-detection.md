---
title: アプリケーションで弁護士とクライアントの特権の検出をAdvanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 弁護士クライアントの特権検出モデルを使用して、機械学習ベースの特権コンテンツの検出を使用して、ユーザーのケースでコンテンツをAdvanced eDiscoveryします。
ms.openlocfilehash: 73a0efeece7bc331045e9bbe1a1da56f9fd24700
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358043"
---
# <a name="set-up-attorney-client-privilege-detection-in-advanced-ediscovery"></a><span data-ttu-id="59ac9-103">アプリケーションで弁護士とクライアントの特権の検出をAdvanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="59ac9-103">Set up attorney-client privilege detection in Advanced eDiscovery</span></span>

<span data-ttu-id="59ac9-104">電子情報開示プロセスのレビュー フェーズの主要でコストの高い側面は、特権コンテンツのドキュメントを確認する方法です。</span><span class="sxs-lookup"><span data-stu-id="59ac9-104">A major and costly aspect of the review phase of any eDiscovery process is reviewing documents for privileged content.</span></span> <span data-ttu-id="59ac9-105">Advanced eDiscovery、このプロセスをより効率的にするための、機械学習ベースの特権コンテンツの検出を提供します。</span><span class="sxs-lookup"><span data-stu-id="59ac9-105">Advanced eDiscovery provides machine learning-based detection of privileged content to make this process more efficient.</span></span> <span data-ttu-id="59ac9-106">この機能は、弁護士 *とクライアントの特権の検出と呼ばれる。*</span><span class="sxs-lookup"><span data-stu-id="59ac9-106">This feature is called *attorney-client privilege detection*.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="59ac9-107">どのような仕組みなのか。</span><span class="sxs-lookup"><span data-stu-id="59ac9-107">How does it work?</span></span>

<span data-ttu-id="59ac9-108">弁護士クライアント特権の検出が有効になっている場合、レビュー セット内のデータを分析すると、レビュー セット内のすべてのドキュメントが弁護士クライアント特権[](analyzing-data-in-review-set.md)検出モデルによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="59ac9-108">When attorney-client privilege detection is enabled, all documents in a review set will be processed by the attorney-client privilege detection model when you [analyze the data](analyzing-data-in-review-set.md) in the review set.</span></span> <span data-ttu-id="59ac9-109">モデルは、次の 2 つのことを探します。</span><span class="sxs-lookup"><span data-stu-id="59ac9-109">The model looks for two things:</span></span>

- <span data-ttu-id="59ac9-110">特権コンテンツ – モデルは機械学習を使用して、ドキュメントに実際に合法なコンテンツが含まれている可能性を判断します。</span><span class="sxs-lookup"><span data-stu-id="59ac9-110">Privileged content – The model uses machine learning to determine the likelihood that the document contains content that is legal in nature.</span></span>

- <span data-ttu-id="59ac9-111">参加者 – 弁護士クライアント特権の検出を設定する一環として、組織の弁護士の一覧を提出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59ac9-111">Participants – As part of setting up attorney-client privilege detection, you have to submit a list of attorneys for your organization.</span></span> <span data-ttu-id="59ac9-112">これを行うと、検出モデルはドキュメントの参加者と弁護士のリストを比較し、ドキュメントに 1 人以上の弁護士の参加者がいるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="59ac9-112">The model then compares the participants of the document with the attorney list to determine if a document has at least one attorney participant.</span></span>

<span data-ttu-id="59ac9-113">モデルは、ドキュメントごとに次の 3 つのプロパティを生成します。</span><span class="sxs-lookup"><span data-stu-id="59ac9-113">The model produces the following three properties for every document:</span></span>

- <span data-ttu-id="59ac9-114">**AttorneyClientPrivilegeScore:** ドキュメントが自然に合法である可能性。スコアの値は **0** ~ **1 です**。</span><span class="sxs-lookup"><span data-stu-id="59ac9-114">**AttorneyClientPrivilegeScore:** The likelihood the document is legal in nature; the values for the score are between **0** and **1**.</span></span>

- <span data-ttu-id="59ac9-115">**HasAttorney:** このプロパティは、ドキュメント **参加者の** 1 つが弁護士リストに表示されている場合は true に設定されます。それ以外の場合、値は **false です**。</span><span class="sxs-lookup"><span data-stu-id="59ac9-115">**HasAttorney:** This property is set to **true** if one of the document participants is listed in the attorney list; otherwise the value is **false**.</span></span> <span data-ttu-id="59ac9-116">組織が弁護士リストをアップロードしていない場合も、値は **false** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="59ac9-116">The value is also set to **false** if your organization didn't upload an attorney list.</span></span>

- <span data-ttu-id="59ac9-117">**IsPrivilege:\*\*\*\*AttorneyClientPrivilegeScore** の値がしきい値を超える場合、またはドキュメントに弁護士参加者が含まれる場合、このプロパティは true に設定されます。 それ以外の場合、値は false に **設定されます**。</span><span class="sxs-lookup"><span data-stu-id="59ac9-117">**IsPrivilege:** This property is set to **true** if the value for **AttorneyClientPrivilegeScore** is above the threshold *or* if the document has an attorney participant; otherwise the value is set to **false**.</span></span>

<span data-ttu-id="59ac9-118">これらのプロパティ (および対応する値) は、次のスクリーンショットに示すように、レビュー セット内のドキュメントのファイル メタデータに追加されます。</span><span class="sxs-lookup"><span data-stu-id="59ac9-118">These properties (and their corresponding values) are added to the file metadata of the documents in a review set, as shown in the following screenshot:</span></span>

![ファイル メタデータに表示される弁護士とクライアントの特権プロパティ](../media/AeDAttorneyClientPrivilegeMetadata.png)

<span data-ttu-id="59ac9-120">これら 3 つのプロパティは、レビュー セット内でも検索できます。</span><span class="sxs-lookup"><span data-stu-id="59ac9-120">These three properties are also searchable within a review set.</span></span> <span data-ttu-id="59ac9-121">詳細については、「レビュー セット [のデータをクエリする」を参照してください](review-set-search.md)。</span><span class="sxs-lookup"><span data-stu-id="59ac9-121">For more information, see [Query the data in a review set](review-set-search.md).</span></span>

## <a name="set-up-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="59ac9-122">弁護士クライアント特権検出モデルのセットアップ</span><span class="sxs-lookup"><span data-stu-id="59ac9-122">Set up the attorney-client privilege detection model</span></span>

<span data-ttu-id="59ac9-123">弁護士クライアント特権検出モデルを有効にするには、組織で有効にして、弁護士リストをアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="59ac9-123">To enable the attorney-client privilege detection model, your organization has to turn it on and then upload an attorney list.</span></span>

### <a name="step-1-turn-on-attorney-client-privilege-detection"></a><span data-ttu-id="59ac9-124">手順 1: 弁護士とクライアントの特権の検出を有効にする</span><span class="sxs-lookup"><span data-stu-id="59ac9-124">Step 1: Turn on attorney-client privilege detection</span></span>

<span data-ttu-id="59ac9-125">組織内の電子情報開示管理者であるユーザー (電子情報開示マネージャー役割グループの電子情報開示管理者サブグループのメンバー) は、Advanced eDiscovery ケースでモデルを使用できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="59ac9-125">A person who is an eDiscovery Administrator in your organization (a member of the eDiscovery Administrator subgroup in the eDiscovery Manager role group) must make the model available in your Advanced eDiscovery cases.</span></span>

1. <span data-ttu-id="59ac9-126">セキュリティ コンプライアンス センター&、電子情報開示のページ **に** 移動> Advanced eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="59ac9-126">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery**.</span></span>

2. <span data-ttu-id="59ac9-127">[ホーム **Advanced eDiscovery]** タイルで、[グローバル分析 **設定** 構成 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="59ac9-127">On the **Advanced eDiscovery** home page, in the **Settings** tile, click **Configure global analytics settings**.</span></span>

   ![[実験的な機能の構成] を選択します。](../media/AeDExperimentalFeatures.png)

3. <span data-ttu-id="59ac9-129">[分析の **設定] タブで** 、[弁護士とクライアント **の特権設定の管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="59ac9-129">On the **Analytics settings** tab, select **Manage attorney-client privilege setting**.</span></span>

4. <span data-ttu-id="59ac9-130">**[弁護士/依頼人特権]** ポップアップ ページで、トグルを使用して機能をオンにし、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="59ac9-130">On the **Attorney-client privilege** flyout page, use the toggle to turn on the feature and then select **Save**.</span></span>

### <a name="step-2-upload-a-list-of-attorneys-optional"></a><span data-ttu-id="59ac9-131">手順 2: アップロードリストを作成する (オプション)</span><span class="sxs-lookup"><span data-stu-id="59ac9-131">Step 2: Upload a list of attorneys (optional)</span></span>

<span data-ttu-id="59ac9-132">弁護士クライアント特権検出モデルをフルに活用し、前述の Has **Attorney** または潜在的特権検出の結果を使用するには、組織で働く弁護士および法務担当者の電子メール アドレスの一覧をアップロードすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="59ac9-132">To take full advantage of the attorney-client privilege detection model and use the results of the **Has Attorney** or **Potentially Privileged** detection that was previously described, we recommend that you upload a list of email addresses for the lawyers and legal personnel who work for your organization.</span></span> 

<span data-ttu-id="59ac9-133">弁護士クライアント特権検出モデルで使用する弁護士リストをアップロードするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="59ac9-133">To upload an attorney list for use by the attorney-client privilege detection model:</span></span>

1. <span data-ttu-id="59ac9-134">.csvファイル (見出し行なし) を作成し、適切な各人のメール アドレスを別々の行に追加します。</span><span class="sxs-lookup"><span data-stu-id="59ac9-134">Create a .csv file (without a header row) and add the email address for each appropriate person on a separate line.</span></span> <span data-ttu-id="59ac9-135">このファイルをローカル コンピューターに保存します。</span><span class="sxs-lookup"><span data-stu-id="59ac9-135">Save this file to your local computer.</span></span>

2. <span data-ttu-id="59ac9-136">**[Advanced eDiscovery]** ホーム ページの [設定] タイルで、[実験機能の構成]**を選択** し、[弁護士とクライアントの特権設定の管理]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="59ac9-136">On the **Advanced eDiscovery** home page, in the **Settings** tile, select **Configure experimental features**, and then select **Manage attorney-client privilege setting**.</span></span>

   <span data-ttu-id="59ac9-137">[ **弁護士とクライアントの特権]** ページが表示され、[ **弁護士クライアント** 特権の検出] トグルがオンにされます。</span><span class="sxs-lookup"><span data-stu-id="59ac9-137">The **Attorney-client privilege** page is displayed, and the **Attorney-client privilege detection** toggle is turned on.</span></span>

   ![弁護士-クライアント特権のフライアウト ページ](../media/AeDUploadAttorneyList.png)

3. <span data-ttu-id="59ac9-139">[ **参照]** を選択し、手順 1 で.csvファイルを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="59ac9-139">Select **Browse** and then find and select the .csv file that you created in step 1.</span></span>

4. <span data-ttu-id="59ac9-140">[保存 **] を** 選択して弁護士リストをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="59ac9-140">Select **Save** to upload the attorney list.</span></span>

## <a name="use-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="59ac9-141">弁護士クライアント特権検出モデルの使用</span><span class="sxs-lookup"><span data-stu-id="59ac9-141">Use the attorney-client privilege detection model</span></span>

<span data-ttu-id="59ac9-142">このセクションの手順に従って、レビュー セット内のドキュメントに対して弁護士クライアント特権の検出を使用します。</span><span class="sxs-lookup"><span data-stu-id="59ac9-142">Follow the steps in this section to use attorney-client privilege detection for documents in a review set.</span></span>

### <a name="step-1-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a><span data-ttu-id="59ac9-143">手順 1: 弁護士とクライアントの特権検出モデルを使用してスマート タグ グループを作成する</span><span class="sxs-lookup"><span data-stu-id="59ac9-143">Step 1: Create a smart tag group with attorney-client privilege detection model</span></span>

<span data-ttu-id="59ac9-144">レビュー プロセスで弁護士/依頼人特権の検出結果を確認する主な方法の 1 つは、スマート タグ グループを使用することです。</span><span class="sxs-lookup"><span data-stu-id="59ac9-144">One of the primary ways to see the results of attorney-client privilege detection in your review process is by using a smart tag group.</span></span> <span data-ttu-id="59ac9-145">スマート タグ グループは、弁護士/依頼人特権の検出結果を示し、スマート タグ グループ内のタグの横に、結果をインラインで表示します。</span><span class="sxs-lookup"><span data-stu-id="59ac9-145">A smart tag group indicates the results of the attorney-client privilege detection and shows the results in-line next to the tags in a smart tag group.</span></span> <span data-ttu-id="59ac9-146">これにより、ドキュメントレビュー中に、潜在的に特権のあるドキュメントをすばやく識別できます。</span><span class="sxs-lookup"><span data-stu-id="59ac9-146">This lets you quickly identify potentially privileged documents during document review.</span></span> <span data-ttu-id="59ac9-147">また、スマート タグ グループ内のタグを使用して、ドキュメントに特権付き、または特権なしのタグを付けることもできます。</span><span class="sxs-lookup"><span data-stu-id="59ac9-147">Additionally, you can also use the tags in the smart tag group to tag documents as privileged or non-privileged.</span></span> <span data-ttu-id="59ac9-148">スマート タグの詳細については、「スマート タグを設定する」を参照[Advanced eDiscovery。](smart-tags.md)</span><span class="sxs-lookup"><span data-stu-id="59ac9-148">For more information about smart tags, see [Set up smart tags in Advanced eDiscovery](smart-tags.md).</span></span>

1. <span data-ttu-id="59ac9-149">手順 1 で分析したドキュメントを含むレビュー セットで、[レビュー セットの管理] を選択し、[タグの管理]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="59ac9-149">In the review set that contains the documents that you analyzed in Step 1, select **Manage review set** and then select **Manage tags**.</span></span>
 
2. <span data-ttu-id="59ac9-150">[ **タグ] で**、[グループの追加] の横にあるプルダウン **を選択し** 、[スマート タグ グループの **追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="59ac9-150">Under **Tags**, select the pull-down next to **Add group** and then select **Add smart tag group**.</span></span>

   ![[スマート タグ グループの追加] を選択します。](../media/AeDCreateSmartTag.png)

3. <span data-ttu-id="59ac9-152">[スマート タグ **のモデルの選択]** ページで、[弁護士クライアント特権] の横にある **[\*\*\*\*選択] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="59ac9-152">On the **Choose a model for your smart tag** page, choose **Select** next to **Attorney-client privilege**.</span></span>

   <span data-ttu-id="59ac9-153">Attorney-client 特権 **という名前のタグ グループが** 表示されます。</span><span class="sxs-lookup"><span data-stu-id="59ac9-153">A tag group named **Attorney-client privilege** is displayed.</span></span> <span data-ttu-id="59ac9-154">このタグには、モデルによって生成される可能性がある結果に対応する **、正** と負という名前の 2 つの子タグが含まれます。</span><span class="sxs-lookup"><span data-stu-id="59ac9-154">It contains two child tags named **Positive** and **Negative**, which correspond to the possible results produced by the model.</span></span>

   ![弁護士-クライアント特権スマート タグ グループ](../media/AeDAttorneyClientSmartTagGroup.png)

3. <span data-ttu-id="59ac9-156">レビューに応じてタグ グループとタグの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="59ac9-156">Rename the tag group and tags as appropriate for your review.</span></span> <span data-ttu-id="59ac9-157">たとえば、正の名前を **[** 特権] に、[負] の **名前** を **[特権** ではありません **] に変更できます**。</span><span class="sxs-lookup"><span data-stu-id="59ac9-157">For example, you can rename **Positive** to **Privileged** and **Negative** to **Not privileged**.</span></span>

### <a name="step-2-analyze-a-review-set"></a><span data-ttu-id="59ac9-158">手順 2: レビュー セットを分析する</span><span class="sxs-lookup"><span data-stu-id="59ac9-158">Step 2: Analyze a review set</span></span>

<span data-ttu-id="59ac9-159">レビュー セット内のドキュメントを分析すると、弁護士クライアント特権検出モデルも実行され、対応するプロパティ (「どのように機能するか[](#how-does-it-work)」で説明)がレビュー セット内のすべてのドキュメントに追加されます。</span><span class="sxs-lookup"><span data-stu-id="59ac9-159">When you analyze the documents in a review set, the attorney-client privilege detection model will also run and the corresponding properties (described in [How does it work?](#how-does-it-work) will be added to every document in the review set.</span></span> <span data-ttu-id="59ac9-160">レビュー セット内のデータの分析の詳細については、「レビュー セット内のデータを分析する」を参照[Advanced eDiscovery。](analyzing-data-in-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="59ac9-160">For more information about analyzing data in review set, see [Analyze data in a review set in Advanced eDiscovery](analyzing-data-in-review-set.md).</span></span>

### <a name="step-3-use-the-smart-tag-group-for-review-of-privileged-content"></a><span data-ttu-id="59ac9-161">手順 3: 特権コンテンツのレビューにスマート タグ グループを使用する</span><span class="sxs-lookup"><span data-stu-id="59ac9-161">Step 3: Use the smart tag group for review of privileged content</span></span>

<span data-ttu-id="59ac9-162">レビュー セットを分析してスマート タグを設定した後、次にドキュメントを確認します。</span><span class="sxs-lookup"><span data-stu-id="59ac9-162">After analyzing the review set and setting up smart tags, the next step is to review the documents.</span></span> <span data-ttu-id="59ac9-163">モデルがドキュメントが潜在的に特権を持つ可能性があると判断した場合、[タグ付け] パネルの対応するスマート タグは、弁護士とクライアントの特権検出によって生成される次の結果を示します。</span><span class="sxs-lookup"><span data-stu-id="59ac9-163">If the model has determined the document is potentially privileged, the corresponding smart tag in the **Tagging panel** will indicate the following results produced by the attorney-client privilege detection:</span></span>

- <span data-ttu-id="59ac9-164">ドキュメントに実際に合法なコンテンツがある場合は、対応するスマート タグの横に [法的コンテンツ] というラベルが表示されます (この場合は既定の **正** のタグです)。</span><span class="sxs-lookup"><span data-stu-id="59ac9-164">If the document has content that may be legal in nature, the label **Legal content** is displayed next to the corresponding smart tag (which in this case is the default **Positive** tag).</span></span>

- <span data-ttu-id="59ac9-165">ドキュメントに組織の弁護士リストに含まれる参加者が含まれる場合は、対応するスマートタグの横に [弁護士] というラベルが表示されます (この場合は既定の **正** のタグです)。</span><span class="sxs-lookup"><span data-stu-id="59ac9-165">If the document has a participant who is found in your organization's attorney list, the label **Attorney** is displayed next to the corresponding smart tag (which in this case is also the default **Positive** tag).</span></span>

- <span data-ttu-id="59ac9-166">ドキュメントに実際に合法なコンテンツが含み、参加者が弁護士リストに見つかった場合は、法務コンテンツと弁護士ラベルの両方 **が** 表示されます。</span><span class="sxs-lookup"><span data-stu-id="59ac9-166">If the document has content that may be legal in nature *and* has a participant found in the attorney list, both the **Legal content**  and **Attorney** labels are displayed.</span></span> 

<span data-ttu-id="59ac9-167">モデルが、ドキュメントに実際に合法なコンテンツが含まれているか、弁護士リストの参加者が含まれていると判断した場合、タグ付けパネルにはどちらのラベルも表示されません。</span><span class="sxs-lookup"><span data-stu-id="59ac9-167">If the model determines that a document doesn't contain content that is legal in nature or doesn't contain a participant from the attorney list, then neither label is displayed in the tagging panel.</span></span>

<span data-ttu-id="59ac9-168">たとえば、次のスクリーンショットは 2 つのドキュメントを示しています。</span><span class="sxs-lookup"><span data-stu-id="59ac9-168">For example, the following screenshots show two documents.</span></span> <span data-ttu-id="59ac9-169">最初のコンテンツには、自然の中で合法的なコンテンツが含まれているので、参加者は弁護士のリストに含まれている。</span><span class="sxs-lookup"><span data-stu-id="59ac9-169">The first one contains content that is legal in nature and has a participant found in the list of attorneys.</span></span> <span data-ttu-id="59ac9-170">2 つ目はどちらも含まれているため、ラベルは表示されません。</span><span class="sxs-lookup"><span data-stu-id="59ac9-170">The second contains neither and therefore doesn't display any labels.</span></span>

![弁護士と法的コンテンツ ラベルを含むドキュメント](../media/AeDTaggingPanelLegalContentAttorney.png)

![ラベルのないドキュメント](../media/AeDTaggingPanelNegative.png)

<span data-ttu-id="59ac9-173">ドキュメントを確認して、特権コンテンツが含まれているか確認した後、適切なタグでドキュメントにタグを付けできます。</span><span class="sxs-lookup"><span data-stu-id="59ac9-173">After you review a document to see if it contains privileged content, you can tag the document with the appropriate tag.</span></span>
