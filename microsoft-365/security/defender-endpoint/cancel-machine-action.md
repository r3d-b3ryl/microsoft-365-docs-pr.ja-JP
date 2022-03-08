---
title: マシン アクション API のキャンセル
description: 既に起動されているコンピューターアクションをキャンセルする方法について
keywords: apis, graph api,
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: fc4191043e19df7fea4f350d85acd78d2eca1551
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63322913"
---
# <a name="cancel-machine-action-api"></a>マシン アクション API のキャンセル

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明

まだ最終状態ではない既に起動されているコンピューター アクションをキャンセルします (完了、取り消し、失敗)。

## <a name="limitations"></a>制限事項

1. この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「開始する」 [を参照してください](apis-intro.md)。

|アクセス許可の種類|アクセス許可|アクセス許可の表示名|
|---|---|---|
|アプリケーション|Machine.CollectForensics <br> Machine.Isolate <br> Machine.RestrictExecution <br> Machine.Scan <br> Machine.Offboard <br> Machine.StopAndQuarantine <br> Machine.LiveResponse|forensics の収集 <br>マシンの隔離<br>コードの実行制限<br>  スキャン マシン<br>  コンピューターのオフロード<br> 停止と検疫<br> 特定のコンピューターでライブ応答を実行する|
|委任 (職場または学校のアカウント)|Machine.CollectForensics<br> Machine.Isolate  <br>Machine.RestrictExecution<br> Machine.Scan<br> Machine.Offboard<br> Machine.StopAndQuarantineMachine.LiveResponse|forensics の収集<br> マシンの隔離<br>  コードの実行制限<br> スキャン マシン<br>コンピューターのオフロード<br> 停止と検疫<br> 特定のコンピューターでライブ応答を実行する|

## <a name="http-request"></a>HTTP 要求

```http
POST https://api.securitycenter.microsoft.com/api/machineactions/<machineactionid>/cancel
```

## <a name="request-headers"></a>要求ヘッダー

|名前|型|説明|
|---|---|---|
|Authorization|String|ベアラー {token}。必須。|
|Content-Type|string|application/json. Required.|

## <a name="request-body"></a>要求本文

|パラメーター|型|説明|
|---|---|---|
|コメント|文字列|キャンセル アクションに関連付けるコメント。|

## <a name="response"></a>応答

成功した場合、このメソッドは Machine Action エンティティを持つ 200 OK 応答コードを返します。 指定した ID を持つコンピューター アクション エンティティが見つからなかった場合 - 404 Not Found。

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
