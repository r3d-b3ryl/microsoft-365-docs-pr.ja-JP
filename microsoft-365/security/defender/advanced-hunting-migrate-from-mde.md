---
title: 高度なハンティング クエリをMicrosoft Defender for Endpointから移行する
description: Microsoft 365 Defenderで使用できるように、Microsoft Defender for Endpointクエリを調整する方法について説明します
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, Microsoft Defender for Endpoint, 検索, クエリ, テレメトリ, カスタム検出, スキーマ, kusto, マッピング
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 9fd00df5e61d37e5133f23e5f06973ceb99c4636
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2022
ms.locfileid: "64666176"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a>高度なハンティング クエリをMicrosoft Defender for Endpointから移行する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

高度なハンティング ワークフローをMicrosoft Defender for Endpointから移動し、より広範なデータ セットを使用して脅威をプロアクティブに検出します。 Microsoft 365 Defenderでは、次のような他のMicrosoft 365 セキュリティ ソリューションからデータにアクセスできます。

- Microsoft Defender for Endpoint
- Microsoft Defender for Office 365
- Microsoft Defender for Cloud Apps
- Microsoft Defender for Identity

>[!NOTE]
>ほとんどのMicrosoft Defender for Endpointのお客様は、[追加のライセンスなしでMicrosoft 365 Defenderを使用](prerequisites.md#licensing-requirements)できます。 Defender for Endpoint から高度なハンティング ワークフローの移行を開始するには、[Microsoft 365 Defenderをオンにします](m365d-enable.md)。

既存の Defender for Endpoint ワークフローに影響を与えずに移行できます。 保存されたクエリはそのまま残り、カスタム検出ルールは引き続き実行され、アラートが生成されます。 ただし、これらはMicrosoft 365 Defenderに表示されます。

## <a name="schema-tables-in-microsoft-365-defender-only"></a>Microsoft 365 Defender内のスキーマ テーブルのみ

[Microsoft 365 Defender高度なハンティング スキーマ](advanced-hunting-schema-tables.md)には、さまざまなMicrosoft 365セキュリティ ソリューションからのデータを含む追加のテーブルが用意されています。 次の表は、Microsoft 365 Defenderでのみ使用できます。

| テーブル名 | 説明 |
|------------|-------------|
| [AlertEvidence](advanced-hunting-alertevidence-table.md) | アラートに関連付けられているファイル、IP アドレス、URL、ユーザー、またはデバイス |
| [AlertInfo](advanced-hunting-alertinfo-table.md) | Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Defender for Cloud Apps、Microsoft Defender for Identityからのアラート重大度情報と脅威カテゴリを含む  |
| [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) | メールに添付されたファイルに関する情報 |
| [EmailEvents](advanced-hunting-emailevents-table.md) | メールの配信やブロック イベントなど、Microsoft 365 のメール イベント |
| [EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) | Microsoft 365 が受信者メールボックスにメールを配信した後に配信後に発生するセキュリティ イベント |
| [EmailUrlInfo](advanced-hunting-emailurlinfo-table.md) | メールの URL に関する情報 |
| [IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) | Active Directory (AD) を実行しているオンプレミス ドメイン コントローラーに関連するイベント。 このテーブルでは、ドメイン コントローラー上の ID 関連のイベントとシステム イベントの範囲を説明しています。 |
| [IdentityInfo](advanced-hunting-identityinfo-table.md) | Azure Active Directory など、様々なソースからのアカウント情報 |
| [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md) | Active Directory および Microsoft オンライン サービスでの認証イベント |
| [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) | ユーザー、グループ、デバイス、ドメインなどの Active Directory オブジェクトのクエリ |

>[!IMPORTANT]
> Microsoft 365 Defenderでのみ使用可能なスキーマ テーブルを使用するクエリとカスタム検出は、Microsoft 365 Defenderでのみ表示できます。

## <a name="map-devicealertevents-table"></a>Map DeviceAlertEvents テーブル

テーブルとテーブルは`AlertInfo`、`AlertEvidence`Microsoft Defender for Endpoint スキーマ内のテーブルを置き換えます`DeviceAlertEvents`。 デバイス アラートに関するデータに加えて、これら 2 つのテーブルには、ID、アプリ、電子メールのアラートに関するデータが含まれます。

次の表を使用して、列を列と`AlertEvidence`テーブル内の列にマップする方法`DeviceAlertEvents`を`AlertInfo`確認します。

> [!TIP]
> 次の表の列に加えて、 `AlertEvidence` さまざまなソースからのアラートのより包括的な画像を提供する他の多くの列も表に含まれています。 [すべての AlertEvidence 列を表示する](advanced-hunting-alertevidence-table.md)

| DeviceAlertEvents 列 | Microsoft 365 Defenderで同じデータを見つける場所 |
|-------------|-----------|-------------|-------------|
| `AlertId` | `AlertInfo` と  `AlertEvidence` テーブル |
| `Timestamp` | `AlertInfo` と  `AlertEvidence` テーブル |
| `DeviceId` | `AlertEvidence` テーブル |
| `DeviceName` | `AlertEvidence` テーブル |
| `Severity` | `AlertInfo` テーブル |
| `Category` | `AlertInfo` テーブル |
| `Title` | `AlertInfo` テーブル |
| `FileName` | `AlertEvidence` テーブル |
| `SHA1` | `AlertEvidence` テーブル |
| `RemoteUrl` | `AlertEvidence` テーブル |
| `RemoteIP` | `AlertEvidence` テーブル |
| `AttackTechniques` | `AlertInfo` テーブル |
| `ReportId` | この列は通常、他のテーブル内の関連レコードを検索するためにMicrosoft Defender for Endpointで使用されます。 Microsoft 365 Defenderでは、テーブルから直接関連データを`AlertEvidence`取得できます。 |
| `Table` | この列は、通常、他のテーブルの追加のイベント情報にMicrosoft Defender for Endpointで使用されます。 Microsoft 365 Defenderでは、テーブルから直接関連データを`AlertEvidence`取得できます。 |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a>既存のMicrosoft Defender for Endpoint クエリを調整する

Microsoft Defender for Endpointクエリは、テーブルを参照しない限り、そのまま動作します`DeviceAlertEvents`。 Microsoft 365 Defenderでこれらのクエリを使用するには、次の変更を適用します。

- `DeviceAlertEvents` を`AlertInfo` に置き換えます。
- テーブルとテーブルを`AlertInfo``AlertEvidence`結合して、同等の`AlertId`データを取得します。

### <a name="original-query"></a>元のクエリ

次のクエリは、Microsoft Defender for Endpointで _powershell.exe関連する_ アラートを取得するために使用`DeviceAlertEvents`します。

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d)
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```

### <a name="modified-query"></a>変更されたクエリ

次のクエリは、Microsoft 365 Defenderで使用するために調整されています。 ファイル名を直接 `DeviceAlertEvents`チェックする代わりに、テーブル内の `AlertEvidence` ファイル名を結合して確認します。

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where AttackTechniques has "PowerShell (T1086)"
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="migrate-custom-detection-rules"></a>カスタム検出規則を移行する

Microsoft Defender for EndpointルールがMicrosoft 365 Defenderで編集されると、結果のクエリがデバイス テーブルのみを参照する場合と同様に、ルールは引き続き機能します。

たとえば、デバイス テーブルのみにクエリを実行するカスタム検出ルールによって生成されたアラートは、Microsoft Defender for Endpointで構成した方法に応じて、引き続き SIEM に配信され、電子メール通知が生成されます。 Defender for Endpoint の既存の抑制ルールも引き続き適用されます。

Defender for Endpoint ルールを編集して ID と電子メール テーブルに対してクエリを実行すると(Microsoft 365 Defenderでのみ使用できます)、ルールは自動的にMicrosoft 365 Defenderに移動されます。

移行されたルールによって生成されるアラート:

- Defender for Endpoint ポータルに表示されなくなった (Microsoft Defender セキュリティ センター)
- SIEM への配信を停止するか、電子メール通知を生成します。 この変更を回避するには、Microsoft 365 Defenderを使用して通知を構成してアラートを取得します。 [Microsoft 365 Defender API](api-incident.md) を使用して、顧客検出アラートまたは関連するインシデントの通知を受信できます。
- Microsoft Defender for Endpoint抑制ルールでは抑制されません。 特定のユーザー、デバイス、またはメールボックスに対してアラートが生成されないようにするには、対応するクエリを変更して、それらのエンティティを明示的に除外します。

この方法でルールを編集すると、そのような変更が適用される前に確認を求めるメッセージが表示されます。

Microsoft 365 Defenderのカスタム検出ルールによって生成された新しいアラートは、次の情報を提供するアラート ページに表示されます。

- アラートのタイトルと説明
- 影響を受けた資産
- アラートに応答して実行されたアクション
- アラートをトリガーしたクエリ結果
- カスタム検出規則に関する情報

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/new-alert-page.png" alt-text="カスタム検出ルールによって生成された新しいアラートをポータルに表示するアラート ページMicrosoft 365 Defender例" lightbox="../../media/new-alert-page.png":::

## <a name="write-queries-without-devicealertevents"></a>DeviceAlertEvents を使用せずにクエリを書き込む

Microsoft 365 Defender スキーマでは、さまざまなソースからのアラートに`AlertInfo`付随する多様な情報セットに対応するために、テーブルと`AlertEvidence`テーブルが提供されます。

Microsoft Defender for Endpoint スキーマのテーブルから`DeviceAlertEvents`取得したのと同じアラート情報を取得するには、テーブルを`ServiceSource`フィルター処理`AlertInfo`し、各一意の ID をテーブルに`AlertEvidence`結合します。これにより、詳細なイベントとエンティティの情報が提供されます。

次のサンプル クエリを参照してください。

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

このクエリでは、Microsoft Defender for Endpoint スキーマよりも`DeviceAlertEvents`多くの列が生成されます。 結果を管理しやすい状態にするには、 `project` 目的の列のみを取得します。 次の例では、調査で PowerShell アクティビティが検出されたときに関心のある列をプロジェクトします。

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine
```

アラートに関係する特定のエンティティをフィルター処理する場合は、エンティティの種類 `EntityType` とフィルター処理する値を指定します。 次の例では、特定の IP アドレスを検索します。

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
- [Microsoft Defender for Endpointでの高度なハンティング](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
