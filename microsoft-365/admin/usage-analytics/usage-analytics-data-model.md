---
title: Microsoft 365 利用状況分析データ モデル
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 08c5307c-4a6b-4761-8410-a6c96725760f
description: '使用状況分析が API に接続する方法と、さまざまなサービスの使用状況の毎月の傾向Microsoft 365します。  '
ms.openlocfilehash: 2f271414f515d2c3a86c6e59d64dc62f44f8ef01
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59178343"
---
# <a name="microsoft-365-usage-analytics-data-model"></a>Microsoft 365 利用状況分析データ モデル

## <a name="data-for-the-microsoft-365-usage-analytics-tables"></a>使用状況分析テーブルMicrosoft 365データ

Microsoft 365分析は、多次元データ モデルを公開する API に接続します。 使用状況分析がデータMicrosoft 365に使用する API は、一般に使用できるさまざまな API Graphです。 使用状況分析 API Microsoft 365自体の関数は、一般に使用できません。
  
> [!NOTE]
> 詳細については[、「Microsoft Microsoft 365での使用状況レポートの操作」を参照Graph。](/graph/api/resources/report) 
  
この API は、さまざまなサービスの使用状況の毎月の傾向に関するMicrosoft 365します。 API によって返される厳密なデータについては、次のセクションの表を参照してください。
  
## <a name="data-tables-returned-by-the-microsoft-365-reporting-api"></a>レポート API から返されるMicrosoft 365テーブル

|**テーブル名**|**テーブル内の情報**|**日付範囲**|
|:-----|:-----|:-----|
|Tenant Product Usage (テナント製品の利用状況)  <br/> |有効ユーザー、アクティブ ユーザー、月次保持ユーザー、初回ユーザー、および累積アクティブ ユーザーの月次合計が含まれる。  <br/> |12 か月連続の期間 (現在のところ、まだ終わっていない月を含む) の月次集計データが含まれています。  <br/> |
|Tenant Product Activity (テナント製品のアクティビティ)  <br/> |製品内のさまざまなアクティビティのアクティビティとアクティブ ユーザー数の月次合計が含まれる。  <br/> このデータ表で返される、ある製品内のアクティビティに関する情報については、[アクティブ ユーザーの定義](active-user-in-usage-reports.md)に関するページを参照してください。  <br/> |12 か月連続の期間 (現在のところ、まだ終わっていない月を含む) の月次集計データが含まれています。  <br/> |
|Tenant Office Licenses (テナントの Office ライセンス)  <br/> |ユーザーに割り当てられている Microsoft Office サブスクリプションの数に関するデータが含まれています。  <br/> |現在の部分月を含む、ローリング 12 か月の期間の月の終わりの状態データを格納します。  <br/> |
|Tenant Mailbox Usage (テナント メールボックスの利用状況)  <br/> |ユーザーのメールボックスに関するデータを含み、メールボックスの総数と記憶域の使用方法を示します。  <br/> |現在の部分月を含む、ローリング 12 か月の期間の月の終わりの状態データを格納します。  <br/> |
|Tenant Client Usage (テナント クライアントの利用状況)  <br/> |Exchange Online、Skype for Business、Yammer への接続に特定のクライアント/デバイスを使用しているユーザーの数に関するデータが含まれています。  <br/> |12 か月連続の期間 (現在のところ、まだ終わっていない月を含む) の月次集計データが含まれています。  <br/> |
|Tenant SharePoint Online Usage (テナント SharePoint オンラインの利用状況)  <br/> |SharePoint サイト、サイトの合計数などの含まれるチームまたはグループ、サイトのドキュメントの数、アクティビティ タイプ別のファイル数、使用しているストレージに関するデータが含まれています。  <br/> |現在の部分月を含む、ローリング 12 か月の期間の月の終わりの状態データを格納します。  <br/> |
|Tenant OneDrive for Business Usage (テナントの OneDrive for Business の利用状況)  <br/> |アカウントの数、OneDrive 全体のドキュメントの数、使用されているストレージ、アクティビティの種類別のファイル数などの OneDrive アカウントに関するデータが含まれています。  <br/> |現在の部分月を含む、ローリング 12 か月の期間の月の終わりの状態データを格納します。  <br/> |
|テナント Microsoft 365 グループの使用状況  <br/> |メールボックス、グループ、Microsoft 365など、グループの使用状況に関するデータSharePoint含Yammer。  <br/> |現在の部分月を含む、ローリング 12 か月の期間の月の終わりの状態データを格納します。  <br/> |
|Tenant Office Activation (テナントの Office ライセンス認証)  <br/> |Office サブスクリプションのライセンス認証数、デバイスごとのライセンス認証数 (Android/iOS/Mac/PC)、サービス プラン別のライセンス認証 (Microsoft 365 Apps for enterprise、Visio、Project など) に関するデータが含まれる。  <br/> |現在の部分月を含む、ローリング 12 か月の期間の月の終わりの状態データを格納します。  <br/> |
|User State (ユーザーの状態)  <br/> |ユーザーの表示名、割り当てられた製品、場所、部署、役職、会社など、ユーザーに関するメタデータが含まれます。 このデータは、最後の完全な月にライセンスが割り当てられたユーザーに関するデータです。 すべてのユーザーは、ユーザー ID によって一意に表されます。  <br/> |このデータは、完了した最後の月にライセンスを割り当てられたユーザーに関するものです。  <br/> |
|User Activity (ユーザー アクティビティ)  <br/> |ライセンスを取得したユーザーが実行したアクティビティに関するユーザーごとの情報が含まれています。  <br/> このデータ表で返される、ある製品内のアクティビティに関する情報については、[アクティブ ユーザーの定義](active-user-in-usage-reports.md)に関するページを参照してください。  <br/> |このデータは、完了した最後の月の間、何らかのサービスでアクティビティを実行したユーザーに関するものです。  <br/> |
   
