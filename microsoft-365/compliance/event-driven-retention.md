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
ms.openlocfilehash: f2cf60eac1197ed7be3fd8cbbe69e41a37614f86
ms.sourcegitcommit: 11218af1d792af297b4280ca5975d139d2bbe350
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2020
ms.locfileid: "45048292"
---
# <a name="overview-of-event-driven-retention"></a><span data-ttu-id="4f8e8-103">イベント ベースの保持の概要</span><span class="sxs-lookup"><span data-stu-id="4f8e8-103">Overview of event-driven retention</span></span>

><span data-ttu-id="4f8e8-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="4f8e8-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="4f8e8-105">When you retain content, the retention period is often based on the age of the content.</span><span class="sxs-lookup"><span data-stu-id="4f8e8-105">When you retain content, the retention period is often based on the age of the content.</span></span> <span data-ttu-id="4f8e8-106">For example, you might retain documents for seven years after they're created and then delete them.</span><span class="sxs-lookup"><span data-stu-id="4f8e8-106">For example, you might retain documents for seven years after they're created and then delete them.</span></span> <span data-ttu-id="4f8e8-107">But when you configure [retention labels](labels.md), you can also base a retention period on when a specific type of event occurs.</span><span class="sxs-lookup"><span data-stu-id="4f8e8-107">But when you configure [retention labels](labels.md), you can also base a retention period on when a specific type of event occurs.</span></span> <span data-ttu-id="4f8e8-108">The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.</span><span class="sxs-lookup"><span data-stu-id="4f8e8-108">The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.</span></span>
  
<span data-ttu-id="4f8e8-109">イベントドリブンの保持を使用する場合の例:</span><span class="sxs-lookup"><span data-stu-id="4f8e8-109">Examples for using event-driven retention:</span></span>
  
- <span data-ttu-id="4f8e8-110">**従業員が組織を離れる場合**、従業員が組織を離れてから 10 年間は、その従業員のレコードを保持する必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-110">**Employees leaving the organization** Suppose that employee records must be retained for 10 years from the time an employee leaves the organization.</span></span> <span data-ttu-id="4f8e8-111">10 年が経過した後、その従業員の採用、業績、および退職に関するすべてのドキュメントを廃棄する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-111">After 10 years elapse, all documents related to the hiring, performance, and termination of that employee must be disposed.</span></span> <span data-ttu-id="4f8e8-112">10 年の保持期間をトリガーするイベントは、組織を離れる従業員となります。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-112">The event that triggers the 10-year retention period is the employee leaving the organization.</span></span> 
    
- <span data-ttu-id="4f8e8-113">**契約満了の場合**、契約に関連するすべてのレコードは、契約満了後 5 年間は保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-113">**Contract expiration** Suppose that all records related to contracts must be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="4f8e8-114">5 年間の保持期間をトリガーするイベントは、契約の満了です。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-114">The event that triggers the five-year retention period is the expiration of the contract.</span></span> 
    
- <span data-ttu-id="4f8e8-115">**Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications.</span><span class="sxs-lookup"><span data-stu-id="4f8e8-115">**Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications.</span></span> <span data-ttu-id="4f8e8-116">In this case, the last manufacturing date is the event that triggers the retention period.</span><span class="sxs-lookup"><span data-stu-id="4f8e8-116">In this case, the last manufacturing date is the event that triggers the retention period.</span></span> 
    
<span data-ttu-id="4f8e8-117">Event-driven retention is typically used as part of a records-management process.</span><span class="sxs-lookup"><span data-stu-id="4f8e8-117">Event-driven retention is typically used as part of a records-management process.</span></span> <span data-ttu-id="4f8e8-118">This means that:</span><span class="sxs-lookup"><span data-stu-id="4f8e8-118">This means that:</span></span>
  
- <span data-ttu-id="4f8e8-119">イベントに基づくラベルでは、通常、レコードとしてコンテンツを分類します。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-119">Labels based on events also usually classify content as a record.</span></span> <span data-ttu-id="4f8e8-120">詳細については、「[レコードの詳細](records.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-120">For more information, see [Learn about records](records.md).</span></span>
    
