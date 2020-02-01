---
title: すぐに使用できる分類子を使用する (プレビュー)
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
description: Microsoft 365 には、組織全体でコンテンツを識別してラベルを付けるために使用できる、machine learning 分類子を使用するための準備が整ったことが用意されています。 このトピックでは、これらを使用して分類子を使用する準備をする方法について説明します。
ms.openlocfilehash: c6659bc32131948c57ad0bf7c8e3a30fbce125d9
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595894"
---
# <a name="using-a-ready-to-use-classifier-preview"></a><span data-ttu-id="c5bb1-104">すぐに使用できる分類子を使用する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="c5bb1-104">Using a ready to use classifier (preview)</span></span>

<span data-ttu-id="c5bb1-105">Microsoft では、非常に大規模なサンプルデータセットを使用して多数の分類子をトレーニングおよびテストしており、特定のカテゴリのコンテンツを特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-105">Microsoft has trained and tested a number of classifiers using very large sample data sets, which can help to identify certain categories of content.</span></span> <span data-ttu-id="c5bb1-106">「 [Trainable 分類子の概要 (プレビュー)」を](classifier-getting-started-with.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-106">See [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span> <span data-ttu-id="c5bb1-107">既定では、 `Ready to use`これらの分類子はグループに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-107">These classifiers show up in the `Ready to use` group by default.</span></span>

- <span data-ttu-id="c5bb1-108">**不快な言葉**: profanities、slurs、taunts、および偽装式を含むテキストアイテムを検出します (これは、より不快な用語と同じ意味を持つ式です)。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-108">**Offensive Language**: detects text items that contain profanities, slurs, taunts, and disguised expressions (which are expressions that have the same meaning as a more offensive term).</span></span>
- <span data-ttu-id="c5bb1-109">**履歴書**: 申請者の個人、教育、専門資格、作業経験、その他の個人を特定できる情報のテキストアカウントであるアイテムを検出します。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-109">**Resumes**: detects items that are textual accounts of an applicant's personal, educational, professional qualifications, work experience, and other personally identifying information.</span></span>
- <span data-ttu-id="c5bb1-110">**SourceCode**: 広く使用されているコンピュータプログラミング言語で記述された命令およびステートメントのセットを含むアイテムを検出します。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-110">**SourceCode**: detects items that contain a set of instructions and statements written in widely used computer programming languages.</span></span>
- <span data-ttu-id="c5bb1-111">**嫌がらせ**: 次の特徴に基づいて、1人または複数の個人を対象とした不快感のある言語のテキストアイテムの特定のカテゴリを検出します。競合、ethnicity、宗教、国内原産者、性別、性的なオリエンテーション、年齢、障碍。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-111">**Harassment**: detects a specific category of offensive language text items related to offensive conduct targeting one or multiple individuals based on the following traits: race, ethnicity, religion, national origin, gender, sexual orientation, age, disability.</span></span>
- <span data-ttu-id="c5bb1-112">**不適切な用語**: 多くの人々を embarrass する式を含む、不快感を与える言語のテキストアイテムの特定のカテゴリを検出します。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-112">**Profanity**: detects a specific category of offensive language text items that contain expressions that embarrass most people.</span></span>
- <span data-ttu-id="c5bb1-113">**脅威**: 暴力をコミットする脅威、または人またはプロパティに物理的な危害または損傷を与える脅威に関連する、不快感を与える言語のテキストアイテムの特定のカテゴリを検出します。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-113">**Threat**: detects a specific category of offensive language text items related to threats to commit violence or do physical harm or damage to a person or property,</span></span>

> [!NOTE]
> <span data-ttu-id="c5bb1-114">分類とラベル付けワークフローで分類子を使用できるようにするには、事前に組織のコンテンツのサンプルに照らしてテストし、分類の予測が期待どおりに満たされることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-114">Before using ready to use classifiers in your classification and labeling workflow, you should test it against a sample of your organization's content that you feel fits the category to verify that its classification predictions meet your expectations.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c5bb1-115">不快な言葉、嫌がらせ、冒涜、および脅威の分類子は、検索可能なテキストのみで機能することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-115">Please note that the offensive language, harassment, profanity, and threat classifiers only work with searchable text are not exhaustive or complete.</span></span> <span data-ttu-id="c5bb1-116">さらに、言語と文化的な標準が絶えず変化し、これらの現実からは、これらの分類子を裁量で更新する権利を Microsoft が留保します。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-116">Further, language and cultural standards continually change, and in light of these realities, Microsoft reserves the right to update these classifiers in its discretion.</span></span> <span data-ttu-id="c5bb1-117">分類子は、お客様の組織が不快な言葉や使用されている他の言語を監視するのに役立ちますが、分類子は、そのような言語の結果に対応していません。そのような言語。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-117">While the classifiers may assist your organization in monitoring offensive and other language used, the classifiers do not address consequences of such language and are not intended to provide your organization’s sole means of monitoring or responding to the use of such language.</span></span> <span data-ttu-id="c5bb1-118">お客様の組織は、Microsoft またはその子会社ではなく、事前に訓練された分類子によって識別されるコンテンツの監視、実施、ブロック、削除、保持に関連するすべての意思決定に対して責任を負うことになります。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-118">Your organization, and not Microsoft or its subsidiaries, remains responsible for all decisions related to monitoring, enforcement, blocking, removal and retention of any content identified by a pre-trained classifier.</span></span>

## <a name="how-to-prepare-for-and-use-a-ready-to-use-classifier"></a><span data-ttu-id="c5bb1-119">使用準備の分類子を準備して使用する方法</span><span class="sxs-lookup"><span data-stu-id="c5bb1-119">How to prepare for and use a ready to use classifier</span></span>

1. <span data-ttu-id="c5bb1-120">破棄可能なテストコンテンツ項目を収集します。 [使用準備完了] 分類子 (正の一致) とそのカテゴリに含まれていないもの (負の一致) のカテゴリに属していると考えられます。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-120">Collect disposable test content items that you feel belong in the category of the ready to use classifier (positive matches) and ones that shouldn't be included (negative matches) in the category you're testing.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c5bb1-121">サンプルアイテムは、暗号化する必要がなく、英語でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-121">The sample items must not be encrypted and they must be in English.</span></span>

2. <span data-ttu-id="c5bb1-122">専用の SharePoint Online フォルダーを作成します。フォルダーが検索インデックスに追加されるまで、少なくとも1時間待機します。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-122">Create a dedicated SharePoint Online folder; wait at least an hour for the folder to be added to the search index.</span></span> <span data-ttu-id="c5bb1-123">フォルダーの URL をメモしておきます。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-123">Make note of the folder URL.</span></span>

3. <span data-ttu-id="c5bb1-124">コンプライアンス管理者またはセキュリティ管理者の役割アクセスを使用して microsoft 365 コンプライアンスセンターにサインインし、 **microsoft 365 コンプライアンスセンター** > の**レコード管理 (プレビュー)** > **ラベルポリシー**タブを開きます。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-124">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** > **Records management (preview)** > **Label policies** tab.</span></span>

4. <span data-ttu-id="c5bb1-125">[ `Auto-apply a label`] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-125">Choose `Auto-apply a label`.</span></span>

5. <span data-ttu-id="c5bb1-126">[ `Choose a label to auto-apply`] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-126">Choose `Choose a label to auto-apply`.</span></span>

6. <span data-ttu-id="c5bb1-127">この`Create new labels`テストで使用するラベルを選択して作成します。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-127">Choose `Create new labels` and create a label for use just with this test.</span></span> <span data-ttu-id="c5bb1-128">この操作を行う場合は`Retention` 、[オフ] のままにします。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-128">When you do this, leave `Retention` set to off.</span></span> <span data-ttu-id="c5bb1-129">保持またはその他のアクションをオンにしない。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-129">You don't want to turn on any retention or other actions.</span></span> <span data-ttu-id="c5bb1-130">この場合は、アクションを強制しないで、単にテキストラベルとして保持ラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-130">In this case, you'll be using the retention label simply as a text label, without enforcing any actions.</span></span> <span data-ttu-id="c5bb1-131">たとえば、アクションなしで「SourceCode クラシファイア test」という名前の保持ラベルを作成し、その保持ラベルを条件としてソースコード分類子のコンテンツに自動適用することができます。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-131">For example, you can create a retention label named "SourceCode classifier test" with no actions, and then auto-apply that retention label to content that has Source code classifier as a condition.</span></span> <span data-ttu-id="c5bb1-132">保持ラベルの作成の詳細については、「[保持ラベルの概要](labels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-132">To learn more about creating retention labels, see [Overview of retention labels](labels.md).</span></span>
  
7. <span data-ttu-id="c5bb1-133">[ `Auto-apply a label` ] を`Choose a label to auto-apply`選択してから、を選びます。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-133">Choose `Auto-apply a label` and then `Choose a label to auto-apply`.</span></span> <span data-ttu-id="c5bb1-134">条件に基づいてラベルを自動適用する方法の詳細については、「[条件に基づいて保持ラベルポリシーを自動適用](labels.md#applying-a-retention-label-automatically-based-on-conditions)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-134">To learn more about using condition based auto-apply a label see, [auto-apply retention label policy based on a condition](labels.md#applying-a-retention-label-automatically-based-on-conditions).</span></span>

8. <span data-ttu-id="c5bb1-135">リストからテストラベルを選択し、を`Next`選択します。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-135">Choose your test label from the list and choose `Next`.</span></span>

9. <span data-ttu-id="c5bb1-136">[ `Apply label to content that matches a trainable classifier`] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-136">Choose `Apply label to content that matches a trainable classifier`.</span></span>

![分類子を条件として選択する](media/classifier-pre-trained-apply-label-match-trainable-classifier.png)<span data-ttu-id="c5bb1-138">.</span><span class="sxs-lookup"><span data-stu-id="c5bb1-138">.</span></span>

10. <span data-ttu-id="c5bb1-139">この場合は、リストから分類子を選択します。`Source Code`</span><span class="sxs-lookup"><span data-stu-id="c5bb1-139">Choose your classifier from the list, in this case `Source Code`</span></span>

11. <span data-ttu-id="c5bb1-140">ポリシーに名前を指定します。たとえば、"ソースコードの準備のために、クラシファイアテストを使用するようにします" などです。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-140">Name the policy, for example "Source code ready to use classifier test".</span></span>

12. <span data-ttu-id="c5bb1-141">[ `Let me choose specific locations`] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-141">Choose `Let me choose specific locations`.</span></span>

13. <span data-ttu-id="c5bb1-142">を除く`SharePoint sites`すべての場所をオフ`Choose sites`にします。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-142">Turn off all locations except `SharePoint sites` and choose `Choose sites`.</span></span>

14. <span data-ttu-id="c5bb1-143">手順2でサイトの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-143">Enter the URL for the site from step 2.</span></span>

15. <span data-ttu-id="c5bb1-144">ウィザードを終了し、`Auto-apply`</span><span class="sxs-lookup"><span data-stu-id="c5bb1-144">Finish the wizard and choose `Auto-apply`</span></span>

16. <span data-ttu-id="c5bb1-145">テストアイテムを専用の SharePoint Online フォルダーに配置します。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-145">Place the test items into the dedicated SharePoint Online folder.</span></span>

17. <span data-ttu-id="c5bb1-146">ラベルが適用される時間を有効にします。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-146">Allow an hour for the label to be applied.</span></span>

18. <span data-ttu-id="c5bb1-147">ラベルのドキュメントのプロパティをチェックして、分類子が予期したとおりにテストコンテンツを含むかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-147">Check the properties of the documents for the label to see if the classifier included and excluded the test content as you expected.</span></span>

19. <span data-ttu-id="c5bb1-148">ラベル付けされたアイテムを確認します。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-148">Review the items that were labeled.</span></span>

20. <span data-ttu-id="c5bb1-149">テストを完了したら、コンテンツとラベルポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-149">Delete the content and the label policy if you're done with your testing.</span></span>

<span data-ttu-id="c5bb1-150">関連項目:</span><span class="sxs-lookup"><span data-stu-id="c5bb1-150">See also:</span></span>

- [<span data-ttu-id="c5bb1-151">トレーニング可能な分類子の使用を開始する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="c5bb1-151">Getting started with trainable classifiers (preview)</span></span>](classifier-getting-started-with.md)
- <span data-ttu-id="c5bb1-152">「[保持ラベルの概要](labels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5bb1-152">[Overview of retention labels](labels.md)</span></span>
- [<span data-ttu-id="c5bb1-153">条件に基づいて保持ラベルポリシーを自動適用する</span><span class="sxs-lookup"><span data-stu-id="c5bb1-153">Auto-apply retention label policy based on a condition</span></span>](labels.md#applying-a-retention-label-automatically-based-on-conditions)
