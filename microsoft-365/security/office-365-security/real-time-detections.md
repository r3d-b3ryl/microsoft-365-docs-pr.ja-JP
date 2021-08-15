---
title: Microsoft Defender の脅威エクスプローラーとリアルタイム検出の基本Office 365
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
ms.openlocfilehash: a89ed9eed07be2d66336dcab799e45d155151fce252f163c1d0eb27f43a4ac46
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53867477"
---
# <a name="explorer-and-real-time-detections-basics"></a>エクスプローラーとリアルタイム検出の基本

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

この記事の内容:

- [エクスプローラーとリアルタイムの検出の違い](#differences-between-explorer-and-real-time-detections)
- [必要なライセンスとアクセス許可](#required-licenses-and-permissions)

> [!NOTE]
> これは **、Explorer (** 脅威エクスプローラーとも呼ばれる) 、電子メール セキュリティ、**エクスプローラー** とリアルタイム検出の基本 (ツールの違い、操作に必要なアクセス許可など) の **3** 記事シリーズの一部です。 このシリーズの他の 2 つの記事は [、Explorer での](threat-hunting-in-threat-explorer.md) 脅威の検出とエクスプローラー [を使用したメール セキュリティです](email-security-in-microsoft-defender.md)。

この記事では、エクスプローラーとリアルタイム検出レポートの違い、および必要なライセンスとアクセス許可について説明します。

組織に microsoft [Defender for Office 365](defender-for-office-365.md)がある場合、アクセス許可 [](#required-licenses-and-permissions)がある場合は、エクスプローラー **(脅威****エクスプローラーとも呼** ばれる) またはリアルタイム検出を使用して、脅威を検出して修復できます。

[ポータル( Microsoft 365 Defender] で、[電子メール グループ&] に移動し、[エクスプローラー] または [リアルタイム検出] <https://security.microsoft.com> **を選択します**。 

これらのツールで以下のことができます。

- セキュリティ機能によって検出されたマルウェアMicrosoft 365参照してください。
- フィッシング URL を表示し、[評決データ] をクリックします。
- エクスプローラーでビューから自動調査と応答プロセスを開始します。
- 悪意のあるメールなどについて調査します。

詳細については、「Explorer を使用 [したメール セキュリティ」を参照してください](email-security-in-microsoft-defender.md)。

## <a name="differences-between-explorer-and-real-time-detections"></a>エクスプローラーとリアルタイムの検出の違い

- *リアルタイム検出は、Defender* でプラン 1 で使用できるレポート Office 365ツールです。 *Threat Explorer* は、Defender で利用可能な脅威の検出と修復ツールで、Office 365 2 です。
- リアルタイム検出レポートを使用すると、リアルタイムで検出を表示できます。 脅威エクスプローラーも同様にこれを実行しますが、攻撃キャンペーンの強調表示など、特定の攻撃に関する追加の詳細を提供し、セキュリティ運用チームに脅威を修復する機能 (自動調査[](automated-investigation-response-office.md)と応答調査のトリガーを含む) を提供します。
- すべての *電子メール ビュー* は脅威エクスプローラーで使用できますが、リアルタイム検出レポートには含まれません。
- 豊富なフィルター機能と修復アクションは、Threat Explorer に含まれています。 詳細については[、「Microsoft Defender for Office 365 サービスの説明:](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)Defender 全体の機能の可用性」を参照してください。Office 365してください。

## <a name="required-licenses-and-permissions"></a>必要なライセンスとアクセス許可

エクスプローラーまたは[リアルタイム検出のいずれかをOffice 365](defender-for-office-365.md)するには、Microsoft Defender が必要です。

- エクスプローラーは、プラン 2 の Defender にのみOffice 365されます。
- リアルタイム検出レポートは、Defender for Office 365プラン 1 に含まれています。

セキュリティ運用チームは、Office 365 の Defender によって保護される必要があるすべてのユーザーにライセンスを割り当て、エクスプローラーとリアルタイムの検出では、ライセンスを持つユーザーの検出データが表示される点に注意する必要があります。

エクスプローラーまたはリアルタイム検出を *表示* および使用するには、次のアクセス許可が必要です。

- [Defender for Office 365:
  - 組織の管理
  - セキュリティ管理者 (この管理者は、管理者センター Azure Active Directory割り当てることができます ( <https://aad.portal.azure.com> )
  - セキュリティ閲覧者
- 次のExchange Online。
  - 組織の管理
  - 表示専用組織の管理
  - "View-Only Recipients/表示専用受信者"
  - コンプライアンス管理

役割とアクセス許可の詳細については、次の記事を参照してください。

- [Microsoft 365 Defender ポータルのアクセス許可](permissions-microsoft-365-security-center.md)
- [Exchange Online のアクセス許可](/e/exchange/permissions-exo/permissions-exo)

## <a name="more-information"></a>詳細

- [脅威エクスプローラーは、電子メール エンティティ ページで電子メールの詳細を収集します。](mdo-email-entity-page.md)
- [配信された悪意のあるメールの検索と調査](investigate-malicious-email-that-was-delivered.md)
- [オンライン、オンライン、SharePoint、およびOneDriveで検出された悪意のあるMicrosoft Teams](mdo-for-spo-odb-and-teams.md)
- [脅威保護の状態レポート](view-email-security-reports.md#threat-protection-status-report)
- [Microsoft Threat Protection での自動調査および対応](automated-investigation-response-office.md)
