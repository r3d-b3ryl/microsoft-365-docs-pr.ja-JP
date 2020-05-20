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
ms.openlocfilehash: edfa708077e273d9c644801f5461c880d87261b5
ms.sourcegitcommit: 261d51b90a9ad53a6a42348c414b1b1e1230c37f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "44292433"
---
# <a name="getting-started-with-trainable-classifiers-preview"></a><span data-ttu-id="2998f-105">トレーニング可能な分類子の使用を開始する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="2998f-105">Getting started with trainable classifiers (preview)</span></span>

<span data-ttu-id="2998f-106">コンテンツを適切に保護および処理できるようにコンテンツを分類およびラベル付けすることは、情報保護に対するトレーニングの出発点です。</span><span class="sxs-lookup"><span data-stu-id="2998f-106">Classifying and labeling content so it can be protected and handled properly is the starting place for the information protection discipline.</span></span> <span data-ttu-id="2998f-107">Microsoft 365 には、コンテンツを分類する 3 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="2998f-107">Microsoft 365 has three ways to classify content.</span></span>

## <a name="manually"></a><span data-ttu-id="2998f-108">手動</span><span class="sxs-lookup"><span data-stu-id="2998f-108">Manually</span></span>

<span data-ttu-id="2998f-109">この方法では、人間の判断と行動が必要です。</span><span class="sxs-lookup"><span data-stu-id="2998f-109">This method requires human judgment and action.</span></span> <span data-ttu-id="2998f-110">管理者は、既存のラベルと機密情報の種類を使用するか、独自のラベルを作成して公開することができます。</span><span class="sxs-lookup"><span data-stu-id="2998f-110">An admin may either use the pre-existing labels and sensitive information types or create their own and then publish them.</span></span> <span data-ttu-id="2998f-111">ユーザーと管理者は、遭遇したコンテンツをそれらに適用します。</span><span class="sxs-lookup"><span data-stu-id="2998f-111">Users and admins apply them to content as they encounter it.</span></span> <span data-ttu-id="2998f-112">その後、コンテンツを保護し、その処分を管理できます。</span><span class="sxs-lookup"><span data-stu-id="2998f-112">You can then protect the content and manage its disposition.</span></span>

## <a name="automated-pattern-matching"></a><span data-ttu-id="2998f-113">自動パターン マッチング</span><span class="sxs-lookup"><span data-stu-id="2998f-113">Automated pattern matching</span></span>

<span data-ttu-id="2998f-114">この分類メカニズムのカテゴリには、次によるコンテンツの検索が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2998f-114">This category of classification mechanisms includes finding content by:</span></span>

- <span data-ttu-id="2998f-115">キーワードまたはメタデータ値 (キーワード クエリ言語)</span><span class="sxs-lookup"><span data-stu-id="2998f-115">keywords or metadata values (keyword query language)</span></span>
- <span data-ttu-id="2998f-116">社会保障、クレジット カード、銀行口座番号などの以前に特定された機密情報のパターンを使用する [(機密情報の種類)](what-the-sensitive-information-types-look-for.md)</span><span class="sxs-lookup"><span data-stu-id="2998f-116">using previously identified patterns of sensitive information like social security, credit card or bank account numbers [(sensitive information types)](what-the-sensitive-information-types-look-for.md)</span></span>
- <span data-ttu-id="2998f-117">テンプレートのバリエーションであるため、アイテムを認識する [(ドキュメント フィンガー プリント)](document-fingerprinting.md)</span><span class="sxs-lookup"><span data-stu-id="2998f-117">Recognizing an item because it's a variation on a template [(document finger printing)](document-fingerprinting.md)</span></span>
- <span data-ttu-id="2998f-118">正確な文字列の存在を使用する [(完全なデータ一致)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)。</span><span class="sxs-lookup"><span data-stu-id="2998f-118">using the presence of exact strings [(exact data match)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).'</span></span>

<span data-ttu-id="2998f-119">次に、秘密度ラベルと保持ラベルを自動的に適用して、コンテンツを[データ損失防止 (DLP)](data-loss-prevention-policies.md) および[保持ポリシー](retention-policies.md)で使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2998f-119">Sensitivity and retention labels can then be automatically applied to make the content available for use in [data loss prevention (DLP)](data-loss-prevention-policies.md) and [retention policies](retention-policies.md).</span></span>

