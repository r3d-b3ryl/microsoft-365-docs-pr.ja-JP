---
title: ドキュメントライブラリにドキュメントを適用する (プレビュー)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: SharePoint ドキュメントライブラリに発行されたモデルを適用する方法について説明します。
ms.openlocfilehash: 8a4931f4b7a936caeb99d7f8c07deefdac62919b
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950250"
---
# <a name="apply-a-document-understanding-model-preview"></a>ドキュメントを適用するモデルについて (プレビュー)

> [!Note] 
> この記事の内容は、Project Cortex のプライベートプレビュー用です。 [詳細については、「Project Cortex](https://aka.ms/projectcortex)」を参照してください。

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

ドキュメントを公開した後、モデルを理解した後、Microsoft 365 テナントの SharePoint ドキュメントライブラリに適用することができます。

> [!Note]
> アクセスできるドキュメントライブラリに対してのみ、モデルを適用することができます。


## <a name="apply-your-model-to-a-document-library"></a>モデルをドキュメントライブラリに適用します。

モデルを SharePoint ドキュメントライブラリに適用するには、次のようにします。

1. モデルのホームページで、[ **ライブラリにモデルを適用** ] タイルで、[ **モデルの発行**] を選択します。 または、[**このモデルを使用してライブラリ**内の**ライブラリを追加**] を選択することもできます。 </br>

    ![ライブラリにモデルを追加する](../media/content-understanding/apply-to-library.png)</br>

2. その後、モデルを適用するドキュメントライブラリを含む SharePoint サイトを選択できます。 サイトが一覧に表示されない場合は、検索ボックスを使用して検索します。</br>

    ![サイトの選択](../media/content-understanding/site-search.png)</br>

    > [!Note]
    > リストのアクセス許可を *管理* するか、モデルを適用するドキュメントライブラリに対する *編集* 権限を持っている必要があります。</br>

3. サイトを選択した後、モデルを適用するドキュメントライブラリを選択する必要があります。 この例では、 *Contoso 社のケーストラッキング*サイトから*ドキュメント*ドキュメントライブラリを選択しています。</br>

    ![ドキュメントライブラリを選択する](../media/content-understanding/select-doc-library.png)</br>

4. モデルはコンテンツタイプに関連付けられているため、ライブラリに適用すると、抽出したラベルが列として表示されるコンテンツタイプのビューが作成されます。 このビューは既定ではライブラリの既定のビューになりますが、オプションで [ **詳細設定** ] を選択し、[ **この新しいビューを既定として設定**する] を選択解除して、既定のビューにしないように選択することもできます。</br>

    ![ライブラリビュー](../media/content-understanding/library-view.png)</br>

5. [ **追加** ] を選択してモデルをライブラリに適用します。 
6. モデルのホームページの [ **このモデルを持つライブラリ** ] セクションに、SharePoint サイトの URL が表示されます。</br>

    ![ライブラリビュー](../media/content-understanding/selected-library.png)</br>

7. ドキュメントライブラリに移動し、モデルのドキュメントライブラリビューを使用していることを確認します。 ドキュメントライブラリ名の横にある [情報] ボタンを選択すると、モデルがドキュメントライブラリに適用されていることを示すメッセージが表示されます。

    ![ライブラリビュー](../media/content-understanding/info-du.png)</br> 


ドキュメントライブラリにモデルを適用した後で、サイトへのドキュメントのアップロードを開始し、結果を確認できます。

モデルは、モデルに関連付けられたコンテンツタイプを持つファイルを識別し、ビューにそのファイルをリストします。 モデルに抽出器がある場合、各ファイルから抽出するデータの列がビューに表示されます。

### <a name="apply-the-model-to-files-already-in-the-document-library"></a>ドキュメントライブラリに既に存在するファイルにモデルを適用する

適用したモデルでは、適用後にドキュメントライブラリにアップロードされたすべてのファイルが処理されますが、次の操作を実行して、モデルを適用する前にドキュメントライブラリに既に存在していたファイルに対してモデルを実行することもできます。

1. ドキュメントライブラリで、モデルで処理するファイルを選択します。
2. ファイルを選択すると、[ドキュメントライブラリ] リボンに **分類と抽出** が表示されます。 [ **分類と抽出**] を選択します。
3. 選択したファイルが処理されるキューに追加されます。

      ![分類と抽出](../media/content-understanding/extract-classify.png)</br> 





## <a name="see-also"></a>関連項目
[分類子を作成する](create-a-classifier.md)</br>
[抽出器を作成する](create-an-extractor.md)</br>
[ドキュメント理解の概要](document-understanding-overview.md)</br>
[フォーム処理モデルを作成する](create-a-form-processing-model.md)  




