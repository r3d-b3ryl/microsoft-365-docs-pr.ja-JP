---
title: 高度なハンティング スキーマの DeviceTvmInfoGathering テーブル
description: 高度なハンティング スキーマの DeviceTvmInfoGathering テーブルで、さまざまな構成の状態やデバイスの攻撃領域の状態など、評価イベントについて説明します。
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
ms.openlocfilehash: 738168153738f8bf4e12220829114efc0cc8beb2
ms.sourcegitcommit: c6f1486617b39565bfd8f662ee6ad65a9cefd3e3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "66532784"
---
# <a name="devicetvminfogathering"></a>DeviceTvmInfoGathering

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

>[!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

`DeviceTvmInfoGathering`高度なハンティング スキーマの表には、さまざまな構成の状態やデバイスの攻撃領域の状態など、[Microsoft Defender 脆弱性の管理](/microsoft-365/security/defender-vulnerability-management/defender-vulnerability-management)評価イベントが含まれています。 この表を使用すると、ゼロ日間の軽減策に関連する評価イベント、脅威分析軽減状態レポートをサポートする新たな脅威の体制評価、サーバーでの TLS プロトコル バージョンの有効化などを探すことができます。 このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | イベントが記録された日付と時刻 |
| `LastSeenTime` | `datetime` | サービスがデバイスを最後に見た日時 |
| `DeviceId` | `string` | サービス内のデバイスの一意の識別子 |
| `DeviceName` | `string` | デバイスの完全修飾ドメイン名 (FQDN) |
| `OSPlatform` | `string` | デバイスで実行されているオペレーティング システムのプラットフォーム。 これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。 |
| `AdditionalFields` | `string` | イベントに関する追加情報  |

たとえば、回避策の軽減策がまだ適用されていないか、適用され、再起動が保留されている [Log4Shell の脆弱性](https://www.microsoft.com/security/blog/2021/12/11/guidance-for-preventing-detecting-and-hunting-for-cve-2021-44228-log4j-2-exploitation/) の影響を受けるデバイスを表示するには、次のクエリを使用します。

```kusto
DeviceTvmInfoGathering
| where AdditionalFields.Log4JEnvironmentVariableMitigation in ("RebootRequired", "false")
| join kind=inner (
    DeviceTvmSoftwareVulnerabilities
    | where CveId == "CVE-2021-44228"
) on DeviceId
| summarize any(DeviceName), any(AdditionalFields.Log4JEnvironmentVariableMitigation) by DeviceId
```

## <a name="related-topics"></a>関連項目
- [DeviceTvmInfoGatheringKB](advanced-hunting-devicetvminfogatheringkb-table.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
- [Defender 脆弱性管理の概要](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
- [Microsoft Defender for Endpointで Log4Shell の脆弱性を管理する方法について説明します](/microsoft-365/security/defender-endpoint/tvm-manage-log4shell-guidance)