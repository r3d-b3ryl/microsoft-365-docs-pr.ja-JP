---
title: 物理的な不良データをインポートするコネクタをセットアップする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: 管理者は、データ コネクタをセットアップして、組織の物理的なバッド システムからデータをインポートして、Microsoft 365。 これにより、内部リスク管理ポリシーでこのデータを使用して、組織に対する内部脅威の可能性を示す可能性のある特定のユーザーによる物理的な建物へのアクセスを検出できます。
ms.openlocfilehash: cb568836c0f763682cbad5524b41d19b034d02dc
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756165"
---
# <a name="set-up-a-connector-to-import-physical-badging-data-preview"></a>物理的な不良データをインポートするコネクタをセットアップする (プレビュー)

Microsoft 365 コンプライアンス センター でデータ コネクタをセットアップして、従業員の生の物理アクセス イベントや、組織の不良システムによって生成された物理アクセス アラームなど、物理的な不良データをインポートできます。 物理アクセス ポイントの例としては、建物へのエントリ、またはサーバー ルームまたはデータ センターへのエントリがあります。 物理的な不正なデータは、Microsoft 365内部での悪意のある活動や[](insider-risk-management.md)データの盗難から組織を保護するために、インサイダー リスク管理ソリューションで使用できます。

物理不良コネクタのセットアップは、次のタスクで構成されます。

- 物理不良データAzure Active Directory含Azure AD JSON ペイロードを受け入れる API エンドポイントにアクセスするためのアプリを、Azure Active Directory (Azure AD) で作成します。

- 物理不良データ コネクタによって定義されたスキーマを使用して JSON ペイロードを作成します。

- 物理不良データ コネクタを作成する方法は、Microsoft 365 コンプライアンス センター。

- 物理不良データを API エンドポイントにプッシュするスクリプトの実行。

- 必要に応じて、スクリプトを自動的に実行して現在の物理的な不良データをインポートするスケジュールを設定します。

## <a name="before-you-set-up-the-connector"></a>コネクタをセットアップする前に

