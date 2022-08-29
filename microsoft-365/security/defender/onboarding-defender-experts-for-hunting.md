---
title: ハンティング用の Microsoft Defender エキスパートをサブスクライブする方法
ms.reviewer: ''
description: Microsoft 365 Defenderおよび Defender Experts for Hunting を初めて使用する場合は、これがサブスクライブ方法です
keywords: マネージド脅威ハンティング サービス、マネージド脅威ハンティング、マネージド検出と応答 (MDR) サービス、MTE、Microsoft 脅威エキスパート、MTE-TAN、ターゲット攻撃通知、Defender エキスパート通知、エンドポイント攻撃通知、Microsoft Defender エキスパートの捜索、脅威の捜索と分析。
search.product: Windows 10
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: vpattnaik
author: vpattnai
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 5165adfd402415ddd7bd5a0fd6b5acb098fd49f1
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67328455"
---
# <a name="start-using-microsoft-defender-experts-for-hunting"></a>ハンティングに Microsoft Defender エキスパートの使用を開始する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="onboarding"></a>オンボード

Microsoft 365 Defenderおよび Defender Experts for Hunting を初めて使用する場合:  

1. ウェルカム メールを受け取ったら、[**Microsoft 365 Defenderにログイン**] を選択します。
2. Microsoft アカウントを既に持っている場合はサインインします。 存在しない場合は、作成します。
3. Microsoft 365 Defenderクイック ツアーでは、セキュリティ スイートの機能とその重要性について理解します。 [ **クイック ツアーを行う**] を選択します。  
4. Microsoft Defender エキスパート サービスの概要と、Microsoft Defender エキスパート サービスが提供する機能に関する簡単な説明を参照してください。 [**次へ**] を選択します。 ウェルカム ページが表示されます。

![Defender Experts for Hunting サービス用のカードを含むMicrosoft 365 Defenderウェルカム ページのスクリーンショット。](../../media/mte/defenderexperts/start-using-defender-experts-for-hunting.png)

## <a name="receive-defender-experts-notifications"></a>Defender エキスパートの通知を受け取る

Defender Experts Notification サービスには、次のものが含まれます。
- 脅威の監視と分析、居住時間の短縮、ビジネスへのリスクの削減
- 既知の攻撃と新たな脅威の両方を検出してターゲットにする、狩人がトレーニングした人工知能 
- 最も関連するリスクを特定し、SOC の有効性を最大化するのに役立ちます 
- 迅速な SOC 対応を可能にするために、侵害の範囲を絞り込み、できるだけ多くのコンテキストを迅速に提供するのに役立ちます 

次のスクリーンショットを参照して、Defender エキスパート通知のサンプルを確認してください。

![Microsoft 365 Defenderの Defender エキスパート通知のスクリーンショット。 Defender Expert Notification には、観察された脅威またはアクティビティ、エグゼクティブ サマリー、推奨事項の一覧を説明するタイトルが含まれています。](../../media/mte/defenderexperts/receive-defender-experts-notification.png)

### <a name="where-youll-find-defender-experts-notifications"></a>Defender エキスパート通知の場所

Defender エキスパートからの Defender エキスパート通知は、次のメディアから受け取ることができます。 

