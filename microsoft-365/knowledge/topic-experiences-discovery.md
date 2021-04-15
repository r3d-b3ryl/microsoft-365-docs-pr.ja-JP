---
title: Microsoft Viva Topics でトピックの検出を管理する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: トピックの検出を管理する方法については、「Microsoft Viva Topics」を参照してください。
ms.openlocfilehash: 53e304dc69ccf2ca6fe01d29f0997c539406b0fe
ms.sourcegitcommit: 4acf613587128cae27e0fd470d1216b509775529
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768976"
---
# <a name="manage-topic-discovery-in-microsoft-viva-topics"></a>Microsoft Viva Topics でトピックの検出を管理する

トピックの検出設定は [、Microsoft 365 管理センターで管理できます](https://admin.microsoft.com)。 これらのタスクを実行するには、グローバル管理者または SharePoint 管理者である必要があります。

## <a name="to-access-topics-management-settings"></a>トピックの管理設定にアクセスするには、次の方法を実行します。

1. Microsoft 365 管理センターで、[設定] をクリック **し**、[組織の設定] **をクリックします**。
2. [サービス] **タブで** 、[トピック エクスペリエンス] **をクリックします**。

    ![ユーザーをナレッジに接続する](../media/admin-org-knowledge-options-completed.png) 

3. [トピックの **検出] タブを** 選択します。各設定の詳細については、以下のセクションを参照してください。

    ![ナレッジ ネットワーク設定](../media/knowledge-network-settings-topic-discovery.png) 

## <a name="select-sharepoint-topic-sources"></a>SharePoint トピック ソースの選択

トピック用にクロールされる組織内の SharePoint サイトを変更できます。

サイトの特定のリストを含めるか除外する場合は、次の .csv テンプレートを使用できます。

``` csv
Site name,URL
```

サイト ピッカーを使用してサイトを追加すると、サイトの既存のリストに追加され、追加または除外されます。 .csv ファイルをアップロードすると、既存のリストが上書きされます。 特定のサイトを以前に含めるか除外した場合は、リストを .csv ファイルとしてダウンロードし、変更を加え、新しいリストをアップロードします。

トピック検出用のサイトを選択するには

1. [トピックの **検出] タブの** **[SharePoint トピック** ソースの選択] で、[編集] を **選択します**。
2. **[SharePoint トピック ソースの選択**] ページで、探索中にトピックのソースとしてクロールする SharePoint サイトを選択します。 次のようなシナリオが考えられます。
    - **すべてのサイト**: テナント内のすべての SharePoint サイト。 これにより、現在および将来のサイトがキャプチャされます。
    - **[すべて] (選択したサイトを** 除く): 除外するサイトの名前を入力します。  検出からオプトアウトするサイトの一覧をアップロードできます。 今後作成されるサイトは、トピック検出のソースとして含まれます。 
    - **選択したサイトのみ**: 含めるサイトの名前を入力します。 サイトのリストをアップロードできます。 今後作成されるサイトは、トピック検出のソースとして含まれません。
    - **サイトなし**: トピックは SharePoint コンテンツで自動的に生成または更新されません。 既存のトピックはトピック センターに残ります。

    ![SharePoint トピック ソースのユーザー インターフェイスのスクリーンショット](../media/k-manage-select-topic-source.png)
   
3. **[保存]** をクリックします。

## <a name="exclude-topics-by-name"></a>トピックを名前で除外する

トピックを検出から除外するには、.csv ファイルを使用してリストをアップロードします。 以前にトピックを除外した場合は、.csv をダウンロードし、変更を加え、もう一度アップロードできます。

1. [トピックの **検出] タブの** [トピックの除外 **] で**、[編集] を **選択します**。
2. [名前 **でトピックを除外する] をクリックします**。
3. リストを作成する必要がある場合は、.csv テンプレートをダウンロードし、除外するトピックを追加します (以下の *「.csv* テンプレートの操作」を参照してください)。 ファイルの準備ができたら、[参照] を **クリックして** ファイルをアップロードします。 既存のリストがある場合は、リストを含む .csv をダウンロードできます。
4. **[保存]** をクリックします。

    ![除外トピックのユーザー インターフェイスのスクリーンショット](../media/km-manage-exclude-topics.png)

### <a name="working-with-the-csv-template"></a>.csv テンプレートの操作

csv テンプレートは、以下にコピーできます。

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

CSV テンプレートで、除外するトピックに関する次の情報を入力します。

- **名前**: 除外するトピックの名前を入力します。 これを行うには 2 つの方法があります。
    - 完全一致: 厳密な名前または頭字語 *(Contoso* や ATL など) を *除外できます*。
    - 部分一致: 特定の単語が含まれていますすべてのトピックを除外できます。  たとえば、*円弧は、* アーク円、プラズマアーク溶接、トレーニングアークなど、アークという単語を含むすべてのトピック *を除外します*。テキストが単語の一部として含まれているトピック (Architecture など) は除外されない点に *注意してください*。
- **略語 (省略可能)**: 頭字語を除外する場合は、頭字語の略語を入力します。
- **MatchType-Exact/Partial**: 入力した名前が完全一致型か部分一致型 *かを入力します*。

    ![CSV テンプレートのトピックを除外する](../media/exclude-topics-csv.png) 

## <a name="see-also"></a>関連項目

[Microsoft 365 でのトピックの表示を管理する](topic-experiences-knowledge-rules.md)

[Microsoft 365 でのトピックのアクセス許可の管理](topic-experiences-user-permissions.md)

[Microsoft 365 でトピック センターの名前を変更する](topic-experiences-administration.md)
