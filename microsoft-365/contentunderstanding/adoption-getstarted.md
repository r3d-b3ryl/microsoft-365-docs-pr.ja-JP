---
title: 'Microsoft SharePoint Syntex 導入: 概要'
description: ビジネス上の問題の解決に役立SharePoint Syntex を組織で使用および実装する方法について学習します。
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
ms.openlocfilehash: e88a7de1c81995b878dbf8a9308fbc774583289e
ms.sourcegitcommit: 8950d3cb0f3087be7105e370ed02c7a575d00ec2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2021
ms.locfileid: "50597060"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a><span data-ttu-id="c394a-103">Microsoft SharePoint Syntex 導入: 概要</span><span class="sxs-lookup"><span data-stu-id="c394a-103">Microsoft SharePoint Syntex adoption: Get started</span></span>

<span data-ttu-id="c394a-104">Syntex で利用可能なインテリジェント コンテンツ サービスは、次SharePoint 3 つの部分を持つと考えてください。</span><span class="sxs-lookup"><span data-stu-id="c394a-104">Think of the intelligent content services available in SharePoint Syntex as having three parts:</span></span>

- <span data-ttu-id="c394a-105">**コンテンツの理解: コード** なし AI モデルを作成してコンテンツから情報を分類および抽出し、ナレッジの検出と再利用のためにメタデータを自動的に適用します。</span><span class="sxs-lookup"><span data-stu-id="c394a-105">**Content understanding:** create no-code AI models to classify and extract information from content to automatically apply metadata for knowledge discovery and reuse.</span></span> <span data-ttu-id="c394a-106">詳しくは、コンテンツ [の理解に関するページを参照してください](document-understanding-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c394a-106">Learn more about [content understanding](document-understanding-overview.md).</span></span>
- <span data-ttu-id="c394a-107">**コンテンツ処理:** コンテンツのキャプチャ、取り込み、および分類を自動化し、コンテンツ中心のプロセスをPower Automate。</span><span class="sxs-lookup"><span data-stu-id="c394a-107">**Content processing:** Automate capture, ingestion, and categorization of content and streamline content-centric processes using Power Automate.</span></span> <span data-ttu-id="c394a-108">コンテンツ処理について [詳しくは、次のページを参照してください](form-processing-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c394a-108">Learn more about [content processing](form-processing-overview.md).</span></span>
- <span data-ttu-id="c394a-109">**コンテンツのコンプライアンス:** Microsoft Information Protection との統合によるセキュリティとガバナンスを向上させるために、コンテンツを制御および管理します。</span><span class="sxs-lookup"><span data-stu-id="c394a-109">**Content compliance:** Control and manage content to improve security and governance with integration to Microsoft Information Protection.</span></span>

<span data-ttu-id="c394a-110">新しい AI サービスと機能を使用すると、コンテンツの理解と分類アプリを、Syntex を使用してコンテンツ管理フローに直接SharePointできます。</span><span class="sxs-lookup"><span data-stu-id="c394a-110">With new AI services and capabilities, you can build content understanding and classification apps directly into the content management flow using SharePoint Syntex.</span></span> <span data-ttu-id="c394a-111">コンテンツを理解するには、2 つの異なる方法があります。</span><span class="sxs-lookup"><span data-stu-id="c394a-111">There are two different ways of understanding your content.</span></span> <span data-ttu-id="c394a-112">使用するモデルの種類は、ファイル形式と使用例に基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="c394a-112">The model type you use is based on file format and use case:</span></span>

| <span data-ttu-id="c394a-113">フォーム処理</span><span class="sxs-lookup"><span data-stu-id="c394a-113">Form processing</span></span> | <span data-ttu-id="c394a-114">ドキュメント理解</span><span class="sxs-lookup"><span data-stu-id="c394a-114">Document understanding</span></span> |
|:-------|:-------|
| <span data-ttu-id="c394a-115">ドキュメント ライブラリから作成されます。</span><span class="sxs-lookup"><span data-stu-id="c394a-115">Created from document library.</span></span> | <span data-ttu-id="c394a-116">コンテンツ センター(Syntex の一部SharePointされます。</span><span class="sxs-lookup"><span data-stu-id="c394a-116">Created in the content center, part of SharePoint Syntex.</span></span> |
| <span data-ttu-id="c394a-117">AI ビルダーで作成されたモデル。</span><span class="sxs-lookup"><span data-stu-id="c394a-117">Model created in AI builder.</span></span> | <span data-ttu-id="c394a-118">ネイティブ インターフェイスで作成されたモデル。</span><span class="sxs-lookup"><span data-stu-id="c394a-118">Model created in native interface.</span></span> |
| <span data-ttu-id="c394a-119">半構造化ファイル形式に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c394a-119">Used for semi-structured file formats.</span></span> | <span data-ttu-id="c394a-120">非構造化ファイル形式に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c394a-120">Used for unstructured file formats.</span></span> |
| <span data-ttu-id="c394a-121">Settable 分類子。</span><span class="sxs-lookup"><span data-stu-id="c394a-121">Settable classifier.</span></span> | <span data-ttu-id="c394a-122">オプションの抽出機能を備えるトレーニング可能な分類子。</span><span class="sxs-lookup"><span data-stu-id="c394a-122">Trainable classifier with optional extractors.</span></span> |
| <span data-ttu-id="c394a-123">1 つのライブラリに制限されています。</span><span class="sxs-lookup"><span data-stu-id="c394a-123">Restricted to a single library.</span></span> | <span data-ttu-id="c394a-124">複数のライブラリに適用できます。</span><span class="sxs-lookup"><span data-stu-id="c394a-124">Can be applied to multiple libraries.</span></span> |
| <span data-ttu-id="c394a-125">PDF、JPG、PNG 形式、合計 50 MB/500 pp でトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="c394a-125">Train on PDF, JPG, PNG format, total 50 MB/500 pp.</span></span> | <span data-ttu-id="c394a-126">否定的な例を含め、5 - 10 個の PDF、Office、またはメール ファイルでトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="c394a-126">Train on 5-10 PDF, Office, or email files, including negative examples.</span></span> |

<span data-ttu-id="c394a-127">機能の詳細な比較については、「ドキュメントの理解モデルとフォーム処理モデルの違 [い」を参照してください](difference-between-document-understanding-and-form-processing-model.md)。</span><span class="sxs-lookup"><span data-stu-id="c394a-127">For a more complete comparison of the capabilities, see [Difference between document understanding and form processing models](difference-between-document-understanding-and-form-processing-model.md).</span></span>

## <a name="identify-pilot-business-scenarios-to-optimize"></a><span data-ttu-id="c394a-128">最適化するパイロット ビジネス シナリオを特定する</span><span class="sxs-lookup"><span data-stu-id="c394a-128">Identify pilot business scenarios to optimize</span></span>

<span data-ttu-id="c394a-129">組織で Syntex SharePointを使用する準備をするには、最初に役立つシナリオを理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c394a-129">To prepare for using SharePoint Syntex in your organization, you first need to understand the scenarios in which it will be useful.</span></span> <span data-ttu-id="c394a-130">"理由" は、必要なモデルを決定し、モデルを適用する場所に基づいて組織を構成する方法を決定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c394a-130">The "why" helps determine what model will be needed, and how to structure your org based on where the model will be applied.</span></span> <span data-ttu-id="c394a-131">ドキュメントの理解が組織に役立つシナリオを次に示します。</span><span class="sxs-lookup"><span data-stu-id="c394a-131">Here are a few scenarios where document understanding can help your organization:</span></span>

- <span data-ttu-id="c394a-132">**コンテンツ処理:** コントラクト、作業明細書、その他のフォームのようなドキュメントを処理します。</span><span class="sxs-lookup"><span data-stu-id="c394a-132">**Content processing:** Process contracts, statements of work, and other form-like documents.</span></span> <span data-ttu-id="c394a-133">フォームを取り込み、フィールドを理解してマップするためにモデルをトレーニングし、フォームを実行してデータを自動的に収集します。</span><span class="sxs-lookup"><span data-stu-id="c394a-133">Intake the forms, train the model to understand and map the fields, and then run your forms through to automatically collect the data.</span></span> <span data-ttu-id="c394a-134">詳細については、「フォーム処理の [概要」を参照してください](form-processing-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c394a-134">For more information, see [Form processing overview](form-processing-overview.md).</span></span>
- <span data-ttu-id="c394a-135">**請求書分析:** 請求書から関連する詳細を引き出し、ポリシーに準拠している、または適切に処理されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c394a-135">**Invoice analysis:** Pull out the relevant details from your invoices and make sure they're complying with policy or are being processed appropriately.</span></span>

<span data-ttu-id="c394a-136">Syntex を使用して組織SharePoint役立つ方法について考えます。</span><span class="sxs-lookup"><span data-stu-id="c394a-136">Think about ways that SharePoint Syntex can help your organization:</span></span>

- <span data-ttu-id="c394a-137">ビジネス プロセスの自動化</span><span class="sxs-lookup"><span data-stu-id="c394a-137">Automate business processes</span></span>
- <span data-ttu-id="c394a-138">検索の精度を向上させる</span><span class="sxs-lookup"><span data-stu-id="c394a-138">Improve search accuracy</span></span>
- <span data-ttu-id="c394a-139">コンプライアンス リスクの管理</span><span class="sxs-lookup"><span data-stu-id="c394a-139">Manage compliance risk</span></span>

<span data-ttu-id="c394a-140">検討するビジネス シナリオを考える場合は、次の質問をしてください。</span><span class="sxs-lookup"><span data-stu-id="c394a-140">When thinking about which business scenarios to consider, ask yourself the following questions:</span></span>

- <span data-ttu-id="c394a-141">それは本当の問題を解決しますか?</span><span class="sxs-lookup"><span data-stu-id="c394a-141">Does it solve a real problem?</span></span>
- <span data-ttu-id="c394a-142">広く使われるか、大きな影響を与えますか?</span><span class="sxs-lookup"><span data-stu-id="c394a-142">Will it be widely used or have broad impact?</span></span>
- <span data-ttu-id="c394a-143">取得可能ですか?</span><span class="sxs-lookup"><span data-stu-id="c394a-143">Is it obtainable?</span></span>
- <span data-ttu-id="c394a-144">成功を測定できますか?</span><span class="sxs-lookup"><span data-stu-id="c394a-144">Can you measure success?</span></span>

<span data-ttu-id="c394a-145">影響と実装の容易さに基づいてシナリオに優先順位を付ける。</span><span class="sxs-lookup"><span data-stu-id="c394a-145">Prioritize scenarios based on impact and ease of implementation.</span></span> <span data-ttu-id="c394a-146">初期フォーカス領域を簡単に実装できる影響の高いシナリオにします。</span><span class="sxs-lookup"><span data-stu-id="c394a-146">Make your initial focus area higher impact scenarios that can also be easily implemented.</span></span> <span data-ttu-id="c394a-147">実装が難しい影響の低いシナリオの優先順位を下げる。</span><span class="sxs-lookup"><span data-stu-id="c394a-147">De-prioritize lower impact scenarios that are hard to implement.</span></span>

<span data-ttu-id="c394a-148">次のシナリオ例を使用して、組織で Syntex を使用する方法SharePointを確認します。</span><span class="sxs-lookup"><span data-stu-id="c394a-148">Use the following example scenarios to prompt ideas about how you can use SharePoint Syntex in your organization.</span></span>

### <a name="scenario-track-data-from-invoices-with-form-processing"></a><span data-ttu-id="c394a-149">シナリオ: フォーム処理を使用して請求書からデータを追跡する</span><span class="sxs-lookup"><span data-stu-id="c394a-149">Scenario: Track data from invoices with form processing</span></span>

<span data-ttu-id="c394a-150">たとえば、Syntex および他の機能を使用SharePoint、Power Automateを設定して請求書を追跡および監視できます。</span><span class="sxs-lookup"><span data-stu-id="c394a-150">For example, you can set up a process using SharePoint Syntex and Power Automate features to track and monitor invoices.</span></span>

1. <span data-ttu-id="c394a-151">請求書ドキュメントを格納するライブラリを設定します。</span><span class="sxs-lookup"><span data-stu-id="c394a-151">Set up a library to store the invoice documents.</span></span>
1. <span data-ttu-id="c394a-152">ドキュメント内のフィールドを認識するようにモデルをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="c394a-152">Train the model to recognize fields in the documents.</span></span>
1. <span data-ttu-id="c394a-153">追跡するフィールドをリストに抽出します。</span><span class="sxs-lookup"><span data-stu-id="c394a-153">Extract the fields you want to track into a list.</span></span>
1. <span data-ttu-id="c394a-154">次のような特定のイベントについて通知するフローを設定します。</span><span class="sxs-lookup"><span data-stu-id="c394a-154">Set up a flow to notify you for specific events, such as:</span></span>
    - <span data-ttu-id="c394a-155">新しい請求書が追加されます。</span><span class="sxs-lookup"><span data-stu-id="c394a-155">A new invoice is added.</span></span>
    - <span data-ttu-id="c394a-156">請求書が期日を過ぎた。</span><span class="sxs-lookup"><span data-stu-id="c394a-156">An invoice is past its due date.</span></span>
    - <span data-ttu-id="c394a-157">請求書は、自動承認金額よりも大きい金額です。</span><span class="sxs-lookup"><span data-stu-id="c394a-157">An invoice is for an amount that's larger than your automatic approval amount.</span></span>

![Syntex とデータを使用して請求書SharePoint追跡Power Automate](../media/content-understanding/process-invoices-flow.png)

<span data-ttu-id="c394a-159">このシナリオを自動化すると、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="c394a-159">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="c394a-160">手動で行う代わりに、請求書からデータを自動的に抽出することで、時間と資金を節約できます。</span><span class="sxs-lookup"><span data-stu-id="c394a-160">Save time and money by automatically extracting data from the invoices instead of doing it manually.</span></span>
- <span data-ttu-id="c394a-161">ワークフローを使用して請求書をチェックし、問題を通知することで、潜在的なエラーを減らし、コンプライアンスを強化します。</span><span class="sxs-lookup"><span data-stu-id="c394a-161">Reduce potential errors and ensure better compliance by using workflows to check invoices and notify you of any issues.</span></span>

### <a name="scenario-track-information-from-contracts-with-document-understanding"></a><span data-ttu-id="c394a-162">シナリオ: ドキュメントを理解して契約からの情報を追跡する</span><span class="sxs-lookup"><span data-stu-id="c394a-162">Scenario: Track information from contracts with document understanding</span></span>

<span data-ttu-id="c394a-163">別の例として、会社が他の会社や個人との契約を特定するプロセスを設定できます。</span><span class="sxs-lookup"><span data-stu-id="c394a-163">As another example, you can set up a process to identify contracts your company has with other companies or individuals.</span></span> <span data-ttu-id="c394a-164">クライアント名、手数料、日付、その他の重要な情報など、それらの契約から重要な情報を抽出し、すぐに表示できるフィールドとしてライブラリに情報を追加するモデルを設定します。</span><span class="sxs-lookup"><span data-stu-id="c394a-164">Set up a model to extract key information from those contracts, such as the client name, fees, dates, or other important information, and add the information to the library as fields you can quickly view.</span></span> <span data-ttu-id="c394a-165">ドキュメント ライブラリに保持ラベルを適用して、ビジネス規制に適切に準拠するために、特定の期間前に契約を削除できません。</span><span class="sxs-lookup"><span data-stu-id="c394a-165">Apply a retention label on the document library to ensure that contracts can't be deleted before a specific length of time for appropriate compliance with your business regulations.</span></span>

1. <span data-ttu-id="c394a-166">コンテンツ センターから開始し、契約の新しいドキュメント理解モデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="c394a-166">Start at the content center and create a new document understanding model for contracts.</span></span>
1. <span data-ttu-id="c394a-167">アップロード例のサンプル ドキュメントを作成し、トレーニングを実行して契約ドキュメントを特定し、結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="c394a-167">Upload sample documents for positive and negative examples, then run the training to identify contract documents and review the results.</span></span>
1. <span data-ttu-id="c394a-168">抽出プログラムをトレーニングして、クライアント名、手数料、日付などのコントラクト内のフィールドを識別し、抽出プログラムをテストします。</span><span class="sxs-lookup"><span data-stu-id="c394a-168">Train the extractor to identify fields in the contracts, such as the client name, fee, and date, and then test the extractor.</span></span>
1. <span data-ttu-id="c394a-169">モデルが完了したら、契約書をアップロードできるライブラリにモデルを適用します。</span><span class="sxs-lookup"><span data-stu-id="c394a-169">When the model is complete, apply the model to a library where you can upload contracts.</span></span>
1. <span data-ttu-id="c394a-170">保持ラベルを日付フィールドに適用して、必要な期間、契約がライブラリに保持されます。</span><span class="sxs-lookup"><span data-stu-id="c394a-170">Apply a retention label to the date field, so that contracts are retained in the library for the required length of time.</span></span>

![Syntex および保持ラベルを使用して契約SharePoint追跡および監視する](../media/content-understanding/process-contracts-flow.png)

<span data-ttu-id="c394a-172">このシナリオを自動化すると、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="c394a-172">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="c394a-173">手動で行う代わりに、契約からデータを自動的に抽出することで、時間と資金を節約できます。</span><span class="sxs-lookup"><span data-stu-id="c394a-173">Save time and money by automatically extracting data from the contracts instead of doing it manually.</span></span>
- <span data-ttu-id="c394a-174">保持ラベルを使用して、契約が適切に保持されるのを確認して、コンプライアンスを強化します。</span><span class="sxs-lookup"><span data-stu-id="c394a-174">Ensure better compliance by using retention labels to ensure that the contracts are retained appropriately.</span></span>

### <a name="scenario-avoid-risk-with-records-management-document-governance-and-compliance-processes-based-on-sharepoint-syntex"></a><span data-ttu-id="c394a-175">シナリオ: Syntex に基づくレコード管理、ドキュメント ガバナンス、コンプライアンス プロセスでリスクSharePointする</span><span class="sxs-lookup"><span data-stu-id="c394a-175">Scenario: Avoid risk with records management, document governance, and compliance processes based on SharePoint Syntex</span></span>

<span data-ttu-id="c394a-176">リスクを減らすことは、ほとんどの企業にとって一般的な目標です。</span><span class="sxs-lookup"><span data-stu-id="c394a-176">Reducing risks is a common goal for most companies.</span></span> <span data-ttu-id="c394a-177">以下が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="c394a-177">You might need:</span></span>

- <span data-ttu-id="c394a-178">テナント全体に情報ガバナンスを提供/適用する優れた方法。</span><span class="sxs-lookup"><span data-stu-id="c394a-178">A better way to provide/enforce information governance across your tenant.</span></span>
- <span data-ttu-id="c394a-179">プロジェクトの「レコード」と見なされるドキュメント、電子メール、その他のコミュニケーションの分類システムを改善する。</span><span class="sxs-lookup"><span data-stu-id="c394a-179">To improve the system for classification of documents, emails and other forms of communication considered ‘records’ for projects.</span></span>
- <span data-ttu-id="c394a-180">会社のポリシーに準拠するために、領収書、契約などについて監査する。</span><span class="sxs-lookup"><span data-stu-id="c394a-180">To audit receipts, contracts, and so on, to ensure compliance with company policies.</span></span>
- <span data-ttu-id="c394a-181">コンプライアンスに必要なすべてのドキュメントがプロジェクトに含まれています。</span><span class="sxs-lookup"><span data-stu-id="c394a-181">To ensure that projects have all the documentation required for compliance.</span></span>

<span data-ttu-id="c394a-182">より良いガバナンスを必要とするドキュメントとフォームをキャプチャし、適切に分類、監査、フラグを設定するために、SharePoint Syntex に準拠するためのいくつかのプロセスを設定します。</span><span class="sxs-lookup"><span data-stu-id="c394a-182">Set up some processes for compliance with SharePoint Syntex to capture and appropriately classify, audit, and flag documents and forms that need better governance.</span></span> <span data-ttu-id="c394a-183">エンド ユーザーが手動でタグSharePoint、コンプライアンス チームがガバナンス ルールとアーカイブを手動で適用するのではなく、コンテンツを自動分類するには、Syntex を使用して自動的に分類できます。</span><span class="sxs-lookup"><span data-stu-id="c394a-183">You can rely on SharePoint Syntex to auto classify content rather than relying on end users to manually tag, or the compliance team to manually apply governance rules and archiving.</span></span> <span data-ttu-id="c394a-184">また、簡単な検索エクスペリエンスを有効にし、データボリュームを管理し、レコード管理と保持ポリシーを適用し、コンプライアンスを確保し、ベスト プラクティスのアーカイブと削除を行います。</span><span class="sxs-lookup"><span data-stu-id="c394a-184">And you can enable a simplified search experience, manage data volumes, apply records management and retention policies, ensure compliance, and best practice archiving and purging practices.</span></span>

<span data-ttu-id="c394a-185">このシナリオを自動化すると、次のセキュリティを確保できます。</span><span class="sxs-lookup"><span data-stu-id="c394a-185">When you automate this scenario, you can feel secure that:</span></span>

- <span data-ttu-id="c394a-186">コンプライアンスが支持され、リスクが軽減されます。</span><span class="sxs-lookup"><span data-stu-id="c394a-186">Compliance is upheld and risk is reduced.</span></span>
- <span data-ttu-id="c394a-187">分類とレコード管理は、一貫して正確に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c394a-187">Taxonomy and records management is consistently and accurately applied.</span></span>
- <span data-ttu-id="c394a-188">コンテンツ ボリュームが制御されます。</span><span class="sxs-lookup"><span data-stu-id="c394a-188">Content volumes are controlled.</span></span>
- <span data-ttu-id="c394a-189">従業員は、適切なコンテキストで適切な情報を簡単に検出できます。</span><span class="sxs-lookup"><span data-stu-id="c394a-189">Employees can easily discover the right information in the right context.</span></span>

### <a name="scenario-capture-information-from-previously-inaccessible-documents"></a><span data-ttu-id="c394a-190">シナリオ: 以前にアクセスできないドキュメントから情報をキャプチャする</span><span class="sxs-lookup"><span data-stu-id="c394a-190">Scenario: Capture information from previously inaccessible documents</span></span>

<span data-ttu-id="c394a-191">ほとんどの組織には、法的ドキュメント、ポリシー、契約、人事ドキュメント、ガバナンス ガイドラインの大規模なリポジトリがあります。</span><span class="sxs-lookup"><span data-stu-id="c394a-191">Most organizations have large repositories of legal documents, policies, contracts, HR documents, and governance guidelines.</span></span> <span data-ttu-id="c394a-192">これらのデータ ストアを採掘して、プロジェクト、セクター、テーマ、人、地理的領域などの貴重な情報を抽出します。</span><span class="sxs-lookup"><span data-stu-id="c394a-192">Mine these data stores to extract valuable information such as: projects, sectors, themes, people, geographical areas, and so on.</span></span>

<span data-ttu-id="c394a-193">たとえば、人事担当ディレクターは、履歴書、人事ポリシー、その他のフォームを含むすべての人事ドキュメントにすばやくアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c394a-193">For example, an HR director needs to quickly access all HR documents – including resumes, HR policies, and other forms.</span></span> <span data-ttu-id="c394a-194">また、ドキュメントを手動でふるいにかけることなく、履歴書や他の人事関連のドキュメントから必要な情報をすばやく特定したいと考える必要があります。</span><span class="sxs-lookup"><span data-stu-id="c394a-194">And they want to quickly identify necessary information from resumes and other HR-related documents without manually sifting through the documents.</span></span> <span data-ttu-id="c394a-195">何千もの履歴書、人事ポリシー、および複数のサイトに広がる可能性があるその他のドキュメントを手動で確認することなく、必要な情報をすばやく見つけ出すソリューションを探しています。</span><span class="sxs-lookup"><span data-stu-id="c394a-195">They’re looking for a solution that allows them to quickly find the information they need without having to manually look through thousands of resumes, HR policies, and other documentation that may be spread across several sites.</span></span>

<span data-ttu-id="c394a-196">このシナリオを自動化すると、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="c394a-196">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="c394a-197">デジタル コンテンツから知識のロックを解除します。</span><span class="sxs-lookup"><span data-stu-id="c394a-197">Unlock knowledge from digital content.</span></span>
- <span data-ttu-id="c394a-198">人事ポリシー、履歴書、販売ドキュメント、技術設計図、アカウントプランを分類し、情報を抽出します。</span><span class="sxs-lookup"><span data-stu-id="c394a-198">Classify HR policies, resumes, sales documents, technical blueprints, account plans and extract information.</span></span>
- <span data-ttu-id="c394a-199">探している正しい情報やドキュメントをすばやく見つける。</span><span class="sxs-lookup"><span data-stu-id="c394a-199">Quickly find the correct information or document that you’re looking for.</span></span>
- <span data-ttu-id="c394a-200">最新情報に即座にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c394a-200">Get instant access to the latest information.</span></span>
- <span data-ttu-id="c394a-201">検索時間を短縮します。</span><span class="sxs-lookup"><span data-stu-id="c394a-201">Reduce search times.</span></span>

### <a name="scenario-improve-data-processing-to-provide-insights--analytics"></a><span data-ttu-id="c394a-202">シナリオ: データ処理を改善し、分析に関する&提供する</span><span class="sxs-lookup"><span data-stu-id="c394a-202">Scenario: Improve data processing to provide insights & analytics</span></span>

<span data-ttu-id="c394a-203">たとえば、製薬会社は、SharePointシンテックスを使用して、FDA ドキュメントから情報を抽出して、リーダーが持っている質問に答えます。</span><span class="sxs-lookup"><span data-stu-id="c394a-203">For example, a pharmaceutical company could use SharePoint Syntex to extract information from FDA documents to answer questions that their leaders have.</span></span> <span data-ttu-id="c394a-204">回答に簡単にアクセスできると、これらの回答を生成するために必要な時間が短縮され、データの可用性が向上して、リーダーシップに関する質問に対するより正確な回答が生成されます。</span><span class="sxs-lookup"><span data-stu-id="c394a-204">Having the answers more easily accessible can reduce the time needed to produce these answers and increase the availability of data to generate more accurate answers to leadership questions.</span></span>

<span data-ttu-id="c394a-205">たとえば、プロジェクト マネージャーは、リーダーシップ チームからの製品関連の質問に対する回答をすばやく提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c394a-205">For example, a project manager needs to quickly provide answers to product-related questions from my leadership team.</span></span> <span data-ttu-id="c394a-206">1 つの統合ダッシュボードでクエリに関連する情報と指標を見つける必要があります。</span><span class="sxs-lookup"><span data-stu-id="c394a-206">They need to find information and metrics related to queries in one consolidated dashboard.</span></span> <span data-ttu-id="c394a-207">製品ラベル、製品パンフレット、その他の資料から必要な情報を抽出し、リーダーシップ チームに報告する際に使用できる統合レポートを生成するソリューションを探しています。</span><span class="sxs-lookup"><span data-stu-id="c394a-207">They’re looking for a solution that extracts the information they need from product labels, product pamphlets, and other materials and generates a consolidated report that they can use when reporting back to their leadership team.</span></span>

<span data-ttu-id="c394a-208">このシナリオを自動化すると、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="c394a-208">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="c394a-209">回答を生成する時間を短縮します。</span><span class="sxs-lookup"><span data-stu-id="c394a-209">Reduce time to produce answers.</span></span>
- <span data-ttu-id="c394a-210">データの可用性を高める。</span><span class="sxs-lookup"><span data-stu-id="c394a-210">Increase availability of data.</span></span>
- <span data-ttu-id="c394a-211">より正確な回答を提供します。</span><span class="sxs-lookup"><span data-stu-id="c394a-211">Provide more accurate answers.</span></span>

### <a name="scenario-automate-order-processing"></a><span data-ttu-id="c394a-212">シナリオ: 注文処理の自動化</span><span class="sxs-lookup"><span data-stu-id="c394a-212">Scenario: Automate order processing</span></span>

<span data-ttu-id="c394a-213">Syntex SharePointを使用すると、顧客注文の手動処理の時間を短縮できます。</span><span class="sxs-lookup"><span data-stu-id="c394a-213">With SharePoint Syntex, you can reduce the time of manual processing of customer orders.</span></span> <span data-ttu-id="c394a-214">たとえば、OCR 処理を使用して FAX、電子メール、または紙から SharePoint に注文をアップロードし、それらの注文からメタデータを抽出して、自動化されたプロセスを使用して注文を満たします。</span><span class="sxs-lookup"><span data-stu-id="c394a-214">For example, you can upload orders from fax, email, or paper into SharePoint by using OCR processing and then extract the metadata from those orders so you can fulfill them by using automated processes.</span></span>

<span data-ttu-id="c394a-215">たとえば、サプライ チェーン マネージャーは、手動データ入力によるエラーを減らしたいと考しています。</span><span class="sxs-lookup"><span data-stu-id="c394a-215">For example, a supply chain manager wants to reduce errors caused by manual data entry.</span></span> <span data-ttu-id="c394a-216">ビジネス システムに入るエラーを減らすために、受信顧客注文 (紙、FAX、または電子メール) の手動レビューとデータ入力を回避したいと考えています。</span><span class="sxs-lookup"><span data-stu-id="c394a-216">They want to avoid manual review and data entry of inbound customer orders (paper, fax, or e-mail) to reduce errors going into their business systems.</span></span> <span data-ttu-id="c394a-217">AI と機械学習の手法を適用して、受信注文情報を検証し、コア データを抽出し、注文のフルフィルメントと調整のために ERP システムに自動的にプッシュするソリューションが必要です。</span><span class="sxs-lookup"><span data-stu-id="c394a-217">They want a solution that applies AI and machine learning techniques to validate incoming order information, extract core data and automatically push it into their ERP system, for order fulfillment and reconciliation.</span></span>

<span data-ttu-id="c394a-218">このシナリオを自動化する場合は、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="c394a-218">When you automate this scenario, you can ensure that:</span></span>

- <span data-ttu-id="c394a-219">注文と出荷の精度が向上します。</span><span class="sxs-lookup"><span data-stu-id="c394a-219">Order and shipment accuracy increases.</span></span>
- <span data-ttu-id="c394a-220">注文または出荷エラーに関連する手数料またはペナルティが軽減されます。</span><span class="sxs-lookup"><span data-stu-id="c394a-220">Fees or penalties associated to order or shipment errors are reduced.</span></span>
- <span data-ttu-id="c394a-221">請求や支払いの遅延が減少します。</span><span class="sxs-lookup"><span data-stu-id="c394a-221">Delays in invoicing or payments decrease.</span></span>
- <span data-ttu-id="c394a-222">人件費が削減されます。</span><span class="sxs-lookup"><span data-stu-id="c394a-222">Personnel costs are reduced.</span></span>

### <a name="scenario-simplify-visa-renewal-process"></a><span data-ttu-id="c394a-223">シナリオ: ビザの更新プロセスを簡素化する</span><span class="sxs-lookup"><span data-stu-id="c394a-223">Scenario: Simplify visa renewal process</span></span>

<span data-ttu-id="c394a-224">SharePointSyntex は、重要な契約情報のリマインダーと更新を自動化するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c394a-224">SharePoint Syntex can help you automate reminders and renewals for key contract information.</span></span> <span data-ttu-id="c394a-225">たとえば、人事担当ディレクターは、従業員のビザが最新の日付または期限内に更新される必要があります。</span><span class="sxs-lookup"><span data-stu-id="c394a-225">For example, an HR director needs to ensure that employees’ visas are up to date and/or renewed on time.</span></span> <span data-ttu-id="c394a-226">彼らは、人々に自分のビザを更新するための簡単で直感的なプロセスを提供したいと考っています。</span><span class="sxs-lookup"><span data-stu-id="c394a-226">They want to give people a simple and intuitive process for updating their Visas.</span></span> <span data-ttu-id="c394a-227">契約から更新日を抽出し、更新日が近づいているときに従業員に自動的に通知を送信するソリューションが必要です。</span><span class="sxs-lookup"><span data-stu-id="c394a-227">They need a solution that extracts renewal dates from contracts and automatically sends employees reminders when their renewal dates are approaching.</span></span>

<span data-ttu-id="c394a-228">このシナリオを自動化する場合は、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="c394a-228">When you automate this scenario, you can ensure that:</span></span>

- <span data-ttu-id="c394a-229">コンプライアンス以外のレベルが低下します。</span><span class="sxs-lookup"><span data-stu-id="c394a-229">The levels of non-compliance are reduced.</span></span>
- <span data-ttu-id="c394a-230">手動アラームの数が減ります。</span><span class="sxs-lookup"><span data-stu-id="c394a-230">The number of manual reminders is reduced.</span></span>
- <span data-ttu-id="c394a-231">コンプライアンスに準拠しない場合の罰金の数を減らします。</span><span class="sxs-lookup"><span data-stu-id="c394a-231">The number of fines for non-compliance is reduced.</span></span>

## <a name="identify-roles--responsibilities"></a><span data-ttu-id="c394a-232">役割と責任&識別する</span><span class="sxs-lookup"><span data-stu-id="c394a-232">Identify roles & responsibilities</span></span>

<span data-ttu-id="c394a-233">組織内でモデルを構築および管理するユーザーを決定しますか?</span><span class="sxs-lookup"><span data-stu-id="c394a-233">Determine who in your organization will build and manage the models?</span></span> <span data-ttu-id="c394a-234">次の役割が関係している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c394a-234">The following roles might be involved:</span></span>

| <span data-ttu-id="c394a-235">SharePoint/ナレッジ管理者</span><span class="sxs-lookup"><span data-stu-id="c394a-235">SharePoint/Knowledge admin</span></span> | <span data-ttu-id="c394a-236">Power Platform 管理者</span><span class="sxs-lookup"><span data-stu-id="c394a-236">Power Platform admin</span></span> | <span data-ttu-id="c394a-237">知識マネージャー</span><span class="sxs-lookup"><span data-stu-id="c394a-237">Knowledge manager</span></span> | <span data-ttu-id="c394a-238">モデル所有者</span><span class="sxs-lookup"><span data-stu-id="c394a-238">Model owner</span></span> |
|:-------|:-------|:-------|:-------|
| <span data-ttu-id="c394a-239">AAD の役割</span><span class="sxs-lookup"><span data-stu-id="c394a-239">AAD role</span></span>| <span data-ttu-id="c394a-240">AAD の役割</span><span class="sxs-lookup"><span data-stu-id="c394a-240">AAD role</span></span> | <span data-ttu-id="c394a-241">AAD の役割</span><span class="sxs-lookup"><span data-stu-id="c394a-241">AAD role</span></span> | <span data-ttu-id="c394a-242">チャンピオン</span><span class="sxs-lookup"><span data-stu-id="c394a-242">Champions</span></span> |
| <span data-ttu-id="c394a-243">フォームの処理を構成する</span><span class="sxs-lookup"><span data-stu-id="c394a-243">Configure form processing</span></span> | <span data-ttu-id="c394a-244">フォーム処理用に共通データ サービス環境を構成する</span><span class="sxs-lookup"><span data-stu-id="c394a-244">Configure Common data service environment for form processing</span></span> | <span data-ttu-id="c394a-245">使用例の収集</span><span class="sxs-lookup"><span data-stu-id="c394a-245">Gather use cases</span></span> | <span data-ttu-id="c394a-246">ビジネスの使用例を収集する</span><span class="sxs-lookup"><span data-stu-id="c394a-246">Gather business use cases</span></span> |
| <span data-ttu-id="c394a-247">コンテンツ センターとアクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="c394a-247">Manage content centers and permissions</span></span>| <span data-ttu-id="c394a-248">AIB クレジットの購入と割り当て</span><span class="sxs-lookup"><span data-stu-id="c394a-248">Purchase and allocate AIB credits</span></span> | <span data-ttu-id="c394a-249">ベスト プラクティスを確立し、モデル分析を確認する</span><span class="sxs-lookup"><span data-stu-id="c394a-249">Establish best practices and review model analytics</span></span> | <span data-ttu-id="c394a-250">モデルの作成と適用</span><span class="sxs-lookup"><span data-stu-id="c394a-250">Create and apply models</span></span> |

<span data-ttu-id="c394a-251">ナレッジ マネージャー、ビジネス プロセス所有者、およびコンテンツ モデル所有者は、組織でサンプル モデルとチャンピオン導入を作成します。</span><span class="sxs-lookup"><span data-stu-id="c394a-251">Knowledge manager, Business Process Owner and Content model owner create sample models and champion adoption in the organization.</span></span>
<span data-ttu-id="c394a-252">関連する可能性があるその他のユーザー: コンプライアンス管理者、分類管理者。</span><span class="sxs-lookup"><span data-stu-id="c394a-252">Others who may be involved: Compliance admin, Taxonomy managers.</span></span>

<span data-ttu-id="c394a-253">モデルを構築して適用する場所</span><span class="sxs-lookup"><span data-stu-id="c394a-253">Where will they build and apply the models?</span></span> <span data-ttu-id="c394a-254">拡張できる既存のプロセスまたはリポジトリはありますか?</span><span class="sxs-lookup"><span data-stu-id="c394a-254">Are there existing processes or repositories that could be enhanced?</span></span>

- <span data-ttu-id="c394a-255">フォーム処理: フォーム処理アクションを取得するサイトを決定します。</span><span class="sxs-lookup"><span data-stu-id="c394a-255">Form processing: Decide which sites will get Form processing action.</span></span>
- <span data-ttu-id="c394a-256">ドキュメントの理解: 異なるビジネス領域に対して複数のコンテンツ センターを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c394a-256">Document understanding: You can create multiple content centers for different business areas.</span></span>

## <a name="strategic-positioning"></a><span data-ttu-id="c394a-257">戦略的な位置付け</span><span class="sxs-lookup"><span data-stu-id="c394a-257">Strategic positioning</span></span>

<span data-ttu-id="c394a-258">関係者と協力して、Syntex を使用する戦略に沿SharePointします。</span><span class="sxs-lookup"><span data-stu-id="c394a-258">Work with stakeholders to make sure they are aligned on the strategy for using SharePoint Syntex.</span></span> <span data-ttu-id="c394a-259">この位置付けを支援するために、次のリソースを調査して提供します。</span><span class="sxs-lookup"><span data-stu-id="c394a-259">Research and provide the following resources to help with this positioning:</span></span>

- <span data-ttu-id="c394a-260">ビジネスの成果:</span><span class="sxs-lookup"><span data-stu-id="c394a-260">Business outcomes:</span></span>
  - <span data-ttu-id="c394a-261">潜在的な財政結果</span><span class="sxs-lookup"><span data-stu-id="c394a-261">Potential fiscal outcomes</span></span>
  - <span data-ttu-id="c394a-262">潜在的な俊敏性の結果</span><span class="sxs-lookup"><span data-stu-id="c394a-262">Potential agility outcomes</span></span>
  - <span data-ttu-id="c394a-263">ビジネス結果テンプレート</span><span class="sxs-lookup"><span data-stu-id="c394a-263">Business outcome template</span></span>
- <span data-ttu-id="c394a-264">利害関係者/Exec スポンサーバイイン/アラインメント</span><span class="sxs-lookup"><span data-stu-id="c394a-264">Stakeholders/Exec sponsor buy-in/alignment</span></span>
  - <span data-ttu-id="c394a-265">ビジネス ケース デッキ</span><span class="sxs-lookup"><span data-stu-id="c394a-265">Business case decks</span></span>
  - <span data-ttu-id="c394a-266">財務モデル</span><span class="sxs-lookup"><span data-stu-id="c394a-266">Financial models</span></span>
  - <span data-ttu-id="c394a-267">会社の準備 - カルチャ</span><span class="sxs-lookup"><span data-stu-id="c394a-267">Company readiness - culture</span></span>

## <a name="identify-stakeholders"></a><span data-ttu-id="c394a-268">関係者の特定</span><span class="sxs-lookup"><span data-stu-id="c394a-268">Identify stakeholders</span></span>

<span data-ttu-id="c394a-269">プロジェクトの関係者を特定します。</span><span class="sxs-lookup"><span data-stu-id="c394a-269">Identify the stakeholders for your project.</span></span>

|<span data-ttu-id="c394a-270">ロール</span><span class="sxs-lookup"><span data-stu-id="c394a-270">Role</span></span> |<span data-ttu-id="c394a-271">責任</span><span class="sxs-lookup"><span data-stu-id="c394a-271">Responsibilities</span></span> |<span data-ttu-id="c394a-272">部署</span><span class="sxs-lookup"><span data-stu-id="c394a-272">Department</span></span> |
|:-------|:-------|:--------|
| <span data-ttu-id="c394a-273">エグゼクティブ スポンサー</span><span class="sxs-lookup"><span data-stu-id="c394a-273">Executive sponsor(s)</span></span>   | <span data-ttu-id="c394a-274">ハイレベルなビジョンと価値を会社に伝える</span><span class="sxs-lookup"><span data-stu-id="c394a-274">Communicate high-level vision and values to the company</span></span>   |  <span data-ttu-id="c394a-275">経営幹部のリーダー</span><span class="sxs-lookup"><span data-stu-id="c394a-275">Executive leadership</span></span>   |
| <span data-ttu-id="c394a-276">Projectリード</span><span class="sxs-lookup"><span data-stu-id="c394a-276">Project lead(s)</span></span> | <span data-ttu-id="c394a-277">起動の実行と展開プロセス全体を監視する</span><span class="sxs-lookup"><span data-stu-id="c394a-277">Oversee the entire launch execution and rollout process</span></span> | <span data-ttu-id="c394a-278">プロジェクト管理</span><span class="sxs-lookup"><span data-stu-id="c394a-278">Project management</span></span> |
| <span data-ttu-id="c394a-279">ナレッジ管理者</span><span class="sxs-lookup"><span data-stu-id="c394a-279">Knowledge administrators</span></span>| <span data-ttu-id="c394a-280">コンテンツ センターの作成と管理</span><span class="sxs-lookup"><span data-stu-id="c394a-280">Create and manage the content centers</span></span> | <span data-ttu-id="c394a-281">IT 部門または他の部署</span><span class="sxs-lookup"><span data-stu-id="c394a-281">IT or other department</span></span>|
| <span data-ttu-id="c394a-282">コンテンツ 管理者とモデル所有者</span><span class="sxs-lookup"><span data-stu-id="c394a-282">Content managers and model owners</span></span>| <span data-ttu-id="c394a-283">使用例を収集し、モデルを作成して適用する</span><span class="sxs-lookup"><span data-stu-id="c394a-283">Gather use cases and create and apply models</span></span> | <span data-ttu-id="c394a-284">任意の部署</span><span class="sxs-lookup"><span data-stu-id="c394a-284">Any department</span></span>|
| <span data-ttu-id="c394a-285">チャンピオン</span><span class="sxs-lookup"><span data-stu-id="c394a-285">Champions</span></span> | <span data-ttu-id="c394a-286">宣伝とクレーム処理の管理を支援する</span><span class="sxs-lookup"><span data-stu-id="c394a-286">Help evangelize and manage objection handling</span></span> | <span data-ttu-id="c394a-287">任意の部署 (スタッフ)</span><span class="sxs-lookup"><span data-stu-id="c394a-287">Any department (staff)</span></span> |
| <span data-ttu-id="c394a-288">テナント管理者</span><span class="sxs-lookup"><span data-stu-id="c394a-288">Tenant administrator</span></span> | <span data-ttu-id="c394a-289">テナント レベルの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="c394a-289">Configure tenant-level settings</span></span> | <span data-ttu-id="c394a-290">IT 部門</span><span class="sxs-lookup"><span data-stu-id="c394a-290">IT department</span></span>|
| <span data-ttu-id="c394a-291">Power プラットフォーム管理者</span><span class="sxs-lookup"><span data-stu-id="c394a-291">Power Platform administrator</span></span>| <span data-ttu-id="c394a-292">共通データ サービス環境を構成する</span><span class="sxs-lookup"><span data-stu-id="c394a-292">Configure common data services environment</span></span> | <span data-ttu-id="c394a-293">IT 部門</span><span class="sxs-lookup"><span data-stu-id="c394a-293">IT department</span></span>|

> [!Note]
> <span data-ttu-id="c394a-294">ロールアウトを通じてこれらの各役割を満たすことをお勧めしますが、特定のソリューションの開始に必要な役割は必要ない場合があります。</span><span class="sxs-lookup"><span data-stu-id="c394a-294">Though we recommend having each of these roles fulfilled throughout your rollout, you may find that you don't require them all to get started with your identified solution.</span></span>

## <a name="readiness-checklist"></a><span data-ttu-id="c394a-295">準備チェックリスト</span><span class="sxs-lookup"><span data-stu-id="c394a-295">Readiness checklist</span></span>

<span data-ttu-id="c394a-296">Syntex を実装する準備をSharePointするには、次の必要があります。</span><span class="sxs-lookup"><span data-stu-id="c394a-296">To get ready for implementing SharePoint Syntex, you need to:</span></span>

![コンテンツ理解の準備](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. <span data-ttu-id="c394a-298">終了状態を計画する</span><span class="sxs-lookup"><span data-stu-id="c394a-298">Plan the end state</span></span>
    - <span data-ttu-id="c394a-299">ドキュメント理解モデルは、最後ではなく手段です。</span><span class="sxs-lookup"><span data-stu-id="c394a-299">Document understanding models are the means, not the end.</span></span>
    - <span data-ttu-id="c394a-300">抽出されたメタデータの値を次の値で活用する計画を立て、</span><span class="sxs-lookup"><span data-stu-id="c394a-300">Plan for harnessing the value of extracted metadata with:</span></span>
      - <span data-ttu-id="c394a-301">検索</span><span class="sxs-lookup"><span data-stu-id="c394a-301">Search</span></span>
      - <span data-ttu-id="c394a-302">フィルター処理と表示の書式設定</span><span class="sxs-lookup"><span data-stu-id="c394a-302">Filtering and view formatting</span></span>
      - <span data-ttu-id="c394a-303">コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="c394a-303">Compliance</span></span>
      - <span data-ttu-id="c394a-304">オートメーション</span><span class="sxs-lookup"><span data-stu-id="c394a-304">Automation</span></span>
2. <span data-ttu-id="c394a-305">識別</span><span class="sxs-lookup"><span data-stu-id="c394a-305">Identify</span></span>
    - <span data-ttu-id="c394a-306">既存の情報アーキテクチャとコンテンツ管理機能の使用について理解する。</span><span class="sxs-lookup"><span data-stu-id="c394a-306">Understand existing information architecture and content management feature use.</span></span>
    - <span data-ttu-id="c394a-307">モデルの候補として既存のコンテンツ タイプはありますか?</span><span class="sxs-lookup"><span data-stu-id="c394a-307">Are any existing content types good candidates for models?</span></span>
    - <span data-ttu-id="c394a-308">メタデータによって改善される既存のプロセス</span><span class="sxs-lookup"><span data-stu-id="c394a-308">What existing processes would be improved by metadata?</span></span>
3. <span data-ttu-id="c394a-309">デザイン</span><span class="sxs-lookup"><span data-stu-id="c394a-309">Design</span></span>
    - <span data-ttu-id="c394a-310">情報アーキテクチャ、管理されたメタデータ、コンテンツ タイプに対するアプローチを設計する</span><span class="sxs-lookup"><span data-stu-id="c394a-310">Design your approach to information architecture, managed metadata and content types</span></span>
    - <span data-ttu-id="c394a-311">定義、作成、管理のプロセスを設計します。</span><span class="sxs-lookup"><span data-stu-id="c394a-311">Design the process for definition, creation, management.</span></span>

## <a name="engage-your-organization"></a><span data-ttu-id="c394a-312">組織に参加する</span><span class="sxs-lookup"><span data-stu-id="c394a-312">Engage your organization</span></span>

1. <span data-ttu-id="c394a-313">ステーク所有者を特定し、シナリオを確認し、プロジェクト計画を策定します。</span><span class="sxs-lookup"><span data-stu-id="c394a-313">Identify stake holders, confirm scenarios, and develop project plan.</span></span>
1. <span data-ttu-id="c394a-314">設定を構成し、ライセンスを適用します。</span><span class="sxs-lookup"><span data-stu-id="c394a-314">Configure settings and apply licenses.</span></span>
1. <span data-ttu-id="c394a-315">認識とトレーニングを開始する – リクルート チャンピオン。</span><span class="sxs-lookup"><span data-stu-id="c394a-315">Begin awareness and training – Recruit Champions.</span></span>
1. <span data-ttu-id="c394a-316">ステージでロールアウトします。</span><span class="sxs-lookup"><span data-stu-id="c394a-316">Roll out in stages.</span></span>  
1. <span data-ttu-id="c394a-317">フィードバックを収集し、反復処理します。</span><span class="sxs-lookup"><span data-stu-id="c394a-317">Gather feedback and iterate.</span></span>
1. <span data-ttu-id="c394a-318">利用状況が増えるにつれて、必要に応じて任意の AI ビルダー クレジットの計画が作成されます。</span><span class="sxs-lookup"><span data-stu-id="c394a-318">As usage grows plan for any AI Builder credits as needed.</span></span>
