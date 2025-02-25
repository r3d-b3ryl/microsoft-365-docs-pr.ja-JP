---
title: 電子情報開示の Teams ワークフロー (Premium)
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
ms.reviewer: jefwan
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: 電子情報開示 (Premium) で Microsoft Teams からコンテンツを保持、収集、確認、エクスポートする方法について説明します。
ms.openlocfilehash: ec3a1029c1a1b8de44a675d1856812aee0a77689
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66629103"
---
# <a name="ediscovery-premium-workflow-for-content-in-microsoft-teams"></a>Microsoft Teams のコンテンツの電子情報開示 (Premium) ワークフロー

この記事では、Microsoft Purview eDiscovery (Premium) を使用して Microsoft Teams からコンテンツを保持、収集、確認、エクスポートするための包括的な手順、ガイドライン、ベスト プラクティスを提供します。 この記事の目的は、Teams コンテンツの電子情報開示ワークフローを最適化することです。

電子情報開示 (Premium) を使用して収集および処理できる Teams コンテンツには、次の 6 つのカテゴリがあります。

- **Teams 1:1 チャット**。 2 人のユーザー間で Teams の会話で共有されるチャット メッセージ、投稿、添付ファイル。  Teams 1:1 チャットは *会話* とも呼ばれます。

- **Teams グループ チャット**。 3 人以上のユーザー間で Teams の会話で共有されるチャット メッセージ、投稿、添付ファイル。 *1:N* チャットまたは *グループ会話* とも呼ばれます。

- **Teams の反応**。 Teams 会話のチャット メッセージ、投稿、添付ファイルに適用されるリアクション。

- **Teams チャネル**。 標準の Teams チャネルで共有されているチャット メッセージ、投稿、返信、添付ファイル。

- **プライベート チャネル**。 プライベート Teams チャネルで共有されているメッセージの投稿、返信、添付ファイル。

- **共有チャネル**。 共有 Teams チャネルで共有されているメッセージの投稿、返信、添付ファイル。

## <a name="where-teams-content-is-stored"></a>Teams コンテンツが保存されている場所

電子情報開示 (Premium) で Teams コンテンツを管理する前提条件は、電子情報開示 (Premium) で収集、処理、レビューできる Teams コンテンツの種類と、そのコンテンツが Microsoft 365 に保存されている場所を理解することです。 次の表に、Teams コンテンツ タイプと各コンテンツ タイプの格納場所を示します。

|&nbsp;|チャット メッセージと投稿の場所|ファイルと添付ファイルの場所|
|---|---|---|
|Teams 1:1 チャット|1 対 1 のチャットのメッセージは、すべてのチャット参加者のExchange Onlineメールボックスに格納されます。|1:1 チャットで共有されたファイルは、ファイルを共有したユーザーのOneDrive for Business アカウントに保存されます。|
|Teams グループ チャット|グループ チャット内のメッセージは、すべてのチャット参加者のExchange Onlineメールボックスに格納されます。|グループ チャットで共有されたファイルは、ファイルを共有したユーザーのOneDrive for Business アカウントに格納されます。|
|Teams の反応|グループ チャット内のメッセージは、すべてのチャット参加者のExchange Onlineメールボックスに格納されます。|グループ チャットで共有されたファイルは、ファイルを共有したユーザーのOneDrive for Business アカウントに格納されます。|
|Teams チャネル|すべてのチャネル メッセージと投稿は、チームに関連付けられているExchange Online メールボックスに格納されます。|チャネルで共有されているファイルは、チームに関連付けられている SharePoint Online サイトに格納されます。|
|プライベート チャネル|プライベート チャネルで送信されたメッセージは、プライベート チャネルのすべてのメンバーのExchange Online メールボックスに格納されます。|プライベート チャネルで共有されるファイルは、プライベート チャネルに関連付けられた専用の SharePoint Online サイトに格納されます。|
|共有チャネル|共有チャネルで送信されたメッセージは、共有チャネルに関連付けられたシステム メールボックスに格納されます。<sup>1</sup>|共有チャネルで共有されているファイルは、共有チャネルに関連付けられた専用の SharePoint Online サイトに格納されます。|

> [!NOTE]
> <sup>1</sup> 共有チャネルで送信されたメッセージを検索 (および保持) するには、親チームのExchange Onlineメールボックスを検索または指定する必要があります。

## <a name="create-a-case-for-teams-content"></a>Teams コンテンツのケースを作成する

電子情報開示 (Premium) で Teams コンテンツを管理する最初の手順は、Teams コンテンツの管理に最適化された新しいケース形式を使用してケースを作成することです。 Teams コンテンツに新しいケース形式を使用する利点を次に示します。

