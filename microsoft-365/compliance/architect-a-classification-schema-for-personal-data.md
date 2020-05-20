---
title: 個人データの分類スキーマを設計する
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
audience: ITPro
ms.topic: overview
ms.collection:
- Strat_O365_Enterprise
- Ent_O365
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: 組織が一般データ保護規則 (GDPR) 計画の一環としてラベルを実装するかどうかを決定します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 17484e56206ba8f32db3c779623f2f8d7ed57496
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035169"
---
# <a name="architect-a-classification-schema-for-personal-data"></a><span data-ttu-id="45546-103">個人データの分類スキーマを設計する</span><span class="sxs-lookup"><span data-stu-id="45546-103">Architect a classification schema for personal data</span></span>

<span data-ttu-id="45546-p101">このシリーズの前の記事では、GDPR の対象となる個人データの識別に機密情報の種類を使用することに焦点を置いていました。機密情報の種類は分類の 1 形式であり、これが、必要な分類すべてである場合もあります。ただし、多数の組織ではラベルを使用した幅広いデータ ガバナンス戦略を取り入れています。このトピックを使用して、GDPR 計画の一環としてラベルを実装するかどうかを決定してください。実装する場合、このトピックは多少のガイダンスと例を提供します。</span><span class="sxs-lookup"><span data-stu-id="45546-p101">Previous articles in this series focus on using sensitive information types to identify personal data that is subject to GDPR. Sensitive information types are a form of classification. This might be all the classification you need. However, many organizations implement a broader data governance strategy using labels. Use this topic to decide if you also want to implement labels as part of your GDPR plan. If you do, this topic provides some guidance and examples.</span></span>

<span data-ttu-id="45546-p102">注: 組織の分類スキーマを定義してポリシー、ラベル、条件を構成するには、慎重な計画と準備が必要です。これは IT 部門が主導するプロセスではないことを認識することが必要です。法務およびコンプライアンス チームと連携を図り、組織のデータ用に適切な分類およびラベル付けスキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="45546-p102">Note: Defining a classification schema for an organization and configuring policies, labels, and conditions requires careful planning and preparation. It's important to realize that this isn't an IT driven process. Be sure to work with your legal and compliance team to develop an appropriate classification and labeling schema for your organization's data.</span></span>

## <a name="decide-if-youre-using-labels-in-addition-to-sensitive-data-types"></a><span data-ttu-id="45546-113">機密データの種類に加えてラベルを使用するかどうかを決定する</span><span class="sxs-lookup"><span data-stu-id="45546-113">Decide if you're using labels in addition to sensitive data types</span></span>

<span data-ttu-id="45546-p103">Microsoft 365 では、2 つある方法のいずれかを使用して個人情報を分類できます。いずれの方法も GDPR 保護に使用できます。機密情報の種類だけを使用して分類することを決定した場合、このトピックの残りの部分はスキップできます。</span><span class="sxs-lookup"><span data-stu-id="45546-p103">You can take one of two approaches for classification in Microsoft 365 for personal information. Either of these can be used for GDPR protection. If you decide to use only sensitive information types for classification, you can skip the rest of this topic.</span></span>

<span data-ttu-id="45546-117">次のいずれかのオプションを選んでください</span><span class="sxs-lookup"><span data-stu-id="45546-117">Choose one of the following options.</span></span>

### <a name="option-1-use-only-microsoft-365-sensitive-information-types"></a><span data-ttu-id="45546-118">オプション 1: Microsoft 365 の機密情報の種類だけを使用する</span><span class="sxs-lookup"><span data-stu-id="45546-118">Option 1: Use only Microsoft 365 sensitive information types</span></span>

- <span data-ttu-id="45546-119">機密情報の種類は GDPR やその他の規制の対象となる個人データの識別と保護に適しています。</span><span class="sxs-lookup"><span data-stu-id="45546-119">Sensitive information types work well to identify and protect personal data subject to GDPR and other types of regulations.</span></span>

- <span data-ttu-id="45546-120">これらは、組織でまだラベルを使用する広範なデータ ガバナンス計画がない場合、またはその実装が準備段階の場合に簡単に使用できます。</span><span class="sxs-lookup"><span data-stu-id="45546-120">These are simpler to use if your organization doesn't already have or plan to implement a broader data governance plan using labels.</span></span>

