---
title: 高度な検索スキーマの DeviceTvmSoftwareInventoryVulnerabilities テーブル
description: お使いのデバイスのソフトウェアのインベントリと、その脆弱性の詳細については、高度な検索スキーマの DeviceTvmSoftwareInventoryVulnerabilities テーブルを参照してください。
keywords: 高度な検索、脅威の検索、サイバー脅威の検出、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、description、threat & 脆弱性管理、TVM、device management、software、inventory、脆弱性、CVE ID、OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: d8858fe9acd8183ad0d8644a9d5e4d70d32990a6
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413224"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a>DeviceTvmSoftwareInventoryVulnerabilities

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft Threat Protection



高度な検索スキーマの `DeviceTvmSoftwareInventoryVulnerabilities` のテーブルには、お使いのデバイス上のソフトウェアの [ の脅威および脆弱性管理 ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) のインベントリと、これらのソフトウェア製品の既知の脆弱性に関する情報が含まれています。 このテーブルには、オペレーティング システム情報、CVE ID、および脆弱性の重要度の情報も含まれます。 このテーブルの情報を返すクエリを作成するには、この参照を使用できます。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `DeviceId` | string | コンピューターの一意識別子 |
| `DeviceName` | string | コンピューターの完全修飾ドメイン名 (FQDN) |
| `OSPlatform` | string | コンピューターで実行されているオペレーティング システムのプラットフォームです。 これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。 |
| `OSVersion` | string | コンピューターで実行されているオペレーティング システムのバージョンです。 |
| `OSArchitecture` | string | コンピューターで実行されているオペレーティング システムのアーキテクチャです。 |
| `SoftwareVendor` | string | ソフトウェアベンダーの名前 |
| `SoftwareName` | string | ソフトウェア製品の名前 |
| `SoftwareVersion` | string | ソフトウェア製品のバージョン番号 |
| `CveId` | string | 共通脆弱性識別子 (CVE) システムでセキュリティの脆弱性に割り当てられている一意の識別子  |
| `VulnerabilitySeverityLevel` | string | CVSS スコアと脅威の度合いの影響を受ける動的要因に基づいて、セキュリティの脆弱性に割り当てられている重大度レベル |



## <a name="related-topics"></a>関連項目

- [積極的に脅威を捜索する](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 間での捜索](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
- [脅威および脆弱性管理の概要](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
