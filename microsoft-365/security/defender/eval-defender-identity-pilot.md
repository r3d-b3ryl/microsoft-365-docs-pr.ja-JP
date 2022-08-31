---
title: パイロット Microsoft Defender for Identity
description: パイロット Microsoft Defender for Identity、ベンチマークの設定、偵察、侵害された資格情報、横移動、ドメイン支配、流出アラートに関するチュートリアルを行います。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
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
ms.openlocfilehash: b6cf54408fff8139f1cd06a303f91c9785cca98a
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67481286"
---
# <a name="pilot-microsoft-defender-for-identity"></a>パイロット Microsoft Defender for Identity


**適用対象:**
- Microsoft 365 Defender

この記事は、Microsoft Defender for Identityの評価環境を設定する手順 [3/3](eval-defender-identity-overview.md) です。 このプロセスの詳細については、 [概要に](eval-defender-identity-overview.md)関する記事を参照してください。

Microsoft Defender for IDENTITY のパイロットをセットアップして構成するには、次の手順に従います。 推奨事項には、パイロット グループの設定は含まれていないことに注意してください。 ベスト プラクティスは、先に進み、Active Directory Domain Services (AD DS) と Active Directory フェデレーション サービス (AD FS) を実行しているすべてのサーバーにセンサーをインストールすることです。

:::image type="content" source="../../media/defender/m365-defender-identity-pilot-steps.png" alt-text="Microsoft Defender 評価環境でMicrosoft Defender for Identityをパイロットするための手順" lightbox="../../media/defender/m365-defender-identity-pilot-steps.png":::

次の表では、図の手順について説明します。

- [手順 1: ID 環境のベンチマーク推奨事項を構成する](#step-1-configure-benchmark-recommendations-for-your-identity-environment)
- [手順 2: 機能を試す - さまざまな攻撃の種類を特定して修復するためのチュートリアルを見る ](#step-2-try-out-capabilities--walk-through-tutorials-for-identifying-and-remediating-different-attack-types)

## <a name="step-1-configure-benchmark-recommendations-for-your-identity-environment"></a>手順 1。 ID 環境のベンチマークの推奨事項を構成する

Microsoft では、Microsoft Cloud サービスを使用しているお客様に対してセキュリティ ベンチマークに関する推奨事項を提供しています。 [Azure Security Benchmark](/security/benchmark/azure/overview) (ASB) には、Azure 上のワークロード、データ、サービスのセキュリティを向上させるための規範的なベスト プラクティスと推奨事項が用意されています。

これらのベンチマークの推奨事項には、[Microsoft Defender for Identityの Azure セキュリティ ベースライン](/security/benchmark/azure/baselines/defender-for-identity-security-baseline)が含まれます。 これらの推奨事項を実装するには、計画と実装に時間がかかる場合があります。 これにより ID 環境のセキュリティが大幅に向上しますが、Microsoft Defender for Identityの評価と実装を継続することを妨げるべきではありません。 これらは、ご自分の認識のためにここに用意されています。

## <a name="step-2-try-out-capabilities--walk-through-tutorials-for-identifying-and-remediating-different-attack-types"></a>手順 2。 機能を試す - さまざまな攻撃の種類を特定して修復するためのチュートリアルを見る

Microsoft Defender for Identityドキュメントには、さまざまな攻撃の種類を特定して修復するプロセスを説明する一連のチュートリアルが含まれています。

Defender for Identity のチュートリアルを試す:
- [偵察アラート](/defender-for-identity/reconnaissance-alerts)
- [侵害された資格情報アラート](/defender-for-identity/compromised-credentials-alerts)
- [横移動アラート](/defender-for-identity/lateral-movement-alerts)
- [ドメイン支配アラート](/defender-for-identity/domain-dominance-alerts)
- [流出アラート](/defender-for-identity/exfiltration-alerts)
- [ユーザーを調査する](/defender-for-identity/investigate-a-user)
- [コンピューターを調査する](/defender-for-identity/investigate-a-computer)
- [横方向の移動パスを調査する](/defender-for-identity/investigate-lateral-movement-path)
- [エンティティを調査する](/defender-for-identity/investigate-entity)

## <a name="next-steps"></a>次の手順

[Microsoft Defender for Office 365 を評価する](eval-defender-office-365-overview.md)

[Microsoft Defender for Office 365の評価](eval-defender-office-365-overview.md)の概要に戻る

[評価とパイロットのMicrosoft 365 Defender](eval-overview.md)の概要に戻る