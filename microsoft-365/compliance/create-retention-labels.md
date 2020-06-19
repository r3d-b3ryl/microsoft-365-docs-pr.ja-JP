---
title: 保持ラベルを作成、発行、および自動適用する
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
description: 必要なものを保持し、不要なものを削除し、Office 365 環境でアイテムをレコードとして宣言するための、保持ラベルの作成、発行、および自動適用の手順。
ms.openlocfilehash: 035038c90179354e0497813326b1fdad01693bec
ms.sourcegitcommit: 589f78fc0f39aff9109959ded48d146cc32fc3c5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44761653"
---
# <a name="create-publish-and-auto-apply-retention-labels"></a><span data-ttu-id="1d462-103">保持ラベルを作成、発行、および自動適用する</span><span class="sxs-lookup"><span data-stu-id="1d462-103">Create, publish, and auto-apply retention labels</span></span>

><span data-ttu-id="1d462-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="1d462-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="1d462-105">次の情報を使用して、[保持ラベル](labels.md)を作成し、ドキュメントやメールに自動的に適用するか、ユーザーが手動で適用できるように公開します。</span><span class="sxs-lookup"><span data-stu-id="1d462-105">Use the following information to help you create [retention labels](labels.md), and then automatically apply them to documents and emails, or publish them so that users can manually apply them.</span></span>

<span data-ttu-id="1d462-106">保持ラベルは、必要なものを保持し、不要なものを削除するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1d462-106">Retention labels help you retain what you need and delete what you don't.</span></span> <span data-ttu-id="1d462-107">また、Microsoft 365 データの[レコード管理](records-management.md)ソリューションの一部として、アイテムをレコードとして宣言するためにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="1d462-107">They are also used to declare an item as a record as part of a [records management](records-management.md) solution for your Microsoft 365 data.</span></span>

<span data-ttu-id="1d462-108">保持ラベルを作成して構成する場所は、レコード管理を使用しているかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="1d462-108">Where you create and configure your retention labels depend on whether you're using records management or not.</span></span> <span data-ttu-id="1d462-109">手順は両方のシナリオに提供されます。</span><span class="sxs-lookup"><span data-stu-id="1d462-109">Instructions are provided for both scenarios.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="1d462-110">はじめに</span><span class="sxs-lookup"><span data-stu-id="1d462-110">Before you begin</span></span>

<span data-ttu-id="1d462-111">保持ラベルを作成するコンプライアンス チームのメンバーには、セキュリティ &amp; コンプライアンス センターにアクセスする許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="1d462-111">Members of your compliance team who will create retention labels need permissions to the Security &amp; Compliance Center.</span></span> <span data-ttu-id="1d462-112">テナント管理者は、規定でこの場所にアクセスできるため、法令遵守責任者や他のユーザーにセキュリティ &amp; コンプライアンス センターへのアクセス権を付与できます。テナント管理者が持つすべてのアクセス許可を付与する必要はありません。これを行うには、セキュリティ &amp; コンプライアンス センターの [**アクセス許可**] ページに移動して、[**コンプライアンス管理者**] 役割グループを編集し、その役割グループにメンバーを追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1d462-112">By default, your tenant admin has access to this location and can give compliance officers and other people access to the Security &amp; Compliance Center, without giving them all of the permissions of a tenant admin. To do this, we recommend that you go to the **Permissions** page of the Security &amp; Compliance Center, edit the **Compliance Administrator** role group, and add members to that role group.</span></span> 
  
