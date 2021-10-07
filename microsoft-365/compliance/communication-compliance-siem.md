---
title: SIEM ソリューションのコミュニケーション コンプライアンス
description: SIEM ソリューションとの通信コンプライアンスの統合について学習します。
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 0e49935ff1d280adf4c1567a2064496a475c6033
ms.sourcegitcommit: afee35210f8d68a7f20676ff2a829464b0b0adb2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2021
ms.locfileid: "60216948"
---
# <a name="communication-compliance-with-siem-solutions"></a>SIEM ソリューションのコミュニケーション コンプライアンス

[コミュニケーション コンプライアンスは](communication-compliance.md)、組織内の不適切なメッセージMicrosoft 365検出、キャプチャ、および操作を支援することで、コミュニケーション リスクを最小限に抑える、コミュニケーション コンプライアンスのインサイダー リスク ソリューションです。 [Azure Sentinel](https://azure.microsoft.com/services/azure-sentinel)や[Splunk](https://www.splunk.com/)などのセキュリティ情報とイベント管理 (SIEM) ソリューションは、組織内の脅威を集約および追跡するためによく使用されます。

組織の一般的なニーズは、コミュニケーション コンプライアンスアラートとこれらの SIEM ソリューションを統合する必要があります。 この統合により、組織は SIEM ソリューションで通信コンプライアンスアラートを表示し、通信コンプライアンス ワークフローとユーザー エクスペリエンス内でアラートを修復できます。 たとえば、従業員が別の従業員に不快なメッセージを送信し、そのメッセージは不快な言語の通信コンプライアンス ポリシー監視によって検出されます。 これらのイベントは、Microsoft 365 コンプライアンス ソリューションによって監査 ("統合監査ログ" とも呼ばれる) で追跡され、SIEM ソリューションにインポートされます。 その後、組織の SIEM ソリューションで、通信コンプライアンス通知に関連付けられている監査で監視Microsoft 365イベントからアラートがトリガーされます。 調査担当者は、SIEM ソリューションでアラートの通知を受け取り、通信コンプライアンス ソリューションでアラートを調査して修復します。

## <a name="communication-compliance-alerts-in-microsoft-365-audit"></a>[監査] での通信コンプライアンスMicrosoft 365通知

すべての通信コンプライアンス ポリシーの一致は、監査にMicrosoft 365されます。 次の例は、選択した通信コンプライアンス ポリシーの一致アクティビティで使用可能な詳細を示しています。

**不快な言語ポリシー テンプレートの一致の監査ログ エントリの例:**

```xml
RunspaceId: 5c7bc9b0-7672-4091-a112-0635bd5f7732
RecordType: ComplianceSupervisionExchange
CreationDate: 7/7/2021 5:30:11 AM
UserIds: user1@contoso.onmicrosoft.com
Operations: SupervisionRuleMatch
AuditData: {"CreationTime":"2021-07-07T05:30:11","Id":"44e98a7e-57fd-4f89-79b8-08d941084a35","Operation":"SupervisionRuleMatch","OrganizationId":"338397e6\-697e-4dbe-a66b-2ea3497ef15c","RecordType":68,"ResultStatus":"{\\"ItemClass\\":\\"IPM.Note\\",\\"CcsiResults\\":\\"\\"}","UserKey":"SupervisionStoreDeliveryAgent","UserType":0,"Version":1,"Workload":"Exchange","ObjectId":"\<HE1P190MB04600526C0524C75E5750C5AC61A9@HE1P190MB0460.EURP190.PROD.OUTLOOK.COM\>","UserId":"user1@contoso.onmicrosoft.com","IsPolicyHit":true,"SRPolicyMatchDetails":{"SRPolicyId":"53be0bf4-75ee-4315-b65d-17d63bdd53ae","SRPolicyName":"Adult images","SRRuleMatchDetails":\[\]}}
ResultIndex: 24
ResultCount: 48
Identity: 44e98a7e-57fd-4f89-79b8-08d941084a35
IsValid: True
ObjectState: Unchanged
```

**カスタム キーワード一致Microsoft 365ポリシーの監査ログ エントリの例 (カスタム機密情報の種類):**

```xml
RunspaceId: 5c7bc9b0-7672-4091-a112-0635bd5f7732
RecordType: ComplianceSupervisionExchange
CreationDate: 7/6/2021 9:50:12 PM
UserIds: user2@contoso.onmicrosoft.com
Operations: SupervisionRuleMatch
AuditData: {"CreationTime":"2021-07-06T21:50:12","Id":"5c61aae5-26fc-4c8e-0791-08d940c8086f","Operation":"SupervisionRuleMatch","OrganizationId":"338397e6\-697e-4dbe-a66b-2ea3497ef15c","RecordType":68,"ResultStatus":"{\\"ItemClass\\":\\"IPM.Note\\",\\"CcsiResults\\":\\"public\\"}","UserKey":"SupervisionStoreDeliveryAgent","UserType":0,"Version":1,"Workload":"Exchange","ObjectId":"\<20210706174831.24375086.807067@sailthru.com\>","UserId":"user2@contoso.onmicrosoft.com","IsPolicyHit":true,"SRPolicyMatchDetails":{"SRPolicyId":"a97cf128-c0fc-42a1-88e3-fd3b88af9941","SRPolicyName":"Insiders","SRRuleMatchDetails":\[{"SRCategoryName":"New insiders lexicon"}\]}}
ResultIndex: 46
ResultCount: 48
Identity: 5c61aae5-26fc-4c8e-0791-08d940c8086f
IsValid: True
ObjectState: Unchanged
```

> [!NOTE]
> 現在、ポリシーの一致が Microsoft 365 Audit に記録される時間と、通信コンプライアンスでポリシーの一致を調査できる時間の間に最大 24 時間の遅延が発生する可能性があります。

## <a name="configure-communication-compliance-and-azure-sentinel-integration"></a>通信コンプライアンスと Azure Sentinel 統合の構成

Azure Sentinel を使用して通信コンプライアンス ポリシーの一致を集約する場合、Sentinel はデータ ソースとして Microsoft 365監査を使用します。 通信コンプライアンスアラートを Sentinel に統合するには、次の手順を実行します。

1. [Azure Sentinel にオンボードします](/azure/sentinel/quickstart-onboard)。 オンボーディング プロセスの一環として、データ ソースを構成します。
2. データ コネクタで Azure Sentinel [Microsoft Office 365を構成](/azure/sentinel/data-connectors-reference#microsoft-office-365)し、コネクタ構成の下で [データ の構成]*を* Exchange。
3. 通信コンプライアンスアラートを取得する検索クエリを構成します。 次に例を示します。

    *|OfficeActivity |ここで、OfficeWorkload == "Exchange" と Operation == "SupervisionRuleMatch" |TimeGenerated による並べ替え*

    特定のユーザーをフィルター処理するには、次のクエリ形式を使用します。

    *|OfficeActivity |ここで、OfficeWorkload == "Exchange" と Operation == "SupervisionRuleMatch" と UserId == "User1@Contoso.com" |TimeGenerated による並べ替え*

Azure Sentinel によって収集されるMicrosoft 365監査ログOffice 365詳細については[、「Azure Monitor Logs リファレンス」を参照してください](/azure/azure-monitor/reference/tables/OfficeActivity)。

## <a name="configure-communication-compliance-and-splunk-integration"></a>通信コンプライアンスと Splunk 統合の構成

通信コンプライアンスアラートを Splunk と統合するには、次の手順を実行します。

1. ユーザー向[け Splunk アドオンをインストールMicrosoft Office 365](https://docs.splunk.com/Documentation/AddOns/released/MSO365/ConfigureinputsmanagementAPI)
2. Splunk アドオン用に Azure AD統合アプリケーションを構成するMicrosoft Office 365
3. Splunk ソリューションで検索クエリを構成します。 次の検索例を使用して、すべての通信コンプライアンスアラートを識別します。

    *index= \* sourcetype="o365:management:activity" Workload=Exchange Operation=SupervisionRuleMatch*

特定の通信コンプライアンス ポリシーの結果をフィルター処理するには *、SRPolicyMatchDetails.SRPolicyName パラメーターを使用* できます。

たとえば、次の検索例は、不快な言語という名前の通信コンプライアンス ポリシーに一致するアラート *を返します*。

  *index= \* sourcetype='o365:management:activity' Workload=Exchange Operation=SupervisionRuleMatch SRPolicyMatchDetails.SRPolicyName=\<Offensive language\>*

次の表に、さまざまなポリシーの種類の検索結果の例を示します。

| ポリシーの種類 | 検索結果の例 |
| :------------------ | :--------------------------------------- |
| カスタムの機密情報の種類のキーワード リストを検出するポリシー | { <br> CreationTime: 2021-09-17T16:29:57 <br> ID: 4b9ce23d-ee60-4f66-f38d-08d979f8631f <br> IsPolicyHit: true <br> ObjectId: <CY1PR05MB27158B96AF7F3AFE62E1F762CFDD9@CY1PR05MB2715.namprd05.prod.outlook.com> <br> 操作: SupervisionRuleMatch <br> OrganizationId: d6a06676-95e8-4632-b949-44bc00f0793f <br> RecordType: 68 <br> ResultStatus: {"ItemClass":"IPM。Note","CcsiResults":"leak"} <br> SRPolicyMatchDetails: { [+] } <br> UserId: user1@contoso。OnMicrosoft.com <br> UserKey: SupervisionStoreDeliveryAgent <br> UserType: 0 <br> バージョン: 1 <br> ワークロード: Exchange <br> } |
| 不適切な言語を検出するポリシー | { <br> CreationTime: 2021-09-17T23:44:35 <br> ID: e0ef6f54-9a52-4e4c-9584-08d97a351ad0 <br> IsPolicyHit: true <br> ObjectId: <BN6PR05MB3571AD9FBB85C4E12C1F66B4CCDD9@BN6PR05MB3571.namprd05.prod.outlook.com> <br> 操作: SupervisionRuleMatch <br> OrganizationId: d6a06676-95e8-4632-b949-44bc00f0793f <br> RecordType: 68 <br> ResultStatus: {"ItemClass":"IPM.Yammer。Message","CcsiResults":""} <br> SRPolicyMatchDetails: { [+] } <br> UserId: user1@contoso.com <br> UserKey: SupervisionStoreDeliveryAgent <br> UserType: 0 <br> バージョン: 1 <br> }  |

## <a name="configure-communication-compliance-with-other-siem-solutions"></a>他の SIEM ソリューションとの通信コンプライアンスを構成する

監査から通信コンプライアンス ポリシーの一致Microsoft 365取得するには、PowerShell または Office 365 管理[API を使用します](/office/office-365-management-api/office-365-management-activity-api-reference)。

PowerShell を使用する場合は **、Search-UnifiedAuditLog** コマンドレットでこれらのパラメーターのいずれかを使用して、通信コンプライアンス アクティビティの監査ログ イベントをフィルター処理できます。

| 監査ログ パラメーター | 通信コンプライアンス パラメーターの値 |
| :------------------ | :--------------------------------------- |
| 操作          | SupervisionRuleMatch                     |
| RecordType          | ComplianceSupervisionExchange            |

たとえば、Operations パラメーターと *SupervisionRuleMatch* 値を使用したサンプル検索を次に示します。 

```powershell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -Operations SupervisionRuleMatch | ft CreationDate,UserIds,AuditData
```
**RecordsType** パラメーターと *ComplianceSupervisionExchange* 値を使用したサンプル検索を次に示します。

```powershell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType ComplianceSuperVisionExchange | ft CreationDate,UserIds,AuditData
```
## <a name="resources"></a>リソース

- [コミュニケーション コンプライアンス監査](communication-compliance-feature-reference.md#audit)
- [Microsoft 365 の高度な監査](advanced-audit.md)
- [Office 365 管理アクティビティ API リファレンス](/office/office-365-management-api/office-365-management-activity-api-reference)
