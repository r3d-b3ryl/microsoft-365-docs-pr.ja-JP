---
title: Microsoft 365 Defenderの高度なハンティングにおける DeviceFromIP() 関数
description: DeviceFromIP() 関数を使用して、特定の IP アドレスが割り当てられているデバイスを取得する方法について説明します
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, スキーマ参照, kusto, デバイス, devicefromIP, 関数, エンリッチメント
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
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
ms.openlocfilehash: 62df7a7c7bbf61c176d69b115f88bddae09fa04f
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67479402"
---
# <a name="devicefromip"></a>DeviceFromIP()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


特定の `DeviceFromIP()` 時点で特定の IP アドレスに割り当てられているデバイスの一覧をすばやく取得するには、 [高度なハンティング](advanced-hunting-overview.md) クエリの関数を使用します。 

この関数は、次の列を含むテーブルを返します。

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

- **x** - 最初のパラメーターは通常、クエリ内の列に既に存在します。 この場合、この列は、割り当てられているデバイスの一覧を表示する IP アドレスという名前 `IP`の列です。 ローカル IP アドレスにする必要があります。 外部 IP アドレスはサポートされていません。
- **y** - 2 番目の `Timestamp`省略可能なパラメーターは、特定の時刻から最新の割り当て済みデバイスを取得するように関数に指示するパラメーターです。 指定しない場合、関数は使用可能な最新のレコードを返します。

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
