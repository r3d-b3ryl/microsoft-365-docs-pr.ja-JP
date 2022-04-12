---
title: Microsoft Productivity Score - Microsoft 365 アプリの正常性
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Microsoft 365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
monikerRange: o365-worldwide
search.appverid:
- MET150
- MOE150
description: Microsoft 365 Apps正常性 - テクノロジエクスペリエンスの生産性スコアの詳細。
ms.openlocfilehash: 2e8e44c954d8d1d6bacca766bd528c3897b7686b
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64782151"
---
# <a name="microsoft-365-apps-health--technology-experiences"></a>Microsoft 365 アプリの正常性 – テクノロジ エクスペリエンス

生産性スコアは、Microsoft 365とそれをサポートするテクノロジ エクスペリエンスを使用することで、組織のデジタル変革の過程に関する分析情報を提供します。 組織のスコアは、ユーザーとテクノロジエクスペリエンスの測定値を反映し、自分に似た組織のベンチマークと比較できます。 アプリの正常性カテゴリは、テクノロジ エクスペリエンスに該当する測定値の一部です。 詳細については、 [生産性スコアの概要](productivity-score.md) を確認し、 [Microsoft のプライバシーに関する声明](https://privacy.microsoft.com/privacystatement)を参照してください。

## <a name="why-your-organizations-microsoft-365-apps-health-score-matters"></a>組織のMicrosoft 365 アプリの正常性スコアが重要な理由

組織の生産性は、正常なアプリケーション環境に依存します。 推奨されるチャネルで最新バージョンのMicrosoft 365 アプリを実行しているデバイスの安全性が向上し、組織内のユーザーがMicrosoft 365の機能を最大限に活用するのに役立ちます。

## <a name="how-we-calculate-the-microsoft-365-apps-health-score"></a>Microsoft 365 アプリの正常性スコアを計算する方法

Microsoft 365 アプリの正常性スコアは、各更新チャネルのデバイス数を測定することによって計算されます。 また、デバイスがサポートされているバージョンを実行しているかどうか、および最新リリースの Microsoft 365 アプリも決定します。

このカテゴリの主要なメトリックを含むエクスペリエンスの主要な分析情報を提供します。 次に、次のセクションで詳しく説明するスコアリング フレームワークを使用して、スコアを計算します。

### <a name="primary-insight"></a>主な分析情報

主要な分析情報は、推奨される更新されたチャネルで Microsoft 365 アプリを実行しているデバイスから計算されます。

:::image type="content" source="../../media/appshealth-primary.png" alt-text="Microsoft 365 アプリの主要な視覚エフェクト。":::

これには、デバイスで実行されているアプリチャネル、ビルド、およびバージョンMicrosoft 365含まれます。

1. **ヘッダー：**  推奨される更新チャネルのデバイスの割合を表示する
1. **体：**  推奨される更新チャネルでデバイスを実行すると、デバイスで最新の更新プログラムを取得し、現在のバージョンを実行する方法について詳しく説明します。
1. **視覚化 (現在の状態):**
    - 青色の部分が推奨される更新チャネルを実行しているデバイスの割合を表す水平バー。
    - 水平バーで表される割合の計算に使用する分数の (分子/分母) を強調表示します。
    - 推奨される更新されたチャネルで実行されているデバイスのピア ベンチマーク値もパーセンテージで表示されます。

#### <a name="trend-visualization-of-the-primary-insight"></a>主要な分析情報の傾向の視覚化

次のグラフは、過去 180 日間の推奨される更新チャネル内のデバイスの数を示しています。 折れ線グラフのデータ ポイントは、過去 28 日間のアクティビティの集計です。

:::image type="content" source="../../media/appshealth-primarytrend.png" alt-text="推奨される更新チャネルを実行しているデバイスの傾向を示すグラフ。":::

### <a name="scoring-framework"></a>スコアリング フレームワーク

Microsoft 365 アプリの正常性スコアは、推奨されるチャネルと最新バージョンでデバイスがMicrosoft 365アプリを実行しているかどうかを測定します。

## <a name="explore-your-organization-microsoft-365-app-channels-and-versions"></a>アプリ チャネルとバージョンMicrosoft 365組織を調べる

また、組織で現在実行されているチャネルとバージョンのデバイスをさらに把握するのに役立つサポート情報も提供されます。 これらの追加メトリックは生産性スコアに影響しませんが、推奨チャネルでデバイスがMicrosoft 365アプリを実行するようにすることで、Microsoft 365 アプリの正常性スコアを向上させるためのアクション プランを作成するのに役立ちます。

### <a name="devices-on-current-channel-and-running-supported-versions"></a>現在のチャネル上のデバイスと、サポートされているバージョンを実行しているデバイス

:::image type="content" source="../../media/devices-current-suppported-channel.png" alt-text="現在サポートされているチャネル内のデバイスの数を示すグラフ。":::

1. **ヘッダー：** 現在のチャネルでサポートされているバージョンのMicrosoft 365 Appsを実行しているデバイスの割合を強調表示します
1. **体：** 推奨されるチャネルでMicrosoft 365 アプリを実行しているデバイスの値に関する情報を提供します。
1. **可視 化：** 視覚化の内訳は、次のように、さまざまなチャネルで最新バージョンとサポートされているバージョンのMicrosoft 365 アプリのデバイスの割合を表します。
    - **サポートされているバージョン:** 青いバーは、サポートされているバージョンのMicrosoft 365 アプリで実行されているデバイスの割合を表します。
    - **最新リリース:** ティール カラー バーは、最新リリースのデバイスの割合を表します。
1. **詳細情報：**   ヘルプ コンテンツを表示するには、このリンクを選択します。

### <a name="devices-running-latest-and-supported-versions"></a>最新バージョンとサポートされているバージョンを実行しているデバイス

:::image type="content" source="../../media/device-supported-versions.png" alt-text="最新バージョンとサポートされているバージョンのアプリを実行しているデバイスの数を示すグラフ。":::

1. **ヘッダー：**  サポートされているバージョンを実行しているデバイスと、最新バージョンを実行しているデバイスの割合を強調表示します。
1. **体：**  推奨されるチャネルとサポートされている/最新バージョンでデバイスを実行している値に関する情報を提供します。
1. **可視 化：** 視覚化の内訳は、サポートされているバージョンと最新バージョンのMicrosoft 365 アプリを実行しているデバイスの数を示す範囲を表しています。
    - **サポートされているバージョン:** バーの青 (色付き) 部分とバーの分数 (分子/分母) は、サポートされているバージョンのMicrosoft 365 アプリを実行しているデバイスの割合を表します。
        - Numerator: 過去 28 日以内にサポートされているバージョンの Microsoft 365 アプリ上のデバイスの数
        - 分母: 過去 28 日以内に Microsoft 365 アプリを使用しているデバイスの数
    - **最新バージョン:** バーのティール (色付き) 部分とバーの分数 (分子/分母) は、最近のバージョンのMicrosoft 365 アプリを実行しているデバイスの割合を表します。
        - Numerator: 過去 28 日以内のMicrosoft 365 アプリの最近のバージョンのデバイスの数
        - 分母: 過去 28 日以内に Microsoft 365 アプリを使用しているデバイスの数
1. **詳細情報：**   ヘルプ コンテンツを表示するには、このリンクを選択します。

#### <a name="trend-visualization-of-the-devices"></a>デバイスの傾向の視覚化

このグラフは、過去 180 日間にサポートされているバージョンと最新バージョンのMicrosoft 365 アプリを実行しているデバイスの傾向線を示しています。

:::image type="content" source="../../media/trendline-devices-supportedversions.png" alt-text="時間の経過と共にサポートされている最新バージョンのアプリを実行するデバイスの数を示すグラフ。":::

## <a name="devices-in-your-organization"></a>組織内のデバイス

このセクションでは、Microsoft 365 アプリの正常性 - テクノロジ エクスペリエンスに関するすべてのメトリックに関連情報を提供することで、注目するメトリックを操作するのに役立ちます。

チャネル/バージョン レベルのテーブルには、次の列が表示されます。

- **チャネル**: デバイス上の現在のMicrosoft 365 アプリ チャネル。
- **状態**: Microsoft 365 アプリは、現在のチャネルとバージョンに基づいてデバイスの状態をサポートします。
- **バージョン**: デバイス上の現在のMicrosoft 365 アプリのバージョン。
- **デバイスの数**: デバイスの数。

## <a name="related-content"></a>関連コンテンツ

[コミュニケーション – People エクスペリエンス](communication.md) (記事)\
[コンテンツ コラボレーション – People エクスペリエンス](content-collaboration.md) (記事)\
[会議 – People エクスペリエンス](meetings.md) (記事)\
[モビリティ – ユーザー エクスペリエンス](mobility.md) (記事)\
[生産性スコアのプライバシー 制御](privacy.md) (記事)\
[チームワーク – People エクスペリエンス](teamwork.md) (記事)