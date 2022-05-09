---
title: 調査リソースの種類
description: Microsoft Defender for Endpoint調査エンティティ。
keywords: apis, graph api, サポートされている API, get, alerts, investigations
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 1749404942b42778ecde99417a8e3501c7c4f4cf
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63327225"
---
# <a name="investigation-resource-type"></a>調査リソースの種類

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!Include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!Include[Improve request performance](../../includes/improve-request-performance.md)]

Defender for Endpoint の自動調査エンティティを表します。

詳細については、「 [自動調査の概要](automated-investigations.md)」を参照してください。

## <a name="methods"></a>メソッド

メソッド|戻り値の型|説明
:---|:---|:---
[調査の一覧表示](get-investigation-collection.md)|調査コレクション|調査のコレクションを取得する
[1 つの調査を取得する](get-investigation-object.md)|調査エンティティ|1 つの調査エンティティを取得します。
[調査の開始](initiate-autoir-investigation.md)|調査エンティティ|デバイスで調査を開始します。

## <a name="properties"></a>プロパティ

プロパティ|種類|説明
:---|:---|:---
ID|String|調査エンティティの ID。 
startTime|DateTime Nullable|調査が作成された日時。
endTime|DateTime Nullable|調査が完了した日時。
cancelledBy|String|その調査を取り消したユーザー/アプリケーションの ID。
状態|列挙|調査の現在の状態。 指定できる値は、"不明"、"終了済み" です。 'SuccessfullyRemediated'、'Benign'、'Failed'、'PartiallyRemediated'、'Running'、'PendingApproval'、'PendingResource'、'PartiallyInvestigated'、'TerminatedByUser'、'TerminatedBySystem'、'Queued'、'InnerFailure'、'PreexistingAlert'、'UnsupportedAlertType'、'SuppressedAlert'。
statusDetails|String|調査の状態に関する追加情報。
machineId|String|調査が実行されるデバイスの ID。
computerDnsName|String|調査が実行されるデバイスの名前。
triggeringAlertId|String|調査をトリガーしたアラートの ID。

## <a name="json-representation"></a>Json 表現

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