- <span data-ttu-id="45546-121">これらは DLP ルールと連携します (保持ラベルも同様です)。</span><span class="sxs-lookup"><span data-stu-id="45546-121">These work with DLP rules (so do retention labels).</span></span>

- <span data-ttu-id="45546-122">機密情報の種類は Cloud App Security とも連携するため、他の SaaS アプリでも機密データを検出することができます。</span><span class="sxs-lookup"><span data-stu-id="45546-122">Sensitive information types work with Cloud App Security so you can detect sensitive information in other SaaS apps.</span></span>

### <a name="option-2-use-sensitive-information-types--retention-labels"></a><span data-ttu-id="45546-123">オプション 2: 機密情報の種類と保持ラベルを使用する</span><span class="sxs-lookup"><span data-stu-id="45546-123">Option 2: Use sensitive information types + retention labels</span></span>

- <span data-ttu-id="45546-124">GDPR の対象となる個人データにラベルを自動的に適用するには、機密情報の種類が必要になるため、必須になります。</span><span class="sxs-lookup"><span data-stu-id="45546-124">You'll need sensitive information types to automatically apply labels to personal data that is subject to GDPR, so these are a prerequisite.</span></span>

- <span data-ttu-id="45546-125">保持ラベルを使用すると、GDPR の対象となる個人データを、組織の広範なデータ ガバナンス計画に含めることができます。</span><span class="sxs-lookup"><span data-stu-id="45546-125">Using retention labels allows you to include personal data that is subject to GDPR into a broader data governance plan for your organization.</span></span>

## <a name="develop-a-label-schema-that-includes-personal-data"></a><span data-ttu-id="45546-126">個人データを含むラベル スキーマを開発する</span><span class="sxs-lookup"><span data-stu-id="45546-126">Develop a label schema that includes personal data</span></span>

<span data-ttu-id="45546-p104">技術的な機能を使用してラベルと保護を適用する前に、まずは組織全体で連携して分類スキーマを定義します。組織内に既に分類スキーマがあるかもしれません。その場合は、個人データをより簡単に追加できます。このトピックでは、分類スキーマの例を 1 つ紹介します。必要な場合は、この例を出発点として使用できます。</span><span class="sxs-lookup"><span data-stu-id="45546-p104">Before using technical capabilities to apply labels and protection, first work across your organization to define a classification schema. Your organization might already have a classification schema, which makes it easier to add personal data. This topic includes an example classification schema. You can use this example as a starting point, if needed.</span></span>

### <a name="getting-started"></a><span data-ttu-id="45546-131">はじめに</span><span class="sxs-lookup"><span data-stu-id="45546-131">Getting started</span></span>

<span data-ttu-id="45546-p105">まず、実装するラベルの数と名前を決定します。これは、どのテクノロジを使用するか、どのようにラベルを適用するかといった点を意識せずに決定してください。このスキーマは、オンプレミスやその他のクラウド サービスに存在するデータを含め、組織全体で汎用的に適用します。</span><span class="sxs-lookup"><span data-stu-id="45546-p105">Begin by deciding on the number and names of labels to implement. Do this activity without worrying about which technology to use and how labels will be applied. Apply this schema universally throughout your organization, including data that resides on premises and in other cloud services.</span></span>

### <a name="recommendations"></a><span data-ttu-id="45546-135">推奨事項</span><span class="sxs-lookup"><span data-stu-id="45546-135">Recommendations</span></span> 

<span data-ttu-id="45546-136">ポリシー、ラベル、条件を設計および実装するには、次の推奨事項に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="45546-136">When designing and implementing policies, labels and conditions, consider following these recommendations:</span></span>

- <span data-ttu-id="45546-p106">既存の分類スキーマを使用する (ある場合) &ndash; 多くの組織では既に何らかの形でデータ分類を使用しています。既存のラベル スキーマを慎重に評価し、可能であればそのまま使用します。エンド ユーザーが認識できる使い慣れたラベルを使用すると、導入が円滑に進みます。</span><span class="sxs-lookup"><span data-stu-id="45546-p106">Use existing classification schema (if any) &ndash; Many organizations already are using data classification in some form. Carefully evaluate the existing label schema and if possible use it as is. Using familiar labels that are recognizable to the end user will drive adoption.</span></span>

