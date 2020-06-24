---
title: セキュリティ/コンプライアンス センターで監査ログを検索する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: 0d4d0f35-390b-4518-800e-0c7ec95e946c
description: 'セキュリティ/コンプライアンス センターを使用して統合監査ログを検索し、組織内のユーザーと管理者のアクティビティを確認できます。 '
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 83eb4c453b3a11cb037e62e43525199fa247c3f5
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818987"
---
# <a name="search-the-audit-log-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センターで監査ログを検索する

ユーザーが特定のドキュメントを表示したかどうか、またはメールボックスからアイテムを削除したかどうかを確認する必要がありますか。 その場合は、セキュリティ/コンプライアンス センターを使用して統合監査ログを検索し、組織内のユーザーと管理者のアクティビティを確認できます。 なぜ統合監査ログが必要なのでしょうか。 Office 365 で以下の種類の[ユーザーおよび管理アクティビティ](#audited-activities)を検索できるためです:

- SharePoint Online および OneDrive for Business 内のユーザー アクティビティ

- Exchange Online 内のユーザー アクティビティ (Exchange メールボックス監査ログ)

- SharePoint Online 内の管理者アクティビティ

- Azure Active Directory (Office 365 のディレクトリ サービス) 内の管理者アクティビティ

- Exchange Online 内の管理者アクティビティ (Exchange 管理者監査ログ)

- Sway 内のユーザーおよび管理者のアクティビティ

- セキュリティ/コンプライアンス センター内の電子情報開示アクティビティ

- Power BI 内のユーザーおよび管理者のアクティビティ

- Microsoft Teams 内のユーザーおよび管理者のアクティビティ

- Dynamics 365 内のユーザーおよび管理者のアクティビティ

- Yammer 内のユーザーおよび管理者のアクティビティ

- Microsoft Power Automate 内のユーザーおよび管理者のアクティビティ

- Microsoft Stream 内のユーザーおよび管理者のアクティビティ

- Microsoft Workplace Analytics でのアナリストと管理者のアクティビティ

- Microsoft Power Apps 内のユーザーおよび管理者のアクティビティ

- Microsoft Forms 内のユーザーおよび管理者のアクティビティ

- SharePoint Online または Microsoft Teams を使用するサイトの機密ラベルのユーザーおよび管理アクティビティ

## <a name="requirements-to-search-the-audit-log"></a>監査ログを検索するための要件

監査ログの検索を開始する前に、次の項目を必ず確認してください。

- 監査ログの検索を開始するには、自分 (または他の管理者) が監査ログを有効にしている必要があります。 有効にするには、セキュリティ/コンプライアンス センターの [**監査ログの検索**] ページで [**監査を有効にする**] をクリックします。 (このリンクが表示されない場合、組織の監査はすでに有効になっています)。有効にすると、監査ログの準備中で、準備が完了してから数時間で検索を実行できることを通知するメッセージが表示されます。 これを行う必要があるのは 1 回だけです。 詳細については、「[監査ログの検索を有効または無効にする](turn-audit-log-search-on-or-off.md)」をご覧ください。

  > [!NOTE]
  > 現在、既定で監査が有効になるように準備を進めています。 それまでは、前述のように監査を有効にすることができます。

- 監査ログを検索するには、Exchange Online で閲覧限定の監査ログまたは監査ログの役割が割り当てられている必要があります。 既定では、これらの役割は Exchange 管理センターの [**アクセス許可**] ページでコンプライアンス管理役割グループまたは組織管理役割グループに割り当てられています。 Office 365 および Microsoft 365 のグローバル管理者は自動的に、組織管理役割グループのメンバーとして Exchange Online に追加されます。 最小限の特権レベルで監査ログを検索する権限をユーザーに付与するには、Exchange Online でカスタムの役割グループを作成し、閲覧限定の監査ログまたは監査ログの役割を追加し、この新しい役割グループのメンバーとしてユーザーを追加します。 詳細については、「[Exchange Online で役割グループを管理する](https://go.microsoft.com/fwlink/p/?LinkID=730688)」を参照してください。

  > [!IMPORTANT]
  > セキュリティ/コンプライアンス センターの **[アクセス許可]** ページでユーザーに View-Only Audit Logs (閲覧限定の監査ログ) または Audit Logs (監査ログ) の役割を割り当てると、監査ログを検索できなくなります。 Exchange Online でアクセス許可を割り当てる必要があります。 これは、監査ログの検索に使用される基本のコマンドレットが ExchangeOnline コマンドレットだからです。

- When an audited activity is performed by a user or admin, an audit record is generated and stored in the audit log for your organization. The length of time that an audit record is retained (and searchable in the audit log) depends on your Office 365 or Microsoft 365 Enterprise subscription, and specifically the type of the license that is assigned to specific users.

  - Office 365 E5 または Microsoft 365 E5 ライセンスが割り当てられたユーザー (または Microsoft 365 E5 Compliance または Microsoft 365 E5 eDiscovery and Audit アドオン ライセンスを持っているユーザー) の場合、Azure Active Directory、Exchange、および SharePoint アクティビティの監査レコードは、既定で 1 年間保持されます。 また、組織では、監査ログの保持ポリシーを作成して、その他のサービスのアクティビティについての監査レコードを最大 1 年間保持します。 詳細については、「[監査ログ保持ポリシーを管理する](audit-log-retention-policies.md)」を参照してください。

    > [!NOTE]
    > 監査レコードを 1 年間保持するプライベート プレビュー プログラムに参加した場合、一般提供のロールアウト日前に生成された監査レコードの保持期間はリセットされません。

  - その他 (E5 以外) の Office 365 または Microsoft 365 ライセンスが割り当てられているユーザーの場合、監査レコードは 90 日間保持されます。 統合監査ログをサポートする Office 365 および Microsoft 365 サブスクリプションのリストについては、「[セキュリティおよびコンプライアンス センター サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)」を参照してください。

    > [!NOTE]
    > デフォルトでメールボックス監査がオンになっている場合でも、一部のユーザーのメールボックス監査イベントが、セキュリティ/コンプライアンス センターまたは Office 365 マネージメント アクティビティ API の監査ログ検索で見つからないことに気付く場合があります。 詳細については、「[More information about mailbox audit logging (メールボックス監査ログの詳細)](enable-mailbox-auditing.md#more-information)」を参照してください。

- 組織の監査ログの検索を無効にする場合は、Exchange Online 組織に接続されたリモート PowerShell で次のコマンドを実行できます。

  ```powershell
  Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
  ```

    監査検索を再度有効にするには、Exchange Online PowerShell で次のコマンドを実行できます。

  ```powershell
  Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
  ```

  詳細については、「[監査ログの検索を無効にする](turn-audit-log-search-on-or-off.md)」を参照してください。

- 前述のように、監査ログの検索に使用される基礎となるコマンドレットは Exchange Online コマンドレットの **Search-UnifiedAuditLog** です。 つまり、セキュリティ/コンプライアンス センターの **[監査ログの検索]** ページではなく、このコマンドレットを使用して監査ログを検索できます。 このコマンドレットは、Exchange Online 組織に接続されているリモートの PowerShell で実行する必要があります。 詳細については、「[Search-UnifiedAuditLog](https://go.microsoft.com/fwlink/p/?linkid=834776)」を参照してください。

  **Search-UnifiedAuditLog** コマンドレットによって返された検索結果を CSV ファイルにエクスポートする方法の詳細については、「[監査ログ レコードをエクスポート、構成、表示する](export-view-audit-log-records.md#tips-for-exporting-and-viewing-the-audit-log)」の「監査ログをエクスポート、表示するためのヒント」のセクションを参照してください。

- If you want to programmatically download data from the audit log, we recommend that you use the Office 365 Management Activity API instead of using a PowerShell script. The Office 365 Management Activity API is a REST web service that you can use to develop operations, security, and compliance monitoring solutions for your organization. For more information, see [Office 365 Management Activity API reference](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).

- It can take up to 30 minutes or up to 24 hours after an event occurs for the corresponding audit log record to be returned in the results of an audit log search. The following table shows the time it takes for the different services in Office 365.

  |**Microsoft 365 サービスまたは機能**|**30 分**|**24 時間**|
  |:-----|:-----:|:-----:|
  |Advanced Threat Protection および脅威インテリジェンス|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Azure Active Directory (ユーザー ログイン イベント)||![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
  |Azure Active Directory (管理イベント)||![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
  |データ損失防止|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Dynamics 365 CRM||![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
  |電子情報開示|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Exchange Online|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Microsoft Power Automate||![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
  |Microsoft Project|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Microsoft Stream|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Microsoft Teams|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Power アプリ||![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
  |Power BI|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |セキュリティ/コンプライアンス センター|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |機密ラベル||![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
  |SharePoint Online と OneDrive for Business|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Sway||![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
  |Workplace Analytics|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Yammer||![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Microsoft Forms|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
  ||||

- Azure Active Directory (Azure AD) は、Office 365 のディレクトリ サービスです。 統合監査ログには、Microsoft 365 管理センターまたは Azure 管理ポータルで実行されたユーザー、グループ、アプリケーション、ドメイン、およびディレクトリのアクティビティが記録されます。 Azure AD のイベントの全リストについては、「[Azure Active Directory 監査レポートのイベント](https://go.microsoft.com/fwlink/p/?LinkID=616549)」を参照してください。

- Power BI の監査ログは、既定では有効になっていません。 監査ログ内の Power BI アクティビティを検索するには、Power BI 管理ポータルで監査を有効にする必要があります。 手順については、[Power BI 管理ポータル](https://docs.microsoft.com/power-bi/service-admin-portal#audit-logs)の「監査ログ」セクションをご覧ください。

## <a name="search-the-audit-log"></a>監査ログの検索

以下に、Office 365 で監査ログを検索するためのプロセスを示します。

[手順 1: 監査ログの検索を実行する](#step-1-run-an-audit-log-search)

[手順 2: 検索結果を表示する](#step-2-view-the-search-results)

[手順 3: 検索結果をフィルター処理する](#step-3-filter-the-search-results)

[手順 4: 検索結果をファイルにエクスポートする](#step-4-export-the-search-results-to-a-file)

### <a name="step-1-run-an-audit-log-search"></a>手順 1: 監査ログの検索を実行する

1. [https://protection.office.com](https://protection.office.com) に移動します。

    > [!TIP]
    > 現在ログオンしている資格情報が使用されないようにするために、プライベート ブラウズ セッション (通常のセッションではありません) を使用してセキュリティ/コンプライアンス センターにアクセスします。 Internet Explorer または Microsoft Edge で InPrivate ブラウズ セッションを開くには、Ctrl + Shift + P キーを押します。 Google Chrome でプライベート ブラウズ セッション (シークレット ウィンドウと呼ばれる) を開くには、Ctrl + Shift + N キーを押します。

2. 職場または学校のアカウントを使用してサインインします。

3. セキュリティ/コンプライアンス センターの左側のウィンドウで、**[検索]** をクリックし、**[監査ログの検索]** をクリックします。

    [**監査ログの検索**] ページが表示されます。

    ![検索条件を設定し、[検索] をクリックしてレポートを実行する](../media/8639d09c-2843-44e4-8b4b-9f45974ff7f1.png)

    > [!NOTE]
    > You have to first turn on audit logging before you can run an audit log search. If the **Start recording user and admin activity** link is displayed, click it to turn on auditing. If you don't see this link, auditing has already been turned on for your organization.

4. 次の検索条件を設定します。

    a. [**アクティビティ**]: ドロップダウン リストをクリックして検索できるアクティビティを表示します。 ユーザーと管理者のアクティビティが、関連するアクティビティのグループに編成されています。 特定のアクティビティを選択することも、アクティビティ グループ名をクリックして、グループ内のすべてのアクティビティを選択することもできます。 選択したアクティビティをクリックして、選択を解除することもできます。 検索の実行後、選択したアクティビティの監査ログ エントリのみが表示されます。 [**すべてのアクティビティの結果を表示**] を選択すると、選択したユーザーまたはユーザーのグループによって実行されたすべてのアクティビティの結果が表示されます。

    監査ログには、100 件以上のユーザーおよび管理者アクティビティが記録されます。 各種サービスの各アクティビティの説明を確認するには、本記事のこのトピックの「**監査されるアクティビティ**」タブをクリックしてください。

    b. [**開始日**] と [**終了日**]: 既定で過去 7 日間が選択されています。 日付と時間の範囲を選択し、その期間内に発生したイベントを表示します。 日付と時間は、協定世界時 (UTC) 形式で指定します。 指定できる日付範囲は最大 90 日です。 選択した日付範囲が 90 日間よりも大きい場合は、エラーが表示されます。

    > [!TIP]
    > If you're using the maximum date range of 90 days, select the current time for the **Start date**. Otherwise, you'll receive an error saying that the start date is earlier than the end date. If you've turned on auditing within the last 90 days, the maximum date range can't start before the date that auditing was turned on.

    c. [**ユーザー**]: このボックスをクリックし、検索結果を表示する 1 人以上のユーザーを選択します。 このボックスで選択したユーザーによって実行された選択したアクティビティの監査ログ エントリが結果の一覧に表示されます。 組織のすべてのユーザー (およびサービス アカウント) のエントリを返すには、このボックスを空白のままにします。

    d. [**ファイル、フォルダー、またはサイト**]: 指定したキーワードを含むフォルダーのファイルに関連するアクティビティを検索するには、ファイルまたはフォルダー名の一部またはすべてを入力します。 ファイルまたはフォルダーの URL を指定することもできます。 URL を使用する場合は、完全な URL パスを入力するか、URL の一部を入力する場合は、特殊文字やスペースを含めないでください。

    組織内のすべてのファイルおよびフォルダーのエントリを返すには、このボックスを空白のままにします。

   **ヒント**

   - ある**サイト**に関するすべてのアクティビティを検索する場合、URL の後ろにワイルドカード文字 (\*) を追加して、そのサイトのすべてのエントリが返されるようにします。例: **"https://contoso-my.sharepoint.com/personal/*"**

   - 特定の**ファイル**に関連するすべてのアクティビティを探す場合は、ファイル名の前にワイルドカード文字 (\*) を追加すると、そのファイルのすべてのエントリが返されます (例: **"*Customer_Profitability_Sample.csv"**)。

5. [**検索**] をクリックして、設定した検索条件で検索を実行します。

   検索結果が読み込まれ、しばらくすると、それらが [**結果**] の下に表示されます。 検索が完了すると、検索結果の件数が表示されます。 [**結果**] ウィンドウには、イベント 150 件の増分で最大 5,000 件のイベントが表示されます。 検索条件を満たすイベントが 5,000 件を超える場合、最新の5,000 件のイベントが表示されます。

   ![検索が完了すると、検索結果の件数が表示される](../media/986216f1-ca2f-4747-9480-e232b5bf094c.png)

#### <a name="tips-for-searching-the-audit-log"></a>監査ログを検索するためのヒント

- 検索する特定のアクティビティを選択するには、アクティビティ名をクリックします。 またはグループ名をクリックして、グループ内のすべてのアクティビティ ([**ファイルとフォルダーのアクティビティ**] など) を検索できます。 アクティビティが選択されている場合は、そのアクティビティをクリックして、選択を取り消すことができます。 また、検索ボックスを使用して、入力したキーワードを含むアクティビティを表示することもできます。

  ![アクティビティ グループの名前をクリックしてすべてのアクティビティを選択する](../media/3cde97cb-6f35-47c0-8612-ecd9c6ac36a3.png)

- Exchange 管理者監査ログのイベントを表示するには、[**アクティビティ**] リストの [**すべてのアクティビティの結果を表示**] を選択する必要があります。 この監査ログのイベントには、結果の [**アクティビティ**] 列にコマンドレット名 (**Set-Mailbox** など) が表示されます。 詳細については、 このトピックの [**監査されるアクティビティ**] タブをクリックし、[**Exchange 管理者アクティビティ**] をクリックします。

  Similarly, there are some auditing activities that don't have a corresponding item in the **Activities** list. If you know the name of the operation for these activities, you can search for all activities, then filter the results by typing the name of the operation in the box for the **Activity** column. See [Step 3: Filter the search results](#step-3-filter-the-search-results) for more information about filtering the results.

- Click **Clear** to clear the current search criteria. The date range returns to the default of the last seven days. You can also click **Clear all to show results for all activities** to cancel all selected activities.

- 5,000 件の結果が見つかった場合、検索条件に一致するイベントが 5,000 件を超えていると見なすことができます。 検索条件を絞り込み、返される結果が少なくなるように検索を再実行するか、[**結果のエクスポート**] \> [**すべての結果をダウンロード**] を選択して、すべての検索結果をエクスポートできます。

### <a name="step-2-view-the-search-results"></a>手順 2: 検索結果を表示する

The results of an audit log search are displayed under **Results** on the **Audit log search** page. As previously stated a maximum of 5,000 (newest) events are displayed in increments of 150 events. To display more events you can use the scroll bar in the **Results** pane or you can press **Shift + End** to display the next 150 events.

検索結果には、検索によって返された各イベントに関する次の情報が含まれます。

- [**日付**]: イベントが発生した日付と時刻 (UTC 形式)。

- [**IP アドレス**]: アクティビティがログに記録されたときに使用されたデバイスの IP アドレス。 IP アドレスは、IPv4 または IPv6 アドレスの形式で表示されます。

   > [!NOTE]
  > 一部のサービスでは、このフィールドに表示される値は、ユーザーに代わってサービスを呼び出す信頼できるアプリケーション (Office on the web アプリなど) の IP アドレスであり、アクティビティを実行したユーザーが使用するデバイスの IP アドレスではない場合があります。 また、Azure Active Directory 関連のイベントの管理者のアクティビティ (またはシステムアカウントによって実行されるアクティビティ) の場合、IP アドレスはログに記録されず、このフィールドに表示される値は `null` になります。

- [**ユーザー**]: イベントをトリガーしたアクションを実行したユーザー (またはサービス アカウント)。

- [**アクティビティ**]: ユーザーが実行したアクティビティ。 この値は [**アクティビティ**] ドロップダウン リストで選択したアクティビティに対応します。 Exchange 管理者監査ログのイベントの場合、この列の値は、Exchange コマンドレットになります。

- [**アイテム**]: 対応するアクティビティの結果として作成または変更されたオブジェクト。 たとえば、表示または変更されたファイルまたは更新されたユーザー アカウントなどです。 すべてのアクティビティにこの列の値があるとは限りません。

- [**詳細**]: アクティビティに関する追加の詳細。 ここでも、すべてのアクティビティに値があるとは限りません。

> [!TIP]
> Click a column header under **Results** to sort the results. You can sort the results from A to Z or Z to A. Click the **Date** header to sort the results from oldest to newest or newest to oldest.

#### <a name="view-the-details-for-a-specific-event"></a>特定のイベントの詳細を表示する

イベントの詳細情報を表示するには、検索結果一覧のイベント レコードをクリックします。 イベント レコードの詳細なプロパティが記載された [**詳細**] ページが表示されます。 表示されるプロパティは、イベントが発生するサービスによって変わります。 これらの詳細な情報を表示するには、[**詳細情報**] をクリックします。 説明については、「[監査ログの詳細なプロパティ](detailed-properties-in-the-office-365-audit-log.md)」をご覧ください。

![[詳細情報] をクリックして監査ログのイベント レコードの詳細なプロパティを表示する](../media/6df582ae-d339-4735-b1a6-80914fb77a08.png)

### <a name="step-3-filter-the-search-results"></a>手順 3: 検索結果をフィルター処理する

並べ替えに加えて、監査ログの検索の結果をフィルター処理することもできます。 これは、特定のユーザーやアクティビティに結果をすばやくフィルター処理できる優れた機能です。 最初に広範な検索を作成してから、結果をすばやくフィルター処理し、特定のイベントを表示できます。 さらに、より小さく簡潔な一連の結果が返されるようにするには、検索条件を絞り込み、検索を再実行します。

結果をフィルター処理するには、次の手順を実行します。

1. 監査ログの検索を実行します。

2. 結果が表示されたら、[**結果をフィルター**] をクリックします。

   各列見出しの下にキーワード ボックスが表示されます。

3. Click one of the boxes under a column header and type a word or phrase, depending on the column you're filtering on. The results will dynamically readjust to display the events that match your filter.

   ![フィルターに単語を入力して、フィルターに一致するイベントを表示する](../media/542dc323-a997-402c-934b-cc5e218e50bc.png)

4. フィルターを解除するには、フィルター ボックスの [**X**] をクリックするか、[**フィルターの非表示**] をクリックします。

> [!TIP]
> To display events from the Exchange admin audit log, type a **-** (dash) in the **Activity** filter box. This will display cmdlet names, which are displayed in the **Activity** column for Exchange admin events. Then you can sort the cmdlet names in alphabetical order.

### <a name="step-4-export-the-search-results-to-a-file"></a>手順 4: 検索結果をファイルにエクスポートする

監査ログの検索の結果を、ローカル コンピューター上のコンマ区切り値 (CSV) ファイルにエクスポートできます。 このファイルを Microsoft Excel で開いて、検索、並べ替え、フィルター処理、および単一の列 (複数のプロパティが含まれる) の複数列への分割などの機能を使用できます。

1. 監査ログの検索を実行して、目的の結果が得られるまで検索条件を変更します。

2. [**結果のエクスポート**] をクリックして、次のいずれかのオプションを選択します。

   - [**読み込まれた結果を保存**]: [**監査ログの検索**] ページの [**結果**] に表示されたエントリのみをエクスポートするには、このオプションを選択します。 ダウンロードした CSV ファイルには、ページに表示されている同じ列 (およびデータ) (日付、ユーザー、アクティビティ、アイテム、詳細) が含まれています。 CSV ファイルには、監査ログ エントリからの詳細な情報を含む追加の列 ([**その他**] と呼ばれる) が含まれます。 [**監査ログの検索**] ページに読み込まれた (および表示可能な) 同じ結果をエクスポートしているため、最大 5,000 件のエントリがエクスポートされます。

   - **[すべての結果をダウンロードする]**: 検索条件に一致する監査ログのすべてのエントリをエクスポートするには、このオプションを選択します。 検索結果セットが大きい場合、このオプションを選択すると、[**監査ログの検索**] ページに表示できる 5,000 個の監査レコードに加えて、監査ログのすべてのエントリがダウンロードされます。 このオプションは、監査ログから CSV ファイルに生データをダウンロードし、**AuditData** という名前の列に監査ログ エントリからの追加情報を格納します。 このエクスポート オプションを選択した場合、ファイルが他のオプションを選択した場合にダウンロードされるファイルよりはるかに大きくなる可能性があるため、ファイルのダウンロードには時間がかかることがあります。

     > [!IMPORTANT]
     > You can download a maximum of 50,000 entries to a CSV file from a single audit log search. If 50,000 entries are downloaded to the CSV file, you can probably assume there are more than 50,000 events that met the search criteria. To export more than this limit, try using a date range to reduce the number of audit log entries. You might have to run multiple searches with smaller date ranges to export more than 50,000 entries.

3. エクスポート オプションを選択すると、ウィンドウの下部にメッセージが表示され、CSV ファイルを開く、[ダウンロード] フォルダーに保存する、または特定のフォルダーに保存するかを選択するように求められます。

#### <a name="more-information-about-exporting-and-viewing-audit-log-search-results"></a>監査ログの検索結果のエクスポートと表示に関する詳細情報

- すべての検索結果をダウンロードすると、その CSV ファイルには **AuditData** という列が含まれており、その列に各イベントに関する追加情報が格納されています。 この列のデータは、監査ログ レコードの複数のプロパティを含む JSON オブジェクトで構成されています。 この JSON オブジェクトに含まれる *property:value* の各ペアは、コンマで区切られます。 Excel の Power Query エディターに含まれる JSON 変換ツールを使用すると、[**AuditData**] 列を複数の列に分割し、JSON オブジェクトのプロパティごとに個別の列を設定できます。 このようにすると、これらの 1 つ以上のプロパティで並べ替えやフィルター処理を行うことができます。 Power Query エディターを使用して JSON オブジェクトを変換するための詳しい手順については、「[監査ログ レコードをエクスポート、構成、表示する](export-view-audit-log-records.md)」を参照してください。

  **AuditData** 列を分割した後、[**操作**] 列でフィルター処理して、特定の種類のアクティビティの詳細なプロパティを表示できます。

- **[すべての結果をダウンロードする]** オプションは、監査ログから CSV ファイルに生データをダウンロードします。 このファイルには **[読み込まれた結果を保存]** オプションを選択した場合にダウンロードされるファイルと異なる列名 (CreationDate、UserIds、Operation、AuditData) が含まれます。 同じアクティビティに対する 2 つの別の CSV ファイル内の値が異なる場合もあります。 たとえば、CSV ファイル内の [**アクション**] 列のアクティビティが、[**監査ログの検索**] ページの [**アクティビティ**] 列に表示される "わかりやすい" 名前とは異なる値になることがあります。 たとえば、MailboxLogin と メールボックスへのユーザーのサインインです。

- さまざまなサービスのイベントが含まれている検索クエリからすべての結果をダウンロードすると、CSV ファイルの **[AuditData]** 列には、そのアクションが実行されたサービスに応じて異なるプロパティが含まれます。 たとえば、Exchange と Azure AD の監査ログのエントリには、アクションが成功したかどうかを示す **ResultStatus** というプロパティが含まれます。 このプロパティは、SharePoint のイベントには含まれません。 同様に、SharePoint イベントには、ファイルおよびフォルダー関連のアクティビティのサイト URL を識別するプロパティがあります。 この動作を軽減するには、別々の検索を使用して、1 つのサービスからのアクティビティの結果をエクスポートすることを検討してください。

  すべての結果をダウンロードする場合に CSV ファイルの **[AuditData]** 列に一覧表示されるプロパティの多く、および各プロパティが適用されるサービスについては、「[監査ログの詳細なプロパティ](detailed-properties-in-the-office-365-audit-log.md)」を参照してください。

## <a name="audited-activities"></a>監査されるアクティビティ

このセクションの表で、Office 365 で監査されるアクティビティについて説明します。 これらのイベントを検索するには、セキュリティ/コンプライアンス センターで監査ログを検索します。

以下の表は、関連するアクティビティまたは特定のサービスのアクティビティをグループ別にまとめたものです。 表には、[**アクティビティ**] ドロップダウン リストに表示されるフレンドリ名と、監査レコードの詳細情報および検索結果をエクスポートするときに CSV ファイルに表示される対応する操作名が含まれています。 詳細情報の説明については、「[監査ログの詳細なプロパティ](detailed-properties-in-the-office-365-audit-log.md)」をご覧ください。

特定の表に移動するには、次のいずれかのリンクをクリックしてください。

||||
|:-----|:-----|:-----|
|[ファイル アクティビティとページ アクティビティ](#file-and-page-activities)|[フォルダー アクティビティ](#folder-activities)|[SharePoint リスト アクティビティ](#sharepoint-list-activities)|
|[共有アクティビティとアクセス要求アクティビティ](#sharing-and-access-request-activities)|[同期アクティビティ](#synchronization-activities)|[サイトの権限のアクティビティ](#site-permissions-activities)|
|[サイト管理アクティビティ](#site-administration-activities)|[Exchange メールボックス アクティビティ](#exchange-mailbox-activities)|[Sway アクティビティ](#sway-activities)|
|[ユーザー管理アクティビティ](#user-administration-activities)|[Azure AD グループ管理アクティビティ](#azure-ad-group-administration-activities)|[アプリケーション管理アクティビティ](#application-administration-activities)|
|[役割管理アクティビティ](#role-administration-activities)|[ディレクトリ管理アクティビティ](#directory-administration-activities)|[電子情報開示アクティビティ](#ediscovery-activities)|
|[Advanced eDiscovery アクティビティ](#advanced-ediscovery-activities)|[Power BI アクティビティ](#power-bi-activities)|[Microsoft Workplace Analytics](#microsoft-workplace-analytics-activities)|
|[Microsoft Teams アクティビティ](#microsoft-teams-activities)|[Microsoft Teams 医療活動アクティビティ](#microsoft-teams-healthcare-activities)|[Microsoft Teams Shifts アクティビティ](#microsoft-teams-shifts-activities)|
|[Yammer アクティビティ](#yammer-activities)|[Microsoft Power Automate のアクティビティ](#microsoft-power-automate-activities)|[Microsoft Power Apps のアクティビティ](#microsoft-power-apps-activities)|
|[Microsoft Stream アクティビティ](#microsoft-stream-activities)|[コンテンツ エクスプローラー アクティビティ](#content-explorer-activities)|[検疫アクティビティ](#quarantine-activities)|
|[Microsoft Forms アクティビティ](#microsoft-forms-activities)|[機密ラベル アクティビティ](#sensitivity-label-activities)|[Exchange 管理アクティビティ](#exchange-admin-audit-log)|
||||

### <a name="file-and-page-activities"></a>ファイル アクティビティとページ アクティビティ

次の表では、SharePoint Online および OneDrive for Business 内のファイル アクティビティとページ アクティビティについて説明します。

|**フレンドリ名**|**操作名**|**説明**|
|:-----|:-----|:-----|
|ファイルへのアクセス|FileAccessed|ユーザーまたはシステム アカウントがファイルにアクセスします。|
|(なし)|FileAccessedExtended|これは、"ファイルへのアクセス" (FileAccessed) アクティビティに関連します。 同じユーザーが長時間 (最大 3 時間) にわたって、ファイルに継続的にアクセスすると、FileAccessedExtended イベントがログに記録されます。 <br/><br/> FileAccessedExtended イベントをログに記録する目的は、ファイルが継続的にアクセスされたときにログに記録される FileAccessed イベントの数を減らすことにあります。 これにより、本質的に同じユーザーのアクティビティであるファイル アクセスに対する無意味な複数の FileAccessed レコードが減り、初期の (より重要な) FileAccessed イベントに注目できます。|
|コンプライアンス ポリシー ラベルが変更されました|ComplianceSettingChanged|保持ラベルがドキュメントに適用またはドキュメントから削除されました。 このイベントは、保持ラベルが手動または自動でメッセージに適用されたときにトリガーされます。|
|レコードのステータスがロックに変更されました|LockRecord|ドキュメントをレコードとして分類する保持ラベルのレコード ステータスがロックされました。 これは、ドキュメントを変更したり削除したりできないことを意味します。 ドキュメントのレコード ステータスを変更できるのは、共同作成者以上のアクセス許可がサイトで割り当てられているユーザーだけです。|
|レコード ステータスが、ロック解除に変更されました|UnlockRecord|ドキュメントをレコードとして分類する保持ラベルのレコード ステータスのロックが解除されました。 これは、ドキュメントを変更したり削除したりできることを意味します。 ドキュメントのレコード ステータスを変更できるのは、共同作成者以上のアクセス許可がサイトで割り当てられているユーザーだけです。|
|ファイルのチェックイン|FileCheckedIn|ユーザーがドキュメント ライブラリからチェックアウトしたドキュメントをチェックインしました。|
|ファイルのチェックアウト|FileCheckedOut|User checks out a document located in a document library. Users can check out and make changes to documents that have been shared with them.|
|ファイルのコピー|FileCopied|User copies a document from a site. The copied file can be saved to another folder on the site.|
|ファイルの削除|FileDeleted|ユーザーがサイトからドキュメントを削除しました。|
|ごみ箱からのファイルの削除|FileDeletedFirstStageRecycleBin|ユーザーがサイトのごみ箱からファイルを削除しました。|
|第 2 段階のごみ箱からのファイルの削除|FileDeletedSecondStageRecycleBin|ユーザーがサイトの第 2 段階のごみ箱からファイルを削除しました。|
|削除されたレコードのコンプライアンス ポリシー ラベル|ComplianceRecordDelete|レコードとして分類されたドキュメントが削除されました。 ドキュメントがレコードとしてみなされるのは、ドキュメントをレコードとして分類する保持ラベルがドキュメントに適用されている場合です。|
|検出されたドキュメントの秘密度の不一致|DocumentSensitivityMismatchDetected|ユーザーが、機密ラベルで保護されているサイトにドキュメントをアップロードし、そのドキュメントの機密ラベルが、サイトに適用されている機密ラベルよりも優先度が高くなっています。 たとえば、「社外秘」というラベルの付いたドキュメントが、「一般」というラベルの付いたサイトにアップロードされている場合です。 <br/><br/> ドキュメントの機密ラベルが、サイトに適用されている機密ラベルよりも優先度が低い場合、このイベントは発生しません。 たとえば、「一般」というラベルの付いたドキュメントが、「社外秘」というラベルの付いたサイトにアップロードされている場合です。 機密ラベルの優先度の詳細については、「[ラベルの優先度 (順序の問題)](sensitivity-labels.md#label-priority-order-matters)」を参照してください。|
|ファイルでのマルウェアの検出|FileMalwareDetected|SharePoint ウイルス対策エンジンにより、ファイル内でマルウェアが検出されました。|
|ファイル チェックアウトの破棄|FileCheckOutDiscarded|User discards (or undos) a checked out file. That means any changes they made to the file when it was checked out are discarded, and not saved to the version of the document in the document library.|
|ファイルのダウンロード|FileDownloaded|ユーザーがサイトからドキュメントをダウンロードしました。|
|ファイルの変更|FileModified|ユーザーまたはシステム アカウントがサイトにあるドキュメントのコンテンツまたはプロパティを変更します。|
|(なし)|FileModifiedExtended|これは、"ファイルの変更" (FileModified) アクティビティに関連しています。 同じユーザーが長時間 (最大 3 時間) にわたって、ファイルの変更を継続的に行うと、FileModifiedExtended イベントがログに記録されます。 <br/><br/> FileModifiedExtended イベントをログに記録する目的は、ファイルの変更が継続的に行われたときにログに記録される FileModified イベントの数を減らすことにあります。 これにより、本質的に同じユーザーのアクティビティであるファイル変更に対する無意味な複数の FileModified レコードを減り、初期 (のより重要な) FileModified イベントに注目できます。|
|ファイルの移動|FileMoved|ユーザーがドキュメントをサイトの現在の場所から新しい場所に移動しました。|
|(なし)|FilePreviewed|ユーザーが SharePoint または OneDrive for Business サイトにあるファイルをプレビューします。 通常、これらのイベントは、イメージ ギャラリーの表示などの 1 つのアクティビティに基づいて、大きいボリュームで発生します。|
|実行された検索クエリ|SearchQueryPerformed|ユーザーまたはシステム アカウントが SharePoint または OneDrive for Business で検索を実行します。 サービス アカウントにより検索クエリが実行される一般的なシナリオとして、電子開示情報の保留またはアイテム保持ポリシーがサイトおよび OneDrive アカウントに適用される場合や、保持ラベルまたは機密ラベルがサイト コンテンツに自動適用される場合があります。|
|リサイクルされたファイルのすべてのマイナー バージョン|FileVersionsAllMinorsRecycled|User deletes all minor versions from the version history of a file. The deleted versions are moved to the site's recycle bin.|
|ファイルのすべてのバージョンのリサイクル|FileVersionsAllRecycled|User deletes all versions from the version history of a file. The deleted versions are moved to the site's recycle bin.|
|ファイルのバージョンのリサイクル|FileVersionRecycled|User deletes a version from the version history of a file. The deleted version is moved to the site's recycle bin.|
|ファイルの名前変更|FileRenamed|ユーザーがサイトのドキュメントの名前を変更しました。|
|ファイルの復元|FileRestored|ユーザーがサイトのごみ箱からドキュメントを復元しました。|
|ファイルのアップロード|FileUploaded|ユーザーがサイトのフォルダーにドキュメントをアップロードしました。|
|ページの表示|PageViewed|User views a page on a site. This doesn't include using a Web browser to view files located in a document library.|
|(なし)|PageViewedExtended|これは、"ページの表示" (PageViewed) アクティビティに関連しています。 同じユーザーが長時間 (最大 3 時間) にわたって、継続的に Web ページを表示すると、PageViewedExtended イベントがログに記録されます。 <br/><br/> PageViewedExtended イベントをログに記録する目的は、ページが継続的に表示されたときにログに記録される PageViewed イベントの数を減らすことにあります。 これにより、本質的に同じユーザーのアクティビティであるページ表示に対する無意味な複数の PageViewed レコードが減り、初期 (のより重要な) PageViewed イベントに注目できます。|
|クライアントが表示をシグナル|ClientViewSignaled|ユーザーのクライアント (Web サイトやモバイル アプリなど) が、示されるページをユーザーが表示したことをシグナルしました。 多くの場合、ページでの PagePrefetched イベントに続いてこのアクティビティがログに記録されます。 <br/><br/>**注**: ClientViewSignaled イベントはサーバーではなくクライアントによりシグナルされるため、イベントがサーバーによってログに記録されず、監査ログに表示されない場合があります。 また、監査レコードの情報の信頼性が低い可能性もあります。 ただし、ユーザーの ID はシグナルの作成に使用されたトークンによって検証されるため、対応する監査レコードに記載されているユーザーの ID は正確です。 |
|(なし)|PagePrefetched|示されるページにユーザーがアクセスした際のパフォーマンスを上げるため、ユーザーのクライアント (Web サイトやモバイル アプリなど) がそのページを要求しました。 このイベントは、ページの内容がユーザーのクライアントに配信されたことを示すため、ログに記録されます。 このイベントは、ユーザーがページに移動したことをはっきりと示します。 <br/><br/> (ユーザーの要求に従って) ページのコンテンツがクライアントによってレンダリングされると、ClientViewSignaled イベントが生成されます。 プレフェッチの指摘はすべてのクライアントでサポートされているわけではないため、プレフェッチされた一部のアクティビティは PageViewed イベントとしてログ記録される可能性があります。|
||||

#### <a name="the-appsharepoint-user-in-audit-records"></a>監査レコード内の app\@sharepoint ユーザー

一部のファイルアクティビティ (およびその他の SharePoint 関連のアクティビティ) の監査レコードでは、([ユーザー] および [UserId] フィールドで識別された) アクティビティを実行したユーザーが app@sharepoint であることがわかります。 これは、アクティビティを実行した「ユーザー」がアプリケーションだったことを示します。 この場合、アプリケーションには、ユーザー、管理者、またはサービスの代理として、組織全体のアクション (SharePoint サイトまたは OneDrive アカウント検索など) を実行するためのアクセス許可が SharePoint に与えられています。 アプリケーションに対するアクセス許可を与えるこのプロセスは、*SharePoint アプリ専用*アクセスと呼ばれます。 これは、アクションを実行するために SharePoint に提示された認証が、ユーザーの代わりに、アプリケーションによって処理されたことを示します。 そのため、app@sharepoint ユーザーが特定の監査レコードで識別されます。 詳細については、「[SharePoint アプリ専用のアクセスを許可する](https://docs.microsoft.com/sharepoint/dev/solution-guidance/security-apponly-azureacs)」を参照してください。

たとえば、多くの場合、app@sharepoint は、"Performed search query" および "Accessed file" のイベントのユーザーとして識別されます。 これは、組織で SharePoint アプリ専用アクセスを持つアプリケーションのみが検索クエリを実行し、アイテム保持ポリシーをサイトおよび OneDrive アカウントに適用するときにファイルにアクセスするためです。

ここでは、アクティビティを実行したユーザーとして監査レコード内で app@sharepoint が識別される可能性のある他のいくつかのシナリオを次に示します。

- Microsoft 365 グループ。 ユーザーまたは管理者が新しいグループを作成すると、サイト コレクションの作成、リストの更新、および SharePoint グループへのメンバーの追加のために監査レコードが生成されます。 これらのタスクは、グループを作成したユーザーの代わりにアプリケーションで実行されます。

- Microsoft Teams。 Microsoft 365 グループと同様に、サイト コレクションの作成、リストの更新、およびチームの作成時に SharePoint グループにメンバーを追加するための監査レコードが生成されます。

- コンプライアンス機能。 管理者が、保持ポリシー、電子情報開示の保持、機密ラベルの自動適用などのコンプライアンス機能を実装する場合。

これらのシナリオおよび他のシナリオでは、指定したユーザーとして app@sharepoint を使用した複数の監査レコードが、非常に短い時間枠内、多くの場合数秒以内に作成されています。 これは、ユーザーが開始した同じタスクによってトリガーされた可能性も示しています。 監査レコード内の ApplicationDisplayName および EventData フィールドを確認することにより、イベントをトリガーしたシナリオまたはアプリケーションを特定できる場合があります。

### <a name="folder-activities"></a>フォルダー アクティビティ

次の表では、SharePoint Online および OneDrive for Business 内のフォルダー アクティビティについて説明します。 前に説明したように、一部の SharePoint アクティビティの監査レコードには、アクションを開始したユーザーまたは管理者に代わって app@sharepoint ユーザーがアクティビティを実行したことが示されます。 詳細については、監査レコード内の[ app\@sharepoint ユーザーを参照してください](#the-appsharepoint-user-in-audit-records)。

|**フレンドリ名**|**操作名**|**説明**|
|:-----|:-----|:-----|
|フォルダーのコピー|FolderCopied|ユーザーがフォルダーをサイトから SharePoint または OneDrive for Business の別の場所にコピーしました。|
|フォルダーの作成|FolderCreated|ユーザーがサイトにフォルダーを作成しました。|
|フォルダーの削除|FolderDeleted|ユーザーがサイトからフォルダーを削除しました。|
|ごみ箱からのフォルダーの削除|FolderDeletedFirstStageRecycleBin|ユーザーがサイトのごみ箱からフォルダーを削除しました。|
|第 2 段階のごみ箱からのフォルダーの削除|FolderDeletedSecondStageRecycleBin|ユーザーがサイトの第 2 段階のごみ箱からフォルダーを削除しました。|
|フォルダーの変更|FolderModified|User modifies a folder on a site. This includes changing the folder metadata, such as changing tags and properties.|
|フォルダーの移動|FolderMoved|ユーザーがフォルダーをサイトの別の場所に移動しました。|
|フォルダーの名前変更|FolderRenamed|ユーザーがサイトのフォルダーの名前を変更しました。|
|フォルダーの復元|FolderRestored|ユーザーがサイトのごみ箱から削除されたフォルダーを復元しました。|
||||

### <a name="sharepoint-list-activities"></a>SharePoint リスト アクティビティ

次の表では、ユーザーが SharePoint Online のリストとリストアイテムを操作する際に関連するアクティビティを説明します。 前に説明したように、一部の SharePoint アクティビティの監査レコードには、アクションを開始したユーザーまたは管理者に代わって app@sharepoint ユーザーがアクティビティを実行したことが示されます。 詳細については、監査レコード内の[ app\@sharepoint ユーザーを参照してください](#the-appsharepoint-user-in-audit-records)。

|**フレンドリ名**|**操作名**|**説明**|
|:-----|:-----|:-----|
|リストの作成|ListCreated|ユーザーが SharePoint リストを作成しました。|
|リスト列の作成|ListColumnCreated|ユーザーが SharePoint リスト列を作成しました。 リスト列は、1 つまたは複数の SharePoint リストに関連付けられている列です。|
|リスト コンテンツ タイプの作成|ListContentTypeCreated|ユーザーがリスト コンテンツ タイプを作成しました。 リスト コンテンツ タイプは、1 つまたは複数の SharePoint リストに関連付けられているコンテンツ タイプです。|
|リスト アイテムの作成|ListItemCreated|ユーザーが既存の SharePoint リストにアイテムを作成しました。|
|サイト列の作成|SiteColumnCreated|ユーザーが SharePoint サイト列を作成しました。 サイト列とは、リストに関連付けられていない列のことです。 サイト列は、特定の Web のすべてのリストで使用できるメタデータ構造でもあります。|
|サイト コンテンツ タイプの作成|サイトの ContentType の作成|ユーザーがサイト コンテンツ タイプを作成しました。 サイト コンテンツ タイプは、親サイトに関連付けられているコンテンツ タイプです。|
|リストの削除|ListDeleted|ユーザーが SharePoint リストを削除しました。|
|リスト列の削除|削除されたリスト列|ユーザーが SharePoint リスト列を削除しました。|
|リスト コンテンツ タイプの削除|ListContentTypeDeleted|ユーザーがリスト コンテンツ タイプを削除しました。|
|リスト アイテムの削除|削除されたリスト アイテム|ユーザーが SharePoint リスト アイテムを削除しました。|
|サイト列の削除|SiteColumnDeleted|ユーザーが SharePoint サイト列を削除しました。|
|サイト コンテンツ タイプの削除|SiteContentTypeDeleted|ユーザーがサイト コンテンツ タイプを削除しました。|
|リスト アイテムのリサイクル|ListItemRecycled|ユーザーが SharePoint リスト アイテムをごみ箱に移動しました。|
|リストの復元|ListRestored|ユーザーが SharePoint リストをごみ箱から復元しました。|
|リスト アイテムの復元|ListItemRestored|ユーザーが SharePoint リスト アイテムをごみ箱から復元しました。|
|リストの更新|ListUpdated|ユーザーが 1 つ以上のプロパティを変更して SharePoint リストを更新しました。|
|リスト列の更新|ListColumnUpdated|ユーザーが 1 つ以上のプロパティを変更して SharePoint リスト列を更新しました。|
|リスト コンテンツ タイプの更新|ListContentTypeUpdated|ユーザーが 1 つ以上のプロパティを変更してリスト コンテンツ タイプを更新しました。|
|リスト アイテムの更新|ListItemUpdated|ユーザーが 1 つ以上のプロパティを変更して SharePoint リスト アイテムを更新しました。|
|サイト列の更新|SiteColumnUpdated|ユーザーが 1 つ以上のプロパティを変更して SharePoint サイト列を更新しました。|
|サイト コンテンツ タイプの更新|SiteContentTypeUpdated|ユーザーが 1 つ以上のプロパティを変更してサイト コンテンツ タイプを更新しました。|
||||

### <a name="sharing-and-access-request-activities"></a>共有アクティビティとアクセス要求アクティビティ

次の表では、SharePoint Online および OneDrive for Business でのユーザー共有とアクセス要求アクティビティを説明します。 共有イベントの場合、[**結果**] の [**詳細**] 列で、アイテムを共有したユーザーまたはグループの名前と、そのユーザーまたはグループが組織のメンバーかゲストかが識別されます。 詳細については、「[監査ログで共有監査を使用する](use-sharing-auditing.md)」を参照してください。

> [!NOTE]
> Users can be either  *members*  or  *guests*  based on the UserType property of the user object. A member is usually an employee, and a guest is usually a collaborator outside of your organization. When a user accepts a sharing invitation (and isn't already part of your organization), a guest account is created for them in your organization's directory. Once the guest user has an account in your directory, resources may be shared directly with them (without requiring an invitation).

|**フレンドリ名**|**操作名**|**説明**|
|:-----|:-----|:-----|
|サイト コレクションへのアクセス許可レベルの追加|PermissionLevelAdded|サイト コレクションにアクセス許可レベルが追加されました。|
|アクセス要求の承諾|AccessRequestAccepted|サイト、フォルダー、またはドキュメントに対するアクセス要求が承諾されて、要求したユーザーがアクセスを許可されました。|
|共有への招待の承諾|SharingInvitationAccepted|User (member or guest) accepted a sharing invitation and was granted access to a resource. This event includes information about the user who was invited and the email address that was used to accept the invitation (they could be different). This activity is often accompanied by a second event that describes how the user was granted access to the resource, for example, adding the user to a group that has access to the resource.|
|共有の招待がブロックされました|SharingInvitationBlocked|A sharing invitation sent by a user in your organization is blocked because of an external sharing policy that either allows or denies external sharing based on the domain of the target user. In this case, the sharing invitation was blocked because: <br/> ターゲット ユーザーのドメインが、許可されたドメインの一覧に含まれていない。 <br/> または <br/> ターゲット ユーザーのドメインが、ブロックするドメインの一覧に含まれている。 <br/> ドメインに基づく外部共有の許可またはブロックの詳細については、「[SharePoint Online and OneDrive for Business での制限付きドメイン共有](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)」を参照してください。|
|アクセス要求の作成|AccessRequestCreated|アクセス許可がないサイト、フォルダー、またはドキュメントに対するアクセスをユーザーが要求しました。|
|会社の共有可能なリンクの作成|CompanyLinkCreated|User created a company-wide link to a resource. company-wide links can only be used by members in your organization. They can't be used by guests.|
|匿名リンクの作成|AnonymousLinkCreated|User created an anonymous link to a resource. Anyone with this link can access the resource without having to be authenticated.|
|セキュリティで保護されたリンクの作成|SecureLinkCreated|セキュリティで保護された、このアイテムへの共有リンクが作成されました。|
|共有への招待の作成|SharingInvitationCreated|ユーザーが、組織のディレクトリ内に含まれていないユーザーと SharePoint Online または OneDrive for Business のリソースを共有しました。|
|セキュリティで保護されたリンクの削除|SecureLinkDeleted|セキュリティで保護されたリンクが削除されました。|
|アクセス要求の拒否|AccessRequestDenied|サイト、フォルダー、またはドキュメントに対するアクセスが拒否されました。|
|会社の共有可能なリンクが削除されました|CompanyLinkRemoved|User removed a company-wide link to a resource. The link can no longer be used to access the resource.|
|匿名リンクの削除|AnonymousLinkRemoved|User removed an anonymous link to a resource. The link can no longer be used to access the resource.|
|ファイル、フォルダー、サイトが共有されました|SharingSet|ユーザー (メンバーまたはゲスト) が、組織のディレクトリ内のユーザーと SharePoint または OneDrive for Business のファイル、フォルダー、またはサイトを共有しました。 このアクティビティの [**詳細**] 列の値で、リソースを共有したユーザー名と、そのユーザーがメンバーかゲストかが識別されます。 <br/><br/> 多くの場合、このアクティビティには、リソースに対してどのようなアクセス権がユーザーに付与されたか、という 2 つ目のイベントが伴います。 たとえば、リソースへのアクセス権を持つグループへのユーザーの追加などです。|
|アクセス要求の更新|AccessRequestUpdated|アイテムに対するアクセス要求が更新されました。|
|匿名リンクの更新|AnonymousLinkUpdated|User updated an anonymous link to a resource. The updated field is included in the EventData property when you export the search results.|
|共有への招待の更新|SharingInvitationUpdated|外部共有への招待が更新されました。|
|匿名リンクの使用|AnonymousLinkUsed|An anonymous user accessed a resource by using an anonymous link. The user's identity might be unknown, but you can get other details such as the user's IP address.|
|ファイル、フォルダー、またはサイトの共有解除|SharingRevoked|ユーザー (メンバーまたはゲスト) が、以前別のユーザーと共有していたファイル、フォルダー、またはサイトの共有を解除しました。|
|会社の共有可能なリンクの使用|CompanyLinkUsed|ユーザーが全社的なリンクを使用してリソースにアクセスしました。|
|セキュリティで保護されたリンクの使用|SecureLinkUsed|ユーザーが、セキュリティで保護されたリンクを使用しました。|
|セキュリティで保護されたリンクへのユーザーの追加|AddedToSecureLink|ユーザーが、セキュリティで保護された共有リンクを使用できるエンティティの一覧に追加されました。|
|セキュリティで保護されたリンクからのユーザーの削除|RemovedFromSecureLink|ユーザーが、セキュリティで保護された共有リンクを使用できるエンティティの一覧から削除されました。|
|共有への招待の取り消し|SharingInvitationRevoked|ユーザーが、リソースの共有への招待を取り消しました。|
||||

### <a name="synchronization-activities"></a>同期アクティビティ

次の表では、SharePoint Online および OneDrive for Business 内のファイル同期アクティビティを一覧表示します。

|**フレンドリ名**|**操作名**|**説明**|
|:-----|:-----|:-----|
|コンピューターに対するファイル同期の許可|ManagedSyncClientAllowed|ユーザーがサイトとの同期関係を正常に確立しました。 ユーザーのコンピューターが、組織内のドキュメント ライブラリにアクセスできるドメインのリスト (*宛先セーフ リスト*と呼ばれる) に追加されているドメインのメンバーであるため、同期関係は成功しました。 <br/><br/> この機能の詳細については、「[Windows PowerShell コマンドレットを使用して宛先セーフ リスト上のドメインに対して OneDrive 同期を有効にする](https://go.microsoft.com/fwlink/p/?LinkID=534609)」を参照してください。|
|コンピューターに対するファイル同期のブロック|UnmanagedSyncClientBlocked|User tries to establish a sync relationship with a site from a computer that isn't a member of your organization's domain or is a member of a domain that hasn't been added to the list of domains (called the  *safe recipients list)*  that can access document libraries in your organization. The sync relationship is not allowed, and the user's computer is blocked from syncing, downloading, or uploading files on a document library. <br/><br/> この機能については、「[Windows PowerShell コマンドレットを使用して宛先セーフ リスト上のドメインに対して OneDrive 同期を有効にする](https://go.microsoft.com/fwlink/p/?LinkID=534609)」を参照してください。|
|コンピューターへのファイルのダウンロード|FileSyncDownloadedFull|ユーザーが同期関係を確立して、ドキュメント ライブラリからコンピューターに初めてファイルを正常にダウンロードしました。|
|コンピューターへのファイル変更のダウンロード|FileSyncDownloadedPartial|User successfully downloads any changes to files from a document library. This activity indicates that any changes that were made to files in the document library were downloaded to the user's computer. Only changes were downloaded because the document library was previously downloaded by the user (as indicated by the **Downloaded files to computer** activity).|
|ファイルがドキュメント ライブラリにアップロードされました|FileSyncUploadedFull|ユーザーが同期関係を確立して、コンピューターからドキュメント ライブラリに初めてファイルを正常にアップロードしました。|
|ドキュメント ライブラリへのファイル変更のアップロード|FileSyncUploadedPartial|ユーザーはドキュメント ライブラリ上のファイルの変更を正常にアップロードしました。 このイベントは、ドキュメント ライブラリからダウンロードしたローカル バージョンのファイルに加えた変更内容が、ドキュメント ライブラリに正常にアップロードされたことを示します。 それらのファイルは、(「**ドキュメント ライブラリへのファイルのアップロード**」 アクティビティによって示されるように) 以前にユーザーによってアップロードされているため、変更内容のみがアップロードされます。|
||||

### <a name="site-permissions-activities"></a>サイトの権限のアクティビティ

次の表では、SharePoint でのアクセス許可の割り当てとグループの使用によるサイトへのアクセス権の付与に関連するイベントを一覧表示します。 前に説明したように、一部の SharePoint アクティビティの監査レコードには、アクションを開始したユーザーまたは管理者に代わって app@sharepoint ユーザーがアクティビティを実行したことが示されます。 詳細については、監査レコード内の[ app\@sharepoint ユーザーを参照してください](#the-appsharepoint-user-in-audit-records)。

|**フレンドリ名**|**操作名**|**説明**|
|:-----|:-----|:-----|
|サイト コレクション管理者の追加|SiteCollectionAdminAdded|サイト コレクション管理者または所有者が、サイトのサイト コレクション管理者としてユーザーを追加します。 サイト コレクション管理者には、サイト コレクションとすべてのサブサイトのフル コントロール権限があります。 このアクティビティは、SharePoint 管理センターでユーザー プロファイルを編集するか [Microsoft 365 管理センターを使用](https://docs.microsoft.com/office365/admin/add-users/get-access-to-and-back-up-a-former-user-s-data)することにより、管理者がユーザーの OneDrive アカウントへのアクセス権限を自分自身に付与する際にも記録されます。|
|SharePoint グループへのユーザーまたはグループの追加|AddedToGroup|User added a member or guest to a SharePoint group. This might have been an intentional action or the result of another activity, such as a sharing event.|
|アクセス許可レベルの継承の停止|PermissionLevelsInheritanceBroken|アイテムが変更されたので、アクセス許可レベルが親から継承されなくなりました。|
|共有の継承の停止|SharingInheritanceBroken|アイテムが変更されたので、共有アクセス許可が親から継承されなくなりました。|
|グループの作成|GroupAdded|Site administrator or owner creates a group for a site, or performs a task that results in a group being created. For example, the first time a user creates a link to share a file, a system group is added to the user's OneDrive for Business site. This event can also be a result of a user creating a link with edit permissions to a shared file.|
|グループの削除|GroupRemoved|ユーザーがサイトからグループを削除しました。|
|アクセス要求の設定の変更|WebRequestAccessModified|サイトでアクセス要求の設定が変更されました。|
|[メンバーが共有可能] 設定の変更|WebMembersCanShareModified|サイトで [**メンバーが共有可能**] 設定が変更されました。|
|サイト コレクションのアクセス許可レベルの変更|PermissionLevelModified|サイト コレクションでアクセス許可レベルが変更されました。|
|サイト アクセス許可の変更|SitePermissionsModified|サイト管理者または所有者 (またはシステム アカウント) がサイトのグループに割り当てられたアクセス許可レベルを変更しました。 すべてのアクセス許可がグループから削除された場合も、このアクティビティが記録されます。 <br/><br/> **注**: この操作は、SharePoint Online で廃止されました。 関連するイベントを見つけるには、**サイト コレクション管理者の追加**、**SharePoint グループへのユーザーまたはグループの追加**、**ユーザーに対するグループ作成の許可**、**グループの作成**、**グループの削除**などのその他のアクセス許可関連のアイテムを検索することができます。|
|サイト コレクションからのアクセス許可レベルの削除|PermissionLevelRemoved|サイト コレクションからアクセス許可レベルが削除されました。|
|サイト コレクション管理者の削除|SiteCollectionAdminRemoved|サイト コレクション管理者または所有者が、サイトのサイト コレクション管理者としてユーザーを削除します。 このアクティビティは、(SharePoint 管理センターでユーザー プロファイルを編集することにより) 管理者がユーザーの OneDrive アカウントのサイト コレクション管理者のリストから自分自身を削除する際にも記録されます。  監査ログの検索結果にこのアクティビティを返すには、すべてのアクティビティを検索する必要があります。|
|SharePoint グループからのユーザーまたはグループの削除|RemovedFromGroup|User removed a member or guest from a SharePoint group. This might have been an intentional action or the result of another activity, such as an unsharing event.|
|サイト管理者アクセス許可の要求|SiteAdminChangeRequest|User requests to be added as a site collection administrator for a site collection. Site collection administrators have full control permissions for the site collection and all subsites.|
|共有の継承の復元|SharingInheritanceReset|変更が加えられたので、共有アクセス許可が親から継承されなくなりました。|
|グループの更新|GroupUpdated|Site administrator or owner changes the settings of a group for a site. This can include changing the group's name, who can view or edit the group membership, and how membership requests are handled.|
||||

### <a name="site-administration-activities"></a>サイト管理アクティビティ

次の表では、SharePoint Online 内のサイト管理タスクによって発生するイベントを一覧表示します。 前に説明したように、一部の SharePoint アクティビティの監査レコードには、アクションを開始したユーザーまたは管理者に代わって app@sharepoint ユーザーがアクティビティを実行したことが示されます。 詳細については、監査レコード内の[ app\@sharepoint ユーザーを参照してください](#the-appsharepoint-user-in-audit-records)。

|**フレンドリ名**|**操作名**|**説明**|
|:-----|:-----|:-----|
|許可されるデータの場所の追加|AllowedDataLocationAdded|SharePoint 管理者またはグローバル管理者が、複数地域環境で許可されるデータの場所を追加しました。|
|適用除外ユーザー エージェントの追加|ExemptUserAgentSet|SharePoint 管理者またはグローバル管理者が、SharePoint 管理センターで適用除外ユーザー エージェントの一覧にユーザー エージェントを追加しました。|
|地理的位置の管理者の追加|GeoAdminAdded|SharePoint 管理者またはグローバル管理者が、地理的位置の管理者としてユーザーを追加しました。|
|ユーザーに対するグループ作成の許可|AllowGroupCreationSet|サイトの管理者または所有者がアクセス許可レベルをサイトに追加しました。そのアクセス許可が割り当てられているユーザーは、そのサイトのグループを作成することが許可されます。|
|サイトの地域の移動の取り消し|SiteGeoMoveCancelled|SharePoint またはグローバル管理者が SharePoint または OneDrive サイトの地域の移動を正常にキャンセルしました。 複数地域機能を使用すると、組織が複数の Microsoft データセンターの場所にまたがることができます。これは「地域」と呼ばれます。 詳細については、「[OneDrive および SharePoint Online の複数地域機能](https://go.microsoft.com/fwlink/?linkid=860840)」を参照してください。|
|共有ポリシーの変更|SharingPolicyChanged|SharePoint またはグローバル管理者が、Microsoft 365 管理ポータル、SharePoint 管理ポータル、または SharePoint Online 管理シェルを使用して SharePoint 共有ポリシーを変更しました。 組織の共有ポリシーの設定が変更されると、ログに記録されます。 変更されたポリシーは、イベント レコードの詳細なプロパティの **ModifiedProperties** フィールドで識別されます。|
|デバイス アクセス ポリシーの変更|DeviceAccessPolicyChanged|SharePoint またはグローバル管理者が、組織の非管理対象デバイス ポリシーを変更しました。 このポリシーは、組織に参加していないデバイスからの SharePoint、OneDrive、および Microsoft 365 へのアクセスを制御します。 このポリシーを構成するには、Enterprise Mobility + Security サブスクリプションが必要です。 詳細については、「[非管理対象デバイスからのアクセスを制御する](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)」を参照してください。|
|適用除外ユーザー エージェントの変更|CustomizeExemptUsers|A SharePoint or global administrator customized the list of exempt user agents in the SharePoint admin center. You can specify which user agents to exempt from receiving an entire web page to index. This means when a user agent you've specified as exempt encounters an InfoPath form, the form will be returned as an XML file, instead of an entire web page. This makes indexing InfoPath forms faster.|
|ネットワーク アクセス ポリシーの変更|NetworkAccessPolicyChanged|A SharePoint or global administrator changed the location-based access policy (also called a trusted network boundary) in the SharePoint admin center or by using SharePoint Online PowerShell. This type of policy controls who can access SharePoint and OneDrive resources in your organization based on authorized IP address ranges that you specify. For more information, see [Control access to SharePoint Online and OneDrive data based on network location](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location).|
|サイトの地域の移動の完了|SiteGeoMoveCompleted|組織のグローバル管理者がスケジュールしたサイトの地域の移動が正常に完了しました。 複数地域機能を使用すると、組織が複数の Microsoft データセンターの場所にまたがることができます。これは「地域」と呼ばれます。 詳細については、「[OneDrive の複数地域機能および Office 365 の SharePoint Online](https://go.microsoft.com/fwlink/?linkid=860840)」を参照してください。|
|送信接続の作成|SendToConnectionAdded|A SharePoint or global administrator creates a new Send To connection on the Records management page in the SharePoint admin center. A Send To connection specifies settings for a document repository or a records center. When you create a Send To connection, a Content Organizer can submit documents to the specified location.|
|サイト コレクションの作成|SiteCollectionCreated|SharePoint 管理者または全体管理者が、SharePoint Online 組織でサイト コレクションを作成したか、ユーザーが OneDrive for Business サイトをプロビジョニングしました。|
|孤立したハブ サイトの削除|HubSiteOrphanHubDeleted|SharePoint 管理者またはグローバル管理者が、孤立したハブサイトを削除しました。これは、それに関連付けられているサイトがないハブサイトです。 孤立したハブは、元のハブサイトの削除が原因である可能性が大きいです。|
|送信接続の削除|SendToConnectionRemoved|SharePoint 管理者または全体管理者が、SharePoint 管理センターの [レコード管理] ページで、送信接続を削除しました。|
|サイトの削除|SiteDeleted|サイト管理者がサイトを削除しました。|
|ドキュメント プレビューの有効化|PreviewModeEnabledSet|サイト管理者がサイトのドキュメントのプレビューを有効にしました。|
|レガシー ワークフローの有効化|LegacyWorkflowEnabledSet|Site administrator or owner adds the SharePoint 2013 Workflow Task content type to the site. Global administrators can also enable work flows for the entire organization in the SharePoint admin center.|
|オンデマンドでの Office の有効化|OfficeOnDemandSet|サイト管理者は、Office オンデマンドを有効にします。これによりユーザーは、Office デスクトップ アプリケーションの最新バージョンにアクセスできます。 Office オンデマンドは SharePoint 管理センターで有効にされ、インストール済みのすべての Office アプリケーションを含む Microsoft 365 サブスクリプションを必要とします。|
|人の検索の検索先の有効化|PeopleResultsScopeSet|サイト管理者が、サイトの人の検索の検索先を作成しました。|
|RSS フィードの有効化|NewsFeedEnabledSet|Site administrator or owner enables RSS feeds for a site. Global administrators can enable RSS feeds for the entire organization in the SharePoint admin center.|
|サイトのハブサイトへの結合|HubSiteJoined|サイト所有者が、サイトをハブサイトに関連付けました。|
|ハブサイトの登録|HubSiteRegistered|SharePoint またはグローバル管理者がハブ サイトを作成しました。 その結果、サイトがハブ サイトとして登録されます。|
|許可されるデータの場所の削除|AllowedDataLocationDeleted|SharePoint 管理者またはグローバル管理者が、複数地域環境で許可されるデータの場所を削除しました。|
|地理的位置の管理者の削除|GeoAdminDeleted|SharePoint 管理者またはグローバル管理者が、ユーザーの地理的位置の管理者の役割を削除しました。|
|サイトの名前変更|SiteRenamed|サイトの管理者または所有者がサイトの名前を変更しました|
|サイトの地域の移動のスケジュール設定|SiteGeoMoveScheduled|SharePoint またはグローバル管理者が SharePoint または OneDrive サイトの地域の移動を正常にスケジュール設定しました。 複数地域機能を使用すると、組織が複数の Microsoft データセンターの場所にまたがることができます。これは「地域」と呼ばれます。 詳細については、「[OneDrive の複数地域機能および Office 365 の SharePoint Online](https://go.microsoft.com/fwlink/?linkid=860840)」を参照してください。|
|ホスト サイトの設定|HostSiteSet|SharePoint 管理者または全体管理者が、個人用サイトまたは OneDrive for Business サイトをホストするために指定されたサイトを変更しました。|
|地理的位置のストレージ クォータの構成|GeoQuotaAllocated|SharePoint 管理者またはグローバル管理者が、複数地域環境での地理的位置のストレージ クォータを構成しました。|
|サイトのハブサイトへの結合解除|HubSiteUnjoined|サイト所有者が、ハブサイトへのサイトの関連付けを解除しました。|
|ハブサイトの登録解除|HubSiteUnregistered|SharePoint またはグローバル管理者が、ハブサイトとしてのサイトの登録を解除しました。 ハブサイトが解除されると、そのサイトはハブサイトとして機能しなくなります。|
||||

### <a name="exchange-mailbox-activities"></a>Exchange メールボックス アクティビティ

次の表に、メールボックス監査ログに記録される可能性があるアクティビティを示します。 メールボックス所有者、委任されたユーザー、または管理者によって実行されたメールボックス アクティビティは、監査ログに最大 90 日間自動的に記録されます。 管理者は、組織のすべてのユーザーについて、メールボックス監査ログをオフにできます。 この場合、いずれのユーザーのメールボックス操作もログに記録されません。 詳細については、「[メールボックスの監査を管理する](enable-mailbox-auditing.md)」を参照してください。

 メールボックス操作の検索は、Exchange Online PowerShell で [Search-MailboxAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) コマンドレットを使用しても行えます。

|**フレンドリ名**|**操作名**|**説明**|
|:-----|:-----|:-----|
|メールボックス アイテムへのアクセス|MailItemsAccessed|メールボックスでメッセージが読み取りまたはアクセスされました。 このアクティビティの監査レコードは、次の 2 つのうちいずれかの方法でトリガーされます。メール クライアント (Outlook など) でメッセージに対するバインド操作が実行されたとき、またはメール プロトコル (Exchange ActiveSync や IMAP など) によりメール フォルダーのアイテムが同期されたとき。 このアクティビティは、Office 365 または Microsoft 365 E5 ライセンスを持つユーザーのみに記録されます。 このアクティビティの監査レコードの分析は、攻撃されたメール アカウントを調査するときに便利です。 詳細については、「[高度な監査](advanced-audit.md#access-to-crucial-events-for-investigations)」の「調査のための重要なイベントへのアクセス」セクションを参照してください。 |
|代理メールボックス アクセス許可の追加|AddMailboxPermissions|An administrator assigned the FullAccess mailbox permission to a user (known as a delegate) to another person's mailbox. The FullAccess permission allows the delegate to open the other person's mailbox, and read and manage the contents of the mailbox.|
|代理人アクセス許可を持つユーザーが予定表フォルダーに追加または削除されました|UpdateCalendarDelegation|ユーザーが、別のユーザーのメールボックスの予定表に代理人として追加または削除されました。 予定表の委任により、同じ組織の他のユーザーに、メールボックス所有者の予定表を管理する権限が付与されます。|
|フォルダーへのアクセス許可が追加されました|AddFolderPermissions|フォルダーのアクセス許可が追加されました。 フォルダーのアクセス許可では、メールボックス内のフォルダーとそれらのフォルダーに格納されているメッセージにアクセスできる組織内のユーザーを制限します。|
|別のフォルダーへのメッセージのコピー|Copy|メッセージが別のフォルダーにコピーされました。|
|メールボックス アイテムの作成|Create|アイテムが、メールボックスの予定表、連絡先、メモ、またはタスク フォルダーに作成されます。 たとえば、新しい会議出席依頼が作成されます。 メッセージの作成、送信、または受信は監査されません。 また、メールボックス フォルダーの作成も監査されません。|
|Outlook Web App の新しい受信トレイ ルールの作成|New-InboxRule|メールボックスの所有者またはメールボックスにアクセスできる別のユーザーが、Outlook Web App で受信トレイ ルールを作成しました。|
|削除済みアイテム フォルダーからのメッセージの削除|SoftDelete|A message was permanently deleted or deleted from the Deleted Items folder. These items are moved to the Recoverable Items folder. Messages are also moved to the Recoverable Items folder when a user selects it and presses **Shift+Delete**.|
|メッセージをレコードとして分類しました|ApplyRecordLabel|メッセージがレコードとして分類されました。 これは、コンテンツをレコードとして分類する保持ラベルが手動または自動でメッセージに適用されるときに発生します。|
|別のフォルダーへのメッセージの移動|Move|メッセージが別のフォルダーに移動されました。|
|削除済みアイテム フォルダーへのメッセージの移動|MoveToDeletedItems|メッセージが削除され、削除済みアイテム フォルダーに移動されました。|
|フォルダーのアクセス許可の変更|UpdateFolderPermissions|A folder permission was changed. Folder permissions control which users in your organization can access mailbox folders and the messages in the folder.|
|Outlook Web App の受信トレイ ルールが変更されました|Set-InboxRule|メールボックスの所有者またはメールボックスにアクセスできる別のユーザーが、Outlook Web App を使用して受信トレイ ルールを変更しました。|
|メールボックスからのメッセージの消去|HardDelete|メッセージが回復可能なアイテム フォルダーから削除されました (メールボックスから完全に削除されました)。|
|代理メールボックス アクセス許可の削除|Remove-MailboxPermission|An administrator removed the FullAccess permission (that was assigned to a delegate) from a person's mailbox. After the FullAccess permission is removed, the delegate can't open the other person's mailbox or access any content in it.|
|フォルダーからアクセス許可が削除されました|RemoveFolderPermissions|フォルダーのアクセス許可が削除されました。 フォルダーのアクセス許可では、メールボックス内のフォルダーとそれらのフォルダーに格納されているメッセージにアクセスできる組織内のユーザーを制限します。|
|送信者権限を使ったメッセージの送信|SendAs|SendAs アクセス許可を使用してメッセージが送信されました。 つまり、別のユーザーがこのメールボックスの所有者を装ってメッセージを送信したということです。|
|代理送信権限を使ったメッセージの送信|SendOnBehalf|SendOnBehalf アクセス許可を使用してメッセージが送信されました。 つまり、別のユーザーがこのメールボックスの所有者の代理人としてメッセージを送信したということです。 このメッセージは、代わりにメッセージが送信されたユーザーと実際にメッセージを送信したユーザーを受信者に示します。|
|Outlook クライアントの受信トレイ ルールの更新|UpdateInboxRules|メールボックスの所有者またはメールボックスにアクセスできる別のユーザーが、Outlook クライアントで受信トレイ ルールを変更しました。|
|メッセージの更新|Update|メッセージまたはそのプロパティが変更されました。|
|メールボックスへのユーザーのサインイン|MailboxLogin|ユーザーが自分のメールボックスにサインインしました。|
||||

### <a name="sway-activities"></a>Sway アクティビティ

次の表は、Sway のユーザーと管理者のアクティビティ一覧です。 Sway は、ユーザーが対話型の Web ベースのキャンバスでアイデア、ストーリー、プレゼンテーションを収集、書式設定、および共有できる Microsoft 365 のアプリです。 詳細については、「[Sway – 管理のヘルプについてよく寄せられる質問](https://support.office.com/article/446380fa-25bf-47b2-996c-e12cb2f9d075)」を参照してください。

|**フレンドリ名**|**操作名**|**説明**|
|:-----|:-----|:-----|
|Sway の共有レベルの変更|SwayChangeShareLevel|User changes the share level of a Sway. This event captures the user changing the scope of sharing associated with a Sway; for example, public versus inside the organization.|
|Sway の作成|SwayCreate|ユーザーが Sway を作成しました。|
|Sway の削除|SwayDelete|ユーザーが Sway を削除しました。|
|Sway の複製の無効化|SwayDisableDuplication|ユーザーが Sway の複製を無効にしました。|
|Sway の複製|SwayDuplicate|ユーザーが Sway を複製しました。|
|Sway の編集|SwayEdit|ユーザーが Sway を編集しました。|
|Sway の複製の有効化|EnableDuplication|ユーザーは Sway を複製できます。 ユーザーが Sway の複製を有効にする機能は、既定で有効になっています。|
|Sway の共有の取り消し|SwayRevokeShare|User stops sharing a Sway by revoking access to it. Revoking access changes the links associated with a Sway.|
|Sway の共有|SwayShare|User intends to share a Sway. This event captures the user action of clicking a specific share destination within the Sway share menu. The event doesn't indicate whether the user completed the share action.|
|Sway の外部共有の無効化|SwayExternalSharingOff|管理者が Microsoft 365 管理センターを使用して、組織全体に対して Sway の外部共有を無効にしました。|
|Sway の外部共有の有効化|SwayExternalSharingOn|管理者が Microsoft 365 管理センターを使用して、組織全体に対して Sway の外部共有を有効にしました。|
|Sway のサービスの無効化|SwayServiceOff|管理者が Microsoft 365 管理センターを使用して、組織全体に対して Sway を無効にしました。|
|Sway のサービスの有効化|SwayServiceOn|管理者が Microsoft 365 管理センターを使用して、組織全体に対して Sway を有効にしました (Sway サービスは既定で有効になります)。|
|Sway の表示|SwayView|ユーザーが Sway を表示しました。|
||||

### <a name="user-administration-activities"></a>ユーザー管理アクティビティ

次の表では、管理者が Microsoft 365 管理センターまたは Azure 管理ポータルを使用してユーザー アカウントを追加または変更したときに記録されるユーザー管理アクティビティを一覧表示します。

|**アクティビティ**|**操作名**|**説明**|
|:-----|:-----|:-----|
|ユーザーの追加|Add user|ユーザー アカウントが作成されました。|
|ユーザー ライセンスの変更|ユーザー ライセンスを変更します|The license assigned to a user what changed. To see what licenses were changes, see the corresponding **Updated user** activity.|
|ユーザー パスワードが変更されました|Change user password|ユーザーがパスワードを変更します。 ユーザーがパスワードをリセットするには、組織内のすべてのユーザーまたは選択したユーザーに対して、セルフサービスパスワードリセットを有効にする必要があります。 Azure Active Directory でセルフサービスのパスワードリセットアクティビティを追跡することもできます。 詳細情報については、[Azure ADパスワード管理に関するレポート　オプション](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-reporting)をご覧ください。
|ユーザーの削除|Delete user|ユーザー アカウントが削除されました。|
|Reset user password|Reset user password|管理者がユーザーのパスワードを再設定します。|
|ユーザーへパスワードの変更を強制するプロパティの設定|Set force change user password|管理者が、ユーザーが次に Office 365 にサインインしたときにパスワードを強制的に変更させるプロパティを設定しました。|
|ライセンス プロパティの設定|Set license properties|管理者が、ユーザーに割り当てられたライセンスのプロパティを変更しました。|
|ユーザーの更新|ユーザーを更新する|Administrator changes one or more properties of a user account. For a list of the user properties that can be updated, see the "Update user attributes" section in [Azure Active Directory Audit Report Events](https://go.microsoft.com/fwlink/p/?LinkID=616549).|
||||

### <a name="azure-ad-group-administration-activities"></a>Azure AD グループ管理アクティビティ

次の表に、管理者かユーザーが Microsoft 365 グループを作成または変更したとき、あるいは管理者が Microsoft 365 管理センターか Azure 管理ポータルを使用してセキュリティ グループを作成したときに記録されるグループ管理アクティビティを示します。 Office 365 のグループの詳細については、「[Microsoft 365 管理センターでグループを表示、作成、削除する](https://docs.microsoft.com/microsoft-365/admin/create-groups/create-groups)」を参照してください。

|**フレンドリ名**|**操作名**|**説明**|
|:-----|:-----|:-----|
|グループの追加|Add group|グループが作成されました。|
|グループへのメンバーの追加|Add member to group|メンバーがグループに追加されました。|
|グループの削除|Delete group|グループが削除されました。|
|グループからのメンバーの削除|Remove member from group|メンバーがグループから削除されました。|
|グループの更新|Update group|グループのプロパティが変更されました。|
||||

### <a name="application-administration-activities"></a>アプリケーション管理アクティビティ

The following table lists application admin activities that are logged when an admin adds or changes an application that's registered in Azure AD. Any application that relies on Azure AD for authentication must be registered in the directory.

|**フレンドリ名**|**操作名**|**説明**|
|:-----|:-----|:-----|
|委任エントリの追加|Add delegation entry|Azure AD 内のアプリケーションに対して認証アクセス許可が作成または付与されました。|
|サービス プリンシパルの追加|Add service principal|An application was registered in Azure AD. An application is represented by a service principal in the directory.|
|サービス プリンシパルへの資格情報の追加|Add service principal credentials|Credentials were added to a service principal in Azure AD. A service principle represents an application in the directory.|
|委任エントリの削除|Remove delegation entry|Azure AD 内のアプリケーションから認証アクセス許可が削除されました。|
|ディレクトリからのサービス プリンシパルの削除|Remove service principal|An application was deleted/unregistered from Azure AD. An application is represented by a service principal in the directory.|
|サービス プリンシパルからの資格情報の削除|Remove service principal credentials|Credentials were removed from a service principal in Azure AD. A service principle represents an application in the directory.|
|委任エントリの設定|Set delegation entry|Azure AD 内のアプリケーションの認証アクセス許可が更新されました。|
||||

### <a name="role-administration-activities"></a>役割管理アクティビティ

次の表に、管理者が Microsoft 365 管理センターまたは Azure 管理ポータルで管理者の役割を管理したときに記録される Azure AD の役割管理アクティビティを示します。

|**フレンドリ名**|**操作名**|**説明**|
|:-----|:-----|:-----|
|役割へのメンバーの追加|Add role member to role|Microsoft 365 の管理者の役割にユーザーが追加されました。|
|ディレクトリ ロールからのユーザーの削除|Remove role member from role|Microsoft 365 の管理者の役割からユーザーが削除されました。|
|会社の連絡先情報の設定|会社の連絡先情報の設定|組織の会社レベルの連絡先設定が更新されました。 これには、Microsoft 365 によって送信されるサブスクリプション関連のメールのメール アドレスと、サービスに関する技術的な通知が含まれます。|
||||

### <a name="directory-administration-activities"></a>ディレクトリ管理アクティビティ

次の表に、管理者が Microsoft 365 管理センターまたは Azure 管理ポータルで組織を管理したときに記録される Azure AD ディレクトリおよびドメイン関連のアクティビティを示します。

|**フレンドリ名**|**操作名**|**説明**|
|:-----|:-----|:-----|
|会社へのドメインの追加|Add domain to company|組織にドメインが追加されました。|
|ディレクトリへのパートナーの追加|Add partner to company|パートナー (代理管理者) が組織に追加されました。|
|会社からのドメインの削除|Remove domain from company|組織からドメインが削除されました。|
|ディレクトリからのパートナーの削除|Remove partner from company|組織からパートナー (代理管理者) が削除されました。|
|会社情報の設定|会社情報の設定|組織の会社情報が更新されました。 これには、Microsoft 365 によって送信されるサブスクリプション関連のメールのメール アドレスと、Microsoft 365 サービスに関する技術的な通知が含まれます。|
|ドメイン認証の設定|ドメイン認証の設定|組織のドメイン認証設定が変更されました。|
|ドメインのフェデレーション設定の更新|Set federation settings on domain|組織のフェデレーション (外部共有) 設定が変更されました。|
|Set password policy|Set password policy|組織のユーザー パスワードの長さと文字の制約が変更されました。|
|Azure AD Sync の有効化|Set DirSyncEnabled flag on company|Azure AD Sync のディレクトリを有効にするプロパティが設定されました。|
|ドメインの更新|Update domain|組織のドメインの設定が更新されました。|
|ドメインの検証|Verify domain|組織がドメインの所有者であるかどうかが検証されました。|
|メールで確認済みのドメインの検証|Verify email verified domain|メールによる確認を使用して、組織がドメインの所有者であるかどうかが検証されました。|
||||

### <a name="ediscovery-activities"></a>電子情報開示アクティビティ

セキュリティ/コンプライアンス センターで実行された (または対応する PowerShell コマンドレットを使用して実行された) コンテンツ検索と電子情報開示関連のアクティビティは監査ログに記録されます。 これには次のアクティビティが含まれます。

- 電子情報開示ケースの作成と管理

- コンテンツ検索の作成、開始、編集

- コンテンツ検索アクション (検索結果のプレビュー、エクスポート、削除など) の実行

- コンテンツ検索用のアクセス許可フィルターの構成

- 電子情報開示管理者の役割の管理

記録される電子情報開示アクティビティの一覧と詳細な説明については、「[監査ログで電子情報開示アクティビティを検索する](search-for-ediscovery-activities-in-the-audit-log.md)」を参照してください。

> [!NOTE]
> [**アクティビティ**] ドロップダウン リストの [**電子情報開示アクティビティ**] および [**Advanced eDiscovery アクティビティ**] の下に表示されるアクティビティの結果のイベントが、検索結果に表示されるまでに最大 30 分かかります。 逆に、電子情報開示コマンドレットのアクティビティの対応するイベントが検索結果に表示されるまでに最大 24 時間かかります。

### <a name="advanced-ediscovery-activities"></a>Advanced eDiscovery アクティビティ

監査ログで Advanced eDiscovery のアクティビティを検索できます。 これらのアクティビティの説明については、「[監査ログで電子情報開示アクティビティを検索する](search-for-ediscovery-activities-in-the-audit-log.md#advanced-ediscovery-activities)」の「Advanced eDiscovery アクティビティ」セクションを参照してください。

### <a name="power-bi-activities"></a>Power BI アクティビティ

監査ログで Power BI のアクティビティを検索できます。 Power BI アクティビティについては、「[組織内での監査の使用](https://docs.microsoft.com/power-bi/service-admin-auditing#activities-audited-by-power-bi)」の「Power BI の監査対象アクティビティ」セクションを参照してください。

Power BI の監査ログは、既定では有効になっていません。 監査ログ内の Power BI アクティビティを検索するには、Power BI 管理ポータルで監査を有効にする必要があります。 手順については、[Power BI 管理ポータル](https://docs.microsoft.com/power-bi/service-admin-portal#audit-logs)の「監査ログ」セクションをご覧ください。

### <a name="microsoft-workplace-analytics-activities"></a>Microsoft Workplace Analytics アクティビティ

Workplace Analytics は、グループが組織全体でどのように共同作業するかに関する分析情報を提供します。 次の表に、Workplace Analytics で管理者の役割またはアナリストの役割が割り当てられているユーザーが実行するアクティビティを示します。 アナリストの役割が割り当てられたユーザーは、すべてのサービス機能に完全なアクセス権を持ち、製品を使用して分析を行います。 管理者の役割を割り当てられたユーザーは、プライバシー設定とシステム既定を構成でき、Workplace Analytics で組織データを準備、アップロード、および検証できます。 詳細については、「[Workplace Analytics](https://docs.microsoft.com/workplace-analytics/index-orig)」を参照してください。

|**フレンドリ名**|**操作名**|**説明**|
|:-----|:-----|:-----|
|OData リンクのアクセス|AccessedOdataLink|アナリストはクエリの OData リンクにアクセスしました。|
|クエリのキャンセル|CanceledQuery|アナリストはクエリの実行をキャンセルしました。|
|会議の除外の作成|MeetingExclusionCreated|アナリストは会議の除外ルールを作成しました。|
|結果の削除|DeletedResult|アナリストはクエリ結果を削除しました。|
|レポートのダウンロード|DownloadedReport|アナリストはクエリ結果のファイルをダウンロードしました。|
|クエリの実行|ExecutedQuery|アナリストはクエリを実行しました。|
|データ アクセス設定の更新|UpdatedDataAccessSetting|管理者はデータ アクセス設定を更新しました。|
|プライバシー設定の更新|UpdatedPrivacySetting|管理者は、プライバシーの設定 (最小グループ サイズなど) を更新しました。|
|組織データのアップロード|UploadedOrgData|管理者は組織データのファイルをアップロードしました。|
|参照の表示|ViewedExplore|アナリストは、1 つまたは複数の参照ページ タブで視覚エフェクトを表示しました。|
||||

### <a name="microsoft-teams-activities"></a>Microsoft Teams アクティビティ

次の表には、監査ログに記録された Microsoft Teams のユーザー アクティビティおよび管理者アクティビティの一覧が表示されています。 Microsoft Teams は Office 365 のチャット中心のワークスペースです。 これにより、チームの会話、会議、ファイル、およびノートが 1 つの場所に集められます。 詳細およびヘルプ トピックへのリンクについては、以下を参照してください。

- [Microsoft Teams についてよく寄せられる質問 - 管理者向けヘルプ](https://docs.microsoft.com/MicrosoftTeams/teams-overview)

- [Microsoft Teams ヘルプ センター](https://support.office.com/teams)

|**フレンドリ名**|**操作名**|**説明**|
|:-----|:-----|:-----|
|チームへのボットの追加|BotAddedToTeam|ユーザーがチームにボットを追加しました。|
|チャネルの追加|ChannelAdded|ユーザーがチームにチャネルを追加しました。|
|コネクタの追加|ConnectorAdded|ユーザーがチャネルにコネクタを追加しました。|
|追加されたメンバー|MemberAdded|チームの所有者が、チーム、チャネル、またはグループ チャットにメンバーを追加しました。|
|タブの追加|TabAdded|ユーザーがチャネルにタブを追加しました。|
|チャネルの設定の変更|ChannelSettingChanged|次のアクティビティがチーム メンバーにより実行されると、ChannelSettingChanged 操作が記録されます。 これらの各アクティビティについては、変更された設定 (以下のかっこ内) の説明が、監査ログの検索結果の [**項目**] 列に表示されます。 <br/><br/>• チーム チャネルの名前が変更されます (**チャネル名**)。 <br/><br/>• チーム チャネルの説明が変更されます (**チャネルの説明**)。|
|組織の設定の変更|TeamsTenantSettingChanged|TeamsTenantSettingChanged は、全体管理者が Microsoft 365 管理センターを使用して次のアクティビティを実行したときに記録されます。これらのアクティビティは組織全体の Microsoft Teams の設定に影響を及ぼすことに注意してください。 詳細については、「[Microsoft Teams の管理者設定](https://docs.microsoft.com/MicrosoftTeams/enable-features-office-365)」を参照してください。 <br/> これらの各アクティビティについては、変更された設定 (以下のかっこ内) の説明が、監査ログの検索結果の [**項目**] 列に表示されます。 <br/><br/>• 組織に対して Microsoft Teams が有効または無効になります (**Microsoft Teams**)。 <br/><br/>• 組織に対して Microsoft Teams と Skype for Business の相互運用が有効または無効になります (**Skype for Business の相互運用性**)。 <br/><br/>• Microsoft Teams クライアントの組織図ビューを有効または無効にします (組織図ビュー **)。<br/><br/>• チーム メンバーがプライベート会議をスケジュールする機能を有効または無効にします (** プライベート会議のスケジュール **)。<br/><br/>• チーム メンバーがチャネル会議をスケジュールする機能を有効または無効にします (チャネル会議のスケジュール**)。 <br/><br/>• Teams 会議のビデオ通話を有効または無効にします (Skype 会議のビデオ **)。<br/><br/>• 組織に対して Microsoft Teams ミートアップの画面共有を有効または無効にします (** Skype 会議の画面共有 **)。<br/><br/>• (Giphys と呼ばれる) アニメーション画像を Teams の会話 (アニメーション画像**) に追加する機能を有効または無効にします。 <br/><br/>• 組織のコンテンツの評価設定を変更します (**コンテンツの評価**)。 コンテンツの評価により、会話に表示されるアニメーション画像の種類が制限されます。 <br/><br/>• チーム メンバーがカスタマイズ可能な画像 (カスタム ミームと呼ばれる) をインターネットからチームの会話に追加する機能が、有効または無効になります (インターネットからのカスタマイズ可能な画像 **)。 <br/><br/>• チーム メンバーが編集可能な画像 (ステッカーと呼ばれる) をチームの会話に追加する機能が、有効または無効になります (** 編集可能な画像 **)。<br/><br/>• チーム メンバーが Microsoft Teams のチャットおよびチャネルでボットを使用する機能が、有効または無効になります (組織全体にわたるボット)。 <br/><br/>• Microsoft Teams に対して特定のボットが有効になります。これには、組織に対してボットが有効になっている場合に使用可能な Teams ヘルプ ボットである T-ボットは含まれません (** 個別ボット **)。 <br/><br/>• チーム メンバーが拡張機能またはタブを追加する機能を有効または無効にします (** 拡張機能またはタブ **)。 <br/><br/>• Microsoft Teams に対して専用ボットのサイドローディングが有効または無効になります (** ボットのサイドローディング **)。 <br/><br/>• ユーザーがメール メッセージを Microsoft Teams に送信する機能が、有効または無効になります (** チャネルのメール**)。|
|チーム内のメンバーの役割変更|MemberRoleChanged|チーム所有者がチームのメンバーの役割を変更します。 次の値は、ユーザーに割り当てられる役割の種類を示します。 <br/><br/> **1** - 所有者ロールを示します。<br/>**2** - メンバー ロールを意味します。 <br/>**3** - ゲスト ロールを意味します。 <br/><br/> メンバー プロパティには、組織の名前とメンバーのメール アドレスも含まれます。|
|チームの設定の変更|TeamSettingChanged|次のアクティビティがチームの所有者により実行されると、TeamSettingChanged 操作が記録されます。 これらの各アクティビティについては、変更された設定 (以下のかっこ内) の説明が、監査ログの検索結果の [**項目**] 列に表示されます。 <br/><br/>• チームのアクセスの種類を変更します。 チームは非公開または公開として設定できます (**チームのアクセスの種類**)。 チームが非公開 (既定の設定) の場合、ユーザーはチームには招待状でのみアクセスでき暗ます。 チームが公開されている場合、誰でもチームにアクセスできます。 <br/><br/>• チームの情報の分類を変更します (**チームの分類**)。 <br/> たとえば、チーム データは、事業影響度高、事業影響度中、事業影響度低として分類できます。<br/><br/>• チームの名前を変更します (**チーム名**)。 <br/><br/>• チームの説明を変更します (チームの説明**)。 <br/><br/>• チームの設定のいずれかが変更されました。 チーム所有者は、チームを右クリックし、[**チームの管理**]、[**設定**] タブの順にクリックして、Teams クライアントのこれらの設定にアクセスできます。これらのアクティビティについては、変更された設定の名前が、監査ログの検索結果の [**項目**] 列に表示されます。|
|チームの作成|TeamCreated|ユーザーがチームを作成しました。|
|チャネルの削除|ChannelDeleted|ユーザーがチームからチャネルを削除しました。|
|チームの削除|TeamDeleted|チーム所有者がチームを削除しました。|
|チームからのボットの削除|BotRemovedFromTeam|ユーザーがチームからボットを削除しました。|
|コネクタの削除|ConnectorRemoved|ユーザーがチャネルからコネクタを削除しました。|
|削除されたメンバー|MemberRemoved|チームの所有者が、チーム、チャネル、またはグループ チャットからメンバーを削除しました。|
|タブの削除|TabRemoved|ユーザーがチャネルからタブを削除しました。|
|コネクタの更新|ConnectorUpdated|ユーザーがチャネルのコネクタを変更しました。|
|タブの更新|TabUpdated|ユーザーがチャネルのタブを変更しました。|
|Teams へのユーザーのサインイン|TeamsSessionStarted|ユーザーが Microsoft Teams クライアントにサインインしました。 このイベントは、トークン更新アクティビティをキャプチャしません。|
||||

### <a name="microsoft-teams-healthcare-activities"></a>Microsoft Teams 医療活動アクティビティ

組織で Microsoft Teams の [患者用アプリケーション](https://docs.microsoft.com/MicrosoftTeams/expand-teams-across-your-org/healthcare/patients-app-overview) を使用している場合は、患者アプリの使用に関連するアクティビティの監査ログを検索できます。 患者アプリをサポートするように使用環境が構成されている場合、これらのアクティビティの追加アクティビティグループは、**アクティビティ** 選択リストに表示されます。

![アクティビティ選択リスト内の Microsoft Teams 医療活動 アクティビティ](../media/TeamsHealthcareAuditActivities.png)

患者アプリのアクティビティの説明については、[患者アプリの監査ログ](https://docs.microsoft.com/MicrosoftTeams/expand-teams-across-your-org/healthcare/patients-audit)をご覧ください。

### <a name="microsoft-teams-shifts-activities"></a>Microsoft Teams Shifts アクティビティ

組織で Microsoft Teams の Shifts アプリを使用している場合は、Shifts アプリの使用に関連するアクティビティの監査ログを検索できます。 Shifts アプリをサポートするように使用環境が構成されている場合、これらのアクティビティの追加アクティビティ グループは、[**アクティビティ**] 選択リストに表示されます。

Shifts アプリのアクティビティの説明については、「[Microsoft Teams でイベントの監査ログを検索する](https://docs.microsoft.com/microsoftteams/audit-log-events#shifts-in-teams-activities)」を参照してください。

### <a name="yammer-activities"></a>Yammer アクティビティ

次の表には、監査ログに記録された Yammer のユーザー アクティビティおよび管理者アクティビティの一覧が表示されています。 監査ログから Yammer に関連するアクティビティを返すには、[**アクティビティ**] リストの [**すべてのアクティビティの結果を表示**] を選択する必要があります。 日付範囲のボックスと [**ユーザー**] リストを使用して、検索結果を絞り込みます。

|**フレンドリ名**|**操作名**|**説明**|
|:-----|:-----|:-----|
|データ保持ポリシーの変更|SoftDeleteSettingsUpdated|Verified admin updates the setting for the network data retention policy to either Hard Delete or Soft Delete. Only verified admins can perform this operation.|
|ネットワークの構成の変更|NetworkConfigurationUpdated|Network or verified admin changes the Yammer network's configuration. This includes setting the interval for exporting data and enabling chat.|
|ネットワーク プロファイル設定の変更|ProcessProfileFields|ネットワーク管理者または認証管理者が、ネットワーク ユーザーのネットワークのメンバー プロファイルに表示される情報を変更しました。|
|プライベート コンテンツ モードの変更|SupervisorAdminToggled|認証管理者が、[*プライベート コンテンツ モード*] をオンまたはオフに切り替えます。 管理者は、このモードを使用して、プライベート グループの投稿や、各ユーザー (またはユーザーのグループ) 間のプライベート メッセージを閲覧できます。 この操作を実行できるのは、認証管理者のみです。|
|セキュリティの構成が変更されました|NetworkSecurityConfigurationUpdated|Verified admin updates the Yammer network's security configuration. This includes setting password expiration policies and restrictions on IP addresses. Only verified admins can perform this operation.|
|ファイルの作成|FileCreated|ユーザーがファイルをアップロードしました。|
|グループの作成|GroupCreation|ユーザーがグループを作成しました。|
|グループの削除|GroupDeletion|Yammer からグループが削除されました。|
|メッセージの削除|MessageDeleted|ユーザーがメッセージを削除しました。|
|ファイルのダウンロード|FileDownloaded|ユーザーがファイルをダウンロードしました。|
|データのエクスポート|DataExport|Verified admin exports Yammer network data. Only verified admins can perform this operation.|
|ファイルの共有|FileShared|ユーザーが別のユーザーとファイルを共有しました。|
|ネットワーク ユーザーの一時停止|NetworkUserSuspended|ネットワーク管理者または認証管理者が、Yammer からユーザーを一時停止 (非アクティブ化) しました。|
|ユーザーの一時停止|UserSuspension|ユーザー アカウントが一時停止 (非アクティブ化) されました。|
|ファイルの説明の更新|FileUpdateDescription|ユーザーがファイルの説明を変更しました。|
|ファイル名の更新|FileUpdateName|ユーザーがファイルの名前を変更しました。|
|ファイルの表示|FileVisited|ユーザーがファイルを表示しました。|
||||

### <a name="microsoft-power-automate-activities"></a>Microsoft Power Automate のアクティビティ

Power Automate (旧称: Microsoft Flow) では、監査ログを検索できます。 これらのアクティビティには、フローの作成、編集、および削除と、フローのアクセス許可の変更があります。 Power Automate アクティビティの監査の詳細については、ブログ「[セキュリティ/コンプライアンス センターで利用可能な Microsoft Flow 監査イベント](https://flow.microsoft.com/blog/security-and-compliance-center)」を参照してください。

### <a name="microsoft-power-apps-activities"></a>Microsoft Power Apps アクティビティ

Power Apps では、アプリ関連のアクティビティの監査ログを検索できます。 これらのアクティビティには、アプリの作成、起動、公開が含まれます。 アプリへのアクセス許可の割り当ても監査されます。 Power Apps のすべてのアクティビティの説明については、「[Activity logging for Power Apps のアクティビティのログ](https://docs.microsoft.com/power-platform/admin/logging-powerapps#what-events-are-audited)」を参照してください。

### <a name="microsoft-stream-activities"></a>Microsoft Stream アクティビティ

監査ログで Microsoft Stream のアクティビティを検索できます。 これらのアクティビティには、ユーザーが実行するビデオ アクティビティ、グループ チャネル アクティビティ、管理アクティビティ (ユーザーの管理、組織の設定の管理、レポートのエクスポートなど) が含まれます。 これらのアクティビティの詳細については、「[Microsoft Stream の監査ログ](https://docs.microsoft.com/stream/audit-logs#actions-logged-in-stream)」の「Stream に記録されたアクション」を参照してください。

### <a name="content-explorer-activities"></a>コンテンツ エクスプローラー アクティビティ

監査ログに記録されるコンテンツ エクスプローラーのアクティビティの一覧を次の表に記載します。 コンテンツ エクスプローラーは、Microsoft 365 コンプライアンス センターの [データ分類ツール] でアクセスできます。 詳細については、「[データ分類コンテンツ エクスプローラーの使用](data-classification-content-explorer.md)」を参照してください。

|**フレンドリ名**|**操作名**|**説明**|
|:-----|:-----|:-----|
|項目がアクセスされました|LabelContentExplorerAccessedItem|管理者 (またはコンテンツ エクスプローラー コンテンツ ビューアー役割グループのメンバーであるユーザー) は、コンテンツ エクスプローラーを使用して電子メール メッセージまたは SharePoint/OneDrive ドキュメントを表示します。|
||||

### <a name="quarantine-activities"></a>検疫アクティビティ

次の表に、監査ログで検索できる検疫アクティビティを示します。 検疫の詳細については、「[Office 365 でのメール メッセージの検疫](../security/office-365-security/quarantine-email-messages.md)」を参照してください。

|**フレンドリ名**|**操作名**|**説明**|
|:-----|:-----|:-----|
|削除された検疫メッセージ|QuarantineDelete|ユーザーが有害と見なされたメール メッセージを削除しました。|
|エクスポートされた検疫メッセージ|QuarantineExport|ユーザーが有害と見なされたメール メッセージをエクスポートしました。|
|プレビューされた検疫メッセージ|QuarantinePreview|ユーザーが有害と見なされたメール メッセージをプレビューしました。|
|解放された検疫メッセージ|QuarantineRelease|ユーザーが有害と見なされたメール メッセージを検疫から解放しました。|
|表示された検疫メッセージのヘッダー|QuarantineViewHeader|ユーザーが有害と見なされたメール メッセージのヘッダーを表示しました。|
||||

### <a name="microsoft-forms-activities"></a>Microsoft Forms アクティビティ

次の表には、監査ログに記録された Microsoft Forms のユーザー アクティビティおよび管理者アクティビティの一覧が表示されています。 Microsoft Forms は、データを収集し分析するために使用するフォーム/クイズ/アンケート ツールです。 

下記の説明に別途記載するとおり、一部の操作には追加のアクティビティ パラメーターが含まれます。

> [!NOTE]
> Forms アクティビティが共同作成者または匿名のレスポンダーによって実行される場合、わずかに異なるログが記録されます。 詳細については、[共同作成者および匿名のレスポンダーによって実行される Forms アクティビティ](#forms-activities-performed-by-co-authors-and-anonymous-responders) セクションを参照してください。

|**フレンドリ名**|**操作名**|**説明**|
|:-----|:-----|:-----|
|コメントが作成される|CreateComment|フォーム所有者がコメントまたはスコアをクイズに追加する。|
|フォームが作成される|CreateForm|フォーム所有者が新しいフォームを作成する。|
|フォームが編集される|EditForm|フォーム所有者が質問の作成、削除、編集など、フォームを編集する。 <br><br>プロパティ EditOperation:string は、編集操作名を示します。 これに含まれる操作: CreateQuestion、CreateQuestionChoice、DeleteQuestion、DeleteQuestionChoice、DeleteFormImage、DeleteQuestionImage、UpdateQuestion、UpdateQuestionChoice、UploadFormImage/Bing/Onedrive、UploadQuestionImage、および ChangeTheme  <br><br>ほとんどの操作名は、特に説明を必要としないはずです。 <br><br>FormImage には、クエリ内や背景テーマなど、ユーザーが画像をアップロードできるフォーム内のすべての場所が含まれます。|
|フォームが移動される|MoveForm|フォーム所有者がフォームを移動する。 <br><br>プロパティ DestinationUserId:string は、フォームを移動したユーザーのユーザー ID を示します。 プロパティ NewFormId:string は、新たにコピーされたフォームの新しい ID です。|
|フォームが削除される|DeleteForm|フォーウ所有者がフォームを削除する。 これには、SoftDelete (削除オプションが使用され、フォームがごみ箱に移動されます) と HardDelete (ごみ箱が空になります) が含まれます。|
|フォームが表示される (デザイン時)|ViewForm|フォーム所有者が既存のフォームを編集するために開く。|
|フォームがプレビューされる|PreviewForm|フォーム所有者がプレビュー機能を使用してフォームをプレビューする。|
|フォームがエクスポートされる|ExportForm|フォーム所有者が結果を Excel にエクスポートする。 <br><br>プロパティ ExportFormat:string は、Excel ファイルがダウンロードなのかオンラインなのかを示します。|
|コピー用のフォームの共有が許可される|AllowShareFormForCopy|フォームを他のユーザーと共有するためのテンプレート リンクをフォーム所有者が作成する。 このイベントは、フォーム所有者がテンプレート URL を生成するためにクリックした際にログに記録されます。|
|コピー用のフォームの共有が許可されない|DisallowShareFormForCopy|フォーム所有者がテンプレートリンクを削除する。|
|フォームの共同編集者が追加される|AddFormCoauthor|回答のデザインや表示のための共同作業リンクをユーザーが使用する。 このイベントは、共同作業 URL が最初に生成されたときではなくユーザーが共同作業 URL を使用したときにログに記録されます。|
|フォームの共同編集者が削除される|RemoveFormCoauthor|フォーム所有者が共同作業リンクを削除する。|
|回答ページが表示される|ViewRuntimeForm|ユーザーが回答ページを開いて表示する。 このイベントは、ユーザーが回答を送信するかどうかに関わらずログに記録されます。|
|回答が作成される|CreateResponse|新しい回答の受信と似ています。  ユーザーがフォームへの回答を送信しました。 <br><br>プロパティ ResponseId:string とプロパティ ResponderId:string は、どの結果が表示されたかを示します。 <br><br>匿名回答者の場合、ResponderId プロパティは null となります。|
|回答が更新される|UpdateResponse|フォーム所有者がクイズのコメントまたはスコアを更新した。 <br><br>プロパティ ResponseId:string とプロパティ ResponderId:string は、どの結果が表示されたかを示します。 <br><br>匿名回答者の場合、ResponderId プロパティは null となります。|
|すべての回答が削除される|DeleteAllResponses|フォーム所有者がすべての回答データを削除する。|
|回答が削除される|DeleteResponse|フォーム所有者が回答を 1 件削除する。 <br><br>プロパティ ResponseId:string は、削除される回答を示します。|
|複数の回答が表示される|ViewResponses|フォーム所有者が回答の集計リストを表示する。 <br><br>プロパティ ViewType:string は、フォーム所有者は「詳細」を表示しているのか、「集計」を表示しているのかを示します。|
|1 件の回答が表示される|ViewResponse|フォーム所有者が特定の 1 件の回答を表示する。 <br><br>プロパティ ResponseId:string とプロパティ ResponderId:string は、どの結果が表示されたかを示します。 <br><br>匿名回答者の場合、ResponderId プロパティは null となります。|
|概要リンクが作成される|GetSummaryLink|結果を共有するための概要結果リンクをフォーム所有者が作成する。|
|概要リンクが削除される|DeleteSummaryLink|フォーム所有者が概要結果リンクを削除する。|
|フォームのフィッシング状態が更新される|UpdatePhishingStatus|このイベントは、内部セキュリティ状態の詳細値が変更されたとき、この変更により最終的なセキュリティの状態 (たとえば、現在フォームは「終了済み」または「開始済み」) が変更されたかどうかに関わらずログに記録されます。 つまり、最終的なセキュリティ状態が変更されない場合でも、重複するイベントが表示されることがあります。|
|Forms Pro の招待が送信される|ProInvitation|ユーザーがクリックして Pro の試用版をアクティブにする。|
|フォームの設定が更新される|UpdateFormSetting|フォーム所有者がフォームの設定を更新する。 <br><br>プロパティ FormSettingName:string は、設定名と新しい値を示します。|
|ユーザー設定が更新される|UpdateUserSetting|フォーム所有者がユーザー設定を更新する。 <br><br>プロパティ UserSettingName:string は、設定名と新しい値を示します。|
|フォームが一覧表示される|ListForms|フォーム所有者がフォームの一覧を表示している。 <br><br>プロパティ ViewType:string は、フォーム所有者が表示に使用しているビュー ([すべてのフォーム]、[自分と共有]、または [グループ フォーム]) を示します。|
|回答が送信される|SubmitResponse|ユーザーがフォームへの回答を送信する。 <br><br>プロパティ IsInternalForm:boolean は、回答者がフォーム所有者と同じ組織内にいるかどうかを示します。|
||||

#### <a name="forms-activities-performed-by-co-authors-and-anonymous-responders"></a>共同作成者および匿名のレスポンダーによって実行される Forms アクティビティ

Forms は、フォームの設計時および回答の分析時の協同作業をサポートします。 フォームの協力者は、*共同作成者* として知られています。 共同作成者は、フォームの削除または移動を除き、フォームの所有者が実行できるすべての操作を実行できます。 また、Forms を使用すると、匿名で回答できるフォームを作成できます。 これは、フォームに回答するためにレスポンダーが組織にサインインする必要がないことを意味します。 

次の表は、共同作成者と匿名のレスポンダーによって実行されたアクティビティの監査アクティビティおよび監査レコードの情報を示しています。

|**アクティビティの種類**|**内部または外部ユーザー**|**ログに記録されたユーザー ID**|**ログインしている組織**|**Forms ユーザーの種類**|
|:-----|:-----|:-----|:-----|:-----|
|共同編集アクティビティ|内部|UPN|フォームの所有者の組織|共同作成者|
|共同編集アクティビティ|外部|UPN<br>|共同作成者の組織<br>|共同作成者|
|共同編集アクティビティ|外部|`urn:forms:coauthor#a0b1c2d3@forms.office.com`<br>(ID の 2 番目の部分はハッシュであり、ユーザーによって異なります)|フォームの所有者の組織<br>|共同作成者|
|回答アクティビティ|外部|UPN<br>|レスポンダーの組織<br>|レスポンダー|
|回答アクティビティ|外部|`urn:forms:external#a0b1c2d3@forms.office.com`<br>(ユーザー ID の 2 番目の部分はハッシュであり、ユーザーによって異なります)|フォームの所有者の組織|レスポンダー|
|回答アクティビティ|匿名|`urn:forms:anonymous#a0b1c2d3@forms.office.com`<br>(ユーザー ID の 2 番目の部分はハッシュであり、ユーザーによって異なります)|フォームの所有者の組織|レスポンダー|
||||

### <a name="sensitivity-label-activities"></a>機密ラベル アクティビティ

次の表に、SharePoint Online および Teams サイトのラベル付けアクティビティから生じるイベントを一覧表示します。

|**フレンドリ名**|**操作名**|**説明**|
|:-----|:-----|:-----|
|サイトに適用された機密ラベル|SensitivityLabelApplied|機密ラベルが SharePoint または Teams サイトに適用されました。|
|サイトから削除された機密ラベル|SensitivityLabelRemoved|SharePoint または Teams サイトから機密ラベルが削除されました。|
|ファイルに適用された機密ラベル|FileSensitivityLabelApplied|Office on the web または自動ラベル付けポリシーを使用して、機密ラベルがドキュメントに適用されました。|
|ファイルに適用された機密ラベルの変更|FileSensitivityLabelChanged|Office on the web または自動ラベル付けポリシーを使用して、異なる機密ラベルがドキュメントに適用されました。|
|ファイルから削除された機密ラベル|FileSensitivityLabelRemoved|Office on the web または自動ラベル付けポリシーを使用して、機密ラベルがドキュメントから削除されました。|
||||

### <a name="exchange-admin-audit-log"></a>Exchange 管理者監査ログ

(Office 365 において既定で有効になっている) Exchange 管理者監査ログは、管理者 (または管理者権限が割り当てられているユーザー) が Exchange Online の組織で変更を行ったときに、監査ログにイベントを記録します。 Exchange 管理センターを使用するか、Exchange Online PowerShell でコマンドレットを実行して加えられた変更は、Exchange 管理者監査ログに記録されます。 監査ログには、動詞の **Get-**、**Search-**、または **Test-** で始まるコマンドレットは記録されません。 Exchange の管理者監査ログの詳細については、「[管理者監査ログ](https://go.microsoft.com/fwlink/p/?LinkID=619225)」を参照してください。

> [!IMPORTANT]
> Exchange 管理者監査ログ (または監査ログ) に記録されない一部の Exchange Online コマンドレット。 これらのコマンドレットの多くは、Exchange Online サービスの保守に関連しており、Microsoft データセンサーの担当者またはサービス アカウントによって実行されます。 "雑音の多い" 監査イベントが多数発生するため、これらのコマンドレットはログに記録されません。 監査されていない Exchange Online コマンドレットがある場合は、[セキュリティ/コンプライアンスの UserVoice フォーラム](https://office365.uservoice.com/forums/289138-office-365-security-compliance)に提案を送信して、監査を有効にするよう依頼してください。 Microsoft サポートには、デザイン変更依頼 (DCR) を送信することもできます。

監査ログを検索するときに Exchange 管理者のアクティビティを検索するためのヒントをいくつか紹介します。

- To return entries from the Exchange admin audit log, you have to select **Show results for all activities** in the **Activities** list. Use the date range boxes and the **Users** list to narrow the search results for cmdlets run by a specific Exchange administrator within a specific date range.

- Exchange 管理者監査ログのイベントを表示するには、検索結果をフィルター処理し、[**アクティビティ**] フィルター ボックスに「**-**」(ダッシュ) を入力します。 これにより、Exchange 管理者イベントの [**アクティビティ**] 列にコマンドレット名が表示されます。 次に、コマンドレット名をアルファベット順に並べ替えることができます。

  ![[アクティビティ] ボックスにダッシュを入力して Exchange 管理イベントをフィルター処理する](../media/7628e7aa-6263-474a-a28b-2dcf5694bb27.png)

- 実行されたコマンドレット、使用されたパラメーターおよびパラメーター値、影響を受けたオブジェクトに関する情報を取得するには、[**すべての結果をダウンロードする**] オプションを選択することで検索結果をエクスポートできます。 詳細については、「[監査ログ レコードをエクスポート、構成、表示する](export-view-audit-log-records.md)」を参照してください。

- Exchange Online PowerShell の `Search-UnifiedAuditLog -RecordType ExchangeAdmin` コマンドを使用して、Exchange 管理者監査ログの監査レコードのみを返すこともできます。 Exchange コマンドレットの実行後、対応する監査ログ エントリが検索結果に返されるまで、最大で 30 分かかる場合があります。 詳細については、「[Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog)」を参照してください。 **Search-UnifiedAuditLog** コマンドレットによって返された検索結果を CSV ファイルにエクスポートする方法の詳細については、「[監査ログ レコードをエクスポート、構成、表示する](export-view-audit-log-records.md#tips-for-exporting-and-viewing-the-audit-log)」の「監査ログをエクスポート、表示するためのヒント」のセクションを参照してください。

- Exchange 管理センターを使用して、または Exchange Online PowerShell で **Search-AdminAuditLog** を実行して、Exchange 管理者監査ログのイベントを表示することもできます。 これは、Exchange Online 管理者が実行したアクティビティを特定するのに適した方法です。 手順については、以下を参照してください。

  - [管理者監査ログを表示する](https://technet.microsoft.com/library/dn342832%28v=exchg.150%29.aspx)

  - [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog)

   Exchange 管理者監査ログと監査ログの両方に同じ Exchange 管理者アクティビティが記録される点に注意してください。


## <a name="frequently-asked-questions"></a>よく寄せられる質問

**現在監査対象となっている Microsoft 365 サービスは何ですか?**

Exchange Online、SharePoint Online、OneDrive for Business、Azure Active Directory、Microsoft Teams、Dynamics 365、Advanced Threat Protection、Power BI など、特に使用頻度の高いサービスが監査されます。 監査対象のサービスのリストについては、[この記事の冒頭](search-the-audit-log-in-security-and-compliance.md)を参照してください。

**Office 365 の監査サービスでは、どんなアクティビティが監視されますか? **

監査されるアクティビティの一覧と説明については、この記事の「[監査されるアクティビティ](#audited-activities)」のセクションを参照してください。

**イベント発生後、監査レコードが使用できるようになるまでどのくらいの時間がかかりますか? **

ほとんどの監査データは 30 分以内に利用可能になりますが、イベントが発生してから対応する監査ログ エントリが検索結果に表示されるまでに最大 24 時間かかる場合があります。 この記事の「[監査ログを検索するための要件](#requirements-to-search-the-audit-log)」セクションの表に、さまざまなサービスのイベントが利用可能になるまでの時間を示します。

**監査レコードの保持期間はどのくらいですか? **

前述のように、Office 365 E5 または Microsoft E5 ライセンスが割り当てられたユーザー (または Microsoft 365 E5 アドオンライセンスを持っているユーザー) が実行したアクティビティの監査レコードは、1 年間保持されます。 統合監査ログをサポートする他のすべてのサブスクリプションの場合、監査レコードは 90 日間保持されます。

**プログラムを使用して監査データにアクセスできますか? **

Yes. The Office 365 Management Activity API is used to fetch the audit logs programmatically.  To get started, see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).

**セキュリティ/コンプライアンス センターまたは Office 365 マネージメント アクティビティ API の使用以外に、監査ログを取得する方法はありますか?**

いいえ。 監査サービスからデータを取得する方法は、この 2 つの方法のみです。

**監査ログを取得したい各サービスで監査を個別に有効にする必要がありますか? **

ほとんどのサービスでは、最初に組織の監査を有効にした後で、既定で監査が有効になります (この記事の「[監査ログを検索するための要件](#requirements-to-search-the-audit-log)」セクションを参照してください)。

**監査サービスは、レコードの重複除去をサポートしますか?**

いいえ。 監査サービス パイプラインはほとんどリアルタイムであるため、重複除去をサポートできません。

**監査データは地域を超えて流出しますか?**

いいえ。 現在、NA (北米)、EMEA (ヨーロッパ、中東、アフリカ)、および APAC (アジア太平洋) 地域に、監査パイプラインを展開しています。 ただし、負荷分散や、ライブサイトの問題発生時にのみ、こういった地域にデータを転送する場合があります。 これらのアクティビティを実行すると、転送中のデータが暗号化されます。

**監査データは暗号化されますか? **

監査データは、統合監査パイプラインが展開されるのと同じ地域の Exchange メールボックス(保存データ)に保存されます。 保管中のメールボック スデータは、Exchange によって暗号化されません。 ただし、Microsoft データセンターの Exchange サーバーは BitLocker を介して暗号化されるため、サービス レベルの暗号化はすべてのメールボックス データを暗号化します。 詳細の情報に、「[Skype for Business、OneDrive for Business、SharePoint Online、および Exchange Online 用の Office 365 の暗号化](office-365-encryption-for-skype-onedrive-sharepoint-and-exchange.md)」を参照してください。

送信中のメールデータは常に暗号化されます。
