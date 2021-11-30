---
title: Microsoft 365 Defender API とインシデント リソースの種類
description: '[インシデント] リソースの種類のメソッドとプロパティについて説明Microsoft 365 Defender'
keywords: インシデント、インシデント、API
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
ms.openlocfilehash: fc2e7f92a48cf94c0092dbcf7da051642949180c
ms.sourcegitcommit: 4af23696ff8b44872330202fe5dbfd2a69d9ddbf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/30/2021
ms.locfileid: "61221390"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incidents-resource-type"></a>Microsoft 365 Defender API とインシデント リソースの種類

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

インシデント [とは](incidents-overview.md) 、攻撃の説明に役立つ関連アラートのコレクションです。 組織内の異なるエンティティからのイベントは、ユーザーが自動的にMicrosoft 365 Defender。 インシデント API を使用して、組織のインシデントと関連するアラートにプログラムでアクセスできます。

## <a name="quotas-and-resource-allocation"></a>クォータとリソース割り当て

1 分あたり最大 50 回の通話または 1 時間あたり 1500 回の通話を要求できます。 また、各メソッドには独自のクォータがあります。 メソッド固有のクォータの詳細については、使用するメソッドの各記事を参照してください。

HTTP 応答コードは、送信された要求の数または割り当てられた実行時間のいずれかによって、クォータに達 `429` したかどうかを示します。 応答本文には、到達したクォータがリセットされるまでの時間が含まれます。

## <a name="permissions"></a>アクセス許可

インシデント API では、それぞれのメソッドに対してさまざまな種類のアクセス許可が必要です。 必要なアクセス許可の詳細については、それぞれのメソッドの記事を参照してください。

## <a name="methods"></a>メソッド

メソッド | 戻り値の型 | 説明
-|-|-
[インシデントをリストする](api-list-incidents.md) | [インシデント リスト](api-incident.md) | インシデントの一覧を取得します。
[インシデントを更新する](api-update-incidents.md) | [インシデント](api-incident.md) | 特定のインシデントを更新します。
[インシデントの取得](api-get-incident.md) | [インシデント](api-incident.md) | 1 つのインシデントを取得します。

## <a name="request-body-response-and-examples"></a>要求の本文、応答、および例

要求の作成方法や応答の解析方法の詳細、および実際の例については、それぞれのメソッドの記事を参照してください。

## <a name="common-properties"></a>共通プロパティ

プロパティ | 種類 | 説明
-|-|-
incidentId | long | インシデントの一意の ID。
redirectIncidentId | null 許容長 | 現在のインシデントが結合されたインシデント ID。
incidentName | string | インシデントの名前。
createdTime | DateTimeOffset | インシデントが作成された日付と時刻 (UTC)。
lastUpdateTime | DateTimeOffset | インシデントが最後に更新された日時 (UTC)。
assignedTo | string | インシデントの所有者。
severity | 列挙 | インシデントの重大度。 使用できる値は ```UnSpecified``` ```Informational``` ```Low``` 、、、、、 ```Medium``` および ```High``` です。
status | 列挙 | インシデントの現在の状態を指定します。 可能な値は、```Active```、```InProgress```、```Resolved```、および ```Redirected``` です。
classification | 列挙 | インシデントの仕様。 可能な値は ```Unknown```、```FalsePositive```、```TruePositive``` です。
決定 | 列挙 | インシデントの決定を指定します。 可能な値は、```NotAvailable```、```Apt```、```Malware```、```SecurityPersonnel```、```SecurityTesting```、```UnwantedSoftware```、```Other``` です。
tags | string List | インシデント タグの一覧。
comments | インシデント コメントの一覧 | インシデント コメント オブジェクトには、コメント文字列、createBy 文字列、createTime 日付時刻が含まれます。
アラート | アラート リスト | 関連するアラートの一覧。 「List Incidents [API」のドキュメントの例](api-list-incidents.md) を参照してください。

## <a name="related-articles"></a>関連記事

- [Microsoft 365 Defender API の概要](api-overview.md)
- [インシデントの概要](incidents-overview.md)
- [インシデント API の一覧表示](api-list-incidents.md)
- [インシデント API の更新](api-update-incidents.md)
