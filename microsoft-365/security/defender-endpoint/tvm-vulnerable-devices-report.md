---
title: 脆弱なデバイス レポート - 脅威と脆弱性の管理
description: 脆弱なデバイスの傾向と現在の統計情報を示すレポート。 目標は、デバイスの露出の呼吸と範囲を理解する目的です。
keywords: Microsoft Defender for Endpoint-tvm の脆弱なデバイス、Microsoft Defender for Endpoint、tvm、脅威& 脆弱性の暴露を減らす、脅威と脆弱性を軽減する、セキュリティ構成を監視する
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
ms.openlocfilehash: fa5280d9c6f396e8e164397210c1b58dfcfc8d9b
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64466721"
---
# <a name="vulnerable-devices-report---threat-and-vulnerability-management"></a>脆弱なデバイス レポート - 脅威と脆弱性の管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [脅威と脆弱性の管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)

レポートには、脆弱なデバイスの傾向と現在の統計を含むグラフと棒グラフが表示されます。 目標は、デバイスの露出の呼吸と範囲を理解する目的です。

[脆弱なデバイスのレポート] Microsoft 365 Defenderにアクセスして、>**ポータルにアクセスします。**

次の 2 つの列があります。

- 傾向 (時間の流れる)。 過去 30 日間、3 か月、6 か月、またはカスタムの日付範囲を表示できます。
- 状態 (現在の情報)

**フィルター**: 脆弱性の重大度レベル、悪用の可用性、脆弱性の年齢、オペレーティング システム プラットフォーム、Windows 10 または Windows 11 バージョン、またはデバイス グループでデータをフィルター処理できます。

**ドリルダウン:** さらに詳しい分析情報がある場合は、関連する棒グラフを選択して、[デバイス インベントリ] ページにフィルター処理されたデバイスの一覧を表示します。 そこからリストをエクスポートできます。

## <a name="severity-level-graphs"></a>重大度レベルのグラフ

各デバイスは、そのデバイスで見つかった最も重大な脆弱性に従って 1 回だけカウントされます。

:::image type="content" source="images/tvm-report-severity.png" alt-text=" 現在のデバイスの脆弱性の重大度レベル、および時間の経時におけるレベルを示すグラフ。" lightbox="images/tvm-report-severity.png":::

## <a name="exploit-availability-graphs"></a>可用性グラフの活用

各デバイスは、既知の悪用の最高レベルに基づいて 1 回だけカウントされます。

:::image type="content" source="images/tvm-report-exploit-availability.png" alt-text="現在のデバイスの悪用の可用性と時間の流れによる可用性を示すグラフ" lightbox="images/tvm-report-exploit-availability.png":::

## <a name="vulnerability-age-graphs"></a>脆弱性の年齢グラフ

各デバイスは、最も古い脆弱性公開日の下で 1 回だけカウントされます。 古い脆弱性は、悪用される可能性が高くなります。

:::image type="content" source="images/tvm-report-age.png" alt-text="現在のデバイスの脆弱性の年齢と時間の経時を示すグラフ" lightbox="images/tvm-report-age.png":::

## <a name="vulnerable-devices-by-operating-system-platform-graphs"></a>オペレーティング システム プラットフォームグラフによる脆弱なデバイス

ソフトウェアの脆弱性により公開される各オペレーティング システム上のデバイスの数。

:::image type="content" source="images/tvm-report-os.png" alt-text="オペレーティング システム プラットフォーム別の現在の脆弱なデバイスと、OS プラットフォームによる脆弱なデバイスを時間の流れで示すグラフ" lightbox="images/tvm-report-os.png":::

## <a name="vulnerable-devices-by-windows-version-graphs"></a>バージョン グラフによるWindowsデバイス

脆弱なアプリケーションまたは OS によってWindows 10または Windows 11 バージョン上のデバイスの数。

:::image type="content" source="images/tvm-report-version.png" alt-text="バージョン別の現在の脆弱なデバイスと、Windows 10バージョンによる脆弱なWindows 10を示すグラフ" lightbox="images/tvm-report-version.png":::

## <a name="related-topics"></a>関連項目

- [脅威と脆弱性の管理概要](next-gen-threat-and-vuln-mgt.md)
- [セキュリティ上の推奨事項](tvm-security-recommendation.md)
