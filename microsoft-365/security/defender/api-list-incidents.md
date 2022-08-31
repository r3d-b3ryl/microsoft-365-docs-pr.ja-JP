---
title: Microsoft 365 Defenderでインシデント API を一覧表示する
description: Microsoft 365 Defenderでインシデント API を一覧表示する方法について説明します
keywords: list, incident, incidents, api
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.custom: api
ms.openlocfilehash: d86c26af54c4cd69e65cd5af952556a2553b728e
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67483060"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a>Microsoft 365 Defenderでインシデント API を一覧表示する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

## <a name="api-description"></a>API の説明

インシデントの一覧 API を使用すると、インシデントを並べ替えて、情報に基づいたサイバーセキュリティ対応を作成できます。 環境保持ポリシーで指定した時間範囲内で、ネットワーク上でフラグが設定されたインシデントのコレクションを公開します。 最新のインシデントが一覧の上部に表示されます。 各インシデントには、関連するアラートとその関連エンティティの配列が含まれています。

API では、次の **OData** 演算子がサポートされています。

- `$filter``lastUpdateTime`、、`createdTime``status`および`assignedTo`プロパティ
- `$top`(最大値 **は 100)**
- `$skip`

## <a name="limitations"></a>制限事項

1. 最大ページ サイズは **100 インシデントです**。
2. 要求の最大レートは **、1 分あたり 50 回** 、 **1 時間あたり 1500 回の呼び出しです**。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「[Access Microsoft 365 Defender API」を](api-access.md)参照してください。

アクセス許可の種類|アクセス許可|アクセス許可の表示名
---|---|---
アプリケーション|Incident.Read.All|すべてのインシデントの読み取り
アプリケーション|Incident.ReadWrite.All|すべてのインシデントの読み取りと書き込み
委任 (職場または学校のアカウント)|Incident.Read|インシデントの読み取り
委任 (職場または学校のアカウント)|Incident.ReadWrite|インシデントの読み取りと書き込み

> [!NOTE]
> ユーザー資格情報を使用してトークンを取得する場合:
>
> - ユーザーは、ポータルでインシデントの表示アクセス許可を持っている必要があります。
> - 応答には、ユーザーが公開されているインシデントのみが含まれます。

## <a name="http-request"></a>HTTP 要求

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a>要求ヘッダー

名前|型|説明
---|---|---
Authorization|String|ベアラー {token}。 **必須**

## <a name="request-body"></a>要求本文

なし。

## <a name="response"></a>応答

成功した場合、このメソッドは `200 OK`応答本文の [インシデント](api-incident.md) の一覧を返します。

## <a name="schema-mapping"></a>スキーマ マッピング

### <a name="incident-metadata"></a>インシデント メタデータ

フィールド名|説明|値の例
---|---|---
incidentId|インシデントを表す一意の識別子|924565
redirectIncidentId|インシデント処理ロジックの一部として、インシデントが別のインシデントとグループ化されている場合にのみ設定されます。|924569
incidentName|すべてのインシデントで使用できる文字列値。|ランサムウェアのアクティビティ
createdTime|インシデントが最初に作成された時刻。|2020-09-06T14:46:57.0733333Z
lastUpdateTime|バックエンドでインシデントが最後に更新された時刻。 <p> このフィールドは、インシデントが取得される時間範囲の要求パラメーターを設定するときに使用できます。|2020-09-06T14:46:57.29Z
assignedTo|インシデントの所有者、または所有者が割り当てられていない場合は *null* 。|secop2@contoso.com
classification|インシデントの仕様。 プロパティの値は、 *不明*、 *FalsePositive*、 *TruePositive です。*|不明
決定|インシデントの決定を指定します。 プロパティの値は次のとおりです。 *NotAvailable*、 *Apt*、 *Malware*、 *SecurityPersonnel*、 *SecurityTesting*、 *UnwantedSoftware*、 *Other*|NotAvailable
detectionSource|検出のソースを指定します。|Defender for Cloud Apps
status|インシデントを分類する ( *アクティブ* または *解決済み*)。 インシデントに対する対応を整理して管理するのに役立ちます。|Active
severity|資産への影響の可能性を示します。 重大度が高いほど、影響は大きくなります。 通常、重大度の高い項目には、最も迅速な注意が必要です。 <p> 次のいずれかの値: *Informational*、*Low*、*Medium *、High。*|中
tags|インシデントに関連付けられているカスタム タグの配列。たとえば、共通の特性を持つインシデントのグループにフラグを設定します。|\[\]
comments|インシデントの管理時に secops によって作成されたコメントの配列 (分類の選択に関する追加情報など)。|\[\]
アラート|インシデントに関連するすべてのアラートに加え、重大度、アラートに関与したエンティティ、アラートのソースなどのその他の情報を含む配列。|\[\] (以下のアラート フィールドの詳細を参照してください)

