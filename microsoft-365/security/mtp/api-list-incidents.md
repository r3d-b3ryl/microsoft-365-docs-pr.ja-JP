---
title: Microsoft 365 Defender のインシデント API を一覧表示する
description: Microsoft 365 Defender でインシデント API を一覧表示する方法について説明します。
keywords: リスト、インシデント、インシデント、api
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 9da6fdf04fd22767f3984229b7862f02b8293067
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844998"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a>Microsoft 365 Defender のインシデント API を一覧表示する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性がある prereleased 製品に関連しています。 Microsoft makes no warranties, express or implied, with respect to the information provided here.


## <a name="api-description"></a>API の説明

インシデント API を使用すると、インシデントを優先して優先度を設定し、通知された cybersecurity 応答を作成することができます。 これにより、環境のアイテム保持ポリシーで指定した時間の範囲内で、ネットワーク内のデバイス、電子メールアカウント、ユーザーのフラグが付けられたインシデントのコレクションが公開されます。 最新のインシデントは、リストの一番上に表示されます。 各インシデントには、関連する通知の配列と、関連するエンティティが含まれています。

<br>この API は、次の **OData** 演算子をサポートしています。
<br>```$filter``` on: ```lastUpdateTime``` 、 ```createdTime``` 、 ```status``` および ```assignedTo``` プロパティ。
<br>```$top``` 最大値 **100**
<br>```$skip```

## <a name="limitations"></a>制限事項

1. 最大ページサイズは **100 インシデント** です。
2. 要求の最大速度は、1 **分あたり50通話** 、1 **時間あたり1500通話** です。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法を含む詳細については、「 [Microsoft 365 Defender Api へのアクセス](api-access.md)」を参照してください。

アクセス許可の種類 |   アクセス許可  |   アクセス許可の表示名
:---|:---|:---
アプリケーション |   インシデント。すべてを読み取ります。 | ' すべてのインシデントの読み取り '
アプリケーション |   インシデント。すべて | ' すべてのインシデントの読み取りと書き込み '
委任 (職場または学校のアカウント) | インシデント。読み取り | ' 読み取りインシデント '
委任 (職場または学校のアカウント) | 障害/書き込み | ' 読み取りおよび書き込みのインシデント '

> [!Note]
> ユーザー資格情報を使用してトークンを取得する場合:
> - ユーザーはポータルのインシデントに対する表示権限を持っている必要があります。
> - 応答には、ユーザーが公開されているインシデントのみが含まれます。

## <a name="http-request"></a>HTTP 要求

```
GET /api/incidents
```

## <a name="request-headers"></a>要求ヘッダー

名前 | 型 | 説明
:---|:---|:---
Authorization | String | ベアラー {token}。 **必須** 。


## <a name="request-body"></a>要求本文
なし。

## <a name="response"></a>応答
成功した場合、このメソッドは 200 OK と、応答本文で [インシデント](api-incident.md) の一覧を返します。

## <a name="schema-mapping"></a>スキーママッピング

