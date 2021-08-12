---
title: 監査ログで電子情報開示アクティビティを検索する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 67cc7f42-a53d-4751-b929-6005c80798f7
description: 電子情報開示アクセス許可が割り当てられたユーザーがコンテンツ検索、コア電子情報開示、および Advanced eDiscovery タスクを実行するときに記録されるイベントMicrosoft 365 コンプライアンス センター。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 097e78c85af5bc75998e1a75fe6148b64afec0eb36d7c19851153920c59a4de0
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53795544"
---
# <a name="search-for-ediscovery-activities-in-the-audit-log"></a>監査ログで電子情報開示アクティビティを検索する

Microsoft 365 コンプライアンス センター または対応する PowerShell コマンドレットを実行して実行されるコンテンツ検索および電子情報開示関連のアクティビティ (Core eDiscovery および Advanced eDiscovery の場合) は、監査ログに記録されます。 イベントは、管理者または電子情報開示マネージャー (または電子情報開示アクセス許可が割り当てられたユーザー) が、次のコンテンツ検索タスクとコア電子情報開示タスクを実行するときにログに記録Microsoft 365 コンプライアンス センター。
  
- コアケースとセキュリティ ケースのAdvanced eDiscovery管理する

- コンテンツ検索の作成、開始、および編集

- 検索結果のプレビュー、エクスポート、削除などの検索アクションの実行

- 管理担当者とレビュー セットを管理するAdvanced eDiscovery

- コンテンツ検索のアクセス許可フィルターの構成

- 電子情報開示管理者の役割の管理
  
監査ログの検索、必要なアクセス許可、および検索結果のエクスポートの詳細については、「監査ログを検索する」を参照[Microsoft 365 コンプライアンス センター。](search-the-audit-log-in-security-and-compliance.md)
  
## <a name="how-to-search-for-and-view-ediscovery-activities"></a>電子情報開示アクティビティを検索して表示する方法

現在、監査ログに記録された電子情報開示アクティビティを表示するには、いくつかの特定の操作を実行する必要があります。 これを行うには、次の操作を実行します。
  
1. <https://compliance.microsoft.com>に移動し、職場または学校アカウントを使用してサインインします。

2. 左側のナビゲーション ウィンドウで、[監査] をMicrosoft 365 コンプライアンス センターを **クリックします**。

3. [アクティビティ **] ドロップダウン** リストの [**電子** 情報開示アクティビティ] または [Advanced eDiscovery] で、検索する 1 つ以上のアクティビティをクリックします。

    > [!NOTE]
    > [**アクティビティ]** ドロップダウン リストには、コマンドレット監査ログからレコードを返す電子情報開示コマンドレット アクティビティという名前のアクティビティのグループも含まれています。
  
4. 日付と時間の範囲を選択します。その期間内に発生した電子情報開示イベントが表示されます。

5. [**ユーザー**] ボックスで、検索結果を表示する 1 人以上のユーザーを選択します。 すべてのユーザーのエントリを返すには、このボックスを空白のままにします。

6. [**検索**] をクリックして、設定した検索条件で検索を実行します。

7. 検索結果が表示されたら、[**フィルター結果**] をクリックして、結果のアクティビティ レコードをフィルター処理または並べ替えることができます。 残念ながら、フィルターを使用して、特定のアクティビティを明示的に除外することはできません。 

