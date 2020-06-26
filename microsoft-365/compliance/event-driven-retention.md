---
title: イベント ベースの保持の概要
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-may2020
- seo-marvel-jun2020
description: 通常、レコード管理ソリューションの一部として、特定したイベントに基づいて保持期間を開始するように保持ラベルを構成することができます。
ms.openlocfilehash: 1e716cc886e8378308054d4f2eedf961045f4486
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817806"
---
# <a name="overview-of-event-driven-retention"></a><span data-ttu-id="9dc15-103">イベント ベースの保持の概要</span><span class="sxs-lookup"><span data-stu-id="9dc15-103">Overview of event-driven retention</span></span>

><span data-ttu-id="9dc15-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="9dc15-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="9dc15-105">When you retain content, the retention period is often based on the age of the content - for example, you might retain documents for seven years after they're created and then delete them.</span><span class="sxs-lookup"><span data-stu-id="9dc15-105">When you retain content, the retention period is often based on the age of the content - for example, you might retain documents for seven years after they're created and then delete them.</span></span> <span data-ttu-id="9dc15-106">But with retention labels in Microsoft 365, you can also base a retention period on when a specific type of event occurs.</span><span class="sxs-lookup"><span data-stu-id="9dc15-106">But with retention labels in Microsoft 365, you can also base a retention period on when a specific type of event occurs.</span></span> <span data-ttu-id="9dc15-107">The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.</span><span class="sxs-lookup"><span data-stu-id="9dc15-107">The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.</span></span>
  
<span data-ttu-id="9dc15-108">たとえば、以下のような場合に、イベント ベースの保持のラベルを使用することができます:</span><span class="sxs-lookup"><span data-stu-id="9dc15-108">For example, you can use labels with event-driven retention for:</span></span>
  
- <span data-ttu-id="9dc15-109">**Employees leaving the organization** Suppose that employee records must be retained for 10 years from the time an employee leaves the organization.</span><span class="sxs-lookup"><span data-stu-id="9dc15-109">**Employees leaving the organization** Suppose that employee records must be retained for 10 years from the time an employee leaves the organization.</span></span> <span data-ttu-id="9dc15-110">After 10 years elapse, all documents related to the hiring, performance, and termination of that employee need to be disposed.</span><span class="sxs-lookup"><span data-stu-id="9dc15-110">After 10 years elapse, all documents related to the hiring, performance, and termination of that employee need to be disposed.</span></span> <span data-ttu-id="9dc15-111">The event that triggers the 10-year retention period is the employee leaving the organization.</span><span class="sxs-lookup"><span data-stu-id="9dc15-111">The event that triggers the 10-year retention period is the employee leaving the organization.</span></span> 
    
- <span data-ttu-id="9dc15-112">**Contract expiration** Suppose that all records related to contracts need to be retained for five years from the time the contract expires.</span><span class="sxs-lookup"><span data-stu-id="9dc15-112">**Contract expiration** Suppose that all records related to contracts need to be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="9dc15-113">The event that triggers the five-year retention period is the expiration of the contract.</span><span class="sxs-lookup"><span data-stu-id="9dc15-113">The event that triggers the five-year retention period is the expiration of the contract.</span></span> 
    
- <span data-ttu-id="9dc15-114">**Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications.</span><span class="sxs-lookup"><span data-stu-id="9dc15-114">**Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications.</span></span> <span data-ttu-id="9dc15-115">In this case, the last manufacturing date is the event that triggers the retention period.</span><span class="sxs-lookup"><span data-stu-id="9dc15-115">In this case, the last manufacturing date is the event that triggers the retention period.</span></span> 
    
<span data-ttu-id="9dc15-116">Event-driven retention is typically used as part of a records-management process.</span><span class="sxs-lookup"><span data-stu-id="9dc15-116">Event-driven retention is typically used as part of a records-management process.</span></span> <span data-ttu-id="9dc15-117">This means that:</span><span class="sxs-lookup"><span data-stu-id="9dc15-117">This means that:</span></span>
  
