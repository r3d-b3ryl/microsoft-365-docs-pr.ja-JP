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
description: 必要なものを保持し、必要でないものを削除するためにラベルを自動的に適用できるように、保持ラベルと自動ラベル付けポリシーを作成します。
ms.openlocfilehash: 34b6fb53095a2c3f52598b84e82cae3083b98f21
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423306"
---
# <a name="automatically-apply-a-retention-label-to-retain-or-delete-content"></a><span data-ttu-id="7a3cf-103">保持ラベルを自動的に適用してコンテンツを保持または削除する</span><span class="sxs-lookup"><span data-stu-id="7a3cf-103">Automatically apply a retention label to retain or delete content</span></span>

><span data-ttu-id="7a3cf-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="7a3cf-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

> [!NOTE]
> <span data-ttu-id="7a3cf-105">このシナリオは、[規制レコード](records-management.md#records)についてはサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-105">This scenario is not supported for [regulatory records](records-management.md#records).</span></span>

<span data-ttu-id="7a3cf-106">[保持ラベル](retention.md)の最も強力な機能の 1 つは、指定した条件に一致したコンテンツに自動的にラベルを適用することです。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-106">One of the most powerful features of [retention labels](retention.md) is the ability to apply them automatically to content that matches specified conditions.</span></span> <span data-ttu-id="7a3cf-107">この場合、組織内のユーザーが保持ラベルを適用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-107">In this case, people in your organization don't need to apply the retention labels.</span></span> <span data-ttu-id="7a3cf-108">Microsoft 365 が行います。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-108">Microsoft 365 does the work for them.</span></span>
  
<span data-ttu-id="7a3cf-109">自動適用アイテム保持ラベルが強力な機能である理由は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-109">Auto-applying retention labels are powerful because:</span></span>
  
- <span data-ttu-id="7a3cf-110">ユーザーのトレーニングは、一部の分類方法についてのみ必要。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-110">You don't need to train your users on all of your classifications.</span></span>
    
- <span data-ttu-id="7a3cf-111">ユーザーへの依存は、一部のコンテンツを正しく分類するためにのみ必要。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-111">You don't need to rely on users to classify all content correctly.</span></span>
    
- <span data-ttu-id="7a3cf-112">ユーザーはデータ ガバナンス ポリシーについて把握する必要がなくなるので、仕事に集中できる。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-112">Users no longer need to know about data governance policies - they can focus on their work.</span></span>
    
<span data-ttu-id="7a3cf-113">コンテンツに機密情報、キーワード、検索可能なプロパティ、または[トレーニング可能な分類子](classifier-get-started-with.md)のマッチが含まれている場合、保持ラベルをコンテンツに自動的に適用できます。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-113">You can apply retention labels to content automatically when that content contains sensitive information, keywords or searchable properties, or a match for [trainable classifiers](classifier-get-started-with.md).</span></span>

> [!TIP]
> <span data-ttu-id="7a3cf-114">プレビューでは、検索可能なプロパティを使用して [Teams 会議のレコーディング](#microsoft-teams-meeting-recordings)を特定できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-114">Now in preview, use searchable properties to identify [Teams meeting recordings](#microsoft-teams-meeting-recordings).</span></span>

<span data-ttu-id="7a3cf-115">保持ラベルを自動的に適用するプロセスは、次の条件に基づいています。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-115">The processes to automatically apply a retention label based on these conditions:</span></span>

![自動適用ラベルの役割とタスクの図](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)

<span data-ttu-id="7a3cf-117">次の手順を 2 つの管理手順に使用します。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-117">Use the following instructions for the two admin steps.</span></span>

> [!NOTE]
> <span data-ttu-id="7a3cf-118">自動ポリシーで、保持ラベルを自動的に適用するための条件によりサービス側でのラベル付けを使用します。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-118">Auto-policies use service-side labeling with conditions to automatically apply retention labels.</span></span> <span data-ttu-id="7a3cf-119">次の操作を行うときにラベル ポリシーを使用して保持ラベルを自動的に適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-119">You can also automatically apply a retention label with a label policy when you do the following:</span></span> 
>
> - <span data-ttu-id="7a3cf-120">SharePoint Syntex のドキュメント理解モデルに保持ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="7a3cf-120">Apply a retention label to a document understanding model in SharePoint Syntex</span></span>
> - <span data-ttu-id="7a3cf-121">SharePoint と Outlook の既定の保持ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="7a3cf-121">Apply a default retention label for SharePoint and Outlook</span></span>
>- <span data-ttu-id="7a3cf-122">Outlook ルールを使用してメールに保持ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="7a3cf-122">Apply a retention label to email by using Outlook rules</span></span>
>
> <span data-ttu-id="7a3cf-123">これらのシナリオについては、[アイテム保持ラベルを作成してアプリに適用する](create-apply-retention-labels.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-123">For these scenarios, see [Create and apply retention labels in apps](create-apply-retention-labels.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7a3cf-124">はじめに</span><span class="sxs-lookup"><span data-stu-id="7a3cf-124">Before you begin</span></span>

<span data-ttu-id="7a3cf-125">組織のグローバル管理者には、保持ラベルとそれらのポリシーを作成および編集できる完全な権限があります。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-125">The global admin for your organization has full permissions to create and edit retention labels and their policies.</span></span> <span data-ttu-id="7a3cf-126">グローバル管理者としてサインインしていない場合は、「[アイテム保持ポリシーと保持ラベルを作成して管理するために必要なアクセス許可](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-126">If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="how-to-auto-apply-a-retention-label"></a><span data-ttu-id="7a3cf-127">保持ラベルを自動適用する方法</span><span class="sxs-lookup"><span data-stu-id="7a3cf-127">How to auto-apply a retention label</span></span>

<span data-ttu-id="7a3cf-128">まず、保持ラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-128">First, create your retention label.</span></span> <span data-ttu-id="7a3cf-129">次に、そのラベルを適用する自動ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-129">Then create an auto-policy to apply that label.</span></span> <span data-ttu-id="7a3cf-130">保持ラベルを既に作成してある場合は、[自動ポリシーの作成](#step-2-create-an-auto-apply-policy)に進んでください。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-130">If you have already created your retention label, skip to [creating an auto-policy](#step-2-create-an-auto-apply-policy).</span></span>

<span data-ttu-id="7a3cf-131">ナビゲーション手順は、[レコード管理](records-management.md)を使用しているかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-131">Navigation instructions depend on whether you're using [records management](records-management.md) or not.</span></span> <span data-ttu-id="7a3cf-132">両方のシナリオの手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-132">Instructions are provided for both scenarios.</span></span>

### <a name="step-1-create-a-retention-label"></a><span data-ttu-id="7a3cf-133">手順 1: 保持ラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="7a3cf-133">Step 1: Create a retention label</span></span>

1. <span data-ttu-id="7a3cf-134">[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)で、次のいずれかの場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-134">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="7a3cf-135">レコード管理を使用している場合:</span><span class="sxs-lookup"><span data-stu-id="7a3cf-135">If you are using records management:</span></span>
        - <span data-ttu-id="7a3cf-136">[**ソリューション**] > [**レコード管理**] > [**ファイル計画**] タブ > [**+ラベルを作成**] > [**保持ラベル**]</span><span class="sxs-lookup"><span data-stu-id="7a3cf-136">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="7a3cf-137">レコード管理を使用していない場合:</span><span class="sxs-lookup"><span data-stu-id="7a3cf-137">If you are not using records management:</span></span>
       - <span data-ttu-id="7a3cf-138">[**ソリューション**] > [**情報ガバナンス**] > [**ラベル**] タブ > + [**ラベルを作成**]</span><span class="sxs-lookup"><span data-stu-id="7a3cf-138">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="7a3cf-139">すぐにオプションが表示されませんか?</span><span class="sxs-lookup"><span data-stu-id="7a3cf-139">Don't immediately see your option?</span></span> <span data-ttu-id="7a3cf-140">最初に [**すべて表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-140">First select **Show all**.</span></span> 

2. <span data-ttu-id="7a3cf-141">ウィザードでプロンプトに従います。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-141">Follow the prompts in the wizard.</span></span> <span data-ttu-id="7a3cf-142">レコード管理を使用している場合:</span><span class="sxs-lookup"><span data-stu-id="7a3cf-142">If you are using records management:</span></span>
    
    - <span data-ttu-id="7a3cf-143">ファイル計画記述子については、「[Use file plan to manage retention labels (ファイル計画を使用して保持ラベルを管理する)](file-plan-manager.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-143">For information about the file plan descriptors, see [Use file plan to manage retention labels](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="7a3cf-144">保持ラベルを使用してレコードを宣言するには、**アイテムをレコードとしてマーク**、または **アイテムを規制レコードとしてマーク** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-144">To use the retention label to declare records, select **Mark items as records**, or **Mark items as regulatory records**.</span></span> <span data-ttu-id="7a3cf-145">詳細については、「 [保持ラベルを構成してレコードを宣言する](declare-records.md#configuring-retention-labels-to-declare-records)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-145">For more information, see [Configuring retention labels to declare records](declare-records.md#configuring-retention-labels-to-declare-records).</span></span>

3. <span data-ttu-id="7a3cf-146">ラベルを作成し、ラベルの公開、ラベルの自動適用、またはラベルの保存のオプションが表示されたら、[**このラベルを特定の種類のコンテンツに自動適用する**] を選択してから、[**完了**] を選択すると、次の手順の手順 2 に直接進む自動ラベル作成ウィザードが起動します。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-146">After you have created the label and you see the options to publish the label, auto-apply the label, or just save the label: Select **Auto-apply this label to a specific type of content**, and then select **Done** to start the Create auto-labeling wizard that takes you directly to step 2 in the following procedure.</span></span>

<span data-ttu-id="7a3cf-147">既存のラベルを編集するには、そのラベルを選択してから [**ラベルの編集**] オプションを選択し、手順 2 からラベルの説明や [有効な設定](#updating-retention-labels-and-their-policies)を変更するための保持の編集ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-147">To edit an existing label, select it, and then select the **Edit label** option to start the Edit retention wizard that lets you change the label descriptions and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>

### <a name="step-2-create-an-auto-apply-policy"></a><span data-ttu-id="7a3cf-148">手順 2: 自動適用ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="7a3cf-148">Step 2: Create an auto-apply policy</span></span>

<span data-ttu-id="7a3cf-149">自動適用ポリシーを作成する場合、指定した条件に基づいてコンテンツに自動的に適用する保持ラベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-149">When you create an auto-apply policy, you select a retention label to automatically apply to content, based on the conditions that you specify.</span></span>

1. <span data-ttu-id="7a3cf-150">[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)で、次のいずれかの場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-150">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="7a3cf-151">レコード管理を使用している場合: **情報ガバナンス**:</span><span class="sxs-lookup"><span data-stu-id="7a3cf-151">If you are using records management: **Information governance**:</span></span>
        - <span data-ttu-id="7a3cf-152">[**ソリューション**] > [**レコード管理**] > [**ラベル ポリシー**] タブ > [**自動適用ラベル**]</span><span class="sxs-lookup"><span data-stu-id="7a3cf-152">**Solutions** > **Records management** > **Label policies** tab > **Auto-apply a label**</span></span>
    
    - <span data-ttu-id="7a3cf-153">レコード管理を使用していない場合:</span><span class="sxs-lookup"><span data-stu-id="7a3cf-153">If you are not using records management:</span></span>
        - <span data-ttu-id="7a3cf-154">[**ソリューション**] > [**情報ガバナンス**] > [**ラベル ポリシー**] タブ > [**自動適用ラベル**]</span><span class="sxs-lookup"><span data-stu-id="7a3cf-154">**Solutions** > **Information governance** > **Label policies** tab > **Auto-apply a label**</span></span>
    
    <span data-ttu-id="7a3cf-155">すぐにオプションが表示されませんか?</span><span class="sxs-lookup"><span data-stu-id="7a3cf-155">Don't immediately see your option?</span></span> <span data-ttu-id="7a3cf-156">最初に [**すべて表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-156">First select **Show all**.</span></span> 

2. <span data-ttu-id="7a3cf-157">自動ラベル作成ウィザードの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-157">Follow the prompts in the Create auto-labeling wizard.</span></span>
    
    <span data-ttu-id="7a3cf-158">保持ラベルを自動的に適用する条件の構成については、このページの「[自動適用の保持ラベルの条件の構成](#configuring-conditions-for-auto-apply-retention-labels)」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-158">For information about configuring the conditions that automatically apply the retention label, see the [Configuring conditions for auto-apply retention labels](#configuring-conditions-for-auto-apply-retention-labels) section on this page.</span></span>
    
    <span data-ttu-id="7a3cf-159">保持ラベルでサポートされている場所については、「[保持ラベルと場所](retention.md#retention-label-policies-and-locations)」のセクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-159">For information about the locations supported by retention labels, see the [Retention labels and locations](retention.md#retention-label-policies-and-locations) section.</span></span>

<span data-ttu-id="7a3cf-160">既存の自動適用ポリシーを編集するには、ポリシーを選択して、アイテム保持ポリシーの編集ウィザードを起動します。このウィザードでは、手順 2 で選択した保持ラベルと[有効な設定](#updating-retention-labels-and-their-policies)を変更できます。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-160">To edit an existing auto-apply policy, select it to start the Edit retention policy wizard that lets you change the selected retention label and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>

<span data-ttu-id="7a3cf-161">自動適用ラベル ポリシーを使用してコンテンツにラベル付けをした後で、コンテンツやポリシーを変更したり、新しい自動適用ラベル ポリシーを使用したりして、適用されているラベルを自動的に削除したり変更したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-161">After content is labeled by using an auto-apply label policy, the applied label can't be automatically removed or changed by changing the content or the policy, or by a new auto-apply label policy.</span></span> <span data-ttu-id="7a3cf-162">詳細については、「[一度に 1 つの保持ラベルのみ](retention.md#only-one-retention-label-at-a-time)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-162">For more information, see [Only one retention label at a time](retention.md#only-one-retention-label-at-a-time).</span></span>

### <a name="configuring-conditions-for-auto-apply-retention-labels"></a><span data-ttu-id="7a3cf-163">自動適用の保持ラベルの条件の構成</span><span class="sxs-lookup"><span data-stu-id="7a3cf-163">Configuring conditions for auto-apply retention labels</span></span>

<span data-ttu-id="7a3cf-164">コンテンツに次の内容が含まれている場合は、保持ラベルを自動的にコンテンツに適用できます。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-164">You can apply retention labels to content automatically when that content contains:</span></span>

- [<span data-ttu-id="7a3cf-165">特定の種類の機密情報</span><span class="sxs-lookup"><span data-stu-id="7a3cf-165">Specific types of sensitive information</span></span>](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)

- [<span data-ttu-id="7a3cf-166">作成したクエリに一致する特定のキーワードまたは検索可能なプロパティ</span><span class="sxs-lookup"><span data-stu-id="7a3cf-166">Specific keywords or searchable properties that match a query you create</span></span>](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [<span data-ttu-id="7a3cf-167">トレーニング可能な分類子の一致</span><span class="sxs-lookup"><span data-stu-id="7a3cf-167">A match for trainable classifiers</span></span>](#auto-apply-labels-to-content-by-using-trainable-classifiers)

#### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="7a3cf-168">特定の種類の機密情報によるコンテンツへのラベルの自動適用</span><span class="sxs-lookup"><span data-stu-id="7a3cf-168">Auto-apply labels to content with specific types of sensitive information</span></span>

> [!WARNING]
> <span data-ttu-id="7a3cf-169">現在、この構成には既知の制限があり、選択した機密情報タイプに一致する場合、ラベルのないすべてのメールに常に選択した保持ラベルが適用されます。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-169">This configuration currently has a known limitation where all unlabeled emails always have the selected retention label applied when there is a match for your chosen sensitive information types.</span></span> <span data-ttu-id="7a3cf-170">たとえば、自動適用ポリシーを特定のユーザーに限定したり、ポリシーに Exchange 以外の場所を選択したりしても、一致する場合は常にラベルのないメールにラベルが適用されます。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-170">For example, even if you scope your auto-apply policy to specific users, or select locations other than Exchange for the policy, the label is always applied to unlabeled emails when there is a match.</span></span>

<span data-ttu-id="7a3cf-171">機密情報用に自動適用の保持ラベル ポリシーを作成するときに、データ損失防止 (DLP) ポリシーを作成するときと同じポリシー テンプレートの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-171">When you create auto-apply retention label policies for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="7a3cf-172">各テンプレートは、特定の種類の機密情報を見つけるように事前に設定されています。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-172">Each template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="7a3cf-173">たとえば、ここに示されているテンプレートは、**プライバシー** カテゴリからの U.S. ITIN、SSN、パスポート番号、および **U.S 個人を特定できる情報 (PII) データ テンプレート** を検索します。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-173">For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers from the **Privacy** category, and **U.S Personally Identifiable Information (PII) Data** template:</span></span>

![機密情報の種類によるポリシー テンプレート](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)

<span data-ttu-id="7a3cf-175">機密情報の種類の詳細については、「[機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-175">To learn more about the sensitivity information types, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span>

<span data-ttu-id="7a3cf-176">ポリシー テンプレートを選択すると、機密情報の任意の種類を追加または削除できます。また、インスタンス数や一致精度を変更できます。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-176">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy.</span></span> <span data-ttu-id="7a3cf-177">次に示すスクリーンショットの例では、保持ラベルは次の場合にのみ自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-177">In the example screenshot shown next, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="7a3cf-178">検出される機密情報の種類には、一致精度 (または信頼度) が少なくとも 75 はあります。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-178">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75.</span></span> <span data-ttu-id="7a3cf-179">機密情報の種類の多くは、複数のパターンで定義されています。高い一致精度が指定されたパターンにはより多くの証拠 (キーワード、日付、アドレスなど) が見つかることが必要とされるのに対して、低い一致精度が指定されたパターンでは必要とされる証拠は少なくなります。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-179">Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence.</span></span> <span data-ttu-id="7a3cf-180">**最小** 一致精度が低いほど、コンテンツは条件に一致しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-180">The lower the **min** match accuracy, the easier it is for content to match the condition.</span></span>

- <span data-ttu-id="7a3cf-181">3 種類の機密情報のうち、1 から 9 個のインスタンスを含むコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-181">The content contains between 1 and 9 instances of any of these three sensitive information types.</span></span> <span data-ttu-id="7a3cf-182">**宛先** 値を削除すると、値は **任意** に変更されます。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-182">You can delete the **to** value so that it changes to **Any**.</span></span>

<span data-ttu-id="7a3cf-183">これらのオプションの詳細については、DLP のドキュメント「[一致の難易度を上下するためにルールを調整する](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)」にある次のガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-183">For more information about these options, see the following guidance from the DLP documentation [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![機密情報の種類を識別するためのオプション](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)

<span data-ttu-id="7a3cf-185">機密情報の種類を使用して保持ラベルの自動適用を検討する場合:</span><span class="sxs-lookup"><span data-stu-id="7a3cf-185">To consider when using sensitive information types to auto-apply retention labels:</span></span>

- <span data-ttu-id="7a3cf-186">新しいアイテムや変更されたアイテムには、自動的にラベルを付けることができます。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-186">New and modified items can be auto-labeled.</span></span>

#### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="7a3cf-187">キーワードまたは検索可能なプロパティによるコンテンツへの自動適用ラベル</span><span class="sxs-lookup"><span data-stu-id="7a3cf-187">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="7a3cf-p116">特定の単語、フレーズ、または検索可能なプロパティの値を含むクエリを使用して、コンテンツにラベルを自動で適用できます。AND、OR、NOT などの検索演算子を使用してクエリを絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-p116">You can auto-apply labels to content by using a query that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators such as AND, OR, and NOT.</span></span>

![クエリ エディター](../media/new-retention-query-editor.png)

<span data-ttu-id="7a3cf-191">キーワード クエリ言語 (KQL) 構文の詳細については、「[キーワード クエリ言語 (KQL) 構文のリファレンス](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-191">For more information about the query syntax that uses Keyword Query Language (KQL), see [Keyword Query Language (KQL) syntax reference](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).</span></span>

<span data-ttu-id="7a3cf-192">クエリ ベースの自動適用ポリシーは、電子情報開示コンテンツの検索と同じ検索インデックスを使用してコンテンツを識別します。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-192">Query-based auto-apply policies use the same search index as eDiscovery content search to identify content.</span></span> <span data-ttu-id="7a3cf-193">使用できる検索可能なプロパティの詳細については、「[キーワード クエリとコンテンツ検索の検索条件](keyword-queries-and-search-conditions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-193">For more information about the searchable properties that you can use, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>

<span data-ttu-id="7a3cf-194">キーワードまたは検索可能なプロパティを使用して保持ラベルを自動適用する際の考慮事項:</span><span class="sxs-lookup"><span data-stu-id="7a3cf-194">Some things to consider when using keywords or searchable properties to auto-apply retention labels:</span></span>

- <span data-ttu-id="7a3cf-195">新規、変更、および既存のアイテムには、SharePoint、OneDrive、および Exchange の自動ラベルが付けられます。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-195">New, modified, and existing items will be auto-labeled for SharePoint, OneDrive, and Exchange.</span></span>

- <span data-ttu-id="7a3cf-196">SharePoint の場合、クロールされたプロパティとカスタム プロパティは、これらの KQL クエリではサポートされていないため、事前定義された管理プロパティのみを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-196">For SharePoint, crawled properties and custom properties aren't supported for these KQL queries and you must use only predefined managed properties.</span></span> <span data-ttu-id="7a3cf-197">ただし、既定で絞り込み条件として有効になっている管理プロパティ (RefinableDate00-19、RefinableString00-99、RefinableInt00-49、RefinableDecimals00-09、および RefinableDouble00-09) を使用して、テナント レベルでマッピングを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-197">However, you can use mappings at the tenant level with the predefined managed properties that are enabled as refiners by default (RefinableDate00-19, RefinableString00-99, RefinableInt00-49, RefinableDecimals00-09, and RefinableDouble00-09).</span></span> <span data-ttu-id="7a3cf-198">詳細については、「[クロールされたプロパティと管理プロパティの概要 (SharePoint Server)](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)」を参照してください。手順については、「[新しい管理プロパティの作成](https://docs.microsoft.com/sharepoint/manage-search-schema#create-a-new-managed-property)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-198">For more information, see [Overview of crawled and managed properties in SharePoint Server](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview), and for instructions, see [Create a new managed property](https://docs.microsoft.com/sharepoint/manage-search-schema#create-a-new-managed-property).</span></span>

- <span data-ttu-id="7a3cf-199">カスタム プロパティを絞り込み条件プロパティの 1 つにマップする場合は、24 時間待ってから、保持ラベルの KQL クエリで使用してください。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-199">If you map a custom property to one of the refiner properties, wait 24 hours before you use it in your KQL query for a retention label.</span></span>

- <span data-ttu-id="7a3cf-200">SharePoint の管理プロパティはエイリアスを使用して名前を変更できますが、ラベルの KQL クエリにはこれらを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-200">Although SharePoint managed properties can be renamed by using aliases, don't use these for KQL queries in your labels.</span></span> <span data-ttu-id="7a3cf-201">「RefinableString01」のように、管理プロパティの実際の名前を常に指定します。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-201">Always specify the actual name of the managed property, for example, "RefinableString01".</span></span>

- <span data-ttu-id="7a3cf-202">スペースまたは特殊文字を含む値を検索するには、二重引用符 (`subject:"Financial Statements"`) で語句を囲みます。例: `" "`</span><span class="sxs-lookup"><span data-stu-id="7a3cf-202">To search for values that contain spaces or special characters, use double quotation marks (`" "`) to contain the phrase; for example, `subject:"Financial Statements"`.</span></span>

- <span data-ttu-id="7a3cf-203">*Path* の代わりに *DocumentLink* プロパティを使用して、URL に基​​づいてアイテムを照合します。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-203">Use the *DocumentLink* property instead of *Path* to match an item based on its URL.</span></span> 

- <span data-ttu-id="7a3cf-204">後方一致ワイルドカード検索 (`*cat` など) や部分文字列ワイルドカード検索 (`*cat*` など) はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-204">Suffix wildcard searches ( such as `*cat`) or substring wildcard searches (such as `*cat*`) aren't supported.</span></span> <span data-ttu-id="7a3cf-205">ただし、プレフィックス ワイルドカード検索 (`cat*` など) はサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-205">However, prefix wildcard searches (such as `cat*`) are supported.</span></span>

- <span data-ttu-id="7a3cf-206">部分的にインデックス付けされたアイテムは、想定するアイテムにラベルを付けない、または NOT 演算子を使用するときにラベル付けから除外されると想定するアイテムにラベルを付ける責任があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-206">Be aware that partially indexed items can be responsible for not labeling items that you're expecting, or labeling items that you're expecting to be excluded from labeling when you use the NOT operator.</span></span> <span data-ttu-id="7a3cf-207">詳細については、「[コンテンツ検索で部分的にインデックスが作成されたアイテム](partially-indexed-items-in-content-search.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-207">For more information, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>


<span data-ttu-id="7a3cf-208">クエリの例:</span><span class="sxs-lookup"><span data-stu-id="7a3cf-208">Examples queries:</span></span>

| <span data-ttu-id="7a3cf-209">Workload</span><span class="sxs-lookup"><span data-stu-id="7a3cf-209">Workload</span></span> | <span data-ttu-id="7a3cf-210">例</span><span class="sxs-lookup"><span data-stu-id="7a3cf-210">Example</span></span> |
|:-----|:-----|
|<span data-ttu-id="7a3cf-211">Exchange</span><span class="sxs-lookup"><span data-stu-id="7a3cf-211">Exchange</span></span>   | `subject:"Financial Statements"` |
|<span data-ttu-id="7a3cf-212">Exchange</span><span class="sxs-lookup"><span data-stu-id="7a3cf-212">Exchange</span></span>   | `recipients:garthf@contoso.com` |
|<span data-ttu-id="7a3cf-213">SharePoint</span><span class="sxs-lookup"><span data-stu-id="7a3cf-213">SharePoint</span></span> | `contenttype:document` |
|<span data-ttu-id="7a3cf-214">SharePoint</span><span class="sxs-lookup"><span data-stu-id="7a3cf-214">SharePoint</span></span> | `site:https://contoso.sharepoint.com/sites/teams/procurement AND contenttype:document`|
|<span data-ttu-id="7a3cf-215">Exchange または SharePoint</span><span class="sxs-lookup"><span data-stu-id="7a3cf-215">Exchange or SharePoint</span></span> | `"customer information" OR "private"`|

<span data-ttu-id="7a3cf-216">より複雑な例:</span><span class="sxs-lookup"><span data-stu-id="7a3cf-216">More complex examples:</span></span>

<span data-ttu-id="7a3cf-217">次の SharePoint のクエリは、Word 文書または Excel スプレッドシートが、キーワード **password**、**passwords**、または **pw** を含む場合に、それらを識別します。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-217">The following query for SharePoint identifies Word documents or Excel spreadsheets when those files contain the keywords **password**, **passwords**, or **pw**:</span></span>

```
(password OR passwords OR pw) AND (filetype:doc* OR filetype:xls*)
```

<span data-ttu-id="7a3cf-218">次の Exchange のクエリは、単語 **nda** またはフレーズ **秘密保持契約書** を含む Word 文書または PDF を、それらの文書がメールに添付されている場合に識別します。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-218">The following query for Exchange identifies any Word document or PDF that contains the word **nda** or the phrase **non disclosure agreement** when those documents are attached to an email:</span></span>

```
(nda OR "non disclosure agreement") AND (attachmentnames:.doc* OR attachmentnames:.pdf)
```

<span data-ttu-id="7a3cf-219">次の SharePoint のクエリは、クレジット カード番号を含むドキュメントを識別します。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-219">The following query for SharePoint identifies documents that contain a credit card number:</span></span> 

```
sensitivetype:"credit card number"
```

<span data-ttu-id="7a3cf-220">次のクエリには、合法的なコンテンツを含むドキュメントまたはメールを識別するのに役立ついくつかの一般的なキーワードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-220">The following query contains some typical keywords to help identify documents or emails that contain legal content:</span></span>

```
ACP OR (Attorney Client Privilege*) OR (AC Privilege)
```

<span data-ttu-id="7a3cf-221">次のクエリには、人事用のドキュメントまたはメールを識別するのに役立つ一般的なキーワードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-221">The following query contains typical keywords to help identify documents or emails for human resources:</span></span> 

```
(resume AND staff AND employee AND salary AND recruitment AND candidate)
```

<span data-ttu-id="7a3cf-222">この最後の例では、キーワード間に常に演算子を含めるというベスト プラクティスを使用していることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-222">Note that this final example uses the best practice of always including  operators between keywords.</span></span> <span data-ttu-id="7a3cf-223">キーワード (または 2 つの property:value 式) 間のスペースは、AND を使用することと同じになります。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-223">A space between keywords (or two property:value expressions) is the same as using AND.</span></span> <span data-ttu-id="7a3cf-224">演算子を常に追加することで、このクエリの例では、キーワードを含むコンテンツではなく、これらのキーワードをすべて含むコンテンツのみを識別することが容易になります。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-224">By always adding operators, it's easier to see that this example query will identify only content that contains all these keywords, instead of content that contains any of the keywords.</span></span> <span data-ttu-id="7a3cf-225">キーワードのいずれかを含むコンテンツを識別する場合は、AND の代わりに OR を指定します。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-225">If your intention is to identify content that contains any of the keywords, specify OR instead of AND.</span></span> <span data-ttu-id="7a3cf-226">この例が示すように、常に演算子を指定すると、クエリを正しく解釈するのが容易になります。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-226">As this example shows, when you always specify the operators, it's easier to correctly interpret the query.</span></span> 

##### <a name="microsoft-teams-meeting-recordings"></a><span data-ttu-id="7a3cf-227">Microsoft Teams 会議のレコーディング</span><span class="sxs-lookup"><span data-stu-id="7a3cf-227">Microsoft Teams meeting recordings</span></span>

> [!NOTE]
> <span data-ttu-id="7a3cf-228">Teams 会議のレコーディングを保持したり削除したりする機能はプレビュー段階にあり、レコーディングを OneDrive や SharePoint に保存する前には機能しません。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-228">The ability to retain and delete Teams meeting recordings is in preview and won't work before recordings are saved to OneDrive or SharePoint.</span></span> <span data-ttu-id="7a3cf-229">詳細については、「[OneDrive for Business と SharePoint または Stream を使用して会議の記録を行う](https://docs.microsoft.com/MicrosoftTeams/tmr-meeting-recording-change)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-229">For more information, see [Use OneDrive for Business and SharePoint Online or Stream for meeting recordings](https://docs.microsoft.com/MicrosoftTeams/tmr-meeting-recording-change).</span></span>

<span data-ttu-id="7a3cf-230">ユーザーの OneDrive アカウントまたは SharePoint に保存されている Microsoft Teams 会議のレコーディングを特定するには、**キーワード クエリ エディター** で次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-230">To identify Microsoft Teams meeting recordings that are stored in users' OneDrive accounts or in SharePoint, specify the following for the **Keyword query editor**:</span></span>

``` 
ProgID:Media AND ProgID:Meeting
```

<span data-ttu-id="7a3cf-231">ほとんどの場合、会議のレコーディングは OneDrive に保存されます。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-231">Most of the time, meeting recordings are saved to OneDrive.</span></span> <span data-ttu-id="7a3cf-232">ただしチャネル会議については、SharePoint に保存されます。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-232">But for channel meetings, they are saved in SharePoint.</span></span>


#### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="7a3cf-233">トレーニング可能な分類子を使用して、ラベルをコンテンツに自動的に適用する</span><span class="sxs-lookup"><span data-stu-id="7a3cf-233">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="7a3cf-234">トレーニング可能な分類子のオプションを選択すると、組み込み分類子またはカスタム分類子のいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-234">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="7a3cf-235">組み込み分類子には、**履歴書**、**ソース コード**、**個人を標的にしたハラスメント**、**冒とく**、および **脅威** が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-235">The built-in classifiers include **Resumes**, **SourceCode**, **Targeted Harassment**, **Profanity**, and **Threat**:</span></span>

![トレーニング可能な分類子の選択](../media/retention-label-classifers.png)

> [!CAUTION]
> <span data-ttu-id="7a3cf-237">組み込みの [**不快な言葉**] は、誤検知の数が多いため、廃止予定です。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-237">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="7a3cf-238">この組み込み分類子を使用しないでください。現在使用している場合は、ビジネス プロセスを移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-238">Don't use this built-in classifier and if you are currently using it, you should move your business processes off it.</span></span> <span data-ttu-id="7a3cf-239">代わりに、[**個人を標的にしたハラスメント**]、[**冒涜的表現**]、および [**脅威**] の組み込み分類子を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-239">We recommend using the **Targeted Harassment**, **Profanity**, and **Threat** built-in classifiers instead.</span></span>

<span data-ttu-id="7a3cf-240">このオプションを使用してラベルを自動的に適用するには、SharePoint サイトとメールボックスには少なくとも 10 MB のデータが必要です。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-240">To automatically apply a label by using this option, SharePoint sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="7a3cf-241">トレーニング可能な分類子の詳細については、「[トレーニング可能な分類子の詳細 (プレビュー)](classifier-learn-about.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-241">For more information about trainable classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

> [!TIP]
> <span data-ttu-id="7a3cf-242">Exchange でトレーニング可能な分類子を使用している場合は、「[コンテンツ エクスプローラーで分類子を再トレーニングする方法 (プレビュー)](classifier-how-to-retrain-content-explorer.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-242">If you use trainable classifiers for Exchange, see [How to retrain a classifier in content explorer](classifier-how-to-retrain-content-explorer.md).</span></span>

<span data-ttu-id="7a3cf-243">トレーニング可能な分類子を使用して保持ラベルの自動適用を検討する場合:</span><span class="sxs-lookup"><span data-stu-id="7a3cf-243">To consider when using trainable classifiers to auto-apply retention labels:</span></span>

- <span data-ttu-id="7a3cf-244">新規アイテムと変更されたアイテム、および過去 6 か月の既存のアイテムにはラベルを付けることができます。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-244">New and modified items can be auto-labeled, and existing items from the last six months.</span></span>

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="7a3cf-245">保持ラベルが有効になるまでの所要時間</span><span class="sxs-lookup"><span data-stu-id="7a3cf-245">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="7a3cf-246">保持ラベルを自動適用する場合、条件に一致する既存のコンテンツすべてに保持ラベルが適用されるまでに最大 7 日間かかります。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-246">When you auto-apply retention labels, it can take up to seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![自動適用ラベルが有効になるタイミングの図](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)

<span data-ttu-id="7a3cf-248">予期されるラベルが 7 日経っても表示されない場合は、コンプライアンス センターの **[ラベル ポリシー]** ページから選択して、自動適用ポリシーの **状態** を確認します。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-248">If the expected labels don't appear after seven days, check the **Status** of the auto-apply policy by selecting it from the **Label policies** page in the compliance center.</span></span> <span data-ttu-id="7a3cf-249">**オフ (エラー)** の状態が表示され、場所の詳細に、ポリシーの展開 (SharePoint の場合) またはポリシーの再展開 (OneDrive の場合) に予想よりも時間がかかっているというメッセージが表示される場合は、[Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy) PowerShell コマンドを実行して、ポリシーの配布を再試行してください:</span><span class="sxs-lookup"><span data-stu-id="7a3cf-249">If you see the status of **Off (Error)** and in the details for the locations see a message that it's taking longer than expected to deploy the policy (for SharePoint) or to try redeploying the policy (for OneDrive), try running the [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy) PowerShell command to retry the policy distribution:</span></span>

1. <span data-ttu-id="7a3cf-250">[セキュリティ/コンプライアンス センターの PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-250">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="7a3cf-251">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-251">Run the following command:</span></span>
    
    ``` PowerShell
    Set-RetentionCompliancePolicy -Identity <policy name> -RetryDistribution
   ```

## <a name="updating-retention-labels-and-their-policies"></a><span data-ttu-id="7a3cf-252">保持ラベルとそのポリシーの更新</span><span class="sxs-lookup"><span data-stu-id="7a3cf-252">Updating retention labels and their policies</span></span>

<span data-ttu-id="7a3cf-253">保持ラベルや自動適用ポリシーを編集すると、その保持ラベルが既にコンテンツに適用されている場合、新しく識別されるコンテンツに加えて、そのコンテンツにも更新された設定が自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-253">When you edit a retention label or auto-apply policy, and the retention label is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly identified.</span></span>

<span data-ttu-id="7a3cf-254">ラベルやポリシーを作成して保存した後には変更できない設定があり、それらは以下のものを含みます。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-254">Some settings can't be changed after the label or policy is created and saved, which include:</span></span>
- <span data-ttu-id="7a3cf-255">保持ラベル名とアイテム保持ポリシー名および保持期間を除く保持設定。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-255">The retention label and policy name, and the retention settings except the retention period.</span></span> <span data-ttu-id="7a3cf-256">ただし、アイテムにラベルが付けられた時期に基づいて保持期間が設定されている場合、保持期間を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-256">However, you can't change the retention period when the retention period is based on when items were labeled.</span></span>
- <span data-ttu-id="7a3cf-257">アイテムをレコードとしてマークするオプション。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-257">The option to mark items as a record.</span></span>

### <a name="deleting-retention-labels"></a><span data-ttu-id="7a3cf-258">保持ラベルの削除</span><span class="sxs-lookup"><span data-stu-id="7a3cf-258">Deleting retention labels</span></span>

<span data-ttu-id="7a3cf-259">どの保持ラベル ポリシーにも現在含まれていない保持ラベルや、イベントベースの保持用に構成されていない保持ラベルを削除したり、アイテムを規制レコードとしてマークしたりできます。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-259">You can delete retention labels that aren't currently included in any retention label policies, that aren't configured for event-based retention, or mark items as regulatory records.</span></span> <span data-ttu-id="7a3cf-260">アイテムをレコードとしてマークする保持ラベルを削除する機能は、現在プレビューで展開しています。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-260">The ability to delete retention labels that mark items as records is currently rolling out in preview.</span></span>

<span data-ttu-id="7a3cf-261">削除可能な保持ラベルについては、アイテムに適用されている場合、削除に失敗し、ラベル付きアイテムを識別するためのコンテンツ エクスプローラーへのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-261">For retention labels that you can delete, if they have been applied to items, the deletion fails and you see a link to content explorer to identify the labeled items.</span></span>

<span data-ttu-id="7a3cf-262">ただし、コンテンツ エクスプローラーにラベルが付いているアイテムが表示されるまでに最大 2 日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-262">However, it can take up to two days for content explorer to show the items that are labeled.</span></span> <span data-ttu-id="7a3cf-263">このシナリオでは、コンテンツ エクスプローラーへのリンクを表示せずに保持ラベルが削除されることがあります。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-263">In this scenario, the retention label might be deleted without showing you the link to content explorer.</span></span>

## <a name="locking-the-policy-to-prevent-changes"></a><span data-ttu-id="7a3cf-264">変更を防止するためにポリシーをロックする</span><span class="sxs-lookup"><span data-stu-id="7a3cf-264">Locking the policy to prevent changes</span></span>

<span data-ttu-id="7a3cf-265">ポリシーをオフにしたり、ポリシーを削除したり、制限を緩和したりすることができないようにする必要がある場合は、「[保管ロックを使用して、アイテム保持ポリシーと保持ラベル ポリシーへの変更を制限する](retention-preservation-lock.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-265">If you need to ensure that no one can turn off the policy, delete the policy, or make it less restrictive, see [Use Preservation Lock to restrict changes to retention policies and retention label policies](retention-preservation-lock.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="7a3cf-266">次の手順</span><span class="sxs-lookup"><span data-stu-id="7a3cf-266">Next steps</span></span>

<span data-ttu-id="7a3cf-267">[保持ラベルを使用して、SharePoint に保存されているドキュメントのライフサイクルを管理する](auto-apply-retention-labels-scenario.md)を参照してください。例として、SharePoint の管理プロパティで、自動適用ポリシー保持ラベルを使用し、保持期間を開始するために、イベントベースの保持を使用するというシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="7a3cf-267">See [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md) for an example scenario that uses an auto-apply retention label policy with managed properties in SharePoint, and event-based retention to start the retention period.</span></span>
