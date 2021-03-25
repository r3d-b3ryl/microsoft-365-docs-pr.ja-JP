---
title: 調査リソースの種類
description: Microsoft Defender ATP 調査エンティティ。
keywords: apis、graph api、サポートされている API、get、アラート、調査
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 36adf0fa5c0de79fe0616f1216118a98ba2005a4
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187249"
---
# <a name="investigation-resource-type"></a>調査リソースの種類

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Defender for Endpoint の自動調査エンティティを表します。
<br> 詳細 [については、「自動調査の概要](automated-investigations.md) 」を参照してください。

## <a name="methods"></a>メソッド
メソッド|戻り値の型 |説明
:---|:---|:---
[リスト調査](get-investigation-collection.md) | 調査コレクション | 調査のコレクションを取得する
[単一の調査を取得する](get-investigation-object.md) | 調査エンティティ | 単一の Investigation エンティティを取得します。
[調査の開始](initiate-autoir-investigation.md) | 調査エンティティ | デバイスで調査を開始します。


## <a name="properties"></a>プロパティ
プロパティ |  種類    |   説明
:---|:---|:---
id | 文字列 | 調査エンティティの ID。 
startTime | DateTime Nullable | 調査が作成された日時。 
endTime | DateTime Nullable | 調査が完了した日時。 
cancelledBy | 文字列 | その調査を取り消したユーザー/アプリケーションの ID。 
investigationState | 列挙 | 調査の現在の状態。 指定できる値は、'Unknown'、'Terminated'、 'SuccessfullyRemediated', '良性', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'unsupportedAlertType', 'unsupportedAlertType''
statusDetails | 文字列 | 調査の状態に関する追加情報。
machineId | 文字列 | 調査が実行されるデバイスの ID。
computerDnsName | 文字列 | 調査が実行されるデバイスの名前。
triggeringAlertId | 文字列 | 調査をトリガーしたアラートの ID。


## <a name="json-representation"></a>Json 表記

```json
{
    "id": "63004",
    "startTime": "2020-01-06T13:05:15Z",
    "endTime": null,
    "state": "Running",
    "cancelledBy": null,
    "statusDetails": null,
    "machineId": "e828a0624ed33f919db541065190d2f75e50a071",
    "computerDnsName": "desktop-test123",
    "triggeringAlertId": "da637139127150012465_1011995739"
}
```
