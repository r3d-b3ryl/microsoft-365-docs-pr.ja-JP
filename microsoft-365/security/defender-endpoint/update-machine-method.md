---
title: コンピューター エンティティ API の更新
description: この API を使用してコンピューター タグを更新する方法について説明します。 タグと devicevalue プロパティを更新できます。
keywords: apis, graph api, supported apis, get, alert, information, id
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 2fc8fe1bc7e33a505038287e6ee6a8481d2c5aeb
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2021
ms.locfileid: "53650789"
---
# <a name="update-machine"></a>コンピューターの更新 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明

既存の Machine のプロパティを更新 [します](machine.md)。

更新可能なプロパティは次 `machineTags` のとおりです `deviceValue` 。

## <a name="limitations"></a>制限事項

1. API で使用できるコンピューターを更新できます。 
2. コンピューターを更新すると、タグ コレクションにタグが追加されます。 タグが存在する場合は、本文の tags コレクションにタグを含める必要があります。
3. この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション|Machine.ReadWrite.All|'すべてのコンピューターのコンピューター情報の読み取りおよび書き込み'
委任 (職場または学校のアカウント)|Machine.ReadWrite|'コンピューター情報の読み取りおよび書き込み'

> [!NOTE]
> ユーザー資格情報を使用してトークンを取得する場合:
> - ユーザーには、少なくとも次の役割のアクセス許可が必要です。"アラートの調査" です。 詳細については、「役割の作成 [と管理」を参照してください](user-roles.md)。
> - ユーザーは、デバイス グループ設定に基づいて、アラートに関連付けられたデバイスにアクセスできる必要があります。 詳細については、「デバイス グループの作成 [と管理」を参照してください](machine-groups.md)。

## <a name="http-request"></a>HTTP 要求

```http
PATCH /api/machines/{machineId}
```

## <a name="request-headers"></a>要求ヘッダー

名前|種類|説明
:---|:---|:---
Authorization|String|ベアラー {token}。 **必須**
Content-Type|文字列|application/json. **必須**

## <a name="request-body"></a>要求本文

要求本文で、更新する必要がある関連フィールドの値を指定します。

要求本文に含まれない既存のプロパティは、以前の値のままになるか、他のプロパティ値の変化に基づいて再計算されます。

最適なパフォーマンスを得る場合は、変更していない既存の値を含めてはならない。

プロパティ|種類|説明
:---|:---|:---
machineTags|文字列コレクション|コンピューター タグ [の](machine.md) セット。
deviceValue|Null 許容列挙|デバイス [の値](tvm-assign-device-value.md)です。 指定できる値は、'Normal'、'Low'、および 'High' です。

## <a name="response"></a>応答

成功した場合、このメソッドは 200 OK[](machine.md)を返し、更新されたプロパティを持つ応答本文の machine エンティティを返します。

本文の machine tags コレクションに既存のコンピューター タグが含まれている場合 - 400 無効な入力と、見つからないタグ/s を通知するメッセージ。

指定した ID を持つコンピューターが見つからない場合 - 404 Not Found。

## <a name="example"></a>例

### <a name="request"></a>要求

要求の例を次に示します。

```http
PATCH https://api.securitycenter.microsoft.com/api/machines/{machineId}
```

```json
{
    "deviceValue": "Normal",
    "machineTags": [
                     "Demo Device",
                     "Generic User Machine - Attack Source",
                     "Windows 10",
                     "Windows Insider - Fast"
    ]
}
```
