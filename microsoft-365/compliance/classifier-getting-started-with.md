---
title: トレーニング可能な分類子の使用を開始する (プレビュー)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 トレーニング可能な分類子は、陽性と陰性のサンプルを提供することによって、さまざまなタイプのコンテンツを認識するトレーニング ツールです。 分類子がトレーニングされると、その結果が正しいことを確認します。 次に、それを使用して組織のコンテンツを検索し、分類して保持または秘密度ラベルを適用するか、データ損失防止 (DLP) または保持ポリシーに含めます。
ms.openlocfilehash: 10475420c729efc6a1ff59b6620fed08a1bdefca
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126336"
---
# <a name="getting-started-with-trainable-classifiers-preview"></a><span data-ttu-id="0faaa-105">トレーニング可能な分類子の使用を開始する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="0faaa-105">Getting started with trainable classifiers (preview)</span></span>

<span data-ttu-id="0faaa-106">コンテンツを適切に保護および処理できるようにコンテンツを分類およびラベル付けすることは、情報保護に対するトレーニングの出発点です。</span><span class="sxs-lookup"><span data-stu-id="0faaa-106">Classifying and labeling content so it can be protected and handled properly is the starting place for the information protection discipline.</span></span> <span data-ttu-id="0faaa-107">Microsoft 365 には、コンテンツを分類する 3 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="0faaa-107">Microsoft 365 has three ways to classify content.</span></span>

## <a name="manually"></a><span data-ttu-id="0faaa-108">手動</span><span class="sxs-lookup"><span data-stu-id="0faaa-108">Manually</span></span>

<span data-ttu-id="0faaa-109">この方法では、人間の判断と行動が必要です。</span><span class="sxs-lookup"><span data-stu-id="0faaa-109">This method requires human judgment and action.</span></span> <span data-ttu-id="0faaa-110">管理者は、既存のラベルと機密情報の種類を使用するか、独自のラベルを作成して公開することができます。</span><span class="sxs-lookup"><span data-stu-id="0faaa-110">An admin may either use the pre-existing labels and sensitive information types or create their own and then publish them.</span></span> <span data-ttu-id="0faaa-111">ユーザーと管理者は、遭遇したコンテンツをそれらに適用します。</span><span class="sxs-lookup"><span data-stu-id="0faaa-111">Users and admins apply them to content as they encounter it.</span></span> <span data-ttu-id="0faaa-112">その後、コンテンツを保護し、その処分を管理できます。</span><span class="sxs-lookup"><span data-stu-id="0faaa-112">You can then protect the content and manage its disposition.</span></span>

## <a name="automated-pattern-matching"></a><span data-ttu-id="0faaa-113">自動パターン マッチング</span><span class="sxs-lookup"><span data-stu-id="0faaa-113">Automated pattern matching</span></span>

<span data-ttu-id="0faaa-114">この分類メカニズムのカテゴリには、次によるコンテンツの検索が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0faaa-114">This category of classification mechanisms includes finding content by:</span></span>

