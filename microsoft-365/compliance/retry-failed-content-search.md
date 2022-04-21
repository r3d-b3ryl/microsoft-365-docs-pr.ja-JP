---
title: コンテンツ検索を再試行してコンテンツの場所エラーを解決する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 調査中に、[再試行] ボタンを使用して、コンテンツの場所エラーが発生したコンテンツ検索を解決できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9ded77dedc2c304e8a51b165ab6b5324cc5e78e3
ms.sourcegitcommit: caedcf7f16eed23596487d97c375d4bc4c8f3566
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2022
ms.locfileid: "64994020"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a>コンテンツ検索を再試行してコンテンツの場所エラーを解決する

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

セキュリティとコンプライアンス センターでコンテンツ検索を使用して多数のメールボックスを検索すると、次のような検索エラーが発生することがあります。

```text
Error


The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

これらのエラー (CS001-002、CS003-002、CS008-009、CS012-002 のエラー コード、および CS0XX-0XX 形式のその他のエラー) は、コンテンツ検索で特定のコンテンツの場所を検索できなかったことを示します。この例では、2 つのメールボックスが検索されませんでした。 これらのエラーは、コンテンツ検索の状態の詳細ポップアップ ページに表示されます。

## <a name="cause-of-content-location-errors"></a>コンテンツの場所エラーの原因

多数のメールボックスを検索する場合、検索は Microsoft データセンター内の数千台のサーバーに分散されます。 一度に、特定のサーバーが再起動状態になるか、冗長コピーにフェールオーバー中である可能性があります。 いずれの場合も、コンテンツ検索によるデータの取得要求はタイムアウトになります。前の例では、失敗したメールボックスのエラーは、検索タイムアウトの結果でした。

## <a name="resolving-content-location-errors"></a>コンテンツの場所エラーの解決

多くの場合、検索を再開すると、異なるサーバーで同様のエラーが発生します。 検索を再開する代わりに、検索結果ページの上部に表示される **[再試行** ] ボタンをクリックします。

![[再試行] ボタンをクリックして、コンテンツの場所のエラーを解決します。](../media/retrycontentsearch3.png)

これにより、失敗したメールボックスについてのみ検索が再試行されます。 検索を再試行すると、正常に返された他の結果が保持されます。

## <a name="tips-to-avoid-content-location-errors"></a>コンテンツの場所のエラーを回避するためのヒント

コンテンツの場所のエラーのその他の原因と、多数のメールボックスを検索するときにそれらを回避するのに役立つヒントを次に示します。

- ユーザー アクティビティが原因で、検索対象のメールボックスがビジー状態になっている可能性があります。 この場合、検索サービスは、メールボックスが使用できないように調整する可能性があります。 これを回避するには、営業時間外に検索を実行してみてください。

- 検索クエリがメールボックスから取得するコンテンツが多すぎる可能性があります。 可能であれば、キーワード、日付範囲、検索条件を使用して検索範囲を絞り込みます。

- キーワード リストを使用して検索クエリを作成するときに、 [キーワードまたはキーワード](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches) フレーズが多すぎます。 キーワード リストを使用する検索クエリを実行すると、サービスは基本的にキーワード リスト内の各行に対して個別の検索を実行し、統計情報を生成できるようにします。 検索クエリでキーワード リストを使用している場合は、キーワード リスト内の行数を最小限に抑えるか、数値キーワードを小さいリストに分割して、キーワード リストごとに異なる検索を作成します。

  > [!NOTE]
  > 大規模なキーワード リストによって生じる問題を軽減するため、検索クエリのキーワード リストの行は最大 20 行に設定されています。

- 同じメールボックスで同時に実行されている検索が多すぎます。 可能であれば、任意の 1 つのメールボックスで一度に 1 回の検索を実行してみてください。

- 1 回の検索でメールボックスを検索する回数が多すぎます。 多数のメールボックスを検索すると、コンテンツの場所エラーの確率が高くなります。 可能であれば、各検索に組織内のメールボックスのサブセットが含まれるように、複数の検索を実行してみてください。

- メールボックスで必要なメンテナンスが実行されています。 この原因はほとんど発生しませんが、コンテンツの場所エラーを受け取ってから少し待ってから、検索を再試行してください。
