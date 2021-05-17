---
title: Microsoft Defender の脅威エクスプローラーとリアルタイム検出Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: エクスプローラーまたはリアルタイム検出を使用して、脅威を効率的に調査して対応します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7ab7b5731d121106d930868b03330d4ac7befd77
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300157"
---
# <a name="threat-explorer-and-real-time-detections-basics"></a>脅威エクスプローラーおよびリアルタイムの検出の基本

この記事の内容:

- [脅威エクスプローラーとリアルタイム検出の違い](#differences-between-threat-explorer-and-real-time-detections)<br/>
- [必要なライセンスとアクセス許可](#required-licenses-and-permissions)

> [!NOTE]
> これは、Threat **Explorer (Explorer)** 、電子メール セキュリティ、**エクスプローラー** とリアルタイム検出の基本 (ツールの違い、操作に必要なアクセス許可など) に関する **3** 記事シリーズの一部です。 このシリーズの他の 2 つの記事は、Threat Explorer での脅威の検出と [、](threat-hunting-in-threat-explorer.md) 脅威エクスプローラーを [使用したメール セキュリティです](email-security-in-microsoft-defender.md)。

この記事では、脅威の調査とリアルタイムの検出レポートの違い、および必要なライセンスとアクセス許可について説明します。

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

組織に Office [365](defender-for-office-365.md)用の Microsoft Defender を使用 [](#required-licenses-and-permissions)し、アクセス許可がある場合は、脅威エクスプローラー **(エクスプローラー** と **呼** ばれる) またはリアルタイム検出を使用して、脅威を検出して修復できます。

[セキュリティ **& コンプライアンス** センター] で、[脅威の管理] に移動し、[**エクスプローラー**  ] または [リアルタイム検出]**を選択します**。

<br>

****

|Microsoft Defender for Office 365 プラン 2 では、次の情報が表示されます。|Microsoft Defender for Office 365 プラン 1 では、次の情報が表示されます。|
|---|---|
|![脅威エクスプローラー](../../media/threatmgmt-explorer.png)|![リアルタイムの検出](../../media/threatmgmt-realtimedetections.png)|
|

これらのツールで以下のことができます。

- Microsoft 365 のセキュリティ機能によって検出されたマルウェアを参照してください。
- フィッシング URL を表示し、[評決データ] をクリックします。
- エクスプローラーでビューから自動調査と応答プロセスを開始します。
- 悪意のあるメールなどについて調査します。

詳細については、「Threat [Explorer を使用したメール セキュリティ」を参照してください](email-security-in-microsoft-defender.md)。

## <a name="differences-between-threat-explorer-and-real-time-detections"></a>脅威エクスプローラーとリアルタイム検出の違い

- *リアルタイム検出は、Defender* で 365 プラン 1 で使用Officeツールです。 *Threat Explorer* は、Defender で 365 プラン 2 の脅威Office修復ツールです。
- リアルタイム検出レポートを使用すると、リアルタイムで検出を表示できます。 脅威エクスプローラーも同様にこれを実行しますが、攻撃キャンペーンの強調表示など、特定の攻撃に関する追加の詳細を提供し、セキュリティ運用チームに脅威を修復する機能 (自動調査[](automated-investigation-response-office.md)と応答調査のトリガーを含む) を提供します。
- すべての *電子メール ビュー* は脅威エクスプローラーで使用できますが、リアルタイム検出レポートには含まれません。
- 豊富なフィルター機能と修復アクションは、Threat Explorer に含まれています。 詳細については [、「Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 プラン」を参照してください](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。

## <a name="required-licenses-and-permissions"></a>必要なライセンスとアクセス許可

エクスプローラーまたは [リアルタイム検出のいずれかを使用するには、Office 365](defender-for-office-365.md) 用の Microsoft Defender が必要です。

- ただし、エクスプローラーは、365 プラン 2 Office Defender にのみ含まれます。
- リアルタイム検出レポートは、Defender for Office 365 プラン 1 に含まれています。

セキュリティ運用チームは、Office 365 の Defender によって保護される必要があるすべてのユーザーにライセンスを割り当て、エクスプローラーとリアルタイムの検出では、ライセンスを持つユーザーの検出データが表示される点に注意する必要があります。

エクスプローラーまたはリアルタイムの検出 *を* 表示および使用するには、次の情報が必要です。

- セキュリティ コンプライアンス センター&:

  - 組織の管理
  - セキュリティ管理者 (これは Azure Active Directory 管理センター ( ) で割り当 <https://aad.portal.azure.com> てることができます。
  - セキュリティ閲覧者

- Exchange Online の場合:

  - 組織の管理
  - 表示専用組織の管理
  - "View-Only Recipients/表示専用受信者"
  - コンプライアンス管理

役割とアクセス許可の詳細については、次のリソースを参照してください。

- [セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)
- [Exchange Online の機能アクセス許可](/exchange/permissions-exo/feature-permissions)
- [Exchange Online の PowerShell](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a>詳細情報
- [脅威エクスプローラーは、電子メール エンティティ ページで電子メールの詳細を収集します。](mdo-email-entity-page.md)
- [配信された悪意のあるメールの検索と調査](investigate-malicious-email-that-was-delivered.md)
- [SharePoint Online、OneDrive、Microsoft Teams で検出された悪意のあるファイルを表示する](mdo-for-spo-odb-and-teams.md)
- [脅威保護の状態レポート](view-email-security-reports.md#threat-protection-status-report)
- [Microsoft Threat Protection での自動調査および対応](automated-investigation-response-office.md)