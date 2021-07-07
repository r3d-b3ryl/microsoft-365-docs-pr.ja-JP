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
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: コンプライアンス センターでポリシーのカスタムの機密情報の種類を作成してインポートする方法について説明します。
ms.openlocfilehash: ab89104804fd1af781ca30ed8893bed60cd29e47
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322259"
---
# <a name="create-a-custom-sensitive-information-type-using-powershell"></a><span data-ttu-id="dfece-103">PowerShell を使用してカスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="dfece-103">Create a custom sensitive information type using PowerShell</span></span>

<span data-ttu-id="dfece-104">ここでは、PowerShell を使用して、独自のカスタムの [機密情報の種類](sensitive-information-type-entity-definitions.md)を定義する XML の *ルール パッケージ* ファイルを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dfece-104">This topic shows you how to use PowerShell to create an XML *rule package* file that defines your own custom [sensitive information types](sensitive-information-type-entity-definitions.md).</span></span> <span data-ttu-id="dfece-105">正規表現の作成方法を理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfece-105">You need to know how to create a regular expression.</span></span> <span data-ttu-id="dfece-106">たとえば、ここでは、従業員 ID を特定するカスタムの機密情報の種類を作成します。</span><span class="sxs-lookup"><span data-stu-id="dfece-106">As an example, this topic creates a custom sensitive information type that identifies an employee ID.</span></span> <span data-ttu-id="dfece-107">この XML 例を始点として参照して、カスタムの XML ファイルを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="dfece-107">You can use this example XML as a starting point for your own XML file.</span></span> <span data-ttu-id="dfece-108">機密情報の種類が初めての場合は、「[機密情報の種類の詳細情報](sensitive-information-type-learn-about.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfece-108">If you are new to sensitive information types, see [Learn about sensitive information types](sensitive-information-type-learn-about.md).</span></span>

<span data-ttu-id="dfece-p102">整形式の XML ファイルを作成したら、Microsoft 365 の PowerShell を使用して Microsoft 365 にアップロードできます。これでポリシーでカスタムの機密情報の種類を使用する準備ができたので、意図したとおりに機密情報が検出されることをテストします。</span><span class="sxs-lookup"><span data-stu-id="dfece-p102">After you've created a well-formed XML file, you can upload it to Microsoft 365 by using Microsoft 365 PowerShell. Then you're ready to use your custom sensitive information type in your policies and test that it's detecting the sensitive information as you intended.</span></span>

> [!NOTE]
> <span data-ttu-id="dfece-111">PowerShell が提供する設定された制御が不要な場合は、コンプライアンス センターでカスタムの機密情報の種類を作成できます。</span><span class="sxs-lookup"><span data-stu-id="dfece-111">If you don't need the fine grained control that PowerShell provides, you can create custom sensitive information types in the Compliance center.</span></span> <span data-ttu-id="dfece-112">詳細については、「[カスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dfece-112">For more information, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

## <a name="important-disclaimer"></a><span data-ttu-id="dfece-113">重要な免責事項</span><span class="sxs-lookup"><span data-stu-id="dfece-113">Important disclaimer</span></span>

<span data-ttu-id="dfece-p104">お客様の環境やコンテンツ マッチの要件はさまざまに異なるため、Microsoft サポートは、カスタム分類や正規表現 (別名: RegEx) パターンを定義するなど、カスタムのコンテンツ マッチング定義を提供することの支援は行えません。カスタムのコンテンツ マッチングの開発、テスト、デバッグについては、Microsoft 365 のお客様は、内部の IT リソースを利用するか、Microsoft コンサルティング サービス (MCS) などの外部のコンサルティング リソースを利用する必要があります。サポート エンジニアは、機能の制限付きサポートを提供することはできますが、カスタムのコンテンツ マッチング開発がお客様の要件や義務を満たすことの保証はできません。提供できるサポートの種類の例として、テスト目的の正規表現パターンのサンプルが挙げられます。また、サポートは、特定の単一コンテンツにおいて期待通りに動作していない既存の RegEx パターンのトラブルシューティングを支援できます。</span><span class="sxs-lookup"><span data-stu-id="dfece-p104">Due to the variances in customer environments and content match requirements, Microsoft Support cannot assist in providing custom content-matching definitions; e.g., defining custom classifications or regular expression (also known as RegEx) patterns. For custom content-matching development, testing, and debugging, Microsoft 365 customers will need to rely upon internal IT resources, or use an external consulting resource such as Microsoft Consulting Services (MCS). Support engineers can provide limited support for the feature, but cannot provide assurances that any custom content-matching development will fulfill the customer's requirements or obligations.  As an example of the type of support that can be provided, sample regular expression patterns may be provided for testing purposes. Or, support can assist with troubleshooting an existing RegEx pattern which is not triggering as expected with a single specific content example.</span></span>

<span data-ttu-id="dfece-119">このトピックの[注意する必要がある潜在的な検証の問題](#potential-validation-issues-to-be-aware-of)を参照。</span><span class="sxs-lookup"><span data-stu-id="dfece-119">See [Potential validation issues to be aware of](#potential-validation-issues-to-be-aware-of) in this topic.</span></span>

<span data-ttu-id="dfece-120">テキストを処理するために使用されている Boost.RegEx (以前の RegEx++) エンジンの詳細については、「[Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfece-120">For more information about the Boost.RegEx (formerly known as RegEx++) engine that's used for processing the text, see [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).</span></span>

> [!NOTE]
> <span data-ttu-id="dfece-121">カスタムの機密情報の種類でキーワードの一部としてアンパサンド文字 (&) を使用する場合は、既知の問題に注意してください。</span><span class="sxs-lookup"><span data-stu-id="dfece-121">If you use an ampersand character (&) as part of a keyword in your custom sensitive information type, please note that there is a known issue.</span></span> <span data-ttu-id="dfece-122">文字が適切に識別されていることを確認するには、文字の周囲にスペースを含む用語を追加する必要があります 。たとえば、L & _P_ ではなく L&P。</span><span class="sxs-lookup"><span data-stu-id="dfece-122">You should add an additional term with spaces around the character to make sure that the character is properly identified, for example, L & P _not_ L&P.</span></span>

## <a name="sample-xml-of-a-rule-package"></a><span data-ttu-id="dfece-123">ルール パッケージのサンプル XML</span><span class="sxs-lookup"><span data-stu-id="dfece-123">Sample XML of a rule package</span></span>

<span data-ttu-id="dfece-p106">このトピックで作成するルール パッケージのサンプル XML を示します。要素と属性については、以降のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="dfece-p106">Here's the sample XML of the rule package that we'll create in this topic. Elements and attributes are explained in the sections below.</span></span>
  
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
  <Entity id="E1CC861E-3FE9-4A58-82DF-4BD259EAB378" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="65">
      <IdMatch idRef="Regex_employee_id"/>
    </Pattern>
    <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_employee_id"/>
      <Match idRef="Func_us_date"/>
    </Pattern>
    <Pattern confidenceLevel="85">
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

## <a name="what-are-your-key-requirements-rule-entity-pattern-elements"></a><span data-ttu-id="dfece-p107">主な要件 [Rule、Entity、Pattern 要素]</span><span class="sxs-lookup"><span data-stu-id="dfece-p107">What are your key requirements? [Rule, Entity, Pattern elements]</span></span>

<span data-ttu-id="dfece-128">作業を開始する前に、ルールの XML スキーマの基本構造と、その構造を使用してカスタムの機密情報の種類を定義し、適切なコンテンツを特定できるようにする方法を理解しておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dfece-128">Before you get started, it's helpful to understand the basic structure of the XML schema for a rule, and how you can use this structure to define your custom sensitive information type so that it will identify the right content.</span></span>
  
<span data-ttu-id="dfece-p108">1 つのルールによって 1 つまたは複数のエンティティ (機密情報の種類) が定義され、各エンティティによって 1 つまたは複数のパターンが定義されています。パターンとは、メールやドキュメントなどのコンテンツを評価するときにポリシーが検索する内容です。</span><span class="sxs-lookup"><span data-stu-id="dfece-p108">A rule defines one or more entities (sensitive information types), and each entity defines one or more patterns. A pattern is what a policy looks for when it evaluates content such as email and documents.</span></span>

<span data-ttu-id="dfece-p109">このトピックの XML マークアップでは、エンティティ (機密情報の種類とも呼びます) を定義するパターンとして、ルールを使用しています。そのため、このトピックに出てくるルールは、条件やアクションではなく、エンティティまたは機密情報の種類と考えてください。</span><span class="sxs-lookup"><span data-stu-id="dfece-p109">In this topic, the XML markup uses rule to mean the patterns that define an entity, also known as a sensitive information type. So in this topic, when you see rule, think entity or sensitive information type, not conditions and actions.</span></span>
  
### <a name="simplest-scenario-entity-with-one-pattern"></a><span data-ttu-id="dfece-133">最もシンプルなシナリオ: パターンが 1 つのエンティティ</span><span class="sxs-lookup"><span data-stu-id="dfece-133">Simplest scenario: entity with one pattern</span></span>

<span data-ttu-id="dfece-p110">ここでは、最もシンプルなシナリオについて説明します。この例では、組織の従業員 ID を含むコンテンツを特定するポリシーが必要です。ID の書式は 9 桁の数値です。この場合のパターンは、9 桁の数値を識別するルールに含まれる正規表現を示します。9 桁の数値を含むすべてのコンテンツはこのパターンを満たします。</span><span class="sxs-lookup"><span data-stu-id="dfece-p110">Here's the simplest scenario. You want your policy to identify content that contains your organization's employee ID, which is formatted as a nine-digit number. So the pattern refers to a regular expression contained in the rule that identifies nine-digit numbers. Any content containing a nine-digit number satisfies the pattern.</span></span>
  
![パターンが 1 つのエンティティの図](../media/4cc82dcf-068f-43ff-99b2-bac3892e9819.png)
  
<span data-ttu-id="dfece-139">このパターンはシンプルですが、従業員 ID ではない可能性がある 9 桁の数値を含むコンテンツと一致するため、誤検知が多数特定される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dfece-139">However, while simple, this pattern may identify many false positives by matching content that contains any nine-digit number that is not necessarily an employee ID.</span></span>
  
### <a name="more-common-scenario-entity-with-multiple-patterns"></a><span data-ttu-id="dfece-140">より一般的なシナリオ: パターンが複数あるエンティティ</span><span class="sxs-lookup"><span data-stu-id="dfece-140">More common scenario: entity with multiple patterns</span></span>

<span data-ttu-id="dfece-141">この理由から、複数のパターンを使用してエンティティを定義し、エンティティ (9 桁の数値など) だけでなく、それらのパターンで補強証拠 (キーワードや日付など) を特定する方が一般的です。</span><span class="sxs-lookup"><span data-stu-id="dfece-141">For this reason, it's more common to define an entity by using more than one pattern, where the patterns identify supporting evidence (such as a keyword or date) in addition to the entity (such as a nine-digit number).</span></span>
  
<span data-ttu-id="dfece-142">たとえば、従業員 ID を含むコンテンツを特定する可能性を高めるために、9 桁の数値に加え、雇用日も特定する別のパターンを定義することができます。雇用日とキーワード ("従業員 ID" など) の両方を特定する別のパターンを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="dfece-142">For example, to increase the likelihood of identifying content that contains an employee ID, you can define another pattern that also identifies a hire date, and define yet another pattern that identifies both a hire date and a keyword (such as "employee ID"), in addition to the nine-digit number.</span></span>
  
![パターンが複数あるエンティティの図](../media/c8dc2c9d-00c6-4ebc-889a-53b41a90024a.png)
  
<span data-ttu-id="dfece-144">この構造の重要な側面について一部を説明します。</span><span class="sxs-lookup"><span data-stu-id="dfece-144">Note a couple of important aspects of this structure:</span></span>
  
- <span data-ttu-id="dfece-p111">より多くの証拠が必要なパターンの方が信頼度が高くなります。この機密情報の種類を後でポリシーにおいて使用する場合、より信頼度の高い一致に対してのみ制限の多いアクション (コンテンツのブロックなど) を使用し、信頼度の低い一致には制限の少ないアクション (通知の送信など) を使用できるので便利です。</span><span class="sxs-lookup"><span data-stu-id="dfece-p111">Patterns that require more evidence have a higher confidence level. This is useful because when you later use this sensitive information type in a policy, you can use more restrictive actions (such as block content) with only the higher-confidence matches, and you can use less restrictive actions (such as send notification) with the lower-confidence matches.</span></span>

- <span data-ttu-id="dfece-p112">サポートされる IdMatch 要素と Match 要素は、Pattern ではなく Rule 要素の子である正規表現とキーワードを参照します。これらのサポートされる要素は、Pattern から参照されますが、Rule に含まれています。つまり、サポートされる要素の 1 つの定義 (正規表現やキーワード一覧など) は、複数のエンティティとパターンで参照できます。</span><span class="sxs-lookup"><span data-stu-id="dfece-p112">The supporting IdMatch and Match elements reference regexes and keywords that are actually children of the Rule element, not the Pattern. These supporting elements are referenced by the Pattern but included in the Rule. This means that a single definition of a supporting element, like a regular expression or a keyword list, can be referenced by multiple entities and patterns.</span></span>

## <a name="what-entity-do-you-need-to-identify-entity-element-id-attribute"></a><span data-ttu-id="dfece-p113">特定する必要があるエンティティ [Entity 要素、id 属性]</span><span class="sxs-lookup"><span data-stu-id="dfece-p113">What entity do you need to identify? [Entity element, id attribute]</span></span>

<span data-ttu-id="dfece-p114">エンティティは、明確に定義されたパターンを持つ、クレジットカード番号などの機密情報の種類です。各エンティティは、ID として一意の GUID を持っています。</span><span class="sxs-lookup"><span data-stu-id="dfece-p114">An entity is a sensitive information type, such as a credit card number, that has a well-defined pattern. Each entity has a unique GUID as its ID.</span></span>
  
### <a name="name-the-entity-and-generate-its-guid"></a><span data-ttu-id="dfece-154">エンティティに名前を付けて GUID を生成する</span><span class="sxs-lookup"><span data-stu-id="dfece-154">Name the entity and generate its GUID</span></span>

1. <span data-ttu-id="dfece-155">選択した XML エディターで、[ルール] 要素と [エンティティ] 要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="dfece-155">In your XML editor of choice, add the Rules and Entity elements.</span></span>
2. <span data-ttu-id="dfece-p115">カスタムのエンティティ名 (この例では従業員 ID) を含むコメントを追加します。後で、ローカライズされた文字列セクションにこのエンティティ名を追加します。この名前は、ポリシーを作成するときに UI に表示されます。</span><span class="sxs-lookup"><span data-stu-id="dfece-p115">Add a comment that contains the name of your custom entity — in this example, Employee ID. Later, you'll add the entity name to the localized strings section, and that name is what appears in the UI when you create a policy.</span></span>
3. <span data-ttu-id="dfece-158">エンティティの GUID を生成します。</span><span class="sxs-lookup"><span data-stu-id="dfece-158">Generate a GUID for your entity.</span></span> <span data-ttu-id="dfece-159">GUID を生成する方法は複数ありますが、PowerShell で「**[guid]::NewGuid()**」と入力して簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="dfece-159">There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing **[guid]::NewGuid()**.</span></span> <span data-ttu-id="dfece-160">また、後でローカライズされた文字列セクションにこのエンティティ GUID を追加します。</span><span class="sxs-lookup"><span data-stu-id="dfece-160">Later, you'll also add the entity GUID to the localized strings section.</span></span>
  
![Rules および Entity 要素を示す XML マークアップ](../media/c46c0209-0947-44e0-ac3a-8fd5209a81aa.png)
  
## <a name="what-pattern-do-you-want-to-match-pattern-element-idmatch-element-regex-element"></a><span data-ttu-id="dfece-p117">マッチングするパターン [Pattern 要素、IdMatch 要素、Regex 要素]</span><span class="sxs-lookup"><span data-stu-id="dfece-p117">What pattern do you want to match? [Pattern element, IdMatch element, Regex element]</span></span>

<span data-ttu-id="dfece-p118">パターンには、機密情報の種類が検索している内容の一覧が含まれています。この一覧には、正規表現、キーワード、組み込み関数 (正規表現を実行して日付や住所を検索するなどのタスクを実行する関数) を含めることができます。機密情報の種類には、固有の信頼度を持つ複数のパターンが含まれます。</span><span class="sxs-lookup"><span data-stu-id="dfece-p118">The pattern contains the list of what the sensitive information type is looking for. This can include regexes, keywords, and built-in functions (which perform tasks like running regexes to find dates or addresses). Sensitive information types can have multiple patterns with unique confidences.</span></span>
  
<span data-ttu-id="dfece-p119">以下のすべてのパターンで共通している点は、すべてが同じ正規表現を参照していることです。この正規表現では、空白 (\s) … (\s) で囲まれた 9 桁の数値 (\d{9}) を検索しています。この正規表現は IdMatch 要素から参照されます。また、この正規表現は従業員 ID エンティティを検索するすべてのパターンに共通する要件です。IdMatch は、パターンがマッチングしようとしている識別子 (従業員 ID、クレジット カード番号、社会保障番号など) です。1 つの Pattern 要素には、1 つの IdMatch 要素のみがあります。</span><span class="sxs-lookup"><span data-stu-id="dfece-p119">What all of the below patterns have in common is that they all reference the same regular expression, which looks for a nine-digit number (\d{9}) surrounded by white space (\s) … (\s). This regular expression is referenced by the IdMatch element and is the common requirement for all patterns that look for the Employee ID entity. IdMatch is the identifier that the pattern is to trying to match, such as Employee ID or credit card number or social security number. A Pattern element must have exactly one IdMatch element.</span></span>
  
![単一の Regex 要素を参照する複数の Pattern 要素を示す XML マークアップ](../media/8f3f497b-3b8b-4bad-9c6a-d9abf0520854.png)
  
<span data-ttu-id="dfece-p120">パターンを満たす場合は、数と信頼度が返され、ポリシーの条件に使用できます。機密情報の種類を検出する条件をポリシーに追加する場合、次のように数と信頼度を編集できます。信頼度 (一致精度とも呼ばれます) については、このトピックで後述します。</span><span class="sxs-lookup"><span data-stu-id="dfece-p120">When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your policy. When you add a condition for detecting a sensitive information type to a policy, you can edit the count and confidence level as shown here. Confidence level (also called match accuracy) is explained later in this topic.</span></span>
  
![インスタンス数と一致精度オプション](../media/sit-confidence-level.png)
  
<span data-ttu-id="dfece-p121">正規表現を作成するときは、潜在的な問題があることに注意してください。たとえば、特定されるコンテンツ数が多すぎる正規表現を作成し、アップロードすると、パフォーマンスに影響する可能性があります。このような潜在的な問題の詳細については、後述の「[注意する必要がある潜在的な検証の問題](#potential-validation-issues-to-be-aware-of)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfece-p121">When you create your regular expression, keep in mind that there are potential issues to be aware of. For example, if you write and upload a regex that identifies too much content, this can impact performance. To learn more about these potential issues, see the later section [Potential validation issues to be aware of](#potential-validation-issues-to-be-aware-of).</span></span>
  
## <a name="do-you-want-to-require-additional-evidence-match-element-mincount-attribute"></a><span data-ttu-id="dfece-p122">追加の証拠が必要な場合 [Match 要素、minCount 属性]</span><span class="sxs-lookup"><span data-stu-id="dfece-p122">Do you want to require additional evidence? [Match element, minCount attribute]</span></span>

<span data-ttu-id="dfece-182">パターンでは、IdMatch だけでなく、Match 要素を使用して、キーワード、正規表現、日付、住所など、追加の補強証拠を必須にすることができます。</span><span class="sxs-lookup"><span data-stu-id="dfece-182">In addition to the IdMatch, a pattern can use the Match element to require additional supporting evidence, such as a keyword, regex, date, or address.</span></span>
  
<span data-ttu-id="dfece-p123">1 つのパターンには複数の Match 要素を含めることができます。Pattern 要素に直接含めるか、Any 要素を使用して組み合わせることができます。複数の Match 要素の場合は、暗黙的な AND 演算子で結合されます。パターンが一致するには、すべての Match 要素を満たす必要があります。Any 要素を使用して、AND 演算子または OR 演算子を導入することもできます (詳細については後述します)。</span><span class="sxs-lookup"><span data-stu-id="dfece-p123">A Pattern can include multiple Match elements; they can be included directly in the Pattern element or combined by using the Any element. Match elements are joined by an implicit AND operator; all Match elements must be satisfied for the pattern to be matched. You can use the Any element to introduce AND or OR operators (more on that in a later section).</span></span>
  
<span data-ttu-id="dfece-p124">省略可能な minCount 属性を使用して、各 Match 要素で検出する必要のある一致のインスタンス数を指定できます。たとえば、キーワード一覧の少なくとも 2 つのキーワードが検出された場合にのみ、パターンを満たすものと指定することができます。</span><span class="sxs-lookup"><span data-stu-id="dfece-p124">You can use the optional minCount attribute to specify how many instances of a match need to be found for each of the Match elements. For example, you can specify that a pattern is satisfied only when at least two keywords from a keyword list are found.</span></span>
  
![minOccurs 属性を持つ Match 要素を示す XML マークアップ](../media/607f6b5e-2c7d-43a5-a131-a649f122e15a.png)
  
### <a name="keywords-keyword-group-and-term-elements-matchstyle-and-casesensitive-attributes"></a><span data-ttu-id="dfece-189">キーワード [Keyword 要素、Group 要素、Term 要素、matchStyle 属性、caseSensitive 属性]</span><span class="sxs-lookup"><span data-stu-id="dfece-189">Keywords [Keyword, Group, and Term elements, matchStyle and caseSensitive attributes]</span></span>

<span data-ttu-id="dfece-p125">従業員 ID などの機密情報を特定するときに、多くの場合、補強証拠としてキーワードが必要になります。たとえば、9 桁の数値と一致するだけでなく、"カード"、"バッジ"、"ID" などの単語を検索することがあります。このような場合に Keyword 要素を使用します。Keyword 要素には ID 属性があり、複数のパターンまたはエンティティの複数の Match 要素から参照できます。</span><span class="sxs-lookup"><span data-stu-id="dfece-p125">When you identify sensitive information, like an employee ID, you often want to require keywords as corroborative evidence. For example, in addition to matching a nine-digit number, you may want to look for words like "card", "badge", or "ID". To do this, you use the Keyword element. The Keyword element has an ID attribute that can be referenced by multiple Match elements in multiple patterns or entities.</span></span>
  
<span data-ttu-id="dfece-p126">キーワードは、Group 要素の Term 要素の一覧として含まれます。Group 要素には、2 つの有効値を持つ matchStyle 属性があります。</span><span class="sxs-lookup"><span data-stu-id="dfece-p126">Keywords are included as a list of Term elements in a Group element. The Group element has a matchStyle attribute with two possible values:</span></span>
  
- <span data-ttu-id="dfece-p127">**matchStyle="word"** word の一致は、空白または他の区切り文字で囲まれた複数の単語全体を特定します。複数の単語の一部に一致させる場合、またはアジア言語の単語と一致させる場合を除き、常に word を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dfece-p127">**matchStyle="word"** Word match identifies whole words surrounded by white space or other delimiters. You should always use word unless you need to match parts of words or match words in Asian languages.</span></span> 
    
- <span data-ttu-id="dfece-p128">**matchStyle="string"** string の一致は、囲んでいる文字にかかわらず、文字列を特定します。たとえば、"id" は "bid" と "idea" と一致します。アジア言語と一致させる必要がある場合、またはキーワードが他の文字列の一部に含まれる可能性がある場合にのみ、string を使用してください。</span><span class="sxs-lookup"><span data-stu-id="dfece-p128">**matchStyle="string"** String match identifies strings no matter what they're surrounded by. For example, "id" will match "bid" and "idea". Use string only when you need to match Asian words or if your keyword may be included as part of other strings.</span></span> 
    
<span data-ttu-id="dfece-201">最後に、Term 要素の caseSensitive 属性を使用して、大文字と小文字を含め、コンテンツがキーワードと完全に一致する必要があることを指定できます。</span><span class="sxs-lookup"><span data-stu-id="dfece-201">Finally, you can use the caseSensitive attribute of the Term element to specify that the content must match the keyword exactly, including lower- and upper-case letters.</span></span>
  
![キーワードを参照する Match 要素を示す XML マークアップ](../media/e729ba27-dec6-46f4-9242-584c6c12fd85.png)
  
### <a name="regular-expressions-regex-element"></a><span data-ttu-id="dfece-203">正規表現 [Regex 要素]</span><span class="sxs-lookup"><span data-stu-id="dfece-203">Regular expressions [Regex element]</span></span>

<span data-ttu-id="dfece-p129">この例の従業員 ID エンティティは、既に IdMatch 要素を使用して、空白で囲まれた 9 桁の数値というパターンの正規表現を参照しています。さらに、パターンに Match 要素を使用して追加の Regex 要素を参照し、米国の郵便番号の書式である 5 桁または 9 桁の数値など、補強証拠を特定することができます。</span><span class="sxs-lookup"><span data-stu-id="dfece-p129">In this example, the employee ID entity already uses the IdMatch element to reference a regex for the pattern — a nine-digit number surrounded by whitespace. In addition, a pattern can use a Match element to reference an additional Regex element to identify corroborative evidence, such as a five- or nine-digit number in the format of a US zip code.</span></span>
  
### <a name="additional-patterns-such-as-dates-or-addresses-built-in-functions"></a><span data-ttu-id="dfece-206">日付や住所などのその他のパターン [組み込み関数]</span><span class="sxs-lookup"><span data-stu-id="dfece-206">Additional patterns such as dates or addresses [built-in functions]</span></span>

<span data-ttu-id="dfece-p130">機密情報の種類には、組み込みの機密情報の種類だけでなく、米国の日付、EU の日付、有効期限の日付、または米国の住所など、補強証拠を特定できる組み込み関数も使用できます。Microsoft 365 は独自のカスタム関数のアップロードをサポートしていませんが、カスタムの機密情報の種類を作成した場合は、エンティティから組み込み関数を参照できます。</span><span class="sxs-lookup"><span data-stu-id="dfece-p130">In addition to the built-in sensitive information types, sensitive information types can also use built-in functions that can identify corroborative evidence such as a US date, EU date, expiration date, or US address. Microsoft 365 does not support uploading your own custom functions, but when you create a custom sensitive information type, your entity can reference the built-in functions.</span></span>
  
<span data-ttu-id="dfece-209">たとえば、従業員 ID バッジには雇用日が記載されているので、このカスタム エンティティで組み込み関数 `Func_us_date` を使用して、米国で一般的に使用されている形式の日付を特定できます。</span><span class="sxs-lookup"><span data-stu-id="dfece-209">For example, an employee ID badge has a hire date on it, so this custom entity can use the built-in function  `Func_us_date` to identify a date in the format commonly used in the US.</span></span> 
  
<span data-ttu-id="dfece-210">詳細は、「[DLP 関数で探索する内容](what-the-dlp-functions-look-for.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfece-210">For more information, see [What the DLP functions look for](what-the-dlp-functions-look-for.md).</span></span>
  
![組み込み関数を参照する Match 要素を示す XML マークアップ](../media/dac6eae3-9c52-4537-b984-f9f127cc9c33.png)
  
## <a name="different-combinations-of-evidence-any-element-minmatches-and-maxmatches-attributes"></a><span data-ttu-id="dfece-212">証拠のさまざまな組み合わせ [Any 要素、minMatches 属性、maxMatches 属性]</span><span class="sxs-lookup"><span data-stu-id="dfece-212">Different combinations of evidence [Any element, minMatches and maxMatches attributes]</span></span>

<span data-ttu-id="dfece-p131">Pattern 要素内のすべての IdMatch 要素と Match 要素は暗黙的な AND 演算子で結合されます。パターンを満たすには、すべての一致を満たしている必要があります。ただし、Any 要素を使用して複数の Match 要素をグループ化することで、より柔軟なマッチング ロジックを作成できます。たとえば、Any 要素を使用して、子 Match 要素のすべて一致、一致なし、完全サブセットの一致を表すことができます。</span><span class="sxs-lookup"><span data-stu-id="dfece-p131">In a Pattern element, all IdMatch and Match elements are joined by an implicit AND operator — all of the matches must be satisfied before the pattern can be satisfied. However, you can create more flexible matching logic by using the Any element to group Match elements. For example, you can use the Any element to match all, none, or an exact subset of its children Match elements.</span></span>
  
<span data-ttu-id="dfece-p132">Any 要素には省略可能な minMatches 属性と maxMatches 属性があります。これらの属性を使用して、パターンが一致する前に満たす必要がある子 Match 要素数を定義できます。これらの属性では、一致が検出された証拠のインスタンス数ではなく、満たす必要がある Match 要素数を定義する点に注意してください。特定の一致について最小のインスタンス数を定義するには (たとえば、一覧の 2 つのキーワードなど)、Match 要素に minCount 属性を使用します (上記を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="dfece-p132">The Any element has optional minMatches and maxMatches attributes that you can use to define how many of the children Match elements must be satisfied before the pattern is matched. Note that these attributes define the number of Match elements that must be satisfied, not the number of instances of evidence found for the matches. To define a minimum number of instances for a specific match, such as two keywords from a list, use the minCount attribute for a Match element (see above).</span></span>
  
### <a name="match-at-least-one-child-match-element"></a><span data-ttu-id="dfece-219">少なくとも 1 つの子 Match 要素に一致する</span><span class="sxs-lookup"><span data-stu-id="dfece-219">Match at least one child Match element</span></span>

<span data-ttu-id="dfece-p133">最小数の Match 要素のみを満たすことを必須にするには、minMatches 属性を使用できます。実質的に、これらの Match 要素は暗黙的な OR 演算子で結合されています。この Any 要素は、米国形式の日付またはいずれかのリストのキーワードが見つかった場合に満たされます。</span><span class="sxs-lookup"><span data-stu-id="dfece-p133">If you want to require that only a minimum number of Match elements must be met, you can use the minMatches attribute. In effect, these Match elements are joined by an implicit OR operator. This Any element is satisfied if a US-formatted date or a keyword from either list is found.</span></span>

```xml
<Any minMatches="1" >
     <Match idRef="Func_us_date" />
     <Match idRef="Keyword_employee" />
     <Match idRef="Keyword_badge" />
</Any>
```
    
### <a name="match-an-exact-subset-of-any-children-match-elements"></a><span data-ttu-id="dfece-223">任意の子 Match 要素の完全サブセットと一致する</span><span class="sxs-lookup"><span data-stu-id="dfece-223">Match an exact subset of any children Match elements</span></span>

<span data-ttu-id="dfece-p134">特定の数の Match 要素を満たすことを必須にするには、minMatches と maxMatches を同じ値に設定できます。この Any 要素は、完全に一致する日付またはキーワードが見つかった場合にのみ満たされます。また、パターンはマッチングされません。</span><span class="sxs-lookup"><span data-stu-id="dfece-p134">If you want to require that an exact number of Match elements must be met, you can set minMatches and maxMatches to the same value. This Any element is satisfied only if exactly one date or keyword is found — any more than that, and the pattern won't be matched.</span></span>

```xml
<Any minMatches="1" maxMatches="1" >
     <Match idRef="Func_us_date" />
     <Match idRef="Keyword_employee" />
     <Match idRef="Keyword_badge" />
</Any>
```
  
### <a name="match-none-of-children-match-elements"></a><span data-ttu-id="dfece-226">子 Match 要素のいずれとも一致しない</span><span class="sxs-lookup"><span data-stu-id="dfece-226">Match none of children Match elements</span></span>

<span data-ttu-id="dfece-p135">パターンを満たすための特定の証拠がないことを必須にするには、minMatches と maxMatches の両方を 0 に設定できます。この方法は、誤検知を示す可能性が高いキーワード一覧やその他の証拠がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="dfece-p135">If you want to require the absence of specific evidence for a pattern to be satisfied, you can set both minMatches and maxMatches to 0. This can be useful if you have a keyword list or other evidence that are likely to indicate a false positive.</span></span>
  
<span data-ttu-id="dfece-p136">たとえば、従業員 ID エンティティは "ID カード" を指している可能性があるため、キーワード "カード" を探しているとします。ただし、カードという単語が "クレジット カード" という語句内にのみ出現する場合、このコンテンツの "カード" が "ID カード" を示す可能性はあまりありません。そのため、パターンを満たす単語から除外する単語の一覧にキーワードとして "クレジット カード" を追加できます。</span><span class="sxs-lookup"><span data-stu-id="dfece-p136">For example, the employee ID entity looks for the keyword "card" because it might refer to an "ID card". However, if card appears only in the phrase "credit card", "card" in this content is unlikely to mean "ID card". So you can add "credit card" as a keyword to a list of terms that you want to exclude from satisfying the pattern.</span></span>
  
```xml
<Any minMatches="0" maxMatches="0" >
    <Match idRef="Keyword_false_positives_local" />
    <Match idRef="Keyword_false_positives_intl" />
</Any>
```

### <a name="match-a-number-of-unique-terms"></a><span data-ttu-id="dfece-232">一意の条件の数を照合する</span><span class="sxs-lookup"><span data-stu-id="dfece-232">Match a number of unique terms</span></span>

<span data-ttu-id="dfece-233">一意の条件の数を照合する場合、以下の例に示されているように、*uniqueResults* パラメーターを *true* に設定して使用します。</span><span class="sxs-lookup"><span data-stu-id="dfece-233">If you want to match a number of unique terms, use the *uniqueResults* parameter, set to *true*, as shown in the following example:</span></span>

```xml
<Pattern confidenceLevel="75">
    <IdMatch idRef="Salary_Revision_terms" />
    <Match idRef=" Salary_Revision_ID " minCount="3" uniqueResults="true" />
</Pattern>
```

<span data-ttu-id="dfece-234">この例では、3 つ以上の一意の一致を使用して、給与改定パターンを定義しています。</span><span class="sxs-lookup"><span data-stu-id="dfece-234">In this example, a pattern is defined for salary revision using at least three unique matches.</span></span> 
  
## <a name="how-close-to-the-entity-must-the-other-evidence-be-patternsproximity-attribute"></a><span data-ttu-id="dfece-p137">エンティティと他の証拠との近接度 [patternsProximity 属性]</span><span class="sxs-lookup"><span data-stu-id="dfece-p137">How close to the entity must the other evidence be? [patternsProximity attribute]</span></span>

<span data-ttu-id="dfece-p138">機密情報の種類で従業員 ID を表すパターンを検索していて、そのパターンの一部として、"ID" などのキーワードのような補強証拠も検索する場合があります。この証拠が互いに近くにあるほど、パターンが実際の従業員 ID になる可能性が高くなります。パターン内の他の証拠とエンティティの近接度を判断するには、Entity 要素の必須の patternsProximity 属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="dfece-p138">Your sensitive information type is looking for a pattern that represents an employee ID, and as part of that pattern it's also looking for corroborative evidence like a keyword such as "ID". It makes sense that the closer together this evidence is, the more likely the pattern is to be an actual employee ID. You can determine how close other evidence in the pattern must be to the entity by using the required patternsProximity attribute of the Entity element.</span></span>
  
![patternsProximity 属性を示す XML マークアップ](../media/e97eb7dc-b897-4e11-9325-91c742d9839b.png)
  
<span data-ttu-id="dfece-p139">エンティティ内の各パターンに対し、そのパターンに対して指定されたすべての他の一致について、patternsProximity 属性値で IdMatch の場所からの距離 (Unicode 文字) を定義します。近接ウィンドウは、IdMatch の場所によってアンカーされ、IdMatch の左側と右側にウィンドウが展開されます。</span><span class="sxs-lookup"><span data-stu-id="dfece-p139">For each pattern in the entity, the patternsProximity attribute value defines the distance (in Unicode characters) from the IdMatch location for all other Matches specified for that Pattern. The proximity window is anchored by the IdMatch location, with the window extending to the left and right of the IdMatch.</span></span>
  
![近接ウィンドウの図](../media/b593dfd1-5eef-4d79-8726-a28923f7c31e.png)
  
<span data-ttu-id="dfece-p140">以下の例は、従業員 ID のカスタム エンティティの IdMatch 要素で、キーワードまたは日付の少なくとも 1 つの補完的な一致を必要とするパターン マッチングに対して、近接ウィンドウがどのように影響するかを示しています。ID2 と ID3 の場合、近接ウィンドウ内に補強証拠がまったくないか、部分的にしかないため、ID1 のみが一致します。</span><span class="sxs-lookup"><span data-stu-id="dfece-p140">The example below illustrates how the proximity window affects the pattern matching where IdMatch element for the employee ID custom entity requires at least one corroborating match of keyword or date. Only ID1 matches because for ID2 and ID3, either no or only partial corroborating evidence is found within the proximity window.</span></span>
  
![補強証拠と近接ウィンドウの図](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)
  
<span data-ttu-id="dfece-p141">メールの場合、メッセージ本文と各添付ファイルは、別のアイテムとして扱われる点に注意してください。つまり、近接ウィンドウは、これらの各アイテムの終端を超えて延長されないということです。各アイテム (添付ファイルまたは本文) に、idMatch と補強証拠の両方が存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfece-p141">Note that for email, the message body and each attachment are treated as separate items. This means that the proximity window does not extend beyond the end of each of these items. For each item (attachment or body), both the idMatch and corroborative evidence needs to reside in that item.</span></span>
  
## <a name="what-are-the-right-confidence-levels-for-different-patterns-confidencelevel-attribute-recommendedconfidence-attribute"></a><span data-ttu-id="dfece-p142">パターンごとの適切な信頼度 [confidenceLevel 属性、recommendedConfidence 属性]</span><span class="sxs-lookup"><span data-stu-id="dfece-p142">What are the right confidence levels for different patterns? [confidenceLevel attribute, recommendedConfidence attribute]</span></span>

<span data-ttu-id="dfece-p143">パターンに必要な証拠が多くなるほど、パターンが一致したときに実際のエンティティ (従業員 ID など) が特定される信頼度が高くなります。たとえば、9 桁の ID 番号、雇用日、近接度の高いキーワードが必要なパターンの場合、9 桁の ID 番号のみが必要なパターンよりも信頼度が高くなります。</span><span class="sxs-lookup"><span data-stu-id="dfece-p143">The more evidence that a pattern requires, the more confidence you have that an actual entity (such as employee ID) has been identified when the pattern is matched. For example, you have more confidence in a pattern that requires a nine-digit ID number, hire date, and keyword in close proximity, than you do in a pattern that requires only a nine-digit ID number.</span></span>
  
<span data-ttu-id="dfece-p144">Pattern 要素には必須の confidenceLevel 属性があります。confidenceLevel の値 (1 から 100 の整数) は、エンティティに含まれる各パターンの一意の ID と考えることができます。エンティティのパターンには、異なる信頼度を割り当てる必要があります。この整数を細かく指定することにあまり大きな意味はありません。社内のコンプライアンス チームにとって意味のある数値を選択してください。カスタムの機密情報の種類をアップロードし、ポリシーを作成したら、作成するルールの条件でその信頼度を参照できます。</span><span class="sxs-lookup"><span data-stu-id="dfece-p144">The Pattern element has a required confidenceLevel attribute. You can think of the value of confidenceLevel (an integer between 1 and 100) as a unique ID for each pattern in an entity — the patterns in an entity must have different confidence levels that you assign. The precise value of the integer doesn't matter — simply pick numbers that make sense to your compliance team. After you upload your custom sensitive information type and then create a policy, you can reference these confidence levels in the conditions of the rules that you create.</span></span>
  
![confidenceLevel 属性にさまざまな値を持つ Pattern 要素を示す XML マークアップ](../media/sit-xml-markedup-2.png)
  
<span data-ttu-id="dfece-259">Entity には各パターン の confidenceLevel に加え、 recommendedConfidence 属性があります。</span><span class="sxs-lookup"><span data-stu-id="dfece-259">In addition to confidenceLevel for each Pattern, the Entity has a recommendedConfidence attribute.</span></span> <span data-ttu-id="dfece-260">recommendedConfidence 属性は、ルールの既定の信頼度と考えることができます。</span><span class="sxs-lookup"><span data-stu-id="dfece-260">The recommended confidence attribute can be thought of as the default confidence level for the rule.</span></span> <span data-ttu-id="dfece-261">ポリシーでルールを作成するときに、使用するルールの信頼度を指定しない場合、そのエンティティの推奨される信頼度に基づいてルールのマッチングが行われます。</span><span class="sxs-lookup"><span data-stu-id="dfece-261">When you create a rule in a policy, if you don't specify a confidence level for the rule to use, that rule will match based on the recommended confidence level for the entity.</span></span> <span data-ttu-id="dfece-262">ルールパッケージ内で各エンティティ ID に recommendedConfidence 属性が必須であることに注意してください。存在しない場合、機密情報の種類を使用するポリシーを保存できません。</span><span class="sxs-lookup"><span data-stu-id="dfece-262">Please note that the recommendedConfidence attribute is mandatory for each Entity ID in the Rule Package, if missing you won't be able to save policies that use the Sensitive Information Type.</span></span> 
  
## <a name="do-you-want-to-support-other-languages-in-the-ui-of-the-compliance-center-localizedstrings-element"></a><span data-ttu-id="dfece-p146">コンプライアンス センターの UI で他の言語をサポートする場合 [LocalizedStrings 要素]</span><span class="sxs-lookup"><span data-stu-id="dfece-p146">Do you want to support other languages in the UI of the Compliance center? [LocalizedStrings element]</span></span>

<span data-ttu-id="dfece-p147">コンプライアンス チームが Microsoft 365 コンプライアンス センターを使用して異なるロケールと異なる言語でポリシーを作成する場合、カスタムの機密情報の種類の名前と説明について、ローカライズされたバージョンを提供することができます。コンプライアンス チームがサポートしている言語で Microsoft 365 を使用すると、ローカライズされた名前が UI に表示されます。</span><span class="sxs-lookup"><span data-stu-id="dfece-p147">If your compliance team uses the Microsoft 365 Compliance center to create polices policies in different locales and in different languages, you can provide localized versions of the name and description of your custom sensitive information type. When your compliance team uses Microsoft 365 in a language that you support, they'll see the localized name in the UI.</span></span>
  
![インスタンス数と一致精度オプション](../media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)
  
<span data-ttu-id="dfece-p148">Rules 要素には、LocalizedStrings 要素を含める必要があります。LocalizedStrings 要素には、カスタム エンティティの GUID を参照する Resource 要素が含まれています。また、各 Resource 要素には、1 つまたは複数の Name 要素と Description 要素が含まれており、それぞれが langcode 属性を使用して特定の言語のローカライズされた文字列を提供します。</span><span class="sxs-lookup"><span data-stu-id="dfece-p148">The Rules element must contain a LocalizedStrings element, which contains a Resource element that references the GUID of your custom entity. In turn, each Resource element contains one or more Name and Description elements that each use the langcode attribute to provide a localized string for a specific language.</span></span>
  
![LocalizedStrings 要素の内容を示す XML マークアップ](../media/a96fc34a-b93d-498f-8b92-285b16a7bbe6.png)
  
<span data-ttu-id="dfece-p149">ローカライズされた文字列は、カスタムの機密情報の種類がコンプライアンス センターの UI でどのように表示されるかを指定するためにのみ使用できることに注意してください。ローカライズされた文字列を使用して、キーワード リストまたは正規表現の異なるローカライズ バージョンを提供することはできません。</span><span class="sxs-lookup"><span data-stu-id="dfece-p149">Note that you use localized strings only for how your custom sensitive information type appears in the UI of the Compliance center. You can't use localized strings to provide different localized versions of a keyword list or regular expression.</span></span>
  
## <a name="other-rule-package-markup-rulepack-guid"></a><span data-ttu-id="dfece-273">その他のルール パッケージ マークアップ [RulePack GUID]</span><span class="sxs-lookup"><span data-stu-id="dfece-273">Other rule package markup [RulePack GUID]</span></span>

<span data-ttu-id="dfece-p150">最後に、各 RulePackage の先頭には、入力する必要のある一般的な情報が含まれています。次のマークアップをテンプレートとして使用し、「. . .」プレースホルダーを自分の情報に置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="dfece-p150">Finally, the beginning of each RulePackage contains some general information that you need to fill in. You can use the following markup as a template and replace the ". . ." placeholders with your own info.</span></span>
  
<span data-ttu-id="dfece-p151">最も重要な点は、RulePack の GUID を生成する必要があることです。これまでにエンティティの GUID を生成しましたが、これは RulePack の 2 つ目の GUID です。GUID を生成するにはいくつかの方法がありますが、PowerShell では [guid]::NewGuid() と入力することで簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="dfece-p151">Most importantly, you'll need to generate a GUID for the RulePack. Above, you generated a GUID for the entity; this is a second GUID for the RulePack. There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing [guid]::NewGuid().</span></span>
  
<span data-ttu-id="dfece-p152">Version 要素も重要です。ルール パッケージを初めてアップロードすると、Microsoft 365 はバージョン番号を記録します。後でルール パッケージを更新して新しいバージョンをアップロードする場合は、バージョン番号を必ず更新してください。そうしないと、Microsoft 365 で新しいルール パッケージは展開されません。</span><span class="sxs-lookup"><span data-stu-id="dfece-p152">The Version element is also important. When you upload your rule package for the first time, Microsoft 365 notes the version number. Later, if you update the rule package and upload a new version, make sure to update the version number or Microsoft 365 won't deploy the rule package.</span></span>
  
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

<span data-ttu-id="dfece-285">完了すると、RulePack 要素は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="dfece-285">When complete, your RulePack element should look like this.</span></span>
  
![RulePack 要素を示す XML マークアップ](../media/fd0f31a7-c3ee-43cd-a71b-6a3813b21155.png)

## <a name="validators"></a><span data-ttu-id="dfece-287">検証ツール</span><span class="sxs-lookup"><span data-stu-id="dfece-287">Validators</span></span>

<span data-ttu-id="dfece-288">Microsoft 365一般的に使用される SIT の関数プロセッサを検証ツールとして公開します。</span><span class="sxs-lookup"><span data-stu-id="dfece-288">Microsoft 365 exposes function processors for commonly used SITs as validators.</span></span> <span data-ttu-id="dfece-289">その一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="dfece-289">Here's a list of them.</span></span> 

### <a name="list-of-validators-currently-available"></a><span data-ttu-id="dfece-290">現在利用可能な検証ツールの一覧</span><span class="sxs-lookup"><span data-stu-id="dfece-290">List of validators currently available</span></span>

- <span data-ttu-id="dfece-291">Func_credit_card</span><span class="sxs-lookup"><span data-stu-id="dfece-291">Func_credit_card</span></span>
- <span data-ttu-id="dfece-292">Func_ssn</span><span class="sxs-lookup"><span data-stu-id="dfece-292">Func_ssn</span></span>
- <span data-ttu-id="dfece-293">Func_unformatted_ssn</span><span class="sxs-lookup"><span data-stu-id="dfece-293">Func_unformatted_ssn</span></span>
- <span data-ttu-id="dfece-294">Func_randomized_formatted_ssn</span><span class="sxs-lookup"><span data-stu-id="dfece-294">Func_randomized_formatted_ssn</span></span>
- <span data-ttu-id="dfece-295">Func_randomized_unformatted_ssn</span><span class="sxs-lookup"><span data-stu-id="dfece-295">Func_randomized_unformatted_ssn</span></span>
- <span data-ttu-id="dfece-296">Func_aba_routing</span><span class="sxs-lookup"><span data-stu-id="dfece-296">Func_aba_routing</span></span>
- <span data-ttu-id="dfece-297">Func_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="dfece-297">Func_south_africa_identification_number</span></span>
- <span data-ttu-id="dfece-298">Func_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="dfece-298">Func_brazil_cpf</span></span>
- <span data-ttu-id="dfece-299">Func_iban</span><span class="sxs-lookup"><span data-stu-id="dfece-299">Func_iban</span></span>
- <span data-ttu-id="dfece-300">Func_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="dfece-300">Func_brazil_cnpj</span></span>
- <span data-ttu-id="dfece-301">Func_swedish_national_identifier</span><span class="sxs-lookup"><span data-stu-id="dfece-301">Func_swedish_national_identifier</span></span>
- <span data-ttu-id="dfece-302">Func_india_aadhaar</span><span class="sxs-lookup"><span data-stu-id="dfece-302">Func_india_aadhaar</span></span>
- <span data-ttu-id="dfece-303">Func_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="dfece-303">Func_uk_nhs_number</span></span>
- <span data-ttu-id="dfece-304">Func_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="dfece-304">Func_Turkish_National_Id</span></span>
- <span data-ttu-id="dfece-305">Func_australian_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="dfece-305">Func_australian_tax_file_number</span></span>
- <span data-ttu-id="dfece-306">Func_usa_uk_passport</span><span class="sxs-lookup"><span data-stu-id="dfece-306">Func_usa_uk_passport</span></span>
- <span data-ttu-id="dfece-307">Func_canadian_sin</span><span class="sxs-lookup"><span data-stu-id="dfece-307">Func_canadian_sin</span></span>
- <span data-ttu-id="dfece-308">Func_formatted_itin</span><span class="sxs-lookup"><span data-stu-id="dfece-308">Func_formatted_itin</span></span>
- <span data-ttu-id="dfece-309">Func_unformatted_itin</span><span class="sxs-lookup"><span data-stu-id="dfece-309">Func_unformatted_itin</span></span>
- <span data-ttu-id="dfece-310">Func_dea_number_v2</span><span class="sxs-lookup"><span data-stu-id="dfece-310">Func_dea_number_v2</span></span>
- <span data-ttu-id="dfece-311">Func_dea_number</span><span class="sxs-lookup"><span data-stu-id="dfece-311">Func_dea_number</span></span>
- <span data-ttu-id="dfece-312">Func_japanese_my_number_personal</span><span class="sxs-lookup"><span data-stu-id="dfece-312">Func_japanese_my_number_personal</span></span>
- <span data-ttu-id="dfece-313">Func_japanese_my_number_corporate</span><span class="sxs-lookup"><span data-stu-id="dfece-313">Func_japanese_my_number_corporate</span></span>

<span data-ttu-id="dfece-314">これにより、独自の正規表現を定義して検証できます。</span><span class="sxs-lookup"><span data-stu-id="dfece-314">This gives you the ability to define your own regex and validate them.</span></span> <span data-ttu-id="dfece-315">バリデーターを使用するには、独自の正規表現を定義し、正規表現を定義するときに、validator プロパティを使用して、選択した関数プロセッサを追加します。</span><span class="sxs-lookup"><span data-stu-id="dfece-315">To use validators, define your own regex and while defining the regex use the validator property to add the function processor of your choice.</span></span> <span data-ttu-id="dfece-316">定義が完了したら、SIT でこの正規表現を使用できます。</span><span class="sxs-lookup"><span data-stu-id="dfece-316">Once defined, you can use this regex in an SIT.</span></span> 

<span data-ttu-id="dfece-317">次の例では、正規表現 - Regex_credit_card_AdditionalDelimiters がクレジット カードに対して定義され、その後、Func_credit_card を検証ツールとして使用してクレジット カードのチェックサム関数を使用して検証されます。</span><span class="sxs-lookup"><span data-stu-id="dfece-317">In the example below, a regular expression - Regex_credit_card_AdditionalDelimiters is defined for Credit card which is then validated using the checksum function for credit card by using Func_credit_card as a validator.</span></span>

```xml
<Regex id="Regex_credit_card_AdditionalDelimiters" validators="Func_credit_card"> (?:^|[\s,;\:\(\)\[\]"'])([0-9]{4}[ -_][0-9]{4}[ -_][0-9]{4}[ -_][0-9]{4})(?:$|[\s,;\:\(\)\[\]"'])</Regex>
<Entity id="675634eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
<Pattern confidenceLevel="85">
<IdMatch idRef="Regex_credit_card_AdditionalDelimiters" />
<Any minMatches="1">
<Match idRef="Keyword_cc_verification" />
<Match idRef="Keyword_cc_name" />
<Match idRef="Func_expiration_date" />
</Any>
</Pattern>
</Entity>
```

<span data-ttu-id="dfece-318">Microsoft 365 2 つの汎用バリデーターを提供する</span><span class="sxs-lookup"><span data-stu-id="dfece-318">Microsoft 365 provides two generic validators</span></span>

### <a name="checksum-validator"></a><span data-ttu-id="dfece-319">チェックサム検証ツール</span><span class="sxs-lookup"><span data-stu-id="dfece-319">Checksum validator</span></span>

<span data-ttu-id="dfece-320">この例では、EmployeeID の正規表現を検証するために、従業員 ID のチェックサム検証ツールが定義されています。</span><span class="sxs-lookup"><span data-stu-id="dfece-320">In this example, a checksum validator for employee ID is defined to validate the regex for EmployeeID.</span></span>

```xml
<Validators id="EmployeeIDChecksumValidator">
<Validator type="Checksum">
<Param name="Weights">2, 2, 2, 2, 2, 1</Param>
<Param name="Mod">28</Param>
<Param name="CheckDigit">2</Param> <!-- Check 2nd digit -->
<Param name="AllowAlphabets">1</Param> <!— 0 if no Alphabets -->
</Validator>
</Validators>
<Regex id="Regex_EmployeeID" validators="ChecksumValidator">(\d{5}[A-Z])</Regex>
<Entity id="675634eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
<Pattern confidenceLevel="85">
<IdMatch idRef="Regex_EmployeeID"/>
</Pattern>
</Entity>
```

### <a name="date-validator"></a><span data-ttu-id="dfece-321">Date Validator</span><span class="sxs-lookup"><span data-stu-id="dfece-321">Date Validator</span></span>

<span data-ttu-id="dfece-322">この例では、日付バリデーターは、日付である正規表現部分に対して定義されます。</span><span class="sxs-lookup"><span data-stu-id="dfece-322">In this example, a date validator is defined for a regex part of which is date.</span></span>

```xml
<Validators id="date_validator_1"> <Validator type="DateSimple"> <Param name="Pattern">DDMMYYYY</Param> <!—supported patterns DDMMYYYY, MMDDYYYY, YYYYDDMM, YYYYMMDD, DDMMYYYY, DDMMYY, MMDDYY, YYDDMM, YYMMDD --> </Validator> </Validators>
<Regex id="date_regex_1" validators="date_validator_1">\d{8}</Regex>
```
  
## <a name="changes-for-exchange-online"></a><span data-ttu-id="dfece-323">Exchange Online の変更</span><span class="sxs-lookup"><span data-stu-id="dfece-323">Changes for Exchange Online</span></span>

<span data-ttu-id="dfece-p155">以前は、DLP 用にカスタムの機密情報の種類をインポートするために Exchange Online PowerShell を使用することがありました。現在は、カスタムの機密情報の種類を Exchange 管理センターとコンプライアンス センターの両方で使用できるようになりました。この改善の一環で、カスタムの機密情報の種類をインポートする場合、コンプライアンス センター PowerShell の使用が必須になりました。Exchange PowerShell からはインポートできません。カスタムの機密情報の種類は以前と同様に使用できますが、コンプライアンス センターでカスタムの機密情報の種類を変更した場合、Exchange 管理センターに表示されるまでに最大 1 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="dfece-p155">Previously, you might have used Exchange Online PowerShell to import your custom sensitive information types for DLP. Now your custom sensitive information types can be used in both the Exchange admin center and the Compliance center. As part of this improvement, you should use Compliance center PowerShell to import your custom sensitive information types — you can't import them from the Exchange PowerShell anymore. Your custom sensitive information types will continue to work just like before; however, it may take up to one hour for changes made to custom sensitive information types in the Compliance center to appear in the Exchange admin center.</span></span>
  
<span data-ttu-id="dfece-328">コンプライアンス センターでは、**[New-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/new-dlpsensitiveinformationtyperulepackage)** コマンドレットを入力して、ルール パッケージをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="dfece-328">Note that in the Compliance center, you use the **[New-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/new-dlpsensitiveinformationtyperulepackage)** cmdlet to upload a rule package.</span></span> <span data-ttu-id="dfece-329">(以前は、Exchange 管理センターで **ClassificationRuleCollection** コマンドレットを使用していました。)</span><span class="sxs-lookup"><span data-stu-id="dfece-329">(Previously, in the Exchange admin center, you used the  **ClassificationRuleCollection**\` cmdlet.)</span></span> 
  
## <a name="upload-your-rule-package"></a><span data-ttu-id="dfece-330">ルール パッケージをアップロードする</span><span class="sxs-lookup"><span data-stu-id="dfece-330">Upload your rule package</span></span>

<span data-ttu-id="dfece-331">ルール パッケージをアップロードするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="dfece-331">To upload your rule package, do the following steps:</span></span>
  
1. <span data-ttu-id="dfece-332">ルールを Unicode エンコードで .xml ファイルとして保存します。</span><span class="sxs-lookup"><span data-stu-id="dfece-332">Save it as an .xml file with Unicode encoding.</span></span>
    
2. [<span data-ttu-id="dfece-333">コンプライアンス センター PowerShell に接続する</span><span class="sxs-lookup"><span data-stu-id="dfece-333">Connect to Compliance center PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)
    
3. <span data-ttu-id="dfece-334">次の構文を使用してください。</span><span class="sxs-lookup"><span data-stu-id="dfece-334">Use the following syntax:</span></span>

   ```powershell
   New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "PathToUnicodeXMLFile" -Encoding Byte -ReadCount 0)
   ```

   <span data-ttu-id="dfece-335">この例では、MyNewRulePack.xml という名前の Unicode XML ファイルを C:\My Documents からアップロードします。</span><span class="sxs-lookup"><span data-stu-id="dfece-335">This example uploads the Unicode XML file named MyNewRulePack.xml from C:\My Documents.</span></span>

   ```powershell
   New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "C:\My Documents\MyNewRulePack.xml" -Encoding Byte -ReadCount 0)
   ```

   <span data-ttu-id="dfece-336">構文とパラメーターの詳細情報については、[New-dlpsensitiveinformationtyperulepackage](/powershell/module/exchange/new-dlpsensitiveinformationtyperulepackage) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dfece-336">For detailed syntax and parameter information, see [New-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/new-dlpsensitiveinformationtyperulepackage).</span></span>

   > [!NOTE]
   > <span data-ttu-id="dfece-337">サポートされるルール パッケージの最大数は 10 ですが、各パッケージには複数の機密情報の種類の定義を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="dfece-337">The maximum number of rule packages supported is 10, but each package can contain the definition of multiple sensitive information types.</span></span>

4. <span data-ttu-id="dfece-338">新しい機密情報の種類が正常に作成されたことを確認するには、次に示す手順のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="dfece-338">To verify that you've successfully created a new sensitive information type, do any of the following steps:</span></span>

   - <span data-ttu-id="dfece-339">[Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) コマンドレットを実行して、新しいルール パッケージが一覧表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dfece-339">Run the [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet to verify the new rule package is listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationTypeRulePackage
     ``` 

   - <span data-ttu-id="dfece-340">[Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) コマンドレットを使用して、機密情報の種類が一覧表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dfece-340">Run the [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to verify the sensitive information type is listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType
     ``` 

     <span data-ttu-id="dfece-341">カスタムの機密情報の種類の場合、Publisher プロパティ値を Microsoft Corporation 以外に設定します。</span><span class="sxs-lookup"><span data-stu-id="dfece-341">For custom sensitive information types, the Publisher property value will be something other than Microsoft Corporation.</span></span>

   - <span data-ttu-id="dfece-342">\<Name\>Name を機密情報の種類の名前値 (たとえば、従業員 ID) に置き換えて、[Get-DlpSensitiveInformationType ](/powershell/module/exchange/get-dlpsensitiveinformationtype)コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="dfece-342">Replace \<Name\> with the Name value of the sensitive information type (example: Employee ID) and run the [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType -Identity "<Name>"
     ```
    
## <a name="potential-validation-issues-to-be-aware-of"></a><span data-ttu-id="dfece-343">注意する必要がある潜在的な検証の問題</span><span class="sxs-lookup"><span data-stu-id="dfece-343">Potential validation issues to be aware of</span></span>

<span data-ttu-id="dfece-p157">ルール パッケージの XML ファイルをアップロードすると、システムで XML が検証され、既知の不適切なパターンや明らかなパフォーマンスの問題が確認されます。検証で確認される既知の正規表現に関する問題について一部を紹介します。</span><span class="sxs-lookup"><span data-stu-id="dfece-p157">When you upload your rule package XML file, the system validates the XML and checks for known bad patterns and obvious performance issues. Here are some known issues that the validation checks for — a regular expression:</span></span>
  
- <span data-ttu-id="dfece-346">先頭または末尾に縦棒 "|" を指定することはできません。これは、空の一致とみなされるため、あらゆるものと一致します。</span><span class="sxs-lookup"><span data-stu-id="dfece-346">Cannot begin or end with alternator "|", which matches everything because it's considered an empty match.</span></span>
    
  <span data-ttu-id="dfece-347">たとえば、"|a" や "b|" では検証に合格しません。</span><span class="sxs-lookup"><span data-stu-id="dfece-347">For example, "|a" or "b|" will not pass validation.</span></span>
    
- <span data-ttu-id="dfece-348">先頭または末尾に ".{0,m}" パターンを指定することはできません。これは機能的な目的がなく、単にパフォーマンスが低下します。</span><span class="sxs-lookup"><span data-stu-id="dfece-348">Cannot begin or end with a ".{0,m}" pattern, which has no functional purpose and only impairs performance.</span></span>
    
  <span data-ttu-id="dfece-349">たとえば、".{0,50}ASDF" や "ASDF.{0,50}" では検証に合格しません。</span><span class="sxs-lookup"><span data-stu-id="dfece-349">For example, ".{0,50}ASDF" or "ASDF.{0,50}" will not pass validation.</span></span>
    
- <span data-ttu-id="dfece-350">".{0,m}" や ".{1,m}" をグループに含めることはできません。また、".\*" や ".+" をグループに含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="dfece-350">Cannot have ".{0,m}" or ".{1,m}" in groups, and cannot have ".\*" or ".+" in groups.</span></span>
    
  <span data-ttu-id="dfece-351">たとえば、"(.{0,50000})" では検証に合格しません。</span><span class="sxs-lookup"><span data-stu-id="dfece-351">For example, "(.{0,50000})" will not pass validation.</span></span>
    
- <span data-ttu-id="dfece-352">"{0,m}" または "{1,m}" リピーターを含む文字はグループ内に含めることができません。</span><span class="sxs-lookup"><span data-stu-id="dfece-352">Cannot have any character with "{0,m}" or "{1,m}" repeaters in groups.</span></span>
    
  <span data-ttu-id="dfece-353">たとえば、"(a\*)" では検証に合格しません。</span><span class="sxs-lookup"><span data-stu-id="dfece-353">For example, "(a\*)" will not pass validation.</span></span>
    
- <span data-ttu-id="dfece-354">先頭または末尾に ".{1,m}" を指定することはできません。代わりに、"." のみを使用してください。</span><span class="sxs-lookup"><span data-stu-id="dfece-354">Cannot begin or end with ".{1,m}"; instead, use just "."</span></span>
    
  <span data-ttu-id="dfece-355">たとえば、".{1,m}asdf" では検証に合格しません。代わりに、".asdf" のみを使用してください。</span><span class="sxs-lookup"><span data-stu-id="dfece-355">For example, ".{1,m}asdf" will not pass validation; instead, use just ".asdf".</span></span>
    
- <span data-ttu-id="dfece-356">グループに無制限のリピーター (「\*」や「+」など) を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="dfece-356">Cannot have an unbounded repeater (such as "\*" or "+") on a group.</span></span>
    
  <span data-ttu-id="dfece-357">たとえば、"(xx)\*" や "(xx)+" では検証に合格しません。</span><span class="sxs-lookup"><span data-stu-id="dfece-357">For example, "(xx)\*" and "(xx)+" will not pass validation.</span></span>
  
- <span data-ttu-id="dfece-358">キーワードの長さは最大 50 文字です。</span><span class="sxs-lookup"><span data-stu-id="dfece-358">Keywords have a maximum of 50 characters in Length.</span></span>  <span data-ttu-id="dfece-359">グループ内にこれを超えるキーワードがある場合、推奨される解決策は、用語のグループを[キーワード ディクショナリ](./create-a-keyword-dictionary.md)として作成し、ファイル内の Match または idMatch のエンティティの一部として XML 構造内のキーワード ディクショナリの GUID を参照することです。</span><span class="sxs-lookup"><span data-stu-id="dfece-359">If you have a keyword within a Group exceeding this, a suggested solution is to create the Group of terms as a [Keyword Dictionary](./create-a-keyword-dictionary.md) and reference the GUID of the Keyword Dictionary within the XML structure as part of the Entity for Match or idMatch in the file.</span></span>

- <span data-ttu-id="dfece-360">各カスタム機密情報タイプには、合計で最大 2048 個のキーワードを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="dfece-360">Each Custom Sensitive Information Type can have a maximum of 2048 keywords total.</span></span>

- <span data-ttu-id="dfece-361">1 つのテナントのキーワード辞書の最大サイズは、圧縮して 1 MB です。</span><span class="sxs-lookup"><span data-stu-id="dfece-361">The maximum size of Keyword Dictionaries in a single tenant is 1 MB compressed.</span></span> <span data-ttu-id="dfece-362">カスタムの機密情報の種類を作成する場合、同じ辞書を必要な回数だけ参照します。</span><span class="sxs-lookup"><span data-stu-id="dfece-362">Reference the same dictionary as many times as necessary when creating custom sensitive information types.</span></span> <span data-ttu-id="dfece-363">キーワード リストに 2048 個を超えるキーワードがある場合、またはキーワードの長さが 50 文字を超える場合は、まず機密情報の種類のカスタム キーワード リストを作成し、キーワード辞書を使用します。</span><span class="sxs-lookup"><span data-stu-id="dfece-363">Start with creating custom keyword lists in the sensitive information type and use keyword dictionaries if you have more than 2048 keywords in a keyword list or a keyword is larger than 50 characters in length.</span></span>

- <span data-ttu-id="dfece-364">テナントでは、最大 50 のキーワード辞書ベースの機密情報の種類が許可されます。</span><span class="sxs-lookup"><span data-stu-id="dfece-364">A maximum of 50 keyword dictionary based sensitive information types are allowed in a tenant.</span></span>

- <span data-ttu-id="dfece-365">各 Entity 要素に recommendedConfidence 属性が含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dfece-365">Ensure each Entity element contains a recommendedConfidence attribute.</span></span>

- <span data-ttu-id="dfece-366">PowerShell コマンドレットを使用する場合、逆シリアル化されたデータの最大戻りサイズは約 1 メガバイトです。</span><span class="sxs-lookup"><span data-stu-id="dfece-366">When using the PowerShell Cmdlet there is a maximum return size of the Deserialized Data of approximately 1 megabyte.</span></span>   <span data-ttu-id="dfece-367">これは、ルール パックの XML ファイルのサイズに影響します。</span><span class="sxs-lookup"><span data-stu-id="dfece-367">This will affect the size of your rule pack XML file.</span></span> <span data-ttu-id="dfece-368">処理時にエラーが発生しない一貫した結果を得るための推奨制限として、アップロードされたファイルを最大 770 メガバイトに制限してください。</span><span class="sxs-lookup"><span data-stu-id="dfece-368">Keep the uploaded file limited to a 770 kilobyte maximum as a suggested limit for consistent results without error when processing.</span></span>

- <span data-ttu-id="dfece-369">XML 構造では、スペース、タブ、復帰/ラインフィード エントリなどの書式設定文字は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="dfece-369">The XML structure does not require formatting characters such as spaces, tabs, or carriage return/linefeed entries.</span></span>  <span data-ttu-id="dfece-370">アップロードのスペースを最適化するときは、このことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="dfece-370">Take note of this when optimizing for space on uploads.</span></span> <span data-ttu-id="dfece-371">Microsoft Visual Code などのツールは、XML ファイルを圧縮するための結合線機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="dfece-371">Tools such as Microsoft Visual Code provide join line features to compact the XML file.</span></span>
    
<span data-ttu-id="dfece-372">パフォーマンスに影響する可能性のある問題がカスタムの機密情報の種類に含まれている場合は、アップロードされず、次のいずれかのエラー メッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="dfece-372">If a custom sensitive information type contains an issue that may affect performance, it won't be uploaded and you may see one of these error messages:</span></span>
  
- <span data-ttu-id="dfece-373">**予想よりも多くのコンテンツに一致する汎用的な限定詞 (‘+’、‘\*’ など)**</span><span class="sxs-lookup"><span data-stu-id="dfece-373">**Generic quantifiers which match more content than expected (e.g., '+', '\*')**</span></span>
    
- <span data-ttu-id="dfece-374">**ルックアラウンド アサーション**</span><span class="sxs-lookup"><span data-stu-id="dfece-374">**Lookaround assertions**</span></span>
    
- <span data-ttu-id="dfece-375">**複雑なグループ化と汎用的な限定詞の併用**</span><span class="sxs-lookup"><span data-stu-id="dfece-375">**Complex grouping in conjunction with general quantifiers**</span></span>
    
## <a name="recrawl-your-content-to-identify-the-sensitive-information"></a><span data-ttu-id="dfece-376">コンテンツを再クロールして機密情報を特定する</span><span class="sxs-lookup"><span data-stu-id="dfece-376">Recrawl your content to identify the sensitive information</span></span>

<span data-ttu-id="dfece-p162">Microsoft 365 は、検索クローラーを使用して、サイト コンテンツ内の機密情報を特定し、分類しています。SharePoint Online サイトと OneDrive for Business サイトのコンテンツが更新されると、自動的に再クロールされます。ただし、既存のすべてのコンテンツで新しいカスタムの機密情報の種類を特定するには、そのコンテンツを再クロールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfece-p162">Microsoft 365 uses the search crawler to identify and classify sensitive information in site content. Content in SharePoint Online and OneDrive for Business sites is recrawled automatically whenever it's updated. But to identify your new custom type of sensitive information in all existing content, that content must be recrawled.</span></span>
  
<span data-ttu-id="dfece-380">Microsoft 365 でテナント全体の再クロールを手動で要求することはできませんが、サイト コレクション、リスト、またはライブラリに対して再クロールすることはできます。詳細については、「[サイト、ライブラリ、またはリストのクロールとインデックス再作成を手動で要求する](/sharepoint/crawl-site-content)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfece-380">In Microsoft 365, you can't manually request a recrawl of an entire tenant, but you can do this for a site collection, list, or library — see [Manually request crawling and re-indexing of a site, a library or a list](/sharepoint/crawl-site-content).</span></span>
  
## <a name="reference-rule-package-xml-schema-definition"></a><span data-ttu-id="dfece-381">リファレンス: ルール パッケージ XML スキーマの定義</span><span class="sxs-lookup"><span data-stu-id="dfece-381">Reference: Rule package XML schema definition</span></span>

<span data-ttu-id="dfece-382">このマークアップをコピーし、XSD ファイルとして保存して、ルール パッケージの XML ファイルの検証に使用できます。</span><span class="sxs-lookup"><span data-stu-id="dfece-382">You can copy this markup, save it as an XSD file, and use it to validate your rule package XML file.</span></span>
  
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

## <a name="more-information"></a><span data-ttu-id="dfece-383">詳細情報</span><span class="sxs-lookup"><span data-stu-id="dfece-383">More information</span></span>

- [<span data-ttu-id="dfece-384">データ損失防止について</span><span class="sxs-lookup"><span data-stu-id="dfece-384">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)

- [<span data-ttu-id="dfece-385">機密情報の種類のエンティティ定義</span><span class="sxs-lookup"><span data-stu-id="dfece-385">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

- [<span data-ttu-id="dfece-386">DLP 関数の検索対象</span><span class="sxs-lookup"><span data-stu-id="dfece-386">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
