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
ms.openlocfilehash: a1adcf15bd051478e874b990a5e6b12f19d3b0c6
ms.sourcegitcommit: 725a92b0b1555572b306b285a0e7a7614d34e5e5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2022
ms.locfileid: "65648351"
---
# <a name="trial-playbook-microsoft-defender-for-office-365"></a>試用版プレイブック: Microsoft Defender for Office 365

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象:**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft Defender for Office 365 試用版のプレイブックへようこそ。 このプレイブックでは、Defender for Office 365 を使用して組織を保護する方法を説明し、90 日間の無料試用版を最大限に活用するサポートを行います。 Microsoft 推奨事項を使用して、Defender for Office 365 が、保護ポリシーの定義、組織への脅威の分析、攻撃への対応にどのように役立つ方法を説明します。

:::image type="content" source="../../media/mdo-trial-playbook-what-is-mdo.png" alt-text="Microsoft Defender for Office 365 のすべてのコンポーネントのグラフィカル表示。" lightbox="../../media/mdo-trial-playbook-what-is-mdo.png":::

これらのアクションは、90 日間の試用版で利用できる主要な機能に関する Microsoft Defender チームの推奨事項です。

## <a name="step-1-getting-started"></a>手順 1: 作業の開始

### <a name="start-your-microsoft-defender-for-office-365-trial"></a>Microsoft Defender for Office 365 試用版の使用開始

お客様が試用版の使用を開始し、セットアップ プロセスを完了した後、変更が有効になるまでに最大 2 時間かかる場合があります。

お使いの環境に[事前設定されたセキュリティ ポリシー](preset-security-policies.md)を自動的に構成しました。 これらのポリシーは、ほとんどのユーザーに適したベースライン保護プロファイルを表します。 標準的な保護は以下のとおりです。

- 安全なリンク、安全な添付ファイル、フィッシング対策の各ポリシーは、テナント全体、または試用版のセットアップ プロセス時に選択したユーザーのサブセットに適用されます。
- SharePoint、OneDrive、Microsoft Teams の安全な添付ファイル保護。
- サポートされている Office 365 アプリの安全なリンク保護。

