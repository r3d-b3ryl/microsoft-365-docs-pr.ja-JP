---
title: 高度なハンティング スキーマMicrosoft 365 Defender名前付けの変更
description: 高度な検索スキーマの名前付け変更テーブルと列を追跡および確認する
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、data、名前付け変更、名前の変更
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
ms.openlocfilehash: 4082dbe9964c115df279f04d4a25ce5fbeb2cec2
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60159116"
---
# <a name="advanced-hunting-schema---naming-changes"></a>高度な検索スキーマ - 名前付けの変更

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

高度 [な検索スキーマは](advanced-hunting-schema-tables.md) 、新しいテーブルと列を追加するために定期的に更新されます。 ユーザー エクスペリエンスを向上させるために、既存の列名の名前が変更または置き換えられる場合があります。 クエリに影響を与える可能性がある名前の変更を確認するには、この記事を参照してください。

名前付けの変更は、カスタム検出ルールで使用されるクエリなど、セキュリティ センターに保存されるクエリに自動的に適用されます。 これらのクエリを手動で更新する必要はありません。 ただし、次のクエリを更新する必要があります。
- API を使用して実行されるクエリ
- セキュリティ センター外の別の場所に保存されるクエリ

## <a name="december-2020"></a>2020 年 12 月

| テーブル名 | 元の列名 | 新しい列名 | 変更の理由
|--|--|--|--|
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | お客様のフィードバック |
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | お客様のフィードバック |
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | お客様のフィードバック |

## <a name="january-2021"></a>2021 年 1 月

| 列名 | 元の値の名前 | 新しい値の名前 | 変更の理由
|--|--|--|--|
| `DetectionSource` | MCAS | Microsoft Cloud App Security | リブランド |
| `DetectionSource` | WindowsDefenderAtp| EDR| リブランド |
| `DetectionSource` | WindowsDefenderAv | ウイルス対策 | リブランド |
| `DetectionSource` | WindowsDefenderSmartScreen |  SmartScreen | リブランド |
| `DetectionSource` | CustomerTI | カスタム TI | リブランド |
| `DetectionSource` | OfficeATP | Microsoft Defender for Office 365 | リブランド |
| `DetectionSource` | MTP | Microsoft 365 Defender | リブランド |
| `DetectionSource` | AzureATP | Microsoft Defender for Identity | リブランド |
| `DetectionSource` | CustomDetection | カスタム検出 | リブランド |
| `DetectionSource` | AutomatedInvestigation |自動調査 | リブランド |
| `DetectionSource` | ThreatExperts | Microsoft 脅威エキスパート | リブランド |
| `DetectionSource` | サードパーティ TI | サードパーティ製センサー | リブランド |
| `ServiceSource` | Microsoft Defender ATP| Microsoft Defender for Endpoint | リブランド |
|`ServiceSource` |Microsoft Threat Protection | Microsoft 365 Defender | リブランド |
| `ServiceSource` | Office 365 ATP |Microsoft Defender for Office 365 | リブランド |
| `ServiceSource` |Azure ATP |Microsoft Defender for Identity | リブランド |

`DetectionSource` は [AlertInfo テーブルで使用](advanced-hunting-alertinfo-table.md) できます。 `ServiceSource` は [、AlertEvidence テーブルと](advanced-hunting-alertevidence-table.md) [AlertInfo テーブルで使用](advanced-hunting-alertinfo-table.md) できます。 

## <a name="february-2021"></a>2021 年 2 月

1. [EmailAttachmentInfo テーブル](advanced-hunting-emailattachmentinfo-table.md)と[EmailEvents](advanced-hunting-emailevents-table.md)テーブルでは、列と列が `MalwareFilterVerdict` `PhishFilterVerdict` 列に置き換 `ThreatTypes` えされています。 列 `MalwareDetectionMethod` と `PhishDetectionMethod` 列も列に置き換 `DetectionMethods` えました。 この合理化により、新しい列の下に詳細な情報を提供できます。 マッピングは以下に示します。

    | テーブル名 | 元の列名 | 新しい列名 | 変更の理由
    |--|--|--|--|
    | `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | その他の検出方法を含める |
    | `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | 脅威の種類を追加する |
    | `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | その他の検出方法を含める |
    | `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | 脅威の種類を追加する |


2. 列とテーブルに、電子メールの脅威に関する詳細を示す列 `EmailAttachmentInfo` `EmailEvents` `ThreatNames` が追加されました。 この列には、スパムやフィッシングのような値が含まれます。

3. [DeviceInfo テーブルの](advanced-hunting-deviceinfo-table.md)列は、顧客からのフィードバックに基 `DeviceObjectId` `AadDeviceId` づいて列に置き換えられます。

4. [DeviceEvents テーブルでは](advanced-hunting-deviceevents-table.md)、アクションの説明を反映するようにいくつかの ActionType 名が変更されました。 変更の詳細については、以下を参照してください。

    | テーブル名 | 元の ActionType 名 | 新しい ActionType 名 | 変更の理由
    |--|--|--|--|
    | `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | お客様のフィードバック |
    | `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | お客様のフィードバック |
    | `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | お客様のフィードバック |
    | `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | お客様のフィードバック |

## <a name="march-2021"></a>2021 年 3 月

テーブル `DeviceTvmSoftwareInventoryVulnerabilities` は廃止されました。 テーブルとテーブルを置 `DeviceTvmSoftwareInventory` き換 `DeviceTvmSoftwareVulnerabilities` える。

## <a name="may-2021"></a>2021 年 5 月

テーブル `AppFileEvents` は廃止されました。 この表には、以前は表に含まれる情報と、クラウド サービス内の `CloudAppEvents` `AppFileEvents` 他のアクティビティが含まれています。

## <a name="related-topics"></a>関連トピック
- [高度な追求の概要](advanced-hunting-overview.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)