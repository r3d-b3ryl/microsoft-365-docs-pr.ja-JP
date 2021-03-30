---
title: 高度なハンティング スキーマの DeviceTvmSoftwareInventory テーブル
description: 高度なハンティング スキーマの DeviceTvmSoftwareInventory テーブルで、デバイス内のソフトウェアのインベントリについて説明します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、mdatp、microsoft Defender atp、wdatp 検索、クエリ、テレメトリ、スキーマ参照、kusto、テーブル、列、データ型、説明、脅威& 脆弱性管理、TVM、デバイス管理、ソフトウェア、インベントリ、脆弱性、CVE ID、OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.technology: mde
ms.openlocfilehash: 18e43d8e38c24a8aa28c6455dc1a769b8da0df2b
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408625"
---
# <a name="devicetvmsoftwareinventory"></a>DeviceTvmSoftwareInventory

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

>Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

高度 `DeviceTvmSoftwareInventory` な検索スキーマの表には、ネットワーク内[](next-gen-threat-and-vuln-mgt.md)のデバイスに現在インストールされているソフトウェアの脅威と脆弱性管理インベントリ (サポート情報の終了など) が含まれている。 たとえば、現在脆弱なソフトウェア バージョンでインストールされているデバイスに関連するイベントを探します。 このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。

DeviceTVMSoftwareInventory には、脅威と脆弱性の管理が共通プラットフォーム列挙 (CPE) と一致する可能性があるすべてのソフトウェアが含まれている 。脆弱性が存在するかどうかに関わりはありません。

>[!NOTE]
>テーブル `DeviceTvmSoftwareInventory` と `DeviceTvmSoftwareVulnerabilities` テーブルがテーブルを置き換 `DeviceTvmSoftwareInventoryVulnerabilities` えました。 最初の 2 つの表には、脆弱性管理アクティビティの通知に使用できる列が追加されています。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `DeviceId` | string | サービス内のデバイスの一意の識別子。 |
| `DeviceName` | string | デバイスの完全修飾ドメイン名 (FQDN)。 |
| `OSPlatform` | string | デバイスで実行されているオペレーティング システムのプラットフォーム。 これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。 |
| `OSVersion` | string | デバイスで実行されているオペレーティング システムのバージョン。 |
| `OSArchitecture` | string | デバイスで実行されているオペレーティング システムのアーキテクチャ。 |
| `SoftwareVendor` | string | ソフトウェア ベンダーの名前。 |
| `SoftwareName` | string | ソフトウェア製品の名前。 |
| `SoftwareVersion` | string | ソフトウェア製品のバージョン番号。 |
| `EndOfSupportStatus` | string | 指定したサポート終了日 (EOS) または終了 (EOL) の日付を基準にしたソフトウェア製品のライフサイクル ステージを示します。 |
| `EndOfSupportDate` | string | ソフトウェア製品のサポート終了日 (EOS) または終了 (EOL) 日付。 |

## <a name="related-topics"></a>関連項目

- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [スキーマを理解する](advanced-hunting-schema-reference.md)
- [脅威および脆弱性管理の概要](next-gen-threat-and-vuln-mgt.md)
