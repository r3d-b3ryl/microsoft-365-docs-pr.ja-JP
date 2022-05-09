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
ms.localizationpriority: medium
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
description: '利用状況分析が API に接続し、さまざまなMicrosoft 365 サービスの使用状況の毎月の傾向を提供する方法について説明します。  '
ms.openlocfilehash: 013fdd75063ad8ad2489ebe43c9091f05f94c14c
ms.sourcegitcommit: 57211e8082a3429017ad33fe0e6bd9af203bb7ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2022
ms.locfileid: "62487277"
---
# <a name="microsoft-365-usage-analytics-data-model"></a>Microsoft 365 利用状況分析データ モデル

## <a name="data-for-the-microsoft-365-usage-analytics-tables"></a>Microsoft 365利用状況分析テーブルのデータ

Microsoft 365利用状況分析は、多次元データ モデルを公開する API に接続します。 利用状況分析Microsoft 365使用してデータを生成する API は、一般に利用可能なさまざまなGraph API から取得されます。 Microsoft 365利用状況分析 API の機能自体は一般公開されていません。
  
> [!NOTE]
> 詳細については、「[Microsoft GraphでのMicrosoft 365使用状況レポートの操作](/graph/api/resources/report)」を参照してください。 
  
この API は、さまざまなMicrosoft 365 サービスの使用状況の月次傾向に関する情報を提供します。 API によって返される厳密なデータについては、次のセクションの表を参照してください。
  
## <a name="data-tables-returned-by-the-microsoft-365-reporting-api"></a>Microsoft 365 Reporting API によって返されるデータ テーブル

|**テーブル名**|**テーブル内の情報**|**日付範囲**|
|:-----|:-----|:-----|
|Tenant Product Usage (テナント製品の利用状況)  <br/> |有効なアクティブ ユーザー、月単位の保持ユーザー、初回ユーザー、および累積アクティブ ユーザーの月単位の合計が含まれます。  <br/> |12 か月連続の期間 (現在のところ、まだ終わっていない月を含む) の月次集計データが含まれています。  <br/> |
|Tenant Product Activity (テナント製品のアクティビティ)  <br/> |製品内のさまざまなアクティビティに対するアクティビティとアクティブユーザー数の月次合計が含まれます。  <br/> このデータ表で返される、ある製品内のアクティビティに関する情報については、[アクティブ ユーザーの定義](active-user-in-usage-reports.md)に関するページを参照してください。  <br/> |12 か月連続の期間 (現在のところ、まだ終わっていない月を含む) の月次集計データが含まれています。  <br/> |
|Tenant Office Licenses (テナントの Office ライセンス)  <br/> |ユーザーに割り当てられている Microsoft Office サブスクリプションの数に関するデータが含まれています。  <br/> |現在の部分的な月を含む、ローリング 12 か月の期間の月末状態データが含まれます。  <br/> |
|Tenant Mailbox Usage (テナント メールボックスの利用状況)  <br/> |ユーザーのメールボックスに関するデータを格納し、メールボックスの合計数とストレージの使用方法を示します。  <br/> |現在の部分的な月を含む、ローリング 12 か月の期間の月末状態データが含まれます。  <br/> |
|Tenant Client Usage (テナント クライアントの利用状況)  <br/> |Exchange Online、Skype for Business、Yammer への接続に特定のクライアント/デバイスを使用しているユーザーの数に関するデータが含まれています。  <br/> |12 か月連続の期間 (現在のところ、まだ終わっていない月を含む) の月次集計データが含まれています。  <br/> |
|Tenant SharePoint Online Usage (テナント SharePoint オンラインの利用状況)  <br/> |SharePoint サイト、サイトの合計数などの含まれるチームまたはグループ、サイトのドキュメントの数、アクティビティ タイプ別のファイル数、使用しているストレージに関するデータが含まれています。  <br/> |現在の部分的な月を含む、ローリング 12 か月の期間の月末状態データが含まれます。  <br/> |
|Tenant OneDrive for Business Usage (テナントの OneDrive for Business の利用状況)  <br/> |アカウントの数、OneDrive 全体のドキュメントの数、使用されているストレージ、アクティビティの種類別のファイル数などの OneDrive アカウントに関するデータが含まれています。  <br/> |現在の部分的な月を含む、ローリング 12 か月の期間の月末状態データが含まれます。  <br/> |
|テナントMicrosoft 365 グループ使用状況  <br/> |メールボックス、SharePoint、Yammerなど、Microsoft 365 グループ使用状況に関するデータが含まれます。  <br/> |現在の部分的な月を含む、ローリング 12 か月の期間の月末状態データが含まれます。  <br/> |
|Tenant Office Activation (テナントの Office ライセンス認証)  <br/> |Officeサブスクリプションのアクティブ化の数、デバイスごとのアクティブ化の数 (Android/iOS/Mac/PC)、サービス プラン別のアクティブ化 (Microsoft 365 Apps for enterprise、Visio、Projectなど) に関するデータが含まれます。  <br/> |現在の部分的な月を含む、ローリング 12 か月の期間の月末状態データが含まれます。  <br/> |
|User State (ユーザーの状態)  <br/> |ユーザーの表示名、割り当てられた製品、場所、部署、役職、会社など、ユーザーに関するメタデータが含まれます。 このデータは、過去 1 か月間にライセンスが割り当てられたユーザーに関するものです。 すべてのユーザーは、ユーザー ID によって一意に表されます。  <br/> |このデータは、完了した最後の月にライセンスを割り当てられたユーザーに関するものです。  <br/> |
|User Activity (ユーザー アクティビティ)  <br/> |ライセンスを取得したユーザーが実行したアクティビティに関するユーザーごとの情報が含まれています。  <br/> このデータ表で返される、ある製品内のアクティビティに関する情報については、[アクティブ ユーザーの定義](active-user-in-usage-reports.md)に関するページを参照してください。  <br/> |このデータは、完了した最後の月の間、何らかのサービスでアクティビティを実行したユーザーに関するものです。  <br/> |
   
