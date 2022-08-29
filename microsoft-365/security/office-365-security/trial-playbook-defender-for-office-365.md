---
title: Microsoft Defender for Office 365 試用版のプレイブック
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.collection: m365-security-compliance
ms.localizationpriority: high
ROBOTS: NOINDEX, NOFOLLOW
ms.prod: m365-security
search.appverid:
- MOE150
- MET150
description: Microsoft Defender for Office 365 ソリューション試用版のプレイブック。
ms.technology: mdo
ms.custom: trial-playbook
ms.openlocfilehash: 942752a8fc13a9644558f20567d7dd32e991867b
ms.sourcegitcommit: 7374c7b013890744d74e5214f7f8d69ca7874466
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2022
ms.locfileid: "67408067"
---
# <a name="trial-playbook-microsoft-defender-for-office-365"></a>試用版プレイブック: Microsoft Defender for Office 365

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象:**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft Defender for Office 365 試用版のプレイブックへようこそ。 このプレイブックでは、Defender for Office 365 を使用して組織を保護する方法を説明し、90 日間の無料試用版を最大限に活用するサポートを行います。

次の 2 つの方法のいずれかで Defender for Office 365 を試すことができます。

- **ブロック モード (推奨)**: メール エクスチェンジャー (MX) レコードが Microsoft 365 をポイントしている場合は、Defender for Office 365 の機能をブロック モードで評価できます。 Defender for Office 365 では、標準の[事前設定されたセキュリティ ポリシー](preset-security-policies.md)設定が自動的に適用されます。

  評価期間中は、いつでもより高い保護テンプレート (厳格な事前設定済みのセキュリティ ポリシー設定) を選択するか、ニーズに合わせて独自の個別の保護ポリシーを作成するかを選択できます。

