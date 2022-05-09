---
title: バッテリーの分析情報
description: 予測されたバッテリ寿命と上位の電力コンシューマーに関するデータを示すレポート
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 32ab3a984d5ab46aac26989518cd3e570082d688
ms.sourcegitcommit: cebbdd393dcfd93ff43a1ab66ad70115853f83e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739834"
---
# <a name="battery-insights"></a>バッテリーの分析情報
このビューでは、Microsoft Managed Desktop デバイスの電源、バッテリ、アプリの使用状況のメトリックが提供されます。 これらの目的のために、アプリが実行中でフォーカスがある場合、アプリは "使用中" と見なされます。

使用状況データを表示するには、[ **バッテリ** ] タブを選択します。

![バッテリ ウィンドウ: 左上のデバイス モデルあたりのバッテリ寿命を予測し、右上に上位のエネルギー コンシューマー (アプリ別) を表示し、下部に分析情報テーブルを表示します。 右上のドキュメント リンク](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a>予測されたバッテリの寿命

**[予測バッテリ寿命]** 領域では、デバイス モデル別に整理された、デバイスに対して予想されるバッテリ寿命の予測を提供します。

> [!NOTE]
> このデータは、データを報告するMicrosoft Managed Desktop展開内のデバイスのランダム<em>な選択</em>から、サンプリングエネルギー使用量、使用時間、バッテリ容量から派生します。

この表では、予測されたバッテリの寿命 (時間単位)、他のMicrosoft Managed Desktopデプロイの同じモデルの平均バッテリ寿命、および環境内でこのデータを報告するデバイスの数を示します。 列見出しを選択してデータを並べ替えます。



## <a name="top-energy-consumers"></a>エネルギー消費の上位

**[トップ エネルギー コンシューマー**] 領域には、環境内で、milliWatt-hours (mWh) で最も多くのエネルギーを消費するアプリが表示されます。 表示されるアプリは特定のデバイスごとに表示されます。このアプリは、左側の [ **予測バッテリ寿命** ] セクションで選択します。 たとえば、Microsoft Surface Book 2 デバイスのアプリごとの消費量を確認するには、バッテリ寿命領域でその行を選択します。 モデルを選択しない場合、表示されるアプリの消費量データは、まとめてデータを持つすべてのアプリに対するものです。

 各アプリについて、色分けされたセグメントには、次のカテゴリのアプリのエネルギー使用量の分布が表示されます。

- CPU
- ディスプレイ
- ネットワーク
- その他

"その他" には、ディスク アクティビティ、モバイル ブロードバンドの使用、内部抵抗に失われたエネルギーなど、さまざまなソースによるエネルギー消費量が含まれる場合があります。 

このビューをフィルター処理して、右上のメニューを使用してフォアグラウンド アプリ、バックグラウンド アプリ、またはその両方のみを表示できます。 フォアグラウンド アプリとは、マウスで何かを選択するなど、過去 28 日間にユーザーが操作したアプリです。

## <a name="insights"></a>分析情報

**インサイト** 領域には、CPU とネットワークのカテゴリの上位 3 つのエネルギー コンシューマーが表示されます。 これらの項目は、すべてのMicrosoft Managed Desktopデプロイと比較して、平均エネルギーよりも高く消費されています。 表示リソースは、デバイスの使用時間と画面の明るさの設定に大きく依存するため、表示リソースは表示されません。 

詳細については、[ **詳細** ] 列の一覧を選択します。

## <a name="battery-optimization"></a>バッテリの最適化

Windows 10には、電源使用量を向上させ、Microsoft Managed Desktop デバイスのバッテリ寿命を長くするためのさまざまなデバイス[設定](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)が用意されています。 これらの設定の一部は、他のWindows機能を低下させる可能性があるため、組織内のデバイスの役割などの他の要因も考慮する必要があります。 Windowsサポートでは、これらの[バッテリ節約のヒント](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)の一覧が保持されます。

ユーザーは、管理者の昇格やサポートを必要とせずに、一部の設定を自分で調整できます。 その他の設定では、組織の IT 管理者によるサポートが必要です。
