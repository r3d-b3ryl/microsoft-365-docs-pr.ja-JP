---
title: 脆弱なデバイス レポート - 脅威と脆弱性の管理
description: 脆弱なデバイスの傾向と現在の統計を示すレポート。 目標は、デバイスの露出の息と範囲を理解することです。
keywords: Microsoft Defender for Endpoint tvm の脆弱なデバイス、Microsoft Defender for Endpoint、tvm、脅威&脆弱性の露出を減らす、脅威と脆弱性を減らす、セキュリティ構成を監視する
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

このレポートには、脆弱なデバイスの傾向と現在の統計情報を含むグラフと横棒グラフが表示されます。 目標は、デバイスの露出の息と範囲を理解することです。

脆弱なデバイス>レポートに移動して、Microsoft 365 Defender ポータル **でレポート** にアクセスする

次の 2 つの列があります。

- 傾向 (時間の経過と共)。 過去 30 日間、3 か月、6 か月、またはカスタム日付範囲を表示できます。
- 状態 (現在の情報)

**フィルター**: 脆弱性の重大度レベル、悪用の可用性、脆弱性の年齢、オペレーティング システム プラットフォーム、Windows 10またはWindows 11バージョン、またはデバイス グループでデータをフィルター処理できます。

**ドリルダウン**: さらに詳しく調べる分析情報がある場合は、関連する横棒グラフを選択して、デバイス インベントリ ページでフィルター処理されたデバイスの一覧を表示します。 そこから、リストをエクスポートできます。

## <a name="severity-level-graphs"></a>重大度レベルのグラフ

各デバイスは、そのデバイスで見つかった最も重大な脆弱性に従って 1 回だけカウントされます。

:::image type="content" source="images/tvm-report-severity.png" alt-text=" 現在のデバイスの脆弱性の重大度レベルと、時間の経過に伴うレベルを示すグラフ。" lightbox="images/tvm-report-severity.png":::

## <a name="exploit-availability-graphs"></a>可用性グラフを利用する

各デバイスは、既知の悪用の最高レベルに基づいて 1 回だけカウントされます。

:::image type="content" source="images/tvm-report-exploit-availability.png" alt-text="現在のデバイスの悪用の可用性と時間の経過に伴う可用性を示すグラフ" lightbox="images/tvm-report-exploit-availability.png":::

## <a name="vulnerability-age-graphs"></a>脆弱性の年齢グラフ

各デバイスは、最も古い脆弱性の公開日の下で 1 回だけカウントされます。 古い脆弱性は、悪用される可能性が高くなります。

:::image type="content" source="images/tvm-report-age.png" alt-text="現在のデバイスの脆弱性の年齢と時間の経過に伴う年齢を示すグラフ" lightbox="images/tvm-report-age.png":::

## <a name="vulnerable-devices-by-operating-system-platform-graphs"></a>オペレーティング システム プラットフォーム グラフによる脆弱なデバイス

ソフトウェアの脆弱性が原因で公開されている各オペレーティング システム上のデバイスの数。

:::image type="content" source="images/tvm-report-os.png" alt-text="オペレーティング システム プラットフォーム別の現在の脆弱なデバイスと、時間の経過に伴う OS プラットフォーム別の脆弱なデバイスを示すグラフ" lightbox="images/tvm-report-os.png":::

## <a name="vulnerable-devices-by-windows-version-graphs"></a>Windows バージョン グラフによる脆弱なデバイス

脆弱なアプリケーションまたは OS が原因で公開されている各Windows 10またはWindows 11 バージョン上のデバイスの数。

:::image type="content" source="images/tvm-report-version.png" alt-text="Windows 10 バージョン別の現在の脆弱なデバイスと、時間の経過と共にWindows 10バージョン別の脆弱なデバイスを示すグラフ" lightbox="images/tvm-report-version.png":::

## <a name="related-topics"></a>関連項目

- [脅威と脆弱性の管理の概要](next-gen-threat-and-vuln-mgt.md)
- [セキュリティに関する推奨事項](tvm-security-recommendation.md)
