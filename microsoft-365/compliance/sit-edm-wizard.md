---
title: 完全一致スキーマと機密情報の種類ウィザードを使用する
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 完全一致スキーマと機密情報の種類ウィザードrを使用する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d9d6f870239b963ee7483b9f08e93e40b10f4f0b
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878006"
---
# <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a><span data-ttu-id="41411-103">完全一致スキーマと機密情報の種類ウィザードを使用する</span><span class="sxs-lookup"><span data-stu-id="41411-103">Use the Exact Data Match Schema and Sensitive Information Type Wizard</span></span>

<span data-ttu-id="41411-104">[完全一致 (EDM) ベースの分類を使用してカスタムの機密情報の種類を作成するには](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)、さまざまな手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="41411-104">[Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)  involves many steps.</span></span>  <span data-ttu-id="41411-105">このウィザードを使用すると、スキーマおよび機密情報の種類 (SIT) パターン (ルール パッケージ) ファイルを作成して、プロセスを簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="41411-105">You can use this wizard to create your schema and sensitive information type (SIT) pattern (rule package) files to help simplify the process.</span></span>

> [!NOTE]
> <span data-ttu-id="41411-106">完全一致スキーマと機密情報の種類ウィザードは、World Wide クラウドと GCC クラウドでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="41411-106">The Exact Data Match Schema and Sensitive Information Type Wizard is only available for the World Wide and GCC clouds only.</span></span>

<span data-ttu-id="41411-107">このウィザードが代わりとなるのは、次のような場合です。</span><span class="sxs-lookup"><span data-stu-id="41411-107">This wizard can be used instead of the:</span></span>

