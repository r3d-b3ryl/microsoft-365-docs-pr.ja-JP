---
title: 説明のタイプ
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Microsoft SharePoint Syntexの説明のタイプの詳細については、こちらを参照してください。
ms.openlocfilehash: 7d78337fd91bc7e5a71bccd4867f019ae663417a
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321799"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="1062e-103">説明の種類の概要</span><span class="sxs-lookup"><span data-stu-id="1062e-103">Introduction to explanation types</span></span>

<span data-ttu-id="1062e-104">説明は、 Microsoft SharePoint Syntexの文書把握モデルでラベルをつけたり、抽出する情報の定義付けをするときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1062e-104">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="1062e-105">説明を作成するときに、説明の種類を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1062e-105">When creating an explanation, you need to select an explanation type.</span></span> <span data-ttu-id="1062e-106">この記事では、さまざまな種類の説明とその使用方法の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="1062e-106">This article will help you learn more to better understand the different explanation types and how they are used.</span></span> 

   ![説明のタイプ](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="1062e-108">これらの説明の種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1062e-108">These explanation types are available:</span></span>

- <span data-ttu-id="1062e-109">**語句リスト**: 抽出する文書または情報で使用できる単語、語句、数字、その他の文字の一覧です。</span><span class="sxs-lookup"><span data-stu-id="1062e-109">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting.</span></span> <span data-ttu-id="1062e-110">たとえば、文字列**医師を参照する**は、指定したすべての医療紹介ドキュメントの中でに存在します。</span><span class="sxs-lookup"><span data-stu-id="1062e-110">For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span></br>

- <span data-ttu-id="1062e-111">**パターン一覧**: 抽出する情報を識別するために使用できる数字、文字、またはその他の文字のパターンのリストを表示します。</span><span class="sxs-lookup"><span data-stu-id="1062e-111">**Pattern list**: List patterns of numbers, letters, or other characters that you can use to identify the information that you are extracting.</span></span> <span data-ttu-id="1062e-112">たとえば、識別しているすべての医療紹介ドキュメントから、参照元の医師の **電話番号** を抽出できます。</span><span class="sxs-lookup"><span data-stu-id="1062e-112">For example, you can extract the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span></br>

- <span data-ttu-id="1062e-113">**類似性**: 説明が他の説明とどの程度相互に近いかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1062e-113">**Proximity**: Describes how close explanations are to each other.</span></span> <span data-ttu-id="1062e-114">たとえば、 *のストリート番号* パターンリストは *ストリート名* 語句リストの直前にありますが、その間にトークンはありません (トークンについては、この記事の後半で説明します)。</span><span class="sxs-lookup"><span data-stu-id="1062e-114">For example, a *street number* pattern list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> <span data-ttu-id="1062e-115">類似型を使用するには、モデルに少なくとも2つの説明が必要です。または、オプションは無効になります。</span><span class="sxs-lookup"><span data-stu-id="1062e-115">Using the proximity type requires you to have at least two explanations in your model, or the option will be disabled.</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="1062e-116">語句リスト</span><span class="sxs-lookup"><span data-stu-id="1062e-116">Phrase list</span></span>

<span data-ttu-id="1062e-117">通常、語句リストの説明の種類は、モデルを介してドキュメントを識別して分類するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1062e-117">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="1062e-118">*医師を参照する* ラベルの例に記載されているように、指定した文書に常に含まれる単語、語句、数字、または文字の文字列です。</span><span class="sxs-lookup"><span data-stu-id="1062e-118">As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="1062e-119">必須ではありませんが、キャプチャしている語句が文書内の一貫した場所にある場合は、説明をうまく行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1062e-119">While not a requirement, you can acheive better success with your explanation if the phrase you are capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="1062e-120">たとえば、 *医師の参照* ラベルは、文書の最初の段落に常に保存されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="1062e-120">For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span>

<span data-ttu-id="1062e-121">ラベルを特定する際に大文字と小文字が区別される必要がある場合は、語句リストの種類を使用して、[**文字の 大文字のみ を選択する**] チェックボックスをオンにして、テキストの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="1062e-121">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

   ![大文字と小文字の区別](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a><span data-ttu-id="1062e-123">パターン一覧</span><span class="sxs-lookup"><span data-stu-id="1062e-123">Pattern lists</span></span>

<span data-ttu-id="1062e-124">パターンリストタイプは、ドキュメントから情報を特定して抽出する説明を作成する場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="1062e-124">A pattern list type is especially useful when you create an explanation that identifies and extracts information from a document.</span></span> <span data-ttu-id="1062e-125">通常、日付、電話番号、クレジットカード番号など、さまざまな形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="1062e-125">It is typically presented in different formats, such as dates, phone numbers, or credit card numbers.</span></span> <span data-ttu-id="1062e-126">たとえば、日付をさまざまな形式の数字で表示できます (1/1/2020、1-1-2020、01/01/20、01/01/2020、Jan 1、2020など)。</span><span class="sxs-lookup"><span data-stu-id="1062e-126">For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.).</span></span> <span data-ttu-id="1062e-127">パターンリストを定義すると、指定して抽出するデータのバリエーションをキャプチャして、説明をより効率的にすることができます。</span><span class="sxs-lookup"><span data-stu-id="1062e-127">Defining a pattern list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="1062e-128">**電話番号**の例については、「モデルで識別されるすべての医療紹介ドキュメントから、各々の参照する医師の電話番号を抽出してください。</span><span class="sxs-lookup"><span data-stu-id="1062e-128">For the **Phone number** sample, extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="1062e-129">説明を作成するときには、パターンリストの種類を選択し、返される可能性のあるさまざまな書式を設定します。</span><span class="sxs-lookup"><span data-stu-id="1062e-129">When you create the explanation, select the Pattern list type to allow the different formats that you may expect to be returned.</span></span>

   ![電話番号パターンの一覧](../media/content-understanding/pattern-list.png)

<span data-ttu-id="1062e-131">この例では、**0-9 の任意の数字** をチェックボックスから選択します。</span><span class="sxs-lookup"><span data-stu-id="1062e-131">For this sample, select the **Any digit from 0-9** checkbox.</span></span> <span data-ttu-id="1062e-132">これを選択すると、パターンリストで使用される各 "0" 値が 0 ~ 9 の任意の数字になります。</span><span class="sxs-lookup"><span data-stu-id="1062e-132">Selecting this recognizes each "0" value used in your pattern list to be any digit from 0 through 9.</span></span>

   ![0-9 の任意の数字](../media/content-understanding/digit-identity.png)

<span data-ttu-id="1062e-134">同様に、テキスト文字を含むパターンリストを作成する場合は、 チェックボックスから **a-zの任意の文字**を選びます。</span><span class="sxs-lookup"><span data-stu-id="1062e-134">Similarly, if you create a pattern list that includes text characters, select the **Any letter from a-z** checkbox.</span></span> <span data-ttu-id="1062e-135">これを選択すると、パターンリストで使用されている "a"文字が "a" ~ "z" のいずれかの文字と認識されます。</span><span class="sxs-lookup"><span data-stu-id="1062e-135">Selecting this recognizes each "a" character used in the pattern list to be any character from "a" to "z".</span></span>

<span data-ttu-id="1062e-136">たとえば、 **日付** パターンリストを作成した場合、 *2020年1月1日*などの日付形式が認識されるようにするには、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="1062e-136">For example, if you create a **Date** pattern list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="1062e-137">*aaa 0, 0000* *aaa 00, 0000* をパターンリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="1062e-137">Add *aaa 0, 0000* and *aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="1062e-138">**a-z の の任意の文字** が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1062e-138">Make sure that **Any letter from a-z** is also selected.</span></span>

   ![A ~ z の任意の文字](../media/content-understanding/any-letter.png)

<span data-ttu-id="1062e-140">また、[パターン] リストに大文字と小文字の区別をする要件がある場合は、[ **大文字のみを区別する** ] チェックボックスをオンにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1062e-140">Additionally, if you have capitalization requirements in your pattern list, you have the option to select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="1062e-141">日付の例では、月の最初の文字を大文字にする必要がある場合、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="1062e-141">For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="1062e-142">*Aaa 0, 0000*および *Aaa 00, 0000* をパターンリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="1062e-142">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="1062e-143">**すべて大文字のみ**が選択されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="1062e-143">Make sure that **Only exact capitalization** is also selected.</span></span>

   ![確実に大文字のみ](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="1062e-145">パターンリストの説明を手動で作成する代わりに、 [説明ライブラリ]() を使用して、共通パターンのリストにあらかじめ用意されているパターンリストテンプレート ( *日付*、 *電話番号*、 *クレジットカード番号*など) を使用します。</span><span class="sxs-lookup"><span data-stu-id="1062e-145">Instead of manually creating pattern list explanation, use the [explanation library]() to use pre-made pattern list templates for common pattern list, such as *date*, *phone number*, *credit card number*, etc..</span></span> 

## <a name="proximity"></a><span data-ttu-id="1062e-146">近接性</span><span class="sxs-lookup"><span data-stu-id="1062e-146">Proximity</span></span> 

<span data-ttu-id="1062e-147">類似性の説明の種類は、モデルが他のデータがどの程度自分と似ているかを定義することによって、データを特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1062e-147">The proximity explanation type helps your model identify data through defining how close another piece of data is to it.</span></span> <span data-ttu-id="1062e-148">たとえば、モデルでは、顧客 にラベルを付けるために、*住所の番地*と *電話番号*の2つの説明を定義しました。</span><span class="sxs-lookup"><span data-stu-id="1062e-148">For example, in your model, you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="1062e-149">また、お客様の電話番号は番地の前に常に表示されることが分かります。</span><span class="sxs-lookup"><span data-stu-id="1062e-149">You also notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="1062e-150">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="1062e-150">Alex Wilburn</span></span><br>
<span data-ttu-id="1062e-151">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="1062e-151">555-555-5555</span></span><br>
<span data-ttu-id="1062e-152">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="1062e-152">One Microsoft Way</span></span><br>
<span data-ttu-id="1062e-153">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="1062e-153">Redmond, WA 98034</span></span><br>

<span data-ttu-id="1062e-154">[類似性の説明を使用して、ドキュメント中の住所の番地をうまく特定するには、電話番号の説明はあまりに類似性が低いことを定義します。</span><span class="sxs-lookup"><span data-stu-id="1062e-154">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

   ![類似性の説明](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a><span data-ttu-id="1062e-156">トークンとは?</span><span class="sxs-lookup"><span data-stu-id="1062e-156">What are tokens?</span></span>

<span data-ttu-id="1062e-157">類似性の説明の種類を使用するには、トークンが何かを理解する必要があります。トークンの数は、ある説明から別の説明への距離を、類似性の説明がどのように測定しているかを表しています。</span><span class="sxs-lookup"><span data-stu-id="1062e-157">In order to use the proximity explanation type, understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span>  

<span data-ttu-id="1062e-158">トークンは、文字と数字を連続しているスパン (スペースや句読点はありません) です。</span><span class="sxs-lookup"><span data-stu-id="1062e-158">A token is a continuous span (no spaces or punctuation) of letters and numbers.</span></span> <span data-ttu-id="1062e-159">スペースはトークンではありません。</span><span class="sxs-lookup"><span data-stu-id="1062e-159">A space is NOT a token.</span></span> <span data-ttu-id="1062e-160">各区切り文字はトークンです。</span><span class="sxs-lookup"><span data-stu-id="1062e-160">Each punctuation character is a token.</span></span> <span data-ttu-id="1062e-161">次の表は、語句の中のトークン数を決定する方法の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="1062e-161">The following table shows some examples of how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="1062e-162">語句</span><span class="sxs-lookup"><span data-stu-id="1062e-162">Phrase</span></span>|<span data-ttu-id="1062e-163">トークン数</span><span class="sxs-lookup"><span data-stu-id="1062e-163">Number of tokens</span></span>|<span data-ttu-id="1062e-164">説明</span><span class="sxs-lookup"><span data-stu-id="1062e-164">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="1062e-165">1</span><span class="sxs-lookup"><span data-stu-id="1062e-165">1</span></span>|<span data-ttu-id="1062e-166">句読点やスペースを含まない1つの単語。</span><span class="sxs-lookup"><span data-stu-id="1062e-166">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="1062e-167">1</span><span class="sxs-lookup"><span data-stu-id="1062e-167">1</span></span>|<span data-ttu-id="1062e-168">レコードロケーター番号。</span><span class="sxs-lookup"><span data-stu-id="1062e-168">A record locator number.</span></span> <span data-ttu-id="1062e-169">数字と文字が含まれる場合がありますが、区切り記号はありません。</span><span class="sxs-lookup"><span data-stu-id="1062e-169">It may have numbers and letters, but does not have any punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="1062e-170">5</span><span class="sxs-lookup"><span data-stu-id="1062e-170">5</span></span>|<span data-ttu-id="1062e-171">電話番号</span><span class="sxs-lookup"><span data-stu-id="1062e-171">A phone number.</span></span> <span data-ttu-id="1062e-172">句読点はそれぞれ1つのトークンです。  `425-555-5555`は、5トークンとなります。</span><span class="sxs-lookup"><span data-stu-id="1062e-172">Each punctuation mark is a single token so  `425-555-5555` would be 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="1062e-173">7</span><span class="sxs-lookup"><span data-stu-id="1062e-173">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="1062e-174">類似性の説明の種類を構成する</span><span class="sxs-lookup"><span data-stu-id="1062e-174">Configure the proximity explanation type</span></span>

<span data-ttu-id="1062e-175">この例では、[類似性] 設定を構成して、*電話番号*の説明が、*住所の番地* 説明から離れてもよい距離のトークンの範囲を定義できるように構成します。</span><span class="sxs-lookup"><span data-stu-id="1062e-175">For the sample, configure the proximity setting so that we can define the range of the number of tokens the *Phone number* explanation is from the *Street address number* explanation.</span></span>

<span data-ttu-id="1062e-176">電話番号と住所の番地の間にトークンがないため、最小範囲が "0" であることがわかります。</span><span class="sxs-lookup"><span data-stu-id="1062e-176">You should see that the minimum range is "0" since there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="1062e-177">ただし、サンプルドキュメントの一部の電話番号には、 *(モバイル)* という接頭語が付いています。</span><span class="sxs-lookup"><span data-stu-id="1062e-177">However, some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="1062e-178">Nestor Wilke</span><span class="sxs-lookup"><span data-stu-id="1062e-178">Nestor Wilke</span></span><br>
<span data-ttu-id="1062e-179">111-111-1111 (モバイル)</span><span class="sxs-lookup"><span data-stu-id="1062e-179">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="1062e-180">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="1062e-180">One Microsoft Way</span></span><br>
<span data-ttu-id="1062e-181">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="1062e-181">Redmond, WA 98034</span></span><br>

<span data-ttu-id="1062e-182">*(モバイル)* には次の3つのトークンがあります。</span><span class="sxs-lookup"><span data-stu-id="1062e-182">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="1062e-183">語句</span><span class="sxs-lookup"><span data-stu-id="1062e-183">Phrase</span></span>|<span data-ttu-id="1062e-184">トークン数</span><span class="sxs-lookup"><span data-stu-id="1062e-184">Token count</span></span>|
|--|--|
|<span data-ttu-id="1062e-185">(</span><span class="sxs-lookup"><span data-stu-id="1062e-185">(</span></span>|<span data-ttu-id="1062e-186">1</span><span class="sxs-lookup"><span data-stu-id="1062e-186">1</span></span>|
|<span data-ttu-id="1062e-187">モバイル</span><span class="sxs-lookup"><span data-stu-id="1062e-187">mobile</span></span>|<span data-ttu-id="1062e-188">2</span><span class="sxs-lookup"><span data-stu-id="1062e-188">2</span></span>|
|<span data-ttu-id="1062e-189">)</span><span class="sxs-lookup"><span data-stu-id="1062e-189">)</span></span>|<span data-ttu-id="1062e-190">3</span><span class="sxs-lookup"><span data-stu-id="1062e-190">3</span></span>|

<span data-ttu-id="1062e-191">0から3までの範囲を設定するには、[類似性] 設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="1062e-191">Configure the proximity setting to have a range of 0 through 3.</span></span>

   ![類似性の例](../media/content-understanding/proximity-example.png)</br>

## <a name="use-explanation-templates"></a><span data-ttu-id="1062e-193">説明テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="1062e-193">Use explanation templates</span></span>

<span data-ttu-id="1062e-194">説明用にさまざまなパターンのリスト値を手動で追加することができますが、説明ライブラリで提供されている作成済みのテンプレートを使用する方が簡単です。</span><span class="sxs-lookup"><span data-stu-id="1062e-194">While you can manually add various pattern list values for your explanation, it can be much easier to use the pre-created templates provided to you in the explanation library.</span></span>

<span data-ttu-id="1062e-195">たとえば、*日付*のバリエーションをすべて手動で追加するのではなく、パターンリストテンプレートをの*日付*を使用できます。これには、既にいくつかのパターンリスト値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1062e-195">For example, instead of manually adding all the variations for *Date*, you can use the pattern list template for *Date*, that already includes a number of pattern lists values:</span></span></br>

   ![説明ライブラリ](../media/content-understanding/explanation-template.png)</br>
 
<span data-ttu-id="1062e-197">説明ライブラリには、よく使用されるパターンリストの説明が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1062e-197">The explanation library includes a number of commonly used pattern list explanations, including:</span></span></br>

- <span data-ttu-id="1062e-198">日付</span><span class="sxs-lookup"><span data-stu-id="1062e-198">Date</span></span></br>
- <span data-ttu-id="1062e-199">Date (数値)</span><span class="sxs-lookup"><span data-stu-id="1062e-199">Date (numeric)</span></span></br>
- <span data-ttu-id="1062e-200">時間</span><span class="sxs-lookup"><span data-stu-id="1062e-200">Time</span></span></br>
- <span data-ttu-id="1062e-201">数字</span><span class="sxs-lookup"><span data-stu-id="1062e-201">Number</span></span></br>
- <span data-ttu-id="1062e-202">電話番号</span><span class="sxs-lookup"><span data-stu-id="1062e-202">Phone number</span></span></br>
- <span data-ttu-id="1062e-203">郵便番号</span><span class="sxs-lookup"><span data-stu-id="1062e-203">Zip code</span></span></br>
- <span data-ttu-id="1062e-204">文章の最初の単語</span><span class="sxs-lookup"><span data-stu-id="1062e-204">First word of sentence</span></span></br>
- <span data-ttu-id="1062e-205">クレジット カード</span><span class="sxs-lookup"><span data-stu-id="1062e-205">Credit card</span></span></br>
- <span data-ttu-id="1062e-206">社会保障番号</span><span class="sxs-lookup"><span data-stu-id="1062e-206">Social security number</span></span></br>

<span data-ttu-id="1062e-207">また、説明ライブラリには、次のような語句リストの説明も含まれます。</span><span class="sxs-lookup"><span data-stu-id="1062e-207">Note that the explanation library also includes templates for phrase list explanations as well, including:</span></span>
- <span data-ttu-id="1062e-208">文の最後</span><span class="sxs-lookup"><span data-stu-id="1062e-208">End of sentence</span></span>
- <span data-ttu-id="1062e-209">通貨</span><span class="sxs-lookup"><span data-stu-id="1062e-209">Currency</span></span>

#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="1062e-210">説明ライブラリのテンプレートを使用するには</span><span class="sxs-lookup"><span data-stu-id="1062e-210">To use a template from the explanation library</span></span>

1. <span data-ttu-id="1062e-211">モデルの **トレーニング** ページの [**説明**] セクションで、[**新しい**] を選び、[**テンプレート から**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="1062e-211">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span></br>

   ![テンプレートから作成する](../media/content-understanding/from-template.png)</br>

2.  <span data-ttu-id="1062e-213">**説明テンプレート** ページで、使用する説明を選び、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1062e-213">On the **Explanation templates** page, select the explanation you want to use, and then select **Add**.</span></span></br>

       ![テンプレートの選択](../media/content-understanding/phone-template.png)</br>

3. <span data-ttu-id="1062e-215">選択したテンプレートの情報は、 **説明を作成する** ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1062e-215">The information for the template you selected will display on the **Create an explanation** page.</span></span> <span data-ttu-id="1062e-216">必要な場合は、説明の名前を編集して、[パターン] リストの項目を追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="1062e-216">If needed, edit the explanation name, and add or remove items from the pattern list.</span></span> </br> 

   ![テンプレートを編集する](../media/content-understanding/phone-template-live.png)</br>

4. <span data-ttu-id="1062e-218">完了したら、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1062e-218">When finished, select **Save**.</span></span>