各データ テーブルの詳細情報を表示するには、次のセクションを展開します。
  
### <a name="data-table---user-state"></a>データ テーブル - User State (ユーザーの状態)

次の表は、最後の完全な月にライセンスが割り当てられているすべてのユーザーのユーザー レベルの詳細を示します。 Azure Active Directory からデータが得られます。
  
|**列名**|**列の説明**|
|:-----|:-----|
|UserId  <br/> |ユーザーを表し、データ セット内の他のデータ テーブルとの結合を有効にする一意のユーザー ID。  <br/> |
|Timeframe  <br/> |この表のデータが属する月を表す値です。  <br/> |
|UPN  <br/> |ユーザー プリンシパル名のことであり、他の外部データ ソースと結合できるよう、ユーザーを一意に識別します。  <br/> |
|DisplayName  <br/> |ユーザーの表示名。  <br/> |
|IDType  <br/> |ID の種類は、ユーザーが Yammer ID を使用して接続する Yammer ユーザーの場合は 1 に、Yammer に接続する場合は Microsoft 365 ID を使用して接続する場合は 0 に設定されます。  <br/> 値は 1 で、このユーザーが自分の id ではなく、Yammer ID Yammerに接続Microsoft 365します。  <br/> |
|HasLicenseEXO  <br/> |ユーザーにライセンスが割り当てられており、Exchange を使用できる場合は、true に設定します。  <br/> |
|HasLicenseODB  <br/> |ユーザーにライセンスが割り当てられており、OneDrive for Business を使用できる場合は、true に設定します。  <br/> |
|HasLicenseSPO  <br/> |ユーザーにライセンスが割り当てられており、SharePoint Online を使用できる場合は、true に設定します。  <br/> |
|HasLicenseYAM  <br/> |ユーザーにライセンスが割り当てられており、Yammer を使用できる場合は、true に設定します。  <br/> |
|HasLicenseSFB  <br/> |ユーザーにライセンスが割り当てられており、Skype For Business を使用できる場合は、true に設定します。  <br/> |
|HasLicenseTeams  <br/> |ユーザーにライセンスが割り当てられている場合は true に設定し、ユーザーがライセンスを使用Microsoft Teams。  <br/> |
|Company  <br/> |このユーザーの Azure Active Directory で表されている会社データです。  <br/> |
|Department  <br/> |このユーザーの Azure Active Directory で表されている部署データです。  <br/> |
|LocationCity  <br/> |このユーザーの Azure Active Directory で表されている都市データです。  <br/> |
|LocationCountry  <br/> |このユーザーの Azure Active Directory で表されている国データです。  <br/> |
|LocationState  <br/> |このユーザーの Azure Active Directory で表されている都道府県データです。  <br/> |
|LocationOffice  <br/> |ユーザーのオフィスです。  <br/> |
|Title  <br/> |このユーザーの Azure Active Directory で表されている役職データです。  <br/> |
|Deleted  <br/> |True の場合は、その最後の完全な月Microsoft 365からユーザーが削除されました。  <br/> |
|DeletedDate  <br/> |ユーザーがユーザーから削除されたMicrosoft 365。  <br/> |
|YAM_State  <br/> |システム内のユーザーのYammer、アクティブ、削除、または中断することができます。  <br/> |
|YAM_ActivationDate  <br/> |ユーザーが Yammer でアクティブ状態になった日付です。  <br/> |
|YAM_DeletionDate  <br/> |ユーザーが Yammer で削除済み状態になった日付です。  <br/> |
|YAM_SuspensionDate  <br/> |ユーザーが Yammer で中断状態になった日付です。  <br/> |
   
