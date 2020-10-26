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
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 完全なデータ一致に基づく分類で、カスタムの機密情報の種類を作成する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 229eb733af85ea5f450969c6d70709cfadcb8f06
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681775"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification"></a><span data-ttu-id="67cb2-103">Exact Data Match に基づく分類で、カスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="67cb2-103">Create custom sensitive information types with Exact Data Match based classification</span></span>

<span data-ttu-id="67cb2-104">[カスタムの機密情報の種類](custom-sensitive-info-types.md) は機密性の高いアイテムの識別に利用され、これにより、不注意による共有や不適切な共有を防止することができます。</span><span class="sxs-lookup"><span data-stu-id="67cb2-104">[Custom sensitive information types](custom-sensitive-info-types.md) are used to help identify sensitive items so that you can prevent them from being inadvertently or inappropriately shared.</span></span> <span data-ttu-id="67cb2-105">以下に基づいて、カスタムの機密情報の種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-105">You define a custom sensitive information type based on:</span></span>

- <span data-ttu-id="67cb2-106">パターン</span><span class="sxs-lookup"><span data-stu-id="67cb2-106">patterns</span></span>
- <span data-ttu-id="67cb2-107">*従業員*、*バッジ*、*ID* などのキーワード証拠</span><span class="sxs-lookup"><span data-stu-id="67cb2-107">keyword evidence such as *employee*, *badge*, or *ID*</span></span>
- <span data-ttu-id="67cb2-108">特定のパターンの証拠に対する文字の近接性</span><span class="sxs-lookup"><span data-stu-id="67cb2-108">character proximity to evidence in a particular pattern</span></span>
- <span data-ttu-id="67cb2-109">信頼度レベル</span><span class="sxs-lookup"><span data-stu-id="67cb2-109">confidence levels</span></span>

 <span data-ttu-id="67cb2-110">このようなカスタムの機密情報の種類は、多くの組織のビジネス ニーズを満たします。</span><span class="sxs-lookup"><span data-stu-id="67cb2-110">Such custom sensitive information types meet business needs for many organizations.</span></span>

<span data-ttu-id="67cb2-111">しかし、汎用的なパターンに基づいて一致を検出するカスタムの機密情報の種類ではなく、正確なデータ値を使用するカスタムの機密情報の種類が必要な場合はどうでしょう。</span><span class="sxs-lookup"><span data-stu-id="67cb2-111">But what if you wanted a custom sensitive information type that uses exact data values, instead of one that found matches based on generic patterns?</span></span> <span data-ttu-id="67cb2-112">Exact Data Match (EDM) ベースの分類では、次の目的で設計されたカスタムの機密情報の種類を作成できます。</span><span class="sxs-lookup"><span data-stu-id="67cb2-112">With Exact Data Match (EDM)-based classification, you can create a custom sensitive information type that is designed to:</span></span>

- <span data-ttu-id="67cb2-113">動的で更新可能なものにする</span><span class="sxs-lookup"><span data-stu-id="67cb2-113">be dynamic and refreshable</span></span>
- <span data-ttu-id="67cb2-114">拡張性の高いものにする</span><span class="sxs-lookup"><span data-stu-id="67cb2-114">be more scalable</span></span>
- <span data-ttu-id="67cb2-115">結果的に誤検知の数を減らす</span><span class="sxs-lookup"><span data-stu-id="67cb2-115">result in fewer false-positives</span></span>
- <span data-ttu-id="67cb2-116">構造化された機密データを操作する</span><span class="sxs-lookup"><span data-stu-id="67cb2-116">work with structured sensitive data</span></span>
- <span data-ttu-id="67cb2-117">機密情報をより安全に処理する</span><span class="sxs-lookup"><span data-stu-id="67cb2-117">handle sensitive information more securely</span></span>
- <span data-ttu-id="67cb2-118">さまざまな Microsoft クラウド サービスで使用する</span><span class="sxs-lookup"><span data-stu-id="67cb2-118">be used with several Microsoft cloud services</span></span>

![EDM ベースの分類](../media/EDMClassification.png)

