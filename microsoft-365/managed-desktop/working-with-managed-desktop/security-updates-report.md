---
title: Windows セキュリティ更新プログラム レポート
description: このレポートに表示される情報について説明します。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 498330ffdf791a0688b9d6bfad432ba5ebea3b2a
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2022
ms.locfileid: "61935815"
---
# <a name="windows-security-updates-report"></a>Windows セキュリティ更新プログラム レポート

このレポートでは、Microsoft Managed Desktop デバイスの特定のセキュリティ更新プログラムWindows展開の進捗状況の概要を示します。 各セキュリティ更新プログラムのリリース サイクルの開始時に、Microsoft Managed Desktop は登録済みのすべてのデバイスのスナップショットを取得します。 展開ターゲットは、その母集団からアクティブ デバイス **の** 95% に設定されます。 グラフは、選択したリリース日の展開の進行状況を Microsoft Managed Desktop の平均と比較して示しています。 アクティブな母集団に焦点を当てながら、このレポートをピボットして、Active **+ Synced** および Out of **synced** デバイスの母集団を表示することもできます。 使用可能なフィルターを変更することで、以前のリリースの展開の進行状況を表示できますが、デバイス レベルの詳細は現在のリリースでのみ使用できます。 グラフに続く表に表示可能なデバイス情報は、オフライン分析にもエクスポートできます。

:::image type="content" source="../../media/mmd-security-updates.png" alt-text="左上に時間の経過とともに更新プログラムのインストールの進行状況を示すレポート、レポートを生成するボタンを含む右上のフィルター、および下部に沿ったレポートの詳細の表":::

通常、Microsoft は毎月第 2 火曜日にセキュリティ更新プログラムをリリースしますが、必要な場合は他の時間にリリースできます。 各リリースでは、既知のセキュリティの脆弱性に関する重要な更新プログラムが追加されます。 Microsoft Managed Desktop では、アクティブなデバイスの 95% が毎月利用可能な最新のセキュリティ更新プログラムで更新されます。 新しい脅威に緊急に対処するためにセキュリティ更新プログラムが他の時点でリリースされると、Microsoft Managed Desktop は同様にこれらの更新プログラムを展開します。 次の用語を使用して、セキュリティ更新プログラムのバージョンの状態を分類します。 

- **Current**: 現在の月にリリースされた更新プログラムを実行しているデバイス 
- **前**: 前の月にリリースされた更新プログラムを実行しているデバイス 
- **古** い : 前月より前にリリースされたセキュリティ更新プログラムを実行しているデバイス 

[古い] カテゴリには、少数のデバイスのみを **含む必要** があります。 大規模または増加している **古** い人口は、Microsoft Managed Desktop に報告して調査を行う必要があるシステム上の問題を示している可能性があります。 
