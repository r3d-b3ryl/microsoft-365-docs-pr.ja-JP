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
ms.openlocfilehash: eb29a846f6a7352eec02683c70dad1b0a423bdfa
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127604"
---
# <a name="automatically-apply-a-retention-label-to-retain-or-delete-content"></a><span data-ttu-id="8f64e-103">保持ラベルを自動的に適用してコンテンツを保持または削除する</span><span class="sxs-lookup"><span data-stu-id="8f64e-103">Automatically apply a retention label to retain or delete content</span></span>

><span data-ttu-id="8f64e-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="8f64e-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="8f64e-105">[保持ラベル](retention.md)の最も強力な機能の 1 つは、指定した条件に一致したコンテンツに自動的にラベルを適用することです。</span><span class="sxs-lookup"><span data-stu-id="8f64e-105">One of the most powerful features of [retention labels](retention.md) is the ability to apply them automatically to content that matches specified conditions.</span></span> <span data-ttu-id="8f64e-106">この場合、組織内のユーザーが保持ラベルを適用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8f64e-106">In this case, people in your organization don't need to apply the retention labels.</span></span> <span data-ttu-id="8f64e-107">Microsoft 365 が行います。</span><span class="sxs-lookup"><span data-stu-id="8f64e-107">Microsoft 365 does the work for them.</span></span>
  
<span data-ttu-id="8f64e-108">自動適用アイテム保持ラベルが強力な機能である理由は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8f64e-108">Auto-applying retention labels are powerful because:</span></span>
  
- <span data-ttu-id="8f64e-109">ユーザーのトレーニングは、一部の分類方法についてのみ必要。</span><span class="sxs-lookup"><span data-stu-id="8f64e-109">You don't need to train your users on all of your classifications.</span></span>
    
- <span data-ttu-id="8f64e-110">ユーザーへの依存は、一部のコンテンツを正しく分類するためにのみ必要。</span><span class="sxs-lookup"><span data-stu-id="8f64e-110">You don't need to rely on users to classify all content correctly.</span></span>
    
- <span data-ttu-id="8f64e-111">ユーザーはデータ ガバナンス ポリシーについて把握する必要がなくなるので、仕事に集中できる。</span><span class="sxs-lookup"><span data-stu-id="8f64e-111">Users no longer need to know about data governance policies - they can focus on their work.</span></span>
    
<span data-ttu-id="8f64e-112">コンテンツに機密情報、キーワード、[トレーニング可能な分類子](classifier-getting-started-with.md)のマッチが含まれている場合、保持ラベルをコンテンツに自動的に適用できます。</span><span class="sxs-lookup"><span data-stu-id="8f64e-112">You can apply retention labels to content automatically when that content contains sensitive information, keywords, or a match for [trainable classifiers](classifier-getting-started-with.md).</span></span>
    
<span data-ttu-id="8f64e-113">保持ラベルを自動的に適用するプロセスは、次の条件に基づいています。</span><span class="sxs-lookup"><span data-stu-id="8f64e-113">The processes to automatically apply a retention label based on these conditions:</span></span>

![自動適用ラベルの役割とタスクの図](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)

<span data-ttu-id="8f64e-115">次の手順を 2 つの管理手順に使用します。</span><span class="sxs-lookup"><span data-stu-id="8f64e-115">Use the following instructions for the two admin steps.</span></span>

