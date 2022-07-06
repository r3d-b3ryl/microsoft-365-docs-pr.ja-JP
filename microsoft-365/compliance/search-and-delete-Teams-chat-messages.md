---
title: Teams でチャット メッセージを検索および削除する
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 3526fd06-b45f-445b-aed4-5ebd37b3762a
description: 電子情報開示 (Premium) と Microsoft Graph エクスプローラーを使用して、Microsoft Teams でチャット メッセージを検索および消去し、Teams のデータ流出インシデントに対応します。
ms.openlocfilehash: 372293e11ee16498746da69c824a91abd108f2cf
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66629207"
---
# <a name="search-and-purge-chat-messages-in-teams-preview"></a>Teams でのチャット メッセージの検索と消去 (プレビュー)

電子情報開示 (Premium) と Microsoft Graph エクスプローラーを使用して、Microsoft Teams でチャット メッセージを検索および削除できます。 これは、機密情報や不適切なコンテンツを見つけて削除するのに役立ちます。 この検索と消去のワークフローは、機密情報や悪意のある情報を含むコンテンツが Teams チャット メッセージを通じてリリースされた場合に、データ流出インシデントに対応するのにも役立ちます。

> [!NOTE]
> この記事は、Microsoft 365 Enterprise組織に適用されます。 米国政府機関向けクラウド (GCC、GCC High、DoD を含む) のサポートは近日公開予定です。

## <a name="before-you-search-and-purge-chat-messages"></a>チャット メッセージを検索して消去する前に

- 電子情報開示 (Premium) ケースを作成し、コレクションを使用してチャット メッセージを検索するには、Microsoft Purview コンプライアンス ポータルの **電子情報開示マネージャー** ロール グループのメンバーである必要があります。 チャット メッセージを削除するには、 **検索ロールと消去** ロールが割り当てられている必要があります。 このロールは、既定でデータ調査担当者と組織管理の役割グループに割り当てられます。 詳細については、「[電子情報開示のアクセス許可を割り当てる](assign-ediscovery-permissions.md)」を参照してください。電子情報開示のアクセス許可を割り当てる」を参照してください。
- テナント内の会話では、検索と消去がサポートされています。 Teams Connect Chat (外部アクセスまたはフェデレーション) の会話のサポートは、インターフェイスで有効になっている場合がありますが、意図したとおりに動作しない場合があります。
- メールボックスごとに最大 10 個のアイテムを一度に削除できます。 チャット メッセージを検索および削除する機能はインシデント対応ツールであるため、この制限はチャット メッセージを迅速に削除するのに役立ちます。

## <a name="search-and-purge-workflow"></a>ワークフローの検索と消去

Teams チャット メッセージを検索して消去するプロセスを次に示します。

![Teams チャット メッセージを検索および消去するワークフロー。](../media/TeamsSearchAndPurgeWorkflow.png)

## <a name="step-1-create-a-case-in-ediscovery-premium"></a>手順 1: 電子情報開示でケースを作成する (Premium)

最初の手順は、検索と消去プロセスを管理するケースを電子情報開示 (Premium) で作成することです。 ケースの作成の詳細については、「 [新しいケース形式を使用する」を](advanced-ediscovery-new-case-format.md)参照してください。

## <a name="step-2-create-a-draft-collection"></a>手順 2: 下書きコレクションを作成する

ケースを作成した後、次の手順では、削除する Teams チャット メッセージを検索する下書きコレクションを作成します。 実行する消去プロセスは、手順 5 では、下書きコレクションに含まれるすべての項目を消去します。

電子情報開示 (Premium) では、 *コレクション* は、消去するチャット メッセージを含む Teams コンテンツの場所の電子情報開示検索です。 前の手順で作成した場合に、下書きコレクションを作成します。 詳細については、「 [下書きコレクションを作成する](create-draft-collection.md)」を参照してください。

### <a name="data-sources-for-chat-messages"></a>チャット メッセージのデータ ソース

次の表を使用して、消去する必要があるチャット メッセージの種類に応じて検索するデータ ソースを決定します。

| この種類のチャットの場合...|このデータ ソースを検索します。..|
|:---------|:---------|
|Teams 1:1 チャット     |チャット参加者のメールボックス。|
|Teams グループ チャット     |チャット参加者のメールボックス。|
|Teams チャネル (標準と共有) |親チームに関連付けられているメールボックス。|
|Teams プライベート チャネル |プライベート チャネル メンバーのメールボックス。|

> [!NOTE]
> 手順 4 では、削除するチャット メッセージの種類を含むメールボックスに割り当てられている保留ポリシーとアイテム保持ポリシーも特定して削除する必要があります。

### <a name="tips-for-searching-for-chat-messages"></a>チャット メッセージを検索するためのヒント

Teams チャット会話 (1 対 1 とグループ チャット、標準チャット、共有チャット、プライベート チャットを含む) の最も包括的なコレクションを確実にするために、 **タイプ** 条件を使用し、下書きコレクションの検索クエリを作成するときに **インスタント メッセージ** オプションを選択します。 また、検索の消去調査に関連する項目にコレクションの範囲を絞り込むために、日付範囲または複数のキーワードを含めることもお勧めします。

