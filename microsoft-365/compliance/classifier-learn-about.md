---
title: トレーニング可能な分類子について
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
ms.openlocfilehash: 0e5f712b76af2fba3d456997a47352773d92d766
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2021
ms.locfileid: "49759901"
---
# <a name="learn-about-trainable-classifiers"></a><span data-ttu-id="a4029-105">トレーニング可能な分類子について</span><span class="sxs-lookup"><span data-stu-id="a4029-105">Learn about trainable classifiers</span></span>

<span data-ttu-id="a4029-106">コンテンツを適切に保護および処理できるようにコンテンツを分類およびラベル付けすることは、情報保護に対するトレーニングの出発点です。</span><span class="sxs-lookup"><span data-stu-id="a4029-106">Classifying and labeling content so it can be protected and handled properly is the starting place for the information protection discipline.</span></span> <span data-ttu-id="a4029-107">Microsoft 365 には、コンテンツを分類する 3 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="a4029-107">Microsoft 365 has three ways to classify content.</span></span>

## <a name="manually"></a><span data-ttu-id="a4029-108">手動</span><span class="sxs-lookup"><span data-stu-id="a4029-108">Manually</span></span>

<span data-ttu-id="a4029-109">この方法では、人間の判断と行動が必要です。</span><span class="sxs-lookup"><span data-stu-id="a4029-109">This method requires human judgment and action.</span></span> <span data-ttu-id="a4029-110">管理者は、既存のラベルと機密情報の種類を使用するか、独自のラベルを作成して公開することができます。</span><span class="sxs-lookup"><span data-stu-id="a4029-110">An admin may either use the pre-existing labels and sensitive information types or create their own and then publish them.</span></span> <span data-ttu-id="a4029-111">ユーザーと管理者は、遭遇したコンテンツをそれらに適用します。</span><span class="sxs-lookup"><span data-stu-id="a4029-111">Users and admins apply them to content as they encounter it.</span></span> <span data-ttu-id="a4029-112">その後、コンテンツを保護し、その処分を管理できます。</span><span class="sxs-lookup"><span data-stu-id="a4029-112">You can then protect the content and manage its disposition.</span></span>

## <a name="automated-pattern-matching"></a><span data-ttu-id="a4029-113">自動パターン マッチング</span><span class="sxs-lookup"><span data-stu-id="a4029-113">Automated pattern matching</span></span>

<span data-ttu-id="a4029-114">このカテゴリの分類メカニズムには、次の方法でコンテンツを検索する方法が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a4029-114">This category of classification mechanisms include finding content by:</span></span>