### <a name="data-table---user-activity"></a>データ テーブル - User Activity (ユーザー アクティビティ)

この表には、前月にいずれかのサービスでアクティビティを実行した各ユーザーに関するデータが含まれます。
  
|**列名**|**列の説明**|
|:-----|:-----|
|UserID  <br/> |ユーザーを表し、データ セット内の他のデータ テーブルとの結合を有効にする一意のユーザー ID。  <br/> |
|IDType  <br/> |ID の種類は、ユーザーが Yammer ID を使用して接続する Yammer ユーザーの場合は 1 に、Yammer に接続する場合は Microsoft 365 ID を使用して接続する場合は 0 に設定されます。  <br/> 値は 1 で、このユーザーが自分の id ではなく、Yammer ID Yammerに接続Microsoft 365します。  <br/> |
|Timeframe  <br/> |この表のデータが属する月を表す値です。  <br/> |
|EXO_EmailSent  <br/> |送信されたメールの数です。  <br/> |
|EXO_EmailReceived  <br/> |受信されたメールの数です。  <br/> |
|EXO_EmailRead  <br/> |ユーザーが実行した電子メールの読み取りアクティビティの数、既に読み取られたメール、または以前に受信した電子メールを複数回読み取る可能性があります。  <br/> |
|EXO_AppointmentCreated  <br/> |作成された予定の数。  <br/> |
|EXO_MeetingAccepted  <br/> |会議の受け入れ数。  <br/> |
|EXO_MeetingCancelled  <br/> |取り消された会議の数。  <br/> |
|EXO_MeetingDeclined  <br/> |会議の数が減少しました。  <br/> |
|EXO_MeetingSent  <br/> |送信された会議の数。  <br/> |
|ODB_FileViewedModified  <br/> |このユーザーがいずれかの OneDrive for Business で操作 (作成、更新、削除、表示、ダウンロードなど) したファイルの数です。  <br/> |
|ODB_FileSynched  <br/> |このユーザーがいずれかの OneDrive for Business で同期したファイルの数です。  <br/> |
|ODB_FileSharedInternally  <br/> |このユーザーが任意のユーザーから内部的に共有OneDrive for Businessグループ内のユーザー (外部ユーザーを含む可能性があります) の数。  <br/> |
|ODB_FileSharedExternally  <br/> |このユーザーがいずれかの OneDrive for Business から外部共有したファイルの数です。  <br/> |
|ODB_AccessedByOwner  <br/> |ユーザーが操作したサイトが、自分のサイトに存在するOneDrive for Business。  <br/> |
|ODB_AccessedByOthers  <br/> |このユーザーが操作した、別のユーザーのサイトに存在するサイトのOneDrive for Business。  <br/> |
|SPO_GroupFileViewedModified  <br/> |このユーザーが任意のグループ サイトで操作したファイルの数。  <br/> |
|SPO_GroupFileSynched  <br/> |このユーザーがグループ サイトで同期したファイルの数です。  <br/> |
|SPO_GroupFileSharedInternally  <br/> |組織内のユーザー、またはグループ内のユーザーと共有されたファイルの数 (外部ユーザーを含む場合があります)。  <br/> |
|SPO_GroupFileSharedExternally  <br/> |このユーザーがグループ サイトから外部共有したファイルの数です。  <br/> |
|SPO_GroupAccessedByOwner  <br/> |ユーザーが所有するグループ サイトに存在するユーザーが操作したサイトの数。  <br/> |
|SPO_GroupAccessedByOthers  <br/> |別のユーザーが所有するグループ サイトに存在する、ユーザーが操作したサイトの数。  <br/> |
|SPO_OtherFileViewedModified  <br/> |このユーザーが他のサイトで操作したファイルの数。  <br/> |
|SPO_OtherFileSynched  <br/> |このユーザーが他のサイトから同期したファイルの数。  <br/> |
|SPO_OtherFileSharedInternally  <br/> |このユーザーが他のサイトから内部的に共有したファイルの数、またはグループ内のユーザー (外部ユーザーを含む可能性があります) の数。 <br/> |
|SPO_OtherFileSharedExternally  <br/> |このユーザーが他のサイトから外部で共有したファイルの数。  <br/> |
|SPO_OtherAccessedByOwner  <br/> |ユーザーが操作したサイトが、自分が所有する他のサイトに存在するサイトの数。  <br/> |
|SPO_OtherAccessedByOthers  <br/> |別のユーザーが所有する他のサイトに存在する、ユーザーが操作したサイトの数。  <br/> |
|SPO_TeamFileViewedModified  <br/> |このユーザーがチーム サイトで対話したファイルの数です。  <br/> |
|SPO_TeamFileSynched  <br/> |このユーザーがチーム サイトで同期したファイルの数です。  <br/> |
|SPO_TeamFileSharedInternally  <br/> |このユーザーがチーム サイトから内部的に共有したファイルの数、またはグループ内のユーザー (外部ユーザーを含む可能性があります) の数。  <br/> |
|SPO_TeamFileSharedExternally  <br/> |このユーザーがチーム サイトから外部共有したファイルの数です。  <br/> |
|SPO_TeamAccessedByOwner  <br/> |ユーザーが操作したサイトが、自分が所有するチーム サイトに存在するサイトの数。  <br/> |
|SPO_TeamAccessedByOthers  <br/> |別のユーザーが所有するチーム サイトに存在する、ユーザーが操作したサイトの数。  <br/> |
|Teams_ChatMessages  <br/> |送信されたチャット メッセージの数。  <br/> |
|Teams_ChannelMessage  <br/> |チャネルに投稿されたメッセージの数。  <br/> |
|Teams_CallParticipate  <br/> |ユーザーが参加した呼び出しの数。  <br/> |
|Teams_MeetingParticipate  <br/> |ユーザーが参加した会議の数。  <br/> |
|Teams_HasOtherAction  <br/> |ユーザーが他のアクションを実行した場合のブールMicrosoft Teams。  <br/> |
|YAM_MessagePost  <br/> |このユーザーがYammerしたメッセージの数。  <br/> |
|YAM_MessageLiked  <br/> |このユーザーがYammerしたメッセージの数。  <br/> |
|YAM_MessageRead  <br/> |このユーザー Yammerメッセージの数。  <br/> |
|SFB_P2PSummary  <br/> |このユーザーが関わったピアツーピア セッションの数です。  <br/> |
|SFB_ConfOrgSummary  <br/> |このユーザーが編成した会議セッションの数です。  <br/> |
|SFB_ConfPartSummary  <br/> |このユーザーが参加した会議セッションの数です。  <br/> |