## <a name="trainable-classifiers"></a><span data-ttu-id="2998f-120">トレーニング可能な分類子</span><span class="sxs-lookup"><span data-stu-id="2998f-120">Trainable classifiers</span></span>

<span data-ttu-id="2998f-121">この分類方法は、手動または自動のパターン マッチング方法では簡単に識別できないコンテンツに特に適しています。</span><span class="sxs-lookup"><span data-stu-id="2998f-121">This classification method is particularly well suited to content that isn't easily identified by either the manual or automated pattern matching methods.</span></span> <span data-ttu-id="2998f-122">この分類方法は、アイテムに含まれる要素ではなく、アイテムが何であるかに基づいてアイテムを識別するように分類子をトレーニングすることです (パターン マッチング)。</span><span class="sxs-lookup"><span data-stu-id="2998f-122">This method of classification is more about training a classifier to identify an item based on what the item is, not by elements that are in the item (pattern matching).</span></span> <span data-ttu-id="2998f-123">分類子は、分類したいコンテンツの数百の例を見て、コンテンツのタイプを識別する方法を学びます。</span><span class="sxs-lookup"><span data-stu-id="2998f-123">A classifier learns how to identify a type of content by looking at hundreds of examples of the content you're interested in classifying.</span></span> <span data-ttu-id="2998f-124">それを間違いなくカテゴリーにある例に与えることから始めます。</span><span class="sxs-lookup"><span data-stu-id="2998f-124">You start by feeding it examples that are definitely in the category.</span></span> <span data-ttu-id="2998f-125">それらを処理したら、一致する例と一致しない例の両方を組み合わせてテストします。</span><span class="sxs-lookup"><span data-stu-id="2998f-125">Once it processes those, you test it by giving it a mix of both matching and non-matching examples.</span></span> <span data-ttu-id="2998f-126">次に、分類子は、特定のアイテムが作成中のカテゴリに該当するかどうかを予測します。</span><span class="sxs-lookup"><span data-stu-id="2998f-126">The classifier then makes predictions as to whether any given item falls into the category you're building.</span></span> <span data-ttu-id="2998f-127">その後、その結果を確認し、陽性、陰性、偽陽性、偽陰性に仕分けし、その予測の正確性を高めます。</span><span class="sxs-lookup"><span data-stu-id="2998f-127">You then confirm its results, sorting out the positives, negatives, false positives, and false negatives to help increase the accuracy of its predictions.</span></span> <span data-ttu-id="2998f-128">トレーニング済みの分類子を公開すると、SharePoint Online、Exchange、OneDrive などの場所にあるアイテムが並べ替えられ、コンテンツが分類されます。</span><span class="sxs-lookup"><span data-stu-id="2998f-128">When you publish the trained classifier, it sorts through items in locations like SharePoint Online, Exchange, and OneDrive, and classifies the content.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2998f-129">組み込みの分類子とトレーニング可能な分類子の両方が、[条件に基づく保持ラベル ポリシーの自動適用](labels.md#applying-a-retention-label-automatically-based-on-conditions)と[通信コンプライアンス](communication-compliance.md)の条件として使用できます。</span><span class="sxs-lookup"><span data-stu-id="2998f-129">Both built-in classifiers and trainable classifiers are available as a condition for [auto-apply retention label policy based on a condition](labels.md#applying-a-retention-label-automatically-based-on-conditions) and [communication compliance](communication-compliance.md).</span></span> <span data-ttu-id="2998f-130">秘密度ラベルは、組み込みの分類子を条件としてのみ使用できます。「[秘密度ラベルをコンテンツに自動的に適用する](apply-sensitivity-label-automatically.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2998f-130">Sensitivity labels can only use built-in classifiers as a condition, see [Apply a sensitivity label to content automatically](apply-sensitivity-label-automatically.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2998f-131">トレーニング可能な分類子は、暗号化されていない英語のアイテムでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="2998f-131">Trainable classifiers only work with items that are not encrypted and are in English.</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="2998f-132">ライセンスの要件</span><span class="sxs-lookup"><span data-stu-id="2998f-132">Licensing requirements</span></span>

