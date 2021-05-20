---
title: Microsoft 365ディフェンダーでインシデント API を一覧表示する
description: Microsoft 365ディフェンダーでインシデント API を一覧表示する方法を学ぶ
keywords: リスト,インシデント,インシデント,API
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 6f0c92371e7e9b7a3348f90df788ee8c3a46374b
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572155"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a>Microsoft 365ディフェンダーでインシデント API を一覧表示する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。


## <a name="api-description"></a>API の説明

リスト インシデント API を使用すると、インシデントを並べ替えて、情報に基づいたサイバーセキュリティ対応を作成できます。 環境の保持ポリシーで指定した時間範囲内で、ネットワークでフラグが設定されたインシデントのコレクションが公開されます。 最新のインシデントがリストの先頭に表示されます。 各インシデントには、関連するアラートと関連エンティティの配列が含まれています。

API は、次の **OData** 演算子をサポートします。

- `$filter` 、 `lastUpdateTime` `createdTime` 、 、 `status` および `assignedTo` プロパティ
- `$top`の最大値が **100** の場合
- `$skip`

## <a name="limitations"></a>制限事項

1. 最大ページ サイズは **100 件です**。
2. 要求の最大レートは **、1 分あたり 50 回の呼び出し** と **1 時間あたり 1500 件の呼び出し** です。

## <a name="permissions"></a>アクセス許可

この API を呼び出すためには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については[、「Defender API へのアクセスMicrosoft 365」を](api-access.md)参照してください。

アクセス許可の種類 | アクセス許可 | アクセス許可の表示名
-|-|-
アプリケーション | インシデント.読み取り.すべて | すべてのインシデントを読み取る
アプリケーション | インシデント.読み書き.すべて | すべてのインシデントの読み取りと書き込み
委任 (職場または学校のアカウント) | インシデント.読み取り | インシデントを読む
委任 (職場または学校のアカウント) | インシデント.読み取り書き込み | インシデントの読み取りと書き込み

> [!Note]
> ユーザーの資格情報を使用してトークンを取得する場合:
>
> - ユーザには、ポータルのインシデントに対する表示権限が必要です。
> - 応答には、ユーザーが公開されているインシデントのみが含まれます。

## <a name="http-request"></a>HTTP 要求

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a>要求ヘッダー

名前 | 型 | 説明
-|-|-
Authorization | String | ベアラー {トークン} **必須**


## <a name="request-body"></a>要求本文

なし。

## <a name="response"></a>応答

成功した場合、このメソッドは `200 OK` 、応答本文に [インシデント](api-incident.md) の一覧とを返します。

## <a name="schema-mapping"></a>スキーママッピング

### <a name="incident-metadata"></a>インシデントメタデータ

フィールド名 | 説明 | 値の例
-|-|-
インシデントId | インシデントを表す一意の識別子 | 924565
インシデント ID をリダイレクトします。 | インシデント処理ロジックの一部として、インシデントが別のインシデントとグループ化されている場合にのみ、設定されます。 | 924569
インシデント名 | すべてのインシデントで使用できる文字列値。 | ランサムウェアのアクティビティ
作成された時刻 | インシデントが最初に作成された時刻。 | 2020-09-06T14:46:57.0733333Z
ラストアップデート時間 | バックエンドでインシデントが最後に更新された時刻。<br /><br /> このフィールドは、インシデントが取得される時間範囲の要求パラメーターを設定するときに使用できます。 | 2020-09-06T14:46:57.29Z
assignedTo | インシデントの所有者、または所有者が割り当てられていない場合は *null。* | secop2@contoso.com
classification | インシデントの仕様。 プロパティ値は *、不明*、 *誤検出*、 *真陽性です。* | 不明
決定 | インシデントの決定を指定します。 プロパティ値は次のとおりです: *利用できません*, *Apt*, *マルウェア*, *セキュリティ要員*, *セキュリティテスト*, *不要なソフトウェア*, *その他* | 利用できません
status | インシデントを *[アクティブ*] 、または [ *解決済み*] として分類します。 インシデントへの対応を整理して管理できます。 | 有効
severity | 資産に与える可能性のある影響を示します。 重大度が高いほど、影響は大きくなります。 通常、重大度が高い項目は、最も迅速な注意が必要です。<br /><br />次の値の 1 つ:*情報、**低*、*中、および *高*。 | 中
tags | インシデントに関連付けられたカスタム タグの配列 (たとえば、共通の特性を持つインシデントのグループにフラグを付ける場合)。 | \[\]
comments | インシデントを管理するときに secops によって作成されたコメントの配列です。 | \[\]
アラート | インシデントに関連するすべてのアラートと、重大度、アラートに関与したエンティティ、アラートのソースなどのその他の情報を含む配列。 | \[\] (下記のアラートフィールドの詳細を参照)

