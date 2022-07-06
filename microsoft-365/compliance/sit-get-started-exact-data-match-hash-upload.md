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
ms.openlocfilehash: dd484f10cf8dad76132ed2a68a34f87b253e76b3
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66641298"
---
# <a name="hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types"></a>機密情報の種類と完全に一致する機密情報のソース テーブルをハッシュしてアップロードする

この記事では、機密情報ソース テーブルをハッシュしてアップロードする方法について説明します。

## <a name="hash-and-upload-the-sensitive-information-source-table"></a>機密情報ソース テーブルをハッシュしてアップロードする

このフェーズでは、次の操作を行います。

1. カスタム セキュリティ グループとユーザー アカウントを設定する
2. EDM Upload Agent ツールを設定する
3. EDM Upload Agent ツールを使用して、機密情報ソース テーブルである salt 値を使用してハッシュし、アップロードします。

ハッシュ化とアップロードは 1 台のコンピューターで行うこともできますし、ハッシュ化のステップとアップロードのステップを分離してセキュリティを高めることもできます。

1 台のコンピューターでハッシュ化とアップロードを行う場合は、ご利用の Microsoft 365 テナントに直接接続可能なコンピューターから行う必要があります。 これには、クリア テキストの機密情報ソース テーブル ファイルがハッシュのためにそのコンピューター上にある必要があります。

直接アクセス コンピューターでクリア テキストの機密情報ソース テーブル ファイルを公開しない場合は、セキュリティで保護された場所にあるコンピューターでハッシュし、アップロードのために Microsoft 365 テナントに直接接続できるコンピューターにハッシュ ファイルと salt ファイルをコピーできます。 分離されたハッシュとアップロードのシナリオでは、両方のコンピューターに EDMUploadAgent が必要です。

> [!IMPORTANT]
> 完全一致スキーマと機密情報の種類ウィザードを使用してスキーマ ファイルを作成した場合は、まだスキーマをダウンロードしていない場合は、この手順のスキーマをダウンロード ***する必要があります*** 。 [「EDM スキーマ ファイルを XML 形式でエクスポート](sit-get-started-exact-data-match-create-schema.md#export-of-the-edm-schema-file-in-xml-format)する」を参照してください。

> [!NOTE]
> 組織が [テナント レベルで Microsoft 365 の顧客キーを](customer-key-overview.md)設定している場合、データの完全一致によって、その暗号化機能が自動的に使用されます。 この機能を利用できるのは、商用クラウド内の E5 ライセンスが割り当てられたテナントのみです。

### <a name="best-practices"></a>ベスト プラクティス

機密データのハッシュとアップロードのプロセスを分離して、プロセス内の問題をより簡単に分離できるようにします。

運用環境に入ったら、ほとんどの場合、2 つの手順を別々にしてください。 分離されたコンピューターでハッシュ 処理を実行し、アップロード用のファイルをインターネットに接続するコンピューターに転送すると、インターネットへの接続が原因で侵害された可能性があるコンピューターのクリア テキスト形式で実際のデータを使用できなくなることが保証されます。

### <a name="ensure-your-sensitive-data-table-doesnt-have-formatting-issues"></a>機密データ テーブルに書式設定の問題がないことを確認する

機密データをハッシュしてアップロードする前に、検索を実行して、コンテンツの解析で問題が発生する可能性がある特殊文字の存在を検証します。
次の構文で EDM アップロード エージェントを使用して、テーブルが EDM で使用するのに適した形式であることを検証できます。

```powershell
EdmUploadAgent.exe /ValidateData /DataFile [data file] /Schema [schema file]
```

ツールが列数の不一致を示している場合は、テーブル内の値内にコンマまたは引用符文字が存在し、列区切り記号と混同されていることが原因である可能性があります。 値全体を囲む場合を除き、単一引用符と二重引用符を使用すると、個々の列が開始または終了する場所がツールで誤って識別される可能性があります。

**完全な値を囲む単一引用符または二重引用符文字が見つかる場合** は、そのままにしておくことができます。

**値の中に単一引用符またはコンマが見つかる場合** は、たとえば、人の名前 Tom O'Neil や、アポストロフィ文字で始まる city 's-Gravenhage) を変更する必要があります。このような列を二重引用符で囲む機密情報テーブルの生成に使用されるデータエクスポート プロセスを変更する必要があります。

