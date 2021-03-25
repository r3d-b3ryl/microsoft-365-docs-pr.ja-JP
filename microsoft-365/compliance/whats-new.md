---
title: Microsoft 365 コンプライアンスの新機能
f1.keywords:
- NOCSH
ms.author: brendonb
author: brendonb
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: コンプライアンス センターに新しいソリューションを追加する場合、フィードバックに基づいて既存の機能を更新する場合、最新のドキュメントを展開する場合でも、Microsoft 365 を使用すると、変化し続けるコンプライアンス環境を常に改善できます。 今月までの予定を確認します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c695bc2632e766eb6f14c4e9f7eabbbddff66fd2
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164976"
---
# <a name="whats-new-in-microsoft-365-compliance"></a>Microsoft 365 コンプライアンスの新機能

Microsoft 365 コンプライアンス センターに新しいソリューションを追加する場合、フィードバックに基づいて既存の機能を更新する場合、最新のドキュメントを展開する場合でも [、Microsoft 365](microsoft-365-compliance-center.md)を使用すると、変化し続けるコンプライアンス環境の上に立ち続けるのに役立ちます。 今日の Microsoft 365 コンプライアンスの新機能については、以下をご覧ください。

> [!NOTE]
> 一部のコンプライアンス機能は、お客様に異なる速度で展開されます。 まだ機能が表示されない場合は、ターゲットリリースに自分自身を [追加してみてください](/office365/admin/manage/release-options-in-office-365)。

