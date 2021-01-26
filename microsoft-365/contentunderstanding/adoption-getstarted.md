---
title: 'Microsoft SharePoint Syntex の導入: 概要'
description: 組織で SharePoint Syntex を使用して実装し、ビジネス上の問題を解決する方法について説明します。
ms.author: samanro
author: samanro
manager: pamgreen
ms.date: 7/20/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: 7a0bd04121d7400cced22e43a539bd21c45a7fc3
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976576"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a><span data-ttu-id="2eb2f-103">Microsoft SharePoint Syntex の導入: 概要</span><span class="sxs-lookup"><span data-stu-id="2eb2f-103">Microsoft SharePoint Syntex adoption: Get started</span></span>

<span data-ttu-id="2eb2f-104">SharePoint Syntex で利用できるインテリジェント コンテンツ サービスは、次の 3 つの部分から構成されています。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-104">Think of the intelligent content services available in SharePoint Syntex as having three parts:</span></span>

- <span data-ttu-id="2eb2f-105">**コンテンツ理解: 情報** を分類してコンテンツから抽出するコードなし AI モデルを作成し、知識の検出と再利用のためにメタデータを自動的に適用します。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-105">**Content understanding:** create no-code AI models to classify and extract information from content to automatically apply metadata for knowledge discovery and reuse.</span></span> <span data-ttu-id="2eb2f-106">コンテンツの理解について [詳しくは、次のリンクを参照してください](document-understanding-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-106">Learn more about [content understanding](document-understanding-overview.md).</span></span>
- <span data-ttu-id="2eb2f-107">**コンテンツ処理:** Power Automate を使用して、コンテンツのキャプチャ、取り込み、分類を自動化し、コンテンツ中心のプロセスを合理化します。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-107">**Content processing:** Automate capture, ingestion and categorization of content and streamline content-centric processes using Power Automate.</span></span> <span data-ttu-id="2eb2f-108">コンテンツ処理について [詳しくは、次のリンクを参照してください](form-processing-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-108">Learn more about [content processing](form-processing-overview.md).</span></span>
- <span data-ttu-id="2eb2f-109">**コンテンツコンプライアンス:** Microsoft Information Protection との統合によるセキュリティとガバナンスを向上させるために、コンテンツを制御および管理します。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-109">**Content compliance:** Control and manage content to improve security and governance with integration to Microsoft Information Protection.</span></span>

<span data-ttu-id="2eb2f-110">新しい AI サービスと機能を使用すると、SharePoint Syntex を使用してコンテンツの理解と分類アプリをコンテンツ管理フローに直接組み込むできます。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-110">With new AI services and capabilities, you can build content understanding and classification apps directly into the content management flow using SharePoint Syntex.</span></span> <span data-ttu-id="2eb2f-111">コンテンツを理解するには、2 つの異なる方法があります。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-111">There are two different ways of understanding your content.</span></span> <span data-ttu-id="2eb2f-112">使用するモデルの種類は、ファイル形式と使用例に基づいて異なります。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-112">The model type you use is based on file format and use case:</span></span>

| <span data-ttu-id="2eb2f-113">フォーム処理</span><span class="sxs-lookup"><span data-stu-id="2eb2f-113">Form processing</span></span> | <span data-ttu-id="2eb2f-114">ドキュメントの理解</span><span class="sxs-lookup"><span data-stu-id="2eb2f-114">Document understanding</span></span> |
|:-------|:-------|
| <span data-ttu-id="2eb2f-115">ドキュメント ライブラリから作成されます。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-115">Created from document library.</span></span> | <span data-ttu-id="2eb2f-116">SharePoint Syntex の一部であるコンテンツ センターで作成されます。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-116">Created in the content center, part of SharePoint Syntex.</span></span> |
| <span data-ttu-id="2eb2f-117">AI ビルダーで作成されたモデル。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-117">Model created in AI builder.</span></span> | <span data-ttu-id="2eb2f-118">ネイティブ インターフェイスで作成されたモデル。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-118">Model created in native interface.</span></span> |
| <span data-ttu-id="2eb2f-119">半構造化ファイル形式に使用されます。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-119">Used for semi-structured file formats.</span></span> | <span data-ttu-id="2eb2f-120">非構造化ファイル形式に使用されます。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-120">Used for unstructured file formats.</span></span> |
| <span data-ttu-id="2eb2f-121">設定可能な分類子。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-121">Settable classifier.</span></span> | <span data-ttu-id="2eb2f-122">トレーニング可能な分類子とオプションの抽出器。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-122">Trainable classifier with optional extractors.</span></span> |
| <span data-ttu-id="2eb2f-123">1 つのライブラリに制限されます。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-123">Restricted to a single library.</span></span> | <span data-ttu-id="2eb2f-124">複数のライブラリに適用できます。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-124">Can be applied to multiple libraries.</span></span> |
| <span data-ttu-id="2eb2f-125">PDF、JPG、PNG 形式でトレーニングを行い、合計 50 MB/500 pp。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-125">Train on PDF, JPG, PNG format, total 50 MB/500 pp.</span></span> | <span data-ttu-id="2eb2f-126">5 から 10 PDF、Office、または電子メール ファイル (負の例を含む) でトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-126">Train on 5-10 PDF, Office, or email files, including negative examples.</span></span> |

