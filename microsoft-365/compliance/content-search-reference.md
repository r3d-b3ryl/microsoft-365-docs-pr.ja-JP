---
title: コンテンツ検索の機能のリファレンス
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MED150
- MET150
ms.custom:
- seo-marvel-apr2020
- admindeeplinkMAC
description: この記事には、Microsoft 365 コンプライアンス センターのコンテンツ検索電子情報開示ツールに関する参照情報が含まれており、コンテンツ検索に関する多くの詳細情報を知ることができます。
ms.openlocfilehash: 3f2918c378d94fd65d4a89afed50957a2da40a7d
ms.sourcegitcommit: 46456ca009c9d50622e57e24269be74986184654
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2022
ms.locfileid: "63716378"
---
# <a name="feature-reference-for-content-search"></a>コンテンツ検索の機能のリファレンス

この記事では、コンテンツ検索の機能について説明します。

## <a name="content-search-limits"></a>コンテンツ検索の制限

コンテンツ検索に適用される制限については、「[コンテンツ検索の制限](limits-for-content-search.md)」を参照してください。

## <a name="building-a-search-query"></a>検索クエリの作成

検索クエリの作成、ブール検索演算子と検索条件の使用、組織外のユーザーと共有する機密情報の種類とコンテンツの検索の詳細については、「[コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。

キーワード リストを使用して検索クエリを作成する場合は、次の点に注意してください。

- 各行のキーワード (またはキーワード フレーズ) が **OR** 演算子でつながれる検索クエリを作成するには、[**キーワード リストの表示**] チェックボックスをオンにしてから、キーワードをそれぞれ別の行に入力する必要があります。キーワード ボックスにキーワードのリストを貼り付けたり、キーワードの入力後に **Enter** キーを押したりする場合、キーワードは **OR** 演算子でつながれません。キーワードのリストを追加する場合の正しくない例と正しい例を以下に示します。

    **正しくない例**

    ![キーワード リストの正しくない書式設定方法 (キーワード ボックスにリストを貼り付ける)](../media/fb54e3df-232a-439a-b3d7-27a60ec76a4c.png)

    **正しい例**

    ![キーワード リストの正しい書式設定方法 (チェックボックスをオンにしてからリストを貼り付ける)](../media/5d511a7b-c1f9-499c-bffe-e075bfc9adec.png)

- Excel ファイルまたはテキスト形式ファイルでキーワードまたはキーワード フレーズのリストを準備してから、キーワード リストに自分のリストをコピーして貼り付けることもできます。これを行うには、[**キーワード リストの表示**] チェックボックスをオンにする必要があります。次に、キーワード リストの最初の行をクリックして、リストを貼り付けます。Excel またはテキスト ファイルの行はそれぞれ、キーワード リストで異なる行に貼り付けられます。

- キーワード リストを使用してクエリを作成したら、検索クエリが意図したものであることを確認することをお勧めします。詳細ウィンドウの **[クエリ]** の下に表示される検索クエリでは、キーワードは **(c:s)** というテキストで区切られます。これは、キーワードが **OR** 演算子と機能的に同様の論理演算子で接続されていることを示します。同様に、検索クエリに条件が含まれている場合、キーワードと条件は **(c:c)** というテキストで区切られます。これは、キーワードが **AND** 演算子と機能的に同様の論理演算子で条件に接続されていることを示します。キーワード リストと条件を使用した場合の結果として (詳細ウィンドウに) 表示される検索クエリの例を以下に示します。

    ![キーワード リストと条件を使用するときに作成されるクエリの例。](../media/b463750c-57fa-4602-9fed-0d5a420db3ad.png)

- コンテンツ検索を実行すると、サポートされていない文字および大文字に変換されない可能性のあるブール演算子について、Microsoft 365 によって検索クエリが自動的にチェックされます。サポートされていない文字は非表示になっていることがよくあり、検索エラーを発生させたり、意図しない結果を返したりする原因になります。確認が行われるサポートされていない文字の詳細については、「[コンテンツ検索クエリでエラーを確認する](check-your-content-search-query-for-errors.md)」を参照してください。

- 英語以外の文字 (中国語の文字など) のキーワードが含まれている検索クエリがある場合は、![[クエリ検索] のクエリ言語-国/地域アイコン](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) [**クエリ言語-国/地域**] をクリックし、検索対象の言語-国のカルチャ コード値を選択します。既定の言語/地域はニュートラルです。コンテンツ検索の言語設定を変更する必要があるかどうかを判断するには、以下を考慮します。コンテンツの場所に検索対象の英語以外の文字が確実に含まれているにもかかわらず、検索結果が返されない場合は、言語設定が原因である可能性があります。

## <a name="partially-indexed-items"></a>部分的にインデックスが作成されたアイテム

- 予想される検索結果には、メールボックス内の部分的にインデックスが作成されたアイテムが含まれます。 SharePoint と OneDrive からの部分的にインデックスが作成されたアイテムは、予想される検索結果に含まれません。 詳細については、「[電子情報開示で部分的にインデックスが作成されたアイテム](partially-indexed-items-in-content-search.md)」を参照してください。

## <a name="searching-onedrive-accounts"></a>OneDrive アカウントの検索

- 組織内にある OneDrive サイトの URL リストの収集については、「[組織内にあるすべての OneDrive の場所のリストを作成する](/onedrive/list-onedrive-urls)」を参照してください。この記事のスクリプトでは、すべての OneDrive サイトのリストが含まれるテキスト ファイルが作成されます。このスクリプトを実行するには、SharePoint Online 管理シェルをインストールして使用する必要があります。検索する各 OneDrive サイトに、組織の MySite ドメインの URL を必ず追加するようにします。これは、組織のすべての OneDrive を含むドメインのことです (`https://contoso-my.sharepoint.com`)。以下は、ユーザーの OneDrive サイトの URL の例です: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`。

    ユーザーのプリンシパル名 (UPN) が変更される稀なケースにおいては、OneDrive の場所のURLが変更され、新しい UPN が組み込まれます。このような場合は、ユーザーの新しい OneDrive の URL を追加し古い OneDrive の URL を削除して、コンテンツ検索を変更する必要があります。詳細については、「[UPN の変更による OneDrive URL への影響](/onedrive/upn-changes)」をご覧ください。

## <a name="searching-microsoft-teams-and-microsoft-365-groups"></a>Microsoft Teams と Microsoft 365 グループの検索

Microsoft Team または Microsoft 365 グループに関連付けられているメールボックスを検索することができます。Microsoft Teams は Microsoft 365 グループ上に構築されているため、検索方法がよく似ています。どちらの場合も、グループまたはチームのメールボックスのみが検索されます。グループ メンバーまたはチーム メンバーのメールボックスは検索されません。検索するには、検索に明示的に追加する必要があります。

Microsoft Teams と Microsoft 365 グループのコンテンツを検索する場合は、次の点に注意してください。

- Teams と Microsoft 365 グループにあるコンテンツを検索するには、チームまたはグループに関連付けられているメールボックスと SharePoint サイトを指定する必要があります。

- プライベートチャネルのコンテンツは、チームのメールボックスではなく、ユーザーのメールボックスに保存されます。 プライベートチャネルのコンテンツを検索する方法については、「[プライベートチャネルの電子情報開示](/microsoftteams/ediscovery-investigation#ediscovery-of-private-and-shared-channels)」を参照してください。

- チームまたは Microsoft 365 グループのプロパティを表示するには、Exchange Online で **Get-UnifiedGroup** コマンドレットを実行します。これは、チームまたはグループに関連付けられているサイトの URL を取得するのに適した方法です。たとえば、次のコマンドは、上級管理職チームという名前の Microsoft 365 グループの選択されたプロパティを表示します。

  ```text
  Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
  DisplayName            : Senior Leadership Team
  Alias                  : seniorleadershipteam
  PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
  SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
  ```

    > [!NOTE]
    > **Get-UnifiedGroup** コマンドレットを実行するには、Exchange Online で View-Only Recipients という役割が割り当てられているか、View-Only Recipients という役割が割り当てられている役割グループに属している必要があります。

- ユーザーのメールボックスを検索すると、ユーザーが属しているチームまたは Microsoft 365 グループは検索されません。同様に、チームまたは Microsoft 365 グループを検索する場合は、指定したグループ メールボックスとグループ サイトのみが検索されます。検索に明示的に追加しない限り、グループ メンバーのメールボックスと OneDrive for Business アカウントは検索されません。

- チームまたは Microsoft 365 グループのメンバーの一覧を取得するには、Microsoft 365 管理センターの **[ホーム]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**[グループ]**</a> ページでプロパティを表示できます。または、Exchange Online PowerShell で次のコマンドを実行できます。

  ```powershell
  Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
  ```

    > [!NOTE]
    > **Get-UnifiedGroupLinks** コマンドレットを実行するには、Exchange Online で View-Only Recipients という役割が割り当てられているか、View-Only Recipients という役割が割り当てられている役割グループに属している必要があります。

- Teams チャネルに含まれる会話は、チームに関連付けられているメールボックスに保存されます。同様に、チャネルでチーム メンバーが共有するファイルはチームの SharePoint サイトに保存されます。そのため、チャネル内の会話とファイルを検索するには、コンテンツの場所としてチーム メールボックスと SharePoint サイトを追加する必要があります。

- または、Teams のチャット リストに含まれる会話はチャットに参加したユーザーの Exchange Online メールボックスに保存されます。チャットの会話でユーザーが共有するファイルは、ファイルを共有するユーザーの OneDrive for Business アカウントに保存されます。そのため、チャット リストの会話やファイルを検索するには、コンテンツの場所として個々のユーザーのメールボックスと OneDrive for Business アカウントを追加する必要があります。

    > [!NOTE]
    > Exchange ハイブリッド展開では、オンプレミスのメールボックスを持つユーザーは、Teams のチャット リストの一部である会話に参加する場合があります。この場合も、これらの会話のコンテンツは、オンプレミスのメールボックスを持つユーザーのためにクラウドベースの記憶域 (*オンプレミス ユーザーのクラウドベースのメールボックス* と呼ばれます) に保存されるため、検索可能です。詳細については、「[オンプレミス ユーザーの Teams チャット データを検索する](search-cloud-based-mailboxes-for-on-premises-users.md)」をご覧ください。

- 各チームまたは各チーム チャネルには、メモと共同作業用の Wiki が含まれています。Wiki コンテンツは、.mht 形式のファイルに自動的に保存されます。このファイルは、チームの SharePoint サイトの Teams Wiki データ ドキュメント ライブラリに保存されます。検索するコンテンツの場所としてチームの SharePoint サイトを指定すると、コンテンツ検索ツールを使用して Wiki を検索することができます。

    > [!NOTE]
    > Wiki でチームまたはチャネル (チームの SharePoint サイトを検索する場合) を検索する機能は、2017 年 6 月 22 日にリリースされました。その日付以降に保存または更新された Wiki ページは検索できるようになります。その日付より前に保存または更新された Wiki ページは、検索には使用できません。

- Teams チャネルでの会議と通話の概要情報は、会議または通話にダイヤルしたユーザーのメールボックスにも保存されます。つまり、コンテンツ検索を使用してこれらの概要レコードを検索することができます。概要情報は次のとおりです。

  - 会議または通話の日付、開始時刻、終了時刻、および継続時間

  - 各参加者の会議または通話の参加日時と退出日時

  - ボイスメールに送信された通話

  - 不在着信

  - 2 つの個別の通話として表される呼び出し転送

  会議と通話の概要レコードが検索できるようになるまで最大 8 時間かかる場合があります。

  検索結果では、会議の概要は **[種類]** フィールドで **[会議]** として識別されます。通話の概要は **[通話]** として識別されます。また、Teams チャネルと 1xN チャットに含まれる会話は、**[種類]** フィールドで **IM** として識別されます。

  ![Teams の会議、通話および 1 対 N チャットは "種類" フィールドで識別されます。](../media/O365-ContentSearch-Teams-MessageKind.png)

   詳細については、[Microsoft Teams が開始した通話と会議の電子情報開示](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-launches-ediscovery-for-calling-and-meetings/ba-p/210947)を参照してください。

- Teams チャネルのアプリ、1:1 チャット、1xN チャットで生成されたカード コンテンツは、メールボックスに保存され、検索することができます。 *カード* とは、短いコンテンツを対象とした UI コンテナです。 カードには複数のプロパティと添付ファイル、およびカード アクションをトリガーするボタンを含めることができます。 詳細については、「[カード](/microsoftteams/platform/task-modules-and-cards/what-are-cards)」を参照してください

  他の Teams のコンテンツと同様に、カードのコンテンツが保存されている場所は、カードが使用された場所に基づいています。 Teams チャネルで使用したカードのコンテンツは、Teams グループのメールボックスに保存されます。 1:1 チャットおよび 1xN チャットのカード コンテンツは、チャット参加者のメールボックスに保存されます。

  カード コンテンツの検索には、検索条件として `kind:microsoftteams` または `itemclass:IPM.SkypeTeams.Message` を使用できます。 検索結果をレビューする場合、Teams チャネルのボットによって生成されたカード コンテンツは `<appname>@teams.microsoft.com` として **送信者/作成者** のメール プロパティを持ち、`appname` はカード コンテンツを生成したアプリの名前です。 カード コンテンツがユーザーによって生成された場合、**送信者/作成者** の値がユーザーを識別します。

  コンテンツの検索結果でカード コンテンツを表示すると、そのコンテンツはメッセージの添付ファイルとして表示されます。 添付ファイルには `appname.html` と名付けられ、`appname` はカード コンテンツを生成したアプリの名前です。 次のスクリーンショットは、カード コンテンツ (Asana という名前のアプリが対象) が Teams や検索結果でどのように表示されるかを示しています。

  **Teams でのカード コンテンツ**

  ![Teams チャネル メッセージでのカード コンテンツ](../media/CardContentTeams.png)

  **検索結果でのカード コンテンツ**

  ![コンテンツ検索の結果での同じカード コンテンツ](../media/CardContentEdiscoverySearchResults.png)

  > [!NOTE]
  > 現時点でカード コンテンツの画像を検索結果に表示するには (前のスクリーンショット内のチェックマークなど)、検索結果を表示するために使用する同一のブラウザー セッション内で、別のタブを使用して Teams (https://teams.microsoft.com) にサインインする必要があります。それ以外の場合には、画像のプレースホルダーが表示されます。

- "**Kind**" 電子メール プロパティまたは "**メッセージの種類**" 検索条件を使用すると、Teams のコンテンツのみを検索できます。

  - キーワード検索クエリの一部として **Kind** プロパティを使用するには、検索クエリの **[キーワード]** ボックスに `kind:microsoftteams` と入力します。

    ![[キーワード] ボックスで kind:microsoftteams を使用します。](../media/O365-ContentSearch-Teams-Keywords.png)

  - 検索条件を使用するには、**[メッセージの種類]** 条件を追加し、値 `microsoftteams` を使用します。

    ![値 microsoftteams で [メッセージの種類] 条件を使用します。](../media/O365-ContentSearch-Teams-MessageKindCondition.png)

   条件は **AND** 演算子によってキーワード クエリに論理的に関連付けられます。つまり、アイテムは検索結果で返されるキーワード クエリと検索条件の両方に一致する必要があります。詳細については、「[コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md#guidelines-for-using-conditions)」の「条件を使用するためのガイドライン」セクションを参照してください。

## <a name="searching-yammer-groups"></a>Yammer グループの検索

**ItemClass** メール プロパティまたは **[タイプ]** 検索条件を使用して、Yammer グループの会話アイテムを具体的に検索できます。

  - キーワード検索クエリの一部として **ItemClass** プロパティを使用するには、検索クエリの **[キーワード]** ボックスで、次のいずれか (またはすべて) の property:value のペアを入力します。

     - ItemClass:IPM.Yammer.message
     - ItemClass:IPM.Yammer.poll
     - ItemClass:IPM.Yammer.praise
     - ItemClass:IPM.Yammer.question

    たとえば、次の検索クエリを使用して、Yammer のメッセージと Yammer の称賛アイテムを取得できます。

    ![ItemClass プロパティを使用して、Yammer アイテムを検索します。](../media/YammerContentSearch1.png)

  - または、**[タイプ]** メール条件を使用し、**[Yammer メッセージ]** を選択して、Yammer アイテムを返すこともできます。 たとえば、次の検索クエリでは、"社外秘" キーワードを含むすべての Yammer の会話アイテムが返されます。

    ![[タイプ] 条件カードを使用して Yammer の会話アイテムを検索します。](../media/YammerContentSearch2.png)

## <a name="searching-inactive-mailboxes"></a>非アクティブなメールボックスの検索

コンテンツ検索で非アクティブなメールボックスを検索できます。組織内の非アクティブなメールボックスのリストを取得するには、Exchange Online PowerShell でコマンド `Get-Mailbox -InactiveMailboxOnly` を実行します。または、セキュリティ/コンプライアンス センターの **[情報ガバナンス]**、\>**[保持]** の順に移動して、**[詳細]**、![ナビゲーション バーの省略記号](../media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif)、\>**[非アクティブなメールボックス]** の順にクリックすることもできます。

非アクティブなメールボックスを検索するときの留意点を以下に示します。

- 既存のコンテンツ検索にユーザー メールボックスが含まれ、そのメールボックスが非アクティブになった場合、非アクティブになった後に検索を再実行すると、コンテンツ検索は非アクティブなメールボックスの検索を続行します。

- 場合によっては、ユーザーは同じ SMTP アドレスを持つアクティブなメールボックスおよび非アクティブなメールボックスを所有している可能性があります。この場合、コンテンツ検索の場所として選択した特定のメールボックスのみが検索されます。つまり、検索にユーザーのメールボックスを追加する場合に、アクティブなメールボックスと非アクティブなメールボックスの両方が検索されることは想定できません。検索に明示的に追加したメールボックスのみが検索されます。

- Security＆Compliance Center PowerShell を使用してコンテンツ検索を作成し、非アクティブなメールボックスを検索できます。 これを行うには、ピリオド (.) を事前に追加する必要があります。 非アクティブなメールボックスのメール アドレスに。 たとえば次のコマンドは、メール アドレス pavelb@contoso.onmicrosoft.com を含む非アクティブなメールボックスを検索するコンテンツ検索を作成します。

   ```powershell
   New-ComplianceSearch -Name InactiveMailboxSearch -ExchangeLocation .pavelb@contoso.onmicrosoft.com -AllowNotFoundExchangeLocationsEnabled $true
   ```

- 同じ SMTP アドレスを持つアクティブなメールボックスと非アクティブなメールボックスを所有しないようにすることを強くお勧めします。非アクティブなメールボックスに割り当てられている SMTP アドレスを再使用する場合は、非アクティブなメールボックスを復元するか、非アクティブなメールボックスのコンテンツをアクティブなメールボックス (またはアクティブなメールボックスのアーカイブ) に復元して、非アクティブなメールボックスを削除することをお勧めします。詳細については、以下のいずれかのトピックを参照してください。

  - [Office 365 で非アクティブなメールボックスを回復する](recover-an-inactive-mailbox.md)

  - [Office 365 の非アクティブなメールボックスを復元する](restore-an-inactive-mailbox.md)

  - [Office 365 の非アクティブなメールボックスを削除する](delete-an-inactive-mailbox.md)

## <a name="searching-disconnected-or-de-licensed-mailboxes"></a>切断された、またはライセンスを解除されたメールボックスを検索する

Exchange Online ライセンス (または Microsoft 365 ライセンス全体) がユーザー アカウントまたは Azure Active Directory から削除されると、ユーザーのメールボックスは *切断された* メールボックスになります。 これは、このメールボックスがユーザー アカウントに関連付けられていないことを意味します。 切断されたメールボックスを検索すると、次のようになります。

- ライセンスがメールボックスから削除されている場合は、メールボックスを検索できなくなります。

- 既存のコンテンツ検索にライセンスが削除されたメールボックスが含まれている場合は、コンテンツ検索を再実行すると切断されたメールボックスの検索結果が一切返されなくなります。

- 検索するための Exchange コンテンツの場所として、コンテンツ検索を作成して切断されたメールボックスを指定するのに **New-ComplianceSearch** コマンドレットを使用する場合は、コンテンツ検索からは切断されたメールボックスの検索結果が一切返されません。

検索できるように切断されたメールボックスにデータを保持する必要がある場合は、ライセンスを削除する前に、メールボックスに保留を適用する必要があります。 これによりデータが保持され、保留が削除されるまで、切断されたメールボックスを検索できます。 保留に関する詳細情報については、[Exchange Online メールボックスに適用されている保留の種類を特定する方法](identify-a-hold-on-an-exchange-online-mailbox.md)をご確認ください。

## <a name="searching-for-content-in-a-sharepoint-multi-geo-environment"></a>SharePoint Multi-Geo 環境のコンテンツを検索する

電子情報開示マネージャーが、[SharePoint Multi-Geo 環境](../enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)内の複数の地域の SharePoint および OneDrive でコンテンツを検索する必要がある場合、これを実行できるようにするには次の操作を実行する必要があります。

1. 電子情報開示マネージャーが検索する必要があるサテライト地域の場所ごとに、個別のユーザー アカウントを作成します。 その地域の場所にあるサイトのコンテンツを検索するには、電子情報開示マネージャーは、その場所用に作成されたアカウントにサインインしてからコンテンツ検索を実行する必要があります。

2. 電子情報開示マネージャーが検索する必要がある各サテライトの地理的位置 (および対応するユーザー アカウント) 用に、検索のアクセス許可フィルターを作成します。 それぞれの検索のアクセス許可フィルターにより、特定の場所と関連付けられているユーザー アカウントに電子情報開示マネージャーがサインインした際に、コンテンツ検索の対象がその地理的位置に限定されます。

> [!TIP]
> [Advanced eDiscovery](overview-ediscovery-20.md) の検索ツールを使用する場合はこの方法を使用する必要はありません。 これは、Advanced eDiscovery で SharePoint サイトと OneDrive アカウントを検索すると、すべてのデータセンターが検索されるためです。 地域限定のユーザー アカウントと検索のアクセス許可フィルターを使用するこの方法を使用する必要があるのは、コンテンツ検索ツールを使用して[電子情報開示のケース](./get-started-core-ediscovery.md)と関連付けられている検索を実行する場合のみです。

たとえば、電子情報開示マネージャーが、北米、ヨーロッパ、アジア太平洋のサテライトの場所で SharePoint と OneDrive のコンテンツを検索する必要があるとします。 最初の手順では、1 つの場所で 1 つずつ、ユーザー アカウントを 3 つ作成します。 次の手順では、1 つの場所で 1 つずつ、*かつ* それぞれの場所のユーザー アカウント用に、検索のアクセス許可フィルターを 3 つ作成します。 このシナリオでの 3 つの検索のアクセス許可フィルターの例を示します。 それぞれの例では、**Region** によりその地域の SharePoint データセンターの場所が指定され、**Users** パラメーターにより対応するユーザー アカウントが指定されています。

**北アメリカ**

```powershell
New-ComplianceSecurityFilter -FilterName "SPMultiGeo-NAM" -Users ediscovery-nam@contoso.com -Region NAM -Action ALL
```

**ヨーロッパ**

```powershell
New-ComplianceSecurityFilter -FilterName "SPMultiGeo-EUR" -Users ediscovery-eur@contoso.com -Region EUR -Action ALL
```

**アジア太平洋**

```powershell
New-ComplianceSecurityFilter -FilterName "SPMultiGeo-APC" -Users ediscovery-apc@contoso.com -Region APC -Action ALL
```

検索のアクセス許可フィルターを使用して複数地域環境のコンテンツを検索する場合は、次の点にご注意ください。

- **Region** パラメーターにより、指定されたサテライトの場所が検索されます。電子情報開示マネージャーが、検索のアクセス許可フィルターで指定された対象以外の SharePoint サイトと OneDrive サイトのみを検索すると、検索結果は何も返されません。

- Exchange メールボックスの検索は、**Region** パラメーターにより制御されません。 メールボックスを検索すると、すべてのデータセンターが検索されます。

複数地域環境での検索のアクセス許可フィルターの使用に関する詳細については、[電子情報開示調査のためにコンプライアンスの境界を設定する](set-up-compliance-boundaries.md#searching-and-exporting-content-in-multi-geo-environments) の「複数地域環境でのコンテンツの検索とエクスポート」セクションを参照してください。
