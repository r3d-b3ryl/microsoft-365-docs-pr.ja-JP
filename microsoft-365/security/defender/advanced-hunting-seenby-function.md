---
title: Microsoft 365 Defenderの高度な捜索における SeenBy() 関数
description: SeenBy() 関数を使用して、オンボードされたデバイスが特定のデバイスを検出したデバイスを検索する方法について説明します
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, スキーマ参照, kusto, SeenBy, デバイス検出, 関数, エンリッチメント
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
ms.openlocfilehash: 4a17efeeaf62ddcf63988f055ca93b536e68c962
ms.sourcegitcommit: f30616b90b382409f53a056b7a6c8be078e6866f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2022
ms.locfileid: "66993780"
---
# <a name="seenby"></a>SeenBy()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

この `SeenBy()` 関数が呼び出され、デバイス検出機能を使用して特定のデバイスを見たオンボードデバイスの一覧が表示されます。

この関数は、次の列を持つテーブルを返します。

| Column | データ型 | 説明 |
|------------|---------------|-------------|
| `DeviceId` | `string` | サービス内のデバイスの一意の識別子 |


## <a name="syntax"></a>構文

```kusto
invoke SeenBy(x)
```

- ここで **、x** は目的のデバイス ID です

>[!TIP]
> エンリッチメント関数は、利用可能な場合にのみ補足情報を表示します。 情報の可用性はさまざまであり、多くの要因によって異なります。 クエリで SeenBy() を使用する場合、またはカスタム検出を作成する場合は、この点を考慮してください。 最適な結果を得るには、DeviceInfo テーブルで SeenBy() 関数を使用することをお勧めします。

### <a name="example-obtain-list-of-onboarded-devices-that-have-seen-a-device"></a>例: デバイスが表示されたオンボードデバイスの一覧を取得する

```kusto
DeviceInfo 
| where OnboardingStatus <> "Onboarded" 
| limit 100 | invoke SeenBy()
```

## <a name="related-topics"></a>関連項目
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [その他のクエリの例を取得する](advanced-hunting-shared-queries.md)
