---
title: Microsoft Purview のリスクおよびコンプライアンス ソリューションの新機能
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: コンプライアンス センターへの新しいソリューションの追加、お客様からのフィードバックに基づく既存の機能の更新、新しく更新されたドキュメントの展開など、Microsoft 365 は刻々と変化するコンプライアンスの状況を常に把握できるようサポートします。 今月起こったことついてご覧ください。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7a44fe74c3d0262737d5af52e226a3aa942a412f
ms.sourcegitcommit: e6595be36bbaba244439bd59dbae935e2b258ded
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2022
ms.locfileid: "67450171"
---
# <a name="whats-new-in-microsoft-purview-risk-and-compliance-solutions"></a>Microsoft Purview のリスクおよびコンプライアンス ソリューションの新機能

[Microsoft Purview コンプライアンス ポータル](microsoft-365-compliance-center.md)への新しいソリューションの追加、お客様からのフィードバックに基づく既存の機能の更新、新しく更新されたドキュメントの展開など、Microsoft 365 は刻々と変化するコンプライアンスの状況を常に把握できるようサポートします。 Microsoft Purview の新機能は以下のとおりです。

> [!NOTE]
> コンプライアンス機能の中には、顧客に提供するスピードが異なるものがあります。 まだ機能が表示されていない場合は、[対象リリース](/office365/admin/manage/release-options-in-office-365)に自分自身を追加してみてください。

