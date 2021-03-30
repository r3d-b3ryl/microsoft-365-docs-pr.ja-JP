---
title: 説明のタイプ
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Microsoft SharePoint Syntexの説明のタイプの詳細については、こちらを参照してください。
ms.openlocfilehash: b34de9ffc565e3d1a17cac05084e4e4b4113a3c6
ms.sourcegitcommit: 3d3c446d5e2e90369be1339dd0a33e71432fbc36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2021
ms.locfileid: "50994630"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="300bc-103">説明の種類の概要</span><span class="sxs-lookup"><span data-stu-id="300bc-103">Introduction to explanation types</span></span>

<span data-ttu-id="300bc-104">説明は、 Microsoft SharePoint Syntexの文書把握モデルでラベルをつけたり、抽出する情報の定義付けをするときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="300bc-104">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="300bc-105">説明を作成するときに、説明の種類を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="300bc-105">When creating an explanation, you need to select an explanation type.</span></span> <span data-ttu-id="300bc-106">この記事では、さまざまな種類の説明とその使用方法の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="300bc-106">This article helps you understand the different explanation types and how they are used.</span></span> 

   ![説明のタイプ](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="300bc-108">これらの説明の種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="300bc-108">These explanation types are available:</span></span>

- <span data-ttu-id="300bc-109">**語句リスト**: 抽出する文書または情報で使用できる単語、語句、数字、その他の文字の一覧です。</span><span class="sxs-lookup"><span data-stu-id="300bc-109">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting.</span></span> <span data-ttu-id="300bc-110">たとえば、文字列 **医師を参照する** は、指定したすべての医療紹介ドキュメントの中でに存在します。</span><span class="sxs-lookup"><span data-stu-id="300bc-110">For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span></br>

- <span data-ttu-id="300bc-111">**パターン一覧**: 抽出する情報を識別するために使用できる数字、文字、またはその他の文字のパターンのリストを表示します。</span><span class="sxs-lookup"><span data-stu-id="300bc-111">**Pattern list**: List patterns of numbers, letters, or other characters that you can use to identify the information that you are extracting.</span></span> <span data-ttu-id="300bc-112">たとえば、識別しているすべての医療紹介ドキュメントから、参照元の医師の **電話番号** を抽出できます。</span><span class="sxs-lookup"><span data-stu-id="300bc-112">For example, you can extract the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span></br>

- <span data-ttu-id="300bc-113">**類似性**: 説明が他の説明とどの程度相互に近いかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="300bc-113">**Proximity**: Describes how close explanations are to each other.</span></span> <span data-ttu-id="300bc-114">たとえば、 *のストリート番号* パターンリストは *ストリート名* 語句リストの直前にありますが、その間にトークンはありません (トークンについては、この記事の後半で説明します)。</span><span class="sxs-lookup"><span data-stu-id="300bc-114">For example, a *street number* pattern list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> <span data-ttu-id="300bc-115">近接型を使用するには、モデルに少なくとも 2 つの説明が必要です。そうでない場合、オプションは無効になります。</span><span class="sxs-lookup"><span data-stu-id="300bc-115">Using the proximity type requires you to have at least two explanations in your model or the option will be disabled.</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="300bc-116">語句リスト</span><span class="sxs-lookup"><span data-stu-id="300bc-116">Phrase list</span></span>

<span data-ttu-id="300bc-117">通常、語句リストの説明の種類は、モデルを介してドキュメントを識別して分類するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="300bc-117">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="300bc-118">*医師を参照する* ラベルの例に記載されているように、指定した文書に常に含まれる単語、語句、数字、または文字の文字列です。</span><span class="sxs-lookup"><span data-stu-id="300bc-118">As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="300bc-119">必須ではありませんが、キャプチャしている語句が文書内の一貫した場所にある場合は、説明をうまく行うことができます。</span><span class="sxs-lookup"><span data-stu-id="300bc-119">While not a requirement, you can achieve better success with your explanation if the phrase you are capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="300bc-120">たとえば、 *医師の参照* ラベルは、文書の最初の段落に常に保存されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="300bc-120">For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span>

<span data-ttu-id="300bc-121">ラベルを特定する際に大文字と小文字が区別される必要がある場合は、語句リストの種類を使用して、[**文字の 大文字のみ を選択する**] チェックボックスをオンにして、テキストの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="300bc-121">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

   ![大文字と小文字の区別](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a><span data-ttu-id="300bc-123">パターン一覧</span><span class="sxs-lookup"><span data-stu-id="300bc-123">Pattern lists</span></span>

<span data-ttu-id="300bc-124">パターンリストタイプは、ドキュメントから情報を特定して抽出する説明を作成する場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="300bc-124">A pattern list type is especially useful when you create an explanation that identifies and extracts information from a document.</span></span> <span data-ttu-id="300bc-125">通常、日付、電話番号、クレジットカード番号などのさまざまな形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="300bc-125">It is typically presented in different formats, such as dates, phone numbers, and credit card numbers.</span></span> <span data-ttu-id="300bc-126">たとえば、日付をさまざまな形式の数字で表示できます (1/1/2020、1-1-2020、01/01/20、01/01/2020、Jan 1、2020など)。</span><span class="sxs-lookup"><span data-stu-id="300bc-126">For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.).</span></span> <span data-ttu-id="300bc-127">パターンリストを定義すると、指定して抽出するデータのバリエーションをキャプチャして、説明をより効率的にすることができます。</span><span class="sxs-lookup"><span data-stu-id="300bc-127">Defining a pattern list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="300bc-128">**電話番号** の例では、モデルが識別するすべての医療紹介文書から、紹介する各医師の電話番号を抽出します。</span><span class="sxs-lookup"><span data-stu-id="300bc-128">For the **Phone number** example, you extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="300bc-129">説明を作成するときには、パターンリストの種類を選択し、返される可能性のあるさまざまな書式を設定します。</span><span class="sxs-lookup"><span data-stu-id="300bc-129">When you create the explanation, select the Pattern list type to allow the different formats that you may expect to be returned.</span></span>

   ![電話番号パターンの一覧](../media/content-understanding/pattern-list.png)

<span data-ttu-id="300bc-131">この例では、**[0〜9 の任意の数字]** チェックボックスを選択して、パターンリストで使用されている各 "0" の値が 0〜9 の任意の数字であることを認識します。</span><span class="sxs-lookup"><span data-stu-id="300bc-131">For this example, select the **Any digit from 0-9** checkbox to recognize each "0" value used in your pattern list to be any digit from 0 through 9.</span></span>

   ![0〜9 の任意の数字](../media/content-understanding/digit-identity.png)

<span data-ttu-id="300bc-133">同様に、テキスト文字を含むパターンリストを作成する場合は、**[a-zから任意の文字]** チェックボックスを選択して、パターンリストで使用される各 "a" 文字が "a" から "z" までの任意の文字であることを認識します。</span><span class="sxs-lookup"><span data-stu-id="300bc-133">Similarly, if you create a pattern list that includes text characters, select the **Any letter from a-z** checkbox to recognize each "a" character used in the pattern list to be any character from "a" to "z".</span></span>

<span data-ttu-id="300bc-134">たとえば、 **日付** パターンリストを作成した場合、 *2020年1月1日* などの日付形式が認識されるようにするには、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="300bc-134">For example, if you create a **Date** pattern list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="300bc-135">*aaa 0, 0000* *aaa 00, 0000* をパターンリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="300bc-135">Add *aaa 0, 0000* and *aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="300bc-136">**a-z の の任意の文字** が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="300bc-136">Make sure that **Any letter from a-z** is also selected.</span></span>

   ![A ~ z の任意の文字](../media/content-understanding/any-letter.png)

<span data-ttu-id="300bc-138">また、[パターン] リストに大文字と小文字の区別をする要件がある場合は、[ **大文字のみを区別する** ] チェックボックスをオンにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="300bc-138">Additionally, if you have capitalization requirements in your pattern list, you have the option to select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="300bc-139">日付の例では、月の最初の文字を大文字にする必要がある場合、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="300bc-139">For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="300bc-140">*Aaa 0, 0000* および *Aaa 00, 0000* をパターンリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="300bc-140">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="300bc-141">**すべて大文字のみ** が選択されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="300bc-141">Make sure that **Only exact capitalization** is also selected.</span></span>

   ![確実に大文字のみ](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="300bc-143">パターンリストの説明を手動で作成する代わりに、 [説明ライブラリ](#use-explanation-templates) を使用して、共通パターンのリストにパターンリストテンプレート ( *日付*、 *電話番号*、 *クレジットカード番号* など) を使用します。</span><span class="sxs-lookup"><span data-stu-id="300bc-143">Instead of manually creating a pattern list explanation, use the [explanation library](#use-explanation-templates) to use pattern list templates for a common pattern list, such as *date*, *phone number*, *credit card number*, etc.</span></span>

## <a name="proximity"></a><span data-ttu-id="300bc-144">類似性</span><span class="sxs-lookup"><span data-stu-id="300bc-144">Proximity</span></span> 

<span data-ttu-id="300bc-145">類似性の説明タイプは、モデルが他のデータがどの程度自分と似ているかを定義することで、データを特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="300bc-145">The proximity explanation type helps your model identify data by defining how close another piece of data is to it.</span></span> <span data-ttu-id="300bc-146">たとえば、モデルでは、顧客にラベルを付けるために、*住所の番地* と *電話番号* の2つの説明を定義しました。</span><span class="sxs-lookup"><span data-stu-id="300bc-146">For example, in your model say you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="300bc-147">お客様の電話番号は番地の前に常に表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="300bc-147">Notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="300bc-148">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="300bc-148">Alex Wilburn</span></span><br>
<span data-ttu-id="300bc-149">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="300bc-149">555-555-5555</span></span><br>
<span data-ttu-id="300bc-150">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="300bc-150">One Microsoft Way</span></span><br>
<span data-ttu-id="300bc-151">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="300bc-151">Redmond, WA 98034</span></span><br>

<span data-ttu-id="300bc-152">[類似性の説明を使用して、ドキュメント中の住所の番地をうまく特定するには、電話番号の説明はあまりに類似性が低いことを定義します。</span><span class="sxs-lookup"><span data-stu-id="300bc-152">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

   ![類似性の説明](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a><span data-ttu-id="300bc-154">トークンとは?</span><span class="sxs-lookup"><span data-stu-id="300bc-154">What are tokens?</span></span>

<span data-ttu-id="300bc-155">類似性の説明の種類を使用するには、トークンが何かを理解する必要があります。トークンの数は、ある説明から別の説明への距離を、類似性の説明がどのように測定しているかを表しています。</span><span class="sxs-lookup"><span data-stu-id="300bc-155">In order to use the proximity explanation type, you need to understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span> <span data-ttu-id="300bc-156">トークンは、文字と数字を連続しているスパン (スペースや句読点を含まない) です。</span><span class="sxs-lookup"><span data-stu-id="300bc-156">A token is a continuous span (not including spaces or punctuation) of letters and numbers.</span></span> 

<span data-ttu-id="300bc-157">次の表は、語句の中のトークン数を決定する方法の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="300bc-157">The following table shows examples for how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="300bc-158">語句</span><span class="sxs-lookup"><span data-stu-id="300bc-158">Phrase</span></span>|<span data-ttu-id="300bc-159">トークン数</span><span class="sxs-lookup"><span data-stu-id="300bc-159">Number of tokens</span></span>|<span data-ttu-id="300bc-160">説明</span><span class="sxs-lookup"><span data-stu-id="300bc-160">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="300bc-161">1</span><span class="sxs-lookup"><span data-stu-id="300bc-161">1</span></span>|<span data-ttu-id="300bc-162">句読点やスペースを含まない1つの単語。</span><span class="sxs-lookup"><span data-stu-id="300bc-162">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="300bc-163">1</span><span class="sxs-lookup"><span data-stu-id="300bc-163">1</span></span>|<span data-ttu-id="300bc-164">レコードロケーター番号。</span><span class="sxs-lookup"><span data-stu-id="300bc-164">A record locator number.</span></span> <span data-ttu-id="300bc-165">数字と文字が含まれる場合がありますが、区切り記号はありません。</span><span class="sxs-lookup"><span data-stu-id="300bc-165">It may include numbers and letters, but does not have punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="300bc-166">5</span><span class="sxs-lookup"><span data-stu-id="300bc-166">5</span></span>|<span data-ttu-id="300bc-167">電話番号</span><span class="sxs-lookup"><span data-stu-id="300bc-167">A phone number.</span></span> <span data-ttu-id="300bc-168">句読点はそれぞれ1つのトークンなので、`425-555-5555` は、5 トークンとなります。</span><span class="sxs-lookup"><span data-stu-id="300bc-168">Each punctuation mark is a single token, so `425-555-5555` is 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="300bc-169">7</span><span class="sxs-lookup"><span data-stu-id="300bc-169">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="300bc-170">類似性の説明の種類を構成する</span><span class="sxs-lookup"><span data-stu-id="300bc-170">Configure the proximity explanation type</span></span>

<span data-ttu-id="300bc-171">この例では、[類似性] 設定を構成して、*番地* の説明から *電話番号* の説明のトークン数の範囲を定義します。</span><span class="sxs-lookup"><span data-stu-id="300bc-171">For the example, configure the proximity setting to define the range of the number of tokens in the *Phone number* explanation from the *Street address number* explanation.</span></span> <span data-ttu-id="300bc-172">電話番号と住所の番地の間にトークンがないため、最小範囲が "0" であることがわかります。</span><span class="sxs-lookup"><span data-stu-id="300bc-172">Notice that the minimum range is "0", because there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="300bc-173">ただし、サンプルドキュメントの一部の電話番号には、接頭語 *(mobile)* が追加されています。</span><span class="sxs-lookup"><span data-stu-id="300bc-173">But some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="300bc-174">Nestor Wilke</span><span class="sxs-lookup"><span data-stu-id="300bc-174">Nestor Wilke</span></span><br>
<span data-ttu-id="300bc-175">111-111-1111 (モバイル)</span><span class="sxs-lookup"><span data-stu-id="300bc-175">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="300bc-176">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="300bc-176">One Microsoft Way</span></span><br>
<span data-ttu-id="300bc-177">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="300bc-177">Redmond, WA 98034</span></span><br>

<span data-ttu-id="300bc-178">*(モバイル)* には次の3つのトークンがあります。</span><span class="sxs-lookup"><span data-stu-id="300bc-178">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="300bc-179">語句</span><span class="sxs-lookup"><span data-stu-id="300bc-179">Phrase</span></span>|<span data-ttu-id="300bc-180">トークン数</span><span class="sxs-lookup"><span data-stu-id="300bc-180">Token count</span></span>|
|--|--|
|<span data-ttu-id="300bc-181">(</span><span class="sxs-lookup"><span data-stu-id="300bc-181">(</span></span>|<span data-ttu-id="300bc-182">1</span><span class="sxs-lookup"><span data-stu-id="300bc-182">1</span></span>|
|<span data-ttu-id="300bc-183">モバイル</span><span class="sxs-lookup"><span data-stu-id="300bc-183">mobile</span></span>|<span data-ttu-id="300bc-184">2</span><span class="sxs-lookup"><span data-stu-id="300bc-184">2</span></span>|
|<span data-ttu-id="300bc-185">)</span><span class="sxs-lookup"><span data-stu-id="300bc-185">)</span></span>|<span data-ttu-id="300bc-186">3</span><span class="sxs-lookup"><span data-stu-id="300bc-186">3</span></span>|

<span data-ttu-id="300bc-187">0から3までの範囲を設定するには、[類似性] 設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="300bc-187">Configure the proximity setting to have a range of 0 through 3.</span></span>

   ![類似性の例](../media/content-understanding/proximity-example.png)</br>


## <a name="configure-where-phrases-occur-in-the-document"></a><span data-ttu-id="300bc-189">ドキュメント内の語句の位置を構成する</span><span class="sxs-lookup"><span data-stu-id="300bc-189">Configure where phrases occur in the document</span></span>

<span data-ttu-id="300bc-190">説明を作成すると、既定でドキュメント全体から抽出しようとしている語句が検索されます。</span><span class="sxs-lookup"><span data-stu-id="300bc-190">When you create an explanation, by default the entire document is searched for the phrase you are trying to extract.</span></span> <span data-ttu-id="300bc-191">ただし、<b>[これらの語句が表示される場所]</b> の詳細設定を使用すると、語句が表示されるドキュメント内の特定の場所を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="300bc-191">However, you can use the <b>Where these phrases occur</b> advanced setting to help in isolating a specific location in the document that a phrase occurs.</span></span> <span data-ttu-id="300bc-192">これは、ドキュメント内の別の場所に語句の類似のインスタンスが表示される可能性があり、正しいインスタンスが選択されていることを確認する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="300bc-192">This is useful in situations where similar instances of a phrase might appear somewhere else in the document, and you want to make sure that the correct one is selected.</span></span> <span data-ttu-id="300bc-193">病院の紹介状の例を参照すると、**[委託医師]** は常にドキュメントの第 1 段落に記載されています。</span><span class="sxs-lookup"><span data-stu-id="300bc-193">Referring to our Medical Referral document example, the **Referring Doctor** is always mentioned in the first paragraph of the document.</span></span> <span data-ttu-id="300bc-194">この例では、<b>[これらの語句が表示される場所]</b> の設定を使用して、このラベルをドキュメントの先頭部分、またはラベルが表示される可能性のあるその他の場所だけで検索するように説明を構成できます。</span><span class="sxs-lookup"><span data-stu-id="300bc-194">With the <b>Where these phrases occur</b> setting, in this example you can configure your explanation to search for this label only in the beginning section of the document, or any other location in which it might occur.</span></span>

   ![[これらの語句が表示される場所] の設定](../media/content-understanding/phrase-location.png)</br>

<span data-ttu-id="300bc-196">この設定では、次のオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="300bc-196">You can choose the following options for this setting:</span></span>

- <span data-ttu-id="300bc-197">ファイル内の任意の場所: ドキュメント全体で語句が検索されます。</span><span class="sxs-lookup"><span data-stu-id="300bc-197">Anywhere in the file: The entire document is searched for the phrase.</span></span>
- <span data-ttu-id="300bc-198">ファイルの先頭: ドキュメントの先頭から語句の場所まで検索されます。</span><span class="sxs-lookup"><span data-stu-id="300bc-198">Beginning of the file:  The document is searched from the beginning to the phrase location.</span></span></br> 
   <span data-ttu-id="300bc-199">![ファイルの先頭](../media/content-understanding/beginning-of-file.png)</span><span class="sxs-lookup"><span data-stu-id="300bc-199">![Beginning of file](../media/content-understanding/beginning-of-file.png)</span></span></br>
<span data-ttu-id="300bc-200">ビューアでは、フェーズが表示される場所を含めるように選択ボックスを手動で調整できます。</span><span class="sxs-lookup"><span data-stu-id="300bc-200">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="300bc-201"><b>[終了位置]</b> の値が更新され、選択した領域に含まれるトークンの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="300bc-201">The <b>End position</b> value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="300bc-202">[終了位置] の値を更新して、選択した領域を調整することもできます。</span><span class="sxs-lookup"><span data-stu-id="300bc-202">Note that you can update the End position value as well to adjust the selected area.</span></span></br>
   <span data-ttu-id="300bc-203">![ファイルの先頭の位置ボックス](../media/content-understanding/beginning-box.png)</span><span class="sxs-lookup"><span data-stu-id="300bc-203">![Beginning of file position box](../media/content-understanding/beginning-box.png)</span></span></br>

- <span data-ttu-id="300bc-204">ファイルの末尾: ドキュメントの末尾から語句の場所まで検索されます。</span><span class="sxs-lookup"><span data-stu-id="300bc-204">End of the file:  The document is searched from the end to the phrase location.</span></span></br> 
   <span data-ttu-id="300bc-205">![ファイルの末尾](../media/content-understanding/end-of-file.png)</span><span class="sxs-lookup"><span data-stu-id="300bc-205">![End of file](../media/content-understanding/end-of-file.png)</span></span></br>
<span data-ttu-id="300bc-206">ビューアでは、フェーズが表示される場所を含めるように選択ボックスを手動で調整できます。</span><span class="sxs-lookup"><span data-stu-id="300bc-206">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="300bc-207"><b>[開始位置]</b> の値が更新され、選択した領域に含まれるトークンの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="300bc-207">The <b>Starting position</b> value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="300bc-208">[開始位置] の値を更新して、選択した領域を調整することもできます。</span><span class="sxs-lookup"><span data-stu-id="300bc-208">Note that you can update the Starting position value as well to adjust the selected area.</span></span></br> 
   <span data-ttu-id="300bc-209">![ファイルの末尾の終了ボックス](../media/content-understanding/end-box.png)</span><span class="sxs-lookup"><span data-stu-id="300bc-209">![End of file end box](../media/content-understanding/end-box.png)</span></span></br>
- <span data-ttu-id="300bc-210">ユーザー設定の範囲: ドキュメント内の指定された範囲で、語句の場所が検索されます。</span><span class="sxs-lookup"><span data-stu-id="300bc-210">Custom range:  The document is searched in a specified range within the it for the phrase location.</span></span></br> 
   <span data-ttu-id="300bc-211">![ユーザー設定の範囲](../media/content-understanding/custom-file.png)</span><span class="sxs-lookup"><span data-stu-id="300bc-211">![Custom range](../media/content-understanding/custom-file.png)</span></span></br>
<span data-ttu-id="300bc-212">ビューアでは、フェーズが表示される場所を含めるように選択ボックスを手動で調整できます。</span><span class="sxs-lookup"><span data-stu-id="300bc-212">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="300bc-213">この設定では、<b>[開始]</b> と <b>[終了]</b> の位置を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="300bc-213">For this setting, you need to select a <b>Start</b> and an <b>End</b> position.</span></span> <span data-ttu-id="300bc-214">これらの値は、ドキュメントの先頭のトークンの数を表します。</span><span class="sxs-lookup"><span data-stu-id="300bc-214">These values represent the number of tokens from the begging of the document.</span></span> <span data-ttu-id="300bc-215">これらの値は手動で入力できますが、ビューアーの選択ボックスを手動で調整する方が簡単です。</span><span class="sxs-lookup"><span data-stu-id="300bc-215">While you can manually enter in these values, it is easier to manually adjust the select box in the viewer.</span></span></br> 
   
## <a name="use-explanation-templates"></a><span data-ttu-id="300bc-216">説明テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="300bc-216">Use explanation templates</span></span>

<span data-ttu-id="300bc-217">説明用にさまざまなフレーズ リスト値を手動で追加できますが、説明ライブラリで提供されているテンプレートを使用する方が簡単な場合があります。</span><span class="sxs-lookup"><span data-stu-id="300bc-217">While you can manually add various phrase list values for your explanation, it can be easier to use the templates provided to you in the explanation library.</span></span>

<span data-ttu-id="300bc-218">たとえば、*Date* のすべてのバリエーションを手動で追加する代わりに、*Date* のフレーズ リスト テンプレートを使用できます。これには、すでにいくつかのフレーズ リスト値が含まれているためです。</span><span class="sxs-lookup"><span data-stu-id="300bc-218">For example, instead of manually adding all the variations for *Date*, you can use the phrase list template for *Date* as it already includes a number of phrase lists values:</span></span></br>

   ![説明ライブラリ](../media/content-understanding/explanation-template.png)</br>
 
<span data-ttu-id="300bc-220">説明ライブラリには、次のような一般的に使用されるフレーズ リストの説明が含まれています。</span><span class="sxs-lookup"><span data-stu-id="300bc-220">The explanation library includes commonly used phrase list explanations, including:</span></span></br>

- <span data-ttu-id="300bc-221">日付: 予定表の日付、すべての形式。</span><span class="sxs-lookup"><span data-stu-id="300bc-221">Date: Calendar dates, all formats.</span></span> <span data-ttu-id="300bc-222">テキストと数値を含む (たとえば、"Dec 9, 2020")。</span><span class="sxs-lookup"><span data-stu-id="300bc-222">Includes text and numbers (for example, "Dec 9, 2020").</span></span></br>
- <span data-ttu-id="300bc-223">日付（数値）: 予定表の日付、すべての形式。</span><span class="sxs-lookup"><span data-stu-id="300bc-223">Date (numeric): Calendar dates, all formats.</span></span> <span data-ttu-id="300bc-224">数値が含まれます (例: 1-11-2020)。</span><span class="sxs-lookup"><span data-stu-id="300bc-224">Includes numbers (for example 1-11-2020).</span></span></br>
- <span data-ttu-id="300bc-225">時刻: 12 時間と 24 時間表示。</span><span class="sxs-lookup"><span data-stu-id="300bc-225">Time: 12 and 24 hour formats.</span></span></br>
- <span data-ttu-id="300bc-226">数値: 最大 2 桁の小数点の正の数と負の数。</span><span class="sxs-lookup"><span data-stu-id="300bc-226">Number: Positive and negative numbers up to 2 decimals.</span></span> </br>
- <span data-ttu-id="300bc-227">パーセンテージ: パーセンテージを表すパターンの一覧。</span><span class="sxs-lookup"><span data-stu-id="300bc-227">Percentage: A list of patterns representing a percentage.</span></span> <span data-ttu-id="300bc-228">たとえば、1%、11%、100%、11.11% などです。</span><span class="sxs-lookup"><span data-stu-id="300bc-228">For example, 1%, 11%, 100%, 11.11%, etc.</span></span></br>
- <span data-ttu-id="300bc-229">電話番号: 米国および国際一般的な形式。</span><span class="sxs-lookup"><span data-stu-id="300bc-229">Phone number: Common US and International formats.</span></span> <span data-ttu-id="300bc-230">たとえば、000 000 0000、000-000-0000、(000)000-0000、(000) 000-0000 など。</span><span class="sxs-lookup"><span data-stu-id="300bc-230">For example, 000 000 0000, 000-000-0000, (000)000-0000, (000) 000-0000, etc.</span></span></br>
- <span data-ttu-id="300bc-231">郵便番号: 米国の郵便番号の形式。</span><span class="sxs-lookup"><span data-stu-id="300bc-231">Zip code: US Zip code formats.</span></span> <span data-ttu-id="300bc-232">たとえば、11111、11111-1111 などです。</span><span class="sxs-lookup"><span data-stu-id="300bc-232">For example, 11111, 11111-1111.</span></span></br>
- <span data-ttu-id="300bc-233">文の最初の単語: 最大 9 文字の単語の一般的なパターン。</span><span class="sxs-lookup"><span data-stu-id="300bc-233">First word of sentence: Common patterns for words up to 9 characters.</span></span> </br>
- <span data-ttu-id="300bc-234">文の末尾: 文の末尾の一般的な句読点</span><span class="sxs-lookup"><span data-stu-id="300bc-234">End of sentence: Common punctuation for end of a sentence</span></span></br>
- <span data-ttu-id="300bc-235">クレジット カード: 一般的なクレジット カード番号の書式。</span><span class="sxs-lookup"><span data-stu-id="300bc-235">Credit card: Common credit card number formats.</span></span> <span data-ttu-id="300bc-236">たとえば、1111-1111-1111-111 などです。</span><span class="sxs-lookup"><span data-stu-id="300bc-236">For example, 1111-1111-1111-1111.</span></span> </br>
- <span data-ttu-id="300bc-237">社会保障番号:米国の社会保障番号の書式。</span><span class="sxs-lookup"><span data-stu-id="300bc-237">Social security number: US Social Security Number format.</span></span> <span data-ttu-id="300bc-238">たとえば、111-11-1111 などです。</span><span class="sxs-lookup"><span data-stu-id="300bc-238">For example, 111-11-1111.</span></span> </br>
- <span data-ttu-id="300bc-239">チェック ボックス: 入力ボックスのバリエーションを表す語句リスト。</span><span class="sxs-lookup"><span data-stu-id="300bc-239">Checkbox: A phrase list representing variations on a filled in checkbox.</span></span> <span data-ttu-id="300bc-240">たとえば、 _X_、_ _X_、など</span><span class="sxs-lookup"><span data-stu-id="300bc-240">For example, _X_, _ _X_, etc.</span></span></br>
- <span data-ttu-id="300bc-241">通貨: 主要な国際記号。</span><span class="sxs-lookup"><span data-stu-id="300bc-241">Currency: Major international symbols.</span></span> <span data-ttu-id="300bc-242">たとえば、 ＄などです。</span><span class="sxs-lookup"><span data-stu-id="300bc-242">For example, $.</span></span> </br>
- <span data-ttu-id="300bc-243">電子メール CC: "CC:" という用語を含む語句一覧。多くの場合、メッセージが送信された他のユーザーまたはグループの名前またはメール アドレスの近くに表示されます。</span><span class="sxs-lookup"><span data-stu-id="300bc-243">Email CC: A phrase list with the term 'CC:', often found near the names or email addresses of additional people or groups the message was sent to.</span></span></br>
- <span data-ttu-id="300bc-244">メールの日付: "Sent on:" という用語を含む語句一覧です。多くの場合、メールの送信日の近くに表示されます。</span><span class="sxs-lookup"><span data-stu-id="300bc-244">Email date: A phrase list with the term 'Sent on:', often found near the date the email was sent.</span></span></br>
- <span data-ttu-id="300bc-245">電子メール応答: メールの一般的な起句。</span><span class="sxs-lookup"><span data-stu-id="300bc-245">Email greeting: Common opening lines for emails.</span></span></br>
- <span data-ttu-id="300bc-246">電子メール受信者: "To:" という用語を含む語句一覧。多くの場合、メッセージが送信されたユーザーまたはグループの名前またはメール アドレスの近くに表示されます。</span><span class="sxs-lookup"><span data-stu-id="300bc-246">Email recipient: A phrase list with the term 'To:', often found near the names or email addresses of people or groups the message was sent to.</span></span> </br>
- <span data-ttu-id="300bc-247">メールの送信者: "差出人:" という用語を含む語句一覧。多くの場合、送信者の名前またはメールアドレスの近くに表示されます。</span><span class="sxs-lookup"><span data-stu-id="300bc-247">Email sender: A phrase list with the term 'From:', often found near the sender's name or email address.</span></span> </br>
- <span data-ttu-id="300bc-248">メールの件名: "Subject:" という用語を含む語句一覧です。多くの場合、メールの件名の近くに表示されます。</span><span class="sxs-lookup"><span data-stu-id="300bc-248">Email subject: A phrase list with the term 'Subject:', often found near the email's subject.</span></span> </br>

<span data-ttu-id="300bc-249">説明ライブラリには、サンプル ファイルでラベル付けしたデータで動作する自動テンプレートの 3 つの種類も含まれています。</span><span class="sxs-lookup"><span data-stu-id="300bc-249">The explanation library also includes three automatic template types that work with the data you've labeled in your example files:</span></span>

- <span data-ttu-id="300bc-250">ラベルの後: サンプル ファイルのラベルの後に表示される単語または文字です。</span><span class="sxs-lookup"><span data-stu-id="300bc-250">After label: The words or characters that occur after the labels in the example files.</span></span></br>
- <span data-ttu-id="300bc-251">ラベルの前: サンプル ファイルのラベルの前に表示される単語または文字です。</span><span class="sxs-lookup"><span data-stu-id="300bc-251">Before label: The words or characters that occur before the labels in the example files.</span></span></br>
- <span data-ttu-id="300bc-252">ラベル: サンプル ファイルの最初の 10 個までのラベルです。</span><span class="sxs-lookup"><span data-stu-id="300bc-252">Labels: Up to the first 10 labels from the example files.</span></span></br>

<span data-ttu-id="300bc-253">自動テンプレートの動作例を示すために、次のサンプル ファイルでは、[ラベルの前] の説明テンプレートを使用して、モデルにより多くの情報を提供し、より正確な一致を取得します。</span><span class="sxs-lookup"><span data-stu-id="300bc-253">To give you an example of how automatic templates work, in the following example file, we will use the Before Label explanation template to help give the model more information to get a more accurate match.</span></span>

   ![サンプル ファイル](../media/content-understanding/before-label.png)</br>

<span data-ttu-id="300bc-255">[ラベルの前] 説明テンプレートを選択すると、サンプル ファイルのラベルの前に表示される最初の単語セットが検索されます。</span><span class="sxs-lookup"><span data-stu-id="300bc-255">When you select the Before Label explanation template, it will look for the first set of words that appear before the label in your example files.</span></span> <span data-ttu-id="300bc-256">この例では、最初のサンプル ファイルで識別される単語は「現在」です。</span><span class="sxs-lookup"><span data-stu-id="300bc-256">In the example, the words that are identified in the first example file is "As of".</span></span>

   ![[ラベルの前] テンプレート](../media/content-understanding/before-label-explanation.png)</br>

<span data-ttu-id="300bc-258"><b>[追加]</b> を選択して、テンプレートから説明を作成できます。</span><span class="sxs-lookup"><span data-stu-id="300bc-258">You can select <b>Add</b> to create an explanation from the template.</span></span>  <span data-ttu-id="300bc-259">サンプル ファイルをさらに追加すると、追加の単語が識別され、フレーズ リストに追加されます。</span><span class="sxs-lookup"><span data-stu-id="300bc-259">As you add more example files, additional words will be identified and added to the phrase list.</span></span>

   ![ラベルを追加する](../media/content-understanding/before-label-add.png)</br>
 
#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="300bc-261">説明ライブラリのテンプレートを使用するには</span><span class="sxs-lookup"><span data-stu-id="300bc-261">To use a template from the explanation library</span></span>

1. <span data-ttu-id="300bc-262">モデルの **トレーニング** ページの [**説明**] セクションで、[**新しい**] を選び、[**テンプレート から**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="300bc-262">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span></br>

   ![[ラベルの前] を追加する](../media/content-understanding/from-template.png)</br>

2.  <span data-ttu-id="300bc-264">**説明テンプレート** ページで、使用する説明を選び、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="300bc-264">On the **Explanation templates** page, select the explanation you want to use, then select **Add**.</span></span></br>

       ![テンプレートの選択](../media/content-understanding/phone-template.png)</br>

3. <span data-ttu-id="300bc-266">選択したテンプレートの情報は、 **説明を作成する** ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="300bc-266">The information for the template you selected displays on the **Create an explanation** page.</span></span> <span data-ttu-id="300bc-267">必要な場合は、説明の名前を編集して、フレーズ リストの項目を追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="300bc-267">If needed, edit the explanation name and add or remove items from the phrase list.</span></span> </br> 

   ![テンプレートを編集する](../media/content-understanding/phone-template-live.png)</br>

4. <span data-ttu-id="300bc-269">完了したら、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="300bc-269">When finished, select **Save**.</span></span>