> [!TIP]
> 他の管理センターで何が起こっているのか興味がありますか? 次の記事を参照してください。<br>[Microsoft 365 管理センターの新機能](/office365/admin/whats-new-in-preview)<br>[SharePoint 管理センターの新機能](/sharepoint/what-s-new-in-admin-center)<br>[Microsoft 365 Defender の新機能](../security/defender/whats-new.md)<br><br>
Microsoft [365 ロードマップ](https://www.microsoft.com/en-us/microsoft-365/roadmap) にアクセスして、起動、展開、開発中、キャンセル、または以前にリリースされた Microsoft 365 の機能について説明します。

## <a name="january-2021"></a>2021 年 1 月

### <a name="support-for-card-content-in-teams"></a>Teams でのカード コンテンツのサポート

次の Microsoft 365 コンプライアンス ソリューションは[](/microsoftteams/platform/task-modules-and-cards/what-are-cards)、Teams メッセージ内のアプリを介して生成されたカード コンテンツの検出をサポートします。

- **Core および Advanced eDiscovery**. カード コンテンツを保留 [にしたり](create-ediscovery-holds.md#preserve-card-content) 、検索に含め [したりできます](/microsoftteams/ediscovery-investigation#search-for-card-content) (コンテンツ検索にも適用されます)。
- **監査**. これで、カードアクティビティ [が監査ログに記録されます](/microsoftteams/audit-log-events#teams-activities)。
- **アイテム保持ポリシー**。 アイテム保持ポリシーを使用して、カード [コンテンツを保持および削除できます](retention-policies-teams.md#whats-included-for-retention-and-deletion)。

### <a name="information-governance-and-records-management"></a>情報ガバナンスとレコード管理

[ニュージーランド公的](retention-regulatory-requirements.md#new-zealand-public-records-act) 記録法のコンプライアンス義務を満たすのに役立つ情報ガバナンスとレコード管理を使用して対処するための新しい評価。

### <a name="sensitivity-labels"></a>秘密度ラベル

- 米国政府機関のテナント (GCC および GCC-H) では、感度ラベルがサポートされています。
- macOS [の新しい自動](sensitivity-labels-office-apps.md) ラベル付けサポート。

## <a name="december-2020"></a>2020年12月

### <a name="spotlight-new-content-for-insider-risk-solutions"></a>スポットライト: インサイダー リスク ソリューションの新しいコンテンツ

Microsoft 365 コンプライアンス コンテンツ チームは、コンプライアンスの目標を達成するためにコンプライアンス機能を一緒に使用する方法を促進するために、"コンテンツ ソリューション" ドキュメントの作成に取り組み、作業を行っています。

まず、コミュニケーションコンプライアンス、インサイダーリスク管理、情報障壁、特権アクセス管理など、インサイダーリスクソリューションを結び付け合うコンテンツです。 次に、見つけた情報を示します。

- [インサイダー リスク ソリューションの新しいランディング ページ](insider-risk-solution-overview.md)。 ソリューションが軽減に役立つリスク、ライセンス要件、展開シーケンス、アーキテクチャの図、トレーニング リソースなどについて詳細に説明します。
- 各インサイダー リスク ソリューションの新しい概要記事。 各ソリューションについて学び、計画し、展開し、管理するのに役立つ記事へのガイダンスとリンク。
  - [通信コンプライアンス](communication-compliance-solution-overview.md)
  - [インサイダー リスクの管理](insider-risk-management-solution-overview.md)
  - [情報障壁](information-barriers-solution-overview.md)
  - [特権アクセスの管理](privileged-access-management-solution-overview.md)
  
より多くのコンテンツ ソリューション ドキュメントが近日公開予定です。

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

高度な電子情報開示[ケースに保管](add-custodians-to-case.md)担当者と非保管データ[](non-custodial-data-sources.md)ソースを追加するためのワークフローと機能が向上しました。

### <a name="data-connectors"></a>データ コネクタ

[Redtail Speak、Salesforce](archiving-third-party-data.md#third-party-data-connectors)Chatter、ServiceNow、Yieldbroker の 4 つの新しい Veritas コネクタがリリースされました。

### <a name="encryption"></a>暗号化

テナント レベル [での Microsoft 365 のカスタマー キーの導入](customer-key-tenant-level.md)。 指定したキーを使用して、データ暗号化ポリシー (DEP) を作成し、テナントに割り当てできます。 DEP は、次のワークロードのテナント全体のデータを暗号化します。

- Teams チャット メッセージ (1:1 チャット、グループ チャット、会議チャット、チャネル会話)
- Teams メディア メッセージ (画像、コード スニペット、ビデオ、Wiki イメージ)
- Teams の通話と Teams ストレージに保存されている会議の記録
- Teams チャット通知
- Cortana による Teams チャットの提案
- Teams の状態メッセージ
- Exchange Online のユーザー情報とシグナル情報

### <a name="records-management"></a>レコード管理

レコード [管理管理者役割グループは、](get-started-with-records-management.md#permissions-required-for-records-management) 廃棄レビューを含むすべてのレコード管理機能に対するアクセス許可を付与します。

### <a name="sensitivity-labels"></a>秘密度ラベル

- [Azure Purview のデータに自動的にラベルを付け (プレビュー) します](/azure/purview/create-sensitivity-label)。 これで、Azure Purview のアセット (Azure Blob ストレージ内のファイルや、Azure の Blob ストレージ内のデータベース列など) に対して、SQL Server。
- [ユーザーがアイテムにラベルを適用する必要があります](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents)。 "必須ラベル付け" とも呼ばれるこの新しいオプションでは、ユーザーが特定のシナリオで感度ラベルを選択して適用する必要があります。

## <a name="november-2020"></a>2020 年 11 月
プレビュー状態で新しい機能や更新された機能をリリースする場合が多いので、一般公開にリリースする前に、機能を磨いて改善することができます。 プレビュー中 (以降) はフィードバックが重要なので、コンプライアンス センターの右下にあるフィードバック カードを開いて、お客様の考えをお知らせください。

![feedback](../media/Feedback_card_MCC.JPG)

### <a name="spotlight-endpoint-data-loss-prevention-dlp-released"></a>Spotlight: エンドポイント データ損失防止 (DLP) がリリースされました

[エンドポイント DLP は](endpoint-dlp-learn-about.md) 、DLP のアクティビティ監視および保護機能を Windows 10 デバイス上の機密情報に拡張します。 デバイスが[](dlp-configure-endpoints.md)Microsoft 365 コンプライアンス センターにオンボードされた後、DLP ポリシーをセットアップして、それらのデバイスの機密情報を保護できます。

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

電子情報開示ワークフローで暗号化されたコンテンツを簡単に管理するために、Microsoft 365 電子情報開示ツールは、[](ediscovery-decryption.md)電子メール メッセージに添付され、Exchange で送信される暗号化されたファイルの暗号化解除を組み込むになりました。 さらに、SharePoint および OneDrive に格納されている暗号化されたドキュメントは、Advanced eDiscovery で復号化されます。

### <a name="compliance-manager"></a>コンプライアンス マネージャー

- [Microsoft 365 Government サブスクリプションのサポート](compliance-manager.md)。 コンプライアンス マネージャーは、米国政府機関コミュニティ (GCC) 中程度および高い顧客が利用できます。
- [コンプライアンス マネージャー用の Microsoft コンプライアンス構成アナライザー](compliance-manager-mcca.md)。 組織の現在の構成をスキャンし、Microsoft 365 推奨ベスト プラクティスに対して検証することで、コンプライアンス マネージャーの使用を開始するのに役立つ新しい PowerShell ベースのツール。
- [新しいテンプレート](compliance-manager-templates-list.md)。 56 の新しいテンプレートが追加され、コンプライアンス マネージャー テンプレートの合計が 230 を超えました。

### <a name="data-connectors"></a>データ コネクタ

[プレビューの 5 つの新しい Veritas コネクタ](archiving-third-party-data.md#third-party-data-connectors)。 新しいコネクタには、Reuters Dealing、Reuters FX、CellTrust、XIP、汎用 MS SQLデータベース データが含まれます。

### <a name="retention-labels-disposition-review"></a>保持ラベル (廃棄レビュー)

廃棄レビュー中にアイテムを表示するには、ユーザーが Content Explorer コンテンツ ビューアーおよびコンテンツ エクスプローラー リスト ビューアーの役割グループのメンバーである [必要があります](disposition.md#permissions-for-disposition)。 アイテムを確認する必要は生まれますが、廃棄レビューを完了するためにこれらの役割グループは必要ありません。

### <a name="sensitivity-labels"></a>秘密度ラベル

- [(プレビュー) SharePoint サイトの外部共有設定](sensitivity-labels-teams-groups-sites.md#how-to-configure-groups-and-site-settings)。 グループとサイトに使用するラベルを作成する場合、ラベルが適用されている SharePoint サイトの外部共有を制御するオプションが表示されます。 すべてのユーザー、新規および既存のゲスト、既存のゲスト、または組織内のユーザーに対して共有を許可できます。 ラベルを適用すると、ラベル設定によって、SharePoint 管理センターで構成されている外部共有設定 [が置き換されます](/sharepoint/change-external-sharing-site)。
- [ラベル付きドキュメントからラベルと暗号化を削除します](sensitivity-labels-sharepoint-onedrive-files.md#remove-encryption-for-a-labeled-document)。 ラベルと、ラベルが適用する暗号化の両方を SharePoint のラベル付きドキュメントから削除するには、グローバル管理者と SharePoint 管理者が新しいコマンドレットを実行 `Unlock-SPOSensitivityLabelEncryptedFile` できます。 このコマンドレットは、管理者がサイトまたはファイルへのアクセス許可を持っていなくても、Azure Rights Management サービスが利用できない場合でも実行されます。

## <a name="october-2020"></a>2020 年 10 月

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

[CJK 言語のサポート](ediscovery-cjk-support.md)。 Advanced eDiscovery では、2 バイト文字セット言語 (総称して CJK 言語) がサポートされています (簡体字中国語、繁体字中国語、日本語、韓国語を含む)。 これらは、いくつかの高度なレビュー セットシナリオで使用できます。

### <a name="sensitivity-labels"></a>秘密度ラベル

- [ラベル スコープ](sensitivity-labels.md#label-scopes)。 感度ラベルを作成するときに、ラベルの範囲を定義する新しいオプションが表示されます。 このオプションを使用すると、ファイルとメール、コンテナー (SharePoint サイトや Teams など)、または両方のラベルを構成できます。
- [動的なコンテンツ マーキング](sensitivity-labels-office-apps.md#dynamic-markings-with-variables)。 感度ラベルのコンテンツ マーキングを構成するときに、ヘッダー、フッター、透かしのテキスト文字列などの動的 `${Item.Label}` 変数 `${Item.Location}` を使用できます。

## <a name="september-2020"></a>2020 年 9 月

### <a name="spotlight-compliance-manager"></a>スポットライト: コンプライアンス マネージャー

今年の Ignite で発表されたコンプライアンス スコアは、コンプライアンス マネージャーとして [ブランド変更されます](compliance-manager.md)。 このリリースでは、Service Trust Portal のコンプライアンス マネージャーの以前のホームからの移行が完了し、Microsoft 365 コンプライアンス センターにエンドツーエンドのコンプライアンス管理ソリューションが導入されています。

コンプライアンス マネージャーが組織がコンプライアンスを管理する方法を簡略化する方法については、以下のビデオをご覧ください。
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4FGYZ]

### <a name="advanced-audit"></a>高度な監査

- 監査ログの新しい 10 年間の保持は、長時間の調査をサポートし、規制、法律、および内部の義務に対応するのに役立ちます。
- [3 つの新しい重要なイベント](advanced-audit.md#access-to-crucial-events-for-investigations)。 次の新しいイベントは、侵害の可能性を調査し、侵害の範囲を特定するのに役立ちます。Send、SearchQueryInitiatedExchange、SearchQueryInitiatedSharePoint。

### <a name="communication-compliance"></a>コミュニケーション コンプライアンス

- [役割グループを更新しました](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance)。 コミュニケーション コンプライアンスの役割グループは、インサイダー リスク管理ソリューションで使用できる役割グループ構造と一致します。
- [レポート ダッシュボード](communication-compliance-feature-reference.md#reports)。 すべての通信コンプライアンス レポートを表示する中心的な場所。 レポート ウィジェットは、通信コンプライアンス活動の状態を全体的に評価するために最も一般的に必要な分析情報のクイック ビューを提供します。
- [Power Automate フロー](communication-compliance-feature-reference.md#power-automate-flows). フローを設定して、アラートとユーザーのタスクを自動化し、ユーザーがアラートをトリガーした場合に管理者に通知します。
- ['分類の改善' 修復アクション](communication-compliance-investigate-remediate.md#step-3-decide-on-a-remediation-action). トレーニング可能な分類子に一致するアイテムを含むアラートは、組織内の誤検知を最小限に抑えるためにフィードバックの恩恵を受ける可能性があります。 [ **分類の改善]** オプションを使用すると、検出されたアイテムが関連する通信コンプライアンス ポリシーで構成された分類子と一致するかどうかをフィードバックできます。 また、他の分類子をアイテムに関連付け、将来のアラートの一致精度を向上させる方法を提案することもできます。

### <a name="data-connectors"></a>データ コネクタ

- [新しいサード パーティ製のデータ コネクタ](archiving-third-party-data.md#third-party-data-connectors)。 25 個の新しいデータ コネクタ(Veritas から 14 個、Telemessage から 8 個を含む)。
- [物理不良コネクタ](import-physical-badging-data.md)。 従業員の生の物理アクセス イベントや、組織の不良システムによって生成された物理アクセス アラームなど、物理的な不良データをインポートします。 たとえば、建物、サーバー ルーム、またはデータ センターへのエントリが含まれます。 物理的な不正なデータは、内部の悪意のある活動やデータの盗難から組織を保護するために、インサイダー リスク管理ソリューションで使用できます。

### <a name="insider-risk-management"></a>インサイダー リスクの管理

- [Microsoft Teams の統合](insider-risk-management-settings.md#microsoft-teams-preview). Teams の統合がインサイダー リスク設定で有効になっている場合は、個々のケースに関連するデータの安全な共有と保存、アナリストや調査担当者からの応答アクティビティの追跡とレビューなどのタスクについて、Teams の他の利害関係者と調整および共同作業を行うことができます。
- [Power Automate フロー](insider-risk-management-settings.md#power-automate-flows-preview). ユーザーの取得、アラート、ケース情報の取得、関係者や他のアプリとの共有、ケース メモへの投稿などのアクションの自動化など、ケースとユーザーの重要なタスクを自動化するためのフローを設定します。
- [アクティビティ エクスプローラー](insider-risk-management-alerts.md#activity-explorer-preview)。 アラートを確認する際に利用できるアクティビティ エクスプローラーは、調査担当者とアナリストに、各アラートを詳細に調査する包括的な分析ツールを提供します。 検出された危険なアクティビティのタイムラインをすばやく確認し、アラートに関連付けられているすべてのリスク アクティビティを特定してフィルター処理します。

### <a name="retention-policies-and-retention-labels"></a>アイテム保持ポリシーと保持ラベル

- [ファイルのYammer。](retention-policies-yammer.md) 保持ポリシーを使用して、コミュニティ メッセージとプライベート メッセージYammer保持および削除できます。
- [Teams 会議の記録にラベルを適用します](apply-retention-labels-automatically.md#microsoft-teams-meeting-recordings)。 自動ラベル付けポリシーを作成する場合は、キーワード クエリ エディターを使用して、ユーザーの OneDrive アカウントまたは SharePoint に保存されている Teams 会議の記録を識別します。

### <a name="records-management"></a>レコード管理

[規制レコードのサポート](declare-records.md#how-to-display-the-option-to-mark-content-as-a-regulatory-record)。 ラベルを規制レコードとして分類すると、ラベルが適用されるコンテンツに対する制限が増加し、ラベル自体に対して使用可能な管理アクションが制限されます。 たとえば、コンテンツに適用した後、グローバル管理者でなくても、誰もラベルを削除できます。 [規制レコード](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked) に対して許可およびブロックされるアクションの詳細については、以下を参照してください。

### <a name="sensitivity-labels"></a>秘密度ラベル

[米国政府機関のお客様向けサポート](/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description)。 感度ラベルは、GCC、GCC High、DoD のお客様に対してサポートされ、Azure Information Protection 統合ラベル付けクライアントとスキャナーの場合のみサポートされています。

### <a name="trainable-classifiers"></a>トレーニング可能な分類子

新しい再トレーニングとフィードバック機能は、すべてのカスタム分類子と事前トレーニング済みの分類子の精度を向上し、誤検知の一致を最小限に抑えるのに役立ちます。 このフローでは、アイテムが特定の分類子と一致するかどうかをフィードバックし、他の分類子にアイテムと関連付ける提案を行い、分類子を再トレーニングしてマッチの精度を調整および向上できます。

この新しい機能は、次の機能に含まれています。

> [!NOTE]
> すべての機能について、少なくとも 30 件のフィードバック応答を提供する場合は、確認できる再トレーニングされたバージョンの分類子を作成します。 改善点がある場合は、分類子を再発行できます。

- [トレーニング可能な分類子](classifier-learn-about.md#retraining-classifiers)。 発行された分類子の精度を向上させるために、検出されたアイテムが分類子と一致するかどうかについてフィードバックを提供できます。
- [コミュニケーションコンプライアンス](classifier-how-to-retrain-comms-compliance.md)。 新しい **[分類修復の** 改善] アクションを使用すると、通信コンプライアンスアラートのアイテムが通信コンプライアンス ポリシーで構成された分類子と一致するかどうかをフィードバックできます。
- [コンテンツ エクスプローラー](classifier-how-to-retrain-content-explorer.md)。 トレーニング可能な分類子に一致する電子メール メッセージにラベルを自動的に適用する保持自動ラベル付けポリシーを設定する場合は、コンテンツ エクスプローラーを使用してラベル付きアイテムを確認し、アイテムが分類子と一致するかどうかをフィードバックすることができます。

## <a name="august-2020"></a>2020 年 8 月

### <a name="spotlight-insider-risk-and-communication-compliance-updates"></a>Spotlight: Insider リスクとコミュニケーションコンプライアンスの更新

いくつかの新機能と改善された機能が、今月公開プレビューに当たっています。

**インサイダー リスクの管理**

- 6 つの新しい [ポリシー テンプレートを確認してください](insider-risk-management-policies.md#policy-templates)。
    - 優先ユーザーによるデータ 漏洩
    - 不満を持つユーザーによるデータ リーク
    - 一般的なセキュリティ ポリシー違反
    - ユーザーの退出によるセキュリティ ポリシー違反
    - 優先度ユーザーによるセキュリティ ポリシー違反
    - 不満を持つユーザーによるセキュリティ ポリシー違反

- Microsoft [Defender for Endpoint との](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 統合により、新しいセキュリティ違反ポリシー テンプレートから作成されたポリシーによって検出されたアクティビティについて、Microsoft Defender for Endpoint アラートをインポートしてフィルター処理できます。 また、関連するインサイ[](insider-risk-management-settings.md#microsoft-defender-for-endpoint-preview)ダー リスク設定を使用して、Microsoft Defender for Endpoint アラート トリアージの状態に基づいて、セキュリティ アラートをインサイダー リスク管理にインポートすることもできます。

    > [!NOTE]
    > Microsoft Defender for Endpoint 統合 (新しいセキュリティ ポリシー違反テンプレートを含む) を利用するには、組織で Microsoft Defender for Endpoint を構成する必要があります。 また、Microsoft Defender for Endpoint の高度な機能を構成することで、インサイダー リスク管理統合のために Microsoft Defender for Endpoint を有効にする [必要があります](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)。
 
- ポリシーを作成するときにインジケーターの [しきい値をカスタマイズします](insider-risk-management-policies.md#create-a-new-policy)。
- 優先度の [高い](insider-risk-management-settings.md#priority-user-groups-preview) ユーザー グループを設定して、自分の位置、機密情報へのアクセスレベル、リスク履歴などの要因に基づいて、アクティビティの詳細な検査が必要な組織内のユーザーを定義します。
- 365 Officeアクティビティ API を使用して、[](insider-risk-management-settings.md#export-alerts-preview)インサイダー リスク アラートの詳細を組織がインサイダー リスク データの管理または集約に使用する可能性がある他のアプリケーションにエクスポートします。
- 新 [しいドメイン設定は](insider-risk-management-settings.md#domains-preview) 、特定のドメインでのアクティビティのリスク レベルを定義および制御するのに役立ちます。

**通信コンプライアンス**

- アラート [でメッセージを確認するときに](communication-compliance-investigate-remediate.md#step-3-decide-on-a-remediation-action)、Microsoft Teams チャネル、1:1、およびグループ チャットで不適切なメッセージを削除できます。 削除されたメッセージとコンテンツは、機密性の高いコンテンツのために削除されたと説明するポリシー ヒントに置き換えられる。
- 新 [しい通信役割](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance) (これらは、9 月にリリースされる新しい通信コンプライアンス役割グループにも含まれます)。
- プライバシーと通知テンプレートの設定を含む新しい[通信コンプライアンス](communication-compliance-feature-reference.md#privacy)[設定エクスペリエンス](communication-compliance-feature-reference.md#notice-templates)。
- 大人 [、人種、ゴー](communication-compliance-feature-reference.md#classifiers) リーの画像を検出するのに役立つ新しい分類子。
- アラートでメッセージを確認するときに表示される新しい[](communication-compliance-investigate-remediate.md#step-2-examine-the-message-details)「パターン検出」 通知を使用すると、ユーザーが同じ動作のインスタンスを再発生した場合について知る事が可能になります。

### <a name="sensitivity-labels"></a>秘密度ラベル

- 米国政府テナント (GCC、GCC-H、DoD) 向けの場合、秘密度ラベルが現在サポートされているのは、Azure Information Protection の統合ラベル付けクライアントおよびスキャナーのみです。 詳細については、[Azure Information Protection Premium の米国政府機関向けのサービスの説明](/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description)を参照してください。
- コンプライアンス センター [PowerShell &を](create-sensitivity-labels.md#use-powershell-for-sensitivity-labels-and-their-policies) 使用して、ラベル付け管理センターに表示される設定を作成および構成できます。 つまり、ラベル付け管理センターで使用できない設定に PowerShell を使用する以外に、感度ラベルと感度ラベル ポリシーの作成とメンテナンスを完全にスクリプト化できます。

### <a name="records-management-content-overhaul"></a>レコード管理: コンテンツのオーバーホール

展開手順、コンテンツをレコードとしてマークする、およびレコードのバージョン管理をカバーする新しいドキュメント。

- [レコード管理の使用を開始する](get-started-with-records-management.md)
- [保持ラベルを使用してレコードを宣言する](declare-records.md)
- [SharePoint または OneDrive に保存されているレコードを更新するためにレコードのバージョン管理を使用する](record-versioning.md)

### <a name="retention-labels--policies"></a>アイテム保持ラベル&ポリシー

保持関連の管理アクティビティが記録され、監査ログで確認できます。 完全なリストについては、「[アイテム保持ポリシーと保持ラベルのアクティビティ](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities)」を参照してください。

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

- コレクション [をレビュー セットに](add-data-to-review-set.md#define-options-to-scope-your-collection-for-review)追加するときに、モダンな添付ファイル ("クラウド添付ファイル" とも呼ばれる) と SharePoint ドキュメント バージョンを含めできます。
- 新 [しい直接ダウンロード エクスポート エクスペリエンス](export-documents-from-review-set.md)により、Azure Storage Explorer を使用してケース コンテンツをダウンロードする必要がなくなります。