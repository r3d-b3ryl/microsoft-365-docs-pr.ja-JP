---
title: 機密情報の種類と完全に一致する機密情報のソース テーブルをハッシュしてアップロードする
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 機密情報の種類に一致する正確なデータの機密情報ソース テーブルをハッシュしてアップロードします。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8d3effe3d46375ffcaec268e4b3fc6d53fc5044e
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2022
ms.locfileid: "63526500"
---
# <a name="hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types"></a>機密情報の種類と完全に一致する機密情報のソース テーブルをハッシュしてアップロードする

この記事では、機密情報ソース テーブルをハッシュしてアップロードする方法を示します。

## <a name="hash-and-upload-the-sensitive-information-source-table"></a>機密情報ソース テーブルのハッシュとアップロード

このフェーズでは、次の条件を実行します。

1. カスタム セキュリティ グループとユーザー アカウントを設定する
2. エージェント ツールの EDM アップロード設定する
3. EDM アップロードエージェント ツールを使用して、ソルト値、機密情報ソース テーブルをハッシュし、アップロードします。

ハッシュ化とアップロードは 1 台のコンピューターで行うこともできますし、ハッシュ化のステップとアップロードのステップを分離してセキュリティを高めることもできます。

1 台のコンピューターでハッシュ化とアップロードを行う場合は、ご利用の Microsoft 365 テナントに直接接続可能なコンピューターから行う必要があります。 これには、クリア テキストの機密情報ソース テーブル ファイルがハッシュのためにそのコンピューター上にある必要があります。

ダイレクト アクセス コンピューターでクリア テキストの機密情報ソース テーブル ファイルを公開しない場合は、セキュリティで保護された場所にあるコンピューターでハッシュし、ハッシュ ファイルとソルト ファイルを、アップロードのために Microsoft 365 テナントに直接接続できるコンピューターにコピーできます。 分離されたハッシュとアップロードのシナリオでは、両方のコンピューターで EDMUploadAgent が必要です。

