---
title: オフボード マシン API
description: API を使用してデバイスをMicrosoft Defender for Endpointからオフボードする方法について説明します。
keywords: apis、graph api、サポートされている API、調査パッケージの収集
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
ms.openlocfilehash: a9e46b428500b41b143585434f7a16c13227db1c
ms.sourcegitcommit: 6c2ab5e8efe74d0dc2df610e2d9d2fdda8aaf074
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65669762"
---
# <a name="offboard-machine-api"></a>オフボード マシン API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明

Defender for Endpoint のオフボード デバイス。

## <a name="limitations"></a>制限事項

- この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。

  [!include[Machine actions note](../../includes/machineactionsnote.md)]

> [!NOTE]
> この API は、Windows 11、Windows 10、バージョン 1703 以降、またはサーバー 2019 以降Windowsでサポートされています。
>
> この API は、MacOS または Linux デバイスではサポートされていません。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「[Defender for Endpoint API の使用」を](apis-intro.md)参照してください。

アクセス許可の種類|アクセス許可|アクセス許可の表示名
---|---|---
アプリケーション|Machine.Offboard|'オフボード マシン'
委任 (職場または学校のアカウント)|Machine.Offboard|'オフボード マシン'

> [!NOTE]
> ユーザー資格情報を使用してトークンを取得する場合:
>
> - ユーザーは "グローバル 管理" AD ロールを必要とする
> - ユーザーは、デバイス グループの設定に基づいてデバイスにアクセスできる必要があります (詳細については、「 [デバイス グループの作成と管理](machine-groups.md) 」を参照してください)

## <a name="http-request"></a>HTTP 要求

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/offboard
```

デバイスを選択すると、マシン ID が URL に表示されます。 一般に、URL に記載されている 40 桁の英数字です。

## <a name="request-headers"></a>要求ヘッダー

名前|型|説明
---|---|---
Authorization|String|ベアラー {token}。 **必須**。
Content-Type|string|application/json. **必須**。

## <a name="request-body"></a>要求本文

要求本文で、次のパラメーターを含む JSON オブジェクトを指定します。

パラメーター|型|説明
---|---|---
コメント|文字列|アクションに関連付けるコメント。 **必須**。

## <a name="response"></a>応答

成功した場合、このメソッドは、応答本文に 200 個の作成済み応答コードと [Machine Action](machineaction.md) を返します。

## <a name="example"></a>例

### <a name="request"></a>要求

以下は、要求の例です。

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/offboard
```

```json
{
  "Comment": "Offboard machine by automation"
}
```
