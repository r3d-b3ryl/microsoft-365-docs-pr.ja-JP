---
title: 事前電子情報開示の検索統計
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: コレクション検索を実行した後に生成される統計情報を表示して、検索結果を検証Advanced eDiscovery。
ms.openlocfilehash: d5eed0f888da717cbf68db837a6d9ff230dbf674
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2022
ms.locfileid: "61942082"
---
# <a name="search-statistics-in-advanced-ediscovery"></a>[検索] で統計情報をAdvanced eDiscovery

検索結果を検証する方法の 1 つは、結果に関する統計情報を確認して、期待に沿った結果を得る方法です。 検索が完了すると、検索の詳細フライアウトに高レベルの統計情報が表示されます。

- 検索によって取得されたアイテムの数とボリューム

- 検索場所で見つかった部分的にインデックス付きまたはインデックスのないアイテムの数とボリューム

- 検索されたメールボックスと場所の数。
より詳細な統計情報を表示するには、検索の詳細フライアウトから [統計情報] をクリックします。

## <a name="summary-view"></a>概要ビュー

[概要] ビューでは、検索結果を場所の種類 (例: Exchange) で表示できます。 場所の種類ごとに、次の情報を確認できます。

- 検索条件に一致するアイテムがあった場所の数

- 検索条件に一致したこれらの場所からのアイテムの数

- 検索条件に一致したアイテムの合計量。

## <a name="top-locations-view"></a>[上位の場所] ビュー

[上位の場所] ビューには、一致が最も多い個々の場所が表示されます。 場所ごとに、次の情報が表示されます。

- 場所名 (URL などSharePoint)

- 場所の種類

- 検索条件に一致したアイテムの数

- 検索条件に一致したアイテムの合計量。

## <a name="queries-view"></a>クエリ ビュー

クエリで (c:s) キーワードまたはキーワード行を使用している場合は、場所の種類ごとのクエリ ビューでクエリの内訳を確認できます。 場所の種類ごとに、次の情報が表示されます。

- パート: この列には、"Primary" または "Keyword" という単語があります。 "Primary" は、行がクエリ全体の統計情報を表示するのに対し、"Keyword" はクエリ コンポーネントの 1 つを意味します。

- クエリ: 行が参照する実際のクエリ コンポーネント。 Part が "Primary" の場合、これはクエリ全体です。Part が "Keyword" の場合は、クエリ コンポーネントの 1 つがここに表示されます。
  
  - (キーワードを指定しない) すべての contentin メールボックスを検索すると、実際のクエリは (サイズ >= 0) なので、すべてのアイテムが返されます。
  
  - SharePoint Online と OneDrive for Business サイトを検索すると、次の 2 つのコンポーネントが追加されます。
    
    - NOT IsExternalContent:1 - オンプレミスの組織からコンテンツをSharePointします
    
    - NOT isOneNotePage: 1 - 検索クエリに一致するドキュメントOneNote重複するファイルなので、すべてのファイルを除外します。

- 検索条件に一致するアイテムを含む場所の数。

- 検索条件に一致したこれらの場所からのアイテムの数。

- 検索条件に一致したアイテムの合計量。
