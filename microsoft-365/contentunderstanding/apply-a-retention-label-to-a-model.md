---
title: 保持ラベルをドキュメント理解モデルに適用する
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: この記事では、保持ラベルをドキュメント理解モデルに適用する方法について説明します
ms.openlocfilehash: 6dcd81b580b7bf0801641bbd019e1b99ecfe7338
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976557"
---
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a>保持ラベルをドキュメント理解モデルに適用する

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


Microsoft SharePoint Syntex のドキュメント理解モデルに[保持ラベル](https://docs.microsoft.com/microsoft-365/compliance/retention)を簡単に適用できます。

保持ラベルを使用すると、ドキュメント理解モデルが識別するドキュメントに保持設定を適用できます。  たとえば、モデルで、ドキュメント ライブラリにアップロードされた *保険通知* ドキュメントを識別するだけでなく、*ビジネス* 保持タグを適用して、これらのドキュメントを指定された期間 ( たとえば、次の5か月) ドキュメント ライブラリから削除できないようにする必要があります。

モデルのホームページのモデル設定を使用して、既存の保持ラベルをドキュメント理解モデルに適用できます。 

> [!Important]
> 保持ラベルをコンテンツ理解モデルに適用できるようにするには、保持ラベルを[作成して Microsoft 365 コンプライアンス センターで公開する](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels)必要があります。

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a>保持ラベルをドキュメント理解モデルに追加する

1. モデルのホーム ページから、[**モデルの設定**]を選択します。</br>
2. [**モデルの設定**] の [**セキュリティとコンプライアンス**] セクションで、[**保持ラベル**] メニューを選択して、モデルに適用できる保持ラベルのリストを表示します。</br>
 ![保持ラベル メニュー](../media/content-understanding/retention-labels-menu.png)</br> 
3. モデルに適用する保持ラベルを選択し、[**保存**] を選択します。</br>

モデルに保持ラベルを適用した後、次のものに適用できます。
- 新しいドキュメント ライブラリ
- モデルがすでに適用されているドキュメント ライブラリ
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a>モデルがすでに適用されているドキュメント ライブラリに保持ラベルを適用します

ドキュメント理解モデルがすでにドキュメント ライブラリに適用されている場合は、次の手順を実行して、保持ラベルの更新を同期し、ドキュメント ライブラリに適用できます。</br>

1. モデルホームページの [**このモデルのあるライブラリ**] セクションで、保持ラベルの更新を適用するドキュメントライブラリを選択します。 </br> 
2. [**同期**] を選択します。 </br>
 ![同期モデル](../media/content-understanding/sync-model.png)</br> 


更新を適用してモデルに同期した後、次の手順を実行して、更新が適用されたことを確認できます。

1. コンテンツ センターの [**このモデルのあるライブラリ**] セクションで、更新したモデルが適用されたライブラリをクリックします。 </br>
2. ドキュメント ライブラリ ビューで、情報アイコンを選択してモデルのプロパティを確認します。</br>  
3. [**アクティブモデル**] リストで、更新したモデルを選択します。</br>
4. [**保持ラベル**] セクションに、適用された保持ラベルの名前が表示されます。</br>


ドキュメント ライブラリのモデルの表示ページに、新しい **保持ラベル** 列が表示されます。  モデルがそのコンテンツ タイプに属するものとして識別したファイルを分類し、それらをライブラリ ビューに一覧表示すると、[保持ラベル]列には、モデルを通じてモデルに適用された保持ラベルの名前も表示されます。


たとえば、モデルが識別するすべての *保険通知* ドキュメントには、*ビジネス* 保持ラベルも適用され、ドキュメント ライブラリから5か月間削除されないようにします。 ドキュメント ライブラリからファイルを削除しようとすると、保持ラベルが適用されているため許可されていないというエラーが表示されます。

## <a name="see-also"></a>関連項目
[分類子を作成する](create-a-classifier.md)

[抽出子を作成する](create-an-extractor.md)

[ドキュメント理解の概要](document-understanding-overview.md)


