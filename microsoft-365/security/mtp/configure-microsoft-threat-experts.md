---
title: Microsoft 365 Defender を使用して Microsoft Threat Experts の機能を構成および管理する
description: Microsoft 365 Defender を通じて Microsoft Threats Experts にサブスクライブし、毎日のセキュリティ操作とセキュリティ管理作業で構成、管理、および使用します。
keywords: Microsoft Threat Experts, managed Threat Hunting Service, MTE, Microsoft マネージ ハンティング サービス
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
ms.openlocfilehash: 93e900423fcef1fd357ca50db70e250ef6082dc7
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570580"
---
# <a name="configure-and-manage-microsoft-threat-experts-capabilities-through-microsoft-365-defender"></a>Microsoft 365 Defender を使用して Microsoft Threat Experts の機能を構成および管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Prerelease](../includes/prerelease.md)]

## <a name="before-you-begin"></a>開始する前に

> [!IMPORTANT]
> 適用する前に、Microsoft Technical Service プロバイダーとアカウント チームと一緒に、Microsoft Threat Experts - Targeted Attack Notifications マネージ脅威ハンティング サービスの適格性要件について説明してください。

標的型攻撃通知を受信するには、デバイスが登録された Microsoft 365 Defender を展開する必要があります。 次に、M365 ポータルから Microsoft Threat Experts - ターゲット攻撃通知のアプリケーションを送信します。

Microsoft Threat Experts - Experts on Demand を購読するには、アカウント チームまたは Microsoft 担当者にお問い合わせください。 オンデマンドの専門家は、関連する検出や敵対者から組織を保護する方法について、脅威の専門家と相談できます。

## <a name="apply-for-microsoft-threat-experts---targeted-attack-notifications-service"></a>Microsoft Threat Experts - ターゲット攻撃通知サービスに適用する

Microsoft Defender for Endpoint と Microsoft 365 Defender を既に持っている場合は、Microsoft 365 Defender ポータルを通じて Microsoft Threat Experts – Targeted Attack Notifications を申請できます。  標的型攻撃通知は、組織にとって最も重要な脅威を特定するのに役立つ特別な洞察と分析を提供し、迅速に対応できます。

1. ナビゲーション ウィンドウから、[エンドポイントの設定] > Microsoft Threat Experts > **>高度>に移動します**。

2. **[適用]** を選択します。

    ![Microsoft Threat Experts の設定のイメージ](../../media/mte/mte-collaboratewithmte.png)

3. Microsoft がアプリケーションについて連絡できるよう、名前とメール アドレスを入力します。

    ![Microsoft Threat Experts アプリケーションのイメージ](../../media/mte/mte-apply.png)

