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
ms.openlocfilehash: d08589ec9465142e772c3190954ed7f93fbc68fe
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2020
ms.locfileid: "46648752"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification"></a><span data-ttu-id="41a28-103">Exact Data Match に基づく分類で、カスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="41a28-103">Create custom sensitive information types with Exact Data Match based classification</span></span>

<span data-ttu-id="41a28-104">[カスタムの機密情報の種類](custom-sensitive-info-types.md) は、機密情報の不注意または不適切な共有を防ぐために使用されます。</span><span class="sxs-lookup"><span data-stu-id="41a28-104">[Custom sensitive information types](custom-sensitive-info-types.md) are used to help prevent inadvertent or inappropriate sharing of sensitive information.</span></span> <span data-ttu-id="41a28-105">管理者はセキュリティ/コンプライアンス センターまたは PowerShell を使用して、パターン、証拠 ( *従業員*、 *バッジ*、 *ID* などのキーワード)、文字の近接性 (特定のパターンの文字に証拠がどれほど近接しているか)、および信頼レベルに基づいてカスタムの機密情報の種類を定義できます。</span><span class="sxs-lookup"><span data-stu-id="41a28-105">As an administrator, you can use the Security & Compliance Center or PowerShell to define a custom sensitive information type based on patterns, evidence (keywords such as *employee*, *badge*, *ID*, and so on), character proximity (how close evidence is to characters in a particular pattern), and confidence levels.</span></span> <span data-ttu-id="41a28-106">このようなカスタムの機密情報の種類は、多くの組織のビジネス ニーズを満たします。</span><span class="sxs-lookup"><span data-stu-id="41a28-106">Such custom sensitive information types meet business needs for many organizations.</span></span>

<span data-ttu-id="41a28-107">しかし、汎用的なパターンのみを使用するのではなく、正確なデータ値を使用するカスタムの機密情報の種類が必要な場合はどうでしょう。</span><span class="sxs-lookup"><span data-stu-id="41a28-107">But what if you wanted a custom sensitive information type that uses exact data values, instead of matching only with generic patterns?</span></span> <span data-ttu-id="41a28-108">Exact Data Match (EDM) ベースの分類では、次の目的で設計されたカスタムの機密情報の種類を作成できます。</span><span class="sxs-lookup"><span data-stu-id="41a28-108">With Exact Data Match (EDM)-based classification, you can create a custom sensitive information type that is designed to:</span></span>

- <span data-ttu-id="41a28-109">動的で更新可能なものにする。</span><span class="sxs-lookup"><span data-stu-id="41a28-109">be dynamic and refreshable;</span></span>
- <span data-ttu-id="41a28-110">拡張性の高いものにする。</span><span class="sxs-lookup"><span data-stu-id="41a28-110">be more scalable;</span></span>
- <span data-ttu-id="41a28-111">結果的に誤検知数を減らす。</span><span class="sxs-lookup"><span data-stu-id="41a28-111">result in fewer false-positives;</span></span>
- <span data-ttu-id="41a28-112">構造化された機密データを操作する。</span><span class="sxs-lookup"><span data-stu-id="41a28-112">work with structured sensitive data;</span></span>
- <span data-ttu-id="41a28-113">機密情報をより安全に処理する。</span><span class="sxs-lookup"><span data-stu-id="41a28-113">handle sensitive information more securely; and</span></span>
- <span data-ttu-id="41a28-114">さまざまな Microsoft クラウド サービスで使用する。</span><span class="sxs-lookup"><span data-stu-id="41a28-114">be used with several Microsoft cloud services.</span></span>

![EDM ベースの分類](../media/EDMClassification.png)