- <span data-ttu-id="9dc15-118">Labels based on events also usually classify content as a record.</span><span class="sxs-lookup"><span data-stu-id="9dc15-118">Labels based on events also usually classify content as a record.</span></span> <span data-ttu-id="9dc15-119">For more information, see [Using Content Search to find all content with a specific retention label applied to it](labels.md#using-content-search-to-find-all-content-with-a-specific-retention-label-applied-to-it).</span><span class="sxs-lookup"><span data-stu-id="9dc15-119">For more information, see [Using Content Search to find all content with a specific retention label applied to it](labels.md#using-content-search-to-find-all-content-with-a-specific-retention-label-applied-to-it).</span></span>
    
- <span data-ttu-id="9dc15-120">レコードとして宣言されているもののイベント トリガーがまだ発生していない文書は、イベントがそのドキュメントの保存期間をトリガーするまで無期限に保持されます (レコードを完全に削除することはできません)。</span><span class="sxs-lookup"><span data-stu-id="9dc15-120">A document that's been declared as a record but whose event trigger has not yet happened is retained indefinitely (records can't be permanently deleted), until an event triggers that document's retention period.</span></span>
    
- <span data-ttu-id="9dc15-121">Retention labels based on events usually trigger a disposition review at the end of the retention period, so that a records manager can manually review and dispose the content.</span><span class="sxs-lookup"><span data-stu-id="9dc15-121">Retention labels based on events usually trigger a disposition review at the end of the retention period, so that a records manager can manually review and dispose the content.</span></span> <span data-ttu-id="9dc15-122">For more information, see [Disposition of content](disposition.md).</span><span class="sxs-lookup"><span data-stu-id="9dc15-122">For more information, see [Disposition of content](disposition.md).</span></span>
    
