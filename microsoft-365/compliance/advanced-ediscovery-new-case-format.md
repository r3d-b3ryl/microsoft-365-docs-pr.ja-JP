---
title: 新しい大文字と小文字のAdvanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: ninachen
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
description: 新しいケース形式を使用して、Advanced eDiscoveryアイテムを追加してセットを確認し、その他の制限や新機能を活用できます。
ms.openlocfilehash: 9b0e87e7d24565bb89444fe5b1e5cbf43d915e42
ms.sourcegitcommit: 7f0c5b55e2966c0c1ce6a153a4e6a7ec035bd818
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2021
ms.locfileid: "61137199"
---
# <a name="use-the-new-case-format-in-advanced-ediscovery"></a>新しい大文字と小文字の形式をAdvanced eDiscovery

より多くの組織が、重要な電子情報開示プロセスAdvanced eDiscoveryソリューションMicrosoft 365ソリューションを使用しています。 これには、規制の要求、調査、訴訟への対応などがあります。 ユーザーの使用Advanced eDiscovery増えるに従って、一般的な顧客の要件は、1 つのケースで管理できるコンテンツの合計量をAdvanced eDiscoveryです。 データ量の合計とアイテムの総数の両方で、ケース サイズが大幅に増加した場合に対応するために、ケースを作成するときに新しいケース形式Advanced eDiscoveryできます。  

## <a name="create-a-case"></a>ケースを作成する

新しいケース形式をAdvanced eDiscoveryケースを作成するには、次のコマンドを実行します。

1. <https://compliance.microsoft.com> に移動し、サインインします。

2. [詳細] ウィンドウの左側のナビゲーション ウィンドウMicrosoft 365 コンプライアンス センター、[**電子情報開示**] >クリックします。

3. [ケースの **Advanced eDiscovery]** ページで、[ケース] タブをクリックし、[ケースの作成 **] をクリックします**。

   [ **新しい電子情報開示ケース]** フライアウト ページが表示されます。 [ **ケース形式]** セクションには、新しい形式を使用してケースを作成するオプションがあります。

   ![[新しい電子情報開示ケース] ページの [新しいケース形式] オプション。](..\media\AeDNewCaseFormat1.png)

4. ケースの名前を付けて、[新規] オプション **を** 選択し、[保存] をクリックして、新しい形式を使用してケースを作成します。

## <a name="benefits-of-the-new-case-format"></a>新しいケース形式の利点

新しいケース形式では、4,000 万件を超えるアイテムを含むケースを管理できます。 この機能は、電子情報開示ワークフロー全体を通じて大量のケース データを効果的に管理するのに役立ちます。

ワークフローの大規模なケースのその他の利点のAdvanced eDiscoveryします。

- **コレクション**: 新しいケース形式では、1 つのコレクションに対して最大 1 TB のデータを収集できます。

   各ケースで、コレクションの設定は既定でクラウドの添付ファイルとコンテキスト コンテンツを収集TeamsおよびYammerされます。 これらの設定は、調査内のデジタル通信の全体像を収集するのに役立ちます。 Teams および Yammer コンテキスト会話の場合、新しいケース形式は、1:1、1:N、チャネルの会話の時間ベースのスナップショットを HTML トランスクリプトに変換し、会話のコンテキストを提供し、チャット ベースのコンテンツによって生成されるアイテムの総数を減らすのに役立ちます。  

- **レビュー**: 各レビュー セットは、拡張前コンテンツを最大 1 TB までサポートします。 その他のメタデータは、チーム名、チャネル名、会話名などのフィルターやクエリで、コンテンツのTeamsされます。 各トランスクリプトには、レスポンシブ アイテムの前と後の時間ベースのコンテンツが含まれます。 チャネルの会話では、ルート投稿とすべての返信がレスポンシブ コンテンツ用に収集されます。 詳細については、「Advanced eDiscoveryのコンテンツMicrosoft Teams[ワークフロー (プレビュー)」を参照してください。](teams-workflow-in-advanced-ediscovery.md)

- **エクスポート**: 1 つのエクスポート ジョブで大きなコンテンツ セットをエクスポートできます。 新しいケース形式を使用すると、500 万のドキュメントまたは 500 GB をエクスポートできます。エクスポート ジョブの方が小さい方です。

さらに、新しいケース形式には、ケース内の各レビュー セットの合計サイズを表示する更新されたユーザー インターフェイスが含まれています。 レビュー セットのサイズは、[レビュー セット] タブの **列に表示** されます。

![ユーザー インターフェイスの新しいレビュー セットAdvanced eDiscovery統計。](..\media\LargeCaseUI.png)

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**1 つのコレクションで 1 TB を超えるコレクションを収集しようとすると、動作しますか?**

パフォーマンスに悪影響が及び、一部のインスタンスで不安定になる可能性があります。

**クラウド添付ファイルが既定で大きな大文字と小文字の形式で含まれている場合。レビュー エクスペリエンスからそのコンテンツを削除する方法**  

レビュー セット フィルターを使用して、メッセージの種類でフィルター処理したり、HasAttachment フィルターを使用してクラウド添付ファイルを除外したりします。 詳細については、「レビュー セット [内のコンテンツのクエリとフィルター」を参照してください](review-set-search.md)。

**チャット会話トランスクリプトをエクスポートする場合、読み込みファイルには、展開されたメタデータとトランスクリプトごとに 1 つのアイテムが含まれますか?**

会話のすべてのメタデータが HTML トランスクリプト ファイルに埋め込まれます。  一般的なフィールドの多くは、読み込みファイルで使用できます。 エクスポートされたメタデータの詳細については[、「Document metadata fields in Advanced eDiscovery」 を参照してください](document-metadata-fields-in-Advanced-eDiscovery.md)。
