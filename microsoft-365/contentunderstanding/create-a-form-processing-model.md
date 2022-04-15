---
title: Microsoft SharePoint Syntex でフォーム処理モデルを作成する
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
ms.custom: admindeeplinkSPO
ms.localizationpriority: medium
description: SharePoint Syntex でフォーム処理モデルを作成する方法について説明します。
ms.openlocfilehash: 3eb14a76bd597f1f382b87813c7e4bd2a4518e19
ms.sourcegitcommit: 23e186b46b27a6a4863f507a52a11105afae9726
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/15/2022
ms.locfileid: "64882354"
---
# <a name="create-a-form-processing-model-in-microsoft-sharepoint-syntex"></a>Microsoft SharePoint Syntex でフォーム処理モデルを作成する

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GnhN]  

</br>

Microsoft PowerApps の機能である [AI ビルダー](/ai-builder/overview)を使用すると、SharePoint Syntex のユーザーは SharePoint ドキュメント ライブラリから直接[フォーム処理モデル](form-processing-overview.md)を作成できます。 

フォーム処理モデルの作成には、次の手順が含まれます。

 - [手順 1: フォーム処理モデルを作成する](create-a-form-processing-model.md#step-1-create-a-form-processing-model)
 - [手順 2: ドキュメントを追加して分析する](create-a-form-processing-model.md#step-2-add-and-analyze-documents)
 - [手順 3: フィールドとテーブルをタグ付けする](create-a-form-processing-model.md#step-3-tag-fields-and-tables)
 - [手順 4: モデルをトレーニングして発行する](create-a-form-processing-model.md#step-4-train-and-publish-your-model)
 - [手順 5: モデルを使用する](create-a-form-processing-model.md#step-5-use-your-model)

## <a name="requirements"></a>要件

フォーム処理モデルの作成は、それが有効になっている SharePoint ドキュメント ライブラリでのみ実行できます。 フォーム処理が有効になっている場合は、ドキュメント ライブラリに **[自動化]** > **[AI ビルダー]** > **[フォームを処理するモデルの作成]** メニューが表示されます。 ドキュメント ライブラリで処理を有効にする必要がある場合は、SharePoint 管理者にお問い合わせください。

 ![AI ビルダー モデルを示すスクリーンショット。](../media/content-understanding/create-ai-builder-model2.png)

## <a name="step-1-create-a-form-processing-model"></a>手順 1: フォーム処理モデルを作成する

フォーム処理モデルを作成する最初の手順は、モデルに名前を付け、新しいコンテンツ タイプを定義して、そのための新しいドキュメント ライブラリ ビューを作成することです。

1. ドキュメント ライブラリで、**[自動化]** メニュー、**[AI ビルダー]**、**[フォームを処理するモデルの作成]** の順に選択します。

    ![[自動化] メニューと [フォームを処理するモデルの作成] オプションを示すスクリーンショット。](../media/content-understanding/create-ai-builder-model2.png)

2. **[フォームを処理するモデルの作成]** パネルで、**[名前]** フィールドにモデルの名前を入力します (*「発注書」* など)。

    ![[フォームを処理するモデルの作成] パネルを示すスクリーンショット。](../media/content-understanding/new-form-model2.png) 

3. これで、SharePoint ドキュメント ライブラリ内にある同じようなレイアウト (請求書や税務書類など) を共有する構造化ファイルの *コレクション* から、情報を自動的に抽出して保存できるようになります。 これにより、複数のモデルを 1 つのモデルとして作成し、特定のテーブルのアイテムの情報を抽出できます。

   コレクション名は、モデルが適用されるドキュメント ライブラリの専用列に保存されます。これにより、同じモデルによって処理される異なるファイル レイアウトを区別できます。

   さらに、抽出されたテーブルの情報は指定されたリストに保存され、アップロードされたファイルと関連付けられるため、簡単に表示し、ビジネス プロセスの自動化をさらに行うことができます。

   関連付けられているリストにテーブルの情報を抽出するには、次の操作を実行します。<br><br>

     1. **[テーブルから情報を抽出しますか?]** セクションで、**[はい]** を選択します。

      ![[フォームを処理するモデルの作成] パネルの [テーブルから情報を抽出しますか?] セクションを示すスクリーンショット。](../media/content-understanding/extract-info-from-tables.png) 

     2. **[テーブルの情報をどこに保存しますか?]** セクションで、次の操作を実行します。
 
        - **[新しいリスト]** (既定の設定) を選択すると、**[新しいリストの名前]** ボックスに名前の候補が自動的に提供されます。 名前は必要に応じて変更できます。 サイト ナビゲーションにリストを表示する場合、**[サイト ナビゲーションに表示する]** チェックボックスをオンにします。

        - **[選択したリスト]** ボックスで **[既存のリスト]** を選択した場合、使用するリストを選択します。

4. フォーム処理モデルを作成する場合は、新しい SharePoint コンテンツタイプを作成します。 SharePointコンテンツタイプは、共通の特徴を持つドキュメントのカテゴリを表し、特定のコンテンツの列またはメタデータプロパティのコレクションを共有します。 SharePointコンテンツ タイプは<a href="https://go.microsoft.com/fwlink/?linkid=2185219" target="_blank">、SharePoint管理センター</a>を通じて管理されます。

   このモデルを SharePoint コンテンツ タイプ ギャラリーの既存のコンテンツ タイプにマッピングするには、**[詳細設定]** を選択します。

    ![[フォームを処理するモデルの作成] パネルの [詳細設定] を示すスクリーンショット。](../media/content-understanding/new-form-model-advanced-settings.png) 

   1. <a href="https://go.microsoft.com/fwlink/?linkid=2185074" target="_blank">コンテンツ タイプ ギャラリー</a>で、新しいコンテンツ タイプを作成するか、既存のコンテンツ タイプを使用するかを選択します。 

   2. 既存のコンテンツ タイプを使用するには、**[いずれかを選択]** を選択して、リストからコンテンツ タイプを選択します。

   3. モデルは、ドキュメント ライブラリに抽出されたデータの新しいビューを作成します。 既定のビューを使用しない場合は、**[このモデルのライブラリ ビュー]** セクションで、**[ビューを既定として設定]** チェックボックスをオフにします。

   4. ファイルに保持ラベルを適用するには、**[保持ラベル]** セクションで、使用する保持ラベルを選択します。

5. **[作成]** を選択します。

## <a name="step-2-add-and-analyze-documents"></a>手順 2: ドキュメントを追加して分析する

新しいフォーム処理モデルを作成すると、ブラウザーに新しい PowerApps AI ビルダーフォームプロセスモデルページが開きます。 このページでは、サンプル ドキュメントを追加して分析できます。 

> [!NOTE]
> 使用するサンプル ファイルを探す場合、「[フォーム処理モデルの要件と最適化のヒント](/ai-builder/form-processing-model-requirements)」を参照してください。 
 
1. 最初に、**[抽出する情報の選択]** ページで、モデルの抽出対象に設定するフィールドおよびテーブルを定義します。 詳細な手順については、「[抽出するフィールドとテーブルを定義する](/ai-builder/create-form-processing-model#define-fields-and-tables-to-extract)」を参照してください。 

2.  モデルが処理するドキュメント レイアウトのコレクションは、必要なだけ作成することができます。 詳細な手順については、「[コレクションごとにドキュメントをグループ化する](/ai-builder/create-form-processing-model#group-documents-by-collections)」を参照してください。 

3. コレクションを作成し、それぞれにサンプル ファイルを追加したら、AI ビルダーはフィールドとテーブルを検出するためにアップロードされたドキュメントを確認します。 これには、通常、数分かかります。 分析が完了したら、ドキュメントのタグ付けに進むことができます。

## <a name="step-3-tag-fields-and-tables"></a>手順 3: フィールドとテーブルをタグ付けする

モデルが抽出するフィールドとテーブル データを理解するよう設定するため、ドキュメントをタグ付けする必要があります。 詳細な手順については、「[ドキュメントにタグを付ける](/ai-builder/create-form-processing-model#tag-documents)」を参照してください。

## <a name="step-4-train-and-publish-your-model"></a>手順 4: モデルをトレーニングして発行する

1. モデルを作成してトレーニングしたら、発行して SharePoint で使用できます。 詳細な手順については、「[フォーム処理モデルをトレーニングして発行する](/ai-builder/form-processing-train)」を参照してください。 

2. モデルを発行したら、**[モデルを使用]**、**[フローを作成]** の順に選択します。 これにより、SharePoint ドキュメント ライブラリで実行し、モデルで識別されたフィールドを抽出できる Power Automate フローが作成されます。

    ![[フローを作成] パネルを示す AI ビルダーのスクリーンショット。](../media/content-understanding/ai-builder-create-a-flow.png)
 
3. 完了すると、*"フローが正常に作成されました"* のメッセージが表示されます。

    ![フローが正常に作成されたことを示す AI ビルダーのスクリーンショット。](../media/content-understanding/ai-builder-flow-created.png)

4. **[SharePoint に移動]** ボタンを選択して、モデルで更新されたドキュメント ライブラリを表示します。

## <a name="step-5-use-your-model"></a>手順 5: モデルを使用する

1. [ドキュメント ライブラリ モデル] ビューで、選択したフィールドが列として表示されるようになりました。

    ![ドキュメント ライブラリ モデルが適用されました。](../media/content-understanding/doc-lib-view.png)

2. **[ドキュメント]** の横にある [情報] リンクで、フォーム処理モデルがこのドキュメント ライブラリに適用されていることが示されています。

    ![[情報] ボタン。](../media/content-understanding/info-button.png)  

3. ファイルをドキュメント ライブラリにアップロードします。 モデルがコンテンツ タイプとして識別するファイルには、ビュー内のファイルが一覧表示され、列に抽出されたデータが表示されます。

    ![[完了]。](../media/content-understanding/doc-lib-done.png) 

> [!NOTE]
> カスタム フォーム処理モデルとドキュメント理解モデルが同じライブラリに適用されている場合、ファイルはドキュメント理解モデルとそのモデルのトレーニング済みエクストラクターを使用して分類されます。 フォーム処理モデルに一致する空の列がある場合は、抽出された値を使用して列が設定されます。

### <a name="use-flows-to-extract-information"></a>フローを使用して情報を抽出する

2 つのフローを使用して、フォーム処理モデルが適用されているライブラリ内の選択したファイルまたはファイルのバッチを処理できます。

- **フォーム処理モデルを使用して画像または PDF ファイルから情報を抽出する - フォーム処理モデル** を実行して、選択した画像または PDF ファイルからテキストを抽出するために使用します。 一度に 1 つの選択されたファイルをサポートし、PDF ファイルと画像ファイル (PNG、JPG、JPEG) のみをサポートします。 フローを実行するには、ファイルを選択し、**AutomateExtract** >  情報を選択します。

    ![[抽出情報] が強調表示された [自動化] メニューを示すスクリーンショット。](../media/content-understanding/automate-extract-info.png)  

- **フォーム処理モデルを使用してファイルから情報を抽出する - フォーム処理** モデルと共に使用して、ファイルのバッチから情報を読み取り、抽出します。 一度に最大 5,000 個のSharePoint ファイルを処理します。 このフローを実行すると、特定のパラメーターを設定できます。 次の操作を行うことができます:

    - 以前に処理されたファイルを含めるかどうかを選択します (既定では、以前に処理されたファイルは含まれません)。
    - 処理するファイルの数を選択します (既定値は 100 ファイルです)。
    - ファイルを処理する順序を指定します (選択できるのは、ファイル ID、ファイル名、ファイルの作成時刻、または最終変更時刻です)。
    - 順序を並べ替える方法 (昇順または降順) を指定します。

    ![パラメーター オプションが強調表示された [実行フロー] パネルを示すスクリーンショット。](../media/content-understanding/run-flow-panel.png)  

### <a name="classification-date-field"></a>[分類日] フィールド

SharePoint Syntexフォーム処理モデル (またはドキュメント理解モデル) をドキュメント ライブラリに適用すると、**分類日** フィールドがライブラリ スキーマに含まれます。 既定では、このフィールドは空です。 ただし、ドキュメントがモデルによって処理および分類されると、このフィールドは完了の日付/時刻スタンプで更新されます。 

モデルに **分類日** がスタンプされている場合は、**ファイル フローを処理SharePoint Syntex後に電子メールを送信** するを使用して、SharePoint ドキュメント ライブラリ内のモデルによって新しいファイルが処理され、分類されたことをユーザーに通知できます。

フローを実行するには:

1. ファイルを選択し、[**統合** > ] を選択 **Power Automate** > **フローを作成** します。

2. [**フローの作成**] パネルで、**ファイルを処理した後SharePoint Syntex [電子メールの送信**] を選択します。

    ![[フロー パネルとフローの作成] オプションが強調表示されているスクリーンショット。](../media/content-understanding/integrate-create-flow.png) 

## <a name="see-also"></a>関連項目
  
[Power 自動化 ドキュメント](/power-automate/)

[トレーニング: AI ビルダーを使用してビジネスの実績を高める](/learn/paths/improve-business-performance-ai-builder/?source=learn)