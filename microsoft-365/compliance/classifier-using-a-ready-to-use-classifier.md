---
title: 保持ラベルを使用した組み込み分類子のテスト (プレビュー)
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
description: Microsoft 365 には、組織全体でコンテンツを識別してラベルを付けるために使用できる組み込みの分類子がいくつか用意されています。 このトピックでは、これらの分類子の使用を準備する方法について説明します。
ms.openlocfilehash: fad35d72c4c40c7b79cba4cb286ccc0f5bb5ab8d
ms.sourcegitcommit: 22e9f54d0d3ead2be91a38d49325308c70f43f90
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "44262548"
---
# <a name="testing-built-in-classifiers-using-retention-labels-preview"></a><span data-ttu-id="ef533-104">保持ラベルを使用した組み込み分類子のテスト (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="ef533-104">Testing built-in classifiers using retention labels (preview)</span></span>

<span data-ttu-id="ef533-105">Microsoft では、特定のカテゴリのコンテンツを特定するのに役立つ5つの分類子をトレーニングおよびテストしています。</span><span class="sxs-lookup"><span data-stu-id="ef533-105">Microsoft has trained and tested five classifiers which can help to identify certain categories of content.</span></span> <span data-ttu-id="ef533-106">これらの分類子は、 `Ready to use` 既定でグループに表示され、非常に大きなサンプルデータセットを使用してトレーニングされています。</span><span class="sxs-lookup"><span data-stu-id="ef533-106">These classifiers show up in the `Ready to use` group by default and were trained using very large sample data sets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ef533-107">分類とラベル付けワークフローに組み込み分類子を使用する前に、組織のコンテンツのサンプルに照らしてテストし、分類の予測が期待どおりに満たされることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef533-107">Before using built-in classifiers in your classification and labeling workflow, you should test it against a sample of your organization's content that you feel fits the category to verify that its classification predictions meet your expectations.</span></span>

