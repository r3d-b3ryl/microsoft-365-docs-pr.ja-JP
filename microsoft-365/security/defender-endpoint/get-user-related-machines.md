---
title: ユーザー関連のコンピューター API を取得する
description: ユーザー関連コンピューターの取得 API を使用して、Microsoft Defender for Endpoint のユーザー ID に関連するデバイスのコレクションを取得する方法について説明します。
keywords: apis, graph api, サポートされている API, get, user, user related alerts
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
ms.openlocfilehash: 207ecaa9352293aebb907d4b14faab1ac2f47187
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2021
ms.locfileid: "53652109"
---
# <a name="get-user-related-machines-api"></a>ユーザー関連のコンピューター API を取得する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明
特定のユーザー ID に関連するデバイスのコレクションを取得します。

## <a name="limitations"></a>制限事項

この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション |Machine.Read.All|'すべてのコンピューター プロファイルを読み取る'
アプリケーション |Machine.ReadWrite.All |'すべてのコンピューター情報の読み取りと書き込み'
委任 (職場または学校のアカウント) | Machine.Read | 'コンピューター情報の読み取り'
委任 (職場または学校のアカウント) | Machine.ReadWrite | 'コンピューター情報の読み取りおよび書き込み'

> [!NOTE]
> ユーザー資格情報を使用してトークンを取得する場合:
>
> - ユーザーには、少なくとも次の役割のアクセス許可が必要です。'データの表示' 。 詳細については、「役割の作成 [と管理」を参照してください](user-roles.md)。
> - 応答には、デバイス グループの設定に基づいて、ユーザーがアクセスできるデバイスだけが含まれます。 詳細については、「デバイス グループの作成 [と管理」を参照してください](machine-groups.md)。

## <a name="http-request"></a>HTTP 要求

```http
GET /api/users/{id}/machines
```

**ID は完全な UPN ではなく、ユーザー名のみです。(たとえば、使用するコンピューターを取得 user1@contoso.com/api/users/user1/machines)**

## <a name="request-headers"></a>要求ヘッダー

名前|種類|説明
:---|:---|:---
Authorization | String | ベアラー {token}。 **必須**

## <a name="request-body"></a>要求本文

Empty

## <a name="response"></a>応答

成功し、ユーザーが存在する場合 - 本文のコンピューター[](machine.md)エンティティの一覧で 200 OK。 ユーザーが存在しない場合 - 404 が見つかりません。

## <a name="example"></a>例

### <a name="request"></a>要求

以下は、要求の例です。

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/machines
```
