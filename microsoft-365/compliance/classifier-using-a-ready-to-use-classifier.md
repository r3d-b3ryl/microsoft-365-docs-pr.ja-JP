---
title: 組み込みの分類子を使用する (プレビュー)
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
ms.openlocfilehash: b8e4b51300bee86682924245bbf530e1e954b483
ms.sourcegitcommit: 2859c82b30ae9cbd3a3e4bcdebd65f18444f1a9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2020
ms.locfileid: "42826248"
---
# <a name="using-a-built-in-classifier-preview"></a><span data-ttu-id="71f8f-104">組み込みの分類子を使用する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="71f8f-104">Using a built-in classifier (preview)</span></span>

<span data-ttu-id="71f8f-105">Microsoft では、非常に大規模なサンプルデータセットを使用して多数の分類子をトレーニングおよびテストしており、特定のカテゴリのコンテンツを特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="71f8f-105">Microsoft has trained and tested a number of classifiers using very large sample data sets, which can help to identify certain categories of content.</span></span> <span data-ttu-id="71f8f-106">「 [Trainable 分類子の概要 (プレビュー)」を](classifier-getting-started-with.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="71f8f-106">See [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span> <span data-ttu-id="71f8f-107">既定では、 `Ready to use`これらの分類子はグループに表示されます。</span><span class="sxs-lookup"><span data-stu-id="71f8f-107">These classifiers show up in the `Ready to use` group by default.</span></span>

- <span data-ttu-id="71f8f-108">**不快な言葉**: profanities、slurs、taunts、および偽装式を含むテキストアイテムを検出します (これは、より不快な用語と同じ意味を持つ式です)。</span><span class="sxs-lookup"><span data-stu-id="71f8f-108">**Offensive Language**: detects text items that contain profanities, slurs, taunts, and disguised expressions (which are expressions that have the same meaning as a more offensive term).</span></span>
- <span data-ttu-id="71f8f-109">**履歴書**: 申請者の個人、教育、専門資格、作業経験、その他の個人を特定できる情報のテキストアカウントであるアイテムを検出します。</span><span class="sxs-lookup"><span data-stu-id="71f8f-109">**Resumes**: detects items that are textual accounts of an applicant's personal, educational, professional qualifications, work experience, and other personally identifying information.</span></span>
- <span data-ttu-id="71f8f-110">**ソースコード**: GitHub で使用されている上位25台のコンピュータプログラミング言語で記述された命令およびステートメントのセットを含むアイテムを検出します。</span><span class="sxs-lookup"><span data-stu-id="71f8f-110">**Source Code**: detects items that contain a set of instructions and statements written in the top 25 used computer programming languages on GitHub.</span></span>

|<span data-ttu-id="71f8f-111">言語名</span><span class="sxs-lookup"><span data-stu-id="71f8f-111">language name</span></span>|||||
|---------|---------|---------|---------|---------|
|<span data-ttu-id="71f8f-112">『</span><span class="sxs-lookup"><span data-stu-id="71f8f-112">ActionScript</span></span>|<span data-ttu-id="71f8f-113">C</span><span class="sxs-lookup"><span data-stu-id="71f8f-113">C</span></span>        |<span data-ttu-id="71f8f-114">C#</span><span class="sxs-lookup"><span data-stu-id="71f8f-114">C#</span></span>       |<span data-ttu-id="71f8f-115">+</span><span class="sxs-lookup"><span data-stu-id="71f8f-115">C++</span></span>     |<span data-ttu-id="71f8f-116">Clojure</span><span class="sxs-lookup"><span data-stu-id="71f8f-116">Clojure</span></span>  |
|<span data-ttu-id="71f8f-117">CoffeeScript</span><span class="sxs-lookup"><span data-stu-id="71f8f-117">CoffeeScript</span></span>|<span data-ttu-id="71f8f-118">CSS</span><span class="sxs-lookup"><span data-stu-id="71f8f-118">CSS</span></span>     |<span data-ttu-id="71f8f-119">移動</span><span class="sxs-lookup"><span data-stu-id="71f8f-119">Go</span></span>       |<span data-ttu-id="71f8f-120">Haskell</span><span class="sxs-lookup"><span data-stu-id="71f8f-120">Haskell</span></span> |<span data-ttu-id="71f8f-121">HTML</span><span class="sxs-lookup"><span data-stu-id="71f8f-121">HTML</span></span>     |
|<span data-ttu-id="71f8f-122">Java</span><span class="sxs-lookup"><span data-stu-id="71f8f-122">Java</span></span>     |<span data-ttu-id="71f8f-123">JavaScript</span><span class="sxs-lookup"><span data-stu-id="71f8f-123">JavaScript</span></span>|<span data-ttu-id="71f8f-124">Lua</span><span class="sxs-lookup"><span data-stu-id="71f8f-124">Lua</span></span>      |<span data-ttu-id="71f8f-125">MATLAB</span><span class="sxs-lookup"><span data-stu-id="71f8f-125">MATLAB</span></span>   |<span data-ttu-id="71f8f-126">Objective-C</span><span class="sxs-lookup"><span data-stu-id="71f8f-126">Objective-C</span></span>|
|<span data-ttu-id="71f8f-127">Perl</span><span class="sxs-lookup"><span data-stu-id="71f8f-127">Perl</span></span>     |<span data-ttu-id="71f8f-128">PHP</span><span class="sxs-lookup"><span data-stu-id="71f8f-128">PHP</span></span>      |<span data-ttu-id="71f8f-129">Python</span><span class="sxs-lookup"><span data-stu-id="71f8f-129">Python</span></span>   |<span data-ttu-id="71f8f-130">R</span><span class="sxs-lookup"><span data-stu-id="71f8f-130">R</span></span>        |<span data-ttu-id="71f8f-131">Ruby</span><span class="sxs-lookup"><span data-stu-id="71f8f-131">Ruby</span></span>     |
|<span data-ttu-id="71f8f-132">スケール a</span><span class="sxs-lookup"><span data-stu-id="71f8f-132">Scala</span></span>    |<span data-ttu-id="71f8f-133">Shell</span><span class="sxs-lookup"><span data-stu-id="71f8f-133">Shell</span></span>    |<span data-ttu-id="71f8f-134">実現</span><span class="sxs-lookup"><span data-stu-id="71f8f-134">Swift</span></span>    |<span data-ttu-id="71f8f-135">テックス</span><span class="sxs-lookup"><span data-stu-id="71f8f-135">Tex</span></span>      |<span data-ttu-id="71f8f-136">Vim スクリプト</span><span class="sxs-lookup"><span data-stu-id="71f8f-136">Vim Script</span></span>|

- <span data-ttu-id="71f8f-137">**嫌がらせ**: 次の特徴に基づいて、1人または複数の個人を対象とした不快感のある言語のテキストアイテムの特定のカテゴリを検出します。競合、ethnicity、宗教、国内原産者、性別、性的なオリエンテーション、年齢、障碍。</span><span class="sxs-lookup"><span data-stu-id="71f8f-137">**Harassment**: detects a specific category of offensive language text items related to offensive conduct targeting one or multiple individuals based on the following traits: race, ethnicity, religion, national origin, gender, sexual orientation, age, disability.</span></span>
- <span data-ttu-id="71f8f-138">**不適切な用語**: 多くの人々を embarrass する式を含む、不快感を与える言語のテキストアイテムの特定のカテゴリを検出します。</span><span class="sxs-lookup"><span data-stu-id="71f8f-138">**Profanity**: detects a specific category of offensive language text items that contain expressions that embarrass most people.</span></span>
- <span data-ttu-id="71f8f-139">**脅威**: 暴力をコミットする脅威、または人またはプロパティに物理的な危害または損傷を与える脅威に関連する、不快感を与える言語のテキストアイテムの特定のカテゴリを検出します。</span><span class="sxs-lookup"><span data-stu-id="71f8f-139">**Threat**: detects a specific category of offensive language text items related to threats to commit violence or do physical harm or damage to a person or property,</span></span>

> [!NOTE]
> <span data-ttu-id="71f8f-140">分類とラベル付けワークフローに組み込み分類子を使用する前に、組織のコンテンツのサンプルに照らしてテストし、分類の予測が期待どおりに満たされることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71f8f-140">Before using built-in classifiers in your classification and labeling workflow, you should test it against a sample of your organization's content that you feel fits the category to verify that its classification predictions meet your expectations.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71f8f-141">不快な言葉、嫌がらせ、冒涜、および脅威の分類子は、検索可能なテキストのみで機能することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="71f8f-141">Please note that the offensive language, harassment, profanity, and threat classifiers only work with searchable text are not exhaustive or complete.</span></span> <span data-ttu-id="71f8f-142">さらに、言語と文化的な標準が絶えず変化し、これらの現実からは、これらの分類子を裁量で更新する権利を Microsoft が留保します。</span><span class="sxs-lookup"><span data-stu-id="71f8f-142">Further, language and cultural standards continually change, and in light of these realities, Microsoft reserves the right to update these classifiers in its discretion.</span></span> <span data-ttu-id="71f8f-143">分類子は、お客様の組織が不快な言葉や使用されている他の言語を監視するのに役立ちますが、分類子は、そのような言語の結果に対応していません。そのような言語。</span><span class="sxs-lookup"><span data-stu-id="71f8f-143">While the classifiers may assist your organization in monitoring offensive and other language used, the classifiers do not address consequences of such language and are not intended to provide your organization's sole means of monitoring or responding to the use of such language.</span></span> <span data-ttu-id="71f8f-144">お客様の組織は、Microsoft またはその子会社ではなく、事前に訓練された分類子によって識別されるコンテンツの監視、実施、ブロック、削除、保持に関連するすべての意思決定に対して責任を負うことになります。</span><span class="sxs-lookup"><span data-stu-id="71f8f-144">Your organization, and not Microsoft or its subsidiaries, remains responsible for all decisions related to monitoring, enforcement, blocking, removal and retention of any content identified by a pre-trained classifier.</span></span>

## <a name="how-to-prepare-for-and-use-a-built-in-classifier"></a><span data-ttu-id="71f8f-145">組み込みの分類子を準備して使用する方法</span><span class="sxs-lookup"><span data-stu-id="71f8f-145">How to prepare for and use a built-in classifier</span></span>

1. <span data-ttu-id="71f8f-146">組み込みの分類子のカテゴリに属していると考えられる (正の一致)、または、テストするカテゴリに含まれるべきではないものを含む、破棄可能なテストコンテンツ項目を収集します。</span><span class="sxs-lookup"><span data-stu-id="71f8f-146">Collect disposable test content items that you feel belong in the category of the built-in classifier (positive matches) and ones that shouldn't be included (negative matches) in the category you're testing.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71f8f-147">サンプルアイテムは、暗号化する必要がなく、英語でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="71f8f-147">The sample items must not be encrypted and they must be in English.</span></span>

2. <span data-ttu-id="71f8f-148">専用の SharePoint Online フォルダーを作成します。フォルダーが検索インデックスに追加されるまで、少なくとも1時間待機します。</span><span class="sxs-lookup"><span data-stu-id="71f8f-148">Create a dedicated SharePoint Online folder; wait at least an hour for the folder to be added to the search index.</span></span> <span data-ttu-id="71f8f-149">フォルダーの URL をメモしておきます。</span><span class="sxs-lookup"><span data-stu-id="71f8f-149">Make note of the folder URL.</span></span>

3. <span data-ttu-id="71f8f-150">コンプライアンス管理者またはセキュリティ管理者の役割アクセスを使用して microsoft 365 コンプライアンスセンターにサインインし、 **microsoft 365 コンプライアンスセンター** > の**レコード管理 (プレビュー)** > **ラベルポリシー**タブを開きます。</span><span class="sxs-lookup"><span data-stu-id="71f8f-150">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** > **Records management (preview)** > **Label policies** tab.</span></span>

4. <span data-ttu-id="71f8f-151">[ `Auto-apply a label`] を選択します。</span><span class="sxs-lookup"><span data-stu-id="71f8f-151">Choose `Auto-apply a label`.</span></span>

5. <span data-ttu-id="71f8f-152">[ `Choose a label to auto-apply`] を選択します。</span><span class="sxs-lookup"><span data-stu-id="71f8f-152">Choose `Choose a label to auto-apply`.</span></span>

6. <span data-ttu-id="71f8f-153">この`Create new labels`テストで使用するラベルを選択して作成します。</span><span class="sxs-lookup"><span data-stu-id="71f8f-153">Choose `Create new labels` and create a label for use just with this test.</span></span> <span data-ttu-id="71f8f-154">この操作を行う場合は`Retention` 、[オフ] のままにします。</span><span class="sxs-lookup"><span data-stu-id="71f8f-154">When you do this, leave `Retention` set to off.</span></span> <span data-ttu-id="71f8f-155">保持またはその他のアクションをオンにしない。</span><span class="sxs-lookup"><span data-stu-id="71f8f-155">You don't want to turn on any retention or other actions.</span></span> <span data-ttu-id="71f8f-156">この場合は、アクションを強制しないで、単にテキストラベルとして保持ラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="71f8f-156">In this case, you'll be using the retention label simply as a text label, without enforcing any actions.</span></span> <span data-ttu-id="71f8f-157">たとえば、アクションなしで「SourceCode クラシファイア test」という名前の保持ラベルを作成し、その保持ラベルを条件としてソースコード分類子のコンテンツに自動適用することができます。</span><span class="sxs-lookup"><span data-stu-id="71f8f-157">For example, you can create a retention label named "SourceCode classifier test" with no actions, and then auto-apply that retention label to content that has Source code classifier as a condition.</span></span> <span data-ttu-id="71f8f-158">保持ラベルの作成の詳細については、「[保持ラベルの概要](labels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71f8f-158">To learn more about creating retention labels, see [Overview of retention labels](labels.md).</span></span>
  
7. <span data-ttu-id="71f8f-159">[ `Auto-apply a label` ] を`Choose a label to auto-apply`選択してから、を選びます。</span><span class="sxs-lookup"><span data-stu-id="71f8f-159">Choose `Auto-apply a label` and then `Choose a label to auto-apply`.</span></span> <span data-ttu-id="71f8f-160">条件に基づいてラベルを自動適用する方法の詳細については、「[条件に基づいて保持ラベルポリシーを自動適用](labels.md#applying-a-retention-label-automatically-based-on-conditions)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71f8f-160">To learn more about using condition based auto-apply a label see, [auto-apply retention label policy based on a condition](labels.md#applying-a-retention-label-automatically-based-on-conditions).</span></span>

8. <span data-ttu-id="71f8f-161">リストからテストラベルを選択し、を`Next`選択します。</span><span class="sxs-lookup"><span data-stu-id="71f8f-161">Choose your test label from the list and choose `Next`.</span></span>

9. <span data-ttu-id="71f8f-162">[ `Apply label to content that matches a trainable classifier`] を選択します。</span><span class="sxs-lookup"><span data-stu-id="71f8f-162">Choose `Apply label to content that matches a trainable classifier`.</span></span>

![分類子を条件として選択する](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)<span data-ttu-id="71f8f-164">.</span><span class="sxs-lookup"><span data-stu-id="71f8f-164">.</span></span>

10. <span data-ttu-id="71f8f-165">この場合は、リストから分類子を選択します。`Source Code`</span><span class="sxs-lookup"><span data-stu-id="71f8f-165">Choose your classifier from the list, in this case `Source Code`</span></span>

11. <span data-ttu-id="71f8f-166">ポリシーに名前を指定します。たとえば、"ソースコードの組み込みの分類子テスト" のようにします。</span><span class="sxs-lookup"><span data-stu-id="71f8f-166">Name the policy, for example "Source code built-in classifier test".</span></span>

12. <span data-ttu-id="71f8f-167">[ `Let me choose specific locations`] を選択します。</span><span class="sxs-lookup"><span data-stu-id="71f8f-167">Choose `Let me choose specific locations`.</span></span>

13. <span data-ttu-id="71f8f-168">を除く`SharePoint sites`すべての場所をオフ`Choose sites`にします。</span><span class="sxs-lookup"><span data-stu-id="71f8f-168">Turn off all locations except `SharePoint sites` and choose `Choose sites`.</span></span>

14. <span data-ttu-id="71f8f-169">手順2でサイトの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="71f8f-169">Enter the URL for the site from step 2.</span></span>

15. <span data-ttu-id="71f8f-170">ウィザードを終了し、`Auto-apply`</span><span class="sxs-lookup"><span data-stu-id="71f8f-170">Finish the wizard and choose `Auto-apply`</span></span>

16. <span data-ttu-id="71f8f-171">テストアイテムを専用の SharePoint Online フォルダーに配置します。</span><span class="sxs-lookup"><span data-stu-id="71f8f-171">Place the test items into the dedicated SharePoint Online folder.</span></span>

17. <span data-ttu-id="71f8f-172">ラベルが適用される時間を有効にします。</span><span class="sxs-lookup"><span data-stu-id="71f8f-172">Allow an hour for the label to be applied.</span></span>

18. <span data-ttu-id="71f8f-173">ラベルのドキュメントのプロパティをチェックして、分類子が予期したとおりにテストコンテンツを含むかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="71f8f-173">Check the properties of the documents for the label to see if the classifier included and excluded the test content as you expected.</span></span>

19. <span data-ttu-id="71f8f-174">ラベル付けされたアイテムを確認します。</span><span class="sxs-lookup"><span data-stu-id="71f8f-174">Review the items that were labeled.</span></span>

20. <span data-ttu-id="71f8f-175">テストを完了したら、コンテンツとラベルポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="71f8f-175">Delete the content and the label policy if you're done with your testing.</span></span>

<span data-ttu-id="71f8f-176">関連項目:</span><span class="sxs-lookup"><span data-stu-id="71f8f-176">See also:</span></span>

- [<span data-ttu-id="71f8f-177">トレーニング可能な分類子の使用を開始する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="71f8f-177">Getting started with trainable classifiers (preview)</span></span>](classifier-getting-started-with.md)
- <span data-ttu-id="71f8f-178">「[保持ラベルの概要](labels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71f8f-178">[Overview of retention labels](labels.md)</span></span>
- [<span data-ttu-id="71f8f-179">条件に基づいて保持ラベルポリシーを自動適用する</span><span class="sxs-lookup"><span data-stu-id="71f8f-179">Auto-apply retention label policy based on a condition</span></span>](labels.md#applying-a-retention-label-automatically-based-on-conditions)
