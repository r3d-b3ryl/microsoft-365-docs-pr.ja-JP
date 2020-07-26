---
title: イベントの発生時に保持を開始する
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
ms.openlocfilehash: a3760feafa5307c8c71e83dcc72b988258b94a2a
ms.sourcegitcommit: 41eb898143286755cd36df9f7e769de641263d73
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "45391509"
---
# <a name="start-retention-when-an-event-occurs"></a><span data-ttu-id="8d519-103">イベントの発生時に保持を開始する</span><span class="sxs-lookup"><span data-stu-id="8d519-103">Start retention when an event occurs</span></span>

><span data-ttu-id="8d519-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="8d519-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="8d519-p101">コンテンツを保持する際、保持期間は多くの場合、コンテンツの経過日数に基づいています。たとえば、ドキュメントを作成してから 7 年間保持をし、それから削除することができます。ただし、[保持ラベル](labels.md) を構成することで、特定の種類のイベントの発生を保持期間の基準として設定することもできます。イベントによって保持期間の開始がトリガーされ、その種類のイベントに保持ラベルが適用されているすべてのコンテンツに、ラベルの保持アクションが適用されます。</span><span class="sxs-lookup"><span data-stu-id="8d519-p101">When you retain content, the retention period is often based on the age of the content. For example, you might retain documents for seven years after they're created and then delete them. But when you configure [retention labels](labels.md), you can also base a retention period on when a specific type of event occurs. The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.</span></span>
  
<span data-ttu-id="8d519-109">イベントドリブンの保持を使用する場合の例:</span><span class="sxs-lookup"><span data-stu-id="8d519-109">Examples for using event-driven retention:</span></span>
  
- <span data-ttu-id="8d519-110">**従業員が組織を離れる場合**、従業員が組織を離れてから 10 年間は、その従業員のレコードを保持する必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="8d519-110">**Employees leaving the organization** Suppose that employee records must be retained for 10 years from the time an employee leaves the organization.</span></span> <span data-ttu-id="8d519-111">10 年が経過した後、その従業員の採用、業績、および退職に関するすべてのドキュメントを廃棄する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d519-111">After 10 years elapse, all documents related to the hiring, performance, and termination of that employee must be disposed.</span></span> <span data-ttu-id="8d519-112">10 年の保持期間をトリガーするイベントは、組織を離れる従業員となります。</span><span class="sxs-lookup"><span data-stu-id="8d519-112">The event that triggers the 10-year retention period is the employee leaving the organization.</span></span> 
    
- <span data-ttu-id="8d519-113">**契約満了の場合**、契約に関連するすべてのレコードは、契約満了後 5 年間は保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d519-113">**Contract expiration** Suppose that all records related to contracts must be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="8d519-114">5 年間の保持期間をトリガーするイベントは、契約の満了です。</span><span class="sxs-lookup"><span data-stu-id="8d519-114">The event that triggers the five-year retention period is the expiration of the contract.</span></span> 
    
- <span data-ttu-id="8d519-p104">**製品の有効期間**: たとえば、組織に、技術仕様などのコンテンツに関して、最終製品製造日に関する保持要件があるとします。この場合、最後に製造された日が、保存期間をトリガーするイベントとなります。</span><span class="sxs-lookup"><span data-stu-id="8d519-p104">**Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications. In this case, the last manufacturing date is the event that triggers the retention period.</span></span> 
    
<span data-ttu-id="8d519-p105">イベント ベースの保持は通常、レコード管理プロセスの一環として使用します。これは以下のことを意味します:</span><span class="sxs-lookup"><span data-stu-id="8d519-p105">Event-driven retention is typically used as part of a records-management process. This means that:</span></span>
  
- <span data-ttu-id="8d519-119">イベントに基づくラベルでは、通常、レコードとしてコンテンツを分類します。</span><span class="sxs-lookup"><span data-stu-id="8d519-119">Labels based on events also usually classify content as a record.</span></span> <span data-ttu-id="8d519-120">詳細については、「[レコードの詳細](records.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d519-120">For more information, see [Learn about records](records.md).</span></span>

- <span data-ttu-id="8d519-121">レコードとして分類されているもののイベント トリガーがまだ発生していない文書は、イベントがそのドキュメントの保存期間をトリガーするまで無期限に保持されます (レコードを完全に削除することはできません)。</span><span class="sxs-lookup"><span data-stu-id="8d519-121">A document that's been classified as a record but whose event trigger has not yet happened is retained indefinitely (records can't be permanently deleted), until an event triggers that document's retention period.</span></span>
    
