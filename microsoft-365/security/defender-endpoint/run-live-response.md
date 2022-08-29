---
title: デバイスでライブ応答コマンドを実行する
description: デバイスで一連のライブ応答コマンドを実行する方法について説明します。
keywords: apis、graph api、サポートされている API、ライブラリへのアップロード
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 6ffed96a1587a656687826c8faee54dc57826a14
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67331431"
---
# <a name="run-live-response-commands-on-a-device"></a>デバイスでライブ応答コマンドを実行する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)


[!include[Prerelease information](../../includes/prerelease.md)]

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明

デバイスで一連のライブ応答コマンドを実行する

## <a name="limitations"></a>制限事項

1. この API のレート制限は、1 分あたり 10 回の呼び出しです (追加の要求は HTTP 429 で応答されます)。

2. 25 個の同時実行セッション (調整制限を超える要求は、"429 - 要求が多すぎます" 応答を受け取ります)。

3. マシンを使用できない場合、セッションは最大 3 日間キューに登録されます。

4. RunScript コマンドは 10 分後にタイムアウトします。

5. ライブ応答コマンドはキューに登録できず、一度に 1 つだけ実行できます。

6. この API 呼び出しを実行しようとしているマシンが、自動修復レベルが割り当てられていない RBAC デバイス グループ内にある場合は、少なくとも特定のデバイス グループの最小修復レベルを有効にする必要があります。

7. 1 つの API 呼び出しで複数のライブ応答コマンドを実行できます。 ただし、ライブ応答コマンドが失敗すると、後続のすべてのアクションは実行されません。

## <a name="minimum-requirements"></a>最小要件

デバイスでセッションを開始する前に、次の要件を満たしていることを確認してください。

- **サポートされているバージョンの Windows** を実行していることを確認します。

  デバイスは、次のいずれかのバージョンの Windows を実行している必要があります

  - **Windows 11**
  
  - **Windows 10**
    - [バージョン 1909](/windows/whats-new/whats-new-windows-10-version-1909) 以降
    - [バージョン 1903](/windows/whats-new/whats-new-windows-10-version-1903)と[KB4515384](https://support.microsoft.com/help/4515384/windows-10-update-kb4515384)
    - [バージョン1809 (RS 5)](/windows/whats-new/whats-new-windows-10-version-1809)と [kb4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)
    - [ 1803 (バージョンRS 4)](/windows/whats-new/whats-new-windows-10-version-1803) と [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)
    - [バージョン1709 (RS 3)](/windows/whats-new/whats-new-windows-10-version-1709) と[KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)

  - **Windows Server 2019 - パブリック プレビューにのみ適用**
    - バージョン 1903 以降 ( [KB4515384](https://support.microsoft.com/help/4515384/windows-10-update-kb4515384)) 以降
    - バージョン 1809 ( [KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818))
    
  - **Windows Server 2022**

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「 [作業の開始](apis-intro.md)」を参照してください。

|アクセス許可の種類|アクセス許可|アクセス許可の表示名|
|---|---|---|
|アプリケーション|Machine.LiveResponse|特定のマシンでライブ応答を実行する|
|委任 (職場または学校のアカウント)|Machine.LiveResponse|特定のマシンでライブ応答を実行する|

## <a name="http-request"></a>HTTP 要求

```HTTP
POST https://api.securitycenter.microsoft.com/API/machines/{machine_id}/runliveresponse
```

## <a name="request-headers"></a>要求ヘッダー

|名前|種類|説明|
|---|---|---|
|Authorization|String|無記名\<token>\. 必須です。|
|Content-Type|string|application/json. Required.|

## <a name="request-body"></a>要求本文

|パラメーター|種類|説明|
|---|---|---|
|コメント|文字列|アクションに関連付けるコメント。|
|コマンド|配列|実行するコマンド。 使用できる値は PutFile、RunScript、GetFile です。|

## <a name="commands"></a>コマンド

|コマンドの種類|パラメーター|説明|
|---|---|---|
|PutFile|キー: FileName <p> 値: \<file name\>|ライブラリからデバイスにファイルを書き込みます。 ファイルは作業フォルダーに保存され、デバイスが既定で再起動すると削除されます。
|RunScript|キー: ScriptName <br> 値: \<Script from library\> <p> キー: Args <br> 値: \<Script arguments\>|デバイス上のライブラリからスクリプトを実行します。 <p>  Args パラメーターはスクリプトに渡されます。 <p> 10 分後のタイムアウト。|
|GetFile|キー: パス <br> 値: \<File path\>|デバイスからファイルを収集します。 注: パス内の円記号はエスケープする必要があります。|

## <a name="response"></a>応答

- 成功した場合、このメソッドは 201 Created を返します。

  アクション エンティティ。 指定した ID を持つマシンが見つからなかった場合は 、404 が見つかりません。

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

コンテンツ タイプ: application/json

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

- [マシン アクション API を取得する](get-machineaction-object.md)
- [ライブ応答結果の取得](get-live-response-result.md)
- [マシン アクションのキャンセル](cancel-machine-action.md)
