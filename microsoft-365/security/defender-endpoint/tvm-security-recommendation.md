---
title: 脅威と脆弱性の管理によるセキュリティに関する推奨事項
description: 脅威と脆弱性の管理で、脅威、侵害される可能性、価値によって優先順位付けされた実用的なセキュリティ推奨事項を取得します。
keywords: 脅威と脆弱性の管理、Microsoft Defender for Endpoint tvm セキュリティに関する推奨事項、サイバーセキュリティの推奨事項、実用的なセキュリティに関する推奨事項
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
ms.openlocfilehash: e7ff7a98e8550996068686b5b0805ea3a72cd6ae
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64468569"
---
# <a name="security-recommendations---threat-and-vulnerability-management"></a>セキュリティに関する推奨事項 - 脅威と脆弱性の管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [脅威と脆弱性の管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)

組織で特定されたサイバーセキュリティの弱点は、実用的なセキュリティ推奨事項にマップされ、その影響によって優先順位が付けられます。 優先順位付けされた推奨事項は、脆弱性を軽減または修復し、コンプライアンスを促進するための時間を短縮するのに役立ちます。

各セキュリティ推奨事項には、実用的な修復手順が含まれています。 タスク管理を支援するために、Microsoft IntuneとMicrosoft Endpoint Configuration Managerを使用して推奨事項を送信することもできます。 脅威の状況が変わると、環境から情報が継続的に収集されるため、推奨事項も変更されます。

> [!TIP]
> 新しい脆弱性イベントに関する電子メールを取得するには、「[Microsoft Defender for Endpointで脆弱性の電子メール通知を構成](configure-vulnerability-email-notifications.md)する」を参照してください。

## <a name="how-it-works"></a>メカニズム

組織内の各デバイスは、顧客が適切なタイミングで適切な事柄に集中するのに役立つ 3 つの重要な要素に基づいてスコア付けされます。

- **脅威**: 組織のデバイスおよび侵害履歴における脆弱性と悪用の特性。 これらの要因に基づいて、セキュリティに関する推奨事項には、アクティブなアラート、進行中の脅威キャンペーン、および対応する脅威分析レポートへの対応するリンクが表示されます。
- **侵害の可能性**: 組織のセキュリティ体制と脅威に対する回復性。
- **ビジネス価値**: 組織の資産、重要なプロセス、および知的財産。

## <a name="navigate-to-the-security-recommendations-page"></a>[セキュリティに関する推奨事項] ページに移動する

[セキュリティに関する推奨事項] ページには、いくつかの異なる方法があります。

- [Microsoft 365 Defender ポータル](portal-overview.md)の [脅威と脆弱性の管理] ナビゲーション メニュー
- [脅威と脆弱性の管理 ダッシュボード](tvm-dashboard-insights.md)の主要なセキュリティに関する推奨事項

関連するセキュリティに関する推奨事項を次の場所に表示します。

- [ソフトウェア] ページ
- [デバイス] ページ

### <a name="navigation-menu"></a>[ナビゲーション] メニュー

**[脆弱性管理**] ナビゲーション メニューに移動し、**おすすめ** を選択します。 このページには、組織で見つかった脅威と脆弱性に関するセキュリティに関する推奨事項の一覧が含まれています。

### <a name="top-security-recommendations-in-the-threat-and-vulnerability-management-dashboard"></a>脅威と脆弱性の管理 ダッシュボードの主要なセキュリティに関する推奨事項

特定の日にセキュリティ管理者として、[脅威と脆弱性の管理 ダッシュボード](tvm-dashboard-insights.md)を見て、[デバイスの Microsoft Secure Score](tvm-microsoft-secure-score-devices.md) と共に[露出スコア](tvm-exposure-score.md)を確認できます。 目標は、組織の脆弱性からの露出を **減らして** 、組織のデバイス セキュリティを高め、サイバーセキュリティの脅威攻撃に対する回復性を **高げること** です。 セキュリティに関する推奨事項のトップ リストは、その目標を達成するのに役立ちます。

