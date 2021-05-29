---
title: Microsoft 365 コンプライアンスの新機能
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
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
description: コンプライアンス センターに新しいソリューションを追加する場合、フィードバックに基づいて既存の機能を更新する場合、新しく更新されたドキュメントを展開する場合でも、Microsoft 365 を使用すると、変化し続けるコンプライアンス環境の上に立ち続けるのに役立ちます。 今月までの予定を確認します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ae1df2ce6373e4a8f6b01c33e50bea5e6c16ca0a
ms.sourcegitcommit: 4bcac4cb4f9399ebbd7c8cff0abb4d6ecedb731e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2021
ms.locfileid: "52698954"
---
# <a name="whats-new-in-microsoft-365-compliance"></a>Microsoft 365 コンプライアンスの新機能

Microsoft 365 コンプライアンス センターに新しいソリューションを追加する場合、フィードバックに基づいて既存の機能を更新する場合、新しく更新されたドキュメントを展開する場合でも[、Microsoft 365](microsoft-365-compliance-center.md)を使用すると、変化し続けるコンプライアンス環境の上に立ち続けるのに役立ちます。 今日のコンプライアンスに関する新機能については、以下Microsoft 365してください。

> [!NOTE]
> 一部のコンプライアンス機能は、お客様に異なる速度で展開されます。 まだ機能が表示されない場合は、ターゲットリリースに自分自身を [追加してみてください](/office365/admin/manage/release-options-in-office-365)。