8. アクティビティの詳細を表示するには、検索結果のリストでアクティビティ レコードをクリックします。 

    イベント レコードの詳細なプロパティが記載された [**詳細**] スライド アウト ページが表示されます。 さらに詳細な情報を表示するには、[**詳細情報**] をクリックします。 これらのプロパティの説明については、「[電子情報開示アクティビティの詳細なプロパティ](#detailed-properties-for-ediscovery-activities)」セクションを参照してください。

9. 必要に応じて、監査ログの検索結果を CSV ファイルにエクスポートし、Excel Power Query 機能を使用して、これらのレコードの書式設定とフィルター処理を行います。 詳細については、「[監査ログ レコードをエクスポート、構成、表示する](export-view-audit-log-records.md)」を参照してください。

## <a name="ediscovery-activities"></a>電子情報開示アクティビティ

次の表では、管理者または電子情報開示マネージャーが電子情報開示関連のアクティビティを Microsoft 365 コンプライアンス センター を使用して実行するときにログに記録されるコンテンツ検索およびコア電子情報開示アクティビティについて説明します。 この一覧でアクティビティAdvanced eDiscovery検索すると、一部のアクティビティが返される場合があります。
  
> [!NOTE]
> このセクションに示されている電子情報開示アクティビティは、次のセクションで説明される電子情報開示コマンドレットのアクティビティと同様の情報を示しています。 電子情報開示アクティビティは 30 分以内に監査ログの検索結果に表示されるため、このセクションで示されている電子情報開示アクティビティを使用することをお勧めします。 電子情報開示コマンドレットのアクティビティが監査ログの検索結果に表示するには、最大で 24 時間かかる場合があります。
  
|**フレンドリ名**|**操作名**|**対応するコマンドレット**|**説明**|
|:-----|:-----|:-----|:-----|
|電子情報開示ケースにメンバーが追加されました  <br/> |CaseMemberAdded  <br/> |Add-ComplianceCaseMember  <br/> |ユーザーが電子情報開示ケースのメンバーとして追加されました。 ケースのメンバーとしてユーザーは、必要なアクセス許可が割り当てられているかどうかに応じて、ケース関連のさまざまなタスクを実行できます。  <br/> |
|コンテンツ検索が変更されました  <br/> |SearchUpdated  <br/> |Set-ComplianceSearch  <br/> |既存のコンテンツの検索が変更されました。 変更としては、コンテンツの場所の追加または削除、検索クエリの編集などがあります。  <br/> |
|電子情報開示管理者のメンバーシップが変更されました  <br/> |CaseAdminUpdated  <br/> |Update-eDiscoveryCaseAdmin  <br/> |組織の電子情報開示管理者のリストが変更されました。 このアクティビティは、電子情報開示管理者が新しいユーザーのグループに置き換えられた場合にログに記録されます。 1 人のユーザーが追加または削除されると、CaseAdminAdded の操作がログに記録されます。  <br/> |
|電子情報開示ケースが変更されました  <br/> |CaseUpdated  <br/> |Set-ComplianceCase  <br/> |電子情報開示ケースが変更されました。 変更としては、開いているケースを閉じる、閉じたケースを再度開くなどがあります。  <br/> |
|電子情報開示ケースのメンバーシップが変更されました  <br/> |CaseMemberUpdated  <br/> |Update-ComplianceCaseMember  <br/> |電子情報開示ケースのメンバーシップ リストが変更されました。 このアクティビティは、すべてのメンバーが新しいユーザーのグループに置き換えられたときにログに記録されます。 単一のメンバーが追加または削除されると、CaseMemberAdded または CaseMemberRemoved 操作がログに記録されます。  <br/> |
|検索のアクセス許可フィルターが変更されました  <br/> |SearchPermissionUpdated  <br/> |Set-ComplianceSecurityFilter  <br/> |検索のアクセス許可フィルターが変更されました。  <br/> |
|電子情報開示ケースの保留に対する検索クエリが変更されました  <br/> |HoldUpdated  <br/> |Set-CaseHoldRule  <br/> |電子情報開示ケースに関連付けられたクエリベースの保留が変更されました。 発生する可能性のある変更としては、クエリの編集、クエリベースの保留の日付範囲の編集があります。  <br/> |
|コンテンツ検索のプレビュー アイテムがダウンロードされました  <br/> |PreviewItemDownloaded  <br/> |該当なし  <br/> |検索結果のプレビュー時に、ユーザーが ([**オリジナルのアイテムをダウンロード**] リンクをクリックして) アイテムをローカル コンピューターにダウンロードしました。  <br/> |
|コンテンツ検索のプレビュー アイテムが一覧されました  <br/> |PreviewItemListed  <br/> |該当なし  <br/> |ユーザーが [検索結果 **のプレビュー** ] をクリックすると、検索結果のプレビュー ページが表示され、検索の結果から最大 1,000 アイテムが一覧表示されます。  <br/> |
|コンテンツ検索のプレビュー アイテムが表示されました  <br/> |PreviewItemRendered  <br/> |該当なし  <br/> |電子情報開示管理者が、検索結果のプレビュー時にアイテムをクリックして、アイテムを表示しました。  <br/> |
|コンテンツ検索が作成されました  <br/> |SearchCreated  <br/> |New-ComplianceSearch  <br/> |新しいコンテンツ検索が作成されました。  <br/> |
|電子情報開示管理者が作成されました  <br/> |CaseAdminAdded  <br/> |Add-eDiscoveryCaseAdmin  <br/> |ユーザーが、組織の電子情報開示管理者として追加されました。  <br/> |
|電子情報開示ケースが作成されました  <br/> |CaseAdded  <br/> |New-ComplianceCase  <br/> |電子情報開示ケースが作成されました。 ケースを作成する際に必要な操作は、名前を付けることだけです。 メンバーの追加、保留の作成、ケースに関連付けられたコンテンツ検索の作成などの他のケース関連のタスクにより、追加のイベントがログに記録されます。  <br/> |
|検索のアクセス許可フィルターが作成されました  <br/> |SearchPermissionCreated  <br/> |New-ComplianceSecurityFilter  <br/> |検索のアクセス許可フィルターが作成されました。  <br/> |
|電子情報開示ケースの保留に対する検索クエリが作成されました  <br/> |HoldCreated  <br/> |New-CaseHoldRule  <br/> |電子情報開示ケースに関連付けられたクエリベースの保留が作成されました。  <br/> |
|コンテンツ検索が削除されました  <br/> |SearchRemoved  <br/> |Remove-ComplianceSearch  <br/> |既存のコンテンツ検索が削除されました。  <br/> |
|電子情報開示管理者が削除されました  <br/> |CaseAdminRemoved  <br/> |Remove-eDiscoveryCaseAdmin  <br/> |電子情報開示管理者が組織から削除されました。  <br/> |
|電子情報開示ケースが削除されました  <br/> |CaseRemoved  <br/> |Remove-ComplianceCase  <br/> |電子情報開示ケースが削除されました。 ケースを削除する前に、ケースに関連付けられた保留をすべて削除する必要があります。  <br/> |
|検索のアクセス許可フィルターが削除されました  <br/> |SearchPermissionRemoved  <br/> |Remove-ComplianceSecurityFilter  <br/> |検索のアクセス許可フィルターが削除されました。  <br/> |
|電子情報開示ケースの保留に対する検索クエリが削除されました  <br/> |HoldRemoved  <br/> |Remove-CaseHoldRule  <br/> |電子情報開示ケースに関連付けられたクエリベースの保留が削除されました。 多くの場合、保留リストからのクエリの削除は、保留を削除した結果として発生します。 保留または保留クエリを削除する場合、保留中だったコンテンツの場所は解放されます。  <br/> |
|コンテンツ検索のエクスポートがダウンロードされました  <br/> |SearchExportDownloaded  <br/> |該当なし  <br/> |ユーザーがコンテンツ検索の結果をローカル コンピューターにダウンロードしました。 検索結果をダウンロードするには、**コンテンツ検索のエクスポートが開始されました** のアクティビティを開始している必要があります。  <br/> |
|コンテンツ検索の結果がプレビューされました  <br/> |SearchPreviewed  <br/> |該当なし  <br/> |ユーザーがコンテンツ検索の結果をプレビューしました。  <br/> |
|コンテンツ検索の結果が消去されました  <br/> |SearchResultsPurged  <br/> |New-ComplianceSearchAction  <br/> |ユーザーは **、New-ComplianceSearchAction -Purge** コマンドを実行して、コンテンツ検索の結果を削除しました。  <br/> |
|コンテンツ検索の分析が削除されました  <br/> |RemovedSearchResultsSentToZoom  <br/> |Remove-ComplianceSearchAction  <br/> |(Advanced eDiscovery の検索結果を準備するための) コンテンツ検索の準備アクションが削除されました。 準備アクションから 2 週間経過していない場合は、Advanced eDiscovery のために準備された検索結果は Microsoft Azure 記憶域から削除されています。 準備アクションが 2 週間以上経過している場合は、このイベントは、対応する準備アクションのみが削除されたことを示しています。  <br/> |
|コンテンツ結果のエクスポートが削除されました  <br/> |RemovedSearchExported  <br/> |Remove-ComplianceSearchAction  <br/> |コンテンツ検索のエクスポート アクションは削除されました。 エクスポート アクションから 2 週間経っていない場合は、Microsoft Azure 記憶域にアップロードされた検索結果は削除されています。 エクスポート アクションが 2 週間以上経過している場合は、このイベントは、対応するエクスポート アクションのみが削除されたことを示しています。  <br/> |
|電子情報開示ケースからメンバーが削除されました  <br/> |CaseMemberRemoved  <br/> |Remove-ComplianceCaseMember  <br/> |ユーザーが、電子情報開示ケースのメンバーから削除されました。  <br/> |
|コンテンツ検索の結果のプレビューが削除されました  <br/> |RemovedSearchPreviewed  <br/> |Remove-ComplianceSearchAction  <br/> |コンテンツ検索のプレビュー アクションが削除されました。  <br/> |
|コンテンツ検索で実行された消去アクションが削除されました  <br/> |RemovedSearchResultsPurged  <br/> |Remove-ComplianceSearchAction  <br/> |コンテンツ検索の消去アクションが削除されました。  <br/> |
|検索レポートが削除されました  <br/> |SearchReportRemoved  <br/> |Remove-ComplianceSearchAction  <br/> |コンテンツ検索のエクスポート レポート アクションが削除されました。  <br/> |
|コンテンツ検索の分析が開始されました  <br/> |SearchResultsSentToZoom  <br/> |New-ComplianceSearchAction  <br/> |コンテンツ検索の結果が、Advanced eDiscovery の分析用に準備されました。  <br/> |
|コンテンツ検索が開始されました  <br/> |SearchStarted  <br/> |Start-ComplianceSearch  <br/> |コンテンツ検索が開始されました。 ユーザー設定を使用してコンテンツ検索を作成または変更するとMicrosoft 365 コンプライアンス センター自動的に検索が開始されます。<br/> |
|コンテンツ検索のエクスポートが開始されました  <br/> |SearchExported  <br/> |New-ComplianceSearchAction  <br/> |ユーザーがコンテンツ検索の結果をエクスポートしました。  <br/> |
|レポートのエクスポートが開始されました  <br/> |SearchReport  <br/> |New-ComplianceSearchAction  <br/> |ユーザーがコンテンツ検索レポートをエクスポートしました。  <br/> |
|コンテンツ検索が停止されました  <br/> |SearchStopped  <br/> |Stop-ComplianceSearch  <br/> |ユーザーがコンテンツ検索を停止しました。  <br/> |
|(なし)|CaseViewed|Get-ComplianceCase|ユーザーがコンプライアンス センターでコア電子情報開示ケースを表示しました。 このイベントの監査レコードには、表示されたケースの名前が含まれます。 |
|(なし)|SearchViewed|Get-ComplianceSearch|ユーザーは、コア電子情報開示ケースの [検索] タブの検索にアクセスするか、[コンテンツの検索] ページでアクセスして、コンプライアンス センターでコンテンツ検索を **表示** しました。 このイベントの監査レコードには、表示された検索の ID が含まれます。|
|(なし)|ViewedSearchExported|Get-ComplianceSearchAction -Export|ユーザーは、コンテンツ検索ページの [エクスポート] タブのエクスポートにアクセスして、コンプライアンス センターでコンテンツ検索エクスポート **を表示** しました。 このアクティビティは、ユーザーが Core 電子情報開示ケースに関連付けられたエクスポートを表示するときにもログに記録されます。|
|(なし)|ViewedSearchPreviewed|Get-ComplianceSearchAction -Preview|ユーザーがコンプライアンス センターでコンテンツ検索の結果をプレビューしました。 このアクティビティは、ユーザーが Core 電子情報開示ケースに関連付けられた検索の結果をプレビューするときにもログに記録されます。|
|||||
  
## <a name="advanced-ediscovery-activities"></a>Advanced eDiscovery アクティビティ

次の表に、監査Advanced eDiscovery記録されるアクティビティの一覧を示します。 これらのアクティビティは、ケース内のアクティビティの進行状況を追跡Advanced eDiscoveryできます。

|**フレンドリ名**|**操作名**|**説明**|
|:-----|:-----|:-----|
|別のレビュー セットへのデータの追加|AddWorkingSetQueryToWorkingSet|ユーザーが、1つのレビュー セットから別のレビュー セットにドキュメントを追加しました。|
|レビュー セットへのデータの追加|AddQueryToWorkingSet|ユーザーが、Advanced eDiscovery のケースに関連付けられているコンテンツ検索の検索結果をレビュー セットに追加しました。|
|Microsoft 365 以外のデータのレビュー セットへの追加|AddNonOffice365DataToWorkingSet|ユーザーが、Microsoft 365 以外のデータをレビュー セットに追加しました。|
|レビュー セットへの修復済みドキュメントの追加|AddRemediatedData|ユーザーが、インデックス作成エラーがあったドキュメントを修復したものをレビュー セットにアップロードしました。|
|レビュー セット内のデータの分析|RunAlgo|ユーザーが、レビュー セット内のドキュメントの分析を実行しました。|
|レビュー セット内ドキュメントへの注釈付け|AnnotateDocument|ユーザーが、レビュー セット内のドキュメントに注釈を付けました。 注釈付けには、ドキュメントのコンテンツの編集が含まれます。|
|読み込みセットの比較|LoadComparisonJob|ユーザーが、レビュー セット内の 2 つの異なる読み込みセットを比較しました。 読み込みセットは、ケースに関連付けられているコンテンツ検索からのデータがレビュー セットに追加されたときに比較されます。|
|編集されたドキュメントの PDF への変換|BurnJob|ユーザーが、レビュー セット内のすべての編集されたドキュメントを PDF ファイルに変換しました。|
|レビュー セットの作成|CreateWorkingSet|ユーザーがレビュー セットを作成しました。|
|レビュー セット検索の作成|CreateWorkingSetSearch|ユーザーが、レビュー セット内のドキュメントを検索する検索クエリを作成しました。|
|タグの作成|CreateTag|ユーザーが、レビュー セット内でタグ グループを作成しました。 タグ グループには、1つまたは複数の子タグを含めることができます。 これらのタグは、レビュー セット内のドキュメントへのタグ付けに使用されます。|
|レビュー セット検索の削除|DeleteWorkingSetSearch|ユーザーが、レビュー セット内の検索クエリを削除しました。|
|タグの削除|DeleteTag|ユーザーが、レビュー セット内のタグまたはタグ グループを削除しました。|
|ダウンロードしたドキュメント|DownloadDocument|ユーザーが、レビュー セットからドキュメントをダウンロードしました。|
|タグの編集|UpdateTag|ユーザーが、レビュー セット内のタグを変更しました。|
|レビュー セットからのドキュメントのエクスポート|ExportJob|ユーザーが、レビュー セットからドキュメントをエクスポートしました。|
|ケースの設定の変更|UpdateCaseSettings|ユーザーがケースの設定を変更しました。 ケースの設定には、ケース情報、アクセス許可、検索と分析の動作を制御する設定などがあります。|
|レビュー セット検索の変更|UpdateWorkingSetSearch|ユーザーが、レビュー セット内の検索クエリを編集しました。|
|レビュー セット検索のプレビュー|PreviewWorkingSetSearch|ユーザーが、レビュー セット内で検索クエリの結果をプレビューしました。|
|エラー ドキュメントの修復|ErrorRemediationJob|ユーザーが、インデックス作成エラーを含むファイルを修正しました。|
|ドキュメントのタグ付け|TagFiles|ユーザーが、レビュー セット内のドキュメントにタグを付けました。|
|クエリ結果のタグ付け|TagJob|ユーザーが、レビュー セット内の、検索クエリの条件に一致するすべてのドキュメントにタグを付けました。|
|レビュー セット内ドキュメントの表示|ViewDocument|ユーザーが、レビュー セット内のドキュメントを表示しました。|
|||

## <a name="ediscovery-cmdlet-activities"></a>電子情報開示コマンドレットのアクティビティ

次の表に、管理者またはユーザーがコンプライアンス センターを使用するか、セキュリティ & コンプライアンス センター PowerShell で対応するコマンドレットを実行して、電子情報開示関連のアクティビティを実行するときにログに記録されるコマンドレット監査ログ レコードを示します。 監査ログ レコードの詳細情報は、この表に一覧されているコマンドレットのアクティビティとは異なります。電子情報開示アクティビティは、前述のセクションに示されています。
  
前に述べたように、電子情報開示コマンドレットのアクティビティが監査ログの検索結果に表示されるには、最大で 24 時間かかる場合があります。
  
> [!TIP]
> 次の表の「**操作**」列のコマンドレットは、TechNet の対応するコマンドレットのヘルプ トピックにリンクされています。 各コマンドレットに使用可能なパラメーターの説明については、コマンドレットのヘルプ トピックを参照してください。 コマンドレットで使用されたパラメーターとパラメーター値は、ログに記録された、各電子情報開示コマンドレッド アクティビティの監査ログ エントリに含まれています。 
  
|**フレンドリ名**|**操作 (コマンドレット)**|**説明**|
|:-----|:-----|:-----|
|電子情報開示ケースで保留が作成されました  <br/> |[New-CaseHoldPolicy](/powershell/module/exchange/new-caseholdpolicy) <br/> |電子情報開示ケースの保留が作成されました。 保留は、コンテンツ ソースを指定してもしなくても作成できます。 コンテンツ ソースを指定すると、監査ログ エントリで識別されます。  <br/> |
|電子情報開示ケースから保留が削除されました  <br/> |[Remove-CaseHoldPolicy](/powershell/module/exchange/remove-caseholdpolicy) <br/> |電子情報開示ケースに関連付けられた保留が削除されました。 保留を削除すると、コンテンツのすべての場所が保留から解放されます。 また、保留を削除すると、その保留に関連付けられたケースの保留ルールも削除されます (下記の **Remove-CaseHoldRule** を参照)。  <br/> |
|電子情報開示ケースで保留が変更されました  <br/> |[Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) <br/> |電子情報開示ケースに関連付けられた保留が変更されました。 発生する可能性のある変更としては、コンテンツの場所の追加または削除、保留のオフ (無効化) があります。  <br/> |
|電子情報開示ケースの保留に対する検索クエリが作成されました  <br/> |[New-CaseHoldRule](/powershell/module/exchange/new-caseholdrule) <br/> |電子情報開示ケースに関連付けられたクエリベースの保留が作成されました。  <br/> |
|電子情報開示ケースの保留に対する検索クエリが削除されました  <br/> |[Remove-CaseHoldRule](/powershell/module/exchange/remove-caseholdrule) <br/> |電子情報開示ケースに関連付けられたクエリベースの保留が削除されました。 多くの場合、保留リストからのクエリの削除は、保留を削除した結果として発生します。 保留または保留クエリを削除する場合、保留中だったコンテンツの場所は解放されます。  <br/> |
|電子情報開示ケースの保留に対する検索クエリが変更されました  <br/> |[Set-CaseHoldRule](/powershell/module/exchange/set-caseholdrule) <br/> |電子情報開示ケースに関連付けられたクエリベースの保留が変更されました。 発生する可能性のある変更としては、クエリの編集、クエリベースの保留の日付範囲の編集があります。  <br/> |
|電子情報開示ケースが作成されました  <br/> |[New-ComplianceCase](/powershell/module/exchange/new-compliancecase) <br/> |電子情報開示ケースが作成されました。 ケースを作成する際に必要な操作は、名前を付けることだけです。 メンバーの追加、保留の作成、ケースに関連付けられたコンテンツ検索の作成などの他のケース関連のタスクにより、追加のイベントがログに記録されます。  <br/> |
|電子情報開示ケースが削除されました  <br/> |[Remove-ComplianceCase](/powershell/module/exchange/remove-compliancecase) <br/> |電子情報開示ケースが削除されました。 ケースを削除する前に、ケースに関連付けられた保留をすべて削除する必要があります。  <br/> |
|電子情報開示ケースが変更されました  <br/> |[Set-ComplianceCase](/powershell/module/exchange/set-compliancecase) <br/> |電子情報開示ケースが変更されました。 変更としては、開いているケースを閉じる、閉じたケースを再度開くなどがあります。  <br/> |
|電子情報開示ケースにメンバーが追加されました  <br/> |[Add-ComplianceCaseMember](/powershell/module/exchange/add-compliancecasemember) <br/> |ユーザーが電子情報開示ケースのメンバーとして追加されました。 ケースのメンバーとしてユーザーは、必要なアクセス許可が割り当てられているかどうかに応じて、ケース関連のさまざまなタスクを実行できます。  <br/> |
|電子情報開示ケースからメンバーが削除されました  <br/> |[Remove-ComplianceCaseMember](/powershell/module/exchange/remove-compliancecasemember) <br/> |ユーザーが、電子情報開示ケースのメンバーから削除されました。  <br/> |
|電子情報開示ケースのメンバーシップが変更されました  <br/> |[Update-ComplianceCaseMember](/powershell/module/exchange/update-compliancecasemember) <br/> |電子情報開示ケースのメンバーシップ リストが変更されました。 このアクティビティは、すべてのメンバーが新しいユーザーのグループに置き換えられたときにログに記録されます。 1 人のメンバーが追加または削除されると、**Add-ComplianceCaseMember** または **Remove-ComplianceCaseMember** 操作がログに記録されます。  <br/> |
|コンテンツ検索が作成されました  <br/> |[New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch) <br/> |新しいコンテンツ検索が作成されました。  <br/> |
|コンテンツ検索が削除されました  <br/> |[Remove-ComplianceSearch](/powershell/module/exchange/remove-compliancesearch) <br/> |既存のコンテンツ検索が削除されました。  <br/> |
|コンテンツ検索が変更されました  <br/> |[Set-ComplianceSearch](/powershell/module/exchange/set-compliancesearch) <br/> |既存のコンテンツの検索が変更されました。 変更としては、検索されるコンテンツの場所の追加または削除、検索クエリの編集などがあります。  <br/> |
|コンテンツ検索が開始されました  <br/> |[Start-ComplianceSearch](/powershell/module/exchange/start-compliancesearch) <br/> |コンテンツ検索が開始されました。 コンプライアンス センターの GUI を使用してコンテンツ検索を作成または変更すると、自動的に検索が開始されます。 **New-ComplianceSearch** または **Set-ComplianceSearch** コマンドレットを使用して検索を作成または変更する場合、**Start-ComplianceSearch** コマンドレットを実行して検索を開始する必要があります。  <br/> |
|コンテンツ検索が停止されました  <br/> |[Stop-ComplianceSearch](/powershell/module/exchange/stop-compliancesearch) <br/> |実行中だったコンテンツ検索が停止されました。  <br/> |
|コンテンツ検索アクションが作成されました  <br/> |[New-ComplianceSearchAction](/powershell/module/exchange/new-compliancesearchaction) <br/> |コンテンツ検索アクションが作成されました。 コンテンツ検索アクションには、検索結果のプレビュー、検索結果のエクスポート、Advanced eDiscovery で分析するための検索結果の準備、コンテンツ検索の検索条件と一致するアイテムの完全な削除などがあります。  <br/> |
|コンテンツ検索アクションが削除されました  <br/> |[Remove-ComplianceSearchAction](/powershell/module/exchange/remove-compliancesearchaction) <br/> |コンテンツ検索アクションが削除されました。  <br/> |
|検索のアクセス許可フィルターが作成されました  <br/> |[New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter) <br/> |検索のアクセス許可フィルターが作成されました。  <br/> |
|検索のアクセス許可フィルターが削除されました  <br/> |[Remove-ComplianceSecurityFilter](/powershell/module/exchange/remove-compliancesecurityfilter) <br/> |検索のアクセス許可フィルターが削除されました。  <br/> |
|検索のアクセス許可フィルターが変更されました  <br/> |[Set-ComplianceSecurityFilter](/powershell/module/exchange/set-compliancesecurityfilter) <br/> |検索のアクセス許可フィルターが変更されました。  <br/> |
|電子情報開示管理者が作成されました  <br/> |[Add-eDiscoveryCaseAdmin](/powershell/module/exchange/add-ediscoverycaseadmin) <br/> |ユーザーが、組織の電子情報開示管理者として追加されました。  <br/> |
|電子情報開示管理者が削除されました  <br/> |[Remove-eDiscoveryCaseAdmin](/powershell/module/exchange/remove-ediscoverycaseadmin) <br/> |電子情報開示管理者が組織から削除されました。  <br/> |
|電子情報開示管理者のメンバーシップが変更されました  <br/> |[Update-eDiscoveryCaseAdmin](/powershell/module/exchange/update-ediscoverycaseadmin) <br/> |組織の電子情報開示管理者のリストが変更されました。 このアクティビティは、電子情報開示管理者が新しいユーザーのグループに置き換えられた場合にログに記録されます。 1 人のユーザーが追加または削除された場合、**Add-eDiscoveryCaseAdmin** または **Remove-eDiscoveryCaseAdmin** 操作がログに記録されます。  <br/> |
|(なし)|[Get-ComplianceCase](/powershell/module/exchange/get-compliancecase) <br/>|このアクティビティは、ユーザーがコア電子情報開示の一覧を表示した場合、またはサポート案件Advanced eDiscoveryされます。 ユーザーが Core 電子情報開示で特定のケースを表示すると、このアクティビティもログに記録されます。 ユーザーが特定のケースを表示すると、監査レコードには、表示されたケースの ID が含まれます。 ユーザーがケースのリストのみを表示した場合、監査レコードにはケース ID は含めされません。|
|(なし)|[Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch)|このアクティビティは、ユーザーがコア電子情報開示ケースに関連付けられたコンテンツ検索または検索の一覧を表示した場合に記録されます。 このアクティビティは、ユーザーが特定のコンテンツ検索を表示したり、コア電子情報開示ケースに関連付けられた特定の検索を表示したりした場合にもログに記録されます。 ユーザーが特定の検索を表示すると、監査レコードには、表示された検索の ID が含まれます。 ユーザーが検索の一覧のみを表示した場合、監査レコードには検索 ID は含めされません。
|(なし)|[Get-ComplianceSearchAction](/powershell/module/exchange/get-compliancesearchaction)|このアクティビティは、ユーザーがコンプライアンス検索アクションの一覧 (エクスポート、プレビュー、パージなど) または Core 電子情報開示ケースに関連付けられたアクションを表示した場合に記録されます。 このアクティビティは、ユーザーが特定のコンプライアンス検索アクション (エクスポートなど) を表示したり、Core 電子情報開示ケースに関連付けられた特定のアクションを表示したりするときにもログに記録されます。 ユーザーが検索アクションを表示すると、監査レコードには、表示された検索アクションの ID が含まれます。 ユーザーがアクションの一覧のみを表示した場合、監査レコードにはアクション ID は含めされません。|
||||

## <a name="detailed-properties-for-ediscovery-activities"></a>電子情報開示アクティビティの詳細なプロパティ

次の表は、検索結果にリストされた電子情報開示アクティビティの [**詳細**] ページで [**詳細情報**] をクリックしたときに含まれるプロパティについて説明しています。 これらのプロパティは、監査ログの検索結果をエクスポートしたときに、CSV ファイルにも含まれます。 電子情報開示アクティビティの監査ログ記録には、以下にリストされている詳細なプロパティがすべて含まれているわけではありません。
  
> [!TIP]
> 検索結果をエクスポートすると、CSV ファイルには、[**詳細**] という名前の列が作成され、この列には、次の表の複数値プロパティで説明される詳細プロパティが含まれます。 Excel の Power Query 機能を使用して、この列を複数の列に分割して、プロパティごとに個別の列を設定することができます。 このようにすると、これらの 1 つ以上のプロパティで並べ替えやフィルター処理を行うことができます。 詳細については、「[監査ログを検索する](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file)」の「検索結果をファイルにエクスポートする」セクションを参照してください。 
  
|**Property**|**説明**|
|:-----|:-----|
|ケース  <br/> |作成、変更、または削除された電子情報開示ケースの ID (GUID)。  <br/> |
|ClientApplication  <br/> |電子情報開示アクティビティ コマンドレッドは、このプロパティの値が **EMC** です。 これは、コンプライアンス センターの GUI を使用するか、PowerShell でコマンドレットを実行してアクティビティが実行されたかどうかを示します。  <br/> |
|ClientIP  <br/> |アクティビティがログ記録されたときに使用されたデバイスの IP アドレス。IP アドレスは IPv4 または IPv6 のアドレス形式で表示されます。  <br/> |
|ClientRequestId  <br/> | 電子情報開示アクティビティの場合、このプロパティは通常空白です。  <br/> |
|CmdletVersion  <br/> |組織内で実行されているコンプライアンス センターのバージョンのビルド番号。  <br/> |
|CreationTime  <br/> |電子情報開示アクティビティが実行されたときの協定世界時 (UTC) の日付と時刻。  <br/> |
|EffectiveOrganization  <br/> |Microsoft 365 組織の名前。  <br/> |
|ExchangeLocations  <br/> |コンテンツ検索に含まれるか、電子情報開示ケースで保留にされている Exchange Online のメールボックス。  <br/> |
|Exclusions  <br/> |コンテンツ検索または電子情報開示ケースの保留から除外されているメールボックスまたはサイトの場所。  <br/> |
|ExtendedProperties  <br/> |アクティビティが実行されたときに使用されたオブジェクト GUID、対応するコマンドレット、コマンドレット パラメーターなど、コンテンツ検索、コンテンツ検索アクション、または電子情報開示ケースの保留の追加プロパティ。  <br/> |
|ID  <br/> |レポート エントリの ID。 ID は、監査ログ エントリを一意に識別します。  <br/> |
|NonPIIParameters  <br/> |Operation プロパティで識別されるコマンドレットで使用されたパラメーターの一覧 (値はリストされません)。 このプロパティにリストされるパラメーターは、Parameters プロパティでリストされるパラメーターと同じです。  <br/> |
|ObjectId  <br/> |Operation プロパティにリストされているアクティビティによって作成、アクセス、変更、または削除されたオブジェクト (コンテンツ検索やコア電子情報開示ケースなど) の GUID または名前。 また、このオブジェクトは、監査ログの検索結果のアイテム列でも識別されます。  <br/> |
|ObjectType  <br/> |ユーザーが作成、削除、変更した電子情報開示オブジェクトの種類。たとえば、コンテンツ検索アクション (プレビュー、エクスポート、または消去)、電子情報開示ケース、またはコンテンツ検索。  <br/> |
|Operation  <br/> |実行された電子情報開示アクティビティに対応する操作の名前。  <br/> |
|OrganizationId  <br/> |Microsoft 365 組織の GUID。  <br/> |
|パラメーター  <br/> |対応するコマンドレットで使用されたパラメーターの名前と値。  <br/> |
|PublicFolderLocations  <br/> |コンテンツ検索に含まれるか、電子情報開示ケースで保留にされている Exchange Online のパブリック フォルダーの場所。  <br/> |
|Query  <br/> |コンテンツ検索やクエリ ベース保留など、アクティビティに関連付けられた検索クエリ。  <br/> |
|RecordType  <br/> |レコードによって示される操作の種類。 値 **18** は、「[電子情報開示コマンドレットのアクティビティ](#ediscovery-cmdlet-activities)」セクションに一覧されているアクティビティに関連するイベントを示しています。 値 **24** は、「[電子情報開示のアクティビティ](#how-to-search-for-and-view-ediscovery-activities)」セクションに一覧されているアクティビティに関連するイベントを示しています。  <br/> |
|ResultStatus  <br/> |(Operation プロパティで指定された) アクションが正常に終了したかどうかどうかを示します。  <br/> |
|SecurityComplianceCenterEventType  <br/> |アクティビティがコンプライアンス センター イベントだったかどうかを示します。 電子情報開示アクティビティはすべて、このプロパティの値が **0** です。  <br/> |
|SharepointLocations  <br/> |コンテンツ検索に含まれるか、電子情報開示ケースで保留にされている SharePoint Online サイト。  <br/> |
|StartTime  <br/> |電子情報開示アクティビティが開始されたときの協定世界時 (UTC) の日付と時刻。  <br/> |
|UserId  <br/> |結果としてログ記録されているレコードが生成されたアクティビティ (Operation プロパティで指定された) を実行したユーザー。 システム アカウント (NT AUTHORITY\SYSTEM など) によって実行された電子情報開示アクティビティのレコードも監査ログに含まれます。  <br/> |
|UserKey  <br/> |UserId プロパティで識別されるユーザーの別の ID。 電子情報開示アクティビティの場合、このプロパティの値は通常、UserId プロパティと同じです。  <br/> |
|UserServicePlan  <br/> |組織で使用されているサブスクリプション。 電子情報開示アクティビティの場合、このプロパティは通常空白です。  <br/> |
|UserType  <br/> |操作を実行したユーザーの種類。次の値は、ユーザーの種類を指定します。  <br/> 0   正規ユーザー。 2   組織の管理者。 3   Microsoft データセンター管理者またはデータセンターのシステム アカウント。 4   システム アカウント。 5   アプリケーション。 6   サービス プリンシパル。 |
|バージョン  <br/> |ログに記録されるアクティビティ (Operation プロパティで識別) のバージョン番号を示します。  <br/> |
|Workload  <br/> |アクティビティが発生したサービス。 電子情報開示アクティビティの場合、この値は、**SecurityComplianceCenter** です。  <br/> |
