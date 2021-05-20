---
title: Microsoft 365Defender インシデント API とインシデント リソースタイプ
description: defender でのインシデント リソースの種類のメソッドとプロパティMicrosoft 365確認します。
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 5cc149668e49e21b38b5fb95ae3f40db6c296e1d
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572587"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a>Microsoft 365ディフェンダー インシデント API とインシデント リソースタイプ

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

[インシデント](incidents-overview.md)とは、攻撃の説明に役立つ関連アラートの集まりです。 組織内のさまざまなエンティティからのイベントは、Microsoft 365 Defender によって自動的に集計されます。 インシデント API を使用すると、組織のインシデントおよび関連するアラートにプログラムでアクセスできます。

## <a name="quotas-and-resource-allocation"></a>クォータとリソース割り当て

1 分あたり最大 50 件のコール、または 1 時間あたり 1500 件のコールをリクエストできます。 各メソッドには、独自のクォータもあります。 メソッド固有のクォータの詳細については、使用するメソッドの各記事を参照してください。

`429`HTTP 応答コードは、送信された要求の数または割り当てられた実行時間によって、クォータに達したことを示します。 応答本文には、到達したクォータがリセットされるまでの時間が含まれます。

## <a name="permissions"></a>アクセス許可

インシデント API では、それぞれのメソッドに対して異なる種類のアクセス許可が必要です。 必要なアクセス許可の詳細については、それぞれのメソッドの記事を参照してください。

## <a name="methods"></a>メソッド

メソッド | 戻り値の型 | 説明
-|-|-
[インシデントを一覧表示する](api-list-incidents.md) | [インシデント](api-incident.md) リスト | インシデントの一覧を取得します。
[インシデントを更新する](api-update-incidents.md) | [インシデント](api-incident.md) | 特定のインシデントを更新します。

## <a name="request-body-response-and-examples"></a>要求本文、応答、例

リクエストの作成方法や応答の解析方法、および実際の例については、それぞれのメソッドの記事を参照してください。

## <a name="common-properties"></a>共通プロパティ

プロパティ | 型 | 説明
-|-|-
インシデントId | long | インシデントの一意の ID。
インシデント ID をリダイレクトします。 | null 許容長 | 現在のインシデントがマージされたインシデント ID。
インシデント名 | string | インシデントの名前。
作成された時刻 | DateTimeOffset | インシデントが作成された日時 (UTC)。
ラストアップデート時間 | DateTimeOffset | インシデントが最後に更新された日時 (UTC)。
assignedTo | string | インシデントの所有者。
severity | 列挙 | インシデントの重大度。 指定できる値は ```UnSpecified``` ```Informational``` 、 、 、 、 、 ```Low``` 、 ```Medium``` です ```High``` 。
status | 列挙 | インシデントの現在の状態を指定します。 使用できる値は ```Active``` 、 ```Resolved``` 、 、 、 です ```Redirected``` 。
classification | 列挙 | インシデントの仕様。 可能な値は、```Unknown```、```FalsePositive```、```TruePositive``` です。
決定 | 列挙 | インシデントの決定を指定します。 可能な値は、```NotAvailable```、```Apt```、```Malware```、```SecurityPersonnel```、```SecurityTesting```、```UnwantedSoftware```、```Other``` です。
tags | 文字列リスト | インシデント タグのリスト。
comments | インシデントコメントの一覧 | インシデント コメント オブジェクトには、コメント文字列、作成文字列、および作成時刻の日時が含まれます。
アラート | アラート一覧 | 関連するアラートの一覧。 インシデント API のドキュメントの [例](api-list-incidents.md) を参照してください。

## <a name="related-articles"></a>関連記事

- [Microsoft 365ディフェンダー API の概要](api-overview.md)
- [インシデントの概要](incidents-overview.md)
- [インシデント API の一覧](api-list-incidents.md)
- [インシデント API の更新](api-update-incidents.md)
