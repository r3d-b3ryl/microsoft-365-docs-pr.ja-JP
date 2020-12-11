---
title: 物理的な不良データをインポートするコネクタを設定する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: 管理者は、データ コネクタを設定して、組織の物理的なバグシステムから Microsoft 365 にデータをインポートできます。 これにより、インサイダー リスク管理ポリシーでこのデータを使用して、組織に対する内部の脅威の可能性を示す可能性のある特定のユーザーによる物理的な建物へのアクセスを検出するのに役立ちます。
ms.openlocfilehash: 7e745b42d0df79f5c39f9fa02cb1b63f164ec2a5
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620133"
---
# <a name="set-up-a-connector-to-import-physical-badging-data-preview"></a>物理的な不良データをインポートするコネクタを設定する (プレビュー)

Microsoft 365 コンプライアンス センターでデータ コネクタを設定して、従業員の生の物理アクセス イベントや、組織の不良システムによって生成された物理的なアクセス アラームなど、物理的な不良データをインポートできます。 物理的なアクセス ポイントの例として、建物へのエントリや、サーバー ルームまたはデータ センターへのエントリがあります。 物理的な不良データは、Microsoft 365 インサイ[](insider-risk-management.md)ダー リスク管理ソリューションで使用して、組織内での悪意のあるアクティビティやデータの盗難から組織を保護できます。

物理的なバグコネクタの設定は、次のタスクで構成されます。

- Azure Active Directory (Azure AD) でアプリを作成し、物理エラー データを含む JSON ペイロードを受け入れる API エンドポイントにアクセスします。

- 物理バグデータ コネクタで定義されたスキーマを使用して JSON ペイロードを作成する。

- Microsoft 365 コンプライアンス センターでの物理的な不良データ コネクタの作成。

- 物理バグデータを API エンドポイントにプッシュするスクリプトの実行。

- 必要に応じて、スクリプトが自動的に実行され、現在物理的な問題データをインポートするスケジュールを設定します。

## <a name="before-you-set-up-the-connector"></a>コネクタを設定する前に

