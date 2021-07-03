---
title: Exact Data Match によりカスタムの機密情報の種類を作成する
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 完全なデータ一致に基づく分類で、カスタムの機密情報の種類を作成する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 17b9d9b1f551c62e42b2f5291f4d1fba8622f1ae
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287043"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification"></a><span data-ttu-id="9cd44-103">Exact Data Match に基づく分類で、カスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="9cd44-103">Create custom sensitive information types with Exact Data Match based classification</span></span>

<span data-ttu-id="9cd44-104">[カスタムの機密情報の種類](sensitive-information-type-learn-about.md) は機密性の高いアイテムの識別に利用され、これにより、不注意による共有や不適切な共有を防止することができます。</span><span class="sxs-lookup"><span data-stu-id="9cd44-104">[Custom sensitive information types](sensitive-information-type-learn-about.md) are used to help identify sensitive items so that you can prevent them from being inadvertently or inappropriately shared.</span></span> <span data-ttu-id="9cd44-105">次に基づいてカスタム機密情報の種類 (SIT) を定義します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-105">You define a custom sensitive information type (SIT)based on:</span></span>

- <span data-ttu-id="9cd44-106">パターン</span><span class="sxs-lookup"><span data-stu-id="9cd44-106">patterns</span></span>
- <span data-ttu-id="9cd44-107">*従業員*、*バッジ*、*ID* などのキーワード証拠</span><span class="sxs-lookup"><span data-stu-id="9cd44-107">keyword evidence such as *employee*, *badge*, or *ID*</span></span>
- <span data-ttu-id="9cd44-108">特定のパターンの証拠に対する文字の近接性</span><span class="sxs-lookup"><span data-stu-id="9cd44-108">character proximity to evidence in a particular pattern</span></span>
- <span data-ttu-id="9cd44-109">信頼度レベル</span><span class="sxs-lookup"><span data-stu-id="9cd44-109">confidence levels</span></span>

 <span data-ttu-id="9cd44-110">このようなカスタムの機密情報の種類は、多くの組織のビジネス ニーズを満たします。</span><span class="sxs-lookup"><span data-stu-id="9cd44-110">Such custom sensitive information types meet business needs for many organizations.</span></span>

<span data-ttu-id="9cd44-111">しかし、汎用的なパターンに基づいて一致を検出するカスタムの機密情報の種類 (SIT) ではなく、正確なデータ値を使用するカスタムの機密情報の種類が必要な場合はどうでしょう。</span><span class="sxs-lookup"><span data-stu-id="9cd44-111">But what if you wanted a custom sensitive information type (SIT) that uses exact data values, instead of one that found matches based on generic patterns?</span></span> <span data-ttu-id="9cd44-112">Exact Data Match (EDM) ベースの分類では、次の目的で設計されたカスタムの機密情報の種類を作成できます。</span><span class="sxs-lookup"><span data-stu-id="9cd44-112">With Exact Data Match (EDM)-based classification, you can create a custom sensitive information type that is designed to:</span></span>

- <span data-ttu-id="9cd44-113">動的に、簡単に更新する</span><span class="sxs-lookup"><span data-stu-id="9cd44-113">be dynamic and easily refreshed</span></span>
- <span data-ttu-id="9cd44-114">拡張性の高いものにする</span><span class="sxs-lookup"><span data-stu-id="9cd44-114">be more scalable</span></span>
- <span data-ttu-id="9cd44-115">結果的に誤検知の数を減らす</span><span class="sxs-lookup"><span data-stu-id="9cd44-115">result in fewer false-positives</span></span>
- <span data-ttu-id="9cd44-116">構造化された機密データを操作する</span><span class="sxs-lookup"><span data-stu-id="9cd44-116">work with structured sensitive data</span></span>
- <span data-ttu-id="9cd44-117">機密情報をより安全に処理する</span><span class="sxs-lookup"><span data-stu-id="9cd44-117">handle sensitive information more securely</span></span>
- <span data-ttu-id="9cd44-118">さまざまな Microsoft クラウド サービスで使用する</span><span class="sxs-lookup"><span data-stu-id="9cd44-118">be used with several Microsoft cloud services</span></span>

![EDM ベースの分類](../media/EDMClassification.png)

<span data-ttu-id="9cd44-120">EDM ベースの分類を使用すると、機密情報のデータベース内の正確な値を参照する、カスタムの機密情報の種類を作成できます。</span><span class="sxs-lookup"><span data-stu-id="9cd44-120">EDM-based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="9cd44-121">データベースは毎日更新できます。また、最大 1 億行のデータを格納できます。</span><span class="sxs-lookup"><span data-stu-id="9cd44-121">The database can be refreshed daily, and contain up to 100 million rows of data.</span></span> <span data-ttu-id="9cd44-122">そのため、従業員、患者、または顧客の出入りに合わせて記録が変更されても、カスタムの機密情報の種類は最新の状態が維持されます。</span><span class="sxs-lookup"><span data-stu-id="9cd44-122">So as employees, patients, or clients come and go, and records change, your custom sensitive information types remain current and applicable.</span></span> <span data-ttu-id="9cd44-123">また、EDM ベースの分類は、[データ損失防止ポリシー](dlp-learn-about-dlp.md)や [Microsoft Cloud App Security ファイル ポリシー](/cloud-app-security/data-protection-policies) などのポリシーと共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="9cd44-123">And, you can use EDM-based classification with policies, such as [data loss prevention policies](dlp-learn-about-dlp.md) or [Microsoft Cloud App Security file policies](/cloud-app-security/data-protection-policies).</span></span>