> [!NOTE]
> Teams_HasOtherActionは、ユーザーがアクティブと見なされますが、チャット メッセージ、1:1 通話、チャネル メッセージ、会議の合計、および会議の開催に対して 0 の値を持つという意味です。
   
### <a name="data-table---tenant-product-usage"></a>データ テーブル - Tenant Product Usage (テナント製品の利用状況)

次の表は、各製品の有効、アクティブ、復帰、および初回ユーザーの観点から、月次導入データをMicrosoft 365。 このMicrosoft 365は、いずれかの製品でのアクティブな使用状況を表します。
  
|**列名**|**列の説明**|
|:-----|:-----|
|製品  <br/> |使用の情報を要約する製品の名前です。 Microsoft 365列の値は、どの製品でもアクティビティを表します。  <br/> |
|Timeframe  <br/> |月の値。現在のところ、まだ完了していない月を含む、最後の 12 か月間に対して月別かつ製品ごとに 1 行割り当てられます。  <br/> |
|EnabledUsers  <br/> |ユーザーが月の一部に対して有効になっている場合、タイム フレーム値に対して製品を使用できるユーザーの数は、引き続きカウントされます。  <br/> |
|ActiveUsers  <br/> |タイム フレーム値の製品で意図的なアクティビティを実行したユーザーの数。  <br/> ユーザーは、製品で主要なアクティビティのいずれかを実行した場合、特定の月にその製品に対してアクティブとしてカウントされます。主要なアクティビティの一覧は、 **Tenant Product Activity** テーブルに示されています。  <br/> |
|CumulativeActiveUsers  <br/> |製品の使用が許可され、新しい利用状況システムでデータ回収が開始してから少なくとも 1 回は製品を使用したユーザーの数を時間枠の最大値まで累積したものです。  <br/> |
|MoMReturningUsers  <br/> |Timeframe の月でアクティブになっており、前月もアクティブであったユーザーの数です。  <br/> |
|FirstTimeUsers  <br/> |新しい利用状況システムのデータ回収以後、Timeframe で初めてアクティブになったユーザーの数です。  <br/> ユーザーは、この新しいレポート システムでのデータ収集開始以降初めてアクティビティが検出された場合に、特定の月の初めてのユーザーとしてカウントされます。 初回ユーザーとしてカウントされた後、このユーザーのアクティビティに大きなギャップがある場合でも、初回ユーザーとして再びカウントされることはありません。  <br/> |
|Content Date  <br/> |Timeframe が現在の月を示している場合、この値はデータが利用できる現在の月の最後の日付を表します。  <br/> Timeframe が前月を示している場合、この値は Timeframe の月の最後の日付を表します。  <br/> |
   
