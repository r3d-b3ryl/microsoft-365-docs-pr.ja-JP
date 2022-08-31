---
title: Microsoft Defender for Endpointアーキテクチャの要件と主要な概念を確認する
description: Microsoft 365 DefenderのMicrosoft Defender for Endpointの技術図は、試用版ラボまたはパイロット環境を構築する前に、Microsoft 365 の ID を理解するのに役立ちます。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
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
- m365solution-scenario
- m365solution-evalutatemtp
- zerotrust-solution
- highpri
ms.topic: conceptual
ms.openlocfilehash: 5a446047168394fd8506f2aaed911ce3af284f10
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67467967"
---
# <a name="review-microsoft-defender-for-endpoint-architecture-requirements-and-key-concepts"></a>Microsoft Defender for Endpointアーキテクチャの要件と主要な概念を確認する

**適用対象:** Microsoft 365 Defender

この記事では、Microsoft Defender for Endpoint環境の評価を設定するプロセスについて説明します。

このプロセスの詳細については、 [概要に](eval-defender-endpoint-overview.md)関する記事を参照してください。

Microsoft Defender for Endpointを有効にする前に、アーキテクチャを理解し、要件を満たすことができることを確認してください。

## <a name="understand-the-architecture"></a>アーキテクチャを理解する

次の図は、Microsoft Defender for Endpointアーキテクチャと統合を示しています。 

:::image type="content" source="../../media/defender/m365-defender-endpoint-architecture.png" alt-text="Microsoft Defender for Office を Defender 評価環境に追加する手順" lightbox="../../media/defender/m365-defender-endpoint-architecture.png":::

次の表で、図について説明します。

コールアウト | 説明
:---|:---|
1 | デバイスは、サポートされている管理ツールの 1 つを介してオンボードされます。 
2 | オンボードデバイスは、Microsoft Defender for Endpoint信号データを提供し、応答します。
3 | マネージド デバイスは、Azure Active Directory に参加または登録されます。
4 | ドメインに参加している Windows デバイスは、Azure Active Directory Connect を使用して Azure Active Directory に同期されます。
5 | Microsoft Defender for Endpointアラート、調査、および応答は、Microsoft 365 Defenderで管理されます。

## <a name="understand-key-concepts"></a>主要な概念を理解する

次の表は、Microsoft Defender for Endpointを評価、構成、デプロイするときに理解するために重要な重要な概念を示しています。 

概念 | 説明 | 詳細情報
:---|:---|:---|
管理ポータル | Microsoft 365 Defenderポータルを使用して、潜在的な高度な永続的な脅威アクティビティまたはデータ侵害のアラートを監視し、対応を支援します。 | [Microsoft Defender for Endpoint ポータルの概要](/microsoft-365/security/defender-endpoint/portal-overview)
攻撃面の縮小 | 組織がサイバー脅威や攻撃に対して脆弱な場所を最小限に抑えることで、攻撃面を減らすことができます。 | [攻撃面の減少の概要](/microsoft-365/security/defender-endpoint/overview-attack-surface-reduction)
エンドポイントの検出と対応 | エンドポイントの検出と応答機能により、ほぼリアルタイムで実行可能な高度な攻撃検出が提供されます。 | [エンドポイントの検出機能と応答機能の概要](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)
ビヘイビアー ブロックとコンテインメント | 動作ブロック機能とコンテインメント機能は、脅威が実行を開始した場合でも、その動作とプロセス ツリーに基づいて、脅威を特定して停止するのに役立ちます。 | [動作ブロックと封じ込め](/microsoft-365/security/defender-endpoint/behavioral-blocking-containment)
自動調査と対応 | 自動調査では、セキュリティ アナリストが使用するプロセスに基づいてさまざまな検査アルゴリズムを使用し、アラートを調べ、侵害を解決するための直ちにアクションを実行するように設計されています。 | [自動調査を使用して脅威を調査および修復する](/microsoft-365/security/defender-endpoint/automated-investigations)
高度なハンティング | 高度なハンティングは、最大 30 日間の未加工データを探索できるクエリベースの脅威検出ツールです。これにより、ネットワーク内のイベントを事前に検査して脅威のインジケーターとエンティティを見つけることができます。 | [高度なハンティングの概要](/microsoft-365/security/defender-endpoint/advanced-hunting-overview)
脅威の分析 | 脅威分析は、最も関連性の高い脅威をカバーする、Microsoft の専門家のセキュリティ研究者からの一連のレポートです。 | [新しい脅威を追跡して対応する](/microsoft-365/security/defender-endpoint/threat-analytics)


Microsoft Defender for Endpointに含まれる機能の詳細については、「[Microsoft Defender for Endpointとは」](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)を参照してください。

## <a name="siem-integration"></a>SIEM 統合

Microsoft Defender for Endpointを Microsoft Sentinel と統合して、組織全体のセキュリティ イベントをより包括的に分析し、効果的かつ迅速な対応のためにプレイブックを構築できます。 

Microsoft Defender for Endpointは、他のセキュリティ情報およびイベント管理 (SIEM) ソリューションにも統合できます。 詳細については、「[Microsoft Defender for Endpointでの SIEM 統合の有効化](/microsoft-365/security/defender-endpoint/enable-siem-integration)」を参照してください。


## <a name="next-steps"></a>次の手順
[評価を有効にする](eval-defender-endpoint-enable-eval.md)

[Microsoft Defender for Endpointの評価](eval-defender-endpoint-overview.md)の概要に戻る

[評価とパイロットのMicrosoft 365 Defender](eval-overview.md)の概要に戻る
