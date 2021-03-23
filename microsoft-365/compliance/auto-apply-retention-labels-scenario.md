---
title: 保持ラベルを使用して、SharePoint に保存されているドキュメントのライフサイクルを管理する
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: メタデータを使用してコンテンツを分類し、ラベルを自動的に適用し、イベントベースの保持を使用して保持期間を開始することにより、保持ラベルを使用して SharePoint のドキュメントのライフサイクルを管理する方法。
ms.openlocfilehash: 6c58658378fd0def9a56783e7b8b35db3323b135
ms.sourcegitcommit: 8998f70d3f7bd673f93f8d1cf12ce981b1b771c3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51034216"
---
# <a name="use-retention-labels-to-manage-the-lifecycle-of-documents-stored-in-sharepoint"></a><span data-ttu-id="1a134-103">保持ラベルを使用して、SharePoint に保存されているドキュメントのライフサイクルを管理する</span><span class="sxs-lookup"><span data-stu-id="1a134-103">Use retention labels to manage the lifecycle of documents stored in SharePoint</span></span>

><span data-ttu-id="1a134-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="1a134-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="1a134-105">この記事では、自動的に適用される保持ラベルとイベントベースの保持を使用して、SharePoint に保存されているドキュメントのライフサイクルを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1a134-105">This article describes how you can manage the lifecycle of documents that are stored in SharePoint by using automatically applied retention labels and event-based retention.</span></span>

<span data-ttu-id="1a134-106">自動適用機能は、ドキュメントを分類するために SharePoint メタデータを使用します。</span><span class="sxs-lookup"><span data-stu-id="1a134-106">The auto-apply functionality uses SharePoint metadata for document classification.</span></span> <span data-ttu-id="1a134-107">この記事は製品関連ドキュメント向けですが、他のシナリオにも同じ概念を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1a134-107">The example in this article is for product-related documents, but the same concepts can be used for other scenarios.</span></span> <span data-ttu-id="1a134-108">たとえば、石油およびガス産業では、石油基地、坑井検層、生産ライセンスなどの物理的資産に関するドキュメントのライフサイクルを管理できます。</span><span class="sxs-lookup"><span data-stu-id="1a134-108">For example, in the oil and gas industry, you could use it to manage the lifecycle of documents about physical assets such as oil platforms, well logs, or production licenses.</span></span> <span data-ttu-id="1a134-109">金融サービス業界では、銀行口座、住宅ローン、または保険契約に関するドキュメントを管理できます。</span><span class="sxs-lookup"><span data-stu-id="1a134-109">In the financial services industry, you could manage bank account, mortgage, or insurance contract documents.</span></span> <span data-ttu-id="1a134-110">公的機関では、建設許可または税務フォームに関する文書を管理できます。</span><span class="sxs-lookup"><span data-stu-id="1a134-110">In the public sector, you could manage construction permits or tax forms.</span></span>

<span data-ttu-id="1a134-111">この記事では、情報アーキテクチャと保持ラベルの定義を見ていきます。</span><span class="sxs-lookup"><span data-stu-id="1a134-111">In this article, we'll look at the information architecture and definition of the retention labels.</span></span> <span data-ttu-id="1a134-112">ラベルを自動適用して、ドキュメントを分類します。</span><span class="sxs-lookup"><span data-stu-id="1a134-112">Then we'll classify documents by auto-applying the labels.</span></span> <span data-ttu-id="1a134-113">最後に、保持期間を開始するイベントが生成されます。</span><span class="sxs-lookup"><span data-stu-id="1a134-113">And finally we'll generate the events that initiate the retention period.</span></span>

## <a name="information-architecture"></a><span data-ttu-id="1a134-114">情報アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="1a134-114">Information architecture</span></span>

<span data-ttu-id="1a134-115">このシナリオは、SharePoint を使用して、会社が開発する製品に関するすべてのドキュメントを保存する製造会社です。</span><span class="sxs-lookup"><span data-stu-id="1a134-115">Our scenario is a manufacturing company that uses SharePoint to store all the documents about the products that the company develops.</span></span> <span data-ttu-id="1a134-116">これらのドキュメントには、製品の仕様、仕入先との契約、およびユーザー マニュアルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1a134-116">These documents include product specifications, agreements with suppliers, and user manuals.</span></span> <span data-ttu-id="1a134-117">これらのドキュメントがエンタープライズ コンテンツ管理ポリシーを通して SharePoint に保存されている場合、ドキュメント メタデータが定義され、分類に使用されます。</span><span class="sxs-lookup"><span data-stu-id="1a134-117">When these documents are stored in SharePoint through Enterprise Content Management policies, document metadata is defined, which is used to classify them.</span></span> <span data-ttu-id="1a134-118">各ドキュメントには、次のメタデータ プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="1a134-118">Each document has the following metadata properties:</span></span>

- <span data-ttu-id="1a134-119">**ドキュメントの種類** (製品の仕様、契約、ユーザー マニュアルなど)</span><span class="sxs-lookup"><span data-stu-id="1a134-119">**Doc Type** (such as product specification, agreement, or user manual)</span></span>

- <span data-ttu-id="1a134-120">**製品名**</span><span class="sxs-lookup"><span data-stu-id="1a134-120">**Product Name**</span></span>

- <span data-ttu-id="1a134-121">**状態** (下書きまたは最終版)</span><span class="sxs-lookup"><span data-stu-id="1a134-121">**Status** (draft or final)</span></span>

<span data-ttu-id="1a134-122">このメタデータは、すべてのドキュメントの *生産ドキュメント* と呼ばれる基本コンテンツの種類を形成します。</span><span class="sxs-lookup"><span data-stu-id="1a134-122">This metadata forms a base content type called *Production Document* for all the documents.</span></span>

![製品ドキュメントのメタデータの表](../media/SPRetention1.png)

> [!NOTE]
> <span data-ttu-id="1a134-124">**ドキュメントの種類** および **状態** プロパティは、後述のシナリオで保持ポリシーによって使用され、保持ラベルを分類して自動適用します。</span><span class="sxs-lookup"><span data-stu-id="1a134-124">The **Doc Type** and **Status** properties are used by retention policies later in this scenario to classify and auto-apply retention labels.</span></span>

<span data-ttu-id="1a134-125">さまざまな種類のドキュメントを表すコンテンツの種類が複数ありますが、製品ドキュメントに重点を置きましょう。</span><span class="sxs-lookup"><span data-stu-id="1a134-125">We might have several content types that represent different types of documents, but let's focus on the product documentation.</span></span>

<span data-ttu-id="1a134-126">このシナリオでは、Managed Metadata Service と用語ストアを使用して、*ドキュメントの種類* の用語セットと *製品名* の用語セットを作成します。</span><span class="sxs-lookup"><span data-stu-id="1a134-126">In this scenario, we use the Managed Metadata service and the Term Store to create a term set for *Doc Type* and another one for *Product Name*.</span></span> <span data-ttu-id="1a134-127">用語セットごとに、値ごとに用語を作成します。</span><span class="sxs-lookup"><span data-stu-id="1a134-127">For each term set, we create a term for each value.</span></span> <span data-ttu-id="1a134-128">SharePoint 組織の用語ストアでは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="1a134-128">It would look like something like this in Term Store for your SharePoint organization:</span></span>

![用語ストアの製品ドキュメントの用語セット例](../media/SPRetention2.png)