### <a name="data-table---tenant-product-activity"></a>データ テーブル - Tenant Product Activity (テナント製品のアクティビティ)

次の表は、製品内のさまざまなアクティビティのアクティビティとアクティブ ユーザー数の月次合計を示します。
  
|**列名**|**列の説明**|
|:-----|:-----|
|Timeframe  <br/> |月の値。現在のところ、まだ完了していない月を含む、最後の 12 か月間に対して月別かつ製品ごとに 1 行割り当てられます。  <br/> |
|Product  <br/> |使用データを使用できるMicrosoft 365内の製品の名前。  <br/> |
|Activity  <br/> |製品のアクティブな使用を示す、製品のアクティビティの名前です。  <br/> |
|ActivityCount  <br/> |これは、すべてのアクティブ ユーザーを対象に、製品内で実行されたアクティビティごとに数えられたアクションの合計数です。  <br/> **注:** SharePoint Online と OneDrive for Business の場合、この値はユーザーが対話した個々のドキュメントの数を表します。  <br/> |
|ActiveUserCount  <br/> |製品内でアクティビティを実行したユーザーの数です。  <br/> |
|TotalDurationInMinute  <br/> |該当する Skype for Business アクティビティで音声または動画による通話を行ったすべてのアクティブ ユーザーを対象とする通話時間 (分単位) です。  <br/> |
|Content Date  <br/> |Timeframe が現在の月を示している場合、この値はデータが利用できる現在の月の最後の日付を表します。  <br/> Timeframe が前月を示している場合、この値は Timeframe の月の最後の日付を表します。  <br/> |
   
### <a name="data-table---tenant-mailbox-usage"></a>データ テーブル - Tenant Mailbox Usage (テナント メールボックスの利用状況)

この表は、ユーザー メールボックスを持つすべてのライセンスユーザー Exchange Online概要データで構成されます。 すべてのユーザーのメールボックスの間での月末の状態が含まれています。 このテーブルのデータは、複数の月の間で追加されることはありません。 このテーブルの最後の月のデータは、最新の状態を表します。
  
|**列名**|**列の説明**|
|:-----|:-----|
|TotalMailboxes  <br/> |サブスクリプションのユーザー Microsoft 365数。  <br/> |
|IssueWarningQuota  <br/> |すべてのユーザーのメールボックスで警告を発行する合計クォータ。  <br/> |
|ProhibitSendQuota  <br/> |すべてのユーザー メールボックスを対象に送信を禁止するための割り当てられる合計容量です。  <br/> |
|ProhibitSendReceiveQuota  <br/> |すべてのユーザー メールボックスを対象に送受信を禁止するための割り当てられる合計容量です。  <br/> |
|TotalItemBytes  <br/> |すべてのユーザー メールボックスで使用されている記憶域の量です (バイト単位)。  <br/> |
|MailboxesNoWarning  <br/> |記憶域の警告の制限下にあったユーザーのメールボックスの数です。  <br/> |
|MailboxesIssueWarning  <br/> |記憶域のクォータに対して警告が発行されたユーザーのメールボックスの数です。  <br/> |
|MailboxesExceedSendQuota  <br/> |送信クォータを超えていたユーザーのメールボックスの数です。  <br/> |
|MailboxesExceedSendReceiveQuota  <br/> |送受信クォータを超えたユーザー メールボックスの数。  <br/> |
|DeletedMailboxes  <br/> |Timeframe で削除されているユーザー メールボックスの数です。  <br/> |
|Timeframe  <br/> |月の値。  <br/> |
|Content Date  <br/> |Timeframe が現在の月を示している場合、この値はデータが利用できる現在の月の最後の日付を表します。  <br/> Timeframe が前月を示している場合、この値は Timeframe の月の最後の日付を表します。  <br/> |
   
