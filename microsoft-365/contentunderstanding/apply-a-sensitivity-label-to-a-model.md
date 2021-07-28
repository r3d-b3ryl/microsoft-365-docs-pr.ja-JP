---
title: Microsoft SharePoint Syntex のモデルに秘密度ラベルを適用する
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
localization_priority: Priority
description: 秘密度ラベルを SharePoint Syntex のモデルに適用する方法について説明します。
ms.openlocfilehash: 2e6fc51db228ac4beb7171047478b0132c1194f5
ms.sourcegitcommit: 60cc1b2828b1e191f30ca439b97e5a38f48c5169
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2021
ms.locfileid: "53543175"
---
# <a name="apply-a-sensitivity-label-to-a-model-in-microsoft-sharepoint-syntex"></a>Microsoft SharePoint Syntex のモデルに秘密度ラベルを適用する

Microsoft SharePoint Syntex のドキュメント理解モデルに[秘密度ラベル](../compliance/sensitivity-labels.md)を簡単に適用できます。 この機能は、フォーム処理モデルではまだ利用できません。

秘密度ラベルを使用すると、モデルが識別するドキュメントに暗号化、共有、および条件付きアクセス ポリシーを適用できます。 たとえば、ドキュメント ライブラリにアップロードされた銀行口座番号やクレジット カード番号を含む財務書類をモデルで識別するだけでなく、それらに *暗号化* 秘密度ラベルを適用して、そのコンテンツにアクセスできるユーザーとそのコンテンツの使用方法を制限することも必要です。 SharePoint Syntex モデルは[ラベルの順序](../compliance/apply-sensitivity-label-automatically.md#how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label)規則を尊重し、ユーザーがファイルに手動で適用した既存のラベルを上書きしません。 

モデルのホーム ページのモデル設定を使用して、既存の秘密度ラベルをモデルに適用できます。 モデル設定から選択できるようにするには、ラベルがすでに公開されている必要があります。

> [!Important]
> 秘密度ラベルをドキュメント理解モデルに適用できるようにするには、秘密度ラベルを[作成して Microsoft 365 コンプライアンス センターで公開する](../business-video/create-sensitivity-labels.md)必要があります。

## <a name="add-a-sensitivity-label-to-a-document-understanding-model"></a>秘密度ラベルをドキュメント理解モデルに追加する

1. モデルのホーム ページから、[**モデルの設定**] を選択します。

   ![[モデルの設定] オプションが強調表示された [モデル] ページのスクリーンショット。](../media/content-understanding/sensitivity-model-settings.png)

2. [**モデルの設定**] ウィンドウの [**コンプライアンス**] セクションで、[**秘密度ラベル**] メニューを選択して、モデルに適用できる秘密度ラベルのリストを表示します。

   ![秘密度ラベル メニューが表示されている [モデルの設定] ウィンドウのスクリーンショット。](../media/content-understanding/sensitivity-model-settings-pane.png) 

3. モデルに適用する秘密度ラベルを選択し、[**保存**] を選択します。

モデルに秘密度ラベルを適用した後、次のものに適用できます。

- 新しいドキュメント ライブラリ
- モデルがすでに適用されているドキュメント ライブラリ
 
### <a name="apply-the-sensitivity-label-to-a-document-library-to-which-the-model-is-already-applied"></a>モデルがすでに適用されているドキュメント ライブラリに秘密度ラベルを適用します

ドキュメント理解モデルがすでにドキュメント ライブラリに適用されている場合は、次の手順を実行して、秘密度ラベルの更新を同期し、ドキュメント ライブラリに適用できます。

1. モデル ホーム ページの [**このモデルのあるライブラリ**] セクションで、秘密度ラベルの更新を適用するドキュメント ライブラリを選択します。

2. [**同期**] を選択します。

   ![[同期] が強調表示された [このモデルのあるライブラリ] セクションを示すスクリーンショット。](../media/content-understanding/sensitivity-libraries-sync.png)

更新を適用してモデルに同期した後、次の手順を実行して、更新が適用されたことを確認できます。

1. コンテンツ センターの [**このモデルのあるライブラリ**] セクションで、更新したモデルが適用されたライブラリを選択します。 

2. ドキュメント ライブラリ ビューで、情報アイコンを選択してモデルのプロパティを確認します。

3. [**アクティブモデル**] リストで、更新したモデルを選択します。

4. [**秘密度ラベル**] セクションに、適用されている秘密度ラベルの名前が表示されます。

ドキュメント ライブラリのモデルの表示ページに、新しい [**秘密度ラベル**] 列が表示されます。 モデルがそのコンテンツ タイプに属するものとして識別したファイルを分類し、それらをライブラリ ビューに一覧表示すると、[**秘密度ラベル**] 列には、モデルを通じてモデルに適用された秘密度ラベルの名前も表示されます。

たとえば、モデルが識別するすべての財務書類にも *暗号化* 秘密度ラベルが適用され、権限のないユーザーがアクセスするのを防ぎます。 権限のないユーザーがドキュメント ライブラリのファイルにアクセスしようとすると、適用されている秘密度ラベルのために許可されていないというエラーが表示されます。

<!---
## Add a sensitivity label to a form processing model

> [!Important]
> For sensitivity labels to be available to apply to your form processing model, they need to be [created and published in the Microsoft 365 Compliance Center](../business-video/create-sensitivity-labels.md).

You can either apply a sensitivity label to a form processing model when you are creating a model, or apply it to an existing model.

### Add a sensitivity label when you create a form processing model

1. When you [create a new form processing model](create-a-form-processing-model.md), select **Advanced settings**.

2. In **Advanced settings**, in the **Sensitivity label** section, select the menu and then select the sensitivity label you want to apply to the model.

3.  After you've completed your remaining model settings, select **Create** to build your model.

### Add a sensitivity label to an existing form processing model

You can add a sensitivity label to an existing form processing model in different ways:

- Through the **Automate** menu in the document library
- Through the **Active model** settings in the document library 

#### Add a sensitivity label to an existing form processing model through the Automate menu

You can add a sensitivity label to an existing form processing model that you own through the **Automate** menu in the document library in which the model is applied.

1. In your document library to which the form processing model is applied, select the **Automate** menu, select **AI Builder**, and then select **View form processing model details**.

2. On the **Model details** pane, in the **Sensitivity label** section, select the sensitivity label you want to apply. Then select **Save**.

#### Add a sensitivity label to an existing form processing model in the active model settings

You can add a sensitivity label to an existing form processing model that you own through the **Active model** settings in the document library in which the model is applied.

1. In the SharePoint document library in which the model is applied, select the **View active models** icon, and then select **View active models**.

2. In **Active models**, select the form processing model to which you want to apply the sensitivity label.

3. On the **Model details** pane, in the **Sensitivity label** section, select the sensitivity label you want to apply. Then select **Save**.

   > [!NOTE]
   > You must be the model owner for the **Model settings** pane to be editable. 
--->

## <a name="see-also"></a>関連項目

[保持ラベルを適用する](apply-a-retention-label-to-a-model.md)

[分類子を作成する](create-a-classifier.md)

[エクストラクターを作成する](create-an-extractor.md)

[ドキュメント理解の概要](document-understanding-overview.md)
