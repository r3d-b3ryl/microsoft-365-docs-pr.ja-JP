---
title: 物理バッジデータをインポートするためのコネクタの設定
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
description: 管理者は、組織の物理バッジシステムから Microsoft 365 にデータをインポートするためのデータコネクタをセットアップすることができます。 これにより、このデータを insider リスク管理ポリシーで使用して、組織に対する潜在的な脅威を示す、特定のユーザーによる物理的な建物へのアクセスを検出するのに役立てることができます。
ms.openlocfilehash: 6d52879031c8801191b1a419f38a1167c1bb0688
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48204505"
---
# <a name="set-up-a-connector-to-import-physical-badging-data-preview"></a>物理バッジデータをインポートするためのコネクタを設定する (プレビュー)

Microsoft 365 コンプライアンスセンターでデータコネクタをセットアップして、従業員の生の物理アクセスイベントや、組織のバッジシステムによって生成された物理的なアクセスに関する警告などの物理的なバッジのデータをインポートすることができます。 物理アクセスポイントの例としては、建物のエントリやサーバールームまたはデータセンターへのエントリがあります。 物理 badworkflowdata は、組織内の悪意のあるアクティビティやデータの盗難から組織を保護するために、Microsoft 365 [insider リスク管理ソリューション](insider-risk-management.md) で使用できます。

物理バッジコネクタの設定は、次のタスクで構成されます。

- Azure Active Directory (azure AD) でアプリを作成して、物理バッジデータを含む JSON ペイロードを受け付ける API エンドポイントにアクセスします。

- 物理バッジデータコネクタによって定義されたスキーマを使用して JSON ペイロードを作成します。

- Microsoft 365 コンプライアンスセンターでの物理バッジデータコネクタの作成。

- スクリプトを実行して、物理バッジデータを API エンドポイントにプッシュします。

- 必要に応じて、現在の物理バッジデータをインポートするようにスクリプトが自動的に実行されるようにスケジュールします。

## <a name="before-you-set-up-the-connector"></a>コネクタを設定する前に

- 組織は、Office 365 インポートサービスが組織内のデータにアクセスできるようにするための同意を得る必要があります。 この要求に同意するには、 [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)に移動して、Microsoft 365 グローバル管理者の資格情報でサインインし、要求を承諾します。 手順3で物理バッジコネクタを正常に作成するには、この手順を完了する必要があります。