### <a name="alerts-metadata"></a>アラート メタデータ

フィールド名|説明|値の例
---|---|---
alertId|アラートを表す一意の識別子|caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC
incidentId|このアラートが関連付けられているインシデントを表す一意の識別子|924565
serviceSource|Microsoft Defender for Endpoint、Microsoft Defender for Cloud Apps、Microsoft Defender for Identity、またはMicrosoft Defender for Office 365。|MicrosoftCloudAppSecurity
creationTime|アラートが最初に作成された時刻。|2020-09-06T14:46:55.7182276Z
lastUpdatedTime|バックエンドでアラートが最後に更新された時刻。|2020-09-06T14:46:57.2433333Z
resolvedTime|アラートが解決された時刻。|2020-09-10T05:22:59Z
firstActivity|バックエンドでアクティビティが更新されたことをアラートが最初に報告した時刻。|2020-09-04T05:22:59Z
title|各アラートで使用できる文字列値を簡単に識別します。|ランサムウェアのアクティビティ
説明|各アラートを記述する文字列値。|ユーザーテスト User2 (testUser2@contoso.com) は、一般的でない拡張子 *herunterladen* で終わる複数の拡張子を持つ 99 ファイルを操作しました。 これは、異常な数のファイル操作であり、ランサムウェア攻撃の可能性を示しています。
category|攻撃がキル チェーンに沿ってどれだけ進行したかを示す視覚的および数値のビュー。 [MITRE ATT&CK™ フレームワーク](https://attack.mitre.org/)にアラインされます。|影響
status|アラートを分類します ( *新規*、 *アクティブ*、または *解決済み*)。 アラートに対する応答を整理して管理するのに役立ちます。|新規
severity|資産への影響の可能性を示します。 重大度が高いほど、影響は大きくなります。 通常、重大度の高い項目には、最も迅速な注意が必要です。<br>次のいずれかの値: *Informational*、*Low*、*Medium**、High。*|中
investigationId|このアラートによってトリガーされる自動調査 ID。|1234
investigationState|調査の現在の状態に関する情報。 次のいずれかの値: *Unknown*、 *Terminated*、 *SuccessfullyRemediated*、 *Benign*、 *Failed*、 *PartiallyRemediated*、 *Running*、 *PendingApproval*、 *PendingResource*、 *PartiallyInvestigated*、 *TerminatedByUser*、 *TerminatedBySystem*、 *Queued*、 *InnerFailure*、 *PreexistingAlert*、 *UnsupportedOs*、 *UnsupportedAlertType*、 *SuppressedAlert*。|UnsupportedAlertType
classification|インシデントの仕様。 プロパティの値は、*不明*、*FalsePositive*、*TruePositive*、または *null です*。|不明
決定|インシデントの決定を指定します。 プロパティの値は、*NotAvailable*、*Apt*、*Malware*、*SecurityPersonnel*、*SecurityTesting*、*UnwantedSoftware*、*Other* または *null です*。|Apt
assignedTo|インシデントの所有者、または所有者が割り当てられていない場合は *null* 。|secop2@contoso.com
actorName|このアラートに関連付けられているアクティビティ グループ (存在する場合)。|ホウ素
threatFamilyName|このアラートに関連付けられている脅威ファミリ。|null
mitreTechniques|[MITRE ATT&CK](https://attack.mitre.org/)™ フレームワークに沿った攻撃手法。|\[\]
デバイス|インシデントに関連するアラートが送信されたすべてのデバイス。|\[\] (以下のエンティティ フィールドの詳細を参照してください)

### <a name="device-format"></a>デバイスの形式

フィールド名|説明|値の例
---|---|---
DeviceId|Microsoft Defender for Endpointで指定されているデバイス ID。|24c222b0b60fe148eeece49ac83910cc6a7ef491
aadDeviceId|[Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis) で指定されているデバイス ID。 ドメインに参加しているデバイスでのみ使用できます。|null
deviceDnsName|デバイスの完全修飾ドメイン名。|user5cx.middleeast.corp.contoso.com
osPlatform|デバイスが実行されている OS プラットフォーム。|WindowsServer2016
osBuild|デバイスが実行されている OS のビルド バージョン。|14393
rbacGroupName|デバイスに関連付けられている [ロールベースのアクセス制御](/azure/role-based-access-control/overview) (RBAC) グループ。|WDATP-Ring0
firstSeen|デバイスが最初に表示された時刻。|2020-02-06T14:16:01.9330135Z
healthStatus|デバイスの正常性状態。|Active
riskScore|デバイスのリスク スコア。|高
エンティティ|特定のアラートの一部または関連として識別されたすべてのエンティティ。|\[\] (以下のエンティティ フィールドの詳細を参照してください)

### <a name="entity-format"></a>エンティティの形式

フィールド名|説明|値の例
---|---|---
Entitytype|特定のアラートの一部または関連するエンティティ。<br>プロパティの値は、*User*、*Ip*、*URL*、*File*、*Process*、*MailBox*、*MailMessage*、*MailCluster*、*Registry* です。|User
sha1|entityType が *File* の場合に使用できます。<br>ファイルまたはプロセスに関連付けられたアラートのファイル ハッシュ。|5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd
sha256|entityType が *File* の場合に使用できます。<br>ファイルまたはプロセスに関連付けられたアラートのファイル ハッシュ。|28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043
fileName|entityType が *File* の場合に使用できます。<br>ファイルまたはプロセスに関連付けられたアラートのファイル名|Detector.UnitTests.dll
Filepath|entityType が *File* の場合に使用できます。<br>ファイルまたはプロセスに関連付けられたアラートのファイル パス|C:\\\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out
processId|entityType が *Process* の場合に使用できます。|24348
processCommandLine|entityType が *Process* の場合に使用できます。|"ファイルを1911150169.exeダウンロード\_ する準備ができました"
processCreationTime|entityType が *Process* の場合に使用できます。|2020-07-18T03:25:38.5269993Z
parentProcessId|entityType が *Process* の場合に使用できます。|16840
parentProcessCreationTime|entityType が *Process* の場合に使用できます。|2020-07-18T02:12:32.8616797Z
ipAddress|entityType が *Ip* の場合に使用できます。 <br>*悪意のあるネットワーク宛先への通信* など、ネットワーク イベントに関連付けられているアラートの IP アドレス。|62.216.203.204
url|entityType が *Url* の場合に使用できます。 <br>*悪意のあるネットワーク宛先への通信* など、ネットワーク イベントに関連付けられているアラートの URL。|down.esales360.cn
accountName|entityType が *User* の場合に使用できます。|testUser2
domainName|entityType が *User* の場合に使用できます。|europe.corp.contoso
userSid|entityType が *User* の場合に使用できます。|S-1-5-21-1721254763-462695806-1538882281-4156657
aadUserId|entityType が *User* の場合に使用できます。|fc8f7484-f813-4db2-afab-bc1507913fb6
userPrincipalName|entityType が *User*/*MailBox*/*MailMessage* の場合に使用できます。|testUser2@contoso.com
mailboxDisplayName|entityType が *MailBox* の場合に使用できます。|User2 をテストする
mailboxAddress|entityType が *User*/*MailBox*/*MailMessage* の場合に使用できます。|testUser2@contoso.com
clusterBy|entityType が  *MailCluster* の場合に使用できます。|件名;P2SenderDomain;Contenttype
sender|entityType が *User*/*MailBox*/*MailMessage* の場合に使用できます。|user.abc@mail.contoso.co.in
受信者|entityType が *MailMessage* の場合に使用できます。|testUser2@contoso.com
subject|entityType が *MailMessage* の場合に使用できます。|\[EXTERNAL\] Attention
deliveryAction|entityType が *MailMessage* の場合に使用できます。|配信
securityGroupId|entityType が  *SecurityGroup* の場合に使用できます。|301c47c8-e15f-4059-ab09-e2ba9ffd372b
securityGroupName|entityType が  *SecurityGroup* の場合に使用できます。|ネットワーク構成演算子
registryHive|entityType が  *Registry* の場合に使用できます。|HKEY\_ローカル\_コンピューター|
Registrykey|entityType が  *Registry* の場合に使用できます。|SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon
registryValueType|entityType が  *Registry* の場合に使用できます。|文字列
registryValue|entityType が  *Registry* の場合に使用できます。|31-00-00-00
deviceId|エンティティに関連するデバイスの ID (存在する場合)。|986e5df8b73dacd43c8917d17e523e76b13c75cd

## <a name="example"></a>例

### <a name="request-example"></a>要求の例

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

### <a name="response-example"></a>応答の例

```json
{
    "@odata.context": "https://api.security.microsoft.com/api/$metadata#Incidents",
    "value": [
            {
            "incidentId": 924565,
            "redirectIncidentId": null,
            "incidentName": "Ransomware activity",
            "createdTime": "2020-09-06T14:46:57.0733333Z",
            "lastUpdateTime": "2020-09-06T14:46:57.29Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Medium",
            "tags": [],
            "comments": [
                {
                    "comment": "test comment for docs",
                    "createdBy": "secop123@contoso.com",
                    "createdTime": "2021-01-26T01:00:37.8404534Z"
                }
            ],
            "alerts": [
                {
                    "alertId": "caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC",
                    "incidentId": 924565,
                    "serviceSource": "MicrosoftCloudAppSecurity",
                    "creationTime": "2020-09-06T14:46:55.7182276Z",
                    "lastUpdatedTime": "2020-09-06T14:46:57.2433333Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-04T05:22:59Z",
                    "lastActivity": "2020-09-04T05:22:59Z",
                    "title": "Ransomware activity",
                    "description": "The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension herunterladen. This is an unusual number of file manipulations and is indicative of a potential ransomware attack.",
                    "category": "Impact",
                    "status": "New",
                    "severity": "Medium",
                    "investigationId": null,
                    "investigationState": "UnsupportedAlertType",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "MCAS",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "User",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": "testUser2",
                            "domainName": "europe.corp.contoso",
                            "userSid": "S-1-5-21-1721254763-462695806-1538882281-4156657",
                            "aadUserId": "fc8f7484-f813-4db2-afab-bc1507913fb6",
                            "userPrincipalName": "testUser2@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "62.216.203.204",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924521,
            "redirectIncidentId": null,
            "incidentName": "'Mimikatz' hacktool was detected on one endpoint",
            "createdTime": "2020-09-06T12:18:03.6266667Z",
            "lastUpdateTime": "2020-09-06T12:18:03.81Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Low",
            "tags": [],
            "comments": [],
            "alerts": [
                {
                    "alertId": "da637349914833441527_393341063",
                    "incidentId": 924521,
                    "serviceSource": "MicrosoftDefenderATP",
                    "creationTime": "2020-09-06T12:18:03.3285366Z",
                    "lastUpdatedTime": "2020-09-06T12:18:04.2566667Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:15:07.7272048Z",
                    "lastActivity": "2020-09-06T12:15:07.7272048Z",
                    "title": "'Mimikatz' hacktool was detected",
                    "description": "Readily available tools, such as hacking programs, can be used by unauthorized individuals to spy on users. When used by attackers, these tools are often installed without authorization and used to compromise targeted machines.\n\nThese tools are often used to collect personal information from browser records, record key presses, access email and instant messages, record voice and video conversations, and take screenshots.\n\nThis detection might indicate that Microsoft Defender Antivirus has stopped the tool from being installed and used effectively. However, it is prudent to check the machine for the files and processes associated with the detected tool.",
                    "category": "Malware",
                    "status": "New",
                    "severity": "Low",
                    "investigationId": null,
                    "investigationState": "UnsupportedOs",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "WindowsDefenderAv",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": "Mimikatz",
                    "mitreTechniques": [],
                    "devices": [
                        {
                            "mdatpDeviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491",
                            "aadDeviceId": null,
                            "deviceDnsName": "user5cx.middleeast.corp.contoso.com",
                            "osPlatform": "WindowsServer2016",
                            "version": "1607",
                            "osProcessor": "x64",
                            "osBuild": 14393,
                            "healthStatus": "Active",
                            "riskScore": "High",
                            "rbacGroupName": "WDATP-Ring0",
                            "rbacGroupId": 9,
                            "firstSeen": "2020-02-06T14:16:01.9330135Z"
                        }
                    ],
                    "entities": [
                        {
                            "entityType": "File",
                            "sha1": "5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd",
                            "sha256": null,
                            "fileName": "Detector.UnitTests.dll",
                            "filePath": "C:\\Agent\\_work\\_temp\\Deploy_SYSTEM 2020-09-06 12_14_54\\Out",
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491"
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924518,
            "redirectIncidentId": null,
            "incidentName": "Email reported by user as malware or phish",
            "createdTime": "2020-09-06T12:07:55.1366667Z",
            "lastUpdateTime": "2020-09-06T12:07:55.32Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Informational",
            "tags": [],
            "comments": [],
            "alerts": [
                {
                    "alertId": "faf8edc936-85f8-a603-b800-08d8525cf099",
                    "incidentId": 924518,
                    "serviceSource": "OfficeATP",
                    "creationTime": "2020-09-06T12:07:54.3716642Z",
                    "lastUpdatedTime": "2020-09-06T12:37:40.88Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:04:00Z",
                    "lastActivity": "2020-09-06T12:04:00Z",
                    "title": "Email reported by user as malware or phish",
                    "description": "This alert is triggered when any email message is reported as malware or phish by users -V1.0.0.2",
                    "category": "InitialAccess",
                    "status": "InProgress",
                    "severity": "Informational",
                    "investigationId": null,
                    "investigationState": "Queued",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "OfficeATP",
                    "assignedTo": "Automation",
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser3@contoso.com",
                            "mailboxDisplayName": "test User3",
                            "mailboxAddress": "testUser3@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser4@contoso.com",
                            "mailboxDisplayName": "test User4",
                            "mailboxAddress": "test.User4@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailMessage",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "test.User4@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": "user.abc@mail.contoso.co.in",
                            "recipient": "test.User4@contoso.com",
                            "subject": "[EXTERNAL] Attention",
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "49.50.81.121",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        ...
    ]
}
```

## <a name="related-articles"></a>関連記事

- [Microsoft 365 Defender API にアクセスする](api-access.md)
- [API の制限とライセンスについて学習する](api-terms.md)
- [エラー コードについて](api-error-codes.md)
- [インシデントの概要](incidents-overview.md)
- [インシデント API](api-incident.md)
- [インシデント API を更新する](api-update-incidents.md)
