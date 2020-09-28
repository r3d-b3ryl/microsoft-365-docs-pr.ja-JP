---
title: フォーム処理モデルを作成する
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft SharePoint の同期 Tex でフォーム処理モデルを作成します。
ms.openlocfilehash: f61dbad837173c412daefb7285c4abff10a01817
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295480"
---
# <a name="create-a-form-processing-model-in-microsoft-sharepoint-syntex"></a>Microsoft SharePoint の同期 Tex でフォーム処理モデルを作成する

この記事の内容は、Project Cortex のプライベートプレビュー用です。 [詳細については、「Project Cortex](https://aka.ms/projectcortex)」を参照してください。

[AI ビルダー](https://docs.microsoft.com/ai-builder/overview)を使用する-Microsoft PowerApps のフィーチャー-プロジェクト cortex ユーザーは、SharePoint ドキュメントライブラリから直接[フォーム処理モデル](form-processing-overview.md)を作成できます。 

フォーム処理モデルを作成するには、以下の作業を行います。
 - 手順 1: コンテンツタイプを作成するための from 処理モデルを作成する
 - 手順 2: サンプルファイルを追加して分析する
 - 手順 3: フォームフィールドを選択する
 - 手順 4: モデルをトレーニングおよびテストする
 - 手順 5: モデルを発行する
 - 手順 6: モデルを使用する

## <a name="requirements"></a>Requirements

フォーム処理モデルは、それが有効になっている SharePoint ドキュメントライブラリでのみ作成できます。 フォーム処理が有効になっている場合は、ドキュメントライブラリの [**自動化**] メニューの [**フォーム処理モデルを作成**する] という**AI ビルダー**が表示されます。  ドキュメントライブラリで処理を有効にする必要がある場合は、SharePoint 管理者に連絡する必要があります。

 ![AI ビルダーモデルを作成する](../media/content-understanding/create-ai-builder-model.png)</br>

## <a name="step-1-create-a-form-processing-model"></a>手順 1: フォーム処理モデルを作成する

フォーム処理モデルを作成する最初の手順は、その名前を作成して、新しいコンテンツタイプを定義し、それに対応する新しいドキュメントライブラリビューを作成することです。

1. ドキュメントライブラリで、[ **自動化** ] メニューの [ **AI ビルダー**] を選択し、[ **フォーム処理モデルの作成**] を選択します。

    ![モデルを作成する](../media/content-understanding/create-ai-builder-model.png)</br>

2. [ **新しいフォーム処理モデル** ] ウィンドウの [  **名前** ] フィールドに、モデルの名前を入力します (例: *発注書*)。

    ![新しいフォーム処理モデル](../media/content-understanding/new-form-model.png)</br> 

3. フォーム処理モデルを作成する場合は、新しい SharePoint コンテンツタイプを作成します。 SharePoint コンテンツタイプは、共通の特性を持つドキュメントのカテゴリを表し、その特定のコンテンツの列またはメタデータプロパティのコレクションを共有します。 SharePoint コンテンツタイプは、 [コンテンツタイプギャラリー]()を使用して管理されます。

    このモデルを SharePoint コンテンツタイプギャラリーの既存のコンテンツタイプにマッピングして、そのスキーマを使用する場合は、[ **詳細設定** ] を選択します。 

4. モデルでは、抽出したデータ用のドキュメントライブラリに新しいビューを作成します。 これを既定のビューにしない場合は、[ **既定としてビューを設定**する] をオフにします。

5. **[作成]** を選択します。

## <a name="step-2-add-and-analyze-documents"></a>手順 2: ドキュメントを追加して分析する

新しいフォーム処理モデルを作成すると、ブラウザーに新しい PowerApps AI ビルダーフォーム処理モデルページが表示されます。 このページでは、サンプルドキュメントを追加して分析することができます。 </br>

> [!NOTE]
> 使用するファイルの例については、「 [フォーム処理モデルの入力文書の要件」と「最適化のヒント](https://docs.microsoft.com/ai-builder/form-processing-model-requirements)」を参照してください。 

   ![Power Apps AI ビルダー](../media/content-understanding/powerapps.png)</br> 
 
1. [ **ドキュメントの追加** ] を選択して、分析するサンプルドキュメントの追加を開始し、抽出できる名前付きの値のペアを決定します。 その後、[ローカルストレージ、 **SharePoint**、または**Azure Blob ストレージ****からのアップロード**] を選択できます。 トレーニングには、少なくとも5つのファイルを使用する必要があります。

2. ファイルを追加した後、[ **分析** ] を選択して、よく使用される情報がすべてファイルであるかどうかを確認します。 この処理が完了するまで数分かかる場合があります。</br> 
 
    ![ファイルを分析する](../media/content-understanding/analyze.png)</br> 

3. ファイルを分析した後、 **[保存するフォームフィールドを選択** してください] ページでファイルを選択して、検出されたフィールドを表示します。</br>

    ![フォームフィールドの選択](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a>手順 3: フォームフィールドを選択する

フィールドのドキュメントを分析した後、検索されたフィールドを確認し、保存するフィールドを識別できるようになりました。 保存されたフィールドは、モデルのドキュメントライブラリビューで列として表示され、各ドキュメントから抽出された値を表示します。

1. 次のページには、サンプルファイルの1つが表示され、システムによって自動的に検出されたすべての共通フィールドが強調表示されます。 </br>

    ![[フィールドの選択] ページ](../media/content-understanding/select-fields-page.png)</br> 

2. 保存するフィールドを選択して、選択内容を確認するチェックボックスをオンにします。 たとえば、[購入注文] モデルでは、 *日付*、 *PO*、および *集計* フィールドを選択します。  また、選択した場合は、フィールドの名前を変更することもできます。 </br>

    ![PO の選択#](../media/content-understanding/po.png)</br> 

3. 分析でフィールドが検出されなかった場合でも、追加することを選択できます。 抽出する情報を選択し、[名前] ボックスに目的の名前を入力します。 次に、チェックボックスをオンにします。 その他のサンプルファイルの検出されていないフィールドを確認する必要があることに注意してください。

4. 保存するフィールドを選択したら、[ **フィールドの確認** ] をクリックします。 </br>
 
    ![フィールドを選択した後にフィールドを確認する](../media/content-understanding/confirm-fields.png)</br> 
 
5. [ **保存するフォームフィールドを選択** してください] ページで、選択したフィールドの数が表示されます。 [**完了**] を選択します。

## <a name="step-4-train-and-test-your-model"></a>手順 4: モデルをトレーニングおよびテストする

保存するフィールドを選択すると、[ **モデルの概要** ] ページでモデルのトレーニングとテストを行うことができます。

1. [ **モデルの概要** ] ページの [ **選択したフィールド** ] セクションに、保存したフィールドが表示されます。 サンプルファイルのトレーニングを開始するには、[ **Train** ] を選択します。 この処理が完了するまで数分かかる場合があることに注意してください。</br>

     ![フィールドを選択する列車](../media/content-understanding/select-fields-train.png)</br> 

2. トレーニングが完了したことを示す通知が表示されたら、[ **詳細ページに移動**] を選択します。 

3. [ **モデルの詳細** ] ページで、[ **クイックテスト**] を選択してモデルの動作をテストできます。 これにより、ファイルをページにドラッグアンドドロップして、フィールドが検出されたかどうかを確認できます。

    ![確認フィールド](../media/content-understanding/select-fields-train.png)</br> 

2. トレーニングが完了したことを示す通知が表示されたら、[ **詳細ページに移動**] を選択します。 

3. [ **モデルの詳細** ] ページで、[ **クイックテスト**] を選択してモデルの動作をテストします。 これにより、ファイルをページにドラッグアンドドロップして、フィールドが検出されたかどうかを確認できます。

## <a name="step-5-publish-your-model"></a>手順 5: モデルを発行する

1. モデルの結果に問題がなければ、[ **発行** ] を選択して使用できるようにします。

2. モデルが公開されたら、[ **Use model**] を選択します。 これにより、SharePoint ドキュメントライブラリで実行してモデルで識別されたフィールドを抽出し、[ **フローの作成**] を選択することができる powerautomate フローが作成されます。
  
3. 完了すると、 **フローが正常に作成され**たことをメッセージが表示されます。
 
## <a name="step-6-use-your-model"></a>手順 6: モデルを使用する

モデルを発行して、そのモデルの PowerAutomate フローを作成した後、モデルを SharePoint ドキュメントライブラリで使用できます。

1. モデルを公開した後、[ **SharePoint に移動** ] を選択してドキュメントライブラリに移動します。

2. [ドキュメントライブラリモデル] ビューで、選択したフィールドが列として表示されることに注意してください。</br>

    ![ドキュメントライブラリモデルの適用](../media/content-understanding/doc-lib-view.png)</br> 

3. **ドキュメント**の横の情報リンクは、フォーム処理モデルがこのドキュメントライブラリに適用されていることに注意してください。

    ![[情報] ボタン](../media/content-understanding/info-button.png)</br>  

4. ファイルをドキュメントライブラリにアップロードします。 モデルがコンテンツタイプとして識別するすべてのファイルは、ビュー内のファイルを一覧表示して、列に抽出されたデータを表示します。</br>

    ![完了](../media/content-understanding/doc-lib-done.png)</br>  

## <a name="see-also"></a>関連項目
  
[電力の自動化に関するドキュメント](https://docs.microsoft.com/power-automate/)</br>
[トレーニング: AI ビルダーを使用してビジネスパフォーマンスを向上させる](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