- スレッドスレッドのサポート。応答アイテムを含む同じ会話内の追加メッセージが自動的に収集され、レビュー セットに追加されます。

- Teams チャットの会話は、HTML トランスクリプト ファイルとしてセットを確認するために自動的に追加されます。 会話で共有されるクラウドの添付ファイルも、レビュー セットに追加されます。 これにより、応答性の高いアイテムを使用して会話にコンテキストを提供し、チャット ベースのコンテンツによって生成されるアイテムの合計数を減らすことができます。

- 最大 1 TB のコレクションをレビュー セットに追加できます。これにより、ケース内で大量の Teams コンテンツを収集して大量に収集できます。

ケース制限の引き上げの詳細については、「 [電子情報開示 (Premium) で新しいケース形式を使用](advanced-ediscovery-new-case-format.md)する」を参照してください。

ケースを作成するには:

1. <https://compliance.microsoft.com> に移動し、サインインします。

2. Microsoft Purview コンプライアンス ポータルの左側のナビゲーション ウィンドウで、[**電子情報開示>詳細設定**] をクリックします。

3. **[電子情報開示 (Premium)]** ページで、[**ケース**] タブをクリックし、[**ケースの作成**] をクリックします。

   **[新しい電子情報開示ケース**] ポップアップ ページが表示されます。 [ **ケース形式]** セクションには、新しいケース形式を使用してケースを作成するオプションが用意されています。

   ![[新しい電子情報開示ケース] ページの [大きいケース] オプション。](..\media\AeDNewCaseFormat1.png)

4. ケースに名前を付けた後、[ **新規** ] オプションを選択し、[ **保存]** をクリックしてケースを作成します。

## <a name="add-teams-custodial-data-sources-and-preserve-teams-content"></a>Teams の管理データ ソースを追加し、Teams コンテンツを保持する  

次の手順では、調査のデータカストディアンであるユーザーを特定し、そのユーザーとそのコンテンツの場所を、前のセクションで作成したケースに保管担当者として追加します。 カストディアンを追加する場合は、そのメールボックスと OneDrive アカウントを保管データ ソースとして指定できます。 また、Teams コンテンツの場所をカストディアン データ ソースとして指定して、調査中にコンテンツを保持するためにこれらの場所をすばやく訴訟ホールドに置くこともできます。 また、コンテンツを簡単に収集し、レビュー セットに追加することもできます。

ケースにカストディアンを追加し、保管データ ソースを保持するには:

1. 前のセクションで作成した電子情報開示 (Premium) ケースに移動し、[ **データ ソース**] をクリックします。

2. [**データ ソース**] ページで、[**データ ソース** > の追加] をクリックして **新しいカストディアンを追加します**。

3. **新しいカストディアン** ウィザードで、ユーザーの名前またはエイリアスの最初の部分を入力して、1 人以上のユーザーをカストディアンとしてケースに追加します。 正しいユーザーを見つけたら、そのユーザーの名前を選択してリストに追加します。  

4. 各カストディアンを展開して、自動的にカストディアンに関連付けられているプライマリ データ ソースを表示し、カストディアンに関連付ける他の場所を選択します。

   ![カストディアン データ ソース。](..\media\TeamsCustodialDataLocations1.png)

