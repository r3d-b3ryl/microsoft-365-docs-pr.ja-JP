---
title: Microsoft 脅威エキスパートの機能を構成および管理する
ms.reviewer: ''
description: Microsoft 脅威エキスパートに登録して、毎日のセキュリティ操作とセキュリティ管理作業で構成、管理、および使用します。
keywords: Microsoft 脅威エキスパート、マネージド 脅威ハンティング サービス、MTE、Microsoft マネージド ハンティング サービス
search.product: Windows 10
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5883b5af4101f9227e43009a148344b82fdfb5ef
ms.sourcegitcommit: fa90763559239c4c46c5e848939126763879d8e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2022
ms.locfileid: "66772689"
---
# <a name="configure-and-manage-microsoft-threat-experts-capabilities"></a>Microsoft 脅威エキスパートの機能を構成および管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="before-you-begin"></a>開始する前に

> [!NOTE]
> Endpoint Attack Notifications マネージド脅威ハンティング サービスに適用する前に、Microsoft Technical Service プロバイダーとアカウント チームと資格要件について話し合ってください。

ラボのセットアップだけでなく、デバイスが登録されている環境に Defender for Endpoint がデプロイされていることを確認します。

Defender for Endpoint のお客様の場合は、 **エンドポイント攻撃通知** を申請して、最も重要な脅威を特定するのに役立つ特別な分析情報と分析情報を取得し、それらに迅速に対応できるようにする必要があります。 Microsoft 脅威エキスパートにサブスクライブするには、アカウント チームまたは Microsoft の担当者に問い合わせてください **。エキスパートオンデマンド** では、関連する検出と敵対者について脅威の専門家に相談してください。

## <a name="apply-for-endpoint-attack-notifications-service"></a>エンドポイント攻撃通知サービスに適用する

Defender for Endpoint のお客様は、Microsoft 365 Defender ポータルから申請できます。

1. ナビゲーション ウィンドウで、[ **設定] > [全般>高度な機能>エンドポイント攻撃通知] に** 移動します。

2. [**適用**] をクリックします。

   :::image type="content" source="images/mte-collaboratewithmte.png" alt-text="Microsoft 脅威エキスパート設定" lightbox="images/mte-collaboratewithmte.png":::

3. Microsoft がアプリケーションに戻ることができるように、名前と電子メール アドレスを入力します。

   :::image type="content" source="images/mte-apply.png" alt-text="Microsoft 脅威エキスパート アプリケーション ページの [名前] フィールド" lightbox="images/mte-apply.png":::

