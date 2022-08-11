---
title: 高度なハンティング スキーマの DeviceAlertEvents テーブル
description: 高度なハンティング スキーマの DeviceAlertEvents テーブルでアラート生成イベントについて説明します
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, mdatp, microsoft defender atp, Microsoft Defender for endpoint, wdatp search, クエリ, テレメトリ, スキーマ参照, kusto, テーブル, 列, データ型, 説明, DeviceAlertEvents, アラート, 重大度, カテゴリ
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/22/2020
ms.technology: mde
ms.openlocfilehash: 1742c674cb982282d8edbe73e43e6ea59fedf8f6
ms.sourcegitcommit: 414682b9bf42dc19a89c893d3c515aee9765b6e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2022
ms.locfileid: "67281841"
---
# <a name="devicealertevents"></a>DeviceAlertEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!IMPORTANT]
> テーブルとテーブルは`AlertInfo`、`AlertEvidence`Microsoft Defender for Endpoint スキーマ内のテーブルを置き換えます`DeviceAlertEvents`。 詳細については、「 [DeviceAlertEvents テーブルのマップ」を](/microsoft-365/security/defender/advanced-hunting-migrate-from-mde)参照してください。

Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

`DeviceAlertEvents` [高度なハンティング](advanced-hunting-overview.md) スキーマの表には、Microsoft 365 Defenderのアラートに関する情報が含まれています。 このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。

高度なハンティング スキーマの他のテーブルについては、 [高度なハンティング スキーマリファレンスを](advanced-hunting-schema-reference.md)参照してください。

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
|`AttackTechniques`|文字列|MITRE ATT&アラートをトリガーしたアクティビティに関連付けられた CK 手法|
|`ReportId`|long|繰り返しカウンターに基づくイベント識別子。 一意のイベントを識別するには、この列を列と`Timestamp`共に使用する`DeviceName`必要があります。|
|`Table`|文字列|イベントの詳細を含むテーブル|

## <a name="related-topics"></a>関連項目

- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [スキーマを理解する](advanced-hunting-schema-reference.md)
