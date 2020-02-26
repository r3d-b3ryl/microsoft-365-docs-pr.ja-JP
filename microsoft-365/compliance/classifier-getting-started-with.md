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
description: Microsoft 365 trainable クラシファイアは、コンテンツのさまざまな種類を認識するために学習することができます。 分類子がトレーニングされると、結果が正確であることを確認できます。 次に、これを使用して組織のコンテンツを検索し、それを分類して、保持または機密ラベルを適用したり、データ損失防止 (DLP) またはアイテム保持ポリシーに含めたりします。
ms.openlocfilehash: 877001784f30f4b51e0e8c9fdb15091ea6308bf5
ms.sourcegitcommit: 109b44aa71bb8453d0a602663df0fcf7ed7dfdbe
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/25/2020
ms.locfileid: "42277204"
---
# <a name="getting-started-with-trainable-classifiers-preview"></a><span data-ttu-id="2330c-105">トレーニング可能な分類子の使用を開始する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="2330c-105">Getting started with trainable classifiers (preview)</span></span>

<span data-ttu-id="2330c-106">コンテンツを保護し、適切に処理するために、コンテンツの分類とラベル付けを行うことは、情報保護の統制の出発点となります。</span><span class="sxs-lookup"><span data-stu-id="2330c-106">Classifying and labeling content so it can be protected and handled properly is the starting place for the information protection discipline.</span></span> <span data-ttu-id="2330c-107">Microsoft 365 には、コンテンツを分類するための3つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="2330c-107">Microsoft 365 has three ways to classify content.</span></span>

## <a name="manually"></a><span data-ttu-id="2330c-108">手動</span><span class="sxs-lookup"><span data-stu-id="2330c-108">Manually</span></span>

<span data-ttu-id="2330c-109">このメソッドには、人間の判断とアクションが必要です。</span><span class="sxs-lookup"><span data-stu-id="2330c-109">This method requires human judgment and action.</span></span> <span data-ttu-id="2330c-110">管理者は、既存のラベルと機密情報の種類を使用するか、独自に作成して発行することができます。</span><span class="sxs-lookup"><span data-stu-id="2330c-110">An admin may either use the pre-existing labels and sensitive information types or create their own and then publish them.</span></span> <span data-ttu-id="2330c-111">ユーザーおよび管理者は、発生時にコンテンツに適用されます。</span><span class="sxs-lookup"><span data-stu-id="2330c-111">Users and admins apply them to content as they encounter it.</span></span> <span data-ttu-id="2330c-112">その後、コンテンツを保護し、廃棄を管理できます。</span><span class="sxs-lookup"><span data-stu-id="2330c-112">You can then protect the content and manage its disposition.</span></span>

## <a name="automated-pattern-matching"></a><span data-ttu-id="2330c-113">自動パターンマッチング</span><span class="sxs-lookup"><span data-stu-id="2330c-113">Automated pattern matching</span></span>

<span data-ttu-id="2330c-114">この分類機構のカテゴリには、コンテンツの検索が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2330c-114">This category of classification mechanisms includes finding content by:</span></span>

