---
title: Microsoft Defender for Endpoint から高度なハンティング クエリを移行する
description: Microsoft 365 Defender で使用できるよう、Microsoft Defender for Endpoint クエリを調整する方法について説明します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft の脅威の保護、microsoft 365、mtp、m365、microsoft Defender atp、mdatp、検索、クエリ、テレメトリ、カスタム検出、スキーマ、kusto、microsoft 365、マッピング
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: c0a29f93b9ea926beaeecb840ba108da04a89ebb
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51501142"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint から高度なハンティング クエリを移行する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

高度なハンティング ワークフローを Microsoft Defender for Endpoint から移動して、より広範なデータセットを使用して脅威を積極的に検出します。 Microsoft 365 Defender では、次を含む他の Microsoft 365 セキュリティ ソリューションからデータにアクセスできます。

- Microsoft Defender for Endpoint
- Microsoft Defender for Office 365
- Microsoft Cloud App Security
- Microsoft Defender for Identity

>[!NOTE]
>ほとんどの Microsoft Defender for Endpoint のお客様は、追加のライセンスなしで [Microsoft 365 Defender を使用できます](prerequisites.md#licensing-requirements)。 Defender for Endpoint から高度なハンティング ワークフローの移行を開始するには [、Microsoft 365 Defender をオンにしてください](m365d-enable.md)。

既存の Defender for Endpoint ワークフローに影響を与えることなく移行できます。 保存されたクエリはそのまま残り、カスタム検出ルールは引き続き実行され、アラートが生成されます。 ただし、Microsoft 365 Defender に表示されます。 

## <a name="schema-tables-in-microsoft-365-defender-only"></a>Microsoft 365 Defender のスキーマ テーブルのみ
[Microsoft 365 Defender の](advanced-hunting-schema-tables.md)高度なハンティング スキーマには、さまざまな Microsoft 365 セキュリティ ソリューションのデータを含む追加のテーブルが含まれています。 次の表は、Microsoft 365 Defender でのみ使用できます。

| テーブル名 | 説明 |
|------------|-------------|
| [AlertEvidence](advanced-hunting-alertevidence-table.md) | アラートに関連付けられたファイル、IP アドレス、URL、ユーザー、またはデバイス |
| [AlertInfo](advanced-hunting-alertinfo-table.md) | Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Cloud App Security、Microsoft Defender for Identity からのアラート (重大度情報と脅威カテゴリを含む)  |
| [AppFileEvents](advanced-hunting-appfileevents-table.md) | クラウド アプリとサービスでのファイル関連のアクティビティ |
| [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) | メールに添付されているファイルに関する情報 |
| [EmailEvents](advanced-hunting-emailevents-table.md) | Microsoft 365 の電子メール イベント (メール配信イベントやブロック イベントを含む) |
| [EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) | Microsoft 365 が受信者メールボックスにメールを配信した後に配信後に発生するセキュリティ イベント |
| [EmailUrlInfo](advanced-hunting-emailurlinfo-table.md) | メールの URL に関する情報 |
| [IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) | Active Directory を実行しているオンプレミスのドメイン コントローラーに関連するイベント (AD)。 次の表では、ドメイン コントローラー上の ID 関連イベントとシステム イベントの範囲について説明します。 |
| [IdentityInfo](advanced-hunting-identityinfo-table.md) | Azure Active Directory を含むさまざまなソースからのアカウント情報 |
| [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md) | Active Directory および Microsoft オンライン サービスでの認証イベント |
| [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) | ユーザー、グループ、デバイス、ドメインなどの Active Directory オブジェクトのクエリ |

>[!IMPORTANT]
> Microsoft 365 Defender でのみ使用できるスキーマ テーブルを使用するクエリとカスタム検出は、Microsoft 365 Defender でのみ表示できます。

## <a name="map-devicealertevents-table"></a>DeviceAlertEvents テーブルのマップ
テーブル `AlertInfo` と `AlertEvidence` テーブルは `DeviceAlertEvents` 、Microsoft Defender for Endpoint スキーマのテーブルを置き換える。 デバイス通知に関するデータに加えて、これら 2 つのテーブルには、ID、アプリ、および電子メールのアラートに関するデータが含まれます。

次の表を使用して、列 `DeviceAlertEvents` が列とテーブルの列にマップされる方法 `AlertInfo` を確認 `AlertEvidence` します。

>[!TIP]
>次の表の列に加えて、さまざまなソースからのアラートの全体的な画像を提供する他の多くの列 `AlertEvidence` も含まれています。 [すべての AlertEvidence 列を表示する](advanced-hunting-alertevidence-table.md) 

| DeviceAlertEvents 列 | Microsoft 365 Defender で同じデータを見つける場所 |
|-------------|-----------|-------------|-------------|
| `AlertId` | `AlertInfo` テーブル  `AlertEvidence` とテーブル |
| `Timestamp` | `AlertInfo` テーブル  `AlertEvidence` とテーブル |
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
| `ReportId` | この列は、通常、Microsoft Defender for Endpoint で他のテーブル内の関連レコードを検索するために使用されます。 Microsoft 365 Defender では、関連するデータをテーブルから直接取得 `AlertEvidence` できます。 |
| `Table` | この列は、通常、Microsoft Defender for Endpoint で他のテーブルの追加イベント情報として使用されます。 Microsoft 365 Defender では、関連するデータをテーブルから直接取得 `AlertEvidence` できます。 |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a>既存の Microsoft Defender for Endpoint クエリを調整する
Microsoft Defender for Endpoint クエリは、テーブルを参照しない限り、現在通り動作 `DeviceAlertEvents` します。 Microsoft 365 Defender でこれらのクエリを使用するには、次の変更を適用します。

- に `DeviceAlertEvents` 置き換える `AlertInfo` 。
- テーブルとテーブル `AlertInfo` を `AlertEvidence` 結合して `AlertId` 同等のデータを取得します。

### <a name="original-query"></a>元のクエリ
次のクエリは `DeviceAlertEvents` 、Microsoft Defender for Endpoint で使用して、エンドポイントに関連するアラートをpowershell.exe。

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a>変更されたクエリ
次のクエリは、Microsoft 365 Defender での使用に合わせて調整されています。 ファイル名を直接からチェックする代わりに、そのテーブル内のファイル名を結合 `DeviceAlertEvents` `AlertEvidence` してチェックします。

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="migrate-custom-detection-rules"></a>カスタム検出ルールの移行

Microsoft Defender for Endpoint ルールが Microsoft 365 Defender で編集されている場合、結果のクエリでデバイス テーブルのみを参照する場合、以前と同様に機能し続ける。 

たとえば、デバイス テーブルのみをクエリするカスタム検出ルールによって生成されたアラートは、Microsoft Defender for Endpoint での構成方法に応じて、引き続き SIEM に配信され、電子メール通知を生成します。 Defender for Endpoint の既存の抑制ルールも引き続き適用されます。

Defender for Endpoint ルールを編集して、Microsoft 365 Defender でのみ使用できる ID テーブルと電子メール テーブルを照会すると、そのルールは自動的に Microsoft 365 Defender に移動されます。 

移行されたルールによって生成されるアラート:

- Defender for Endpoint ポータルに表示されなくなりました (Microsoft Defender セキュリティ センター)
- SIEM への配信を停止するか、電子メール通知を生成します。 この変更を回避するには、Microsoft 365 Defender を使用して通知を構成して、アラートを取得します。 [Microsoft 365 Defender API を使用して](api-incident.md)、顧客検出アラートまたは関連インシデントに関する通知を受信できます。
- Microsoft Defender for Endpoint 抑制ルールでは抑制されません。 特定のユーザー、デバイス、またはメールボックスに対してアラートが生成されるのを防ぐために、対応するクエリを変更して、それらのエンティティを明示的に除外します。

この方法でルールを編集すると、そのような変更が適用される前に確認を求めるメッセージが表示されます。

Microsoft 365 Defender ポータルのカスタム検出ルールによって生成された新しいアラートは、次の情報を提供するアラート ページに表示されます。

- アラートのタイトルと説明 
- 影響を受け取ったアセット
- アラートに応答して実行されるアクション
- アラートをトリガーしたクエリ結果 
- カスタム検出ルールに関する情報 
 
![新しいアラート ページのイメージ](../../media/new-alert-page.png)

## <a name="write-queries-without-devicealertevents"></a>DeviceAlertEvents を使用せずにクエリを書き込む

Microsoft 365 Defender スキーマでは、さまざまなソースからのアラートに付随する多様な情報セットに対応するために、テーブル `AlertInfo` `AlertEvidence` とテーブルが提供されます。 

Microsoft Defender for Endpoint スキーマのテーブルから取得したのと同じアラート情報を取得するには、テーブルをフィルター処理し、各一意 `DeviceAlertEvents` `AlertInfo` の `ServiceSource` ID `AlertEvidence` をテーブルに結合して、詳細なイベントとエンティティ情報を提供します。 

以下のサンプル クエリを参照してください。

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

このクエリは、Microsoft Defender for Endpoint スキーマよりも `DeviceAlertEvents` 多くの列を生成します。 結果を管理し続けるには、関心 `project` のある列のみを取得します。 次の例では、調査で PowerShell アクティビティが検出された場合に関心のある列をプロジェクトします。

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine 
```

アラートに関連する特定のエンティティをフィルター処理する場合は、エンティティの種類とフィルター処理する値を指定します `EntityType` 。 次の例では、特定の IP アドレスを検索します。

```kusto
AlertInfo
| where Title == "Insert_your_alert_title"
| join AlertEvidence on AlertId 
| where EntityType == "Ip" and RemoteIP == "192.88.99.01" 
```

## <a name="see-also"></a>関連項目
- [Microsoft 365 Defender を有効にする](advanced-hunting-query-language.md)
- [高度な追求の概要](advanced-hunting-overview.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [エンドポイント向け Microsoft Defender での高度な検索](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)