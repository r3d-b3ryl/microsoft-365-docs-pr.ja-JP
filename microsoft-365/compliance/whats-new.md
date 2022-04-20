---
title: Microsoft Purview の新機能
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
ms.openlocfilehash: 5c1e48f1cd9d4a73e703e4d5d93d6d1354d57366
ms.sourcegitcommit: e911dd506ea066795e418daf7b84c1e11381a21c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64953719"
---
# <a name="whats-new-in-microsoft-purview"></a>Microsoft Purview の新機能

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

### <a name="changes-to-product-names"></a>製品名の変更

今日の分散型のデータリッチな職場の課題に対応するために、Microsoft [Purview](https://aka.ms/microsoftpurview) は、データ資産全体を理解、管理、保護するのに役立つ包括的なソリューションセットです。 この新しいブランド ファミリは、以前の Microsoft Purview Data Map の機能と、顧客が既に信頼しているMicrosoft 365コンプライアンス ポートフォリオを組み合わせて、組織に統合されたデータ ガバナンスとリスク管理を提供します。

| **以前の名前** | **New Name/新しい名前** | **説明** |
|:----------------|:-------------|:----------------|
| 高度な監査のMicrosoft 365 | Microsoft Purview 監査 (プレミアム) | 監査ソリューションは、組織がセキュリティ イベント、フォレンジック調査、内部調査、コンプライアンス義務に効果的に対応するのに役立つ統合ソリューションを提供します。 詳細については、「[Microsoft Purview Advanced Audit (プレミアム)](advanced-audit.md)」を参照してください。 |
| Microsoft 365コミュニケーション コンプライアンス | Microsoft Purview Communication Compliance | コミュニケーション コンプライアンスは、会社のコミュニケーション チャネルとポリシー違反の迅速な検出、キャプチャ、修復アクションの実行を支援することで、リスクを最小限に抑えるのに役立ちます。 詳細については、「 [Microsoft Purview Communication Compliance](communication-compliance-solution-overview.md)」を参照してください。 |
| Microsoft コンプライアンス マネージャー | Microsoft Purview コンプライアンス マネージャー | コンプライアンス マネージャーは、データ保護リスクのインベントリの作成から、複雑な制御の実装の管理、規制や認証の最新情報の入手、監査人への報告まで、コンプライアンスの過程全体を支援します。 詳細については、 [Microsoft Purview コンプライアンス マネージャーに関する](compliance-manager.md)ページを参照してください。 |
| 顧客キーのMicrosoft 365 | Microsoft Purview カスタマー キー | カスタマー キーは、承認されていないシステムまたは担当者によるデータの表示に対する保護を強化し、Microsoft データ センターでの BitLocker ディスク暗号化を補完します。 詳細については、 [Microsoft Purview カスタマー キーに関するページを](customer-key-overview.md)参照してください。 |
| Office 365 のカスタマー ロックボックス | Microsoft Purview Customer Lockbox | カスタマー ロックボックスを使用すると、Microsoft が明示的な承認なしにサービス操作を行うためにコンテンツにアクセスできなくなります。 Customer Lockbox は、承認された要求のみがコンテンツへのアクセスを許可するように Microsoft が使用する承認ワークフロー プロセスに移行します。 詳細については、「 [Microsoft Purview Customer Lockbox](customer-lockbox-requests.md)」を参照してください。 |
| データ損失防止 | Microsoft Purview データ損失防止 | DLP は、機密データを保護し、ユーザーがデータを持つべきでないユーザーと不適切に共有できないようにすることで、リスクを軽減するのに役立ちます。 詳細については、「 [Microsoft Purview データ損失防止](dlp-learn-about-dlp.md)」を参照してください。 |
| Microsoft 365のダブル キー暗号化 | Microsoft Purview Double Key Encryption | Double Key Encryption (DKE) では、2 つのキーを一緒に使用して、保護されたコンテンツにアクセスします。 Microsoft は 1 つのキーをMicrosoft Azureに格納し、もう一方のキーを保持します。 詳細については、[Microsoft Purview Double Key Encryption](double-key-encryption.md) に関するページを参照してください。 |
| Microsoft 365情報バリア | Microsoft Purview 情報バリア | 情報バリアは、内部情報を保護するために組織内の特定のユーザー間のコミュニケーションとコラボレーションを制限するソリューションです。 詳細については、 [Microsoft Purview 情報バリアに関する](information-barriers-solution-overview.md)ページを参照してください。 |
| Microsoft Information Protection | Microsoft Purview Information Protection | 情報保護は、機密情報がどこに存在するか、移動する場所を問わず、検出、分類、および保護するのに役立ちます。 詳細については、「[Microsoft Purview Information Protection](information-protection.md)」を参照してください。 |
| Microsoft 情報ガバナンス | Microsoft Purview データ ライフサイクル管理 | データ ライフサイクル管理では、保持および削除する必要があるコンテンツを保持するためのツールと機能が提供されます。 詳細については、「 [Microsoft Purview データ ライフサイクル管理](data-lifecycle-management.md)」を参照してください。 |
| Microsoft 365 インサイダー リスク管理 | Microsoft Purview Insider リスク管理 | インサイダー リスク管理では、幅広いサービスとサードパーティの指標を使用して、リスクの高いユーザー アクティビティをすばやく特定、トリアージ、および対処するのに役立ちます。 詳細については、「 [Microsoft Purview Insider Risk Management](insider-risk-management.md)」を参照してください。 |
| Office 365 Message Encryption | Microsoft Purview メッセージ暗号化 | Message Encryption を使用すると、組織は組織内外のユーザー間で暗号化された電子メール メッセージを送受信できます。 詳細については、「 [Microsoft Purview メッセージ暗号化](ome.md)」を参照してください。 |
| Microsoft 365の特権アクセス管理 | Microsoft Purview Privileged Access Management | Privileged Access Management は、組織を侵害から保護し、機密データへの永続的なアクセスや重要な構成設定へのアクセスを制限することで、コンプライアンスのベスト プラクティスを満たすのに役立ちます。 詳細については、「 [Microsoft Purview Privileged Access Management](privileged-access-management-solution-overview.md)」を参照してください。 |
| Microsoft データ コネクタ | Microsoft Purview データ コネクタ | Microsoft 365管理者は、データ コネクタを使用して、Microsoft 以外のサード パーティのデータをソーシャル メディア プラットフォーム、インスタント メッセージング プラットフォーム、ドキュメント コラボレーション プラットフォームから、Microsoft 365組織内のメールボックスにインポートおよびアーカイブできます。 詳細については、 [Microsoft Purview データ コネクタに関するページを](compliance-extensibility.md)参照してください。 |
| Microsoft 365 Advanced eDiscovery | Microsoft Purview 電子情報開示プレミアム | 電子情報開示 (eDiscovery) とは、訴訟で証拠として使用できる電子的情報を特定および提供するプロセスです。 詳細については、「[Microsoft Purview 電子情報開示プレミアム](overview-ediscovery-20.md)」を参照してください。 |
| Microsoft 365 コンプライアンス センター | Microsoft Purview コンプライアンス ポータル | Microsoft 365 E5 Compliance スイート内のソリューションとソリューション カタログにアクセスするための管理ポータル。 詳細については、 [Microsoft Purview コンプライアンス ポータル](microsoft-365-compliance-center.md)を参照してください。 |

## <a name="february-2022"></a>2022 年 2 月

### <a name="ediscovery"></a>電子情報開示

- [Advanced eDiscoveryでカストディアン通信テンプレートを管理](advanced-ediscovery-communications-library.md)する - 電子情報開示マネージャーは、組織内の任意のAdvanced eDiscoveryケースで使用できるカストディアン通信テンプレートを作成できるようになりました。
- [Advanced eDiscoveryで発行担当者を管理](advanced-ediscovery-issuing-officers.md)する - 電子情報開示マネージャーは、組織内の任意のAdvanced eDiscoveryケースでカストディアン通信に割り当てることができる発行担当者の一覧を追加できます。

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
- 現在のチャネル (プレビュー) の既存のドキュメントの既定のラベルと、Office on the webの理由テキストをロールアウトします。
- バージョン 2202 以降の 7 月Semi-Annual Enterprise チャネルについて発表: Outlookの共同編集と監査。

## <a name="december-2021"></a>2021 年 12 月

### <a name="compliance-and-service-assurance"></a>コンプライアンスとサービスの保証

- [GDPR に基づく Azure、Dynamics 365、Windows侵害通知](/compliance/regulatory/gdpr-breach-notification) - セキュリティやプライバシーに関する通知を受け取るために、お客様が有料サービス (Defender for Cloudなど) を使用する必要がないことを明確にするために更新されました

### <a name="ediscovery"></a>電子情報開示

- [Microsoft TeamsのコンテンツのAdvanced eDiscoveryワークフロー - Advanced eDiscovery](teams-workflow-in-advanced-ediscovery.md#reference-guide)でコンテンツを管理するための新しいダウンロード可能なクイック リファレンス ガイドで更新Teams

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

- [新しいケース形式Advanced eDiscovery](advanced-ediscovery-new-case-format.md)一般公開にリリースされ、"大きなケース形式" から名前が変更された新しいケース形式を使用する

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

## <a name="october-2021"></a>2021 年 10 月

### <a name="app-governance"></a>アプリ ガバナンス

- [Defender for Cloud Apps 用アプリ ガバナンス アドオンが一般公開されました](/cloud-app-security/app-governance-manage-app-governance)。 アプリ ガバナンスのドキュメントは、Defender for Cloud Apps のドキュメントに参加するように移動しました。

### <a name="compliance--service-assurance"></a>コンプライアンス&サービスアシュアランス

- [サービスアシュアランス](/compliance) - 認定および適用性に関する声明のコンテンツ更新プログラムを四半期ごとに確認する) データセンター資産管理
  - データセンターのアーキテクチャとインフラストラクチャ
  - データセンターのビジネス継続性とディザスター リカバリー
  - データセンターの環境保護
  - データセンターの物理アクセス セキュリティ
  - Microsoft 365 SDL コンプライアンス プログラム
  - Microsoft 365 サービス エンジニアのアクセスの制御
  - MS Cloud のリスク評価ガイド

### <a name="data-loss-prevention"></a>データ損失防止

- MacOS のサポートと高度な分類用に[更新された Microsoft Purview データ損失防止について説明](endpoint-dlp-learn-about.md)します。は、サポートされているすべてのファイルの種類のアクティビティを監査するカスタム DLP ポリシーを作成するために更新されました。
- [Microsoft 365 エンドポイントのデータ損失防止に関する概要](endpoint-dlp-getting-started.md)は、macOS のサポートと高度な分類用に更新されました。
- macOS のサポートと高度な分類のために[、エンドポイントデータ損失防止の使用](endpoint-dlp-using.md)が更新されました。
- macOS のサポートと高度な分類について[、データ損失防止ポリシーのヒントリファレンス](dlp-policy-tips-reference.md)が更新されました。
- [macOS デバイスをMicrosoft 365 (プレビュー) にオンボード](device-onboarding-macos-overview.md)すると、macOS のサポートと高度な分類が更新されました。
- デバイスのオンボード用に次の新しいページを追加しました。
  - [Intuneを使用して macOS デバイスを Microsoft Purview ソリューションにオンボードおよびオフボードする (プレビュー)](device-onboarding-offboarding-macos-intune.md)
  - [Microsoft Defender for Endpoint のお客様向け Intune を使用したコンプライアンス ソリューションへの macOS デバイスのオンボードとオフボード (プレビュー)](device-onboarding-offboarding-macos-intune-mde.md)
  - [JAMF Proを使用して macOS デバイスを Microsoft Purview ソリューションにオンボードおよびオフボードする (プレビュー)](device-onboarding-offboarding-macos-jamfpro.md)
  - [Microsoft Defender for Endpoint のお客様向け JAMF Pro を使用したコンプライアンス ソリューションへの macOS デバイスのオンボードとオフボード (プレビュー)](device-onboarding-offboarding-macos-jamfpro-mde.md)

### <a name="ediscovery"></a>電子情報開示

- [クラウド添付ファイルの](advanced-ediscovery-cloud-attachments.md)最新バージョンを収集するだけでなく、Advanced eDiscoveryでクラウド添付ファイルを収集したり、メール メッセージやチャット会話で共有されたバージョンを収集Teamsできます。共有バージョンの収集は、クラウド添付ファイルに保持ラベルを自動的に適用する新機能によって可能になります。
- [検索のためにSharePoint](advanced-ediscovery-historical-versions.md) サイトに格納されているすべてのバージョンのドキュメントにインデックスを付ける新しい機能Advanced eDiscovery履歴バージョンを設定します。つまり、コレクション クエリに一致するコンテンツを含むドキュメント バージョンが検索結果に返されます。

### <a name="encryption"></a>暗号化

- [1 対 1 のMicrosoft Teams呼び出し (パブリック プレビュー) パブリック プレビュー](/microsoftteams/teams-end-to-end-encryption)の新しいコンテンツには、エンド ツー エンドの暗号化を使用します。

### <a name="data-lifecycle-management"></a>データ ライフサイクル管理

- [エピック EHR 監査データをインポートするコネクタを設定](import-epic-data.md) する新しいコネクタを使用すると、エピック電子医療記録システムからデータをインポートして、インサイダー リスク管理の新しい一般的な患者データの誤用シナリオをサポートできます。
- [医療 EHR 監査データをインポートするコネクタを設定](import-healthcare-data.md) する新しいコネクタを使用すると、電子医療記録システムからデータをインポートして、インサイダー リスク管理の新しい一般的な患者データ誤用シナリオをサポートできます。

### <a name="retention-and-records-management"></a>保持とレコードの管理
- [アダプティブ ポリシー スコープは、](retention.md#adaptive-or-static-policy-scopes-for-retention) アイテム保持ポリシーとアイテム保持ラベル ポリシーのプレビューでリリースされます。
- [秘密度ラベルに基づいて保持ラベルを自動的に適用](apply-retention-labels-automatically.md#identify-files-and-emails-that-have-a-sensitivity-label)できるようになりました。
- ファイル プランに新しい [インポート プロセス](file-plan-manager.md#import-retention-labels-into-your-file-plan)があります。
- [アイテム保持ポリシーとアイテム保持ラベル ポリシーの一般的な設定: アイテム保持ポリシーとアイテム保持ラベル ポリシー](retention-settings.md)の両方でアダプティブ スコープとその他の設定を構成する方法の詳細については、新しい記事を参照してください。

### <a name="sensitive-information-types"></a>機密情報の種類

- [名前付きエンティティの新しいコンテンツの名前付きエンティティ (プレビュー) について説明](named-entities-learn.md) します。
- [データ損失防止ポリシーで名前付きエンティティを使用する (プレビュー)](named-entities-use.md) 名前付きエンティティの使用に関する新しいコンテンツ。

### <a name="sensitivity-labels"></a>秘密度ラベル

- [既定のラベルと既定のポリシー](mip-easy-trials.md) は、対象となる顧客にロールアウトされます。

## <a name="september-2021"></a>2021 年 9 月

### <a name="app-governance"></a>アプリ ガバナンス

- [合理化されたアプリ ガバナンスの開始情報](app-governance-get-started.md) によってワークフローが変更され、パブリック プレビューサインアップへの新しいリンクが追加されました
- [新しい検出アラート定義](app-governance-anomaly-detection-alerts.md#app-made-high-volume-of-importance-mail-read-and-created-inbox-rule) が追加されました (更新されました。コレクション アラートの新しい定義が追加されました)

### <a name="auditing"></a>監査

- 組織の監査状態に対する変更自体の監査方法に関する新しいセクションを追加して、監査の[オンとオフを切り替](turn-audit-log-search-on-or-off.md)えます。つまり、監査レコードは、監査がオンまたはオフになっているときにログに記録されます。Exchange管理者監査ログでこれらの監査レコードを検索できます。

### <a name="communication-compliance"></a>コミュニケーション コンプライアンス

- [SIEM ソリューションとの通信コンプライアンス](communication-compliance-siem.md) の統合に関する SIEM ソリューションガイダンスとの通信コンプライアンス)

### <a name="compliance-offerings"></a>コンプライアンス認証

- [多層クラウド セキュリティ (MTCS)](/compliance/regulatory/offering-mtcs-singapore) Dynamics 365 カバレッジのシンガポールの標準更新プログラム
- [支払いカード業界 (PCI)](/compliance/regulatory/offering-pci-dss)SharePoint Online カバレッジの Data Security Standard (DSS) 更新プログラム
- [米国セクション 508](/compliance/regulatory/offering-section-508-vpats) の新しいクライアント ソフトウェア ガイダンス
- [Web コンテンツ アクセシビリティ ガイドライン](/compliance/regulatory/offering-wcag-2-1) の新しいクライアント ソフトウェア ガイダンス

### <a name="compliance--service-assurance"></a>コンプライアンス&サービスアシュアランス

- [サービス アシュアランス](/compliance/) は、認定と適用性に関する声明のコンテンツ更新プログラムを四半期ごとに確認します
  - データを有するデバイスの破棄
  - DDOS 攻撃

### <a name="data-connectors"></a>データ コネクタ

- CellTrust および 17a-4 LLC からMicrosoft 365 データ コネクタに[サード パーティのデータ](archiving-third-party-data.md#data-connectors-in-the-us-government-cloud) GCCをアーカイブする
- [YouTube データをアーカイブするためのコネクタを設定](archive-youtube-data.md) すると、パブリック プレビューでこの機能に関する新しいガイダンスが提供されます。

### <a name="ediscovery"></a>電子情報開示

- [KQL エディターを使用して](ediscovery-kql-editor.md)、コンテンツ検索、Core 電子情報開示、Advanced eDiscoveryで検索クエリを作成する新しい方法の検索クエリパブリック プレビューを作成します。KQL エディターは、サポートされている検索可能なプロパティと条件のオートコンプリートを提供し、標準プロパティと条件でサポートされている値の一覧を表示します。KQL エディターでは、検索クエリで発生する可能性のあるエラーの修正に対するエラー検出と提案も提供されます

### <a name="information-barriers"></a>情報バリア

- [情報バリア モードの新](information-barriers-policies.md#step-6-information-barriers-modes)しいプレビュー機能を使用した概要
- [情報バリア モードの](/microsoftteams/information-barriers-in-teams)新しいプレビュー機能Microsoft Teams備えた情報バリア
- [情報バリア モードの](/onedrive/information-barriers)新しいプレビュー機能OneDrive備えた情報バリア
- [情報バリア モードのSharePoint Online](/sharepoint/information-barriers) 新しいプレビュー機能を備えた情報バリア

### <a name="insider-risk-management"></a>インサイダー リスクの管理

- 推奨されるアクションを開始するための[インサイダー リスク管理](insider-risk-management-configure.md#recommended-actions-preview)の新しいプレビュー機能を使用した概要
- [インサイダー リスク アクティビティを調査](insider-risk-management-activities.md#get-help-managing-your-insider-risk-alert-queue) する新しい「インサイダー リスク アラート キューの管理に関するヘルプを表示する」ガイダンス セクション
- [インサイダー リスク管理設定を使用した概要](insider-risk-management-settings.md#admin-notifications)新しい管理者通知設定プレビュー機能

### <a name="retention-and-records-management"></a>保持とレコードの管理
- [多段階の廃棄レビュー](disposition.md) が一般公開 (GA) され、新しい [監査イベントが](search-the-audit-log-in-security-and-compliance.md#disposition-review-activities)追加されました。 多段階の廃棄レビューを使用すると、保持ラベルに対して最大 5 つの連続する廃棄レビューステージを指定でき、レビュー担当者は他のユーザーをその廃棄レビュー ステージに追加できます。 メールの通知とアラームをカスタマイズすることもできます。
- [Teamsアイテム保持ポリシー](create-retention-policies.md#retention-policy-for-teams-locations)のプライベート チャネルが一般公開されました (GA)。

### <a name="sensitivity-labels"></a>秘密度ラベル
- [共同編集と自動保存](sensitivity-labels-coauthoring.md)は、Windows (Current Channel または Monthly Enterprise Channel から 2107 の最小バージョン) と macOS (最小バージョン 16.51) で一般公開されるようになりました。
- 組み込みのラベルを使用するOffice アプリのロールアウト: 既定のラベル設定では、既存のドキュメントと新しいドキュメントがサポートされるようになりました。 この動作の変更は、Azure Information Protection の統合ラベル付けクライアントとのパリティを提供します。 アプリごとのロールアウトと最小バージョンの詳細については、Word、Excel、PowerPoint の [機能表](sensitivity-labels-office-apps.md#sensitivity-label-capabilities-in-word-excel-and-powerpoint) を参照してください。
- コンテナー ラベルでは、 [PowerShell の詳細設定を使用して、既定の共有リンク設定が](sensitivity-labels-teams-groups-sites.md#configure-settings-for-the-default-sharing-link-type-for-a-site-by-using-powershell-advanced-settings)サポートされるようになりました。
- 組み込みのラベル付けでサポートされている最小バージョンを一覧表示する[機能テーブル](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)には、現在のチャネル、月次Enterprise チャネル、およびSemi-Annual Enterprise チャネルのバージョンが含まれるようになりました。
