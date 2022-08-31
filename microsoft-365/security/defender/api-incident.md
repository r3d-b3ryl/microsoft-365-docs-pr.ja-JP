---
title: Microsoft 365 Defenderインシデント API とインシデント リソースの種類
description: Microsoft 365 Defenderの Incidents リソースの種類のメソッドとプロパティについて説明します。
keywords: incident, incidents, api
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
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
ms.custom: api
ms.openlocfilehash: 8531a2f647f9f8adaeb952c08cae596142fc884f
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67471370"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incidents-resource-type"></a>Microsoft 365 Defenderインシデント API とインシデント リソースの種類

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

[インシデント](incidents-overview.md)は、攻撃を記述するのに役立つ関連するアラートのコレクションです。 組織内のさまざまなエンティティからのイベントは、Microsoft 365 Defenderによって自動的に集計されます。 インシデント API を使用して、組織のインシデントと関連するアラートにプログラムでアクセスできます。

## <a name="quotas-and-resource-allocation"></a>クォータとリソースの割り当て

1 分あたり最大 50 回の通話、または 1 時間あたり 1500 回の通話を要求できます。 各メソッドには、独自のクォータもあります。 メソッド固有のクォータの詳細については、使用するメソッドのそれぞれの記事を参照してください。

HTTP 応答コードは `429` 、送信された要求の数または割り当てられた実行時間によって、クォータに達したことを示します。 応答本文には、到達したクォータがリセットされるまでの時間が含まれます。

## <a name="permissions"></a>アクセス許可

インシデント API には、そのメソッドごとにさまざまな種類のアクセス許可が必要です。 必要なアクセス許可の詳細については、それぞれのメソッドの記事を参照してください。

## <a name="methods"></a>メソッド

メソッド | 戻り値の型 | 説明
-|-|-
[インシデントをリストする](api-list-incidents.md) | [インシデント](api-incident.md) の一覧 | インシデントの一覧を取得します。
[インシデントを更新する](api-update-incidents.md) | [インシデント](api-incident.md) | 特定のインシデントを更新します。
[インシデントを取得する](api-get-incident.md) | [インシデント](api-incident.md) | 1 つのインシデントを取得します。

## <a name="request-body-response-and-examples"></a>要求本文、応答、および例

要求の作成方法や応答の解析方法の詳細、および実際の例については、それぞれのメソッドの記事を参照してください。

## <a name="common-properties"></a>共通プロパティ

プロパティ | 型 | 説明
-|-|-
incidentId | long | インシデントの一意の ID。
redirectIncidentId | null 許容 long | 現在のインシデントがマージされたインシデント ID。
incidentName | 文字列 | インシデントの名前。
createdTime | DateTimeOffset | インシデントが作成された日時 (UTC)。
lastUpdateTime | DateTimeOffset | インシデントが最後に更新された日時 (UTC)。
assignedTo | 文字列 | インシデントの所有者。
severity | 列挙 | インシデントの重大度。 指定できる値は、次```Low``````Informational``````Medium``````High```のとおりです。 ```UnSpecified```
status | 列挙 | インシデントの現在の状態を指定します。 可能な値は、```Active```、```InProgress```、```Resolved```、および ```Redirected``` です。
classification | 列挙 | インシデントの仕様。 可能な値は ```Unknown```、```FalsePositive```、```TruePositive``` です。
決定 | 列挙 | インシデントの決定を指定します。 可能な値は、```NotAvailable```、```Apt```、```Malware```、```SecurityPersonnel```、```SecurityTesting```、```UnwantedSoftware```、```Other``` です。
tags | string List | インシデント タグの一覧。
comments | インシデント コメントの一覧 | インシデント コメント オブジェクトには、コメント文字列、createdBy 文字列、createTime の日付時刻が含まれます。
アラート | アラート 一覧 | 関連するアラートの一覧。 [List incidents API のドキュメントの例を](api-list-incidents.md)参照してください。

>[!NOTE]
>2022 年 8 月 29 日頃、以前にサポートされていたアラート決定値 ('Apt' と 'SecurityPersonnel') は非推奨になり、API 経由では使用できなくなります。

## <a name="related-articles"></a>関連記事

- [Microsoft 365 Defender API の概要](api-overview.md)
- [インシデントの概要](incidents-overview.md)
- [インシデントの一覧表示 API](api-list-incidents.md)
- [インシデント API を更新する](api-update-incidents.md)