- <span data-ttu-id="a4029-115">キーワードまたはメタデータ値 (キーワード クエリ言語)。</span><span class="sxs-lookup"><span data-stu-id="a4029-115">Keywords or metadata values (keyword query language).</span></span>
- <span data-ttu-id="a4029-116">社会保障、クレジット カード番号、銀行口座番号 (機密情報の種類のエンティティ定義) など、以前に識別された機密情報のパターン [を使用する](sensitive-information-type-entity-definitions.md)。</span><span class="sxs-lookup"><span data-stu-id="a4029-116">Using previously identified patterns of sensitive information like social security, credit card or bank account numbers [(Sensitive information type entity definitions)](sensitive-information-type-entity-definitions.md).</span></span>
- <span data-ttu-id="a4029-117">テンプレート上のバリエーション (ドキュメントの指の印刷) のため、アイテム [を認識します](document-fingerprinting.md)。</span><span class="sxs-lookup"><span data-stu-id="a4029-117">Recognizing an item because it's a variation on a template [(document finger printing)](document-fingerprinting.md).</span></span>
- <span data-ttu-id="a4029-118">正確な文字列 (完全なデータ一 [致) の存在を使用します](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)。</span><span class="sxs-lookup"><span data-stu-id="a4029-118">Using the presence of exact strings [(exact data match)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

<span data-ttu-id="a4029-119">その後、データ損失防止 [(DLP)](data-loss-prevention-policies.md) および保持ラベルの自動適用ポリシーでコンテンツを使用できるよう、そのラベルを自動的に適用 [できます](apply-retention-labels-automatically.md)。</span><span class="sxs-lookup"><span data-stu-id="a4029-119">Sensitivity and retention labels can then be automatically applied to make the content available for use in [data loss prevention (DLP)](data-loss-prevention-policies.md) and [auto-apply polices for retention labels](apply-retention-labels-automatically.md).</span></span>

## <a name="classifiers"></a><span data-ttu-id="a4029-120">分類子</span><span class="sxs-lookup"><span data-stu-id="a4029-120">Classifiers</span></span>

<span data-ttu-id="a4029-121">この分類方法は、手動または自動のパターン マッチング方法では簡単に識別できないコンテンツに特に適しています。</span><span class="sxs-lookup"><span data-stu-id="a4029-121">This classification method is particularly well suited to content that isn't easily identified by either the manual or automated pattern matching methods.</span></span> <span data-ttu-id="a4029-122">この分類方法は、アイテムに含まれる要素ではなく、アイテムが何であるかに基づいてアイテムを識別するように分類子をトレーニングすることです (パターン マッチング)。</span><span class="sxs-lookup"><span data-stu-id="a4029-122">This method of classification is more about training a classifier to identify an item based on what the item is, not by elements that are in the item (pattern matching).</span></span> <span data-ttu-id="a4029-123">分類子は、分類したいコンテンツの数百の例を見て、コンテンツのタイプを識別する方法を学びます。</span><span class="sxs-lookup"><span data-stu-id="a4029-123">A classifier learns how to identify a type of content by looking at hundreds of examples of the content you're interested in classifying.</span></span> <span data-ttu-id="a4029-124">それを間違いなくカテゴリーにある例に与えることから始めます。</span><span class="sxs-lookup"><span data-stu-id="a4029-124">You start by feeding it examples that are definitely in the category.</span></span> <span data-ttu-id="a4029-125">それらを処理したら、一致する例と一致しない例の両方を組み合わせてテストします。</span><span class="sxs-lookup"><span data-stu-id="a4029-125">Once it processes those, you test it by giving it a mix of both matching and non-matching examples.</span></span> <span data-ttu-id="a4029-126">次に、分類子は、特定のアイテムが作成中のカテゴリに該当するかどうかを予測します。</span><span class="sxs-lookup"><span data-stu-id="a4029-126">The classifier then makes predictions as to whether any given item falls into the category you're building.</span></span> <span data-ttu-id="a4029-127">その結果を確認し、真陽性、真陰性、誤検知、検出を並べ替えて予測精度を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="a4029-127">You then confirm its results, sorting out the true positives, true negatives, false positives, and false negatives to help increase the accuracy of its predictions.</span></span> 

<span data-ttu-id="a4029-128">分類子を発行すると、SharePoint Online、Exchange、OneDrive のような場所にあるアイテムを並べ替え、コンテンツが分類されます。</span><span class="sxs-lookup"><span data-stu-id="a4029-128">When you publish the classifier, it sorts through items in locations like SharePoint Online, Exchange, and OneDrive, and classifies the content.</span></span> <span data-ttu-id="a4029-129">分類子を発行した後は、最初のトレーニング プロセスと同様のフィードバック プロセスを使用して、分類子を引き続きトレーニングできます。</span><span class="sxs-lookup"><span data-stu-id="a4029-129">After you publish the classifier, you can continue to train it using a feedback process that is similar to the initial training process.</span></span>

### <a name="where-you-can-use-trainable-classifiers"></a><span data-ttu-id="a4029-130">トレーニング可能な分類子を使用できる場所</span><span class="sxs-lookup"><span data-stu-id="a4029-130">Where you can use trainable classifiers</span></span>
<span data-ttu-id="a4029-131">組み込みの分類子とトレーニング可能な分類子の両方が、Office の機度[](apply-sensitivity-label-automatically.md)ラベルによる自動ラベル付けの条件として利用できます。[](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels)条件と通信コンプライアンスに基づいて保持ラベル ポリシーを自動適用[します。](communication-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="a4029-131">Both built-in classifiers and trainable classifiers are available as a condition for [Office autolabeling with sensitivity labels](apply-sensitivity-label-automatically.md), [auto-apply retention label policy based on a condition](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) and in [communication compliance](communication-compliance.md).</span></span> 

<span data-ttu-id="a4029-132">機度ラベルでは、条件として分類子を使用できます。「コンテンツに機ティフィティ ラベルを自動的に適用 [する」を参照してください](apply-sensitivity-label-automatically.md)。</span><span class="sxs-lookup"><span data-stu-id="a4029-132">Sensitivity labels can use classifiers as conditions, see [Apply a sensitivity label to content automatically](apply-sensitivity-label-automatically.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4029-133">分類子は、暗号化されていない、英語のアイテムでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="a4029-133">Classifiers only work with items that are not encrypted and are in English.</span></span>

## <a name="types-of-classifiers"></a><span data-ttu-id="a4029-134">分類子のタイプ</span><span class="sxs-lookup"><span data-stu-id="a4029-134">Types of classifiers</span></span>

- <span data-ttu-id="a4029-135">**事前トレーニング済みの** 分類子 - Microsoft は、トレーニングなしで使用を開始できる多くの分類子を作成および事前トレーニングしています。</span><span class="sxs-lookup"><span data-stu-id="a4029-135">**pre-trained classifiers** - Microsoft has created and pre-trained a number of classifiers that you can start using without training them.</span></span> <span data-ttu-id="a4029-136">これらの分類子は、状態と一緒に表示されます `Ready to use` 。</span><span class="sxs-lookup"><span data-stu-id="a4029-136">These classifiers will appear with the status of `Ready to use`.</span></span>
- <span data-ttu-id="a4029-137">**カスタム分類子** - 事前トレーニング済みの分類子の範囲を超える分類ニーズがある場合は、独自の分類子を作成してトレーニングできます。</span><span class="sxs-lookup"><span data-stu-id="a4029-137">**custom classifiers** - If you have classification needs that extend beyond what the pre-trained classifiers cover, you can create and train your own classifiers.</span></span>

### <a name="pre-trained-classifiers"></a><span data-ttu-id="a4029-138">トレーニング済みの分類子</span><span class="sxs-lookup"><span data-stu-id="a4029-138">Pre-trained classifiers</span></span>

<span data-ttu-id="a4029-139">Microsoft 365 には、5 つの事前トレーニング済みの分類子が付属しています。</span><span class="sxs-lookup"><span data-stu-id="a4029-139">Microsoft 365 comes with five pre-trained classifiers:</span></span>

> [!CAUTION]
> <span data-ttu-id="a4029-140">不快言語の事前 **トレーニング済** み分類子は、誤検知の数が多く生成され始めているため、廃止されます。</span><span class="sxs-lookup"><span data-stu-id="a4029-140">We are deprecating the **Offensive Language** pre-trained classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="a4029-141">使用しないでください。現在使用している場合は、ビジネス プロセスを移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4029-141">Don't use it and if you are currently using it, you should move your business processes off of it.</span></span> <span data-ttu-id="a4029-142">代わりに **、脅威、** 不適切行為、**および** ハラスメントの事前トレーニング済みの分類子を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a4029-142">We recommend using the **Threat**, **Profanity**, and **Harassment** pre-trained classifiers instead.</span></span>

- <span data-ttu-id="a4029-143">**履歴** 書 : 指定された個人、教育、専門的資格、作業経験、その他の個人を特定する情報のテキスト アカウントであるアイテムを検出します。</span><span class="sxs-lookup"><span data-stu-id="a4029-143">**Resumes**: detects items that are textual accounts of an applicant's personal, educational, professional qualifications, work experience, and other personally identifying information</span></span>
- <span data-ttu-id="a4029-144">**ソース コード**: GitHub の上位 25 の使用コンピューター プログラミング言語で記述された一連の命令とステートメントを含むアイテムを検出します</span><span class="sxs-lookup"><span data-stu-id="a4029-144">**Source Code**: detects items that contain a set of instructions and statements written in the top 25 used computer programming languages on GitHub</span></span>
    - <span data-ttu-id="a4029-145">ActionScript</span><span class="sxs-lookup"><span data-stu-id="a4029-145">ActionScript</span></span>
    - <span data-ttu-id="a4029-146">C</span><span class="sxs-lookup"><span data-stu-id="a4029-146">C</span></span>
    - <span data-ttu-id="a4029-147">C#</span><span class="sxs-lookup"><span data-stu-id="a4029-147">C#</span></span>
    - <span data-ttu-id="a4029-148">C++</span><span class="sxs-lookup"><span data-stu-id="a4029-148">C++</span></span>
    - <span data-ttu-id="a4029-149">Clojure</span><span class="sxs-lookup"><span data-stu-id="a4029-149">Clojure</span></span>
    - <span data-ttu-id="a4029-150">CoffeeScript</span><span class="sxs-lookup"><span data-stu-id="a4029-150">CoffeeScript</span></span>
    - <span data-ttu-id="a4029-151">Go</span><span class="sxs-lookup"><span data-stu-id="a4029-151">Go</span></span>
    - <span data-ttu-id="a4029-152">Haskell</span><span class="sxs-lookup"><span data-stu-id="a4029-152">Haskell</span></span>
    - <span data-ttu-id="a4029-153">Java</span><span class="sxs-lookup"><span data-stu-id="a4029-153">Java</span></span>
    - <span data-ttu-id="a4029-154">JavaScript</span><span class="sxs-lookup"><span data-stu-id="a4029-154">JavaScript</span></span>
    - <span data-ttu-id="a4029-155">Lua</span><span class="sxs-lookup"><span data-stu-id="a4029-155">Lua</span></span>
    - <span data-ttu-id="a4029-156">MATLAB</span><span class="sxs-lookup"><span data-stu-id="a4029-156">MATLAB</span></span>
    - <span data-ttu-id="a4029-157">Objective-C</span><span class="sxs-lookup"><span data-stu-id="a4029-157">Objective-C</span></span>
    - <span data-ttu-id="a4029-158">Perl</span><span class="sxs-lookup"><span data-stu-id="a4029-158">Perl</span></span>
    - <span data-ttu-id="a4029-159">PHP</span><span class="sxs-lookup"><span data-stu-id="a4029-159">PHP</span></span>
    - <span data-ttu-id="a4029-160">Python</span><span class="sxs-lookup"><span data-stu-id="a4029-160">Python</span></span>
    - <span data-ttu-id="a4029-161">R</span><span class="sxs-lookup"><span data-stu-id="a4029-161">R</span></span>
    - <span data-ttu-id="a4029-162">Ruby</span><span class="sxs-lookup"><span data-stu-id="a4029-162">Ruby</span></span>
    - <span data-ttu-id="a4029-163">Scala</span><span class="sxs-lookup"><span data-stu-id="a4029-163">Scala</span></span>
    - <span data-ttu-id="a4029-164">Shell</span><span class="sxs-lookup"><span data-stu-id="a4029-164">Shell</span></span>
    - <span data-ttu-id="a4029-165">Swift</span><span class="sxs-lookup"><span data-stu-id="a4029-165">Swift</span></span>
    - <span data-ttu-id="a4029-166">Tex</span><span class="sxs-lookup"><span data-stu-id="a4029-166">Tex</span></span>
    - <span data-ttu-id="a4029-167">Vim Script</span><span class="sxs-lookup"><span data-stu-id="a4029-167">Vim Script</span></span>

> [!NOTE]
> <span data-ttu-id="a4029-168">ソース コードは、テキストの大部分がソース コードである場合を検出するトレーニングを受けています。</span><span class="sxs-lookup"><span data-stu-id="a4029-168">Source Code is trained to detect when the bulk of the text is source code.</span></span> <span data-ttu-id="a4029-169">プレーン テキストと一緒に挿入されているソース コード テキストは検出されません。</span><span class="sxs-lookup"><span data-stu-id="a4029-169">It does not detect source code text that is interspersed with plain text.</span></span>

- <span data-ttu-id="a4029-170">**ハラ** スメント: 次の特徴に基づいて、1 人または複数の個人を対象とする攻撃的行為に関連する特定のカテゴリの不快言語テキスト アイテムを検出します。特徴は次のとおりです。レース、民族性、民族、国民の原点、性別、性的指向、年齢、障がい</span><span class="sxs-lookup"><span data-stu-id="a4029-170">**Harassment**: detects a specific category of offensive language text items related to offensive conduct targeting one or multiple individuals based on the following traits: race, ethnicity, religion, national origin, gender, sexual orientation, age, disability</span></span>
- <span data-ttu-id="a4029-171">**不適切表現**: ほとんどのユーザーを困惑する表現を含む、不快な言語のテキスト アイテムの特定のカテゴリを検出します</span><span class="sxs-lookup"><span data-stu-id="a4029-171">**Profanity**: detects a specific category of offensive language text items that contain expressions that embarrass most people</span></span>
- <span data-ttu-id="a4029-172">**脅威**: 暴力を加え、人やプロパティに物理的な危害や損害を与える脅威に関連する、攻撃的な言語のテキスト アイテムの特定のカテゴリを検出します</span><span class="sxs-lookup"><span data-stu-id="a4029-172">**Threat**: detects a specific category of offensive language text items related to threats to commit violence or do physical harm or damage to a person or property</span></span>

<span data-ttu-id="a4029-173">これらは **、Microsoft 365** コンプライアンス センターのデータ分類のトレーニング可能な分類子ビューに表示され、  >    >  状態は次のように表示されます `Ready to use` 。</span><span class="sxs-lookup"><span data-stu-id="a4029-173">These appear in the **Microsoft 365 compliance center** > **Data classification** > **Trainable classifiers** view with the status of `Ready to use`.</span></span>

![分類子-pre-trained-classifiers](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> <span data-ttu-id="a4029-175">不快な言葉、ハラスメント、冒涜的表現、および脅威の分類は、検索可能なテキストでのみ機能し、網羅的または完全ではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a4029-175">Please note that the offensive language, harassment, profanity, and threat classifiers only work with searchable text are not exhaustive or complete.</span></span>  <span data-ttu-id="a4029-176">さらに、言語と文化の基準は絶えず変化し、これらの現実に照らして、Microsoft は独自の裁量でこれらの分類子を更新する権利を留保します。</span><span class="sxs-lookup"><span data-stu-id="a4029-176">Further, language and cultural standards continually change, and in light of these realities, Microsoft reserves the right to update these classifiers in its discretion.</span></span> <span data-ttu-id="a4029-177">分類子は、不快な言語やその他の使用言語を監視するのに役立ちますが、分類子は、そのような言語の結果に対処するものではなく、そのような言語の使用を監視または応答する唯一の手段を組織に提供するものではありません。</span><span class="sxs-lookup"><span data-stu-id="a4029-177">While the classifiers may assist your organization in monitoring offensive and other language used, the classifiers do not address consequences of such language and are not intended to provide your organization's sole means of monitoring or responding to the use of such language.</span></span> <span data-ttu-id="a4029-178">事前にトレーニングされた分類子によって識別されたコンテンツの監視、施行、ブロック、削除、および保持に関するすべての決定は、Microsoft またはその子会社ではなく、お客様の組織の責任となります。</span><span class="sxs-lookup"><span data-stu-id="a4029-178">Your organization, and not Microsoft or its subsidiaries, remains responsible for all decisions related to monitoring, enforcement, blocking, removal and retention of any content identified by a pre-trained classifier.</span></span>

### <a name="custom-classifiers"></a><span data-ttu-id="a4029-179">カスタム分類子</span><span class="sxs-lookup"><span data-stu-id="a4029-179">Custom classifiers</span></span>

<span data-ttu-id="a4029-180">事前トレーニング済みの分類子がニーズを満たしない場合は、独自の分類子を作成してトレーニングできます。</span><span class="sxs-lookup"><span data-stu-id="a4029-180">When the pre-trained classifiers don't meet your needs, you can create and train your own classifiers.</span></span> <span data-ttu-id="a4029-181">独自に作成するには、はるかに多くの作業が必要になりますが、組織のニーズに合わせてカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="a4029-181">There's significantly more work involved with creating your own, but they'll be much better tailored to your organizations needs.</span></span> 

<span data-ttu-id="a4029-182">たとえば、次のトレーニング可能な分類子を作成できます。</span><span class="sxs-lookup"><span data-stu-id="a4029-182">For example you could create trainable classifiers for:</span></span>
 
- <span data-ttu-id="a4029-183">法的文書 - 弁護士依頼人特権、終了セット、作業明細書など</span><span class="sxs-lookup"><span data-stu-id="a4029-183">Legal documents - such as attorney client privilege, closing sets, statement of work</span></span>
- <span data-ttu-id="a4029-184">戦略的ビジネス ドキュメント - プレス リリース、合併と買収、取引、ビジネスまたはマーケティング計画、知的財産、特許、デザイン ドキュメントなど</span><span class="sxs-lookup"><span data-stu-id="a4029-184">Strategic business documents - like press releases, merger and acquisition, deals, business or marketing plans, intellectual property, patents, design docs</span></span>
- <span data-ttu-id="a4029-185">価格情報 - 請求書、価格見積もり、作業命令、文書の編集など</span><span class="sxs-lookup"><span data-stu-id="a4029-185">Pricing information - like invoices, price quotes, work orders, bidding documents</span></span> 
- <span data-ttu-id="a4029-186">財務情報 - 組織への投資、四半期または年間の結果など</span><span class="sxs-lookup"><span data-stu-id="a4029-186">Financial information - such as organizational investments, quarterly or annual results</span></span>    

#### <a name="process-flow-for-creating-custom-classifiers"></a><span data-ttu-id="a4029-187">カスタム分類子を作成するためのプロセス フロー</span><span class="sxs-lookup"><span data-stu-id="a4029-187">Process flow for creating custom classifiers</span></span>

<span data-ttu-id="a4029-188">アイテム保持ポリシーや通信監督などのコンプライアンス ソリューションで使用する分類子の作成と発行は、このフローに従います。</span><span class="sxs-lookup"><span data-stu-id="a4029-188">Creating and publishing a classifier for use in compliance solutions, such as retention policies and communication supervision, follows this flow.</span></span> <span data-ttu-id="a4029-189">カスタムのトレーニング可能な分類子の作成の詳細については、「カスタム分類子の [作成」を参照してください](classifier-get-started-with.md)。</span><span class="sxs-lookup"><span data-stu-id="a4029-189">For more detail on creating a custom trainable classifier see, [Creating a custom classifier](classifier-get-started-with.md).</span></span>

![プロセス フローカスタム分類子](../media/classifier-trainable-classifier-flow.png)

### <a name="retraining-classifiers"></a><span data-ttu-id="a4029-191">分類子の再トレーニング</span><span class="sxs-lookup"><span data-stu-id="a4029-191">Retraining classifiers</span></span>

<span data-ttu-id="a4029-192">すべてのカスタム分類子と事前トレーニング済みの分類子の精度を向上させるために、実行する分類の精度に関するフィードバックを提供できます。</span><span class="sxs-lookup"><span data-stu-id="a4029-192">You can help improve the accuracy of all custom classifiers and some pre-trained classifiers by providing them with feedback on the accuracy of the classification that they perform.</span></span> <span data-ttu-id="a4029-193">これを再トレーニングと呼び、このワークフローに従います。</span><span class="sxs-lookup"><span data-stu-id="a4029-193">This is called retraining and follow this workflow.</span></span>

![分類子再トレーニング ワークフロー](../media/classifier-retraining-workflow.png)

## <a name="see-also"></a><span data-ttu-id="a4029-195">関連項目</span><span class="sxs-lookup"><span data-stu-id="a4029-195">See also</span></span>

- [<span data-ttu-id="a4029-196">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="a4029-196">Retention labels</span></span>](retention.md)
- [<span data-ttu-id="a4029-197">データ損失防止 (DLP)</span><span class="sxs-lookup"><span data-stu-id="a4029-197">Data loss prevention (DLP)</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="a4029-198">秘密度ラベル</span><span class="sxs-lookup"><span data-stu-id="a4029-198">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="a4029-199">機密情報の種類のエンティティ定義</span><span class="sxs-lookup"><span data-stu-id="a4029-199">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="a4029-200">ドキュメントの指の印刷</span><span class="sxs-lookup"><span data-stu-id="a4029-200">Document finger printing</span></span>](document-fingerprinting.md)
- [<span data-ttu-id="a4029-201">完全なデータ一致</span><span class="sxs-lookup"><span data-stu-id="a4029-201">Exact data match</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
