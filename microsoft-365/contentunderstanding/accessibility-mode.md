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
description: Syntex でモデルをトレーニングするときにアクセシビリティ モードを使用するSharePointします。
ms.openlocfilehash: 5f6e9d542f3d41dbddacd54b1b379910dcb0c9dc
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515150"
---
# <a name="sharepoint-syntex-accessibility-mode"></a>SharePoint Syntex アクセシビリティ モード

Syntex [SharePoint](index.md)では、サンプル ドキュメントを操作するときに、モデル トレーニングのすべての段階 (ラベル、トレーニング、テスト) でアクセシビリティ モードを有効にできます。 アクセシビリティ モードを使用すると、ユーザーがドキュメント ビューアーで項目を移動およびラベル付けする場合に、ユーザーがキーボードのアクセシビリティを簡単に行えるのに役立ちます。

これにより、ユーザーはキーボードを使用してドキュメント ビューアー内のテキスト内を移動したり、選択した値だけでなく、アクション (選択したテキストからのラベル付けや削除など) のナレーションや、追加のサンプル ドキュメントを使用してモデルをトレーニングする場合の予測ラベル値を聞くことができます。 


![アクセシビリティ モード](../media/content-understanding/accessibility-mode.png)

## <a name="requirements"></a>要件

ナレーションの音声を聞く場合は、ナレーター システムの[](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1)ナレーター 設定で Windows 10してください。

![[オンにする] ナレーター](../media/content-understanding/narrator-settings.png)

## <a name="labeling-for-keyboard-users"></a>キーボード ユーザーのラベル付け

アクセシビリティ モードを使用するキーボード ユーザーの場合、ビューアーでサンプル ドキュメントのテキストにラベルを付けする場合は、次のキーを使用できます。

- Tab: 前方に移動し、次の単語を選択します。
- Tab + Shift: 前に移動し、前の単語を選択します。
- Enter: 選択した単語にラベルを付け、またはラベルを削除します。
- 右矢印: 選択した単語の個々の文字を移動します。
- 左矢印: 選択した単語の個々の文字を後方に移動します。

> [!NOTE]
> 1 つのラベルに複数の単語をラベル付けする場合は、各単語にラベルを付けする必要があります。


## <a name="narration"></a>ナレーション

ユーザーナレーターユーザーがアクセシビリティ モードを使用する場合は、キーボード ユーザーに説明されているのと同じキーボード ナビゲーションを使用して、ビューアーのドキュメント例を確認します。

サンプル ドキュメントとラベル文字列値を移動すると、ナレーター次の音声プロンプトが表示されます。

- キーボードを使用してドキュメント ビューアー内を移動すると、オーディオナレーター選択した文字列が表示されます。
- 選択した文字列内で、ナレーターまたは右矢印キーを使用して選択すると、文字列内の各文字が音声で表示されます。
- ラベルが付いた文字列を選択すると、ナレーターが表示され、[ラベル付け] が表示されます。  たとえば、ラベル値が "Contoso" の場合、"Costoso labeled" と表示されます。 
- [トレーニング] タブで、予測されただけの文字列をドキュメント ビューアーで選択すると、ナレーターオーディオに値が表示され、"予測" されます。 これは、トレーニングによって、ユーザーがラベル付けされた値と一致しないファイル内の値を予測するときに発生します。
- [トレーニング] タブで、ラベル付けおよび予測されたドキュメント ビューアーで文字列を選択すると、ナレーター オーディオに値が表示され、[ラベル付けおよび予測] が表示されます。 これは、トレーニングが成功し、予測値とユーザー ラベルの間に一致する場合に発生します。



文字列にラベルが付けられているか、ビューアーでラベルが削除されると、ナレーター前に変更を保存する警告が表示されます。

## <a name="see-also"></a>関連項目

[エクストラクターを作成する](create-an-extractor.md)</br>

[分類子を作成する](create-a-classifier.md)</br>










 


  
  