- **監査モード**: MX レコードが Microsoft 365 以外の場所 (サードパーティの電子メール ゲートウェイなど) をポイントしている場合は、監査モードで Defender for Office 365 を評価できます。 Defender for Office 365 は、有害であると判断したメッセージに対してブロック操作は行いません。

  これらの脅威はログに記録され、[脅威に対する保護の進捗レポート](view-email-security-reports.md#threat-protection-status-report)を通じて確認できます。これにより、検出された脅威の種類、脅威の対象ユーザー、その他の詳細情報が提供されます。 これら追加の "キャッチ" は、標準の Exchange Online Protection (EOP) 機能を介した Defender for Office 365 の追加の保護機能、または他のサード パーティ製の電子メール ゲートウェイの機能を示します。 Defender for Office 365 を使用する準備ができたら、[Defender for Office 365](migrate-to-defender-for-office-365.md) に移行できます。

:::image type="content" source="../../media/mdo-trial-playbook-what-is-mdo.png" alt-text="Microsoft Defender for Office 365 のすべてのコンポーネントのグラフィカル表示。" lightbox="../../media/mdo-trial-playbook-what-is-mdo.png":::

このガイドのおすすめ候補を使用して、Defender for Office 365 を使用して保護ポリシーを定義し、組織に対する脅威を分析し、攻撃に対応する方法について説明します。

では、始めましょう。

## <a name="blocking-mode"></a>ブロック モード

### <a name="step-1-getting-started-in-blocking-mode"></a>手順 1: ブロック モードの概要

#### <a name="start-your-microsoft-defender-for-office-365-trial"></a>Microsoft Defender for Office 365 試用版の使用開始

お客様が試用版の使用を開始し、[セットアップ プロセス](try-microsoft-defender-for-office-365.md#set-up-an-evaluation-in-blocking-mode)を完了した後、変更が有効になるまでに最大 2 時間かかる場合があります。

お使いの環境に[事前設定されたセキュリティ ポリシー](preset-security-policies.md)を自動的に構成しました。 これらのポリシーは、ほとんどのユーザーに適したベースライン保護プロファイルを表します。 標準的な保護は以下のとおりです。

- 安全なリンク、安全な添付ファイル、フィッシング対策の各ポリシーは、テナント全体、または試用版のセットアップ プロセス時に選択したユーザーのサブセットに適用されます。
- SharePoint、OneDrive、Microsoft Teams の安全な添付ファイル保護。
- サポートされている Office 365 アプリの安全なリンク保護。

詳細については、以下のビデオをご覧ください。[Microsoft Defender for Office 365 の安全なリンクで悪意のあるリンクから保護する - YouTube](https://www.youtube.com/watch?v=vhIJ1Veq36Y&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=9)。

#### <a name="enable-users-to-report-suspicious-content-in-blocking-mode"></a>ユーザーがブロック モードで疑わしいコンテンツを報告できるようにする

Defender for Office 365 は、ユーザーがセキュリティ チームにメッセージを報告したり、管理者が Microsoft にメッセージを送信して分析を依頼したりすることができます。

- 「[メッセージ アドインのレポートまたはフィッシング アドインのレポートを有効にする](enable-the-report-message-add-in.md)」を展開します。
- 「[誤検出と検出漏れを報告する](report-false-positives-and-false-negatives.md)」ワークフローを確立します。
- [送信ポータル](admin-submission.md)を使用します。

詳細については、以下のビデオをご覧ください。[送信ポータルを使用して分析用メッセージを送信する方法を学ぶ - YouTube](https://www.youtube.com/watch?v=ta5S09Yz6Ks&ab_channel=MicrosoftSecurit)。

#### <a name="review-reports-to-understand-the-threat-landscape-in-blocking-mode"></a>レポートを確認して、ブロック モードの脅威の状況を理解する

Defender for Office 365 のレポート機能を使用して、環境の詳細を入手します。

- [脅威保護進捗レポート](view-email-security-reports.md#threat-protection-status-report)を使用して、メールやコラボレーション ツールで受信した脅威を把握します。
- [メールフロー進捗レポート](view-email-security-reports.md#mailflow-status-report)を使用して、脅威がブロックされている場所を確認します。
- ユーザーが表示した、またはシステムがブロックした[リンクを確認します](view-reports-for-mdo.md#url-protection-report)。

:::image type="content" source="../../media/mdo-trial-playbook-reporting.png" alt-text="Microsoft 365 Defender ポータルのメールとコラボレーションのレポート" lightbox="../../media/mdo-trial-playbook-reporting.png":::

### <a name="step-2-intermediate-steps-in-blocking-mode"></a>手順 2: ブロック モードの中間ステップ

#### <a name="prioritize-focus-on-your-most-targeted-users"></a>対象ユーザーに優先的にフォーカスする

Defender for Office 365 の「優先アカウント保護」を使用して、最も対象となるユーザーや最も目にする機会の多いユーザーを保護し、ワークフローに優先順位をつけてこれらのユーザーの安全を確保するのに役立ちます。

- 最も対象となるユーザー、または目にする機会の多いユーザーを特定します。
- 優先アカウントとして[これらのユーザーをタグ付けします](../../admin/setup/priority-accounts.md#add-priority-accounts-from-the-setup-page)。
- 優先アカウントへの脅威をポータル全体で追跡します。

詳細については、以下のビデオをご覧ください。[Microsoft Defender for Office 365 での優先アカウントの保護 - YouTube](https://www.youtube.com/watch?v=tqnj0TlzQcI&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=11)。

:::image type="content" source="../../media/mdo-trial-playbook-alerts.png" alt-text="Microsoft 365 Defender ポータルのアラート" lightbox="../../media/mdo-trial-playbook-alerts.png":::

### <a name="avoid-costly-breaches-by-preventing-user-compromise"></a>ユーザーの侵害を防いでコストのかかる侵害を回避

侵害の可能性を警告し、これらの脅威の影響を自動的に制限することで、攻撃者がユーザーの環境に深くアクセスすることを防ぎます。

- [侵害されたユーザーの警告](address-compromised-users-quickly.md#compromised-user-alerts)を確認します。
- 侵害されたユーザーへの[脅威の調査と対応](address-compromised-users-quickly.md)。

:::image type="content" source="../../media/mdo-trial-playbook-investigation.png" alt-text="侵害されたユーザーの調査。" lightbox="../../media/mdo-trial-playbook-investigation.png":::

詳細については、以下のビデオをご覧ください。[Microsoft Defender for Office 365 での侵害の検出と対応 - YouTube](https://www.youtube.com/watch?v=Pc7y3a-wdR0&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=5)。

#### <a name="use-threat-explorer-to-investigate-malicious-email"></a>脅威エクスプローラーを使用して悪質なメールを調査する

Defender for Office 365 を使用すると、組織内のユーザーを危険にさらすアクティビティを調査し、組織を保護するためのアクションを実行できます。これは、[脅威エクスプローラー](threat-explorer.md)を使用して行うことができます。

- [配信された疑わしいメールの検索](investigate-malicious-email-that-was-delivered.md#find-suspicious-email-that-was-delivered): メッセージを見つけて削除したり、悪意のあるメール送信者の IP アドレスを特定したり、さらなる調査のためにインシデントを開始したりすることができます。
- [配信アクションと場所のチェック](investigate-malicious-email-that-was-delivered.md#check-the-delivery-action-and-location): このチェックにより、問題のあるメール メッセージの場所を把握することができます。
- [メールのタイムラインを表示する](investigate-malicious-email-that-was-delivered.md#view-the-timeline-of-your-email): お客様のセキュリティ運用チームを簡単にハンティングします。

#### <a name="see-campaigns-targeting-your-organization"></a>所属している組織を対象とした攻撃活動を確認する

Defender for Office 365 のキャンペーン ビューを使用して、組織を標的とした攻撃活動と、その攻撃活動がユーザーに与える影響を表示し、全体像を把握することができます。

- ユーザーを対象とした[攻撃活動を特定します](campaigns.md#what-is-a-campaign)。
- 攻撃の[範囲を可視化します](campaigns.md#campaign-views-in-the-microsoft-365-defender-portal)。
- これらのメッセージを使用して[ユーザーの操作を追跡します](campaigns.md#campaign-details)。

  :::image type="content" source="../../media/mdo-trial-playbook-campaign-details.png" alt-text="Microsoft 365 Defender ポータルでの攻撃活動の詳細。" lightbox="../../media/mdo-trial-playbook-campaign-details.png":::

詳細については、以下のビデオをご覧ください。[Microsoft Defender for Office 365 でのキャンペーン ビュー - YouTube](https://www.youtube.com/watch?v=DvqzzYKu7cQ&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=14)。

#### <a name="use-automation-to-remediate-risks"></a>自動化を使用したリスクの修復

自動調査と応答 (AIR) を使用して、脅威の確認、優先度付け、対応を効率的に行います。

- 調査プレイブックの[詳細情報](automated-investigation-response-office.md)。
- 調査の[詳細と結果を表示します](email-analysis-investigations.md)。
- [修復処理を承認する](air-remediation-actions.md)ことで、脅威を排除します。

:::image type="content" source="../../media/mdo-trial-playbook-investigation-results.png" alt-text="調査結果。" lightbox="../../media/mdo-trial-playbook-investigation-results.png":::

### <a name="step-3-advanced-content-in-blocking-mode"></a>手順 3: ブロック モードの高度なコンテンツ

#### <a name="dive-deep-into-data-with-query-based-hunting"></a>クエリベースのハンティングを使用してデータの詳細を理解する

高度なハンティングを使用して、カスタムの検出ルールを記述し、環境内のイベントを予防的に検査し、脅威の指標を検索します。環境内のRaw データを調査します。

- [カスタム検出ルールを作成します](../defender/custom-detections-overview.md)。
- 他のユーザーが作成した[共有クエリにアクセスします](../defender/advanced-hunting-shared-queries.md)。

詳細については、以下のビデオをご覧ください。[Microsoft 365 Defender を使用した脅威ハンティング - YouTube](https://www.youtube.com/watch?v=l3OmH4U6XAs&list=PL3ZTgFEc7Lyt1O81TZol31YXve4e6lyQu&index=4)。

#### <a name="train-users-to-spot-threats-by-simulating-attacks"></a>攻撃のシミュレーションを行い、ユーザーが脅威を発見するトレーニングを行う

Defender for Office 365 の攻撃シミュレーション トレーニングを使用して、脅威を特定し、疑わしいメッセージを報告するための正しい知識をユーザーに提供します。

- [現実的な脅威をシミュレーション](attack-simulation-training.md)し、脆弱なユーザーを特定します。
- シミュレーション結果に基づいて、ユーザーに[トレーニングを割り当てます](attack-simulation-training.md#assign-training)。
- シミュレーションやトレーニング完了時の組織の[進捗状況を追跡します](attack-simulation-training-insights.md)。

  :::image type="content" source="../../media/mdo-trial-playbook-attack-simulation-training-results.png" alt-text="Microsoft 365 Defender ポータルでの攻撃シミュレーション トレーニングの分析情報" lightbox="../../media/mdo-trial-playbook-attack-simulation-training-results.png":::

## <a name="auditing-mode"></a>監査モード

### <a name="step-1-get-started-in-auditing-mode"></a>手順 1: 監査モードでの概要

#### <a name="start-your-defender-for-office-365-evaluation"></a>Microsoft Defender for Office 365 の評価を開始する

[セットアップ プロセス](try-microsoft-defender-for-office-365.md#set-up-an-evaluation-in-audit-mode)を完了すると、変更が有効になるまで最大 2 時間かかる場合があります。 お使いの環境で事前設定された評価ポリシーが自動的に構成されました。

評価ポリシーを使用すると、Defender for Office 365 によって検出された電子メールに対して何のアクションも実行されません。

#### <a name="enable-users-to-report-suspicious-content-in-auditing-mode"></a>ユーザーが監査モードで疑わしいコンテンツを報告できるようにする

Defender for Office 365 は、ユーザーがセキュリティ チームにメッセージを報告したり、管理者が Microsoft にメッセージを送信して分析を依頼したりすることができます。

- 「[メッセージ アドインのレポートまたはフィッシング アドインのレポートを有効にする](enable-the-report-message-add-in.md)」を展開します。
- 「[誤検出と検出漏れを報告する](report-false-positives-and-false-negatives.md)」ワークフローを確立します。
- [送信ポータル](admin-submission.md)を使用します。

詳細については、以下のビデオをご覧ください。[送信ポータルを使用して分析用メッセージを送信する方法を学ぶ - YouTube](https://www.youtube.com/watch?v=ta5S09Yz6Ks&ab_channel=MicrosoftSecurit)。

#### <a name="review-reports-to-understand-the-threat-landscape-in-auditing-mode"></a>レポートを確認して、監査モードの脅威の状況を理解する

Defender for Office 365 のレポート機能を使用して、環境の詳細を入手します。

- [評価ダッシュボード](try-microsoft-defender-for-office-365.md#reporting-in-audit-mode)は、評価中に Defender for Office 365 によって検出された脅威を簡単に確認できます。
- [脅威保護進捗レポート](view-email-security-reports.md#threat-protection-status-report)を使用して、メールやコラボレーション ツールで受信した脅威を把握します。

### <a name="step-2-intermediate-steps-in-auditing-mode"></a>手順 2: 監査モードの中間ステップ

#### <a name="use-threat-explorer-to-investigate-malicious-email-in-auditing-mode"></a>脅威エクスプローラーを使用して、監査モードで悪意のあるメールを調査する

Defender for Office 365 を使用すると、組織内のユーザーを危険にさらすアクティビティを調査し、組織を保護するためのアクションを実行できます。これは、[脅威エクスプローラー](threat-explorer.md)を使用して行うことができます。

- [配信された疑わしいメールの検索](investigate-malicious-email-that-was-delivered.md#find-suspicious-email-that-was-delivered): メッセージを見つけて削除したり、悪意のあるメール送信者の IP アドレスを特定したり、さらなる調査のためにインシデントを開始したりすることができます。
- [配信アクションと場所のチェック](investigate-malicious-email-that-was-delivered.md#check-the-delivery-action-and-location): このチェックにより、問題のあるメール メッセージの場所を把握することができます。
- [メールのタイムラインを表示する](investigate-malicious-email-that-was-delivered.md#view-the-timeline-of-your-email): お客様のセキュリティ運用チームを簡単にハンティングします。

#### <a name="convert-to-standard-protection-at-the-end-of-evaluation-period"></a>評価期間の終了時に [Standard 保護] に変換する

運用環境で Defender for Office 365 ポリシーを有効にする準備ができたら、評価管理エクスペリエンス内で [Standard 保護に変換] を使用して、[事前設定されたセキュリティ ポリシー](preset-security-policies.md)で Standard 保護に簡単に移行できます。

1. <https://security.microsoft.com/atpEvaluation> の [**Microsoft Defender for Office 365 評価**] ページで、[**管理**] をクリックします。

   :::image type="content" source="../../media/mdo-trial-playbook-mdo-evaluation-page.png" alt-text="Microsoft 365 Defender ポータルの Defender for Office 365 評価ページで [管理] をクリックします。" lightbox="../../media/mdo-trial-playbook-mdo-evaluation-page.png":::

2. 表示されたポップアップで、[**Standard 保護に変換**] をクリックします

   :::image type="content" source="../../media/mdo-trial-playbook-manage-flyout.png" alt-text="[Defender for Office 365 評価] ページの [管理] ポップアップで [Standard 保護に変換] をクリックします。" lightbox="../../media/mdo-trial-playbook-manage-flyout.png":::

3. [**Standard 保護への変換**] ダイアログが開いたら、[**続行**] をクリックしてセットアップを開始します。

#### <a name="migrate-from-a-third-party-protection-service-or-device-to-defender-for-office-365"></a>サードパーティの保護サービスまたはデバイスから Defender for Office 365 に移行する

Microsoft 365 の前にすでに既存のサードパーティ製保護サービスやデバイスをお持ちの場合、保護機能を Microsoft Defender for Office 365 に移行することで、統合管理、潜在的なコスト削減（すでに支払っている製品の使用）、統合セキュリティ保護を備えた成熟した製品という利点を得ることができます。

詳細については、「[サードパーティの保護サービスまたはデバイスから Microsoft Defender for Office 365 に移行する」を参照してください](migrate-to-defender-for-office-365.md)。

### <a name="step-3-advanced-content-in-auditing-mode"></a>手順 3: 監査モードの高度なコンテンツ

#### <a name="train-users-to-spot-threats-by-simulating-attacks-in-auditing-mode"></a>監査モードで攻撃をシミュレートして脅威を特定するようにユーザーをトレーニングする

Defender for Office 365 の攻撃シミュレーション トレーニングを使用して、脅威を特定し、疑わしいメッセージを報告するための正しい知識をユーザーに提供します。

- [現実的な脅威をシミュレーション](attack-simulation-training.md)し、脆弱なユーザーを特定します。
- シミュレーション結果に基づいて、ユーザーに[トレーニングを割り当てます](attack-simulation-training.md#assign-training)。
- シミュレーションやトレーニング完了時の組織の[進捗状況を追跡します](attack-simulation-training-insights.md)。

  :::image type="content" source="../../media/mdo-trial-playbook-attack-simulation-training-results.png" alt-text="Microsoft 365 Defender ポータルでの攻撃シミュレーション トレーニングの分析情報" lightbox="../../media/mdo-trial-playbook-attack-simulation-training-results.png":::

## <a name="additional-resources"></a>その他のリソース

- **対話型のガイド**: Defender for Office 365 に慣れていないユーザー向け [対話型のガイド](https://mslearn.cloudguides.com/guides/Safeguard%20your%20organization%20with%20Microsoft%20Defender%20for%20Office%20365)を確認して、利用を開始する方法を理解します。
- **すばやく開始するためのガイド***: [Microsoft Defender for Office 365](https://go.microsoft.com/fwlink/p/?linkid=2197415)
- **Microsoft のドキュメント**: Defender for Office 365 のしくみや、組織に最適な実装方法などの詳細情報を入手します。「[ドキュメント](overview.md)」 の詳細。
- **含まれるもの**: Office 365 メール セキュリティ機能の完全な一覧と製品レベル別の機能については、「[機能一覧](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability)」をご覧ください。
- **Defender for Office 365 を選ぶ理由**: [Defender for Office 365 データシート](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE4FCiy)では、お客様が Microsoft を選ぶ理由のトップ 10 を紹介しています。
