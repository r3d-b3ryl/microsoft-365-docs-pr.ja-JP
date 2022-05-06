---
title: 手順 1. Microsoft 365 Defender操作の準備を計画する
description: Microsoft 365 Defenderをセキュリティ操作に統合する際のMicrosoft 365 Defender操作準備の計画の基本。
keywords: インシデント, アラート, 調査, 相関関係, 攻撃, デバイス, ユーザー, ID, ID, メールボックス, 電子メール, 365, Microsoft, m365, インシデント対応, サイバー攻撃, secops, セキュリティ操作, soc
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 8c69e92390e6ed6515be6f399703124ece99cc39
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2022
ms.locfileid: "64664020"
---
# <a name="step-1-plan-for-microsoft-365-defender-operations-readiness"></a>手順 1. Microsoft 365 Defender操作の準備を計画する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

セキュリティ運用の現在の成熟度にかかわらず、セキュリティ オペレーション センター (SOC) に合わせることが重要です。 すべての組織に適合する単一のモデルはありませんが、他の組織よりも一般的な側面があります。

以降のセクションでは、SOC のコア関数について説明します。

## <a name="provide-situational-awareness-of-modern-threats"></a>現代の脅威に対する状況認識を提供する

SOC チームは、組織と連携して対策と対応を確立できるように、新しい脅威と受信する脅威の準備と捜索を行います。 SOC チームには、最新の攻撃方法と手法に関する高度なトレーニングを受け、脅威のアクターを理解する担当者が必要です。 [サイバー キル チェーン](https://www.microsoft.com/security/blog/2016/11/28/disrupting-the-kill-chain/)や [MITRE ATT&CK フレームワーク](https://attack.mitre.org/)などの共有脅威インテリジェンスとフレームワークを使用すると、脅威アナリストや脅威の調査担当者のスタッフを強化できます。

## <a name="provide-first-second-and-potentially-third-level-responses-to-cyber-incidents-and-events"></a>サイバー インシデントやイベントに対する第 1、第 2、および潜在的に第 3 レベルの対応を提供する

SOC は、セキュリティ イベントやインシデントに対する防御の最前線です。 イベント、脅威、攻撃、ポリシー違反、または監査の結果がアラートまたはアクションの呼び出しをトリガーすると、SOC チームは評価を行ってトリアージして含めるか、調査のためにエスカレーションします。 そのため、SOC の最初の行レスポンダーは、セキュリティ イベントとインジケーターに関する広範な技術的知識を持っている必要があります。

## <a name="centralize-monitoring-and-logging-of-your-organizations-security-sources"></a>組織のセキュリティ ソースの監視とログ記録を一元化する

通常、SOC チームの中核となる機能は、ファイアウォール、侵入防止システム、データ損失防止システム、脅威と脆弱性の管理 システム、ID システムなど、すべてのセキュリティ デバイスが正しく機能し、監視されていることを確認することです。 SOC チームは、ID、DevOps、クラウド、アプリケーション、データ サイエンス、その他のビジネス チームなどの広範なネットワーク操作と連携して、セキュリティ情報の分析が一元化され、セキュリティで保護されるようにします。 さらに、SOC チームは、さまざまな形式の解析と正規化を含む、使用可能で読み取り可能な形式でデータのログを管理する役割を担います。

## <a name="establish-red-blue-and-purple-team-operational-readiness"></a>赤、青、紫のチームの運用準備を確立する

すべての SOC チームは、サイバー インシデントに対応する準備をテストする必要があります。 テストは、IT、セキュリティ、ビジネス レベルのさまざまな個人とのテーブルトップや演習実行などのトレーニング演習を通じて行うことができます。 個々のトレーニング演習チームは、代表的な役割に基づいて作成され、防御者 (ブルー チーム)、攻撃者 (赤いチーム) の役割を果たしているか、または練習中に明らかにされた長所と短所を通じて青と赤の両方のチームの方法とテクニックを向上させようとしているオブザーバーとして (Purple Team)。

## <a name="next-step"></a>次の手順

[手順 2.ゼロ トラスト Framework を使用して SOC 統合準備性評価を実行する](integrate-microsoft-365-defender-secops-readiness.md)
