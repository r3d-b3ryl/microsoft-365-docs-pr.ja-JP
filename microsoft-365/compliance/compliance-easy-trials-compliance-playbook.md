---
title: Microsoft Purview ソリューション試用版プレイブック
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: landing-page
ms.service: O365-seccomp
ms.collection: m365-security-compliance
ms.localizationpriority: high
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MOE150
- MET150
description: Microsoft Purview ソリューション試用版プレイブック。
ms.openlocfilehash: 4544e07baa5b8d2b89991d9a31c84a2d7cefb7f8
ms.sourcegitcommit: 45bc65972d4007b2aa7760d4457a0d2699f81926
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2022
ms.locfileid: "64973775"
---
# <a name="trial-playbook-microsoft-purview-solutions"></a>試用版プレイブック: Microsoft Purview ソリューション

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Microsoft Purview ソリューション試用版プレイブックへようこそ。このプレイブックは、Microsoft Purview およびセキュリティ製品の堅牢で包括的な機能を見つけ出すのに役立ち、90 日間の無料試用版を最大限に活用するのに役立ちます。

それぞれのソリューションを試すことで、組織のコンプライアンスのニーズを満たすための十分な情報に基づいた決断に役立ちます。

機能: 

- [監査 (プレミアム)](#audit-premium)
- [コミュニケーション コンプライアンス](#communication-compliance)
- [コンプライアンス マネージャー](#compliance-manager)
- [Microsoft Purview データ損失防止](#data-loss-prevention)
- [電子情報開示](#ediscovery)
- [情報保護](#information-protection)
- [インサイダー リスクの管理](#insider-risk-management)
- [レコード管理](#records-management)

省略可能なアドオン:

- [コンプライアンス マネージャー プレミアム評価](#compliance-manager-premium-assessments)
- [Microsoft Priva プライバシー リスク管理と Microsoft Priva 主体の権利要求](#microsoft-priva-privacy-risk-management-and-microsoft-priva-subject-rights-requests)

## <a name="compliance-actions-with-microsoft-purview"></a>Microsoft Purview を使用したコンプライアンス アクション

組織のメタデータを変更することなく、Microsoft のコンプライアンス ソリューションを簡単かつ迅速に試すことができます。 お客様の優先順位に応じて、これらのソリューション分野のいずれかを開始することで、すぐに価値を見出すことができます。 以下に、お客様から寄せられた 5 つの組織的な懸念事項と、それを解決するためのお勧めの方法をご紹介します。

:::image type="content" source="../media/compliance-trial/workflow.png" alt-text="コンプライアンス アクションと Microsoft 365":::

## <a name="audit-premium"></a>監査 (プレミアム)

**調査の実施**

Microsoft Purview の監査 (プレミアム) は、侵害の範囲の決定に役立つ重要なイベントへのアクセスを提供し、Office 365 管理アクティビティ API への迅速なアクセスを提供することで、調査の実施に必要な監査ログの保持を高め、組織によるフォレンジック調査やコンプライアンス調査の実施をサポートします。

### <a name="step-1-apply-the-e5-license-to-each-user-for-which-youd-like-to-generate-e5-events"></a>手順 1: [E5 イベントを生成する各ユーザーに E5 ライセンスを適用する](set-up-advanced-audit.md#step-1-set-up-audit-premium-for-users)

> [!TIP]
> 試用版のベスト プラクティス: 1 日目

MailItemsAccessed や Send などの重要なイベントをログに記録する機能などの監査 (プレミアム) 機能を使用するには、ユーザーに適切な E5 ライセンスが割り当てられている必要があります。 さらに、それらのユーザーに対して高度な監査アプリ/サービス プランを有効にする必要があります。

ユーザーの監査 (プレミアム) のセットアップを行う - 高度な監査アプリがユーザーに割り当てられていることを確認するには、[ユーザーごとに次の手順を実行します](set-up-advanced-audit.md#step-1-set-up-audit-premium-for-users)。

1. 監査 (プレミアム) イベントを有効にする - [SearchQueryInitiatedExchange および SearchQueryInitiatedSharePoint](set-up-advanced-audit.md#step-2-enable-audit-premium-events) を、[Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) でユーザーごとに監査できるようにします。
1. 監査保持ポリシーの設定 - 組織のセキュリティ運用、IT、コンプライアンス チームの要件に合わせて、[追加の監査ログ保持ポリシー](set-up-advanced-audit.md#step-3-set-up-audit-retention-policies)を作成します。
1. 監査 (プレミアム) イベントの検索 - フォレンジック調査を行う場合に[重要な監査 (プレミアム) イベントの検索](set-up-advanced-audit.md#step-4-search-for-audit-premium-events)やその他のアクィビティの検索を実行します。

### <a name="step-2-create-new-audit-log-policies-to-specify-how-long-to-retain-audit-logs-in-your-org-for-activities-performed-by-users-and-define-priority-levels-for-your-policies"></a>手順 2: [新しい監査ログ ポリシーを作成して、ユーザーが実行したアクティビティの監査ログを組織内で保持する期間を指定し、ポリシーの優先度を定義します](audit-log-retention-policies.md#before-you-create-an-audit-log-retention-policy)。

> [!TIP]
> 試用版のベスト プラクティス: 最初の 30 日以内に作成する

監査ログの保持ポリシーは、Microsoft 365 の新しい監査 (プレミアム) 機能の一部です。 監査ログの保持ポリシーでは、組織の監査ログを保持する期間を指定できます。

1. 監査ログ保持ポリシーの作成前 - ポリシーを作成する前に[知っておきたい主なポイント](audit-log-retention-policies.md#before-you-create-an-audit-log-retention-policy)。
1. [PowerShell で監査ログの保持ポリシーを作成する](audit-log-retention-policies.md#create-an-audit-log-retention-policy)
1. [Microsoft Purview コンプライアンス ポータルの監査ログ保持ポリシーの管理](audit-log-retention-policies.md#manage-audit-log-retention-policies-in-the-compliance-portal) - 監査ログの保持ポリシーは、[監査の保持ポリシー] タブ (ダッシュボードとも呼ばれます) に一覧表示されます。ダッシュボードを使用して、監査アイテム保持ポリシーを表示、編集、および削除できます。
1. PowerShell で監査ログ保持ポリシーを作成して管理する - セキュリティ/コンプライアンス センター PowerShellを使用して、[監査ログ保持ポリシーの作成および管理](audit-log-retention-policies.md#create-and-manage-audit-log-retention-policies-in-powershell)を行うこともできます。 PowerShell を使用する理由の 1 つは、UI で使用できないレコードの種類またはアクティビティのポリシーを作成することです。

## <a name="communication-compliance"></a>通信コンプライアンス

**行動規範ポリシー違反を特定し、対処する**

Microsoft Purview コミュニケーション コンプライアンスでは、不適切なメッセージの検出、ポリシー違反の可能性の調査、修正に向けた改善のための処置など、コンプライアンスと健全な職場環境をサポートするために、コミュニケーション違反をインテリジェントに特定するのに役立ちます。

### <a name="step-1-enable-permissions-for-communication-compliance"></a>手順 1: [通信コンプライアンスのためのアクセス許可を有効にする](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance)

> [!TIP]
> 試用版のベスト プラクティス: 1 日目

[すべてのコンプライアンス ユーザーをコミュニケーション コンプライアンス ロール グループに割り当てます](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance)。

### <a name="step-2-enable-the-audit-log"></a>手順 2: [監査ログを有効にする](communication-compliance-configure.md#step-2-required-enable-the-audit-log)

> [!TIP]
> 試用版のベスト プラクティス: 最初の 30 日以内に設定する

この機能を使用するには、監査を有効にして、組織内のユーザーと管理者のアクティビティを記録し始めることができるようにします。これを有効にすると、アクティビティが監査ログに記録されて、レポートに表示できるようになります。詳しくは、「[監査ログ検索のオン/オフを切り替える](turn-audit-log-search-on-or-off.md)」 を参照してください。

### <a name="step-3-create-a-communication-compliance-policy"></a>手順 3: [コミュニケーション コンプライアンス ポリシーを作成する](communication-compliance-policies.md)

[既存のテンプレートを使用して通信コンプライアンス ポリシーを作成する](communication-compliance-policies.md): 1 - 不適切なコンテンツ。2 - 機密情報。3 - 規制遵守。4 - 利益相反。

### <a name="step-4-investigate-and-remediate-alerts"></a>手順 4 : [警告の調査および修復](communication-compliance-investigate-remediate.md)

通信コンプライアンスのアラートを[調査して修復します](communication-compliance-investigate-remediate.md)。

## <a name="compliance-manager"></a>コンプライアンス マネージャー

**組織のコンプライアンスを簡単に管理する**

Microsoft Purview コンプライアンス マネージャーは、データ保護リスクのインベントリの作成から、複雑な制御の実装の管理、規制や認証の最新情報の入手、監査人への報告まで、コンプライアンスの過程全体を支援します。

### <a name="step-1-get-to-know-compliance-manager"></a>手順 1: [コンプライアンス マネージャーについて理解する](compliance-manager-quickstart.md#first-visit-get-to-know-compliance-manager)

> [!TIP]
> 試用版のベスト プラクティス: 1 日目

コンプライアンス マネージャーの概要ページは、コンプライアンス マネージャーとは何か、どのように機能するのかを包括的に確認するための最初の手段に最適です。 また、以下のリンクを使用して、ドキュメントの主要なセクションに移動することもできます。

- [コンプライアンス スコアについて理解する](compliance-manager.md#understanding-your-compliance-score)
- [主要な要素の概要: コントロール、評価、テンプレート、改善のための処置](compliance-manager.md#key-elements-controls-assessments-templates-improvement-actions)
- [コンプライアンス マネージャー ダッシュ ボードを理解する](compliance-manager-setup.md#understand-the-compliance-manager-dashboard)
- [ダッシュボード ビューをフィルター処理します](compliance-manager-setup.md#filtering-your-dashboard-view)
- [改善のための処置に関する詳細情報](compliance-manager-setup.md#improvement-actions-page)
- [評価を理解する](compliance-manager.md#assessments)
- [Microsoft コンプライアンス構成マネージャーを使用して環境のクイック スキャンを実行する](compliance-manager-mcca.md)

![コンプライアンス マネージャーのダッシュ ボード。](../media/compliance-manager-dashboard.png "コンプライアンス マネージャーのダッシュ ボード")

### <a name="step-2-configure-compliance-manager-to-manage-your-compliance-activities"></a>手順 2: [コンプライアンス マネージャーを構成してコンプライアンス アクティビティを管理する](compliance-manager-assessments.md)

> [!TIP]
> 試用版のベスト プラクティス: 最初の 30 日以内に検査を行う

評価を開始し、改善のための処置を実行してコントロールを実装し、コンプライアンス スコアを向上させます。

1. [事前に作成されたテンプレートを選択し、最初の評価を作成して管理します](compliance-manager-assessments.md)。
1. [評価を構築するためにテンプレートを使用する方法を理解します](compliance-manager-templates.md)。
1. [改善のための処置の実装とテスト作業を実行して、評価のコントロールを完了させます](compliance-manager-improvement-actions.md)。
1. [さまざまなアクションがコンプライアンス スコアに与える影響への理解を深めます](compliance-score-calculation.md)。

> [!NOTE]
> Microsoft 365 または Office 365 E1/E3 サブスクリプションには、Microsoft データ保護基準テンプレートが含まれます。 Microsoft 365 または Office 365 E5、E5 コンプライアンスには、次のテンプレートが含まれています。
>
> - Microsoft データ保護のベースライン
> - 欧州連合 の GDPR  
> - ISO/IEC 27001、
> - NIST 800-53
>
> コンプライアンス マネージャーには、アドオンとして購入できる 300 以上の規制またはプレミアム テンプレートがあります。 その一覧については、こちらを参照してください。 プレミアム テンプレート (サブスクリプションに含まれるか、アドオンとして購入) を使用すると、それらのテンプレートのユニバーサル バージョンを受け取り、あらゆる製品やサービスのコンプライアンスを管理できます

### <a name="step-3-scaling-up-use-advanced-functionality-to-meet-your-custom-needs"></a>手順 3: [スケール アップ: 高度な機能を使用してカスタムのニーズを満たす](compliance-manager-templates-create.md)

カスタム評価は、次の場合に役立ちます。

- サードパーティのアプリやサービス、オンプレミスのアプリケーション、その他の資産など、Microsoft 365 以外の製品向けコンプライアンスの管理
- 独自のカスタムまたはビジネスに特化したコンプライアンス コントロールの管理

1. [独自のコントロールと改善のための処置を追加してコンプライアンス マネージャー テンプレートを拡張する](compliance-manager-templates-extend.md)
1. [独自のカスタム テンプレートを作成する](compliance-manager-templates-create.md)
1. [既存のテンプレートを変更してコントロールとアクションを追加または削除する](compliance-manager-templates-modify.md)
1. [改善のための処置の自動テストを設定する](compliance-manager-setup.md#set-up-automated-testing)
1. [改善のための処置を別のユーザーに再び割り当てる](compliance-manager-setup.md#reassign-improvement-actions-to-another-user)

## <a name="data-loss-prevention"></a>データ損失防止

**機密データの保護**

ビジネスの標準や業界の規制に準拠するために、組織は機密情報を保護し、不注意による情報漏えいを防ぐ必要があります。 Microsoft Purview データ損失防止ポリシーを設定して、Microsoft 365 全体で機密情報を特定、監視、および自動的に保護します。

### <a name="step-1-protect-data-loss-on-teams-locations"></a>手順 1:[Teams の場所でのデータ損失を保護する](dlp-microsoft-teams.md#dlp-licensing-for-microsoft-teams)

> [!TIP]
> 試用版のベスト プラクティス: 1 日目

組織にデータ損失防止 (DLP) がある場合は、Microsoft Teams チャネルまたはチャット セッションで機密情報を共有できないようにするポリシーを定義できます。

1. [Microsoft Teams の DLP ライセンスと DLP 保護の範囲](dlp-microsoft-teams.md#dlp-licensing-for-microsoft-teams)に関する詳細情報
1. [Microsoft Teams を場所として既存の DLP ポリシーに追加する](dlp-microsoft-teams.md#add-microsoft-teams-as-a-location-to-existing-dlp-policies)
1. [Teams 用の既定の DLP ポリシーの構成](mip-easy-trials.md)または [Microsoft Teams 用の新しい DLP ポリシーの定義](dlp-microsoft-teams.md#define-a-new-dlp-policy-for-microsoft-teams)

### <a name="step-2-protect-data-loss-on-device-locations"></a>手順 2: [デバイスの場所でのデータ損失を保護する](endpoint-dlp-getting-started.md)

> [!TIP]
> 試用版のベスト プラクティス: 最初の 30 日以内に設定する

Microsoft Endpoint DLP は、Windows 10 デバイスを監視し、機密性の高いアイテムが使用および共有されていることを検出します。

1. エンドポイントの準備 - [これらの要件を満たす](endpoint-dlp-getting-started.md)ために、エンドポイント DLP の導入を計画している Windows 10 デバイスを確認してください
1. [デバイス管理にデバイスをオンボードする](endpoint-dlp-getting-started.md) - デバイス上の機密アイテムを監視および保護する前に、デバイスの監視を有効にし、エンドポイントをオンボードしなければなりません。 これらのアクションはどちらも Microsoft Purview コンプライアンスポータルで行われます。
   - シナリオ 1 – まだオンボードされていない[オンボーディング デバイス](endpoint-dlp-getting-started.md)。
   - シナリオ 2 - [Microsoft Defender for Endpoint は既に導入されており、レポートするエンドポイントがあります](endpoint-dlp-getting-started.md)。 これらすべてのエンドポイントが管理対象デバイスのリストに表示されます。
1. [デバイス用の既定の DLP ポリシーの構成](mip-easy-trials.md#dlp-for-devices)または[デバイス用の新しい DLP ポリシーの定義](endpoint-dlp-learn-about.md)。
1. DLP 警告管理ダッシュボードでの[エンドポイント DLP 警告の表示](dlp-configure-view-alerts-policies.md)。
1. Activity エクスプローラーでの [Endpoint DLP データの表示](data-classification-activity-explorer.md)。

### <a name="step-3-expand-policies-in-scope-or-protection"></a>手順 3: [範囲または保護でポリシーを展開する](dlp-learn-about-dlp.md#dlp-policy-configuration-overview)

DLP ポリシーの構成は柔軟に行うことができます。 Teams やデバイス用の既定の DLP ポリシーの使用を開始し、それらのポリシーを拡張して、追加の場所、機密情報の種類、またはラベルを保護することができます。 さらに、ポリシー アクションの拡張やアラートのカスタマイズもできます。

1. 場所の追加
1. 機密情報の種類またはラベルを追加して保護する
1. アクションの追加
   - Teams:
      - [機密文書への外部アクセスを防止する](dlp-microsoft-teams.md#prevent-external-access-to-sensitive-documents)
      - [ユーザーの教育に役立つポリシー ヒントと、ポリシー ヒントをカスタマイズする手順を入手する](dlp-microsoft-teams.md#policy-tips-help-educate-users)
   - デバイス: 監査のみからブロックに切り替える
1. [データ損失防止ポリシーのアラートを構成および表示する - Microsoft Purview | Microsoft Docs](dlp-configure-view-alerts-policies.md)

## <a name="ediscovery"></a>電子情報開示

**エンドツーエンドのワークフローを使用して詳細を検索する**

組織の内部および外部の調査に対応するコンテンツを保持、収集、分析、エクスポートするためのエンド ツー エンドのワークフローを活用します。 訴訟チームは、ケースに関係するカストディアンとコミュニケーションを取ることで、法的情報保留通知プロセス全体を管理することもできます。

### <a name="step-1-required-permissions"></a>手順 1 (必須): [アクセス許可](https://aka.ms/ediscoveryninja)

> [!TIP]
> 試用版のベスト プラクティス: 1 日目

電子情報開示 (プレミアム) にアクセスしたり、電子情報開示 (プレミアム) のケースのメンバーとして追加するには、ユーザーに適切なアクセス許可を割り当てる必要があります。

1. [電子情報開示 (プレミアム) の設定 – 電子情報開示のアクセス許可を割り当てる](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions)
1. [ケースでメンバーを追加または削除する](add-or-remove-members-from-a-case-in-advanced-ediscovery.md)

### <a name="step-2-required-create-a-case"></a>手順 2 (必須): ケースの作成

> [!TIP]
> 試用版のベスト プラクティス: 最初の 30 日以内に作成する

より多くの企業が、重要な電子情報開示プロセスに Microsoft 365 の電子情報開示 (プレミアム) ソリューションを使用しています。 これには、規制の要求、調査、訴訟への対応などがあります。

1. 電子情報開示 (プレミアム) を管理する - [電子情報開示 (プレミアム) の構成、セキュリティ/コンプライアンス センターを使用したケースの管理、電子情報開示 (プレミアム) でのワークフローの管理、電子情報開示 (プレミアム) の検索結果の分析などの方法を説明します](/learn/modules/manage-advanced-ediscovery)。
1. [Advanced eDiscovery の新しいケース形式を使用して電子情報開示ケースを作成する](advanced-ediscovery-new-case-format.md)
1. [ケースを閉じるまたは削除します](close-or-delete-case.md) - 訴訟ケースまたは調査が完了したら、終了または削除できます。また、閉じたケースを再度開くこともできます。

### <a name="step-3-optional-settings"></a>手順 3 (省略可能): 設定

組織内のユーザーがケースの作成と使用を開始するには、組織内のすべてのケースに適用されるグローバル設定を構成する必要があります。 現時点では、唯一のグローバル設定は、**弁護士/依頼人特権の検出** です (今後、より多くのグローバル設定が利用可能になります)。

1. [電子情報開示 (プレミアム) を設定する – グローバル設定](get-started-with-advanced-ediscovery.md#step-3-configure-global-settings-for-ediscovery-premium)
1. [検索と分析の設定を構成する](configure-search-and-analytics-settings-in-advanced-ediscovery.md)
1. [電子情報開示 (プレミアム) でジョブを管理する](managing-jobs-ediscovery20.md)

### <a name="step-4-optional-compliance-boundaries"></a>手順 4 (省略可能): [コンプライアンスの境界](set-up-compliance-boundaries.md)

コンプライアンスの境界では、電子情報開示マネージャーが検索できるユーザー コンテンツの場所 (メールボックス、OneDrive アカウント、SharePoint サイトなど) を制御する組織内に論理的な境界を作成します。 また、組織内の法務、人事、またはその他の調査を管理するために使用する電子情報開示ケースにアクセスできるユーザーを制御します。

![コンプライアンスの境界は、機関へのアクセスを制御する検索アクセス許可フィルターと、電子情報開示ケースへのアクセスを制御する管理者の役割グループで構成されています。](../media/M365_ComplianceBoundary_OrgChart_v2.png)

電子情報開示調査のためにコンプライアンスの境界を設定する

1. [ユーザー属性を特定して機関を定義する](set-up-compliance-boundaries.md#step-1-identify-a-user-attribute-to-define-your-agencies)
1. [各機関の役割グループを作成する](set-up-compliance-boundaries.md#step-2-create-a-role-group-for-each-agency)
1. [検索アクセス許可のフィルターを作成して、コンプライアンスの境界を適用する](set-up-compliance-boundaries.md#step-3-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)
1. [機関内調査の電子情報開示ケースを作成する](set-up-compliance-boundaries.md#step-4-create-an-ediscovery-case-for-intra-agency-investigations)

### <a name="step-5-optional-learn-about-content-search-tool"></a>手順 5 (省略可能): [コンテンツ検索ツールに関する詳細情報](search-for-content.md)

Microsoft Purview コンプライアンス ポータルのコンテンツ検索ツールを使用して、Exchange メールボックスのメール、SharePoint サイトおよび OneDrive ロケーションのドキュメント、Skype for Business のインスタント メッセージングの会話をすばやく検索できます。 コンテンツ検索ツールは、Microsoft Teams や Microsoft 365 グループなどのコラボレーション ツール内のメール、ドキュメント、インスタント メッセージングの会話を検索するために使用できます。

- [電子情報開示 (プレミアム) の検索に関する詳細情報](search-for-content.md#search-for-content)

## <a name="information-protection"></a>情報保護

**機密情報を検出し、分類して保護する**

Microsoft Purview の情報保護ラベルと機密ラベルを実装して、ユーザーがどこに住んでいても、どこを移動中でも、機密コンテンツを発見、分類、保護できるようにします。

### <a name="step-1-start-your-information-protection-trial"></a>手順 1: [情報保護の試用版の使用を開始する](mip-easy-trials.md)

> [!TIP]
> 試用版のベスト プラクティス: 1 日目

対象となるお客様は、Microsoft Purview の情報保護の既定のラベルとポリシーをアクティブ化できます。試用版で既定の構成を有効にすると、テナントのすべてのポリシーを構成するのに約 2 分かかります。これらの既定のポリシーの結果を表示するには、最大 24 時間かかります。

既定の構成を選択すると、1 クリックで次の設定が自動的に構成されます。

- 秘密度ラベルと秘密度ラベル ポリシー
- クライアント側の自動ラベル付け
- サービス側の自動ラベル付け
- Teams とデバイスのデータ損失防止 (DLP) ポリシー

[既定のラベルとポリシーをアクティブ化します](mip-easy-trials.md#activate-the-default-labels-and-policies)。 必要に応じて、構成の完了後に手動で編集できます。

### <a name="step-2-automatically-apply-sensitivity-labels-to-documents"></a>手順 2: [秘密度ラベルをドキュメントとメールに自動的に適用する](apply-sensitivity-label-automatically.md)

> [!TIP]
> 試用版のベスト プラクティス: 最初の 30 日以内に設定する

秘密度ラベルを作成する場合、指定した条件に一致したときに、そのラベルをファイルやメールに自動的に割り当てることができます。

1. [秘密度ラベルを作成して構成する](create-sensitivity-labels.md#create-and-configure-sensitivity-labels)
1. [すべてのユーザーに対して秘密度ラベル ポリシーを発行する](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)
1. [新しい自動ラベル付けポリシーを作成する](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)
   - ラベルを適用する情報を選択する
   - ラベルを適用する場所を定義する
   - 適用するラベルを選択する
   - [シミュレーション モードでポリシーを実行する](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)

![自動ラベル付けの新しいポリシー構成。](../media/auto-labeling-wizard.png)

### <a name="step-3-review-and-turn-on-auto-labeling-policy"></a>手順 3: [自動ラベル付けポリシーを確認して有効にする](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)

これで、[**情報保護**]、 > [**自動ラベル付け (プレビュー)**] ページの [**シミュレーション**] セクションに、自動ラベル付けポリシーが表示されます。

ポリシーを選択して、構成と状態の詳細を確認します。 シミュレーションが完了したら、[確認するアイテム] タブを選択して、指定したルールと一致するメールまたはドキュメントを確認します。

シミュレーションなしでポリシーを実行する準備が整っているときには、**[ポリシーを有効にする]** オプションを選択します。

## <a name="insider-risk-management"></a>インサイダー リスクの管理

**インサイダー リスクの検出および修復**

人工知能を活用して、内部リスクをすばやく特定、トリアージ、修復するのに役立ちます。Microsoft 365 および Azure サービスからのログを使用すると、インサイダー リスクシグナルを監視するポリシーを定義し、ユーザー教育の促進や調査の開始などの修復アクションを実行できます。

### <a name="step-1-required-enable-permissions-for-insider-risk-management"></a>手順 1 (必須): [インサイダー リスク管理のアクセス許可を有効にする](insider-risk-management-configure.md#step-1-required-enable-permissions-for-insider-risk-management)

> [!TIP]
> 試用版のベスト プラクティス: 1 日目

インサイダー リスク管理機能を管理するためのアクセス許可を構成するために使用される役割グループは 4 種類あります。

[インサイダー リスク管理の役割グループにユーザーを追加します。](insider-risk-management-configure.md#add-users-to-an-insider-risk-management-role-group)

アクセス許可が表示されない場合は、テナント管理者に問い合わせ、正しい役割を割り当ててください。

### <a name="step-2-start-with-user-quick-start-guide"></a>手順 2: [ユーザー クイック スタート ガイドを開始する](insider-risk-management-configure.md#recommended-actions-preview)

推奨されるアクションを使用して、インサイダー リスク管理機能をすばやく開始し、最大限に活用します。 [概要] ページにある推奨アクションは、ポリシーを構成して展開する手順や、ポリシーの一致からアラートを生成するユーザー アクション用の調査アクションを実行する手順を示します。

[一覧から推奨事項を選択](insider-risk-management-configure.md#recommended-actions-preview)して、インサイダー リスク管理の構成を開始します。

![インサイダー リスクの管理に推奨されるアクション。](../media/insider-risk-recommended-actions.png)

推奨されるそれぞれのアクションでは、要件、予想される内容、組織で機能を構成した場合の影響など、推奨事項に必要なアクティビティに関する説明が行われます。

### <a name="step-3-required-enable-the-microsoft-365-audit-log"></a>手順 3 (必須):[Microsoft 365 監査ログを有効にする](insider-risk-management-configure.md#step-2-required-enable-the-microsoft-365-audit-log)

Microsoft 365 の組織では、監査が既定で有効になっています。 組織によっては、特定の理由で監査を無効にしている場合があります。 組織の監査が無効になっている場合は、別の管理者が無効にしている可能性があります。 この手順を完了する場合は、監査を再びオンにしても問題ないか確認することをお勧めします。

監査を有効にする詳しい手順については、「[監査ログ検索を有効または無効する](turn-audit-log-search-on-or-off.md)」を参照してください。 監査を有効にすると、監査ログの準備中で、準備が完了してから数時間で検索を実行できるというメッセージが表示されます。 このアクションを行う必要があるのは 1 回だけです。 Microsoft 365 監査ログの使用に関する詳細については、「[監査ログを検索する](search-the-audit-log-in-security-and-compliance.md)」を参照してください。

### <a name="step-4-required-enable-and-view-insider-risk-analytics-insights"></a>手順 4 (必須): [インサイダー リスク分析の分析情報を有効にして表示する](insider-risk-management-configure.md#step-3-optional-enable-and-view-insider-risk-analytics-insights)

Insider リスク管理分析では、インサイダー リスク ポリシーを構成することなく、組織内の潜在的なインサイダー リスクの評価を行うことができます。 分析スキャン結果は、分析情報がレポートとして確認できるようになるまで最大 48 時間かかる場合があります。 分析情報に関する詳細については、「[インサイダー リスク管理の設定: 分析 (プレビュー)](insider-risk-management-settings.md)」を参照し、[インサイダー リスク管理分析のビデオ](https://www.youtube.com/watch?v=5c0P5MCXNXk)をチェックすることで、インサイダー リスクの姿勢を理解し、リスクの高いユーザーを特定するために適切なポリシーを設定することで処置を講じるのに役立ちます。

インサイダー リスク分析を有効にするには、インサイダー リスク管理またはインサイダー リスク管理者のメンバーである必要があります。[これらの手順を実行して、インサイダー リスク分析を有効にします](insider-risk-management-configure.md)。

## <a name="records-management"></a>レコード管理

**ビジネス クリティカルな記録の保持スケジュールを自動化する**

統合された Microsoft Purview のレコード管理機能を使用して、組織の規制、法律、およびビジネスに不可欠なレコードの保持スケジュールを自動化します。 作成から共同作業、レコード宣言、保持、廃棄に至るまで、コンテンツのライフサイクル全体のサポートを取得します。

### <a name="step-1-dynamically-target-retention-policies-with-adaptive-policy-scopes"></a>手順 1: アダプティブ ポリシー スコープを使用してアイテム保持ポリシーを動的に対象化する

> [!TIP]
> 試用版のベスト プラクティス: 1 日目

アダプティブ ポリシー スコープを使用すると、AD の属性に基づいて、特定のユーザー、グループ、またはサイトにポリシーを動的に適用することができます。

スコープの属性は、一覧から選択するか、詳細なクエリ ビルダーを使用してカスタマイズすることができます。

アダプティブ ポリシー スコープを使用するポリシーは、新しい従業員の入社や退職など、組織の変化に合わせて常に最新の状態に維持されます。 また、ポリシーに含まれていた 100/1,000 の場所の従来の制限の対象にもなりません。

- [アダプティブ ポリシー スコープ](retention.md#adaptive-or-static-policy-scopes-for-retention)を作成し、アイテム保持ポリシーと併用する

### <a name="step-2-automate-labeling-of-sensitive-information-with-the-ability-to-review-before-disposal"></a>手順 2: 廃棄前に確認する機能を備えた機密情報のラベル付けを自動化する

> [!TIP]
> 試用版のベスト プラクティス: 最初の 30 日以内に設定する

保持ラベルは、クレジット カード番号などの機密情報を検出した場合にコンテンツに自動的に適用されるように設定できます。 これにより、ユーザーがラベル付けアクティビティを手動で実行する必要がなくなります。

保持期間の終了時には、指定したユーザー ("レビュー担当者") に通知して、コンテンツを確認し、完全に廃棄する処置の承認を得ます。 そうすることにより、長期間保存する必要がある場合にそれが可能になります。

ラベル申請アクティビティと廃棄レビュー アクティビティのいずれも、[レコード管理の概要] 画面で表示できます。

1. [保持ラベルを機密情報を含むコンテンツに自動的に適用する](retention.md#retention-labels)
1. 保持期間の終了時に[廃棄レビュー](disposition.md#disposition-reviews)を含む保持ラベルを作成して適用する

### <a name="step-3-label-content-as-records-automatically-using-trainable-classifiers"></a>手順 3: トレーニング可能な分類子を使用してコンテンツを記録として自動的にラベル付けする

コンテンツがレコードとして宣言されると、どのようなアクションが許可されるか、またはブロックされるかという点でアイテムに制限が加えられ、アイテムに関する追加のアクティビティが記録され、保持期間の終わりにアイテムが削除された場合には、廃棄の証明が得られます。

トレーニング可能な分類子は、与えられたサンプルに基づいて、さまざまな種類のコンテンツを認識するツールです。 さまざまな組み込みオプションから選択するか、特定のニーズに合わせてカスタム分類子を設定します。

1. [コンテンツをレコードまたは規制レコードとして宣言する](records-management.md#records)保持ラベルを作成する
1. [トレーニング可能な分類子を使用して、保持ラベルをコンテンツに自動的に適用する](apply-retention-labels-automatically.md#auto-apply-labels-to-content-by-using-trainable-classifiers)

### <a name="more-information-auto-apply-retention-labels--disposition-review"></a>詳細情報: 保持ラベルの自動適用および処理確認

**必要なものを保持するためにラベルを自動的に適用します。** アイテム保持ラベルは、次のものが含まれている場合に、コンテンツに自動的に適用できます。

- [特定の種類の機密情報](apply-retention-labels-automatically.md#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)
- [作成したクエリに一致する特定のキーワードまたは検索可能なプロパティ](apply-retention-labels-automatically.md#auto-apply-labels-to-content-with-keywords-or-searchable-properties)
- [トレーニング可能な分類子の一致](apply-retention-labels-automatically.md#auto-apply-labels-to-content-by-using-trainable-classifiers)

**...最後に、安全に処理します。**

保持期間の終わりに処理確認がトリガーされると、選択したレビュー担当者は、レビューするコンテンツがあるというメール通知を受け取ります。

処理確認を待っているコンテンツは、処理確認の最終ステージで確認担当者がコンテンツの恒久的な削除を選択しない限り削除されません。

## <a name="additional-trials-and-add-ons"></a>追加の試用版とアドオン

### <a name="compliance-manager-premium-assessments"></a>コンプライアンス マネージャー プレミアム評価

**リスクを評価し、効率的に対応する**

データの収集と使用を規定する国、地域、業界の要求に対して、組織がリスクを評価し、効率的に対応するのに役立ちます。

[コンプライアンス マネージャー プレミアム評価の試用版に関する詳細情報](compliance-easy-trials-compliance-manager-assessments.md)。

[試用版プレイブック: Microsoft Purview コンプライアンス マネージャー プレミアム アセスメント](compliance-easy-trials-compliance-manager-assessment-playbook.md)

### <a name="microsoft-priva-privacy-risk-management-and-microsoft-priva-subject-rights-requests"></a>Microsoft Priva プライバシー リスク管理と Microsoft Priva 主体の権利要求

**プライバシー リスクの特定と防止**

データの囲い込み、データ転送、データの過剰共有などのプライバシー リスクに対してプロアクティブに特定して保護し、組織が大規模な件名要求を自動化し管理するサポートを行います。

[Microsoft Priva の詳細についてはこちらをご覧ください](/privacy/solutions/privacymanagement/privacy-management)。

[試用版プレイブック: Microsoft Priva](/privacy/solutions/privacymanagement/privacy-management-trial-playbook)

## <a name="additional-resources"></a>その他のリソース

**含まれるもの**: Microsoft Purview ソリューションの完全な一覧と製品レベル別の機能については、「[機能一覧](https://go.microsoft.com/fwlink/?linkid=2139145)」をご覧ください。

**Microsoft Security Technical Content ライブラリ**: このライブラリを探索して、ユーザーのニーズに関連する対話型ガイドやその他の学習コンテンツを見つけます。[ライブラリに行く](/security)。

**Microsoft Security リソース**: マルウェア対策からゼロ トラストまで、組織のセキュリティ ニーズに関連するすべてのリソースを入手します。[リソースに行く](/security/business/resources)。