各データ テーブルの詳細情報を表示するには、次のセクションを展開します。
  
### <a name="data-table---user-state"></a>データ テーブル - User State (ユーザーの状態)

この表では、過去 1 か月間にライセンスが割り当てられているすべてのユーザーのユーザー レベルの詳細を示します。 Azure Active Directory からデータが得られます。
  
|**列名**|**列の説明**|
|:-----|:-----|
|UserId  <br/> |ユーザーを表し、データ セット内の他のデータ テーブルとの結合を有効にする一意のユーザー ID。  <br/> |
|Timeframe  <br/> |この表のデータが属する月を表す値です。  <br/> |
|UPN  <br/> |ユーザー プリンシパル名のことであり、他の外部データ ソースと結合できるよう、ユーザーを一意に識別します。  <br/> |
|DisplayName  <br/> |ユーザーの表示名。  <br/> |
|IDType  <br/> |ID の種類は、ユーザーがYammer ID を使用して接続するYammer ユーザーの場合は 1、Microsoft 365 ID を使用してYammerに接続する場合は 0 に設定されます。  <br/> 値は、このユーザーがMicrosoft 365 ID ではなく、Yammer ID を使用してYammerに接続することを表す 1 です。  <br/> |
|HasLicenseEXO  <br/> |ユーザーにライセンスが割り当てられ、月の最終日にExchangeを使用できる場合は true に設定します。  <br/> |
|HasLicenseODB  <br/> |ユーザーにライセンスが割り当てられ、月の最終日にOneDrive for Businessを使用できる場合は true に設定します。  <br/> |
|HasLicenseSPO  <br/> |ユーザーにライセンスが割り当てられ、月の最終日に SharePoint Online の使用が有効になっている場合は true に設定します。  <br/> |
|HasLicenseYAM  <br/> |ユーザーにライセンスが割り当てられ、月の最終日にYammerを使用できる場合は true に設定します。  <br/> |
|HasLicenseSFB  <br/> |ユーザーにライセンスが割り当てられ、Skype For Business を月の最終日に使用できる場合は true に設定します。  <br/> |
|HasLicenseTeams  <br/> |ユーザーにライセンスが割り当てられ、月の最終日にMicrosoft Teamsを使用できるようにする場合は true に設定します。  <br/> |
|Company  <br/> |このユーザーの Azure Active Directory で表されている会社データです。  <br/> |
|Department  <br/> |このユーザーの Azure Active Directory で表されている部署データです。  <br/> |
|LocationCity  <br/> |このユーザーの Azure Active Directory で表されている都市データです。  <br/> |
|LocationCountry  <br/> |このユーザーの Azure Active Directory で表されている国データです。  <br/> |
|LocationState  <br/> |このユーザーの Azure Active Directory で表されている都道府県データです。  <br/> |
|LocationOffice  <br/> |ユーザーのオフィスです。  <br/> |
|Title  <br/> |このユーザーの Azure Active Directory で表されている役職データです。  <br/> |
|Deleted  <br/> |True の場合、ユーザーは、その最後の完全な月にMicrosoft 365から削除されました。  <br/> |
|DeletedDate  <br/> |ユーザーがMicrosoft 365から削除された日付。  <br/> |
|YAM_State  <br/> |Yammer システム内のユーザーの状態は、アクティブ、削除、または中断できます。  <br/> |
|YAM_ActivationDate  <br/> |ユーザーが Yammer でアクティブ状態になった日付です。  <br/> |
|YAM_DeletionDate  <br/> |ユーザーが Yammer で削除済み状態になった日付です。  <br/> |
|YAM_SuspensionDate  <br/> |ユーザーが Yammer で中断状態になった日付です。  <br/> |
   
