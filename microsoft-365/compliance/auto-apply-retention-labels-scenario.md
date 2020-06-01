---
title: 保持ラベルを使用して、SharePoint Online に保存されている製品ドキュメントのライフサイクルを管理する
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
description: このソリューション シナリオは、保持ラベルを使用して SharePoint Online に保存されている製品関連ドキュメントのライフサイクルを管理する方法を示します。 これは、ドキュメントを使用してコンテンツを分類し、特に保持ラベルを自動適用し、イベント ベースの保持を設定することによって行われます。
ms.openlocfilehash: 9c8a7044dccdb60f8e579d6dcad64310d1dda0d5
ms.sourcegitcommit: 6746fae2f68400fd985711b1945b66766d2a59a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2020
ms.locfileid: "44419103"
---
# <a name="manage-the-lifecycle-of-sharepoint-documents-with-retention-labels"></a><span data-ttu-id="9c4f5-104">保持ラベルを使用して SharePoint ドキュメントのライフサイクルを管理する</span><span class="sxs-lookup"><span data-stu-id="9c4f5-104">Manage the lifecycle of SharePoint documents with retention labels</span></span>

><span data-ttu-id="9c4f5-105">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="9c4f5-105">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="9c4f5-106">この記事では、保持ラベルを使用して、特にラベルを自動適用してイベント ベースの保持を構成することにより、SharePoint Online に保存されている製品関連ドキュメントのライフサイクルを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-106">This article describes how you can manage the lifecycle of product-related documents stored in SharePoint Online by using retention labels, and specifically by auto-applying labels and configuring event-based retention.</span></span> <span data-ttu-id="9c4f5-107">自動適用機能は、SharePoint メタデータを使用してドキュメント分類を活用します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-107">The auto-apply functionality leverages document classification by the use of SharePoint metadata.</span></span> <span data-ttu-id="9c4f5-108">この記事のシナリオは製品関連のドキュメントに基づいていますが、他のシナリオにも同じ概念を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-108">The scenario in this article is based on product-related documents, but the same concepts can be used for other scenarios.</span></span> <span data-ttu-id="9c4f5-109">たとえば、石油およびガス産業では、石油基地、坑井検層、生産ライセンスなどの物理的資産に関連するドキュメントのライフサイクルを管理できます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-109">For example, in the oil and gas industry, you could manage the lifecycle of documents related to physical assets such as oil platforms, well logs, or production licenses.</span></span> <span data-ttu-id="9c4f5-110">金融サービス業界では、銀行口座、住宅ローン、または保険契約に関連するドキュメントを管理できます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-110">In the financial services industry, you can manage documents related to bank accounts, mortgages, or insurance contracts.</span></span> <span data-ttu-id="9c4f5-111">公的機関では、建設許可または税務フォームに関連する文書を管理できます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-111">In the public sector, you can manage documents related to construction permits or tax forms.</span></span>

<span data-ttu-id="9c4f5-112">この記事のシナリオを見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-112">Let's look at the scenario for this article.</span></span> <span data-ttu-id="9c4f5-113">情報アーキテクチャと保持ラベルの定義を見ていきます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-113">We'll look at the information architecture and the definition of the retention labels.</span></span> <span data-ttu-id="9c4f5-114">次に、ラベルを自動適用してドキュメントを分類し、最終的に保持期間の開始を開始するイベントを生成します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-114">Then we'll look at classifying documents by auto-applying the labels, and finally generating the events that initiate the start of the retention period.</span></span>

## <a name="information-architecture"></a><span data-ttu-id="9c4f5-115">情報アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="9c4f5-115">Information architecture</span></span>

<span data-ttu-id="9c4f5-116">この記事のシナリオは、SharePoint Online を使用して、会社が開発する製品に関連するすべてのドキュメントを保存する製造会社に基づいています。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-116">The scenario for this article is based on a manufacturing company that uses SharePoint Online to store all the documents related to the products the company develops.</span></span> <span data-ttu-id="9c4f5-117">これらのドキュメントには、製品の仕様、仕入先との契約、およびユーザー マニュアルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-117">These documents include product specifications, agreements with suppliers, and user manuals.</span></span> <span data-ttu-id="9c4f5-118">これらのドキュメントがエンタープライズ コンテンツ管理ポリシーの一部として SharePoint に保存されている場合、ドキュメント メタデータが定義され、分類に使用されます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-118">When these documents are stored in SharePoint as part of the Enterprise Content Management policies, document metadata is defined and used to classify them.</span></span> <span data-ttu-id="9c4f5-119">各ドキュメントには、次のメタデータ プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-119">Each document has the following metadata properties:</span></span>

- <span data-ttu-id="9c4f5-120">**ドキュメントの種類** (製品の仕様、契約、ユーザー マニュアルなど)</span><span class="sxs-lookup"><span data-stu-id="9c4f5-120">**Doc Type** (such as product specification, agreement, and user manual)</span></span>

- <span data-ttu-id="9c4f5-121">**製品名**</span><span class="sxs-lookup"><span data-stu-id="9c4f5-121">**Product Name**</span></span>

- <span data-ttu-id="9c4f5-122">**状態** (下書きまたは最終版)</span><span class="sxs-lookup"><span data-stu-id="9c4f5-122">**Status** (draft or final)</span></span>

<span data-ttu-id="9c4f5-123">このメタデータは、すべてのドキュメントの**生産ドキュメント**と呼ばれる基本コンテンツの種類を形成します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-123">This metadata forms the base content type called **Production Document** for all documents.</span></span>

![製品ドキュメントのメタデータ](../media/SPRetention1.png)

> [!NOTE]
> <span data-ttu-id="9c4f5-125">**ドキュメントの種類**プロパティと**状態**プロパティは、後述のシナリオで保持ポリシーによって使用され、保持ラベルを分類して自動適用します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-125">The **Doc Type** and **Status** properties are used by retention policies later in the scenario to classify and auto-apply retention labels.</span></span>

<span data-ttu-id="9c4f5-126">さまざまな種類のドキュメントを表す複数のコンテンツの種類を使用できますが、製品ドキュメントに重点を置きましょう。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-126">We can have several content types that represent different types of documents, but let's focus on the Product Documentation.</span></span>

<span data-ttu-id="9c4f5-127">このシナリオでは、Managed Metadata Service と用語ストアを使用して、**ドキュメントの種類**の用語セットと**製品名**の用語セットを作成します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-127">In this scenario, we use the Managed Metadata service and the Term store to create a term set for **Doc Type** and another one for **Product Name**.</span></span> <span data-ttu-id="9c4f5-128">用語セットごとに、値ごとに用語を作成します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-128">For each term set, we create a term for each value.</span></span> <span data-ttu-id="9c4f5-129">SharePoint 組織の用語ストアでは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-129">It would look like something like this in Term store for your SharePoint organization:</span></span>

![用語ストアの製品ドキュメントの用語セット](../media/SPRetention2.png)

