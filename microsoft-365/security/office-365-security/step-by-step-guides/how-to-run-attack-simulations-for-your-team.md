---
title: チームの攻撃シミュレーションを実行する方法
description: トレーニングのために、攻撃シミュレーション ペイロードをチームまたは組織のターゲット ユーザーに送信する手順。 シミュレートされた攻撃は、実際の攻撃が組織に影響を与える前に、脆弱なユーザー、ポリシー、およびプラクティスを特定して見つけるのに役立ちます。
search.product: ''
search.appverid: ''
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-guidance-templates
ms.topic: how-to
ms.technology: mdo
ms.openlocfilehash: d3ce22386d0ebde6dbc3035056b683894cdd6131
ms.sourcegitcommit: 7e551fa4e9b8b25ed62b5f406143b6b1dae08cbf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2022
ms.locfileid: "67107373"
---
# <a name="how-to-run-attack-simulations-for-your-team"></a>チームの攻撃シミュレーションを実行する方法

攻撃シミュレーション トレーニングを使用すると、組織内で現実的で無害なサイバー攻撃シナリオを実行できます。 シミュレートされた攻撃は、実際の攻撃が組織に影響を与える前に、脆弱なユーザー、ポリシー、およびプラクティスを特定し、見つけるのに役立ちます。組み込みトレーニングまたはカスタム トレーニングを利用して、リスクを軽減し、脅威に関するエンド ユーザーの教育を向上させることができます。

## <a name="what-youll-need"></a>必要なもの

- Microsoft Defender for Office 365 プラン 2 (E5 の一部として含まれる)
- 十分なアクセス許可 (セキュリティ管理者ロール)
- 次の手順を実行するには、5 分から 10 分かかります。

## <a name="send-a-payload-to-target-users"></a>ターゲット ユーザーにペイロードを送信する

1. サブスクリプションの [攻撃シミュレーション トレーニング](https://security.microsoft.com/attacksimulator ) に移動します。
1. 上部のナビゲーション バーから **[シミュレーション** ] を選択します。
1. [ **シミュレーションの起動] を選択します**。
1. ポップアップから使用する手法を選択し、 **次へ** キーを押します。
1. 関連するものや思い出に残る名前を付けて、 **次へ** キーを押します。
1. ウィザードから関連するペイロードを選択し、詳細を確認し、必要に応じてカスタマイズします。選択に問題がなければ、[ **次へ**] を押します。
1. ペイロードでターゲットを設定するユーザーを選択します。 組織全体を選択する場合は、ラジオ ボタンを強調表示し、[ **次へ**] を押します。
1. それ以外の場合 **は、[ユーザーの追加]** を選択し、ウィザードでユーザーを検索またはフィルター処理します。 [ユーザーの追加] を選択し、[ **次へ**] を選択します。
1. [ **トレーニング コンテンツの選択] 基本設定** で、既定の *Microsoft トレーニング エクスペリエンス (推奨)* のままにするか、 *カスタム URL を使用する場合は [カスタム URL にリダイレクト* ] を選択します。 トレーニングを割り当てたくない場合は、[トレーニング *なし*] を選択します。
    - [トレーニングの割り当て] を選択して Microsoft にトレーニング コースを *割り当て* させるか、自分で *トレーニング コースとモジュールを選択して特定のモジュールを* 選択できます。
    - ドロップダウン メニューから期限 (30、15、または 7 日間) を選択します。
    - 続行するには、**[次へ]** をクリックします。
1. 必要に応じて、ユーザーがフィッシングされた場合に表示されるランディング ページをカスタマイズするか、Microsoft Default のままにします。
    1. [ **ペイロード インジケーター**] で、電子メールにペイロード インジケーターを追加するチェック ボックスをオンにします。 ペイロードを追加すると、ユーザーはフィッシングメールを識別する方法を学習するのに役立ちます。 [ *プレビュー パネルを開く]* を選択してメッセージを表示します。
    1. 続行するには、**[次へ]** をクリックします。
1. エンド ユーザー通知を希望するかどうかを選択し、その場合は配信設定を選択し、必要に応じてカスタマイズします。
    1. [ *既定の言語* の選択] ドロップダウン メニューで、通知の **既定の言語を選択** することもできます。
1. シミュレーションをいつ起動するか、および有効にする必要がある期間を選択します。 *リージョン対応のタイム ゾーン配信* を有効にすることもできます。 このオプションは、従業員の地域に基づいて *、勤務時間* 中にシミュレートされた攻撃メッセージを従業員に配信します。 **[次へ]** を選択します。
1. 準備ができたら、テストを送信します。 選択肢の概要を確認します。 [**送信**] をクリックします。

### <a name="further-reading"></a>その他の読み取り

攻撃シミュレーションのしくみについては、「攻撃シミュレーション [トレーニングを使用してフィッシング攻撃をシミュレートする - Office 365 |Microsoft Docs](../../office-365-security/attack-simulation-training.md)