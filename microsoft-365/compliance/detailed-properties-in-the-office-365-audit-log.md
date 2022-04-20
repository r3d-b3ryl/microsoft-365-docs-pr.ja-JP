---
title: 監査ログの詳細なプロパティ
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- BCS160
- MET150
ms.assetid: ce004100-9e7f-443e-942b-9b04098fcfc3
description: この記事では、Office 365監査ログ レコードの結果をエクスポートするときに含まれる追加のプロパティについて説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7e65b5e27f8c6821b12c7f0b7f03e4ecb472c0a9
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64948949"
---
# <a name="detailed-properties-in-the-audit-log"></a>監査ログの詳細なプロパティ

Microsoft Purview コンプライアンス ポータルから監査ログ検索の結果をエクスポートする場合は、検索条件を満たすすべての結果をダウンロードできます。 このエクスポートを行うには、[**監査ログの検索**] ページで、[**結果のエクスポート**] \> [**テスト結果のダウンロード**] の順に選択します。 詳細については、「[監査ログの検索](search-the-audit-log-in-security-and-compliance.md)」を参照してください。
  
 監査ログ検索のすべての結果をエクスポートすると、統合監査ログの生データが、ローカル コンピューターにダウンロードされるコンマ区切り値 (CSV) ファイルにコピーされます。 このファイルには、[**AuditData**] という名前の列にある各監査レコードからの追加情報が入っています。 この列には、監査ログ レコードからの複数のプロパティに対する複数値プロパティが含まれています。 この複数値プロパティに含まれる各 **プロパティ: 値** ペアはカンマで区切られています。 
  
次の表では、マルチプロパティ **AuditData** 列に含まれるプロパティ (イベントが発生するサービスに応じて) について説明します。 **このプロパティ列を持つ Office 365 サービス** は、プロパティが含まれるサービスとアクティビティの種類 (ユーザーまたは管理者) を示します。 これらのプロパティまたはこのトピックに記載されていないプロパティの詳細については、「 [管理アクティビティ API スキーマ」を](/office/office-365-management-api/office-365-management-activity-api-schema)参照してください。
  
> [!TIP]
> Excel の Power Query に含まれる JSON 変換機能を使用すると、[**AuditData**] 列を複数の列に分割し、プロパティごとに個別の列を設定できます。 このようにすると、これらの 1 つ以上のプロパティで並べ替えやフィルター処理を行うことができます。 これを行う方法については、「[監査ログ レコードをエクスポート、構成、表示する](export-view-audit-log-records.md)」を参照してください。 
  
