---
title: Microsoft SharePoint Syntexのドキュメント理解モデルを適用する
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: Microsoft SharePoint SyntexのSharePoint ドキュメント ライブラリに公開済みのモデルを適用する方法について説明します。
ms.openlocfilehash: 6be3a1b0badaecf1196545c313adcce51f3d2b55
ms.sourcegitcommit: 46e796c6b76a01516c48977335bbf5076ca74a06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2022
ms.locfileid: "64738474"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a>Microsoft SharePoint Syntexのドキュメント理解モデルを適用する

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

ドキュメント理解モデルを発行した後、Microsoft 365 テナント内の 1 つ以上のSharePointドキュメント ライブラリに適用できます。

> [!NOTE]
> ユーザーがアクセスできるドキュメントライブラリにのみモデルを適用できます。


## <a name="apply-your-model-to-a-document-library"></a>ドキュメント ライブラリにモデルを適用する

SharePoint ドキュメント ライブラリにモデルを適用するには:

1. モデルのホーム ページの [ **モデルをライブラリに適用** ] タイルで、[ **モデルの適用**] を選択します。 または、[ **モデルの適用場所] セクションで** 、[ **+ライブラリの追加]** を選択します。

    ![[ライブラリの追加] オプションが強調表示されている [モデルの適用場所] セクションのスクリーンショット。](../media/content-understanding/apply-to-library.png)

2. モデルを適用するドキュメントライブラリが含まれている SharePoint サイトを選択できます。 サイトが一覧に表示されない場合は、検索ボックスを使用して検索します。

    ![サイトを選択します。](../media/content-understanding/site-search.png)

    > [!NOTE]
    > モデルを適用しようとしているドキュメントライブラリへの *リスト管理* 許可を持っているかまたは、*編集* 権限を持っていなければなりません。

3. サイトを選択した後、モデルを適用するドキュメントライブラリを選択します。 このサンプルでは、*Contoso ケーストラッキング* サイトから *ドキュメント* ドキュメントライブラリ を選びます。

    ![ドキュメントライブラリを選択します。](../media/content-understanding/select-doc-library.png)