- <span data-ttu-id="4f8e8-121">レコードとして分類されているもののイベント トリガーがまだ発生していない文書は、イベントがそのドキュメントの保存期間をトリガーするまで無期限に保持されます (レコードを完全に削除することはできません)。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-121">A document that's been classified as a record but whose event trigger has not yet happened is retained indefinitely (records can't be permanently deleted), until an event triggers that document's retention period.</span></span>
    
- <span data-ttu-id="4f8e8-122">イベントに基づく保持ラベルは、通常、保持期間の最後に廃棄レビューをトリガーするため、レコード管理者はコンテンツを手動で確認して廃棄できます。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-122">Retention labels based on events usually trigger a disposition review at the end of the retention period, so that a records manager can manually review and dispose of the content.</span></span> <span data-ttu-id="4f8e8-123">詳細については、「[コンテンツの廃棄](disposition.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-123">For more information, see [Disposition of content](disposition.md).</span></span>
    
<span data-ttu-id="4f8e8-124">イベントに基づく保持ラベルには、Microsoft 365 の他の保持ラベルと同じ機能があります。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-124">A retention label based on an event has the same capabilities as any retention label in Microsoft 365.</span></span> <span data-ttu-id="4f8e8-125">詳細については、「[保持ラベルの詳細](labels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-125">For more information, see [Learn about retention labels](labels.md).</span></span>

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a><span data-ttu-id="4f8e8-126">イベントの種類、ラベル、イベント、アセット ID の関係を理解する</span><span class="sxs-lookup"><span data-stu-id="4f8e8-126">Understanding the relationship between event types, labels, events, and asset IDs</span></span>

<span data-ttu-id="4f8e8-127">イベント ベースの保持を活用するには、図と以下の説明に示すように、イベントの種類、保持ラベル、イベント、アセット ID の関係を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-127">To successfully use event-driven retention, it's important to understand the relationship between event types, retention labels, events, and asset IDs as illustrated in the diagrams and the explanation that follows:</span></span> 
  
