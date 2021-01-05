---
title: Advanced eDiscovery のケースのデータを収集する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Advanced eDiscovery の検索ツールを使用して、調査でレビューするドキュメント セットを識別する方法について説明します。
ms.custom: seo-marvel-2020
ms.openlocfilehash: b69127f1a372a9b843b9c7dac1b2909dd80b2988
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751271"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a>Advanced eDiscovery のケースのデータを収集する

ケースに関心のあるカストディアンとデータ ソースを特定したら、次に、詳細を確認するドキュメントのセットを特定します。 Advanced eDiscovery の検索ツールを使用して、Microsoft 365 の保管場所と保管場所以外の場所から関連するドキュメントを識別できます。

検索を実行すると、検索クエリに一致したアイテムが最も多かった場所など、取得したアイテムの統計情報を表示できます。 結果のサブセットをプレビューできます。 さらに調べるドキュメントのセットを特定した後、検索結果をレビュー セットに追加して、収集と処理を行います。

## <a name="create-a-search"></a>検索を作成する

[検索 **] タブで**[新しい検索] を選択すると、検索を作成するためのウィザードが開始されます。  検索を作成する方法の詳細については、「データを収集する検索を作成 [する」を参照してください](create-search-to-collect-data.md)。

検索が作成されると、詳細を含むフライアウト ページが表示されます。 [**統計情報]****ボタンと**[プレビュー] ボタンは、検索がまだ完了していないので、最初は使用できません。 [検索] タブでは、検索の進行状況 **を追跡** できます。

## <a name="view-search-results-and-statistics"></a>検索結果と統計情報を表示する

コンテンツ検索には、統計情報 (推定値) とプレビューの 2 つのコンポーネントがあります。 これらの各コンポーネントが完了すると、[検索] タブの対応する列に状態が表示され、[送信済み]から[進行中] から [完了] に変 **わります**。

検索の推定が完了したら、検索を選択してフライアウト ページを表示します。このページには、検索の結果に関する高レベルの統計情報が表示されます。 この時点で、[統計情報 **] ボタン** がアクティブになります。 このオプションを選択すると、次のような検索統計を表示できます。

- 概要
- トップの場所
- クエリ

検索統計の詳細については、「検索統計」 [を参照してください](search-statistics-in-advanced-ediscovery.md)。

プレビューが完了すると、[プレビュー] **ボタン** がアクティブになります。 結果のサンプリングされたサブセットをプレビューするには、このオプションを選択します。

## <a name="add-search-results-to-a-review-set"></a>検索結果をレビュー セットに追加する

検索の結果全体を収集して処理する準備ができたら、それをレビュー セットに追加します。 詳細については、「レビュー セット [にデータを追加する」を参照してください](add-data-to-review-set.md)。

## <a name="add-non-microsoft-365-data-to-a-review-set"></a>Microsoft 365 以外のデータをレビュー セットに追加する

ケースの収集プロセスの一環として、Office 365 以外のデータをレビュー セットに追加し、検索ツールを使用して収集した Office 365 データと共にレビューおよび分析することもできます。 365 以外Office追加する場合は、ケース内の特定のカストディアンに関連付ける必要があります。 詳細については [、「Microsoft 365 以外のデータをレビュー セットに読み込む」を参照してください](load-non-Office-365-data-into-a-review-set.md)。