:::image type="content" source="images/top-security-recommendations350.png" alt-text="セキュリティに関する推奨事項の上位カード" lightbox="images/top-security-recommendations350.png":::


セキュリティに関する推奨事項の上位には、前のセクションで説明した重要な要因 (脅威、侵害される可能性、価値) に基づいて、改善の機会が優先されます。 推奨事項を選択すると、セキュリティの推奨事項ページに詳細が表示されます。

## <a name="security-recommendations-overview"></a>セキュリティに関する推奨事項の概要

推奨事項、検出された弱点の数、関連コンポーネント、脅威分析情報、公開されたデバイスの数、状態、修復の種類、修復アクティビティ、露出スコアと Microsoft Secure Score for Devices への影響、および関連タグを表示します。

**露出デバイス** グラフの色は、傾向が変化するにつれて変化します。 公開されているデバイスの数が増加している場合、色は赤に変わります。 公開されているデバイスの数が減少した場合、グラフの色は緑色に変わります。

> [!NOTE]
> 脅威と脆弱性の管理には、最大 **30 日前** に使用されていたデバイスが表示されます。 これは、デバイスが 7 日を超えて使用されていない場合に "非アクティブ" 状態になっている他のMicrosoft Defender for Endpointとは異なります。

:::image type="content" source="images/tvmsecrec-updated.png" alt-text="セキュリティに関する推奨事項のランディング ページ" lightbox="images/tvmsecrec-updated.png":::

### <a name="icons"></a>アイコン

便利なアイコンは、次の項目に対する注意もすぐに呼び出します。

- ![矢印がターゲットに当たっている。](images/tvm_alert_icon.png) アクティブなアラートの可能性
- ![赤のバグ。](images/tvm_bug_icon.png) 関連するパブリックエクスプロイト
- ![電球。](images/tvm_insight_icon.png) 推奨事項の分析情報

### <a name="explore-security-recommendation-options"></a>セキュリティに関する推奨事項のオプションを確認する

調査または処理するセキュリティに関する推奨事項を選択します。

:::image type="content" source="images/secrec-flyouteolsw.png" alt-text="セキュリティに関する推奨事項のポップアップ ページ" lightbox="images/secrec-flyouteolsw.png":::

ポップアップから、次のいずれかのオプションを選択できます。

- **[ソフトウェアを開く] ページ** - ソフトウェア ページを開いて、ソフトウェアとその配布方法に関するより多くのコンテキストを取得します。 この情報には、脅威コンテキスト、関連する推奨事項、検出された弱点、公開されたデバイスの数、検出された脆弱性、ソフトウェアがインストールされているデバイスの名前と詳細、バージョンの配布などがあります。

- [**修復オプション**](tvm-remediation.md) - 修復要求を送信して、IT 管理者が受け取って対処するためのチケットをMicrosoft Intuneで開きます。 修復ページで修復アクティビティを追跡します。

- [**例外オプション**](tvm-exception.md) - 問題をまだ修復できない場合は、例外を送信し、理由を指定し、例外期間を設定します。

> [!NOTE]
> Windows、Linux、または macOS デバイスでソフトウェアの変更が行われると、通常、データがセキュリティ ポータルに反映されるまでに 2 ~ 4 時間かかります。 iOS および Android デバイスの変更が反映されるまでには、最大で 8 時間かかる場合があります。 時間がかかる場合があります。
> 
> 構成の変更には、4 時間から 24 時間かかる場合があります。

### <a name="investigate-changes-in-device-exposure-or-impact"></a>デバイスの露出または影響の変化を調査する

公開されているデバイスの数が大幅に増加した場合、または組織の公開スコアと Microsoft Secure Score for Devices への影響が大幅に増加した場合は、そのセキュリティに関する推奨事項を調査する価値があります。