<span data-ttu-id="1a134-130">*コンテンツの種類* は、[コンテンツ タイプ ハブ](https://support.office.com/article/manage-content-type-publishing-06f39ac0-5576-4b68-abbc-82b68334889b) を使用して作成および公開できます。</span><span class="sxs-lookup"><span data-stu-id="1a134-130">*Content Type* can be created and published by using the [Content Type Hub](https://support.office.com/article/manage-content-type-publishing-06f39ac0-5576-4b68-abbc-82b68334889b).</span></span> <span data-ttu-id="1a134-131">コンテンツの種類は、[PnP プロビジョニング フレームワーク](/sharepoint/dev/solution-guidance/pnp-provisioning-framework) や [サイト デザイン JSON スキーマ](/sharepoint/dev/declarative-customization/site-design-json-schema#define-a-new-content-type) などのサイト プロビジョニング ツールを使用して作成および公開することもできます。</span><span class="sxs-lookup"><span data-stu-id="1a134-131">You can also create and publish a content type by using site provisioning tools, such as the [PnP provisioning framework](/sharepoint/dev/solution-guidance/pnp-provisioning-framework) or [site design JSON schema](/sharepoint/dev/declarative-customization/site-design-json-schema#define-a-new-content-type).</span></span>

<span data-ttu-id="1a134-132">各製品には、1 つのドキュメント ライブラリを含む専用の SharePoint サイトがあり、適切なコンテンツの種類が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="1a134-132">Each product has a dedicated SharePoint site that contains one document library that has the right content types enabled.</span></span> <span data-ttu-id="1a134-133">すべてのドキュメントはこのドキュメント ライブラリに保存されます。</span><span class="sxs-lookup"><span data-stu-id="1a134-133">All documents are stored in this document library.</span></span>

<span data-ttu-id="1a134-134">[![製品ドキュメントのドキュメント ライブラリ](../media/SPRetention3.png)](../media/SPRetention3.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="1a134-134">[ ![Document library for product documentation](../media/SPRetention3.png) ](../media/SPRetention3.png#lightbox)</span></span>

> [!NOTE]
> <span data-ttu-id="1a134-135">このシナリオの製造会社では、製品ごとに SharePoint サイトを用意する代わりに、製品ごとに Microsoft Teams を使用して、永続チャットなどのチーム メンバーとの共同作業をサポートし、Teams の [**ファイル**] タブを使用してドキュメントを管理できます。</span><span class="sxs-lookup"><span data-stu-id="1a134-135">Instead of having a SharePoint site per product, the manufacturing company in this scenario could use a Microsoft Team per product to support collaboration among members of the team, such as through persistent chat, and use the **Files** tab in Teams for document management.</span></span> <span data-ttu-id="1a134-136">この記事ではドキュメントのみに重点を置いているため、サイトのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="1a134-136">In this article we only focus on documents, so, we'll only use a site.</span></span>

<span data-ttu-id="1a134-137">回転ウィジェット製品のドキュメント ライブラリのビューを次に示します。</span><span class="sxs-lookup"><span data-stu-id="1a134-137">Here's a view of the document library for the Spinning Widget product:</span></span>

<span data-ttu-id="1a134-138">[![回転ウィジェットのドキュメント ライブラリ](../media/SPRetention4.png)](../media/SPRetention4.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="1a134-138">[ ![Spinning Widget document library](../media/SPRetention4.png) ](../media/SPRetention4.png#lightbox)</span></span>

<span data-ttu-id="1a134-139">ドキュメント管理用に基本的な情報アーキテクチャが用意されているので、ドキュメントのメタデータと分類を使用するドキュメントの保持および廃棄戦略を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="1a134-139">Now that we have the basic information architecture in place for document management, let's look at the retention and disposal strategy for the documents that use the metadata and how we classify those documents.</span></span>

## <a name="retention-and-disposition"></a><span data-ttu-id="1a134-140">保持および廃棄</span><span class="sxs-lookup"><span data-stu-id="1a134-140">Retention and disposition</span></span>

<span data-ttu-id="1a134-141">製造会社のコンプライアンスおよびデータ ガバナンスのポリシーは、データの保持および廃棄方法を規定しています。</span><span class="sxs-lookup"><span data-stu-id="1a134-141">The manufacturing company's compliance and data governance policies dictate how data is preserved and disposed of.</span></span> <span data-ttu-id="1a134-142">製品に関連するドキュメントは、製品を製造する期間、および一定の追加期間保管する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a134-142">Product-related documents must be kept for as long as the product is manufactured and for a certain additional period.</span></span> <span data-ttu-id="1a134-143">この追加期間は、製品の仕様、契約、およびユーザー マニュアルによって異なります。</span><span class="sxs-lookup"><span data-stu-id="1a134-143">The additional period differs for product specifications, agreements, and user manuals.</span></span> <span data-ttu-id="1a134-144">次の表は、保持と廃棄の要件を示しています。</span><span class="sxs-lookup"><span data-stu-id="1a134-144">The following table indicates the retention and disposition requirements:</span></span>

|   <span data-ttu-id="1a134-145">ドキュメントの種類</span><span class="sxs-lookup"><span data-stu-id="1a134-145">Document type</span></span>            |   <span data-ttu-id="1a134-146">保持</span><span class="sxs-lookup"><span data-stu-id="1a134-146">Retention</span></span>                            |   <span data-ttu-id="1a134-147">廃棄</span><span class="sxs-lookup"><span data-stu-id="1a134-147">Disposition</span></span>                                |
| -------------------------- | -------------------------------------- | -------------------------------------------- |
| <span data-ttu-id="1a134-148">製品の仕様</span><span class="sxs-lookup"><span data-stu-id="1a134-148">Product specifications</span></span>      | <span data-ttu-id="1a134-149">生産中止後 5 年</span><span class="sxs-lookup"><span data-stu-id="1a134-149">5 years after production stops</span></span>  | <span data-ttu-id="1a134-150">削除</span><span class="sxs-lookup"><span data-stu-id="1a134-150">Delete</span></span>                                       |
| <span data-ttu-id="1a134-151">製品契約</span><span class="sxs-lookup"><span data-stu-id="1a134-151">Product agreements</span></span>          | <span data-ttu-id="1a134-152">生産中止後 10 年</span><span class="sxs-lookup"><span data-stu-id="1a134-152">10 years after production stops</span></span> | <span data-ttu-id="1a134-153">レビュー</span><span class="sxs-lookup"><span data-stu-id="1a134-153">Review</span></span>                                       |
| <span data-ttu-id="1a134-154">ユーザー マニュアル</span><span class="sxs-lookup"><span data-stu-id="1a134-154">User manuals</span></span>                | <span data-ttu-id="1a134-155">生産中止後 5 年</span><span class="sxs-lookup"><span data-stu-id="1a134-155">5 years after production stops</span></span>  | <span data-ttu-id="1a134-156">削除</span><span class="sxs-lookup"><span data-stu-id="1a134-156">Delete</span></span>                                       |
| <span data-ttu-id="1a134-157">他のすべての種類のドキュメント</span><span class="sxs-lookup"><span data-stu-id="1a134-157">All other types of documents</span></span> | <span data-ttu-id="1a134-158">積極的に保持しない</span><span class="sxs-lookup"><span data-stu-id="1a134-158">Don't actively retain</span></span>  | <span data-ttu-id="1a134-159">ドキュメントが 3 年以上経過したときに削除する</span><span class="sxs-lookup"><span data-stu-id="1a134-159">Delete when document is older than 3 years</span></span> <br /><br /> <span data-ttu-id="1a134-160">過去 3 年以内に変更されていないドキュメントは、3 年以上前のものと見なされます。</span><span class="sxs-lookup"><span data-stu-id="1a134-160">A document is considered older than 3 years if it hasn't been modified within the last 3 years.</span></span> |
|||

<span data-ttu-id="1a134-161">Microsoft 365 コンプライアンス センターを使用して、次の [保持ラベル](retention.md#retention-labels) を作成します。</span><span class="sxs-lookup"><span data-stu-id="1a134-161">We use the Microsoft 365 compliance center to create the following [retention labels](retention.md#retention-labels):</span></span>

  - <span data-ttu-id="1a134-162">製品の仕様</span><span class="sxs-lookup"><span data-stu-id="1a134-162">Product Specification</span></span>

  - <span data-ttu-id="1a134-163">製品の契約</span><span class="sxs-lookup"><span data-stu-id="1a134-163">Product Agreement</span></span>

  - <span data-ttu-id="1a134-164">ユーザー マニュアル</span><span class="sxs-lookup"><span data-stu-id="1a134-164">User Manual</span></span>

<span data-ttu-id="1a134-165">この記事では、製品の仕様の保持ラベルを作成して自動適用する方法のみを示します。</span><span class="sxs-lookup"><span data-stu-id="1a134-165">In this article, we only show how to create and auto-apply the Product Specification retention label.</span></span> <span data-ttu-id="1a134-166">完全なシナリオを実装するには、他の 2 つのドキュメントの種類の保持ラベルも作成して自動適用します。</span><span class="sxs-lookup"><span data-stu-id="1a134-166">To implement the complete scenario, you would also create and auto-apply retention labels for the other two document types.</span></span>

### <a name="settings-for-the-product-specification-retention-label"></a><span data-ttu-id="1a134-167">製品の仕様の保持ラベルの設定</span><span class="sxs-lookup"><span data-stu-id="1a134-167">Settings for the Product Specification retention label</span></span>

<span data-ttu-id="1a134-168">製品の仕様の保持ラベルの[ファイル計画](file-plan-manager.md)は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1a134-168">Here's the [file plan](file-plan-manager.md) for the Product Specification retention label:</span></span>

- <span data-ttu-id="1a134-169">**名前:** 製品の仕様</span><span class="sxs-lookup"><span data-stu-id="1a134-169">**Name:** Product Specification</span></span>

- <span data-ttu-id="1a134-170">**ユーザー向けの説明:** 生産中止後 5 年間保持します。</span><span class="sxs-lookup"><span data-stu-id="1a134-170">**Description for users:** Retain for 5 years after production stops.</span></span>

- <span data-ttu-id="1a134-171">**管理者向けの説明:** 生産中止後 5 年間保持、自動削除、イベント ベースの保持、イベントの種類は *製品の中止* です。</span><span class="sxs-lookup"><span data-stu-id="1a134-171">**Description for admins:** Retain for 5 years after production stops, auto delete, event-based retention, event type is *Product Cessation*.</span></span>

- <span data-ttu-id="1a134-172">**保持処理:** 保持して削除します。</span><span class="sxs-lookup"><span data-stu-id="1a134-172">**Retention action:** Retain and delete.</span></span>

- <span data-ttu-id="1a134-173">**保持期間:** 5 年 (1825 日) です。</span><span class="sxs-lookup"><span data-stu-id="1a134-173">**Retention duration:** 5 years (1,825 days).</span></span>

- <span data-ttu-id="1a134-174">**レコード ラベル**: アイテムを [レコード](records-management.md#records)としてマークするように保持ラベルを設定します。つまり、ラベル付けされたドキュメントをユーザーが変更または削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="1a134-174">**Record label**: Configure the retention label to mark items as a [record](records-management.md#records), which means the labeled documents can't then be modified or deleted by users.</span></span>

- <span data-ttu-id="1a134-175">**ファイル計画記述子:** シナリオを簡素化するため、オプションのファイル記述子は提供されません。</span><span class="sxs-lookup"><span data-stu-id="1a134-175">**File plan descriptors:** For simplifying the scenario, no optional file descriptors are provided.</span></span>

<span data-ttu-id="1a134-176">次のスクリーンショットは、Microsoft 365 コンプライアンス センターで製品の仕様の保持ラベルを作成するときの設定を示しています。</span><span class="sxs-lookup"><span data-stu-id="1a134-176">The following screenshot shows the settings when you create the Product Specification retention label in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="1a134-177">保持ラベルを作成するときに、*製品の中止* のイベントの種類を作成できます。</span><span class="sxs-lookup"><span data-stu-id="1a134-177">You can create the *Product Cessation* event type when you create the retention label.</span></span> <span data-ttu-id="1a134-178">次のセクションの手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a134-178">See the procedure in the following section.</span></span>

![製品の仕様ラベル向けの保持設定](../media/SPRetention5.png)

> [!NOTE]
> <span data-ttu-id="1a134-180">テスト環境でこのシナリオを再作成する場合、5 年経ってからドキュメントを削除することを防ぐには、保持期間を ***1 日*** に設定します。</span><span class="sxs-lookup"><span data-stu-id="1a134-180">To avoid a 5-year wait for document deletion, set the retention duration to ***1 day*** if you're recreating this scenario in a test environment.</span></span>

### <a name="create-an-event-type-when-you-create-a-retention-label"></a><span data-ttu-id="1a134-181">保持ラベルを作成するときにイベント種類を作成する</span><span class="sxs-lookup"><span data-stu-id="1a134-181">Create an event type when you create a retention label</span></span>

1. <span data-ttu-id="1a134-182">保持ラベルの作成]ウィザードの [**保持設定の定義**] ページで、**次の基準に基づいて保持期間を開始** した後、[**新しいイベントの種類を作成する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a134-182">On the **Define retention settings** page of the Create retention label wizard, after **Start the retention period based on**, select **Create new event type**:</span></span>
    
    ![[製品仕様書ラベル] ダイアログボックスの新しいイベントの種類を作成する](../media/SPRetention6.png)

3. <span data-ttu-id="1a134-184">[**イベントの種類に名前を付ける**] ページで、[**製品の停止**] とオプションの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="1a134-184">On the **Name your event type** page, enter **Product Cessation** and an optional description.</span></span> <span data-ttu-id="1a134-185">次に、[**次へ**]、[**送信**]、[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a134-185">Then select **Next**, **Submit**, and **Done**.</span></span>

4. <span data-ttu-id="1a134-186">[**保持設定の定義**] ページに戻り、[**保持期間の開始日**] のドロップダウン ボックスを使用して、作成した [**製品の停止**] のイベントの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a134-186">Back on the **Define retention settings** page, for **Start the retention period based on**, use the dropdown box to select the **Product Cessation** event type that you created.</span></span>
    
    <span data-ttu-id="1a134-187">製品の仕様の保持ラベルの設定は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1a134-187">Here's what the settings look like for the Product Specification retention label:</span></span> 
    
   ![新しい製品仕様ラベルの設定](../media/SPRetention7.png)

6. <span data-ttu-id="1a134-189">[**ラベルの作成**] を選択し、次のページでラベルの公開、ラベルの自動適用、または単にラベルを保存するオプションが表示されたら、[**今すぐラベルを保存する**] を選択し、[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a134-189">Select **Create label**, and on the next page when you see the options to publish the label, auto-apply the label, or just save the label: Select **Just save the label for now**, and then select **Done**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="1a134-190">詳細な手順については、「[保持期間がイベントに基づくラベルを作成する](event-driven-retention.md#step-1-create-a-label-whose-retention-period-is-based-on-an-event)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1a134-190">For more detailed steps, see [Create a label whose retention period is based on an event](event-driven-retention.md#step-1-create-a-label-whose-retention-period-is-based-on-an-event).</span></span>

<span data-ttu-id="1a134-191">次に、製品仕様のコンテンツに保持ラベルを自動で適用する方法を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="1a134-191">Now let's look at how we'll auto-apply the retention label to product-specification content.</span></span>

## <a name="auto-apply-retention-labels-to-documents"></a><span data-ttu-id="1a134-192">保持ラベルをドキュメントに自動適用</span><span class="sxs-lookup"><span data-stu-id="1a134-192">Auto-apply retention labels to documents</span></span>

<span data-ttu-id="1a134-193">キーワード クエリ言語 (KQL) を使用して、作成した保持ラベルを [自動適用](apply-retention-labels-automatically.md) します。</span><span class="sxs-lookup"><span data-stu-id="1a134-193">We're going to use Keyword Query Language (KQL) to [auto-apply](apply-retention-labels-automatically.md) the retention labels that we created.</span></span> <span data-ttu-id="1a134-194">KQL は、検索クエリの構築に使用される言語です。</span><span class="sxs-lookup"><span data-stu-id="1a134-194">KQL is the language that's used to build search queries.</span></span> <span data-ttu-id="1a134-195">KQL では、キーワードまたは管理プロパティを使用して検索できます。</span><span class="sxs-lookup"><span data-stu-id="1a134-195">In KQL, you can search by using keywords or managed properties.</span></span> <span data-ttu-id="1a134-196">詳細については、「[キーワード クエリ言語 (KQL) 構文のリファレンス](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a134-196">For more information, see [Keyword Query Language (KQL) syntax reference](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).</span></span>

<span data-ttu-id="1a134-197">基本的に、大まかに言うと、Microsoft 365 に、「**製品の仕様** の保持ラベルを、**最終版** の **状態** および **製品の仕様** の **ドキュメントの種類** であるすべてのドキュメントに適用する」 ように指示します。</span><span class="sxs-lookup"><span data-stu-id="1a134-197">Basically, we want to tell Microsoft 365 to "apply the **Product Specification** retention label to all documents that have a **Status** of **Final** and a **Doc Type** of **Product Specification**."</span></span> <span data-ttu-id="1a134-198">**状態** および **ドキュメントの種類** は、以前に 「[情報アーキテクチャ](#information-architecture)」 セクションで製品のドキュメント コンテンツの種類に対して定義したサイト列であることを思い出してください。</span><span class="sxs-lookup"><span data-stu-id="1a134-198">Recall that **Status** and **Doc Type** are the site columns that we defined for the Product Documentation content type in the [Information architecture](#information-architecture) section.</span></span> <span data-ttu-id="1a134-199">これを行うには、検索スキーマを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a134-199">To do this, we need to configure the search schema.</span></span>

<span data-ttu-id="1a134-200">SharePoint がコンテンツのインデックスを作成するとき、各サイト列のクロールされたプロパティを自動的に生成します。</span><span class="sxs-lookup"><span data-stu-id="1a134-200">When SharePoint indexes content, it automatically generates crawled properties for each site column.</span></span> <span data-ttu-id="1a134-201">このシナリオでは、**ドキュメントの種類** プロパティと **状態** プロパティに関心があります。</span><span class="sxs-lookup"><span data-stu-id="1a134-201">For this scenario, we're interested in the **Doc Type** and **Status** properties.</span></span> <span data-ttu-id="1a134-202">検索でクロールされたプロパティを作成するには、適切なコンテンツの種類を使用し、サイト列に入力されたライブラリ内のドキュメントが必要です。</span><span class="sxs-lookup"><span data-stu-id="1a134-202">We need documents in the library that are the right content type and have the site columns filled in for search to create the crawled properties.</span></span>

<span data-ttu-id="1a134-203">SharePoint 管理センターで検索構成を開き、[**検索スキーマの管理**] を選択して、クロールされたプロパティを表示および構成できます。</span><span class="sxs-lookup"><span data-stu-id="1a134-203">In the SharePoint admin center, open the Search configuration, and select **Manage Search Schema** to view and configure the crawled properties.</span></span>

![検索スキーマのクロールされたプロパティ](../media/SPRetention8.png)

<span data-ttu-id="1a134-205">[_ \*クロールされたプロパティ\*\*] ボックスに \***状態** _ を入力し、緑色の矢印を選択すると、次のような結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a134-205">If we type ***status** _ in the _ *Crawled properties** box and select the green arrow, we should see a result like this:</span></span>

![ows_Status のクロールされたプロパティ](../media/SPRetention9.png)

<span data-ttu-id="1a134-207">**ows\_\_Status** プロパティ (二重アンダースコアに注意) は、興味を引かれるものです。</span><span class="sxs-lookup"><span data-stu-id="1a134-207">The **ows\_\_Status** property (notice the double underscore) is the one that interests us.</span></span> <span data-ttu-id="1a134-208">これは、生産ドキュメントのコンテンツの種類の **状態** プロパティにマップします。</span><span class="sxs-lookup"><span data-stu-id="1a134-208">It maps to the **Status** property of the Production Document content type.</span></span>

<span data-ttu-id="1a134-209">***ows\_doc*** と入力して緑色の矢印を選択すると、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a134-209">Now, if we type ***ows\_doc*** and select the green arrow, we should see something like this:</span></span>

![ows_Doc_Type のクロールされたプロパティ](../media/SPRetention10.png)

<span data-ttu-id="1a134-211">**ows\_Doc\_x0020\_Type** プロパティは、興味を引かれる2番目のプロパティです。</span><span class="sxs-lookup"><span data-stu-id="1a134-211">The **ows\_Doc\_x0020\_Type** property is the second property that interests us.</span></span> <span data-ttu-id="1a134-212">これは、生産ドキュメントのコンテンツの種類の **ドキュメントの種類** プロパティにマップします。</span><span class="sxs-lookup"><span data-stu-id="1a134-212">It maps to the **Doc Type** property of the Production Document content type.</span></span>

> [!TIP]
> <span data-ttu-id="1a134-213">このシナリオのクロールされたプロパティの名前を特定するには、生産ドキュメントを含むドキュメント ライブラリに移動します。</span><span class="sxs-lookup"><span data-stu-id="1a134-213">To identify the name of a crawled property for this scenario, go to the document library that contains the production documents.</span></span> <span data-ttu-id="1a134-214">[ライブラリの設定] に移動します。</span><span class="sxs-lookup"><span data-stu-id="1a134-214">Then go to the library settings.</span></span> <span data-ttu-id="1a134-215">[**列**] には、列の名前 (**状態** や **ドキュメントの種類** など) を選択して、サイトの列ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="1a134-215">For **Columns**, select the name of the column (for example, **Status** or **Doc Type**) to open the site column page.</span></span> <span data-ttu-id="1a134-216">そのページの URL の *フィールド* パラメーターには、フィールドの名前が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1a134-216">The *Field* parameter in the URL for that page contains the name of the field.</span></span> <span data-ttu-id="1a134-217">先頭に「ows_」が付いたこのフィールド名は、クロールされたプロパティの名前です。</span><span class="sxs-lookup"><span data-stu-id="1a134-217">This field name, prefixed with "ows_", is the name of the crawled property.</span></span> <span data-ttu-id="1a134-218">たとえば、URL `https://tenantname.sharepoint.com/sites/SpinningWidget/_layouts/15/FldEdit.aspx?List=%7BC38C2F45-3BD6-4C3B-AA3B-EF5DF6B3D172%7D&Field=_Status` は *ows\_\_Status* のクロールされたプロパティに対応します。</span><span class="sxs-lookup"><span data-stu-id="1a134-218">For example, the URL `https://tenantname.sharepoint.com/sites/SpinningWidget/_layouts/15/FldEdit.aspx?List=%7BC38C2F45-3BD6-4C3B-AA3B-EF5DF6B3D172%7D&Field=_Status` corresponds to the *ows\_\_Status* crawled property.</span></span>

<span data-ttu-id="1a134-219">探しているクロールされたプロパティが SharePoint 管理センターの [検索スキーマの管理] セクションに表示されない場合、次のいずれかの理由が考えられます。</span><span class="sxs-lookup"><span data-stu-id="1a134-219">If the crawled properties you're looking for don't appear in the Manage Search Schema section in SharePoint admin center:</span></span>

- <span data-ttu-id="1a134-220">ドキュメントのインデックスが作成されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1a134-220">Maybe the documents haven't been indexed.</span></span> <span data-ttu-id="1a134-221">[**ドキュメント ライブラリ設定**] > [**詳細設定**] の順に移動し、ライブラリのインデックスを強制的に再作成できます。</span><span class="sxs-lookup"><span data-stu-id="1a134-221">You can force a reindex of the library by going to **Document library settings** > **Advanced Settings**.</span></span>

- <span data-ttu-id="1a134-222">ドキュメント ライブラリが最新のサイトにある場合は、SharePoint 管理者もサイト コレクション管理者であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="1a134-222">If the document library is in a modern site, make sure that the SharePoint admin is also a site collection admin.</span></span>

<span data-ttu-id="1a134-223">クロールされ管理されたプロパティの詳細については、「[SharePoint Server で自動的に作成される管理プロパティ](/sharepoint/technical-reference/automatically-created-managed-properties-in-sharepoint)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1a134-223">For more information about crawled and managed properties, see [Automatically created managed properties in SharePoint Server](/sharepoint/technical-reference/automatically-created-managed-properties-in-sharepoint).</span></span>

### <a name="map-crawled-properties-to-pre-defined-managed-properties"></a><span data-ttu-id="1a134-224">クロールされたプロパティを事前定義された管理プロパティにマップする</span><span class="sxs-lookup"><span data-stu-id="1a134-224">Map crawled properties to pre-defined managed properties</span></span>

<span data-ttu-id="1a134-225">KQL は、検索クエリでクロールされたプロパティを使用できません。</span><span class="sxs-lookup"><span data-stu-id="1a134-225">KQL can't use crawled properties in search queries.</span></span> <span data-ttu-id="1a134-226">管理プロパティを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a134-226">It has to use a managed property.</span></span> <span data-ttu-id="1a134-227">通常の検索シナリオでは、管理プロパティを作成し、クロールされた必要なプロパティにマップします。</span><span class="sxs-lookup"><span data-stu-id="1a134-227">In a typical search scenario, we create a managed property and map it to the crawled property that we need.</span></span> <span data-ttu-id="1a134-228">ただし、保持ラベルを自動適用する場合は、KQL で事前定義された管理プロパティのみを指定でき、カスタム管理プロパティは指定できません。</span><span class="sxs-lookup"><span data-stu-id="1a134-228">However, for auto-applying retention labels, you can only specify pre-defined managed properties in KQL, not custom managed properties.</span></span> <span data-ttu-id="1a134-229">使用可能な文字列 *RefinableString00* から *RefinableString199* に対して、システム内で事前に定義された管理プロパティのセットがあります。</span><span class="sxs-lookup"><span data-stu-id="1a134-229">There's a set of predefined managed properties in the system for string *RefinableString00* to *RefinableString199* that you can use.</span></span> <span data-ttu-id="1a134-230">完全なリストについては、「[既定の未使用の管理プロパティ](/sharepoint/manage-search-schema#default-unused-managed-properties)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a134-230">For a complete list, see [Default unused managed properties](/sharepoint/manage-search-schema#default-unused-managed-properties).</span></span> <span data-ttu-id="1a134-231">これらの既定の管理プロパティは、通常、絞り込み検索の条件を定義するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1a134-231">These default managed properties are typically used for defining search refiners.</span></span>

<span data-ttu-id="1a134-232">KQL クエリが機能し、正しい保持ラベルを製品ドキュメント コンテンツに自動適用するために、クロールされたプロパティ **ows\_Doc\_x0020\_Type* および *ows\_\_Status** を 2 つの絞り込み可能な管理プロパティにマップします。</span><span class="sxs-lookup"><span data-stu-id="1a134-232">For the KQL query to automatically apply the correct retention label to product document content, we map the crawled properties **ows\_Doc\_x0020\_Type* and *ows\_\_Status** to two refinable managed properties.</span></span> <span data-ttu-id="1a134-233">このシナリオのテスト環境では、**RefinableString00** と **RefinableString01** は使用されていません。</span><span class="sxs-lookup"><span data-stu-id="1a134-233">In our test environment for this scenario, **RefinableString00** and **RefinableString01** aren't being used.</span></span> <span data-ttu-id="1a134-234">SharePont 管理センターの [**検索スキーマの管理**] で [**管理プロパティ**] を見て、これを決定しました。</span><span class="sxs-lookup"><span data-stu-id="1a134-234">We determined this by looking at **Managed Properties** in **Manage Search Schema** in the SharePoint admin center.</span></span>

<span data-ttu-id="1a134-235">[![検索スキーマの管理プロパティ](../media/SPRetention12.png)](../media/SPRetention12.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="1a134-235">[ ![Managed properties in search schema](../media/SPRetention12.png) ](../media/SPRetention12.png#lightbox)</span></span>

<span data-ttu-id="1a134-236">前のスクリーンショットの [**マップ先のクロールされたプロパティ**] 列は空であることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="1a134-236">Notice that the **Mapped Crawled Properties** column in the previous screenshot is empty.</span></span>

<span data-ttu-id="1a134-237">**ows\_Doc\_x0020\_Type** のクロールされたプロパティをマップするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a134-237">To map the **ows\_Doc\_x0020\_Type** crawled property, follow these steps:</span></span>

1. <span data-ttu-id="1a134-238">[**管理プロパティ**] フィルター ボックスに **_RefinableString00_** と入力し、緑色の矢印を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a134-238">In the **Managed property** filter box, type **_RefinableString00_** and select the green arrow.</span></span>

2. <span data-ttu-id="1a134-239">結果一覧で、**RefinableString00** リンクを選択し、[**クロールされたプロパティへのマッピング**] セクションまで下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="1a134-239">In the results list, select the **RefinableString00** link, and then scroll down to the **Mappings to crawled properties** section.</span></span>  

3. <span data-ttu-id="1a134-240">[**マッピングの追加**] を選択し、\**_ows\_Doc\_x0020\_Type_*_ を [\* クロールされたプロパティの選択\*\*] ウィンドウの [_ **クロールされたプロパティ名の検索**] ボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="1a134-240">Select **Add a Mapping**, and then type **_ows\_Doc\_x0020\_Type_*_ in the _\* Search for a crawled property name*\* box in the **Crawled property selection** window.</span></span> <span data-ttu-id="1a134-241">[**検索**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a134-241">Select **Find**.</span></span>  

4. <span data-ttu-id="1a134-242">結果リストで、**ows\_Doc\_x0020\_Type** を選択し、[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a134-242">In the results list, select **ows\_Doc\_x0020\_Type** and then select **OK**.</span></span>

   <span data-ttu-id="1a134-243">[**マップ先のクロールされたプロパティ**] セクションに、次のスクリーンショットのようなものが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a134-243">In the **Mapped Crawled Properties** section, you should see something similar to this screenshot:</span></span>

   <span data-ttu-id="1a134-244">[![[マップ先のクロールされたプロパティ] セクションで [マッピングの追加] を選択する](../media/SPRetention13.png)](../media/SPRetention13.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="1a134-244">[ ![Select Add a mapping in the Mapped crawled properties section](../media/SPRetention13.png) ](../media/SPRetention13.png#lightbox)</span></span>


5. <span data-ttu-id="1a134-245">ページの一番下までスクロールし、[**OK**] を選択してマッピングを保存します。</span><span class="sxs-lookup"><span data-stu-id="1a134-245">Scroll to the bottom of the page and select **OK** to save the mapping.</span></span>

<span data-ttu-id="1a134-246">この同じ手順を繰り返して、**RefinableString01** と **ows\_\_Status** をマップします。</span><span class="sxs-lookup"><span data-stu-id="1a134-246">Repeat these steps to map **RefinableString01** and **ows\_\_Status**.</span></span>

<span data-ttu-id="1a134-247">これで、2 つのクロールされたプロパティにマップされた 2 つの管理プロパティが必要になります。</span><span class="sxs-lookup"><span data-stu-id="1a134-247">Now you should have two managed properties mapped to the two crawled properties:</span></span>

<span data-ttu-id="1a134-248">[![マップ先のクロールされたプロパティに表示された管理プロパティ](../media/SPRetention14.png)](../media/SPRetention14.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="1a134-248">[ ![Managed properties shown mapped to crawled properties](../media/SPRetention14.png) ](../media/SPRetention14.png#lightbox)</span></span>

<span data-ttu-id="1a134-249">エンタープライズ検索を実行して、正しく設定されていることを確認しましょう。</span><span class="sxs-lookup"><span data-stu-id="1a134-249">Let's verify that our setup is correct by running an enterprise search.</span></span> <span data-ttu-id="1a134-250">ブラウザーで、 *https://\<your_tenant>.sharepoint.com/search* に移動します。</span><span class="sxs-lookup"><span data-stu-id="1a134-250">In a browser, go to *https://\<your_tenant>.sharepoint.com/search*.</span></span> <span data-ttu-id="1a134-251">検索ボックスに \***RefinableString00:"Product Specification"** _ と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="1a134-251">In the search box, type \***RefinableString00:"Product Specification"** _ and press enter.</span></span> <span data-ttu-id="1a134-252">この検索により、**_ドキュメントの種類_** の _ *製品の仕様*\* を持つすべてのドキュメントが返されます。</span><span class="sxs-lookup"><span data-stu-id="1a134-252">This search should return all documents that have a _ *Product Specification*\* of **_Doc Type_**.</span></span>

<span data-ttu-id="1a134-253">検索ボックスに、**RefinableString00:"Product Specification" AND RefinableString01:Final** と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="1a134-253">Now in the search box, type **RefinableString00:"Product Specification" AND RefinableString01:Final** and press enter.</span></span> <span data-ttu-id="1a134-254">これにより、**_ドキュメントの種類_*_ の **製品の仕様** を持ち、_\* 状態*\* が **_最終版_** であるすべてのドキュメントが返されます。</span><span class="sxs-lookup"><span data-stu-id="1a134-254">This should return all documents that have **Product Specification** of **_Doc Type_*_ and a _\* Status*\* of **_Final_**.</span></span>

### <a name="create-auto-apply-label-policies"></a><span data-ttu-id="1a134-255">自動適用ラベル ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="1a134-255">Create auto-apply label policies</span></span>

<span data-ttu-id="1a134-256">KQL クエリが機能していることを確認したので、KQL クエリを使用して適切なドキュメントに製品の仕様の保持ラベルを適切なドキュメントに自動的に適用する自動適用ラベル ポリシーを作成しましょう。</span><span class="sxs-lookup"><span data-stu-id="1a134-256">Now that we've verified that the KQL query is working, let's create an auto-apply label policy that uses a KQL query to automatically apply the Product Specification retention label to the appropriate documents.</span></span>

1. <span data-ttu-id="1a134-257">[[コンプライアンス センター]](https://compliance.microsoft.com/homepage)で、[**レコード管理**] > [**ラベル ポリシー**] > [**ラベルの自動適用**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="1a134-257">In the [compliance center](https://compliance.microsoft.com/homepage), go to **Records management** > **Label policies** > **Auto-apply a label**.</span></span>

   <span data-ttu-id="1a134-258">[![[ラベル] ページで [ラベルの自動適用] を選択する](../media/SPRetention16.png)](../media/SPRetention16.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="1a134-258">[ ![Select "Auto-apply a label" on the Labels page](../media/SPRetention16.png) ](../media/SPRetention16.png#lightbox)</span></span>

2. <span data-ttu-id="1a134-259">自動ラベル付けポリシーの作成ウィザードの [**自動ラベル付けポリシーに名前を付ける**] ページで、**製品仕様ラベルの自動適用** などの名前と、オプションの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="1a134-259">In the Create auto-labeling policy wizard, on the **Name your auto-labeling policy** page, enter a name such as **Auto-apply Product Specification label**, and an optional description.</span></span> <span data-ttu-id="1a134-260">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a134-260">Then select **Next**.</span></span>

3. <span data-ttu-id="1a134-261">[**このラベルを適用するコンテンツの種類を選択する**] ページで、[**特定の単語やフレーズ、またはプロパティを含むコンテンツにラベルを適用する**] を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a134-261">On the **Choose the type of content you want to apply this label to** page, select **Apply label to content that contains specific words or phrases, or properties**, and then select **Next**.</span></span>
    
   <span data-ttu-id="1a134-262">[ ![[特定の単語、語句、またはプロパティを含むコンテンツにラベルを適用する] を選択する](../media/SPRetention17.png) ](../media/SPRetention17.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="1a134-262">[ ![Select Apply label to content that contains specific words or phrases, or properties](../media/SPRetention17.png) ](../media/SPRetention17.png#lightbox)</span></span>
    
   <span data-ttu-id="1a134-263">このオプションでは、前のセクションでテストしたものと同じ KQL 検索クエリを提供します。</span><span class="sxs-lookup"><span data-stu-id="1a134-263">This option lets us provide the same KQL search query that we tested in the previous section.</span></span> <span data-ttu-id="1a134-264">このクエリは、状態が [*最終*] のすべての製品の仕様ドキュメントを返します。</span><span class="sxs-lookup"><span data-stu-id="1a134-264">The query returns all Product Specification documents that have a status of *Final*.</span></span> <span data-ttu-id="1a134-265">自動適用ラベル ポリシーでこの同じクエリを使用すると、製品の仕様の保持ラベルが、このクエリに一致するすべてのドキュメントに自動適用されます。</span><span class="sxs-lookup"><span data-stu-id="1a134-265">When we use this same query in the auto-apply label policy, the Product Specification retention label will be automatically applied to all documents that match it.</span></span>

4. <span data-ttu-id="1a134-266">[**このクエリに一致するコンテンツにラベルを適用する**] ページで、「**RefinableString00:"Product Specification" AND RefinableString01:Final**」と入力し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a134-266">On the **Apply label to content matching this query** page, type **RefinableString00:"Product Specification" AND RefinableString01:Final**, and then select **Next**.</span></span>

   ![[キーワード クエリ エディター] ボックスでクエリを指定する](../media/SPRetention19.png)

5. <span data-ttu-id="1a134-268">[**ポリシーを適用する場所を選択する**] ページで、ポリシーを適用するコンテンツの場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a134-268">On the **Choose locations to apply the policy** page, you select the content locations that you want to apply the policy to.</span></span> <span data-ttu-id="1a134-269">このシナリオでは、すべての生産ドキュメントが SharePoint ドキュメント ライブラリにのみ保存されるため、SharePoint の場所にのみポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="1a134-269">For this scenario, we apply the policy only to SharePoint locations, because all the production documents are stored in SharePoint document libraries.</span></span> <span data-ttu-id="1a134-270">**Exchange メール**、**OneDrive アカウント**、および **Microsoft 365 グループ** の状態を [**オフ**] に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="1a134-270">Toggle the status for **Exchange email**, **OneDrive accounts**, and **Microsoft 365 Groups** to **Off**.</span></span> <span data-ttu-id="1a134-271">[**次へ**] を選択する前に、SharePoint サイトの状態が [**オン**] に設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="1a134-271">Make sure that the status for SharePoint sites is set to **On** before you select **Next**:</span></span> 
    
    ![ラベルを自動適用する特定のサイトを選択する](../media/SPRetentionSPlocations.png)
    
   > [!TIP]
   > <span data-ttu-id="1a134-273">ポリシーをすべての SharePoint サイトに適用する代わりに、[**サイトの選択**] を選択して、特定の SharePoint サイトの URL を追加できます。</span><span class="sxs-lookup"><span data-stu-id="1a134-273">Instead of applying the policy to all SharePoint sites, you can select **Choose site** and add the URLs for specific SharePoint sites.</span></span>

6. <span data-ttu-id="1a134-274">[**自動適用するラベルを選択する**] ページで、[**ラベルの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a134-274">On the **Choose a label to auto-apply** page, select **Add label**.</span></span>

7. <span data-ttu-id="1a134-275">保持ラベルの一覧で、[**製品の仕様**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a134-275">From the list of retention labels, select **Product Specification**.</span></span> <span data-ttu-id="1a134-276">[**追加**]、[**次へ**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="1a134-276">Then select **Add** and **Next**.</span></span>

8. <span data-ttu-id="1a134-277">設定の確認:</span><span class="sxs-lookup"><span data-stu-id="1a134-277">Review your settings:</span></span>

    ![ラベルを自動適用するように設定する](../media/SPRetention18.png)

9. <span data-ttu-id="1a134-279">[**送信**] を選択して、自動適用ラベル ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="1a134-279">Select **Submit** to create the auto-apply label policy.</span></span>
    
   >[!NOTE]
   ><span data-ttu-id="1a134-280">KQL 検索クエリに一致するすべてのドキュメントに製品の仕様のラベルを自動的に適用するには、最大 7 日かかります。</span><span class="sxs-lookup"><span data-stu-id="1a134-280">It takes up to 7 days to automatically apply the Product Specification label to all documents that match the KQL search query.</span></span>

### <a name="verify-that-the-retention-label-was-automatically-applied"></a><span data-ttu-id="1a134-281">保持ラベルが自動的に適用されたことを確認する</span><span class="sxs-lookup"><span data-stu-id="1a134-281">Verify that the retention label was automatically applied</span></span>

<span data-ttu-id="1a134-282">7 日後、コンプライアンス センターの [[アクティビティ エクスプローラー](data-classification-activity-explorer.md)] を使用して、作成した自動適用ラベル ポリシーがこのシナリオの保持ラベルを製品ドキュメントに自動的に適用したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="1a134-282">After 7 days, use [activity explorer](data-classification-activity-explorer.md) in the compliance center to verify that the auto-apply label policy that we created did automatically apply the retention labels to the product documents.</span></span>

<span data-ttu-id="1a134-283">ドキュメント ライブラリ内のドキュメントのプロパティも確認します。</span><span class="sxs-lookup"><span data-stu-id="1a134-283">Also look at the properties of the documents in the Document Library.</span></span> <span data-ttu-id="1a134-284">情報パネルで、選択したドキュメントに保持ラベルが適用されていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="1a134-284">In the information panel, you can see that the retention label is applied to a selected document.</span></span>

<span data-ttu-id="1a134-285">[![ドキュメント ライブラリのドキュメント プロパティを見て、ラベルが適用されたことを確認する](../media/SPRetention21.png)](../media/SPRetention21.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="1a134-285">[ ![Verify that label was applied by looking at the document properties in the Document Library](../media/SPRetention21.png) ](../media/SPRetention21.png#lightbox)</span></span>

<span data-ttu-id="1a134-286">保持ラベルはドキュメントに自動適用され、これらのドキュメントを *レコード* として宣言するように保持ラベルが構成されているため、ドキュメントは削除されないよう保護されます。</span><span class="sxs-lookup"><span data-stu-id="1a134-286">Because the retention labels were auto-applied to documents, those documents are protected from deletion because the retention label was configured to declare the documents as *records*.</span></span> <span data-ttu-id="1a134-287">この保護の例として、これらのドキュメントのいずれかを削除しようとすると、次のエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a134-287">As an example of this protection, we get the following error message when we try to delete one of these documents:</span></span>

<span data-ttu-id="1a134-288">[![ラベルがドキュメントをレコードとして宣言しているため、ドキュメントを削除できないことを示すエラーメッセージが表示されます。](../media/SPRetention22.png)](../media/SPRetention22.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="1a134-288">[ ![An error message shows that documents can't be deleted because the label declares that the documents are records.](../media/SPRetention22.png) ](../media/SPRetention22.png#lightbox)</span></span>

## <a name="generate-the-event-that-triggers-the-retention-period"></a><span data-ttu-id="1a134-289">保持期間をトリガーするイベントを生成する</span><span class="sxs-lookup"><span data-stu-id="1a134-289">Generate the event that triggers the retention period</span></span>

<span data-ttu-id="1a134-290">保持ラベルが適用されたので、特定の製品の生産終了を示すイベントに注目しましょう。</span><span class="sxs-lookup"><span data-stu-id="1a134-290">Now that the retention labels are applied, let's focus on the event that will indicate the end of production for a particular product.</span></span> <span data-ttu-id="1a134-291">このイベントは、保持ラベルで定義されている保持期間の開始をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="1a134-291">This event triggers the beginning of the retention period that's defined in the retention labels.</span></span> <span data-ttu-id="1a134-292">たとえば、製品の仕様ドキュメントの場合、「生産終了」 イベントがトリガーされると、5 年間の保持期間が開始します。</span><span class="sxs-lookup"><span data-stu-id="1a134-292">For example, for product specification documents, the 5-year retention period begins when the "end of production" event is triggered.</span></span>

<span data-ttu-id="1a134-293">**管理** > **イベントのレコード** に移動して、Microsoft 365 コンプライアンス センターでイベントを手動で作成できます。</span><span class="sxs-lookup"><span data-stu-id="1a134-293">You can manually create the event in the Microsoft 365 compliance center by going to **Records Managements** > **Events**.</span></span> <span data-ttu-id="1a134-294">イベントの種類を選択し、正しい資産 ID を設定して、イベントの日付を入力します。</span><span class="sxs-lookup"><span data-stu-id="1a134-294">You would choose the event type, set the correct asset IDs, and enter a date for the event.</span></span> <span data-ttu-id="1a134-295">詳細については、[「イベントが発生したときに保持を開始 」](event-driven-retention.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a134-295">For more information, see [Start retention when an event occurs](event-driven-retention.md).</span></span>

<span data-ttu-id="1a134-296">ただし、このシナリオでは、外部の生産システムからイベントを自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="1a134-296">But for this scenario, we'll automatically generate the event from an external production system.</span></span> <span data-ttu-id="1a134-297">このシステムは、製品が生産中であるかどうかを示す単一の SharePoint リストです。</span><span class="sxs-lookup"><span data-stu-id="1a134-297">The system is a simple SharePoint list that indicates whether a product is in production.</span></span> <span data-ttu-id="1a134-298">リストに関連付けられた [Power Automate](/flow/getting-started) フローが、イベントをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="1a134-298">A [Power Automate](/flow/getting-started) flow that's associated with the list will trigger the event.</span></span> <span data-ttu-id="1a134-299">実際のシナリオでは、HR や CRM システムなど、イベントを生成するさまざまなシステムを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1a134-299">In a real-world scenario, you could use various systems to generate the event, such as an HR or CRM system.</span></span> <span data-ttu-id="1a134-300">Power Automate には、Microsoft Exchange、SharePoint、Teams、Dynamics 365 などの Microsoft 365 ワークロードに加え、Twitter、Box、Salesforce、Workdays などのサード パーティ アプリ向けのすぐに使用できる多くの操作と文書パーツが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1a134-300">Power Automate contains many ready-to-use interactions and building block for Microsoft 365 workloads, such as Microsoft Exchange, SharePoint, Teams, and Dynamics 365, plus third-party apps such as Twitter, Box, Salesforce, and Workdays.</span></span> <span data-ttu-id="1a134-301">この機能を使用すると、Power Automate をさまざまなシステムと簡単に統合できます。</span><span class="sxs-lookup"><span data-stu-id="1a134-301">This feature makes it easy to integrate Power Automate with various systems.</span></span> <span data-ttu-id="1a134-302">詳細については、「[イベント ベースの保持を自動化する](./event-driven-retention.md#automate-events-by-using-a-rest-api)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a134-302">For more information, see [Automate event-driven retention](./event-driven-retention.md#automate-events-by-using-a-rest-api).</span></span>

<span data-ttu-id="1a134-303">次のスクリーンショットは、イベントのトリガーに使用される SharePoint リストを示しています。</span><span class="sxs-lookup"><span data-stu-id="1a134-303">The following screenshot shows the SharePoint list that will be used the trigger the event:</span></span>

<span data-ttu-id="1a134-304">[![保持イベントをトリガーするリスト](../media/SPRetention23.png)](../media/SPRetention23.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="1a134-304">[ ![The list that will trigger the retention event](../media/SPRetention23.png) ](../media/SPRetention23.png#lightbox)</span></span>

<span data-ttu-id="1a134-305">現在生産中の製品は 2 つあり、[_ **生産中\*\*\*] 列で [**はい\* _] で示されます。</span><span class="sxs-lookup"><span data-stu-id="1a134-305">There are two products currently in production, as indicated by the ***Yes** _ in the _ *In Production** column.</span></span> <span data-ttu-id="1a134-306">製品のこの列の値が [**_いいえ_**] に設定されている場合、リストに関連付けられたフローは自動的にイベントを生成します。</span><span class="sxs-lookup"><span data-stu-id="1a134-306">When the value in this column is set to **_No_** for a product, the flow associated with the list will automatically generate the event.</span></span> <span data-ttu-id="1a134-307">このイベントにより、対応する製品ドキュメントに自動適用された保持ラベルの保持期間の開始がトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="1a134-307">The event triggers the start of the retention period for the retention label that was auto-applied to the corresponding product documents.</span></span>

<span data-ttu-id="1a134-308">このシナリオでは、次のフローを使用してイベントをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="1a134-308">For this scenario, we use the following flow to trigger the event:</span></span>

<span data-ttu-id="1a134-309">[![イベントをトリガーするフローの構成](../media/SPRetention24.png)](../media/SPRetention24.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="1a134-309">[ ![Configuring the flow that will trigger the event](../media/SPRetention24.png) ](../media/SPRetention24.png#lightbox)</span></span>

<span data-ttu-id="1a134-310">このフローを作成するには、SharePoint コネクターから開始し、「**アイテムが作成または変更されたとき**」トリガーを選択します。</span><span class="sxs-lookup"><span data-stu-id="1a134-310">To create this flow, start from a SharePoint connector and select the **When an item is created or modified** trigger.</span></span> <span data-ttu-id="1a134-311">サイトアドレスおよびリスト名を指定します。</span><span class="sxs-lookup"><span data-stu-id="1a134-311">Specify the site address and list name.</span></span> <span data-ttu-id="1a134-312">[**生産中**] リスト列の値が [\**_いいえ_* _] に設定されている (または条件カードで false に等しい) 場合に基づいて条件を追加します。</span><span class="sxs-lookup"><span data-stu-id="1a134-312">Then add a condition based on when the **In Production** list column value is set to **_No_* _ (or equal to _false* on the condition card).</span></span> <span data-ttu-id="1a134-313">次に、組み込みの HTTP テンプレートに基づいてアクションを追加します。</span><span class="sxs-lookup"><span data-stu-id="1a134-313">Then add an action based on the built-in HTTP template.</span></span> <span data-ttu-id="1a134-314">次のセクションの値を使用して、HTTP アクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="1a134-314">Use the values in the following section to configure the HTTP action.</span></span> <span data-ttu-id="1a134-315">以下のセクションから **URI** および **本文** プロパティの値をコピーして、テンプレートに貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="1a134-315">You can copy the values for the **URI** and **Body** properties from the following section and paste them into the template.</span></span>

- <span data-ttu-id="1a134-316">**方法**: 投稿</span><span class="sxs-lookup"><span data-stu-id="1a134-316">**Method**: POST</span></span>
- <span data-ttu-id="1a134-317">**URI**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="1a134-317">**URI**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>
- <span data-ttu-id="1a134-318">**ヘッダー**: キー = Content-Type、値 = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="1a134-318">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>
- <span data-ttu-id="1a134-319">**本文**:</span><span class="sxs-lookup"><span data-stu-id="1a134-319">**Body**:</span></span>
    
    ```xml
    <?xml version='1.0' encoding='utf-8' standalone='yes'>
    <entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices' xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata' xmlns='https://www.w3.org/2005/Atom'>
    <category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent'>
    <updated>9/9/2017 10:50:00 PM</updated>
    <content type='application/xml'>
    <m:properties>
    <d:Name>Cessation Production @{triggerBody()?['Product_x0020_Name']?['Value']}</d:Name>
    <d:EventType>Product Cessation&lt;</d:EventType>
    <d:SharePointAssetIdQuery>ProductName:&quot;@{triggerBody()?['Product_x0020_Name']?['Value']}<d:SharePointAssetIdQuery>
    <d:EventDateTime>@{formatDateTime(utcNow(),'yyyy-MM-dd')}</d:EventDateTime>
    </m:properties>
    </content&gt>
    </entry>
    ```

<span data-ttu-id="1a134-320">このリストでは、このシナリオ用に構成する必要があるアクションの **本文** プロパティ内のパラメーターを以下のように説明します。</span><span class="sxs-lookup"><span data-stu-id="1a134-320">This list describes the parameters in the **Body** property of the action that must be configured for this scenario:</span></span>

- <span data-ttu-id="1a134-321">**名前**: このパラメーターは、Microsoft 365 コンプライアンス センターで作成されるイベントの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="1a134-321">**Name**: This parameter specifies the name of the event that will be created in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="1a134-322">このシナリオでは、名前は「Cessation Production *xxx*」 です。*xxx* は、前に作成した **ProductName** 管理プロパティの値です。</span><span class="sxs-lookup"><span data-stu-id="1a134-322">For this scenario, the name is "Cessation Production *xxx*", where *xxx* is the value of the **ProductName** managed property that we created earlier.</span></span>
- <span data-ttu-id="1a134-323">**EventType**: このパラメーターの値は、作成されたイベントが適用されるイベントの種類に対応します。</span><span class="sxs-lookup"><span data-stu-id="1a134-323">**EventType**: The value for this parameter corresponds to the event type that the created event will apply to.</span></span> <span data-ttu-id="1a134-324">このイベントの種類は、保持ラベルを作成したときに定義されました。</span><span class="sxs-lookup"><span data-stu-id="1a134-324">This event type was defined when you created the retention label.</span></span> <span data-ttu-id="1a134-325">このシナリオでは、イベントの種類は 「製品の中止」 です。</span><span class="sxs-lookup"><span data-stu-id="1a134-325">For this scenario, the event type is "Product Cessation."</span></span>
- <span data-ttu-id="1a134-326">**SharePointAssetIdQuery**: このパラメーターは、イベントの資産 ID を定義します。</span><span class="sxs-lookup"><span data-stu-id="1a134-326">**SharePointAssetIdQuery**: This parameter defines the asset ID for the event.</span></span> <span data-ttu-id="1a134-327">イベント ベースの保持には、ドキュメントの一意の識別子が必要です。</span><span class="sxs-lookup"><span data-stu-id="1a134-327">Event-based retention needs a unique identifier for the document.</span></span> <span data-ttu-id="1a134-328">資産 ID を使用して、特別なイベントが適用されるドキュメントを特定できます。または、このシナリオの場合と同様に、独自の **製品名** であるメタデータ列を特定できます。</span><span class="sxs-lookup"><span data-stu-id="1a134-328">We can use asset IDs to identify the documents that a particular event applies to or, as in this scenario, the metadata column **Product Name**.</span></span> <span data-ttu-id="1a134-329">これを行うには、KQL クエリで使用できる新しい **ProductName** 管理プロパティを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a134-329">To do  this, we need to create a new **ProductName** managed property that can be used in the KQL query.</span></span> <span data-ttu-id="1a134-330">(または、新しい管理プロパティを作成する代わりに **RefinableString00** を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="1a134-330">(Alternatively, we could use **RefinableString00** instead of creating a new managed property).</span></span> <span data-ttu-id="1a134-331">また、この新しい管理プロパティを **ows_Product_x0020_Name** のクロールされたプロパティにマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a134-331">We also need to map this new managed property to the **ows_Product_x0020_Name** crawled property.</span></span> <span data-ttu-id="1a134-332">この管理プロパティのスクリーンショットを次に示します。</span><span class="sxs-lookup"><span data-stu-id="1a134-332">Here's a screenshot of this managed property.</span></span>

    <span data-ttu-id="1a134-333">[![保持管理プロパティ](../media/SPRetention25.png)](../media/SPRetention25.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="1a134-333">[ ![Rentention managed property](../media/SPRetention25.png) ](../media/SPRetention25.png#lightbox)</span></span>

- <span data-ttu-id="1a134-334">**EventDateTime**: このパラメーターは、イベントが発生する日付を定義します。</span><span class="sxs-lookup"><span data-stu-id="1a134-334">**EventDateTime**: This parameter defines the date that the event occurs.</span></span> <span data-ttu-id="1a134-335">現在の日付の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="1a134-335">Use the current date format:</span></span><br/><br/><span data-ttu-id="1a134-336">*formatDateTime(utcNow(),'yyyy-MM-dd'*)</span><span class="sxs-lookup"><span data-stu-id="1a134-336">*formatDateTime(utcNow(),'yyyy-MM-dd'*)</span></span>

### <a name="putting-it-all-together"></a><span data-ttu-id="1a134-337">すべてをまとめる</span><span class="sxs-lookup"><span data-stu-id="1a134-337">Putting it all together</span></span>

<span data-ttu-id="1a134-338">保持ラベルが作成されて自動適用され、フローが構成および作成されます。</span><span class="sxs-lookup"><span data-stu-id="1a134-338">Now the retention label is created and auto-applied, and the flow is configured and created.</span></span> <span data-ttu-id="1a134-339">[製品] リストの **[生産中]** 列の値が、**_[はい]_*_ から _*_[いいえ]_*_ に変更された場合は、フローがトリガーされてイベントが作成されます。コンプライアンス センターでこのイベントを確認するには、_*[レコード管理]** > **[イベント]** の順にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="1a134-339">When the value in the **In Production** column for the Spinning Widget product in the Products list is changed from **_Yes_*_ to _*_No_*_, the flow is triggered to create the event. To see this event in the compliance center, go to _\* Records management*\* > **Events**.</span></span>

<span data-ttu-id="1a134-340">[![コンプライアンス センターの [イベント] ページに表示されるフローによってトリガーされたイベント。](../media/SPRetention28.png)](../media/SPRetention28.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="1a134-340">[ ![The event that was triggered by the flow is displayed on the Events page in the compliance center.](../media/SPRetention28.png) ](../media/SPRetention28.png#lightbox)</span></span>

<span data-ttu-id="1a134-341">イベントを選択して、ポップアップ ページで詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="1a134-341">Select the event to view the details on the flyout page.</span></span> <span data-ttu-id="1a134-342">イベントが作成された場合でも、イベントの状態には、SharePoint サイトまたはドキュメントが処理されていないことが示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1a134-342">Notice that even though the event is created, the event status shows that no SharePoint sites or documents have been processed.</span></span>

![イベントの詳細](../media/SPRetention29.png)

<span data-ttu-id="1a134-344">しかし、しばらくすると、イベントの状態に、SharePoint サイトと SharePoint ドキュメントが処理されたことが示されます。</span><span class="sxs-lookup"><span data-stu-id="1a134-344">But after a delay, the event status shows that a SharePoint site and a SharePoint document have been processed.</span></span>  

![イベントの詳細は、ドキュメントが処理されたことを示します。](../media/SPRetention31.png)
 
<span data-ttu-id="1a134-346">これは、*生産中止の回転ウィジェット イベント* イベントの日付に基づいて、回転ウィジェットの製品ドキュメントに適用されるラベルの保持期間が開始されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="1a134-346">This shows that the retention period for the label applied to the Spinning Widget product document has been initiated, based on the event date of the *Cessation Production Spinning Widget* event.</span></span> <span data-ttu-id="1a134-347">1 日間の保持期間を構成してテスト環境にシナリオを実装したと仮定すると、イベントが作成されてから数日後に製品ドキュメントのドキュメント ライブラリに移動し、ドキュメントが削除されたことを確認できます (SharePoint で削除ジョブが実行された後)。</span><span class="sxs-lookup"><span data-stu-id="1a134-347">Assuming that you implemented the scenario in your test environment by configuring a one-day retention period, you can go to the document library for your product documents a few days after the event was created and verify that the document was deleted (after the deletion job in SharePoint has run).</span></span>

### <a name="more-about-asset-ids"></a><span data-ttu-id="1a134-348">資産 ID の詳細</span><span class="sxs-lookup"><span data-stu-id="1a134-348">More about asset IDs</span></span>

<span data-ttu-id="1a134-349">[「イベントが発生したときに保持を開始」](event-driven-retention.md) の記事で説明したように、イベントの種類、保持ラベル、イベント、および資産 ID の関係を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="1a134-349">As the [Start retention when an event occurs](event-driven-retention.md) article explains, it's important to understand the relationship between event types, retention labels, events, and asset IDs.</span></span> <span data-ttu-id="1a134-350">資産 ID は、SharePoint と OneDrive の単一のドキュメント プロパティです。</span><span class="sxs-lookup"><span data-stu-id="1a134-350">The asset ID is simply a document property in SharePoint and OneDrive.</span></span> <span data-ttu-id="1a134-351">イベントによって保持期間がトリガーされるドキュメントを特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1a134-351">It helps you identify the documents whose retention period will be triggered by the event.</span></span> <span data-ttu-id="1a134-352">既定では、SharePoint にはイベント ベースの保持に使用できる **資産 ID** プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="1a134-352">By default, SharePoint has an **Asset Id** property that you can use for event-driven retention:</span></span>

![資産 ID プロパティは、ドキュメント プロパティの詳細ページに表示されます。](../media/SPRetention26.png)

<span data-ttu-id="1a134-354">次のスクリーンショットに示すように、資産 ID 管理プロパティは **ComplianceAssetId** と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="1a134-354">As the following screenshot shows, the asset ID managed property is called **ComplianceAssetId**.</span></span>

<span data-ttu-id="1a134-355">[![ComplianceAssetId 管理プロパティ](../media/SPRetention27.png)](../media/SPRetention27.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="1a134-355">[ ![ComplianceAssetId managed property](../media/SPRetention27.png) ](../media/SPRetention27.png#lightbox)</span></span>

<span data-ttu-id="1a134-356">既定の **資産 ID** プロパティを使用する代わりに、他のプロパティを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="1a134-356">Instead of using the default **Asset Id** property as we do in this scenario, you can use any other property.</span></span> <span data-ttu-id="1a134-357">ただし、イベントの資産 ID またはキーワードを指定しない場合、そのイベントの種類のラベルの付いたすべてのコンテンツはイベントによってトリガーされる保持期間を持つことを理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="1a134-357">But it's important to understand that if you don't specify an asset ID or keywords for an event, all the content that has a label of that event type will get its retention period triggered by the event.</span></span>

### <a name="using-advanced-search-in-sharepoint"></a><span data-ttu-id="1a134-358">SharePoint で高度な検索を使用する</span><span class="sxs-lookup"><span data-stu-id="1a134-358">Using advanced search in SharePoint</span></span>

<span data-ttu-id="1a134-359">前のスクリーンショットでは、**ComplianceTag** と呼ばれる保持ラベルに関連する別の管理プロパティがあり、クロールされたプロパティにマップされていることもわかります。</span><span class="sxs-lookup"><span data-stu-id="1a134-359">In the previous screenshot, you can see that there's another managed property related to retention labels called **ComplianceTag** that's mapped to a crawled property.</span></span> <span data-ttu-id="1a134-360">**ComplianceAssetId** 管理プロパティは、クロールされたプロパティにもマップされます。</span><span class="sxs-lookup"><span data-stu-id="1a134-360">The **ComplianceAssetId** managed property is also mapped to a crawled property.</span></span> <span data-ttu-id="1a134-361">つまり、高度な検索でこれらの管理プロパティを使用して、保持ラベルでタグ付けされたすべてのドキュメントを取得できます。</span><span class="sxs-lookup"><span data-stu-id="1a134-361">This means that you can use these managed properties in advanced search to retrieve all documents that have been tagged with a retention label.</span></span>