4. プライバシーに [関する声明を読み](https://privacy.microsoft.com/en-us/privacystatement)、完了 **したら [送信** ] を選択します。 アプリケーションが承認されると、ウェルカム メールが届きます。

    ![Microsoft Threat Experts アプリケーション確認のイメージ](../../media/mte/mte-applicationconfirmation.png)

5. ウェルカム メールを受信すると、ターゲット攻撃通知の受信が自動的に開始されます。

6. [設定] ページの [エンドポイント] ページの [全般> **詳細>を>確認できます**。 承認されると **、Microsoft Threat Experts - ターゲット攻撃通知** トグルが表示され、[オン] に切り替 **わるようになります**。

## <a name="where-youll-see-the-targeted-attack-notifications-from-microsoft-threat-experts"></a>Microsoft Threat Experts からのターゲット攻撃通知が表示される場所

次のメディアを使用して、Microsoft Threat Experts から標的型攻撃通知を受け取ります。

- Microsoft 365 Defender ポータルの **[インシデント] ページ**
- Microsoft 365 Defender ポータルの **アラート** ダッシュボード
- OData アラート [API と](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/get-alerts) REST [API](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/pull-alerts-using-rest-api)
- [高度な検索の DeviceAlertEvents](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-devicealertevents-table) テーブル
- 電子メールを介してターゲット攻撃通知を送信する場合は、受信トレイ。 以下の [「電子メール通知ルールを作成する」を](#create-an-email-notification-rule) 参照してください。

### <a name="create-an-email-notification-rule"></a>電子メール通知ルールの作成

通知受信者の電子メール通知を送信するルールを作成できます。 詳細については、「アラート通知を  [構成して](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-email-notifications) 電子メール通知を作成、編集、削除、またはトラブルシューティングする」を参照してください。

## <a name="view-targeted-attack-notifications"></a>ターゲット攻撃の通知を表示する

電子メール通知を受信するようにシステムを構成した後、電子メールで Microsoft Threat Experts から標的型攻撃通知の受信を開始します。

1. メール内のリンクを選択して、脅威の専門家とタグ付けされたダッシュボードの対応するアラート コンテキスト **に移動します**。

2. [アラート **] ページ** で、電子メールで受信したアラート トピックと同じアラート トピックを選択して、詳細を表示します。

## <a name="subscribe-to-microsoft-threat-experts---experts-on-demand"></a>Microsoft Threat Experts の購読 - エキスパート オンデマンド

Microsoft Defender for Endpoint のお客様が既に存在する場合は、Microsoft の担当者に問い合わせ、Microsoft Threat Experts - Experts on Demand を購読できます。

## <a name="consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization"></a>組織内の疑わしいサイバーセキュリティアクティビティについて Microsoft の脅威専門家に相談する

Microsoft 365 Defender ポータル内から Microsoft Threat Experts に問い合わせできます。 専門家は、複雑な脅威や標的型攻撃の通知を理解するのに役立ちます。 アラートやインシデントに関する詳細、または侵害の処理に関するアドバイスについては、専門家と提携してください。 ポータル ダッシュボードで説明されている脅威インテリジェンス コンテキストに関する分析情報を取得します。

> [!NOTE]
>
> - 組織のカスタマイズされた脅威インテリジェンス データに関連するアラートの問い合わせは現在サポートされていません。 詳細については、セキュリティ操作またはインシデント対応チームに問い合わせください。
> - Microsoft 365 Defender ポータルの [セキュリティ センターのセキュリティ設定の管理] アクセス許可を持って、[脅威の専門家に相談する] フォームから問い合わせを **送信する必要** があります。 

1. 調査する情報 (デバイス、アラート、インシデントなど) に関連するポータル **ページに移動****します**。 調査要求を送信する前に、問い合わせに関連するポータル ページが表示されている必要があります。

2. トップ メニューから **[?脅威の専門家に相談してください**。

    ![メニューから Microsoft Threat Experts Experts on Demand のイメージ](../../media/mte/incidents-action-mte-highlighted.png)

    フライアウト画面が開きます。

    このヘッダーには、試用版サブスクリプションか、Microsoft Threat Experts - Experts on-Demand サブスクリプションの完全版が表示されます。

    ![Microsoft Threat Experts Experts on Demand 試用版サブスクリプション画面の画像](../../media/mte/mte-trial.png)

    [ **調査] トピック** フィールドには、要求の関連ページへのリンクが既に入力されています。

3. 次のフィールドで、調査を開始するのに十分なコンテキストを Microsoft Threat Experts に提供するのに十分な情報を提供します。

4. Microsoft Threat Experts に対応するために使用するメール アドレスを入力します。

> [!NOTE]
> Microsoft Services Hub を通じてエキスパート オンデマンド ケースの状態を追跡する場合は、テクニカル アカウント マネージャーに連絡してください。

Microsoft Services Hub の概要については、このビデオをご覧ください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4pk9f]

## <a name="sample-investigation-topics"></a>調査のサンプル トピック

### <a name="alert-information"></a>アラート情報

- 新しい種類のアラートが、生きている土地のバイナリに対して表示されます。 アラート ID を指定できます。 このアラートの詳細と、さらに詳しく調査する方法を教えてください。
- 同様の攻撃が 2 つ見られたので、どちらも悪意のある PowerShell スクリプトを実行しようとするが、異なるアラートを生成します。 1 つは "不審な PowerShell コマンド ライン" で、もう 1 つは "O365 によって提供される指示に基づいて悪意のあるファイルが検出されました" です。 違いは何ですか?
- 今日、知名度の高いユーザーのデバイスから失敗したログインの異常数に関する奇数の警告を受け取りました。 これらの試みについてのそれ以上の証拠は見つからん。 Microsoft 365 Defender でこれらの試みを確認する方法 監視対象のログインの種類
- 「システム ユーティリティによる疑わしい動作が観察されました」というアラートに関するコンテキストや分析情報を追加できますか?
- "転送/リダイレクト ルールの作成" というタイトルのアラートが表示されました。 アクティビティは良性だと思います。 通知を受け取った理由を教えてください。

### <a name="possible-machine-compromise"></a>コンピューターの侵害の可能性

- 組織内の多くのデバイスで「不明なプロセスが観察された」というメッセージや警告が表示される理由を説明できますか? このメッセージまたはアラートが悪意のあるアクティビティに関連するかどうかを明確にするための任意の入力に感謝します。
- 次のシステムで、先週から発生した可能性がある侵害の検証に役立ちますか? これは、6 か月前に同じシステムで以前のマルウェア検出と同様に動作します。

### <a name="threat-intelligence-details"></a>脅威インテリジェンスの詳細

- 悪意のある Word 文書をユーザーに配信したフィッシングメールが検出されました。 このドキュメントでは、一連の疑わしいイベントが発生し、特定のマルウェア ファミリに対して複数のアラートが発生しました。 このマルウェアに関する情報はありますか? はいの場合、リンクを送信できますか?
- 最近、業界をターゲットにしている脅威に関するブログ投稿を見ました。 この脅威アクターに対して Microsoft 365 Defender が提供する保護を理解するのに役立ちますか?
- 最近、組織に対して行われたフィッシング キャンペーンを確認しました。 これは、特に当社または垂直に対象とされたのか教えてください。

### <a name="microsoft-threat-experts-alert-communications"></a>Microsoft Threat Experts のアラート通信

- インシデント対応チームは、対象となる攻撃通知に対処するのに役立ちますか?
- Microsoft Threat Experts からこの標的型攻撃の通知を受け取った。 独自のインシデント対応チームは持ち合わせください。 ここで何を行い、インシデントを含めるのか。
- Microsoft Threat Experts から標的型攻撃の通知を受け取った。 インシデント対応チームに渡すデータを提供できますか?

> [!NOTE]
> Microsoft Threat Experts は、インシデント対応サービスではなく、管理された脅威検出サービスです。 ただし、専門家は必要に応じて、調査を Microsoft サイバーセキュリティ ソリューション グループ (CSG) の検出および応答チーム (DART) サービスにシームレスに移行できます。 また、インシデント対応チームと関わり、インシデント対応が必要な問題に対処できます。

## <a name="scenario"></a>シナリオ

### <a name="receive-a-progress-report-about-your-managed-hunting-inquiry"></a>管理された狩猟に関する問い合わせに関する進行状況レポートを受け取る

Microsoft Threat Experts からの応答は、お問い合わせに応じて異なります。 通常、次のいずれかの応答を受け取る必要があります。

- 調査を続行するには、さらに詳しい情報が必要です。
- 技術的なコンテキストを決定するには、ファイルまたは複数のファイル サンプルが必要です
- 調査にはより多くの時間が必要
- 最初の情報は、調査を終了するのに十分でした

専門家が詳細な情報やファイル サンプルを要求する場合は、調査の動きを維持するために迅速に対応することが重要です。

## <a name="see-also"></a>関連項目

- [Microsoft Threat Experts の概要](microsoft-threat-experts.md)
