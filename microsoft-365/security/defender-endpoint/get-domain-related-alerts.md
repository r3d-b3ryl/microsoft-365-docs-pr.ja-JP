---
title: ドメイン関連のアラート API を取得する
description: Get domain related alerts API を使用して、Microsoft Defender for Endpoint の特定のドメイン アドレスに関連するアラートを取得する方法について説明します。
keywords: apis, graph api, supported apis, get, domain, related, alerts
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
ms.openlocfilehash: 5ca04c71c2a79297195f6c11ac65aa86e818ac85
ms.sourcegitcommit: 3576c2fee77962b516236cb67dd3df847d61c527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2021
ms.locfileid: "53623302"
---
# <a name="get-domain-related-alerts-api"></a>ドメイン関連のアラート API を取得する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API の説明
特定のドメイン アドレスに関連 [するアラート](alerts.md) のコレクションを取得します。


## <a name="limitations"></a>制限事項
1. 構成済みの保持期間に従って、最後に更新されたアラートに対してクエリを実行できます。
2. この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。


## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)

アクセス許可の種類 |   アクセス許可  |   アクセス許可の表示名
:---|:---|:---
アプリケーション |   Alert.Read.All |    'すべてのアラートの読み取り'
アプリケーション |   Alert.ReadWrite.All |   'すべてのアラートの読み取りと書き込み'
委任 (職場または学校のアカウント) | Alert.Read | 'アラートの読み取り'
委任 (職場または学校のアカウント) | Alert.ReadWrite | 'アラートの読み取りと書き込み'

> [!NOTE]
> ユーザー資格情報を使用してトークンを取得する場合:
>
> - ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'データの表示' (詳細については、「 [役割](user-roles.md) の作成と管理」を参照してください)
>- 応答には、デバイス グループ設定に基づいて、ユーザーがアクセスできるデバイスに関連付けられたアラートだけが含まれます[](machine-groups.md)(詳細については、「デバイス グループの作成と管理」を参照してください)

## <a name="http-request"></a>HTTP 要求
```http
GET /api/domains/{domain}/alerts
```

## <a name="request-headers"></a>要求ヘッダー

| ヘッダー        | 値  |
|:--------------|:-------|
| Authorization | String |

## <a name="request-body"></a>要求本文

Empty

## <a name="response"></a>応答

成功した場合とドメインが存在する場合 - アラート[](alerts.md)エンティティの一覧で 200 OK。 ドメインが存在しない場合 - 404 が見つかりません。

## <a name="example"></a>例

### <a name="request"></a>要求

以下は、要求の例です。

```http
GET https://api.securitycenter.microsoft.com/api/domains/client.wns.windows.com/alerts
```
