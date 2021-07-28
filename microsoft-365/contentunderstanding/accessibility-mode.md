---
title: SharePoint Syntex アクセシビリティ モード
ms.author: chucked
author: chuckedmonson
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Normal
description: ユーザー補助モードを使用してモデルをトレーニングする方法についてSharePoint Syntex。
ms.openlocfilehash: 168b64563ef720d659996d1093c8b181b145046d
ms.sourcegitcommit: 60cc1b2828b1e191f30ca439b97e5a38f48c5169
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2021
ms.locfileid: "53543223"
---
# <a name="sharepoint-syntex-accessibility-mode"></a>SharePoint Syntex アクセシビリティ モード

この[SharePoint Syntex、](index.md)ユーザーはサンプル ドキュメントを操作するときに、モデル トレーニングのすべての段階 (ラベル、トレーニング、テスト) でアクセシビリティ モードを有効にできます。 アクセシビリティ モードを使用すると、ユーザーがドキュメント ビューアーで項目を移動およびラベル付けする場合に、ユーザーがキーボードのアクセシビリティを簡単に行えるのに役立ちます。

これにより、ユーザーはキーボードを使用してドキュメント ビューアー内のテキスト内を移動したり、選択した値だけでなく、アクション (選択したテキストからのラベル付けや削除など) のナレーションや、追加のサンプル ドキュメントを使用してモデルをトレーニングする場合の予測ラベル値を聞くことができます。 


![アクセシビリティ モード](../media/content-understanding/accessibility-mode.png)

## <a name="requirements"></a>要件

ナレーションの音声を聞く場合は、ナレーター アプリを[](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1)ナレーター設定でオンにWindows 10してください。

![ナレーターを有効にする](../media/content-understanding/narrator-settings.png)

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

ユーザー補助モードを使用するナレーター ユーザーの場合は、キーボード ユーザーがビューアーのサンプル ドキュメントを通過するために説明されているのと同じキーボード ナビゲーションを使用します。

サンプル ドキュメントとラベル文字列値を移動すると、ナレーターはユーザーに次の音声プロンプトを表示します。

- キーボードを使用してドキュメント ビューアー内を移動すると、ナレーターオーディオに選択した文字列が表示されます。
- 選択した文字列内で、ナレーターオーディオは、左矢印キーまたは右矢印キーを使用して選択すると、文字列内の各文字を表示します。
- ラベルが付いた文字列を選択すると、ナレーターは値を表示し、"ラベル付け" します。  たとえば、ラベル値が "Contoso" の場合、"Costoso labeled" と表示されます。 
- [トレーニング] タブで、予測されただけの文字列をドキュメント ビューアーで選択すると、ナレーターのオーディオに値が表示され、"予測" されます。 これは、トレーニングによって、ユーザーがラベル付けされた値と一致しないファイル内の値を予測するときに発生します。
- [トレーニング] タブで、ラベル付けおよび予測されたドキュメント ビューアーで文字列を選択すると、ナレーターオーディオに値が表示され、[ラベル付けおよび予測] が表示されます。 これは、トレーニングが成功し、予測値とユーザー ラベルの間に一致する場合に発生します。

文字列にラベルが付けられているか、ビューアーでラベルが削除されると、ナレーターオーディオは終了する前に変更を保存する警告を表示します。

## <a name="see-also"></a>関連項目

[エクストラクターを作成する](create-an-extractor.md)

[分類子を作成する](create-a-classifier.md)










 


  
  