<span data-ttu-id="9dc15-123">イベントに基づくラベルには、Microsoft 365 の他の保持ラベルと同じ機能があります。</span><span class="sxs-lookup"><span data-stu-id="9dc15-123">A label based on an event has the same capabilities as any retention label in Microsoft  365.</span></span> <span data-ttu-id="9dc15-124">詳細については、「[保持ラベルの詳細](labels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dc15-124">For more information, see [Learn about retention labels](labels.md).</span></span>

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a><span data-ttu-id="9dc15-125">イベントの種類、ラベル、イベント、アセット ID の関係を理解する</span><span class="sxs-lookup"><span data-stu-id="9dc15-125">Understanding the relationship between event types, labels, events, and asset IDs</span></span>

<span data-ttu-id="9dc15-126">イベント ベースの保持を活用するには、図と以下の説明に示すように、イベントの種類、保持ラベル、イベント、アセット ID の関係を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="9dc15-126">To successfully use event-driven retention, it's important to understand the relationship between event types, retention labels, events, and asset IDs as illustrated in the diagrams and the explanation that follows:</span></span> 
  
![イベントの種類、ラベル、イベント、アセット ID の図](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![イベントの種類、ラベル、イベント、アセット ID の図](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. <span data-ttu-id="9dc15-129">さまざまな種類のコンテンツの保持ラベルを作成してから、イベントの種類に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="9dc15-129">You create retention labels for different types of content and then associate them with a type of event.</span></span> <span data-ttu-id="9dc15-130">たとえば、さまざまな種類の製品ファイルとレコードの保持ラベルは、製品を使用しなくなった時点からレコードを 10 年間保持する必要があるため、Product Lifetime という名前のイベントの種類に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="9dc15-130">For example, retention labels for different types of product files and records are associated with an event type named Product Lifetime because those records must be retained for 10 years from the time the product reaches its end of life.</span></span>
    
2. <span data-ttu-id="9dc15-131">ユーザー (通常はレコード管理者) はコンテンツにこれらの保持ラベルを適用し、(SharePoint と OneDrive のドキュメントの場合) アイテムごとに資産 ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="9dc15-131">Users (typically records managers) apply those retention labels to content and (for SharePoint and OneDrive documents) enter an asset ID for each item.</span></span> <span data-ttu-id="9dc15-132">この例では、資産 ID は組織で使用される製品名またはコードです。</span><span class="sxs-lookup"><span data-stu-id="9dc15-132">In this example, the asset ID is a product name or code used by the organization.</span></span> <span data-ttu-id="9dc15-133">したがって、各製品のレコードには保持ラベルが割り当てられ、各レコードには資産 ID を含むプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9dc15-133">Thus, each product's records are assigned a retention label, and each record has a property that contains an asset ID.</span></span> <span data-ttu-id="9dc15-134">この図は組織内のすべての製品レコードの**すべてのコンテンツ**を表しており、各アイテムにはそのレコードに該当する製品の資産 ID が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9dc15-134">The diagram represents **all of the content** for all product records in an organization, and each item bears the asset ID of the product whose record it is.</span></span> 
    
3. <span data-ttu-id="9dc15-135">Product Lifetime is the event type; a specific product reaching end of life is an event.</span><span class="sxs-lookup"><span data-stu-id="9dc15-135">Product Lifetime is the event type; a specific product reaching end of life is an event.</span></span> <span data-ttu-id="9dc15-136">When an event of that event type occurs - in this case, when a product reaches its end of life - you create an event that specifies:</span><span class="sxs-lookup"><span data-stu-id="9dc15-136">When an event of that event type occurs - in this case, when a product reaches its end of life - you create an event that specifies:</span></span>
    
  - <span data-ttu-id="9dc15-137">(SharePoint および OneDrive のドキュメントの) アセット ID。</span><span class="sxs-lookup"><span data-stu-id="9dc15-137">An asset ID (for SharePoint and OneDrive documents)</span></span>
    
  - <span data-ttu-id="9dc15-138">Keywords (for Exchange items).</span><span class="sxs-lookup"><span data-stu-id="9dc15-138">Keywords (for Exchange items).</span></span> <span data-ttu-id="9dc15-139">In this example, the organization uses a product code in messages containing product records, so the keyword for Exchange items is the same as the asset ID for SharePoint and OneDrive documents.</span><span class="sxs-lookup"><span data-stu-id="9dc15-139">In this example, the organization uses a product code in messages containing product records, so the keyword for Exchange items is the same as the asset ID for SharePoint and OneDrive documents.</span></span>
    
  - <span data-ttu-id="9dc15-140">The date when the event occurred.</span><span class="sxs-lookup"><span data-stu-id="9dc15-140">The date when the event occurred.</span></span> <span data-ttu-id="9dc15-141">This date is used as the start of the retention period.</span><span class="sxs-lookup"><span data-stu-id="9dc15-141">This date is used as the start of the retention period.</span></span> <span data-ttu-id="9dc15-142">This date can be the current, a past, or a future date.</span><span class="sxs-lookup"><span data-stu-id="9dc15-142">This date can be the current, a past, or a future date.</span></span>
    
4. <span data-ttu-id="9dc15-143">イベントの作成後、イベントの日付は、そのイベントの種類の保持ラベルを持ち、指定された資産 ID またはキーワードを含むすべてのコンテンツに同期されます。</span><span class="sxs-lookup"><span data-stu-id="9dc15-143">After you create an event, that event date is synchronized to all the content that has a retention label of that event type and that contains the specified asset ID or keyword.</span></span> <span data-ttu-id="9dc15-144">その他の保持ラベルと同様に、この同期には最大で 7 日間かかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9dc15-144">Like any retention label, this synchronization can take up to 7 days.</span></span> <span data-ttu-id="9dc15-145">前の図では、赤で囲まれているアイテムはすべて、このイベントによって保持期間がトリガーされています。</span><span class="sxs-lookup"><span data-stu-id="9dc15-145">In the previous diagram, all the items circled in red have their retention period triggered by this event .</span></span> <span data-ttu-id="9dc15-146">言い換えれば、この製品の期限が切れたとき、そのイベントがその製品のレコードの保持期間のトリガーとなります。</span><span class="sxs-lookup"><span data-stu-id="9dc15-146">In other words, when this product reaches its end of life, that event triggers the retention period for that product's records.</span></span>
    
<span data-ttu-id="9dc15-147">イベントに資産 ID またはキーワードを指定しない場合、そのイベントの種類のラベルの付いた**すべてのコンテンツ**はイベントによってトリガーされる保持期間を持つことを理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="9dc15-147">It's important to understand that if you don't specify an asset ID or keywords for an event, **all content** with a label of that event type will have its retention period triggered by the event.</span></span> <span data-ttu-id="9dc15-148">つまり、前の図の場合であれば、すべてのコンテンツの保持が開始されます。</span><span class="sxs-lookup"><span data-stu-id="9dc15-148">This means that in the previous diagram, all content would start being retained.</span></span> <span data-ttu-id="9dc15-149">これは、意図したものとは異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9dc15-149">This might not be what you intend.</span></span> 
  
<span data-ttu-id="9dc15-150">最後に、それぞれの保持ラベルにはそれぞれの保持設定があることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="9dc15-150">Finally, remember that each retention label has its own retention settings.</span></span> <span data-ttu-id="9dc15-151">この例では、すべて 10 年間に指定されていますが、それぞれのラベルが異なる保持期間を持つ保持ラベルを、1 つのイベントでトリガーすることができます。</span><span class="sxs-lookup"><span data-stu-id="9dc15-151">In this example, they all specify 10 years, but it's possible for an event to trigger retention labels where each label has a different retention period.</span></span>
  
## <a name="how-to-set-up-event-driven-retention"></a><span data-ttu-id="9dc15-152">イベント ドリブンの保持のセットアップ方法</span><span class="sxs-lookup"><span data-stu-id="9dc15-152">How to set up event-driven retention</span></span>

<span data-ttu-id="9dc15-153">イベント ドリブンの保持のワークフロー概要:</span><span class="sxs-lookup"><span data-stu-id="9dc15-153">High-level workflow for event-driven retention:</span></span>
  
![イベント ベースの保持をセットアップするワークフローの図](../media/event-based-retention-process.png)
  
> [!TIP]
> <span data-ttu-id="9dc15-155">SharePont の管理プロパティを使用して保持ラベルを自動適用し、イベント ドリブンの保持を実装する詳細なシナリオについては、「[保持ラベルを使用して SharePoint ドキュメントのライフサイクルを管理する](auto-apply-retention-labels-scenario.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dc15-155">See [Manage the lifecycle of SharePoint documents with retention labels](auto-apply-retention-labels-scenario.md) for a detailed scenario about using managed properties in SharePoint to auto-apply retention labels and implement event-driven retention.</span></span>

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a><span data-ttu-id="9dc15-156">手順 1: 保持期間がイベントに基づくラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="9dc15-156">Step 1: Create a label whose retention period is based on an event</span></span>

<span data-ttu-id="9dc15-157">Microsoft 365 コンプライアンス センターの左側のナビゲーションで、**[情報ガバナンス]** > **[ラベル]** > **[ラベルの作成]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="9dc15-157">In the Microsoft 365 compliance center, in the left navigation, select **Information governance** > **Labels** > **Create a label**.</span></span> <span data-ttu-id="9dc15-158">**[情報ガバナンス]** がナビゲーション ウィンドウに表示されない場合は、下にスクロールして **[すべて表示]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9dc15-158">If **Information governance** does not display in the navigation pane, scroll down and select **Show all**.</span></span>
  
<span data-ttu-id="9dc15-159">When you create the label, turn on retention, and then choose the option shown below to retain or delete the content based on an event.</span><span class="sxs-lookup"><span data-stu-id="9dc15-159">When you create the label, turn on retention, and then choose the option shown below to retain or delete the content based on an event.</span></span> <span data-ttu-id="9dc15-160">This means that the retention settings won't go into effect until Step 5, when you create an event on the **Events** page.</span><span class="sxs-lookup"><span data-stu-id="9dc15-160">This means that the retention settings won't go into effect until Step 5, when you create an event on the **Events** page.</span></span> 
  
<span data-ttu-id="9dc15-161">イベント ドリブンの保持は、通常、レコードとして分類されているコンテンツに使用されることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="9dc15-161">Note that event-driven retention is typically used for content that's classified as a record.</span></span> <span data-ttu-id="9dc15-162">そのため、イベントに基づいて保持ラベルを作成する場合、通常は **[このラベルを使用して、コンテンツを "レコード" に分類する]** というオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="9dc15-162">For this reason, when you create retention labels based on an event, you typically choose the option to **Use label to classify content as a "Record"**.</span></span>
  
<span data-ttu-id="9dc15-163">また、イベント ベースの保持には、以下のような保持の設定が必要になります:</span><span class="sxs-lookup"><span data-stu-id="9dc15-163">Also note that event-driven retention requires retention settings that:</span></span>
  
- <span data-ttu-id="9dc15-164">コンテンツを保持する。</span><span class="sxs-lookup"><span data-stu-id="9dc15-164">Retain the content.</span></span>
    
- <span data-ttu-id="9dc15-165">保存期間の終わりに、コンテンツの自動削除または廃棄レビューのトリガーを行う。</span><span class="sxs-lookup"><span data-stu-id="9dc15-165">Delete the content automatically or trigger a disposition review at the end of the retention period.</span></span>
    
![ベースにするイベントのラベルのオプション](../media/a4902281-5196-4194-9737-f30231d95861.png)
  
### <a name="step-2-choose-an-event-type-for-that-label"></a><span data-ttu-id="9dc15-167">手順 2: そのラベルのイベントの種類を選択する</span><span class="sxs-lookup"><span data-stu-id="9dc15-167">Step 2: Choose an event type for that label</span></span>

<span data-ttu-id="9dc15-168">ラベルの設定で、**イベント**に基づいてラベルを設定するオプションを選ぶと、**[イベントの種類の選択]** というオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9dc15-168">In the label settings, after you choose the option to base the label on an **event**, you'll see the option to **Choose an event type**.</span></span> <span data-ttu-id="9dc15-169">イベントの種類とは、ラベルを関連付けるイベントの単なる一般的な説明です。</span><span class="sxs-lookup"><span data-stu-id="9dc15-169">An event type is simply a general description of an event that you want to associate a label with.</span></span>
  
<span data-ttu-id="9dc15-170">たとえば、Product Lifetime という名前のイベントの種類を作成する場合は、"製品開発ファイル" や "製品の経営的意思決定" など、ラベルを適用するコンテンツの種類が分かるような名前でイベント ベースの保持ラベルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dc15-170">For example, if you create an event type named Product Lifetime, you'll create event-based retention labels with names that describe what types of content you want the labels to be applied to, such as "Product development files" or "Product business decision records".</span></span>
  
<span data-ttu-id="9dc15-171">一度イベントの種類を選択して保持ラベルを作成すると、イベントの種類の変更はできませんので、ご注意ください。</span><span class="sxs-lookup"><span data-stu-id="9dc15-171">Note that once you choose an event type and create the retention label, the event type cannot be changed.</span></span>
  
![イベントの種類を作成または選択するオプション](../media/8b7afe79-72cb-462e-81d4-b5ddbe899dbc.png)
  
### <a name="step-3-publish-or-auto-apply-the-event-based-retention-labels"></a><span data-ttu-id="9dc15-173">手順 3: イベント ベースの保持ラベルを発行または自動適用する</span><span class="sxs-lookup"><span data-stu-id="9dc15-173">Step 3: Publish or auto-apply the event-based retention labels</span></span>

<span data-ttu-id="9dc15-174">他の保持ラベルと同じように、イベント ベースのラベルを[発行または自動適用](create-retention-labels.md)する必要があります。したがって、このラベルはコンテンツに手動または自動で適用されます。</span><span class="sxs-lookup"><span data-stu-id="9dc15-174">Just like any retention label, you need to [publish or auto-apply](create-retention-labels.md) an event-based label, so that it's manually or automatically applied to content.</span></span>

> [!NOTE]
> <span data-ttu-id="9dc15-175">[**レコード管理**] > [**ファイル計画**] タブまたは [**データ ガバナンス**] > [**ラベル**] タブからイベント駆動型の保持ラベルを選択した場合、[**ラベルの自動適用**] ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="9dc15-175">If you select an event-driven retention label from **Records Management** > **File plan** tab or **Data governance** > **Labels** tab, the **Auto-apply a label** button is not available.</span></span>
> 
> <span data-ttu-id="9dc15-176">このボタンの代わりに、次のいずれかの場所からのラベルまたはポリシーのリストの上にある [**ラベルを自動適用**] オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="9dc15-176">Instead of this button, use the **Auto-apply a label** option above the list of labels or policies from one of the following locations:</span></span>
> - <span data-ttu-id="9dc15-177">[**レコード管理**] > [**ラベル ポリシー**] タブ</span><span class="sxs-lookup"><span data-stu-id="9dc15-177">**Records management** > **Label policies** tab</span></span>
> - <span data-ttu-id="9dc15-178">[**データ ガバナンス**] > [**ラベル**] タブまたは [**ラベル ポリシー**] タブ</span><span class="sxs-lookup"><span data-stu-id="9dc15-178">**Data governance** > **Labels** tab or **Label policies** tab</span></span>


![保持ラベルの発行または自動適用のオプション](..\media\compliance-information-governance-publish-labels.png)

### <a name="step-4-enter-an-asset-id"></a><span data-ttu-id="9dc15-180">手順 4: アセット ID を入力する</span><span class="sxs-lookup"><span data-stu-id="9dc15-180">Step 4: Enter an asset ID</span></span>

<span data-ttu-id="9dc15-181">After an event-driven label is applied to content, you can enter an asset ID for each item.</span><span class="sxs-lookup"><span data-stu-id="9dc15-181">After an event-driven label is applied to content, you can enter an asset ID for each item.</span></span> <span data-ttu-id="9dc15-182">For example, your organization might use:</span><span class="sxs-lookup"><span data-stu-id="9dc15-182">For example, your organization might use:</span></span>
  
- <span data-ttu-id="9dc15-183">特定の製品のみのコンテンツ保持に使用する製品コード。</span><span class="sxs-lookup"><span data-stu-id="9dc15-183">Product codes that you can use to retain content for only a specific product.</span></span>
    
- <span data-ttu-id="9dc15-184">特定の製品のみのコンテンツ保持に使用するプロジェクト コード。</span><span class="sxs-lookup"><span data-stu-id="9dc15-184">Project codes that you can use to retain content for only a specific project.</span></span>
    
- <span data-ttu-id="9dc15-185">特定の製品のみのコンテンツ保持に使用する従業員 ID。</span><span class="sxs-lookup"><span data-stu-id="9dc15-185">Employee IDs that you can use to retain content for only a specific person.</span></span>
    
<span data-ttu-id="9dc15-186">資産 ID は、SharePoint と OneDrive for Business の単なる別のドキュメント プロパティであることをご理解ください。</span><span class="sxs-lookup"><span data-stu-id="9dc15-186">Understand that Asset ID is simply another document property in SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="9dc15-187">組織では既に別のドキュメント プロパティや ID を使用してコンテンツを分類している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9dc15-187">Your organization might already use other document properties and IDs to classify content.</span></span> <span data-ttu-id="9dc15-188">その場合は、イベントの作成時にそれらのプロパティと値を使用することもできます (後述する手順 6 を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="9dc15-188">If so, you can also use those properties and values when you create an event - see step 6 that follows.</span></span> <span data-ttu-id="9dc15-189">重要な点は、組織はドキュメント プロパティで property:value の組み合わせを使用して、そのアイテムをイベントの種類に関連付ける必要があるということです。</span><span class="sxs-lookup"><span data-stu-id="9dc15-189">The important point is that your organization must use some property:value combination in the document properties to associate that item with an event type.</span></span>
  
![アセット ID を入力するテキスト ボックス](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a><span data-ttu-id="9dc15-191">手順 5: イベントを作成する</span><span class="sxs-lookup"><span data-stu-id="9dc15-191">Step 5: Create an event</span></span>

<span data-ttu-id="9dc15-192">When a particular instance of that event type occurs - for example, a product reaches its end of life - go to the **Records management** > **Events** page in the Microsoft 365 compliance center and create an event.</span><span class="sxs-lookup"><span data-stu-id="9dc15-192">When a particular instance of that event type occurs - for example, a product reaches its end of life - go to the **Records management** > **Events** page in the Microsoft 365 compliance center and create an event.</span></span> <span data-ttu-id="9dc15-193">You need to manually trigger an event by creating it.</span><span class="sxs-lookup"><span data-stu-id="9dc15-193">You need to manually trigger an event by creating it.</span></span>
  
### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a><span data-ttu-id="9dc15-194">手順 6: 手順 2 でのラベルを使用したイベントの種類と同じものを選択する</span><span class="sxs-lookup"><span data-stu-id="9dc15-194">Step 6: Choose the same event type used by the label in step 2</span></span>

<span data-ttu-id="9dc15-195">イベントを作成するときには、手順 2 の保持ラベルで使用したものと同じイベントの種類 (Product Lifetime など) を選択します。</span><span class="sxs-lookup"><span data-stu-id="9dc15-195">When you create the event, choose the same event type used by the retention label in step 2 - for example, Product Lifetime.</span></span> <span data-ttu-id="9dc15-196">そのイベントの種類が選択されたイベントに適用されている保持ラベルの付いたコンテンツのみが、トリガーされる保持期間を持ちます。</span><span class="sxs-lookup"><span data-stu-id="9dc15-196">Only content with retention labels applied to it of that event type will have its retention period triggered.</span></span>
  
![イベントの種類を選択するイベント設定のオプション](../media/11663591-5628-419e-9537-61eb8f5c741f.png)
  
### <a name="step-7-enter-keywords-or-an-asset-id"></a><span data-ttu-id="9dc15-198">手順 7: キーワードまたはアセット ID を入力する</span><span class="sxs-lookup"><span data-stu-id="9dc15-198">Step 7: Enter keywords or an asset ID</span></span>

<span data-ttu-id="9dc15-199">Now you narrow the scope of the content by specifying asset IDs for SharePoint and OneDrive content or keywords for Exchange content.</span><span class="sxs-lookup"><span data-stu-id="9dc15-199">Now you narrow the scope of the content by specifying asset IDs for SharePoint and OneDrive content or keywords for Exchange content.</span></span> <span data-ttu-id="9dc15-200">For asset IDs, retention will be enforced only on content with the specified property:value pair.</span><span class="sxs-lookup"><span data-stu-id="9dc15-200">For asset IDs, retention will be enforced only on content with the specified property:value pair.</span></span> <span data-ttu-id="9dc15-201">If an asset ID is not entered, **all content** with labels of that event type get the same retention date applied to them.</span><span class="sxs-lookup"><span data-stu-id="9dc15-201">If an asset ID is not entered, **all content** with labels of that event type get the same retention date applied to them.</span></span> 
  
<span data-ttu-id="9dc15-202">資産 ID は、SharePoint と OneDrive for Business の単なる別のドキュメント プロパティであることをご理解ください。</span><span class="sxs-lookup"><span data-stu-id="9dc15-202">Understand that Asset ID is simply another document property in SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="9dc15-203">資産 ID プロパティを使用する場合は、下に示される資産 ID のボックスに「ComplianceAssetID:\<value\>」と入力します。</span><span class="sxs-lookup"><span data-stu-id="9dc15-203">If you're using the Asset ID property, you would enter ComplianceAssetID:\<value\> in the box for asset IDs shown below.</span></span>
  
<span data-ttu-id="9dc15-204">Your organization might have applied other properties and IDs to the documents related to this event type.</span><span class="sxs-lookup"><span data-stu-id="9dc15-204">Your organization might have applied other properties and IDs to the documents related to this event type.</span></span> <span data-ttu-id="9dc15-205">For example, if you need to detect a specific product's records, the ID might be a combination of your custom property ProductID and the value "XYZ".</span><span class="sxs-lookup"><span data-stu-id="9dc15-205">For example, if you need to detect a specific product's records, the ID might be a combination of your custom property ProductID and the value "XYZ".</span></span> <span data-ttu-id="9dc15-206">In this case, you'd enter ProductID:XYZ in the box for asset IDs shown below.</span><span class="sxs-lookup"><span data-stu-id="9dc15-206">In this case, you'd enter ProductID:XYZ in the box for asset IDs shown below.</span></span>
  
<span data-ttu-id="9dc15-207">For Exchange items, you can include keywords.</span><span class="sxs-lookup"><span data-stu-id="9dc15-207">For Exchange items, you can include keywords.</span></span> <span data-ttu-id="9dc15-208">You can refine your query by using search operators like AND, OR, and NOT.</span><span class="sxs-lookup"><span data-stu-id="9dc15-208">You can refine your query by using search operators like AND, OR, and NOT.</span></span> <span data-ttu-id="9dc15-209">For more information on operators, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="9dc15-209">For more information on operators, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="9dc15-210">最後に、イベントが発生した日付を選択します。この日付が、保持期間の開始日として使用されます。</span><span class="sxs-lookup"><span data-stu-id="9dc15-210">Finally, choose the date when the event occurred; this date is used as the start of the retention period.</span></span> <span data-ttu-id="9dc15-211">イベントの作成後、そのイベントの日付は、そのイベントの種類の保持ラベル、資産 ID、キーワードを持つすべてのコンテンツに同期されます。</span><span class="sxs-lookup"><span data-stu-id="9dc15-211">After you create an event, that event date is synchronized to all the content with a retention label of that event type, asset ID, and keywords.</span></span> <span data-ttu-id="9dc15-212">その他の保持ラベルと同様に、この同期には最大で 7 日間かかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9dc15-212">Like any retention label, this synchronization can take up to 7 days.</span></span>
  
![[イベントの設定] ページ](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)
  
## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a><span data-ttu-id="9dc15-214">コンテンツ検索を使用して、特定のラベルまたはアセット ID が適用されたすべてのコンテンツを検索する</span><span class="sxs-lookup"><span data-stu-id="9dc15-214">Use Content Search to find all content with a specific label or asset ID</span></span>

<span data-ttu-id="9dc15-215">保持ラベルをコンテンツに割り当てた後は、特定の保持ラベルで分類されている、または特定の資産 ID を含むすべてのコンテンツをコンテンツ検索を使用して検索することができます。</span><span class="sxs-lookup"><span data-stu-id="9dc15-215">After retention labels are assigned to content, you can use content search to find all content that's classified with a specific retention label or that contains a specific asset ID.</span></span>
  
<span data-ttu-id="9dc15-216">コンテンツ検索を行うときは、次のようにします:</span><span class="sxs-lookup"><span data-stu-id="9dc15-216">When you create a content search:</span></span>
  
- <span data-ttu-id="9dc15-217">特定の保持ラベルを持つすべてのコンテンツを検索するには、**[コンプライアンス タグ]** の条件を選択した後、完全なラベル名を入力するか、ラベル名の一部を入力してワイルドカードを使用します。</span><span class="sxs-lookup"><span data-stu-id="9dc15-217">To find all content with a specific retention label, choose the **Compliance Tag** condition, and then enter the complete label name or part of the label name and use a wildcard.</span></span> 
    
- <span data-ttu-id="9dc15-218">特定のアセット ID を持つすべてのコンテンツを検索するには、**ComplianceAssetID** プロパティと値 (例: ComplianceAssetID:\<value\>) を入力します。</span><span class="sxs-lookup"><span data-stu-id="9dc15-218">To find all content with a specific asset ID, enter the **ComplianceAssetID** property and a value, like ComplianceAssetID:\<value\>.</span></span> 
    
<span data-ttu-id="9dc15-219">詳細については、「[コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dc15-219">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="permissions"></a><span data-ttu-id="9dc15-220">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="9dc15-220">Permissions</span></span>

<span data-ttu-id="9dc15-221">To get access to the **Events** page, reviewers must be members of a role group with the **Disposition Management** role and the **View-Only Audit Logs** role.</span><span class="sxs-lookup"><span data-stu-id="9dc15-221">To get access to the **Events** page, reviewers must be members of a role group with the **Disposition Management** role and the **View-Only Audit Logs** role.</span></span> <span data-ttu-id="9dc15-222">We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group.</span><span class="sxs-lookup"><span data-stu-id="9dc15-222">We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group.</span></span> 
  
<span data-ttu-id="9dc15-223">詳細については、「[ユーザーに Office 365 セキュリティ&amp;コンプライアンス センターへのアクセス権を付与する](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dc15-223">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
## <a name="automate-events-by-using-powershell"></a><span data-ttu-id="9dc15-224">PowerShell を使用してイベントを自動化する</span><span class="sxs-lookup"><span data-stu-id="9dc15-224">Automate events by using PowerShell</span></span>

<span data-ttu-id="9dc15-225">In the admin center, you can only create events manually; it's not possible to automatically trigger an event when it occurs.</span><span class="sxs-lookup"><span data-stu-id="9dc15-225">In the admin center, you can only create events manually; it's not possible to automatically trigger an event when it occurs.</span></span> <span data-ttu-id="9dc15-226">However, you can use a Rest API to trigger events automatically; for more information, see [Automate event-based retention](automate-event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="9dc15-226">However, you can use a Rest API to trigger events automatically; for more information, see [Automate event-based retention](automate-event-driven-retention.md).</span></span>

<span data-ttu-id="9dc15-227">PowerShellスクリプトを使用して、業務用アプリケーションからのイベント ベースの保持を自動化することもできます。</span><span class="sxs-lookup"><span data-stu-id="9dc15-227">You can also use a PowerShell script to automate event-based retention from your business applications.</span></span> <span data-ttu-id="9dc15-228">イベント ドリブンの保持で利用可能な PowerShell コマンドレットは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9dc15-228">The PowerShell cmdlets available for event-driven retention:</span></span>
  
- [<span data-ttu-id="9dc15-229">Get-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="9dc15-229">Get-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873002)
    
- [<span data-ttu-id="9dc15-230">New-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="9dc15-230">New-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873004)
    
- [<span data-ttu-id="9dc15-231">Remove-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="9dc15-231">Remove-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873005)
    
- [<span data-ttu-id="9dc15-232">Set-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="9dc15-232">Set-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873006)
    
- [<span data-ttu-id="9dc15-233">Get-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="9dc15-233">Get-ComplianceRetentionEvent</span></span>](https://go.microsoft.com/fwlink/?linkid=873001)
    
- [<span data-ttu-id="9dc15-234">New-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="9dc15-234">New-ComplianceRetentionEvent</span></span>](https://go.microsoft.com/fwlink/?linkid=873003)
    

