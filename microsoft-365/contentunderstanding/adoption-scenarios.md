---
title: Microsoft SharePoint Syntex のシナリオと使用例
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: laurieellis
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
description: 組織で Syntex を使用するSharePointシナリオを確認します。
ms.openlocfilehash: b28239a304c8fab209436c12e6cdbffe160b7981
ms.sourcegitcommit: a3359982fea01339c7377e3ee89f223788cee0bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2021
ms.locfileid: "52697067"
---
# <a name="scenarios-and-use-cases-for-microsoft-sharepoint-syntex"></a><span data-ttu-id="85518-103">Microsoft SharePoint Syntex のシナリオと使用例</span><span class="sxs-lookup"><span data-stu-id="85518-103">Scenarios and use cases for Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="85518-104">次のシナリオ例を使用して、組織で Syntex を使用する方法SharePointを確認します。</span><span class="sxs-lookup"><span data-stu-id="85518-104">Use the following example scenarios to prompt ideas about how you can use SharePoint Syntex in your organization.</span></span>

- [<span data-ttu-id="85518-105">シナリオ: フォーム処理を使用して請求書からデータを追跡する</span><span class="sxs-lookup"><span data-stu-id="85518-105">Scenario: Track data from invoices with form processing</span></span>](adoption-scenarios.md#scenario-track-data-from-invoices-with-form-processing)
- [<span data-ttu-id="85518-106">シナリオ: ドキュメントを理解して契約からの情報を追跡する</span><span class="sxs-lookup"><span data-stu-id="85518-106">Scenario: Track information from contracts with document understanding</span></span>](adoption-scenarios.md#scenario-track-information-from-contracts-with-document-understanding)
- [<span data-ttu-id="85518-107">シナリオ: Syntex に基づくレコード管理、ドキュメント ガバナンス、コンプライアンス プロセスでリスクSharePointする</span><span class="sxs-lookup"><span data-stu-id="85518-107">Scenario: Avoid risk with records management, document governance, and compliance processes based on SharePoint Syntex</span></span>](adoption-scenarios.md#scenario-avoid-risk-with-records-management-document-governance-and-compliance-processes-based-on-sharepoint-syntex)
- [<span data-ttu-id="85518-108">シナリオ: 以前にアクセスできないドキュメントから情報をキャプチャする</span><span class="sxs-lookup"><span data-stu-id="85518-108">Scenario: Capture information from previously inaccessible documents</span></span>](adoption-scenarios.md#scenario-capture-information-from-previously-inaccessible-documents)
- [<span data-ttu-id="85518-109">シナリオ: データ処理を改善して分析と分析を提供する</span><span class="sxs-lookup"><span data-stu-id="85518-109">Scenario: Improve data processing to provide insights and analytics</span></span>](adoption-scenarios.md#scenario-improve-data-processing-to-provide-insights-and-analytics)
- [<span data-ttu-id="85518-110">シナリオ: 注文処理の自動化</span><span class="sxs-lookup"><span data-stu-id="85518-110">Scenario: Automate order processing</span></span>](adoption-scenarios.md#scenario-automate-order-processing)
- [<span data-ttu-id="85518-111">シナリオ: ビザの更新プロセスを簡素化する</span><span class="sxs-lookup"><span data-stu-id="85518-111">Scenario: Simplify visa renewal process</span></span>](adoption-scenarios.md#scenario-simplify-visa-renewal-process)

## <a name="scenario-track-data-from-invoices-with-form-processing"></a><span data-ttu-id="85518-112">シナリオ: フォーム処理を使用して請求書からデータを追跡する</span><span class="sxs-lookup"><span data-stu-id="85518-112">Scenario: Track data from invoices with form processing</span></span>

<span data-ttu-id="85518-113">たとえば、Syntex および他の機能を使用SharePoint、Power Automateを設定して請求書を追跡および監視できます。</span><span class="sxs-lookup"><span data-stu-id="85518-113">For example, you can set up a process using SharePoint Syntex and Power Automate features to track and monitor invoices.</span></span>

1. <span data-ttu-id="85518-114">請求書ドキュメントを格納するライブラリを設定します。</span><span class="sxs-lookup"><span data-stu-id="85518-114">Set up a library to store the invoice documents.</span></span>
1. <span data-ttu-id="85518-115">ドキュメント内のフィールドを認識するようにモデルをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="85518-115">Train the model to recognize fields in the documents.</span></span>
1. <span data-ttu-id="85518-116">追跡するフィールドをリストに抽出します。</span><span class="sxs-lookup"><span data-stu-id="85518-116">Extract the fields you want to track into a list.</span></span>
1. <span data-ttu-id="85518-117">次のような特定のイベントについて通知するフローを設定します。</span><span class="sxs-lookup"><span data-stu-id="85518-117">Set up a flow to notify you for specific events, such as:</span></span>
    - <span data-ttu-id="85518-118">新しい請求書が追加されます。</span><span class="sxs-lookup"><span data-stu-id="85518-118">A new invoice is added.</span></span>
    - <span data-ttu-id="85518-119">請求書が期日を過ぎた。</span><span class="sxs-lookup"><span data-stu-id="85518-119">An invoice is past its due date.</span></span>
    - <span data-ttu-id="85518-120">請求書は、自動承認金額よりも大きい金額です。</span><span class="sxs-lookup"><span data-stu-id="85518-120">An invoice is for an amount that's larger than your automatic approval amount.</span></span>

![Syntex とデータを使用して請求書SharePoint追跡Power Automate](../media/content-understanding/process-invoices-flow.png)

<span data-ttu-id="85518-122">このシナリオを自動化すると、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="85518-122">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="85518-123">手動で行う代わりに、請求書からデータを自動的に抽出することで、時間と資金を節約できます。</span><span class="sxs-lookup"><span data-stu-id="85518-123">Save time and money by automatically extracting data from the invoices instead of doing it manually.</span></span>
- <span data-ttu-id="85518-124">ワークフローを使用して請求書をチェックし、問題を通知することで、潜在的なエラーを減らし、コンプライアンスを強化します。</span><span class="sxs-lookup"><span data-stu-id="85518-124">Reduce potential errors and ensure better compliance by using workflows to check invoices and notify you of any issues.</span></span>

## <a name="scenario-track-information-from-contracts-with-document-understanding"></a><span data-ttu-id="85518-125">シナリオ: ドキュメントを理解して契約からの情報を追跡する</span><span class="sxs-lookup"><span data-stu-id="85518-125">Scenario: Track information from contracts with document understanding</span></span>

<span data-ttu-id="85518-126">別の例として、会社が他の会社や個人との契約を特定するプロセスを設定できます。</span><span class="sxs-lookup"><span data-stu-id="85518-126">As another example, you can set up a process to identify contracts your company has with other companies or individuals.</span></span> <span data-ttu-id="85518-127">クライアント名、手数料、日付、その他の重要な情報など、それらの契約から重要な情報を抽出し、すぐに表示できるフィールドとしてライブラリに情報を追加するモデルを設定します。</span><span class="sxs-lookup"><span data-stu-id="85518-127">Set up a model to extract key information from those contracts, such as the client name, fees, dates, or other important information, and add the information to the library as fields you can quickly view.</span></span> <span data-ttu-id="85518-128">ドキュメント ライブラリに保持ラベルを適用して、ビジネス規制に適切に準拠するために、特定の期間前に契約を削除できません。</span><span class="sxs-lookup"><span data-stu-id="85518-128">Apply a retention label on the document library to ensure that contracts can't be deleted before a specific length of time for appropriate compliance with your business regulations.</span></span>

1. <span data-ttu-id="85518-129">コンテンツ センターから開始し、契約の新しいドキュメント理解モデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="85518-129">Start at the content center and create a new document understanding model for contracts.</span></span>
1. <span data-ttu-id="85518-130">アップロード例のサンプル ドキュメントを作成し、トレーニングを実行して契約ドキュメントを特定し、結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="85518-130">Upload sample documents for positive and negative examples, then run the training to identify contract documents and review the results.</span></span>
1. <span data-ttu-id="85518-131">抽出プログラムをトレーニングして、クライアント名、手数料、日付などのコントラクト内のフィールドを識別し、抽出プログラムをテストします。</span><span class="sxs-lookup"><span data-stu-id="85518-131">Train the extractor to identify fields in the contracts, such as the client name, fee, and date, and then test the extractor.</span></span>
1. <span data-ttu-id="85518-132">モデルが完了したら、契約書をアップロードできるライブラリにモデルを適用します。</span><span class="sxs-lookup"><span data-stu-id="85518-132">When the model is complete, apply the model to a library where you can upload contracts.</span></span>
1. <span data-ttu-id="85518-133">保持ラベルを日付フィールドに適用して、必要な期間、契約がライブラリに保持されます。</span><span class="sxs-lookup"><span data-stu-id="85518-133">Apply a retention label to the date field, so that contracts are retained in the library for the required length of time.</span></span>

![Syntex および保持ラベルを使用して契約SharePoint追跡および監視する](../media/content-understanding/process-contracts-flow.png)

<span data-ttu-id="85518-135">このシナリオを自動化すると、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="85518-135">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="85518-136">手動で行う代わりに、契約からデータを自動的に抽出することで、時間と資金を節約できます。</span><span class="sxs-lookup"><span data-stu-id="85518-136">Save time and money by automatically extracting data from the contracts instead of doing it manually.</span></span>
- <span data-ttu-id="85518-137">保持ラベルを使用して、契約が適切に保持されるのを確認して、コンプライアンスを強化します。</span><span class="sxs-lookup"><span data-stu-id="85518-137">Ensure better compliance by using retention labels to ensure that the contracts are retained appropriately.</span></span>

## <a name="scenario-avoid-risk-with-records-management-document-governance-and-compliance-processes-based-on-sharepoint-syntex"></a><span data-ttu-id="85518-138">シナリオ: Syntex に基づくレコード管理、ドキュメント ガバナンス、コンプライアンス プロセスでリスクSharePointする</span><span class="sxs-lookup"><span data-stu-id="85518-138">Scenario: Avoid risk with records management, document governance, and compliance processes based on SharePoint Syntex</span></span>

<span data-ttu-id="85518-139">リスクを減らすことは、ほとんどの企業にとって一般的な目標です。</span><span class="sxs-lookup"><span data-stu-id="85518-139">Reducing risks is a common goal for most companies.</span></span> <span data-ttu-id="85518-140">以下が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="85518-140">You might need:</span></span>

- <span data-ttu-id="85518-141">テナント全体に情報ガバナンスを提供/適用する優れた方法。</span><span class="sxs-lookup"><span data-stu-id="85518-141">A better way to provide/enforce information governance across your tenant.</span></span>
- <span data-ttu-id="85518-142">プロジェクトの「レコード」と見なされるドキュメント、電子メール、その他のコミュニケーションの分類システムを改善する。</span><span class="sxs-lookup"><span data-stu-id="85518-142">To improve the system for classification of documents, emails and other forms of communication considered ‘records’ for projects.</span></span>
- <span data-ttu-id="85518-143">会社のポリシーに準拠するために、領収書、契約などについて監査する。</span><span class="sxs-lookup"><span data-stu-id="85518-143">To audit receipts, contracts, and so on, to ensure compliance with company policies.</span></span>
- <span data-ttu-id="85518-144">コンプライアンスに必要なすべてのドキュメントがプロジェクトに含まれています。</span><span class="sxs-lookup"><span data-stu-id="85518-144">To ensure that projects have all the documentation required for compliance.</span></span>

<span data-ttu-id="85518-145">より良いガバナンスを必要とするドキュメントとフォームをキャプチャし、適切に分類、監査、フラグを設定するために、SharePoint Syntex に準拠するためのいくつかのプロセスを設定します。</span><span class="sxs-lookup"><span data-stu-id="85518-145">Set up some processes for compliance with SharePoint Syntex to capture and appropriately classify, audit, and flag documents and forms that need better governance.</span></span> <span data-ttu-id="85518-146">エンド ユーザーが手動でタグSharePoint、コンプライアンス チームがガバナンス ルールとアーカイブを手動で適用するのではなく、コンテンツを自動分類するには、Syntex を使用して自動的に分類できます。</span><span class="sxs-lookup"><span data-stu-id="85518-146">You can rely on SharePoint Syntex to auto classify content rather than relying on end users to manually tag, or the compliance team to manually apply governance rules and archiving.</span></span> <span data-ttu-id="85518-147">また、簡単な検索エクスペリエンスを有効にし、データボリュームを管理し、レコード管理と保持ポリシーを適用し、コンプライアンスを確保し、ベスト プラクティスのアーカイブと削除を行います。</span><span class="sxs-lookup"><span data-stu-id="85518-147">And you can enable a simplified search experience, manage data volumes, apply records management and retention policies, ensure compliance, and best practice archiving and purging practices.</span></span>

<span data-ttu-id="85518-148">このシナリオを自動化すると、次のセキュリティを確保できます。</span><span class="sxs-lookup"><span data-stu-id="85518-148">When you automate this scenario, you can feel secure that:</span></span>

- <span data-ttu-id="85518-149">コンプライアンスが支持され、リスクが軽減されます。</span><span class="sxs-lookup"><span data-stu-id="85518-149">Compliance is upheld and risk is reduced.</span></span>
- <span data-ttu-id="85518-150">分類とレコード管理は、一貫して正確に適用されます。</span><span class="sxs-lookup"><span data-stu-id="85518-150">Taxonomy and records management is consistently and accurately applied.</span></span>
- <span data-ttu-id="85518-151">コンテンツ ボリュームが制御されます。</span><span class="sxs-lookup"><span data-stu-id="85518-151">Content volumes are controlled.</span></span>
- <span data-ttu-id="85518-152">従業員は、適切なコンテキストで適切な情報を簡単に検出できます。</span><span class="sxs-lookup"><span data-stu-id="85518-152">Employees can easily discover the right information in the right context.</span></span>

## <a name="scenario-capture-information-from-previously-inaccessible-documents"></a><span data-ttu-id="85518-153">シナリオ: 以前にアクセスできないドキュメントから情報をキャプチャする</span><span class="sxs-lookup"><span data-stu-id="85518-153">Scenario: Capture information from previously inaccessible documents</span></span>

<span data-ttu-id="85518-154">ほとんどの組織には、法的ドキュメント、ポリシー、契約、人事ドキュメント、ガバナンス ガイドラインの大規模なリポジトリがあります。</span><span class="sxs-lookup"><span data-stu-id="85518-154">Most organizations have large repositories of legal documents, policies, contracts, HR documents, and governance guidelines.</span></span> <span data-ttu-id="85518-155">これらのデータ ストアを採掘して、プロジェクト、セクター、テーマ、人、地理的領域などの貴重な情報を抽出します。</span><span class="sxs-lookup"><span data-stu-id="85518-155">Mine these data stores to extract valuable information such as: projects, sectors, themes, people, geographical areas, and so on.</span></span>

<span data-ttu-id="85518-156">たとえば、人事担当ディレクターは、履歴書、人事ポリシー、その他のフォームを含むすべての人事ドキュメントにすばやくアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="85518-156">For example, an HR director needs to quickly access all HR documents – including resumes, HR policies, and other forms.</span></span> <span data-ttu-id="85518-157">また、ドキュメントを手動でふるいにかけることなく、履歴書や他の人事関連のドキュメントから必要な情報をすばやく特定したいと考える必要があります。</span><span class="sxs-lookup"><span data-stu-id="85518-157">And they want to quickly identify necessary information from resumes and other HR-related documents without manually sifting through the documents.</span></span> <span data-ttu-id="85518-158">何千もの履歴書、人事ポリシー、および複数のサイトに広がる可能性があるその他のドキュメントを手動で確認することなく、必要な情報をすばやく見つけ出すソリューションを探しています。</span><span class="sxs-lookup"><span data-stu-id="85518-158">They’re looking for a solution that allows them to quickly find the information they need without having to manually look through thousands of resumes, HR policies, and other documentation that may be spread across several sites.</span></span>

<span data-ttu-id="85518-159">このシナリオを自動化すると、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="85518-159">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="85518-160">デジタル コンテンツから知識のロックを解除します。</span><span class="sxs-lookup"><span data-stu-id="85518-160">Unlock knowledge from digital content.</span></span>
- <span data-ttu-id="85518-161">人事ポリシー、履歴書、販売ドキュメント、技術設計図、アカウントプランを分類し、情報を抽出します。</span><span class="sxs-lookup"><span data-stu-id="85518-161">Classify HR policies, resumes, sales documents, technical blueprints, account plans and extract information.</span></span>
- <span data-ttu-id="85518-162">探している正しい情報やドキュメントをすばやく見つける。</span><span class="sxs-lookup"><span data-stu-id="85518-162">Quickly find the correct information or document that you’re looking for.</span></span>
- <span data-ttu-id="85518-163">最新情報に即座にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="85518-163">Get instant access to the latest information.</span></span>
- <span data-ttu-id="85518-164">検索時間を短縮します。</span><span class="sxs-lookup"><span data-stu-id="85518-164">Reduce search times.</span></span>

## <a name="scenario-improve-data-processing-to-provide-insights-and-analytics"></a><span data-ttu-id="85518-165">シナリオ: データ処理を改善して分析と分析を提供する</span><span class="sxs-lookup"><span data-stu-id="85518-165">Scenario: Improve data processing to provide insights and analytics</span></span>

<span data-ttu-id="85518-166">たとえば、製薬会社は、SharePointシンテックスを使用して、FDA ドキュメントから情報を抽出して、リーダーが持っている質問に答えます。</span><span class="sxs-lookup"><span data-stu-id="85518-166">For example, a pharmaceutical company could use SharePoint Syntex to extract information from FDA documents to answer questions that their leaders have.</span></span> <span data-ttu-id="85518-167">回答に簡単にアクセスできると、これらの回答を生成するために必要な時間が短縮され、データの可用性が向上して、リーダーシップに関する質問に対するより正確な回答が生成されます。</span><span class="sxs-lookup"><span data-stu-id="85518-167">Having the answers more easily accessible can reduce the time needed to produce these answers and increase the availability of data to generate more accurate answers to leadership questions.</span></span>

<span data-ttu-id="85518-168">たとえば、プロジェクト マネージャーは、リーダーシップ チームからの製品関連の質問に対する回答をすばやく提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85518-168">For example, a project manager needs to quickly provide answers to product-related questions from my leadership team.</span></span> <span data-ttu-id="85518-169">1 つの統合ダッシュボードでクエリに関連する情報と指標を見つける必要があります。</span><span class="sxs-lookup"><span data-stu-id="85518-169">They need to find information and metrics related to queries in one consolidated dashboard.</span></span> <span data-ttu-id="85518-170">製品ラベル、製品パンフレット、その他の資料から必要な情報を抽出し、リーダーシップ チームに報告する際に使用できる統合レポートを生成するソリューションを探しています。</span><span class="sxs-lookup"><span data-stu-id="85518-170">They’re looking for a solution that extracts the information they need from product labels, product pamphlets, and other materials and generates a consolidated report that they can use when reporting back to their leadership team.</span></span>

<span data-ttu-id="85518-171">このシナリオを自動化すると、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="85518-171">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="85518-172">回答を生成する時間を短縮します。</span><span class="sxs-lookup"><span data-stu-id="85518-172">Reduce time to produce answers.</span></span>
- <span data-ttu-id="85518-173">データの可用性を高める。</span><span class="sxs-lookup"><span data-stu-id="85518-173">Increase availability of data.</span></span>
- <span data-ttu-id="85518-174">より正確な回答を提供します。</span><span class="sxs-lookup"><span data-stu-id="85518-174">Provide more accurate answers.</span></span>

## <a name="scenario-automate-order-processing"></a><span data-ttu-id="85518-175">シナリオ: 注文処理の自動化</span><span class="sxs-lookup"><span data-stu-id="85518-175">Scenario: Automate order processing</span></span>

<span data-ttu-id="85518-176">Syntex SharePointを使用すると、顧客注文の手動処理の時間を短縮できます。</span><span class="sxs-lookup"><span data-stu-id="85518-176">With SharePoint Syntex, you can reduce the time of manual processing of customer orders.</span></span> <span data-ttu-id="85518-177">たとえば、OCR 処理を使用して FAX、電子メール、または紙から SharePoint に注文をアップロードし、それらの注文からメタデータを抽出して、自動化されたプロセスを使用して注文を満たします。</span><span class="sxs-lookup"><span data-stu-id="85518-177">For example, you can upload orders from fax, email, or paper into SharePoint by using OCR processing and then extract the metadata from those orders so you can fulfill them by using automated processes.</span></span>

<span data-ttu-id="85518-178">たとえば、サプライ チェーン マネージャーは、手動データ入力によるエラーを減らしたいと考しています。</span><span class="sxs-lookup"><span data-stu-id="85518-178">For example, a supply chain manager wants to reduce errors caused by manual data entry.</span></span> <span data-ttu-id="85518-179">ビジネス システムに入るエラーを減らすために、受信顧客注文 (紙、FAX、または電子メール) の手動レビューとデータ入力を回避したいと考えています。</span><span class="sxs-lookup"><span data-stu-id="85518-179">They want to avoid manual review and data entry of inbound customer orders (paper, fax, or e-mail) to reduce errors going into their business systems.</span></span> <span data-ttu-id="85518-180">AI と機械学習の手法を適用して、受信注文情報を検証し、コア データを抽出し、注文のフルフィルメントと調整のために ERP システムに自動的にプッシュするソリューションが必要です。</span><span class="sxs-lookup"><span data-stu-id="85518-180">They want a solution that applies AI and machine learning techniques to validate incoming order information, extract core data and automatically push it into their ERP system, for order fulfillment and reconciliation.</span></span>

<span data-ttu-id="85518-181">このシナリオを自動化する場合は、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="85518-181">When you automate this scenario, you can ensure that:</span></span>

- <span data-ttu-id="85518-182">注文と出荷の精度が向上します。</span><span class="sxs-lookup"><span data-stu-id="85518-182">Order and shipment accuracy increases.</span></span>
- <span data-ttu-id="85518-183">注文または出荷エラーに関連する手数料またはペナルティが軽減されます。</span><span class="sxs-lookup"><span data-stu-id="85518-183">Fees or penalties associated to order or shipment errors are reduced.</span></span>
- <span data-ttu-id="85518-184">請求や支払いの遅延が減少します。</span><span class="sxs-lookup"><span data-stu-id="85518-184">Delays in invoicing or payments decrease.</span></span>
- <span data-ttu-id="85518-185">人件費が削減されます。</span><span class="sxs-lookup"><span data-stu-id="85518-185">Personnel costs are reduced.</span></span>

## <a name="scenario-simplify-visa-renewal-process"></a><span data-ttu-id="85518-186">シナリオ: ビザの更新プロセスを簡素化する</span><span class="sxs-lookup"><span data-stu-id="85518-186">Scenario: Simplify visa renewal process</span></span>

<span data-ttu-id="85518-187">SharePointSyntex は、重要な契約情報のリマインダーと更新を自動化するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="85518-187">SharePoint Syntex can help you automate reminders and renewals for key contract information.</span></span> <span data-ttu-id="85518-188">たとえば、人事担当ディレクターは、従業員のビザが最新の日付または期限内に更新される必要があります。</span><span class="sxs-lookup"><span data-stu-id="85518-188">For example, an HR director needs to ensure that employees’ visas are up to date and/or renewed on time.</span></span> <span data-ttu-id="85518-189">彼らは、人々に自分のビザを更新するための簡単で直感的なプロセスを提供したいと考っています。</span><span class="sxs-lookup"><span data-stu-id="85518-189">They want to give people a simple and intuitive process for updating their Visas.</span></span> <span data-ttu-id="85518-190">契約から更新日を抽出し、更新日が近づいているときに従業員に自動的に通知を送信するソリューションが必要です。</span><span class="sxs-lookup"><span data-stu-id="85518-190">They need a solution that extracts renewal dates from contracts and automatically sends employees reminders when their renewal dates are approaching.</span></span>

<span data-ttu-id="85518-191">このシナリオを自動化する場合は、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="85518-191">When you automate this scenario, you can ensure that:</span></span>

- <span data-ttu-id="85518-192">コンプライアンス以外のレベルが低下します。</span><span class="sxs-lookup"><span data-stu-id="85518-192">The levels of non-compliance are reduced.</span></span>
- <span data-ttu-id="85518-193">手動アラームの数が減ります。</span><span class="sxs-lookup"><span data-stu-id="85518-193">The number of manual reminders is reduced.</span></span>
- <span data-ttu-id="85518-194">コンプライアンスに準拠しない場合の罰金の数を減らします。</span><span class="sxs-lookup"><span data-stu-id="85518-194">The number of fines for non-compliance is reduced.</span></span>

## <a name="see-also"></a><span data-ttu-id="85518-195">関連項目</span><span class="sxs-lookup"><span data-stu-id="85518-195">See also</span></span>

[<span data-ttu-id="85518-196">Microsoft SharePoint Syntex 導入: 概要</span><span class="sxs-lookup"><span data-stu-id="85518-196">Microsoft SharePoint Syntex adoption: Get started</span></span>](adoption-getstarted.md)