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
ms.openlocfilehash: 2652df8d79b06d6614e2478843195e67de0a8ebb
ms.sourcegitcommit: 87eff6e8a08cec3cb0464a3b765434717584a4a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/26/2020
ms.locfileid: "44371409"
---
# <a name="testing-built-in-classifiers-using-retention-labels-preview"></a><span data-ttu-id="f4674-104">保持ラベルを使用した組み込み分類子のテスト (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="f4674-104">Testing built-in classifiers using retention labels (preview)</span></span>

<span data-ttu-id="f4674-105">Microsoft では、特定のカテゴリのコンテンツを特定するのに役立つ5つの分類子をトレーニングおよびテストしています。</span><span class="sxs-lookup"><span data-stu-id="f4674-105">Microsoft has trained and tested five classifiers which can help to identify certain categories of content.</span></span> <span data-ttu-id="f4674-106">これらの分類子は、 `Ready to use` 既定でグループに表示され、非常に大きなサンプルデータセットを使用してトレーニングされています。</span><span class="sxs-lookup"><span data-stu-id="f4674-106">These classifiers show up in the `Ready to use` group by default and were trained using very large sample data sets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f4674-107">分類とラベル付けワークフローに組み込み分類子を使用する前に、組織のコンテンツのサンプルに照らしてテストし、分類の予測が期待どおりに満たされることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4674-107">Before using built-in classifiers in your classification and labeling workflow, you should test it against a sample of your organization's content that you feel fits the category to verify that its classification predictions meet your expectations.</span></span>

