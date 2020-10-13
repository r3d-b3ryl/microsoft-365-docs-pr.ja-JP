---
title: Microsoft Defender ATP から高度な検索クエリを移行する
description: Microsoft Defender ATP クエリを調整して Microsoft の脅威保護に使用できるようにする方法について説明します。
keywords: 高度な検索、脅威の探し、サイバーの脅威の検索、microsoft の脅威の防止、microsoft 365、mtp、m365、microsoft defender atp、mdatp、検索、クエリ、テレメトリ、カスタム検出、スキーマ、kusto、microsoft 365、マッピング
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: f56360b28a9fe9de4198d97954a64a429d1d99a5
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429697"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-atp"></a>Microsoft Defender ATP から高度な検索クエリを移行する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft Threat Protection

高度な検索ワークフローを Microsoft Defender ATP から移動して、より広範なデータセットを使用して脅威を事前に探します。 Microsoft の脅威保護では、他の Microsoft 365 セキュリティソリューション (次のものを含む) からデータにアクセスできます。

- Microsoft Defender Advanced Threat Protection
- Office 365 Advanced Threat Protection
- Microsoft Cloud App Security
- Azure Advanced Threat Protection

>[!NOTE]
>多くの Microsoft Defender ATP のお客様は、 [追加のライセンスを持たずに microsoft の脅威保護を使用](prerequisites.md#licensing-requirements)できます。 Microsoft Defender ATP から高度な検索ワークフローの移行を開始するには、 [microsoft の脅威保護を有効](mtp-enable.md)にします。

既存の Microsoft Defender ATP ワークフローに影響を与えることなく移行できます。 保存されたクエリはそのまま残り、カスタムの検出ルールは引き続き実行され、通知を生成します。 ただし、これらは Microsoft の脅威保護に表示されます。 

## <a name="schema-tables-in-microsoft-threat-protection-only"></a>Microsoft の脅威保護のスキーマテーブル
[Microsoft Threat Protection の高度な検索スキーマ](advanced-hunting-schema-tables.md)は、microsoft 365 のさまざまなセキュリティソリューションからのデータを含むテーブルを追加します。 次の表は、Microsoft の脅威保護でのみ利用可能です。

| テーブル名 | 説明 |
|------------|-------------|
| [AlertEvidence](advanced-hunting-alertevidence-table.md) | アラートに関連付けられているファイル、IP アドレス、Url、ユーザー、またはデバイス |
| [AlertInfo](advanced-hunting-alertinfo-table.md) | Microsoft Defender ATP、Office 365 ATP、Microsoft Cloud App Security、および Azure ATP (重大度情報や脅威カテゴリを含む) からの通知  |
| [AppFileEvents](advanced-hunting-appfileevents-table.md) | クラウドアプリとサービスのファイル関連アクティビティ |
| [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) | 電子メールに添付されたファイルに関する情報 |
| [EmailEvents](advanced-hunting-emailevents-table.md) | Microsoft 365 の電子メールイベント (電子メール配信およびブロックイベントを含む) |
| [EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) | Microsoft 365 がメールを受信者のメールボックスに配信した後の、配信後に発生するセキュリティイベント |
| [EmailUrlInfo](advanced-hunting-emailurlinfo-table.md) | メールの Url に関する情報 |
| [IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) | Active Directory (AD) を実行しているオンプレミスのドメインコントローラーに関係するイベント。 この表は、ドメインコントローラーの id 関連イベントとシステムイベントの範囲を示しています。 |
| [IdentityInfo](advanced-hunting-identityinfo-table.md) | Azure Active Directory を含む、さまざまなソースからのアカウント情報 |
| [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md) | Active Directory と Microsoft online services の認証イベント |
| [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) | ユーザー、グループ、デバイス、ドメインなどの Active Directory オブジェクトに対するクエリ |

## <a name="map-devicealertevents-table"></a>DeviceAlertEvents テーブルのマップ
`AlertInfo`とテーブルは、 `AlertEvidence` `DeviceAlertEvents` Microsoft Defender ATP スキーマの表を置換します。 デバイス通知に関するデータに加えて、これらの2つのテーブルには、id、アプリ、電子メールの警告に関するデータが含まれています。

次の表を使用し `DeviceAlertEvents` て、列とテーブル内の列をどのようにマッピングするかを確認し `AlertInfo` `AlertEvidence` ます。

>[!TIP]
>表には、次の表に加えて、 `AlertEvidence` さまざまなソースからのアラートの全体的な概要を提供する、他の多くの列が含まれています。 [すべての AlertEvidence 列を表示する](advanced-hunting-alertevidence-table.md) 

| DeviceAlertEvents 列 | Microsoft の脅威保護で同じデータを検索する場所 |
|-------------|-----------|-------------|-------------|
| `AlertId` | `AlertInfo` および  `AlertEvidence` テーブル |
| `Timestamp` | `AlertInfo` および  `AlertEvidence` テーブル |
| `DeviceId` | `AlertEvidence`  |
| `DeviceName` | `AlertEvidence`  |
| `Severity` | `AlertInfo`  |
| `Category` | `AlertInfo`  |
| `Title` | `AlertInfo`  |
| `FileName` | `AlertEvidence`  |
| `SHA1` | `AlertEvidence`  |
| `RemoteUrl` | `AlertEvidence`  |
| `RemoteIP` | `AlertEvidence`  |
| `AttackTechniques` | `AlertInfo`  |
| `ReportId` | この列は、通常、Microsoft Defender ATP で他のテーブル内の関連レコードを検索するために使用されます。 Microsoft の脅威保護では、関連するデータをテーブルから直接取得することができ `AlertEvidence` ます。 |
| `Table` | この列は、通常、Microsoft Defender ATP で他のテーブルの追加イベント情報に使用されます。 Microsoft の脅威保護では、関連するデータをテーブルから直接取得することができ `AlertEvidence` ます。 |

## <a name="adjust-existing-microsoft-defender-atp-queries"></a>既存の Microsoft Defender ATP クエリを調整する
Microsoft Defender ATP クエリは、テーブルを参照していない限り、として機能し `DeviceAlertEvents` ます。 Microsoft の脅威保護でこれらのクエリを使用するには、次の変更を適用します。

- `DeviceAlertEvents`をに置き換え `AlertInfo` ます。
- とのテーブルを結合して、 `AlertInfo` `AlertEvidence` 同等の `AlertId` データを取得します。

### <a name="original-query"></a>元のクエリ
次のクエリは、 `DeviceAlertEvents` Microsoft DEFENDER ATP で、 _powershell.exe_に関連する警告を取得するために使用します。

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a>変更されたクエリ
次のクエリは、Microsoft の脅威保護で使用するように調整されています。 ファイル名をから直接チェックする代わりに `DeviceAlertEvents` 、その `AlertEvidence` テーブル内のファイル名を結合して確認します。

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="related-topics"></a>関連項目
- [Microsoft Threat Protection を有効にする](advanced-hunting-query-language.md)
- [高度な検出の概要](advanced-hunting-overview.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [Microsoft Defender ATP での高度な検索](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)