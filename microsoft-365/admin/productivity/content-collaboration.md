---
title: Microsoft 生産性スコア - コンテンツコラボレーション
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
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
monikerRange: o365-worldwide
search.appverid:
- MET150
- MOE150
description: コンテンツ コラボレーションの詳細 - ユーザーエクスペリエンスの生産性スコア。
ms.openlocfilehash: 13bee74b901bef4a4d4086e5cbed97a1bdddbabb145acaee5e68af9f5fdac010
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53823293"
---
# <a name="content-collaboration--people-experiences"></a>コンテンツのコラボレーション – ユーザー エクスペリエンス

生産性スコアは、組織のデジタル変換の取り組みについて、Microsoft 365をサポートするテクノロジ エクスペリエンスを通じて分析情報を提供します。 組織のスコアは、ユーザーとテクノロジ エクスペリエンスの測定値を反映し、類似した組織のベンチマークと比較できます。 コンテンツ コラボレーション カテゴリは、ユーザーエクスペリエンスの測定値の一部です。 詳細については、「生産性スコアの概要」 [を参照し](productivity-score.md) 、「Microsoft のプライバシーに関 [する声明」を参照してください](https://privacy.microsoft.com/privacystatement)。

## <a name="prerequisites"></a>前提条件

コンテンツ コラボレーションの分析情報を使い始めるには、組織内のユーザーに次のライセンスを与える必要があります。

- OneDrive for Business
- SharePoint
- Exchange Online

詳細については、「ユーザーにライセンスを [割り当てる」を参照してください](../manage/assign-licenses-to-users.md)。

 過去 28 日間に少なくとも 1 回、上記の製品でユーザーがアクティブにされた後、分析情報が表示されます。

## <a name="why-your-organization39s-content-collaboration-score-matters"></a>組織でコンテンツ&#39;スコアが重要な理由

デジタル変換の重要な側面は、ユーザーがファイルで共同作業を行う方法です。 コンテンツをオンにMicrosoft 365ユーザーは、任意の場所から他のユーザーとコンテンツにアクセス、作成、変更、および共同作業を行います。 調査によると、ユーザーがオンライン ファイルを使用して共同作業を行う場合、各ユーザーは週平均 100 分を節約できます。

## <a name="how-we-calculate-the-content-collaboration-score"></a>コンテンツ コラボレーション スコアの計算方法

組織のコンテンツ コラボレーションの主要な指標を含む主要な分析情報を提供します。 次に、以下に示すスコアリング フレームワークを使用して、組織のスコアを計算します。

> [!NOTE]
> 2021 年 4 月 22 日に、共同作業者の指標の計算方法が変更されました。 これは、主 [な分析情報](#primary-insight)、ファイル [コラボレーションの分析](#number-of-files-collaborated-on)情報、およびコンテンツ コラボレーション スコアの測定方法に影響します。 この変更は、Microsoft や他のサード パーティ製アプリケーションからの非人間エージェント (またはボット) からのデータのノイズを軽減し、より正確でアクション可能なスコアを得るのに役立ちます。

### <a name="primary-insight"></a>主な分析情報

Microsoft OneDriveおよびビジネス 向けSharePointは、ユーザーがデバイスやアプリケーション間で、Microsoft 365で自分の個人および共有コンテンツを簡単に作成、読み取り、検出するのに役立ちます。 また、ユーザーはコンテンツを安全に共有し、共同作業することができます。 主な分析情報には、ユーザーとユーザーを使用できるすべてのOneDrive for BusinessがSharePoint。 さらに、ユーザーの読み取り、作成、および共同作業の数に関する詳細が、OneDrive for BusinessおよびSharePoint。

:::image type="content" source="../../media/collabscore_primary.jpg" alt-text="コミュニケーション コラボレーション スコアからの主な分析情報。":::


この情報で考慮される種類には、Word、Excel、PowerPoint、OneNote PDF ファイルが含まれます。

1. **ヘッダー:** 組織で、コンテンツで共同作業を行っているユーザーまたはOneDriveユーザー SharePoint割合を表示します。
2. **本文:** オンラインでのファイルの読み取りおよび作成の動作が、ファイルの共同作業にリンクされる方法について詳しく説明します。
3. **視覚化 (現在の状態):**
    - 青い色の部分が、過去 28 日間にオンライン ファイルの閲覧者、作成者、または共同作業者である OneDrive またはSharePoint によるファイルの共同作業を有効にしたユーザーの割合を表す水平バー。

        これらは次のように定義されます。</br>
        **閲覧者:** オンライン ファイルにアクセスまたはダウンロードするユーザーは、OneDriveまたはSharePoint。</br>
        **作成者:** ファイルを作成、変更、アップロード、同期、チェックイン、コピー、またはオンラインで移動OneDriveまたはSharePointします。</br>
        **共同作業者:** オンライン ファイルを使用して共同作業を行うユーザーは、OneDriveまたはSharePoint。 他のユーザーが作成または変更した後、28 日間のウィンドウ内でオンライン Office アプリ または PDF を読み取りまたは編集する場合、2 人は共同作業者です。

        > [!NOTE]
        > 視覚エフェクトで考慮されるファイルは、オンラインで Excel、PowerPoint、OneNote、または PDF ファイルであり、オンラインで、OneDrive または SharePoint に保存されます。 

    - 分数の強調表示 (分子/分母) は、各水平バーで表されるパーセンテージを計算するために使用されます。
    
      - **閲覧者:**</br>
          - Numerator: 過去 28 日間にオンライン ファイルにアクセスまたはダウンロードOneDriveまたはSharePointのユーザー数</br>
          - 分母: 過去 28 日間OneDriveまたはSharePointにアクセスしたユーザーの数</br>
      - **作成者:**</br>
        - Numerator: 過去 28 日間に OneDrive または SharePoint でオンライン ファイルを作成、変更、アップロード、同期、チェックイン、コピー、または移動するユーザーの数</br>
        - 分母: 過去 28 日間OneDriveまたはSharePointにアクセスしたユーザーの数。 </br> 
      - **共同作業者:**</br>
        - Numerator: 過去 28 日間にオンライン OneDriveまたはSharePoint共同作業を行ったユーザーの数</br>
        - 分母: 過去 28 日間のうち少なくとも 1 OneDriveまたはSharePointにアクセスしたユーザーの数

    - 各読者、作成者、および共同作業者のピア ベンチマーク値もパーセンテージとして表示されます。 つまり、作成者の数の値は、ユーザーまたはユーザーにアクセスできるユーザー数の割合OneDrive表示SharePoint。
    
1. **リソースへのリンク:** このリンクを選択すると、照合されたビデオ、および他の関連するヘルプ コンテンツが表示されます。


#### <a name="trend-visualization-of-primary-insight"></a>主な分析情報の傾向の視覚化

傾向の視覚化グラフは、過去 180 日間の読者、作成者、および共同作業者の主な分析情報の主要な指標の傾向線を示しています。 グラフ上の各データ ポイントは、過去 28 日間のアクティビティの集計です。 各作成者データ ポイントは、x 軸の日付ごとに過去 28 日以内に作成者としてタグ付けされたすべてのユーザーの数を提供します。

:::image type="content" source="../../media/trendvisualization.jpg" alt-text="コラボレーションの主な分析情報の傾向を示すグラフ。":::

### <a name="scoring-framework"></a>スコアリング フレームワーク

組織のコンテンツ コラボレーション スコアは、ユーザーが Word、Excel、PowerPoint、OneNote、PDF などのオンライン Office ファイル、または OneDrive または SharePoint で一貫して読み取り、作成、または共同作業を行っているかどうかを集計 (組織) レベルで測定します。

スコアは個々のユーザー レベルでは提供されない。

## <a name="explore-how-your-organization-collaborates"></a>組織の共同作業方法を確認する

また、コンテンツに関する組織の共同作業を可視化するのに役立つ情報も提供します。 これらの追加の指標は、生産性スコアに直接貢献するのではなく、デジタル変換の一環としてアクション プランを作成し、ユーザーの働き方を最適化するのに役立ちます。

### <a name="creating-files-in-onedrive-or-sharepoint"></a>ファイルの作成は、OneDriveまたはSharePoint

:::image type="content" source="../../media/sharepointonedrivefiles.jpg" alt-text="ユーザーまたはユーザーにファイルを作成するユーザーの数OneDriveグラフSharePoint":::

1. **ヘッダー:** アプリケーション上でファイルを作成するMicrosoft 365 Officeでアクティブなユーザーの割合を強調表示OneDriveまたはSharePoint。
2. **本文:** コンテンツの作成の値に関する情報を、OneDriveおよびSharePoint。
3. **視覚化:** 視覚化の内訳は、次のように、Microsoft Office アプリを使用してファイルを OneDriveおよびSharePointする範囲を表します。
      - **OneDrive:** バーの青い (色付き) 部分とバーの分数は、Office アプリケーションでコンテンツを作成する際にアクティブなユーザーの割合を次OneDriveします。
        - Numerator: 過去 28 日以内に OneDrive でオンライン Office ファイルを作成、変更、アップロード、同期、チェックイン、コピー、または移動するユーザーの数。</br>
        - 分母: 過去 28 日以内に、OneDriveまたはSharePointファイルにアクセスし、Office ファイルにアクセスできるユーザーの数。
      - **SharePoint:** バーの青い (色付き) 部分とバーの端数は、Office アプリケーションでアクティブで、SharePoint でコンテンツを作成するユーザーの割合を表します。</br>
         - Numerator: 過去 28 日以内に SharePoint でオンライン Office ファイル (Microsoft Word、Excel、PowerPoint、OneNote ファイル) を作成、変更、アップロード、同期、チェックイン、コピー、または移動するユーザーの数。</br>
        - 分母: 過去 28 日以内に OneDrive または SharePoint ファイルにアクセスし、Officeファイルにアクセスしたユーザーの数。

4. **リソースへのリンク:** ヘルプ コンテンツを表示するには、このリンクを選択します。

### <a name="use-of-attachments-in-email"></a>メールでの添付ファイルの使用

**メールでの添付ファイルの使用** クラウド内のコンテンツへのリンクではなく、メールに物理ファイルを添付しているユーザーの数を把握し、時間の流中でこの数の削減を監視します。

:::image type="content" source="../../media/emailattachments.png" alt-text="電子メールの添付ファイルの使用。":::

1. **ヘッダー:** オンライン ファイルに保存されていないメールで添付ファイルを使用するユーザーの割合を強調表示します。
2. **本文:** コラボレーションとセキュリティの観点からオンライン ファイルへのリンクを共有する価値に関する情報を提供します。
3. **視覚化:** 視覚化の内訳は、メールにコンテンツを添付しているユーザーがさまざまなモード (オンライン ファイルに保存されていないファイル、オンライン ファイルへのリンク) を使用している範囲を表すものです。
      - **ファイルの添付:** バーの青い (色付き) 部分とバーの分数 (分子/分母) は、電子メールで添付ファイルを使用しているユーザーの割合を表します。
        - Numerator: 過去 28 日以内にオンライン ファイルに保存されなかった電子メールにファイルを添付するユーザーの数。
        - 分母: 過去 28 日以内に Exchange、OneDrive、SharePoint、または両方にアクセスしたユーザーの数。
      - **オンライン ファイルへのリンク:** バーの青い (色付き) 部分とバーの分数 (分子/分母) は、添付ファイルを使用し、電子メール内のファイルへのリンクを添付するユーザーの割合を表します。
        - Numerator: 過去 28 日以内にオンライン ファイルへのリンクをメールに添付するユーザーの数。
        - 分母: 過去 28 日以内に、Exchange、OneDrive、SharePoint、または両方にアクセスできるユーザーの数。
4. **リソースへのリンク:** ヘルプ コンテンツを表示するには、このリンクを選択します。

### <a name="sharing-of-online-files"></a>オンライン ファイルの共有

:::image type="content" source="../../media/sharingonlinefiles.png" alt-text="オンラインでファイルを共有するユーザーの数を示すグラフ。":::

1. **ヘッダー:** 外部でファイルを共有しているユーザーまたはOneDriveまたはSharePointにアクセスできるユーザーの割合を強調表示します。
2. **本文:** 組織内のファイル共有設定&#39;変更して、組織に最も適したレベルのコラボレーションを有効にする管理者に関する情報を提供します。
3. **視覚化:** ユーザーまたはユーザーにアクセスできるユーザーが、OneDriveまたは外部SharePoint共有する範囲を表します。
      - **外部:** バーの青い (色付き) 部分とバーの分数 (分子/分母) は、OneDrive または SharePoint へのアクセス権を持ち、ファイルを外部で共有しているユーザーの割合を表します。
        -  Numerator: 過去 28 日間に外部でファイルを共有しているユーザーの数
        - 分母: 過去 28 日間のうち少なくとも 1 日間、OneDriveまたはSharePointにアクセスしたユーザーの総数。
      - **内部的にのみ:** バーの青い (色付き) 部分とバーの分数 (分子/分母) は、OneDrive または SharePoint へのアクセス権を持ち、内部でのみファイルを共有しているユーザーの割合を表します。
        - Numerator: 過去 28 日以内にファイルを内部的に共有しているユーザーの数
        - 分母: 過去 28 日間のうち少なくとも 1 日間、OneDriveまたはSharePointにアクセスしたユーザーの総数。
4. **リソースへのリンク:** ヘルプ コンテンツを表示するには、このリンクを選択します。

### <a name="number-of-files-collaborated-on"></a>共同作業を行うファイルの数

:::image type="content" source="../../media/intensityofcollab.png" alt-text="最も共同作業が行ったファイルの数を示すグラフ。":::

1. **ヘッダー:** 4 つ以上のファイルで共同作業を行OneDriveまたはSharePointユーザーの割合を強調表示します。
2. **本文:** ユーザーがオンライン ファイルを活用して共同作業を強化する方法に関する情報を提供します。
3. **視覚化:** 共同作業するファイルの数に基づいて、OneDriveまたはSharePointユーザーの配布を表示します。 これは、次の 4 つのカテゴリ (バーの青い部分と、そのカテゴリに分類される OneDrive または SharePoint にアクセスできるユーザーの割合を表します)。
      - **コラボレーションなし:**
        - Numerator: 過去 28 日間に任意のファイルで共同作業を行ってないユーザーの数。
        - 分母: 過去 28 日間OneDriveまたはSharePointにアクセスできるユーザーの総数。
      - **1 ~ 3 ファイルでの共同作業:**
        - Numerator: 過去 28 日間に 1 ~ 3 つのファイルで共同作業を行っているユーザーの数。
        - 分母: 過去 28 日間のうち少なくとも 1 日間、OneDriveまたはSharePointにアクセスしたユーザーの総数。
      - **4 ~ 10 ファイルでの共同作業:**
        - Numerator: 過去 28 日間に 4 ~ 10 ファイルで共同作業を行っているユーザーの数。
        - 分母: 過去 28 日間のうち少なくとも 1 日間、OneDriveまたはSharePointにアクセスしたユーザーの総数。
      - **11 以上のファイルでの共同作業:**
        - Numerator: 過去 28 日間に 11 つ以上のファイルで共同作業を行っているユーザーの数。
        - 分母: 過去 28 日間のうち少なくとも 1 日間、OneDriveまたはSharePointにアクセスしたユーザーの総数。
        
4. **リソースへのリンク:** ヘルプ コンテンツを表示するには、このリンクを選択します。

### <a name="network-performance-strength-for-onedrive-and-sharepoint"></a>ネットワークパフォーマンスの強OneDriveとSharePoint

:::image type="content" source="../../media/networkperfstrength.png" alt-text="ユーザーとユーザーのネットワークパフォーマンスをOneDriveグラフSharePoint。":::

1. **ヘッダー:** テスト済みのすべてのデバイスで、ネットワーク接続が悪いデバイスの割合を強調表示し、OneDriveおよびSharePoint。 
2. **本文:** ネットワーク接続のパフォーマンスがコラボレーションにとって重要な理由に関する情報を提供します。 
3. **視覚化:** ネットワーク接続パフォーマンスのレベルが異なるデバイスの割合を、次のOneDrive表示SharePoint。
      - **81~ 100 (最適)**: バーの濃い緑色 (色付き) 部分は、パフォーマンスが最も高いデバイスの割合を表します。
      - **61 ~ 80**: バーの緑色 (色付き) 部分は、ネットワーク パフォーマンス スコアが 60 ~ 80 のデバイスの割合を表します。 
      - **41~ 60**: バーのオレンジ色 (色) 部分は、ネットワーク パフォーマンス スコアが 40 ~ 60 のデバイスの割合を表します。 
      - **21 ~ 40**: バーの赤 (色) 部分は、ネットワーク パフォーマンス スコアが 20 ~ 40 のデバイスの割合を表します。 
      - **0 ~ 20**: バーの濃い赤色 (色付き) 部分は、ネットワーク パフォーマンス スコアが 0 ~ 20 の間で最悪のデバイスの割合を表します。 

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365アプリの正常性 – テクノロジ エクスペリエンス](apps-health.md)(記事)\
[コミュニケーション – ユーザー エクスペリエンス](communication.md) (記事)\
[会議 – ユーザー エクスペリエンス](meetings.md) (記事)\
[モビリティ – ユーザー エクスペリエンス](mobility.md) (記事)\
[生産性スコアのプライバシーコントロール](privacy.md) (記事)\
[チームワーク – ユーザー エクスペリエンス](teamwork.md) (記事)
