---
title: Microsoft 365 Defender評価環境を作成してサイバー セキュリティと XDR を強化する
description: 評価するMicrosoft 365 Defender XDR に含まれる内容を確認し、試用版ライセンスをアクティブ化して、Microsoft 365 Defender試用版ラボまたはパイロット環境の詳細を確認します。 ここで XDR のサイバー セキュリティ体験を開始し、そのテストを運用環境に移行する方法について説明します。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 05/19/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
- zerotrust-solution
- highpri
ms.topic: how-to
ms.openlocfilehash: 31254fac4b56da65469fac56320440bfd0e487c3
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67470555"
---
# <a name="step-1-create-the-microsoft-365-defender-evaluation-environment-for-greater-cyber-security"></a>手順 1. Microsoft 365 Defender評価環境を作成してサイバーセキュリティを強化する

このMicrosoft Defender XDR ソリューションについては、このシリーズの残りの部分を通じて配布される手順で学習し、構築できます。

- [環境を作成する方法](eval-create-eval-environment.md)
- この Microsoft XDR の各テクノロジを設定または学習する
    - [Microsoft Defender for Identity](eval-defender-identity-overview.md)
    - [Microsoft Defender for Office](eval-defender-office-365-overview.md)
    - [Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)
    - [Microsoft Defender for Cloud Apps](eval-defender-mcas-overview.md)
- [この XDR を使用して調査して応答する方法](eval-defender-investigate-respond.md)
- [試用版環境を運用環境に昇格させる](eval-defender-promote-to-production.md)
- [概要に戻る](eval-overview.md)

このシリーズの手順は、Microsoft 365 Defender XDR の背後にある概念の学習から構築、評価環境の運用まで、エンドツーエンドで実行されます。

この次の評価手順には、2 つの一般的な方法があります。 このシリーズは、運用 Microsoft 365 テナントが既にあると想定しており、E5 試用版ライセンスをアクティブ化して *、現在の環境* でMicrosoft 365 Defenderを評価します。 インプレース評価を使用すると、評価期間の後にライセンスを購入したセキュリティ方法を保持できます。

2 つ目は、評価を目的として[Microsoft 365 Defender試用版ラボ環境を設定](setup-m365deval.md)することです。 テスト中は、ビジネスからの実際のシグナルが多くない可能性があることに注意してください。

## <a name="you-will-need-to-activate-e5-trial-licenses-to-evaluate-microsoft-365-defender"></a>Microsoft 365 Defenderを評価するには、E5 試用版ライセンスをアクティブ化する必要があります。

1. 既存の Microsoft 365 テナント管理ポータルにログオンします。
2. ナビゲーション メニューから [ **サービスの購入** ] を選択します。
3. [Office 365] セクションまで下にスクロールし、ライセンスの下にある [**詳細**] ボタンOffice 365 E5選択します。

   :::image type="content" source="../../media/mdo-eval/2_mdo-eval-license-details.png" alt-text="Microsoft 365 Defender ポータルの [詳細] ボタン" lightbox="../../media/mdo-eval/2_mdo-eval-license-details.png":::

4. [ **無料試用版** の開始] リンクを選択します。

   :::image type="content" source="../../media/mdo-eval/3-m365-purchase-button.png" alt-text="Microsoft 365 Defender ポータルの [無料試用版の開始] ボタン" lightbox="../../media/mdo-eval/3-m365-purchase-button.png":::

5. 要求を確認し、[ **今すぐ試す** ] ボタンをクリックします。

   :::image type="content" source="../../media/mdo-eval/4_mdo-trial-order.png" alt-text="Microsoft 365 Defender ポータルの [今すぐ試す] ボタン" lightbox="../../media/mdo-eval/4_mdo-trial-order.png":::

## <a name="go-to-the-next-step"></a>次の手順に進む

[Microsoft 365 for Identity を有効にする方法について説明します](eval-defender-identity-overview.md)

または、[評価とパイロットMicrosoft 365 Defender](eval-overview.md)の概要に戻ります。
