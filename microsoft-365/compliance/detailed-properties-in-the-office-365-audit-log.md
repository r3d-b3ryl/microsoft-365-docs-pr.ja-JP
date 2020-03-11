---
title: Office 365 監査ログの詳細なプロパティ
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- BCS160
- MET150
ms.assetid: ce004100-9e7f-443e-942b-9b04098fcfc3
description: Office 365 監査ログ レコードに含まれている追加のプロパティについて説明します。
ms.openlocfilehash: 82425348129011095012d3ada75f378150381f08
ms.sourcegitcommit: 0b2c41dad19da5f0513097c36a4ff32a5868836c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2020
ms.locfileid: "42588730"
---
# <a name="detailed-properties-in-the-office-365-audit-log"></a>Office 365 監査ログの詳細なプロパティ

監査ログの検索結果をセキュリティ/コンプライアンス センターからエクスポートする場合は、検索条件に一致するすべての結果をダウンロードするオプションを利用できます。 このエクスポートを行うには、[**監査ログの検索**] ページで、[**結果のエクスポート**] \> [**テスト結果のダウンロード**] の順に選択します。 詳細については、「[Search the audit log in the Office 365 (Office 365 での監査ログの検索)](search-the-audit-log-in-security-and-compliance.md)」を参照してください。
  
 監査ログ検索のすべての結果をエクスポートする場合、Office 365 の統一監査ログからの未処理のデータは、ローカル コンピューターにダウンロードされたカンマ区切り値 (CSV) ファイルにコピーされます。 このファイルには、[**AuditData**] という名前の列にある各監査レコードからの追加情報が入っています。 この列には、監査ログ レコードからの複数のプロパティに対する複数値プロパティが含まれています。 この複数値プロパティに含まれる各 **プロパティ: 値** ペアはカンマで区切られています。 
  
