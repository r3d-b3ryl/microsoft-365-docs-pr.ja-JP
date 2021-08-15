---
title: マシン タグ API の追加と削除
description: Add or Remove machine tags API を使用して、Microsoft Defender for Endpoint のマシンのタグを追加または削除する方法について説明します。
keywords: apis、graph api、サポートされている API、タグ、マシン タグ
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
ms.openlocfilehash: 1158f0bf09b45bda17521ba7e0e472c5633492d205e60c312e93c071abb5e6fc
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53857885"
---
# <a name="add-or-remove-machine-tags-api"></a>マシン タグ API の追加と削除

**適用対象:**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明

特定のコンピューターにタグを追加または削除 [します](machine.md)。

## <a name="limitations"></a>制限事項

1. 構成済みの保持期間に従って最後に表示されたコンピューターに投稿できます。

2. この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法などの詳細については [、「Use Defender for Endpoint API」を参照してください。](apis-intro.md)

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション|Machine.ReadWrite.All|'すべてのコンピューター情報の読み取りと書き込み'
委任 (職場または学校のアカウント)|Machine.ReadWrite|'コンピューター情報の読み取りおよび書き込み'

> [!NOTE]
> ユーザー資格情報を使用してトークンを取得する場合:
>
> - ユーザーには、少なくとも次の役割のアクセス許可が必要です。'セキュリティ設定の管理' 。 詳細については、「役割の [作成と管理」を](user-roles.md) 参照してください。
> - ユーザーは、コンピューター グループの設定に基づいてコンピューターにアクセスする必要があります (詳細については、「 [コンピューター](machine-groups.md) グループの作成と管理」を参照してください)

## <a name="http-request"></a>HTTP 要求

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/tags
```

## <a name="request-headers"></a>要求ヘッダー

名前|種類|説明
:---|:---|:---
Authorization|String|ベアラー {token}。 **必須**
Content-Type|string|application/json. **必須**

## <a name="request-body"></a>要求本文

要求本文で、JSON オブジェクトに次のパラメーターを指定します。

パラメーター|種類|説明
:---|:---|:---
値|String|タグ名。 **必須**
Action|列挙|追加または削除。 使用できる値は、'Add' または 'Remove' です。 **必須**

## <a name="response"></a>応答

成功した場合、このメソッドは 200 - OK 応答コードと更新された Machine を応答本文で返します。

## <a name="example"></a>例

### <a name="request"></a>要求

コンピューター タグを追加する要求の例を次に示します。

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/tags
```

```json
{
  "Value" : "test Tag 2",
  "Action": "Add"
}
```

- コンピューター タグを削除するには、要求本文で [追加] ではなく [アクション] を [削除] に設定します。
