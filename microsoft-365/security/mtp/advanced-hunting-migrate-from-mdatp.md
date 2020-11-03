---
title: エンドポイントの Microsoft Defender から高度な検索クエリを移行する
description: Microsoft 365 Defender で使用できるように Microsoft Defender をエンドポイントクエリ用に調整する方法について説明します。
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
ms.openlocfilehash: 8b69dff94cc5d3ba3331fd6d13b1d7de1402ac47
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846858"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a>エンドポイントの Microsoft Defender から高度な検索クエリを移行する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

より広範なデータセットを使用して脅威を事前にハントするために、Microsoft Defender から高度な検索ワークフローを移動します。 Microsoft 365 Defender では、次のような他の Microsoft 365 セキュリティソリューションからデータにアクセスできます。

- Microsoft Defender for Endpoint
- Microsoft Defender for Office 365
- Microsoft Cloud App Security
- Id の Microsoft Defender

>[!NOTE]
>エンドポイントのお客様のための Microsoft Defender の多くは、ライセンスを追加すること [なく microsoft 365 Defender を使用](prerequisites.md#licensing-requirements)できます。 エンドポイントの Defender から高度な検索ワークフローへの移行を開始するには、 [Microsoft 365 Defender をオン](mtp-enable.md)にします。

エンドポイントワークフローの既存の Defender に影響を与えることなく移行できます。 保存されたクエリはそのまま残り、カスタムの検出ルールは引き続き実行され、通知を生成します。 ただし、これらは Microsoft 365 Defender に表示されます。 

## <a name="schema-tables-in-microsoft-365-defender-only"></a>Microsoft 365 Defender のスキーマテーブルのみ
[Microsoft 365 Defender の高度な検索スキーマ](advanced-hunting-schema-tables.md)では、microsoft 365 のさまざまなセキュリティソリューションからのデータを含むテーブルが追加されています。 次の表は、Microsoft 365 Defender でのみ使用できます。

| テーブル名 | 説明 |
|------------|-------------|
| [AlertEvidence](advanced-hunting-alertevidence-table.md) | アラートに関連付けられているファイル、IP アドレス、Url、ユーザー、またはデバイス |
| [AlertInfo](advanced-hunting-alertinfo-table.md) | エンドポイントの Microsoft Defender、microsoft Defender for Office 365、Microsoft Cloud App Security、および Id (重要度情報や脅威カテゴリを含む) に関する microsoft defender からの通知  |
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
`AlertInfo` `AlertEvidence` エンドポイントスキーマでは、Microsoft Defender のテーブルがとテーブルに置き換えられ `DeviceAlertEvents` ます。 デバイス通知に関するデータに加えて、これらの2つのテーブルには、id、アプリ、電子メールの警告に関するデータが含まれています。

次の表を使用し `DeviceAlertEvents` て、列とテーブル内の列をどのようにマッピングするかを確認し `AlertInfo` `AlertEvidence` ます。

>[!TIP]
>表には、次の表に加えて、 `AlertEvidence` さまざまなソースからのアラートの全体的な概要を提供する、他の多くの列が含まれています。 [すべての AlertEvidence 列を表示する](advanced-hunting-alertevidence-table.md) 

| DeviceAlertEvents 列 | Microsoft 365 Defender で同じデータを検索する場所 |
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
| `ReportId` | この列は、通常、エンドポイントの Microsoft Defender で、他のテーブル内の関連レコードを検索するために使用されます。 Microsoft 365 Defender では、関連するデータをテーブルから直接取得することができ `AlertEvidence` ます。 |
| `Table` | この列は、通常、他のテーブルの追加のイベント情報をエンドポイントとして Microsoft Defender で使用します。 Microsoft 365 Defender では、関連するデータをテーブルから直接取得することができ `AlertEvidence` ます。 |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a>エンドポイントクエリ用に既存の Microsoft Defender を調整する
エンドポイントクエリの場合、Microsoft Defender は、そのテーブルを参照していない限り、として機能し `DeviceAlertEvents` ます。 Microsoft 365 Defender でこれらのクエリを使用するには、次の変更を適用します。

- `DeviceAlertEvents`をに置き換え `AlertInfo` ます。
- とのテーブルを結合して、 `AlertInfo` `AlertEvidence` 同等の `AlertId` データを取得します。

### <a name="original-query"></a>元のクエリ
次のクエリは、 `DeviceAlertEvents` エンドポイントの Microsoft Defender で、 _powershell.exe_ に関連する警告を取得するために使用します。

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a>変更されたクエリ
次のクエリは、Microsoft 365 Defender で使用するように調整されています。 ファイル名をから直接チェックする代わりに `DeviceAlertEvents` 、その `AlertEvidence` テーブル内のファイル名を結合して確認します。

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="related-topics"></a>関連項目
- [Microsoft 365 Defender をオンにする](advanced-hunting-query-language.md)
- [高度な検出の概要](advanced-hunting-overview.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [エンドポイントの Microsoft Defender での高度な検索](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)