### <a name="data-table---user-activity"></a>データ テーブル - User Activity (ユーザー アクティビティ)

この表には、前月にいずれかのサービスでアクティビティを実行した各ユーザーに関するデータが含まれます。
  
|**列名**|**列の説明**|
|:-----|:-----|
|UserID  <br/> |ユーザーを表し、データ セット内の他のデータ テーブルとの結合を有効にする一意のユーザー ID。  <br/> |
|IDType  <br/> |ID の種類は、ユーザーがYammer ID を使用して接続するYammer ユーザーの場合は 1、Microsoft 365 ID を使用してYammerに接続する場合は 0 に設定されます。  <br/> 値は、このユーザーがMicrosoft 365 ID ではなく、Yammer ID を使用してYammerに接続することを表す 1 です。  <br/> |
|Timeframe  <br/> |この表のデータが属する月を表す値です。  <br/> |
|EXO_EmailSent  <br/> |送信されたメールの数です。  <br/> |
|EXO_EmailReceived  <br/> |受信されたメールの数です。  <br/> |
|EXO_EmailRead  <br/> |ユーザーが実行したアクティビティを読み取った電子メールの数、既に読み取ったメール、または以前に受信した電子メールを複数回読み取る可能性があります。  <br/> |
|EXO_AppointmentCreated  <br/> |作成された予定の数。  <br/> |
|EXO_MeetingAccepted  <br/> |承諾された会議の数。  <br/> |
|EXO_MeetingCancelled  <br/> |キャンセルされた会議の数。  <br/> |
|EXO_MeetingDeclined  <br/> |会議の数が拒否されました。  <br/> |
|EXO_MeetingSent  <br/> |送信された会議の数。  <br/> |
|ODB_FileViewedModified  <br/> |このユーザーがいずれかの OneDrive for Business で操作 (作成、更新、削除、表示、ダウンロードなど) したファイルの数です。  <br/> |
|ODB_FileSynched  <br/> |このユーザーがいずれかの OneDrive for Business で同期したファイルの数です。  <br/> |
|ODB_FileSharedInternally  <br/> |このユーザーが内部で任意のOneDrive for Businessまたはグループ内のユーザーと共有したファイルの数 (外部ユーザーを含む場合があります)。  <br/> |
|ODB_FileSharedExternally  <br/> |このユーザーがいずれかの OneDrive for Business から外部共有したファイルの数です。  <br/> |
|ODB_AccessedByOwner  <br/> |ユーザーが操作したサイトの数は、自分のOneDrive for Businessに存在します。  <br/> |
|ODB_AccessedByOthers  <br/> |このユーザーが操作したサイトの数。別のユーザーのOneDrive for Businessに存在します。  <br/> |
|SPO_GroupFileViewedModified  <br/> |このユーザーが任意のグループ サイトで操作したファイルの数。  <br/> |
|SPO_GroupFileSynched  <br/> |このユーザーがグループ サイトで同期したファイルの数です。  <br/> |
|SPO_GroupFileSharedInternally  <br/> |組織内のユーザー、またはグループ内のユーザーと共有されたファイルの数 (外部ユーザーを含む場合があります)。  <br/> |
|SPO_GroupFileSharedExternally  <br/> |このユーザーがグループ サイトから外部共有したファイルの数です。  <br/> |
|SPO_GroupAccessedByOwner  <br/> |ユーザーが所有するグループ サイトに存在するユーザーが操作したサイトの数。  <br/> |
|SPO_GroupAccessedByOthers  <br/> |別のユーザーが所有するグループ サイトに存在するユーザーが操作したサイトの数。  <br/> |
|SPO_OtherFileViewedModified  <br/> |このユーザーが他のサイトで対話したファイルの数。  <br/> |
|SPO_OtherFileSynched  <br/> |このユーザーが他のサイトから同期したファイルの数。  <br/> |
|SPO_OtherFileSharedInternally  <br/> |このユーザーが他のサイトから内部的に共有したファイルの数、またはグループ内のユーザー (外部ユーザーを含む場合があります) と共有されます。 <br/> |
|SPO_OtherFileSharedExternally  <br/> |このユーザーが他のサイトから外部で共有したファイルの数。  <br/> |
|SPO_OtherAccessedByOwner  <br/> |ユーザーが自分が所有する他のサイトに存在するユーザーが操作したサイトの数。  <br/> |
|SPO_OtherAccessedByOthers  <br/> |別のユーザーが所有する他のサイトに存在する、ユーザーが操作したサイトの数。  <br/> |
|SPO_TeamFileViewedModified  <br/> |このユーザーがチーム サイトで対話したファイルの数です。  <br/> |
|SPO_TeamFileSynched  <br/> |このユーザーがチーム サイトで同期したファイルの数です。  <br/> |
|SPO_TeamFileSharedInternally  <br/> |このユーザーが任意のチーム サイトから内部で共有したファイルの数、またはグループ内のユーザー (外部ユーザーを含む場合があります) と共有されたファイルの数。  <br/> |
|SPO_TeamFileSharedExternally  <br/> |このユーザーがチーム サイトから外部共有したファイルの数です。  <br/> |
|SPO_TeamAccessedByOwner  <br/> |ユーザーが所有するチーム サイトに存在するユーザーが操作したサイトの数。  <br/> |
|SPO_TeamAccessedByOthers  <br/> |別のユーザーが所有するチーム サイトに存在するユーザーが操作したサイトの数。  <br/> |
|Teams_ChatMessages  <br/> |送信されたチャット メッセージの数。  <br/> |
|Teams_ChannelMessage  <br/> |チャネルに投稿されたメッセージの数。  <br/> |
|Teams_CallParticipate  <br/> |ユーザーが参加した通話の数。  <br/> |
|Teams_MeetingParticipate  <br/> |ユーザーが参加した会議の数。  <br/> |
|Teams_HasOtherAction  <br/> |ユーザーがMicrosoft Teamsで他のアクションを実行した場合のブール値。  <br/> |
|YAM_MessagePost  <br/> |このユーザーが投稿したYammer メッセージの数。  <br/> |
|YAM_MessageLiked  <br/> |このユーザーが気に入ったYammer メッセージの数。  <br/> |
|YAM_MessageRead  <br/> |このユーザーが読み取ったYammer メッセージの数。  <br/> |
|SFB_P2PSummary  <br/> |このユーザーが関わったピアツーピア セッションの数です。  <br/> |
|SFB_ConfOrgSummary  <br/> |このユーザーが編成した会議セッションの数です。  <br/> |
|SFB_ConfPartSummary  <br/> |このユーザーが参加した会議セッションの数です。  <br/> |