<span data-ttu-id="2998f-133">トレーニング可能な分類子は、Microsoft 365 E5 または E5 コンプライアンス機能です。</span><span class="sxs-lookup"><span data-stu-id="2998f-133">Trainable classifiers are a Microsoft 365 E5, or E5 Compliance feature.</span></span> <span data-ttu-id="2998f-134">それらを使用するには、これらのサブスクリプションのいずれかが必要です。</span><span class="sxs-lookup"><span data-stu-id="2998f-134">You must have one of these subscriptions to make use of them.</span></span>

## <a name="types-of-classifiers"></a><span data-ttu-id="2998f-135">分類子のタイプ</span><span class="sxs-lookup"><span data-stu-id="2998f-135">Types of classifiers</span></span>

<span data-ttu-id="2998f-136">組み込みの分類子とトレーニング可能な分類子があります。</span><span class="sxs-lookup"><span data-stu-id="2998f-136">There are built-in classifiers and trainable classifiers.</span></span> <span data-ttu-id="2998f-137">トレーニング可能な分類子を公開可能な状態にするには、それをトレーニングするために時間を投資する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2998f-137">Getting a trainable classifier to a publishable state requires a time investment to train it.</span></span> <span data-ttu-id="2998f-138">分類子の使用を開始するために、Microsoft 365 にはいくつかの組み込みの分類子が付属しています。</span><span class="sxs-lookup"><span data-stu-id="2998f-138">To help you get started using classifiers, Microsoft 365 comes with a few built-in classifiers.</span></span>

> [!NOTE]
> <span data-ttu-id="2998f-139">分類とラベル付けのワークフローで組み込みの分類子を使用する前に、カテゴリに適合すると思われる組織コンテンツのサンプルに対してテストし、分類予測が期待を満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2998f-139">Before using any built-in classifier in your classification and labeling workflow, you should test it against a sample of your organizations content that you feel fits the category to verify that its classification predictions meet your expectations.</span></span>

### <a name="understanding-built-in-classifiers"></a><span data-ttu-id="2998f-140">組み込み分類子について</span><span class="sxs-lookup"><span data-stu-id="2998f-140">Understanding built-in classifiers</span></span>

<span data-ttu-id="2998f-141">Microsoft 365 には、推奨される 5 つの組み込み分類子が付属しています。</span><span class="sxs-lookup"><span data-stu-id="2998f-141">Microsoft 365 comes with five recommended built-in classifiers:</span></span>

> [!CAUTION]
> <span data-ttu-id="2998f-142">組み込みの [**不快な言葉**] は、誤検知の数が多いため、廃止予定です。</span><span class="sxs-lookup"><span data-stu-id="2998f-142">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="2998f-143">使用しないでください。現在使用している場合は、ビジネス プロセスを移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2998f-143">Don't use it and if you are currently using it, you should move your business processes off of it.</span></span> <span data-ttu-id="2998f-144">代わりに、[**脅威**]、[**冒涜的表現**]、および [**ハラスメント**] の組み込み分類子を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2998f-144">We recommend using the **Threat**, **Profanity**, and **Harassment** built-in classifiers instead.</span></span>

- <span data-ttu-id="2998f-145">**履歴書**: 申請者の個人、教育、専門資格、作業経験、その他個人を識別する情報のテキストアカウントであるアイテムを検出します。</span><span class="sxs-lookup"><span data-stu-id="2998f-145">**Resumes**: detects items that are textual accounts of an applicant's personal, educational, professional qualifications, work experience, and other personally identifying information</span></span>
- <span data-ttu-id="2998f-146">**ソースコード**: GitHub で使用されている上位25台のコンピュータプログラミング言語で記述された命令およびステートメントのセットを含むアイテムを検出します。</span><span class="sxs-lookup"><span data-stu-id="2998f-146">**Source Code**: detects items that contain a set of instructions and statements written in the top 25 used computer programming languages on GitHub</span></span>

