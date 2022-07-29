---
title: 物理的な不正なデータをインポートするコネクタを設定する
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: admindeeplinkCOMPLIANCE
description: 管理者は、組織の物理的な不正プログラム システムから Microsoft 365 にデータをインポートするデータ コネクタを設定できます。 これにより、内部リスク管理ポリシーでこのデータを使用して、組織に対する内部脅威の可能性を示す可能性がある特定のユーザーによる物理的な建物へのアクセスを検出するのに役立ちます。
ms.openlocfilehash: 9b4eeba7c89b5753b44e76d65dc3838182476766
ms.sourcegitcommit: 61df6377a6185a8b55e668cfb81adbd8462a9cce
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2022
ms.locfileid: "67071396"
---
# <a name="set-up-a-connector-to-import-physical-badging-data-preview"></a>物理的な不正なデータをインポートするようにコネクタを設定する (プレビュー)

Microsoft Purview コンプライアンス ポータルでデータ コネクタを設定して、従業員の生の物理アクセス イベントや組織の不正プログラム システムによって生成された物理アクセス アラームなどの物理的な不正アクセス データをインポートできます。 物理的なアクセス ポイントの例として、建物への入り口、サーバー ルームまたはデータ センターへのエントリなどがあります。 物理的な不正使用データは、Microsoft Purview [Insider Risk Management ソリューション](insider-risk-management.md) によって使用され、組織内の悪意のあるアクティビティやデータ盗難から組織を保護するのに役立ちます。

物理的な不適切なコネクタの設定は、次のタスクで構成されます。

- 物理的な不正なデータを含む JSON ペイロードを受け入れる API エンドポイントにアクセスするための Azure Active Directory (Azure AD) でのアプリの作成。

- 物理不正処理データ コネクタによって定義されたスキーマを使用して JSON ペイロードを作成する。

- コンプライアンス ポータルで物理的な不適切なデータ コネクタを作成する。

- 物理的な不正なデータを API エンドポイントにプッシュするスクリプトを実行します。

- 必要に応じて、現在物理的な不正なデータをインポートするためにスクリプトを自動的に実行するようにスケジュールします。

プレビューに参加する場合は、dcfeedback@microsoft.com のチームにお問い合わせください。

## <a name="before-you-set-up-the-connector"></a>コネクタを設定する前に