> [!NOTE]
> <span data-ttu-id="9cd44-124">Microsoft 365Information Protection では、次の 2 バイト文字セット言語がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9cd44-124">Microsoft 365 Information Protection supports double byte character set languages for:</span></span>
>
> - <span data-ttu-id="9cd44-125">中国語 (簡体字)</span><span class="sxs-lookup"><span data-stu-id="9cd44-125">Chinese (simplified)</span></span>
> - <span data-ttu-id="9cd44-126">中国語 (繁体字)</span><span class="sxs-lookup"><span data-stu-id="9cd44-126">Chinese (traditional)</span></span>
> - <span data-ttu-id="9cd44-127">韓国語</span><span class="sxs-lookup"><span data-stu-id="9cd44-127">Korean</span></span>
> - <span data-ttu-id="9cd44-128">日本語</span><span class="sxs-lookup"><span data-stu-id="9cd44-128">Japanese</span></span>
>
> <span data-ttu-id="9cd44-129">このサポートは、機密情報の種類で使用できます。</span><span class="sxs-lookup"><span data-stu-id="9cd44-129">This support is available for sensitive information types.</span></span> <span data-ttu-id="9cd44-130">詳細については、「[2バイト文字セットのリリースノート (preview) についての情報保護サポート](mip-dbcs-relnotes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cd44-130">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="9cd44-131">必要なライセンスとアクセス許可</span><span class="sxs-lookup"><span data-stu-id="9cd44-131">Required licenses and permissions</span></span>

<span data-ttu-id="9cd44-132">この記事で説明されているタスクを実行するには、全体管理者、コンプライアンス管理者、または Exchange Online の管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cd44-132">You must be a global admin, compliance administrator, or Exchange Online administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="9cd44-133">DLP アクセス許可の詳細については、「[アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cd44-133">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="9cd44-134">これらのサブスクリプションには、EDM ベースの分類が含まれています</span><span class="sxs-lookup"><span data-stu-id="9cd44-134">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="9cd44-135">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="9cd44-135">Office 365 E5</span></span>
- <span data-ttu-id="9cd44-136">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="9cd44-136">Microsoft 365 E5</span></span>
- <span data-ttu-id="9cd44-137">Microsoft 365 E5 Compliance </span><span class="sxs-lookup"><span data-stu-id="9cd44-137">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="9cd44-138">Microsoft E5/A5 Information Protection and Governance</span><span class="sxs-lookup"><span data-stu-id="9cd44-138">Microsoft E5/A5 Information Protection and Governance</span></span>

## <a name="portal-links-for-your-subscription"></a><span data-ttu-id="9cd44-139">サブスクリプションのポータルリンク</span><span class="sxs-lookup"><span data-stu-id="9cd44-139">Portal links for your subscription</span></span>

|<span data-ttu-id="9cd44-140">ポータル</span><span class="sxs-lookup"><span data-stu-id="9cd44-140">Portal</span></span>|<span data-ttu-id="9cd44-141">世界中の GCC</span><span class="sxs-lookup"><span data-stu-id="9cd44-141">World Wide/GCC</span></span>|<span data-ttu-id="9cd44-142">GCC-High</span><span class="sxs-lookup"><span data-stu-id="9cd44-142">GCC-High</span></span>|<span data-ttu-id="9cd44-143">DOD</span><span class="sxs-lookup"><span data-stu-id="9cd44-143">DOD</span></span>|
|---|---|---|---|
|<span data-ttu-id="9cd44-144">Office SCC</span><span class="sxs-lookup"><span data-stu-id="9cd44-144">Office SCC</span></span>|<span data-ttu-id="9cd44-145">protection.office.com</span><span class="sxs-lookup"><span data-stu-id="9cd44-145">protection.office.com</span></span>|<span data-ttu-id="9cd44-146">scc.office365.us</span><span class="sxs-lookup"><span data-stu-id="9cd44-146">scc.office365.us</span></span>|<span data-ttu-id="9cd44-147">scc.protection.apps.mil</span><span class="sxs-lookup"><span data-stu-id="9cd44-147">scc.protection.apps.mil</span></span>|
|<span data-ttu-id="9cd44-148">Microsoft 365 セキュリティ センター</span><span class="sxs-lookup"><span data-stu-id="9cd44-148">Microsoft 365 Security center</span></span>|<span data-ttu-id="9cd44-149">security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9cd44-149">security.microsoft.com</span></span>|<span data-ttu-id="9cd44-150">security.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="9cd44-150">security.microsoft.us</span></span>|<span data-ttu-id="9cd44-151">security.apps.mil</span><span class="sxs-lookup"><span data-stu-id="9cd44-151">security.apps.mil</span></span>|
|<span data-ttu-id="9cd44-152">Microsoft 365 コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="9cd44-152">Microsoft 365 Compliance center</span></span>|<span data-ttu-id="9cd44-153">compliance.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9cd44-153">compliance.microsoft.com</span></span>|<span data-ttu-id="9cd44-154">compliance.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="9cd44-154">compliance.microsoft.us</span></span>|<span data-ttu-id="9cd44-155">compliance.apps.mil</span><span class="sxs-lookup"><span data-stu-id="9cd44-155">compliance.apps.mil</span></span>|

## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="9cd44-156">ワークフローの概要</span><span class="sxs-lookup"><span data-stu-id="9cd44-156">The work flow at a glance</span></span>

|<span data-ttu-id="9cd44-157">フェーズ</span><span class="sxs-lookup"><span data-stu-id="9cd44-157">Phase</span></span>|<span data-ttu-id="9cd44-158">前提条件</span><span class="sxs-lookup"><span data-stu-id="9cd44-158">What's needed</span></span>|
|---|---|
|[<span data-ttu-id="9cd44-159">パート 1: EDM ベースの分類をセットアップする</span><span class="sxs-lookup"><span data-stu-id="9cd44-159">Part 1: Set up EDM-based classification</span></span>](#part-1-set-up-edm-based-classification)<br/><br/><span data-ttu-id="9cd44-160">(適宜)</span><span class="sxs-lookup"><span data-stu-id="9cd44-160">(As needed)</span></span><br/><span data-ttu-id="9cd44-161">- [データベーススキーマを編集する](#editing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="9cd44-161">- [Edit the database schema](#editing-the-schema-for-edm-based-classification)</span></span> <br/><span data-ttu-id="9cd44-162">- [スキーマを削除する](#removing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="9cd44-162">- [Remove the schema](#removing-the-schema-for-edm-based-classification)</span></span>|<span data-ttu-id="9cd44-163">- 機密データへの読み取りアクセス</span><span class="sxs-lookup"><span data-stu-id="9cd44-163">- Read access to the sensitive data</span></span><br/><span data-ttu-id="9cd44-164">- XML 形式のデータベース スキーマ (例を提供)</span><span class="sxs-lookup"><span data-stu-id="9cd44-164">- Database schema in XML format (example provided)</span></span><br/><span data-ttu-id="9cd44-165">- XML 形式のルール パッケージ (例を提供)</span><span class="sxs-lookup"><span data-stu-id="9cd44-165">- Rule package in XML format (example provided)</span></span><br/><span data-ttu-id="9cd44-166">- セキュリティ/コンプライアンス センターへの管理者権限 (PowerShell を使用)</span><span class="sxs-lookup"><span data-stu-id="9cd44-166">- Admin permissions to the Security & Compliance Center (using PowerShell)</span></span>|
|[<span data-ttu-id="9cd44-167">パート 2: 機密データをハッシュしアップロードする</span><span class="sxs-lookup"><span data-stu-id="9cd44-167">Part 2: Hash and upload the sensitive data</span></span>](#part-2-hash-and-upload-the-sensitive-data)<br/><br/><span data-ttu-id="9cd44-168">(適宜)</span><span class="sxs-lookup"><span data-stu-id="9cd44-168">(As needed)</span></span><br/>[<span data-ttu-id="9cd44-169">データを更新する</span><span class="sxs-lookup"><span data-stu-id="9cd44-169">Refresh the data</span></span>](#refreshing-your-sensitive-information-database)|<span data-ttu-id="9cd44-170">- カスタムのセキュリティ グループとユーザー アカウント</span><span class="sxs-lookup"><span data-stu-id="9cd44-170">- Custom security group and user account</span></span><br/><span data-ttu-id="9cd44-171">- EDM アップロード エージェントを使用するコンピューターへのローカル管理者アクセス</span><span class="sxs-lookup"><span data-stu-id="9cd44-171">- Local admin access to machine with EDM Upload Agent</span></span><br/><span data-ttu-id="9cd44-172">- 機密データへの読み取りアクセス</span><span class="sxs-lookup"><span data-stu-id="9cd44-172">- Read access to the sensitive data</span></span><br/><span data-ttu-id="9cd44-173">- データ更新のプロセスとスケジュール</span><span class="sxs-lookup"><span data-stu-id="9cd44-173">- Process and schedule for refreshing the data</span></span>|
|[<span data-ttu-id="9cd44-174">パート 3: Microsoft クラウド サービスで EDM ベースの分類を使用する</span><span class="sxs-lookup"><span data-stu-id="9cd44-174">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services)|<span data-ttu-id="9cd44-175">- DLP を使用する Microsoft 365 サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="9cd44-175">- Microsoft 365 subscription with DLP</span></span><br/><span data-ttu-id="9cd44-176">- 有効化された EDM ベースの分類機能</span><span class="sxs-lookup"><span data-stu-id="9cd44-176">- EDM-based classification feature enabled</span></span>|

### <a name="part-1-set-up-edm-based-classification"></a><span data-ttu-id="9cd44-177">パート 1: EDM ベースの分類をセットアップする</span><span class="sxs-lookup"><span data-stu-id="9cd44-177">Part 1: Set up EDM-based classification</span></span>

<span data-ttu-id="9cd44-178">EDM ベースの分類の設定と構成には、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9cd44-178">Setting up and configuring EDM-based classification involves:</span></span>

1. [<span data-ttu-id="9cd44-179">機密データを .csv .tsv 形式で保存する</span><span class="sxs-lookup"><span data-stu-id="9cd44-179">Saving sensitive data in .csv or .tsv format</span></span>](#save-sensitive-data-in-csv-or-tsv-format)
2. [<span data-ttu-id="9cd44-180">機密情報データベース スキーマを定義する</span><span class="sxs-lookup"><span data-stu-id="9cd44-180">Define your sensitive information database schema</span></span>](#define-the-schema-for-your-database-of-sensitive-information)
3. [<span data-ttu-id="9cd44-181">ルール パッケージを作成する</span><span class="sxs-lookup"><span data-stu-id="9cd44-181">Create a rule package</span></span>](#set-up-a-rule-package)

#### <a name="save-sensitive-data-in-csv-or-tsv-format"></a><span data-ttu-id="9cd44-182">機密データを .csv .tsv 形式で保存する</span><span class="sxs-lookup"><span data-stu-id="9cd44-182">Save sensitive data in .csv or .tsv format</span></span>

1. <span data-ttu-id="9cd44-183">使用する機密情報を特定します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-183">Identify the sensitive information you want to use.</span></span> <span data-ttu-id="9cd44-184">データをアプリにエクスポートし、Microsoft Excelファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-184">Export the data to an app, such as Microsoft Excel, and save the file in a text file.</span></span> <span data-ttu-id="9cd44-185">ファイルは、.csv (コンマ区切り値)、.tsv (タブ区切り値)、またはパイプ区切り (|) 形式で保存できます。</span><span class="sxs-lookup"><span data-stu-id="9cd44-185">The file can be saved in .csv (comma-separated values), .tsv (tab-separated values), or pipe-separated (|) format.</span></span> <span data-ttu-id="9cd44-186">データ値に住所などのコンマが含まれている場合は、.tsv 形式をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9cd44-186">The .tsv format is recommended in cases where your data values may included commas, such as street addresses.</span></span>
<span data-ttu-id="9cd44-187">データ ファイルには、次のデータを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="9cd44-187">The data file can include a maximum of:</span></span>
   - <span data-ttu-id="9cd44-188">最大 1 億行の機密データ</span><span class="sxs-lookup"><span data-stu-id="9cd44-188">Up to 100 million rows of sensitive data</span></span>
   - <span data-ttu-id="9cd44-189">データ ソースごとに最大 32 列 (フィールド)</span><span class="sxs-lookup"><span data-stu-id="9cd44-189">Up to 32 columns (fields) per data source</span></span>
   - <span data-ttu-id="9cd44-190">検索可能としてマークされた列 (フィールド) を最大 5 列</span><span class="sxs-lookup"><span data-stu-id="9cd44-190">Up to 5 columns (fields) marked as searchable</span></span>

2. <span data-ttu-id="9cd44-191">EDM ベースの分類に使用されるフィールドの名前が最初の行に含まれる.csvまたは .tsv ファイル内の機密データを構造化します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-191">Structure the sensitive data in the .csv or .tsv file such that the first row includes the names of the fields used for EDM-based classification.</span></span> <span data-ttu-id="9cd44-192">ファイルには、"ssn"、"birthdate"、"firstname"、"lastname" などのフィールド名が含まれ得ます。</span><span class="sxs-lookup"><span data-stu-id="9cd44-192">In your file you might have field names such as "ssn", "birthdate", "firstname", "lastname".</span></span> <span data-ttu-id="9cd44-193">列見出しの名前にスペースやアンダースコアを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="9cd44-193">The column header names can't include spaces or underscores.</span></span> <span data-ttu-id="9cd44-194">たとえば、この記事で使用するサンプルの .csv ファイルは *PatientRecords.csv* と呼ばれており、その列には *PatientID*、*MRN*、*LastName*、*FirstName*、*SSN* などが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9cd44-194">For example, the sample .csv file that we use in this article is named *PatientRecords.csv*, and its columns include *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN*, and more.</span></span>

3. <span data-ttu-id="9cd44-195">機密データ フィールドの形式に注意してください。</span><span class="sxs-lookup"><span data-stu-id="9cd44-195">Pay attention to the format of the sensitive data fields.</span></span> <span data-ttu-id="9cd44-196">特に、コンテンツにコンマを含む可能性があるフィールド (たとえば、値 "Seattle,WA" を含む住所) は、.csv 形式が選択されている場合に解析すると、2 つの別個のフィールドとして解析されます。</span><span class="sxs-lookup"><span data-stu-id="9cd44-196">In particular, fields that may contain commas in their content, for example, a street address that contains the value "Seattle,WA" would be parsed as two separate fields when parsed if the .csv format is selected.</span></span> <span data-ttu-id="9cd44-197">この問題を回避するには、.tsv 形式を使用するか、機密データ テーブルの値を二重引用符で囲むコンマを囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cd44-197">To avoid this, use the .tsv format or surrounded the comma containing values by double quotes in the sensitive data table.</span></span> <span data-ttu-id="9cd44-198">コンマを含む値にスペースも含まれている場合は、対応する形式に一致するカスタム SIT を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cd44-198">If comma containing values also contain spaces, you need to create a custom SIT that matches the corresponding format.</span></span> <span data-ttu-id="9cd44-199">たとえば、コンマとスペースを含む複数単語文字列を検出する SIT。</span><span class="sxs-lookup"><span data-stu-id="9cd44-199">For example, a SIT that detects multi-word string with commas and spaces in it.</span></span>

#### <a name="define-the-schema-for-your-database-of-sensitive-information"></a><span data-ttu-id="9cd44-200">機密情報のデータベースのスキーマを定義する</span><span class="sxs-lookup"><span data-stu-id="9cd44-200">Define the schema for your database of sensitive information</span></span>

<span data-ttu-id="9cd44-201">ビジネス上または技術的な理由で、PowerShell またはコマンド ラインを使用してスキーマと EDM の機密情報の種類のパターン (ルール パッケージ) を作成しない場合は、 [Exact Data Match スキーマと機密情報の種類ウィザード](sit-edm-wizard.md)を使って作成できます。</span><span class="sxs-lookup"><span data-stu-id="9cd44-201">If for business or technical reasons, you prefer not to use PowerShell or command line to create your schema and EDM sensitive info type pattern (rule package), you can use the [Exact Data Match Schema and Sensitive Information Type Wizard](sit-edm-wizard.md) to create them.</span></span> <span data-ttu-id="9cd44-202">スキーマおよび EDM の機密情報の種類パターンの作成が完了したら、EDM ベースの機密情報の種類を使用できるようにするために必要なすべての手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-202">When you are done creating the schema and EDM sensitive info type pattern, return to complete all the steps necessary to make your EDM based sensitive information type available for use.</span></span>

> [!NOTE]
> <span data-ttu-id="9cd44-203">完全一致スキーマと機密情報の種類ウィザードは、World Wide クラウドと GCC クラウドでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="9cd44-203">The Exact Data Match Schema and Sensitive Information Type Wizard is only available for the World Wide and GCC clouds only.</span></span>

1. <span data-ttu-id="9cd44-204">機密情報のデータベースのスキーマを XML 形式で定義します (次の例と同様)。</span><span class="sxs-lookup"><span data-stu-id="9cd44-204">Define the schema for the database of sensitive information in XML format (similar to our example below).</span></span> <span data-ttu-id="9cd44-205">このスキーマ ファイルの名前を **edm.xml** にして、データベースの各列に対して構文を使用する行があるように構成します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-205">Name this schema file **edm.xml**, and configure it such that for each column in the database, there is a line that uses the syntax:</span></span>

      <span data-ttu-id="9cd44-206">`\<Field name="" searchable=""/\>`.</span><span class="sxs-lookup"><span data-stu-id="9cd44-206">`\<Field name="" searchable=""/\>`.</span></span>

      - <span data-ttu-id="9cd44-207">*Field name* の値に列名を使用します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-207">Use column names for *Field name* values.</span></span>
      - <span data-ttu-id="9cd44-208">*searchable="true"* を使用して、最大 5 つのフィールドで検索可能にします。</span><span class="sxs-lookup"><span data-stu-id="9cd44-208">Use *searchable="true"* for the fields that you want to be searchable up to a maximum of 5 fields.</span></span> <span data-ttu-id="9cd44-209">少なくとも 1 つのフィールドは検索可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cd44-209">At least one field must be searchable.</span></span>

      <span data-ttu-id="9cd44-210">たとえば、次の XML ファイルは患者レコードのデータベースのスキーマを定義します。検索可能として指定された 5 つのフィールドは、*PatientID*、*MRN*、*SSN*、*Phone*、*DOB* です。</span><span class="sxs-lookup"><span data-stu-id="9cd44-210">As an example, the following XML file defines the schema for a patient records database, with five fields specified as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span>

      <span data-ttu-id="9cd44-211">(この例は、コピー、変更、使用することができます。)</span><span class="sxs-lookup"><span data-stu-id="9cd44-211">(You can copy, modify, and use our example.)</span></span>

      ```xml
      <EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
            <DataStore name="PatientRecords" description="Schema for patient records" version="1">
                  <Field name="PatientID" searchable="true" caseInsensitive="true" ignoredDelimiters="-,/,*,#,^" />
                  <Field name="MRN" searchable="true" />
                  <Field name="FirstName" />
                  <Field name="LastName" />
                  <Field name="SSN" searchable="true" />
                  <Field name="Phone" searchable="true" />
                  <Field name="DOB" searchable="true" />
                  <Field name="Gender" />
                  <Field name="Address" />
            </DataStore>
      </EdmSchema>
      ```

##### <a name="configurable-match-using-the-caseinsensitive-and-ignoreddelimiters-fields"></a><span data-ttu-id="9cd44-212">大文字と小文字を区別せず、区切り文字フィールドを無視する構成可能な一致</span><span class="sxs-lookup"><span data-stu-id="9cd44-212">Configurable match using the caseInsensitive and ignoredDelimiters fields</span></span>

<span data-ttu-id="9cd44-213">上記のXMLサンプルは、`caseInsensitive` フィールドと `ignoredDelimiters` フィールドを使用しています。</span><span class="sxs-lookup"><span data-stu-id="9cd44-213">The above XML sample makes use of the `caseInsensitive` and the `ignoredDelimiters` fields.</span></span>

<span data-ttu-id="9cd44-214">スキーマ定義に `true` の値に設定された \***caseInsensitive** _ フィールドを含めると、EDM は `PatientID` フィールドの大文字と小文字の違いに基づいてアイテムを除外しません。</span><span class="sxs-lookup"><span data-stu-id="9cd44-214">When you include the \***caseInsensitive** _ field set to the value of `true` in your schema definition, EDM will not exclude an item based on case differences for `PatientID` field.</span></span> <span data-ttu-id="9cd44-215">したがって、EDM は、`PatientID` _ *FOO-1234*\* と **fOo-1234** が同一であると見なします。</span><span class="sxs-lookup"><span data-stu-id="9cd44-215">So EDM will see, `PatientID` _ *FOO-1234*\* and **fOo-1234** as being identical.</span></span>

<span data-ttu-id="9cd44-216">サポートされている文字を含む \***ignoredDelimiters** _ フィールドを含めると、EDM は `PatientID` 内のそれらの文字を無視します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-216">When you include the \***ignoredDelimiters** _ field with supported characters,  EDM will ignore those characters in the `PatientID`.</span></span> <span data-ttu-id="9cd44-217">したがって、EDM は、`PatientID` _ *FOO-1234*\* と `PatientID` **FOO#1234** が同一であると見なします。</span><span class="sxs-lookup"><span data-stu-id="9cd44-217">So EDM will see, `PatientID` _ *FOO-1234*\* and `PatientID` **FOO#1234** as being identical.</span></span> <span data-ttu-id="9cd44-218">`ignoredDelimiters` フラグは英数字以外の文字をサポートします。次にいくつかの例を示します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-218">The `ignoredDelimiters` flag supports any non-alphanumeric character, here are some examples:</span></span>

- <span data-ttu-id="9cd44-219">\.</span><span class="sxs-lookup"><span data-stu-id="9cd44-219">\.</span></span>
- \-
- \/
- \_
- \*
- \^
- \#
- \!
- \?
- \[
- \]
- \{
- \}
- \\
- \~
- \;

<span data-ttu-id="9cd44-220">`ignoredDelimiters`フラグは以下をサポートしていません:</span><span class="sxs-lookup"><span data-stu-id="9cd44-220">The `ignoredDelimiters` flag doesn't support:</span></span>

- <span data-ttu-id="9cd44-221">0 から 9 の文字</span><span class="sxs-lookup"><span data-stu-id="9cd44-221">characters 0-9</span></span>
- <span data-ttu-id="9cd44-222">A から Z</span><span class="sxs-lookup"><span data-stu-id="9cd44-222">A-Z</span></span>
- <span data-ttu-id="9cd44-223">a から z</span><span class="sxs-lookup"><span data-stu-id="9cd44-223">a-z</span></span>
- \"
- \,

<span data-ttu-id="9cd44-224">この例では、`caseInsensitive` と`ignoredDelimiters` の両方が使用されている場合、EDMは **FOO-1234** と **fOo#1234** を同一と見なし、アイテムを患者記録の機密情報タイプとして分類します。 </span><span class="sxs-lookup"><span data-stu-id="9cd44-224">In this example, where both `caseInsensitive` and `ignoredDelimiters` are used, EDM would see **FOO-1234** and **fOo#1234** as  identical and classify the item as a patient record sensitive information type.</span></span>

1. <span data-ttu-id="9cd44-225">Connectコンプライアンス センター PowerShell &の手順を使用して、セキュリティ Connect コンプライアンス センター [PowerShell &にアクセスします](/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="9cd44-225">Connect to the Security & Compliance Center PowerShell using the procedures in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="9cd44-226">データベース スキーマをアップロードするには、次のコマンドレットを 1 つずつ実行します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-226">To upload the database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="9cd44-227">次のように、確認を求められます。</span><span class="sxs-lookup"><span data-stu-id="9cd44-227">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="9cd44-228">確認</span><span class="sxs-lookup"><span data-stu-id="9cd44-228">Confirm</span></span>
      >
      > <span data-ttu-id="9cd44-229">この操作を実行しますか?</span><span class="sxs-lookup"><span data-stu-id="9cd44-229">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="9cd44-230">データストア ' patientrecords ' の新しい EDM スキーマがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="9cd44-230">New EDM Schema for the data store 'patientrecords' will be imported.</span></span>
      >
      > <span data-ttu-id="9cd44-231">\[Y\] Yes \[A\] すべて Yes \[N\] No \[L\] すべて No \[?\] ヘルプ (規定値は "Y"):</span><span class="sxs-lookup"><span data-stu-id="9cd44-231">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
> <span data-ttu-id="9cd44-232">確認なしで変更を行う場合は、手順 5 で次のコマンドレットを代わりに使用します: New-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="9cd44-232">If you want your changes to occur without confirmation, in Step 5, use this cmdlet instead: New-DlpEdmSchema -FileData $edmSchemaXml</span></span>

> [!NOTE]
> <span data-ttu-id="9cd44-233">追加機能を使用して EDMSchema を更新するには、10 から 60 分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="9cd44-233">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="9cd44-234">追加機能を使用する手順を実行する前に、更新プログラムを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cd44-234">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="set-up-a-rule-package"></a><span data-ttu-id="9cd44-235">ルール パッケージを設定する</span><span class="sxs-lookup"><span data-stu-id="9cd44-235">Set up a rule package</span></span>

1. <span data-ttu-id="9cd44-236">次の例のように、XML 形式 (Unicode エンコード) でルール パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-236">Create a rule package in XML format (with Unicode encoding), similar to the following example.</span></span> <span data-ttu-id="9cd44-237">(この例は、コピー、変更、使用することができます。)</span><span class="sxs-lookup"><span data-stu-id="9cd44-237">(You can copy, modify, and use our example.)</span></span>

      <span data-ttu-id="9cd44-238">ルール パッケージを設定する場合は、ファイルまたは .tsv .csvファイルとファイルを正しく **edm.xmlしてください。**</span><span class="sxs-lookup"><span data-stu-id="9cd44-238">When you set up your rule package, make sure to correctly reference your .csv or .tsv file and **edm.xml** file.</span></span> <span data-ttu-id="9cd44-239">この例は、コピー、変更、使用が可能です。</span><span class="sxs-lookup"><span data-stu-id="9cd44-239">You can copy, modify, and use our example.</span></span> <span data-ttu-id="9cd44-240">このサンプル xml では、EDM の機密情報の種類を作成するために、次のフィールドをカスタマイズする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cd44-240">In this sample xml the following fields needs to be customized to create your EDM sensitive type:</span></span>

      - <span data-ttu-id="9cd44-241">**RulePack id & ExactMatch id**: [New-GUID](/powershell/module/microsoft.powershell.utility/new-guid) を使用して GUID を作成します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-241">**RulePack id & ExactMatch id**: Use [New-GUID](/powershell/module/microsoft.powershell.utility/new-guid) to generate a GUID.</span></span>

      - <span data-ttu-id="9cd44-242">**Datastore**: このフィールドは、使用する EDM ルックアップデータストアを指定します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-242">**Datastore**: This field specifies EDM lookup data store to be used.</span></span> <span data-ttu-id="9cd44-243">設定済みの EDM スキーマのデータソース名を指定します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-243">You provide a data source name of a configured EDM Schema.</span></span>

      - <span data-ttu-id="9cd44-244">**idMatch**: このフィールドは、EDM の主要素を示します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-244">**idMatch**: This field points to the primary element for EDM.</span></span>
        - <span data-ttu-id="9cd44-245">検索結果: ルックアップで使用するフィールドを指定します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-245">Matches: Specifies the field to be used in exact lookup.</span></span> <span data-ttu-id="9cd44-246">データストアの EDM スキーマで検索可能なフィールド名を指定します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-246">You provide a searchable field name in EDM Schema for the DataStore.</span></span>
        - <span data-ttu-id="9cd44-247">分類: このフィールドでは、EDM ルックアップをトリガーする、機密情報の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-247">Classification: This field specifies the sensitive type match that triggers EDM lookup.</span></span> <span data-ttu-id="9cd44-248">既存の組み込みまたはカスタムの機密情報の種類の名前または GUID を指定できます。</span><span class="sxs-lookup"><span data-stu-id="9cd44-248">You can provide the Name or GUID of an existing built-in or custom sensitive information type.</span></span> <span data-ttu-id="9cd44-249">指定した機密情報の種類に一致する文字列はすべてハッシュされ、機密情報テーブルのすべてのエントリと比較されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9cd44-249">Be aware that any string that matches the sensitive information type provided will be hashed and compared to every entry in the sensitive information table.</span></span> <span data-ttu-id="9cd44-250">パフォーマンスの問題を回避するために、EDM の分類要素としてカスタムの機密情報の種類を使用する場合は、コンテンツの大部分に一致するもの ("任意の数字" や "任意の 5 文字の単語" など) を使用しないようにします。これには、補助キーワードを追加するか、カスタムの機密情報の種類の定義でのフォーマットを含めます。</span><span class="sxs-lookup"><span data-stu-id="9cd44-250">In order to avoid causing performance issues, if you use a custom sensitive information type as the Classification element in EDM, avoid using one that will match a large percentage of content (such as "any number" or "any five-letter word") by adding supporting keywords or including formatting in the definition of the custom classification sensitive information type.</span></span>

      - <span data-ttu-id="9cd44-251">**Match:** このフィールドは、近接 idMatch で見つかった追加の証拠を示します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-251">**Match:** This field points to additional evidence found in proximity of idMatch.</span></span>
        - <span data-ttu-id="9cd44-252">Matches: データストアの EDM スキーマで検索可能なフィールド名を指定します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-252">Matches: You provide any field name in EDM Schema for DataStore.</span></span>
      - <span data-ttu-id="9cd44-253">**リソース:** このセクションでは、複数のローカルでの機密情報の種類の名前と説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-253">**Resource:** This section specifies the name and description for sensitive type in multiple locales.</span></span>
        - <span data-ttu-id="9cd44-254">idRef: ExactMatch ID の GUID を指定します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-254">idRef: You provide GUID for ExactMatch ID.</span></span>
        - <span data-ttu-id="9cd44-255">名前と説明: 必要に応じてカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="9cd44-255">Name & descriptions: customize as required.</span></span>

      ```xml
      <RulePackage xmlns="http://schemas.microsoft.com/office/2018/edm">
        <RulePack id="fd098e03-1796-41a5-8ab6-198c93c62b11">
          <Version build="0" major="2" minor="0" revision="0" />
          <Publisher id="eb553734-8306-44b4-9ad5-c388ad970528" />
          <Details defaultLangCode="en-us">
            <LocalizedDetails langcode="en-us">
              <PublisherName>IP DLP</PublisherName>
              <Name>Health Care EDM Rulepack</Name>
              <Description>This rule package contains the EDM sensitive type for health care sensitive types.</Description>
            </LocalizedDetails>
          </Details>
        </RulePack>
        <Rules>
          <ExactMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB371" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
            <Pattern confidenceLevel="65">
              <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
            </Pattern>
            <Pattern confidenceLevel="75">
              <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
              <Any minMatches ="3" maxMatches ="6">
                <match matches="PatientID" />
                <match matches="MRN"/>
                <match matches="FirstName"/>
                <match matches="LastName"/>
                <match matches="Phone"/>
                <match matches="DOB"/>
              </Any>
            </Pattern>
          </ExactMatch>
          <LocalizedStrings>
            <Resource idRef="E1CC861E-3FE9-4A58-82DF-4BD259EAB371">
              <Name default="true" langcode="en-us">Patient SSN Exact Match.</Name>
              <Description default="true" langcode="en-us">EDM Sensitive type for detecting Patient SSN.</Description>
            </Resource>
          </LocalizedStrings>
        </Rules>
      </RulePackage>
      ```

2. <span data-ttu-id="9cd44-256">次の PowerShell コマンドレットを 1 つずつ実行して、ルール パッケージをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="9cd44-256">Upload the rule package by running the following PowerShell cmdlets, one at a time:</span></span>

      ```powershell
      $rulepack=Get-Content .\\rulepack.xml -Encoding Byte -ReadCount 0
      New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack
      ```

<span data-ttu-id="9cd44-257">この時点で、EDM ベースの分類がセットアップされています。</span><span class="sxs-lookup"><span data-stu-id="9cd44-257">At this point, you have set up EDM-based classification.</span></span> <span data-ttu-id="9cd44-258">次の手順では、機密データをハッシュして、インデックス用のハッシュをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="9cd44-258">The next step is to hash the sensitive data, and then upload the hashes for indexing.</span></span>

<span data-ttu-id="9cd44-259">前の手順から PatientRecords スキーマが 5 つのフィールドを検索可能として定義していることに注意してください: *PatientID*、*MRN*、*SSN*、*Phone*、*DOB*。</span><span class="sxs-lookup"><span data-stu-id="9cd44-259">Recall from the previous procedure that our PatientRecords schema defines five fields as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span> <span data-ttu-id="9cd44-260">例のルール パッケージにはこれらのフィールドが含まれ、検索可能なフィールドごとに 1 つの *ExactMatch* アイテムを含むデータベース スキーマ ファイル (**edm.xml**) を参照します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-260">Our example rule package includes those fields and references the database schema file (**edm.xml**), with one *ExactMatch* item per searchable field.</span></span> <span data-ttu-id="9cd44-261">次の ExactMatch アイテムをご検討ください。</span><span class="sxs-lookup"><span data-stu-id="9cd44-261">Consider the following ExactMatch item:</span></span>

```xml
<ExactMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB371" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
      <Pattern confidenceLevel="65">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
        <Any minMatches ="3" maxMatches ="100">
          <match matches="PatientID" />
          <match matches="MRN"/>
          <match matches="FirstName"/>
          <match matches="LastName"/>
          <match matches="Phone"/>
          <match matches="DOB"/>
        </Any>
      </Pattern>
    </ExactMatch>
```

<span data-ttu-id="9cd44-262">このサンプルでは、次の点にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="9cd44-262">In this example, note that:</span></span>

- <span data-ttu-id="9cd44-263">dataStore 名は、以前に作成した .csv ファイルを参照します (**dataStore = "PatientRecords"**)。</span><span class="sxs-lookup"><span data-stu-id="9cd44-263">The dataStore name references the .csv file we created earlier: **dataStore = "PatientRecords"**.</span></span>

- <span data-ttu-id="9cd44-264">idMatch 値は、データベース スキーマ ファイルに一覧表示されている検索可能なフィールドを参照しています (**idMatch matches = "SSN"**)。</span><span class="sxs-lookup"><span data-stu-id="9cd44-264">The idMatch value references a searchable field that is listed in the database schema file: **idMatch matches = "SSN"**.</span></span>

- <span data-ttu-id="9cd44-265">分類の値は、既存またはカスタムの機密情報の種類を参照します (**分類 = "米国社会保障番号 (SSN)"**)。</span><span class="sxs-lookup"><span data-stu-id="9cd44-265">The classification value references an existing or custom sensitive information type: **classification = "U.S. Social Security Number (SSN)"**.</span></span> <span data-ttu-id="9cd44-266">(この場合は、既存の機密情報の種類の米国社会保障番号を使用します。)</span><span class="sxs-lookup"><span data-stu-id="9cd44-266">(In this case, we use the existing sensitive information type of U.S. Social Security Number.)</span></span>

> [!NOTE]
> <span data-ttu-id="9cd44-267">追加機能を使用して EDMSchema を更新するには、10 から 60 分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="9cd44-267">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="9cd44-268">追加機能を使用する手順を実行する前に、更新プログラムを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cd44-268">The update must complete before you execute steps that use the additions.</span></span>

<span data-ttu-id="9cd44-269">EDM 機密情報タイプを使用してルール パッケージをインポートし、機密データテーブルをインポートした後、コンプライアンス センターの EDM ウィザードのテスト機能を使用して、新しく作成したタイプを **テスト** することができます。</span><span class="sxs-lookup"><span data-stu-id="9cd44-269">After you have imported your rule package with your EDM sensitive info type and have imported your sensitive data table, you can test your newly created type by using the **Test** function in the EDM wizard in the compliance center.</span></span> <span data-ttu-id="9cd44-270">この機能の使用方法については、「[完全一致スキーマと機密情報の種類ウィザードを使用する](sit-edm-wizard.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cd44-270">See [Use the Exact Data Match Schema and Sensitive Information Type Wizard](sit-edm-wizard.md) for instructions on using this functionality.</span></span>

#### <a name="editing-the-schema-for-edm-based-classification"></a><span data-ttu-id="9cd44-271">EDM ベースの分類のスキーマを編集する</span><span class="sxs-lookup"><span data-stu-id="9cd44-271">Editing the schema for EDM-based classification</span></span>

<span data-ttu-id="9cd44-272">EDM ベースの分類に使用するフィールドの変更など、**edm.xml** ファイルを変更する場合は、次の手順に従います:</span><span class="sxs-lookup"><span data-stu-id="9cd44-272">If you want to make changes to your **edm.xml** file, such as changing which fields are used for EDM-based classification, follow these steps:</span></span>

> [!TIP]
> <span data-ttu-id="9cd44-273">EDM スキーマとデータ ファイルを変更して、**構成可能な一致** を利用できます。</span><span class="sxs-lookup"><span data-stu-id="9cd44-273">You can change your EDM schema and data file to take advantage of **configurable match**.</span></span> <span data-ttu-id="9cd44-274">構成されている場合、EDM はアイテムを評価するときに、大文字と小文字の違いと一部の区切り文字を無視します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-274">When configured, EDM will ignore case differences and some delimiters when it evaluates an item.</span></span> <span data-ttu-id="9cd44-275">これにより、xml スキーマと機密データ ファイルの定義が容易になります。</span><span class="sxs-lookup"><span data-stu-id="9cd44-275">This makes defining your xml schema and your sensitive data files easier.</span></span> <span data-ttu-id="9cd44-276">詳細については、「[構成可能な一致を使用するために完全一致スキーマを変更する](sit-modify-edm-schema-configurable-match.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cd44-276">To learn more see, [Modify Exact Data Match schema to use configurable match](sit-modify-edm-schema-configurable-match.md).</span></span>

1. <span data-ttu-id="9cd44-277">**edm.xml** ファイルを編集します (これは、この記事の「[スキーマを定義する](#define-the-schema-for-your-database-of-sensitive-information)」セクションで説明したファイルです)。</span><span class="sxs-lookup"><span data-stu-id="9cd44-277">Edit your **edm.xml** file (this is the file discussed in the [Define the schema](#define-the-schema-for-your-database-of-sensitive-information) section of this article).</span></span>

2. <span data-ttu-id="9cd44-278">[セキュリティ/コンプライアンス センター PowerShellに接続する](/powershell/exchange/connect-to-scc-powershell)の手順を使用して、セキュリティ/コンプライアンス センターに接続します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-278">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

3. <span data-ttu-id="9cd44-279">データベース スキーマを更新するには、次のコマンドレットを 1 つずつ実行します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-279">To update your database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="9cd44-280">次のように、確認を求められます。</span><span class="sxs-lookup"><span data-stu-id="9cd44-280">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="9cd44-281">確認</span><span class="sxs-lookup"><span data-stu-id="9cd44-281">Confirm</span></span>
      >
      > <span data-ttu-id="9cd44-282">この操作を実行しますか?</span><span class="sxs-lookup"><span data-stu-id="9cd44-282">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="9cd44-283">データストア ' patientrecords ' の EDM スキーマが更新されます。</span><span class="sxs-lookup"><span data-stu-id="9cd44-283">EDM Schema for the data store 'patientrecords' will be updated.</span></span>
      >
      > <span data-ttu-id="9cd44-284">\[Y\] Yes \[A\] すべて Yes \[N\] No \[L\] すべて No \[?\] ヘルプ (規定値は "Y"):</span><span class="sxs-lookup"><span data-stu-id="9cd44-284">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      > <span data-ttu-id="9cd44-285">確認なしで変更を行う場合は、手順 3 で次のコマンドレットを代わりに使用します: Set-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="9cd44-285">If you want your changes to occur without confirmation, in Step 3, use this cmdlet instead: Set-DlpEdmSchema -FileData $edmSchemaXml</span></span>

      > [!NOTE]
      > <span data-ttu-id="9cd44-286">追加機能を使用して EDMSchema を更新するには、10 から 60 分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="9cd44-286">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="9cd44-287">追加機能を使用する手順を実行する前に、更新プログラムを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cd44-287">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="removing-the-schema-for-edm-based-classification"></a><span data-ttu-id="9cd44-288">EDM ベースの分類のスキーマを削除する</span><span class="sxs-lookup"><span data-stu-id="9cd44-288">Removing the schema for EDM-based classification</span></span>

<span data-ttu-id="9cd44-289">(必要に応じて) EDM ベースの分類に使用しているスキーマを削除するには、次の手順に従います:</span><span class="sxs-lookup"><span data-stu-id="9cd44-289">(As needed) If you want to remove the schema you're using for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="9cd44-290">[セキュリティ/コンプライアンス センター PowerShellに接続する](/powershell/exchange/connect-to-scc-powershell)の手順を使用して、セキュリティ/コンプライアンス センターに接続します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-290">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="9cd44-291">次の PowerShell コマンドレットを実行して、"patient records" のデータ ストア名を削除するものに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="9cd44-291">Run the following PowerShell cmdlets, substituting the data store name of "patient records" with the one you want to remove:</span></span>

      ```powershell
      Remove-DlpEdmSchema -Identity patientrecords
      ```

      <span data-ttu-id="9cd44-292">次のように確認を求められます。</span><span class="sxs-lookup"><span data-stu-id="9cd44-292">You will be prompted to confirm:</span></span>

      > <span data-ttu-id="9cd44-293">確認</span><span class="sxs-lookup"><span data-stu-id="9cd44-293">Confirm</span></span>
      >
      > <span data-ttu-id="9cd44-294">この操作を実行しますか?</span><span class="sxs-lookup"><span data-stu-id="9cd44-294">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="9cd44-295">データストア ' patientrecords ' の EDM スキーマが削除されます。</span><span class="sxs-lookup"><span data-stu-id="9cd44-295">EDM Schema for the data store 'patientrecords' will be removed.</span></span>
      >
      > <span data-ttu-id="9cd44-296">\[Y\] Yes \[A\] すべて Yes \[N\] No \[L\] すべて No \[?\] ヘルプ (規定値は "Y"):</span><span class="sxs-lookup"><span data-stu-id="9cd44-296">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      >  <span data-ttu-id="9cd44-297">確認なしで変更を行う場合は、手順 2 で次のコマンドレットを代わりに使用します: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span><span class="sxs-lookup"><span data-stu-id="9cd44-297">If you want your changes to occur without confirmation, in Step 2, use this cmdlet instead: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span></span>

### <a name="part-2-hash-and-upload-the-sensitive-data"></a><span data-ttu-id="9cd44-298">パート 2: 機密データをハッシュ化してアップロードする</span><span class="sxs-lookup"><span data-stu-id="9cd44-298">Part 2: Hash and upload the sensitive data</span></span>

<span data-ttu-id="9cd44-299">このフェーズでは、カスタムのセキュリティ グループとユーザー アカウントをセットアップし、EDM アップロード エージェント ツールをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="9cd44-299">In this phase, you set up a custom security group and user account, and set up the EDM Upload Agent tool.</span></span> <span data-ttu-id="9cd44-300">次に、このツールを使用して機密データにソルト値を付与してハッシュ化し、データをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="9cd44-300">Then, you use the tool to hash with salt value the sensitive data, and upload it.</span></span>

<span data-ttu-id="9cd44-301">ハッシュ化とアップロードは 1 台のコンピューターで行うこともできますし、ハッシュ化のステップとアップロードのステップを分離してセキュリティを高めることもできます。</span><span class="sxs-lookup"><span data-stu-id="9cd44-301">The hashing and uploading can be done using one computer or you can separate the hashing step from the upload step for greater security.</span></span>

<span data-ttu-id="9cd44-302">1 台のコンピューターでハッシュ化とアップロードを行う場合は、ご利用の Microsoft 365 テナントに直接接続可能なコンピューターから行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cd44-302">If you want to hash and upload from one computer, you need to do it from a computer that can directly connect to your Microsoft 365 tenant.</span></span> <span data-ttu-id="9cd44-303">そのためには、ハッシュ化のためにクリア テキストの機密データ ファイルがそのコンピューター上にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cd44-303">This requires that your clear text sensitive data files are on that computer for hashing.</span></span>

<span data-ttu-id="9cd44-p129">クリア テキストの機密データ ファイルを公開したくない場合は、安全な場所にあるコンピューターでハッシュ化し、ハッシュ ファイルとソルト ファイルをご利用の Microsoft 365 テナントに直接接続可能なコンピューターにコピーしてアップロードすることができます。このシナリオでは、両方のコンピューターにEDMUploadAgentが必要になります。</span><span class="sxs-lookup"><span data-stu-id="9cd44-p129">If you do not want to expose your clear text sensitive data file, you can hash it on a computer in a secure location and then copy the hash file and the salt file to a computer that can directly connect to your Microsoft 365 tenant for upload. In this scenario, you will need the EDMUploadAgent on both computers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9cd44-306">完全一致スキーマと機密情報の種類ウィザードを使用してスキーマ ファイルおよびパターン ファイルの作成する場合、この手順のスキーマをダウンロードする ***必要があります***。</span><span class="sxs-lookup"><span data-stu-id="9cd44-306">If you used the Exact Data Match schema and sensitive information type wizard to create your schema and pattern files, you ***must*** download the schema for this procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="9cd44-307">組織がテナント レベルで[](customer-key-overview.md)顧客キーをMicrosoft 365場合、完全なデータ一致は暗号化機能を自動的に利用します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-307">If your organization has set up [Customer Key for Microsoft 365 at the tenant level](customer-key-overview.md), Exact data match will make use of its encryption functionality automatically.</span></span> <span data-ttu-id="9cd44-308">この機能を利用できるのは、商用クラウド内の E5 ライセンスが割り当てられたテナントのみです。</span><span class="sxs-lookup"><span data-stu-id="9cd44-308">This is available only to E5 licensed tenants in the Commercial cloud.</span></span>

#### <a name="prerequisites"></a><span data-ttu-id="9cd44-309">前提条件</span><span class="sxs-lookup"><span data-stu-id="9cd44-309">Prerequisites</span></span>

- <span data-ttu-id="9cd44-310">**EDM\_DataUploaders** セキュリティ グループに追加される Microsoft 365 の職場または学校のアカウント</span><span class="sxs-lookup"><span data-stu-id="9cd44-310">a work or school account for Microsoft 365  that will be added to the **EDM\_DataUploaders** security group</span></span>
- <span data-ttu-id="9cd44-311">EDMUploadAgent を実行するための .NET バージョン 4.6.2 が搭載された Windows 10 または Windows Server 2016 マシン</span><span class="sxs-lookup"><span data-stu-id="9cd44-311">a Windows 10 or Windows Server 2016 machine with .NET version 4.6.2 for running the EDMUploadAgent</span></span>
- <span data-ttu-id="9cd44-312">以下のためのアップロード マシン上のディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="9cd44-312">a directory on your upload machine for the:</span></span>
  - <span data-ttu-id="9cd44-313">EDMUploadAgent</span><span class="sxs-lookup"><span data-stu-id="9cd44-313">EDMUploadAgent</span></span>
  - <span data-ttu-id="9cd44-314">この例では、.csv .tsv 形式の機密アイテム **PatientRecords.csv** ファイル</span><span class="sxs-lookup"><span data-stu-id="9cd44-314">your sensitive item file in .csv or .tsv format, **PatientRecords.csv** in our examples</span></span>
  - <span data-ttu-id="9cd44-315">出力ハッシュファイルとソルト ファイル</span><span class="sxs-lookup"><span data-stu-id="9cd44-315">the output hash and salt files</span></span>
  - <span data-ttu-id="9cd44-316">**edm.xml** ファイルのデータストア名 (このサンプルでは `PatientRecords`)</span><span class="sxs-lookup"><span data-stu-id="9cd44-316">the datastore name from the **edm.xml** file, for this example its `PatientRecords`</span></span>
- <span data-ttu-id="9cd44-317">[完全一致スキーマと機密情報の種類ウィザード](sit-edm-wizard.md)を使用している場合は、それをダウンロードする ***必要が あります***</span><span class="sxs-lookup"><span data-stu-id="9cd44-317">If you used the [Exact Data Match schema and sensitive information type wizard](sit-edm-wizard.md) you ***must*** download it</span></span>

#### <a name="set-up-the-security-group-and-user-account"></a><span data-ttu-id="9cd44-318">セキュリティ グループとユーザー アカウントをセットアップする</span><span class="sxs-lookup"><span data-stu-id="9cd44-318">Set up the security group and user account</span></span>

1. <span data-ttu-id="9cd44-319">全体管理者として、[サブスクリプションの適切なリンク](#portal-links-for-your-subscription) を使用して管理センターにアクセスし、**EDM\_DataUploaders** という [セキュリティ グループを作成します](/office365/admin/email/create-edit-or-delete-a-security-group)。</span><span class="sxs-lookup"><span data-stu-id="9cd44-319">As a global administrator, go to the admin center using the appropriate [link for your subscription](#portal-links-for-your-subscription) and [create a security group](/office365/admin/email/create-edit-or-delete-a-security-group) called **EDM\_DataUploaders**.</span></span>

2. <span data-ttu-id="9cd44-320">**EDM\_DataUploaders** セキュリティ グループに、1 人以上のユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-320">Add one or more users to the **EDM\_DataUploaders** security group.</span></span> <span data-ttu-id="9cd44-321">(これらのユーザーは機密情報のデータベースを管理します)。</span><span class="sxs-lookup"><span data-stu-id="9cd44-321">(These users will manage the database of sensitive information.)</span></span>

#### <a name="hash-and-upload-from-one-computer"></a><span data-ttu-id="9cd44-322">1 台のコンピューターからハッシュ化とアップロードを行う</span><span class="sxs-lookup"><span data-stu-id="9cd44-322">Hash and upload from one computer</span></span>

<span data-ttu-id="9cd44-323">このコンピュータは、ご利用の Microsoft 365 テナントに直接アクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cd44-323">This computer must have direct access to your Microsoft 365 tenant.</span></span>

> [!NOTE]
>
> <span data-ttu-id="9cd44-324">この手順を開始する前に、自分が **EDM\_DataUploaders** セキュリティ グループのメンバーであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-324">Before you begin this procedure, make sure that you are a member of the **EDM\_DataUploaders** security group.</span></span>
>
> <span data-ttu-id="9cd44-325">必要に応じて、次を実行してアップロードする前に、.csvファイルまたは .tsv ファイルに対して検証を実行できます。</span><span class="sxs-lookup"><span data-stu-id="9cd44-325">Optionally, you can run a validation against your .csv or .tsv file before uploading by running:</span></span>
>
> `EdmUploadAgent.exe /ValidateData /DataFile [data file] /Schema [schema file]`
>
> <span data-ttu-id="9cd44-326">すべての EdmUploadAgent.exe > サポートされているパラメータの詳細情報については</span><span class="sxs-lookup"><span data-stu-id="9cd44-326">For more information on all the EdmUploadAgent.exe >supported parameters run</span></span>
>
> `EdmUploadAgent.exe /?`

#### <a name="links-to-edm-upload-agent-by-subscription-type"></a><span data-ttu-id="9cd44-327">サブスクリプションの種類別の EDM アップロードエージェントへのリンク</span><span class="sxs-lookup"><span data-stu-id="9cd44-327">Links to EDM upload agent by subscription type</span></span>

- <span data-ttu-id="9cd44-328">[商用 + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - ほとんどの商用のお客様はこれを使用する必要があります</span><span class="sxs-lookup"><span data-stu-id="9cd44-328">[Commercial + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - most commercial customers should use this</span></span>
- <span data-ttu-id="9cd44-329">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - これは特に高セキュリティの政府機関向けクラウド加入者を対象にしています</span><span class="sxs-lookup"><span data-stu-id="9cd44-329">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - This is specifically for high security government cloud subscribers</span></span>
- <span data-ttu-id="9cd44-330">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - これは特に米国国防総省のクラウド顧客対象にしています</span><span class="sxs-lookup"><span data-stu-id="9cd44-330">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - this is specifically for United States Department of Defense cloud customers</span></span>

1. <span data-ttu-id="9cd44-331">EDMUploadAgent の作業ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-331">Create a working directory for the EDMUploadAgent.</span></span> <span data-ttu-id="9cd44-332">たとえば、**C:\EDM\Data** です。</span><span class="sxs-lookup"><span data-stu-id="9cd44-332">For example, **C:\EDM\Data**.</span></span> <span data-ttu-id="9cd44-333">そこに **PatientRecords.csv** ファイルを配置します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-333">Place the **PatientRecords.csv** file there.</span></span>

2. <span data-ttu-id="9cd44-334">手順 1 で作成したディレクトリに、サブスクリプションに適した [EDM アップロードエージェント](#links-to-edm-upload-agent-by-subscription-type) をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="9cd44-334">Download and install the appropriate [EDM Upload Agent](#links-to-edm-upload-agent-by-subscription-type) for your subscription into the directory you created in step 1.</span></span>

   > [!NOTE]
   > <span data-ttu-id="9cd44-335">上記リンクにある EDMUploadAgent は、ハッシュ化されたデータに自動的にソルト値を追加するように更新されています。</span><span class="sxs-lookup"><span data-stu-id="9cd44-335">The EDMUploadAgent at the above links has been updated to automatically add a salt value to the hashed data.</span></span> <span data-ttu-id="9cd44-336">または、独自のソルト値を提供することもできます。</span><span class="sxs-lookup"><span data-stu-id="9cd44-336">Alternately, you can provide your own salt value.</span></span> <span data-ttu-id="9cd44-337">このバージョンを使用すると、以前のバージョンの EDMUploadAgent は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="9cd44-337">Once you have used this version, you will not be able to use the previous version of the EDMUploadAgent.</span></span>
   >
   > <span data-ttu-id="9cd44-338">EDMUploadAgent を使用して特定のデータ ストアにデータをアップロードできるのは、1 日に 2 回だけです。</span><span class="sxs-lookup"><span data-stu-id="9cd44-338">You can upload data with the EDMUploadAgent to any given data store only twice per day.</span></span>

   > [!TIP]
   > <span data-ttu-id="9cd44-p134">サポートされているコマンド パラメーターから一覧を取得するには、エージェントの引数を実行します。たとえば、'EdmUploadAgent.exe' などです。</span><span class="sxs-lookup"><span data-stu-id="9cd44-p134">To a get a list out of the supported command parameters, run the agent no arguments. For example 'EdmUploadAgent.exe'.</span></span>

3. <span data-ttu-id="9cd44-341">EDM アップロード エージェントを承認し、管理者としてコマンド プロンプト ウィンドウを開き、**C:\EDM\Data** ディレクトリに切り替え、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-341">Authorize the EDM Upload Agent, open  Command Prompt window (as an administrator), switch to the **C:\EDM\Data** directory and then run the following command:</span></span>

   `EdmUploadAgent.exe /Authorize`

4. <span data-ttu-id="9cd44-342">EDM_DataUploaders セキュリティ グループに追加された、Microsoft 365 の職場または学校のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="9cd44-342">Sign in with your work or school account for Microsoft 365 that was added to the EDM_DataUploaders security group.</span></span> <span data-ttu-id="9cd44-343">ユーザー アカウントからご利用のテナント情報を抽出し、接続を行います。</span><span class="sxs-lookup"><span data-stu-id="9cd44-343">Your tenant information is extracted from the user account to make the connection.</span></span>

   <span data-ttu-id="9cd44-344">オプション: 完全一致スキーマと機密情報の種類ウィザードを使ってスキーマ ファイルおよびパターン ファイルを作成した場合は、コマンド プロンプト ウィンドウで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-344">OPTIONAL: If you used the Exact Data Match schema and sensitive information type wizard to create your schema and pattern files, run the following command in a Command Prompt window:</span></span>

   ```dos
   EdmUploadAgent.exe /SaveSchema /DataStoreName <schema name> /OutputDir <path to output folder>
   ```

5. <span data-ttu-id="9cd44-345">機密データをハッシュ化してアップロートするには、コマンド プロンプト ウィンドウで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-345">To hash and upload the sensitive data, run the following command in Command Prompt window:</span></span>

   ```dos
   EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Schema [Schema file] /ColumnSeparator ["{Tab}"|"|"]
   ```

   <span data-ttu-id="9cd44-346">例: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml**</span><span class="sxs-lookup"><span data-stu-id="9cd44-346">Example: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml**</span></span>

   <span data-ttu-id="9cd44-347">機密データ ファイルの既定の形式はコンマ区切りの値です。</span><span class="sxs-lookup"><span data-stu-id="9cd44-347">The default format for the sensitive data file is comma-separated values.</span></span> <span data-ttu-id="9cd44-348">タブ区切りファイルを指定するには、/ColumnSeparator パラメーターで "{Tab}" オプションを指定するか、"|" オプションを指定してパイプ区切りファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-348">You can specify a tab-separated file by indicating the "{Tab}" option with the /ColumnSeparator parameter, or you can specify a pipe-separated file by indicating the "|" option.</span></span>
   <span data-ttu-id="9cd44-349">このコマンドは、ランダムに生成されたソルト値をハッシュに自動的に追加し、セキュリティを強化します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-349">This command will automatically add a randomly generated salt value to the hash for greater security.</span></span> <span data-ttu-id="9cd44-350">オプションで独自のソルト値を使用する場合は、コマンドに **/Salt<saltvalue>** を追加します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-350">Optionally, if you want to use your own salt value, add the **/Salt <saltvalue>** to the command.</span></span> <span data-ttu-id="9cd44-351">この値は 64 文字の長さにする必要があり、a-z 文字と 0-9 文字のみを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="9cd44-351">This value must be 64 characters in length and can only contain the a-z characters and 0-9 characters.</span></span>

6. <span data-ttu-id="9cd44-352">次のコマンドを実行してアップロードの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-352">Check the upload status by running this command:</span></span>

   ```dos
   EdmUploadAgent.exe /GetSession /DataStoreName \<DataStoreName\>
   ```

   <span data-ttu-id="9cd44-353">例: **EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords**</span><span class="sxs-lookup"><span data-stu-id="9cd44-353">Example: **EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords**</span></span>

   <span data-ttu-id="9cd44-354">**ProcessingInProgress** にある状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-354">Look for the status to be in **ProcessingInProgress**.</span></span> <span data-ttu-id="9cd44-355">状態が **完了** に変わるまで、数分ごとにご確認ください。</span><span class="sxs-lookup"><span data-stu-id="9cd44-355">Check again every few minutes until the status changes to **Completed**.</span></span> <span data-ttu-id="9cd44-356">状態が完了になれば、EDM データはいつでも使用することができます。</span><span class="sxs-lookup"><span data-stu-id="9cd44-356">Once the status is completed, your EDM data is ready for use.</span></span>

#### <a name="separate-hash-and-upload"></a><span data-ttu-id="9cd44-357">ハッシュ化とアップロードを分離する</span><span class="sxs-lookup"><span data-stu-id="9cd44-357">Separate Hash and upload</span></span>

<span data-ttu-id="9cd44-358">安全な環境にあるコンピューター上でハッシュ化を実行します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-358">Perform the hash on a computer in a secure environment.</span></span>

<span data-ttu-id="9cd44-359">オプション: 完全一致スキーマと機密情報の種類ウィザードを使ってスキーマ ファイルおよびパターン ファイルを作成した場合は、コマンド プロンプト ウィンドウで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-359">OPTIONAL: If you used the Exact Data Match schema and sensitive information type wizard to create your schema and pattern files, run the following command in a Command Prompt window:</span></span>

```dos
EdmUploadAgent.exe /SaveSchema /DataStoreName <schema name> /OutputDir <path to output folder>
````

1. <span data-ttu-id="9cd44-360">コマンド プロンプト ウィンドウで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-360">Run the following command in Command Prompt windows:</span></span>

   ```dos
   EdmUploadAgent.exe /CreateHash /DataFile [data file] /HashLocation [hash file location] /Schema [Schema file]
   ```

   <span data-ttu-id="9cd44-361">例:</span><span class="sxs-lookup"><span data-stu-id="9cd44-361">For example:</span></span>

   ```dos
   EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml
   ```

   <span data-ttu-id="9cd44-362">**/Salt<saltvalue>** オプションを指定しなかった場合、このコマンドは次の拡張子を持つハッシュ化されたファイルとソルト ファイルを出力します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-362">This will output a hashed file and a salt file with these extensions if you didn't specify the **/Salt <saltvalue>** option:</span></span>

   - <span data-ttu-id="9cd44-363">.EdmHash</span><span class="sxs-lookup"><span data-stu-id="9cd44-363">.EdmHash</span></span>
   - <span data-ttu-id="9cd44-364">.EdmSalt</span><span class="sxs-lookup"><span data-stu-id="9cd44-364">.EdmSalt</span></span>

2. <span data-ttu-id="9cd44-365">これらのファイルを安全な方法でコンピューターにコピーして、機密アイテム .csv または .tsv ファイル (PatientRecords) をテナントにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="9cd44-365">Copy these files in a secure fashion to the computer you will use to upload your sensitive items .csv or .tsv file (PatientRecords) to your tenant.</span></span>

   <span data-ttu-id="9cd44-366">ハッシュされたデータをアップロードするには、Windows コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-366">To upload the hashed data, run the following command in Windows Command Prompt:</span></span>

   ```dos
   EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\>
   ```

   <span data-ttu-id="9cd44-367">例:</span><span class="sxs-lookup"><span data-stu-id="9cd44-367">For example:</span></span>

   ```dos
   EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**
   ```

   <span data-ttu-id="9cd44-368">機密データがアップロードされたことを確認するには、コマンド プロンプト ウィンドウで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-368">To verify that your sensitive data has been uploaded, run the following command in Command Prompt window:</span></span>

   ```dos
   EdmUploadAgent.exe /GetDataStore
   ```

   <span data-ttu-id="9cd44-369">データ ストアのリストと、それらが最後に更新された日時が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9cd44-369">You'll see a list of data stores and when they were last updated.</span></span>

   <span data-ttu-id="9cd44-370">特定のストアへのデータのアップロードをすべて表示する場合は、Windows コマンドプロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-370">If you want to see all the data uploads to a particular store, run the following command in a Windows command prompt:</span></span>

   ```dos
   EdmUploadAgent.exe /GetSession /DataStoreName <DataStoreName>
   ```

   <span data-ttu-id="9cd44-371">[機密情報データベースを更新する](#refreshing-your-sensitive-information-database) ためのプロセスとスケジュールのセットアップを進めます。</span><span class="sxs-lookup"><span data-stu-id="9cd44-371">Proceed to set up your process and schedule for [Refreshing your sensitive information database](#refreshing-your-sensitive-information-database).</span></span>

<span data-ttu-id="9cd44-372">この時点で、Microsoft クラウド サービスで EDM ベースの分類を使用する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="9cd44-372">At this point, you are ready to use EDM-based classification with your Microsoft cloud services.</span></span> <span data-ttu-id="9cd44-373">たとえば、[EDM ベースの分類を使用して DLP ポリシーを設定](#to-create-a-dlp-policy-with-edm)できます。</span><span class="sxs-lookup"><span data-stu-id="9cd44-373">For example, you can [set up a DLP policy using EDM-based classification](#to-create-a-dlp-policy-with-edm).</span></span>

#### <a name="refreshing-your-sensitive-information-database"></a><span data-ttu-id="9cd44-374">機密情報データベースを更新する</span><span class="sxs-lookup"><span data-stu-id="9cd44-374">Refreshing your sensitive information database</span></span>

<span data-ttu-id="9cd44-375">機密情報データベースは毎日更新できます。また、EDM アップロード ツールを使用して機密データのインデックスを再作成し、インデックス付きデータを再アップロードできます。</span><span class="sxs-lookup"><span data-stu-id="9cd44-375">You can refresh your sensitive information database daily, and the EDM Upload Tool can reindex the sensitive data and then reupload the indexed data.</span></span>

1. <span data-ttu-id="9cd44-376">機密情報のデータベースを更新するためのプロセスと頻度 (毎日または毎週) を決定します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-376">Determine your process and frequency (daily or weekly) for refreshing the database of sensitive information.</span></span>

2. <span data-ttu-id="9cd44-377">機密データをアプリ (Microsoft Excel など) に再エクスポートし、ファイルを .csv .tsv 形式で保存します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-377">Re-export the sensitive data to an app, such as Microsoft Excel, and save the file in .csv or .tsv format.</span></span> <span data-ttu-id="9cd44-378">「[機密データをハッシュしアップロードする](#part-2-hash-and-upload-the-sensitive-data)」で説明した手順の実行時に使用したものと同じファイル名と場所を使用してください。</span><span class="sxs-lookup"><span data-stu-id="9cd44-378">Keep the same file name and location you used when you followed the steps described in [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data).</span></span>

      > [!NOTE]
      > <span data-ttu-id="9cd44-379">.csv または .tsv ファイルの構造 (フィールド名) に変更がない場合は、データを更新するときにデータベース スキーマ ファイルを変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9cd44-379">If there are no changes to the structure (field names) of the .csv or .tsv file, you won't need to make any changes to your database schema file when you refresh the data.</span></span> <span data-ttu-id="9cd44-380">ただし、変更が必要な場合は、必要に応じてデータベース スキーマとルール パッケージを編集してください。</span><span class="sxs-lookup"><span data-stu-id="9cd44-380">But if you must make changes, make sure to edit the database schema and your rule package accordingly.</span></span>

3. <span data-ttu-id="9cd44-381">「[機密データをハッシュしアップロードする](#part-2-hash-and-upload-the-sensitive-data)」の手順の、手順 2 と 3 を自動化するには、[タスク スケジューラ](/windows/desktop/TaskSchd/task-scheduler-start-page) を使用します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-381">Use [Task Scheduler](/windows/desktop/TaskSchd/task-scheduler-start-page) to automate steps 2 and 3 in the [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data) procedure.</span></span> <span data-ttu-id="9cd44-382">タスクのスケジュールを設定するにはいくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="9cd44-382">You can schedule tasks using several methods:</span></span>

   |<span data-ttu-id="9cd44-383">メソッド</span><span class="sxs-lookup"><span data-stu-id="9cd44-383">Method</span></span>|<span data-ttu-id="9cd44-384">操作</span><span class="sxs-lookup"><span data-stu-id="9cd44-384">What to do</span></span>|
   |---|---|
   |<span data-ttu-id="9cd44-385">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9cd44-385">Windows PowerShell</span></span>|<span data-ttu-id="9cd44-386">[ScheduledTasks](/powershell/module/scheduledtasks/) のドキュメントと、この記事の [PowerShell スクリプトの例](#example-powershell-script-for-task-scheduler)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cd44-386">See the [ScheduledTasks](/powershell/module/scheduledtasks/) documentation and the [example PowerShell script](#example-powershell-script-for-task-scheduler) in this article</span></span>|
   |<span data-ttu-id="9cd44-387">タスク スケジューラ API</span><span class="sxs-lookup"><span data-stu-id="9cd44-387">Task Scheduler API</span></span>|<span data-ttu-id="9cd44-388">[Task Scheduler](/windows/desktop/TaskSchd/using-the-task-scheduler) のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cd44-388">See the [Task Scheduler](/windows/desktop/TaskSchd/using-the-task-scheduler) documentation</span></span>|
   |<span data-ttu-id="9cd44-389">Windows のユーザー インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9cd44-389">Windows user interface</span></span>|<span data-ttu-id="9cd44-390">Windows の場合、**[スタート]** をクリックし、「タスク スケジューラ」と入力します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-390">In Windows, click **Start**, and type Task Scheduler.</span></span> <span data-ttu-id="9cd44-391">次に、結果のリストで **[タスク スケジューラ]** を右クリックし、**[管理者として実行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-391">Then, in the list of results, right-click **Task Scheduler**, and choose **Run as administrator**.</span></span>|

#### <a name="example-powershell-script-for-task-scheduler"></a><span data-ttu-id="9cd44-392">タスク スケジューラの PowerShell スクリプトの例</span><span class="sxs-lookup"><span data-stu-id="9cd44-392">Example PowerShell script for Task Scheduler</span></span>

<span data-ttu-id="9cd44-393">このセクションには、データをハッシュしたり、ハッシュされたデータをアップロードするタスクのスケジュールに使用できる PowerShell スクリプトの例が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9cd44-393">This section includes an example PowerShell script you can use to schedule your tasks for hashing data and uploading the hashed data:</span></span>

##### <a name="to-schedule-hashing-and-upload-in-a-combined-step"></a><span data-ttu-id="9cd44-394">ハッシュのスケジュールを設定して、結合されたステップでアップロードするには</span><span class="sxs-lookup"><span data-stu-id="9cd44-394">To schedule hashing and upload in a combined step</span></span>

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$schemaext = '.xml'
\# Assuming file name is same as data store name and file is in .csv format
$dataFile = "$fileLocation\\$dataStoreName$csvext"
\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
\# Assuming Schema file name is same as data store name
$schemaFile = "$fileLocation\\$dataStoreName$schemaext"
$uploadDataArgs = '/UploadData /DataStoreName ' + $dataStoreName + ' /DataFile ' + $dataFile + ' /HashLocation' + $hashLocation + ' /Schema ' + $schemaFile
\# Set up actions associated with the task
$actions = @()
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $uploadDataArgs -WorkingDirectory $edminstallpath
\# Set up trigger for the task
$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 2am
\# Set up task settings
$principal = New-ScheduledTaskPrincipal -UserId $user -LogonType S4U -RunLevel Highest
$settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -StartWhenAvailable -WakeToRun
\# Create the scheduled task
$scheduledTask = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings
\# Get credentials to run the task
$creds = Get-Credential -UserName $user -Message "Enter credentials to run the task"
$password=\[Runtime.InteropServices.Marshal\]::PtrToStringAuto(\[Runtime.InteropServices.Marshal\]::SecureStringToBSTR($creds.Password))
\# Register the scheduled task
$taskName = 'EDMUpload\_' + $dataStoreName
Register-ScheduledTask -TaskName $taskName -InputObject $scheduledTask -User $user -Password $password
```

#### <a name="to-schedule-hashing-and-upload-as-separate-steps"></a><span data-ttu-id="9cd44-395">ハッシュのスケジュールを設定して、結合されたステップでアップロードするには</span><span class="sxs-lookup"><span data-stu-id="9cd44-395">To schedule hashing and upload as separate steps</span></span>

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$edmext = '.EdmHash'
$schemaext = '.xml'
\# Assuming file name is same as data store name and file is in .csv format
$dataFile = "$fileLocation\\$dataStoreName$csvext"
$hashFile = "$fileLocation\\$dataStoreName$edmext"
\# Assuming Schema file name is same as data store name
$schemaFile = "$fileLocation\\$dataStoreName$schemaext "

\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$createHashArgs = '/CreateHash' + ' /DataFile ' + $dataFile + ' /HashLocation ' + $hashLocation + ' /Schema ' + $schemaFile
$uploadHashArgs = '/UploadHash /DataStoreName ' + $dataStoreName + ' /HashFile ' + $hashFile
\# Set up actions associated with the task
$actions = @()
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $createHashArgs -WorkingDirectory $edminstallpath
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $uploadHashArgs -WorkingDirectory $edminstallpath
\# Set up trigger for the task
$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 2am
\# Set up task settings
$principal = New-ScheduledTaskPrincipal -UserId $user -LogonType S4U -RunLevel Highest
$settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -StartWhenAvailable -WakeToRun
\# Create the scheduled task
$scheduledTask = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings
\# Get credentials to run the task
$creds = Get-Credential -UserName $user -Message "Enter credentials to run the task"
$password=\[Runtime.InteropServices.Marshal\]::PtrToStringAuto(\[Runtime.InteropServices.Marshal\]::SecureStringToBSTR($creds.Password))
\# Register the scheduled task
$taskName = 'EDMUpload\_' + $dataStoreName
Register-ScheduledTask -TaskName $taskName -InputObject $scheduledTask -User $user -Password $password
```

### <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a><span data-ttu-id="9cd44-396">パート 3: Microsoft クラウド サービスで EDM ベースの分類を使用する</span><span class="sxs-lookup"><span data-stu-id="9cd44-396">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>

<span data-ttu-id="9cd44-397">これらの場所が、EDM の機密情報の種類をサポートしています:</span><span class="sxs-lookup"><span data-stu-id="9cd44-397">These locations are support EDM sensitive information types:</span></span>

- <span data-ttu-id="9cd44-398">DLP for Exchange Online (メール)</span><span class="sxs-lookup"><span data-stu-id="9cd44-398">DLP for Exchange Online (email)</span></span>
- <span data-ttu-id="9cd44-399">OneDrive for Business (ファイル)</span><span class="sxs-lookup"><span data-stu-id="9cd44-399">OneDrive for Business (files)</span></span>
- <span data-ttu-id="9cd44-400">Microsoft Teams (会話)</span><span class="sxs-lookup"><span data-stu-id="9cd44-400">Microsoft Teams (conversations)</span></span>
- <span data-ttu-id="9cd44-401">DLP for SharePoint (ファイル)</span><span class="sxs-lookup"><span data-stu-id="9cd44-401">DLP for SharePoint (files)</span></span>
- <span data-ttu-id="9cd44-402">Microsoft Cloud App Security DLP ポリシー</span><span class="sxs-lookup"><span data-stu-id="9cd44-402">Microsoft Cloud App Security DLP policies</span></span>
- <span data-ttu-id="9cd44-403">サーバー側の自動ラベル付けポリシー - 商用クラウドのお客様および政府機関向けクラウドのお客様向け</span><span class="sxs-lookup"><span data-stu-id="9cd44-403">Server-side auto-labeling policies - available for commercial cloud customers and government cloud customers</span></span>

#### <a name="to-create-a-dlp-policy-with-edm"></a><span data-ttu-id="9cd44-404">EDM を使用して DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="9cd44-404">To create a DLP policy with EDM</span></span>

1. <span data-ttu-id="9cd44-405">[サブスクリプションに適切なリンク](#portal-links-for-your-subscription)を使用して、セキュリティ/コンプライアンス センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-405">Go to the Security & Compliance Center using the appropriate [link for your subscription](#portal-links-for-your-subscription).</span></span>

2. <span data-ttu-id="9cd44-406">**[データ損失防止]** \> **[ポリシー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-406">Choose **Data loss prevention** \> **Policy**.</span></span>

3. <span data-ttu-id="9cd44-407">**[ポリシーの作成]** \> **[カスタム]** \> **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-407">Choose **Create a policy** \> **Custom** \> **Next**.</span></span>

4. <span data-ttu-id="9cd44-408">**[ポリシーの名前を設定]** タブで名前と説明を指定し、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-408">On the **Name your policy** tab, specify a name and description, and then choose **Next**.</span></span>

5. <span data-ttu-id="9cd44-409">**[場所の選択]** タブで **[特定の場所を選択]** を選択し、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-409">On the **Choose locations** tab, select **Let me choose specific locations**, and then choose **Next**.</span></span>

6. <span data-ttu-id="9cd44-410">**[状態]** 列で、**Exchange メール、OneDrive アカウント、Teams チャット、チャネル メッセージ** を選択し、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-410">In the **Status** column, select **Exchange email, OneDrive accounts, Teams chat and channel message**, and then choose **Next**.</span></span>

7. <span data-ttu-id="9cd44-411">**[ポリシーの設定]** タブで **[詳細な設定を使用]** を選択し、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-411">On the **Policy settings** tab, choose **Use advanced settings**, and then choose **Next**.</span></span>

8. <span data-ttu-id="9cd44-412">**[+ 新しいルール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-412">Choose **+ New rule**.</span></span>

9. <span data-ttu-id="9cd44-413">**[名前]** セクションで、ルールの名前と説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-413">In the **Name** section, specify a name and description for the rule.</span></span>

10. <span data-ttu-id="9cd44-414">**[条件]** セクションの **[+ 条件の追加]** リストで、**[コンテンツに機密情報の種類を含む]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-414">In the **Conditions** section, in the **+ Add a condition** list, choose **Content contains sensitive type**.</span></span>

      ![機密情報の種類を含むコンテンツ](../media/edm-dlp-newrule-conditions.png)

11. <span data-ttu-id="9cd44-416">ルール パッケージのセットアップ時に作成した機密情報の種類を検索し、**[+ 追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-416">Search for the sensitive information type you created when you set up your rule package, and then choose **+ Add**.</span></span>
    <span data-ttu-id="9cd44-417">次に、**[完了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-417">Then choose **Done**.</span></span>

12. <span data-ttu-id="9cd44-418">ルールのオプション (**[ユーザー通知]**、**[ユーザーによる上書き]**、**[インシデント レポート]** など) の選択を終了し、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-418">Finish selecting options for your rule, such as **User notifications**, **User overrides**, **Incident reports**, and so on, and then choose **Save**.</span></span>

13. <span data-ttu-id="9cd44-419">**[ポリシーの設定]** タブでルールを確認し、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-419">On the **Policy settings** tab, review your rules, and then choose **Next**.</span></span>

14. <span data-ttu-id="9cd44-420">ポリシーをすぐに有効にするか、テストするか、無効にするかを指定します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-420">Specify whether to turn on the policy right away, test it out, or keep it turned off.</span></span> <span data-ttu-id="9cd44-421">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-421">Then choose **Next**.</span></span>

15. <span data-ttu-id="9cd44-422">**[設定を確認]** タブで、ポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-422">On the **Review your settings** tab, review your policy.</span></span> <span data-ttu-id="9cd44-423">必要な変更を行います。</span><span class="sxs-lookup"><span data-stu-id="9cd44-423">Make any needed changes.</span></span> <span data-ttu-id="9cd44-424">準備ができたら **[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9cd44-424">When you're ready, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="9cd44-425">新しい DLP ポリシーがデータ センターを通過するまでに、約 1 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="9cd44-425">Allow approximately one hour for your new DLP policy to work its way through your data center.</span></span>

## <a name="related-articles"></a><span data-ttu-id="9cd44-426">関連記事</span><span class="sxs-lookup"><span data-stu-id="9cd44-426">Related articles</span></span>

- [<span data-ttu-id="9cd44-427">機密情報の種類のエンティティ定義</span><span class="sxs-lookup"><span data-stu-id="9cd44-427">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="9cd44-428">機密情報の種類に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="9cd44-428">Learn about sensitive information types</span></span>](sensitive-information-type-learn-about.md)
- [<span data-ttu-id="9cd44-429">データ損失防止について</span><span class="sxs-lookup"><span data-stu-id="9cd44-429">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="9cd44-430">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="9cd44-430">Microsoft Cloud App Security</span></span>](/cloud-app-security)
- [<span data-ttu-id="9cd44-431">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="9cd44-431">New-DlpEdmSchema</span></span>](/powershell/module/exchange/new-dlpedmschema)
- [<span data-ttu-id="9cd44-432">構成可能な一致を使用するために完全一致スキーマを変更する</span><span class="sxs-lookup"><span data-stu-id="9cd44-432">Modify Exact Data Match schema to use configurable match</span></span>](sit-modify-edm-schema-configurable-match.md)