<span data-ttu-id="41a28-116">EDM ベースの分類を使用すると、機密情報のデータベース内の正確な値を参照する、カスタムの機密情報の種類を作成できます。</span><span class="sxs-lookup"><span data-stu-id="41a28-116">EDM-based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="41a28-117">データベースは毎日、または毎週更新できます。また、最大 1 億行のデータを格納できます。</span><span class="sxs-lookup"><span data-stu-id="41a28-117">The database can be refreshed daily or weekly, and it can contain up to 100 million rows of data.</span></span> <span data-ttu-id="41a28-118">そのため、従業員、患者、または顧客の出入りに合わせて記録が変更されても、カスタムの機密情報の種類は最新の状態が維持されます。</span><span class="sxs-lookup"><span data-stu-id="41a28-118">So as employees, patients, or clients come and go, and records change, your custom sensitive information types remain current and applicable.</span></span> <span data-ttu-id="41a28-119">また、EDM ベースの分類は、 [データ損失防止ポリシー](data-loss-prevention-policies.md) (DLP) や [Microsoft Cloud App Security ファイル ポリシー](https://docs.microsoft.com/cloud-app-security/data-protection-policies) などのポリシーと共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="41a28-119">And, you can use EDM-based classification with policies, such as [data loss prevention policies](data-loss-prevention-policies.md) (DLP) or [Microsoft Cloud App Security file policies](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="41a28-120">必要なライセンスとアクセス許可</span><span class="sxs-lookup"><span data-stu-id="41a28-120">Required licenses and permissions</span></span>

<span data-ttu-id="41a28-121">この記事で説明されているタスクを実行するには、全体管理者、コンプライアンス管理者、または Exchange Online の管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="41a28-121">You must be a global admin, compliance administrator, or Exchange Online administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="41a28-122">DLP アクセス許可の詳細については、「 [アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41a28-122">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="41a28-123">これらのサブスクリプションには、EDM ベースの分類が含まれています</span><span class="sxs-lookup"><span data-stu-id="41a28-123">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="41a28-124">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="41a28-124">Office 365 E5</span></span>
- <span data-ttu-id="41a28-125">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="41a28-125">Microsoft 365 E5</span></span>
- <span data-ttu-id="41a28-126">Microsoft 365 E5 Compliance </span><span class="sxs-lookup"><span data-stu-id="41a28-126">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="41a28-127">Microsoft E5/A5 Information Protection and Governance</span><span class="sxs-lookup"><span data-stu-id="41a28-127">Microsoft E5/A5 Information Protection and Governance</span></span>

## <a name="portal-links-for-your-subscription"></a><span data-ttu-id="41a28-128">サブスクリプションのポータルリンク</span><span class="sxs-lookup"><span data-stu-id="41a28-128">Portal links for your subscription</span></span>


|<span data-ttu-id="41a28-129">ポータル</span><span class="sxs-lookup"><span data-stu-id="41a28-129">Portal</span></span>  |<span data-ttu-id="41a28-130">世界中の GCC</span><span class="sxs-lookup"><span data-stu-id="41a28-130">World Wide/GCC</span></span>  |<span data-ttu-id="41a28-131">GCC-High</span><span class="sxs-lookup"><span data-stu-id="41a28-131">GCC-High</span></span>  |<span data-ttu-id="41a28-132">DOD</span><span class="sxs-lookup"><span data-stu-id="41a28-132">DOD</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="41a28-133">Office SCC</span><span class="sxs-lookup"><span data-stu-id="41a28-133">Office SCC</span></span>     |  <span data-ttu-id="41a28-134">protection.office.com</span><span class="sxs-lookup"><span data-stu-id="41a28-134">protection.office.com</span></span>       |<span data-ttu-id="41a28-135">scc.office365.us</span><span class="sxs-lookup"><span data-stu-id="41a28-135">scc.office365.us</span></span>         |<span data-ttu-id="41a28-136">scc.protection.apps.mil</span><span class="sxs-lookup"><span data-stu-id="41a28-136">scc.protection.apps.mil</span></span> |
|<span data-ttu-id="41a28-137">Microsoft 365 セキュリティ センター</span><span class="sxs-lookup"><span data-stu-id="41a28-137">Microsoft 365 Security center</span></span>     |<span data-ttu-id="41a28-138">security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="41a28-138">security.microsoft.com</span></span>         |<span data-ttu-id="41a28-139">security.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="41a28-139">security.microsoft.us</span></span>         |<span data-ttu-id="41a28-140">security.apps.mil</span><span class="sxs-lookup"><span data-stu-id="41a28-140">security.apps.mil</span></span>|
|<span data-ttu-id="41a28-141">Microsoft 365 コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="41a28-141">Microsoft 365 Compliance center</span></span>     |<span data-ttu-id="41a28-142">compliance.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="41a28-142">compliance.microsoft.com</span></span>         |<span data-ttu-id="41a28-143">compliance.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="41a28-143">compliance.microsoft.us</span></span>         |<span data-ttu-id="41a28-144">compliance.apps.mil</span><span class="sxs-lookup"><span data-stu-id="41a28-144">compliance.apps.mil</span></span>|


## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="41a28-145">ワークフローの概要</span><span class="sxs-lookup"><span data-stu-id="41a28-145">The work flow at a glance</span></span>

|<span data-ttu-id="41a28-146">フェーズ</span><span class="sxs-lookup"><span data-stu-id="41a28-146">Phase</span></span>  |<span data-ttu-id="41a28-147">前提条件</span><span class="sxs-lookup"><span data-stu-id="41a28-147">What's needed</span></span>  |
|---------|---------|
|[<span data-ttu-id="41a28-148">パート 1: EDM ベースの分類をセットアップする</span><span class="sxs-lookup"><span data-stu-id="41a28-148">Part 1: Set up EDM-based classification</span></span>](#part-1-set-up-edm-based-classification)<br/><br/><span data-ttu-id="41a28-149">(適宜)</span><span class="sxs-lookup"><span data-stu-id="41a28-149">(As needed)</span></span><br/><span data-ttu-id="41a28-150">- [データベーススキーマを編集する](#editing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="41a28-150">- [Edit the database schema](#editing-the-schema-for-edm-based-classification)</span></span> <br/><span data-ttu-id="41a28-151">- [スキーマを削除する](#removing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="41a28-151">- [Remove the schema](#removing-the-schema-for-edm-based-classification)</span></span> |<span data-ttu-id="41a28-152">- 機密データへの読み取りアクセス</span><span class="sxs-lookup"><span data-stu-id="41a28-152">- Read access to the sensitive data</span></span><br/><span data-ttu-id="41a28-153">- XML 形式のデータベース スキーマ (例を提供)</span><span class="sxs-lookup"><span data-stu-id="41a28-153">- Database schema in XML format (example provided)</span></span><br/><span data-ttu-id="41a28-154">- XML 形式のルール パッケージ (例を提供)</span><span class="sxs-lookup"><span data-stu-id="41a28-154">- Rule package in XML format (example provided)</span></span><br/><span data-ttu-id="41a28-155">- セキュリティ/コンプライアンス センターへの管理者権限 (PowerShell を使用)</span><span class="sxs-lookup"><span data-stu-id="41a28-155">- Admin permissions to the Security & Compliance Center (using PowerShell)</span></span> |
|[<span data-ttu-id="41a28-156">パート 2: 機密データをハッシュしアップロードする</span><span class="sxs-lookup"><span data-stu-id="41a28-156">Part 2: Hash and upload the sensitive data</span></span>](#part-2-hash-and-upload-the-sensitive-data)<br/><br/><span data-ttu-id="41a28-157">(適宜)</span><span class="sxs-lookup"><span data-stu-id="41a28-157">(As needed)</span></span><br/>[<span data-ttu-id="41a28-158">データを更新する</span><span class="sxs-lookup"><span data-stu-id="41a28-158">Refresh the data</span></span>](#refreshing-your-sensitive-information-database) |<span data-ttu-id="41a28-159">- カスタムのセキュリティ グループとユーザー アカウント</span><span class="sxs-lookup"><span data-stu-id="41a28-159">- Custom security group and user account</span></span><br/><span data-ttu-id="41a28-160">- EDM アップロード エージェントを使用するコンピューターへのローカル管理者アクセス</span><span class="sxs-lookup"><span data-stu-id="41a28-160">- Local admin access to machine with EDM Upload Agent</span></span><br/><span data-ttu-id="41a28-161">- 機密データへの読み取りアクセス</span><span class="sxs-lookup"><span data-stu-id="41a28-161">- Read access to the sensitive data</span></span><br/><span data-ttu-id="41a28-162">- データ更新のプロセスとスケジュール</span><span class="sxs-lookup"><span data-stu-id="41a28-162">- Process and schedule for refreshing the data</span></span>|
|[<span data-ttu-id="41a28-163">パート 3: Microsoft クラウド サービスで EDM ベースの分類を使用する</span><span class="sxs-lookup"><span data-stu-id="41a28-163">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services) |<span data-ttu-id="41a28-164">- DLP を使用する Microsoft 365 サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="41a28-164">- Microsoft 365 subscription with DLP</span></span><br/><span data-ttu-id="41a28-165">- 有効化された EDM ベースの分類機能</span><span class="sxs-lookup"><span data-stu-id="41a28-165">- EDM-based classification feature enabled</span></span> |

### <a name="part-1-set-up-edm-based-classification"></a><span data-ttu-id="41a28-166">パート 1: EDM ベースの分類をセットアップする</span><span class="sxs-lookup"><span data-stu-id="41a28-166">Part 1: Set up EDM-based classification</span></span>

<span data-ttu-id="41a28-167">EDM ベースの分類をセットアップおよび構成するには、機密データを .csv 形式で保存し、機密情報のデータベースのスキーマを定義して、ルール パッケージを作成し、スキーマとルール パッケージをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="41a28-167">Setting up and configuring EDM-based classification involves saving sensitive data in .csv format, defining a schema for your database of sensitive information, creating a rule package, and then uploading the schema and rule package.</span></span>

#### <a name="define-the-schema-for-your-database-of-sensitive-information"></a><span data-ttu-id="41a28-168">機密情報のデータベースのスキーマを定義する</span><span class="sxs-lookup"><span data-stu-id="41a28-168">Define the schema for your database of sensitive information</span></span>

1. <span data-ttu-id="41a28-169">使用する機密情報を特定します。</span><span class="sxs-lookup"><span data-stu-id="41a28-169">Identify the sensitive information you want to use.</span></span> <span data-ttu-id="41a28-170">データを Microsoft Excel などのアプリにエクスポートし、ファイルを .csv 形式で保存します。</span><span class="sxs-lookup"><span data-stu-id="41a28-170">Export the data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="41a28-171">データ ファイルには、次のデータを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="41a28-171">The data file can include a maximum of:</span></span>
      - <span data-ttu-id="41a28-172">最大 1 億行の機密データ</span><span class="sxs-lookup"><span data-stu-id="41a28-172">Up to 100 million rows of sensitive data</span></span>
      - <span data-ttu-id="41a28-173">データ ソースごとに最大 32 列 (フィールド)</span><span class="sxs-lookup"><span data-stu-id="41a28-173">Up to 32 columns (fields) per data source</span></span>
      - <span data-ttu-id="41a28-174">検索可能としてマークされた列 (フィールド) を最大 5 列</span><span class="sxs-lookup"><span data-stu-id="41a28-174">Up to 5 columns (fields) marked as searchable</span></span>

2. <span data-ttu-id="41a28-175">EDM ベースの分類に使用されるフィールドの名前が 1 行目に含まれるように、.csv ファイル内の機密データを構成します。</span><span class="sxs-lookup"><span data-stu-id="41a28-175">Structure the sensitive data in the .csv file such that the first row includes the names of the fields used for EDM-based classification.</span></span> <span data-ttu-id="41a28-176">.csv ファイルには、"ssn"、"birthdate"、"firstname"、"lastname" などのフィールド名があります。</span><span class="sxs-lookup"><span data-stu-id="41a28-176">In your .csv file, you might have field names, such as "ssn", "birthdate", "firstname", "lastname", and so on.</span></span> <span data-ttu-id="41a28-177">列見出しに、名前にスペースまたはアンダースコアを含めることはできませんのでご了承ください。</span><span class="sxs-lookup"><span data-stu-id="41a28-177">Please note that column headers can't include spaces or underscores in their names.</span></span> <span data-ttu-id="41a28-178">たとえば、 csv ファイルは *PatientRecords.csv*と呼ばれており、その列には *PatientID*、 *MRN*、 *LastName*、 *FirstName*、 *SSN*などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="41a28-178">As an example, our .csv file is called *PatientRecords.csv*, and its columns include *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN*, and more.</span></span>

3. <span data-ttu-id="41a28-179">機密情報のデータベースのスキーマを XML 形式で定義します (次の例と同様)。</span><span class="sxs-lookup"><span data-stu-id="41a28-179">Define the schema for the database of sensitive information in XML format (similar to our example below).</span></span> <span data-ttu-id="41a28-180">このスキーマ ファイルの名前を  **edm.xml** にして、データベースの各列に対して構文を使用する行があるように構成します。</span><span class="sxs-lookup"><span data-stu-id="41a28-180">Name this schema file **edm.xml**, and configure it such that for each column in the database, there is a line that uses the syntax:</span></span> 

      <span data-ttu-id="41a28-181">`\<Field name="" searchable=""/\>`</span><span class="sxs-lookup"><span data-stu-id="41a28-181">`\<Field name="" searchable=""/\>`.</span></span>

      - <span data-ttu-id="41a28-182"> *Field name*  の値に列名を使用します。</span><span class="sxs-lookup"><span data-stu-id="41a28-182">Use column names for *Field name* values.</span></span>
      - <span data-ttu-id="41a28-183"> *searchable="true"*  を使用して、最大 5 つのフィールドで検索可能にします。</span><span class="sxs-lookup"><span data-stu-id="41a28-183">Use *searchable="true"* for the fields that you want to be searchable up to a maximum of 5 fields.</span></span> <span data-ttu-id="41a28-184">少なくとも 1 つのフィールドを検索可能に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41a28-184">You must designate a minimum of one field as searchable.</span></span>

      <span data-ttu-id="41a28-185">たとえば、次の XML ファイルは患者の記録のデータベースのスキーマを定義します。検索可能として指定された 5 つのフィールドは、 *PatientID*、 *MRN*、 *SSN*、 *Phone*、 *DOB* です。</span><span class="sxs-lookup"><span data-stu-id="41a28-185">As an example, the following XML file defines the schema for a patient records database, with five fields specified as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span>

      <span data-ttu-id="41a28-186">(この例は、コピー、変更、使用することができます。)</span><span class="sxs-lookup"><span data-stu-id="41a28-186">(You can copy, modify, and use our example.)</span></span>

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

4. <span data-ttu-id="41a28-187">[セキュリティ/コンプライアンス センター PowerShellに接続する](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)の手順を使用して、セキュリティ/コンプライアンス センターに接続します。</span><span class="sxs-lookup"><span data-stu-id="41a28-187">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

5. <span data-ttu-id="41a28-188">データベース スキーマをアップロードするには、次のコマンドレットを 1 つずつ実行します。</span><span class="sxs-lookup"><span data-stu-id="41a28-188">To upload the database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="41a28-189">次のように、確認を求められます。</span><span class="sxs-lookup"><span data-stu-id="41a28-189">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="41a28-190">確認</span><span class="sxs-lookup"><span data-stu-id="41a28-190">Confirm</span></span>
      >
      > <span data-ttu-id="41a28-191">この操作を実行しますか?</span><span class="sxs-lookup"><span data-stu-id="41a28-191">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="41a28-192">データストア ' patientrecords ' の新しい EDM スキーマがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="41a28-192">New EDM Schema for the data store 'patientrecords' will be imported.</span></span>
      >
      > <span data-ttu-id="41a28-193">\[Y\] Yes \[A\] すべて Yes \[N\] No \[L\] すべて No \[?\] ヘルプ (規定値は "Y"):</span><span class="sxs-lookup"><span data-stu-id="41a28-193">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
> <span data-ttu-id="41a28-194">確認なしで変更を行う場合は、手順 5 で次のコマンドレットを代わりに使用します: New-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="41a28-194">If you want your changes to occur without confirmation, in Step 5, use this cmdlet instead: New-DlpEdmSchema -FileData $edmSchemaXml</span></span>

> [!NOTE]
> <span data-ttu-id="41a28-195">追加機能を使用して EDMSchema を更新するには、10 から 60 分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="41a28-195">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="41a28-196">追加機能を使用する手順を実行する前に、更新プログラムを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41a28-196">The update must complete before you execute steps that use the additions.</span></span>

<span data-ttu-id="41a28-197">機密情報のデータベースのスキーマが定義されたので、次はルール パッケージをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="41a28-197">Now that the schema for your database of sensitive information is defined, the next step is to set up a rule package.</span></span> <span data-ttu-id="41a28-198">セクション「 [ルール パッケージのセットアップ](#set-up-a-rule-package)」に進みます。</span><span class="sxs-lookup"><span data-stu-id="41a28-198">Proceed to the section [Set up a rule package](#set-up-a-rule-package).</span></span>

#### <a name="editing-the-schema-for-edm-based-classification"></a><span data-ttu-id="41a28-199">EDM ベースの分類のスキーマを編集する</span><span class="sxs-lookup"><span data-stu-id="41a28-199">Editing the schema for EDM-based classification</span></span>

<span data-ttu-id="41a28-200">EDM ベースの分類に使用するフィールドの変更など、**edm.xml** ファイルを変更する場合は、次の手順に従います:</span><span class="sxs-lookup"><span data-stu-id="41a28-200">If you want to make changes to your **edm.xml** file, such as changing which fields are used for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="41a28-201">**edm.mxl** ファイルを編集します (これは、この記事の「 [スキーマを定義する](#define-the-schema-for-your-database-of-sensitive-information) 」セクションで説明したファイルです)。</span><span class="sxs-lookup"><span data-stu-id="41a28-201">Edit your **edm.xml** file (this is the file discussed in the [Define the schema](#define-the-schema-for-your-database-of-sensitive-information) section of this article).</span></span>

2. <span data-ttu-id="41a28-202">[セキュリティ/コンプライアンス センター PowerShellに接続する](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)の手順を使用して、セキュリティ/コンプライアンス センターに接続します。</span><span class="sxs-lookup"><span data-stu-id="41a28-202">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

3. <span data-ttu-id="41a28-203">データベース スキーマを更新するには、次のコマンドレットを 1 つずつ実行します。</span><span class="sxs-lookup"><span data-stu-id="41a28-203">To update your database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="41a28-204">次のように、確認を求められます。</span><span class="sxs-lookup"><span data-stu-id="41a28-204">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="41a28-205">確認</span><span class="sxs-lookup"><span data-stu-id="41a28-205">Confirm</span></span>
      >
      > <span data-ttu-id="41a28-206">この操作を実行しますか?</span><span class="sxs-lookup"><span data-stu-id="41a28-206">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="41a28-207">データストア ' patientrecords ' の EDM スキーマが更新されます。</span><span class="sxs-lookup"><span data-stu-id="41a28-207">EDM Schema for the data store 'patientrecords' will be updated.</span></span>
      >
      > <span data-ttu-id="41a28-208">\[Y\] Yes \[A\] すべて Yes \[N\] No \[L\] すべて No \[?\] ヘルプ (規定値は "Y"):</span><span class="sxs-lookup"><span data-stu-id="41a28-208">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      > <span data-ttu-id="41a28-209">確認なしで変更を行う場合は、手順 3 で次のコマンドレットを代わりに使用します: Set-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="41a28-209">If you want your changes to occur without confirmation, in Step 3, use this cmdlet instead: Set-DlpEdmSchema -FileData $edmSchemaXml</span></span>

      > [!NOTE]
      > <span data-ttu-id="41a28-210">追加機能を使用して EDMSchema を更新するには、10 から 60 分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="41a28-210">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="41a28-211">追加機能を使用する手順を実行する前に、更新プログラムを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41a28-211">The update must complete before you execute steps that use the additions.</span></span>

## <a name="removing-the-schema-for-edm-based-classification"></a><span data-ttu-id="41a28-212">EDM ベースの分類のスキーマを削除する</span><span class="sxs-lookup"><span data-stu-id="41a28-212">Removing the schema for EDM-based classification</span></span>

<span data-ttu-id="41a28-213">(必要に応じて) EDM ベースの分類に使用しているスキーマを削除するには、次の手順に従います:</span><span class="sxs-lookup"><span data-stu-id="41a28-213">(As needed) If you want to remove the schema you're using for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="41a28-214">[セキュリティ/コンプライアンス センター PowerShellに接続する](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)の手順を使用して、セキュリティ/コンプライアンス センターに接続します。</span><span class="sxs-lookup"><span data-stu-id="41a28-214">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

2. <span data-ttu-id="41a28-215">次の PowerShell コマンドレットを実行して、「patientrecords」のデータ ストア名を削除するものに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="41a28-215">Run the following PowerShell cmdlets, substituting the data store name of "patientrecords" with the one you want to remove:</span></span>

      ```powershell
      Remove-DlpEdmSchema -Identity patientrecords
      ```

      <span data-ttu-id="41a28-216">次のように、確認を求められます。</span><span class="sxs-lookup"><span data-stu-id="41a28-216">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="41a28-217">確認</span><span class="sxs-lookup"><span data-stu-id="41a28-217">Confirm</span></span>
      >
      > <span data-ttu-id="41a28-218">この操作を実行しますか?</span><span class="sxs-lookup"><span data-stu-id="41a28-218">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="41a28-219">データストア ' patientrecords ' の EDM スキーマが削除されます。</span><span class="sxs-lookup"><span data-stu-id="41a28-219">EDM Schema for the data store 'patientrecords' will be removed.</span></span>
      >
      > <span data-ttu-id="41a28-220">\[Y\] Yes \[A\] すべて Yes \[N\] No \[L\] すべて No \[?\] ヘルプ (規定値は "Y"):</span><span class="sxs-lookup"><span data-stu-id="41a28-220">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      >  <span data-ttu-id="41a28-221">確認なしで変更を行う場合は、手順 2 で次のコマンドレットを代わりに使用します: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span><span class="sxs-lookup"><span data-stu-id="41a28-221">If you want your changes to occur without confirmation, in Step 2, use this cmdlet instead: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span></span>

### <a name="set-up-a-rule-package"></a><span data-ttu-id="41a28-222">ルール パッケージを設定する</span><span class="sxs-lookup"><span data-stu-id="41a28-222">Set up a rule package</span></span>

1. <span data-ttu-id="41a28-223">次の例のように、XML 形式 (Unicode エンコード) でルール パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="41a28-223">Create a rule package in XML format (with Unicode encoding), similar to the following example.</span></span> <span data-ttu-id="41a28-224">(この例は、コピー、変更、使用することができます。)</span><span class="sxs-lookup"><span data-stu-id="41a28-224">(You can copy, modify, and use our example.)</span></span>

      <span data-ttu-id="41a28-225">ルール パッケージをセットアップするときに、.csv ファイルと **edm .xml** ファイルを正しく参照してください。</span><span class="sxs-lookup"><span data-stu-id="41a28-225">When you set up your rule package, make sure to correctly reference your .csv file and **edm.xml** file.</span></span> <span data-ttu-id="41a28-226">この例は、コピー、変更、使用が可能です。</span><span class="sxs-lookup"><span data-stu-id="41a28-226">You can copy, modify, and use our example.</span></span> <span data-ttu-id="41a28-227">このサンプル xml では、EDM の機密情報の種類を作成するために、次のフィールドをカスタマイズする必要があります。</span><span class="sxs-lookup"><span data-stu-id="41a28-227">In this sample xml the following fields needs to be customized to create your EDM sensitive type:</span></span>

      - <span data-ttu-id="41a28-228">**RulePack id & ExactMatch id**:  [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6)  を使用して GUID を作成します。</span><span class="sxs-lookup"><span data-stu-id="41a28-228">**RulePack id & ExactMatch id**: Use [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) to generate a GUID.</span></span>

      - <span data-ttu-id="41a28-229">**Datastore**: このフィールドは、使用する EDM ルックアップデータストアを指定します。</span><span class="sxs-lookup"><span data-stu-id="41a28-229">**Datastore**: This field specifies EDM lookup data store to be used.</span></span> <span data-ttu-id="41a28-230">設定済みの EDM スキーマのデータソース名を指定します。</span><span class="sxs-lookup"><span data-stu-id="41a28-230">You provide a data source name of a configured EDM Schema.</span></span>

      - <span data-ttu-id="41a28-231">**idMatch**: このフィールドは、EDM の主要素を示します。</span><span class="sxs-lookup"><span data-stu-id="41a28-231">**idMatch**: This field points to the primary element for EDM.</span></span>
        - <span data-ttu-id="41a28-232">検索結果: ルックアップで使用するフィールドを指定します。</span><span class="sxs-lookup"><span data-stu-id="41a28-232">Matches: Specifies the field to be used in exact lookup.</span></span> <span data-ttu-id="41a28-233">データストアの EDM スキーマで検索可能なフィールド名を指定します。</span><span class="sxs-lookup"><span data-stu-id="41a28-233">You provide a searchable field name in EDM Schema for the DataStore.</span></span>
        - <span data-ttu-id="41a28-234">分類: このフィールドでは、EDM ルックアップをトリガーする、機密情報の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="41a28-234">Classification: This field specifies the sensitive type match that triggers EDM lookup.</span></span> <span data-ttu-id="41a28-235">既存の組み込みまたはカスタム分類の名前または GUID を指定できます。</span><span class="sxs-lookup"><span data-stu-id="41a28-235">You can provide Name or GUID of an existing built-in or custom classification.</span></span>

      - <span data-ttu-id="41a28-236">**Match:** このフィールドは、近接 idMatch で見つかった追加の証拠を示します。</span><span class="sxs-lookup"><span data-stu-id="41a28-236">**Match:** This field points to additional evidence found in proximity of idMatch.</span></span>
        - <span data-ttu-id="41a28-237">Matches: データストアの EDM スキーマで検索可能なフィールド名を指定します。</span><span class="sxs-lookup"><span data-stu-id="41a28-237">Matches: You provide any field name in EDM Schema for DataStore.</span></span>
      - <span data-ttu-id="41a28-238">**リソース:** このセクションでは、複数のローカルでの機密情報の種類の名前と説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="41a28-238">**Resource:** This section specifies the name and description for sensitive type in multiple locales.</span></span>
        - <span data-ttu-id="41a28-239">idRef: ExactMatch ID の GUID を指定します。</span><span class="sxs-lookup"><span data-stu-id="41a28-239">idRef: You provide GUID for ExactMatch ID.</span></span>
        - <span data-ttu-id="41a28-240">名前と説明: 必要に応じてカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="41a28-240">Name & descriptions: customize as required.</span></span>

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

1. <span data-ttu-id="41a28-241">次の PowerShell コマンドレットを 1 つずつ実行して、ルール パッケージをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="41a28-241">Upload the rule package by running the following PowerShell cmdlets, one at a time:</span></span>

      ```powershell
      $rulepack=Get-Content .\\rulepack.xml -Encoding Byte -ReadCount 0
      New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack
      ```

<span data-ttu-id="41a28-242">この時点で、EDM ベースの分類がセットアップされています。</span><span class="sxs-lookup"><span data-stu-id="41a28-242">At this point, you have set up EDM-based classification.</span></span> <span data-ttu-id="41a28-243">次の手順では、機密データをハッシュして、インデックス用のハッシュをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="41a28-243">The next step is to hash the sensitive data, and then upload the hashes for indexing.</span></span>

<span data-ttu-id="41a28-244">前の手順から PatientRecords スキーマが次の 5 つのフィールドを検索可能として定義していることに注意してください:  *PatientID*、 *MRN*、 *SSN*、 *Phone*、 *DOB*。</span><span class="sxs-lookup"><span data-stu-id="41a28-244">Recall from the previous procedure that our PatientRecords schema defines five fields as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span> <span data-ttu-id="41a28-245">ルール パッケージの例には、これらのフィールドが含まれ、検索可能なフィールドごとに 1 つの  *ExactMatch*  アイテムを含むデータベース スキーマ ファイル (**edm.xml**) を参照します。</span><span class="sxs-lookup"><span data-stu-id="41a28-245">Our example rule package includes those fields and references the database schema file (**edm.xml**), with one *ExactMatch* items per searchable field.</span></span> <span data-ttu-id="41a28-246">次の ExactMatch アイテムを検討してください。</span><span class="sxs-lookup"><span data-stu-id="41a28-246">Consider the following ExactMatch item:</span></span>

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

<span data-ttu-id="41a28-247">この例では、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="41a28-247">In this example, note the following:</span></span>

- <span data-ttu-id="41a28-248">データストア名は、以前に作成した .csv ファイルを参照します ( **datastore = "PatientRecords"**)。</span><span class="sxs-lookup"><span data-stu-id="41a28-248">The dataStore name references the .csv file we created earlier: **dataStore = "PatientRecords"**.</span></span>

- <span data-ttu-id="41a28-249">idMatch 値は、データベース スキーマ ファイルに一覧表示されている検索可能なフィールドを参照します ( **idMatch matches = "SSN"**)。</span><span class="sxs-lookup"><span data-stu-id="41a28-249">The idMatch value references a searchable field that is listed in the database schema file: **idMatch matches = "SSN"**.</span></span>

- <span data-ttu-id="41a28-250">分類の値は、既存またはカスタムの機密情報の種類を参照します ( **分類 = "米国社会保障番号 (SSN)"**)。</span><span class="sxs-lookup"><span data-stu-id="41a28-250">The classification value references an existing or custom sensitive information type: **classification = "U.S. Social Security Number (SSN)"**.</span></span> <span data-ttu-id="41a28-251">(この場合は、既存の機密情報の種類の米国社会保障番号を使用します。)</span><span class="sxs-lookup"><span data-stu-id="41a28-251">(In this case, we use the existing sensitive information type of U.S. Social Security Number.)</span></span>

> [!NOTE]
> <span data-ttu-id="41a28-252">追加機能を使用して EDMSchema を更新するには、10 から 60 分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="41a28-252">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="41a28-253">追加機能を使用する手順を実行する前に、更新プログラムを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41a28-253">The update must complete before you execute steps that use the additions.</span></span>

### <a name="part-2-hash-and-upload-the-sensitive-data"></a><span data-ttu-id="41a28-254">パート 2: 機密データをハッシュしアップロードする</span><span class="sxs-lookup"><span data-stu-id="41a28-254">Part 2: Hash and upload the sensitive data</span></span>

<span data-ttu-id="41a28-255">このフェーズでは、カスタムのセキュリティ グループとユーザー アカウントをセットアップし、EDM Upload Agent ツールをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="41a28-255">During this phase, you set up a custom security group and user account, and set up the EDM Upload Agent tool.</span></span> <span data-ttu-id="41a28-256">次に、このツールを使用して機密データにハッシュして、インデックスが付けられるようにハッシュされたデータをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="41a28-256">Then, you use the tool to hash the sensitive data, and upload the hashed data so it can be indexed.</span></span>

#### <a name="set-up-the-security-group-and-user-account"></a><span data-ttu-id="41a28-257">セキュリティ グループとユーザー アカウントをセットアップする</span><span class="sxs-lookup"><span data-stu-id="41a28-257">Set up the security group and user account</span></span>

1. <span data-ttu-id="41a28-258">全体管理者として、[サブスクリプションに適した リンク](#portal-links-for-your-subscription)を使用して管理センターに移動し、 [セキュリティグループを作成](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) します。 **EDM\_DataUploaders**と言います。</span><span class="sxs-lookup"><span data-stu-id="41a28-258">As a global administrator, go to the admin center using the appropriate [link for your subscription](#portal-links-for-your-subscription) and [create a security group](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) called **EDM\_DataUploaders**.</span></span>

2. <span data-ttu-id="41a28-259"> **EDM\_DataUploaders**  セキュリティ グループに、1 人以上のユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="41a28-259">Add one or more users to the **EDM\_DataUploaders** security group.</span></span> <span data-ttu-id="41a28-260">(これらのユーザーは機密情報のデータベースを管理します)。</span><span class="sxs-lookup"><span data-stu-id="41a28-260">(These users will manage the database of sensitive information.)</span></span>

3. <span data-ttu-id="41a28-261">機密データを管理している各ユーザーが、EDM アップロード エージェントに使用されるコンピューターのローカル管理者であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="41a28-261">Make sure each user who is managing the sensitive data is a local admin on the machine used for the EDM Upload Agent.</span></span>

#### <a name="set-up-the-edm-upload-agent"></a><span data-ttu-id="41a28-262">EDM アップロード エージェントをセットアップする</span><span class="sxs-lookup"><span data-stu-id="41a28-262">Set up the EDM Upload Agent</span></span>

>[!NOTE]
> <span data-ttu-id="41a28-263">この手順を開始する前に、自分が  **EDM\_DataUploaders**  セキュリティ グループのメンバーであり、コンピューターのローカル管理者であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="41a28-263">Before you begin this procedure, make sure that you are a member of the **EDM\_DataUploaders** security group and a local admin on your machine.</span></span>

#### <a name="links-to-edm-upload-agent-by-subscription-type"></a><span data-ttu-id="41a28-264">サブスクリプションの種類別の EDM アップロードエージェントへのリンク</span><span class="sxs-lookup"><span data-stu-id="41a28-264">Links to EDM upload agent by subscription type</span></span>

- [<span data-ttu-id="41a28-265">商用 + GCC</span><span class="sxs-lookup"><span data-stu-id="41a28-265">Commercial + GCC</span></span>](https://go.microsoft.com/fwlink/?linkid=2088639)
- [<span data-ttu-id="41a28-266">GCC-High</span><span class="sxs-lookup"><span data-stu-id="41a28-266">GCC-High</span></span>](https://go.microsoft.com/fwlink/?linkid=2137521)
- [<span data-ttu-id="41a28-267">DoD</span><span class="sxs-lookup"><span data-stu-id="41a28-267">DoD</span></span>](https://go.microsoft.com/fwlink/?linkid=2137807)

1. <span data-ttu-id="41a28-268">サブスクリプションに適した [EDM アップロードエージェント](#links-to-edm-upload-agent-by-subscription-type) をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="41a28-268">Download and install the appropriate [EDM Upload Agent](#links-to-edm-upload-agent-by-subscription-type) for your subscription.</span></span> <span data-ttu-id="41a28-269">既定では、インストール場所は、[ **C:\\Program Files\\Microsoft\\EdmUploadAgent**] になります。</span><span class="sxs-lookup"><span data-stu-id="41a28-269">By default, the installation location should be **C:\\Program Files\\Microsoft\\EdmUploadAgent**.</span></span>

   > [!TIP]
   > <span data-ttu-id="41a28-270">サポートされているコマンド パラメーターから一覧を取得するには、エージェントの引数を実行します。</span><span class="sxs-lookup"><span data-stu-id="41a28-270">To a get a list out of the supported command parameters, run the agent no arguments.</span></span> <span data-ttu-id="41a28-271">たとえば、「EdmUploadAgent.exe」です。</span><span class="sxs-lookup"><span data-stu-id="41a28-271">For example 'EdmUploadAgent.exe'.</span></span>

   > [!NOTE]
   > <span data-ttu-id="41a28-272">EDMUploadAgent を使用して、1日に2回だけ、特定のデータストアにデータをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="41a28-272">You can upload data with the EDMUploadAgent to any given data store only twice per day.</span></span>

2. <span data-ttu-id="41a28-273">EDM アップロード エージェントを承認するには、管理者として Windows コマンド プロンプトを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="41a28-273">To authorize the EDM Upload Agent, open Windows Command Prompt (as an administrator), and then run the following command:</span></span>

   `EdmUploadAgent.exe /Authorize`

3. <span data-ttu-id="41a28-274">EDM_DataUploaders セキュリティグループに追加された、Office 365 の職場または学校のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="41a28-274">Sign in with your work or school account for Office 365 that was added to the EDM_DataUploaders security group.</span></span>

<span data-ttu-id="41a28-275">次の手順では、EDM アップロード エージェントを使用して機密データにハッシュし、ハッシュされたデータをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="41a28-275">The next step is to use the EDM Upload Agent to hash the sensitive data, and then upload the hashed data.</span></span>

#### <a name="hash-and-upload-the-sensitive-data"></a><span data-ttu-id="41a28-276">機密データをハッシュしアップロードする</span><span class="sxs-lookup"><span data-stu-id="41a28-276">Hash and upload the sensitive data</span></span>

<span data-ttu-id="41a28-277">機密データ ファイル (この例では  **PatientRecords.csv**) をコンピューターのローカル ドライブに保存します。</span><span class="sxs-lookup"><span data-stu-id="41a28-277">Save the sensitive data file (recall our example is **PatientRecords.csv**) to the local drive on the machine.</span></span> <span data-ttu-id="41a28-278">(例の  **PatientRecords.csv**  ファイルを  **C:\\Edm\\Data** に保存しました。)</span><span class="sxs-lookup"><span data-stu-id="41a28-278">(We saved our example **PatientRecords.csv** file to **C:\\Edm\\Data**.)</span></span>

<span data-ttu-id="41a28-279">機密データにインデックスを付けてアップロートするには、Windows コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="41a28-279">To hash and upload the sensitive data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /UploadData /DataStoreName \<DataStoreName\> /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="41a28-280">例: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\\Edm\\Hash\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span><span class="sxs-lookup"><span data-stu-id="41a28-280">Example: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\\Edm\\Hash\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span></span>

<span data-ttu-id="41a28-281">分離された環境で機密データのハッシュを分離して実行するには、ハッシュを実行し、手順を個別にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="41a28-281">To separate and execute the hashing of sensitive data in an isolated environment, execute the hashing and upload steps separately.</span></span>

<span data-ttu-id="41a28-282">機密データをハッシュするには、Windows コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="41a28-282">To hash the sensitive data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /CreateHash /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="41a28-283">例:</span><span class="sxs-lookup"><span data-stu-id="41a28-283">For example:</span></span>

> <span data-ttu-id="41a28-284">**EdmUploadAgent.exe /CreateHash /DataFile C:\\Edm\\Data\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span><span class="sxs-lookup"><span data-stu-id="41a28-284">**EdmUploadAgent.exe /CreateHash /DataFile C:\\Edm\\Data\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span></span>

<span data-ttu-id="41a28-285">ハッシュされたデータをアップロードするには、Windows コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="41a28-285">To upload the hashed data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\>`

<span data-ttu-id="41a28-286">例:</span><span class="sxs-lookup"><span data-stu-id="41a28-286">For example:</span></span>

> <span data-ttu-id="41a28-287">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span><span class="sxs-lookup"><span data-stu-id="41a28-287">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span></span>


<span data-ttu-id="41a28-288">機密データがアップロードされたことを確認するには、コマンド プロンプト ウィンドウで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="41a28-288">To verify that your sensitive data has been uploaded, run the following command in Command Prompt window:</span></span>


`EdmUploadAgent.exe /GetDataStore`

<span data-ttu-id="41a28-289">データ ストアのリストと、それらが最後に更新された日時が表示されます。</span><span class="sxs-lookup"><span data-stu-id="41a28-289">You'll see a list of data stores and when they were last updated.</span></span>

<span data-ttu-id="41a28-290">特定のストアへのデータのアップロードをすべて表示する場合は、Windows コマンドプロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="41a28-290">If you want to see all the data uploads to a particular store, run the following command in a Windows command prompt:</span></span>

`EdmUploadAgent.exe /GetSession /DataStoreName <DataStoreName>`

<span data-ttu-id="41a28-291"> [機密情報データベースを更新する](#refreshing-your-sensitive-information-database)ためのプロセスとスケジュールのセットアップを進めます。</span><span class="sxs-lookup"><span data-stu-id="41a28-291">Proceed to set up your process and schedule for [Refreshing your sensitive information database](#refreshing-your-sensitive-information-database).</span></span>

<span data-ttu-id="41a28-292">この時点で、Microsoft クラウド サービスで EDM ベースの分類を使用する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="41a28-292">At this point, you are ready to use EDM-based classification with your Microsoft cloud services.</span></span> <span data-ttu-id="41a28-293">たとえば、 [EDM ベースの分類を使用して DLP ポリシーを設定](#to-create-a-dlp-policy-with-edm)できます。</span><span class="sxs-lookup"><span data-stu-id="41a28-293">For example, you can [set up a DLP policy using EDM-based classification](#to-create-a-dlp-policy-with-edm).</span></span>

#### <a name="refreshing-your-sensitive-information-database"></a><span data-ttu-id="41a28-294">機密情報データベースを更新する</span><span class="sxs-lookup"><span data-stu-id="41a28-294">Refreshing your sensitive information database</span></span>

<span data-ttu-id="41a28-295">機密情報データベースは毎日または毎週更新できます。また、EDM アップロード ツールを使用して機密データを再ハッシュしてから、ハッシュされたデータを再アップロードできます。</span><span class="sxs-lookup"><span data-stu-id="41a28-295">You can refresh your sensitive information database daily or weekly, and the EDM Upload Tool can re-hash the sensitive data and then reupload the hashed data.</span></span>

1. <span data-ttu-id="41a28-296">機密情報のデータベースを更新するためのプロセスと頻度 (毎日または毎週) を決定します。</span><span class="sxs-lookup"><span data-stu-id="41a28-296">Determine your process and frequency (daily or weekly) for refreshing the database of sensitive information.</span></span>

2. <span data-ttu-id="41a28-297">機密情報データを Microsoft Excel などのアプリに再度エクスポートし、ファイルを .csv 形式で保存します。</span><span class="sxs-lookup"><span data-stu-id="41a28-297">Re-export the sensitive data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="41a28-298">「 [機密データをハッシュしアップロードする](#hash-and-upload-the-sensitive-data)」で説明した手順の実行時に使用したファイル名と場所と同じものを使用してください。</span><span class="sxs-lookup"><span data-stu-id="41a28-298">Keep the same file name and location you used when you followed the steps described in [Hash and upload the sensitive data](#hash-and-upload-the-sensitive-data).</span></span>

      > [!NOTE]
      > <span data-ttu-id="41a28-299">.csv ファイルの構造 (フィールド名) に変更がない場合は、データを更新する際に、データベース スキーマ ファイルを変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="41a28-299">If there are no changes to the structure (field names) of the .csv file, you won't need to make any changes to your database schema file when you refresh the data.</span></span> <span data-ttu-id="41a28-300">ただし、変更が必要な場合は、必要に応じてデータベース スキーマとルール パッケージを編集してください。</span><span class="sxs-lookup"><span data-stu-id="41a28-300">But if you must make changes, make sure to edit the database schema and your rule package accordingly.</span></span>

3. <span data-ttu-id="41a28-301"> [タスク スケジューラ](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) を使用して、 [機密データをハッシュしアップロードする](#hash-and-upload-the-sensitive-data)  手順の、手順 2 と 3 を自動化します。</span><span class="sxs-lookup"><span data-stu-id="41a28-301">Use [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) to automate steps 2 and 3 in the [Hash and upload the sensitive data](#hash-and-upload-the-sensitive-data) procedure.</span></span> <span data-ttu-id="41a28-302">タスクのスケジュールを設定するにはいくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="41a28-302">You can schedule tasks using several methods:</span></span>

      | <span data-ttu-id="41a28-303">メソッド</span><span class="sxs-lookup"><span data-stu-id="41a28-303">Method</span></span>             | <span data-ttu-id="41a28-304">操作</span><span class="sxs-lookup"><span data-stu-id="41a28-304">What to do</span></span> |
      | ---------------------- | ---------------- |
      | <span data-ttu-id="41a28-305">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="41a28-305">Windows PowerShell</span></span>     | <span data-ttu-id="41a28-306"> [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) のドキュメントと、この記事の  [PowerShell スクリプトの例](#example-powershell-script-for-task-scheduler) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41a28-306">See the [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) documentation and the [example PowerShell script](#example-powershell-script-for-task-scheduler) in this article</span></span> |
      | <span data-ttu-id="41a28-307">タスク スケジューラ API</span><span class="sxs-lookup"><span data-stu-id="41a28-307">Task Scheduler API</span></span>     | <span data-ttu-id="41a28-308"> [タスク スケジューラ](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) ドキュメントを参照してください</span><span class="sxs-lookup"><span data-stu-id="41a28-308">See the [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) documentation</span></span>                                                                                                                                                                                                                                                                                |
      | <span data-ttu-id="41a28-309">Windows のユーザー インターフェイス</span><span class="sxs-lookup"><span data-stu-id="41a28-309">Windows user interface</span></span> | <span data-ttu-id="41a28-310">Windows の場合、 **[スタート]** をクリックし、「タスクスケジューラ」と入力します。</span><span class="sxs-lookup"><span data-stu-id="41a28-310">In Windows, click **Start**, and type Task Scheduler.</span></span> <span data-ttu-id="41a28-311">次に、結果のリストで  **[タスク スケジューラ]** を右クリックし、 **[管理者として実行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="41a28-311">Then, in the list of results, right-click **Task Scheduler**, and choose **Run as administrator**.</span></span>                                                                                                                                                                                                                                                                           |

#### <a name="example-powershell-script-for-task-scheduler"></a><span data-ttu-id="41a28-312">タスク スケジューラの PowerShell スクリプトの例</span><span class="sxs-lookup"><span data-stu-id="41a28-312">Example PowerShell script for Task Scheduler</span></span>

<span data-ttu-id="41a28-313">このセクションには、データをハッシュしたり、ハッシュされたデータをアップロードするタスクのスケジュールに使用できる PowerShell スクリプトの例が含まれています。</span><span class="sxs-lookup"><span data-stu-id="41a28-313">This section includes an example PowerShell script you can use to schedule your tasks for hashing data and uploading the hashed data:</span></span>

##### <a name="to-schedule-hashing-and-upload-in-a-combined-step"></a><span data-ttu-id="41a28-314">ハッシュのスケジュールを設定して、結合されたステップでアップロードするには</span><span class="sxs-lookup"><span data-stu-id="41a28-314">To schedule hashing and upload in a combined step</span></span>

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

#### <a name="to-schedule-hashing-and-upload-as-separate-steps"></a><span data-ttu-id="41a28-315">ハッシュのスケジュールを設定して、結合されたステップでアップロードするには</span><span class="sxs-lookup"><span data-stu-id="41a28-315">To schedule hashing and upload as separate steps</span></span>

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

### <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a><span data-ttu-id="41a28-316">パート 3: Microsoft クラウド サービスで EDM ベースの分類を使用する</span><span class="sxs-lookup"><span data-stu-id="41a28-316">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>

<span data-ttu-id="41a28-317">これらの場所が、EDM の機密情報の種類をサポートしています:</span><span class="sxs-lookup"><span data-stu-id="41a28-317">These locations are support EDM sensitive information types:</span></span>

- <span data-ttu-id="41a28-318">DLP for Exchange Online (メール)</span><span class="sxs-lookup"><span data-stu-id="41a28-318">DLP for Exchange Online (email)</span></span>
- <span data-ttu-id="41a28-319">OneDrive for Business (ファイル)</span><span class="sxs-lookup"><span data-stu-id="41a28-319">OneDrive for Business (files)</span></span>
- <span data-ttu-id="41a28-320">Microsoft Teams (会話)</span><span class="sxs-lookup"><span data-stu-id="41a28-320">Microsoft Teams (conversations)</span></span>
- <span data-ttu-id="41a28-321">DLP for SharePoint (ファイル)</span><span class="sxs-lookup"><span data-stu-id="41a28-321">DLP for SharePoint (files)</span></span>
- <span data-ttu-id="41a28-322">Microsoft Cloud App Security DLP ポリシー</span><span class="sxs-lookup"><span data-stu-id="41a28-322">Microsoft Cloud App Security DLP policies</span></span>

<span data-ttu-id="41a28-323">次のシナリオでは、EDM の機密情報の種類は現在開発中で、まだご利用いただけません。</span><span class="sxs-lookup"><span data-stu-id="41a28-323">EDM sensitive information types for following scenarios are currently in development, but not yet available:</span></span>

- <span data-ttu-id="41a28-324">機密度ラベルと保持ラベルの自動分類</span><span class="sxs-lookup"><span data-stu-id="41a28-324">Auto-classification of sensitivity labels and retention labels</span></span>

#### <a name="to-create-a-dlp-policy-with-edm"></a><span data-ttu-id="41a28-325">EDM を使用して DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="41a28-325">To create a DLP policy with EDM</span></span>

1. <span data-ttu-id="41a28-326">[サブスクリプションに適切なリンク](#portal-links-for-your-subscription)を使用して、セキュリティ/コンプライアンス センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="41a28-326">Go to the Security & Compliance Center using the appropriate [link for your subscription](#portal-links-for-your-subscription).</span></span>

2. <span data-ttu-id="41a28-327"> **[データ損失防止]** \> **[ポリシー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="41a28-327">Choose **Data loss prevention** \> **Policy**.</span></span>

3. <span data-ttu-id="41a28-328"> **[ポリシーの作成]** \> **[カスタム]** \> **[次へ]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="41a28-328">Choose **Create a policy** \> **Custom** \> **Next**.</span></span>

4. <span data-ttu-id="41a28-329"> **[ポリシーの名前を設定]**  タブで名前と説明を指定し、 **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="41a28-329">On the **Name your policy** tab, specify a name and description, and then choose **Next**.</span></span>

5. <span data-ttu-id="41a28-330"> **[場所の選択]**  タブで、 **[特定の場所を選択]** し、 **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="41a28-330">On the **Choose locations** tab, select **Let me choose specific locations**, and then choose **Next**.</span></span>

6. <span data-ttu-id="41a28-331"> **[状態]** の列で、 **Exchange メール、OneDrive アカウント、Teams チャット、チャネル メッセージ** を選択し、 **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="41a28-331">In the **Status** column, select **Exchange email, OneDrive accounts, Teams chat and channel message** , and then choose **Next**.</span></span>

7. <span data-ttu-id="41a28-332"> **[ポリシーの設定]**  タブで、 **[詳細設定を使用]** を選択し、 **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="41a28-332">On the **Policy settings** tab, choose **Use advanced settings**, and then choose **Next**.</span></span>

8. <span data-ttu-id="41a28-333"> **[+ 新しいルール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="41a28-333">Choose **+ New rule**.</span></span>

9. <span data-ttu-id="41a28-334"> **[名前]**  セクションで、ルールの名前と説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="41a28-334">In the **Name** section, specify a name and description for the rule.</span></span>

10. <span data-ttu-id="41a28-335"> **[条件]**  セクションの、 **[+ 条件の追加]**  リストで、 **[機密情報の種類を含むコンテンツ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="41a28-335">In the **Conditions** section, in the **+ Add a condition** list, choose **Content contains sensitive type**.</span></span>

      ![機密情報の種類を含むコンテンツ](../media/edm-dlp-newrule-conditions.png)

11. <span data-ttu-id="41a28-337">ルール パッケージのセットアップ時に作成した機密情 報の種類を検索し、 **[+ 追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="41a28-337">Search for the sensitive information type you created when you set up your rule package, and then choose **+ Add**.</span></span>  
    <span data-ttu-id="41a28-338"> **[完了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="41a28-338">Then choose **Done**.</span></span>

12. <span data-ttu-id="41a28-339">ルールのオプション ( **[ユーザー通知]**、 **[ユーザーによる上書き]**、 **[インシデント レポート]** など) の選択を終了し、 **[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="41a28-339">Finish selecting options for your rule, such as **User notifications**, **User overrides**, **Incident reports**, and so on, and then choose **Save**.</span></span>

13. <span data-ttu-id="41a28-340"> **[ポリシーの設定]**  タブでルールを確認し、 **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="41a28-340">On the **Policy settings** tab, review your rules, and then choose **Next**.</span></span>

14. <span data-ttu-id="41a28-341">ポリシーをすぐに有効にするか、テストするか、無効にするかを指定します。</span><span class="sxs-lookup"><span data-stu-id="41a28-341">Specify whether to turn on the policy right away, test it out, or keep it turned off.</span></span> <span data-ttu-id="41a28-342"> **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="41a28-342">Then choose **Next**.</span></span>

15. <span data-ttu-id="41a28-343"> **[設定を確認]**  タブで、ポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="41a28-343">On the **Review your settings** tab, review your policy.</span></span> <span data-ttu-id="41a28-344">必要な変更を行います。</span><span class="sxs-lookup"><span data-stu-id="41a28-344">Make any needed changes.</span></span> <span data-ttu-id="41a28-345">準備ができたら  **[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="41a28-345">When you're ready, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="41a28-346">新しい DLP ポリシーがデータ センターを通過するまでに、約 1 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="41a28-346">Allow approximately one hour for your new DLP policy to work its way through your data center.</span></span>

## <a name="related-articles"></a><span data-ttu-id="41a28-347">関連記事</span><span class="sxs-lookup"><span data-stu-id="41a28-347">Related articles</span></span>

- [<span data-ttu-id="41a28-348">機密情報の種類のエンティティ定義</span><span class="sxs-lookup"><span data-stu-id="41a28-348">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="41a28-349">カスタムの機密情報の種類</span><span class="sxs-lookup"><span data-stu-id="41a28-349">Custom sensitive information types</span></span>](custom-sensitive-info-types.md)
- [<span data-ttu-id="41a28-350">DLP ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="41a28-350">Overview of DLP policies</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="41a28-351">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="41a28-351">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)
- [<span data-ttu-id="41a28-352">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="41a28-352">New-DlpEdmSchema</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-dlpedmschema?view=exchange-ps)

