---
title: DeviceTvmSoftwareEvidence 高度なハンティング スキーマのBeta テーブル
description: 高度なハンティング スキーマで DeviceTvmSoftwareEvidenceBeta テーブルを使用する方法について説明します。
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、列、データ型、説明、脅威& 脆弱性の管理、証拠、ソフトウェア証拠、TVM、デバイス管理、ソフトウェア、インベントリ、脆弱性、CVE ID、OS DeviceTvmSoftwareEvidenceBeta
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
ms.openlocfilehash: dd71e4b3554b2cd45b648300f84ec96a73e5116b
ms.sourcegitcommit: f8fbabf1ec7421cd7ad36aa52b8856fb863cf284
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/28/2021
ms.locfileid: "61620550"
---
# <a name="devicetvmsoftwareevidencebeta"></a>DeviceTvmSoftwareEvidenceBeta

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

> [!IMPORTANT]
> このテーブルは現在ベータ版で、デバイスにソフトウェアが存在するかどうかを示す証拠をすばやく探し出す機能 `DeviceTvmSoftwareEvidenceBeta` が提供されています。

高度 `DeviceTvmSoftwareEvidenceBeta` な検索スキーマの表には、[ソフトウェアの証拠] セクションに関連&[の](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)脆弱性管理のデータ[が含まれている。](/microsoft-365/security/defender-endpoint/tvm-software-inventory#software-evidence) 次の表では、デバイスで特定のソフトウェアが検出された場所の証拠を表示できます。 たとえば、この表を使用して、特定のソフトウェアのファイル パスを識別できます。 このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `DeviceId` | `string` | サービス内のデバイスの一意の識別子 |
| `SoftwareVendor` | `string` | ソフトウェア発行元の名前 |
| `SoftwareName` | `string` | ソフトウェア製品の名前 |
| `SoftwareVersion` | `string` | ソフトウェア製品のバージョン番号 |
| `RegistryPaths` | `dynamic` | デバイス上のソフトウェアの存在を示す証拠が検出されたレジストリ パス |
| `DiskPaths` | `dynamic` | デバイス上のソフトウェアの存在を示すファイル レベルの証拠が検出されたディスク パス |
| `LastSeenTime` | `string` | このサービスでデバイスが最後に表示された日時 |




## <a name="related-topics"></a>関連項目

- [脅威および脆弱性管理の概要](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
- [積極的に脅威を捜索する](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
