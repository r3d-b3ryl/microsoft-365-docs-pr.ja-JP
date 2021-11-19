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
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 構成可能な一致を使用するために、完全一致スキーマを変更する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e546d90c94cc2a4ab349b3de7ba970b94f6491e3
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2021
ms.locfileid: "61110489"
---
# <a name="modify-exact-data-match-schema-to-use-configurable-match"></a>構成可能な一致を使用するために完全一致スキーマを変更する

完全一致 (EDM) ベースの分類を使用すると、機密情報のデータベース内の正確な値を参照するカスタムの機密情報タイプを作成できます。 正確な文字列のバリアントを許可する必要がある場合は、*構成可能な一致* を使用して、大文字と小文字および一部の区切り文字を無視するように Microsoft 365 に指示できます。 

> [!IMPORTANT]
> 既存の EDM スキーマとデータファイルを変更するには、以下の手順を実行します。

1. EDM スキーマとデータファイルのアップロードの目的で Microsoft 365 への接続に使用するコンピューターから、**EdmUploadAgent.exe** をアンインストールします。

2. 以下のリンクを使用して、サブスクリプションに適した **EdmUploadAgent.exe** ファイルをダウンロードします。
    - [商用 + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - ほとんどの商用のお客様はこれを使用する必要があります
    - [GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - これは特に高セキュリティの政府機関向けクラウド加入者を対象にしています
    - [DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - これは特に米国国防総省のクラウド顧客対象にしています

3. EDM アップロード エージェントを承認し、管理者としてコマンドプロンプト ウィンドウを開いて、次のコマンドを実行します。

   `EdmUploadAgent.exe /Authorize`

4. 既存のスキーマの最新のコピーがない場合は、既存のスキーマのコピーをダウンロードして、次のコマンドを実行する必要があります。

    `EdmUploadAgent.exe /SaveSchema /DataStoreName <dataStoreName> [/OutputDir [Output dir location]]`

5. 各列が “caseInsensitive” または “ignoredDelimiters” を利用するようにスキーマをカスタマイズします。  “caseInsensitive“ の既定値は “false“ で、“ignoredDelimiters“ の場合は空の文字列です。 

    > [!NOTE]
    > 一般的な正規表現パターンの検出に使用される、基になるカスタム機密情報タイプまたは組み込みの機密情報タイプは、ignoredDelimiters でリストされたバリエーション入力の検出をサポートする必要があります。 たとえば、組み込みの米国社会保障番号 (SSN) の機密情報タイプは、SSNを構成するグループ化された番号間のダッシュ、スペース、またはスペースの不足を含むデータの変動を検出できます。 その結果、ESN データの EDM の ignoredDelimiters に含めるのに関連する区切り文字は、ダッシュとスペースのみです。
    
    これは、機密データの大文字と小文字の違いを認識するために必要な追加の列を作成することにより、大文字と小文字を区別しない一致をシミュレートするサンプル スキーマです。
    
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
    
    上記の例では、`caseInsensitive`と`ignoredDelimiters`の両方が追加された場合、元の `PolicyNumber` 列のバリエーションは不要になります。
    
    EDM が構成可能な一致を使用するようにこのスキーマを更新するには、`caseInsensitive` フラグと `ignoredDelimiters` フラグを使用します。 その方法を次に示します:
    
    ```xml
    <EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
      <DataStore name="PatientRecords" description="Schema for patient records policy" version="1">
             <Field name="PolicyNumber" searchable="true" caseInsensitive="true" ignoredDelimiters="-,/,*,#,^" />
      </DataStore>
    </EdmSchema>
    ```
    
    `ignoredDelimiters` フラグは英数字以外の文字をサポートします。次にいくつかの例を示します。
    - \.
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
    
    `ignoredDelimiters`フラグは以下をサポートしていません:
    - 0 から 9 の文字
    - A から Z
    - a から z
    - \"
    - \,    

6. [セキュリティ/コンプライアンス センター PowerShellに接続する](/powershell/exchange/connect-to-scc-powershell)の手順を使用して、セキュリティ/コンプライアンス センターに接続します。

    > [!NOTE]
    > 組織が [テナント レベル (パブリック プレビュー) で Microsoft 365 のカスタム キー](customer-key-tenant-level.md#overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview) を設定している場合、完全なデータ一致によって暗号化機能が自動的に使用されます。これは、商用クラウドの E5 ライセンステナントでのみ使用できます。

7. 以下のコマンドレットを一度に 1 つずつ実行して、スキーマを更新します。

    `$edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0`
    
    `Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true`

8. 必要に応じて、新しいスキーマ バージョンと一致するようにデータ ファイルを更新します

    > [!TIP]
    > オプションとして、アップロードする前に、以下を実行して csv ファイルに対して検証を実行することもできます。
    >
    >`EdmUploadAgent.exe /ValidateData /DataFile [data file] [schema file]`
    >
    >すべての EdmUploadAgent.exe > サポートされているパラメータの詳細情報については
    >
    > `EdmUploadAgent.exe /?`

9. (管理者として) コマンドプロンプト ウィンドウを開き、次のコマンドを実行して機密データをハッシュおよびアップロードします。

    `EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Salt [custom salt] /Schema [Schema file]`


## <a name="related-articles"></a>関連記事

- [完全なデータ一致に基づく機密情報の種類の詳細](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
- [機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)
- [カスタムの機密情報の種類](./sensitive-information-type-learn-about.md)
- [データ損失防止について](dlp-learn-about-dlp.md)
- [Microsoft Defender for Cloud Apps](/cloud-app-security)
- [New-DlpEdmSchema](/powershell/module/exchange/new-dlpedmschema)