- 手順3で物理バッジコネクタを作成するユーザーには、Exchange Online のメールボックスのインポートのエクスポート役割が割り当てられている必要があります。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。 または、新しい役割グループを作成し、メールボックスインポートエクスポートの役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。 詳細については、記事「Manage role groups in Exchange Online」の「 [役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 」または「 [役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 」のセクションを参照してください。

- 組織の物理バッジシステムからデータを取得またはエクスポートする方法 (毎日) を決定し、手順2で説明されている JSON ファイルを作成する必要があります。 手順4で実行したスクリプトによって、JSON ファイルのデータが API エンドポイントにプッシュされます。

- 手順4で実行したサンプルスクリプトによって、JSON ファイルの物理バッジデータが、insider リスク管理ソリューションで使用できるようにコネクタ API にプッシュされます。 このサンプルスクリプトは、Microsoft の標準サポートプログラムまたはサービスではサポートされていません。 このサンプルスクリプトは、あらゆる種類の保証なしに提供されています。 さらに、Microsoft は、商品性、特定目的への適合性を含む一切の黙示の保証をいたしかねます。 サンプルスクリプトおよびドキュメントの使用によって発生した、またはパフォーマンスの低下によって生じるリスク全体は、そのままになります。 サンプル スクリプトおよびドキュメントを使用したこと、または使用できなかったことに伴って生じるいかなる損害 (業務利益の損失、業務の中断、業務情報の損失、金銭上の損失、その他一切の損害) についても、Microsoft、Microsoft に帰属する作者、スクリプトの作成、製造、または納入に関与したその他のすべての人員は、いかなる場合も責めを負わないものとします。

## <a name="step-1-create-an-app-in-azure-active-directory"></a>手順 1: Azure Active Directory でアプリを作成する

最初の手順として、Azure Active Directory (Azure AD) で新しいアプリを作成して登録します。 このアプリは、手順3で作成した物理的なバッジコネクタに対応しています。 このアプリを作成すると、Azure AD は物理的なバッジデータを含む JSON ペイロードのプッシュ要求を認証できるようになります。 この Azure AD アプリの作成時には、必ず次の情報を保存してください。 これらの値は、後の手順で使用します。

- Azure AD アプリケーション ID ( *アプリ id* または *クライアント id*とも呼ばれる)

- Azure AD アプリケーションシークレット ( *クライアントシークレット*とも呼ばれる)

- テナント Id ( *ディレクトリ id*とも呼ばれる)

Azure AD でアプリを作成するための詳細な手順については、「 [Microsoft identity platform を使用](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)してアプリケーションを登録する」を参照してください。

## <a name="step-2-prepare-a-json-file-with-physical-badging-data"></a>手順 2: 物理バッジデータを含む JSON ファイルを準備する

次の手順では、従業員の物理アクセスデータに関する情報を含む JSON ファイルを作成します。 「はじめに」のセクションで説明されているように、この JSON ファイルを組織の物理バッジの内容システムから生成する方法を決定する必要があります。

JSON ファイルは、コネクタが必要とするスキーマ定義に準拠している必要があります。 ここでは、JSON ファイルに必要なスキーマプロパティについて説明します。

|**プロパティ**|**説明**|**データ型**|
|:-----------|:--------------|:------------|
|UserId|従業員は、システム全体で複数のデジタル id を持つことができます。 入力には、ソースシステムによって既に解決されている Azure AD ID が必要です。 |UPN またはメールアドレス|
|その assetid|物理的な資産または物理的なアクセスポイントの参照 ID。| 英数字の文字列|
|AssetName|物理的な資産または物理アクセスポイントのフレンドリ名。|英数字の文字列|
|EventTime|アクセスのタイムスタンプ。|日付と時刻 (UTC 形式)|
|AccessStatus|`Success`またはの値`Failed`| String|
|||

必要なスキーマに準拠した JSON ファイルの例を次に示します。

```text
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
手順3で物理バッジコネクタを作成したときに、ウィザードから JSON ファイルの次のスキーマ定義をダウンロードすることもできます。

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

## <a name="step-3-create-the-physical-badging-connector"></a>手順 3: 物理バッジコネクタを作成する

次の手順では、Microsoft 365 コンプライアンスセンターで物理バッジコネクタを作成します。 手順4でスクリプトを実行すると、手順3で作成した JSON ファイルが処理され、手順1で構成した API エンドポイントにプッシュされます。 この手順では、コネクタの作成時に生成された JobId をコピーしてください。 スクリプトを実行するときは、JobId を使用します。

1. に移動し [https://compliance.microsoft.com](https://compliance.microsoft.com/) 、左側のナビゲーションで [ **データコネクタ** ] をクリックします。

2. [ **データコネクタ** ] ページの [ **物理バッジ**] の下で、[ **表示**] をクリックします。

3. [ **物理バッジ** ] ページで、[ **コネクタの追加**] をクリックします。

4. [ **認証資格情報** ] ページで、次の操作を実行し、[ **次へ**] をクリックします。
  
   1. 手順1で作成した Azure アプリケーションの Azure AD アプリケーション ID を入力するか貼り付けます。
  
   2. JSON ファイルを作成するために、参照用のサンプルスキーマをダウンロードします。
  
   3. 物理バッジコネクタの一意の名前を入力します。

5. [ **レビュー** ] ページで、設定を確認し、[ **完了** ] をクリックしてコネクタを作成します。

6. コネクタが作成されたことを確認する [状態] ページが表示されます。 このページには、ジョブ ID も含まれます。 このページから、またはコネクタのフライアウトページからジョブ ID をコピーできます。 このジョブ ID は、スクリプトを実行するときに必要になります。

   [状態] ページには、スクリプトへのリンクも含まれています。 JSON ファイルを API エンドポイントに投稿する方法については、このスクリプトを参照してください。

7. [ **完了**] をクリックします。

   新しいコネクタが [ **コネクタ** ] タブの一覧に表示されます。

8. 作成した物理的なバッジコネクタをクリックすると、フライアウトページが表示されます。このコネクタには、プロパティやコネクタに関するその他の情報が含まれています。

## <a name="step-4-run-the-script-to-post-your-json-file-containing-physical-badging-data"></a>手順 4: 物理バッジデータを含む JSON ファイルをポストするスクリプトを実行する

物理バッジコネクタを設定する次の手順では、手順1で作成した API エンドポイントに、(手順2で作成した) JSON ファイル内の物理バッジデータをプッシュするスクリプトを実行します。 参照用のサンプルスクリプトが提供されており、それを使用するか、または JSON ファイルを API エンドポイントにポストするために独自のスクリプトを作成するかを選択できます。

スクリプトを実行すると、物理バッジデータを含む JSON ファイルが Microsoft 365 組織にプッシュされ、insider リスク管理ソリューションからアクセスできるようになります。 物理バッジデータは毎日投稿することをお勧めします。 これを行うには、物理バッジシステムから毎日 JSON ファイルを生成し、そのデータをプッシュするようにスクリプトをスケジューリングする処理を自動化します。

> [!NOTE]
> API によって処理できる JSON ファイル内のレコードの最大数は5万レコードです。

1. サンプルスクリプトにアクセスするには、 [この GitHub サイト](https://github.com/microsoft/m365-hrconnector-sample-scripts/blob/master/upload_termination_records.ps1) に移動します。

2. [ **Raw** ] ボタンをクリックすると、スクリプトがテキストビューに表示されます。

3. サンプルスクリプトのすべての行をコピーして、テキストファイルに保存します。

4. 必要に応じて、組織のサンプルスクリプトを変更します。

5. ファイル名サフィックス. ps1 を使用して、Windows PowerShell スクリプトファイルとしてテキストファイルを保存します。たとえば、PhysicalBadging.ps1 のようにします。

6. ローカルコンピューターでコマンドプロンプトを開き、スクリプトを保存したディレクトリに移動します。

7. 次のコマンドを実行して、JSON ファイルの物理バッジデータを Microsoft cloud にプッシュします。例えば：

   ```powershell
   .\PhysicalBadging.ps1 -tenantId "<Tenant Id>" -appId "<Azure AD App Id>" -appSecret "<Azure AD App Secret>" -jobId "Job Id" -jsonFilePath "<records file path>"
   ```

   次の表では、このスクリプトで使用するパラメーターと、必要な値について説明します。 前の手順で取得した情報は、これらのパラメーターの値で使用されます。

   | **パラメーター**|**説明**|
   |:-------------|:--------------|
   |tenantId | これは、手順1で取得した Microsoft 365 組織の Id です。 Azure AD 管理センターの **概要** ブレードで、組織の tenantId を取得することもできます。 これは、組織を識別するために使用されます。 |
   |appId | これは、手順1で Azure AD で作成したアプリの Azure AD アプリケーション Id です。 これは、スクリプトが Microsoft 365 組織にアクセスしようとするときに、Azure AD によって認証に使用されます。                    |
   |Appsecret プレースホルダ | これは、手順1で Azure AD で作成したアプリの Azure AD アプリケーションシークレットです。 これは認証にも使用されます。                                                        |
   |jobId | これは、手順3で作成した物理バッジのジョブ Id です。 これは、物理バッジコネクタを使用して、Microsoft クラウドにプッシュされる物理バッジデータを関連付けるために使用されます。              |
   |JsonFilePath | これは、手順2で作成した JSON ファイルのローカルコンピューター (スクリプトの実行に使用している) のファイルパスです。 このファイルは、手順3で説明したサンプルスキーマに従う必要があります。|
   |||

   次の例は、各パラメーターに実際の値を使用して、物理バッジコネクタスクリプトの構文を示しています。

   ```powershell
   .\PhysicalBadging.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\physical_badging_data.json'
   ```

   アップロードが成功すると、[ **アップロードに成功しまし** た] メッセージがスクリプトに表示されます。

   複数の JSON ファイルがある場合は、各ファイルに対してスクリプトを実行する必要があります。

> [!NOTE]
> また、前のスクリプトを実行する以外の方法で、物理 badreleasedata を API エンドポイントにプッシュすることを選択することもできます。 たとえば、Postman を使用して API エンドポイントにデータをプッシュする例を次に示します。

## <a name="step-5-monitor-the-physical-badging-connector"></a>手順 5: 物理バッジコネクタを監視する

物理バッジコネクタを作成し、物理バッジデータをプッシュした後、Microsoft 365 コンプライアンスセンターでコネクタとアップロードの状態を表示できます。 定期的にスクリプトを自動的に実行するようにスケジュールする場合は、最後にスクリプトを実行した後に現在の状態を表示することもできます。

1. [https://compliance.microsoft.com](https://compliance.microsoft.com/)左側のナビゲーションに移動し、[**データコネクタ**] をクリックします。

2. [ **コネクタ** ] タブをクリックしてから、物理バッジコネクタを選択して、コネクタに関するプロパティと情報を含むフライアウトページを表示します。

   ![物理バッジの状態ポップアップページ](..\media\PhysicalBadgingStatusFlyout.png)

3. [ **前回のインポート**] で、[ **ログのダウンロード** ] リンクをクリックしてコネクタの状態ログを開く (または保存) します。 このログには、スクリプトが実行されるたびに関する情報が含まれ、CSV ファイルのデータを Microsoft クラウドにアップロードします。

   ![物理バッジコネクタログファイルには、アップロードされた JSON ファイルの行数が表示されます。](..\media\PhysicalBadgingConnectorLogFile.png)

   [ **レコードの保存** ] フィールドは、アップロードされた CSV ファイルの行数を示します。 たとえば、CSV ファイルに4つの行が含まれている場合、スクリプトによって CSV ファイル内のすべての行が正常にアップロードされると、[ **レコードの保存** ] フィールドの値は4になります。

手順4でスクリプトを実行していない場合は、スクリプトをダウンロードするためのリンクが [ **前回のインポート**] の下に表示されます。 スクリプトをダウンロードして、手順4の手順に従って実行します。

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a>オプション手順 6: スクリプトが自動的に実行されるようにスケジュールする

組織からの最新の物理バッジのデータが、insider リスク管理ソリューションなどのツールで利用できることを確認するために、毎日1回など定期的にスクリプトを自動的に実行するようにスケジュールすることをお勧めします。 また、同様の (同じではない) スケジュールで物理バッジデータを JSON ファイルに更新して、組織を退職する従業員に関する最新情報が含まれるようにする必要もあります。 ここでの目的は、物理バッジを使用して insider リスク管理ソリューションで利用できるようにするために、最新の物理バッジデータをアップロードすることです。

Windows でタスクスケジューラアプリを使用して、スクリプトを毎日自動的に実行することができます。

1. ローカルコンピューターで、Windows の [ **スタート** ] ボタンをクリックし、[ **タスクスケジューラ**] を入力します。

2. **タスクスケジューラ**アプリをクリックして開きます。

3. [ **アクション** ] セクションで、[ **タスクの作成**] をクリックします。

4. [ **全般** ] タブで、スケジュールされたタスクのわかりやすい名前を入力します。たとえば、 **物理バッジのスクリプト**です。 また、オプションの説明を追加することもできます。

5. [ **セキュリティオプション**] で、次の操作を行います。

   1. ログオンしているかどうかにかかわらず、コンピューターにログオンしている場合または実行した場合にのみスクリプトを実行するかどうかを決定します。

   2. [ **最上位の特権で実行** する] チェックボックスがオンになっていることを確認します。

6. [ **トリガー** ] タブを選択し、[ **新規**] をクリックして、次の操作を行います。

   1. [ **設定**] で [ **毎日** ] オプションを選択し、スクリプトを初めて実行する日付と時刻を選択します。 このスクリプトは毎日、指定した時刻に実行されます。

   2. [ **詳細設定**] で、[ **有効** ] チェックボックスがオンになっていることを確認します。

   3. [**OK**] をクリックします。

7. [ **Actions** ] タブを選択し、[ **新規**] をクリックして、次の操作を行います。

   ![物理バッジコネクタの新しいスケジュールされたタスクを作成するためのアクションの設定](..\media\SchedulePhysicalBadgingScript1.png)

   1. [ **アクション** ] ドロップダウンリストで、[ **プログラムの開始** ] が選択されていることを確認してください。

   2. [ **プログラム/スクリプト** ] ボックスで、[ **参照**] をクリックし、次の場所に移動して選択します。このパスは、[C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe] ボックスに表示されます。

   3. [ **引数を追加する (省略可能)** ] ボックスに、手順4で実行したのと同じスクリプトコマンドを貼り付けます。 たとえば、.\PhysicalBadging.ps1-tenantId "d5723623-11cf-b5a5-01d1506273g9"-appId "c12823b7-b55a-4989-faba-02de41bb97c3"-appSecret "MNubVGbcQDkGCnn"-jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458"-jsonFilePath "C:\Users\contosoadmin\Desktop\Data\physical_badging_data.csv"

   4. [ **開始 (省略可能)** ] ボックスに、手順4で実行したスクリプトのフォルダーの場所を貼り付けます。 たとえば、C:\Users\contosoadmin\Desktop\Scripts.

   5. [ **Ok]** をクリックして、新しいアクションの設定を保存します。

8. [ **タスクの作成** ] ウィンドウで、[ **Ok** ] をクリックして、スケジュールされたタスクを保存します。 ユーザーアカウントの資格情報の入力を求められる場合があります。

   タスクスケジューラライブラリに新しいタスクが表示されます。

   ![タスクスケジューラライブラリに新しいタスクが表示されます。](..\media\SchedulePhysicalBadgingScript2.png)

前回スクリプトが実行された日時と、次回の実行スケジュールが表示されます。 タスクをダブルクリックすると、そのタスクを編集できます。

また、コンプライアンスセンターの対応する物理バッジコネクタのフライアウトページで、最後にスクリプトが実行された日時を確認することもできます。