<span data-ttu-id="ef533-108">Trainable 分類子の詳細については、「 [trainable 分類子の概要 (プレビュー)](classifier-getting-started-with.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef533-108">For more information on trainable classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="ef533-109">Microsoft 365 には、推奨されている5つの組み込み分類子が付属しています。</span><span class="sxs-lookup"><span data-stu-id="ef533-109">Microsoft 365 comes with five recommended built-in classifiers:</span></span>

> [!CAUTION]
> <span data-ttu-id="ef533-110">誤検知が大量に発生しているため、**不快感**を持つ言語の組み込みの分類子を廃止しています。</span><span class="sxs-lookup"><span data-stu-id="ef533-110">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="ef533-111">使用しないでください。現在使用している場合は、ビジネスプロセスを移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef533-111">Don't use it and if you are currently using it, you should move your business processes off of it.</span></span> <span data-ttu-id="ef533-112">代わりに、**脅威**、**プロファニティ**、および**嫌がらせ**の組み込みの分類子を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ef533-112">We recommend using the **Threat**, **Profanity**, and **Harassment** built-in classifiers instead.</span></span>

- <span data-ttu-id="ef533-113">**履歴書**: 申請者の個人、教育、専門資格、作業経験、その他の個人を特定できる情報のテキストアカウントであるアイテムを検出します。</span><span class="sxs-lookup"><span data-stu-id="ef533-113">**Resumes**: detects items that are textual accounts of an applicant's personal, educational, professional qualifications, work experience, and other personally identifying information.</span></span>
- <span data-ttu-id="ef533-114">**ソースコード**: GitHub で使用されている上位25台のコンピュータプログラミング言語で記述された命令およびステートメントのセットを含むアイテムを検出します。</span><span class="sxs-lookup"><span data-stu-id="ef533-114">**Source Code**: detects items that contain a set of instructions and statements written in the top 25 used computer programming languages on GitHub.</span></span>

|<span data-ttu-id="ef533-115">言語名</span><span class="sxs-lookup"><span data-stu-id="ef533-115">language name</span></span>|||||
|---------|---------|---------|---------|---------|
|<span data-ttu-id="ef533-116">『</span><span class="sxs-lookup"><span data-stu-id="ef533-116">ActionScript</span></span>|<span data-ttu-id="ef533-117">C</span><span class="sxs-lookup"><span data-stu-id="ef533-117">C</span></span>        |<span data-ttu-id="ef533-118">C#</span><span class="sxs-lookup"><span data-stu-id="ef533-118">C#</span></span>       |<span data-ttu-id="ef533-119">+</span><span class="sxs-lookup"><span data-stu-id="ef533-119">C++</span></span>     |<span data-ttu-id="ef533-120">Clojure</span><span class="sxs-lookup"><span data-stu-id="ef533-120">Clojure</span></span>  |
|<span data-ttu-id="ef533-121">CoffeeScript</span><span class="sxs-lookup"><span data-stu-id="ef533-121">CoffeeScript</span></span>|<span data-ttu-id="ef533-122">CSS</span><span class="sxs-lookup"><span data-stu-id="ef533-122">CSS</span></span>     |<span data-ttu-id="ef533-123">移動</span><span class="sxs-lookup"><span data-stu-id="ef533-123">Go</span></span>       |<span data-ttu-id="ef533-124">Haskell</span><span class="sxs-lookup"><span data-stu-id="ef533-124">Haskell</span></span> |<span data-ttu-id="ef533-125">HTML</span><span class="sxs-lookup"><span data-stu-id="ef533-125">HTML</span></span>     |
|<span data-ttu-id="ef533-126">Java</span><span class="sxs-lookup"><span data-stu-id="ef533-126">Java</span></span>     |<span data-ttu-id="ef533-127">JavaScript</span><span class="sxs-lookup"><span data-stu-id="ef533-127">JavaScript</span></span>|<span data-ttu-id="ef533-128">Lua</span><span class="sxs-lookup"><span data-stu-id="ef533-128">Lua</span></span>      |<span data-ttu-id="ef533-129">MATLAB</span><span class="sxs-lookup"><span data-stu-id="ef533-129">MATLAB</span></span>   |<span data-ttu-id="ef533-130">Objective-C</span><span class="sxs-lookup"><span data-stu-id="ef533-130">Objective-C</span></span>|
|<span data-ttu-id="ef533-131">Perl</span><span class="sxs-lookup"><span data-stu-id="ef533-131">Perl</span></span>     |<span data-ttu-id="ef533-132">PHP</span><span class="sxs-lookup"><span data-stu-id="ef533-132">PHP</span></span>      |<span data-ttu-id="ef533-133">Python</span><span class="sxs-lookup"><span data-stu-id="ef533-133">Python</span></span>   |<span data-ttu-id="ef533-134">R</span><span class="sxs-lookup"><span data-stu-id="ef533-134">R</span></span>        |<span data-ttu-id="ef533-135">Ruby</span><span class="sxs-lookup"><span data-stu-id="ef533-135">Ruby</span></span>     |
|<span data-ttu-id="ef533-136">スケール a</span><span class="sxs-lookup"><span data-stu-id="ef533-136">Scala</span></span>    |<span data-ttu-id="ef533-137">Shell</span><span class="sxs-lookup"><span data-stu-id="ef533-137">Shell</span></span>    |<span data-ttu-id="ef533-138">実現</span><span class="sxs-lookup"><span data-stu-id="ef533-138">Swift</span></span>    |<span data-ttu-id="ef533-139">テックス</span><span class="sxs-lookup"><span data-stu-id="ef533-139">Tex</span></span>      |<span data-ttu-id="ef533-140">Vim スクリプト</span><span class="sxs-lookup"><span data-stu-id="ef533-140">Vim Script</span></span>|

- <span data-ttu-id="ef533-141">**嫌がらせ**: 次の特徴に基づいて、1人または複数の個人を対象とした不快感のある言語のテキストアイテムの特定のカテゴリを検出します。競合、ethnicity、宗教、国内原産者、性別、性的なオリエンテーション、年齢、障碍。</span><span class="sxs-lookup"><span data-stu-id="ef533-141">**Harassment**: detects a specific category of offensive language text items related to offensive conduct targeting one or multiple individuals based on the following traits: race, ethnicity, religion, national origin, gender, sexual orientation, age, disability.</span></span>
- <span data-ttu-id="ef533-142">**不適切な用語**: 多くの人々を embarrass する式を含む、不快感を与える言語のテキストアイテムの特定のカテゴリを検出します。</span><span class="sxs-lookup"><span data-stu-id="ef533-142">**Profanity**: detects a specific category of offensive language text items that contain expressions that embarrass most people.</span></span>
- <span data-ttu-id="ef533-143">**脅威**: 暴力をコミットする脅威、または人またはプロパティに物理的な危害または損傷を与える脅威に関連する、不快感を与える言語のテキストアイテムの特定のカテゴリを検出します。</span><span class="sxs-lookup"><span data-stu-id="ef533-143">**Threat**: detects a specific category of offensive language text items related to threats to commit violence or do physical harm or damage to a person or property,</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ef533-144">不快な言葉、嫌がらせ、冒涜、および脅威の分類子は、検索可能なテキストのみで機能することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ef533-144">Please note that the offensive language, harassment, profanity, and threat classifiers only work with searchable text are not exhaustive or complete.</span></span> <span data-ttu-id="ef533-145">さらに、言語と文化的な標準が絶えず変化し、これらの現実からは、これらの分類子を裁量で更新する権利を Microsoft が留保します。</span><span class="sxs-lookup"><span data-stu-id="ef533-145">Further, language and cultural standards continually change, and in light of these realities, Microsoft reserves the right to update these classifiers in its discretion.</span></span> <span data-ttu-id="ef533-146">分類子は、お客様の組織に不快な言葉や使用されている言語の監視を支援することがありますが、分類子はそのような言語の影響を受けません。また、そのような言語の使用を監視したり、それに応答したりすることを意図したものではありません。</span><span class="sxs-lookup"><span data-stu-id="ef533-146">While the classifiers may assist your organization in monitoring offensive and other language used, the classifiers do not address consequences of such language and are not intended to provide your organization's sole means of monitoring or responding to the use of such language.</span></span> <span data-ttu-id="ef533-147">お客様の組織は、Microsoft またはその子会社ではなく、事前に訓練された分類子によって識別されるコンテンツの監視、実施、ブロック、削除、保持に関連するすべての意思決定に対して責任を負うことになります。</span><span class="sxs-lookup"><span data-stu-id="ef533-147">Your organization, and not Microsoft or its subsidiaries, remains responsible for all decisions related to monitoring, enforcement, blocking, removal and retention of any content identified by a pre-trained classifier.</span></span>

## <a name="how-to-verify-that-a-built-in-classifier-will-meet-your-needs"></a><span data-ttu-id="ef533-148">組み込みの分類子がニーズを満たすことを確認する方法</span><span class="sxs-lookup"><span data-stu-id="ef533-148">How to verify that a built-in classifier will meet your needs</span></span>

1. <span data-ttu-id="ef533-149">組み込みの分類子のカテゴリに属していると考えられる (正の一致)、または、テストするカテゴリに含まれるべきではないものを含む、破棄可能なテストコンテンツ項目を収集します。</span><span class="sxs-lookup"><span data-stu-id="ef533-149">Collect disposable test content items that you feel belong in the category of the built-in classifier (positive matches) and ones that shouldn't be included (negative matches) in the category you're testing.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ef533-150">サンプルアイテムは、暗号化する必要がなく、英語でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="ef533-150">The sample items must not be encrypted and they must be in English.</span></span>

2. <span data-ttu-id="ef533-151">専用の SharePoint Online フォルダーを作成します。フォルダーが検索インデックスに追加されるまで、少なくとも1時間待機します。</span><span class="sxs-lookup"><span data-stu-id="ef533-151">Create a dedicated SharePoint Online folder; wait at least an hour for the folder to be added to the search index.</span></span> <span data-ttu-id="ef533-152">フォルダーの URL をメモしておきます。</span><span class="sxs-lookup"><span data-stu-id="ef533-152">Make note of the folder URL.</span></span>

3. <span data-ttu-id="ef533-153">コンプライアンス管理者またはセキュリティ管理者の役割アクセスを使用して microsoft 365 コンプライアンスセンターにサインインし、 **microsoft 365 コンプライアンスセンター**の  >  **レコード管理 (プレビュー)**  >  **ラベルポリシー**タブを開きます。</span><span class="sxs-lookup"><span data-stu-id="ef533-153">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** > **Records management (preview)** > **Label policies** tab.</span></span>

4. <span data-ttu-id="ef533-154">[] を選択 `Auto-apply a label` します。</span><span class="sxs-lookup"><span data-stu-id="ef533-154">Choose `Auto-apply a label`.</span></span>

5. <span data-ttu-id="ef533-155">[] を選択 `Choose a label to auto-apply` します。</span><span class="sxs-lookup"><span data-stu-id="ef533-155">Choose `Choose a label to auto-apply`.</span></span>

6. <span data-ttu-id="ef533-156">`Create new labels`このテストで使用するラベルを選択して作成します。</span><span class="sxs-lookup"><span data-stu-id="ef533-156">Choose `Create new labels` and create a label for use just with this test.</span></span> <span data-ttu-id="ef533-157">その場合は、 `Retention` をに設定 `off` します。</span><span class="sxs-lookup"><span data-stu-id="ef533-157">When you do this, leave `Retention` set to `off`.</span></span> <span data-ttu-id="ef533-158">保持またはその他のアクションをオンにしない。</span><span class="sxs-lookup"><span data-stu-id="ef533-158">You don't want to turn on any retention or other actions.</span></span> <span data-ttu-id="ef533-159">この場合は、アクションを強制しないで、単にテキストラベルとして保持ラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="ef533-159">In this case, you'll be using the retention label simply as a text label, without enforcing any actions.</span></span> <span data-ttu-id="ef533-160">たとえば、アクションなしで「SourceCode クラシファイア test」という名前の保持ラベルを作成し、その保持ラベルを条件としてソースコード分類子のコンテンツに自動適用することができます。</span><span class="sxs-lookup"><span data-stu-id="ef533-160">For example, you can create a retention label named "SourceCode classifier test" with no actions, and then auto-apply that retention label to content that has Source code classifier as a condition.</span></span> <span data-ttu-id="ef533-161">保持ラベルの作成の詳細については、「[保持ラベルの概要](labels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef533-161">To learn more about creating retention labels, see [Overview of retention labels](labels.md).</span></span>
  
7. <span data-ttu-id="ef533-162">[] を選択し `Auto-apply a label` てから、を選び `Choose a label to auto-apply` ます。</span><span class="sxs-lookup"><span data-stu-id="ef533-162">Choose `Auto-apply a label` and then `Choose a label to auto-apply`.</span></span> <span data-ttu-id="ef533-163">条件に基づいてラベルを自動適用する方法の詳細については、「[条件に基づいて保持ラベルポリシーを自動適用](labels.md#applying-a-retention-label-automatically-based-on-conditions)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef533-163">To learn more about using condition based auto-apply a label see, [auto-apply retention label policy based on a condition](labels.md#applying-a-retention-label-automatically-based-on-conditions).</span></span>

8. <span data-ttu-id="ef533-164">リストからテストラベルを選択し、を選択し `Next` ます。</span><span class="sxs-lookup"><span data-stu-id="ef533-164">Choose your test label from the list and choose `Next`.</span></span>

9. <span data-ttu-id="ef533-165">[] を選択 `Apply label to content that matches a trainable classifier` します。</span><span class="sxs-lookup"><span data-stu-id="ef533-165">Choose `Apply label to content that matches a trainable classifier`.</span></span>

![分類子を条件として選択する](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)<span data-ttu-id="ef533-167">.</span><span class="sxs-lookup"><span data-stu-id="ef533-167">.</span></span>

10. <span data-ttu-id="ef533-168">この場合は、リストから分類子を選択します。`Source Code`</span><span class="sxs-lookup"><span data-stu-id="ef533-168">Choose your classifier from the list, in this case `Source Code`</span></span>

11. <span data-ttu-id="ef533-169">ポリシーに名前を指定します。たとえば、"ソースコードの組み込みの分類子テスト" のようにします。</span><span class="sxs-lookup"><span data-stu-id="ef533-169">Name the policy, for example "Source code built-in classifier test".</span></span>

12. <span data-ttu-id="ef533-170">[] を選択 `Let me choose specific locations` します。</span><span class="sxs-lookup"><span data-stu-id="ef533-170">Choose `Let me choose specific locations`.</span></span>

13. <span data-ttu-id="ef533-171">を除くすべての場所をオフにし `SharePoint sites` `Choose sites` ます。</span><span class="sxs-lookup"><span data-stu-id="ef533-171">Turn off all locations except `SharePoint sites` and choose `Choose sites`.</span></span>

14. <span data-ttu-id="ef533-172">手順2でサイトの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="ef533-172">Enter the URL for the site from step 2.</span></span>

15. <span data-ttu-id="ef533-173">ウィザードを終了し、`Auto-apply`</span><span class="sxs-lookup"><span data-stu-id="ef533-173">Finish the wizard and choose `Auto-apply`</span></span>

16. <span data-ttu-id="ef533-174">テストアイテムを専用の SharePoint Online フォルダーに配置します。</span><span class="sxs-lookup"><span data-stu-id="ef533-174">Place the test items into the dedicated SharePoint Online folder.</span></span>

17. <span data-ttu-id="ef533-175">ラベルが適用される時間を有効にします。</span><span class="sxs-lookup"><span data-stu-id="ef533-175">Allow an hour for the label to be applied.</span></span>

18. <span data-ttu-id="ef533-176">ラベルのドキュメントのプロパティをチェックして、分類子が予期したとおりにテストコンテンツを含むかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="ef533-176">Check the properties of the documents for the label to see if the classifier included and excluded the test content as you expected.</span></span>

19. <span data-ttu-id="ef533-177">ラベル付けされたアイテムを確認します。</span><span class="sxs-lookup"><span data-stu-id="ef533-177">Review the items that were labeled.</span></span>

20. <span data-ttu-id="ef533-178">テストを完了したら、コンテンツとラベルポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="ef533-178">Delete the content and the label policy if you're done with your testing.</span></span>

<span data-ttu-id="ef533-179">関連項目:</span><span class="sxs-lookup"><span data-stu-id="ef533-179">See also:</span></span>

- [<span data-ttu-id="ef533-180">トレーニング可能な分類子の使用を開始する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="ef533-180">Getting started with trainable classifiers (preview)</span></span>](classifier-getting-started-with.md)
- <span data-ttu-id="ef533-181">「[保持ラベルの概要](labels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef533-181">[Overview of retention labels](labels.md)</span></span>
- [<span data-ttu-id="ef533-182">条件に基づいて保持ラベルポリシーを自動適用する</span><span class="sxs-lookup"><span data-stu-id="ef533-182">Auto-apply retention label policy based on a condition</span></span>](labels.md#applying-a-retention-label-automatically-based-on-conditions)
