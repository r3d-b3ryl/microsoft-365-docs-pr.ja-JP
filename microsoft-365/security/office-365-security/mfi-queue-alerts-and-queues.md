---
title: メール フロー ダッシュボードの Queues 分析情報
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.custom: ''
ms.localizationpriority: medium
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: 管理者は、セキュリティ & コンプライアンス センターの [メール フロー] ダッシュボードの [キュー] ウィジェットを使用して、送信コネクタ経由でオンプレミスまたはパートナー組織へのメール フローの失敗を監視する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.collection: M365-security-compliance
ms.openlocfilehash: 146ce26c32f1ff80a451b85fd343990db547a131
ms.sourcegitcommit: 45bc65972d4007b2aa7760d4457a0d2699f81926
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2022
ms.locfileid: "64972653"
---
# <a name="queues-insight-in-the-security--compliance-center"></a>セキュリティ & コンプライアンス センターの Queues 分析情報

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

コネクタを使用して組織からオンプレミスまたはパートナーの電子メール サーバーにメッセージを送信できない場合、メッセージはMicrosoft 365にキューに入れられます。 この条件の原因となる一般的な例は次のとおりです。

- コネクタが正しく構成されていません。
- オンプレミス環境でネットワークまたはファイアウォールの変更が行われています。

Microsoft 365は引き続き 24 時間配信を再試行します。 24 時間後、メッセージは期限切れになり、配信不能レポート (NDR またはバウンス メッセージとも呼ばれます) で送信者に返されます。

キューに置かれた電子メール ボリュームが定義済みのしきい値を超えた場合 (既定値は 200 メッセージ)、情報は次の場所で使用できます。

- [セキュリティ & コンプライアンス センター](https://protection.office.com)の [メール フロー ダッシュボード](mail-flow-insights-v2.md)の **Queues** 分析情報。 詳細については、この記事の [「メール フロー ダッシュボード」セクションの Queues 分析情報](#queues-insight-in-the-mail-flow-dashboard) を参照してください。

- アラートは、[セキュリティ & コンプライアンス センター](https://protection.office.com) (アラート **ダッシュボード** または<https://protection.office.com/alertsdashboard>アラート ダッシュボード) の [最近の **アラート]** \> ダッシュボードに表示されます。

  :::image type="content" source="../../media/mfi-queued-messages-alert.png" alt-text="セキュリティ & コンプライアンス センターの [アラート] ダッシュボードの [最近のアラート]" lightbox="../../media/mfi-queued-messages-alert.png":::

- 管理者は、 **メッセージが遅延した** という名前の既定のアラート ポリシーの構成に基づいて、電子メール通知を受け取ります。 このアラートの通知設定を構成するには、次のセクションを参照してください。

  アラート ポリシーの詳細については、 [セキュリティ & コンプライアンス センターのアラート ポリシーに](../../compliance/alert-policies.md)関するページを参照してください。

## <a name="customize-queue-alerts"></a>キュー アラートをカスタマイズする

1. [セキュリティ & コンプライアンス センター](https://protection.office.com)で、**アラート アラート** \> **ポリシー** に移動するか、 を開きます<https://protection.office.com/alertpolicies>。

2. [ **アラート ポリシー** ] ページで、 **メッセージが遅延した** という名前のポリシーを見つけて選択します。

3. メッセージが表示 **された遅延** ポップアップで、アラートのオンとオフを切り替え、通知設定を構成できます。

   :::image type="content" source="../../media/mfi-queued-messages-alert-policy.png" alt-text="メッセージの詳細が遅延したアラート" lightbox="../../media/mfi-queued-messages-alert-policy.png":::

   - **状態**: アラートのオンとオフを切り替えることができます。

   - **電子メール受信者** と **毎日の通知の制限**: **[編集]** をクリックして、次の設定を構成します。

4. 通知設定を構成するには、[ **編集]** をクリックします。 表示される **[ポリシーの編集]** ポップアップで、次の設定を構成します。

   - **電子メール通知の送信**: 既定値はオンです。
   - **電子メール受信者**: 既定値は **TenantAdmins** です。
   - **日次通知の制限**: 既定値は **制限なし** です。
   - **しきい値**: 既定値は 200 です。

     :::image type="content" source="../../media/mfi-queued-messages-alert-policy-notification-settings.png" alt-text="[メッセージ] の [通知] 設定が遅延したアラート" lightbox="../../media/mfi-queued-messages-alert-policy-notification-settings.png":::

5. 完了したら、[**保存して****閉じる**] をクリックします。

## <a name="queues-insight-in-the-mail-flow-dashboard"></a>メール フロー ダッシュボードの Queues 分析情報

キューに置かれたメッセージ ボリュームがしきい値を超えず、アラートを生成していない場合でも、[メール フロー ダッシュボード](mail-flow-insights-v2.md)の **Queues** 分析情報を使用して、1 時間以上キューに登録されたメッセージを表示し、キューに置かれたメッセージの数が多くなりすぎる前にアクションを実行できます。

:::image type="content" source="../../media/mfi-queues-widget.png" alt-text="セキュリティ & コンプライアンス センターの [メール フロー] ダッシュボードの [キュー] ウィジェット" lightbox="../../media/mfi-queues-widget.png":::

ウィジェットでメッセージの数をクリックすると、次の情報を含む **メッセージ キューに置かれた** ポップアップが表示されます。

- **キューに置かれたメッセージの数**
- **コネクタ名**: Exchange管理センター (EAC) <https://admin.exchange.microsoft.com/#/connectors>でコネクタを管理するコネクタ名を選択します。
- **キューの開始時刻**
- **最も古いメッセージの有効期限が切れています**
- **移行先サーバー**
- **最後の IP アドレス**
- **最後のエラー**
- **修正方法**: 一般的な問題と解決策を利用できます。 **[今すぐ修正]** リンクが使用可能な場合は、クリックして問題を解決します。 それ以外の場合は、エラーと考えられる解決策の詳細については、使用可能なリンクをクリックしてください。

:::image type="content" source="../../media/mfi-queues-details.png" alt-text="[メール フロー] ダッシュボードで [キュー] 分析情報をクリックした後の詳細" lightbox="../../media/mfi-queues-details.png":::

メッセージの詳細で **[キューの表示** ] をクリックすると、同じポップアップ **が表示されます** 。

:::image type="content" source="../../media/mfi-queued-messages-alert-details.png" alt-text="メッセージの詳細は、セキュリティ & コンプライアンス センターでアラートが遅延しています" lightbox="../../media/mfi-queued-messages-alert-details.png":::

## <a name="see-also"></a>関連項目

メール フロー ダッシュボードのその他の分析情報については、 [セキュリティ & コンプライアンス センターのメール フロー分析情報に関する](mail-flow-insights-v2.md)ページを参照してください。
