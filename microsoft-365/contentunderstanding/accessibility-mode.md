---
title: 'SharePoint Syntex アクセシビリティ モード '
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Normal
description: SharePoint Syntex でモデルをトレーニングするときにアクセシビリティ モードを使用する方法について説明します。
ms.openlocfilehash: 32e5bd132a7a0145f03e4620545d65d1d92ff223
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/02/2021
ms.locfileid: "50081009"
---
# <a name="sharepoint-syntex-accessibility-mode"></a>SharePoint Syntex アクセシビリティ モード

[SharePoint Syntex](index.md)では、サンプル ドキュメントを操作するときに、ユーザーはモデル トレーニングのすべての段階 (ラベル、トレーニング、テスト) でアクセシビリティ モードを有効にできます。 アクセシビリティ モードを使用すると、ユーザーがドキュメント ビューアー内の項目間を移動してラベルを付け、キーボードのアクセシビリティを容易にすることができます。

これにより、ユーザーはキーボードを使用してドキュメント ビューアーのテキスト内を移動したり、選択した値だけでなく、操作 (選択したテキストへのラベル付けや削除など) のナレーションや、追加のサンプル ドキュメントを使用してモデルをトレーニングする場合の予測ラベル値を聞くことができます。 


![アクセシビリティ モード](../media/content-understanding/accessibility-mode.png)

## <a name="requirements"></a>要件

ナレーションの音声を聞く場合は、Windows 10[](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1)システムのナレーター設定でナレーター アプリをオンにしてください。

![ナレーターを有効にする](../media/content-understanding/narrator-settings.png)

## <a name="labeling-for-keyboard-users"></a>キーボード ユーザーのラベル付け

アクセシビリティ モードを使用するキーボード ユーザーの場合、ビューアーでサンプル ドキュメントのテキストにラベルを付けしている場合は、次のキーを使用できます。

- Tab: 前方に移動し、次の単語を選択します。
- Tab キーを押しながら Shift キーを押します。前の単語を前に移動して選択します。
- Enter: Label or removes a label from the selected word.
- 方向キー: 選択した単語内の個々の文字を移動します。
- 下方向キー: 選択した単語内の個々の文字を後方に移動します。

> [!NOTE]
> 1 つのラベルに複数の単語をラベル付けする場合は、各単語にラベルを付けする必要があります。


## <a name="narration"></a>ナレーション

アクセシビリティ モードを使うナレーター ユーザーの場合は、キーボード ユーザーがビューアーのサンプル ドキュメントを操作するために説明されているのと同じキーボード ナビゲーションを使います。

サンプル ドキュメントとラベル文字列値を移動すると、ナレーターはユーザーに次の音声プロンプトを表示します。

- キーボードを使用してドキュメント ビューアー内を移動すると、ナレーターオーディオは選択した文字列を表示します。
- 選択した文字列内で、ナレーターオーディオは、前方矢印または戻る矢印を使用して、選択した文字列内の各文字を表示します。
- ラベルが付いた文字列を選択すると、ナレーターは値を入力してから "ラベル付け" を行います。  たとえば、ラベルの値が "Contoso" の場合、"Costoso labeled" と表示されます。 
- [トレーニング] タブで、予測されただけの文字列をドキュメント ビューアーで選択すると、ナレーターのオーディオに値が表示され、"予測" されます。 これは、ユーザーがラベル付けした値と一致しないファイル内の値をトレーニングが予測するときに発生します。
- [トレーニング] タブで、ラベルが付いて予測されているドキュメント ビューアーで文字列を選択すると、ナレーターオーディオに値が表示され、"ラベル付けおよび予測" されます。 これは、トレーニングが成功し、予測値とユーザー ラベルが一致する場合に発生します。



文字列にラベルが付けられているか、ビューアーでラベルが削除されると、終了する前に変更を保存する警告がナレーターのオーディオに表示されます。

## <a name="see-also"></a>関連項目

[エクストラクターを作成する](create-an-extractor.md)</br>

[分類子を作成する](create-a-classifier.md)</br>










 


  
  



