---
title: 高度なハンティング スキーマの DeviceTvmSoftwareVulnerabilities テーブル
description: デバイスで見つかったソフトウェアの脆弱性と、高度なハンティング スキーマの DeviceTvmSoftwareVulnerabilities テーブルの各脆弱性に対処する利用可能なセキュリティ更新プログラムの一覧について説明します。
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, スキーマ参照, kusto, テーブル, データ型, 説明, 脅威& 脆弱性の管理, TVM, デバイス管理, ソフトウェア, インベントリ, 脆弱性, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: a6588134ba2cdf166a465998cd0b1a4fd7134dbb
ms.sourcegitcommit: 6dcc3b039e0f0b9bae17c386f14ed2b577b453a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2021
ms.locfileid: "61531525"
---
# <a name="devicetvmsoftwarevulnerabilities"></a>DeviceTvmSoftwareVulnerabilities

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

>[!IMPORTANT]
> 一部の情報は、リリース済みの製品に関連しており、商用リリースされる前に大幅に変更される可能性があります。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

`DeviceTvmSoftwareVulnerabilities`高度なハンティング スキーマの表には、インストールされているソフトウェア製品の脆弱性の[脅威&脆弱性管理](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)の一覧が含まれています。 このテーブルには、オペレーティング システム情報、CVE ID、および脆弱性の重要度の情報も含まれます。 たとえば、この表を使用して、ソフトウェアに重大な脆弱性があるデバイスに関連するイベントを探すことができます。 このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。

>[!NOTE]
> テーブルと`DeviceTvmSoftwareVulnerabilities`テーブルが`DeviceTvmSoftwareInventory`置き換えられました`DeviceTvmSoftwareInventoryVulnerabilities`。 最初の 2 つのテーブルには、脆弱性の管理アクティビティに通知したり、脆弱なデバイスを探したりするのに役立つ列が追加されています。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `DeviceId` | `string` | コンピューターの一意識別子 |
| `DeviceName` | `string` | コンピューターの完全修飾ドメイン名 (FQDN) |
| `OSPlatform` | `string` | コンピューターで実行されているオペレーティング システムのプラットフォームです。 Windows 11、Windows 10、Windows 7 など、同じファミリ内のバリエーションを含む特定のオペレーティング システムを示します。 |
| `OSVersion` | `string` | コンピューターで実行されているオペレーティング システムのバージョンです。 |
| `OSArchitecture` | `string` | コンピューターで実行されているオペレーティング システムのアーキテクチャです。 |
| `SoftwareVendor` | `string` | ソフトウェア発行元の名前 |
| `SoftwareName` | `string` | ソフトウェア製品の名前 |
| `SoftwareVersion` | `string` | ソフトウェア製品のバージョン番号 |
| `CveId` | `string` | 共通脆弱性識別子 (CVE) システムでセキュリティの脆弱性に割り当てられている一意の識別子  |
| `VulnerabilitySeverityLevel` | `string` | CVSS スコアと脅威の度合いの影響を受ける動的要因に基づいて、セキュリティの脆弱性に割り当てられている重大度レベル |
| `RecommendedSecurityUpdate` | `string` | ソフトウェア発行元が脆弱性に対処するために提供するセキュリティ更新プログラムの名前または説明 |
| `RecommendedSecurityUpdateId` | `string` | 該当するガイダンスまたはサポート情報 (KB) の記事の該当するセキュリティ更新プログラムまたは識別子の識別子 |



## <a name="related-topics"></a>関連項目

- [積極的に脅威を捜索する](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
- [脅威および脆弱性管理の概要](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)