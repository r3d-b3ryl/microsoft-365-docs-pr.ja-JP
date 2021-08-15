---
title: 調査 API の開始
description: この API を使用して、デバイスの調査を開始します。
keywords: apis, graph api, サポートされている API, 調査
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
ms.openlocfilehash: b69acd8bb60c6b4c2d254c9cd1ca5aef7de69cf583fa02e56d799076c84d372a
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53869000"
---
# <a name="start-investigation-api"></a>調査 API の開始

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明

デバイスで自動調査を開始します。

詳細 [については、「自動調査の概要](automated-investigations.md) 」を参照してください。

## <a name="limitations"></a>制限事項

1. この API のレート制限は、1 時間あたり 50 回の呼び出しです。

## <a name="requirements-for-air"></a>AIR の要件

組織には Defender for Endpoint が必要です (「エンドポイント用 Microsoft Defender の最小[要件」を参照)。](minimum-requirements.md)

現在、AIR は次の OS バージョンのみをサポートしています。

- Windows Server 2019
- Windows 10バージョン 1709 (OS ビルド 16299.1085[および KB4493441)](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441)以降
- Windows 10バージョン 1803 (OS ビルド 17134.704[および KB4493464)](https://support.microsoft.com/help/4493464/windows-10-update-kb4493464)以降
- Windows 10バージョン[1803](/windows/release-information/status-windows-10-1809-and-windows-server-2019)以降

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション|Alert.ReadWrite.All|'すべてのアラートの読み取りと書き込み'
委任 (職場または学校のアカウント)|Alert.ReadWrite|'アラートの読み取りと書き込み'

> [!NOTE]
> ユーザー資格情報を使用してトークンを取得する場合:
>
> - ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'Active 修復アクション' (詳細については、「役割の作成と管理 [」](user-roles.md) を参照してください)
> - ユーザーは、デバイス グループ設定に基づいてデバイスにアクセスする必要があります (詳細については、「 [デバイス](machine-groups.md) グループの作成と管理」を参照してください)

## <a name="http-request"></a>HTTP 要求

```http
POST https://api.security.microsoft.com/api/machines/{id}/startInvestigation
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
コメント|文字列|アクションに関連付けるコメント。 **必須**

## <a name="response"></a>応答

成功した場合、このメソッドは 201 - 作成された応答コードと [応答本文の調査](investigation.md) を返します。

## <a name="example"></a>例

### <a name="request"></a>要求

以下は、要求の例です。

```https
POST https://api.security.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/startInvestigation
```

```json
{
  "Comment": "Test investigation"
}
```