<span data-ttu-id="1d462-113">詳細については、「[ユーザーに Office 365 セキュリティ センター/コンプライアンス センターへのアクセス権を付与する](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d462-113">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="1d462-114">These permissions are required only to create and apply retention labels and a label policy.</span><span class="sxs-lookup"><span data-stu-id="1d462-114">These permissions are required only to create and apply retention labels and a label policy.</span></span> <span data-ttu-id="1d462-115">Policy enforcement does not require access to the content.</span><span class="sxs-lookup"><span data-stu-id="1d462-115">Policy enforcement does not require access to the content.</span></span>

## <a name="create-and-configure-retention-labels"></a><span data-ttu-id="1d462-116">保持ラベルを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="1d462-116">Create and configure retention labels</span></span>

1. <span data-ttu-id="1d462-117">[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)で、次のいずれかの場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="1d462-117">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="1d462-118">レコード管理を使用している場合:</span><span class="sxs-lookup"><span data-stu-id="1d462-118">If you are using records management:</span></span>
        - <span data-ttu-id="1d462-119">[**ソリューション**] > [**レコード管理**] > [**ファイル計画**] タブ > [**+ラベルを作成**] > [**保持ラベル**]</span><span class="sxs-lookup"><span data-stu-id="1d462-119">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="1d462-120">レコード管理を使用していない場合:</span><span class="sxs-lookup"><span data-stu-id="1d462-120">If you are not using records management:</span></span>
       - <span data-ttu-id="1d462-121">[**ソリューション**] > [**情報ガバナンス**] > [**ラベル**] タブ > + [**ラベルを作成**]</span><span class="sxs-lookup"><span data-stu-id="1d462-121">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="1d462-122">すぐにオプションが表示されませんか?</span><span class="sxs-lookup"><span data-stu-id="1d462-122">Don't immediately see your option?</span></span> <span data-ttu-id="1d462-123">最初に [**すべて表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1d462-123">First select **Show all**.</span></span> 

2. <span data-ttu-id="1d462-124">ウィザードでプロンプトに従います。</span><span class="sxs-lookup"><span data-stu-id="1d462-124">Follow the prompts in the wizard.</span></span> <span data-ttu-id="1d462-125">レコード管理を使用している場合:</span><span class="sxs-lookup"><span data-stu-id="1d462-125">If you are using records management:</span></span>
    
    - <span data-ttu-id="1d462-126">ファイル計画記述子については、「[Use file plan to manage retention labels (ファイル計画を使用して保持ラベルを管理する)](file-plan-manager.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d462-126">For information about the file plan descriptors, see [Use file plan to manage retention labels](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="1d462-127">保持ラベルを使用してコンテンツをレコードとして宣言するには、[**このラベルを使用して、コンテンツを「レコード」に分類する**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="1d462-127">To use the retention label to declare content as a record, enable the checkbox **Use label to classify content as a "Record"**.</span></span>

3. <span data-ttu-id="1d462-128">さらにラベルを作成するには、これらの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="1d462-128">Repeat these steps to create more labels.</span></span>

<span data-ttu-id="1d462-129">既存のラベルを編集するには、そのラベルを選択してから [**ラベルの編集**] を選択し、手順 2 からラベルの説明や[有効な設定](#updating-retention-labels-and-their-policies)を変更するための同じウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="1d462-129">To edit an existing label, select it, and then select **Edit label** to start the same wizard that lets you change the label descriptions and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span> <span data-ttu-id="1d462-130">または、利用可能な**編集**オプションを選択して、関連するページに直接アクセスして更新を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="1d462-130">Alternatively, select any of the available **Edit** options to go directly to the relevant page to make your update.</span></span>

## <a name="publish-retention-labels-by-creating-a-retention-label-policy"></a><span data-ttu-id="1d462-131">保持ラベル ポリシーを作成して保持ラベルを発行する</span><span class="sxs-lookup"><span data-stu-id="1d462-131">Publish retention labels by creating a retention label policy</span></span>

<span data-ttu-id="1d462-132">保持ラベルを発行して、ユーザーが手動で適用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="1d462-132">Publish retention labels so that they can be manually applied by users.</span></span>

1. <span data-ttu-id="1d462-133">[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)で、次のいずれかの場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="1d462-133">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="1d462-134">レコード管理を使用している場合:</span><span class="sxs-lookup"><span data-stu-id="1d462-134">If you are using records management:</span></span>
        - <span data-ttu-id="1d462-135">[**ソリューション**] > [**レコード管理**] > [**ラベル ポリシー**] タブ > [**ラベルの発行**]</span><span class="sxs-lookup"><span data-stu-id="1d462-135">**Solutions** > **Records management** > > **Label policies** tab > **Publish labels**</span></span>
    
    - <span data-ttu-id="1d462-136">レコード管理を使用していない場合:</span><span class="sxs-lookup"><span data-stu-id="1d462-136">If you are not using records management:</span></span>
        - <span data-ttu-id="1d462-137">[**ソリューション**] > [**情報ガバナンス**] > [**ラベル ポリシー**] タブ > [**ラベルの発行**]</span><span class="sxs-lookup"><span data-stu-id="1d462-137">**Solutions** > **Information governance** > **Label policies** tab > **Publish labels**</span></span>
    
    <span data-ttu-id="1d462-138">すぐにオプションが表示されませんか?</span><span class="sxs-lookup"><span data-stu-id="1d462-138">Don't immediately see your option?</span></span> <span data-ttu-id="1d462-139">最初に [**すべて表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1d462-139">First select **Show all**.</span></span> 

2. <span data-ttu-id="1d462-140">ウィザードでプロンプトに従います。</span><span class="sxs-lookup"><span data-stu-id="1d462-140">Follow the prompts in the wizard.</span></span>
    
    <span data-ttu-id="1d462-141">保持ラベルでサポートされている場所については、「[保持ラベルと場所](labels.md#retention-label-policies-and-locations)」のセクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1d462-141">For information about the locations supported by retention labels, see the [Retention labels and locations](labels.md#retention-label-policies-and-locations) section.</span></span> 

<span data-ttu-id="1d462-142">既存の保持ラベル ポリシーを編集するには、そのラベルを選択してから [**ポリシーの編集**] を選択し、手順 2 からポリシーの説明や[有効な設定](#updating-retention-labels-and-their-policies)を変更するための同じウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="1d462-142">To edit an existing retention label policy, select it, and then select **Edit policy** to start the same wizard that lets you change the policy description and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span> <span data-ttu-id="1d462-143">または、利用可能な**編集**オプションを選択して、関連するページに直接アクセスして更新を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="1d462-143">Alternatively, select any of the available **Edit** options to go directly to the relevant page to make your update.</span></span>

## <a name="auto-apply-a-retention-label"></a><span data-ttu-id="1d462-144">自動適用の保持ラベル</span><span class="sxs-lookup"><span data-stu-id="1d462-144">Auto-apply a retention label</span></span>

<span data-ttu-id="1d462-145">指定した条件に基づいて、保持ラベルを自動的に適用します。</span><span class="sxs-lookup"><span data-stu-id="1d462-145">Auto-apply a retention label, based on the conditions that you specify.</span></span>

1. <span data-ttu-id="1d462-146">[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)で、次のいずれかの場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="1d462-146">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="1d462-147">レコード管理を使用している場合: **情報ガバナンス**:</span><span class="sxs-lookup"><span data-stu-id="1d462-147">If you are using records management: **Information governance**:</span></span>
        - <span data-ttu-id="1d462-148">[**ソリューション**] > [**レコード管理**] > [**ラベル ポリシー**] タブ > [**自動適用ラベル**]</span><span class="sxs-lookup"><span data-stu-id="1d462-148">**Solutions** > **Records management** > **Label policies** tab > **Auto-apply label**</span></span>
    
    - <span data-ttu-id="1d462-149">レコード管理を使用していない場合:</span><span class="sxs-lookup"><span data-stu-id="1d462-149">If you are not using records management:</span></span>
        - <span data-ttu-id="1d462-150">[**ソリューション**] > [**情報ガバナンス**] > [**ラベル ポリシー**] タブ > [**自動適用ラベル**]</span><span class="sxs-lookup"><span data-stu-id="1d462-150">**Solutions** > **Information governance** > **Label policies** tab > **Auto-apply label**</span></span>
    
    <span data-ttu-id="1d462-151">すぐにオプションが表示されませんか?</span><span class="sxs-lookup"><span data-stu-id="1d462-151">Don't immediately see your option?</span></span> <span data-ttu-id="1d462-152">最初に [**すべて表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1d462-152">First select **Show all**.</span></span> 

2. <span data-ttu-id="1d462-153">ウィザードでプロンプトに従います。</span><span class="sxs-lookup"><span data-stu-id="1d462-153">Follow the prompts in the wizard.</span></span>
    
    <span data-ttu-id="1d462-154">保持ラベルを自動的に適用する条件の構成については、このページの「[自動適用の保持ラベルの条件の構成](#configuring-conditions-for-auto-apply-retention-labels)」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1d462-154">For information about configuring the conditions that automatically apply the retention label, see the [Configuring conditions for auto-apply retention labels](#configuring-conditions-for-auto-apply-retention-labels) section on this page.</span></span>
    
    <span data-ttu-id="1d462-155">保持ラベルでサポートされている場所については、「[保持ラベルと場所](labels.md#retention-label-policies-and-locations)」のセクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1d462-155">For information about the locations supported by retention labels, see the [Retention labels and locations](labels.md#retention-label-policies-and-locations) section.</span></span>

<span data-ttu-id="1d462-156">既存の自動適用ラベル ポリシーを編集するには、そのラベルを選択してから [**ポリシーの編集**] を選択し、手順 2 からポリシーの説明や[有効な設定](#updating-retention-labels-and-their-policies)を変更するための同じウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="1d462-156">To edit an existing auto-apply label policy, select it, and then select **Edit policy** to start the same wizard that lets you change the policy description and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span> <span data-ttu-id="1d462-157">または、利用可能な**編集**オプションを選択して、関連するページに直接アクセスして更新を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="1d462-157">Alternatively, select any of the available **Edit** options to go directly to the relevant page to make your update.</span></span>


## <a name="configuring-conditions-for-auto-apply-retention-labels"></a><span data-ttu-id="1d462-158">自動適用の保持ラベルの条件の構成</span><span class="sxs-lookup"><span data-stu-id="1d462-158">Configuring conditions for auto-apply retention labels</span></span>

<span data-ttu-id="1d462-159">コンテンツに次の内容が含まれている場合は、保持ラベルを自動的にコンテンツに適用できます。</span><span class="sxs-lookup"><span data-stu-id="1d462-159">You can apply retention labels to content automatically when that content contains:</span></span>
  
- [<span data-ttu-id="1d462-160">特定の種類の機密情報</span><span class="sxs-lookup"><span data-stu-id="1d462-160">Specific types of sensitive information</span></span>](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)
    
- [<span data-ttu-id="1d462-161">作成したクエリに一致する特定のキーワード</span><span class="sxs-lookup"><span data-stu-id="1d462-161">Specific keywords that match a query you create</span></span>](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [<span data-ttu-id="1d462-162">トレーニング可能な分類子の一致</span><span class="sxs-lookup"><span data-stu-id="1d462-162">A match for trainable classifiers</span></span>](#auto-apply-labels-to-content-by-using-trainable-classifiers)
    
![自動適用ラベルの [条件選択] ページ](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)

<span data-ttu-id="1d462-164">構成した条件に一致するすべてのコンテンツに保持ラベルを自動的に適用するには、最大 7 日かかります。</span><span class="sxs-lookup"><span data-stu-id="1d462-164">It can take up to seven days for auto-apply retention labels to be applied to all content that matches the conditions you've configured.</span></span>

### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="1d462-165">特定の種類の機密情報によるコンテンツへのラベルの自動適用</span><span class="sxs-lookup"><span data-stu-id="1d462-165">Auto-apply labels to content with specific types of sensitive information</span></span>

<span data-ttu-id="1d462-166">機密情報用に自動適用の保持ラベルを作成するときに、データ損失防止 (DLP) ポリシーを作成するときと同じポリシー テンプレートの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1d462-166">When you create auto-apply retention labels for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="1d462-167">各ポリシー テンプレートは、特定の種類の機密情報を見つけるように事前に設定されています。</span><span class="sxs-lookup"><span data-stu-id="1d462-167">Each policy template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="1d462-168">たとえば、次に示すテンプレートは、米国の ITIN、SSN、パスポート番号を探します。</span><span class="sxs-lookup"><span data-stu-id="1d462-168">For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers.</span></span> <span data-ttu-id="1d462-169">DLP の詳細については、「[データ損失防止ポリシーの概要](data-loss-prevention-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d462-169">To learn more about DLP, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
![機密情報の種類によるポリシー テンプレート](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)
  
<span data-ttu-id="1d462-171">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy.</span><span class="sxs-lookup"><span data-stu-id="1d462-171">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy.</span></span> <span data-ttu-id="1d462-172">In the example shown here, a retention label will be auto-applied only when:</span><span class="sxs-lookup"><span data-stu-id="1d462-172">In the example shown here, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="1d462-173">The content contains between 1 and 9 instances of any of these three sensitive information types.</span><span class="sxs-lookup"><span data-stu-id="1d462-173">The content contains between 1 and 9 instances of any of these three sensitive information types.</span></span> <span data-ttu-id="1d462-174">You can delete the **max** value so that it changes to **any**.</span><span class="sxs-lookup"><span data-stu-id="1d462-174">You can delete the **max** value so that it changes to **any**.</span></span>
    
- <span data-ttu-id="1d462-175">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75.</span><span class="sxs-lookup"><span data-stu-id="1d462-175">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75.</span></span> <span data-ttu-id="1d462-176">Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence.</span><span class="sxs-lookup"><span data-stu-id="1d462-176">Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence.</span></span> <span data-ttu-id="1d462-177">Simply put, the lower the **min** match accuracy, the easier it is for content to match the condition.</span><span class="sxs-lookup"><span data-stu-id="1d462-177">Simply put, the lower the **min** match accuracy, the easier it is for content to match the condition.</span></span> 
    
<span data-ttu-id="1d462-178">これらのオプションの詳細については、「[一致の難易度を設定するためのルールの調整](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1d462-178">For more information on these options, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![機密情報の種類を識別するためのオプション](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="1d462-180">キーワードまたは検索可能なプロパティによるコンテンツへの自動適用ラベル</span><span class="sxs-lookup"><span data-stu-id="1d462-180">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="1d462-181">You can auto-apply labels to content that satisfies certain conditions.</span><span class="sxs-lookup"><span data-stu-id="1d462-181">You can auto-apply labels to content that satisfies certain conditions.</span></span> <span data-ttu-id="1d462-182">The conditions now available support applying a label to content that contains specific words, phrases, or values of searchable properties.</span><span class="sxs-lookup"><span data-stu-id="1d462-182">The conditions now available support applying a label to content that contains specific words, phrases, or values of searchable properties.</span></span> <span data-ttu-id="1d462-183">You can refine your query by using search operators like AND, OR, and NOT.</span><span class="sxs-lookup"><span data-stu-id="1d462-183">You can refine your query by using search operators like AND, OR, and NOT.</span></span>

<span data-ttu-id="1d462-184">クエリ構文の詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d462-184">For more information on query syntax, see:</span></span>

- [<span data-ttu-id="1d462-185">キーワード クエリ言語 (KQL) 構文のリファレンス</span><span class="sxs-lookup"><span data-stu-id="1d462-185">Keyword Query Language (KQL) syntax reference</span></span>](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

<span data-ttu-id="1d462-186">Query-based labels use the search index to identify content.</span><span class="sxs-lookup"><span data-stu-id="1d462-186">Query-based labels use the search index to identify content.</span></span> <span data-ttu-id="1d462-187">For more information on valid searchable properties, see:</span><span class="sxs-lookup"><span data-stu-id="1d462-187">For more information on valid searchable properties, see:</span></span>

- [<span data-ttu-id="1d462-188">コンテンツ検索のキーワード クエリと検索条件</span><span class="sxs-lookup"><span data-stu-id="1d462-188">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
- [<span data-ttu-id="1d462-189">クロールされたプロパティと管理プロパティの概要 (SharePoint Server)</span><span class="sxs-lookup"><span data-stu-id="1d462-189">Overview of crawled and managed properties in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

<span data-ttu-id="1d462-190">クエリの例:</span><span class="sxs-lookup"><span data-stu-id="1d462-190">Examples queries:</span></span>

- <span data-ttu-id="1d462-191">Exchange</span><span class="sxs-lookup"><span data-stu-id="1d462-191">Exchange</span></span>
    - <span data-ttu-id="1d462-192">subject:"Quarterly Financials"</span><span class="sxs-lookup"><span data-stu-id="1d462-192">subject:"Quarterly Financials"</span></span>
    - <span data-ttu-id="1d462-193">受信者: garthf</span><span class="sxs-lookup"><span data-stu-id="1d462-193">recipients:garthf</span></span><!--nolink--><span data-ttu-id="1d462-194">@contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d462-194">@contoso.com</span></span>
- <span data-ttu-id="1d462-195">SharePoint および OneDrive</span><span class="sxs-lookup"><span data-stu-id="1d462-195">SharePoint and OneDrive</span></span>
    - <span data-ttu-id="1d462-196">contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="1d462-196">contenttype:contract</span></span>
    - <span data-ttu-id="1d462-197">site:https</span><span class="sxs-lookup"><span data-stu-id="1d462-197">site:https</span></span><!--nolink--><span data-ttu-id="1d462-198">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="1d462-198">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span></span>

![クエリ エディター](../media/ac5b8e5e-7453-4ec7-905c-160df57298d3.png)


### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="1d462-200">トレーニング可能な分類子を使用して、ラベルをコンテンツに自動的に適用する</span><span class="sxs-lookup"><span data-stu-id="1d462-200">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="1d462-201">トレーニング可能な分類子のオプションを選択すると、組み込み分類子またはカスタム分類子のいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="1d462-201">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="1d462-202">組み込み分類子には、**履歴書**、**ソース コード**、**個人を標的にしたハラスメント**、**冒とく**、および**脅威**が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1d462-202">The built-in classifiers include **Resumes**, **SourceCode**, **Targeted Harassment**, **Profanity**, and **Threat**:</span></span>

![トレーニング可能な分類子の選択](../media/retention-label-classifers.png)

<span data-ttu-id="1d462-204">このオプションを使用してラベルを自動的に適用するには、SharePoint Online サイトとメールボックスには少なくとも 10 MB のデータが必要です。</span><span class="sxs-lookup"><span data-stu-id="1d462-204">To automatically apply a label by using this option, SharePoint Online sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="1d462-205">トレーニング可能な分類子の詳細については、「[トレーニング可能な分類子 (プレビュー) の概要](classifier-getting-started-with.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d462-205">For more information about trainable classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="1d462-206">構成の例については、「[組み込みの分類子を準備して使用する方法](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d462-206">For an example configuration, see [How to prepare for and use a built-in classifier](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs).</span></span>

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="1d462-207">保持ラベルが有効になるまでの所要時間</span><span class="sxs-lookup"><span data-stu-id="1d462-207">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="1d462-208">保持ラベルを発行または自動適用しても、すぐには有効になりません。</span><span class="sxs-lookup"><span data-stu-id="1d462-208">When you publish or auto-apply retention labels, they don't take effect immediately:</span></span>
  
1. <span data-ttu-id="1d462-209">まず、ラベル ポリシーを管理センターからポリシー内の場所に同期させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d462-209">First the label policy needs to be synced from the admin center to the locations in the policy.</span></span>
    
2. <span data-ttu-id="1d462-210">また、発行された保持ラベルをエンド ユーザーが利用したり、ラベルをコンテンツに自動適用したりできるようになるまでには、場所で時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="1d462-210">Then the location might require time to make published retention labels available to end users or time to auto-apply labels to content.</span></span> <span data-ttu-id="1d462-211">これにかかる時間は、場所と保持ラベルの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="1d462-211">How long this takes depends on the location and type of retention label.</span></span>
    
### <a name="published-retention-labels"></a><span data-ttu-id="1d462-212">発行された保持ラベル</span><span class="sxs-lookup"><span data-stu-id="1d462-212">Published retention labels</span></span>

<span data-ttu-id="1d462-213">If you publish retention labels to SharePoint or OneDrive, those labels  typically appear for end users to select within one day.</span><span class="sxs-lookup"><span data-stu-id="1d462-213">If you publish retention labels to SharePoint or OneDrive, those labels  typically appear for end users to select within one day.</span></span> <span data-ttu-id="1d462-214">However, allow up to seven days.</span><span class="sxs-lookup"><span data-stu-id="1d462-214">However, allow up to seven days.</span></span> <span data-ttu-id="1d462-215">If you publish retention labels to Exchange, it can take up to seven days for those retention labels to appear for end users, and the mailbox must contain at least 10 MB of data.</span><span class="sxs-lookup"><span data-stu-id="1d462-215">If you publish retention labels to Exchange, it can take up to seven days for those retention labels to appear for end users, and the mailbox must contain at least 10 MB of data.</span></span>

<span data-ttu-id="1d462-216">例:</span><span class="sxs-lookup"><span data-stu-id="1d462-216">For example:</span></span>
  
![手動ラベルが有効になるタイミングの図](../media/b19f3a10-f625-45bf-9a53-dd14df02ae7c.png)
  
### <a name="auto-apply-retention-labels"></a><span data-ttu-id="1d462-218">自動適用の保持ラベル</span><span class="sxs-lookup"><span data-stu-id="1d462-218">Auto-apply retention labels</span></span>

<span data-ttu-id="1d462-219">特定の条件に一致するコンテンツに保持ラベルを自動適用する場合、条件に一致するすべての既存コンテンツに保持ラベルが適用されるまでに最大 7 日間かかります。</span><span class="sxs-lookup"><span data-stu-id="1d462-219">If you auto-apply retention labels to content matching specific conditions, it can take up to seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![自動適用ラベルが有効になるタイミングの図](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
### <a name="how-to-check-on-the-status-of-retention-labels-published-to-exchange"></a><span data-ttu-id="1d462-221">Exchange に発行された保持ラベルの状態を確認する方法</span><span class="sxs-lookup"><span data-stu-id="1d462-221">How to check on the status of retention labels published to Exchange</span></span>

<span data-ttu-id="1d462-222">Exchange Online では、7 日ごとにプロセスが実行され、保持ラベルがエンド ユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1d462-222">In Exchange Online, retention labels are made available to end users by a process that runs every seven days.</span></span> <span data-ttu-id="1d462-223">PowerShell を使用することで、このプロセスが最後に実行された日時を確認できるため、いつ実行されるかを特定できます。</span><span class="sxs-lookup"><span data-stu-id="1d462-223">By using Powershell, you can see when this process last ran and therefore identify when it will run again.</span></span>
  
1. <span data-ttu-id="1d462-224">[Exchange Online PowerShell に接続します](https://go.microsoft.com/fwlink/?linkid=799773)。</span><span class="sxs-lookup"><span data-stu-id="1d462-224">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=799773).</span></span>
    
2. <span data-ttu-id="1d462-225">これらのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1d462-225">Run these commands.</span></span>
    
   ```powershell
   $logProps = Export-MailboxDiagnosticLogs <user> -ExtendedProperties
   ```

   ```powershell
   $xmlprops = [xml]($logProps.MailboxLog)
   ```

   ```powershell
   $xmlprops.Properties.MailboxTable.Property | ? {$_.Name -like "ELC*"}   ```

In the results, the `ELCLastSuccessTimeStamp` (UTC) property shows when the system last processed your mailbox. If it has not happened since the time you created the policy, the labels are not going to appear. To force processing, run  `Start-ManagedFolderAssistant -Identity <user>`.
    
If labels aren't appearing in Outlook on the web and you think they should be, make sure to clear the cache in your browser (CTRL+F5).
    

## Updating retention labels and their policies

When you edit a retention label, retention label policy, or auto-apply policy, and the retention label or policy is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly identified.

Some settings can't be changed after the label or policy is created and saved, which include:
- The retention settings except the retention period, unless you've configured the label to retain or delete the content based on when it was created.
- The option to classify as a record.

## Find the PowerShell cmdlets for retention labels

To use the retention label cmdlets:
  
1. [Connect to the Office 365 Security & Compliance Center Powershell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)
    
2. Use these Office 365 Security & Compliance Center cmdlets:
    
    - [Get-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/get-compliancetag)
    
    - [New-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/new-compliancetag)
    
    - [Remove-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/remove-compliancetag)
    
    - [Set-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/set-compliancetag)
    
    - [Enable-ComplianceTagStorage](https://docs.microsoft.com/powershell/module/exchange/enable-compliancetagstorage)
    
    - [Get-ComplianceTagStorage](https://docs.microsoft.com/powershell/module/exchange/get-compliancetagstorage)
    
    - [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)
    
    - [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)
    
    - [Remove-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancepolicy)
    
    - [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)
    
    - [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule)
    
    - [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule)
    
    - [Remove-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancerule)
    
    - [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule)
