---
title: 個人データの検索
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 2/7/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Office 365 の EU 一般データ保護規則 (GDPR) の対象となる個人データを検索して見つける方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e0d29697a28221b5ff998f5ce923c143bf7a0804
ms.sourcegitcommit: 1c90bcc5c56f24895f01c3e0423c3f6b73715c13
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44214581"
---
# <a name="search-for-and-find-personal-data"></a><span data-ttu-id="7ced1-103">個人データの検索</span><span class="sxs-lookup"><span data-stu-id="7ced1-103">Search for and find personal data</span></span>

<span data-ttu-id="7ced1-104">個人データは GDPR のもとで、欧州連合 (EU) 内で特定される個人、または特定可能な個人に関連するあらゆるデータとして、非常に広範に定義されています。</span><span class="sxs-lookup"><span data-stu-id="7ced1-104">Personal data is defined very broadly under the GDPR as any data that relates to an identified or identifiable natural person that is a resident of the European Union (EU).</span></span>

<span data-ttu-id="7ced1-105">記事 4: 定義</span><span class="sxs-lookup"><span data-stu-id="7ced1-105">Article 4 – Definitions</span></span>

> <span data-ttu-id="7ced1-106">'個人データ' とは特定される個人、または特定可能な個人 ('データ主体') に関連するあらゆる情報であり、特定可能な個人とは、その個人の名前、ID 番号、位置データ、オンライン ID、または物理的、生理学的、遺伝子上、心理的、経済的、文化的、社会的な識別情報に固有の 1 つ以上の因子を参照することによって直接または間接的に特定される人物です。</span><span class="sxs-lookup"><span data-stu-id="7ced1-106">'personal data' means any information relating to an identified or identifiable natural person ('data subject'); an identifiable natural person is one who can be identified, directly or indirectly, in particular by reference to an identifier such as a name, an identification number, location data, an online identifier or to one or more factors specific to the physical, physiological, genetic, mental, economic, cultural or social identity of that natural person;</span></span>

<span data-ttu-id="7ced1-107">この記事では、SharePoint Online および OneDrive for Business (すべての Microsoft 365 グループおよび Microsoft Teams のサイトを含む) に保管されている個人データを検索する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7ced1-107">This article demonstrates how to find personal data stored in SharePoint Online and OneDrive for Business (which includes the sites for all Microsoft 365 groups and Microsoft Teams).</span></span>

<span data-ttu-id="7ced1-108">GDPR の対象となる個人データを見つけることは、Office 365 の機密情報の種類の使用に依存します。</span><span class="sxs-lookup"><span data-stu-id="7ced1-108">Finding personal data subject to GDPR relies on using sensitive information types in Office 365.</span></span> <span data-ttu-id="7ced1-109">これらは、自動プロセスが正常性サービス番号やクレジット カード番号などの特定の情報の種類を認識する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="7ced1-109">These define how the automated process recognizes specific information types such as health service numbers and credit card numbers.</span></span> <span data-ttu-id="7ced1-110">データ損失防止ポリシーを使用して、送信中のメールで個人データを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="7ced1-110">You can use data loss prevention policies to find personal data in mail while in transit.</span></span> <span data-ttu-id="7ced1-111">GDPR 用に作成した機密情報の種類を使用して、メールで送信される個人情報の検索と保護を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7ced1-111">You can use the sensitive information types you curate for GDPR to find and protect personal information as it is sent through email.</span></span> <span data-ttu-id="7ced1-112">また、「[セキュリティ/コンプライアンス センターで DSR ケース ツールを使用して GDPR データ主体要求を管理する](https://docs.microsoft.com/microsoft-365/compliance/manage-gdpr-data-subject-requests-with-the-dsr-case-tool)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ced1-112">Also see [Managed GDPR data subject requests with the DSR case tool in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/manage-gdpr-data-subject-requests-with-the-dsr-case-tool).</span></span>

## <a name="use-content-search-to-find-personal-data"></a><span data-ttu-id="7ced1-113">コンテンツ検索を使用して個人データを検索する</span><span class="sxs-lookup"><span data-stu-id="7ced1-113">Use Content Search to find personal data</span></span>