### <a name="data-table---tenant-client-usage"></a>データ テーブル - Tenant Client Usage (テナント クライアントの使用状況)

次の表は、ユーザーがユーザーに接続するために使用しているクライアントに関する月次の概要データを示Exchange Online、Skype for Business、Yammer。 このテーブルには、SharePoint Online と OneDrive for Business のクライアントの使用状況データはまだありません。
  
|**列名**|**列の説明**|
|:-----|:-----|
|製品  <br/> |クライアント使用状況データが使用可能Microsoft 365内の製品の名前。  <br/> |
|ClientId  <br/> |製品への接続に使用する各デバイスの名前です。  <br/> |
|UserCount  <br/> |各クライアントを使用したユーザーの製品別の数です。  <br/> |
|Timeframe  <br/> |月の値  <br/> |
|Content Date  <br/> |Timeframe が現在の月を示している場合、この値はデータが利用できる現在の月の最後の日付を表します。  <br/> Timeframe が前月を示している場合、この値は Timeframe の月の最後の日付を表します。  <br/> |
   
### <a name="data-table---tenant-sharepoint-online-usage"></a>データ テーブル - Tenant SharePoint Online Usage (テナント SharePoint オンラインの利用状況)

この表は、オンライン サイトの利用状況またはアクティビティに関する月の月SharePoint構成されています。 これは、チーム サイトとグループ サイトのみを対象とします。 SharePoint Online サイトの月末の状態は、たとえば、ユーザーが 5 つのドキュメントを作成し、ストレージ全体に 10 MB を使用し、一部のファイルを削除し、ファイルの最後の状態が 5 MB の記憶域を使用する合計 7 つのファイルを追加した場合、この表で表される値は月の終わりの状態になります。 このテーブルは、集計の重複カウントを回避するために非表示にされ、2 つの参照テーブルを作成するソースとして使用されます。
  
|**列名**|**列の説明**|
|:-----|:-----|
|SiteType  <br/> |サイトの種類の値 (任意/チーム/グループ) (任意はこれら 2 つのサイトの種類のどちらかを表します)。  <br/> |
|TotalSites  <br/> |Timeframe の最後に存在していたサイトの数です。  <br/> |
|DocumentCount  <br/> |Timeframe の最後にサイトに存在していたドキュメントの数です。  <br/> |
|Diplansed  <br/> |Timeframe の最後にすべてのサイト全体で集計した使用済み記憶域の合計です。  <br/> |
|ActivityType  <br/> |ファイル アクティビティのさまざまな種類 (任意/アクティブなファイル/外部共有ファイル/内部共有ファイル/同期されているファイル) が記録されているサイトの数。  <br/> 実行されたファイル アクティビティを表します。  <br/> |
|SitesWithOwnerActivities  <br/> |サイトの所有者が自分のサイトで特定のファイル アクティビティを実行したアクティブ サイト数です。 サイトの所有者は、PowerShell コマンド **get-sposite から取得できます**。 これは、サイトの責任者です。   <br/> |
|SitesWithNonOwnerActivities  <br/> |サイトの所有者以外のユーザーがその月にサイトで特定のファイルのアクティビティを実行したアクティブ サイト数の合計です。 サイトの所有者は、PowerShell コマンド **get-sposite から取得できます**。 これは、サイトの責任者です。 <br/> |
|ActivityTotalSites  <br/> |その Timeframe でアクティビティを記録したサイトの数です。サイトで Timeframe の前半にアクティビティが存在し、Timeframe の終わりまでに削除された場合でも、その Timeframe のアクティブ サイトの合計で数えられます。  <br/> |
|Timeframe  <br/> |この列は、日付の値を持っています。予定表テーブルに対する多対 1 のリレーションシップとして使用されます。  <br/> |
|Content Date  <br/> |Timeframe が現在の月を示している場合、この値はデータが利用できる現在の月の最後の日付を表します。  <br/> Timeframe が前月を示している場合、この値は Timeframe の月の最後の日付を表します。  <br/> |
   
### <a name="data-table---tenant-onedrive-usage"></a>データ テーブル - テナントOneDrive利用状況