4. [プライバシーに関する声明](https://privacy.microsoft.com/privacystatement)を読み、完了したら [**送信]** をクリックします。 アプリケーションが承認されると、ウェルカム メールが届きます。

   :::image type="content" source="images/mte-applicationconfirmation.png" alt-text="Microsoft 脅威エキスパートアプリケーションの確認メッセージ" lightbox="images/mte-applicationconfirmation.png":::

承諾されると、ウェルカム メールが届き、[ **適用** ] ボタンが "オン" になっているトグルに変更されて表示されます。 エンドポイント攻撃通知サービスから自分を離れたい場合は、トグルを "オフ" にスライドさせて、ページの下部にある [ **保存] を** クリックします。

## <a name="where-youll-see-the-endpoint-attack-notifications-from-microsoft-threat-experts"></a>Microsoft 脅威エキスパートからのエンドポイント攻撃通知が表示される場所

Microsoft 脅威エキスパートから、以下の媒体を通じて、標的型攻撃通知を受信できます。

- Defender for Endpoint portal の **[インシデント]** ページ
- Defender for Endpoint ポータルの **アラート** ダッシュボード
- OData アラート [API](/windows/security/threat-protection/microsoft-defender-atp/get-alerts) と [REST API](/windows/security/threat-protection/microsoft-defender-atp/pull-alerts-using-rest-api)
- 高度なハンティングの [DeviceAlertEvents](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-devicealertevents-table) テーブル
- ユーザーのメール(構成することにした場合)

電子メールでエンドポイント攻撃通知を受信するには、電子メール通知ルールを作成します。

### <a name="create-an-email-notification-rule"></a>電子メール通知ルールを作成する

通知の受信者に電子メール通知を送信するルールを作成できます。 詳細については、「電子メール通知を作成、編集、削除、またはトラブルシューティングするようにアラート通知を  [構成](configure-email-notifications.md) する」を参照してください。

## <a name="view-the-endpoint-attack-notifications"></a>エンドポイント攻撃通知を表示する

電子メール通知を受信するようにシステムを構成した後、電子メールのMicrosoft 脅威エキスパートからエンドポイント攻撃通知の受信を開始します。

1. メール内のリンクをクリックして、 **脅威の専門家** がタグ付けされたダッシュボードの対応するアラート コンテキストに移動します。

2. ダッシュボードから、メールから取得したのと同じアラート トピックを選択して、詳細を表示します。

## <a name="subscribe-to-microsoft-threat-experts---experts-on-demand"></a>Microsoft 脅威エキスパートをサブスクライブする - エキスパート オンデマンド

これはサブスクリプション サービスとして使用できます。 すでに Defender for Endpoint のお客様である場合は、Microsoft の担当者に連絡して、Microsoft 脅威エキスパート - エキスパート オンデマンドに登録することができます。

## <a name="consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization"></a>組織内の疑わしいサイバーセキュリティアクティビティについて Microsoft の脅威の専門家に問い合わせてください

Microsoft 365 Defender ポータル内から直接対応できるMicrosoft 脅威エキスパートと提携できます。 専門家は、ポータル ダッシュボードに表示される複雑な脅威、ターゲットを絞った攻撃通知、またはアラート、侵害された可能性のあるデバイス、脅威インテリジェンス コンテキストに関する詳細情報が必要な場合に、より深く理解するための分析情報を提供します。

> [!NOTE]
>
> - 組織のカスタマイズされた脅威インテリジェンス データに関連するアラートの問い合わせは、現在サポートされていません。 詳細については、セキュリティ運用またはインシデント対応チームに問い合わせてください。
> - "脅威の専門家に相談してください" の問い合わせを送信するには、Microsoft 365 Defender ポータルで **セキュリティ設定の管理** アクセス許可が必要です。

1. 調査する関連情報を含むポータル ページ ( **インシデント ページなど** ) に移動します。 調査要求を送信する前に、関連するアラートまたはデバイスのページが表示されていることを確認します。

2. 右上のメニューで 、 **?** 選択します。 次に、[ **脅威の専門家に相談** する] を選択します。

    :::image type="content" source="images/mte-eod-menu.png" alt-text="[Microsoft 脅威エキスパートエキスパートオンデマンド] メニュー項目" lightbox="images/mte-eod-menu.png":::

    ポップアップ画面が開きます。 次の画面は、試用版サブスクリプションの場合を示しています。

    :::image type="content" source="images/mte-eod.png" alt-text="Microsoft 脅威エキスパートエキスパート オンデマンド ページ" lightbox="images/mte-eod.png":::

    次の画面は、完全なMicrosoft 脅威エキスパート - エキスパート オンデマンド サブスクリプションの場合を示しています。

    :::image type="content" source="images/mte-eod-fullsubscription.png" alt-text="Microsoft 脅威エキスパート エキスパート オンデマンドの完全なサブスクリプション ページ" lightbox="images/mte-eod-fullsubscription.png":::

    **[お問い合わせ] トピック** フィールドには、調査要求に関連するページへのリンクが事前に設定されています。 たとえば、要求を行ったときのインシデント、アラート、またはデバイスの詳細ページへのリンクなどです。

3. 次のフィールドで、調査を開始するのに十分なコンテキストをMicrosoft 脅威エキスパートするのに十分な情報を指定します。

4. Microsoft 脅威エキスパートに対応するために使用する電子メール アドレスを入力します。

> [!NOTE]
> Microsoft Services Hub を通じてエキスパート オンデマンド ケースの状態を追跡する場合は、カスタマー サクセス アカウント マネージャーにお問い合わせください。

Microsoft Services Hub の概要については、このビデオをご覧ください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4pk9f]

## <a name="sample-investigation-topics-that-you-can-consult-with-microsoft-threat-experts---experts-on-demand"></a>Microsoft 脅威エキスパートに相談できるサンプル調査トピック - エキスパート オンデマンド

### <a name="alert-information"></a>アラート情報

