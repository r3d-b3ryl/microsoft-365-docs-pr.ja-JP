---
title: メール フロー ダッシュボードでのキューの分析情報
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードでキュー ウィジェットを使用して、送信コネクタを使用してオンプレミスまたはパートナー組織への失敗したメール フローを監視する方法について説明します。
ms.openlocfilehash: a1563c61620ef9f1ae97739681f426fd0ea38bd8
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659282"
---
# <a name="queues-insight-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センターでの&の分析情報

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


コネクタを使用して組織からオンプレミスまたはパートナーの電子メール サーバーにメッセージを送信できない場合、メッセージは Microsoft 365 でキューに入れられます。 この状態を引き起こす一般的な例を次に示します。

- コネクタが正しく構成されていません。
- オンプレミス環境でネットワークまたはファイアウォールの変更が行いました。

Microsoft 365 は引き続き配信を 24 時間再試行します。 24 時間後、メッセージは有効期限が切れ、配信拒否レポート (NDRs またはバウンス メッセージとも呼ばれる) で送信者に返されます。

キューに入った電子メール ボリュームが定義済みのしきい値 (既定値は 200 メッセージ) を超える場合、情報は次の場所で使用できます。

- セキュリティ **/コンプライアンス** センターの [メール](mail-flow-insights-v2.md) フロー ダッシュボードの [キュー&表示されます](https://protection.office.com)。 詳細については、この記事の「メール フロー ダッシュボード」セクションの [「](#queues-insight-in-the-mail-flow-dashboard) キュー」の分析情報を参照してください。

- アラートは、セキュリティ/**コンプライアンス** センター (アラート ダッシュボードまたは) の [[最近&](https://protection.office.com)**アラート]** \> **ダッシュボードに表示** されます <https://protection.office.com/alertsdashboard> 。

  ![セキュリティ/コンプライアンス センターのアラート ダッシュボード&最近のアラート](../../media/mfi-queued-messages-alert.png)

- 管理者は、"メッセージ" という名前の既定のアラート ポリシーの構成に基づいて、電子 **メール通知を受信します**。 このアラートの通知設定を構成するには、次のセクションを参照してください。

  アラート ポリシーの詳細については、セキュリティ/コンプライアンス センターの「アラート [&参照してください](../../compliance/alert-policies.md)。

## <a name="customize-queue-alerts"></a>キュー通知をカスタマイズする

1. セキュリティ/ [コンプライアンス センターで&](https://protection.office.com)アラート **ポリシー** に移動するか \> **、開** きます <https://protection.office.com/alertpolicies> 。

2. [アラート **ポリシー] ページで** 、[メッセージ] という名前のポリシーを見つけて **選択します**。

3. メッセージが **遅延して表示される** フライアウトで、通知をオンまたはオフにし、通知設定を構成できます。

   ![メッセージは、セキュリティ/コンプライアンス センターの警告ポリシー&遅れています](../../media/mfi-queued-messages-alert-policy.png)

   - **状態**: アラートのオンとオフを切り替えます。

   - **電子メールの受信者と** **1 日の通知の制限**: [編集 **]** をクリックして、次の設定を構成します。

4. 通知設定を構成するには、[編集] を **クリックします**。 表示される **ポリシーの** 編集フライアウトで、次の設定を構成します。

   - **電子メール通知の** 送信 : 既定値はオンです。
   - **電子メールの受信者**: 既定値は **TenantAdmins です**。
   - **1 日の通知の** 制限 : 既定値は **[制限なし] です**。
   - **しきい** 値 : 既定値は 200 です。

   ![メッセージの通知設定は、セキュリティ/コンプライアンス センターの警告ポリシーの&されています。](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. 完了したら、[保存して閉じる] **を** クリック **します**。

## <a name="queues-insight-in-the-mail-flow-dashboard"></a>メール フロー ダッシュボードでのキューの分析情報

キューに入っているメッセージ ボリュームがしきい値を超えていてアラートを生成していなくても、メール フローダッシュボードでキューの分析[](mail-flow-insights-v2.md)情報を使用して、1 時間以上キューに入っているメッセージを確認し、キューに入っているメッセージの数が多くなりすぎる前にアクションを実行できます。

![セキュリティ/コンプライアンス センターのメール フロー ダッシュボード&ウィジェット](../../media/mfi-queues-widget.png)

ウィジェット上のメッセージ数をクリックすると、キューに入ったメッセージ **のフライ** アウトが次の情報と一緒に表示されます。

- **キューに入ったメッセージの数**
- **コネクタ名**: コネクタ名をクリックして、Exchange 管理センター (EAC) でコネクタを管理します。
- **キューの開始時刻**
- **最も古いメッセージの有効期限が切れています**
- **送信先サーバー**
- **最後の IP アドレス**
- **最後のエラー**
- **解決方法**: 一般的な問題と解決策を利用できます。 If is a **Fix it now** link is available, click it to fix the problem. それ以外の場合は、エラーと考えられる解決策の詳細については、利用可能なリンクをクリックしてください。

![メール フロー ダッシュボードでキューの分析情報をクリックした後の詳細](../../media/mfi-queues-details.png)

メッセージが遅延アラートの詳細で [キューの表示] をクリックすると、同 **じフライアウトが表示** されます。

![セキュリティ/コンプライアンス センターでメッセージの警告の&されています](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a>関連項目

メール フロー ダッシュボードの他の分析情報については、セキュリティ/コンプライアンス センターの「メール [フロー&参照してください](mail-flow-insights-v2.md)。
