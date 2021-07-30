---
title: 手順 1. 運用の準備Microsoft 365 Defender計画する
description: セキュリティ操作に統合する際Microsoft 365 Defender準備をMicrosoft 365 Defenderの基本。
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 3e8bf320bd25dacb3312605d5bc6428ad15210fb
ms.sourcegitcommit: 3576c2fee77962b516236cb67dd3df847d61c527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2021
ms.locfileid: "53622386"
---
# <a name="step-1-plan-for-microsoft-365-defender-operations-readiness"></a>手順 1. 運用の準備Microsoft 365 Defender計画する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

セキュリティ操作の現在の成熟度が何であれ、セキュリティ 運用センター (SOC) に合わせて調整することが重要です。 すべての組織に適合するモデルは 1 つはありませんが、他のモデルよりも一般的な側面があります。 

次のセクションでは、SOC のコア関数について説明します。

## <a name="provide-situational-awareness-of-modern-threats"></a>最新の脅威に対する状況認識を提供する

SOC チームは、組織と一緒に対策と対応を確立できるよう、新しい脅威と着信脅威を準備し、検出します。 SOC チームには、最新の攻撃方法と手法で高度なトレーニングを受け、脅威アクターを理解する担当者が必要です。 サイバー キル チェーンや[MITRE ATT](https://attack.mitre.org/)&CK フレームワークのような共有脅威インテリジェンスとフレームワークは、脅威アナリストや脅威ハンターのスタッフに力を与える可能性があります。 [](https://www.microsoft.com/security/blog/2016/11/28/disrupting-the-kill-chain/)

## <a name="provide-first-second-and-potentially-third-level-responses-to-cyber-incidents-and-events"></a>サイバー インシデントやイベントに対して、第 1、第 2、第 3 レベルの対応を提供する

SOC は、セキュリティ イベントやインシデントに対する防御の最前線です。 イベント、脅威、攻撃、ポリシー違反、または監査の検出によってアラートまたはアクションの呼び出しがトリガーされると、SOC チームは評価をトリアージし、調査のためにそれを含めるか、またはエスカレートします。 したがって、SOC の最初の回線レスポンダーは、セキュリティ イベントとインジケーターに関する幅広い技術的知識を持っている必要があります。

## <a name="centralize-monitoring-and-logging-of-your-organizations-security-sources"></a>組織のセキュリティ ソースの監視とログの一元化 

通常、SOC チームの主な機能は、ファイアウォール、侵入防止システム、データ損失防止システム、脅威と脆弱性の管理 システム、ID システムなど、すべてのセキュリティ デバイスが正しく機能し、監視されていることを確認することです。 SOC チームは、ID、DevOps、クラウド、アプリケーション、データ サイエンス、その他のビジネス チームなど、より広範なネットワーク運用と組み合って、セキュリティ情報の分析を一元化してセキュリティで保護します。 さらに、SOC チームは、データのログを使用できる読み取り可能な形式で管理します。この場合は、異なる形式の解析と正規化が含まれます。

## <a name="establish-red-blue-and-purple-team-operational-readiness"></a>赤、青、紫のチームの運用準備を確立する

すべての SOC チームは、サイバー インシデントに対応する準備をテストする必要があります。 テストは、IT、セキュリティ、およびビジネス レベルでさまざまな個人とテーブルトップやプラクティス実行などのトレーニング演習を使用して実行できます。 個々のトレーニング演習チームは、代表的な役割に基づいて作成され、ディフェンダー (Blue Team)、攻撃者 (レッド チーム) の役割を果たすか、または演習中に明らかにされた長所と短所を通じて青と赤の両方のチームの方法とテクニックを向上させる観察者として (Purple Team) 役割を果たしています。

## <a name="next-step"></a>次の手順

[手順 2.ゼロトラスト フレームワークを使用して SOC 統合準備評価を実行する](integrate-microsoft-365-defender-secops-readiness.md)