<span data-ttu-id="7ced1-p102">Microsoft では、Office 365 の個人データ検索に 3 段階のアプローチをお勧めします。このトピックの残りの部分では、これらの各段階について説明します。</span><span class="sxs-lookup"><span data-stu-id="7ced1-p102">Microsoft recommends a three-stage approach to finding personal data in Office 365. The rest of this topic provides guidance for each of these stages.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="7ced1-116"><strong>手順</strong></span><span class="sxs-lookup"><span data-stu-id="7ced1-116"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="7ced1-117"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="7ced1-117"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7ced1-118">1. 機密情報の種類の検索</span><span class="sxs-lookup"><span data-stu-id="7ced1-118">1. Search for sensitive information types</span></span></p></td>
<td align="left"><p><span data-ttu-id="7ced1-p103">機密情報の種類を使用して個人データの検索を開始します。各機密情報の種類に対してコンテンツ検索クエリを作成します。クエリを実行し、結果を分析します。</span><span class="sxs-lookup"><span data-stu-id="7ced1-p103">Start by using sensitive information types to find personal data. Create a Content Search query for each sensitive information type. Run the query and analyze the results.</span></span></p>
<span data-ttu-id="7ced1-122">必要に応じてクエリにパラメーターを追加し、誤検知を減らします。</span><span class="sxs-lookup"><span data-stu-id="7ced1-122">If needed, add parameters to the query to reduce false positives:</span></span> <li><span data-ttu-id="7ced1-123">カウント範囲</span><span class="sxs-lookup"><span data-stu-id="7ced1-123">Count range</span></span></li>
    <li><span data-ttu-id="7ced1-124">信頼範囲</span><span class="sxs-lookup"><span data-stu-id="7ced1-124">Confidence range</span></span></li>
    <li><span data-ttu-id="7ced1-125">より複雑なクエリのためのその他のプロパティや演算子</span><span class="sxs-lookup"><span data-stu-id="7ced1-125">Other properties or operators for more complex queries</span></span></li>
<p><span data-ttu-id="7ced1-126">必要であれば、機密情報の種類を変更して組織の精度を向上させます。</span><span class="sxs-lookup"><span data-stu-id="7ced1-126">If necessary, modify a sensitive information type to improve accuracy for your organization:</span></span></p>
<p><li><span data-ttu-id="7ced1-127">XML で信頼度を直接調整します。</span><span class="sxs-lookup"><span data-stu-id="7ced1-127">Adjust the confidence level directly in the XML.</span></span></li></p>
<p><li><span data-ttu-id="7ced1-128">キーワードを追加します。</span><span class="sxs-lookup"><span data-stu-id="7ced1-128">Add key words.</span></span></li></p>
<p><li><span data-ttu-id="7ced1-129">キーワードの近接性要件を調整します。</span><span class="sxs-lookup"><span data-stu-id="7ced1-129">Adjust the proximity requirements for keywords.</span></span></li></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7ced1-130">2. キーワード クエリ言語 (KQL) を使用して環境内で追加の個人データを検索する</span><span class="sxs-lookup"><span data-stu-id="7ced1-130">2. Use Keyword Query Language (KQL) to find additional personal data in your environment</span></span></p></td>
<td align="left"><p><span data-ttu-id="7ced1-131">機密情報の種類に含まれていないデータを検索するには、KQL クエリ言語を使用してカスタム クエリを開発します。</span><span class="sxs-lookup"><span data-stu-id="7ced1-131">To find data not included in sensitive information types, use the KQL query language to develop custom queries.</span></span></p>
<p><span data-ttu-id="7ced1-132">これらの検索の結果をテストし、期待どおりの結果が得られるまで、KQL クエリ文字列を調整します。</span><span class="sxs-lookup"><span data-stu-id="7ced1-132">Test the results of these searches and adjust the KQL query string until you achieve the expected result.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7ced1-133">3. KQL クエリを使用して新しいカスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="7ced1-133">3. Create new custom sensitive information types using the KQL queries</span></span></p></td>
<td align="left"><span data-ttu-id="7ced1-p104">KQL クエリを最適化して対象のデータを検索した後、これらのクエリを使用して新しいカスタムの機密情報の種類を作成します。次に、これらカスタムの機密情報の種類を、DLP ポリシーやその他のツール、およびその他の KQL クエリ内でのコンテンツ検索に使用します。</span><span class="sxs-lookup"><span data-stu-id="7ced1-p104">After optimizing KQL queries to find target data, create new custom sensitive information types using these queries. You can then use these custom sensitive information types with Content Search, in DLP policies and other tools, and within other KQL queries.</span></span></td>
</tr>
</tbody>
</table>


