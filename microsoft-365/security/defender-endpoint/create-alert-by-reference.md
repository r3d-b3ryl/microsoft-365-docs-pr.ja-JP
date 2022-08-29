---
title: イベント API からアラートを作成する
description: アラートの作成 API を使用して、Microsoft Defender for Endpointのイベントの上に新しいアラートを作成する方法について説明します。
keywords: apis, graph api, サポートされている API, get, alert, information, id
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
ms.openlocfilehash: 9a211034b164381226df0d5d79d0d709db3c2e98
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67326741"
---
# <a name="create-alert-api"></a>アラート API を作成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API の説明

イベントの上に新しい [アラート](alerts.md) を作成 **します**。

- **Microsoft Defender for Endpoint イベント** は、アラートの作成に必要です。
- 要求で Event から 3 つのパラメーター ( **イベント時刻**、 **マシン ID**、 **レポート ID**) を指定する必要があります。 次の例を参照してください。
- 高度なハンティング API またはポータルにあるイベントを使用できます。
- 同じタイトルを持つ同じデバイスに既に開いているアラートがある場合は、新しく作成されたアラートがマージされます。
- 自動調査は、API を使用して作成されたアラートに対して自動的に開始されます。

## <a name="limitations"></a>制限事項

1. この API のレート制限は、1 分あたり 15 回の呼び出しです。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「[Microsoft Defender for Endpoint API の使用」を](apis-intro.md)参照してください。

アクセス許可の種類 | アクセス許可 | アクセス許可の表示名
:---|:---|:---
アプリケーション | Alert.ReadWrite.All | 'すべてのアラートの読み取りと書き込み'
委任 (職場または学校のアカウント) | Alert.ReadWrite | 'アラートの読み取りと書き込み'

> [!NOTE]
> ユーザー資格情報を使用してトークンを取得する場合:
>
> - ユーザーには、少なくとも次のロールアクセス許可が必要です:"アラート調査" (詳細については、 [ロールの作成と管理](user-roles.md) を参照してください)
> - ユーザーは、デバイス グループの設定に基づいて、アラートに関連付けられているデバイスにアクセスできる必要があります (詳細については、「[デバイス グループの作成と管理](machine-groups.md)」を参照してください)

## <a name="http-request"></a>HTTP 要求

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

## <a name="request-headers"></a>要求ヘッダー

名前|種類|説明
:---|:---|:---
Authorization | String | ベアラー {token}。 **必須**。
Content-Type | 文字列 | application/json. **必須**。

## <a name="request-body"></a>要求本文

要求本文で、次の値を指定します (すべて必須)。

プロパティ | 種類 | 説明
:---|:---|:---
eventTime | DateTime(UTC) | 高度なハンティングから取得した、文字列としてのイベントの正確な時刻。 たとえば、  ```2018-08-03T16:45:21.7115183Z``` **必須** です。
reportId | 文字列 | 高度な捜索から取得したイベントの reportId。 **必須**。
MachineId | String | イベントが識別されたデバイスの ID。 **必須**。
severity | 文字列 | アラートの重大度。 プロパティの値は、'Low'、'Medium'、'High' です。 **必須**。
title | String | アラートのタイトル。 **必須**。
説明 | String | アラートの説明。 **必須**。
recommendedAction| 文字列 | セキュリティ担当者は、アラートを分析するときにこのアクションを実行する必要があります。 **必須**。
category| 文字列 | アラートのカテゴリ。 プロパティの値は次のとおりです。"General"、"CommandAndControl"、"Collection"、"CredentialAccess"、"DefenseEvasion"、"Discovery"、"Exfiltration"、"Exploit"、"Execution"、"InitialAccess"、"LateralMovement"、"Malware"、"Persistence"、"PrivilegeEscalation"、"Ransomware"、"SuspiciousActivity" **が必要** です。

## <a name="response"></a>応答

成功した場合、このメソッドは 200 OK を返し、応答本文に新しい [アラート](alerts.md) オブジェクトを返します。 指定したプロパティを持つイベント (_reportId_、 _eventTime_ 、 _machineId_) が見つからなかった場合は、404 Not Found です。

## <a name="example"></a>例

### <a name="request"></a>要求

要求の例を次に示します。

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