|**Property**|**説明**|**このプロパティを持つサービスをMicrosoft 365する**|
|:-----|:-----|:-----|
|Actor|アクションを実行したユーザーまたはサービス アカウント。|Azure Active Directory|
|AddOnName|チームで追加、削除、または更新されたアドオンの名前。 Microsoft Teams のアドオンの種類には、ボット、コネクタ、またはタブがあります。|Microsoft Teams|
|AddOnType|チームで追加、削除、または更新されたアドオンの種類。次の値によって、アドオンの種類が示されます。<br/> **1** -ボットを意味します。<br/> **2** -コネクタを意味します。<br/> **3** -タブを意味します。|Microsoft Teams|
|AzureActiveDirectoryEventType|Azure Active Directory のイベントの種類。次の値によって、イベントの種類が示されます。<br/> **0** - アカウント ログイン イベントを意味します。<br/> **1** - Azure アプリケーション セキュリティ イベントを意味します。|Azure Active Directory|
|ChannelGuid|Microsoft Teams のチャネルの ID。チャネルが置かれているチームは、**TeamName** プロパティと **TeamGuid** プロパティによって識別されます。|Microsoft Teams|
|ChannelName|Microsoft Teams のチャネルの名前。チャネルが置かれているチームは、**TeamName** プロパティと **TeamGuid** プロパティによって識別されます。|Microsoft Teams|
|Client|ログイン イベントに使用されたクライアント デバイスと、そのデバイスの OS およびブラウザー (例: Nokia Lumia 920、Windows Phone 8、IE Mobile 11)。|Azure Active Directory|
|ClientInfoString|操作を実行するために使用されたメール クライアントに関する情報 (ブラウザーのバージョン、Outlook のバージョン、およびモバイル デバイスの情報など)。|Exchange (メールボックス アクティビティ)|
|ClientIP|アクティビティがログに記録されたときに使用されたデバイスの IP アドレス。IP アドレスは、IPv4 または IPv6 アドレスの形式で表示されます。<br/><br/> 一部のサービスでは、このプロパティに表示される値は、ユーザーに代わってサービスを呼び出す信頼できるアプリケーション (Office on the web アプリなど) の IP アドレスであり、アクティビティを実行したユーザーが使用するデバイスの IP アドレスではない場合があります。 <br/><br/>また、Azure Active Directory 関連のイベントの管理者のアクティビティ (またはシステムアカウントによって実行されるアクティビティ) の場合、IP アドレスはログに記録されず、ClientIP プロパティの値は `null` になります。 |Azure Active Directory、Exchange、SharePoint|
|CreationTime|ユーザーがアクティビティを実行した、世界協定時刻 (UTC) での日時。|すべて|
|DestinationFileExtension|コピーまたは移動されたファイルのファイル拡張子。このプロパティは、FileCopied および FileMoved ユーザー アクティビティに対してのみ表示されます。|SharePoint|
|DestinationFileName|コピーまたは移動されたファイルの名前。このプロパティは、FileCopied および FileMoved アクションに対してのみ表示されます。|SharePoint|
|DestinationRelativeUrl|ファイルのコピー先または移動先フォルダーの URL。 **SiteURL**、**DestinationRelativeURL**、および **DestinationFileName** プロパティの値の組み合わせは、**ObjectID** プロパティの値と同じであり、コピーされたファイルの完全パス名です。 このプロパティは、FileCopied および FileMoved ユーザー アクティビティに対してのみ表示されます。|SharePoint|
|EventSource|SharePoint でイベントが発生したことを示します。有効な値は、**SharePoint** と **ObjectModel** です。|SharePoint|
|ExternalAccess|Exchange 管理者のアクティビティの場合は、組織内のユーザー、Microsoft データセンター担当者またはデータセンター サービス アカウント、あるいは代理管理者によってコマンドレットが実行されたことを示します。値 **False** は、コマンドレットが組織内のユーザーによって実行されたことを意味します。値 **True** は、コマンドレットがデータセンター担当者、データセンター サービス アカウント、または代理管理者によって実行されたことを意味します。<br/> Exchange メールボックス アクティビティの場合は、メールボックスにアクセスしたのが組織外のユーザーであるかどうかを示します。|Exchange|
|ExtendedProperties|Azure Active Directory イベントの拡張プロパティ。|Azure Active Directory|
|ID|レポート エントリの ID。この ID は、レポート エントリを一意に識別します。|すべて|
|InternalLogonType|内部使用のため予約済み。|Exchange (メールボックス アクティビティ)|
|ItemType|アクセスまたは変更されたオブジェクトの種類。設定できる値は、**File**、**Folder**、**Web**、**Site**、**Tenant**、および **DocumentLibrary** です。|SharePoint|
|LoginStatus|発生した可能性のあるログイン失敗を識別します。|Azure Active Directory|
|LogonType|メールボックス アクセスの種類。次の値によって、メールボックスにアクセスしたユーザーの種類が示されます。<br/><br/> **0** - メールボックスの所有者を意味します。<br/> **1** - 管理者を意味します。<br/> **2** - 代理人を意味します。 <br/>**3** - Microsoft データセンターのトランスポート サービスを意味します。<br/> **4** - Microsoft データセンターのサービス アカウントを意味します。 <br/>**6** - 代理管理者を意味します。|Exchange (メールボックス アクティビティ)|
|MailboxGuid|アクセスされたメールボックスの Exchange GUID。|Exchange (メールボックス アクティビティ)|
|MailboxOwnerUPN|アクセスされたメールボックスの所有者のメール アドレス。|Exchange (メールボックス アクティビティ)|
|Members|チームで追加または削除されたユーザーが一覧表示されます。次の値によって、ユーザーに割り当てられているロールの種類が示されます。<br/><br/> **1** - 所有者ロールを意味します。<br/> **2** - メンバー ロールを意味します。<br/> **3** - ゲスト ロールを意味します。 <br/><br/>Members プロパティには、組織の名前とメンバーのメール アドレスも含まれます。|Microsoft Teams|
|ModifiedProperties (Name、NewValue、OldValue)|このプロパティは、管理イベント (サイトまたはサイト コレクションの管理者グループのメンバーとしてユーザーを追加するなど) に対して表示されます。このプロパティには、変更されたプロパティの名前 (サイト管理者グループなど)、変更されたプロパティの新しい値 (サイト管理者として追加されたユーザーなど)、および変更されたオブジェクトの以前の値が格納されます。|すべて (管理者のアクティビティ)|
|ObjectId|Exchange 管理者の監査ログの場合は、コマンドレットによって変更されたオブジェクトの名前。  <br/> SharePoint アクティビティの場合は、ユーザーがアクセスしたファイルまたはフォルダーの完全な URL パス名。  <br/> Azure AD アクティビティの場合は、変更されたユーザー アカウントの名前。|すべて|
|Operation|ユーザーまたは管理アクティビティの名前。 このプロパティの値は、[**アクティビティ**] ドロップ ダウン リストで選択した値に対応します。 [**すべてのアクティビティの結果を表示**] を選択した場合、レポートにはすべてのサービスのすべてのユーザーと管理アクティビティのエントリが取り込まれます。 監査ログに記録される操作/アクティビティの説明については、Office 365の監査ログを検索するの監査 **アクティビティ** タブ [を](search-the-audit-log-in-security-and-compliance.md)参照してください。  <br/> Exchange 管理者アクティビティでは、このプロパティは、実行されたコマンドレットの名前を識別します。|すべて|
|OrganizationId|組織の GUID。|すべて|
|Path|アクセスされたメッセージが置かれているメールボックス フォルダーの名前。このプロパティは、メッセージの作成先、コピー先、移動先のフォルダーも識別します。|Exchange (メールボックス アクティビティ)|
|Parameters|Exchange 管理者のアクティビティの場合、Operation プロパティで識別されたコマンドレットで使用された、すべてのパラメーターの名前と値。|Exchange (管理者のアクティビティ)|
|RecordType|レコードによって示される操作の種類。 このプロパティは、操作がトリガーされたサービスまたは機能を示します。 レコードの種類とその対応する ENUM 値 (監査レコードの **RecordType** プロパティに表示される値) の一覧については、「 [監査ログ レコードの種類](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype)」を参照してください。| 
|ResultStatus|(**Operation** プロパティで指定された) アクションが正常に終了したかどうかを示します。  <br/> Exchange 管理者アクティビティでは、値は **True** (成功) または **False** (失敗) のいずれかになります。|すべて  <br/>|
|SecurityComplianceCenterEventType|アクティビティがコンプライアンス ポータル イベントであったことを示します。 すべてのコンプライアンス センター アクティビティには、このプロパティの値 **が 0 になります** 。|セキュリティ/コンプライアンス センター|
|SharingType|リソースが共有されたユーザーに割り当てられているアクセス許可の種類。このユーザーは、**UserSharedWith** プロパティによって識別されます。|SharePoint|
|Site|ユーザーがアクセスしたファイルまたはフォルダーが置かれているサイトの GUID。|SharePoint|
|SiteUrl|ユーザーがアクセスしたファイルまたはフォルダーが置かれているサイトの URL。|SharePoint|
|SourceFileExtension|ユーザーがアクセスしたファイルのファイル拡張子。アクセスされたオブジェクトがフォルダーの場合、このプロパティは空白になります。|SharePoint|
|SourceFileName|ユーザーがアクセスしたファイルまたはフォルダーの名前。|SharePoint|
|SourceRelativeUrl|ユーザーがアクセスするファイルが含まれているフォルダーの URL。 **SiteURL**、**SourceRelativeURL**、および **SourceFileName** プロパティの値の組み合わせは、**ObjectID** プロパティの値と同じであり、ユーザーがアクセスするファイルの完全パス名です。|SharePoint|
|Subject|アクセスされたメッセージの件名。|Exchange (メールボックス アクティビティ)|
|TabType| チームで追加、削除、または更新されたタブの種類。このプロパティの有効な値は次のとおりです。<br/><br/> **Excel pin** - Excel のタブ。  <br/> **Extension** - すべてのファースト パーティおよびサード パーティのアプリ (Class Schedule、VSTS、Forms など)。  <br/> **Notes** - OneNote のタブ。  <br/> **Pdfpin** - PDF のタブ。  <br/> **Powerbi** - [Power BI] タブ。  <br/> **Powerpointpin** - PowerPoint のタブ。  <br/> **Sharepointfiles** - SharePoint のタブ。  <br/> **Webpage** - ピン留めされた Web サイトのタブ。  <br/> **Wiki-tab** - Wiki のタブ。  <br/> **Wordpin** - Word のタブ。|Microsoft Teams|
|Target|(**Operation** プロパティで識別された) アクションの実行対象となったユーザー。たとえば、SharePoint または Microsoft Team にゲスト ユーザーが追加されると、このプロパティにそのユーザーが一覧表示されます。|Azure Active Directory|
|TeamGuid|Microsoft Teams のチームの ID。|Microsoft Teams|
|TeamName|Microsoft Teams のチームの名前。|Microsoft Teams|
|UserAgent|ユーザーのブラウザーに関する情報。この情報は、ブラウザーによって提供されます。|SharePoint|
|UserDomain|アクションを実行したユーザー (アクター) のテナント組織に関する情報を示します。|Azure Active Directory|
|UserId|結果としてログ記録されているレコードが生成されたアクション (**Operation** プロパティで指定された) を実行したユーザー。 システム アカウント (SHAREPOINT\system または NT AUTHORITY\SYSTEM など) によって実行されたアクティビティの監査レコードも監査ログに含まれます。 UserId プロパティのもう 1 つの一般的な値は app@sharepoint です。 これは、アクティビティを実行した "ユーザー" が、ユーザー、管理者、またはサービスの代理として、組織全体のアクション (SharePoint サイトまたは OneDrive アカウント検索など) を実行するために必要な アクセス許可が SharePoint に与えられているアプリケーションであることを示しています。 <br/><br/>詳細については、以下を参照してください。<br/> [監査レコード内の appsharepoint\@ ユーザー](search-the-audit-log-in-security-and-compliance.md#the-appsharepoint-user-in-audit-records)<br/> or <br/>[Exchange メールボックス監査レコード内のシステム アカウント](search-the-audit-log-in-security-and-compliance.md#system-accounts-in-exchange-mailbox-audit-records)。 |すべて|
|UserKey|**UserID** プロパティで識別されたユーザーの別の ID。このプロパティには、たとえば SharePoint でユーザーによって発生したイベントの Passport 固有 ID (PUID) が格納されます。このプロパティは、他のサービスで発生したイベントや、システム アカウントによって発生したイベントの **UserID** プロパティと同じ値を示す場合もあります。|すべて|
|UserSharedWith|リソースが共有されたユーザー。**Operation** プロパティの値が **SharingSet** の場合は、このプロパティが含まれます。このユーザーは、レポートの **[共有ユーザー]** 列にも表示されます。|SharePoint|
|UserType|操作を実行したユーザーの種類。次の値によって、ユーザーの種類が示されます。<br/> <br/> **0** - 標準のユーザー。 <br/>**2** - Microsoft 365組織内の管理者。<sup>1</sup> <br/>**3** - Microsoft データセンター管理者またはデータセンターのシステム アカウント。 <br/>**4** - システム アカウント。 <br/>**5** - アプリケーション。 <br/>**6** - サービス プリンシパル。<br/>**7** - カスタム ポリシー。<br/>**8** - システム ポリシー。|すべて|
|Version|ログに記録された (**Operation** プロパティで識別された) アクティビティのバージョン番号を示します。|すべて|
|Workload|アクティビティが発生したMicrosoft 365 サービス。|すべて|
||||

> [!NOTE]
><sup>1</sup> Azure Active Directory 関連のイベントの場合、管理者の値は監査レコードで使用されません。 管理者によって実行されたアクティビティの監査レコードは、通常のユーザー (たとえば、**UserType: 0**) がアクティビティを実行したことを意味します。 **UserID** プロパティは、アクティビティを実行したユーザー (通常のユーザーまたは管理者) を識別します。
