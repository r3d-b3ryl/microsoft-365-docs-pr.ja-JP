---
title: 高度なハンティング スキーマの DeviceAlertEvents テーブル
description: 高度なハンティング スキーマの DeviceAlertEvents テーブルのアラート生成イベントについて説明します。
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、mdatp、microsoft Defender atp、エンドポイント用の microsoft Defender、wdatp 検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、データ型、説明、DeviceAlertEvents、アラート、重大度、カテゴリ
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/22/2020
ms.technology: mde
ms.openlocfilehash: 6a56a1abab388e98af52fadc322d41484c1610a5
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59179463"
---
# <a name="devicealertevents"></a>DeviceAlertEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)



> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

高度 `DeviceAlertEvents` な検索スキーマの[表](advanced-hunting-overview.md)には、このスキーマのアラートに関する情報Microsoft Defender セキュリティ センター。 このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。

高度なハンティング スキーマの他のテーブルの詳細については、高度なハンティング [スキーマリファレンスを参照してください](advanced-hunting-schema-reference.md)。

|列名|データ型|説明|
|---|---|---|
|`AlertId`|string|アラートの一意識別子|
|`Timestamp`|datetime|イベントが記録された日付と時刻|
|`DeviceId`|string|サービス内のデバイスの一意の識別子|
|`DeviceName`|string|デバイスの完全修飾ドメイン名 (FQDN)|
|`Severity`|文字列|アラートで識別された脅威インジケーターまたは侵害アクティビティの起こりうる影響 (高、中、低) を示します。|
|`Category`|文字列|アラートで識別された脅威インジケーターまたは侵害アクティビティの種類|
|`Title`|文字列|アラートのタイトル|
|`FileName`|文字列|記録されたアクションが適用されたファイルの名前|
|`SHA1`|文字列|記録されたアクションが適用されたファイルの SHA-1|
|`RemoteUrl`|文字列|に接続されていた URL または完全修飾ドメイン名 (FQDN)|
|`RemoteIP`|文字列|に接続されていた IP アドレス|
|`AttackTechniques`|string|MITRE ATT&をトリガーしたアクティビティに関連付けられた CK テクニックを使用します。|
|`ReportId`|long|繰り返しカウンターに基づくイベント識別子。 一意のイベントを識別するには、この列を and 列と組み合わせて `DeviceName` 使用する必要 `Timestamp` があります。|
|`Table`|文字列|イベントの詳細を含むテーブル|

## <a name="related-topics"></a>関連項目

- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [スキーマを理解する](advanced-hunting-schema-reference.md)
