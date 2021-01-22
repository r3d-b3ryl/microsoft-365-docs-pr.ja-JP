---
title: Microsoft 365 Defender の高度な検索での DeviceFromIP() 関数
description: DeviceFromIP() 関数を使用して、特定の IP アドレスが割り当てられているデバイスを取得する方法について説明します。
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、device、devicefromIP、function、enrichment
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 86373c903252fde4ab71c80a81404428a7366da7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931304"
---
# <a name="devicefromip"></a>DeviceFromIP()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


高度な検索クエリの関数を使用して、特定の時点で特定の IP アドレスに割り当てられたデバイスの一覧 `DeviceFromIP()` をすばやく取得します。 [](advanced-hunting-overview.md) 

この関数は、次の列を含むテーブルを返します。

| Column | データ型 | 説明 |
|------------|-------------|-------------|
| `IP` | string | IP アドレス  |
| `DeviceId` | string | サービス内のデバイスの一意識別子 |


## <a name="syntax"></a>構文

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a>引数

この関数はクエリの一部として呼び出されます。

- **x**- 最初のパラメーターは、通常、クエリ内の列です。 この場合は、割り当てられているデバイスの一覧を表示する IP アドレスという名前の列 `IP` です。 ローカル IP アドレスである必要があります。 外部 IP アドレスはサポートされていません。
- **y**- 2 番目の省略可能なパラメーターは、 特定の時刻から最新の割り当てられたデバイスを取得するように関数 `Timestamp` に指示するパラメーターです。 指定しない場合、関数は使用可能な最新のレコードを返します。

## <a name="example"></a>例


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a>特定の IP アドレスが割り当てられている最新のデバイスを取得する

```kusto
DeviceNetworkEvents 
| limit 100 
| project IP = LocalIP 
| invoke DeviceFromIP()
```

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