- <span data-ttu-id="8d519-122">イベントに基づく保持ラベルは、通常、保持期間の最後に廃棄レビューをトリガーするため、レコード管理者はコンテンツを手動で確認して廃棄できます。</span><span class="sxs-lookup"><span data-stu-id="8d519-122">Retention labels based on events usually trigger a disposition review at the end of the retention period, so that a records manager can manually review and dispose of the content.</span></span> <span data-ttu-id="8d519-123">詳細については、「[コンテンツの廃棄](disposition.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d519-123">For more information, see [Disposition of content](disposition.md).</span></span>
    

<span data-ttu-id="8d519-124">イベントに基づくラベルには、Microsoft 365 の他の保持ラベルと同じ機能があります。</span><span class="sxs-lookup"><span data-stu-id="8d519-124">A label based on an event has the same capabilities as any retention label in Microsoft  365.</span></span> <span data-ttu-id="8d519-125">詳細については、「[アイテム保持ポリシーと保持ラベルの詳細](retention.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d519-125">For more information, see [Learn about retention policies and retention labels](retention.md).</span></span>

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a><span data-ttu-id="8d519-126">イベントの種類、ラベル、イベント、アセット ID の関係を理解する</span><span class="sxs-lookup"><span data-stu-id="8d519-126">Understanding the relationship between event types, labels, events, and asset IDs</span></span>

<span data-ttu-id="8d519-127">イベント ベースの保持を活用するには、図と以下の説明に示すように、イベントの種類、保持ラベル、イベント、アセット ID の関係を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="8d519-127">To successfully use event-driven retention, it's important to understand the relationship between event types, retention labels, events, and asset IDs as illustrated in the diagrams and the explanation that follows:</span></span> 
  
![イベントの種類、ラベル、イベント、アセット ID の図](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![イベントの種類、ラベル、イベント、アセット ID の図](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. <span data-ttu-id="8d519-130">さまざまな種類のコンテンツの保持ラベルを作成してから、イベントの種類に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="8d519-130">You create retention labels for different types of content and then associate them with a type of event.</span></span> <span data-ttu-id="8d519-131">たとえば、さまざまな種類の製品ファイルとレコードの保持ラベルは、製品を使用しなくなった時点からレコードを 10 年間保持する必要があるため、Product Lifetime という名前のイベントの種類に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="8d519-131">For example, retention labels for different types of product files and records are associated with an event type named Product Lifetime because those records must be retained for 10 years from the time the product reaches its end of life.</span></span>
    
2. <span data-ttu-id="8d519-132">ユーザー (通常はレコード管理者) はコンテンツにこれらの保持ラベルを適用し、(SharePoint と OneDrive のドキュメントの場合) アイテムごとに資産 ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="8d519-132">Users (typically records managers) apply those retention labels to content and (for SharePoint and OneDrive documents) enter an asset ID for each item.</span></span> <span data-ttu-id="8d519-133">この例では、資産 ID は組織で使用される製品名またはコードです。</span><span class="sxs-lookup"><span data-stu-id="8d519-133">In this example, the asset ID is a product name or code used by the organization.</span></span> <span data-ttu-id="8d519-134">したがって、各製品のレコードには保持ラベルが割り当てられ、各レコードには資産 ID を含むプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8d519-134">Thus, each product's records are assigned a retention label, and each record has a property that contains an asset ID.</span></span> <span data-ttu-id="8d519-135">この図は組織内のすべての製品レコードの**すべてのコンテンツ**を表しており、各アイテムにはそのレコードに該当する製品の資産 ID が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8d519-135">The diagram represents **all of the content** for all product records in an organization, and each item bears the asset ID of the product whose record it is.</span></span> 
    
3. <span data-ttu-id="8d519-p111">製品の有効期限がイベントの種類であり、有効期限が切れた特定の製品がイベントになります。そのイベントの種類のイベントが発生したら (この場合、製品の有効期限が切れるとき)、以下を指定するイベントを作成します。</span><span class="sxs-lookup"><span data-stu-id="8d519-p111">Product Lifetime is the event type; a specific product reaching end of life is an event. When an event of that event type occurs—in this case, when a product reaches its end of life—you create an event that specifies:</span></span>
    
   - <span data-ttu-id="8d519-138">(SharePoint および OneDrive のドキュメントの) アセット ID。</span><span class="sxs-lookup"><span data-stu-id="8d519-138">An asset ID (for SharePoint and OneDrive documents)</span></span>
    
   - <span data-ttu-id="8d519-p112">(Exchange アイテムの) キーワード。上の例において組織は、製品レコードを含むメッセージで製品コードを使用するため、Exchange アイテムのキーワードは  SharePoint および OneDrive ドキュメントのアセット  ID と同じになります。</span><span class="sxs-lookup"><span data-stu-id="8d519-p112">Keywords (for Exchange items). In this example, the organization uses a product code in messages containing product records, so the keyword for Exchange items is the same as the asset ID for SharePoint and OneDrive documents.</span></span>
    
   - <span data-ttu-id="8d519-p113">イベントが発生した日付。この日付は、保持期間の開始日として使用されます。この日付には、現在、過去、または将来の日付を使用できます。</span><span class="sxs-lookup"><span data-stu-id="8d519-p113">The date when the event occurred. This date is used as the start of the retention period. This date can be the current, a past, or a future date.</span></span>

4. <span data-ttu-id="8d519-144">イベントの作成後、イベントの日付は、そのイベントの種類の保持ラベルを持ち、指定された資産 ID またはキーワードを含むすべてのコンテンツに同期されます。</span><span class="sxs-lookup"><span data-stu-id="8d519-144">After you create an event, that event date is synchronized to all the content that has a retention label of that event type and that contains the specified asset ID or keyword.</span></span> <span data-ttu-id="8d519-145">他の保持ラベルと同様に、この同期には最大で 7 日間かかります。</span><span class="sxs-lookup"><span data-stu-id="8d519-145">Like any retention label, this synchronization can take up to seven days.</span></span> <span data-ttu-id="8d519-146">前の図では、赤で囲まれているアイテムはすべて、このイベントによって保持期間がトリガーされています。</span><span class="sxs-lookup"><span data-stu-id="8d519-146">In the previous diagram, all the items circled in red have their retention period triggered by this event.</span></span> <span data-ttu-id="8d519-147">言い換えれば、この製品の期限が切れたとき、そのイベントがその製品のレコードの保持期間のトリガーとなります。</span><span class="sxs-lookup"><span data-stu-id="8d519-147">In other words, when this product reaches its end of life, that event triggers the retention period for that product's records.</span></span>

<span data-ttu-id="8d519-148">イベントに資産 ID またはキーワードを指定しない場合、そのイベントの種類のラベルの付いた**すべてのコンテンツ**はイベントによってトリガーされる保持期間を持つことを理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="8d519-148">It's important to understand that if you don't specify an asset ID or keywords for an event, **all content** with a label of that event type will have its retention period triggered by the event.</span></span> <span data-ttu-id="8d519-149">つまり、前の図の場合であれば、すべてのコンテンツの保持が開始されます。</span><span class="sxs-lookup"><span data-stu-id="8d519-149">This means that in the previous diagram, all content would start being retained.</span></span> <span data-ttu-id="8d519-150">これは、意図したものとは異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8d519-150">This might not be what you intend.</span></span> 

<span data-ttu-id="8d519-151">最後に、それぞれの保持ラベルにはそれぞれの保持設定があることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="8d519-151">Finally, remember that each retention label has its own retention settings.</span></span> <span data-ttu-id="8d519-152">この例では、すべて 10 年間に指定されていますが、それぞれのラベルが異なる保持期間を持つ保持ラベルを、1 つのイベントでトリガーすることができます。</span><span class="sxs-lookup"><span data-stu-id="8d519-152">In this example, they all specify 10 years, but it's possible for an event to trigger retention labels where each label has a different retention period.</span></span>
  
## <a name="how-to-set-up-event-driven-retention"></a><span data-ttu-id="8d519-153">イベント ドリブンの保持のセットアップ方法</span><span class="sxs-lookup"><span data-stu-id="8d519-153">How to set up event-driven retention</span></span>

<span data-ttu-id="8d519-154">イベント ドリブンの保持のワークフロー概要:</span><span class="sxs-lookup"><span data-stu-id="8d519-154">High-level workflow for event-driven retention:</span></span>
  
![イベント ベースの保持をセットアップするワークフローの図](../media/event-based-retention-process.png)
  
> [!TIP]
> <span data-ttu-id="8d519-156">SharePont の管理プロパティを使用して保持ラベルを自動適用し、イベント ドリブンの保持を実装する詳細なシナリオについては、「[保持ラベルを使用して SharePoint ドキュメントのライフサイクルを管理する](auto-apply-retention-labels-scenario.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d519-156">See [Manage the lifecycle of SharePoint documents with retention labels](auto-apply-retention-labels-scenario.md) for a detailed scenario about using managed properties in SharePoint to auto-apply retention labels and implement event-driven retention.</span></span>

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a><span data-ttu-id="8d519-157">手順 1: 保持期間がイベントに基づくラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="8d519-157">Step 1: Create a label whose retention period is based on an event</span></span>

<span data-ttu-id="8d519-158">保持ラベルを作成して構成するには、[[保持ラベルを作成して構成する](create-retention-labels.md#create-and-configure-retention-labels)] の手順で [保持] をオンにして、イベントに基づいてコンテンツを保持または削除するオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="8d519-158">To create and configure your retention label, use the instructions from [Create and configure retention labels](create-retention-labels.md#create-and-configure-retention-labels) and when you turn on retention, choose the option to retain or delete the content based on an event.</span></span> <span data-ttu-id="8d519-159">つまり、この設定では、保持設定は手順 5 の [**イベント**] ページでイベントを作成するまで有効になりません。</span><span class="sxs-lookup"><span data-stu-id="8d519-159">This setting means that the retention settings won't go into effect until Step 5, when you create an event on the **Events** page.</span></span> 
  
<span data-ttu-id="8d519-160">通常、イベントドリブンの保持は、レコードとして分類されているコンテンツに使用されるので、コンテンツをレコードとしてマークするオプションも選択する必要があるかどうかを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8d519-160">Event-driven retention is typically used for content that's classified as a record, so this is a good time to check whether you also need to select the option that marks content as a record.</span></span>
  
<span data-ttu-id="8d519-161">イベントドリブンの保持には、次のような保持の設定が必要になります。</span><span class="sxs-lookup"><span data-stu-id="8d519-161">Event-driven retention requires retention settings that:</span></span>
  
- <span data-ttu-id="8d519-162">コンテンツを保持する。</span><span class="sxs-lookup"><span data-stu-id="8d519-162">Retain the content.</span></span>
    
- <span data-ttu-id="8d519-163">保存期間の終わりに、コンテンツの自動削除または廃棄レビューのトリガーを行う。</span><span class="sxs-lookup"><span data-stu-id="8d519-163">Delete the content automatically or trigger a disposition review at the end of the retention period.</span></span>
    
![ベースにするイベントのラベルのオプション](../media/a4902281-5196-4194-9737-f30231d95861.png)

### <a name="step-2-choose-an-event-type-for-that-label"></a><span data-ttu-id="8d519-165">手順 2: そのラベルのイベントの種類を選択する</span><span class="sxs-lookup"><span data-stu-id="8d519-165">Step 2: Choose an event type for that label</span></span>

<span data-ttu-id="8d519-166">ラベルの設定で、**イベント**に基づいてラベルを設定するオプションを選ぶと、**[イベントの種類の選択]** というオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d519-166">In the label settings, after you choose the option to base the label on an **event**, you'll see the option to **Choose an event type**.</span></span> <span data-ttu-id="8d519-167">イベントの種類とは、ラベルを関連付けるイベントの単なる一般的な説明です。</span><span class="sxs-lookup"><span data-stu-id="8d519-167">An event type is simply a general description of an event that you want to associate a label with.</span></span>
  
<span data-ttu-id="8d519-168">たとえば、Product Lifetime という名前のイベントの種類を作成する場合は、"製品開発ファイル" や "製品の経営的意思決定" など、ラベルを適用するコンテンツの種類が分かるような名前でイベント ベースの保持ラベルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d519-168">For example, if you create an event type named Product Lifetime, you'll create event-based retention labels with names that describe what types of content you want the labels to be applied to, such as "Product development files" or "Product business decision records".</span></span>

<span data-ttu-id="8d519-169">組み込みのイベントタイプのいずれかを選択するか、独自のイベントタイプを作成して選択します。</span><span class="sxs-lookup"><span data-stu-id="8d519-169">Select one of the built-in event types, or create your own and then select it.</span></span>

<span data-ttu-id="8d519-170">イベントの種類を選択して保持ラベルを保存すると、イベントの種類の変更はできませんので、ご注意ください。</span><span class="sxs-lookup"><span data-stu-id="8d519-170">After you choose an event type and save the retention label, the event type cannot be changed.</span></span>
  
![イベントの種類を作成または選択するオプション](../media/8b7afe79-72cb-462e-81d4-b5ddbe899dbc.png)
  
### <a name="step-3-publish-or-auto-apply-the-event-based-retention-labels"></a><span data-ttu-id="8d519-172">手順 3: イベント ベースの保持ラベルを発行または自動適用する</span><span class="sxs-lookup"><span data-stu-id="8d519-172">Step 3: Publish or auto-apply the event-based retention labels</span></span>

<span data-ttu-id="8d519-173">他の保持ラベルと同じように、イベント ベースのラベルを発行するか自動適用して、コンテンツに手動または自動で適用されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d519-173">Just like any retention label, you need to publish or auto-apply an event-based label, for it to be manually or automatically applied to content:</span></span>
- [<span data-ttu-id="8d519-174">アイテム保持ラベルを作成してアプリに適用する</span><span class="sxs-lookup"><span data-stu-id="8d519-174">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
- [<span data-ttu-id="8d519-175">保持ラベルをコンテンツに自動的に適用する</span><span class="sxs-lookup"><span data-stu-id="8d519-175">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)


> [!NOTE]
> <span data-ttu-id="8d519-176">[**レコード管理**] > [**ファイル計画**] タブまたは [**データ ガバナンス**] > [**ラベル**] タブからイベント ベースの保持ラベルを選択した場合、[**ラベルの自動適用**] ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="8d519-176">If you select an event-based retention label from **Records Management** > **File plan** tab or **Data governance** > **Labels** tab, the **Auto-apply a label** button is not available.</span></span>
> 
> <span data-ttu-id="8d519-177">このボタンの代わりに、次のいずれかの場所からのラベルまたはポリシーのリストの上にある [**ラベルを自動適用**] オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="8d519-177">Instead of this button, use the **Auto-apply a label** option above the list of labels or policies from one of the following locations:</span></span>
> - <span data-ttu-id="8d519-178">[**レコード管理**] > [**ラベル ポリシー**] タブ</span><span class="sxs-lookup"><span data-stu-id="8d519-178">**Records management** > **Label policies** tab</span></span>
> - <span data-ttu-id="8d519-179">[**データ ガバナンス**] > [**ラベル**] タブまたは [**ラベル ポリシー**] タブ</span><span class="sxs-lookup"><span data-stu-id="8d519-179">**Data governance** > **Labels** tab or **Label policies** tab</span></span>


![保持ラベルの発行または自動適用のオプション](..\media\compliance-information-governance-publish-labels.png)

### <a name="step-4-enter-an-asset-id"></a><span data-ttu-id="8d519-181">手順 4: アセット ID を入力する</span><span class="sxs-lookup"><span data-stu-id="8d519-181">Step 4: Enter an asset ID</span></span>

<span data-ttu-id="8d519-182">イベント ベースのラベルがコンテンツに適用されたら、アイテムごとに資産 ID を入力できます。</span><span class="sxs-lookup"><span data-stu-id="8d519-182">After an event-based label is applied to content, you can enter an asset ID for each item.</span></span> <span data-ttu-id="8d519-183">たとえば、組織では以下のものを使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="8d519-183">For example, your organization might use:</span></span>
  
- <span data-ttu-id="8d519-184">特定の製品のみのコンテンツ保持に使用する製品コード。</span><span class="sxs-lookup"><span data-stu-id="8d519-184">Product codes that you can use to retain content for only a specific product.</span></span>
    
- <span data-ttu-id="8d519-185">特定の製品のみのコンテンツ保持に使用するプロジェクト コード。</span><span class="sxs-lookup"><span data-stu-id="8d519-185">Project codes that you can use to retain content for only a specific project.</span></span>
    
- <span data-ttu-id="8d519-186">特定の製品のみのコンテンツ保持に使用する従業員 ID。</span><span class="sxs-lookup"><span data-stu-id="8d519-186">Employee IDs that you can use to retain content for only a specific person.</span></span>
    
<span data-ttu-id="8d519-187">資産 ID は、SharePoint と OneDrive で利用できる別のドキュメント プロパティです。</span><span class="sxs-lookup"><span data-stu-id="8d519-187">Asset ID is simply another document property that's available in SharePoint and OneDrive.</span></span> <span data-ttu-id="8d519-188">組織では既に別のドキュメント プロパティや ID を使用してコンテンツを分類している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8d519-188">Your organization might already use other document properties and IDs to classify content.</span></span> <span data-ttu-id="8d519-189">その場合、イベントの作成時にそれらのプロパティおよび値を使用することもできます (後述する手順 6 を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="8d519-189">If so, you can also use those properties and values when you create an event—see step 6 that follows.</span></span> <span data-ttu-id="8d519-190">重要な点は、ドキュメント プロパティで *property:value* の組み合わせを使用して、そのアイテムをイベントの種類に関連付ける必要があるということです。</span><span class="sxs-lookup"><span data-stu-id="8d519-190">The important point is that you must use some *property:value* combination in the document properties to associate that item with an event type.</span></span>
  
![アセット ID を入力するテキスト ボックス](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a><span data-ttu-id="8d519-192">手順 5: イベントを作成する</span><span class="sxs-lookup"><span data-stu-id="8d519-192">Step 5: Create an event</span></span>

<span data-ttu-id="8d519-193">製品の使用を終えるなど、イベントの種類に関する特定のインスタンスが発生するときは、Microsoft 365 コンプライアンス センターで **[レコード管理]** > **[イベント]** ページの順に移動し、イベントを作成します。</span><span class="sxs-lookup"><span data-stu-id="8d519-193">When a particular instance of that event type occurs, such as a product reaches its end of life, go to the **Records management** > **Events** page in the Microsoft 365 compliance center and create an event.</span></span> <span data-ttu-id="8d519-194">イベントを作成し、トリガーします。</span><span class="sxs-lookup"><span data-stu-id="8d519-194">You trigger an event by creating it.</span></span>
  
### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a><span data-ttu-id="8d519-195">手順 6: 手順 2 でのラベルを使用したイベントの種類と同じものを選択する</span><span class="sxs-lookup"><span data-stu-id="8d519-195">Step 6: Choose the same event type used by the label in step 2</span></span>

<span data-ttu-id="8d519-196">イベントを作成するときには、手順 2 の保持ラベルで使用したものと同じイベントの種類 (製品の有効期限など) を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d519-196">When you create the event, choose the same event type used by the retention label in step 2—for example, Product Lifetime.</span></span> <span data-ttu-id="8d519-197">そのイベントの種類が選択されたイベントに適用されている保持ラベルの付いたコンテンツのみが、トリガーされる保持期間を持ちます。</span><span class="sxs-lookup"><span data-stu-id="8d519-197">Only content with retention labels applied to it of that event type will have its retention period triggered.</span></span>
  
![イベントの種類を選択するイベント設定のオプション](../media/11663591-5628-419e-9537-61eb8f5c741f.png)
  
### <a name="step-7-enter-keywords-or-an-asset-id"></a><span data-ttu-id="8d519-199">手順 7: キーワードまたはアセット ID を入力する</span><span class="sxs-lookup"><span data-stu-id="8d519-199">Step 7: Enter keywords or an asset ID</span></span>

<span data-ttu-id="8d519-200">ここで、資産 ID (SharePoint および OneDrive コンテンツの場合) またはキーワード (Exchange コンテンツの場合) を指定して、コンテンツの範囲を絞り込みます。</span><span class="sxs-lookup"><span data-stu-id="8d519-200">Now you narrow the scope of the content by specifying asset IDs for SharePoint and OneDrive content, or keywords for Exchange content.</span></span> <span data-ttu-id="8d519-201">資産 ID の場合、保持は指定された *property:value* ペアを持つコンテンツにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="8d519-201">For asset IDs, retention will be enforced only on content with the specified *property:value* pair.</span></span> <span data-ttu-id="8d519-202">資産 ID が入力されていない場合は、そのイベントの種類のラベルの付いたすべてのコンテンツに同じ保持期限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="8d519-202">If an asset ID is not entered, all content with labels of that event type get the same retention date applied to them.</span></span>

<span data-ttu-id="8d519-203">例えば、資産 ID プロパティを使用する場合は、下に示される資産 ID のボックスに 「`ComplianceAssetID:<value>`」 と入力します。</span><span class="sxs-lookup"><span data-stu-id="8d519-203">For example: If you're using the Asset ID property, enter `ComplianceAssetID:<value>` in the box for asset IDs shown below.</span></span>
  
<span data-ttu-id="8d519-204">組織は、このイベントの種類に関するドキュメントに他のプロパティと ID を適用している場合があります。</span><span class="sxs-lookup"><span data-stu-id="8d519-204">Your organization might have applied other properties and IDs to the documents related to this event type.</span></span> <span data-ttu-id="8d519-205">たとえば、特定の製品のレコードを検出する必要がある場合、ID はカスタム プロパティ製品 ID とその値 "XYZ" の組み合わせである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8d519-205">For example, if you need to detect a specific product's records, the ID might be a combination of your custom property ProductID and the value "XYZ".</span></span> <span data-ttu-id="8d519-206">この場合は、次の図に示されるアセット ID のボックスに 「`ProductID:XYZ`」 と入力します。</span><span class="sxs-lookup"><span data-stu-id="8d519-206">In this case, you'd enter `ProductID:XYZ` in the box for asset IDs shown in the following picture.</span></span>
  
<span data-ttu-id="8d519-207">Exchange アイテムの場合、キーワード を使用します。</span><span class="sxs-lookup"><span data-stu-id="8d519-207">For Exchange items, use keywords.</span></span> <span data-ttu-id="8d519-208">AND、OR、NOT などの検索演算子を使用して、クエリを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="8d519-208">You can use a query by using search operators such as AND, OR, and NOT.</span></span> <span data-ttu-id="8d519-209">詳細については、「[コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d519-209">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="8d519-210">最後に、イベントが発生した日付を選択します。この日付が、保持期間の開始日として使用されます。</span><span class="sxs-lookup"><span data-stu-id="8d519-210">Finally, choose the date when the event occurred; this date is used as the start of the retention period.</span></span> <span data-ttu-id="8d519-211">イベントの作成後、そのイベントの日付は、そのイベントの種類の保持ラベル、資産 ID、キーワードを持つすべてのコンテンツに同期されます。</span><span class="sxs-lookup"><span data-stu-id="8d519-211">After you create an event, that event date is synchronized to all the content with a retention label of that event type, asset ID, and keywords.</span></span> <span data-ttu-id="8d519-212">その他の保持ラベルと同様に、この同期には最大で 7 日間かかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8d519-212">As with any retention label, this synchronization can take up to seven days.</span></span>
  
![[イベントの設定] ページ](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)

<span data-ttu-id="8d519-214">イベントを作成すると、既にラベル付けされてインデックスが作成されているコンテンツの保持設定が有効になります。</span><span class="sxs-lookup"><span data-stu-id="8d519-214">After creating an event, the retention settings take effect for the content that's already labeled and indexed.</span></span> <span data-ttu-id="8d519-215">イベントが作成された後に保持ラベルが新しいコンテンツに追加された場合は、同じ詳細を使用して新しいイベントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d519-215">If the retention label is added to new content after the event is created, you must create a new event with the same details.</span></span>

<span data-ttu-id="8d519-216">イベントを削除しても、既にラベル付けされているコンテンツに対して現在有効になっている保持設定は取り消されません。</span><span class="sxs-lookup"><span data-stu-id="8d519-216">Deleting an event doesn't cancel the retention settings that are now in effect for the content that's already labeled.</span></span> <span data-ttu-id="8d519-217">それを行うには、同じ詳細を使用して新しいイベントを作成しますが、日付は空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="8d519-217">To do that, create a new event with the same details, but leave the date blank.</span></span> 

## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a><span data-ttu-id="8d519-218">コンテンツ検索を使用して、特定のラベルまたはアセット ID が適用されたすべてのコンテンツを検索する</span><span class="sxs-lookup"><span data-stu-id="8d519-218">Use Content Search to find all content with a specific label or asset ID</span></span>

<span data-ttu-id="8d519-219">保持ラベルをコンテンツに割り当てた後は、特定の保持ラベルで分類されている、または特定のアセット ID を含むすべてのコンテンツをコンテンツ検索を使用して検索することができます。</span><span class="sxs-lookup"><span data-stu-id="8d519-219">After retention labels are assigned to content, you can use content search to find all content that's classified with a specific retention label or that contains a specific asset ID:</span></span>
  
- <span data-ttu-id="8d519-220">特定の保持ラベルを持つすべてのコンテンツを検索するには、 **保持ラベル**の条件を選択した後、完全なラベル名を入力するか、ラベル名の一部を入力してワイルドカードを使用します。</span><span class="sxs-lookup"><span data-stu-id="8d519-220">To find all content with a specific retention label, choose the **Retention label** condition, and then enter the complete label name or part of the label name and use a wildcard.</span></span> 
    
- <span data-ttu-id="8d519-221">特定のアセット ID を持つすべてのコンテンツを検索するには、**ComplianceAssetID** プロパティと `ComplianceAssetID:<value>` のフォーマットを使用した値を入力します。</span><span class="sxs-lookup"><span data-stu-id="8d519-221">To find all content with a specific asset ID, enter the **ComplianceAssetID** property and a value, using the format `ComplianceAssetID:<value>`.</span></span> 
    
<span data-ttu-id="8d519-222">詳細については、「[コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d519-222">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="permissions"></a><span data-ttu-id="8d519-223">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="8d519-223">Permissions</span></span>

<span data-ttu-id="8d519-p129">**[イベント]** ページにアクセスするには、レビュー担当者は、**廃棄管理**の役割と**監査ログの閲覧限定**の役割を持つ、役割グループのメンバーである必要があります。Disposition Reviewers という新しい役割グループを作成し、これら 2 つの役割をその役割グループに追加して、それからメンバーをその役割グループに追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8d519-p129">To get access to the **Events** page, reviewers must be members of a role group with the **Disposition Management** role and the **View-Only Audit Logs** role. We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group.</span></span> 
  
<span data-ttu-id="8d519-226">詳細については、「[ユーザーに Office 365 セキュリティ&amp;コンプライアンス センターへのアクセス権を付与する](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d519-226">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
## <a name="automate-events-by-using-powershell"></a><span data-ttu-id="8d519-227">PowerShell を使用してイベントを自動化する</span><span class="sxs-lookup"><span data-stu-id="8d519-227">Automate events by using PowerShell</span></span>

<span data-ttu-id="8d519-228">PowerShell スクリプトを使用して、ビジネス アプリケーションからイベント ベースの保持を自動化することができます。</span><span class="sxs-lookup"><span data-stu-id="8d519-228">You can use a PowerShell script to automate event-based retention from your business applications.</span></span> <span data-ttu-id="8d519-229">イベント ベースの保持で利用可能な PowerShell コマンドレットは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8d519-229">The PowerShell cmdlets available for event-based retention:</span></span>
  
- [<span data-ttu-id="8d519-230">Get-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="8d519-230">Get-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873002)
    
- [<span data-ttu-id="8d519-231">New-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="8d519-231">New-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873004)
    
- [<span data-ttu-id="8d519-232">Remove-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="8d519-232">Remove-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873005)
    
- [<span data-ttu-id="8d519-233">Set-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="8d519-233">Set-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873006)
    
- [<span data-ttu-id="8d519-234">Get-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="8d519-234">Get-ComplianceRetentionEvent</span></span>](https://go.microsoft.com/fwlink/?linkid=873001)
    
- [<span data-ttu-id="8d519-235">New-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="8d519-235">New-ComplianceRetentionEvent</span></span>](https://go.microsoft.com/fwlink/?linkid=873003)
    

## <a name="automate-events-by-using-a-rest-api"></a><span data-ttu-id="8d519-236">REST API を使用してイベントを自動化する</span><span class="sxs-lookup"><span data-stu-id="8d519-236">Automate events by using a REST API</span></span>

<span data-ttu-id="8d519-237">REST API を使用して、保持期間の開始をトリガーするイベントを自動的に作成できます。</span><span class="sxs-lookup"><span data-stu-id="8d519-237">You can use a REST API to automatically create the events that trigger the start of the retention time.</span></span>

<span data-ttu-id="8d519-238">REST API は一連の HTTP 操作 (HTTP メソッド) をサポートするサービス エンドポイントで、サービス リソースへのアクセス権の作成/取得/更新/削除をできるようにします。</span><span class="sxs-lookup"><span data-stu-id="8d519-238">A REST API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources.</span></span> <span data-ttu-id="8d519-239">詳細については、「[REST API 要求/応答のコンポーネント](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d519-239">For more information, see [Components of a REST API request/response](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span></span> <span data-ttu-id="8d519-240">Microsoft 365 REST API を使用することにより、POST および GET メソッドを使用してイベントを作成および取得できます。</span><span class="sxs-lookup"><span data-stu-id="8d519-240">By using the Microsoft 365 REST API, events can be created and retrieved using the POST and GET methods.</span></span>

<span data-ttu-id="8d519-241">REST API を使用するには、2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="8d519-241">There are two options for using the REST API:</span></span>

- <span data-ttu-id="8d519-242">イベントの発生を自動的にトリガーする **Microsoft Power Automate または同様のアプリケーション**。</span><span class="sxs-lookup"><span data-stu-id="8d519-242">**Microsoft Power Automate or a similar application** to trigger the occurrence of an event automatically.</span></span> <span data-ttu-id="8d519-243">Microsoft Power Automate は、他のシステムに接続するためのオーケストレーターなので、カスタム ソリューションを作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8d519-243">Microsoft Power Automate is an orchestrator for connecting to other systems, so you don't need to write a custom solution.</span></span> <span data-ttu-id="8d519-244">詳細については、[Power Automate Web サイト](https://flow.microsoft.com/ja-JP/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d519-244">For more information, see the [Power Automate website](https://flow.microsoft.com/ja-JP/).</span></span>

- <span data-ttu-id="8d519-245">**PowerShell または HTTP クライアントで REST API** を呼び出して、カスタム ソリューションの一部である PowerShell (バージョン 6 以降) を使用してイベントを作成します。</span><span class="sxs-lookup"><span data-stu-id="8d519-245">**PowerShell or an HTTP client to call the REST API** to create events by using PowerShell (version 6 or later), which is part of a custom solution.</span></span>

<span data-ttu-id="8d519-246">REST API を使用する前に、グローバル管理者として、保持イベント呼び出しに使用する URL を確認します。</span><span class="sxs-lookup"><span data-stu-id="8d519-246">Before you use the REST API, as a global administrator, confirm the URL to use for the retention event call.</span></span> <span data-ttu-id="8d519-247">これを行うには、REST API の URL を使用して、保持イベント呼び出しの取得を実行します。</span><span class="sxs-lookup"><span data-stu-id="8d519-247">To do this, run a GET retention event call by using the REST API URL:</span></span>

```console
https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent
```

<span data-ttu-id="8d519-248">応答コードを確認します。</span><span class="sxs-lookup"><span data-stu-id="8d519-248">Check the response code.</span></span> <span data-ttu-id="8d519-249">302 の場合は、応答ヘッダーの Location プロパティからリダイレクトされた URL を取得し、以下の手順で `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent` の代わりにその URL を使用します。</span><span class="sxs-lookup"><span data-stu-id="8d519-249">If it's 302, get the redirected URL from the Location property of the response header and use that URL instead of `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent` in the instructions that follow.</span></span>

<span data-ttu-id="8d519-250">自動作成されたイベントは、Microsoft 365 コンプライアンス センター > **レコード管理** >  **イベント** で表示することで確認できます。</span><span class="sxs-lookup"><span data-stu-id="8d519-250">The events that get automatically created can be confirmed by viewing them in the Microsoft 365 compliance center > **Records management** >  **Events**.</span></span>

### <a name="use-microsoft-power-automate-to-create-the-event"></a><span data-ttu-id="8d519-251">Microsoft Power Automate を使用してイベントを作成する</span><span class="sxs-lookup"><span data-stu-id="8d519-251">Use Microsoft Power Automate to create the event</span></span>

<span data-ttu-id="8d519-252">Microsoft 365 REST API を使用してイベントを作成するフローを作成します</span><span class="sxs-lookup"><span data-stu-id="8d519-252">Create a flow that creates an event using the Microsoft 365 REST API:</span></span>

![Flow を使用してイベントを作成する](../media/automate-event-driven-retention-flow-1.png)

![Flow を使用して REST API を呼び出す](../media/automate-event-driven-retention-flow-2.png)

#### <a name="create-an-event"></a><span data-ttu-id="8d519-255">イベントを作成する</span><span class="sxs-lookup"><span data-stu-id="8d519-255">Create an event</span></span>

<span data-ttu-id="8d519-256">REST API を呼び出すサンプル コード</span><span class="sxs-lookup"><span data-stu-id="8d519-256">Sample code to call the REST API:</span></span>

- <span data-ttu-id="8d519-257">**方法**: 投稿</span><span class="sxs-lookup"><span data-stu-id="8d519-257">**Method**: POST</span></span>
- <span data-ttu-id="8d519-258">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="8d519-258">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>
- <span data-ttu-id="8d519-259">**ヘッダー**: キー = Content-Type、値 = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="8d519-259">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>
- <span data-ttu-id="8d519-260">**本文**:</span><span class="sxs-lookup"><span data-stu-id="8d519-260">**Body**:</span></span>
    
    ```xml
    <?xml version='1.0' encoding='utf-8' standalone='yes'?>
    
    <entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'
    
    xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'
    
    xmlns='http://www.w3.org/2005/Atom'>
    
    <category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />
    
    <updated>9/9/2017 10:50:00 PM</updated>
    
    <content type='application/xml'>
    
    <m:properties>
    
    <d:Name>Employee Termination </d:Name>
    
    <d:EventType>99e0ae64-a4b8-40bb-82ed-645895610f56</d:EventType>
    
    <d:SharePointAssetIdQuery>1234</d:SharePointAssetIdQuery>
    
    <d:EventDateTime>2018-12-01T00:00:00Z </d:EventDateTime>
    
    </m:properties>
    
    </content>
    
    </entry>
    ```
    
- <span data-ttu-id="8d519-261">**認証**: 基本</span><span class="sxs-lookup"><span data-stu-id="8d519-261">**Authentication**: Basic</span></span>
- <span data-ttu-id="8d519-262">**ユーザー名**: 「Complianceuser」</span><span class="sxs-lookup"><span data-stu-id="8d519-262">**Username**: "Complianceuser"</span></span>
- <span data-ttu-id="8d519-263">**パスワード**: 「Compliancepassword」</span><span class="sxs-lookup"><span data-stu-id="8d519-263">**Password**: "Compliancepassword"</span></span>


##### <a name="available-parameters"></a><span data-ttu-id="8d519-264">利用可能なパラメーター</span><span class="sxs-lookup"><span data-stu-id="8d519-264">Available parameters</span></span>


|<span data-ttu-id="8d519-265">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8d519-265">Parameters</span></span>|<span data-ttu-id="8d519-266">説明</span><span class="sxs-lookup"><span data-stu-id="8d519-266">Description</span></span>|<span data-ttu-id="8d519-267">Notes</span><span class="sxs-lookup"><span data-stu-id="8d519-267">Notes</span></span>|
|--- |--- |--- |
|<span data-ttu-id="8d519-268"><d:Name></d:Name></span><span class="sxs-lookup"><span data-stu-id="8d519-268"><d:Name></d:Name></span></span>|<span data-ttu-id="8d519-269">イベントの一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="8d519-269">Provide a unique name for the event,</span></span>|<span data-ttu-id="8d519-270">末尾のスペースおよび以下の文字は使用できません。% \* \ & < \> \| # ?</span><span class="sxs-lookup"><span data-stu-id="8d519-270">Cannot contain trailing spaces or the following characters: % \* \ & < \> \| # ?</span></span> <span data-ttu-id="8d519-271">, : ;</span><span class="sxs-lookup"><span data-stu-id="8d519-271">, : ;</span></span>|
|<span data-ttu-id="8d519-272"><d:EventType></d:EventType></span><span class="sxs-lookup"><span data-stu-id="8d519-272"><d:EventType></d:EventType></span></span>|<span data-ttu-id="8d519-273">イベントの種類の名前 (または GUID) を入力します。</span><span class="sxs-lookup"><span data-stu-id="8d519-273">Enter event type name (or Guid),</span></span>|<span data-ttu-id="8d519-274">例: 「従業員の退職」。</span><span class="sxs-lookup"><span data-stu-id="8d519-274">Example: "Employee termination".</span></span> <span data-ttu-id="8d519-275">イベントの種類を保持ラベルに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d519-275">Event type has to be associated with a retention label.</span></span>|
|<span data-ttu-id="8d519-276"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span><span class="sxs-lookup"><span data-stu-id="8d519-276"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span></span>|<span data-ttu-id="8d519-277">「ComplianceAssetId:」 と従業員 ID を入力します</span><span class="sxs-lookup"><span data-stu-id="8d519-277">Enter "ComplianceAssetId:" + employee ID</span></span>|<span data-ttu-id="8d519-278">例: 「ComplianceAssetId: 12345」</span><span class="sxs-lookup"><span data-stu-id="8d519-278">Example: "ComplianceAssetId:12345"</span></span>|
|<span data-ttu-id="8d519-279"><d:EventDateTime></d:EventDateTime></span><span class="sxs-lookup"><span data-stu-id="8d519-279"><d:EventDateTime></d:EventDateTime></span></span>|<span data-ttu-id="8d519-280">イベントの日時</span><span class="sxs-lookup"><span data-stu-id="8d519-280">Event Date and Time</span></span>|<span data-ttu-id="8d519-281">形式: yyyy-MM-ddTHH:mm:ssZ、例: 2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="8d519-281">Format: yyyy-MM-ddTHH:mm:ssZ, Example: 2018-12-01T00:00:00Z</span></span>
|

###### <a name="response-codes"></a><span data-ttu-id="8d519-282">応答コード</span><span class="sxs-lookup"><span data-stu-id="8d519-282">Response codes</span></span>

| <span data-ttu-id="8d519-283">応答コード</span><span class="sxs-lookup"><span data-stu-id="8d519-283">Response Code</span></span> | <span data-ttu-id="8d519-284">説明</span><span class="sxs-lookup"><span data-stu-id="8d519-284">Description</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="8d519-285">302</span><span class="sxs-lookup"><span data-stu-id="8d519-285">302</span></span>               | <span data-ttu-id="8d519-286">リダイレクト</span><span class="sxs-lookup"><span data-stu-id="8d519-286">Redirect</span></span>              |
| <span data-ttu-id="8d519-287">201</span><span class="sxs-lookup"><span data-stu-id="8d519-287">201</span></span>               | <span data-ttu-id="8d519-288">作成済み</span><span class="sxs-lookup"><span data-stu-id="8d519-288">Created</span></span>               |
| <span data-ttu-id="8d519-289">403</span><span class="sxs-lookup"><span data-stu-id="8d519-289">403</span></span>               | <span data-ttu-id="8d519-290">承認に失敗しました</span><span class="sxs-lookup"><span data-stu-id="8d519-290">Authorization Failed</span></span>  |
| <span data-ttu-id="8d519-291">401</span><span class="sxs-lookup"><span data-stu-id="8d519-291">401</span></span>               | <span data-ttu-id="8d519-292">認証に失敗しました</span><span class="sxs-lookup"><span data-stu-id="8d519-292">Authentication Failed</span></span> |

##### <a name="get-events-based-on-a-time-range"></a><span data-ttu-id="8d519-293">時間範囲に基づいてイベントを取得する</span><span class="sxs-lookup"><span data-stu-id="8d519-293">Get events based on a time range</span></span>

- <span data-ttu-id="8d519-294">**メソッド**: GET</span><span class="sxs-lookup"><span data-stu-id="8d519-294">**Method**: GET</span></span>

- <span data-ttu-id="8d519-295">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span><span class="sxs-lookup"><span data-stu-id="8d519-295">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span></span>

- <span data-ttu-id="8d519-296">**ヘッダー**: キー = Content-Type、値 = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="8d519-296">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="8d519-297">**認証**: 基本</span><span class="sxs-lookup"><span data-stu-id="8d519-297">**Authentication**: Basic</span></span>

- <span data-ttu-id="8d519-298">**ユーザー名**: 「Complianceuser」</span><span class="sxs-lookup"><span data-stu-id="8d519-298">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="8d519-299">**パスワード**: 「Compliancepassword」</span><span class="sxs-lookup"><span data-stu-id="8d519-299">**Password**: "Compliancepassword"</span></span>


###### <a name="response-codes"></a><span data-ttu-id="8d519-300">応答コード</span><span class="sxs-lookup"><span data-stu-id="8d519-300">Response codes</span></span>

| <span data-ttu-id="8d519-301">応答コード</span><span class="sxs-lookup"><span data-stu-id="8d519-301">Response Code</span></span> | <span data-ttu-id="8d519-302">説明</span><span class="sxs-lookup"><span data-stu-id="8d519-302">Description</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="8d519-303">200</span><span class="sxs-lookup"><span data-stu-id="8d519-303">200</span></span>               | <span data-ttu-id="8d519-304">問題ありません。イベントの一覧は atom+ xml 形式です</span><span class="sxs-lookup"><span data-stu-id="8d519-304">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="8d519-305">404</span><span class="sxs-lookup"><span data-stu-id="8d519-305">404</span></span>               | <span data-ttu-id="8d519-306">見つかりません</span><span class="sxs-lookup"><span data-stu-id="8d519-306">Not found</span></span>                         |
| <span data-ttu-id="8d519-307">302</span><span class="sxs-lookup"><span data-stu-id="8d519-307">302</span></span>               | <span data-ttu-id="8d519-308">リダイレクト</span><span class="sxs-lookup"><span data-stu-id="8d519-308">Redirect</span></span>                          |
| <span data-ttu-id="8d519-309">401</span><span class="sxs-lookup"><span data-stu-id="8d519-309">401</span></span>               | <span data-ttu-id="8d519-310">承認に失敗しました</span><span class="sxs-lookup"><span data-stu-id="8d519-310">Authorization Failed</span></span>              |
| <span data-ttu-id="8d519-311">403</span><span class="sxs-lookup"><span data-stu-id="8d519-311">403</span></span>               | <span data-ttu-id="8d519-312">認証に失敗しました</span><span class="sxs-lookup"><span data-stu-id="8d519-312">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="8d519-313">ID でイベントを取得する</span><span class="sxs-lookup"><span data-stu-id="8d519-313">Get an event by ID</span></span>

- <span data-ttu-id="8d519-314">**メソッド**: GET</span><span class="sxs-lookup"><span data-stu-id="8d519-314">**Method**: GET</span></span>

- <span data-ttu-id="8d519-315">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span><span class="sxs-lookup"><span data-stu-id="8d519-315">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span></span>

- <span data-ttu-id="8d519-316">**ヘッダー**: キー = Content-Type、値 = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="8d519-316">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="8d519-317">**認証**: 基本</span><span class="sxs-lookup"><span data-stu-id="8d519-317">**Authentication**: Basic</span></span>

- <span data-ttu-id="8d519-318">**ユーザー名**: 「Complianceuser」</span><span class="sxs-lookup"><span data-stu-id="8d519-318">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="8d519-319">**パスワード**: 「Compliancepassword」</span><span class="sxs-lookup"><span data-stu-id="8d519-319">**Password**: "Compliancepassword"</span></span>

###### <a name="response-codes"></a><span data-ttu-id="8d519-320">応答コード</span><span class="sxs-lookup"><span data-stu-id="8d519-320">Response codes</span></span>

| <span data-ttu-id="8d519-321">応答コード</span><span class="sxs-lookup"><span data-stu-id="8d519-321">Response Code</span></span> | <span data-ttu-id="8d519-322">説明</span><span class="sxs-lookup"><span data-stu-id="8d519-322">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="8d519-323">200</span><span class="sxs-lookup"><span data-stu-id="8d519-323">200</span></span>               | <span data-ttu-id="8d519-324">問題ありません。応答本体に atom+xml 形式のイベントが含まれています</span><span class="sxs-lookup"><span data-stu-id="8d519-324">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="8d519-325">404</span><span class="sxs-lookup"><span data-stu-id="8d519-325">404</span></span>               | <span data-ttu-id="8d519-326">見つかりません</span><span class="sxs-lookup"><span data-stu-id="8d519-326">Not found</span></span>                                            |
| <span data-ttu-id="8d519-327">302</span><span class="sxs-lookup"><span data-stu-id="8d519-327">302</span></span>               | <span data-ttu-id="8d519-328">リダイレクト</span><span class="sxs-lookup"><span data-stu-id="8d519-328">Redirect</span></span>                                             |
| <span data-ttu-id="8d519-329">401</span><span class="sxs-lookup"><span data-stu-id="8d519-329">401</span></span>               | <span data-ttu-id="8d519-330">承認に失敗しました</span><span class="sxs-lookup"><span data-stu-id="8d519-330">Authorization Failed</span></span>                                 |
| <span data-ttu-id="8d519-331">403</span><span class="sxs-lookup"><span data-stu-id="8d519-331">403</span></span>               | <span data-ttu-id="8d519-332">認証に失敗しました</span><span class="sxs-lookup"><span data-stu-id="8d519-332">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="8d519-333">名前でイベントを取得する</span><span class="sxs-lookup"><span data-stu-id="8d519-333">Get an event by name</span></span>

- <span data-ttu-id="8d519-334">**メソッド**: GET</span><span class="sxs-lookup"><span data-stu-id="8d519-334">**Method**: GET</span></span>

- <span data-ttu-id="8d519-335">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="8d519-335">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>

- <span data-ttu-id="8d519-336">**ヘッダー**: キー = Content-Type、値 = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="8d519-336">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="8d519-337">**認証**: 基本</span><span class="sxs-lookup"><span data-stu-id="8d519-337">**Authentication**: Basic</span></span>

- <span data-ttu-id="8d519-338">**ユーザー名**: 「Complianceuser」</span><span class="sxs-lookup"><span data-stu-id="8d519-338">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="8d519-339">**パスワード**: 「Compliancepassword」</span><span class="sxs-lookup"><span data-stu-id="8d519-339">**Password**: "Compliancepassword"</span></span>


###### <a name="response-codes"></a><span data-ttu-id="8d519-340">応答コード</span><span class="sxs-lookup"><span data-stu-id="8d519-340">Response codes</span></span>

| <span data-ttu-id="8d519-341">応答コード</span><span class="sxs-lookup"><span data-stu-id="8d519-341">Response Code</span></span> | <span data-ttu-id="8d519-342">説明</span><span class="sxs-lookup"><span data-stu-id="8d519-342">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="8d519-343">200</span><span class="sxs-lookup"><span data-stu-id="8d519-343">200</span></span>               | <span data-ttu-id="8d519-344">問題ありません。応答本体に atom+xml 形式のイベントが含まれています</span><span class="sxs-lookup"><span data-stu-id="8d519-344">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="8d519-345">404</span><span class="sxs-lookup"><span data-stu-id="8d519-345">404</span></span>               | <span data-ttu-id="8d519-346">見つかりません</span><span class="sxs-lookup"><span data-stu-id="8d519-346">Not found</span></span>                                            |
| <span data-ttu-id="8d519-347">302</span><span class="sxs-lookup"><span data-stu-id="8d519-347">302</span></span>               | <span data-ttu-id="8d519-348">リダイレクト</span><span class="sxs-lookup"><span data-stu-id="8d519-348">Redirect</span></span>                                             |
| <span data-ttu-id="8d519-349">401</span><span class="sxs-lookup"><span data-stu-id="8d519-349">401</span></span>               | <span data-ttu-id="8d519-350">承認に失敗しました</span><span class="sxs-lookup"><span data-stu-id="8d519-350">Authorization Failed</span></span>                                 |
| <span data-ttu-id="8d519-351">403</span><span class="sxs-lookup"><span data-stu-id="8d519-351">403</span></span>               | <span data-ttu-id="8d519-352">認証に失敗しました</span><span class="sxs-lookup"><span data-stu-id="8d519-352">Authentication Failed</span></span>                                |

### <a name="use-powershell-or-any-http-client-to-create-the-event"></a><span data-ttu-id="8d519-353">PowerShell または HTTP クライアントを使用してイベントを作成する</span><span class="sxs-lookup"><span data-stu-id="8d519-353">Use PowerShell or any HTTP client to create the event</span></span>

<span data-ttu-id="8d519-354">PowerShell はバージョン 6 以降がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d519-354">PowerShell must be version 6 or later.</span></span>

<span data-ttu-id="8d519-355">PowerShell セッションで、次のスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="8d519-355">In a PowerShell session, run the following script:</span></span>

```powershell
param([string]$baseUri)

$userName = "UserName"

$password = "Password"

$securePassword = ConvertTo-SecureString $password -AsPlainText -Force

$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)

$EventName="EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))"

Write-Host "Start to create an event with name: $EventName"

$body = "<?xml version='1.0' encoding='utf-8' standalone='yes'?>

<entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'

xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'

xmlns='http://www.w3.org/2005/Atom'>

<category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />

<updated>7/14/2017 2:03:36 PM</updated>

<content type='application/xml'>

<m:properties>

<d:Name>$EventName</d:Name>

<d:EventType>e823b782-9a07-4e30-8091-034fc01f9347</d:EventType>

<d:SharePointAssetIdQuery>'ComplianceAssetId:123'</d:SharePointAssetIdQuery>

</m:properties>

</content>

</entry>"

$event = $null

try

{

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri "$baseUri/ComplianceRetentionEvent" -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

catch

{

$response = $_.Exception.Response

if($response.StatusCode -eq "Redirect")

{

$url = $response.Headers.Location

Write-Host "redirected to $url"

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

}

$event | fl *

```

