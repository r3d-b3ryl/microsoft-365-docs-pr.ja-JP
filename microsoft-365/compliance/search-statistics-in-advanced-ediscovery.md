---
title: Advance eDiscovery での検索統計
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Advanced eDiscovery でコレクション検索を実行した後に生成される統計情報を表示して、検索結果を検証します。
ms.openlocfilehash: 5b6cfdaffc7851a00035a4edcc9d490b229c455d
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750778"
---
# <a name="search-statistics-in-advanced-ediscovery"></a>Advanced eDiscovery の検索統計

検索結果を検証する 1 つの方法は、結果に関する統計情報を確認して、期待に沿った結果を確認する方法です。 検索が完了すると、検索の詳細のフライアウトに高レベルの統計情報が表示されます。

- 検索によって取得されたアイテムの数と量

- 検索場所で見つかった、部分的にインデックスが作成されたアイテムまたはインデックスのないアイテムの数と量

- 検索されたメールボックスと場所の数。
より詳細な統計情報を表示するには、検索の詳細のフライアウトから [統計情報] をクリックします。

## <a name="summary-view"></a>概要ビュー

[概要] ビューでは、場所の種類 (Exchange など) 別に検索結果が表示されます。 場所の種類ごとに、次の情報が表示されます。

- 検索条件に一致するアイテムを含む場所の数

- 検索条件に一致したこれらの場所からのアイテムの数

- 検索条件に一致したアイテムの合計量。

## <a name="top-locations-view"></a>[上位の場所] ビュー

[上位の場所] ビューには、最も一致する場所が個別に表示されます。 場所ごとに、次の情報が表示されます。

- 場所名 (例: SharePoint URL)

- 場所の種類

- 検索条件に一致したアイテムの数

- 検索条件に一致したアイテムの合計量。

## <a name="queries-view"></a>クエリ ビュー

クエリで (c:s) キーワードまたはキーワード行を使用した場合は、場所の種類ごとにクエリ ビューでクエリの詳細を表示できます。 場所の種類ごとに、次の情報が表示されます。

- パート: この列には、単語 "Primary" または "Keyword" が含まれる。 "Primary" は、行がクエリ全体に統計情報を表示し、"キーワード" はクエリ コンポーネントの 1 つを意味します。

- クエリ: 行が参照する実際のクエリ コンポーネント。 Part が "Primary" の場合、これはクエリ全体です。Part が "Keyword" の場合、クエリ コンポーネントの 1 つがここに表示されます。
  
  - (キーワードを指定しない) すべてのコンテンツ イン メールボックスを検索する場合、実際のクエリは (サイズ >= 0) なので、すべてのアイテムが返されます。
  
  - SharePoint Online と OneDrive for Business サイトを検索すると、次の 2 つのコンポーネントが追加されます。
    
    - NOT IsExternalContent:1 - オンプレミスの SharePoint 組織からコンテンツを除外します
    
    - NOT isOneNotePage: 1 - 検索クエリに一致するドキュメントが重複する可能性がある OneNote ファイルはすべて除外されます。

- 検索条件と一致するアイテムを含む場所の数。

- 検索条件に一致したこれらの場所からのアイテムの数。

- 検索条件に一致したアイテムの合計量。
