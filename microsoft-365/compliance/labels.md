---
title: 保持ラベルの概要
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
description: 保持ラベルを使用すると、ガバナンス用に組織全体のデータを分類し、その分類に基づいて保持ルールを強制できます。保持ラベルを使用して、Microsoft 365 のレコード管理ソリューションを実装することもできます。
ms.openlocfilehash: 59adebd9b61761f05156247bbb6c4cb27b42c52b
ms.sourcegitcommit: e695bcfc69203da5d3d96f3d6a891664a0e27ae2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2020
ms.locfileid: "43106009"
---
# <a name="overview-of-retention-labels"></a><span data-ttu-id="8690d-104">保持ラベルの概要</span><span class="sxs-lookup"><span data-stu-id="8690d-104">Overview of retention labels</span></span>

><span data-ttu-id="8690d-105">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="8690d-105">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="8690d-p102">おそらく、組織全体では、業界の規制や社内のポリシーを遵守するためにさまざまアクションを実行する必要のある、多様な種類のコンテンツがあります。たとえば、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="8690d-p102">Across your organization, you probably have different types of content that require different actions taken on them in order to comply with industry regulations and internal policies. For example, you might have:</span></span>
  
- <span data-ttu-id="8690d-108">最小限の期間、**保持する**必要のある税フォーム。</span><span class="sxs-lookup"><span data-stu-id="8690d-108">Tax forms that need to be **retained** for a minimum period of time.</span></span> 
    
- <span data-ttu-id="8690d-109">一定の期間に到達した場合、**完全に削除する**必要があるプレス資料。</span><span class="sxs-lookup"><span data-stu-id="8690d-109">Press materials that need to be **permanently deleted** when they reach a certain age.</span></span> 
    
- <span data-ttu-id="8690d-110">**保持**と**完全な削除**の両方が必要な競合他社のリサーチ。</span><span class="sxs-lookup"><span data-stu-id="8690d-110">Competitive research that needs to be both **retained** and then **permanently deleted**.</span></span> 
    
- <span data-ttu-id="8690d-111">編集も削除もできないように、**レコードとしてマーク**する必要のある就労ビザ。</span><span class="sxs-lookup"><span data-stu-id="8690d-111">Work visas that must be **marked as a record** so that they can't be edited or deleted.</span></span> 
    
<span data-ttu-id="8690d-p103">これらのすべてのケースにおいて、Office 365 の保持ラベルは、適切なコンテンツで適切な操作を実行するために役立ちます。保持ラベルを使用すると、ガバナンス用に組織全体のデータを分類し、その分類に基づいて保持ルールを強制できます。</span><span class="sxs-lookup"><span data-stu-id="8690d-p103">In all of these cases, retention labels in Office 365 can help you take the right actions on the right content. With retention labels, you can classify data across your organization for governance, and enforce retention rules based on that classification.</span></span>
  
<span data-ttu-id="8690d-114">保持ラベルを使用すると、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="8690d-114">With retention labels, you can:</span></span>
  
- <span data-ttu-id="8690d-p104">Outlook on the web、Outlook 2010 以降、OneDrive、SharePoint、Office 365 グループのコンテンツに、**組織内のユーザーが保持ラベルを手動で適用**できるようにします。多くの場合、コンテンツの種類を最も良く理解しているのはそれを扱っているユーザーです。そこでユーザーにコンテンツを分類し、適切なポリシーを適用してもらいます。</span><span class="sxs-lookup"><span data-stu-id="8690d-p104">**Enable people in your organization to apply a retention label manually** to content in Outlook on the web, Outlook 2010 and later, OneDrive, SharePoint, and Office 365 groups. Users often know best what type of content they're working with, so they can classify it and have the appropriate policy applied.</span></span> 
    
- <span data-ttu-id="8690d-117">コンテンツに次のものが含まれている場合など、特定の条件に一致するときには、**保持ラベルをコンテンツに自動的に適用**できます。</span><span class="sxs-lookup"><span data-stu-id="8690d-117">**Apply retention labels to content automatically** if it matches specific conditions, such as when the content contains:</span></span> 
    
    - <span data-ttu-id="8690d-118">特定の種類の機密情報。</span><span class="sxs-lookup"><span data-stu-id="8690d-118">Specific types of sensitive information.</span></span>
    
    - <span data-ttu-id="8690d-119">作成したクエリに一致する特定のキーワード。</span><span class="sxs-lookup"><span data-stu-id="8690d-119">Specific keywords that match a query you create.</span></span>
    
    - <span data-ttu-id="8690d-120">トレーニング可能な分類子のパターン マッチ。</span><span class="sxs-lookup"><span data-stu-id="8690d-120">Pattern matches for a trainable classifier.</span></span>
    
  <span data-ttu-id="8690d-121">保持ラベルを自動的にコンテンツに適用する機能が重要である理由は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8690d-121">The ability to apply retention labels to content automatically is important because:</span></span>
    
     - <span data-ttu-id="8690d-122">ユーザーのトレーニングは、一部の分類方法についてのみ必要。</span><span class="sxs-lookup"><span data-stu-id="8690d-122">You don't need to train your users on all of your classifications.</span></span>
    
     - <span data-ttu-id="8690d-123">ユーザーへの依存は、一部のコンテンツを正しく分類するためにのみ必要。</span><span class="sxs-lookup"><span data-stu-id="8690d-123">You don't need to rely on users to classify all content correctly.</span></span>
    
   - <span data-ttu-id="8690d-124">ユーザーはデータ ガバナンス ポリシーについて把握する必要がなくなり、仕事に集中できる。</span><span class="sxs-lookup"><span data-stu-id="8690d-124">Users no longer need to know about data governance policies - they can instead focus on their work.</span></span>

- <span data-ttu-id="8690d-p105">メールとドキュメントの両方を含む、**Office 365 全体でレコード管理を実装**できます。保持ラベルを使用して、コンテンツをレコードとして分類できます。この場合、ラベルの変更と削除、およびコンテンツの編集と削除はできません。</span><span class="sxs-lookup"><span data-stu-id="8690d-p105">**Implement records management across Office 365**, including both email and documents. You can use a retention label to classify content as a record. When this happens, the label can't be changed or removed, and the content can't be edited or deleted.</span></span> 

- <span data-ttu-id="8690d-128">SharePoint の **ドキュメント ライブラリ、フォルダー、またはドキュメント セットに既定の保持ラベルを適用**することにより、この場所に到着するすべてのドキュメントに既定の保持ラベルが継承されるようになります。</span><span class="sxs-lookup"><span data-stu-id="8690d-128">**Apply a default retention label to a document library, folder, or document set** in SharePoint, so that all documents that arrive in that location inherit the default retention label.</span></span>  
    
<span data-ttu-id="8690d-129">Microsoft 365 コンプライアンス センター、Microsoft 365 セキュリティ センター、または Office 365 セキュリティ/コンプライアンス センターで保持ラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="8690d-129">You create retention labels in the Microsoft 365 compliance center, Microsoft 365 security center, or Office 365 Security & Compliance Center.</span></span>

## <a name="how-retention-labels-work-with-retention-label-policies"></a><span data-ttu-id="8690d-130">保持ラベル ポリシーでの保持ラベルのしくみ</span><span class="sxs-lookup"><span data-stu-id="8690d-130">How retention labels work with retention label policies</span></span>

<span data-ttu-id="8690d-131">組織のユーザーがコンテンツを分類できるよう保持ラベルを提供するには、次の 2 つの手順を行います。まず、保持ラベルを作成して、ユーザーが使用できるように指定の場所に発行します。</span><span class="sxs-lookup"><span data-stu-id="8690d-131">Making retention labels available to people in your organization so that they can classify content is a two-step process: first you create the retention labels, and then you publish them to the locations you choose.</span></span> <span data-ttu-id="8690d-132">保持ラベルを発行すると、保持ラベル ポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="8690d-132">When you publish retention labels, a retention label policy gets created.</span></span>
  
![ラベルの役割とタスクの図](../media/4082bc7d-c04c-4b9a-8a26-7f12565d3311.png)
  
<span data-ttu-id="8690d-134">保持ラベルは依存しない、再利用可能な文書パーツで、1 つ以上の保持ラベル ポリシーに含まれています。</span><span class="sxs-lookup"><span data-stu-id="8690d-134">Retention labels are independent, reusable building blocks that are included in one or more retention label policies.</span></span> <span data-ttu-id="8690d-135">保持ラベル ポリシーの主な目的は、保持ラベルのセットをグループ化して、ラベルを表示する場所を特定することです。</span><span class="sxs-lookup"><span data-stu-id="8690d-135">The primary purpose of a retention label policy is to group a set of retention labels and specify the locations where you want those labels to appear.</span></span>
  
![ラベル、ラベル ポリシー、および場所の図](../media/eee42516-adf0-4664-b5ab-76727a9a3511.png)
  
1. <span data-ttu-id="8690d-137">保持ラベルを発行すると、保持ラベルは保持ラベル ポリシーに含まれるようになります。</span><span class="sxs-lookup"><span data-stu-id="8690d-137">When you publish retention labels, they're included in a retention label policy.</span></span> <span data-ttu-id="8690d-138">保持ラベル名は変更することができないため、作成後に編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="8690d-138">Retention label names are immutable, which means that they and cannot be edited after they're created.</span></span>


2. <span data-ttu-id="8690d-139">1 つの保持ラベルは、複数の保持ラベル ポリシーに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="8690d-139">A single retention label can be included in many retention label policies.</span></span>

3. <span data-ttu-id="8690d-140">また、1 つの場所は、複数の保持ラベル ポリシーに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="8690d-140">A single location can also be included in many retention label policies.</span></span>    
    
3. <span data-ttu-id="8690d-141">保持ラベル ポリシーは保持ラベルを発行する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="8690d-141">Retention label policies specify the locations to publish the retention labels.</span></span>
    