- <span data-ttu-id="2330c-115">キーワードまたはメタデータ値 (キーワードクエリ言語)</span><span class="sxs-lookup"><span data-stu-id="2330c-115">keywords or metadata values (keyword query language)</span></span>
- <span data-ttu-id="2330c-116">ソーシャルセキュリティ、クレジットカード、または銀行口座番号[(機密情報の種類)](what-the-sensitive-information-types-look-for.md)など、以前に識別された機密情報のパターンを使用する</span><span class="sxs-lookup"><span data-stu-id="2330c-116">using previously identified patterns of sensitive information like social security, credit card or bank account numbers [(sensitive information types)](what-the-sensitive-information-types-look-for.md)</span></span>
- <span data-ttu-id="2330c-117">テンプレートのバリエーションであるためにアイテムを認識する[(ドキュメントのフィンガープリント)](document-fingerprinting.md)</span><span class="sxs-lookup"><span data-stu-id="2330c-117">Recognizing an item because it's a variation on a template [(document finger printing)](document-fingerprinting.md)</span></span>
- <span data-ttu-id="2330c-118">正確な文字列の存在[(正確なデータ一致)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="2330c-118">using the presence of exact strings [(exact data match)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

<span data-ttu-id="2330c-119">機密情報と保持ラベルを自動的に適用して、[データ損失防止 (DLP)](data-loss-prevention-policies.md)と[アイテム保持ポリシー](retention-policies.md)でコンテンツを使用できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="2330c-119">Sensitivity and retention labels can then be automatically applied to make the content available for use in [data loss prevention (DLP)](data-loss-prevention-policies.md) and [retention policies](retention-policies.md).</span></span>

## <a name="trainable-classifiers"></a><span data-ttu-id="2330c-120">Trainable 分類子</span><span class="sxs-lookup"><span data-stu-id="2330c-120">Trainable classifiers</span></span>

<span data-ttu-id="2330c-121">この分類方法は、手動または自動のパターン一致方式のどちらかによって簡単に識別できないコンテンツに特に適しています。</span><span class="sxs-lookup"><span data-stu-id="2330c-121">This classification method is particularly well suited to content that isn't easily identified by either the manual or automated pattern matching methods.</span></span> <span data-ttu-id="2330c-122">この分類の方法は、アイテムに基づいてアイテムを識別する分類子をトレーニングすることになります (アイテムに含まれる要素ではありません) (パターンマッチング)。</span><span class="sxs-lookup"><span data-stu-id="2330c-122">This method of classification is more about training a classifier to identify an item based on what the item is, not by elements that are in the item (pattern matching).</span></span> <span data-ttu-id="2330c-123">分類子は、分類するコンテンツの数百の例を参照して、コンテンツの種類を識別する方法を学習します。</span><span class="sxs-lookup"><span data-stu-id="2330c-123">A classifier learns how to identify a type of content by looking at hundreds of examples of the content you're interested in classifying.</span></span> <span data-ttu-id="2330c-124">最初に、カテゴリに含まれている例を示します。</span><span class="sxs-lookup"><span data-stu-id="2330c-124">You start by feeding it examples that are definitely in the category.</span></span> <span data-ttu-id="2330c-125">それらを処理したら、一致する比較例と一致しない例の両方を組み合わせてテストします。</span><span class="sxs-lookup"><span data-stu-id="2330c-125">Once it processes those, you test it by giving it a mix of both matching and non-matching examples.</span></span> <span data-ttu-id="2330c-126">その後、分類子は、指定されたアイテムが作成中のカテゴリに属するかどうかについての予測を行います。</span><span class="sxs-lookup"><span data-stu-id="2330c-126">The classifier then makes predictions as to whether any given item falls into the category you're building.</span></span> <span data-ttu-id="2330c-127">その後、その結果を確認し、陽性、ネガ、偽陽性、誤検知を並べ替えて、予測の精度を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="2330c-127">You then confirm its results, sorting out the positives, negatives, false positives, and false negatives to help increase the accuracy of its predictions.</span></span> <span data-ttu-id="2330c-128">トレーニング対象の分類子を発行すると、SharePoint Online、Exchange、および OneDrive などの場所にあるアイテムが並べ替えられ、コンテンツが分類されます。</span><span class="sxs-lookup"><span data-stu-id="2330c-128">When you publish the trained classifier, it sorts through items in locations like SharePoint Online, Exchange, and OneDrive, and classifies the content.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2330c-129">両方の種類の分類子は、条件と[通信のコンプライアンス](communication-compliance.md)[に基づいて、自動適用の保持ラベルポリシー](labels.md#applying-a-retention-label-automatically-based-on-conditions)の条件として使用できます。</span><span class="sxs-lookup"><span data-stu-id="2330c-129">Both types of classifiers are available as a condition for [auto-apply retention label policy based on a condition](labels.md#applying-a-retention-label-automatically-based-on-conditions) and [Communication compliance](communication-compliance.md).</span></span> <span data-ttu-id="2330c-130">機密ラベルは、組み込みの分類子を条件としてのみ使用できます。詳細については、「[コンテンツに機密ラベルを自動的に適用](apply-sensitivity-label-automatically.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2330c-130">Sensitivity labels can only use built-in classifiers as a condition, see [Apply a sensitivity label to content automatically](apply-sensitivity-label-automatically.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2330c-131">Trainable 分類子は、暗号化されておらず英語になっているアイテムに対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="2330c-131">Trainable classifiers only work with items that are not encrypted and are in English.</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="2330c-132">ライセンス要件</span><span class="sxs-lookup"><span data-stu-id="2330c-132">Licensing requirements</span></span>

<span data-ttu-id="2330c-133">Trainable 分類子は、Microsoft 365 E5 または E5 準拠の機能です。</span><span class="sxs-lookup"><span data-stu-id="2330c-133">Trainable classifiers are a Microsoft 365 E5, or E5 Compliance feature.</span></span> <span data-ttu-id="2330c-134">それらを利用するには、これらのサブスクリプションのいずれかが必要です。</span><span class="sxs-lookup"><span data-stu-id="2330c-134">You must have one of these subscriptions to make use of them.</span></span>

## <a name="types-of-classifiers"></a><span data-ttu-id="2330c-135">分類子の種類</span><span class="sxs-lookup"><span data-stu-id="2330c-135">Types of classifiers</span></span>

<span data-ttu-id="2330c-136">組み込みの分類子と trainable 分類子があります。</span><span class="sxs-lookup"><span data-stu-id="2330c-136">There are built-in classifiers and trainable classifiers.</span></span> <span data-ttu-id="2330c-137">Trainable クラシファイアを公開された状態にするには、トレーニングに必要な時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="2330c-137">Getting a trainable classifier to a publishable state requires a time investment to train it.</span></span> <span data-ttu-id="2330c-138">分類子の使用を開始するために、Microsoft 365 にはいくつかの組み込み分類子が付属しています。</span><span class="sxs-lookup"><span data-stu-id="2330c-138">To help you get started using classifiers, Microsoft 365 comes with a few built-in classifiers.</span></span>

> [!NOTE]
> <span data-ttu-id="2330c-139">分類とラベル付けワークフローに組み込みの分類子を使用する前に、分類の予測が期待どおりになっていることを確認するために、カテゴリに適合していると思われる組織のコンテンツのサンプルに照らしてテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2330c-139">Before using any built-in classifier in your classification and labeling workflow, you should test it against a sample of your organizations content that you feel fits the category to verify that its classification predictions meet your expectations.</span></span>

### <a name="understanding-built-in-classifiers"></a><span data-ttu-id="2330c-140">組み込み分類子について</span><span class="sxs-lookup"><span data-stu-id="2330c-140">Understanding built-in classifiers</span></span>

<span data-ttu-id="2330c-141">Microsoft 365 には、次の6つの組み込み分類子が付属しています。</span><span class="sxs-lookup"><span data-stu-id="2330c-141">Microsoft 365 comes with six built-in classifiers:</span></span>

- <span data-ttu-id="2330c-142">**不快な言葉**: profanities、slurs、taunts、および偽装式を含むテキストアイテムを検出します (これは、より不快な用語と同じ意味を持つ式です)。</span><span class="sxs-lookup"><span data-stu-id="2330c-142">**Offensive Language**: detects text items that contain profanities, slurs, taunts, and disguised expressions (which are expressions that have the same meaning as a more offensive term).</span></span>
- <span data-ttu-id="2330c-143">**履歴書**: 申請者の個人、教育、専門資格、作業経験、その他の個人を特定できる情報のテキストアカウントであるアイテムを検出します。</span><span class="sxs-lookup"><span data-stu-id="2330c-143">**Resumes**: detects items that are textual accounts of an applicant's personal, educational, professional qualifications, work experience, and other personally identifying information.</span></span>
- <span data-ttu-id="2330c-144">**SourceCode**: 広く使用されているコンピュータプログラミング言語で記述された命令およびステートメントのセットを含むアイテムを検出します。</span><span class="sxs-lookup"><span data-stu-id="2330c-144">**SourceCode**: detects items that contain a set of instructions and statements written in widely used computer programming languages.</span></span>
- <span data-ttu-id="2330c-145">**嫌がらせ**: 次の特徴に基づいて、1人または複数の個人を対象とした不快感のある言語のテキストアイテムの特定のカテゴリを検出します。競合、ethnicity、宗教、国内原産者、性別、性的なオリエンテーション、年齢、障碍。</span><span class="sxs-lookup"><span data-stu-id="2330c-145">**Harassment**: detects a specific category of offensive language text items related to offensive conduct targeting one or multiple individuals based on the following traits: race, ethnicity, religion, national origin, gender, sexual orientation, age, disability.</span></span>
- <span data-ttu-id="2330c-146">**不適切な用語**: 多くの人々を embarrass する式を含む、不快感を与える言語のテキストアイテムの特定のカテゴリを検出します。</span><span class="sxs-lookup"><span data-stu-id="2330c-146">**Profanity**: detects a specific category of offensive language text items that contain expressions that embarrass most people.</span></span>
- <span data-ttu-id="2330c-147">**脅威**: 暴力をコミットする脅威に関連する、不快感を与える、個人またはプロパティに対する物理的な損傷または損害をもたらす、不快な言語のテキストアイテムの特定のカテゴリを検出します。</span><span class="sxs-lookup"><span data-stu-id="2330c-147">**Threat**: detects a specific category of offensive language text items related to threats to commit violence or do physical harm or damage to a person or property.</span></span>

<span data-ttu-id="2330c-148">これらは、 **Microsoft 365 コンプライアンスセンター** > **データ分類 (プレビュー)** > **Trainable 分類子**ビューに、の`Ready to use`状態と共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2330c-148">These appear in the **Microsoft 365 compliance center** > **Data classification (preview)** > **Trainable classifiers** view with the status of `Ready to use`.</span></span>

![分類子-すぐに使用できる分類子](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> <span data-ttu-id="2330c-150">不快な言葉、嫌がらせ、冒涜、および脅威の分類子は、検索可能なテキストのみで機能することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2330c-150">Please note that the offensive language, harassment, profanity, and threat classifiers only work with searchable text are not exhaustive or complete.</span></span>  <span data-ttu-id="2330c-151">さらに、言語と文化的な標準が絶えず変化し、これらの現実からは、これらの分類子を裁量で更新する権利を Microsoft が留保します。</span><span class="sxs-lookup"><span data-stu-id="2330c-151">Further, language and cultural standards continually change, and in light of these realities, Microsoft reserves the right to update these classifiers in its discretion.</span></span> <span data-ttu-id="2330c-152">分類子は、お客様の組織が不快な言葉や使用されている他の言語を監視するのに役立ちますが、分類子は、そのような言語の結果に対応していません。そのような言語。</span><span class="sxs-lookup"><span data-stu-id="2330c-152">While the classifiers may assist your organization in monitoring offensive and other language used, the classifiers do not address consequences of such language and are not intended to provide your organization’s sole means of monitoring or responding to the use of such language.</span></span> <span data-ttu-id="2330c-153">お客様の組織は、Microsoft またはその子会社ではなく、事前に訓練された分類子によって識別されるコンテンツの監視、実施、ブロック、削除、保持に関連するすべての意思決定に対して責任を負うことになります。</span><span class="sxs-lookup"><span data-stu-id="2330c-153">Your organization, and not Microsoft or its subsidiaries, remains responsible for all decisions related to monitoring, enforcement, blocking, removal and retention of any content identified by a pre-trained classifier.</span></span>

#### <a name="process-flow-for-using-built-in-classifiers"></a><span data-ttu-id="2330c-154">組み込み分類子を使用するためのプロセスフロー</span><span class="sxs-lookup"><span data-stu-id="2330c-154">Process flow for using built-in classifiers</span></span>

<span data-ttu-id="2330c-155">組み込みの分類子をトレーニングする必要はありませんが、コンプライアンスソリューションで使用する前に、必要なコンテンツの種類を特定することを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2330c-155">Built-in classifiers don't need to be trained, but you do need to confirm that they will identify the types of content that you need them to before you use them in compliance solutions.</span></span> <span data-ttu-id="2330c-156">事前に学習した分類子のテストは、このフローに従います。</span><span class="sxs-lookup"><span data-stu-id="2330c-156">Testing a pre-trained classifier follows this flow.</span></span>

![事前に学習した分類子をテストするプロセスフロー](../media/classifier-pre-trained-classifier-flow.png)

### <a name="understanding-trainable-classifiers"></a><span data-ttu-id="2330c-158">Trainable 分類子について</span><span class="sxs-lookup"><span data-stu-id="2330c-158">Understanding trainable classifiers</span></span>

<span data-ttu-id="2330c-159">組み込みの分類子がニーズに合わない場合は、独自の分類子を作成してトレーニングできます。</span><span class="sxs-lookup"><span data-stu-id="2330c-159">When the built-in classifiers don't meet your needs, you can create and train your own classifiers.</span></span> <span data-ttu-id="2330c-160">独自の作成に関しては、非常に多くの作業が必要になりますが、組織のニーズに応じてより適切にカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="2330c-160">There's significantly more work involved with creating your own, but they'll be much better tailored to your organizations needs.</span></span> <span data-ttu-id="2330c-161">事前に学習した分類子の使用方法の詳細については、「[組み込みの分類子を使用](classifier-using-a-ready-to-use-classifier.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2330c-161">For more detail on how to use a pre-trained classifier, see [Using a built-in classifier](classifier-using-a-ready-to-use-classifier.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2330c-162">Trainable 分類子を作成したユーザーのみが、その分類子によって行われた予測をトレーニングし、確認することができます。</span><span class="sxs-lookup"><span data-stu-id="2330c-162">Only the user who creates a trainable classifier can train and review predictions made by that classifier.</span></span>

#### <a name="process-flow-for-creating-trainable-classifiers"></a><span data-ttu-id="2330c-163">Trainable 分類子を作成するためのプロセスフロー</span><span class="sxs-lookup"><span data-stu-id="2330c-163">Process flow for creating trainable classifiers</span></span>

<span data-ttu-id="2330c-164">Trainable 分類子を作成して、アイテム保持ポリシー、通信監督などのコンプライアンスソリューションで使用するために、このフローに従います。</span><span class="sxs-lookup"><span data-stu-id="2330c-164">Creating and publishing a trainable classifier for use in compliance solutions, such as retention policies and communication supervision, follows this flow.</span></span> <span data-ttu-id="2330c-165">Trainable 分類子を作成する方法の詳細については、「 [trainable クラシファイアを作成](classifier-creating-a-trainable-classifier.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2330c-165">For more detail on creating a trainable classifier see, [Creating a trainable classifier](classifier-creating-a-trainable-classifier.md).</span></span>

![プロセスフロー trainable クラシファイア](../media/classifier-trainable-classifier-flow.png)

## <a name="see-also"></a><span data-ttu-id="2330c-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="2330c-167">See also</span></span>

- [<span data-ttu-id="2330c-168">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="2330c-168">retention labels</span></span>](labels.md)
- [<span data-ttu-id="2330c-169">アイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="2330c-169">retention policies</span></span>](retention-policies.md)
- [<span data-ttu-id="2330c-170">データ損失防止 (DLP)</span><span class="sxs-lookup"><span data-stu-id="2330c-170">data loss prevention (DLP)</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="2330c-171">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="2330c-171">sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="2330c-172">機密情報の種類</span><span class="sxs-lookup"><span data-stu-id="2330c-172">sensitive information types</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="2330c-173">ドキュメントのフィンガープリント</span><span class="sxs-lookup"><span data-stu-id="2330c-173">document finger printing</span></span>](document-fingerprinting.md)
- [<span data-ttu-id="2330c-174">正確なデータ一致</span><span class="sxs-lookup"><span data-stu-id="2330c-174">exact data match</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
