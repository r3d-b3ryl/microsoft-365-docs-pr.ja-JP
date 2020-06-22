---
title: セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を作成する
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
ms.openlocfilehash: f702582a0e2c53b0846cd0586295d9bbea657e3c
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818066"
---
<!-- rename md file to match the display name -->
# <a name="create-a-custom-sensitive-information-type-in-the-security--compliance-center"></a><span data-ttu-id="8d024-103">セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="8d024-103">Create a custom sensitive information type in the Security & Compliance Center</span></span>

<span data-ttu-id="8d024-104">セキュリティ/コンプライアンス センターで[カスタムの機密情報の種類](custom-sensitive-info-types.md)を作成するために、この記事をお読みください(「[https://protection.office.com](https://protection.office.com)」)。</span><span class="sxs-lookup"><span data-stu-id="8d024-104">Read this article to create a [custom sensitive information type](custom-sensitive-info-types.md) in the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span> <span data-ttu-id="8d024-105">この方法を使用して作成されるカスタムの機密情報の種類は、`Microsoft.SCCManaged.CustomRulePack`という名前のルール パッケージに追加されます。</span><span class="sxs-lookup"><span data-stu-id="8d024-105">The custom sensitive information types that you create by using this method are added to the rule package named `Microsoft.SCCManaged.CustomRulePack`.</span></span>

<span data-ttu-id="8d024-106">PowerShell および Exact Data Match の機能を使用して、カスタムの機密情報の種類を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="8d024-106">You can also create custom sensitive information types by using PowerShell and Exact Data Match capabilities.</span></span> <span data-ttu-id="8d024-107">これらの方法の詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d024-107">To learn more about those methods, see:</span></span>
- [<span data-ttu-id="8d024-108">セキュリティ/コンプライアンス センター PowerShell でカスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="8d024-108">Create a custom sensitive information type in Security & Compliance Center PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [<span data-ttu-id="8d024-109">Exact Data Match (EMD) を使用して、DPL 向けのカスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="8d024-109">Create a custom sensitive information type for DLP with Exact Data Match (EDM)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

## <a name="before-you-begin"></a><span data-ttu-id="8d024-110">はじめに</span><span class="sxs-lookup"><span data-stu-id="8d024-110">Before you begin</span></span>

> [!NOTE]
> <span data-ttu-id="8d024-111">UI を使用してカスタムの機密情報の種類を作成、テスト、展開するには、グローバル管理者またはコンプライアンス管理者のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="8d024-111">You should have Global admin or Compliance admin permissions to create, test, and deploy a custom sensitive information type through the UI.</span></span> <span data-ttu-id="8d024-112">Office 365 で「[管理者ロールについて](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d024-112">See [About admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide) in Office 365.</span></span>

- <span data-ttu-id="8d024-113">組織には、データ損失防止 (DLP) を含む Office 365 Enterprise などのサブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="8d024-113">Your organization must have a subscription, such as Office 365 Enterprise, that includes Data Loss Prevention (DLP).</span></span> <span data-ttu-id="8d024-114">[メッセージング ポリシーとコンプライアンス サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d024-114">See [Messaging Policy and Compliance ServiceDescription](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc).</span></span> 

- <span data-ttu-id="8d024-115">Custom sensitive information types require familiarity with regular expressions (RegEx).</span><span class="sxs-lookup"><span data-stu-id="8d024-115">Custom sensitive information types require familiarity with regular expressions (RegEx).</span></span> <span data-ttu-id="8d024-116">For more information about the Boost.RegEx (formerly known as RegEx++) engine that's used for processing the text, see [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).</span><span class="sxs-lookup"><span data-stu-id="8d024-116">For more information about the Boost.RegEx (formerly known as RegEx++) engine that's used for processing the text, see [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).</span></span>

  <span data-ttu-id="8d024-117">Microsoft カスタマー サービス/サポートでは、カスタム分類または正規表現パターンの作成をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="8d024-117">Microsoft Customer Service & Support can't assist with creating custom classifications or regular expression patterns.</span></span> <span data-ttu-id="8d024-118">サポート エンジニアは、たとえば、テスト目的のサンプルの正規表現パターンを提供したり、期待通りにトリガーされない既存の正規表現パターンのトラブルシューティングをサポートしたりなど、機能に対する限定的なサポートを提供しますが、カスタムのコンテンツ一致の開発でユーザーの要件を満たしたり、義務を果たしたりすることを確約するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="8d024-118">Support engineers can provide limited support for the feature, such as, providing sample regular expression patterns for testing purposes, or assisting with troubleshooting an existing regular expression pattern that's not triggering as expected, but can't provide assurances that any custom content-matching development will fulfill your requirements or obligations.</span></span>

- <span data-ttu-id="8d024-119">DLP では、検索クローラーを使用して、SharePoint Online および OneDrive for Business のサイトの機密情報を特定して分類します。</span><span class="sxs-lookup"><span data-stu-id="8d024-119">DLP uses the search crawler to identify and classify sensitive information in SharePoint Online and OneDrive for Business sites.</span></span> <span data-ttu-id="8d024-120">既存のコンテンツで新しいカスタムの機密情報の種類を特定するには、そのコンテンツを再クロールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d024-120">To identify your new custom sensitive information type in existing content, the content must be re-crawled.</span></span> <span data-ttu-id="8d024-121">コンテンツは、スケジュールに基づいてクロールされますが、サイト コレクション、リスト、またはライブラリのコンテンツを手動で再クロールすることができます。</span><span class="sxs-lookup"><span data-stu-id="8d024-121">Content is crawled based on a schedule, but you can manually re-crawl content for a site collection, list, or library.</span></span> <span data-ttu-id="8d024-122">詳細については、「[サイト、ライブラリ、またはリストのクロールおよび再インデックスの手動要求](https://docs.microsoft.com/sharepoint/crawl-site-content)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d024-122">For more information, see [Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/sharepoint/crawl-site-content).</span></span>

## <a name="create-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="8d024-123">セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="8d024-123">Create custom sensitive information types in the Security & Compliance Center</span></span>

<span data-ttu-id="8d024-124">セキュリティ/コンプライアンス センターで、**[分類]** \> **[機密情報の種類]** に移動して **[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d024-124">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and click **Create**.</span></span>

<span data-ttu-id="8d024-125">各設定については説明するまでもありませんが、ウィザードの関連ページには説明が記載されています。</span><span class="sxs-lookup"><span data-stu-id="8d024-125">The settings are fairly self-evident, and are explained on the associate page of the wizard:</span></span>

- <span data-ttu-id="8d024-126">**[名前]**</span><span class="sxs-lookup"><span data-stu-id="8d024-126">**Name**</span></span>

- <span data-ttu-id="8d024-127">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="8d024-127">**Description**</span></span>

- <span data-ttu-id="8d024-128">**[近接性]**</span><span class="sxs-lookup"><span data-stu-id="8d024-128">**Proximity**</span></span>

- <span data-ttu-id="8d024-129">**[信頼度]**</span><span class="sxs-lookup"><span data-stu-id="8d024-129">**Confidence level**</span></span>

- <span data-ttu-id="8d024-130">**[プライマリ パターン要素]** (キーワード、正規表現、またはディクショナリ)</span><span class="sxs-lookup"><span data-stu-id="8d024-130">**Primary pattern element** (keywords, regular expression, or dictionary)</span></span>

- <span data-ttu-id="8d024-131">オプションの **[補強パターン要素]** (キーワード、正規表現、またはディクショナリ) および対応する **[最小コスト]** 値。</span><span class="sxs-lookup"><span data-stu-id="8d024-131">Optional **Supporting pattern elements** (keywords, regular expression, or dictionary) and a corresponding **Minimum cost** value.</span></span>

<span data-ttu-id="8d024-132">Here's a scenario: You want a custom sensitive information type that detects 9-digit employee numbers in content, along with the keywords "employee" "ID" and "badge".</span><span class="sxs-lookup"><span data-stu-id="8d024-132">Here's a scenario: You want a custom sensitive information type that detects 9-digit employee numbers in content, along with the keywords "employee" "ID" and "badge".</span></span> <span data-ttu-id="8d024-133">To create this custom sensitive information type, do the following steps:</span><span class="sxs-lookup"><span data-stu-id="8d024-133">To create this custom sensitive information type, do the following steps:</span></span>

1. <span data-ttu-id="8d024-134">セキュリティ/コンプライアンス センターで、**[分類]** \> **[機密情報の種類]** に移動して **[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d024-134">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and click **Create**.</span></span>

    ![機密情報の種類と [作成] ボタンの場所](../media/scc-cust-sens-info-type-new.png)

2. <span data-ttu-id="8d024-136">**[名前と説明の選択]** ページが開いたら、次の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="8d024-136">In the **Choose a name and description** page that opens, enter the following values:</span></span>

  - <span data-ttu-id="8d024-137">**[名前]**: 従業員 ID。</span><span class="sxs-lookup"><span data-stu-id="8d024-137">**Name**: Employee ID.</span></span>

  - <span data-ttu-id="8d024-138">**[説明]**: 9 桁の Contoso 従業員 ID 番号を検出します。</span><span class="sxs-lookup"><span data-stu-id="8d024-138">**Description**: Detect nine-digit Contoso employee ID numbers.</span></span>

    ![名前と説明のページ](../media/scc-cust-sens-info-type-new-name-desc.png)

    <span data-ttu-id="8d024-140">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d024-140">When you're finished, click **Next**.</span></span>

3. <span data-ttu-id="8d024-141">**[一致の要件]** ページが開いたら、**[要素の追加]** をクリックして、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="8d024-141">In the **Requirements for matching** page that opens, click **Add an element** configure the following settings:</span></span>

    - <span data-ttu-id="8d024-142">**次を含むコンテンツを検出する**:</span><span class="sxs-lookup"><span data-stu-id="8d024-142">**Detect content containing**:</span></span>
 
      <span data-ttu-id="8d024-143">a.</span><span class="sxs-lookup"><span data-stu-id="8d024-143">a.</span></span> <span data-ttu-id="8d024-144">Click **Any of these** and select **Regular expression**.</span><span class="sxs-lookup"><span data-stu-id="8d024-144">Click **Any of these** and select **Regular expression**.</span></span>

      <span data-ttu-id="8d024-145">b.</span><span class="sxs-lookup"><span data-stu-id="8d024-145">b.</span></span> <span data-ttu-id="8d024-146">In the regular expression box, enter `(\s)(\d{9})(\s)` (nine-digit numbers surrounded by white space).</span><span class="sxs-lookup"><span data-stu-id="8d024-146">In the regular expression box, enter `(\s)(\d{9})(\s)` (nine-digit numbers surrounded by white space).</span></span>
  
    - <span data-ttu-id="8d024-147">**[補強要素]**: **[補強要素の追加]** をクリックして、**[このキーワード リストを含める]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d024-147">**Supporting elements**: Click **Add supporting elements** and select **Contains this keyword list**.</span></span>

    - <span data-ttu-id="8d024-148">**[このキーワード リストを含める]** 領域が表示されたら、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="8d024-148">In the **Contains this keyword list** area that appears, configure the following settings:</span></span>

      - <span data-ttu-id="8d024-149">**[キーワード リスト]**: 次の値を入力します: 従業員、ID、社員証。</span><span class="sxs-lookup"><span data-stu-id="8d024-149">**Keyword list**: Enter the following value: employee,ID,badge.</span></span>

      - <span data-ttu-id="8d024-150">**[最低数]**: 既定値 1 のままにします。</span><span class="sxs-lookup"><span data-stu-id="8d024-150">**Minimum count**: Leave the default value 1.</span></span>

    - <span data-ttu-id="8d024-151">既定の **[信頼度]** 値 60 のままにします。</span><span class="sxs-lookup"><span data-stu-id="8d024-151">Leave the default **Confidence level** value 60.</span></span> 

    - <span data-ttu-id="8d024-152">既定の **[文字の近接]** 値 300 のままにします。</span><span class="sxs-lookup"><span data-stu-id="8d024-152">Leave the default **Character proximity** value 300.</span></span>

    ![[一致の要件] ページ](../media/scc-cust-sens-info-type-new-reqs.png)

    <span data-ttu-id="8d024-154">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d024-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="8d024-155">**[確認と最終処理]** ページが開いたら、設定を確認して **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d024-155">On the **Review and finalize** page that opens, review the settings and click **Finish**.</span></span>

    ![[確認と最終処理] ページ](../media/scc-cust-sens-info-type-new-review.png)

5. <span data-ttu-id="8d024-157">The next page encourages you to test the new custom sensitive information type by clicking **Yes**.</span><span class="sxs-lookup"><span data-stu-id="8d024-157">The next page encourages you to test the new custom sensitive information type by clicking **Yes**.</span></span> <span data-ttu-id="8d024-158">For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="8d024-158">For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span> <span data-ttu-id="8d024-159">To test the rule later, click **No**.</span><span class="sxs-lookup"><span data-stu-id="8d024-159">To test the rule later, click **No**.</span></span>

    ![推奨をテストするページ](../media/scc-cust-sens-info-type-new-test.png)

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="8d024-161">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="8d024-161">How do you know this worked?</span></span>

<span data-ttu-id="8d024-162">新しい機密情報の種類が正常に作成されたことを確認するには、次に示す手順のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="8d024-162">To verify that you've successfully created a new sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="8d024-163">**[分類]** \> **[機密情報の種類]** に移動して、新しいカスタムの機密情報の種類が一覧に表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8d024-163">Go to **Classifications** \> **Sensitive info types** and verify the new custom sensitive information type is listed.</span></span>

  - <span data-ttu-id="8d024-164">Test the new custom sensitive information type.</span><span class="sxs-lookup"><span data-stu-id="8d024-164">Test the new custom sensitive information type.</span></span> <span data-ttu-id="8d024-165">For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="8d024-165">For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

## <a name="modify-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="8d024-166">セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を変更する</span><span class="sxs-lookup"><span data-stu-id="8d024-166">Modify custom sensitive information types in the Security & Compliance Center</span></span>

<span data-ttu-id="8d024-167">**注**:</span><span class="sxs-lookup"><span data-stu-id="8d024-167">**Notes**:</span></span>
<!-- check to see if this note contradicts the guidance in "customize a built in sensitive information type customize-a-built-in-sensitive-information-type it sure seems like it does-->
- <span data-ttu-id="8d024-168">You can only modify custom sensitive information types; you can't modify built-in sensitive information types.</span><span class="sxs-lookup"><span data-stu-id="8d024-168">You can only modify custom sensitive information types; you can't modify built-in sensitive information types.</span></span> <span data-ttu-id="8d024-169">But you can use PowerShell to export built-in custom sensitive information types, customize them, and import them as custom sensitive information types.</span><span class="sxs-lookup"><span data-stu-id="8d024-169">But you can use PowerShell to export built-in custom sensitive information types, customize them, and import them as custom sensitive information types.</span></span> <span data-ttu-id="8d024-170">For more information, see [Customize a built-in sensitive information type](customize-a-built-in-sensitive-information-type.md).</span><span class="sxs-lookup"><span data-stu-id="8d024-170">For more information, see [Customize a built-in sensitive information type](customize-a-built-in-sensitive-information-type.md).</span></span>

- <span data-ttu-id="8d024-171">You can only modify custom sensitive information types that you created in the UI.</span><span class="sxs-lookup"><span data-stu-id="8d024-171">You can only modify custom sensitive information types that you created in the UI.</span></span> <span data-ttu-id="8d024-172">If you used the [PowerShell procedure](create-a-custom-sensitive-information-type-in-scc-powershell.md) to import a custom sensitive information type rule package, you'll get an error.</span><span class="sxs-lookup"><span data-stu-id="8d024-172">If you used the [PowerShell procedure](create-a-custom-sensitive-information-type-in-scc-powershell.md) to import a custom sensitive information type rule package, you'll get an error.</span></span>

<span data-ttu-id="8d024-173">セキュリティ/コンプライアンス センターで、**[分類]** \> **[機密情報の種類]** に移動して、変更するカスタムの機密情報の種類を選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d024-173">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types**, select the custom sensitive information type that you want to modify, and then click **Edit**.</span></span>

  ![機密情報の種類と [編集] ボタンの場所](../media/scc-cust-sens-info-type-edit.png)

<span data-ttu-id="8d024-175">The same options are available here as when you created the custom sensitive information type in the Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="8d024-175">The same options are available here as when you created the custom sensitive information type in the Security & Compliance Center.</span></span> <span data-ttu-id="8d024-176">For more information, see [Create custom sensitive information types in the Security & Compliance Center](#create-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="8d024-176">For more information, see [Create custom sensitive information types in the Security & Compliance Center](#create-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="8d024-177">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="8d024-177">How do you know this worked?</span></span>

<span data-ttu-id="8d024-178">機密情報の種類が正常に変更されたことを確認するには、次に示す手順のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="8d024-178">To verify that you've successfully modified a sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="8d024-179">**[分類]** \> **[機密情報の種類]** に移動して、変更したカスタムの機密情報の種類のプロパティを確認します。</span><span class="sxs-lookup"><span data-stu-id="8d024-179">Go to **Classifications** \> **Sensitive info types** to verify the properties of the modified custom sensitive information type.</span></span> 

  - <span data-ttu-id="8d024-180">Test the modified custom sensitive information type.</span><span class="sxs-lookup"><span data-stu-id="8d024-180">Test the modified custom sensitive information type.</span></span> <span data-ttu-id="8d024-181">For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="8d024-181">For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

## <a name="remove-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="8d024-182">セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を削除する</span><span class="sxs-lookup"><span data-stu-id="8d024-182">Remove custom sensitive information types in the Security & Compliance Center</span></span> 

<span data-ttu-id="8d024-183">**注**:</span><span class="sxs-lookup"><span data-stu-id="8d024-183">**Notes**:</span></span>

- <span data-ttu-id="8d024-184">カスタムの機密情報の種類のみを削除できます。組み込みの機密情報の種類は削除できません。</span><span class="sxs-lookup"><span data-stu-id="8d024-184">You can only remove custom sensitive information types; you can't remove built-in sensitive information types.</span></span>

- <span data-ttu-id="8d024-185">カスタムの機密情報の種類を削除する前に、その機密情報の種類を参照している DLP ポリシーまたは Exchange メール フロー ルール (別名: トランスポート ルール) がないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8d024-185">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

1. <span data-ttu-id="8d024-186">セキュリティ/コンプライアンス センターで、**[分類]** \> **[機密情報の種類]** に移動して、削除するカスタムの機密情報の種類を 1 つ以上選択します。</span><span class="sxs-lookup"><span data-stu-id="8d024-186">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and select one or more custom sensitive information types that you want to remove.</span></span>

2. <span data-ttu-id="8d024-187">ポップアップが開いたら、**[削除]** (複数選択した場合は **[機密情報の種類の削除]**) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d024-187">In the fly-out that opens, click **Delete** (or **Delete sensitive info types** if you selected more than one).</span></span>

    ![機密情報の種類と [削除] ボタンの場所](../media/scc-cust-sens-info-type-delete.png)

3. <span data-ttu-id="8d024-189">警告メッセージが表示されたら、**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d024-189">In the warning message that appears, click **Yes**.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="8d024-190">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="8d024-190">How do you know this worked?</span></span>

<span data-ttu-id="8d024-191">カスタムの機密情報の種類が正常に削除されたことを確認するには、**[分類]** \> **[機密情報の種類]** に移動して、そのカスタムの機密情報の種類が一覧に表示されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="8d024-191">To verify that you've successfully removed a custom sensitive information type, go to **Classifications** \> **Sensitive info types** to verify the custom sensitive information type is no longer listed.</span></span>

## <a name="test-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="8d024-192">セキュリティ/コンプライアンス センターでカスタムの機密情報の種類をテストする</span><span class="sxs-lookup"><span data-stu-id="8d024-192">Test custom sensitive information types in the Security & Compliance Center</span></span>

1. <span data-ttu-id="8d024-193">セキュリティ/コンプライアンス センターで、**[分類]** \> **[機密情報の種類]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="8d024-193">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types**.</span></span>

2. <span data-ttu-id="8d024-194">Select one or more custom sensitive information types to test.</span><span class="sxs-lookup"><span data-stu-id="8d024-194">Select one or more custom sensitive information types to test.</span></span> <span data-ttu-id="8d024-195">In the fly-out that opens, click **Test type** (or **Test sensitive info types** if you selected more than one).</span><span class="sxs-lookup"><span data-stu-id="8d024-195">In the fly-out that opens, click **Test type** (or **Test sensitive info types** if you selected more than one).</span></span>

    ![機密情報の種類と [種類のテスト] ボタンの場所](../media/scc-cust-sens-info-type-test.png)

3. <span data-ttu-id="8d024-197">[**テストの対象ファイルのアップロード**] ページが開いたら、ファイルをドラッグ アンド ドロップするか、または [**参照**] をクリックしてファイルを選択し、テストの対象ドキュメントをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="8d024-197">On the **Upload file to test** page that opens, upload a document to test by dragging and dropping a file or by clicking **Browse** and selecting a file.</span></span>

    ![[テストの対象ファイルのアップロード] ページ](../media/scc-cust-sens-info-type-test-upload.png)

4. <span data-ttu-id="8d024-199">**[テスト]** ボタンをクリックして、ファイル内のパターン マッチについてドキュメントをテストします。</span><span class="sxs-lookup"><span data-stu-id="8d024-199">Click the **Test** button to test the document for pattern matches in the file.</span></span>

5. <span data-ttu-id="8d024-200">[**照合結果**] ページで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d024-200">On the **Match results** page, click **Finish**.</span></span>

    ![照合結果](../media/scc-cust-sens-info-type-test-results.png)
