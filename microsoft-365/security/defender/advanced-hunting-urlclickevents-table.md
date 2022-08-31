---
title: 高度なハンティング スキーマの UrlClickEvents テーブル
description: 高度なハンティング スキーマの UrlClickEvents テーブルを使用して、フィッシング キャンペーンと疑わしいクリックを検出する方法について説明します。
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, スキーマ参照, kusto, テーブル, 列, データ型, 説明, UrlClickEvents, SafeLinks, フィッシング, マルウェア, 悪意のあるクリック, outlook, チーム, 電子メール, office365
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
ms.openlocfilehash: 068e083321b465410df9e734660344c03e6b55ce
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67476046"
---
# <a name="urlclickevents"></a>UrlClickEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender
- Microsoft Defender for Office 365


`UrlClickEvents`高度な検索スキーマの表には、サポートされているデスクトップ、モバイル、および Web アプリの電子メール メッセージ、Microsoft Teams、Office 365 アプリからの[セーフ リンク](../office-365-security/safe-links.md)のクリックに関する情報が含まれています。 

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | ユーザーがリンクをクリックした日時 |
| `Url` | `string` | ユーザーがクリックした完全な URL |
| `ActionType` | `string` | [テナント許可のブロック] リストなど、テナント ポリシーが原因でクリックがセーフ リンクによって許可されたかブロックされたか、ブロックされたかを示します。|
| `AccountUpn` | `string` | リンクをクリックしたアカウントのユーザー プリンシパル名|
| `Workload` | `string` | ユーザーがリンクをクリックしたアプリケーション。値はEmail、Office、Teams です。|
| `NetworkMessageId` | `string` | Microsoft 365 によって生成されたクリックされたリンクを含む電子メールの一意の識別子|
| `IPAddress` | `string` | ユーザーがリンクをクリックしたデバイスのパブリック IP アドレス|
| `ThreatTypes` | `string` | URL がマルウェア、フィッシング、またはその他の脅威につながったかどうかを示すクリック時の判定|
| `DetectionMethods` | `string` | クリック時に脅威を特定するために使用された検出テクノロジ|
| `IsClickedThrough` | `bool` | ユーザーが元の URL までクリックできたか、許可されなかったかを示します。|
| `UrlChain` | `string` | リダイレクトに関連するシナリオの場合は、リダイレクト チェーンに存在する URL が含まれます。|
| `ReportId` | `string` | これは、クリック イベントの一意の識別子です。 クリックスルー シナリオでは、レポート ID の値が同じであるため、クリック イベントを関連付けるために使用する必要があることに注意してください。|

テーブルを使用 `UrlClickEvents` して、ユーザーが続行を許可されたリンクの一覧を返す次のクエリ例を試すことができます。 

```kusto
// Search for malicious links where user was allowed to proceed through
UrlClickEvents
| where ActionType == "ClickAllowed" or IsClickedThrough !="0"
| where ThreatTypes has "Phish"
| summarize by ReportId, IsClickedThrough, AccountUpn, NetworkMessageId, ThreatTypes, Timestamp
```

## <a name="related-topics"></a>関連項目

- [積極的に脅威を捜索する](advanced-hunting-overview.md)
- [Microsoft Defender for Office 365 の安全なリンク](../office-365-security/safe-links.md)
- [高度なハンティング クエリの結果に対してアクションを実行する](advanced-hunting-take-action.md)