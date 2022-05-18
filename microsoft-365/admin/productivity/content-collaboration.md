---
title: Microsoft Productivity Score コンテンツ コラボレーションの分析情報
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
description: コンテンツ コラボレーションの詳細 - ユーザーは生産性スコアを体験します。
ms.openlocfilehash: db747819b4c6a6599d1d7919c2a36f34204779a1
ms.sourcegitcommit: da6b3cb3b2ccfcdcd5091efce8290b6c486547db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/18/2022
ms.locfileid: "65466440"
---
# <a name="content-collaboration--people-experiences"></a>コンテンツ コラボレーション – ユーザー エクスペリエンス

生産性スコアは、Microsoft 365とそれをサポートするテクノロジ エクスペリエンスを使用することで、組織のデジタル変革の過程に関する分析情報を提供します。 組織のスコアは、ユーザーとテクノロジエクスペリエンスの測定値を反映し、自分に似た組織のベンチマークと比較できます。 コンテンツ コラボレーション カテゴリは、ユーザーエクスペリエンス測定の一部です。 詳細については、 [生産性スコアの概要](productivity-score.md) を確認し、 [Microsoft のプライバシーに関する声明](https://privacy.microsoft.com/privacystatement)を参照してください。

## <a name="prerequisites"></a>前提条件

コンテンツ コラボレーションの分析情報を使用するには、組織内のユーザーに次のライセンスを付与する必要があります。

- OneDrive for Business
- SharePoint
- Exchange Online

詳細については、「[ユーザーにライセンスを割り当てる](../manage/assign-licenses-to-users.md)」 を参照してください。

 過去 28 日間に少なくとも 1 回、上記の製品でユーザーがアクティブになった後、分析情報が表示されます。

## <a name="why-your-organization39s-content-collaboration-score-matters"></a>組織&#39;コンテンツ コラボレーション スコアが重要な理由

デジタル変革の重要な側面は、ユーザーがファイル内で共同作業する方法です。 Microsoft 365上のコンテンツを使用すると、他のユーザーと任意の場所からコンテンツにアクセス、作成、変更、共同作業を行うことができます。 調査によると、ユーザーがオンライン ファイルと共同作業すると、各ユーザーが 1 週間に平均 100 分保存されます。

## <a name="how-we-calculate-the-content-collaboration-score"></a>コンテンツ コラボレーション スコアを計算する方法

組織のコンテンツ コラボレーションの主要なメトリックを含む主要な分析情報を提供します。 次に、以下に詳しく説明するスコアリング フレームワークを使用して、組織のスコアを計算します。

> [!NOTE]
> 2021 年 4 月 22 日に、コラボレーターメトリックの計算方法を変更しました。 これは、 [プライマリ 分析情報](#primary-insight)、 [ファイル コラボレーション分析情報](#number-of-files-collaborated-on)、およびコンテンツ コラボレーション スコアの測定方法に影響します。 この変更は、Microsoft やその他のサードパーティ アプリケーションからの人間以外のエージェント (またはボット) からのデータのノイズを減らすのに役立ち、その結果、より正確で実用的なスコアが得られます。

### <a name="primary-insight"></a>主な分析情報

Microsoft OneDrive for BusinessとSharePointは、ユーザーがデバイスやアプリケーション間でMicrosoft 365で個人や共有コンテンツを簡単に作成、読み取り、検出するのに役立ちます。 また、ユーザーはコンテンツを安全に共有し、共同作業することもできます。 主な分析情報には、OneDrive for Business と SharePoint を使用できるすべてのユーザーからの情報が含まれます。 さらに、OneDrive for Business および SharePoint に保管されているコンテンツを何人のユーザーが読み取り、作成、およびコラボレーションしているのかに関する詳細も説明します。

:::image type="content" source="../../media/collabscore_primary.jpg" alt-text="コミュニケーション コラボレーション スコアからの主要な分析情報。":::


この情報で考慮される種類には、Word、Excel、PowerPoint、OneNote、PDF ファイルなどがあります。

1. **ヘッダー：** コンテンツで共同作業しているOneDriveまたはSharePointにアクセスできる組織内のユーザーの割合を示します。
2. **体：** ファイルのオンラインでの読み取りと作成の動作がファイルの共同作業にどのようにリンクされるかについて詳しく説明します。
3. **視覚化 (現在の状態):**
    - 青色の部分を示す横棒は、過去 28 日間にオンライン ファイルの **閲覧者、作成者、****コラボレーター** であったOneDriveまたはSharePointを通じてファイル コラボレーションを有効にしたユーザーの割合を表します。

        これらは次のように定義されています。</br>
        **読者：** OneDriveまたはSharePointでオンライン ファイルにアクセスまたはダウンロードするユーザー。</br>
        **クリエイター：** ファイルの作成、変更、アップロード、同期、チェックイン、コピー、またはオンライン OneDriveまたはSharePointの移動を行うユーザー。</br>
        **協力：** OneDriveまたはSharePointを使用してオンライン ファイルと共同作業するユーザー。 28 日間のウィンドウ内で、他のユーザーがオンライン Office アプリまたは PDF を作成または変更した後に、そのうちの 1 人が読み取りまたは編集した場合、2 人はコラボレーターです。

        > [!NOTE]
        > 視覚化で考慮されるファイルは、Word、Excel、PowerPoint、OneNote、PDF ファイルで、オンラインでOneDriveまたはSharePointに保存されます。 

    - 分数の強調表示 (numerator/分母) は、各水平バーで表されるパーセンテージを計算するために使用されます。
    
      - **読者：**</br>
          - Numerator: 過去 28 日間にOneDriveまたはSharePointでオンライン ファイルにアクセスまたはダウンロードしたユーザーの数</br>
          - 分母: 過去 28 日間のうち少なくとも 1 日間、OneDriveまたはSharePointにアクセスしたユーザーの数</br>
      - **クリエイター：**</br>
        - Numerator: 過去 28 日間にOneDriveまたはSharePointでオンライン ファイルを作成、変更、アップロード、同期、チェックイン、コピー、または移動するユーザーの数</br>
        - 分母: 過去 28 日間のうち少なくとも 1 日間、OneDriveまたはSharePointにアクセスしたユーザーの数。 </br> 
      - **協力：**</br>
        - Numerator: 過去 28 日間にOneDriveまたはSharePointのオンライン ファイルで共同作業を行ったユーザーの数</br>
        - 分母: 過去 28 日間のうち少なくとも 1 日間、OneDriveまたはSharePointにアクセスしたユーザーの数

    - 閲覧者、作成者、コラボレーターごとのピア ベンチマーク値もパーセンテージで表示されます。 つまり、作成者の数の値は、OneDriveまたはSharePointにアクセスできるユーザーの数の割合として表示されます。
    
1. **リソースへのリンク:** このリンクを選択すると、照合されたビデオやその他の関連するヘルプ コンテンツが表示されます。


#### <a name="trend-visualization-of-primary-insight"></a>主要な分析情報の傾向の視覚化

傾向視覚化グラフには、過去 180 日間のリーダー、作成者、コラボレーターの主要な分析情報の主要なメトリックの傾向線が表示されます。 グラフ上の各データ ポイントは、過去 28 日間のアクティビティの集計です。 各作成者データ ポイントには、x 軸上の日付ごとに、過去 28 日以内に作成者としてタグ付けされたすべてのユーザーの数が表示されます。

:::image type="content" source="../../media/trendvisualization.jpg" alt-text="コラボレーションの主な分析情報の傾向を含むグラフ。":::

### <a name="scoring-framework"></a>スコアリング フレームワーク

組織のコンテンツ コラボレーション スコアは、ユーザーが Word、Excel、PowerPoint、OneNote、PDF などのオンライン Office ファイル、またはOneDriveまたはSharePointで一貫して読み取り、作成、または共同作業を行っているかどうかにかかわらず、集計 (組織) レベルで測定されます。

スコアは、個々のユーザー レベルでは提供されません。

## <a name="explore-how-your-organization-collaborates"></a>組織の共同作業方法を確認する

また、組織がコンテンツに対して共同作業する方法を把握するのに役立つ情報も提供されます。 これらの追加メトリックは、生産性スコアに直接影響を与えるのではなく、デジタル変革の一環としてアクション プランを作成し、ユーザーの働き方を最適化するのに役立ちます。

### <a name="creating-files-in-onedrive-or-sharepoint"></a>OneDriveまたはSharePointでのファイルの作成

:::image type="content" source="../../media/sharepointonedrivefiles.jpg" alt-text="OneDriveまたはSharePointでファイルを作成するユーザーの数を示すグラフ。":::

1. **ヘッダー：** OneDriveまたはSharePointでファイルを作成するMicrosoft 365 Office アプリケーションでアクティブなユーザーの割合を強調表示します。
2. **体：** OneDriveとSharePointでのコンテンツ作成の価値に関する情報を提供します。
3. **可視 化：** 視覚化の内訳は、OneDriveとSharePointでMicrosoft Office アプリを使用してファイルを作成するユーザーの範囲を次のように表します。
      - **OneDrive:** バーの青 (色付き) 部分とバーの分数は、OneDriveでコンテンツを作成するOffice アプリケーションでアクティブなユーザーの割合を次のように表します。
        - Numerator: 過去 28 日以内にOneDriveでオンライン Office ファイルを作成、変更、アップロード、同期、チェックイン、コピー、または移動するユーザーの数。</br>
        - 分母: 過去 28 日以内にOneDriveまたはSharePointにアクセスし、オフィス ファイルにアクセスできるユーザーの数。
      - **SharePoint:** バーの青 (色付き) 部分とバーの分数は、Office アプリケーションでアクティブで、SharePointでコンテンツを作成するユーザーの割合を表します。</br>
         - Numerator: 過去 28 日以内にSharePointでオンライン Office ファイル (Microsoft Word、Excel、PowerPoint、またはOneNote ファイル) を作成、変更、アップロード、同期、チェックイン、コピー、または移動するユーザーの数。</br>
        - 分母: 過去 28 日以内にOneDriveまたはSharePointにアクセスし、Office ファイルにアクセスしたユーザーの数。

4. **リソースへのリンク:** ヘルプ コンテンツを表示するには、このリンクを選択します。

### <a name="use-of-attachments-in-email"></a>電子メールでの添付ファイルの使用

**電子メールでの添付ファイルの使用** クラウド内のコンテンツへのリンクではなく、電子メールに物理ファイルを添付しているユーザーの数を理解し、時間の経過と共にこの数の減少を監視します。

:::image type="content" source="../../media/emailattachments.png" alt-text="電子メールの添付ファイルの使用。":::

1. **ヘッダー：** オンライン ファイルに保存されなかったメールで添付ファイルを使用しているユーザーの割合を強調表示します。
2. **体：** コラボレーションとセキュリティの観点から、オンライン ファイルへのリンクを共有することの価値に関する情報を提供します。
3. **可視 化：** 視覚化の内訳は、電子メールでコンテンツを添付しているユーザーが異なるモード (オンライン ファイルに保存されていないファイル、オンライン ファイルへのリンク) を使用している範囲を表します。
      - **ファイルを添付する:** バーの青 (色付き) 部分とバーの分数 (分子/分母) は、メールで添付ファイルを使用しているユーザーの割合を表します。
        - Numerator: 過去 28 日以内にオンライン ファイルに保存されなかったメールにファイルを添付したユーザーの数。
        - 分母: 過去 28 日以内にExchangeとOneDrive、SharePoint、またはその両方にアクセスしたユーザーの数。
      - **オンライン ファイルへのリンク:** バーの青 (色付き) 部分とバーの分数 (分子/分母) は、添付ファイルを使用し、メール内のファイルへのリンクを添付しているユーザーの割合を表します。
        - Numerator: 過去 28 日以内にオンライン ファイルへのリンクを電子メールに添付しているユーザーの数。
        - 分母: 過去 28 日以内にExchangeとOneDrive、SharePoint、またはその両方にアクセスできるユーザーの数。
4. **リソースへのリンク:** ヘルプ コンテンツを表示するには、このリンクを選択します。

### <a name="sharing-of-online-files"></a>オンライン ファイルの共有

:::image type="content" source="../../media/sharingonlinefiles.png" alt-text="オンラインでファイルを共有しているユーザーの数を示すグラフ。":::

1. **ヘッダー：** 外部でファイルを共有しているOneDriveまたはSharePointにアクセスできるユーザーの割合を強調表示します。
2. **体：** 組織に最適なコラボレーション レベルを有効にするために、組織内のファイル共有設定を変更する&#39;管理者に関する情報を提供します。
3. **可視 化：** OneDriveまたはSharePointにアクセスできるユーザーが内部または外部でファイルを共有している範囲を表します。
      - **外部：** バーの青 (色付き) 部分とバーの分数 (分子/分母) は、OneDriveまたはSharePointにアクセスし、外部でファイルを共有しているユーザーの割合を表します。
        -  Numerator: 過去 28 日間に外部でファイルを共有したユーザーの数
        - 分母: 過去 28 日間のうち少なくとも 1 日間、OneDriveまたはSharePointにアクセスしたユーザーの合計数。
      - **内部的にのみ:** バーの青 (色付き) 部分とバーの分数 (分子/分母) は、OneDriveまたはSharePointにアクセスし、内部的にのみファイルを共有しているユーザーの割合を表します。
        - Numerator: 過去 28 日以内にのみ内部でファイルを共有しているユーザーの数。
        - 分母: 過去 28 日間のうち少なくとも 1 日間、OneDriveまたはSharePointにアクセスしたユーザーの合計数。
4. **リソースへのリンク:** ヘルプ コンテンツを表示するには、このリンクを選択します。

### <a name="number-of-files-collaborated-on"></a>共同作業を行ったファイルの数

:::image type="content" source="../../media/intensityofcollab.png" alt-text="最も共同作業が行われたファイルの数を示すグラフ。":::

1. **ヘッダー：** 4 つ以上のファイルで共同作業しているOneDriveまたはSharePointにアクセスできるユーザーの割合を強調表示します。
2. **体：** ユーザーがオンライン ファイルを活用して共同作業を強化する方法に関する情報を提供します。
3. **可視 化：** 共同作業するファイルの数に基づいて、OneDriveまたはSharePointにアクセスできるユーザーの分布を示します。 これは、次の 4 つのカテゴリ (それぞれ、バーの青い部分と、そのカテゴリに該当するOneDriveまたはSharePointにアクセスできるユーザーの割合を表します)。
      - **コラボレーションなし:**
        - Numerator: 過去 28 日間に任意のファイルで共同作業を行っていないユーザーの数。
        - 分母: 過去 28 日間のうち少なくとも 1 日間、OneDriveまたはSharePointにアクセスできるユーザーの合計数。
      - **1 - 3 ファイルでのコラボレーション:**
        - Numerator: 過去 28 日間に 1 ~ 3 個のファイルで共同作業しているユーザーの数。
        - 分母: 過去 28 日間のうち少なくとも 1 日間、OneDriveまたはSharePointにアクセスしたユーザーの合計数。
      - **4 - 10 ファイルでのコラボレーション:**
        - Numerator: 過去 28 日間に 4 ~ 10 個のファイルで共同作業を行っているユーザーの数。
        - 分母: 過去 28 日間のうち少なくとも 1 日間、OneDriveまたはSharePointにアクセスしたユーザーの合計数。
      - **11 以上のファイルに対するコラボレーション:**
        - Numerator: 過去 28 日間に 11 以上のファイルで共同作業しているユーザーの数。
        - 分母: 過去 28 日間のうち少なくとも 1 日間、OneDriveまたはSharePointにアクセスしたユーザーの合計数。
        
4. **リソースへのリンク:** ヘルプ コンテンツを表示するには、このリンクを選択します。

### <a name="network-performance-strength-for-onedrive-and-sharepoint"></a>OneDriveとSharePointのネットワーク パフォーマンスの強度

:::image type="content" source="../../media/networkperfstrength.png" alt-text="OneDriveとSharePointのネットワーク パフォーマンスを示すグラフ。":::

1. **ヘッダー：** テスト済みのすべてのデバイスのうち、OneDriveとSharePointへのネットワーク接続が不十分なデバイスの割合を強調表示します。 
2. **体：** コラボレーションにとってネットワーク接続のパフォーマンスが重要な理由に関する情報を提供します。 
3. **可視 化：** OneDriveとSharePointに関連するネットワーク接続のパフォーマンスのレベルが異なるデバイスの割合を示します。
      - **81 ~ 100 (最適)**: バーの濃い緑色 (色付き) 部分は、最適なパフォーマンスを持つデバイスの割合を表します。
      - **61 - 80**: バーの緑色の部分は、ネットワーク パフォーマンス スコアが 60 ~ 80 のデバイスの割合を表します。 
      - **41 - 60**: バーのオレンジ色の部分は、ネットワーク パフォーマンス スコアが 40 ~ 60 のデバイスの割合を表します。 
      - **21 - 40**: バーの赤 (色付き) 部分は、ネットワーク パフォーマンス スコアが 20 ~ 40 のデバイスの割合を表します。 
      - **0 ~ 20**: バーの濃い赤 (色付き) 部分は、ネットワーク パフォーマンススコアが 0 ~ 20 の最悪のデバイスの割合を表します。 

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365 アプリの正常性 – テクノロジ エクスペリエンス](apps-health.md) (記事)\
[コミュニケーション – People エクスペリエンス](communication.md) (記事)\
[会議 – People エクスペリエンス](meetings.md) (記事)\
[モビリティ – ユーザー エクスペリエンス](mobility.md) (記事)\
[生産性スコアのプライバシー 制御](privacy.md) (記事)\
[チームワーク – People エクスペリエンス](teamwork.md) (記事)