このテーブルでは、アカウント数、OneDrive アカウント全体のドキュメント数、使用されている記憶域、アクティビティの種類別のファイル数など、OneDrive アカウントに関するデータをまとめています。 このテーブルでは、OneDrive for Business アカウントの月末の状態が表されます。 たとえば、ユーザーが 10 MB のストレージを使用する 5 つのドキュメントを作成し、いくつかのファイルを削除し、さらにファイルを追加して、月末に 5 MB のストレージを使用する 7 つのファイルがある場合、月末の値は、この表で表されます。
  
|**列名**|**列の説明**|
|:-----|:-----|
|SiteType  <br/> |値は "OneDrive" です。  <br/> |
|TotalSites  <br/> |Timeframe の終わりに存在した OneDrive for Business アカウントの数です。  <br/> |
|DocumentCount  <br/> |Timeframe の終わりに OneDrive for Business アカウント全体で存在したドキュメントの合計数です。  <br/> |
|Diplansed  <br/> |時間枠の最後に、すべてのアカウントOneDrive合計された合計ストレージ。  <br/> |
|ActivityType  <br/> |ファイル アクティビティのさまざまな種類 (任意/アクティブなファイル/外部共有ファイル/内部共有ファイル/同期されているファイル) が記録されているアカウントの数です。  <br/> 任意の場合、実行されたいずれかのファイル アクティビティを表します。  <br/> |
|SitesWithOwnerActivities  <br/> |アカウントの所有者が自分のアカウントで特定のファイル アクティビティを実行した、アクティブな OneDrive for Business アカウントの数です。  <br/> |
|SitesWithNonOwnerActivities  <br/> |ファイル アクティビティがアカウントの所有者以外のユーザーによって実行された OneDrive for Business アカウントの数です。  <br/> |
|ActivityTotalSites  <br/> |Timeframe の間に記録された OneDrive for Business アカウントの数です。Timeframe の早い段階で OneDrive for Business アカウントでアクティビティが行われ、Timeframe の終わりまでに削除された場合でも、その Timeframe のアクティブな OneDrive for Business アカウントとして数えられます。  <br/> |
|Timeframe  <br/> |この列は、日付の値を持っています。予定表テーブルに対する多対 1 のリレーションシップとして使用されます。  <br/> |
|Content Date  <br/> |Timeframe が現在の月を示している場合、この値はデータが利用できる現在の月の最後の日付を表します。  <br/> Timeframe が前月を示している場合、この値は Timeframe の月の最後の日付を表します。  <br/> |
   
### <a name="data-table---tenant-microsoft-365-groups-usage"></a>データ テーブル - テナント Microsoft 365 グループの使用状況

次の表は、組織全体でMicrosoft 365グループの使用方法に関するデータを提供します。
  
****

