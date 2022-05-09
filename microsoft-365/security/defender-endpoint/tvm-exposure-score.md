---
title: 脅威と脆弱性の管理における露出スコア
description: 脅威と脆弱性の管理公開スコアは、組織がサイバーセキュリティの脅威に対してどれほど脆弱であるかを示します。
keywords: 露出スコア、Microsoft Defender for Endpoint露出スコア、Microsoft Defender for Endpoint tvm 露出スコア、組織の露出スコア、tvm 組織の露出スコア、脅威と脆弱性の管理、Microsoft Defender for Endpoint
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: f65b48f37d1cf141611af075e55328226db6c6bd
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64471585"
---
# <a name="exposure-score---threat-and-vulnerability-management"></a>露出スコア - 脅威と脆弱性の管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [脅威と脆弱性の管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)

露出スコアは、Microsoft 365 Defender ポータルの [[脅威と脆弱性の管理] ダッシュボード](tvm-dashboard-insights.md)に表示されます。 これは、組織がサイバーセキュリティの脅威に対してどれほど脆弱であるかを反映しています。 露出スコアが低いということは、デバイスが悪用の影響を受けにくいという意味です。

- 組織内のセキュリティの状態に関する高レベルの取り組みをすばやく理解し、特定します。
- 現在の状態を改善するために調査またはアクションが必要な領域を検出して対応します。
- セキュリティの取り組みの影響について、ピアや管理と通信します。

カードを使用すると、時間の経過に伴う露出スコアの傾向を高いレベルで確認できます。 グラフの急増は、サイバーセキュリティの脅威にさらされている可能性が高いことを視覚的に示し、さらに調査することができます。

:::image type="content" source="images/tvm_exp_score.png" alt-text="露出スコアカード" lightbox="images/tvm_exp_score.png":::

## <a name="how-it-works"></a>メカニズム

露出スコアは次のレベルに分類されます。

- 0-29: 露出スコアが低い
- 30-69: 中程度の露出スコア
- 70-100: 高い露出スコア

優先順位付けされた [セキュリティに](tvm-security-recommendation.md) 関する推奨事項に基づいて問題を修復し、露出スコアを減らすことができます。 各ソフトウェアには、組織に対するリスクに基づいて推奨事項に変換され、優先順位付けされる弱点があります。

## <a name="reduce-your-threat-and-vulnerability-exposure"></a>脅威と脆弱性の露出を減らす

[セキュリティに関する推奨事項](tvm-security-recommendation.md)を修復することで、脅威と脆弱性の影響を軽減します。 脅威と脆弱性の管理 ダッシュボードで表示できる、最高のセキュリティ推奨事項を修復することで、露出スコアに最も影響を与[えます](tvm-dashboard-insights.md)。

## <a name="related-topics"></a>関連項目

- [脅威と脆弱性の管理の概要](next-gen-threat-and-vuln-mgt.md)
- [デバイス向けの Microsoft セキュア スコア](tvm-microsoft-secure-score-devices.md)
- [セキュリティに関する推奨事項](tvm-security-recommendation.md)
- [イベントのタイムライン](threat-and-vuln-mgt-event-timeline.md)
