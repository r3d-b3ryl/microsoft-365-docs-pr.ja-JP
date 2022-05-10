---
title: Microsoft Purview の最新情報
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
description: コンプライアンス センターに新しいソリューションを追加する場合でも、フィードバックに基づいて既存の機能を更新する場合でも、更新されたドキュメントを展開する場合でも、Microsoft 365は絶えず変化するコンプライアンス環境を把握するのに役立ちます。 今月までの内容を確認してください。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3bfa6ce581b0bd4846ebe27b95cf27d1228b10b2
ms.sourcegitcommit: f723ebbc56db8013598a88b0d7f13214d9d3eb10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2022
ms.locfileid: "65294619"
---
# <a name="whats-new-in-microsoft-purview"></a>Microsoft Purview の最新情報

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

[Microsoft Purview コンプライアンス ポータル](microsoft-365-compliance-center.md)に新しいソリューションを追加する場合でも、フィードバックに基づいて既存の機能を更新する場合でも、新しく更新されたドキュメントを展開する場合でも、Microsoft 365常に変化するコンプライアンス環境を把握するのに役立ちます。 Microsoft Purview の現在の新機能については、以下をご覧ください。

> [!NOTE]
> 一部のコンプライアンス機能は、お客様に対して異なる速度でロールアウトされます。 まだ機能が表示されていない場合は、 [対象となるリリース](/office365/admin/manage/release-options-in-office-365)に自分を追加してみてください。

