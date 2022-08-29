---
title: タグ API でデバイスを検索する
description: specifc タグを含むすべてのデバイスを検索する
keywords: apis, サポートされている API, get, device, find, find device, by tag, tag
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
ms.openlocfilehash: f7926003a11c5aa27da5bbf4913feb54504a60d1
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67327819"
---
# <a name="find-devices-by-tag-api"></a>タグ API でデバイスを検索する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:** 
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明

タグで [コンピューターを](machine.md) 検索 [します](machine-tags.md)。

`startswith` クエリがサポートされています。

## <a name="limitations"></a>制限事項

1. この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。

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
GET /api/machines/findbytag?tag={tag}&useStartsWithFilter={true/false}
```

## <a name="request-headers"></a>要求ヘッダー

名前|種類|説明
:---|:---|:---
Authorization|String|ベアラー {token}。 **必須**。

## <a name="request-uri-parameters"></a>要求 URI パラメーター

名前|種類|説明
:---|:---|:---
tag|文字列|タグ名。 **必須**。
useStartsWithFilter|ブール型|true に設定すると、クエリ内の特定のタグで始まるタグ名を持つすべてのデバイスが検索されます。 既定は false です。 **オプション**。

## <a name="request-body"></a>要求本文

Empty

## <a name="response"></a>応答

成功した場合 - 応答本文のマシンの一覧で 200 OK。

## <a name="example"></a>例

### <a name="request"></a>要求

以下は、要求の例です。

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbytag?tag=testTag&useStartsWithFilter=true
```
