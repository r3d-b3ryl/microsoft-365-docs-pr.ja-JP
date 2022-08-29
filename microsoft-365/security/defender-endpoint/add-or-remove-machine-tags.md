---
title: マシン タグ API の追加または削除
description: マシン タグの追加と削除 API を使用して、Microsoft Defender for Endpointでコンピューターのタグを追加または削除する方法について説明します。
keywords: apis, graph api, サポートされている API, タグ, マシン タグ
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
ms.technology: m365d
ms.custom: api
ms.openlocfilehash: f5a4a232e7752ae990c1f32ca69653c45baecb8b
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67328103"
---
# <a name="add-or-remove-machine-tags-api"></a>マシン タグ API の追加または削除

**適用対象:**

- [Microsoft Defender for Endpoint プラン 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint プラン 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明

特定のコンピューターにタグを追加または削除 [します](machine.md)。

## <a name="limitations"></a>制限事項

1. 構成された保有期間に従って、最後に表示されたマシンに投稿できます。

2. この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「[Defender for Endpoint API の使用」を](apis-intro.md)参照してください。

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション|Machine.ReadWrite.All|'すべてのマシン情報の読み取りと書き込み'
委任 (職場または学校のアカウント)|Machine.ReadWrite|'マシン情報の読み取りと書き込み'

> [!NOTE]
> ユーザー資格情報を使用してトークンを取得する場合:
>
> - ユーザーには、少なくとも次のロールアクセス許可が必要です:"セキュリティ設定の管理"。 詳細については、「 [ロールの作成と管理](user-roles.md) 」を参照してください。
> - ユーザーは、マシン グループの設定に基づいてマシンにアクセスする必要があります (詳細については、「 [マシン グループの作成と管理](machine-groups.md) 」を参照してください)

## <a name="http-request"></a>HTTP 要求

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/tags
```

## <a name="request-headers"></a>要求ヘッダー

名前|種類|説明
:---|:---|:---
Authorization|String|ベアラー {token}。 **必須**。
Content-Type|string|application/json. **必須**。

## <a name="request-body"></a>要求本文

要求本文で、次のパラメーターを含む JSON オブジェクトを指定します。

パラメーター|種類|説明
:---|:---|:---
値|String|タグ名。 **必須**。
アクション|列挙|追加または削除します。 使用できる値は、'Add' または 'Remove' です。 **必須**。

## <a name="response"></a>応答

成功した場合、このメソッドは 200 - OK 応答コードと、応答本文で更新された Machine を返します。

## <a name="example"></a>例

### <a name="request"></a>要求

マシン タグを追加する要求の例を次に示します。

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/tags
```

```json
{
  "Value" : "test Tag 2",
  "Action": "Add"
}
```

- マシン タグを削除するには、要求本文で [追加] ではなく [削除] にアクションを設定します。
