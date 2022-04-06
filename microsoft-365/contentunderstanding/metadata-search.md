---
title: Microsoft SharePoint Syntex のドキュメント ライブラリでメタデータを検索する
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: kkameth
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: high
description: 高度なメタデータ検索とカスタム サイト列の検索を使用して、SharePoint Syntex で SharePoint ドキュメント ライブラリ内のアイテムを検索する方法について説明します。
ms.openlocfilehash: f010c6944fdcb05fcfe2c254274249b2dcabe99e
ms.sourcegitcommit: 33bc25167812b31c51cf096c728e3a5854e94f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2022
ms.locfileid: "64595381"
---
# <a name="search-for-metadata-in-document-libraries-in-microsoft-sharepoint-syntex"></a>Microsoft SharePoint Syntex のドキュメント ライブラリでメタデータを検索する

SharePoint Syntex の高度なメタデータ検索機能を使用すると、SharePoint ドキュメント ライブラリに対して特定のメタデータ ベースのクエリを実行できます。 キーワードを検索するのではなく、特定のメタデータ列の値に基づいて、より高速で正確なクエリを行なえます。

高度なメタデータ検索を使用すると、ドキュメントに関連付けられているメタデータを使用して、SharePoint ドキュメント ライブラリ内のファイルを見つけられます。 この機能は、ドキュメントが最後に変更されたとき、ファイルに関連付けられている特定のユーザー、特定のファイルの種類など、検索する特定の情報がある場合に特に便利です。

> [!NOTE]
> この機能は、SharePoint Syntex のライセンスを取得しているユーザーのみが使用できます。 

## <a name="to-use-advanced-metadata-search"></a>高度なメタデータ検索を使用するには

1. SharePoint ドキュメント ライブラリから、 **このライブラリを検索** ボックスで、メタデータ検索アイコン (メタデータ検索アイコンの ![Screenshot.](../media/content-understanding/metadata-search-icon.png)) を選択します。

    ![メタデータ検索アイコンが強調表示された検索ボックスを示すドキュメント ライブラリ ページのスクリーンショット。](../media/content-understanding/metadata-search-box.png)

2. メタデータ検索ウィンドウで、テキストを入力するか、1 つ以上の検索フィールドで検索するパラメーターを選択します。

    ![メタデータ検索ウィンドウを示すドキュメント ライブラリ ページのスクリーンショット。](../media/content-understanding/metadata-search-pane.png)

   現在、次のメタデータ検索フィールドを使用できます。 今後、さらにフィールドが追加される予定です。

   |Field    |このフィールドを使用して  |
   |---------|---------|
   |キーワード |メタデータまたはドキュメントのフルテキストで文字列の一致を検索します。 |
   |ファイル名     |ライブラリの **名前** 列を検索します。          |
   |ユーザー   |ライブラリ内の任意の列のユーザーとの一致を検索します。   |
   |更新日 |ライブラリの **更新** 列で、選択した日付範囲を検索します。         |
   |ファイルの種類     |選択したファイルの種類 (Word 文書や PDF など) で検索します。        |
   |コンテンツ タイプ  |選択したコンテンツ タイプで検索します。 このオプションは、ライブラリに既定以外のコンテンツ タイプが適用されている場合にのみ表示されます。 既定のコンテンツ タイプは、 *ドキュメント* と *フォルダー* です。        |

3. また、現在のライブラリ ビューにあるカスタム サイト列を検索することもできます。 これは、メタデータ抽出器が自動的にサイト列に情報を入力するために、ライブラリでモデルを実行している場合は特に便利です。  

    カスタム サイト列を検索に追加するには、[**その他のオプションを追加**] を選択し、サイト列の名前を選択します。

    ![メタデータ検索ウィンドウの [その他のオプションを追加] メニューのスクリーンショット。](../media/content-understanding/metadata-search-add-more-options.png)

    > [!NOTE]
    > 現在、管理されたメタデータ フィールドや複数行のテキスト フィールドを追加する機能は使用できません。 

4. **検索** を選択します。メタデータ検索に一致するドキュメントが結果ページに表示されます。 
