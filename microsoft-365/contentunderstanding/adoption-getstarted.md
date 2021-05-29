---
title: 'Microsoft SharePoint Syntex 導入: 概要'
description: ビジネス上の問題の解決に役立SharePoint Syntex を組織で使用および実装する方法について学習します。
ms.author: samanro
author: samanro
manager: pamgreen
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: 62e65f9be25e2c482cca78577048d504ee93097a
ms.sourcegitcommit: 4bcac4cb4f9399ebbd7c8cff0abb4d6ecedb731e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2021
ms.locfileid: "52698978"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a><span data-ttu-id="e1f3a-103">Microsoft SharePoint Syntex 導入: 概要</span><span class="sxs-lookup"><span data-stu-id="e1f3a-103">Microsoft SharePoint Syntex adoption: Get started</span></span>

<span data-ttu-id="e1f3a-104">Syntex で利用可能なインテリジェント コンテンツ サービスは、次SharePoint 3 つの部分を持つと考えてください。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-104">Think of the intelligent content services available in SharePoint Syntex as having three parts:</span></span>

- <span data-ttu-id="e1f3a-105">**コンテンツの理解:** コンテンツから情報を分類して抽出するコードなし AI モデルを作成し、ナレッジの検出と再利用のためにメタデータを自動的に適用します。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-105">**Content understanding:** Create no-code AI models to classify and extract information from content to automatically apply metadata for knowledge discovery and reuse.</span></span> <span data-ttu-id="e1f3a-106">詳しくは、コンテンツ [の理解に関するページを参照してください](document-understanding-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-106">Learn more about [content understanding](document-understanding-overview.md).</span></span>
- <span data-ttu-id="e1f3a-107">**コンテンツ処理:** コンテンツのキャプチャ、取り込み、および分類を自動化し、コンテンツ中心のプロセスをPower Automate。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-107">**Content processing:** Automate capture, ingestion, and categorization of content and streamline content-centric processes using Power Automate.</span></span> <span data-ttu-id="e1f3a-108">コンテンツ処理について [詳しくは、次のページを参照してください](form-processing-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-108">Learn more about [content processing](form-processing-overview.md).</span></span>
- <span data-ttu-id="e1f3a-109">**コンテンツのコンプライアンス:** Microsoft Information Protection との統合によるセキュリティとガバナンスを向上させるために、コンテンツを制御および管理します。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-109">**Content compliance:** Control and manage content to improve security and governance with integration to Microsoft Information Protection.</span></span>

<span data-ttu-id="e1f3a-110">新しい AI サービスと機能を使用すると、コンテンツの理解と分類アプリを、Syntex を使用してコンテンツ管理フローに直接SharePointできます。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-110">With new AI services and capabilities, you can build content understanding and classification apps directly into the content management flow using SharePoint Syntex.</span></span> <span data-ttu-id="e1f3a-111">コンテンツを理解するには、2 つの異なる方法があります。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-111">There are two different ways of understanding your content.</span></span> <span data-ttu-id="e1f3a-112">使用するモデルの種類は、ファイル形式と使用例に基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-112">The model type you use is based on file format and use case:</span></span>

