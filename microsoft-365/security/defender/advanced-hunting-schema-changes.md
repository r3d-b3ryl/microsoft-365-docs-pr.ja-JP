---
title: Microsoft 365 Defender高度なハンティング スキーマでの名前付けの変更
description: 高度なハンティング スキーマの名前付け変更テーブルと列を追跡および確認する
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, スキーマ参照, kusto, テーブル, データ, 名前変更, 名前変更
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
ms.openlocfilehash: 12653741e10eaba0e8a658e24d3001e16af4e5d5
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67482518"
---
# <a name="advanced-hunting-schema---naming-changes"></a>高度なハンティング スキーマ - 名前付けの変更

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[高度なハンティング スキーマ](advanced-hunting-schema-tables.md)は、新しいテーブルと列を追加するために定期的に更新されます。 場合によっては、ユーザー エクスペリエンスを向上させるために、既存の列名の名前が変更または置き換えられます。 この記事を参照して、クエリに影響を与える可能性のある名前付けの変更を確認してください。

名前付けの変更は、カスタム検出ルールで使用されるクエリを含め、Defender for Cloud に保存されるクエリに自動的に適用されます。 これらのクエリを手動で更新する必要はありません。 ただし、次のクエリを更新する必要があります。
- API を使用して実行されるクエリ
- Defender for Cloud の外部の他の場所に保存されるクエリ

## <a name="december-2020"></a>2020 年 12 月

| テーブル名 | 元の列名 | 新しい列名 | 変更の理由
|--|--|--|--|
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | お客様のフィードバック |
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | お客様のフィードバック |
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | お客様のフィードバック |

## <a name="january-2021"></a>2021 年 1 月

| 列名 | 元の値の名前 | 新しい値の名前 | 変更の理由
|--|--|--|--|
| `DetectionSource` | Defender for Cloud Apps | Microsoft Defender for Cloud Apps | ブランド |
| `DetectionSource` | WindowsDefenderAtp| EDR| ブランド |
| `DetectionSource` | WindowsDefenderAv | ウイルス対策 | ブランド |
| `DetectionSource` | WindowsDefenderSmartScreen |  Smartscreen | ブランド |
| `DetectionSource` | CustomerTI | カスタム TI | ブランド |
| `DetectionSource` | OfficeATP | Microsoft Defender for Office 365 | ブランド |
| `DetectionSource` | Mtp | Microsoft 365 Defender | ブランド |
| `DetectionSource` | AzureATP | Microsoft Defender for Identity | ブランド |
| `DetectionSource` | CustomDetection | カスタム検出 | ブランド |
| `DetectionSource` | AutomatedInvestigation |自動調査 | ブランド |
| `DetectionSource` | ThreatExperts | Microsoft 脅威エキスパート | ブランド |
| `DetectionSource` | サード パーティの TI | サード パーティ製センサー | ブランド |
| `ServiceSource` | Microsoft Defender ATP| Microsoft Defender for Endpoint | ブランド |
|`ServiceSource` |Microsoft Threat Protection | Microsoft 365 Defender | ブランド |
| `ServiceSource` | Office 365 ATP |Microsoft Defender for Office 365 | ブランド |
| `ServiceSource` |Azure ATP |Microsoft Defender for Identity | ブランド |

`DetectionSource` は [AlertInfo](advanced-hunting-alertinfo-table.md) テーブルで使用できます。 `ServiceSource` は [、AlertEvidence](advanced-hunting-alertevidence-table.md) テーブルと [AlertInfo テーブルで](advanced-hunting-alertinfo-table.md) 使用できます。 

## <a name="february-2021"></a>2021年2月

1. [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) テーブルと [EmailEvents](advanced-hunting-emailevents-table.md) テーブルでは、`MalwareFilterVerdict`列と`PhishFilterVerdict`列は列に`ThreatTypes`置き換えられています。 `MalwareDetectionMethod`列と`PhishDetectionMethod`列も列に`DetectionMethods`置き換えられました。 この合理化により、新しい列の下に詳細情報を提供できます。 マッピングは次のとおりです。

    | テーブル名 | 元の列名 | 新しい列名 | 変更の理由
    |--|--|--|--|
    | `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | その他の検出方法を含める |
    | `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | その他の脅威の種類を含める |
    | `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | その他の検出方法を含める |
    | `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | その他の脅威の種類を含める |


2. `EmailAttachmentInfo`テーブルと`EmailEvents`テーブルに、電子メールの`ThreatNames`脅威に関する詳細情報を提供するために列が追加されました。 この列には、スパムやフィッシングなどの値が含まれています。

3. [DeviceInfo](advanced-hunting-deviceinfo-table.md) テーブルでは、顧客からのフィードバックに`DeviceObjectId`基づいて列が列に`AadDeviceId`置き換えられました。

4. [DeviceEvents](advanced-hunting-deviceevents-table.md) テーブルでは、アクションの説明をより適切に反映するために、いくつかの ActionType 名が変更されました。 変更の詳細については、以下をご覧ください。

    | テーブル名 | 元の ActionType 名 | 新しい ActionType 名 | 変更の理由
    |--|--|--|--|
    | `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | お客様のフィードバック |
    | `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | お客様のフィードバック |
    | `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | お客様のフィードバック |
    | `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | お客様のフィードバック |

## <a name="march-2021"></a>2021 年 3 月

テーブルは `DeviceTvmSoftwareInventoryVulnerabilities` 非推奨になりました。 置き換えるのがテーブル `DeviceTvmSoftwareInventory` です `DeviceTvmSoftwareVulnerabilities` 。

## <a name="may-2021"></a>2021 年 5 月

テーブルは `AppFileEvents` 非推奨になりました。 この `CloudAppEvents` 表には、クラウド サービスの他の `AppFileEvents` アクティビティと共に、以前はテーブル内に存在した情報が含まれています。

## <a name="related-topics"></a>関連項目
- [高度な追求の概要](advanced-hunting-overview.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