> [!NOTE]
> Teams_HasOtherActionは、ユーザーがアクティブと見なされますが、チャット メッセージ、1 対 1 の通話、チャネル メッセージ、会議の合計数、会議の 0 の値が整理されていることを意味します。
   
### <a name="data-table---tenant-product-usage"></a>データ テーブル - Tenant Product Usage (テナント製品の利用状況)

この表では、Microsoft 365内の各製品の有効化、アクティブ、リターン、および初回ユーザーの観点から、月単位の導入データを示します。 Microsoft 365値は、いずれかの製品でのアクティブな使用状況を表します。
  
|**列名**|**列の説明**|
|:-----|:-----|
|製品  <br/> |使用の情報を要約する製品の名前です。 製品列のMicrosoft 365値は、任意の製品にわたるアクティビティを表します  <br/> |
|Timeframe  <br/> |月の値。現在のところ、まだ完了していない月を含む、最後の 12 か月間に対して月別かつ製品ごとに 1 行割り当てられます。  <br/> |
|EnabledUsers  <br/> |期間の値に対して製品の使用を有効にしたユーザーの数は、ユーザーが月の一部に対して有効であった場合でもカウントされます。  <br/> |
|ActiveUsers  <br/> |期間の値に対して製品で意図的なアクティビティを実行したユーザーの数。  <br/> ユーザーは、製品で主要なアクティビティのいずれかを実行した場合、特定の月にその製品に対してアクティブとしてカウントされます。主要なアクティビティの一覧は、 **Tenant Product Activity** テーブルに示されています。  <br/> |
|CumulativeActiveUsers  <br/> |製品の使用が許可され、新しい利用状況システムでデータ回収が開始してから少なくとも 1 回は製品を使用したユーザーの数を時間枠の最大値まで累積したものです。  <br/> |
|MoMReturningUsers  <br/> |Timeframe の月でアクティブになっており、前月もアクティブであったユーザーの数です。  <br/> |
|FirstTimeUsers  <br/> |新しい利用状況システムのデータ回収以後、Timeframe で初めてアクティブになったユーザーの数です。  <br/> ユーザーは、この新しいレポート システムでのデータ収集開始以降初めてアクティビティが検出された場合に、特定の月の初めてのユーザーとしてカウントされます。 初めてのユーザーとしてカウントされると、このユーザーのアクティビティに大きなギャップがある場合でも、初めてのユーザーとして再びカウントされることはありません  <br/> |
|Content Date  <br/> |Timeframe が現在の月を示している場合、この値はデータが利用できる現在の月の最後の日付を表します。  <br/> Timeframe が前月を示している場合、この値は Timeframe の月の最後の日付を表します。  <br/> |
   
