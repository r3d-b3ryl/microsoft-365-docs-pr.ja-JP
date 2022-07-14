---
title: SIEM ソリューションのコミュニケーション コンプライアンスの使用
description: SIEM ソリューションとの通信コンプライアンスの統合について説明します。
keywords: Microsoft 365、Microsoft Purview、コンプライアンス、通信コンプライアンス
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
ms.openlocfilehash: 2413cee978fa2fe66a2672e307e8cad12a7b803b
ms.sourcegitcommit: 221212fff9737e0ea386755deb8fed62ae9c254b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2022
ms.locfileid: "66787037"
---
# <a name="use-communication-compliance-with-siem-solutions"></a>SIEM ソリューションのコミュニケーション コンプライアンスの使用

[コミュニケーション コンプライアンス](/microsoft-365/compliance/communication-compliance) は Microsoft Purview のインサイダー リスク ソリューションであり、組織内の不適切なメッセージを検出、キャプチャ、および操作できるようにすることで、コミュニケーション リスクを最小限に抑えることができます。 [Microsoft Sentinel](https://azure.microsoft.com/services/azure-sentinel) や [Splunk](https://www.splunk.com/) などのセキュリティ情報とイベント管理 (SIEM) ソリューションは、組織内の脅威の集計と追跡に一般的に使用されます。

組織の一般的なニーズは、通信コンプライアンス アラートとこれらの SIEM ソリューションを統合することです。 この統合により、組織は SIEM ソリューションで通信コンプライアンス アラートを表示し、通信コンプライアンス ワークフローとユーザー エクスペリエンス内のアラートを修復できます。 たとえば、従業員は別の従業員に不快なメッセージを送信し、そのメッセージは不適切なコンテンツに対するコミュニケーション コンプライアンス ポリシーによって検出されます。 これらのイベントは、通信コンプライアンス ソリューションによって Microsoft 365 監査 ("統合監査ログ" とも呼ばれます) で追跡され、SIEM ソリューションにインポートされます。 その後、通信コンプライアンス アラートに関連付けられている Microsoft 365 監査に含まれるイベントから、組織の SIEM ソリューションでアラートがトリガーされます。 調査担当者には SIEM ソリューションでアラートが通知され、通信コンプライアンス ソリューションでアラートを調査して修復します。

## <a name="communication-compliance-alerts-in-microsoft-365-audit"></a>Microsoft 365 監査の通信コンプライアンス アラート

すべての通信コンプライアンス ポリシーの一致は、Microsoft 365 監査でキャプチャされます。 次の例は、選択した通信コンプライアンス ポリシー一致アクティビティで使用できる詳細を示しています。

**不適切なコンテンツ ポリシー テンプレート一致の監査ログ エントリの例:**

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

**カスタム キーワード一致 (カスタム機密情報の種類) を持つポリシーの Microsoft 365 監査ログ エントリの例:**

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
> 現時点では、ポリシー一致が Microsoft 365 監査に記録されてから、ポリシーの一致を通信コンプライアンスで調査できる時間までの間に、最大で 24 時間の遅延が発生する可能性があります。

## <a name="configure-communication-compliance-and-microsoft-sentinel-integration"></a>通信コンプライアンスと Microsoft Sentinel 統合を構成する

Microsoft Sentinel を使用して通信コンプライアンス ポリシーの一致を集計する場合、Sentinel はデータ ソースとして Microsoft 365 監査を使用します。 通信コンプライアンス アラートを Sentinel と統合するには、次の手順を実行します。

1. [Microsoft Sentinel にオンボード](/azure/sentinel/quickstart-onboard)します。 オンボード プロセスの一環として、データ ソースを構成します。
2. Microsoft Sentinel [Microsoft Office 365 データ コネクタ](/azure/sentinel/data-connectors-reference#microsoft-office-365)を構成し、コネクタの構成で *Exchange* を選択します。
3. 通信コンプライアンス アラートを取得するように検索クエリを構成します。 次に例を示します。

    *|OfficeActivity |ここで、OfficeWorkload == "Exchange" と Operation == "SupervisionRuleMatch" |TimeGenerated で並べ替える*

    特定のユーザーをフィルター処理するには、次のクエリ形式を使用します。

    *|OfficeActivity |ここで、OfficeWorkload == "Exchange" と Operation == "SupervisionRuleMatch" と UserId == "User1@Contoso.com" |TimeGenerated で並べ替える*

Microsoft Sentinel によって収集されたOffice 365の Microsoft 365 監査ログの詳細については、「[Azure Monitor ログ リファレンス」を参照してください](/azure/azure-monitor/reference/tables/OfficeActivity)。

## <a name="configure-communication-compliance-and-splunk-integration"></a>通信コンプライアンスと Splunk 統合を構成する

通信コンプライアンス アラートを Splunk と統合するには、次の手順を実行します。

1. [Microsoft Office 365用の Splunk アドオンを](https://docs.splunk.com/Documentation/AddOns/released/MSO365/ConfigureinputsmanagementAPI)インストールする
2. Microsoft Office 365用の Splunk アドオン用に Azure AD で統合アプリケーションを構成する
3. Splunk ソリューションで検索クエリを構成します。 次の検索例を使用して、すべての通信コンプライアンス アラートを識別します。

    *index=\* sourcetype="o365:management:activity" Workload=Exchange Operation=SupervisionRuleMatch*

特定の通信コンプライアンス ポリシーの結果をフィルター処理するには、 *SRPolicyMatchDetails.SRPolicyName* パラメーターを使用します。

たとえば、次の検索例は、 *不適切なコンテンツ* という名前の通信コンプライアンス ポリシーに一致するアラートを返します。

  *index=\* sourcetype='o365:management:activity' Workload=Exchange Operation=SupervisionRuleMatch SRPolicyMatchDetails.SRPolicyName=\<Inappropriate content\>*

次の表は、さまざまなポリシーの種類のサンプル検索結果を示しています。

| ポリシーの種類 | 検索結果の例 |
| :------------------ | :--------------------------------------- |
| カスタムの機密情報の種類のキーワード リストを検出するポリシー | { <br> CreationTime: 2021-09-17T16:29:57 <br> ID: 4b9ce23d-ee60-4f66-f38d-08d979f8631f <br> IsPolicyHit: true <br> Objectid： <CY1PR05MB27158B96AF7F3AFE62E1F762CFDD9@CY1PR05MB2715.namprd05.prod.outlook.com> <br> 操作: SupervisionRuleMatch <br> OrganizationId: d6a06676-95e8-4632-b949-44bc00f0793f <br> RecordType: 68 <br> ResultStatus: {"ItemClass":"IPM。注","CcsiResults":"leak"} <br> SRPolicyMatchDetails: { [+] } <br> UserId: user1@contoso.OnMicrosoft.com <br> UserKey: SupervisionStoreDeliveryAgent <br> UserType: 0 <br> バージョン: 1 <br> ワークロード: Exchange <br> } |
| 不適切な言語を検出するポリシー | { <br> CreationTime: 2021-09-17T23:44:35 <br> ID: e0ef6f54-9a52-4e4c-9584-08d97a351ad0 <br> IsPolicyHit: true <br> Objectid： <BN6PR05MB3571AD9FBB85C4E12C1F66B4CCDD9@BN6PR05MB3571.namprd05.prod.outlook.com> <br> 操作: SupervisionRuleMatch <br> OrganizationId: d6a06676-95e8-4632-b949-44bc00f0793f <br> RecordType: 68 <br> ResultStatus: {"ItemClass":"IPM。Yammer.Message","CcsiResults":"} <br> SRPolicyMatchDetails: { [+] } <br> UserId: user1@contoso.com <br> UserKey: SupervisionStoreDeliveryAgent <br> UserType: 0 <br> バージョン: 1 <br> }  |

## <a name="configure-communication-compliance-with-other-siem-solutions"></a>他の SIEM ソリューションとの通信コンプライアンスを構成する

Microsoft 365 監査から通信コンプライアンス ポリシーの一致を取得するには、PowerShell または [Office 365 Management API](/office/office-365-management-api/office-365-management-activity-api-reference) を使用できます。

PowerShell を使用する場合は、これらのパラメーターのいずれかを **Search-UnifiedAuditLog** コマンドレットと共に使用して、監査ログ イベントをフィルター処理して、通信コンプライアンス アクティビティを行うことができます。

| 監査ログ パラメーター | 通信コンプライアンス パラメーターの値 |
| :------------------ | :--------------------------------------- |
| 業務          | SupervisionRuleMatch                     |
| RecordType          | ComplianceSupervisionExchange            |

たとえば、 **Operations** パラメーターと *SupervisionRuleMatch* 値を使用したサンプル検索を次に示します。

```powershell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -Operations SupervisionRuleMatch | ft CreationDate,UserIds,AuditData
```
**RecordsType** パラメーターと *ComplianceSupervisionExchange* 値を使用したサンプル検索を次に示します。

```powershell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType ComplianceSuperVisionExchange | ft CreationDate,UserIds,AuditData
```
## <a name="resources"></a>リソース

- [コミュニケーション コンプライアンス監査](/microsoft-365/compliance/communication-compliance-reports-audits#audit)
- [Microsoft Purview 監査 (Premium)](/microsoft-365/compliance/advanced-audit)
- [Office 365 管理アクティビティ API リファレンス](/office/office-365-management-api/office-365-management-activity-api-reference)