次の表では、(イベントが発生する Office 365 サービスに応じて) マルチ プロパティの [**AuditData**] 列に取り込まれるプロパティについて説明します。 **このプロパティ列を持つ Office 365 サービス**は、プロパティが含まれるサービスとアクティビティの種類 (ユーザーまたは管理者) を示します。 これらのプロパティの詳細情報またはこのトピックに一覧表示されていないプロパティの詳細情報については、「[Office 365 Management Activity API Schema (Office 365 管理アクティビティ API スキーマ)](https://go.microsoft.com/fwlink/p/?LinkId=717993)」を参照してください。
  
> [!TIP]
> Excel の Power Query に含まれる JSON 変換機能を使用すると、[**AuditData**] 列を複数の列に分割し、プロパティごとに個別の列を設定できます。 このようにすると、これらの 1 つ以上のプロパティで並べ替えやフィルター処理を行うことができます。 これを行う方法については、「[監査ログ レコードをエクスポート、構成、表示する](export-view-audit-log-records.md)」を参照してください。 
  
|**Property**|**説明**|**このプロパティを使用する Office 365 サービス**|
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
|ObjectId|Exchange 管理者監査ログの場合は、コマンドレットによって変更されたオブジェクトの名前。  <br/> SharePoint アクティビティの場合は、ユーザーがアクセスしたファイルまたはフォルダーの完全な URL パス名。  <br/> Azure AD アクティビティの場合は、変更されたユーザー アカウントの名前。|すべて|
|Operation|ユーザーまたは管理アクティビティの名前。 このプロパティの値は、[**アクティビティ**] ドロップ ダウン リストで選択した値に対応します。 [**すべてのアクティビティの結果を表示**] を選択した場合、レポートにはすべてのサービスのすべてのユーザーと管理アクティビティのエントリが取り込まれます。 Office 365 監査ログに記録される操作/アクティビティについては、「[Search the audit log in the Office 365 (Office 365 での監査ログの検索)](search-the-audit-log-in-security-and-compliance.md)」の [**監査されるアクティビティ**] タブを参照してください。  <br/> Exchange 管理者アクティビティでは、このプロパティは、実行されたコマンドレットの名前を識別します。|すべて|
|OrganizationId|Office 365 組織の GUID。|すべて|
|Path|アクセスされたメッセージが置かれているメールボックス フォルダーの名前。このプロパティは、メッセージの作成先、コピー先、移動先のフォルダーも識別します。|Exchange (メールボックス アクティビティ)|
|Parameters|Exchange 管理者のアクティビティの場合、Operation プロパティで識別されたコマンドレットで使用された、すべてのパラメーターの名前と値。|Exchange (管理者のアクティビティ)|
|RecordType|レコードで示されている操作の種類。次の値によって、レコードの種類が示されます。<br/><br/> **1** - Exchange 管理者監査ログのレコードを意味します。 <br/>**2** - Exchange メールボックス監査ログの、単一のメールボックス アイテムに対して行われた操作に関するレコードを意味します。 <br/>**3** - Exchange メールボックス監査ログからのレコードも示します。 このレコードの種類は、ソース メールボックス内の複数のアイテムに対して操作が実行されたことを示します (削除済みアイテム フォルダーへの複数のアイテムの移動、または複数のアイテムの完全な削除など)。 <br/>**4** - SharePoint でのサイト管理者の操作 (管理者またはユーザーがサイトに対するアクセス許可を割り当てるなど) を意味します。 <br/>**6** - SharePoint でのファイルまたはフォルダーに関連する操作 (ユーザーの表示、ファイルの変更など) を意味します。 <br/>**8** - Azure Active Directory で行われた管理者の操作を意味します。 <br/>**9** - Azure Active Directory での OrgId ログオン イベントを意味します。このレコードの種類は非推奨となっています。<br/>**10** - データ センターで Microsoft 担当者が行ったセキュリティ コマンドレット イベントを意味します。 <br/>**11** - SharePoint でのデータ損失防止 (DLP) イベントを意味します。<br/> **12** - Sway のイベントを意味します。 <br/>**13** - 統合 DLP ポリシーを使用して構成された場合の Exchange の DLP イベントを意味します。 Exchange メール フロー ルール (トランスポート ルールとも呼ばれます) に基づく DLP イベントはサポートされていません。<br>**14** - SharePoint の共有イベントを意味します。<br/> **15** - Azure Active Directory の Secure Token Service (STS) ログオン イベントを意味します。 <br/>**18** - セキュリティ/コンプライアンス センターのイベントを意味します。 <br/>**19** - 非常に短い期間内に発生する反復アクティビティが集約されたExchange メールボックスの操作を意味します。 <br/>**20** - Power BI のイベントを意味します。 <br/>**21**- Dynamics 365 のイベントを意味します。<br/>**22** - Yammer のイベントを意味します。 <br/>**23** - Skype for Business のイベントを意味します。 <br/>**24** - 電子情報開示のイベントを意味します。 このレコードの種類は、セキュリティ/コンプライアンス センターでコンテンツ検索を実行し、eDiscovery のケースを管理することによって実行されるアクティビティを意味します。 詳細については、「[Office 365 監査ログで電子情報開示アクティビティを検索する](search-for-ediscovery-activities-in-the-audit-log.md)」を参照してください。<br/>**25、26、27** - Microsoft Teams のイベントを意味します。 <br/>**28** - Exchange Online Protection と Office 365 Advanced Threat Protection からのフィッシングとマルウェアのイベントを意味します。<br/>**29** - Exchange Online Protection と Office 365 Advanced Threat Protection からのフィッシングとマルウェアの提出イベントを意味します。<br/>**30** - Microsoft Power Automate (旧称 Microsoft Flow) イベントを意味します。<br/> **31** - 高度な電子情報開示イベントを意味します。<br/> **32** - Microsoft Stream のイベントを意味します。<br/> **33** - SharePoint の DLP 分類に関連するイベントを意味します。<br/>**35** - Microsoft Project のイベントを意味します。 <br/> **36** - Sharepoint リストのイベントを意味します。<br/>**37** - SharePoint コメントに関連するイベントを意味します。 <br/>**38** - セキュリティ/コンプライアンス センターにおけるアイテム保持ポリシーと保持ラベルに関連するイベントを意味します。  <br/>**40** - セキュリティ/コンプライアンス アラートのシグナルに起因するイベントを意味します。<br/> **41** - Office 365 Advanced Threat Protection でのブロック時の安全なリンクと上書きのブロック イベントを意味します。<br/>**42** - Office 365 セキュリティおよびコンプライアンス センターの分析情報とレポートに関連するイベントを意味します。<br/>**44** - Workplace Analytics のイベントを意味します。 <br/>**45** - Power アプリのイベントを意味します。 <br/> **47** - SharePoint、OneDrive、Microsoft Teams 内のファイルに対する、Office 365 Advanced Threat Protection からのフィッシングとマルウェアのイベントを意味します。<br/> **49** - 医療関係向け Microsoft Teams の[患者アプリケーション](https://docs.microsoft.com/MicrosoftTeams/expand-teams-across-your-org/healthcare/patients-audit)に関連するイベントを意味します。 <br/>**50** - MailItemsAccessed メールボックス監査アクションに関連するイベントを意味します。 <br/>**52** - データ インサイト REST API に関連するイベントを意味します。<br/>**53** - 情報障壁ポリシーの適用に関連するイベントを意味します。 詳細については、「[Define policies for information barriers (情報障壁のポリシーを定義する)](information-barriers-policies.md)」を参照してください。 <br/>**54** - SharePoint リスト アイテム イベントを意味します。<br/>**55** - SharePoint コンテンツ タイプ イベントを意味します。<br/> **56** - SharePoint リスト フィールド イベントを意味します。 <br/>**62** - メール攻撃キャンペーンに関連するイベントを意味します。 詳細については、「[Office 365 ATP のキャンペーン ビュー](https://docs.microsoft.com/microsoft-365/security/office-365-security/campaigns)」を参照してください。<br/>**64** - 自動調査および対応イベントを意味します。 詳細については、「[Office 365 での自動調査および対応 (AIR)](../security/office-365-security/automated-investigation-response-office.md)」を参照してください<br/>**65** -検疫監査レコードイベントを示します。<br/>**66** - Microsoft Forms のイベントを意味します。<br/>**68** - Exchange の通信コンプライアンス イベントを示します。 詳細については、「[Microsoft 365 での通信コンプライアンス](communication-compliance.md)」を参照してください。<br/>**69** -顧客キーの暗号化に関連するイベントを示します。 詳細については、「[Service encryption with Customer Key in Office 365 (Office 365 カスタマー キーを使用したサービス暗号化)](customer-key-overview.md)」を参照してください。 
|ResultStatus|(**Operation** プロパティで指定された) アクションが正常に終了したかどうかを示します。  <br/> Exchange 管理者アクティビティでは、値は **True** (成功) または **False** (失敗) のいずれかになります。|すべて  <br/>|
|SecurityComplianceCenterEventType|アクティビティがセキュリティ/コンプライアンス センター イベントであることを意味します。 セキュリティ/コンプライアンス センター アクティビティはすべて、このプロパティの値が **0** です。|セキュリティ/コンプライアンス センター|
|SharingType|リソースが共有されたユーザーに割り当てられているアクセス許可の種類。このユーザーは、**UserSharedWith** プロパティによって識別されます。|SharePoint|
|Site|ユーザーがアクセスしたファイルまたはフォルダーが置かれているサイトの GUID。|SharePoint|
|SiteUrl|ユーザーがアクセスしたファイルまたはフォルダーが置かれているサイトの URL。|SharePoint|
|SourceFileExtension|ユーザーがアクセスしたファイルのファイル拡張子。アクセスされたオブジェクトがフォルダーの場合、このプロパティは空白になります。|SharePoint|
|SourceFileName|ユーザーがアクセスしたファイルまたはフォルダーの名前。|SharePoint|
|SourceRelativeUrl|ユーザーがアクセスするファイルが含まれているフォルダーの URL。 **SiteURL**、**SourceRelativeURL**、および **SourceFileName** プロパティの値の組み合わせは、**ObjectID** プロパティの値と同じであり、ユーザーがアクセスするファイルの完全パス名です。|SharePoint|
|Subject|アクセスされたメッセージの件名。|Exchange (メールボックス アクティビティ)|
|TabType| チームで追加、削除、または更新されたタブの種類。このプロパティの有効な値は次のとおりです。<br/><br/> **Excel pin** - Excel のタブ。  <br/> **Extension** - すべてのファースト パーティおよびサード パーティのアプリ (Class Schedule、VSTS、Forms など)。  <br/> **Notes** - OneNote のタブ。  <br/> **Pdfpin** - PDF のタブ。  <br/> **Powerbi** - PowerBI のタブ。  <br/> **Powerpointpin** - PowerPoint のタブ。  <br/> **Sharepointfiles** - SharePoint のタブ。  <br/> **Webpage** - ピン留めされた Web サイトのタブ。  <br/> **Wiki-tab** - Wiki のタブ。  <br/> **Wordpin** - Word のタブ。|Microsoft Teams|
|Target|(**Operation** プロパティで識別された) アクションの実行対象となったユーザー。たとえば、SharePoint または Microsoft Team にゲスト ユーザーが追加されると、このプロパティにそのユーザーが一覧表示されます。|Azure Active Directory|
|TeamGuid|Microsoft Teams のチームの ID。|Microsoft Teams|
|TeamName|Microsoft Teams のチームの名前。|Microsoft Teams|
|UserAgent|ユーザーのブラウザーに関する情報。この情報は、ブラウザーによって提供されます。|SharePoint|
|UserDomain|アクションを実行したユーザー (アクター) のテナント組織に関する情報を示します。|Azure Active Directory|
|UserId|結果としてログ記録されているレコードが生成されたアクション (**Operation** プロパティで指定された) を実行したユーザー。 システムアカウント (SHAREPOINT\system、NT AUTHORITY\SYSTEM など) によって実行されたアクティビティの監査レコードも、監査ログに含まれています。 UserId プロパティのもう1つの一般的な値は app@sharepoint です。 これは、アクティビティを実行した "ユーザー" が、ユーザー、管理者、またはサービスに代わって組織全体の操作 (SharePoint サイトまたは OneDrive アカウントの検索など) を実行するために、SharePoint で必要なアクセス許可を持つアプリケーションであったことを示しています。 詳細については、監査レコード内の[ app\@sharepoint ユーザーを参照してください](search-the-audit-log-in-security-and-compliance.md#the-appsharepoint-user-in-audit-records)。 |すべて|
|UserKey|**UserID** プロパティで識別されたユーザーの別の ID。このプロパティには、たとえば SharePoint でユーザーによって発生したイベントの Passport 固有 ID (PUID) が格納されます。このプロパティは、他のサービスで発生したイベントや、システム アカウントによって発生したイベントの **UserID** プロパティと同じ値を示す場合もあります。|すべて|
|UserSharedWith|リソースが共有されたユーザー。**Operation** プロパティの値が **SharingSet** の場合は、このプロパティが含まれます。このユーザーは、レポートの **[共有ユーザー]** 列にも表示されます。|SharePoint|
|UserType|操作を実行したユーザーの種類。次の値によって、ユーザーの種類が示されます。<br/> <br/> **0** - 標準のユーザー。 <br/>**2** - Office 365 組織の管理者。<sup>1</sup> <br/>**3** - Microsoft データセンター管理者またはデータセンターのシステム アカウント。 <br/>**4** - システム アカウント。 <br/>**5** - アプリケーション。 <br/>**6** - サービス プリンシパル。<br/>**7** - カスタム ポリシー。<br/>**8** - システム ポリシー。|すべて|
|Version|ログに記録された (**Operation** プロパティで識別された) アクティビティのバージョン番号を示します。|すべて|
|Workload|アクティビティが発生した Office 365 サービス。このプロパティの有効な値は次のとおりです。<br/> <br/>**SharePoint<br/>OneDrive<br/>Exchange<br/>AzureActiveDirectory<br/>DataCenterSecurity<br/>Compliance<br/>Sway<br/>Skype for Business<br/>SecurityComplianceCenter<br/>PowerBI<br/>CRM<br/>Yammer<br/>MicrosoftTeams<br/>ThreatIntelligence<br/>MicrosoftFlow<br/>MicrosoftStream<br/>DlpSharePointClassificationData<br/>Project<br/>PowerApps<br/>Workplace Analytics**<br/>**MicrosoftForms**<br/>**AirInvestigation**|すべて|
||||

> [!NOTE]
><sup>1</sup> Azure Active Directory 関連のイベントの場合、管理者の値は監査レコードで使用されません。 管理者によって実行されたアクティビティの監査レコードは、通常のユーザー (たとえば、**UserType: 0**) がアクティビティを実行したことを意味します。 **UserID** プロパティは、アクティビティを実行したユーザー (通常のユーザーまたは管理者) を識別します。<br/>

上記のプロパティは、特定のイベントの詳細が表示されている状態で [**詳細情報**] をクリックした場合にも表示されます。 
  
![[詳細情報] をクリックして監査ログのイベント レコードの詳細なプロパティを表示する](../media/6df582ae-d339-4735-b1a6-80914fb77a08.png)