|<span data-ttu-id="2998f-147">言語名</span><span class="sxs-lookup"><span data-stu-id="2998f-147">language name</span></span>|||||
|---------|---------|---------|---------|---------|
|<span data-ttu-id="2998f-148">ActionScript</span><span class="sxs-lookup"><span data-stu-id="2998f-148">ActionScript</span></span>|<span data-ttu-id="2998f-149">C</span><span class="sxs-lookup"><span data-stu-id="2998f-149">C</span></span>        |<span data-ttu-id="2998f-150">C#</span><span class="sxs-lookup"><span data-stu-id="2998f-150">C#</span></span>       |<span data-ttu-id="2998f-151">C++</span><span class="sxs-lookup"><span data-stu-id="2998f-151">C++</span></span>     |<span data-ttu-id="2998f-152">Clojure</span><span class="sxs-lookup"><span data-stu-id="2998f-152">Clojure</span></span>  |
|<span data-ttu-id="2998f-153">CoffeeScript</span><span class="sxs-lookup"><span data-stu-id="2998f-153">CoffeeScript</span></span>|<span data-ttu-id="2998f-154">CSS</span><span class="sxs-lookup"><span data-stu-id="2998f-154">CSS</span></span>     |<span data-ttu-id="2998f-155">Go</span><span class="sxs-lookup"><span data-stu-id="2998f-155">Go</span></span>       |<span data-ttu-id="2998f-156">Haskell</span><span class="sxs-lookup"><span data-stu-id="2998f-156">Haskell</span></span> |<span data-ttu-id="2998f-157">HTML</span><span class="sxs-lookup"><span data-stu-id="2998f-157">HTML</span></span>     |
|<span data-ttu-id="2998f-158">Java</span><span class="sxs-lookup"><span data-stu-id="2998f-158">Java</span></span>     |<span data-ttu-id="2998f-159">JavaScript</span><span class="sxs-lookup"><span data-stu-id="2998f-159">JavaScript</span></span>|<span data-ttu-id="2998f-160">Lua</span><span class="sxs-lookup"><span data-stu-id="2998f-160">Lua</span></span>      |<span data-ttu-id="2998f-161">MATLAB</span><span class="sxs-lookup"><span data-stu-id="2998f-161">MATLAB</span></span>   |<span data-ttu-id="2998f-162">Objective-C</span><span class="sxs-lookup"><span data-stu-id="2998f-162">Objective-C</span></span>|
|<span data-ttu-id="2998f-163">Perl</span><span class="sxs-lookup"><span data-stu-id="2998f-163">Perl</span></span>     |<span data-ttu-id="2998f-164">PHP</span><span class="sxs-lookup"><span data-stu-id="2998f-164">PHP</span></span>      |<span data-ttu-id="2998f-165">Python</span><span class="sxs-lookup"><span data-stu-id="2998f-165">Python</span></span>   |<span data-ttu-id="2998f-166">R</span><span class="sxs-lookup"><span data-stu-id="2998f-166">R</span></span>        |<span data-ttu-id="2998f-167">Ruby</span><span class="sxs-lookup"><span data-stu-id="2998f-167">Ruby</span></span>     |
|<span data-ttu-id="2998f-168">Scala</span><span class="sxs-lookup"><span data-stu-id="2998f-168">Scala</span></span>    |<span data-ttu-id="2998f-169">Shell</span><span class="sxs-lookup"><span data-stu-id="2998f-169">Shell</span></span>    |<span data-ttu-id="2998f-170">Swift</span><span class="sxs-lookup"><span data-stu-id="2998f-170">Swift</span></span>    |<span data-ttu-id="2998f-171">Tex</span><span class="sxs-lookup"><span data-stu-id="2998f-171">Tex</span></span>      |<span data-ttu-id="2998f-172">Vim Script</span><span class="sxs-lookup"><span data-stu-id="2998f-172">Vim Script</span></span>|

> [!NOTE]
> <span data-ttu-id="2998f-173">ソースコードは、テキストの大部分がソースコードであるときに検出するためにトレーニングされています。</span><span class="sxs-lookup"><span data-stu-id="2998f-173">Source Code is trained to detect when the bulk of the text is source code.</span></span> <span data-ttu-id="2998f-174">プレーンテキストが混在しているソースコードテキストは検出されません。</span><span class="sxs-lookup"><span data-stu-id="2998f-174">It does not detect source code text that is interspersed with plain text.</span></span>

