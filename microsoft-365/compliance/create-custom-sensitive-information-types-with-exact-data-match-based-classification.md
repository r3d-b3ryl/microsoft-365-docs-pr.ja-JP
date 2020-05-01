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
description: Exact Data Match に基づく分類を使って、カスタムの機密情報の種類を作成します。
ms.openlocfilehash: d234b4c9ba01b185c367074ee78b0f92be226c46
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2020
ms.locfileid: "43938617"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification"></a><span data-ttu-id="260d1-103">Exact Data Match に基づく分類で、カスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="260d1-103">Create custom sensitive information types with Exact Data Match based classification</span></span>

## <a name="overview"></a><span data-ttu-id="260d1-104">概要</span><span class="sxs-lookup"><span data-stu-id="260d1-104">Overview</span></span>

<span data-ttu-id="260d1-105">[カスタムの機密情報の種類](custom-sensitive-info-types.md) は、機密情報の不注意または不適切な共有を防ぐために使用されます。</span><span class="sxs-lookup"><span data-stu-id="260d1-105">[Custom sensitive information types](custom-sensitive-info-types.md) are used to help prevent inadvertent or inappropriate sharing of sensitive information.</span></span> <span data-ttu-id="260d1-106">管理者は  [セキュリティー/コンプライアンス センター](create-a-custom-sensitive-information-type.md) または [PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md)  を使用して、パターン、証拠 ( *従業員*、 *バッジ*、 *ID*などのキーワード)、文字の近接性 (特定のパターンの文字に証拠がどれほど近接しているか)、および信頼レベルに基づいてカスタムの機密情報の種類を定義できます。</span><span class="sxs-lookup"><span data-stu-id="260d1-106">As an administrator, you can use the [Security & Compliance Center](create-a-custom-sensitive-information-type.md) or [PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md) to define a custom sensitive information type based on patterns, evidence (keywords such as *employee*, *badge*, *ID*, and so on), character proximity (how close evidence is to characters in a particular pattern), and confidence levels.</span></span> <span data-ttu-id="260d1-107">このようなカスタムの機密情報の種類は、多くの組織のビジネス ニーズを満たします。</span><span class="sxs-lookup"><span data-stu-id="260d1-107">Such custom sensitive information types meet business needs for many organizations.</span></span>

<span data-ttu-id="260d1-108">しかし、汎用的なパターンのみを使用するのではなく、正確なデータ値を使用するカスタムの機密情報の種類が必要な場合はどうでしょう。</span><span class="sxs-lookup"><span data-stu-id="260d1-108">But what if you wanted a custom sensitive information type that uses exact data values, instead of matching only with generic patterns?</span></span> <span data-ttu-id="260d1-109">Exact Data Match (EDM) ベースの分類では、次の目的で設計されたカスタムの機密情報の種類を作成できます。</span><span class="sxs-lookup"><span data-stu-id="260d1-109">With Exact Data Match (EDM)-based classification, you can create a custom sensitive information type that is designed to:</span></span>

- <span data-ttu-id="260d1-110">動的で更新可能なものにする。</span><span class="sxs-lookup"><span data-stu-id="260d1-110">be dynamic and refreshable;</span></span>
- <span data-ttu-id="260d1-111">拡張性の高いものにする。</span><span class="sxs-lookup"><span data-stu-id="260d1-111">be more scalable;</span></span>
- <span data-ttu-id="260d1-112">結果的に誤検知数を減らす。</span><span class="sxs-lookup"><span data-stu-id="260d1-112">result in fewer false-positives;</span></span>
- <span data-ttu-id="260d1-113">構造化された機密データを操作する。</span><span class="sxs-lookup"><span data-stu-id="260d1-113">work with structured sensitive data;</span></span>
- <span data-ttu-id="260d1-114">機密情報をより安全に処理する。</span><span class="sxs-lookup"><span data-stu-id="260d1-114">handle sensitive information more securely; and</span></span>
- <span data-ttu-id="260d1-115">さまざまな Microsoft クラウド サービスで使用する。</span><span class="sxs-lookup"><span data-stu-id="260d1-115">be used with several Microsoft cloud services.</span></span>

![EDM ベースの分類](../media/EDMClassification.png)

