---
title: デバイスの高度な検索で DeviceFromIP() Microsoft 365 Defender
description: DeviceFromIP() 関数を使用して、特定の IP アドレスが割り当てられているデバイスを取得する方法について説明します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、device、devicefromIP、function、enrichment
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 4a1f1198c247aefbcbb093d1a5f5105704255692
ms.sourcegitcommit: 6dcc3b039e0f0b9bae17c386f14ed2b577b453a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2021
ms.locfileid: "61531581"
---
# <a name="devicefromip"></a>DeviceFromIP()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


高度な検索クエリの関数を使用して、特定の時点で特定の IP アドレスに割り当てられているデバイスの一覧 `DeviceFromIP()` をすばやく取得します。 [](advanced-hunting-overview.md) 

この関数は、次の列を持つテーブルを返します。

| Column | データ型 | 説明 |
|------------|-------------|-------------|
| `IP` | `string` | IP アドレス  |
| `DeviceId` | `string` | サービス内のデバイスの一意の識別子 |


## <a name="syntax"></a>構文

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a>引数

この関数は、クエリの一部として呼び出されます。

- **x**—最初のパラメーターは、通常、クエリ内の列です。 この例では、割り当てられているデバイスの一覧を表示する IP アドレスという名前の列 `IP` です。 ローカル IP アドレスである必要があります。 外部 IP アドレスはサポートされていません。
- **y**:2 番目の省略可能なパラメーターは、特定の時刻から最新の割り当てられたデバイスを取得するように関数 `Timestamp` に指示します。 指定しない場合、関数は使用可能な最新のレコードを返します。

## <a name="example"></a>例


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a>特定の IP アドレスが割り当てられている最新のデバイスを取得する

```kusto
DeviceNetworkEvents 
| limit 100 
| project IP = LocalIP 
| invoke DeviceFromIP()
```

## <a name="related-topics"></a>関連項目
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
