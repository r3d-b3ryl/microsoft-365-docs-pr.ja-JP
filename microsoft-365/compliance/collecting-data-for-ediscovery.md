---
title: 高度な電子情報開示でケースのデータを収集する
f1.keywords:
- NOCSH
ms.author: esclee
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
description: ''
ms.openlocfilehash: 462c58f8531265026b34fe3d8484736aefa4c5fa
ms.sourcegitcommit: 72e43b9bf85dbf8f5cf2040ea6a4750d6dc867c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2020
ms.locfileid: "43799940"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a>高度な電子情報開示でケースのデータを収集する

ケースに関係のある保管担当者およびデータソースを特定したら、詳細についてのドキュメントを特定します。 上級電子情報開示の検索ツールを使用して、Microsoft 365 の custodial および非 wi-fi ダイヤルの場所から関連するドキュメントを識別できます。

検索を実行すると、検索クエリに一致したアイテムが最も多い場所など、取得したアイテムの統計情報を表示できます。 結果のサブセットをプレビューすることもできます。 さらに調査するドキュメントのセットを特定したら、検索結果をレビューセットに追加して、収集して処理することができます。

## <a name="create-a-search"></a>検索を作成する

[**検索] タブの [** **新しい検索**] を選択すると、検索を作成するためのガイドとなるウィザードが起動します。 検索を作成する方法の詳細については、「[データを収集するための検索を作成する](create-search-to-collect-data.md)」を参照してください。

検索が作成されると、詳細情報を含むフライアウトページが表示されます。 検索がまだ完了していないため、[**統計**] および [**プレビュー** ] ボタンは最初は使用できません。 検索の進行状況を追跡するには、[**検索**] タブを使用します。

## <a name="view-search-results-and-statistics"></a>検索結果と統計情報を表示する

コンテンツ検索には、統計 (見積り) とプレビューという2つのコンポーネントがあります。 これらの各コンポーネントが完了すると、[**検索**] タブの対応する列に [**送信****済み**] から [**進行**中] に変更された状態が表示されます。

検索の推定が完了したら、検索を選択すると、検索結果に関する大まかな統計情報が表示される、フライアウトページが表示されます。 この時点で、[**統計**] ボタンがアクティブになります。 このチェックボックスをオンにすると、次のような検索統計情報を表示できます。

- 要約
- トップの場所
- クエリ

検索統計の詳細については、「[検索統計](search-statistics.md)」を参照してください。

プレビューが完了すると、[**プレビュー** ] ボタンがアクティブになります。 このチェックボックスをオンにして、抽出された結果のサブセットをプレビューします。

## <a name="add-search-results-to-a-review-set"></a>検索結果をレビュー セットに追加する

検索結果全体を収集して処理する準備ができたら、それをレビューセットに追加することで、それを行うことができます。 詳細については、「[レビューセットにデータを追加する](add-data-to-review-set.md)」を参照してください。

## <a name="add-non-microsoft-365-data-to-a-review-set"></a>Microsoft 以外の365データをレビューセットに追加する

ケースのコレクションプロセスの一部として、Office 以外の365データをレビューセットに追加し、検索ツールを使用して収集した Office 365 データと一緒に確認して分析することもできます。 Office 以外の365を追加する場合は、そのようなを特定の保管担当者に関連付ける必要があります。 詳細については、「 [Microsoft 以外の365データをレビューセットに読み込む](load-non-Office-365-data-into-a-review-set.md)」を参照してください。