<span data-ttu-id="2eb2f-127">次の表では、SharePoint Syntex の可用性とライセンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-127">The following table explains availability and licensing for SharePoint Syntex:</span></span>

| <span data-ttu-id="2eb2f-128">フォーム処理</span><span class="sxs-lookup"><span data-stu-id="2eb2f-128">Form processing</span></span> | <span data-ttu-id="2eb2f-129">ドキュメントの理解</span><span class="sxs-lookup"><span data-stu-id="2eb2f-129">Document understanding</span></span> |
|:-------|:-------|
| <span data-ttu-id="2eb2f-130">フォーム処理は、Power Platform に依存します。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-130">Form processing relies on Power Platform.</span></span> <br><span data-ttu-id="2eb2f-131">Power Platform と AI Builder のグローバルな可用性については、「Power Platform の可用性」 [を参照してください](https://dynamics.microsoft.com/geographic-availability/)。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-131">For information about global availability for Power Platform and AI Builder, see [Power Platform availability](https://dynamics.microsoft.com/geographic-availability/).</span></span> | <span data-ttu-id="2eb2f-132">すべての地域で使用できます。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-132">Available in all regions.</span></span> |
| <span data-ttu-id="2eb2f-133">AI ビルダー クレジットを使用します。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-133">Uses AI Builder credits.</span></span><br><span data-ttu-id="2eb2f-134">クレジットは 1M のバッチで購入できます。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-134">Credits can be purchased in batches of 1M.</span></span><br><span data-ttu-id="2eb2f-135">300 以上の SharePoint Syntex ライセンスを購入すると、1M クレジットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-135">1M credits are included when 300+ SharePoint Syntex licenses are purchased.</span></span><br><span data-ttu-id="2eb2f-136">1M クレジットでは、2000 のファイル ページを処理できます。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-136">1M credits will allow processing of 2000 file pages.</span></span> | <span data-ttu-id="2eb2f-137">モデルは、ラテン語のすべての言語で動作します。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-137">Models work on all latin alphabet languages.</span></span> <span data-ttu-id="2eb2f-138">英語に加えて、ドイツ語、スウェーデン語、フランス語、スペイン語、イタリア語、ポルトガル語。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-138">In addition to English: German, Swedish, French, Spanish, Italian, and Portuguese.</span></span> |
| <span data-ttu-id="2eb2f-139">既定の共通データ サービス環境に対して準備されます。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-139">Provisioned against the default common data service environment.</span></span> | <span data-ttu-id="2eb2f-140">容量の制限はありません。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-140">Does not have capacity restrictions.</span></span> |

<span data-ttu-id="2eb2f-141">AI Builder のクレジットと単位の詳細については [、「AI Builder のライセンス」を参照してください](https://docs.microsoft.com/ai-builder/administer-licensing)。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-141">For more information about AI Builder credits and units, see [AI Builder licensing](https://docs.microsoft.com/ai-builder/administer-licensing).</span></span>

<span data-ttu-id="2eb2f-142">SharePoint Syntex は、次のような Microsoft 365 コンプライアンス機能と統合されます。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-142">SharePoint Syntex integrates with Microsoft 365 compliance features like:</span></span>

- <span data-ttu-id="2eb2f-143">ドキュメントの保存期間または外部イベントに基づいてレコード ポリシーを定義する保持ラベル。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-143">Retention labels that define records policy based on document age or external events.</span></span>
- <span data-ttu-id="2eb2f-144">DLP、暗号化、共有、条件付きアクセス ポリシーを設定する感度ラベル。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-144">Sensitivity labels that set DLP, encryption, sharing, and conditional access policies.</span></span>

<span data-ttu-id="2eb2f-145">ユーザーはラベルを適用するか、SharePoint Syntex AI モデルによって自動的に適用できます。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-145">Users can apply labels, or they can be applied automatically by SharePoint Syntex AI models.</span></span> <span data-ttu-id="2eb2f-146">分析とファイル計画では、ラベルの使用状況とポリシーを拡張して管理できます。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-146">Analytics and file plans provide scaled management of label usage and policies.</span></span>

## <a name="identify-pilot-business-scenarios-to-optimize"></a><span data-ttu-id="2eb2f-147">最適化するパイロット ビジネス シナリオを特定する</span><span class="sxs-lookup"><span data-stu-id="2eb2f-147">Identify pilot business scenarios to optimize</span></span>

<span data-ttu-id="2eb2f-148">組織で SharePoint Syntex を使用する準備をするには、まず、それが役立つシナリオを理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-148">To prepare for using SharePoint Syntex in your organization, you first need to understand the scenarios in which it will be useful.</span></span> <span data-ttu-id="2eb2f-149">この理由は、必要なモデルを決定し、モデルを適用する場所に基づいて組織を構造化する方法を決定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-149">The why helps determine what model will be needed, and how to structure your org based on where the model will be applied.</span></span> <span data-ttu-id="2eb2f-150">ドキュメントの理解が組織に役立ついくつかのシナリオを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-150">Here are a few scenarios where document understanding can help your organization:</span></span>

- <span data-ttu-id="2eb2f-151">コンテンツ処理: 契約、作業明細書、その他のフォームのようなドキュメントを処理します。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-151">Content processing: Process contracts, statements of work, and other form-like documents.</span></span> <span data-ttu-id="2eb2f-152">フォームを入力し、フィールドを理解してマップし、フォームを実行して自動的にデータを収集するモデルをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-152">Intake the forms, train the model to understand and map the fields, and then run your forms through to automatically collect the data.</span></span> <span data-ttu-id="2eb2f-153">詳細については、「フォーム処理の [概要」を参照してください](form-processing-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-153">For more information, see [Form processing overview](form-processing-overview.md).</span></span>
- <span data-ttu-id="2eb2f-154">請求書の分析: 請求書から関連する詳細を引き出し、ポリシーに準拠している、または適切に処理されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-154">Invoice analysis: Pull out the relevant details from your invoices and make sure they're complying with policy or are being processed appropriately.</span></span>

<span data-ttu-id="2eb2f-155">SharePoint Syntex が組織を支援する方法について考えます。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-155">Think about ways that SharePoint Syntex can help your organization:</span></span>

- <span data-ttu-id="2eb2f-156">ビジネス プロセスを自動化する</span><span class="sxs-lookup"><span data-stu-id="2eb2f-156">Automate business processes</span></span>
- <span data-ttu-id="2eb2f-157">検索の精度を向上させる</span><span class="sxs-lookup"><span data-stu-id="2eb2f-157">Improve search accuracy</span></span>
- <span data-ttu-id="2eb2f-158">コンプライアンス リスクを管理する</span><span class="sxs-lookup"><span data-stu-id="2eb2f-158">Manage compliance risk</span></span>

### <a name="form-processing-scenario-example"></a><span data-ttu-id="2eb2f-159">フォーム処理シナリオの例</span><span class="sxs-lookup"><span data-stu-id="2eb2f-159">Form processing scenario example</span></span>

<span data-ttu-id="2eb2f-160">たとえば、SharePoint Syntex 機能と Power Automate 機能を使用して、請求書を追跡および監視するプロセスを設定できます。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-160">For example, you can set up a process using SharePoint Syntex and Power Automate features to track and monitor invoices.</span></span>

1. <span data-ttu-id="2eb2f-161">請求書のドキュメントを格納するライブラリを設定します。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-161">Set up a library to store the invoice documents.</span></span>
1. <span data-ttu-id="2eb2f-162">ドキュメント内のフィールドを認識するようにモデルをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-162">Train the model to recognize fields in the documents.</span></span>
1. <span data-ttu-id="2eb2f-163">追跡するフィールドをリストに抽出します。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-163">Extract the fields you want to track into a list.</span></span>
1. <span data-ttu-id="2eb2f-164">次のような特定のイベントについて通知するフローを設定します。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-164">Set up a flow to notify you for specific events, such as:</span></span>
    - <span data-ttu-id="2eb2f-165">新しい請求書が追加されます。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-165">A new invoice is added.</span></span>
    - <span data-ttu-id="2eb2f-166">請求書が期限を過ぎた。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-166">An invoice is past its due date.</span></span>
    - <span data-ttu-id="2eb2f-167">請求書は、自動承認金額より大きい金額です。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-167">An invoice is for an amount that's larger than your automatic approval amount.</span></span>

![SharePoint Syntex と Power Automate を使用して請求書を追跡および監視する](../media/content-understanding/process-invoices-flow.png)

<span data-ttu-id="2eb2f-169">このシナリオを自動化すると、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-169">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="2eb2f-170">手動で行う代わりに、請求書からデータを自動的に抽出することで、時間と支払いを節約できます。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-170">Save time and money by automatically extracting data from the invoices instead of doing it manually.</span></span>
- <span data-ttu-id="2eb2f-171">ワークフローを使用して請求書を処理し、問題を通知することにより、潜在的なエラーを削減し、コンプライアンスを強化します。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-171">Reduce potential errors and ensure better compliance by using workflows to act on the invoices and notify you of any issues.</span></span>

### <a name="document-understanding-scenario-example"></a><span data-ttu-id="2eb2f-172">ドキュメント理解シナリオの例</span><span class="sxs-lookup"><span data-stu-id="2eb2f-172">Document understanding scenario example</span></span>

<span data-ttu-id="2eb2f-173">別の例として、会社が他の会社や個人と締結している契約を識別するプロセスを設定できます。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-173">As another example, you can set up a process to identify contracts that your company has with other companies or individuals.</span></span> <span data-ttu-id="2eb2f-174">クライアント名、手数料、日付、その他の重要な情報などの重要な情報をコントラクトから抽出するモデルを設定し、それをすぐに表示できるフィールドとしてライブラリに追加できます。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-174">You can set up a model to extract key information from those contracts, such as the client name, fees, dates, or other important information, and add that to the library as fields you can quickly view.</span></span> <span data-ttu-id="2eb2f-175">また、ドキュメント ライブラリに保持ラベルを適用して、ビジネス規制に適切に準拠するために、特定の期間がたつ前に契約を削除できないことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-175">And you can apply a retention label on the document library to ensure that contracts cannot be deleted before a specific length of time for appropriate compliance with your business regulations.</span></span>

1. <span data-ttu-id="2eb2f-176">コンテンツ センターから開始し、契約書の新しいドキュメント理解モデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-176">Start at the content center and create a new document understanding model for contracts.</span></span>
1. <span data-ttu-id="2eb2f-177">正と負の例のサンプル ドキュメントをアップロードし、契約ドキュメントを識別して結果を確認するトレーニングを実行します。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-177">Upload sample documents for positive and negative examples, then run the training to identify contract documents and review the results.</span></span>
1. <span data-ttu-id="2eb2f-178">クライアント名、手数料、日付などの契約内のフィールドを識別する抽出器をトレーニングし、抽出器をテストします。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-178">Train the extractor to identify fields in the contracts, such as the client name, fee, and date, and then test the extractor.</span></span>
1. <span data-ttu-id="2eb2f-179">モデルが完了したら、コントラクトをアップロードできるライブラリにモデルを適用します。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-179">When the model is complete, apply the model to a library where you can upload contracts.</span></span>
1. <span data-ttu-id="2eb2f-180">日付フィールドに保持ラベルを適用して、組織が契約に必要な期間、契約書をライブラリに保持します。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-180">Apply a retention label to the date field, so that contracts are retained in the library for the length of time your organization requires for contracts.</span></span>

![SharePoint Syntex と保持ラベルとの契約を追跡および監視する](../media/content-understanding/process-contracts-flow.png)

<span data-ttu-id="2eb2f-182">このシナリオを自動化すると、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-182">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="2eb2f-183">手動で行う代わりに、契約から自動的にデータを抽出することで、時間と支払いを節約できます。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-183">Save time and money by automatically extracting data from the contracts instead of doing it manually.</span></span>
- <span data-ttu-id="2eb2f-184">保持ラベルを使用して契約が適切に保持され、コンプライアンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-184">Ensure better compliance by using retention labels to ensure that the contracts are retained appropriately.</span></span>

### <a name="tips-for-identifying-scenarios"></a><span data-ttu-id="2eb2f-185">シナリオを特定するためのヒント</span><span class="sxs-lookup"><span data-stu-id="2eb2f-185">Tips for identifying scenarios</span></span>

<span data-ttu-id="2eb2f-186">どのビジネス シナリオを検討する必要があるのか考える場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-186">When thinking about which business scenarios to consider, ask yourself the following questions:</span></span>

- <span data-ttu-id="2eb2f-187">それは実際の問題を解決しますか?</span><span class="sxs-lookup"><span data-stu-id="2eb2f-187">Does it solve a real problem?</span></span>
- <span data-ttu-id="2eb2f-188">広く使用されるか、広く影響を与えるのか。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-188">Will it be widely used or have broad impact?</span></span>
- <span data-ttu-id="2eb2f-189">入手できますか?</span><span class="sxs-lookup"><span data-stu-id="2eb2f-189">Is it obtainable?</span></span>
- <span data-ttu-id="2eb2f-190">成功を測定できますか?</span><span class="sxs-lookup"><span data-stu-id="2eb2f-190">Can you measure success?</span></span>

<span data-ttu-id="2eb2f-191">影響と実装の容易性に基づいてシナリオに優先順位を付ける。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-191">Prioritize scenarios based on impact and ease of implementation.</span></span> <span data-ttu-id="2eb2f-192">初期フォーカス領域を簡単に実装できる影響の高いシナリオにします。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-192">Make your initial focus area higher impact scenarios that can also be easily implemented.</span></span> <span data-ttu-id="2eb2f-193">実装が難しい影響の低いシナリオの優先順位を下げる。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-193">De-prioritize lower impact scenarios that are hard to implement.</span></span>

## <a name="identify-roles--responsibilities"></a><span data-ttu-id="2eb2f-194">役割と責任&特定する</span><span class="sxs-lookup"><span data-stu-id="2eb2f-194">Identify roles & responsibilities</span></span>

<span data-ttu-id="2eb2f-195">組織内でモデルを構築および管理するユーザーを決定する</span><span class="sxs-lookup"><span data-stu-id="2eb2f-195">Determine who in your organization will build and manage the models?</span></span> <span data-ttu-id="2eb2f-196">次の役割が関係する場合があります。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-196">The following roles might be involved:</span></span>

| <span data-ttu-id="2eb2f-197">SharePoint/ナレッジ管理者</span><span class="sxs-lookup"><span data-stu-id="2eb2f-197">SharePoint/Knowledge admin</span></span> | <span data-ttu-id="2eb2f-198">Power Platform 管理者</span><span class="sxs-lookup"><span data-stu-id="2eb2f-198">Power Platform admin</span></span> | <span data-ttu-id="2eb2f-199">ナレッジ マネージャー</span><span class="sxs-lookup"><span data-stu-id="2eb2f-199">Knowledge manager</span></span> | <span data-ttu-id="2eb2f-200">モデル所有者</span><span class="sxs-lookup"><span data-stu-id="2eb2f-200">Model owner</span></span> |
|:-------|:-------|:-------|:-------|
| <span data-ttu-id="2eb2f-201">AAD 役割</span><span class="sxs-lookup"><span data-stu-id="2eb2f-201">AAD role</span></span>| <span data-ttu-id="2eb2f-202">役割を追加する</span><span class="sxs-lookup"><span data-stu-id="2eb2f-202">ADD role</span></span> | <span data-ttu-id="2eb2f-203">AAD 役割</span><span class="sxs-lookup"><span data-stu-id="2eb2f-203">AAD role</span></span> | <span data-ttu-id="2eb2f-204">チャンピオン</span><span class="sxs-lookup"><span data-stu-id="2eb2f-204">Champions</span></span> |
| <span data-ttu-id="2eb2f-205">フォームの処理を構成する</span><span class="sxs-lookup"><span data-stu-id="2eb2f-205">Configure form processing</span></span> | <span data-ttu-id="2eb2f-206">フォーム処理用に共通データ サービス環境を構成する</span><span class="sxs-lookup"><span data-stu-id="2eb2f-206">Configure Common data service environment for form processing</span></span> | <span data-ttu-id="2eb2f-207">使用事例を収集する</span><span class="sxs-lookup"><span data-stu-id="2eb2f-207">Gather use cases</span></span> | <span data-ttu-id="2eb2f-208">ビジネス の使用事例を収集する</span><span class="sxs-lookup"><span data-stu-id="2eb2f-208">Gather business use cases</span></span> |
| <span data-ttu-id="2eb2f-209">コンテンツ センターとアクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="2eb2f-209">Manage content centers and permissions</span></span>| <span data-ttu-id="2eb2f-210">AIB クレジットを購入して割り当てる</span><span class="sxs-lookup"><span data-stu-id="2eb2f-210">Purchase and allocate AIB credits</span></span> | <span data-ttu-id="2eb2f-211">ベスト プラクティスの確立とモデル分析のレビュー</span><span class="sxs-lookup"><span data-stu-id="2eb2f-211">Establish best practices and review model analytics</span></span> | <span data-ttu-id="2eb2f-212">モデルの作成と適用</span><span class="sxs-lookup"><span data-stu-id="2eb2f-212">Create and apply models</span></span> |

<span data-ttu-id="2eb2f-213">ナレッジ マネージャー、ビジネス プロセス所有者、およびコンテンツ モデルの所有者は、組織内でサンプル モデルとチャンピオン導入を作成します。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-213">Knowledge manager, Business Process Owner and Content model owner create sample models and champion adoption in the organization.</span></span>
<span data-ttu-id="2eb2f-214">関連する可能性があるその他のユーザー: コンプライアンス管理者、分類マネージャー。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-214">Others who may be involved: Compliance admin, Taxonomy managers.</span></span>

<span data-ttu-id="2eb2f-215">モデルを構築して適用する場所</span><span class="sxs-lookup"><span data-stu-id="2eb2f-215">Where will they build and apply the models?</span></span> <span data-ttu-id="2eb2f-216">拡張できる既存のプロセスまたはリポジトリはありますか?</span><span class="sxs-lookup"><span data-stu-id="2eb2f-216">Are there existing processes or repositories that could be enhanced?</span></span>

- <span data-ttu-id="2eb2f-217">フォーム処理: フォーム処理アクションを取得するサイトを決定します。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-217">Form processing: Decide which sites will get Form processing action.</span></span>
- <span data-ttu-id="2eb2f-218">ドキュメントの理解: ビジネス領域ごとに複数のコンテンツ センターを作成できます。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-218">Document understanding: You can create multiple content centers for different business areas.</span></span>

## <a name="strategic-positioning"></a><span data-ttu-id="2eb2f-219">戦略的位置付け</span><span class="sxs-lookup"><span data-stu-id="2eb2f-219">Strategic positioning</span></span>

<span data-ttu-id="2eb2f-220">関係者と協力して、SharePoint Syntex を使用する戦略に沿っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-220">Work with stakeholders to make sure they are aligned on the strategy for using SharePoint Syntex.</span></span> <span data-ttu-id="2eb2f-221">この位置付けに役立つ次のリソースを調査して提供します。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-221">Research and provide the following resources to help with this positioning:</span></span>

- <span data-ttu-id="2eb2f-222">ビジネス成果:</span><span class="sxs-lookup"><span data-stu-id="2eb2f-222">Business outcomes:</span></span>
  - <span data-ttu-id="2eb2f-223">潜在的な会計結果</span><span class="sxs-lookup"><span data-stu-id="2eb2f-223">Potential fiscal outcomes</span></span>
  - <span data-ttu-id="2eb2f-224">潜在的な機敏性の結果</span><span class="sxs-lookup"><span data-stu-id="2eb2f-224">Potential agility outcomes</span></span>
  - <span data-ttu-id="2eb2f-225">ビジネス成果テンプレート</span><span class="sxs-lookup"><span data-stu-id="2eb2f-225">Business outcome template</span></span>
- <span data-ttu-id="2eb2f-226">関係者/エグゼクティブ スポンサーのバイイン/アラインメント</span><span class="sxs-lookup"><span data-stu-id="2eb2f-226">Stakeholders/Exec sponsor buy-in/alignment</span></span>
  - <span data-ttu-id="2eb2f-227">ビジネス ケース デッキ</span><span class="sxs-lookup"><span data-stu-id="2eb2f-227">Business case decks</span></span>
  - <span data-ttu-id="2eb2f-228">財務モデル</span><span class="sxs-lookup"><span data-stu-id="2eb2f-228">Financial models</span></span>
  - <span data-ttu-id="2eb2f-229">会社の準備 - カルチャ</span><span class="sxs-lookup"><span data-stu-id="2eb2f-229">Company readiness - culture</span></span>

## <a name="identify-stakeholders"></a><span data-ttu-id="2eb2f-230">関係者の特定</span><span class="sxs-lookup"><span data-stu-id="2eb2f-230">Identify stakeholders</span></span>

<span data-ttu-id="2eb2f-231">プロジェクトの関係者を特定します。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-231">Identify the stakeholders for your project.</span></span>

|<span data-ttu-id="2eb2f-232">ロール</span><span class="sxs-lookup"><span data-stu-id="2eb2f-232">Role</span></span> |<span data-ttu-id="2eb2f-233">責任</span><span class="sxs-lookup"><span data-stu-id="2eb2f-233">Responsibilities</span></span> |<span data-ttu-id="2eb2f-234">部門</span><span class="sxs-lookup"><span data-stu-id="2eb2f-234">Department</span></span> |
|:-------|:-------|:--------|
| <span data-ttu-id="2eb2f-235">エグゼクティブ スポンサー</span><span class="sxs-lookup"><span data-stu-id="2eb2f-235">Executive sponsor(s)</span></span>   | <span data-ttu-id="2eb2f-236">会社に高レベルのビジョンと価値を伝える</span><span class="sxs-lookup"><span data-stu-id="2eb2f-236">Communicate high-level vision and values to the company</span></span>   |  <span data-ttu-id="2eb2f-237">エグゼクティブ リーダー</span><span class="sxs-lookup"><span data-stu-id="2eb2f-237">Executive leadership</span></span>   |
| <span data-ttu-id="2eb2f-238">プロジェクト リード</span><span class="sxs-lookup"><span data-stu-id="2eb2f-238">Project lead(s)</span></span> | <span data-ttu-id="2eb2f-239">起動の実行とロールアウトプロセス全体を監視する</span><span class="sxs-lookup"><span data-stu-id="2eb2f-239">Oversee the entire launch execution and rollout process</span></span> | <span data-ttu-id="2eb2f-240">プロジェクト管理</span><span class="sxs-lookup"><span data-stu-id="2eb2f-240">Project management</span></span> |
| <span data-ttu-id="2eb2f-241">ナレッジ管理者</span><span class="sxs-lookup"><span data-stu-id="2eb2f-241">Knowledge administrators</span></span>| <span data-ttu-id="2eb2f-242">コンテンツ センターを作成および管理する</span><span class="sxs-lookup"><span data-stu-id="2eb2f-242">Create and manage the content centers</span></span> | <span data-ttu-id="2eb2f-243">IT 部門または他の部門</span><span class="sxs-lookup"><span data-stu-id="2eb2f-243">IT or other department</span></span>|
| <span data-ttu-id="2eb2f-244">コンテンツ管理者とモデル所有者</span><span class="sxs-lookup"><span data-stu-id="2eb2f-244">Content managers and model owners</span></span>| <span data-ttu-id="2eb2f-245">使用事例の収集とモデルの作成と適用</span><span class="sxs-lookup"><span data-stu-id="2eb2f-245">Gather use cases and create and apply models</span></span> | <span data-ttu-id="2eb2f-246">任意の部署</span><span class="sxs-lookup"><span data-stu-id="2eb2f-246">Any department</span></span>|
| <span data-ttu-id="2eb2f-247">チャンピオン</span><span class="sxs-lookup"><span data-stu-id="2eb2f-247">Champions</span></span> | <span data-ttu-id="2eb2f-248">オブジェクト処理の助けと管理</span><span class="sxs-lookup"><span data-stu-id="2eb2f-248">Help evangelize and manage objection handling</span></span> | <span data-ttu-id="2eb2f-249">任意の部署 (スタッフ)</span><span class="sxs-lookup"><span data-stu-id="2eb2f-249">Any department (staff)</span></span> |
| <span data-ttu-id="2eb2f-250">テナント管理者</span><span class="sxs-lookup"><span data-stu-id="2eb2f-250">Tenant administrator</span></span> | <span data-ttu-id="2eb2f-251">テナント レベルの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="2eb2f-251">Configure tenant-level settings</span></span> | <span data-ttu-id="2eb2f-252">IT 部門</span><span class="sxs-lookup"><span data-stu-id="2eb2f-252">IT department</span></span>|
| <span data-ttu-id="2eb2f-253">Power Platform 管理者</span><span class="sxs-lookup"><span data-stu-id="2eb2f-253">Power Platform administrator</span></span>| <span data-ttu-id="2eb2f-254">共通データ サービス環境を構成する</span><span class="sxs-lookup"><span data-stu-id="2eb2f-254">Configure common data services environment</span></span> | <span data-ttu-id="2eb2f-255">IT 部門</span><span class="sxs-lookup"><span data-stu-id="2eb2f-255">IT department</span></span>|

> [!Note]
> <span data-ttu-id="2eb2f-256">ロールアウトを通じてこれらの各役割を満たすことをお勧めしますが、特定のソリューションを開始するためにそれらのすべての役割を必要としない場合があります。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-256">Though we recommend having each of these roles fulfilled throughout your rollout, you may find that you don't require them all to get started with your identified solution.</span></span>

## <a name="readiness-checklist"></a><span data-ttu-id="2eb2f-257">準備チェックリスト</span><span class="sxs-lookup"><span data-stu-id="2eb2f-257">Readiness checklist</span></span>

<span data-ttu-id="2eb2f-258">SharePoint Syntex を実装する準備をするには、次の必要があります。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-258">To get ready for implementing SharePoint Syntex, you need to:</span></span>

![コンテンツを理解する準備](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. <span data-ttu-id="2eb2f-260">終了状態を計画する</span><span class="sxs-lookup"><span data-stu-id="2eb2f-260">Plan the end state</span></span>
    - <span data-ttu-id="2eb2f-261">ドキュメント理解モデルは、最後の手段ではなく、手段です。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-261">Document understanding models are the means, not the end.</span></span>
    - <span data-ttu-id="2eb2f-262">抽出されたメタデータの値を次の方法で活用する計画を立てします。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-262">Plan for harnessing the value of extracted metadata with:</span></span>
      - <span data-ttu-id="2eb2f-263">検索</span><span class="sxs-lookup"><span data-stu-id="2eb2f-263">Search</span></span>
      - <span data-ttu-id="2eb2f-264">フィルター処理とビューの書式設定</span><span class="sxs-lookup"><span data-stu-id="2eb2f-264">Filtering and view formatting</span></span>
      - <span data-ttu-id="2eb2f-265">コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="2eb2f-265">Compliance</span></span>
      - <span data-ttu-id="2eb2f-266">オートメーション</span><span class="sxs-lookup"><span data-stu-id="2eb2f-266">Automation</span></span>
2. <span data-ttu-id="2eb2f-267">識別</span><span class="sxs-lookup"><span data-stu-id="2eb2f-267">Identify</span></span>
    - <span data-ttu-id="2eb2f-268">既存の情報アーキテクチャとコンテンツ管理機能の使用について理解します。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-268">Understand existing information architecture and content management feature use.</span></span>
    - <span data-ttu-id="2eb2f-269">既存のコンテンツ タイプはモデルの候補として優れたものはありますか?</span><span class="sxs-lookup"><span data-stu-id="2eb2f-269">Are any existing content types good candidates for models?</span></span>
    - <span data-ttu-id="2eb2f-270">メタデータによって改善される既存のプロセス</span><span class="sxs-lookup"><span data-stu-id="2eb2f-270">What existing processes would be improved by metadata?</span></span>
3. <span data-ttu-id="2eb2f-271">デザイン</span><span class="sxs-lookup"><span data-stu-id="2eb2f-271">Design</span></span>
    - <span data-ttu-id="2eb2f-272">情報アーキテクチャ、管理されたメタデータ、およびコンテンツ タイプに対するアプローチを設計する</span><span class="sxs-lookup"><span data-stu-id="2eb2f-272">Design your approach to information architecture, managed metadata and content types</span></span>
    - <span data-ttu-id="2eb2f-273">定義、作成、管理のプロセスを設計します。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-273">Design the process for definition, creation, management.</span></span>

## <a name="engage-your-organization"></a><span data-ttu-id="2eb2f-274">組織を関与する</span><span class="sxs-lookup"><span data-stu-id="2eb2f-274">Engage your organization</span></span>

1. <span data-ttu-id="2eb2f-275">利害関係の所有者を特定し、シナリオを確認し、プロジェクト計画を策定します。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-275">Identify stake holders, confirm scenarios, and develop project plan.</span></span>
1. <span data-ttu-id="2eb2f-276">設定を構成し、ライセンスを適用します。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-276">Configure settings and apply licenses.</span></span>
1. <span data-ttu-id="2eb2f-277">認識とトレーニングを開始する – チャンピオンを募集します。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-277">Begin awareness and training – Recruit Champions.</span></span>
1. <span data-ttu-id="2eb2f-278">段階に分け展開します。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-278">Roll out in stages.</span></span>  
1. <span data-ttu-id="2eb2f-279">フィードバックを収集し、反復処理を行います。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-279">Gather feedback and iterate.</span></span>
1. <span data-ttu-id="2eb2f-280">利用状況が増えるにつれて、必要に応じて AI ビルダー クレジットのプランが拡大します。</span><span class="sxs-lookup"><span data-stu-id="2eb2f-280">As usage grows plan for any AI Builder credits as needed.</span></span>
