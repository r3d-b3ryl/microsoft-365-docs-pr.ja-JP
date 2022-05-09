---
title: Microsoft 365 Defenderを使用してMicrosoft 脅威エキスパート機能を構成および管理する
description: Microsoft 365 Defenderを通じて Microsoft 脅威エキスパートにサブスクライブし、毎日のセキュリティ操作とセキュリティ管理作業で構成、管理、および使用します。
keywords: Microsoft 脅威エキスパート、マネージド 脅威ハンティング サービス、MTE、Microsoft マネージド ハンティング サービス
search.product: Windows 10
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-maave
author: martyav
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.topic: article
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: cd8f7e65c409138d6404a734b098e70e6d419cbb
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2022
ms.locfileid: "64667276"
---
# <a name="configure-and-manage-microsoft-threat-experts-capabilities-through-microsoft-365-defender"></a>Microsoft 365 Defenderを使用してMicrosoft 脅威エキスパート機能を構成および管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Prerelease](../includes/prerelease.md)]

## <a name="before-you-begin"></a>開始する前に

> [!IMPORTANT]
> 申し込む前に、Microsoft Technical Service プロバイダーとアカウント チームとMicrosoft 脅威エキスパート – ターゲット攻撃通知マネージド脅威ハンティング サービスの資格要件について説明してください。

ターゲットを絞った攻撃通知を受け取るには、デバイスが登録された状態で展開Microsoft 365 Defender必要があります。 次に、M365 ポータルからアプリケーションを送信し、Microsoft 脅威エキスパート - ターゲット攻撃通知を送信します。

アカウント チームまたは Microsoft 担当者に問い合わせて、Microsoft 脅威エキスパート - エキスパート オンデマンドにサブスクライブしてください。 エキスパート オン デマンドでは、関連する検出や敵対者から組織を保護する方法について、脅威の専門家に相談できます。

## <a name="apply-for-microsoft-threat-experts---targeted-attack-notifications-service"></a>Microsoft 脅威エキスパート - ターゲット攻撃通知サービスに申請する

Microsoft Defender for EndpointとMicrosoft 365 Defenderが既にある場合は、Microsoft 365 Defender ポータルからMicrosoft 脅威エキスパート – 対象攻撃通知を申請できます。  標的型攻撃通知は、組織に対する最も重要な脅威を特定するのに役立つ特別な分析情報と分析を提供し、迅速に対応できるようにします。

1. ナビゲーション ウィンドウで、[**設定 > エンドポイント] > [全般>高度な機能] > Microsoft 脅威エキスパート - [ターゲット攻撃通知] に移動します**。

2. **[適用]** を選択します。

    :::image type="content" source="../../media/mte/mte-collaboratewithmte.png" alt-text="Microsoft 365 Defender ポータルの [Microsoft 脅威エキスパート設定] ページ" lightbox="../../media/mte/mte-collaboratewithmte.png":::

3. Microsoft がアプリケーションについて連絡できるように、名前と電子メール アドレスを入力します。

    :::image type="content" source="../../media/mte/mte-apply.png" alt-text="Microsoft 365 Defender ポータルの [Microsoft 脅威エキスパート アプリケーション] ページ" lightbox="../../media/mte/mte-apply.png":::
  
