---
title: 保持ラベルの詳細
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
description: 保持ラベルがガバナンス用に組織全体のデータを分類し、その分類に基づいて保持ルールを強制する方法を説明します。保持ラベルを使用して、Microsoft 365 のレコード管理ソリューションを実装することもできます。
ms.openlocfilehash: 54691f996f1b2e0759c4d8758df0044a32b9ffa9
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327905"
---
# <a name="learn-about-retention-labels"></a><span data-ttu-id="837fa-104">保持ラベルの詳細</span><span class="sxs-lookup"><span data-stu-id="837fa-104">Learn about retention labels</span></span>

><span data-ttu-id="837fa-105">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="837fa-105">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="837fa-p102">おそらく、組織全体では、業界の規制や社内のポリシーを遵守するためにさまざまアクションを実行する必要のある、多様な種類のコンテンツがあります。たとえば、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="837fa-p102">Across your organization, you probably have different types of content that require different actions taken on them in order to comply with industry regulations and internal policies. For example, you might have:</span></span>
  
- <span data-ttu-id="837fa-108">最小限の期間、**保持する**必要のある税フォーム。</span><span class="sxs-lookup"><span data-stu-id="837fa-108">Tax forms that need to be **retained** for a minimum period of time.</span></span> 
    
- <span data-ttu-id="837fa-109">一定の期間に到達した場合、**完全に削除する**必要があるプレス資料。</span><span class="sxs-lookup"><span data-stu-id="837fa-109">Press materials that need to be **permanently deleted** when they reach a certain age.</span></span> 
    
- <span data-ttu-id="837fa-110">**保持**と**完全な削除**の両方が必要な競合他社のリサーチ。</span><span class="sxs-lookup"><span data-stu-id="837fa-110">Competitive research that needs to be both **retained** and then **permanently deleted**.</span></span> 
    
- <span data-ttu-id="837fa-111">編集も削除もできないように、**レコードとしてマーク**する必要のある就労ビザ。</span><span class="sxs-lookup"><span data-stu-id="837fa-111">Work visas that must be **marked as a record** so that they can't be edited or deleted.</span></span> 
    
<span data-ttu-id="837fa-p103">これらのすべてのケースにおいて、保持ラベルは適切なコンテンツで適切な操作を実行するために役立ちます。保持ラベルを使用すると、ガバナンス用に組織全体のデータを分類し、その分類に基づいて保持ルールを強制できます。</span><span class="sxs-lookup"><span data-stu-id="837fa-p103">In all of these cases, retention labels can help you take the right actions on the right content. With retention labels, you can classify data across your organization for governance, and enforce retention rules based on that classification.</span></span>
  
<span data-ttu-id="837fa-114">保持ラベルを使用すると、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="837fa-114">With retention labels, you can:</span></span>
  
- <span data-ttu-id="837fa-p104">Outlook on the web、Outlook 2010 以降、OneDrive、SharePoint、Microsoft 365 グループのコンテンツに、**組織内のユーザーが保持ラベルを手動で適用**できるようにします。多くの場合、コンテンツの種類を最も良く理解しているのはそれを扱っているユーザーです。そこでユーザーにコンテンツを分類し、適切なポリシーを適用してもらいます。</span><span class="sxs-lookup"><span data-stu-id="837fa-p104">**Enable people in your organization to apply a retention label manually** to content in Outlook on the web, Outlook 2010 and later, OneDrive, SharePoint, and Microsoft 365 Groups. Users often know best what type of content they're working with, so they can classify it and have the appropriate policy applied.</span></span> 
    
- <span data-ttu-id="837fa-117">コンテンツに次のものが含まれている場合など、特定の条件に一致するときには、**保持ラベルをコンテンツに自動的に適用**できます。</span><span class="sxs-lookup"><span data-stu-id="837fa-117">**Apply retention labels to content automatically** if it matches specific conditions, such as when the content contains:</span></span> 
    
    - <span data-ttu-id="837fa-118">特定の種類の機密情報。</span><span class="sxs-lookup"><span data-stu-id="837fa-118">Specific types of sensitive information.</span></span>
    
    - <span data-ttu-id="837fa-119">作成したクエリに一致する特定のキーワード。</span><span class="sxs-lookup"><span data-stu-id="837fa-119">Specific keywords that match a query you create.</span></span>
    
    - <span data-ttu-id="837fa-120">トレーニング可能な分類子のパターン マッチ。</span><span class="sxs-lookup"><span data-stu-id="837fa-120">Pattern matches for a trainable classifier.</span></span>
    
  <span data-ttu-id="837fa-121">保持ラベルを自動的にコンテンツに適用する機能が重要である理由は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="837fa-121">The ability to apply retention labels to content automatically is important because:</span></span>
    
     - <span data-ttu-id="837fa-122">ユーザーのトレーニングは、一部の分類方法についてのみ必要。</span><span class="sxs-lookup"><span data-stu-id="837fa-122">You don't need to train your users on all of your classifications.</span></span>
    
     - <span data-ttu-id="837fa-123">ユーザーへの依存は、一部のコンテンツを正しく分類するためにのみ必要。</span><span class="sxs-lookup"><span data-stu-id="837fa-123">You don't need to rely on users to classify all content correctly.</span></span>
    
   - <span data-ttu-id="837fa-124">ユーザーはデータ ガバナンス ポリシーについて把握する必要がなくなり、仕事に集中できる。</span><span class="sxs-lookup"><span data-stu-id="837fa-124">Users no longer need to know about data governance policies - they can instead focus on their work.</span></span>

- <span data-ttu-id="837fa-125">SharePoint の**ドキュメント ライブラリ、フォルダー、またはドキュメント セットに既定の保持ラベルを適用**することにより、この場所に保存するすべてのドキュメントに既定の保持ラベルが継承されるようになります。</span><span class="sxs-lookup"><span data-stu-id="837fa-125">**Apply a default retention label to a document library, folder, or document set** in SharePoint, so that all documents that are stored in that location inherit the default retention label.</span></span>

<span data-ttu-id="837fa-126">さらに、保持ラベルは、Microsoft 365 アプリとサービス全体でのメールとドキュメントの[レコード管理](records-management.md)をサポートします。</span><span class="sxs-lookup"><span data-stu-id="837fa-126">Additionally, retention labels support [records management](records-management.md) for email and documents across Microsoft 365 apps and services.</span></span> <span data-ttu-id="837fa-127">保持ラベルを使用して、コンテンツをレコードとして分類できます。</span><span class="sxs-lookup"><span data-stu-id="837fa-127">You can use a retention label to classify content as a record.</span></span> <span data-ttu-id="837fa-128">この操作を行うと、ラベルを変更または削除することはできません。また、コンテンツを編集または削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="837fa-128">When this happens, the label can't be changed or removed, and the content can't be edited or deleted.</span></span> 

<span data-ttu-id="837fa-129">テナントでサポートされる保持ラベルの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="837fa-129">There is no limit to the number of retention labels that are supported for a tenant.</span></span> <span data-ttu-id="837fa-130">ただし、10,000 はテナントでサポートされるポリシーの最大数であり、これらには、ラベルを適用するポリシー (保持ラベル ポリシーと自動適用アイテム保持ポリシー) とアイテム保持ポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="837fa-130">However, 10,000 is the maximum number of policies that are supported for a tenant and these include the policies that apply the labels (retention label policies and auto-apply retention policies), as well as retention policies.</span></span>

## <a name="how-retention-labels-work-with-retention-label-policies"></a><span data-ttu-id="837fa-131">保持ラベル ポリシーでの保持ラベルのしくみ</span><span class="sxs-lookup"><span data-stu-id="837fa-131">How retention labels work with retention label policies</span></span>

<span data-ttu-id="837fa-132">組織内のユーザーが保持ラベルを使用できるようにして、コンテンツを分類できるようにするプロセスは 2 段階です。</span><span class="sxs-lookup"><span data-stu-id="837fa-132">Making retention labels available to people in your organization so that they can classify content is a two-step process:</span></span> 

1. <span data-ttu-id="837fa-133">保持ラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="837fa-133">Create the retention labels</span></span>

2. <span data-ttu-id="837fa-134">保持ラベル ポリシーを使用して保持ラベルを発行する</span><span class="sxs-lookup"><span data-stu-id="837fa-134">Publish the retention labels by using a retention label policy</span></span>
  
![ラベルの役割とタスクの図](../media/4082bc7d-c04c-4b9a-8a26-7f12565d3311.png)
  
