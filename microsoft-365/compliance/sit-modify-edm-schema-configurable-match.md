---
title: 構成可能な一致を使用するために完全一致スキーマを変更する
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
description: 構成可能な一致を使用するために、完全一致スキーマを変更する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dea641072983163c6fbbcc5888d5ee6ea91f6990
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408316"
---
# <a name="modify-exact-data-match-schema-to-use-configurable-match"></a><span data-ttu-id="263db-103">構成可能な一致を使用するために完全一致スキーマを変更する</span><span class="sxs-lookup"><span data-stu-id="263db-103">Modify Exact Data Match schema to use configurable match</span></span>

<span data-ttu-id="263db-104">完全一致 (EDM) ベースの分類を使用すると、機密情報のデータベース内の正確な値を参照するカスタムの機密情報タイプを作成できます。</span><span class="sxs-lookup"><span data-stu-id="263db-104">Exact Data Match (EDM) based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="263db-105">正確な文字列のバリアントを許可する必要がある場合は、*構成可能な一致* を使用して、大文字と小文字および一部の区切り文字を無視するように Microsoft 365 に指示できます。</span><span class="sxs-lookup"><span data-stu-id="263db-105">When you need to allow for variants of a exact string, you can use *configurable match* to tell Microsoft 365 to ignore case and some delimiters.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="263db-106">既存の EDM スキーマとデータファイルを変更するには、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="263db-106">Use this procedure to modify an existing EDM schema and data file.</span></span>

1. <span data-ttu-id="263db-107">EDM スキーマとデータファイルのアップロードの目的で Microsoft 365 への接続に使用するコンピューターから、**EdmUploadAgent.exe** をアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="263db-107">Uninstall the **EdmUploadAgent.exe** from the computer that you use to connect to Microsoft 365 for EDM schema and data file upload purposes.</span></span>