<span data-ttu-id="9c4f5-131">コンテンツの種類は、[コンテンツ タイプ ハブ](https://support.office.com/article/manage-content-type-publishing-06f39ac0-5576-4b68-abbc-82b68334889b)を使用して作成および公開できます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-131">Content Type can be created and published using the [Content Type Hub](https://support.office.com/article/manage-content-type-publishing-06f39ac0-5576-4b68-abbc-82b68334889b).</span></span> <span data-ttu-id="9c4f5-132">コンテンツの種類は、[PnP プロビジョニング フレームワーク](https://docs.microsoft.com/sharepoint/dev/solution-guidance/pnp-provisioning-framework)や[サイト デザイン JSON スキーマ](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-json-schema#define-a-new-content-type)などのサイト プロビジョニング ツールを使用して作成および公開することもできます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-132">A content type can also be created and published using site provisioning tools such as the [PnP provisioning framework](https://docs.microsoft.com/sharepoint/dev/solution-guidance/pnp-provisioning-framework) or the [site design JSON schema](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-json-schema#define-a-new-content-type).</span></span>

<span data-ttu-id="9c4f5-133">各製品には、1 つのドキュメント ライブラリを含む専用の SharePoint Online サイトがあり、適切なコンテンツの種類が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-133">Each product has a dedicated SharePoint Online site that contains one document library, with the right content types enabled.</span></span> <span data-ttu-id="9c4f5-134">すべてのドキュメントはこのドキュメント ライブラリに保存されます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-134">All documents are stored in this document library.</span></span>

![製品ドキュメントのドキュメント ライブラリ](../media/SPRetention3.png)

> [!NOTE]
> <span data-ttu-id="9c4f5-136">このシナリオの製造会社では、製品ごとに SharePoint Online サイトを用意する代わりに、製品ごとに Microsoft チームを使用して、永続チャットなどのチーム メンバーとの共同作業をサポートし、チームの [**ファイル**] タブを使用してドキュメントを管理できます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-136">Instead of having a SharePoint Online site per product, the manufacturing company in this scenario could use a Microsoft Team per product that would support collaboration with members of the team, such as persistent chat and use the **Files** tab in the team for document management.</span></span> <span data-ttu-id="9c4f5-137">この記事ではドキュメントのみに重点を置いているため、サイトのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-137">In this article we only focus on documents, therefore we will only use a site.</span></span>

<span data-ttu-id="9c4f5-138">回転ウィジェット製品のドキュメント ライブラリのビューを次に示します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-138">Here's a view of the document library for the Spinning Widget product:</span></span>

![回転ウィジェットのドキュメント ライブラリ](../media/SPRetention4.png)

<span data-ttu-id="9c4f5-140">ドキュメント管理用に基本的な情報アーキテクチャが用意されているので、ドキュメントのメタデータと分類を使用するドキュメントの保持および廃棄戦略を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-140">Now that we have the basic information architecture in place for document management, let's look at the retention and disposal strategy of the documents that use the metadata and classification of documents.</span></span>

## <a name="retention-and-disposition"></a><span data-ttu-id="9c4f5-141">保持および廃棄</span><span class="sxs-lookup"><span data-stu-id="9c4f5-141">Retention and disposition</span></span>

<span data-ttu-id="9c4f5-142">製造会社のコンプライアンスおよびデータ ガバナンスのポリシーは、データの保存および廃棄方法を規定しています。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-142">The manufacturing company's compliance and data governance policies dictate the way data is preserved and disposed of.</span></span> <span data-ttu-id="9c4f5-143">製品に関連するドキュメントは、製品を製造する期間、およびその後の一定期間保管する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-143">Product-related documents must be kept for as long as the product is manufactured, and for a certain period after that.</span></span> <span data-ttu-id="9c4f5-144">この期間は、製品の仕様、契約、およびユーザー マニュアルによって異なります。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-144">This period is different for product specifications, agreements, and user manuals.</span></span> <span data-ttu-id="9c4f5-145">次の表は、保持と廃棄の要件を示しています。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-145">The following table indicates the retention and disposition requirements:</span></span>

| <span data-ttu-id="9c4f5-146">**ドキュメントの種類**</span><span class="sxs-lookup"><span data-stu-id="9c4f5-146">**Document type**</span></span>          | <span data-ttu-id="9c4f5-147">**保持**</span><span class="sxs-lookup"><span data-stu-id="9c4f5-147">**Retention**</span></span>                          | <span data-ttu-id="9c4f5-148">**廃棄**</span><span class="sxs-lookup"><span data-stu-id="9c4f5-148">**Disposition**</span></span>                              |
| -------------------------- | -------------------------------------- | -------------------------------------------- |
| <span data-ttu-id="9c4f5-149">製品の仕様</span><span class="sxs-lookup"><span data-stu-id="9c4f5-149">Product specification</span></span>      | <span data-ttu-id="9c4f5-150">生産中止後 5 年</span><span class="sxs-lookup"><span data-stu-id="9c4f5-150">5 years after cessation of production</span></span>  | <span data-ttu-id="9c4f5-151">削除</span><span class="sxs-lookup"><span data-stu-id="9c4f5-151">Delete</span></span>                                       |
| <span data-ttu-id="9c4f5-152">製品契約</span><span class="sxs-lookup"><span data-stu-id="9c4f5-152">Product agreement</span></span>          | <span data-ttu-id="9c4f5-153">生産中止後 10 年</span><span class="sxs-lookup"><span data-stu-id="9c4f5-153">10 years after cessation of production</span></span> | <span data-ttu-id="9c4f5-154">レビュー</span><span class="sxs-lookup"><span data-stu-id="9c4f5-154">Review</span></span>                                       |
| <span data-ttu-id="9c4f5-155">ユーザー マニュアル</span><span class="sxs-lookup"><span data-stu-id="9c4f5-155">User manual</span></span>                | <span data-ttu-id="9c4f5-156">生産中止後 5 年</span><span class="sxs-lookup"><span data-stu-id="9c4f5-156">5 years after cessation of production</span></span>  | <span data-ttu-id="9c4f5-157">削除</span><span class="sxs-lookup"><span data-stu-id="9c4f5-157">Delete</span></span>                                       |
| <span data-ttu-id="9c4f5-158">他のすべての種類のドキュメント</span><span class="sxs-lookup"><span data-stu-id="9c4f5-158">All other types of documents</span></span> | <span data-ttu-id="9c4f5-159">他のドキュメントを積極的に保持しない</span><span class="sxs-lookup"><span data-stu-id="9c4f5-159">Don't actively retain other documents</span></span>  | <span data-ttu-id="9c4f5-160">ドキュメントが 3 年以上経過したときに削除する<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9c4f5-160">Delete when document is older than 3 years<sup>\*</sup></span></span>  |
|||

> [!NOTE]
> <span data-ttu-id="9c4f5-161"><sup>\*</sup> 過去 3 年以内に変更されていないドキュメントは、3 年以上前のものと見なされます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-161"><sup>\*</sup> A document is considered older than 3 years if it hasn't been modified within the last 3 years.</span></span>

<span data-ttu-id="9c4f5-162">セキュリティとコンプライアンス センターを使用して、次の保持ラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-162">Using the security and compliance center, we create the following retention labels:</span></span>

  - <span data-ttu-id="9c4f5-163">製品の仕様</span><span class="sxs-lookup"><span data-stu-id="9c4f5-163">Product Specification</span></span>

  - <span data-ttu-id="9c4f5-164">製品の契約</span><span class="sxs-lookup"><span data-stu-id="9c4f5-164">Product Agreement</span></span>

  - <span data-ttu-id="9c4f5-165">ユーザー マニュアル</span><span class="sxs-lookup"><span data-stu-id="9c4f5-165">User Manual</span></span>

<span data-ttu-id="9c4f5-166">この記事では、製品の仕様の保持ラベルを作成して自動適用する方法のみを示します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-166">In this article, we only show how to create and auto-apply the Product Specification retention label.</span></span> <span data-ttu-id="9c4f5-167">完全なシナリオを実装するには、他の 2 つのドキュメントの種類の保持ラベルを作成して自動適用します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-167">To implement the complete scenario, you would create and auto-apply retention labels for the other two document types.</span></span>

### <a name="settings-for-the-product-specification-retention-label"></a><span data-ttu-id="9c4f5-168">製品の仕様の保持ラベルの設定</span><span class="sxs-lookup"><span data-stu-id="9c4f5-168">Settings for the Product Specification retention label</span></span>

<span data-ttu-id="9c4f5-169">製品の仕様の保持ラベルの[ファイル計画](file-plan-manager.md)は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-169">Here's the [file plan](file-plan-manager.md) for the Product Specification retention label:</span></span> 

- <span data-ttu-id="9c4f5-170">**名前:** 製品の仕様</span><span class="sxs-lookup"><span data-stu-id="9c4f5-170">**Name:** Product Specification</span></span>

- <span data-ttu-id="9c4f5-171">**管理者向けの説明:** 製品の仕様のラベル、生産中止後 5 年間保持、自動削除、イベント ベースの保持、イベントの種類は製品の中止</span><span class="sxs-lookup"><span data-stu-id="9c4f5-171">**Description for admins:** Product Specification Label, retain for five years after cessation of production, auto delete, event-based retention, event type is Product Cessation.</span></span>

- <span data-ttu-id="9c4f5-172">**ユーザーの説明:** 生産中止後 5 年間保持</span><span class="sxs-lookup"><span data-stu-id="9c4f5-172">**Description for users:** Retain for five years after cessation of production.</span></span>

- <span data-ttu-id="9c4f5-173">**保持処理:** 保持と削除</span><span class="sxs-lookup"><span data-stu-id="9c4f5-173">**Retention action:** Keep and delete</span></span>

- <span data-ttu-id="9c4f5-174">**保持期間:**  5 年 (1825 日)</span><span class="sxs-lookup"><span data-stu-id="9c4f5-174">**Retention duration:** Five years (1825 days)</span></span>

- <span data-ttu-id="9c4f5-175">**レコード ラベル:** 保持ラベルを構成して、コンテンツを[レコード](labels.md#using-retention-labels-for-records-management)として分類する(レコードとして分類されたドキュメントは、ユーザーが変更または削除することはできません)</span><span class="sxs-lookup"><span data-stu-id="9c4f5-175">**Record label**: Configure the retention label to classify content as a [record](labels.md#using-retention-labels-for-records-management) (documents that are classified as a record can't be modified or deleted by users)</span></span>

- <span data-ttu-id="9c4f5-176">**ファイル計画記述子:** (シナリオを簡素化するため、ファイル記述子は提供されません)</span><span class="sxs-lookup"><span data-stu-id="9c4f5-176">**File plan descriptors:** (for simplifying the scenario, no file descriptors are provided)</span></span>

<span data-ttu-id="9c4f5-177">次のスクリーンショットは、セキュリティおよびコンプライアンス センターで製品の仕様の[保持ラベル](labels.md)を作成するときの設定を示しています。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-177">The following screenshot shows the settings when you create the Product Specification [retention label](labels.md) in the security and compliance center.</span></span> <span data-ttu-id="9c4f5-178">保持ラベルを作成するときに、**製品の中止**のイベントの種類を作成できます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-178">You can create the **Product Cessation** event type when you create the retention label.</span></span> <span data-ttu-id="9c4f5-179">以下の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-179">See the steps below.</span></span>

![製品の仕様のラベルの保持設定](../media/SPRetention5.png)

> [!NOTE]
> <span data-ttu-id="9c4f5-181">実用的な目的のため、またドキュメントが自動的に削除されるのを 5 年間待つ必要をなくすために、テスト環境でこのシナリオを再作成する場合は、保持期間を 1 日に設定します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-181">For the practical purposes and to avoid having to wait 5 years to see a document automatically deleted, set the retention duration to 1 day if you're recreating this scenario in your test environment.</span></span>

### <a name="create-an-event-type-when-creating-a-retention-label"></a><span data-ttu-id="9c4f5-182">保持ラベルを作成するときにイベント種類を作成する</span><span class="sxs-lookup"><span data-stu-id="9c4f5-182">Create an event type when creating a retention label</span></span>

1. <span data-ttu-id="9c4f5-183">ドロップダウン リストに**基づくコンテンツの保持または削除**で、**イベント**を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-183">In the **Retain or delete content based** on dropdown list, select **an event**.</span></span>

2. <span data-ttu-id="9c4f5-184">[**イベントの種類を選択します**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-184">Select **Choose an event type**.</span></span>

   ![製品の仕様のラベルの新しいイベントの種類を作成する](../media/SPRetention6.png)

3. <span data-ttu-id="9c4f5-186">[**イベントの種類を選択します**] ページで、ここで [**新しいイベントの種類を作成できます**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-186">On the **Choose an event type** page, select **You can create new event types here**.</span></span>

4. <span data-ttu-id="9c4f5-187">[**製品の中止**] という名前のイベントの種類を作成し、説明を入力し、[**完了**] を選択して作成します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-187">Create an event type named **Product Cessation**, give a description, and select **Finish** to create it.</span></span> 

5. <span data-ttu-id="9c4f5-188">[**イベントの種類を選択します**] ページに戻り、作成した [**製品の中止**] イベントの種類を選択して、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-188">Back on the **Choose an event type** page, select the **Product Cessation** event type that you created, and then select **Add**.</span></span>

<span data-ttu-id="9c4f5-189">製品の仕様の保持ラベルの設定は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-189">Here's what the settings look like for the Product Specification retention label.</span></span> <span data-ttu-id="9c4f5-190">[**このラベルを作成**] を選択して作成します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-190">Select **Create this label** to create it.</span></span>

![新しい製品の仕様のラベルの設定](../media/SPRetention7.png)

> [!TIP]
> <span data-ttu-id="9c4f5-192">詳細な手順については、「[保持期間がイベントに基づくラベルを作成する](event-driven-retention.md#step-1-create-a-label-whose-retention-period-is-based-on-an-event)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-192">For more detailed steps, see [Create a label whose retention period is based on an event](event-driven-retention.md#step-1-create-a-label-whose-retention-period-is-based-on-an-event).</span></span>

<span data-ttu-id="9c4f5-193">保持ラベルが作成されたので、製品の仕様のコンテンツへの保持ラベルの自動適用を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-193">Now that the retention label is created, let's look at auto-applying the retention label to product specification content.</span></span>

## <a name="classifying-content-by-auto-applying-retention-labels"></a><span data-ttu-id="9c4f5-194">保持ラベルの自動適用によるコンテンツの分類</span><span class="sxs-lookup"><span data-stu-id="9c4f5-194">Classifying content by auto-applying retention labels</span></span>

<span data-ttu-id="9c4f5-195">キーワード クエリ言語 (KQL) を使用して、このシナリオ用に作成した保持ラベルを[自動適用](labels.md#applying-a-retention-label-automatically-based-on-conditions)します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-195">We're going to [auto-apply](labels.md#applying-a-retention-label-automatically-based-on-conditions) the retention labels that we've created for this scenario by using Keyword Query Language (KQL).</span></span> <span data-ttu-id="9c4f5-196">KQL は、検索クエリの作成に使用される言語です。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-196">KQL is the language used to build search queries.</span></span> <span data-ttu-id="9c4f5-197">KQL では、キーワードまたは管理プロパティを使用して検索できます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-197">In KQL, you can search by using keywords or managed properties.</span></span> <span data-ttu-id="9c4f5-198">KQL の詳細については、<https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference> を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-198">For more information about KQL, see <https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference></span></span>

<span data-ttu-id="9c4f5-199">大まかに言うと、Microsoft 365 に、「**製品の仕様**の保持ラベルを、**最終版**の**状態**および**製品の仕様**の**ドキュメントの種類**であるすべてのドキュメントに適用する」ように指示します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-199">At a high level, we want to tell Microsoft 365 to "apply the **Product Specification** retention label to all documents that have a **Status** of **Final** and a **Doc Type** of **Product Specification**.</span></span> <span data-ttu-id="9c4f5-200">**状態**および**ドキュメントの種類**は、以前に「[情報アーキテクチャ](#information-architecture)」セクションで製品のドキュメント コンテンツの種類に対して定義したサイト列であることを思い出してください。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-200">Recall that **Status** and **Doc Type** are the site columns we previously defined for Product Documentation content type in the [Information architecture](#information-architecture) section.</span></span> <span data-ttu-id="9c4f5-201">これを実現するには、検索スキーマを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-201">To achieve this, we need to configure the search schema.</span></span>

<span data-ttu-id="9c4f5-202">SharePoint がコンテンツのインデックスを作成するとき、各サイト列のクロールされたプロパティを自動的に生成します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-202">When SharePoint indexes content, it automatically generates crawled properties for each site column.</span></span> <span data-ttu-id="9c4f5-203">このシナリオでは、**ドキュメントの種類** プロパティと**状態**プロパティに関心があります。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-203">For this scenario, we're interested in the **Doc Type** and **Status** properties.</span></span> <span data-ttu-id="9c4f5-204">検索でクロールされたプロパティを作成するには、適切なコンテンツの種類を使用し、サイト列に入力されたライブラリ内のドキュメントが必要です。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-204">We need documents in the library using the right content type and have the site columns filled in, in order for search to create the crawled properties.</span></span>

<span data-ttu-id="9c4f5-205">SharePoint 管理センターで、検索構成を開き、[**検索スキーマの管理**] を選択して、クロールされたプロパティを表示および構成できます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-205">In the SharePoint admin center, we can open the Search configuration, and select **Manage Search Schema** to view and configure the crawled properties.</span></span>

![検索スキーマのクロールされたプロパティ](../media/SPRetention8.png)

<span data-ttu-id="9c4f5-207">[**クロールされたプロパティ**] ボックスに**状態**を入力し、緑色の矢印を選択すると、次のような結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-207">If we type **status** in the **Crawled properties** box, and select the green arrow, we should see a result like this:</span></span>

![ows_Status のクロールされたプロパティ](../media/SPRetention9.png)

<span data-ttu-id="9c4f5-209">**ows\_\_Status** (二重アンダースコアに注意) のプロパティは、我々にとって興味のあるものです。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-209">The property **ows\_\_Status** (notice the double underscore) is the one that interests us.</span></span> <span data-ttu-id="9c4f5-210">これは、生産ドキュメントのコンテンツの種類の**状態**プロパティにマップします。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-210">This maps to the **Status** property of the Production Document content type.</span></span>

<span data-ttu-id="9c4f5-211">**ows\_doc**と入力して緑色の矢印を選択すると、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-211">Now if we type **ows\_doc** and select the green arrow we should see something like this:</span></span>

![ows_Doc_Type のクロールされたプロパティ](../media/SPRetention10.png)

<span data-ttu-id="9c4f5-213">プロパティ **ows\_Doc\_x0020\_Type** は、興味のある 2 番目のプロパティです。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-213">The property **ows\_Doc\_x0020\_Type** is the second property that interests us.</span></span> <span data-ttu-id="9c4f5-214">これは、生産ドキュメントのコンテンツの種類の**ドキュメントの種類**プロパティにマップします。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-214">This maps to the **Doc Type** property of the Production Document content type.</span></span>

> [!TIP]
> <span data-ttu-id="9c4f5-215">このシナリオのクロールされたプロパティの名前を識別するには、生産ドキュメントを含むドキュメント ライブラリに移動してから、ライブラリ設定に移動します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-215">To identify the name of a crawled property for this scenario, go the document library that contains the production documents and then go to the library settings.</span></span> <span data-ttu-id="9c4f5-216">[**列**] で、列の名前 (**状態**や**ドキュメントの種類**など) を選択して、サイトの列ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-216">In the **Columns**, select the name of the column (for example, **Status** or **Doc Type**) to open the site column page.</span></span> <span data-ttu-id="9c4f5-217">そのページの URL の**フィールド** パラメーターには、フィールドの名前が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-217">The **Field** parameter in the URL for that page contains the name of the field.</span></span> <span data-ttu-id="9c4f5-218">先頭に「ows_」が付いたこのフィールド名は、クロールされたプロパティの名前です。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-218">This field name, prefixed with "ows_", is the name of the crawled property.</span></span> <span data-ttu-id="9c4f5-219">たとえば、URL `https://tenantname.sharepoint.com/sites/SpinningWidget/_layouts/15/FldEdit.aspx?List=%7BC38C2F45-3BD6-4C3B-AA3B-EF5DF6B3D172%7D&Field=_Status` は **ows\_\_Status** のクロールされたプロパティに対応します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-219">For example, the URL `https://tenantname.sharepoint.com/sites/SpinningWidget/_layouts/15/FldEdit.aspx?List=%7BC38C2F45-3BD6-4C3B-AA3B-EF5DF6B3D172%7D&Field=_Status` corresponds to the **ows\_\_Status** crawled property.</span></span>

<span data-ttu-id="9c4f5-220">探しているクロールされたプロパティが SharePoint 管理センターの [検索スキーマの管理] セクションに表示されない場合、次のいずれかの理由が考えられます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-220">If the crawled properties you're looking for don't appear in the Manage Search Schema section in the SharePoint admin center, it could be for one of the following reasons:</span></span>

- <span data-ttu-id="9c4f5-221">ドキュメントには索引が作成されていません。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-221">The documents haven't been indexed.</span></span> <span data-ttu-id="9c4f5-222">[ドキュメント ライブラリ設定]、[詳細設定] の順に移動し、ライブラリのインデックスを強制的に再作成できます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-222">You can force a re-index of the library by going to Document library settings > Advanced Settings.</span></span>

- <span data-ttu-id="9c4f5-223">ドキュメント ライブラリが最新のサイトにある場合は、SharePoint 管理者もサイト コレクション管理者であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-223">If the document library is in a modern site, make sure that the SharePoint admin is also a site collection admin.</span></span>

<span data-ttu-id="9c4f5-224">クロールされ管理されたプロパティの詳細については、「[SharePoint Server で自動的に作成される管理プロパティ](https://docs.microsoft.com/sharepoint/technical-reference/automatically-created-managed-properties-in-sharepoint)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-224">For more information about crawled and managed properties, see [Automatically created managed properties in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/automatically-created-managed-properties-in-sharepoint).</span></span>

### <a name="mapping-crawled-properties-to-pre-defined-managed-properties"></a><span data-ttu-id="9c4f5-225">クロールされたプロパティを事前定義された管理プロパティにマッピングする</span><span class="sxs-lookup"><span data-stu-id="9c4f5-225">Mapping crawled properties to pre-defined managed properties</span></span>

<span data-ttu-id="9c4f5-226">KQL は、検索クエリでクロールされたプロパティを使用できません。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-226">KQL can't use crawled properties in search queries.</span></span> <span data-ttu-id="9c4f5-227">管理プロパティを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-227">It has to use a managed property.</span></span> <span data-ttu-id="9c4f5-228">通常の検索シナリオでは、管理プロパティを作成し、必要なクロールされたプロパティにマップします。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-228">In a normal search scenario, we create a managed property and map it to the crawled property that we need.</span></span> <span data-ttu-id="9c4f5-229">ただし、保持ラベルを自動適用する場合は、KQL で事前定義された管理プロパティのみを指定でき、カスタム管理プロパティは指定できません。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-229">However, for auto-applying retention labels, you can only specify in KQL pre-defined managed properties and not custom managed properties.</span></span> <span data-ttu-id="9c4f5-230">使用可能な文字列 RefinableString00 から RefinableString199 に対して、システム内に既に作成された定義済みの管理プロパティのセットがあります。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-230">There's a set of predefined managed properties already created in the system for string RefinableString00 to RefinableString199 that can be used.</span></span> <span data-ttu-id="9c4f5-231">完全なリストについては、「[既定の未使用の管理プロパティ](https://docs.microsoft.com/sharepoint/manage-search-schema#default-unused-managed-properties)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-231">For a complete list, see [Default unused managed properties](https://docs.microsoft.com/sharepoint/manage-search-schema#default-unused-managed-properties).</span></span> <span data-ttu-id="9c4f5-232">これらの既定の管理プロパティは、通常、絞り込み検索の条件を定義するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-232">These default managed properties are typically used for defining search refiners.</span></span>

<span data-ttu-id="9c4f5-233">KQL クエリが機能し、正しい保持ラベルを製品ドキュメント コンテンツに自動的に適用するために、クロールされたプロパティ **ows\_Doc\_x0020\_Type** および **ows\_\_Status** を 2 つの絞り込み可能な管理プロパティにマップします。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-233">For the KQL query to work and automatically apply the correct retention label to product document content, we map the crawled properties **ows\_Doc\_x0020\_Type** and **ows\_\_Status** to two refinable managed properties.</span></span> <span data-ttu-id="9c4f5-234">このシナリオのテスト環境では、**RefinableString00** と **RefinableString01** は使用されていません。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-234">In our test environment for this scenario, **RefinableString00** and **RefinableString01** aren't being used.</span></span> <span data-ttu-id="9c4f5-235">SharePont 管理センターの [**検索スキーマの管理**] で [**管理プロパティ**] を見て、これを決定しました。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-235">We determined this by looking at **Managed Properties** in the **Manage Search Schema** in the SharePont admin center.</span></span>

![検索スキーマの管理されたプロパティ](../media/SPRetention12.png)

<span data-ttu-id="9c4f5-237">前のスクリーンショットの [**マップ先のクロールされたプロパティ**] 列は空であることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-237">Notice that the **Mapped Crawled Properties** column in the previous screenshot is empty.</span></span>

<span data-ttu-id="9c4f5-238">**ows\_Doc\_x0020\_Type** のクロールされたプロパティをマップするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-238">To map the **ows\_Doc\_x0020\_Type** crawled property, do the following:</span></span>

1. <span data-ttu-id="9c4f5-239">[**管理プロパティ**] フィルター ボックスに **RefinableString00** と入力し、緑色の矢印を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-239">In the **Managed property** filter box, type **RefinableString00** and select the green arrow.</span></span>

2. <span data-ttu-id="9c4f5-240">結果一覧で、**RefinableString00** リンクを選択し、[**クロールされたプロパティへのマッピング**] セクションまで下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-240">In the results list, select the **RefinableString00** link, and then scroll down to the **Mappings to crawled properties** section.</span></span>  

3. <span data-ttu-id="9c4f5-241">[**マッピングの追加**] を選択し、[**クロールされたプロパティの選択**] ウィンドウの [**クロールされたプロパティ名の検索**] ボックスに **ows\_Doc\_x0020\_Type** と入力します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-241">Select **Add a Mapping**, and then type **ows\_Doc\_x0020\_Type** in the **Search for a crawled property name** box in the **Crawled property selection** window.</span></span> <span data-ttu-id="9c4f5-242">[**検索**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-242">Select **Find**.</span></span>  

4. <span data-ttu-id="9c4f5-243">結果リストで、**ows\_Doc\_x0020\_Type** を選択し、[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-243">In the results list, select **ows\_Doc\_x0020\_Type** and then select **OK**.</span></span>

   <span data-ttu-id="9c4f5-244">[**マップ先のクロールされたプロパティ**] セクションに、次のスクリーンショットのようなものが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-244">In the **Mapped Crawled Properties** section, you should see something similar to this screenshot:</span></span>

   ![[マップ先のクロールされたプロパティ] セクションで [マッピングの追加] を選択する](../media/SPRetention13.png)

5. <span data-ttu-id="9c4f5-246">ページの一番下までスクロールし、[**OK**] を選択してマッピングを保存します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-246">Scroll to the bottom of the page and select **OK** to save the mapping.</span></span>

<span data-ttu-id="9c4f5-247">この同じ手順を繰り返して、RefinableString01 と ows\_\_Status をマップします。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-247">Repeat this same procedure to map RefinableString01 and ows\_\_Status.</span></span>

<span data-ttu-id="9c4f5-248">これで、2 つのクロールされたプロパティにマップされた 2 つの管理プロパティが必要になります。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-248">Now you should have two managed properties mapped to the two crawled properties:</span></span>

![クロールされたプロパティにマップされた管理プロパティ](../media/SPRetention14.png)

<span data-ttu-id="9c4f5-250">エンタープライズ検索を実行して、これらすべてが正しく設定されていることを確認しましょう。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-250">Let's verify that all this is set up correctly by running an enterprise search.</span></span> <span data-ttu-id="9c4f5-251">ブラウザーで、https://yourtenant.sharepoint.com/search に移動します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-251">In a browser, go to https://yourtenant.sharepoint.com/search.</span></span> <span data-ttu-id="9c4f5-252">検索ボックスに **RefinableString00:"Product Specification"** と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-252">In the search box, type **RefinableString00:"Product Specification"** and press enter.</span></span> <span data-ttu-id="9c4f5-253">これにより、製品の仕様が**ドキュメントの種類**であるすべてのドキュメントが返されます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-253">This should return all documents that have Product Specification as **Doc Type**.</span></span>

<span data-ttu-id="9c4f5-254">検索ボックスに、**RefinableString00:"Product Specification" AND RefinableString01:Final** と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-254">Now in the search box, type **RefinableString00:"Product Specification" AND RefinableString01:Final** and press enter.</span></span> <span data-ttu-id="9c4f5-255">これにより、**ドキュメントの種類**として製品の仕様を持ち、状態が**最終版**であるすべてのドキュメントが返されます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-255">This should return all documents that have Product Specification as **Doc Type** and a Status of **Final**.</span></span>

### <a name="creating-the-auto-apply-label-policies"></a><span data-ttu-id="9c4f5-256">自動適用ラベル ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="9c4f5-256">Creating the auto-apply label policies</span></span>

<span data-ttu-id="9c4f5-257">KQL クエリが正しく機能していることを確認したので、KQL クエリを使用して適切なドキュメントに製品の仕様の保持ラベルを自動適用するラベル ポリシーを作成しましょう。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-257">Now that we verified that the KQL query is working correctly, let's create the label policy that uses a KQL query to auto-apply the Product Specification retention label to the appropriate documents.</span></span>

1. <span data-ttu-id="9c4f5-258">[セキュリティおよびコンプライアンス センター](https://protection.office.com)で、[**分類**] > [**保持ラベル**] に移動し、[**ラベルの自動適用**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-258">In the [security and compliance center](https://protection.office.com), go to **Classification** > **Retention labels**, and then select **Auto-apply a label**.</span></span> 

   ![[ラベル] ページで [ラベルの自動適用] を選択する](../media/SPRetention16.png)

2. <span data-ttu-id="9c4f5-260">[**自動適用するラベルの選択**] ウィザード ページで、[**自動適用するラベルの選択**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-260">On the **Choose a label to auto-apply** wizard page, select **Choose a label to auto-apply**.</span></span>

3. <span data-ttu-id="9c4f5-261">ラベル リストで [**製品の仕様**] を選択し、[**追加**]、[**次へ**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-261">In the list of labels, select **Product Specification**, select **Add**, and then select **Next**.</span></span>

4. <span data-ttu-id="9c4f5-262">[**特定の単語または語句を含むコンテンツにラベルを適用する**] を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-262">Select **Apply label to content that contains specific words or phrases, or properties**, and then select **Next**.</span></span>

   ![特定の単語、語句、またはプロパティを含むコンテンツに [ラベルを適用する] を選択する](../media/SPRetention17.png)

   <span data-ttu-id="9c4f5-264">次の手順では、前のセクションでテストしたものと同じ KQL 検索クエリを提供します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-264">In the next step, you will provide the same KQL search query that we tested in the previous section.</span></span> <span data-ttu-id="9c4f5-265">お気付きのとおり、このクエリは、状態が最終のすべての製品の仕様を返しました。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-265">As you recall, this query returned all Product Specification documents that have a status of Final.</span></span> <span data-ttu-id="9c4f5-266">ラベル ポリシーでこの同じクエリを使用すると、製品の仕様の保持ラベルが、この検索クエリに一致するすべてのドキュメントに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-266">The result of using this same query in the label policy means that the Product Specification retention label will be automatically applied to all documents that match this search query.</span></span>

5. <span data-ttu-id="9c4f5-267">[**キーワード クエリ エディター**] ボックスに、**RefinableString00:"Product Specification" AND RefinableString01:Final** と入力し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-267">In the **Keyword query editor** box, type **RefinableString00:"Product Specification" AND RefinableString01:Final**, and then select **Next**.</span></span>

   ![[キーワード クエリ エディター] ボックスでクエリを指定する](../media/SPRetention19.png)

6. <span data-ttu-id="9c4f5-269">ラベル ポリシーの名前 (例: **製品の仕様のラベルの自動適用**) とオプションの説明を入力し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-269">Type a name (for example, **Auto apply Product Specification label**) and an optional description for the label policy, and then select **Next**.</span></span> 

7. <span data-ttu-id="9c4f5-270">[**場所の選択**] ウィザード ページで、ポリシーを適用するコンテンツの場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-270">On the **Choose locations** wizard page, you select the content locations that you want to apply the policy to.</span></span> <span data-ttu-id="9c4f5-271">このシナリオでは、すべての生産ドキュメントが SharePoint ドキュメント ライブラリにのみ保存されるため、SharePoint の場所にのみポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-271">For this scenario, we apply the policy only to SharePoint locations because all production documents are stored only in SharePoint document libraries.</span></span> <span data-ttu-id="9c4f5-272">[**特定の場所を選択**] を選択して、Exchange メール、OneDrive アカウント、および Microsoft 365 グループの状態をオフに切り替え、SharePoint サイトの状態がオンに切り替えられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-272">Select **Let me choose specific locations**, toggle the status for Exchange email, OneDrive accounts, and Microsoft 365 Groups to off and make sure the status for SharePoint sites is toggled on.</span></span> 

    ![ラベルを自動適用する特定のサイトを選択する](../media/SPRetentionSPlocations.png)

   > [!TIP]
   > <span data-ttu-id="9c4f5-274">ポリシーをすべての SharePoint サイトに適用する代わりに、[**サイトの選択**] を選択して、特定の SharePoint サイトの URL を追加できます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-274">Instead of applying the policy to all SharePoint sites, you can select **Choose sites** and add the URLs for specific SharePoint sites.</span></span>

8. <span data-ttu-id="9c4f5-275">[**次へ**] を選択して、[**設定を確認**] ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-275">Select **Next** to display the **Review your settings** page.</span></span> 

    ![ラベルを自動適用するための設定](../media/SPRetention18.png)

9. <span data-ttu-id="9c4f5-277">[**自動適用**] を選択して、ラベル ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-277">Select **Auto-apply** to create the label policy.</span></span> <span data-ttu-id="9c4f5-278">提供した KQL 検索クエリに一致するすべてのドキュメントに製品の仕様のラベルを自動的に適用するには、最大 7 日かかります。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-278">It takes up to seven days to automatically apply the Product Specification label to all documents that match the KQL search query that you provided.</span></span>

### <a name="verifying-the-retention-label-was-automatically-applied"></a><span data-ttu-id="9c4f5-279">保持ラベルが自動的に適用されたことを確認する</span><span class="sxs-lookup"><span data-stu-id="9c4f5-279">Verifying the retention label was automatically applied</span></span>

<span data-ttu-id="9c4f5-280">7 日後、セキュリティおよびコンプライアンス センターの [[ラベル アクティビティ エクスプローラー](view-label-activity-for-documents.md)] を使用して、作成したラベル ポリシーがこのシナリオの保持ラベルを製品ドキュメントに自動的に適用したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-280">After seven days, use the [Label activity explorer](view-label-activity-for-documents.md) in the security and compliance center to see that the label policy that we created has automatically applied the retention labels in this scenario to the product documents.</span></span> <span data-ttu-id="9c4f5-281">次のスクリーンショットでは、保持ラベルは製品の契約およびユーザー マニュアルにも適用されています。ただし、この記事では保持ラベルとラベル ポリシーの作成については説明されていません。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-281">In the following screenshot, retention labels have also been applied to product agreements and user manuals, even though we didn't cover creating those retention labels and label policies in this article.</span></span>

![ラベル アクティビティ エクスプローラーを使用して、ラベルが自動適用されたことを確認する](../media/SPRetention20.png)

<span data-ttu-id="9c4f5-283">もう 1 つの検証手順は、ドキュメント ライブラリ内のドキュメントのプロパティを調べることです。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-283">Another verification step is to look at the properties of the document in the Document Library.</span></span> <span data-ttu-id="9c4f5-284">情報パネルで、選択したドキュメントに保持ラベルが適用されていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-284">In the information panel, you can see that the retention label is applied to a selected document.</span></span>

![ドキュメント ライブラリのドキュメント プロパティを見て、ラベルが適用されたことを確認する](../media/SPRetention21.png)

<span data-ttu-id="9c4f5-286">保持ラベルはドキュメントに自動適用されていて、ドキュメントをレコードとして宣言するように保持ラベルが構成されているため、ドキュメントは削除されません。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-286">Because the retention labels have been auto-applied to documents, the documents are protected from being deleted because the retention label was configured to declare the documents as records.</span></span> <span data-ttu-id="9c4f5-287">この保護の例として、これらのドキュメントのいずれかを削除しようとすると、次のスクリーンショットに示すエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-287">As an example of this protection, we receive an error message shown in the following screenshot when we try to delete one of these documents.</span></span>

![ラベルがドキュメント レコードを宣言しているため、ドキュメントを削除できません](../media/SPRetention22.png)

## <a name="generating-the-events-that-trigger-the-start-of-the-retention-period"></a><span data-ttu-id="9c4f5-289">保持期間の開始をトリガーするイベントの生成</span><span class="sxs-lookup"><span data-stu-id="9c4f5-289">Generating the events that trigger the start of the retention period</span></span>

<span data-ttu-id="9c4f5-290">保持ラベルが自動的に正常に適用されたので、特定の製品の生産終了を示すイベントに注目しましょう。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-290">Now that the retention labels were successfully automatically applied, let's focus on the event that will indicate the end of production for a particular product.</span></span> <span data-ttu-id="9c4f5-291">このイベントが発生すると、ドキュメントに自動適用される保持ラベルで定義された保持期間の開始がトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-291">When this event occurs, it triggers the beginning of the retention period defined in retention labels auto-applied to documents.</span></span> <span data-ttu-id="9c4f5-292">たとえば、製品の仕様の場合、「生産終了」イベントがトリガーされると、5 年間の保持期間が開始されます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-292">For example, for product specification documents, the five-year retention period begins when the "end of production" event is triggered.</span></span>

<span data-ttu-id="9c4f5-293">セキュリティおよびコンプライアンス センターで ([**レコード管理**] > [**イベント**] に移動して) イベントを手動で作成し、イベントの種類を選択し、正しい資産 ID を設定してイベントの日付を入力できます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-293">You can manually create the event in the security and compliance center by going to **Records Managements** > **Events** and choosing the event type, setting the correct Asset Ids, and entering a date for the event.</span></span> <span data-ttu-id="9c4f5-294">詳細については、「[イベント ベースの保持の概要](event-driven-retention.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-294">For more information, see [Overview of event-driven retention](event-driven-retention.md).</span></span>

<span data-ttu-id="9c4f5-295">このシナリオでは、外部の生産システムからイベントを生成することにより、イベントを自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-295">For this scenario, we'll automatically create the event by generating it from an external production system.</span></span> <span data-ttu-id="9c4f5-296">この場合、イベントを生成するシステムは、製品が生産中かどうかを示す単純な SharePoint リストと、リストに関連付けられてイベントをトリガーする [Microsoft Flow](https://docs.microsoft.com/flow/getting-started) です。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-296">In this case, the system that generates the event is a simple SharePoint list that indicates whether a product is in production and a [Microsoft Flow](https://docs.microsoft.com/flow/getting-started) that's associated with the list and will trigger the event.</span></span> <span data-ttu-id="9c4f5-297">実際のシナリオでは、HR や CRM システムなど、イベントを生成する任意のシステムを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-297">In a real-world scenario, it could be any system that generates the event, such as an HR or CRM system.</span></span> <span data-ttu-id="9c4f5-298">Flow には、Exchange、SharePoint、Teams、Dynamics 365 などの Microsoft 365 ワークロード、および Twitter、Box、Salesforce、Workdays などのサード パーティ アプリ向けのすぐに使用できる多くの操作と文書パーツが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-298">Flow contains many ready-to-use interactions and building block for Microsoft 365 workloads such as Exchange, SharePoint, Teams, and Dynamics 365, and third-party apps such as Twitter, Box, Salesforce, and Workdays.</span></span> <span data-ttu-id="9c4f5-299">これにより、Flow をこれらのシステムに簡単に統合できます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-299">This makes it easy to integrate Flow with these systems.</span></span> <span data-ttu-id="9c4f5-300">詳細については、「[イベント ベースの保持を自動化する](automate-event-driven-retention.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-300">For more information, see [Automate event-driven retention](automate-event-driven-retention.md).</span></span>

<span data-ttu-id="9c4f5-301">次のスクリーンショットは、イベントのトリガーに使用される SharePoint リストを示しています。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-301">The following screenshot shows the SharePoint list that will be used the trigger the event:</span></span> 

![保持イベントをトリガーするために使用されるリスト](../media/SPRetention23.png)

<span data-ttu-id="9c4f5-303">現在生産中の製品は 2 つあり、[**生産中**] 列の [**はい**] の値で示されます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-303">There are two products currently in production, which is indicated by the value of **Yes** in the **In Production** column.</span></span> <span data-ttu-id="9c4f5-304">製品のこの列の値が [**いいえ**] に設定されている場合、リストに関連付けられたフローは自動的にイベントを生成します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-304">When the value in this column is set to **No** for a product, the flow associated with the list will automatically generate the event.</span></span> <span data-ttu-id="9c4f5-305">これにより、対応する製品ドキュメントに自動適用された保持ラベルの保持期間の開始がトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-305">This in turn triggers the start of the retention period for the retention label that was auto-applied to the corresponding product documents.</span></span>

<span data-ttu-id="9c4f5-306">このシナリオでは、次のフローを使用してイベントをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-306">For this scenario, we use the following flow to trigger the event:</span></span>

![イベントをトリガーするフローの構成](../media/SPRetention24.png)

<span data-ttu-id="9c4f5-308">このフローを作成するには、SharePoint コネクターから開始し、「**アイテムが作成または変更されたとき**」トリガーを選択します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-308">To create this flow, start from a SharePoint connector and select the **When an item is created or modified** trigger.</span></span> <span data-ttu-id="9c4f5-309">サイト アドレスとリスト名を指定し、[**生産中**] リスト列の値が [**いいえ**] に設定されている (または条件カードで false に等しい) ときに基づいて条件を追加します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-309">Specify the site address and list name, and then add a condition based on when the **In Production** list column value is set to **No** (or equal to false in the condition card).</span></span> <span data-ttu-id="9c4f5-310">次に、組み込みの HTTP テンプレートに基づいてアクションを追加します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-310">Then add an action based on the built-in HTTP template.</span></span> <span data-ttu-id="9c4f5-311">次のセクションの値を使用して、HTTP アクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-311">Use the values in the following section to configure the HTTP action.</span></span> <span data-ttu-id="9c4f5-312">以下のセクションから URI および本文プロパティの値をコピーして、テンプレートに貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-312">You can copy the values for the URI and Body properties from the section below and then paste them into the template.</span></span>

- <span data-ttu-id="9c4f5-313">**方法**: 投稿</span><span class="sxs-lookup"><span data-stu-id="9c4f5-313">**Method**: POST</span></span>
- <span data-ttu-id="9c4f5-314">**URI**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="9c4f5-314">**URI**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>
- <span data-ttu-id="9c4f5-315">**ヘッダー**: キー = Content-Type、値 = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="9c4f5-315">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>
- <span data-ttu-id="9c4f5-316">**本文**:</span><span class="sxs-lookup"><span data-stu-id="9c4f5-316">**Body**:</span></span>
    
    ```HTML
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

<span data-ttu-id="9c4f5-317">次のセクションに、このシナリオ専用に構成する必要があるアクションの*本文*プロパティ内のパラメーターを示します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-317">The following section describes the parameters within the *Body* property of the action that must be configured specifically for this scenario.</span></span>

- <span data-ttu-id="9c4f5-318">**名前**: このパラメーターは、セキュリティおよびコンプライアンス センターで作成されるイベントの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-318">**Name**: This parameter specifies the name of the event that will be created in the security and compliance center.</span></span> <span data-ttu-id="9c4f5-319">このシナリオでは、名前は「Cessation Production xxx」です。xxx は、前に作成した ProductName 管理プロパティの値です。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-319">For this scenario, the name is "Cessation Production xxx", where xxx is the value of the ProductName managed property that we created earlier.</span></span>
- <span data-ttu-id="9c4f5-320">**EventType**: このパラメーターの値は、作成されたイベントが適用されるイベントの種類に対応します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-320">**EventType**: The value for this parameter corresponds to the event type that the created event will apply to.</span></span> <span data-ttu-id="9c4f5-321">このイベントの種類は、保持ラベルを作成したときに定義されました。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-321">This event type was defined when you created the retention label.</span></span> <span data-ttu-id="9c4f5-322">このシナリオでは、イベントの種類は「製品の中止」です。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-322">For this scenario, the event type is "Product Cessation".</span></span>
- <span data-ttu-id="9c4f5-323">**SharePointAssetIdQuery**: このパラメーターは、イベントの資産 ID を定義します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-323">**SharePointAssetIdQuery**:This parameter defines the Asset Id for the event.</span></span> <span data-ttu-id="9c4f5-324">イベント ベースの保持には、ドキュメントの一意の識別子が必要です。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-324">Event-based retention needs a unique identifier for the document.</span></span> <span data-ttu-id="9c4f5-325">資産 ID を使用して、特定のイベントが適用されるドキュメントを識別できます。または、このシナリオの場合と同様に、独自の製品名であるメタデータ列を特定できます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-325">We can use Asset Ids to identify the documents that a particular event applies to, or as we do for this scenario, a metadata column, our own Product Name.</span></span> <span data-ttu-id="9c4f5-326">これを行うには、KQL クエリで使用できる ProductName という名前の新しい管理プロパティを作成する必要があります (または、新しい管理プロパティを作成する代わりに RefinableString00 を使用することもできます)。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-326">To do  this, we have to create a new managed property named ProductName that can be used in the KQL query (or we could have used RefinableString00 instead of creating a new managed property).</span></span> <span data-ttu-id="9c4f5-327">また、この新しい管理プロパティを ows_Product_x0020_Name のクロールされたプロパティにマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-327">We also need to map this new managed property to the ows_Product_x0020_Name crawled property.</span></span> <span data-ttu-id="9c4f5-328">この管理プロパティのスクリーンショットを次に示します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-328">Here's a screenshot of this managed property.</span></span>

    ![保持管理プロパティ](../media/SPRetention25.png)

- <span data-ttu-id="9c4f5-330">**EventDateTime**: このパラメーターは、イベントが発生する日付を定義します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-330">**EventDateTime**: This parameter defines the date the event occurs.</span></span> <span data-ttu-id="9c4f5-331">現在の日付形式を使用します: *formatDateTime(utcNow(),'yyyy-MM-dd'*)</span><span class="sxs-lookup"><span data-stu-id="9c4f5-331">Use the current date format: *formatDateTime(utcNow(),'yyyy-MM-dd'*)</span></span>

### <a name="putting-it-all-together"></a><span data-ttu-id="9c4f5-332">すべてをまとめる</span><span class="sxs-lookup"><span data-stu-id="9c4f5-332">Putting it all together</span></span>

<span data-ttu-id="9c4f5-333">保持ラベルが作成および自動適用され、フローが構成および作成されたので、製品リストの回転ウィジェットの製品の [**生産中**] 列の値が [**はい**] から [**いいえ**] に変更されると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-333">Now that the retention label is created and auto-applied and the flow is configured and created, here's what happens when the value in the **In Production** column for the Spinning Widget product in the Products list is changed from **Yes** to **No**.</span></span> <span data-ttu-id="9c4f5-334">フローがトリガーされ、イベントが作成されます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-334">The flow is triggered and creates the event.</span></span> <span data-ttu-id="9c4f5-335">セキュリティおよびコンプライアンス センターでこのイベントを表示するには、[**レコード管理**] > [**イベント**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-335">To see this event in the security and compliance center, go to **Records management** > **Events**.</span></span>

![セキュリティおよびコンプライアンス センターの [イベント] ページに表示されるフローによってトリガーされたイベント](../media/SPRetention28.png)

<span data-ttu-id="9c4f5-337">イベントを選択して、ポップアップ ページで詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-337">Select the event to view the details on the flyout page.</span></span> <span data-ttu-id="9c4f5-338">イベントが作成された場合でも、イベントの状態の詳細には、SharePoint サイトまたはドキュメントが処理されていないことが示されます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-338">Notice that even though the event is created, the details in the event status show that no SharePoint sites or documents have been processed.</span></span>

![イベントの詳細](../media/SPRetention29.png)

<span data-ttu-id="9c4f5-340">しかし、しばらくすると、イベントの状態のセクションに、SharePoint サイトと SharePoint ドキュメントが処理されたことが示されます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-340">But after some time, the event status section shows that for a SharePoint site and a SharePoint document have been processed.</span></span>  

![イベントの詳細は、ドキュメントが処理されたことを示します](../media/SPRetention31.png)
 
<span data-ttu-id="9c4f5-342">これは、生産中止の回転ウィジェット イベントのイベント日付に基づいて、回転ウィジェットの製品ドキュメントに適用されるラベルの保持期間が開始されたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-342">This means the retention period for the label applied to the Spinning Widget product document has been initiated, based on the event date of the Cessation Production Spinning Widget event.</span></span> <span data-ttu-id="9c4f5-343">1 日間の保持期間を構成してテスト環境にシナリオを実装したと仮定すると、イベントが作成されてから数日後に製品ドキュメントのドキュメント ライブラリに移動し、ドキュメントが削除されたことを確認できます (SharePoint で削除ジョブが実行された後)。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-343">Assuming you implemented the scenario in your test environment by configuring a one-day retention period, you can go to the document library for your product documents a few days after the event was created and verify that the document is deleted (after the deletion job in SharePoint has run).</span></span>

### <a name="more-about-asset-ids"></a><span data-ttu-id="9c4f5-344">資産 ID の詳細</span><span class="sxs-lookup"><span data-stu-id="9c4f5-344">More about Asset Ids</span></span>

<span data-ttu-id="9c4f5-345">「[イベント ベースの保持の概要](event-driven-retention.md)」で説明したように、イベントの種類、ラベル、イベント、資産 ID の関係を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-345">As explained in the [overview of event-driven retention](event-driven-retention.md), it's important to understand the relationship between event types, labels, events, and asset Ids.</span></span> <span data-ttu-id="9c4f5-346">資産 ID は、SharePoint と OneDrive の別のドキュメント プロパティです。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-346">The Asset Id is simply another document property in SharePoint and OneDrive.</span></span> <span data-ttu-id="9c4f5-347">イベントによって保持期間がトリガーされるドキュメントをさらに識別するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-347">It helps you to further identify the documents whose retention period will be triggered by the event.</span></span> <span data-ttu-id="9c4f5-348">既定では、SharePoint にはイベント ベースの保持に使用できる資産 ID プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-348">By default, SharePoint has an Asset Id property that you can use for event-driven retention:</span></span>

![ドキュメント プロパティの詳細ページに表示される資産 ID プロパティ](../media/SPRetention26.png)

<span data-ttu-id="9c4f5-350">次のスクリーンショットに示すように、資産 ID 管理プロパティは **ComplianceAssetId** と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-350">As shown in the following screenshot, the Asset Id managed property is called **ComplianceAssetId**.</span></span>

![ComplianceAssetId 管理プロパティ](../media/SPRetention27.png)

<span data-ttu-id="9c4f5-352">このシナリオで行うように、既定の資産 ID プロパティを使用する代わりに、他のプロパティを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-352">Instead of using the default Asset Id property, you can also use any other property, as we do in this scenario.</span></span> <span data-ttu-id="9c4f5-353">ただし、イベントの資産 ID またはキーワードを指定しない場合、そのイベントの種類のラベルの付いたすべてのコンテンツはイベントによってトリガーされる保持期間を持つことを理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-353">But it's important to understand that if you don't specify an asset ID or keywords for an event, all of the content with a label of that event type will have its retention period triggered by the event.</span></span>

### <a name="using-advanced-search-in-sharepoint"></a><span data-ttu-id="9c4f5-354">SharePoint で高度な検索を使用する</span><span class="sxs-lookup"><span data-stu-id="9c4f5-354">Using advanced search in SharePoint</span></span>

<span data-ttu-id="9c4f5-355">前のスクリーンショットでは、**ComplianceTag** と呼ばれる保持ラベルに関連する別の管理プロパティがあり、クロールされたプロパティにマップされていることもわかります。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-355">In the previous screenshot, we can also see that there's another managed property related to retention labels called **ComplianceTag** and that it's mapped to a crawled property.</span></span> <span data-ttu-id="9c4f5-356">**ComplianceAssetId** 管理プロパティは、クロールされたプロパティにもマップされます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-356">The **ComplianceAssetId** managed property is also mapped to a crawled property.</span></span> <span data-ttu-id="9c4f5-357">つまり、高度な検索でこれらの管理プロパティを使用して、保持ラベルでタグ付けされたすべてのドキュメントを取得できます。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-357">This means you can use these managed properties in advanced search to retrieve all documents that have been tagged with a retention label.</span></span>

## <a name="summary"></a><span data-ttu-id="9c4f5-358">概要</span><span class="sxs-lookup"><span data-stu-id="9c4f5-358">Summary</span></span>

<span data-ttu-id="9c4f5-359">この記事では、SharePoint のサイト列に基づいて保持ラベルを自動的に適用するドキュメント管理シナリオを示しました。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-359">This article illustrated a document management scenario where we automatically applied a retention label based on a site column in SharePoint.</span></span> <span data-ttu-id="9c4f5-360">次に、イベント ベースの保持と Microsoft Flow を使用して、外部イベントに基づいて保持期間の開始を自動的にトリガーしました。</span><span class="sxs-lookup"><span data-stu-id="9c4f5-360">Then we used event-based retention and Microsoft Flow to automatically trigger the start of the retention period based on an external event.</span></span>

## <a name="credits"></a><span data-ttu-id="9c4f5-361">開発者情報</span><span class="sxs-lookup"><span data-stu-id="9c4f5-361">Credits</span></span>

<span data-ttu-id="9c4f5-362">このシナリオの作成者:</span><span class="sxs-lookup"><span data-stu-id="9c4f5-362">This scenario was authored by:</span></span> 

<span data-ttu-id="9c4f5-363">Frederic Lapierre</span><span class="sxs-lookup"><span data-stu-id="9c4f5-363">Frederic Lapierre</span></span><br/><span data-ttu-id="9c4f5-364">Microsoft Services プリンシパル コンサルタント</span><span class="sxs-lookup"><span data-stu-id="9c4f5-364">Principal Consultant, Microsoft Services</span></span>
