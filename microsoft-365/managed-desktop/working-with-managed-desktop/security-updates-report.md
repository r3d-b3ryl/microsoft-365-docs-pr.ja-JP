---
title: Windows セキュリティ更新プログラム レポート
description: このレポートに表示される情報について説明します。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: c809f341c8bcb1b1f028a8a06ed06a1beeb8c00a
ms.sourcegitcommit: 38a07b23d41763275628ab89e2e4e58ae2926997
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2021
ms.locfileid: "58357441"
---
# <a name="windows-security-updates-report"></a>Windows セキュリティ更新プログラム レポート

このレポートでは、特定のデバイスの特定のセキュリティ更新プログラムのWindowsの概要をMicrosoft マネージド デスクトップします。 各セキュリティ更新プログラムのリリース サイクルの開始時に、Microsoft マネージド デスクトップ は Active デバイスの状態を持つすべてのデバイスのスナップショットを取得し、展開ターゲットをその人口の 95% に設定します。 グラフは、選択したリリース日の展開の進行状況を、平均と比較Microsoft マネージド デスクトップします。 アクティブな母集団に焦点を当てながら、このレポートをピボットして、Active **+ Synced** および Out of **synced** デバイスの母集団を表示することもできます。 使用可能なフィルターを変更することで、以前のリリースの展開の進行状況を表示できますが、デバイス レベルの詳細は現在のリリースでのみ使用できます。 グラフに続く表に表示可能なデバイス情報は、オフライン分析にもエクスポートできます。

:::image type="content" source="../../media/mmd-security-updates.png" alt-text="左上に時間の経過とともに更新プログラムのインストールの進行状況を示すレポート、レポートを生成するボタンを含む右上のフィルター、および下部に沿ったレポートの詳細の表":::

通常、Microsoft は毎月第 2 火曜日にセキュリティ更新プログラムをリリースしますが、必要な場合は他の時間にリリースできます。 各リリースでは、既知のセキュリティの脆弱性に関する重要な更新プログラムが追加されます。 Microsoft マネージド デスクトップ、アクティブなデバイスの 95% が毎月利用可能な最新のセキュリティ更新プログラムで更新されます。 新しい脅威に緊急に対処するためにセキュリティ更新プログラムが他の時点でリリースされると、Microsoft マネージド デスクトップ同様に展開されます。 次の用語を使用して、セキュリティ更新プログラムのバージョンの状態を分類します。 

- **Current**: 現在の月にリリースされた更新プログラムを実行しているデバイス 
- **前**: 前の月にリリースされた更新プログラムを実行しているデバイス 
- **古** い : 前月より前にリリースされたセキュリティ更新プログラムを実行しているデバイス 

[古い] カテゴリには、少数のデバイスのみを **含む必要** があります。 大規模または増加している **古** い人口は、おそらく、調査を行う際に報告する必要があるMicrosoft マネージド デスクトップを示しています。 