**[種類**] オプションと [日付] オプションを使用したサンプル クエリのスクリーンショットを次 **に示** します。

   ![Teams コンテンツを収集するためのクエリ。](..\media\TeamsConditionsQueryType.png)

詳細については、「 [コレクションの検索クエリを作成する」を](building-search-queries.md)参照してください。

## <a name="step-3-review-and-verify-chat-messages-to-purge"></a>手順 3: チャット メッセージを確認して消去する

前述のように、手順 5 の消去プロセスでは、コレクションから返されたアイテムが削除されます。 そのため、コレクションの下書き結果を確認して、コレクションが消去する項目のみを返すようにすることが重要です。 下書きコレクション内の項目のサンプルを確認するには、「下書きコレクションの作成」の「下書きコレクションが完了した後の次の手順」セクション [を](create-draft-collection.md#next-steps-after-a-draft-collection-is-complete)参照してください。

さらに、コレクション統計 (特に上位の場所の統計情報) を使用して、コレクションによって返される項目を含むデータ ソースの一覧を生成できます。 次の手順でこの一覧を使用して、検索結果を含むデータ ソースから保留ポリシーとアイテム保持ポリシーを削除します。 詳細については、「 [コレクションの統計情報とレポート](collection-statistics-reports.md)」を参照してください。

## <a name="step-4-remove-holds-and-retention-policies-from-data-sources"></a>手順 4: データ ソースから保留ポリシーと保持ポリシーを削除する

メールボックスからチャット メッセージを消去する前に、ターゲット メールボックスに割り当てられている保留ポリシーまたはアイテム保持ポリシーを削除する必要があります。 削除していない場合、削除しようとしているチャットは保持されます。

削除するチャット メッセージを含むメールボックスの一覧を使用し、それらのメールボックスに保留ポリシーまたはアイテム保持ポリシーが割り当てられているかどうかを判断し、保持ポリシーまたはアイテム保持ポリシーを削除します。 手順 7. でメールボックスに再割り当てできるように、削除する保留ポリシーまたはアイテム保持ポリシーを必ず特定してください。

保留ポリシーとアイテム保持ポリシーを特定して削除する方法については、「手順 3: メールボックスからすべての保留を削除する」を参照してください。保留状態にある [クラウドベースのメールボックスの回復可能なアイテム フォルダーのアイテムを削除](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-3-remove-all-holds-from-the-mailbox)します。

## <a name="step-5-purge-chat-messages-from-teams"></a>手順 5: Teams からチャット メッセージを消去する

これで、Teams からチャット メッセージを実際に消去する準備が整いました。 Microsoft Graph エクスプローラーを使用して、次の 3 つのタスクを実行します。

1. 手順 1 で作成した電子情報開示 (Premium) ケースの ID を取得します。 これは、手順 2 で作成したコレクションを含む場合です。

2. 手順 2 で作成したコレクションの ID を取得し、手順 3 で検索結果を確認します。 このコレクション内の検索クエリは、削除されるチャット メッセージを返します。

3. コレクションから返されたチャット メッセージを消去します。

Graph エクスプローラーの使用の詳細については、「 [Graph エクスプローラーを使用して Microsoft Graph API を試す」を参照してください](/graph/graph-explorer/graph-explorer-overview)。

> [!IMPORTANT]
> Microsoft Graph の /beta バージョンの API は変更される可能性があります。 実稼働アプリケーションでこれらの API を使用することは、サポートされていません。 API が v1.0 で使用できるかどうかを確認するには、バージョン セレクターを使用します。

> [!IMPORTANT]
> Graph Explorer でこれら 3 つのタスクを実行するには、電子情報開示.Read.All と eDiscovery.ReadWrite.All のアクセス許可に同意する必要があります。 詳細については、「 [Graph Explorer の操作](/graph/graph-explorer/graph-explorer-features#consent-to-permissions)」の「アクセス許可に同意する」セクションを参照してください。

### <a name="get-the-case-id"></a>ケース ID を取得する

1. <https://developer.microsoft.com/graph/graph-explorer> Microsoft Purview コンプライアンス ポータルで検索ロールと消去ロールが割り当てられているアカウントを使用して、Graph Explorer に移動 **して** サインインします。

2. 次の GET 要求を実行して、電子情報開示 (Premium) ケースの ID を取得します。 要求クエリのアドレス バーの値 `https://graph.microsoft.com/beta/compliance/ediscovery/cases` を使用します。 API バージョンのドロップダウン リストで **v1.0** を選択してください。

   ![ケース ID の GET 要求。](..\media\GraphGetRequestForCaseId.png)

   この要求は、[ **応答プレビュー** ] タブで組織内のすべてのケースに関する情報を返します。

3. 応答をスクロールして、電子情報開示 (Premium) ケースを見つけます。 **displayName** プロパティを使用してケースを識別します。

   ![ケース ID を含む応答。](..\media\GraphResponseForCaseId.png)

4. 対応する ID をコピーします (または、テキスト ファイルにコピーして貼り付けます)。 次のタスクでこの ID を使用して、コレクション ID を取得します。

> [!TIP]
> 前の手順を使用してケース ID を取得する代わりに、Microsoft Purview コンプライアンス ポータルでケースを開き、URL からケース ID をコピーできます。

### <a name="get-the-collection-id"></a>コレクション ID を取得する

1. Graph Explorer で、次の GET 要求を実行して、手順 2. で作成したコレクションの ID を取得し、消去する項目を含めます。 要求クエリのアドレス バーの値 `https://graph.microsoft.com/beta/compliance/ediscovery/cases('caseId')/sourceCollections` を使用します。CaseId は、前の手順で取得した ID です。 ケース ID は、必ずかっこと単一引用符で囲んでください。

   ![コレクション ID の GET 要求。](..\media\GraphGetRequestForCollectionId.png)

   この要求は、[ **応答プレビュー** ] タブのケース内のすべてのコレクションに関する情報を返します。

2. 応答をスクロールして、消去する項目を含むコレクションを見つけます。 **displayName** プロパティを使用して、手順 3. で作成したコレクションを識別します。

   ![コレクション ID を持つ応答。](..\media\GraphResponseForCollectionId.png)

   応答では、コレクションからの検索クエリが **contentQuery** プロパティに表示されます。 このクエリによって返されたアイテムは、次のタスクで削除されます。

3. 対応する ID をコピーします (または、テキスト ファイルにコピーして貼り付けます)。 次のタスクでこの ID を使用して、チャット メッセージを消去します。

### <a name="purge-the-chat-messages"></a>チャット メッセージを消去する

1. Graph Explorer で、次の POST 要求を実行して、手順 2. で作成したコレクションから返された項目を消去します。 要求クエリのアドレス バーの値 `https://graph.microsoft.com/beta/compliance/ediscovery/cases('caseId')/sourceCollections('collectionId')/purgeData` を使用します。caseId と collectionId は、前の手順で取得した ID です。 Id 値は必ずかっこと単一引用符で囲んでください。

      ![コレクションから返されたアイテムを削除する POST 要求。](..\media\GraphPOSTRequestToPurgeItems.png)

   POST 要求が成功すると、要求が受け入れられたことを示す HTTP 応答コードが緑色のバナーに表示されます。

   ![消去要求に対する応答。](..\media\GraphResponseForPurge.png)

  purgeData の詳細については、「 [sourceCollection: purgeData](/graph/api/ediscovery-sourcecollection-purgedata)」を参照してください。

## <a name="step-6-verify-chat-messages-are-purged"></a>手順 6: チャット メッセージが削除されたことを確認する

POST 要求を実行してチャット メッセージを消去すると、これらのメッセージは Teams クライアントから削除され、管理者がメッセージを削除したことを示す自動生成されたメッセージに置き換えられます。 このメッセージの例については、この記事の [「エンド ユーザー エクスペリエンス](#end-user-experience) 」セクションを参照してください。

削除されたチャット メッセージは、隠しメールボックス フォルダーである[Boardsholds] フォルダーに移動されます。 削除されたチャット メッセージは少なくとも 1 日間そこに保存され、次にタイマー ジョブが実行されるときに (通常は 1 ~ 7 日間) 完全に削除されます。 詳細については、「 [Microsoft Teams のリテンション期間の詳細」を参照してください](retention-policies-teams.md)。

## <a name="step-7-reapply-holds-and-retention-policies-to-data-sources"></a>手順 7: 保持ポリシーと保持ポリシーをデータ ソースに再適用する

チャット メッセージが削除され、Teams クライアントから削除されたことを確認したら、手順 4. で削除した保留ポリシーとアイテム保持ポリシーを再適用できます。

<!--
## Deleting chat messages in federated environments

Admins can use the procedures in this article to search and delete Teams chat messages in federated environments. However, you must adhere to the following guidelines. These guidelines are based on the organizational ownership of the conversation thread that contains the messages you want to delete. An organization is the owner of a conversation thread that is started by a user in that organization. In other words, when a user starts a chat, the user's organization becomes the owner of the conversation thread.

- Admins can delete the compliance copy in conversation threads owned by their organization. That means compliance copies are purged when the admin who purges the chat messages in Step 5 is in the same organization as the user who initiated the conversation thread that contains the purged messages. If a conversation thread has users in two organizations, compliance copies for the other organization will be retained.

- If a conversation thread has users in two organizations, purged chat messages are removed from the Teams client in both organizations.

- The only way to purge chat messages from user mailboxes in your organization for chat messages in conversation threads owned by another organization is to use retention policies for Teams. For more information, see [Learn about retention for Microsoft Teams](retention-policies-teams.md).
-->

## <a name="end-user-experience"></a>エンドユーザーのエクスペリエンス

削除されたチャット メッセージの場合、"このメッセージは管理者によって削除されました" というメッセージが自動的に生成されます。

![Teams クライアントで削除されたチャット メッセージのビュー。](..\media\TeamsPurgeTombstone.png)

前のスクリーンショットのメッセージは、削除されたチャット メッセージに置き換えられます。

> [!NOTE]
> エンド ユーザーであり、チャット メッセージが削除された場合は、詳細については管理者にお問い合わせください。