## <a name="only-one-retention-label-at-a-time"></a><span data-ttu-id="8690d-142">一度に 1 つの保持ラベルのみ</span><span class="sxs-lookup"><span data-stu-id="8690d-142">Only one retention label at a time</span></span>

<span data-ttu-id="8690d-143">メールやドキュメントなどのコンテンツに一度に割り当てられる保持ラベルは 1 つのみです。これを知っておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="8690d-143">It's important to know that content like an email or document can have only a single retention label assigned to it at a time:</span></span>
  
- <span data-ttu-id="8690d-144">エンド ユーザーが手動で割り当てた保持ラベルの場合、ユーザーは割り当てられている保持ラベルを削除または変更できます。</span><span class="sxs-lookup"><span data-stu-id="8690d-144">For retention labels assigned manually by end users, people can remove or change the retention label that's assigned.</span></span>
    
- <span data-ttu-id="8690d-145">コンテンツに自動適用ラベルが割り当てられている場合は、自動適用ラベルをエンド ユーザーが手動で割り当てた保持ラベルに置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="8690d-145">If content has an auto-apply label assigned, an auto-apply label can be replaced by a retention label assigned manually by an end user.</span></span>
    
- <span data-ttu-id="8690d-146">コンテンツにエンド ユーザーが手動で割り当てた保持ラベルがある場合は、自動適用ラベルと手動で割り当てられた保持ラベルを置き換えることはできません。</span><span class="sxs-lookup"><span data-stu-id="8690d-146">If content has a retention label assigned manually by an end user, an auto-apply label cannot replace the manually assigned retention label.</span></span>
    
- <span data-ttu-id="8690d-147">自動適用ラベルを割り当てるルールが複数あり、コンテンツが複数のルールの条件を満たしている場合、最も古いルールの保持ラベルが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="8690d-147">If there are multiple rules that assign an auto-apply label and content meets the conditions of multiple rules, the retention label for the oldest rule is assigned.</span></span>
    
