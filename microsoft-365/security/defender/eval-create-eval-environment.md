---
title: サイバーセキュリティと XDR Microsoft 365 Defender評価環境を作成する
description: 評価する XDR に含まれるMicrosoft 365 Defenderを確認し、試用版ライセンスをアクティブ化して、Microsoft 365 Defender 試用版ラボまたはパイロット環境を作成します。 ここで XDR サイバーセキュリティの旅を開始し、そのテストを実稼働環境に持ち込む方法について学ぶ。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.topic: how-to
ms.technology: m365d
ms.openlocfilehash: d81d33a01802ebdf8ef0ea67a9ee74fc69b79384
ms.sourcegitcommit: 8423f47fce3905a48db9daefe69c21c841da43a0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2022
ms.locfileid: "63504736"
---
# <a name="step-1-create-the-microsoft-365-defender-evaluation-environment-for-greater-cyber-security"></a>手順 1. サイバーセキュリティを強化Microsoft 365 Defender評価環境を作成する

LYou は、このシリーズの残りの部分で配布Microsoft Defender XDRこのソリューションについて学び、構築することができます。

- [環境を作成する方法](eval-create-eval-environment.md)
- この Microsoft XDR の各テクノロジをセットアップまたは学習する
    - [Microsoft Defender for Identity](eval-defender-identity-overview.md)
    - [Microsoft Defender for Office](eval-defender-office-365-overview.md)
    - [Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)
    - [Microsoft Defender for Cloud Apps](eval-defender-mcas-overview.md)
- [この XDR を使用して調査および応答する方法](eval-defender-investigate-respond.md)
- [試用版環境を実稼働環境に昇格する](eval-defender-promote-to-production.md)
- [概要に戻る](eval-overview.md)

このシリーズの手順は、Microsoft 365 Defender XDR の背後にある概念の学習から構築、評価環境の実稼働化まで、エンドツーエンドで実行されます。

評価では、この次の手順を実行する 2 つの一般的な方法があります。 このシリーズでは、既に実稼働環境テナントMicrosoft 365想定し、E5 試用版ライセンスをアクティブ化して、現在の環境Microsoft 365 Defender評価 *します*。 インプレイス評価を使用すると、評価期間後にライセンスの購入に関するセキュリティ方法を保持できます。

2 つ目は[、評価Microsoft 365 Defenderラボ環境](setup-m365deval.md)をセットアップする方法です。 テスト中は、ビジネスからの実際のシグナルが多くない場合があります。

## <a name="you-will-need-to-activate-e5-trial-licenses-to-evaluate-microsoft-365-defender"></a>E5 試用版ライセンスをアクティブ化して、評価する必要Microsoft 365 Defender

1. 既存のテナント管理ポータルMicrosoft 365ログオンします。
2. ナビゲーション **メニューから [サービス** の購入] を選択します。
3. [ライセンス] セクションまで下Office 365し、[**ライセンス] の** 下の [詳細] Office 365 E5します。

   :::image type="content" source="../../media/mdo-eval/2_mdo-eval-license-details.png" alt-text="[Office 365] セクションには、クリックする [詳細] ボタンがあります。":::

4. [無料 **試用版の開始] リンクを** 選択します。

   :::image type="content" source="../../media/mdo-eval/3-m365-purchase-button.png" alt-text="[無料試用版の開始] をクリックします (料金は 35$ です)。":::

5. 要求を確認し、[今すぐ試 **す] ボタンを** クリックします。

   :::image type="content" source="../../media/mdo-eval/4_mdo-trial-order.png" alt-text="[チェックアウトして、注文を確認する] パネルに [今すぐ試す] ボタンがあります (25 人のユーザーに対して 1 か月Office 365 E5試用の場合)。":::

## <a name="go-to-the-next-step"></a>次の手順に進む

[Id の認証を有効にするMicrosoft 365を確認する](eval-defender-identity-overview.md)

または、[評価とパイロット] [の概要に戻Microsoft 365 Defender](eval-overview.md)