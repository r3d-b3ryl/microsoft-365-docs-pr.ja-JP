---
title: 高度な狩猟スキーマの DeviceTvmSoftwareVulnerabilities テーブル
description: デバイスで見つかったソフトウェアの脆弱性と、高度なハンティング スキーマの DeviceTvmSoftwareVulnerabilities テーブルの各脆弱性に対処する利用可能なセキュリティ更新プログラムの一覧について説明します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、テーブル、列、データ型、説明、脅威 & 脆弱性の管理、TVM、デバイス管理、ソフトウェア、インベントリ、脆弱性、CVE ID、OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: e8febbf47e8aa7c6d4e78bd783c5274f2b20c9af
ms.sourcegitcommit: 07405a81513d1c63071a128b9d5070d3a3bfe1cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2021
ms.locfileid: "61121699"
---
# <a name="devicetvmsoftwarevulnerabilities"></a>DeviceTvmSoftwareVulnerabilities

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

>[!IMPORTANT]
> 一部の情報は、製品が市販される前に大幅に変更される可能性があるプレリリース製品に関連しています。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

高度 `DeviceTvmSoftwareVulnerabilities` な検索スキーマの表には、インストールされている [ソフトウェア製品の&](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) の脅威と脆弱性管理の一覧が記載されています。 このテーブルには、オペレーティング システム情報、CVE ID、および脆弱性の重要度の情報も含まれます。 たとえば、この表を使用して、ソフトウェアに重大な脆弱性を持つデバイスに関連するイベントを探します。 このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。

>[!NOTE]
> テーブル `DeviceTvmSoftwareInventory` と `DeviceTvmSoftwareVulnerabilities` テーブルがテーブルを置き換 `DeviceTvmSoftwareInventoryVulnerabilities` えました。 最初の 2 つのテーブルには、ユーザーにアクティビティを通知したり、脆弱なデバイス脆弱性の管理を探したりするために使用できる列が追加されています。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `DeviceId` | string | コンピューターの一意識別子 |
| `DeviceName` | string | コンピューターの完全修飾ドメイン名 (FQDN) |
| `OSPlatform` | string | コンピューターで実行されているオペレーティング システムのプラットフォームです。 11、Windows Windows 10、および 7 など、同じファミリ内Windows 10オペレーティング システムWindows示します。 |
| `OSVersion` | string | コンピューターで実行されているオペレーティング システムのバージョンです。 |
| `OSArchitecture` | string | コンピューターで実行されているオペレーティング システムのアーキテクチャです。 |
| `SoftwareVendor` | string | ソフトウェア発行元の名前 |
| `SoftwareName` | string | ソフトウェア製品の名前 |
| `SoftwareVersion` | string | ソフトウェア製品のバージョン番号 |
| `CveId` | string | 共通脆弱性識別子 (CVE) システムでセキュリティの脆弱性に割り当てられている一意の識別子  |
| `VulnerabilitySeverityLevel` | string | CVSS スコアと脅威の度合いの影響を受ける動的要因に基づいて、セキュリティの脆弱性に割り当てられている重大度レベル |
| `RecommendedSecurityUpdate` | string | 脆弱性に対処するためにソフトウェア発行元が提供するセキュリティ更新プログラムの名前または説明 |
| `RecommendedSecurityUpdateId` | string | 対応するガイダンスまたはナレッジ ベース (KB) 記事の該当するセキュリティ更新プログラムまたは識別子の識別子 |



## <a name="related-topics"></a>関連項目

- [積極的に脅威を捜索する](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
- [脅威および脆弱性管理の概要](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)