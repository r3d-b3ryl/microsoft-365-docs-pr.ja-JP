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
ms.openlocfilehash: 49fe330fa6844361a77caaebb0e6a411297ee643
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907017"
---
# <a name="start-retention-when-an-event-occurs"></a><span data-ttu-id="1cf4f-103">イベントの発生時に保持を開始する</span><span class="sxs-lookup"><span data-stu-id="1cf4f-103">Start retention when an event occurs</span></span>

><span data-ttu-id="1cf4f-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="1cf4f-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="1cf4f-p101">コンテンツを保持する際、保持期間は多くの場合、コンテンツの経過日数に基づいています。たとえば、ドキュメントを作成してから 7 年間保持をし、それから削除することができます。ただし、[保持ラベル](retention.md#retention-labels) を構成することで、特定の種類のイベントの発生を保持期間の基準として設定することもできます。イベントによって保持期間の開始がトリガーされ、その種類のイベントに保持ラベルが適用されているすべてのコンテンツに、ラベルの保持アクションが適用されます。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-p101">When you retain content, the retention period is often based on the age of the content. For example, you might retain documents for seven years after they're created and then delete them. But when you configure [retention labels](retention.md#retention-labels), you can also base a retention period on when a specific type of event occurs. The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.</span></span>
  
<span data-ttu-id="1cf4f-109">イベント ベースの保持を使用する場合の例:</span><span class="sxs-lookup"><span data-stu-id="1cf4f-109">Examples for using event-based retention:</span></span>
  
- <span data-ttu-id="1cf4f-110">**従業員が組織を離れる場合**、従業員が組織を離れてから 10 年間は、その従業員のレコードを保持する必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-110">**Employees leaving the organization** Suppose that employee records must be retained for 10 years from the time an employee leaves the organization.</span></span> <span data-ttu-id="1cf4f-111">10 年が経過した後、その従業員の採用、業績、および退職に関するすべてのドキュメントを廃棄する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-111">After 10 years elapse, all documents related to the hiring, performance, and termination of that employee must be disposed.</span></span> <span data-ttu-id="1cf4f-112">10 年の保持期間をトリガーするイベントは、組織を離れる従業員となります。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-112">The event that triggers the 10-year retention period is the employee leaving the organization.</span></span> 
    
- <span data-ttu-id="1cf4f-113">**契約満了の場合**、契約に関連するすべてのレコードは、契約満了後 5 年間は保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-113">**Contract expiration** Suppose that all records related to contracts must be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="1cf4f-114">5 年間の保持期間をトリガーするイベントは、契約の満了です。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-114">The event that triggers the five-year retention period is the expiration of the contract.</span></span> 
    
- <span data-ttu-id="1cf4f-p104">**製品の有効期間**: たとえば、組織に、技術仕様などのコンテンツに関して、最終製品製造日に関する保持要件があるとします。この場合、最後に製造された日が、保存期間をトリガーするイベントとなります。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-p104">**Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications. In this case, the last manufacturing date is the event that triggers the retention period.</span></span> 
    
<span data-ttu-id="1cf4f-p105">イベント ベースの保持は通常、レコード管理プロセスの一環として使用します。これは以下のことを意味します:</span><span class="sxs-lookup"><span data-stu-id="1cf4f-p105">Event-based retention is typically used as part of a records-management process. This means that:</span></span>
  
- <span data-ttu-id="1cf4f-119">イベントに基づく保持ラベルは、通常、レコード管理ソリューションの一環として、アイテムをレコードとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-119">Retention labels based on events also usually mark items as a record, as a part of a records management solution.</span></span> <span data-ttu-id="1cf4f-120">詳細については、「[レコードの詳細](records-management.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-120">For more information, see [Learn about records management](records-management.md).</span></span>

- <span data-ttu-id="1cf4f-121">レコードとして宣言されているもののイベント トリガーがまだ発生していない文書は、イベントがそのドキュメントの保存期間をトリガーするまで無期限に保持されます (レコードを完全に削除することはできません)。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-121">A document that's been declared a record but whose event trigger has not yet happened is retained indefinitely (records can't be permanently deleted), until an event triggers that document's retention period.</span></span>
    
- <span data-ttu-id="1cf4f-122">イベントに基づく保持ラベルは、通常、保持期間の最後に廃棄レビューをトリガーするため、レコード管理者はコンテンツを手動で確認して廃棄できます。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-122">Retention labels based on events usually trigger a disposition review at the end of the retention period, so that a records manager can manually review and dispose of the content.</span></span> <span data-ttu-id="1cf4f-123">詳細については、「[コンテンツの廃棄](disposition.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-123">For more information, see [Disposition of content](disposition.md).</span></span>
    

<span data-ttu-id="1cf4f-124">イベントに基づく保持ラベルには、Microsoft 365 の他の保持ラベルと同じ機能があります。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-124">A retention label based on an event has the same capabilities as any retention label in Microsoft 365.</span></span> <span data-ttu-id="1cf4f-125">詳細については、「[アイテム保持ポリシーと保持ラベルの詳細](retention.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-125">For more information, see [Learn about retention policies and retention labels](retention.md).</span></span>

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a><span data-ttu-id="1cf4f-126">イベントの種類、ラベル、イベント、アセット ID の関係を理解する</span><span class="sxs-lookup"><span data-stu-id="1cf4f-126">Understanding the relationship between event types, labels, events, and asset IDs</span></span>

<span data-ttu-id="1cf4f-127">イベント ベースの保持を活用するには、図と以下の説明に示すように、イベントの種類、保持ラベル、イベント、アセット ID の関係を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-127">To successfully use event-based retention, it's important to understand the relationship between event types, retention labels, events, and asset IDs as illustrated in the diagrams and the explanation that follows:</span></span> 
  
![図 1/2: イベントの種類、ラベル、イベント、アセット ID](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![図 2/2: イベントの種類、ラベル、イベント、アセット ID](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. <span data-ttu-id="1cf4f-130">さまざまな種類のコンテンツの保持ラベルを作成してから、イベントの種類に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-130">You create retention labels for different types of content and then associate them with a type of event.</span></span> <span data-ttu-id="1cf4f-131">たとえば、さまざまな種類の製品ファイルとレコードの保持ラベルは、製品を使用しなくなった時点からレコードを 10 年間保持する必要があるため、Product Lifetime という名前のイベントの種類に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-131">For example, retention labels for different types of product files and records are associated with an event type named Product Lifetime because those records must be retained for 10 years from the time the product reaches its end of life.</span></span>
    
2. <span data-ttu-id="1cf4f-132">ユーザー (通常はレコード管理者) はコンテンツにこれらの保持ラベルを適用し、(SharePoint と OneDrive のドキュメントの場合) アイテムごとに資産 ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-132">Users (typically records managers) apply those retention labels to content and (for documents in SharePoint and OneDrive) enter an asset ID for each item.</span></span> <span data-ttu-id="1cf4f-133">この例では、資産 ID は組織で使用される製品名またはコードです。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-133">In this example, the asset ID is a product name or code used by the organization.</span></span> <span data-ttu-id="1cf4f-134">したがって、各製品のレコードには保持ラベルが割り当てられ、各レコードには資産 ID を含むプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-134">Then, each product's records are assigned a retention label, and each record has a property that contains an asset ID.</span></span> <span data-ttu-id="1cf4f-135">この図は組織内のすべての製品レコードの **すべてのコンテンツ** を表しており、各アイテムにはそのレコードに該当する製品の資産 ID が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-135">The diagram represents **all the content** for all product records in an organization, and each item bears the asset ID of the product whose record it is.</span></span> 
    
3. <span data-ttu-id="1cf4f-p111">製品の有効期限がイベントの種類であり、有効期限が切れた特定の製品がイベントになります。そのイベントの種類のイベントが発生したら (この場合、製品の有効期限が切れるとき)、以下を指定するイベントを作成します。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-p111">Product Lifetime is the event type; a specific product reaching end of life is an event. When an event of that event type occurs—in this case, when a product reaches its end of life—you create an event that specifies:</span></span>
    
   - <span data-ttu-id="1cf4f-138">(SharePoint および OneDrive のドキュメントの) アセット ID。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-138">An asset ID (for SharePoint and OneDrive documents)</span></span>
    
   - <span data-ttu-id="1cf4f-p112">(Exchange アイテムの) キーワード。上の例において組織は、製品レコードを含むメッセージで製品コードを使用するため、Exchange アイテムのキーワードは SharePoint および OneDrive ドキュメントのアセット ID と機能的に同じになります。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-p112">Keywords (for Exchange items). In this example, the organization uses a product code in messages containing product records, so the keyword for Exchange items is functionally the same as the asset ID for SharePoint and OneDrive documents.</span></span>
    
   - <span data-ttu-id="1cf4f-p113">イベントが発生した日付。この日付は、保持期間の開始日として使用されます。この日付には、現在、過去、または将来の日付を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-p113">The date when the event occurred. This date is used as the start of the retention period. This date can be the current, a past, or a future date.</span></span>

4. <span data-ttu-id="1cf4f-144">イベントの作成後、イベントの日付は、そのイベントの種類の保持ラベルを持ち、指定された資産 ID またはキーワードを含むすべてのコンテンツに同期されます。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-144">After you create an event, that event date is synchronized to all the content that has a retention label of that event type and that contains the specified asset ID or keyword.</span></span> <span data-ttu-id="1cf4f-145">他の保持ラベルと同様に、この同期には最大で 7 日間かかります。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-145">Like any retention label, this synchronization can take up to seven days.</span></span> <span data-ttu-id="1cf4f-146">前の図では、赤で囲まれているアイテムはすべて、このイベントによって保持期間がトリガーされています。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-146">In the previous diagram, all the items circled in red have their retention period triggered by this event.</span></span> <span data-ttu-id="1cf4f-147">言い換えれば、この製品の期限が切れたとき、そのイベントがその製品のレコードの保持期間のトリガーとなります。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-147">In other words, when this product reaches its end of life, that event triggers the retention period for that product's records.</span></span>

<span data-ttu-id="1cf4f-148">イベントの資産 ID またはキーワードを指定しない場合、そのイベントの種類の保持ラベルの付いた **すべてのコンテンツ** が、イベントによってトリガーされる保持期間を持つことを理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-148">It's important to understand that if you don't specify an asset ID or keywords for an event, **all content** with a retention label of that event type will have its retention period triggered by the event.</span></span> <span data-ttu-id="1cf4f-149">つまり、前の図の場合であれば、すべてのコンテンツの保持が開始されます。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-149">This means that in the previous diagram, all content would start being retained.</span></span> <span data-ttu-id="1cf4f-150">これは、意図したものとは異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-150">This might not be what you intend.</span></span>

<span data-ttu-id="1cf4f-151">最後に、それぞれの保持ラベルにはそれぞれの保持設定があることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-151">Finally, remember that each retention label has its own retention settings.</span></span> <span data-ttu-id="1cf4f-152">この例では、すべて 10 年間に指定されていますが、それぞれのラベルが異なる保持期間を持つ保持ラベルを、1 つのイベントでトリガーすることができます。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-152">In this example, they all specify 10 years, but it's possible for an event to trigger retention labels where each label has a different retention period.</span></span>
  
## <a name="how-to-set-up-event-driven-retention"></a><span data-ttu-id="1cf4f-153">イベント ドリブンの保持のセットアップ方法</span><span class="sxs-lookup"><span data-stu-id="1cf4f-153">How to set up event-driven retention</span></span>

<span data-ttu-id="1cf4f-154">イベント ドリブンの保持のワークフロー概要:</span><span class="sxs-lookup"><span data-stu-id="1cf4f-154">High-level workflow for event-driven retention:</span></span>
  
![イベント ベースの保持をセットアップするワークフローの図](../media/event-based-retention-process.png)
  
> [!TIP]
> <span data-ttu-id="1cf4f-156">SharePont の管理プロパティを使用して保持ラベルを自動適用し、イベント ドリブンの保持を実装する詳細なシナリオについては、[保持ラベルを使用して SharePoint ドキュメントのライフサイクルを管理する](auto-apply-retention-labels-scenario.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-156">See [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md) for a detailed scenario about using managed properties in SharePoint to auto-apply retention labels and implement event-driven retention.</span></span>

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a><span data-ttu-id="1cf4f-157">手順 1: 保持期間がイベントに基づくラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="1cf4f-157">Step 1: Create a label whose retention period is based on an event</span></span>

<span data-ttu-id="1cf4f-158">保持ラベルを作成して構成するには、[[保持ラベルの作成と構成](./create-apply-retention-labels.md#create-and-configure-retention-labels)] の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-158">To create and configure your retention label, use the instructions from [Create and configure retention labels](./create-apply-retention-labels.md#create-and-configure-retention-labels).</span></span> <span data-ttu-id="1cf4f-159">ただし、イベント ベースの保持に固有の [保持ラベルの作成] ウィザードの [**保持設定の定義**] ページで、**次の期間に基づいて保持期間を開始** した後、既定のイベントの種類の 1 つをドロップダウン リスト、または **新しいイベントの種類の作成** を選択して独自のリストを作成します。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-159">But specific to event-based retention, on the **Define retention settings** page of the Create retention label wizard, after **Start the retention period based on**, select one of the default event types from the dropdown list, or create your own by selecting **Create new event type**:</span></span>

![保持ラベルの新しいイベントの種類を作成する](../media/SPRetention6.png)

<span data-ttu-id="1cf4f-161">イベントの種類とは、保持ラベルに関連付けるイベントの一般的な説明です。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-161">An event type is simply a general description of an event that you want to associate with a retention label.</span></span>

<span data-ttu-id="1cf4f-162">既定のイベントの種類は、簡単に識別できるようにドロップダウン リストの名前の後に **(イベントの種類)** があり、**[レコード管理]**  >  **[イベント]** タブ、**[イベントの種類の管理]** からイベントの種類を確認して作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-162">The default event types have **(event type)** after their name in the dropdown list for easier identification, and you can also see and create event type from the **Records management** > **Events** tab > **Manage event types**.</span></span>

<span data-ttu-id="1cf4f-163">イベント ベースの保持には、次のような保持の設定が必要になります。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-163">Event-based retention requires retention settings that:</span></span>
  
- <span data-ttu-id="1cf4f-164">コンテンツを保持する。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-164">Retain the content.</span></span>
    
- <span data-ttu-id="1cf4f-165">保存期間の終わりに、コンテンツの自動削除または廃棄レビューのトリガーを行う。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-165">Delete the content automatically or trigger a disposition review at the end of the retention period.</span></span>
  
<span data-ttu-id="1cf4f-166">通常、イベント ベースの保持は、通常、レコードが宣言されているコンテンツに使用されるので、コンテンツを[レコード](records-management.md#records)としてマークするオプションも選択する必要があるかどうかを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-166">Event-based retention is typically used for content that's declared a record, so this is a good time to check whether you also need to select the option that marks content as a [record](records-management.md#records).</span></span>

<span data-ttu-id="1cf4f-167">新しいイベントの種類を作成するのではなく、既存のイベントの種類を使用している場合は、手順 3 に進みます。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-167">If you're using an existing event type rather than creating a new event type, skip to step 3.</span></span>

> [!NOTE]
> <span data-ttu-id="1cf4f-168">イベントの種類を選択して保持ラベルを保存すると、イベントの種類の変更はできませんので、ご注意ください。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-168">After you choose an event type and save the retention label, the event type cannot be changed.</span></span>

### <a name="step-2-create-a-new-event-type-for-your-label"></a><span data-ttu-id="1cf4f-169">手順 2: ラベルの新しいイベントの種類を作成する</span><span class="sxs-lookup"><span data-stu-id="1cf4f-169">Step 2: Create a new event type for your label</span></span>

<span data-ttu-id="1cf4f-170">保持設定で、[**新しいイベントの種類の作成**] を選択した場合は、イベントの種類の名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-170">For the retention settings, if you selected **Create new event type**, enter a name and description for your event type.</span></span> <span data-ttu-id="1cf4f-171">次に、[**次へ**]、[**送信**]、[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-171">Then select **Next**, **Submit**, and **Done**.</span></span>

<span data-ttu-id="1cf4f-172">[**保持設定の定義**] ページに戻り、[**保持期間の開始日**] のドロップダウン リストを使用して、作成したイベントの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-172">Back on the **Define retention settings** page, for **Start the retention period based on**, use the dropdown list to select the event type that you created.</span></span>

  
### <a name="step-3-publish-or-auto-apply-the-event-based-retention-labels"></a><span data-ttu-id="1cf4f-173">手順 3: イベント ベースの保持ラベルを発行または自動適用する</span><span class="sxs-lookup"><span data-stu-id="1cf4f-173">Step 3: Publish or auto-apply the event-based retention labels</span></span>

<span data-ttu-id="1cf4f-174">他の保持ラベルと同じように、イベント ベースのラベルを発行するか自動適用して、コンテンツに手動または自動で適用されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-174">Just like any retention label, you need to publish or auto-apply an event-based label, for it to be manually or automatically applied to content:</span></span>
- [<span data-ttu-id="1cf4f-175">アイテム保持ラベルを作成してアプリに適用する</span><span class="sxs-lookup"><span data-stu-id="1cf4f-175">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
- [<span data-ttu-id="1cf4f-176">保持ラベルをコンテンツに自動的に適用する</span><span class="sxs-lookup"><span data-stu-id="1cf4f-176">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

### <a name="step-4-enter-an-asset-id"></a><span data-ttu-id="1cf4f-177">手順 4: アセット ID を入力する</span><span class="sxs-lookup"><span data-stu-id="1cf4f-177">Step 4: Enter an asset ID</span></span>

<span data-ttu-id="1cf4f-178">イベント ベースのラベルがコンテンツに適用されたら、アイテムごとに資産 ID を入力できます。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-178">After an event-based label is applied to content, you can enter an asset ID for each item.</span></span> <span data-ttu-id="1cf4f-179">たとえば、組織では以下のものを使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-179">For example, your organization might use:</span></span>
  
- <span data-ttu-id="1cf4f-180">特定の製品のみのコンテンツ保持に使用する製品コード。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-180">Product codes that you can use to retain content for only a specific product.</span></span>
    
- <span data-ttu-id="1cf4f-181">特定の製品のみのコンテンツ保持に使用するプロジェクト コード。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-181">Project codes that you can use to retain content for only a specific project.</span></span>
    
- <span data-ttu-id="1cf4f-182">特定の製品のみのコンテンツ保持に使用する従業員 ID。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-182">Employee IDs that you can use to retain content for only a specific person.</span></span>
    
<span data-ttu-id="1cf4f-183">資産 ID は、SharePoint と OneDrive で利用できる別のドキュメント プロパティです。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-183">Asset ID is simply another document property that's available in SharePoint and OneDrive.</span></span> <span data-ttu-id="1cf4f-184">組織では既に別のドキュメント プロパティや ID を使用してコンテンツを分類している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-184">Your organization might already use other document properties and IDs to classify content.</span></span> <span data-ttu-id="1cf4f-185">その場合、イベントの作成時にそれらのプロパティおよび値を使用することもできます (後述する手順 6 を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-185">If so, you can also use those properties and values when you create an event—see step 6 that follows.</span></span> <span data-ttu-id="1cf4f-186">重要な点は、ドキュメント プロパティで *property:value* の組み合わせを使用して、そのアイテムをイベントの種類に関連付ける必要があるということです。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-186">The important point is that you must use some *property:value* combination in the document properties to associate that item with an event type.</span></span>
  
![アセット ID を入力するテキスト ボックス](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a><span data-ttu-id="1cf4f-188">手順 5: イベントを作成する</span><span class="sxs-lookup"><span data-stu-id="1cf4f-188">Step 5: Create an event</span></span>

<span data-ttu-id="1cf4f-189">製品の使用を終えるなど、イベントの種類に関する特定のインスタンスが発生するときは、Microsoft 365 コンプライアンス センターで **[レコード管理]** > **[イベント]** ページの順に移動して [**+ 作成**] を選択してイベントを作成します。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-189">When a particular instance of that event type occurs, such as a product reaches its end of life, go to the **Records management** > **Events** page in the Microsoft 365 compliance center, and select **+ Create** to create an event.</span></span> <span data-ttu-id="1cf4f-190">ここでは、イベントを作成し、トリガーします。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-190">You trigger the event by creating it, here.</span></span>

![イベント ベースの保持ラベルの保持の開始をトリガーするイベントを作成する](../media/create-event-records-management.png)

<span data-ttu-id="1cf4f-192">テナントごとに最大 100 万件のイベントがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-192">Up to one million events are supported per tenant.</span></span>

### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a><span data-ttu-id="1cf4f-193">手順 6: 手順 2 でのラベルを使用したイベントの種類と同じものを選択する</span><span class="sxs-lookup"><span data-stu-id="1cf4f-193">Step 6: Choose the same event type used by the label in step 2</span></span>

<span data-ttu-id="1cf4f-194">イベントを作成するときは、手順 2 の保持ラベル設定で指定したものと同じイベントの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-194">When you create the event, choose the same event type specified in the retention label settings in step 2.</span></span> <span data-ttu-id="1cf4f-195">たとえば、ラベル設定のイベントの種類として [**製品の有効期間**] を選択した場合、イベントを作成するときに [**製品の有効期間**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-195">For example, if you selected **Product Lifetime** as your event type for the label settings, select **Product Lifetime** when you create the event.</span></span> <span data-ttu-id="1cf4f-196">そのイベントの種類が選択されたイベントに適用されている保持ラベルの付いたコンテンツのみが、トリガーされる保持期間を持ちます。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-196">Only content with retention labels applied to it of that event type will have its retention period triggered.</span></span>

![イベントの種類を選択するイベント設定のオプション](../media/choose-event-type-records-management.png)

<span data-ttu-id="1cf4f-198">または、イベントの種類が異なる複数の保持ラベルのイベントを作成する必要がある場合は、[**既存のラベルの選択**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-198">Alternatively, if you need to create an event for multiple retention labels that have different event types, select the **Choose Existing Labels** option.</span></span> <span data-ttu-id="1cf4f-199">次に、このイベントに関連付けるイベントの種類に構成されているラベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-199">Then, select the labels that are configured for the event types you want to associate with this event.</span></span>

### <a name="step-7-enter-keywords-or-an-asset-id"></a><span data-ttu-id="1cf4f-200">手順 7: キーワードまたはアセット ID を入力する</span><span class="sxs-lookup"><span data-stu-id="1cf4f-200">Step 7: Enter keywords or an asset ID</span></span>

<span data-ttu-id="1cf4f-201">ここで、資産 ID (SharePoint および OneDrive コンテンツの場合) またはキーワード (Exchange コンテンツの場合) を指定して、コンテンツの範囲を絞り込みます。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-201">Now you narrow the scope of the content by specifying asset IDs for SharePoint and OneDrive content, or keywords for Exchange content.</span></span> <span data-ttu-id="1cf4f-202">資産 ID の場合、保持は指定された *property:value* ペアを持つコンテンツにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-202">For asset IDs, retention will be enforced only on content with the specified *property:value* pair.</span></span> <span data-ttu-id="1cf4f-203">資産 ID が入力されていない場合は、そのイベントの種類のラベルの付いたすべてのコンテンツに同じ保持期限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-203">If an asset ID is not entered, all content with labels of that event type get the same retention date applied to them.</span></span>

<span data-ttu-id="1cf4f-204">例えば、資産 ID プロパティを使用する場合は、下に示される資産 ID のボックスに 「`ComplianceAssetID:<value>`」 と入力します。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-204">For example: If you're using the Asset ID property, enter `ComplianceAssetID:<value>` in the box for asset IDs shown below.</span></span>
  
<span data-ttu-id="1cf4f-205">組織は、このイベントの種類に関するドキュメントに他のプロパティと ID を適用している場合があります。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-205">Your organization might have applied other properties and IDs to the documents related to this event type.</span></span> <span data-ttu-id="1cf4f-206">たとえば、特定の製品のレコードを検出する必要がある場合、ID はカスタム プロパティ製品 ID とその値 "XYZ" の組み合わせである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-206">For example, if you need to detect a specific product's records, the ID might be a combination of your custom property ProductID and the value "XYZ".</span></span> <span data-ttu-id="1cf4f-207">この場合は、次の図に示されるアセット ID のボックスに 「`ProductID:XYZ`」 と入力します。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-207">In this case, you'd enter `ProductID:XYZ` in the box for asset IDs shown in the following picture.</span></span>
  
<span data-ttu-id="1cf4f-208">Exchange アイテムの場合、キーワード を使用します。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-208">For Exchange items, use keywords.</span></span> <span data-ttu-id="1cf4f-209">AND、OR、NOT などの検索演算子を使用して、クエリを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-209">You can use a query by using search operators such as AND, OR, and NOT.</span></span> <span data-ttu-id="1cf4f-210">詳細については、「[コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-210">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="1cf4f-211">最後に、イベントが発生した日付を選択します。この日付が、保持期間の開始日として使用されます。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-211">Finally, choose the date when the event occurred; this date is used as the start of the retention period.</span></span> <span data-ttu-id="1cf4f-212">イベントの作成後、そのイベントの日付は、そのイベントの種類の保持ラベル、資産 ID、キーワードを持つすべてのコンテンツに同期されます。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-212">After you create an event, that event date is synchronized to all the content with a retention label of that event type, asset ID, and keywords.</span></span> <span data-ttu-id="1cf4f-213">その他の保持ラベルと同様に、この同期には最大で 7 日間かかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-213">As with any retention label, this synchronization can take up to seven days.</span></span>
  
![[イベントの設定] ページ](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)

<span data-ttu-id="1cf4f-215">イベントを作成すると、既にラベル付けされてインデックスが作成されているコンテンツの保持設定が有効になります。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-215">After creating an event, the retention settings take effect for the content that's already labeled and indexed.</span></span> <span data-ttu-id="1cf4f-216">イベントが作成された後に保持ラベルが新しいコンテンツに追加された場合は、同じ詳細を使用して新しいイベントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-216">If the retention label is added to new content after the event is created, you must create a new event with the same details.</span></span>

<span data-ttu-id="1cf4f-217">イベントを削除しても、既にラベル付けされているコンテンツに対して現在有効になっている保持設定は取り消されません。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-217">Deleting an event doesn't cancel the retention settings that are now in effect for the content that's already labeled.</span></span> <span data-ttu-id="1cf4f-218">それを行うには、同じ詳細を使用して新しいイベントを作成しますが、日付は空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-218">To do that, create a new event with the same details, but leave the date blank.</span></span> 

## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a><span data-ttu-id="1cf4f-219">コンテンツ検索を使用して、特定のラベルまたはアセット ID が適用されたすべてのコンテンツを検索する</span><span class="sxs-lookup"><span data-stu-id="1cf4f-219">Use Content Search to find all content with a specific label or asset ID</span></span>

<span data-ttu-id="1cf4f-220">保持ラベルをコンテンツに割り当てた後は、特定の保持ラベルで分類されている、または特定のアセット ID を含むすべてのコンテンツをコンテンツ検索を使用して検索することができます。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-220">After retention labels are assigned to content, you can use content search to find all content that's classified with a specific retention label or that contains a specific asset ID:</span></span>
  
- <span data-ttu-id="1cf4f-221">特定の保持ラベルを持つすべてのコンテンツを検索するには、 **保持ラベル** の条件を選択した後、完全なラベル名を入力するか、ラベル名の一部を入力してワイルドカードを使用します。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-221">To find all content with a specific retention label, choose the **Retention label** condition, and then enter the complete label name or part of the label name and use a wildcard.</span></span> 
    
- <span data-ttu-id="1cf4f-222">特定のアセット ID を持つすべてのコンテンツを検索するには、**ComplianceAssetID** プロパティと `ComplianceAssetID:<value>` のフォーマットを使用した値を入力します。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-222">To find all content with a specific asset ID, enter the **ComplianceAssetID** property and a value, using the format `ComplianceAssetID:<value>`.</span></span> 
    
<span data-ttu-id="1cf4f-223">詳細については、「[コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-223">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>

## <a name="automate-events-by-using-powershell"></a><span data-ttu-id="1cf4f-224">PowerShell を使用してイベントを自動化する</span><span class="sxs-lookup"><span data-stu-id="1cf4f-224">Automate events by using PowerShell</span></span>

<span data-ttu-id="1cf4f-225">PowerShell スクリプトを使用して、ビジネス アプリケーションからイベント ベースの保持を自動化することができます。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-225">You can use a PowerShell script to automate event-based retention from your business applications.</span></span> <span data-ttu-id="1cf4f-226">イベント ベースの保持で利用可能な PowerShell コマンドレットは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-226">The PowerShell cmdlets available for event-based retention:</span></span>
  
- [<span data-ttu-id="1cf4f-227">Get-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="1cf4f-227">Get-ComplianceRetentionEventType</span></span>](/powershell/module/exchange/get-complianceretentioneventtype)
    
- [<span data-ttu-id="1cf4f-228">New-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="1cf4f-228">New-ComplianceRetentionEventType</span></span>](/powershell/module/exchange/new-complianceretentioneventtype)
    
- [<span data-ttu-id="1cf4f-229">Remove-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="1cf4f-229">Remove-ComplianceRetentionEventType</span></span>](/powershell/module/exchange/remove-complianceretentioneventtype)
    
- [<span data-ttu-id="1cf4f-230">Set-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="1cf4f-230">Set-ComplianceRetentionEventType</span></span>](/powershell/module/exchange/set-complianceretentioneventtype)
    
- [<span data-ttu-id="1cf4f-231">Get-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="1cf4f-231">Get-ComplianceRetentionEvent</span></span>](/powershell/module/exchange/get-complianceretentionevent)
    
- [<span data-ttu-id="1cf4f-232">New-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="1cf4f-232">New-ComplianceRetentionEvent</span></span>](/powershell/module/exchange/new-complianceretentionevent)
    

## <a name="automate-events-by-using-a-rest-api"></a><span data-ttu-id="1cf4f-233">REST API を使用してイベントを自動化する</span><span class="sxs-lookup"><span data-stu-id="1cf4f-233">Automate events by using a REST API</span></span>

<span data-ttu-id="1cf4f-234">REST API を使用して、保持期間の開始をトリガーするイベントを自動的に作成できます。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-234">You can use a REST API to automatically create the events that trigger the start of the retention time.</span></span>

<span data-ttu-id="1cf4f-235">REST API は一連の HTTP 操作 (HTTP メソッド) をサポートするサービス エンドポイントで、サービス リソースへのアクセス権の作成/取得/更新/削除をできるようにします。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-235">A REST API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources.</span></span> <span data-ttu-id="1cf4f-236">詳細については、「[REST API 要求/応答のコンポーネント](/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-236">For more information, see [Components of a REST API request/response](/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span></span> <span data-ttu-id="1cf4f-237">Microsoft 365 REST API を使用することにより、POST および GET メソッドを使用してイベントを作成および取得できます。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-237">By using the Microsoft 365 REST API, events can be created and retrieved using the POST and GET methods.</span></span>

<span data-ttu-id="1cf4f-238">REST API を使用するには、2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-238">There are two options for using the REST API:</span></span>

- <span data-ttu-id="1cf4f-239">イベントの発生を自動的にトリガーする **Microsoft Power Automate または同様のアプリケーション**。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-239">**Microsoft Power Automate or a similar application** to trigger the occurrence of an event automatically.</span></span> <span data-ttu-id="1cf4f-240">Microsoft Power Automate は、他のシステムに接続するためのオーケストレーターなので、カスタム ソリューションを作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-240">Microsoft Power Automate is an orchestrator for connecting to other systems, so you don't need to write a custom solution.</span></span> <span data-ttu-id="1cf4f-241">詳細については、[Power Automate Web サイト](https://flow.microsoft.com/ja-JP/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-241">For more information, see the [Power Automate website](https://flow.microsoft.com/ja-JP/).</span></span>

- <span data-ttu-id="1cf4f-242">**PowerShell または HTTP クライアントで REST API** を呼び出して、カスタム ソリューションの一部である PowerShell (バージョン 6 以降) を使用してイベントを作成します。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-242">**PowerShell or an HTTP client to call the REST API** to create events by using PowerShell (version 6 or later), which is part of a custom solution.</span></span>

<span data-ttu-id="1cf4f-243">REST API を使用する前に、グローバル管理者として、保持イベント呼び出しに使用する URL を確認します。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-243">Before you use the REST API, as a global administrator, confirm the URL to use for the retention event call.</span></span> <span data-ttu-id="1cf4f-244">これを行うには、REST API の URL を使用して、保持イベント呼び出しの取得を実行します。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-244">To do this, run a GET retention event call by using the REST API URL:</span></span>

```console
https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent
```

<span data-ttu-id="1cf4f-245">応答コードを確認します。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-245">Check the response code.</span></span> <span data-ttu-id="1cf4f-246">302 の場合は、応答ヘッダーの Location プロパティからリダイレクトされた URL を取得し、以下の手順で `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent` の代わりにその URL を使用します。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-246">If it's 302, get the redirected URL from the Location property of the response header and use that URL instead of `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent` in the instructions that follow.</span></span>

<span data-ttu-id="1cf4f-247">自動作成されたイベントは、Microsoft 365 コンプライアンス センター > **レコード管理** >  **イベント** で表示することで確認できます。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-247">The events that get automatically created can be confirmed by viewing them in the Microsoft 365 compliance center > **Records management** >  **Events**.</span></span>

### <a name="use-microsoft-power-automate-to-create-the-event"></a><span data-ttu-id="1cf4f-248">Microsoft Power Automate を使用してイベントを作成する</span><span class="sxs-lookup"><span data-stu-id="1cf4f-248">Use Microsoft Power Automate to create the event</span></span>

<span data-ttu-id="1cf4f-249">Microsoft 365 REST API を使用してイベントを作成するフローを作成します</span><span class="sxs-lookup"><span data-stu-id="1cf4f-249">Create a flow that creates an event using the Microsoft 365 REST API:</span></span>

![Flow を使用してイベントを作成する](../media/automate-event-driven-retention-flow-1.png)

![Flow を使用して REST API を呼び出す](../media/automate-event-driven-retention-flow-2.png)

#### <a name="create-an-event"></a><span data-ttu-id="1cf4f-252">イベントを作成する</span><span class="sxs-lookup"><span data-stu-id="1cf4f-252">Create an event</span></span>

<span data-ttu-id="1cf4f-253">REST API を呼び出すサンプル コード</span><span class="sxs-lookup"><span data-stu-id="1cf4f-253">Sample code to call the REST API:</span></span>

- <span data-ttu-id="1cf4f-254">**方法**: 投稿</span><span class="sxs-lookup"><span data-stu-id="1cf4f-254">**Method**: POST</span></span>
- <span data-ttu-id="1cf4f-255">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="1cf4f-255">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>
- <span data-ttu-id="1cf4f-256">**ヘッダー**: キー = Content-Type、値 = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="1cf4f-256">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>
- <span data-ttu-id="1cf4f-257">**本文**:</span><span class="sxs-lookup"><span data-stu-id="1cf4f-257">**Body**:</span></span>
    
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
    
- <span data-ttu-id="1cf4f-258">**認証**: 基本</span><span class="sxs-lookup"><span data-stu-id="1cf4f-258">**Authentication**: Basic</span></span>
- <span data-ttu-id="1cf4f-259">**ユーザー名**: 「Complianceuser」</span><span class="sxs-lookup"><span data-stu-id="1cf4f-259">**Username**: "Complianceuser"</span></span>
- <span data-ttu-id="1cf4f-260">**パスワード**: 「Compliancepassword」</span><span class="sxs-lookup"><span data-stu-id="1cf4f-260">**Password**: "Compliancepassword"</span></span>


##### <a name="available-parameters"></a><span data-ttu-id="1cf4f-261">利用可能なパラメーター</span><span class="sxs-lookup"><span data-stu-id="1cf4f-261">Available parameters</span></span>


|<span data-ttu-id="1cf4f-262">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1cf4f-262">Parameters</span></span>|<span data-ttu-id="1cf4f-263">説明</span><span class="sxs-lookup"><span data-stu-id="1cf4f-263">Description</span></span>|<span data-ttu-id="1cf4f-264">Notes</span><span class="sxs-lookup"><span data-stu-id="1cf4f-264">Notes</span></span>|
|--- |--- |--- |
|<span data-ttu-id="1cf4f-265"><d:Name></d:Name></span><span class="sxs-lookup"><span data-stu-id="1cf4f-265"><d:Name></d:Name></span></span>|<span data-ttu-id="1cf4f-266">イベントの一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-266">Provide a unique name for the event,</span></span>|<span data-ttu-id="1cf4f-267">末尾のスペースおよび以下の文字は使用できません。% \* \ & < \> \| # ?</span><span class="sxs-lookup"><span data-stu-id="1cf4f-267">Cannot contain trailing spaces or the following characters: % \* \ & < \> \| # ?</span></span> <span data-ttu-id="1cf4f-268">, : ;</span><span class="sxs-lookup"><span data-stu-id="1cf4f-268">, : ;</span></span>|
|<span data-ttu-id="1cf4f-269"><d:EventType></d:EventType></span><span class="sxs-lookup"><span data-stu-id="1cf4f-269"><d:EventType></d:EventType></span></span>|<span data-ttu-id="1cf4f-270">イベントの種類の名前 (または GUID) を入力します。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-270">Enter event type name (or Guid),</span></span>|<span data-ttu-id="1cf4f-271">例: 「従業員の退職」。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-271">Example: "Employee termination".</span></span> <span data-ttu-id="1cf4f-272">イベントの種類を保持ラベルに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-272">Event type has to be associated with a retention label.</span></span>|
|<span data-ttu-id="1cf4f-273"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span><span class="sxs-lookup"><span data-stu-id="1cf4f-273"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span></span>|<span data-ttu-id="1cf4f-274">「ComplianceAssetId:」 と従業員 ID を入力します</span><span class="sxs-lookup"><span data-stu-id="1cf4f-274">Enter "ComplianceAssetId:" + employee ID</span></span>|<span data-ttu-id="1cf4f-275">例: 「ComplianceAssetId: 12345」</span><span class="sxs-lookup"><span data-stu-id="1cf4f-275">Example: "ComplianceAssetId:12345"</span></span>|
|<span data-ttu-id="1cf4f-276"><d:EventDateTime></d:EventDateTime></span><span class="sxs-lookup"><span data-stu-id="1cf4f-276"><d:EventDateTime></d:EventDateTime></span></span>|<span data-ttu-id="1cf4f-277">イベントの日時</span><span class="sxs-lookup"><span data-stu-id="1cf4f-277">Event Date and Time</span></span>|<span data-ttu-id="1cf4f-278">形式: yyyy-MM-ddTHH:mm:ssZ、例: 2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="1cf4f-278">Format: yyyy-MM-ddTHH:mm:ssZ, Example: 2018-12-01T00:00:00Z</span></span>
|

###### <a name="response-codes"></a><span data-ttu-id="1cf4f-279">応答コード</span><span class="sxs-lookup"><span data-stu-id="1cf4f-279">Response codes</span></span>

| <span data-ttu-id="1cf4f-280">応答コード</span><span class="sxs-lookup"><span data-stu-id="1cf4f-280">Response Code</span></span> | <span data-ttu-id="1cf4f-281">説明</span><span class="sxs-lookup"><span data-stu-id="1cf4f-281">Description</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="1cf4f-282">302</span><span class="sxs-lookup"><span data-stu-id="1cf4f-282">302</span></span>               | <span data-ttu-id="1cf4f-283">リダイレクト</span><span class="sxs-lookup"><span data-stu-id="1cf4f-283">Redirect</span></span>              |
| <span data-ttu-id="1cf4f-284">201</span><span class="sxs-lookup"><span data-stu-id="1cf4f-284">201</span></span>               | <span data-ttu-id="1cf4f-285">作成済み</span><span class="sxs-lookup"><span data-stu-id="1cf4f-285">Created</span></span>               |
| <span data-ttu-id="1cf4f-286">403</span><span class="sxs-lookup"><span data-stu-id="1cf4f-286">403</span></span>               | <span data-ttu-id="1cf4f-287">承認に失敗しました</span><span class="sxs-lookup"><span data-stu-id="1cf4f-287">Authorization Failed</span></span>  |
| <span data-ttu-id="1cf4f-288">401</span><span class="sxs-lookup"><span data-stu-id="1cf4f-288">401</span></span>               | <span data-ttu-id="1cf4f-289">認証に失敗しました</span><span class="sxs-lookup"><span data-stu-id="1cf4f-289">Authentication Failed</span></span> |

##### <a name="get-events-based-on-a-time-range"></a><span data-ttu-id="1cf4f-290">時間範囲に基づいてイベントを取得する</span><span class="sxs-lookup"><span data-stu-id="1cf4f-290">Get events based on a time range</span></span>

- <span data-ttu-id="1cf4f-291">**メソッド**: GET</span><span class="sxs-lookup"><span data-stu-id="1cf4f-291">**Method**: GET</span></span>

- <span data-ttu-id="1cf4f-292">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span><span class="sxs-lookup"><span data-stu-id="1cf4f-292">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span></span>

- <span data-ttu-id="1cf4f-293">**ヘッダー**: キー = Content-Type、値 = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="1cf4f-293">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="1cf4f-294">**認証**: 基本</span><span class="sxs-lookup"><span data-stu-id="1cf4f-294">**Authentication**: Basic</span></span>

- <span data-ttu-id="1cf4f-295">**ユーザー名**: 「Complianceuser」</span><span class="sxs-lookup"><span data-stu-id="1cf4f-295">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="1cf4f-296">**パスワード**: 「Compliancepassword」</span><span class="sxs-lookup"><span data-stu-id="1cf4f-296">**Password**: "Compliancepassword"</span></span>


###### <a name="response-codes"></a><span data-ttu-id="1cf4f-297">応答コード</span><span class="sxs-lookup"><span data-stu-id="1cf4f-297">Response codes</span></span>

| <span data-ttu-id="1cf4f-298">応答コード</span><span class="sxs-lookup"><span data-stu-id="1cf4f-298">Response Code</span></span> | <span data-ttu-id="1cf4f-299">説明</span><span class="sxs-lookup"><span data-stu-id="1cf4f-299">Description</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="1cf4f-300">200</span><span class="sxs-lookup"><span data-stu-id="1cf4f-300">200</span></span>               | <span data-ttu-id="1cf4f-301">問題ありません。イベントの一覧は atom+ xml 形式です</span><span class="sxs-lookup"><span data-stu-id="1cf4f-301">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="1cf4f-302">404</span><span class="sxs-lookup"><span data-stu-id="1cf4f-302">404</span></span>               | <span data-ttu-id="1cf4f-303">見つかりません</span><span class="sxs-lookup"><span data-stu-id="1cf4f-303">Not found</span></span>                         |
| <span data-ttu-id="1cf4f-304">302</span><span class="sxs-lookup"><span data-stu-id="1cf4f-304">302</span></span>               | <span data-ttu-id="1cf4f-305">リダイレクト</span><span class="sxs-lookup"><span data-stu-id="1cf4f-305">Redirect</span></span>                          |
| <span data-ttu-id="1cf4f-306">401</span><span class="sxs-lookup"><span data-stu-id="1cf4f-306">401</span></span>               | <span data-ttu-id="1cf4f-307">承認に失敗しました</span><span class="sxs-lookup"><span data-stu-id="1cf4f-307">Authorization Failed</span></span>              |
| <span data-ttu-id="1cf4f-308">403</span><span class="sxs-lookup"><span data-stu-id="1cf4f-308">403</span></span>               | <span data-ttu-id="1cf4f-309">認証に失敗しました</span><span class="sxs-lookup"><span data-stu-id="1cf4f-309">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="1cf4f-310">ID でイベントを取得する</span><span class="sxs-lookup"><span data-stu-id="1cf4f-310">Get an event by ID</span></span>

- <span data-ttu-id="1cf4f-311">**メソッド**: GET</span><span class="sxs-lookup"><span data-stu-id="1cf4f-311">**Method**: GET</span></span>

- <span data-ttu-id="1cf4f-312">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span><span class="sxs-lookup"><span data-stu-id="1cf4f-312">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span></span>

- <span data-ttu-id="1cf4f-313">**ヘッダー**: キー = Content-Type、値 = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="1cf4f-313">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="1cf4f-314">**認証**: 基本</span><span class="sxs-lookup"><span data-stu-id="1cf4f-314">**Authentication**: Basic</span></span>

- <span data-ttu-id="1cf4f-315">**ユーザー名**: 「Complianceuser」</span><span class="sxs-lookup"><span data-stu-id="1cf4f-315">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="1cf4f-316">**パスワード**: 「Compliancepassword」</span><span class="sxs-lookup"><span data-stu-id="1cf4f-316">**Password**: "Compliancepassword"</span></span>

###### <a name="response-codes"></a><span data-ttu-id="1cf4f-317">応答コード</span><span class="sxs-lookup"><span data-stu-id="1cf4f-317">Response codes</span></span>

| <span data-ttu-id="1cf4f-318">応答コード</span><span class="sxs-lookup"><span data-stu-id="1cf4f-318">Response Code</span></span> | <span data-ttu-id="1cf4f-319">説明</span><span class="sxs-lookup"><span data-stu-id="1cf4f-319">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="1cf4f-320">200</span><span class="sxs-lookup"><span data-stu-id="1cf4f-320">200</span></span>               | <span data-ttu-id="1cf4f-321">問題ありません。応答本体に atom+xml 形式のイベントが含まれています</span><span class="sxs-lookup"><span data-stu-id="1cf4f-321">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="1cf4f-322">404</span><span class="sxs-lookup"><span data-stu-id="1cf4f-322">404</span></span>               | <span data-ttu-id="1cf4f-323">見つかりません</span><span class="sxs-lookup"><span data-stu-id="1cf4f-323">Not found</span></span>                                            |
| <span data-ttu-id="1cf4f-324">302</span><span class="sxs-lookup"><span data-stu-id="1cf4f-324">302</span></span>               | <span data-ttu-id="1cf4f-325">リダイレクト</span><span class="sxs-lookup"><span data-stu-id="1cf4f-325">Redirect</span></span>                                             |
| <span data-ttu-id="1cf4f-326">401</span><span class="sxs-lookup"><span data-stu-id="1cf4f-326">401</span></span>               | <span data-ttu-id="1cf4f-327">承認に失敗しました</span><span class="sxs-lookup"><span data-stu-id="1cf4f-327">Authorization Failed</span></span>                                 |
| <span data-ttu-id="1cf4f-328">403</span><span class="sxs-lookup"><span data-stu-id="1cf4f-328">403</span></span>               | <span data-ttu-id="1cf4f-329">認証に失敗しました</span><span class="sxs-lookup"><span data-stu-id="1cf4f-329">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="1cf4f-330">名前でイベントを取得する</span><span class="sxs-lookup"><span data-stu-id="1cf4f-330">Get an event by name</span></span>

- <span data-ttu-id="1cf4f-331">**メソッド**: GET</span><span class="sxs-lookup"><span data-stu-id="1cf4f-331">**Method**: GET</span></span>

- <span data-ttu-id="1cf4f-332">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="1cf4f-332">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>

- <span data-ttu-id="1cf4f-333">**ヘッダー**: キー = Content-Type、値 = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="1cf4f-333">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="1cf4f-334">**認証**: 基本</span><span class="sxs-lookup"><span data-stu-id="1cf4f-334">**Authentication**: Basic</span></span>

- <span data-ttu-id="1cf4f-335">**ユーザー名**: 「Complianceuser」</span><span class="sxs-lookup"><span data-stu-id="1cf4f-335">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="1cf4f-336">**パスワード**: 「Compliancepassword」</span><span class="sxs-lookup"><span data-stu-id="1cf4f-336">**Password**: "Compliancepassword"</span></span>


###### <a name="response-codes"></a><span data-ttu-id="1cf4f-337">応答コード</span><span class="sxs-lookup"><span data-stu-id="1cf4f-337">Response codes</span></span>

| <span data-ttu-id="1cf4f-338">応答コード</span><span class="sxs-lookup"><span data-stu-id="1cf4f-338">Response Code</span></span> | <span data-ttu-id="1cf4f-339">説明</span><span class="sxs-lookup"><span data-stu-id="1cf4f-339">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="1cf4f-340">200</span><span class="sxs-lookup"><span data-stu-id="1cf4f-340">200</span></span>               | <span data-ttu-id="1cf4f-341">問題ありません。応答本体に atom+xml 形式のイベントが含まれています</span><span class="sxs-lookup"><span data-stu-id="1cf4f-341">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="1cf4f-342">404</span><span class="sxs-lookup"><span data-stu-id="1cf4f-342">404</span></span>               | <span data-ttu-id="1cf4f-343">見つかりません</span><span class="sxs-lookup"><span data-stu-id="1cf4f-343">Not found</span></span>                                            |
| <span data-ttu-id="1cf4f-344">302</span><span class="sxs-lookup"><span data-stu-id="1cf4f-344">302</span></span>               | <span data-ttu-id="1cf4f-345">リダイレクト</span><span class="sxs-lookup"><span data-stu-id="1cf4f-345">Redirect</span></span>                                             |
| <span data-ttu-id="1cf4f-346">401</span><span class="sxs-lookup"><span data-stu-id="1cf4f-346">401</span></span>               | <span data-ttu-id="1cf4f-347">承認に失敗しました</span><span class="sxs-lookup"><span data-stu-id="1cf4f-347">Authorization Failed</span></span>                                 |
| <span data-ttu-id="1cf4f-348">403</span><span class="sxs-lookup"><span data-stu-id="1cf4f-348">403</span></span>               | <span data-ttu-id="1cf4f-349">認証に失敗しました</span><span class="sxs-lookup"><span data-stu-id="1cf4f-349">Authentication Failed</span></span>                                |

### <a name="use-powershell-or-any-http-client-to-create-the-event"></a><span data-ttu-id="1cf4f-350">PowerShell または HTTP クライアントを使用してイベントを作成する</span><span class="sxs-lookup"><span data-stu-id="1cf4f-350">Use PowerShell or any HTTP client to create the event</span></span>

<span data-ttu-id="1cf4f-351">PowerShell はバージョン 6 以降がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-351">PowerShell must be version 6 or later.</span></span>

<span data-ttu-id="1cf4f-352">PowerShell セッションで、次のスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="1cf4f-352">In a PowerShell session, run the following script:</span></span>

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