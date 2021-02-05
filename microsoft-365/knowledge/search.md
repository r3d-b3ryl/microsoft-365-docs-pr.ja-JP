---
title: Microsoft Search を使用して Microsoft のトピックを検索する
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
description: Microsoft Microsoft Microsoft のトピックを検索する方法について説明します。
ms.openlocfilehash: 484d2477f7e4dbef096a4b8a2d30095708c6cc3f
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2021
ms.locfileid: "50108301"
---
# <a name="use-microsoft-search-to-find-topics-in-microsoft-viva-topics"></a>Microsoft Search を使用して Microsoft のトピックを検索する

ユーザーは、SharePoint サイトのトピックハイライトを通じてトピックを見つける一方で、Microsoft Search を通じてトピックを見つけるのも可能です。 

## <a name="topic-answer"></a>トピック回答

Microsoft Search で特定のトピック ("Saturn" など) を検索すると、トピックが存在し、見つかった場合は、その結果が回答候補形式で表示されます。

トピックの回答が表示されます。
- トピック名
- 代替名: トピックの代替名または頭字語。
- 定義: AI によって提供される、またはユーザーが手動で追加したトピックの説明。
- 推奨ユーザーまたはピン留めされたユーザー: AI によって提案されたユーザー、またはユーザーによってトピックにピン留めされたユーザー
- 推奨リソースまたは固定リソース: AI によって提案されたファイル、ページ、またはサイト、またはユーザーによってトピックにピン留めされたファイル、ページ、またはサイト。 

   ![検索のトピック](../media/knowledge-management/search-topic-answer.png) 

トピック の回答カードが表示されない場合でも、トピック ページを検索結果に表示できます。


## <a name="acronyms"></a>頭字語

In Topics, you can manually edit a topic to include aronym for it as an <b>Alternate Name</b>. これにより、トピックの頭字語のみを検索しているユーザーは、Microsoft Search を使用してトピックの回答を検索できます。

[頭字語の回答は](https://docs.microsoft.com/microsoftsearch/manage-acronyms) 、Microsoft Search によって提供される機能であり、「トピック」とは別に管理されています。

## <a name="bookmarks-and-topics"></a>ブックマークとトピック

[ブックマーク](https://docs.microsoft.com/microsoftsearch/manage-bookmarks) は、検索だけで重要なサイトやツールをすばやく見つけるのに役立つ Microsoft Search 機能です (たとえば、Microsoft 365 テナント外の外部サイトの旅行予約ツール)。 これらは、Microsoft 365 管理センターの検索管理者によって作成されます。 

出張の予約に関する情報をお探しのユーザーの場合:

- 一部のユーザーが旅行ツール名 ("Concur" など) を知っている場合は、外部サイトに直接移動するブックマークを作成する方が簡単です。
- 一般的に 「旅行」を検索するユーザーの場合は、表示される情報を含むトピックを "Travel" に作成します。 トピックの説明に、Concur 外部サイトへのリンクを追加する方法を検討してください。 代わりに、Microsoft 365 テナントでホストされている内部の旅行予約サイトへのリンクである場合は、"ピン留めされたリソース" に追加できます。
 
### <a name="search-results-priority"></a>検索結果の優先順位 
 
ユーザー検索エクスペリエンスでは、ユーザーが 「旅行」のような用語を検索すると、検索結果は Microsoft Search で次の優先度で表示されます。
1. 発行済みまたは確認済みトピック 
2. ブックマーク
3. お勧めするトピック 