## <a name="search-for-sensitive-information-types-using-content-search"></a><span data-ttu-id="7ced1-136">コンテンツ検索を使用した機密情報の種類の検索</span><span class="sxs-lookup"><span data-stu-id="7ced1-136">Search for sensitive information types using Content Search</span></span>

<span data-ttu-id="7ced1-137">Office 365 に含まれている機密情報の種類を使用して個人データの検索を開始します。</span><span class="sxs-lookup"><span data-stu-id="7ced1-137">Begin searching for personal data by using the sensitive information types that are included with Office 365.</span></span> <span data-ttu-id="7ced1-138">これらはセキュリティ/コンプライアンス センターの [分類] の下にリストされています。</span><span class="sxs-lookup"><span data-stu-id="7ced1-138">These are listed under Classification in the security center and compliance center.</span></span>

<span data-ttu-id="7ced1-139">このトピックでは、欧州連合の市民に適用される機密情報の種類の一部がリストされています。</span><span class="sxs-lookup"><span data-stu-id="7ced1-139">This topic includes a list of some sensitive information types that apply to citizens in the European Union.</span></span> <span data-ttu-id="7ced1-140">GDPR コンプライアンスを支援できる新しい追加については、セキュリティ センターまたはコンプライアンス センターを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7ced1-140">Check the security center or the compliance center for new additions that can help with GDPR compliance.</span></span>

