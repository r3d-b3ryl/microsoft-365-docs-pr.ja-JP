---
title: コンテンツを検索する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
description: Microsoft 365 コンプライアンス センター のコンテンツ検索電子情報開示ツールを使用して、Exchange メールボックス内の電子メール、SharePoint サイトと OneDrive の場所のドキュメント、Skype for Business でのインスタント メッセージング会話をすばやく検索します。
ms.openlocfilehash: 577b3af2bbeb1856f55de31123b71f2597c6604a
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59175791"
---
# <a name="search-for-content-using-the-content-search-tool"></a>コンテンツ検索ツールを使用してコンテンツを検索する

Microsoft 365 コンプライアンス センター のコンテンツ検索ツールを使用して、Exchange メールボックス内の電子メール、SharePoint サイトと OneDrive の場所のドキュメント、Skype for Business でのインスタント メッセージング会話をすばやく検索します。 コンテンツ検索ツールを使用して、メール、ドキュメント、インスタント メッセージングの会話を、グループやグループなどのコラボレーション Microsoft Teams検索Microsoft 365できます。
  
## <a name="search-for-content"></a>コンテンツを検索する

最初の手順は、コンテンツ検索ツールを使用してコンテンツの場所を選択し、特定のアイテムを検索するキーワード クエリを検索して構成します。 または、クエリを空白のままにして、ターゲットの場所のすべてのアイテムを返す方法があります。
  
- [コンテンツ検索の](content-search.md) 作成と実行

- [コンテンツ検索の](content-search-reference.md) 機能参照

- [検索クエリを作成し、条件を使用して](keyword-queries-and-search-conditions.md) 検索を絞り込む

- [電子情報開示マネージャーが](permissions-filtering-for-content-search.md) 組織内のメールボックスまたはサイトのサブセットのみを検索できるよう、検索アクセス許可フィルターを構成する

- [ID リスト検索を実行して](csv-file-for-an-id-list-content-search.md) 特定の電子メール メッセージを検索する

- [クラウド ベースのメールボックスを検索](search-cloud-based-mailboxes-for-on-premises-users.md)して、ユーザー内のオンプレミス ユーザー Microsoft 365

- [検索結果のキーワード統計](view-keyword-statistics-for-content-search.md) を表示し、必要に応じてクエリを絞り込む

- [組織がインポートしたサード](use-content-search-to-search-third-party-data-that-was-imported.md)パーティ製のデータを検索Microsoft 365

- [コンテンツの場所エラーを解決](retry-failed-content-search.md) するためにコンテンツ検索を再試行する

- [BCC 受信者を保持](/exchange/policy-and-compliance/holds/preserve-bcc-recipients-and-group-members) してそれらを検索する

## <a name="perform-actions-on-content-you-find"></a>見つけたコンテンツに対してアクションを実行する

検索を実行し、必要に応じて絞り込み後、次の手順では、検索によって返される結果を使用して何かを行います。 結果をエクスポートしてローカル コンピューターにダウンロードするか、組織に対する電子メール攻撃の場合は、ユーザー メールボックスから検索の結果を削除できます。
  
- [コンテンツ検索の結果をエクスポートし](export-search-results.md) 、ローカル コンピューターにダウンロードする

- [ウイルス、危険な添付ファイル](search-for-and-delete-messages-in-your-organization.md)、フィッシング メッセージを含むメッセージなどの電子メール メッセージを検索および削除する

- [実際の結果を](export-a-content-search-report.md) エクスポートせずに、コンテンツ検索の結果に関するレポートをエクスポートする

## <a name="learn-more-about-content-search"></a>コンテンツ検索の詳細

コンテンツ検索は使いやすいですが、強力なツールです。 舞台裏では、多くの問題が起こっています。 その動作とその制限を理解すればする度に、組織の検索と調査のニーズに使用できます。 以下について調べます。
  
- [検索結果をエクスポートおよびダウンロードするときに](partially-indexed-items-in-content-search.md)、ExchangeおよびSharePointに部分的にインデックス付けされたアイテムと、それらを含めるまたは除外する方法

- [部分的にインデックス付けされたアイテムを調査](investigating-partially-indexed-items-in-ediscovery.md) し、組織のアイテムへの露出を判断する

- [コンテンツ検索ツール](limits-for-content-search.md)の制限 (一度に実行できる検索の最大数、1 回の検索に含めるコンテンツの場所の最大数など)

- [推定検索結果と実際の](differences-between-estimated-and-actual-ediscovery-search-results.md) 検索結果、および検索結果のエクスポートおよびダウンロード時に違いがある理由

- [検索の結果である電子メール](de-duplication-in-ediscovery-search-results.md) メッセージをエクスポートするときに有効にできる検索結果の重複を除外する

## <a name="use-scripts-for-advanced-scenarios"></a>高度なシナリオでスクリプトを使用する

場合によっては、より高度で複雑で繰り返しのコンテンツ検索タスクを実行する必要があります。 このような場合は、セキュリティ センター PowerShell でコマンドを使用する方&速くなります。 これを容易にするために、複雑なコンテンツ検索関連のタスクを完了するのに役立つ、&コンプライアンス センター PowerShell スクリプトを多数作成しました。

- [ケースに対応する](use-content-search-for-targeted-collections.md) アイテムがフォルダー内にあると確信している場合に、特定のメールボックスおよびサイト フォルダー (*ターゲット コレクションと呼ばれる) を検索する

- [メールボックスとユーザーのOneDrive場所](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md)を検索する

- [複数の検索を作成、レポート、および削除](create-report-on-and-delete-multiple-content-searches.md) して、検索データをすばやく効率的に識別し、検索する

- [コンテンツ検索を複製し](clone-a-content-search.md) 、同じコンテンツの場所で実行されるさまざまなキーワード検索クエリの結果をすばやく比較します。または、新しい検索を作成するときに多数のコンテンツの場所を再入力する必要がなかから、スクリプトを使用して時間を節約する