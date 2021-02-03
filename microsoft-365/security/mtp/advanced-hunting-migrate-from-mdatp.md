---
title: Microsoft Defender for Endpoint から高度な検索クエリを移行する
description: Microsoft 365 Defender で使用できるよう、エンドポイント用 Microsoft Defender クエリを調整する方法について説明します。
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、Microsoft Defender atp、mdatp、検索、クエリ、テレメトリ、カスタム検出、スキーマ、kusto、Microsoft 365、マッピング
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 4e008488bdd733c9a7ce5b418fb838e0fe880d9d
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080744"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint から高度な検索クエリを移行する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

高度なハンティング ワークフローを Microsoft Defender for Endpoint から移動し、広範なデータセットを使用して脅威を事前に検出します。 Microsoft 365 Defender では、次を含む他の Microsoft 365 セキュリティ ソリューションからデータにアクセスできます。

- Microsoft Defender for Endpoint
- Microsoft Defender for Office 365
- Microsoft Cloud App Security
- Microsoft Defender for Identity

>[!NOTE]
>ほとんどの Microsoft Defender for Endpoint のお客様は、追加のライセンスなしで [Microsoft 365 Defender を使用できます](prerequisites.md#licensing-requirements)。 Defender for Endpoint から高度なハンティング ワークフローの移行を開始するには [、Microsoft 365 Defender をオンにしてください](mtp-enable.md)。

既存の Defender for Endpoint ワークフローに影響を与えることなく移行できます。 保存されたクエリはそのまま残り、カスタム検出ルールは引き続き実行され、アラートが生成されます。 ただし、Microsoft 365 Defender に表示されます。 

## <a name="schema-tables-in-microsoft-365-defender-only"></a>Microsoft 365 Defender のスキーマ テーブルのみ
[Microsoft 365 Defender 高度](advanced-hunting-schema-tables.md)な検索スキーマには、さまざまな Microsoft 365 セキュリティ ソリューションのデータを含む追加のテーブルが含まれています。 次の表は、Microsoft 365 Defender でのみ使用できます。

| テーブル名 | 説明 |
|------------|-------------|
| [AlertEvidence](advanced-hunting-alertevidence-table.md) | アラートに関連付けられているファイル、IP アドレス、URL、ユーザー、またはデバイス |
| [AlertInfo](advanced-hunting-alertinfo-table.md) | エンドポイント用 Microsoft Defender、Office 365 用 Microsoft Defender、Microsoft Cloud App Security、Id 用 Microsoft Defender からのアラート (重大度情報と脅威カテゴリを含む)  |
| [AppFileEvents](advanced-hunting-appfileevents-table.md) | クラウド アプリとサービスでのファイル関連のアクティビティ |
| [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) | メールに添付されたファイルに関する情報 |
| [EmailEvents](advanced-hunting-emailevents-table.md) | Microsoft 365 電子メール イベント (メール配信イベントとブロック イベントを含む) |
| [EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) | Microsoft 365 が受信者のメールボックスにメールを配信した後に、配信後に発生するセキュリティ イベント |
| [EmailUrlInfo](advanced-hunting-emailurlinfo-table.md) | メールの URL に関する情報 |
| [IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) | Active Directory を実行しているオンプレミスのドメイン コントローラーに関連するイベント (AD)。 次の表に、ドメイン コントローラー上の ID 関連のイベントとシステム イベントの範囲を示します。 |
| [IdentityInfo](advanced-hunting-identityinfo-table.md) | Azure Active Directory など、さまざまなソースからのアカウント情報 |
| [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md) | Active Directory および Microsoft オンライン サービスの認証イベント |
| [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) | ユーザー、グループ、デバイス、ドメインなどの Active Directory オブジェクトのクエリ |

## <a name="map-devicealertevents-table"></a>DeviceAlertEvents テーブルのマップ
The `AlertInfo` and tables replace the table in the Microsoft Defender for Endpoint `AlertEvidence` `DeviceAlertEvents` schema. デバイスアラートに関するデータに加えて、これら 2 つの表には、ID、アプリ、メールのアラートに関するデータが含まれています。

次の表を使用して、列とテーブルの列のマップ `DeviceAlertEvents` 方法を `AlertInfo` 確認 `AlertEvidence` します。

>[!TIP]
>次の表の列に加えて、この表には、さまざまなソースからのアラートのより包括的な画像を提供するその他の多くの列 `AlertEvidence` が含まれています。 [AlertEvidence のすべての列を表示する](advanced-hunting-alertevidence-table.md) 

| DeviceAlertEvents 列 | Microsoft 365 Defender で同じデータを検索する場所 |
|-------------|-----------|-------------|-------------|
| `AlertId` | `AlertInfo` および  `AlertEvidence` テーブル |
| `Timestamp` | `AlertInfo` および  `AlertEvidence` テーブル |
| `DeviceId` | `AlertEvidence` table |
| `DeviceName` | `AlertEvidence` table |
| `Severity` | `AlertInfo` table |
| `Category` | `AlertInfo` table |
| `Title` | `AlertInfo` table |
| `FileName` | `AlertEvidence` table |
| `SHA1` | `AlertEvidence` table |
| `RemoteUrl` | `AlertEvidence` table |
| `RemoteIP` | `AlertEvidence` table |
| `AttackTechniques` | `AlertInfo` table |
| `ReportId` | この列は、通常、Microsoft Defender for Endpoint で他のテーブル内の関連レコードを検索するために使用されます。 Microsoft 365 Defender では、テーブルから直接関連データを取得 `AlertEvidence` できます。 |
| `Table` | この列は、通常、他の表の追加のイベント情報のために Microsoft Defender for Endpoint で使用されます。 Microsoft 365 Defender では、テーブルから直接関連データを取得 `AlertEvidence` できます。 |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a>エンドポイント用の既存の Microsoft Defender クエリを調整する
Microsoft Defender for Endpoint のクエリは、テーブルを参照しない限り、同じ方法で動作 `DeviceAlertEvents` します。 Microsoft 365 Defender でこれらのクエリを使用するには、次の変更を適用します。

- 置換 `DeviceAlertEvents` 後 `AlertInfo` の文字列
- テーブルとテーブル `AlertInfo` を `AlertEvidence` 結合して `AlertId` 、同等のデータを取得します。

### <a name="original-query"></a>元のクエリ
次のクエリは `DeviceAlertEvents` 、Microsoft Defender for Endpoint で使用して、エンドポイントに関連するアラート _をpowershell.exe。_

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a>クエリの変更
次のクエリは、Microsoft 365 Defender での使用に合わせて調整されています。 ファイル名を直接チェックする代わりに、テーブル内のファイル名を結合 `DeviceAlertEvents` `AlertEvidence` して確認します。

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="migrate-custom-detection-rules"></a>カスタム検出ルールを移行する

Microsoft Defender for Endpoint ルールが Microsoft 365 Defender で編集された場合、結果のクエリでデバイス テーブルのみを検索する場合と同様に機能し続ける。 たとえば、デバイス テーブルのみを照会するカスタム検出ルールによって生成されたアラートは、Microsoft Defender for Endpoint での構成方法に応じて、SIEM に配信され、電子メール通知を生成します。 Defender for Endpoint の既存の抑制ルールも引き続き適用されます。

Microsoft 365 Defender でのみ使用可能な ID と電子メール テーブルを照会する Defender for Endpoint ルールを編集すると、そのルールは自動的に Microsoft 365 Defender に移動されます。 

移行されたルールによって生成されたアラート:

- Defender for Endpoint ポータルに表示されなくなりました (Microsoft Defender セキュリティ センター)
- SIEM への配信を停止するか、メール通知を生成します。 この変更を回避するには、Microsoft 365 Defender 経由で通知を構成してアラートを取得します。 [Microsoft 365 Defender API を使用](api-incident.md)して、顧客検出のアラートや関連するインシデントに関する通知を受信できます。
- Microsoft Defender for Endpoint の抑制ルールでは抑制されません。 特定のユーザー、デバイス、またはメールボックスに対してアラートが生成されるのを防ぐには、対応するクエリを変更して、それらのエンティティを明示的に除外します。

この方法でルールを編集すると、そのような変更が適用される前に確認を求めるメッセージが表示されます。

Microsoft 365 Defender ポータルのカスタム検出ルールによって生成された新しいアラートは、次の情報を提供するアラート ページに表示されます。

- アラートのタイトルと説明 
- 影響を受け資産
- アラートに対して実行されたアクション
- アラートをトリガーしたクエリ結果 
- カスタム検出ルールに関する情報 
 
![新しいアラート ページの画像](../../media/newalertpage.png)

## <a name="write-queries-without-devicealertevents"></a>DeviceAlertEvents を使用せずにクエリを書き込む

Microsoft 365 Defender スキーマでは、さまざまなソースからのアラートに付随するさまざまな情報のセットに対応するために、表 `AlertInfo` `AlertEvidence` と表が提供されています。 

Microsoft Defender for Endpoint スキーマの表から取得するために使用したのと同じアラート情報を取得するには、テーブルをフィルター処理し、各一意 `DeviceAlertEvents` `AlertInfo` の `ServiceSource` ID `AlertEvidence` をテーブルに結合します。テーブルは、詳細なイベントとエンティティ情報を提供します。 

以下のサンプル クエリを参照してください。

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

このクエリは、Microsoft Defender for Endpoint スキーマよりも `DeviceAlertEvents` 多くの列を生成します。 結果を管理可能な状態に保つには、関心 `project` のある列のみを取得するために使用します。 次の例では、調査で PowerShell アクティビティが検出された場合に関心のある列をプロジェクトします。

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine 
```

通知に関係する特定のエンティティをフィルター処理する場合は、フィルター処理するエンティティの種類と値を指定します `EntityType` 。 次の例では、特定の IP アドレスを検索します。

```kusto
AlertInfo
| where Title == "Insert_your_alert_title"
| join AlertEvidence on AlertId 
| where EntityType == "Ip" and RemoteIP == "192.88.99.01" 
```

## <a name="see-also"></a>関連項目
- [Microsoft 365 Defender を有効にする](advanced-hunting-query-language.md)
- [高度な検出の概要](advanced-hunting-overview.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [Microsoft Defender for Endpoint での高度な検索](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)