4. モデルはコンテンツ タイプに関連付けられているため、ライブラリに適用すると、コンテンツ タイプが追加され、抽出したラベルが列として表示された既定のビューが更新されます。 ただし、[ **詳細設定** ] を選択して、必要に応じて、現在のライブラリ ビューを保持するか、モデル情報とファイル サムネイルを含む新しいビューを使用するかを選択できます。 現在のライブラリ ビューを保持することを選択した場合、モデル情報を含む新しいビューは、ライブラリのビュー メニューで引き続き使用できます。

    ![ライブラリ ビューを示す詳細設定のスクリーンショット。](../media/content-understanding/library-view.png)

    詳細については、この記事 [の後半の「ドキュメント ライブラリのビューを変更](#change-the-view-in-a-document-library) する」を参照してください。

5. モデルをライブラリに適用するには、[ **追加** ] を選択します。

6. モデルのホーム ページの [**モデルの適用場所]** セクションに、SharePoint サイトの名前が一覧表示されます。

7. ドキュメントライブラリに移動し、モデルのドキュメントライブラリビューに移動していることを確認します。 **AutomateView** >  **ドキュメント理解モデル** を選択します。

8. [ **モデルのレビューと新しいモデルの適用** ] ページで、[ **適用]** タブを選択して、ドキュメント ライブラリに適用されるモデルを表示します。

    ![[適用済み] タブが選択され、適用されたモデルを示すスクリーンショット。](../media/content-understanding/applied-models.png) 

9. モデル **の詳細の表示** を選択して、モデルの説明、モデルを公開したユーザー、モデルが分類するファイルに保持ラベルまたは秘密度ラベルを適用するかどうかなど、モデルに関する情報を表示します。

モデルをドキュメントライブラリに適用したら、サイトにドキュメントをアップロードし、結果を確認できます。

モデルは、モデルに関連付けられているコンテンツ タイプを持つすべてのファイルとフォルダーを識別し、それらをビューに一覧表示します。 モデルに抽出器がある場合は、各ファイルまたはフォルダーから抽出するデータの列がビューに表示されます。

> [!NOTE]
> 2 つ以上のドキュメント理解モデルが同じライブラリに適用されている場合、アップロードされたファイルは、平均信頼度スコアが最も高いモデルを使用して分類されます。 抽出されたエンティティは、適用されたモデルからのみ取得されます。 <br><br>カスタム フォーム処理モデルとドキュメント理解モデルが同じライブラリに適用されている場合、ファイルはドキュメント理解モデルとそのモデルのトレーニング済みエクストラクターを使用して分類されます。 フォーム処理モデルに一致する空の列がある場合は、抽出された値を使用して列が設定されます。

## <a name="sync-changes-to-one-or-more-libraries"></a>変更を 1 つ以上のライブラリに同期する

モデルを複数のドキュメント ライブラリに発行し、抽出器の追加や削除など、モデルを更新する場合は、モデルが適用されているすべてのライブラリに更新をプッシュする必要があります。

適用されたすべてのライブラリに対する変更を同期するには:

1. モデルのホーム ページの [ **モデルの適用場所** ] セクションで、[ **すべて同期**] を選択します。

    ![[モデルの適用場所] セクションと [すべて同期] ボタンが強調表示されているスクリーンショット。](../media/content-understanding/sync-all-button.png) 

選択した 1 つまたは複数のライブラリに対する変更を同期するには:

1. モデルのホーム ページの [ **モデルの適用場所** ] セクションで、変更を適用するライブラリを選択します。

2. [**同期**] を選択します。

    ![[モデルの適用場所] セクションと [同期] ボタンが強調表示されているスクリーンショット。](../media/content-understanding/sync-button.png) 

## <a name="apply-the-model-to-files-and-folder-content-already-in-the-document-library"></a>ドキュメント ライブラリに既に存在するファイルとフォルダーのコンテンツにモデルを適用する

適用されたモデルは、適用後にドキュメント ライブラリにアップロードされたすべてのファイルとフォルダー コンテンツを処理しますが、モデルが適用される前にドキュメント ライブラリに既に存在するファイルとフォルダー コンテンツに対してモデルを実行するために、次の操作を実行することもできます。

1. ドキュメント ライブラリで、モデルで処理するファイルとフォルダーを選択します。

2. ファイルとフォルダーを選択すると、 **分類と抽出** がドキュメント ライブラリのリボンに表示されます。 **分類および抽出** を選択します。

      ![[分類と抽出] オプションを示すスクリーンショット。](../media/content-understanding/extract-classify.png) 

3. 選択したファイルとフォルダーが、処理するキューに追加されます。

    > [!NOTE]
    > 分類にかかる時間を示すメッセージが表示されます。 ファイルのみを選択した場合、分類には最大 30 分かかる場合があります。 1 つ以上のフォルダーを選択した場合、分類には最大 24 時間かかる場合があります。

### <a name="classification-date-field"></a>[分類日] フィールド

SharePoint Syntexドキュメント理解モデル (またはフォーム処理モデル) がドキュメント ライブラリに適用されると、**分類日** フィールドがライブラリ スキーマに含まれます。 既定では、このフィールドは空です。 ただし、ドキュメントがモデルによって処理および分類されると、このフィールドは完了の日付/時刻スタンプで更新されます。 

   ![[分類日] 列を示すドキュメント ライブラリのスクリーンショット。](../media/content-understanding/class-date-column.png) 

**[分類日]** フィールド [**は、ファイルがコンテンツ理解モデル トリガーによって分類されたときに、モデルがファイル**](/connectors/sharepointonline/#when-a-file-is-classified-by-a-content-understanding-model)またはフォルダーの内容の処理を完了し、[**分類日**] フィールドを更新した後に、Power Automate フローを実行するために使用されます。

   ![トリガー Flow。](../media/content-understanding/trigger.png)

**その後、コンテンツ理解モデル トリガーによってファイルが分類されたとき** は、ファイルまたはフォルダーから抽出された情報を使用してフローを開始できます。

たとえば、モデルに **分類日** がスタンプされている場合は、**ファイル フローを処理SharePoint Syntex後に電子メールを送信** するを使用して、SharePoint ドキュメント ライブラリ内のモデルによって新しいファイルが処理および分類されたことをユーザーに通知できます。

フローを実行するには:

1. ファイルを選択し、[**統合** > ] を選択 **Power Automate** > **フローを作成** します。

2. [**フローの作成**] パネルで、**ファイルを処理した後SharePoint Syntex [電子メールの送信**] を選択します。

    ![[フロー パネルとフローの作成] オプションが強調表示されているスクリーンショット。](../media/content-understanding/integrate-create-flow.png) 

## <a name="change-the-view-in-a-document-library"></a>ドキュメント ライブラリのビューを変更する

[!INCLUDE [Change the view in a document library](../includes/change-library-view.md)]

## <a name="see-also"></a>関連項目

[分類子を作成する](create-a-classifier.md)

[エクストラクターを作成する](create-an-extractor.md)

[ドキュメント理解の概要](document-understanding-overview.md)
