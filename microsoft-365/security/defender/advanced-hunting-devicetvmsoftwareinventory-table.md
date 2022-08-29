---
title: 高度なハンティング スキーマの DeviceTvmSoftwareInventory テーブル
description: 高度なハンティング スキーマの DeviceTvmSoftwareInventory テーブルで、デバイス内のソフトウェアのインベントリについて説明します。
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, スキーマ参照, kusto, テーブル, 列, データ型, 説明, 脅威&脆弱性管理, TVM, デバイス管理, ソフトウェア, インベントリ, 脆弱性, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: 64ecf8a3f0d040ce8645d6dde803126efa11060f
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67329313"
---
# <a name="devicetvmsoftwareinventory"></a>DeviceTvmSoftwareInventory

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

>[!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。


`DeviceTvmSoftwareInventory`高度なハンティング スキーマの表には、サポート終了情報など、ネットワーク内のデバイスに現在インストールされているソフトウェアの[Microsoft Defender 脆弱性の管理 インベントリが](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)含まれています。 たとえば、現在脆弱なソフトウェア バージョンでインストールされているデバイスに関連するイベントを探すことができます。 このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。

>[!NOTE]
> テーブルと`DeviceTvmSoftwareVulnerabilities`テーブルが`DeviceTvmSoftwareInventory`置き換えられました`DeviceTvmSoftwareInventoryVulnerabilities`。 最初の 2 つのテーブルには、脆弱な管理アクティビティに通知したり、脆弱なデバイスを探したりする際に役立つ列が追加されています。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `DeviceId` | `string` | コンピューターの一意識別子 |
| `DeviceName` | `string` | コンピューターの完全修飾ドメイン名 (FQDN) |
| `OSPlatform` | `string` | コンピューターで実行されているオペレーティング システムのプラットフォームです。 これは、Windows 11、Windows 10、Windows 7 など、同じファミリ内のバリエーションを含む特定のオペレーティング システムを示します。 |
| `OSVersion` | `string` | コンピューターで実行されているオペレーティング システムのバージョンです。 |
| `OSArchitecture` | `string` | コンピューターで実行されているオペレーティング システムのアーキテクチャです。 |
| `SoftwareVendor` | `string` | ソフトウェア ベンダーの名前 |
| `SoftwareName` | `string` | ソフトウェア製品の名前 |
| `SoftwareVersion` | `string` | ソフトウェア製品のバージョン番号 |
| `EndOfSupportStatus` | `string` | 指定されたサポート終了日 (EOS) または有効期限 (EOL) の日付に対するソフトウェア製品のライフサイクル ステージを示します。 |
| `EndOfSupportDate` | `string` | ソフトウェア製品のサポート終了日 (EOS) または EOL (EOL) の日付 |
| `ProductCodeCpe` | `string` | ソフトウェア製品の CPE、または CPE がない場合は "利用できない" |
| `CveTags` | `string` | CVE に関連するタグの配列。 現在サポートされているタグは、"ZeroDay" と "NoSecurityUpdate" です。

## <a name="related-topics"></a>関連項目

- [積極的に脅威を捜索する](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
- [Microsoft Defender 脆弱性の管理の概要](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)