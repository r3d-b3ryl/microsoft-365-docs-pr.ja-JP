---
title: カスタムの機密情報の種類を使用する前に
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/17/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: セキュリティ/コンプライアンス センターのグラフィカル ユーザー インターフェイスで DLP のカスタム機密情報の種類を作成、変更、削除、およびテストする方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 94f0f6b68e9f952e0d52ce7cb71ccf03913584f4
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929353"
---
# <a name="get-started-with-custom-sensitive-information-types"></a><span data-ttu-id="8f4df-103">カスタムの機密情報の種類を使用する前に</span><span class="sxs-lookup"><span data-stu-id="8f4df-103">Get started with custom sensitive information types</span></span>

<span data-ttu-id="8f4df-104">事前構成の機密情報の種類がニーズを満たしていない場合は、完全に定義した独自のカスタムの機密情報の種類を作成するか、事前構成のいずれかをコピーして変更できます。</span><span class="sxs-lookup"><span data-stu-id="8f4df-104">If the pre-configured sensitive information types don't meet your needs, you can create your own custom sensitive information types that you fully define or you can copy one of the pre-configured ones and modify it.</span></span>

<span data-ttu-id="8f4df-105">この方法を使用して作成されるカスタムの機密情報の種類は、`Microsoft.SCCManaged.CustomRulePack`という名前のルール パッケージに追加されます。</span><span class="sxs-lookup"><span data-stu-id="8f4df-105">The custom sensitive information types that you create by using this method are added to the rule package named `Microsoft.SCCManaged.CustomRulePack`.</span></span>

<span data-ttu-id="8f4df-106">新しい機密情報の種類を作成するには、次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="8f4df-106">There are two ways to create a new sensitive information type:</span></span>