### <a name="data-table---tenant-product-activity"></a>データ テーブル - Tenant Product Activity (テナント製品のアクティビティ)

次の表は、製品内のさまざまなアクティビティに対する月間アクティビティの合計とアクティブなユーザー数を示しています。
  
|**列名**|**列の説明**|
|:-----|:-----|
|Timeframe  <br/> |月の値。現在のところ、まだ完了していない月を含む、最後の 12 か月間に対して月別かつ製品ごとに 1 行割り当てられます。  <br/> |
|Product  <br/> |使用状況データを使用できるMicrosoft 365内の製品の名前。  <br/> |
|Activity  <br/> |製品のアクティブな使用を示す、製品のアクティビティの名前です。  <br/> |
|ActivityCount  <br/> |これは、すべてのアクティブ ユーザーを対象に、製品内で実行されたアクティビティごとに数えられたアクションの合計数です。  <br/> **注:** SharePoint Online と OneDrive for Business の場合、この値はユーザーが対話した個々のドキュメントの数を表します。  <br/> |
|ActiveUserCount  <br/> |製品内でアクティビティを実行したユーザーの数です。  <br/> |
|TotalDurationInMinute  <br/> |該当する Skype for Business アクティビティで音声または動画による通話を行ったすべてのアクティブ ユーザーを対象とする通話時間 (分単位) です。  <br/> |
|Content Date  <br/> |Timeframe が現在の月を示している場合、この値はデータが利用できる現在の月の最後の日付を表します。  <br/> Timeframe が前月を示している場合、この値は Timeframe の月の最後の日付を表します。  <br/> |
   
