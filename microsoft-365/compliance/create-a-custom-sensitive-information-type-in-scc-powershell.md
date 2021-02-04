---
title: PowerShell を使用してカスタムの機密情報の種類を作成する
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: コンプライアンス センターでポリシーのカスタムの機密情報の種類を作成してインポートする方法について説明します。
ms.openlocfilehash: ab96a3928105f612ab97bc8ca3a0acc3613082c3
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080682"
---
# <a name="create-a-custom-sensitive-information-type-using-powershell"></a><span data-ttu-id="5ff75-103">PowerShell を使用してカスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="5ff75-103">Create a custom sensitive information type using PowerShell</span></span>

<span data-ttu-id="5ff75-104">ここでは、PowerShell を使用して、独自のカスタムの [機密情報の種類](sensitive-information-type-entity-definitions.md)を定義する XML の *ルール パッケージ* ファイルを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-104">This topic shows you how to use PowerShell to create an XML *rule package* file that defines your own custom [sensitive information types](sensitive-information-type-entity-definitions.md).</span></span> <span data-ttu-id="5ff75-105">正規表現の作成方法を理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ff75-105">You need to know how to create a regular expression.</span></span> <span data-ttu-id="5ff75-106">たとえば、ここでは、従業員 ID を特定するカスタムの機密情報の種類を作成します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-106">As an example, this topic creates a custom sensitive information type that identifies an employee ID.</span></span> <span data-ttu-id="5ff75-107">この XML 例を始点として参照して、カスタムの XML ファイルを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="5ff75-107">You can use this example XML as a starting point for your own XML file.</span></span> <span data-ttu-id="5ff75-108">機密情報の種類が初めての場合は、「[機密情報の種類の詳細情報](sensitive-information-type-learn-about.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ff75-108">If you are new to sensitive information types, see [Learn about sensitive information types](sensitive-information-type-learn-about.md).</span></span>

<span data-ttu-id="5ff75-109">整形式の XML ファイルを作成したら、Microsoft 365 PowerShell を使用して Microsoft 365 にアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="5ff75-109">After you've created a well-formed XML file, you can upload it to Microsoft 365 by using Microsoft 365 PowerShell.</span></span> <span data-ttu-id="5ff75-110">アップロードすると、ポリシー内にあるカスタムの機密情報の種類を使用し、意図したとおりに機密情報が検出されることをテストできます。</span><span class="sxs-lookup"><span data-stu-id="5ff75-110">Then you're ready to use your custom sensitive information type in your policies and test that it's detecting the sensitive information as you intended.</span></span>

> [!NOTE]
> <span data-ttu-id="5ff75-111">PowerShell が提供する設定された制御が不要な場合は、コンプライアンス センターでカスタムの機密情報の種類を作成できます。</span><span class="sxs-lookup"><span data-stu-id="5ff75-111">If you don't need the fine grained control that PowerShell provides, you can create custom sensitive information types in the Compliance center.</span></span> <span data-ttu-id="5ff75-112">詳細については、「[カスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5ff75-112">For more information, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

## <a name="important-disclaimer"></a><span data-ttu-id="5ff75-113">重要な免責事項</span><span class="sxs-lookup"><span data-stu-id="5ff75-113">Important disclaimer</span></span>

<span data-ttu-id="5ff75-p104">お客様の環境やコンテンツ マッチの要件はさまざまに異なるため、Microsoft サポートは、カスタム分類や正規表現 (別名: RegEx) パターンを定義するなど、カスタムのコンテンツ マッチング定義を提供することの支援は行えません。カスタムのコンテンツ マッチングの開発、テスト、デバッグについては、Microsoft 365 のお客様は、内部の IT リソースを利用するか、Microsoft コンサルティング サービス (MCS) などの外部のコンサルティング リソースを利用する必要があります。サポート エンジニアは、機能の制限付きサポートを提供することはできますが、カスタムのコンテンツ マッチング開発がお客様の要件や義務を満たすことの保証はできません。提供できるサポートの種類の例として、テスト目的の正規表現パターンのサンプルが挙げられます。また、サポートは、特定の単一コンテンツにおいて期待通りに動作していない既存の RegEx パターンのトラブルシューティングを支援できます。</span><span class="sxs-lookup"><span data-stu-id="5ff75-p104">Due to the variances in customer environments and content match requirements, Microsoft Support cannot assist in providing custom content-matching definitions; e.g., defining custom classifications or regular expression (also known as RegEx) patterns. For custom content-matching development, testing, and debugging, Microsoft 365 customers will need to rely upon internal IT resources, or use an external consulting resource such as Microsoft Consulting Services (MCS). Support engineers can provide limited support for the feature, but cannot provide assurances that any custom content-matching development will fulfill the customer's requirements or obligations.  As an example of the type of support that can be provided, sample regular expression patterns may be provided for testing purposes. Or, support can assist with troubleshooting an existing RegEx pattern which is not triggering as expected with a single specific content example.</span></span>