1. 推奨事項と **[ソフトウェアを開く] ページ** を選択します
2. [ **イベント タイムライン** ] タブを選択すると、新しい脆弱性や新しいパブリック エクスプロイトなど、そのソフトウェアに関連するすべての影響を受けるイベントが表示されます。 [イベント タイムラインの詳細](threat-and-vuln-mgt-event-timeline.md)
3. 修復要求の送信など、組織の露出や増加に対処する方法を決定する

## <a name="request-remediation"></a>修復を要求する

脅威と脆弱性の管理修復機能は、修復要求ワークフローを通じてセキュリティ管理者と IT 管理者の間のギャップを埋めます。 このようなセキュリティ管理者は、IT 管理者に対して、**セキュリティに関する推奨事項** ページからIntuneへの脆弱性の修復を要求できます。 [修復オプションの詳細](tvm-remediation.md)

### <a name="how-to-request-remediation"></a>修復を要求する方法

修復を要求するセキュリティに関する推奨事項を選択し、 **修復オプションを** 選択します。 フォームに入力し、[ **要求の送信]** を選択します。 修復ページに移動して、 [**修復**](tvm-remediation.md) 要求の状態を表示します。 [修復を要求する方法の詳細](tvm-remediation.md#request-remediation)

## <a name="file-for-exception"></a>例外のファイル

現時点で推奨事項が関連していない場合の修復要求の代わりに、推奨事項の例外を作成できます。 [例外の詳細を確認する](tvm-exception.md)

"例外処理" アクセス許可を持つユーザーのみが例外を追加できます。 [RBAC ロールの詳細については、こちらを参照してください](user-roles.md)。

推奨事項に対して例外が作成されると、推奨事項はアクティブでなくなります。 推奨事項の状態は、 **完全な例外** または **部分例外** (デバイス グループ別) に変更されます。

### <a name="how-to-create-an-exception"></a>例外を作成する方法

例外を作成するセキュリティに関する推奨事項を選択し、 **例外オプション** を選択します。

:::image type="content" source="images/tvm-exception-options.png" alt-text="セキュリティに関する推奨事項ポップアップの [例外オプション] ボタン" lightbox="images/tvm-exception-options.png":::

フォームに入力して送信します。 すべての例外 (現在および過去) を表示するには、[**脅威&脆弱性管理**] メニューの [[修復](tvm-remediation.md)] ページに移動し、[**例外**] タブを選択します。[例外の作成方法の詳細](tvm-exception.md#create-an-exception)

## <a name="report-inaccuracy"></a>レポートの不正確さ

あいまい、不正確、不完全、または既に修復されたセキュリティ推奨事項情報が表示された場合は、誤検知を報告できます。

1. セキュリティに関する推奨事項を開きます。

2. レポートするセキュリティに関する推奨事項の横にある 3 つの点を選択し、[ **不正確なレポート**] を選択します。

   :::image type="content" source="images/report-inaccuracy500.png" alt-text="[レポートの不正確さ] ボタン" lightbox="images/report-inaccuracy500.png":::

3. ポップアップ ウィンドウで、ドロップダウン メニューから不正確なカテゴリを選択し、メール アドレスと不正確さに関する詳細を入力します。

4. **[送信]** を選択します。 フィードバックはすぐに脅威と脆弱性の管理エキスパートに送信されます。

## <a name="related-articles"></a>関連記事

- [脅威と脆弱性の管理の概要](next-gen-threat-and-vuln-mgt.md)
- [ダッシュボード](tvm-dashboard-insights.md)
- [暴露スコア](tvm-exposure-score.md)
- [デバイス向けの Microsoft セキュア スコア](tvm-microsoft-secure-score-devices.md)
- [脆弱性を修復する](tvm-remediation.md)
- [セキュリティに関する推奨事項の例外を作成して表示する](tvm-exception.md)
- [イベントのタイムライン](threat-and-vuln-mgt-event-timeline.md)
