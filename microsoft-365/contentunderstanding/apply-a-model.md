---
title: ドキュメントライブラリにドキュメントを適用する
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
description: SharePoint ドキュメントライブラリに発行されたモデルを適用する方法について説明します。
ms.openlocfilehash: c693fa08bf3103eca01e01774e8f8b1d9e783b07
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295492"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a>ドキュメントを適用する Microsoft SharePoint の同期のモデルを理解する

この記事の内容は、Project Cortex のプライベートプレビュー用です。 [詳細については、「Project Cortex](https://aka.ms/projectcortex)」を参照してください。

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

ドキュメントを公開した後、モデルを理解した後、Microsoft 365 テナントの SharePoint ドキュメントライブラリに適用することができます。

> [!NOTE]
> アクセスできるドキュメントライブラリにのみモデルを適用できます。


## <a name="apply-your-model-to-a-document-library"></a>モデルをドキュメントライブラリに適用します。

モデルを SharePoint ドキュメントライブラリに適用するには、次のようにします。

1. モデルのホームページで、[ **ライブラリにモデルを適用** ] タイルの [ **発行モデル**] を選択します。 または、[**このモデルを使用してライブラリ**内の**ライブラリを追加**] を選択することもできます。 </br>

    ![ライブラリにモデルを追加する](../media/content-understanding/apply-to-library.png)</br>

2. モデルを適用するドキュメントライブラリが含まれている SharePoint サイトを選択します。 サイトが一覧に表示されない場合は、検索ボックスを使用して検索します。</br>

    ![サイトの選択](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > リストのアクセス許可を *管理* するか、モデルを適用するドキュメントライブラリに対する *編集* 権限を持っている必要があります。</br>

3. サイトを選択してから、モデルを適用するドキュメントライブラリを選択します。 サンプルでは、 *Contoso 社のケーストラッキング*サイトから*ドキュメント*ドキュメントライブラリを選択します。</br>

    ![ドキュメントライブラリを選択する](../media/content-understanding/select-doc-library.png)</br>

4. モデルはコンテンツタイプに関連付けられているため、ライブラリに適用すると、抽出したラベルが列として表示されるコンテンツタイプのビューが作成されます。 このビューは既定ではライブラリの既定のビューですが、オプションで **[詳細設定** ] を選択し、[ **この新しいビューを既定として設定**する] をオフにして、既定のビューにしないように選択することもできます。</br>

    ![ライブラリビュー](../media/content-understanding/library-view.png)</br>

5. [ **追加** ] を選択してモデルをライブラリに適用します。 
6. モデルのホームページの [ **このモデルを持つライブラリ** ] セクションに、表示されている SharePoint サイトの URL が表示されます。</br>

    ![選択されたライブラリ](../media/content-understanding/selected-library.png)</br>

7. ドキュメントライブラリに移動し、モデルのドキュメントライブラリビューを使用していることを確認します。 ドキュメントライブラリ名の横にある [情報] ボタンを選択すると、モデルがドキュメントライブラリに適用されたことを示すメッセージが表示されることに注意してください。

    ![情報ビュー](../media/content-understanding/info-du.png)</br> 


ドキュメントライブラリにモデルを適用した後で、サイトへのドキュメントのアップロードを開始し、結果を確認できます。

モデルは、モデルに関連付けられたコンテンツタイプのすべてのファイルを識別し、ビューにリストを表示します。 モデルに抽出器がある場合、ビューには各ファイルから抽出するデータの列が表示されます。

### <a name="apply-the-model-to-files-already-in-the-document-library"></a>ドキュメントライブラリに既に存在するファイルにモデルを適用する

適用されたモデルは、適用された後にドキュメントライブラリにアップロードされたすべてのファイルを処理しますが、次の操作を行って、モデルを適用する前に、ドキュメントライブラリに既に存在するファイルに対してモデルを実行することもできます。

1. ドキュメントライブラリで、モデルで処理するファイルを選択します。
2. ファイルを選択すると、[ドキュメントライブラリ] リボンに **分類と抽出** が表示されます。 [ **分類と抽出**] を選択します。
3. 選択したファイルが処理されるキューに追加されます。

      ![分類と抽出](../media/content-understanding/extract-classify.png)</br> 

## <a name="see-also"></a>関連項目
[分類子を作成する](create-a-classifier.md)</br>
[抽出器を作成する](create-an-extractor.md)</br>
[ドキュメント理解の概要](document-understanding-overview.md)</br>
[フォーム処理モデルを作成する](create-a-form-processing-model.md)  
