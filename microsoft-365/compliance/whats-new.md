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
description: コンプライアンス センターへの新しいソリューションの追加、フィードバックに基づく既存の機能の更新、最新および更新されたドキュメントの展開など、Microsoft 365 は変化し続けるコンプライアンス環境を常に改善するのに役立ちます。 今月の予定を確認します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3688ee7390b7cadf701e8dbefd8b12c82cf6d89c
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751594"
---
# <a name="whats-new-in-microsoft-365-compliance"></a>Microsoft 365 コンプライアンスの新機能

[Microsoft 365](microsoft-365-compliance-center.md)コンプライアンス センターへの新しいソリューションの追加、フィードバックに基づく既存の機能の更新、最新および更新されたドキュメントの展開など、Microsoft 365 は変化し続けるコンプライアンスの状況を常に改善するのに役立ちます。 Microsoft 365 コンプライアンスの新機能については、以下をご覧ください。 

> [!NOTE]
> 一部のコンプライアンス機能は、お客様に対して異なる速度で展開されます。 If you aren't seeing a feature yet, try adding yourself to [targeted release](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365).


> [!TIP]
> 他の管理センターで何が起こっていますか? 次の記事を参照してください。<br>[Microsoft 365 管理センターの新機能](https://docs.microsoft.com/office365/admin/whats-new-in-preview)<br>[SharePoint 管理センターの新機能](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center)<br>[Microsoft 365 Defender の新機能](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)<br><br>
また [、Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/roadmap) ロードマップにアクセスして、起動、展開中、開発中、キャンセル済み、以前にリリースされた Microsoft 365 の機能について説明します。

## <a name="november--december-2020"></a>2020 年 11 月 & 12 月
新しい機能や更新された機能をプレビュー状態でリリースして、その使い方を確認し、一般提供にリリースする前に改良を図る必要があります。 お客様からのフィードバックはプレビュー中 (およびそれ以降) に不可欠なので、コンプライアンス センターの右下にあるフィードバック カードを開いてご意見をお聞かせください。

![feedback](../media/Feedback_card_MCC.JPG)

### <a name="spotlight-endpoint-data-loss-prevention-dlp-released"></a>スポットライト: エンドポイント データ損失防止 (DLP) のリリース

[エンドポイント DLP は](endpoint-dlp-learn-about.md) 、DLP のアクティビティ監視および保護機能を Windows 10 デバイス上の機密情報に拡張します。 デバイスが[](dlp-configure-endpoints.md)Microsoft 365 コンプライアンス センターにオンボードされた後、DLP ポリシーを設定して、それらのデバイスの機密情報を保護できます。

### <a name="advanced-ediscovery"></a>高度な電子情報開示

電子情報開示ワークフローで暗号化されたコンテンツを簡単に管理するために、Microsoft 365 電子情報開示ツールには、[](ediscovery-decryption.md)電子メール メッセージに添付され、Exchange で送信される暗号化されたファイルの暗号化解除が組み込まれています。 さらに、SharePoint と OneDrive に保存されている暗号化されたドキュメントは、Advanced eDiscovery で復号化されます。

### <a name="compliance-manager"></a>コンプライアンス マネージャー

- [Microsoft 365 Government サブスクリプションのサポート](compliance-manager.md)。 コンプライアンス マネージャーは、米国政府機関向けコミュニティ (GCC) の中および高のお客様が利用できます。
- [コンプライアンス マネージャー用の Microsoft Compliance Configuration Analyzer](compliance-manager-mcca.md)。 組織の現在の構成をスキャンし、Microsoft 365 の推奨ベスト プラクティスに対して検証することで、コンプライアンス マネージャーの使用を開始するのに役立つ新しい PowerShell ベースのツール。
- [新しいテンプレート](compliance-manager-templates-list.md)。 56 の新しいテンプレートが追加され、コンプライアンス マネージャー テンプレートの合計は 230 を超えました。

### <a name="data-connectors"></a>データ コネクタ

[プレビューで 5 つの新しい Globanet コネクタ](archiving-third-party-data.md#third-party-data-connectors)。 新しいコネクタには、Reuters Dealing、Reuters FX、CellTrust、XIP、汎用 MS SQL データベース データが含まれます。

### <a name="retention-labels-disposition-review"></a>保持ラベル (廃棄レビュー)

廃棄レビュー中にアイテムを表示するには、コンテンツ エクスプローラーのコンテンツ ビューアーとコンテンツ エクスプローラーのリスト ビューアーの役割グループのメンバーである [必要があります](disposition.md#permissions-for-disposition)。 アイテムの確認は必須ですが、これらの役割グループは廃棄レビューを完了するために必要ありません。

### <a name="sensitivity-labels"></a>秘密度ラベル

- [(プレビュー) SharePoint サイトの外部共有設定](sensitivity-labels-teams-groups-sites.md#how-to-configure-groups-and-site-settings)。 グループとサイトに使用するラベルを作成する場合、ラベルが適用されている SharePoint サイトの外部共有を制御するオプションが表示されます。 組織内のすべてのユーザー、新規および既存のゲスト、既存のゲストのみ、または組織内のユーザーに対して共有を許可できます。 ラベルが適用されると、ラベル設定は SharePoint 管理センターで構成された外部共有設定 [に置き換わるものになります](https://docs.microsoft.com/sharepoint/change-external-sharing-site)。
- [ラベル付きドキュメントからラベルと暗号化を削除します](sensitivity-labels-sharepoint-onedrive-files.md#remove-encryption-for-a-labeled-document)。 ラベルと、ラベルが適用する暗号化の両方を SharePoint のラベル付きドキュメントから削除するために、グローバル管理者と SharePoint 管理者は新しいコマンドレットを実行 `Unlock-SPOSensitivityLabelEncryptedFile` できます。 このコマンドレットは、管理者がサイトまたはファイルに対するアクセス許可を持たなかったり、Azure Rights Management サービスが利用できない場合でも実行されます。

## <a name="october-2020"></a>2020 年 10 月

### <a name="advanced-ediscovery"></a>高度な電子情報開示

[CJK 言語サポート](ediscovery-cjk-support.md)。 Advanced eDiscovery では、CJK 言語と総称される 2 バイト文字セット言語 (簡体字中国語、繁体字中国語、日本語、韓国語を含む) がサポートされます。 これらは、いくつかの高度なレビュー セット シナリオで使用できます。

### <a name="sensitivity-labels"></a>秘密度ラベル

- [ラベルの範囲](sensitivity-labels.md#label-scopes)です。 ラベルを作成するときに、ラベルの範囲を定義する新しいオプションが表示されます。 このオプションでは、ファイルとメール、コンテナー (SharePoint サイトや Teams など)、または両方のラベルを構成できます。
- [動的なコンテンツのマーキング](sensitivity-labels-office-apps.md#dynamic-markings-with-variables)。 機度ラベルのコンテンツ マーキングを構成する際に、ヘッダー、フッター、透かしなどの動的変数と、ヘッダー、フッター、透かしのテキスト文字列を `${Item.Label}` `${Item.Location}` 使用できます。

## <a name="september-2020"></a>2020 年 9 月

### <a name="spotlight-compliance-manager"></a>スポットライト: コンプライアンス マネージャー

今年 Ignite で発表されたコンプライアンス スコアは、コンプライアンス マネージャーとして [再ブランドされています](compliance-manager.md)。 このリリースでは、Service Trust Portal のコンプライアンス マネージャーの以前のホームからの移行が完了し、Microsoft 365 コンプライアンス センターにエンドツーエンドのコンプライアンス管理ソリューションが導入されています。

以下のビデオを見て、コンプライアンス マネージャーが組織でコンプライアンスを管理する方法を簡素化する方法について説明します。
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4FGYZ]

### <a name="advanced-audit"></a>高度な監査

- 監査ログの新しい 10 年間の保持は、長期の調査をサポートし、規制、法律、および内部の義務に対応するのに役立ちます。
- [3 つの新しい重要なイベント](advanced-audit.md#access-to-crucial-events-for-investigations)。 次の新しいイベントは、侵害の可能性を調査し、侵害の範囲を決定するのに役立ちます:Send、SearchQueryInitiatedExchange、SearchQueryInitiatedSharePoint。

### <a name="communication-compliance"></a>通信コンプライアンス

- [役割グループを更新しました](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance)。 通信コンプライアンス役割グループは、インサイダー リスク管理ソリューションで使用可能な役割グループ構造と一致する必要があります。
- [レポート ダッシュボード](communication-compliance-feature-reference.md#reports-preview)。 すべての通信コンプライアンス レポートを表示する中心的な場所。 レポート ウィジェットは、通信コンプライアンス アクティビティの状態を全体的に評価するために最も一般的に必要な分析情報のクイック ビューを提供します。
- [Power Automate フロー](communication-compliance-feature-reference.md#power-automate-flows-preview)。 フローを設定して、アラートとユーザーのタスクを自動化し、ユーザーがアラートをトリガーした場合にマネージャーに通知します。
- ['分類の改善' 修復アクション](communication-compliance-investigate-remediate.md#step-3-decide-on-a-remediation-action)。 トレーニング可能な分類子に一致するアイテムを含むアラートは、組織内で誤検知を最小限に抑えるためにフィードバックを利用できる場合があります。 分類 **の改善オプション** を使用すると、検出されたアイテムが関連する通信コンプライアンス ポリシーで構成されている分類子と一致するかどうかをフィードバックできます。 他の分類子を提案してアイテムに関連付け、今後のアラートの一致精度を向上させる場合があります。

### <a name="data-connectors"></a>データ コネクタ

- [新しいサードパーティのデータ コネクタ](archiving-third-party-data.md#third-party-data-connectors)。 Globanet から 14 個、Telemessage から 8 個を含む 25 個の新しいデータ コネクタ。
- [物理バグコネクタ](import-physical-badging-data.md)。 従業員の生の物理的なアクセス イベントや、組織の不良システムによって生成された物理的なアクセス アラームなど、物理的な不良データをインポートします。 たとえば、建物、サーバー ルーム、またはデータ センターへのエントリが含まれます。 インサイダー リスク管理ソリューションは、物理的な不正なデータを使用して、組織内の悪意のあるアクティビティやデータの盗難から組織を保護できます。

### <a name="insider-risk-management"></a>インサイダー リスクの管理

- [Microsoft Teams の統合](insider-risk-management-settings.md#microsoft-teams-preview)。 インサイダー リスク設定で Teams の統合が有効になっている場合は、個々のケースに関連するデータの安全な共有と保存、アナリストや調査担当者からの対応活動の追跡と確認などのタスクについて、Teams の他の関係者と調整して共同作業を行うことができます。
- [Power Automate フロー](insider-risk-management-settings.md#power-automate-flows-preview)。 ユーザー、アラート、ケース情報の取得、関係者や他のアプリと共有するケース情報の取得、ケース ノートへの投稿などのアクションの自動化など、ケースとユーザーの重要なタスクを自動化するためのフローを設定します。
- [アクティビティ エクスプローラー](insider-risk-management-alerts.md#activity-explorer-preview)。 アラートを確認するときに利用できるアクティビティ エクスプローラーは、調査担当者やアナリストに、各アラートを詳細に掘り下ろす包括的な分析ツールを提供します。 検出された危険なアクティビティのタイムラインをすばやく確認し、アラートに関連付けられているすべてのリスク アクティビティを特定してフィルター処理します。

### <a name="retention-policies-and-retention-labels"></a>アイテム保持ポリシーと保持ラベル

- [サービスのYammer。](retention-policies-yammer.md) アイテム保持ポリシーを使用して、コミュニティ メッセージやプライベート メッセージYammer保持および削除できます。
- [Teams 会議のレコーディングにラベルを適用します](apply-retention-labels-automatically.md#microsoft-teams-meeting-recordings)。 自動ラベル付けポリシーを作成する場合は、キーワード クエリ エディターを使用して、ユーザーの OneDrive アカウントまたは SharePoint に保存されている Teams 会議のレコーディングを識別します。

### <a name="records-management"></a>レコード管理

[規制記録のサポート](declare-records.md#how-to-display-the-option-to-mark-content-as-a-regulatory-record)。 ラベルを規制レコードとして分類すると、ラベルが適用されるコンテンツに対する制限が増加し、ラベル自体に対して使用可能な管理アクションが制限されます。 たとえば、コンテンツに適用した後は、グローバル管理者でなくても誰もラベルを削除できます。 [規制レコード](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked) に対して許可およびブロックするアクションについて詳しくは、以下を参照してください。

### <a name="sensitivity-labels"></a>秘密度ラベル

[米国政府機関のお客様向けサポート](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description)。 これで、GCC、GCC High、DoD の顧客に対して、Azure Information Protection 統合ラベル付けクライアントとスキャナーのラベル付けだけがサポートされます。

### <a name="trainable-classifiers"></a>トレーニング可能な分類子

新しい再トレーニング機能とフィードバック機能は、精度を向上し、すべてのカスタム分類子といくつかの事前トレーニング済み分類子に対する誤検知の一致を最小限に抑えるのに役立ちます。 このフローを使用すると、アイテムが特定の分類子と一致するかどうかに関するフィードバックを提供し、他の分類子にアイテムに関連付け、分類子を再トレーニングして一致精度を調整および向上することができます。

この新機能は、次の機能に含まれています。

> [!NOTE]
> すべての機能について、少なくとも 30 件のフィードバック応答を提供する場合は、レビュー可能な再トレーニングされたバージョンの分類子が作成されます。 改善された場合は、分類子を再発行できます。

- [トレーニング可能な分類子](classifier-learn-about.md#retraining-classifiers)。 発行された分類子の精度を向上させるために、検出されたアイテムが分類子と一致するかどうかに関するフィードバックを提供できます。
- [通信コンプライアンス](classifier-how-to-retrain-comms-compliance.md)。 新しい **分類の改善** の修復アクションを使用すると、通信コンプライアンスアラートのアイテムが通信コンプライアンス ポリシーで構成された分類子と一致するかどうかをフィードバックできます。
- [コンテンツ エクスプローラー](classifier-how-to-retrain-content-explorer.md)。 保持の自動ラベル付けポリシーを設定して、トレーニング可能な分類子に一致するメール メッセージにラベルを自動的に適用する場合は、コンテンツ エクスプローラーを使用してラベル付けされたアイテムを確認し、アイテムが分類子と一致するかどうかをフィードバックできます。

## <a name="august-2020"></a>2020 年 8 月

### <a name="spotlight-insider-risk-and-communication-compliance-updates"></a>スポットライト: インサイダー リスクと通信コンプライアンスの更新

いくつかの新機能と強化された機能が、今月パブリック プレビューにヒットしました。

**インサイダー リスクの管理**

- 6 つの新しいポリシー [テンプレートを確認してください](insider-risk-management-policies.md#policy-templates)。
    - 優先度の高いユーザーによるデータ漏洩
    - 不満を持つユーザーによるデータ漏洩
    - 一般的なセキュリティ ポリシー違反
    - 権限を持つユーザーによるセキュリティ ポリシー違反
    - 優先度ユーザーによるセキュリティ ポリシー違反
    - 不満を持つユーザーによるセキュリティ ポリシー違反

- Microsoft [Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) との統合により、新しいセキュリティ違反ポリシー テンプレートから作成されたポリシーによって検出されたアクティビティについて、Microsoft Defender for Endpoint のアラートをインポートしてフィルター処理できます。 また、関連するインサイ[](insider-risk-management-settings.md#microsoft-defender-for-endpoint-preview)ダー リスク設定では、Microsoft Defender for Endpoint の警告トリアージの状態に基づいて、インサイダー リスク管理にセキュリティの警告をインポートできます。

    > [!NOTE]
    > Microsoft Defender for Endpoint 統合 (新しいセキュリティ ポリシー違反テンプレートを含む) を利用するには、組織で Microsoft Defender for Endpoint を構成する必要があります。 また、Microsoft Defender for Endpoint の高度な機能を構成して、インサイダー リスク管理統合のために Microsoft Defender for Endpoint を有効 [にする必要があります](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)。
 
- ポリシーを作成するときにインジケーターのしきい [値をカスタマイズします](insider-risk-management-policies.md#create-a-new-policy)。
- 優先度の [ユーザー グループ](insider-risk-management-settings.md#priority-user-groups-preview) を設定して、自分の位置、機密情報へのアクセスレベル、リスク履歴などの要因に基づいて、アクティビティの詳細な検査が必要な組織内のユーザーを定義します。
- 365 Officeアクティビティ API を使用して、[](insider-risk-management-settings.md#export-alerts-preview)インサイダー リスク アラートの詳細を、組織がインサイダー リスク データの管理または集計に使用する可能性がある他のアプリケーションにエクスポートします。
- 新 [しいドメイン設定は](insider-risk-management-settings.md#domains-preview) 、特定のドメインでのアクティビティのリスク レベルを定義および制御するのに役立ちます。

**通信コンプライアンス**

- アラート [でメッセージを](communication-compliance-investigate-remediate.md#step-3-decide-on-a-remediation-action)確認するときに、Microsoft Teams チャネル、1 対 1、およびグループ チャットで不適切なメッセージを削除できます。 削除されたメッセージとコンテンツは、機密性の高いコンテンツのために削除されたというポリシー ヒントに置き換えられる。
- 新 [しい通信役割](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance) (これらは、9 月にリリースされる新しい通信コンプライアンス役割グループにも含まれます)。
- プライバシーと通知テンプレートの設定 [を含む](communication-compliance-feature-reference.md#privacy-preview) 新しい通信コンプライアンス [設定エクスペリエンス](communication-compliance-feature-reference.md#notice-templates)。
- 成人 [向け、](communication-compliance-feature-reference.md#classifiers) 不器用、不作作な画像の検出に役立つ新しい分類子。
- アラート内のメッセージを確認するときに表示される新しい[](communication-compliance-investigate-remediate.md#step-2-examine-the-message-details)"パターン検出" 通知により、ユーザーが同じ動作のインスタンスを再発生した場合を確認できます。

### <a name="sensitivity-labels"></a>秘密度ラベル

- 米国政府テナント (GCC、GCC-H、DoD) 向けの場合、秘密度ラベルが現在サポートされているのは、Azure Information Protection の統合ラベル付けクライアントおよびスキャナーのみです。 詳細については、[Azure Information Protection Premium の米国政府機関向けのサービスの説明](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description)を参照してください。
- セキュリティ/ [コンプライアンス センターの PowerShell &使用](create-sensitivity-labels.md#use-powershell-for-sensitivity-labels-and-their-policies) して、ラベル付け管理センターに表示される設定を作成して構成できます。 つまり、ラベル付け管理センターでは使用できない設定に PowerShell を使用する以外に、ラベル付けラベルと感度ラベル ポリシーの作成と保守を完全にスクリプト化できます。

### <a name="records-management-content-overhaul"></a>レコード管理: コンテンツのオーバーホール

展開手順、コンテンツをレコードとしてマーク、およびレコードのバージョン管理に関する新しいドキュメント:

- [レコード管理の使用を開始する](get-started-with-records-management.md)
- [保持ラベルを使用してレコードを宣言する](declare-records.md)
- [SharePoint または OneDrive に保存されているレコードを更新するためにレコードのバージョン管理を使用する](record-versioning.md)

### <a name="retention-labels--policies"></a>保持ラベルと&ポリシー

保持関連の管理者アクティビティが記録され、監査ログで確認できます。 完全なリストについては、「[アイテム保持ポリシーと保持ラベルのアクティビティ](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities)」を参照してください。

### <a name="advanced-ediscovery"></a>高度な電子情報開示

- コレクション [をレビュー セットに](add-data-to-review-set.md#define-options-to-scope-your-collection-for-review)追加するときに、モダン添付ファイル (「クラウド添付ファイル」とも呼ばれる) と SharePoint ドキュメント バージョンを含めできます。
- 新 [しい直接ダウンロードエクスポート エクスペリエンス](export-documents-from-review-set.md)により、ケースコンテンツをダウンロードするために Azure Storage Explorer を使用する必要がなくなります。


## <a name="july-2020"></a>2020 年7 月

### <a name="spotlight-on-help-docs"></a>ヘルプ ドキュメントのスポットライト

組織の機密データの保護と管理に使用されるコンプライアンス ソリューションを理解するために、2 つの新しいランディング ページを作成し、関連ドキュメントへのリンクを含め、ソリューションがそれらの目標を達成する方法の概要を示しました。

[Microsoft 365 の Microsoft Information Protection](information-protection.md)<br>
[Microsoft 365 の Microsoft 情報ガバナンス](manage-Information-governance.md)

### <a name="advanced-ediscovery-add-non-custodial-data-sources-to-your-cases"></a>Advanced eDiscovery: ケースに保管されていないデータ ソースを追加する

データをカストディアン (非保管データ ソースと呼ばれる) に関連付けずにケース [に追加します](non-custodial-data-sources.md)。 また、この保管されていないデータを保留する必要がある場合は、新しい高度なインデックス機能を使用して保持できます。

### <a name="data-connectors-hr-connector-enhancements"></a>データ コネクタ: HR コネクタの機能強化

(プレビュー中)新しいバージョンの [HR](import-hr-data.md) コネクタを使用すると、ジョブ レベルの変更、パフォーマンス レビュー、およびパフォーマンス向上計画に関連するデータをインポートできます。 その後、このデータを複数のインサイダー リスク ポリシーで [使用](insider-risk-management-policies.md) して、関連するアクティビティを検出できます。

### <a name="retention-labels-new-support-for-email"></a>保持ラベル: 電子メールの新しいサポート

保持ラベルを作成して [、メッセージ](retention.md#retention-labels) がラベル付けされた時間に基づいて電子メールの保持を開始できます。 これは予定表アイテムには適用されません。予定表アイテムは、アイテムが送信された時点に基づいて保持されます。

### <a name="sensitivity-labels-new-feature-and-an-improvement"></a>Sensitivity labels: New feature and an improvement

- (プレビュー中)ラベルの暗号化設定を構成する場合は、 [二](encryption-sensitivity-labels.md#double-key-encryption) 重キー暗号化を使用してラベル付けされたファイルと電子メールをさらに保護する新しいオプションを探します。
- ラベル ポリシーを作成または削除したり、ラベル ポリシーを作成、編集、または削除したりすると、変更は 1 時間以内にすべてのユーザー、アプリ、およびサービスに同期されます。

## <a name="june-2020"></a>2020 年 6 月

### <a name="spotlight-new-data-connectors-hit-preview"></a>スポットライト: 新しいデータ コネクタのヒット プレビュー

Microsoft 365 により多くのサード パーティソースからデータをインポートする約束を基に、さらに 2 つのデータ コネクタのプレビュー リリースをお知らせします。

- [Bloomberg メッセージ](archive-bloomberg-message-data.md)。 Bloomberg メッセージ コラボレーション ツールから金融サービスの電子メール データをインポートしてアーカイブします。 データがメールボックスに保存された後、訴訟ホールド、コンテンツ検索、インサイト アーカイブ、監査、通信コンプライアンス、アイテム保持ポリシーなどのコンプライアンス機能のデータにアクセスして使用できます。
- [ICE チャット](archive-icechat-data.md)。 ICE Chat コラボレーション ツールから金融サービスのチャット データをインポートしてアーカイブします。 データがメールボックスに保存された後、訴訟ホールド、電子情報開示、アーカイブ、監査、通信コンプライアンス、アイテム保持ポリシーなどのコンプライアンス機能のデータにアクセスして使用できます。

### <a name="compliance-score--compliance-manager-the-hits-keep-coming"></a>コンプライアンス スコア&コンプライアンス マネージャー: ヒットが続く

6 月の更新プログラムには、コンプライアンス スコアの新しい評価ドリルダウン [ビューが含まれます](compliance-score.md)。 コントロールの進行状況を監視したり、コンプライアンス スコアから直接評価を追加、削除したりします。

コンプライアンス スコアとコンプライアンス マネージャーの更新を最新の情報に残したい場合 コンプライアンス スコア [のリリース ノートにブックマークを付け](compliance-score-release-notes.md) 、頻繁に確認してください。

## <a name="may-2020"></a>2020 年 5 月

### <a name="spotlight-data-classification-is-officially-released"></a>スポットライト: データ分類が正式にリリースされる

データ分類 (別名[:](data-classification-overview.md)「データを知る」)、機能 (分析、コンテンツ エクスプローラー、アクティビティ エクスプローラー) がプレビュー フェーズから離れたので、すべての組織が利用できます。 強力な分析情報とツールを使用すると、組織全体のコンテンツで機密性の高い情報とラベル (保持と機密) がどのように使用されているのか検出および評価できます。 機密情報を含むコンテンツやラベルが適用されているコンテンツの確認、Microsoft 365 の場所でのラベル アクティビティの探索、カスタムの機密情報の種類の作成など。

ビデオ ツアーに参加する

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vx8x]

### <a name="trainable-classifiers-a-fix-and-a-feature"></a>トレーニング可能な分類子: 修正プログラムと機能

トレーニング可能な分類子の機能が強化される場合があります。

- フィードバックに基づく修正: カスタム分類子をシードしてトレーニングするときに、SharePoint サイトの URL とフォルダー パスを手動で入力する必要がなくなりました。 サイトとフォルダーの事前設定リストから選択できます。
- 新機能: Office アプリの機度ラベルを作成し、自動ラベル付け設定を構成するときに、トレーニング可能な分類子に一致するコンテンツにラベルを自動的に適用 (またはユーザーに適用することを推奨) できます。 [詳細情報](apply-sensitivity-label-automatically.md#configuring-trainable-classifiers-for-a-label)

### <a name="communication-compliance-yammer-support-is-here"></a>通信コンプライアンス: サポートYammerここ

コミュニケーション コンプライアンス ポリシーでは、Yammerプライベート メッセージとパブリック コミュニティの会話がサポートされています。 Yammer はオプションのチャネルであり、メッセージと添付ファイルのスキャンをサポートするためには、[ネイティブ モード](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode)に設定されている必要があります。

### <a name="data-loss-prevention-new-sharing-restriction"></a>データ損失防止: 新しい共有制限

SharePoint または OneDrive のコンテンツを保護する DLP ポリシーを設定する際に、"コンテンツへのアクセスを制限する" アクションを構成して、[リンクを持つ[](https://support.microsoft.com/office/share-files-outside-your-organization-with-anyone-links-53e91027-fb8e-4a6e-a3e4-5df4be32e38a)すべてのユーザー] オプションを使用してコンテンツへのアクセスを許可されたユーザーをブロックできます。

### <a name="insider-risk-management-tailor-your-alert-volume"></a>インサイダー リスク管理: アラートボリュームを調整する

インサイダー リスク ポリシーによって検出されたユーザー アクティビティには、特定のリスク スコアが割り当てられます。このスコアによってアラートの重大度 (低、中、高) が決定されます。 既定では、Microsoft 365 は一定量の低、中、高の重大度のアラートを生成しますが[](insider-risk-management-settings.md#alert-volume)、新しいアラート ボリューム設定を使用すると、ニーズに合わせてボリュームを増減できます。

### <a name="pst-import-new-region-supported"></a>PST インポート: サポートされる新しい地域

ネットワーク アップロードは、アラブ首長国連邦で利用できます。

### <a name="sensitivity-labels-new-privacy-option"></a>[Sensitivity labels]: 新しいプライバシー オプション

ラベルのサイトと [グループ](sensitivity-labels-teams-groups-sites.md#how-to-configure-groups-and-site-settings) の設定を構成するときに、プライバシー オプションを [なし] に設定し、ユーザーがサイトにアクセスできるユーザー **を選択できます**。 これは、コンテナー内のコンテンツを区別ラベルを使用して保護するが、ユーザーがプライバシー設定を自分で構成できる場合に便利です。

## <a name="april-2020"></a>2020 年 4 月

### <a name="records-management-overhauland-a-new-addition"></a>レコード管理: オーバーホール....および新しい追加

April には、レコード管理ソリューションに対する重要な更新が 2 つ含まれています。

- [レコード管理] セクションがコンプライアンス センターで完全に利用可能になります。 ファイル計画、保持ラベルとラベル ポリシー、イベント、廃棄のための更新されたユーザー インターフェイスと機能を活用します。
- 廃棄と言えば、SharePoint および[](disposition.md#disposition-of-records)OneDrive のレコードの廃棄証明も展開しました。 自動的に破棄された、または廃棄レビューの後に、それらの場所にあるアイテムの一覧を表示できます。

### <a name="sensitivity-labels-preview-auto-labeling-policies"></a>[Sensitivity labels]: Preview auto-labeling policies

自動ラベル付けポリシーを使用すると、既に保存されている SharePoint ドキュメントと OneDrive ドキュメント (保存データ) と、既に送信または受信されたメール (別名「送信中のメール」) に、自動的にラベルを適用できます。 このラベル付けはアプリではなくサービスによって適用されるので、ユーザーが持っているアプリとバージョンについて心配する必要はありません。

この機能は、区別ラベルの作成時に "Office アプリの自動ラベル付け" 設定に既に含まれている既存のクライアント側ラベル付け機能を拡張します。 両方の自動ラベル付けオプションの違いおよび利点を速くするには、更新された記事 [を参照してください](apply-sensitivity-label-automatically.md)。

## <a name="march-2020"></a>2020 年 3 月

### <a name="introducing-advanced-audit"></a>高度な監査の導入

[Microsoft 365](advanced-audit.md) の高度な監査では、組織が法医学とコンプライアンスの調査に役立つ新しい監査機能を導入しています。 主な機能として、監査ログの長期保持、カスタム監査ログ保持ポリシー、新しい *MailItemsAccessed* メールボックス監査アクション、および新しいテナント レベルの調整制限の導入が含まれます。この制限により、組織は監査データにアクセスするために割り当てられた帯域幅のクォータを完全に割り当てできます。

### <a name="compliance-score--compliance-manager-preview-the-latest-enhancements"></a>コンプライアンス スコア & コンプライアンス マネージャー: 最新の拡張機能をプレビューする

このプレビュー リリースの主な更新プログラムは次のとおりです。

- テンプレートの作成と変更のプロセスを簡素化する
- テンプレートとアクションのバージョン管理に関する通知と制御
- グループ間で共通のアクションを同期する
- 中国語 (簡体字)、中国語 (繁体字)、フランス語、ドイツ語、イタリア語、日本語、韓国語、ポルトガル語 (ブラジル)、ロシア語、スペイン語に言語サポートが拡張されました

コンプライアンス スコアと[コンプライアンス マネージャーの](compliance-score.md)[詳細](compliance-manager-overview.md)

### <a name="sensitivity-labels-support-for-labeling-office-files-in-sharepoint-and-onedrive-preview"></a>感度ラベル: SharePoint および OneDrive Officeファイルへのラベル付け (プレビュー) のサポート

プレビューを有効にすると、ユーザーは Web 上のOfficeラベルを適用できます。 リボンの **[Sensitivity]** ボタンと、ステータス バーに適用されたラベル名を表示できます。 さらに、デスクトップ アプリを使用して SharePoint または OneDrive にファイルにラベルを付けて保存した場合、ラベルに暗号化設定が適用されている場合、Microsoft 365 はこれらのファイルのコンテンツを処理できます。 このような状況では、共同編集、電子情報開示、データ損失防止、検索、その他の共同作業機能もサポートされます。

[プレビューを有効にする方法について](sensitivity-labels-sharepoint-onedrive-files.md)

## <a name="february-2020"></a>2020 年 2 月

### <a name="insider-risk-management-is-officially-released"></a>インサイダー リスク管理が正式にリリースされる

ロール、お願いします。...<br>インサイダー リスク管理は、次のサブスクリプションを持つ組織で利用できます。

- [Microsoft 365 E5](https://go.microsoft.com/fwlink/?linkid=2120431) (有料版または試用版)
- Microsoft E5 コンプライアンス アドオンを使用した Microsoft 365 [Enterprise E3 サブスクリプション](https://go.microsoft.com/fwlink/?linkid=2120432)

新しい役割グループやソリューション全体の設定など、プレビュー リリース以降 [にいくつかの](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management) 改善 [を](insider-risk-management-configure.md#step-4-configure-insider-risk-settings)行いました。

お客様がソリューションを使用する場合は、常にフィードバックをお寄せください。改善を継続して行います。

### <a name="records-management"></a>レコード管理

この新しいソリューションは、すべてのレコード管理機能を単一の管理下に置きます。 主な機能は、SharePoint および OneDrive のレコードのバージョン管理の導入と、レコードの廃棄の証明です。

![Microsoft 365 コンプライアンス センターの [レコード管理] ページ](../media/mcc-records-management-page.png)

[レコード管理の詳細](records-management.md)

### <a name="solution-spotlight-data-connectors-for-facebook-and-twitter"></a>ソリューション スポットライト: Facebook と Twitter のデータ コネクタ

先月 [リリースされた](#just-launched) データ コネクタは、次のコネクタのテストに役立ちます。

- [Facebook ビジネス ページ](archive-facebook-data-with-sample-connector.md)。 Facebook ビジネス ページから Microsoft 365 にデータをインポートしてアーカイブします。 レコード管理や電子情報開示などのコンプライアンス ソリューションに役立つ。
- [Twitter](archive-twitter-data-with-sample-connector.md). Twitter から Microsoft 365 にデータをインポートしてアーカイブします。 レコード管理や電子情報開示などのコンプライアンス ソリューションに役立つ。

これらのコネクタをセットアップして検証する場合は、うまくいったのか、何が良くなかったのか、エクスペリエンスを改善するために何ができないかについてフィードバックをお寄せください。

## <a name="january-2020"></a>2020 年 1 月

待機は終わりました。 Microsoft 365 コンプライアンス センターは、Microsoft 365、Office 365、Enterprise Mobility + Security (EMS)、Windows 10 Enterprise の各プランをお持ちのすべてのお客様が利用できます。 セキュリティ/コンプライアンス センターで管理していたデータまたはポリシー&コンプライアンス センターで利用できます。そのため、前後にジャンプする必要はありません。

ブックマークを作成して、組織全体のコンプライアンスを管理するための 1 か月のショップ [https://compliance.microsoft.com](https://compliance.microsoft.com) を紹介します。または [、この記事を読](microsoft-365-compliance-center.md) んでもう少し掘り下げください。

![Microsoft 365 コンプライアンス センターのホーム ページ](../media/mcc-home-ga.png)

また、新しいソリューションと更新されたソリューションを今月リリースしました。 以下は、ハイライトを一目見た目で示しています。

### <a name="now-in-preview"></a>プレビュー中

**インサイダー リスク管理 (プレビュー)**

インサイダー リスク管理ソリューションがパブリック プレビューに入りましたのでお知らせします。 インサイダー リスク管理は、次の機能を提供することで、インサイダー リスクに対する組織のインテリジェントな識別とアクションの実行を支援します。

- ユーザーのプライバシーを確保するための匿名性コントロール。
- データ漏洩などのインサイダーの脅威を識別するネイティブおよびサード パーティのインジケーターを含むインテリジェント なポリシー テンプレート。
- IT、人事、法務チーム全体にわたる統合されたエンドツーエンドの調査ワークフロー。

ご意見をお聞かしいと思います。 お客様がソリューションを使用する場合は、一般提供に向けてお客様のニーズを満たしてお客様のニーズを満たせできるよう、フィードバックをお寄せください。

[インサイダー リスク管理の詳細](insider-risk-management.md)

### <a name="just-launched"></a>起動されたばかり

**通信コンプライアンス**

プレビュー フェーズから完全な可用性への取り組みにより、通信コンプライアンスは新しいインサイダー リスク ソリューション セットの重要なコンポーネントです。 この堅牢なソリューションは、組織の基準を満たさなかったメッセージの検出、調査、修復アクションを実行するためのワークフローを使用して、通信リスクを最小限に抑えるのに役立ちます。

プレビュー中のお客様からのフィードバックは素晴らしいものでした。 その結果、開始するための最初の実行エクスペリエンス、調査と修復アクションの改善など、いくつかの機能が強化されました。

[通信コンプライアンスの詳細](communication-compliance.md)

![Microsoft 365 コンプライアンス センターの通信コンプライアンス ページにようこそエクスペリエンスの最初のカードが表示されている](../media/mcc-communication-compliance-page-with-fre.png)

**データ コネクタ**

以前は Office 365 セキュリティ & コンプライアンス センターの他の 「インポート」機能とスペースを共有する場合、データ コネクタは Microsoft 365 コンプライアンス センターに独自のホームを持つものになっています。 新しい [データ コネクタ] ページを使用して、組織の人事 (HR) ファイルやさまざまなサードパーティ プラットフォーム (Facebook、LinkedIn、Twitter、Instant Bloomberg など) から Microsoft 365 組織内のメールボックスにデータをインポートしてアーカイブします。 インポート後、このデータは、電子情報開示、インサイダー リスク管理、通信コンプライアンス、監査、保持ポリシーなど、いくつかのコンプライアンス ソリューションで管理できます。

[データ コネクタの詳細](archiving-third-party-data.md)

![Microsoft 365 コンプライアンス センターの [データ コネクタ] ページ](../media/mcc-data-connectors-page.png)

### <a name="noteworthy-updates"></a>注目すべき更新プログラム

**コンプライアンス スコア (プレビュー) の新しい評価テンプレート**

コンプライアンス スコア チームでは、常に進化し続けるコンプライアンス環境を先取りするために常に取り組み、最近の規制に対する組織のコンプライアンス体制を評価し、より効果的なコントロールを実装する方法に関するガイダンスを得る際に役立つ新しい一連のテンプレートを提供しました。 次の新しいテンプレートが表示されます。

- ISO/IEC 27701:2019
- カリフォルニア州消費者プライバシー法 (CCPA)
- ブラジルの一般データ保護法 (Lg Geral de Proteção de Brazilos - LGPD)
- SOC 1 タイプ 2 および SOC 2 タイプ 2

[コンプライアンス スコア テンプレートの詳細](compliance-score.md#templates)