- <span data-ttu-id="45546-p107">既定のポリシーとラベルから開始する &ndash; すべてのソリューションでは、事前定義されたポリシーとラベルが用意されています。それらを組織の法務および業務要件に照らして慎重に評価し、新しいものを作成するのではなく、それらを使用することを検討します。</span><span class="sxs-lookup"><span data-stu-id="45546-p107">Start with default policies and labels &ndash; All solutions come with a set of predefined policies and labels. Carefully evaluate these against the organization's legal and business requirements and consider using them instead of creating new ones.</span></span>

- <span data-ttu-id="45546-p108">少ない数から始める &ndash; 作成できるラベルの数に実質的な制限はありません。ただし、ラベルとサブ ラベルが多数ある場合、導入にマイナスの影響を与えます。多過ぎる選択肢は、選択肢がないのとほとんど変わりません。</span><span class="sxs-lookup"><span data-stu-id="45546-p108">Start small &ndash; There's virtually no limit to the number of labels that can be created. However, large numbers of labels and sub-labels will negatively impact the adoption. Too many choices often mean no choice at all.</span></span>

- <span data-ttu-id="45546-145">シナリオとユース ケースを使用する &ndash; 組織内の一般的なユース ケースを特定し、想定するラベルと分類の構成が実際に機能するかどうかを GDPR に由来するシナリオを使用して確認します。</span><span class="sxs-lookup"><span data-stu-id="45546-145">Use scenarios and use cases &ndash; Identify common use cases within the organization and use scenarios derived from the GDPR to verify if the envisioned label and classification configuration will work in practice.</span></span>

- <span data-ttu-id="45546-p109">新しいラベルに対する要求をすべて検証する &ndash; 各シナリオまたはユース ケースには新しいラベルが本当に必要か、既にあるラベルを使用できないかを確認します。ラベルの数を最小限に抑えることで、導入を促進できます。</span><span class="sxs-lookup"><span data-stu-id="45546-p109">Question every request for a new label &ndash; Does every scenario or use case really need a new label or can you use what you already have? Keeping the number of labels to a minimum improves adoption.</span></span>

- <span data-ttu-id="45546-p110">主要部門でサブラベル使用する &ndash; 一部の部門では、特定のラベルを必要とする特殊なニーズがあります。これらのラベルを既存のラベルのサブ ラベルとして定義し、組織全体ではなく、ユーザー グループに割り当てる範囲限定ポリシーを使用することを検討します。</span><span class="sxs-lookup"><span data-stu-id="45546-p110">Use sub-labels for key departments &ndash; Some departments will have specific needs that require specific labels. Define these labels as sub-labels to an existing label, and consider using scoped policies that are assigned to user groups instead of globally.</span></span>

- <span data-ttu-id="45546-p111">範囲限定ポリシーの使用を検討 &ndash; ポリシーの対象をユーザーのサブセットに限定すると、「ラベルのオーバーロード」を防止できます。範囲限定ポリシーを使用すると、ロールまたは部門固有の (サブ) ラベルを、その特定の部門に所属する従業員のみに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="45546-p111">Consider scoped policies &ndash; Policies targeted at subsets of users will prevent "label overload". A scoped policy lets you assign role or department-specific (sub-)labels to just employees that work for that specific department.</span></span>

- <span data-ttu-id="45546-p112">わかりやすいラベル名を使用する &ndash; ラベル名には専門用語、規格、略語を使用しないことが推奨されます。導入を促進するために、エンド ユーザーが認識できる名前を付けます。PII、PCI、HIPAA、LBI、MBI、HBI といったラベルではなく、「非業務」、「公開」、「一般」、「社外秘」、「極秘」などの名前の使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="45546-p112">Use meaningful label names &ndash; We recommend that you don't use jargon, standards, or acronyms as label names. Try to use names that resonate with the end user to improve adoption. Instead of using labels like PII, PCI, HIPAA, LBI, MBI, and HBI, consider names like Non-Business, Public, General, Confidential, and Highly Confidential.</span></span>

