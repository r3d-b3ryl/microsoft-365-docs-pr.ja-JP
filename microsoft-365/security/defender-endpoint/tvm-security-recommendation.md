---
title: セキュリティに関する推奨事項 (脅威と脆弱性の管理
description: 脅威、侵害される可能性、および価値に優先順位付けされた、アクション可能なセキュリティ脅威と脆弱性の管理。
keywords: 脅威と脆弱性の管理、Microsoft Defender for Endpoint tvm セキュリティ推奨事項、サイバーセキュリティの推奨事項、アクション可能なセキュリティ推奨事項
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 57c1909ff54fea6b9151e212f465abb75bab48f8
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63325321"
---
# <a name="security-recommendations---threat-and-vulnerability-management"></a>セキュリティに関する推奨事項 - 脅威と脆弱性の管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [脅威と脆弱性の管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)

組織内で特定されたサイバーセキュリティの弱点は、アクション可能なセキュリティ推奨事項にマップされ、影響によって優先順位が付けされます。 優先順位付けされた推奨事項は、脆弱性を軽減または修復し、コンプライアンスを推進する時間を短縮するのに役立ちます。

各セキュリティ推奨事項には、アクション可能な修復手順が含まれています。 タスクの管理を支援するために、推奨事項は、タスクの管理とMicrosoft IntuneをMicrosoft Endpoint Configuration Manager。 脅威の状況が変化すると、環境から情報を継続的に収集する際に、推奨事項も変更されます。

> [!TIP]
> 新しい脆弱性イベントに関する電子メールを取得するには、「 [Configure vulnerability email notifications in Microsoft Defender for Endpoint」を参照してください。](configure-vulnerability-email-notifications.md)

## <a name="how-it-works"></a>しくみ

組織内の各デバイスは、3 つの重要な要素に基づいてスコア付けされます。

- **脅威**: 組織のデバイスの脆弱性と悪用の特性と侵害履歴。 これらの要因に基づいて、セキュリティに関する推奨事項には、アクティブなアラート、継続的な脅威キャンペーン、対応する脅威分析レポートへの対応するリンクが表示されます。
- **侵害の可能性**: 組織のセキュリティ体制と脅威に対する回復力。
- **ビジネス価値**: 組織の資産、重要なプロセス、および知的財産。

## <a name="navigate-to-the-security-recommendations-page"></a>[セキュリティの推奨事項] ページに移動します。

[セキュリティの推奨事項] ページにアクセスするには、次のいくつかの方法があります。

- 脅威と脆弱性の管理ポータルのナビゲーション [Microsoft 365 Defenderメニュー](portal-overview.md)
- ダッシュボードのセキュリティに[関する脅威と脆弱性の管理おすすめ](tvm-dashboard-insights.md)

関連するセキュリティに関する推奨事項を次の場所で表示します。

- [ソフトウェア] ページ
- [デバイス] ページ

### <a name="navigation-menu"></a>[ナビゲーション] メニュー

[脆弱性管理] **ナビゲーション メニューに移動し** 、[推奨事項] **を選択します**。 このページには、組織で見つかった脅威と脆弱性に関するセキュリティ推奨事項の一覧が含まれている。

### <a name="top-security-recommendations-in-the-threat-and-vulnerability-management-dashboard"></a>ダッシュボードのセキュリティに関する脅威と脆弱性の管理おすすめ

セキュリティ管理者として特定の日に、[脅威と脆弱性の管理](tvm-dashboard-insights.md) ダッシュボードを見て、露出スコアを [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md) と並[](tvm-exposure-score.md)べて確認できます。 目標は、組織の脆弱性による露出を低くし、組織のデバイス セキュリティを強化して、サイバーセキュリティの脅威攻撃に対する回復力を高める方法です。 セキュリティに関する推奨事項の上位一覧は、その目標を達成するのに役立ちます。

![4 つのセキュリティ推奨事項を含むトップ セキュリティ推奨事項カードの例。](images/top-security-recommendations350.png)

上位のセキュリティ推奨事項は、前のセクションで説明した重要な要因 (脅威、侵害される可能性、および価値) に基づいて優先順位付けされた改善の機会を示しています。 推奨事項を選択すると、詳細を示すセキュリティの推奨事項ページが表示されます。

## <a name="security-recommendations-overview"></a>セキュリティに関する推奨事項の概要

推奨事項、見つかった弱点の数、関連するコンポーネント、脅威の分析情報、公開されているデバイスの数、状態、修復の種類、修復アクティビティ、露出スコアと Microsoft Secure Score for Devices への影響、および関連タグを表示します。

露出デバイスグラフの **色は** 、傾向の変化に合って変化します。 公開されているデバイスの数が増えている場合、色は赤に変わります。 公開されているデバイスの数が減った場合、グラフの色は緑に変わります。

> [!NOTE]
> 脅威と脆弱性の管理は、最大 30 日前に使用していた **デバイスを示** します。 これは、他の Microsoft Defender for Endpoint とは異なります。デバイスが 7 日間以上使用されていない場合は、"非アクティブ" 状態になっています。

![セキュリティに関する推奨事項のランディング ページの例。](images/tvmsecrec-updated.png)

### <a name="icons"></a>アイコン

役に立つアイコンは、次の点に注意を迅速に呼び出します。

- ![ターゲットに当たる矢印をクリックします。](images/tvm_alert_icon.png) 有効なアラートの可能性
- ![赤いバグ。](images/tvm_bug_icon.png) 関連するパブリックエクスプロイト
- ![電球。](images/tvm_insight_icon.png) 推奨事項の分析情報

### <a name="explore-security-recommendation-options"></a>セキュリティに関する推奨事項のオプションを確認する

調査または処理するセキュリティ推奨事項を選択します。

:::image type="content" alt-text="セキュリティ推奨事項のフライアウト ページの例。" source="images/secrec-flyouteolsw.png" lightbox="images/secrec-flyouteolsw.png":::

フライアウトから、次のオプションを選択できます。

- **[ソフトウェア ページを開** く] - ソフトウェア ページを開いて、ソフトウェアのコンテキストと配布方法を確認します。 この情報には、脅威コンテキスト、関連する推奨事項、検出された弱点、公開されたデバイスの数、検出された脆弱性、ソフトウェアがインストールされているデバイスの名前と詳細、バージョンの配布が含まれます。

- [**修復オプション**](tvm-remediation.md) - 修復要求を送信して、IT 管理者がMicrosoft Intuneアドレスを設定するためのチケットを開きます。 [修復] ページで修復アクティビティを追跡します。

- [**例外オプション**](tvm-exception.md) - まだ問題を修復できない場合は、例外を送信し、正当化を提供し、例外期間を設定します。

> [!NOTE]
> Windows、Linux、または macOS デバイスでソフトウェアの変更が行われた場合、通常、データがセキュリティ ポータルに反映されるのに 2 ~ 4 時間かかります。 iOS および Android デバイスの変更が反映されるには、最大 8 時間かかる場合があります。 時間がかかる場合があります。
> 
> 構成の変更には、4 ~ 24 時間かかる場合があります。

### <a name="investigate-changes-in-device-exposure-or-impact"></a>デバイスの露出や影響の変化を調査する

公開されているデバイスの数が大きく増加したり、組織の露出スコアや Microsoft Secure Score for Devices への影響が急激に増加する場合は、そのセキュリティ推奨事項を調査する価値があります。

1. 推奨事項と [ソフトウェアを開 **く] ページを選択する**
2. [イベント タイムライン **] タブを** 選択すると、新しい脆弱性や新しいパブリックエクスプロイトなど、そのソフトウェアに関連する影響を受けのあるすべてのイベントが表示されます。 [イベントタイムラインの詳細](threat-and-vuln-mgt-event-timeline.md)
3. 修復要求の提出など、増加または組織の露出に対処する方法を決定する

## <a name="request-remediation"></a>修復の要求

修復脅威と脆弱性の管理機能は、修復要求ワークフローを通じてセキュリティ管理者と IT 管理者の間のギャップを埋め合わせています。 IT 管理者に対して、セキュリティの推奨事項ページから Intune への脆弱性の修復を要求できるセキュリティ管理者。 [修復オプションの詳細](tvm-remediation.md)

### <a name="how-to-request-remediation"></a>修復を要求する方法

修復を要求するセキュリティ推奨事項を選択し、[修復オプション] **を選択します**。 フォームに入力し、[要求の送信] **を選択します**。 [修復] [**ページに**](tvm-remediation.md) 移動して、修復要求の状態を表示します。 [修復を要求する方法の詳細](tvm-remediation.md#request-remediation)

## <a name="file-for-exception"></a>例外ファイル

推奨事項が現時点では関連しない場合の修復要求の代わりに、推奨事項の例外を作成できます。 [例外の詳細](tvm-exception.md)

"例外処理" アクセス許可を持つユーザーだけが例外を追加できます。 [RBAC の役割について詳しくは、次のページを参照してください](user-roles.md)。

推奨事項に対して例外が作成されると、推奨事項はアクティブではなくなりました。 推奨事項の状態が [完全な例外] **または [部分的な** 例外] (デバイス **グループ** 別) に変更されます。

### <a name="how-to-create-an-exception"></a>例外を作成する方法

例外を作成するセキュリティ推奨事項を選択し、[例外オプション] **を選択します**。

!["例外オプション" のボタンがセキュリティ推奨事項のフライアウト内の場所である場所を表示します。](images/tvm-exception-options.png)

フォームに入力して送信します。 すべての例外 (現在と過去) を表示するには、[脅威 **&** の脆弱性管理] メニューの [修復] ページに移動し、[例外]  タブを選択します [](tvm-exception.md#create-an-exception)。例外を作成する方法の詳細については、以下を参照してください。[](tvm-remediation.md)

## <a name="report-inaccuracy"></a>レポートの不正確さ

あいまいで不正確、不完全、または既に修復済みのセキュリティ推奨情報が表示された場合は、誤検知を報告できます。

1. セキュリティの推奨事項を開きます。

2. 報告するセキュリティ推奨事項の横にある 3 つの点を選択し、[不正確なレポート] **を選択します**。

    ![[不正確なレポート] ボタンがセキュリティ推奨事項のフライアウト内にある場所を表示します。](images/report-inaccuracy500.png)

3. フライアウト ウィンドウで、ドロップダウン メニューから不正確なカテゴリを選択し、電子メール アドレスを入力し、不正確に関する詳細を入力します。

4. **[送信]** を選択します。 フィードバックはすぐに専門家に脅威と脆弱性の管理されます。

## <a name="related-articles"></a>関連記事

- [脅威と脆弱性の管理概要](next-gen-threat-and-vuln-mgt.md)
- [ダッシュボード](tvm-dashboard-insights.md)
- [暴露スコア](tvm-exposure-score.md)
- [デバイス向けの Microsoft セキュア スコア](tvm-microsoft-secure-score-devices.md)
- [脆弱性を修復する](tvm-remediation.md)
- [セキュリティに関する推奨事項の例外を作成および表示する](tvm-exception.md)
- [イベントのタイムライン](threat-and-vuln-mgt-event-timeline.md)
