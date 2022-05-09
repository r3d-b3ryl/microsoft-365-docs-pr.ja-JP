---
title: 露出したデバイスの追求
description: 脅威と脆弱性の管理を使用して、セキュリティ管理者、IT 管理者、SecOps の共同作業を支援する方法について説明します。
keywords: Microsoft Defender for Endpoint-tvm のシナリオ、Microsoft Defender for Endpoint、tvm、tvm のシナリオ、脅威&脆弱性の露出を減らす、脅威と脆弱性を減らす、セキュリティ構成を改善する、Microsoft Secure Score for Devices を増やす、脅威&脆弱性を増やす Microsoft Secure Score for Devices、デバイスの Microsoft Secure Score、公開スコア、セキュリティ制御
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 40544ab3879acd026d7f327e63d02bdb79d00d83
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2021
ms.locfileid: "61167972"
---
# <a name="hunt-for-exposed-devices---threat-and-vulnerability-management"></a>公開されているデバイスのハント - 脅威と脆弱性の管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [脅威と脆弱性の管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="use-advanced-hunting-to-find-devices-with-vulnerabilities"></a>高度な捜索を使用して、脆弱性を持つデバイスを見つける

高度な捜索は、クエリ ベースの脅威の捜索ツールで、最大 30 日間のロー データを検索できます。 ネットワーク内のイベントを事前に検査して、脅威インジケーターとエンティティを見つけることができます。 データへの柔軟なアクセスにより、既知の脅威と潜在的な脅威の両方に対する制約のない捜索が可能になります。 [高度なハンティングの詳細を確認する](advanced-hunting-overview.md)

### <a name="schema-tables"></a>スキーマ テーブル

- [DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md) - デバイスにインストールされているソフトウェアのインベントリ(バージョン情報やサポート終了の状態など)。

- [DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md) - デバイスで見つかったソフトウェアの脆弱性と、各脆弱性に対処する利用可能なセキュリティ更新プログラムの一覧。

- [DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md) - 悪用コードが公開されているかどうかなど、一般に公開されている脆弱性のナレッジ ベース。

- [DeviceTvmSecureConfigurationassessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) - 脅威と脆弱性の管理評価イベント。デバイス上のさまざまなセキュリティ構成の状態を示します。

- [DeviceTvmSecureConfigurationassessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) - Threat & Vulnerability Management がデバイスを評価するために使用するさまざまなセキュリティ構成のナレッジ ベース。には、さまざまな標準とベンチマークへのマッピングが含まれます

## <a name="check-which-devices-are-involved-in-high-severity-alerts"></a>重大度の高いアラートに関係するデバイスを確認する

1. Microsoft 365 Defender ポータルの左側のナビゲーション ウィンドウから、[**Hunting** **Advanced hunting] (高度なハンティング**\>) に移動します。

2. TVM の高度なハンティング スキーマまで下にスクロールして、列名を理解します。

3. 次のクエリを入力します。

    ```kusto
    // Search for devices with High active alerts or Critical CVE public exploit
    let DeviceWithHighAlerts = AlertInfo
    | where Severity == "High"
    | project Timestamp, AlertId, Title, ServiceSource, Severity
    | join kind=inner (AlertEvidence | where EntityType == "Machine" | project AlertId, DeviceId, DeviceName) on AlertId
    | summarize HighSevAlerts = dcount(AlertId) by DeviceId;
    let DeviceWithCriticalCve = DeviceTvmSoftwareVulnerabilities
    | join kind=inner(DeviceTvmSoftwareVulnerabilitiesKB) on CveId
    | where IsExploitAvailable == 1 and CvssScore >= 7
    | summarize NumOfVulnerabilities=dcount(CveId),
    DeviceName=any(DeviceName) by DeviceId;
    DeviceWithCriticalCve
    | join kind=inner DeviceWithHighAlerts on DeviceId
    | project DeviceId, DeviceName, NumOfVulnerabilities, HighSevAlerts
    ```

## <a name="related-topics"></a>関連項目

- [脅威と脆弱性の管理の概要](next-gen-threat-and-vuln-mgt.md)
- [セキュリティに関する推奨事項](tvm-security-recommendation.md)
- [API](next-gen-threat-and-vuln-mgt.md#apis)
- [脅威と脆弱性の管理 ロールのデータ アクセスを構成する](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group)
- [高度な追求の概要](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [すべての高度なハンティング テーブル](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference.md)
