---
title: 高度なハンティング スキーマの DeviceTvmSoftwareEvidenceBeta テーブル
description: 高度なハンティング スキーマで DeviceTvmSoftwareEvidenceBeta テーブルを使用する方法について説明します。
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, スキーマ参照, kusto, テーブル, 列, データ型, 説明, 脅威&脆弱性管理, 証拠, ソフトウェア証拠, TVM, デバイス管理, ソフトウェア, インベントリ, 脆弱性, CVE ID, OS DeviceTvmSoftwareEvidenceBeta
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
ms.openlocfilehash: 1e9f88822bdcf21c71f21c43eabd91b737bab350
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67480561"
---
# <a name="devicetvmsoftwareevidencebeta"></a>DeviceTvmSoftwareEvidenceBeta

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

> [!IMPORTANT]
> テーブルは `DeviceTvmSoftwareEvidenceBeta` 現在ベータ版です。 ベータ版を終了すると、最終的なテーブル名が変更され、列名も変更される可能性があります。 その後、変更によって、以前の名前を使用しているクエリが中断される可能性があります。 このテーブルが完成したら、ユーザーはクエリを確認して調整することをお勧めします。 

`DeviceTvmSoftwareEvidenceBeta`高度なハンティング スキーマの表には、[ソフトウェア証拠セクション](/microsoft-365/security/defender-endpoint/tvm-software-inventory#software-evidence)に関連[するMicrosoft Defender 脆弱性の管理](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)からのデータが含まれています。 この表では、デバイスで特定のソフトウェアが検出された場所の証拠を表示できます。 たとえば、このテーブルを使用して、特定のソフトウェアのファイル パスを識別できます。 このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。

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

- [Microsoft Defender 脆弱性の管理の概要](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
- [積極的に脅威を捜索する](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