<span data-ttu-id="837fa-136">保持ラベルは依存しない、再利用可能な文書パーツで、1 つ以上の保持ラベル ポリシーに含まれています。</span><span class="sxs-lookup"><span data-stu-id="837fa-136">Retention labels are independent, reusable building blocks that are included in one or more retention label policies.</span></span> <span data-ttu-id="837fa-137">保持ラベル ポリシーの主な目的は、保持ラベルのセットをグループ化して、ラベルを表示する場所を特定することです。</span><span class="sxs-lookup"><span data-stu-id="837fa-137">The primary purpose of a retention label policy is to group a set of retention labels and specify the locations where you want those labels to appear.</span></span>
  
![ラベル、ラベル ポリシー、および場所の図](../media/eee42516-adf0-4664-b5ab-76727a9a3511.png)
  
1. <span data-ttu-id="837fa-139">保持ラベルを発行すると、保持ラベルは保持ラベル ポリシーに含まれるようになります。</span><span class="sxs-lookup"><span data-stu-id="837fa-139">When you publish retention labels, they're included in a retention label policy.</span></span> <span data-ttu-id="837fa-140">保持ラベル名は変更することができないため、作成後に編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="837fa-140">Retention label names are immutable, which means that they cannot be edited after they're created.</span></span>

2. <span data-ttu-id="837fa-141">1 つの保持ラベルは、複数の保持ラベル ポリシーに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="837fa-141">A single retention label can be included in many retention label policies.</span></span>

3. <span data-ttu-id="837fa-142">また、1 つの場所は、複数の保持ラベル ポリシーに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="837fa-142">A single location can also be included in many retention label policies.</span></span>
    
3. <span data-ttu-id="837fa-143">保持ラベル ポリシーは保持ラベルを発行する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="837fa-143">Retention label policies specify the locations to publish the retention labels.</span></span>
    
## <a name="only-one-retention-label-at-a-time"></a><span data-ttu-id="837fa-144">一度に 1 つの保持ラベルのみ</span><span class="sxs-lookup"><span data-stu-id="837fa-144">Only one retention label at a time</span></span>

<span data-ttu-id="837fa-145">メールやドキュメントなどのコンテンツに一度に割り当てられる保持ラベルは 1 つのみです。これを知っておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="837fa-145">It's important to know that content like an email or document can have only a single retention label assigned to it at a time:</span></span>
  
- <span data-ttu-id="837fa-146">エンド ユーザーが手動で割り当てた保持ラベルの場合、ユーザーは割り当てられている保持ラベルを削除または変更できます。</span><span class="sxs-lookup"><span data-stu-id="837fa-146">For retention labels assigned manually by end users, people can remove or change the retention label that's assigned.</span></span>
    
- <span data-ttu-id="837fa-147">コンテンツに自動適用ラベルが割り当てられている場合は、自動適用ラベルをエンド ユーザーが手動で割り当てた保持ラベルに置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="837fa-147">If content has an auto-apply label assigned, an auto-apply label can be replaced by a retention label assigned manually by an end user.</span></span>
    
- <span data-ttu-id="837fa-148">コンテンツにエンド ユーザーが手動で割り当てた保持ラベルがある場合は、自動適用ラベルと手動で割り当てられた保持ラベルを置き換えることはできません。</span><span class="sxs-lookup"><span data-stu-id="837fa-148">If content has a retention label assigned manually by an end user, an auto-apply label cannot replace the manually assigned retention label.</span></span>
    
- <span data-ttu-id="837fa-149">自動適用ラベルを割り当てるルールが複数あり、コンテンツが複数のルールの条件を満たしている場合、最も古いルールの保持ラベルが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="837fa-149">If there are multiple rules that assign an auto-apply label and content meets the conditions of multiple rules, the retention label for the oldest rule is assigned.</span></span>
    
<span data-ttu-id="837fa-150">保持ラベルが別の保持ラベルではなくどのように適用されるかを理解するには、ラベルを明示的に割り当てることと、ラベルを暗黙的に割り当てることの違いを理解することが役立ちます。</span><span class="sxs-lookup"><span data-stu-id="837fa-150">To understand how and why one retention label is applied rather than another, it's helpful to understand the difference between explicitly assign a label, and implicitly assigned a label:</span></span>

- <span data-ttu-id="837fa-151">手動で割り当てられたラベルは明示的に割り当てられます</span><span class="sxs-lookup"><span data-stu-id="837fa-151">Manually assigned labels are explicitly assigned</span></span>
- <span data-ttu-id="837fa-152">自動的に適用されるラベルは暗黙的に割り当てられます</span><span class="sxs-lookup"><span data-stu-id="837fa-152">Automatically applied labels are implicitly assigned</span></span>

