---
title: 調査リソースの種類
description: Microsoft Defender for Endpoint Investigation エンティティ。
keywords: apis、graph api、サポートされている API、get、アラート、調査
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 069e74b8ad0aef33caab411b92c24c4d0b72f022
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60194155"
---
# <a name="investigation-resource-type"></a>調査リソースの種類

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Defender for Endpoint の自動調査エンティティを表します。

詳細 [については、「自動調査の概要](automated-investigations.md) 」を参照してください。

## <a name="methods"></a>メソッド

メソッド|戻り値の型|説明
:---|:---|:---
[リスト調査](get-investigation-collection.md)|調査コレクション|調査のコレクションを取得する
[単一の調査を取得する](get-investigation-object.md)|調査エンティティ|単一の Investigation エンティティを取得します。
[調査の開始](initiate-autoir-investigation.md)|調査エンティティ|デバイスで調査を開始します。

## <a name="properties"></a>プロパティ

プロパティ|型|説明
:---|:---|:---
id|String|調査エンティティの ID。 
startTime|DateTime Nullable|調査が作成された日時。
endTime|DateTime Nullable|調査が完了した日時。
cancelledBy|String|その調査を取り消したユーザー/アプリケーションの ID。
state|列挙|調査の現在の状態。 指定できる値は、'Unknown'、'Terminated'、 'SuccessfullyRemediated', '良性', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'unsupportedAlertType', 'unsupportedAlertType''
statusDetails|String|調査の状態に関する追加情報。
machineId|String|調査が実行されるデバイスの ID。
computerDnsName|String|調査が実行されるデバイスの名前。
triggeringAlertId|String|調査をトリガーしたアラートの ID。

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