<span data-ttu-id="260d1-117">EDM ベースの分類を使用すると、機密情報のデータベース内の正確な値を参照する、カスタムの機密情報の種類を作成できます。</span><span class="sxs-lookup"><span data-stu-id="260d1-117">EDM-based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="260d1-118">データベースは毎日、または毎週更新できます。また、最大 1000 万行のデータを格納できます。</span><span class="sxs-lookup"><span data-stu-id="260d1-118">The database can be refreshed daily or weekly, and it can contain up to 10 million rows of data.</span></span> <span data-ttu-id="260d1-119">そのため、従業員、患者、または顧客の出入りに合わせて記録が変更されても、カスタムの機密情報の種類は最新の状態が維持されます。</span><span class="sxs-lookup"><span data-stu-id="260d1-119">So as employees, patients, or clients come and go, and records change, your custom sensitive information types remain current and applicable.</span></span> <span data-ttu-id="260d1-120">また、EDM ベースの分類は、 [データ損失防止ポリシー](data-loss-prevention-policies.md) (DLP) や [Microsoft Cloud App Security ファイル ポリシー](https://docs.microsoft.com/cloud-app-security/data-protection-policies) などのポリシーと共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="260d1-120">And, you can use EDM-based classification with policies, such as [data loss prevention policies](data-loss-prevention-policies.md) (DLP) or [Microsoft Cloud App Security file policies](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="260d1-121">必要なライセンスとアクセス許可</span><span class="sxs-lookup"><span data-stu-id="260d1-121">Required licenses and permissions</span></span>

<span data-ttu-id="260d1-122">この記事で説明されているタスクを実行するには、全体管理者、コンプライアンス管理者、または Exchange Online の管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="260d1-122">You must be a global admin, compliance administrator, or Exchange Online administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="260d1-123">DLP アクセス許可の詳細については、「 [アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="260d1-123">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="260d1-124">一般公開されると、EDM ベースの分類は次のサブスクリプションに含まれます。</span><span class="sxs-lookup"><span data-stu-id="260d1-124">When generally available, EDM-based classification will be included in these subscriptions</span></span>

- <span data-ttu-id="260d1-125">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="260d1-125">Office 365 E5</span></span>
- <span data-ttu-id="260d1-126">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="260d1-126">Microsoft 365 E5</span></span>
- <span data-ttu-id="260d1-127">Microsoft 365 E5 Compliance </span><span class="sxs-lookup"><span data-stu-id="260d1-127">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="260d1-128">Microsoft E5/A5 Information Protection and Governance</span><span class="sxs-lookup"><span data-stu-id="260d1-128">Microsoft E5/A5 Information Protection and Governance</span></span>

## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="260d1-129">ワークフローの概要</span><span class="sxs-lookup"><span data-stu-id="260d1-129">The work flow at a glance</span></span>

|<span data-ttu-id="260d1-130">フェーズ</span><span class="sxs-lookup"><span data-stu-id="260d1-130">Phase</span></span>  |<span data-ttu-id="260d1-131">前提条件</span><span class="sxs-lookup"><span data-stu-id="260d1-131">What's needed</span></span>  |
|---------|---------|
|[<span data-ttu-id="260d1-132">パート 1: EDM ベースの分類をセットアップする</span><span class="sxs-lookup"><span data-stu-id="260d1-132">Part 1: Set up EDM-based classification</span></span>](#part-1-set-up-edm-based-classification)<br/><br/><span data-ttu-id="260d1-133">(適宜)</span><span class="sxs-lookup"><span data-stu-id="260d1-133">(As needed)</span></span><br/><span data-ttu-id="260d1-134">- [データベーススキーマを編集する](#editing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="260d1-134">- [Edit the database schema](#editing-the-schema-for-edm-based-classification)</span></span> <br/><span data-ttu-id="260d1-135">- [スキーマを削除する](#removing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="260d1-135">- [Remove the schema](#removing-the-schema-for-edm-based-classification)</span></span> |<span data-ttu-id="260d1-136">- 機密データへの読み取りアクセス</span><span class="sxs-lookup"><span data-stu-id="260d1-136">- Read access to the sensitive data</span></span><br/><span data-ttu-id="260d1-137">- .xml 形式のデータベース スキーマ (例を提供)</span><span class="sxs-lookup"><span data-stu-id="260d1-137">- Database schema in .xml format (example provided)</span></span><br/><span data-ttu-id="260d1-138">- .xml 形式のルールパッケージ (例を提供)</span><span class="sxs-lookup"><span data-stu-id="260d1-138">- Rule package in .xml format (example provided)</span></span><br/><span data-ttu-id="260d1-139">- セキュリティ/コンプライアンス センターへの管理者権限 (PowerShell を使用)</span><span class="sxs-lookup"><span data-stu-id="260d1-139">- Admin permissions to the Security & Compliance Center (using PowerShell)</span></span> |
|[<span data-ttu-id="260d1-140">パート 2: 機密データのインデックスを作成しアップロードする</span><span class="sxs-lookup"><span data-stu-id="260d1-140">Part 2: Index and upload the sensitive data</span></span>](#part-2-index-and-upload-the-sensitive-data)<br/><br/><span data-ttu-id="260d1-141">(適宜)</span><span class="sxs-lookup"><span data-stu-id="260d1-141">(As needed)</span></span><br/>[<span data-ttu-id="260d1-142">データを更新する</span><span class="sxs-lookup"><span data-stu-id="260d1-142">Refresh the data</span></span>](#refreshing-your-sensitive-information-database) |<span data-ttu-id="260d1-143">- カスタムのセキュリティ グループとユーザー アカウント</span><span class="sxs-lookup"><span data-stu-id="260d1-143">- Custom security group and user account</span></span><br/><span data-ttu-id="260d1-144">- EDM アップロード エージェントを使用するコンピューターへのローカル管理者アクセス</span><span class="sxs-lookup"><span data-stu-id="260d1-144">- Local admin access to machine with EDM Upload Agent</span></span><br/><span data-ttu-id="260d1-145">- 機密データへの読み取りアクセス</span><span class="sxs-lookup"><span data-stu-id="260d1-145">- Read access to the sensitive data</span></span><br/><span data-ttu-id="260d1-146">- データ更新のプロセスとスケジュール</span><span class="sxs-lookup"><span data-stu-id="260d1-146">- Process and schedule for refreshing the data</span></span>|
|[<span data-ttu-id="260d1-147">パート 3: Microsoft クラウド サービスで EDM ベースの分類を使用する</span><span class="sxs-lookup"><span data-stu-id="260d1-147">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services) |<span data-ttu-id="260d1-148">- DLP を使用する Microsoft 365 サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="260d1-148">- Microsoft 365 subscription with DLP</span></span><br/><span data-ttu-id="260d1-149">- 有効化された EDM ベースの分類機能</span><span class="sxs-lookup"><span data-stu-id="260d1-149">- EDM-based classification feature enabled</span></span> |

### <a name="part-1-set-up-edm-based-classification"></a><span data-ttu-id="260d1-150">パート 1: EDM ベースの分類をセットアップする</span><span class="sxs-lookup"><span data-stu-id="260d1-150">Part 1: Set up EDM-based classification</span></span>

<span data-ttu-id="260d1-151">EDM ベースの分類をセットアップおよび構成するには、機密データを .csv 形式で保存し、機密情報のデータベースのスキーマを定義して、ルール パッケージを作成し、スキーマとルール パッケージをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="260d1-151">Setting up and configuring EDM-based classification involves saving sensitive data in .csv format, defining a schema for your database of sensitive information, creating a rule package, and then uploading the schema and rule package.</span></span>

#### <a name="define-the-schema-for-your-database-of-sensitive-information"></a><span data-ttu-id="260d1-152">機密情報のデータベースのスキーマを定義する</span><span class="sxs-lookup"><span data-stu-id="260d1-152">Define the schema for your database of sensitive information</span></span>

1. <span data-ttu-id="260d1-153">使用する機密情報を特定します。</span><span class="sxs-lookup"><span data-stu-id="260d1-153">Identify the sensitive information you want to use.</span></span> <span data-ttu-id="260d1-154">データを Microsoft Excel などのアプリにエクスポートし、ファイルを .csv 形式で保存します。</span><span class="sxs-lookup"><span data-stu-id="260d1-154">Export the data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="260d1-155">データ ファイルには、次のデータを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="260d1-155">The data file can include a maximum of:</span></span>
      - <span data-ttu-id="260d1-156">最大 1,000 万行の機密データ</span><span class="sxs-lookup"><span data-stu-id="260d1-156">Up to 10 million rows of sensitive data</span></span>
      - <span data-ttu-id="260d1-157">データ ソースごとに最大 32 列 (フィールド)</span><span class="sxs-lookup"><span data-stu-id="260d1-157">Up to 32 columns (fields) per data source</span></span>
      - <span data-ttu-id="260d1-158">検索可能としてマークされた列 (フィールド) を最大 5 列</span><span class="sxs-lookup"><span data-stu-id="260d1-158">Up to 5 columns (fields) marked as searchable</span></span>

2. <span data-ttu-id="260d1-159">EDM ベースの分類に使用されるフィールドの名前が 1 行目に含まれるように、.csv ファイル内の機密データを構成します。</span><span class="sxs-lookup"><span data-stu-id="260d1-159">Structure the sensitive data in the .csv file such that the first row includes the names of the fields used for EDM-based classification.</span></span> <span data-ttu-id="260d1-160">.csv ファイルには、"ssn"、"birthdate"、"firstname"、"lastname" などのフィールド名があります。</span><span class="sxs-lookup"><span data-stu-id="260d1-160">In your .csv file, you might have field names, such as "ssn", "birthdate", "firstname", "lastname", and so on.</span></span> <span data-ttu-id="260d1-161">列見出しに、名前にスペースまたはアンダースコアを含めることはできませんのでご了承ください。</span><span class="sxs-lookup"><span data-stu-id="260d1-161">Please note that column headers can't include spaces or underscores in their names.</span></span> <span data-ttu-id="260d1-162">たとえば、 csv ファイルは *PatientRecords.csv*と呼ばれており、その列には *PatientID*、 *MRN*、 *LastName*、 *FirstName*、 *SSN*などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="260d1-162">As an example, our .csv file is called *PatientRecords.csv*, and its columns include *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN*, and more.</span></span>

3. <span data-ttu-id="260d1-163">機密情報のデータベースのスキーマを .xml 形式で定義します (次の例と同様)。</span><span class="sxs-lookup"><span data-stu-id="260d1-163">Define the schema for the database of sensitive information in .xml format (similar to our example below).</span></span> <span data-ttu-id="260d1-164">このスキーマ ファイルの名前を  **edm.xml** にして、データベースの各列に対して構文を使用する行があるように構成します。</span><span class="sxs-lookup"><span data-stu-id="260d1-164">Name this schema file **edm.xml**, and configure it such that for each column in the database, there is a line that uses the syntax:</span></span> 

      <span data-ttu-id="260d1-165">`\<Field name="" searchable=""/\>`</span><span class="sxs-lookup"><span data-stu-id="260d1-165">`\<Field name="" searchable=""/\>`.</span></span>

      - <span data-ttu-id="260d1-166"> *Field name*  の値に列名を使用します。</span><span class="sxs-lookup"><span data-stu-id="260d1-166">Use column names for *Field name* values.</span></span>
      - <span data-ttu-id="260d1-167"> *searchable="true"*  を使用して、最大 5 つのフィールドで検索可能にします。</span><span class="sxs-lookup"><span data-stu-id="260d1-167">Use *searchable="true"* for the fields that you want to be searchable up to a maximum of 5 fields.</span></span> <span data-ttu-id="260d1-168">少なくとも 1 つのフィールドを検索可能に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="260d1-168">You must designate a minimum of one field as searchable.</span></span>

      <span data-ttu-id="260d1-169">たとえば、次の .xml ファイルは患者の記録のデータベースのスキーマを定義します。検索可能として指定された 5 つのフィールドは、 *PatientID*、 *MRN*、 *SSN*、 *Phone*、 *DOB* です。</span><span class="sxs-lookup"><span data-stu-id="260d1-169">As an example, the following .xml file defines the schema for a patient records database, with five fields specified as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span>

      <span data-ttu-id="260d1-170">(この例は、コピー、変更、使用することができます。)</span><span class="sxs-lookup"><span data-stu-id="260d1-170">(You can copy, modify, and use our example.)</span></span>

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

4. <span data-ttu-id="260d1-171">[セキュリティ/コンプライアンス センター PowerShell に接続します](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="260d1-171">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

5. <span data-ttu-id="260d1-172">データベース スキーマをアップロードするには、次のコマンドレットを 1 つずつ実行します。</span><span class="sxs-lookup"><span data-stu-id="260d1-172">To upload the database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="260d1-173">次のように、確認を求められます。</span><span class="sxs-lookup"><span data-stu-id="260d1-173">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="260d1-174">確認</span><span class="sxs-lookup"><span data-stu-id="260d1-174">Confirm</span></span>
      >
      > <span data-ttu-id="260d1-175">この操作を実行しますか?</span><span class="sxs-lookup"><span data-stu-id="260d1-175">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="260d1-176">データストア ' patientrecords ' の新しい EDM スキーマがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="260d1-176">New EDM Schema for the data store 'patientrecords' will be imported.</span></span>
      >
      > <span data-ttu-id="260d1-177">\[Y\] Yes \[A\] すべて Yes \[N\] No \[L\] すべて No \[?\] ヘルプ (規定値は "Y"):</span><span class="sxs-lookup"><span data-stu-id="260d1-177">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
> <span data-ttu-id="260d1-178">確認なしで変更を行う場合は、手順 5 で次のコマンドレットを代わりに使用します: New-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="260d1-178">If you want your changes to occur without confirmation, in Step 5, use this cmdlet instead: New-DlpEdmSchema -FileData $edmSchemaXml</span></span>

> [!NOTE]
> <span data-ttu-id="260d1-179">追加機能を使用して EDMSchema を更新するには、10 から 60 分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="260d1-179">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="260d1-180">追加機能を使用する手順を実行する前に、更新プログラムを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="260d1-180">The update must complete before you execute steps that use the additions.</span></span>

<span data-ttu-id="260d1-181">機密情報のデータベースのスキーマが定義されたので、次はルール パッケージをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="260d1-181">Now that the schema for your database of sensitive information is defined, the next step is to set up a rule package.</span></span> <span data-ttu-id="260d1-182">セクション「 [ルール パッケージのセットアップ](#set-up-a-rule-package)」に進みます。</span><span class="sxs-lookup"><span data-stu-id="260d1-182">Proceed to the section [Set up a rule package](#set-up-a-rule-package).</span></span>

#### <a name="editing-the-schema-for-edm-based-classification"></a><span data-ttu-id="260d1-183">EDM ベースの分類のスキーマを編集する</span><span class="sxs-lookup"><span data-stu-id="260d1-183">Editing the schema for EDM-based classification</span></span>

<span data-ttu-id="260d1-184">EDM ベースの分類に使用するフィールドの変更など、**edm.xml** ファイルを変更する場合は、次の手順に従います:</span><span class="sxs-lookup"><span data-stu-id="260d1-184">If you want to make changes to your **edm.xml** file, such as changing which fields are used for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="260d1-185">**edm.mxl** ファイルを編集します (これは、この記事の「 [スキーマを定義する](#define-the-schema-for-your-database-of-sensitive-information) 」セクションで説明したファイルです)。</span><span class="sxs-lookup"><span data-stu-id="260d1-185">Edit your **edm.xml** file (this is the file discussed in the [Define the schema](#define-the-schema-for-your-database-of-sensitive-information) section of this article).</span></span>

2. <span data-ttu-id="260d1-186">[セキュリティ/コンプライアンス センター PowerShell に接続します](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="260d1-186">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

3. <span data-ttu-id="260d1-187">データベース スキーマを更新するには、次のコマンドレットを 1 つずつ実行します。</span><span class="sxs-lookup"><span data-stu-id="260d1-187">To update your database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="260d1-188">次のように、確認を求められます。</span><span class="sxs-lookup"><span data-stu-id="260d1-188">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="260d1-189">確認</span><span class="sxs-lookup"><span data-stu-id="260d1-189">Confirm</span></span>
      >
      > <span data-ttu-id="260d1-190">この操作を実行しますか?</span><span class="sxs-lookup"><span data-stu-id="260d1-190">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="260d1-191">データストア ' patientrecords ' の EDM スキーマが更新されます。</span><span class="sxs-lookup"><span data-stu-id="260d1-191">EDM Schema for the data store 'patientrecords' will be updated.</span></span>
      >
      > <span data-ttu-id="260d1-192">\[Y\] Yes \[A\] すべて Yes \[N\] No \[L\] すべて No \[?\] ヘルプ (規定値は "Y"):</span><span class="sxs-lookup"><span data-stu-id="260d1-192">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      > <span data-ttu-id="260d1-193">確認なしで変更を行う場合は、手順 3 で次のコマンドレットを代わりに使用します: Set-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="260d1-193">If you want your changes to occur without confirmation, in Step 3, use this cmdlet instead: Set-DlpEdmSchema -FileData $edmSchemaXml</span></span>

      > [!NOTE]
      > <span data-ttu-id="260d1-194">追加機能を使用して EDMSchema を更新するには、10 から 60 分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="260d1-194">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="260d1-195">追加機能を使用する手順を実行する前に、更新プログラムを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="260d1-195">The update must complete before you execute steps that use the additions.</span></span>

## <a name="removing-the-schema-for-edm-based-classification"></a><span data-ttu-id="260d1-196">EDM ベースの分類のスキーマを削除する</span><span class="sxs-lookup"><span data-stu-id="260d1-196">Removing the schema for EDM-based classification</span></span>

<span data-ttu-id="260d1-197">(必要に応じて) EDM ベースの分類に使用しているスキーマを削除するには、次の手順に従います:</span><span class="sxs-lookup"><span data-stu-id="260d1-197">(As needed) If you want to remove the schema you're using for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="260d1-198">[セキュリティ/コンプライアンス センター PowerShell に接続します](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="260d1-198">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

2. <span data-ttu-id="260d1-199">次の PowerShell コマンドレットを実行して、「patientrecords」のデータ ストア名を削除するものに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="260d1-199">Run the following PowerShell cmdlets, substituting the data store name of "patientrecords" with the one you want to remove:</span></span>

      ```powershell
      Remove-DlpEdmSchema -Identity patientrecords
      ```

      <span data-ttu-id="260d1-200">次のように、確認を求められます。</span><span class="sxs-lookup"><span data-stu-id="260d1-200">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="260d1-201">確認</span><span class="sxs-lookup"><span data-stu-id="260d1-201">Confirm</span></span>
      >
      > <span data-ttu-id="260d1-202">この操作を実行しますか?</span><span class="sxs-lookup"><span data-stu-id="260d1-202">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="260d1-203">データストア ' patientrecords ' の EDM スキーマが削除されます。</span><span class="sxs-lookup"><span data-stu-id="260d1-203">EDM Schema for the data store 'patientrecords' will be removed.</span></span>
      >
      > <span data-ttu-id="260d1-204">\[Y\] Yes \[A\] すべて Yes \[N\] No \[L\] すべて No \[?\] ヘルプ (規定値は "Y"):</span><span class="sxs-lookup"><span data-stu-id="260d1-204">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      >  <span data-ttu-id="260d1-205">確認なしで変更を行う場合は、手順 2 で次のコマンドレットを代わりに使用します: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span><span class="sxs-lookup"><span data-stu-id="260d1-205">If you want your changes to occur without confirmation, in Step 2, use this cmdlet instead: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span></span>

### <a name="set-up-a-rule-package"></a><span data-ttu-id="260d1-206">ルール パッケージを設定する</span><span class="sxs-lookup"><span data-stu-id="260d1-206">Set up a rule package</span></span>

1. <span data-ttu-id="260d1-207">次の例のように、.xml 形式 (Unicode エンコード) でルール パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="260d1-207">Create a rule package in .xml format (with Unicode encoding), similar to the following example.</span></span> <span data-ttu-id="260d1-208">(この例は、コピー、変更、使用することができます。)</span><span class="sxs-lookup"><span data-stu-id="260d1-208">(You can copy, modify, and use our example.)</span></span>

      <span data-ttu-id="260d1-209">ルール パッケージをセットアップするときに、.csv ファイルと **edm .xml** ファイルを正しく参照してください。</span><span class="sxs-lookup"><span data-stu-id="260d1-209">When you set up your rule package, make sure to correctly reference your .csv file and **edm.xml** file.</span></span> <span data-ttu-id="260d1-210">この例は、コピー、変更、使用が可能です。</span><span class="sxs-lookup"><span data-stu-id="260d1-210">You can copy, modify, and use our example.</span></span> <span data-ttu-id="260d1-211">このサンプル xml では、EDM の機密情報の種類を作成するために、次のフィールドをカスタマイズする必要があります。</span><span class="sxs-lookup"><span data-stu-id="260d1-211">In this sample xml the following fields needs to be customized to create your EDM sensitive type:</span></span>

      - <span data-ttu-id="260d1-212">**RulePack id & ExactMatch id**:  [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6)  を使用して GUID を作成します。</span><span class="sxs-lookup"><span data-stu-id="260d1-212">**RulePack id & ExactMatch id**: Use [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) to generate a GUID.</span></span>

      - <span data-ttu-id="260d1-213">**Datastore**: このフィールドは、使用する EDM ルックアップデータストアを指定します。</span><span class="sxs-lookup"><span data-stu-id="260d1-213">**Datastore**: This field specifies EDM lookup data store to be used.</span></span> <span data-ttu-id="260d1-214">設定済みの EDM スキーマのデータソース名を指定します。</span><span class="sxs-lookup"><span data-stu-id="260d1-214">You provide a data source name of a configured EDM Schema.</span></span>

      - <span data-ttu-id="260d1-215">**idMatch**: このフィールドは、EDM の主要素を示します。</span><span class="sxs-lookup"><span data-stu-id="260d1-215">**idMatch**: This field points to the primary element for EDM.</span></span>
        - <span data-ttu-id="260d1-216">検索結果: ルックアップで使用するフィールドを指定します。</span><span class="sxs-lookup"><span data-stu-id="260d1-216">Matches: Specifies the field to be used in exact lookup.</span></span> <span data-ttu-id="260d1-217">データストアの EDM スキーマで検索可能なフィールド名を指定します。</span><span class="sxs-lookup"><span data-stu-id="260d1-217">You provide a searchable field name in EDM Schema for the DataStore.</span></span>
        - <span data-ttu-id="260d1-218">分類: このフィールドでは、EDM ルックアップをトリガーする、機密情報の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="260d1-218">Classification: This field specifies the sensitive type match that triggers EDM lookup.</span></span> <span data-ttu-id="260d1-219">既存の組み込みまたはカスタム分類の名前または GUID を指定できます。</span><span class="sxs-lookup"><span data-stu-id="260d1-219">You can provide Name or GUID of an existing built-in or custom classification.</span></span>

      - <span data-ttu-id="260d1-220">**Match:** このフィールドは、近接 idMatch で見つかった追加の証拠を示します。</span><span class="sxs-lookup"><span data-stu-id="260d1-220">**Match:** This field points to additional evidence found in proximity of idMatch.</span></span>
        - <span data-ttu-id="260d1-221">Matches: データストアの EDM スキーマで検索可能なフィールド名を指定します。</span><span class="sxs-lookup"><span data-stu-id="260d1-221">Matches: You provide any field name in EDM Schema for DataStore.</span></span>
      - <span data-ttu-id="260d1-222">**リソース:** このセクションでは、複数のローカルでの機密情報の種類の名前と説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="260d1-222">**Resource:** This section specifies the name and description for sensitive type in multiple locales.</span></span>
        - <span data-ttu-id="260d1-223">idRef: ExactMatch ID の GUID を指定します。</span><span class="sxs-lookup"><span data-stu-id="260d1-223">idRef: You provide GUID for ExactMatch ID.</span></span>
        - <span data-ttu-id="260d1-224">名前と説明: 必要に応じてカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="260d1-224">Name & descriptions: customize as required.</span></span>

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
          <LocalizedStrings>
            <Resource idRef="E1CC861E-3FE9-4A58-82DF-4BD259EAB371">
              <Name default="true" langcode="en-us">Patient SSN Exact Match.</Name>
              <Description default="true" langcode="en-us">EDM Sensitive type for detecting Patient SSN.</Description>
            </Resource>
          </LocalizedStrings>
        </Rules>
      </RulePackage>
      ```

1. <span data-ttu-id="260d1-225">次の PowerShell コマンドレットを 1 つずつ実行して、ルール パッケージをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="260d1-225">Upload the rule package by running the following PowerShell cmdlets, one at a time:</span></span>

      ```powershell
      $rulepack=Get-Content .\\rulepack.xml -Encoding Byte -ReadCount 0
      New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack
      ```

<span data-ttu-id="260d1-226">この時点で、EDM ベースの分類がセットアップされています。</span><span class="sxs-lookup"><span data-stu-id="260d1-226">At this point, you have set up EDM-based classification.</span></span> <span data-ttu-id="260d1-227">次の手順では、機密データにインデックスを付け、インデックス付きのデータをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="260d1-227">The next step is to index the sensitive data, and then upload the indexed data.</span></span>

<span data-ttu-id="260d1-228">前の手順から PatientRecords スキーマが次の 5 つのフィールドを検索可能として定義していることに注意してください:  *PatientID*、 *MRN*、 *SSN*、 *Phone*、 *DOB*。</span><span class="sxs-lookup"><span data-stu-id="260d1-228">Recall from the previous procedure that our PatientRecords schema defines five fields as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span> <span data-ttu-id="260d1-229">ルール パッケージの例には、これらのフィールドが含まれ、検索可能なフィールドごとに 1 つの  *ExactMatch*  アイテムを含むデータベース スキーマ ファイル (**edm.xml**) を参照します。</span><span class="sxs-lookup"><span data-stu-id="260d1-229">Our example rule package includes those fields and references the database schema file (**edm.xml**), with one *ExactMatch* items per searchable field.</span></span> <span data-ttu-id="260d1-230">次の ExactMatch アイテムを検討してください。</span><span class="sxs-lookup"><span data-stu-id="260d1-230">Consider the following ExactMatch item:</span></span>

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

<span data-ttu-id="260d1-231">この例では、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="260d1-231">In this example, note the following:</span></span>

- <span data-ttu-id="260d1-232">データストア名は、以前に作成した .csv ファイルを参照します ( **datastore = "PatientRecords"**)。</span><span class="sxs-lookup"><span data-stu-id="260d1-232">The dataStore name references the .csv file we created earlier: **dataStore = "PatientRecords"**.</span></span>

- <span data-ttu-id="260d1-233">idMatch 値は、データベース スキーマ ファイルに一覧表示されている検索可能なフィールドを参照します ( **idMatch matches = "SSN"**)。</span><span class="sxs-lookup"><span data-stu-id="260d1-233">The idMatch value references a searchable field that is listed in the database schema file: **idMatch matches = "SSN"**.</span></span>

- <span data-ttu-id="260d1-234">分類の値は、既存またはカスタムの機密情報の種類を参照します ( **分類 = "米国社会保障番号 (SSN)"**)。</span><span class="sxs-lookup"><span data-stu-id="260d1-234">The classification value references an existing or custom sensitive information type: **classification = "U.S. Social Security Number (SSN)"**.</span></span> <span data-ttu-id="260d1-235">(この場合は、既存の機密情報の種類の米国社会保障番号を使用します。)</span><span class="sxs-lookup"><span data-stu-id="260d1-235">(In this case, we use the existing sensitive information type of U.S. Social Security Number.)</span></span>

> [!NOTE]
> <span data-ttu-id="260d1-236">追加機能を使用して EDMSchema を更新するには、10 から 60 分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="260d1-236">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="260d1-237">追加機能を使用する手順を実行する前に、更新プログラムを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="260d1-237">The update must complete before you execute steps that use the additions.</span></span>

### <a name="part-2-index-and-upload-the-sensitive-data"></a><span data-ttu-id="260d1-238">パート 2: 機密データのインデックスを作成しアップロードする</span><span class="sxs-lookup"><span data-stu-id="260d1-238">Part 2: Index and upload the sensitive data</span></span>

<span data-ttu-id="260d1-239">このフェーズでは、カスタムのセキュリティ グループとユーザー アカウントをセットアップし、EDM Upload Agent ツールをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="260d1-239">During this phase, you set up a custom security group and user account, and set up the EDM Upload Agent tool.</span></span> <span data-ttu-id="260d1-240">次に、このツールを使用して機密データにインデックスを作成し、インデックス付きのデータをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="260d1-240">Then, you use the tool to index the sensitive data, and upload the indexed data.</span></span>

#### <a name="set-up-the-security-group-and-user-account"></a><span data-ttu-id="260d1-241">セキュリティ グループとユーザー アカウントをセットアップする</span><span class="sxs-lookup"><span data-stu-id="260d1-241">Set up the security group and user account</span></span>

1. <span data-ttu-id="260d1-242">全体管理者として、管理センター ([https://admin.microsoft.com](https://admin.microsoft.com/)) へ移動し、 **EDM\_DataUploaders** という [セキュリティー グループを作成](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide)  します。</span><span class="sxs-lookup"><span data-stu-id="260d1-242">As a global administrator, go to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com/)) and [create a security group](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) called **EDM\_DataUploaders**.</span></span>

2. <span data-ttu-id="260d1-243"> **EDM\_DataUploaders**  セキュリティ グループに、1 人以上のユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="260d1-243">Add one or more users to the **EDM\_DataUploaders** security group.</span></span> <span data-ttu-id="260d1-244">(これらのユーザーは機密情報のデータベースを管理します)。</span><span class="sxs-lookup"><span data-stu-id="260d1-244">(These users will manage the database of sensitive information.)</span></span>

3. <span data-ttu-id="260d1-245">機密データを管理している各ユーザーが、EDM アップロード エージェントに使用されるコンピューターのローカル管理者であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="260d1-245">Make sure each user who is managing the sensitive data is a local admin on the machine used for the EDM Upload Agent.</span></span>

#### <a name="set-up-the-edm-upload-agent"></a><span data-ttu-id="260d1-246">EDM アップロード エージェントをセットアップする</span><span class="sxs-lookup"><span data-stu-id="260d1-246">Set up the EDM Upload Agent</span></span>

>[!NOTE]
> <span data-ttu-id="260d1-247">この手順を開始する前に、自分が  **EDM\_DataUploaders**  セキュリティ グループのメンバーであり、コンピューターのローカル管理者であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="260d1-247">Before you begin this procedure, make sure that you are a member of the **EDM\_DataUploaders** security group and a local admin on your machine.</span></span>

1. <span data-ttu-id="260d1-248">[EDM アップロード エージェント](https://go.microsoft.com/fwlink/?linkid=2088639)をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="260d1-248">Download and install the [EDM Upload Agent](https://go.microsoft.com/fwlink/?linkid=2088639).</span></span> <span data-ttu-id="260d1-249">既定では、インストール場所は、[ **C:\\Program Files\\Microsoft\\EdmUploadAgent**] になります。</span><span class="sxs-lookup"><span data-stu-id="260d1-249">By default, the installation location should be **C:\\Program Files\\Microsoft\\EdmUploadAgent**.</span></span>

      > [!TIP]
      > <span data-ttu-id="260d1-250">サポートされているコマンド パラメーターから一覧を取得するには、エージェントの引数を実行します。</span><span class="sxs-lookup"><span data-stu-id="260d1-250">To a get a list out of the supported command parameters, run the agent no arguments.</span></span> <span data-ttu-id="260d1-251">たとえば、「EdmUploadAgent.exe」です。</span><span class="sxs-lookup"><span data-stu-id="260d1-251">For example 'EdmUploadAgent.exe'.</span></span>

2. <span data-ttu-id="260d1-252">EDM アップロード エージェントを承認するには、管理者として Windows コマンド プロンプトを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="260d1-252">To authorize the EDM Upload Agent, open Windows Command Prompt (as an administrator), and then run the following command:</span></span>

    `EdmUploadAgent.exe /Authorize`

3. <span data-ttu-id="260d1-253">職場または学校の Office 365 アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="260d1-253">Sign in with your work or school account for Office 365.</span></span>

<span data-ttu-id="260d1-254">次の手順では、EDM アップロード エージェントを使用して機密データにインデックスを付け、インデックス付きのデータをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="260d1-254">The next step is to use the EDM Upload Agent to index the sensitive data, and then upload the indexed data.</span></span>

#### <a name="index-and-upload-the-sensitive-data"></a><span data-ttu-id="260d1-255">機密データのインデックスを作成しアップロードする</span><span class="sxs-lookup"><span data-stu-id="260d1-255">Index and upload the sensitive data</span></span>

<span data-ttu-id="260d1-256">機密データ ファイル (この例では  **PatientRecords.csv**) をコンピューターのローカル ドライブに保存します。</span><span class="sxs-lookup"><span data-stu-id="260d1-256">Save the sensitive data file (recall our example is **PatientRecords.csv**) to the local drive on the machine.</span></span> <span data-ttu-id="260d1-257">(例の  **PatientRecords.csv**  ファイルを  **C:\\Edm\\Data** に保存しました。)</span><span class="sxs-lookup"><span data-stu-id="260d1-257">(We saved our example **PatientRecords.csv** file to **C:\\Edm\\Data**.)</span></span>

<span data-ttu-id="260d1-258">機密データにインデックスを付けてアップロートするには、Windows コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="260d1-258">To index and upload the sensitive data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /UploadData /DataStoreName \<DataStoreName\> /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="260d1-259">例: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\\Edm\\Hash\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span><span class="sxs-lookup"><span data-stu-id="260d1-259">Example: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\\Edm\\Hash\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span></span>

<span data-ttu-id="260d1-260">分離された環境で機密データのインデックスを作成して実行するには、インデックスを実行し、手順を個別にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="260d1-260">To separate and execute index of sensitive data in an isolated environment, execute index and upload steps separately.</span></span>

<span data-ttu-id="260d1-261">機密データにインデックスを付けるには、Windows コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="260d1-261">To index the sensitive data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /CreateHash /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="260d1-262">例:</span><span class="sxs-lookup"><span data-stu-id="260d1-262">For example:</span></span>

> <span data-ttu-id="260d1-263">**EdmUploadAgent.exe /CreateHash /DataFile C:\\Edm\\Data\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span><span class="sxs-lookup"><span data-stu-id="260d1-263">**EdmUploadAgent.exe /CreateHash /DataFile C:\\Edm\\Data\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span></span>

<span data-ttu-id="260d1-264">インデックス付きのデータをアップロードするには、Windows コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="260d1-264">To upload the indexed data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\>`

<span data-ttu-id="260d1-265">例:</span><span class="sxs-lookup"><span data-stu-id="260d1-265">For example:</span></span>

> <span data-ttu-id="260d1-266">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span><span class="sxs-lookup"><span data-stu-id="260d1-266">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span></span>

<span data-ttu-id="260d1-267">機密データがアップロードされたことを確認するには、Windows コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="260d1-267">To verify your sensitive data has been uploaded, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /GetDataStore`

<span data-ttu-id="260d1-268">データ ストアのリストと、それらが最後に更新された日時が表示されます。</span><span class="sxs-lookup"><span data-stu-id="260d1-268">You'll see a list of data stores and when they were last updated.</span></span>

<span data-ttu-id="260d1-269"> [機密情報データベースを更新する](#refreshing-your-sensitive-information-database)ためのプロセスとスケジュールのセットアップを進めます。</span><span class="sxs-lookup"><span data-stu-id="260d1-269">Proceed to set up your process and schedule for [Refreshing your sensitive information database](#refreshing-your-sensitive-information-database).</span></span>

<span data-ttu-id="260d1-270">この時点で、Microsoft クラウド サービスで EDM ベースの分類を使用する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="260d1-270">At this point, you are ready to use EDM-based classification with your Microsoft cloud services.</span></span> <span data-ttu-id="260d1-271">たとえば、 [EDM ベースの分類を使用して DLP ポリシーを設定](#to-create-a-dlp-policy-with-edm)できます。</span><span class="sxs-lookup"><span data-stu-id="260d1-271">For example, you can [set up a DLP policy using EDM-based classification](#to-create-a-dlp-policy-with-edm).</span></span>

#### <a name="refreshing-your-sensitive-information-database"></a><span data-ttu-id="260d1-272">機密情報データベースを更新する</span><span class="sxs-lookup"><span data-stu-id="260d1-272">Refreshing your sensitive information database</span></span>

<span data-ttu-id="260d1-273">機密情報データベースは毎日または毎週更新できます。また、EDM アップロード ツールを使用して機密データのインデックスを再作成し、インデックス付きデータを再アップロードできます。</span><span class="sxs-lookup"><span data-stu-id="260d1-273">You can refresh your sensitive information database daily or weekly, and the EDM Upload Tool can reindex the sensitive data and then reupload the indexed data.</span></span>

1. <span data-ttu-id="260d1-274">機密情報のデータベースを更新するためのプロセスと頻度 (毎日または毎週) を決定します。</span><span class="sxs-lookup"><span data-stu-id="260d1-274">Determine your process and frequency (daily or weekly) for refreshing the database of sensitive information.</span></span>

2. <span data-ttu-id="260d1-275">機密情報データを Microsoft Excel などのアプリに再度エクスポートし、ファイルを .csv 形式で保存します。</span><span class="sxs-lookup"><span data-stu-id="260d1-275">Re-export the sensitive data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="260d1-276">「 [機密データのインデックスを作成しアップロードする](#index-and-upload-the-sensitive-data)」で説明した手順の実行時に使用したファイル名と場所と同じものを使用してください。</span><span class="sxs-lookup"><span data-stu-id="260d1-276">Keep the same file name and location you used when you followed the steps described in [Index and upload the sensitive data](#index-and-upload-the-sensitive-data).</span></span>

      > [!NOTE]
      > <span data-ttu-id="260d1-277">.csv ファイルの構造 (フィールド名) に変更がない場合は、データを更新する際に、データベース スキーマ ファイルを変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="260d1-277">If there are no changes to the structure (field names) of the .csv file, you won't need to make any changes to your database schema file when you refresh the data.</span></span> <span data-ttu-id="260d1-278">ただし、変更が必要な場合は、必要に応じてデータベース スキーマとルール パッケージを編集してください。</span><span class="sxs-lookup"><span data-stu-id="260d1-278">But if you must make changes, make sure to edit the database schema and your rule package accordingly.</span></span>

3. <span data-ttu-id="260d1-279"> [タスク スケジューラ](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) を使用して、 [機密データのインデックスを作成しアップロードする](#index-and-upload-the-sensitive-data)  手順の、手順 2 と 3 を自動化します。</span><span class="sxs-lookup"><span data-stu-id="260d1-279">Use [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) to automate steps 2 and 3 in the [Index and upload the sensitive data](#index-and-upload-the-sensitive-data) procedure.</span></span> <span data-ttu-id="260d1-280">タスクのスケジュールを設定するにはいくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="260d1-280">You can schedule tasks using several methods:</span></span>

      | <span data-ttu-id="260d1-281">**方法**</span><span class="sxs-lookup"><span data-stu-id="260d1-281">**Method**</span></span>             | <span data-ttu-id="260d1-282">**操作**</span><span class="sxs-lookup"><span data-stu-id="260d1-282">**What to do**</span></span>                                                                                                                                                                                                                                                                                                                                                                                                                     |
      | ---------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
      | <span data-ttu-id="260d1-283">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="260d1-283">Windows PowerShell</span></span>     | <span data-ttu-id="260d1-284"> [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) のドキュメントと、この記事の  [PowerShell スクリプトの例](#example-powershell-script-for-task-scheduler) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="260d1-284">See the [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) documentation and the [example PowerShell script](#example-powershell-script-for-task-scheduler) in this article</span></span> |
      | <span data-ttu-id="260d1-285">タスク スケジューラ API</span><span class="sxs-lookup"><span data-stu-id="260d1-285">Task Scheduler API</span></span>     | <span data-ttu-id="260d1-286"> [タスク スケジューラ](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) ドキュメントを参照してください</span><span class="sxs-lookup"><span data-stu-id="260d1-286">See the [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) documentation</span></span>                                                                                                                                                                                                                                                                                |
      | <span data-ttu-id="260d1-287">Windows のユーザー インターフェイス</span><span class="sxs-lookup"><span data-stu-id="260d1-287">Windows user interface</span></span> | <span data-ttu-id="260d1-288">Windows の場合、 **[スタート]** をクリックし、「タスクスケジューラ」と入力します。</span><span class="sxs-lookup"><span data-stu-id="260d1-288">In Windows, click **Start**, and type Task Scheduler.</span></span> <span data-ttu-id="260d1-289">次に、結果のリストで  **[タスク スケジューラ]** を右クリックし、 **[管理者として実行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="260d1-289">Then, in the list of results, right-click **Task Scheduler**, and choose **Run as administrator**.</span></span>                                                                                                                                                                                                                                                                           |

#### <a name="example-powershell-script-for-task-scheduler"></a><span data-ttu-id="260d1-290">タスク スケジューラの PowerShell スクリプトの例</span><span class="sxs-lookup"><span data-stu-id="260d1-290">Example PowerShell script for Task Scheduler</span></span>

<span data-ttu-id="260d1-291">このセクションには、データのインデックスを作成したり、インデックス付きのデータをアップロードするタスクのスケジュールに使用できる PowerShell スクリプトの例が含まれています。</span><span class="sxs-lookup"><span data-stu-id="260d1-291">This section includes an example PowerShell script you can use to schedule your tasks for indexing data and uploading the indexed data:</span></span>

##### <a name="to-schedule-index-and-upload-in-a-combined-step"></a><span data-ttu-id="260d1-292">インデックスのスケジュールを設定して、結合されたステップでアップロードするには</span><span class="sxs-lookup"><span data-stu-id="260d1-292">To schedule index and upload in a combined step</span></span>

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

#### <a name="to-schedule-index-and-upload-as-separate-steps"></a><span data-ttu-id="260d1-293">インデックスのスケジュールを設定して、個別のステップでアップロードするには</span><span class="sxs-lookup"><span data-stu-id="260d1-293">To schedule index and upload as separate steps</span></span>

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

### <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a><span data-ttu-id="260d1-294">パート 3: Microsoft クラウド サービスで EDM ベースの分類を使用する</span><span class="sxs-lookup"><span data-stu-id="260d1-294">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>

<span data-ttu-id="260d1-295">DLP for Exchange Online (メール)、OneDrive for Business (ファイル)、Microsoft Teams (会話)、Microsoft Cloud App Security DLP ポリシーは、EDM の機密情報の種類をサポートします。</span><span class="sxs-lookup"><span data-stu-id="260d1-295">DLP for Exchange Online (email), OneDrive for Business (files), Microsoft Teams (conversations) and Microsoft Cloud App Security DLP policies will support EDM sensitive information types.</span></span>

<span data-ttu-id="260d1-296">次のシナリオでは、EDM の機密情報の種類は現在開発中で、まだご利用いただけません。</span><span class="sxs-lookup"><span data-stu-id="260d1-296">EDM sensitive information types for following scenarios are currently in development, but not yet available:</span></span>

- <span data-ttu-id="260d1-297">DLP for SharePoint (ファイル)</span><span class="sxs-lookup"><span data-stu-id="260d1-297">DLP for SharePoint (files)</span></span>
- <span data-ttu-id="260d1-298">機密度ラベルと保持ラベルの自動分類</span><span class="sxs-lookup"><span data-stu-id="260d1-298">Auto-classification of sensitivity labels and retention labels</span></span>

#### <a name="to-create-a-dlp-policy-with-edm"></a><span data-ttu-id="260d1-299">EDM を使用して DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="260d1-299">To create a DLP policy with EDM</span></span>

1. <span data-ttu-id="260d1-300">セキュリティ/コンプライアンス センターに移動します ([https://protection.office.com](https://protection.office.com/))。</span><span class="sxs-lookup"><span data-stu-id="260d1-300">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com/)).</span></span>

2. <span data-ttu-id="260d1-301"> **[データ損失防止]** \> **[ポリシー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="260d1-301">Choose **Data loss prevention** \> **Policy**.</span></span>

3. <span data-ttu-id="260d1-302"> **[ポリシーの作成]** \> **[カスタム]** \> **[次へ]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="260d1-302">Choose **Create a policy** \> **Custom** \> **Next**.</span></span>

4. <span data-ttu-id="260d1-303"> **[ポリシーの名前を設定]**  タブで名前と説明を指定し、 **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="260d1-303">On the **Name your policy** tab, specify a name and description, and then choose **Next**.</span></span>

5. <span data-ttu-id="260d1-304"> **[場所の選択]**  タブで、 **[特定の場所を選択]** し、 **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="260d1-304">On the **Choose locations** tab, select **Let me choose specific locations**, and then choose **Next**.</span></span>

6. <span data-ttu-id="260d1-305"> **[状態]** の列で、 **Exchange メール、OneDrive アカウント、Teams チャット、チャネル メッセージ** を選択し、 **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="260d1-305">In the **Status** column, select **Exchange email, OneDrive accounts, Teams chat and channel message** , and then choose **Next**.</span></span> <span data-ttu-id="260d1-306">(注: 現在、EDM は SharePoint サイトでサポートされていないため、DLP ポリシーは Sharepoint for EDM でファイルを検出できません)</span><span class="sxs-lookup"><span data-stu-id="260d1-306">(Note: EDM is currently not supported in SharePoint sites and DLP policy will not detect files in Sharepoint for EDM)</span></span>

7. <span data-ttu-id="260d1-307"> **[ポリシーの設定]**  タブで、 **[詳細設定を使用]** を選択し、 **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="260d1-307">On the **Policy settings** tab, choose **Use advanced settings**, and then choose **Next**.</span></span>

8. <span data-ttu-id="260d1-308"> **[+ 新しいルール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="260d1-308">Choose **+ New rule**.</span></span>

9. <span data-ttu-id="260d1-309"> **[名前]**  セクションで、ルールの名前と説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="260d1-309">In the **Name** section, specify a name and description for the rule.</span></span>

10. <span data-ttu-id="260d1-310"> **[条件]**  セクションの、 **[+ 条件の追加]**  リストで、 **[機密情報の種類を含むコンテンツ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="260d1-310">In the **Conditions** section, in the **+ Add a condition** list, choose **Content contains sensitive type**.</span></span>

      ![機密情報の種類を含むコンテンツ](../media/edm-dlp-newrule-conditions.png)

11. <span data-ttu-id="260d1-312">ルール パッケージのセットアップ時に作成した機密情 報の種類を検索し、 **[+ 追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="260d1-312">Search for the sensitive information type you created when you set up your rule package, and then choose **+ Add**.</span></span>  
    <span data-ttu-id="260d1-313"> **[完了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="260d1-313">Then choose **Done**.</span></span>

12. <span data-ttu-id="260d1-314">ルールのオプション ( **[ユーザー通知]**、 **[ユーザーによる上書き]**、 **[インシデント レポート]** など) の選択を終了し、 **[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="260d1-314">Finish selecting options for your rule, such as **User notifications**, **User overrides**, **Incident reports**, and so on, and then choose **Save**.</span></span>

13. <span data-ttu-id="260d1-315"> **[ポリシーの設定]**  タブでルールを確認し、 **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="260d1-315">On the **Policy settings** tab, review your rules, and then choose **Next**.</span></span>

14. <span data-ttu-id="260d1-316">ポリシーをすぐに有効にするか、テストするか、無効にするかを指定します。</span><span class="sxs-lookup"><span data-stu-id="260d1-316">Specify whether to turn on the policy right away, test it out, or keep it turned off.</span></span> <span data-ttu-id="260d1-317"> **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="260d1-317">Then choose **Next**.</span></span>

15. <span data-ttu-id="260d1-318"> **[設定を確認]**  タブで、ポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="260d1-318">On the **Review your settings** tab, review your policy.</span></span> <span data-ttu-id="260d1-319">必要な変更を行います。</span><span class="sxs-lookup"><span data-stu-id="260d1-319">Make any needed changes.</span></span> <span data-ttu-id="260d1-320">準備ができたら  **[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="260d1-320">When you're ready, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="260d1-321">新しい DLP ポリシーがデータ センターを通過するまでに、約 1 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="260d1-321">Allow approximately one hour for your new DLP policy to work its way through your data center.</span></span>

## <a name="related-articles"></a><span data-ttu-id="260d1-322">関連記事</span><span class="sxs-lookup"><span data-stu-id="260d1-322">Related articles</span></span>

[<span data-ttu-id="260d1-323">組み込みの機密情報の種類とその検索対象</span><span class="sxs-lookup"><span data-stu-id="260d1-323">Built-in sensitive information types and what they look for</span></span>](what-the-sensitive-information-types-look-for.md)

[<span data-ttu-id="260d1-324">カスタムの機密情報の種類</span><span class="sxs-lookup"><span data-stu-id="260d1-324">Custom sensitive information types</span></span>](custom-sensitive-info-types.md)

[<span data-ttu-id="260d1-325">DLP ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="260d1-325">Overview of DLP policies</span></span>](data-loss-prevention-policies.md)

[<span data-ttu-id="260d1-326">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="260d1-326">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)

[<span data-ttu-id="260d1-327">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="260d1-327">New-DlpEdmSchema</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/new-dlpedmschema?view=exchange-ps)

## <a name="feedback"></a><span data-ttu-id="260d1-328">フィードバック</span><span class="sxs-lookup"><span data-stu-id="260d1-328">Feedback</span></span>

<span data-ttu-id="260d1-329">GitHub フィードバックは有効になっていますが、懸案事項の追加は、公開サイトでのみ行うことができます。</span><span class="sxs-lookup"><span data-stu-id="260d1-329">GitHub feedback is enabled, but adding issues is only available on the public site.</span></span>
