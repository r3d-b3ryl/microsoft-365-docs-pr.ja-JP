---
title: Advanced eDiscovery で検索クエリを作成する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-mar2020
description: Microsoft 365 の Advanced eDiscovery を使用してデータを検索する場合は、キーワードと条件を使用して検索範囲を絞り込む。
ms.openlocfilehash: 8ec1e099625bb081f8a915f08ac818fddcc2b60d
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751114"
---
# <a name="build-search-collection-queries-in-advanced-ediscovery"></a>Advanced eDiscovery で検索コレクション クエリを作成する

Advanced eDiscovery ケースでデータを収集する検索クエリを作成する場合、キーワードを使用して特定のコンテンツと条件を検索し、検索範囲を絞り込み、法的調査に最も関連するアイテムを返します。

![キーワードと条件を使用して検索の結果を絞り込む](../media/SearchQueryBox.png)

## <a name="keyword-searches"></a>キーワード検索

検索クエリの [キーワード] **ボックス** にキーワード クエリを入力します。 キーワード、電子メール メッセージのプロパティ (送信日と受信日など)、またはドキュメントのプロパティ (ファイル名やドキュメントが最後に変更された日付など) を指定できます。 **AND**、**OR**、**NOT**、**NEAR** などのブール演算子を使用するより複雑なクエリを使用できます。 また、SharePoint と OneDrive のドキュメント (電子メール メッセージではなく) で機密情報 (社会保障番号など) を検索したり、外部で共有されているドキュメントを検索したりすることもできます。 この **キーワード** ボックスを空のままにすると、指定したコンテンツの場所にあるすべてのコンテンツが検索結果に入ります。

## <a name="keyword-list"></a>キーワード リスト

または、[キーワード リストを表示する] チェック ボックス **をオンにして** 、各行にキーワードまたはキーワード フレーズを入力することもできます。 各行のキーワードは、作成される検索クエリの **OR** 演算子と同様の機能を持つ論理演算子 (検索クエリ構文では *c:s* として表されます) によって接続されます。 つまり、任意の行にキーワードを含むアイテムが検索結果に表示されます。 Advanced eDiscovery 検索クエリでは、キーワード リストに最大 180 行を追加できます。

![キーワード リストを使用してクエリ内の各キーワードの統計情報を取得する](../media/KeywordListSearch.png)

キーワード リストを使用する理由 キーワード リスト内の各キーワードに一致するアイテムの数を示す統計情報を取得できます。 これにより、最も効果的な (かつ最も少ない) キーワードをすばやく識別できます。 キーワード リスト内の行でキーワード フレーズ (かっこで囲む) を使用できます。 検索統計の詳細については、「検索統計」 [を参照してください](search-statistics-in-advanced-ediscovery.md)。

## <a name="conditions"></a>条件

検索条件を追加して検索範囲を絞り込み、より絞り込みされた結果セットを返します。 各条件によって、作成された検索クエリに句が追加され、ユーザーが検索を開始するとそのクエリが実行されます。 条件は、AND 演算子と同様の機能を持つ論理演算子 (検索クエリ構文では *c:c* として表されます) によって、キーワード ボックスで指定されたキーワード クエリに論理的に接続されます。 つまり、アイテムはキーワード クエリと検索結果に含まれる 1 つ以上の条件の両方を満たす必要があります。 このように、条件を使用して結果を絞り込むことができます。 検索クエリで使用できる条件の一覧と説明については、キーワード クエリと検索条件の「検索条件」セクション [を参照してください](keyword-queries-and-search-conditions.md#search-conditions)。