- <span data-ttu-id="2998f-175">**嫌がらせ**: 次の特徴に基づいて、1人または複数の個人を対象とした不快感を持つ、不快感を持つテキストアイテムの特定のカテゴリを検出します。競合、ethnicity、宗教、国内原産者、性別、性的なオリエンテーション、年齢、障碍</span><span class="sxs-lookup"><span data-stu-id="2998f-175">**Harassment**: detects a specific category of offensive language text items related to offensive conduct targeting one or multiple individuals based on the following traits: race, ethnicity, religion, national origin, gender, sexual orientation, age, disability</span></span>
- <span data-ttu-id="2998f-176">**不適切な用語**: 多くのユーザーを embarrass する式を含む、不快感を与える言語のテキストアイテムの特定のカテゴリを検出します。</span><span class="sxs-lookup"><span data-stu-id="2998f-176">**Profanity**: detects a specific category of offensive language text items that contain expressions that embarrass most people</span></span>
- <span data-ttu-id="2998f-177">**脅威**: 暴力を確定する脅威、または人またはプロパティに物理的な悪影響や損害を与えることに関連する脅威に関連する、不快な言語のテキストアイテムの特定のカテゴリを検出します。</span><span class="sxs-lookup"><span data-stu-id="2998f-177">**Threat**: detects a specific category of offensive language text items related to threats to commit violence or do physical harm or damage to a person or property</span></span>

<span data-ttu-id="2998f-178">これらは、[**Microsoft 365 コンプライアンス センター**]  >  [**データ分類 (プレビュー)**]  >  [**トレーニング可能な分類子**] ビューに表示され、ステータスは `Ready to use` です。</span><span class="sxs-lookup"><span data-stu-id="2998f-178">These appear in the **Microsoft 365 compliance center** > **Data classification (preview)** > **Trainable classifiers** view with the status of `Ready to use`.</span></span>

