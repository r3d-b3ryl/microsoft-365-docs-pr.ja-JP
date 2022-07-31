---
title: Microsoft Defender for Office 365データリテンション期間
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.technology: mdo
ms.localizationpriority: medium
search.appverid: ''
ms.collection:
- M365-security-compliance
ms.custom: ''
description: Microsoft Defender for Office 365データ保持情報Threat Explorer/Real-Time検出
ms.openlocfilehash: 9cab47358890b47796a42e48b690818d65e20527
ms.sourcegitcommit: 38a18b0195d99222c2c6da0c80838d24b5f66b97
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2022
ms.locfileid: "66994185"
---
# <a name="data-retention-information-for-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365のデータ保持情報

既定では、異なる機能間のデータは最大 30 日間保持されます。 ただし、一部の機能では、ポリシーに基づいて保持期間を指定できます。 機能ごとに異なる保有期間については、次の表を参照してください。

> [!NOTE]
> Microsoft Defender for Office 365 には、2 種類のプランがあります。 "リアルタイム検出" を使用している場合は **プラン 1** で、脅威エクスプローラーを使用している場合は **プラン 2** が表示されます。 このプランは、表示されるツールに影響しますので、お客様のプランについて理解していることをご確認ください。

## <a name="defender-for-office-365-plan-1"></a>Microsoft Defender for Office 365 プラン 1

|機能|保有期間|
|---|---|
|アラート メタデータの詳細 (Microsoft Defender for Office アラート) | 90 日間 |
|エンティティ メタデータの詳細 (電子メール) | 30 日間 |
|アクティビティ アラートの詳細 (監査ログ) | 7 日間 |
|[メール エンティティ] ページ | 30 日間 |
|検疫する | 30 日 (最大 30 日間まで構成可能) |
|レポート | 90 日間 (集計されたすべてのデータの場合) <br>30 日間 (以下を除くすべての詳細情報) <br> 10 日間 (脅威保護状態レポートの詳細とスプーフィング メール レポートの詳細の場合) <br> 7 日間 (URL 保護レポートの詳細) <br>
|提出物 | 30 日間 |
|脅威エクスプローラー/Real-Time検出 | 30 日間 |

## <a name="defender-for-office-365-plan-2"></a>Defender for Office 365 プラン 2

Defender for Office 365 プラン 1 の機能に加えて、次の機能も含まれます。

|機能|保有期間|
|---|---|
|アクション センター | 180 日、30 日 (Office アクション センター)   |
|高度なハンティング | 30 日間 |
|AIR (自動調査と応答) | 60 日間 (調査メタデータの場合)<br> 30 日間 (電子メール メタデータの場合)  |
|攻撃シミュレーション データ | 18 か月 |
|キャンペーン | 30 日間 |
|インシデント | 30 日間|
|修復 | 30 日間 |
|脅威の分析 | 30 日間 |
|脅威トラッカー | 30 日間 |