<span data-ttu-id="5ff75-119">このトピックの[注意する必要がある潜在的な検証の問題](#potential-validation-issues-to-be-aware-of)を参照。</span><span class="sxs-lookup"><span data-stu-id="5ff75-119">See [Potential validation issues to be aware of](#potential-validation-issues-to-be-aware-of) in this topic.</span></span>

<span data-ttu-id="5ff75-120">テキストを処理するために使用されている Boost.RegEx (以前の RegEx++) エンジンの詳細については、「[Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ff75-120">For more information about the Boost.RegEx (formerly known as RegEx++) engine that's used for processing the text, see [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).</span></span>

## <a name="sample-xml-of-a-rule-package"></a><span data-ttu-id="5ff75-121">ルール パッケージのサンプル XML</span><span class="sxs-lookup"><span data-stu-id="5ff75-121">Sample XML of a rule package</span></span>

<span data-ttu-id="5ff75-p105">このトピックで作成するルール パッケージのサンプル XML を示します。要素と属性については、以降のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-p105">Here's the sample XML of the rule package that we'll create in this topic. Elements and attributes are explained in the sections below.</span></span>
  
```xml
<?xml version="1.0" encoding="UTF-16"?>
<RulePackage xmlns="http://schemas.microsoft.com/office/2011/mce">
<RulePack id="DAD86A92-AB18-43BB-AB35-96F7C594ADAA">
    <Version build="0" major="1" minor="0" revision="0"/>
    <Publisher id="619DD8C3-7B80-4998-A312-4DF0402BAC04"/>
    <Details defaultLangCode="en-us">
        <LocalizedDetails langcode="en-us">
            <PublisherName>Contoso</PublisherName>
            <Name>Employee ID Custom Rule Pack</Name>
            <Description>
            This rule package contains the custom Employee ID entity.
            </Description>
        </LocalizedDetails>
    </Details>
</RulePack>
<Rules>
<!-- Employee ID -->
    <Entity id="E1CC861E-3FE9-4A58-82DF-4BD259EAB378" patternsProximity="300" recommendedConfidence="70">
        <Pattern confidenceLevel="60">
            <IdMatch idRef="Regex_employee_id"/>
        </Pattern>
        <Pattern confidenceLevel="70">
            <IdMatch idRef="Regex_employee_id"/>
            <Match idRef="Func_us_date"/>
        </Pattern>
        <Pattern confidenceLevel="80">
            <IdMatch idRef="Regex_employee_id"/>
            <Match idRef="Func_us_date"/>
            <Any minMatches="1">
                <Match idRef="Keyword_badge" minCount="2"/>
                <Match idRef="Keyword_employee"/>
            </Any>
            <Any minMatches="0" maxMatches="0">
                <Match idRef="Keyword_false_positives_local"/>
                <Match idRef="Keyword_false_positives_intl"/>
            </Any>
        </Pattern>
    </Entity>
    <Regex id="Regex_employee_id">(\s)(\d{9})(\s)</Regex>
    <Keyword id="Keyword_employee">
        <Group matchStyle="word">
            <Term>Identification</Term>
            <Term>Contoso Employee</Term>
        </Group>
    </Keyword>
    <Keyword id="Keyword_badge">
        <Group matchStyle="string">
            <Term>card</Term>
            <Term>badge</Term>
            <Term caseSensitive="true">ID</Term>
        </Group>
    </Keyword>
    <Keyword id="Keyword_false_positives_local">
        <Group matchStyle="word">
            <Term>credit card</Term>
            <Term>national ID</Term>
        </Group>
    </Keyword>
    <Keyword id="Keyword_false_positives_intl">
        <Group matchStyle="word">
            <Term>identity card</Term>
            <Term>national ID</Term>
            <Term>EU debit card</Term>
        </Group>
    </Keyword>
    <LocalizedStrings>
        <Resource idRef="E1CC861E-3FE9-4A58-82DF-4BD259EAB378">
            <Name default="true" langcode="en-us">Employee ID</Name>
            <Description default="true" langcode="en-us">
            A custom classification for detecting Employee IDs.
            </Description>
            <Description default="false" langcode="de-de">
            Description for German locale.
            </Description>
        </Resource>
    </LocalizedStrings>
</Rules>
</RulePackage>
```

## <a name="what-are-your-key-requirements-rule-entity-pattern-elements"></a><span data-ttu-id="5ff75-p106">主な要件 [Rule、Entity、Pattern 要素]</span><span class="sxs-lookup"><span data-stu-id="5ff75-p106">What are your key requirements? [Rule, Entity, Pattern elements]</span></span>

<span data-ttu-id="5ff75-126">作業を開始する前に、ルールの XML スキーマの基本構造と、その構造を使用してカスタムの機密情報の種類を定義し、適切なコンテンツを特定できるようにする方法を理解しておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5ff75-126">Before you get started, it's helpful to understand the basic structure of the XML schema for a rule, and how you can use this structure to define your custom sensitive information type so that it will identify the right content.</span></span>
  
<span data-ttu-id="5ff75-127">1 つのルールによって 1 つまたは複数のエンティティ (機密情報の種類) が定義され、各エンティティによって 1 つまたは複数のパターンが定義されています。</span><span class="sxs-lookup"><span data-stu-id="5ff75-127">A rule defines one or more entities (sensitive information types), and each entity defines one or more patterns.</span></span> <span data-ttu-id="5ff75-128">パターンとは、メールやドキュメントなどのコンテンツを評価するときにポリシーが検索する内容です</span><span class="sxs-lookup"><span data-stu-id="5ff75-128">A pattern is what a policy looks for when it evaluates content such as email and documents.</span></span>

<span data-ttu-id="5ff75-129">このトピックの XML マークアップでは、エンティティ (機密情報の種類とも呼びます) を定義するパターンとして、ルールを使用しています。</span><span class="sxs-lookup"><span data-stu-id="5ff75-129">In this topic, the XML markup uses rule to mean the patterns that define an entity, also known as a sensitive information type.</span></span> <span data-ttu-id="5ff75-130">そのため、このトピックに出てくるルールは、条件やアクションではなく、エンティティまたは機密情報の種類と考えてください)。</span><span class="sxs-lookup"><span data-stu-id="5ff75-130">So in this topic, when you see rule, think entity or sensitive information type, not conditions and actions.</span></span>
  
### <a name="simplest-scenario-entity-with-one-pattern"></a><span data-ttu-id="5ff75-131">最もシンプルなシナリオ: パターンが 1 つのエンティティ</span><span class="sxs-lookup"><span data-stu-id="5ff75-131">Simplest scenario: entity with one pattern</span></span>

<span data-ttu-id="5ff75-132">ここでは、最も簡単なシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-132">Here's the simplest scenario.</span></span> <span data-ttu-id="5ff75-133">この例では、組織の従業員 ID を含むコンテンツを特定するポリシーが必要です。ID の書式は 9 桁の数値です。</span><span class="sxs-lookup"><span data-stu-id="5ff75-133">You want your policy to identify content that contains your organization's employee ID, which is formatted as a nine-digit number.</span></span> <span data-ttu-id="5ff75-134">この場合のパターンは、9 桁の数値を識別するルールに含まれる正規表現を示します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-134">So the pattern refers to a regular expression contained in the rule that identifies nine-digit numbers.</span></span> <span data-ttu-id="5ff75-135">9 桁の数値を含むすべてのコンテンツはこのパターンを満たします。</span><span class="sxs-lookup"><span data-stu-id="5ff75-135">Any content containing a nine-digit number satisfies the pattern.</span></span>
  
![パターンが 1 つのエンティティの図](../media/4cc82dcf-068f-43ff-99b2-bac3892e9819.png)
  
<span data-ttu-id="5ff75-137">このパターンはシンプルですが、従業員 ID ではない可能性がある 9 桁の数値を含むコンテンツと一致するため、誤検知が多数特定される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5ff75-137">However, while simple, this pattern may identify many false positives by matching content that contains any nine-digit number that is not necessarily an employee ID.</span></span>
  
### <a name="more-common-scenario-entity-with-multiple-patterns"></a><span data-ttu-id="5ff75-138">より一般的なシナリオ: パターンが複数あるエンティティ</span><span class="sxs-lookup"><span data-stu-id="5ff75-138">More common scenario: entity with multiple patterns</span></span>

<span data-ttu-id="5ff75-139">この理由から、複数のパターンを使用してエンティティを定義し、エンティティ (9 桁の数値など) だけでなく、それらのパターンで補強証拠 (キーワードや日付など) を特定する方が一般的です。</span><span class="sxs-lookup"><span data-stu-id="5ff75-139">For this reason, it's more common to define an entity by using more than one pattern, where the patterns identify supporting evidence (such as a keyword or date) in addition to the entity (such as a nine-digit number).</span></span>
  
<span data-ttu-id="5ff75-140">たとえば、従業員 ID を含むコンテンツを特定する可能性を高めるために、9 桁の数値に加え、雇用日も特定する別のパターンを定義することができます。雇用日とキーワード ("従業員 ID" など) の両方を特定する別のパターンを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="5ff75-140">For example, to increase the likelihood of identifying content that contains an employee ID, you can define another pattern that also identifies a hire date, and define yet another pattern that identifies both a hire date and a keyword (such as "employee ID"), in addition to the nine-digit number.</span></span>
  
![パターンが複数あるエンティティの図](../media/c8dc2c9d-00c6-4ebc-889a-53b41a90024a.png)
  
<span data-ttu-id="5ff75-142">この構造の重要な側面について一部を説明します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-142">Note a couple of important aspects of this structure:</span></span>
  
- <span data-ttu-id="5ff75-143">より多くの証拠が必要なパターンの方が信頼度が高くなります。</span><span class="sxs-lookup"><span data-stu-id="5ff75-143">Patterns that require more evidence have a higher confidence level.</span></span> <span data-ttu-id="5ff75-144">この機密情報の種類をポリシーに後で使用する場合、より信頼度の高い一致に対してのみ制限の多いアクション (コンテンツのブロックなど) を使用し、信頼度の低い一致には制限の少ないアクション (通知の送信など) を使用できるので便利です。</span><span class="sxs-lookup"><span data-stu-id="5ff75-144">This is useful because when you later use this sensitive information type in a policy, you can use more restrictive actions (such as block content) with only the higher-confidence matches, and you can use less restrictive actions (such as send notification) with the lower-confidence matches.</span></span>

- <span data-ttu-id="5ff75-p111">サポートされる IdMatch 要素と Match 要素は、Pattern ではなく Rule 要素の子である正規表現とキーワードを参照します。これらのサポートされる要素は、Pattern から参照されますが、Rule に含まれています。つまり、サポートされる要素の 1 つの定義 (正規表現やキーワード一覧など) は、複数のエンティティとパターンで参照できます。</span><span class="sxs-lookup"><span data-stu-id="5ff75-p111">The supporting IdMatch and Match elements reference regexes and keywords that are actually children of the Rule element, not the Pattern. These supporting elements are referenced by the Pattern but included in the Rule. This means that a single definition of a supporting element, like a regular expression or a keyword list, can be referenced by multiple entities and patterns.</span></span>

## <a name="what-entity-do-you-need-to-identify-entity-element-id-attribute"></a><span data-ttu-id="5ff75-p112">特定する必要があるエンティティ [Entity 要素、id 属性]</span><span class="sxs-lookup"><span data-stu-id="5ff75-p112">What entity do you need to identify? [Entity element, id attribute]</span></span>

<span data-ttu-id="5ff75-p113">エンティティは、明確に定義されたパターンを持つ、クレジットカード番号などの機密情報の種類です。各エンティティは、ID として一意の GUID を持っています。</span><span class="sxs-lookup"><span data-stu-id="5ff75-p113">An entity is a sensitive information type, such as a credit card number, that has a well-defined pattern. Each entity has a unique GUID as its ID.</span></span>
  
### <a name="name-the-entity-and-generate-its-guid"></a><span data-ttu-id="5ff75-152">エンティティに名前を付けて GUID を生成する</span><span class="sxs-lookup"><span data-stu-id="5ff75-152">Name the entity and generate its GUID</span></span>

1. <span data-ttu-id="5ff75-153">選択した XML エディターで、[ルール] 要素と [エンティティ] 要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-153">In your XML editor of choice, add the Rules and Entity elements.</span></span>
2. <span data-ttu-id="5ff75-154">カスタムのエンティティ名 (この例では Employee ID) を含むコメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-154">Add a comment that contains the name of your custom entity — in this example, Employee ID.</span></span> <span data-ttu-id="5ff75-155">後で、ローカライズされた文字列セクションにこのエンティティ名を追加します。この名前は、ポリシーを作成するときに UI に表示されます。</span><span class="sxs-lookup"><span data-stu-id="5ff75-155">Later, you'll add the entity name to the localized strings section, and that name is what appears in the UI when you create a policy.</span></span>
3. <span data-ttu-id="5ff75-156">エンティティの GUID を生成します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-156">Generate a GUID for your entity.</span></span> <span data-ttu-id="5ff75-157">GUID を生成する方法は複数ありますが、PowerShell で「**[guid]::NewGuid()**」と入力して簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="5ff75-157">There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing **[guid]::NewGuid()**.</span></span> <span data-ttu-id="5ff75-158">また、後でローカライズされた文字列セクションにこのエンティティ GUID を追加します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-158">Later, you'll also add the entity GUID to the localized strings section.</span></span>
  
![Rules および Entity 要素を示す XML マークアップ](../media/c46c0209-0947-44e0-ac3a-8fd5209a81aa.png)
  
## <a name="what-pattern-do-you-want-to-match-pattern-element-idmatch-element-regex-element"></a><span data-ttu-id="5ff75-p116">マッチングするパターン [Pattern 要素、IdMatch 要素、Regex 要素]</span><span class="sxs-lookup"><span data-stu-id="5ff75-p116">What pattern do you want to match? [Pattern element, IdMatch element, Regex element]</span></span>

<span data-ttu-id="5ff75-p117">パターンには、機密情報の種類が検索している内容の一覧が含まれています。この一覧には、正規表現、キーワード、組み込み関数 (正規表現を実行して日付や住所を検索するなどのタスクを実行する関数) を含めることができます。機密情報の種類には、固有の信頼度を持つ複数のパターンが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5ff75-p117">The pattern contains the list of what the sensitive information type is looking for. This can include regexes, keywords, and built-in functions (which perform tasks like running regexes to find dates or addresses). Sensitive information types can have multiple patterns with unique confidences.</span></span>
  
<span data-ttu-id="5ff75-p118">以下のすべてのパターンで共通している点は、すべてが同じ正規表現を参照していることです。この正規表現では、空白 (\s) … (\s) で囲まれた 9 桁の数値 (\d{9}) を検索しています。この正規表現は IdMatch 要素から参照されます。また、この正規表現は従業員 ID エンティティを検索するすべてのパターンに共通する要件です。IdMatch は、パターンがマッチングしようとしている識別子 (従業員 ID、クレジット カード番号、社会保障番号など) です。1 つの Pattern 要素には、1 つの IdMatch 要素のみがあります。</span><span class="sxs-lookup"><span data-stu-id="5ff75-p118">What all of the below patterns have in common is that they all reference the same regular expression, which looks for a nine-digit number (\d{9}) surrounded by white space (\s) … (\s). This regular expression is referenced by the IdMatch element and is the common requirement for all patterns that look for the Employee ID entity. IdMatch is the identifier that the pattern is to trying to match, such as Employee ID or credit card number or social security number. A Pattern element must have exactly one IdMatch element.</span></span>
  
![単一の Regex 要素を参照する複数の Pattern 要素を示す XML マークアップ](../media/8f3f497b-3b8b-4bad-9c6a-d9abf0520854.png)
  
<span data-ttu-id="5ff75-171">パターンを満たす場合は、数と信頼度が返され、ポリシーの条件に使用できます。</span><span class="sxs-lookup"><span data-stu-id="5ff75-171">When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your policy.</span></span> <span data-ttu-id="5ff75-172">機密情報の種類を検出する条件をポリシーに追加する場合、次のように数と信頼度を編集できます。</span><span class="sxs-lookup"><span data-stu-id="5ff75-172">When you add a condition for detecting a sensitive information type to a policy, you can edit the count and confidence level as shown here.</span></span> <span data-ttu-id="5ff75-173">信頼度 (一致精度とも呼ばれます) については、このトピックで後述します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-173">Confidence level (also called match accuracy) is explained later in this topic.</span></span>
  
![インスタンス数と一致精度オプション](../media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)
  
<span data-ttu-id="5ff75-p120">正規表現を作成するときは、潜在的な問題があることに注意してください。たとえば、特定されるコンテンツ数が多すぎる正規表現を作成し、アップロードすると、パフォーマンスに影響する可能性があります。このような潜在的な問題の詳細については、後述の「[注意する必要がある潜在的な検証の問題](#potential-validation-issues-to-be-aware-of)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ff75-p120">When you create your regular expression, keep in mind that there are potential issues to be aware of. For example, if you write and upload a regex that identifies too much content, this can impact performance. To learn more about these potential issues, see the later section [Potential validation issues to be aware of](#potential-validation-issues-to-be-aware-of).</span></span>
  
## <a name="do-you-want-to-require-additional-evidence-match-element-mincount-attribute"></a><span data-ttu-id="5ff75-p121">追加の証拠が必要な場合 [Match 要素、minCount 属性]</span><span class="sxs-lookup"><span data-stu-id="5ff75-p121">Do you want to require additional evidence? [Match element, minCount attribute]</span></span>

<span data-ttu-id="5ff75-180">パターンでは、IdMatch だけでなく、Match 要素を使用して、キーワード、正規表現、日付、住所など、追加の補強証拠を必須にすることができます。</span><span class="sxs-lookup"><span data-stu-id="5ff75-180">In addition to the IdMatch, a pattern can use the Match element to require additional supporting evidence, such as a keyword, regex, date, or address.</span></span>
  
<span data-ttu-id="5ff75-p122">1 つのパターンには複数の Match 要素を含めることができます。Pattern 要素に直接含めるか、Any 要素を使用して組み合わせることができます。複数の Match 要素の場合は、暗黙的な AND 演算子で結合されます。パターンが一致するには、すべての Match 要素を満たす必要があります。Any 要素を使用して、AND 演算子または OR 演算子を導入することもできます (詳細については後述します)。</span><span class="sxs-lookup"><span data-stu-id="5ff75-p122">A Pattern can include multiple Match elements; they can be included directly in the Pattern element or combined by using the Any element. Match elements are joined by an implicit AND operator; all Match elements must be satisfied for the pattern to be matched. You can use the Any element to introduce AND or OR operators (more on that in a later section).</span></span>
  
<span data-ttu-id="5ff75-p123">省略可能な minCount 属性を使用して、各 Match 要素で検出する必要のある一致のインスタンス数を指定できます。たとえば、キーワード一覧の少なくとも 2 つのキーワードが検出された場合にのみ、パターンを満たすものと指定することができます。</span><span class="sxs-lookup"><span data-stu-id="5ff75-p123">You can use the optional minCount attribute to specify how many instances of a match need to be found for each of the Match elements. For example, you can specify that a pattern is satisfied only when at least two keywords from a keyword list are found.</span></span>
  
![minOccurs 属性を持つ Match 要素を示す XML マークアップ](../media/607f6b5e-2c7d-43a5-a131-a649f122e15a.png)
  
### <a name="keywords-keyword-group-and-term-elements-matchstyle-and-casesensitive-attributes"></a><span data-ttu-id="5ff75-187">キーワード [Keyword 要素、Group 要素、Term 要素、matchStyle 属性、caseSensitive 属性]</span><span class="sxs-lookup"><span data-stu-id="5ff75-187">Keywords [Keyword, Group, and Term elements, matchStyle and caseSensitive attributes]</span></span>

<span data-ttu-id="5ff75-p124">従業員 ID などの機密情報を特定するときに、多くの場合、補強証拠としてキーワードが必要になります。たとえば、9 桁の数値と一致するだけでなく、"カード"、"バッジ"、"ID" などの単語を検索することがあります。このような場合に Keyword 要素を使用します。Keyword 要素には ID 属性があり、複数のパターンまたはエンティティの複数の Match 要素から参照できます。</span><span class="sxs-lookup"><span data-stu-id="5ff75-p124">When you identify sensitive information, like an employee ID, you often want to require keywords as corroborative evidence. For example, in addition to matching a nine-digit number, you may want to look for words like "card", "badge", or "ID". To do this, you use the Keyword element. The Keyword element has an ID attribute that can be referenced by multiple Match elements in multiple patterns or entities.</span></span>
  
<span data-ttu-id="5ff75-p125">キーワードは、Group 要素の Term 要素の一覧として含まれます。Group 要素には、2 つの有効値を持つ matchStyle 属性があります。</span><span class="sxs-lookup"><span data-stu-id="5ff75-p125">Keywords are included as a list of Term elements in a Group element. The Group element has a matchStyle attribute with two possible values:</span></span>
  
- <span data-ttu-id="5ff75-p126">**matchStyle="word"** word の一致は、空白または他の区切り文字で囲まれた複数の単語全体を特定します。複数の単語の一部に一致させる場合、またはアジア言語の単語と一致させる場合を除き、常に word を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5ff75-p126">**matchStyle="word"** Word match identifies whole words surrounded by white space or other delimiters. You should always use word unless you need to match parts of words or match words in Asian languages.</span></span> 
    
- <span data-ttu-id="5ff75-p127">**matchStyle="string"** string の一致は、囲んでいる文字にかかわらず、文字列を特定します。たとえば、"id" は "bid" と "idea" と一致します。アジア言語と一致させる必要がある場合、またはキーワードが他の文字列の一部に含まれる可能性がある場合にのみ、string を使用してください。</span><span class="sxs-lookup"><span data-stu-id="5ff75-p127">**matchStyle="string"** String match identifies strings no matter what they're surrounded by. For example, "id" will match "bid" and "idea". Use string only when you need to match Asian words or if your keyword may be included as part of other strings.</span></span> 
    
<span data-ttu-id="5ff75-199">最後に、Term 要素の caseSensitive 属性を使用して、大文字と小文字を含め、コンテンツがキーワードと完全に一致する必要があることを指定できます。</span><span class="sxs-lookup"><span data-stu-id="5ff75-199">Finally, you can use the caseSensitive attribute of the Term element to specify that the content must match the keyword exactly, including lower- and upper-case letters.</span></span>
  
![キーワードを参照する Match 要素を示す XML マークアップ](../media/e729ba27-dec6-46f4-9242-584c6c12fd85.png)
  
### <a name="regular-expressions-regex-element"></a><span data-ttu-id="5ff75-201">正規表現 [Regex 要素]</span><span class="sxs-lookup"><span data-stu-id="5ff75-201">Regular expressions [Regex element]</span></span>

<span data-ttu-id="5ff75-p128">この例の従業員 ID エンティティは、既に IdMatch 要素を使用して、空白で囲まれた 9 桁の数値というパターンの正規表現を参照しています。さらに、パターンに Match 要素を使用して追加の Regex 要素を参照し、米国の郵便番号の書式である 5 桁または 9 桁の数値など、補強証拠を特定することができます。</span><span class="sxs-lookup"><span data-stu-id="5ff75-p128">In this example, the employee ID entity already uses the IdMatch element to reference a regex for the pattern — a nine-digit number surrounded by whitespace. In addition, a pattern can use a Match element to reference an additional Regex element to identify corroborative evidence, such as a five- or nine-digit number in the format of a US zip code.</span></span>
  
### <a name="additional-patterns-such-as-dates-or-addresses-built-in-functions"></a><span data-ttu-id="5ff75-204">日付や住所などのその他のパターン [組み込み関数]</span><span class="sxs-lookup"><span data-stu-id="5ff75-204">Additional patterns such as dates or addresses [built-in functions]</span></span>

<span data-ttu-id="5ff75-205">組み込みの機密情報の種類だけでなく、米国の日付、EU の日付、有効期限、米国の住所など、補強証拠を特定できる組み込み関数も使用できます。</span><span class="sxs-lookup"><span data-stu-id="5ff75-205">In addition to the built-in sensitive information types, sensitive information types can also use built-in functions that can identify corroborative evidence such as a US date, EU date, expiration date, or US address.</span></span> <span data-ttu-id="5ff75-206">Microsoft 365 は、カスタム関数のアップロードをサポートしていませんが、カスタムの機密情報の種類を作成した場合は、エンティティから組み込み関数を参照できます。</span><span class="sxs-lookup"><span data-stu-id="5ff75-206">Microsoft 365 does not support uploading your own custom functions, but when you create a custom sensitive information type, your entity can reference the built-in functions.</span></span>
  
<span data-ttu-id="5ff75-207">たとえば、従業員 ID バッジには雇用日が記載されているので、このカスタム エンティティで組み込み関数 `Func_us_date` を使用して、米国で一般的に使用されている形式の日付を特定できます。</span><span class="sxs-lookup"><span data-stu-id="5ff75-207">For example, an employee ID badge has a hire date on it, so this custom entity can use the built-in function  `Func_us_date` to identify a date in the format commonly used in the US.</span></span> 
  
<span data-ttu-id="5ff75-208">詳細は、「[DLP 関数で探索する内容](what-the-dlp-functions-look-for.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ff75-208">For more information, see [What the DLP functions look for](what-the-dlp-functions-look-for.md).</span></span>
  
![組み込み関数を参照する Match 要素を示す XML マークアップ](../media/dac6eae3-9c52-4537-b984-f9f127cc9c33.png)
  
## <a name="different-combinations-of-evidence-any-element-minmatches-and-maxmatches-attributes"></a><span data-ttu-id="5ff75-210">証拠のさまざまな組み合わせ [Any 要素、minMatches 属性、maxMatches 属性]</span><span class="sxs-lookup"><span data-stu-id="5ff75-210">Different combinations of evidence [Any element, minMatches and maxMatches attributes]</span></span>

<span data-ttu-id="5ff75-p130">Pattern 要素内のすべての IdMatch 要素と Match 要素は暗黙的な AND 演算子で結合されます。パターンを満たすには、すべての一致を満たしている必要があります。ただし、Any 要素を使用して複数の Match 要素をグループ化することで、より柔軟なマッチング ロジックを作成できます。たとえば、Any 要素を使用して、子 Match 要素のすべて一致、一致なし、完全サブセットの一致を表すことができます。</span><span class="sxs-lookup"><span data-stu-id="5ff75-p130">In a Pattern element, all IdMatch and Match elements are joined by an implicit AND operator — all of the matches must be satisfied before the pattern can be satisfied. However, you can create more flexible matching logic by using the Any element to group Match elements. For example, you can use the Any element to match all, none, or an exact subset of its children Match elements.</span></span>
  
<span data-ttu-id="5ff75-p131">Any 要素には省略可能な minMatches 属性と maxMatches 属性があります。これらの属性を使用して、パターンが一致する前に満たす必要がある子 Match 要素数を定義できます。これらの属性では、一致が検出された証拠のインスタンス数ではなく、満たす必要がある Match 要素数を定義する点に注意してください。特定の一致について最小のインスタンス数を定義するには (たとえば、一覧の 2 つのキーワードなど)、Match 要素に minCount 属性を使用します (上記を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="5ff75-p131">The Any element has optional minMatches and maxMatches attributes that you can use to define how many of the children Match elements must be satisfied before the pattern is matched. Note that these attributes define the number of Match elements that must be satisfied, not the number of instances of evidence found for the matches. To define a minimum number of instances for a specific match, such as two keywords from a list, use the minCount attribute for a Match element (see above).</span></span>
  
### <a name="match-at-least-one-child-match-element"></a><span data-ttu-id="5ff75-217">少なくとも 1 つの子 Match 要素に一致する</span><span class="sxs-lookup"><span data-stu-id="5ff75-217">Match at least one child Match element</span></span>

<span data-ttu-id="5ff75-p132">最小数の Match 要素のみを満たすことを必須にするには、minMatches 属性を使用できます。実質的に、これらの Match 要素は暗黙的な OR 演算子で結合されています。この Any 要素は、米国形式の日付またはいずれかのリストのキーワードが見つかった場合に満たされます。</span><span class="sxs-lookup"><span data-stu-id="5ff75-p132">If you want to require that only a minimum number of Match elements must be met, you can use the minMatches attribute. In effect, these Match elements are joined by an implicit OR operator. This Any element is satisfied if a US-formatted date or a keyword from either list is found.</span></span>

```xml
<Any minMatches="1" >
     <Match idRef="Func_us_date" />
     <Match idRef="Keyword_employee" />
     <Match idRef="Keyword_badge" />
</Any>
```
    
### <a name="match-an-exact-subset-of-any-children-match-elements"></a><span data-ttu-id="5ff75-221">任意の子 Match 要素の完全サブセットと一致する</span><span class="sxs-lookup"><span data-stu-id="5ff75-221">Match an exact subset of any children Match elements</span></span>

<span data-ttu-id="5ff75-p133">特定の数の Match 要素を満たすことを必須にするには、minMatches と maxMatches を同じ値に設定できます。この Any 要素は、完全に一致する日付またはキーワードが見つかった場合にのみ満たされます。また、パターンはマッチングされません。</span><span class="sxs-lookup"><span data-stu-id="5ff75-p133">If you want to require that an exact number of Match elements must be met, you can set minMatches and maxMatches to the same value. This Any element is satisfied only if exactly one date or keyword is found — any more than that, and the pattern won't be matched.</span></span>

```xml
<Any minMatches="1" maxMatches="1" >
     <Match idRef="Func_us_date" />
     <Match idRef="Keyword_employee" />
     <Match idRef="Keyword_badge" />
</Any>
```
  
### <a name="match-none-of-children-match-elements"></a><span data-ttu-id="5ff75-224">子 Match 要素のいずれとも一致しない</span><span class="sxs-lookup"><span data-stu-id="5ff75-224">Match none of children Match elements</span></span>

<span data-ttu-id="5ff75-p134">パターンを満たすための特定の証拠がないことを必須にするには、minMatches と maxMatches の両方を 0 に設定できます。この方法は、誤検知を示す可能性が高いキーワード一覧やその他の証拠がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="5ff75-p134">If you want to require the absence of specific evidence for a pattern to be satisfied, you can set both minMatches and maxMatches to 0. This can be useful if you have a keyword list or other evidence that are likely to indicate a false positive.</span></span>
  
<span data-ttu-id="5ff75-p135">たとえば、従業員 ID エンティティは "ID カード" を指している可能性があるため、キーワード "カード" を探しているとします。ただし、カードという単語が "クレジット カード" という語句内にのみ出現する場合、このコンテンツの "カード" が "ID カード" を示す可能性はあまりありません。そのため、パターンを満たす単語から除外する単語の一覧にキーワードとして "クレジット カード" を追加できます。</span><span class="sxs-lookup"><span data-stu-id="5ff75-p135">For example, the employee ID entity looks for the keyword "card" because it might refer to an "ID card". However, if card appears only in the phrase "credit card", "card" in this content is unlikely to mean "ID card". So you can add "credit card" as a keyword to a list of terms that you want to exclude from satisfying the pattern.</span></span>
  
```xml
<Any minMatches="0" maxMatches="0" >
    <Match idRef="Keyword_false_positives_local" />
    <Match idRef="Keyword_false_positives_intl" />
</Any>
```

### <a name="match-a-number-of-unique-terms"></a><span data-ttu-id="5ff75-230">一意の条件の数を照合する</span><span class="sxs-lookup"><span data-stu-id="5ff75-230">Match a number of unique terms</span></span>

<span data-ttu-id="5ff75-231">一意の条件の数を照合する場合、以下の例に示されているように、*uniqueResults* パラメーターを *true* に設定して使用します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-231">If you want to match a number of unique terms, use the *uniqueResults* parameter, set to *true*, as shown in the following example:</span></span>

```xml
<Pattern confidenceLevel="75">
    <IdMatch idRef="Salary_Revision_terms" />
    <Match idRef=" Salary_Revision_ID " minCount="3" uniqueResults="true" />
</Pattern>
```

<span data-ttu-id="5ff75-232">この例では、3 つ以上の一意の一致を使用して、給与改定パターンを定義しています。</span><span class="sxs-lookup"><span data-stu-id="5ff75-232">In this example, a pattern is defined for salary revision using at least three unique matches.</span></span> 
  
## <a name="how-close-to-the-entity-must-the-other-evidence-be-patternsproximity-attribute"></a><span data-ttu-id="5ff75-p136">エンティティと他の証拠との近接度 [patternsProximity 属性]</span><span class="sxs-lookup"><span data-stu-id="5ff75-p136">How close to the entity must the other evidence be? [patternsProximity attribute]</span></span>

<span data-ttu-id="5ff75-p137">機密情報の種類で従業員 ID を表すパターンを検索していて、そのパターンの一部として、"ID" などのキーワードのような補強証拠も検索する場合があります。この証拠が互いに近くにあるほど、パターンが実際の従業員 ID になる可能性が高くなります。パターン内の他の証拠とエンティティの近接度を判断するには、Entity 要素の必須の patternsProximity 属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-p137">Your sensitive information type is looking for a pattern that represents an employee ID, and as part of that pattern it's also looking for corroborative evidence like a keyword such as "ID". It makes sense that the closer together this evidence is, the more likely the pattern is to be an actual employee ID. You can determine how close other evidence in the pattern must be to the entity by using the required patternsProximity attribute of the Entity element.</span></span>
  
![patternsProximity 属性を示す XML マークアップ](../media/e97eb7dc-b897-4e11-9325-91c742d9839b.png)
  
<span data-ttu-id="5ff75-p138">エンティティ内の各パターンに対し、そのパターンに対して指定されたすべての他の一致について、patternsProximity 属性値で IdMatch の場所からの距離 (Unicode 文字) を定義します。近接ウィンドウは、IdMatch の場所によってアンカーされ、IdMatch の左側と右側にウィンドウが展開されます。</span><span class="sxs-lookup"><span data-stu-id="5ff75-p138">For each pattern in the entity, the patternsProximity attribute value defines the distance (in Unicode characters) from the IdMatch location for all other Matches specified for that Pattern. The proximity window is anchored by the IdMatch location, with the window extending to the left and right of the IdMatch.</span></span>
  
![近接ウィンドウの図](../media/b593dfd1-5eef-4d79-8726-a28923f7c31e.png)
  
<span data-ttu-id="5ff75-p139">以下の例は、従業員 ID のカスタム エンティティの IdMatch 要素で、キーワードまたは日付の少なくとも 1 つの補完的な一致を必要とするパターン マッチングに対して、近接ウィンドウがどのように影響するかを示しています。ID2 と ID3 の場合、近接ウィンドウ内に補強証拠がまったくないか、部分的にしかないため、ID1 のみが一致します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-p139">The example below illustrates how the proximity window affects the pattern matching where IdMatch element for the employee ID custom entity requires at least one corroborating match of keyword or date. Only ID1 matches because for ID2 and ID3, either no or only partial corroborating evidence is found within the proximity window.</span></span>
  
![補強証拠と近接ウィンドウの図](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)
  
<span data-ttu-id="5ff75-p140">メールの場合、メッセージ本文と各添付ファイルは、別のアイテムとして扱われる点に注意してください。つまり、近接ウィンドウは、これらの各アイテムの終端を超えて延長されないということです。各アイテム (添付ファイルまたは本文) に、idMatch と補強証拠の両方が存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ff75-p140">Note that for email, the message body and each attachment are treated as separate items. This means that the proximity window does not extend beyond the end of each of these items. For each item (attachment or body), both the idMatch and corroborative evidence needs to reside in that item.</span></span>
  
## <a name="what-are-the-right-confidence-levels-for-different-patterns-confidencelevel-attribute-recommendedconfidence-attribute"></a><span data-ttu-id="5ff75-p141">パターンごとの適切な信頼度 [confidenceLevel 属性、recommendedConfidence 属性]</span><span class="sxs-lookup"><span data-stu-id="5ff75-p141">What are the right confidence levels for different patterns? [confidenceLevel attribute, recommendedConfidence attribute]</span></span>

<span data-ttu-id="5ff75-p142">パターンに必要な証拠が多くなるほど、パターンが一致したときに実際のエンティティ (従業員 ID など) が特定される信頼度が高くなります。たとえば、9 桁の ID 番号、雇用日、近接度の高いキーワードが必要なパターンの場合、9 桁の ID 番号のみが必要なパターンよりも信頼度が高くなります。</span><span class="sxs-lookup"><span data-stu-id="5ff75-p142">The more evidence that a pattern requires, the more confidence you have that an actual entity (such as employee ID) has been identified when the pattern is matched. For example, you have more confidence in a pattern that requires a nine-digit ID number, hire date, and keyword in close proximity, than you do in a pattern that requires only a nine-digit ID number.</span></span>
  
<span data-ttu-id="5ff75-252">Pattern 要素には必須の confidenceLevel 属性があります。</span><span class="sxs-lookup"><span data-stu-id="5ff75-252">The Pattern element has a required confidenceLevel attribute.</span></span> <span data-ttu-id="5ff75-253">confidenceLevel の値 (1 から 100 の整数) は、エンティティに含まれる各パターンの一意の ID と考えることができます。エンティティのパターンには、異なる信頼度を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ff75-253">You can think of the value of confidenceLevel (an integer between 1 and 100) as a unique ID for each pattern in an entity — the patterns in an entity must have different confidence levels that you assign.</span></span> <span data-ttu-id="5ff75-254">整数の正確な値は問題になりません。社内のコンプライアンス チームにとって意味のある数値を選択してください。</span><span class="sxs-lookup"><span data-stu-id="5ff75-254">The precise value of the integer doesn't matter — simply pick numbers that make sense to your compliance team.</span></span> <span data-ttu-id="5ff75-255">カスタムの機密情報の種類をアップロードし、ポリシーを作成したら、作成するルールの条件でその信頼度を参照できます。</span><span class="sxs-lookup"><span data-stu-id="5ff75-255">After you upload your custom sensitive information type and then create a policy, you can reference these confidence levels in the conditions of the rules that you create.</span></span>
  
![confidenceLevel 属性にさまざまな値を持つ Pattern 要素を示す XML マークアップ](../media/301e0ba1-2deb-4add-977b-f6e9e18fba8b.png)
  
<span data-ttu-id="5ff75-257">Entity には各パターン の confidenceLevel に加え、 recommendedConfidence 属性があります。</span><span class="sxs-lookup"><span data-stu-id="5ff75-257">In addition to confidenceLevel for each Pattern, the Entity has a recommendedConfidence attribute.</span></span> <span data-ttu-id="5ff75-258">recommendedConfidence 属性は、ルールの既定の信頼度と考えることができます。</span><span class="sxs-lookup"><span data-stu-id="5ff75-258">The recommended confidence attribute can be thought of as the default confidence level for the rule.</span></span> <span data-ttu-id="5ff75-259">ポリシーでルールを作成するときに、使用するルールの信頼度を指定しない場合、そのエンティティの推奨される信頼度に基づいてルールのマッチングが行われます。</span><span class="sxs-lookup"><span data-stu-id="5ff75-259">When you create a rule in a policy, if you don't specify a confidence level for the rule to use, that rule will match based on the recommended confidence level for the entity.</span></span> <span data-ttu-id="5ff75-260">ルールパッケージ内で各エンティティ ID に recommendedConfidence 属性が必須であることに注意してください。存在しない場合、機密情報の種類を使用するポリシーを保存できません。</span><span class="sxs-lookup"><span data-stu-id="5ff75-260">Please note that the recommendedConfidence attribute is mandatory for each Entity ID in the Rule Package, if missing you won't be able to save policies that use the Sensitive Information Type.</span></span> 
  
## <a name="do-you-want-to-support-other-languages-in-the-ui-of-the-compliance-center-localizedstrings-element"></a><span data-ttu-id="5ff75-261">コンプライアンス センターの UI で他の言語をサポートする場合</span><span class="sxs-lookup"><span data-stu-id="5ff75-261">Do you want to support other languages in the UI of the Compliance center?</span></span> <span data-ttu-id="5ff75-262">[LocalizedStrings 要素]</span><span class="sxs-lookup"><span data-stu-id="5ff75-262">[LocalizedStrings element]</span></span>

<span data-ttu-id="5ff75-263">コンプライアンス チームが Microsoft 365 コンプライアンス センターを使用して、異なるロケール、異なる言語のポリシーを作成する場合、カスタムの機密情報の種類の名前と説明について、ローカライズされたバージョンを用意することができます。</span><span class="sxs-lookup"><span data-stu-id="5ff75-263">If your compliance team uses the Microsoft 365 Compliance center to create polices policies in different locales and in different languages, you can provide localized versions of the name and description of your custom sensitive information type.</span></span> <span data-ttu-id="5ff75-264">コンプライアンス チームが、サポートしている言語で Microsoft 365 を使用すると、UI にローカライズされた名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5ff75-264">When your compliance team uses Microsoft 365 in a language that you support, they'll see the localized name in the UI.</span></span>
  
![インスタンス数と一致精度オプション](../media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)
  
<span data-ttu-id="5ff75-p147">Rules 要素には、LocalizedStrings 要素を含める必要があります。LocalizedStrings 要素には、カスタム エンティティの GUID を参照する Resource 要素が含まれています。また、各 Resource 要素には、1 つまたは複数の Name 要素と Description 要素が含まれており、それぞれが langcode 属性を使用して特定の言語のローカライズされた文字列を提供します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-p147">The Rules element must contain a LocalizedStrings element, which contains a Resource element that references the GUID of your custom entity. In turn, each Resource element contains one or more Name and Description elements that each use the langcode attribute to provide a localized string for a specific language.</span></span>
  
![LocalizedStrings 要素の内容を示す XML マークアップ](../media/a96fc34a-b93d-498f-8b92-285b16a7bbe6.png)
  
<span data-ttu-id="5ff75-269">ローカライズされた文字列は、カスタムの機密情報の種類がコンプライアンス センターの UI で表示される方法にのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-269">Note that you use localized strings only for how your custom sensitive information type appears in the UI of the Compliance center.</span></span> <span data-ttu-id="5ff75-270">ローカライズされた文字列を使用して、キーワード リストまたは正規表現の複数のローカライズ バージョンを提供することはできません。</span><span class="sxs-lookup"><span data-stu-id="5ff75-270">You can't use localized strings to provide different localized versions of a keyword list or regular expression.</span></span>
  
## <a name="other-rule-package-markup-rulepack-guid"></a><span data-ttu-id="5ff75-271">その他のルール パッケージ マークアップ [RulePack GUID]</span><span class="sxs-lookup"><span data-stu-id="5ff75-271">Other rule package markup [RulePack GUID]</span></span>

<span data-ttu-id="5ff75-p149">最後に、各 RulePackage の先頭には、入力する必要のある一般的な情報が含まれています。次のマークアップをテンプレートとして使用し、「. . .」プレースホルダーを自分の情報に置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="5ff75-p149">Finally, the beginning of each RulePackage contains some general information that you need to fill in. You can use the following markup as a template and replace the ". . ." placeholders with your own info.</span></span>
  
<span data-ttu-id="5ff75-p150">最も重要な点は、RulePack の GUID を生成する必要があることです。これまでにエンティティの GUID を生成しましたが、これは RulePack の 2 つ目の GUID です。GUID を生成するにはいくつかの方法がありますが、PowerShell では [guid]::NewGuid() と入力することで簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5ff75-p150">Most importantly, you'll need to generate a GUID for the RulePack. Above, you generated a GUID for the entity; this is a second GUID for the RulePack. There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing [guid]::NewGuid().</span></span>
  
<span data-ttu-id="5ff75-p151">Version 要素も重要です。ルール パッケージを初めてアップロードすると、Microsoft 365 はバージョン番号を記録します。後でルール パッケージを更新して新しいバージョンをアップロードする場合は、バージョン番号を必ず更新してください。そうしないと、Microsoft 365 で新しいルール パッケージは展開されません。</span><span class="sxs-lookup"><span data-stu-id="5ff75-p151">The Version element is also important. When you upload your rule package for the first time, Microsoft 365 notes the version number. Later, if you update the rule package and upload a new version, make sure to update the version number or Microsoft 365 won't deploy the rule package.</span></span>
  
```xml
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="http://schemas.microsoft.com/office/2011/mce">
  <RulePack id=". . .">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id=". . ." /> 
    <Details defaultLangCode=". . .">
      <LocalizedDetails langcode=" . . . ">
         <PublisherName>. . .</PublisherName>
         <Name>. . .</Name>
         <Description>. . .</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>
  
 <Rules>
    . . .
 </Rules>
</RulePackage>

```

<span data-ttu-id="5ff75-283">完了すると、RulePack 要素は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5ff75-283">When complete, your RulePack element should look like this.</span></span>
  
![RulePack 要素を示す XML マークアップ](../media/fd0f31a7-c3ee-43cd-a71b-6a3813b21155.png)
  
## <a name="changes-for-exchange-online"></a><span data-ttu-id="5ff75-285">Exchange Online の変更</span><span class="sxs-lookup"><span data-stu-id="5ff75-285">Changes for Exchange Online</span></span>

<span data-ttu-id="5ff75-286">以前は、DLP 用にカスタムの機密情報の種類をインポートするために Exchange Online PowerShell を使用することがありました。</span><span class="sxs-lookup"><span data-stu-id="5ff75-286">Previously, you might have used Exchange Online PowerShell to import your custom sensitive information types for DLP.</span></span> <span data-ttu-id="5ff75-287">カスタムの機密情報の種類は、Exchange 管理センターとコンプライアンス センターの両方で使用できます。</span><span class="sxs-lookup"><span data-stu-id="5ff75-287">Now your custom sensitive information types can be used in both the Exchange admin center and the Compliance center.</span></span> <span data-ttu-id="5ff75-288">この改善の一環で、カスタムの機密情報の種類をインポートする場合、コンプライアンス センター PowerShell の使用が必須になりました。Exchange PowerShell からはインポートできません。</span><span class="sxs-lookup"><span data-stu-id="5ff75-288">As part of this improvement, you should use Compliance center PowerShell to import your custom sensitive information types — you can't import them from the Exchange PowerShell anymore.</span></span> <span data-ttu-id="5ff75-289">カスタムの機密情報の種類は以前と同様に使用できますが、コンプライアンス センターでカスタムの機密情報の種類を変更した場合、Exchange 管理センターに表示されるまでに最大 1 時間かかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5ff75-289">Your custom sensitive information types will continue to work just like before; however, it may take up to one hour for changes made to custom sensitive information types in the Compliance center to appear in the Exchange admin center.</span></span>
  
<span data-ttu-id="5ff75-290">コンプライアンス センターでは、**[New-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/new-dlpsensitiveinformationtyperulepackage)** コマンドレットを入力して、ルール パッケージをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="5ff75-290">Note that in the Compliance center, you use the **[New-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/new-dlpsensitiveinformationtyperulepackage)** cmdlet to upload a rule package.</span></span> <span data-ttu-id="5ff75-291">(以前は、Exchange 管理センターで **ClassificationRuleCollection** コマンドレットを使用していました。)</span><span class="sxs-lookup"><span data-stu-id="5ff75-291">(Previously, in the Exchange admin center, you used the  **ClassificationRuleCollection**\` cmdlet.)</span></span> 
  
## <a name="upload-your-rule-package"></a><span data-ttu-id="5ff75-292">ルール パッケージをアップロードする</span><span class="sxs-lookup"><span data-stu-id="5ff75-292">Upload your rule package</span></span>



<span data-ttu-id="5ff75-293">ルール パッケージをアップロードするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-293">To upload your rule package, do the following steps:</span></span>
  
1. <span data-ttu-id="5ff75-294">ルールを Unicode エンコードで .xml ファイルとして保存します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-294">Save it as an .xml file with Unicode encoding.</span></span>
    
2. [<span data-ttu-id="5ff75-295">コンプライアンス センター PowerShell に接続する</span><span class="sxs-lookup"><span data-stu-id="5ff75-295">Connect to Compliance center PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=799771)
    
3. <span data-ttu-id="5ff75-296">次の構文を使用してください。</span><span class="sxs-lookup"><span data-stu-id="5ff75-296">Use the following syntax:</span></span>

   ```powershell
   New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "PathToUnicodeXMLFile" -Encoding Byte -ReadCount 0)
   ```

   <span data-ttu-id="5ff75-297">この例では、MyNewRulePack.xml という名前の Unicode XML ファイルを C:\My Documents からアップロードします。</span><span class="sxs-lookup"><span data-stu-id="5ff75-297">This example uploads the Unicode XML file named MyNewRulePack.xml from C:\My Documents.</span></span>

   ```powershell
   New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "C:\My Documents\MyNewRulePack.xml" -Encoding Byte -ReadCount 0)
   ```

   <span data-ttu-id="5ff75-298">構文とパラメーターの詳細情報については、[New-dlpsensitiveinformationtyperulepackage](https://docs.microsoft.com/powershell/module/exchange/new-dlpsensitiveinformationtyperulepackage) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5ff75-298">For detailed syntax and parameter information, see [New-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/new-dlpsensitiveinformationtyperulepackage).</span></span>

   > [!NOTE]
   > <span data-ttu-id="5ff75-299">カスタムの機密情報の種類のコレクションの制限は 10 です。</span><span class="sxs-lookup"><span data-stu-id="5ff75-299">The limit for custom sensitive information type collections is 10.</span></span>

4. <span data-ttu-id="5ff75-300">新しい機密情報の種類が正常に作成されたことを確認するには、次に示す手順のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-300">To verify that you've successfully created a new sensitive information type, do any of the following steps:</span></span>

   - <span data-ttu-id="5ff75-301">[Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) コマンドレットを実行して、新しいルール パッケージが一覧表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-301">Run the [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet to verify the new rule package is listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationTypeRulePackage
     ``` 

   - <span data-ttu-id="5ff75-302">[Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype) コマンドレットを使用して、機密情報の種類が一覧表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-302">Run the [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to verify the sensitive information type is listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType
     ``` 

     <span data-ttu-id="5ff75-303">カスタムの機密情報の種類の場合、Publisher プロパティ値を Microsoft Corporation 以外に設定します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-303">For custom sensitive information types, the Publisher property value will be something other than Microsoft Corporation.</span></span>

   - <span data-ttu-id="5ff75-304">\<Name\>Name を機密情報の種類の名前値 (たとえば、従業員 ID) に置き換えて、[Get-DlpSensitiveInformationType ](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype)コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-304">Replace \<Name\> with the Name value of the sensitive information type (example: Employee ID) and run the [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType -Identity "<Name>"
     ```
    
## <a name="potential-validation-issues-to-be-aware-of"></a><span data-ttu-id="5ff75-305">注意する必要がある潜在的な検証の問題</span><span class="sxs-lookup"><span data-stu-id="5ff75-305">Potential validation issues to be aware of</span></span>

<span data-ttu-id="5ff75-p154">ルール パッケージの XML ファイルをアップロードすると、システムで XML が検証され、既知の不適切なパターンや明らかなパフォーマンスの問題が確認されます。検証で確認される既知の正規表現に関する問題について一部を紹介します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-p154">When you upload your rule package XML file, the system validates the XML and checks for known bad patterns and obvious performance issues. Here are some known issues that the validation checks for — a regular expression:</span></span>
  
- <span data-ttu-id="5ff75-308">先頭または末尾に縦棒 "|" を指定することはできません。これは、空の一致とみなされるため、あらゆるものと一致します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-308">Cannot begin or end with alternator "|", which matches everything because it's considered an empty match.</span></span>
    
  <span data-ttu-id="5ff75-309">たとえば、"|a" や "b|" では検証に合格しません。</span><span class="sxs-lookup"><span data-stu-id="5ff75-309">For example, "|a" or "b|" will not pass validation.</span></span>
    
- <span data-ttu-id="5ff75-310">先頭または末尾に ".{0,m}" パターンを指定することはできません。これは機能的な目的がなく、単にパフォーマンスが低下します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-310">Cannot begin or end with a ".{0,m}" pattern, which has no functional purpose and only impairs performance.</span></span>
    
  <span data-ttu-id="5ff75-311">たとえば、".{0,50}ASDF" や "ASDF.{0,50}" では検証に合格しません。</span><span class="sxs-lookup"><span data-stu-id="5ff75-311">For example, ".{0,50}ASDF" or "ASDF.{0,50}" will not pass validation.</span></span>
    
- <span data-ttu-id="5ff75-312">".{0,m}" や ".{1,m}" をグループに含めることはできません。また、".\*" や ".+" をグループに含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="5ff75-312">Cannot have ".{0,m}" or ".{1,m}" in groups, and cannot have ".\*" or ".+" in groups.</span></span>
    
  <span data-ttu-id="5ff75-313">たとえば、"(.{0,50000})" では検証に合格しません。</span><span class="sxs-lookup"><span data-stu-id="5ff75-313">For example, "(.{0,50000})" will not pass validation.</span></span>
    
- <span data-ttu-id="5ff75-314">"{0,m}" または "{1,m}" リピーターを含む文字はグループ内に含めることができません。</span><span class="sxs-lookup"><span data-stu-id="5ff75-314">Cannot have any character with "{0,m}" or "{1,m}" repeaters in groups.</span></span>
    
  <span data-ttu-id="5ff75-315">たとえば、"(a\*)" では検証に合格しません。</span><span class="sxs-lookup"><span data-stu-id="5ff75-315">For example, "(a\*)" will not pass validation.</span></span>
    
- <span data-ttu-id="5ff75-316">先頭または末尾に ".{1,m}" を指定することはできません。代わりに、"." のみを使用してください。</span><span class="sxs-lookup"><span data-stu-id="5ff75-316">Cannot begin or end with ".{1,m}"; instead, use just "."</span></span>
    
  <span data-ttu-id="5ff75-317">たとえば、".{1,m}asdf" では検証に合格しません。代わりに、".asdf" のみを使用してください。</span><span class="sxs-lookup"><span data-stu-id="5ff75-317">For example, ".{1,m}asdf" will not pass validation; instead, use just ".asdf".</span></span>
    
- <span data-ttu-id="5ff75-318">グループに無制限のリピーター (「\*」や「+」など) を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="5ff75-318">Cannot have an unbounded repeater (such as "\*" or "+") on a group.</span></span>
    
  <span data-ttu-id="5ff75-319">たとえば、"(xx)\*" や "(xx)+" では検証に合格しません。</span><span class="sxs-lookup"><span data-stu-id="5ff75-319">For example, "(xx)\*" and "(xx)+" will not pass validation.</span></span>
  
- <span data-ttu-id="5ff75-320">キーワードの長さは最大 50 文字です。</span><span class="sxs-lookup"><span data-stu-id="5ff75-320">Keywords have a maximum of 50 characters in Length.</span></span>  <span data-ttu-id="5ff75-321">グループ内にこれを超えるキーワードがある場合、推奨される解決策は、用語のグループを[キーワード ディクショナリ](https://docs.microsoft.com/microsoft-365/compliance/create-a-keyword-dictionary)として作成し、ファイル内の Match または idMatch のエンティティの一部として XML 構造内のキーワード ディクショナリの GUID を参照することです。</span><span class="sxs-lookup"><span data-stu-id="5ff75-321">If you have a keyword within a Group exceeding this, a suggested solution is to create the Group of terms as a [Keyword Dictionary](https://docs.microsoft.com/microsoft-365/compliance/create-a-keyword-dictionary) and reference the GUID of the Keyword Dictionary within the XML structure as part of the Entity for Match or idMatch in the file.</span></span>

- <span data-ttu-id="5ff75-322">各カスタム機密情報タイプには、合計で最大 2048 個のキーワードを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="5ff75-322">Each Custom Sensitive Information Type can have a maximum of 2048 keywords total.</span></span>

- <span data-ttu-id="5ff75-323">PowerShell コマンドレットを使用する場合、逆シリアル化されたデータの最大戻りサイズは約 1 メガバイトです。</span><span class="sxs-lookup"><span data-stu-id="5ff75-323">When using the PowerShell Cmdlet there is a maximum return size of the Deserialized Data of approximately 1 megabyte.</span></span>   <span data-ttu-id="5ff75-324">これは、XML ファイルのサイズに影響します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-324">This will affect the size of your XML file.</span></span> <span data-ttu-id="5ff75-325">処理時にエラーが発生しない一貫した結果を得るための推奨制限として、アップロードされたファイルを最大 512 メガバイトに制限してください。</span><span class="sxs-lookup"><span data-stu-id="5ff75-325">Keep the uploaded file limited to a 512 megabyte maximum as a suggested limit for consistent results without error when processing.</span></span>

- <span data-ttu-id="5ff75-326">XML 構造では、スペース、タブ、キャリッジ リターン/ラインフィード エントリなどの書式設定文字は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5ff75-326">The XML structure does not require formatting characters such as Spaces, Tabs or Carriage Return / Linefeed entries.</span></span>  <span data-ttu-id="5ff75-327">アップロードのスペースを最適化するときは、このことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5ff75-327">Take note of this when optimizing for space on uploads.</span></span>
    
<span data-ttu-id="5ff75-328">パフォーマンスに影響する可能性のある問題がカスタムの機密情報の種類に含まれている場合は、アップロードされず、次のいずれかのエラー メッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="5ff75-328">If a custom sensitive information type contains an issue that may affect performance, it won't be uploaded and you may see one of these error messages:</span></span>
  
- <span data-ttu-id="5ff75-329">**予想よりも多くのコンテンツに一致する汎用的な限定詞 (‘+’、‘\*’ など)**</span><span class="sxs-lookup"><span data-stu-id="5ff75-329">**Generic quantifiers which match more content than expected (e.g., '+', '\*')**</span></span>
    
- <span data-ttu-id="5ff75-330">**ルックアラウンド アサーション**</span><span class="sxs-lookup"><span data-stu-id="5ff75-330">**Lookaround assertions**</span></span>
    
- <span data-ttu-id="5ff75-331">**複雑なグループ化と汎用的な限定詞の併用**</span><span class="sxs-lookup"><span data-stu-id="5ff75-331">**Complex grouping in conjunction with general quantifiers**</span></span>
    
## <a name="recrawl-your-content-to-identify-the-sensitive-information"></a><span data-ttu-id="5ff75-332">コンテンツを再クロールして機密情報を特定する</span><span class="sxs-lookup"><span data-stu-id="5ff75-332">Recrawl your content to identify the sensitive information</span></span>

<span data-ttu-id="5ff75-333">Microsoft 365 は、検索クローラーを使用して、サイト コンテンツ内の機密情報を特定し、分類しています。</span><span class="sxs-lookup"><span data-stu-id="5ff75-333">Microsoft 365 uses the search crawler to identify and classify sensitive information in site content.</span></span> <span data-ttu-id="5ff75-334">SharePoint Online サイトと OneDrive for Business サイトのコンテンツが更新されると、自動的に再クロールされます。</span><span class="sxs-lookup"><span data-stu-id="5ff75-334">Content in SharePoint Online and OneDrive for Business sites is recrawled automatically whenever it's updated.</span></span> <span data-ttu-id="5ff75-335">ただし、既存のすべてのコンテンツで新しいカスタムの機密情報の種類を特定するには、そのコンテンツを再クロールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ff75-335">But to identify your new custom type of sensitive information in all existing content, that content must be recrawled.</span></span>
  
<span data-ttu-id="5ff75-336">Microsoft 365 でテナント全体の再クロールを手動で要求することはできませんが、サイト コレクション、リスト、またはライブラリに対して再クロールすることはできます。詳細については、「[サイト、ライブラリ、またはリストのクロールとインデックス再作成を手動で要求する](https://docs.microsoft.com/sharepoint/crawl-site-content)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ff75-336">In Microsoft 365, you can't manually request a recrawl of an entire tenant, but you can do this for a site collection, list, or library — see [Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/sharepoint/crawl-site-content).</span></span>
  
## <a name="remove-a-custom-sensitive-information-type"></a><span data-ttu-id="5ff75-337">カスタムの機密情報の種類を削除する</span><span class="sxs-lookup"><span data-stu-id="5ff75-337">Remove a custom sensitive information type</span></span>

> [!NOTE]
> <span data-ttu-id="5ff75-338">カスタムの機密情報の種類を削除する前に、その機密情報の種類を参照している DLP ポリシーまたは Exchange メール フロー ルール (別名: トランスポート ルール) がないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5ff75-338">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

<span data-ttu-id="5ff75-339">コンプライアンス センターの PowerShell では、カスタムの機密情報の種類を削除する 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="5ff75-339">In Compliance center PowerShell, there are two methods to remove custom sensitive information types:</span></span>

- <span data-ttu-id="5ff75-p159">**個々のカスタムの機密情報の種類を削除する**: 「[カスタムの機密情報の種類を変更する](#modify-a-custom-sensitive-information-type)」に記載されている方法を使用します。カスタムの機密情報の種類を含むカスタム ルール パッケージをエクスポートし、XML ファイルから機密情報の種類を削除して、更新された XML ファイルを既存のカスタム ルール パッケージにインポートします。</span><span class="sxs-lookup"><span data-stu-id="5ff75-p159">**Remove individual custom sensitive information types**: Use the method documented in [Modify a custom sensitive information type](#modify-a-custom-sensitive-information-type). You export the custom rule package that contains the custom sensitive information type, remove the sensitive information type from the XML file, and import the updated XML file back into the existing custom rule package.</span></span>

- <span data-ttu-id="5ff75-342">**カスタム ルール パッケージとそれに含まれるすべてのカスタムの機密情報の種類を削除する**: この方法は、このセクションに記載されています。</span><span class="sxs-lookup"><span data-stu-id="5ff75-342">**Remove a custom rule package and all custom sensitive information types that it contains**: This method is documented in this section.</span></span>

1. [<span data-ttu-id="5ff75-343">コンプライアンス センター PowerShell に接続する</span><span class="sxs-lookup"><span data-stu-id="5ff75-343">Connect to Compliance center PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=799771)

2. <span data-ttu-id="5ff75-344">カスタム ルール パッケージを削除する場合、[Remove-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-344">To remove a custom rule package, use the [Remove-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage) cmdlet:</span></span>

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageIdentity"
   ```

   <span data-ttu-id="5ff75-345">Name 値 (任意の言語) または `RulePack id` (GUID) 値を使用して、ルール パッケージを識別します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-345">You can use the Name value (for any language) or the `RulePack id` (GUID) value to identify the rule package.</span></span>

   <span data-ttu-id="5ff75-346">この例では、"Employee ID Custom Rule Pack" (従業員 ID カスタム ルール パック) という名前のルール パッケージを削除します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-346">This example removes the rule package named "Employee ID Custom Rule Pack".</span></span>

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

   <span data-ttu-id="5ff75-347">構文とパラメーターの詳細情報については、[Remove-dlpsensitiveinformationtyperulepackage](https://docs.microsoft.com/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5ff75-347">For detailed syntax and parameter information, see [Remove-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage).</span></span>

3. <span data-ttu-id="5ff75-348">カスタムの機密情報の種類が正常に削除されたことを確認するには、次に示す手順のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-348">To verify that you've successfully removed a custom sensitive information type, do any of the following steps:</span></span>

   - <span data-ttu-id="5ff75-349">[Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) コマンドレットを実行して、ルール パッケージが一覧表示されないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-349">Run the [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet and verify the rule package is no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationTypeRulePackage
     ```

   - <span data-ttu-id="5ff75-350">[Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype) コマンドレットを実行し、削除されたルール パッケージで機密情報の種類が一覧表示されなくなったことを確認します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-350">Run the [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to verify the sensitive information types in the removed rule package are no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType
     ```

     <span data-ttu-id="5ff75-351">カスタムの機密情報の種類の場合、Publisher プロパティ値を Microsoft Corporation 以外に設定します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-351">For custom sensitive information types, the Publisher property value will be something other than Microsoft Corporation.</span></span>

   - <span data-ttu-id="5ff75-352">\<Name\>Name を機密情報の種類の名前値 (たとえば、従業員 ID) に置き換えて、[Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype)コマンドレットを実行し、機密情報の種類が一覧表示されなくなったことを確認します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-352">Replace \<Name\> with the Name value of the sensitive information type (for example, Employee ID) and run the [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to verify the sensitive information type is no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType -Identity "<Name>"
     ```

## <a name="modify-a-custom-sensitive-information-type"></a><span data-ttu-id="5ff75-353">カスタムの機密情報の種類を変更する</span><span class="sxs-lookup"><span data-stu-id="5ff75-353">Modify a custom sensitive information type</span></span>

<span data-ttu-id="5ff75-354">コンプライアンス センターの PowerShell でカスタムの機密情報の種類を変更するには、次のようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ff75-354">In Compliance center PowerShell, modifying a custom sensitive information type requires you to:</span></span>

1. <span data-ttu-id="5ff75-355">カスタムの機密情報の種類が含まれている既存のルール パッケージを XML ファイル (または、ある場合は既存の XML ファイル) にエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="5ff75-355">Export the existing rule package that contains the custom sensitive information type to an XML file (or use the existing XML file if you have it).</span></span>

2. <span data-ttu-id="5ff75-356">エクスポートした XML ファイルで、カスタムの機密情報の種類を変更します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-356">Modify the custom sensitive information type in the exported XML file.</span></span>

3. <span data-ttu-id="5ff75-357">更新した XML ファイルを既存のルール パッケージにインポートします。</span><span class="sxs-lookup"><span data-stu-id="5ff75-357">Import the updated XML file back into the existing rule package.</span></span>

<span data-ttu-id="5ff75-358">コンプライアンス センターの PowerShell に接続するには、「[コンプライアンス センター PowerShell に接続する](https://go.microsoft.com/fwlink/p/?LinkID=799771)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ff75-358">To connect to Compliance Center PowerShell, see [Connect to Compliance Center PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=799771).</span></span>

### <a name="step-1-export-the-existing-rule-package-to-an-xml-file"></a><span data-ttu-id="5ff75-359">手順 1: 既存のルール パッケージを XML ファイルにエクスポートします</span><span class="sxs-lookup"><span data-stu-id="5ff75-359">Step 1: Export the existing rule package to an XML file</span></span>

> [!NOTE]
> <span data-ttu-id="5ff75-360">XML ファイルのコピーがある場合 (たとえば、先ほど作成してインポートした場合)、次の手順に進んで、XML ファイルを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="5ff75-360">If you have a copy of the XML file (for example, you just created and imported it), you can skip to the next step to modify the XML file.</span></span>

1. <span data-ttu-id="5ff75-361">不明な場合には、[Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype) コマンドレットを実行して、カスタム ルール パッケージの名前を確認します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-361">If you don't already know it, run the [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to find the name of the custom rule package:</span></span>

   ```powershell
   Get-DlpSensitiveInformationTypeRulePackage
   ```

   > [!NOTE]
   > <span data-ttu-id="5ff75-362">組み込みの機密情報の種類を含む組み込みのルール パッケージは、Microsoft Rule Packageという名前になります。</span><span class="sxs-lookup"><span data-stu-id="5ff75-362">The built-in rule package that contains the built-in sensitive information types is named Microsoft Rule Package.</span></span> <span data-ttu-id="5ff75-363">コンプライアンス センターの UI で作成したカスタムの機密情報の種類が含まれるルール パッケージは Microsoft.SCCManaged.CustomRulePack と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="5ff75-363">The rule package that contains the custom sensitive information types that you created in the Compliance center UI is named Microsoft.SCCManaged.CustomRulePack.</span></span>

2. <span data-ttu-id="5ff75-364">[Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) コマンドレットを使用して、カスタム ルール パッケージを変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-364">Use the [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet to store the custom rule package to a variable:</span></span>

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageName"
   ```

   <span data-ttu-id="5ff75-365">たとえば、ルール パッケージの名前が "Employee ID Custom Rule Pack" (従業員 ID カスタム ルール パック) の場合、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-365">For example, if the name of the rule package is "Employee ID Custom Rule Pack", run the following cmdlet:</span></span>

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

3. <span data-ttu-id="5ff75-366">[Set-Content](https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-content?view=powershell-6) コマンドレットを使用して、カスタム ルール パッケージを XML ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="5ff75-366">Use the [Set-Content](https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-content?view=powershell-6) cmdlet to export the custom rule package to an XML file:</span></span>

   ```powershell
   Set-Content -Path "XMLFileAndPath" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

   <span data-ttu-id="5ff75-367">この例では、ルール パッケージを C:\My Documents フォルダーの ExportedRulePackage.xml という名前のファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="5ff75-367">This example export the rule package to the file named ExportedRulePackage.xml in the C:\My Documents folder.</span></span>

   ```powershell
   Set-Content -Path "C:\My Documents\ExportedRulePackage.xml" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

#### <a name="step-2-modify-the-sensitive-information-type-in-the-exported-xml-file"></a><span data-ttu-id="5ff75-368">手順 2: エクスポートした XML ファイルでカスタムの機密情報の種類を変更します</span><span class="sxs-lookup"><span data-stu-id="5ff75-368">Step 2: Modify the sensitive information type in the exported XML file</span></span>

<span data-ttu-id="5ff75-369">XML ファイル内の機密情報の種類、およびファイル内の他の要素については、このトピックで前述されています。</span><span class="sxs-lookup"><span data-stu-id="5ff75-369">Sensitive information types in the XML file and other elements in the file are described earlier in this topic.</span></span>

#### <a name="step-3-import-the-updated-xml-file-back-into-the-existing-rule-package"></a><span data-ttu-id="5ff75-370">手順 3: 更新した XML ファイルを既存のルール パッケージにインポートします</span><span class="sxs-lookup"><span data-stu-id="5ff75-370">Step 3: Import the updated XML file back into the existing rule package</span></span>

<span data-ttu-id="5ff75-371">更新された XML を既存のルール パッケージに再びインポートするには、[Set-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5ff75-371">To import the updated XML back into the existing rule package, use the [Set-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage) cmdlet:</span></span>

```powershell
Set-DlpSensitiveInformationTypeRulePackage -FileData ([Byte[]]$(Get-Content -Path "C:\My Documents\External Sensitive Info Type Rule Collection.xml" -Encoding Byte -ReadCount 0))
```

<span data-ttu-id="5ff75-372">構文とパラメーターの詳細情報については、[Set-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5ff75-372">For detailed syntax and parameter information, see [Set-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage).</span></span>

## <a name="reference-rule-package-xml-schema-definition"></a><span data-ttu-id="5ff75-373">リファレンス: ルール パッケージ XML スキーマの定義</span><span class="sxs-lookup"><span data-stu-id="5ff75-373">Reference: Rule package XML schema definition</span></span>

<span data-ttu-id="5ff75-374">このマークアップをコピーし、XSD ファイルとして保存して、ルール パッケージの XML ファイルの検証に使用できます。</span><span class="sxs-lookup"><span data-stu-id="5ff75-374">You can copy this markup, save it as an XSD file, and use it to validate your rule package XML file.</span></span>
  
```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema xmlns:mce="http://schemas.microsoft.com/office/2011/mce"
           targetNamespace="http://schemas.microsoft.com/office/2011/mce"
           xmlns:xs="https://www.w3.org/2001/XMLSchema"
           elementFormDefault="qualified"
           attributeFormDefault="unqualified"
           id="RulePackageSchema">
  <!-- Use include if this schema has the same target namespace as the schema being referenced, otherwise use import -->
  <xs:element name="RulePackage" type="mce:RulePackageType"/>
  <xs:simpleType name="LangType">
    <xs:union memberTypes="xs:language">
      <xs:simpleType>
        <xs:restriction base="xs:string">
          <xs:enumeration value=""/>
        </xs:restriction>
      </xs:simpleType>
    </xs:union>
  </xs:simpleType>
  <xs:simpleType name="GuidType" final="#all">
    <xs:restriction base="xs:token">
      <xs:pattern value="[0-9a-fA-F]{8}\-([0-9a-fA-F]{4}\-){3}[0-9a-fA-F]{12}"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="RulePackageType">
    <xs:sequence>
      <xs:element name="RulePack" type="mce:RulePackType"/>
      <xs:element name="Rules" type="mce:RulesType">
        <xs:key name="UniqueRuleId">
          <xs:selector xpath="mce:Entity|mce:Affinity|mce:Version/mce:Entity|mce:Version/mce:Affinity"/>
          <xs:field xpath="@id"/>
        </xs:key>
        <xs:key name="UniqueProcessorId">
          <xs:selector xpath="mce:Regex|mce:Keyword|mce:Fingerprint"></xs:selector>
          <xs:field xpath="@id"/>
        </xs:key>
        <xs:key name="UniqueResourceIdRef">
          <xs:selector xpath="mce:LocalizedStrings/mce:Resource"/>
          <xs:field xpath="@idRef"/>
        </xs:key>
        <xs:keyref name="ReferencedRuleMustExist" refer="mce:UniqueRuleId">
          <xs:selector xpath="mce:LocalizedStrings/mce:Resource"/>
          <xs:field xpath="@idRef"/>
        </xs:keyref>
        <xs:keyref name="RuleMustHaveResource" refer="mce:UniqueResourceIdRef">
          <xs:selector xpath="mce:Entity|mce:Affinity|mce:Version/mce:Entity|mce:Version/mce:Affinity"/>
          <xs:field xpath="@id"/>
        </xs:keyref>
      </xs:element>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name="RulePackType">
    <xs:sequence>
      <xs:element name="Version" type="mce:VersionType"/>
      <xs:element name="Publisher" type="mce:PublisherType"/>
      <xs:element name="Details" type="mce:DetailsType">
        <xs:key name="UniqueLangCodeInLocalizedDetails">
          <xs:selector xpath="mce:LocalizedDetails"/>
          <xs:field xpath="@langcode"/>
        </xs:key>
        <xs:keyref name="DefaultLangCodeMustExist" refer="mce:UniqueLangCodeInLocalizedDetails">
          <xs:selector xpath="."/>
          <xs:field xpath="@defaultLangCode"/>
        </xs:keyref>
      </xs:element>
      <xs:element name="Encryption" type="mce:EncryptionType" minOccurs="0" maxOccurs="1"/>
    </xs:sequence>
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
  </xs:complexType>
  <xs:complexType name="VersionType">
    <xs:attribute name="major" type="xs:unsignedShort" use="required"/>
    <xs:attribute name="minor" type="xs:unsignedShort" use="required"/>
    <xs:attribute name="build" type="xs:unsignedShort" use="required"/>
    <xs:attribute name="revision" type="xs:unsignedShort" use="required"/>
  </xs:complexType>
  <xs:complexType name="PublisherType">
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
  </xs:complexType>
  <xs:complexType name="LocalizedDetailsType">
    <xs:sequence>
      <xs:element name="PublisherName" type="mce:NameType"/>
      <xs:element name="Name" type="mce:RulePackNameType"/>
      <xs:element name="Description" type="mce:OptionalNameType"/>
    </xs:sequence>
    <xs:attribute name="langcode" type="mce:LangType" use="required"/>
  </xs:complexType>
  <xs:complexType name="DetailsType">
    <xs:sequence>
      <xs:element name="LocalizedDetails" type="mce:LocalizedDetailsType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="defaultLangCode" type="mce:LangType" use="required"/>
  </xs:complexType>
  <xs:complexType name="EncryptionType">
    <xs:sequence>
      <xs:element name="Key" type="xs:normalizedString"/>
      <xs:element name="IV" type="xs:normalizedString"/>
    </xs:sequence>
  </xs:complexType>
  <xs:simpleType name="RulePackNameType">
    <xs:restriction base="xs:token">
      <xs:minLength value="1"/>
      <xs:maxLength value="64"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="NameType">
    <xs:restriction base="xs:normalizedString">
      <xs:minLength value="1"/>
      <xs:maxLength value="256"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="OptionalNameType">
    <xs:restriction base="xs:normalizedString">
      <xs:minLength value="0"/>
      <xs:maxLength value="256"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="RestrictedTermType">
    <xs:restriction base="xs:string">
      <xs:minLength value="1"/>
      <xs:maxLength value="100"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="RulesType">
    <xs:sequence>
      <xs:choice maxOccurs="unbounded">
        <xs:element name="Entity" type="mce:EntityType"/>
        <xs:element name="Affinity" type="mce:AffinityType"/>
        <xs:element name="Version" type="mce:VersionedRuleType"/>
      </xs:choice>
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element name="Regex" type="mce:RegexType"/>
        <xs:element name="Keyword" type="mce:KeywordType"/>
        <xs:element name="Fingerprint" type="mce:FingerprintType"/>
        <xs:element name="ExtendedKeyword" type="mce:ExtendedKeywordType"/>
      </xs:choice>
      <xs:element name="LocalizedStrings" type="mce:LocalizedStringsType"/>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name="EntityType">
    <xs:sequence>
      <xs:element name="Pattern" type="mce:PatternType" maxOccurs="unbounded"/>
      <xs:element name="Version" type="mce:VersionedPatternType" minOccurs="0" maxOccurs="unbounded" />
    </xs:sequence>
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
    <xs:attribute name="patternsProximity" type="mce:ProximityType" use="required"/>
    <xs:attribute name="recommendedConfidence" type="mce:ProbabilityType"/>
    <xs:attribute name="workload" type="mce:WorkloadType"/>
  </xs:complexType>
  <xs:complexType name="PatternType">
    <xs:sequence>
      <xs:element name="IdMatch" type="mce:IdMatchType"/>
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element name="Match" type="mce:MatchType"/>
        <xs:element name="Any" type="mce:AnyType"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="confidenceLevel" type="mce:ProbabilityType" use="required"/>
  </xs:complexType>
  <xs:complexType name="AffinityType">
    <xs:sequence>
      <xs:element name="Evidence" type="mce:EvidenceType" maxOccurs="unbounded"/>
      <xs:element name="Version" type="mce:VersionedEvidenceType" minOccurs="0" maxOccurs="unbounded" />
    </xs:sequence>
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
    <xs:attribute name="evidencesProximity" type="mce:ProximityType" use="required"/>
    <xs:attribute name="thresholdConfidenceLevel" type="mce:ProbabilityType" use="required"/>
    <xs:attribute name="workload" type="mce:WorkloadType"/>
  </xs:complexType>
  <xs:complexType name="EvidenceType">
    <xs:sequence>
      <xs:choice maxOccurs="unbounded">
        <xs:element name="Match" type="mce:MatchType"/>
        <xs:element name="Any" type="mce:AnyType"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="confidenceLevel" type="mce:ProbabilityType" use="required"/>
  </xs:complexType>
  <xs:complexType name="IdMatchType">
    <xs:attribute name="idRef" type="xs:string" use="required"/>
  </xs:complexType>
  <xs:complexType name="MatchType">
    <xs:attribute name="idRef" type="xs:string" use="required"/>
    <xs:attribute name="minCount" type="xs:positiveInteger" use="optional"/>
    <xs:attribute name="uniqueResults" type="xs:boolean" use="optional"/>
  </xs:complexType>
  <xs:complexType name="AnyType">
    <xs:sequence>
      <xs:choice maxOccurs="unbounded">
        <xs:element name="Match" type="mce:MatchType"/>
        <xs:element name="Any" type="mce:AnyType"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="minMatches" type="xs:nonNegativeInteger" default="1"/>
    <xs:attribute name="maxMatches" type="xs:nonNegativeInteger" use="optional"/>
  </xs:complexType>
  <xs:simpleType name="ProximityType">
    <xs:union>
      <xs:simpleType>
        <xs:restriction base='xs:string'>
          <xs:enumeration value="unlimited"/>
        </xs:restriction>
      </xs:simpleType>
      <xs:simpleType>
        <xs:restriction base="xs:positiveInteger">
          <xs:minInclusive value="1"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:union>
  </xs:simpleType>
  <xs:simpleType name="ProbabilityType">
    <xs:restriction base="xs:integer">
      <xs:minInclusive value="1"/>
      <xs:maxInclusive value="100"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="WorkloadType">
    <xs:restriction base="xs:string">
      <xs:enumeration value="Exchange"/>
      <xs:enumeration value="Outlook"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="EngineVersionType">
    <xs:restriction base="xs:token">
      <xs:pattern value="^\d{2}\.01?\.\d{3,4}\.\d{1,3}$"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="VersionedRuleType">
    <xs:choice maxOccurs="unbounded">
      <xs:element name="Entity" type="mce:EntityType"/>
      <xs:element name="Affinity" type="mce:AffinityType"/>
    </xs:choice>
    <xs:attribute name="minEngineVersion" type="mce:EngineVersionType" use="required" />
  </xs:complexType>
  <xs:complexType name="VersionedPatternType">
    <xs:sequence>
      <xs:element name="Pattern" type="mce:PatternType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="minEngineVersion" type="mce:EngineVersionType" use="required" />
  </xs:complexType>
  <xs:complexType name="VersionedEvidenceType">
    <xs:sequence>
      <xs:element name="Evidence" type="mce:EvidenceType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="minEngineVersion" type="mce:EngineVersionType" use="required" />
  </xs:complexType>
  <xs:simpleType name="FingerprintValueType">
    <xs:restriction base="xs:string">
      <xs:minLength value="2732"/>
      <xs:maxLength value="2732"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="FingerprintType">
    <xs:simpleContent>
      <xs:extension base="mce:FingerprintValueType">
        <xs:attribute name="id" type="xs:token" use="required"/>
        <xs:attribute name="threshold" type="mce:ProbabilityType" use="required"/>
        <xs:attribute name="shingleCount" type="xs:positiveInteger" use="required"/>
        <xs:attribute name="description" type="xs:string" use="optional"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="RegexType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="id" type="xs:token" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="KeywordType">
    <xs:sequence>
      <xs:element name="Group" type="mce:GroupType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="id" type="xs:token" use="required"/>
  </xs:complexType>
  <xs:complexType name="GroupType">
    <xs:sequence>
      <xs:choice>
        <xs:element name="Term" type="mce:TermType" maxOccurs="unbounded"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="matchStyle" default="word">
      <xs:simpleType>
        <xs:restriction base="xs:NMTOKEN">
          <xs:enumeration value="word"/>
          <xs:enumeration value="string"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:attribute>
  </xs:complexType>
  <xs:complexType name="TermType">
    <xs:simpleContent>
      <xs:extension base="mce:RestrictedTermType">
        <xs:attribute name="caseSensitive" type="xs:boolean" default="false"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="ExtendedKeywordType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="id" type="xs:token" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="LocalizedStringsType">
    <xs:sequence>
      <xs:element name="Resource" type="mce:ResourceType" maxOccurs="unbounded">
      <xs:key name="UniqueLangCodeUsedInNamePerResource">
        <xs:selector xpath="mce:Name"/>
        <xs:field xpath="@langcode"/>
      </xs:key>
      <xs:key name="UniqueLangCodeUsedInDescriptionPerResource">
        <xs:selector xpath="mce:Description"/>
        <xs:field xpath="@langcode"/>
      </xs:key>
    </xs:element>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name="ResourceType">
    <xs:sequence>
      <xs:element name="Name" type="mce:ResourceNameType" maxOccurs="unbounded"/>
      <xs:element name="Description" type="mce:DescriptionType" minOccurs="0" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="idRef" type="mce:GuidType" use="required"/>
  </xs:complexType>
  <xs:complexType name="ResourceNameType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="default" type="xs:boolean" default="false"/>
        <xs:attribute name="langcode" type="mce:LangType" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="DescriptionType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="default" type="xs:boolean" default="false"/>
        <xs:attribute name="langcode" type="mce:LangType" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
</xs:schema>
```

## <a name="more-information"></a><span data-ttu-id="5ff75-375">詳細情報</span><span class="sxs-lookup"><span data-stu-id="5ff75-375">More information</span></span>

- [<span data-ttu-id="5ff75-376">データ損失防止ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="5ff75-376">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)

- [<span data-ttu-id="5ff75-377">機密情報の種類のエンティティ定義</span><span class="sxs-lookup"><span data-stu-id="5ff75-377">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

- [<span data-ttu-id="5ff75-378">DLP 関数の検索対象</span><span class="sxs-lookup"><span data-stu-id="5ff75-378">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
