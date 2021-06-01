---
title: Microsoft SharePoint Syntex の説明の種類
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Microsoft SharePoint Syntex の説明の種類について説明します。
ms.openlocfilehash: 515fd8af289ec7c64e14eb6d54b236ba3a8aa9f6
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706578"
---
# <a name="explanation-types-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="0008f-103">Microsoft SharePoint Syntex の説明の種類</span><span class="sxs-lookup"><span data-stu-id="0008f-103">Explanation types in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="0008f-104">説明は、 Microsoft SharePoint Syntexの文書把握モデルでラベルをつけたり、抽出する情報の定義付けをするときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0008f-104">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="0008f-105">説明を作成するときに、説明の種類を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0008f-105">When you create an explanation, you need to select an explanation type.</span></span> <span data-ttu-id="0008f-106">この記事では、さまざまな種類の説明とその使用方法の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="0008f-106">This article helps you understand the different explanation types and how they're used.</span></span>

![3 つの説明の種類を示す [説明の作成] パネルのスクリーンショット。](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="0008f-108">説明の種類には、次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="0008f-108">These explanation types are available:</span></span>

- <span data-ttu-id="0008f-109">[**語句リスト**](#phrase-list): 抽出する文書または情報で使用できる単語、語句、数字、その他の文字の一覧です。</span><span class="sxs-lookup"><span data-stu-id="0008f-109">[**Phrase list**](#phrase-list): List of words, phrases, numbers, or other characters you can use in the document or information that you're extracting.</span></span> <span data-ttu-id="0008f-110">たとえば、*委託医師* の文字列は、指定したすべての医療紹介文書に存在します。</span><span class="sxs-lookup"><span data-stu-id="0008f-110">For example, the text string *referring doctor* is in all Medical Referral documents you're identifying.</span></span> <span data-ttu-id="0008f-111">または、識別しているすべての医療紹介文書から、委託医師の *電話番号* を抽出できます。</span><span class="sxs-lookup"><span data-stu-id="0008f-111">Or the *phone number* of the referring doctor from all Medical Referral documents that you're identifying.</span></span>

- <span data-ttu-id="0008f-112">[**正規表現**](#regular-expression): パターン マッチングの表記を使用して、特定の文字パターンを検索します。</span><span class="sxs-lookup"><span data-stu-id="0008f-112">[**Regular expression**](#regular-expression): Uses a pattern-matching notation to find specific character patterns.</span></span> <span data-ttu-id="0008f-113">たとえば、正規表現を使用して、一連のドキュメント内の *メール アドレス* パターンのすべてのインスタンスを検索できます。</span><span class="sxs-lookup"><span data-stu-id="0008f-113">For example, you can use a regular expression to find all instances of an *email address* pattern in a set of documents.</span></span>

- <span data-ttu-id="0008f-114">[**類似性**](#proximity): 説明が他の説明とどの程度相互に近いかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="0008f-114">[**Proximity**](#proximity): Describes how close explanations are to each other.</span></span> <span data-ttu-id="0008f-115">たとえば、 *のストリート番号* 語句一覧は *ストリート名* 語句リストの直前にありますが、その間にトークンはありません (トークンについては、この記事の後半で説明します)。</span><span class="sxs-lookup"><span data-stu-id="0008f-115">For example, a *street number* phrase list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> <span data-ttu-id="0008f-116">近接型を使用するには、モデルに少なくとも 2 つの説明が必要です。そうでない場合、オプションは無効になります。</span><span class="sxs-lookup"><span data-stu-id="0008f-116">Using the proximity type requires you to have at least two explanations in your model or the option will be disabled.</span></span> 

## <a name="phrase-list"></a><span data-ttu-id="0008f-117">語句リスト</span><span class="sxs-lookup"><span data-stu-id="0008f-117">Phrase list</span></span>

<span data-ttu-id="0008f-118">通常、語句リストの説明の種類は、モデルを介してドキュメントを識別して分類するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="0008f-118">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="0008f-119">*委託医師* のラベルの例に記載されているように、指定した文書に常に含まれる単語、語句、数字、または文字の文字列です。</span><span class="sxs-lookup"><span data-stu-id="0008f-119">As described in the *referring doctor* label example, it's a string of words, phrases, numbers, or characters that is consistently in the documents that you're identifying.</span></span>

<span data-ttu-id="0008f-120">必須ではありませんが、キャプチャしている語句が文書内の一貫した場所にある場合は、説明をうまく行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0008f-120">While not a requirement, you can achieve better success with your explanation if the phrase you're capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="0008f-121">たとえば、*委託医師* のラベルは、文書の最初の段落に常に保存されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="0008f-121">For example, the *referring doctor* label might be consistently located in the first paragraph of the document.</span></span> <span data-ttu-id="0008f-122">また、[**[ドキュメント内の語句の位置を構成する](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#configure-where-phrases-occur-in-the-document)**] 詳細設定を使用して、特にドキュメント内の複数の場所に語句がある可能性がある場合、語句を配置する特定のエリアを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="0008f-122">You can also use the **[Configure where phrases occur in the document](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#configure-where-phrases-occur-in-the-document)** advanced setting to select specific areas where the phrase is located, especially if there's a chance that the phrase might occur in multiple locations in your document.</span></span>

<span data-ttu-id="0008f-123">ラベルを特定する際に大文字と小文字が区別される必要がある場合は、語句リストの種類を使用して、[**文字の 大文字のみ を選択する**] チェックボックスをオンにして、テキストの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="0008f-123">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

![大文字と小文字の区別](../media/content-understanding/case-sensitivity.png) 

<span data-ttu-id="0008f-125">語句の種類は、日付、電話番号、クレジットカード番号など、さまざまな形式の情報を特定して抽出する説明を作成する場合に特に有効です。</span><span class="sxs-lookup"><span data-stu-id="0008f-125">A phrase type is especially useful when you create an explanation that identifies and extracts information in different formats, such as dates, phone numbers, and credit card numbers.</span></span> <span data-ttu-id="0008f-126">たとえば、日付をさまざまな形式で表示できます (1/1/2020、1-1-2020、01/01/20、01/01/2020、Jan 1、2020 など)。</span><span class="sxs-lookup"><span data-stu-id="0008f-126">For example, a date can be displayed in many different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, or Jan 1,2020).</span></span> <span data-ttu-id="0008f-127">語句一覧を定義すると、指定して抽出するデータのバリエーションをキャプチャして、説明をより効率的にすることができます。</span><span class="sxs-lookup"><span data-stu-id="0008f-127">Defining a phrase list makes your explanation more efficient by capturing any possible variations in the data that you're trying to identify and extract.</span></span> 

<span data-ttu-id="0008f-128">*電話番号* の例では、モデルが識別するすべての医療紹介文書から、委託する各医師の電話番号を抽出します。</span><span class="sxs-lookup"><span data-stu-id="0008f-128">For the *phone number* example, you extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="0008f-129">説明を作成する場合は、電話番号が表示されるさまざまな形式を文書に入力し、可能なバリエーションをキャプチャできるようにします。</span><span class="sxs-lookup"><span data-stu-id="0008f-129">When you create the explanation, type the different formats a phone number might display in your document so that you're able to capture possible variations.</span></span> 

![電話番号の語句パターン](../media/content-understanding/pattern-list.png)

<span data-ttu-id="0008f-131">この例では、**詳細設定** で **[0〜9 の任意の数字]** チェックボックスを選択して、語句一覧で使用されている各 "0" の値が 0〜9 の任意の数字であることを認識します。</span><span class="sxs-lookup"><span data-stu-id="0008f-131">For this example, in **Advanced Settings** select the **Any digit from 0-9** checkbox to recognize each "0" value used in your phrase list to be any digit from 0 through 9.</span></span>

![0〜9 の任意の数字](../media/content-understanding/digit-identity.png)

<span data-ttu-id="0008f-133">同様に、テキスト文字を含む語句一覧を作成する場合は、**[a-zから任意の文字]** チェックボックスを選択して、語句一覧で使用される各 "a" 文字が "a" から "z" までの任意の文字であることを認識します。</span><span class="sxs-lookup"><span data-stu-id="0008f-133">Similarly, if you create a phrase list that includes text characters, select the **Any letter from a-z** checkbox to recognize each "a" character used in the phrase list to be any character from "a" to "z".</span></span>

<span data-ttu-id="0008f-134">たとえば、 **日付** の語句一覧を作成した場合、 *2020年1月1日* などの日付形式が認識されるようにするには、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="0008f-134">For example, if you create a **Date** phrase list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>

- <span data-ttu-id="0008f-135">*aaa 0, 0000* *aaa 00, 0000* を語句一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="0008f-135">Add *aaa 0, 0000* and *aaa 00, 0000* to your phrase list.</span></span>
- <span data-ttu-id="0008f-136">**a-z の の任意の文字** が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0008f-136">Make sure that **Any letter from a-z** is also selected.</span></span>

![A ~ z の任意の文字](../media/content-understanding/any-letter.png)

<span data-ttu-id="0008f-138">語句一覧に大文字と小文字の区別をする要件がある場合は、[**大文字のみを区別する**] チェックボックスをオンにできます。</span><span class="sxs-lookup"><span data-stu-id="0008f-138">If you have capitalization requirements in your phrase list, you can select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="0008f-139">日付の例では、月の最初の文字を大文字にする必要がある場合、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="0008f-139">For the date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="0008f-140">*Aaa 0, 0000* および *Aaa 00, 0000* を語句一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="0008f-140">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your phrase list.</span></span>
- <span data-ttu-id="0008f-141">**すべて大文字のみ** が選択されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0008f-141">Make sure that **Only exact capitalization** is also selected.</span></span>

![確実に大文字のみ](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="0008f-143">語句一覧の説明を手動で作成する代わりに、[説明ライブラリ](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates)を使用して、共通語句一覧に語句一覧テンプレート (*日付*、 *電話番号*、*クレジット カード番号* など) を使用します。</span><span class="sxs-lookup"><span data-stu-id="0008f-143">Instead of manually creating a phrase list explanation, use the [explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) to use phrase list templates for a common phrase list, such as *date*, *phone number*, or *credit card number*.</span></span>

## <a name="regular-expression"></a><span data-ttu-id="0008f-144">正規表現</span><span class="sxs-lookup"><span data-stu-id="0008f-144">Regular expression</span></span>

<span data-ttu-id="0008f-145">正規表現の説明の種類を使用すると、ドキュメント内の特定の文字列を見つけて識別するのに役立つパターンを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0008f-145">A regular expression explanation type allows you to create patterns that help find and identify certain text strings in documents.</span></span> <span data-ttu-id="0008f-146">正規表現を使用すると、大量のテキストをすばやく解析して次のことができます。</span><span class="sxs-lookup"><span data-stu-id="0008f-146">You can use regular expressions to quickly parse large amounts of text to:</span></span>

- <span data-ttu-id="0008f-147">特定の文字パターンを見つけます。</span><span class="sxs-lookup"><span data-stu-id="0008f-147">Find specific character patterns.</span></span>
- <span data-ttu-id="0008f-148">テキストを検証して、事前定義されたパターン (メール アドレスなど) と一致することを確認します。</span><span class="sxs-lookup"><span data-stu-id="0008f-148">Validate text to ensure that it matches a predefined pattern (such as an email address).</span></span>
- <span data-ttu-id="0008f-149">部分文字列を抽出、編集、置換、または削除します。</span><span class="sxs-lookup"><span data-stu-id="0008f-149">Extract, edit, replace, or delete text substrings.</span></span>

<span data-ttu-id="0008f-150">正規表現の種類は、メール アドレス、銀行口座番号、URL など、同様の形式の情報を特定して抽出する説明を作成する場合に特に有効です。</span><span class="sxs-lookup"><span data-stu-id="0008f-150">A regular expression type is especially useful when you create an explanation that identifies and extracts information in similar formats, such as email addresses, bank account numbers, or URLs.</span></span> <span data-ttu-id="0008f-151">たとえば、megan@contoso.com などのメール アドレスは、特定のパターン ("megan" が最初の部分、"com" が最後の部分) で表示されます。</span><span class="sxs-lookup"><span data-stu-id="0008f-151">For example, an email address, such as megan@contoso.com, is displayed in a certain pattern ("megan" is the first part, and "com" is the last part).</span></span> 

<span data-ttu-id="0008f-152">メール アドレスの正規表現は、**[A-Za-z0-9._%-]+@[A-Za-z0-9.-]+.[A-Za-z]{2,6}** です。</span><span class="sxs-lookup"><span data-stu-id="0008f-152">The regular expression for an email address is: **[A-Za-z0-9._%-]+@[A-Za-z0-9.-]+.[A-Za-z]{2,6}**.</span></span>

<span data-ttu-id="0008f-153">この式は、次の順序の 5 つの部分から構成されます。</span><span class="sxs-lookup"><span data-stu-id="0008f-153">This expression consists of five parts, in this order:</span></span>

1. <span data-ttu-id="0008f-154">次の任意の長さの文字:</span><span class="sxs-lookup"><span data-stu-id="0008f-154">Any amount of the following characters:</span></span>

   <span data-ttu-id="0008f-155">a.</span><span class="sxs-lookup"><span data-stu-id="0008f-155">a.</span></span> <span data-ttu-id="0008f-156">a から z までの文字</span><span class="sxs-lookup"><span data-stu-id="0008f-156">Letters from a to z</span></span>

   <span data-ttu-id="0008f-157">b.</span><span class="sxs-lookup"><span data-stu-id="0008f-157">b.</span></span> <span data-ttu-id="0008f-158">0 から 9 までの番号</span><span class="sxs-lookup"><span data-stu-id="0008f-158">Numbers from 0-9</span></span>

   <span data-ttu-id="0008f-159">c.</span><span class="sxs-lookup"><span data-stu-id="0008f-159">c.</span></span> <span data-ttu-id="0008f-160">ピリオド、アンダースコア、パーセント、ダッシュ</span><span class="sxs-lookup"><span data-stu-id="0008f-160">Period, underscore, percent, or dash</span></span>

2. <span data-ttu-id="0008f-161">@ 記号</span><span class="sxs-lookup"><span data-stu-id="0008f-161">The @ symbol</span></span>

3. <span data-ttu-id="0008f-162">任意の長さのメール アドレスの最初の部分と同じ文字</span><span class="sxs-lookup"><span data-stu-id="0008f-162">Any amount of the same characters as the first part of the email address</span></span>

4. <span data-ttu-id="0008f-163">ピリオド 1 つ</span><span class="sxs-lookup"><span data-stu-id="0008f-163">A period</span></span>

5. <span data-ttu-id="0008f-164">2 文字から 6 文字</span><span class="sxs-lookup"><span data-stu-id="0008f-164">Two to six letters</span></span>

<span data-ttu-id="0008f-165">正規表現の説明を追加するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="0008f-165">To add a regular expression explanation type:</span></span>

1. <span data-ttu-id="0008f-166">[**説明の作成**] パネルの [**説明の種類**] で [**正規表現**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0008f-166">From the **Create an explanation** panel, under **Explanation type**, select **Regular expression**.</span></span>

   ![[正規表現] が選択された [説明の作成] パネルを示すスクリーンショット。](../media/content-understanding/create-regular-expression.png)

2. <span data-ttu-id="0008f-168">[**正規表現**] テキスト ボックスに式を入力するか、[**テンプレートから正規表現を追加**] を選択できます。</span><span class="sxs-lookup"><span data-stu-id="0008f-168">You can either type an expression in the **Regular expression** text box or select **Add a regular expression from a template**.</span></span>

   <span data-ttu-id="0008f-169">テンプレートを使用して正規表現を追加すると、名前と正規表現がテキスト ボックスに自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="0008f-169">When you add a regular expression by using a template, it automatically adds the name and the regular expression to the text box.</span></span> <span data-ttu-id="0008f-170">たとえば、[**メール アドレス**] テンプレートを選択すると、[**説明の作成**] パネルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0008f-170">For example, if you choose the **Email address** template, the **Create an explanation** panel will be populated.</span></span>

   ![[メール アドレス] テンプレートが適用された [説明の作成] パネルを示すスクリーンショット。](../media/content-understanding/create-regular-expression-email.png)

## <a name="proximity"></a><span data-ttu-id="0008f-172">類似性</span><span class="sxs-lookup"><span data-stu-id="0008f-172">Proximity</span></span> 

<span data-ttu-id="0008f-173">類似性の説明タイプは、モデルが他のデータがどの程度自分と似ているかを定義することで、データを特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0008f-173">The proximity explanation type helps your model identify data by defining how close another piece of data is to it.</span></span> <span data-ttu-id="0008f-174">たとえば、モデルでは、顧客にラベルを付けるために、*番地* と *電話番号* の 2 つの説明を定義しました。</span><span class="sxs-lookup"><span data-stu-id="0008f-174">For example, in your model say you have defined two explanations that label both the customer *street address number* and *phone number*.</span></span> 

<span data-ttu-id="0008f-175">お客様の電話番号は番地の前に常に表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0008f-175">Notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="0008f-176">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="0008f-176">Alex Wilburn</span></span><br>
<span data-ttu-id="0008f-177">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="0008f-177">555-555-5555</span></span><br>
<span data-ttu-id="0008f-178">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="0008f-178">One Microsoft Way</span></span><br>
<span data-ttu-id="0008f-179">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="0008f-179">Redmond, WA 98034</span></span><br>

<span data-ttu-id="0008f-180">[類似性の説明を使用して、ドキュメント中の住所の番地をうまく特定するには、電話番号の説明はあまりに類似性が低いことを定義します。</span><span class="sxs-lookup"><span data-stu-id="0008f-180">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

![類似性の説明](../media/content-understanding/proximity.png)

#### <a name="what-are-tokens"></a><span data-ttu-id="0008f-182">トークンとは?</span><span class="sxs-lookup"><span data-stu-id="0008f-182">What are tokens?</span></span>

<span data-ttu-id="0008f-183">類似性の説明の種類を使用するには、トークンが何かを理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0008f-183">To use the proximity explanation type, you need to understand what a token is.</span></span> <span data-ttu-id="0008f-184">トークンの数は、ある説明から別の説明への距離を、類似性の説明がどのように測定しているかを表しています。</span><span class="sxs-lookup"><span data-stu-id="0008f-184">The number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span> <span data-ttu-id="0008f-185">トークンは、文字と数字を連続しているスパン (スペースや句読点を含まない) です。</span><span class="sxs-lookup"><span data-stu-id="0008f-185">A token is a continuous span (not including spaces or punctuation) of letters and numbers.</span></span> 

<span data-ttu-id="0008f-186">次の表は、語句の中のトークン数を決定する方法の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="0008f-186">The following table shows examples for how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="0008f-187">語句</span><span class="sxs-lookup"><span data-stu-id="0008f-187">Phrase</span></span>|<span data-ttu-id="0008f-188">トークン数</span><span class="sxs-lookup"><span data-stu-id="0008f-188">Number of tokens</span></span>|<span data-ttu-id="0008f-189">説明</span><span class="sxs-lookup"><span data-stu-id="0008f-189">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="0008f-190">1</span><span class="sxs-lookup"><span data-stu-id="0008f-190">1</span></span>|<span data-ttu-id="0008f-191">句読点やスペースを含まない1つの単語。</span><span class="sxs-lookup"><span data-stu-id="0008f-191">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="0008f-192">1</span><span class="sxs-lookup"><span data-stu-id="0008f-192">1</span></span>|<span data-ttu-id="0008f-193">レコードロケーター番号。</span><span class="sxs-lookup"><span data-stu-id="0008f-193">A record locator number.</span></span> <span data-ttu-id="0008f-194">数字と文字が含まれる場合がありますが、区切り記号はありません。</span><span class="sxs-lookup"><span data-stu-id="0008f-194">It might include numbers and letters, but doesn't have punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="0008f-195">5</span><span class="sxs-lookup"><span data-stu-id="0008f-195">5</span></span>|<span data-ttu-id="0008f-196">電話番号</span><span class="sxs-lookup"><span data-stu-id="0008f-196">A phone number.</span></span> <span data-ttu-id="0008f-197">句読点はそれぞれ1つのトークンなので、`425-555-5555` は、5 トークンとなります。</span><span class="sxs-lookup"><span data-stu-id="0008f-197">Each punctuation mark is a single token, so `425-555-5555` is 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="0008f-198">7</span><span class="sxs-lookup"><span data-stu-id="0008f-198">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="0008f-199">類似性の説明の種類を構成する</span><span class="sxs-lookup"><span data-stu-id="0008f-199">Configure the proximity explanation type</span></span>

<span data-ttu-id="0008f-200">この例では、[類似性] 設定を構成して、*番地* の説明から *電話番号* の説明のトークン数の範囲を定義します。</span><span class="sxs-lookup"><span data-stu-id="0008f-200">For the example, configure the proximity setting to define the range of the number of tokens in the *phone number* explanation from the *street address number* explanation.</span></span> <span data-ttu-id="0008f-201">電話番号と住所の番地の間にトークンがないため、最小範囲が "0" であることがわかります。</span><span class="sxs-lookup"><span data-stu-id="0008f-201">Notice that the minimum range is "0", because there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="0008f-202">ただし、サンプルドキュメントの一部の電話番号には、接頭語 *(mobile)* が追加されています。</span><span class="sxs-lookup"><span data-stu-id="0008f-202">But some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="0008f-203">Nestor Wilke</span><span class="sxs-lookup"><span data-stu-id="0008f-203">Nestor Wilke</span></span><br>
<span data-ttu-id="0008f-204">111-111-1111 (モバイル)</span><span class="sxs-lookup"><span data-stu-id="0008f-204">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="0008f-205">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="0008f-205">One Microsoft Way</span></span><br>
<span data-ttu-id="0008f-206">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="0008f-206">Redmond, WA 98034</span></span><br>

<span data-ttu-id="0008f-207">*(モバイル)* には次の3つのトークンがあります。</span><span class="sxs-lookup"><span data-stu-id="0008f-207">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="0008f-208">語句</span><span class="sxs-lookup"><span data-stu-id="0008f-208">Phrase</span></span>|<span data-ttu-id="0008f-209">トークン数</span><span class="sxs-lookup"><span data-stu-id="0008f-209">Token count</span></span>|
|--|--|
|<span data-ttu-id="0008f-210">(</span><span class="sxs-lookup"><span data-stu-id="0008f-210">(</span></span>|<span data-ttu-id="0008f-211">1</span><span class="sxs-lookup"><span data-stu-id="0008f-211">1</span></span>|
|<span data-ttu-id="0008f-212">モバイル</span><span class="sxs-lookup"><span data-stu-id="0008f-212">mobile</span></span>|<span data-ttu-id="0008f-213">2</span><span class="sxs-lookup"><span data-stu-id="0008f-213">2</span></span>|
|<span data-ttu-id="0008f-214">)</span><span class="sxs-lookup"><span data-stu-id="0008f-214">)</span></span>|<span data-ttu-id="0008f-215">3</span><span class="sxs-lookup"><span data-stu-id="0008f-215">3</span></span>|

<span data-ttu-id="0008f-216">0から3までの範囲を設定するには、[類似性] 設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="0008f-216">Configure the proximity setting to have a range of 0 through 3.</span></span>

![類似性の例](../media/content-understanding/proximity-example.png)

## <a name="configure-where-phrases-occur-in-the-document"></a><span data-ttu-id="0008f-218">ドキュメント内の語句の位置を構成する</span><span class="sxs-lookup"><span data-stu-id="0008f-218">Configure where phrases occur in the document</span></span>

<span data-ttu-id="0008f-219">説明を作成すると、既定でドキュメント全体から抽出しようとしている語句が検索されます。</span><span class="sxs-lookup"><span data-stu-id="0008f-219">When you create an explanation, by default the entire document is searched for the phrase you're trying to extract.</span></span> <span data-ttu-id="0008f-220">ただし、**[これらの語句が表示される場所]** の詳細設定を使用すると、語句が表示されるドキュメント内の特定の場所を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0008f-220">However, you can use the **Where these phrases occur** advanced setting to help in isolating a specific location in the document that a phrase occurs.</span></span> <span data-ttu-id="0008f-221">この設定は、ドキュメント内の別の場所に語句の類似のインスタンスが表示される可能性があり、正しいインスタンスが選択されていることを確認する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0008f-221">This setting is useful in situations where similar instances of a phrase might appear somewhere else in the document, and you want to make sure that the correct one is selected.</span></span>

<span data-ttu-id="0008f-222">医療紹介文書の例を参照すると、*委託医師* は常にドキュメントの第 1 段落に記載されています。</span><span class="sxs-lookup"><span data-stu-id="0008f-222">Referring to our Medical Referral document example, the *referring doctor* is always mentioned in the first paragraph of the document.</span></span> <span data-ttu-id="0008f-223">この例では、**[これらの語句が表示される場所]** の設定を使用して、このラベルをドキュメントの先頭部分、またはラベルが表示される可能性のあるその他の場所だけで検索するように説明を構成できます。</span><span class="sxs-lookup"><span data-stu-id="0008f-223">With the **Where these phrases occur** setting, in this example you can configure your explanation to search for this label only in the beginning section of the document, or any other location in which it might occur.</span></span>

![[これらの語句が表示される場所] の設定](../media/content-understanding/phrase-location.png)

<span data-ttu-id="0008f-225">この設定では、次のオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="0008f-225">You can choose the following options for this setting:</span></span>

- <span data-ttu-id="0008f-226">ファイル内の任意の場所: ドキュメント全体で語句が検索されます。</span><span class="sxs-lookup"><span data-stu-id="0008f-226">Anywhere in the file: The entire document is searched for the phrase.</span></span>

- <span data-ttu-id="0008f-227">ファイルの先頭: ドキュメントの先頭から語句の場所まで検索されます。</span><span class="sxs-lookup"><span data-stu-id="0008f-227">Beginning of the file:  The document is searched from the beginning to the phrase location.</span></span>

   ![ファイルの先頭](../media/content-understanding/beginning-of-file.png)

    <span data-ttu-id="0008f-229">ビューアでは、フェーズが表示される場所を含めるように選択ボックスを手動で調整できます。</span><span class="sxs-lookup"><span data-stu-id="0008f-229">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="0008f-230">**[終了位置]** の値が更新され、選択した領域に含まれるトークンの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0008f-230">The **End position** value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="0008f-231">**[終了位置]** の値を更新して、選択した領域を調整することもできます。</span><span class="sxs-lookup"><span data-stu-id="0008f-231">You can update the **End position** value as well to adjust the selected area.</span></span>

   ![ファイルの先頭の位置ボックス](../media/content-understanding/beginning-box.png)

- <span data-ttu-id="0008f-233">ファイルの末尾: ドキュメントの末尾から語句の場所まで検索されます。</span><span class="sxs-lookup"><span data-stu-id="0008f-233">End of the file: The document is searched from the end to the phrase location.</span></span>

   ![ファイルの末尾](../media/content-understanding/end-of-file.png)

    <span data-ttu-id="0008f-235">ビューアでは、フェーズが表示される場所を含めるように選択ボックスを手動で調整できます。</span><span class="sxs-lookup"><span data-stu-id="0008f-235">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="0008f-236">**[開始位置]** の値が更新され、選択した領域に含まれるトークンの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0008f-236">The **Starting position** value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="0008f-237">[開始位置] の値を更新して、選択した領域を調整することもできます。</span><span class="sxs-lookup"><span data-stu-id="0008f-237">You can update the Starting position value as well to adjust the selected area.</span></span>

   ![ファイルの末尾の終了ボックス](../media/content-understanding/end-box.png)

- <span data-ttu-id="0008f-239">ユーザー設定の範囲: ドキュメントは指定された範囲内で、語句の場所が検索されます。</span><span class="sxs-lookup"><span data-stu-id="0008f-239">Custom range: The document is searched within a specified range for the phrase location.</span></span>

   ![ユーザー設定の範囲](../media/content-understanding/custom-file.png)

    <span data-ttu-id="0008f-241">ビューアでは、フェーズが表示される場所を含めるように選択ボックスを手動で調整できます。</span><span class="sxs-lookup"><span data-stu-id="0008f-241">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="0008f-242">この設定では、**[開始]** と **[終了]** の位置を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0008f-242">For this setting, you need to select a **Start** and an **End** position.</span></span> <span data-ttu-id="0008f-243">これらの値は、ドキュメントの先頭のトークンの数を表します。</span><span class="sxs-lookup"><span data-stu-id="0008f-243">These values represent the number of tokens from the beginning of the document.</span></span> <span data-ttu-id="0008f-244">これらの値は手動で入力できますが、ビューアーの選択ボックスを手動で調整する方が簡単です。</span><span class="sxs-lookup"><span data-stu-id="0008f-244">While you can manually enter in these values, it's easier to manually adjust the select box in the viewer.</span></span> 
   
## <a name="use-explanation-templates"></a><span data-ttu-id="0008f-245">説明テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="0008f-245">Use explanation templates</span></span>

<span data-ttu-id="0008f-246">説明用にさまざまなフレーズ リスト値を手動で追加できますが、説明ライブラリで提供されているテンプレートを使用する方が簡単な場合があります。</span><span class="sxs-lookup"><span data-stu-id="0008f-246">While you can manually add various phrase list values for your explanation, it can be easier to use the templates provided to you in the explanation library.</span></span>

<span data-ttu-id="0008f-247">たとえば、*日付* のすべてのバリエーションを手動で追加する代わりに、*日付* のフレーズ リスト テンプレートを使用できます。これには、すでに多くのフレーズ リスト値が含まれているためです。</span><span class="sxs-lookup"><span data-stu-id="0008f-247">For example, instead of manually adding all the variations for *date*, you can use the phrase list template for *date* because it already includes many phrase lists values:</span></span>

![説明ライブラリ](../media/content-understanding/explanation-template.png)
 
<span data-ttu-id="0008f-249&quot;>説明ライブラリには、次のような一般的に使用される *フレーズ リスト* の説明が含まれています。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;0008f-249&quot;>The explanation library includes commonly used *phrase list* explanations, including:</span></span>

- <span data-ttu-id=&quot;0008f-250&quot;>日付: 予定表の日付、すべての形式。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;0008f-250&quot;>Date: Calendar dates, all formats.</span></span> <span data-ttu-id=&quot;0008f-251&quot;>テキストと数値を含む (たとえば、&quot;Dec 9, 2020")。</span><span class="sxs-lookup"><span data-stu-id="0008f-251">Includes text and numbers (for example, "Dec 9, 2020").</span></span>
- <span data-ttu-id="0008f-252">日付（数値）: 予定表の日付、すべての形式。</span><span class="sxs-lookup"><span data-stu-id="0008f-252">Date (numeric): Calendar dates, all formats.</span></span> <span data-ttu-id="0008f-253">数値が含まれます (例: 1-11-2020)。</span><span class="sxs-lookup"><span data-stu-id="0008f-253">Includes numbers (for example, 1-11-2020).</span></span>
- <span data-ttu-id="0008f-254">時刻: 12 時間と 24 時間表示。</span><span class="sxs-lookup"><span data-stu-id="0008f-254">Time: 12 and 24 hour formats.</span></span>
- <span data-ttu-id="0008f-255">数値: 最大 2 桁の小数点の正の数と負の数。</span><span class="sxs-lookup"><span data-stu-id="0008f-255">Number: Positive and negative numbers up to two decimals.</span></span> 
- <span data-ttu-id="0008f-256">パーセンテージ: パーセンテージを表すパターンの一覧。</span><span class="sxs-lookup"><span data-stu-id="0008f-256">Percentage: A list of patterns representing a percentage.</span></span> <span data-ttu-id="0008f-257">たとえば、1%、11%、100%、11.11% などです。</span><span class="sxs-lookup"><span data-stu-id="0008f-257">For example, 1%, 11%, 100%, or 11.11%.</span></span>
- <span data-ttu-id="0008f-258">電話番号: 米国および国際一般的な形式。</span><span class="sxs-lookup"><span data-stu-id="0008f-258">Phone number: Common US and International formats.</span></span> <span data-ttu-id="0008f-259">たとえば、000 000 0000、000-000-0000、(000)000-0000、(000) 000-0000 などです。</span><span class="sxs-lookup"><span data-stu-id="0008f-259">For example, 000 000 0000, 000-000-0000, (000)000-0000, or (000) 000-0000.</span></span>
- <span data-ttu-id="0008f-260">郵便番号: 米国の郵便番号の形式。</span><span class="sxs-lookup"><span data-stu-id="0008f-260">Zip code: US Zip code formats.</span></span> <span data-ttu-id="0008f-261">たとえば、11111、11111-1111 などです。</span><span class="sxs-lookup"><span data-stu-id="0008f-261">For example, 11111, 11111-1111.</span></span>
- <span data-ttu-id="0008f-262">文の最初の単語: 最大 9 文字の単語の一般的なパターン。</span><span class="sxs-lookup"><span data-stu-id="0008f-262">First word of sentence: Common patterns for words up to nine characters.</span></span> 
- <span data-ttu-id="0008f-263">文の末尾: 文の末尾の一般的な句読点。</span><span class="sxs-lookup"><span data-stu-id="0008f-263">End of sentence: Common punctuation for end of a sentence.</span></span>
- <span data-ttu-id="0008f-264">クレジット カード: 一般的なクレジット カード番号の書式。</span><span class="sxs-lookup"><span data-stu-id="0008f-264">Credit card: Common credit card number formats.</span></span> <span data-ttu-id="0008f-265">たとえば、1111-1111-1111-111 などです。</span><span class="sxs-lookup"><span data-stu-id="0008f-265">For example, 1111-1111-1111-1111.</span></span> 
- <span data-ttu-id="0008f-p132">社会保障番号: 米国の社会保障番号の書式。たとえば、111-11-1111 などです。</span><span class="sxs-lookup"><span data-stu-id="0008f-p132">Social security number: US Social Security Number format. For example, 111-11-1111.</span></span> 
- <span data-ttu-id="0008f-268">チェック ボックス: 入力済みチェック ボックスのバリエーションを表す語句一覧。</span><span class="sxs-lookup"><span data-stu-id="0008f-268">Checkbox: A phrase list representing variations on a filled in checkbox.</span></span> <span data-ttu-id="0008f-269">たとえば、_X_、_ _X_ などです。</span><span class="sxs-lookup"><span data-stu-id="0008f-269">For example, _X_, _ _X_.</span></span>
- <span data-ttu-id="0008f-270">通貨: 主要な国際記号。</span><span class="sxs-lookup"><span data-stu-id="0008f-270">Currency: Major international symbols.</span></span> <span data-ttu-id="0008f-271">たとえば、 ＄などです。</span><span class="sxs-lookup"><span data-stu-id="0008f-271">For example, $.</span></span> 
- <span data-ttu-id="0008f-272">電子メール CC: "CC:" という用語を含む語句一覧。多くの場合、メッセージが送信された他のユーザーまたはグループの名前またはメール アドレスの近くに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0008f-272">Email CC: A phrase list with the term 'CC:', often found near the names or email addresses of other people or groups the message was sent to.</span></span>
- <span data-ttu-id="0008f-273">メールの日付: "Sent on:" という用語を含む語句一覧です。多くの場合、メールの送信日の近くに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0008f-273">Email date: A phrase list with the term 'Sent on:', often found near the date the email was sent.</span></span>
- <span data-ttu-id="0008f-274">電子メール応答: メールの一般的な起句。</span><span class="sxs-lookup"><span data-stu-id="0008f-274">Email greeting: Common opening lines for emails.</span></span>
- <span data-ttu-id="0008f-275">電子メール受信者: "To:" という用語を含む語句一覧。多くの場合、メッセージが送信されたユーザーまたはグループの名前またはメール アドレスの近くに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0008f-275">Email recipient: A phrase list with the term 'To:', often found near the names or email addresses of people or groups the message was sent to.</span></span> 
- <span data-ttu-id="0008f-276">メールの送信者: "差出人:" という用語を含む語句一覧。多くの場合、送信者の名前またはメールアドレスの近くに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0008f-276">Email sender: A phrase list with the term 'From:', often found near the sender's name or email address.</span></span> 
- <span data-ttu-id="0008f-277">メールの件名: "Subject:" という用語を含む語句一覧です。多くの場合、メールの件名の近くに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0008f-277">Email subject: A phrase list with the term 'Subject:', often found near the email's subject.</span></span>

<span data-ttu-id="0008f-278">説明ライブラリには、次のような一般的に使用される *正規表現* の説明も含まれています。</span><span class="sxs-lookup"><span data-stu-id="0008f-278">The explanation library also includes commonly used *regular expression* explanations, including:</span></span>

- <span data-ttu-id="0008f-279">6 - 17 桁の数字: 6 - 17 桁の任意の数字に一致します。</span><span class="sxs-lookup"><span data-stu-id="0008f-279">6 to 17 digit numbers: Matches any number from 6 to 17 digits long.</span></span> <span data-ttu-id="0008f-280">米国の銀行口座番号はこのパターンに当てはまります。</span><span class="sxs-lookup"><span data-stu-id="0008f-280">US bank account numbers fit this pattern.</span></span>
- <span data-ttu-id="0008f-281">メール アドレス: meganb@contoso.com などの一般的な種類のメール アドレスに一致します。</span><span class="sxs-lookup"><span data-stu-id="0008f-281">Email address: Matches a common type of email address like meganb@contoso.com.</span></span>
- <span data-ttu-id="0008f-282">米国納税者 ID 番号: 9 で始まる 3 桁の数字と、それに続く 7 または 8 で始まる 6 桁の数字に一致します。</span><span class="sxs-lookup"><span data-stu-id="0008f-282">US taxpayer ID number: Matches a three-digit number starting with 9 followed by a 6 digit number starting with 7 or 8.</span></span> 
- <span data-ttu-id="0008f-283">Web アドレス (URL): http:// または https:// で始まる Web アドレスの形式に一致します。</span><span class="sxs-lookup"><span data-stu-id="0008f-283">Web address (URL): Matches the format of a web address, starting with http:// or https://.</span></span>

<span data-ttu-id="0008f-284">さらに、説明ライブラリには、サンプル ファイルでラベル付けしたデータで動作する自動テンプレートの 3 つの種類も含まれています。</span><span class="sxs-lookup"><span data-stu-id="0008f-284">In addition, the explanation library includes three automatic template types that work with the data you've labeled in your example files:</span></span>

- <span data-ttu-id="0008f-285">ラベルの後: サンプル ファイルのラベルの後に表示される単語または文字です。</span><span class="sxs-lookup"><span data-stu-id="0008f-285">After label: The words or characters that occur after the labels in the example files.</span></span>
- <span data-ttu-id="0008f-286">ラベルの前: サンプル ファイルのラベルの前に表示される単語または文字です。</span><span class="sxs-lookup"><span data-stu-id="0008f-286">Before label: The words or characters that occur before the labels in the example files.</span></span>
- <span data-ttu-id="0008f-287">ラベル: サンプル ファイルの最初の 10 個までのラベルです。</span><span class="sxs-lookup"><span data-stu-id="0008f-287">Labels: Up to the first 10 labels from the example files.</span></span>

<span data-ttu-id="0008f-288">自動テンプレートの動作例を示すために、次のサンプル ファイルでは、[ラベルの前] の説明テンプレートを使用して、モデルにより多くの情報を提供し、より正確な一致を取得します。</span><span class="sxs-lookup"><span data-stu-id="0008f-288">To give you an example of how automatic templates work, in the following example file, we'll use the Before label explanation template to help give the model more information to get a more accurate match.</span></span>

![サンプル ファイル](../media/content-understanding/before-label.png)

<span data-ttu-id="0008f-290">[ラベルの前] 説明テンプレートを選択すると、サンプル ファイルのラベルの前に表示される最初の単語セットが検索されます。</span><span class="sxs-lookup"><span data-stu-id="0008f-290">When you select the Before label explanation template, it will look for the first set of words that appear before the label in your example files.</span></span> <span data-ttu-id="0008f-291">この例では、最初のサンプル ファイルで識別される単語は「現在」です。</span><span class="sxs-lookup"><span data-stu-id="0008f-291">In the example, the words that are identified in the first example file is "As of".</span></span>

![[ラベルの前] テンプレート](../media/content-understanding/before-label-explanation.png)

<span data-ttu-id="0008f-293">**[追加]** を選択して、テンプレートから説明を作成できます。</span><span class="sxs-lookup"><span data-stu-id="0008f-293">You can select **Add** to create an explanation from the template.</span></span>  <span data-ttu-id="0008f-294">サンプル ファイルをさらに追加すると、追加の単語が識別され、フレーズ リストに追加されます。</span><span class="sxs-lookup"><span data-stu-id="0008f-294">As you add more example files, additional words will be identified and added to the phrase list.</span></span>

![ラベルを追加する](../media/content-understanding/before-label-add.png)
 
#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="0008f-296">説明ライブラリのテンプレートを使用するには</span><span class="sxs-lookup"><span data-stu-id="0008f-296">To use a template from the explanation library</span></span>

1. <span data-ttu-id="0008f-297">モデルの **トレーニング** ページの [**説明**] セクションで、[**新しい**] を選び、[**テンプレート から**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="0008f-297">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span>

   ![[ラベルの前] を追加する](../media/content-understanding/from-template.png)

2.  <span data-ttu-id="0008f-299">**説明テンプレート** ページで、使用する説明を選び、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0008f-299">On the **Explanation templates** page, select the explanation you want to use, then select **Add**.</span></span>

    ![テンプレートの選択](../media/content-understanding/phone-template.png)

3. <span data-ttu-id="0008f-301">選択したテンプレートの情報は、 **説明を作成する** ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0008f-301">The information for the template you selected displays on the **Create an explanation** page.</span></span> <span data-ttu-id="0008f-302">必要な場合は、説明の名前を編集して、フレーズ リストの項目を追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="0008f-302">If needed, edit the explanation name and add or remove items from the phrase list.</span></span>  

    ![テンプレートを編集する](../media/content-understanding/phone-template-live.png)

4. <span data-ttu-id="0008f-304">完了したら、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0008f-304">When finished, select **Save**.</span></span>