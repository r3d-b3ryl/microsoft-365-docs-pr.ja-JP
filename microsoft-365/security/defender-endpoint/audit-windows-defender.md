---
title: Microsoft Defender for Endpoint の機能が監査モードで動作する方法をテストする
description: 監査モードは、Microsoft Defender for Endpoint が有効になっている場合にデバイスを保護する方法を確認するのに役立ちます。
keywords: exploit guard, audit, auditing, mode, enabled, disabled, test, demo, evaluate, lab
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7ce652d58be2d9ff28d82c088d5471a7bffdf6dc
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570974"
---
# <a name="test-how-microsoft-defender-for-endpoint-features-work-in-audit-mode"></a>Microsoft Defender for Endpoint の機能が監査モードで動作する方法をテストする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


監査モードでは、攻撃表面の縮小ルール、エクスプロイト保護、ネットワーク保護、およびフォルダー アクセスの制御を有効にできます。 監査モードでは、機能を有効にした場合に何が起こったかの記録を確認できます。

組織での機能の動作をテストするときに、監査モードを有効にできます。 これにより、一行のアプリが影響を受けずに行うのに役立ちます。 また、一定の期間に発生する疑わしいファイル変更の試行回数を確認できます。

この機能は、アプリ、スクリプト、またはファイルが変更されるのをブロックまたは防止できません。 ただし、イベント ログWindows機能が完全に有効になっている場合と同様にイベントが記録されます。 監査モードでは、イベント ログを確認して、機能が有効な場合にどのような影響を与えたかを確認できます。

監査されたエントリを見つけるには、「Applications and Services Microsoft **Windows Windows Defender**  >    >    >    >  **します**。

Defender for Endpoint を使用すると、特に攻撃表面の縮小ルールを調査するために、各イベントの詳細を取得できます。 Defender for Endpoint コンソールを使用すると、アラートタイムラインと調査シナリオの一部として問題 [を調査できます](investigate-alerts.md)。

グループ ポリシー、PowerShell、および構成サービス プロバイダー (CSP) を使用して監査モードを有効にできます。

> [!TIP]
> また、テストグラウンドのWindows Defenderに[アクセスして](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)demo.wd.microsoft.com 機能を確認し、機能の動作を確認できます。

 **監査オプション** | **監査モードを有効にする方法** | **イベントを表示する方法**
|---------|---------|---------|
| 監査はすべてのイベントに適用されます | [制御されたフォルダー アクセスを有効にする](enable-controlled-folders.md) | [フォルダー アクセスイベントの制御](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| 監査は個々のルールに適用されます | [攻撃面の減少ルールを有効にする](enable-attack-surface-reduction.md) | [攻撃表面の縮小ルール イベント](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| 監査はすべてのイベントに適用されます | [ネットワーク保護を有効にする](enable-network-protection.md) | [ネットワーク保護イベント](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| 監査は個々の軽減策に適用されます | [エクスプロイト保護を有効にする](enable-exploit-protection.md) | [エクスプロイト保護イベント](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)

## <a name="related-topics"></a>関連項目

* [エクスプロイトからデバイスを保護する](exploit-protection.md)
* [攻撃表面の縮小ルールを使用して攻撃表面を削減する](attack-surface-reduction.md)
* [ネットワークを保護する](network-protection.md)
* [重要なフォルダーを保護する](controlled-folders.md)