- <span data-ttu-id="0faaa-115">キーワードまたはメタデータ値 (キーワードクエリ言語)。</span><span class="sxs-lookup"><span data-stu-id="0faaa-115">Keywords or metadata values (keyword query language).</span></span>
- <span data-ttu-id="0faaa-116">ソーシャルセキュリティ、クレジットカード、または銀行口座番号[(機密情報の種類のエンティティ定義)](sensitive-information-type-entity-definitions.md)など、以前に識別された機密情報のパターンを使用します。</span><span class="sxs-lookup"><span data-stu-id="0faaa-116">Using previously identified patterns of sensitive information like social security, credit card or bank account numbers [(Sensitive information type entity definitions)](sensitive-information-type-entity-definitions.md).</span></span>
- <span data-ttu-id="0faaa-117">テンプレートのバリエーションであるためにアイテムを認識する[(ドキュメントのフィンガープリント)](document-fingerprinting.md)。</span><span class="sxs-lookup"><span data-stu-id="0faaa-117">Recognizing an item because it's a variation on a template [(document finger printing)](document-fingerprinting.md).</span></span>
- <span data-ttu-id="0faaa-118">正確な文字列の存在[(正確なデータ一致)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="0faaa-118">Using the presence of exact strings [(exact data match)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

<span data-ttu-id="0faaa-119">機密情報と保持ラベルを自動的に適用して、[データ損失防止 (DLP)](data-loss-prevention-policies.md)および[保持ラベルの自動適用ポリシー](apply-retention-labels-automatically.md)で使用できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="0faaa-119">Sensitivity and retention labels can then be automatically applied to make the content available for use in [data loss prevention (DLP)](data-loss-prevention-policies.md) and [auto-apply polices for retention labels](apply-retention-labels-automatically.md).</span></span>

## <a name="trainable-classifiers"></a><span data-ttu-id="0faaa-120">トレーニング可能な分類子</span><span class="sxs-lookup"><span data-stu-id="0faaa-120">Trainable classifiers</span></span>

<span data-ttu-id="0faaa-121">この分類方法は、手動または自動のパターン マッチング方法では簡単に識別できないコンテンツに特に適しています。</span><span class="sxs-lookup"><span data-stu-id="0faaa-121">This classification method is particularly well suited to content that isn't easily identified by either the manual or automated pattern matching methods.</span></span> <span data-ttu-id="0faaa-122">この分類方法は、アイテムに含まれる要素ではなく、アイテムが何であるかに基づいてアイテムを識別するように分類子をトレーニングすることです (パターン マッチング)。</span><span class="sxs-lookup"><span data-stu-id="0faaa-122">This method of classification is more about training a classifier to identify an item based on what the item is, not by elements that are in the item (pattern matching).</span></span> <span data-ttu-id="0faaa-123">分類子は、分類したいコンテンツの数百の例を見て、コンテンツのタイプを識別する方法を学びます。</span><span class="sxs-lookup"><span data-stu-id="0faaa-123">A classifier learns how to identify a type of content by looking at hundreds of examples of the content you're interested in classifying.</span></span> <span data-ttu-id="0faaa-124">それを間違いなくカテゴリーにある例に与えることから始めます。</span><span class="sxs-lookup"><span data-stu-id="0faaa-124">You start by feeding it examples that are definitely in the category.</span></span> <span data-ttu-id="0faaa-125">それらを処理したら、一致する例と一致しない例の両方を組み合わせてテストします。</span><span class="sxs-lookup"><span data-stu-id="0faaa-125">Once it processes those, you test it by giving it a mix of both matching and non-matching examples.</span></span> <span data-ttu-id="0faaa-126">次に、分類子は、特定のアイテムが作成中のカテゴリに該当するかどうかを予測します。</span><span class="sxs-lookup"><span data-stu-id="0faaa-126">The classifier then makes predictions as to whether any given item falls into the category you're building.</span></span> <span data-ttu-id="0faaa-127">その後、その結果を確認し、陽性、陰性、偽陽性、偽陰性に仕分けし、その予測の正確性を高めます。</span><span class="sxs-lookup"><span data-stu-id="0faaa-127">You then confirm its results, sorting out the positives, negatives, false positives, and false negatives to help increase the accuracy of its predictions.</span></span> <span data-ttu-id="0faaa-128">トレーニング済みの分類子を公開すると、SharePoint Online、Exchange、OneDrive などの場所にあるアイテムが並べ替えられ、コンテンツが分類されます。</span><span class="sxs-lookup"><span data-stu-id="0faaa-128">When you publish the trained classifier, it sorts through items in locations like SharePoint Online, Exchange, and OneDrive, and classifies the content.</span></span>

### <a name="where-you-can-use-trainable-classifiers"></a><span data-ttu-id="0faaa-129">Trainable 分類子を使用できる場所</span><span class="sxs-lookup"><span data-stu-id="0faaa-129">Where you can use trainable classifiers</span></span>
<span data-ttu-id="0faaa-130">組み込みの分類子とトレーニング可能な分類子の両方が、[条件に基づく保持ラベル ポリシーの自動適用](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels)と[通信コンプライアンス](communication-compliance-configure.md)の条件として使用できます。</span><span class="sxs-lookup"><span data-stu-id="0faaa-130">Both built-in classifiers and trainable classifiers are available as a condition for [auto-apply retention label policy based on a condition](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) and [communication compliance](communication-compliance-configure.md).</span></span> 

<span data-ttu-id="0faaa-131">機密ラベルを使用して、組み込みの分類子を条件として使用できます。「[機密ラベルをコンテンツに自動的に適用](apply-sensitivity-label-automatically.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0faaa-131">Sensitivity labels can use built-in and build-your-own classifiers as conditions, see [Apply a sensitivity label to content automatically](apply-sensitivity-label-automatically.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0faaa-132">トレーニング可能な分類子は、暗号化されていない英語のアイテムでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="0faaa-132">Trainable classifiers only work with items that are not encrypted and are in English.</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="0faaa-133">ライセンスの要件</span><span class="sxs-lookup"><span data-stu-id="0faaa-133">Licensing requirements</span></span>

<span data-ttu-id="0faaa-134">トレーニング可能な分類子は、Microsoft 365 E5 または E5 コンプライアンス機能です。</span><span class="sxs-lookup"><span data-stu-id="0faaa-134">Trainable classifiers are a Microsoft 365 E5, or E5 Compliance feature.</span></span> <span data-ttu-id="0faaa-135">それらを使用するには、これらのサブスクリプションのいずれかが必要です。</span><span class="sxs-lookup"><span data-stu-id="0faaa-135">You must have one of these subscriptions to make use of them.</span></span>

### <a name="pre-requisites"></a><span data-ttu-id="0faaa-136">前提条件</span><span class="sxs-lookup"><span data-stu-id="0faaa-136">Pre-requisites</span></span>

<span data-ttu-id="0faaa-137">UI の trainable 分類子にアクセスするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="0faaa-137">To access trainable classifiers in the UI:</span></span> 
- <span data-ttu-id="0faaa-138">グローバル管理者がテナントに対してオプトインを選択する必要がある</span><span class="sxs-lookup"><span data-stu-id="0faaa-138">the Global admin needs to opt in for the tenant</span></span>
- <span data-ttu-id="0faaa-139">分類子を教育するには、コンプライアンス管理者ロールまたはコンプライアンスデータ管理者が必要</span><span class="sxs-lookup"><span data-stu-id="0faaa-139">Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="0faaa-140">次のシナリオでは、trainable 分類子を使用するために、これらのアクセス許可を持つアカウントが必要になります。</span><span class="sxs-lookup"><span data-stu-id="0faaa-140">You'll need accounts with these permissions to use trainable classifiers in these scenarios:</span></span>

- <span data-ttu-id="0faaa-141">保持ラベルポリシーシナリオ: RecordManagement および Retention Management の役割</span><span class="sxs-lookup"><span data-stu-id="0faaa-141">Retention label policy scenario: RecordManagement and Retention Management roles</span></span> 
- <span data-ttu-id="0faaa-142">機密ラベルポリシーのシナリオ: セキュリティ管理者、コンプライアンス管理者、コンプライアンスデータ管理者</span><span class="sxs-lookup"><span data-stu-id="0faaa-142">Sensitivity label policy scenario: Security Administrator, Compliance Administrator, Compliance Data Administrator</span></span>
- <span data-ttu-id="0faaa-143">コミュニケーションコンプライアンスポリシーのシナリオ: Insider リスク管理管理者、監督レビュー管理者</span><span class="sxs-lookup"><span data-stu-id="0faaa-143">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

## <a name="types-of-classifiers"></a><span data-ttu-id="0faaa-144">分類子のタイプ</span><span class="sxs-lookup"><span data-stu-id="0faaa-144">Types of classifiers</span></span>

<span data-ttu-id="0faaa-145">組み込みの分類子とトレーニング可能な分類子があります。</span><span class="sxs-lookup"><span data-stu-id="0faaa-145">There are built-in classifiers and trainable classifiers.</span></span> <span data-ttu-id="0faaa-146">トレーニング可能な分類子を公開可能な状態にするには、それをトレーニングするために時間を投資する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0faaa-146">Getting a trainable classifier to a publishable state requires a time investment to train it.</span></span> <span data-ttu-id="0faaa-147">分類子の使用を開始するために、Microsoft 365 にはいくつかの組み込みの分類子が付属しています。</span><span class="sxs-lookup"><span data-stu-id="0faaa-147">To help you get started using classifiers, Microsoft 365 comes with a few built-in classifiers.</span></span>

> [!NOTE]
> <span data-ttu-id="0faaa-148">分類とラベル付けのワークフローで組み込みの分類子を使用する前に、カテゴリに適合すると思われる組織コンテンツのサンプルに対してテストし、分類予測が期待を満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0faaa-148">Before using any built-in classifier in your classification and labeling workflow, you should test it against a sample of your organizations content that you feel fits the category to verify that its classification predictions meet your expectations.</span></span>

### <a name="understanding-built-in-classifiers"></a><span data-ttu-id="0faaa-149">組み込み分類子について</span><span class="sxs-lookup"><span data-stu-id="0faaa-149">Understanding built-in classifiers</span></span>

<span data-ttu-id="0faaa-150">Microsoft 365 には、推奨される 5 つの組み込み分類子が付属しています。</span><span class="sxs-lookup"><span data-stu-id="0faaa-150">Microsoft 365 comes with five recommended built-in classifiers:</span></span>

> [!CAUTION]
> <span data-ttu-id="0faaa-151">組み込みの [**不快な言葉**] は、誤検知の数が多いため、廃止予定です。</span><span class="sxs-lookup"><span data-stu-id="0faaa-151">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="0faaa-152">使用しないでください。現在使用している場合は、ビジネス プロセスを移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0faaa-152">Don't use it and if you are currently using it, you should move your business processes off of it.</span></span> <span data-ttu-id="0faaa-153">代わりに、[**脅威**]、[**冒涜的表現**]、および [**ハラスメント**] の組み込み分類子を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0faaa-153">We recommend using the **Threat**, **Profanity**, and **Harassment** built-in classifiers instead.</span></span>

- <span data-ttu-id="0faaa-154">**履歴書**: 申請者の個人、教育、専門資格、作業経験、その他個人を識別する情報のテキストアカウントであるアイテムを検出します。</span><span class="sxs-lookup"><span data-stu-id="0faaa-154">**Resumes**: detects items that are textual accounts of an applicant's personal, educational, professional qualifications, work experience, and other personally identifying information</span></span>
- <span data-ttu-id="0faaa-155">**ソースコード**: GitHub で使用されている上位25台のコンピュータプログラミング言語で記述された命令およびステートメントのセットを含むアイテムを検出します。</span><span class="sxs-lookup"><span data-stu-id="0faaa-155">**Source Code**: detects items that contain a set of instructions and statements written in the top 25 used computer programming languages on GitHub</span></span>

  |<span data-ttu-id="0faaa-156">言語名</span><span class="sxs-lookup"><span data-stu-id="0faaa-156">language name</span></span>|||||
  |---------|---------|---------|---------|---------|
  |<span data-ttu-id="0faaa-157">ActionScript</span><span class="sxs-lookup"><span data-stu-id="0faaa-157">ActionScript</span></span>|<span data-ttu-id="0faaa-158">C</span><span class="sxs-lookup"><span data-stu-id="0faaa-158">C</span></span>        |<span data-ttu-id="0faaa-159">C#</span><span class="sxs-lookup"><span data-stu-id="0faaa-159">C#</span></span>       |<span data-ttu-id="0faaa-160">C++</span><span class="sxs-lookup"><span data-stu-id="0faaa-160">C++</span></span>     |<span data-ttu-id="0faaa-161">Clojure</span><span class="sxs-lookup"><span data-stu-id="0faaa-161">Clojure</span></span>  |
  |<span data-ttu-id="0faaa-162">CoffeeScript</span><span class="sxs-lookup"><span data-stu-id="0faaa-162">CoffeeScript</span></span>|<span data-ttu-id="0faaa-163">CSS</span><span class="sxs-lookup"><span data-stu-id="0faaa-163">CSS</span></span>     |<span data-ttu-id="0faaa-164">Go</span><span class="sxs-lookup"><span data-stu-id="0faaa-164">Go</span></span>       |<span data-ttu-id="0faaa-165">Haskell</span><span class="sxs-lookup"><span data-stu-id="0faaa-165">Haskell</span></span> |<span data-ttu-id="0faaa-166">HTML</span><span class="sxs-lookup"><span data-stu-id="0faaa-166">HTML</span></span>     |
  |<span data-ttu-id="0faaa-167">Java</span><span class="sxs-lookup"><span data-stu-id="0faaa-167">Java</span></span>     |<span data-ttu-id="0faaa-168">JavaScript</span><span class="sxs-lookup"><span data-stu-id="0faaa-168">JavaScript</span></span>|<span data-ttu-id="0faaa-169">Lua</span><span class="sxs-lookup"><span data-stu-id="0faaa-169">Lua</span></span>      |<span data-ttu-id="0faaa-170">MATLAB</span><span class="sxs-lookup"><span data-stu-id="0faaa-170">MATLAB</span></span>   |<span data-ttu-id="0faaa-171">Objective-C</span><span class="sxs-lookup"><span data-stu-id="0faaa-171">Objective-C</span></span>|
  |<span data-ttu-id="0faaa-172">Perl</span><span class="sxs-lookup"><span data-stu-id="0faaa-172">Perl</span></span>     |<span data-ttu-id="0faaa-173">PHP</span><span class="sxs-lookup"><span data-stu-id="0faaa-173">PHP</span></span>      |<span data-ttu-id="0faaa-174">Python</span><span class="sxs-lookup"><span data-stu-id="0faaa-174">Python</span></span>   |<span data-ttu-id="0faaa-175">R</span><span class="sxs-lookup"><span data-stu-id="0faaa-175">R</span></span>        |<span data-ttu-id="0faaa-176">Ruby</span><span class="sxs-lookup"><span data-stu-id="0faaa-176">Ruby</span></span>     |
  |<span data-ttu-id="0faaa-177">Scala</span><span class="sxs-lookup"><span data-stu-id="0faaa-177">Scala</span></span>    |<span data-ttu-id="0faaa-178">Shell</span><span class="sxs-lookup"><span data-stu-id="0faaa-178">Shell</span></span>    |<span data-ttu-id="0faaa-179">Swift</span><span class="sxs-lookup"><span data-stu-id="0faaa-179">Swift</span></span>    |<span data-ttu-id="0faaa-180">Tex</span><span class="sxs-lookup"><span data-stu-id="0faaa-180">Tex</span></span>      |<span data-ttu-id="0faaa-181">Vim Script</span><span class="sxs-lookup"><span data-stu-id="0faaa-181">Vim Script</span></span>|

> [!NOTE]
> <span data-ttu-id="0faaa-182">ソースコードは、テキストの大部分がソースコードであるときに検出するためにトレーニングされています。</span><span class="sxs-lookup"><span data-stu-id="0faaa-182">Source Code is trained to detect when the bulk of the text is source code.</span></span> <span data-ttu-id="0faaa-183">プレーンテキストが混在しているソースコードテキストは検出されません。</span><span class="sxs-lookup"><span data-stu-id="0faaa-183">It does not detect source code text that is interspersed with plain text.</span></span>

- <span data-ttu-id="0faaa-184">**嫌がらせ**: 次の特徴に基づいて、1人または複数の個人を対象とした不快感を持つ、不快感を持つテキストアイテムの特定のカテゴリを検出します。競合、ethnicity、宗教、国内原産者、性別、性的なオリエンテーション、年齢、障碍</span><span class="sxs-lookup"><span data-stu-id="0faaa-184">**Harassment**: detects a specific category of offensive language text items related to offensive conduct targeting one or multiple individuals based on the following traits: race, ethnicity, religion, national origin, gender, sexual orientation, age, disability</span></span>
- <span data-ttu-id="0faaa-185">**不適切な用語**: 多くのユーザーを embarrass する式を含む、不快感を与える言語のテキストアイテムの特定のカテゴリを検出します。</span><span class="sxs-lookup"><span data-stu-id="0faaa-185">**Profanity**: detects a specific category of offensive language text items that contain expressions that embarrass most people</span></span>
- <span data-ttu-id="0faaa-186">**脅威**: 暴力を確定する脅威、または人またはプロパティに物理的な悪影響や損害を与えることに関連する脅威に関連する、不快な言語のテキストアイテムの特定のカテゴリを検出します。</span><span class="sxs-lookup"><span data-stu-id="0faaa-186">**Threat**: detects a specific category of offensive language text items related to threats to commit violence or do physical harm or damage to a person or property</span></span>

<span data-ttu-id="0faaa-187">これらは、[**Microsoft 365 コンプライアンス センター**]  >  [**データ分類 (プレビュー)**]  >  [**トレーニング可能な分類子**] ビューに表示され、ステータスは `Ready to use` です。</span><span class="sxs-lookup"><span data-stu-id="0faaa-187">These appear in the **Microsoft 365 compliance center** > **Data classification (preview)** > **Trainable classifiers** view with the status of `Ready to use`.</span></span>

![分類子はすぐに使用できる分類子](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> <span data-ttu-id="0faaa-189">不快な言葉、ハラスメント、冒涜的表現、および脅威の分類は、検索可能なテキストでのみ機能し、網羅的または完全ではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0faaa-189">Please note that the offensive language, harassment, profanity, and threat classifiers only work with searchable text are not exhaustive or complete.</span></span>  <span data-ttu-id="0faaa-190">さらに、言語と文化の基準は絶えず変化し、これらの現実に照らして、Microsoft は独自の裁量でこれらの分類子を更新する権利を留保します。</span><span class="sxs-lookup"><span data-stu-id="0faaa-190">Further, language and cultural standards continually change, and in light of these realities, Microsoft reserves the right to update these classifiers in its discretion.</span></span> <span data-ttu-id="0faaa-191">分類子は、不快な言語やその他の使用言語を監視するのに役立ちますが、分類子は、そのような言語の結果に対処するものではなく、そのような言語の使用を監視または応答する唯一の手段を組織に提供するものではありません。</span><span class="sxs-lookup"><span data-stu-id="0faaa-191">While the classifiers may assist your organization in monitoring offensive and other language used, the classifiers do not address consequences of such language and are not intended to provide your organization's sole means of monitoring or responding to the use of such language.</span></span> <span data-ttu-id="0faaa-192">事前にトレーニングされた分類子によって識別されたコンテンツの監視、施行、ブロック、削除、および保持に関するすべての決定は、Microsoft またはその子会社ではなく、お客様の組織の責任となります。</span><span class="sxs-lookup"><span data-stu-id="0faaa-192">Your organization, and not Microsoft or its subsidiaries, remains responsible for all decisions related to monitoring, enforcement, blocking, removal and retention of any content identified by a pre-trained classifier.</span></span>

#### <a name="process-flow-for-using-built-in-classifiers"></a><span data-ttu-id="0faaa-193">組み込み分類子を使用するためのプロセス フロー</span><span class="sxs-lookup"><span data-stu-id="0faaa-193">Process flow for using built-in classifiers</span></span>

<span data-ttu-id="0faaa-194">組み込み分類子をトレーニングする必要はありませんが、コンプライアンス ソリューションで使用する前に、それらが必要とするコンテンツのタイプを識別できることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0faaa-194">Built-in classifiers don't need to be trained, but you do need to confirm that they will identify the types of content that you need them to before you use them in compliance solutions.</span></span> <span data-ttu-id="0faaa-195">このフローに従って、事前トレーニング済みの分類子のテストを行います。</span><span class="sxs-lookup"><span data-stu-id="0faaa-195">Testing a pre-trained classifier follows this flow.</span></span>

![事前トレーニング済みの分類子をテストするプロセス フロー](../media/classifier-pre-trained-classifier-flow.png)

### <a name="understanding-trainable-classifiers"></a><span data-ttu-id="0faaa-197">トレーニング可能な分類子について</span><span class="sxs-lookup"><span data-stu-id="0faaa-197">Understanding trainable classifiers</span></span>

<span data-ttu-id="0faaa-198">組み込み分類子がニーズを満たさない場合は、独自の分類子を作成してトレーニングできます。</span><span class="sxs-lookup"><span data-stu-id="0faaa-198">When the built-in classifiers don't meet your needs, you can create and train your own classifiers.</span></span> <span data-ttu-id="0faaa-199">独自に作成するには、はるかに多くの作業が必要になりますが、組織のニーズに合わせてカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="0faaa-199">There's significantly more work involved with creating your own, but they'll be much better tailored to your organizations needs.</span></span> <span data-ttu-id="0faaa-200">事前トレーニング済みの分類子の使用方法の詳細については、「[組み込み分類子の使用](classifier-using-a-ready-to-use-classifier.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0faaa-200">For more detail on how to use a pre-trained classifier, see [Using a built-in classifier](classifier-using-a-ready-to-use-classifier.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0faaa-201">トレーニング可能な分類子を作成するユーザーのみが、その分類子によって行われた予測をトレーニングおよび確認できます。</span><span class="sxs-lookup"><span data-stu-id="0faaa-201">Only the user who creates a trainable classifier can train and review predictions made by that classifier.</span></span>

#### <a name="process-flow-for-creating-trainable-classifiers"></a><span data-ttu-id="0faaa-202">トレーニング可能な分類子を作成するためのプロセス フロー</span><span class="sxs-lookup"><span data-stu-id="0faaa-202">Process flow for creating trainable classifiers</span></span>

<span data-ttu-id="0faaa-203">保持ポリシーや通信監督など、コンプライアンス ソリューションで使用するトレーニング可能な分類子の作成と公開はこのフローに従います。</span><span class="sxs-lookup"><span data-stu-id="0faaa-203">Creating and publishing a trainable classifier for use in compliance solutions, such as retention policies and communication supervision, follows this flow.</span></span> <span data-ttu-id="0faaa-204">トレーニング可能な分類子の作成の詳細については、「[トレーニング可能な分類子の作成](classifier-creating-a-trainable-classifier.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0faaa-204">For more detail on creating a trainable classifier see, [Creating a trainable classifier](classifier-creating-a-trainable-classifier.md).</span></span>

![プロセス フローのトレーニング可能な分類子](../media/classifier-trainable-classifier-flow.png)

## <a name="see-also"></a><span data-ttu-id="0faaa-206">関連項目</span><span class="sxs-lookup"><span data-stu-id="0faaa-206">See also</span></span>


- [<span data-ttu-id="0faaa-207">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="0faaa-207">Retention labels</span></span>](retention.md)
- [<span data-ttu-id="0faaa-208">データ損失防止 (DLP)</span><span class="sxs-lookup"><span data-stu-id="0faaa-208">Data loss prevention (DLP)</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="0faaa-209">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="0faaa-209">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="0faaa-210">機密情報の種類のエンティティ定義</span><span class="sxs-lookup"><span data-stu-id="0faaa-210">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="0faaa-211">ドキュメントのフィンガープリント</span><span class="sxs-lookup"><span data-stu-id="0faaa-211">Document finger printing</span></span>](document-fingerprinting.md)
- [<span data-ttu-id="0faaa-212">正確なデータ一致</span><span class="sxs-lookup"><span data-stu-id="0faaa-212">Exact data match</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
