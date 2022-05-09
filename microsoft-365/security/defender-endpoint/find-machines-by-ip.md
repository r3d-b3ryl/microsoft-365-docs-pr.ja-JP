---
title: 内部 IP API でデバイスを検索する
description: 特定のタイムスタンプの 15 分前と後の時間範囲で、要求された内部 IP で見られるデバイスを検索する
keywords: apis, graph api, サポートされている API, get, device, IP, find, find device, by ip, ip
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
ms.openlocfilehash: 702626d3e147bdd02c4988ffabbd158a44f911c7
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2021
ms.locfileid: "61302268"
---
# <a name="find-devices-by-internal-ip-api"></a>内部 IP API でデバイスを検索する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:** 
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!Include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!Include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明

指定されたタイムスタンプの 15 分前と後の時間範囲で、要求された内部 IP で見られる [マシン](machine.md) を検索します。

## <a name="limitations"></a>制限事項

1. 指定されたタイムスタンプは、過去 30 日間である必要があります。
2. この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「[Microsoft Defender for Endpoint API の使用」を](apis-intro.md)参照してください。

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション|Machine.Read.All|'すべてのマシン プロファイルを読み取る'
アプリケーション|Machine.ReadWrite.All|'すべてのマシン情報の読み取りと書き込み'
委任 (職場または学校のアカウント)|Machine.Read|'マシン情報の読み取り'
委任 (職場または学校のアカウント)|Machine.ReadWrite|'マシン情報の読み取りと書き込み'

> [!NOTE]
> ユーザー資格情報を使用してトークンを取得する場合:
>
> - 応答には、デバイス グループの設定に基づいてユーザーがアクセスできるデバイスのみが含まれます (詳細については、「 [デバイス グループの作成と管理](machine-groups.md) 」を参照してください)
> - ユーザーには、少なくとも次のロールアクセス許可が必要です:"データの表示" (詳細については、「 [ロールの作成と管理](user-roles.md) 」を参照)
> - 応答には、デバイス グループの設定に基づいてユーザーがアクセスできるデバイスのみが含まれます (詳細については、「 [デバイス グループの作成と管理](machine-groups.md) 」を参照してください)

## <a name="http-request"></a>HTTP 要求

```http
GET /api/machines/findbyip(ip='{IP}',timestamp={TimeStamp})
```

## <a name="request-headers"></a>要求ヘッダー

名前|種類|説明
:---|:---|:---
Authorization|String|ベアラー {token}。 **必須**。

## <a name="request-body"></a>要求本文

Empty

## <a name="response"></a>応答

成功した場合 - 応答本文のマシンの一覧で 200 OK。
タイムスタンプが過去 30 日間ではない場合は、400 無効な要求です。

## <a name="example"></a>例

### <a name="request"></a>要求

要求の例を次に示します。

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbyip(ip='10.248.240.38',timestamp=2019-09-22T08:44:05Z)
```
