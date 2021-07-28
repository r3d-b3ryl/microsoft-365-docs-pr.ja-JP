---
title: ライブ応答の結果を取得する
description: インデックスによって特定のライブ応答コマンドの結果を取得する方法について説明します。
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
ms.openlocfilehash: d5152940bee3637352d61fea6f251144644ca3ae
ms.sourcegitcommit: 3576c2fee77962b516236cb67dd3df847d61c527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2021
ms.locfileid: "53621909"
---
#  <a name="get-live-response-results"></a>ライブ応答の結果を取得する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明

インデックスによって特定のライブ応答コマンドの結果を取得します。

## <a name="limitations"></a>制限事項

1. この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可を選択する方法など、詳細については、「開始する」 [を参照してください](apis-intro.md)。

|アクセス許可の種類|アクセス許可|アクセス許可の表示名|
|---|---|---|
|アプリケーション|Machine.LiveResponse|特定のコンピューターでライブ応答を実行する|
|委任 (職場または学校のアカウント)|Machine.LiveResponse|特定のコンピューターでライブ応答を実行する|

## <a name="http-request"></a>HTTP 要求

```HTTP
GET https://api.securitycenter.microsoft.com/api/machineactions/{machine action
id}/GetLiveResponseResultDownloadLink(index={command-index})
```

## <a name="request-headers"></a>要求ヘッダー

|名前|種類|説明|
|---|---|---|
|Authorization|String|ベアラー {トークン}。必須。|

## <a name="request-body"></a>要求本文

Empty

## <a name="response"></a>応答

成功した場合、このメソッドは、コマンドへのリンクを保持するオブジェクトを含む 200 Ok 応答コードを value プロパティ *に返* します。 このリンクは 30 分間有効であり、パッケージをローカル ストレージにダウンロードするためにすぐに使用する必要があります。 有効期限が切れたリンクは、別の呼び出しによって再作成できます。また、ライブ応答を再度実行する必要はありません。

*Runscript トランスクリプト プロパティ:*

|プロパティ|説明|
|---|---|
|name|実行されたスクリプト名|
|exit_code|実行されたスクリプトの終了コード|
|script_output|実行されたスクリプトの標準出力|
|script_error|実行されたスクリプトの標準エラー出力|

## <a name="example"></a>例

### <a name="request-example"></a>要求の例

以下は、要求の例です。

```HTTP
GET https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/GetLiveResponseResultDownloadLink(index=0)
```

### <a name="response-example"></a>応答の例

以下は、応答の例です。

HTTP/1.1 200 Ok

コンテンツタイプ: application/json

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
    "script_error":""
}
```

## <a name="related-topics"></a>関連項目

- [コンピューター アクション API の取得](get-machineaction-object.md)
- [マシン アクションのキャンセル](cancel-machine-action.md)
- [ライブ応答を実行する](run-live-response.md) 