![イベントの種類、ラベル、イベント、アセット ID の図](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![イベントの種類、ラベル、イベント、アセット ID の図](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. <span data-ttu-id="4f8e8-130">さまざまな種類のコンテンツの保持ラベルを作成してから、イベントの種類に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-130">You create retention labels for different types of content and then associate them with a type of event.</span></span> <span data-ttu-id="4f8e8-131">たとえば、さまざまな種類の製品ファイルとレコードの保持ラベルは、製品を使用しなくなった時点からレコードを 10 年間保持する必要があるため、Product Lifetime という名前のイベントの種類に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-131">For example, retention labels for different types of product files and records are associated with an event type named Product Lifetime because those records must be retained for 10 years from the time the product reaches its end of life.</span></span>
    
2. <span data-ttu-id="4f8e8-132">ユーザー (通常はレコード管理者) はコンテンツにこれらの保持ラベルを適用し、(SharePoint と OneDrive のドキュメントの場合) アイテムごとに資産 ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-132">Users (typically records managers) apply those retention labels to content and (for SharePoint and OneDrive documents) enter an asset ID for each item.</span></span> <span data-ttu-id="4f8e8-133">この例では、資産 ID は組織で使用される製品名またはコードです。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-133">In this example, the asset ID is a product name or code used by the organization.</span></span> <span data-ttu-id="4f8e8-134">したがって、各製品のレコードには保持ラベルが割り当てられ、各レコードには資産 ID を含むプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-134">Thus, each product's records are assigned a retention label, and each record has a property that contains an asset ID.</span></span> <span data-ttu-id="4f8e8-135">この図は組織内のすべての製品レコードの**すべてのコンテンツ**を表しており、各アイテムにはそのレコードに該当する製品の資産 ID が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-135">The diagram represents **all of the content** for all product records in an organization, and each item bears the asset ID of the product whose record it is.</span></span> 
    
3. <span data-ttu-id="4f8e8-136">Product Lifetime is the event type; a specific product reaching end of life is an event.</span><span class="sxs-lookup"><span data-stu-id="4f8e8-136">Product Lifetime is the event type; a specific product reaching end of life is an event.</span></span> <span data-ttu-id="4f8e8-137">When an event of that event type occurs - in this case, when a product reaches its end of life - you create an event that specifies:</span><span class="sxs-lookup"><span data-stu-id="4f8e8-137">When an event of that event type occurs - in this case, when a product reaches its end of life - you create an event that specifies:</span></span>
    
  - <span data-ttu-id="4f8e8-138">(SharePoint および OneDrive のドキュメントの) アセット ID。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-138">An asset ID (for SharePoint and OneDrive documents)</span></span>
    
  - <span data-ttu-id="4f8e8-139">Keywords (for Exchange items).</span><span class="sxs-lookup"><span data-stu-id="4f8e8-139">Keywords (for Exchange items).</span></span> <span data-ttu-id="4f8e8-140">In this example, the organization uses a product code in messages containing product records, so the keyword for Exchange items is the same as the asset ID for SharePoint and OneDrive documents.</span><span class="sxs-lookup"><span data-stu-id="4f8e8-140">In this example, the organization uses a product code in messages containing product records, so the keyword for Exchange items is the same as the asset ID for SharePoint and OneDrive documents.</span></span>
    
  - <span data-ttu-id="4f8e8-141">The date when the event occurred.</span><span class="sxs-lookup"><span data-stu-id="4f8e8-141">The date when the event occurred.</span></span> <span data-ttu-id="4f8e8-142">This date is used as the start of the retention period.</span><span class="sxs-lookup"><span data-stu-id="4f8e8-142">This date is used as the start of the retention period.</span></span> <span data-ttu-id="4f8e8-143">This date can be the current, a past, or a future date.</span><span class="sxs-lookup"><span data-stu-id="4f8e8-143">This date can be the current, a past, or a future date.</span></span>
    
4. <span data-ttu-id="4f8e8-144">イベントの作成後、イベントの日付は、そのイベントの種類の保持ラベルを持ち、指定された資産 ID またはキーワードを含むすべてのコンテンツに同期されます。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-144">After you create an event, that event date is synchronized to all the content that has a retention label of that event type and that contains the specified asset ID or keyword.</span></span> <span data-ttu-id="4f8e8-145">その他の保持ラベルと同様に、この同期には最大で 7 日間かかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-145">Like any retention label, this synchronization can take up to 7 days.</span></span> <span data-ttu-id="4f8e8-146">前の図では、赤で囲まれているアイテムはすべて、このイベントによって保持期間がトリガーされています。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-146">In the previous diagram, all the items circled in red have their retention period triggered by this event.</span></span> <span data-ttu-id="4f8e8-147">言い換えれば、この製品の期限が切れたとき、そのイベントがその製品のレコードの保持期間のトリガーとなります。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-147">In other words, when this product reaches its end of life, that event triggers the retention period for that product's records.</span></span>
    
<span data-ttu-id="4f8e8-148">イベントに資産 ID またはキーワードを指定しない場合、そのイベントの種類のラベルの付いた**すべてのコンテンツ**はイベントによってトリガーされる保持期間を持つことを理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-148">It's important to understand that if you don't specify an asset ID or keywords for an event, **all content** with a label of that event type will have its retention period triggered by the event.</span></span> <span data-ttu-id="4f8e8-149">つまり、前の図の場合であれば、すべてのコンテンツの保持が開始されます。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-149">This means that in the previous diagram, all content would start being retained.</span></span> <span data-ttu-id="4f8e8-150">これは、意図したものとは異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-150">This might not be what you intend.</span></span> 
  
<span data-ttu-id="4f8e8-151">最後に、それぞれの保持ラベルにはそれぞれの保持設定があることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-151">Finally, remember that each retention label has its own retention settings.</span></span> <span data-ttu-id="4f8e8-152">この例では、すべて 10 年間に指定されていますが、それぞれのラベルが異なる保持期間を持つ保持ラベルを、1 つのイベントでトリガーすることができます。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-152">In this example, they all specify 10 years, but it's possible for an event to trigger retention labels where each label has a different retention period.</span></span>
  
## <a name="how-to-set-up-event-driven-retention"></a><span data-ttu-id="4f8e8-153">イベント ドリブンの保持のセットアップ方法</span><span class="sxs-lookup"><span data-stu-id="4f8e8-153">How to set up event-driven retention</span></span>

<span data-ttu-id="4f8e8-154">イベント ドリブンの保持のワークフロー概要:</span><span class="sxs-lookup"><span data-stu-id="4f8e8-154">High-level workflow for event-driven retention:</span></span>
  
![イベント ベースの保持をセットアップするワークフローの図](../media/event-based-retention-process.png)
  
> [!TIP]
> <span data-ttu-id="4f8e8-156">SharePont の管理プロパティを使用して保持ラベルを自動適用し、イベント ドリブンの保持を実装する詳細なシナリオについては、「[保持ラベルを使用して SharePoint ドキュメントのライフサイクルを管理する](auto-apply-retention-labels-scenario.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-156">See [Manage the lifecycle of SharePoint documents with retention labels](auto-apply-retention-labels-scenario.md) for a detailed scenario about using managed properties in SharePoint to auto-apply retention labels and implement event-driven retention.</span></span>

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a><span data-ttu-id="4f8e8-157">手順 1: 保持期間がイベントに基づくラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="4f8e8-157">Step 1: Create a label whose retention period is based on an event</span></span>

<span data-ttu-id="4f8e8-158">保持ラベルを作成して構成するには、[[保持ラベルを作成して構成する](create-retention-labels.md#create-and-configure-retention-labels)] の手順で [保持] をオンにして、イベントに基づいてコンテンツを保持または削除するオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-158">To create and configure your retention label, use the instructions from [Create and configure retention labels](create-retention-labels.md#create-and-configure-retention-labels) and when you turn on retention, choose the option to retain or delete the content based on an event.</span></span> <span data-ttu-id="4f8e8-159">つまり、この設定では、保持設定は手順 5 の [**イベント**] ページでイベントを作成するまで有効になりません。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-159">This setting means that the retention settings won't go into effect until Step 5, when you create an event on the **Events** page.</span></span> 
  
<span data-ttu-id="4f8e8-160">通常、イベントドリブンの保持は、レコードとして分類されているコンテンツに使用されるので、コンテンツをレコードとしてマークするオプションも選択する必要があるかどうかを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-160">Event-driven retention is typically used for content that's classified as a record, so this is a good time to check whether you also need to select the option that marks content as a record.</span></span>
  
<span data-ttu-id="4f8e8-161">イベントドリブンの保持には、次のような保持の設定が必要になります。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-161">Event-driven retention requires retention settings that:</span></span>
  
- <span data-ttu-id="4f8e8-162">コンテンツを保持する。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-162">Retain the content.</span></span>
    
- <span data-ttu-id="4f8e8-163">保存期間の終わりに、コンテンツの自動削除または廃棄レビューのトリガーを行う。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-163">Delete the content automatically or trigger a disposition review at the end of the retention period.</span></span>
    
![ベースにするイベントのラベルのオプション](../media/a4902281-5196-4194-9737-f30231d95861.png)

### <a name="step-2-choose-an-event-type-for-that-label"></a><span data-ttu-id="4f8e8-165">手順 2: そのラベルのイベントの種類を選択する</span><span class="sxs-lookup"><span data-stu-id="4f8e8-165">Step 2: Choose an event type for that label</span></span>

<span data-ttu-id="4f8e8-166">ラベルの設定で、**イベント**に基づいてラベルを設定するオプションを選ぶと、**[イベントの種類の選択]** というオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-166">In the label settings, after you choose the option to base the label on an **event**, you'll see the option to **Choose an event type**.</span></span> <span data-ttu-id="4f8e8-167">イベントの種類とは、ラベルを関連付けるイベントの単なる一般的な説明です。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-167">An event type is simply a general description of an event that you want to associate a label with.</span></span>
  
<span data-ttu-id="4f8e8-168">たとえば、Product Lifetime という名前のイベントの種類を作成する場合は、"製品開発ファイル" や "製品の経営的意思決定" など、ラベルを適用するコンテンツの種類が分かるような名前でイベント ベースの保持ラベルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-168">For example, if you create an event type named Product Lifetime, you'll create event-based retention labels with names that describe what types of content you want the labels to be applied to, such as "Product development files" or "Product business decision records".</span></span>
  
<span data-ttu-id="4f8e8-169">イベントの種類を選択して保持ラベルを保存すると、イベントの種類の変更はできませんので、ご注意ください。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-169">After you choose an event type and save the retention label, the event type cannot be changed.</span></span>
  
![イベントの種類を作成または選択するオプション](../media/8b7afe79-72cb-462e-81d4-b5ddbe899dbc.png)
  
### <a name="step-3-publish-or-auto-apply-the-event-based-retention-labels"></a><span data-ttu-id="4f8e8-171">手順 3: イベント ベースの保持ラベルを発行または自動適用する</span><span class="sxs-lookup"><span data-stu-id="4f8e8-171">Step 3: Publish or auto-apply the event-based retention labels</span></span>

<span data-ttu-id="4f8e8-172">他の保持ラベルと同じように、イベント ベースのラベルを[発行または自動適用](create-retention-labels.md)する必要があります。したがって、このラベルはコンテンツに手動または自動で適用されます。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-172">Just like any retention label, you need to [publish or auto-apply](create-retention-labels.md) an event-based label, so that it's manually or automatically applied to content.</span></span>

> [!NOTE]
> <span data-ttu-id="4f8e8-173">[**レコード管理**] > [**ファイル計画**] タブまたは [**データ ガバナンス**] > [**ラベル**] タブからイベント駆動型の保持ラベルを選択した場合、[**ラベルの自動適用**] ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-173">If you select an event-driven retention label from **Records Management** > **File plan** tab or **Data governance** > **Labels** tab, the **Auto-apply a label** button is not available.</span></span>
> 
> <span data-ttu-id="4f8e8-174">このボタンの代わりに、次のいずれかの場所からのラベルまたはポリシーのリストの上にある [**ラベルを自動適用**] オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-174">Instead of this button, use the **Auto-apply a label** option above the list of labels or policies from one of the following locations:</span></span>
> - <span data-ttu-id="4f8e8-175">[**レコード管理**] > [**ラベル ポリシー**] タブ</span><span class="sxs-lookup"><span data-stu-id="4f8e8-175">**Records management** > **Label policies** tab</span></span>
> - <span data-ttu-id="4f8e8-176">[**データ ガバナンス**] > [**ラベル**] タブまたは [**ラベル ポリシー**] タブ</span><span class="sxs-lookup"><span data-stu-id="4f8e8-176">**Data governance** > **Labels** tab or **Label policies** tab</span></span>


![保持ラベルの発行または自動適用のオプション](..\media\compliance-information-governance-publish-labels.png)

### <a name="step-4-enter-an-asset-id"></a><span data-ttu-id="4f8e8-178">手順 4: アセット ID を入力する</span><span class="sxs-lookup"><span data-stu-id="4f8e8-178">Step 4: Enter an asset ID</span></span>

<span data-ttu-id="4f8e8-179">After an event-driven label is applied to content, you can enter an asset ID for each item.</span><span class="sxs-lookup"><span data-stu-id="4f8e8-179">After an event-driven label is applied to content, you can enter an asset ID for each item.</span></span> <span data-ttu-id="4f8e8-180">For example, your organization might use:</span><span class="sxs-lookup"><span data-stu-id="4f8e8-180">For example, your organization might use:</span></span>
  
- <span data-ttu-id="4f8e8-181">特定の製品のみのコンテンツ保持に使用する製品コード。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-181">Product codes that you can use to retain content for only a specific product.</span></span>
    
- <span data-ttu-id="4f8e8-182">特定の製品のみのコンテンツ保持に使用するプロジェクト コード。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-182">Project codes that you can use to retain content for only a specific project.</span></span>
    
- <span data-ttu-id="4f8e8-183">特定の製品のみのコンテンツ保持に使用する従業員 ID。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-183">Employee IDs that you can use to retain content for only a specific person.</span></span>
    
<span data-ttu-id="4f8e8-184">アセット ID は、SharePoint と OneDrive の別のドキュメント プロパティです。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-184">Asset ID is simply another document property in SharePoint and OneDrive.</span></span> <span data-ttu-id="4f8e8-185">組織では既に別のドキュメント プロパティや ID を使用してコンテンツを分類している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-185">Your organization might already use other document properties and IDs to classify content.</span></span> <span data-ttu-id="4f8e8-186">その場合は、イベントの作成時にそれらのプロパティと値を使用することもできます (後述する手順 6 を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-186">If so, you can also use those properties and values when you create an event - see step 6 that follows.</span></span> <span data-ttu-id="4f8e8-187">重要な点は、組織はドキュメント プロパティで property:value の組み合わせを使用して、そのアイテムをイベントの種類に関連付ける必要があるということです。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-187">The important point is that your organization must use some property:value combination in the document properties to associate that item with an event type.</span></span>
  
![アセット ID を入力するテキスト ボックス](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a><span data-ttu-id="4f8e8-189">手順 5: イベントを作成する</span><span class="sxs-lookup"><span data-stu-id="4f8e8-189">Step 5: Create an event</span></span>

<span data-ttu-id="4f8e8-190">製品の使用を終えるなど、イベントの種類に関する特定のインスタンスが発生するときは、Microsoft 365 コンプライアンス センターで **[レコード管理]** > **[イベント]** ページの順に移動し、イベントを作成します。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-190">When a particular instance of that event type occurs, such as a product reaches its end of life, go to the **Records management** > **Events** page in the Microsoft 365 compliance center and create an event.</span></span> <span data-ttu-id="4f8e8-191">イベントを作成し、それを手動でトリガーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-191">You need to manually trigger an event by creating it.</span></span>
  
### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a><span data-ttu-id="4f8e8-192">手順 6: 手順 2 でのラベルを使用したイベントの種類と同じものを選択する</span><span class="sxs-lookup"><span data-stu-id="4f8e8-192">Step 6: Choose the same event type used by the label in step 2</span></span>

<span data-ttu-id="4f8e8-193">イベントを作成するときには、手順 2 の保持ラベルで使用したものと同じイベントの種類 (Product Lifetime など) を選択します。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-193">When you create the event, choose the same event type used by the retention label in step 2 - for example, Product Lifetime.</span></span> <span data-ttu-id="4f8e8-194">そのイベントの種類が選択されたイベントに適用されている保持ラベルの付いたコンテンツのみが、トリガーされる保持期間を持ちます。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-194">Only content with retention labels applied to it of that event type will have its retention period triggered.</span></span>
  
![イベントの種類を選択するイベント設定のオプション](../media/11663591-5628-419e-9537-61eb8f5c741f.png)
  
### <a name="step-7-enter-keywords-or-an-asset-id"></a><span data-ttu-id="4f8e8-196">手順 7: キーワードまたはアセット ID を入力する</span><span class="sxs-lookup"><span data-stu-id="4f8e8-196">Step 7: Enter keywords or an asset ID</span></span>

<span data-ttu-id="4f8e8-197">Now you narrow the scope of the content by specifying asset IDs for SharePoint and OneDrive content or keywords for Exchange content.</span><span class="sxs-lookup"><span data-stu-id="4f8e8-197">Now you narrow the scope of the content by specifying asset IDs for SharePoint and OneDrive content or keywords for Exchange content.</span></span> <span data-ttu-id="4f8e8-198">For asset IDs, retention will be enforced only on content with the specified property:value pair.</span><span class="sxs-lookup"><span data-stu-id="4f8e8-198">For asset IDs, retention will be enforced only on content with the specified property:value pair.</span></span> <span data-ttu-id="4f8e8-199">If an asset ID is not entered, **all content** with labels of that event type get the same retention date applied to them.</span><span class="sxs-lookup"><span data-stu-id="4f8e8-199">If an asset ID is not entered, **all content** with labels of that event type get the same retention date applied to them.</span></span> 
  
<span data-ttu-id="4f8e8-200">アセット ID は、SharePoint と OneDrive の別のドキュメント プロパティです。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-200">Asset ID is simply another document property in SharePoint and OneDrive.</span></span> <span data-ttu-id="4f8e8-201">アセット ID プロパティを使用する場合は、下に示されるアセット ID のボックスに 「`ComplianceAssetID:<value>`」 と入力します。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-201">If you're using the Asset ID property, you would enter `ComplianceAssetID:<value>` in the box for asset IDs shown below.</span></span>
  
<span data-ttu-id="4f8e8-202">組織は、このイベントの種類に関するドキュメントに他のプロパティと ID を適用している場合があります。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-202">Your organization might have applied other properties and IDs to the documents related to this event type.</span></span> <span data-ttu-id="4f8e8-203">たとえば、特定の製品のレコードを検出する必要がある場合、ID はカスタム プロパティ製品 ID とその値 "XYZ" の組み合わせである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-203">For example, if you need to detect a specific product's records, the ID might be a combination of your custom property ProductID and the value "XYZ".</span></span> <span data-ttu-id="4f8e8-204">この場合は、下に示されるアセット ID のボックスに 「`ProductID:XYZ`」 と入力します。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-204">In this case, you'd enter `ProductID:XYZ` in the box for asset IDs shown below.</span></span>
  
<span data-ttu-id="4f8e8-205">For Exchange items, you can include keywords.</span><span class="sxs-lookup"><span data-stu-id="4f8e8-205">For Exchange items, you can include keywords.</span></span> <span data-ttu-id="4f8e8-206">You can refine your query by using search operators like AND, OR, and NOT.</span><span class="sxs-lookup"><span data-stu-id="4f8e8-206">You can refine your query by using search operators like AND, OR, and NOT.</span></span> <span data-ttu-id="4f8e8-207">For more information on operators, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="4f8e8-207">For more information on operators, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="4f8e8-208">最後に、イベントが発生した日付を選択します。この日付が、保持期間の開始日として使用されます。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-208">Finally, choose the date when the event occurred; this date is used as the start of the retention period.</span></span> <span data-ttu-id="4f8e8-209">イベントの作成後、そのイベントの日付は、そのイベントの種類の保持ラベル、資産 ID、キーワードを持つすべてのコンテンツに同期されます。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-209">After you create an event, that event date is synchronized to all the content with a retention label of that event type, asset ID, and keywords.</span></span> <span data-ttu-id="4f8e8-210">その他の保持ラベルと同様に、この同期には最大で 7 日間かかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-210">Like any retention label, this synchronization can take up to seven days.</span></span>
  
![[イベントの設定] ページ](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)

> [!NOTE]
> <span data-ttu-id="4f8e8-212">イベントを作成すると、既にラベル付けされてインデックスが作成されているコンテンツの保持設定が有効になります。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-212">After creating an event, the retention settings take effect for the content that's already labeled and indexed.</span></span> <span data-ttu-id="4f8e8-213">イベントが作成された後に保持ラベルが新しいコンテンツに追加された場合は、同じ詳細を使用して新しいイベントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-213">If the retention label is added to new content after the event is created, you must create a new event with the same details.</span></span>

<span data-ttu-id="4f8e8-214">イベントを削除しても、既にラベル付けされているコンテンツに対して現在有効になっている保持設定は取り消されません。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-214">Deleting an event doesn't cancel the retention settings that are now in effect for the content that's already labeled.</span></span> <span data-ttu-id="4f8e8-215">それを行うには、同じ詳細を使用して新しいイベントを作成しますが、日付は空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-215">To do that, create a new event with the same details, but leave the date blank.</span></span> 

## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a><span data-ttu-id="4f8e8-216">コンテンツ検索を使用して、特定のラベルまたはアセット ID が適用されたすべてのコンテンツを検索する</span><span class="sxs-lookup"><span data-stu-id="4f8e8-216">Use Content Search to find all content with a specific label or asset ID</span></span>

<span data-ttu-id="4f8e8-217">保持ラベルをコンテンツに割り当てた後は、特定の保持ラベルで分類されている、または特定のアセット ID を含むすべてのコンテンツをコンテンツ検索を使用して検索することができます。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-217">After retention labels are assigned to content, you can use content search to find all content that's classified with a specific retention label or that contains a specific asset ID:</span></span>
  
- <span data-ttu-id="4f8e8-218">特定の保持ラベルを持つすべてのコンテンツを検索するには、**[コンプライアンス ラベル]** の条件を選択した後、完全なラベル名を入力するか、ラベル名の一部を入力してワイルドカードを使用します。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-218">To find all content with a specific retention label, choose the **Compliance label** condition, and then enter the complete label name or part of the label name and use a wildcard.</span></span> 
    
- <span data-ttu-id="4f8e8-219">特定のアセット ID を持つすべてのコンテンツを検索するには、**ComplianceAssetID** プロパティと `ComplianceAssetID:<value>` のフォーマットを使用した値を入力します。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-219">To find all content with a specific asset ID, enter the **ComplianceAssetID** property and a value, using the format `ComplianceAssetID:<value>`.</span></span> 
    
<span data-ttu-id="4f8e8-220">詳細については、「[コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-220">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="permissions"></a><span data-ttu-id="4f8e8-221">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="4f8e8-221">Permissions</span></span>

<span data-ttu-id="4f8e8-222">To get access to the **Events** page, reviewers must be members of a role group with the **Disposition Management** role and the **View-Only Audit Logs** role.</span><span class="sxs-lookup"><span data-stu-id="4f8e8-222">To get access to the **Events** page, reviewers must be members of a role group with the **Disposition Management** role and the **View-Only Audit Logs** role.</span></span> <span data-ttu-id="4f8e8-223">We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group.</span><span class="sxs-lookup"><span data-stu-id="4f8e8-223">We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group.</span></span> 
  
<span data-ttu-id="4f8e8-224">詳細については、「[ユーザーに Office 365 セキュリティ&amp;コンプライアンス センターへのアクセス権を付与する](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-224">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
## <a name="automate-events-by-using-powershell"></a><span data-ttu-id="4f8e8-225">PowerShell を使用してイベントを自動化する</span><span class="sxs-lookup"><span data-stu-id="4f8e8-225">Automate events by using PowerShell</span></span>

<span data-ttu-id="4f8e8-226">Microsoft 365 コンプライアンス センターでは、イベントを手動で作成することができますが、イベントが発生した場合、自動的にトリガーすることをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-226">The Microsoft 365 compliance center lets you create events manually and doesn't support automatically triggering an event when it occurs.</span></span> <span data-ttu-id="4f8e8-227">ただし、Rest API を使用してイベントを自動的にトリガーすることはできます。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-227">However, you can use a Rest API to trigger events automatically.</span></span> <span data-ttu-id="4f8e8-228">詳細については、「[イベント ベースの保持を自動化する](automate-event-driven-retention.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-228">For more information, see [Automate event-based retention](automate-event-driven-retention.md).</span></span>

<span data-ttu-id="4f8e8-229">PowerShellスクリプトを使用して、業務用アプリケーションからのイベント ベースの保持を自動化することもできます。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-229">You can also use a PowerShell script to automate event-based retention from your business applications.</span></span> <span data-ttu-id="4f8e8-230">イベント ドリブンの保持で利用可能な PowerShell コマンドレットは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4f8e8-230">The PowerShell cmdlets available for event-driven retention:</span></span>
  
- [<span data-ttu-id="4f8e8-231">Get-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="4f8e8-231">Get-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873002)
    
- [<span data-ttu-id="4f8e8-232">New-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="4f8e8-232">New-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873004)
    
- [<span data-ttu-id="4f8e8-233">Remove-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="4f8e8-233">Remove-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873005)
    
- [<span data-ttu-id="4f8e8-234">Set-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="4f8e8-234">Set-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873006)
    
- [<span data-ttu-id="4f8e8-235">Get-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="4f8e8-235">Get-ComplianceRetentionEvent</span></span>](https://go.microsoft.com/fwlink/?linkid=873001)
    
- [<span data-ttu-id="4f8e8-236">New-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="4f8e8-236">New-ComplianceRetentionEvent</span></span>](https://go.microsoft.com/fwlink/?linkid=873003)
    

