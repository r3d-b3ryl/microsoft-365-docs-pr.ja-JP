---
title: 運用環境でMicrosoft Defender for Office 365の評価環境を有効にする
description: 試用版ライセンス、MX レコード処理、承認済みドメインと受信接続の監査& Microsoft Defender for Office 365評価をアクティブ化する手順。
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
ms.date: 07/01/2021
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
ms.openlocfilehash: b41754e6fe8930f2b01c983ff7d30e1d478efcb4
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67478863"
---
# <a name="enable-the-evaluation-environment"></a>評価環境を有効にする

**適用対象:**
- Microsoft 365 Defender

この記事は、Microsoft Defender for Office 365の評価環境を設定する手順 [2/3](eval-defender-office-365-overview.md) です。 このプロセスの詳細については、 [概要に](eval-defender-office-365-overview.md)関する記事を参照してください。

次の手順を使用して、Microsoft Defender for Office 365の評価を有効にします。

:::image type="content" source="../../media/defender/m365-defender-office-eval-enable-steps.png" alt-text="Microsoft Defender 評価環境でMicrosoft Defender for Office 365を有効にする手順" lightbox="../../media/defender/m365-defender-office-eval-enable-steps.png":::


- [手順 1: 試用版ライセンスをアクティブ化する](#step-1-activate-trial-licenses)
- [手順 2: パブリック MX レコードを監査して確認する](#step-2-audit-and-verify-the-public-mx-record)
- [手順 3: 承認済みドメインを監査する](#step-3-audit-accepted-domains)
- [手順 4: 受信コネクタを監査する](#step-4-audit-inbound-connectors)
- [手順 5: 評価をアクティブ化する](#step-5-activate-the-evaluation)

## <a name="step-1-activate-trial-licenses"></a>手順 1: 試用版ライセンスをアクティブ化する

既存のMicrosoft Defender for Office 365環境またはテナント管理ポータルにログオンします。

1. 管理ポータルに移動します。
2. クイック起動から [サービスの購入] を選択します。

   :::image type="content" source="../../media/mdo-eval/1_m365-purchase-services.png" alt-text="Microsoft 365 管理センターでクリックする [サービスの購入] オプション" lightbox="../../media/mdo-eval/1_m365-purchase-services.png":::

3. Add-On セクションまで下にスクロール (または "Defender" を検索) して、Microsoft Defender for Office 365プランを見つけます。
4. 評価するプランの横にある [詳細] をクリックします。

   :::image type="content" source="../../media/mdo-eval/2_mdo-eval-license-details.png" alt-text="クリックする [詳細] ボタン" lightbox="../../media/mdo-eval/2_mdo-eval-license-details.png":::

5. [ *無料試用版の開始]* リンクをクリックします。

   :::image type="content" source="../../media/mdo-eval/3-m365-purchase-button.png" alt-text="無料試用版の開始ハイパーリンク" lightbox="../../media/mdo-eval/3-m365-purchase-button.png":::

6. 要求を確認し、[ *今すぐ試す* ] ボタンをクリックします。

   :::image type="content" source="../../media/mdo-eval/4_mdo-trial-order.png" alt-text="[今すぐ試す] ボタン" lightbox="../../media/mdo-eval/4_mdo-trial-order.png":::

## <a name="step-2-audit-and-verify-the-public-mx-record"></a>手順 2: パブリック MX レコードを監査して確認する

Microsoft Defender for Office 365を効果的に評価するには、テナントに関連付けられているExchange Online Protection (EOP) インスタンスを介して受信外部メールを中継することが重要です。

1. M365 管理 ポータルにログオンし、[設定] を展開して [ドメイン] を選択します。
2. 確認済みの電子メール ドメインを選択し、[DNS の管理] をクリックします。
3. EOP テナントに生成および割り当てられた MX レコードをメモしておきます。
4. 外部 (パブリック) DNS ゾーンにアクセスし、メール ドメインに関連付けられているプライマリ MX レコードを確認します。
    - *パブリック MX レコードが現在、割り当てられた EOP アドレス (tenant-com.mail.protection.outlook.com など) と一致している場合は、それ以上のルーティング変更は必要ありません*。
    - パブリック MX レコードが現在サード パーティまたはオンプレミスの SMTP ゲートウェイに解決されている場合は、追加のルーティング構成が必要になる場合があります。
    - パブリック MX レコードが現在オンプレミスの Exchange に解決されている場合でも、一部の受信者メールボックスがまだ EXO に移行されていないハイブリッド モデルになっている可能性があります。

## <a name="step-3-audit-accepted-domains"></a>手順 3: 承認済みドメインを監査する

1. Exchange Online 管理 ポータルにログオンし、[メール フロー] を選択し、[承認済みドメイン] をクリックします。
2. テナントで追加および検証された承認済みドメインの一覧から、プライマリ電子メール ドメインの **ドメインの種類** を書き留めておきます。
    - ドメインの種類が ***[権限あり]*** に設定されている場合は、組織のすべての受信者メールボックスが現在Exchange Onlineにあると見なされます。
    - ドメインの種類が ***内部リレー*** に設定されている場合でも、一部の受信者メールボックスがまだオンプレミスに存在するハイブリッド モデルになっている可能性があります。

## <a name="step-4-audit-inbound-connectors"></a>手順 4: 受信コネクタを監査する

1. Exchange Online 管理 ポータルにログオンし、[メール フロー] を選択し、[コネクタ] をクリックします。
2. 構成済みのコネクタの一覧から、 **パートナー組織** のエントリを書き留め、サード パーティの SMTP ゲートウェイに関連付けることができます。
3. 構成済みのコネクタの一覧から、 **組織の電子メール サーバーから** というラベルが付いたエントリを書き留めます。これは、まだハイブリッド シナリオに入っていることを示している可能性があります。

## <a name="step-5-activate-the-evaluation"></a>手順 5: 評価をアクティブ化する

こちらの手順に従って、Microsoft 365 Defender ポータルからMicrosoft Defender for Office 365評価をアクティブ化します。

1. Microsoft 365 Defender ポータルにアクセスできるアカウントを使用してテナントにログオンします。
2. **Microsoft 365 Defender ポータルをMicrosoft Defender for Office 365** 管理用の既定のインターフェイスにするかどうかを選択します (推奨)。

   :::image type="content" source="../../media/mdo-eval/1_mdo-eval-activate-eval.png" alt-text="[設定で有効にする] ボタンを使用すると、管理用の一元化された改善されたMicrosoft 365 Defender ポータルが作成されます。" lightbox="../../media/mdo-eval/1_mdo-eval-activate-eval.png":::

3. ナビゲーション メニューの [*Email & コラボレーション*] **で [ポリシー&ルール**] を選択します。

   :::image type="content" source="../../media/mdo-eval/2_mdo-eval-activate-eval.png" alt-text="クリックする [ポリシー&ルール] メニュー項目" lightbox="../../media/mdo-eval/2_mdo-eval-activate-eval.png":::

4. [ *ポリシー & ルール* ] ダッシュボードで、[ **脅威ポリシー**] をクリックします。

   :::image type="content" source="../../media/mdo-eval/3_mdo-eval-activate-eval.png" alt-text="クリックする [脅威ポリシー] メニュー項目" lightbox="../../media/mdo-eval/3_mdo-eval-activate-eval.png":::

5. *[その他のポリシー]* まで下にスクロールし、[**評価] Defender for Office 365** タイルを選択します。

   :::image type="content" source="../../media/mdo-eval/4_mdo-eval-activate-eval.png" alt-text="Eval Defender for Office 365 タイル" lightbox="../../media/mdo-eval/4_mdo-eval-activate-eval.png":::

6. 次に、外部メールが直接Exchange Onlineするか、サード パーティのゲートウェイまたはサービスにルーティングするかを選択し、[次へ] をクリックします。

   :::image type="content" source="../../media/mdo-eval/5_mdo-eval-activate-eval.png" alt-text="Microsoft Defender for Office 365 ポータルの [ルーティング設定] ウィンドウ" lightbox="../../media/mdo-eval/5_mdo-eval-activate-eval.png":::

7. サード パーティゲートウェイを使用する場合は、ドロップダウンからベンダー名と、そのソリューションに関連付けられている受信コネクタを選択します。 回答の一覧が表示されたら、[次へ] をクリックします。

   :::image type="content" source="../../media/mdo-eval/6-mdo-eval-activate-eval-settings.png" alt-text="Microsoft Defender for Office 365 ポータルの [サード パーティまたはオンプレミスの設定] ウィンドウ" lightbox="../../media/mdo-eval/6-mdo-eval-activate-eval-settings.png":::

8. 設定を確認し、[ **評価の作成** ] ボタンをクリックします。

   |イベント前|イベント後|
   |:---:|:---:|
   |:::image type="content" source="../../media/mdo-eval/7-mdo-eval-activate-review.png" alt-text="Microsoft Defender for Office 365 ポータルの [設定の確認] ウィンドウ" lightbox="../../media/mdo-eval/7-mdo-eval-activate-review.png":::|:::image type="content" source="../../media/mdo-eval/8-mdo-eval-activate-complete.png" alt-text="Microsoft Defender for Office 365 ポータルの評価セットアップ完了通知" lightbox="../../media/mdo-eval/8-mdo-eval-activate-complete.png":::|
   |

## <a name="next-steps"></a>次の手順

手順 3/3: Microsoft Defender for Office 365のパイロットを設定する

[Microsoft Defender for Office 365の評価](eval-defender-office-365-overview.md)の概要に戻る

[評価とパイロットのMicrosoft 365 Defender](eval-overview.md)の概要に戻る