| フィールド名                                | 説明                                                                                                                                                                                                                                                                                                                                                                                | 値の例                                                                                                                                                                                                                                     |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **インシデントのメタデータ**                         |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| インシデント識別子 d                                | インシデントを表す一意の識別子。                                                                                                                                                                                                                                                                                                                                                | 924565                                                                                                                                                                                                                                            |
| Redirectインシデント識別子 d                        | インシデントが別のインシデントと一緒にグループ化されている場合にのみ、インシデント処理ロジックの一部として設定されます。                                                                                                                                                                                                                                                           | 924569                                                                                                                                                                                                                                            |
| incidentName                              | すべてのインシデントで利用可能な文字列値。                                                                                                                                                                                                                                                                                                                                                  | ランサムウェアアクティビティ                                                                                                                                                                                                                               |
| createdTime                               | インシデントが最初に作成された日時。                                                                                                                                                                                                                                                                                                                                                      | 2020-09-06T14:46: 57.0733333 Z                                                                                                                                                                                                                      |
| lastUpdateTime                            | インシデントがバックエンドで最後に更新された時刻。<br> このフィールドは、インシデントを取得する時間の範囲の request パラメータを設定するときに使用できます。                                                                                                                                                                                                                      | 2020-09-06T14:46: 57.29 Z                                                                                                                                                                                                                           |
| assignedTo                                | インシデントの所有者。所有者が割り当てられていない場合は、 *null* 。                                                                                                                                                                                                                                                                                                                         | secop2@contoso.com                                                                                                                                                                                                |
| classification                            | インシデントの仕様。 プロパティの値は次のとおりです。 *Unknown* 、 *false 陽性* 、 *TruePositive*                                                                                                                                                                                                                                                                           | 不明                                                                                                                                                                                                                                           |
| 決定                             | インシデントの決定を指定します。 プロパティの値は次のとおりです。 *Notavailable* 、 *Apt* 、 *マルウェア* 、 *securitypersonnel* 、 *securitypersonnel* 、 *UnwantedSoftware* 、 *Other*                                                                                                                                                                                                                | NotAvailable                                                                                                                                                                                                                                      |
| status                                    | インシデント ( *アクティブ* または *解決済み* ) を分類します。 これにより、インシデントへの対応を整理し、管理することができます。                                                                                                                                                                                                                                                                  | Active                                                                                                                                                                                                                                            |
| severity                                  | アセットに影響を与える可能性があることを示します。 重要度が高いほど、影響が大きくなります。 通常、重要度が高いアイテムは、即時注意が必要です。<br>次のいずれかの値: [ *情報* ]、[ *低* ]、[中]、[ *高* ]。                                                                                                                                | 中                                                                                                                                                                                                                                            |
| tags                                      | インシデントに関連付けられているカスタムタグの配列です。たとえば、共通の特性を使用して、インシデントのグループにフラグを設定します。                                                                                                                                                                                                                                                                  | \[\]                                                                                                                                                                                                                                              |
| アラート                                    | インシデントに関連付けられているすべての警告とその他の情報 (重要度、警告に関係していたエンティティ、アラートのソースなど) の配列。                                                                                                                                                                                                                     | \[\] (下の警告フィールドの詳細を参照してください)                                                                                                                                                                                                          |
| **通知のメタデータ**                           |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| alertId                                   | 通知を表す一意識別子                                                                                                                                                                                                                                                                                                                                                   | caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC                                                                                                                                                                                                            |
| インシデント識別子 d                                | このアラートが関連付けられているインシデントを表す一意識別子                                                                                                                                                                                                                                                                                                                  | 924565                                                                                                                                                                                                                                            |
| サービス Ource                             | アラートの発生元であるサービス (エンドポイントの場合は Microsoft Defender、Microsoft Cloud App Security、Identity の場合は microsoft defender、Office 365 の場合は Microsoft Defender)。                                                                                                                                                                                                                                                                     | Microsoft Cloudappsecurity                                                                                                                                                                                                                         |
| creationTime                              | 通知が最初に作成された日時。                                                                                                                                                                                                                                                                                                                                                         | 2020-09-06T14:46: 55.7182276 Z                                                                                                                                                                                                                      |
| lastUpdatedTime                           | バックエンドで通知が最後に更新された時刻。                                                                                                                                                                                                                                                                                                                                           | 2020-09-06T14:46: 57.2433333 Z                                                                                                                                                                                                                      |
| resolvedTime                              | 通知が解決された時刻。                                                                                                                                                                                                                                                                                                                                                              | 2020-09-10T05:22: 59Z                                                                                                                                                                                                                              |
| firstActivity                             | 警告が最初にアクティビティが更新されたことを報告した日時です。                                                                                                                                                                                                                                                                                                                             | 2020-09-04T05:22: 59Z                                                                                                                                                                                                                              |
| title                                     | 各警告で使用可能な短い識別文字列値。                                                                                                                                                                                                                                                                                                                                                     | ランサムウェアアクティビティ                                                                                                                                                                                                                               |
| 説明                               | 各警告を説明する文字列値。                                                                                                                                                                                                                                                                                                                                                        | ユーザーテスト User2 (testUser2@contoso.com) は、複数の拡張子を持つ99ファイルを、一般的でない拡張子 *herunterladen* で終了するように操作します。 これは、通常のファイル操作の数で、ランサムウェアによる可能性のある攻撃を示しています。 |
| category                                  | キルチェーンに沿った攻撃の進行状況を示す視覚的および数値のビュー。 [MITRE ATT&の™ framework](https://attack.mitre.org/)に配置されます。                                                                                                                                                                                                                           | 影響                                                                                                                                                                                                                                            |
| status                                    | 通知を分類します ( *新規* 、 *アクティブ* 、または *解決済み* )。 これにより、アラートへの対応を整理し、管理することができます。                                                                                                                                                                                                                                                                   | 新規                                                                                                                                                                                                                                               |
| severity                                  | アセットに影響を与える可能性があることを示します。 重要度が高いほど、影響が大きくなります。 通常、重要度が高いアイテムは、即時注意が必要です。<br>次のいずれかの値: [ *情報* ]、[ *低* ]、[中]、[ *高* ]。                                                                                                                                   | 中                                                                                                                                                                                                                                            |
| investigationId                           | このアラートによってトリガーされた自動調査 id。                                                                                                                                                                                                                                                                                                                                | 1234                                                                                                                                                                                                                                              |
| investigationState                        | 調査の現在の状態に関する情報。 *Unknown* 、 *終わら* れた *修復* 済み、 *無害* 、 *Failed* 、 *PartiallyRemediated* 、 *Running* 、 *pendingapproval* 、 *pendingapproval* 、 *PartiallyInvestigated* 、 *TerminatedByUser* 、 *TerminatedBySystem* 、 *Queued* 、 *innerfailure* 、 *preexistingalert* 、 *UnsupportedOs* 、 *presupportedalerttype* 、 *SuppressedAlert* のいずれか。 | アン Supportedalerttype                                                                                                                                                                                                                              |
| classification                            | インシデントの仕様。 プロパティの値は次のとおりです。 *Unknown* 、 *false 陽性* 、 *TruePositive* 、または *null*                                                                                                                                                                                                                                                                   | 不明                                                                                                                                                                                                                                           |
| 決定                             | インシデントの決定を指定します。 プロパティの値は次のとおりです。 *Notavailable* 、 *Apt* 、 *マルウェア* 、 *securitypersonnel* 、 *securitypersonnel* 、 *UnwantedSoftware* 、 *Other* 、または  *null*                                                                                                                                                                                                     | Excel                                                                                                                                                                                                                                               |
| assignedTo                                | インシデントの所有者。所有者が割り当てられていない場合は、 *null* 。                                                                                                                                                                                                                                                                                                                            | secop2@contoso.com                                                                                                                                                                                                 |
| actorName                                 | このアラートに関連付けられているアクティビティグループ (存在する場合)。                                                                                                                                                                                                                                                                                                                                        | BORON                                                                                                                                                                                                                                             |
| threatFamilyName                          | このアラートに関連付けられている脅威ファミリ。                                                                                                                                                                                                                                                                                                                                                   | null                                                                                                                                                                                                                                              |
| mitreTechniques                           | [MITRE ATT&](https://attack.mitre.org/)の™ framework に沿った攻撃手法。                                                                                                                                                                                                                                                                                                                              | \[\]                                                                                                                                                                                                                                              |
| ハードウェア                                   | インシデントに関連するアラートが送信されたすべてのデバイス。                                                                                                                                                                                                                                                                                                     | \[\] (以下のエンティティフィールドの詳細を参照)                                                                                                                                                                                                         |
| **デバイス形式**                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| DeviceId                                  | エンドポイントの Microsoft Defender で指定されているデバイス ID。                                                                                                                                                                                                                                                                                                                                                       | 24c222b0b60fe148eeece49ac83910cc6a7ef491                                                                                                                                                                                                          |
| aadDeviceId                               |  [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) (AAD) で指定されているデバイス Id。 ドメインに参加しているデバイスでのみ使用できます。                                                                                                                                                                                                                                                                                                                              | null                                                                                                                                                                                                                                              |
| deviceDnsName                             | デバイスの完全修飾ドメイン名。                                                                                                                                                                                                                                                                                                                                                                        | user5cx.middleeast.corp.contoso.com                                                                                                                                                                                                    |
| osPlatform                                | デバイスが実行されている OS プラットフォーム。                                                                                                                                                                                                                                                                                                                                                                     | WindowsServer2016                                                                                                                                                                                                                                 |
| osBuild                                   | デバイスが実行している OS のビルドバージョン。                                                                                                                                                                                                                                                                                                                                                                | 14393                                                                                                                                                                                                                                             |
| rbacGroupName                             | デバイスに関連付けられている [役割ベースのアクセス制御](https://docs.microsoft.com/azure/role-based-access-control/overview) (RBAC) グループ。                                                                                                                                                                                                                                                                                                                             | WDATP-Ring0                                                                                                                                                                                                                                       |
| 最初の表示                                 | デバイスが最初に表示された時刻。                                                                                                                                                                                                                                                                                                                                                           | 2020-02-06T14:16: 01.9330135 Z                                                                                                                                                                                                                      |
| healthStatus                              | デバイスの正常性の状態。                                                                                                                                                                                                                                                                                                                                                                        | Active                                                                                                                                                                                                                                            |
| riskScore                                 | デバイスのリスクスコア。                                                                                                                                                                                                                                                                                                                                                                       | 高い                                                                                                                                                                                                                                              |
| 法人                                  | 特定のアラートに含まれている、またはそれに関連付けられているすべてのエンティティ。                                                                                                                                                                                                                                                                                | \[\] (以下のエンティティフィールドの詳細を参照)                                                                                                                                                                                                         |
| **エンティティ形式**                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| entityType                                | 特定の警告に含まれている、または関連するエンティティ。<br>プロパティの値は次のとおりです。 *ユーザー* 、 *Ip* 、 *Url* 、 *ファイル* 、 *プロセス* 、 *メールボックス* 、 *MailMessage* 、 *mailcluster* 、 *Registry*                                                                                                                                                                                                     | User                                                                                                                                                                                                                                              |
| sha1                                      | EntityType が *File* の場合に使用できます。<br>ファイルまたはプロセスに関連付けられた通知のファイルハッシュ。                                                                                                                                                                                                                                                                                    | 5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd                                                                                                                                                                                                          |
| sha256                                    | EntityType が *File* の場合に使用できます。<br>ファイルまたはプロセスに関連付けられた通知のファイルハッシュ。                                                                                                                                                                                                                                                                                    | 28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043                                                                                                                                                                                  |
| fileName                                  | EntityType が *File* の場合に使用できます。<br>ファイルまたはプロセスに関連付けられた通知のファイル名                                                                                                                                                                                                                                                                                    | Detector.UnitTests.dll                                                                                                                                                                                                                            |
| パス                                  | EntityType が *File* の場合に使用できます。<br>ファイルまたはプロセスに関連付けられた通知のファイルパス                                                                                                                                                                                                                                                                                    | C: \\ \\ エージェント \\ \\ \_ 作業 \\ \\ \_ 温度 \\ \\ 展開 \_ システム 2020-09-06 12 \_ 14 \_ 54 \\ \\ アウト                                                                                                                                                                    |
| processId                                 | EntityType が *Process* の場合に使用できます。                                                                                                                                                                                                                                                                                                                                                     | 24348                                                                                                                                                                                                                                             |
| processCommandLine                        | EntityType が *Process* の場合に使用できます。                                                                                                                                                                                                                                                                                                                                                     | " \\ " ファイルをダウンロードする準備ができました \_1911150169.exe\\ "                                                                                                                                                                                           |
| Process/時間                       | EntityType が *Process* の場合に使用できます。                                                                                                                                                                                                                                                                                                                                                     | 2020-07-18T03:25: 38.5269993 Z                                                                                                                                                                                                                      |
| parentProcessId                           | EntityType が *Process* の場合に使用できます。                                                                                                                                                                                                                                                                                                                                                   | 16840                                                                                                                                                                                                                                             |
| Parentprocess/時間                 | EntityType が *Process* の場合に使用できます。                                                                                                                                                                                                                                                                                                                                                     | 2020-07-18T02:12: 32.8616797 Z                                                                                                                                                                                                                      |
| ipAddress                                 | EntityType が *Ip* の場合に使用できます。 <br>*悪意のあるネットワークの宛先への通信* など、ネットワークイベントに関連付けられた通知の IP アドレス。                                                                                                                                                                                                                                   | 62.216.203.204                                                                                                                                                                                                                                    |
| url                                       | EntityType が *Url* の場合に使用できます。 <br>ネットワークイベント ( *悪意のあるネットワークの宛先への通信* など) に関連付けられた通知の Url。                                                                                                                                                                                                                                  | down.esales360.cn                                                                                                                                                                                                                                 |
| アカウント                               | EntityType が *User* の場合に使用できます。                                                                                                                                                                                                                                                                                                                                                         | testUser2                                                                                                                                                                                                                                         |
| domainName                                | EntityType が *User* の場合に使用できます。                                                                                                                                                                                                                                                                                                                                                        | 欧州. contoso                                                                                                                                                                                                                              |
| userSid                                   | EntityType が *User* の場合に使用できます。                                                                                                                                                                                                                                                                                                                                                        | S-1-5-21-1721254763-462695806-1538882281-4156657                                                                                                                                                                                                  |
| Usersecuritystate                                 | EntityType が *User* の場合に使用できます。                                                                                                                                                                                                                                                                                                                                                        | fc8f7484-f813-4db2-afab-bc1507913fb6                                                                                                                                                                                                              |
| userPrincipalName                         | EntityType がユーザーの *User* / *メールボックス* MailMessage の場合に使用でき / *MailMessage* ます。                                                                                                                                                                                                                                                                                                                                | testUser2@contoso.com                                                                                                                                                                                      |
| mailboxDisplayName                        | EntityType が *MailBox* の場合に使用できます。                                                                                                                                                                                                                                                                                                                                                     | User2 のテスト                                                                                                                                                                                                                                        |
| mailboxAddress                            | EntityType がユーザーの *User* / *メールボックス* MailMessage の場合に使用でき / *MailMessage* ます。                                                                                                                                                                                                                                                                                                                                | testUser2@contoso.com                                                                                                                                                                                      |
| clusterBy                                 | EntityType が  *Mailcluster* の場合に使用できます。                                                                                                                                                                                                                                                                                                                                                 | 対象P2SenderDomain;ContentType                                                                                                                                                                                                                |
| sender                                    | EntityType がユーザーの *User* / *メールボックス* MailMessage の場合に使用でき / *MailMessage* ます。                                                                                                                                                                                                                                                                                                                                  | user.abc@mail.contoso.co.in                                                                                                                                                                 |
| 受信者                                 | EntityType が *MailMessage* の場合に使用できます。                                                                                                                                                                                                                                                                                                                                                | testUser2@contoso.com                                                                                                                                                                                       |
| subject                                   | EntityType が *MailMessage* の場合に使用できます。                                                                                                                                                                                                                                                                                                                                                 | \[外部 \] 注目                                                                                                                                                                                                                            |
| deliveryAction                            | EntityType が *MailMessage* の場合に使用できます。                                                                                                                                                                                                                                                                                                                                                 | 届け                                                                                                                                                                                                                                         |
| securityGroupId                           | EntityType が  *microsoft.rtc.management.writableconfig.settings.centralizedlogging.securitygroup* の場合に使用できます。                                                                                                                                                                                                                                                                                                                                               | 301c47c8-e15f-4059-ab09-e2ba9ffd372b                                                                                                                                                                                                              |
| securityGroupName                         | EntityType が  *microsoft.rtc.management.writableconfig.settings.centralizedlogging.securitygroup* の場合に使用できます。                                                                                                                                                                                                                                                                                                                                               | ネットワーク構成演算子                                                                                                                                                                                                                   |
| registryHive                              | EntityType が  *レジストリ* の場合に使用できます。                                                                                                                                                                                                                                                                                                                                                    | HKEY \_ ローカル \_ コンピューター                                                                                                                                                                                                                              |
| Rename                               | EntityType が  *レジストリ* の場合に使用できます。                                                                                                                                                                                                                                                                                                                                                     | ソフトウェア \\ \\ MICROSOFT \\ \\ Windows NT \\ \\ currentversion: \\ \\ Winlogon                                                                                                                                                                                 |
| registryValueType                         | EntityType が  *レジストリ* の場合に使用できます。                                                                                                                                                                                                                                                                                                                                                    | String                                                                                                                                                                                                                                            |
| registryValue                             | EntityType が  *レジストリ* の場合に使用できます。                                                                                                                                                                                                                                                                                                                                                    | 31-00-00-00                                                                                                                                                                                                                                       |
| deviceId                                  | エンティティに関連付けられているデバイスの ID (存在する場合)。                                                                                                                                                                                                                                                                                                                                           | 986e5df8b73dacd43c8917d17e523e76b13c75cd                                                                                                                                                                                                          |



## <a name="example"></a>例

**要求**

```
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

## <a name="related-topic"></a>関連トピック
- [インシデント API](api-incident.md)
- [インシデントを更新する](api-update-incidents.md)