<span data-ttu-id="8690d-p109">手動で割り当てたラベルは明示的に割り当てられ、自動適用のラベルは暗黙的に割り当てられます。明示的な保持ラベルは暗黙的なラベルよりも優先されます。詳細については、後続の「[保持の原則、すなわち優先順位について](#the-principles-of-retention-or-what-takes-precedence)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8690d-p109">Manually assigned labels are explicitly assigned; auto-apply labels are implicitly assigned; an explicit retention label takes precedence over an implicit label. For more information, see the below section on [The principles of retention, or what takes precedence?](#the-principles-of-retention-or-what-takes-precedence).</span></span>

<span data-ttu-id="8690d-150">このセクションのすべての情報は、保持ラベルにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="8690d-150">All the information in this section applies only to retention labels.</span></span> <span data-ttu-id="8690d-151">コンテンツのアイテムには、1 つの保持ラベルの他に 1 つの秘密度ラベルを適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="8690d-151">Note that an item of content can also have one sensitivity label applied to it, in addition to one retention label.</span></span>
  
## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="8690d-152">保持ラベルが有効になるまでの所要時間</span><span class="sxs-lookup"><span data-stu-id="8690d-152">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="8690d-153">保持ラベルを発行または自動適用しても、すぐには有効になりません。</span><span class="sxs-lookup"><span data-stu-id="8690d-153">When you publish or auto-apply retention labels, they don't take effect immediately:</span></span>
  
1. <span data-ttu-id="8690d-154">まず、ラベル ポリシーを管理センターからポリシー内の場所に同期させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="8690d-154">First the label policy needs to be synced from the admin center to the locations in the policy.</span></span>
    
2. <span data-ttu-id="8690d-155">また、発行された保持ラベルをエンド ユーザーが利用したり、ラベルをコンテンツに自動適用したりできるようになるまでには、場所で時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="8690d-155">Then the location may require time to make published retention labels available to end users or time to auto-apply labels to content.</span></span> <span data-ttu-id="8690d-156">これにかかる時間は、場所と保持ラベルの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="8690d-156">How long this takes depends on the location and type of retention label.</span></span>
    
### <a name="published-retention-labels"></a><span data-ttu-id="8690d-157">発行された保持ラベル</span><span class="sxs-lookup"><span data-stu-id="8690d-157">Published retention labels</span></span>

<span data-ttu-id="8690d-p112">SharePoint または OneDrive に保持ラベルを発行する場合、保持ラベルがエンド ユーザーに表示されるまでに 1 日かかる場合があります。また、Exchange に保持ラベルを発行する場合は、保持ラベルがエンド ユーザーに表示するまでに 7 日間かかる場合があり、さらにメールボックスには少なくとも 10 MB のデータが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8690d-p112">If you publish retention labels to SharePoint or OneDrive, it can take one day for those retention labels to appear for end users. In addition, if you publish retention labels to Exchange, it can take 7 days for those retention labels to appear for end users, and the mailbox needs to contain at least 10 MB of data.</span></span>
  
![手動ラベルが有効になるタイミングの図](../media/b19f3a10-f625-45bf-9a53-dd14df02ae7c.png)
  
### <a name="auto-apply-retention-labels"></a><span data-ttu-id="8690d-161">自動適用の保持ラベル</span><span class="sxs-lookup"><span data-stu-id="8690d-161">Auto-apply retention labels</span></span>

<span data-ttu-id="8690d-162">特定の条件に一致するコンテンツに保持ラベルを自動適用する場合、条件に一致するすべての既存コンテンツに保持ラベルが適用されるまでに 7 日間かかります。</span><span class="sxs-lookup"><span data-stu-id="8690d-162">If you auto-apply retention labels to content matching specific conditions, it can take seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![自動適用ラベルが有効になるタイミングの図](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
### <a name="how-to-check-on-the-status-of-retention-labels-published-to-exchange"></a><span data-ttu-id="8690d-164">Exchange に発行された保持ラベルの状態を確認する方法</span><span class="sxs-lookup"><span data-stu-id="8690d-164">How to check on the status of retention labels published to Exchange</span></span>

<span data-ttu-id="8690d-p113">Exchange Online では、7 日ごとに実行されるプロセスによってエンド ユーザーが保持ラベルを利用できるようになります。Powershell を使用することで、このプロセスが最後に実行された日時を確認できるため、次に実行される日時を判断できます。</span><span class="sxs-lookup"><span data-stu-id="8690d-p113">In Exchange Online, retention labels are made available to end users by a process that runs every seven days. By using Powershell, you can see when this process last ran and thus determine when it will run again.</span></span>
  
1. <span data-ttu-id="8690d-167">[Exchange Online PowerShell に接続します](https://go.microsoft.com/fwlink/?linkid=799773)。</span><span class="sxs-lookup"><span data-stu-id="8690d-167">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=799773).</span></span>
    
2. <span data-ttu-id="8690d-168">これらのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8690d-168">Run these commands.</span></span>
    
   ```powershell
   $logProps = Export-MailboxDiagnosticLogs <user> -ExtendedProperties
   ```

   ```powershell
   $xmlprops = [xml]($logProps.MailboxLog)
   ```

   ```powershell
   $xmlprops.Properties.MailboxTable.Property | ? {$_.Name -like "ELC*"}
   ```

<span data-ttu-id="8690d-169">結果の中で、`ELCLastSuccessTimeStamp` (UTC) プロパティは、システムがメールボックスを最後に処理した日時を示しています。</span><span class="sxs-lookup"><span data-stu-id="8690d-169">In the results, the `ELCLastSuccessTimeStamp` (UTC) property shows when the system last processed your mailbox.</span></span> <span data-ttu-id="8690d-170">ポリシーの作成後に処理がまだ行われていない場合は、ラベルは表示されません。</span><span class="sxs-lookup"><span data-stu-id="8690d-170">If it has not happened since the time you created the policy, the labels are not going to appear.</span></span> <span data-ttu-id="8690d-171">処理を強制的に行うには、`Start-ManagedFolderAssistant -Identity <user>` を実行します。</span><span class="sxs-lookup"><span data-stu-id="8690d-171">To force processing, run  `Start-ManagedFolderAssistant -Identity <user>`.</span></span>
    
<span data-ttu-id="8690d-172">Outlook on the web にラベルが表示されると思われるにもかかわらず、ラベルが表示されない場合は、ブラウザーのキャッシュを必ず消去してください (CTRL + F5)。</span><span class="sxs-lookup"><span data-stu-id="8690d-172">If labels aren't appearing in Outlook on the web and you think they should be, make sure to clear the cache in your browser (CTRL+F5).</span></span>
    
## <a name="retention-label-policies-and-locations"></a><span data-ttu-id="8690d-173">保持ラベルのポリシーと場所</span><span class="sxs-lookup"><span data-stu-id="8690d-173">Retention label policies and locations</span></span>

<span data-ttu-id="8690d-174">保持ラベルの内容に応じて、多様な種類の保持ラベルをさまざまな場所に発行できます。</span><span class="sxs-lookup"><span data-stu-id="8690d-174">Different types of retention labels can be published to different locations, depending on what the retention label does.</span></span>
  
|<span data-ttu-id="8690d-175">**保持ラベルの種類**</span><span class="sxs-lookup"><span data-stu-id="8690d-175">**If the retention label is…**</span></span>|<span data-ttu-id="8690d-176">**ラベル ポリシーの適用先**</span><span class="sxs-lookup"><span data-stu-id="8690d-176">**Then the label policy can be applied to…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8690d-177">エンド ユーザーに発行されたラベル</span><span class="sxs-lookup"><span data-stu-id="8690d-177">Published to end users</span></span>  <br/> |<span data-ttu-id="8690d-178">Exchange、SharePoint、OneDrive、Office 365 グループ</span><span class="sxs-lookup"><span data-stu-id="8690d-178">Exchange, SharePoint, OneDrive, Office 365 groups</span></span>  <br/> |
|<span data-ttu-id="8690d-179">機密情報の種類に基づいて自動適用されたラベル</span><span class="sxs-lookup"><span data-stu-id="8690d-179">Auto-applied based on sensitive information types</span></span>  <br/> |<span data-ttu-id="8690d-180">Exchange (すべてのメールボックスのみ)、SharePoint、OneDrive</span><span class="sxs-lookup"><span data-stu-id="8690d-180">Exchange (all mailboxes only), SharePoint, OneDrive</span></span>  <br/> |
|<span data-ttu-id="8690d-181">クエリに基づいて自動適用されたラベル</span><span class="sxs-lookup"><span data-stu-id="8690d-181">Auto-applied based on a query</span></span>  <br/> |<span data-ttu-id="8690d-182">Exchange、SharePoint、OneDrive、Office 365 グループ</span><span class="sxs-lookup"><span data-stu-id="8690d-182">Exchange, SharePoint, OneDrive, Office 365 groups</span></span>  <br/> |
   
<span data-ttu-id="8690d-183">Exchange の自動適用保持ラベル (クエリと機密情報の両方の種類) は、新しく送信されたメッセージ (送信中のデータ) のみに適用され、現在メールボックスにあるすべてのアイテム (保存中のデータ) には適用されません。</span><span class="sxs-lookup"><span data-stu-id="8690d-183">In Exchange, auto-apply retention labels (for both queries and sensitive information types) are applied only to messages newly sent (data in transit), not to all items currently in the mailbox (data at rest).</span></span> <span data-ttu-id="8690d-184">また、機密情報の種類の自動適用保持ラベルはすべてのメールボックスのみに適用でき、特定のメールボックスを選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="8690d-184">Also, auto-apply retention labels for sensitive information types can apply only to all mailboxes; you can't select the specific mailboxes.</span></span>
  
<span data-ttu-id="8690d-185">Exchange パブリック フォルダーと Skype ではラベルはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8690d-185">Exchange public folders and Skype do not support labels.</span></span>
  
## <a name="how-retention-labels-enforce-retention"></a><span data-ttu-id="8690d-186">保持ラベルによる強制保持のしくみ</span><span class="sxs-lookup"><span data-stu-id="8690d-186">How retention labels enforce retention</span></span>

<span data-ttu-id="8690d-187">保持ラベルで、アイテム保持ポリシーが行うのと同じ操作を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="8690d-187">Retention labels can enforce the same retention actions that a retention policy can.</span></span> <span data-ttu-id="8690d-188">保持ラベルを使用して、高度なコンテンツ プラン (またはファイル プラン) を実装できます。</span><span class="sxs-lookup"><span data-stu-id="8690d-188">You can use retention labels to implement a sophisticated content plan (or file plan).</span></span> <span data-ttu-id="8690d-189">保持機能についての詳細は、「[アイテム保持ポリシーの概要](retention-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8690d-189">For more information on how retention works, see [Overview of retention policies](retention-policies.md).</span></span>
  
<span data-ttu-id="8690d-p117">さらに、保持ラベルには 2 つの保持オプションがあります。これらのオプションは保持ラベルでのみ使用でき、アイテム保持ポリシーでは使用できません。保持ラベルを使用すると、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="8690d-p117">In addition, a retention label has two retention options that are available only in a retention label and not in a retention policy. With a retention label, you can:</span></span>
  
- <span data-ttu-id="8690d-p118">保持期間の終了時に廃棄レビューをトリガーし、SharePoint と OneDrive のドキュメントを確認してから削除するようにできます。詳細については、「[廃棄レビューの概要](disposition-reviews.md)」をご参照ください。</span><span class="sxs-lookup"><span data-stu-id="8690d-p118">Trigger a disposition review at the end of the retention period, so that SharePoint and OneDrive documents must be reviewed before they can be deleted. For more information, see [Overview of disposition reviews](disposition-reviews.md).</span></span>
    
- <span data-ttu-id="8690d-194">コンテンツの作成日または最終変更日時ではなく、コンテンツがラベル付けされた時点から保持期間を開始できます。</span><span class="sxs-lookup"><span data-stu-id="8690d-194">Start the retention period from when the content was labeled, instead of the age of the content or when it was last modified.</span></span> <span data-ttu-id="8690d-195">このオプションは、SharePoint サイトおよび OneDrive アカウントのコンテンツにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="8690d-195">This option applies only to content in SharePoint sites and OneDrive accounts.</span></span> <span data-ttu-id="8690d-196">Exchange メールの場合、オプションのどれを選んだかを問わず、保持期間は常にメッセージが送受信された日付に基づきます。</span><span class="sxs-lookup"><span data-stu-id="8690d-196">For Exchange email, the retention period is always based on the date when the message was sent or received, no matter which option you choose here.</span></span>
    
![ラベル固有のオプションによる保持設定](../media/c49118c9-6279-4661-94db-deffa76e27ac.png)
  
## <a name="where-published-retention-labels-can-appear-to-end-users"></a><span data-ttu-id="8690d-198">発行済みラベルをエンド ユーザー向けに表示できる場所</span><span class="sxs-lookup"><span data-stu-id="8690d-198">Where published retention labels can appear to end users</span></span>

<span data-ttu-id="8690d-199">保持ラベルがエンド ユーザーによってコンテンツに割り当てられる場合、保持ラベルは次の場所に発行できます。</span><span class="sxs-lookup"><span data-stu-id="8690d-199">If your retention label will be assigned to content by end users, you can publish it to:</span></span>
  
- <span data-ttu-id="8690d-200">Outlook on the web</span><span class="sxs-lookup"><span data-stu-id="8690d-200">Outlook on the web</span></span>
    
- <span data-ttu-id="8690d-201">Outlook 2010 以降</span><span class="sxs-lookup"><span data-stu-id="8690d-201">Outlook 2010 and later</span></span>
    
- <span data-ttu-id="8690d-202">OneDrive</span><span class="sxs-lookup"><span data-stu-id="8690d-202">OneDrive</span></span>
    
- <span data-ttu-id="8690d-203">SharePoint</span><span class="sxs-lookup"><span data-stu-id="8690d-203">SharePoint</span></span>
    
- <span data-ttu-id="8690d-204">Office 365 グループ (Outlook on the web のグループ サイトとグループ メールボックスの両方)</span><span class="sxs-lookup"><span data-stu-id="8690d-204">Office 365 groups (both the group site and group mailbox in Outlook on the web)</span></span>
    
<span data-ttu-id="8690d-205">次のセクションでは、さまざまなアプリで組織内のユーザーに対してラベルがどのように表示されるかを説明します。</span><span class="sxs-lookup"><span data-stu-id="8690d-205">The sections that follow explain how labels appear in different apps to people in your organization.</span></span>
  
### <a name="outlook-on-the-web"></a><span data-ttu-id="8690d-206">Outlook on the web</span><span class="sxs-lookup"><span data-stu-id="8690d-206">Outlook on the web</span></span>

<span data-ttu-id="8690d-207">Outlook on the web でアイテムにラベルを付けるには、アイテム \>**[ポリシーの割り当て]**\> の順に右クリックして、保持ラベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="8690d-207">To label an item in Outlook on the web, right-click the item \> **Assign policy** \> choose the retention label.</span></span> 
  
![Outlook on the web の [ポリシーの割り当て] メニュー](../media/146a23cf-e478-4595-b2e8-f707fc4e6ea3.png)
  
<span data-ttu-id="8690d-p120">保持ラベルが適用されると、アイテムの上部にその保持ラベルとラベルが実行するアクションが表示されます。メールが分類され、保持期間が関連付けられている場合、メールの有効期限が一目でわかります。</span><span class="sxs-lookup"><span data-stu-id="8690d-p120">After the retention label is applied, you can view that retention label and what action it takes at the top of the item. If an email is classified and has an associated retention period, you can know at a glance when the email will expire.</span></span>
  
![メールに割り当てられたラベル (Outlook on the web)](../media/16f6c91b-5eab-4574-9d13-6d12be00a783.png)
  
<span data-ttu-id="8690d-212">保持ラベルはフォルダーに適用することもできます。その場合は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8690d-212">You can also apply retention labels to folders, in which case:</span></span>
  
- <span data-ttu-id="8690d-p121">明示的に保持ラベルが適用されているアイテムを**除き**、フォルダー内のすべてのアイテムに同じ保持ラベルが自動的に設定されます。明示的にラベル付けされたアイテムは、既存の保持ラベルを維持します。詳細については、保持の原則に関する後続のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8690d-p121">All items in the folder automatically get the same retention label, **except** for items that have had a retention label applied explicitly to them. Explicitly labeled items keep their existing retention label. For more information, see the below section on the principles of retention.</span></span> 
    
- <span data-ttu-id="8690d-216">フォルダーの既定の保持ラベルを変更または削除すると、明示的な保持ラベルを持つアイテムを**除き**、フォルダー内にあるすべてのアイテムの保持ラベルも変更または削除されます。</span><span class="sxs-lookup"><span data-stu-id="8690d-216">If you change or remove the default retention label for a folder, the retention label's also changed or removed for all items in the folder, **except** items with explicit retention labels.</span></span> 
    
- <span data-ttu-id="8690d-217">既定の保持ラベルを持つアイテムをあるフォルダーから異なる既定の保持ラベルを持つ別のフォルダーに移動すると、そのアイテムには新しい既定の保持ラベルが設定されます。</span><span class="sxs-lookup"><span data-stu-id="8690d-217">If you move an item with a default retention label from one folder to another folder with a different default retention label, the item gets the new default retention label.</span></span>
    
- <span data-ttu-id="8690d-218">既定の保持ラベルを持つアイテムをあるフォルダーから既定の保持ラベルがない別のフォルダーに移動すると、以前の既定の保持ラベルが削除されます。</span><span class="sxs-lookup"><span data-stu-id="8690d-218">If you move an item with a default retention label from one folder to another folder with no default retention label, the old default retention label is removed.</span></span>
    
### <a name="outlook-2010-and-later"></a><span data-ttu-id="8690d-219">Outlook 2010 以降</span><span class="sxs-lookup"><span data-stu-id="8690d-219">Outlook 2010 and later</span></span>

<span data-ttu-id="8690d-220">Outlook デスクトップ クライアントでアイテムにラベルを付けるには、アイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="8690d-220">To label an item in the Outlook desktop client, select the item.</span></span> <span data-ttu-id="8690d-221">リボンの **[ホーム]** タブで、**[ポリシーの割り当て]** をクリックし、保持ラベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="8690d-221">On the **Home** tab on the ribbon, click **Assign Policy**, and then choose the retention label.</span></span> 
  
![[ポリシーの割り当て] ボタン](../media/30684dea-dd73-4e4a-9185-8e29f403b6ca.png)
  
<span data-ttu-id="8690d-223">アイテムを右クリックし、コンテキスト メニューの **[ポリシーの割り当て]** をクリックし、保持ラベルを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="8690d-223">You can also right-click an item, click **Assign Policy** in the context menu, and then choose the retention label.</span></span> 

<span data-ttu-id="8690d-224">保持ラベルを適用すると、アイテムの上部でその保持ラベルとラベルで行える操作が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8690d-224">After the retention label is applied, you can view that retention label and what action it takes at the top of the item.</span></span> <span data-ttu-id="8690d-225">保持期間が関連付けられている保持ラベルがメールに含まれている場合は、メールの有効期間を一目で確認できます。</span><span class="sxs-lookup"><span data-stu-id="8690d-225">If an email has a retention label applied that has an associated retention period, you can see at a glance when the email expires.</span></span>
  
<span data-ttu-id="8690d-226">保持ラベルはフォルダーに適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="8690d-226">You can also apply retention labels to folders.</span></span> <span data-ttu-id="8690d-227">これは、Outlook on the web の場合と同様に、Outlook 2010 以降のバージョンでも機能します。</span><span class="sxs-lookup"><span data-stu-id="8690d-227">This works the same in Outlook 2010 and later as it does in Outlook on the web.</span></span> <span data-ttu-id="8690d-228">詳細については、前のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8690d-228">See the previous section for more info.</span></span>
  
### <a name="onedrive-and-sharepoint"></a><span data-ttu-id="8690d-229">OneDrive と SharePoint</span><span class="sxs-lookup"><span data-stu-id="8690d-229">OneDrive and SharePoint</span></span>

<span data-ttu-id="8690d-230">OneDrive または SharePoint でドキュメント (OneNote ファイルを含む) にラベルを付けるには、右上隅のアイテム \> を選択し、[**詳細ウィンドウを開く**] ![情報ウィンドウ アイコン](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) \> [**保持ラベルを適用**] \> の順に移動し保持ラベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="8690d-230">To label a document (including OneNote files) in OneDrive or SharePoint, select the item \> in the upper-right corner, choose **Open the details pane**![Information pane icon](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) \> **Apply retention label** \> choose the retention label.</span></span> 
  
<span data-ttu-id="8690d-231">フォルダーまたはドキュメントのセットに保持ラベルを適用することもできます。また、ドキュメント ライブラリに対して既定の保持ラベルを設定できます。</span><span class="sxs-lookup"><span data-stu-id="8690d-231">You can also apply a retention label to a folder or document set, and you can set a default retention label for a document library.</span></span> <span data-ttu-id="8690d-232">詳細については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8690d-232">See the section below for more information.</span></span>
  
![SharePoint のアイテムに対するラベル リストの適用](../media/151cc83c-da57-45b0-9cd1-fd2f28a31083.png)
  
<span data-ttu-id="8690d-234">アイテムに保持ラベルが適用されると、そのアイテムの選択時に、詳細ウィンドウにラベルを表示できます。</span><span class="sxs-lookup"><span data-stu-id="8690d-234">After a retention label is applied to an item, you can view it in the details pane when that item's selected.</span></span>
  
![詳細ウィンドウに表示される適用されたラベル](../media/d06e585e-29f7-4c8c-afef-629c97268b8e.png)
  
<span data-ttu-id="8690d-p126">**[ラベル]** 列または **[アイテムがレコード]** 列を含むライブラリのビューを作成して、すべてのアイテムに割り当てられた保持ラベルとレコードであるアイテムを一目で確認できるようにすることも可能です。ただし、**[アイテムがレコード]** 列を使用してビューをフィルターすることはできません。</span><span class="sxs-lookup"><span data-stu-id="8690d-p126">You can also create a view of the library that contains the **Labels** column or **Item is a Record** column, so that you can see at a glance the retention labels assigned to all items and which items are records. Note, however, that you can't filter the view by the **Item is a Record** column.</span></span> 
  
![カスタム ビューで表示されるラベルのライブラリの列](../media/e3392627-c0a3-405e-bb57-55f27c34cfdd.png)
  
### <a name="office-365-groups"></a><span data-ttu-id="8690d-239">Office 365 グループ</span><span class="sxs-lookup"><span data-stu-id="8690d-239">Office 365 groups</span></span>

<span data-ttu-id="8690d-p127">Office 365 グループに保持ラベルを発行すると、保持ラベルは Outlook on the web のグループ サイトとグループ メールボックスの両方に表示されます。コンテンツに保持ラベルを適用する場合のエクスペリエンスは、上記のメールとドキュメントの場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="8690d-p127">When you publish retention labels to an Office 365 group, the retention labels appear in both the group site and group mailbox in Outlook on the web. The experience of applying a retention label to content is identical to that shown above for email and documents.</span></span>

<span data-ttu-id="8690d-p128">Office 365 グループのコンテンツを保持するには、Office 365 グループの場所を使用する必要があります。Office 365 グループには Exchange メールボックスがありますが、Exchange の場所全体が含まれるアイテム保持ポリシーには、Office 365 グループのメールボックスのコンテンツは含まれません。</span><span class="sxs-lookup"><span data-stu-id="8690d-p128">To retain content for an Office 365 group, you need to use the Office 365 groups location. Even though an Office 365 group has an Exchange mailbox, a retention policy that includes the entire Exchange location won't include content in Office 365 group mailboxes.</span></span>

<span data-ttu-id="8690d-244">また、Exchange の場所を使用して、特定のグループ メールボックスを含めたり、除外したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="8690d-244">In addition, it's not possible to use the Exchange location to include or exclude a specific group mailbox.</span></span> <span data-ttu-id="8690d-245">最初は Exchange の場所でグループ メールボックスを選択できますが、アイテム保持ポリシーを保存しようとすると、Exchange の場所では "RemoteGroupMailbox" を選択できないことを示すエラーを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="8690d-245">Although the Exchange location initially allows a group mailbox to be selected, when you try to save the retention policy, you receive an error that "RemoteGroupMailbox" is not a valid selection for the Exchange location.</span></span>
  
## <a name="applying-a-retention-label-automatically-based-on-conditions"></a><span data-ttu-id="8690d-246">条件に基づいた保持ラベルの自動適用</span><span class="sxs-lookup"><span data-stu-id="8690d-246">Applying a retention label automatically based on conditions</span></span>

<span data-ttu-id="8690d-247">保持ラベルの最も強力な機能の 1 つは、特定の条件に一致したコンテンツに自動的にラベルを適用することです。</span><span class="sxs-lookup"><span data-stu-id="8690d-247">One of the most powerful features of retention labels is the ability to apply them automatically to content that matches certain conditions.</span></span> <span data-ttu-id="8690d-248">この場合、組織内のユーザーが保持ラベルを適用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8690d-248">In this case, people in your organization don't need to apply the retention labels.</span></span> <span data-ttu-id="8690d-249">Office 365 が行います。</span><span class="sxs-lookup"><span data-stu-id="8690d-249">Office 365 does the work for them.</span></span>
  
![自動適用ラベルの役割とタスクの図](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)
  
<span data-ttu-id="8690d-251">自動適用の保持ラベルが強力な機能である理由は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8690d-251">Auto-apply retention labels are powerful because:</span></span>
  
- <span data-ttu-id="8690d-252">ユーザーのトレーニングは、一部の分類方法についてのみ必要。</span><span class="sxs-lookup"><span data-stu-id="8690d-252">You don't need to train your users on all of your classifications.</span></span>
    
- <span data-ttu-id="8690d-253">ユーザーへの依存は、一部のコンテンツを正しく分類するためにのみ必要。</span><span class="sxs-lookup"><span data-stu-id="8690d-253">You don't need to rely on users to classify all content correctly.</span></span>
    
- <span data-ttu-id="8690d-254">ユーザーはデータ ガバナンス ポリシーについて把握する必要がなくなるので、仕事に集中できる。</span><span class="sxs-lookup"><span data-stu-id="8690d-254">Users no longer need to know about data governance policies - they can focus on their work.</span></span>
    
<span data-ttu-id="8690d-255">コンテンツに次の内容が含まれている場合は、保持ラベルを自動的にコンテンツに適用するように選択できます。</span><span class="sxs-lookup"><span data-stu-id="8690d-255">You can choose to apply retention labels to content automatically when that content contains:</span></span>
  
- [<span data-ttu-id="8690d-256">特定の種類の機密情報</span><span class="sxs-lookup"><span data-stu-id="8690d-256">Specific types of sensitive information</span></span>](#auto-apply-retention-labels-to-content-with-specific-types-of-sensitive-information)
    
- [<span data-ttu-id="8690d-257">作成したクエリに一致する特定のキーワード</span><span class="sxs-lookup"><span data-stu-id="8690d-257">Specific keywords that match a query you create</span></span>](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [<span data-ttu-id="8690d-258">トレーニング可能な分類子の一致</span><span class="sxs-lookup"><span data-stu-id="8690d-258">A match for trainable classifiers</span></span>](#auto-apply-labels-to-content-by-using-trainable-classifiers)
    
![自動適用ラベルの [条件選択] ページ](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)

<span data-ttu-id="8690d-260">構成した条件に一致するすべてのコンテンツに保持ラベルを自動的に適用するには、最大 7 日かかります。</span><span class="sxs-lookup"><span data-stu-id="8690d-260">It can take up to seven days for auto-apply retention labels to be applied to all content that matches the conditions you've configured.</span></span>
  
> [!TIP]
> <span data-ttu-id="8690d-261">SharePont の管理プロパティを使用して保持ラベルを自動適用し、イベント ドリブンの保持を実装する詳細なシナリオについては、「[保持ラベルを使用して SharePoint ドキュメントのライフサイクルを管理する](auto-apply-retention-labels-scenario.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8690d-261">See [Manage the lifecycle of SharePoint documents with retention labels](auto-apply-retention-labels-scenario.md) for a detailed scenario about using managed properties in SharePoint to auto-apply retention labels and implement event-driven retention.</span></span>

### <a name="auto-apply-retention-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="8690d-262">特定の種類の機密情報によるコンテンツへの保持ラベルの自動適用</span><span class="sxs-lookup"><span data-stu-id="8690d-262">Auto-apply retention labels to content with specific types of sensitive information</span></span>

<span data-ttu-id="8690d-263">機密情報用に自動適用の保持ラベルを作成するときに、データ損失防止 (DLP) ポリシーを作成するときと同じポリシー テンプレートの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8690d-263">When you create auto-apply retention labels for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="8690d-264">各ポリシー テンプレートは、特定の種類の機密情報を見つけるように事前に設定されています。</span><span class="sxs-lookup"><span data-stu-id="8690d-264">Each policy template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="8690d-265">たとえば、次に示すテンプレートは、米国の ITIN、SSN、パスポート番号を探します。</span><span class="sxs-lookup"><span data-stu-id="8690d-265">For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers.</span></span> <span data-ttu-id="8690d-266">DLP の詳細については、「[データ損失防止ポリシーの概要](data-loss-prevention-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8690d-266">To learn more about DLP, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
![機密情報の種類によるポリシー テンプレート](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)
  
<span data-ttu-id="8690d-p132">ポリシー テンプレートを選択すると、すべての種類の機密情報を追加または削除したり、インスタンス数と一致精度を変更したりできます。ここに示す例では、保持ラベルは次の場合にのみ自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="8690d-p132">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy. In the example shown here, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="8690d-p133">コンテンツに、次の 3 種類の機密情報のいずれかに 1 から 9 個のインスタンスが含まれる場合。**最大** 値を削除して、**任意** の値に変更できます。</span><span class="sxs-lookup"><span data-stu-id="8690d-p133">The content contains between 1 and 9 instances of any of these three sensitive information types. You can delete the **max** value so that it changes to **any**.</span></span>
    
- <span data-ttu-id="8690d-p134">検出された機密情報の種類は、一致精度 (または信頼レベル) が少なくとも 75 に設定されています。多くの機密情報の種類は複数のパターンで定義されています。一致精度の高いパターンでは、より多くの証拠 (キーワード、日付、アドレスなど) が検索される必要がありますが、一致精度の低いパターンでは必要な証拠は少なくなります。簡単に言えば、一致精度の **最小** 値が低いほど、コンテンツは条件に一致しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="8690d-p134">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75. Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence. Simply put, the lower the **min** match accuracy, the easier it is for content to match the condition.</span></span> 
    
<span data-ttu-id="8690d-275">これらのオプションの詳細については、「[一致の難易度を設定するためのルールの調整](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8690d-275">For more information on these options, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![機密情報の種類を識別するためのオプション](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="8690d-277">キーワードまたは検索可能なプロパティによるコンテンツへの自動適用ラベル</span><span class="sxs-lookup"><span data-stu-id="8690d-277">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="8690d-p135">特定の条件を満たすコンテンツにラベルを自動的に適用できます。現在利用可能な条件では、特定の単語、フレーズ、または検索可能なプロパティの値を含むコンテンツへのラベルの適用がサポートされています。AND、OR、NOT などの検索演算子を使用してクエリを絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="8690d-p135">You can auto-apply labels to content that satisfies certain conditions. The conditions now available support applying a label to content that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators like AND, OR, and NOT.</span></span>

<span data-ttu-id="8690d-281">クエリ構文の詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8690d-281">For more information on query syntax, see:</span></span>

- [<span data-ttu-id="8690d-282">キーワード クエリ言語 (KQL) 構文のリファレンス</span><span class="sxs-lookup"><span data-stu-id="8690d-282">Keyword Query Language (KQL) syntax reference</span></span>](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

<span data-ttu-id="8690d-p136">クエリ ベースのラベルは検索インデックスを使用してコンテンツを特定します。有効な検索可能なプロパティの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8690d-p136">Query-based labels use the search index to identify content. For more information on valid searchable properties, see:</span></span>

- [<span data-ttu-id="8690d-285">コンテンツ検索のキーワード クエリと検索条件</span><span class="sxs-lookup"><span data-stu-id="8690d-285">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
- [<span data-ttu-id="8690d-286">クロールされたプロパティと管理プロパティの概要 (SharePoint Server)</span><span class="sxs-lookup"><span data-stu-id="8690d-286">Overview of crawled and managed properties in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

<span data-ttu-id="8690d-287">クエリの例:</span><span class="sxs-lookup"><span data-stu-id="8690d-287">Examples queries:</span></span>

- <span data-ttu-id="8690d-288">Exchange</span><span class="sxs-lookup"><span data-stu-id="8690d-288">Exchange</span></span>
    - <span data-ttu-id="8690d-289">subject:"Quarterly Financials"</span><span class="sxs-lookup"><span data-stu-id="8690d-289">subject:"Quarterly Financials"</span></span>
    - <span data-ttu-id="8690d-290">受信者: garthf</span><span class="sxs-lookup"><span data-stu-id="8690d-290">recipients:garthf</span></span><!--nolink--><span data-ttu-id="8690d-291">@contoso.com</span><span class="sxs-lookup"><span data-stu-id="8690d-291">@contoso.com</span></span>
- <span data-ttu-id="8690d-292">SharePoint および OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="8690d-292">SharePoint and OneDrive for Business</span></span>
    - <span data-ttu-id="8690d-293">contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="8690d-293">contenttype:contract</span></span>
    - <span data-ttu-id="8690d-294">site:https</span><span class="sxs-lookup"><span data-stu-id="8690d-294">site:https</span></span><!--nolink--><span data-ttu-id="8690d-295">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="8690d-295">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span></span>

![クエリ エディター](../media/ac5b8e5e-7453-4ec7-905c-160df57298d3.png)


### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="8690d-297">トレーニング可能な分類子を使用して、ラベルをコンテンツに自動的に適用する</span><span class="sxs-lookup"><span data-stu-id="8690d-297">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="8690d-298">トレーニング可能な分類子のオプションを選択すると、組み込み分類子またはカスタム分類子のいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="8690d-298">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="8690d-299">組み込み分類子には、**攻撃的言語**、**履歴書**、**ソース コード**、**個人を標的にしたハラスメント**、**冒とく**、および**脅威**が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8690d-299">The built-in classifiers include **Offensive Language**, **Resumes**, **SourceCode**, **Targeted Harassment**, **Profanity**, and **Threat**:</span></span>

![トレーニング可能な分類子の選択](../media/retention-label-classifers.png)

<span data-ttu-id="8690d-301">このオプションを使用してラベルを自動的に適用するには、SharePoint Online サイトとメールボックスには少なくとも 10 MB のデータが必要です。</span><span class="sxs-lookup"><span data-stu-id="8690d-301">To automatically apply a label by using this option, SharePoint Online sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="8690d-302">トレーニング可能な分類子の詳細については、「[トレーニング可能な分類子 (プレビュー) の概要](classifier-getting-started-with.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8690d-302">For more information about trainable classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="8690d-303">構成の例については、「[組み込みの分類子を準備して使用する方法](classifier-using-a-ready-to-use-classifier.md#how-to-prepare-for-and-use-a-built-in-classifier)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8690d-303">For an example configuration, see [How to prepare for and use a built-in classifier](classifier-using-a-ready-to-use-classifier.md#how-to-prepare-for-and-use-a-built-in-classifier).</span></span>

## <a name="applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set"></a><span data-ttu-id="8690d-304">SharePoint ライブラリ、フォルダー、またはドキュメント セット内のすべてのコンテンツへの既定の保持ラベルの適用</span><span class="sxs-lookup"><span data-stu-id="8690d-304">Applying a default retention label to all content in a SharePoint library, folder, or document set</span></span>

<span data-ttu-id="8690d-305">個々のドキュメントにユーザーが保持ラベルを適用できるようにするだけでなく、既定の保持ラベルを SharePoint ライブラリ、フォルダー、またはドキュメント セットに適用して、その場所にあるすべてのドキュメントに既定の保持ラベルを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="8690d-305">In addition to enabling people to apply a retention label to individual documents, you can also apply a default retention label to a SharePoint library, folder, or document set, so that all documents in that location get the default retention label.</span></span>
  
<span data-ttu-id="8690d-306">ドキュメント ライブラリの場合、この操作はドキュメント ライブラリの **[ライブラリの設定]** ページで行います。</span><span class="sxs-lookup"><span data-stu-id="8690d-306">For a document library, this is done on the **Library settings** page for a document library.</span></span> <span data-ttu-id="8690d-307">既定の保持ラベルを選択すると、ライブラリにある既存のアイテムにも適用するか選択できます。</span><span class="sxs-lookup"><span data-stu-id="8690d-307">When you choose the default retention label, you can also choose to apply it to existing items in the library.</span></span> 
  
<span data-ttu-id="8690d-308">たとえば、マーケティング資料用のタグがあり、特定のドキュメント ライブラリにその種類のコンテンツだけが含まれていることがわかっている場合は、[マーケティング資料] タグをそのライブラリ内にあるすべてのドキュメントの既定に設定できます。</span><span class="sxs-lookup"><span data-stu-id="8690d-308">For example, if you have a tag for marketing materials, and you know a specific document library contains only that type of content, you can make the Marketing Materials tag the default for all documents in that library.</span></span>
  
![ライブラリの設定ページでのラベル オプションの適用](../media/0787d651-63dc-43b4-8768-716a5ecc64ec.png)
  
<span data-ttu-id="8690d-310">ライブラリ、フォルダー、またはドキュメント セット内にある既存のアイテムに既定の保持ラベルを適用すると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8690d-310">If you apply a default retention label to existing items in the library, folder, or document set:</span></span>
  
- <span data-ttu-id="8690d-311">ただし、明示的に保持ラベルが適用されているアイテム (レコードなど) を**除き**、ライブラリ、フォルダー、またはドキュメント セット内のすべてのアイテムには自動的に同じ保持ラベルが付けられます。</span><span class="sxs-lookup"><span data-stu-id="8690d-311">All items in the library, folder, or document set automatically get the same retention label, **except** for items that have had a retention label applied explicitly to them (such as records).</span></span> <span data-ttu-id="8690d-312">明示的にラベルが付いたアイテムは、既存のラベルを保持します。</span><span class="sxs-lookup"><span data-stu-id="8690d-312">Explicitly labeled items keep their existing label.</span></span> <span data-ttu-id="8690d-313">詳細については、下記の[保持の原則または優先順位](#the-principles-of-retention-or-what-takes-precedence)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8690d-313">For more information, see the below section on [The principles of retention, or what takes precedence](#the-principles-of-retention-or-what-takes-precedence).</span></span>
    
- <span data-ttu-id="8690d-314">ライブラリ、フォルダー、またはドキュメント セットの既定の保持ラベルを変更または削除すると、明示的な保持ラベルを持つアイテム (レコードなど) を**除き**、ライブラリ、フォルダー、またはドキュメント セット内にあるすべてのアイテムの保持ラベルも変更または削除されます。</span><span class="sxs-lookup"><span data-stu-id="8690d-314">If you change or remove the default retention label for a library, folder, or document set, the retention label is also changed or removed for all items in the library, folder, or document set, **except** items with explicit retention labels (such as records).</span></span>
    
- <span data-ttu-id="8690d-315">既定の保持ラベルを持つアイテムをあるサイト コレクション、ライブラリ、フォルダー、またはドキュメント セットから別のサイト コレクション、ライブラリ、フォルダー、または異なるラベルを持つドキュメント セットに移動すると、新しい場所に別の既定の保持ラベルが設定されていても、アイテムは既存の既定の保持ラベルを維持します。</span><span class="sxs-lookup"><span data-stu-id="8690d-315">If you move an item with a default retention label from one site collection, library, folder, or document set to another site collection, library, folder, or document set that has a different label, the item keeps its existing default retention label, even if the new location has a different default retention label.</span></span> <span data-ttu-id="8690d-316">アイテムの移動前にラベルが付いていない場合は、新しい場所の既定の保持ラベルが付けられます。</span><span class="sxs-lookup"><span data-stu-id="8690d-316">If the item does not have a label before moving, it will take on the default retention label of the new location.</span></span>

<span data-ttu-id="8690d-317">**レコード:** ライブラリ、フォルダー、またはドキュメント セットに既定のレコード ラベルを適用すると、それらの場所内のすべての項目にレコード ラベルが適用されます。</span><span class="sxs-lookup"><span data-stu-id="8690d-317">**Records:** If you apply a default record label to a library, folder, or document set, then a record label is applied to all the individual items within those locations.</span></span> <span data-ttu-id="8690d-318">新しいアイテムをレコード ラベルが付けられている場所に移動すると、そのアイテムにはレコード ラベルが付けられます。</span><span class="sxs-lookup"><span data-stu-id="8690d-318">When you move a new item into a location with a record label, that item is labeled a record.</span></span> <span data-ttu-id="8690d-319">ただし、既定の保持ラベルを、コンテンツをレコードとして宣言しないラベルに変更した場合、このアクションによりレコード ラベルが個々のアイテムから削除されることは**ありません**。これらのアイテムでは、レコード ラベルが保持されます。</span><span class="sxs-lookup"><span data-stu-id="8690d-319">However, if you change the default retention label to a label that doesn't declare content as a record, that action **does not** remove the record label from the individual items; those items retain their record label.</span></span> <span data-ttu-id="8690d-320">レコード アイテムの保持ラベルを明示的に削除または変更できるのは、サイト コレクションの管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="8690d-320">Only a site collection admin can explicitly remove or change the retention label of record items.</span></span>

<span data-ttu-id="8690d-321">コンテンツをレコードとして宣言する保持ラベルの詳細については、「[レコードの概要](records.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8690d-321">For more information about retention labels that declare content as a record, see [Overview of records](records.md).</span></span>
    
## <a name="applying-a-retention-label-to-email-by-using-rules"></a><span data-ttu-id="8690d-322">ルールを使用したメールへの保持ラベルの適用</span><span class="sxs-lookup"><span data-stu-id="8690d-322">Applying a retention label to email by using rules</span></span>

<span data-ttu-id="8690d-323">Outlook 2010 以降では、保持ラベルまたはアイテム保持ポリシーを適用するためのルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="8690d-323">In Outlook 2010 or later, you can create rules to apply a retention label or retention policy.</span></span>
  
<span data-ttu-id="8690d-324">たとえば、特定の配布グループとの間で送受信されるすべてのメッセージに対して特定の保持ラベルを適用するルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="8690d-324">For example, you can create a rule that applies a specific retention label to all messages sent to or from a specific distribution group.</span></span>
  
<span data-ttu-id="8690d-325">ルールを作成するには、アイテム \>**[ルール]**\>**[ルールの作成]**\>**[高度なオプション]**\>**[ルール ウィザード]**\>**[アイテム保持ポリシーの適用]** の順に右クリックします。</span><span class="sxs-lookup"><span data-stu-id="8690d-325">To create a rule, right-click an item \> **Rules** \> **Create Rule** \> **Advanced Options** \> **Rules Wizard** \> **apply retention policy**.</span></span>
  
![アイテム保持ポリシーを適用するオプションを含むルール ウィザード](../media/eeb2407c-15b6-4224-99cf-e0a00034d8ea.png)
  
## <a name="classifying-content-without-applying-any-actions"></a><span data-ttu-id="8690d-327">アクションを適用しないコンテンツの分類</span><span class="sxs-lookup"><span data-stu-id="8690d-327">Classifying content without applying any actions</span></span>

<span data-ttu-id="8690d-p142">保持ラベルを作成する場合、以下に示すように、保持やその他の操作を有効にすることなくラベルを作成できます。この場合、アクションを強制せずに、保持ラベルを単にテキスト ラベルとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="8690d-p142">When you create a retention label, you can do so without turning on any retention or other actions, as shown below. In this case, you can use a retention label simply as a text label, without enforcing any actions.</span></span>
  
<span data-ttu-id="8690d-330">たとえば、アクションを適用せずに「後で確認」という名前の保持ラベルを作成して、機密情報の種類を持つコンテンツまたはクエリの対象となるコンテンツにその保持ラベルを自動的に適用することができます。</span><span class="sxs-lookup"><span data-stu-id="8690d-330">For example, you can create a retention label named "Review later" with no actions, and then auto-apply that retention label to content with sensitive information types or queried content.</span></span>
  
![保持がオフになっているラベルの設定ページ](../media/17ce863b-a823-426e-aaad-83718465f762.png)
  
## <a name="using-retention-labels-for-records-management"></a><span data-ttu-id="8690d-332">レコード管理用の保持ラベルの使用</span><span class="sxs-lookup"><span data-stu-id="8690d-332">Using retention labels for records management</span></span>
    
<span data-ttu-id="8690d-333">保持ラベルを使用して、コンテンツをレコードとして宣言できます。</span><span class="sxs-lookup"><span data-stu-id="8690d-333">You can use retention labels to declare content as a record.</span></span> <span data-ttu-id="8690d-334">これにより、1 つの一貫したレコード管理戦略を Office 365 全体に実装できます。</span><span class="sxs-lookup"><span data-stu-id="8690d-334">This lets you implement a single, consistent records-management strategy across Office 365.</span></span> <span data-ttu-id="8690d-335">詳細については、「[レコードの概要](records.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8690d-335">For more information, see [Overview of records](records.md).</span></span>
  
## <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="8690d-336">DLP ポリシーでの条件としての保持ラベルの使用</span><span class="sxs-lookup"><span data-stu-id="8690d-336">Using a retention label as a condition in a DLP policy</span></span>

<span data-ttu-id="8690d-p144">保持ラベルはコンテンツに対して保持アクションを強制できます。また、保持ラベルをデータ損失防止 (DLP) ポリシーで条件として使用できます。DLP ポリシーは特定のラベルを含むコンテンツに対して、アクセスを制限するなどの他のアクションを強制できます。</span><span class="sxs-lookup"><span data-stu-id="8690d-p144">A retention label can enforce retention actions on content. In addition, you can use a retention label as a condition in a data loss prevention (DLP) policy, and the DLP policy can enforce other actions, such as restricting access, on content that contains a specific label.</span></span> 
  
<span data-ttu-id="8690d-339">詳細については、「[DLP ポリシーにおける条件としてのラベルの使用](data-loss-prevention-policies.md#using-a-label-as-a-condition-in-a-dlp-policy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8690d-339">For more information, see [Using a label as a condition in a DLP policy](data-loss-prevention-policies.md#using-a-label-as-a-condition-in-a-dlp-policy).</span></span>
  
## <a name="monitor-retention-labels"></a><span data-ttu-id="8690d-340">保持ラベルの監視</span><span class="sxs-lookup"><span data-stu-id="8690d-340">Monitor retention labels</span></span>

<span data-ttu-id="8690d-p145">保持ラベルを発行または自動適用した後、意図したとおりにラベルがコンテンツに適用されていることを確認する必要があります。保持ラベルを監視するには、次のものを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8690d-p145">After you publish or auto-apply your retention labels, you'll want to verify that they're being applied to content as you intended. To monitor your retention labels, you can use the:</span></span>
  
- <span data-ttu-id="8690d-p146">**ラベル アクティビティ エクスプローラー**。エクスプローラー (下記参照) を使用すると、過去 30 日間の SharePoint および OneDrive for Business 全体のすべてのコンテンツの保持ラベルのアクティビティをすばやく検索して表示できます。詳細については、「[ドキュメントのラベルのアクティビティを表示する](view-label-activity-for-documents.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8690d-p146">**Label Activity Explorer**. With the explorer (shown below), you can quickly search and view retention label activity for all content across SharePoint and OneDrive for Business over the past 30 days. For more information, see [View label activity for documents](view-label-activity-for-documents.md).</span></span>

- <span data-ttu-id="8690d-346">**[ラベル分析]** ページ。</span><span class="sxs-lookup"><span data-stu-id="8690d-346">**Label analytics** page.</span></span> <span data-ttu-id="8690d-347">Microsoft 365 コンプライアンス センターと Microsoft 365 セキュリティ センターでは、上位のラベルとその適用対象を簡単に表示できます。</span><span class="sxs-lookup"><span data-stu-id="8690d-347">In the Microsoft 365 compliance center and Microsoft 365 security center, you can quickly view your top labels and where they're applied.</span></span> <span data-ttu-id="8690d-348">また、特定のラベルが付いたコンテンツをすべて表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="8690d-348">You can also view all content with a specific label.</span></span> <span data-ttu-id="8690d-349">詳細については、「[ラベル分析でラベルの使用状況を表示する](label-analytics.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8690d-349">For more information, see [View label usage with label analytics](label-analytics.md).</span></span>
    
- <span data-ttu-id="8690d-p148">**データ ガバナンス レポート**。これらのレポートでは、過去 90 日間の Exchange、SharePoint および OneDrive for Business 全体のすべてのコンテンツの保持ラベルの傾向とアクティビティをすばやく表示できます。詳細については、「[データ ガバナンス レポートを表示する](view-the-data-governance-reports.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8690d-p148">**Data governance reports**. With these reports, you can quickly view retention label trends and activity for all content across Exchange, SharePoint, and OneDrive for Business over the past 90 days. For more information, see [View the data governance reports](view-the-data-governance-reports.md).</span></span>
    
![ラベル アクティビティ エクスプローラー](../media/671ca0cd-1457-40b4-9917-b663360afd95.png)
  
## <a name="using-content-search-to-find-all-content-with-a-specific-retention-label-applied-to-it"></a><span data-ttu-id="8690d-354">コンテンツ検索を使用した特定の保持ラベルが適用されたすべてのコンテンツの検索</span><span class="sxs-lookup"><span data-stu-id="8690d-354">Using Content Search to find all content with a specific retention label applied to it</span></span>

<span data-ttu-id="8690d-355">ユーザーまたは自動適用によって保持ラベルがコンテンツに割り当てられた後、コンテンツ検索を使用して、特定の保持ラベルで分類されているすべてのコンテンツを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="8690d-355">After retention labels are assigned to content, either by users or auto-applied, you can use content search to find all content that's classified with a specific retention label.</span></span>
  
<span data-ttu-id="8690d-p149">コンテンツ検索を作成する場合は、**[コンプライアンス タグ]** 条件を選択し、完全なラベル名またはラベル名の一部を入力し、ワイルドカードを使用します。詳細については、「[コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)」をご参照ください。</span><span class="sxs-lookup"><span data-stu-id="8690d-p149">When you create a content search, choose the **Compliance Tag** condition, and then enter the complete label name or part of the label name and use a wildcard. For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
![[コンプライアンス タグ] 条件](../media/82d6af16-59f8-462f-babb-c894b2917018.png)
  
## <a name="the-principles-of-retention-or-what-takes-precedence"></a><span data-ttu-id="8690d-359">保持の原則、すなわち優先順位について</span><span class="sxs-lookup"><span data-stu-id="8690d-359">The principles of retention, or what takes precedence?</span></span>

<span data-ttu-id="8690d-p150">コンテンツには複数のアイテム保持ポリシーが適用され、各ポリシーに異なるアクション (保持または削除、あるいはその両方) と保持期間が設定されている場合が多くあります。どれが優先されるのでしょうか? 概ね、あるポリシーで保持されているコンテンツを別のポリシーで完全に削除することはできないので、ご安心ください。</span><span class="sxs-lookup"><span data-stu-id="8690d-p150">It's possible or even likely that content might have several retention policies applied to it, each with a different action (retain, delete, or both) and retention period. What takes precedence? At the highest level, rest assured that content being retained by one policy can't be permanently deleted by another policy.</span></span>
  
![保持の原則の図](../media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
<span data-ttu-id="8690d-364">保持アクションが設定されたさまざまなラベルがコンテンツにどのように適用されているかを理解するには、次の保持の原則に注意してください。</span><span class="sxs-lookup"><span data-stu-id="8690d-364">To understand how different labels with retention actions are applied to content, keep these principles of retention in mind:</span></span>
  
1. <span data-ttu-id="8690d-p151">**保持の削除が優先されます。** あるアイテム保持ポリシーで 3 年後に Exchange メールを削除するように設定され、別のアイテム保持ポリシーでは Exchange メールを 5 年間保持してから削除するように設定されているとします。この場合、3 年を経過したコンテンツはすべて削除され、ユーザーには表示されなくなりますが、コンテンツは完全に削除される 5 年を経過するまで、回復可能なアイテム フォルダーに保持されます。</span><span class="sxs-lookup"><span data-stu-id="8690d-p151">**Retention wins over deletion.** Suppose that one retention policy says to delete Exchange email after three years, but another retention policy says to retain Exchange email for five years and then delete it. Any content that reaches three years old will be deleted and hidden from the users' view, but still retained in the Recoverable Items folder until the content reaches five years old, when it will be permanently deleted.</span></span> 
    
2. <span data-ttu-id="8690d-p152">**最長の保持期間が優先されます。** コンテンツを保持する複数のポリシーの対象となるコンテンツは、最長の保持期間が終了するまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="8690d-p152">**The longest retention period wins.** If content's subject to multiple policies that retain content, it will be retained until the end of the longest retention period.</span></span> 
    
3. <span data-ttu-id="8690d-p153">**明示的な包含は暗黙的な包含に優先します。** これは次を意味します。</span><span class="sxs-lookup"><span data-stu-id="8690d-p153">**Explicit inclusion wins over implicit inclusion.** This means:</span></span> 
    
    1. <span data-ttu-id="8690d-372">Exchange メールや OneDrive ドキュメントなど、ユーザーが保持設定の保持ラベルを手動でアイテムに割り当てた場合、サイトまたはメールボックス レベルで割り当てたポリシーや、ドキュメント ライブラリで割り当てた既定の保持ラベルよりも、手動で割り当てたラベルが優先されます。</span><span class="sxs-lookup"><span data-stu-id="8690d-372">If a retention label with retention settings is manually assigned by a user to an item, such as an Exchange email or OneDrive document, that retention label takes precedence over both a policy assigned at the site or mailbox level and a default retention label assigned by the document library.</span></span> <span data-ttu-id="8690d-373">たとえば、明示的な保持ラベルでは 10 年間保持し、サイトに割り当てたアイテム保持ポリシーでは 5 年間のみ保持する場合、明示的な保持ラベルが優先されます。</span><span class="sxs-lookup"><span data-stu-id="8690d-373">For example, if the explicit retention label says to retain for 10 years, but the retention policy assigned to the site says to retain for only five years, the retention label takes precedence.</span></span> <span data-ttu-id="8690d-374">自動適用の保持ラベルは、Office 365 によって自動的に適用されるため、明示的ではなく、暗黙的とされます。</span><span class="sxs-lookup"><span data-stu-id="8690d-374">Auto-applied retention labels are considered implicit, not explicit, because they're applied automatically by Office 365.</span></span>
    
    2. <span data-ttu-id="8690d-375">アイテム保持ポリシーに特定のユーザーのメールボックスまたは OneDrive for Business のアカウントなどの特定の場所が含まれている場合、そのポリシーは、すべてのユーザーのメールボックスまたは OneDrive for Business のアカウントに適用されるが、そのユーザーのメールボックスを特に含まない別の保持ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="8690d-375">If a retention policy includes a specific location, such as a specific user's mailbox or OneDrive for Business account, that policy takes precedence over another retention policy that applies to all users' mailboxes or OneDrive for Business accounts but doesn't specifically include that user's mailbox.</span></span>
    
4. <span data-ttu-id="8690d-p155">**最短の削除期間が優先されます。** 同様に、コンテンツを削除する複数のポリシー (保持なし) の対象となるコンテンツは、最短保持期間の終了時に削除されます。</span><span class="sxs-lookup"><span data-stu-id="8690d-p155">**The shortest deletion period wins.** Similarly, if content's subject to multiple policies that delete content (with no retention), it will be deleted at the end of the shortest retention period.</span></span> 
    
<span data-ttu-id="8690d-378">保持の原則は上位から下位のタイブレーク フローとして機能することを理解します。すべてのポリシーまたはラベルによって適用された複数のルールがあるレベルで同じ場合、フローは次の下位レベルに移動し、ルールが適用される優先順位を決定します。</span><span class="sxs-lookup"><span data-stu-id="8690d-378">Understand that the principles of retention work as a tie-breaking flow from top to bottom: If the rules applied by all policies or labels are the same at one level, the flow moves down to the next level to determine precedence for which rule is applied.</span></span>
  
<span data-ttu-id="8690d-p156">最終的には、アイテム保持ポリシーまたはラベルでは、電子情報開示のために保留中のコンテンツを完全に削除することはできません。保留が解除されると、コンテンツは再び上記に記載されたクリーンアップ プロセスの対象となります。</span><span class="sxs-lookup"><span data-stu-id="8690d-p156">Finally, a retention policy or label cannot permanently delete any content that's on hold for eDiscovery. When the hold is released, the content again becomes eligible for the cleanup process described above.</span></span>

### <a name="precedence-for-auto-labeling-with-trainable-classifiers"></a><span data-ttu-id="8690d-381">トレーニング可能な分類子による自動ラベル付けの優先順位</span><span class="sxs-lookup"><span data-stu-id="8690d-381">Precedence for auto-labeling with trainable classifiers</span></span>

<span data-ttu-id="8690d-382">トレーニング可能な分類子用に構成されているすべての保持ラベルに対しては、評価が同時に行われます。</span><span class="sxs-lookup"><span data-stu-id="8690d-382">All retention labels that are configured for trainable classifiers are evaluated simultaneously.</span></span> <span data-ttu-id="8690d-383">アイテムが複数のトレーニング可能な分類子によって検出された場合、次の基準に基づいて、適用する保持ラベルを決定します。</span><span class="sxs-lookup"><span data-stu-id="8690d-383">If an item is detected by more than one trainable classifier, the following criteria is used to determine which retention label to apply:</span></span>

1. <span data-ttu-id="8690d-384">保持のみまたは保持してから削除するように構成された保持ラベルは、削除のみに構成された保持ラベルよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="8690d-384">Retention labels configured for retain-only or retain and then delete have a higher priority over retention labels that are configured for delete-only.</span></span>

2. <span data-ttu-id="8690d-385">保持のみまたは保持してから削除するように構成されている保持ラベルの場合、最長の保持期間で構成されている保持ラベルが優先されます。</span><span class="sxs-lookup"><span data-stu-id="8690d-385">For retention labels that are configured for retain-only or retain and then delete, the retention label that is configured for the longest retention period wins.</span></span>

3. <span data-ttu-id="8690d-386">削除のみに構成されている保持ラベルの場合、最短期間で構成されている保持ラベルが優先されます。</span><span class="sxs-lookup"><span data-stu-id="8690d-386">For retention labels that are configured for delete-only, the retention label that has been configured for the shortest period wins.</span></span>

4. <span data-ttu-id="8690d-387">ラベルのアクションと期間が同じだけでは、優先されるラベルが決定されません。</span><span class="sxs-lookup"><span data-stu-id="8690d-387">Retention labels with the same action and the same period result in a retention label selection that is non-deterministic.</span></span>

## <a name="use-retention-labels-instead-of-these-features"></a><span data-ttu-id="8690d-388">次の機能の代わりとしての保持ラベルの使用</span><span class="sxs-lookup"><span data-stu-id="8690d-388">Use retention labels instead of these features</span></span>

<span data-ttu-id="8690d-p158">保持ラベルは、組織全体および Exchange、SharePoint、OneDrive、Office 365 グループなど Office 365 全体にわたる組織のコンテンツで簡単に使用できます。Office 365 の任意の場所でコンテンツを分類したり、レコードを管理したり必要がある場合は、保持ラベルを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8690d-p158">Retention labels can easily be made available to an entire organization and its content across Office 365, including Exchange, SharePoint, OneDrive, and Office 365 groups. If you need to classify content or manage records anywhere in Office 365, we recommend that you use retention labels.</span></span>
  
<span data-ttu-id="8690d-391">Office 365 でコンテンツの分類またはレコード管理を行うのに以前使用されていた他の機能がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="8690d-391">There are several other features that have previously been used to classify content or manage records in Office 365.</span></span> <span data-ttu-id="8690d-392">以下にその一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="8690d-392">These are listed below.</span></span> <span data-ttu-id="8690d-393">これらの機能は引き続き保持ラベルと並行して機能します。</span><span class="sxs-lookup"><span data-stu-id="8690d-393">These features will continue to work side by side with retention labels.</span></span> <span data-ttu-id="8690d-394">保持ラベルの実装が以前の機能とは異なるインスタンスがありますが、保持ラベルが進化したことで、Office 365 全体でのレコード管理が今後、改善される予定です。</span><span class="sxs-lookup"><span data-stu-id="8690d-394">While there are instances where the implementation of retention labels differs from previous features, the evolution of retention labels will drive the future of records management across Office 365.</span></span> <span data-ttu-id="8690d-395">そのため、データ ガバナンスの場合、今後はこれらの機能ではなく、保持ラベルの使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8690d-395">Therefore, moving forward, for data governance, we recommend that you use retention labels instead of these features.</span></span>
  
### <a name="exchange-online"></a><span data-ttu-id="8690d-396">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8690d-396">Exchange Online</span></span>

- <span data-ttu-id="8690d-397">[メッセージング レコード管理 (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) とも呼ばれる、[保持タグおよびアイテム保持ポリシー](https://go.microsoft.com/fwlink/?linkid=846125) (削除のみ)</span><span class="sxs-lookup"><span data-stu-id="8690d-397">[Retention tags and retention policies](https://go.microsoft.com/fwlink/?linkid=846125), also known as [messaging records management (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (Deletion only)</span></span> 
    
### <a name="sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="8690d-398">SharePoint Online と OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="8690d-398">SharePoint Online and OneDrive for Business</span></span>

- <span data-ttu-id="8690d-399">[インプレース レコード管理の構成](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (保持)</span><span class="sxs-lookup"><span data-stu-id="8690d-399">[Configuring in place records management](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (Retention)</span></span> 
    
- <span data-ttu-id="8690d-400">[レコード センターの概要](https://support.office.com/article/bae6ca5a-7b19-40e0-b433-e3613a747c2c) (保持)</span><span class="sxs-lookup"><span data-stu-id="8690d-400">[Introduction to the Records Center](https://support.office.com/article/bae6ca5a-7b19-40e0-b433-e3613a747c2c) (Retention)</span></span> 
    
- <span data-ttu-id="8690d-401">[情報管理ポリシー](intro-to-info-mgmt-policies.md) (削除のみ)</span><span class="sxs-lookup"><span data-stu-id="8690d-401">[Information management policies](intro-to-info-mgmt-policies.md) (Deletion only)</span></span> 
    
## <a name="permissions"></a><span data-ttu-id="8690d-402">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="8690d-402">Permissions</span></span>

<span data-ttu-id="8690d-403">保持ラベルを作成するコンプライアンス チームのメンバーには、セキュリティ &amp; コンプライアンス センターにアクセスする許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="8690d-403">Members of your compliance team who will create retention labels need permissions to the Security &amp; Compliance Center.</span></span> <span data-ttu-id="8690d-404">テナント管理者は、規定でこの場所にアクセスできるため、法令遵守責任者や他のユーザーにセキュリティ &amp; コンプライアンス センターへのアクセス権を付与できます。テナント管理者が持つすべてのアクセス許可を付与する必要はありません。これを行うには、セキュリティ &amp; コンプライアンス センターの [**アクセス許可**] ページに移動して、[**コンプライアンス管理者**] 役割グループを編集し、その役割グループにメンバーを追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8690d-404">By default, your tenant admin has access to this location and can give compliance officers and other people access to the Security &amp; Compliance Center, without giving them all of the permissions of a tenant admin. To do this, we recommend that you go to the **Permissions** page of the Security &amp; Compliance Center, edit the **Compliance Administrator** role group, and add members to that role group.</span></span> 
  
<span data-ttu-id="8690d-405">詳細については、「[ユーザーに Office 365 セキュリティ センター/コンプライアンス センターへのアクセス権を付与する](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8690d-405">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="8690d-p161">これらのアクセス許可は、保持ラベルとラベル ポリシーを作成して適用するときにのみ必要になります。ポリシーを適用する場合に、コンテンツへのアクセスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="8690d-p161">These permissions are required only to create and apply retention labels and a label policy. Policy enforcement does not require access to the content.</span></span>  
## <a name="find-the-powershell-cmdlets-for-labels"></a><span data-ttu-id="8690d-408">ラベルの PowerShell コマンドレットの検索</span><span class="sxs-lookup"><span data-stu-id="8690d-408">Find the PowerShell cmdlets for labels</span></span>

<span data-ttu-id="8690d-409">ラベル コマンドレットを使用するには、次を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8690d-409">To use the label cmdlets, you need to:</span></span>
  
1. [<span data-ttu-id="8690d-410">Office 365 セキュリティ センターとコンプライアンス センターの PowerShell への接続</span><span class="sxs-lookup"><span data-stu-id="8690d-410">Connect to the Office 365 Security & Compliance Center Powershell</span></span>](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)
    
2. <span data-ttu-id="8690d-411">以下の Office 365 セキュリティ センターとコンプライアンス センターのコマンドレットの使用</span><span class="sxs-lookup"><span data-stu-id="8690d-411">Use these Office 365 Security & Compliance Center cmdlets:</span></span>

  - [<span data-ttu-id="8690d-412">Get-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="8690d-412">Get-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-compliancetag)

  - [<span data-ttu-id="8690d-413">New-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="8690d-413">New-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-compliancetag)

  - [<span data-ttu-id="8690d-414">Remove-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="8690d-414">Remove-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-compliancetag)

  - [<span data-ttu-id="8690d-415">Set-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="8690d-415">Set-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-compliancetag)

  - [<span data-ttu-id="8690d-416">Enable-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="8690d-416">Enable-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/enable-compliancetagstorage)

  - [<span data-ttu-id="8690d-417">Get-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="8690d-417">Get-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-compliancetagstorage)

  - [<span data-ttu-id="8690d-418">Get-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="8690d-418">Get-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancepolicy)

  - [<span data-ttu-id="8690d-419">New-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="8690d-419">New-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancepolicy)

  - [<span data-ttu-id="8690d-420">Remove-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="8690d-420">Remove-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancepolicy)

  - [<span data-ttu-id="8690d-421">Set-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="8690d-421">Set-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancepolicy)

  - [<span data-ttu-id="8690d-422">Get-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="8690d-422">Get-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule)

  - [<span data-ttu-id="8690d-423">New-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="8690d-423">New-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancerule)

  - [<span data-ttu-id="8690d-424">Remove-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="8690d-424">Remove-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancerule)

  - [<span data-ttu-id="8690d-425">Set-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="8690d-425">Set-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancerule)
