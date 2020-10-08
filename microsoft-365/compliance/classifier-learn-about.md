---
title: トレーニング可能な分類子の詳細 (プレビュー)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 トレーニング可能な分類子は、陽性と陰性のサンプルを提供することによって、さまざまなタイプのコンテンツを認識するトレーニング ツールです。 分類子がトレーニングされると、その結果が正しいことを確認します。 次に、それを使用して組織のコンテンツを検索し、分類して保持または秘密度ラベルを適用するか、データ損失防止 (DLP) または保持ポリシーに含めます。
ms.openlocfilehash: 7abfbe101508d24e58464ff38b14ab87447001f0
ms.sourcegitcommit: 5e40c760c1af2a4cc6d85cb782b17f5c979677c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2020
ms.locfileid: "48379309"
---
# <a name="learn-about-classifiers-preview"></a><span data-ttu-id="0334a-105">分類子 (プレビュー) について</span><span class="sxs-lookup"><span data-stu-id="0334a-105">Learn about classifiers (preview)</span></span>

<span data-ttu-id="0334a-106">コンテンツを適切に保護および処理できるようにコンテンツを分類およびラベル付けすることは、情報保護に対するトレーニングの出発点です。</span><span class="sxs-lookup"><span data-stu-id="0334a-106">Classifying and labeling content so it can be protected and handled properly is the starting place for the information protection discipline.</span></span> <span data-ttu-id="0334a-107">Microsoft 365 には、コンテンツを分類する 3 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="0334a-107">Microsoft 365 has three ways to classify content.</span></span>

## <a name="manually"></a><span data-ttu-id="0334a-108">手動</span><span class="sxs-lookup"><span data-stu-id="0334a-108">Manually</span></span>

<span data-ttu-id="0334a-109">この方法では、人間の判断と行動が必要です。</span><span class="sxs-lookup"><span data-stu-id="0334a-109">This method requires human judgment and action.</span></span> <span data-ttu-id="0334a-110">管理者は、既存のラベルと機密情報の種類を使用するか、独自のラベルを作成して公開することができます。</span><span class="sxs-lookup"><span data-stu-id="0334a-110">An admin may either use the pre-existing labels and sensitive information types or create their own and then publish them.</span></span> <span data-ttu-id="0334a-111">ユーザーと管理者は、遭遇したコンテンツをそれらに適用します。</span><span class="sxs-lookup"><span data-stu-id="0334a-111">Users and admins apply them to content as they encounter it.</span></span> <span data-ttu-id="0334a-112">その後、コンテンツを保護し、その処分を管理できます。</span><span class="sxs-lookup"><span data-stu-id="0334a-112">You can then protect the content and manage its disposition.</span></span>

## <a name="automated-pattern-matching"></a><span data-ttu-id="0334a-113">自動パターン マッチング</span><span class="sxs-lookup"><span data-stu-id="0334a-113">Automated pattern matching</span></span>

<span data-ttu-id="0334a-114">この分類メカニズムのカテゴリには、コンテンツの検索が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0334a-114">This category of classification mechanisms include finding content by:</span></span>