> [!TIP]
> 他の管理センターで何が起こっているのか興味がありますか? 次の記事を参照してください。<br>[管理センターの新機能Microsoft 365](/office365/admin/whats-new-in-preview)<br>[SharePoint 管理センターの新機能](/sharepoint/what-s-new-in-admin-center)<br>[Microsoft 365 Defender の新機能](../security/defender/whats-new.md)<br><br>
また、「Microsoft 365[](https://www.microsoft.com/microsoft-365/roadmap)ロードマップ」を参照して、Microsoft 365、展開中、開発中、キャンセル済み、または以前にリリースされた機能について説明します。

## <a name="april-2021"></a>2021 年 4 月

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

- [Advanced eDiscovery](/microsoft-365/compliance/limits-ediscovery20#export-limits---final-export-out-of-review-set)の制限。 組織は、レビュー セットからアイテムを 1 回エクスポートする場合に、最大 500 万アイテムまたは 500 MB をエクスポートできます(小さい方)。

### <a name="data-classification"></a>データ分類

- [アクティビティ エクスプローラーで使用できるアクティビティのラベル付け](/microsoft-365/compliance/data-classification-activity-explorer-available-events)

### <a name="data-connectors"></a>データ コネクタ

- [Oracle データで Cisco Jabber をアーカイブするコネクタをセットアップする]/microsoft-365/compliance/archive-ciscojabberonoracle-data)
- [PostgreSQL データで Cisco Jabber をアーカイブするコネクタをセットアップする](/microsoft-365/compliance/archive-ciscojabberonpostgresql-data)

### <a name="data-loss-prevention"></a>データ損失防止

- データ損失防止ポリシー [のヒントリファレンスの新しいトピック](/microsoft-365/compliance/dlp-policy-tips-reference)です。
- 「データ損失 [防止について」の新しいトピックを参照してください](/microsoft-365/compliance/dlp-learn-about-dlp)。
- 「データ損失 [防止アラート ダッシュボードの使用を開始する」の新しいトピック](/microsoft-365/compliance/dlp-alerts-dashboard-get-started)です。

### <a name="retention-policies-and-retention-label-policies"></a>アイテム保持ポリシーと保持ラベル ポリシー

- Microsoft 365 グループの場所では、Applications パラメーターを使用して[Set-RetentionCompliancePolicy PowerShell](/powershell/module/exchange/set-retentioncompliancepolicy)コマンドレットを使用して、Microsoft 365 メールボックスまたは接続された SharePoint サイトへの保持設定の適用がサポートされています。

### <a name="sensitivity-labels"></a>秘密度ラベル

Outlookと更新プログラム:
- 以前は AIP 統合ラベル付けクライアントでのみサポートされ、組み込みのラベル付けは既定のラベルと必須ラベル付けの異なる設定 [をサポートしています](sensitivity-labels-office-apps.md#outlook-specific-options-for-default-label-and-mandatory-labeling)
- Encrypt-Only macOS、iOS、Android でサポートされる
- [Office](/microsoft-365/compliance/sensitivity-labels-office-apps)アプリのトピックで、Outlook 機能テーブルの [既定のラベルの異なる設定] の新[](/microsoft-365/compliance/sensitivity-labels-office-apps#outlook-specific-options-for-default-label-and-mandatory-labeling)しいエントリで更新され、組み込みのラベル付け用の新しい[Outlook](/microsoft-365/compliance/sensitivity-labels-office-apps#sensitivity-label-capabilities-in-outlook)機能リリースの必須ラベル付けが更新され、別の既定のラベルをサポートし、必須ラベル付けが適用されません。 さらに、Encrypt-Only オプションは macOS/iOS/Android でサポートされ、変数を含むすべての動的マーキングがすべての Outlook クライアントでサポートされています。 現在、必須のラベル付けは残りのプラットフォームに展開されています。

## <a name="march-2021"></a>2021 年 3 月

3 月のコンプライアンス ソリューションとMicrosoft 365の変更点を次に示します。

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

- **Advanced eDiscoveryコレクションは、新** しいコレクション ツール [とワークフローをサポートしています](/microsoft-365/compliance/collections-overview)。 その他の新しいトピックには、下書きコレクションの [作成](https://docs.microsoft.com/microsoft-365/compliance/create-draft-collection)、 [下](/microsoft-365/compliance/commit-draft-collection)書きコレクションをレビュー セットにコミットする、コレクションの統計情報 [とレポートが含まれます](/microsoft-365/compliance/collection-statistics-reports)。
- **レビュー セット内の** ドキュメントをユーザーアカウントに [Azure Storage](/microsoft-365/compliance/download-export-jobs)します。
- **予測コーディング モジュール (Advanced eDiscovery)** まず、廃止された関連性 [モジュール](/microsoft-365/compliance/predictive-coding-overview) に代わる新しい予測コーディング機能について説明します。

### <a name="data-classification"></a>データの分類

- **データ分類エクスプローラー**。 [データ分類](/microsoft-365/compliance/data-classification-activity-explorer) エクスプローラーの使用を開始します。

### <a name="data-connectors"></a>データ コネクタ

- **プライベート キー**。 ブルームバーグ メッセージ データ[、ICE](/microsoft-365/compliance/archive-icechat-data#set-up-a-connector-using-public-keys) [](/microsoft-365/compliance/archive-bloomberg-message-data#set-up-a-connector-using-public-keys)チャット データ、インスタント ブルームバーグ データ コネクタに、プライベート キーのサポート[が](/microsoft-365/compliance/archive-instant-bloomberg-data#set-up-a-connector-using-public-keys)追加されました。

### <a name="data-loss-prevention"></a>データ損失防止

- **Microsoft Teamsサポート**. データ損失防止のサポートは、データ損失[Microsoft Teams。](/microsoft-365/compliance/dlp-teams-default-policy)
- **Microsoft Compliance extension**. Microsoft コンプライアンス拡張機能 [の使用を開始します](/microsoft-365/compliance/dlp-chrome-get-started)。

### <a name="encryption"></a>暗号化

- **顧客キーのMicrosoft 365。** [テナント レベル (パブリック プレビュー](/microsoft-365/compliance/customer-key-tenant-level) ) Microsoft 365顧客キーの概要。
- **二重キー暗号化**. ラベル付き[ドキュメントと](/microsoft-365/compliance/double-key-encryption)保護されたドキュメントのサポートを有効にする方法の詳細については、SharePointおよびOneDrive for Business。

### <a name="insider-risk-management"></a>インサイダー リスクの管理

3 月にパブリック プレビュー用にリリースされたインサイダー リスク管理機能の更新プログラムは次のとおりです。

- インサイダー リスク ポリシーを作成する前にリスクを特定するための新しい分析機能
- 新しいリスク アクティビティ シーケンス検出のサポートと管理
- 新しい累積的な外用検出のサポート
- 新しいアプリ内ポリシーの正常性レポートと推奨事項のサポート
- 新しい監査ログ機能とレポート
- ポリシー作成ウィザードの機能強化
- コンテンツ エクスプローラーの更新
- 新しいユーザー管理プロセス/サポート (ポリシーからユーザーを追加または削除する)
- AAD 統合の新しいサポート (ユーザー ポリシーのサポートを開始する)
- ポリシーでのドメイン サポートの更新 (REGEX)
- ポリシー テンプレートの機能強化と改善

次のトピックは、これらの新機能をサポートするために更新または追加されました。

- [インサイダー リスク管理の詳細](/microsoft-365/compliance/insider-risk-management)
- [インサイダー リスク管理のための計画](/microsoft-365/compliance/insider-risk-management-plan)
- [インサイダーリスク管理設定の使用を開始する](/microsoft-365/compliance/insider-risk-management-settings)
- [インサイダー リスクの管理の概要](/microsoft-365/compliance/insider-risk-management-configure)
- [インサイダー リスク ポリシーを作成して管理する](/microsoft-365/compliance/insider-risk-management-policies)
- [インサイダー リスクのアラートを調査する](/microsoft-365/compliance/insider-risk-management-alerts)
- [インサイダー リスクのケースに対処する](/microsoft-365/compliance/insider-risk-management-cases)
- [インサイダーリスク監査ログを使用してアクティビティを確認する](/microsoft-365/compliance/insider-risk-management-audit-log)
- [インサイダー リスク コンテンツ エクスプローラーを使用してデータを確認する](/microsoft-365/compliance/insider-risk-management-content-explorer)
- [ユーザー ダッシュボードを使用してワークフローを管理する](/microsoft-365/compliance/insider-risk-management-users)

### <a name="records-management"></a>レコード管理

- **ファイル計画の改善**。 ファイル プランを [更新すると](file-plan-manager.md) 、以前のインポートの長さの制限が削除または改善されます。
- **レコードの保持ラベルを削除します**。 プレビュー リリースでは、アイテムをレコードとして [マークする保持ラベル](create-apply-retention-labels.md#deleting-retention-labels) を削除する機能がサポートされています。

### <a name="sensitive-information-types"></a>機密情報の種類

次のトピックでコンテンツが追加または更新されました。

- [カスタム機密情報の種類の使用を開始する](/microsoft-365/compliance/create-a-custom-sensitive-information-type)
- [機密情報の種類に関する詳細情報](/microsoft-365/compliance/sensitive-information-type-learn-about)
- [Exact Data Match に基づく分類で、カスタムの機密情報の種類を作成する](/microsoft-365/compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification)
- [完全なデータ一致アクティビティの通知を作成する](/microsoft-365/compliance/sit-edm-notifications-activities)
- [機密情報の種類エンティティ定義](/microsoft-365/compliance/sensitive-information-type-entity-definitions)
- [PowerShell を使用してカスタム機密情報の種類を作成する](/microsoft-365/compliance/create-a-custom-sensitive-information-type-in-scc-powershell)
- [キーワード辞書を作成する](/microsoft-365/compliance/create-a-keyword-dictionary)

### <a name="sensitivity-labels"></a>秘密度ラベル

- **DoD のサポート**。 DoD 環境を使用した米国政府機関テナントのサポート。
- **[暗号化のみ] を使用Outlook。** [ユーザーにアクセス許可Outlook割りEncrypt-Onlyを許可する] を選択すると、暗号化オプションにアクセス[許可が追加されます](encryption-sensitivity-labels.md#let-users-assign-permissions)。
- **アプリに組み込みのラベルをOfficeします**。 Azure [](sensitivity-labels-office-apps.md#office-built-in-labeling-client-and-the-azure-information-protection-client) Information Protection 統合ラベル付けクライアントがインストールされている場合に、Officeアプリに組み込みラベルを適用する方法のガイダンスが更新されました。

## <a name="february-2021"></a>2021 年 2 月

2 月のコンプライアンス ソリューションMicrosoft 365コンテンツに対する変更点を次に示します。

### <a name="auditing"></a>監査

- **監査ログ保持ポリシーを管理します**。 新しい監査保持ポリシー [ダッシュボードの詳細については、以下を参照してください](/microsoft-365/compliance/audit-log-retention-policies#manage-audit-log-retention-policies-1)。
- **監査ログを検索します**。 [PowerShell スクリプトを使用して監査ログを検索します](/microsoft-365/compliance/audit-log-search-script)。

### <a name="data-classification-content-explorer"></a>データ分類コンテンツ エクスプローラー

次のトピックでコンテンツが追加または更新されました。

- [コンテンツ エクスプローラーの使用を開始する](/microsoft-365/compliance/data-classification-content-explorer)
- [データ分類のリリース ノート](/microsoft-365/compliance/data-classification-pub-preview-relnotes)

### <a name="data-loss-prevention"></a>データ損失防止

次のトピックでコンテンツが追加または更新されました。

- [エンドポイント DLP の詳細](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about)
- [メール通知を送信して、DLP ポリシーのヒントを表示する](https://docs.microsoft.com/microsoft-365/compliance/use-notifications-and-policy-tips)
- [データ損失防止Microsoft 365オンプレミス スキャナーの詳細](https://docs.microsoft.com/microsoft-365/compliance/dlp-on-premises-scanner-learn)
- [データ損失防止オンプレミス スキャナーの使用を開始する](https://docs.microsoft.com/microsoft-365/compliance/dlp-on-premises-scanner-get-started)
- [FCI または他のプロパティを含むドキュメントを保護するために DLP ポリシーを作成する](https://docs.microsoft.com/microsoft-365/compliance/protect-documents-that-have-fci-or-other-properties)
- [エンドポイントのデータ損失防止の使用](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-using)
- [エンドポイント データ損失防止の使用を開始する](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-getting-started)

### <a name="ediscovery"></a>電子情報開示

次のトピックでコンテンツが追加または更新されました。

- [電子情報開示ツールMicrosoft 365復号化](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-decryption)
- [キーワード クエリと検索条件](https://docs.microsoft.com/microsoft-365/compliance/keyword-queries-and-search-conditions#limitations-for-searching-sensitive-data-types)
- [[関連] モジュールを使用Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/relevance-module-retirement)
- [スクリプトを使用してコア電子情報開示ケースの保留リストにユーザーを追加する](https://docs.microsoft.com/microsoft-365/compliance/use-a-script-to-add-users-to-a-hold-in-ediscovery)

### <a name="encryption"></a>暗号化

次のトピックでコンテンツが追加または更新されました。

#### <a name="azure-rights-management-service-rms"></a>Azure Rights Management Service (RMS)

- [顧客により管理される暗号化機能](https://docs.microsoft.com/microsoft-365/compliance/office-365-customer-managed-encryption-features)
- [Exchange Online RMS を使用してメールAD暗号化を行います](https://docs.microsoft.com/microsoft-365/compliance/information-rights-management-in-exchange-online)。 このサービスのサポートは廃止されました。 ハイブリッド環境では、AD RMS Exchange使用できなくなりました。 代わりに、Azure RMS に移行します。

#### <a name="customer-key"></a>顧客キー

- [テナント レベルMicrosoft 365顧客キー](https://docs.microsoft.com/microsoft-365/compliance/customer-key-tenant-level)
- [セキュリティとコンプライアンスの概要](https://docs.microsoft.com/microsoftteams/security-compliance-overview)

#### <a name="information-rights-management-irm"></a>Information Rights Management (IRM)

- [リストまたはライブラリに Information Rights Management (IRM) を適用します](https://docs.microsoft.com/microsoft-365/compliance/configure-irm-to-use-an-on-premises-ad-rms-server)。 これらの国内クラウドでは、この設定はサポートされていません。
    - Microsoft Cloud for US Government
    - Microsoft Cloud Germany
    - Azure と Microsoft 365 21Vianet が中国で運用)
- [RMS サーバーでオンプレミスのサーバーを使用AD IRM を構成します](https://docs.microsoft.com/microsoft-365/compliance/configure-irm-to-use-an-on-premises-ad-rms-server)。 ハイブリッド環境でのこのサービスExchangeは廃止されました。

### <a name="sensitive-information-types"></a>機密情報の種類

次のトピックでコンテンツが追加または更新されました。

- [機密情報の種類に関する詳細情報](https://docs.microsoft.com/microsoft-365/compliance/sensitive-information-type-learn-about)
- [PowerShell を使用してカスタムの機密情報の種類を作成する](https://docs.microsoft.com/microsoft-365/compliance/create-a-custom-sensitive-information-type-in-scc-powershell)
- [完全データ一致ベースの分類を使用してカスタム機密情報の種類を作成する](https://docs.microsoft.com/microsoft-365/compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification)
- [機密情報の種類のエンティティ定義](https://docs.microsoft.com/microsoft-365/compliance/sensitive-information-type-entity-definitions)


### <a name="sensitivity-labels"></a>秘密度ラベル

次のトピックでコンテンツが追加または更新されました。

- **SharePoint共有を行います**。 コンテナー[ラベルの](sensitivity-labels-teams-groups-sites.md)場合は、サイトからの外部共有SharePoint一般公開されました。 さらに、管理者センター Microsoft 365 Planner は、これらの感度ラベルの適用をサポートしています。 
- **共同編集と自動保存**。 暗号化された [ファイルの共同編集と自動保存](sensitivity-labels-coauthoring.md) のサポートは、非実稼働テナントでのテストのプレビューとしてリリースされます。

## <a name="january-2021"></a>2021 年 1 月

### <a name="support-for-card-content-in-teams"></a>カード コンテンツのサポート (Teams

コンプライアンス ソリューションMicrosoft 365、アプリを介して生成されたカード[](/microsoftteams/platform/task-modules-and-cards/what-are-cards)コンテンツの検出を、メッセージ内でサポートTeamsしています。

- **コアとAdvanced eDiscovery**. カード コンテンツを保留 [にしたり](create-ediscovery-holds.md#preserve-card-content) 、検索に含め [したりできます](/microsoftteams/ediscovery-investigation#search-for-card-content) (コンテンツ検索にも適用されます)。
- **監査**. これで、カードアクティビティ [が監査ログに記録されます](/microsoftteams/audit-log-events#teams-activities)。
- **アイテム保持ポリシー**。 アイテム保持ポリシーを使用して、カード [コンテンツを保持および削除できます](retention-policies-teams.md#whats-included-for-retention-and-deletion)。

### <a name="information-governance-and-records-management"></a>情報ガバナンスとレコード管理

[ニュージーランド公的](retention-regulatory-requirements.md#new-zealand-public-records-act) 記録法のコンプライアンス義務を満たすのに役立つ情報ガバナンスとレコード管理を使用して対処するための新しい評価。

### <a name="sensitivity-labels"></a>秘密度ラベル

- 米国政府機関のテナント (GCC および GCC-H) では、GCCラベルがサポートされています。
- macOS [の新しい自動](sensitivity-labels-office-apps.md) ラベル付けサポート。

## <a name="december-2020"></a>2020年12月

### <a name="spotlight-new-content-for-insider-risk-solutions"></a>スポットライト: インサイダー リスク ソリューションの新しいコンテンツ

コンプライアンス Microsoft 365チームは、コンプライアンスの目標を達成するためにコンプライアンス機能を一緒に使用する方法を促進するために、"コンテンツ ソリューション" ドキュメントを作成する作業に取り組む必要があります。

まず、コミュニケーションコンプライアンス、インサイダーリスク管理、情報障壁、特権アクセス管理など、インサイダーリスクソリューションを結び付け合うコンテンツです。 次に、見つけた情報を示します。

- [インサイダー リスク ソリューションの新しいランディング ページ](insider-risk-solution-overview.md)。 ソリューションが軽減に役立つリスク、ライセンス要件、展開シーケンス、アーキテクチャの図、トレーニング リソースなどについて詳細に説明します。
- 各インサイダー リスク ソリューションの新しい概要記事。 各ソリューションについて学び、計画し、展開し、管理するのに役立つ記事へのガイダンスとリンク。
  - [通信コンプライアンス](communication-compliance-solution-overview.md)
  - [インサイダー リスクの管理](insider-risk-management-solution-overview.md)
  - [情報障壁](information-barriers-solution-overview.md)
  - [特権アクセスの管理](privileged-access-management-solution-overview.md)
  
より多くのコンテンツ ソリューション ドキュメントが近日公開予定です。

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

カストディアンと非保管データ[](add-custodians-to-case.md)ソースをサポートケース[](non-custodial-data-sources.md)に追加するためのワークフローとAdvanced eDiscoveryしました。

### <a name="data-connectors"></a>データ コネクタ

[Redtail Speak、Salesforce](archiving-third-party-data.md#third-party-data-connectors)Chatter、ServiceNow、Yieldbroker の 4 つの新しい Veritas コネクタがリリースされました。

### <a name="encryption"></a>暗号化

テナント レベル[での顧客キーのMicrosoft 365を紹介します](customer-key-tenant-level.md)。 指定したキーを使用して、データ暗号化ポリシー (DEP) を作成し、テナントに割り当てできます。 DEP は、次のワークロードのテナント全体のデータを暗号化します。

- Teamsチャット メッセージ (1:1 チャット、グループ チャット、会議チャット、チャネル会話)
- Teamsメディア メッセージ (画像、コード スニペット、ビデオ、Wiki イメージ)
- Teamsストレージに保存されている通話と会議のTeams記録
- Teamsチャット通知
- Teams Cortana によるチャットの提案
- Teams状態メッセージ
- ユーザーとシグナルの情報をExchange Online

### <a name="records-management"></a>レコード管理

レコード [管理管理者役割グループは、](get-started-with-records-management.md#permissions-required-for-records-management) 廃棄レビューを含むすべてのレコード管理機能に対するアクセス許可を付与します。

### <a name="sensitivity-labels"></a>秘密度ラベル

- [Azure Purview のデータに自動的にラベルを付け (プレビュー) します](/azure/purview/create-sensitivity-label)。 これで、Azure Purview のアセット (Azure BLOB ストレージ内のファイルや、Azure の Blob ストレージ内のデータベース列など) に対して、感度ラベルを作成して自動的に適用SQL Server。
- [ユーザーがアイテムにラベルを適用する必要があります](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents)。 "必須ラベル付け" とも呼ばれるこの新しいオプションでは、ユーザーが特定のシナリオで感度ラベルを選択して適用する必要があります。