> [!IMPORTANT]
> 完全一致スキーマと機密情報の種類ウィザードを使用してスキーマ ファイルを作成した場合は、まだスキーマを作成していない場合は、この手順のスキーマをダウンロードする必要があります。 「 [EDM スキーマ ファイルを XML 形式でエクスポートする」を参照してください](sit-get-started-exact-data-match-create-schema.md#export-of-the-edm-schema-file-in-xml-format)。

> [!NOTE]
> 組織がテナント レベルで顧客[](customer-key-overview.md)キーをMicrosoft 365場合、完全一致データは自動的に暗号化機能を利用します。 この機能を利用できるのは、商用クラウド内の E5 ライセンスが割り当てられたテナントのみです。

### <a name="best-practices"></a>ベスト プラクティス

機密データのハッシュとアップロードのプロセスを分離して、プロセス内の問題を簡単に分離できます。
 
実稼働環境に入った後は、ほとんどの場合、2 つの手順を分ける必要があります。 分離されたコンピューターでハッシュ 処理を実行し、インターネットに接続するコンピューターにアップロードするファイルを転送すると、実際のデータは、インターネットへの接続により侵害された可能性があるコンピューターのクリア テキスト形式で使用できません。

### <a name="ensure-your-sensitive-data-table-doesnt-have-formatting-issues"></a>機密データ テーブルに書式設定の問題が含されていないことを確認します。 

機密データをハッシュしてアップロードする前に、検索を実行して、コンテンツの解析に問題が発生する可能性のある特殊文字の存在を検証します。 EDM アップロード エージェントを使用して、次の構文を使用して、テーブルが EDM で使用に適した形式にあるか検証できます。

```powershell
EdmUploadAgent.exe /ValidateData /DataFile [data file] /Schema [schema file] 
```

ツールが列数の不一致を示している場合は、列区切り記号と混同されているテーブルの値内にコンマまたは引用符が存在している可能性があります。 値全体を囲む場合を指定しない限り、単一引用符と二重引用符を使用すると、個々の列の開始または終了場所を誤って特定する可能性があります。 

**完全な値を囲む単一引用符または二重引用符文字が見つけた** 場合は、そのままにしておく必要があります。

値の中に単一引用符またはコンマが含まれている場合(たとえば、人物の名前 Tom O'Neil、またはアポストロフィ文字で始まる市のS-Gravenhage)、そのような列を二重引用符で囲む機密情報テーブルを生成するために使用されるデータエクスポートプロセスを変更する必要があります。

**値の内部に** 二重引用符が見つかった場合は、このような問題の影響を受けにくい表に Tab 区切り形式を使用することが望ましい場合があります。

### <a name="prerequisites"></a>前提条件

- **EDM\_DataUploaders** セキュリティ グループに追加される Microsoft 365 の職場または学校のアカウント
- .NET Windows 10 4.6.2 Windows Server 2016を持つコンピューターまたはコンピューター <!--4.7.2 un comment this around 9/29-->EDMUploadAgent を実行する場合
- 以下のためのアップロード マシン上のディレクトリ。
  - [EDM アップロード エージェント](#links-to-edm-upload-agent-by-subscription-type)
  - この例では、.csv.tsv またはパイプ (|) 形式の機密アイテムPatientRecords.csvファイル ****
  - この手順で作成した出力ハッシュ ファイルとソルト ファイル
  - **edm.xml** ファイルのデータストア名 (このサンプルでは `PatientRecords`)

#### <a name="set-up-the-security-group-and-user-account"></a>セキュリティ グループとユーザー アカウントをセットアップする

1. 全体管理者として、[サブスクリプションの適切なリンク](sit-get-started-exact-data-match-based-sits-overview.md#portal-links-for-your-subscription) を使用して管理センターにアクセスし、**EDM\_DataUploaders** という [セキュリティ グループを作成します](/office365/admin/email/create-edit-or-delete-a-security-group)。

2. **EDM\_DataUploaders** セキュリティ グループに、1 人以上のユーザーを追加します。 (これらのユーザーは機密情報のデータベースを管理します)。

### <a name="hash-and-upload-from-one-computer"></a>1 台のコンピューターからハッシュ化とアップロードを行う

このコンピュータは、ご利用の Microsoft 365 テナントに直接アクセスできる必要があります。

> [!NOTE]
> この手順を開始する前に、自分が **EDM\_DataUploaders** セキュリティ グループのメンバーであることを確認します。

> [!TIP] 
>必要に応じて、機密情報ソース テーブル ファイルに対して検証を実行して、次を実行してアップロードする前にエラーを確認できます。
>
> `EdmUploadAgent.exe /ValidateData /DataFile [data file] /Schema [schema file]`
>
> サポートされているすべてのパラメーターの詳細EdmUploadAgent.exe実行する
>
> `EdmUploadAgent.exe /?`

#### <a name="links-to-edm-upload-agent-by-subscription-type"></a>サブスクリプションの種類別の EDM アップロードエージェントへのリンク

- [商用 + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - ほとんどの商用のお客様はこれを使用する必要があります
- [GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - これは特に高セキュリティの政府機関向けクラウド加入者を対象にしています
- [DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - これは特に米国国防総省のクラウド顧客対象にしています

1. EDMUploadAgent の作業ディレクトリを作成します。 たとえば、**C:\EDM\Data** です。 そこに **PatientRecords.csv** ファイルを配置します。

2. 手順 1 で作成したディレクトリに、サブスクリプションに適した [EDM アップロードエージェント](#links-to-edm-upload-agent-by-subscription-type) をダウンロードしてインストールします。

   > [!NOTE]
   > 上記リンクにある EDMUploadAgent は、ハッシュ化されたデータに自動的にソルト値を追加するように更新されています。 または、独自のソルト値を提供することもできます。 このバージョンを使用すると、以前のバージョンの EDMUploadAgent は使用できなくなります。
   >
   > EDMUploadAgent を使用して特定のデータ ストアにデータをアップロードできるのは、1 日に 2 回だけです。

3. EDM アップロードエージェントを承認し、管理者としてコマンド プロンプト ウィンドウを開き、**C:\EDM\Data** ディレクトリに切り替えて、次のコマンドを実行します。

   `EdmUploadAgent.exe /Authorize`

> [!IMPORTANT]
> インストールされているフォルダー **から EdmUploadAgent** を実行し、データ ファイルへの完全なパスを指定する必要があります。 

4. EDM_DataUploaders セキュリティ グループに追加された、Microsoft 365 の職場または学校のアカウントでサインインします。 ユーザー アカウントからご利用のテナント情報を抽出し、接続を行います。

   省略可能: 完全データ一致スキーマと機密情報の種類ウィザードを使用してスキーマを作成した場合は、まだ使用していない場合は、この手順で使用するためにダウンロードする必要があります。 コマンド プロンプト ウィンドウで次のコマンドを実行します。

   ```dos
   EdmUploadAgent.exe /SaveSchema /DataStoreName <schema name> /OutputDir <path to output folder>
   ```

5. 機密データをハッシュ化してアップロートするには、コマンド プロンプト ウィンドウで次のコマンドを実行します。

   ```dos
   EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Schema [Schema file] /ColumnSeparator ["{Tab}"|"|"] /AllowedBadLinesPercentage [value]
   ```
   > [!NOTE]
> 機密データ ファイルの既定の形式はコンマ区切りの値です。 タブ区切りファイルを指定するには、/ColumnSeparator パラメーターで "{Tab}" オプションを指定するか、"|" オプションを指定してパイプ区切りファイルを指定します。

   例: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml /AllowedBadLinesPercentage 5**

機密情報テーブルに正しくない形式の値が含まれているが、無効な行を無視しながら残りのデータをインポートする場合は、コマンドで */AllowedBadLinesPercentage* パラメーターを使用できます。 上記の例では、5 パーセントのしきい値を指定します。 つまり、最大 5% の行が無効な場合でも、ツールは機密情報テーブルをハッシュしてアップロードします。 

このコマンドは、ランダムに生成されたソルト値をハッシュに自動的に追加し、セキュリティを強化します。 オプションで独自のソルト値を使用する場合は、コマンドに **/Salt<saltvalue>** を追加します。 この値は 64 文字の長さにする必要があり、a-z 文字と 0-9 文字のみを使用することができます。

6. 次のコマンドを実行してアップロードの状態を確認します。

   ```dos
   EdmUploadAgent.exe /GetSession /DataStoreName \<DataStoreName\>
   ```

   例: **EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords**

   **ProcessingInProgress** にある状態を確認します。 状態が **完了** に変わるまで、数分ごとにご確認ください。 状態が完了になれば、EDM データはいつでも使用することができます。 機密情報ソース テーブル ファイルのサイズによっては、数分から数時間かかる場合があります。 

> [!TIP]
> アップロードされた機密データを使用する準備が整った後に通知を受け取る場合は、「完全なデータ一致アクティビティの通知を作成する [」の手順に従います](sit-edm-notifications-activities.md#create-notifications-for-exact-data-match-activities)。

### <a name="separate-hash-and-upload"></a>ハッシュ化とアップロードを分離する

安全な環境にあるコンピューター上でハッシュ化を実行します。 両方のコンピューターに **EDMUploadAgent が** インストールされている必要があります。

省略可能: 完全データ一致スキーマと機密情報の種類ウィザードを使用してスキーマを作成し、まだダウンロードしていない場合は、コマンド プロンプト ウィンドウで次のコマンドを実行して、XML 形式でファイルをダウンロードします。

```dos
EdmUploadAgent.exe /SaveSchema /DataStoreName <schema name> /OutputDir <path to output folder>
````

1. セキュリティで保護された環境のコンピューターで、コマンド プロンプト ウィンドウで次のコマンドを実行します。

   ```dos
   EdmUploadAgent.exe /CreateHash /DataFile [data file] /HashLocation [hash file location] /Schema [Schema file] /AllowedBadLinesPercentage [value]
   ```

   例:

   ```dos
   EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml /AllowedBadLinesPercentage 5
   ```

> [!NOTE]
> 機密データ ファイルの既定の形式はコンマ区切りの値です。 タブ区切りファイルを指定するには、/ColumnSeparator パラメーターで "{Tab}" オプションを指定するか、"|" オプションを指定してパイプ区切りファイルを指定します。


   **/Salt<saltvalue>** オプションを指定しなかった場合、このコマンドは次の拡張子を持つハッシュ化されたファイルとソルト ファイルを出力します。

   - .EdmHash
   - .EdmSalt


2. これらのファイルを安全な方法で、機密情報ソース テーブル ファイル (PatientRecords) をテナントにアップロードするために使用するコンピューターにコピーします。

3. EDM アップロードエージェントを承認し、管理者としてコマンド プロンプト ウィンドウを開き、**C:\EDM\Data** ディレクトリに切り替えて、次のコマンドを実行します。

   `EdmUploadAgent.exe /Authorize`

> [!IMPORTANT]
> インストールされているフォルダー **から EdmUploadAgent** を実行し、データ ファイルへの完全なパスを指定する必要があります。 

4. EDM_DataUploaders セキュリティ グループに追加された、Microsoft 365 の職場または学校のアカウントでサインインします。 ユーザー アカウントからご利用のテナント情報を抽出し、接続を行います。

5. ハッシュされたデータをアップロードするには、Windows コマンド プロンプトで次のコマンドを実行します。

   ```dos
   EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\ /ColumnSeparator ["{Tab}"|"|"]
   ```

   例:

   ```dos
   EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\**PatientRecords.EdmHash**
   ```

6. 機密データがアップロードされたことを確認するには、コマンド プロンプト ウィンドウで次のコマンドを実行します。

   ```dos
   EdmUploadAgent.exe /GetDataStore
   ```
   データ ストアのリストと、それらが最後に更新された日時が表示されます。

7. 特定のストアへのすべてのデータ アップロードを表示する場合は、Windows コマンド プロンプトで次のコマンドを実行して、すべてのデータ ストアの一覧と更新時を確認します。

   ```dos
   EdmUploadAgent.exe /GetSession /DataStoreName <DataStoreName>
   ```
     
## <a name="next-step"></a>次のステップ

- [機密情報の種類/ルール パッケージと完全に一致するデータを作成する](sit-get-started-exact-data-match-create-rule-package.md#create-exact-data-match-sensitive-information-typerule-package)

