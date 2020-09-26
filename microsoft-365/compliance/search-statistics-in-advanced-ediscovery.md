---
title: 高度電子情報開示の検索統計
f1.keywords:
- NOCSH
ms.author: markjjo
author: esclee
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
description: 高度な電子情報開示でコレクション検索を実行した後に生成された統計情報を表示して、検索結果を検証します。
ms.openlocfilehash: ef5653a76d94272ba5f608149648f1421198929a
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286083"
---
# <a name="search-statistics-in-advanced-ediscovery"></a>高度な電子情報開示の検索統計

検索結果を検証する方法の1つは、結果に関する統計を調べて、期待どおりに配置されるようにすることです。 検索が完了すると、高度な統計情報が検索の詳細ポップアップに表示されます。

- 検索によって取得されたアイテムの数とボリューム

- 検索場所で見つかった、部分的にインデックスまたはインデックス付けされていないアイテムの数とボリューム

- 検索されたメールボックスと場所の数。
詳細な統計情報を表示するには、検索の詳細ポップアップから [統計] をクリックします。

## <a name="summary-view"></a>概要ビュー

概要ビューでは、検索結果が場所の種類 (例: Exchange) ごとに分類されて表示されます。 場所の種類ごとに、次の情報が表示できます。

- 検索条件に一致したアイテムがある場所の数

- 検索条件に一致したこれらの場所からのアイテムの数

- 検索条件に一致したアイテムの合計量。

## <a name="top-locations-view"></a>トップの場所ビュー

上部の [場所] ビューには、最も一致がある個々の場所が表示されます。 場所ごとに、次の情報が表示されます。

- 場所の名前 (例: SharePoint URL)

- 場所の種類

- 検索条件に一致したアイテムの数

- 検索条件に一致したアイテムの合計量。

## <a name="queries-view"></a>クエリビュー

クエリで (c:s) キーワードまたはキーワード行を使用している場合は、場所の種類ごとのクエリビューにクエリのブレークダウンを表示できます。 場所の種類ごとに、次のように表示されます。

- Part: この列には、"Primary" または "Keyword" という単語が表示されます。 "Primary" は、クエリ全体に対して行が統計情報を表示することを意味し、"Keyword" は1つのクエリコンポーネントを表します。

- クエリ: 行が参照している実際のクエリコンポーネントです。 Part が "Primary" の場合、これはクエリ全体になります。Part が "Keyword" であった場合は、クエリコンポーネントのいずれかがここに表示されます。
  
  - キーワードを指定せずにすべての contentin メールボックスを検索すると、実際のクエリは (size >= 0)、すべてのアイテムが返されるようになります。
  
  - SharePoint Online と OneDrive for Business サイトを検索すると、次の 2 つのコンポーネントが追加されます。
    
    - NOT IsExternalContent: 1-オンプレミスの SharePoint 組織からコンテンツを除外する
    
    - NOT isOneNotePage: 1-すべての OneNote ファイルを除外します。これは、検索クエリに一致するドキュメントと重複する可能性があるためです。

- 検索条件に一致したアイテムがある場所の数。

- 検索条件に一致したこれらの場所からのアイテムの数。

- 検索条件に一致したアイテムの合計量。
