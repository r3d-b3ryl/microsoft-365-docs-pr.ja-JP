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
ms.openlocfilehash: 59d16ed662ff1b577bbb6c8388c5d27836832c1f
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681723"
---
<!-- rename md file to match the display name -->
# <a name="create-a-custom-sensitive-information-type-in-the-security--compliance-center"></a><span data-ttu-id="20c70-103">セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="20c70-103">Create a custom sensitive information type in the Security & Compliance Center</span></span>

<span data-ttu-id="20c70-104">セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を作成するために、この記事をお読みください([https://protection.office.com](https://protection.office.com))。</span><span class="sxs-lookup"><span data-stu-id="20c70-104">Read this article to create a custom sensitive information type in the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span> <span data-ttu-id="20c70-105">この方法を使用して作成されるカスタムの機密情報の種類は、`Microsoft.SCCManaged.CustomRulePack`という名前のルール パッケージに追加されます。</span><span class="sxs-lookup"><span data-stu-id="20c70-105">The custom sensitive information types that you create by using this method are added to the rule package named `Microsoft.SCCManaged.CustomRulePack`.</span></span>

<span data-ttu-id="20c70-106">PowerShell および Exact Data Match の機能を使用して、カスタムの機密情報の種類を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="20c70-106">You can also create custom sensitive information types by using PowerShell and Exact Data Match capabilities.</span></span> <span data-ttu-id="20c70-107">これらの方法の詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20c70-107">To learn more about those methods, see:</span></span>
- [<span data-ttu-id="20c70-108">セキュリティ/コンプライアンス センター PowerShell でカスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="20c70-108">Create a custom sensitive information type in Security & Compliance Center PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [<span data-ttu-id="20c70-109">Exact Data Match (EMD) を使用して、DPL 向けのカスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="20c70-109">Create a custom sensitive information type for DLP with Exact Data Match (EDM)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

> [!NOTE]
> <span data-ttu-id="20c70-110">Microsoft 365 の情報保護は、次のような場合に2バイト文字セットの言語をpreviewでサポートしています。</span><span class="sxs-lookup"><span data-stu-id="20c70-110">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="20c70-111">中国語 (簡体字)</span><span class="sxs-lookup"><span data-stu-id="20c70-111">Chinese (simplified)</span></span>
> - <span data-ttu-id="20c70-112">中国語 (繁体字)</span><span class="sxs-lookup"><span data-stu-id="20c70-112">Chinese (traditional)</span></span>
> - <span data-ttu-id="20c70-113">韓国語</span><span class="sxs-lookup"><span data-stu-id="20c70-113">Korean</span></span>
> - <span data-ttu-id="20c70-114">日本語</span><span class="sxs-lookup"><span data-stu-id="20c70-114">Japanese</span></span>
>
><span data-ttu-id="20c70-115">このサポートは、機密情報の種類で使用できます。</span><span class="sxs-lookup"><span data-stu-id="20c70-115">This support is available for sensitive information types.</span></span> <span data-ttu-id="20c70-116">詳細については、「[2バイト文字セットのリリースノート (preview) についての情報保護サポート](mip-dbcs-relnotes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20c70-116">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="20c70-117">はじめに</span><span class="sxs-lookup"><span data-stu-id="20c70-117">Before you begin</span></span>

> [!NOTE]
> <span data-ttu-id="20c70-118">UI を使用してカスタムの機密情報の種類を作成、テスト、展開するには、グローバル管理者またはコンプライアンス管理者のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="20c70-118">You should have Global admin or Compliance admin permissions to create, test, and deploy a custom sensitive information type through the UI.</span></span> <span data-ttu-id="20c70-119">Office 365 で「[管理者ロールについて](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20c70-119">See [About admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide) in Office 365.</span></span>

- <span data-ttu-id="20c70-120">組織には、データ損失防止 (DLP) を含む Office 365 Enterprise などのサブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="20c70-120">Your organization must have a subscription, such as Office 365 Enterprise, that includes Data Loss Prevention (DLP).</span></span> <span data-ttu-id="20c70-121">[メッセージング ポリシーとコンプライアンス サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20c70-121">See [Messaging Policy and Compliance ServiceDescription](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc).</span></span> 

- <span data-ttu-id="20c70-p106">カスタムの機密情報の種類では、正規表現 (RegEx) に精通している必要があります。テキストの処理に使用される Boost.RegEx (旧称 RegEx++) エンジンの詳細については、「[Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20c70-p106">Custom sensitive information types require familiarity with regular expressions (RegEx). For more information about the Boost.RegEx (formerly known as RegEx++) engine that's used for processing the text, see [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).</span></span>

  <span data-ttu-id="20c70-124">Microsoft カスタマー サービス/サポートでは、カスタム分類または正規表現パターンの作成をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="20c70-124">Microsoft Customer Service & Support can't assist with creating custom classifications or regular expression patterns.</span></span> <span data-ttu-id="20c70-125">サポート エンジニアは、たとえば、テスト目的のサンプルの正規表現パターンを提供したり、期待通りにトリガーされない既存の正規表現パターンのトラブルシューティングをサポートしたりなど、機能に対する限定的なサポートを提供しますが、カスタムのコンテンツ一致の開発でユーザーの要件を満たしたり、義務を果たしたりすることを確約するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="20c70-125">Support engineers can provide limited support for the feature, such as, providing sample regular expression patterns for testing purposes, or assisting with troubleshooting an existing regular expression pattern that's not triggering as expected, but can't provide assurances that any custom content-matching development will fulfill your requirements or obligations.</span></span>

- <span data-ttu-id="20c70-126">DLP では、検索クローラーを使用して、SharePoint Online および OneDrive for Business のサイトの機密情報を特定して分類します。</span><span class="sxs-lookup"><span data-stu-id="20c70-126">DLP uses the search crawler to identify and classify sensitive information in SharePoint Online and OneDrive for Business sites.</span></span> <span data-ttu-id="20c70-127">既存のコンテンツで新しいカスタムの機密情報の種類を特定するには、そのコンテンツを再クロールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="20c70-127">To identify your new custom sensitive information type in existing content, the content must be re-crawled.</span></span> <span data-ttu-id="20c70-128">コンテンツは、スケジュールに基づいてクロールされますが、サイト コレクション、リスト、またはライブラリのコンテンツを手動で再クロールすることができます。</span><span class="sxs-lookup"><span data-stu-id="20c70-128">Content is crawled based on a schedule, but you can manually re-crawl content for a site collection, list, or library.</span></span> <span data-ttu-id="20c70-129">詳細については、「[サイト、ライブラリ、またはリストのクロールおよび再インデックスの手動要求](https://docs.microsoft.com/sharepoint/crawl-site-content)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20c70-129">For more information, see [Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/sharepoint/crawl-site-content).</span></span>

## <a name="create-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="20c70-130">セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="20c70-130">Create custom sensitive information types in the Security & Compliance Center</span></span>

<span data-ttu-id="20c70-131">セキュリティ/コンプライアンス センターで、**[分類]** \> **[機密情報の種類]** に移動して **[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20c70-131">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and click **Create**.</span></span>

<span data-ttu-id="20c70-132">各設定については説明するまでもありませんが、ウィザードの関連ページには説明が記載されています。</span><span class="sxs-lookup"><span data-stu-id="20c70-132">The settings are fairly self-evident, and are explained on the associate page of the wizard:</span></span>

- <span data-ttu-id="20c70-133">**[名前]**</span><span class="sxs-lookup"><span data-stu-id="20c70-133">**Name**</span></span>

- <span data-ttu-id="20c70-134">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="20c70-134">**Description**</span></span>

- <span data-ttu-id="20c70-135">**[近接性]**</span><span class="sxs-lookup"><span data-stu-id="20c70-135">**Proximity**</span></span>

- <span data-ttu-id="20c70-136">**[信頼度]**</span><span class="sxs-lookup"><span data-stu-id="20c70-136">**Confidence level**</span></span>

- <span data-ttu-id="20c70-137">**[プライマリ パターン要素]** (キーワード、正規表現、またはディクショナリ)</span><span class="sxs-lookup"><span data-stu-id="20c70-137">**Primary pattern element** (keywords, regular expression, or dictionary)</span></span>

- <span data-ttu-id="20c70-138">オプションの **[補強パターン要素]** (キーワード、正規表現、またはディクショナリ) および対応する **[最小コスト]** 値。</span><span class="sxs-lookup"><span data-stu-id="20c70-138">Optional **Supporting pattern elements** (keywords, regular expression, or dictionary) and a corresponding **Minimum cost** value.</span></span>

<span data-ttu-id="20c70-p109">この例のシナリオ: キーワードの「従業員」、「ID」および「社員証」と共に、コンテンツに含まれる 9 桁の従業員番号を検出するために、カスタムの機密情報の種類が必要になりました。このカスタムの機密情報の種類を作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="20c70-p109">Here's a scenario: You want a custom sensitive information type that detects 9-digit employee numbers in content, along with the keywords "employee" "ID" and "badge". To create this custom sensitive information type, do the following steps:</span></span>

1. <span data-ttu-id="20c70-141">セキュリティ/コンプライアンス センターで、**[分類]** \> **[機密情報の種類]** に移動して **[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20c70-141">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and click **Create**.</span></span>

    ![機密情報の種類と [作成] ボタンの場所](../media/scc-cust-sens-info-type-new.png)

2. <span data-ttu-id="20c70-143">**[名前と説明の選択]** ページが開いたら、次の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="20c70-143">In the **Choose a name and description** page that opens, enter the following values:</span></span>

  - <span data-ttu-id="20c70-144">**[名前]**: 従業員 ID。</span><span class="sxs-lookup"><span data-stu-id="20c70-144">**Name**: Employee ID.</span></span>

  - <span data-ttu-id="20c70-145">**[説明]**: 9 桁の Contoso 従業員 ID 番号を検出します。</span><span class="sxs-lookup"><span data-stu-id="20c70-145">**Description**: Detect nine-digit Contoso employee ID numbers.</span></span>

    ![名前と説明のページ](../media/scc-cust-sens-info-type-new-name-desc.png)

    <span data-ttu-id="20c70-147">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20c70-147">When you're finished, click **Next**.</span></span>

3. <span data-ttu-id="20c70-148">**[一致の要件]** ページが開いたら、**[要素の追加]** をクリックして、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="20c70-148">In the **Requirements for matching** page that opens, click **Add an element** configure the following settings:</span></span>

    - <span data-ttu-id="20c70-149">**次を含むコンテンツを検出する**:</span><span class="sxs-lookup"><span data-stu-id="20c70-149">**Detect content containing**:</span></span>
 
      <span data-ttu-id="20c70-p110">a. **[これらのいずれか]** をクリックして、**[正規表現]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="20c70-p110">a. Click **Any of these** and select **Regular expression**.</span></span>

      <span data-ttu-id="20c70-p111">b. 正規表現ボックスに、`(\s)(\d{9})(\s)` (空白文字で囲まれた 9 桁の数字) を入力します。</span><span class="sxs-lookup"><span data-stu-id="20c70-p111">b. In the regular expression box, enter `(\s)(\d{9})(\s)` (nine-digit numbers surrounded by white space).</span></span>
  
    - <span data-ttu-id="20c70-154">**[補強要素]**: **[補強要素の追加]** をクリックして、**[このキーワード リストを含める]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="20c70-154">**Supporting elements**: Click **Add supporting elements** and select **Contains this keyword list**.</span></span>

    - <span data-ttu-id="20c70-155">**[このキーワード リストを含める]** 領域が表示されたら、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="20c70-155">In the **Contains this keyword list** area that appears, configure the following settings:</span></span>

      - <span data-ttu-id="20c70-156">**[キーワード リスト]**: 次の値を入力します: 従業員、ID、社員証。</span><span class="sxs-lookup"><span data-stu-id="20c70-156">**Keyword list**: Enter the following value: employee,ID,badge.</span></span>

      - <span data-ttu-id="20c70-157">**[最低数]**: 既定値 1 のままにします。</span><span class="sxs-lookup"><span data-stu-id="20c70-157">**Minimum count**: Leave the default value 1.</span></span>

    - <span data-ttu-id="20c70-158">既定の **[信頼度]** 値 60 のままにします。</span><span class="sxs-lookup"><span data-stu-id="20c70-158">Leave the default **Confidence level** value 60.</span></span> 

    - <span data-ttu-id="20c70-159">既定の **[文字の近接]** 値 300 のままにします。</span><span class="sxs-lookup"><span data-stu-id="20c70-159">Leave the default **Character proximity** value 300.</span></span>

    ![[一致の要件] ページ](../media/scc-cust-sens-info-type-new-reqs.png)

    <span data-ttu-id="20c70-161">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20c70-161">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="20c70-162">**[確認と最終処理]** ページが開いたら、設定を確認して **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20c70-162">On the **Review and finalize** page that opens, review the settings and click **Finish**.</span></span>

    ![[確認と最終処理] ページ](../media/scc-cust-sens-info-type-new-review.png)

5. <span data-ttu-id="20c70-p112">次のページでは、[**はい**] をクリックして新しいカスタムの機密情報の種類をテストするように促されます。詳細については、「[セキュリティ/コンプライアンス センターでカスタムの機密情報の種類をテストする](#test-custom-sensitive-information-types-in-the-security--compliance-center)」を参照してください。ルールのテストを後で行うには、[**いいえ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20c70-p112">The next page encourages you to test the new custom sensitive information type by clicking **Yes**. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center). To test the rule later, click **No**.</span></span>

    ![推奨をテストするページ](../media/scc-cust-sens-info-type-new-test.png)

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="20c70-168">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="20c70-168">How do you know this worked?</span></span>

<span data-ttu-id="20c70-169">新しい機密情報の種類が正常に作成されたことを確認するには、次に示す手順のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="20c70-169">To verify that you've successfully created a new sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="20c70-170">**[分類]** \> **[機密情報の種類]** に移動して、新しいカスタムの機密情報の種類が一覧に表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="20c70-170">Go to **Classifications** \> **Sensitive info types** and verify the new custom sensitive information type is listed.</span></span>

  - <span data-ttu-id="20c70-p113">新しいカスタムの機密情報の種類をテストします。詳細については、「[セキュリティ/コンプライアンス センターでカスタムの機密情報の種類をテストする](#test-custom-sensitive-information-types-in-the-security--compliance-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20c70-p113">Test the new custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

## <a name="modify-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="20c70-173">セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を変更する</span><span class="sxs-lookup"><span data-stu-id="20c70-173">Modify custom sensitive information types in the Security & Compliance Center</span></span>

<span data-ttu-id="20c70-174">**注**:</span><span class="sxs-lookup"><span data-stu-id="20c70-174">**Notes**:</span></span>
<!-- check to see if this note contradicts the guidance in "customize a built in sensitive information type customize-a-built-in-sensitive-information-type it sure seems like it does-->
- <span data-ttu-id="20c70-p114">カスタムの機密情報の種類のみを変更できます。組み込みの機密情報の種類は変更できません。ただし、PowerShell を使用して組み込みの機密情報の種類をエクスポートし、エクスポートしたものをカスタムの機密情報の種類としてインポートすることができます。詳細については、「[組み込みの機密情報の種類をカスタマイズする](customize-a-built-in-sensitive-information-type.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20c70-p114">You can only modify custom sensitive information types; you can't modify built-in sensitive information types. But you can use PowerShell to export built-in custom sensitive information types, customize them, and import them as custom sensitive information types. For more information, see [Customize a built-in sensitive information type](customize-a-built-in-sensitive-information-type.md).</span></span>

- <span data-ttu-id="20c70-p115">変更できるのは、UI で作成したカスタムの機密情報の種類のみです。カスタムの機密情報の種類のルール パッケージをインポートするのに [PowerShell プロシージャ](create-a-custom-sensitive-information-type-in-scc-powershell.md)を使用した場合、エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="20c70-p115">You can only modify custom sensitive information types that you created in the UI. If you used the [PowerShell procedure](create-a-custom-sensitive-information-type-in-scc-powershell.md) to import a custom sensitive information type rule package, you'll get an error.</span></span>

<span data-ttu-id="20c70-180">セキュリティ/コンプライアンス センターで、**[分類]** \> **[機密情報の種類]** に移動して、変更するカスタムの機密情報の種類を選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20c70-180">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types**, select the custom sensitive information type that you want to modify, and then click **Edit**.</span></span>

  ![機密情報の種類と [編集] ボタンの場所](../media/scc-cust-sens-info-type-edit.png)

<span data-ttu-id="20c70-p116">ここでは、セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を作成したときと同じオプションを選択できます。詳細については、「[セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を作成する](#create-custom-sensitive-information-types-in-the-security--compliance-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20c70-p116">The same options are available here as when you created the custom sensitive information type in the Security & Compliance Center. For more information, see [Create custom sensitive information types in the Security & Compliance Center](#create-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="20c70-184">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="20c70-184">How do you know this worked?</span></span>

<span data-ttu-id="20c70-185">機密情報の種類が正常に変更されたことを確認するには、次に示す手順のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="20c70-185">To verify that you've successfully modified a sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="20c70-186">**[分類]** \> **[機密情報の種類]** に移動して、変更したカスタムの機密情報の種類のプロパティを確認します。</span><span class="sxs-lookup"><span data-stu-id="20c70-186">Go to **Classifications** \> **Sensitive info types** to verify the properties of the modified custom sensitive information type.</span></span> 

  - <span data-ttu-id="20c70-p117">変更したカスタムの機密情報の種類をテストします。詳細については、「[セキュリティ/コンプライアンス センターでカスタムの機密情報の種類をテストする](#test-custom-sensitive-information-types-in-the-security--compliance-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20c70-p117">Test the modified custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

## <a name="remove-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="20c70-189">セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を削除する</span><span class="sxs-lookup"><span data-stu-id="20c70-189">Remove custom sensitive information types in the Security & Compliance Center</span></span> 

<span data-ttu-id="20c70-190">**注**:</span><span class="sxs-lookup"><span data-stu-id="20c70-190">**Notes**:</span></span>

- <span data-ttu-id="20c70-191">カスタムの機密情報の種類のみを削除できます。組み込みの機密情報の種類は削除できません。</span><span class="sxs-lookup"><span data-stu-id="20c70-191">You can only remove custom sensitive information types; you can't remove built-in sensitive information types.</span></span>

- <span data-ttu-id="20c70-192">カスタムの機密情報の種類を削除する前に、その機密情報の種類を参照している DLP ポリシーまたは Exchange メール フロー ルール (別名: トランスポート ルール) がないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="20c70-192">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

1. <span data-ttu-id="20c70-193">セキュリティ/コンプライアンス センターで、**[分類]** \> **[機密情報の種類]** に移動して、削除するカスタムの機密情報の種類を 1 つ以上選択します。</span><span class="sxs-lookup"><span data-stu-id="20c70-193">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and select one or more custom sensitive information types that you want to remove.</span></span>

2. <span data-ttu-id="20c70-194">ポップアップが開いたら、**[削除]** (複数選択した場合は **[機密情報の種類の削除]**) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20c70-194">In the fly-out that opens, click **Delete** (or **Delete sensitive info types** if you selected more than one).</span></span>

    ![機密情報の種類と [削除] ボタンの場所](../media/scc-cust-sens-info-type-delete.png)

3. <span data-ttu-id="20c70-196">警告メッセージが表示されたら、**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20c70-196">In the warning message that appears, click **Yes**.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="20c70-197">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="20c70-197">How do you know this worked?</span></span>

<span data-ttu-id="20c70-198">カスタムの機密情報の種類が正常に削除されたことを確認するには、**[分類]** \> **[機密情報の種類]** に移動して、そのカスタムの機密情報の種類が一覧に表示されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="20c70-198">To verify that you've successfully removed a custom sensitive information type, go to **Classifications** \> **Sensitive info types** to verify the custom sensitive information type is no longer listed.</span></span>

## <a name="test-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="20c70-199">セキュリティ/コンプライアンス センターでカスタムの機密情報の種類をテストする</span><span class="sxs-lookup"><span data-stu-id="20c70-199">Test custom sensitive information types in the Security & Compliance Center</span></span>

1. <span data-ttu-id="20c70-200">セキュリティ/コンプライアンス センターで、**[分類]** \> **[機密情報の種類]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="20c70-200">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types**.</span></span>

2. <span data-ttu-id="20c70-p118">テストするカスタムの機密情報の種類を 1 つ以上選択します。ポップアップが開いたら、**[種類のテスト]** (複数選択した場合は **[機密情報の種類のテスト]**) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20c70-p118">Select one or more custom sensitive information types to test. In the fly-out that opens, click **Test type** (or **Test sensitive info types** if you selected more than one).</span></span>

    ![機密情報の種類と [種類のテスト] ボタンの場所](../media/scc-cust-sens-info-type-test.png)

3. <span data-ttu-id="20c70-204">[**テストの対象ファイルのアップロード**] ページが開いたら、ファイルをドラッグ アンド ドロップするか、または [**参照**] をクリックしてファイルを選択し、テストの対象ドキュメントをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="20c70-204">On the **Upload file to test** page that opens, upload a document to test by dragging and dropping a file or by clicking **Browse** and selecting a file.</span></span>

    ![[テストの対象ファイルのアップロード] ページ](../media/scc-cust-sens-info-type-test-upload.png)

4. <span data-ttu-id="20c70-206">**[テスト]** ボタンをクリックして、ファイル内のパターン マッチについてドキュメントをテストします。</span><span class="sxs-lookup"><span data-stu-id="20c70-206">Click the **Test** button to test the document for pattern matches in the file.</span></span>

5. <span data-ttu-id="20c70-207">[**照合結果**] ページで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20c70-207">On the **Match results** page, click **Finish**.</span></span>

    ![照合結果](../media/scc-cust-sens-info-type-test-results.png)