### <a name="data-table---tenant-mailbox-usage"></a>データ テーブル - Tenant Mailbox Usage (テナント メールボックスの利用状況)

このテーブルは、ユーザー メールボックスを持つすべてのライセンスExchange Onlineユーザーの概要データで構成されます。 すべてのユーザーのメールボックスの間での月末の状態が含まれています。 このテーブルのデータは、複数の月の間で追加されることはありません。 このテーブルの最後の月のデータは、最新の状態を表します。
  
|**列名**|**列の説明**|
|:-----|:-----|
|TotalMailboxes  <br/> |Microsoft 365 サブスクリプションのユーザー メールボックスの数。  <br/> |
|IssueWarningQuota  <br/> |すべてのユーザーのメールボックスに対して警告を発行するための合計クォータ。  <br/> |
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

この表では、ユーザーがExchange Online、Skype for Business、Yammerに接続するために使用しているクライアントに関する月単位の概要データを示します。 このテーブルには、SharePoint Online と OneDrive for Business のクライアントの使用状況データはまだありません。
  
|**列名**|**列の説明**|
|:-----|:-----|
|製品  <br/> |クライアント使用状況データを使用できるMicrosoft 365内の製品の名前。  <br/> |
|Clientid  <br/> |製品への接続に使用する各デバイスの名前です。  <br/> |
|UserCount  <br/> |各クライアントを使用したユーザーの製品別の数です。  <br/> |
|Timeframe  <br/> |月の値  <br/> |
|Content Date  <br/> |Timeframe が現在の月を示している場合、この値はデータが利用できる現在の月の最後の日付を表します。  <br/> Timeframe が前月を示している場合、この値は Timeframe の月の最後の日付を表します。  <br/> |
   
### <a name="data-table---tenant-sharepoint-online-usage"></a>データ テーブル - Tenant SharePoint Online Usage (テナント SharePoint オンラインの利用状況)

この表は、SharePoint Online サイトの使用状況またはアクティビティに関する月単位の概要データで構成されます。 これは、チーム サイトとグループ サイトのみを対象としています。 SharePoint Online サイトの月末の状態は、たとえば、ユーザーが 5 つのドキュメントを作成し、合計ストレージに 10 MB を使用した後、一部のファイルを削除し、ファイルの月末の状態が 5 MB のストレージを使用する合計 7 個になるようにファイルを追加した場合などに、この列で表されます。 このテーブルで表される値は、月末の状態です。 このテーブルは、集計の重複カウントを回避するために非表示になっており、2 つの参照テーブルを作成するソースとして使用されます。
  
|**列名**|**列の説明**|
|:-----|:-----|
|SiteType  <br/> |サイトの種類の値 (任意/チーム/グループ) (任意はこれら 2 つのサイトの種類のどちらかを表します)。  <br/> |
|TotalSites  <br/> |Timeframe の最後に存在していたサイトの数です。  <br/> |
|DocumentCount  <br/> |Timeframe の最後にサイトに存在していたドキュメントの数です。  <br/> |
|Diplansed  <br/> |Timeframe の最後にすべてのサイト全体で集計した使用済み記憶域の合計です。  <br/> |
|ActivityType  <br/> |ファイル アクティビティのさまざまな種類 (任意/アクティブなファイル/外部共有ファイル/内部共有ファイル/同期されているファイル) が記録されているサイトの数。  <br/> 実行されたファイル アクティビティのいずれかを表します。  <br/> |
|SitesWithOwnerActivities  <br/> |サイトの所有者が自分のサイトで特定のファイル アクティビティを実行したアクティブ サイト数です。 サイト所有者は、PowerShell コマンド **get-sposite から取得** できます。 これは、サイトの責任者です。   <br/> |
|SitesWithNonOwnerActivities  <br/> |サイトの所有者以外のユーザーがその月にサイトで特定のファイルのアクティビティを実行したアクティブ サイト数の合計です。 サイト所有者は、PowerShell コマンド **get-sposite から取得** できます。 これは、サイトの責任者です。 <br/> |
|ActivityTotalSites  <br/> |その Timeframe でアクティビティを記録したサイトの数です。サイトで Timeframe の前半にアクティビティが存在し、Timeframe の終わりまでに削除された場合でも、その Timeframe のアクティブ サイトの合計で数えられます。  <br/> |
|Timeframe  <br/> |この列は、日付の値を持っています。予定表テーブルに対する多対 1 のリレーションシップとして使用されます。  <br/> |
|Content Date  <br/> |Timeframe が現在の月を示している場合、この値はデータが利用できる現在の月の最後の日付を表します。  <br/> Timeframe が前月を示している場合、この値は Timeframe の月の最後の日付を表します。  <br/> |
   
