---
title: Microsoft 365 利用状況分析データ モデル
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: '利用状況分析が API に接続する方法について説明し、さまざまな Microsoft 365 サービスの利用状況の月単位の傾向を示します。  '
ms.openlocfilehash: 9d13d979e64a68aaffb3582ad6b09ab901843cd4
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841377"
---
# <a name="microsoft-365-usage-analytics-data-model"></a>Microsoft 365 利用状況分析データ モデル

## <a name="data-for-the-microsoft-365-usage-analytics-tables"></a>Microsoft 365 usage analytics の表のデータ

Microsoft 365 usage analytics は、多次元データモデルを公開する API に接続します。 Api はプレビュー段階にあり、でアクセスでき `https://reports.office.com/pbi/v1.0/\<tenantid\>` ます (は、を \<tenant id\> テナントの GUID に置き換えます)。 
  
> [!NOTE]
> 詳細については、microsoft [Graph の「microsoft 365 使用状況レポート](https://go.microsoft.com/fwlink/p/?linkid=864336)を使用する」を参照してください。 
  
この API は、さまざまな Microsoft 365 サービスの使用状況の月ごとの傾向に関する情報を提供します。 API によって返される厳密なデータについては、次のセクションの表を参照してください。
  
## <a name="data-tables-returned-by-the-microsoft-365-reporting-api"></a>Microsoft 365 レポート API によって返されるデータテーブル

|**テーブル名**|**テーブル内の情報**|**日付範囲**|
|:-----|:-----|:-----|
|Tenant Product Usage (テナント製品の利用状況)  <br/> |[有効]、[アクティブなユーザー]、[月単位の保存ユーザー]、[初回ユーザー]、および [累積アクティブユーザー] の月ごとの合計が含まれています。  <br/> |12 か月連続の期間 (現在のところ、まだ終わっていない月を含む) の月次集計データが含まれています。  <br/> |
|Tenant Product Activity (テナント製品のアクティビティ)  <br/> |製品内のさまざまなアクティビティについて、アクティビティの月次合計とアクティブなユーザー数を含みます。  <br/> このデータ表で返される、ある製品内のアクティビティに関する情報については、[アクティブ ユーザーの定義](active-user-in-usage-reports.md)に関するページを参照してください。  <br/> |12 か月連続の期間 (現在のところ、まだ終わっていない月を含む) の月次集計データが含まれています。  <br/> |
|Tenant Office Licenses (テナントの Office ライセンス)  <br/> |ユーザーに割り当てられている Microsoft Office サブスクリプションの数に関するデータが含まれています。  <br/> |現在の一部の月を含む12か月のローリング期間の終了月の状態データが含まれています。  <br/> |
|Tenant Mailbox Usage (テナント メールボックスの利用状況)  <br/> |メールボックスの合計数と記憶域の使用方法に関する、ユーザーのメールボックスに関するデータが保存されています。  <br/> |現在の一部の月を含む12か月のローリング期間の終了月の状態データが含まれています。  <br/> |
|Tenant Client Usage (テナント クライアントの利用状況)  <br/> |Exchange Online、Skype for Business、Yammer への接続に特定のクライアント/デバイスを使用しているユーザーの数に関するデータが含まれています。  <br/> |12 か月連続の期間 (現在のところ、まだ終わっていない月を含む) の月次集計データが含まれています。  <br/> |
|Tenant SharePoint Online Usage (テナント SharePoint オンラインの利用状況)  <br/> |SharePoint サイト、サイトの合計数などの含まれるチームまたはグループ、サイトのドキュメントの数、アクティビティ タイプ別のファイル数、使用しているストレージに関するデータが含まれています。  <br/> |現在の一部の月を含む12か月のローリング期間の終了月の状態データが含まれています。  <br/> |
|Tenant OneDrive for Business Usage (テナントの OneDrive for Business の利用状況)  <br/> |アカウントの数、OneDrive 全体のドキュメントの数、使用されているストレージ、アクティビティの種類別のファイル数などの OneDrive アカウントに関するデータが含まれています。  <br/> |現在の一部の月を含む12か月のローリング期間の終了月の状態データが含まれています。  <br/> |
|テナントの Microsoft 365 グループの使用  <br/> |メールボックス、SharePoint、Yammer など、Microsoft 365 グループの使用法に関するデータが保存されています。  <br/> |現在の一部の月を含む12か月のローリング期間の終了月の状態データが含まれています。  <br/> |
|Tenant Office Activation (テナントの Office ライセンス認証)  <br/> |Office サブスクリプションのライセンス認証数、デバイスごとのライセンス認証数 (Android/iOS/Mac/PC)、サービスプランによるライセンス認証の数に関するデータが含まれます。たとえば、Microsoft 365 Apps for enterprise、Visio、Project などです。  <br/> |現在の一部の月を含む12か月のローリング期間の終了月の状態データが含まれています。  <br/> |
|User State (ユーザーの状態)  <br/> |ユーザーの表示名、割り当てられた製品、場所、部署、役職、会社など、ユーザーに関するメタデータが含まれます。 このデータは、最後に完了した月にライセンスが割り当てられたユーザーに関するものです。 すべてのユーザーは、ユーザー ID で一意に表されます。  <br/> |このデータは、完了した最後の月にライセンスを割り当てられたユーザーに関するものです。  <br/> |
|User Activity (ユーザー アクティビティ)  <br/> |ライセンスを取得したユーザーが実行したアクティビティに関するユーザーごとの情報が含まれています。  <br/> このデータ表で返される、ある製品内のアクティビティに関する情報については、[アクティブ ユーザーの定義](active-user-in-usage-reports.md)に関するページを参照してください。  <br/> |このデータは、完了した最後の月の間、何らかのサービスでアクティビティを実行したユーザーに関するものです。  <br/> |
   
各データ テーブルの詳細情報を表示するには、次のセクションを展開します。
  
### <a name="data-table---user-state"></a>データ テーブル - User State (ユーザーの状態)

この表には、最後の完了月にライセンスが割り当てられているすべてのユーザーのユーザーレベルの詳細が表示されます。 Azure Active Directory からデータが得られます。
  
|**列名**|**列の説明**|
|:-----|:-----|
|UserId  <br/> |ユーザーを表す一意のユーザー ID。データセット内の他のデータテーブルとの結合を可能にします。  <br/> |
|Timeframe  <br/> |この表のデータが属する月を表す値です。  <br/> |
|UPN  <br/> |ユーザー プリンシパル名のことであり、他の外部データ ソースと結合できるよう、ユーザーを一意に識別します。  <br/> |
|DisplayName  <br/> |ユーザーの表示名。  <br/> |
|IDType  <br/> |ユーザーが yammer ID を使用して接続する Yammer ユーザー、または Microsoft 365 ID を使用して Yammer に接続する場合、ID の種類は1に設定されます。  <br/> このユーザーが yammer ID を使用して Yammer に接続し、Microsoft 365 ID ではないことを表す値は1です。  <br/> |
|HasLicenseEXO  <br/> |ユーザーにライセンスが割り当てられており、Exchange を使用できる場合は、true に設定します。  <br/> |
|HasLicenseODB  <br/> |ユーザーにライセンスが割り当てられており、OneDrive for Business を使用できる場合は、true に設定します。  <br/> |
|HasLicenseSPO  <br/> |ユーザーにライセンスが割り当てられており、SharePoint Online を使用できる場合は、true に設定します。  <br/> |
|HasLicenseYAM  <br/> |ユーザーにライセンスが割り当てられており、Yammer を使用できる場合は、true に設定します。  <br/> |
|HasLicenseSFB  <br/> |ユーザーにライセンスが割り当てられており、Skype For Business を使用できる場合は、true に設定します。  <br/> |
|HasLicenseTeams  <br/> |ユーザーにライセンスが割り当てられ、Microsoft Teams を使用できるようにする場合は、true に設定します。  <br/> |
|Company  <br/> |このユーザーの Azure Active Directory で表されている会社データです。  <br/> |
|Department  <br/> |このユーザーの Azure Active Directory で表されている部署データです。  <br/> |
|LocationCity  <br/> |このユーザーの Azure Active Directory で表されている都市データです。  <br/> |
|LocationCountry  <br/> |このユーザーの Azure Active Directory で表されている国データです。  <br/> |
|LocationState  <br/> |このユーザーの Azure Active Directory で表されている都道府県データです。  <br/> |
|LocationOffice  <br/> |ユーザーのオフィスです。  <br/> |
|Title  <br/> |このユーザーの Azure Active Directory で表されている役職データです。  <br/> |
|Deleted  <br/> |True の場合、ユーザーは最後の完全な月の Microsoft 365 から削除されています。  <br/> |
|DeletedDate  <br/> |ユーザーが Microsoft 365 から削除された日付。  <br/> |
|YAM_State  <br/> |Yammer システムのユーザーの状態。アクティブ、削除済み、または中断が可能です。  <br/> |
|YAM_ActivationDate  <br/> |ユーザーが Yammer でアクティブ状態になった日付です。  <br/> |
|YAM_DeletionDate  <br/> |ユーザーが Yammer で削除済み状態になった日付です。  <br/> |
|YAM_SuspensionDate  <br/> |ユーザーが Yammer で中断状態になった日付です。  <br/> |
   
### <a name="data-table---user-activity"></a>データ テーブル - User Activity (ユーザー アクティビティ)

この表には、前月にいずれかのサービスでアクティビティを実行した各ユーザーに関するデータが含まれます。
  
|**列名**|**列の説明**|
|:-----|:-----|
|UserID  <br/> |ユーザーを表す一意のユーザー ID。データセット内の他のデータテーブルとの結合を可能にします。  <br/> |
|IDType  <br/> |ユーザーが yammer ID を使用して接続する Yammer ユーザー、または Microsoft 365 ID を使用して Yammer に接続する場合、ID の種類は1に設定されます。  <br/> このユーザーが yammer ID を使用して Yammer に接続し、Microsoft 365 ID ではないことを表す値は1です。  <br/> |
|Timeframe  <br/> |この表のデータが属する月を表す値です。  <br/> |
|EXO_EmailSent  <br/> |送信されたメールの数です。  <br/> |
|EXO_EmailReceived  <br/> |受信されたメールの数です。  <br/> |
|EXO_EmailRead  <br/> |ユーザーが実行したメールの読み取りアクティビティの数。既読の電子メールまたは以前に受信した電子メールを複数回読み取ることができます。  <br/> |
|EXO_AppointmentCreated  <br/> |作成された予定の数。  <br/> |
|EXO_MeetingAccepted  <br/> |承諾した会議の数。  <br/> |
|EXO_MeetingCancelled  <br/> |キャンセルされた会議の数。  <br/> |
|EXO_MeetingDeclined  <br/> |辞退した会議の数。  <br/> |
|EXO_MeetingSent  <br/> |送信された会議の数。  <br/> |
|ODB_FileViewedModified  <br/> |このユーザーがいずれかの OneDrive for Business で操作 (作成、更新、削除、表示、ダウンロードなど) したファイルの数です。  <br/> |
|ODB_FileSynched  <br/> |このユーザーがいずれかの OneDrive for Business で同期したファイルの数です。  <br/> |
|ODB_FileSharedInternally  <br/> |このユーザーが OneDrive for business またはグループ内のユーザー (外部ユーザーを含む場合があります) から内部共有しているファイルの数。  <br/> |
|ODB_FileSharedExternally  <br/> |このユーザーがいずれかの OneDrive for Business から外部共有したファイルの数です。  <br/> |
|ODB_AccessByOwner  <br/> |ユーザーが対話したファイル (自分の OneDrive for Business 上に存在する) の数です。  <br/> |
|ODB_AccessOthers  <br/> |このユーザーが対話したファイル (別のユーザーの OneDrive for Business 上に存在する) の数です。  <br/> |
|SPO_GroupFileViewedModified  <br/> |このユーザーがグループ サイトで対話したファイルの数です。  <br/> |
|SPO_GroupFileSynched  <br/> |このユーザーがグループ サイトで同期したファイルの数です。  <br/> |
|SPO_GroupFileSharedInternally  <br/> |組織内のユーザーが共有しているファイルの数、またはグループ内のユーザー (外部ユーザーが含まれる可能性があります)。  <br/> |
|SPO_GroupFileSharedExternally  <br/> |このユーザーがグループ サイトから外部共有したファイルの数です。  <br/> |
|SPO_GroupAccessByOwner  <br/> |ユーザーが対話したファイル (自分が所有するグループ サイト上に存在する) の数です。  <br/> |
|SPO_GroupAccessByOthers  <br/> |ユーザーが対話したファイル (別のユーザーが所有するグループ サイト上に存在する) の数です。  <br/> |
|SPO_OtherFileViewedModified  <br/> |このユーザーが他のサイトで対話したファイルの数。  <br/> |
|SPO_OtherFileSynched  <br/> |このユーザーが他のサイトから同期したファイルの数。  <br/> |
|SPO_OtherFileSharedInternally  <br/> |このユーザーが他のサイトから内部共有したファイルの数、またはグループ内のユーザー (外部ユーザーが含まれている可能性があります)。 <br/> |
|SPO_OtherFileSharedExternally  <br/> |このユーザーが他のサイトの外部で共有したファイルの数。  <br/> |
|SPO_OtherAccessedByOwner  <br/> |ユーザーが対話したサイトのうち、自分が所有している他のサイトに存在するサイトの数。  <br/> |
|SPO_OtherAccessedByOthers  <br/> |他のユーザーが所有している他のサイトに存在する、ユーザーが対話したサイトの数。  <br/> |
|SPO_TeamFileViewedModified  <br/> |このユーザーがチーム サイトで対話したファイルの数です。  <br/> |
|SPO_TeamFileSynched  <br/> |このユーザーがチーム サイトで同期したファイルの数です。  <br/> |
|SPO_TeamFileSharedInternally  <br/> |このユーザーがチームサイトから内部共有しているファイルの数、またはグループ内のユーザー (外部ユーザーが含まれている可能性がある場合があります)。  <br/> |
|SPO_TeamFileSharedExternally  <br/> |このユーザーがチーム サイトから外部共有したファイルの数です。  <br/> |
|SPO_TeamAccessByOwner  <br/> |ユーザーが対話したファイル (自分が所有するチーム サイト上に存在する) の数です。  <br/> |
|SPO_TeamAccessByOthers  <br/> |ユーザーが対話したファイル (別のユーザーが所有するチーム サイト上に存在する) の数です。  <br/> |
|Teams_ChatMessages  <br/> |送信されたチャットメッセージの数。  <br/> |
|Teams_ChannelMessage  <br/> |チャネルに投稿されたメッセージの数。  <br/> |
|Teams_CallParticipate  <br/> |ユーザーが参加した通話の数。  <br/> |
|Teams_MeetingParticipate  <br/> |ユーザーが参加した会議の数。  <br/> |
|Teams_HasOtherAction  <br/> |ユーザーが Microsoft Teams で他のアクションを実行した場合のブール値。  <br/> |
|YAM_MessagePost  <br/> |このユーザーが投稿した Yammer メッセージの数です。  <br/> |
|YAM_MessageLiked  <br/> |このユーザーが賛同した Yammer メッセージの数です。  <br/> |
|YAM_MessageRead  <br/> |このユーザーが読み取る Yammer メッセージの数です。  <br/> |
|SFB_P2PSummary  <br/> |このユーザーが関わったピアツーピア セッションの数です。  <br/> |
|SFB_ConfOrgSummary  <br/> |このユーザーが編成した会議セッションの数です。  <br/> |
|SFB_ConfPartSummary  <br/> |このユーザーが参加した会議セッションの数です。  <br/> |

> [!NOTE]
> Teams_HasOtherAction は、ユーザーはアクティブと見なされますが、チャットメッセージ、1:1 通話、チャネルメッセージ、会議の合計、および開催された会議に対して、0の値があることを意味します。
   
### <a name="data-table---tenant-product-usage"></a>データ テーブル - Tenant Product Usage (テナント製品の利用状況)

次の表では、Microsoft 365 内の各製品の有効化、アクティブ、返品、および初回ユーザーのために、月単位の導入データを提供します。 Microsoft 365 の値は、いずれかの製品のアクティブな使用法を表します。
  
|**列名**|**列の説明**|
|:-----|:-----|
|製品  <br/> |使用の情報を要約する製品の名前です。 製品列の Microsoft 365 値は、いずれかの製品におけるアクティビティを表します。  <br/> |
|Timeframe  <br/> |月の値。現在のところ、まだ完了していない月を含む、最後の 12 か月間に対して月別かつ製品ごとに 1 行割り当てられます。  <br/> |
|EnabledUsers  <br/> |タイムフレームの値に対して有効にされたユーザーの数。ユーザーがその月の一部を有効にした場合は、カウントされたままになります。  <br/> |
|ActiveUsers  <br/> |タイムフレーム値について、製品内で意図的なアクティビティを実行したユーザーの数。  <br/> ユーザーは、製品で主要なアクティビティのいずれかを実行した場合、特定の月にその製品に対してアクティブとしてカウントされます。主要なアクティビティの一覧は、 **Tenant Product Activity** テーブルに示されています。  <br/> |
|CumulativeActiveUsers  <br/> |製品の使用が許可され、新しい利用状況システムでデータ回収が開始してから少なくとも 1 回は製品を使用したユーザーの数を時間枠の最大値まで累積したものです。  <br/> |
|MoMReturningUsers  <br/> |Timeframe の月でアクティブになっており、前月もアクティブであったユーザーの数です。  <br/> |
|FirstTimeUsers  <br/> |新しい利用状況システムのデータ回収以後、Timeframe で初めてアクティブになったユーザーの数です。  <br/> ユーザーは、この新しいレポート システムでのデータ収集開始以降初めてアクティビティが検出された場合に、特定の月の初めてのユーザーとしてカウントされます。 最初のユーザーとして数えられた場合、このユーザーがアクティビティに大きな隙間がある場合でも、初回のユーザーとして再びカウントされることはありません。  <br/> |
|Content Date  <br/> |Timeframe が現在の月を示している場合、この値はデータが利用できる現在の月の最後の日付を表します。  <br/> Timeframe が前月を示している場合、この値は Timeframe の月の最後の日付を表します。  <br/> |
   
### <a name="data-table---tenant-product-activity"></a>データ テーブル - Tenant Product Activity (テナント製品のアクティビティ)

次の表は、製品内のさまざまなアクティビティについて、アクティビティの合計数とアクティブなユーザー数を示しています。
  
|**列名**|**列の説明**|
|:-----|:-----|
|Timeframe  <br/> |月の値。現在のところ、まだ完了していない月を含む、最後の 12 か月間に対して月別かつ製品ごとに 1 行割り当てられます。  <br/> |
|Product  <br/> |利用状況データを利用できる Microsoft 365 内の製品の名前です。  <br/> |
|Activity  <br/> |製品のアクティブな使用を示す、製品のアクティビティの名前です。  <br/> |
|ActivityCount  <br/> |これは、すべてのアクティブ ユーザーを対象に、製品内で実行されたアクティビティごとに数えられたアクションの合計数です。  <br/> **注:** SharePoint Online と OneDrive for Business の場合、この値はユーザーが対話した個々のドキュメントの数を表します。  <br/> |
|ActiveUserCount  <br/> |製品内でアクティビティを実行したユーザーの数です。  <br/> |
|TotalDurationInMinute  <br/> |該当する Skype for Business アクティビティで音声または動画による通話を行ったすべてのアクティブ ユーザーを対象とする通話時間 (分単位) です。  <br/> |
|Content Date  <br/> |Timeframe が現在の月を示している場合、この値はデータが利用できる現在の月の最後の日付を表します。  <br/> Timeframe が前月を示している場合、この値は Timeframe の月の最後の日付を表します。  <br/> |
   
### <a name="data-table---tenant-mailbox-usage"></a>データ テーブル - Tenant Mailbox Usage (テナント メールボックスの利用状況)

この表は、ユーザーのメールボックスを持つすべてのライセンスされた Exchange Online ユーザーの要約データで構成されています。 すべてのユーザーのメールボックスの間での月末の状態が含まれています。 このテーブルのデータは、複数の月の間で追加されることはありません。 このテーブルの最後の月のデータは、最新の状態を表します。
  
|**列名**|**列の説明**|
|:-----|:-----|
|TotalMailboxes ボックス  <br/> |Microsoft 365 サブスクリプションのユーザーメールボックスの数。  <br/> |
|IssueWarningQuota  <br/> |すべてのユーザーのメールボックスで警告を発行するための総クォータ。  <br/> |
|ProhibitSendQuota  <br/> |すべてのユーザー メールボックスを対象に送信を禁止するための割り当てられる合計容量です。  <br/> |
|ProhibitSendReceiveQuota  <br/> |すべてのユーザー メールボックスを対象に送受信を禁止するための割り当てられる合計容量です。  <br/> |
|TotalItemBytes  <br/> |すべてのユーザー メールボックスで使用されている記憶域の量です (バイト単位)。  <br/> |
|MailboxesNoWarning  <br/> |記憶域の警告の制限下にあったユーザーのメールボックスの数です。  <br/> |
|MailboxesIssueWarning  <br/> |記憶域のクォータに対して警告が発行されたユーザーのメールボックスの数です。  <br/> |
|MailboxesExceedSendQuota  <br/> |送信クォータを超えていたユーザーのメールボックスの数です。  <br/> |
|MailboxesExceedSendReceiveQuota  <br/> |送信/受信クォータを超過したユーザーメールボックスの数。  <br/> |
|DeletedMailboxes  <br/> |Timeframe で削除されているユーザー メールボックスの数です。  <br/> |
|Timeframe  <br/> |月の値。  <br/> |
|Content Date  <br/> |Timeframe が現在の月を示している場合、この値はデータが利用できる現在の月の最後の日付を表します。  <br/> Timeframe が前月を示している場合、この値は Timeframe の月の最後の日付を表します。  <br/> |
   
### <a name="data-table---tenant-client-usage"></a>データ テーブル - Tenant Client Usage (テナント クライアントの使用状況)

次の表は、ユーザーが Exchange Online、Skype for Business、Yammer への接続に使用しているクライアントに関する、月単位の概要データを示しています。 このテーブルには、SharePoint Online と OneDrive for Business のクライアントの使用状況データはまだありません。
  
|**列名**|**列の説明**|
|:-----|:-----|
|製品  <br/> |Microsoft 365 内の、クライアント利用状況データが利用できる製品の名前です。  <br/> |
|ClientId  <br/> |製品への接続に使用する各デバイスの名前です。  <br/> |
|UserCount  <br/> |各クライアントを使用したユーザーの製品別の数です。  <br/> |
|Timeframe  <br/> |月の値  <br/> |
|Content Date  <br/> |Timeframe が現在の月を示している場合、この値はデータが利用できる現在の月の最後の日付を表します。  <br/> Timeframe が前月を示している場合、この値は Timeframe の月の最後の日付を表します。  <br/> |
   
### <a name="data-table---tenant-sharepoint-online-usage"></a>データ テーブル - Tenant SharePoint Online Usage (テナント SharePoint オンラインの利用状況)

この表は、SharePoint Online サイトの使用状況またはアクティビティに関する月別の概要データで構成されています。 これは、チームサイトとグループサイトのみを対象としています。 SharePoint Online サイトの月末の状態は、この列に表示されます。たとえば、ユーザーが5つのドキュメントを作成し、総記憶領域に 10 MB を使用して、ファイルを削除して、ファイルの月の最後の状態が 5 MB のストレージを使用する7合計の場合、この表に示されている値は月末の状態です このテーブルは非表示になっており、集計の重複数を回避し、ソースとして2つの参照テーブルを作成するために使用されます。
  
|**列名**|**列の説明**|
|:-----|:-----|
|SiteType  <br/> |サイトの種類の値 (任意/チーム/グループ) (任意はこれら 2 つのサイトの種類のどちらかを表します)。  <br/> |
|TotalSites  <br/> |Timeframe の最後に存在していたサイトの数です。  <br/> |
|DocumentCount  <br/> |Timeframe の最後にサイトに存在していたドキュメントの数です。  <br/> |
|Diplan sed  <br/> |Timeframe の最後にすべてのサイト全体で集計した使用済み記憶域の合計です。  <br/> |
|ActivityType  <br/> |ファイル アクティビティのさまざまな種類 (任意/アクティブなファイル/外部共有ファイル/内部共有ファイル/同期されているファイル) が記録されているサイトの数。  <br/> 実行されたファイルアクティビティのいずれかを表します。  <br/> |
|SitesWithOwnerActivities  <br/> |サイトの所有者が自分のサイトで特定のファイル アクティビティを実行したアクティブ サイト数です。  <br/> |
|(所有) 非所有者アクティビティ  <br/> |サイトの所有者以外のユーザーがその月にサイトで特定のファイルのアクティビティを実行したアクティブ サイト数の合計です。  <br/> |
|ActivityTotalSites  <br/> |その Timeframe でアクティビティを記録したサイトの数です。サイトで Timeframe の前半にアクティビティが存在し、Timeframe の終わりまでに削除された場合でも、その Timeframe のアクティブ サイトの合計で数えられます。  <br/> |
|Timeframe  <br/> |この列は、日付の値を持っています。予定表テーブルに対する多対 1 のリレーションシップとして使用されます。  <br/> |
|Content Date  <br/> |Timeframe が現在の月を示している場合、この値はデータが利用できる現在の月の最後の日付を表します。  <br/> Timeframe が前月を示している場合、この値は Timeframe の月の最後の日付を表します。  <br/> |
   
### <a name="data-table---tenant-onedrive-usage"></a>データテーブル-テナントの OneDrive 使用法

このテーブルでは、アカウント数、OneDrive アカウント全体のドキュメント数、使用されている記憶域、アクティビティの種類別のファイル数など、OneDrive アカウントに関するデータをまとめています。 このテーブルでは、OneDrive for Business アカウントの月末の状態が表されます。 たとえば、ユーザーが 10 MB のストレージを使用した5つのドキュメントを作成した後で、さらにいくつかのファイルを削除して、月末に 5 MB のストレージを使用する7つのファイルがある場合、月の最後の値はこの表ではその月の終わりに表示されます。
  
|**列名**|**列の説明**|
|:-----|:-----|
|SiteType  <br/> |値は "OneDrive" です。  <br/> |
|TotalSites  <br/> |Timeframe の終わりに存在した OneDrive for Business アカウントの数です。  <br/> |
|DocumentCount  <br/> |Timeframe の終わりに OneDrive for Business アカウント全体で存在したドキュメントの合計数です。  <br/> |
|Diplan sed  <br/> |タイムフレームの終わりにすべての OneDrive アカウントで合計使用された記憶域の合計。  <br/> |
|ActivityType  <br/> |ファイル アクティビティのさまざまな種類 (任意/アクティブなファイル/外部共有ファイル/内部共有ファイル/同期されているファイル) が記録されているアカウントの数です。  <br/> 任意の場合、実行されたいずれかのファイル アクティビティを表します。  <br/> |
|SitesWithOwnerActivities  <br/> |アカウントの所有者が自分のアカウントで特定のファイル アクティビティを実行した、アクティブな OneDrive for Business アカウントの数です。  <br/> |
|(所有) 非所有者アクティビティ  <br/> |ファイル アクティビティがアカウントの所有者以外のユーザーによって実行された OneDrive for Business アカウントの数です。  <br/> |
|ActivityTotalSites  <br/> |Timeframe の間に記録された OneDrive for Business アカウントの数です。Timeframe の早い段階で OneDrive for Business アカウントでアクティビティが行われ、Timeframe の終わりまでに削除された場合でも、その Timeframe のアクティブな OneDrive for Business アカウントとして数えられます。  <br/> |
|Timeframe  <br/> |この列は、日付の値を持っています。予定表テーブルに対する多対 1 のリレーションシップとして使用されます。  <br/> |
|Content Date  <br/> |Timeframe が現在の月を示している場合、この値はデータが利用できる現在の月の最後の日付を表します。  <br/> Timeframe が前月を示している場合、この値は Timeframe の月の最後の日付を表します。  <br/> |
   
### <a name="data-table---tenant-microsoft-365-groups-usage"></a>データテーブル-テナントの Microsoft 365 グループの使用

この表は、Microsoft 365 グループが組織全体でどのように使用されているかに関するデータを提供します。
  
****

|**列名**|**列の説明**|
|:-----|:-----|
|TimeFrame  <br/> |月の値。 現在のところ、まだ完了していない月を含む、最後の 12 か月間に対して月別かつ製品ごとに 1 行割り当てられます。  <br/> |
|GroupType  <br/> |グループの種類 (private/public/any)。  <br/> |
|TotalGroups  <br/> |各グループの種類に含まれるグループの数。  <br/> |
|ActiveGroups  <br/> |アクティブなグループの数。  <br/> |
|MBX_TotalGroups  <br/> |メールボックスグループの数。  <br/> |
|MBX_ActiveGroups  <br/> |アクティブなメールボックスグループの数。  <br/> |
|MBX_TotalActivities  <br/> |メールボックスアクティビティの数。  <br/> |
|MBX_TotalItems  <br/> |メールボックスアイテムの数。  <br/> |
|MBX_StorageUsed  <br/> |使用されているメールボックスの記憶域の量。  <br/> |
|SPO_TotalGroups  <br/> |SharePoint グループの数。  <br/> |
|SPO_ActiveGroups  <br/> |アクティブな SharePoint グループの数。  <br/> |
|SPO_FileAccessedActiveGroups  <br/> |ファイルにアクセスされたアクティビティを持つ SharePoint グループの数。  <br/> |
|SPO_FileSyncedActiveGroups  <br/> |ファイルが同期されたアクティビティを持つ SharePoint グループの数。  <br/> |
|SPO_FileSharedInternallyActiveGroups  <br/> |内部で、またはグループ (外部ユーザーが含まれる可能性がある) で共有されている SharePoint グループの数。  <br/> |
|SPO_FileSharedExternallyActiveGroups  <br/> |外部アクティビティを共有している SharePoint グループの数。  <br/> |
|SPO_TotalActivities  <br/> |SharePoint アクティビティの数。  <br/> |
|SPO_FileAccessedActivities  <br/> |SharePoint ファイルにアクセスされたアクティビティの数。  <br/> |
|SPO_FileSyncedActivities  <br/> |SharePoint ファイルで同期されたアクティビティの数。  <br/> |
|SPO_FileSharedInternallyActivities  <br/> |内部で、または (外部メンバーが含まれる可能性がある) グループを使用して、SharePoint ファイルの共有アクティビティの数。  <br/> |
|SPO_FileSharedExternallyActivities  <br/> |外部の SharePoint ファイル共有アクティビティの数。  <br/> |
|SPO_TotalFiles  <br/> |SharePoint ファイルの数。  <br/> |
|SPO_ActiveFiles  <br/> |アクティブな SharePoint ファイルの数。  <br/> |
|SPO_StorageUsed  <br/> |使用されている SharePoint ストレージの数量。  <br/> |
|YAM_TotalGroups  <br/> |Yammer グループの数。  <br/> |
|YAM_ActiveGroups  <br/> |アクティブな Yammer グループの数。  <br/> |
|YAM_LikedActiveGroups  <br/> |アクティビティに似た Yammer グループの数。  <br/> |
|YAM_PostedActiveGroups  <br/> |投稿アクティビティがある Yammer グループの数。  <br/> |
|YAM_ReadActiveGroups  <br/> |読み取りアクティビティを含む Yammer グループの数。  <br/> |
|YAM_TotalActivities  <br/> |Yammer アクティビティの数。  <br/> |
|YAM_LikedActivities  <br/> |Yammer のアクティビティの数。  <br/> |
|YAM_PostedActivties  <br/> |Yammer の投稿アクティビティの数。  <br/> |
|YAM_ReadActivites  <br/> |Yammer の読み取りアクティビティの数。  <br/> |
   
### <a name="data-table---tenant-office-activation"></a>データ テーブル - Tenant Office Activation(テナントの Office ライセンス認証)

この表は、サービスプラン全体にわたる Office サブスクリプションのライセンス認証数に関するデータを提供します。たとえば、企業用の Microsoft 365 アプリ、Visio、Project などです。 デバイス (Android/iOS/Mac/PC) 別のライセンス認証数に関するデータも提供します。
  
|**列名**|**列の説明**|
|:-----|:-----|
|Serviceplan の名前  <br/> |サービス プラン名の値とデバイス別のライセンス認証の数を一覧表示します。それぞれの説明は以下の列のようになります。  <br/> |
|TotalEnabled  <br/> |Timeframe の終わりまでに有効化されたユーザーの数をサービス プラン名別に示したものです。  <br/> |
|TotalActivatedUsers ユーザー  <br/> |Timeframe の終わりまでに各サービス プランをライセンス認証したユーザーの数を示したものです。  <br/> |
|AndroidCount  <br/> |Timeframe の終わりまでのライセンス認証数を Android デバイスのサービス プランを対象に示したものです。  <br/> |
|iOSCount  <br/> |Timeframe の終わりまでのライセンス認証数を iOS デバイスのサービス プランを対象に示したものです。  <br/> |
|MacCount  <br/> |Timeframe の終わりまでのライセンス認証数を MAC デバイスのサービス プランを対象に示したものです。  <br/> |
|PcCount  <br/> |Timeframe の終わりまでのライセンス認証数を PC デバイスのサービス プランを対象に示したものです。  <br/> |
|WinRtCount  <br/> |Timeframe の終わりまでのライセンス認証数を Windows Mobile デバイスのサービス プランを対象に示したものです。  <br/> |
|Timeframe  <br/> |この列は、日付の値を持っています。予定表テーブルに対する多対 1 のリレーションシップとして使用されます。  <br/> |
|Content Date  <br/> |Timeframe が現在の月を示している場合、この値はデータが利用できる現在の月の最後の日付を表します。  <br/> Timeframe が前月を示している場合、この値は Timeframe の月の最後の日付を表します。  <br/> |
   

