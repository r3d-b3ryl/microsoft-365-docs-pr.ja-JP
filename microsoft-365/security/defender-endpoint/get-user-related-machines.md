---
title: ユーザー関連のマシン API を取得する
description: ユーザー関連マシンの取得 API を使用して、Microsoft Defender for Endpointのユーザー ID に関連するデバイスのコレクションを取得する方法について説明します。
keywords: apis, graph api, サポートされている API, get, user, user related alerts
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
ms.openlocfilehash: 5dd8cbd36fdac4aa3d0661a9b418a30ec2bae44f
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2021
ms.locfileid: "61369866"
---
# <a name="get-user-related-machines-api"></a>ユーザー関連のマシン API を取得する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明
特定のユーザー ID に関連するデバイスのコレクションを取得します。

## <a name="limitations"></a>制限事項

この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「[Microsoft Defender for Endpoint API の使用」を](apis-intro.md)参照してください。

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション |Machine.Read.All|'すべてのマシン プロファイルを読み取る'
アプリケーション |Machine.ReadWrite.All |'すべてのマシン情報の読み取りと書き込み'
委任 (職場または学校のアカウント) | Machine.Read | 'マシン情報の読み取り'
委任 (職場または学校のアカウント) | Machine.ReadWrite | 'マシン情報の読み取りと書き込み'

> [!NOTE]
> ユーザー資格情報を使用してトークンを取得する場合:
>
> - ユーザーには、少なくとも次のロール権限が必要です。"データの表示"。 詳細については、「[ロールの作成と管理](user-roles.md)」を参照してください。
> - 応答には、デバイス グループの設定に基づいて、ユーザーがアクセスできるデバイスのみが含まれます。 詳細については、「 [デバイス グループの作成と管理](machine-groups.md)」を参照してください。

## <a name="http-request"></a>HTTP 要求

```http
GET /api/users/{id}/machines
```

**ID は完全な UPN ではなく、ユーザー名のみです。(たとえば、/api/users/user1/machines を使用 user1@contoso.com マシンを取得する場合)**

## <a name="request-headers"></a>要求ヘッダー

名前|種類|説明
:---|:---|:---
Authorization | String | ベアラー {token}。 **必須**。

## <a name="request-body"></a>要求本文

Empty

## <a name="response"></a>応答

成功し、ユーザーが存在する場合は、本文内の [マシン](machine.md) エンティティの一覧を含む 200 OK です。 ユーザーが存在しない場合は、空のセットで 200 OK です。

## <a name="example"></a>例

### <a name="request"></a>要求

以下は、要求の例です。

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/machines
```
