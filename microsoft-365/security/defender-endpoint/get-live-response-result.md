---
title: ライブ応答の結果を取得する
description: インデックスによって特定のライブ応答コマンドの結果を取得する方法について説明します。
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
ms.openlocfilehash: fb001d0212b6eabcbabd0a2f5c3a108e7a1a9c33
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67324432"
---
# <a name="get-live-response-results"></a>ライブ応答の結果を取得する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

[!include[Prerelease information](../../includes/prerelease.md)]

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明

インデックスによって特定のライブ応答コマンドの結果を取得します。

## <a name="limitations"></a>制限事項

1. この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。

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
アプリケーション|Machine.Read.All|''すべてのマシン プロファイルを読み取る''
アプリケーション|"Machine.ReadWrite.All|'すべてのマシン情報の読み取りと書き込み'
|委任 (職場または学校のアカウント)|Machine.LiveResponse|特定のマシンでライブ応答を実行する|

## <a name="http-request"></a>HTTP 要求

```HTTP
GET https://api.securitycenter.microsoft.com/api/machineactions/{machine action
id}/GetLiveResponseResultDownloadLink(index={command-index})
```

## <a name="request-headers"></a>要求ヘッダー

|名前|種類|説明|
|---|---|---|
|Authorization|String|ベアラー {token}。必須。|

## <a name="request-body"></a>要求本文

Empty

## <a name="response"></a>応答

成功した場合、このメソッドは 200 を返します。コマンドへのリンクを保持するオブジェクトを含む Ok 応答コードは *value* プロパティになります。 このリンクは 30 分間有効であり、パッケージをローカル ストレージにダウンロードするためにすぐに使用する必要があります。 有効期限が切れたリンクは別の呼び出しによって再作成でき、ライブ応答を再度実行する必要はありません。

*Runscript トランスクリプトのプロパティ:*

|プロパティ|説明|
|---|---|
|script_name|実行されたスクリプト名|
|exit_code|実行されたスクリプト終了コード|
|script_output|実行されたスクリプト標準出力|
|script_errors|実行されたスクリプト標準エラー出力|

## <a name="example"></a>例

### <a name="request-example"></a>要求の例

以下は、要求の例です。

```HTTP
GET https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/GetLiveResponseResultDownloadLink(index=0)
```

### <a name="response-example"></a>応答の例

以下は、応答の例です。

HTTP/1.1 200 Ok

コンテンツ タイプ: application/json

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Edm.String",
    "value": "https://core.windows.net/investigation-actions-data/ID/CustomPlaybookCommandOutput/4ed5e7807ad1fe59b00b664fe06a0f07?se=2021-02-04T16%3A13%3A50Z&sp=r&sv=2019-07-07&sr=b&sig=1dYGe9rPvUlXBPvYSmr6/OLXPY98m8qWqfIQCBbyZTY%3D"
}
```

*ファイルの内容:*

```JSON
{
    "script_name": "minidump.ps1",
    "exit_code": 0,
    "script_output": "Transcript started, output file is C:\\ProgramData\\Microsoft\\Windows Defender Advanced Threat Protection\\Temp\\PSScriptOutputs\\PSScript_Transcript_{TRANSCRIPT_ID}.txt
C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip\n51 MB\n\u0000\u0000\u0000",
    "script_errors":""
}
```

## <a name="related-topics"></a>関連項目

- [マシン アクション API を取得する](get-machineaction-object.md)
- [マシン アクションのキャンセル](cancel-machine-action.md)
- [ライブ応答を実行する](run-live-response.md) 