| <span data-ttu-id="e1f3a-113">フォーム処理</span><span class="sxs-lookup"><span data-stu-id="e1f3a-113">Form processing</span></span> | <span data-ttu-id="e1f3a-114">ドキュメント理解</span><span class="sxs-lookup"><span data-stu-id="e1f3a-114">Document understanding</span></span> |
|:-------|:-------|
| <span data-ttu-id="e1f3a-115">ドキュメント ライブラリから作成されます。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-115">Created from document library.</span></span> | <span data-ttu-id="e1f3a-116">コンテンツ センター(Syntex の一部SharePointされます。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-116">Created in the content center, part of SharePoint Syntex.</span></span> |
| <span data-ttu-id="e1f3a-117">AI ビルダーで作成されたモデル。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-117">Model created in AI builder.</span></span> | <span data-ttu-id="e1f3a-118">ネイティブ インターフェイスで作成されたモデル。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-118">Model created in native interface.</span></span> |
| <span data-ttu-id="e1f3a-119">半構造化ファイル形式に使用されます。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-119">Used for semi-structured file formats.</span></span> | <span data-ttu-id="e1f3a-120">非構造化ファイル形式に使用されます。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-120">Used for unstructured file formats.</span></span> |
| <span data-ttu-id="e1f3a-121">Settable 分類子。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-121">Settable classifier.</span></span> | <span data-ttu-id="e1f3a-122">オプションの抽出機能を備えるトレーニング可能な分類子。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-122">Trainable classifier with optional extractors.</span></span> |
| <span data-ttu-id="e1f3a-123">1 つのライブラリに制限されています。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-123">Restricted to a single library.</span></span> | <span data-ttu-id="e1f3a-124">複数のライブラリに適用できます。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-124">Can be applied to multiple libraries.</span></span> |
| <span data-ttu-id="e1f3a-125">PDF、JPG、PNG 形式、合計 50 MB/500 pp でトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-125">Train on PDF, JPG, PNG format, total 50 MB/500 pp.</span></span> | <span data-ttu-id="e1f3a-126">否定的な例を含め、5 - 10 個の PDF、Office、またはメール ファイルでトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-126">Train on 5-10 PDF, Office, or email files, including negative examples.</span></span> |

<span data-ttu-id="e1f3a-127">機能の詳細な比較については、「ドキュメントの理解モデルとフォーム処理モデルの違 [い」を参照してください](difference-between-document-understanding-and-form-processing-model.md)。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-127">For a more complete comparison of the capabilities, see [Difference between document understanding and form processing models](difference-between-document-understanding-and-form-processing-model.md).</span></span>

## <a name="identify-pilot-business-scenarios-to-optimize"></a><span data-ttu-id="e1f3a-128">最適化するパイロット ビジネス シナリオを特定する</span><span class="sxs-lookup"><span data-stu-id="e1f3a-128">Identify pilot business scenarios to optimize</span></span>

<span data-ttu-id="e1f3a-129">組織で Syntex SharePointを使用する準備をするには、最初に役立つシナリオを理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-129">To prepare for using SharePoint Syntex in your organization, you first need to understand the scenarios in which it will be useful.</span></span> <span data-ttu-id="e1f3a-130">"理由" は、必要なモデルを決定し、モデルを適用する場所に基づいて組織を構成する方法を決定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-130">The "why" helps determine what model will be needed, and how to structure your org based on where the model will be applied.</span></span> <span data-ttu-id="e1f3a-131">ドキュメントの理解が組織に役立つシナリオを次に示します。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-131">Here are a few scenarios where document understanding can help your organization:</span></span>