![分類子はすぐに使用できる分類子](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> <span data-ttu-id="2998f-180">不快な言葉、ハラスメント、冒涜的表現、および脅威の分類は、検索可能なテキストでのみ機能し、網羅的または完全ではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2998f-180">Please note that the offensive language, harassment, profanity, and threat classifiers only work with searchable text are not exhaustive or complete.</span></span>  <span data-ttu-id="2998f-181">さらに、言語と文化の基準は絶えず変化し、これらの現実に照らして、Microsoft は独自の裁量でこれらの分類子を更新する権利を留保します。</span><span class="sxs-lookup"><span data-stu-id="2998f-181">Further, language and cultural standards continually change, and in light of these realities, Microsoft reserves the right to update these classifiers in its discretion.</span></span> <span data-ttu-id="2998f-182">分類子は、不快な言語やその他の使用言語を監視するのに役立ちますが、分類子は、そのような言語の結果に対処するものではなく、そのような言語の使用を監視または応答する唯一の手段を組織に提供するものではありません。</span><span class="sxs-lookup"><span data-stu-id="2998f-182">While the classifiers may assist your organization in monitoring offensive and other language used, the classifiers do not address consequences of such language and are not intended to provide your organization's sole means of monitoring or responding to the use of such language.</span></span> <span data-ttu-id="2998f-183">事前にトレーニングされた分類子によって識別されたコンテンツの監視、施行、ブロック、削除、および保持に関するすべての決定は、Microsoft またはその子会社ではなく、お客様の組織の責任となります。</span><span class="sxs-lookup"><span data-stu-id="2998f-183">Your organization, and not Microsoft or its subsidiaries, remains responsible for all decisions related to monitoring, enforcement, blocking, removal and retention of any content identified by a pre-trained classifier.</span></span>

#### <a name="process-flow-for-using-built-in-classifiers"></a><span data-ttu-id="2998f-184">組み込み分類子を使用するためのプロセス フロー</span><span class="sxs-lookup"><span data-stu-id="2998f-184">Process flow for using built-in classifiers</span></span>

<span data-ttu-id="2998f-185">組み込み分類子をトレーニングする必要はありませんが、コンプライアンス ソリューションで使用する前に、それらが必要とするコンテンツのタイプを識別できることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2998f-185">Built-in classifiers don't need to be trained, but you do need to confirm that they will identify the types of content that you need them to before you use them in compliance solutions.</span></span> <span data-ttu-id="2998f-186">このフローに従って、事前トレーニング済みの分類子のテストを行います。</span><span class="sxs-lookup"><span data-stu-id="2998f-186">Testing a pre-trained classifier follows this flow.</span></span>

![事前トレーニング済みの分類子をテストするプロセス フロー](../media/classifier-pre-trained-classifier-flow.png)

### <a name="understanding-trainable-classifiers"></a><span data-ttu-id="2998f-188">トレーニング可能な分類子について</span><span class="sxs-lookup"><span data-stu-id="2998f-188">Understanding trainable classifiers</span></span>

<span data-ttu-id="2998f-189">組み込み分類子がニーズを満たさない場合は、独自の分類子を作成してトレーニングできます。</span><span class="sxs-lookup"><span data-stu-id="2998f-189">When the built-in classifiers don't meet your needs, you can create and train your own classifiers.</span></span> <span data-ttu-id="2998f-190">独自に作成するには、はるかに多くの作業が必要になりますが、組織のニーズに合わせてカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="2998f-190">There's significantly more work involved with creating your own, but they'll be much better tailored to your organizations needs.</span></span> <span data-ttu-id="2998f-191">事前トレーニング済みの分類子の使用方法の詳細については、「[組み込み分類子の使用](classifier-using-a-ready-to-use-classifier.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2998f-191">For more detail on how to use a pre-trained classifier, see [Using a built-in classifier](classifier-using-a-ready-to-use-classifier.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2998f-192">トレーニング可能な分類子を作成するユーザーのみが、その分類子によって行われた予測をトレーニングおよび確認できます。</span><span class="sxs-lookup"><span data-stu-id="2998f-192">Only the user who creates a trainable classifier can train and review predictions made by that classifier.</span></span>

#### <a name="process-flow-for-creating-trainable-classifiers"></a><span data-ttu-id="2998f-193">トレーニング可能な分類子を作成するためのプロセス フロー</span><span class="sxs-lookup"><span data-stu-id="2998f-193">Process flow for creating trainable classifiers</span></span>

<span data-ttu-id="2998f-194">保持ポリシーや通信監督など、コンプライアンス ソリューションで使用するトレーニング可能な分類子の作成と公開はこのフローに従います。</span><span class="sxs-lookup"><span data-stu-id="2998f-194">Creating and publishing a trainable classifier for use in compliance solutions, such as retention policies and communication supervision, follows this flow.</span></span> <span data-ttu-id="2998f-195">トレーニング可能な分類子の作成の詳細については、「[トレーニング可能な分類子の作成](classifier-creating-a-trainable-classifier.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2998f-195">For more detail on creating a trainable classifier see, [Creating a trainable classifier](classifier-creating-a-trainable-classifier.md).</span></span>

![プロセス フローのトレーニング可能な分類子](../media/classifier-trainable-classifier-flow.png)

## <a name="see-also"></a><span data-ttu-id="2998f-197">関連項目</span><span class="sxs-lookup"><span data-stu-id="2998f-197">See also</span></span>

- [<span data-ttu-id="2998f-198">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="2998f-198">retention labels</span></span>](labels.md)
- [<span data-ttu-id="2998f-199">保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="2998f-199">retention policies</span></span>](retention-policies.md)
- [<span data-ttu-id="2998f-200">データ損失防止 (DLP)</span><span class="sxs-lookup"><span data-stu-id="2998f-200">data loss prevention (DLP)</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="2998f-201">秘密度ラベル</span><span class="sxs-lookup"><span data-stu-id="2998f-201">sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="2998f-202">機密情報の種類</span><span class="sxs-lookup"><span data-stu-id="2998f-202">sensitive information types</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="2998f-203">ドキュメント フィンガー プリント</span><span class="sxs-lookup"><span data-stu-id="2998f-203">document finger printing</span></span>](document-fingerprinting.md)
- [<span data-ttu-id="2998f-204">完全に一致するデータ</span><span class="sxs-lookup"><span data-stu-id="2998f-204">exact data match</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)