### <a name="alerts-metadata"></a>アラートメタデータ

フィールド名 | 説明 | 値の例
-|-|-
アラートId | 警告を表す一意の識別子 | caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC
インシデントId | このアラートが関連付けられているインシデントを表す一意の識別子 | 924565
サービスソース | エンドポイントの Microsoft Defender、Microsoft Cloud App Security、Id のマイクロソフト ディフェンダー、Office 365用のマイクロソフト ディフェンダーなど、アラートの発生元のサービス。 | マイクロソフトクラウドアプセキュリティ
作成時間 | アラートが最初に作成された時刻。 | 2020-09-06T14:46:55.7182276Z
最後に更新された時間 | バックエンドでアラートが最後に更新された時刻。 | 2020-09-06T14:46:57.2433333Z
解決された時間 | アラートが解決された時刻。 | 2020-09-10T05:22:59Z
最初の活動 | バックエンドでアクティビティが更新されたことをアラートが最初に報告した時刻。| 2020-09-04T05:22:59Z
title | 各アラートに使用できる簡単な識別文字列値。 | ランサムウェアのアクティビティ
説明 | 各アラートを説明する文字列値。 | ユーザーテストUser2 (testUser2@contoso.com) は、複数の拡張子が一般的でない拡張子 *herunterladen* で終わる 99 のファイルを操作しました。 これは、ファイル操作の異常な数であり、潜在的なランサムウェア攻撃を示しています。
category | キルチェーンに沿って攻撃がどこまで進行したかの視覚的および数値的なビュー。 [MITRE ATT&CK™ フレームワーク](https://attack.mitre.org/)に合わせて配置します。 | 影響
status | アラートを [ *新規作成*]、[ *アクティブ*]、[ *解決済み*] の順に分類します。 アラートへの対応を整理して管理できます。 | 新規
severity | 資産に与える可能性のある影響を示します。 重大度が高いほど、影響は大きくなります。 通常、重大度が高い項目は、最も迅速な注意が必要です。<br>次の値の 1 つ:*情報、**低*、*中、および *高*。 | 中
調査Id | このアラートによってトリガーされる自動調査 ID。 | 1234
調査状態 | 調査の現在の状態に関する情報。 次の値の 1 つ:*不明*,*終了しました ,**正常に修復されました*,*問題**が発生しました ,**部分的に修復されました*,*実行中*,*保留中の承認*,*保留中のリソース*,*部分的に調査済み*,*終了バイユーザー*,*終了システム ,**キューに入れ,**内部失敗*,*既存の警告*,*サポートされていない人*,*サポートされていないAlertType*,*抑制されたアラート*. | サポートされていないアラートタイプ
classification | インシデントの仕様。 プロパティ値は *、不明*、*誤検出**、TruePositive*、または *null です。* | 不明
決定 | インシデントの決定を指定します。 プロパティ値は次のとおりです: *利用できません*, *Apt*, *マルウェア*, *セキュリティ要員*, *セキュリティテスト*, *不要なソフトウェア*, *その他* または  *ヌル* | アプト
assignedTo | インシデントの所有者、または所有者が割り当てられていない場合は *null。* | secop2@contoso.com
俳優名 | このアラートに関連付けられている活動グループ (存在する場合)。 | 硼素
脅威家族名 | このアラートに関連付けられている脅威ファミリ。 | null
ミトレテクニック | [MITRE ATT と](https://attack.mitre.org/)一致する攻撃手法&CK ™ フレームワーク。 | \[\]
デバイス | インシデントに関連するアラートが送信されたすべてのデバイス。 | \[\] (下のエンティティ フィールドの詳細を参照)

### <a name="device-format"></a>デバイス形式

フィールド名 | 説明 | 値の例
-|-|-
DeviceId | エンドポイントの Microsoft Defender で指定されたデバイス ID。 | 24c222b0b60fe148eece49ac83910cc6a7ef491
アアドデバイスId |  [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis)で指定されたデバイス ID。 ドメインに参加しているデバイスでのみ使用できます。 | null
を使用します。 | デバイスの完全修飾ドメイン名。 | user5cx.middleeast.corp.contoso.com
osプラットフォーム | デバイスが実行されている OS プラットフォーム。| 2016
osBuild | デバイスが実行されている OS のビルド バージョン。 | 14393
バクグループ名 | デバイスに関連付けられている [ロール ベースのアクセス制御](/azure/role-based-access-control/overview) (RBAC) グループ。 | WDATP-Ring0
最初に見た | デバイスが最初に見られた時刻。 | 2020-02-06T14:16:01.9330135Z
ヘルスステータス | デバイスのヘルス状態。 | 有効
リスクスコア | デバイスのリスク スコア。 | 高い
エンティティ | 特定のアラートの一部であるか、または関連していると識別されたすべてのエンティティ。 | \[\] (下のエンティティ フィールドの詳細を参照)

### <a name="entity-format"></a>エンティティの形式

フィールド名 | 説明 | 値の例
-|-|-
エンティティタイプ | 特定のアラートの一部であるか、または関連していると識別されたエンティティ。<br>プロパティの値は、 *次* のとおりです: ユーザー , *Ip*, *URL*, *ファイル*, *プロセス*, *メール ボックス*, *メール メッセージ*, *メールクラスタ*, *レジストリ* | User
sha1 | entityType が *ファイル* の場合に使用できます。<br>ファイルまたはプロセスに関連付けられたアラートのファイル ハッシュ。 | 5de839186691aa9ee2ca6d74f0a38fb8d1bd6d
sha256 | entityType が *ファイル* の場合に使用できます。<br>ファイルまたはプロセスに関連付けられたアラートのファイル ハッシュ。 | 28cb017dfc99073aa1b47c1b30f413e3ce777c4991eb4158de50f9dbb36d8043
fileName | entityType が *ファイル* の場合に使用できます。<br>ファイルまたはプロセスに関連付けられた警告のファイル名 | Detector.UnitTests.dll
ファイルパス | entityType が *ファイル* の場合に使用できます。<br>ファイルまたはプロセスに関連付けられたアラートのファイル パス | C: \\ \agent_work_temp\展開\システム\2020-09-06 12_14_54\Out
プロセスId | エンティティの種類が *プロセス* の場合に使用できます。 | 24348
コマンドラインを処理します。 | エンティティの種類が *プロセス* の場合に使用できます。 | "ファイルは1911150169.exeダウンロードする準備ができています \_ "
プロセス作成時間 | エンティティの種類が *プロセス* の場合に使用できます。 | 2020-07-18T03:25:38.5269993Z
親プロセスId | エンティティの種類が *プロセス* の場合に使用できます。 | 16840
親プロセス作成時間 | エンティティの種類が *プロセス* の場合に使用できます。 | 2020-07-18T02:12:32.8616797Z
ipAddress | エンティティタイプが *Ip* の場合に使用できます。 <br>ネットワーク イベントに関連するアラートの IP アドレス ( *悪質なネットワーク宛先への通信* など )。 | 62.216.203.204
url | エンティティの種類が *[ Url ]* の場合に使用できます。 <br>ネットワーク イベントに関連付けられたアラートの URL( *悪意のあるネットワーク宛先への通信* など)。 | down.esales360.cn
アカウント名 | entityType が *ユーザー* の場合に使用できます。 | テストユーザー2
domainName | entityType が *ユーザー* の場合に使用できます。 | ヨーロッパ.corp.contoso
ユーザー Sid | entityType が *ユーザー* の場合に使用できます。 | S-1-5-21-1721254763-462695806-1538882281-4156657
アアドユーザーId | entityType が *ユーザー* の場合に使用できます。 | fc8f7484-f813-4db2-afab-bc1507913fb6
userPrincipalName | エンティティの種類が *ユーザー* / *メール ボックス* / *メール メッセージ* の場合に使用できます。 | testUser2@contoso.com
メールボックス表示名 | エンティティの種類が *[メール ボックス]* の場合に使用できます。 | テスト ユーザー 2
メールボックスアドレス | エンティティの種類が *ユーザー* / *メール ボックス* / *メール メッセージ* の場合に使用できます。 | testUser2@contoso.com
クラスターによって | エンティティの種類が  *メール クラスタ* の場合に使用できます。 | 件名;をクリックします。コンテンツタイプ
sender | エンティティの種類が *ユーザー* / *メール ボックス* / *メール メッセージ* の場合に使用できます。 | user.abc@mail.contoso.co.in
受信者 | エンティティの種類が *メール メッセージ* の場合に使用できます。 | testUser2@contoso.com
subject | エンティティの種類が *メール メッセージ* の場合に使用できます。 | \[外部 \] の注意
デリバリーアクション | エンティティの種類が *メール メッセージ* の場合に使用できます。 | 配信
セキュリティグループID | エンティティの種類が  *セキュリティ グループ* の場合に使用できます。 | 301c47c8-e15f-4059-ab09-e2ba9ffd372b
グループ名をセキュリティで保護します。 | エンティティの種類が  *セキュリティ グループ* の場合に使用できます。 | ネットワーク構成オペレーター
registryHive | entityType が  *レジストリ* の場合に使用できます。 | HKEY \_ ローカル \_ マシン |
レジストリキー | entityType が  *レジストリ* の場合に使用できます。 | ソフトウェア\マイクロソフト\Windows NT\現在のバージョン\ウィンログオン
registryValueType | entityType が  *レジストリ* の場合に使用できます。 | String
レジストリ値 | entityType が  *レジストリ* の場合に使用できます。 | 31-00-00-00
deviceId | エンティティに関連付けられているデバイスの ID (存在する場合)。 | 986e5df8b73dac43c8917d17e523376b13c75cd

## <a name="example"></a>例

**要求**

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

**応答**

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
                    "description": "Readily available tools, such as hacking programs, can be used by unauthorized individuals to spy on users. When used by attackers, these tools are often installed without authorization and used to compromise targeted machines.\n\nThese tools are often used to collect personal information from browser records, record key presses, access email and instant messages, record voice and video conversations, and take screenshots.\n\nThis detection might indicate that Windows Defender Antivirus has stopped the tool from being installed and used effectively. However, it is prudent to check the machine for the files and processes associated with the detected tool.",
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

- [Microsoft 365ディフェンダー API へのアクセス](api-access.md)
- [API の制限とライセンスについて](api-terms.md)
- [エラー コードを理解する](api-error-codes.md)
- [インシデントの概要](incidents-overview.md)
- [インシデント API](api-incident.md)
- [インシデント API の更新](api-update-incidents.md)
