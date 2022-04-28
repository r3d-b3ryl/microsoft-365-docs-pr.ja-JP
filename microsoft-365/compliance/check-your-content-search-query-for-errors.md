---
title: 検索クエリでエラーを確認する
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: 88898874-e262-4c5c-b6d2-4e697497fc74
ms.custom: seo-marvel-apr2020
description: 検索を実行する前に、電子情報開示検索のキーワード クエリでエラーと入力ミスを検出する方法について説明します。
ms.openlocfilehash: 858db046cf78482e8540425a3f826f2ce28e78cd
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65091789"
---
# <a name="check-your-search-query-for-errors"></a>検索クエリでエラーを確認する

[!include[Purview banner](../includes/purview-rebrand-banner.md)]
  
コンテンツ検索と Microsoft Purview 電子情報開示 (Standard) の検索クエリでチェックするサポートされていない文字の一覧を次に示します。 サポートされていない文字は非表示になることが多く、通常は検索エラーが発生したり、意図しない結果が返されたりします。
  
- **スマート引用符** - スマート単一引用符と二重引用符 (カーリー 引用符とも呼ばれます) はサポートされていません。 検索クエリでは、ストレート引用符のみ使用できます。 

- **印刷できない文字と制御文字** - 印刷不能文字と制御文字は、英数字などの書き込み記号を表しません。 印刷不可能な文字と制御文字には、テキストを書式設定する文字や個別のテキスト行などが含まれます。 

- **左から右、右から左のマーク** - これらのマークは、左から右の言語 (英語やスペイン語など) と右から左の言語 (アラビア語やヘブライ語など) のテキスト方向を示すために使用される制御文字です。

- **小文字のブール演算子** - 検索クエリで **AND**、 **OR**、 **NOT** などのブール演算子を使用する場合は、大文字にする必要があります。 入力ミスのクエリをチェックすると、小文字の演算子を使用する場合でも、クエリ構文でブール演算子が使用されていることが多く示されます。たとえば、. `(WordA or WordB) and (WordC or WordD)`

## <a name="what-happens-if-a-query-has-an-unsupported-character"></a>クエリにサポートされていない文字がある場合はどうなりますか?

クエリでサポートされていない文字が見つかった場合は、サポートされていない文字が見つかったことを示す警告メッセージが表示され、代わりの文字が提案されます。 その後、元のクエリを保持するか、推奨される変更されたクエリに置き換えることができます。

前のスクリーンショットで検索クエリの [ **クエリの入力ミスの確認** ] をクリックした後に表示される警告メッセージの例を次に示します。 元のクエリでは、スマート 引用符と小文字のブール演算子が使用されていることに注意してください。
  
![警告メッセージが表示され、クエリの推奨リビジョンが表示されます。](../media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a>検索クエリでサポートされていない文字を防ぐ方法

サポートされていない文字は、通常、クエリまたはクエリの一部を他のアプリケーション (Microsoft WordやMicrosoft Excelなど) からコピーし、コンテンツ検索のクエリ ページのキーワード ボックスに貼り付けると、クエリに追加されます。 サポートされていない文字を使用しないようにする最善の方法は、キーワード ボックスにクエリを入力することです。 または、Word またはExcelからクエリをコピーし、Microsoft メモ帳などのプレーンテキスト エディターに貼り付けることができます。 テキスト ファイルを保存し、[**エンコード]** ドロップダウン リストで **[ANSI**] を選択します。 これにより、すべての書式設定とサポートされない文字が削除されます。 その後、テキスト ファイルからクエリをコピーして、キーワード クエリ ボックスに貼り付けることができます。