- <span data-ttu-id="0334a-115">キーワードまたはメタデータ値 (キーワードクエリ言語)。</span><span class="sxs-lookup"><span data-stu-id="0334a-115">Keywords or metadata values (keyword query language).</span></span>
- <span data-ttu-id="0334a-116">ソーシャルセキュリティ、クレジットカード、または銀行口座番号 [(機密情報の種類のエンティティ定義)](sensitive-information-type-entity-definitions.md)など、以前に識別された機密情報のパターンを使用します。</span><span class="sxs-lookup"><span data-stu-id="0334a-116">Using previously identified patterns of sensitive information like social security, credit card or bank account numbers [(Sensitive information type entity definitions)](sensitive-information-type-entity-definitions.md).</span></span>
- <span data-ttu-id="0334a-117">テンプレートのバリエーションであるためにアイテムを認識する [(ドキュメントのフィンガープリント)](document-fingerprinting.md)。</span><span class="sxs-lookup"><span data-stu-id="0334a-117">Recognizing an item because it's a variation on a template [(document finger printing)](document-fingerprinting.md).</span></span>
- <span data-ttu-id="0334a-118">正確な文字列の存在 [(正確なデータ一致)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="0334a-118">Using the presence of exact strings [(exact data match)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

<span data-ttu-id="0334a-119">機密情報と保持ラベルを自動的に適用して、 [データ損失防止 (DLP)](data-loss-prevention-policies.md) および [保持ラベルの自動適用ポリシー](apply-retention-labels-automatically.md)で使用できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="0334a-119">Sensitivity and retention labels can then be automatically applied to make the content available for use in [data loss prevention (DLP)](data-loss-prevention-policies.md) and [auto-apply polices for retention labels](apply-retention-labels-automatically.md).</span></span>

## <a name="classifiers"></a><span data-ttu-id="0334a-120">器</span><span class="sxs-lookup"><span data-stu-id="0334a-120">Classifiers</span></span>

<span data-ttu-id="0334a-121">この分類方法は、手動または自動のパターン マッチング方法では簡単に識別できないコンテンツに特に適しています。</span><span class="sxs-lookup"><span data-stu-id="0334a-121">This classification method is particularly well suited to content that isn't easily identified by either the manual or automated pattern matching methods.</span></span> <span data-ttu-id="0334a-122">この分類方法は、アイテムに含まれる要素ではなく、アイテムが何であるかに基づいてアイテムを識別するように分類子をトレーニングすることです (パターン マッチング)。</span><span class="sxs-lookup"><span data-stu-id="0334a-122">This method of classification is more about training a classifier to identify an item based on what the item is, not by elements that are in the item (pattern matching).</span></span> <span data-ttu-id="0334a-123">分類子は、分類したいコンテンツの数百の例を見て、コンテンツのタイプを識別する方法を学びます。</span><span class="sxs-lookup"><span data-stu-id="0334a-123">A classifier learns how to identify a type of content by looking at hundreds of examples of the content you're interested in classifying.</span></span> <span data-ttu-id="0334a-124">それを間違いなくカテゴリーにある例に与えることから始めます。</span><span class="sxs-lookup"><span data-stu-id="0334a-124">You start by feeding it examples that are definitely in the category.</span></span> <span data-ttu-id="0334a-125">それらを処理したら、一致する例と一致しない例の両方を組み合わせてテストします。</span><span class="sxs-lookup"><span data-stu-id="0334a-125">Once it processes those, you test it by giving it a mix of both matching and non-matching examples.</span></span> <span data-ttu-id="0334a-126">次に、分類子は、特定のアイテムが作成中のカテゴリに該当するかどうかを予測します。</span><span class="sxs-lookup"><span data-stu-id="0334a-126">The classifier then makes predictions as to whether any given item falls into the category you're building.</span></span> <span data-ttu-id="0334a-127">その後、結果を確認し、真陽性、真陽性、誤検知、誤検知を並べ替えて、予測の精度を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="0334a-127">You then confirm its results, sorting out the true positives, true negatives, false positives, and false negatives to help increase the accuracy of its predictions.</span></span> 

<span data-ttu-id="0334a-128">分類子を発行すると、SharePoint Online、Exchange、および OneDrive などの場所にあるアイテムが並べ替えられ、コンテンツが分類されます。</span><span class="sxs-lookup"><span data-stu-id="0334a-128">When you publish the classifier, it sorts through items in locations like SharePoint Online, Exchange, and OneDrive, and classifies the content.</span></span> <span data-ttu-id="0334a-129">分類子を発行した後は、最初のトレーニングプロセスに似たフィードバックプロセスを使用して、それを引き続きトレーニングできます。</span><span class="sxs-lookup"><span data-stu-id="0334a-129">After you publish the classifier, you can continue to train it using a feedback process that is similar to the initial training process.</span></span>

### <a name="where-you-can-use-trainable-classifiers"></a><span data-ttu-id="0334a-130">Trainable 分類子を使用できる場所</span><span class="sxs-lookup"><span data-stu-id="0334a-130">Where you can use trainable classifiers</span></span>
<span data-ttu-id="0334a-131">組み込み分類子と trainable 分類子は、両方とも、[条件](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels)および[通信コンプライアンス](communication-compliance.md)に基づいて、[機密ラベルを使用した Office autolabeling](apply-sensitivity-label-automatically.md)の条件として使用できます。</span><span class="sxs-lookup"><span data-stu-id="0334a-131">Both built-in classifiers and trainable classifiers are available as a condition for [Office autolabeling with sensitivity labels](apply-sensitivity-label-automatically.md), [auto-apply retention label policy based on a condition](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) and in [communication compliance](communication-compliance.md).</span></span> 

<span data-ttu-id="0334a-132">機密ラベルでは分類子を条件として使用できます。「 [機密ラベルをコンテンツに自動的に適用](apply-sensitivity-label-automatically.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0334a-132">Sensitivity labels can use classifiers as conditions, see [Apply a sensitivity label to content automatically](apply-sensitivity-label-automatically.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0334a-133">分類子は、暗号化されておらず英語になっているアイテムに対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="0334a-133">Classifiers only work with items that are not encrypted and are in English.</span></span>

## <a name="types-of-classifiers"></a><span data-ttu-id="0334a-134">分類子のタイプ</span><span class="sxs-lookup"><span data-stu-id="0334a-134">Types of classifiers</span></span>

- <span data-ttu-id="0334a-135">事前にトレーニングされた**分類子**-Microsoft は、トレーニングを実施せずに使用を開始できる分類子を作成し、事前にトレーニングを受けています。</span><span class="sxs-lookup"><span data-stu-id="0334a-135">**pre-trained classifiers** - Microsoft has created and pre-trained a number of classifiers that you can start using without training them.</span></span> <span data-ttu-id="0334a-136">これらの分類子は、の状態と共に表示され `Ready to use` ます。</span><span class="sxs-lookup"><span data-stu-id="0334a-136">These classifiers will appear with the status of `Ready to use`.</span></span>
- <span data-ttu-id="0334a-137">**カスタム分類子** -事前に訓練された分類子の範囲を超えて分類する必要がある場合は、独自の分類子を作成してトレーニングできます。</span><span class="sxs-lookup"><span data-stu-id="0334a-137">**custom classifiers** - If you have classification needs that extend beyond what the pre-trained classifiers cover, you can create and train your own classifiers.</span></span>

### <a name="pre-trained-classifiers"></a><span data-ttu-id="0334a-138">事前にトレーニングした分類子</span><span class="sxs-lookup"><span data-stu-id="0334a-138">Pre-trained classifiers</span></span>

<span data-ttu-id="0334a-139">Microsoft 365 には、事前にトレーニングされた分類子が5つあります。</span><span class="sxs-lookup"><span data-stu-id="0334a-139">Microsoft 365 comes with five pre-trained classifiers:</span></span>

> [!CAUTION]
> <span data-ttu-id="0334a-140">不快なのは、誤検知の数が多いので、 **不快感** を持つ言語の事前トレーニングされた分類子を廃止しています。</span><span class="sxs-lookup"><span data-stu-id="0334a-140">We are deprecating the **Offensive Language** pre-trained classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="0334a-141">使用しないでください。現在使用している場合は、ビジネス プロセスを移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0334a-141">Don't use it and if you are currently using it, you should move your business processes off of it.</span></span> <span data-ttu-id="0334a-142">代わりに、 **脅威**、 **プロファニティ**、および **嫌がらせ** の事前トレーニング分類子を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0334a-142">We recommend using the **Threat**, **Profanity**, and **Harassment** pre-trained classifiers instead.</span></span>

- <span data-ttu-id="0334a-143">**履歴書**: 申請者の個人、教育、専門資格、作業経験、その他個人を識別する情報のテキストアカウントであるアイテムを検出します。</span><span class="sxs-lookup"><span data-stu-id="0334a-143">**Resumes**: detects items that are textual accounts of an applicant's personal, educational, professional qualifications, work experience, and other personally identifying information</span></span>
- <span data-ttu-id="0334a-144">**ソースコード**: GitHub で使用されている上位25台のコンピュータプログラミング言語で記述された命令およびステートメントのセットを含むアイテムを検出します。</span><span class="sxs-lookup"><span data-stu-id="0334a-144">**Source Code**: detects items that contain a set of instructions and statements written in the top 25 used computer programming languages on GitHub</span></span>
    - <span data-ttu-id="0334a-145">ActionScript</span><span class="sxs-lookup"><span data-stu-id="0334a-145">ActionScript</span></span>
    - <span data-ttu-id="0334a-146">C</span><span class="sxs-lookup"><span data-stu-id="0334a-146">C</span></span>
    - <span data-ttu-id="0334a-147">C#</span><span class="sxs-lookup"><span data-stu-id="0334a-147">C#</span></span>
    - <span data-ttu-id="0334a-148">C++</span><span class="sxs-lookup"><span data-stu-id="0334a-148">C++</span></span>
    - <span data-ttu-id="0334a-149">Clojure</span><span class="sxs-lookup"><span data-stu-id="0334a-149">Clojure</span></span>
    - <span data-ttu-id="0334a-150">CoffeeScript</span><span class="sxs-lookup"><span data-stu-id="0334a-150">CoffeeScript</span></span>
    - <span data-ttu-id="0334a-151">Go</span><span class="sxs-lookup"><span data-stu-id="0334a-151">Go</span></span>
    - <span data-ttu-id="0334a-152">Haskell</span><span class="sxs-lookup"><span data-stu-id="0334a-152">Haskell</span></span>
    - <span data-ttu-id="0334a-153">Java</span><span class="sxs-lookup"><span data-stu-id="0334a-153">Java</span></span>
    - <span data-ttu-id="0334a-154">JavaScript</span><span class="sxs-lookup"><span data-stu-id="0334a-154">JavaScript</span></span>
    - <span data-ttu-id="0334a-155">Lua</span><span class="sxs-lookup"><span data-stu-id="0334a-155">Lua</span></span>
    - <span data-ttu-id="0334a-156">MATLAB</span><span class="sxs-lookup"><span data-stu-id="0334a-156">MATLAB</span></span>
    - <span data-ttu-id="0334a-157">Objective-C</span><span class="sxs-lookup"><span data-stu-id="0334a-157">Objective-C</span></span>
    - <span data-ttu-id="0334a-158">Perl</span><span class="sxs-lookup"><span data-stu-id="0334a-158">Perl</span></span>
    - <span data-ttu-id="0334a-159">PHP</span><span class="sxs-lookup"><span data-stu-id="0334a-159">PHP</span></span>
    - <span data-ttu-id="0334a-160">Python</span><span class="sxs-lookup"><span data-stu-id="0334a-160">Python</span></span>
    - <span data-ttu-id="0334a-161">R</span><span class="sxs-lookup"><span data-stu-id="0334a-161">R</span></span>
    - <span data-ttu-id="0334a-162">Ruby</span><span class="sxs-lookup"><span data-stu-id="0334a-162">Ruby</span></span>
    - <span data-ttu-id="0334a-163">Scala</span><span class="sxs-lookup"><span data-stu-id="0334a-163">Scala</span></span>
    - <span data-ttu-id="0334a-164">Shell</span><span class="sxs-lookup"><span data-stu-id="0334a-164">Shell</span></span>
    - <span data-ttu-id="0334a-165">Swift</span><span class="sxs-lookup"><span data-stu-id="0334a-165">Swift</span></span>
    - <span data-ttu-id="0334a-166">Tex</span><span class="sxs-lookup"><span data-stu-id="0334a-166">Tex</span></span>
    - <span data-ttu-id="0334a-167">Vim Script</span><span class="sxs-lookup"><span data-stu-id="0334a-167">Vim Script</span></span>

> [!NOTE]
> <span data-ttu-id="0334a-168">ソースコードは、テキストの大部分がソースコードであるときに検出するためにトレーニングされています。</span><span class="sxs-lookup"><span data-stu-id="0334a-168">Source Code is trained to detect when the bulk of the text is source code.</span></span> <span data-ttu-id="0334a-169">プレーンテキストが混在しているソースコードテキストは検出されません。</span><span class="sxs-lookup"><span data-stu-id="0334a-169">It does not detect source code text that is interspersed with plain text.</span></span>

- <span data-ttu-id="0334a-170">**嫌がらせ**: 次の特徴に基づいて、1人または複数の個人を対象とした不快感を持つ、不快感を持つテキストアイテムの特定のカテゴリを検出します。競合、ethnicity、宗教、国内原産者、性別、性的なオリエンテーション、年齢、障碍</span><span class="sxs-lookup"><span data-stu-id="0334a-170">**Harassment**: detects a specific category of offensive language text items related to offensive conduct targeting one or multiple individuals based on the following traits: race, ethnicity, religion, national origin, gender, sexual orientation, age, disability</span></span>
- <span data-ttu-id="0334a-171">**不適切な用語**: 多くのユーザーを embarrass する式を含む、不快感を与える言語のテキストアイテムの特定のカテゴリを検出します。</span><span class="sxs-lookup"><span data-stu-id="0334a-171">**Profanity**: detects a specific category of offensive language text items that contain expressions that embarrass most people</span></span>
- <span data-ttu-id="0334a-172">**脅威**: 暴力を確定する脅威、または人またはプロパティに物理的な悪影響や損害を与えることに関連する脅威に関連する、不快な言語のテキストアイテムの特定のカテゴリを検出します。</span><span class="sxs-lookup"><span data-stu-id="0334a-172">**Threat**: detects a specific category of offensive language text items related to threats to commit violence or do physical harm or damage to a person or property</span></span>

<span data-ttu-id="0334a-173">これらは、[**Microsoft 365 コンプライアンス センター**]  >  [**データ分類 (プレビュー)**]  >  [**トレーニング可能な分類子**] ビューに表示され、ステータスは `Ready to use` です。</span><span class="sxs-lookup"><span data-stu-id="0334a-173">These appear in the **Microsoft 365 compliance center** > **Data classification (preview)** > **Trainable classifiers** view with the status of `Ready to use`.</span></span>

![分類子-事前トレーニング-分類子](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> <span data-ttu-id="0334a-175">不快な言葉、ハラスメント、冒涜的表現、および脅威の分類は、検索可能なテキストでのみ機能し、網羅的または完全ではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0334a-175">Please note that the offensive language, harassment, profanity, and threat classifiers only work with searchable text are not exhaustive or complete.</span></span>  <span data-ttu-id="0334a-176">さらに、言語と文化の基準は絶えず変化し、これらの現実に照らして、Microsoft は独自の裁量でこれらの分類子を更新する権利を留保します。</span><span class="sxs-lookup"><span data-stu-id="0334a-176">Further, language and cultural standards continually change, and in light of these realities, Microsoft reserves the right to update these classifiers in its discretion.</span></span> <span data-ttu-id="0334a-177">分類子は、不快な言語やその他の使用言語を監視するのに役立ちますが、分類子は、そのような言語の結果に対処するものではなく、そのような言語の使用を監視または応答する唯一の手段を組織に提供するものではありません。</span><span class="sxs-lookup"><span data-stu-id="0334a-177">While the classifiers may assist your organization in monitoring offensive and other language used, the classifiers do not address consequences of such language and are not intended to provide your organization's sole means of monitoring or responding to the use of such language.</span></span> <span data-ttu-id="0334a-178">事前にトレーニングされた分類子によって識別されたコンテンツの監視、施行、ブロック、削除、および保持に関するすべての決定は、Microsoft またはその子会社ではなく、お客様の組織の責任となります。</span><span class="sxs-lookup"><span data-stu-id="0334a-178">Your organization, and not Microsoft or its subsidiaries, remains responsible for all decisions related to monitoring, enforcement, blocking, removal and retention of any content identified by a pre-trained classifier.</span></span>

### <a name="custom-classifiers"></a><span data-ttu-id="0334a-179">カスタム分類子</span><span class="sxs-lookup"><span data-stu-id="0334a-179">Custom classifiers</span></span>

<span data-ttu-id="0334a-180">事前に訓練された分類子がニーズに合わない場合は、独自の分類子を作成してトレーニングできます。</span><span class="sxs-lookup"><span data-stu-id="0334a-180">When the pre-trained classifiers don't meet your needs, you can create and train your own classifiers.</span></span> <span data-ttu-id="0334a-181">独自に作成するには、はるかに多くの作業が必要になりますが、組織のニーズに合わせてカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="0334a-181">There's significantly more work involved with creating your own, but they'll be much better tailored to your organizations needs.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0334a-182">既定では、カスタムの分類子を作成したユーザーのみが、その分類子によって行われた予測を教育およびレビューすることができます。</span><span class="sxs-lookup"><span data-stu-id="0334a-182">By default, only the user who creates a custom classifier can train and review predictions made by that classifier.</span></span> <span data-ttu-id="0334a-183">他のユーザーが分類子予測をトレーニングおよびレビューできるようにする場合は、「 [他のユーザーにトレーニングとレビューの権限を付与](classifier-get-started-with.md#give-others-train-and-review-rights)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0334a-183">If you want others to be able to train and review classifier predictions, see [Give others train and review rights](classifier-get-started-with.md#give-others-train-and-review-rights).</span></span>

#### <a name="process-flow-for-creating-custom-classifiers"></a><span data-ttu-id="0334a-184">カスタム分類子を作成するためのプロセスフロー</span><span class="sxs-lookup"><span data-stu-id="0334a-184">Process flow for creating custom classifiers</span></span>

<span data-ttu-id="0334a-185">保持ポリシー、コミュニケーション監督など、コンプライアンスソリューションで使用する分類子を作成して発行するには、このフローに従います。</span><span class="sxs-lookup"><span data-stu-id="0334a-185">Creating and publishing a classifier for use in compliance solutions, such as retention policies and communication supervision, follows this flow.</span></span> <span data-ttu-id="0334a-186">カスタム trainable 分類子を作成する方法の詳細については、「 [カスタム分類子を作成](classifier-get-started-with.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0334a-186">For more detail on creating a custom trainable classifier see, [Creating a custom classifier](classifier-get-started-with.md).</span></span>

![プロセスフローカスタム分類子](../media/classifier-trainable-classifier-flow.png)

### <a name="retraining-classifiers"></a><span data-ttu-id="0334a-188">再トレーニング分類子</span><span class="sxs-lookup"><span data-stu-id="0334a-188">Retraining classifiers</span></span>

<span data-ttu-id="0334a-189">ユーザーが実行する分類の精度に関するフィードバックを提供することにより、すべてのカスタム分類子と事前トレーニングされた分類子の精度を向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="0334a-189">You can help improve the accuracy of all custom classifiers and some pre-trained classifiers by providing them with feedback on the accuracy of the classification that they perform.</span></span> <span data-ttu-id="0334a-190">これは再トレーニングと呼ばれ、このワークフローに従います。</span><span class="sxs-lookup"><span data-stu-id="0334a-190">This is called retraining and follow this workflow.</span></span>

![分類子の再トレーニングワークフロー](../media/classifier-retraining-workflow.png)

## <a name="see-also"></a><span data-ttu-id="0334a-192">関連項目</span><span class="sxs-lookup"><span data-stu-id="0334a-192">See also</span></span>

- [<span data-ttu-id="0334a-193">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="0334a-193">Retention labels</span></span>](retention.md)
- [<span data-ttu-id="0334a-194">データ損失防止 (DLP)</span><span class="sxs-lookup"><span data-stu-id="0334a-194">Data loss prevention (DLP)</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="0334a-195">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="0334a-195">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="0334a-196">機密情報の種類のエンティティ定義</span><span class="sxs-lookup"><span data-stu-id="0334a-196">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="0334a-197">ドキュメントのフィンガープリント</span><span class="sxs-lookup"><span data-stu-id="0334a-197">Document finger printing</span></span>](document-fingerprinting.md)
- [<span data-ttu-id="0334a-198">正確なデータ一致</span><span class="sxs-lookup"><span data-stu-id="0334a-198">Exact data match</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
