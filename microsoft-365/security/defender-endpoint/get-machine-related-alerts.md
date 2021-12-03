---
title: コンピューター関連のアラート API を取得する
description: コンピューター関連のアラート API を使用する方法について説明します。 この API を使用すると、Microsoft Defender for Endpoint の特定のデバイスに関連するアラートを取得できます。
keywords: apis, graph api, サポートされている API, get, デバイス, 関連, アラート
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 49cc0fca3ae7617b86ab079daace92eb3790db94
ms.sourcegitcommit: c11d4a2b9cb891ba22e16a96cb9d6389f6482459
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2021
ms.locfileid: "61283511"
---
# <a name="get-machine-related-alerts--api"></a>コンピューター関連のアラート API を取得する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:** 
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明

特定のデバイスに [関連付](alerts.md) なすべてのアラートを取得します。

## <a name="limitations"></a>制限事項

1. 構成済みの保持期間に従って、最後に更新されたデバイスに対してクエリを実行できます。
2. この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション|Alert.Read.All|'すべてのアラートの読み取り'
アプリケーション|Alert.ReadWrite.All|'すべてのアラートの読み取りと書き込み'
委任 (職場または学校のアカウント) | Alert.Read | 'アラートの読み取り'
委任 (職場または学校のアカウント) | Alert.ReadWrite | 'アラートの読み取りと書き込み'

> [!NOTE]
> ユーザー資格情報を使用してトークンを取得する場合:
>
> - ユーザーには、少なくとも次の役割のアクセス許可が必要です。'データの表示' 。 アクセス許可の詳細については、「役割の作成と [管理」を参照してください](user-roles.md)。
> - ユーザーは、デバイス グループの設定に基づいて、デバイスにアクセスする必要があります。 デバイス グループ設定の詳細については、「デバイス グループの作成と [管理」を参照してください](machine-groups.md)。

## <a name="http-request"></a>HTTP 要求

```http
GET /api/machines/{id}/alerts
```

## <a name="request-headers"></a>要求ヘッダー

名前|種類|説明
:---|:---|:---
Authorization | String | ベアラー {token}。 **必須**。

## <a name="request-body"></a>要求本文

Empty

## <a name="response"></a>応答

成功し、デバイスが存在する場合: 200 [](alerts.md) OK 本文のアラート エンティティの一覧。 デバイスが見つからない場合:404 が見つかりません。