> [!NOTE]
> <span data-ttu-id="8f64e-116">自動ポリシーで、保持ラベルを自動的に適用するための条件によりサービス側でのラベル付けを使用します。</span><span class="sxs-lookup"><span data-stu-id="8f64e-116">Auto-policies use service-side labeling with conditions to automatically apply retention labels.</span></span> <span data-ttu-id="8f64e-117">次の操作を行うときにラベル ポリシーを使用して保持ラベルを自動的に適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="8f64e-117">You can also automatically apply a retention label with a label policy when you do the following:</span></span> 
>
> - <span data-ttu-id="8f64e-118">SharePoint ライブラリ、フォルダー、ドキュメントに既定の保持ラベルを適用して、そのコンテナー内のラベルのないコンテンツに自動的にラベルが付けられるようにする</span><span class="sxs-lookup"><span data-stu-id="8f64e-118">Apply a default retention label to a SharePoint library, folder, or document set so that unlabeled content in that container is automatically labeled</span></span>
>- <span data-ttu-id="8f64e-119">ルールを使用して、保持ラベルをメールに自動的に適用する</span><span class="sxs-lookup"><span data-stu-id="8f64e-119">Automatically applying a retention label to email by using rules</span></span>
>
> <span data-ttu-id="8f64e-120">これらのシナリオについては、[アイテム保持ラベルを作成してアプリに適用する](create-apply-retention-labels.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f64e-120">For these scenarios, see [Create and apply retention labels in apps](create-apply-retention-labels.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="8f64e-121">はじめに</span><span class="sxs-lookup"><span data-stu-id="8f64e-121">Before you begin</span></span>

<span data-ttu-id="8f64e-122">組織のグローバル管理者には、保持ラベルとそれらのポリシーを作成および編集できる完全な権限があります。</span><span class="sxs-lookup"><span data-stu-id="8f64e-122">The global admin for your organization has full permissions to create and edit retention labels and their policies.</span></span> <span data-ttu-id="8f64e-123">グローバル管理者としてサインインしていない場合は、「[アイテム保持ポリシーと保持ラベルを作成して管理するために必要なアクセス許可](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f64e-123">If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="how-to-auto-apply-a-retention-label"></a><span data-ttu-id="8f64e-124">保持ラベルを自動適用する方法</span><span class="sxs-lookup"><span data-stu-id="8f64e-124">How to auto-apply a retention label</span></span>

<span data-ttu-id="8f64e-125">まず、保持ラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="8f64e-125">First, create your retention label.</span></span> <span data-ttu-id="8f64e-126">次に、そのラベルを適用する自動ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="8f64e-126">Then create an auto-policy to apply that label.</span></span> <span data-ttu-id="8f64e-127">保持ラベルを既に作成してある場合は、[自動ポリシーの作成](#step-2-create-an-auto-apply-policy)に進んでください。</span><span class="sxs-lookup"><span data-stu-id="8f64e-127">If you have already created your retention label, skip to [creating an auto-policy](#step-2-create-an-auto-apply-policy).</span></span>

<span data-ttu-id="8f64e-128">ナビゲーション手順は、[レコード管理](records-management.md)を使用しているかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="8f64e-128">Navigation instructions depend on whether you're using [records management](records-management.md) or not.</span></span> <span data-ttu-id="8f64e-129">両方のシナリオの手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="8f64e-129">Instructions are provided for both scenarios.</span></span>

### <a name="step-1-create-a-retention-label"></a><span data-ttu-id="8f64e-130">手順 1: 保持ラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="8f64e-130">Step 1: Create a retention label</span></span>

1. <span data-ttu-id="8f64e-131">[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)で、次のいずれかの場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="8f64e-131">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="8f64e-132">レコード管理を使用している場合:</span><span class="sxs-lookup"><span data-stu-id="8f64e-132">If you are using records management:</span></span>
        - <span data-ttu-id="8f64e-133">[**ソリューション**] > [**レコード管理**] > [**ファイル計画**] タブ > [**+ラベルを作成**] > [**保持ラベル**]</span><span class="sxs-lookup"><span data-stu-id="8f64e-133">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="8f64e-134">レコード管理を使用していない場合:</span><span class="sxs-lookup"><span data-stu-id="8f64e-134">If you are not using records management:</span></span>
       - <span data-ttu-id="8f64e-135">[**ソリューション**] > [**情報ガバナンス**] > [**ラベル**] タブ > + [**ラベルを作成**]</span><span class="sxs-lookup"><span data-stu-id="8f64e-135">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="8f64e-136">すぐにオプションが表示されませんか?</span><span class="sxs-lookup"><span data-stu-id="8f64e-136">Don't immediately see your option?</span></span> <span data-ttu-id="8f64e-137">最初に [**すべて表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f64e-137">First select **Show all**.</span></span> 

2. <span data-ttu-id="8f64e-138">ウィザードでプロンプトに従います。</span><span class="sxs-lookup"><span data-stu-id="8f64e-138">Follow the prompts in the wizard.</span></span> <span data-ttu-id="8f64e-139">レコード管理を使用している場合:</span><span class="sxs-lookup"><span data-stu-id="8f64e-139">If you are using records management:</span></span>
    
    - <span data-ttu-id="8f64e-140">ファイル計画記述子については、「[Use file plan to manage retention labels (ファイル計画を使用して保持ラベルを管理する)](file-plan-manager.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f64e-140">For information about the file plan descriptors, see [Use file plan to manage retention labels](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="8f64e-141">保持ラベルを使用してコンテンツをレコードとして宣言するには、[**このラベルを使用して、コンテンツを「レコード」に分類する**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="8f64e-141">To use the retention label to declare content as a record, enable the checkbox **Use label to classify content as a "Record"**.</span></span>

<span data-ttu-id="8f64e-142">既存のラベルを編集するには、そのラベルを選択してから [**ラベルの編集**] を選択し、手順 2 からラベルの説明や[有効な設定](#updating-retention-labels-and-their-policies)を変更するための同じウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="8f64e-142">To edit an existing label, select it, and then select **Edit label** to start the same wizard that lets you change the label descriptions and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span> <span data-ttu-id="8f64e-143">または、使用可能な **[編集]** オプションのいずれかを選択して、関連するページに直接アクセスして更新を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="8f64e-143">Alternatively, select any of the available **Edit** options to go directly to the relevant page to make your update.</span></span>


### <a name="step-2-create-an-auto-apply-policy"></a><span data-ttu-id="8f64e-144">手順 2: 自動適用ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="8f64e-144">Step 2: Create an auto-apply policy</span></span>

<span data-ttu-id="8f64e-145">自動適用ポリシーを作成する場合、指定した条件に基づいてコンテンツに自動的に適用する保持ラベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="8f64e-145">When you create an auto-apply policy, you select a retention label to automatically apply to content, based on the conditions that you specify.</span></span>

1. <span data-ttu-id="8f64e-146">[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)で、次のいずれかの場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="8f64e-146">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="8f64e-147">レコード管理を使用している場合: **情報ガバナンス**:</span><span class="sxs-lookup"><span data-stu-id="8f64e-147">If you are using records management: **Information governance**:</span></span>
        - <span data-ttu-id="8f64e-148">[**ソリューション**] > [**レコード管理**] > [**ラベル ポリシー**] タブ > [**自動適用ラベル**]</span><span class="sxs-lookup"><span data-stu-id="8f64e-148">**Solutions** > **Records management** > **Label policies** tab > **Auto-apply label**</span></span>
    
    - <span data-ttu-id="8f64e-149">レコード管理を使用していない場合:</span><span class="sxs-lookup"><span data-stu-id="8f64e-149">If you are not using records management:</span></span>
        - <span data-ttu-id="8f64e-150">[**ソリューション**] > [**情報ガバナンス**] > [**ラベル ポリシー**] タブ > [**自動適用ラベル**]</span><span class="sxs-lookup"><span data-stu-id="8f64e-150">**Solutions** > **Information governance** > **Label policies** tab > **Auto-apply label**</span></span>
    
    <span data-ttu-id="8f64e-151">すぐにオプションが表示されませんか?</span><span class="sxs-lookup"><span data-stu-id="8f64e-151">Don't immediately see your option?</span></span> <span data-ttu-id="8f64e-152">最初に [**すべて表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f64e-152">First select **Show all**.</span></span> 

2. <span data-ttu-id="8f64e-153">ウィザードでプロンプトに従います。</span><span class="sxs-lookup"><span data-stu-id="8f64e-153">Follow the prompts in the wizard.</span></span>
    
    <span data-ttu-id="8f64e-154">保持ラベルを自動的に適用する条件の構成については、このページの「[自動適用の保持ラベルの条件の構成](#configuring-conditions-for-auto-apply-retention-labels)」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8f64e-154">For information about configuring the conditions that automatically apply the retention label, see the [Configuring conditions for auto-apply retention labels](#configuring-conditions-for-auto-apply-retention-labels) section on this page.</span></span>
    
    <span data-ttu-id="8f64e-155">保持ラベルでサポートされている場所については、「[保持ラベルと場所](retention.md#retention-label-policies-and-locations)」のセクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8f64e-155">For information about the locations supported by retention labels, see the [Retention labels and locations](retention.md#retention-label-policies-and-locations) section.</span></span>

<span data-ttu-id="8f64e-156">既存の自動適用ラベル ポリシーを編集するには、そのラベルを選択してから [**ポリシーの編集**] を選択し、手順 2 からポリシーの説明や[有効な設定](#updating-retention-labels-and-their-policies)を変更するための同じウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="8f64e-156">To edit an existing auto-apply label policy, select it, and then select **Edit policy** to start the same wizard that lets you change the policy description and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span> <span data-ttu-id="8f64e-157">または、利用可能な**編集**オプションを選択して、関連するページに直接アクセスして更新を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="8f64e-157">Alternatively, select any of the available **Edit** options to go directly to the relevant page to make your update.</span></span>

### <a name="configuring-conditions-for-auto-apply-retention-labels"></a><span data-ttu-id="8f64e-158">自動適用の保持ラベルの条件の構成</span><span class="sxs-lookup"><span data-stu-id="8f64e-158">Configuring conditions for auto-apply retention labels</span></span>

<span data-ttu-id="8f64e-159">コンテンツに次の内容が含まれている場合は、保持ラベルを自動的にコンテンツに適用できます。</span><span class="sxs-lookup"><span data-stu-id="8f64e-159">You can apply retention labels to content automatically when that content contains:</span></span>

- [<span data-ttu-id="8f64e-160">特定の種類の機密情報</span><span class="sxs-lookup"><span data-stu-id="8f64e-160">Specific types of sensitive information</span></span>](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)

- [<span data-ttu-id="8f64e-161">作成したクエリに一致する特定のキーワード</span><span class="sxs-lookup"><span data-stu-id="8f64e-161">Specific keywords that match a query you create</span></span>](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [<span data-ttu-id="8f64e-162">トレーニング可能な分類子の一致</span><span class="sxs-lookup"><span data-stu-id="8f64e-162">A match for trainable classifiers</span></span>](#auto-apply-labels-to-content-by-using-trainable-classifiers)

#### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="8f64e-163">特定の種類の機密情報によるコンテンツへのラベルの自動適用</span><span class="sxs-lookup"><span data-stu-id="8f64e-163">Auto-apply labels to content with specific types of sensitive information</span></span>

<span data-ttu-id="8f64e-164">機密情報用に自動適用の保持ラベルを作成するときに、データ損失防止 (DLP) ポリシーを作成するときと同じポリシー テンプレートの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f64e-164">When you create auto-apply retention labels for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="8f64e-165">各ポリシー テンプレートは、特定の種類の機密情報を見つけるように事前に設定されています。</span><span class="sxs-lookup"><span data-stu-id="8f64e-165">Each policy template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="8f64e-166">たとえば、次に示すテンプレートは、米国の ITIN、SSN、パスポート番号を探します。</span><span class="sxs-lookup"><span data-stu-id="8f64e-166">For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers.</span></span> <span data-ttu-id="8f64e-167">DLP の詳細については、「[データ損失防止ポリシーの概要](data-loss-prevention-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f64e-167">To learn more about DLP, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
![機密情報の種類によるポリシー テンプレート](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)
  
<span data-ttu-id="8f64e-p112">ポリシー テンプレートを選択すると、すべての種類の機密情報を追加または削除したり、インスタンス数と一致精度を変更したりできます。ここに示す例では、保持ラベルは次の場合にのみ自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="8f64e-p112">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy. In the example shown here, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="8f64e-p113">コンテンツに、次の 3 種類の機密情報のいずれかに 1 から 9 個のインスタンスが含まれる場合。**最大** 値を削除して、**任意** の値に変更できます。</span><span class="sxs-lookup"><span data-stu-id="8f64e-p113">The content contains between 1 and 9 instances of any of these three sensitive information types. You can delete the **max** value so that it changes to **any**.</span></span>
    
- <span data-ttu-id="8f64e-173">検出される機密情報の種類には、一致精度 (または信頼度) が少なくとも 75 はあります。</span><span class="sxs-lookup"><span data-stu-id="8f64e-173">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75.</span></span> <span data-ttu-id="8f64e-174">機密情報の種類の多くは、複数のパターンで定義されています。高い一致精度が指定されたパターンにはより多くの証拠 (キーワード、日付、アドレスなど) が見つかることが必要とされるのに対して、低い一致精度が指定されたパターンでは必要とされる証拠は少なくなります。</span><span class="sxs-lookup"><span data-stu-id="8f64e-174">Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence.</span></span> <span data-ttu-id="8f64e-175">**最小**一致精度が低いほど、コンテンツは条件に一致しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="8f64e-175">The lower the **min** match accuracy, the easier it is for content to match the condition.</span></span> 
    
<span data-ttu-id="8f64e-176">これらのオプションの詳細については、「[一致の難易度を設定するためのルールの調整](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8f64e-176">For more information on these options, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![機密情報の種類を識別するためのオプション](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
#### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="8f64e-178">キーワードまたは検索可能なプロパティによるコンテンツへの自動適用ラベル</span><span class="sxs-lookup"><span data-stu-id="8f64e-178">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="8f64e-p115">特定の条件を満たすコンテンツにラベルを自動的に適用できます。現在利用可能な条件では、特定の単語、フレーズ、または検索可能なプロパティの値を含むコンテンツへのラベルの適用がサポートされています。AND、OR、NOT などの検索演算子を使用してクエリを絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="8f64e-p115">You can auto-apply labels to content that satisfies certain conditions. The conditions now available support applying a label to content that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators like AND, OR, and NOT.</span></span>

<span data-ttu-id="8f64e-182">クエリ構文の詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f64e-182">For more information on query syntax, see:</span></span>

- [<span data-ttu-id="8f64e-183">キーワード クエリ言語 (KQL) 構文のリファレンス</span><span class="sxs-lookup"><span data-stu-id="8f64e-183">Keyword Query Language (KQL) syntax reference</span></span>](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

<span data-ttu-id="8f64e-p116">クエリ ベースのラベルは検索インデックスを使用してコンテンツを特定します。有効な検索可能なプロパティの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f64e-p116">Query-based labels use the search index to identify content. For more information on valid searchable properties, see:</span></span>

- [<span data-ttu-id="8f64e-186">コンテンツ検索のキーワード クエリと検索条件</span><span class="sxs-lookup"><span data-stu-id="8f64e-186">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
- [<span data-ttu-id="8f64e-187">クロールされたプロパティと管理プロパティの概要 (SharePoint Server)</span><span class="sxs-lookup"><span data-stu-id="8f64e-187">Overview of crawled and managed properties in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

<span data-ttu-id="8f64e-188">クエリの例:</span><span class="sxs-lookup"><span data-stu-id="8f64e-188">Examples queries:</span></span>

- <span data-ttu-id="8f64e-189">Exchange</span><span class="sxs-lookup"><span data-stu-id="8f64e-189">Exchange</span></span>
    - <span data-ttu-id="8f64e-190">subject:"Quarterly Financials"</span><span class="sxs-lookup"><span data-stu-id="8f64e-190">subject:"Quarterly Financials"</span></span>
    - <span data-ttu-id="8f64e-191">受信者: garthf</span><span class="sxs-lookup"><span data-stu-id="8f64e-191">recipients:garthf</span></span><!--nolink--><span data-ttu-id="8f64e-192">@contoso.com</span><span class="sxs-lookup"><span data-stu-id="8f64e-192">@contoso.com</span></span>
- <span data-ttu-id="8f64e-193">SharePoint および OneDrive</span><span class="sxs-lookup"><span data-stu-id="8f64e-193">SharePoint and OneDrive</span></span>
    - <span data-ttu-id="8f64e-194">contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="8f64e-194">contenttype:contract</span></span>
    - <span data-ttu-id="8f64e-195">site:https</span><span class="sxs-lookup"><span data-stu-id="8f64e-195">site:https</span></span><!--nolink--><span data-ttu-id="8f64e-196">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="8f64e-196">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span></span>

![クエリ エディター](../media/ac5b8e5e-7453-4ec7-905c-160df57298d3.png)


#### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="8f64e-198">トレーニング可能な分類子を使用して、ラベルをコンテンツに自動的に適用する</span><span class="sxs-lookup"><span data-stu-id="8f64e-198">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="8f64e-199">トレーニング可能な分類子のオプションを選択すると、組み込み分類子またはカスタム分類子のいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="8f64e-199">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="8f64e-200">組み込み分類子には、**履歴書**、**ソース コード**、**個人を標的にしたハラスメント**、**冒とく**、および**脅威**が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8f64e-200">The built-in classifiers include **Resumes**, **SourceCode**, **Targeted Harassment**, **Profanity**, and **Threat**:</span></span>

![トレーニング可能な分類子の選択](../media/retention-label-classifers.png)

> [!CAUTION]
> <span data-ttu-id="8f64e-202">組み込みの [**不快な言葉**] は、誤検知の数が多いため、廃止予定です。</span><span class="sxs-lookup"><span data-stu-id="8f64e-202">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="8f64e-203">この組み込み分類子を使用しないでください。現在使用している場合は、ビジネス プロセスを移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f64e-203">Don't use this built-in classifier and if you are currently using it, you should move your business processes off it.</span></span> <span data-ttu-id="8f64e-204">代わりに、[**個人を標的にしたハラスメント**]、[**冒涜的表現**]、および [**脅威**] の組み込み分類子を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8f64e-204">We recommend using the **Targeted Harassment**, **Profanity**, and **Threat** built-in classifiers instead.</span></span>

<span data-ttu-id="8f64e-205">このオプションを使用してラベルを自動的に適用するには、SharePoint Online サイトとメールボックスには少なくとも 10 MB のデータが必要です。</span><span class="sxs-lookup"><span data-stu-id="8f64e-205">To automatically apply a label by using this option, SharePoint Online sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="8f64e-206">トレーニング可能な分類子の詳細については、「[トレーニング可能な分類子 (プレビュー) の概要](classifier-getting-started-with.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f64e-206">For more information about trainable classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="8f64e-207">構成の例については、「[組み込みの分類子を準備して使用する方法](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f64e-207">For an example configuration, see [How to prepare for and use a built-in classifier](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs).</span></span>

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="8f64e-208">保持ラベルが有効になるまでの所要時間</span><span class="sxs-lookup"><span data-stu-id="8f64e-208">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="8f64e-209">保持ラベルを自動適用する場合、条件に一致する既存のコンテンツすべてに保持ラベルが適用されるまでに最大 7 日間かかります。</span><span class="sxs-lookup"><span data-stu-id="8f64e-209">When you auto-apply retention labels, it can take up to seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![自動適用ラベルが有効になるタイミングの図](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
## <a name="updating-retention-labels-and-their-policies"></a><span data-ttu-id="8f64e-211">保持ラベルとそのポリシーの更新</span><span class="sxs-lookup"><span data-stu-id="8f64e-211">Updating retention labels and their policies</span></span>

<span data-ttu-id="8f64e-212">保持ラベルや自動適用ポリシーを編集すると、その保持ラベルが既にコンテンツに適用されている場合、新しく識別されるコンテンツに加えて、そのコンテンツにも更新された設定が自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="8f64e-212">When you edit a retention label or auto-apply policy, and the retention label is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly identified.</span></span>

<span data-ttu-id="8f64e-213">ラベルやポリシーを作成して保存した後には変更できない設定があり、それらは以下のものを含みます。</span><span class="sxs-lookup"><span data-stu-id="8f64e-213">Some settings can't be changed after the label or policy is created and saved, which include:</span></span>
- <span data-ttu-id="8f64e-214">作成日時に基づいてコンテンツを保持または削除するようにラベルを構成していない場合を除いた、保持期間以外の保持設定。</span><span class="sxs-lookup"><span data-stu-id="8f64e-214">The retention settings except the retention period, unless you've configured the label to retain or delete the content based on when it was created.</span></span>
- <span data-ttu-id="8f64e-215">レコードとして分類するオプション。</span><span class="sxs-lookup"><span data-stu-id="8f64e-215">The option to classify as a record.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8f64e-216">次の手順</span><span class="sxs-lookup"><span data-stu-id="8f64e-216">Next steps</span></span>

<span data-ttu-id="8f64e-217">別の形式のオートメーションである[イベント ベースの保持](event-driven-retention.md)による保持ラベルの使用を検討します。</span><span class="sxs-lookup"><span data-stu-id="8f64e-217">Consider using retention labels with another form of automation, [event-driven retention](event-driven-retention.md).</span></span> <span data-ttu-id="8f64e-218">この構成を使用すると、指定したイベントによって保持の開始がトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="8f64e-218">When you use this configuration, the start of retention is triggered by an event that you identify.</span></span> <span data-ttu-id="8f64e-219">イベント ベースの保持は、自動ポリシーやラベル ポリシーと組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="8f64e-219">You can use event-driven retention with an auto-policy or a label policy.</span></span>

<span data-ttu-id="8f64e-220">SharePont の管理プロパティを使用して保持ラベルを自動適用し、イベント ドリブンの保持を実装する詳細なシナリオについては、「[保持ラベルを使用して SharePoint ドキュメントのライフサイクルを管理する](auto-apply-retention-labels-scenario.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f64e-220">See [Manage the lifecycle of SharePoint documents with retention labels](auto-apply-retention-labels-scenario.md) for a detailed scenario about using managed properties in SharePoint to auto-apply retention labels and implement event-driven retention.</span></span>