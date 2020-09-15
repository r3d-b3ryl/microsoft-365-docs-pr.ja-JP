---
title: Microsoft Threat Protection API のインシデントリソースの種類
description: Microsoft Threat Protection の Incident リソースタイプのメソッドとプロパティについて説明します。
keywords: インシデント、インシデント、api
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 310e3105c973223ea79373d770eb10f7753b917e
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650414"
---
# <a name="incident-resource-type"></a>インシデントリソースの種類

**適用対象:**
- Microsoft Threat Protection

>[!IMPORTANT] 
>一部の情報は、市販される前に大幅に変更される可能性がある prereleased 製品に関連しています。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="methods"></a>メソッド

メソッド |戻り値の型 |説明
:---|:---|:---
[インシデントを一覧表示する](api-list-incidents.md) | [インシデント](api-incident.md) リスト | インシデントの一覧を取得します。
[インシデントの更新](api-update-incidents.md) | [事例](api-incident.md) | 特定のインシデントを更新します。


## <a name="properties"></a>プロパティ

プロパティ |    種類    |    説明
:---|:---|:---
インシデント識別子 d | long | インシデントの一意の ID。
Redirectインシデント識別子 d | null 許容長 | 現在のインシデントが結合されたインシデント ID。
incidentName | string | インシデントの名前。
createdTime | DateTimeOffset | インシデントが作成された日付と時刻 (UTC)。
lastUpdateTime | DateTimeOffset | インシデントが最後に更新された日付と時刻 (UTC)。
assignedTo | string | インシデントの所有者。
severity | 列挙 | インシデントの重大度。 可能な値は ```UnSpecified``` 、、、 ```Informational``` ```Low``` 、 ```Medium``` ```High``` です。
status | 列挙 | インシデントの現在の状態を指定します。 可能な値は ```Active``` 、、、 ```Resolved``` ```Redirected``` です。
classification | 列挙 | インシデントの仕様。 可能な値は、```Unknown```、```FalsePositive```、```TruePositive``` です。
決定 | 列挙 | インシデントの決定を指定します。 可能な値は、```NotAvailable```、```Apt```、```Malware```、```SecurityPersonnel```、```SecurityTesting```、```UnwantedSoftware```、```Other``` です。
tags | 文字列リスト | インシデントタグのリスト。
アラート | 通知リスト | 関連する通知のリスト。 「 [List インシデント](api-list-incidents.md) API ドキュメント」の例を参照してください。