- [AlertID] という新しい種類のライブ オフ ランド バイナリに対するアラートが表示されます。 このアラートの詳細と、さらに詳しく調査する方法をお聞かせください。
- 2 つの同様の攻撃が見られ、悪意のある PowerShell スクリプトを実行しようとしましたが、異なるアラートが生成されます。 1 つは "疑わしい PowerShell コマンド ライン" で、もう 1 つは "O365 によって提供された指示に基づいて悪意のあるファイルが検出されました" です。 違いは何ですか?
- 今日、高プロファイル ユーザーのデバイスから失敗したログインの異常な数に関する奇数のアラートを受け取ります。 これらのサインイン試行に関するそれ以上の証拠は見つかりません。 Defender for Endpoint では、これらの試行をどのように確認できますか? 監視対象のサインインの種類は何ですか?
- このアラートに関するより多くのコンテキストや分析情報を提供できますか。"システム ユーティリティによる疑わしい動作が観察されました"。

### <a name="possible-device-compromise"></a>デバイスの侵害の可能性

- "不明なプロセスが観察された" と表示される理由の回答をお願いします。 このメッセージまたはアラートは、多くのデバイスで頻繁に表示されます。 このメッセージまたはアラートが悪意のあるアクティビティに関連しているかどうかを明確にするために、ご意見をお願いします。
- [月] の同じシステムでの以前の [マルウェア名] マルウェア検出と同様の動作を持つ [日付] に、次のシステムで侵害の可能性を検証するのに役立ちますか?

### <a name="threat-intelligence-details"></a>脅威インテリジェンスの詳細

- 悪意のある Word 文書をユーザーに配信したフィッシングメールが検出されました。 悪意のある Word 文書により、一連の疑わしいイベントが発生し、[マルウェア名] マルウェアに対する複数のエンドポイント攻撃通知アラートがトリガーされました。 このマルウェアに関する情報はありますか? はいの場合は、リンクを送信できますか?
- 最近、業界をターゲットにしている脅威に関する [ソーシャル メディア リファレンス (Twitter やブログなど)] の投稿を見ました。 この脅威アクターに対して Defender for Endpoint が提供する保護について理解するのに役立ちますか?

### <a name="microsoft-threat-experts-alert-communications"></a>Microsoft 脅威エキスパート' アラート通信

- インシデント対応チームは、Microsoft が受け取ったエンドポイント攻撃通知に対処するのに役立ちますか?
- このエンドポイント攻撃通知をMicrosoft 脅威エキスパートから受信しました。 独自のインシデント対応チームはありません。 この時点でできることと、インシデントをどのように含めることができるか。
- Microsoft 脅威エキスパートからエンドポイント攻撃通知を受け取った。 インシデント対応チームに渡すことができるデータは何ですか?

  > [!NOTE]
  > Microsoft 脅威エキスパートはマネージド サイバーセキュリティハンティング サービスであり、インシデント対応サービスではありません。 ただし、独自のインシデント対応チームと連携して、インシデント対応が必要な問題に対処できます。 独自のインシデント対応チームがなく、Microsoft のサポートが必要な場合は、CSS サイバーセキュリティ インシデント対応チーム (CIRT) に参加できます。 問い合わせに対処するためにチケットを開くことができます。

## <a name="scenario"></a>シナリオ

### <a name="receive-a-progress-report-about-your-managed-hunting-inquiry"></a>マネージドハンティングの問い合わせに関する進行状況レポートを受け取る

Microsoft 脅威エキスパートからの応答は、お問い合わせによって異なります。 次のカテゴリから調査の状態を伝えるために、2 日以内に **脅威の専門家に問** い合わせに関する進行状況レポートを電子メールで送信します。

- 調査を続行するには、より多くの情報が必要です
- 技術的なコンテキストを決定するには、ファイルまたは複数のファイル サンプルが必要です
- 調査にはより多くの時間が必要です
- 調査を完了するのに十分な初期情報

調査を進め続けるためには、迅速に対応することが重要です。

## <a name="related-topic"></a>関連トピック

- [Microsoft 脅威エキスパートの概要](microsoft-threat-experts.md)
- [Microsoft 365 のMicrosoft 脅威エキスパートの概要](/microsoft-365/security/mtp/microsoft-threat-experts)
