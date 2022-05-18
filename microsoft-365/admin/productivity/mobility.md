---
title: Microsoft Productivity Score and mobility insights
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
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
monikerRange: o365-worldwide
search.appverid:
- MET150
- MOE150
description: モビリティの詳細 - ユーザーは生産性スコアを経験します。
ms.openlocfilehash: 737083a8f874f3c50d44af607cf624166157e4dc
ms.sourcegitcommit: da6b3cb3b2ccfcdcd5091efce8290b6c486547db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/18/2022
ms.locfileid: "65465956"
---
# <a name="mobility-insights-score--people-experiences"></a>モビリティ分析情報スコア – ユーザー エクスペリエンス

生産性スコアは、Microsoft 365とそれをサポートするテクノロジ エクスペリエンスを使用することで、組織のデジタル変革の過程に関する分析情報を提供します。 組織のスコアは、ユーザーとテクノロジエクスペリエンスの測定値を反映し、自分に似た組織のベンチマークと比較できます。 モビリティ カテゴリは、ユーザーエクスペリエンスメジャーの一部です。 詳細については、 [生産性スコアの概要](productivity-score.md) を確認し、 [Microsoft のプライバシーに関する声明](https://privacy.microsoft.com/privacystatement)を参照してください。

## <a name="prerequisites"></a>前提条件

Mobility insights の使用を開始するには、組織内のユーザーに次のライセンスを付与する必要があります。

- Microsoft Teams
- Exchange Online
- Word
- Excel
- PowerPoint
- OneNote

詳細については、「[ユーザーにライセンスを割り当てる](../manage/assign-licenses-to-users.md)」 を参照してください。

過去 28 日間に少なくとも 1 回、上記の製品でユーザーがアクティブになった後、分析情報が表示されます。

## <a name="why-your-organization39s-mobility-score-matters"></a>組織&#39;モビリティ スコアが重要な理由

組織の生産性の基本となる柱は、どこからでも人々が柔軟に作業できるかどうかです。 Microsoft 365 では、ユーザーは Outlook、Microsoft Teams、Yammer でつながりを維持することができます。 また、Word、Excel、PowerPoint、OneNote を使用して、どこからでも、あらゆるプラットフォームでコンテンツの共同作業をシームレスにおこなうこともできます。

## <a name="how-we-calculate-the-score"></a>スコアの計算方法

このカテゴリの主要なメトリックを含むエクスペリエンスの主要な分析情報を提供します。 次に、以下に詳しく説明するスコアリング フレームワークを使用して、組織のスコアを計算します。

### <a name="primary-insight"></a>主な分析情報

Microsoft 365 を利用することで、Microsoft Outlook、Word、Excel、PowerPoint、OneNote、Microsoft Teams、Yammer、Skype for Business などのアプリ間で柔軟に作業することができます。 また、デスクトップ、Web、モバイル プラットフォーム全体でシームレスなエクスペリエンスを使用して、どこからでも作業することもできます。 主要な分析情報は、組織内のユーザーに対して有効になっている製品と、少なくとも 2 つのプラットフォームでアクティブになっているこれらのユーザーの数を確認します。

:::image type="content" source="../../media/primary-mobility.png" alt-text="モビリティの主要な分析情報を示すグラフ - ユーザーは生産性スコアを体験します。":::

1. **ヘッダー：** 組織内の任意のMicrosoft 365 Appsにアクセスできるユーザーと、複数のプラットフォームでこれらのアプリケーションの少なくとも 1 つでアクティブになっているユーザーの割合を示します。
2. **体：** 複数のプラットフォームでこれらのアプリケーションを使用すると効率と満足度が向上する方法について詳しく説明します。
3. **視覚化 (現在の状態):** デスクトップ、モバイル、および Web で少なくとも 1 つのMicrosoft 365 (以下の一覧) で複数のプラットフォームを使用するユーザーの数を次に示します。
    - 青 (色付き) 部分がヘッダーで表される割合を表す **水平バー**。
    - バーの **分数は**、ヘッダー内のパーセンテージの計算に使用される (分子/分母) を強調表示します。
        - Numerator: 過去 28 日間に、Microsoft Outlook、Word、Excel、PowerPoint、OneNote、Microsoft Teams、Yammer、Skype内の任意のアプリケーションを使用している組織内のユーザーの数。
        - 分母: 過去 28 日間のうち少なくとも 1 日間、Microsoft 365 Apps、Exchange、Yammer、Microsoft Teams、またはSkypeのライセンスを受けたユーザーの数。
    - キー メトリックの **ピア ベンチマーク** 値もパーセンテージで表示されます。
4. **モビリティ リソースを表示する:** ヘルプ コンテンツを表示するには、このリンクを選択します。

#### <a name="trend-visualization-of-the-primary-insight"></a>主要な分析情報の傾向の視覚化

:::image type="content" source="../../media/mobility-primary.png" alt-text="複数のプラットフォームを使用するユーザーの数と時間を示すグラフ。":::

このグラフは、過去 180 日間にアプリを使用したユーザーの数を分子とする傾向線を示しています。 折れ線グラフの各データ ポイントは、過去 28 日間のアクティビティの集計です。 各データ ポイントは、x 軸上の各日付について、過去 28 日間に少なくとも 2 つのプラットフォームにわたってアプリケーションを使用して組織内のすべてのユーザーの数を提供します。

### <a name="scoring-framework"></a>スコアリング フレームワーク

組織のモビリティ スコアは、ユーザーがOutlook、Teams、Word、Excel、PowerPoint、OneNote、Yammer、Skypeなど、Microsoft 365 Appsを使用しているかどうかを組織 (集計) レベルで測定します。 - デスクトップ、Web、モバイルなど、さまざまなプラットフォームで使用できます。

スコアは、個々のユーザー レベルでは提供されません。

## <a name="explore-how-your-org-works-across-platforms-and-locations"></a>プラットフォームと場所をまたいで組織がどのように機能するかを調べる

また、組織内のユーザーがプラットフォーム間でどのように機能するかを把握するのに役立つ情報も提供されます。 これらの追加メトリックは、生産性スコアに直接影響を与えるのではなく、デジタル変革の一環としてアクション プランを作成するのに役立ちます。  

### <a name="use-of-outlook-across-platforms"></a>プラットフォーム間でのOutlookの使用

:::image type="content" source="../../media/outlook-across-platforms.png" alt-text="複数のプラットフォームでOutlookを使用しているユーザーの数を示すグラフ。":::

1. **ヘッダー：** 複数のプラットフォームでOutlookを使用しているOutlookでアクティブなユーザーの割合を示します。
2. **体：** モバイル デバイスでOutlookを使用して、電子メール上のどこからでも接続を維持する価値に関する情報を提供します。
3. **可視 化：** Outlookでアクティブで、1 つ以上のプラットフォームを使用しているユーザーの割合を示します。
      - **複数のプラットフォーム:**
        - Numerator: 過去 28 日間にデスクトップ、モバイル、または Web から少なくとも 2 つのプラットフォームでOutlookを使用したユーザーの数。
        - 分母: 過去 28 日間に少なくとも 1 回Outlook使用したユーザーの数。
      - **デスクトップのみ:**
        - Numerator: 過去 28 日間にデスクトップ プラットフォームでのみOutlookを使用したユーザーの数。
        - 分母: 過去 28 日間に少なくとも 1 回Outlook使用したユーザーの数
      - **Web のみ:**
        - Numerator: 過去 28 日間に Web プラットフォームでのみOutlookを使用したユーザーの数。
        - 分母: 過去 28 日間に少なくとも 1 回Outlook使用したユーザーの数。
      - **モバイルのみ:**
        - Numerator: 過去 28 日間にモバイル プラットフォームでのみOutlookを使用したユーザーの数。
        - *分母: 過去 28 日間に少なくとも 1 回Outlookを使用したユーザーの数。

### <a name="use-of-teams-across-platforms"></a>プラットフォーム間でのTeamsの使用

:::image type="content" source="../../media/teams-across-platforms.png" alt-text="複数のプラットフォームまたは 1 つのプラットフォームでTeamsを使用しているユーザーの数を示すグラフ。":::

1. **ヘッダー：** Microsoft Teamsでアクティブなユーザーの割合が複数のプラットフォームで使用されているかを示します。
2. **体：** モバイル デバイスでTeamsを使用して、ユーザーが任意の場所から作業しているときにメッセージを最新の状態に保つのに役立つ価値に関する情報を提供します。
3. **可視 化：** 1 つのプラットフォームまたは複数のプラットフォームで使用しているMicrosoft Teamsでアクティブなユーザーの割合を示します。 
    - **複数のプラットフォーム:**
        - Numerator: デスクトップ、モバイル、または Web の 2 つ以上のプラットフォームで、過去 28 日間にTeamsを使用したユーザーの数。
        - 分母: 過去 28 日間に少なくとも 1 回Microsoft Teams使用したユーザーの数。
    - **デスクトップのみ:**
        - Numerator: 過去 28 日間にデスクトップ プラットフォームでのみMicrosoft Teamsを使用したユーザーの数
        - 分母: 過去 28 日間に少なくとも 1 回Teams使用したユーザーの数
    - **Web のみ:**
        - Numerator: 過去 28 日間に Web プラットフォームでのみMicrosoft Teamsを使用したユーザーの数
        - 分母: 過去 28 日間に少なくとも 1 回Microsoft Teams使用したユーザーの数
    - **モバイルのみ:**
        - Numerator: 過去 28 日間にモバイル プラットフォームでのみMicrosoft Teamsを使用したユーザーの数
        - 分母: 過去 28 日間に少なくとも 1 回Teams使用したユーザーの数

### <a name="use-of-microsoft-365-apps-across-platforms"></a>プラットフォーム間でのMicrosoft 365 Appsの使用

:::image type="content" source="../../media/microsoft365apps-platforms.png" alt-text="複数または 1 つのプラットフォームでMicrosoft 365 アプリを使用しているユーザーの数を示すグラフ。":::

1. **ヘッダー：** 複数のプラットフォームでMicrosoft 365 Apps (Word、Excel、PowerPoint、OneNote) でアクティブなユーザーの割合を示します。
2. **体：** 組織内のユーザーにどこからでもファイルにアクセスできる柔軟性を提供することの価値に関する情報を提供します。
3. **可視 化：** グループ化された垂直は、Word、Excel、PowerPoint、OneNoteの各アプリを 1 つまたは複数のプラットフォームで使用しているユーザーの数を表します。 これらのアプリケーションごとに、バーは次を表します。
      - **複数のプラットフォーム:** 過去 28 日間に少なくとも 2 つのプラットフォームでアプリでアクティブなユーザーの数。
      - **デスクトップのみ:** 過去 28 日間にデスクトップ プラットフォームのみでアプリでアクティブなユーザーの数。
      - **Web のみ:** 過去 28 日間に Web プラットフォームのみでアプリでアクティブなユーザーの数。
      - **モバイルのみ:** 過去 28 日間にモバイル プラットフォームでのみアプリでアクティブなユーザーの数。

### <a name="remote-work"></a>リモート作業

:::image type="content" source="../../media/remotework-trend.png" alt-text="リモート、オンサイト、またはその両方で作業しているユーザーの数を示すグラフ。":::

1. **ヘッダー：** 自宅または会社のネットワーク外の場所からのみ働いているユーザーの割合を示します。
2. **体：** 組織の物理的なオフィスにアクセスできないユーザーのリモート作業を容易にすることの重要性を強調します。
3. **可視 化：** リモートでのみ働くユーザーの 1 日の割合と、オンサイトで働くユーザーの 1 日の割合を示す傾向線を示します。 ユーザーは、1 日に 3 時間以上のアクティビティを Microsoft 365 Apps でおこなった場合に職場にいると見なされます。

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365 アプリの正常性 – テクノロジ エクスペリエンス](apps-health.md) (記事)\
[コミュニケーション – People エクスペリエンス](communication.md) (記事)\
[コンテンツ コラボレーション – People エクスペリエンス](content-collaboration.md) (記事)\
[会議 – People エクスペリエンス](meetings.md) (記事)\
[生産性スコアのプライバシー 制御](privacy.md) (記事)\
[チームワーク – People エクスペリエンス](teamwork.md) (記事)