---
title: マシン アクション API を取り消す
description: 既に起動されているマシン アクションを取り消す方法について説明します
keywords: apis、graph api、
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
ms.openlocfilehash: d5736ee3374b182f1b22f1b728ac2378eb66b66d
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67331887"
---
# <a name="cancel-machine-action-api"></a>マシン アクション API を取り消す

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/defender-endpoint)
- [Microsoft Defender for Endpoint Plan 1](/microsoft-365/security/defender-endpoint/defender-endpoint-plan-1)

[!include[Prerelease information](../../includes/prerelease.md)]

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明

まだ最終的な状態ではない (完了、キャンセル、失敗) 既に起動されたマシン アクションをキャンセルします。

## <a name="limitations"></a>制限事項

1. この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「 [作業の開始](apis-intro.md)」を参照してください。

|アクセス許可の種類|アクセス許可|アクセス許可の表示名|
|---|---|---|
|アプリケーション|Machine.CollectForensics <br> Machine.Isolate <br> Machine.RestrictExecution <br> Machine.Scan <br> Machine.Offboard <br> Machine.StopAndQuarantine <br> Machine.LiveResponse|フォレンジックを収集する <br>マシンの隔離<br>コードの実行制限<br>  コンピューターをスキャンする<br>  コンピューターのオフロード<br> 停止と検疫<br> 特定のマシンでライブ応答を実行する|
|委任 (職場または学校のアカウント)|Machine.CollectForensics<br> Machine.Isolate  <br>Machine.RestrictExecution<br> Machine.Scan<br> Machine.Offboard<br> Machine.StopAndQuarantineMachine.LiveResponse|フォレンジックを収集する<br> マシンの隔離<br>  コードの実行制限<br> コンピューターをスキャンする<br>コンピューターのオフロード<br> 停止と検疫<br> 特定のマシンでライブ応答を実行する|

## <a name="http-request"></a>HTTP 要求

```http
POST https://api.securitycenter.microsoft.com/api/machineactions/<machineactionid>/cancel
```

## <a name="request-headers"></a>要求ヘッダー

|名前|種類|説明|
|---|---|---|
|Authorization|String|ベアラー {token}。必須。|
|Content-Type|string|application/json. Required.|

## <a name="request-body"></a>要求本文

|パラメーター|種類|説明|
|---|---|---|
|コメント|文字列|取り消しアクションに関連付けるコメント。|

## <a name="response"></a>応答

成功した場合、このメソッドは Machine Action エンティティを含む 200 OK 応答コードを返します。 指定した ID を持つマシン アクション エンティティが見つからなかった場合は 、404 Not Found です。

## <a name="example"></a>例

### <a name="request"></a>要求

以下は、要求の例です。

```HTTP
POST
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/cancel
```

```JSON
{
    "Comment": "Machine action was canceled by automation"
}
```

## <a name="related-topic"></a>関連トピック

- [マシン アクション API を取得する](get-machineaction-object.md)
