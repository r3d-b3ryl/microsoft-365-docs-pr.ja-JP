---
title: 説明の種類
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft SharePoint の同期 Tex での説明の種類の詳細については、
ms.openlocfilehash: f4f5dbc24bef57b1801f7df1b7e2fc7ef9b08116
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295993"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="38a14-103">説明の種類の概要</span><span class="sxs-lookup"><span data-stu-id="38a14-103">Introduction to explanation types</span></span>

<span data-ttu-id="38a14-104">説明を使用して、ラベル付けする情報を定義し、ドキュメント内で抽出します。 Microsoft SharePoint の同期のモデルについて理解します。</span><span class="sxs-lookup"><span data-stu-id="38a14-104">Use explanations to help to define the information that you want to label, and extract in your document the understanding models for Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="38a14-105">説明を作成する場合は、必ず説明の種類を選択してください。</span><span class="sxs-lookup"><span data-stu-id="38a14-105">When you create an explanation, be sure to select an explanation type.</span></span> 

<span data-ttu-id="38a14-106">この記事では、さまざまな説明の種類とその使用方法を理解するのに役立つ情報を示します。</span><span class="sxs-lookup"><span data-stu-id="38a14-106">This article helps you understand the different explanation types and how they are used.</span></span>

   ![説明の種類](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="38a14-108">次の説明タイプを使用できます。</span><span class="sxs-lookup"><span data-stu-id="38a14-108">These explanation types are available:</span></span>

- <span data-ttu-id="38a14-109">**Phrase list**: ドキュメントまたは抽出する情報で使用できる単語、語句、数字、またはその他の文字のリスト。</span><span class="sxs-lookup"><span data-stu-id="38a14-109">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting.</span></span> <span data-ttu-id="38a14-110">たとえば、ユーザーが認識しているすべての医療照会ドキュメントに、 **医師を参照** しているテキスト文字列が含まれているとします。</span><span class="sxs-lookup"><span data-stu-id="38a14-110">For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span></br>

- <span data-ttu-id="38a14-111">**パターンリスト**: 抽出する情報を識別するために使用できる、数字、文字、またはその他の文字のパターンを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="38a14-111">**Pattern list**: List patterns of numbers, letters, or other characters that you can use to identify the information that you are extracting.</span></span> <span data-ttu-id="38a14-112">たとえば、識別しているすべての医療照会ドキュメントから、参照した医師の **電話番号** を抽出できます。</span><span class="sxs-lookup"><span data-stu-id="38a14-112">For example, you can extract the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span></br>

- <span data-ttu-id="38a14-113">**近接**: 説明が互いにどのように近いかを表します。</span><span class="sxs-lookup"><span data-stu-id="38a14-113">**Proximity**: Describes how close explanations are to each other.</span></span> <span data-ttu-id="38a14-114">たとえば、ストリート *番号* パターンリストは、間にトークンがない状態で、 *ストリート名* の語句リストの直前にあります (トークンについては、この記事の後半で説明します)。</span><span class="sxs-lookup"><span data-stu-id="38a14-114">For example, a *street number* pattern list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="38a14-115">語句一覧</span><span class="sxs-lookup"><span data-stu-id="38a14-115">Phrase list</span></span>

<span data-ttu-id="38a14-116">語句リストの説明タイプは、通常、モデルを通じてドキュメントを識別して分類するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="38a14-116">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="38a14-117">「 *参照する医師* 」ラベルの例で説明されているように、識別するドキュメント内で一貫している単語、語句、数字、または文字の文字列です。</span><span class="sxs-lookup"><span data-stu-id="38a14-117">As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="38a14-118">必要なものではありませんが、取り込んだ語句が文書内の一貫した場所にある場合、説明に対して適切な成功を実現できます。</span><span class="sxs-lookup"><span data-stu-id="38a14-118">While not a requirement, you can acheive better success with your explanation if the phrase you are capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="38a14-119">たとえば、文書の最初の段落には、文書の最初の段落に表示される *医師* のラベルが一貫して存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="38a14-119">For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span>

<span data-ttu-id="38a14-120">ラベルを識別する際に大文字と小文字を区別する必要がある場合は、語句リストの種類を使用すると、[ **大文字と小文字** を区別する] チェックボックスをオンにすることにより、説明にそれを指定できます。</span><span class="sxs-lookup"><span data-stu-id="38a14-120">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

   ![大文字と小文字の区別](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a><span data-ttu-id="38a14-122">パターン一覧</span><span class="sxs-lookup"><span data-stu-id="38a14-122">Pattern lists</span></span>

<span data-ttu-id="38a14-123">パターンリストの種類は、ドキュメントから情報を識別および抽出する説明を作成する場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="38a14-123">A pattern list type is especially useful when you create an explanation that identifies and extracts information from a document.</span></span> <span data-ttu-id="38a14-124">通常は、日付、電話番号、クレジットカード番号など、さまざまな形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="38a14-124">It is typically presented in different formats, such as dates, phone numbers, or credit card numbers.</span></span> <span data-ttu-id="38a14-125">たとえば、日付をさまざまな形式で表示できます (1/1/2020、1-1-2020、01/01/20、01/01/2020、Jan 1、2020など)。</span><span class="sxs-lookup"><span data-stu-id="38a14-125">For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.).</span></span> <span data-ttu-id="38a14-126">パターンリストを定義することで、わかりやすくするために、特定して抽出しようとしているデータにあらゆるバリエーションを取り込むことにより、説明がより効率的になります。</span><span class="sxs-lookup"><span data-stu-id="38a14-126">Defining a pattern list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="38a14-127">**電話番号**サンプルの場合は、モデルで認識されているすべての医療照会ドキュメントから、各参照医師の電話番号を抽出します。</span><span class="sxs-lookup"><span data-stu-id="38a14-127">For the **Phone number** sample, extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="38a14-128">説明を作成するときに、[パターン] ボックスの一覧を選択して、返される可能性があるさまざまな形式を許可します。</span><span class="sxs-lookup"><span data-stu-id="38a14-128">When you create the explanation, select the Pattern list type to allow the different formats that you may expect to be returned.</span></span>

   ![電話番号パターン一覧](../media/content-understanding/pattern-list.png)

<span data-ttu-id="38a14-130">この例では、[ **任意の数字を0-9 から** 選択します] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="38a14-130">For this sample, select the **Any digit from 0-9** checkbox.</span></span> <span data-ttu-id="38a14-131">これを選択すると、パターンリストで使用されている各 "0" 値が0から9までの数字であることを認識します。</span><span class="sxs-lookup"><span data-stu-id="38a14-131">Selecting this recognizes each "0" value used in your pattern list to be any digit from 0 through 9.</span></span>

   ![0-9 からの任意の数字](../media/content-understanding/digit-identity.png)

<span data-ttu-id="38a14-133">同様に、テキスト文字を含むパターンリストを作成する場合は、 **-z チェックボックスから任意の文字** を選択します。</span><span class="sxs-lookup"><span data-stu-id="38a14-133">Similarly, if you create a pattern list that includes text characters, select the **Any letter from a-z** checkbox.</span></span> <span data-ttu-id="38a14-134">これを選択すると、パターンリストで使用される各 "a" 文字が "a" ~ "z" のいずれかの文字として認識されます。</span><span class="sxs-lookup"><span data-stu-id="38a14-134">Selecting this recognizes each "a" character used in the pattern list to be any character from "a" to "z".</span></span>

<span data-ttu-id="38a14-135">たとえば、 **日付** パターンリストを作成している場合に、 *2020 年1月 1* 日などの日付形式が認識されるようにするには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="38a14-135">For example, if you create a **Date** pattern list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="38a14-136">自分のパターンリストに *aaa 0、0000* 、 *aaa 00、0000* を追加します。</span><span class="sxs-lookup"><span data-stu-id="38a14-136">Add *aaa 0, 0000* and *aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="38a14-137">**-Z からの文字**も選択されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="38a14-137">Make sure that **Any letter from a-z** is also selected.</span></span>

   ![A ~ z の任意の文字](../media/content-understanding/any-letter.png)

<span data-ttu-id="38a14-139">また、パターンリストに大文字/小文字の要件がある場合は、[ **大文字と小文字** を区別する] チェックボックスのみを選択できます。</span><span class="sxs-lookup"><span data-stu-id="38a14-139">Additionally, if you have capitalization requirements in your pattern list, you have the option to select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="38a14-140">日付の例では、月の最初の文字を大文字にする必要がある場合は、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="38a14-140">For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="38a14-141">自分のパターンリストに *aaa 0、0000* 、 *aaa 00、0000* を追加します。</span><span class="sxs-lookup"><span data-stu-id="38a14-141">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="38a14-142">**完全な大文字と小文字だけ**も選択されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="38a14-142">Make sure that **Only exact capitalization** is also selected.</span></span>

   ![正確な大文字と小文字のみ](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="38a14-144">パターンリストの説明を手動で作成する代わりに、 [説明ライブラリ]() を使用して、 *日付*、 *電話番号*、 *クレジットカード番号*などの共通パターンリストに対して事前に定義されたパターンリストテンプレートを使用します。</span><span class="sxs-lookup"><span data-stu-id="38a14-144">Instead of manually creating pattern list explanation, use the [explanation library]() to use pre-made pattern list templates for common pattern list, such as *date*, *phone number*, *credit card number*, etc..</span></span> 

## <a name="proximity"></a><span data-ttu-id="38a14-145">近接性</span><span class="sxs-lookup"><span data-stu-id="38a14-145">Proximity</span></span> 

<span data-ttu-id="38a14-146">近接説明の種類は、モデルがデータを識別する際に、別のデータをどのように閉じるかを定義するのに便利です。</span><span class="sxs-lookup"><span data-stu-id="38a14-146">The proximity explanation type helps your model identify data through defining how close another piece of data is to it.</span></span> <span data-ttu-id="38a14-147">たとえば、モデルでは、顧客の *番地* と *電話番号*の両方をラベルする2つの説明が定義されています。</span><span class="sxs-lookup"><span data-stu-id="38a14-147">For example, in your model, you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="38a14-148">また、顧客の電話番号は、番地の番号の前に常に表示されることにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="38a14-148">You also notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="38a14-149">Alex/書き込み</span><span class="sxs-lookup"><span data-stu-id="38a14-149">Alex Wilburn</span></span><br>
<span data-ttu-id="38a14-150">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="38a14-150">555-555-5555</span></span><br>
<span data-ttu-id="38a14-151">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="38a14-151">One Microsoft Way</span></span><br>
<span data-ttu-id="38a14-152">Redmond、ワシントン98034</span><span class="sxs-lookup"><span data-stu-id="38a14-152">Redmond, WA 98034</span></span><br>

<span data-ttu-id="38a14-153">近接説明を使用して、ドキュメント内の番地を識別するための電話番号の説明の詳細を定義します。</span><span class="sxs-lookup"><span data-stu-id="38a14-153">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

   ![近接説明](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a><span data-ttu-id="38a14-155">トークンとは</span><span class="sxs-lookup"><span data-stu-id="38a14-155">What are tokens?</span></span>

<span data-ttu-id="38a14-156">近接度の説明の種類を使用するには、トークンの数は、ある説明から別の説明への距離を近接説明で測定する方法として、トークンの数を理解します。</span><span class="sxs-lookup"><span data-stu-id="38a14-156">In order to use the proximity explanation type, understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span>  

<span data-ttu-id="38a14-157">トークンは、文字と数字の連続したスパン (スペースや句読点なし) です。</span><span class="sxs-lookup"><span data-stu-id="38a14-157">A token is a continuous span (no spaces or punctuation) of letters and numbers.</span></span> <span data-ttu-id="38a14-158">スペースはトークンではありません。</span><span class="sxs-lookup"><span data-stu-id="38a14-158">A space is NOT a token.</span></span> <span data-ttu-id="38a14-159">各区切り文字はトークンです。</span><span class="sxs-lookup"><span data-stu-id="38a14-159">Each punctuation character is a token.</span></span> <span data-ttu-id="38a14-160">次の表は、語句内のトークンの数を確認する方法の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="38a14-160">The following table shows some examples of how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="38a14-161">Sdl</span><span class="sxs-lookup"><span data-stu-id="38a14-161">Phrase</span></span>|<span data-ttu-id="38a14-162">トークンの数</span><span class="sxs-lookup"><span data-stu-id="38a14-162">Number of tokens</span></span>|<span data-ttu-id="38a14-163">説明</span><span class="sxs-lookup"><span data-stu-id="38a14-163">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="38a14-164">1 </span><span class="sxs-lookup"><span data-stu-id="38a14-164">1</span></span>|<span data-ttu-id="38a14-165">句読点またはスペースを含まない1つの単語。</span><span class="sxs-lookup"><span data-stu-id="38a14-165">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="38a14-166">1 </span><span class="sxs-lookup"><span data-stu-id="38a14-166">1</span></span>|<span data-ttu-id="38a14-167">レコードロケーター番号。</span><span class="sxs-lookup"><span data-stu-id="38a14-167">A record locator number.</span></span> <span data-ttu-id="38a14-168">数字と文字を含めることができますが、句読点は含まれません。</span><span class="sxs-lookup"><span data-stu-id="38a14-168">It may have numbers and letters, but does not have any punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="38a14-169">5 </span><span class="sxs-lookup"><span data-stu-id="38a14-169">5</span></span>|<span data-ttu-id="38a14-170">電話番号。</span><span class="sxs-lookup"><span data-stu-id="38a14-170">A phone number.</span></span> <span data-ttu-id="38a14-171">各句読点マークは1つのトークンであるため、5つのトークンが  `425-555-5555` あります。</span><span class="sxs-lookup"><span data-stu-id="38a14-171">Each punctuation mark is a single token so  `425-555-5555` would be 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="38a14-172">7 </span><span class="sxs-lookup"><span data-stu-id="38a14-172">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="38a14-173">近接説明の種類を構成する</span><span class="sxs-lookup"><span data-stu-id="38a14-173">Configure the proximity explanation type</span></span>

<span data-ttu-id="38a14-174">この例では、 *電話番号* の説明が *番地* の説明からのトークン数の範囲を定義できるように近接設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="38a14-174">For the sample, configure the proximity setting so that we can define the range of the number of tokens the *Phone number* explanation is from the *Street address number* explanation.</span></span>

<span data-ttu-id="38a14-175">電話番号とストリートアドレス番号の間にトークンがないため、最小範囲が "0" であることがわかります。</span><span class="sxs-lookup"><span data-stu-id="38a14-175">You should see that the minimum range is "0" since there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="38a14-176">ただし、サンプルドキュメント内の一部の電話番号は、 *(mobile)* に追加されています。</span><span class="sxs-lookup"><span data-stu-id="38a14-176">However, some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="38a14-177">Nestor/Ke</span><span class="sxs-lookup"><span data-stu-id="38a14-177">Nestor Wilke</span></span><br>
<span data-ttu-id="38a14-178">111-111-1111 (モバイル)</span><span class="sxs-lookup"><span data-stu-id="38a14-178">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="38a14-179">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="38a14-179">One Microsoft Way</span></span><br>
<span data-ttu-id="38a14-180">Redmond、ワシントン98034</span><span class="sxs-lookup"><span data-stu-id="38a14-180">Redmond, WA 98034</span></span><br>

<span data-ttu-id="38a14-181">*(Mobile)* には、次の3つのトークンがあります。</span><span class="sxs-lookup"><span data-stu-id="38a14-181">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="38a14-182">Sdl</span><span class="sxs-lookup"><span data-stu-id="38a14-182">Phrase</span></span>|<span data-ttu-id="38a14-183">トークンの数</span><span class="sxs-lookup"><span data-stu-id="38a14-183">Token count</span></span>|
|--|--|
|<span data-ttu-id="38a14-184">(</span><span class="sxs-lookup"><span data-stu-id="38a14-184">(</span></span>|<span data-ttu-id="38a14-185">1 </span><span class="sxs-lookup"><span data-stu-id="38a14-185">1</span></span>|
|<span data-ttu-id="38a14-186">体</span><span class="sxs-lookup"><span data-stu-id="38a14-186">mobile</span></span>|<span data-ttu-id="38a14-187">2 </span><span class="sxs-lookup"><span data-stu-id="38a14-187">2</span></span>|
|<span data-ttu-id="38a14-188">)</span><span class="sxs-lookup"><span data-stu-id="38a14-188">)</span></span>|<span data-ttu-id="38a14-189">3 </span><span class="sxs-lookup"><span data-stu-id="38a14-189">3</span></span>|

<span data-ttu-id="38a14-190">0 ~ 3 の範囲の近接設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="38a14-190">Configure the proximity setting to have a range of 0 through 3.</span></span>

   ![近接の例](../media/content-understanding/proximity-example.png)</br>

## <a name="use-the-explanation-library"></a><span data-ttu-id="38a14-192">説明ライブラリを使用する</span><span class="sxs-lookup"><span data-stu-id="38a14-192">Use the explanation library</span></span>

<span data-ttu-id="38a14-193">説明用にさまざまなパターンリストの値を手動で追加することができますが、説明ライブラリで提供されている作成済みテンプレートを使用する方がはるかに簡単です。</span><span class="sxs-lookup"><span data-stu-id="38a14-193">While you can manually add various pattern list values for your explanation, it's much easier to use the pre-created templates provided to you in the explanation library.</span></span>

<span data-ttu-id="38a14-194">たとえば、 *日付*のバリエーションを手動で追加する代わりに、 *日付*のパターンリストテンプレートを使用して、既にいくつかのパターンリストの値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="38a14-194">For example, instead of manually adding all the variations for *Date*, use the pattern list template for *Date*, that already includes a number of pattern lists values:</span></span></br>

   ![説明ライブラリ](../media/content-understanding/explanation-template.png)</br>
 
<span data-ttu-id="38a14-196">説明ライブラリには、一般的に使用される次のようなパターンリストの説明が含まれています。</span><span class="sxs-lookup"><span data-stu-id="38a14-196">The explanation library includes a number of commonly used pattern list explanations, including:</span></span></br>

- <span data-ttu-id="38a14-197">日付</span><span class="sxs-lookup"><span data-stu-id="38a14-197">Date</span></span></br>
- <span data-ttu-id="38a14-198">Date (数値)</span><span class="sxs-lookup"><span data-stu-id="38a14-198">Date (numeric)</span></span></br>
- <span data-ttu-id="38a14-199">Time</span><span class="sxs-lookup"><span data-stu-id="38a14-199">Time</span></span></br>
- <span data-ttu-id="38a14-200">番号</span><span class="sxs-lookup"><span data-stu-id="38a14-200">Number</span></span></br>
- <span data-ttu-id="38a14-201">電話番号</span><span class="sxs-lookup"><span data-stu-id="38a14-201">Phone number</span></span></br>
- <span data-ttu-id="38a14-202">郵便番号</span><span class="sxs-lookup"><span data-stu-id="38a14-202">Zip code</span></span></br>
- <span data-ttu-id="38a14-203">文の最初の単語</span><span class="sxs-lookup"><span data-stu-id="38a14-203">First word of sentence</span></span></br>
- <span data-ttu-id="38a14-204">クレジットカード</span><span class="sxs-lookup"><span data-stu-id="38a14-204">Credit card</span></span></br>
- <span data-ttu-id="38a14-205">社会保障番号</span><span class="sxs-lookup"><span data-stu-id="38a14-205">Social security number</span></span></br>

<span data-ttu-id="38a14-206">説明ライブラリにも、語句一覧の説明のためのテンプレートが含まれていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="38a14-206">Note that the explanation library also includes templates for phrase list explanations as well, including:</span></span>
- <span data-ttu-id="38a14-207">文の終わり</span><span class="sxs-lookup"><span data-stu-id="38a14-207">End of sentence</span></span>
- <span data-ttu-id="38a14-208">通貨</span><span class="sxs-lookup"><span data-stu-id="38a14-208">Currency</span></span>

#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="38a14-209">説明ライブラリからテンプレートを使用するには</span><span class="sxs-lookup"><span data-stu-id="38a14-209">To use a template from the explanation library</span></span>

1. <span data-ttu-id="38a14-210">モデルの [**トレーニング**] ページの [**説明**] セクションで、[**新規**] を選択し、[**テンプレートから**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="38a14-210">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span></br>

   ![テンプレートから作成](../media/content-understanding/from-template.png)</br>

2.  <span data-ttu-id="38a14-212">[ **説明テンプレート** ] ページで、使用する説明を選択し、[ **追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="38a14-212">On the **Explanation templates** page, select the explanation you want to use, and then select **Add**.</span></span></br>

       ![テンプレートの選択](../media/content-understanding/phone-template.png)</br>

3. <span data-ttu-id="38a14-214">選択したテンプレートの情報は、[説明の **作成** ] ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="38a14-214">The information for the template you selected will display on the **Create an explanation** page.</span></span> <span data-ttu-id="38a14-215">必要に応じて、説明の名前を編集し、[パターン] ボックスの一覧からアイテムを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="38a14-215">If needed, edit the explanation name, and add or remove items from the pattern list.</span></span> </br> 

   ![テンプレートの編集](../media/content-understanding/phone-template-live.png)</br>

4. <span data-ttu-id="38a14-217">完了したら、[ **保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="38a14-217">When finished, select **Save**.</span></span>
