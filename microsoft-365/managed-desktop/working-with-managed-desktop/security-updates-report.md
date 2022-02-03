---
title: Windows セキュリティ更新プログラム レポート
description: このレポートに表示される情報について説明します。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: d20a10fa1fb645763f6eec20f52b4c9e4fe294a1
ms.sourcegitcommit: bae72428d229827cba4c807d9cd362417afbcccb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/02/2022
ms.locfileid: "62322423"
---
# <a name="windows-security-updates-report"></a>Windows セキュリティ更新プログラム レポート

このレポートでは、Microsoft Managed Desktop デバイスの特定のセキュリティ更新プログラムWindows展開の進捗状況の概要を示します。

各セキュリティ更新プログラムのリリース サイクルの開始時に、Microsoft Managed Desktop は登録済みのすべてのデバイスのスナップショットを取得します。 展開ターゲットは、その母集団からアクティブ デバイス **の** 95% に設定されます。 グラフは、選択したリリース日の展開の進行状況を Microsoft Managed Desktop の平均と比較して示しています。

アクティブな母集団に重点を置く一方で、このレポートをピボットして、Active **+ Synced および Out of synced** デバイスの母集団を表示することもできます。 使用可能なフィルターを変更することで、以前のリリースの展開の進行状況を表示できますが、デバイス レベルの詳細は現在のリリースでのみ使用できます。 グラフに続く表のデバイス情報もオフライン分析用にエクスポートできます。

:::image type="content" source="../../media/mmd-security-updates.png" alt-text="左上に時間の経過とともに更新プログラムのインストールの進行状況を示すレポート、レポートを生成するボタンを含む右上のフィルター、および下部に沿ったレポートの詳細の表":::

通常、Microsoft は毎月第 2 火曜日にセキュリティ更新プログラムをリリースします。 ただし、必要に応じて他の時点でリリースできます。 各リリースでは、既知のセキュリティの脆弱性に関する重要な更新プログラムが追加されます。

Microsoft Managed Desktop は、アクティブなデバイスの 95% が毎月利用可能な最新のセキュリティ更新プログラムで更新されます。 セキュリティ更新プログラムがリリースされると、新しい脅威に緊急に対処するために、Microsoft Managed Desktop は同様にこれらの更新プログラムを展開します。

## <a name="status-categories"></a>状態カテゴリ

セキュリティ更新プログラムのバージョンの状態は、次の用語を使用して分類されます。

| セキュリティ更新プログラムの状態 | 説明 |
| ------ | ------ |
| Current | 現在の月にリリースされた更新プログラムを実行しているデバイス。 |
| Previous | 前月にリリースされた更新プログラムを実行しているデバイス。 |
| 古い | 前月より前にリリースされたセキュリティ更新プログラムを実行しているデバイス。 |

> [!NOTE]
> [古い] カテゴリには、少数のデバイスのみを **含む必要** があります。 大規模または増加している **古** い人口は、調査のために Microsoft Managed Desktop に報告する必要があるシステム上の問題を示している可能性があります。
