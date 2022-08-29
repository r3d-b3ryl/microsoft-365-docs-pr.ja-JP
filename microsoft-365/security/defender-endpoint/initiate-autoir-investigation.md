---
title: 調査 API を開始する
description: この API を使用して、デバイスの調査を開始します。
keywords: apis, graph api, サポートされている API, 調査
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
ms.openlocfilehash: ec442fdfbb785fd09248fd40acaac2d54b56e1c2
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67325795"
---
# <a name="start-investigation-api"></a>調査 API を開始する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明

デバイスで自動調査を開始します。

詳細については、「 [自動調査の概要](automated-investigations.md) 」を参照してください。

## <a name="limitations"></a>制限事項

1. この API のレート制限は、1 時間あたり 50 回の呼び出しです。

## <a name="requirements-for-air"></a>AIR の要件

組織には Defender for Endpoint が必要です ([「Microsoft Defender for Endpointの最小要件」を](minimum-requirements.md)参照してください。

現時点では、AIR では次の OS バージョンのみがサポートされています。

- Windows Server 2019
- Windows Server 2022
- Windows 10バージョン 1709 (OS ビルド 16299.1085 と [KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441)) 以降
- Windows 10バージョン 1803 (OS Build 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464/windows-10-update-kb4493464)) 以降
- Windows 10バージョン [1803](/windows/release-information/status-windows-10-1809-and-windows-server-2019) 以降
- Windows 11

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「[Microsoft Defender for Endpoint API の使用」を](apis-intro.md)参照してください。

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション|Alert.ReadWrite.All|'すべてのアラートの読み取りと書き込み'
委任 (職場または学校のアカウント)|Alert.ReadWrite|'アラートの読み取りと書き込み'

> [!NOTE]
> ユーザー資格情報を使用してトークンを取得する場合:
>
> - ユーザーには、少なくとも次のロールアクセス許可が必要です:"アクティブ修復アクション" (詳細については、 [ロールの作成と管理](user-roles.md) に関するページを参照してください)
> - ユーザーは、デバイス グループの設定に基づいてデバイスにアクセスできる必要があります (詳細については、「 [デバイス グループの作成と管理](machine-groups.md) 」を参照してください)

## <a name="http-request"></a>HTTP 要求

```http
POST https://api.security.microsoft.com/api/machines/{id}/startInvestigation
```

## <a name="request-headers"></a>要求ヘッダー

名前|種類|説明
:---|:---|:---
Authorization|String|ベアラー {token}。 **必須**。
Content-Type|string|application/json. **必須**。

## <a name="request-body"></a>要求本文

要求本文で、次のパラメーターを含む JSON オブジェクトを指定します。

パラメーター|種類|説明
:---|:---|:---
コメント|文字列|アクションに関連付けるコメント。 **必須**。

## <a name="response"></a>応答

成功した場合、このメソッドは 201 - 作成された応答コードと応答本文の [調査](investigation.md) を返します。

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