- 手順 3 で物理的な不適切なコネクタを作成するユーザーには、Data Connector 管理 ロールを割り当てる必要があります。 このロールは、コンプライアンス ポータルの **[データ コネクタ** ] ページでコネクタを追加するために必要です。 このロールは、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ & コンプライアンス センターのアクセス許可」の「 [セキュリティとコンプライアンス センターの](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)ロール」セクションを参照してください。 または、組織内の管理者がカスタムロール グループを作成し、Data Connector 管理ロールを割り当ててから、適切なユーザーをメンバーとして追加することもできます。 手順については、[Microsoft Purview コンプライアンス ポータルのアクセス許可](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)の「カスタム ロール グループの作成」セクションを参照してください。

   > [!NOTE]
   > Data Connector 管理 ロールは、現在、米国政府機関 GCC High および DoD 環境ではサポートされていません。 そのため、GCC High および DoD 環境で HR コネクタを作成するユーザーには、Exchange Onlineでメールボックスインポートエクスポートロールを割り当てる必要があります。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 Exchange Onlineの組織管理役割グループにメールボックスインポートエクスポートロールを追加できます。 または、新しい役割グループを作成し、メールボックスインポートエクスポートロールを割り当て、適切なユーザーをメンバーとして追加することもできます。 詳細については、「Exchange Onlineでの[役割グループ](/Exchange/permissions-exo/role-groups#create-role-groups)の管理」の記事の「[役割グループ](/Exchange/permissions-exo/role-groups#modify-role-groups)の作成または役割グループの変更」セクションを参照してください。

- 組織の物理的な不正使用システムから (毎日) データを取得またはエクスポートし、手順 2 で説明されている JSON ファイルを作成する方法を決定する必要があります。 手順 4 で実行するスクリプトは、JSON ファイル内のデータを API エンドポイントにプッシュします。

- 手順 4 で実行したサンプル スクリプトは、JSON ファイルからコネクタ API に物理的な不正なデータをプッシュして、インサイダー リスク管理ソリューションで使用できるようにします。 このサンプル スクリプトは、Microsoft 標準サポート プログラムまたはサービスではサポートされていません。 サンプル スクリプトは現状のまま提供され、いかなる保証も伴いません。 さらに、Microsoft は、商品性、特定目的への適合性の黙示の保証を含む、一切の黙示の保証をいたしかねます。 本サンプル スクリプトおよびドキュメントの使用または性能に起因するすべてのリスクは、お客様が負うものとします。 サンプル スクリプトおよびドキュメントを使用したこと、または使用できなかったことに伴って生じるいかなる損害 (業務利益の損失、業務の中断、業務情報の損失、金銭上の損失、その他一切の損害) についても、Microsoft、Microsoft に帰属する作者、スクリプトの作成、製造、または納入に関与したその他のすべての人員は、いかなる場合も責めを負わないものとします。

- このコネクタは、Microsoft 365 US Government クラウドの GCC 環境で使用できます。 サード パーティのアプリケーションとサービスには、Microsoft 365 インフラストラクチャの外部にあり、Microsoft Purview およびデータ保護コミットメントの対象外であるサード パーティ システムに対する組織の顧客データの保存、送信、処理が含まれる場合があります。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続することは、これらのサードパーティ アプリケーションが FEDRAMP に準拠していることを意味することを示しません。

## <a name="step-1-create-an-app-in-azure-active-directory"></a>手順 1: Azure Active Directory でアプリを作成する

最初の手順では、Azure Active Directory (Azure AD) に新しいアプリを作成して登録します。 アプリは、手順 3. で作成した物理的な不適切なコネクタに対応します。 このアプリを作成すると、Azure AD は、物理的な不正なデータを含む JSON ペイロードのプッシュ要求を認証できます。 この Azure AD アプリの作成中に、次の情報を保存してください。 これらの値は、後の手順で使用されます。

- Azure AD アプリケーション ID ( *アプリ ID* または *クライアント ID* とも呼ばれます)

- Azure AD アプリケーション シークレット ( *クライアント シークレット* とも呼ばれます)

- テナント ID ( *ディレクトリ ID* とも呼ばれます)

Azure AD でアプリを作成する手順については、「[アプリケーションをMicrosoft ID プラットフォームに登録する](/azure/active-directory/develop/quickstart-register-app)」を参照してください。

## <a name="step-2-prepare-a-json-file-with-physical-badging-data"></a>手順 2: 物理的な不正なデータを含む JSON ファイルを準備する

次の手順では、従業員の物理アクセス データに関する情報を含む JSON ファイルを作成します。 「開始する前に」セクションで説明したように、組織の物理的な不正処理システムからこの JSON ファイルを生成する方法を決定する必要があります。

JSON ファイルは、コネクタに必要なスキーマ定義に準拠している必要があります。 JSON ファイルに必要なスキーマ プロパティの説明を次に示します。

|プロパティ|説明|データ型|
|---|---|---|
|UserId|従業員は、システム全体で複数のデジタル ID を持つことができます。 入力には、ソース システムによって Azure AD ID が既に解決されている必要があります。|UPN または電子メール アドレス|
|AssetId|物理資産または物理アクセス ポイントの参照 ID。|英数字文字列|
|AssetName|物理資産または物理アクセス ポイントのフレンドリ名。|英数字文字列|
|EventTime|アクセスのタイムスタンプ。|日付と時刻 (UTC 形式)|
|AccessStatus|`Success`の値または`Failed`|String|
|||

必要なスキーマに準拠する JSON ファイルの例を次に示します。

```json
[
    {
        "UserId":"sarad@contoso.com",
        "AssetId":"Mid-Sec-7",
        "AssetName":"Main Building 1st Floor Mid Section",
        "EventTime":"2019-07-04T01:57:49",
        "AccessStatus":"Failed"
    },
    {
        "UserId":"pilarp@contoso.com",
        "AssetId":"Mid-Sec-7",
        "AssetName":"Main Building 1st Floor Mid Section",
        "EventTime":"2019-07-04T02:57:49",
        "AccessStatus":"Success"
    }
]
```

手順 3 で物理不正検出コネクタを作成するときに、ウィザードから JSON ファイルの次のスキーマ定義をダウンロードすることもできます。

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

## <a name="step-3-create-the-physical-badging-connector"></a>手順 3: 物理的な不適切なコネクタを作成する

次の手順では、コンプライアンス ポータルで物理的な不適切なコネクタを作成します。 手順 4 でスクリプトを実行すると、手順 3 で作成した JSON ファイルが処理され、手順 1 で構成した API エンドポイントにプッシュされます。 この手順では、コネクタの作成時に生成される JobId を必ずコピーします。 スクリプトを実行するときに JobId を使用します。

1. コンプライアンス ポータルに移動し、 <a href="https://go.microsoft.com/fwlink/p/?linkid=2173865" target="_blank">**データ コネクタ**</a>を選択します。

2. [**物理的な不正プログラム**] の [**データ コネクタ**] ページで、[**表示**] をクリックします。

3. [ **物理不正プログラム** ] ページで、[ **コネクタの追加**] をクリックします。

4. [ **認証資格情報** ] ページで、次の操作を行い、[ **次へ**] をクリックします。

   1. 手順 1. で作成した Azure アプリの Azure AD アプリケーション ID を入力または貼り付けます。

   2. 参照用のサンプル スキーマをダウンロードして、JSON ファイルを作成します。

   3. 物理不正接続コネクタの一意の名前を入力します。

5. [ **校閲** ] ページで設定を確認し、[ **完了]** をクリックしてコネクタを作成します。

6. コネクタが作成されたことを確認する状態ページが表示されます。 このページには、ジョブ ID も含まれています。 ジョブ ID は、このページまたはコネクタのポップアップ ページからコピーできます。 スクリプトを実行するときは、このジョブ ID が必要です。

   状態ページには、スクリプトへのリンクも含まれています。 API エンドポイントに JSON ファイルを投稿する方法については、このスクリプトを参照してください。

7. **[完了]** をクリックします。

   新しいコネクタ **が [コネクタ** ] タブの一覧に表示されます。

8. 先ほど作成した物理的な不適切なコネクタをクリックして、コネクタに関するプロパティとその他の情報を含むポップアップ ページを表示します。

## <a name="step-4-run-the-script-to-post-your-json-file-containing-physical-badging-data"></a>手順 4: スクリプトを実行して、物理的な不正なデータを含む JSON ファイルを POST する

物理不正検出コネクタを設定する次の手順は、JSON ファイル内の物理不正プログラム データ (手順 2 で作成した) を手順 1 で作成した API エンドポイントにプッシュするスクリプトを実行することです。 参照用のサンプル スクリプトが用意されており、それを使用するか、独自のスクリプトを作成して JSON ファイルを API エンドポイントに投稿するかを選択できます。

スクリプトを実行すると、物理的な不正なデータを含む JSON ファイルが Microsoft 365 組織にプッシュされ、インサイダー リスク管理ソリューションからアクセスできます。 物理的な不正使用データを毎日投稿することをお勧めします。 これを行うには、物理不正処理システムから JSON ファイルを毎日生成するプロセスを自動化し、スクリプトをスケジュールしてデータをプッシュします。

> [!NOTE]
> API で処理できる JSON ファイル内のレコードの最大数は 50,000 レコードです。

1. [この GitHub サイト](https://github.com/microsoft/m365-physical-badging-connector-sample-scripts/blob/master/push_physical_badging_records.ps1)に移動して、サンプル スクリプトにアクセスします。

2. **[未加工**] ボタンをクリックして、テキスト ビューにスクリプトを表示します。

3. サンプル スクリプト内のすべての行をコピーし、テキスト ファイルに保存します。

4. 必要に応じて、組織のサンプル スクリプトを変更します。

5. .ps1のファイル名サフィックス (PhysicalBadging.ps1など) を使用して、テキスト ファイルをWindows PowerShell スクリプト ファイルとして保存します。

6. ローカル コンピューターでコマンド プロンプトを開き、スクリプトを保存したディレクトリに移動します。

7. 次のコマンドを実行して、JSON ファイル内の物理的な不正なデータを Microsoft クラウドにプッシュします。例えば：

   ```powershell
   .\PhysicalBadging.ps1 -tenantId "<Tenant Id>" -appId "<Azure AD App Id>" -appSecret "<Azure AD App Secret>" -jobId "Job Id" -jsonFilePath "<records file path>"
   ```

   次の表では、このスクリプトで使用するパラメーターとその必要な値について説明します。 前の手順で取得した情報は、これらのパラメーターの値で使用されます。

   |パラメーター|説明|
   |---|---|
   |tenantId|これは、手順 1 で取得した Microsoft 365 組織の ID です。 Azure AD 管理センターの **[概要** ] ブレードで、組織の tenantId を取得することもできます。 これは、組織を識別するために使用されます。|
   |appId|これは、手順 1. で Azure AD で作成したアプリの Azure AD アプリケーション ID です。 これは、スクリプトが Microsoft 365 組織にアクセスしようとしたときに、認証に Azure AD によって使用されます。|
   |appSecret|これは、手順 1. で Azure AD で作成したアプリの Azure AD アプリケーション シークレットです。 これは、認証にも使用されます。|
   |jobId|これは、手順 3. で作成した物理不正検出コネクタのジョブ ID です。 これは、Microsoft クラウドにプッシュされる物理不正プログラム データを物理不正検出コネクタに関連付けるために使用されます。|
   |JsonFilePath|これは、手順 2. で作成した JSON ファイルのローカル コンピューター上のファイル パス (スクリプトの実行に使用しているファイル) です。 このファイルは、手順 3 で説明したサンプル スキーマに従う必要があります。|
   |||

   各パラメーターの実際の値を使用した物理不正解コネクタ スクリプトの構文の例を次に示します。

   ```powershell
   .\PhysicalBadging.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -jsonFilePath 'C:\Users\contosoadmin\Desktop\Data\physical_badging_data.json'
   ```

   アップロードが成功した場合は、アップロードが **成功した** メッセージがスクリプトに表示されます。

   複数の JSON ファイルがある場合は、ファイルごとにスクリプトを実行する必要があります。

> [!NOTE]
> また、前のスクリプトを実行する以外の方法で、物理的な不正なデータを API エンドポイントにプッシュすることもできます。 たとえば、Postman を使用して API エンドポイントにデータをプッシュするためのサンプルを次に示します。

## <a name="step-5-monitor-the-physical-badging-connector"></a>手順 5: 物理的な不正なコネクタを監視する

物理的な不適切なコネクタを作成し、物理的な不正プログラム データをプッシュした後、コネクタを表示し、コンプライアンス ポータルで状態をアップロードできます。 スクリプトを定期的に自動的に実行するようにスケジュールする場合は、スクリプトが最後に実行された後の現在の状態を表示することもできます。

1. コンプライアンス ポータルに移動し、 <a href="https://go.microsoft.com/fwlink/p/?linkid=2173865" target="_blank">**データ コネクタ**</a>を選択します。

2. [ **コネクタ** ] タブをクリックし、物理的な不適切なコネクタを選択してポップアップ ページを表示します。 このページには、コネクタに関するプロパティと情報が含まれています。

   ![物理不良コネクタの状態ポップアップ ページ。](..\media\PhysicalBadgingStatusFlyout.png)

3. [ **最後のインポート**] で、[ **ログのダウンロード** ] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 このログには、スクリプトが実行され、JSON ファイルから Microsoft クラウドにデータがアップロードされるたびに関する情報が含まれます。

   ![物理的な不適切なコネクタ ログ ファイルには、アップロードされた JSON ファイルのオブジェクトの数が表示されます。](..\media\PhysicalBadgingConnectorLogFile.png)

   **RecordsSaved** フィールドは、アップロードされた JSON ファイル内のレコードの数を示します。 たとえば、JSON ファイルに 4 つのレコードが含まれている場合、スクリプトが JSON ファイル内のすべてのレコードを正常にアップロードした場合、 **RecordsSaved** フィールドの値は 4 になります。 **RecordsSkipped** フィールドは、スキップされた JSON ファイル内のレコードの数を示します。 JSON ファイル内のレコードをアップロードする前に、レコードのEmail ID が検証されます。 無効なEmail ID を持つレコードはすべてスキップされ、対応するEmail ID が **EmailIdsNotSaved** フィールドに表示されます。

手順 4 でスクリプトを実行していない場合は、[ **最後のインポート**] にスクリプトをダウンロードするためのリンクが表示されます。 スクリプトをダウンロードし、手順 4 の手順に従って実行できます。

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a>(省略可能)手順 6: スクリプトを自動的に実行するようにスケジュールする

組織の最新の物理的な不適切なデータをインサイダー リスク管理ソリューションなどのツールで使用できるようにするには、スクリプトを定期的に実行するようにスケジュールすることをお勧めします (1 日に 1 回など)。 また、組織を離れた従業員に関する最新の情報が含まれるように、同様の (同じではない場合は) スケジュールで物理的な不正なデータを JSON ファイルに更新する必要もあります。 目標は、物理的な不正アクセス コネクタが内部リスク管理ソリューションで使用できるように、最新の物理的な不正プログラム データをアップロードすることです。

Windows でタスク スケジューラ アプリを使用すると、毎日スクリプトを自動的に実行できます。

1. ローカル コンピューターで Windows **スタート** ボタンをクリックし、「 **タスク スケジューラ」** と入力します。

2. **タスク スケジューラ** アプリをクリックして開きます。

3. [ **アクション]** セクションで、[ **タスクの作成**] をクリックします。

4. [ **全般** ] タブで、スケジュールされたタスクのわかりやすい名前を入力します。たとえば、 **物理的な不適切なコネクタ スクリプト** などです。 オプションの説明を追加することもできます。

5. [ **セキュリティ オプション]** で、次の操作を行います。

   1. コンピューターにログオンしている場合にのみスクリプトを実行するか、ログオンしているときに実行するかを決定します。

   2. **[最高の特権で実行]** チェック ボックスがオンになっていることを確認します。

6. [トリガー] タブ **を** 選択し、[ **新規**] をクリックして、次の操作を行います。

   1. [ **設定]** で [ **日単位** ] オプションを選択し、スクリプトを初めて実行する日付と時刻を選択します。 スクリプトは、指定された時刻に毎日実行されます。

   2. [ **詳細設定]** で、[ **有効]** チェック ボックスがオンになっていることを確認します。

   3. [**OK**] をクリックします。

7. [ **アクション]** タブを選択し、[ **新規**] をクリックして、次の操作を行います。

   ![物理的な不適切なコネクタ スクリプトの新しいスケジュールされたタスクを作成するためのアクション設定。](..\media\SchedulePhysicalBadgingScript1.png)

   1. **[アクション**] ドロップダウン リストで、[**プログラムの開始]** が選択されていることを確認します。

   2. [ **プログラム/スクリプト** ] ボックスで [ **参照**] をクリックし、次の場所に移動し、パスがボックスに表示されるように選択します:C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe。

   3. [ **引数の追加 (省略可能)]** ボックスに、手順 4 で実行したのと同じスクリプト コマンドを貼り付けます。 たとえば、 .\PhysicalBadging.ps1-tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9" -appId "c12823b7-b55a-4989-faba-02de41bb97c "appSecret "MNubVGbcQDkGCnn" -jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458" -jsonFilePath "C:\Users\contosoadmin\Desktop\Data\physical_badging_data.json"

   4. [ **Start in (省略可能)] ボックスに** 、手順 4. で実行したスクリプトのフォルダーの場所を貼り付けます。 たとえば、C:\Users\contosoadmin\Desktop\Scripts です。

   5. [ **OK] を** クリックして、新しいアクションの設定を保存します。

8. [ **タスクの作成** ] ウィンドウで、[ **OK] を** クリックしてスケジュールされたタスクを保存します。 ユーザー アカウントの資格情報の入力を求めるメッセージが表示される場合があります。

   新しいタスクがタスク スケジューラ ライブラリに表示されます。

   ![新しいタスクがタスク スケジューラ ライブラリに表示されます。](..\media\SchedulePhysicalBadgingScript2.png)

スクリプトが最後に実行されたときと、次回実行がスケジュールされた時刻が表示されます。 タスクをダブルクリックして編集できます。

また、コンプライアンス センターの対応する物理不良コネクタのポップアップ ページでスクリプトが最後に実行された時刻を確認することもできます。
