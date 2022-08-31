---
title: Microsoft 365 Defenderをセキュリティ操作に統合する
description: Microsoft 365 Defenderをセキュリティ操作に統合する基本。
keywords: インシデント, アラート, 調査, 相関関係, 攻撃, デバイス, ユーザー, ID, ID, メールボックス, 電子メール, 365, Microsoft, m365, インシデント対応, サイバー攻撃, secops, セキュリティ操作, soc
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-m365dsecops
- m365solution-overview
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 2761d361c0bf1e4b8f709e668a0aa39c8e25a602
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67474800"
---
# <a name="integrating-microsoft-365-defender-into-your-security-operations"></a>Microsoft 365 Defenderをセキュリティ操作に統合する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

最新のセキュリティ オペレーション センター (SOC) は、セキュリティが組み込まれるように、デプロイ プロセスの前にセキュリティ プロセスを移動するという脅威防御戦略を採用するインテリジェンス主導の適応型組織です。 つまり、単一のセキュリティ アナリストに対する分離されたテクノロジとプロセスの従来の割り当ては、複数のソースからのデータの大幅な増加をサポートしなくなりました。 セキュリティ アナリストとエンジニアは、より包括的なアプローチを取り、さまざまなプラットフォームや規範間で共有された分析情報を使用して効果的なアクションを実行するよう求められます。

このため、Microsoft 365 Defender プラットフォームのデプロイと実装には、Microsoft 365 Defender サービス自体の日常的な運用とライフサイクル管理を最適化するために、SOC チームとの慎重な計画が必要になります。 このコンテンツでは、Microsoft 365 Defenderを、最新のセキュリティ操作の基礎となる新規または既存のユーザー、プロセス、テクノロジと運用化および統合する方法に関するいくつかの概念について説明します。

Microsoft 365 Defenderについてまだ理解していない場合は、次の記事を参照してください。

- [Microsoft 365 Defender の使用を開始する](get-started.md)
- [Microsoft 365 Defender を有効にする](m365d-enable.md)

組織が既にMicrosoft 365 Defenderのいくつかの側面を実装している場合、これらの記事は既存のアーキテクチャとプロセスを肯定するか、改善するのに役立ちます。

>[!Note]
>Microsoft のパートナーである Protiviti は、この記事のために情報や重要なフィードバックを提供してくれました。
>

## <a name="target-audience"></a>対象となる読者

このコンテンツは、次の目的で設計されています。

- DevOps および Security Operations (SecOps) チーム
- セキュリティ エンジニアリング チーム
- IT チーム
- CISO と CTO
- 赤、青、紫の Teams
- CSIRT &フォレンジック チーム
- Microsoft 365 管理者

## <a name="next-steps"></a>次の手順

SOC にMicrosoft 365 Defenderを統合するには、次の手順に従います。

- [手順 1.Microsoft 365 Defender操作の準備を計画する](integrate-microsoft-365-defender-secops-plan.md)
- [手順 2.ゼロ トラスト Framework を使用して SOC 統合準備性評価を実行する](integrate-microsoft-365-defender-secops-readiness.md)
- [手順 3.MICROSOFT 365 DEFENDERサービスの SOC カタログとの統合を計画する](integrate-microsoft-365-defender-secops-services.md)
- [手順 4.Microsoft 365 Defenderロール、責任、監視を定義する](integrate-microsoft-365-defender-secops-roles.md)
- [手順 5.ユース ケースの開発とテスト](integrate-microsoft-365-defender-secops-use-cases.md)
- [手順 6.SOC メンテナンス タスクを特定する](integrate-microsoft-365-defender-secops-tasks.md)