<span data-ttu-id="837fa-153">明示的に割り当てられた保持ラベルは、暗黙的に割り当てられた保持ラベルよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="837fa-153">An explicitly assigned retention label takes precedence over an implicitly assigned retention label.</span></span> <span data-ttu-id="837fa-154">詳細については、このページの「[保持の原則または優先順位](#the-principles-of-retention-or-what-takes-precedence)」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="837fa-154">For more information, see the [The principles of retention, or what takes precedence?](#the-principles-of-retention-or-what-takes-precedence) section on this page.</span></span>

<span data-ttu-id="837fa-155">結果の中で、`ELCLastSuccessTimeStamp` (UTC) プロパティは、システムがメールボックスを最後に処理した日時を示しています。</span><span class="sxs-lookup"><span data-stu-id="837fa-155">In the results, the `ELCLastSuccessTimeStamp` (UTC) property shows when the system last processed your mailbox.</span></span> <span data-ttu-id="837fa-156">ポリシーの作成後に処理がまだ行われていない場合は、ラベルは表示されません。</span><span class="sxs-lookup"><span data-stu-id="837fa-156">If it has not happened since the time you created the policy, the labels are not going to appear.</span></span> <span data-ttu-id="837fa-157">処理を強制的に行うには、`Start-ManagedFolderAssistant -Identity <user>` を実行します。</span><span class="sxs-lookup"><span data-stu-id="837fa-157">To force processing, run  `Start-ManagedFolderAssistant -Identity <user>`.</span></span>
    
<span data-ttu-id="837fa-158">Outlook on the web にラベルが表示されると思われるにもかかわらず、ラベルが表示されない場合は、ブラウザーのキャッシュを必ず消去してください (CTRL + F5)。</span><span class="sxs-lookup"><span data-stu-id="837fa-158">If labels aren't appearing in Outlook on the web and you think they should be, make sure to clear the cache in your browser (CTRL+F5).</span></span>
    
## <a name="retention-label-policies-and-locations"></a><span data-ttu-id="837fa-159">保持ラベルのポリシーと場所</span><span class="sxs-lookup"><span data-stu-id="837fa-159">Retention label policies and locations</span></span>

<span data-ttu-id="837fa-160">保持ラベルの内容に応じて、多様な種類の保持ラベルをさまざまな場所に発行できます。</span><span class="sxs-lookup"><span data-stu-id="837fa-160">Different types of retention labels can be published to different locations, depending on what the retention label does.</span></span>
  
|<span data-ttu-id="837fa-161">**保持ラベルの種類**</span><span class="sxs-lookup"><span data-stu-id="837fa-161">**If the retention label is…**</span></span>|<span data-ttu-id="837fa-162">**ラベル ポリシーの適用先**</span><span class="sxs-lookup"><span data-stu-id="837fa-162">**Then the label policy can be applied to…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="837fa-163">エンド ユーザーに発行されたラベル</span><span class="sxs-lookup"><span data-stu-id="837fa-163">Published to end users</span></span>  <br/> |<span data-ttu-id="837fa-164">Exchange、SharePoint、OneDrive、Microsoft 365 グループ</span><span class="sxs-lookup"><span data-stu-id="837fa-164">Exchange, SharePoint, OneDrive, Microsoft 365 Groups</span></span>  <br/> |
|<span data-ttu-id="837fa-165">機密情報の種類に基づいて自動適用されたラベル</span><span class="sxs-lookup"><span data-stu-id="837fa-165">Auto-applied based on sensitive information types</span></span>  <br/> |<span data-ttu-id="837fa-166">Exchange (すべてのメールボックスのみ)、SharePoint、OneDrive</span><span class="sxs-lookup"><span data-stu-id="837fa-166">Exchange (all mailboxes only), SharePoint, OneDrive</span></span>  <br/> |
|<span data-ttu-id="837fa-167">クエリに基づいて自動適用されたラベル</span><span class="sxs-lookup"><span data-stu-id="837fa-167">Auto-applied based on a query</span></span>  <br/> |<span data-ttu-id="837fa-168">Exchange、SharePoint、OneDrive、Microsoft 365 グループ</span><span class="sxs-lookup"><span data-stu-id="837fa-168">Exchange, SharePoint, OneDrive, Microsoft 365 Groups</span></span>  <br/> |
   
<span data-ttu-id="837fa-169">Exchange の自動適用保持ラベル (クエリと機密情報の両方の種類) は、新しく送信されたメッセージ (送信中のデータ) のみに適用され、現在メールボックスにあるすべてのアイテム (保存中のデータ) には適用されません。</span><span class="sxs-lookup"><span data-stu-id="837fa-169">In Exchange, auto-apply retention labels (for both queries and sensitive information types) are applied only to messages newly sent (data in transit), not to all items currently in the mailbox (data at rest).</span></span> <span data-ttu-id="837fa-170">また、機密情報の種類の自動適用保持ラベルはすべてのメールボックスのみに適用でき、特定のメールボックスを選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="837fa-170">Also, auto-apply retention labels for sensitive information types can apply only to all mailboxes; you can't select the specific mailboxes.</span></span>
  
<span data-ttu-id="837fa-171">Exchange パブリック フォルダーと Skype では保持ラベルはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="837fa-171">Exchange public folders and Skype do not support retention labels.</span></span>

## <a name="how-retention-labels-enforce-retention"></a><span data-ttu-id="837fa-172">保持ラベルによる強制保持のしくみ</span><span class="sxs-lookup"><span data-stu-id="837fa-172">How retention labels enforce retention</span></span>

<span data-ttu-id="837fa-173">保持ラベルは、保持ポリシーと同じ保持操作 (保持してから削除する、保持のみ、または削除のみ) を実施できます。</span><span class="sxs-lookup"><span data-stu-id="837fa-173">Retention labels can enforce the same retention actions that a retention policy can - retain and then delete, or retain-only, or delete-only.</span></span> <span data-ttu-id="837fa-174">保持ラベルを使用して、高度なコンテンツ プラン (またはファイル プラン) を実装できます。</span><span class="sxs-lookup"><span data-stu-id="837fa-174">You can use retention labels to implement a sophisticated content plan (or file plan).</span></span> <span data-ttu-id="837fa-175">保持の仕組みに関する詳細情報は、「[アイテム保持ポリシーの詳細](retention-policies.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="837fa-175">For more information about how retention works, see [Learn about retention policies](retention-policies.md).</span></span>
  
<span data-ttu-id="837fa-p113">さらに、保持ラベルには 2 つの保持オプションがあります。これらのオプションは保持ラベルでのみ使用でき、アイテム保持ポリシーでは使用できません。保持ラベルを使用すると、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="837fa-p113">In addition, a retention label has two retention options that are available only in a retention label and not in a retention policy. With a retention label, you can:</span></span>
  
- <span data-ttu-id="837fa-178">保持期間の終了時に処理の確認をトリガーすることができます。SharePoint および OneDrive のドキュメントは削除する前に、確認する必要があるからです。</span><span class="sxs-lookup"><span data-stu-id="837fa-178">Trigger a disposition review at the end of the retention period, so that SharePoint and OneDrive documents must be reviewed before they can be deleted.</span></span> <span data-ttu-id="837fa-179">詳細については、「[廃棄確認](disposition.md#disposition-reviews)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="837fa-179">For more information, see [Disposition reviews](disposition.md#disposition-reviews).</span></span>
    
- <span data-ttu-id="837fa-180">コンテンツの作成日または最終変更日時ではなく、コンテンツがラベル付けされた時点から保持期間を開始できます。</span><span class="sxs-lookup"><span data-stu-id="837fa-180">Start the retention period from when the content was labeled, instead of the age of the content or when it was last modified.</span></span> <span data-ttu-id="837fa-181">このオプションは、SharePoint サイトおよび OneDrive アカウントのコンテンツにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="837fa-181">This option applies only to content in SharePoint sites and OneDrive accounts.</span></span> <span data-ttu-id="837fa-182">Exchange メールの場合、オプションのどれを選んだかを問わず、保持期間は常にメッセージが送受信された日付に基づきます。</span><span class="sxs-lookup"><span data-stu-id="837fa-182">For Exchange email, the retention period is always based on the date when the message was sent or received, no matter which option you choose here.</span></span>
    
![ラベル固有のオプションによる保持設定](../media/c49118c9-6279-4661-94db-deffa76e27ac.png)

## <a name="where-published-retention-labels-can-appear-to-end-users"></a><span data-ttu-id="837fa-184">発行済みラベルをエンド ユーザー向けに表示できる場所</span><span class="sxs-lookup"><span data-stu-id="837fa-184">Where published retention labels can appear to end users</span></span>

<span data-ttu-id="837fa-185">保持ラベルがエンド ユーザーによってコンテンツに割り当てられる場合、保持ラベルは次の場所に発行できます。</span><span class="sxs-lookup"><span data-stu-id="837fa-185">If your retention label will be assigned to content by end users, you can publish it to:</span></span>
  
- <span data-ttu-id="837fa-186">Outlook および Outlook on the web</span><span class="sxs-lookup"><span data-stu-id="837fa-186">Outlook and Outlook on the web</span></span>
    
- <span data-ttu-id="837fa-187">OneDrive</span><span class="sxs-lookup"><span data-stu-id="837fa-187">OneDrive</span></span>
    
- <span data-ttu-id="837fa-188">SharePoint</span><span class="sxs-lookup"><span data-stu-id="837fa-188">SharePoint</span></span>
    
- <span data-ttu-id="837fa-189">Microsoft 365 グループ (Outlook on the web のグループ サイトとグループ メールボックスの両方)</span><span class="sxs-lookup"><span data-stu-id="837fa-189">Microsoft 365 groups (both the group site and group mailbox in Outlook on the web)</span></span>
    
<span data-ttu-id="837fa-190">次のセクションでは、さまざまなアプリで組織内のユーザーに対してラベルがどのように表示されるかを説明します。</span><span class="sxs-lookup"><span data-stu-id="837fa-190">The sections that follow explain how labels appear in different apps to people in your organization.</span></span>
  

### <a name="outlook"></a><span data-ttu-id="837fa-191">Outlook</span><span class="sxs-lookup"><span data-stu-id="837fa-191">Outlook</span></span>

<span data-ttu-id="837fa-192">Outlook デスクトップ クライアントでアイテムにラベルを付けるには、アイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="837fa-192">To label an item in the Outlook desktop client, select the item.</span></span> <span data-ttu-id="837fa-193">リボンの **[ホーム]** タブで、**[ポリシーの割り当て]** をクリックし、保持ラベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="837fa-193">On the **Home** tab on the ribbon, click **Assign Policy**, and then choose the retention label.</span></span> 
  
![[ポリシーの割り当て] ボタン](../media/30684dea-dd73-4e4a-9185-8e29f403b6ca.png)
  
<span data-ttu-id="837fa-195">アイテムを右クリックし、コンテキスト メニューの **[ポリシーの割り当て]** をクリックし、保持ラベルを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="837fa-195">You can also right-click an item, click **Assign Policy** in the context menu, and then choose the retention label.</span></span> 

<span data-ttu-id="837fa-196">保持ラベルを適用すると、アイテムの上部でその保持ラベルとラベルで行える操作が表示されます。</span><span class="sxs-lookup"><span data-stu-id="837fa-196">After the retention label is applied, you can view that retention label and what action it takes at the top of the item.</span></span> <span data-ttu-id="837fa-197">保持期間が関連付けられている保持ラベルがメールに含まれている場合は、メールの有効期間を一目で確認できます。</span><span class="sxs-lookup"><span data-stu-id="837fa-197">If an email has a retention label applied that has an associated retention period, you can see at a glance when the email expires.</span></span>
  
<span data-ttu-id="837fa-198">保持ラベルはフォルダーに適用することもできます。その場合は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="837fa-198">You can also apply retention labels to folders, in which case:</span></span>
  
- <span data-ttu-id="837fa-199">フォルダー内のすべてのアイテムは、同じ保持ラベルを自動的に取得します。ただし、明示的に保持ラベルが適用されたアイテムは**除きます**。</span><span class="sxs-lookup"><span data-stu-id="837fa-199">All items in the folder automatically get the same retention label, **except** for items that have had a retention label applied explicitly to them.</span></span> <span data-ttu-id="837fa-200">明示的にラベルが付いたアイテムは、既存の保持ラベルを保持します。</span><span class="sxs-lookup"><span data-stu-id="837fa-200">Explicitly labeled items keep their existing retention label.</span></span> <span data-ttu-id="837fa-201">詳細については、下記の[保持の原則または優先順位](#the-principles-of-retention-or-what-takes-precedence)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="837fa-201">For more information, see [The principles of retention, or what takes precedence?](#the-principles-of-retention-or-what-takes-precedence) section on this page.</span></span> 
    
- <span data-ttu-id="837fa-202">フォルダーの既定の保持ラベルを変更または削除すると、保持ラベルが明示的に割り当てられているアイテムを**除き**、フォルダー内にあるすべてのアイテムの保持ラベルも変更または削除されます。</span><span class="sxs-lookup"><span data-stu-id="837fa-202">If you change or remove the default retention label for a folder, the retention label's also changed or removed for all items in the folder, **except** items with explicitly assigned retention labels.</span></span> 
    
- <span data-ttu-id="837fa-203">既定の保持ラベルを持つアイテムをあるフォルダーから異なる既定の保持ラベルを持つ別のフォルダーに移動すると、そのアイテムには新しい既定の保持ラベルが設定されます。</span><span class="sxs-lookup"><span data-stu-id="837fa-203">If you move an item with a default retention label from one folder to another folder with a different default retention label, the item gets the new default retention label.</span></span>
    
- <span data-ttu-id="837fa-204">既定の保持ラベルを持つアイテムをあるフォルダーから既定の保持ラベルがない別のフォルダーに移動すると、以前の既定の保持ラベルが削除されます。</span><span class="sxs-lookup"><span data-stu-id="837fa-204">If you move an item with a default retention label from one folder to another folder with no default retention label, the old default retention label is removed.</span></span>

### <a name="outlook-on-the-web"></a><span data-ttu-id="837fa-205">Outlook on the web</span><span class="sxs-lookup"><span data-stu-id="837fa-205">Outlook on the web</span></span>

<span data-ttu-id="837fa-206">Outlook on the web でアイテムにラベルを付けるには、アイテム \>**[ポリシーの割り当て]**\> の順に右クリックして、保持ラベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="837fa-206">To label an item in Outlook on the web, right-click the item \> **Assign policy** \> choose the retention label.</span></span> 
  
![Outlook on the web の [ポリシーの割り当て] メニュー](../media/146a23cf-e478-4595-b2e8-f707fc4e6ea3.png)
  
<span data-ttu-id="837fa-p119">保持ラベルが適用されると、アイテムの上部にその保持ラベルとラベルが実行するアクションが表示されます。メールが分類され、保持期間が関連付けられている場合、メールの有効期限が一目でわかります。</span><span class="sxs-lookup"><span data-stu-id="837fa-p119">After the retention label is applied, you can view that retention label and what action it takes at the top of the item. If an email is classified and has an associated retention period, you can know at a glance when the email will expire.</span></span>
  
![メールに割り当てられたラベル (Outlook on the web)](../media/16f6c91b-5eab-4574-9d13-6d12be00a783.png)
  
<span data-ttu-id="837fa-211">Outlook on the web と同様に、保持ラベルはフォルダーに適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="837fa-211">As with Outlook on the web, you can also apply retention labels to folders.</span></span> 

### <a name="onedrive-and-sharepoint"></a><span data-ttu-id="837fa-212">OneDrive と SharePoint</span><span class="sxs-lookup"><span data-stu-id="837fa-212">OneDrive and SharePoint</span></span>

<span data-ttu-id="837fa-213">OneDrive または SharePoint でドキュメント (OneNote ファイルを含む) にラベルを付けるには、右上隅のアイテム \> を選択し、[**詳細ウィンドウを開く**] ![情報ウィンドウ アイコン](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) \> [**保持ラベルを適用**] \> の順に移動し保持ラベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="837fa-213">To label a document (including OneNote files) in OneDrive or SharePoint, select the item \> in the upper-right corner, choose **Open the details pane**![Information pane icon](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) \> **Apply retention label** \> choose the retention label.</span></span> 
  
<span data-ttu-id="837fa-214">フォルダーまたはドキュメントのセットに保持ラベルを適用することもできます。また、[ドキュメント ライブラリに対して既定の保持ラベル](#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set)を設定できます。</span><span class="sxs-lookup"><span data-stu-id="837fa-214">You can also apply a retention label to a folder or document set, and you can set a [default retention label for a document library](#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>
  
![SharePoint のアイテムに対するラベル リストの適用](../media/151cc83c-da57-45b0-9cd1-fd2f28a31083.png)
  
<span data-ttu-id="837fa-216">アイテムに保持ラベルが適用されると、そのアイテムの選択時に、詳細ウィンドウにラベルを表示できます。</span><span class="sxs-lookup"><span data-stu-id="837fa-216">After a retention label is applied to an item, you can view it in the details pane when that item's selected.</span></span>
  
![詳細ウィンドウに表示される適用されたラベル](../media/d06e585e-29f7-4c8c-afef-629c97268b8e.png)
  
<span data-ttu-id="837fa-218">OneDrive ではなく SharePoint の場合、[**ラベル**] 列または [**レコードとして登録されているアイテム**] 列を含むライブラリのビューを作成できます。</span><span class="sxs-lookup"><span data-stu-id="837fa-218">For SharePoint, but not OneDrive, you can create a view of the library that contains the **Labels** column or **Item is a Record** column.</span></span> <span data-ttu-id="837fa-219">このビューでは、すべてのアイテムに割り当てられている保持ラベルと、レコードであるアイテムを一目で確認できます。</span><span class="sxs-lookup"><span data-stu-id="837fa-219">This view lets you see at a glance the retention labels assigned to all items and which items are records.</span></span> <span data-ttu-id="837fa-220">ただし、[**レコードとして登録されているアイテム**] 列でビューをフィルター処理することはできません。</span><span class="sxs-lookup"><span data-stu-id="837fa-220">Note, however, that you can't filter the view by the **Item is a Record** column.</span></span> <span data-ttu-id="837fa-221">列を追加する方法については、「[リストまたはライブラリの列の表示/非表示を切り替える](https://support.microsoft.com/ja-JP/office/show-or-hide-columns-in-a-list-or-library-b820db0d-9e3e-4ff9-8b8b-0b2dbefa87e2)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="837fa-221">For instructions how to add columns, see [Show or hide columns in a list or library](https://support.microsoft.com/ja-JP/office/show-or-hide-columns-in-a-list-or-library-b820db0d-9e3e-4ff9-8b8b-0b2dbefa87e2).</span></span>
  

### <a name="microsoft-365-groups"></a><span data-ttu-id="837fa-222">Microsoft 365 グループ</span><span class="sxs-lookup"><span data-stu-id="837fa-222">Microsoft 365 groups</span></span>

<span data-ttu-id="837fa-223">保持ラベルを Microsoft 365 グループ ([以前の Office 365 グループ](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) に発行すると、保持ラベルはグループ サイトと Outlook on the web のグループ メールボックスの両方に表示されます。</span><span class="sxs-lookup"><span data-stu-id="837fa-223">When you publish retention labels to Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)), the retention labels appear in both the group site and group mailbox in Outlook on the web.</span></span> <span data-ttu-id="837fa-224">保持ラベルをコンテンツに適用する操作は、メールやドキュメントの操作と似ています。</span><span class="sxs-lookup"><span data-stu-id="837fa-224">The experience of applying a retention label to content is identical to that for email and documents.</span></span>

<span data-ttu-id="837fa-225">Microsoft 365 グループのコンテンツを保持するには、**Office 365 グループ**の場所を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="837fa-225">To retain content for a Microsoft 365 group, use the **Office 365 groups** location.</span></span> <span data-ttu-id="837fa-226">Microsoft 365 グループには Exchange メールボックスがありますが、Exchange の場所全体が含まれるアイテム保持ポリシーには、Microsoft 365 グループのメールボックスのコンテンツは含まれません。</span><span class="sxs-lookup"><span data-stu-id="837fa-226">Even though a Microsoft 365 group has an Exchange mailbox, a retention policy that includes the entire Exchange location won't include content in Microsoft 365 group mailboxes.</span></span>

<span data-ttu-id="837fa-227">また、Exchange の場所を使用して特定のグループ メールボックスを含めたり除外したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="837fa-227">In addition, it's not possible to use the Exchange location to include or exclude a specific group mailbox.</span></span> <span data-ttu-id="837fa-228">最初は Exchange の場所でグループ メールボックスを選択できますが、アイテム保持ポリシーを保存しようとすると、Exchange の場所では "RemoteGroupMailbox" を選択できないことを示すエラーを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="837fa-228">Although the Exchange location initially allows a group mailbox to be selected, when you try to save the retention policy, you receive an error that "RemoteGroupMailbox" is not a valid selection for the Exchange location.</span></span>
  
<span data-ttu-id="837fa-229">まず、アプリやその他のサービスで使用する秘密度ラベルを作成し、構成します。</span><span class="sxs-lookup"><span data-stu-id="837fa-229">First, create and configure the sensitivity labels that you want to make available for apps and other services.</span></span> <span data-ttu-id="837fa-230">たとえば、ユーザーに表示して Office アプリから適用するラベルです。</span><span class="sxs-lookup"><span data-stu-id="837fa-230">For example, the labels you want users to see and apply from Office apps.</span></span> 

<span data-ttu-id="837fa-231">次に、構成するラベルとポリシー設定を含む 1 つ以上のラベル ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="837fa-231">Then, create one or more label policies that contain the labels and policy settings that you configure.</span></span> <span data-ttu-id="837fa-232">このラベル ポリシーで、選択したユーザーと場所のラベルと設定を発行します。</span><span class="sxs-lookup"><span data-stu-id="837fa-232">It's the label policy that publishes the labels and settings for your chosen users and locations.</span></span>

## <a name="applying-a-retention-label-automatically-based-on-conditions"></a><span data-ttu-id="837fa-233">条件に基づいた保持ラベルの自動適用</span><span class="sxs-lookup"><span data-stu-id="837fa-233">Applying a retention label automatically based on conditions</span></span>

<span data-ttu-id="837fa-234">保持ラベルの最も強力な機能の 1 つは、特定の条件に一致したコンテンツに自動的にラベルを適用することです。</span><span class="sxs-lookup"><span data-stu-id="837fa-234">One of the most powerful features of retention labels is the ability to apply them automatically to content that matches certain conditions.</span></span> <span data-ttu-id="837fa-235">この場合、組織内のユーザーが保持ラベルを適用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="837fa-235">In this case, people in your organization don't need to apply the retention labels.</span></span> <span data-ttu-id="837fa-236">Microsoft 365 が行います。</span><span class="sxs-lookup"><span data-stu-id="837fa-236">Microsoft 365 does the work for them.</span></span>
  
![自動適用ラベルの役割とタスクの図](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)
  
<span data-ttu-id="837fa-238">自動適用アイテム保持ラベルが強力な機能である理由は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="837fa-238">Auto-applying retention labels are powerful because:</span></span>
  
- <span data-ttu-id="837fa-239">ユーザーのトレーニングは、一部の分類方法についてのみ必要。</span><span class="sxs-lookup"><span data-stu-id="837fa-239">You don't need to train your users on all of your classifications.</span></span>
    
- <span data-ttu-id="837fa-240">ユーザーへの依存は、一部のコンテンツを正しく分類するためにのみ必要。</span><span class="sxs-lookup"><span data-stu-id="837fa-240">You don't need to rely on users to classify all content correctly.</span></span>
    
- <span data-ttu-id="837fa-241">ユーザーはデータ ガバナンス ポリシーについて把握する必要がなくなるので、仕事に集中できる。</span><span class="sxs-lookup"><span data-stu-id="837fa-241">Users no longer need to know about data governance policies - they can focus on their work.</span></span>
    
<span data-ttu-id="837fa-242">コンテンツに次の内容が含まれている場合は、保持ラベルを自動的にコンテンツに適用するように選択できます。</span><span class="sxs-lookup"><span data-stu-id="837fa-242">You can choose to apply retention labels to content automatically when that content contains:</span></span>
  
- [<span data-ttu-id="837fa-243">特定の種類の機密情報</span><span class="sxs-lookup"><span data-stu-id="837fa-243">Specific types of sensitive information</span></span>](create-retention-labels.md#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)
    
- [<span data-ttu-id="837fa-244">作成したクエリに一致する特定のキーワード</span><span class="sxs-lookup"><span data-stu-id="837fa-244">Specific keywords that match a query you create</span></span>](create-retention-labels.md#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [<span data-ttu-id="837fa-245">トレーニング可能な分類子の一致</span><span class="sxs-lookup"><span data-stu-id="837fa-245">A match for trainable classifiers</span></span>](create-retention-labels.md#auto-apply-labels-to-content-by-using-trainable-classifiers)
    
![自動適用ラベルの [条件選択] ページ](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)

> [!TIP]
> <span data-ttu-id="837fa-247">SharePont の管理プロパティを使用して保持ラベルを自動適用し、イベント ドリブンの保持を実装する詳細なシナリオについては、「[保持ラベルを使用して SharePoint ドキュメントのライフサイクルを管理する](auto-apply-retention-labels-scenario.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="837fa-247">See [Manage the lifecycle of SharePoint documents with retention labels](auto-apply-retention-labels-scenario.md) for a detailed scenario about using managed properties in SharePoint to auto-apply retention labels and implement event-driven retention.</span></span>

## <a name="applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set"></a><span data-ttu-id="837fa-248">SharePoint ライブラリ、フォルダー、またはドキュメント セット内のすべてのコンテンツへの既定の保持ラベルの適用</span><span class="sxs-lookup"><span data-stu-id="837fa-248">Applying a default retention label to all content in a SharePoint library, folder, or document set</span></span>

<span data-ttu-id="837fa-249">個々のドキュメントにユーザーが保持ラベルを適用できるようにするだけでなく、既定の保持ラベルを SharePoint ライブラリ、フォルダー、またはドキュメント セットに適用して、その場所にあるすべてのドキュメントに既定の保持ラベルを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="837fa-249">In addition to enabling people to apply a retention label to individual documents, you can also apply a default retention label to a SharePoint library, folder, or document set, so that all documents in that location get the default retention label.</span></span>
  
<span data-ttu-id="837fa-250">ドキュメント ライブラリの場合、この操作はドキュメント ライブラリの **[ライブラリの設定]** ページで行います。</span><span class="sxs-lookup"><span data-stu-id="837fa-250">For a document library, this is done on the **Library settings** page for a document library.</span></span> <span data-ttu-id="837fa-251">既定の保持ラベルを選択すると、ライブラリにある既存のアイテムにも適用するか選択できます。</span><span class="sxs-lookup"><span data-stu-id="837fa-251">When you choose the default retention label, you can also choose to apply it to existing items in the library.</span></span> 
  
<span data-ttu-id="837fa-252">たとえば、マーケティング資料用のタグがあり、特定のドキュメント ライブラリにその種類のコンテンツだけが含まれていることがわかっている場合は、[マーケティング資料] タグをそのライブラリ内にあるすべてのドキュメントの既定に設定できます。</span><span class="sxs-lookup"><span data-stu-id="837fa-252">For example, if you have a tag for marketing materials, and you know a specific document library contains only that type of content, you can make the Marketing Materials tag the default for all documents in that library.</span></span>
  
![ライブラリの設定ページでのラベル オプションの適用](../media/0787d651-63dc-43b4-8768-716a5ecc64ec.png)
  
<span data-ttu-id="837fa-254">ライブラリ、フォルダー、またはドキュメント セット内にある既存のアイテムに既定の保持ラベルを適用すると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="837fa-254">If you apply a default retention label to existing items in the library, folder, or document set:</span></span>
  
- <span data-ttu-id="837fa-255">ただし、明示的に保持ラベルが適用されているアイテム (レコードなど) を**除き**、ライブラリ、フォルダー、またはドキュメント セット内のすべてのアイテムには自動的に同じ保持ラベルが付けられます。</span><span class="sxs-lookup"><span data-stu-id="837fa-255">All items in the library, folder, or document set automatically get the same retention label, **except** for items that have had a retention label applied explicitly to them (such as records).</span></span> <span data-ttu-id="837fa-256">明示的にラベルが付いたアイテムは、既存のラベルを保持します。</span><span class="sxs-lookup"><span data-stu-id="837fa-256">Explicitly labeled items keep their existing label.</span></span> <span data-ttu-id="837fa-257">詳細については、下記の[保持の原則または優先順位](#the-principles-of-retention-or-what-takes-precedence)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="837fa-257">For more information, see the below section on [The principles of retention, or what takes precedence](#the-principles-of-retention-or-what-takes-precedence).</span></span>
    
- <span data-ttu-id="837fa-258">ライブラリ、フォルダー、またはドキュメント セットの既定の保持ラベルを変更または削除すると、明示的な保持ラベルを持つアイテム (レコードなど) を**除き**、ライブラリ、フォルダー、またはドキュメント セット内にあるすべてのアイテムの保持ラベルも変更または削除されます。</span><span class="sxs-lookup"><span data-stu-id="837fa-258">If you change or remove the default retention label for a library, folder, or document set, the retention label is also changed or removed for all items in the library, folder, or document set, **except** items with explicit retention labels (such as records).</span></span>
    
- <span data-ttu-id="837fa-259">既定の保持ラベルを持つアイテムをあるサイト コレクション、ライブラリ、フォルダー、またはドキュメント セットから別のサイト コレクション、ライブラリ、フォルダー、または異なるラベルを持つドキュメント セットに移動すると、新しい場所に別の既定の保持ラベルが設定されていても、アイテムは既存の既定の保持ラベルを維持します。</span><span class="sxs-lookup"><span data-stu-id="837fa-259">If you move an item with a default retention label from one site collection, library, folder, or document set to another site collection, library, folder, or document set that has a different label, the item keeps its existing default retention label, even if the new location has a different default retention label.</span></span> <span data-ttu-id="837fa-260">アイテムの移動前にラベルが付いていない場合は、新しい場所の既定の保持ラベルが付けられます。</span><span class="sxs-lookup"><span data-stu-id="837fa-260">If the item does not have a label before moving, it will take on the default retention label of the new location.</span></span>

<span data-ttu-id="837fa-261">**レコード:** ライブラリ、フォルダー、またはドキュメント セットに既定のレコード ラベルを適用すると、それらの場所内のすべての項目にレコード ラベルが適用されます。</span><span class="sxs-lookup"><span data-stu-id="837fa-261">**Records:** If you apply a default record label to a library, folder, or document set, then a record label is applied to all the individual items within those locations.</span></span> <span data-ttu-id="837fa-262">新しいアイテムをレコード ラベルが付けられている場所に移動すると、そのアイテムにはレコード ラベルが付けられます。</span><span class="sxs-lookup"><span data-stu-id="837fa-262">When you move a new item into a location with a record label, that item is labeled a record.</span></span> <span data-ttu-id="837fa-263">ただし、既定の保持ラベルを、コンテンツをレコードとして宣言しないラベルに変更した場合、このアクションによりレコード ラベルが個々のアイテムから削除されることはありません。これらのアイテムでは、レコード ラベルが保持されます。</span><span class="sxs-lookup"><span data-stu-id="837fa-263">However, if you change the default retention label to a label that doesn't declare content as a record, that action does not remove the record label from the individual items; those items retain their record label.</span></span> <span data-ttu-id="837fa-264">レコード アイテムの保持ラベルを明示的に削除または変更できるのは、サイト コレクションの管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="837fa-264">Only a site collection admin can explicitly remove or change the retention label of record items.</span></span>

<span data-ttu-id="837fa-265">コンテンツをレコードとして宣言する保持ラベルの詳細については、「[レコードの詳細](records.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="837fa-265">For more information about retention labels that declare content as a record, see [Learn about records](records.md).</span></span>

## <a name="applying-a-retention-label-to-email-by-using-rules"></a><span data-ttu-id="837fa-266">ルールを使用したメールへの保持ラベルの適用</span><span class="sxs-lookup"><span data-stu-id="837fa-266">Applying a retention label to email by using rules</span></span>

<span data-ttu-id="837fa-267">Outlook では、保持ラベルまたはアイテム保持ポリシーを適用するためのルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="837fa-267">In Outlook, you can create rules to apply a retention label or retention policy.</span></span>
  
<span data-ttu-id="837fa-268">たとえば、特定の配布グループとの間で送受信されるすべてのメッセージに対して特定の保持ラベルを適用するルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="837fa-268">For example, you can create a rule that applies a specific retention label to all messages sent to or from a specific distribution group.</span></span>
  
<span data-ttu-id="837fa-269">ルールを作成するには、アイテム \>**[ルール]**\>**[ルールの作成]**\>**[高度なオプション]**\>**[ルール ウィザード]**\>**[アイテム保持ポリシーの適用]** の順に右クリックします。</span><span class="sxs-lookup"><span data-stu-id="837fa-269">To create a rule, right-click an item \> **Rules** \> **Create Rule** \> **Advanced Options** \> **Rules Wizard** \> **apply retention policy**.</span></span>
  
![アイテム保持ポリシーを適用するオプションを含むルール ウィザード](../media/eeb2407c-15b6-4224-99cf-e0a00034d8ea.png)
  
## <a name="classifying-content-without-applying-any-actions"></a><span data-ttu-id="837fa-271">アクションを適用しないコンテンツの分類</span><span class="sxs-lookup"><span data-stu-id="837fa-271">Classifying content without applying any actions</span></span>

<span data-ttu-id="837fa-272">保持ラベルを作成するときに、保持機能や他のアクションを有効にせずに、コンテンツを分類することができます。</span><span class="sxs-lookup"><span data-stu-id="837fa-272">When you create a retention label, you can do so without turning on any retention or other actions.</span></span> <span data-ttu-id="837fa-273">この場合、テキスト ラベルとして保持ラベルを使用するだけで、他のアクションを適用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="837fa-273">In this case, you can use a retention label simply as a text label, without enforcing any actions.</span></span>
  
<span data-ttu-id="837fa-274">たとえば、アクションを適用せずに「後で確認」という名前の保持ラベルを作成して、機密情報の種類を持つコンテンツまたはクエリの対象となるコンテンツにその保持ラベルを自動的に適用することができます。</span><span class="sxs-lookup"><span data-stu-id="837fa-274">For example, you can create a retention label named "Review later" with no actions, and then auto-apply that retention label to content with sensitive information types or queried content.</span></span>
  
![保持がオフになっているラベルの設定ページ](../media/17ce863b-a823-426e-aaad-83718465f762.png)
  
## <a name="using-retention-labels-for-records-management"></a><span data-ttu-id="837fa-276">レコード管理用の保持ラベルの使用</span><span class="sxs-lookup"><span data-stu-id="837fa-276">Using retention labels for records management</span></span>
    
<span data-ttu-id="837fa-277">保持ラベルを使用して、コンテンツをレコードとして宣言できます。</span><span class="sxs-lookup"><span data-stu-id="837fa-277">You can use retention labels to declare content as a record.</span></span> <span data-ttu-id="837fa-278">これにより、1 つの一貫したレコード管理戦略を Microsoft 365 全体に実装できます。</span><span class="sxs-lookup"><span data-stu-id="837fa-278">This lets you implement a single, consistent records-management strategy across Microsoft 365.</span></span> <span data-ttu-id="837fa-279">詳細については、「[レコードの概要](records.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="837fa-279">For more information, see [Overview of records](records.md).</span></span>
  
## <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="837fa-280">DLP ポリシーでの条件としての保持ラベルの使用</span><span class="sxs-lookup"><span data-stu-id="837fa-280">Using a retention label as a condition in a DLP policy</span></span>

<span data-ttu-id="837fa-p133">保持ラベルはコンテンツに対して保持アクションを強制できます。また、保持ラベルをデータ損失防止 (DLP) ポリシーで条件として使用できます。DLP ポリシーは特定のラベルを含むコンテンツに対して、アクセスを制限するなどの他のアクションを強制できます。</span><span class="sxs-lookup"><span data-stu-id="837fa-p133">A retention label can enforce retention actions on content. In addition, you can use a retention label as a condition in a data loss prevention (DLP) policy, and the DLP policy can enforce other actions, such as restricting access, on content that contains a specific label.</span></span> 
  
<span data-ttu-id="837fa-283">詳細については、「[DLP ポリシーにおける条件としての保持ラベルの使用](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="837fa-283">For more information, see [Using a retention label as a condition in a DLP policy](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy).</span></span>
  

## <a name="the-principles-of-retention-or-what-takes-precedence"></a><span data-ttu-id="837fa-284">保持の原則、すなわち優先順位について</span><span class="sxs-lookup"><span data-stu-id="837fa-284">The principles of retention, or what takes precedence?</span></span>

<span data-ttu-id="837fa-p134">コンテンツには複数のアイテム保持ポリシーが適用され、各ポリシーに異なるアクション (保持または削除、あるいはその両方) と保持期間が設定されている場合が多くあります。どれが優先されるのでしょうか? 概ね、あるポリシーで保持されているコンテンツを別のポリシーで完全に削除することはできないので、ご安心ください。</span><span class="sxs-lookup"><span data-stu-id="837fa-p134">It's possible or even likely that content might have several retention policies applied to it, each with a different action (retain, delete, or both) and retention period. What takes precedence? At the highest level, rest assured that content being retained by one policy can't be permanently deleted by another policy.</span></span>
  
![保持の原則の図](../media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
<span data-ttu-id="837fa-289">保持アクションが設定されたさまざまなラベルがコンテンツにどのように適用されているかを理解するには、次の保持の原則に注意してください。</span><span class="sxs-lookup"><span data-stu-id="837fa-289">To understand how different labels with retention actions are applied to content, keep these principles of retention in mind:</span></span>
  
1. <span data-ttu-id="837fa-p135">**保持の削除が優先されます。** あるアイテム保持ポリシーで 3 年後に Exchange メールを削除するように設定され、別のアイテム保持ポリシーでは Exchange メールを 5 年間保持してから削除するように設定されているとします。この場合、3 年を経過したコンテンツはすべて削除され、ユーザーには表示されなくなりますが、コンテンツは完全に削除される 5 年を経過するまで、回復可能なアイテム フォルダーに保持されます。</span><span class="sxs-lookup"><span data-stu-id="837fa-p135">**Retention wins over deletion.** Suppose that one retention policy says to delete Exchange email after three years, but another retention policy says to retain Exchange email for five years and then delete it. Any content that reaches three years old will be deleted and hidden from the users' view, but still retained in the Recoverable Items folder until the content reaches five years old, when it will be permanently deleted.</span></span> 
    
2. <span data-ttu-id="837fa-p136">**最長の保持期間が優先されます。** コンテンツを保持する複数のポリシーの対象となるコンテンツは、最長の保持期間が終了するまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="837fa-p136">**The longest retention period wins.** If content's subject to multiple policies that retain content, it will be retained until the end of the longest retention period.</span></span> 
    
3. <span data-ttu-id="837fa-p137">**明示的な包含は暗黙的な包含に優先します。** これは次を意味します。</span><span class="sxs-lookup"><span data-stu-id="837fa-p137">**Explicit inclusion wins over implicit inclusion.** This means:</span></span> 
    
    1. <span data-ttu-id="837fa-297">Exchange メールや OneDrive ドキュメントなど、ユーザーが保持設定の保持ラベルを手動でアイテムに割り当てた場合、サイトまたはメールボックス レベルで割り当てたポリシーや、ドキュメント ライブラリで割り当てた既定の保持ラベルよりも、手動で割り当てたラベルが優先されます。</span><span class="sxs-lookup"><span data-stu-id="837fa-297">If a retention label with retention settings is manually assigned by a user to an item, such as an Exchange email or OneDrive document, that retention label takes precedence over both a policy assigned at the site or mailbox level and a default retention label assigned by the document library.</span></span> <span data-ttu-id="837fa-298">たとえば、明示的な保持ラベルでは 10 年間保持し、サイトに割り当てたアイテム保持ポリシーでは 5 年間のみ保持する場合、明示的な保持ラベルが優先されます。</span><span class="sxs-lookup"><span data-stu-id="837fa-298">For example, if the explicit retention label says to retain for 10 years, but the retention policy assigned to the site says to retain for only five years, the retention label takes precedence.</span></span> <span data-ttu-id="837fa-299">自動適用の保持ラベルは、Microsoft 365 によって自動的に適用されるため、明示的ではなく、暗黙的とされます。</span><span class="sxs-lookup"><span data-stu-id="837fa-299">Auto-applied retention labels are considered implicit, not explicit, because they're applied automatically by Microsoft 365.</span></span>
    
    2. <span data-ttu-id="837fa-300">アイテム保持ポリシーに特定のユーザーのメールボックスまたは OneDrive のアカウントなどの特定の場所が含まれている場合、そのポリシーは、すべてのユーザーのメールボックスまたは OneDrive のアカウントに適用されるが、そのユーザーのメールボックスを特に含まない別の保持ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="837fa-300">If a retention policy includes a specific location, such as a specific user's mailbox or OneDrive account, that policy takes precedence over another retention policy that applies to all users' mailboxes or OneDrive accounts but doesn't specifically include that user's mailbox.</span></span>
    
4. <span data-ttu-id="837fa-p139">**最短の削除期間が優先されます。** 同様に、コンテンツを削除する複数のポリシー (保持なし) の対象となるコンテンツは、最短保持期間の終了時に削除されます。</span><span class="sxs-lookup"><span data-stu-id="837fa-p139">**The shortest deletion period wins.** Similarly, if content's subject to multiple policies that delete content (with no retention), it will be deleted at the end of the shortest retention period.</span></span> 
    
<span data-ttu-id="837fa-303">保持の原則は上位から下位のタイブレーク フローとして機能することを理解します。すべてのポリシーまたはラベルによって適用された複数のルールがあるレベルで同じ場合、フローは次の下位レベルに移動し、ルールが適用される優先順位を決定します。</span><span class="sxs-lookup"><span data-stu-id="837fa-303">Understand that the principles of retention work as a tie-breaking flow from top to bottom: If the rules applied by all policies or labels are the same at one level, the flow moves down to the next level to determine precedence for which rule is applied.</span></span>
  
<span data-ttu-id="837fa-304">最後に、アイテム保持ポリシーや保持ラベルは、電子情報開示のために保持しているコンテンツを完全に削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="837fa-304">Finally, a retention policy or retention label cannot permanently delete any content that's on hold for eDiscovery.</span></span> <span data-ttu-id="837fa-305">保持対象からリリースされると、コンテンツは再び上記で説明したクリーンアップ処理の対象になります。</span><span class="sxs-lookup"><span data-stu-id="837fa-305">When the hold is released, the content again becomes eligible for the cleanup process described above.</span></span>

### <a name="precedence-for-auto-labeling-with-trainable-classifiers"></a><span data-ttu-id="837fa-306">トレーニング可能な分類子による自動ラベル付けの優先順位</span><span class="sxs-lookup"><span data-stu-id="837fa-306">Precedence for auto-labeling with trainable classifiers</span></span>

<span data-ttu-id="837fa-307">トレーニング可能な分類子用に構成されているすべての保持ラベルに対しては、評価が同時に行われます。</span><span class="sxs-lookup"><span data-stu-id="837fa-307">All retention labels that are configured for trainable classifiers are evaluated simultaneously.</span></span> <span data-ttu-id="837fa-308">アイテムが複数のトレーニング可能な分類子によって検出された場合、次の基準に基づいて、適用する保持ラベルを決定します。</span><span class="sxs-lookup"><span data-stu-id="837fa-308">If an item is detected by more than one trainable classifier, the following criteria is used to determine which retention label to apply:</span></span>

1. <span data-ttu-id="837fa-309">保持のみまたは保持してから削除するように構成された保持ラベルは、削除のみに構成された保持ラベルよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="837fa-309">Retention labels configured for retain-only or retain and then delete have a higher priority over retention labels that are configured for delete-only.</span></span>

2. <span data-ttu-id="837fa-310">保持のみまたは保持してから削除するように構成されている保持ラベルの場合、最長の保持期間で構成されている保持ラベルが優先されます。</span><span class="sxs-lookup"><span data-stu-id="837fa-310">For retention labels that are configured for retain-only or retain and then delete, the retention label that is configured for the longest retention period wins.</span></span>

3. <span data-ttu-id="837fa-311">削除のみに構成されている保持ラベルの場合、最短期間で構成されている保持ラベルが優先されます。</span><span class="sxs-lookup"><span data-stu-id="837fa-311">For retention labels that are configured for delete-only, the retention label that has been configured for the shortest period wins.</span></span>

4. <span data-ttu-id="837fa-312">ラベルのアクションと期間が同じだけでは、優先されるラベルが決定されません。</span><span class="sxs-lookup"><span data-stu-id="837fa-312">Retention labels with the same action and the same period result in a retention label selection that is non-deterministic.</span></span>

## <a name="monitor-retention-labels"></a><span data-ttu-id="837fa-313">保持ラベルの監視</span><span class="sxs-lookup"><span data-stu-id="837fa-313">Monitor retention labels</span></span>

<span data-ttu-id="837fa-314">保持ラベルを発行または自動適用した後、意図したとおりにラベルがコンテンツに適用されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="837fa-314">After you publish or auto-apply your retention labels, you'll want to verify that they're being applied to content as you intended.</span></span> <span data-ttu-id="837fa-315">保持ラベルを監視するには:</span><span class="sxs-lookup"><span data-stu-id="837fa-315">To monitor your retention labels:</span></span>
  
- <span data-ttu-id="837fa-316">**ラベル アクティビティのエクスプローラー**。</span><span class="sxs-lookup"><span data-stu-id="837fa-316">**Label Activity Explorer**.</span></span> <span data-ttu-id="837fa-317">エクスプローラー (次の画像の例) では、過去 30 日間の SharePoint および OneDrive のすべてのコンテンツの保持ラベル アクティビティをすばやく検索して表示することができます。</span><span class="sxs-lookup"><span data-stu-id="837fa-317">With the explorer (example in the next picture), you can quickly search and view retention label activity for all content across SharePoint and OneDrive over the past 30 days.</span></span> <span data-ttu-id="837fa-318">詳細については、「[View label activity for documents](view-label-activity-for-documents.md)」 (ドキュメントのラベル アクティビティを表示する) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="837fa-318">For more information, see [View label activity for documents](view-label-activity-for-documents.md).</span></span>

- <span data-ttu-id="837fa-319">**[ラベル分析]** ページ。</span><span class="sxs-lookup"><span data-stu-id="837fa-319">**Label analytics** page.</span></span> <span data-ttu-id="837fa-320">Microsoft 365 コンプライアンス センターと Microsoft 365 セキュリティ センターでは、上位の保持ラベルとその適用対象を簡単に表示できます。</span><span class="sxs-lookup"><span data-stu-id="837fa-320">In the Microsoft 365 compliance center and Microsoft 365 security center, you can quickly view your top retention labels and where they're applied.</span></span> <span data-ttu-id="837fa-321">特定の保持ラベルを持つすべてのコンテンツを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="837fa-321">You can also view all content with a specific retention label.</span></span> <span data-ttu-id="837fa-322">詳細については、「[ラベル分析でラベルの使用状況を表示する](label-analytics.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="837fa-322">For more information, see [View label usage with label analytics](label-analytics.md).</span></span>
    
- <span data-ttu-id="837fa-323">**データ ガバナンスのレポート**。</span><span class="sxs-lookup"><span data-stu-id="837fa-323">**Data governance reports**.</span></span> <span data-ttu-id="837fa-324">このレポートでは、過去 90 日間の Exchange、SharePoint および OneDrive のすべてのコンテンツの保持ラベル トレンドとアクティビティをすばやく表示することができます。</span><span class="sxs-lookup"><span data-stu-id="837fa-324">With these reports, you can quickly view retention label trends and activity for all content across Exchange, SharePoint, and OneDrive over the past 90 days.</span></span> <span data-ttu-id="837fa-325">詳細については、「[データ ガバナンスのレポートを表示する](view-the-data-governance-reports.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="837fa-325">For more information, see [View the data governance reports](view-the-data-governance-reports.md).</span></span>
    
![ラベル アクティビティ エクスプローラー](../media/671ca0cd-1457-40b4-9917-b663360afd95.png)

## <a name="using-content-search-to-find-all-content-with-a-specific-retention-label-applied-to-it"></a><span data-ttu-id="837fa-327">コンテンツ検索を使用した特定の保持ラベルが適用されたすべてのコンテンツの検索</span><span class="sxs-lookup"><span data-stu-id="837fa-327">Using Content Search to find all content with a specific retention label applied to it</span></span>

<span data-ttu-id="837fa-328">ユーザーまたは自動適用によって保持ラベルがコンテンツに割り当てられた後、コンテンツ検索を使用して、特定の保持ラベルで分類されているすべてのコンテンツを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="837fa-328">After retention labels are assigned to content, either by users or auto-applied, you can use content search to find all content that's classified with a specific retention label.</span></span>
  
<span data-ttu-id="837fa-329">コンテンツの検索を作成するとき、**コンプライアンス タグ**条件を選択し、完全な保持ラベル名を入力するか、ラベル名の一部を入力してワイルドカードを使用します。</span><span class="sxs-lookup"><span data-stu-id="837fa-329">When you create a content search, choose the **Compliance Tag** condition, and then enter the complete retention label name or part of the label name and use a wildcard.</span></span> <span data-ttu-id="837fa-330">詳細については、「[コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="837fa-330">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
![[コンプライアンス タグ] 条件](../media/82d6af16-59f8-462f-babb-c894b2917018.png)
  
## <a name="use-retention-labels-instead-of-older-features"></a><span data-ttu-id="837fa-332">古い機能の代わりとしての保持ラベルの使用</span><span class="sxs-lookup"><span data-stu-id="837fa-332">Use retention labels instead of older features</span></span>

<span data-ttu-id="837fa-333">組織全体や、Exchange、SharePoint、OneDrive、Microsoft 365 グループなどの Microsoft 365 全体のコンテンツに保持ラベルを簡単に提供できます。</span><span class="sxs-lookup"><span data-stu-id="837fa-333">Retention labels can easily be made available to an entire organization and its content across Microsoft 365, including Exchange, SharePoint, OneDrive, and Microsoft 365 groups.</span></span> <span data-ttu-id="837fa-334">Microsoft 365 内のコンテンツを保持、または削除、または Microsoft 365 内のレコードを管理する必要がある場合、保持ラベルの使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="837fa-334">If you need to retain or delete content, or manage records anywhere in Microsoft 365, we recommend that you use retention labels.</span></span>
  
<span data-ttu-id="837fa-335">Microsoft 365 内のコンテンツを保持または削除、または Microsoft 365 内のレコードを管理するために以前使用されていた別の機能がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="837fa-335">There are several other features that have previously been used to retain or delete content or to manage records in Microsoft 365.</span></span> <span data-ttu-id="837fa-336">これらの機能は引き続き保持ラベルと並行して機能します。</span><span class="sxs-lookup"><span data-stu-id="837fa-336">These features will continue to work side by side with retention labels.</span></span> <span data-ttu-id="837fa-337">保持ラベルの実装が以前の機能とは異なるインスタンスがありますが、保持ラベルが進化したことで、Microsoft 365 全体でのレコード管理が今後、改善される予定です。</span><span class="sxs-lookup"><span data-stu-id="837fa-337">While there are instances where the implementation of retention labels differs from previous features, the evolution of retention labels will drive the future of records management across Microsoft 365.</span></span> <span data-ttu-id="837fa-338">そのため、データ ガバナンスの場合、次の古い機能の代わりに保持ラベルを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="837fa-338">Therefore, moving forward, for data governance, we recommend that you use retention labels instead of the following older features.</span></span>
  
### <a name="exchange-online"></a><span data-ttu-id="837fa-339">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="837fa-339">Exchange Online</span></span>

- <span data-ttu-id="837fa-340">[メッセージング レコード管理 (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) とも呼ばれる、[保持タグおよびアイテム保持ポリシー](https://go.microsoft.com/fwlink/?linkid=846125) (削除のみ)</span><span class="sxs-lookup"><span data-stu-id="837fa-340">[Retention tags and retention policies](https://go.microsoft.com/fwlink/?linkid=846125), also known as [messaging records management (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (Deletion only)</span></span> 
    
### <a name="sharepoint-and-onedrive"></a><span data-ttu-id="837fa-341">SharePoint および OneDrive</span><span class="sxs-lookup"><span data-stu-id="837fa-341">SharePoint and OneDrive</span></span>

- <span data-ttu-id="837fa-342">[インプレース レコード管理の構成](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (保持)</span><span class="sxs-lookup"><span data-stu-id="837fa-342">[Configuring in place records management](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (retention)</span></span> 
    
- <span data-ttu-id="837fa-343">[レコード センターの概要](https://support.office.com/article/bae6ca5a-7b19-40e0-b433-e3613a747c2c) (保持)</span><span class="sxs-lookup"><span data-stu-id="837fa-343">[Introduction to the Records Center](https://support.office.com/article/bae6ca5a-7b19-40e0-b433-e3613a747c2c) (Retention)</span></span> 
    
- <span data-ttu-id="837fa-344">[情報管理ポリシー](intro-to-info-mgmt-policies.md) (削除のみ)</span><span class="sxs-lookup"><span data-stu-id="837fa-344">[Information management policies](intro-to-info-mgmt-policies.md) (deletion only)</span></span> 
    