> [!TIP]
> 他の管理センターで何が起こっているか興味がありますか? 次の記事を確認してください。
>
> - [Microsoft 365 管理センターの新機能](/office365/admin/whats-new-in-preview)
> - [SharePoint 管理センターの新機能](/sharepoint/what-s-new-in-admin-center)
> - [Microsoft 365 Defender の新機能](../security/defender/whats-new.md)
>
> Microsoft 365[ロードマップ](https://www.microsoft.com/microsoft-365/roadmap)にアクセスして、起動、ロールアウト、開発中、取り消し済み、または以前にリリースされたMicrosoft 365機能について説明します。

## <a name="april-2022"></a>2022 年 4 月

### <a name="communication-compliance"></a>コミュニケーション コンプライアンス

- [通信コンプライアンス ポリシーの作成と管理](communication-compliance-policies.md) - Microsoft Teams統合のための新しいユーザー報告メッセージ ポリシー機能に関するガイダンスが追加されて更新されました。
- [通信コンプライアンスの概要](communication-compliance-configure.md) - F5 サブスクリプションとライセンスの明確化を追加するように更新されました。

### <a name="compliance-manager"></a>コンプライアンス マネージャー

- [Compliance Manager テンプレートの一覧](compliance-manager-templates-list.md) - ページに 6 つの新しいテンプレートとナビゲーション リンクを追加して、テンプレート カテゴリに簡単にジャンプできるようになりました。
- [コンプライアンス マネージャーの概要](compliance-manager.md) - 更新された製品の概要ビデオ。

### <a name="compliance-offerings--service-assurance"></a>コンプライアンス オファリング&サービス アシュアランス

- [コンプライアンス オファリング](/compliance/regulatory/offering-home) - VPATS、SOC、ISO、FedRAMP オファリングのサービス カバレッジと監査レポートの更新。

### <a name="data-lifecycle-management-and-records-management"></a>データ ライフサイクル管理とレコード管理

- [Microsoft Purview を使用してデータを管理](manage-data-governance.md) する - データ コネクタはこのページから削除され、レコード管理ソリューションはピア製品として表示されます。
- [アイテム保持ポリシーと保持ラベルの一般的な設定](retention-settings.md) - 新しく設計された保持ラベル ウィザードの新しいナビゲーションと UI 参照が反映されます。
- [保持ラベルを使用してレコードを宣言](declare-records.md)し、[レコードのバージョン管理を使用してSharePointまたはOneDriveに格納されているレコードを更新](record-versioning.md)します。プレビュー段階で現在展開されている新しい "既定でこのレコードのロックを解除する" ラベル設定に関する新しい情報。
- [ファイル プランを使用して保持ラベルを作成および管理](file-plan-manager.md#information-about-the-label-properties-for-import)  します。インポート セクションでは、インポートで現在サポートされていないラベル設定が開示されるようになりました (既定では、このレコードを多段階で確認してロック解除します)。

### <a name="data-loss-prevention"></a>データ損失防止

- macOS デバイスオンボード GA 用に更新された記事:
  - [エンドポイント DLP について学習する](endpoint-dlp-learn-about.md)
  - [エンドポイント データ損失防止の設定を構成する](dlp-configure-endpoint-settings.md)
  - [データ損失防止 (DLP) の計画](dlp-overview-plan-for-dlp.md)
  - [データ損失防止ポリシーリファレンス](dlp-policy-reference.md)
  - [エンドポイント データ損失防止の使用を開始する](endpoint-dlp-getting-started.md)
- [DLP ポリシーの条件、例外、アクション](dlp-conditions-and-exceptions.md) - 件名の変更アクションに関するガイダンスが追加されました。
- [データ損失防止ポリシー リファレンス](dlp-policy-reference.md) - GA SPO/ODB 述語。エンドポイントでのルール処理に関する新しいガイダンスを使用して更新されました。

### <a name="device-onboarding"></a>デバイスオンボーディング

- macOS デバイスオンボード GA 用に更新された記事:
  - [macOS デバイスをMicrosoft 365の概要にオンボードする](device-onboarding-macos-overview.md)
  - [Microsoft Defender for Endpoint のお客様向け Intune を使用したコンプライアンス ソリューションへの macOS デバイスのオンボードとオフボード](device-onboarding-offboarding-macos-intune-mde.md)
  - [Intune を使用した Microsoft Purview ソリューションへの macOS デバイスのオンボードとオフボード](device-onboarding-offboarding-macos-intune.md)
  - [Microsoft Defender for Endpoint のお客様向け JAMF Pro を使用したコンプライアンス ソリューションへの macOS デバイスのオンボードとオフボード](device-onboarding-offboarding-macos-jamfpro-mde.md)
  - [JAMF Proを使用して macOS デバイスを Microsoft Purview ソリューションにオンボードおよびオフボードする](device-onboarding-offboarding-macos-jamfpro.md)

### <a name="information-barriers"></a>情報バリア

- [SharePointで情報バリアを使用する](/sharepoint/information-barriers) - SharePointで新しいプライベート チャネルのサポートに関するガイダンスを追加しました。
- [情報バリア ポリシーを管理する](information-barriers-edit-segments-policies.md) - セグメントとポリシー/セグメントをまとめて削除するためのガイダンスを追加しました。

### <a name="microsoft-priva"></a>Microsoft Priva

- [プライバシー リスク管理ポリシー](/privacy/priva/risk-management) - 新しいページ、重要な更新プログラム、ポリシー コンテンツの再構築。以下の詳細:
  - [プライバシー リスク管理ポリシー](/privacy/priva/risk-management-policies) - すべてのポリシーに適用されるポリシーのセットアップと管理に関する重要な詳細を追加しました。3 つのポリシーの種類ごとに新しいページへのリンクが追加されました。
  - [データの露出過剰ポリシー - ポリシー](/privacy/priva/risk-management-policy-data-overexposure) の必要性と用途を明確にします。では、既定の作成の既定の設定と、設定をカスタマイズするための詳細な手順について説明します。
  - [データ転送ポリシー](/privacy/priva/risk-management-policy-data-transfer) - ポリシーが組織外の転送を検出するための新しい条件を強調表示します。ポリシーの必要性と用途を明確にします。では、既定の作成の既定の設定と、設定をカスタマイズするための詳細な手順について説明します。
  - [データ最小化ポリシー - ポリシー](/privacy/priva/risk-management-policy-data-minimization) の必要性と用途を明確にします。では、既定の作成の既定の設定と、設定をカスタマイズするための詳細な手順について説明します。
  - [アラートを調査して修復](/privacy/priva/risk-management-alerts) する - 読みやすくするために詳細と書式設定の変更を明確にしました。
  - [ユーザー通知](/privacy/priva/risk-management-notifications) - 電子メール通知コンテンツをプレビューおよびカスタマイズするための機能に関する情報を追加しました。
- [サブジェクト権限要求を作成](/privacy/priva/subject-rights-requests-create) する - 機能を調べる既定の設定を使用して、最初の要求の開始に関するセクションを追加しました。
- [サブジェクト権利要求のデータを確認](/privacy/priva/subject-rights-requests-data-review) する - 確認する優先度項目とその検索方法を説明する詳細と、この分析情報を取得するためにデータ一致を設定する必要性を追加しました。
- [個人データを見つけて視覚化](/privacy/priva/priva-data-profile) する - "Key insights" の下にある "データ主体のコンテンツが最も多いアイテム" の分析情報を受け取るために、ユーザーがデータマッチングを設定する必要があることを明確にしました。
- [サブジェクト権利要求のデータ照合](/privacy/priva/subject-rights-requests-data-match) - このプロセスのステップ進行を明確にし、機密情報の種類を作成する 2 番目の手順を追加しました。

### <a name="sensitive-information-types"></a>機密情報の種類

- [DLP ポリシーで名前付きエンティティ](named-entities-use.md) (名前付きエンティティ GA) を使用します。
- [名前付きエンティティ - 名前付きエンティティ GA について説明](named-entities-learn.md) します。
- [機密情報の種類エンティティ定義](sensitive-information-type-entity-definitions.md) - 名前付きエンティティ GA、およびパターンの更新。
- [機密情報の種類 (](sensitive-information-type-learn-about.md) 名前付きエンティティ GA) について説明します。

### <a name="sensitivity-labels"></a>秘密度ラベル

- [秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護](sensitivity-labels-teams-groups-sites.md#configure-site-sharing-permissions-by-using-powershell-advanced-settings)します。PowerShell の詳細設定を使用して、サイト共有アクセス許可の新しい構成がプレビュー段階になりました。
- [秘密度ラベルを使用して暗号化を適用してコンテンツへのアクセスを制限](encryption-sensitivity-labels.md) する - メール連絡先を含むグループを指定するための既知の問題が追加されました。詳細と回避策については、発行された KB へのリンクが含まれています。
- [コンテンツに秘密度ラベルを自動的に適用する](apply-sensitivity-label-automatically.md) - 削除されたOneDrive サイトが自動ラベル付けポリシーのシミュレーション結果に正しく表示されないという既知の問題が削除されました)
- [秘密度ラベルで暗号化されたファイルの共同編集を有効にします](sensitivity-labels-coauthoring.md)。顧客からのフィードバックの結果として、この機能がまだSemi-Annual Enterprise チャネルでサポートされていないという前提条件セクションの吹き出しが削除され、代わりに最小バージョン 2202 でチャネル (プレビュー) Semi-Annual Enterprise追加されました。
- [Office アプリで秘密度ラベルを管理](sensitivity-labels-office-apps.md)する - 既存のドキュメントに既定のラベルを適用するためのサポートの詳細が更新され、Windowsでは、このリリースは引き続きベータ チャネルで展開され、Web 向けに完全にロールアウトされます。

### <a name="changes-to-product-names"></a>製品名の変更

今日の分散型のデータリッチな職場の課題に対応するために、Microsoft [Purview](https://aka.ms/microsoftpurview) は、データ資産全体を理解、管理、保護するのに役立つ包括的なソリューションセットです。 この新しいブランド ファミリは、以前の Microsoft Purview Data Map の機能と、顧客が既に信頼しているMicrosoft 365コンプライアンス ポートフォリオを組み合わせて、組織に統合されたデータ ガバナンスとリスク管理を提供します。

| **以前の名前** | **New Name/新しい名前** | **説明** |
|:----------------|:-------------|:----------------|
| 高度な監査のMicrosoft 365 <br><br> Microsoft 365基本監査 | Microsoft Purview 監査 (プレミアム) <br><br> Microsoft Purview 監査 (Standard)| 監査ソリューションは、組織がセキュリティ イベント、フォレンジック調査、内部調査、コンプライアンス義務に効果的に対応するのに役立つ統合ソリューションを提供します。 詳細については、「[Microsoft Purview Advanced Audit (プレミアム)](advanced-audit.md)」と[「Microsoft Purview Advanced Audit (Standard)」](set-up-basic-audit.md)を参照してください。 |
| Microsoft 365コミュニケーション コンプライアンス | Microsoft Purview でのコミュニケーション コンプライアンス | コミュニケーション コンプライアンスは、会社のコミュニケーション チャネルとポリシー違反の迅速な検出、キャプチャ、修復アクションの実行を支援することで、リスクを最小限に抑えるのに役立ちます。 詳細については、「 [Microsoft Purview Communication Compliance](communication-compliance-solution-overview.md)」を参照してください。 |
| Microsoft コンプライアンス マネージャー | Microsoft Purview コンプライアンス マネージャー | コンプライアンス マネージャーは、データ保護リスクのインベントリの作成から、複雑な制御の実装の管理、規制や認証の最新情報の入手、監査人への報告まで、コンプライアンスの過程全体を支援します。 詳細については、 [Microsoft Purview コンプライアンス マネージャーに関する](compliance-manager.md)ページを参照してください。 |
| 顧客キーのMicrosoft 365 | Microsoft Purview カスタマー キー | カスタマー キーは、承認されていないシステムまたは担当者によるデータの表示に対する保護を強化し、Microsoft データ センターでの BitLocker ディスク暗号化を補完します。 詳細については、 [Microsoft Purview カスタマー キーに関するページを](customer-key-overview.md)参照してください。 |
| Office 365 のカスタマー ロックボックス | Microsoft Purview カスタマー ロックボックス | カスタマー ロックボックスを使用すると、Microsoft が明示的な承認なしにサービス操作を行うためにコンテンツにアクセスできなくなります。 Customer Lockbox は、承認された要求のみがコンテンツへのアクセスを許可するように Microsoft が使用する承認ワークフロー プロセスに移行します。 詳細については、「 [Microsoft Purview Customer Lockbox](customer-lockbox-requests.md)」を参照してください。 |
| データ損失防止 | Microsoft Purview データ損失防止 | DLP は、機密データを保護し、ユーザーがデータを持つべきでないユーザーと不適切に共有できないようにすることで、リスクを軽減するのに役立ちます。 詳細については、「 [Microsoft Purview データ損失防止](dlp-learn-about-dlp.md)」を参照してください。 |
| Microsoft 365のダブル キー暗号化 | Microsoft Purview Double Key Encryption | Double Key Encryption (DKE) では、2 つのキーを一緒に使用して、保護されたコンテンツにアクセスします。 Microsoft は 1 つのキーをMicrosoft Azureに格納し、もう一方のキーを保持します。 詳細については、[Microsoft Purview Double Key Encryption](double-key-encryption.md) に関するページを参照してください。 |
| Microsoft 365情報バリア | Microsoft Purview 情報バリア | 情報バリアは、内部情報を保護するために組織内の特定のユーザー間のコミュニケーションとコラボレーションを制限するソリューションです。 詳細については、 [Microsoft Purview 情報バリアに関する](information-barriers-solution-overview.md)ページを参照してください。 |
| Microsoft Information Protection | Microsoft Purview Information Protection | 情報保護は、機密情報がどこに存在するか、移動する場所を問わず、検出、分類、および保護するのに役立ちます。 詳細については、「[Microsoft Purview Information Protection](information-protection.md)」を参照してください。 |
| Microsoft 情報ガバナンス | Microsoft Purview データ ライフサイクル管理 | データ ライフサイクル管理では、保持および削除する必要があるコンテンツを保持するためのツールと機能が提供されます。 詳細については、「 [Microsoft Purview データ ライフサイクル管理](data-lifecycle-management.md)」を参照してください。 |
| Microsoft 365 インサイダー リスク管理 | Microsoft Purview インサイダー リスク管理 | インサイダー リスク管理では、幅広いサービスとサードパーティの指標を使用して、リスクの高いユーザー アクティビティをすばやく特定、トリアージ、および対処するのに役立ちます。 詳細については、「 [Microsoft Purview Insider Risk Management](insider-risk-management.md)」を参照してください。 |
| Office 365 Message Encryption | Microsoft Purview のメッセージの暗号化 | Message Encryption を使用すると、組織は組織内外のユーザー間で暗号化された電子メール メッセージを送受信できます。 詳細については、「 [Microsoft Purview メッセージ暗号化](ome.md)」を参照してください。 |
| Microsoft 365の特権アクセス管理 | Microsoft Purview Privileged Access Management | Privileged Access Management は、組織を侵害から保護し、機密データへの永続的なアクセスや重要な構成設定へのアクセスを制限することで、コンプライアンスのベスト プラクティスを満たすのに役立ちます。 詳細については、「 [Microsoft Purview Privileged Access Management](privileged-access-management-solution-overview.md)」を参照してください。 |
| Microsoft データ コネクタ | Microsoft Purview データ コネクタ | Microsoft 365管理者は、データ コネクタを使用して、Microsoft 以外のサード パーティのデータをソーシャル メディア プラットフォーム、インスタント メッセージング プラットフォーム、ドキュメント コラボレーション プラットフォームから、Microsoft 365組織内のメールボックスにインポートおよびアーカイブできます。 詳細については、 [Microsoft Purview データ コネクタに関するページを](compliance-extensibility.md)参照してください。 |
| Microsoft 365 Advanced eDiscovery <br><br> Microsoft 365 Core 電子情報開示 | Microsoft Purview 電子情報開示 (プレミアム) <br><br> Microsoft Purview 電子情報開示 (標準) | 電子情報開示 (eDiscovery) とは、訴訟で証拠として使用できる電子的情報を特定および提供するプロセスです。 詳細については、「[Microsoft Purview 電子情報開示 (プレミアム)](overview-ediscovery-20.md)」と[「Microsoft Purview 電子情報開示 (Standard)」](get-started-core-ediscovery.md)を参照してください。 |
| Microsoft 365 コンプライアンス センター | Microsoft Purview コンプライアンス ポータル | Microsoft 365 E5 Compliance スイート内のソリューションとソリューション カタログにアクセスするための管理ポータル。 詳細については、 [Microsoft Purview コンプライアンス ポータル](microsoft-365-compliance-center.md)を参照してください。 |

## <a name="march-2022"></a>2022 年 3 月

### <a name="communication-compliance"></a>コミュニケーション コンプライアンス

- [通信コンプライアンス アラートを調査して修復](communication-compliance-investigate-remediate.md) する - 非推奨の注釈ビューのガイダンスが削除されました。

### <a name="compliance-manager"></a>コンプライアンス マネージャー

- [コンプライアンス マネージャーと概要](compliance-manager-setup.md)[改善アクションを操作](compliance-manager-improvement-actions.md)する - 自動的に監視およびテストできるより多くの改善アクション ("継続的なコンプライアンス評価") に関する情報を追加しました。これには、アクションのテスト状態を別のアクションのテスト状態を親にする新しい機能が含まれます。

### <a name="data-classification"></a>データ分類

- [コンテンツ エクスプローラーを使用したはじめに](data-classification-content-explorer.md) - Teamsガイダンスが追加されました。ライセンス セクションでは、サービスの説明が示されています。

### <a name="data-lifecycle-management-and-records-management"></a>データ ライフサイクル管理とレコード管理

- [Yammerのアイテム保持ポリシー](create-retention-policies.md#retention-policy-for-yammer-locations)が一般公開されました (GA)。
- 現在プレビュー段階の共有チャネルのサポート。 Teams チャネル メッセージの場所に対してアイテム保持ポリシーを構成すると、共有チャネルは親チームから保持設定を継承します。
- [コンテンツ処理のテナントごとの制限](retention-limits.md#maximum-number-of-items-for-disposition)。

### <a name="data-loss-prevention"></a>データ損失防止

- [データ損失防止とMicrosoft Teams](dlp-microsoft-teams.md) - Share Teams Channels コンテンツのパブリック プレビュー。
- [Microsoft コンプライアンス拡張機能の概要](dlp-chrome-get-started.md) - 制限付きアプリ グループのパブリック プレビュー、レジストリ キーの手順の削除、既定での構成が有効になりました。
- [エンドポイント データ損失防止設定を構成する](dlp-configure-endpoint-settings.md) - 制限付きアプリ グループのパブリック プレビュー用に新しく追加されました。
- [データ損失防止ポリシー リファレンス](dlp-policy-reference.md) - 制限付きアプリ グループのパブリック プレビュー用に更新されました。
- [Power BIのデータ損失防止に関する概要](dlp-powerbi-get-started.md) - パブリック プレビュー用の新機能。

### <a name="insider-risk-management"></a>インサイダー リスクの管理

- [インサイダー リスク管理の概要](insider-risk-management-configure.md) - 推奨されるアクション ガイダンスの新しいタスクが追加されました。
- [インサイダー リスク管理設定を使用した概要](insider-risk-management-settings.md) - 通知と電子メール アラート機能の新しい更新プログラム、分析通知の新しい更新プログラム。

### <a name="microsoft-information-protection"></a>Microsoft Information Protection

- [2 バイト文字セットのリリース ノートのサポート](mip-dbcs-relnotes.md) - macOS のガイダンスが追加されました。

### <a name="microsoft-priva"></a>Microsoft Priva

- [Priva 設定を構成する](/privacy/priva/priva-settings) - サブジェクト権限要求のデータ保持期間に関する情報を明確に更新しました。サブジェクト権限要求のデータ レビュー タグの管理と適用に関する詳細が追加されました。
- [サブジェクト権限要求を作成](/privacy/priva/subject-rights-requests-create)する - 検索の絞り込みと条件と属性の選択に関する詳細を追加しました。ユーザーが検索でSharePointアイテムのすべてのバージョンを選択できるようにする新機能に関する情報が追加されました (既定の設定と、現在のバージョンのSharePoint項目のみを返します)。
- [サブジェクト権利要求のデータを確認](/privacy/priva/subject-rights-requests-data-review) する - データレビュー ステージ中にアイテムを確認するための手順 3 の詳細が追加されました。これには、ファイルをインクルード/除外としてマークする、ファイルに注釈を付けてやり直しを適用する、タグを適用する、メモを入力するなどです。
- [レポートを生成し、件名の権利要求を満たす](/privacy/priva/subject-rights-requests-reports) - レポートを理解する方法に関する詳細を追加しました。エクスポート パッケージがいつ生成されるか、およびその内容を操作する方法が明確になります。監査ログ、タグ付けされたファイル レポート、および SRR データとレポートの保持期間に関する情報が追加されました。

### <a name="sensitivity-labels"></a>秘密度ラベル

- [Teamsの秘密度ラベル](sensitivity-labels-teams-groups-sites.md):
  - 現在プレビュー段階の共有チャネルのサポート。 チームに共有チャネルがある場合、そのチームは親チームから秘密度ラベル設定を自動的に継承し、そのラベルを削除したり、別のラベルに置き換えたりすることはできません。
  - Teams Graph [API および PowerShell コマンドレットではサポートされていない]( /microsoftteams/sensitivity-labels#limitations)テンプレートのサポート。  
- Word、Excel、およびPowerPoint on the webを監査するために、正当な理由テキストが完全にロールアウトされるようになりました。
- Word、Excel、およびPowerPoint on the webの既存のドキュメントに既定のラベルを適用することが完全にロールアウトされました。

## <a name="february-2022"></a>2022 年 2 月

### <a name="ediscovery"></a>電子情報開示

- [電子情報開示 (プレミアム) でカストディアン通信テンプレートを管理](advanced-ediscovery-communications-library.md)する - 電子情報開示マネージャーは、組織内の任意の電子情報開示 (プレミアム) ケースで使用できるカストディアン通信テンプレートを作成できるようになりました。
- [電子情報開示 (プレミアム) で発行担当者を管理](advanced-ediscovery-issuing-officers.md)する - 電子情報開示マネージャーは、組織内の任意の電子情報開示 (プレミアム) ケースでカストディアン通信に割り当てることができる発行担当者の一覧を追加できます。

### <a name="data-lifecycle-management-and-records-management"></a>データ ライフサイクル管理とレコード管理

- アイテム保持ポリシーとアイテム保持ラベル ポリシーの[アダプティブ スコープ](retention.md#adaptive-or-static-policy-scopes-for-retention)が一般公開されました (GA)。 [アダプティブ スコープを構成する](retention-settings.md#to-configure-an-adaptive-scope)手順には、SharePointサイト スコープの詳細が含まれるようになりました。カスタム サイト プロパティを使用するためのブログ投稿リファレンスと、サイト プロパティ SiteTemplate を使用して、高度なクエリ ビルダーで特定のサイトの種類を含めるか除外する方法について説明します。
- データ ライフサイクル管理ソリューションの[ポリシー参照](retention.md#policy-lookup)が一般公開されました (GA。
- ユーザーが AllowFilesWithKeepLabelToBeDeletedSPO と AllowFilesWithKeepLabelToBeDeletedODB を [Get-PnPTenant](/powershell/module/sharepoint-pnp/get-pnptenant) および [Set-PnPTenant]( /powershell/module/sharepoint-pnp/set-pnptenant) から使用して、SharePointおよびOneDrive内のラベル付きアイテムを削除できるようにするレコード管理設定に代わる PowerShell。

### <a name="sensitivity-labels"></a>秘密度ラベル

- 新しいガイダンス:Windows コンピューターに Azure Information Protection (AIP) 統合ラベル付けクライアントを使用している場合に[、Office アプリの AIP アドインに対して組み込みの](sensitivity-labels-aip.md)ラベル付けを選択する理由。 このページには、Office アプリの新しいプライベート プレビューに関する情報が含まれています。
- [自動ラベル付けポリシーの](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)新しい設定:
  - 常に一致する秘密度ラベルの適用をサポートし、組織外から受信した電子メールに暗号化を適用するための電子メールの追加設定。
  - 特定のインスタンス (ユーザー、グループ、サイト) の除外は、既定で **[すべて**] が [**含まれる**] に指定されている場合に、新しい **[除外]** オプションを使用してサポートされます。
- プレビュー段階: モバイル デバイス (iOS と Android) では、最小バージョンがあり、このプレビューにオプトインするときに [共同編集](sensitivity-labels-coauthoring.md) がサポートされます。
- 既定の共有リンクの種類の設定のサポートは、SharePointおよびOneDrive内の個々のドキュメントに拡張されています。 詳細については、新しい記事「[秘密度ラベルを使用して、SharePointおよびOneDriveのサイトとドキュメントの既定の共有リンクの種類を構成]( sensitivity-labels-default-sharing-link.md)する」を参照してください。
- 管理センター Teamsコンテナー ラベル (グループ & サイトのスコープを持つ秘密度ラベル) がサポートされるようになりました。

## <a name="january-2022"></a>2022 年 1 月

### <a name="microsoft-purview-data-lifecycle-management"></a>Microsoft Purview データ ライフサイクル管理

- 以前の Microsoft Information Governance のドキュメントは、Microsoft Purview コンプライアンス ポータル (データ コネクタ、データ ライフサイクル管理、レコード管理) で構成したソリューションに関連する情報をより簡単に見つけられるように大幅に改訂され、再構築されています。 このリビジョンの一環として、ドキュメントでは、データ ライフサイクル管理とレコード管理の保持シナリオの明確な違いを示します。
- 再構築をサポートするために、[データ ライフサイクル管理について説明](data-lifecycle-management.md)します。新機能です。
- [データ ライフサイクル管理の概要](get-started-with-data-lifecycle-management.md) - "概要をリテンション期間に置き換える" 新しい記事では、保持を含むすべてのデータ ライフサイクル管理機能の開始手順について説明します。
- [アイテム保持ポリシーの例外の保持ラベルを作成する](create-retention-labels-data-lifecycle-management.md) - レコード管理ではなく、データ ライフサイクル管理に保持ラベルを使用するための新しい、識別されたシナリオ。
- [アーカイブ メールボックスの詳細については、「アーカイブ メールボックス](archive-mailboxes.md) を有効にする」の記事に記載されていた概念的な情報を含む、再構築をサポートする新規のメールボックスについて説明します。

### <a name="microsoft-priva"></a>Microsoft Priva

- [プライバシー管理が Microsoft Priva になりました](/privacy/priva/priva-overview) 。製品とそのソリューション、Priva Privacy Risk Management、Priva Subject Rights Requests のブランドを変更するように更新されました。

### <a name="sensitivity-labels"></a>秘密度ラベル

- 新しい [ロール グループとロール](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels)のサポートがプレビュー段階になりました。
- 自動ラベル付けポリシーの新しい [監視機能](apply-sensitivity-label-automatically.md#monitoring-your-auto-labeling-policy) 。
- 今すぐロールアウトします。既存のドキュメントの既定のラベルと、Office on the webの理由テキスト。
- バージョン 2202 以降の 7 月Semi-Annual Enterprise チャネルについて発表: Outlookの共同編集と監査。

## <a name="december-2021"></a>2021 年 12 月

### <a name="compliance-and-service-assurance"></a>コンプライアンスとサービスの保証

- [GDPR に基づく Azure、Dynamics 365、Windows侵害通知](/compliance/regulatory/gdpr-breach-notification) - セキュリティやプライバシーに関する通知を受け取るために、お客様が有料サービス (Defender for Cloudなど) を使用する必要がないことを明確にするために更新されました

### <a name="ediscovery"></a>電子情報開示

- [Microsoft Teamsのコンテンツの電子情報開示 (プレミアム) ワークフロー](teams-workflow-in-advanced-ediscovery.md#reference-guide) - 電子情報開示 (プレミアム) でTeamsコンテンツを管理するための新しいダウンロード可能なクイック リファレンス ガイドで更新されました

### <a name="data-lifecycle-management"></a>データ ライフサイクル管理

- [コンプライアンス センターでアーカイブ メールボックスを有効にする](enable-archive-mailboxes.md#run-diagnostics-on-archive-mailboxes) - アーカイブ メールボックスの新しい診断ツールに関するセクションを追加しました
- [ネットワーク アップロードを使用して組織の PST ファイルをMicrosoft 365にインポートする](use-network-upload-to-import-pst-files.md#step-2-upload-your-pst-files-to-microsoft-365) - PST インポートで AzCopy v10 がサポートされるようになりました
- [非アクティブなメールボックスを復元する - 非アクティブなメールボックス](restore-an-inactive-mailbox.md) の LegacyExchangeDN をターゲット メールボックスに最初に追加して非アクティブなメールボックスを復元する手順を変更しました

### <a name="information-protection"></a>情報保護

- [Microsoft Purview を使用して情報保護ソリューションをデプロイする - Microsoft Purview](information-protection-solution.md) Information Protectionを展開するための規範的なロードマップを探しているお客様向けの新しいステップ バイ ステップ ガイダンス

### <a name="retention-and-records-management"></a>保持とレコードの管理

- [アイテム保持ポリシーが有効になるまでの時間に関する](create-retention-policies.md#how-long-it-takes-for-retention-policies-to-take-effect)新しいガイダンス
- 新しいテナント設定のロールアウト: レコードとしてマークされ、ロックされているラベル付きSharePointアイテムのプロパティを編集できないようにするレコード管理設定と、ユーザーがレコードとしてマークされたアイテムのロックを解除できないようにするその他の設定

### <a name="sensitivity-labels"></a>秘密度ラベル

- 必須のラベル付けとPower BIの既定のラベルが一般公開されました (GA)

## <a name="november-2021"></a>2021 年 11 月

### <a name="compliance-manager"></a>コンプライアンス マネージャー

新しいコンテンツ更新プログラムは、 [Microsoft Purview コンプライアンス マネージャーの新機能に](compliance-manager-whats-new.md)関するページで確認できます。

### <a name="device-onboarding"></a>デバイスオンボーディング

デバイスオンボーディングのために次の記事が追加されました。

- [Microsoft 365 への macOS デバイスのオンボードに関する概要 (プレビュー)](device-onboarding-macos-overview.md)
- [Intuneを使用して macOS デバイスを Microsoft Purview ソリューションにオンボードおよびオフボードする (プレビュー)](device-onboarding-offboarding-macos-intune.md)
- [Microsoft Defender for Endpoint のお客様向け Intune を使用したコンプライアンス ソリューションへの macOS デバイスのオンボードとオフボード (プレビュー)](device-onboarding-offboarding-macos-intune-mde.md)
- [JAMF Proを使用して macOS デバイスを Microsoft Purview ソリューションにオンボードおよびオフボードする (プレビュー)](device-onboarding-offboarding-macos-jamfpro.md)
- [Microsoft Defender for Endpoint のお客様向け JAMF Pro を使用したコンプライアンス ソリューションへの macOS デバイスのオンボードとオフボード (プレビュー)](device-onboarding-offboarding-macos-jamfpro-mde.md)

### <a name="ediscovery"></a>電子情報開示

- [電子情報開示で新しいケース形式を使用する (プレミアム)](advanced-ediscovery-new-case-format.md) 新しいケース形式が一般公開にリリースされ、"大きなケース形式" から名前が変更されました

### <a name="retention-and-records-management"></a>保持とレコードの管理
- ロールアウト: SharePointおよびOneDrive内のラベル付きアイテムをユーザーが削除できるかどうかを制御する新しいレコード管理設定。 以前は、コンテンツを保持するように構成され、アイテムをレコードとしてマークしなかった保持ラベルでは、OneDriveでこのアクションが許可されたときに、ユーザーがSharePointでラベル付けされたコンテンツを削除できませんでした。 詳細については、「[SharePointとOneDriveのリテンション期間](retention-policies-sharepoint.md#how-retention-works-for-sharepoint-and-onedrive)のしくみ」を参照してください。

### <a name="sensitive-information-types"></a>機密情報の種類

次の新しい記事を追加しました。

- [完全なデータ一致に基づく機密情報の種類の詳細](sit-learn-about-exact-data-match-based-sits.md)
- [完全なデータ一致に基づく機密情報の種類の使用を開始する](sit-get-started-exact-data-match-based-sits-overview.md)
- [完全なデータ一致に基づく機密情報の種類のソース データをエクスポートする](sit-get-started-exact-data-match-export-data.md)
- [完全なデータ一致に基づく機密情報の種類のスキーマを作成する](sit-get-started-exact-data-match-create-schema.md)
- [機密情報の種類と完全に一致する機密情報のソース テーブルをハッシュしてアップロードする](sit-get-started-exact-data-match-hash-upload.md)
- [機密情報の種類/ルール パッケージと完全に一致するデータを作成する](sit-get-started-exact-data-match-create-rule-package.md)
- [機密情報の種類と完全に一致するデータをテストする](sit-get-started-exact-data-match-test.md)
- [正確なデータ一致スキーマを管理する](sit-use-exact-data-manage-schema.md)
- [機密情報のソース テーブル ファイルを更新する](sit-use-exact-data-refresh-data.md)

### <a name="sensitivity-labels"></a>秘密度ラベル
- [Microsoft Purview Data Map ラベル](/azure/purview/create-sensitivity-label)のスコープ名が "スキーマ化されたデータ資産" になりました。
