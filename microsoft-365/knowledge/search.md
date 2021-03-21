---
title: Microsoft Search を使用して Microsoft Viva のトピックを検索する
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
description: Microsoft Viva でトピックを検索する方法について説明します。
ms.openlocfilehash: 1739923c95b42f192bb2e285245f72c3e09e1c30
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925930"
---
# <a name="use-microsoft-search-to-find-topics-in-microsoft-viva-topics"></a>Microsoft Search を使用して Microsoft Viva のトピックを検索する

ビバ トピックのユーザーは、SharePoint サイトのトピックのハイライトを通じてトピックを見つける一方で、Microsoft Search を通じてトピックを検索できます。 

## <a name="topic-answer"></a>トピックの回答

Microsoft Search で特定のトピック ("Saturn" など) を検索すると、トピックが存在し、見つかった場合は、回答候補形式で結果が表示されます。

トピックの回答が表示されます。
- トピック名
- 代替名: トピックの代替名または頭字語。
- 定義: AI によって提供されるトピックの説明、またはユーザーが手動で追加したトピックの説明。
- 推奨ユーザーまたはピン留めされたユーザー: AI によって提案されたユーザー、またはユーザーがトピックにピン留めしたユーザー
- 推奨リソースまたはピン留めされたリソース: AI によって提案されたファイル、ページ、またはサイト、またはユーザーによってトピックにピン留めされたサイト。 

   ![検索のトピック](../media/knowledge-management/search-topic-answer.png) 

トピック の応答カードが表示されない場合でも、トピック ページを検索結果に表示できます。


## <a name="acronyms"></a>頭字語

Viva Topics では、トピックを手動で編集して、トピックの頭字語を代替名として <b>含めできます</b>。 これにより、トピックの頭字語のみを使用して検索しているユーザーは、Microsoft Search を通じてトピックの回答を検索できます。

[頭字語の回答は](/microsoftsearch/manage-acronyms) 、Microsoft Search によって提供される機能であり、ビバ トピックとは別に管理されます。

## <a name="bookmarks-and-topics"></a>ブックマークとトピック

[ブックマークは](/microsoftsearch/manage-bookmarks) 、ユーザーが検索だけで重要なサイトやツールをすばやく見つけるのに役立つ Microsoft Search 機能です (たとえば、Microsoft 365 テナント外の外部サイトの旅行予約ツール)。 これらは、Microsoft 365 管理センターの検索管理者によって作成されます。 

出張の予約に関する情報をお探しのユーザー向け:

- 一部のユーザーが旅行ツール名 ("Concur" など) を知っている場合は、外部サイトに直接移動するブックマークを作成する方が簡単です。
- 一般的に "旅行" を検索するユーザーの場合は、「旅行」に関するトピックを作成します。そのトピックには、表示される情報が含されます。 トピックの説明で Concur 外部サイトへのリンクを追加する方法を検討してください。 リンクが Microsoft 365 テナントでホストされている内部旅行予約サイトにリンクされている場合は、"ピン留めされたリソース" に追加できます。
 
### <a name="search-results-priority"></a>検索結果の優先度 
 
ユーザー検索エクスペリエンスでは、ユーザーが "旅行" のような用語を検索すると、検索結果は Microsoft Search で次の優先度で表示されます。
1. 発行済みトピックまたは確認済みトピック 
2. ブックマーク
3. 推奨されるトピック