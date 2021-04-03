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
ms.openlocfilehash: dedd39a84580f26e80e5586e07fb64c8a6d35573
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580860"
---
# <a name="content-collaboration--people-experiences"></a>コンテンツのコラボレーション – ユーザー エクスペリエンス

生産性スコアは、Microsoft 365 の使用とそれをサポートするテクノロジ エクスペリエンスを通じて、組織のデジタル変換の旅に関する洞察を提供します。 組織のスコアは、ユーザーとテクノロジ エクスペリエンスの測定値を反映し、類似した組織のベンチマークと比較できます。 コンテンツ コラボレーション カテゴリは、ユーザーエクスペリエンスの測定値の一部です。 詳細については、「生産性スコアの概要」 [を参照し](productivity-score.md) 、「Microsoft のプライバシーに関 [する声明」を参照してください](https://privacy.microsoft.com/privacystatement)。

## <a name="prerequisites"></a>前提条件

コンテンツ コラボレーションの分析情報を使い始めるには、組織内のユーザーに次のライセンスを与える必要があります。

- OneDrive for Business
- SharePoint
- Exchange Online

詳細については、「ユーザーにライセンスを [割り当てる」を参照してください](../manage/assign-licenses-to-users.md)。

 過去 28 日間に少なくとも 1 回、上記の製品でユーザーがアクティブにされた後、分析情報が表示されます。

## <a name="why-your-organization39s-content-collaboration-score-matters"></a>組織でコンテンツ&#39;スコアが重要な理由

デジタル変換の重要な側面は、ユーザーがファイルで共同作業を行う方法です。 Microsoft 365 のコンテンツを使用すると、ユーザーは任意の場所から他のユーザーとコンテンツにアクセス、作成、変更、および共同作業を行います。 調査によると、ユーザーがオンライン ファイルを使用して共同作業を行う場合、各ユーザーは週平均 100 分を節約できます。 [証拠を参照してください](https://vc2prod.blob.core.windows.net/vc-resources/TEIStudies/TEI%20of%20Microsoft%20365%20E5%20-%20Oct%202018.pdf)。

## <a name="how-we-calculate-the-content-collaboration-score"></a>コンテンツ コラボレーション スコアの計算方法

組織のコンテンツ コラボレーションの主要な指標を含む主要な分析情報を提供します。 次に、以下に示すスコアリング フレームワークを使用して、組織のスコアを計算します。

### <a name="primary-insight"></a>主な分析情報

Microsoft OneDrive for Business および SharePoint は、ユーザーが Microsoft 365 の個々のコンテンツと共有コンテンツをデバイスやアプリケーション間で簡単に作成、読み取り、検出するのに役立ちます。 また、ユーザーはコンテンツを安全に共有し、共同作業することができます。 主な分析情報には、OneDrive for Business および SharePoint を使用できるすべてのユーザーからの情報が含まれる。 さらに、OneDrive for Business および SharePoint に保存されているコンテンツに対する読み取り、作成、および共同作業の数に関する詳細が細分されます。

:::image type="content" source="../../media/collabscore_primary.jpg" alt-text="コミュニケーション コラボレーション スコアからの主な分析情報。":::


この情報で考慮される種類には、Word、Excel、PowerPoint、OneNote、PDF ファイルが含まれます。

1. **ヘッダー:** OneDrive または SharePoint にアクセスできる組織で、コンテンツで共同作業を行っているユーザーの割合を表示します。
2. **本文:** オンラインでのファイルの読み取りおよび作成の動作が、ファイルの共同作業にリンクされる方法について詳しく説明します。
3. **視覚化 (現在の状態):**
    - 青い色の部分が、過去 28 日間にオンライン ファイルの閲覧者、作成者、または共同作業者であるOneDrive またはSharePoint を通じてファイルの共同作業を有効にしたユーザーの割合を表す水平バー。

        これらは次のように定義されます。</br>
        **閲覧者:** OneDrive または SharePoint でオンライン ファイルにアクセスまたはダウンロードするユーザー。</br>
        **作成者:** OneDrive または SharePoint のオンライン ファイルを作成、変更、アップロード、同期、チェックイン、コピー、または移動するユーザー。</br>
        **共同作業者:** OneDrive または SharePoint を使用してオンライン ファイルと共同作業を行うユーザー。 他のユーザーが 28 日間のウィンドウ内でオンライン Office アプリまたは PDF を作成または変更した後に、そのうちの 1 人がオンライン Office アプリまたは PDF を読み取りまたは編集した場合、2 人は共同作業者です。

        > [!NOTE]
        > 視覚化で考慮されるファイルは、オンラインで OneDrive または SharePoint に保存された Word、Excel、PowerPoint、OneNote、または PDF ファイルです。 

    - 分数の強調表示 (分子/分母) は、各水平バーで表されるパーセンテージを計算するために使用されます。
    
      - **閲覧者:**</br>
          - Numerator: 過去 28 日間に OneDrive または SharePoint でオンライン ファイルにアクセスまたはダウンロードするユーザーの数</br>
          - 分母: 過去 28 日間のうち少なくとも 1 日間、OneDrive または SharePoint にアクセスしたユーザーの数</br>
      - **作成者:**</br>
        - Numerator: 過去 28 日間に OneDrive または SharePoint でオンライン ファイルを作成、変更、アップロード、同期、チェックイン、コピー、または移動するユーザーの数</br>
        - 分母: 過去 28 日間のうち少なくとも 1 日間、OneDrive または SharePoint にアクセスしたユーザーの数。 </br> 
      - **共同作業者:**</br>
        - Numerator: 過去 28 日間に OneDrive または SharePoint のオンライン ファイルで共同作業を行ったユーザーの数</br>
        - 分母: 過去 28 日間のうち少なくとも 1 日間、OneDrive または SharePoint にアクセスできるユーザーの数

    - 各読者、作成者、および共同作業者のピア ベンチマーク値もパーセンテージとして表示されます。 つまり、作成者の数の値は、OneDrive または SharePoint にアクセスできるユーザーの数に対する割合として表示されます。
    
1. **リソースへのリンク:** このリンクを選択すると、照合されたビデオ、および他の関連するヘルプ コンテンツが表示されます。


#### <a name="trend-visualization-of-primary-insight"></a>主な分析情報の傾向の視覚化

傾向の視覚化グラフは、過去 180 日間の読者、作成者、および共同作業者の主な分析情報の主要な指標の傾向線を示しています。 グラフ上の各データ ポイントは、過去 28 日間のアクティビティの集計です。 各作成者データ ポイントは、x 軸の日付ごとに過去 28 日以内に作成者としてタグ付けされたすべてのユーザーの数を提供します。

:::image type="content" source="../../media/trendvisualization.jpg" alt-text="コラボレーションの主な分析情報の傾向を示すグラフ。":::

### <a name="scoring-framework"></a>スコアリング フレームワーク

組織のコンテンツ コラボレーション スコアは、Word、Excel、PowerPoint、OneNote、PDF などのオンライン Office ファイル、OneDrive または SharePoint でユーザーが一貫して読み取り、作成、または共同作業を行っているかどうかを集計 (組織) レベルで測定します。

スコアは個々のユーザー レベルでは提供されない。


## <a name="explore-how-your-organization-collaborates"></a>組織の共同作業方法を確認する

また、コンテンツに関する組織の共同作業を可視化するのに役立つ情報も提供します。 これらの追加の指標は、生産性スコアに直接貢献するのではなく、デジタルトランスフォーメーションの一環としてアクション プランプランを作成し、ユーザーの働き方を最適化するのに役立ちます。

### <a name="creating-files-in-onedrive-or-sharepoint"></a>OneDrive または SharePoint でのファイルの作成

:::image type="content" source="../../media/sharepointonedrivefiles.jpg" alt-text="OneDrive または SharePoint でファイルを作成するユーザーの数を示すグラフ":::

1. **ヘッダー:** OneDrive または SharePoint でファイルを作成する Microsoft 365 Officeアプリケーションでアクティブなユーザーの割合を強調表示します。
2. **本文:** OneDrive および SharePoint でのコンテンツ作成の値に関する情報を提供します。
3. **視覚化:** 視覚化の内訳は、OneDrive と SharePoint でファイルを作成するためにアプリMicrosoft Officeを使用しているユーザーの範囲を表します。次のようにします。
      - **OneDrive:** バーの青い (色付き) 部分とバーの分数は、OneDrive でコンテンツを作成する Office アプリケーションでアクティブなユーザーの割合を次のように表します。
        - Numerator: 過去 28 日以内に OneDrive でオンライン Office ファイルを作成、変更、アップロード、同期、チェックイン、コピー、または移動するユーザーの数。</br>
        - 分母: 過去 28 日以内に OneDrive または SharePoint にアクセスし、Office ファイルにアクセスできるユーザーの数。
      - **SharePoint:** バーの青い (色付き) 部分とバーの端数は、Office アプリケーションでアクティブで SharePoint でコンテンツを作成するユーザーの割合を表します。</br>
         - Numerator: 過去 28 日以内に SharePoint でオンライン Office ファイル (Microsoft Word、Excel、PowerPoint、または OneNote ファイル) を作成、変更、アップロード、同期、チェックイン、コピー、または移動するユーザーの数。</br>
        - 分母: OneDrive または SharePoint にアクセスし、過去 28 日以内に Officeファイルにアクセスしたユーザーの数。

4. **リソースへのリンク:** ヘルプ コンテンツを表示するには、このリンクを選択します。

### <a name="use-of-attachments-in-email"></a>メールでの添付ファイルの使用

:::image type="content" source="../../media/emailattachments.png" alt-text="電子メールの添付ファイルの使用。":::

1. **ヘッダー:** OneDrive または SharePoint に保存されていないメールで添付ファイルを使用するユーザーの割合を強調表示します。
2. **本文:** コラボレーションとセキュリティの観点からオンライン ファイルへのリンクを共有する価値に関する情報を提供します。
3. **視覚化:** 視覚化の内訳は、メールにコンテンツを添付しているユーザーがさまざまなモード (OneDrive または SharePoint 上のファイルではなく、オンライン ファイルへのリンク、電子メールに埋め込まれたリンク) を使用している範囲を表すものです。
      - **ファイルの添付:** バーの青い (色付き) 部分とバーの分数 (分子/分母) は、電子メールで添付ファイルを使用しているユーザーの割合を表します。
        - Numerator: 過去 28 日以内に OneDrive または SharePoint に保存されなかったメールにファイルを添付するユーザーの数。
        - 分母:  分母: 過去 28 日以内に Exchange と OneDrive、SharePoint、または両方にアクセスしたユーザーの数。
      - **オンライン ファイルへのリンク:** バーの青い (色付き) 部分とバーの分数 (分子/分母) は、添付ファイルを使用し、電子メール内のファイルへのリンクを添付するユーザーの割合を表します。
        - Numerator: 過去 28 日以内にオンライン ファイル (OneDrive または SharePoint に保存) へのリンクをメールに添付するユーザーの数。
        - 分母:  分母: 過去 28 日以内に Exchange および OneDrive、SharePoint、または両方にアクセスできるユーザーの数。
      - **メールにリンクを埋め込む:** バーの青い (色付き) 部分とバーの端数は、電子メールの本文にリンクを埋め込むユーザーの割合を表します。
        - Numerator: 過去 28 日以内にオンライン ファイル (OneDrive または SharePoint に保存) への電子メールの本文にリンクを埋め込むユーザーの数。
        - 分母:  分母: 過去 28 日以内に Exchange と OneDrive、SharePoint、または両方にアクセスできるユーザーの数。
4. **リソースへのリンク:** ヘルプ コンテンツを表示するには、このリンクを選択します。

### <a name="sharing-of-online-files"></a>オンライン ファイルの共有

:::image type="content" source="../../media/sharingonlinefiles.png" alt-text="オンラインでファイルを共有するユーザーの数を示すグラフ。":::

1. **ヘッダー:** ファイルを外部で共有している OneDrive または SharePoint のアクセス権を持つユーザーの割合を強調表示します。
2. **本文:** 組織内のファイル共有設定&#39;変更して、組織に最も適したレベルのコラボレーションを有効にする管理者に関する情報を提供します。
3. **視覚化:** OneDrive または SharePoint にアクセスできるユーザーがファイルを内部または外部で共有する範囲を表します。
      - **外部:** バーの青い (色付き) 部分とバーの分数 (分子/分母) は、OneDrive または SharePoint へのアクセス権を持ち、ファイルを外部で共有しているユーザーの割合を表します。
        -  Numerator: 過去 28 日間に外部でファイルを共有しているユーザーの数
        - 分母: 過去 28 日間のうち少なくとも 1 日間、OneDrive または SharePoint にアクセスしたユーザーの総数。
      - **内部的にのみ:** バーの青い (色付き) 部分とバーの分数 (分子/分母) は、OneDrive または SharePoint にアクセス可能で、内部でのみファイルを共有しているユーザーの割合を表します。
        - Numerator: 過去 28 日以内にファイルを内部的に共有しているユーザーの数
        - 分母: 過去 28 日間のうち少なくとも 1 日間、OneDrive または SharePoint にアクセスしたユーザーの総数。
4. **リソースへのリンク:** ヘルプ コンテンツを表示するには、このリンクを選択します。

### <a name="number-of-files-collaborated-on"></a>共同作業を行うファイルの数

:::image type="content" source="../../media/intensityofcollab.png" alt-text="最も共同作業が行ったファイルの数を示すグラフ。":::

1. **ヘッダー:** これにより、4 つ以上のファイルで共同作業を行っている OneDrive または SharePoint にアクセスできるユーザーの割合が強調表示されます。
2. **本文:** これにより、ユーザーがオンライン ファイルを活用して共同作業を強化する方法に関する情報が提供されます。
3. **視覚化:** これは、共同作業を行うファイルの数に基づいて、OneDrive または SharePoint にアクセスできるユーザーの分布を示します。 これは、次の 4 つのカテゴリ (バーの青い部分と、そのカテゴリに分類される OneDrive または SharePoint にアクセスできるユーザーの割合を表します)。
      - **コラボレーションなし:**
        - **Numerator:** 過去 28 日間に任意のファイルで共同作業を行ってないユーザーの数
        - **分母:** 過去 28 日間のうち少なくとも 1 日間、OneDrive または SharePoint にアクセスできるユーザーの総数。
      - **1 ~ 3 ファイルでの共同作業:**
        - **Numerator:** 過去 28 日間に 1 ~ 3 つのファイルで共同作業を行うユーザーの数。
        - **分母:** 過去 28 日間のうち少なくとも 1 日間、OneDrive または SharePoint にアクセスしたユーザーの総数。
      - **4 ~ 10 ファイルでの共同作業:**
        - **Numerator:** 過去 28 日間に 4 ~ 10 のファイルで共同作業を行うユーザーの数
        - **分母:** 過去 28 日間のうち少なくとも 1 日間、OneDrive または SharePoint にアクセスしたユーザーの総数。
      - **11 以上のファイルでの共同作業:**
        - **Numerator:** 過去 28 日間に 11 つ以上のファイルで共同作業を行うユーザーの数
        - **分母:** 過去 28 日間のうち少なくとも 1 日間、OneDrive または SharePoint にアクセスしたユーザーの総数。
        
4. **リソースへのリンク:** ヘルプ コンテンツを表示するには、このリンクを選択します。

### <a name="network-performance-strength-for-onedrive-and-sharepoint"></a>OneDrive と SharePoint のネットワーク パフォーマンスの強さ

:::image type="content" source="../../media/networkperfstrength.png" alt-text="OneDrive と SharePoint のネットワーク パフォーマンスを示すグラフ。":::

1. **ヘッダー:** OneDrive と SharePoint へのネットワーク接続が悪いテスト済みデバイスの割合を強調表示します。 
2. **本文:** ネットワーク接続のパフォーマンスがコラボレーションにとって重要な理由に関する情報を提供します。 
3. **視覚化:** OneDrive と SharePoint に関連するネットワーク接続パフォーマンスのレベルが異なるデバイスの割合を示します。
      - **81~ 100 (最適)**: バーの濃い緑色 (色付き) 部分は、パフォーマンスが最も高いデバイスの割合を表します。
      - **61 ~ 80:** バーの緑色 (色付き) 部分は、ネットワーク パフォーマンス スコアが 60 ~ 80 のデバイスの割合を表します。 
      - **41~60**: バーのオレンジ色の部分は、ネットワーク パフォーマンス スコアが 40 ~ 60 のデバイスの割合を表します。 
      - **21 ~ 40:** バーの赤 (色) 部分は、ネットワーク パフォーマンス スコアが 20 ~ 40 のデバイスの割合を表します。 
      - **0 ~ 20**: バーの濃い赤色 (色付き) 部分は、ネットワーク パフォーマンス スコアが 0 ~ 20 の間で最悪のデバイスの割合を表します。 

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365 アプリの正常性 – テクノロジ エクスペリエンス](apps-health.md) (記事)\
[コミュニケーション – ユーザー エクスペリエンス](communication.md) (記事)\
[会議 – ユーザー エクスペリエンス](meetings.md) (記事)\
[モビリティ – ユーザー エクスペリエンス](mobility.md) (記事)\
[生産性スコアのプライバシーコントロール](privacy.md) (記事)\
[チームワーク – ユーザー エクスペリエンス](teamwork.md) (記事)