### <a name="data-table---tenant-onedrive-usage"></a>データ テーブル - テナントOneDrive使用状況

このテーブルでは、アカウント数、OneDrive アカウント全体のドキュメント数、使用されている記憶域、アクティビティの種類別のファイル数など、OneDrive アカウントに関するデータをまとめています。 このテーブルでは、OneDrive for Business アカウントの月末の状態が表されます。 たとえば、ユーザーが 10 MB のストレージを使用する 5 つのドキュメントを作成した後、いくつかのファイルを削除し、さらにファイルを追加して、月末に 5 MB のストレージを使用する 7 つのファイルを持つ場合、月末にこの表に月の終わりの値が表されます。
  
|**列名**|**列の説明**|
|:-----|:-----|
|SiteType  <br/> |値は "OneDrive" です。  <br/> |
|TotalSites  <br/> |Timeframe の終わりに存在した OneDrive for Business アカウントの数です。  <br/> |
|DocumentCount  <br/> |Timeframe の終わりに OneDrive for Business アカウント全体で存在したドキュメントの合計数です。  <br/> |
|Diplansed  <br/> |期間の終わりに、すべてのOneDriveアカウントで合計された合計ストレージの合計。  <br/> |
|ActivityType  <br/> |ファイル アクティビティのさまざまな種類 (任意/アクティブなファイル/外部共有ファイル/内部共有ファイル/同期されているファイル) が記録されているアカウントの数です。  <br/> 任意の場合、実行されたいずれかのファイル アクティビティを表します。  <br/> |
|SitesWithOwnerActivities  <br/> |アカウントの所有者が自分のアカウントで特定のファイル アクティビティを実行した、アクティブな OneDrive for Business アカウントの数です。  <br/> |
|SitesWithNonOwnerActivities  <br/> |ファイル アクティビティがアカウントの所有者以外のユーザーによって実行された OneDrive for Business アカウントの数です。  <br/> |
|ActivityTotalSites  <br/> |Timeframe の間に記録された OneDrive for Business アカウントの数です。Timeframe の早い段階で OneDrive for Business アカウントでアクティビティが行われ、Timeframe の終わりまでに削除された場合でも、その Timeframe のアクティブな OneDrive for Business アカウントとして数えられます。  <br/> |
|Timeframe  <br/> |この列は、日付の値を持っています。予定表テーブルに対する多対 1 のリレーションシップとして使用されます。  <br/> |
|Content Date  <br/> |Timeframe が現在の月を示している場合、この値はデータが利用できる現在の月の最後の日付を表します。  <br/> Timeframe が前月を示している場合、この値は Timeframe の月の最後の日付を表します。  <br/> |
   
### <a name="data-table---tenant-microsoft-365-groups-usage"></a>データ テーブル - テナントMicrosoft 365 グループ使用状況

次の表に、組織全体でMicrosoft 365 グループを使用する方法に関するデータを示します。
  
****

