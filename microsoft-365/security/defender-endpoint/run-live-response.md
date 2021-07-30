---
title: デバイスでライブ応答コマンドを実行する
description: デバイスで一連のライブ応答コマンドを実行する方法について説明します。
keywords: apis、graph api、サポートされている API、ライブラリへのアップロード
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 9c974da84dfffeeb655e29e934e2fe37c9af94bc
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2021
ms.locfileid: "53650933"
---
#  <a name="run-live-response-commands-on-a-device"></a>デバイスでライブ応答コマンドを実行する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)


[!include[Prerelease information](../../includes/prerelease.md)]

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明

デバイスで一連のライブ応答コマンドを実行する

## <a name="limitations"></a>制限事項

1.  この API のレート制限は、1 分あたり 10 回の呼び出しです (追加の要求は HTTP 429 で応答されます)。

2.  25 の同時実行セッション (調整制限を超える要求は"429 - 要求が多すぎます" という応答を受け取ります)。

3.  コンピューターが使用できない場合、セッションは最大 3 日間キューに入れられます。

4.  RunScript コマンドは 10 分後にタイムアウトします。

5.  ライブ応答コマンドが失敗すると、フォローしているすべてのアクションは実行されません。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可を選択する方法など、詳細については、「開始する」 [を参照してください](apis-intro.md)。

|アクセス許可の種類|アクセス許可|アクセス許可の表示名|
|---|---|---|
|アプリケーション|Machine.LiveResponse|特定のコンピューターでライブ応答を実行する|
|委任 (職場または学校のアカウント)|Machine.LiveResponse|特定のコンピューターでライブ応答を実行する|

## <a name="http-request"></a>HTTP 要求

```HTTP
POST https://api.securitycenter.microsoft.com/API/machines/{machine_id}/runliveresponse
```

## <a name="request-headers"></a>要求ヘッダー

|名前|種類|説明|
|---|---|---|
|Authorization|String|ベアラー\<token>\. 必須です。|
|Content-Type|string|application/json. Required.|

## <a name="request-body"></a>要求本文

|パラメーター|種類|説明|
|---|---|---|
|コメント|文字列|アクションに関連付けるコメント。|
|コマンド|配列|実行するコマンド。 使用できる値は PutFile、RunScript、GetFile です。|

**コマンド**:

|コマンドの種類|パラメーター|説明|
|---|---|---|
|PutFile|キー: FileName <p> 値: \<file name\>|ライブラリからデバイスにファイルを置く。 ファイルは作業フォルダーに保存され、デバイスが既定で再起動すると削除されます。
|RunScript|キー: ScriptName <br> 値: \<Script from library\> <p> キー: Args <br> 値: \<Script arguments\>|デバイス上のライブラリからスクリプトを実行します。 <p>  Args パラメーターはスクリプトに渡されます。 <p> 10 分後のタイムアウト。|
|GetFile|キー: パス <br> 値: \<File path\>|デバイスからファイルを収集します。 注: パス内の円記号はエスケープする必要があります。|

## <a name="response"></a>応答

- 成功した場合、このメソッドは 200 Ok を返します。

  アクション エンティティ。 指定した ID を持つコンピューターが見つからない場合 - 404 Not Found。

## <a name="example"></a>例

### <a name="request-example"></a>要求の例

以下は、要求の例です。

```HTTP
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runliveresponse

```JSON
{
   "Commands":[
      {
         "type":"RunScript",
         "params":[
            {
               "key":"ScriptName",
               "value":"minidump.ps1"
            },
            {
               "key":"Args",
               "value":"OfficeClickToRun"
            }

         ]
      },
      {
         "type":"GetFile",
         "params":[
            {
               "key":"Path",
               "value":"C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
            }
         ]
      }
   ],
   "Comment":"Testing Live Response API"
}
```

### <a name="response-example"></a>応答の例

以下は、応答の例です。

```HTTP
HTTP/1.1 200 Ok
```

コンテンツタイプ: application/json

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions/$entity",
    "id": "{machine_action_id}",
    "type": "LiveResponse",
    "requestor": "analyst@microsoft.com",
    "requestorComment": "Testing Live Response API",
    "status": "Pending",
    "machineId": "{machine_id}",
    "computerDnsName": "hostname",
    "creationDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "lastUpdateDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "errorHResult": 0,
    "commands": [
        {
            "index": 0,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "RunScript",
                "params": [
                    {
                        "key": "ScriptName",
                        "value": "minidump.ps1"
                    },{
                        "key": "Args",
                        "value": "OfficeClickToRun"
                    }
                ]
            }
        }, {
            "index": 1,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "GetFile",
                "params": [{
                        "key": "Path", "value": "C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
                    }
                ]
            }
        }
    ]
}
```

## <a name="related-topics"></a>関連項目

- [コンピューター アクション API の取得](get-machineaction-object.md)
- [ライブ応答結果の取得](get-live-response-result.md)
- [マシン アクションのキャンセル](cancel-machine-action.md)
