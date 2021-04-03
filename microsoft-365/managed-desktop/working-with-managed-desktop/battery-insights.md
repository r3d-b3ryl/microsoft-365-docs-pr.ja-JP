---
title: バッテリーの分析情報
description: 予測バッテリ寿命とトップパワーコンシューマに関するデータを示すレポート
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
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579712"
---
# <a name="battery-insights"></a>バッテリーの分析情報
このビューは、Microsoft Managed Desktop デバイスの電源、バッテリー、アプリの使用状況の指標を提供します。 これらの目的のために、アプリが実行中でフォーカスがある場合、アプリは "使用中" と見なされます。

使用状況データを表示するには、[バッテリー] タブ **を選択** します。

![バッテリー ウィンドウ: 左上のデバイス モデルごとの予測バッテリ寿命、右上の上位エネルギーコンシューマ (アプリ別)、下部の分析情報テーブル。 右上のドキュメント リンク](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a>予測バッテリ寿命

[予測 **バッテリ寿命] 領域** では、デバイス モデル別に整理された、デバイスの予想されるバッテリ寿命の予測を提供します。

> [!NOTE]
> このデータは、データも報告している Microsoft Managed Desktop 展開内の<em></em>デバイスのランダムな選択から、サンプリング エネルギー使用量、使用時間、およびバッテリー容量から派生します。

次の表は、予測されるバッテリ寿命 (時間)、他の Microsoft Managed Desktop 展開の同じモデルの平均バッテリ寿命、および環境内のこのデータを報告するデバイスの数を示しています。 列見出しを選択してデータを並べ替える。



## <a name="top-energy-consumers"></a>トップエネルギーコンシューマ

[トップ **エネルギーコンシューマ** ] 領域には、milliWatt-hours (mWh) で最もエネルギーを消費する環境内のアプリが表示されます。 表示されるアプリは、特定のデバイスごとに表示され、左側の [予測バッテリ寿命] **セクションで** 選択します。 たとえば、Microsoft Surface Book 2 デバイスのアプリごとの消費量を確認するには、バッテリー寿命領域でその行を選択します。 モデルを選択しない場合、表示されるアプリ消費データは、まとめてデータを持つすべてのアプリに対して表示されます。

 各アプリについて、色付きセグメントには、次のカテゴリ間でのアプリのエネルギー使用の分布が表示されます。

- CPU
- ディスプレイ
- ネットワーク
- その他

"その他" には、ディスクアクティビティ、モバイル ブロードバンドの使用、内部抵抗に失われたエネルギーなど、さまざまなソースによるエネルギー消費量が含まれる場合があります。 

このビューをフィルター処理して、右上のメニューを使用してフォアグラウンド アプリ、バックグラウンド アプリ、または両方のみを表示できます。 フォアグラウンド アプリは、マウスで何かを選択するなど、過去 28 日間にユーザー操作を行ったアプリです。

## <a name="insights"></a>分析情報

[ **インサイト] 領域には** 、CPU およびネットワーク カテゴリの上位 3 つのエネルギー コンシューマが表示されます。 これらのアイテムは、すべての Microsoft Managed Desktop 展開に比べて平均的なエネルギーよりも高く消費されています。 表示リソースは、デバイスの使用時間と画面の明るさの設定に大きく依存します。 

詳細については、[詳細] 列 **の** リストを選択します。

## <a name="battery-optimization"></a>バッテリーの最適化

Windows 10 には [、電力使用量](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) を改善し、Microsoft Managed Desktop デバイスのバッテリ寿命を上げするための多数のデバイス設定が用意されています。 これらの設定の中には、他の Windows 機能が低下する場合があります。そのため、組織内のデバイスの役割など、他の要因も考慮する必要があります。 Windows サポートは、これらのバッテリー節約のヒント [の一覧を維持します](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)。

ユーザーは、管理者の昇格やサポートを必要とせずに、一部の設定を自分で調整できます。 その他の設定では、組織の IT 管理者からのサポートが必要です。