- 手順 3 で物理不良コネクタを作成するユーザーには、メールボックスインポートエクスポートの役割が割り当てられている必要Exchange Online。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 [メールボックスのインポートエクスポート] 役割は、組織の [組織の管理] 役割グループに追加Exchange Online。 または、新しい役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「グループ内の[役割グループを](/Exchange/permissions-exo/role-groups#create-role-groups)管理[](/Exchange/permissions-exo/role-groups#modify-role-groups)する」の「役割グループの作成」または「役割グループの変更」セクションを参照Exchange Online。

- 組織の物理的な不良システムからデータを取得またはエクスポートする方法 (日単位) を決定し、手順 2 で説明する JSON ファイルを作成する必要があります。 手順 4 で実行するスクリプトは、JSON ファイル内のデータを API エンドポイントにプッシュします。

- 手順 4 で実行するサンプル スクリプトは、物理的な不良データを JSON ファイルからコネクタ API にプッシュして、インサイダー リスク管理ソリューションで使用できます。 このサンプル スクリプトは、Microsoft 標準サポート プログラムまたはサービスではサポートされていません。 サンプル スクリプトは現状のまま提供され、いかなる保証も伴いません。 さらに、Microsoft は、商品性、特定目的への適合性の黙示の保証を含む、一切の黙示の保証をいたしかねます。 本サンプル スクリプトおよびドキュメントの使用または性能に起因するすべてのリスクは、お客様が負うものとします。 サンプル スクリプトおよびドキュメントを使用したこと、または使用できなかったことに伴って生じるいかなる損害 (業務利益の損失、業務の中断、業務情報の損失、金銭上の損失、その他一切の損害) についても、Microsoft、Microsoft に帰属する作者、スクリプトの作成、製造、または納入に関与したその他のすべての人員は、いかなる場合も責めを負わないものとします。

- このコネクタは、米国政府機関GCC内のMicrosoft 365環境で使用できます。 サード パーティのアプリケーションとサービスには、Microsoft 365 インフラストラクチャの外部にあるサードパーティ システムに組織の顧客データを格納、送信、処理する必要がある場合があります。したがって、Microsoft 365 コンプライアンスとデータ保護のコミットメントの対象とはなってはいけなかっています。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続する場合、これらのサード パーティ製アプリケーションが FEDRAMP に準拠しているという意味を示していません。

## <a name="step-1-create-an-app-in-azure-active-directory"></a>手順 1: アプリをアプリで作成Azure Active Directory

最初の手順は、新しいアプリを作成し、アプリに登録Azure Active Directory (Azure AD)。 アプリは、手順 3 で作成した物理的な不良コネクタに対応します。 このアプリを作成すると、Azure ADデータを含む JSON ペイロードのプッシュ要求を認証できます。 このアプリの作成中Azure AD情報を保存してください。 これらの値は、後の手順で使用されます。

- Azure AD ID (アプリ ID またはクライアント *ID* とも *呼* ばれる)

- Azure AD シークレット (クライアント シークレットとも *呼ばれる*)

- テナント ID (ディレクトリ *ID とも呼ばれる*)

アプリを作成する手順については、「アプリケーションをアプリに登録する」をAzure ADを参照[Microsoft ID プラットフォーム。](/azure/active-directory/develop/quickstart-register-app)

## <a name="step-2-prepare-a-json-file-with-physical-badging-data"></a>手順 2: 物理不良データを含む JSON ファイルを準備する

次の手順では、従業員の物理アクセス データに関する情報を含む JSON ファイルを作成します。 「開始する前に」セクションで説明したように、組織の物理的な不良システムからこの JSON ファイルを生成する方法を決定する必要があります。

JSON ファイルは、コネクタで必要なスキーマ定義に準拠している必要があります。 JSON ファイルに必要なスキーマ プロパティの説明を次に示します。

|プロパティ|説明|データ型|
|---|---|---|
|UserId|従業員は、システム全体で複数のデジタル ID を持つ可能性があります。 入力には、ソース システムによってAzure AD ID が既に解決されている必要があります。|UPN またはメール アドレス|
|AssetId|物理資産または物理アクセス ポイントの参照 ID。|英数字の文字列|
|AssetName|物理アセットまたは物理アクセス ポイントの表示名。|英数字の文字列|
|EventTime|アクセスのタイムスタンプ。|日付と時刻 (UTC 形式)|
|AccessStatus|の値 `Success` または `Failed`|文字列|
|||

必要なスキーマに準拠する JSON ファイルの例を次に示します。

```json
[
    {
        "UserId":"sarad@contoso.com"
        "AssetId":"Mid-Sec-7",
        "AssetName":"Main Building 1st Floor Mid Section",
        "EventTime":"2019-07-04T01:57:49",
        "AccessStatus":"Failed",
    },
    {
        "UserId":"pilarp@contoso.com",
        "AssetId":"Mid-Sec-7",
        "AssetName":"Main Building 1st Floor Mid Section",
        "EventTime":"2019-07-04T02:57:49",
        "AccessStatus":"Success",
    }
]
```

手順 3 で物理不良コネクタを作成するときに、ウィザードから JSON ファイルの次のスキーマ定義をダウンロードすることもできます。

```text
{
   "title" : "Physical Badging Signals",
   "description" : "Access signals from physical badging systems",
   "DataType" : {
      "description" : "Identify what is the data type for input signal",
      "type" : "string",
   },
   "type" : "object",
   "properties": {
      "UserId" : {
         "description" : "Unique identifier AAD Id resolved by the source system",
         "type" : "string",
      },
      "AssetId": {
         "description" : "Unique ID of the physical asset/access point",
         "type" : "string",
      },
      "AssetName": {
         "description" : "friendly name of the physical asset/access point",
         "type" : "string",
      },
      "EventTime" : {
         "description" : "timestamp of access",
         "type" : "string",
      },
      "AccessStatus" : {
         "description" : "what was the status of access attempt - Success/Failed",
         "type" : "string",
      },
   }
   "required" : ["UserId", "AssetId", "EventTime" "AccessStatus"]
}
```

## <a name="step-3-create-the-physical-badging-connector"></a>手順 3: 物理的な不良コネクタを作成する

次の手順では、物理バッド コネクタをインターフェイスにMicrosoft 365 コンプライアンス センター。 手順 4 でスクリプトを実行すると、手順 3 で作成した JSON ファイルが処理され、手順 1 で構成した API エンドポイントにプッシュされます。 この手順では、コネクタの作成時に生成される JobId を必ずコピーします。 スクリプトの実行時に JobId を使用します。

1. [データ コネクタ] にMicrosoft 365 コンプライアンス センターし、[データ コネクタ]<a href="https://go.microsoft.com/fwlink/p/?linkid=2173865" target="_blank">**を選択します**</a>。

2. [物理バー **ジ] の [** データ コネクタ] ページ **で、[** 表示] を **クリックします**。

3. [物理バー **ジ] ページで、[** コネクタの追加] **をクリックします**。

4. [認証資格情報 **] ページで、** 次の操作を行い、[次へ] を **クリックします**。

   1. 手順 1 で作成Azure AD Azure アプリのアプリケーション ID を入力または貼り付けます。

   2. JSON ファイルを作成するには、参照用のサンプル スキーマをダウンロードします。

   3. 物理不良コネクタの一意の名前を入力します。

5. [確認 **] ページで** 設定を確認し、[完了] を **クリックして** コネクタを作成します。

6. コネクタが作成されたのを確認する状態ページが表示されます。 このページには、ジョブ ID も含まれる。 このページまたはコネクタのフライアウト ページからジョブ ID をコピーできます。 スクリプトを実行する場合は、このジョブ ID が必要です。

   状態ページには、スクリプトへのリンクも含まれる。 JSON ファイルを API エンドポイントに投稿する方法については、このスクリプトを参照してください。

7. **[完了]** をクリックします。

   新しいコネクタが [コネクタ] タブの一覧 **に表示** されます。

8. 作成した物理的な不良コネクタをクリックして、コネクタに関するプロパティや他の情報を含むフライアウト ページを表示します。

## <a name="step-4-run-the-script-to-post-your-json-file-containing-physical-badging-data"></a>手順 4: スクリプトを実行して、物理不良データを含む JSON ファイルを POST する

物理不良コネクタをセットアップする次の手順は、JSON ファイル (手順 2 で作成した) の物理不良データを手順 1 で作成した API エンドポイントにプッシュするスクリプトを実行することです。 参照用のサンプル スクリプトを提供し、それを使用するか、独自のスクリプトを作成して JSON ファイルを API エンドポイントに投稿することができます。

スクリプトを実行すると、物理的な不良データを含む JSON ファイルが Microsoft 365 組織にプッシュされ、内部リスク管理ソリューションからアクセスできます。 物理的な不良データを毎日投稿することをお勧めします。 これを行うには、プロセスを自動化して、物理バッド システムから毎日 JSON ファイルを生成し、スクリプトをスケジュールしてデータをプッシュします。

> [!NOTE]
> API で処理できる JSON ファイル内のレコードの最大数は 50,000 レコードです。

1. サンプル スクリプト[にアクセスGitHubこの](https://github.com/microsoft/m365-hrconnector-sample-scripts/blob/master/upload_termination_records.ps1)サイトに移動します。

2. [Raw] **ボタンを** クリックして、スクリプトをテキスト ビューに表示する

3. サンプル スクリプト内のすべての行をコピーし、テキスト ファイルに保存します。

4. 必要に応じて、組織のサンプル スクリプトを変更します。

5. テキスト ファイルをスクリプト ファイルとして保存するにはWindows PowerShellのファイル名サフィックスを使用.ps1。たとえば、PhysicalBadging.ps1。

6. ローカル コンピューターでコマンド プロンプトを開き、スクリプトを保存したディレクトリに移動します。

7. 次のコマンドを実行して、JSON ファイル内の物理不良データを Microsoft クラウドにプッシュします。例えば：

   ```powershell
   .\PhysicalBadging.ps1 -tenantId "<Tenant Id>" -appId "<Azure AD App Id>" -appSecret "<Azure AD App Secret>" -jobId "Job Id" -jsonFilePath "<records file path>"
   ```

   次の表では、このスクリプトで使用するパラメーターとその必要な値について説明します。 前の手順で取得した情報は、これらのパラメーターの値で使用されます。

   |パラメーター|説明|
   |---|---|
   |tenantId|これは、手順 1 で取得Microsoft 365組織の ID です。 組織の tenantId は、管理センターの[概要] ブレードAzure ADすることもできます。 これは、組織を識別するために使用されます。|
   |appId|これは、手順 1 Azure ADで作成したアプリのAzure AD ID です。 これは、スクリプトが組織Azure ADアクセスしようとするときに、認証に使用Microsoft 365されます。|
   |appSecret|これは、手順 1 Azure ADで作成したアプリのアプリケーション Azure ADシークレットです。 これは、認証にも使用されます。|
   |jobId|これは、手順 3 で作成した物理不良コネクタのジョブ ID です。 これは、Microsoft クラウドにプッシュされる物理不良データを物理的な不良コネクタに関連付ける場合に使用します。|
   |JsonFilePath|これは、手順 2 で作成した JSON ファイルのローカル コンピューター (スクリプトの実行に使用するファイル) のファイル パスです。 このファイルは、手順 3 で説明されているサンプル スキーマに従う必要があります。|
   |||

   各パラメーターの実際の値を使用する物理バッド コネクタ スクリプトの構文の例を次に示します。

   ```powershell
   .\PhysicalBadging.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\physical_badging_data.json'
   ```

   アップロードが成功した場合、スクリプトは成功したメッセージアップロード **表示** します。

   複数の JSON ファイルがある場合は、ファイルごとにスクリプトを実行する必要があります。

> [!NOTE]
> 前のスクリプトを実行する以外の方法で、物理不良データを API エンドポイントにプッシュすることもできます。 たとえば、Postman を使用してデータを API エンドポイントにプッシュするサンプルを次に示します。

## <a name="step-5-monitor-the-physical-badging-connector"></a>手順 5: 物理的な不良コネクタを監視する

物理的な不良コネクタを作成し、物理的な不良データをプッシュした後、コネクタを表示し、ファイルの状態をアップロードMicrosoft 365 コンプライアンス センター。 スクリプトを定期的に自動的に実行するスケジュールを設定した場合は、前回スクリプトを実行した後に現在の状態を表示することもできます。

1. [データ コネクタ] にMicrosoft 365 コンプライアンス センターし、[データ コネクタ]<a href="https://go.microsoft.com/fwlink/p/?linkid=2173865" target="_blank">**を選択します**</a>。

2. [コネクタ **] タブをクリック** し、物理的な不良コネクタを選択して、フライアウト ページを表示します。 このページには、コネクタに関するプロパティと情報が含まれる。

   ![物理的な不良コネクタの状態のフライアウト ページ。](..\media\PhysicalBadgingStatusFlyout.png)

3. [ **最後のインポート]** で、[ログのダウンロード] リンク **を** クリックして、コネクタの状態ログを開く (または保存) します。 このログには、スクリプトが実行され、CSV ファイルから Microsoft クラウドにデータをアップロードする度に関する情報が含まれます。

   ![物理不良コネクタ ログ ファイルには、アップロードされた JSON ファイルの番号行が表示されます。](..\media\PhysicalBadgingConnectorLogFile.png)

   **[RecordsSaved] フィールド** は、アップロードした CSV ファイル内の行数を示します。 たとえば、CSV ファイルに 4 行が含まれている場合、スクリプトが CSV ファイル内のすべての行を正常にアップロードした場合 **、RecordsSaved** フィールドの値は 4 になります。

手順 4 でスクリプトを実行していない場合、スクリプトをダウンロードするリンクが [最後のインポート] の下 **に表示されます**。 スクリプトをダウンロードし、手順 4 の手順に従って実行できます。

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a>(省略可能)手順 6: スクリプトを自動的に実行するスケジュールを設定する

組織の最新の物理的な不良データをインサイダー リスク管理ソリューションなどのツールで利用するには、スクリプトを 1 日に 1 回など定期的に自動的に実行するようにスケジュールすることをお勧めします。 また、物理的な不良データを同様のスケジュール (同じではない場合) の JSON ファイルに更新して、組織を離れる従業員に関する最新情報が含まれる必要があります。 目標は、最新の物理不良データをアップロードして、物理的な不良コネクタが内部リスク管理ソリューションで使用できるようすることです。

タスク スケジューラ アプリを使用すると、Windowsスクリプトを自動的に実行できます。

1. ローカル コンピューターで、[スタート] ボタンをクリックWindows **タスク** スケジューラと **入力します**。

2. タスク スケジューラ **アプリをクリック** して開きます。

3. [アクション] **セクションで** 、[タスクの作成] **をクリックします**。

4. [全般 **] タブ** で、スケジュールされたタスクのわかりやすい名前を入力します。たとえば、物理 **バッド コネクタ スクリプト です**。 オプションの説明を追加できます。

5. [ **セキュリティ オプション] で**、次の操作を行います。

   1. コンピューターにログオンしている場合にのみスクリプトを実行するか、ログオンしていないときに実行するかどうかを決定します。

   2. [最高の権限で **実行する] チェック ボックスが** オンになっていることを確認します。

6. [トリガー] **タブを選択** し、[ **新規**] をクリックし、次の操作を行います。

   1. **[設定]** で [**日** 次] オプションを選択し、スクリプトを初めて実行する日時を選択します。 スクリプトは、毎日同じ指定された時刻に実行されます。

   2. [ **詳細設定] で**、[有効] **チェック ボックスが** オンになっていることを確認します。

   3. [**OK**] をクリックします。

7. [操作] **タブを** 選択し、[ **新規**] をクリックし、次の操作を行います。

   ![物理的な不良コネクタ スクリプトの新しいスケジュールされたタスクを作成するアクション設定。](..\media\SchedulePhysicalBadgingScript1.png)

   1. [アクション **] ドロップダウン** リストで、[プログラムの開始 **] が選択されている** 必要があります。

   2. [プログラム **/スクリプト] ボックス** で、[参照] をクリックし、次の場所に移動して選択して、パスがボックスに表示C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe。

   3. [引数 **の追加 (オプション)]** ボックスに、手順 4 で実行したのと同じスクリプト コマンドを貼り付けます。 たとえば、 .\PhysicalBadging.ps1-tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9" -appId "c12823b7-b55a-4989-faba-0 2de41bb97c3" -appSecret "MNubVGbcQDkGCnn" -jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458" -jsonFilePath "C:\Users\contosoadmin\Desktop\Data\physical_badging_data.csv"

   4. [スタート **] (オプション) ボックス** に、手順 4 で実行したスクリプトのフォルダーの場所を貼り付けます。 たとえば、C:\Users\contosoadmin\Desktop\Scripts です。

   5. **[OK] を** クリックして、新しいアクションの設定を保存します。

8. [タスクの **作成] ウィンドウで****、[OK] をクリックして**、スケジュールされたタスクを保存します。 ユーザー アカウントの資格情報の入力を求めるメッセージが表示される場合があります。

   新しいタスクがタスク スケジューラ ライブラリに表示されます。

   ![新しいタスクがタスク スケジューラ ライブラリに表示されます。](..\media\SchedulePhysicalBadgingScript2.png)

スクリプトが最後に実行された時刻と、次回の実行がスケジュールされている時間が表示されます。 タスクをダブルクリックして編集できます。

コンプライアンス センターの対応する物理的な不良コネクタのフライアウト ページでスクリプトが最後に実行された時刻を確認することもできます。
