---
title: コンテンツを検索する
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
description: Microsoft Purview コンプライアンス ポータルのコンテンツ検索電子情報開示ツールを使用すると、Exchange メールボックス内の電子メール、SharePoint サイトやOneDriveの場所のドキュメント、Skype for Businessのインスタント メッセージング会話をすばやく見つけることができます。
ms.openlocfilehash: cf5c6b61e9b4cc041d9f8e315321c63c78415a63
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2022
ms.locfileid: "66009433"
---
# <a name="search-for-content-using-the-content-search-tool"></a>コンテンツ検索ツールを使用してコンテンツを検索します

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Microsoft Purview コンプライアンス ポータルのコンテンツ検索ツールを使用して、Exchange メールボックスのメール、SharePoint サイトおよび OneDrive ロケーションのドキュメント、Skype for Business のインスタント メッセージングの会話をすばやく検索できます。 コンテンツ検索ツールは、Microsoft Teams や Microsoft 365 グループなどのコラボレーション ツール内のメール、ドキュメント、インスタント メッセージングの会話を検索するために使用できます。
  
## <a name="search-for-content"></a>コンテンツを検索する

最初の手順では、コンテンツ検索ツールを使用してコンテンツの場所を選択し、特定のアイテムを検索するキーワード クエリを検索および構成します。 または、クエリを空白のままにして、ターゲットの場所のすべてのアイテムを返すこともできます。
  
- コンテンツ検索[を作成して実行](content-search.md)する

- [検索クエリを作成し、条件を使用](keyword-queries-and-search-conditions.md) して検索を絞り込む

- コンテンツ検索の[機能リファレンス](content-search-reference.md)

- 電子情報開示マネージャーが組織内のメールボックスまたはサイトのサブセットのみを検索できるように、[検索アクセス許可フィルターを構成](permissions-filtering-for-content-search.md)する

- Microsoft 365のオンプレミス ユーザーの[クラウドベースのメールボックスを検索](search-cloud-based-mailboxes-for-on-premises-users.md)する

- 検索結果の[キーワード統計を表示](view-keyword-statistics-for-content-search.md)し、必要に応じてクエリを絞り込みます

- 組織がMicrosoft 365にインポートした[サード パーティのデータを検索](use-content-search-to-search-third-party-data-that-was-imported.md)する

- [Bcc 受信者を](/exchange/policy-and-compliance/holds/preserve-bcc-recipients-and-group-members) 検索できるように保持する

## <a name="perform-actions-on-content-you-find"></a>見つけたコンテンツに対してアクションを実行する

検索を実行し、必要に応じて絞り込んだ後、次の手順では、検索によって返された結果を使用して何かを行います。 結果をエクスポートしてローカル コンピューターにダウンロードするか、組織に対する電子メール攻撃の場合は、ユーザー メールボックスから検索結果を削除できます。
  
- [コンテンツ検索の結果をエクスポート](export-search-results.md) し、ローカル コンピューターにダウンロードする

- ウイルス、危険な添付ファイル、フィッシング メッセージを含むメッセージなど、[電子メール](search-for-and-delete-messages-in-your-organization.md) メッセージを検索して削除する

- 実際[の結果をエクスポート](export-a-content-search-report.md)せずに、コンテンツ検索の結果に関するレポートをエクスポートする

## <a name="learn-more-about-content-search"></a>コンテンツ検索の詳細を確認する

コンテンツ検索は使いやすいですが、強力なツールでもあります。 バックグラウンドでは、多くの作業が行われています。 そのことを理解し、その動作とその制限事項を理解すればするほど、組織の検索と調査のニーズに合わせて使用できるようになります。 以下について調べます。
  
- [一](limits-for-content-search.md)度に実行できる検索の最大数や、1 回の検索に含めることができるコンテンツの場所の最大数など、コンテンツ検索の制限

- 検索結果をエクスポートおよびダウンロードするときに、[推定検索結果と実際の検索結果](differences-between-estimated-and-actual-ediscovery-search-results.md)、およびそれらの間に違いがある可能性がある理由

- [ExchangeおよびSharePoint内の部分的にインデックスが作成されたアイテム](partially-indexed-items-in-content-search.md)と、検索結果をエクスポートおよびダウンロードするときにアイテムを含めたり除外したりする方法

- [部分的にインデックスが作成されたアイテムを調査](investigating-partially-indexed-items-in-ediscovery.md) し、組織がそれらのアイテムに公開しているかどうかを判断する

- [検索結果の重複を取](de-duplication-in-ediscovery-search-results.md) り除き、検索結果である電子メール メッセージをエクスポートするときに有効にすることができます。

## <a name="use-scripts-for-advanced-scenarios"></a>高度なシナリオにスクリプトを使用する

場合によっては、より高度で複雑で反復的なコンテンツ検索タスクを実行する必要があります。 このような場合は、Security & Compliance PowerShell でコマンドを使用する方が簡単で高速です。 これを簡単にするために、複雑なコンテンツ検索関連のタスクを完了するために、セキュリティ &コンプライアンス PowerShell スクリプトを多数作成しました。

- ケースに対応するアイテムがそのフォルダー内にあると確信している場合は、[特定のメールボックスフォルダーとサイト](use-content-search-for-targeted-collections.md) フォルダー (*ターゲット* コレクションと呼ばれます) を検索する

- [メールボックスとOneDrive場所を検索](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md)して、ユーザーの一覧を探します

- [複数の検索を作成、レポート、削除して、](create-report-on-and-delete-multiple-content-searches.md) 検索データを迅速かつ効率的に識別およびカリングする

- [コンテンツ検索を複製](clone-a-content-search.md) し、同じコンテンツの場所で実行されるさまざまなキーワード検索クエリの結果をすばやく比較します。またはスクリプトを使用して、新しい検索を作成するときに多数のコンテンツの場所を再入力する必要がないことで時間を節約します
