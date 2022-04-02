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
ms.openlocfilehash: a5a14d507f7cd10ff4f7ab62b552ab256f0e4a5e
ms.sourcegitcommit: 3b8e009ea1ce928505b8fc3b8926021fb91155f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2022
ms.locfileid: "64499003"
---
# <a name="enable-the-evaluation-environment"></a>評価環境を有効にする

**適用対象:**
- Microsoft 365 Defender

この記事は[、Microsoft Defender for microsoft Defender の](eval-defender-office-365-overview.md)評価環境をセットアップするプロセスの手順 2/3 Office 365。 このプロセスの詳細については、概要の記事を [参照してください](eval-defender-office-365-overview.md)。

次の手順を使用して、Microsoft Defender の評価を有効にOffice 365。

:::image type="content" source="../../media/defender/m365-defender-office-eval-enable-steps.png" alt-text="Microsoft Defender 評価環境で Microsoft Defender Office 365を有効にする手順" lightbox="../../media/defender/m365-defender-office-eval-enable-steps.png":::


- [手順 1: 試用版ライセンスをアクティブ化する](#step-1-activate-trial-licenses)
- [手順 2: パブリック MX レコードの監査と確認](#step-2-audit-and-verify-the-public-mx-record)
- [手順 3: 承認されたドメインを監査する](#step-3-audit-accepted-domains)
- [手順 4: 受信コネクタを監査する](#step-4-audit-inbound-connectors)
- [手順 5: 評価をアクティブ化する](#step-5-activate-the-evaluation)

## <a name="step-1-activate-trial-licenses"></a>手順 1: 試用版ライセンスをアクティブ化する

既存の Microsoft Defender にログオンして、Office 365管理ポータルにログオンします。

1. 管理ポータルに移動します。
2. クイック 起動から [サービスの購入] を選択します。

   :::image type="content" source="../../media/mdo-eval/1_m365-purchase-services.png" alt-text="[サービスの購入] オプションをクリックして、Microsoft 365 管理センター" lightbox="../../media/mdo-eval/1_m365-purchase-services.png":::

3. 下にスクロールして 、[Add-On] セクション (または "Defender") を検索して、Microsoft Defender のプランOffice 365します。
4. 評価するプランの横にある [詳細] をクリックします。

   :::image type="content" source="../../media/mdo-eval/2_mdo-eval-license-details.png" alt-text="クリックする [詳細] ボタン" lightbox="../../media/mdo-eval/2_mdo-eval-license-details.png":::

5. [無料試用版 *の開始] リンクをクリック* します。

   :::image type="content" source="../../media/mdo-eval/3-m365-purchase-button.png" alt-text="無料試用版の開始ハイパーリンク" lightbox="../../media/mdo-eval/3-m365-purchase-button.png":::

6. 要求を確認し、[今すぐ試 *す] ボタンをクリック* します。

   :::image type="content" source="../../media/mdo-eval/4_mdo-trial-order.png" alt-text="[今すぐ試す] ボタン" lightbox="../../media/mdo-eval/4_mdo-trial-order.png":::

## <a name="step-2-audit-and-verify-the-public-mx-record"></a>手順 2: パブリック MX レコードの監査と確認

Microsoft Defender for Office 365を効果的に評価するには、テナントに関連付けられた Exchange Online Protection (EOP) インスタンスを介して受信外部メールを中継することが重要です。

1. M365 管理ポータルにログオンし、[ドメイン] を設定し、[ドメイン] を選択します。
2. 確認済みのメール ドメインを選択し、[DNS の管理] をクリックします。
3. 生成され、EOP テナントに割り当てられた MX レコードをメモします。
4. 外部 (パブリック) DNS ゾーンにアクセスし、メール ドメインに関連付けられているプライマリ MX レコードを確認します。
    - *パブリック MX レコードが現在* 割り当てられている EOP アドレス (tenant-com.mail.protection.outlook.com など) と一致する場合は、それ以上のルーティング変更は必要ありません。
    - パブリック MX レコードが現在サード パーティまたはオンプレミスの SMTP ゲートウェイに解決されている場合は、追加のルーティング構成が必要になる場合があります。
    - パブリック MX レコードが現在オンプレミスのレコードに解決されている場合Exchange、一部の受信者メールボックスがまだ EXO に移行されていないハイブリッド モデルに残っている可能性があります。

## <a name="step-3-audit-accepted-domains"></a>手順 3: 承認されたドメインを監査する

1. [管理者ポータル] Exchange Onlineログオンし、[メール アドレス] をFlowし、[承諾されたドメイン] をクリックします。
2. テナントで追加および検証された承認されたドメインの一覧から、プライマリ メール ドメインのドメインの種類をメモします。
    - ドメインの種類が [権限]  に設定されている場合は、組織のすべての受信者メールボックスが現在組織に存在Exchange Online。
    - ドメインの種類が ***Internal Relay*** に設定されている場合、一部の受信者メールボックスがまだオンプレミスに存在するハイブリッド モデルに存在する可能性があります。

## <a name="step-4-audit-inbound-connectors"></a>手順 4: 受信コネクタを監査する

1. [管理者ポータル] Exchange Onlineログオンし、[メール] Flowを選択し、[コネクタ] をクリックします。
2. 構成済みのコネクタの一覧から、パートナー組織からのエントリをメモし、サード パーティの SMTP ゲートウェイに関連付ける可能性があります。
3. 構成済みのコネクタの一覧から、ハイブリッド シナリオに残っている可能性がある組織のメール サーバーからというラベルが付いたエントリをメモします。

## <a name="step-5-activate-the-evaluation"></a>手順 5: 評価をアクティブ化する

この手順を使用して、Microsoft Defender をアクティブ化し、Office 365評価をMicrosoft 365 Defenderします。

1. ポータルにアクセスできるアカウントを使用してテナントにログオンMicrosoft 365 Defenderします。
2. 管理者向け Microsoft Defender の既定のMicrosoft 365 Defender **ポータル** を作成するかどうかをOffice 365選択します (推奨)。

   :::image type="content" source="../../media/mdo-eval/1_mdo-eval-activate-eval.png" alt-text="管理用の一元設定および改善されたポータルを表示するには、[Microsoft 365 Defenderを有効にする] ボタン" lightbox="../../media/mdo-eval/1_mdo-eval-activate-eval.png":::

3. ナビゲーション メニューから、[メールとコラボレーション] の下 **&ポリシー***とルール&選択します*。

   :::image type="content" source="../../media/mdo-eval/2_mdo-eval-activate-eval.png" alt-text="[ポリシー] &ルール] メニュー項目をクリックします。" lightbox="../../media/mdo-eval/2_mdo-eval-activate-eval.png":::

4. [ポリシー の *設定&] ダッシュボードで* 、[脅威 **ポリシー] をクリックします**。

   :::image type="content" source="../../media/mdo-eval/3_mdo-eval-activate-eval.png" alt-text="[脅威ポリシー] メニュー項目をクリックする" lightbox="../../media/mdo-eval/3_mdo-eval-activate-eval.png":::

5. [その他の *ポリシー] まで下にスクロールし*、[追加ポリシーの Defender の評価 **] タイルOffice 365** します。

   :::image type="content" source="../../media/mdo-eval/4_mdo-eval-activate-eval.png" alt-text="[Eval Defender for Office 365] タイル" lightbox="../../media/mdo-eval/4_mdo-eval-activate-eval.png":::

6. 次に、外部メールを直接送信するかExchange Onlineサード パーティのゲートウェイまたはサービスにルーティングするか選択し、[次へ] をクリックします。

   :::image type="content" source="../../media/mdo-eval/5_mdo-eval-activate-eval.png" alt-text="Microsoft Defender for microsoft Defender for Office 365 ウィンドウ" lightbox="../../media/mdo-eval/5_mdo-eval-activate-eval.png":::

7. サードパーティゲートウェイを使用する場合は、ドロップダウンからベンダー名を選択し、そのソリューションに関連付けられた受信コネクタを選択します。 回答を一覧表示した場合は、[次へ] をクリックします。

   :::image type="content" source="../../media/mdo-eval/6-mdo-eval-activate-eval-settings.png" alt-text="Microsoft Defender for Office 365 ポータルの [サード パーティまたはオンプレミスの設定] ウィンドウ" lightbox="../../media/mdo-eval/6-mdo-eval-activate-eval-settings.png":::

8. 設定を確認し、[評価の作成 **] ボタンをクリック** します。

   |イベント前|イベント後|
   |:---:|:---:|
   |:::image type="content" source="../../media/mdo-eval/7-mdo-eval-activate-review.png" alt-text="Microsoft Defender for the Microsoft Defender for Office 365 ポータル" lightbox="../../media/mdo-eval/7-mdo-eval-activate-review.png":::|:::image type="content" source="../../media/mdo-eval/8-mdo-eval-activate-complete.png" alt-text="Microsoft Defender for microsoft Defender for Office 365完了通知" lightbox="../../media/mdo-eval/8-mdo-eval-activate-complete.png":::|
   |

## <a name="next-steps"></a>次の手順

手順 3/ 3: Microsoft Defender のパイロットをセットアップして、ユーザーにOffice 365

[Microsoft [Defender for Office 365](eval-defender-office-365-overview.md)

[評価とパイロット] [の概要に戻Microsoft 365 Defender](eval-overview.md)
