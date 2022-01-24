---
title: 実稼働環境で Microsoft Defender の評価Office 365を有効にする
description: Microsoft Defender をライセンス認証Office 365評価を行い、試用版ライセンス、MX レコード処理、&ドメインと受信接続の監査を行います。
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
ms.date: 07/01/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: how-to
ms.technology: m365d
ms.openlocfilehash: 4d2f77b41dccd5620b96d816869d7d7b6458a798
ms.sourcegitcommit: 6f3bc00a5cf25c48c61eb3835ac069e9f41dc4db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2022
ms.locfileid: "62172177"
---
# <a name="enable-the-evaluation-environment"></a>評価環境を有効にする

**適用対象:**
- Microsoft 365 Defender

この記事は、Microsoft Defender の評価環境を設定するプロセスの手順[2/3](eval-defender-office-365-overview.md) Office 365。 このプロセスの詳細については、「概要」の記事を [参照してください](eval-defender-office-365-overview.md)。

次の手順を使用して、Microsoft Defender の評価を有効にOffice 365。

![Microsoft Defender 評価環境で Microsoft Defender Office 365を有効にする手順。](../../media/defender/m365-defender-office-eval-enable-steps.png)

- [手順 1: 試用版ライセンスをアクティブ化する](#step-1-activate-trial-licenses)
- [手順 2: パブリック MX レコードの監査と確認](#step-2-audit-and-verify-the-public-mx-record)
- [手順 3: 承認されたドメインを監査する](#step-3-audit-accepted-domains)
- [手順 4: 受信コネクタを監査する](#step-4-audit-inbound-connectors)
- [手順 5: 評価をアクティブ化する](#step-5-activate-the-evaluation)

## <a name="step-1-activate-trial-licenses"></a>手順 1: 試用版ライセンスをアクティブ化する

既存の Microsoft Defender にログオンして、Office 365管理ポータルにログオンします。

1. 管理ポータルに移動します。
2. クイック 起動から [サービスの購入] を選択します。

   :::image type="content" source="../../media/mdo-eval/1_m365-purchase-services.png" alt-text="[サービスの購入] をクリックします。このページのナビゲーション ウィンドウOffice 365。":::

3. 下にスクロールして 、[Add-On] セクション (または "Defender") を検索して、Microsoft Defender のプランをOffice 365します。
4. 評価するプランの横にある [詳細] をクリックします。

   :::image type="content" source="../../media/mdo-eval/2_mdo-eval-license-details.png" alt-text="[詳細] ボタンをクリックし、次へをクリックします。":::

5. [無料試用版 *の開始] リンクをクリック* します。

   :::image type="content" source="../../media/mdo-eval/3-m365-purchase-button.png" alt-text="このパネルの [無料試用版の開始 *ハイパーリンク*] をクリックします。":::

6. 要求を確認し、[今すぐ試 *す] ボタンをクリック* します。

   :::image type="content" source="../../media/mdo-eval/4_mdo-trial-order.png" alt-text="[今すぐ試す] *ボタン *をクリックします。":::

## <a name="step-2-audit-and-verify-the-public-mx-record"></a>手順 2: パブリック MX レコードの監査と確認

Microsoft Defender for Office 365を効果的に評価するには、テナントに関連付けられた Exchange Online Protection (EOP) インスタンスを介して受信外部メールを中継することが重要です。

1. M365 管理ポータルにログオンし、[ドメイン] 設定を展開します。
2. 確認済みのメール ドメインを選択し、[DNS の管理] をクリックします。
3. 生成され、EOP テナントに割り当てられた MX レコードをメモします。
4. 外部 (パブリック) DNS ゾーンにアクセスし、メール ドメインに関連付けられているプライマリ MX レコードを確認します。
    - *パブリック MX レコードが現在* 割り当てられている EOP アドレス (tenant-com.mail.protection.outlook.com など) と一致する場合は、それ以上のルーティング変更は必要ありません。
    - パブリック MX レコードが現在サード パーティまたはオンプレミスの SMTP ゲートウェイに解決されている場合は、追加のルーティング構成が必要になる場合があります。
    - パブリック MX レコードが現在オンプレミスのレコードに解決されているExchange、一部の受信者メールボックスがまだ EXO に移行されていないハイブリッド モデルに存在する可能性があります。

## <a name="step-3-audit-accepted-domains"></a>手順 3: 承認されたドメインを監査する

1. 管理者ポータルにログオンExchange Online[メール] を選択Flowし、[承諾されたドメイン] をクリックします。
2. テナントで追加および検証された承認されたドメインの一覧から、プライマリ メール ドメインのドメインの種類をメモします。
    - ドメインの種類が [権限] に設定されている場合は、組織のすべての受信者メールボックスが現在、Exchange Online。
    - ドメインの種類が Internal ***Relay*** に設定されている場合、一部の受信者メールボックスがまだオンプレミスに存在するハイブリッド モデルに存在する可能性があります。

## <a name="step-4-audit-inbound-connectors"></a>手順 4: 受信コネクタを監査する

1. [管理者ポータル] Exchange Onlineログオンし、[メール] Flowをクリックし、[コネクタ] をクリックします。
2. 構成済みのコネクタの一覧から、パートナー組織からのエントリをメモし、サード パーティの SMTP ゲートウェイに関連付ける可能性があります。
3. 構成済みのコネクタの一覧から、ハイブリッド シナリオに残っている可能性がある組織のメール サーバーからというラベルが付いたエントリをメモします。

## <a name="step-5-activate-the-evaluation"></a>手順 5: 評価をアクティブ化する

この手順を使用して、Microsoft Defender をアクティブ化し、Office 365評価をMicrosoft 365 Defenderします。

1. ポータルにアクセスできるアカウントを使用してテナントにログオンMicrosoft 365 Defenderします。
2. 管理者向け Microsoft Defender の既定のインターフェイスMicrosoft 365 Defender **ポータル** にする (推奨) Office 365選択します。

   :::image type="content" source="../../media/mdo-eval/1_mdo-eval-activate-eval.png" alt-text="[設定を有効にする] ボタンをクリックして、管理用に一元管理Microsoft 365 Defenderを使用します。":::

3. ナビゲーション メニューから、[メールとコラボレーション] の **下&ポリシーと** ルール *&選択します*。

   :::image type="content" source="../../media/mdo-eval/2_mdo-eval-activate-eval.png" alt-text="[ポリシーとルール] を&する [メール と共同作業] &します。クリックします。":::

4. [ポリシー の *設定] &ダッシュボードで* 、[脅威 **ポリシー] をクリックします**。

   :::image type="content" source="../../media/mdo-eval/3_mdo-eval-activate-eval.png" alt-text="[ポリシーとルール] &の図と、脅威ポリシーを示す矢印を示します。次にクリックします。":::

5. [その他の *ポリシー] まで下にスクロールし*、[追加ポリシーの Defender を評価 **する] タイルOffice 365** します。

   :::image type="content" source="../../media/mdo-eval/4_mdo-eval-activate-eval.png" alt-text="[Eval Defender for Office 365] タイルは、電子メールとコラボレーション ベクターの間で 30 日間&試用です。[クリックスルー] をクリックします。":::

6. 次に、外部メールを直接送信するかExchange Onlineサード パーティのゲートウェイまたはサービスにルーティングするか選択し、[次へ] をクリックします。

   :::image type="content" source="../../media/mdo-eval/5_mdo-eval-activate-eval.png" alt-text="Defender for Office 365は、メールボックスへのメール送信をExchange Onlineします。メールのルーティング方法の詳細 (メールをルーティングする送信コネクタの名前など) を指定します。EOP (EOP) Exchange Online Protection使用する場合は、コネクタを使用することはできません。3rd-party プロバイダーまたはオンプレミス プロバイダーを使用しているか、EOP のみを使用する場合は、1 つを選択します。":::

7. サードパーティゲートウェイを使用する場合は、ドロップダウンからベンダー名を選択し、そのソリューションに関連付けられた受信コネクタを選択します。 回答を一覧表示した場合は、[次へ] をクリックします。

   :::image type="content" source="../../media/mdo-eval/6-mdo-eval-activate-eval-settings.png" alt-text="このダイアログで、組織で使用しているサードパーティ ベンダー サービスを選択するか、[*Other*] を選択します。次のダイアログ ボックスで、受信コネクタを選択します。次に、[次へ] をクリックします。":::

8. 設定を確認し、[評価の作成 **] ボタンをクリック** します。

   |イベント前|イベント後|
   |:---:|:---:|
   |:::image type="content" source="../../media/mdo-eval/7-mdo-eval-activate-review.png" alt-text="このウィンドウには、設定を確認するドロップダウンがあります。必要に応じて、[ルーティングの種類を編集する] へのリンクもクリックできます。準備ができたら、大きな青い [評価の作成] ボタンをクリックします。":::|:::image type="content" source="../../media/mdo-eval/8-mdo-eval-activate-complete.png" alt-text="これで、セットアップが完了しました。このページの青いボタンに「評価に移動」と表示されます。":::|
   |

## <a name="next-steps"></a>次の手順

手順 3/ 3: Microsoft Defender のパイロットをセットアップして、ユーザーにOffice 365

[Microsoft Defender for Office 365 の評価[] の概要に戻Office 365](eval-defender-office-365-overview.md)

[評価とパイロット][の概要に戻Microsoft 365 Defender](eval-overview.md)