4. [プライバシーに関する声明](https://privacy.microsoft.com/en-us/privacystatement)を読み、完了したら **[送信]** を選択します。 アプリケーションが承認されると、ウェルカム メールが届きます。

    :::image type="content" source="../../media/mte/mte-applicationconfirmation.png" alt-text="Microsoft 365 Defender ポータルでのMicrosoft 脅威エキスパートアプリケーションの確認" lightbox="../../media/mte/mte-applicationconfirmation.png":::

5. ウェルカム メールを受信すると、ターゲットを絞った攻撃通知の受信が自動的に開始されます。

6. 状態を確認するには **、設定 > エンドポイント>一般的な>高度な機能** にアクセスします。 承認されると、**Microsoft 脅威エキスパート - ターゲット攻撃通知** のトグルが表示され、**オン** に切り替わります。

## <a name="where-youll-see-the-targeted-attack-notifications-from-microsoft-threat-experts"></a>Microsoft 脅威エキスパートからの標的型攻撃通知が表示される場所

次のメディアを通じて、Microsoft 脅威エキスパートから標的型攻撃通知を受け取ることができます。

- Microsoft 365 Defender ポータルの **[インシデント]** ページ
- Microsoft 365 Defender ポータルの **アラート** ダッシュボード
- OData アラート [API](/windows/security/threat-protection/microsoft-defender-atp/get-alerts) と [REST API](/windows/security/threat-protection/microsoft-defender-atp/pull-alerts-using-rest-api)
- 高度なハンティングの [DeviceAlertEvents](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-devicealertevents-table) テーブル
- 電子メールでターゲットを絞った攻撃通知を送信することを選択した場合は、受信トレイ。 以下 [の「電子メール通知ルールを作成する](#create-an-email-notification-rule) 」を参照してください。

### <a name="create-an-email-notification-rule"></a>電子メール通知ルールを作成する

通知の受信者に電子メール通知を送信するルールを作成できます。 詳細については、「電子メール通知を作成、編集、削除、またはトラブルシューティングするための  [アラート通知の構成](/windows/security/threat-protection/microsoft-defender-atp/configure-email-notifications) 」を参照してください。

## <a name="view-targeted-attack-notifications"></a>対象となる攻撃通知を表示する

電子メール通知を受信するようにシステムを構成した後、電子メール内のMicrosoft 脅威エキスパートから標的型攻撃通知の受信を開始します。

1. メール内のリンクを選択して、 **脅威の専門家** がタグ付けされたダッシュボードの対応するアラート コンテキストに移動します。

2. [ **アラート** ] ページで、メールで受信したアラート トピックと同じアラート トピックを選択して、詳細を表示します。

## <a name="subscribe-to-microsoft-threat-experts---experts-on-demand"></a>Microsoft 脅威エキスパートをサブスクライブする - エキスパート オンデマンド

既にMicrosoft Defender for Endpoint顧客である場合は、Microsoft の担当者に問い合わせて、Microsoft 脅威エキスパート - エキスパート オンデマンドにサブスクライブできます。

## <a name="consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization"></a>組織内の疑わしいサイバーセキュリティアクティビティについて Microsoft の脅威の専門家に問い合わせてください

Microsoft 365 Defender ポータル内からMicrosoft 脅威エキスパートに連絡できます。 専門家は、複雑な脅威とターゲットを絞った攻撃通知を理解するのに役立ちます。 アラートやインシデントの詳細、または侵害の処理に関するアドバイスについては、エキスパートと協力してください。 ポータル ダッシュボードで説明されている脅威インテリジェンス コンテキストに関する分析情報を取得します。

> [!NOTE]
>
> - 組織のカスタマイズされた脅威インテリジェンス データに関連するアラートの問い合わせは、現在サポートされていません。 詳細については、セキュリティ運用またはインシデント対応チームにお問い合わせください。
> - 脅威 **の専門家に相談** するフォームから問い合わせを送信するには、Microsoft 365 Defender ポータルの **セキュリティ センターでセキュリティ設定を管理** するアクセス許可が必要です。

1. 調査する情報に関連するポータル ページ ( **デバイス**、 **アラート**、 **インシデント** など) に移動します。 調査要求を送信する前に、お問い合わせに関連するポータル ページが表示されていることを確認してください。

2. 上部のメニューから [ **?脅威の専門家に問い合わせてください**。

    :::image type="content" source="../../media/mte/incidents-action-mte-highlighted.png" alt-text="Microsoft 365 Defender ポータルのメニューからMicrosoft 脅威エキスパートエキスパートオンデマンド" lightbox="../../media/mte/incidents-action-mte-highlighted.png":::

    ポップアップ画面が開きます。

    ヘッダーには、試用版サブスクリプションを使用しているか、または完全なMicrosoft 脅威エキスパート - エキスパート オンデマンド サブスクリプションが表示されます。

    :::image type="content" source="../../media/mte/mte-trial.png" alt-text="Microsoft 365 Defender ポータルの [Microsoft 脅威エキスパート エキスパート オンデマンド試用版サブスクリプション] 画面" lightbox="../../media/mte/mte-trial.png":::

    **[調査] トピック** フィールドには、要求に関連するページへのリンクが既に設定されます。

3. 次のフィールドで、調査を開始するのに十分なコンテキストをMicrosoft 脅威エキスパートするのに十分な情報を指定します。

4. Microsoft 脅威エキスパートに対応するために使用する電子メール アドレスを入力します。

> [!NOTE]
> Microsoft Services Hub を通じてエキスパート オンデマンド ケースの状態を追跡する場合は、テクニカル アカウント マネージャーにお問い合わせください。

Microsoft Services Hub の概要については、このビデオをご覧ください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4pk9f]

## <a name="sample-investigation-topics"></a>調査トピックのサンプル

### <a name="alert-information"></a>アラート情報

- 新しい種類のアラートが、ライブオフのバイナリに対して見えました。 アラート ID を指定できます。 このアラートの詳細と、さらに詳しく調査する方法をお聞かせください。
- 2 つの同様の攻撃が観察されました。どちらも悪意のある PowerShell スクリプトを実行しようとしましたが、異なるアラートを生成します。 1 つは "疑わしい PowerShell コマンド ライン" で、もう 1 つは "O365 によって提供された指示に基づいて悪意のあるファイルが検出されました" です。 違いは何ですか?
- 今日、高プロファイル ユーザーのデバイスから、失敗したログインの異常な数に関する奇数のアラートを受け取った。 これらの試みについてそれ以上の証拠を見つけることができません。 これらの試みをMicrosoft 365 Defenderはどのように確認できますか? 監視対象のログインの種類は何ですか?
- "システム ユーティリティによる疑わしい動作が観察されました"というアラートに関して、より多くのコンテキストや分析情報を提供できますか?
- "転送/リダイレクト ルールの作成" というタイトルのアラートを観察しました。 アクティビティは問題ないと思います。 アラートを受け取った理由を教えてください。

### <a name="possible-machine-compromise"></a>コンピューターの侵害の可能性

- 組織内の多くのデバイスで"不明なプロセスが観察された" というメッセージまたはアラートが表示される理由を説明してください。 このメッセージまたはアラートが悪意のあるアクティビティに関連しているかどうかを明確にするために、ご意見をお願いします。
- 先週から交際している次のシステムで、侵害の可能性を検証するのに役立ちますか? これは、6 か月前に同じシステムで以前のマルウェア検出と同様に動作しています。

### <a name="threat-intelligence-details"></a>脅威インテリジェンスの詳細

- 悪意のある Word 文書をユーザーに配信したフィッシングメールが検出されました。 このドキュメントでは、一連の疑わしいイベントが発生し、特定のマルウェア ファミリに対して複数のアラートがトリガーされました。 このマルウェアに関する情報はありますか? はいの場合は、リンクを送信できますか?
- 最近、業界をターゲットにしている脅威に関するブログ投稿を見ました。 この脅威アクターに対してどのような保護Microsoft 365 Defender提供されるかを理解するのに役立ちますか?
- 最近、組織に対して行われたフィッシング キャンペーンを観察しました。 これが会社または垂直向けに特別にターゲットにされたかどうかをお聞かせください。

### <a name="microsoft-threat-experts-alert-communications"></a>Microsoft 脅威エキスパート' アラート通信

- インシデント対応チームは、ターゲットを絞った攻撃通知に対処するのに役立ちますか?
- Microsoft 脅威エキスパートからこの標的型攻撃通知を受け取った。 独自のインシデント対応チームはありません。 この時点でできることと、インシデントをどのように含めることができるか。
- Microsoft 脅威エキスパートから標的型攻撃通知を受け取った。 インシデント対応チームに渡すことができるデータは何ですか?

> [!NOTE]
> Microsoft 脅威エキスパートはマネージド脅威ハンティング サービスであり、インシデント対応サービスではありません。 ただし、独自のインシデント対応チームと連携して、インシデント対応が必要な問題に対処できます。 独自のインシデント対応チームがなく、Microsoft のサポートが必要な場合は、CSS サイバーセキュリティ インシデント対応チーム (CIRT) に参加できます。 問い合わせに対処するためにチケットを開くことができます。

## <a name="scenario"></a>シナリオ

### <a name="receive-a-progress-report-about-your-managed-hunting-inquiry"></a>マネージドハンティングの問い合わせに関する進行状況レポートを受け取る

Microsoft 脅威エキスパートからの回答は、お問い合わせによって異なります。 通常、次のいずれかの応答を受け取ります。

- 調査を続行するには、より多くの情報が必要です
- 技術的なコンテキストを決定するには、ファイルまたは複数のファイル サンプルが必要です
- 調査にはより多くの時間が必要です
- 調査を完了するのに十分な初期情報

専門家がより多くの情報やファイル サンプルを要求する場合は、調査を継続するために迅速に対応することが重要です。

## <a name="see-also"></a>関連項目

- [Microsoft 脅威エキスパートの概要](microsoft-threat-experts.md)