詳細については、以下のビデオをご覧ください。[Microsoft Defender for Office 365 の安全なリンクで悪意のあるリンクから保護する - YouTube](https://www.youtube.com/watch?v=vhIJ1Veq36Y&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=9)。

### <a name="enable-users-to-report-suspicious-content"></a>ユーザーが疑わしいコンテンツを報告できるようにする

Defender for Office 365 は、ユーザーがセキュリティ チームにメッセージを報告したり、管理者が Microsoft にメッセージを送信して分析を依頼したりすることができます。

- 「[メッセージ アドインのレポートまたはフィッシング アドインのレポートを有効にする](enable-the-report-message-add-in.md)」を展開します。
- 「[誤検出と検出漏れを報告する](report-false-positives-and-false-negatives.md)」ワークフローを確立します。
- [送信ポータル](admin-submission.md)を使用します。

詳細については、以下のビデオをご覧ください。[送信ポータルを使用して分析用メッセージを送信する方法を学ぶ - YouTube](https://www.youtube.com/watch?v=ta5S09Yz6Ks&ab_channel=MicrosoftSecurit)。

### <a name="review-reports-to-understand-the-threat-landscape"></a>脅威の概要を理解するためのレポートのレビュー

Defender for Office 365 のレポート機能を使用して、環境の詳細を入手します。

- [脅威保護進捗レポート](view-email-security-reports.md#threat-protection-status-report)を使用して、メールやコラボレーション ツールで受信した脅威を把握します。
- [メールフロー進捗レポート](view-email-security-reports.md#mailflow-status-report)を使用して、脅威がブロックされている場所を確認します。
- ユーザーが表示した、またはシステムがブロックした[リンクを確認します](view-reports-for-mdo.md#url-protection-report)。

:::image type="content" source="../../media/mdo-trial-playbook-reporting.png" alt-text="Microsoft 365 Defender ポータルのメールとコラボレーションのレポート" lightbox="../../media/mdo-trial-playbook-reporting.png":::

## <a name="step-2-intermediate-steps"></a>手順 2: 中間ステップ

### <a name="prioritize-focus-on-your-most-targeted-users"></a>対象ユーザーに優先的にフォーカスする

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

### <a name="use-threat-explorer-to-investigate-malicious-email"></a>脅威エクスプローラーを使用して悪質なメールを調査する

Defender for Office 365 を使用すると、組織内のユーザーを危険にさらすアクティビティを調査し、組織を保護するためのアクションを実行できます。これは、[脅威エクスプローラー](threat-explorer.md)を使用して行うことができます。

- [配信された疑わしいメールの検索](investigate-malicious-email-that-was-delivered.md#find-suspicious-email-that-was-delivered): メッセージを見つけて削除したり、悪意のあるメール送信者の IP アドレスを特定したり、さらなる調査のためにインシデントを開始したりすることができます。
- [配信アクションと場所のチェック](investigate-malicious-email-that-was-delivered.md#check-the-delivery-action-and-location): このチェックにより、問題のあるメール メッセージの場所を把握することができます。
- [メールのタイムラインを表示する](investigate-malicious-email-that-was-delivered.md#view-the-timeline-of-your-email): お客様のセキュリティ運用チームを簡単にハンティングします。

### <a name="see-campaigns-targeting-your-organization"></a>所属している組織を対象とした攻撃活動を確認する

Defender for Office 365 のキャンペーン ビューを使用して、組織を標的とした攻撃活動と、その攻撃活動がユーザーに与える影響を表示し、全体像を把握することができます。

- ユーザーを対象とした[攻撃活動を特定します](campaigns.md#what-is-a-campaign)。
- 攻撃の[範囲を可視化します](campaigns.md#campaign-views-in-the-microsoft-365-defender-portal)。
- これらのメッセージを使用して[ユーザーの操作を追跡します](campaigns.md#campaign-details)。

  :::image type="content" source="../../media/mdo-trial-playbook-campaign-details.png" alt-text="Microsoft 365 Defender ポータルでの攻撃活動の詳細。" lightbox="../../media/mdo-trial-playbook-campaign-details.png":::

詳細については、以下のビデオをご覧ください。[Microsoft Defender for Office 365 でのキャンペーン ビュー - YouTube](https://www.youtube.com/watch?v=DvqzzYKu7cQ&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=14)。

### <a name="use-automation-to-remediate-risks"></a>自動化を使用したリスクの修復

自動調査と応答 (AIR) を使用して、脅威の確認、優先度付け、対応を効率的に行います。

- 調査プレイブックの[詳細情報](automated-investigation-response-office.md)。
- 調査の[詳細と結果を表示します](email-analysis-investigations.md)。
- [修復処理を承認する](air-remediation-actions.md)ことで、脅威を排除します。

:::image type="content" source="../../media/mdo-trial-playbook-investigation-results.png" alt-text="調査結果。" lightbox="../../media/mdo-trial-playbook-investigation-results.png":::

## <a name="step-3-advanced-content"></a>手順 3: 高度なコンテンツ

### <a name="dive-deep-into-data-with-query-based-hunting"></a>クエリベースのハンティングを使用してデータの詳細を理解する

高度なハンティングを使用して、カスタムの検出ルールを記述し、環境内のイベントを予防的に検査し、脅威の指標を検索します。環境内のRaw データを調査します。

- [カスタム検出ルールを作成します](../defender/advanced-hunting-overview.md#get-started-with-advanced-hunting)。
- 他のユーザーが作成した[共有クエリにアクセスします](../defender/advanced-hunting-shared-queries.md)。

詳細については、以下のビデオをご覧ください。[Microsoft 365 Defender を使用した脅威ハンティング - YouTube](https://www.youtube.com/watch?v=l3OmH4U6XAs&list=PL3ZTgFEc7Lyt1O81TZol31YXve4e6lyQu&index=4)。

### <a name="train-users-to-spot-threats-by-simulating-attacks"></a>攻撃のシミュレーションを行い、ユーザーが脅威を発見するトレーニングを行う

Defender for Office 365 の攻撃シミュレーション トレーニングを使用して、脅威を特定し、疑わしいメッセージを報告するための正しい知識をユーザーに提供します。

- [現実的な脅威をシミュレーション](attack-simulation-training.md)し、脆弱なユーザーを特定します。
- シミュレーション結果に基づいて、ユーザーに[トレーニングを割り当てます](attack-simulation-training.md#assign-training)。
- シミュレーションやトレーニング完了時の組織の[進捗状況を追跡します](attack-simulation-training-insights.md)。

  :::image type="content" source="../../media/mdo-trial-playbook-attack-simulation-training-results.png" alt-text="Microsoft 365 Defender ポータルでの攻撃シミュレーション トレーニングの分析情報" lightbox="../../media/mdo-trial-playbook-attack-simulation-training-results.png":::

## <a name="additional-resources"></a>その他のリソース

- **対話型のガイド**: Defender for Office 365 に慣れていないユーザー向け [対話型のガイド](https://mslearn.cloudguides.com/guides/Safeguard%20your%20organization%20with%20Microsoft%20Defender%20for%20Office%20365)を確認して、利用を開始する方法を理解します。
- **Microsoft のドキュメント**: Defender for Office 365 のしくみや、組織に最適な実装方法などの詳細情報を入手します。「[ドキュメント](overview.md)」 の詳細。
- **含まれるもの**: Office 365 メール セキュリティ機能の完全な一覧と製品レベル別の機能については、「[機能一覧](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability)」をご覧ください。
- **Defender for Office 365 を選ぶ理由**: [Defender for Office 365 データシート](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE4FCiy)では、お客様が Microsoft を選ぶ理由のトップ 10 を紹介しています。
