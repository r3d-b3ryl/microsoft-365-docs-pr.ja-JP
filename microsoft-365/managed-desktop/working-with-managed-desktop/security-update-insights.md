---
title: Windows セキュリティ更新プログラムの分析情報
description: ''
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b3b1f43217b3be285f20925065bf9710a38f9606
ms.sourcegitcommit: cebbdd393dcfd93ff43a1ab66ad70115853f83e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739835"
---
# <a name="windows-security-update-insights"></a>Windows セキュリティ更新プログラムの分析情報
このビューでは、Microsoft Managed Desktop デバイスのセキュリティ更新プログラムの状態の概要を示します。 

使用状況データを表示するには、[<strong>Windowsセキュリティ更新プログラム</strong>] タブを選択します。

![Windowsセキュリティ更新プログラム ウィンドウ: 左側の列のデバイスの状態と更新バージョンの棒グラフ、中央の列の時間の経過に伴う展開の進行状況、展開グループごとのアクティブなデバイスの割合、および右側の列の 95% の展開ターゲットに到達するまでにかかった日数。](../../media/update-insights.jpg)

## <a name="device-status"></a>デバイスの状態

Windows Updateによってデバイスを更新するには、デバイスをインターネットに接続し、少なくとも 6 時間休止しないようにする必要があります。そのうちの 2 つを連続する必要があります。 これらの要件を満たしていないデバイスが更新される可能性がありますが、それを満たすデバイスは更新される可能性が最も高くなります。 

次の用語を使用して、Windows Updateのコンテキストでデバイス アクティビティを分類します。

- <strong>アクティブ：</strong>最新のセキュリティ更新プログラム リリースの最小アクティビティ条件 (6 時間、連続 2 時間) を満たしており、少なくとも 5 日ごとにMicrosoft Intuneでチェックインしたデバイス
- <strong>同期：</strong>過去 28 日以内にIntuneでチェックインしたデバイス
- <strong>同期が取れなくなっている:</strong>過去 28 日間にIntuneでチェックイン<i>していない</i>デバイス




## <a name="update-version-status"></a>バージョンの状態を更新する

Microsoft は、毎月第 2 火曜日にセキュリティ更新プログラムをリリースします。 各リリースでは、既知のセキュリティの脆弱性に関する重要な更新プログラムが追加されます。 Microsoft Managed Desktopでは、マネージド デバイスの 95% が毎月利用可能な最新のセキュリティ更新プログラムで確実に更新されます。 セキュリティ更新プログラムは、新しい脅威に緊急に対処するために、他の時期にリリースされることがあります。 Microsoft Managed Desktopは、同様の方法でこれらの更新プログラムをデプロイします。

セキュリティ更新プログラムのバージョンの状態は、次の用語で分類されます。

- <strong>現在の：</strong> 現在の月にリリースされた更新プログラムを実行しているデバイス
- <strong>先の：</strong> 前月にリリースされた更新プログラムを実行しているデバイス
- <strong>古い：</strong> 前月より前にリリースされたセキュリティ更新プログラムを実行しているデバイス

<strong>古い</strong>カテゴリのデバイスはほとんど表示されないはずです。人口が大きい、または増加している場合は、調査できるようにMicrosoft Managed Desktopに報告する必要があるシステム上の問題を示している可能性があります。


## <a name="deployment-progress"></a>デプロイの進行状況

各セキュリティ更新プログラムリリース サイクルの開始時に、Microsoft Managed Desktopはデバイスの母集団のスナップショットを取得し、展開ターゲットをその母集団の 95% に設定します。 <strong>デプロイの進行状況</strong>領域には、更新プログラムの展開がリリースごとにこのターゲットをどの程度近く満たしているかを追跡する、毎日更新された過去の傾向が表示されます。 このグラフには、アクティブな状態のデバイスのみが表示されます。

このデータは、右上のドロップダウン メニューを使用して、以前の更新サイクルで表示できます。 このメニューで選択した期間は、ページ全体のすべての情報に適用されます。

<strong>[展開グループ別に更新されたアクティブなデバイス]</strong> 領域には、Microsoft Managed Desktop展開グループごとに更新プログラムのインストールの進行状況が表示され、別のビューが表示されます。

<strong>[ターゲットに到達するまでの日数</strong>] 領域には、現在のセキュリティ更新プログラムで更新されるデバイスの合計数の 95% にかかった時間が表示されます。 デプロイの進行中は、選択した更新プログラムの 95% のターゲットに到達するまで、この領域は <strong>引き続き</strong> 更新中と表示されます。

## <a name="device-details-area"></a>デバイスの詳細領域

ダッシュボードの下部には、 [デバイスの状態](#device-status) や [更新バージョンの状態](#update-version-status)など、デバイスの詳細情報を示すテーブルがあります。 この一覧を検索するか、一覧に表示されている任意の値でフィルター処理できます。


![デバイス名、割り当てられたユーザー、デバイスの状態、更新バージョン、オペレーティング システムのバージョン、およびデバイスが最後に同期された日付の列を示すデバイスの詳細テーブル。](../../media/security-update-insights-device-table-sterile.png)