- <span data-ttu-id="e1f3a-132">**コンテンツ処理:** コントラクト、作業明細書、その他のフォームのようなドキュメントを処理します。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-132">**Content processing:** Process contracts, statements of work, and other form-like documents.</span></span> <span data-ttu-id="e1f3a-133">フォームを取り込み、フィールドを理解してマップするためにモデルをトレーニングし、フォームを実行してデータを自動的に収集します。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-133">Intake the forms, train the model to understand and map the fields, and then run your forms through to automatically collect the data.</span></span> <span data-ttu-id="e1f3a-134">詳細については、「フォーム処理の [概要」を参照してください](form-processing-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-134">For more information, see [Form processing overview](form-processing-overview.md).</span></span>
- <span data-ttu-id="e1f3a-135">**請求書分析:** 請求書から関連する詳細を引き出し、ポリシーに準拠している、または適切に処理されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-135">**Invoice analysis:** Pull out the relevant details from your invoices and make sure they're complying with policy or are being processed appropriately.</span></span>

<span data-ttu-id="e1f3a-136">Syntex を使用して組織SharePoint役立つ方法について考えます。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-136">Think about ways that SharePoint Syntex can help your organization:</span></span>

- <span data-ttu-id="e1f3a-137">ビジネス プロセスの自動化</span><span class="sxs-lookup"><span data-stu-id="e1f3a-137">Automate business processes</span></span>
- <span data-ttu-id="e1f3a-138">検索の精度を向上させる</span><span class="sxs-lookup"><span data-stu-id="e1f3a-138">Improve search accuracy</span></span>
- <span data-ttu-id="e1f3a-139">コンプライアンス リスクの管理</span><span class="sxs-lookup"><span data-stu-id="e1f3a-139">Manage compliance risk</span></span>

<span data-ttu-id="e1f3a-140">検討するビジネス シナリオを考える場合は、次の質問をしてください。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-140">When thinking about which business scenarios to consider, ask yourself the following questions:</span></span>

- <span data-ttu-id="e1f3a-141">それは本当の問題を解決しますか?</span><span class="sxs-lookup"><span data-stu-id="e1f3a-141">Does it solve a real problem?</span></span>
- <span data-ttu-id="e1f3a-142">広く使われるか、大きな影響を与えますか?</span><span class="sxs-lookup"><span data-stu-id="e1f3a-142">Will it be widely used or have broad impact?</span></span>
- <span data-ttu-id="e1f3a-143">取得可能ですか?</span><span class="sxs-lookup"><span data-stu-id="e1f3a-143">Is it obtainable?</span></span>
- <span data-ttu-id="e1f3a-144">成功を測定できますか?</span><span class="sxs-lookup"><span data-stu-id="e1f3a-144">Can you measure success?</span></span>

<span data-ttu-id="e1f3a-145">影響と実装の容易さに基づいてシナリオに優先順位を付ける。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-145">Prioritize scenarios based on impact and ease of implementation.</span></span> <span data-ttu-id="e1f3a-146">初期フォーカス領域を簡単に実装できる影響の高いシナリオにします。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-146">Make your initial focus area higher impact scenarios that can also be easily implemented.</span></span> <span data-ttu-id="e1f3a-147">実装が難しい影響の低いシナリオの優先順位を下げる。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-147">De-prioritize lower impact scenarios that are hard to implement.</span></span>

<span data-ttu-id="e1f3a-148">次の[シナリオと使用例を使用](adoption-scenarios.md)して、組織で Syntex を使用する方法についてのSharePointを確認します。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-148">Use the [example scenarios and use cases](adoption-scenarios.md) to prompt ideas about how you can use SharePoint Syntex in your organization.</span></span>

## <a name="identify-roles--responsibilities"></a><span data-ttu-id="e1f3a-149">役割と責任&識別する</span><span class="sxs-lookup"><span data-stu-id="e1f3a-149">Identify roles & responsibilities</span></span>

<span data-ttu-id="e1f3a-150">組織内でモデルを構築および管理するユーザーを決定しますか?</span><span class="sxs-lookup"><span data-stu-id="e1f3a-150">Determine who in your organization will build and manage the models?</span></span> <span data-ttu-id="e1f3a-151">次の役割が関係している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-151">The following roles might be involved:</span></span>

| <span data-ttu-id="e1f3a-152">SharePoint/ナレッジ管理者</span><span class="sxs-lookup"><span data-stu-id="e1f3a-152">SharePoint/Knowledge admin</span></span> | <span data-ttu-id="e1f3a-153">Power Platform 管理者</span><span class="sxs-lookup"><span data-stu-id="e1f3a-153">Power Platform admin</span></span> | <span data-ttu-id="e1f3a-154">知識マネージャー</span><span class="sxs-lookup"><span data-stu-id="e1f3a-154">Knowledge manager</span></span> | <span data-ttu-id="e1f3a-155">モデル所有者</span><span class="sxs-lookup"><span data-stu-id="e1f3a-155">Model owner</span></span> |
|:-------|:-------|:-------|:-------|
| <span data-ttu-id="e1f3a-156">AAD の役割</span><span class="sxs-lookup"><span data-stu-id="e1f3a-156">AAD role</span></span>| <span data-ttu-id="e1f3a-157">AAD の役割</span><span class="sxs-lookup"><span data-stu-id="e1f3a-157">AAD role</span></span> | <span data-ttu-id="e1f3a-158">AAD の役割</span><span class="sxs-lookup"><span data-stu-id="e1f3a-158">AAD role</span></span> | <span data-ttu-id="e1f3a-159">チャンピオン</span><span class="sxs-lookup"><span data-stu-id="e1f3a-159">Champions</span></span> |
| <span data-ttu-id="e1f3a-160">フォームの処理を構成する</span><span class="sxs-lookup"><span data-stu-id="e1f3a-160">Configure form processing</span></span> | <span data-ttu-id="e1f3a-161">フォーム処理用に共通データ サービス環境を構成する</span><span class="sxs-lookup"><span data-stu-id="e1f3a-161">Configure Common data service environment for form processing</span></span> | <span data-ttu-id="e1f3a-162">使用例の収集</span><span class="sxs-lookup"><span data-stu-id="e1f3a-162">Gather use cases</span></span> | <span data-ttu-id="e1f3a-163">ビジネスの使用例を収集する</span><span class="sxs-lookup"><span data-stu-id="e1f3a-163">Gather business use cases</span></span> |
| <span data-ttu-id="e1f3a-164">コンテンツ センターとアクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="e1f3a-164">Manage content centers and permissions</span></span>| <span data-ttu-id="e1f3a-165">AIB クレジットの購入と割り当て</span><span class="sxs-lookup"><span data-stu-id="e1f3a-165">Purchase and allocate AIB credits</span></span> | <span data-ttu-id="e1f3a-166">ベスト プラクティスを確立し、モデル分析を確認する</span><span class="sxs-lookup"><span data-stu-id="e1f3a-166">Establish best practices and review model analytics</span></span> | <span data-ttu-id="e1f3a-167">モデルの作成と適用</span><span class="sxs-lookup"><span data-stu-id="e1f3a-167">Create and apply models</span></span> |

<span data-ttu-id="e1f3a-168">ナレッジ マネージャー、ビジネス プロセス所有者、およびコンテンツ モデル所有者は、組織でサンプル モデルとチャンピオン導入を作成します。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-168">Knowledge manager, Business Process Owner and Content model owner create sample models and champion adoption in the organization.</span></span>
<span data-ttu-id="e1f3a-169">関連する可能性があるその他のユーザー: コンプライアンス管理者、分類管理者。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-169">Others who may be involved: Compliance admin, Taxonomy managers.</span></span>

<span data-ttu-id="e1f3a-170">モデルを構築して適用する場所</span><span class="sxs-lookup"><span data-stu-id="e1f3a-170">Where will they build and apply the models?</span></span> <span data-ttu-id="e1f3a-171">拡張できる既存のプロセスまたはリポジトリはありますか?</span><span class="sxs-lookup"><span data-stu-id="e1f3a-171">Are there existing processes or repositories that could be enhanced?</span></span>

- <span data-ttu-id="e1f3a-172">フォーム処理: フォーム処理アクションを取得するサイトを決定します。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-172">Form processing: Decide which sites will get Form processing action.</span></span>
- <span data-ttu-id="e1f3a-173">ドキュメントの理解: 異なるビジネス領域に対して複数のコンテンツ センターを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-173">Document understanding: You can create multiple content centers for different business areas.</span></span>

## <a name="strategic-positioning"></a><span data-ttu-id="e1f3a-174">戦略的な位置付け</span><span class="sxs-lookup"><span data-stu-id="e1f3a-174">Strategic positioning</span></span>

<span data-ttu-id="e1f3a-175">関係者と協力して、Syntex を使用する戦略に沿SharePointします。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-175">Work with stakeholders to make sure they are aligned on the strategy for using SharePoint Syntex.</span></span> <span data-ttu-id="e1f3a-176">この位置付けを支援するために、次のリソースを調査して提供します。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-176">Research and provide the following resources to help with this positioning:</span></span>

- <span data-ttu-id="e1f3a-177">ビジネスの成果:</span><span class="sxs-lookup"><span data-stu-id="e1f3a-177">Business outcomes:</span></span>
  - <span data-ttu-id="e1f3a-178">潜在的な財政結果</span><span class="sxs-lookup"><span data-stu-id="e1f3a-178">Potential fiscal outcomes</span></span>
  - <span data-ttu-id="e1f3a-179">潜在的な俊敏性の結果</span><span class="sxs-lookup"><span data-stu-id="e1f3a-179">Potential agility outcomes</span></span>
  - <span data-ttu-id="e1f3a-180">ビジネス結果テンプレート</span><span class="sxs-lookup"><span data-stu-id="e1f3a-180">Business outcome template</span></span>
- <span data-ttu-id="e1f3a-181">利害関係者/Exec スポンサーバイイン/アラインメント</span><span class="sxs-lookup"><span data-stu-id="e1f3a-181">Stakeholders/Exec sponsor buy-in/alignment</span></span>
  - <span data-ttu-id="e1f3a-182">ビジネス ケース デッキ</span><span class="sxs-lookup"><span data-stu-id="e1f3a-182">Business case decks</span></span>
  - <span data-ttu-id="e1f3a-183">財務モデル</span><span class="sxs-lookup"><span data-stu-id="e1f3a-183">Financial models</span></span>
  - <span data-ttu-id="e1f3a-184">会社の準備 - カルチャ</span><span class="sxs-lookup"><span data-stu-id="e1f3a-184">Company readiness - culture</span></span>

## <a name="identify-stakeholders"></a><span data-ttu-id="e1f3a-185">関係者の特定</span><span class="sxs-lookup"><span data-stu-id="e1f3a-185">Identify stakeholders</span></span>

<span data-ttu-id="e1f3a-186">プロジェクトの関係者を特定します。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-186">Identify the stakeholders for your project.</span></span>

|<span data-ttu-id="e1f3a-187">ロール</span><span class="sxs-lookup"><span data-stu-id="e1f3a-187">Role</span></span> |<span data-ttu-id="e1f3a-188">責任</span><span class="sxs-lookup"><span data-stu-id="e1f3a-188">Responsibilities</span></span> |<span data-ttu-id="e1f3a-189">部署</span><span class="sxs-lookup"><span data-stu-id="e1f3a-189">Department</span></span> |
|:-------|:-------|:--------|
| <span data-ttu-id="e1f3a-190">エグゼクティブ スポンサー</span><span class="sxs-lookup"><span data-stu-id="e1f3a-190">Executive sponsor(s)</span></span>   | <span data-ttu-id="e1f3a-191">ハイレベルなビジョンと価値を会社に伝える</span><span class="sxs-lookup"><span data-stu-id="e1f3a-191">Communicate high-level vision and values to the company</span></span>   |  <span data-ttu-id="e1f3a-192">経営幹部のリーダー</span><span class="sxs-lookup"><span data-stu-id="e1f3a-192">Executive leadership</span></span>   |
| <span data-ttu-id="e1f3a-193">Projectリード</span><span class="sxs-lookup"><span data-stu-id="e1f3a-193">Project lead(s)</span></span> | <span data-ttu-id="e1f3a-194">起動の実行と展開プロセス全体を監視する</span><span class="sxs-lookup"><span data-stu-id="e1f3a-194">Oversee the entire launch execution and rollout process</span></span> | <span data-ttu-id="e1f3a-195">プロジェクト管理</span><span class="sxs-lookup"><span data-stu-id="e1f3a-195">Project management</span></span> |
| <span data-ttu-id="e1f3a-196">ナレッジ管理者</span><span class="sxs-lookup"><span data-stu-id="e1f3a-196">Knowledge administrators</span></span>| <span data-ttu-id="e1f3a-197">コンテンツ センターの作成と管理</span><span class="sxs-lookup"><span data-stu-id="e1f3a-197">Create and manage the content centers</span></span> | <span data-ttu-id="e1f3a-198">IT 部門または他の部署</span><span class="sxs-lookup"><span data-stu-id="e1f3a-198">IT or other department</span></span>|
| <span data-ttu-id="e1f3a-199">コンテンツ 管理者とモデル所有者</span><span class="sxs-lookup"><span data-stu-id="e1f3a-199">Content managers and model owners</span></span>| <span data-ttu-id="e1f3a-200">使用例を収集し、モデルを作成して適用する</span><span class="sxs-lookup"><span data-stu-id="e1f3a-200">Gather use cases and create and apply models</span></span> | <span data-ttu-id="e1f3a-201">任意の部署</span><span class="sxs-lookup"><span data-stu-id="e1f3a-201">Any department</span></span>|
| <span data-ttu-id="e1f3a-202">チャンピオン</span><span class="sxs-lookup"><span data-stu-id="e1f3a-202">Champions</span></span> | <span data-ttu-id="e1f3a-203">宣伝とクレーム処理の管理を支援する</span><span class="sxs-lookup"><span data-stu-id="e1f3a-203">Help evangelize and manage objection handling</span></span> | <span data-ttu-id="e1f3a-204">任意の部署 (スタッフ)</span><span class="sxs-lookup"><span data-stu-id="e1f3a-204">Any department (staff)</span></span> |
| <span data-ttu-id="e1f3a-205">テナント管理者</span><span class="sxs-lookup"><span data-stu-id="e1f3a-205">Tenant administrator</span></span> | <span data-ttu-id="e1f3a-206">テナント レベルの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="e1f3a-206">Configure tenant-level settings</span></span> | <span data-ttu-id="e1f3a-207">IT 部門</span><span class="sxs-lookup"><span data-stu-id="e1f3a-207">IT department</span></span>|
| <span data-ttu-id="e1f3a-208">Power プラットフォーム管理者</span><span class="sxs-lookup"><span data-stu-id="e1f3a-208">Power Platform administrator</span></span>| <span data-ttu-id="e1f3a-209">共通データ サービス環境を構成する</span><span class="sxs-lookup"><span data-stu-id="e1f3a-209">Configure common data services environment</span></span> | <span data-ttu-id="e1f3a-210">IT 部門</span><span class="sxs-lookup"><span data-stu-id="e1f3a-210">IT department</span></span>|

> [!Note]
> <span data-ttu-id="e1f3a-211">ロールアウトを通じてこれらの各役割を満たすことをお勧めしますが、特定のソリューションの開始に必要な役割は必要ない場合があります。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-211">Though we recommend having each of these roles fulfilled throughout your rollout, you may find that you don't require them all to get started with your identified solution.</span></span>

## <a name="readiness-checklist"></a><span data-ttu-id="e1f3a-212">準備チェックリスト</span><span class="sxs-lookup"><span data-stu-id="e1f3a-212">Readiness checklist</span></span>

<span data-ttu-id="e1f3a-213">Syntex を実装する準備をSharePointするには、次の必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-213">To get ready for implementing SharePoint Syntex, you need to:</span></span>

![コンテンツ理解の準備](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. <span data-ttu-id="e1f3a-215">終了状態を計画する</span><span class="sxs-lookup"><span data-stu-id="e1f3a-215">Plan the end state</span></span>
    - <span data-ttu-id="e1f3a-216">ドキュメント理解モデルは、最後ではなく手段です。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-216">Document understanding models are the means, not the end.</span></span>
    - <span data-ttu-id="e1f3a-217">抽出されたメタデータの値を次の値で活用する計画を立て、</span><span class="sxs-lookup"><span data-stu-id="e1f3a-217">Plan for harnessing the value of extracted metadata with:</span></span>
      - <span data-ttu-id="e1f3a-218">検索</span><span class="sxs-lookup"><span data-stu-id="e1f3a-218">Search</span></span>
      - <span data-ttu-id="e1f3a-219">フィルター処理と表示の書式設定</span><span class="sxs-lookup"><span data-stu-id="e1f3a-219">Filtering and view formatting</span></span>
      - <span data-ttu-id="e1f3a-220">コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="e1f3a-220">Compliance</span></span>
      - <span data-ttu-id="e1f3a-221">オートメーション</span><span class="sxs-lookup"><span data-stu-id="e1f3a-221">Automation</span></span>
2. <span data-ttu-id="e1f3a-222">識別</span><span class="sxs-lookup"><span data-stu-id="e1f3a-222">Identify</span></span>
    - <span data-ttu-id="e1f3a-223">既存の情報アーキテクチャとコンテンツ管理機能の使用について理解する。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-223">Understand existing information architecture and content management feature use.</span></span>
    - <span data-ttu-id="e1f3a-224">モデルの候補として既存のコンテンツ タイプはありますか?</span><span class="sxs-lookup"><span data-stu-id="e1f3a-224">Are any existing content types good candidates for models?</span></span>
    - <span data-ttu-id="e1f3a-225">メタデータによって改善される既存のプロセス</span><span class="sxs-lookup"><span data-stu-id="e1f3a-225">What existing processes would be improved by metadata?</span></span>
3. <span data-ttu-id="e1f3a-226">デザイン</span><span class="sxs-lookup"><span data-stu-id="e1f3a-226">Design</span></span>
    - <span data-ttu-id="e1f3a-227">情報アーキテクチャ、管理されたメタデータ、コンテンツ タイプに対するアプローチを設計する</span><span class="sxs-lookup"><span data-stu-id="e1f3a-227">Design your approach to information architecture, managed metadata and content types</span></span>
    - <span data-ttu-id="e1f3a-228">定義、作成、管理のプロセスを設計します。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-228">Design the process for definition, creation, management.</span></span>

## <a name="engage-your-organization"></a><span data-ttu-id="e1f3a-229">組織に参加する</span><span class="sxs-lookup"><span data-stu-id="e1f3a-229">Engage your organization</span></span>

1. <span data-ttu-id="e1f3a-230">ステーク所有者を特定し、シナリオを確認し、プロジェクト計画を策定します。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-230">Identify stake holders, confirm scenarios, and develop project plan.</span></span>
1. <span data-ttu-id="e1f3a-231">設定を構成し、ライセンスを適用します。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-231">Configure settings and apply licenses.</span></span>
1. <span data-ttu-id="e1f3a-232">認識とトレーニングを開始する – リクルート チャンピオン。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-232">Begin awareness and training – Recruit Champions.</span></span>
1. <span data-ttu-id="e1f3a-233">ステージでロールアウトします。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-233">Roll out in stages.</span></span>  
1. <span data-ttu-id="e1f3a-234">フィードバックを収集し、反復処理します。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-234">Gather feedback and iterate.</span></span>
1. <span data-ttu-id="e1f3a-235">利用状況が増えるにつれて、必要に応じて任意の AI ビルダー クレジットの計画が作成されます。</span><span class="sxs-lookup"><span data-stu-id="e1f3a-235">As usage grows plan for any AI Builder credits as needed.</span></span>

## <a name="see-also"></a><span data-ttu-id="e1f3a-236">関連項目</span><span class="sxs-lookup"><span data-stu-id="e1f3a-236">See also</span></span>

[<span data-ttu-id="e1f3a-237">Syntex のシナリオと使用例SharePoint例</span><span class="sxs-lookup"><span data-stu-id="e1f3a-237">Scenarios and use cases for SharePoint Syntex</span></span>](adoption-scenarios.md)