**値内に二重引用符文字が見つかった場合は**、このような問題の影響を受けにくいテーブルに Tab 区切り形式を使用することをお勧めします。

### <a name="prerequisites"></a>前提条件

- **EDM\_DataUploaders** セキュリティ グループに追加される Microsoft 365 の職場または学校のアカウント
- .NET バージョン 4.6.2 のWindows 10またはWindows Server 2016 マシン <!--4.7.2 un comment this around 9/29-->EDMUploadAgent を実行するための
- 以下のためのアップロード マシン上のディレクトリ。
  - [EDM アップロード エージェント](#links-to-edm-upload-agent-by-subscription-type)
  - .csv、.tsv、またはパイプ (|) 形式の機密アイテム ファイル( **例PatientRecords.csv)**
  - この手順で作成した出力ハッシュファイルと salt ファイル
  - **edm.xml** ファイルのデータストア名 (このサンプルでは `PatientRecords`)

#### <a name="set-up-the-security-group-and-user-account"></a>セキュリティ グループとユーザー アカウントをセットアップする

1. 全体管理者として、[サブスクリプションの適切なリンク](sit-get-started-exact-data-match-based-sits-overview.md#portal-links-for-your-subscription) を使用して管理センターにアクセスし、**EDM\_DataUploaders** という [セキュリティ グループを作成します](/office365/admin/email/create-edit-or-delete-a-security-group)。

2. **EDM\_DataUploaders** セキュリティ グループに、1 人以上のユーザーを追加します。 (これらのユーザーは機密情報のデータベースを管理します)。

### <a name="hash-and-upload-from-one-computer"></a>1 台のコンピューターからハッシュ化とアップロードを行う

このコンピュータは、ご利用の Microsoft 365 テナントに直接アクセスできる必要があります。

> [!NOTE]
> この手順を開始する前に、自分が **EDM\_DataUploaders** セキュリティ グループのメンバーであることを確認します。

> [!TIP]
>必要に応じて、機密情報ソース テーブル ファイルに対して検証を実行し、次を実行してアップロードする前にエラーを確認できます。
>
> `EdmUploadAgent.exe /ValidateData /DataFile [data file] /Schema [schema file]`
>
> サポートされているすべてのパラメーターの実行EdmUploadAgent.exe詳細については、
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

3. EDM アップロード エージェントを承認し、管理者としてコマンド プロンプト ウィンドウを開き、 **C:\EDM\Data ディレクトリに** 切り替えてから、次のコマンドを実行します。

   `EdmUploadAgent.exe /Authorize`

   > [!IMPORTANT]
   > インストールされているフォルダーから **EdmUploadAgent** を実行し、データ ファイルへの完全なパスを示す必要があります。

4. EDM_DataUploaders セキュリティ グループに追加された、Microsoft 365 の職場または学校のアカウントでサインインします。 ユーザー アカウントからご利用のテナント情報を抽出し、接続を行います。

   省略可能: 完全一致スキーマと機密情報の種類ウィザードを使用してスキーマを作成した場合は、まだこの手順で使用するためにダウンロードする ***必要があります*** 。 コマンド プロンプト ウィンドウで次のコマンドを実行します。

   ```dos
   EdmUploadAgent.exe /SaveSchema /DataStoreName <schema name> /OutputDir <path to output folder>
   ```

5. 機密データをハッシュ化してアップロートするには、コマンド プロンプト ウィンドウで次のコマンドを実行します。

   ```dos
   EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Schema [Schema file] /ColumnSeparator ["{Tab}"|"|"] /AllowedBadLinesPercentage [value]
   ```

   > [!NOTE]
   > 機密データ ファイルの既定の形式はコンマ区切り値です。 タブ区切りファイルを指定するには、/ColumnSeparator パラメーターで "{Tab}" オプションを指定するか、"|" オプションを指定してパイプ区切りファイルを指定します。
   >
   > 例: `EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml /AllowedBadLinesPercentage 5`

   機密情報テーブルに正しく書式設定されていない値がありますが、残りのデータをインポートするときに無効な行を無視する場合は、コマンドで */AllowedBadLinesPercentage* パラメーターを使用できます。 上の例では、5% のしきい値を指定しています。 つまり、行の最大 5% が無効な場合でも、ツールは機密情報テーブルをハッシュしてアップロードします。

   このコマンドは、セキュリティを強化するために、ランダムに生成された salt 値をハッシュに自動的に追加します。 オプションで独自のソルト値を使用する場合は、コマンドに **/Salt\<saltvalue\>** を追加します。 この値は 64 文字の長さにする必要があり、a-z 文字と 0-9 文字のみを使用することができます。

6. 次のコマンドを実行してアップロードの状態を確認します。

   ```dos
   EdmUploadAgent.exe /GetSession /DataStoreName \<DataStoreName\>
   ```

   例: `EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords`

   **ProcessingInProgress** にある状態を確認します。 状態が **完了** に変わるまで、数分ごとにご確認ください。 状態が完了になれば、EDM データはいつでも使用することができます。 機密情報ソース テーブル ファイルのサイズによっては、数分から数時間かかる場合があります。

> [!TIP]
> アップロードされた機密データを使用する準備ができたら、通知を受け取る場合は、「 [完全なデータ一致アクティビティの通知を作成する](sit-edm-notifications-activities.md#create-notifications-for-exact-data-match-activities)」の手順に従います。

### <a name="separate-hash-and-upload"></a>ハッシュ化とアップロードを分離する

安全な環境にあるコンピューター上でハッシュ化を実行します。 両方のコンピューターに **EDMUploadAgent** がインストールされている必要があります。

省略可能: 完全一致スキーマと機密情報の種類ウィザードを使用してスキーマを作成し、まだダウンロードしていない場合は、コマンド プロンプト ウィンドウで次のコマンドを実行して、XML 形式でファイルをダウンロードします。

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
   > 機密データ ファイルの既定の形式はコンマ区切り値です。 タブ区切りファイルを指定するには、/ColumnSeparator パラメーターで "{Tab}" オプションを指定するか、"|" オプションを指定してパイプ区切りファイルを指定します。

   **/Salt\<saltvalue\>** オプションを指定しなかった場合、このコマンドは次の拡張子を持つハッシュ化されたファイルとソルト ファイルを出力します。

   - .EdmHash
   - .EdmSalt

2. 機密情報ソース テーブル ファイル (PatientRecords) をテナントにアップロードするために使用するコンピューターに、セキュリティで保護された方法でこれらのファイルをコピーします。

3. EDM アップロード エージェントを承認し、管理者としてコマンド プロンプト ウィンドウを開き、 **C:\EDM\Data ディレクトリに** 切り替えてから、次のコマンドを実行します。

   ```dos
   EdmUploadAgent.exe /Authorize
   ```

   > [!IMPORTANT]
   > インストールされているフォルダーから **EdmUploadAgent** を実行し、データ ファイルへの完全なパスを示す必要があります。

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

7. 特定のストアへのすべてのデータ アップロードを表示する場合は、Windows コマンド プロンプトで次のコマンドを実行して、すべてのデータ ストアの一覧とその更新日時を確認します。

   ```dos
   EdmUploadAgent.exe /GetSession /DataStoreName <DataStoreName>
   ```

> [!NOTE]
> 初めて作成した後にハッシュとアップロード プロセスを自動化するには、「正確 [なデータ一致の機密情報ソース テーブル ファイルを更新](sit-use-exact-data-refresh-data.md)する」を参照してください。

## <a name="next-step"></a>次のステップ

- [機密情報の種類/ルール パッケージと完全に一致するデータを作成する](sit-get-started-exact-data-match-create-rule-package.md#create-exact-data-match-sensitive-information-typerule-package)
