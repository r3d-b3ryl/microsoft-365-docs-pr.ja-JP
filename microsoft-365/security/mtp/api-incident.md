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
ms.openlocfilehash: ac149ca7263b8ef8bb37a7dd18bf0787a3114b37
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201305"
---
# <a name="incident-resource-type"></a>インシデントリソースの種類

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft Threat Protection

>[!IMPORTANT] 
>一部の情報は、市販される前に大幅に変更される可能性がある prereleased 製品に関連しています。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="methods"></a>メソッド

メソッド |戻り値の型 |説明
:---|:---|:---
[インシデントを一覧表示する](api-list-incidents.md) | [インシデント](api-incident.md) リスト | インシデントの一覧を取得します。
[インシデントを更新する](api-update-incidents.md) | [事例](api-incident.md) | 特定のインシデントを更新します。


## <a name="properties"></a>プロパティ

プロパティ |    種類    |    説明
:---|:---|:---
インシデント識別子 d | long | インシデントの一意の ID。
Redirectインシデント識別子 d | null 許容長 | 現在のインシデントが結合されたインシデント ID。
incidentName | 文字列 | インシデントの名前。
createdTime | DateTimeOffset | インシデントが作成された日付と時刻 (UTC)。
lastUpdateTime | DateTimeOffset | インシデントが最後に更新された日付と時刻 (UTC)。
assignedTo | 文字列 | インシデントの所有者。
severity | 列挙 | インシデントの重大度。 可能な値は ```UnSpecified``` 、、、 ```Informational``` ```Low``` 、 ```Medium``` ```High``` です。
status | 列挙 | インシデントの現在の状態を指定します。 可能な値は ```Active``` 、、、 ```Resolved``` ```Redirected``` です。
classification | 列挙 | インシデントの仕様。 可能な値は ```Unknown```、```FalsePositive```、```TruePositive``` です。
決定 | 列挙 | インシデントの決定を指定します。 可能な値は、```NotAvailable```、```Apt```、```Malware```、```SecurityPersonnel```、```SecurityTesting```、```UnwantedSoftware```、```Other``` です。
tags | 文字列リスト | インシデントタグのリスト。
アラート | 通知リスト | 関連する通知のリスト。 「 [List インシデント](api-list-incidents.md) API ドキュメント」の例を参照してください。
