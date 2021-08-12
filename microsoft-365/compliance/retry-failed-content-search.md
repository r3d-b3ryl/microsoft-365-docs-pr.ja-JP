---
title: コンテンツ検索を再試行してコンテンツの場所のエラーを解決する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 調査中に、[再試行] ボタンを使用して、コンテンツの場所にエラーがあるコンテンツ検索を解決できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a67702e7c9d3c307ed44fe52c86c8b080f8d1e01e7cf9dcdc9dfb3929c638bf6
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53795679"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a>コンテンツ検索を再試行してコンテンツの場所のエラーを解決する

セキュリティとコンプライアンス センターでコンテンツ検索を使用して多数のメールボックスを検索すると、次のような検索エラーが発生することがあります。

```text
Error


The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

これらのエラー (CS001-002、CS003-002、CS008-009、CS012-002、および CS0XX-0XX という形式の他のエラーのエラーを含む) は、コンテンツ検索が特定のコンテンツの場所を検索できなかったかどうかを示します。この例では、2 つのメールボックスが検索されません。 これらのエラーは、コンテンツ検索の [状態の詳細] フライアウト ページに表示されます。

## <a name="cause-of-content-location-errors"></a>コンテンツの場所エラーの原因

多数のメールボックスを検索する場合、検索は Microsoft データセンター内の何千ものサーバーに分散されます。 一度に、特定のサーバーが再起動状態にあるか、冗長コピーにフェールオーバーする過程にある可能性があります。 どちらの場合も、データを取得するコンテンツ検索の要求はタイム アウトします。前の例では、失敗したメールボックスのエラーは、検索のタイミングアウトの結果です。

## <a name="resolving-content-location-errors"></a>コンテンツの場所のエラーの解決

検索を再開すると、多くの場合、異なるサーバーで同様のエラーが発生します。 検索を再開する代わりに、検索結果ページの上部に表示される [再試行] ボタンをクリックします。

![[再試行] ボタンをクリックしてコンテンツの場所のエラーを解決する](../media/retrycontentsearch3.png)

これにより、失敗したメールボックスの検索のみを再試行します。 検索を再試行すると、正常に返された他の結果は保持されます。

## <a name="tips-to-avoid-content-location-errors"></a>ヒント場所のエラーを回避する方法

コンテンツの場所のエラーの追加の原因と、多数のメールボックスを検索するときにそれらを回避するためのヒントを次に示します。

- ユーザーアクティビティが原因で、検索中のメールボックスがビジー状態になる可能性があります。 この場合、検索サービスは、メールボックスが使用できなくなるのを防ぐために、それ自体を調整する可能性があります。 これを回避するには、営業時間外に検索を実行してみてください。

- 検索クエリがメールボックスからコンテンツを取得しすぎる可能性があります。 可能であれば、キーワード、日付範囲、および検索条件を使用して検索範囲を絞り込もうとします。

- キーワード リストを使用して検索クエリを作成すると、キーワードまたはキーワード 語句 [が多すぎます](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches)。 キーワード リストを使用する検索クエリを実行すると、サービスは基本的にキーワード リスト内の各行に対して個別の検索を実行し、統計情報を生成できます。 検索クエリでキーワード リストを使用している場合は、キーワード リスト内の行数を最小限にするか、数値キーワードを小さいリストに分割し、各キーワード リストに対して異なる検索を作成します。

  > [!NOTE]
  > 大規模なキーワード リストによって生じる問題を軽減するため、検索クエリのキーワード リストの行は最大 20 行に設定されています。

- 同じメールボックスで同時に実行される検索が多すぎます。 可能であれば、任意の 1 つのメールボックスで一度に 1 つの検索を実行してみてください。

- 1 つの検索で多くのメールボックスを検索する。 多数のメールボックスを検索すると、コンテンツの場所エラーの確率が高くなっています。 可能であれば、複数の検索を実行して、各検索に組織内のメールボックスのサブセットが含まれるのを試してください。

- メールボックスで必要なメンテナンスが実行されています。 この原因はおそらくまれに発生しますが、コンテンツの場所エラーを受け取った後少し待って、検索を再試行してください。
