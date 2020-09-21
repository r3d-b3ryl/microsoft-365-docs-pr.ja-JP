---
title: 保持ラベルを自動的に適用してコンテンツを保持または削除する
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 必要なものを保持し、必要でないものを削除するためにラベルを自動的に適用できるように、保持ラベルを作成して自動発行します。
ms.openlocfilehash: 088a521089d34e74865c94b3cd147b02f8d812cb
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "47816970"
---
# <a name="automatically-apply-a-retention-label-to-retain-or-delete-content"></a><span data-ttu-id="27e27-103">保持ラベルを自動的に適用してコンテンツを保持または削除する</span><span class="sxs-lookup"><span data-stu-id="27e27-103">Automatically apply a retention label to retain or delete content</span></span>

><span data-ttu-id="27e27-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="27e27-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="27e27-105">[保持ラベル](retention.md)の最も強力な機能の 1 つは、指定した条件に一致したコンテンツに自動的にラベルを適用することです。</span><span class="sxs-lookup"><span data-stu-id="27e27-105">One of the most powerful features of [retention labels](retention.md) is the ability to apply them automatically to content that matches specified conditions.</span></span> <span data-ttu-id="27e27-106">この場合、組織内のユーザーが保持ラベルを適用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="27e27-106">In this case, people in your organization don't need to apply the retention labels.</span></span> <span data-ttu-id="27e27-107">Microsoft 365 が行います。</span><span class="sxs-lookup"><span data-stu-id="27e27-107">Microsoft 365 does the work for them.</span></span>
  
<span data-ttu-id="27e27-108">自動適用アイテム保持ラベルが強力な機能である理由は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="27e27-108">Auto-applying retention labels are powerful because:</span></span>
  
- <span data-ttu-id="27e27-109">ユーザーのトレーニングは、一部の分類方法についてのみ必要。</span><span class="sxs-lookup"><span data-stu-id="27e27-109">You don't need to train your users on all of your classifications.</span></span>
    
- <span data-ttu-id="27e27-110">ユーザーへの依存は、一部のコンテンツを正しく分類するためにのみ必要。</span><span class="sxs-lookup"><span data-stu-id="27e27-110">You don't need to rely on users to classify all content correctly.</span></span>
    
- <span data-ttu-id="27e27-111">ユーザーはデータ ガバナンス ポリシーについて把握する必要がなくなるので、仕事に集中できる。</span><span class="sxs-lookup"><span data-stu-id="27e27-111">Users no longer need to know about data governance policies - they can focus on their work.</span></span>
    