- Microsoft 365 Defender ポータルの [[インシデント]](https://security.microsoft.com/incidents?tid=f839b112-d9d7-4d27-9bf6-94542403f21c) ページ
- Microsoft 365 Defender ポータルの [[アラート]](https://security.microsoft.com/alerts?tid=f839b112-d9d7-4d27-9bf6-94542403f21c) ページ
- OData アラート [API](../../security/defender-endpoint/get-alerts.md) と [REST API](../defender-endpoint/configure-siem.md)
- 高度なハンティングの [DeviceAlertEvents](../../security/defender-endpoint/advanced-hunting-devicealertevents-table.md) テーブル

### <a name="filter-to-view-just-the-defender-experts-notifications"></a>Defender エキスパート通知のみを表示するフィルター

多数のアラートのうち Defender エキスパート通知のみを表示する場合は、インシデントとアラートをフィルター処理できます。 そのためには、次を実行します。

1. ナビゲーション メニューの [**インシデント&アラート** > **インシデント**] に移動>、[フィルター] アイコン](../../media/mte/defenderexperts/filter.png) アイコンを![選択します。
2. [ **タグ** ] フィールドまで下にスクロール> **、[Defender エキスパート** ] チェック ボックスをオンにします。
3. **[適用]** を選択します。

### <a name="collaborate-with-experts-on-demand"></a>エキスパートとオンデマンドで共同作業する

> [!NOTE]
> オンデマンドエキスパートは、毎月割り当てられた Defender Experts for Hunting サブスクリプションに含まれています。 ただし、セキュリティ インシデント対応サービスではありません。 これは、組織に影響を与える複雑な脅威をより深く理解することを目的としています。 独自のセキュリティ インシデント対応チームと連携して、緊急のセキュリティ インシデント対応の問題に対処します。 独自のセキュリティ インシデント対応チームがなく、Microsoft のサポートを希望する場合は、 [Premier Services Hub](/services-hub/) でサポート リクエストを作成します。

Microsoft 365 セキュリティ ポータル内で **Defender エキスパートに直接問い合わせて** 、脅威の捜索に関するすべての質問に迅速かつ正確に対応します。 専門家は、組織が直面する可能性のある複雑な脅威をよりよく理解するための分析情報を提供できます。 オンデマンドのエキスパートは、次の作業に役立ちます。 

- 根本原因やスコープなど、アラートとインシデントに関する追加情報を収集する
- 疑わしいデバイス、アラート、またはインシデントを明確にし、高度な攻撃者に直面した場合は次の手順を実行する
- 脅威アクター、キャンペーン、または新たな攻撃者手法に関連するリスクと使用可能な保護を決定する

**Defender エキスパートに質問** するオプションは、ポータル全体で複数の場所で使用できます。

- ***[デバイス ページのアクション] メニュー***

![Microsoft 365 Defender ポータルの [デバイス] ページアクション メニューの [Defender エキスパートに問い合わせ] メニュー オプションのスクリーンショット。](../../media/mte/defenderexperts/device-page-actions-menu.png)

- ***[デバイス インベントリ] ページのポップアップ メニュー***

![Microsoft 365 Defender ポータルの [デバイス インベントリ] ページのポップアップ メニューの [Defender エキスパートに問い合わせ] メニュー オプションのスクリーンショット。](../../media/mte/defenderexperts/device-inventory-flyout-menu.png)

- ***[アラート] ページのポップアップ メニュー***

![Microsoft 365 Defender ポータルの [アラート] ページのポップアップ メニューの [Defender エキスパートに問い合わせ] メニュー オプションのスクリーンショット。](../../media/mte/defenderexperts/alerts-flyout-menu.png)

- ***[インシデント] ページの [アクション] メニュー***

![Microsoft 365 Defender ポータルの [インシデント] ページの [アクション] メニューの [Defender エキスパートに問い合わせ] メニュー オプションのスクリーンショット。](../../media/mte/defenderexperts/incidents-page-actions-menu.png)

> [!NOTE]
> Microsoft Services Hub を通じてエキスパート オンデマンド ケースの状態を追跡する場合は、カスタマー サクセス アカウント マネージャーにお問い合わせください。 Microsoft Services Hub の概要については、この [ビデオ](https://www.microsoft.com/videoplayer/embed/RE4pk9f) をご覧ください。

## <a name="sample-questions-you-can-ask-from-defender-experts"></a>Defender エキスパートから質問できるサンプルの質問

### <a name="alert-information"></a>アラート情報

- 新しい種類のアラートが、ライブオフのバイナリに対して見えました。 アラート ID を指定できます。 このアラートの詳細と、インシデントに関連するかどうか、さらに調査する方法を教えてください。
- 2 つの同様の攻撃が観察されました。どちらも悪意のある PowerShell スクリプトを実行しようとしましたが、異なるアラートを生成します。 1 つは "疑わしい PowerShell コマンド ライン" で、もう 1 つは "Office 365 によって提供された指示に基づいて悪意のあるファイルが検出されました" です。 違いは何ですか?
- 今日、高プロファイル ユーザーのデバイスから、失敗したログインの異常な数に関する奇数のアラートを受け取った。 これらの試みについてそれ以上の証拠を見つけることができません。 これらの試みをMicrosoft 365 Defenderはどのように確認できますか? 監視対象のログインの種類は何ですか?
- アラートに関するより多くのコンテキストや分析情報、および関連するインシデント ("システム ユーティリティによる疑わしい動作が観察されました") を提供できますか?
- "転送/リダイレクト ルールの作成" というタイトルのアラートを観察しました。 アクティビティは問題ないと思います。 アラートを受け取った理由を教えてください。

### <a name="possible-device-compromise"></a>デバイスの侵害の可能性

- 組織内の多くのデバイスで"不明なプロセスが観察された" というメッセージまたはアラートが表示される理由を説明してください。 このメッセージまたはアラートが悪意のあるアクティビティまたはインシデントに関連しているかどうかを明確にするために、ご意見をお願いします。
- 先週から交際している次のシステムで、侵害の可能性を検証するのに役立ちますか? これは、6 か月前に同じシステムで以前のマルウェア検出と同様に動作しています。

### <a name="threat-intelligence-details"></a>脅威インテリジェンスの詳細

- 悪意のある Word 文書をユーザーに配信したフィッシングメールが検出されました。 このドキュメントでは、一連の疑わしいイベントが発生し、特定のマルウェア ファミリに対して複数のアラートがトリガーされました。 このマルウェアに関する情報はありますか? はいの場合は、リンクを送信できますか?
- 最近、業界をターゲットにしている脅威に関するブログ投稿を見ました。 この脅威アクターに対してどのような保護Microsoft 365 Defender提供されるかを理解するのに役立ちますか?
- 最近、組織に対して行われたフィッシング キャンペーンを観察しました。 これが会社または垂直向けに特別にターゲットにされたかどうかをお聞かせください。

### <a name="microsoft-defender-experts-for-hunting-alert-communications"></a>ハンティングの Microsoft Defender エキスパートのアラート通信

- インシデント対応チームは、私たちが受け取った Defender エキスパート通知に対処するのに役立ちますか?
- Microsoft Defender Experts for Hunting からこの Defender エキスパート通知を受け取っています。 独自のインシデント対応チームはありません。 この時点でできることと、インシデントをどのように含めることができるか。
- Microsoft Defender Experts for Hunting から Defender エキスパート通知を受け取った。 インシデント対応チームに渡すことができるデータは何ですか?

### <a name="next-step"></a>次のステップ

- [Microsoft 365 Defenderの Defender Experts for Hunting レポートを理解する](defender-experts-report.md)
