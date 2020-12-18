---
title: Microsoft Productivity Score - コンテンツコラボレーション
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: コンテンツコラボレーションの詳細 - ユーザーエクスペリエンスの生産性スコア。
ms.openlocfilehash: 62486511be7e085401e4a2934ce3742a15729e1f
ms.sourcegitcommit: 0867495cb02d0b38b439b16bdce97e6eda483ba9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/18/2020
ms.locfileid: "49712593"
---
# <a name="content-collaboration--people-experiences"></a>コンテンツコラボレーション - ユーザー エクスペリエンス

生産性スコアは、Microsoft 365 の使用とそれをサポートするテクノロジ エクスペリエンスを通じて、組織のデジタル変換への取り組みについての洞察を提供します。 組織のスコアは、人とテクノロジのエクスペリエンスの測定値を反映し、自分と同様の組織からのベンチマークと比較できます。 コンテンツ コラボレーション カテゴリは、ユーザー エクスペリエンスの測定値の一部です。 詳細については、生産性スコアの概要 [を](productivity-score.md) 確認し、Microsoft のプライバシーに関する声明 [を参照してください](https://privacy.microsoft.com/privacystatement)。

## <a name="prerequisites"></a>前提条件

コンテンツコラボレーションの分析情報を開始するには、組織内のユーザーに次のライセンスが必要です。

- OneDrive for Business
- SharePoint
- Exchange Online

詳細については、「ライセンスをユーザーに割 [り当てる」を参照してください](../manage/assign-licenses-to-users.md)。

 過去 28 日間に少なくとも 1 回、上記の製品でユーザーがアクティブにされた後、分析情報の表示が開始されます。

## <a name="why-your-organization39s-content-collaboration-score-matters"></a>組織でコンテンツ コラボレーション&#39;が重要な理由

デジタル変換の重要な側面は、ユーザーがファイルでどのように共同作業を行うかです。 Microsoft 365 のコンテンツを使用すると、ユーザーは任意の場所から他のユーザーとコンテンツにアクセス、作成、変更、共同作業を行います。 調査によると、ユーザーがオンライン ファイルで共同作業を行う場合、各ユーザーは 1 週間に平均 100 分保存されます。 [証拠を確認します](https://vc2prod.blob.core.windows.net/vc-resources/TEIStudies/TEI%20of%20Microsoft%20365%20E5%20-%20Oct%202018.pdf)。

## <a name="how-we-calculate-the-content-collaboration-score"></a>コンテンツ コラボレーション スコアの計算方法

組織のコンテンツコラボレーションに関する主要な指標を含む主要な分析情報を提供します。 次に、以下に示すスコアリング フレームワークを使用して、組織のスコアを計算します。

### <a name="primary-insight"></a>主な分析情報

Microsoft OneDrive for Business と SharePoint を使用すると、Microsoft 365 の個々のコンテンツや共有コンテンツをデバイスやアプリケーション間から簡単に作成、読み取り、検出できます。 また、ユーザーはコンテンツを安全に共有し、共同作業することができます。 主要な分析情報には、OneDrive for Business と SharePoint を使用できるすべてのユーザーからの情報が含まれる。 さらに、OneDrive for Business と SharePoint に保存されているコンテンツの読み取り、作成、共同作業のユーザー数に関する詳細が分かっています。

:::image type="content" source="../../media/collabscore_primary.jpg" alt-text="コミュニケーション コラボレーション スコアからの主要な分析情報。":::


この情報を考慮する型には、Word、Excel、PowerPoint、OneNote、PDF ファイルが含まれます。

1. **ヘッダー:** OneDrive または SharePoint にアクセスできる、コンテンツで共同作業を行っているユーザーの割合を示します。
2. **本文:** オンラインでのファイルの読み取りおよび作成の動作とファイルの共同作業とのリンクについて詳しく説明します。
3. **視覚化 (現在の状態):**
    - 青色の部分が、過去 28 日間にオンライン ファイルの閲覧者、作成者、または共同作業者である OneDrive または SharePointを通じてファイルの共同作業が有効にされたユーザーの割合を表す水平バー。 

        これらは次のように定義されます。</br>
        **閲覧者:** OneDrive または SharePoint でオンライン ファイルにアクセスまたはダウンロードするユーザー。</br>
        **作成者:** オンラインの OneDrive または SharePoint ファイルを作成、変更、アップロード、同期、チェックイン、コピー、または移動するユーザー。</br>
        **共同作業者:** OneDrive または SharePoint を使用してオンライン ファイルで共同作業を行うユーザー。 2 人のユーザーが 28 日間のウィンドウ内で、他のユーザーが作成または変更した後にオンライン Office アプリまたは PDF を読み取りまたは編集した場合、2 人は共同作業者です。

        > [!NOTE]
        > 視覚エフェクトで考慮されるファイルは、オンラインで OneDrive または SharePoint に保存されている Word、Excel、PowerPoint、OneNote、または PDF ファイルです。 

    - 分数の強調表示 (numerator/分母) は、各水平バーで表されるパーセンテージを計算するために使用されます。
    
      - **閲覧者:**</br>
          - Numerator: 過去 28 日間に OneDrive または SharePoint のオンライン ファイルにアクセスまたはダウンロードしたユーザーの数</br>
          - 分母: 過去 28 日間のうち少なくとも 1 日間、OneDrive または SharePoint にアクセスしたユーザーの数</br>
      - **作成者:**</br>
        - Numerator: 過去 28 日間に OneDrive または SharePoint でオンライン ファイルを作成、変更、アップロード、同期、チェックイン、コピー、または移動したユーザーの数</br>
        - 分母: 過去 28 日間のうち少なくとも 1 日間、OneDrive または SharePoint にアクセスしたユーザーの数。 </br> 
      - **共同作業者:**</br>
        - Numerator: 過去 28 日間に OneDrive または SharePoint のオンライン ファイルで共同作業を行ったユーザーの数</br>
        - 分母: 過去 28 日間のうち少なくとも 1 日間、OneDrive または SharePoint にアクセスしたユーザーの数

    - 各閲覧者、作成者、および共同作業者のピア ベンチマーク値もパーセンテージで表示されます。 つまり、作成者の数の値は、OneDrive または SharePoint にアクセスできるユーザーの数に対する割合として表示されます。
    
1. **リソースへのリンク:** 照合されたビデオ、および他の関連するヘルプ コンテンツを表示するには、このリンクを選択します。


#### <a name="trend-visualization-of-primary-insight"></a>主な分析情報の傾向の視覚化

傾向可視化グラフには、過去 180 日間の閲覧者、作成者、および共同作業者の主な分析情報の主要指標の傾向線が表示されます。 グラフの各データ ポイントは、過去 28 日間のアクティビティの集計です。 各作成者データ ポイントは、x 軸の日付ごとに、過去 28 日以内に作成者としてタグ付けされたユーザーの数を提供します。

:::image type="content" source="../../media/trendvisualization.jpg" alt-text="コラボレーションの主な分析情報の傾向を示す図。":::

### <a name="scoring-framework"></a>スコアリング フレームワーク

組織のコンテンツ コラボレーション スコアは、ユーザーがオンラインの Office ファイル (Word、Excel、PowerPoint、OneNote、PDF など) または OneDrive または SharePoint で一貫して読み取り、作成、または共同作業を行っているかどうかについて、集計 (組織) レベルで測定します。

スコアは個々のユーザー レベルでは提供されない。


## <a name="explore-how-your-organization-collaborates"></a>組織の共同作業方法を確認する

また、組織がコンテンツに関する共同作業を行う方法を知るために役立つ情報も提供されます。 これらの追加の指標は、生産性スコアに直接貢献するのではなく、デジタル変換の一環としてアクション プラン計画を作成し、ユーザーの作業方法を最適化するのに役立ちます。

### <a name="creating-files-in-onedrive-or-sharepoint"></a>OneDrive または SharePoint でのファイルの作成

:::image type="content" source="../../media/sharepointonedrivefiles.jpg" alt-text="OneDrive または SharePoint でファイルを作成したユーザーの数を示すグラフ":::

1. **ヘッダー:** OneDrive または SharePoint でファイルを作成する Microsoft 365 Officeでアクティブなユーザーの割合を強調表示します。
2. **本文:** OneDrive および SharePoint でのコンテンツ作成の価値に関する情報を提供します。
3. **視覚化:** 視覚エフェクトの内訳は、OneDrive と SharePoint で Microsoft Office アプリを使用してファイルを作成しているユーザーの範囲を表します。
      - **OneDrive:** バーの青色 (色付き) 部分とバーの分数は、OneDrive 上でコンテンツを作成する Office アプリケーションでアクティブなユーザーの割合を次のように表します。
        - Numerator: 過去 28 日以内に OneDrive でオンライン Office ファイルを作成、変更、アップロード、同期、チェックイン、コピー、または移動したユーザーの数。</br>
        - 分母: OneDrive または SharePoint にアクセスし、過去 28 日以内に Office ファイルにアクセスできるユーザーの数。
      - **SharePoint:** バーの青 (色付き) 部分とバーの小数部は、Office アプリケーションでアクティブで、SharePoint 上で次のようにコンテンツを作成するユーザーの割合を表します。</br>
         - Numerator: 過去 28 日以内に SharePoint 上のオンライン Office ファイル (Microsoft Word、Excel、PowerPoint、または OneNote ファイル) を作成、変更、アップロード、同期、チェックイン、コピー、または移動したユーザーの数。</br>
        - 分母: OneDrive または SharePoint にアクセスし、過去 28 日以内に Officeファイルにアクセスしたユーザーの数。

4. **リソースへのリンク:** ヘルプ コンテンツを表示するには、このリンクを選択します。

### <a name="use-of-attachments-in-email"></a>メールでの添付ファイルの使用

:::image type="content" source="../../media/emailattachments.png" alt-text="メールの添付ファイルの使用。":::

1. **ヘッダー:** OneDrive または SharePoint に保存されていないメールで添付ファイルを使用するユーザーの割合を強調表示します。
2. **本文:** コラボレーションとセキュリティの観点から、オンライン ファイルへのリンクを共有する価値に関する情報を提供します。
3. **視覚化:** 視覚エフェクトの内訳は、メールにコンテンツを添付しているユーザーが、どの程度異なるモード (OneDrive または SharePoint 上のファイルではなく、オンライン ファイルへのリンク、電子メールに埋め込まれたリンク) を使用するかを表すものです。
      - **ファイルを添付します。** バーの青色 (色付き) 部分とバーの分数 (分子/分母) は、メールの添付ファイルを使用しているユーザーの割合を表します。
        - Numerator: 過去 28 日以内に OneDrive または SharePoint に保存されなかったメールにファイルを添付したユーザーの数。
        - 分母: – 分母: 過去 28 日以内に Exchange と OneDrive、SharePoint、または両方にアクセスしたユーザーの数。
      - **オンライン ファイルへのリンク:** バーの青色 (色付き) 部分とバーの分数 (分子/分母) は、添付ファイルを使用し、メール内のファイルへのリンクを添付しているユーザーの割合を表します。
        - Numerator: 過去 28 日以内にオンライン ファイル (OneDrive または SharePoint に保存) へのリンクをメールに添付するユーザーの数。
        - 分母: – 分母: 過去 28 日以内に Exchange と OneDrive、SharePoint、または両方にアクセスできるユーザーの数。
      - **メールへのリンクの埋め込み:** バーの青色 (色付き) 部分とバーの分数は、メールの本文にリンクを埋め込むユーザーの割合を表します。
        - Numerator: 過去 28 日以内にオンライン ファイル (OneDrive または SharePoint に保存) へのメール本文にリンクを埋め込むユーザーの数。
        - 分母: – 分母: 過去 28 日以内に Exchange と OneDrive、SharePoint、または両方にアクセスできるユーザーの数。
4. **リソースへのリンク:** ヘルプ コンテンツを表示するには、このリンクを選択します。

### <a name="sharing-of-online-files"></a>オンライン ファイルの共有

:::image type="content" source="../../media/sharingonlinefiles.png" alt-text="オンラインでファイルを共有しているユーザーの数を示すグラフ。":::

1. **ヘッダー:** 外部でファイルを共有している OneDrive または SharePoint にアクセスできるユーザーの割合を強調表示します。
2. **本文:** 組織に最適なコラボレーション&#39;レベルを有効にするために、組織内のファイル共有設定を変更する機能を持つ管理者に関する情報を提供します。
3. **視覚化:** OneDrive または SharePoint にアクセスできるユーザーがファイルを内部または外部で共有する範囲を表します。
      - **外部的:** バーの青色 (色付き) 部分とバーの分数 (分子/分母) は、OneDrive または SharePoint にアクセス可能で、外部でファイルを共有しているユーザーの割合を表します。
        -  Numerator: 過去 28 日間にファイルを外部と共有したユーザーの数
        - 分母: 過去 28 日間のうち少なくとも 1 日間に OneDrive または SharePoint にアクセスしたユーザーの総数です。
      - **内部のみ:** バーの青色 (色付き) 部分とバーの分数 (分子/分母) は、OneDrive または SharePoint にアクセスできるユーザーの割合を表し、ファイルを内部でのみ共有しています。
        - Numerator: 過去 28 日以内にのみ内部的にファイルを共有したユーザーの数
        - 分母: 過去 28 日間のうち少なくとも 1 日間に OneDrive または SharePoint にアクセスしたユーザーの総数です。
4. **リソースへのリンク:** ヘルプ コンテンツを表示するには、このリンクを選択します。

### <a name="number-of-files-collaborated-on"></a>共同作業を行ったファイルの数

:::image type="content" source="../../media/intensityofcollab.png" alt-text="最も共同作業が行ったファイルの数を示す図。":::

1. **ヘッダー:** これは、4 つ以上のファイルで共同作業を行っている OneDrive または SharePoint にアクセスできるユーザーの割合を強調しています。
2. **本文:** これにより、ユーザーがオンライン ファイルを活用して共同作業を向上する方法に関する情報が提供されます。
3. **視覚化:** これは、共同作業を行うファイルの数に基づいて、OneDrive または SharePoint にアクセスできるユーザーの配布を示しています。 これは、次の 4 つのカテゴリを通じて表示されます (それぞれ、バーの青色の部分と分数は、そのカテゴリに分類される OneDrive または SharePoint にアクセスできるユーザーの割合を表します)。
      - **コラボレーションなし:**
        - **Numerator:** 過去 28 日間にファイルで共同作業を行ってないユーザーの数
        - **分母:** 過去 28 日間のうち少なくとも 1 日間、OneDrive または SharePoint にアクセスできるユーザーの総数です。
      - **1 ~ 3 ファイルでのコラボレーション:**
        - **Numerator:** 過去 28 日間に 1 ~ 3 ファイルで共同作業を行ったユーザーの数。
        - **分母:** 過去 28 日間のうち少なくとも 1 日間に OneDrive または SharePoint にアクセスしたユーザーの総数です。
      - **4 ~ 10 ファイルでのコラボレーション:**
        - **Numerator:** 過去 28 日間に 4 ~ 10 のファイルで共同作業を行っているユーザーの数
        - **分母: 過去** 28 日間のうち少なくとも 1 日間に OneDrive または SharePoint にアクセスしたユーザーの総数です。
      - **11 以上のファイルでのコラボレーション:**
        - **Numerator:** 過去 28 日間に 11 以上のファイルで共同作業を行っているユーザーの数
        - **分母:** 過去 28 日間のうち少なくとも 1 日間に OneDrive または SharePoint にアクセスしたユーザーの総数です。
        
4. **リソースへのリンク:** ヘルプ コンテンツを表示するには、このリンクを選択します。

### <a name="network-performance-strength-for-onedrive-and-sharepoint"></a>OneDrive と SharePoint のネットワーク パフォーマンスの強度

:::image type="content" source="../../media/networkperfstrength.png" alt-text="OneDrive と SharePoint のネットワーク パフォーマンスを示す図。":::

1. **ヘッダー:** OneDrive と SharePoint へのネットワーク接続が不十分なテスト済みデバイスの割合を強調表示します。 
2. **本文:** コラボレーションでネットワーク接続のパフォーマンスが重要な理由に関する情報を提供します。 
3. **視覚化:** OneDrive と SharePoint に関連するネットワーク接続パフォーマンスのレベルが異なるデバイスの割合を示します。
      - **81 ~ 100 (最適)**: バーの濃い緑色 (色付き) の部分は、最高のパフォーマンスを持つデバイスの割合を表します。
      - **61 ~ 80:** バーの緑色 (色付き) の部分は、ネットワーク パフォーマンス スコアが 60 ~ 80 のデバイスの割合を表します。 
      - **41 ~ 60:** バーのオレンジ (色付き) 部分は、ネットワーク パフォーマンス スコアが 40 ~ 60 のデバイスの割合を表します。 
      - **21 ~ 40:** バーの赤 (色付き) 部分は、ネットワーク パフォーマンス スコアが 20 ~ 40 のデバイスの割合を表します。 
      - **0 ~ 20:** バーの濃い赤色 (色付き) の部分は、ネットワーク パフォーマンス スコアが 0 ~ 20 の最も低いデバイスの割合を表します。 

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365 アプリの正常性 – テクノロジ エクスペリエンス](apps-health.md) (記事)\
[コミュニケーション – ユーザー エクスペリエンス](communication.md) (記事)\
[会議 - ユーザー エクスペリエンス](meetings.md) (記事)\
[モビリティ – ユーザー エクスペリエンス](mobility.md) (記事)\
[生産性スコアのプライバシー コントロール](privacy.md) (記事)\
[チームワーク - 人のエクスペリエンス](teamwork.md) (記事)
