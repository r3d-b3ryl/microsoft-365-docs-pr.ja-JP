---
title: Microsoft のトピックの検出を管理するトピック
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: トピック検出を管理する方法については、「Microsoft のトピック」を参照してください。
ms.openlocfilehash: 36b64433726479dc2a46c809ae9504c6f12f4ab8
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107761"
---
# <a name="manage-topic-discovery-in-microsoft-viva-topics"></a>Microsoft のトピックの検出を管理するトピック

トピック検出の設定は [、Microsoft 365 管理センターで管理できます](https://admin.microsoft.com)。 これらのタスクを実行するには、全体管理者または SharePoint 管理者である必要があります。

## <a name="to-access-topics-management-settings"></a>トピックの管理設定にアクセスするには:

1. Microsoft 365 管理センターで、[設定] をクリックし、[組織の設定]**をクリックします**。
2. [サービス] **タブで** 、[トピックエクスペリエンス] **をクリックします**。

    ![ユーザーを知識に接続する](../media/admin-org-knowledge-options-completed.png) 

3. [トピックの **検出] タブを選択** します。各設定の詳細については、以下のセクションを参照してください。

    ![knowledge-network-settings](../media/knowledge-network-settings-topic-discovery.png) 

## <a name="select-sharepoint-topic-sources"></a>SharePoint トピック ソースの選択

トピックをクロールする組織内の SharePoint サイトを変更できます。

サイトの特定のリストを含める、または除外する場合は、次の .csv テンプレートを使用できます。

``` csv
Site name,URL
```

サイト ピッカーを使用してサイトを追加すると、既存のサイト一覧に追加され、追加または除外されます。 .csv ファイルをアップロードすると、既存のリストが上書きされます。 以前に特定のサイトを含めるか除外した場合は、リストを .csv ファイルとしてダウンロードし、変更を加え、新しいリストをアップロードします。

トピック検出用のサイトを選択するには

1. [トピックの **検出]** タブの **[SharePoint** トピック ソースの選択] で、[編集] を **選択します**。
2. **[SharePoint トピック ソース** の選択] ページで、検出時にトピックのソースとしてクロールする SharePoint サイトを選択します。 これには以下が含まれます。
    - **すべてのサイト**: テナント内のすべての SharePoint サイト。 これにより、現在および将来のサイトがキャプチャされます。
    - **すべて (選択したサイトを** 除く): 除外するサイトの名前を入力します。  検出からオプトアウトするサイトの一覧をアップロードできます。 今後作成されるサイトは、トピック検出のソースとして含まれる予定です。 
    - **選択したサイト** のみ: 含めるサイトの名前を入力します。 サイトの一覧をアップロードできます。 将来作成されるサイトは、トピック検出のソースとして含まれません。
    - **サイトなし**: トピックは SharePoint コンテンツで自動的に生成または更新されません。 既存のトピックはトピック センターに残ります。

    ![SharePoint トピック ソースのユーザー インターフェイスのスクリーンショット](../media/k-manage-select-topic-source.png)
   
3. **[保存]** をクリックします。

## <a name="exclude-topics-by-name"></a>名前でトピックを除外する

.csv ファイルを使用してリストをアップロードすることで、検出からトピックを除外できます。 トピックを以前に除外した場合は、.csv をダウンロードし、変更を加え、もう一度アップロードできます。

1. [トピックの **検出] タブの** [除外] **トピックで**、[編集] を **選択します**。
2. [名前 **でトピックを除外する] をクリックします**。
3. リストを作成する必要がある場合は、.csv テンプレートをダウンロードし、除外するトピックを追加します (以下の *.csv* テンプレートの操作を参照してください)。 ファイルの準備ができたら、[参照] をクリック **して** ファイルをアップロードします。 既存のリストがある場合は、リストを含む .csv をダウンロードできます。
4. **[保存]** をクリックします。

    ![除外トピックのユーザー インターフェイスのスクリーンショット](../media/km-manage-exclude-topics.png)

### <a name="working-with-the-csv-template"></a>.csv テンプレートを操作する

csv テンプレートは、次の場所にコピーできます。

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

CSV テンプレートで、除外するトピックに関する次の情報を入力します。

- **[名前**]: 除外するトピックの名前を入力します。 これを行うには 2 つの方法があります。
    - 完全一致: 正確な名前または頭字語 *(Contoso* や ATL など) *を含めできます*。
    - 部分一致: 特定の単語を含むすべてのトピックを除外できます。  たとえば、円弧 *には*、円弧、円弧の円弧、トレーニング用の円弧など、その中に円弧を含むすべてのトピック *が除外されます*。 Architecture など、単語の一部としてテキストが含まれるトピックは除外されない点に注意 *してください*。
- **略語 (省略可能)**: 頭字語を除外する場合は、略語の略語を入力します。
- **MatchType-Exact/Partial**: 入力した名前が完全一致型か部分一致型 *かを入力します*。

    ![CSV テンプレートでトピックを除外する](../media/exclude-topics-csv.png) 

## <a name="see-also"></a>関連項目

[Microsoft 365 でトピックの表示を管理する](topic-experiences-knowledge-rules.md)

[Microsoft 365 でトピックのアクセス許可を管理する](topic-experiences-user-permissions.md)

[Microsoft 365 のトピック センターの名前を変更する](topic-experiences-administration.md)