> [!TIP]
> 他の管理センターで起こっていることに興味がありますか? 以下の記事をご覧ください。
>
> - [Microsoft 365 管理センターの新機能](/office365/admin/whats-new-in-preview)
> - [SharePoint 管理センターの新機能](/sharepoint/what-s-new-in-admin-center)
> - [Microsoft 365 Defender の新機能](../security/defender/whats-new.md)
>
> [Microsoft 365 のロードマップ](https://www.microsoft.com/microsoft-365/roadmap)では、提供済み、ロールアウト中、開発中、キャンセル済み、以前にリリース済みの Microsoft 365 機能がわかります。

## <a name="july-2022"></a>2022 年 7 月

### <a name="compliance-manager"></a>コンプライアンス マネージャー

- [コンプライアンス マネージャー テンプレートの一覧](compliance-manager-templates-list.md) - "香港 - 銀行業務と支払いカードのコード" のAsia-Pacific国カテゴリに新しいプレミアム テンプレートを追加しました。

### <a name="compliance-offerings--service-assurance"></a>コンプライアンス オファリングとサービス アシュアランス

- [Microsoft 365 の SharePoint と OneDrive のデータ回復性](/compliance/assurance/assurance-sharepoint-onedrive-data-resiliency) - BLOB ストレージの回復性に関するセクションの変更。

### <a name="data-lifecycle-management-and-records-management"></a>データ ライフサイクル管理とレコード管理

- [シナリオの詳細を追加したライセンス セクションを結合](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#microsoft-purview-data-lifecycle-management--microsoft-purview-records-management) しました。
- SharePoint ドキュメント バージョンの保持では、保持保持ライブラリ内の個別のファイルは使用されなくなりました。 詳細については、更新されたドキュメント「 [ドキュメント バージョンでの保持のしくみ](retention-policies-sharepoint.md#how-retention-works-with-document-versions)」を参照してください。
- [SharePoint または OneDrive に移行したレコードを検証する](records-management.md#validating-migrated-records)方法について説明します。
- [SEC 17a-4(f)、FINRA 4511(c)、CFTC 1.31(c)-(d)](retention-regulatory-requirements.md#sec-17a-4f-finra-4511c-and-cftc-131c-d)の Cohasset 評価レポートを更新しました。
- この機能が GA で展開されるようになった Teams 共有チャネルのアイテム保持ポリシーのプレビュー免責事項を削除しました。

### <a name="data-loss-prevention"></a>データ損失防止

- [DLP ポリシー リファレンス](dlp-policy-reference.md#blocking-and-notifications-in-sharepoint-online-and-onedrive-for-business) - SharePoint Online でのブロックと通知に関する新しいセクションが追加され、顧客のエスカレーションに対応してOneDrive for Businessされました。 機密サービス ドメインのパブリック プレビューをサポートするように更新されました。 Power BI のサポートを更新しました。 トレーニング可能な分類子のサポートを更新しました。
- [エンドポイント DLP 設定を構成する](dlp-configure-endpoint-settings.md#sensitive-service-domains) - 機密性の高いサービス ドメインパブリック プレビューのパブリック プレビュー リリースをサポートする新しいコンテンツを追加しました。 URL 照合動作を更新しました。
- [エンドポイント DLP の使用](endpoint-dlp-using.md#scenario-6-monitor-or-restrict-user-activities-on-sensitive-service-domains) - 機密サービス ドメインのパブリック プレビュー リリースをサポートする新しいシナリオ コンテンツ。 サブスクリプション情報を更新しました。

### <a name="ediscovery"></a>電子情報開示

- [電子情報開示のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md) - 置き換えられた情報が削除されました。

### <a name="sensitive-information-types"></a>機密情報の種類

- [機密情報の種類エンティティ定義](sensitive-information-type-entity-definitions.md) - 41 個の新しい資格情報スキャン SIT をサポートするために、41 個の新しい SIT エンティティ定義が追加されました。 SIT エンティティ定義のコンテンツは、単一のモノリシックアーティクルから、より簡単に参照可能でサポート可能な個々の記事に完全にリワークされました。 これで、42 個の新しい資格情報スキャン SIT を含む合計で 303 件の記事が作成されています。

### <a name="sensitivity-labels"></a>秘密度ラベル

- プレビュー段階: [SharePoint ドキュメント ライブラリの既定の秘密度ラベル](sensitivity-labels-sharepoint-default-label.md)。
- プレビューでは、ユーザーがアクセス許可を割り当てるように秘密度ラベルが構成されている場合の Windows の [組織全体のカスタム](encryption-sensitivity-labels.md#support-for-organization-wide-custom-permissions) アクセス許可。 詳細については、「  [組織全体のカスタムアクセス許可のサポート](encryption-sensitivity-labels.md#support-for-organization-wide-custom-permissions)」を参照してください。
- 次に、Windows の現在のチャネル (プレビュー) にロールアウトします。既存のドキュメントの既定のラベル。
- Semi-Annual エンタープライズ チャネル: [秘密度ラベルで暗号化されたファイルの共同編集で](sensitivity-labels-coauthoring.md)使用できるようになりました。
- 秘密 [度ラベル](sensitivity-labels.md#label-scopes) を構成するときに表示される "ファイル & 電子メール" のラベル スコープ名が "アイテム" になりました。

## <a name="june-2022"></a>2022 年 6 月

### <a name="compliance-manager"></a>コンプライアンス マネージャー

- [Microsoft Purview Compliance Manager のアラートとアラート ポリシー - アラート ポリシー](compliance-manager-alert-policies.md) を作成または編集するアクセス許可を持つ 3 つの AAD ロールが追加されました。
- [Configuration Analyzer for Microsoft Purview](compliance-manager-mcca.md) - 以前は "Microsoft Compliance Configuration Analyzer" という名前の Compliance Manager のこの入門ツールの新しい名前と更新された参照リンク。

### <a name="data-loss-prevention"></a>データ損失防止

- Microsoft Purview ブランドのスクリーンショットに関する多数のページ更新プログラム。

### <a name="data-lifecycle-management-and-records-management"></a>データ ライフサイクル管理とレコード管理

- プレビュー段階: [Microsoft Graph API for records management](compliance-extensibility.md#microsoft-graph-api-for-records-management-preview)

### <a name="microsoft-priva"></a>Microsoft Priva

- [Subject Rights Requests](/privacy/priva/subject-rights-requests) - 各進行状況ステップを通じてユーザーを支援するために、SRR コンテンツの大幅な更新と再構築。以下の詳細を参照してください。
  - Priva 主体の権利要求 - 顧客価値の小道具の明確なアーティキュレーションと、SRR プロセスの一般的な概要[について説明](/privacy/priva/subject-rights-requests)します。
  - [ワークフローと詳細ページを理解](/privacy/priva/subject-rights-requests-workflow) する - 要求を完了し、手動と自動進行を示し、詳細なコンテンツにリンクする手順を明確にします。セクションでは、新しい [履歴] タブなど、要求の詳細ページを解釈して操作する方法について説明します。
  - [要求を作成して検索設定を定義](/privacy/priva/subject-rights-requests-create) する - サブヘッドを使用して新しいフレームを作成する方法は、ガイド付きプロセスを使用したカスタム メソッドと、状況に最も関連するコンテンツの取得を目的としたテンプレートを使用する新機能の 2 つの方法です。
  - [データの見積もりと取得](/privacy/priva/subject-rights-requests-data-retrieval) - 一部の要求がデータ見積もり段階で一時停止する理由と、結果として検索を調整する方法について説明します。また、データの取得を自動的に進める前に、最初に一時停止するように要求を設定する方法についても説明します。
  - [サブジェクト権限要求のデータを確認](/privacy/priva/subject-rights-requests-data-review) する - 新しいインポート ファイル機能を使用すると、ユーザーは Microsoft 以外の 365 の場所からファイルを取得できます。それ以外の場合は、検索で取得されていないファイルを [データ収集] タブに移動できます。
  - [レポートを生成し、要求を閉じる](/privacy/priva/subject-rights-requests-reports) - 最終的なデータ パッケージがいつ生成され、どのような種類のファイルが含まれているかを明確にします。
  - [Microsoft Graph APIと Power Automate を統合して拡張](/privacy/priva/subject-rights-requests-automate)する - この以前の Power Automate ページのタイトルと拡張されたページ コンテンツのタイトルを変更し、以前に別のページに存在していたGraph APIコンテンツと参照リンクを含めます。

### <a name="sensitive-information-types"></a>機密情報の種類

- [正確なデータ一致ベースの機密情報の種類について説明](sit-learn-about-exact-data-match-based-sits.md) します。EDM がサポートするサービスに関するセクションが追加されました。

### <a name="sensitivity-labels"></a>秘密度ラベル

- プレビューでは、 [ドキュメントを PDF](sensitivity-labels-office-apps.md#pdf-support) 形式に変換し、視覚的なマーキングと暗号化でラベルを継承する Office アプリの PDF サポート。 PDF への印刷はサポートされておらず、ラベル ポリシーが必須ラベル付け用に構成されている場合、このオプションはユーザーに対して使用できなくなります。
- プレビュー段階: ラベルの削除またはダウングレードの理由を要求するようにラベル ポリシーが構成されている場合にユーザーが表示するダイアログ ボックスは、入力された応答に機密データを含めないことをユーザーに警告するように更新されます。 [ラベル ポリシーで [実行できる操作](sensitivity-labels.md#what-label-policies-can-do) ] セクションのスクリーンショットは、この更新されたダイアログ ボックスを示しています。これにより、運用環境で使用するために Office 展開チャネルに進むことができます。
- プレビュー段階: [S/MIME 保護を適用するための Outlook のサポート](sensitivity-labels-office-apps.md#configure-a-label-to-apply-smime-protection-in-outlook) は、クライアント プラットフォーム間でロールアウトされ始めたばかりです。
- [自動ラベル付けポリシー](apply-sensitivity-label-automatically.md#creating-an-auto-labeling-policy)の場合、設定された日数内に編集されていない場合にポリシーを自動的に有効にできる新しい設定。

### <a name="trainable-classifiers"></a>トレーニング可能な分類子

- [トレーニング可能な分類子 (](classifier-learn-about.md) 追加された Adult、Racy、Gory 画像トレーニング可能な分類子) について説明します。

## <a name="may-2022"></a>2022 年 5 月

### <a name="communication-compliance"></a>コミュニケーション コンプライアンス

- [コミュニケーション コンプライアンス レポートと監査](communication-compliance-reports-audits.md) - エクスポートされたレポートのファイル サイズ制限を更新しました。
- [コミュニケーション コンプライアンス ポリシー](communication-compliance-policies.md) - 明確化されたユーザー報告メッセージは、Teams と Exchange のプロセスを無効化/有効化し、処理を明確化しました。

### <a name="compliance-manager"></a>コンプライアンス マネージャー

- [アラートとアラート ポリシー](compliance-manager-alert-policies.md) - すべての組織の既定のスコア変更ポリシーを説明する新しいセクション。
- [改善アクションの操作](compliance-manager-improvement-actions.md) - 実装ステータスとテスト ステータスのステータス状態を明確にし、自動テストされたアクションと手動でテストされたアクションを区別します。
- [テンプレート リスト](compliance-manager-templates-list.md) - ヨーロッパ、中近東およびアフリカ (EMEA) 地域に 2 つの新しいテンプレート、カタール国家情報保証 (NIA) とUAE データ プライバシー法を追加しました。

### <a name="compliance-offerings--service-assurance"></a>コンプライアンス オファリングとサービス アシュアランス

- [Microsoft セキュリティ開発ライフサイクル](/compliance/assurance/assurance-microsoft-security-development-lifecycle) - Microsoft サービスの新しい SDL 保証トピック。

### <a name="data-lifecycle-management-and-records-management"></a>データ ライフサイクル管理とレコード管理

- 現在プレビューでロールアウト中: [保持期間の終了時の新しいラベル変更オプション](retention-settings.md#relabeling-at-the-end-of-the-retention-period)。
- 新しい展開ガイダンス: [Microsoft Purview を使用してデータ ガバナンス ソリューションを展開する](data-governance-solution.md)
- ドキュメントの修正により、リソース メールボックスが静的スコープと適応スコープの両方の Exchange の保持と削除でサポートされていることを確認します。 静的スコープの場合、リソース メールボックスは既定で組織全体のポリシーに含まれます (すべて既定)。
- エンド ユーザー向けの新しいドキュメント: [オンライン アーカイブ メールボックスを使用してメール ストレージを管理する](https://support.services.microsoft.com/office/manage-email-storage-with-online-archive-mailboxes-1cae7d17-7813-4fe8-8ca2-9a5494e9a721)

### <a name="data-loss-prevention"></a>データ損失防止

- [メール通知と DLP ポリシーのポリシー ヒントを送信する](use-notifications-and-policy-tips.md) - 通知をトリガーするものと、通知を受信できるユーザーに関する新しい情報を追加しました。

### <a name="information-barriers"></a>情報バリア

- [情報バリアの詳細](information-barriers.md)、[情報バリアの開始](information-barriers-policies.md) - トピックの構造をリファクタリングし、Exchange Online のサポートと制限についての説明を追加し、新しい IB UI エクスペリエンスのサポートを含むように更新しました。

### <a name="insider-risk-management"></a>インサイダー リスクの管理

- [インサイダー リスク管理設定の開始](insider-risk-management-settings.md) - 新しい Defender for Cloud Apps インジケーターのガイダンスの追加、カスタムしきい値のトリガー イベントとしての新しい変則、新しいファイル拡張子の優先順位付け、秘密度ラベル ポリシーのサポート。
- [インサイダー リスク管理ケース](insider-risk-management-cases.md) - eDiscovery ケース ガイダンスへのエスカレーションを明確にしました。

### <a name="microsoft-priva"></a>Microsoft Priva

- [Priva 無料試用版の詳細](/privacy/priva/priva-trial) - 新しいユニバーサル Microsoft 365 試用版の使用条件への更新されたリンクと、役割と適格性を明確にするためのマイナーな更新。
- [Priva の使用を開始する](/privacy/priva/priva-setup) - Priva の可用性の制限を示すセクションを追加しました。

### <a name="sensitive-information-types"></a>機密情報の種類

- [正確なデータ一致ベースの機密情報の種類の詳細](sit-learn-about-exact-data-match-based-sits.md) - 顧客のエスカレーションから、EDM がサポートされている地域と、テナントの地域を見つける手順を追加しました。
- [EDM SIT ルール パッケージの作成](sit-get-started-exact-data-match-create-rule-package.md) - スキーマの記事から「特定の種類のデータの処理」を追加しました。
- [EDM SIT のスキーマの作成](sit-get-started-exact-data-match-create-schema.md) - 「特定の種類のデータの処理」を削除しました。
- [DLP ポリシーで名前付きエンティティを使用する](named-entities-use.md) - Microsoft Defender for Cloud Apps のサポート ステートメントを追加しました。

### <a name="sensitivity-labels"></a>秘密度ラベル

- ラベルの作成または編集プロセスの最後に、[自動ラベル付け設定を自動ラベル付けポリシーに自動的に変換する](apply-sensitivity-label-automatically.md#convert-your-label-settings-into-an-auto-labeling-policy)新しいオプション。
- SharePoint と OneDrive の自動ラベル付けポリシーで、ファイルを最後に変更したアカウントが Azure AD に存在しなくなったときに、暗号化されたラベルを適用できるようになりました。
- コンテナー ラベルは、Office 365 コンテンツ配信ネットワーク (CDN) でサポートされています。
- [ラベルの削除と削除](create-sensitivity-labels.md#removing-and-deleting-labels)の説明。
- 新しい[一般的なシナリオ](get-started-with-sensitivity-labels.md#common-scenarios-for-sensitivity-labels):
  - ファイルや電子メールに使用しているものと同じ秘密度ラベルを使用して SQL データベース列にラベルを付けて、エクスポート時に、構造化データを保護し続けることができる統合ラベル付けソリューションを組織が持つようにします。
  - 個人データを含むコンテンツが共有されつつあるか、保護が必要であるというアラートを受け取った後に、機密ラベルをファイルに適用する

## <a name="april-2022"></a>2022 年 4 月

### <a name="communication-compliance"></a>コミュニケーション コンプライアンス

- [コミュニケーション コンプライアンス ポリシーを作成して管理する](communication-compliance-policies.md) - Microsoft Teams の統合に向けた新しいユーザー報告型メッセージ ポリシー機能に関するガイダンスを追加して更新しました。
- [コミュニケーション コンプライアンスの使用を開始する](communication-compliance-configure.md) - F5 サブスクリプションとライセンスに関する説明を追加するために更新されました。

### <a name="compliance-manager"></a>コンプライアンス マネージャー

- [コンプライアンスマネージャーテンプレートの一覧](compliance-manager-templates-list.md) - 6 つの新しいテンプレートと、より簡単にテンプレート カテゴリにジャンプするためのナビゲーション リンクがページに追加されました。
- [コンプライアンス マネージャーの概要](compliance-manager.md) - 製品概要ビデオを更新しました。

### <a name="compliance-offerings--service-assurance"></a>コンプライアンス オファリングとサービス アシュアランス

- [コンプライアンス オファリング](/compliance/regulatory/offering-home) - VPATS、SOC、ISO、FedRAMP オファリングのサービス カバレッジと監査レポートを更新します。

### <a name="data-lifecycle-management-and-records-management"></a>データ ライフサイクル管理とレコード管理

- [製品名の変更](#changes-to-product-names)に伴い、コンプライアンス ポータルの **情報ガバナンス** は **データライフサイクル管理** に名称変更されました。
- 現在展開中: 保持ラベル設定構成の新しいデザイン。
- 現在展開中: "既定でこのレコードのロックを解除します"、というプレビューの新しいラベル オプション。 詳細については、「[保持ラベルを構成してレコードを宣言する](declare-records.md#configuring-retention-labels-to-declare-records)」および 「[SharePoint または OneDrive に保存されているレコードを更新するためにレコードのバージョン管理を使用する](record-versioning.md)」を参照してください。

### <a name="data-loss-prevention"></a>データ損失防止

- macOS デバイスのオンボーディング GA に関する以下の記事を更新しました。
  - [エンドポイント DLP に関する詳細](endpoint-dlp-learn-about.md)
  - [エンドポイント データ損失防止の設定を構成する](dlp-configure-endpoint-settings.md)
  - [データ損失防止ポリシー (DLP) のサポート](dlp-overview-plan-for-dlp.md)
  - [データ損失防止ポリシー リファレンス](dlp-policy-reference.md)
  - [エンドポイント データ損失防止の使用を開始する](endpoint-dlp-getting-started.md)
- [DLP ポリシーの条件、例外、およびアクション](dlp-conditions-and-exceptions.md) - [件名の変更] アクションのガイダンスを追加しました。
- [データ損失防止ポリシー リファレンス](dlp-policy-reference.md) - GA SPO/ODB 述語、エンドポイントでのルール処理に関する新しいガイダンスが更新されました。

### <a name="device-onboarding"></a>デバイスのオンボード

- macOS デバイスのオンボーディング GA に関する以下の記事を更新しました。
  - [Microsoft 365 への macOS デバイスのオンボードに関する概要](device-onboarding-macos-overview.md)
  - [Microsoft Defender for Endpoint のお客様向け Intune を使用したコンプライアンス ソリューションへの macOS デバイスのオンボードとオフボード](device-onboarding-offboarding-macos-intune-mde.md)
  - [Intune を使用した Microsoft Purview ソリューションへの macOS デバイスのオンボードとオフボード](device-onboarding-offboarding-macos-intune.md)
  - [Microsoft Defender for Endpoint のお客様向け JAMF Pro を使用したコンプライアンス ソリューションへの macOS デバイスのオンボードとオフボード](device-onboarding-offboarding-macos-jamfpro-mde.md)
  - [JAMF Pro を使用した Microsoft Purview ソリューションへの macOS デバイスのオンボードとオフボード](device-onboarding-offboarding-macos-jamfpro.md)

### <a name="information-barriers"></a>情報バリア

- [SharePoint で情報バリアを使用する](/sharepoint/information-barriers) - SharePoint の新しいプライベート チャネル サポートのためのガイダンスが追加されました。
- [情報バリア ポリシーを管理する](information-barriers-edit-segments-policies.md) - セグメントとポリシー/セグメントを一緒に削除するためのガイダンスが追加されました。

### <a name="microsoft-priva"></a>Microsoft Priva

- [プライバシー リスク管理ポリシー](/privacy/priva/risk-management) - 新規ページ、大幅な更新、ポリシー内容の再構築を行いました。詳細は以下のとおりです。
  - [プライバシー リスク管理ポリシー](/privacy/priva/risk-management-policies) - すべてのポリシーに適用されるポリシーの設定と管理に関する重要な詳細を追加し、3 つのポリシーの種類のそれぞれの新しいページへのリンクを追加しました。
  - [過剰露出データ ポリシー](/privacy/priva/risk-management-policy-data-overexposure) - ポリシーの必要性と用途を明確にし、すぐに作成できる既定の設定と、設定のカスタマイズの詳細な手順について説明します。
  - [データ転送ポリシー](/privacy/priva/risk-management-policy-data-transfer) - 組織外への転送を検出するポリシーの新しい条件を明確にし、ポリシーの必要性と用途を明確にし、すぐに作成できる既定の設定と、設定のカスタマイズの詳細な手順について説明します。
  - [データ最小化ポリシー](/privacy/priva/risk-management-policy-data-minimization) - ポリシーの必要性と用途を明確にし、すぐに作成できる既定の設定と、設定のカスタマイズの詳細な手順について説明します。
  - [アラートを調査して修復する](/privacy/priva/risk-management-alerts) - 読みやすさを向上させるために明確な詳細と書式の変更を追加しました。
  - [ユーザー通知](/privacy/priva/risk-management-notifications) - メール通知の内容をプレビューしてカスタマイズするための機能に関する情報を追加しました。
- [主体の権利を作成する](/privacy/priva/subject-rights-requests-create) - 機能を調べるために、既定の設定を使用して最初の要求を開始するセクションを追加しました。
- [主体の権利要求のデータをレビューする](/privacy/priva/subject-rights-requests-data-review) - 確認が必要な優先アイテムとその検出方法、この分析情報を得るためにデータ照合を設定する必要性を説明する詳細を追加しました。
- [個人用データの検索と可視化](/privacy/priva/priva-data-profile) - 「主な分析情報」の「データ主体のコンテンツが最も多いアイテム」に対する分析情報を受け取るために、ユーザーがデータ照合を設定する必要があることを明確にしました。
- [主体の権利要求のためのデータ照合](/privacy/priva/subject-rights-requests-data-match) - このプロセスの手順の進行を明確にし、機密情報の種類を作成する 2 番目の手順を追加しました。

### <a name="sensitive-information-types"></a>機密情報の種類

- [DLP ポリシーで名前付きエンティティを使用する](named-entities-use.md) - 名前付きエンティティ GA。
- [名前付きエンティティの詳細](named-entities-learn.md) - 名前付きエンティティ GA。
- [機密情報の種類のエンティティの定義](sensitive-information-type-entity-definitions.md) - 名前付きエンティティ GA とパターンの更新。
- [機密情報の種類に関する詳細情報](sensitive-information-type-learn-about.md)名前付きエンティティ GA。

### <a name="sensitivity-labels"></a>秘密度ラベル

- SharePoint サイトで新しくサポートされるシナリオのプレビューが開始されました: 「[PowerShell の詳細設定を使用してサイト共有のアクセス許可を構成する](sensitivity-labels-teams-groups-sites.md#configure-site-sharing-permissions-by-using-powershell-advanced-settings)」
- [秘密度ラベルで暗号化されたファイルの共同編集](sensitivity-labels-coauthoring.md)が、半期エンタープライズ チャネル (プレビュー版) チャネルでテストできるようになりました。
- 削除された OneDrive アカウントが、自動ラベル付けポリシーのシミュレーション結果に正しく表示されるようになりました。
- 暗号化用の秘密度ラベルを構成するときに、[グループ内のメール連絡先にアクセス許可を割り当てる](/office365/troubleshoot/sensitivity-labels/mail-contacts-lose-access-encrypted-content)場合の既知の問題。

### <a name="changes-to-product-names"></a>製品名の変更

今日の分散化されデータにあふれた職場の課題に対応するため、データ資産全体の把握、管理、保護をサポートする一連の包括的なソリューションである [Microsoft Purview](https://aka.ms/microsoftpurview) を紹介します。 この新しいブランド ファミリーは、旧称 Microsoft Purview Data Map の機能と、お客様がすでに信頼している Microsoft 365 コンプライアンス ポートフォリオを組み合わせ、お客様の組織に統一されたデータ ガバナンスとリスク管理を提供します。

| **旧称** | **New Name/新しい名前** | **説明** |
|:----------------|:-------------|:----------------|
| Microsoft 365 の高度な監査 <br><br> Microsoft 365 基本的な監査 | Microsoft Purview 監査 (Premium) <br><br> Microsoft Purview 監査 (Standard)| 監査ソリューションは、セキュリティ イベント、フォレンジック調査、内部調査、コンプライアンス義務に組織が効果的に対応するための統合ソリューションが用意されています。 詳細については、「[Microsoft Purview Advanced 監査 (Premium)](advanced-audit.md)」「[Microsoft Purview Advanced 監査 (Standard)](set-up-basic-audit.md)」を参照してください。 |
| Microsoft 365 でのコミュニケーション コンプライアンス | Microsoft Purview でのコミュニケーション コンプライアンス | コミュニケーション コンプライアンスは、企業のコミュニケーション チャネルやポリシー違反の迅速な検出、取得、是正措置をサポートすることで、リスクを最小化します。 詳細については、「[Microsoft Purview コミュニケーション コンプライアンス](communication-compliance-solution-overview.md)」を参照してください。 |
| Microsoft コンプライアンス マネージャー | Microsoft Purview コンプライアンス マネージャー | コンプライアンス マネージャーは、データ保護リスクのインベントリの作成から、複雑な制御の実装の管理、規制や認証の最新情報の入手、監査人への報告まで、コンプライアンスの過程全体を支援します。詳細については、「[Microsoft Purview コンプライアンス マネージャー](compliance-manager.md)」を参照してください。 |
| Microsoft 365 カスタマー キー | Microsoft Purview カスタマー キー | カスタマー キーは、承認されていないシステムや個人によるデータの閲覧を防止するための追加の保護を提供し、Microsoft データセンターの Bitlocker ディスク暗号化を補完します。 詳細については、「[Microsoft Purview カスタマー キー](customer-key-overview.md)」を参照してください。 |
| Office 365 のカスタマー ロックボックス | Microsoft Purview カスタマー ロックボックス | カスタマー ロックボックスを使用すると、明示的な承認なしにサービス操作を実行するために、Microsoft がコンテンツにアクセスできなくなります。 カスタマー ロックボックスは、Microsoft で使用する承認ワークフロー プロセスを導入し、承認された要求のみコンテンツにアクセスできるようにします。 詳細については、「[Microsoft Purview カスタマー ロックボックス](customer-lockbox-requests.md)」を参照してください。 |
| データ損失防止 | Microsoft Purview データ損失防止 | DLP は、データを保持するべきでないユーザーと不適切に共有できないようにすることで、機密データを保護し、リスクを軽減するのに役立ちます。 詳細については、「[Microsoft Purview データ損失防止](dlp-learn-about-dlp.md)」を参照してください。 |
| Microsoft 365 の二重キー暗号化 | Microsoft Purview 二重キー暗号化 | 二重キー暗号化 (DKE) は、保護されたコンテンツにアクセスするために 2 つの鍵を同時に使用します。 Microsoft は一方の鍵を Microsoft Azure に保管し、もう一方の鍵はユーザーが保持します。 詳細については、「[Microsoft Purview 二重キー暗号化](double-key-encryption.md)」を参照してください。 |
| Microsoft 365 の情報バリア | Microsoft Purview 情報バリア | 情報バリアは、組織内の特定のユーザーとのコミュニケーションやコラボレーションを制限し、内部情報を保護するソリューションです。 詳細については、「[Microsoft Purview 情報バリア](information-barriers-solution-overview.md)」を参照してください。 |
| Microsoft Information Protection | Microsoft Purview Information Protection | Information Protection を使用すれば、機密情報がどこに保存されていても、どこに移動しても、それらの情報の検出、分類、保護が可能になります。 詳細については、「[Microsoft Purview Information Protection](information-protection.md)」を参照してください。 |
| Microsoft 情報ガバナンス | Microsoft Purview データ ライフサイクル管理 | データ ライフサイクル管理は、保持する必要があるコンテンツを保持し、保持しないコンテンツを削除するためのツールと機能を提供します。 詳細については、「[Microsoft Purview データ ライフサイクル管理](data-lifecycle-management.md)」を参照してください。 |
| Microsoft 365 インサイダー リスク管理 | Microsoft Purview インサイダー リスク管理 | インサイダー リスク管理では、幅広いサービスとサードパーティの指標を使用して、リスクの高いユーザー アクティビティをすばやく特定、トリアージ、および対処するのに役立ちます。詳細については、「[Microsoft Purview インサイダー リスク管理](insider-risk-management.md)」を参照してください。 |
| Office 365 Message Encryption | Microsoft Purview のメッセージの暗号化 | Message Encryption を使用すると、組織は組織内外のユーザーとの間で暗号化されたメール メッセージを送受信できます。詳細については、「[Microsoft Purview Message Encryption](ome.md)」を参照してください。 |
| Microsoft 365 での特権アクセス管理 | Microsoft Purview Privileged Access Management | 特権アクセス管理は、機密データへの常時アクセスや重要な構成設定へのアクセスを制限することで、組織を情報漏えいから守り、コンプライアンスのベスト プラクティスに適合させるのに役立ちます。 詳細については、「[Microsoft Purview Privileged Access Management](privileged-access-management-solution-overview.md)」を参照してください。 |
| Microsoft データ コネクタ | Microsoft Purview データ コネクタ | Microsoft 365 を使用すると、管理者はソーシャル メディア プラットフォーム、インスタント メッセージング プラットフォーム、ドキュメント コラボレーション プラットフォームからのサードパーティ データを、Microsoft 365 組織のメールボックスにインポートしてアーカイブすることができます。 詳細については、「[Microsoft Purview データ コネクタ](compliance-extensibility.md)」を参照してください。 |
| Microsoft 365 Advanced eDiscovery <br><br> Microsoft 365 Core eDiscovery | Microsoft Purview 電子情報開示 (プレミアム) <br><br> Microsoft Purview eDiscovery (Standard) | 電子情報開示 (eDiscovery) とは、訴訟で証拠として使用できる電子的情報を特定および提供するプロセスです。 詳細については、「[Microsoft Purview eDiscovery (Premium)](overview-ediscovery-20.md)」「[Microsoft Purview eDiscovery (Standard)](get-started-core-ediscovery.md)」を参照してください。 |
| Microsoft 365 コンプライアンス センター | Microsoft Purview コンプライアンス ポータル | Microsoft 365 E5 Compliance スイート内のソリューションとソリューション カタログにアクセスするための管理者ポータル。 詳細については、「[Microsoft Purview コンプライアンス ポータル](microsoft-365-compliance-center.md)」を参照してください。 |

## <a name="march-2022"></a>2022 年 3 月

### <a name="communication-compliance"></a>コミュニケーション コンプライアンス

- [コミュニケーション コンプライアンス警告の調査と修復](communication-compliance-investigate-remediate.md) - 非推奨の注釈ビューのガイダンスを削除しました。

### <a name="compliance-manager"></a>コンプライアンス マネージャー

- [改善のための処置の操作](compliance-manager-improvement-actions.md)、[コンプライアンス マネージャーの使用を開始する](compliance-manager-setup.md) - 自動的に監視およびテストできる改善のための処置 (「継続的なコンプライアンス評価」) に関する情報を追加しました。これには、ある処置のテスト状態を別の処置のテスト状態に親和させる新しい機能が含まれます。

### <a name="data-classification"></a>データの分類

- [コンテンツ エクスプローラーを開始する](data-classification-content-explorer.md) - ライセンス セクションでサービスの説明を指摘する、チーム ガイダンスを追加しました。

### <a name="data-lifecycle-management-and-records-management"></a>データ ライフサイクル管理とレコード管理

- [Yammerのアイテム保持ポリシー](create-retention-policies.md#retention-policy-for-yammer-locations)が一般公開 (GA) されました。
- 共有チャネルのサポートは、現在プレビュー段階です。Teams チャネル メッセージの場所に対するアイテム保持ポリシーを構成すると、共有チャネルがある場合、それらはデータ保持設定を親チームから継承します。
- [コンテンツ処理のテナント単位での制限](retention-limits.md#maximum-number-of-items-for-disposition)。

### <a name="data-loss-prevention"></a>データ損失防止

- [データ損失防止と Microsoft Teams](dlp-microsoft-teams.md) - Teams チャネル コンテンツの共有のパブリック プレビュー。
- [Microsoft Compliance Extension を開始する](dlp-chrome-get-started.md) - 制限されたアプリ グループの公開プレビュー、レジストリ キーの手順の削除、構成が既定で有効になりました。
- [エンドポイント データ損失防止の構成](dlp-configure-endpoint-settings.md) - 制限されたアプリ グループのパブリック プレビュー向け新機能。
- [データ損失防止ポリシー参照](dlp-policy-reference.md) - 制限付きアプリ グループのパブリック プレビュー用に更新されました。
- [Power BI のデータ損失防止の使用を開始する](dlp-powerbi-get-started.md) - パブリック プレビュー向け新機能。
- 
### <a name="information-protection"></a>情報保護

- [2 バイト文字セットのリリース ノート向けサポート](mip-dbcs-relnotes.md) - macOS 向けのガイダンスが追加されました。
- 
### <a name="insider-risk-management"></a>インサイダー リスクの管理

- [インサイダー リスクの管理を開始する](insider-risk-management-configure.md) - おすすめの操作ガイダンスに新しいタスクが追加されました。
- [インサイダー リスク管理設定の使用を開始する](insider-risk-management-settings.md) - 通知とメール アラート機能の新しい更新情報、分析通知の新しい更新情報。

### <a name="microsoft-priva"></a>Microsoft Priva

- [Priva の設定を構成する](/privacy/priva/priva-settings) - データ主体の権利の要求のデータ保持期間に関する明確な情報を更新し、データ主体の権利の要求のデータ レビュー タグの管理および適用に関する詳細を追加しました。
- [データ主体の権利の要求を作成する](/privacy/priva/subject-rights-requests-create) - 検索の絞り込み、条件と属性の選択に関する詳細を追加しました。ユーザーが検索ですべてのバージョンの SharePoint アイテムを選択できる新機能に関する情報を追加しました (既定の設定では、現在のバージョンの SharePoint アイテムのみが返されます)。
- [データ主体の権利の要求用のデータのレビュー](/privacy/priva/subject-rights-requests-data-review) - 手順 3 で、ファイルを包含/除外としてマークする、ファイルに注釈を付けて冗長化を適用する、タグを適用する、メモを入力するなど、データ レビュー段階でアイテムをレビューするための詳細が追加されました。
- [レポートを生成し、データ主体の権利の要求を満たす](/privacy/priva/subject-rights-requests-reports) - レポートの理解方法に関する詳細の追加、エクスポート パッケージの生成のタイミングとそのコンテンツの操作方法の明確化、監査ログ、タグ付けされたファイル レポート、SRR データとレポートの保持期間に関する情報が追加されました。

### <a name="sensitivity-labels"></a>秘密度ラベル

- [Teams の機密度ラベル](sensitivity-labels-teams-groups-sites.md):
  - 共有チャネルのサポートは、現在プレビュー中です。チームに共有チャネルがある場合、そのチームは親チームから秘密度ラベル設定を自動的に継承し、そのラベルを削除したり、別のラベルに置き換えたりすることはできません。
  - 以前は [Teams Graph API と PowerShell コマンドレットでサポートされていない]( /microsoftteams/sensitivity-labels#limitations)と一覧表示されていたテンプレートのサポート。  
- Web 上の Word、Excel、PowerPoint の監査の場合、理由テキストが完全に展開されるようになりました。
- Web 上の Word、Excel、PowerPoint の既存のドキュメントに既定のラベルの適用が本格的に展開されました。

## <a name="february-2022"></a>2022 年 2 月

### <a name="ediscovery"></a>電子情報開示

- [eDiscovery (Premium) でカストディアンの通信テンプレートを管理する](advanced-ediscovery-communications-library.md) - eDiscovery マネージャーは、組織内のすべての eDiscovery (Premium) ケースで使用できるカストディアン通信テンプレートを作成できるようになりました。
- [ eDiscovery (Premium) の発行責任者を管理する](advanced-ediscovery-issuing-officers.md) - eDiscovery 管理者は、組織内のあらゆる eDiscovery (Premium) ケースのカストディアンの通信に割り当てることができる発行責任者の一覧を追加できます。

### <a name="data-lifecycle-management-and-records-management"></a>データ ライフサイクル管理とレコード管理

- アイテム保持ポリシーと保持ラベル ポリシーの[アダプティブ スコープ](retention.md#adaptive-or-static-policy-scopes-for-retention)が一般公開 (GA) されました。 [アダプティブ スコープの構成](retention-settings.md#to-configure-an-adaptive-scope)の手順には、SharePoint サイト スコープに関する詳細情報が含まれるようになりました。これは、カスタム サイト プロパティの使用に関するブログ記事の参照と、サイトプロパティ SiteTemplate を使用して、高度なクエリ ビルダーで特定のサイトの種類を対象にしたり除外したりする方法です。
- データ ライフサイクル管理での[ポリシー検索](retention.md#policy-lookup)が一般公開 (GA) されました。
- [Get-PnPTenant](https://pnp.github.io/powershell/cmdlets/Get-PnPTenant.html) と [Set-PnPTenant](https://pnp.github.io/powershell/cmdlets/Set-PnPTenant.html) から AllowFilesWithKeepLabelToBeDeletedSPO および AllowFilesWithKeepLabelToBeDeletedODB を使用して、ユーザーが SharePoint および OneDrive のラベル付けされたアイテムを削除できるレコード管理設定に代わる PowerShell の設定。

### <a name="sensitivity-labels"></a>秘密度ラベル

- Windows コンピューター用の Azure Information Protection (AIP) 統合ラベリング クライアントを使用している場合、[Office アプリの AIP アドインに組み込みラベル付けを選択する理由](sensitivity-labels-aip.md)の新しいガイダンス。 このページでは、Office アプリの新しいプライベート プレビューに関する情報があります。
- [自動ラベル付けポリシー](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)向けの新しい設定
  - メールに関する追加設定では、常に一致した秘密度ラベルを適用し、組織外から受信したメールに暗号化を適用することをサポートします。
  - **[指定済]** に既定値の **[すべて]** を指定した場合、新しい **[除外]** オプションを使用して特定のインスタンス (ユーザー、グループ、サイト) の除外がサポートされます。
- 現在プレビュー中です。モバイル デバイス (iOS および Android) には最小限のバージョンがあり、このプレビューにオプトインした場合に[共同編集](sensitivity-labels-coauthoring.md)をサポートします。
- 既定の共有リンクの種類の設定に対するサポートが、SharePoint と OneDrive の個々のドキュメントに拡張されました。 詳細については、「[秘密度ラベルを使用して、SharePoint と OneDrive のサイトとドキュメントの既定の共有依存タイプを構成する]( sensitivity-labels-default-sharing-link.md)」に関する新しい記事を参照してください。
- Teams 管理センターがコンテナー ラベル (グループとサイトの範囲を含む秘密度ラベル) をサポートするようになりました。
