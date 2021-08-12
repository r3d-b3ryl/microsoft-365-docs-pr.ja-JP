---
title: マシン アクション API のキャンセル
description: 既に起動されているコンピューターアクションをキャンセルする方法について
keywords: apis, graph api,
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
ms.openlocfilehash: ff360a460884f15f14501a241bbd96939184e792
ms.sourcegitcommit: af575ade7b187af70f94db904b03f0471f56452a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2021
ms.locfileid: "53591069"
---
# <a name="cancel-machine-action-api"></a>マシン アクション API のキャンセル

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明

(完了、キャンセル、失敗) まだ最終状態ではない既に起動されているコンピューターアクションをキャンセルします。

## <a name="limitations"></a>制限事項

1. この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可を選択する方法など、詳細については、「開始する」 [を参照してください](apis-intro.md)。

|アクセス許可の種類|アクセス許可|アクセス許可の表示名|
|---|---|---|
|アプリケーション|Machine.CollectForensic <br> Machine.Isolate <br> Machine.RestrictExecution <br> Machine.Scan <br> Machine.Offboard <br> Machine.StopAndQuarantine <br> Machine.LiveResponse|forensics の収集 <br>マシンの隔離<br>コードの実行を制限する<br>  スキャン マシン<br>  マシンのオフボード<br> 停止と検疫<br> 特定のコンピューターでライブ応答を実行する|
|委任 (職場または学校のアカウント)|Machine.CollectForensic<br> Machine.Isolate  <br>Machine.RestrictExecution<br> Machine.Scan<br> Machine.Offboard<br> Machine.StopAndQuarantineMachine.LiveResponse|forensics の収集<br> マシンの隔離<br>  コードの実行を制限する<br> スキャン マシン<br>マシンのオフボード<br> 停止と検疫<br> 特定のコンピューターでライブ応答を実行する|


## <a name="http-request"></a>HTTP 要求

```
POST https://api.securitycenter.microsoft.com/api/machineactions/<machineactionid>/cancel  
```


## <a name="request-headers"></a>要求ヘッダー

|名前|種類|説明|
|---|---|---|
|Authorization|String|ベアラー {トークン}。必須。|
|Content-Type|string|application/json. Required.|

## <a name="request-body"></a>要求本文

|パラメーター|種類|説明|
|---|---|---|
|コメント|文字列|キャンセル アクションに関連付けるコメント。|

## <a name="response"></a>応答

成功した場合、このメソッドは Machine Action エンティティを持つ 200 Ok 応答コードを返します。 指定した ID を持つコンピューター アクション エンティティが見つからなかった場合 - 404 Not Found。

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

- [コンピューター アクション API の取得](get-machineaction-object.md)