<span data-ttu-id="f4674-108">Trainable 分類子の詳細については、「 [trainable 分類子の概要 (プレビュー)](classifier-getting-started-with.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4674-108">For more information on trainable classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="f4674-109">Microsoft 365 には、推奨される 5 つの組み込み分類子が付属しています。</span><span class="sxs-lookup"><span data-stu-id="f4674-109">Microsoft 365 comes with five recommended built-in classifiers:</span></span>

> [!CAUTION]
> <span data-ttu-id="f4674-110">組み込みの [**不快な言葉**] は、誤検知の数が多いため、廃止予定です。</span><span class="sxs-lookup"><span data-stu-id="f4674-110">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="f4674-111">使用しないでください。現在使用している場合は、ビジネス プロセスを移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4674-111">Don't use it and if you are currently using it, you should move your business processes off of it.</span></span> <span data-ttu-id="f4674-112">代わりに、[**脅威**]、[**冒涜的表現**]、および [**ハラスメント**] の組み込み分類子を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f4674-112">We recommend using the **Threat**, **Profanity**, and **Harassment** built-in classifiers instead.</span></span>

- <span data-ttu-id="f4674-113">**履歴書**: 申請者の個人、教育、専門資格、作業経験、その他個人を識別する情報のテキストアカウントであるアイテムを検出します。</span><span class="sxs-lookup"><span data-stu-id="f4674-113">**Resumes**: detects items that are textual accounts of an applicant's personal, educational, professional qualifications, work experience, and other personally identifying information</span></span>
- <span data-ttu-id="f4674-114">**ソースコード**: GitHub で使用されている上位25台のコンピュータプログラミング言語で記述された命令およびステートメントのセットを含むアイテムを検出します。</span><span class="sxs-lookup"><span data-stu-id="f4674-114">**Source Code**: detects items that contain a set of instructions and statements written in the top 25 used computer programming languages on GitHub</span></span>

  |<span data-ttu-id="f4674-115">言語名</span><span class="sxs-lookup"><span data-stu-id="f4674-115">language name</span></span>|||||
  |---------|---------|---------|---------|---------|
  |<span data-ttu-id="f4674-116">ActionScript</span><span class="sxs-lookup"><span data-stu-id="f4674-116">ActionScript</span></span>|<span data-ttu-id="f4674-117">C</span><span class="sxs-lookup"><span data-stu-id="f4674-117">C</span></span>        |<span data-ttu-id="f4674-118">C#</span><span class="sxs-lookup"><span data-stu-id="f4674-118">C#</span></span>       |<span data-ttu-id="f4674-119">C++</span><span class="sxs-lookup"><span data-stu-id="f4674-119">C++</span></span>     |<span data-ttu-id="f4674-120">Clojure</span><span class="sxs-lookup"><span data-stu-id="f4674-120">Clojure</span></span>  |
  |<span data-ttu-id="f4674-121">CoffeeScript</span><span class="sxs-lookup"><span data-stu-id="f4674-121">CoffeeScript</span></span>|<span data-ttu-id="f4674-122">CSS</span><span class="sxs-lookup"><span data-stu-id="f4674-122">CSS</span></span>     |<span data-ttu-id="f4674-123">Go</span><span class="sxs-lookup"><span data-stu-id="f4674-123">Go</span></span>       |<span data-ttu-id="f4674-124">Haskell</span><span class="sxs-lookup"><span data-stu-id="f4674-124">Haskell</span></span> |<span data-ttu-id="f4674-125">HTML</span><span class="sxs-lookup"><span data-stu-id="f4674-125">HTML</span></span>     |
  |<span data-ttu-id="f4674-126">Java</span><span class="sxs-lookup"><span data-stu-id="f4674-126">Java</span></span>     |<span data-ttu-id="f4674-127">JavaScript</span><span class="sxs-lookup"><span data-stu-id="f4674-127">JavaScript</span></span>|<span data-ttu-id="f4674-128">Lua</span><span class="sxs-lookup"><span data-stu-id="f4674-128">Lua</span></span>      |<span data-ttu-id="f4674-129">MATLAB</span><span class="sxs-lookup"><span data-stu-id="f4674-129">MATLAB</span></span>   |<span data-ttu-id="f4674-130">Objective-C</span><span class="sxs-lookup"><span data-stu-id="f4674-130">Objective-C</span></span>|
  |<span data-ttu-id="f4674-131">Perl</span><span class="sxs-lookup"><span data-stu-id="f4674-131">Perl</span></span>     |<span data-ttu-id="f4674-132">PHP</span><span class="sxs-lookup"><span data-stu-id="f4674-132">PHP</span></span>      |<span data-ttu-id="f4674-133">Python</span><span class="sxs-lookup"><span data-stu-id="f4674-133">Python</span></span>   |<span data-ttu-id="f4674-134">R</span><span class="sxs-lookup"><span data-stu-id="f4674-134">R</span></span>        |<span data-ttu-id="f4674-135">Ruby</span><span class="sxs-lookup"><span data-stu-id="f4674-135">Ruby</span></span>     |
  |<span data-ttu-id="f4674-136">Scala</span><span class="sxs-lookup"><span data-stu-id="f4674-136">Scala</span></span>    |<span data-ttu-id="f4674-137">Shell</span><span class="sxs-lookup"><span data-stu-id="f4674-137">Shell</span></span>    |<span data-ttu-id="f4674-138">Swift</span><span class="sxs-lookup"><span data-stu-id="f4674-138">Swift</span></span>    |<span data-ttu-id="f4674-139">Tex</span><span class="sxs-lookup"><span data-stu-id="f4674-139">Tex</span></span>      |<span data-ttu-id="f4674-140">Vim Script</span><span class="sxs-lookup"><span data-stu-id="f4674-140">Vim Script</span></span>|

> [!NOTE]
> <span data-ttu-id="f4674-141">ソースコードは、テキストの大部分がソースコードであるときに検出するためにトレーニングされています。</span><span class="sxs-lookup"><span data-stu-id="f4674-141">Source Code is trained to detect when the bulk of the text is source code.</span></span> <span data-ttu-id="f4674-142">プレーンテキストが混在しているソースコードテキストは検出されません。</span><span class="sxs-lookup"><span data-stu-id="f4674-142">It does not detect source code text that is interspersed with plain text.</span></span>

- <span data-ttu-id="f4674-143">**嫌がらせ**: 次の特徴に基づいて、1人または複数の個人を対象とした不快感を持つ、不快感を持つテキストアイテムの特定のカテゴリを検出します。競合、ethnicity、宗教、国内原産者、性別、性的なオリエンテーション、年齢、障碍</span><span class="sxs-lookup"><span data-stu-id="f4674-143">**Harassment**: detects a specific category of offensive language text items related to offensive conduct targeting one or multiple individuals based on the following traits: race, ethnicity, religion, national origin, gender, sexual orientation, age, disability</span></span>
- <span data-ttu-id="f4674-144">**不適切な用語**: 多くのユーザーを embarrass する式を含む、不快感を与える言語のテキストアイテムの特定のカテゴリを検出します。</span><span class="sxs-lookup"><span data-stu-id="f4674-144">**Profanity**: detects a specific category of offensive language text items that contain expressions that embarrass most people</span></span>
- <span data-ttu-id="f4674-145">**脅威**: 暴力を確定する脅威、または人またはプロパティに物理的な悪影響や損害を与えることに関連する脅威に関連する、不快な言語のテキストアイテムの特定のカテゴリを検出します。</span><span class="sxs-lookup"><span data-stu-id="f4674-145">**Threat**: detects a specific category of offensive language text items related to threats to commit violence or do physical harm or damage to a person or property</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f4674-146">不快な言葉、ハラスメント、冒涜的表現、および脅威の分類は、検索可能なテキストでのみ機能し、網羅的または完全ではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f4674-146">Please note that the offensive language, harassment, profanity, and threat classifiers only work with searchable text are not exhaustive or complete.</span></span> <span data-ttu-id="f4674-147">さらに、言語と文化の基準は絶えず変化し、これらの現実に照らして、Microsoft は独自の裁量でこれらの分類子を更新する権利を留保します。</span><span class="sxs-lookup"><span data-stu-id="f4674-147">Further, language and cultural standards continually change, and in light of these realities, Microsoft reserves the right to update these classifiers in its discretion.</span></span> <span data-ttu-id="f4674-148">分類子は、不快な言語やその他の使用言語を監視するのに役立ちますが、分類子は、そのような言語の結果に対処するものではなく、そのような言語の使用を監視または応答する唯一の手段を組織に提供するものではありません。</span><span class="sxs-lookup"><span data-stu-id="f4674-148">While the classifiers may assist your organization in monitoring offensive and other language used, the classifiers do not address consequences of such language and are not intended to provide your organization's sole means of monitoring or responding to the use of such language.</span></span> <span data-ttu-id="f4674-149">事前にトレーニングされた分類子によって識別されたコンテンツの監視、施行、ブロック、削除、および保持に関するすべての決定は、Microsoft またはその子会社ではなく、お客様の組織の責任となります。</span><span class="sxs-lookup"><span data-stu-id="f4674-149">Your organization, and not Microsoft or its subsidiaries, remains responsible for all decisions related to monitoring, enforcement, blocking, removal and retention of any content identified by a pre-trained classifier.</span></span>

## <a name="how-to-verify-that-a-built-in-classifier-will-meet-your-needs"></a><span data-ttu-id="f4674-150">組み込みの分類子がニーズを満たすことを確認する方法</span><span class="sxs-lookup"><span data-stu-id="f4674-150">How to verify that a built-in classifier will meet your needs</span></span>

1. <span data-ttu-id="f4674-151">組み込みの分類子のカテゴリに属していると考えられる (正の一致)、または、テストするカテゴリに含まれるべきではないものを含む、破棄可能なテストコンテンツ項目を収集します。</span><span class="sxs-lookup"><span data-stu-id="f4674-151">Collect disposable test content items that you feel belong in the category of the built-in classifier (positive matches) and ones that shouldn't be included (negative matches) in the category you're testing.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="f4674-152">サンプルアイテムは、暗号化する必要がなく、英語でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="f4674-152">The sample items must not be encrypted and they must be in English.</span></span>

2. <span data-ttu-id="f4674-153">専用の SharePoint Online フォルダーを作成します。フォルダーが検索インデックスに追加されるまで、少なくとも1時間待機します。</span><span class="sxs-lookup"><span data-stu-id="f4674-153">Create a dedicated SharePoint Online folder; wait at least an hour for the folder to be added to the search index.</span></span> <span data-ttu-id="f4674-154">フォルダーの URL をメモしておきます。</span><span class="sxs-lookup"><span data-stu-id="f4674-154">Make note of the folder URL.</span></span>

3. <span data-ttu-id="f4674-155">コンプライアンス管理者またはセキュリティ管理者の役割アクセスを使用して microsoft 365 コンプライアンスセンターにサインインし、 **microsoft 365 コンプライアンスセンター**の  >  **レコード管理 (プレビュー)**  >  **ラベルポリシー**タブを開きます。</span><span class="sxs-lookup"><span data-stu-id="f4674-155">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** > **Records management (preview)** > **Label policies** tab.</span></span>

4. <span data-ttu-id="f4674-156">[] を選択 `Auto-apply a label` します。</span><span class="sxs-lookup"><span data-stu-id="f4674-156">Choose `Auto-apply a label`.</span></span>

5. <span data-ttu-id="f4674-157">[] を選択 `Choose a label to auto-apply` します。</span><span class="sxs-lookup"><span data-stu-id="f4674-157">Choose `Choose a label to auto-apply`.</span></span>

6. <span data-ttu-id="f4674-158">`Create new labels`このテストで使用するラベルを選択して作成します。</span><span class="sxs-lookup"><span data-stu-id="f4674-158">Choose `Create new labels` and create a label for use just with this test.</span></span> <span data-ttu-id="f4674-159">その場合は、 `Retention` をに設定 `off` します。</span><span class="sxs-lookup"><span data-stu-id="f4674-159">When you do this, leave `Retention` set to `off`.</span></span> <span data-ttu-id="f4674-160">保持またはその他のアクションをオンにしない。</span><span class="sxs-lookup"><span data-stu-id="f4674-160">You don't want to turn on any retention or other actions.</span></span> <span data-ttu-id="f4674-161">この場合は、アクションを強制しないで、単にテキストラベルとして保持ラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="f4674-161">In this case, you'll be using the retention label simply as a text label, without enforcing any actions.</span></span> <span data-ttu-id="f4674-162">たとえば、アクションなしで「SourceCode クラシファイア test」という名前の保持ラベルを作成し、その保持ラベルを条件としてソースコード分類子のコンテンツに自動適用することができます。</span><span class="sxs-lookup"><span data-stu-id="f4674-162">For example, you can create a retention label named "SourceCode classifier test" with no actions, and then auto-apply that retention label to content that has Source code classifier as a condition.</span></span> <span data-ttu-id="f4674-163">保持ラベルの作成の詳細については、「[保持ラベルの概要](labels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4674-163">To learn more about creating retention labels, see [Overview of retention labels](labels.md).</span></span>
  
7. <span data-ttu-id="f4674-164">[] を選択し `Auto-apply a label` てから、を選び `Choose a label to auto-apply` ます。</span><span class="sxs-lookup"><span data-stu-id="f4674-164">Choose `Auto-apply a label` and then `Choose a label to auto-apply`.</span></span> <span data-ttu-id="f4674-165">条件に基づいてラベルを自動適用する方法の詳細については、「[条件に基づいて保持ラベルポリシーを自動適用](labels.md#applying-a-retention-label-automatically-based-on-conditions)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4674-165">To learn more about using condition based auto-apply a label see, [auto-apply retention label policy based on a condition](labels.md#applying-a-retention-label-automatically-based-on-conditions).</span></span>

8. <span data-ttu-id="f4674-166">リストからテストラベルを選択し、を選択し `Next` ます。</span><span class="sxs-lookup"><span data-stu-id="f4674-166">Choose your test label from the list and choose `Next`.</span></span>

9. <span data-ttu-id="f4674-167">[] を選択 `Apply label to content that matches a trainable classifier` します。</span><span class="sxs-lookup"><span data-stu-id="f4674-167">Choose `Apply label to content that matches a trainable classifier`.</span></span>

   ![分類子を条件として選択する](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)

10. <span data-ttu-id="f4674-169">この場合は、リストから分類子を選択します。`Source Code`</span><span class="sxs-lookup"><span data-stu-id="f4674-169">Choose your classifier from the list, in this case `Source Code`</span></span>

11. <span data-ttu-id="f4674-170">ポリシーに名前を指定します。たとえば、"ソースコードの組み込みの分類子テスト" のようにします。</span><span class="sxs-lookup"><span data-stu-id="f4674-170">Name the policy, for example "Source code built-in classifier test".</span></span>

12. <span data-ttu-id="f4674-171">[] を選択 `Let me choose specific locations` します。</span><span class="sxs-lookup"><span data-stu-id="f4674-171">Choose `Let me choose specific locations`.</span></span>

13. <span data-ttu-id="f4674-172">を除くすべての場所をオフにし `SharePoint sites` `Choose sites` ます。</span><span class="sxs-lookup"><span data-stu-id="f4674-172">Turn off all locations except `SharePoint sites` and choose `Choose sites`.</span></span>

14. <span data-ttu-id="f4674-173">手順2でサイトの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="f4674-173">Enter the URL for the site from step 2.</span></span>

15. <span data-ttu-id="f4674-174">ウィザードを終了し、`Auto-apply`</span><span class="sxs-lookup"><span data-stu-id="f4674-174">Finish the wizard and choose `Auto-apply`</span></span>

16. <span data-ttu-id="f4674-175">テストアイテムを専用の SharePoint Online フォルダーに配置します。</span><span class="sxs-lookup"><span data-stu-id="f4674-175">Place the test items into the dedicated SharePoint Online folder.</span></span>

17. <span data-ttu-id="f4674-176">ラベルが適用される時間を有効にします。</span><span class="sxs-lookup"><span data-stu-id="f4674-176">Allow an hour for the label to be applied.</span></span>

18. <span data-ttu-id="f4674-177">ラベルのドキュメントのプロパティをチェックして、分類子が予期したとおりにテストコンテンツを含むかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="f4674-177">Check the properties of the documents for the label to see if the classifier included and excluded the test content as you expected.</span></span>

19. <span data-ttu-id="f4674-178">ラベル付けされたアイテムを確認します。</span><span class="sxs-lookup"><span data-stu-id="f4674-178">Review the items that were labeled.</span></span>

20. <span data-ttu-id="f4674-179">テストを完了したら、コンテンツとラベルポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="f4674-179">Delete the content and the label policy if you're done with your testing.</span></span>

<span data-ttu-id="f4674-180">関連項目:</span><span class="sxs-lookup"><span data-stu-id="f4674-180">See also:</span></span>

- [<span data-ttu-id="f4674-181">トレーニング可能な分類子の使用を開始する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="f4674-181">Getting started with trainable classifiers (preview)</span></span>](classifier-getting-started-with.md)
- <span data-ttu-id="f4674-182">「[保持ラベルの概要](labels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4674-182">[Overview of retention labels](labels.md)</span></span>
- [<span data-ttu-id="f4674-183">条件に基づいて保持ラベルポリシーを自動適用する</span><span class="sxs-lookup"><span data-stu-id="f4674-183">Auto-apply retention label policy based on a condition</span></span>](labels.md#applying-a-retention-label-automatically-based-on-conditions)
