---
title: Advanced eDiscovery で分析の [テキストを無視する] オプションを設定する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 44055727-56e8-42d7-9dc3-fb942f3901cc
description: Advanced eDiscovery の分析モジュールとプロセス モジュールを使用するときに、特定のテキストを無視するルールを定義する方法について説明します。
ms.openlocfilehash: f61724e3964ff4ba7f099dbfb4411e19db258adc
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663472"
---
# <a name="set-ignore-text-option-for-analyze-in-advanced-ediscovery-classic"></a>Advanced eDiscovery (クラシック) で分析の [テキストを無視する] オプションを設定する

> [!NOTE]
> Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。 
  
テキストを無視する機能は、Advanced eDiscovery モジュールのすべてまたは任意に適用できます。分析 (近重複、電子メール スレッド、テーマ) および関連性。 無視されたテキストは、関連性に表示されるファイルには表示されません。分析/計算では、無視されたテキストは破棄されます。
  
既に実行されているモジュールに対して [テキストを無視] 機能が既に定義されている場合、[テキストを無視] 設定は変更されません。 ただし、関連性モジュールの [テキストを無視] 機能は、いつでも変更できます。
  
## <a name="how-ignore-text-filters-are-applied"></a>[テキストを無視する] フィルターの適用方法

複数の無視テキスト フィルターが入力された順序で適用されます。 適用する順序を変更するには、削除して目的の順序で再入力する必要があります。
  
たとえば、テキスト コンテンツが "DAVE BOB ALICE CAROLEVE" の場合、無視するテキスト エントリのサンプルと、これらのエントリによって生成される結果を次に示します。

|**テキスト のエントリを無視する** <br/> |**結果** <br/> |
|:-----|:-----|
|"ALICE"、"BOB CAROL"  <br/> |"DAVEEVE"  <br/> |
|"ALICE"、"BOB ALICE CAROL"  <br/> |"DAVE BOB CAROLEVE"  <br/> |
   
2 番目の Ignore Text エントリは、最初の無視テキストが適用された後にこのような文字列が見つからないため、実装されていません。
  
## <a name="use-regular-expressions-when-defining-ignore-text"></a>無視するテキストを定義するときに正規表現を使用する

Ignore Text を定義する場合は、正規表現がサポートされています。 正規表現の構文と使用方法の例を次に示します。
  
- 行の末尾まで Begin からテキストを削除 (無視) するには:
    
     `Begin(.*)$`
    
    ここで、"Begin" は行内でこの文字列が最初に出現します。
    
    たとえば、次のテキストの場合:
    
    **"これは最初の文と最初の行です。**
    
    **これは 2 番目の文と 2 行目です"**
    
    正規表現 first(. \* )$ を指定すると、次の結果が返されます。
    
    **"これは次の場合です。**
    
    **これは 2 番目の文と 2 行目です"**
    
- 電子メール スレッドの末尾に自動的に挿入される免責事項と法的声明を削除するには、次の操作を行います。
    
     `Begin(.|\s)*End`
    
    ここで、"Begin" と "End" は、ラップされたテキスト段落の先頭と末尾に一意の文字列です。 
    
    たとえば、次の正規表現は、Begin 文字列と End 文字列の間の電子メール スレッドに含めらた免責事項と法的ステートメントを削除します。
    
    **このメッセージには機密情報 (.|\s) \* 検証が必要な場合は、ハード コピー バージョンを要求してください**
    
- 免責事項 (特殊文字を含む) を削除するには: 
    
    たとえば、次のテキストの場合 (ここで x で表される免責事項を含む)。 
    
    **/\*\ このメッセージには機密情報が含まれている。xxxx xxxx**
    
    **xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx**
    
    **xxxx xxxx 検証が必要な場合は、ハード コピー バージョンを要求してください。/\*\**
    
    上記の免責事項を削除する正規表現は次のようにする必要があります。 
    
    **\/\\*\\このメッセージには機密情報 \. (.|\s) \* 検証が必要な場合は、ハード コピー バージョンを要求してください \.\/\\*\\**
    
- 正規表現ルール:
    
  - スペース、"_"、および "-" 以外のアルファベットの一部ではない文字の前に " が必要です \" 。
    
  - 通常の eExpression フィールドの長さは無制限です。
    
> [!TIP]
> 正規表現の説明と詳細な構文については、「正規表現言語 - クイック [リファレンス」を参照してください](https://msdn.microsoft.com/library/az24scfc%28v=vs.110%29.aspx)。 
  
## <a name="define-ignore-text-rule"></a>テキスト無視ルールの定義

1. [分析 **の \> 管理 \> ] オプション タブ** の[テキストを無視] セクションで、アイコンをクリックして **+** ルールを追加します。 
    
2. [テキスト **を無視して** 追加] ダイアログの **[名前** ] フィールドに、無視するテキスト ルールの名前を入力します。 
    
    ![無視されたテキストの追加](../media/98e5129b-2667-4692-86fa-2d0117187a7f.png)
  
3. [テキスト **] ボックス** に、無視するテキストを入力します。 テキスト フィールドでは、文字数に制限はありません。 
    
    > [!TIP]
    > 上のウィンドウに示すように、ライト ライト ライト **を** クリックすると、テキストを無視するルールの一般的な構文ガイドラインが表示されます。 
  
4. 必要に応 **じて、[** 大文字と小文字を区別する] チェック ボックスをオンにします。 
    
5. [適用 **先] ボックスの** 一覧で、定義を適用する Advanced eDiscovery モジュールを選択します。 
    
6. サンプル テキストでテストを実行する場合は、[入力] テキストボックスにサンプル テキストを入力し、[テスト] をクリック **します**。 結果が [出力] テキスト **ボックスに** 表示されます。 
    
7. **[OK] を** クリックして [テキストを無視] ルールを保存します。 定義されている無視テキスト ルールが表示されます。 
    
    ![無視されたテキスト名を設定する](../media/3a788ac3-4a1c-46c9-89bd-7ff32d68ce23.png)
  
## <a name="see-also"></a>関連項目

[Advanced eDiscovery (クラシック)](office-365-advanced-ediscovery.md)
  
[ドキュメントの類似性について](understand-document-similarity-in-advanced-ediscovery.md)
  
[分析オプションの設定](set-analyze-options-in-advanced-ediscovery.md)
  
[分析の詳細設定の設定](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[分析結果の表示](view-analyze-results-in-advanced-ediscovery.md)

