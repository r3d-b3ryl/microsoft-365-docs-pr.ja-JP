---
title: Microsoft 生産性スコア - Microsoft 365の正常性
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Microsoft 365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
monikerRange: o365-worldwide
search.appverid:
- MET150
- MOE150
description: 正常性の詳細 - Microsoft 365 Apps生産性スコア。
ms.openlocfilehash: def83cb3a468a31ce5d714af4337f786ef660ebd89293ead9c6c92d9ec23c34d
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53823400"
---
# <a name="microsoft-365-apps-health--technology-experiences"></a>Microsoft 365 アプリの正常性 – テクノロジ エクスペリエンス

生産性スコアは、組織のデジタル変換の取り組みについて、Microsoft 365をサポートするテクノロジ エクスペリエンスを通じて分析情報を提供します。 組織のスコアは、ユーザーとテクノロジ エクスペリエンスの測定値を反映し、類似した組織のベンチマークと比較できます。 アプリの正常性カテゴリは、テクノロジ エクスペリエンスに該当する測定値の一部です。 詳細については、「生産性スコアの概要」 [を参照し](productivity-score.md) 、「Microsoft のプライバシーに関 [する声明」を参照してください](https://privacy.microsoft.com/privacystatement)。

## <a name="why-your-organization39s-microsoft-365-apps-health-score-matters"></a>組織がアプリの&#39;スコアMicrosoft 365重要な理由

組織の生産性は、正常なアプリケーション環境に依存します。 推奨チャネルで最新バージョンの Microsoft 365 アプリを実行しているデバイスは、セキュリティが高く、組織内のユーザーが Microsoft 365 の機能を最も多く利用するのに役立ちます。

## <a name="how-we-calculate-the-microsoft-365-apps-health-score"></a>アプリの正常性スコアMicrosoft 365計算する方法

各更新チャネルMicrosoft 365デバイスの数を測定して、アプリの正常性スコアを計算します。 また、デバイスでサポートされているバージョンが実行されているかどうかを確認し、最新のリリースのアプリMicrosoft 365します。

このカテゴリの主要な指標を含むエクスペリエンスの主な分析情報を提供します。 次に、次のセクションで詳しく説明するスコアリング フレームワークを使用して、スコアを計算します。

### <a name="primary-insight"></a>主な分析情報

主な分析情報は、推奨される更新されたチャネルでMicrosoft 365 Appsデバイスから計算されます。

:::image type="content" source="../../media/appshealth-primary.png" alt-text="アプリの主な視覚Microsoft 365視覚化。":::

この場合に考慮される情報にはMicrosoft 365で実行されているアプリ チャネル、ビルド、およびバージョンが含まれます。

1. **ヘッダー:**  推奨される更新チャネルのデバイスの割合を表示する
1. **本文:**  推奨される更新プログラム チャネルでデバイスを実行すると、最新の更新プログラムを取得し、デバイスで現在のバージョンを実行する方法の詳細が示されます。
1. **視覚化 (現在の状態):**
    - 青色の部分が推奨更新チャネルを実行しているデバイスの割合を表す水平バー。
    - 水平バーで表されるパーセンテージを計算するために使用される分数の (分子/分母) を強調表示します。
    - 推奨される更新されたチャネルで実行されているデバイスのピア ベンチマーク値もパーセンテージとして表示されます。

#### <a name="trend-visualization-of-the-primary-insight"></a>主要な分析情報の傾向の視覚化

次のグラフは、過去 180 日間の推奨更新チャネル内のデバイスの数を示しています。 線グラフ上のデータ ポイントは、過去 28 日間のアクティビティの集計です。

:::image type="content" source="../../media/appshealth-primarytrend.png" alt-text="推奨更新プログラム チャネルを実行しているデバイスの傾向を示すグラフ。":::

### <a name="scoring-framework"></a>スコアリング フレームワーク

アプリMicrosoft 365正常性スコアは、デバイスが推奨チャネルと最新バージョンMicrosoft 365アプリで実行されているかどうかを測定します。

## <a name="explore-your-organization-microsoft-365-app-channels-and-versions"></a>組織のアプリ チャネルMicrosoft 365バージョンを確認する

また、組織内で現在実行されているチャネルとバージョンのデバイスに関する追加の可視性を得るために役立つサポート情報も提供しています。 これらの追加の指標は生産性スコアには影響しませんが、デバイスが推奨チャネルで Microsoft 365 アプリを実行することで、Microsoft 365 アプリの正常性スコアを上げするためのアクション プランを作成するのに役立ちます。

### <a name="devices-on-current-channel-and-running-supported-versions"></a>現在のチャネル上のデバイスとサポートされているバージョンの実行

:::image type="content" source="../../media/devices-current-suppported-channel.png" alt-text="現在サポートされているチャネル内のデバイス数を示すグラフ。":::

1. **ヘッダー:** 現在のチャネルでサポートされているバージョンのデバイスを実行しているデバイスの割合を強調表示Microsoft 365 Apps
1. **本文:** 推奨チャネルでアプリを実行しているデバイスMicrosoft 365情報を提供します。
1. **視覚化:** 視覚化の内訳は、次のように、最新バージョンおよびサポートされているバージョンの Microsoft 365 アプリのデバイスの割合を表します。
    - **サポートされているバージョン:** 青いバーは、サポートされているバージョンのアプリで実行されているデバイスのMicrosoft 365します。
    - **最新のリリース:** ティール カラー バーは、最新リリースのデバイスの割合を表します。
1. **詳細については、次の情報を参照してください。**   ヘルプ コンテンツを表示するには、このリンクを選択します。

### <a name="devices-running-latest-and-supported-versions"></a>最新バージョンとサポートされているバージョンを実行しているデバイス

:::image type="content" source="../../media/device-supported-versions.png" alt-text="最新バージョンおよびサポートされているバージョンのアプリを実行しているデバイスの数を示すグラフ。":::

1. **ヘッダー:**  サポートされているバージョンと最新バージョンを実行しているデバイスを実行しているデバイスの割合を強調表示します。
1. **本文:**  推奨チャネルおよびサポートされている/最新バージョンでデバイスを実行している値に関する情報を提供します。
1. **視覚化:** 視覚化の内訳は、サポートされているバージョンと最新バージョンのアプリを実行しているデバイスの数を表示する範囲を表Microsoft 365されています。
    - **サポートされているバージョン:** バーの青い (色付き) 部分とバーの分数 (分子/分母) は、サポートされているバージョンの Microsoft 365 アプリを実行しているデバイスの割合を表します。
        - Numerator: 過去 28 日以内にサポートされているバージョンMicrosoft 365アプリのデバイス数
        - 分母: 過去 28 Microsoft 365アプリを使用するデバイスの数
    - **最新のバージョン:** バーのティール (色付き) 部分とバーの分数 (分子/分母) は、最新バージョンの Microsoft 365 アプリを実行しているデバイスの割合を表します。
        - Numerator: 過去 28 日以内の最新バージョンMicrosoft 365アプリのデバイス数
        - 分母: 過去 28 Microsoft 365アプリを使用するデバイスの数
1. **詳細については、次の情報を参照してください。**   ヘルプ コンテンツを表示するには、このリンクを選択します。

#### <a name="trend-visualization-of-the-devices"></a>デバイスの傾向の視覚化

このグラフは、過去 180 日間にサポートされているバージョンと最新バージョンの Microsoft 365を実行しているデバイスの傾向線を示しています。

:::image type="content" source="../../media/trendline-devices-supportedversions.png" alt-text="サポートされているアプリと最新バージョンのアプリを実行するデバイスの数を昭和に示します。":::

## <a name="devices-in-your-organization"></a>組織内のデバイス

このセクションでは、アプリの正常性 (テクノロジ エクスペリエンス) に関するすべての指標に関連情報を提供することで、注目するMicrosoft 365に基Microsoft 365役立ちます。

次の列は、チャネル/バージョン レベルの表に表示されます。

- **チャネル**: デバイスMicrosoft 365現在のアプリ チャネル。
- **状態:**  Microsoft 365アプリは、現在のチャネルとバージョンに基づいてデバイスの状態をサポートします。
- **バージョン:**  デバイスMicrosoft 365アプリの現在のバージョン。
- **デバイスの数:**  デバイスの数。

## <a name="related-content"></a>関連コンテンツ

[コミュニケーション – ユーザー エクスペリエンス](communication.md) (記事)\
[コンテンツのコラボレーション – ユーザー エクスペリエンス](content-collaboration.md) (記事)\
[会議 – ユーザー エクスペリエンス](meetings.md) (記事)\
[モビリティ – ユーザー エクスペリエンス](mobility.md) (記事)\
[生産性スコアのプライバシーコントロール](privacy.md) (記事)\
[チームワーク – ユーザー エクスペリエンス](teamwork.md) (記事)