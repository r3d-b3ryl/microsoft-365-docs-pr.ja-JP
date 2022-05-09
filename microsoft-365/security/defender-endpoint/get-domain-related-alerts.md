---
title: ドメイン関連のアラート API を取得する
description: Get domain-related alerts API を使用して、Microsoft Defender for Endpoint内の特定のドメイン アドレスに関連するアラートを取得する方法について説明します。
keywords: apis, graph api, サポートされている API, get, domain, related, alerts
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
ms.openlocfilehash: b67b97ac115057b0e17bfd492e6330a13ee9e213
ms.sourcegitcommit: c11d4a2b9cb891ba22e16a96cb9d6389f6482459
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2021
ms.locfileid: "61284639"
---
# <a name="get-domain-related-alerts-api"></a>ドメイン関連のアラート API を取得する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明

特定のドメイン アドレスに関連する [アラート](alerts.md) のコレクションを取得します。

## <a name="limitations"></a>制限事項

- 構成された保有期間に従って、最後に更新されたアラートに対してクエリを実行できます。
- この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「[Microsoft Defender for Endpoint API の使用」を](apis-intro.md)参照してください。

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション|Alert.Read.All|'すべてのアラートを読み取る'
アプリケーション|Alert.ReadWrite.All|'すべてのアラートの読み取りと書き込み'
委任 (職場または学校のアカウント)|Alert.Read|'アラートの読み取り'
委任 (職場または学校のアカウント)|Alert.ReadWrite|'アラートの読み取りと書き込み'

> [!NOTE]
> ユーザー資格情報を使用してトークンを取得する場合:
>
> - ユーザーには、少なくとも次のロールアクセス許可が必要です:"データの表示" (詳細については、「 [ロールの作成と管理](user-roles.md) 」を参照)
> - 応答には、デバイス グループの設定に基づいて、ユーザーがアクセスできるデバイスに関連付けられたアラートのみが含まれます (詳細については、「 [デバイス グループの作成と管理](machine-groups.md) 」を参照してください)

## <a name="http-request"></a>HTTP 要求

```http
GET /api/domains/{domain}/alerts
```

## <a name="request-headers"></a>要求ヘッダー

|ヘッダー|値|
|---|---|
|Authorization|String|

## <a name="request-body"></a>要求本文

Empty

## <a name="response"></a>応答

成功し、ドメインが存在する場合は、 [アラート](alerts.md) エンティティの一覧で 200 OK です。 ドメインが存在しない場合は、空のセットで 200 OK です。

## <a name="example"></a>例

### <a name="request"></a>要求

要求の例を次に示します。

```http
GET https://api.securitycenter.microsoft.com/api/domains/client.wns.windows.com/alerts
```