2. <span data-ttu-id="263db-108">以下のリンクを使用して、サブスクリプションに適した **EdmUploadAgent.exe** ファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="263db-108">Download the appropriate **EdmUploadAgent.exe** file for your subscription using the links below:</span></span>
    - <span data-ttu-id="263db-109">[商用 + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - ほとんどの商用のお客様はこれを使用する必要があります</span><span class="sxs-lookup"><span data-stu-id="263db-109">[Commercial + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - most commercial customers should use this</span></span>
    - <span data-ttu-id="263db-110">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - これは特に高セキュリティの政府機関向けクラウド加入者を対象にしています</span><span class="sxs-lookup"><span data-stu-id="263db-110">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - This is specifically for high security government cloud subscribers</span></span>
    - <span data-ttu-id="263db-111">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - これは特に米国国防総省のクラウド顧客対象にしています</span><span class="sxs-lookup"><span data-stu-id="263db-111">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - this is specifically for United States Department of Defense cloud customers</span></span>

3. <span data-ttu-id="263db-112">EDM アップロード エージェントを承認し、管理者としてコマンドプロンプト ウィンドウを開いて、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="263db-112">Authorize the EDM Upload Agent, open Command Prompt window (as an administrator) and run the following command:</span></span>

   `EdmUploadAgent.exe /Authorize`

4. <span data-ttu-id="263db-113">既存のスキーマの最新のコピーがない場合は、既存のスキーマのコピーをダウンロードして、次のコマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="263db-113">If you don't have a current copy of the existing schema, you'll need to download a copy of the existing schema, run this command:</span></span>

    `EdmUploadAgent.exe /SaveSchema /DataStoreName <dataStoreName> [/OutputDir [Output dir location]]`

5. <span data-ttu-id="263db-114">各列が “caseInsensitive” または “ignoredDelimiters” を利用するようにスキーマをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="263db-114">Customize the schema so each column utilizes “caseInsensitive” and / or “ignoredDelimiters”.</span></span>  <span data-ttu-id="263db-115">“caseInsensitive“ の既定値は “false“ で、“ignoredDelimiters“ の場合は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="263db-115">The default value for “caseInsensitive” is “false” and for “ignoredDelimiters”, it is an empty string.</span></span> 

> [!NOTE]
> <span data-ttu-id="263db-116">一般的な正規表現パターンの検出に使用される、基になるカスタム機密情報タイプまたは組み込みの機密情報タイプは、ignoredDelimiters でリストされたバリエーション入力の検出をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="263db-116">The underlying custom sensitive information type or built in sensitive information type used to detect the general regex pattern must support detection of the variations inputs listed with ignoredDelimiters.</span></span> <span data-ttu-id="263db-117">たとえば、組み込みの米国社会保障番号 (SSN) の機密情報タイプは、SSNを構成するグループ化された番号間のダッシュ、スペース、またはスペースの不足を含むデータの変動を検出できます。</span><span class="sxs-lookup"><span data-stu-id="263db-117">For example, the built in U.S. social security number (SSN) sensitive information type can detect variations in the data that include dashes, spaces, or lack of spaces between the grouped numbers that make up the SSN.</span></span> <span data-ttu-id="263db-118">その結果、ESN データの EDM の ignoredDelimiters に含めるのに関連する区切り文字は、ダッシュとスペースのみです。</span><span class="sxs-lookup"><span data-stu-id="263db-118">As a result, the only delimiters that are relevant to include in EDM’s ignoredDelimiters for SSN data are: dash and space.</span></span>

<span data-ttu-id="263db-119">これは、機密データの大文字と小文字の違いを認識するために必要な追加の列を作成することにより、大文字と小文字を区別しない一致をシミュレートするサンプル スキーマです。</span><span class="sxs-lookup"><span data-stu-id="263db-119">Here is a sample schema that simulates case insensitive match by creating the extra columns needed to recognize case variations in the sensitive data.</span></span>

```xml
<EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
  <DataStore name="PatientRecords" description="Schema for patient records policy" version="1">
           <Field name="PolicyNumber" searchable="true" />
           <Field name="PolicyNumberLowerCase" searchable="true" />
           <Field name="PolicyNumberUpperCase" searchable="true" />
           <Field name="PolicyNumberCapitalLetters" searchable="true" />
  </DataStore>
</EdmSchema>
```

<span data-ttu-id="263db-120">上記の例では、`caseInsensitive`と`ignoredDelimiters`の両方が追加された場合、元の `PolicyNumber` 列のバリエーションは不要になります。</span><span class="sxs-lookup"><span data-stu-id="263db-120">In the above example, the variations of the original `PolicyNumber` column will no longer be needed if both `caseInsensitive` and `ignoredDelimiters` are added.</span></span>

<span data-ttu-id="263db-121">EDM が構成可能な一致を使用するようにこのスキーマを更新するには、`caseInsensitive` および `ignoredDelimiters` フラグを使用します。</span><span class="sxs-lookup"><span data-stu-id="263db-121">To update this schema so that EDM uses configurable match use the `caseInsensitive` and `ignoredDelimiters` flags.</span></span>  <span data-ttu-id="263db-122">外観は以下の通りです。</span><span class="sxs-lookup"><span data-stu-id="263db-122">Here's how that looks:</span></span>

```xml
<EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
  <DataStore name="PatientRecords" description="Schema for patient records policy" version="1">
         <Field name="PolicyNumber" searchable="true" caseInsensitive="true" ignoredDelimiters="-,/,*,#,^" />
  </DataStore>
</EdmSchema>
```

<span data-ttu-id="263db-123">`ignoredDelimiters` フラグは英数字以外の文字をサポートします。次にいくつかの例を示します。</span><span class="sxs-lookup"><span data-stu-id="263db-123">The `ignoredDelimiters` flag supports any non-alphanumeric character, here are some examples:</span></span>
- <span data-ttu-id="263db-124">\.</span><span class="sxs-lookup"><span data-stu-id="263db-124">\.</span></span>
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

<span data-ttu-id="263db-125">`ignoredDelimiters`フラグは以下をサポートしていません:</span><span class="sxs-lookup"><span data-stu-id="263db-125">The `ignoredDelimiters` flag doesn't support:</span></span>
- <span data-ttu-id="263db-126">0 から 9 の文字</span><span class="sxs-lookup"><span data-stu-id="263db-126">characters 0-9</span></span>
- <span data-ttu-id="263db-127">A から Z</span><span class="sxs-lookup"><span data-stu-id="263db-127">A-Z</span></span>
- <span data-ttu-id="263db-128">a から z</span><span class="sxs-lookup"><span data-stu-id="263db-128">a-z</span></span>
- \"
- \,

6. <span data-ttu-id="263db-129">[セキュリティ/コンプライアンス センター PowerShellに接続する](/powershell/exchange/connect-to-scc-powershell)の手順を使用して、セキュリティ/コンプライアンス センターに接続します。</span><span class="sxs-lookup"><span data-stu-id="263db-129">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

> [!NOTE]
> <span data-ttu-id="263db-130">組織が[テナント レベル (パブリック プレビュー) で Microsoft 365 のカスタマー キー](customer-key-tenant-level.md#overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview)を設定している場合、完全一致では暗号化機能が自動的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="263db-130">If your organization has set up [Customer Key for Microsoft 365 at the tenant level (public preview)](customer-key-tenant-level.md#overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview), Exact data match will make use of its encryption functionality automatically.</span></span> <span data-ttu-id="263db-131">この機能を利用できるのは、商用クラウド内の E5 ライセンスが割り当てられたテナントのみです。</span><span class="sxs-lookup"><span data-stu-id="263db-131">This is available only to E5 licensed tenants in the Commercial cloud.</span></span>

7. <span data-ttu-id="263db-132">以下のコマンドレットを一度に 1 つずつ実行して、スキーマを更新します。</span><span class="sxs-lookup"><span data-stu-id="263db-132">Update your schema by running these cmdlets one at a time:</span></span>

`$edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0`

`Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true`

8. <span data-ttu-id="263db-133">必要に応じて、新しいスキーマ バージョンと一致するようにデータ ファイルを更新します</span><span class="sxs-lookup"><span data-stu-id="263db-133">If necessary, update the data file to match the new schema version</span></span>

> [!TIP]
> <span data-ttu-id="263db-134">オプションとして、アップロードする前に、以下を実行して csv ファイルに対して検証を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="263db-134">Optionally, you can run a validation against your csv file before uploading by running:</span></span>
>
>`EdmUploadAgent.exe /ValidateData /DataFile [data file] [schema file]`
>
><span data-ttu-id="263db-135">すべての EdmUploadAgent.exe > サポートされているパラメータの詳細情報については</span><span class="sxs-lookup"><span data-stu-id="263db-135">For more information on all the EdmUploadAgent.exe >supported parameters run</span></span>
>
> `EdmUploadAgent.exe /?`

9. <span data-ttu-id="263db-136">(管理者として) コマンドプロンプト ウィンドウを開き、次のコマンドを実行して機密データをハッシュおよびアップロードします。</span><span class="sxs-lookup"><span data-stu-id="263db-136">Open Command Prompt window (as an administrator) and run the following command to hash and upload your sensitive data:</span></span>

    `EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Salt [custom salt] /Schema [Schema file]`


## <a name="related-articles"></a><span data-ttu-id="263db-137">関連記事</span><span class="sxs-lookup"><span data-stu-id="263db-137">Related articles</span></span>

- <span data-ttu-id="263db-138">詳細については、「[Exact Data Match に基づく分類で、カスタムの機密情報の種類を作成する](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="263db-138">[Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)</span></span>
- [<span data-ttu-id="263db-139">機密情報の種類のエンティティ定義</span><span class="sxs-lookup"><span data-stu-id="263db-139">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="263db-140">カスタムの機密情報の種類</span><span class="sxs-lookup"><span data-stu-id="263db-140">Custom sensitive information types</span></span>](./sensitive-information-type-learn-about.md)
- [<span data-ttu-id="263db-141">DLP ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="263db-141">Overview of DLP policies</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="263db-142">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="263db-142">Microsoft Cloud App Security</span></span>](/cloud-app-security)
- [<span data-ttu-id="263db-143">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="263db-143">New-DlpEdmSchema</span></span>](/powershell/module/exchange/new-dlpedmschema)