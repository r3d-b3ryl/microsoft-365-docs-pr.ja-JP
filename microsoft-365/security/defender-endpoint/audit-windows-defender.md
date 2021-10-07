---
title: Microsoft Defender for Endpoint の機能が監査モードで動作する方法をテストする
description: 監査モードは、Microsoft Defender for Endpoint が有効になっている場合にデバイスを保護する方法を確認するのに役立ちます。
keywords: exploit guard, audit, auditing, mode, enabled, disabled, test, demo, evaluate, lab
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.topic: article
ms.technology: mde
ms.date: 09/22/2021
ms.collection: M365-security-compliance
ms.openlocfilehash: b261625215fa5f4f84daac7850f50569d8826cb6
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60174869"
---
# <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a>エンドポイント向け Microsoft Defender の攻撃表面の縮小をテストする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

組織のセキュリティ チームの一部として、監査モードで実行する攻撃表面の縮小機能を構成して、その動作を確認できます。 監査モードでは、次の機能を有効にできます。

- 攻撃面の減少ルール
- エクスプロイト保護
- ネットワーク保護
- 監査モードでのフォルダー アクセスの制御

監査モードでは、機能を有効にした場合に何が起こったかの記録を確認できます。

機能の動作をテストするときに監査モードを有効にできます。 これにより、一行のアプリが影響を受けずに行うのに役立ちます。 また、一定の期間に発生する疑わしいファイル変更の試行回数を確認できます。

この機能は、アプリ、スクリプト、またはファイルが変更されるのをブロックまたは防止できません。 ただし、イベント ログWindows機能が完全に有効になっている場合と同様にイベントが記録されます。 監査モードを使用すると、イベント ログを確認して、機能が有効になっている場合の影響を確認できます。

監査されたエントリを見つけるには、「Applications and Services Microsoft **Windows Windows Defender** \>  \>  \>  \> **します**。

Defender for Endpoint を使用して、特に攻撃表面の縮小ルールを調査するために、各イベントの詳細を取得します。 Defender for Endpoint コンソールを使用すると、アラートタイムラインと調査シナリオの一部として問題 [を調査できます](investigate-alerts.md)。

グループ ポリシー、PowerShell、および構成サービス プロバイダー (CSP) を使用して監査モードを有効にできます。

> [!TIP]
> また、テストグラウンドのWindows Defenderに[アクセスして](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)demo.wd.microsoft.com 機能を確認し、機能の動作を確認できます。

|監査オプション|監査モードを有効にする方法|イベントを表示する方法|
|---|---|---|
|監査はすべてのイベントに適用されます|[制御されたフォルダー アクセスを有効にする](enable-controlled-folders.md)|[フォルダー アクセスイベントの制御](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
|監査は個々のルールに適用されます|[攻撃面の減少ルールを有効にする](enable-attack-surface-reduction.md)|[攻撃表面の縮小ルール イベント](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
|監査はすべてのイベントに適用されます|[ネットワーク保護を有効にする](enable-network-protection.md)|[ネットワーク保護イベント](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
|監査は個々の軽減策に適用されます|[エクスプロイト保護を有効にする](enable-exploit-protection.md)|[エクスプロイト保護イベント](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)
