---
title: Microsoft 365 Defender API のインシデントリソースの種類
description: Microsoft 365 Defender の Incident リソースタイプのメソッドとプロパティについて説明します。
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
ms.openlocfilehash: 68bee647cdd5687dbaad08ce3cd01b427dabf030
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844022"
---
# <a name="incident-resource-type"></a>インシデントリソースの種類

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

>[!IMPORTANT] 
>一部の情報は、市販される前に大幅に変更される可能性がある prereleased 製品に関連しています。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="methods"></a>メソッド

メソッド |戻り値の型 |説明
:---|:---|:---
[インシデントを一覧表示する](api-list-incidents.md) | [インシデント](api-incident.md) リスト | インシデントの一覧を取得します。
[インシデントを更新する](api-update-incidents.md) | [事例](api-incident.md) | 特定のインシデントを更新します。


## <a name="properties"></a>プロパティ

プロパティ |    型    |    説明
:---|:---|:---
インシデント識別子 d | long | インシデントの一意の ID。
Redirectインシデント識別子 d | null 許容長 | 現在のインシデントが結合されたインシデント ID。
incidentName | string | インシデントの名前。
createdTime | DateTimeOffset | インシデントが作成された日付と時刻 (UTC)。
lastUpdateTime | DateTimeOffset | インシデントが最後に更新された日付と時刻 (UTC)。
assignedTo | string | インシデントの所有者。
severity | 列挙 | インシデントの重大度。 可能な値は ```UnSpecified``` 、、、 ```Informational``` ```Low``` 、 ```Medium``` ```High``` です。
status | 列挙 | インシデントの現在の状態を指定します。 可能な値は ```Active``` 、、、 ```Resolved``` ```Redirected``` です。
classification | 列挙 | インシデントの仕様。 可能な値は ```Unknown```、```FalsePositive```、```TruePositive``` です。
決定 | 列挙 | インシデントの決定を指定します。 可能な値は、```NotAvailable```、```Apt```、```Malware```、```SecurityPersonnel```、```SecurityTesting```、```UnwantedSoftware```、```Other``` です。
tags | 文字列リスト | インシデントタグのリスト。
アラート | 通知リスト | 関連する通知のリスト。 「 [List インシデント](api-list-incidents.md) API ドキュメント」の例を参照してください。