<span data-ttu-id="27e27-112">コンテンツに機密情報、キーワード、検索可能なプロパティ、または[トレーニング可能な分類子](classifier-getting-started-with.md)のマッチが含まれている場合、保持ラベルをコンテンツに自動的に適用できます。</span><span class="sxs-lookup"><span data-stu-id="27e27-112">You can apply retention labels to content automatically when that content contains sensitive information, keywords or searchable properties, or a match for [trainable classifiers](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="27e27-113">保持ラベルを自動的に適用するプロセスは、次の条件に基づいています。</span><span class="sxs-lookup"><span data-stu-id="27e27-113">The processes to automatically apply a retention label based on these conditions:</span></span>

![自動適用ラベルの役割とタスクの図](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)

<span data-ttu-id="27e27-115">次の手順を 2 つの管理手順に使用します。</span><span class="sxs-lookup"><span data-stu-id="27e27-115">Use the following instructions for the two admin steps.</span></span>

> [!NOTE]
> <span data-ttu-id="27e27-116">自動ポリシーで、保持ラベルを自動的に適用するための条件によりサービス側でのラベル付けを使用します。</span><span class="sxs-lookup"><span data-stu-id="27e27-116">Auto-policies use service-side labeling with conditions to automatically apply retention labels.</span></span> <span data-ttu-id="27e27-117">次の操作を行うときにラベル ポリシーを使用して保持ラベルを自動的に適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="27e27-117">You can also automatically apply a retention label with a label policy when you do the following:</span></span> 
>
> - <span data-ttu-id="27e27-118">SharePoint ライブラリ、フォルダー、ドキュメントに既定の保持ラベルを適用して、そのコンテナー内のラベルのないコンテンツに自動的にラベルが付けられるようにする</span><span class="sxs-lookup"><span data-stu-id="27e27-118">Apply a default retention label to a SharePoint library, folder, or document set so that unlabeled content in that container is automatically labeled</span></span>
>- <span data-ttu-id="27e27-119">ルールを使用して、保持ラベルをメールに自動的に適用する</span><span class="sxs-lookup"><span data-stu-id="27e27-119">Automatically applying a retention label to email by using rules</span></span>
>
> <span data-ttu-id="27e27-120">これらのシナリオについては、[アイテム保持ラベルを作成してアプリに適用する](create-apply-retention-labels.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27e27-120">For these scenarios, see [Create and apply retention labels in apps](create-apply-retention-labels.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="27e27-121">はじめに</span><span class="sxs-lookup"><span data-stu-id="27e27-121">Before you begin</span></span>

<span data-ttu-id="27e27-122">組織のグローバル管理者には、保持ラベルとそれらのポリシーを作成および編集できる完全な権限があります。</span><span class="sxs-lookup"><span data-stu-id="27e27-122">The global admin for your organization has full permissions to create and edit retention labels and their policies.</span></span> <span data-ttu-id="27e27-123">グローバル管理者としてサインインしていない場合は、「[アイテム保持ポリシーと保持ラベルを作成して管理するために必要なアクセス許可](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27e27-123">If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="how-to-auto-apply-a-retention-label"></a><span data-ttu-id="27e27-124">保持ラベルを自動適用する方法</span><span class="sxs-lookup"><span data-stu-id="27e27-124">How to auto-apply a retention label</span></span>

<span data-ttu-id="27e27-125">まず、保持ラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="27e27-125">First, create your retention label.</span></span> <span data-ttu-id="27e27-126">次に、そのラベルを適用する自動ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="27e27-126">Then create an auto-policy to apply that label.</span></span> <span data-ttu-id="27e27-127">保持ラベルを既に作成してある場合は、[自動ポリシーの作成](#step-2-create-an-auto-apply-policy)に進んでください。</span><span class="sxs-lookup"><span data-stu-id="27e27-127">If you have already created your retention label, skip to [creating an auto-policy](#step-2-create-an-auto-apply-policy).</span></span>

<span data-ttu-id="27e27-128">ナビゲーション手順は、[レコード管理](records-management.md)を使用しているかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="27e27-128">Navigation instructions depend on whether you're using [records management](records-management.md) or not.</span></span> <span data-ttu-id="27e27-129">両方のシナリオの手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="27e27-129">Instructions are provided for both scenarios.</span></span>

### <a name="step-1-create-a-retention-label"></a><span data-ttu-id="27e27-130">手順 1: 保持ラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="27e27-130">Step 1: Create a retention label</span></span>

1. <span data-ttu-id="27e27-131">[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)で、次のいずれかの場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="27e27-131">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="27e27-132">レコード管理を使用している場合:</span><span class="sxs-lookup"><span data-stu-id="27e27-132">If you are using records management:</span></span>
        - <span data-ttu-id="27e27-133">[**ソリューション**] > [**レコード管理**] > [**ファイル計画**] タブ > [**+ラベルを作成**] > [**保持ラベル**]</span><span class="sxs-lookup"><span data-stu-id="27e27-133">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="27e27-134">レコード管理を使用していない場合:</span><span class="sxs-lookup"><span data-stu-id="27e27-134">If you are not using records management:</span></span>
       - <span data-ttu-id="27e27-135">[**ソリューション**] > [**情報ガバナンス**] > [**ラベル**] タブ > + [**ラベルを作成**]</span><span class="sxs-lookup"><span data-stu-id="27e27-135">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="27e27-136">すぐにオプションが表示されませんか?</span><span class="sxs-lookup"><span data-stu-id="27e27-136">Don't immediately see your option?</span></span> <span data-ttu-id="27e27-137">最初に [**すべて表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="27e27-137">First select **Show all**.</span></span> 

2. <span data-ttu-id="27e27-138">ウィザードでプロンプトに従います。</span><span class="sxs-lookup"><span data-stu-id="27e27-138">Follow the prompts in the wizard.</span></span> <span data-ttu-id="27e27-139">レコード管理を使用している場合:</span><span class="sxs-lookup"><span data-stu-id="27e27-139">If you are using records management:</span></span>
    
    - <span data-ttu-id="27e27-140">ファイル計画記述子については、「[Use file plan to manage retention labels (ファイル計画を使用して保持ラベルを管理する)](file-plan-manager.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27e27-140">For information about the file plan descriptors, see [Use file plan to manage retention labels](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="27e27-141">保持ラベルを使用して[レコード](records-management.md#records)を宣言するには、[**アイテムをレコードとしてマークする**] オプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="27e27-141">To use the retention label to declare a [record](records-management.md#records), enable the option **Mark items as a record**.</span></span>

3. <span data-ttu-id="27e27-142">ラベルを作成し、ラベルの公開、ラベルの自動適用、またはラベルの保存のオプションが表示されたら、[**このラベルを特定の種類のコンテンツに自動適用する**] を選択してから、[**完了**] を選択すると、次の手順の手順 2 に直接進む自動ラベル作成ウィザードが起動します。</span><span class="sxs-lookup"><span data-stu-id="27e27-142">After you have created the label and you see the options to publish the label, auto-apply the label, or just save the label: Select **Auto-apply this label to a specific type of content**, and then select **Done** to start the Create auto-labeling wizard that takes you directly to step 2 in the following procedure.</span></span>

<span data-ttu-id="27e27-143">既存のラベルを編集するには、そのラベルを選択してから [**ラベルの編集**] オプションを選択し、手順 2 からラベルの説明や[有効な設定](#updating-retention-labels-and-their-policies)を変更するための保持の編集ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="27e27-143">To edit an existing label, select it, and then select the **Edit label** option to start the Edit retention wizard that lets you change the label descriptions and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>


### <a name="step-2-create-an-auto-apply-policy"></a><span data-ttu-id="27e27-144">手順 2: 自動適用ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="27e27-144">Step 2: Create an auto-apply policy</span></span>

<span data-ttu-id="27e27-145">自動適用ポリシーを作成する場合、指定した条件に基づいてコンテンツに自動的に適用する保持ラベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="27e27-145">When you create an auto-apply policy, you select a retention label to automatically apply to content, based on the conditions that you specify.</span></span>

1. <span data-ttu-id="27e27-146">[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)で、次のいずれかの場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="27e27-146">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="27e27-147">レコード管理を使用している場合: **情報ガバナンス**:</span><span class="sxs-lookup"><span data-stu-id="27e27-147">If you are using records management: **Information governance**:</span></span>
        - <span data-ttu-id="27e27-148">[**ソリューション**] > [**レコード管理**] > [**ラベル ポリシー**] タブ > [**自動適用ラベル**]</span><span class="sxs-lookup"><span data-stu-id="27e27-148">**Solutions** > **Records management** > **Label policies** tab > **Auto-apply a label**</span></span>
    
    - <span data-ttu-id="27e27-149">レコード管理を使用していない場合:</span><span class="sxs-lookup"><span data-stu-id="27e27-149">If you are not using records management:</span></span>
        - <span data-ttu-id="27e27-150">[**ソリューション**] > [**情報ガバナンス**] > [**ラベル ポリシー**] タブ > [**自動適用ラベル**]</span><span class="sxs-lookup"><span data-stu-id="27e27-150">**Solutions** > **Information governance** > **Label policies** tab > **Auto-apply a label**</span></span>
    
    <span data-ttu-id="27e27-151">すぐにオプションが表示されませんか?</span><span class="sxs-lookup"><span data-stu-id="27e27-151">Don't immediately see your option?</span></span> <span data-ttu-id="27e27-152">最初に [**すべて表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="27e27-152">First select **Show all**.</span></span> 

2. <span data-ttu-id="27e27-153">自動ラベル作成ウィザードの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="27e27-153">Follow the prompts in the Create auto-labeling wizard.</span></span>
    
    <span data-ttu-id="27e27-154">保持ラベルを自動的に適用する条件の構成については、このページの「[自動適用の保持ラベルの条件の構成](#configuring-conditions-for-auto-apply-retention-labels)」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="27e27-154">For information about configuring the conditions that automatically apply the retention label, see the [Configuring conditions for auto-apply retention labels](#configuring-conditions-for-auto-apply-retention-labels) section on this page.</span></span>
    
    <span data-ttu-id="27e27-155">保持ラベルでサポートされている場所については、「[保持ラベルと場所](retention.md#retention-label-policies-and-locations)」のセクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="27e27-155">For information about the locations supported by retention labels, see the [Retention labels and locations](retention.md#retention-label-policies-and-locations) section.</span></span>

<span data-ttu-id="27e27-156">既存の自動適用ポリシーを編集するには、ポリシーを選択して、アイテム保持ポリシーの編集ウィザードを起動します。このウィザードでは、手順 2 で選択した保持ラベルと[有効な設定](#updating-retention-labels-and-their-policies)を変更できます。</span><span class="sxs-lookup"><span data-stu-id="27e27-156">To edit an existing auto-apply policy, select it to start the Edit retention policy wizard that lets you change the selected retention label and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>


### <a name="configuring-conditions-for-auto-apply-retention-labels"></a><span data-ttu-id="27e27-157">自動適用の保持ラベルの条件の構成</span><span class="sxs-lookup"><span data-stu-id="27e27-157">Configuring conditions for auto-apply retention labels</span></span>

<span data-ttu-id="27e27-158">コンテンツに次の内容が含まれている場合は、保持ラベルを自動的にコンテンツに適用できます。</span><span class="sxs-lookup"><span data-stu-id="27e27-158">You can apply retention labels to content automatically when that content contains:</span></span>

- [<span data-ttu-id="27e27-159">特定の種類の機密情報</span><span class="sxs-lookup"><span data-stu-id="27e27-159">Specific types of sensitive information</span></span>](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)

- [<span data-ttu-id="27e27-160">作成したクエリに一致する特定のキーワードまたは検索可能なプロパティ</span><span class="sxs-lookup"><span data-stu-id="27e27-160">Specific keywords or searchable properties that match a query you create</span></span>](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [<span data-ttu-id="27e27-161">トレーニング可能な分類子の一致</span><span class="sxs-lookup"><span data-stu-id="27e27-161">A match for trainable classifiers</span></span>](#auto-apply-labels-to-content-by-using-trainable-classifiers)

#### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="27e27-162">特定の種類の機密情報によるコンテンツへのラベルの自動適用</span><span class="sxs-lookup"><span data-stu-id="27e27-162">Auto-apply labels to content with specific types of sensitive information</span></span>

<span data-ttu-id="27e27-163">機密情報用に自動適用の保持ラベルを作成するときに、データ損失防止 (DLP) ポリシーを作成するときと同じポリシー テンプレートの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="27e27-163">When you create auto-apply retention labels for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="27e27-164">各テンプレートは、特定の種類の機密情報を見つけるように事前に設定されています。</span><span class="sxs-lookup"><span data-stu-id="27e27-164">Each template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="27e27-165">たとえば、ここに示されているテンプレートは、**プライバシー** カテゴリからの U.S. ITIN、SSN、パスポート番号、および **U.S 個人を特定できる情報 (PII) データ テンプレート**を検索します。</span><span class="sxs-lookup"><span data-stu-id="27e27-165">For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers from the **Privacy** category, and **U.S Personally Identifiable Information (PII) Data template**:</span></span>

![機密情報の種類によるポリシー テンプレート](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)

<span data-ttu-id="27e27-167">機密情報の種類の詳細については、「[機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27e27-167">To learn more about the sensitivity information types, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span>

<span data-ttu-id="27e27-168">ポリシー テンプレートを選択すると、機密情報の任意の種類を追加または削除できます。また、インスタンス数や一致精度を変更できます。</span><span class="sxs-lookup"><span data-stu-id="27e27-168">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy.</span></span> <span data-ttu-id="27e27-169">次に示すスクリーンショットの例では、保持ラベルは次の場合にのみ自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="27e27-169">In the example screenshot shown next, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="27e27-170">検出される機密情報の種類には、一致精度 (または信頼度) が少なくとも 75 はあります。</span><span class="sxs-lookup"><span data-stu-id="27e27-170">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75.</span></span> <span data-ttu-id="27e27-171">機密情報の種類の多くは、複数のパターンで定義されています。高い一致精度が指定されたパターンにはより多くの証拠 (キーワード、日付、アドレスなど) が見つかることが必要とされるのに対して、低い一致精度が指定されたパターンでは必要とされる証拠は少なくなります。</span><span class="sxs-lookup"><span data-stu-id="27e27-171">Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence.</span></span> <span data-ttu-id="27e27-172">**最小**一致精度が低いほど、コンテンツは条件に一致しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="27e27-172">The lower the **min** match accuracy, the easier it is for content to match the condition.</span></span>

- <span data-ttu-id="27e27-173">3 種類の機密情報のうち、1 から 9 個のインスタンスを含むコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="27e27-173">The content contains between 1 and 9 instances of any of these three sensitive information types.</span></span> <span data-ttu-id="27e27-174">**宛先**値を削除すると、値は**任意**に変更されます。</span><span class="sxs-lookup"><span data-stu-id="27e27-174">You can delete the **to** value so that it changes to **Any**.</span></span>

<span data-ttu-id="27e27-175">これらのオプションの詳細については、DLP のドキュメント「[一致の難易度を上下するためにルールを調整する](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)」にある次のガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="27e27-175">For more information about these options, see the following guidance from the DLP documentation [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![機密情報の種類を識別するためのオプション](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
#### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="27e27-177">キーワードまたは検索可能なプロパティによるコンテンツへの自動適用ラベル</span><span class="sxs-lookup"><span data-stu-id="27e27-177">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="27e27-p113">特定の単語、フレーズ、または検索可能なプロパティの値を含むクエリを使用して、コンテンツにラベルを自動で適用できます。AND、OR、NOT などの検索演算子を使用してクエリを絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="27e27-p113">You can auto-apply labels to content by using a query that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators such as AND, OR, and NOT.</span></span>

![クエリ エディター](../media/new-retention-query-editor.png)

<span data-ttu-id="27e27-181">キーワード クエリ言語 (KQL) 構文の詳細については、「[キーワード クエリ言語 (KQL) 構文のリファレンス](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="27e27-181">For more information about the query syntax that uses Keyword Query Language (KQL), see [Keyword Query Language (KQL) syntax reference](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).</span></span>

<span data-ttu-id="27e27-182">クエリベースのラベルでは、検索インデックスを使用してコンテンツを識別します。</span><span class="sxs-lookup"><span data-stu-id="27e27-182">Query-based labels use the search index to identify content.</span></span> <span data-ttu-id="27e27-183">使用できる検索可能なプロパティの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27e27-183">For more information about the searchable properties that you can use, see:</span></span>

- [<span data-ttu-id="27e27-184">コンテンツ検索のキーワード クエリと検索条件</span><span class="sxs-lookup"><span data-stu-id="27e27-184">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
- [<span data-ttu-id="27e27-185">クロールされたプロパティと管理プロパティの概要 (SharePoint Server)</span><span class="sxs-lookup"><span data-stu-id="27e27-185">Overview of crawled and managed properties in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

> [!NOTE]
> <span data-ttu-id="27e27-186">SharePoint 管理プロパティはエイリアスをサポートしますが、保持ラベルを構成するときにこれらを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="27e27-186">Although SharePoint managed properties support aliases, don't use these when you configure your retention labels.</span></span> <span data-ttu-id="27e27-187">「RefinableString01」のように、管理プロパティの実際の名前を常に指定します。</span><span class="sxs-lookup"><span data-stu-id="27e27-187">Always specify the actual name of the managed property, for example, "RefinableString01".</span></span>

<span data-ttu-id="27e27-188">クエリの例:</span><span class="sxs-lookup"><span data-stu-id="27e27-188">Examples queries:</span></span>

| <span data-ttu-id="27e27-189">Workload</span><span class="sxs-lookup"><span data-stu-id="27e27-189">Workload</span></span> | <span data-ttu-id="27e27-190">例</span><span class="sxs-lookup"><span data-stu-id="27e27-190">Example</span></span> |
|:-----|:-----|
|<span data-ttu-id="27e27-191">Exchange</span><span class="sxs-lookup"><span data-stu-id="27e27-191">Exchange</span></span>   | `subject:"Quarterly Financials"` |
|<span data-ttu-id="27e27-192">Exchange</span><span class="sxs-lookup"><span data-stu-id="27e27-192">Exchange</span></span>   | `recipients:garthf@contoso.com` |
|<span data-ttu-id="27e27-193">SharePoint</span><span class="sxs-lookup"><span data-stu-id="27e27-193">SharePoint</span></span> | `contenttype:contract` |
|<span data-ttu-id="27e27-194">SharePoint</span><span class="sxs-lookup"><span data-stu-id="27e27-194">SharePoint</span></span> | `site:https://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract`|

#### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="27e27-195">トレーニング可能な分類子を使用して、ラベルをコンテンツに自動的に適用する</span><span class="sxs-lookup"><span data-stu-id="27e27-195">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="27e27-196">トレーニング可能な分類子のオプションを選択すると、組み込み分類子またはカスタム分類子のいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="27e27-196">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="27e27-197">組み込み分類子には、**履歴書**、**ソース コード**、**個人を標的にしたハラスメント**、**冒とく**、および**脅威**が含まれます。</span><span class="sxs-lookup"><span data-stu-id="27e27-197">The built-in classifiers include **Resumes**, **SourceCode**, **Targeted Harassment**, **Profanity**, and **Threat**:</span></span>

![トレーニング可能な分類子の選択](../media/retention-label-classifers.png)

> [!CAUTION]
> <span data-ttu-id="27e27-199">組み込みの [**不快な言葉**] は、誤検知の数が多いため、廃止予定です。</span><span class="sxs-lookup"><span data-stu-id="27e27-199">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="27e27-200">この組み込み分類子を使用しないでください。現在使用している場合は、ビジネス プロセスを移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27e27-200">Don't use this built-in classifier and if you are currently using it, you should move your business processes off it.</span></span> <span data-ttu-id="27e27-201">代わりに、[**個人を標的にしたハラスメント**]、[**冒涜的表現**]、および [**脅威**] の組み込み分類子を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="27e27-201">We recommend using the **Targeted Harassment**, **Profanity**, and **Threat** built-in classifiers instead.</span></span>

<span data-ttu-id="27e27-202">このオプションを使用してラベルを自動的に適用するには、SharePoint サイトとメールボックスには少なくとも 10 MB のデータが必要です。</span><span class="sxs-lookup"><span data-stu-id="27e27-202">To automatically apply a label by using this option, SharePoint sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="27e27-203">トレーニング可能な分類子の詳細については、「[トレーニング可能な分類子 (プレビュー) の概要](classifier-getting-started-with.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27e27-203">For more information about trainable classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="27e27-204">構成の例については、「[組み込みの分類子を準備して使用する方法](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27e27-204">For an example configuration, see [How to prepare for and use a built-in classifier](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs).</span></span>

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="27e27-205">保持ラベルが有効になるまでの所要時間</span><span class="sxs-lookup"><span data-stu-id="27e27-205">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="27e27-206">保持ラベルを自動適用する場合、条件に一致する既存のコンテンツすべてに保持ラベルが適用されるまでに最大 7 日間かかります。</span><span class="sxs-lookup"><span data-stu-id="27e27-206">When you auto-apply retention labels, it can take up to seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![自動適用ラベルが有効になるタイミングの図](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
## <a name="updating-retention-labels-and-their-policies"></a><span data-ttu-id="27e27-208">保持ラベルとそのポリシーの更新</span><span class="sxs-lookup"><span data-stu-id="27e27-208">Updating retention labels and their policies</span></span>

<span data-ttu-id="27e27-209">保持ラベルや自動適用ポリシーを編集すると、その保持ラベルが既にコンテンツに適用されている場合、新しく識別されるコンテンツに加えて、そのコンテンツにも更新された設定が自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="27e27-209">When you edit a retention label or auto-apply policy, and the retention label is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly identified.</span></span>

<span data-ttu-id="27e27-210">ラベルやポリシーを作成して保存した後には変更できない設定があり、それらは以下のものを含みます。</span><span class="sxs-lookup"><span data-stu-id="27e27-210">Some settings can't be changed after the label or policy is created and saved, which include:</span></span>
- <span data-ttu-id="27e27-211">作成日時に基づいてコンテンツを保持または削除するようにラベルを構成していない場合を除いた、保持期間以外の保持設定。</span><span class="sxs-lookup"><span data-stu-id="27e27-211">The retention settings except the retention period, unless you've configured the label to retain or delete the content based on when it was created.</span></span>
- <span data-ttu-id="27e27-212">アイテムをレコードとしてマークするオプション。</span><span class="sxs-lookup"><span data-stu-id="27e27-212">The option to mark items as a record.</span></span>

## <a name="next-steps"></a><span data-ttu-id="27e27-213">次の手順</span><span class="sxs-lookup"><span data-stu-id="27e27-213">Next steps</span></span>

<span data-ttu-id="27e27-214">[保持ラベルを使用して、SharePoint に保存されているドキュメントのライフサイクルを管理する](auto-apply-retention-labels-scenario.md)を参照してください。例として、SharePoint の管理プロパティで、自動適用ポリシーを使用し、保持期間を開始するために、イベントベースの保持を使用するというシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="27e27-214">See [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md) for an example scenario that uses an auto-apply policy with managed properties in SharePoint, and event-based retention to start the retention period.</span></span>