|**列名**|**列の説明**|
|:-----|:-----|
|TimeFrame  <br/> |月の値。現在のところ、まだ完了していない月を含む、最後の 12 か月間に対して月別かつ製品ごとに 1 行割り当てられます。  <br/> |
|GroupType  <br/> |グループの種類 (プライベート/パブリック/any)。  <br/> |
|TotalGroups  <br/> |各グループの種類のグループの数。  <br/> |
|ActiveGroups  <br/> |アクティブ なグループの数。  <br/> |
|MBX_TotalGroups  <br/> |メールボックス グループの数。  <br/> |
|MBX_ActiveGroups  <br/> |アクティブなメールボックス グループの数。  <br/> |
|MBX_TotalActivities  <br/> |メールボックス アクティビティの数。  <br/> |
|MBX_TotalItems  <br/> |メールボックス アイテムの数。  <br/> |
|MBX_StorageUsed  <br/> |使用されるメールボックス ストレージの量。  <br/> |
|SPO_TotalGroups  <br/> |グループSharePoint数。  <br/> |
|SPO_ActiveGroups  <br/> |アクティブなグループSharePoint数。  <br/> |
|SPO_FileAccessedActiveGroups  <br/> |ファイルにアクセスSharePointアクティビティを持つグループの数。  <br/> |
|SPO_FileSyncedActiveGroups  <br/> |ファイルの同期SharePointアクティビティを持つグループの数。  <br/> |
|SPO_FileSharedInternallyActiveGroups  <br/> |内部でSharePointを持つグループ、またはグループ (外部ユーザーを含む場合があります) を含むグループの数。  <br/> |
|SPO_FileSharedExternallyActiveGroups  <br/> |外部アクティビティSharePointしたグループの数。  <br/> |
|SPO_TotalActivities  <br/> |アクティビティSharePoint数。  <br/> |
|SPO_FileAccessedActivities  <br/> |ファイルにアクセスSharePointアクティビティの数。  <br/> |
|SPO_FileSyncedActivities  <br/> |ファイル同期SharePointアクティビティの数。  <br/> |
|SPO_FileSharedInternallyActivities  <br/> |ファイル共有SharePoint内部またはグループ (外部メンバーを含む) の数。  <br/> |
|SPO_FileSharedExternallyActivities  <br/> |外部で共有SharePointファイルの数。  <br/> |
|SPO_TotalFiles  <br/> |ファイルのSharePoint数。  <br/> |
|SPO_ActiveFiles  <br/> |アクティブなファイルSharePointします。  <br/> |
|SPO_StorageUsed  <br/> |使用されるストレージSharePoint量。  <br/> |
|YAM_TotalGroups  <br/> |グループの数Yammerします。  <br/> |
|YAM_ActiveGroups  <br/> |アクティブなグループYammer数。  <br/> |
|YAM_LikedActiveGroups  <br/> |アクティビティがYammerグループの数。  <br/> |
|YAM_PostedActiveGroups  <br/> |投稿アクティビティYammerグループの数。  <br/> |
|YAM_ReadActiveGroups  <br/> |読み取りYammerを持つグループの数。  <br/> |
|YAM_TotalActivities  <br/> |アクティビティYammer数。  <br/> |
|YAM_LikedActivities  <br/> |アクティビティYammer数。  <br/> |
|YAM_PostedActivties  <br/> |投稿アクティビティYammer数。  <br/> |
|YAM_ReadActivites  <br/> |読み取Yammerの数。  <br/> |

### <a name="data-table---tenant-office-licenses"></a>データ テーブル - テナント Office ライセンス

次の表に、ユーザーのライセンス割り当てに関する月次の概要データを示します。 
  
|**列名**|**列の説明**|
|:-----|:-----|
|LicenseName  <br/> |ライセンスの名前。  <br/> |
|AssignedCount  <br/> |割り当てられたライセンスの数。  <br/> |
|Timeframe  <br/> |月の値。  <br/> |

### <a name="data-table---tenant-office-activation"></a>データ テーブル - Tenant Office Activation(テナントの Office ライセンス認証)

この表には、サービス プラン全体の Office サブスクリプションライセンス認証の数に関するデータ (たとえば、Microsoft 365 Apps、エンタープライズ、Visio、Project) が示されています。 デバイス (Android/iOS/Mac/PC) 別のライセンス認証数に関するデータも提供します。
  
|**列名**|**列の説明**|
|:-----|:-----|
|ServicePlanName  <br/> |サービス プラン名の値とデバイス別のライセンス認証の数を一覧表示します。それぞれの説明は以下の列のようになります。  <br/> |
|TotalEnabled  <br/> |Timeframe の終わりまでに有効化されたユーザーの数をサービス プラン名別に示したものです。  <br/> |
|TotalActivatedUsers  <br/> |Timeframe の終わりまでに各サービス プランをライセンス認証したユーザーの数を示したものです。  <br/> |
|AndroidCount  <br/> |Timeframe の終わりまでのライセンス認証数を Android デバイスのサービス プランを対象に示したものです。  <br/> |
|iOSCount  <br/> |Timeframe の終わりまでのライセンス認証数を iOS デバイスのサービス プランを対象に示したものです。  <br/> |
|MacCount  <br/> |Timeframe の終わりまでのライセンス認証数を MAC デバイスのサービス プランを対象に示したものです。  <br/> |
|PcCount  <br/> |Timeframe の終わりまでのライセンス認証数を PC デバイスのサービス プランを対象に示したものです。  <br/> |
|WinRtCount  <br/> |Timeframe の終わりまでのライセンス認証数を Windows Mobile デバイスのサービス プランを対象に示したものです。  <br/> |
|Timeframe  <br/> |この列は、日付の値を持っています。予定表テーブルに対する多対 1 のリレーションシップとして使用されます。  <br/> |
|Content Date  <br/> |Timeframe が現在の月を示している場合、この値はデータが利用できる現在の月の最後の日付を表します。  <br/> Timeframe が前月を示している場合、この値は Timeframe の月の最後の日付を表します。  <br/> |
