---
title: マシン エンティティ API を更新する
description: この API を使用してマシン タグを更新する方法について説明します。 タグと devicevalue プロパティを更新できます。
keywords: apis, graph api, サポートされている API, get, alert, information, id
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 5674f9b8038bba646d86b02fe775525ad433dcac
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67330673"
---
# <a name="update-machine"></a>コンピューターの更新 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明

既存の[コンピューター](machine.md)のプロパティを更新します。

更新可能なプロパティは次のとおりです`machineTags`。`deviceValue`

## <a name="limitations"></a>制限事項

1. API で使用可能なマシンを更新できます。 
2. コンピューターを更新すると、タグ コレクションにタグのみが追加されます。 タグが存在する場合は、本文の tags コレクションに含まれている必要があります。
3. この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「[Microsoft Defender for Endpoint API の使用」を](apis-intro.md)参照してください。

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション|Machine.ReadWrite.All|'すべてのマシンのマシン情報の読み取りと書き込み'
委任 (職場または学校のアカウント)|Machine.ReadWrite|'マシン情報の読み取りと書き込み'

> [!NOTE]
> ユーザー資格情報を使用してトークンを取得する場合:
> - ユーザーには、少なくとも次のロールアクセス許可が必要です。"アラート調査"。 詳細については、「 [ロールの作成と管理](user-roles.md)」を参照してください。
> - ユーザーは、デバイス グループの設定に基づいて、アラートに関連付けられているデバイスにアクセスできる必要があります。 詳細については、「 [デバイス グループの作成と管理](machine-groups.md)」を参照してください。

## <a name="http-request"></a>HTTP 要求

```http
PATCH /api/machines/{machineId}
```

## <a name="request-headers"></a>要求ヘッダー

名前|種類|説明
:---|:---|:---
Authorization|String|ベアラー {token}。 **必須**。
Content-Type|文字列|application/json. **必須**。

## <a name="request-body"></a>要求本文

要求本文で、更新する必要がある関連フィールドの値を指定します。

要求本文に含まれない既存のプロパティは、以前の値のままになるか、他のプロパティ値の変化に基づいて再計算されます。

パフォーマンスを最大限に高めるには、変更されていない既存の値を含めてはなりません。

プロパティ|種類|説明
:---|:---|:---
machineTags|String collection|[マシン](machine.md) タグのセット。
deviceValue|Null 許容列挙型|[デバイスの値](tvm-assign-device-value.md)。 指定できる値は、"Normal"、"Low"、"High" です。

## <a name="response"></a>応答

成功した場合、このメソッドは 200 OK を返し、応答本文の [コンピューター](machine.md) エンティティは更新されたプロパティを持ちます。

本文の machine tags コレクションに既存のマシン タグが含まれていない場合は、すべてのタグを要求本文で指定されたタグに置き換えます。

指定した ID を持つマシンが見つからなかった場合は 、404 が見つかりません。

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
                     "Windows 10" "Windows11",
                     "Windows Insider - Fast"
    ]
}
```
