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
description: コンプライアンス センターへの新しいソリューションの追加、フィードバックに基づく既存の機能の更新、最新の更新されたドキュメントの展開など、Microsoft 365 は変化し続けるコンプライアンス環境を常に改善するのに役立ちます。 今月の予定を確認します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 40140c950bb42078cb1e72ae74762db00a4516b6
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233165"
---
# <a name="whats-new-in-microsoft-365-compliance"></a>Microsoft 365 コンプライアンスの新機能

[Microsoft 365](microsoft-365-compliance-center.md)コンプライアンス センターへの新しいソリューションの追加、フィードバックに基づく既存の機能の更新、最新のドキュメントの展開など、Microsoft 365 は変化し続けるコンプライアンス状況を常に改善するのに役立ちます。 Microsoft 365 コンプライアンスの新機能については、以下をご覧ください。

> [!NOTE]
> 一部のコンプライアンス機能は、お客様に対して異なる速度で展開されます。 If you aren't seeing a feature yet, try adding yourself to [targeted release](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365).

> [!TIP]
> 他の管理センターで何が起こっていますか? 次の記事を参照してください。<br>[Microsoft 365 管理センターの新機能](https://docs.microsoft.com/office365/admin/whats-new-in-preview)<br>[SharePoint 管理センターの新機能](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center)<br>[Microsoft 365 Defender の新機能](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)<br><br>
また [、Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/roadmap) ロードマップにアクセスして、起動、展開中、開発中、キャンセル済み、以前にリリースされた Microsoft 365 の機能について説明します。

## <a name="january-2021"></a>2021 年 1 月

### <a name="support-for-card-content-in-teams"></a>Teams でのカード コンテンツのサポート

次の Microsoft 365 コンプライアンス ソリューションは[](https://docs.microsoft.com/microsoftteams/platform/task-modules-and-cards/what-are-cards)、Teams メッセージ内のアプリによって生成されたカード コンテンツの検出をサポートします。

- **コアおよび Advanced eDiscovery**。 カードのコンテンツを [保留にしたり](create-ediscovery-holds.md#preserve-card-content) 、検索に含める [(コンテンツ](https://docs.microsoft.com/microsoftteams/ediscovery-investigation#search-for-card-content) 検索にも適用される) ことが可能です。
- **監査**. カードアクティビティが [監査ログに記録されます](https://docs.microsoft.com/microsoftteams/audit-log-events#teams-activities)。
- **アイテム保持ポリシー**。 アイテム保持ポリシーを使用して、カード [のコンテンツを保持および削除できます](retention-policies-teams.md#whats-included-for-retention-and-deletion)。

### <a name="information-governance-and-records-management"></a>情報ガバナンスとレコード管理

[情報ガバナンスと](retention-regulatory-requirements.md#new-zealand-public-records-act) レコード管理の使用に対応する新しい評価。ニュージーランドの公的記録法のコンプライアンス義務を果たします。

### <a name="sensitivity-labels"></a>秘密度ラベル

- 米国政府機関向けテナント (GCC および GCC-H) では、感度ラベルがサポートされます。
- macOS [の新しい](sensitivity-labels-office-apps.md) 自動ラベル付けサポート。

## <a name="december-2020"></a>2020 年 12 月

### <a name="spotlight-new-content-for-insider-risk-solutions"></a>スポットライト: インサイダー リスク ソリューションの新しいコンテンツ

Microsoft 365 コンプライアンス コンテンツ チームは、コンプライアンスの目標を達成するためにコンプライアンス機能を一緒に使用する方法を促進するために、"コンテンツ ソリューション" ドキュメントの作成に取り組み中です。

まず、インサイダー リスク ソリューション (コミュニケーション コンプライアンス、インサイダー リスク管理、情報障壁、特権アクセス管理) を結び付け合うコンテンツです。 次に、表示される情報を示します。

- [インサイダー リスク ソリューションの新しいランディング ページ](insider-risk-solution-overview.md)。 ソリューションが軽減するのに役立つリスク、ライセンス要件、展開シーケンス、アーキテクチャの図、トレーニング リソースなどについての詳細が含まれています。
- 各インサイダー リスク ソリューションの新しい概要記事。 各ソリューションの学習、計画、展開、管理に役立つ記事へのガイダンスとリンクを示します。
  - [通信コンプライアンス](communication-compliance-solution-overview.md)
  - [インサイダー リスクの管理](insider-risk-management-solution-overview.md)
  - [情報障壁](information-barriers-solution-overview.md)
  - [特権アクセスの管理](privileged-access-management-solution-overview.md)
  
その他のコンテンツ ソリューション ドキュメントは近日公開予定です。

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

Advanced eDiscovery ケースに[保管](add-custodians-to-case.md)担当者と保管されていない[](non-custodial-data-sources.md)データ ソースを追加するためのワークフローと機能の強化。

### <a name="data-connectors"></a>データ コネクタ

[Redtail Speak、Salesforce](archiving-third-party-data.md#third-party-data-connectors)Chatter、ServiceNow、Yieldbroker の 4 つの新しい Globanet コネクタがリリースされました。

### <a name="encryption"></a>暗号化

テナント レベル [での Microsoft 365 のカスタマー キーの導入](customer-key-tenant-level.md)。 入力したキーを使用して、データ暗号化ポリシー (DEP) を作成し、それをテナントに割り当てできます。 DEP は、次のワークロードのデータをテナント全体で暗号化します。

- Teams のチャット メッセージ (1 対 1 のチャット、グループ チャット、会議チャット、チャネル会話)
- Teams のメディア メッセージ (画像、コード スニペット、ビデオ、Wiki 画像)
- Teams ストレージに保存された Teams の通話と会議のレコーディング
- Teams のチャット通知
- Cortana による Teams チャットの提案
- Teams のステータス メッセージ
- Exchange Online のユーザー情報とシグナル情報

### <a name="records-management"></a>レコード管理

レコード [管理管理役割グループは、廃棄](get-started-with-records-management.md#permissions-required-for-records-management) レビューを含むすべてのレコード管理機能に対するアクセス許可を付与します。

### <a name="sensitivity-labels"></a>秘密度ラベル

- [Azure Purview でデータに自動的にラベルを付け (プレビュー) します](https://docs.microsoft.com/azure/purview/create-sensitivity-label)。 Azure Purview のアセット (Azure Blob Storage 内のファイルや、SQL Server のデータベース列など) に、区別ラベルを作成して自動的に適用できます。
- [ユーザーがアイテムにラベルを適用する必要があります](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents)。 "必須のラベル付け" とも呼ばれるこの新しいオプションでは、ユーザーが特定のシナリオで区別ラベルを選択して適用する必要があります。

## <a name="november-2020"></a>2020 年 11 月
新しい機能や更新された機能をプレビュー状態でリリースして、その使い方を確認し、一般提供にリリースする前に改良を図る必要があります。 お客様からのフィードバックはプレビュー中 (およびそれ以降) に不可欠なので、コンプライアンス センターの右下にあるフィードバック カードを開いてご意見をお聞かせください。

![feedback](../media/Feedback_card_MCC.JPG)

### <a name="spotlight-endpoint-data-loss-prevention-dlp-released"></a>スポットライト: エンドポイント データ損失防止 (DLP) のリリース

[エンドポイント DLP は](endpoint-dlp-learn-about.md) 、DLP のアクティビティ監視および保護機能を Windows 10 デバイス上の機密情報に拡張します。 デバイスが[](dlp-configure-endpoints.md)Microsoft 365 コンプライアンス センターにオンボードされた後、DLP ポリシーを設定して、それらのデバイスの機密情報を保護できます。

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

電子情報開示ワークフローで暗号化されたコンテンツを簡単に管理するために、Microsoft 365 電子情報開示ツールには、[](ediscovery-decryption.md)電子メール メッセージに添付され、Exchange で送信される暗号化されたファイルの暗号化解除が組み込まれています。 さらに、SharePoint と OneDrive に保存されている暗号化されたドキュメントは、Advanced eDiscovery で復号化されます。

### <a name="compliance-manager"></a>コンプライアンス マネージャー

- [Microsoft 365 Government サブスクリプションのサポート](compliance-manager.md)。 コンプライアンス マネージャーは、米国政府機関向けコミュニティ (GCC) の中および高のお客様が利用できます。
- [コンプライアンス マネージャー用の Microsoft Compliance Configuration Analyzer](compliance-manager-mcca.md)。 組織の現在の構成をスキャンし、Microsoft 365 の推奨ベスト プラクティスに対して検証することで、コンプライアンス マネージャーの使用を開始するのに役立つ新しい PowerShell ベースのツール。
- [新しいテンプレート](compliance-manager-templates-list.md)。 56 の新しいテンプレートが追加され、コンプライアンス マネージャーテンプレートの合計は 230 を超えました。

### <a name="data-connectors"></a>データ コネクタ

[プレビューで 5 つの新しい Globanet コネクタ](archiving-third-party-data.md#third-party-data-connectors)。 新しいコネクタには、Reuters Dealing、Reuters FX、CellTrust、XIP、汎用 MS SQL データベース データが含まれます。

### <a name="retention-labels-disposition-review"></a>保持ラベル (廃棄レビュー)

廃棄レビュー中にアイテムを表示するには、コンテンツ エクスプローラーのコンテンツ ビューアーおよびコンテンツ エクスプローラーのリスト ビューアー役割グループのメンバーである [必要があります](disposition.md#permissions-for-disposition)。 アイテムの確認は必須ですが、これらの役割グループは廃棄レビューを完了するために必要ありません。

### <a name="sensitivity-labels"></a>秘密度ラベル

- [(プレビュー) SharePoint サイトの外部共有設定](sensitivity-labels-teams-groups-sites.md#how-to-configure-groups-and-site-settings)。 グループとサイトに使用するラベルを作成する場合、ラベルが適用されている SharePoint サイトの外部共有を制御するオプションが表示されます。 組織内のすべてのユーザー、新規および既存のゲスト、既存のゲストのみ、または組織内のユーザーに対して共有を許可できます。 ラベルが適用されると、ラベル設定は SharePoint 管理センターで構成された外部共有設定 [に置き換わるものになります](https://docs.microsoft.com/sharepoint/change-external-sharing-site)。
- [ラベル付きドキュメントからラベルと暗号化を削除します](sensitivity-labels-sharepoint-onedrive-files.md#remove-encryption-for-a-labeled-document)。 ラベルと、ラベルが適用する暗号化の両方を SharePoint のラベル付きドキュメントから削除するために、グローバル管理者と SharePoint 管理者は新しいコマンドレットを実行 `Unlock-SPOSensitivityLabelEncryptedFile` できます。 このコマンドレットは、管理者がサイトまたはファイルに対するアクセス許可を持たなかったり、Azure Rights Management サービスが利用できない場合でも実行されます。

## <a name="october-2020"></a>2020 年 10 月

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

[CJK 言語サポート](ediscovery-cjk-support.md)。 Advanced eDiscovery では、CJK 言語と総称される 2 バイト文字セット言語 (簡体字中国語、繁体字中国語、日本語、韓国語を含む) がサポートされます。 これらは、いくつかの高度なレビュー セット シナリオで使用できます。

### <a name="sensitivity-labels"></a>秘密度ラベル

- [ラベルの範囲](sensitivity-labels.md#label-scopes)。 ラベルを作成するときに、ラベルの範囲を定義する新しいオプションが表示されます。 このオプションでは、ファイルとメール、コンテナー (SharePoint サイトや Teams など)、または両方のラベルを構成できます。
- [動的なコンテンツのマーキング](sensitivity-labels-office-apps.md#dynamic-markings-with-variables)。 機度ラベルのコンテンツ マーキングを構成する際に、ヘッダー、フッター、透かしなどの動的変数と、ヘッダー、フッター、透かしのテキスト文字列を `${Item.Label}` `${Item.Location}` 使用できます。

## <a name="september-2020"></a>2020 年 9 月

### <a name="spotlight-compliance-manager"></a>スポットライト: コンプライアンス マネージャー

今年 Ignite で発表されたコンプライアンス スコアは、コンプライアンス マネージャーとして [再ブランドされています](compliance-manager.md)。 このリリースでは、Service Trust Portal のコンプライアンス マネージャーの以前のホームからの移行が完了し、Microsoft 365 コンプライアンス センターにエンドツーエンドのコンプライアンス管理ソリューションが導入されています。

コンプライアンス マネージャーが組織でコンプライアンスを管理する方法を簡素化する方法については、以下のビデオをご覧ください。
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4FGYZ]

### <a name="advanced-audit"></a>高度な監査

- 監査ログの新しい 10 年間の保持は、長期の調査をサポートし、規制、法律、および内部の義務に対応するのに役立ちます。
- [3 つの新しい重要なイベント](advanced-audit.md#access-to-crucial-events-for-investigations)。 次の新しいイベントは、発生する可能性がある侵害を調査し、侵害の範囲 (Send、SearchQueryInitiatedExchange、SearchQueryInitiatedSharePoint) を特定するのに役立ちます。

### <a name="communication-compliance"></a>コミュニケーション コンプライアンス

- [役割グループを更新しました](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance)。 通信コンプライアンス役割グループは、インサイダー リスク管理ソリューションで使用可能な役割グループ構造と一致する必要があります。
- [レポート ダッシュボード](communication-compliance-feature-reference.md#reports-preview)。 すべての通信コンプライアンス レポートを表示する中心的な場所。 レポート ウィジェットは、通信コンプライアンス アクティビティの状態を全体的に評価するために最も一般的に必要な分析情報のクイック ビューを提供します。
- [Power Automate フロー](communication-compliance-feature-reference.md#power-automate-flows)。 フローを設定して、アラートとユーザーのタスクを自動化し、ユーザーがアラートをトリガーした場合にマネージャーに通知します。
- ['分類の改善' 修復アクション](communication-compliance-investigate-remediate.md#step-3-decide-on-a-remediation-action)。 トレーニング可能な分類子に一致するアイテムを含むアラートは、組織内の誤検知を最小限に抑えるためにフィードバックを利用できる場合があります。 分類 **の改善オプション** を使用すると、検出されたアイテムが関連する通信コンプライアンス ポリシーで構成されている分類子と一致するかどうかをフィードバックできます。 他の分類子を提案してアイテムに関連付け、今後のアラートの一致精度を向上させる場合があります。

### <a name="data-connectors"></a>データ コネクタ

- [新しいサードパーティのデータ コネクタ](archiving-third-party-data.md#third-party-data-connectors)。 Globanet から 14 個、Telemessage から 8 個を含む 25 個の新しいデータ コネクタ。
- [物理バグコネクタ](import-physical-badging-data.md)。 従業員の生の物理的なアクセス イベントや、組織の不良システムによって生成された物理的なアクセス アラームなど、物理的な不良データをインポートします。 たとえば、建物、サーバー ルーム、またはデータ センターへのエントリが含まれます。 インサイダー リスク管理ソリューションは、物理的な不正なデータを使用して、組織内の悪意のある活動やデータの盗難から組織を保護できます。

### <a name="insider-risk-management"></a>インサイダー リスクの管理

- [Microsoft Teams の統合](insider-risk-management-settings.md#microsoft-teams-preview)。 インサイダー リスク設定で Teams の統合が有効になっている場合は、個々のケースに関連するデータの安全な共有と保存、アナリストや調査担当者からの対応活動の追跡と確認などのタスクについて、Teams の他の関係者と調整して共同作業できます。
- [Power Automate フロー](insider-risk-management-settings.md#power-automate-flows-preview)。 ユーザー、アラート、ケース情報の取得、関係者や他のアプリと共有するケース情報の取得、ケース ノートへの投稿などのアクションの自動化など、ケースとユーザーの重要なタスクを自動化するためのフローを設定します。
- [アクティビティ エクスプローラー](insider-risk-management-alerts.md#activity-explorer-preview)。 アラートを確認するときに利用できるアクティビティ エクスプローラーは、調査担当者とアナリストに、各アラートを詳細に掘り下ろす包括的な分析ツールを提供します。 検出された危険なアクティビティのタイムラインをすばやく確認し、アラートに関連付けられているすべてのリスク アクティビティを特定してフィルター処理します。

### <a name="retention-policies-and-retention-labels"></a>アイテム保持ポリシーと保持ラベル

- [この機能のYammer。](retention-policies-yammer.md) アイテム保持ポリシーを使用して、コミュニティ メッセージやプライベート メッセージYammer保持および削除できます。
- [Teams 会議のレコーディングにラベルを適用します](apply-retention-labels-automatically.md#microsoft-teams-meeting-recordings)。 自動ラベル付けポリシーを作成する場合は、キーワード クエリ エディターを使用して、ユーザーの OneDrive アカウントまたは SharePoint に保存されている Teams 会議のレコーディングを識別します。

### <a name="records-management"></a>レコード管理

[規制記録のサポート](declare-records.md#how-to-display-the-option-to-mark-content-as-a-regulatory-record)。 ラベルを規制レコードとして分類すると、ラベルが適用されるコンテンツに対する制限が増加し、ラベル自体に対して使用可能な管理アクションが制限されます。 たとえば、コンテンツに適用した後は、グローバル管理者でなくても誰もラベルを削除できます。 [規制レコード](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked) に対して許可およびブロックするアクションについて詳しくは、以下を参照してください。

### <a name="sensitivity-labels"></a>秘密度ラベル

[米国政府機関のお客様向けサポート](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description)。 これで、GCC、GCC High、DoD の顧客に対して、Azure Information Protection 統合ラベル付けクライアントとスキャナーのラベル付けだけがサポートされます。

### <a name="trainable-classifiers"></a>トレーニング可能な分類子

新しい再トレーニング機能とフィードバック機能は、精度を向上し、すべてのカスタム分類子といくつかの事前トレーニング済みの分類子に対する誤検知の一致を最小限に抑えるのに役立ちます。 このフローを使用すると、アイテムが特定の分類子と一致するかどうかに関するフィードバックを提供し、他の分類子がアイテムに関連付けるかどうかを提案し、分類子を再トレーニングして一致精度を調整および向上できます。

この新機能は、次の機能に含まれています。

> [!NOTE]
> すべての機能について、少なくとも 30 件のフィードバック応答を提供する場合は、レビュー可能な再トレーニングされたバージョンの分類子が作成されます。 改善された場合は、分類子を再発行できます。

- [トレーニング可能な分類子](classifier-learn-about.md#retraining-classifiers)。 発行された分類子の精度を向上させるために、検出されたアイテムが分類子と一致するかどうかに関するフィードバックを提供できます。
- [通信コンプライアンス](classifier-how-to-retrain-comms-compliance.md)。 新しい **分類改善** 修復アクションを使用すると、通信コンプライアンスアラートのアイテムが通信コンプライアンス ポリシーで構成された分類子と一致するかどうかをフィードバックできます。
- [コンテンツ エクスプローラー](classifier-how-to-retrain-content-explorer.md)。 トレーニング可能な分類子に一致する電子メール メッセージにラベルを自動的に適用する保持自動ラベル付けポリシーを設定した場合は、コンテンツ エクスプローラーを使用してラベル付けされたアイテムを確認し、アイテムが分類子と一致するかどうかをフィードバックできます。

## <a name="august-2020"></a>2020 年 8 月

### <a name="spotlight-insider-risk-and-communication-compliance-updates"></a>スポットライト: インサイダー リスクと通信コンプライアンスの更新

毎月、いくつかの新機能と強化された機能がパブリック プレビューにヒットしました。

**インサイダー リスクの管理**

- 6 つの新しいポリシー [テンプレートを確認してください](insider-risk-management-policies.md#policy-templates)。
    - 優先度の高いユーザーによるデータ漏洩
    - 不満を持つユーザーによるデータ漏洩
    - 一般的なセキュリティ ポリシー違反
    - 権限を持つユーザーによるセキュリティ ポリシー違反
    - 優先度ユーザーによるセキュリティ ポリシー違反
    - 不満を持つユーザーによるセキュリティ ポリシー違反

- Microsoft [Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) との統合により、新しいセキュリティ違反ポリシー テンプレートから作成されたポリシーによって検出されたアクティビティについて、Microsoft Defender for Endpoint のアラートをインポートしてフィルター処理できます。 また、関連するインサイ[](insider-risk-management-settings.md#microsoft-defender-for-endpoint-preview)ダー リスクの設定では、Microsoft Defender for Endpoint の警告トリアージの状態に基づいて、インサイダー リスク管理にセキュリティの警告をインポートできます。

    > [!NOTE]
    > Microsoft Defender for Endpoint 統合 (新しいセキュリティ ポリシー違反テンプレートを含む) を利用するには、組織で Microsoft Defender for Endpoint を構成する必要があります。 また、Microsoft Defender for Endpoint の高度な機能を構成して、インサイダー リスク管理統合のために Microsoft Defender for Endpoint を有効 [にする必要があります](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)。
 
- ポリシーを作成するときにインジケーターのしきい [値をカスタマイズします](insider-risk-management-policies.md#create-a-new-policy)。
- 優先度の [ユーザー グループ](insider-risk-management-settings.md#priority-user-groups-preview) を設定して、位置、機密情報へのアクセスレベル、リスク履歴などの要因に基づいて、アクティビティの詳細な検査が必要な組織内のユーザーを定義します。
- 365 Officeアクティビティ API を使用して、[](insider-risk-management-settings.md#export-alerts-preview)インサイダー リスク アラートの詳細を、組織がインサイダー リスク データの管理または集計に使用する可能性がある他のアプリケーションにエクスポートします。
- 新 [しいドメイン設定は](insider-risk-management-settings.md#domains-preview) 、特定のドメインでのアクティビティのリスク レベルを定義および制御するのに役立ちます。

**通信コンプライアンス**

- アラート [でメッセージを](communication-compliance-investigate-remediate.md#step-3-decide-on-a-remediation-action)確認するときに、Microsoft Teams チャネル、1 対 1、およびグループ チャットで不適切なメッセージを削除できます。 削除されたメッセージとコンテンツは、機密性の高いコンテンツのために削除されたというポリシー ヒントに置き換えられる。
- 新 [しい通信役割](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance) (9 月にリリースされる新しい通信コンプライアンス役割グループにも含まれます)。
- プライバシーと通知テンプレートの設定 [を含む](communication-compliance-feature-reference.md#privacy) 新しい通信コンプライアンス [設定エクスペリエンス](communication-compliance-feature-reference.md#notice-templates)。
- 成人 [向け、](communication-compliance-feature-reference.md#classifiers) 不器用、不作作な画像の検出に役立つ新しい分類子。
- アラート内のメッセージを確認するときに表示される新しい[](communication-compliance-investigate-remediate.md#step-2-examine-the-message-details)"パターン検出" 通知により、ユーザーが同じ動作のインスタンスを再発生した場合を確認できます。

### <a name="sensitivity-labels"></a>秘密度ラベル

- 米国政府テナント (GCC、GCC-H、DoD) 向けの場合、秘密度ラベルが現在サポートされているのは、Azure Information Protection の統合ラベル付けクライアントおよびスキャナーのみです。 詳細については、[Azure Information Protection Premium の米国政府機関向けのサービスの説明](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description)を参照してください。
- セキュリティ/ [コンプライアンス センターの PowerShell &](create-sensitivity-labels.md#use-powershell-for-sensitivity-labels-and-their-policies) 使用して、ラベル付け管理センターに表示される設定を作成して構成できます。 つまり、ラベル付け管理センターでは使用できない設定に PowerShell を使用する以外に、ラベル付けラベルと感度ラベル ポリシーの作成と保守を完全にスクリプト化できます。

### <a name="records-management-content-overhaul"></a>レコード管理: コンテンツのオーバーホール

展開手順、コンテンツをレコードとしてマーク、およびレコードのバージョン管理に関する新しいドキュメント:

- [レコード管理の使用を開始する](get-started-with-records-management.md)
- [保持ラベルを使用してレコードを宣言する](declare-records.md)
- [SharePoint または OneDrive に保存されているレコードを更新するためにレコードのバージョン管理を使用する](record-versioning.md)

### <a name="retention-labels--policies"></a>保持ラベルと&ポリシー

保持関連の管理者アクティビティが記録され、監査ログで確認できます。 完全なリストについては、「[アイテム保持ポリシーと保持ラベルのアクティビティ](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities)」を参照してください。

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

- コレクション [をレビュー セットに](add-data-to-review-set.md#define-options-to-scope-your-collection-for-review)追加するときに、モダン添付ファイル (「クラウド添付ファイル」とも呼ばれる) と SharePoint ドキュメント バージョンを含めできます。
- 新 [しい直接ダウンロードエクスポート エクスペリエンス](export-documents-from-review-set.md)により、ケースのコンテンツをダウンロードするために Azure Storage Explorer を使用する必要がなくなります。
