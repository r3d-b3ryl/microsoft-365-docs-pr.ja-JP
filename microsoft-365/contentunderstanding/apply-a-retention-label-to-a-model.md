---
title: ドキュメントへの保持ラベルの適用モデルについて
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: この記事では、ドキュメントに保持ラベルを適用する方法について説明します。モデルを理解する
ms.openlocfilehash: 26ad64906c0e2a311d8b244e8e1596a8b975cc15
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294925"
---
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a>ドキュメントへの保持ラベルの適用モデルについて

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

[保持ラベル](https://docs.microsoft.com/microsoft-365/compliance/retention)は、Microsoft SharePoint の同期のモデルを理解するドキュメントに簡単に適用できます。

保持ラベルを使用すると、ドキュメントが識別するドキュメントに保持設定を適用できます。  たとえば、ドキュメントライブラリにアップロードされる *保険通知* ドキュメントを特定するだけでなく、指定された期間 (たとえば、次の5か月) にこれらのドキュメントをドキュメントライブラリから削除できないようにするために、モデルに *ビジネス* 保持タグを適用することもできます。

既存の保持ラベルをドキュメントに適用するには、モデルのホームページのモデル設定を使用します。 

> [!Important]
> コンテンツについて理解するために保持ラベルを使用できるようにするには、 [Microsoft 365 コンプライアンスセンターで作成および発行](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels)する必要があります。

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a>ドキュメントに保持ラベルを追加するにはモデルを理解する

1. モデルのホームページで、[ **モデルの設定**] を選択します。</br>
2. [ **モデル設定**] の [ **セキュリティとコンプライアンス** ] セクションで、[ **保持ラベル** ] メニューを選択して、モデルに適用するために使用できる保持ラベルのリストを表示します。</br>
 ![保持ラベルメニュー](../media/content-understanding/retention-labels-menu.png)</br> 
3. モデルに適用する保持ラベルを選択し、[ **保存**] を選択します。</br>

保持ラベルをモデルに適用した後、それをモデルに適用することができます。
- 新しいドキュメントライブラリ
- モデルが既に適用されているドキュメントライブラリ
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a>モデルが既に適用されているドキュメントライブラリに保持ラベルを適用する

ドキュメントがドキュメントライブラリに既に適用されている場合、ドキュメントライブラリに適用するために保持ラベルの更新を同期するには、次の操作を実行できます。</br>

1. モデルのホームページの [ **このモデルを持つライブラリ** ] セクションで、保持ラベルの更新を適用するドキュメントライブラリを選択します。 </br> 
2. [ **同期**] を選択します。 </br>
 ![同期モデル](../media/content-understanding/sync-model.png)</br> 


更新を適用してモデルに同期した後、次の操作を実行して、更新が適用されたことを確認できます。

1. コンテンツセンターの [ **このモデルを持つライブラリ** ] セクションで、更新したモデルが適用されたライブラリをクリックします。 </br>
2. ドキュメントライブラリビューで、[情報] アイコンを選択してモデルプロパティを確認します。</br>  
3. [ **アクティブなモデル** ] の一覧で、更新したモデルを選択します。</br>
4. [ **保持ラベル** ] セクションに、適用される保持ラベルの名前が表示されます。</br>


ドキュメントライブラリのモデルの表示ページで、新しい [ **保持ラベル** ] 列が表示されます。  モデルは、そのコンテンツタイプに属すると識別されるファイルを分類し、それらをライブラリビューで一覧表示します。また、[保持ラベル] 列には、モデルによって適用された保持ラベルの名前も表示されます。


たとえば、モデルによって識別されるすべての *保険通知* ドキュメントにも、 *ビジネス* 保持ラベルが適用されるため、5か月間ドキュメントライブラリから削除されることはありません。 ドキュメントライブラリからファイルを削除しようとすると、適用された保持ラベルが原因で許可されていないというエラーが表示されます。

## <a name="see-also"></a>関連項目
[分類子を作成する](create-a-classifier.md)</br>
[抽出器を作成する](create-an-extractor.md)</br>
[ドキュメント理解の概要](document-understanding-overview.md)</br>
[フォーム処理モデルを作成する](create-a-form-processing-model.md)  