- [<span data-ttu-id="8f4df-107">すべての要素を完全に定義するところから</span><span class="sxs-lookup"><span data-stu-id="8f4df-107">from scratch where you fully define all elements</span></span>](#create-a-custom-sensitive-information-type)
- [<span data-ttu-id="8f4df-108">既存の機密情報の種類をコピーおよび変更する</span><span class="sxs-lookup"><span data-stu-id="8f4df-108">copy and modify an existing sensitive information type</span></span>](#copy-and-modify-a-sensitive-information-type)


## <a name="before-you-begin"></a><span data-ttu-id="8f4df-109">開始する前に</span><span class="sxs-lookup"><span data-stu-id="8f4df-109">Before you begin</span></span>

- <span data-ttu-id="8f4df-110">機密情報の種類とその構成に精通している必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f4df-110">You should be familiar with sensitive information types and what they are composed of.</span></span> <span data-ttu-id="8f4df-111">「[機密情報の種類に関する詳細情報](sensitive-information-type-learn-about.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f4df-111">See, [Learn about sensitive information types](sensitive-information-type-learn-about.md).</span></span> <span data-ttu-id="8f4df-112">次の役割を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="8f4df-112">It is critical to understand the roles of:</span></span>
    - <span data-ttu-id="8f4df-113">[正規表現](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/) - Microsoft 365 の機密情報の種類は Boost.RegEx 5.1.3 エンジンを使用する</span><span class="sxs-lookup"><span data-stu-id="8f4df-113">[regular expressions](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/) - Microsoft 365 sensitive information types uses the Boost.RegEx 5.1.3 engine</span></span>
    - <span data-ttu-id="8f4df-114">キーワード リスト - 機密情報の種類を定義する際に独自のキーワードを作成することも、既存のキーワード リストから選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="8f4df-114">keyword lists - you can create your own as you define your sensitive information type or choose from existing keyword lists</span></span>
    - [<span data-ttu-id="8f4df-115">キーワード辞書</span><span class="sxs-lookup"><span data-stu-id="8f4df-115">keyword dictionary</span></span>](create-a-keyword-dictionary.md)
    - [<span data-ttu-id="8f4df-116">関数</span><span class="sxs-lookup"><span data-stu-id="8f4df-116">functions</span></span>](what-the-dlp-functions-look-for.md)
    - [<span data-ttu-id="8f4df-117">信頼度レベル</span><span class="sxs-lookup"><span data-stu-id="8f4df-117">confidence levels</span></span>](sensitive-information-type-learn-about.md#more-on-confidence-levels)
 
- <span data-ttu-id="8f4df-118">UI を使用してカスタムの機密情報の種類を作成、テスト、展開するには、グローバル管理者またはコンプライアンス管理者のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="8f4df-118">You must have Global admin or Compliance admin permissions to create, test, and deploy a custom sensitive information type through the UI.</span></span> <span data-ttu-id="8f4df-119">Office 365 で「[管理者ロールについて](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f4df-119">See [About admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide) in Office 365.</span></span>

- <span data-ttu-id="8f4df-120">組織には、データ損失防止 (DLP) を含む Office 365 Enterprise などのサブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="8f4df-120">Your organization must have a subscription, such as Office 365 Enterprise, that includes Data Loss Prevention (DLP).</span></span> <span data-ttu-id="8f4df-121">[メッセージング ポリシーとコンプライアンス サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f4df-121">See [Messaging Policy and Compliance ServiceDescription](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc).</span></span> 


> [!IMPORTANT]
> <span data-ttu-id="8f4df-122">Microsoft カスタマー サービス/サポートでは、カスタム分類または正規表現パターンの作成をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="8f4df-122">Microsoft Customer Service & Support can't assist with creating custom classifications or regular expression patterns.</span></span> <span data-ttu-id="8f4df-123">サポート エンジニアは、たとえば、テスト目的のサンプルの正規表現パターンを提供したり、期待通りにトリガーされない既存の正規表現パターンのトラブルシューティングをサポートしたりなど、機能に対する限定的なサポートを提供しますが、カスタムのコンテンツ一致の開発でユーザーの要件を満たしたり、義務を果たしたりすることを確約するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="8f4df-123">Support engineers can provide limited support for the feature, such as, providing sample regular expression patterns for testing purposes, or assisting with troubleshooting an existing regular expression pattern that's not triggering as expected, but can't provide assurances that any custom content-matching development will fulfill your requirements or obligations.</span></span>

## <a name="create-a-custom-sensitive-information-type"></a><span data-ttu-id="8f4df-124">カスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="8f4df-124">Create a custom sensitive information type</span></span>

<span data-ttu-id="8f4df-125">完全に定義した新しい機密情報の種類を作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8f4df-125">Use this procedure to create a new sensitive information type that you fully define.</span></span> 

1. <span data-ttu-id="8f4df-126">コンプライアンス センターで、**[データの分類]** \> **[機密情報の種類]** の順に移動し、**[情報の種類を作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f4df-126">In the Compliance Center, go to **Data classification** \> **Sensitive info types** and choose **Create info type**.</span></span>
2. <span data-ttu-id="8f4df-127">**[名前]** および **[説明]** の値を入力し、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f4df-127">Fill in values for **Name** and **Description** and choose **Next**.</span></span>
3. <span data-ttu-id="8f4df-128">**[パターンの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f4df-128">Choose **Create pattern**.</span></span> <span data-ttu-id="8f4df-129">新しい機密情報の種類を定義するときに、それぞれ異なる要素と信頼度レベルを持つ複数のパターンを作成できます。</span><span class="sxs-lookup"><span data-stu-id="8f4df-129">You can create multiple patterns, each with different elements and confidence levels, as you define your new sensitive information type.</span></span>
4. <span data-ttu-id="8f4df-130">パターンの既定の信頼度レベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="8f4df-130">Choose the default confidence level for the pattern.</span></span> <span data-ttu-id="8f4df-131">値は、**[低い信頼度]**、**[中程度の信頼度]**、および **[高い信頼度]** です。</span><span class="sxs-lookup"><span data-stu-id="8f4df-131">The values are **Low confidence**, **Medium confidence**, and **High confidence**.</span></span>
5. <span data-ttu-id="8f4df-132">**[主要要素]** を選択して定義します。</span><span class="sxs-lookup"><span data-stu-id="8f4df-132">Choose and define **Primary element**.</span></span> <span data-ttu-id="8f4df-133">主要要素は、オプションの検証を使用した **[正規表現]**、**[キーワード リスト]**、**[キーワード辞書]**、または事前構成の **[関数]** のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="8f4df-133">The primary element can be a **Regular expression** with an optional validator, a **Keyword list**, a **Keyword dictionary**, or one of the pre-configured **Functions**.</span></span> <span data-ttu-id="8f4df-134">DLP 関数の詳細については、「[DLP 関数で探索する内容](what-the-dlp-functions-look-for.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f4df-134">For more information on DLP functions, see [What the DLP functions look for](what-the-dlp-functions-look-for.md).</span></span>
6. <span data-ttu-id="8f4df-135">**[文字の近接度]** の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="8f4df-135">Fill in a value for **Character proximity**.</span></span>
7. <span data-ttu-id="8f4df-136">(省略可能) サポート要素がある場合は追加します。</span><span class="sxs-lookup"><span data-stu-id="8f4df-136">(Optional) Add supporting elements if you have any.</span></span> <span data-ttu-id="8f4df-137">サポート要素は、オプションの検証、キーワード リスト、キーワード辞書、または事前定義された関数のいずれかを使用する正規表現です。</span><span class="sxs-lookup"><span data-stu-id="8f4df-137">Supporting elements can be a regular expression with an optional validator, a keyword list, a keyword dictionary or one of the pre-defined functions.</span></span> 
8.  <span data-ttu-id="8f4df-138">(省略可能) 使用可能なチェックのリストから追加チェックを追加します。</span><span class="sxs-lookup"><span data-stu-id="8f4df-138">(Optional) Add additional checks from the list of available checks</span></span>
9. <span data-ttu-id="8f4df-139">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f4df-139">Choose **Create**.</span></span>
10. <span data-ttu-id="8f4df-140">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f4df-140">Choose **Next**.</span></span>
11. <span data-ttu-id="8f4df-141">この機密情報の種類に対して、**推奨される信頼度レベル** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f4df-141">Choose the **recommended confidence level** for this sensitive information type.</span></span>
12. <span data-ttu-id="8f4df-142">設定を確認し、**[送信]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f4df-142">Check your setting and choose **Submit**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8f4df-143">Microsoft 365 では、検索クローラーを使用して、SharePoint Online および OneDrive for Business のサイトの機密情報を特定して分類します。</span><span class="sxs-lookup"><span data-stu-id="8f4df-143">Microsoft 365 uses the search crawler to identify and classify sensitive information in SharePoint Online and OneDrive for Business sites.</span></span> <span data-ttu-id="8f4df-144">既存のコンテンツで新しいカスタムの機密情報の種類を特定するには、そのコンテンツを再クロールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f4df-144">To identify your new custom sensitive information type in existing content, the content must be re-crawled.</span></span> <span data-ttu-id="8f4df-145">コンテンツは、スケジュールに基づいてクロールされますが、サイト コレクション、リスト、またはライブラリのコンテンツを手動で再クロールすることができます。</span><span class="sxs-lookup"><span data-stu-id="8f4df-145">Content is crawled based on a schedule, but you can manually re-crawl content for a site collection, list, or library.</span></span> <span data-ttu-id="8f4df-146">詳細については、「[サイト、ライブラリ、またはリストのクロールおよび再インデックスの手動要求](https://docs.microsoft.com/sharepoint/crawl-site-content)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f4df-146">For more information, see [Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/sharepoint/crawl-site-content).</span></span>

13. <span data-ttu-id="8f4df-147">**[データの分類]** ページに、すべての機密情報の種類が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f4df-147">On the **Data classification** page, you'll see all the sensitive information types listed.</span></span> <span data-ttu-id="8f4df-148">**[更新]** を選択し、検索ツールを参照または使用して作成した機密情報の種類を検索します。</span><span class="sxs-lookup"><span data-stu-id="8f4df-148">Choose **Refresh** and then browse for or use the search tool to find the sensitive information type you just created.</span></span>

## <a name="test-a-sensitive-information-type"></a><span data-ttu-id="8f4df-149">機密情報の種類をテストする</span><span class="sxs-lookup"><span data-stu-id="8f4df-149">Test a sensitive information type</span></span>

<span data-ttu-id="8f4df-150">リスト内の任意の機密情報の種類をテストできます。</span><span class="sxs-lookup"><span data-stu-id="8f4df-150">You can test any sensitive information type in the list.</span></span> <span data-ttu-id="8f4df-151">ポリシーで使用する前に、作成するすべての機密情報の種類をテストすることを推奨します。</span><span class="sxs-lookup"><span data-stu-id="8f4df-151">We suggest that you test every sensitive information type that you create before using it in a policy.</span></span>

1. <span data-ttu-id="8f4df-152">Word 文書のように、2 つのファイルを準備します。</span><span class="sxs-lookup"><span data-stu-id="8f4df-152">Prepare two files, like a Word document.</span></span> <span data-ttu-id="8f4df-153">機密情報の種類で指定した要素と一致するコンテンツと一致しないコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="8f4df-153">One with content that matches the elements you specified in your sensitive information type and one that doesn't match.</span></span>
2. <span data-ttu-id="8f4df-154">コンプライアンス センターで、**[データの分類]** \> **[機密情報の種類]** の順に移動し、リストから機密情報の種類を選択して詳細ウィンドウを開き、**[テスト]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f4df-154">In the Compliance Center, go to **Data classification** \> **Sensitive info types** and choose the sensitive information type from the list to open the details pane and choose **Test**.</span></span>
3. <span data-ttu-id="8f4df-155">ファイルをアップロードし、**[テスト]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f4df-155">Upload a file and choose **Test**.</span></span>
4. <span data-ttu-id="8f4df-156">**[結果と一致]** ページで、結果を確認して **[完了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f4df-156">On the **Matches results** page, review the results and choose **Finish**.</span></span>

## <a name="modify-custom-sensitive-information-types-in-the-compliance-center"></a><span data-ttu-id="8f4df-157">コンプライアンス センターでカスタムの機密情報の種類を変更する</span><span class="sxs-lookup"><span data-stu-id="8f4df-157">Modify custom sensitive information types in the Compliance Center</span></span>

1. <span data-ttu-id="8f4df-158">コンプライアンス センターで、**[データの分類]** \> **[機密情報の種類]** の順に移動し、変更する機密情報の種類をリストから選択して **[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f4df-158">In the Compliance Center, go to **Data classification** \> **Sensitive info types** and choose the sensitive information type from the list that you want to modify choose **Edit**.</span></span>
2. <span data-ttu-id="8f4df-159">固有の重要要素およびサポート要素、信頼度レベル、文字の近接度、チェックの追加、または既存のパターンの編集と削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8f4df-159">You can add other patterns, with unique primary and supporting elements, confidence levels, character proximity, and additional checks or edit/remove the existing ones.</span></span> <span data-ttu-id="8f4df-160">詳細については、「[カスタムの機密情報の種類を作成する](#create-a-custom-sensitive-information-type)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8f4df-160">For more information, see [Create a custom sensitive information type](#create-a-custom-sensitive-information-type).</span></span>

## <a name="remove-custom-sensitive-information-types-in-the-compliance-center"></a><span data-ttu-id="8f4df-161">コンプライアンス センターでカスタムの機密情報の種類を削除する</span><span class="sxs-lookup"><span data-stu-id="8f4df-161">Remove custom sensitive information types in the Compliance Center</span></span> 

> [!NOTE]
> <span data-ttu-id="8f4df-162">カスタムの機密情報の種類のみを削除できます。組み込みの機密情報の種類は削除できません。</span><span class="sxs-lookup"><span data-stu-id="8f4df-162">You can only remove custom sensitive information types; you can't remove built-in sensitive information types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8f4df-163">カスタムの機密情報の種類を削除する前に、その機密情報の種類を参照している DLP ポリシーまたは Exchange メール フロー ルール (別名: トランスポート ルール) がないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8f4df-163">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

1. <span data-ttu-id="8f4df-164">コンプライアンス センターで、**[データの分類]** \> **[機密情報の種類]** の順に移動し、削除したいリストから機密情報の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f4df-164">In the Compliance Center, go to **Data classification** \> **Sensitive info types** and choose the sensitive information type from the list that you want to remove.</span></span>
2. <span data-ttu-id="8f4df-165">開くフライアウトで、**[削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f4df-165">In the fly-out that opens, choose **Delete**.</span></span>

## <a name="copy-and-modify-a-sensitive-information-type"></a><span data-ttu-id="8f4df-166">機密情報の種類をコピーおよび変更する</span><span class="sxs-lookup"><span data-stu-id="8f4df-166">Copy and modify a sensitive information type</span></span>

<span data-ttu-id="8f4df-167">既存の機密情報の種類に基づいて新しい機密情報の種類を作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8f4df-167">Use this procedure to create a new sensitive information type that is based on an existing sensitive information type.</span></span> 

1. <span data-ttu-id="8f4df-168">コンプライアンス センターで、**[データの分類]** \> **[機密情報の種類]** の順に移動し、コピーする機密情報の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f4df-168">In the Compliance Center, go to **Data classification** \> **Sensitive info types** and choose the sensitive information type that you want to copy.</span></span>
2. <span data-ttu-id="8f4df-169">フライアウトで、**[コピー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f4df-169">In the flyout, choose **Copy**.</span></span>
3. <span data-ttu-id="8f4df-170">機密情報の種類のリストから **[更新]** を選択し、作成したコピーを参照または検索します。</span><span class="sxs-lookup"><span data-stu-id="8f4df-170">Choose **Refresh** in the list of sensitive information types and either browse or search for the copy you just made.</span></span> <span data-ttu-id="8f4df-171">部分的な文字列の検索が機能するため、`copy` だけを検索すると、名前に `copy` という単語が含まれるすべての機密情報の種類が返されます。</span><span class="sxs-lookup"><span data-stu-id="8f4df-171">Partial sting searches work, so you could just search for `copy` and search would return all the sensitive information types with the word `copy` in the name.</span></span> 
4. <span data-ttu-id="8f4df-172">**[名前]** および **[説明]** の値を入力し、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f4df-172">Fill in values for **Name** and **Description** and choose **Next**.</span></span>
5. <span data-ttu-id="8f4df-173">機密情報の種類のコピーを選択し、**[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f4df-173">Choose your sensitive information type copy and choose **Edit**.</span></span> 
6. <span data-ttu-id="8f4df-174">新しい機密情報の種類に新しい **[名前]** および **[説明]** を指定します。</span><span class="sxs-lookup"><span data-stu-id="8f4df-174">Give your new sensitive information type a new **Name** and **Description**.</span></span>
7. <span data-ttu-id="8f4df-175">既存のパターンを編集または削除し、新しいパターンを追加できます。</span><span class="sxs-lookup"><span data-stu-id="8f4df-175">You can choose to edit or remove the existing patterns and add new ones.</span></span> <span data-ttu-id="8f4df-176">新しいパターンの既定の信頼度レベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="8f4df-176">Choose the default confidence level for the new pattern.</span></span> <span data-ttu-id="8f4df-177">値は、**[低い信頼度]**、**[中程度の信頼度]**、および **[高い信頼度]** です。</span><span class="sxs-lookup"><span data-stu-id="8f4df-177">The values are **Low confidence**, **Medium confidence**, and **High confidence**.</span></span>
8. <span data-ttu-id="8f4df-178">**[主要要素]** を選択して定義します。</span><span class="sxs-lookup"><span data-stu-id="8f4df-178">Choose and define **Primary element**.</span></span> <span data-ttu-id="8f4df-179">主要要素は、**[正規表現]**、**[キーワード リスト]**、**[キーワード辞書]**、または事前構成の **[関数]** のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="8f4df-179">The primary element can be a **Regular expression**, a **Keyword list**, a **Keyword dictionary**, or one of the pre-configured **Functions**.</span></span> <span data-ttu-id="8f4df-180">「[DLP 関数の検索対象](what-the-dlp-functions-look-for.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f4df-180">See, [What the DLP functions look for](what-the-dlp-functions-look-for.md).</span></span>
9. <span data-ttu-id="8f4df-181">**[文字の近接度]** の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="8f4df-181">Fill in a value for **Character proximity**.</span></span>
10. <span data-ttu-id="8f4df-182">(省略可能) **[サポート要素]** または任意の **[追加チェック]** がある場合は、それらを追加します。</span><span class="sxs-lookup"><span data-stu-id="8f4df-182">(Optional) If you have **Supporting elements** or any **Additional checks** add them.</span></span> <span data-ttu-id="8f4df-183">必要に応じて、**[サポート要素]** をグループ化できます。</span><span class="sxs-lookup"><span data-stu-id="8f4df-183">If needed you can group your **Supporting elements**.</span></span>
11. <span data-ttu-id="8f4df-184">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f4df-184">Choose **Create**.</span></span>
12. <span data-ttu-id="8f4df-185">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f4df-185">Choose **Next**.</span></span>
13. <span data-ttu-id="8f4df-186">この機密情報の種類に対して、**推奨される信頼度レベル** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f4df-186">Choose the **recommended confidence level** for this sensitive information type.</span></span>
14. <span data-ttu-id="8f4df-187">設定を確認し、**[送信]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f4df-187">Check your setting and choose **Submit**.</span></span>

<span data-ttu-id="8f4df-188">PowerShell および Exact Data Match の機能を使用して、カスタムの機密情報の種類を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="8f4df-188">You can also create custom sensitive information types by using PowerShell and Exact Data Match capabilities.</span></span> <span data-ttu-id="8f4df-189">これらの方法の詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f4df-189">To learn more about those methods, see:</span></span>
- [<span data-ttu-id="8f4df-190">セキュリティ/コンプライアンス センター PowerShell でカスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="8f4df-190">Create a custom sensitive information type in Security & Compliance Center PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [<span data-ttu-id="8f4df-191">Exact Data Match (EMD) を使用して、DPL 向けのカスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="8f4df-191">Create a custom sensitive information type for DLP with Exact Data Match (EDM)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
 
> [!NOTE]
> <span data-ttu-id="8f4df-192">Microsoft 365 Information Protection は、次のような場合に 2 バイト文字セットの言語をプレビューでサポートします。</span><span class="sxs-lookup"><span data-stu-id="8f4df-192">Microsoft 365 Information Protection supports, in preview, double byte character set languages for:</span></span>
> - <span data-ttu-id="8f4df-193">中国語 (簡体字)</span><span class="sxs-lookup"><span data-stu-id="8f4df-193">Chinese (simplified)</span></span>
> - <span data-ttu-id="8f4df-194">中国語 (繁体字)</span><span class="sxs-lookup"><span data-stu-id="8f4df-194">Chinese (traditional)</span></span>
> - <span data-ttu-id="8f4df-195">韓国語</span><span class="sxs-lookup"><span data-stu-id="8f4df-195">Korean</span></span>
> - <span data-ttu-id="8f4df-196">日本語</span><span class="sxs-lookup"><span data-stu-id="8f4df-196">Japanese</span></span>
>
><span data-ttu-id="8f4df-197">このサポートは、機密情報の種類で使用できます。</span><span class="sxs-lookup"><span data-stu-id="8f4df-197">This support is available for sensitive information types.</span></span> <span data-ttu-id="8f4df-198">詳細については、「[2バイト文字セットのリリースノート (preview) についての情報保護サポー](mip-dbcs-relnotes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f4df-198">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>