### <a name="example-classification-schema"></a><span data-ttu-id="45546-155">分類スキーマの例</span><span class="sxs-lookup"><span data-stu-id="45546-155">Example classification schema</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="45546-156"><strong>ラベル名</strong></span><span class="sxs-lookup"><span data-stu-id="45546-156"><strong>Label name</strong></span></span></th>
<th align="left"><span data-ttu-id="45546-157"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="45546-157"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="45546-158">個人</span><span class="sxs-lookup"><span data-stu-id="45546-158">Personal</span></span></td>
<td align="left"><span data-ttu-id="45546-159">ビジネス以外のデータ (個人使用のみ)。</span><span class="sxs-lookup"><span data-stu-id="45546-159">Non-business data, for personal use only.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="45546-160">公開</span><span class="sxs-lookup"><span data-stu-id="45546-160">Public</span></span></td>
<td align="left"><span data-ttu-id="45546-161">公開使用向けに明確に準備、承認されているビジネス データ。</span><span class="sxs-lookup"><span data-stu-id="45546-161">Business data that is specifically prepared and approved for public consumption.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="45546-162">顧客データ</span><span class="sxs-lookup"><span data-stu-id="45546-162">Customer data</span></span></td>
<td align="left"><span data-ttu-id="45546-p113">個人を特定できる情報を含むビジネス データ。例としては、クレジット カード番号、銀行口座番号、社会保障番号などがあります。</span><span class="sxs-lookup"><span data-stu-id="45546-p113">Business data that contains personal identifiable information. Examples are credit card numbers, bank account numbers, and social security numbers.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="45546-165">人事データ</span><span class="sxs-lookup"><span data-stu-id="45546-165">HR data</span></span></td>
<td align="left"><span data-ttu-id="45546-166">従業員番号や給与データなど、Contoso 社の社員の人事管理データ。</span><span class="sxs-lookup"><span data-stu-id="45546-166">Human Resource data about Contoso employees, such as employee number and salary data.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="45546-167">社外秘</span><span class="sxs-lookup"><span data-stu-id="45546-167">Confidential</span></span></td>
<td align="left"><span data-ttu-id="45546-p114">権限のないユーザーと共有すると、ビジネスに損害を与える可能性のある機密性の高いビジネス データ。例としては、契約書、セキュリティ レポート、予測サマリー、販売取引データなどがあります。</span><span class="sxs-lookup"><span data-stu-id="45546-p114">Sensitive business data that could cause damage to the business if shared with unauthorized people. Examples include contracts, security reports, forecast summaries, and sales account data.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="45546-170">非常に機密性の高い社外秘</span><span class="sxs-lookup"><span data-stu-id="45546-170">Highly confidential</span></span></td>
<td align="left"><span data-ttu-id="45546-p115">権限のないユーザーと共有すると、ビジネスに損害を与える可能性のある非常に機密性の高いビジネス データ。例としては、従業員情報と顧客情報、パスワード、ソース コード、発表前の財務レポートなどがあります。</span><span class="sxs-lookup"><span data-stu-id="45546-p115">Very sensitive business data that would cause damage to the business if it was shared with unauthorized people. Examples include employee and customer information, passwords, source code, and pre-announced financial reports.</span></span></td>
</tr>
</tbody>
</table>

## <a name="define-a-taxonomy-and-search-criteria-for-each-label"></a><span data-ttu-id="45546-173">各ラベルの分類と検索条件を定義する</span><span class="sxs-lookup"><span data-stu-id="45546-173">Define a taxonomy and search criteria for each label</span></span>

<span data-ttu-id="45546-p116">組織の分類スキーマを作成したら、次にこのデータを検索するための分類と検索条件を作成します。個人データの場合、この作業は、機密情報の種類を特定し、組織の環境に合わせて機密情報の種類をカスタマイズまたは新規作成した際に既に完了しています。</span><span class="sxs-lookup"><span data-stu-id="45546-p116">After developing a classification schema for your organization, the next step is to develop the taxonomy and search criteria for finding this data. For personal data, you've already completed this work by identifying sensitive information types and customizing or creating new sensitive information types for your environment.</span></span>

<span data-ttu-id="45546-p117">次の表には、組織用のスキーマ、分類、および検索条件の例を示します。ラベルは機密性の低いものから高いものの順に並べられ、複数のラベル条件と一致するデータが適切なラベルに割り当てられるようにしています。</span><span class="sxs-lookup"><span data-stu-id="45546-p117">The following table provides an example schema, taxonomy, and search criteria for an organization. The labels are ordered by sensitivity level from least sensitive to most sensitive to ensure that data that matches multiple label conditions is assigned the appropriate label.</span></span>

<span data-ttu-id="45546-178">注: 構成の例は例示のためのものであり、展開のガイダンスや参照情報として意図されたものではありません。</span><span class="sxs-lookup"><span data-stu-id="45546-178">Note: The configuration example is provided for illustration only and is not intended as deployment guidance or reference.</span></span>