- [<span data-ttu-id="41411-108">機密情報のデータベースのスキーマを定義する</span><span class="sxs-lookup"><span data-stu-id="41411-108">Define the schema for your database of sensitive information</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#define-the-schema-for-your-database-of-sensitive-information)
- [<span data-ttu-id="41411-109">パターンを設定する (ルール パッケージ)</span><span class="sxs-lookup"><span data-stu-id="41411-109">Set up a pattern (rule package)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#set-up-a-rule-package)

<span data-ttu-id="41411-110">手順 [パート 1: EDM ベースの分類をセットアップする](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification)。</span><span class="sxs-lookup"><span data-stu-id="41411-110">steps in [Part 1: Set up EDM-based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="41411-111">前提条件.</span><span class="sxs-lookup"><span data-stu-id="41411-111">Pre-requisites</span></span>

1. <span data-ttu-id="41411-112">EDM [ワーク フローの概要](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance)で、カスタムの機密情報の種類を作成する手順がわかります。</span><span class="sxs-lookup"><span data-stu-id="41411-112">Familiarize yourself with the steps to create a custom sensitive information type with EDM [work flow at a glance](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance).</span></span>

2. <span data-ttu-id="41411-113">「機密データをファイル形式または [.tsv 形式.csv保存する」の手順を実行します](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-or-tsv-format)。</span><span class="sxs-lookup"><span data-stu-id="41411-113">Perform the steps in [Save sensitive data in .csv or .tsv format](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-or-tsv-format).</span></span>

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a><span data-ttu-id="41411-114">完全一致スキーマと機密情報の種類パターンウィザードを使用する</span><span class="sxs-lookup"><span data-stu-id="41411-114">Use the exact data match schema and sensitive information type pattern wizard</span></span>

1. <span data-ttu-id="41411-115">テナントの Microsoft 365 コンプライアンス センターでは、**データの分類** > **完全一致** に移動します。 </span><span class="sxs-lookup"><span data-stu-id="41411-115">In the Microsoft 365 Compliance center for your tenant go to **Data classification** > **Exact data matches**.</span></span>

2. <span data-ttu-id="41411-116">**EDM スキーマを作成** を選択して、スキーマ ウィザードの構成 ポップアップを開きます。</span><span class="sxs-lookup"><span data-stu-id="41411-116">Choose **Create EDM schema** to open the schema wizard configuration flyout.</span></span>

![EDM スキーマ作成ウィザードの設定ポップアップ](../media/edm-schema-wizard-1.png)

3. <span data-ttu-id="41411-118">適切な **名前** と **説明** を入力します。</span><span class="sxs-lookup"><span data-stu-id="41411-118">Fill in an appropriate **Name** and **Description**.</span></span>

4. <span data-ttu-id="41411-119">その動作 **が必要な場合は、[** すべてのスキーマ フィールドの区切り記号と句読点を無視する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="41411-119">Choose **Ignore delimiters and punctuation for all schema fields** if you want that behavior.</span></span> <span data-ttu-id="41411-120">大文字と小文字または区切り記号を無視するように EDM を構成する方法の詳細については、「完全データ一致 [(EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)ベースの分類を使用してカスタム機密情報の種類を作成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41411-120">To learn more about configuring EDM to ignore case or delimiters, see [Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

5. <span data-ttu-id="41411-121">**スキーマ フィールド#1** 必要な値を入力し、必要に応じてフィールドを追加します。</span><span class="sxs-lookup"><span data-stu-id="41411-121">Fill in your desired values for your **Schema field #1** and add more fields as needed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="41411-122">1 つ以上 5 つ以下のスキーマ フィールド を検索可能として指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41411-122">At least one, but no more than five of your schema fields must be designated as searchable.</span></span>

6. <span data-ttu-id="41411-123">[保存] を選択します。</span><span class="sxs-lookup"><span data-stu-id="41411-123">Choose save.</span></span> <span data-ttu-id="41411-124">スキーマ一覧表が表示されます。</span><span class="sxs-lookup"><span data-stu-id="41411-124">Your schema will now be listed.</span></span>

7. <span data-ttu-id="41411-125">**EDM の機密情報の種類** を選択し、 **EDM の機密情報の種類を作成** して、機密情報の種類の構成ウィザードを開きます。</span><span class="sxs-lookup"><span data-stu-id="41411-125">Choose **EDM sensitive info types** and **Create EDM sensitive info type** to open the sensitive info type configuration wizard.</span></span>

8. <span data-ttu-id="41411-126">**既存のEDM スキーマを選択** を選択し、リストの手順2 から 6 で作成したスキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="41411-126">Choose **Choose an existing EDM schema** and choose the schema you created in steps 2-6 from the list.</span></span>

9. <span data-ttu-id="41411-127">**次へ** を選択し、**パターンの作成** を選択します。</span><span class="sxs-lookup"><span data-stu-id="41411-127">Choose **Next** and choose **Create pattern**.</span></span>

10. <span data-ttu-id="41411-128">**信頼度** および **主要要素** を選択します。</span><span class="sxs-lookup"><span data-stu-id="41411-128">Choose the **Confidence level** and **Primary element**.</span></span>  <span data-ttu-id="41411-129">パターン構成方法の詳細については、「[コンプライアンス センターでカスタムの機密情報の種類を作成](create-a-custom-sensitive-information-type.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41411-129">To learn more about configuring a pattern, see [Create a custom sensitive information type in the Compliance Center](create-a-custom-sensitive-information-type.md)</span></span>

11.  <span data-ttu-id="41411-130">**主要要素の機密情報の種類** を選択し、それをに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="41411-130">Choose the **Primary element's sensitive info type** to associate it with.</span></span> <span data-ttu-id="41411-131">利用可能な機密情報の種類の詳細については、「[機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41411-131">See [Sensitive Information Type Entity Definitions](sensitive-information-type-entity-definitions.md) to learn more about the available sensitive information types.</span></span>

12. <span data-ttu-id="41411-132">[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="41411-132">Choose **Done**.</span></span>

13. <span data-ttu-id="41411-133">目的の **信頼度と文字の間隔** を選択します。</span><span class="sxs-lookup"><span data-stu-id="41411-133">Choose your desired **Confidence level and character proximity**.</span></span>  <span data-ttu-id="41411-134">これは、EDM の機密情報の種類の既定値となります。</span><span class="sxs-lookup"><span data-stu-id="41411-134">This will be the default value for the whole EDM sensitive info type</span></span>

13. <span data-ttu-id="41411-135">EDM **機密情報** の種類に追加のパターンを作成する場合は、[パターンの作成] を選択します。</span><span class="sxs-lookup"><span data-stu-id="41411-135">Choose **Create pattern** if you want to create additional patterns for your EDM sensitive info type.</span></span>

14. <span data-ttu-id="41411-136">[**次へ**] を選択し、**名前** および **管理者向けの説明** を入力します。</span><span class="sxs-lookup"><span data-stu-id="41411-136">Choose **Next** and fill in a **Name** and **Description for admins**.</span></span>

15. <span data-ttu-id="41411-137">レビューし、[**送信**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="41411-137">Review and choose **Submit**.</span></span>

<span data-ttu-id="41411-138">編集および削除コントロールを表示して、機密情報の種類パターンを削除または編集します。</span><span class="sxs-lookup"><span data-stu-id="41411-138">You can delete or edit the sensitive information type pattern by selecting it which surfaces the edit and delete controls.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="41411-139">スキーマを削除し、それが既に EDM の機密情報の種類に関連付けられている場合は、まずEDM の機密情報の種類を削除し、その後、スキーマを削除できます。</span><span class="sxs-lookup"><span data-stu-id="41411-139">If you want to remove a schema, and it is already associated with an EDM sensitive info type, you must first delete the EDM sensitive info type, then you can delete the schema.</span></span>

## <a name="post-creation-steps"></a><span data-ttu-id="41411-140">作成後の手順</span><span class="sxs-lookup"><span data-stu-id="41411-140">Post creation steps</span></span>

<span data-ttu-id="41411-141">このウィザードを使用して EDM のスキーマおよびパターン (ルール パッケージ) ファイルを作成後、EDM ユーザー機密情報の種類を使用する前に、手順 [パート 2: 機密性の高いデータをハッシュおよびアップロードする](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data)の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41411-141">After you have used this wizard to create your EDM schema and pattern (rule package) files, you still have to perform the steps in [Part 2: Hash and upload the sensitive data](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) before you can use the EDM custom sensitive information type.</span></span>

<span data-ttu-id="41411-142">機密情報テーブルが正しくアップロードされていることを確認したら、正しく動作しているのをテストできます。</span><span class="sxs-lookup"><span data-stu-id="41411-142">After verifying that your sensitive information table has correctly been uploaded, you can test that it's working properly.</span></span>

1. <span data-ttu-id="41411-143">Open **Compliance center** Data  >  **classification** Sensitive Information  >  **Types**.</span><span class="sxs-lookup"><span data-stu-id="41411-143">Open **Compliance center** > **Data classification** > **Sensitive Information Types**.</span></span>
2. <span data-ttu-id="41411-144">リストから EDM SIT を選択し、フライアウト ウィンドウ **で [テスト** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="41411-144">Select your EDM SIT from the list and then select **Test** in the flyout pane.</span></span> 
3. <span data-ttu-id="41411-145">アップロードするデータを含むアイテムを作成します。たとえば、機密情報テーブルにデータの一部を含むアイテムを作成します。</span><span class="sxs-lookup"><span data-stu-id="41411-145">Upload an item that contains data you want to detect, for example create an item that contains some of the data in your sensitive information table.</span></span> <span data-ttu-id="41411-146">スキーマで構成可能な一致機能を使用して、無視される区切り記号を定義した場合は、それらの区切り記号の使用と使用しない例がアイテムに含まれるか確認してください。</span><span class="sxs-lookup"><span data-stu-id="41411-146">If you used the configurable match feature in your schema to define ignored delimiters, make sure the item includes examples with and without those delimiters.</span></span>
4. <span data-ttu-id="41411-147">ファイルがアップロードおよびスキャンされた後、EDM SIT との一致を確認します。</span><span class="sxs-lookup"><span data-stu-id="41411-147">After the file has been uploaded and scanned, check for matches to your EDM SIT.</span></span>
5. <span data-ttu-id="41411-148">SIT の **Test** 関数で一致が検出された場合は、その関数がトリミングされていないか、誤って抽出されていないか確認してください。</span><span class="sxs-lookup"><span data-stu-id="41411-148">If the **Test** function in the SIT detects a match, check that it is not trimming it or extracting it incorrectly.</span></span> <span data-ttu-id="41411-149">たとえば、検出するはずの文字列全体の部分文字列のみを抽出したり、複数単語の文字列の最初の単語のみを取得したり、抽出に余分な記号や文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="41411-149">For example by extracting only a substring of the full string it is supposed to detect, or picking up only the first word in a multi-word string, or including extra symbols or characters in the extraction.</span></span> <span data-ttu-id="41411-150">正規表現 [言語リファレンスについては、「正規表現言語 -](/dotnet/standard/base-types/regular-expression-language-quick-reference) クイック リファレンス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41411-150">See [Regular Expression Language - Quick Reference](/dotnet/standard/base-types/regular-expression-language-quick-reference) for the regular expression language reference.</span></span> 

### <a name="troubleshooting"></a><span data-ttu-id="41411-151">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="41411-151">Troubleshooting</span></span>

<span data-ttu-id="41411-152">一致が見つからなかった場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="41411-152">If you don't find any matches, try the following:</span></span>
- <span data-ttu-id="41411-153">[EDM](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)ツールを使用して機密データをアップロードするガイダンスで説明されているコマンドを使用して、機密データが正しくアップロードされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="41411-153">Confirm that your sensitive data was uploaded correctly using the commands explained in [the guidance for uploading your sensitive data using the EDM tool](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>
- <span data-ttu-id="41411-154">アイテムに入力した例が機密情報テーブルに存在し、無視された区切り記号が正しいか確認します。</span><span class="sxs-lookup"><span data-stu-id="41411-154">Check that the examples you entered in the item are present in your sensitive information table and that the ignored delimiters are correct.</span></span>
- <span data-ttu-id="41411-155">**各** パターンでプライマリ要素を構成するときに使用した SIT をテストします。</span><span class="sxs-lookup"><span data-stu-id="41411-155">**Test** the SIT you used when you configured the primary element in each of your patterns.</span></span> <span data-ttu-id="41411-156">これにより、SIT がアイテムの例と一致する可能性が確認されます。</span><span class="sxs-lookup"><span data-stu-id="41411-156">This will confirm that the SIT is able to match the examples in the item.</span></span> 
  -  <span data-ttu-id="41411-157">EDM 型のプライマリ要素に対して選択した SIT がアイテム内で一致を見つけなかったり、予期した数よりも少ない一致を見つけた場合は、コンテンツに存在する区切り記号と区切り記号がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="41411-157">If the SIT you selected for a primary element in the EDM type doesn't find a match in the item or finds fewer matches than you expected, check that it supports separators and delimiters that exist in the content.</span></span> <span data-ttu-id="41411-158">スキーマで定義されている無視された区切り記号を必ず含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="41411-158">Be sure to include the ignored delimiters defined in your schema.</span></span> 
  -  <span data-ttu-id="41411-159">Test 関数 **で** コンテンツが検出されない場合は、選択した SIT に追加のキーワードまたは他の検証の要件が含まれるか確認します。</span><span class="sxs-lookup"><span data-stu-id="41411-159">If the **Test** function does not detect any content at all, check if the SIT you selected includes requirements for additional keywords or other validations.</span></span> <span data-ttu-id="41411-160">組み込みの SIT については[](sensitive-information-type-entity-definitions.md)、「機密情報の種類エンティティ定義」を参照して、各種類に一致する最小要件を確認します。</span><span class="sxs-lookup"><span data-stu-id="41411-160">For the built-in SITs, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md) to verify what the minimum requirements are for matching each type.</span></span>