|**列名**|**列の説明**|
|:-----|:-----|
|期間  <br/> |月の値。現在のところ、まだ完了していない月を含む、最後の 12 か月間に対して月別かつ製品ごとに 1 行割り当てられます。  <br/> |
|GroupType  <br/> |グループの種類 (private/public/any)。  <br/> |
|TotalGroups  <br/> |各グループの種類のグループの数。  <br/> |
|ActiveGroups  <br/> |アクティブなグループの数。  <br/> |
|MBX_TotalGroups  <br/> |メールボックス グループの数。  <br/> |
|MBX_ActiveGroups  <br/> |アクティブなメールボックス グループの数。  <br/> |
|MBX_TotalActivities  <br/> |メールボックス アクティビティの数。  <br/> |
|MBX_TotalItems  <br/> |メールボックス アイテムの数。  <br/> |
|MBX_StorageUsed  <br/> |使用されるメールボックス ストレージの数量。  <br/> |
|SPO_TotalGroups  <br/> |SharePoint グループの数。  <br/> |
|SPO_ActiveGroups  <br/> |アクティブなSharePoint グループの数。  <br/> |
|SPO_FileAccessedActiveGroups  <br/> |ファイル アクセスアクティビティを持つSharePoint グループの数。  <br/> |
|SPO_FileSyncedActiveGroups  <br/> |ファイル同期アクティビティを持つSharePoint グループの数。  <br/> |
|SPO_FileSharedInternallyActiveGroups  <br/> |内部またはグループ (外部ユーザーを含む) で共有アクティビティを持つSharePoint グループの数。  <br/> |
|SPO_FileSharedExternallyActiveGroups  <br/> |外部でアクティビティを共有しているSharePoint グループの数。  <br/> |
|SPO_TotalActivities  <br/> |SharePointアクティビティの数。  <br/> |
|SPO_FileAccessedActivities  <br/> |アクセスされたSharePointファイルアクティビティの数。  <br/> |
|SPO_FileSyncedActivities  <br/> |SharePointファイル同期アクティビティの数。  <br/> |
|SPO_FileSharedInternallyActivities  <br/> |SharePoint ファイル共有アクティビティの内部またはグループ (外部メンバーを含む可能性があります) の数。  <br/> |
|SPO_FileSharedExternallyActivities  <br/> |外部で共有されるSharePoint ファイルの数。  <br/> |
|SPO_TotalFiles  <br/> |SharePoint ファイルの数。  <br/> |
|SPO_ActiveFiles  <br/> |アクティブなSharePoint ファイルの数。  <br/> |
|SPO_StorageUsed  <br/> |使用SharePointストレージの数量。  <br/> |
|YAM_TotalGroups  <br/> |Yammer グループの数。  <br/> |
|YAM_ActiveGroups  <br/> |アクティブなYammer グループの数。  <br/> |
|YAM_LikedActiveGroups  <br/> |同様のアクティビティを持つYammer グループの数。  <br/> |
|YAM_PostedActiveGroups  <br/> |投稿アクティビティがあるYammer グループの数。  <br/> |
|YAM_ReadActiveGroups  <br/> |読み取りアクティビティを持つYammer グループの数。  <br/> |
|YAM_TotalActivities  <br/> |Yammerアクティビティの数。  <br/> |
|YAM_LikedActivities  <br/> |アクティビティのようなYammerの数。  <br/> |
|YAM_PostedActivties  <br/> |Yammer投稿アクティビティの数。  <br/> |
|YAM_ReadActivites  <br/> |Yammer読み取りアクティビティの数。  <br/> |

### <a name="data-table---tenant-office-licenses"></a>データ テーブル - テナント Office ライセンス

この表では、ユーザーのライセンス割り当てに関する月単位の概要データを示します。 
  
|**列名**|**列の説明**|
|:-----|:-----|
|LicenseName  <br/> |ライセンスの名前。  <br/> |
|AssignedCount  <br/> |割り当てられたライセンスの数。  <br/> |
|Timeframe  <br/> |月の値。  <br/> |

### <a name="data-table---tenant-office-activation"></a>データ テーブル - Tenant Office Activation(テナントの Office ライセンス認証)

この表では、企業、Visio、ProjectのMicrosoft 365 Appsなど、サービス プラン全体でのOfficeサブスクリプションのアクティブ化の数に関するデータを示します。 デバイス (Android/iOS/Mac/PC) 別のライセンス認証数に関するデータも提供します。
  
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
