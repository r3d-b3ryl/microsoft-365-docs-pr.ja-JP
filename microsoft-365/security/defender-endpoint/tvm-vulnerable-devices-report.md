---
title: 脆弱なデバイス レポート - 脅威と脆弱性の管理
description: 脆弱なデバイスの傾向と現在の統計情報を示すレポート。 目標は、デバイスの露出の呼吸と範囲を理解する目的です。
keywords: Microsoft Defender for Endpoint-tvm の脆弱なデバイス、Microsoft Defender for Endpoint、tvm、脅威& 脆弱性の暴露を減らす、脅威と脆弱性を軽減する、セキュリティ構成を監視する
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 355561936642b1fa38228bfa07ad59269c48d817
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245482"
---
# <a name="vulnerable-devices-report---threat-and-vulnerability-management"></a>脆弱なデバイス レポート - 脅威と脆弱性の管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [脅威と脆弱性の管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

レポートには、脆弱なデバイスの傾向と現在の統計を含むグラフと棒グラフが表示されます。 目標は、デバイスの露出の呼吸と範囲を理解する目的です。

[脆弱なデバイスのレポート] Microsoft Defender セキュリティ センターにアクセスして、>**レポートにアクセスします。**

次の 2 つの列があります。

- 傾向 (時間の流れる)。 過去 30 日間、3 か月、6 か月、またはカスタムの日付範囲を表示できます。
- 今日 (現在の情報)

**フィルター**: 脆弱性の重大度レベル、悪用の可用性、脆弱性の年齢、オペレーティング システム プラットフォーム、Windows 10 バージョン、またはデバイス グループでデータをフィルター処理できます。

**ドリルダウン:** さらに詳しい分析情報がある場合は、関連する棒グラフを選択して、[デバイス インベントリ] ページにフィルター処理されたデバイスの一覧を表示します。 そこからリストをエクスポートできます。

## <a name="severity-level-graphs"></a>重大度レベルのグラフ

各デバイスは、そのデバイスで見つかった最も重大な脆弱性に従って 1 回だけカウントされます。

![現在のデバイスの脆弱性の重大度レベルの 1 つのグラフと、時間の流中のレベルを示す 1 つのグラフ。](images/tvm-report-severity.png)

## <a name="exploit-availability-graphs"></a>可用性グラフの活用

各デバイスは、既知の悪用の最高レベルに基づいて 1 回だけカウントされます。

![現在のデバイスの利用可能性のグラフと、時間の流れによる可用性を示すグラフが 1 つ表示されます。](images/tvm-report-exploit-availability.png)

## <a name="vulnerability-age-graphs"></a>脆弱性の年齢グラフ

各デバイスは、最も古い脆弱性公開日の下で 1 回だけカウントされます。 古い脆弱性は悪用される可能性が高くなります。

![現在のデバイスの脆弱性の年齢のグラフと、時間の経時を示す 1 つのグラフ。](images/tvm-report-age.png)

## <a name="vulnerable-devices-by-operating-system-platform-graphs"></a>オペレーティング システム プラットフォームグラフによる脆弱なデバイス

ソフトウェアの脆弱性により公開される各オペレーティング システム上のデバイスの数。

![オペレーティング システム プラットフォーム別の現在の脆弱なデバイスの 1 つのグラフと、OS プラットフォームによる脆弱なデバイスの時間の経時を示す 1 つのグラフ。](images/tvm-report-os.png)

## <a name="vulnerable-devices-by-windows-10-version-graphs"></a>バージョン グラフによるWindows 10デバイス

脆弱なアプリケーションまたは OS Windows 10される各バージョンのデバイスの数。

![現在の脆弱なデバイスのバージョン別の 1 つのグラフWindows 10、1 つのグラフは、Windows 10バージョンで脆弱なデバイスを示します。](images/tvm-report-version.png)

## <a name="related-topics"></a>関連項目

- [脅威と脆弱性の管理概要](next-gen-threat-and-vuln-mgt.md)
- [セキュリティ上の推奨事項](tvm-security-recommendation.md)
