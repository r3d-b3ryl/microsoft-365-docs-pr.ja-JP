---
title: イベント API からアラートを作成する
description: Create alert API を使用して、Microsoft Defender for Endpoint のイベントの上に新しいアラートを作成する方法について説明します。
keywords: apis, graph api, supported apis, get, alert, information, id
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
ms.openlocfilehash: 9ff52a2c2cd464552637a166708669c2ab4d00eece6bd6585603d2a33bf5a038
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53794380"
---
# <a name="create-alert-api"></a>アラート API の作成

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

- Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API の説明

イベントの上 [に新しいアラート](alerts.md) を **作成します**。

- **Microsoft Defender for Endpoint Event は** 、アラートの作成に必要です。
- 要求でイベントから 3 つのパラメーターを指定する必要があります **。イベント** 時間、 **コンピューター ID、** レポート **ID です**。 次の例を参照してください。
- Advanced Hunting API または Portal で見つかったイベントを使用できます。
- 同じタイトルを持つ同じデバイスに開いているアラートが既存の場合、新しく作成されたアラートは、そのデバイスとマージされます。
- 自動調査は、API を介して作成されたアラートで自動的に開始されます。

## <a name="limitations"></a>制限事項

1. この API のレート制限は、1 分あたり 15 回の呼び出しです。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)

アクセス許可の種類 | アクセス許可 | アクセス許可の表示名
:---|:---|:---
アプリケーション | Alerts.ReadWrite.All | 'すべてのアラートの読み取りと書き込み'
委任 (職場または学校のアカウント) | Alert.ReadWrite | 'アラートの読み取りと書き込み'

> [!NOTE]
> ユーザー資格情報を使用してトークンを取得する場合:
>
> - ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'アラートの調査' (詳細については、「 [役割](user-roles.md) の作成と管理」を参照してください)
> - ユーザーは、デバイス グループ設定に基づいて、アラートに関連付けられたデバイスにアクセスできる必要[](machine-groups.md)があります (詳細については、「デバイス グループの作成と管理」を参照してください)

## <a name="http-request"></a>HTTP 要求

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

## <a name="request-headers"></a>要求ヘッダー

名前|種類|説明
:---|:---|:---
Authorization | String | ベアラー {token}。 **必須**
Content-Type | 文字列 | application/json. **必須**

## <a name="request-body"></a>要求本文

要求本文で、次の値を指定します (すべて必須)。

プロパティ | 種類 | 説明
:---|:---|:---
eventTime | DateTime(UTC) | 高度な検索から取得したイベントの正確な時刻を文字列として指定します。 例: ```2018-08-03T16:45:21.7115183Z``` **必須です**。
reportId | String | 高度な狩猟から取得したイベントの reportId。 **必須**
machineId | String | イベントが識別されたデバイスの ID。 **必須**
severity | String | アラートの重大度。 プロパティの値は、'Low'、'Medium'、および 'High' です。 **必須**
title | String | アラートのタイトル。 **必須**
description | String | アラートの説明。 **必須**
recommendedAction| String | アラートの分析時にセキュリティ担当者が実行するアクションを推奨します。 **必須**
category| String | アラートのカテゴリ。 プロパティの値は、"General"、"CommandAndControl"、"Collection"、"CredentialAccess"、"DefenseEvasion"、"Discovery"、"エクスプロイト"、"Exploit"、"Execution"、"InitialAccess"、"LateralMovement"、"Malware"、"Persistence"、"PrivilegeEscalation"、"Ransomware"、"SuspiciousActivity" が必要です。

## <a name="response"></a>応答

成功した場合、このメソッドは 200 OK を返し、応答本文に新しい [アラート](alerts.md) オブジェクトを返します。 指定したプロパティ _(reportId、eventTime、machineId)_ を持つイベントが見つからなかった場合は、404 Not Found です。  

## <a name="example"></a>例

### <a name="request"></a>要求

以下は、要求の例です。

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

```json
{
    "machineId": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "severity": "Low",
    "title": "example",
    "description": "example alert",
    "recommendedAction": "nothing",
    "eventTime": "2018-08-03T16:45:21.7115183Z",
    "reportId": "20776",
    "category": "Exploit"
}
```