<span data-ttu-id="7ced1-141">また次の記事も参照してください: [機密情報の種類と、それぞれの検索対象の一覧](https://docs.microsoft.com/microsoft-365/compliance/content-search)</span><span class="sxs-lookup"><span data-stu-id="7ced1-141">Also see this article: [List of sensitive information types and what each one looks for](https://docs.microsoft.com/microsoft-365/compliance/content-search).</span></span>

<span data-ttu-id="7ced1-p107">機密情報の種類は、自動化されたプロセスが銀行口座番号、健康保険番号、クレジット カード番号などの特定の情報の種類を認識できる方法を定義します。機密情報の種類は条件とも呼ばれます。機密情報の種類はパターンで定義され、正規表現または関数で識別できます。機密情報の種類はさらに、キーワードやチェックサムなどの確証的な証拠を使用して識別することもできます。また、評価プロセスでは信頼度や近接度も使用されます。</span><span class="sxs-lookup"><span data-stu-id="7ced1-p107">Sensitive information types define how the automated process recognizes specific information types such as bank account numbers, health service numbers, and credit card numbers. Sensitive information types are also referred to as conditions. A sensitive information type is defined by a pattern that can be identified by a regular expression or a function. In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type. Confidence level and proximity are also used in the evaluation process.</span></span>

<span data-ttu-id="7ced1-147">現時点では、メールボックス内に保管中のデータ検索には機密情報の種類を使用できません。</span><span class="sxs-lookup"><span data-stu-id="7ced1-147">At this time sensitive information types cannot be used to find data at rest in mailboxes.</span></span>

### <a name="using-content-search-with-sensitive-information-types"></a><span data-ttu-id="7ced1-148">機密情報の種類によるコンテンツ検索の使用</span><span class="sxs-lookup"><span data-stu-id="7ced1-148">Using Content Search with sensitive information types</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="7ced1-149"><strong>手順</strong></span><span class="sxs-lookup"><span data-stu-id="7ced1-149"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="7ced1-150"><strong>詳細情報</strong></span><span class="sxs-lookup"><span data-stu-id="7ced1-150"><strong>More information</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd"><td align="left"><p><span data-ttu-id="7ced1-151">セキュリティ/コンプライアンス センターでコンテンツ検索に進む</span><span class="sxs-lookup"><span data-stu-id="7ced1-151">Go to Content Search in the Security and Compliance Center</span></span></p></td>
<td align="left"><p><span data-ttu-id="7ced1-152">セキュリティ/コンプライアンス センターの左側のウィンドウで、**[検索と調査]** &gt; **[コンテンツ検索]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="7ced1-152">In the left pane of the Security &amp; Compliance Center, click **Search &amp; investigation** &gt; **Content search**.</span></span></p>
<p><span data-ttu-id="7ced1-153"><a href="https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a">セキュリティ/コンプライアンス センターでコンテンツ検索を実行する方法</a>に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7ced1-153">See <a href="https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a">Run a Content Search in the Security &amp; Compliance Center</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7ced1-154">それぞれの機密情報の種類に新しい検索項目を作成する</span><span class="sxs-lookup"><span data-stu-id="7ced1-154">Create a new search item for each sensitive information type</span></span></p></td>
<td align="left"><p><span data-ttu-id="7ced1-155">次の構文を使用してください。</span><span class="sxs-lookup"><span data-stu-id="7ced1-155">Use the following syntax:</span></span></p>
<blockquote>
<p><span data-ttu-id="7ced1-156">SensitiveType:"&lt;種類&gt;"</span><span class="sxs-lookup"><span data-stu-id="7ced1-156">SensitiveType:"&lt;type&gt;"</span></span></p>
</blockquote>
<p><span data-ttu-id="7ced1-157">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7ced1-157">For example:</span></span></p>
<blockquote>
<p><span data-ttu-id="7ced1-158">SensitiveType:&quot;France Passport Number&quot;</span><span class="sxs-lookup"><span data-stu-id="7ced1-158">SensitiveType:&quot;France Passport Number&quot;</span></span></p>
</blockquote>
<p><span data-ttu-id="7ced1-p108">SharePoint (OneDrive for Business を含む) に、検索の範囲を指定します。構文が完全に一致し、余分なスペースや入力ミスがないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7ced1-p108">Scope the search to SharePoint (includes OneDrive for Business). Make sure the syntax is exact and there are no extra spaces or typos.</span></span></p>
<p><span data-ttu-id="7ced1-161">「<a href="https://docs.microsoft.com/microsoft-365/compliance/form-a-query-to-find-sensitive-data-stored-on-sites">サイトに保存された機密データを検索するクエリの形成</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ced1-161">See <a href="https://docs.microsoft.com/microsoft-365/compliance/form-a-query-to-find-sensitive-data-stored-on-sites">Form a query to find sensitive data stored on sites</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7ced1-162">各検索の結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="7ced1-162">Review the results for each search</span></span></p></td>
<td align="left"><p><span data-ttu-id="7ced1-163">次のような種類の問題を確認して、クエリの精度が正確かどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="7ced1-163">Look for these types of issues to determine if the query accuracy is on target:</span></span></p>
<p><li><span data-ttu-id="7ced1-164">誤検知が多い</span><span class="sxs-lookup"><span data-stu-id="7ced1-164">Many false positives</span></span></li></p>
<p><li><span data-ttu-id="7ced1-165">データの既知のインスタンスがない</span><span class="sxs-lookup"><span data-stu-id="7ced1-165">Missing known instances of data</span></span></li></p>
<p><span data-ttu-id="7ced1-166">詳細については、<a href="https://docs.microsoft.com/microsoft-365/compliance/export-search-results">セキュリティ/コンプライアンス センターからコンテンツ検索の結果をエクスポートする方法</a>に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7ced1-166">See <a href="https://docs.microsoft.com/microsoft-365/compliance/export-search-results">Export Content Search results from the Security &amp; Compliance Center</a>.</span></span></p>
<p><span data-ttu-id="7ced1-167">注: Mozilla Firefox または Chrome を使用している場合、最初に Internet Explorer または Microsoft Edge を使用してレポートをダウンロードし、必要なアドオンをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ced1-167">Note: if you're using Mozilla Firefox or Chrome, you might need to first download reports using Internet Explorer or Edge in order to install the required add-in.</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="sensitive-information-types-for-eu-citizen-data"></a><span data-ttu-id="7ced1-168">EU 市民データのための機密情報の種類</span><span class="sxs-lookup"><span data-stu-id="7ced1-168">Sensitive information types for EU citizen data</span></span>

<span data-ttu-id="7ced1-p109">次のような機密情報の種類から開始します。EU 加盟国の個人データについては、その他にも多数の機密情報の種類が近日公開されます。</span><span class="sxs-lookup"><span data-stu-id="7ced1-p109">Start with these sensitive information types. Many more sensitive information types are coming soon for personal data in EU countries.</span></span>

> <span data-ttu-id="7ced1-171">ベルギーの国民番号</span><span class="sxs-lookup"><span data-stu-id="7ced1-171">Belgium National Number</span></span>
>
> <span data-ttu-id="7ced1-172">クレジット カード番号</span><span class="sxs-lookup"><span data-stu-id="7ced1-172">Credit Card Number</span></span>
>
> <span data-ttu-id="7ced1-173">クロアチアの身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="7ced1-173">Croatia Identity Card Number</span></span>
>
> <span data-ttu-id="7ced1-174">クロアチアの個人識別 (OIB) 番号</span><span class="sxs-lookup"><span data-stu-id="7ced1-174">Croatia Personal Identification (OIB) Number</span></span>
>
> <span data-ttu-id="7ced1-175">チェコの国民身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="7ced1-175">Czech National Identity Card Number</span></span>
>
> <span data-ttu-id="7ced1-176">デンマークの個人識別番号</span><span class="sxs-lookup"><span data-stu-id="7ced1-176">Denmark Personal Identification Number</span></span>
>
> <span data-ttu-id="7ced1-177">欧州連合のデビット カード番号</span><span class="sxs-lookup"><span data-stu-id="7ced1-177">EU Debit Card Number</span></span>
>
> <span data-ttu-id="7ced1-178">フィンランドの国民 ID</span><span class="sxs-lookup"><span data-stu-id="7ced1-178">Finland National ID</span></span>
>
> <span data-ttu-id="7ced1-179">フィンランドのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="7ced1-179">Finland Passport Number</span></span>
>
> <span data-ttu-id="7ced1-180">フランスの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="7ced1-180">France Driver's License Number</span></span>
>
> <span data-ttu-id="7ced1-181">フランスの国民識別カード (CNI)</span><span class="sxs-lookup"><span data-stu-id="7ced1-181">France National ID Card (CNI)</span></span>
>
> <span data-ttu-id="7ced1-182">フランスのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="7ced1-182">France Passport Number</span></span>
>
> <span data-ttu-id="7ced1-183">フランスの社会保障番号 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="7ced1-183">France Social Security Number (INSEE)</span></span>
>
> <span data-ttu-id="7ced1-184">ドイツの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="7ced1-184">German Driver's License Number</span></span>
>
> <span data-ttu-id="7ced1-185">ドイツの身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="7ced1-185">Germany Identity Card Number</span></span>
>
> <span data-ttu-id="7ced1-186">ドイツのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="7ced1-186">German Passport Number</span></span>
>
> <span data-ttu-id="7ced1-187">ギリシャの国民識別カード</span><span class="sxs-lookup"><span data-stu-id="7ced1-187">Greece National ID Card</span></span>
>
> <span data-ttu-id="7ced1-188">国際銀行口座番号 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="7ced1-188">International Banking Account Number (IBAN)</span></span>
>
> <span data-ttu-id="7ced1-189">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="7ced1-189">IP Address</span></span>
>
> <span data-ttu-id="7ced1-190">アイルランドの個人公共サービス (PPS) 番号</span><span class="sxs-lookup"><span data-stu-id="7ced1-190">Ireland Personal Public Service (PPS) Number</span></span>
>
> <span data-ttu-id="7ced1-191">イタリアの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="7ced1-191">Italy's Driver's License Number</span></span>
>
> <span data-ttu-id="7ced1-192">オランダの市民サービス (BSN) 番号</span><span class="sxs-lookup"><span data-stu-id="7ced1-192">Netherlands Citizen's Service (BSN) Number</span></span>
>
> <span data-ttu-id="7ced1-193">ノルウェーの識別番号</span><span class="sxs-lookup"><span data-stu-id="7ced1-193">Norway Identity Number</span></span>
>
> <span data-ttu-id="7ced1-194">ポーランドの ID カード</span><span class="sxs-lookup"><span data-stu-id="7ced1-194">Poland Identity Card</span></span>
>
> <span data-ttu-id="7ced1-195">ポーランドの国民 ID (PESEL)</span><span class="sxs-lookup"><span data-stu-id="7ced1-195">Poland National ID (PESEL)</span></span>
>
> <span data-ttu-id="7ced1-196">ポーランドのパスポート</span><span class="sxs-lookup"><span data-stu-id="7ced1-196">Poland Passport</span></span>
>
> <span data-ttu-id="7ced1-197">ポルトガルの市民カード番号</span><span class="sxs-lookup"><span data-stu-id="7ced1-197">Portugal Citizen Card Number</span></span>
>
> <span data-ttu-id="7ced1-198">スペインの社会保障番号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="7ced1-198">Spain Social Security Number (SSN)</span></span>
>
> <span data-ttu-id="7ced1-199">スウェーデンの国民 ID</span><span class="sxs-lookup"><span data-stu-id="7ced1-199">Sweden National ID</span></span>
>
> <span data-ttu-id="7ced1-200">スウェーデンのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="7ced1-200">Sweden Passport Number</span></span>
>
> <span data-ttu-id="7ced1-p110">英国の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="7ced1-p110">U.K. Driver's License Number</span></span>
>
> <span data-ttu-id="7ced1-p111">英国の選挙登録番号</span><span class="sxs-lookup"><span data-stu-id="7ced1-p111">U.K. Electoral Roll Number</span></span>
>
> <span data-ttu-id="7ced1-p112">英国の国民健康保険番号</span><span class="sxs-lookup"><span data-stu-id="7ced1-p112">U.K. National Health Service Number</span></span>
>
> <span data-ttu-id="7ced1-p113">英国の国民保険番号 (NINO)</span><span class="sxs-lookup"><span data-stu-id="7ced1-p113">U.K. National Insurance Number (NINO)</span></span>
>
> <span data-ttu-id="7ced1-p114">米国/英国のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="7ced1-p114">U.S./U.K. Passport Number</span></span>

## <a name="add-parameters-to-a-sensitive-information-type-query-to-hone-the-results"></a><span data-ttu-id="7ced1-211">機密情報の種類クエリにパラメーターを追加して、結果の精度を上げます。</span><span class="sxs-lookup"><span data-stu-id="7ced1-211">Add parameters to a sensitive information type query to hone the results</span></span>

<span data-ttu-id="7ced1-212">次のパラメーターを機密情報の種類クエリに追加できます。</span><span class="sxs-lookup"><span data-stu-id="7ced1-212">You can add these parameters to a sensitive information type query:</span></span>

-   <span data-ttu-id="7ced1-213">カウント範囲: 定義した数の機密情報がドキュメント内に出現した場合にそのドキュメントをクエリ結果に含めることができます。</span><span class="sxs-lookup"><span data-stu-id="7ced1-213">Count range — define the number of occurrences of sensitive information a document needs to contain before it's included in the query results.</span></span>

-   <span data-ttu-id="7ced1-214">信頼範囲: 85 (85%) など、検出された機密情報の種類が満たすべき信頼レベルです。</span><span class="sxs-lookup"><span data-stu-id="7ced1-214">Confidence range — the level of confidence that the detected sensitive type is actually a match, such as 85 (85%).</span></span>

<span data-ttu-id="7ced1-215">構文:</span><span class="sxs-lookup"><span data-stu-id="7ced1-215">Syntax:</span></span>

-   <span data-ttu-id="7ced1-216">SensitiveType:"\<種類\>|\<カウント範囲\>|\<信頼範囲\>"</span><span class="sxs-lookup"><span data-stu-id="7ced1-216">SensitiveType:"\<type\>|\<count range\>|\<confidence range\>"</span></span>

<span data-ttu-id="7ced1-217">例:</span><span class="sxs-lookup"><span data-stu-id="7ced1-217">Examples:</span></span>

-   <span data-ttu-id="7ced1-218">SensitiveType:"Credit Card Number|5" (5 つのクレジット カード番号を持つドキュメントのみを返します)</span><span class="sxs-lookup"><span data-stu-id="7ced1-218">SensitiveType:"Credit Card Number|5" (return only documents that contain exactly five credit card numbers)</span></span>

-   <span data-ttu-id="7ced1-219">SensitiveType:"Credit Card Number|\*|85.." (信頼範囲が 85% 以上)</span><span class="sxs-lookup"><span data-stu-id="7ced1-219">SensitiveType:"Credit Card Number|\*|85.." (confidence range is 85 percent or higher)</span></span>

<span data-ttu-id="7ced1-220">注: "SensitiveType" は大文字と小文字を区別しますが、クエリの残りの部分では区別しません。</span><span class="sxs-lookup"><span data-stu-id="7ced1-220">Note: "SensitiveType" is case sensitive, but the rest of the query is not.</span></span>

<span data-ttu-id="7ced1-p115">プロパティと演算子を使用してクエリを調整する方法を示すこともできます。詳細とその他の例については、「[サイトに保存された機密データを検索するクエリの形成](https://docs.microsoft.com/microsoft-365/compliance/form-a-query-to-find-sensitive-data-stored-on-sites)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ced1-p115">You can also use properties, and operators to illustrate how you can refine your queries. For more information and examples, see [Form a query to find sensitive data stored on sites](https://docs.microsoft.com/microsoft-365/compliance/form-a-query-to-find-sensitive-data-stored-on-sites).</span></span>