- 手順 3 で物理バグコネクタを作成するユーザーには、Exchange Online の "Mailbox Import Export/メールボックスのインポートエクスポート" 役割が割り当てられている必要があります。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 "Mailbox Import Export/メールボックスのインポートとエクスポート" 役割は、Exchange Online の "Organization Management/組織の管理" 役割グループに追加できます。 または、新しい役割グループを作成し、Mailbox Import Export 役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「Exchange Online[で役割](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の「役割グループの作成」または「役割グループの変更」セクションを参照してください。

- 組織の物理的な不良システムから (毎日) データを取得またはエクスポートする方法を決定し、手順 2 で説明する JSON ファイルを作成する必要があります。 手順 4 で実行するスクリプトは、JSON ファイル内のデータを API エンドポイントにプッシュします。

- 手順 4 で実行するサンプル スクリプトは、JSON ファイルからコネクタ API に物理バグデータをプッシュして、インサイダー リスク管理ソリューションで使用できます。 このサンプル スクリプトは、Microsoft 標準のサポート プログラムまたはサービスではサポートされていません。 サンプル スクリプトは、いかなる種類の保証なしに、IS 形式で提供されます。 さらに、Microsoft は、商品性、特定目的への適合性を含む一切の黙示の保証をいたしかねます。 サンプル スクリプトとドキュメントの使用またはパフォーマンスから生じるリスク全体は、引き続きお持ちです。 サンプル スクリプトおよびドキュメントを使用したこと、または使用できなかったことに伴って生じるいかなる損害 (業務利益の損失、業務の中断、業務情報の損失、金銭上の損失、その他一切の損害) についても、Microsoft、Microsoft に帰属する作者、スクリプトの作成、製造、または納入に関与したその他のすべての人員は、いかなる場合も責めを負わないものとします。

## <a name="step-1-create-an-app-in-azure-active-directory"></a>手順 1: Azure Active Directory でアプリを作成する

最初の手順は、Azure Active Directory (Azure Active Directory) で新しいアプリを作成して登録AD。 アプリは、手順 3 で作成した物理的なバグ コネクタに対応します。 このアプリを作成すると、Azure ADは、物理バグデータを含む JSON ペイロードのプッシュ要求を認証できます。 この Azure アプリの作成時AD、次の情報を保存してください。 これらの値は、後の手順で使用します。

- Azure ADアプリケーション ID (アプリ ID またはクライアント *ID* とも *呼ばれる*)

- Azure AD アプリケーション シークレット (クライアント シークレットとも *呼ばれる*)

- テナント ID (ディレクトリ *ID とも呼ばれる*)

Azure AD でアプリを作成するための詳しい手順については、「Microsoft ID プラットフォームにアプリケーションを登録する」を [参照してください](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)。

## <a name="step-2-prepare-a-json-file-with-physical-badging-data"></a>手順 2: 物理的な不良データを含む JSON ファイルを準備する

次の手順では、従業員の物理的なアクセス データに関する情報を含む JSON ファイルを作成します。 開始する前のセクションで説明したように、組織の物理バグシステムからこの JSON ファイルを生成する方法を決定する必要があります。

JSON ファイルは、コネクタで必要なスキーマ定義に準拠している必要があります。 JSON ファイルに必要なスキーマ プロパティの説明を次に示します。

| プロパティ | 説明 | データ型 |
|:-----------|:--------------|:------------|
|UserId|従業員は、システム全体で複数のデジタル ID を持つ可能性があります。 入力には、ソース システムによって Azure AD ID が既に解決されている必要があります。 |UPN または電子メール アドレス|
|AssetId|物理資産または物理アクセス ポイントの参照 ID。| 英数字|
|AssetName|物理資産または物理アクセス ポイントの表示名。|英数字|
|EventTime|アクセスのタイム スタンプ。|日付と時刻 (UTC 形式)|
|AccessStatus|値または `Success``Failed`| String|
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
手順 3 で物理バグコネクタを作成するときに、ウィザードから JSON ファイルの次のスキーマ定義をダウンロードすることもできます。

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

## <a name="step-3-create-the-physical-badging-connector"></a>手順 3: 物理的なバグコネクタを作成する

次の手順では、Microsoft 365 コンプライアンス センターで物理的なバグコネクタを作成します。 手順 4 でスクリプトを実行すると、手順 3 で作成した JSON ファイルが処理され、手順 1 で構成した API エンドポイントにプッシュされます。 この手順では、コネクタの作成時に生成される JobId をコピーしてください。 スクリプトを実行するときに JobId を使用します。

1. 左側の [https://compliance.microsoft.com](https://compliance.microsoft.com/) ナビゲーションの [ **データ コネクタ]** に移動してクリックします。

2. On the **Data connectors** page under **Physical badging,** click **View**.

3. [物理バ **グ] ページで、[コネクタの** 追加] **をクリックします**。

4. [認証資格情報 **] ページで、** 次の操作を行い、[次へ] をクリック **します**。
  
   1. 手順 1 で作成AD Azure アプリの Azure アプリケーション ID を入力するか、貼り付けます。
  
   2. JSON ファイルを作成するには、参照用のサンプル スキーマをダウンロードします。
  
   3. 物理バグコネクタの一意の名前を入力します。

5. [確認 **] ページ** で設定を確認し、[完了] をクリック **して** コネクタを作成します。

6. コネクタが作成されたのを確認するステータス ページが表示されます。 このページにはジョブ ID も含まれる。 このページまたはコネクタのフライアウト ページからジョブ ID をコピーできます。 スクリプトを実行する場合は、このジョブ ID が必要です。

   ステータス ページには、スクリプトへのリンクも含まれる。 JSON ファイルを API エンドポイントにポストする方法については、このスクリプトを参照してください。

7. **[完了]** をクリックします。

   新しいコネクタが [コネクタ] タブの一覧 **に表示** されます。

8. 作成した物理的なバグコネクタをクリックして、コネクタに関するプロパティと他の情報を含むフライアウト ページを表示します。

## <a name="step-4-run-the-script-to-post-your-json-file-containing-physical-badging-data"></a>手順 4: スクリプトを実行して、物理的なエラー データを含む JSON ファイルを POST する

物理的なバグコネクタを設定する次の手順は、JSON ファイル (手順 2 で作成した) 内の物理的な不良データを手順 1 で作成した API エンドポイントにプッシュするスクリプトを実行することです。 リファレンス用のサンプル スクリプトが提供されています。このサンプル スクリプトを使用するか、独自のスクリプトを作成して JSON ファイルを API エンドポイントにポストすることができます。

スクリプトを実行すると、物理的なバグデータを含む JSON ファイルが Microsoft 365 組織にプッシュされ、インサイダー リスク管理ソリューションからアクセスできます。 物理的なバグデータは毎日投稿することをお勧めします。 これを行うには、物理バグシステムから毎日 JSON ファイルを生成するプロセスを自動化し、データをプッシュするスクリプトをスケジュールします。

> [!NOTE]
> API で処理できる JSON ファイル内のレコードの最大数は 50,000 レコードです。

1. この [GitHub サイトに移動して、](https://github.com/microsoft/m365-hrconnector-sample-scripts/blob/master/upload_termination_records.ps1) サンプル スクリプトにアクセスします。

2. **[Raw] ボタンを** クリックしてスクリプトをテキスト ビューに表示する

3. サンプル スクリプト内のすべての行をコピーし、テキスト ファイルに保存します。

4. 必要に応じて、組織のサンプル スクリプトを変更します。

5. ファイル名サフィックス .ps1 を使用Windows PowerShellスクリプト ファイルとしてテキスト ファイルを保存します。たとえば、PhysicalBadging.ps1。

6. ローカル コンピューターでコマンド プロンプトを開き、スクリプトを保存したディレクトリに移動します。

7. 次のコマンドを実行して、JSON ファイル内の物理的な不良データを Microsoft クラウドにプッシュします。例えば：

   ```powershell
   .\PhysicalBadging.ps1 -tenantId "<Tenant Id>" -appId "<Azure AD App Id>" -appSecret "<Azure AD App Secret>" -jobId "Job Id" -jsonFilePath "<records file path>"
   ```

   次の表では、このスクリプトで使用するパラメーターと、必要な値について説明します。 前の手順で取得した情報は、これらのパラメーターの値で使用されます。

   | パラメーター | 説明 |
   |:-------------|:--------------|
   |tenantId | これは、手順 1 で取得した Microsoft 365 組織の ID です。 Azure AD 管理センターの [概要]ブレードで、組織の tenantId を取得することもできます。 これは、組織を識別するために使用されます。 |
   |appId | これは、手順 1 で Azure AD作成したアプリの Azure AD ID です。 これは、スクリプトが Microsoft 365 組織にアクセスAD認証のために Azure AD によって使用されます。                    |
   |appSecret | これは、手順 1 で Azure AD作成したアプリの Azure AD アプリケーション シークレットです。 これは認証にも使用されます。                                                        |
   |jobId | これは、手順 3 で作成した物理バグコネクタのジョブ ID です。 これは、Microsoft クラウドにプッシュされる物理的な不良データを物理バグ コネクタに関連付けるのに使用されます。              |
   |JsonFilePath | これは、手順 2 で作成した JSON ファイルのローカル コンピューター上のファイル パス (スクリプトの実行に使用しているパス) です。 このファイルは、手順 3 で説明したサンプル スキーマに従う必要があります。|
   |||

   各パラメーターの実際の値を使用する物理バグコネクタ スクリプトの構文の例を次に示します。

   ```powershell
   .\PhysicalBadging.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\physical_badging_data.json'
   ```

   アップロードが成功した場合、スクリプトは [成功したアップロード] **メッセージを表示** します。

   複数の JSON ファイルがある場合は、ファイルごとにスクリプトを実行する必要があります。

> [!NOTE]
> また、前のスクリプトを実行する以外のメソッドを使用して、物理バグデータを API エンドポイントにプッシュすることもできます。 たとえば、Postman を使用してデータを API エンドポイントにプッシュするサンプルを次に示します。

## <a name="step-5-monitor-the-physical-badging-connector"></a>手順 5: 物理バグコネクタを監視する

物理的な不良コネクタを作成し、物理的なバグデータをプッシュした後、Microsoft 365 コンプライアンス センターでコネクタを表示し、状態をアップロードできます。 スクリプトが定期的に自動的に実行されるスケジュールを設定すると、スクリプトが最後に実行された後の現在の状態を表示することもできます。

1. 左側の [https://compliance.microsoft.com](https://compliance.microsoft.com/) ナビゲーションの **[データ コネクタ]** に移動してクリックします。

2. [ **コネクタ] タブを** クリックし、物理バグコネクタを選択して、フライアウト ページを表示します。 このページには、コネクタに関するプロパティと情報が含まれる。

   ![物理的なバグリング コネクタの状態のフライアウト ページ](..\media\PhysicalBadgingStatusFlyout.png)

3. [ **最後のインポート]** で、[ログ **のダウンロード]** リンクをクリックして、コネクタの状態ログを開く (または保存する) 必要があります。 このログには、スクリプトが実行され、CSV ファイルから Microsoft クラウドにデータがアップロードされるたびに関する情報が含まれます。

   ![物理バグリング コネクタ ログ ファイルには、アップロードされた JSON ファイルの番号行が表示されます。](..\media\PhysicalBadgingConnectorLogFile.png)

   **RecordsSaved フィールド** は、アップロードした CSV ファイル内の行数を示します。 たとえば、CSV ファイルに 4 行が含まれる場合、スクリプトが CSV ファイル内のすべての行を正常にアップロードした場合 **、RecordsSaved** フィールドの値は 4 になります。

手順 4 でスクリプトを実行していない場合は、スクリプトをダウンロードするリンクが [最後のインポート] の下 **に表示されます**。 スクリプトをダウンロードし、手順 4 の手順に従ってスクリプトを実行できます。

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a>(省略可能)手順 6: スクリプトが自動的に実行されるスケジュールを設定する

インサイダー リスク管理ソリューションなどのツールで組織の最新の物理的な不良データを確実に利用するには、スクリプトを定期的に (1 日に 1 回など) 自動的に実行するようにスケジュールすることをお勧めします。 また、組織を離れる従業員に関する最新情報が含まれるような (同じではない場合は) 同様のスケジュールで、物理バグデータを JSON ファイルに更新する必要があります。 目標は、物理バグリング コネクタがインサイダー リスク管理ソリューションで使用できるよう、最新の物理的な不良データをアップロードすることです。

Windows のタスク スケジューラ アプリを使用して、スクリプトを毎日自動的に実行できます。

1. ローカル コンピューターで、[Windows スタート] ボタンを **クリックし** 、「タスク スケジューラ」 **と入力します**。

2. タスク スケジューラ **アプリをクリック** して開きます。

3. [操作 **] セクションで** 、[タスクの作成] **をクリックします**。

4. [全般 **] タブ** で、スケジュールされたタスクのわかりやすい名前を入力します。たとえば、物理 **バグコネクタ スクリプトです**。 オプションの説明を追加できます。

5. [ **セキュリティ オプション] で**、次の操作を行います。

   1. コンピューターにログオンしている場合にのみスクリプトを実行するか、ログオン時に実行するかしないかを決定します。

   2. [最高特権で **実行] チェック ボックス** がオンになっていることを確認します。

6. [トリガー **] タブを選択** し、[新規] **をクリック** して、次の操作を行います。

   1. [ **設定]** で [日] **オプションを** 選択し、スクリプトを初めて実行する日時を選択します。 スクリプトは毎日同じ指定時刻に実行されます。

   2. [ **詳細設定] で**、[有効] **チェック ボックス** がオンになっていることを確認します。

   3. [**OK**] をクリックします。

7. [操作 **] タブを** 選択し、[新規] **をクリックして**、次の操作を行います。

   ![物理的なバグリング コネクタ スクリプト用の新しいスケジュールされたタスクを作成するアクション設定](..\media\SchedulePhysicalBadgingScript1.png)

   1. [操作 **] ドロップダウン** リストで、[プログラムの開始 **] が** 選択されている必要があります。

   2. [プログラム **/** スクリプト] ボックスで[参照] をクリックし、次の場所に移動して、パスがボックスに表示C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe。

   3. [引数 **の追加 ] (オプション)** ボックスに、手順 4 で実行したのと同じスクリプト コマンドを貼り付けます。 たとえば、次のようになります。 .\PhysicalBadging.ps1-tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9" -appId "c12823b7-b55a-4989-faba-02de41bb97c3" -appSecret "MNubVGbcQDkGCnn" -jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458" -jsonFilePath "C:\Users\contosoadmin\Desktop\Data\physical_badging_data.csv"

   4. [開始 **位置] (オプション)** ボックスに、手順 4 で実行したスクリプトのフォルダーの場所を貼り付けます。 たとえば、C:\Users\contosoadmin\Desktop\Scripts などです。

   5. **[OK] を** クリックして、新しいアクションの設定を保存します。

8. [タスクの **作成] ウィンドウで****、[OK]** をクリックしてスケジュールされたタスクを保存します。 ユーザー アカウントの資格情報の入力を求めるメッセージが表示される場合があります。

   新しいタスクがタスク スケジューラ ライブラリに表示されます。

   ![新しいタスクがタスク スケジューラ ライブラリに表示されます。](..\media\SchedulePhysicalBadgingScript2.png)

スクリプトが最後に実行された時刻と、次回実行がスケジュールされた時刻が表示されます。 タスクをダブルクリックして編集できます。

コンプライアンス センターの対応する物理バグコネクタのフライアウト ページでスクリプトが最後に実行された時刻を確認することもできます。
