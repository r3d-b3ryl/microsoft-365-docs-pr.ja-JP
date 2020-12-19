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
ms.collection: enabler-strategic
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: 18bc5d8d0f80f7cee024f4d6358361509879bd11
ms.sourcegitcommit: 86f75cf77a7a446a79226ca530bd7b5eb39189cb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/18/2020
ms.locfileid: "49717021"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a><span data-ttu-id="939ba-103">Microsoft SharePoint Syntex の導入: 概要</span><span class="sxs-lookup"><span data-stu-id="939ba-103">Microsoft SharePoint Syntex adoption: Get started</span></span>

<span data-ttu-id="939ba-104">SharePoint Syntex で利用できるインテリジェント コンテンツ サービスは、次の 3 つの部分から構成されています。</span><span class="sxs-lookup"><span data-stu-id="939ba-104">Think of the intelligent content services available in SharePoint Syntex as having three parts:</span></span>

- <span data-ttu-id="939ba-105">**コンテンツ理解: 情報** を分類してコンテンツから抽出するコードなし AI モデルを作成し、知識の検出と再利用のためにメタデータを自動的に適用します。</span><span class="sxs-lookup"><span data-stu-id="939ba-105">**Content understanding:** create no-code AI models to classify and extract information from content to automatically apply metadata for knowledge discovery and reuse.</span></span> <span data-ttu-id="939ba-106">コンテンツの理解について [詳しくは、次のリンクを参照してください](document-understanding-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="939ba-106">Learn more about [content understanding](document-understanding-overview.md).</span></span>
- <span data-ttu-id="939ba-107">**コンテンツ処理:** Power Automate を使用して、コンテンツのキャプチャ、取り込み、分類を自動化し、コンテンツ中心のプロセスを合理化します。</span><span class="sxs-lookup"><span data-stu-id="939ba-107">**Content processing:** Automate capture, ingestion and categorization of content and streamline content-centric processes using Power Automate.</span></span> <span data-ttu-id="939ba-108">コンテンツ処理について [詳しくは、次のリンクを参照してください](form-processing-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="939ba-108">Learn more about [content processing](form-processing-overview.md).</span></span>
- <span data-ttu-id="939ba-109">**コンテンツコンプライアンス:** Microsoft Information Protection との統合によるセキュリティとガバナンスを向上させるために、コンテンツを制御および管理します。</span><span class="sxs-lookup"><span data-stu-id="939ba-109">**Content compliance:** Control and manage content to improve security and governance with integration to Microsoft Information Protection.</span></span>

<span data-ttu-id="939ba-110">新しい AI サービスと機能を使用すると、SharePoint Syntex を使用してコンテンツの理解と分類アプリをコンテンツ管理フローに直接組み込むできます。</span><span class="sxs-lookup"><span data-stu-id="939ba-110">With new AI services and capabilities, you can build content understanding and classification apps directly into the content management flow using SharePoint Syntex:</span></span>

|<span data-ttu-id="939ba-111">手動入力</span><span class="sxs-lookup"><span data-stu-id="939ba-111">Manual entry</span></span>| <span data-ttu-id="939ba-112">フォーム処理</span><span class="sxs-lookup"><span data-stu-id="939ba-112">Form processing</span></span> | <span data-ttu-id="939ba-113">ドキュメントの理解</span><span class="sxs-lookup"><span data-stu-id="939ba-113">Document understanding</span></span> |
|:-------|:--------|:--------|
| <span data-ttu-id="939ba-114">任意のコンテンツに対するデータの入力と手間のかかる作業</span><span class="sxs-lookup"><span data-stu-id="939ba-114">Data entry and labor-intensive on any content</span></span> | <span data-ttu-id="939ba-115">デジタル コンテンツの処理 - 写真、スキャン、受領通知、名刺、OCR を使用したビデオ&テキスト</span><span class="sxs-lookup"><span data-stu-id="939ba-115">Process digital content - photos, scans, receipts, business cards, videos with OCR & text</span></span> |  <span data-ttu-id="939ba-116">契約書、履歴書、その他の構造化ドキュメントからコンテンツ タイプとメタデータを取得する</span><span class="sxs-lookup"><span data-stu-id="939ba-116">Capture content types and  metadata from contracts, resumes, and other structured documents</span></span> |
| <span data-ttu-id="939ba-117">対話操作が可能</span><span class="sxs-lookup"><span data-stu-id="939ba-117">Interactive</span></span>   | <span data-ttu-id="939ba-118">事前に作成され、自動化されている</span><span class="sxs-lookup"><span data-stu-id="939ba-118">Pre-built, automated</span></span>   | <span data-ttu-id="939ba-119">カスタム、アシスト</span><span class="sxs-lookup"><span data-stu-id="939ba-119">Custom, assisted</span></span>  |
| <span data-ttu-id="939ba-120">作業を行うユーザー</span><span class="sxs-lookup"><span data-stu-id="939ba-120">People doing the work</span></span> | <span data-ttu-id="939ba-121">対象分野の専門家 (SMEs) が教える。</span><span class="sxs-lookup"><span data-stu-id="939ba-121">Taught by your subject matter experts (SMEs).</span></span> <span data-ttu-id="939ba-122">契約書、履歴書、その他の構造化ドキュメントからコンテンツ タイプとメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="939ba-122">Capture content types and  metadata from contracts, resumes, other structured documents.</span></span> | <span data-ttu-id="939ba-123">SMES の関与は少ない。</span><span class="sxs-lookup"><span data-stu-id="939ba-123">SMEs are less involved.</span></span> <span data-ttu-id="939ba-124">発注書、アプリケーション、その他の半構造化および構造化されたドキュメントから</span><span class="sxs-lookup"><span data-stu-id="939ba-124">from purchase orders, applications, other semi structured and structured documents</span></span> |

<span data-ttu-id="939ba-125">次の表では、SharePoint Syntex を使用するときに得る機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="939ba-125">The following table explains what you get when you use SharePoint Syntex:</span></span>

| <span data-ttu-id="939ba-126">フォーム処理</span><span class="sxs-lookup"><span data-stu-id="939ba-126">Form processing</span></span> | <span data-ttu-id="939ba-127">ドキュメントの理解</span><span class="sxs-lookup"><span data-stu-id="939ba-127">Document understanding</span></span> |
|:-------|:-------|
| <span data-ttu-id="939ba-128">APAC、オーストラリア、カナダ、EU、JP、LATAM、英国、米国で利用可能</span><span class="sxs-lookup"><span data-stu-id="939ba-128">Available in APAC, Australia, Canada, EU, JP, LATAM, UK, US</span></span> | <span data-ttu-id="939ba-129">すべての地域で使用可能</span><span class="sxs-lookup"><span data-stu-id="939ba-129">Available in all regions</span></span> |
| <span data-ttu-id="939ba-130">AI ビルダー クレジットを使用 - 1M クレジット = 2000 ページ使用量は約 2,000 請求書 =2 単位です。</span><span class="sxs-lookup"><span data-stu-id="939ba-130">Uses AI Builder credits - 1M credits = 2000 pages; Consumption is about 2000 invoices=2 units.</span></span> <span data-ttu-id="939ba-131">Power Automate が必要です。さらに必要な場合は、追加できます。</span><span class="sxs-lookup"><span data-stu-id="939ba-131">Power Automate is required - if you need more you can add it.</span></span> <span data-ttu-id="939ba-132">購入した 300 以上のライセンスに割り当てられた 1M クレジット。</span><span class="sxs-lookup"><span data-stu-id="939ba-132">1M credits allocated for 300+ licenses purchased.</span></span> <span data-ttu-id="939ba-133">また、クレジットを個別に購入できます。</span><span class="sxs-lookup"><span data-stu-id="939ba-133">You can also purchase credits separately.</span></span> | <span data-ttu-id="939ba-134">モデルは、ラテン語のすべての言語で動作します。</span><span class="sxs-lookup"><span data-stu-id="939ba-134">Models work on all latin alphabet languages.</span></span> <span data-ttu-id="939ba-135">英語に加えて、ドイツ語、スウェーデン語、フランス語、スペイン語、イタリア語、ポルトガル語。</span><span class="sxs-lookup"><span data-stu-id="939ba-135">In addition to English: German, Swedish, French, Spanish, Italian, and Portuguese.</span></span> |
| <span data-ttu-id="939ba-136">既定の共通データ サービス環境に対して準備</span><span class="sxs-lookup"><span data-stu-id="939ba-136">Provisioned against the default common data service environment</span></span>| <span data-ttu-id="939ba-137">容量の制限はありません。</span><span class="sxs-lookup"><span data-stu-id="939ba-137">Does not have capacity restrictions.</span></span> |

<span data-ttu-id="939ba-138">コンテンツを理解するには、2 つの異なる方法があります。</span><span class="sxs-lookup"><span data-stu-id="939ba-138">There are two different ways of understanding your content.</span></span> <span data-ttu-id="939ba-139">使用するモデルの種類は、ファイル形式と使用例に基づいて異なります。</span><span class="sxs-lookup"><span data-stu-id="939ba-139">The model type you use is based on file format and use case:</span></span>

| <span data-ttu-id="939ba-140">フォーム処理</span><span class="sxs-lookup"><span data-stu-id="939ba-140">Form processing</span></span> | <span data-ttu-id="939ba-141">ドキュメントの理解</span><span class="sxs-lookup"><span data-stu-id="939ba-141">Document understanding</span></span> |
|:-------|:-------|
| <span data-ttu-id="939ba-142">ドキュメント ライブラリから作成</span><span class="sxs-lookup"><span data-stu-id="939ba-142">Created from document library</span></span> | <span data-ttu-id="939ba-143">コンテンツ センター (SharePoint Syntex の一部) で作成</span><span class="sxs-lookup"><span data-stu-id="939ba-143">Created in the content center, part of SharePoint Syntex</span></span> |
| <span data-ttu-id="939ba-144">AI ビルダーで作成されたモデル</span><span class="sxs-lookup"><span data-stu-id="939ba-144">Model created in AI builder</span></span> | <span data-ttu-id="939ba-145">ネイティブ インターフェイスで作成されたモデル</span><span class="sxs-lookup"><span data-stu-id="939ba-145">Model created in native interface</span></span> |
| <span data-ttu-id="939ba-146">半構造化ファイル形式に使用されます。</span><span class="sxs-lookup"><span data-stu-id="939ba-146">Used for semi-structured file formats</span></span> | <span data-ttu-id="939ba-147">非構造化ファイル形式に使用</span><span class="sxs-lookup"><span data-stu-id="939ba-147">Used for unstructured file formats</span></span> |
| <span data-ttu-id="939ba-148">Settable 分類子</span><span class="sxs-lookup"><span data-stu-id="939ba-148">Settable classifier</span></span> | <span data-ttu-id="939ba-149">トレーニング可能な分類子とオプションの抽出器</span><span class="sxs-lookup"><span data-stu-id="939ba-149">Trainable classifier with optional extractors</span></span> |
| <span data-ttu-id="939ba-150">1 つのライブラリに制限</span><span class="sxs-lookup"><span data-stu-id="939ba-150">Restricted to a single library</span></span> | <span data-ttu-id="939ba-151">複数のライブラリに適用できる</span><span class="sxs-lookup"><span data-stu-id="939ba-151">Can be applied to multiple libraries</span></span> |
| <span data-ttu-id="939ba-152">PDF、JPG、PNG 形式でのトレーニング、合計 50 MB/500 pp</span><span class="sxs-lookup"><span data-stu-id="939ba-152">Train on PDF, JPG, PNG format, total 50 MB/500 pp</span></span> | <span data-ttu-id="939ba-153">5 から 10 PDF、Office、または電子メール ファイル (負の例を含む) でトレーニングする</span><span class="sxs-lookup"><span data-stu-id="939ba-153">Train on 5-10 PDF, Office, or email files, including negative examples</span></span> |

<span data-ttu-id="939ba-154">SharePoint Syntex は、次のような Microsoft 365 コンプライアンス機能と統合されます。</span><span class="sxs-lookup"><span data-stu-id="939ba-154">SharePoint Syntex integrates with Microsoft 365 compliance features like:</span></span>

- <span data-ttu-id="939ba-155">ドキュメントの保存期間または外部イベントに基づいてレコード ポリシーを定義する保持ラベル。</span><span class="sxs-lookup"><span data-stu-id="939ba-155">Retention labels that define records policy based on document age or external events.</span></span>
- <span data-ttu-id="939ba-156">DLP、暗号化、共有、条件付きアクセス ポリシーを設定する感度ラベル。</span><span class="sxs-lookup"><span data-stu-id="939ba-156">Sensitivity labels that set DLP, encryption, sharing, and conditional access policies.</span></span>

<span data-ttu-id="939ba-157">ユーザーはラベルを適用するか、SharePoint Syntex AI モデルによって自動的に適用できます。</span><span class="sxs-lookup"><span data-stu-id="939ba-157">Users can apply labels, or they can be applied automatically by SharePoint Syntex AI models.</span></span> <span data-ttu-id="939ba-158">分析とファイル計画では、ラベルの使用状況とポリシーを拡張して管理できます。</span><span class="sxs-lookup"><span data-stu-id="939ba-158">Analytics and file plans provide scaled management of label usage and policies.</span></span>

## <a name="identify-pilot-business-scenarios-to-optimize"></a><span data-ttu-id="939ba-159">最適化するパイロット ビジネス シナリオを特定する</span><span class="sxs-lookup"><span data-stu-id="939ba-159">Identify pilot business scenarios to optimize</span></span>

<span data-ttu-id="939ba-160">組織で SharePoint Syntex を使用する準備をするには、まず、それが役立つシナリオを理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="939ba-160">To prepare for using SharePoint Syntex in your organization, you first need to understand the scenarios in which it will be useful.</span></span> <span data-ttu-id="939ba-161">この理由は、必要なモデルを決定し、モデルを適用する場所に基づいて組織を構造化する方法を決定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="939ba-161">The why helps determine what model will be needed, and how to structure your org based on where the model will be applied.</span></span> <span data-ttu-id="939ba-162">ドキュメントの理解が組織に役立ついくつかのシナリオを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="939ba-162">Here are a few scenarios where document understanding can help your organization:</span></span>

- <span data-ttu-id="939ba-163">コンテンツ処理: 契約、作業明細書、その他のフォームのようなドキュメントを処理します。</span><span class="sxs-lookup"><span data-stu-id="939ba-163">Content processing: Process contracts, statements of work, and other form-like documents.</span></span> <span data-ttu-id="939ba-164">フォームを入力し、フィールドを理解してマップし、フォームを実行して自動的にデータを収集するモデルをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="939ba-164">Intake the forms, train the model to understand and map the fields, and then run your forms through to automatically collect the data.</span></span> <span data-ttu-id="939ba-165">詳細については、「フォーム処理の [概要」を参照してください](form-processing-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="939ba-165">For more information, see [Form processing overview](form-processing-overview.md).</span></span>
- <span data-ttu-id="939ba-166">請求書の分析: 請求書から関連する詳細を引き出し、ポリシーに準拠している、または適切に処理されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="939ba-166">Invoice analysis: Pull out the relevant details from your invoices and make sure they're complying with policy or are being processed appropriately.</span></span>

<span data-ttu-id="939ba-167">SharePoint Syntex が組織を支援する方法について考えます。</span><span class="sxs-lookup"><span data-stu-id="939ba-167">Think about ways that SharePoint Syntex can help your organization:</span></span>

- <span data-ttu-id="939ba-168">ビジネス プロセスを自動化する</span><span class="sxs-lookup"><span data-stu-id="939ba-168">Automate business processes</span></span>
- <span data-ttu-id="939ba-169">検索の精度を向上させる</span><span class="sxs-lookup"><span data-stu-id="939ba-169">Improve search accuracy</span></span>
- <span data-ttu-id="939ba-170">コンプライアンス リスクを管理する</span><span class="sxs-lookup"><span data-stu-id="939ba-170">Manage compliance risk</span></span>

### <a name="form-processing-scenario-example"></a><span data-ttu-id="939ba-171">フォーム処理シナリオの例</span><span class="sxs-lookup"><span data-stu-id="939ba-171">Form processing scenario example</span></span>

<span data-ttu-id="939ba-172">たとえば、SharePoint Syntex 機能と Power Automate 機能を使用して、請求書を追跡および監視するプロセスを設定できます。</span><span class="sxs-lookup"><span data-stu-id="939ba-172">For example, you can set up a process using SharePoint Syntex and Power Automate features to track and monitor invoices.</span></span>

1. <span data-ttu-id="939ba-173">請求書のドキュメントを格納するライブラリを設定します。</span><span class="sxs-lookup"><span data-stu-id="939ba-173">Set up a library to store the invoice documents.</span></span>
1. <span data-ttu-id="939ba-174">ドキュメント内のフィールドを認識するようにモデルをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="939ba-174">Train the model to recognize fields in the documents.</span></span>
1. <span data-ttu-id="939ba-175">追跡するフィールドをリストに抽出します。</span><span class="sxs-lookup"><span data-stu-id="939ba-175">Extract the fields you want to track into a list.</span></span>
1. <span data-ttu-id="939ba-176">次のような特定のイベントについて通知するフローを設定します。</span><span class="sxs-lookup"><span data-stu-id="939ba-176">Set up a flow to notify you for specific events, such as:</span></span>
    - <span data-ttu-id="939ba-177">新しい請求書が追加されます。</span><span class="sxs-lookup"><span data-stu-id="939ba-177">A new invoice is added.</span></span>
    - <span data-ttu-id="939ba-178">請求書が期限を過ぎた。</span><span class="sxs-lookup"><span data-stu-id="939ba-178">An invoice is past its due date.</span></span>
    - <span data-ttu-id="939ba-179">請求書は、自動承認金額より大きい金額です。</span><span class="sxs-lookup"><span data-stu-id="939ba-179">An invoice is for an amount that's larger than your automatic approval amount.</span></span>

![SharePoint Syntex と Power Automate を使用して請求書を追跡および監視する](../media/content-understanding/process-invoices-flow.png)

<span data-ttu-id="939ba-181">このシナリオを自動化すると、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="939ba-181">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="939ba-182">手動で行う代わりに、請求書からデータを自動的に抽出することで、時間と支払いを節約できます。</span><span class="sxs-lookup"><span data-stu-id="939ba-182">Save time and money by automatically extracting data from the invoices instead of doing it manually.</span></span>
- <span data-ttu-id="939ba-183">ワークフローを使用して請求書を処理し、問題を通知することにより、潜在的なエラーを削減し、コンプライアンスを強化します。</span><span class="sxs-lookup"><span data-stu-id="939ba-183">Reduce potential errors and ensure better compliance by using workflows to act on the invoices and notify you of any issues.</span></span>

### <a name="document-understanding-scenario-example"></a><span data-ttu-id="939ba-184">ドキュメント理解シナリオの例</span><span class="sxs-lookup"><span data-stu-id="939ba-184">Document understanding scenario example</span></span>

<span data-ttu-id="939ba-185">別の例として、会社が他の会社や個人と締結している契約を識別するプロセスを設定できます。</span><span class="sxs-lookup"><span data-stu-id="939ba-185">As another example, you can set up a process to identify contracts that your company has with other companies or individuals.</span></span> <span data-ttu-id="939ba-186">クライアント名、手数料、日付、その他の重要な情報などの重要な情報をコントラクトから抽出するモデルを設定し、それをすぐに表示できるフィールドとしてライブラリに追加できます。</span><span class="sxs-lookup"><span data-stu-id="939ba-186">You can set up a model to extract key information from those contracts, such as the client name, fees, dates, or other important information, and add that to the library as fields you can quickly view.</span></span> <span data-ttu-id="939ba-187">また、ドキュメント ライブラリに保持ラベルを適用して、ビジネス規制に適切に準拠するために、特定の期間の前に契約を削除できないことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="939ba-187">And you can apply a retention label on the document library to ensure that contracts cannot be deleted before a specific length of time for appropriate compliance with your business regulations.</span></span>

1. <span data-ttu-id="939ba-188">コンテンツ センターから開始し、契約書の新しいドキュメント理解モデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="939ba-188">Start at the content center and create a new document understanding model for contracts.</span></span>
1. <span data-ttu-id="939ba-189">正と負の例のサンプル ドキュメントをアップロードし、契約ドキュメントを識別して結果を確認するトレーニングを実行します。</span><span class="sxs-lookup"><span data-stu-id="939ba-189">Upload sample documents for positive and negative examples, then run the training to identify contract documents and review the results.</span></span>
1. <span data-ttu-id="939ba-190">クライアント名、手数料、日付などの契約内のフィールドを識別する抽出器をトレーニングし、抽出器をテストします。</span><span class="sxs-lookup"><span data-stu-id="939ba-190">Train the extractor to identify fields in the contracts, such as the client name, fee, and date, and then test the extractor.</span></span>
1. <span data-ttu-id="939ba-191">モデルが完了したら、コントラクトをアップロードできるライブラリにモデルを適用します。</span><span class="sxs-lookup"><span data-stu-id="939ba-191">When the model is complete, apply the model to a library where you can upload contracts.</span></span>
1. <span data-ttu-id="939ba-192">日付フィールドに保持ラベルを適用して、組織が契約に必要な期間、契約書をライブラリに保持します。</span><span class="sxs-lookup"><span data-stu-id="939ba-192">Apply a retention label to the date field, so that contracts are retained in the library for the length of time your organization requires for contracts.</span></span>

![SharePoint Syntex と保持ラベルとの契約を追跡および監視する](../media/content-understanding/process-contracts-flow.png)

<span data-ttu-id="939ba-194">このシナリオを自動化すると、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="939ba-194">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="939ba-195">手動で行う代わりに、契約から自動的にデータを抽出することで、時間と支払いを節約できます。</span><span class="sxs-lookup"><span data-stu-id="939ba-195">Save time and money by automatically extracting data from the contracts instead of doing it manually.</span></span>
- <span data-ttu-id="939ba-196">保持ラベルを使用して契約が適切に保持され、コンプライアンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="939ba-196">Ensure better compliance by using retention labels to ensure that the contracts are retained appropriately.</span></span>

### <a name="tips-for-identifying-scenarios"></a><span data-ttu-id="939ba-197">シナリオを特定するためのヒント</span><span class="sxs-lookup"><span data-stu-id="939ba-197">Tips for identifying scenarios</span></span>

<span data-ttu-id="939ba-198">どのビジネス シナリオを検討する必要があるのか考える場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="939ba-198">When thinking about which business scenarios to consider, ask yourself the following questions:</span></span>

- <span data-ttu-id="939ba-199">それは実際の問題を解決しますか?</span><span class="sxs-lookup"><span data-stu-id="939ba-199">Does it solve a real problem?</span></span>
- <span data-ttu-id="939ba-200">広く使用されるか、広く影響を与えるのか。</span><span class="sxs-lookup"><span data-stu-id="939ba-200">Will it be widely used or have broad impact?</span></span>
- <span data-ttu-id="939ba-201">入手できますか?</span><span class="sxs-lookup"><span data-stu-id="939ba-201">Is it obtainable?</span></span>
- <span data-ttu-id="939ba-202">成功を測定できますか?</span><span class="sxs-lookup"><span data-stu-id="939ba-202">Can you measure success?</span></span>

<span data-ttu-id="939ba-203">影響と実装の容易性に基づいてシナリオに優先順位を付ける。</span><span class="sxs-lookup"><span data-stu-id="939ba-203">Prioritize scenarios based on impact and ease of implementation.</span></span> <span data-ttu-id="939ba-204">初期フォーカス領域を簡単に実装できる影響の高いシナリオにします。</span><span class="sxs-lookup"><span data-stu-id="939ba-204">Make your initial focus area higher impact scenarios that can also be easily implemented.</span></span> <span data-ttu-id="939ba-205">実装が難しい影響の低いシナリオの優先順位を下げる。</span><span class="sxs-lookup"><span data-stu-id="939ba-205">De-prioritize lower impact scenarios that are hard to implement.</span></span>

## <a name="identify-roles--responsibilities"></a><span data-ttu-id="939ba-206">役割と責任&特定する</span><span class="sxs-lookup"><span data-stu-id="939ba-206">Identify roles & responsibilities</span></span>

<span data-ttu-id="939ba-207">組織内でモデルを構築および管理するユーザーを決定する</span><span class="sxs-lookup"><span data-stu-id="939ba-207">Determine who in your organization will build and manage the models?</span></span> <span data-ttu-id="939ba-208">次の役割が関係している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="939ba-208">The following roles might be involved:</span></span>

| <span data-ttu-id="939ba-209">SharePoint/ナレッジ管理者</span><span class="sxs-lookup"><span data-stu-id="939ba-209">SharePoint/Knowledge admin</span></span> | <span data-ttu-id="939ba-210">Power Platform 管理者</span><span class="sxs-lookup"><span data-stu-id="939ba-210">Power Platform admin</span></span> | <span data-ttu-id="939ba-211">ナレッジ マネージャー</span><span class="sxs-lookup"><span data-stu-id="939ba-211">Knowledge manager</span></span> | <span data-ttu-id="939ba-212">モデル所有者</span><span class="sxs-lookup"><span data-stu-id="939ba-212">Model owner</span></span> |
|:-------|:-------|:-------|:-------|
| <span data-ttu-id="939ba-213">AAD 役割</span><span class="sxs-lookup"><span data-stu-id="939ba-213">AAD role</span></span>| <span data-ttu-id="939ba-214">役割を追加する</span><span class="sxs-lookup"><span data-stu-id="939ba-214">ADD role</span></span> | <span data-ttu-id="939ba-215">AAD 役割</span><span class="sxs-lookup"><span data-stu-id="939ba-215">AAD role</span></span> | <span data-ttu-id="939ba-216">チャンピオン</span><span class="sxs-lookup"><span data-stu-id="939ba-216">Champions</span></span> |
| <span data-ttu-id="939ba-217">フォームの処理を構成する</span><span class="sxs-lookup"><span data-stu-id="939ba-217">Configure form processing</span></span> | <span data-ttu-id="939ba-218">フォーム処理用に共通データ サービス環境を構成する</span><span class="sxs-lookup"><span data-stu-id="939ba-218">Configure Common data service environment for form processing</span></span> | <span data-ttu-id="939ba-219">使用事例を収集する</span><span class="sxs-lookup"><span data-stu-id="939ba-219">Gather use cases</span></span> | <span data-ttu-id="939ba-220">ビジネス の使用事例を収集する</span><span class="sxs-lookup"><span data-stu-id="939ba-220">Gather business use cases</span></span> |
| <span data-ttu-id="939ba-221">コンテンツ センターとアクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="939ba-221">Manage content centers and permissions</span></span>| <span data-ttu-id="939ba-222">AIB クレジットを購入して割り当てる</span><span class="sxs-lookup"><span data-stu-id="939ba-222">Purchase and allocate AIB credits</span></span> | <span data-ttu-id="939ba-223">ベスト プラクティスの確立とモデル分析のレビュー</span><span class="sxs-lookup"><span data-stu-id="939ba-223">Establish best practices and review model analytics</span></span> | <span data-ttu-id="939ba-224">モデルの作成と適用</span><span class="sxs-lookup"><span data-stu-id="939ba-224">Create and apply models</span></span> |

<span data-ttu-id="939ba-225">ナレッジ マネージャー、ビジネス プロセス所有者、およびコンテンツ モデルの所有者は、組織内でサンプル モデルとチャンピオン導入を作成します。</span><span class="sxs-lookup"><span data-stu-id="939ba-225">Knowledge manager, Business Process Owner and Content model owner create sample models and champion adoption in the organization.</span></span>
<span data-ttu-id="939ba-226">関連する可能性があるその他のユーザー: コンプライアンス管理者、分類マネージャー。</span><span class="sxs-lookup"><span data-stu-id="939ba-226">Others who may be involved: Compliance admin, Taxonomy managers.</span></span>

<span data-ttu-id="939ba-227">モデルを構築して適用する場所</span><span class="sxs-lookup"><span data-stu-id="939ba-227">Where will they build and apply the models?</span></span> <span data-ttu-id="939ba-228">拡張できる既存のプロセスまたはリポジトリはありますか?</span><span class="sxs-lookup"><span data-stu-id="939ba-228">Are there existing processes or repositories that could be enhanced?</span></span>

- <span data-ttu-id="939ba-229">フォーム処理: フォーム処理アクションを取得するサイトを決定します。</span><span class="sxs-lookup"><span data-stu-id="939ba-229">Form processing: Decide which sites will get Form processing action.</span></span>
- <span data-ttu-id="939ba-230">ドキュメントの理解: ビジネス領域ごとに複数のコンテンツ センターを作成できます。</span><span class="sxs-lookup"><span data-stu-id="939ba-230">Document understanding: You can create multiple content centers for different business areas.</span></span>

## <a name="strategic-positioning"></a><span data-ttu-id="939ba-231">戦略的な位置付け</span><span class="sxs-lookup"><span data-stu-id="939ba-231">Strategic positioning</span></span>

<span data-ttu-id="939ba-232">関係者と協力して、SharePoint Syntex を使用する戦略に沿っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="939ba-232">Work with stakeholders to make sure they are aligned on the strategy for using SharePoint Syntex.</span></span> <span data-ttu-id="939ba-233">この位置付けに役立つ次のリソースを調査して提供します。</span><span class="sxs-lookup"><span data-stu-id="939ba-233">Research and provide the following resources to help with this positioning:</span></span>

- <span data-ttu-id="939ba-234">ビジネス成果:</span><span class="sxs-lookup"><span data-stu-id="939ba-234">Business outcomes:</span></span>
  - <span data-ttu-id="939ba-235">潜在的な会計結果</span><span class="sxs-lookup"><span data-stu-id="939ba-235">Potential fiscal outcomes</span></span>
  - <span data-ttu-id="939ba-236">潜在的な機敏性の結果</span><span class="sxs-lookup"><span data-stu-id="939ba-236">Potential agility outcomes</span></span>
  - <span data-ttu-id="939ba-237">ビジネス成果テンプレート</span><span class="sxs-lookup"><span data-stu-id="939ba-237">Business outcome template</span></span>
- <span data-ttu-id="939ba-238">関係者/エグゼクティブ スポンサーのバイイン/アラインメント</span><span class="sxs-lookup"><span data-stu-id="939ba-238">Stakeholders/Exec sponsor buy-in/alignment</span></span>
  - <span data-ttu-id="939ba-239">ビジネス ケース デッキ</span><span class="sxs-lookup"><span data-stu-id="939ba-239">Business case decks</span></span>
  - <span data-ttu-id="939ba-240">財務モデル</span><span class="sxs-lookup"><span data-stu-id="939ba-240">Financial models</span></span>
  - <span data-ttu-id="939ba-241">会社の準備 - カルチャ</span><span class="sxs-lookup"><span data-stu-id="939ba-241">Company readiness - culture</span></span>

## <a name="identify-stakeholders"></a><span data-ttu-id="939ba-242">関係者の特定</span><span class="sxs-lookup"><span data-stu-id="939ba-242">Identify stakeholders</span></span>

<span data-ttu-id="939ba-243">プロジェクトの関係者を特定します。</span><span class="sxs-lookup"><span data-stu-id="939ba-243">Identify the stakeholders for your project.</span></span>

|<span data-ttu-id="939ba-244">ロール</span><span class="sxs-lookup"><span data-stu-id="939ba-244">Role</span></span> |<span data-ttu-id="939ba-245">責任</span><span class="sxs-lookup"><span data-stu-id="939ba-245">Responsibilities</span></span> |<span data-ttu-id="939ba-246">部門</span><span class="sxs-lookup"><span data-stu-id="939ba-246">Department</span></span> |
|:-------|:-------|:--------|
| <span data-ttu-id="939ba-247">エグゼクティブ スポンサー</span><span class="sxs-lookup"><span data-stu-id="939ba-247">Executive sponsor(s)</span></span>   | <span data-ttu-id="939ba-248">会社に高レベルのビジョンと価値を伝える</span><span class="sxs-lookup"><span data-stu-id="939ba-248">Communicate high-level vision and values to the company</span></span>   |  <span data-ttu-id="939ba-249">エグゼクティブ リーダー</span><span class="sxs-lookup"><span data-stu-id="939ba-249">Executive leadership</span></span>   |
| <span data-ttu-id="939ba-250">プロジェクト リード</span><span class="sxs-lookup"><span data-stu-id="939ba-250">Project lead(s)</span></span> | <span data-ttu-id="939ba-251">起動の実行とロールアウトプロセス全体を監視する</span><span class="sxs-lookup"><span data-stu-id="939ba-251">Oversee the entire launch execution and rollout process</span></span> | <span data-ttu-id="939ba-252">プロジェクト管理</span><span class="sxs-lookup"><span data-stu-id="939ba-252">Project management</span></span> |
| <span data-ttu-id="939ba-253">ナレッジ管理者</span><span class="sxs-lookup"><span data-stu-id="939ba-253">Knowledge administrators</span></span>| <span data-ttu-id="939ba-254">コンテンツ センターの作成と管理</span><span class="sxs-lookup"><span data-stu-id="939ba-254">Create and manage the content centers</span></span> | <span data-ttu-id="939ba-255">IT 部門または他の部門</span><span class="sxs-lookup"><span data-stu-id="939ba-255">IT or other department</span></span>|
| <span data-ttu-id="939ba-256">コンテンツ管理者とモデル所有者</span><span class="sxs-lookup"><span data-stu-id="939ba-256">Content managers and model owners</span></span>| <span data-ttu-id="939ba-257">使用事例の収集とモデルの作成と適用</span><span class="sxs-lookup"><span data-stu-id="939ba-257">Gather use cases and create and apply models</span></span> | <span data-ttu-id="939ba-258">任意の部署</span><span class="sxs-lookup"><span data-stu-id="939ba-258">Any department</span></span>|
| <span data-ttu-id="939ba-259">チャンピオン</span><span class="sxs-lookup"><span data-stu-id="939ba-259">Champions</span></span> | <span data-ttu-id="939ba-260">オブジェクト処理の助けと管理</span><span class="sxs-lookup"><span data-stu-id="939ba-260">Help evangelize and manage objection handling</span></span> | <span data-ttu-id="939ba-261">任意の部署 (スタッフ)</span><span class="sxs-lookup"><span data-stu-id="939ba-261">Any department (staff)</span></span> |
| <span data-ttu-id="939ba-262">テナント管理者</span><span class="sxs-lookup"><span data-stu-id="939ba-262">Tenant administrator</span></span> | <span data-ttu-id="939ba-263">テナント レベルの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="939ba-263">Configure tenant-level settings</span></span> | <span data-ttu-id="939ba-264">IT 部門</span><span class="sxs-lookup"><span data-stu-id="939ba-264">IT department</span></span>|
| <span data-ttu-id="939ba-265">Power Platform 管理者</span><span class="sxs-lookup"><span data-stu-id="939ba-265">Power Platform administrator</span></span>| <span data-ttu-id="939ba-266">共通データ サービス環境を構成する</span><span class="sxs-lookup"><span data-stu-id="939ba-266">Configure common data services environment</span></span> | <span data-ttu-id="939ba-267">IT 部門</span><span class="sxs-lookup"><span data-stu-id="939ba-267">IT department</span></span>|

> [!Note]
> <span data-ttu-id="939ba-268">ロールアウトを通じてこれらの各役割を満たすことをお勧めしますが、特定のソリューションを開始するためにそれらのすべての役割を必要としない場合があります。</span><span class="sxs-lookup"><span data-stu-id="939ba-268">Though we recommend having each of these roles fulfilled throughout your rollout, you may find that you don't require them all to get started with your identified solution.</span></span>

## <a name="readiness-checklist"></a><span data-ttu-id="939ba-269">準備チェックリスト</span><span class="sxs-lookup"><span data-stu-id="939ba-269">Readiness checklist</span></span>

<span data-ttu-id="939ba-270">SharePoint Syntex を実装する準備をするには、次の必要があります。</span><span class="sxs-lookup"><span data-stu-id="939ba-270">To get ready for implementing SharePoint Syntex, you need to:</span></span>

![コンテンツを理解する準備](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. <span data-ttu-id="939ba-272">終了状態を計画する</span><span class="sxs-lookup"><span data-stu-id="939ba-272">Plan the end state</span></span>
    - <span data-ttu-id="939ba-273">ドキュメント理解モデルは、終わりではなく手段です。</span><span class="sxs-lookup"><span data-stu-id="939ba-273">Document understanding models are the means, not the end.</span></span>
    - <span data-ttu-id="939ba-274">抽出されたメタデータの値を次の方法で活用する計画を立てします。</span><span class="sxs-lookup"><span data-stu-id="939ba-274">Plan for harnessing the value of extracted metadata with:</span></span>
      - <span data-ttu-id="939ba-275">検索</span><span class="sxs-lookup"><span data-stu-id="939ba-275">Search</span></span>
      - <span data-ttu-id="939ba-276">フィルター処理とビューの書式設定</span><span class="sxs-lookup"><span data-stu-id="939ba-276">Filtering and view formatting</span></span>
      - <span data-ttu-id="939ba-277">コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="939ba-277">Compliance</span></span>
      - <span data-ttu-id="939ba-278">オートメーション</span><span class="sxs-lookup"><span data-stu-id="939ba-278">Automation</span></span>
2. <span data-ttu-id="939ba-279">識別</span><span class="sxs-lookup"><span data-stu-id="939ba-279">Identify</span></span>
    - <span data-ttu-id="939ba-280">既存の情報アーキテクチャとコンテンツ管理機能の使用について理解します。</span><span class="sxs-lookup"><span data-stu-id="939ba-280">Understand existing information architecture and content management feature use.</span></span>
    - <span data-ttu-id="939ba-281">既存のコンテンツ タイプはモデルに対して良い候補はありますか?</span><span class="sxs-lookup"><span data-stu-id="939ba-281">Are any existing content types good candidates for models?</span></span>
    - <span data-ttu-id="939ba-282">メタデータによって改善される既存のプロセス</span><span class="sxs-lookup"><span data-stu-id="939ba-282">What existing processes would be improved by metadata?</span></span>
3. <span data-ttu-id="939ba-283">デザイン</span><span class="sxs-lookup"><span data-stu-id="939ba-283">Design</span></span>
    - <span data-ttu-id="939ba-284">情報アーキテクチャ、管理されたメタデータ、およびコンテンツ タイプに対するアプローチを設計する</span><span class="sxs-lookup"><span data-stu-id="939ba-284">Design your approach to information architecture, managed metadata and content types</span></span>
    - <span data-ttu-id="939ba-285">定義、作成、管理のプロセスを設計します。</span><span class="sxs-lookup"><span data-stu-id="939ba-285">Design the process for definition, creation, management.</span></span>

## <a name="engage-your-organization"></a><span data-ttu-id="939ba-286">組織を関与する</span><span class="sxs-lookup"><span data-stu-id="939ba-286">Engage your organization</span></span>

1. <span data-ttu-id="939ba-287">利害関係の所有者を特定し、シナリオを確認し、プロジェクト計画を作成します。</span><span class="sxs-lookup"><span data-stu-id="939ba-287">Identify stake holders, confirm scenarios, and develop project plan.</span></span>
1. <span data-ttu-id="939ba-288">設定を構成し、ライセンスを適用します。</span><span class="sxs-lookup"><span data-stu-id="939ba-288">Configure settings and apply licenses.</span></span>
1. <span data-ttu-id="939ba-289">認識とトレーニングを開始する – チャンピオンを募集します。</span><span class="sxs-lookup"><span data-stu-id="939ba-289">Begin awareness and training – Recruit Champions.</span></span>
1. <span data-ttu-id="939ba-290">段階に分け展開します。</span><span class="sxs-lookup"><span data-stu-id="939ba-290">Roll out in stages.</span></span>  
1. <span data-ttu-id="939ba-291">フィードバックを収集し、反復処理を行います。</span><span class="sxs-lookup"><span data-stu-id="939ba-291">Gather feedback and iterate.</span></span>
1. <span data-ttu-id="939ba-292">利用状況が増えるにつれて、必要に応じて AI ビルダー クレジットのプランが拡大します。</span><span class="sxs-lookup"><span data-stu-id="939ba-292">As usage grows plan for any AI Builder credits as needed.</span></span>