<span data-ttu-id="67cb2-120">EDM ベースの分類を使用すると、機密情報のデータベース内の正確な値を参照する、カスタムの機密情報の種類を作成できます。</span><span class="sxs-lookup"><span data-stu-id="67cb2-120">EDM-based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="67cb2-121">データベースは毎日更新できます。また、最大 1 億行のデータを格納できます。</span><span class="sxs-lookup"><span data-stu-id="67cb2-121">The database can be refreshed daily, and contain up to 100 million rows of data.</span></span> <span data-ttu-id="67cb2-122">そのため、従業員、患者、または顧客の出入りに合わせて記録が変更されても、カスタムの機密情報の種類は最新の状態が維持されます。</span><span class="sxs-lookup"><span data-stu-id="67cb2-122">So as employees, patients, or clients come and go, and records change, your custom sensitive information types remain current and applicable.</span></span> <span data-ttu-id="67cb2-123">また、EDM ベースの分類は、[データ損失防止ポリシー](data-loss-prevention-policies.md) (DLP) や [Microsoft Cloud App Security ファイル ポリシー](https://docs.microsoft.com/cloud-app-security/data-protection-policies) などのポリシーと共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="67cb2-123">And, you can use EDM-based classification with policies, such as [data loss prevention policies](data-loss-prevention-policies.md) (DLP) or [Microsoft Cloud App Security file policies](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span></span>

> [!NOTE]
> <span data-ttu-id="67cb2-124">Microsoft 365 の情報保護は、次のような場合に2バイト文字セットの言語をpreviewでサポートしています。</span><span class="sxs-lookup"><span data-stu-id="67cb2-124">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="67cb2-125">中国語 (簡体字)</span><span class="sxs-lookup"><span data-stu-id="67cb2-125">Chinese (simplified)</span></span>
> - <span data-ttu-id="67cb2-126">中国語 (繁体字)</span><span class="sxs-lookup"><span data-stu-id="67cb2-126">Chinese (traditional)</span></span>
> - <span data-ttu-id="67cb2-127">韓国語</span><span class="sxs-lookup"><span data-stu-id="67cb2-127">Korean</span></span>
> - <span data-ttu-id="67cb2-128">日本語</span><span class="sxs-lookup"><span data-stu-id="67cb2-128">Japanese</span></span>

><span data-ttu-id="67cb2-129">このサポートは、機密情報の種類で使用できます。</span><span class="sxs-lookup"><span data-stu-id="67cb2-129">This support is available for sensitive information types.</span></span> <span data-ttu-id="67cb2-130">詳細については、「[2バイト文字セットのリリースノート (preview) についての情報保護サポート](mip-dbcs-relnotes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67cb2-130">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="67cb2-131">必要なライセンスとアクセス許可</span><span class="sxs-lookup"><span data-stu-id="67cb2-131">Required licenses and permissions</span></span>

<span data-ttu-id="67cb2-132">この記事で説明されているタスクを実行するには、全体管理者、コンプライアンス管理者、または Exchange Online 管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="67cb2-132">You must be a global admin, compliance administrator, or Exchange Online administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="67cb2-133">DLP アクセス許可の詳細については、「[アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67cb2-133">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="67cb2-134">これらのサブスクリプションには、EDM ベースの分類が含まれています</span><span class="sxs-lookup"><span data-stu-id="67cb2-134">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="67cb2-135">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="67cb2-135">Office 365 E5</span></span>
- <span data-ttu-id="67cb2-136">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="67cb2-136">Microsoft 365 E5</span></span>
- <span data-ttu-id="67cb2-137">Microsoft 365 E5 Compliance </span><span class="sxs-lookup"><span data-stu-id="67cb2-137">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="67cb2-138">Microsoft E5/A5 Information Protection and Governance</span><span class="sxs-lookup"><span data-stu-id="67cb2-138">Microsoft E5/A5 Information Protection and Governance</span></span>

## <a name="portal-links-for-your-subscription"></a><span data-ttu-id="67cb2-139">サブスクリプションのポータルリンク</span><span class="sxs-lookup"><span data-stu-id="67cb2-139">Portal links for your subscription</span></span>


|<span data-ttu-id="67cb2-140">ポータル</span><span class="sxs-lookup"><span data-stu-id="67cb2-140">Portal</span></span>  |<span data-ttu-id="67cb2-141">世界中の GCC</span><span class="sxs-lookup"><span data-stu-id="67cb2-141">World Wide/GCC</span></span>  |<span data-ttu-id="67cb2-142">GCC-High</span><span class="sxs-lookup"><span data-stu-id="67cb2-142">GCC-High</span></span>  |<span data-ttu-id="67cb2-143">DOD</span><span class="sxs-lookup"><span data-stu-id="67cb2-143">DOD</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="67cb2-144">Office SCC</span><span class="sxs-lookup"><span data-stu-id="67cb2-144">Office SCC</span></span>     |  <span data-ttu-id="67cb2-145">protection.office.com</span><span class="sxs-lookup"><span data-stu-id="67cb2-145">protection.office.com</span></span>       |<span data-ttu-id="67cb2-146">scc.office365.us</span><span class="sxs-lookup"><span data-stu-id="67cb2-146">scc.office365.us</span></span>         |<span data-ttu-id="67cb2-147">scc.protection.apps.mil</span><span class="sxs-lookup"><span data-stu-id="67cb2-147">scc.protection.apps.mil</span></span> |
|<span data-ttu-id="67cb2-148">Microsoft 365 セキュリティ センター</span><span class="sxs-lookup"><span data-stu-id="67cb2-148">Microsoft 365 Security center</span></span>     |<span data-ttu-id="67cb2-149">security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="67cb2-149">security.microsoft.com</span></span>         |<span data-ttu-id="67cb2-150">security.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="67cb2-150">security.microsoft.us</span></span>         |<span data-ttu-id="67cb2-151">security.apps.mil</span><span class="sxs-lookup"><span data-stu-id="67cb2-151">security.apps.mil</span></span>|
|<span data-ttu-id="67cb2-152">Microsoft 365 コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="67cb2-152">Microsoft 365 Compliance center</span></span>     |<span data-ttu-id="67cb2-153">compliance.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="67cb2-153">compliance.microsoft.com</span></span>         |<span data-ttu-id="67cb2-154">compliance.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="67cb2-154">compliance.microsoft.us</span></span>         |<span data-ttu-id="67cb2-155">compliance.apps.mil</span><span class="sxs-lookup"><span data-stu-id="67cb2-155">compliance.apps.mil</span></span>|


## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="67cb2-156">ワークフローの概要</span><span class="sxs-lookup"><span data-stu-id="67cb2-156">The work flow at a glance</span></span>

|<span data-ttu-id="67cb2-157">フェーズ</span><span class="sxs-lookup"><span data-stu-id="67cb2-157">Phase</span></span>  |<span data-ttu-id="67cb2-158">前提条件</span><span class="sxs-lookup"><span data-stu-id="67cb2-158">What's needed</span></span>  |
|---------|---------|
|[<span data-ttu-id="67cb2-159">パート 1: EDM ベースの分類をセットアップする</span><span class="sxs-lookup"><span data-stu-id="67cb2-159">Part 1: Set up EDM-based classification</span></span>](#part-1-set-up-edm-based-classification)<br/><br/><span data-ttu-id="67cb2-160">(適宜)</span><span class="sxs-lookup"><span data-stu-id="67cb2-160">(As needed)</span></span><br/><span data-ttu-id="67cb2-161">- [データベーススキーマを編集する](#editing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="67cb2-161">- [Edit the database schema](#editing-the-schema-for-edm-based-classification)</span></span> <br/><span data-ttu-id="67cb2-162">- [スキーマを削除する](#removing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="67cb2-162">- [Remove the schema](#removing-the-schema-for-edm-based-classification)</span></span> |<span data-ttu-id="67cb2-163">- 機密データへの読み取りアクセス</span><span class="sxs-lookup"><span data-stu-id="67cb2-163">- Read access to the sensitive data</span></span><br/><span data-ttu-id="67cb2-164">- XML 形式のデータベース スキーマ (例を提供)</span><span class="sxs-lookup"><span data-stu-id="67cb2-164">- Database schema in XML format (example provided)</span></span><br/><span data-ttu-id="67cb2-165">- XML 形式のルール パッケージ (例を提供)</span><span class="sxs-lookup"><span data-stu-id="67cb2-165">- Rule package in XML format (example provided)</span></span><br/><span data-ttu-id="67cb2-166">- セキュリティ/コンプライアンス センターへの管理者権限 (PowerShell を使用)</span><span class="sxs-lookup"><span data-stu-id="67cb2-166">- Admin permissions to the Security & Compliance Center (using PowerShell)</span></span> |
|[<span data-ttu-id="67cb2-167">パート 2: 機密データをハッシュしアップロードする</span><span class="sxs-lookup"><span data-stu-id="67cb2-167">Part 2: Hash and upload the sensitive data</span></span>](#part-2-hash-and-upload-the-sensitive-data)<br/><br/><span data-ttu-id="67cb2-168">(適宜)</span><span class="sxs-lookup"><span data-stu-id="67cb2-168">(As needed)</span></span><br/>[<span data-ttu-id="67cb2-169">データを更新する</span><span class="sxs-lookup"><span data-stu-id="67cb2-169">Refresh the data</span></span>](#refreshing-your-sensitive-information-database) |<span data-ttu-id="67cb2-170">- カスタムのセキュリティ グループとユーザー アカウント</span><span class="sxs-lookup"><span data-stu-id="67cb2-170">- Custom security group and user account</span></span><br/><span data-ttu-id="67cb2-171">- EDM アップロード エージェントを使用するコンピューターへのローカル管理者アクセス</span><span class="sxs-lookup"><span data-stu-id="67cb2-171">- Local admin access to machine with EDM Upload Agent</span></span><br/><span data-ttu-id="67cb2-172">- 機密データへの読み取りアクセス</span><span class="sxs-lookup"><span data-stu-id="67cb2-172">- Read access to the sensitive data</span></span><br/><span data-ttu-id="67cb2-173">- データ更新のプロセスとスケジュール</span><span class="sxs-lookup"><span data-stu-id="67cb2-173">- Process and schedule for refreshing the data</span></span>|
|[<span data-ttu-id="67cb2-174">パート 3: Microsoft クラウド サービスで EDM ベースの分類を使用する</span><span class="sxs-lookup"><span data-stu-id="67cb2-174">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services) |<span data-ttu-id="67cb2-175">- DLP を使用する Microsoft 365 サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="67cb2-175">- Microsoft 365 subscription with DLP</span></span><br/><span data-ttu-id="67cb2-176">- 有効化された EDM ベースの分類機能</span><span class="sxs-lookup"><span data-stu-id="67cb2-176">- EDM-based classification feature enabled</span></span> |

### <a name="part-1-set-up-edm-based-classification"></a><span data-ttu-id="67cb2-177">パート 1: EDM ベースの分類をセットアップする</span><span class="sxs-lookup"><span data-stu-id="67cb2-177">Part 1: Set up EDM-based classification</span></span>

<span data-ttu-id="67cb2-178">EDM ベースの分類の設定と構成には、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="67cb2-178">Setting up and configuring EDM-based classification involves:</span></span>

1. [<span data-ttu-id="67cb2-179">.csv 形式での機密データの保存 </span><span class="sxs-lookup"><span data-stu-id="67cb2-179">Saving sensitive data in .csv format</span></span>](#save-sensitive-data-in-csv-format)
2. [<span data-ttu-id="67cb2-180">機密情報データベース スキーマを定義する</span><span class="sxs-lookup"><span data-stu-id="67cb2-180">Define your sensitive information database schema</span></span>](#define-the-schema-for-your-database-of-sensitive-information)
3. [<span data-ttu-id="67cb2-181">ルール パッケージを作成する</span><span class="sxs-lookup"><span data-stu-id="67cb2-181">Create a rule package</span></span>](#set-up-a-rule-package)


#### <a name="save-sensitive-data-in-csv-format"></a><span data-ttu-id="67cb2-182">.csv 形式で機密データを保存する</span><span class="sxs-lookup"><span data-stu-id="67cb2-182">Save sensitive data in .csv format</span></span>

1. <span data-ttu-id="67cb2-183">使用する機密情報を特定します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-183">Identify the sensitive information you want to use.</span></span> <span data-ttu-id="67cb2-184">データを Microsoft Excel などのアプリにエクスポートし、ファイルを .csv 形式で保存します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-184">Export the data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="67cb2-185">データ ファイルには、次のデータを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="67cb2-185">The data file can include a maximum of:</span></span>
      - <span data-ttu-id="67cb2-186">最大 1 億行の機密データ</span><span class="sxs-lookup"><span data-stu-id="67cb2-186">Up to 100 million rows of sensitive data</span></span>
      - <span data-ttu-id="67cb2-187">データ ソースごとに最大 32 列 (フィールド)</span><span class="sxs-lookup"><span data-stu-id="67cb2-187">Up to 32 columns (fields) per data source</span></span>
      - <span data-ttu-id="67cb2-188">検索可能としてマークされた列 (フィールド) を最大 5 列</span><span class="sxs-lookup"><span data-stu-id="67cb2-188">Up to 5 columns (fields) marked as searchable</span></span>

2. <span data-ttu-id="67cb2-189">EDM ベースの分類に使用されるフィールドの名前が 1 行目に含まれるように、.csv ファイル内の機密データを構成します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-189">Structure the sensitive data in the .csv file such that the first row includes the names of the fields used for EDM-based classification.</span></span> <span data-ttu-id="67cb2-190">.csv ファイルには、"ssn"、"birthdate"、"firstname"、"lastname" のフィールド名がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="67cb2-190">In your .csv file, you might have field names, such as "ssn", "birthdate", "firstname", "lastname".</span></span> <span data-ttu-id="67cb2-191">列見出しの名前にスペースやアンダースコアを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="67cb2-191">The column header names can't include spaces or underscores.</span></span> <span data-ttu-id="67cb2-192">たとえば、この記事で使用するサンプルの .csv ファイルは *PatientRecords.csv* と呼ばれており、その列には *PatientID*、*MRN*、*LastName*、*FirstName*、*SSN* などが含まれています。</span><span class="sxs-lookup"><span data-stu-id="67cb2-192">For example, the sample .csv file that we use in this article is named *PatientRecords.csv*, and its columns include *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN*, and more.</span></span>

#### <a name="define-the-schema-for-your-database-of-sensitive-information"></a><span data-ttu-id="67cb2-193">機密情報のデータベースのスキーマを定義する</span><span class="sxs-lookup"><span data-stu-id="67cb2-193">Define the schema for your database of sensitive information</span></span>

3. <span data-ttu-id="67cb2-194">機密情報のデータベースのスキーマを XML 形式で定義します (次の例と同様)。</span><span class="sxs-lookup"><span data-stu-id="67cb2-194">Define the schema for the database of sensitive information in XML format (similar to our example below).</span></span> <span data-ttu-id="67cb2-195">このスキーマ ファイルの名前を **edm.xml** にして、データベースの各列に対して構文を使用する行があるように構成します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-195">Name this schema file **edm.xml**, and configure it such that for each column in the database, there is a line that uses the syntax:</span></span> 

      <span data-ttu-id="67cb2-196">`\<Field name="" searchable=""/\>`</span><span class="sxs-lookup"><span data-stu-id="67cb2-196">`\<Field name="" searchable=""/\>`.</span></span>

      - <span data-ttu-id="67cb2-197">*Field name* の値に列名を使用します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-197">Use column names for *Field name* values.</span></span>
      - <span data-ttu-id="67cb2-198">*searchable="true"* を使用して、最大 5 つのフィールドで検索可能にします。</span><span class="sxs-lookup"><span data-stu-id="67cb2-198">Use *searchable="true"* for the fields that you want to be searchable up to a maximum of 5 fields.</span></span> <span data-ttu-id="67cb2-199">少なくとも 1 つのフィールドは検索可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="67cb2-199">At least one field must be searchable.</span></span>

      <span data-ttu-id="67cb2-200">たとえば、次の XML ファイルは患者レコードのデータベースのスキーマを定義します。検索可能として指定された 5 つのフィールドは、*PatientID*、*MRN*、*SSN*、*Phone*、*DOB* です。</span><span class="sxs-lookup"><span data-stu-id="67cb2-200">As an example, the following XML file defines the schema for a patient records database, with five fields specified as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span>

      <span data-ttu-id="67cb2-201">(この例は、コピー、変更、使用することができます。)</span><span class="sxs-lookup"><span data-stu-id="67cb2-201">(You can copy, modify, and use our example.)</span></span>

      ```xml
      <EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
            <DataStore name="PatientRecords" description="Schema for patient records" version="1">
                  <Field name="PatientID" searchable="true" />
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

4. <span data-ttu-id="67cb2-202">[セキュリティ/コンプライアンス センター PowerShellに接続する](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)の手順を使用して、セキュリティ/コンプライアンス センターに接続します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-202">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

5. <span data-ttu-id="67cb2-203">データベース スキーマをアップロードするには、次のコマンドレットを 1 つずつ実行します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-203">To upload the database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="67cb2-204">次のように、確認を求められます。</span><span class="sxs-lookup"><span data-stu-id="67cb2-204">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="67cb2-205">確認</span><span class="sxs-lookup"><span data-stu-id="67cb2-205">Confirm</span></span>
      >
      > <span data-ttu-id="67cb2-206">この操作を実行しますか?</span><span class="sxs-lookup"><span data-stu-id="67cb2-206">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="67cb2-207">データストア ' patientrecords ' の新しい EDM スキーマがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="67cb2-207">New EDM Schema for the data store 'patientrecords' will be imported.</span></span>
      >
      > <span data-ttu-id="67cb2-208">\[Y\] Yes \[A\] すべて Yes \[N\] No \[L\] すべて No \[?\] ヘルプ (規定値は "Y"):</span><span class="sxs-lookup"><span data-stu-id="67cb2-208">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
> <span data-ttu-id="67cb2-209">確認なしで変更を行う場合は、手順 5 で次のコマンドレットを代わりに使用します: New-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="67cb2-209">If you want your changes to occur without confirmation, in Step 5, use this cmdlet instead: New-DlpEdmSchema -FileData $edmSchemaXml</span></span>

> [!NOTE]
> <span data-ttu-id="67cb2-210">追加機能を使用して EDMSchema を更新するには、10 から 60 分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="67cb2-210">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="67cb2-211">追加機能を使用する手順を実行する前に、更新プログラムを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67cb2-211">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="set-up-a-rule-package"></a><span data-ttu-id="67cb2-212">ルール パッケージを設定する</span><span class="sxs-lookup"><span data-stu-id="67cb2-212">Set up a rule package</span></span>

1. <span data-ttu-id="67cb2-213">次の例のように、XML 形式 (Unicode エンコード) でルール パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-213">Create a rule package in XML format (with Unicode encoding), similar to the following example.</span></span> <span data-ttu-id="67cb2-214">(この例は、コピー、変更、使用することができます。)</span><span class="sxs-lookup"><span data-stu-id="67cb2-214">(You can copy, modify, and use our example.)</span></span>

      <span data-ttu-id="67cb2-215">ルール パッケージをセットアップするときに、.csv ファイルと **edm .xml** ファイルを正しく参照してください。</span><span class="sxs-lookup"><span data-stu-id="67cb2-215">When you set up your rule package, make sure to correctly reference your .csv file and **edm.xml** file.</span></span> <span data-ttu-id="67cb2-216">この例は、コピー、変更、使用が可能です。</span><span class="sxs-lookup"><span data-stu-id="67cb2-216">You can copy, modify, and use our example.</span></span> <span data-ttu-id="67cb2-217">このサンプル xml では、EDM の機密情報の種類を作成するために、次のフィールドをカスタマイズする必要があります。</span><span class="sxs-lookup"><span data-stu-id="67cb2-217">In this sample xml the following fields needs to be customized to create your EDM sensitive type:</span></span>

      - <span data-ttu-id="67cb2-218">**RulePack id & ExactMatch id**: [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) を使用して GUID を作成します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-218">**RulePack id & ExactMatch id**: Use [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) to generate a GUID.</span></span>

      - <span data-ttu-id="67cb2-219">**Datastore**: このフィールドは、使用する EDM ルックアップデータストアを指定します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-219">**Datastore**: This field specifies EDM lookup data store to be used.</span></span> <span data-ttu-id="67cb2-220">設定済みの EDM スキーマのデータソース名を指定します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-220">You provide a data source name of a configured EDM Schema.</span></span>

      - <span data-ttu-id="67cb2-221">**idMatch**: このフィールドは、EDM の主要素を示します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-221">**idMatch**: This field points to the primary element for EDM.</span></span>
        - <span data-ttu-id="67cb2-222">検索結果: ルックアップで使用するフィールドを指定します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-222">Matches: Specifies the field to be used in exact lookup.</span></span> <span data-ttu-id="67cb2-223">データストアの EDM スキーマで検索可能なフィールド名を指定します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-223">You provide a searchable field name in EDM Schema for the DataStore.</span></span>
        - <span data-ttu-id="67cb2-224">分類: このフィールドでは、EDM ルックアップをトリガーする、機密情報の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-224">Classification: This field specifies the sensitive type match that triggers EDM lookup.</span></span> <span data-ttu-id="67cb2-225">既存の組み込みまたはカスタム分類の名前または GUID を指定できます。</span><span class="sxs-lookup"><span data-stu-id="67cb2-225">You can provide Name or GUID of an existing built-in or custom classification.</span></span>

      - <span data-ttu-id="67cb2-226">**Match:** このフィールドは、近接 idMatch で見つかった追加の証拠を示します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-226">**Match:** This field points to additional evidence found in proximity of idMatch.</span></span>
        - <span data-ttu-id="67cb2-227">Matches: データストアの EDM スキーマで検索可能なフィールド名を指定します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-227">Matches: You provide any field name in EDM Schema for DataStore.</span></span>
      - <span data-ttu-id="67cb2-228">**リソース:** このセクションでは、複数のローカルでの機密情報の種類の名前と説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-228">**Resource:** This section specifies the name and description for sensitive type in multiple locales.</span></span>
        - <span data-ttu-id="67cb2-229">idRef: ExactMatch ID の GUID を指定します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-229">idRef: You provide GUID for ExactMatch ID.</span></span>
        - <span data-ttu-id="67cb2-230">名前と説明: 必要に応じてカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="67cb2-230">Name & descriptions: customize as required.</span></span>

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

1. <span data-ttu-id="67cb2-231">次の PowerShell コマンドレットを 1 つずつ実行して、ルール パッケージをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="67cb2-231">Upload the rule package by running the following PowerShell cmdlets, one at a time:</span></span>

      ```powershell
      $rulepack=Get-Content .\\rulepack.xml -Encoding Byte -ReadCount 0
      New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack
      ```

<span data-ttu-id="67cb2-232">この時点で、EDM ベースの分類がセットアップされています。</span><span class="sxs-lookup"><span data-stu-id="67cb2-232">At this point, you have set up EDM-based classification.</span></span> <span data-ttu-id="67cb2-233">次の手順では、機密データをハッシュして、インデックス用のハッシュをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="67cb2-233">The next step is to hash the sensitive data, and then upload the hashes for indexing.</span></span>

<span data-ttu-id="67cb2-234">前の手順から PatientRecords スキーマが 5 つのフィールドを検索可能として定義していることに注意してください: *PatientID*、*MRN*、*SSN*、*Phone*、*DOB*。</span><span class="sxs-lookup"><span data-stu-id="67cb2-234">Recall from the previous procedure that our PatientRecords schema defines five fields as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span> <span data-ttu-id="67cb2-235">例のルール パッケージにはこれらのフィールドが含まれ、検索可能なフィールドごとに 1 つの *ExactMatch* アイテムを含むデータベース スキーマ ファイル (**edm.xml**) を参照します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-235">Our example rule package includes those fields and references the database schema file (**edm.xml**), with one *ExactMatch* item per searchable field.</span></span> <span data-ttu-id="67cb2-236">次の ExactMatch アイテムをご検討ください。</span><span class="sxs-lookup"><span data-stu-id="67cb2-236">Consider the following ExactMatch item:</span></span>

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

<span data-ttu-id="67cb2-237">このサンプルでは、次の点にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="67cb2-237">In this example, note that:</span></span>

- <span data-ttu-id="67cb2-238">dataStore 名は、以前に作成した .csv ファイルを参照します (**dataStore = "PatientRecords"**)。</span><span class="sxs-lookup"><span data-stu-id="67cb2-238">The dataStore name references the .csv file we created earlier: **dataStore = "PatientRecords"**.</span></span>

- <span data-ttu-id="67cb2-239">idMatch 値は、データベース スキーマ ファイルに一覧表示されている検索可能なフィールドを参照しています (**idMatch matches = "SSN"**)。</span><span class="sxs-lookup"><span data-stu-id="67cb2-239">The idMatch value references a searchable field that is listed in the database schema file: **idMatch matches = "SSN"**.</span></span>

- <span data-ttu-id="67cb2-240">分類の値は、既存またはカスタムの機密情報の種類を参照します (**分類 = "米国社会保障番号 (SSN)"**)。</span><span class="sxs-lookup"><span data-stu-id="67cb2-240">The classification value references an existing or custom sensitive information type: **classification = "U.S. Social Security Number (SSN)"**.</span></span> <span data-ttu-id="67cb2-241">(この場合は、既存の機密情報の種類の米国社会保障番号を使用します。)</span><span class="sxs-lookup"><span data-stu-id="67cb2-241">(In this case, we use the existing sensitive information type of U.S. Social Security Number.)</span></span>

> [!NOTE]
> <span data-ttu-id="67cb2-242">追加機能を使用して EDMSchema を更新するには、10 から 60 分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="67cb2-242">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="67cb2-243">追加機能を使用する手順を実行する前に、更新プログラムを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67cb2-243">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="editing-the-schema-for-edm-based-classification"></a><span data-ttu-id="67cb2-244">EDM ベースの分類のスキーマを編集する</span><span class="sxs-lookup"><span data-stu-id="67cb2-244">Editing the schema for EDM-based classification</span></span>

<span data-ttu-id="67cb2-245">EDM ベースの分類に使用するフィールドの変更など、**edm.xml** ファイルを変更する場合は、次の手順に従います:</span><span class="sxs-lookup"><span data-stu-id="67cb2-245">If you want to make changes to your **edm.xml** file, such as changing which fields are used for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="67cb2-246">**edm.xml** ファイルを編集します (これは、この記事の「[スキーマを定義する](#define-the-schema-for-your-database-of-sensitive-information)」セクションで説明したファイルです)。</span><span class="sxs-lookup"><span data-stu-id="67cb2-246">Edit your **edm.xml** file (this is the file discussed in the [Define the schema](#define-the-schema-for-your-database-of-sensitive-information) section of this article).</span></span>

2. <span data-ttu-id="67cb2-247">[セキュリティ/コンプライアンス センター PowerShellに接続する](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)の手順を使用して、セキュリティ/コンプライアンス センターに接続します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-247">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

3. <span data-ttu-id="67cb2-248">データベース スキーマを更新するには、次のコマンドレットを 1 つずつ実行します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-248">To update your database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="67cb2-249">次のように、確認を求められます。</span><span class="sxs-lookup"><span data-stu-id="67cb2-249">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="67cb2-250">確認</span><span class="sxs-lookup"><span data-stu-id="67cb2-250">Confirm</span></span>
      >
      > <span data-ttu-id="67cb2-251">この操作を実行しますか?</span><span class="sxs-lookup"><span data-stu-id="67cb2-251">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="67cb2-252">データストア ' patientrecords ' の EDM スキーマが更新されます。</span><span class="sxs-lookup"><span data-stu-id="67cb2-252">EDM Schema for the data store 'patientrecords' will be updated.</span></span>
      >
      > <span data-ttu-id="67cb2-253">\[Y\] Yes \[A\] すべて Yes \[N\] No \[L\] すべて No \[?\] ヘルプ (規定値は "Y"):</span><span class="sxs-lookup"><span data-stu-id="67cb2-253">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      > <span data-ttu-id="67cb2-254">確認なしで変更を行う場合は、手順 3 で次のコマンドレットを代わりに使用します: Set-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="67cb2-254">If you want your changes to occur without confirmation, in Step 3, use this cmdlet instead: Set-DlpEdmSchema -FileData $edmSchemaXml</span></span>

      > [!NOTE]
      > <span data-ttu-id="67cb2-255">追加機能を使用して EDMSchema を更新するには、10 から 60 分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="67cb2-255">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="67cb2-256">追加機能を使用する手順を実行する前に、更新プログラムを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67cb2-256">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="removing-the-schema-for-edm-based-classification"></a><span data-ttu-id="67cb2-257">EDM ベースの分類のスキーマを削除する</span><span class="sxs-lookup"><span data-stu-id="67cb2-257">Removing the schema for EDM-based classification</span></span>

<span data-ttu-id="67cb2-258">(必要に応じて) EDM ベースの分類に使用しているスキーマを削除するには、次の手順に従います:</span><span class="sxs-lookup"><span data-stu-id="67cb2-258">(As needed) If you want to remove the schema you're using for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="67cb2-259">[セキュリティ/コンプライアンス センター PowerShellに接続する](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)の手順を使用して、セキュリティ/コンプライアンス センターに接続します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-259">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="67cb2-260">次の PowerShell コマンドレットを実行して、"patient records" のデータ ストア名を削除するものに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="67cb2-260">Run the following PowerShell cmdlets, substituting the data store name of "patient records" with the one you want to remove:</span></span>

      ```powershell
      Remove-DlpEdmSchema -Identity patientrecords
      ```

      <span data-ttu-id="67cb2-261">次のように確認を求められます。</span><span class="sxs-lookup"><span data-stu-id="67cb2-261">You will be prompted to confirm:</span></span>

      > <span data-ttu-id="67cb2-262">確認</span><span class="sxs-lookup"><span data-stu-id="67cb2-262">Confirm</span></span>
      >
      > <span data-ttu-id="67cb2-263">この操作を実行しますか?</span><span class="sxs-lookup"><span data-stu-id="67cb2-263">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="67cb2-264">データストア ' patientrecords ' の EDM スキーマが削除されます。</span><span class="sxs-lookup"><span data-stu-id="67cb2-264">EDM Schema for the data store 'patientrecords' will be removed.</span></span>
      >
      > <span data-ttu-id="67cb2-265">\[Y\] Yes \[A\] すべて Yes \[N\] No \[L\] すべて No \[?\] ヘルプ (規定値は "Y"):</span><span class="sxs-lookup"><span data-stu-id="67cb2-265">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      >  <span data-ttu-id="67cb2-266">確認なしで変更を行う場合は、手順 2 で次のコマンドレットを代わりに使用します: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span><span class="sxs-lookup"><span data-stu-id="67cb2-266">If you want your changes to occur without confirmation, in Step 2, use this cmdlet instead: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span></span>


<!-- salt notes
need two salting procedures, one for onestep from the externally facing and another for two step, on an internal machine then the upload from the external machine

- create A  folder put the edmupload agent and, csv and salt file there, run all processes there
- 
- stuff you need to have first: DataStoreName, /DataFile name (csv file)  /Hashlocation

- salt can be randomly generated by Microsoft or can be provided by the customer. If provided by the customer it must follow  format of 64 character, and can contain only letters or 0-9 characters.  Use a website to generate a valid salt value.
 
- can run EDMuploadagent.exe from PS or Windows cmd window . tested on Windows Server 2016 or Windows 10 and dot net version 4.6.2

when defiuning the schema file the searchable fields must be either an out of box SIT or custom SIT, only 5 fields )column headings) can be searchable

1. From outbound access device from the cmd prompt run EdmUploadAgent.exe /Authorize -  
2. data store schema must have already been uploaded
3.  create hash first then do upload
4. EdmUploadAgent.exe /CreateHash /DataFile (where the data file is ) E:\emd\test\data\schema32_1000000,csv /HashLocation  (where to store it) E:\edm\tat\hash this makes the salt file and the hash file as output
5. next is upload EdmUploadAgent.exe /UploadHash /DataStoreName (found in the Schema file DataSore name="FOO" /HashFile (path to hash file locaztion and file name /HashLocation path to hash)  for example
1.EdmUploadAgent/exe /UploadHash /DataStoreName schema321 /HashFile E:\edm\test\hash\schema32_10000000.EdmHash /HashLocation E:\edm\test\hash  -this one  uses MSFT generated salt, so no need to provide

Salt is an optional parameter so if yo uwant to use a custom salt add /salt and the salt value if salt file not copied to the outbound machine 

OR copy both files hash and salt to the same directory and the commmand will get both


OR do it in single step hash, salt ulopad

!! once they download the updated upload agent they will always have SALT, there is no going back.


all in one step: EdmUploadAgent.exe /UploadData /DataStoreName schema321 /DataFile E:\edm\test\data\schema32_10000.csv /HashLocation E:\edm\test\hash

tshooting/check status cmd



Once it gets to completed the admin can start using it in the custom SIT

they have to get their own custom SALT

just copy SALT over in a secure fashion










1.
6.
7.
1.  


 -->

### <a name="part-2-hash-and-upload-the-sensitive-data"></a><span data-ttu-id="67cb2-267">パート 2: 機密データをハッシュ化してアップロードする</span><span class="sxs-lookup"><span data-stu-id="67cb2-267">Part 2: Hash and upload the sensitive data</span></span>

<span data-ttu-id="67cb2-268">このフェーズでは、カスタムのセキュリティ グループとユーザー アカウントをセットアップし、EDM アップロード エージェント ツールをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="67cb2-268">In this phase, you set up a custom security group and user account, and set up the EDM Upload Agent tool.</span></span> <span data-ttu-id="67cb2-269">次に、このツールを使用して機密データにソルト値を付与してハッシュ化し、データをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="67cb2-269">Then, you use the tool to hash with salt value the sensitive data, and upload it.</span></span>

<span data-ttu-id="67cb2-270">ハッシュ化とアップロードは 1 台のコンピューターで行うこともできますし、ハッシュ化のステップとアップロードのステップを分離してセキュリティを高めることもできます。</span><span class="sxs-lookup"><span data-stu-id="67cb2-270">The hashing and uploading can be done using one computer or you can separate the hashing step from the upload step for greater security.</span></span>

<span data-ttu-id="67cb2-271">1 台のコンピューターでハッシュ化とアップロードを行う場合は、ご利用の Microsoft 365 テナントに直接接続可能なコンピューターから行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="67cb2-271">If you want to hash and upload from one computer, you need to do it from a computer that can directly connect to your Microsoft 365 tenant.</span></span> <span data-ttu-id="67cb2-272">そのためには、ハッシュ化のためにクリア テキストの機密データ ファイルがそのコンピューター上にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="67cb2-272">This requires that your clear text sensitive data files are on that computer for hashing.</span></span>

<span data-ttu-id="67cb2-273">クリア テキストの機密データ ファイルを公開したくない場合は、安全な場所にあるコンピューターでハッシュ化し、ハッシュ ファイルとソルト ファイルをご利用の Microsoft 365 テナントに直接接続可能なコンピューターにコピーしてアップロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="67cb2-273">If you do not want to expose your clear text sensitive data file, you can hash it on a computer in a secure location and then copy the hash file and the salt file to a computer that can directly connect to your Microsoft 365 tenant for upload.</span></span> <span data-ttu-id="67cb2-274">このシナリオでは、両方のコンピューターに EDMUploadAgent が必要です。</span><span class="sxs-lookup"><span data-stu-id="67cb2-274">In this scenario, you will need the EDMUploadAgent on both computers.</span></span> 

#### <a name="prerequisites"></a><span data-ttu-id="67cb2-275">前提条件</span><span class="sxs-lookup"><span data-stu-id="67cb2-275">Prerequisites</span></span>

- <span data-ttu-id="67cb2-276">**EDM\_DataUploaders** セキュリティ グループに追加される Microsoft 365 の職場または学校のアカウント</span><span class="sxs-lookup"><span data-stu-id="67cb2-276">a work or school account for Microsoft 365  that will be added to the **EDM\_DataUploaders** security group</span></span>
- <span data-ttu-id="67cb2-277">EDMUploadAgent を実行するための .NET バージョン 4.6.2 が搭載された Windows 10 または Windows Server 2016 マシン</span><span class="sxs-lookup"><span data-stu-id="67cb2-277">a Windows 10 or Windows Server 2016 machine with .NET version 4.6.2 for running the EDMUploadAgent</span></span>
- <span data-ttu-id="67cb2-278">以下のためのアップロード マシン上のディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="67cb2-278">a directory on your upload machine for the:</span></span>
    -  <span data-ttu-id="67cb2-279">EDMUploadAgent</span><span class="sxs-lookup"><span data-stu-id="67cb2-279">EDMUploadAgent</span></span>
    - <span data-ttu-id="67cb2-280">このサンプルでは、csv 形式の **PatientRecords.csv** の機密アイテム ファイル</span><span class="sxs-lookup"><span data-stu-id="67cb2-280">your sensitive item file in csv format **PatientRecords.csv** in our examples</span></span>
    -  <span data-ttu-id="67cb2-281">出力ハッシュ ファイルとソルト ファイル</span><span class="sxs-lookup"><span data-stu-id="67cb2-281">and the output hash and salt files</span></span>
    - <span data-ttu-id="67cb2-282">**edm.xml** ファイルのデータストア名 (このサンプルでは `PatientRecords`)</span><span class="sxs-lookup"><span data-stu-id="67cb2-282">the datastore name from the **edm.xml** file, for this example its `PatientRecords`</span></span>

#### <a name="set-up-the-security-group-and-user-account"></a><span data-ttu-id="67cb2-283">セキュリティ グループとユーザー アカウントをセットアップする</span><span class="sxs-lookup"><span data-stu-id="67cb2-283">Set up the security group and user account</span></span>

1. <span data-ttu-id="67cb2-284">全体管理者として、[サブスクリプションの適切なリンク](#portal-links-for-your-subscription) を使用して管理センターにアクセスし、**EDM\_DataUploaders** という [セキュリティ グループを作成します](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="67cb2-284">As a global administrator, go to the admin center using the appropriate [link for your subscription](#portal-links-for-your-subscription) and [create a security group](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) called **EDM\_DataUploaders**.</span></span>

2. <span data-ttu-id="67cb2-285">**EDM\_DataUploaders** セキュリティ グループに、1 人以上のユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-285">Add one or more users to the **EDM\_DataUploaders** security group.</span></span> <span data-ttu-id="67cb2-286">(これらのユーザーは機密情報のデータベースを管理します)。</span><span class="sxs-lookup"><span data-stu-id="67cb2-286">(These users will manage the database of sensitive information.)</span></span>

#### <a name="hash-and-upload-from-one-computer"></a><span data-ttu-id="67cb2-287">1 台のコンピューターからハッシュ化とアップロードを行う</span><span class="sxs-lookup"><span data-stu-id="67cb2-287">Hash and upload from one computer</span></span>

<span data-ttu-id="67cb2-288">このコンピュータは、ご利用の Microsoft 365 テナントに直接アクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="67cb2-288">This computer must have direct access to your Microsoft 365 tenant.</span></span>

>[!NOTE]
> <span data-ttu-id="67cb2-289">この手順を開始する前に、自分が **EDM\_DataUploaders** セキュリティ グループのメンバーであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-289">Before you begin this procedure, make sure that you are a member of the **EDM\_DataUploaders** security group.</span></span>

#### <a name="links-to-edm-upload-agent-by-subscription-type"></a><span data-ttu-id="67cb2-290">サブスクリプションの種類別の EDM アップロードエージェントへのリンク</span><span class="sxs-lookup"><span data-stu-id="67cb2-290">Links to EDM upload agent by subscription type</span></span>

- [<span data-ttu-id="67cb2-291">商用 + GCC</span><span class="sxs-lookup"><span data-stu-id="67cb2-291">Commercial + GCC</span></span>](https://go.microsoft.com/fwlink/?linkid=2088639)
- [<span data-ttu-id="67cb2-292">GCC-High</span><span class="sxs-lookup"><span data-stu-id="67cb2-292">GCC-High</span></span>](https://go.microsoft.com/fwlink/?linkid=2137521)
- [<span data-ttu-id="67cb2-293">DoD</span><span class="sxs-lookup"><span data-stu-id="67cb2-293">DoD</span></span>](https://go.microsoft.com/fwlink/?linkid=2137807)

1. <span data-ttu-id="67cb2-294">EDMUploadAgent の作業ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-294">Create a working directory for the EDMUploadAgent.</span></span> <span data-ttu-id="67cb2-295">たとえば、**C:\EDM\Data** です。</span><span class="sxs-lookup"><span data-stu-id="67cb2-295">For example, **C:\EDM\Data**.</span></span> <span data-ttu-id="67cb2-296">そこに **PatientRecords.csv** ファイルを配置します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-296">Place the **PatientRecords.csv** file there.</span></span>

2. <span data-ttu-id="67cb2-297">手順 1 で作成したディレクトリに、サブスクリプションに適した [EDM アップロードエージェント](#links-to-edm-upload-agent-by-subscription-type) をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="67cb2-297">Download and install the appropriate [EDM Upload Agent](#links-to-edm-upload-agent-by-subscription-type) for your subscription into the directory you created in step 1.</span></span>

> [!NOTE]
> <span data-ttu-id="67cb2-298">上記リンクにある EDMUploadAgent は、ハッシュ化されたデータに自動的にソルト値を追加するように更新されています。</span><span class="sxs-lookup"><span data-stu-id="67cb2-298">The EDMUploadAgent at the above links has been updated to automatically add a salt value to the hashed data.</span></span> <span data-ttu-id="67cb2-299">または、独自のソルト値を提供することもできます。</span><span class="sxs-lookup"><span data-stu-id="67cb2-299">Alternately, you can provide your own salt value.</span></span> <span data-ttu-id="67cb2-300">このバージョンを使用すると、以前のバージョンの EDMUploadAgent は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="67cb2-300">Once you have used this version, you will not be able to use the previous version of the EDMUploadAgent.</span></span>
>
> <span data-ttu-id="67cb2-301">EDMUploadAgent を使用して特定のデータ ストアにデータをアップロードできるのは、1 日に 2 回だけです。</span><span class="sxs-lookup"><span data-stu-id="67cb2-301">You can upload data with the EDMUploadAgent to any given data store only twice per day.</span></span>

> [!TIP]
> <span data-ttu-id="67cb2-302">サポートされているコマンド パラメーターから一覧を取得するには、エージェントの引数を実行します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-302">To a get a list out of the supported command parameters, run the agent no arguments.</span></span> <span data-ttu-id="67cb2-303">たとえば、「EdmUploadAgent.exe」です。</span><span class="sxs-lookup"><span data-stu-id="67cb2-303">For example 'EdmUploadAgent.exe'.</span></span>

2. <span data-ttu-id="67cb2-304">EDM アップロード エージェントを承認し、管理者としてコマンド プロンプト ウィンドウを開き、**C:\EDM\Data** ディレクトリに切り替え、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-304">Authorize the EDM Upload Agent, open  Command Prompt window (as an administrator), switch to the **C:\EDM\Data** directory and then run the following command:</span></span>

   `EdmUploadAgent.exe /Authorize`

3. <span data-ttu-id="67cb2-305">EDM_DataUploaders セキュリティ グループに追加された、Microsoft 365 の職場または学校のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="67cb2-305">Sign in with your work or school account for Microsoft 365 that was added to the EDM_DataUploaders security group.</span></span> <span data-ttu-id="67cb2-306">ユーザー アカウントからご利用のテナント情報を抽出し、接続を行います。</span><span class="sxs-lookup"><span data-stu-id="67cb2-306">Your tenant information is extracted from the user account to make the connection.</span></span>

4. <span data-ttu-id="67cb2-307">機密データをハッシュ化してアップロートするには、コマンド プロンプト ウィンドウで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-307">To hash and upload the sensitive data, run the following command in Command Prompt window:</span></span>

`EdmUploadAgent.exe /UploadData /DataStoreName \<DataStoreName\> /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="67cb2-308">例: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash**</span><span class="sxs-lookup"><span data-stu-id="67cb2-308">Example: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash**</span></span>

<span data-ttu-id="67cb2-309">これにより、ランダムに生成されたソルト値がハッシュに自動的に追加され、セキュリティが強化されます。</span><span class="sxs-lookup"><span data-stu-id="67cb2-309">This will automatically add a randomly generated salt value to the hash for greater security.</span></span> <span data-ttu-id="67cb2-310">オプションで独自のソルト値を使用する場合は、コマンドに **/Salt<saltvalue>** を追加します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-310">Optionally, if you want to use your own salt value, add the **/Salt <saltvalue>** to the command.</span></span> <span data-ttu-id="67cb2-311">この値は 64 文字の長さにする必要があり、a-z 文字と 0-9 文字のみを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="67cb2-311">This value must be 64 characters in length and can only contain the a-z characters and 0-9 characters.</span></span>

5. <span data-ttu-id="67cb2-312">次のコマンドを実行してアップロードの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-312">Check the upload status by running this command:</span></span>

`EdmUploadAgent.exe /GetSession /DataStoreName \<DataStoreName\>`

<span data-ttu-id="67cb2-313">例: **EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords**</span><span class="sxs-lookup"><span data-stu-id="67cb2-313">Example: **EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords**</span></span>

<span data-ttu-id="67cb2-314">**ProcessingInProgress** にある状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-314">Look for the status to be in **ProcessingInProgress**.</span></span> <span data-ttu-id="67cb2-315">状態が**完了**に変わるまで、数分ごとにご確認ください。</span><span class="sxs-lookup"><span data-stu-id="67cb2-315">Check again every few minutes until the status changes to **Completed**.</span></span> <span data-ttu-id="67cb2-316">状態が完了になれば、EDM データはいつでも使用することができます。</span><span class="sxs-lookup"><span data-stu-id="67cb2-316">Once the status is completed, your EDM data is ready for use.</span></span>

#### <a name="separate-hash-and-upload"></a><span data-ttu-id="67cb2-317">ハッシュ化とアップロードを分離する</span><span class="sxs-lookup"><span data-stu-id="67cb2-317">Separate Hash and upload</span></span>

<span data-ttu-id="67cb2-318">安全な環境にあるコンピューター上でハッシュ化を実行します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-318">Perform the hash on a computer in a secure environment.</span></span>

1. <span data-ttu-id="67cb2-319">コマンド プロンプト ウィンドウで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-319">Run the following command in Command Prompt windows:</span></span>

`EdmUploadAgent.exe /CreateHash /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="67cb2-320">例:</span><span class="sxs-lookup"><span data-stu-id="67cb2-320">For example:</span></span>

> <span data-ttu-id="67cb2-321">**EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash**</span><span class="sxs-lookup"><span data-stu-id="67cb2-321">**EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash**</span></span>

<span data-ttu-id="67cb2-322">**/Salt<saltvalue>** オプションを指定しなかった場合、このコマンドは次の拡張子を持つハッシュ化されたファイルとソルト ファイルを出力します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-322">This will output a hashed file and a salt file with these extensions if you didn't specify the **/Salt <saltvalue>** option:</span></span>
- <span data-ttu-id="67cb2-323">.EdmHash</span><span class="sxs-lookup"><span data-stu-id="67cb2-323">.EdmHash</span></span>
- <span data-ttu-id="67cb2-324">.EdmSalt</span><span class="sxs-lookup"><span data-stu-id="67cb2-324">.EdmSalt</span></span>

2. <span data-ttu-id="67cb2-325">これらのファイルを、機密アイテムの csv ファイル (PatientRecords) をテナントにアップロードするために使用するコンピューターへと安全な方法でコピーします。</span><span class="sxs-lookup"><span data-stu-id="67cb2-325">Copy these files in a secure fashion to the computer you will use to upload your sensitive items csv file (PatientRecords) to your tenant.</span></span>

<span data-ttu-id="67cb2-326">ハッシュされたデータをアップロードするには、Windows コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-326">To upload the hashed data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\>`

<span data-ttu-id="67cb2-327">例:</span><span class="sxs-lookup"><span data-stu-id="67cb2-327">For example:</span></span>

> <span data-ttu-id="67cb2-328">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span><span class="sxs-lookup"><span data-stu-id="67cb2-328">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span></span>


<span data-ttu-id="67cb2-329">機密データがアップロードされたことを確認するには、コマンド プロンプト ウィンドウで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-329">To verify that your sensitive data has been uploaded, run the following command in Command Prompt window:</span></span>


`EdmUploadAgent.exe /GetDataStore`

<span data-ttu-id="67cb2-330">データ ストアのリストと、それらが最後に更新された日時が表示されます。</span><span class="sxs-lookup"><span data-stu-id="67cb2-330">You'll see a list of data stores and when they were last updated.</span></span>

<span data-ttu-id="67cb2-331">特定のストアへのデータのアップロードをすべて表示する場合は、Windows コマンドプロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-331">If you want to see all the data uploads to a particular store, run the following command in a Windows command prompt:</span></span>

`EdmUploadAgent.exe /GetSession /DataStoreName <DataStoreName>`

<span data-ttu-id="67cb2-332">[機密情報データベースを更新する](#refreshing-your-sensitive-information-database) ためのプロセスとスケジュールのセットアップを進めます。</span><span class="sxs-lookup"><span data-stu-id="67cb2-332">Proceed to set up your process and schedule for [Refreshing your sensitive information database](#refreshing-your-sensitive-information-database).</span></span>

<span data-ttu-id="67cb2-333">この時点で、Microsoft クラウド サービスで EDM ベースの分類を使用する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="67cb2-333">At this point, you are ready to use EDM-based classification with your Microsoft cloud services.</span></span> <span data-ttu-id="67cb2-334">たとえば、[EDM ベースの分類を使用して DLP ポリシーを設定](#to-create-a-dlp-policy-with-edm)できます。</span><span class="sxs-lookup"><span data-stu-id="67cb2-334">For example, you can [set up a DLP policy using EDM-based classification](#to-create-a-dlp-policy-with-edm).</span></span>

#### <a name="refreshing-your-sensitive-information-database"></a><span data-ttu-id="67cb2-335">機密情報データベースを更新する</span><span class="sxs-lookup"><span data-stu-id="67cb2-335">Refreshing your sensitive information database</span></span>

<span data-ttu-id="67cb2-336">機密情報データベースは毎日更新できます。また、EDM アップロード ツールを使用して機密データのインデックスを再作成し、インデックス付きデータを再アップロードできます。</span><span class="sxs-lookup"><span data-stu-id="67cb2-336">You can refresh your sensitive information database daily, and the EDM Upload Tool can reindex the sensitive data and then reupload the indexed data.</span></span>

1. <span data-ttu-id="67cb2-337">機密情報のデータベースを更新するためのプロセスと頻度 (毎日または毎週) を決定します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-337">Determine your process and frequency (daily or weekly) for refreshing the database of sensitive information.</span></span>

2. <span data-ttu-id="67cb2-338">機密情報データを Microsoft Excel などのアプリに再度エクスポートし、ファイルを .csv 形式で保存します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-338">Re-export the sensitive data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="67cb2-339">「[機密データをハッシュしアップロードする](#part-2-hash-and-upload-the-sensitive-data)」で説明した手順の実行時に使用したものと同じファイル名と場所を使用してください。</span><span class="sxs-lookup"><span data-stu-id="67cb2-339">Keep the same file name and location you used when you followed the steps described in [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data).</span></span>

      > [!NOTE]
      > <span data-ttu-id="67cb2-340">.csv ファイルの構造 (フィールド名) に変更がない場合は、データを更新する際に、データベース スキーマ ファイルを変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="67cb2-340">If there are no changes to the structure (field names) of the .csv file, you won't need to make any changes to your database schema file when you refresh the data.</span></span> <span data-ttu-id="67cb2-341">ただし、変更が必要な場合は、必要に応じてデータベース スキーマとルール パッケージを編集してください。</span><span class="sxs-lookup"><span data-stu-id="67cb2-341">But if you must make changes, make sure to edit the database schema and your rule package accordingly.</span></span>

3. <span data-ttu-id="67cb2-342">「[機密データをハッシュしアップロードする](#part-2-hash-and-upload-the-sensitive-data)」の手順の、手順 2 と 3 を自動化するには、[タスク スケジューラ](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) を使用します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-342">Use [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) to automate steps 2 and 3 in the [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data) procedure.</span></span> <span data-ttu-id="67cb2-343">タスクのスケジュールを設定するにはいくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="67cb2-343">You can schedule tasks using several methods:</span></span>

      | <span data-ttu-id="67cb2-344">メソッド</span><span class="sxs-lookup"><span data-stu-id="67cb2-344">Method</span></span>             | <span data-ttu-id="67cb2-345">操作</span><span class="sxs-lookup"><span data-stu-id="67cb2-345">What to do</span></span> |
      | ---------------------- | ---------------- |
      | <span data-ttu-id="67cb2-346">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="67cb2-346">Windows PowerShell</span></span>     | <span data-ttu-id="67cb2-347">[ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) のドキュメントと、この記事の [PowerShell スクリプトの例](#example-powershell-script-for-task-scheduler)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67cb2-347">See the [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) documentation and the [example PowerShell script](#example-powershell-script-for-task-scheduler) in this article</span></span> |
      | <span data-ttu-id="67cb2-348">タスク スケジューラ API</span><span class="sxs-lookup"><span data-stu-id="67cb2-348">Task Scheduler API</span></span>     | <span data-ttu-id="67cb2-349">[Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="67cb2-349">See the [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) documentation</span></span>                                                                                                                                                                                                                                                                                |
      | <span data-ttu-id="67cb2-350">Windows のユーザー インターフェイス</span><span class="sxs-lookup"><span data-stu-id="67cb2-350">Windows user interface</span></span> | <span data-ttu-id="67cb2-351">Windows の場合、**[スタート]** をクリックし、「タスク スケジューラ」と入力します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-351">In Windows, click **Start**, and type Task Scheduler.</span></span> <span data-ttu-id="67cb2-352">次に、結果のリストで **[タスク スケジューラ]** を右クリックし、**[管理者として実行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-352">Then, in the list of results, right-click **Task Scheduler**, and choose **Run as administrator**.</span></span>                                                                                                                                                                                                                                                                           |

#### <a name="example-powershell-script-for-task-scheduler"></a><span data-ttu-id="67cb2-353">タスク スケジューラの PowerShell スクリプトの例</span><span class="sxs-lookup"><span data-stu-id="67cb2-353">Example PowerShell script for Task Scheduler</span></span>

<span data-ttu-id="67cb2-354">このセクションには、データをハッシュしたり、ハッシュされたデータをアップロードするタスクのスケジュールに使用できる PowerShell スクリプトの例が含まれています。</span><span class="sxs-lookup"><span data-stu-id="67cb2-354">This section includes an example PowerShell script you can use to schedule your tasks for hashing data and uploading the hashed data:</span></span>

##### <a name="to-schedule-hashing-and-upload-in-a-combined-step"></a><span data-ttu-id="67cb2-355">ハッシュのスケジュールを設定して、結合されたステップでアップロードするには</span><span class="sxs-lookup"><span data-stu-id="67cb2-355">To schedule hashing and upload in a combined step</span></span>

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
\# Assuming CSV file name is same as data store name
$dataFile = "$fileLocation\\$dataStoreName$csvext"
\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$uploadDataArgs = '/UploadData /DataStoreName ' + $dataStoreName + ' /DataFile ' + $dataFile + ' /HashLocation' + $hashLocation
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

#### <a name="to-schedule-hashing-and-upload-as-separate-steps"></a><span data-ttu-id="67cb2-356">ハッシュのスケジュールを設定して、結合されたステップでアップロードするには</span><span class="sxs-lookup"><span data-stu-id="67cb2-356">To schedule hashing and upload as separate steps</span></span>

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$edmext = '.EdmHash'
\# Assuming CSV file name is same as data store name
$dataFile = "$fileLocation\\$dataStoreName$csvext"
$hashFile = "$fileLocation\\$dataStoreName$edmext"
\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$createHashArgs = '/CreateHash' + ' /DataFile ' + $dataFile + ' /HashLocation ' + $hashLocation
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

### <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a><span data-ttu-id="67cb2-357">パート 3: Microsoft クラウド サービスで EDM ベースの分類を使用する</span><span class="sxs-lookup"><span data-stu-id="67cb2-357">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>

<span data-ttu-id="67cb2-358">これらの場所が、EDM の機密情報の種類をサポートしています:</span><span class="sxs-lookup"><span data-stu-id="67cb2-358">These locations are support EDM sensitive information types:</span></span>

- <span data-ttu-id="67cb2-359">DLP for Exchange Online (メール)</span><span class="sxs-lookup"><span data-stu-id="67cb2-359">DLP for Exchange Online (email)</span></span>
- <span data-ttu-id="67cb2-360">OneDrive for Business (ファイル)</span><span class="sxs-lookup"><span data-stu-id="67cb2-360">OneDrive for Business (files)</span></span>
- <span data-ttu-id="67cb2-361">Microsoft Teams (会話)</span><span class="sxs-lookup"><span data-stu-id="67cb2-361">Microsoft Teams (conversations)</span></span>
- <span data-ttu-id="67cb2-362">DLP for SharePoint (ファイル)</span><span class="sxs-lookup"><span data-stu-id="67cb2-362">DLP for SharePoint (files)</span></span>
- <span data-ttu-id="67cb2-363">Microsoft Cloud App Security DLP ポリシー</span><span class="sxs-lookup"><span data-stu-id="67cb2-363">Microsoft Cloud App Security DLP policies</span></span>

<span data-ttu-id="67cb2-364">次のシナリオでは、EDM の機密情報の種類は現在開発中で、まだご利用いただけません。</span><span class="sxs-lookup"><span data-stu-id="67cb2-364">EDM sensitive information types for following scenarios are currently in development, but not yet available:</span></span>

- <span data-ttu-id="67cb2-365">機密度ラベルと保持ラベルの自動分類</span><span class="sxs-lookup"><span data-stu-id="67cb2-365">Auto-classification of sensitivity labels and retention labels</span></span>

#### <a name="to-create-a-dlp-policy-with-edm"></a><span data-ttu-id="67cb2-366">EDM を使用して DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="67cb2-366">To create a DLP policy with EDM</span></span>

1. <span data-ttu-id="67cb2-367">[サブスクリプションに適切なリンク](#portal-links-for-your-subscription)を使用して、セキュリティ/コンプライアンス センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-367">Go to the Security & Compliance Center using the appropriate [link for your subscription](#portal-links-for-your-subscription).</span></span>

2. <span data-ttu-id="67cb2-368">**[データ損失防止]** \> **[ポリシー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-368">Choose **Data loss prevention** \> **Policy**.</span></span>

3. <span data-ttu-id="67cb2-369">**[ポリシーの作成]** \> **[カスタム]** \> **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-369">Choose **Create a policy** \> **Custom** \> **Next**.</span></span>

4. <span data-ttu-id="67cb2-370">**[ポリシーの名前を設定]** タブで名前と説明を指定し、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-370">On the **Name your policy** tab, specify a name and description, and then choose **Next**.</span></span>

5. <span data-ttu-id="67cb2-371">**[場所の選択]** タブで **[特定の場所を選択]** を選択し、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-371">On the **Choose locations** tab, select **Let me choose specific locations**, and then choose **Next**.</span></span>

6. <span data-ttu-id="67cb2-372">**[状態]** の列で、**Exchange メール、OneDrive アカウント、Teams チャット、チャネル メッセージ** を選択し、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-372">In the **Status** column, select **Exchange email, OneDrive accounts, Teams chat and channel message** , and then choose **Next**.</span></span>

7. <span data-ttu-id="67cb2-373">**[ポリシーの設定]** タブで **[詳細な設定を使用]** を選択し、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-373">On the **Policy settings** tab, choose **Use advanced settings**, and then choose **Next**.</span></span>

8. <span data-ttu-id="67cb2-374">**[+ 新しいルール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-374">Choose **+ New rule**.</span></span>

9. <span data-ttu-id="67cb2-375">**[名前]** セクションで、ルールの名前と説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-375">In the **Name** section, specify a name and description for the rule.</span></span>

10. <span data-ttu-id="67cb2-376">**[条件]** セクションの **[+ 条件の追加]** リストで、**[コンテンツに機密情報の種類を含む]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-376">In the **Conditions** section, in the **+ Add a condition** list, choose **Content contains sensitive type**.</span></span>

      ![機密情報の種類を含むコンテンツ](../media/edm-dlp-newrule-conditions.png)

11. <span data-ttu-id="67cb2-378">ルール パッケージのセットアップ時に作成した機密情報の種類を検索し、**[+ 追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-378">Search for the sensitive information type you created when you set up your rule package, and then choose **+ Add**.</span></span>  
    <span data-ttu-id="67cb2-379">次に、**[完了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-379">Then choose **Done**.</span></span>

12. <span data-ttu-id="67cb2-380">ルールのオプション (**[ユーザー通知]**、**[ユーザーによる上書き]**、**[インシデント レポート]** など) の選択を終了し、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-380">Finish selecting options for your rule, such as **User notifications**, **User overrides**, **Incident reports**, and so on, and then choose **Save**.</span></span>

13. <span data-ttu-id="67cb2-381">**[ポリシーの設定]** タブでルールを確認し、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-381">On the **Policy settings** tab, review your rules, and then choose **Next**.</span></span>

14. <span data-ttu-id="67cb2-382">ポリシーをすぐに有効にするか、テストするか、無効にするかを指定します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-382">Specify whether to turn on the policy right away, test it out, or keep it turned off.</span></span> <span data-ttu-id="67cb2-383">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-383">Then choose **Next**.</span></span>

15. <span data-ttu-id="67cb2-384">**[設定を確認]** タブで、ポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-384">On the **Review your settings** tab, review your policy.</span></span> <span data-ttu-id="67cb2-385">必要な変更を行います。</span><span class="sxs-lookup"><span data-stu-id="67cb2-385">Make any needed changes.</span></span> <span data-ttu-id="67cb2-386">準備ができたら **[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="67cb2-386">When you're ready, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="67cb2-387">新しい DLP ポリシーがデータ センターを通過するまでに、約 1 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="67cb2-387">Allow approximately one hour for your new DLP policy to work its way through your data center.</span></span>

## <a name="related-articles"></a><span data-ttu-id="67cb2-388">関連記事</span><span class="sxs-lookup"><span data-stu-id="67cb2-388">Related articles</span></span>

- [<span data-ttu-id="67cb2-389">機密情報の種類のエンティティ定義</span><span class="sxs-lookup"><span data-stu-id="67cb2-389">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="67cb2-390">カスタムの機密情報の種類</span><span class="sxs-lookup"><span data-stu-id="67cb2-390">Custom sensitive information types</span></span>](custom-sensitive-info-types.md)
- [<span data-ttu-id="67cb2-391">DLP ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="67cb2-391">Overview of DLP policies</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="67cb2-392">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="67cb2-392">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)
- [<span data-ttu-id="67cb2-393">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="67cb2-393">New-DlpEdmSchema</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-dlpedmschema)

