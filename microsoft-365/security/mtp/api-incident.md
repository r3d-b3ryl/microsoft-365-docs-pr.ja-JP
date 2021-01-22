---
title: Microsoft 365 Defender インシデント API とインシデント リソースの種類
description: Microsoft 365 Defender の Incident リソースタイプのメソッドとプロパティについて説明します。
keywords: incident, incidents, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 37413c3c7458527e90d4657ddfb3afb058e1dfaa
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928356"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a>Microsoft 365 Defender インシデント API とインシデント リソースの種類

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 一部の情報は、製品のリリース前に大幅に変更される可能性があるプレリリース製品に関連しています。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

インシデント [は](incidents-overview.md) 、攻撃の説明に役立つ関連するアラートのコレクションです。 組織内の異なるエンティティからのイベントは、Microsoft 365 Defender によって自動的に集計されます。 インシデント API を使用すると、組織のインシデントと関連するアラートにプログラムでアクセスできます。

## <a name="quotas-and-resource-allocation"></a>クォータとリソース割り当て

1 分あたり最大 50 件、または 1 時間あたり 1500 件の通話を要求できます。 また、各メソッドには独自のクォータがあります。 メソッド固有のクォータの詳細については、使用する方法に関するそれぞれの記事を参照してください。

HTTP 応答コードは、送信された要求の数または割り当てられた実行時間によってクォータに達 `429` したかどうかを示します。 応答本文には、到達したクォータがリセットされるまでの時間が含まれます。

## <a name="permissions"></a>Permissions

インシデント API では、そのメソッドごとに異なる種類のアクセス許可が必要です。 必要なアクセス許可の詳細については、それぞれのメソッドの記事を参照してください。

## <a name="methods"></a>メソッド

メソッド | 戻り値の型 | 説明
-|-|-
[インシデントを一覧表示する](api-list-incidents.md) | [インシデント リスト](api-incident.md) | インシデントの一覧を取得します。
[インシデントを更新する](api-update-incidents.md) | [インシデント](api-incident.md) | 特定のインシデントを更新します。

## <a name="request-body-response-and-examples"></a>要求の本文、応答、および例

要求を作成する方法や応答を解析する方法の詳細、および実際の例については、それぞれのメソッドの記事を参照してください。

## <a name="common-properties"></a>共通プロパティ

プロパティ | 種類 | 説明
-|-|-
incidentId | long | インシデントの一意の ID。
redirectIncidentId | nullable long | 現在のインシデントがマージされたインシデント ID。
incidentName | string | インシデントの名前。
createdTime | DateTimeOffset | インシデントが作成された日時 (UTC)。
lastUpdateTime | DateTimeOffset | インシデントが最後に更新された日時 (UTC)。
assignedTo | string | インシデントの所有者。
severity | 列挙 | インシデントの重大度。 使用できる値は ```UnSpecified``` 、 ```Informational``` 次 ```Low``` ```Medium``` のとおりです ```High``` 。
status | 列挙 | インシデントの現在の状態を指定します。 使用できる値は ```Active``` 、次 ```Resolved``` のとおりです ```Redirected``` 。
classification | 列挙 | インシデントの仕様。 可能な値は ```Unknown```、```FalsePositive```、```TruePositive``` です。
判断 | 列挙 | インシデントの決定を指定します。 可能な値は、```NotAvailable```、```Apt```、```Malware```、```SecurityPersonnel```、```SecurityTesting```、```UnwantedSoftware```、```Other``` です。
tags | string List | インシデント タグのリスト。
アラート | アラート リスト | 関連するアラートのリスト。 インシデント一覧 API [ドキュメントの例を](api-list-incidents.md) 参照してください。

## <a name="related-articles"></a>関連記事

- [Microsoft 365 Defender API の概要](api-overview.md)
- [インシデントの概要](incidents-overview.md)
- [インシデント API を一覧表示する](api-list-incidents.md)
- [インシデント API を更新する](api-update-incidents.md)