<span data-ttu-id="45546-179">ここで重要な点は、GDPR 準拠のための個人データの分類に費やす作業が、組織全体の目的と一致している必要があるということです。</span><span class="sxs-lookup"><span data-stu-id="45546-179">The important takeaway is to ensure that the work you invest to classify personal data for GDPR compliance fits together with the objectives for your entire organization.</span></span>

### <a name="example-schema-taxonomy-and-search-criteria"></a><span data-ttu-id="45546-180">スキーマ、分類、および検索条件の例</span><span class="sxs-lookup"><span data-stu-id="45546-180">Example schema, taxonomy, and search criteria</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="45546-181"><strong>ラベル</strong></span><span class="sxs-lookup"><span data-stu-id="45546-181"><strong>Label</strong></span></span></th>
<th align="left"><span data-ttu-id="45546-182"><strong>分類</strong></span><span class="sxs-lookup"><span data-stu-id="45546-182"><strong>Taxonomy</strong></span></span></th>
<th align="left"><span data-ttu-id="45546-183"><strong>メソッド</strong></span><span class="sxs-lookup"><span data-stu-id="45546-183"><strong>Method</strong></span></span></th>
<th align="left"><span data-ttu-id="45546-184"><strong>検索構文</strong></span><span class="sxs-lookup"><span data-stu-id="45546-184"><strong>Search syntax</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="45546-185">個人</span><span class="sxs-lookup"><span data-stu-id="45546-185">Personal</span></span></td>
<td align="left"><span data-ttu-id="45546-186">エンド ユーザーにより手動で「個人」とラベル付けされたドキュメント。</span><span class="sxs-lookup"><span data-stu-id="45546-186">Documents manually labeled personal by the end user.</span></span></td>
<td align="left"><span data-ttu-id="45546-187">手動</span><span class="sxs-lookup"><span data-stu-id="45546-187">Manual</span></span></td>
<td align="left"><span data-ttu-id="45546-188">エンド ユーザーにより手動で「個人」とラベル付けされたドキュメント。</span><span class="sxs-lookup"><span data-stu-id="45546-188">Documents manually labeled personal by the end user.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="45546-189">パブリック</span><span class="sxs-lookup"><span data-stu-id="45546-189">Public</span></span></td>
<td align="left"><span data-ttu-id="45546-190">「Approved for Public Release ##/####」という大文字/小文字を区別しない語句を含み、# が任意の数字を示すドキュメント。</span><span class="sxs-lookup"><span data-stu-id="45546-190">Documents containing the case insensitive phrase Approved for Public Release ##/#### where # represents any digit.</span></span></td>
<td align="left"><p><span data-ttu-id="45546-191">KQL</span><span class="sxs-lookup"><span data-stu-id="45546-191">KQL</span></span></p>
<p><span data-ttu-id="45546-192">RegEx</span><span class="sxs-lookup"><span data-stu-id="45546-192">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="45546-193">KQL — Approved for Public Release\*</span><span class="sxs-lookup"><span data-stu-id="45546-193">KQL — Approved for Public Release\*</span></span></p>
<p><span data-ttu-id="45546-194">RegEx — (?i)(\bApproved for Public Release \d{2}\/\d{4}\b)</span><span class="sxs-lookup"><span data-stu-id="45546-194">RegEx — (?i)(\bApproved for Public Release \d{2}\/\d{4}\b)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="45546-195">顧客データ</span><span class="sxs-lookup"><span data-stu-id="45546-195">Customer data</span></span></td>
<td align="left"><span data-ttu-id="45546-196">EU 市民データのための機密情報の種類。</span><span class="sxs-lookup"><span data-stu-id="45546-196">Sensitive information types for EU citizen data.</span></span></td>
<td align="left"><span data-ttu-id="45546-197">機密情報の種類</span><span class="sxs-lookup"><span data-stu-id="45546-197">Sensitive information types</span></span></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="45546-198">人事 — 従業員データ</span><span class="sxs-lookup"><span data-stu-id="45546-198">Human Resources — Employee Data</span></span></td>
<td align="left"><span data-ttu-id="45546-199">CONTOSO-9##### という形式で大文字/小文字を区別する従業員 ID を含み、# が任意の数字を示すドキュメント。</span><span class="sxs-lookup"><span data-stu-id="45546-199">Documents that include the case-sensitive employee id in the format CONTOSO-9##### where # represents any digit.</span></span></td>
<td align="left"><p><span data-ttu-id="45546-200">KQL</span><span class="sxs-lookup"><span data-stu-id="45546-200">KQL</span></span></p>
<p><span data-ttu-id="45546-201">RegEx</span><span class="sxs-lookup"><span data-stu-id="45546-201">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="45546-202">KQL — CONTOSO-9\*</span><span class="sxs-lookup"><span data-stu-id="45546-202">KQL — CONTOSO-9\*</span></span></p>
<p><span data-ttu-id="45546-203">RegEx — (\bCONTOSO-9\d{5}\b)</span><span class="sxs-lookup"><span data-stu-id="45546-203">RegEx — (\bCONTOSO-9\d{5}\b)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="45546-204">人事 — 給与データ</span><span class="sxs-lookup"><span data-stu-id="45546-204">Human Resources — Salary Data</span></span></td>
<td align="left"><span data-ttu-id="45546-205">キーワード (大文字/小文字を区別しない)「Contoso 」と、キーワード (大文字/小文字を区別しない)「Salary」または「Compensation」を含むドキュメント</span><span class="sxs-lookup"><span data-stu-id="45546-205">Documents that include the keyword (not case sensitive) Contoso AND either keyword (not case sensitive) Salary OR Compensation</span></span></td>
<td align="left"><p><span data-ttu-id="45546-206">KQL</span><span class="sxs-lookup"><span data-stu-id="45546-206">KQL</span></span></p>
<p><span data-ttu-id="45546-207">RegEx</span><span class="sxs-lookup"><span data-stu-id="45546-207">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="45546-208">KQL — Contoso AND (Salary OR Compensation)</span><span class="sxs-lookup"><span data-stu-id="45546-208">KQL — Contoso AND (Salary OR Compensation)</span></span></p>
<p><span data-ttu-id="45546-209">RegEx — (\bCONTOSO-9\d{5}\b)</span><span class="sxs-lookup"><span data-stu-id="45546-209">RegEx — (\bCONTOSO-9\d{5}\b)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="45546-210">Confidential</span><span class="sxs-lookup"><span data-stu-id="45546-210">Confidential</span></span></td>
<td align="left"><span data-ttu-id="45546-211">語句 (大文字/小文字を区別しない)「Contoso Confidential」を含むドキュメント。</span><span class="sxs-lookup"><span data-stu-id="45546-211">Documents containing the phrase (not case sensitive) Contoso Confidential.</span></span></td>
<td align="left"><p><span data-ttu-id="45546-212">KQL</span><span class="sxs-lookup"><span data-stu-id="45546-212">KQL</span></span></p>
<p><span data-ttu-id="45546-213">RegEx</span><span class="sxs-lookup"><span data-stu-id="45546-213">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="45546-214">KQL — Contoso Confidential</span><span class="sxs-lookup"><span data-stu-id="45546-214">KQL — Contoso Confidential</span></span></p>
<p><span data-ttu-id="45546-215">RegEx — (?i)(\bContoso Confidential\b)</span><span class="sxs-lookup"><span data-stu-id="45546-215">RegEx — (?i)(\bContoso Confidential\b)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="45546-216">非常に機密性の高い社外秘</span><span class="sxs-lookup"><span data-stu-id="45546-216">Highly confidential</span></span></td>
<td align="left"><span data-ttu-id="45546-217">語句 (大文字/小文字を区別する)「Contoso Secret」または「Secret-C####」を含み、# が任意の数字を示すドキュメント。</span><span class="sxs-lookup"><span data-stu-id="45546-217">Documents that include either pharase (case sensitive) Contoso Secret or Secret-C#### where # represents any digit.</span></span></td>
<td align="left"><p><span data-ttu-id="45546-218">KQL</span><span class="sxs-lookup"><span data-stu-id="45546-218">KQL</span></span></p>
<p><span data-ttu-id="45546-219">RegEx</span><span class="sxs-lookup"><span data-stu-id="45546-219">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="45546-220">KQL — Contoso Secret OR Secret-C\*</span><span class="sxs-lookup"><span data-stu-id="45546-220">KQL — Contoso Secret OR Secret-C\*</span></span></p>
<p><span data-ttu-id="45546-221">RegEx — (?i)(\bContoso Secret\b)|(\bSecret-C\d{4}\b)</span><span class="sxs-lookup"><span data-stu-id="45546-221">RegEx — (?i)(\bContoso Secret\b)|(\bSecret-C\d{4}\b)</span></span></p></td>
</tr>
</tbody>
</table>