5. Teams コンテンツの管理データ ソースを追加するには、次のガイドラインに従います。 [ **編集] を** クリックしてデータの場所を追加します。

   - **メールボックス**。 カストディアンのメールボックスは既定で選択されています。 1 対 1 のチャット、グループ チャット、プライベート チャネル チャットを保管データとして追加 (および保持) するには、これを選択したままにします。

   - **OneDrives**。 カストディアンの OneDrive アカウントは既定で選択されています。 1 対 1 のチャットとグループ チャットで共有されているファイルを保管データとして追加 (および保持) するには、この項目を選択したままにします。

   - **SharePoint**。 カストディアンがメンバーであるプライベートチャネルまたは共有チャネルに関連付けられた SharePoint サイトを追加し、チャネルで共有されているファイルを保管データとして追加 (および保持) します。 [ **編集]** をクリックし、プライベート チャネルまたは共有チャネルに関連付けられている SharePoint サイトの URL を追加します。 ユーザーがメンバーであるプライベート チャネルと共有チャネルを見つける方法については、「 [プライベート チャネルと共有チャネルの電子情報開示](/microsoftteams/ediscovery-investigation#ediscovery-of-private-and-shared-channels)」を参照してください。

   - **Teams**。 カストディアンがメンバーであるチームを追加して、すべてのチャネル メッセージと Teams チャネルに共有されているすべてのファイルを保管データとして追加 (および保持) します。 これには、カストディアンがメンバーである共有チャネルの親チームのメールボックスを追加することが含まれます。 **[編集]** をクリックすると、カストディアンがメンバーである各チームに関連付けられているメールボックスとサイトが一覧に表示されます。 カストディアンに関連付けるチームを選択します。 各チームに対応するメールボックスとサイトの両方を選択する必要があります。

   > [!NOTE]
   > カストディアンがカストディアン データの場所としてメンバーでない Teams のメールボックスとサイトを追加することもできます。 これを行うには、**Exchange** と **SharePoint** の横にある **[編集]** をクリックし、チームに関連付けられているメールボックスとサイトを追加します。

6. カストディアンを追加して保管データ ソースを構成したら、[ **次へ** ] をクリックして **[保留設定]** ページを表示します。

   カストディアンの一覧が表示され、既定で **[保留** ] 列のチェック ボックスがオンになっています。 これは、各カストディアンに関連付けたデータ ソースに保留が配置されることを示しました。 このデータを保持するには、これらのチェック ボックスをオンのままにします。

7. [ **保留設定]** ページで、[ **次へ** ] をクリックしてカストディアンの設定を確認します。 [ **送信] を** クリックして、カストディアンをケースに追加します。

電子情報開示 (Premium) ケースでのデータ ソースの追加と保持の詳細については、次を参照してください。

- [電子情報開示 (Premium) ケースにカストディアンを追加する](add-custodians-to-case.md)

- [非保管データ ソースを電子情報開示 (Premium) ケースに追加する](non-custodial-data-sources.md)

## <a name="collect-teams-content-and-add-to-review-set"></a>Teams のコンテンツを収集し、レビュー セットに追加する

ケースにカストディアンを追加し、カストディアン データ ソース内のコンテンツを保持した後、ワークフローの次の手順では、調査に関連する Teams コンテンツを検索し、それをレビュー セットに追加して、さらにレビューと分析を行います。 Teams コンテンツを、Exchange の電子メールや SharePoint のドキュメントなど、他の Microsoft 365 サービスのコンテンツと共に収集するのが一般的ですが、このセクションでは、コレクション内の Teams コンテンツの収集に特に焦点を当てます。 Teams 以外のコンテンツを収集してレビュー セットに追加する追加のコレクションを作成できます。

ケースの Teams コンテンツを収集する場合、ワークフローには次の 2 つの手順があります。

1. **下書きコレクションを作成します**。  最初の手順では、検索条件に一致するアイテムの見積もりである *下書きコレクション* を作成します。 検索クエリに一致した結果に関する情報 (見つかったアイテムの合計数とサイズ、検出された異なるデータ ソース、検索クエリに関する統計情報など) を表示できます。 コレクションから返された項目のサンプルをプレビューすることもできます。 これらの統計情報を使用して、検索クエリを変更し、ケースに関連するコンテンツを収集することが完了するまで結果を絞り込むために必要な回数だけ下書きコレクションを再実行できます。

2. **下書きコレクションをレビュー セットにコミットします**。 下書きコレクションの結果に問題がなければ、コレクションをレビュー セットにコミットできます。 下書きコレクションをコミットすると、コレクションによって返された項目がレビュー セットに追加され、レビュー、分析、およびエクスポートが行われます。

また、コレクションを作成して実行するときに、下書きコレクションを実行せず、コレクションの結果をレビュー セットに直接追加することもできます。

Teams コンテンツのコレクションを作成するには:

1. 前のセクションでカストディアンを追加した電子情報開示 (Premium) ケースに移動し、[ **コレクション**] をクリックします。

2. [**コレクション**] ページで、[**新しいコレクション****標準コレクション** > ] を選択します。

3. コレクションの名前 (必須) と説明 (省略可能) を入力します。

4. [ **保管データ ソース** ] ページで、[ **保管担当者の選択** ] をクリックして、ケースに追加したカストディアンを選択します。

   ケースカストディアンの一覧は、[カストディアンの **選択** ] ポップアップ ページに表示されます。

5. 1 つ以上のカストディアンを選択し、[ **追加**] をクリックします。

   コレクションに特定のカストディアンを追加すると、各カストディアンの特定のデータ ソースの一覧が表示されます。 これらは、ケースにカストディアンを追加したときに構成したデータ ソースです。 すべてのカストディアン データ ソースが既定で選択されます。 これには、カストディアンに関連付けたすべての Teams またはチャネルが含まれます。

   Teams コンテンツを収集する場合は、次のことを行うことをお勧めします。

   - カストディアンの OneDrive アカウントをコレクション スコープから削除します ( **各カストディアンの [カストディアン] の [OneDrive** ] 列のチェック ボックスをオフにします)。 これにより、1 対 1 のチャットとグループ チャットに添付された重複するファイルのコレクションが防止されます。 クラウドの添付ファイルは、下書きコレクションをレビュー セットにコミットすると、コレクション内の各会話から自動的に収集されます。 このメソッドを使用すると (コレクションの一部として OneDrive アカウントを検索する代わりに) 1:1 に添付されたファイルとグループ チャットは、共有された会話にグループ化されます。

   - [ **追加サイト** ] 列のチェック ボックスをオフにして、プライベート チャネルまたは共有チャネルで共有されているファイルを含む SharePoint サイトを削除します。 これにより、下書きコレクションをコミットし、共有された会話にグループ化すると、これらのクラウドの添付ファイルがレビュー セットに自動的に追加されるため、プライベートまたは共有チャネルの会話に添付された重複するファイルを収集する必要がなくなります。

6. 以前に手順に従って Teams コンテンツをカストディアン データ ソースとして追加した場合は、この手順をスキップして **[次へ**] を選択できます。 それ以外の場合は、[ **非保管データ ソース** ] ウィザード ページで、コレクション内で検索するためにケースに追加した可能性がある Teams コンテンツを含む非親権データ ソースを選択できます。

7. 以前に手順に従って Teams コンテンツをカストディアン データ ソースとして追加した場合は、この手順をスキップして **[次へ**] を選択できます。 それ以外の場合は、[ **その他の場所** ] ウィザード ページで、コレクション内で検索する他のデータ ソースを追加できます。 たとえば、保管データ ソースまたは非保管データ ソースとして追加されなかったチームのメールボックスとサイトを追加できます。 それ以外の場合は、[ **次へ** ] を選択し、この手順をスキップします。

8. **[条件**] ウィザード ページで、前のウィザード ページで指定したデータ ソースから Teams コンテンツを収集するように検索クエリを構成します。 さまざまなキーワードと検索条件を使用して、コレクションの範囲を絞り込むことができます。 詳細については、「 [コレクションの検索クエリを作成する」を](building-search-queries.md)参照してください。

   Teams チャットの会話の最も包括的なコレクション (1:1、グループ、チャネル チャットを含む) で **[種類]** 条件を使用し、[ **インスタント メッセージ** ] オプションを選択します。 また、調査に関連する項目にコレクションの範囲を絞り込むために、日付範囲または複数のキーワードを含めることもお勧めします。 **[種類**] オプションと [日付] オプションを使用したサンプル クエリのスクリーンショットを次 **に示** します。

   ![Teams コンテンツを収集するためのクエリ。](..\media\TeamsConditionsQueryType.png)

9. **[下書きまたは収集の保存**] ウィザード ページで、下書きコレクションを作成するか、コレクションをレビュー セットにコミットするかに応じて、次のいずれかの操作を行います。

   ![下書きコレクションまたはコミット コレクションを保存します。](..\media\TeamsDraftCommitCollection.png)

   1. **コレクションを下書きとして保存します**。 下書きコレクションを作成するには、このオプションを選択します。 前述のように、下書きコレクションではコレクションの結果がレビュー セットに追加されません。 コレクション スコープ内のデータ ソースの検索クエリと一致する検索結果の見積もりを返します。 これにより、[コレクションの統計とレポート][(collection-statistics-reports.md)] を表示し、下書きコレクションを編集および再実行できます。 下書きコレクションの結果に問題がなければ、それをレビュー セットにコミットできます。 詳細については、「 [下書きコレクションを作成する](create-draft-collection.md)」を参照してください。

   2. **アイテムを収集し、レビュー セットに追加します**。 コレクションを実行し、結果をレビュー セットに追加するには、このオプションを選択します。 コレクションは、新しいレビュー セットまたは既存のレビュー セットに追加できます。 コンテキスト Teams の会話メッセージ (会話スレッドとも呼ばれます) を収集し、クラウドの添付ファイル *を収集する* オプションは既定で選択され、選択を解除することはできません。 これらのオプションは、Teams コンテンツのケースを最初に作成したときに使用した新しいケース形式のために自動的に適用されます。 コレクションをレビュー セットにコミットする方法の詳細については、「レビュー セットに [下書きコレクションをコミットする」を](commit-draft-collection.md)参照してください。

10. コレクションの構成が完了したら、コレクションを送信して下書きコレクションを作成するか、アイテムを収集してレビュー セットに追加します。

   コレクションをレビュー セットに追加するプロセスが完了すると、[ **コレクション** ] タブのコレクションの状態値が **[コミット済み**] に設定されます。

## <a name="review-teams-content-in-a-review-set"></a>レビュー セット内の Teams コンテンツを確認する

Teams コンテンツのコレクションをレビュー セットに追加した後、次の手順では、調査に関連するコンテンツを確認し、必要に応じてカリングします。 Teams コンテンツを確認するための重要な前提条件は、電子情報開示 (Premium) がレビュー セットに追加するときに Teams チャットの会話と添付ファイルを処理する方法を理解することです。 この Teams コンテンツの処理により、次の 3 つのことが行われます。

- **[グループ化](#grouping)**。 メッセージ、投稿、返信の Teams の会話がグループ化され、レビュー セットに表示される方法。 これには、チャット会話の添付ファイルも抽出され、会話内でグループ化されます。

- **[トランスクリプト会話のスレッド処理](#transcript-conversation-threading)**。 電子情報開示 (Premium) によって、コレクションの条件に一致するアイテムに関するコンテキストを提供するために、収集する会話の追加コンテンツを決定する方法。

- **[重複除去](#deduplication-of-teams-content)**。 電子情報開示 (Premium) が重複する Teams コンテンツを処理する方法。

- **[メタデータ](#metadata-for-teams-content)**。 電子情報開示 (Premium) が収集され、レビュー セットに追加された後に Teams コンテンツに追加されるメタデータ プロパティ。

グループ化、会話スレッド処理、重複除去、Teams メタデータを理解すると、Teams コンテンツのレビューと分析を最適化するのに役立ちます。 このセクションでは、 [レビュー セットで Teams コンテンツを表示するためのヒントも紹介します](#tips-for-viewing-teams-content-in-a-review-set)。

### <a name="grouping"></a>グループ化

Teams チャット会話のコンテンツがレビュー セットに追加されると、メッセージ、投稿、会話からの返信が HTML トランスクリプト ファイルに集計されます。 1 つのチャット会話に複数のトランスクリプト ファイルを含めることができます。 これらのトランスクリプト ファイルの重要な機能は、個々の (または個別の) メッセージではなく、Teams コンテンツを継続的な会話として表示することです。 これにより、前の手順でコレクションの検索条件に一致した項目のコンテキストが提供され、レビュー セットに収集されるアイテムの数が減ります。 トランスクリプトと関連アイテムは、 *家族* または *会話* のいずれかでグループ化できます。 同じファミリ内のアイテムは、 **FamilyId** メタデータ プロパティに対して同じ値を持ちます。 同じ会話内のアイテムは、 **ConversationId** メタデータ プロパティに対して同じ値を持つことになります。

次の表では、さまざまな種類の Teams チャット コンテンツを家族と会話でグループ化する方法について説明します。

|Teams コンテンツ タイプ|ファミリ別にグループ化する|会話別のグループ化|
|---|---|---|
|Teams 1:1 とグループ チャット|トランスクリプトとそのすべての添付ファイルと抽出されたアイテムは、同じ **FamilyId** を共有します。 各トランスクリプトには一意の **FamilyId があります**。|同じ会話内のすべてのトランスクリプト ファイルとそのファミリ アイテムは、同じ **ConversationId** を共有します。 これには、次の項目が含まれます。 <ul><li>抽出されたすべてのアイテムと、同じ **ConversationId** を共有するすべてのトランスクリプトの添付ファイル。</li><li>同じチャット会話のすべてのトランスクリプト</li><li>各トランスクリプトのすべてのカストディアン コピー</li><li>同じチャット会話からの後続のコレクションからのトランスクリプト</li></ul> <br/> Teams 1:1 とグループ チャットの会話の場合は、会話内の異なる時間枠に対応するトランスクリプト ファイルが複数ある場合があります。 これらのトランスクリプト ファイルは、同じ参加者と同じ会話から取得されるため、同じ **ConversationId** を共有します。|
|Standard、Private、Shared チャネル チャット|各投稿とすべての返信と添付ファイルは、独自のトランスクリプトに保存されます。 このトランスクリプトとそのすべての添付ファイルと抽出されたアイテムは、同じ **FamilyId** を共有します。|各投稿とその添付ファイルと抽出されたアイテムには、一意の **ConversationId があります**。 同じ投稿からの後続のコレクションまたは新しい返信がある場合、それらのコレクションから生じる差分トランスクリプトも同じ **ConversationId** を持つことになります。|

レビュー セットのコマンド バーにある **グループ** コントロールを使用して、家族または会話でグループ化された Teams コンテンツを表示します。

![コマンド バーのグループ コントロール。](..\media\TeamsGroupControl.png)

- [ **グループ ファミリの添付ファイル** ] を選択して、ファミリ別にグループ化された Teams コンテンツを表示します。 各トランスクリプト ファイルは、レビュー セット アイテムの一覧の行に表示されます。 添付ファイルはアイテムの下に入れ子になります。

- **[グループ Teams] または [Yammer の会話**] を選択して、会話別にグループ化された Teams コンテンツを表示します。 各会話は、レビュー セット アイテムの一覧の行に表示されます。 トランスクリプト ファイルと添付ファイルは、最上位レベルの会話の下に入れ子になります。

> [!NOTE]
> クラウドの添付ファイルは、表示される会話とグループ化されます。 このグループ化は、ファイルが添付されたメッセージのトランスクリプト ファイルと同じ **FamilyId** と、メッセージが表示された会話と同じ **ConversationId** を割り当てることによって実現されます。 つまり、クラウド添付ファイルが異なる会話に添付されている場合、レビュー セットに複数のコピーが追加される可能性があります。

#### <a name="viewing-transcript-files-for-conversations"></a>会話のトランスクリプト ファイルを表示する

レビュー セット内のトランスクリプト ファイルを表示すると、メッセージの一部が紫色で強調表示されます。 強調表示されているメッセージは、表示しているトランスクリプトの保管担当者のコピーによって異なります。 たとえば、User4 と User2 の間の 1 対 1 のチャットでは、User4 のメールボックスから収集されたトランスクリプトを表示すると、User4 によって投稿されたメッセージが紫色で強調表示されます。 同じ会話の User2 のトランスクリプトを表示すると、User2 によって投稿されたメッセージが紫色で強調表示されます。 この強調表示動作は、ユーザーの投稿が Teams クライアントで紫色で強調表示されているのと同じ Teams クライアント エクスペリエンスに基づいています。

次のスクリーンショットは、Teams クライアントでの会話の例と、レビュー セット内の同じ会話のトランスクリプト ファイルを示しています。 トランスクリプト ファイルの紫色の強調表示は、トランスクリプトが User2 のメールボックスから収集されたことを示します。

##### <a name="conversation-in-teams-client"></a>Teams クライアントでの会話

![レビュー セットのトランスクリプト ファイルに表示される会話。](..\media\TeamsClient1.png)

##### <a name="conversation-in-transcript-file"></a>トランスクリプト ファイル内の会話

![Teams クライアントで同じ会話が表示されます。](..\media\TeamsTranscript1.png)

### <a name="transcript-conversation-threading"></a>トランスクリプト会話のスレッド処理

電子情報開示 (Premium) の新しいケース形式の会話スレッド機能は、調査に関連する可能性のある項目に関連するコンテキスト コンテンツを識別するのに役立ちます。 この機能は、コレクション中に検索クエリに一致するアイテムの前と後に続くチャット メッセージを含む個別の会話ビューを生成します。 この機能を使用すると、Microsoft Teams で完全なチャット会話 ( *スレッド会話* と呼ばれる) を効率的かつ迅速に確認できます。 前に説明したように、電子情報開示 (Premium) が Teams コンテンツをレビュー セットに追加すると、チャット会話は HTML トランスクリプト ファイルに再構築されます。

電子情報開示 (Premium) が、Teams コンテンツの収集時に使用したコレクション クエリ ( *応答* アイテムと呼ばれる) と一致するアイテムに関するコンテキストを提供する追加のメッセージと応答トランスクリプト ファイルを含めるために使用されるロジックを次に示します。 スレッド処理のさまざまな動作は、チャットの種類と、応答性の高いアイテムの収集に使用される検索クエリに基づきます。 2 つの一般的なコレクション シナリオがあります。

- キーワードやプロパティ:値のペアなど、検索パラメーターを使用するクエリ

- 日付範囲のみを使用するクエリ

|Teams コンテンツ タイプ|検索パラメーターを持つクエリ|日付範囲を含むクエリ|
|---|---|---|
|Teams 1:1 とグループ チャット|応答アイテムの 12 時間前と 12 時間後に投稿されたメッセージは、1 つのトランスクリプト ファイル内のレスポンシブ アイテムとグループ化されます。|24 時間ウィンドウ内のメッセージは、1 つのトランスクリプト ファイルにグループ化されます。|
|標準、プライベート、共有の Teams チャネル チャット|応答アイテムと対応するすべての返信を含む各投稿は、1 つのトランスクリプト ファイルにグループ化されます。|応答アイテムと対応するすべての返信を含む各投稿は、1 つのトランスクリプト ファイルにグループ化されます。|

### <a name="deduplication-of-teams-content"></a>Teams コンテンツの重複除去

次の一覧では、Teams コンテンツをレビュー セットに収集するときの重複除去 (および重複) 動作について説明します。

- レビュー セットに追加される各トランスクリプト ファイルは、データの場所に格納されているコンテンツに対する 1 対 1 のマッピングである必要があります。 つまり、電子情報開示 (Premium) では、レビュー セットに既に追加されている Teams コンテンツは収集されません。 チャット メッセージがレビュー セットに既に収集されている場合、電子情報開示 (Premium) は、同じデータの場所から後続のコレクションのレビュー セットに同じメッセージを追加しません。

- 1 対 1 とグループ チャットの場合、メッセージのコピーは各会話参加者のメールボックスに格納されます。 異なる参加者のメールボックスに存在する同じ会話のコピーは、異なるメタデータで収集されます。 その結果、会話の各インスタンスは一意として扱われ、個別のトランスクリプト ファイルでレビュー セットに取り込まれます。 そのため、1 対 1 またはグループ チャットのすべての参加者がケースでカストディアンとして追加され、コレクションのスコープに含まれている場合、各トランスクリプトのコピー (同じ保存用) がレビュー セットに追加され、同じ **ConversationId** でグループ化されます。 これらの各コピーは、対応するカストディアンに関連付けられます。 **ヒント**: レビュー セットリストの **カストディアン** 列は、対応するトランスクリプト ファイルのカストディアンを識別します。

- 同じ会話のアイテムの後続のコレクションでは、以前に収集されなかったデルタ コンテンツのみがレビュー セットに追加され、同じ会話から以前に収集されたトランスクリプトと (同じ **ConversationId を** 共有して) グループ化されます。 この動作の例を次に示します。

   1. コレクション A は、User1 と User2 の間の会話でメッセージを収集し、レビュー セットに追加します。

   2. コレクション B は同じ会話からメッセージを収集しますが、コレクション A が実行されたため、User1 と User2 の間に新しいメッセージがあります。

   3. コレクション B の新しいメッセージのみがレビュー セットに追加されます。 これらのメッセージは別のトランスクリプト ファイルに追加されますが、新しいトランスクリプトはコレクション A のトランスクリプトと同じ **ConversationId** でグループ化されます。

   この動作は、すべての種類の Teams チャットに適用されます。

### <a name="metadata-for-teams-content"></a>Teams コンテンツのメタデータ

数千または数百万のアイテムを含む大規模なレビュー セットでは、レビューの範囲を Teams コンテンツに絞り込むのは困難な場合があります。 Teams コンテンツにレビューを集中させるために、Teams コンテンツに固有のメタデータ プロパティがあります。 これらのプロパティを使用して、レビュー リスト内の列を整理し、 [フィルターとクエリを構成](review-set-search.md) して Teams コンテンツのレビューを最適化できます。 これらのメタデータ プロパティは、エクスポート後またはサードパーティの電子情報開示ツールでコンテンツを整理して表示するために、電子情報開示 (Premium) から Teams コンテンツをエクスポートするときにも含まれます。

次の表では、Teams コンテンツのメタデータ プロパティについて説明します。

|Metadata プロパティ|説明|
|---|---|
|ContainsEditedMessage|トランスクリプト ファイルに編集されたメッセージが含まれているかどうかを示します。 編集されたメッセージは、トランスクリプト ファイルを表示するときに識別されます。|
|ConversationId|アイテムが関連付けられている会話を識別する GUID。 同じ会話のトランスクリプト ファイルと添付ファイルには、このプロパティの値が同じになります。|
|会話名|トランスクリプト ファイルまたは添付ファイルが関連付けられている会話の名前。 Teams 1:1 とグループ チャットの場合、このプロパティの値は、会話のすべての参加者の UPN が連結されます。 たとえば、「 `User3 <User3@contoso.onmicrosoft.com>,User4 <User4@contoso.onmicrosoft.com>,User2 <User2@contoso.onmicrosoft.com>` 」のように入力します。 Teams チャネル (標準、プライベート、共有) チャットでは、会話名に次の形式が使用されます `<Team name>,<Channel name>`。 たとえば、「 `eDiscovery vNext, General` 」のように入力します。|
|ConversationType|チーム チャットの種類を示します。 Teams 1:1 とグループ チャットの場合、このプロパティの値は `Group`. 標準、プライベート、および共有チャネル チャットの場合、値は `Channel`.|
|日付|トランスクリプト ファイル内の最初のメッセージのタイムスタンプ。|
|FamilyId|チャット会話のトランスクリプト ファイルを識別する GUID。 添付ファイルは、ファイルが添付されたメッセージを含むトランスクリプト ファイルと同じ値を持ちます。|
|FileClass|その種類のコンテンツを示します。 Teams チャットのアイテムには値 `Conversation`があります。 これに対し、Exchange 電子メール メッセージには値 `Email`があります。|
|MessageKind|メッセージの種類プロパティ。 Teams コンテンツには価値があります `microsoftteams , im`。|
|受信者|トランスクリプト会話内でメッセージを受信したすべてのユーザーの一覧。|
|TeamsChannelName|トランスクリプトの Teams チャネル名。|

その他の電子情報開示 (Premium) メタデータ プロパティの説明については、「 [電子情報開示 (Premium) のドキュメント メタデータ フィールド](document-metadata-fields-in-Advanced-eDiscovery.md)」を参照してください。

## <a name="export-teams-content"></a>Teams コンテンツをエクスポートする

レビュー セット内の Teams コンテンツを確認およびカリングしたら、調査に対応するコンテンツを含むトランスクリプト ファイルをエクスポートできます。 Teams コンテンツの特定のエクスポート設定はありません。 各トランスクリプト ファイルは HTML メッセージ ファイルとしてエクスポートされます。 このファイルには、個々のチャット メッセージのすべてのメタデータを含む非表示の CDATA タグも含まれています。 前のセクションで説明したメタデータ プロパティは、Teams コンテンツがエクスポートされるときに含まれます。  

各トランスクリプト ファイルは読み込みファイルで参照され、読み込みファイルのExport_native_path フィールドの相対パスを使用して配置できます。 トランスクリプト ファイルは、ルート エクスポート フォルダーの Conversations フォルダーにあります。

## <a name="tips-for-viewing-teams-content-in-a-review-set"></a>レビュー セットで Teams コンテンツを表示するためのヒント

Teams コンテンツをレビュー セットで表示するためのヒントとベスト プラクティスを次に示します。

- コマンド バーの **[列のカスタマイズ** ] コントロールを使用して、Teams コンテンツのレビューを最適化するために列を追加および整理します。

  ![列の追加、削除、整理を行う場合は、[列の編集] ポップアップ ページを使用します。](..\media\EditReviewSetColumns.png)

   Teams コンテンツに役立つ列を追加および削除できます。 列の順序は、[列の **編集]** ポップアップ ページでドラッグ アンド ドロップすることもできます。 列を並べ替えて、並べ替えた列に対して同様の値を持つ Teams コンテンツをグループ化することもできます。

- Teams コンテンツを確認するのに役立つ便利な列には、 **カストディアン**、 **受信者**、 **ファイルの種類** 、 **メッセージの種類などがあります**。

- Teams 関連のプロパティの [フィルター](review-set-search.md) を使用して、Teams コンテンツをすばやく表示します。 前のセクションで説明したほとんどのメタデータ プロパティにはフィルターがあります。

## <a name="deleting-teams-chat-messages"></a>Teams チャット メッセージを削除する

電子情報開示 (Premium) と Microsoft Graph エクスプローラーを使用して、機密情報または悪意のある情報を含むコンテンツが Teams チャット メッセージを通じてリリースされた場合に、データ流出インシデントに対応できます。 組織内の管理者は、Microsoft Teams でチャット メッセージを検索および削除できます。 これは、Teams チャット メッセージの機密情報や不適切なコンテンツを削除するのに役立ちます。 詳細については、「 [Teams でのチャット メッセージの検索と消去](search-and-delete-Teams-chat-messages.md)」を参照してください。

## <a name="reference-guide"></a>リファレンス ガイド

Microsoft Teams で電子情報開示 (Premium) を使用するためのクイック リファレンス ガイドを次に示します。 このガイドでは、電子情報開示 (Premium) を使用して Microsoft Teams からコンテンツを保持、収集、確認、エクスポートするためのキー ポイントをまとめたものです。

![Microsoft Teams で電子情報開示 (Premium) を使用するためのリファレンス ガイドのサムネイル。](../media/AeDTeamsReferenceGuide-thumbnail.png)

[PDF ファイルとしてダウンロードする](https://download.microsoft.com/download/9/e/4/9e4eec6f-c476-452f-b414-4bd4b5c39dca/AeDTeamsReferenceGuide.pdf)
