---
title: Microsoft Defender for Endpoint アーキテクチャの要件と主な概念を確認する
description: テスト ラボまたはパイロット環境を構築する前Microsoft 365 Defenderの Microsoft Defender for Endpoint の技術図は、Microsoft 365の ID を理解するのに役立ちます。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
ms.date: 07/09/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: e2cb2f915726289474826a3b4aa41da847152212
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60154544"
---
# <a name="review-microsoft-defender-for-endpoint-architecture-requirements-and-key-concepts"></a>Microsoft Defender for Endpoint アーキテクチャの要件と主な概念を確認する

**適用対象: Microsoft 365 Defender**

この記事では、Microsoft Defender for Endpoint 環境の評価をセットアップするプロセスについて説明します。

このプロセスの詳細については、「概要」の記事を [参照してください](eval-defender-endpoint-overview.md)。

Microsoft Defender for Endpoint を有効にする前に、アーキテクチャを理解し、要件を満たしていることを確認してください。

## <a name="understand-the-architecture"></a>アーキテクチャを理解する

次の図は、Microsoft Defender for Endpoint アーキテクチャと統合を示しています。 

![Defender 評価環境に Microsoft Defender を追加Office手順を実行します。](../../media/defender/m365-defender-endpoint-architecture.png)

次の表に、図を示します。

コールアウト | 説明
:---|:---|
1 | デバイスは、サポートされている管理ツールのいずれかを介してオンボードされます。 
2 | ボード上のデバイスは、Microsoft Defender for Endpoint シグナル データを提供して応答します。
3 | 管理対象デバイスは、デバイスに参加または登録Azure Active Directory。
4  | ドメインに参加しているWindowsデバイスは、デバイスを使用Azure Active DirectoryにAzure Active Directory Connect。
5 | Microsoft Defender for Endpoint のアラート、調査、および応答は、Microsoft 365 Defender。

## <a name="understand-key-concepts"></a>主要な概念を理解する

次の表に、Microsoft Defender for Endpoint の評価、構成、展開を行う際に重要な重要な概念を示します。 

概念 | 説明 | 詳細情報
:---|:---|:---|
管理ポータル | Microsoft 365 Defender、高度な永続的な脅威アクティビティやデータ侵害の可能性に関するアラートの監視と対応を支援するポータルを提供します。 | [Microsoft Defender for Endpoint ポータルの概要](/microsoft-365/security/defender-endpoint/portal-overview)
攻撃表面の縮小 | 組織がサイバー脅威や攻撃に対して脆弱な場所を最小限に抑えることによって、攻撃の表面を減らすのに役立ちます。 | [攻撃面の減少の概要](/microsoft-365/security/defender-endpoint/overview-attack-surface-reduction)
エンドポイントの検出と応答 | エンドポイントの検出および応答機能は、ほぼリアルタイムでアクション可能な高度な攻撃検出を提供します。 | [エンドポイントの検出および応答機能の概要](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)
動作のブロックと格納 | 動作のブロックと格納機能は、脅威の実行が開始された場合でも、その動作とプロセス ツリーに基づいて、脅威を特定して停止するのに役立ちます。 | [動作ブロックと封じ込め](/microsoft-365/security/defender-endpoint/behavioral-blocking-containment)
自動調査と対応 | 自動調査では、セキュリティ アナリストが使用するプロセスに基づいてさまざまな検査アルゴリズムを使用し、アラートを調べ、侵害を解決するために直ちに対応するように設計されています。 | [自動調査を使用して脅威を調査および修復する](/microsoft-365/security/defender-endpoint/automated-investigations)
高度なハンティング | 高度な検索はクエリベースの脅威ハンティング ツールで、最大 30 日間の生データを調査して、ネットワーク内のイベントを積極的に検査して脅威インジケーターとエンティティを特定できます。 | [高度な検索の概要](/microsoft-365/security/defender-endpoint/advanced-hunting-overview)
脅威の分析 | 脅威分析は、最も関連性の高い脅威をカバーする Microsoft の専門家のセキュリティ研究者からの一連のレポートです。 | [新しい脅威を追跡して対応する](/microsoft-365/security/defender-endpoint/threat-analytics)


Microsoft Defender for Endpoint に含まれる機能の詳細については、「What [is Microsoft Defender for Endpoint」を参照してください](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)。

## <a name="siem-integration"></a>SIEM 統合

Microsoft Defender for Endpoint と Azure Sentinel を統合して、組織全体のセキュリティ イベントをより包括的に分析し、効果的かつ迅速な対応を行うプレイブックを構築できます。 

Microsoft Defender for Endpoint は、他のセキュリティ情報およびイベント管理 (SIEM) ソリューションにも統合できます。 詳細については [、「Enable SIEM integration in Microsoft Defender for Endpoint」を参照してください](/microsoft-365/security/defender-endpoint/enable-siem-integration)。


## <a name="next-steps"></a>次の手順
[評価を有効にする](eval-defender-endpoint-enable-eval.md)

エンドポイントの Microsoft [Defender の評価の概要に戻る](eval-defender-endpoint-overview.md)

[評価とパイロット][の概要に戻Microsoft 365 Defender](eval-overview.md)
