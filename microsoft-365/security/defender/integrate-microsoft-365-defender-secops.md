---
title: セキュリティMicrosoft 365 Defenderに統合する
description: セキュリティ操作にMicrosoft 365 Defenderの基本。
keywords: インシデント、アラート、調査、相関関係、攻撃、デバイス、ユーザー、ID、ID、メールボックス、メール、365、microsoft、m365、インシデント対応、サイバー攻撃、secops、セキュリティ操作、soc
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
- m365solution-m365dsecops
- m365solution-overview
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 5c88d6530fe8316f0297f716d51a28a64ede72f9
ms.sourcegitcommit: 07405a81513d1c63071a128b9d5070d3a3bfe1cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2021
ms.locfileid: "61121425"
---
# <a name="integrating-microsoft-365-defender-into-your-security-operations"></a>セキュリティMicrosoft 365 Defenderに統合する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

最新のセキュリティ 運用センター (SOC) は、セキュリティを組み込む前の展開プロセスでセキュリティ プロセスを移動する脅威防御戦略を取り入れた、インテリジェンス駆動型のアダプティブ組織です。 つまり、分離されたテクノロジとプロセスを単一のセキュリティ アナリストに割り当てている従来の割り当ては、複数のソースからのデータの大幅な増加をサポートしなくなりました。 セキュリティ アナリストとエンジニアは、より全体的なアプローチを取り、さまざまなプラットフォームや分野間で共有された洞察を使用して効果的なアクションを実行することを求めらされています。

このため、Microsoft 365 Defender プラットフォームの展開と実装では、Microsoft 365 Defender サービス自体の毎日の運用とライフサイクル管理を最適化するために、SOC チームと慎重に計画する必要があります。 このコンテンツでは、Microsoft 365 Defender を最新のセキュリティ操作の基礎となる新規または既存のユーザー、プロセス、およびテクノロジと運用および統合する方法に関するいくつかの概念について説明します。

ユーザー設定に関する詳しいMicrosoft 365 Defender、次の記事を参照してください。

- [Microsoft 365 Defender の使用を開始する](get-started.md)
- [Microsoft 365 Defender を有効にする](m365d-enable.md)

組織が既存のアーキテクチャとプロセスをMicrosoft 365 Defender場合、これらの記事は既存のアーキテクチャとプロセスを肯定または改善できます。

>[!Note]
>Microsoft のパートナーである Protiviti は、この記事のために情報や重要なフィードバックを提供してくれました。
>

## <a name="target-audience"></a>対象となる読者

このコンテンツは、次の目的で設計されています。

- DevOpsおよびセキュリティ操作 (SecOps) チーム
- セキュリティ エンジニアリング チーム
- IT チーム
- CISOs と COS
- 赤、青、紫のTeams
- CSIRT &のチーム
- Microsoft 365管理者

## <a name="next-steps"></a>次の手順

次の手順を使用して、Microsoft 365 Defenderを SOC に統合します。

- [手順 1.運用の準備Microsoft 365 Defender計画する](integrate-microsoft-365-defender-secops-plan.md)
- [手順 2.ゼロトラスト フレームワークを使用して SOC 統合準備評価を実行する](integrate-microsoft-365-defender-secops-readiness.md)
- [手順 3.サービスの SOC Microsoft 365 Defenderとの統合を計画する](integrate-microsoft-365-defender-secops-services.md)
- [手順 4.役割Microsoft 365 Defender監督の定義](integrate-microsoft-365-defender-secops-roles.md)
- [手順 5.使用例の開発とテスト](integrate-microsoft-365-defender-secops-use-cases.md)
- [手順 6.SOC のメンテナンス タスクを特定する](integrate-microsoft-365-defender-secops-tasks.md)



