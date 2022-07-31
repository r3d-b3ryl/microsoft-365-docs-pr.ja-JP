---
title: Microsoft Purview のリスクおよびコンプライアンス ソリューション
description: Microsoft Purview のリスクとコンプライアンス ソリューションの詳細については、この記事を参照してください。
keywords: Microsoft 365、Microsoft Purview、コンプライアンス、ソリューション
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: m365-security-compliance
ms.openlocfilehash: 96b1efdddcf8a0b2e1034c392c27f160137379de
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66994492"
---
# <a name="microsoft-purview-risk-and-compliance-solutions"></a>Microsoft Purview のリスクおよびコンプライアンス ソリューション

[Microsoft Purview](/purview/purview) のリスクとコンプライアンス ソリューションは、データの管理と監視、情報の保護、コンプライアンス リスクの最小化、および規制要件の満たすのに役立ちます。 この記事は、Microsoft Purview のリスクとコンプライアンス ソリューションについて学習し、組織の特定のコンプライアンス ニーズを満たすためにこれらのソリューションの展開をすばやく開始するのに役立ちます。

## <a name="protect-sensitive-data-across-clouds-apps-and-devices"></a>クラウド、アプリ、デバイス全体で機密データを保護する

情報保護戦略はビジネス ニーズによって推進される必要がありますが、すべての組織にはデータの一部または全部を保護する必要があります。 [Microsoft Purview 情報保護](/microsoft-365/compliance/information-protection) (以前はMicrosoft Information Protection) の機能を使用して、機密情報がどこに存在するか移動する場合でも、機密情報を検出、分類、保護、管理するのに役立ちます。

### <a name="know-your-data"></a>データを把握する

すべての Microsoft 365 サービスとオンプレミスに情報が存在します。 機密性の高い項目を特定し、それらがどのように使用されているかを把握することは、情報保護の実践の中心です。 Microsoft Purview には次のものが含まれます。

- 組み込みまたはカスタム正規表現、または関数を使用して機密項目を識別する[機密情報の種類](/microsoft-365/compliance/sensitive-information-type-learn-about)。
- アイテム内の要素を識別するのではなく、目的のデータの例を使用して機密アイテムを識別する[トレーニング可能な分類子](/microsoft-365/compliance/classifier-learn-about)。
- [データ分類](/microsoft-365/compliance/data-classification-overview) では、機密ラベル、保持ラベル、または分類された組織内のアイテムと、ユーザーが実行しているアクションをグラフィカルに識別できます。

### <a name="protect-your-data"></a>データを保護する

Microsoft Purview 情報保護 ソリューションから、データが格納されている場所とアクセス先にかかわらず、データを保護するために使用できる機能は多数あります。 ただし、秘密度ラベルは、保護アクションを提供し、他の Purview ソリューションや機能と対話する基本的な機能です。

秘密度ラベルを使用すると、ユーザーと管理者は、使用しているデータの秘密度を把握でき、ラベル自体は暗号化、アクセス制限、視覚的なマーキングを含む保護アクションを適用できます。 サポートされているラベル付けシナリオの範囲の詳細については、作業の開始に関するドキュメントの [「機密ラベルの一般的なシナリオ](/microsoft-365/compliance/get-started-with-sensitivity-labels#common-scenarios-for-sensitivity-labels) 」セクションを参照してください。 秘密度ラベルの詳細については、「秘密 [度ラベルの詳細](/microsoft-365/compliance/sensitivity-labels)」を参照してください。

### <a name="prevent-data-loss"></a>データの損失を防止する

機密アイテムを意図せずに共有すると、組織に金銭的損害を与え、法律や規制に違反する可能性があります。 [Microsoft Purview データ損失防止](/microsoft-365/compliance/dlp-learn-about-dlp)は、組織の内部と外部の両方で機密情報を意図せずに共有したり、偶発的に共有したりしないように組織を保護するのに役立ちます。 データ損失防止ポリシーでは、次のことを行います。

- 財務データ、健康データ、医療データ、プライバシー データなど、監視する機密情報を定義します。
- Microsoft 365 サービスや Windows デバイスや macOS デバイスなど、監視する場所。
- クレジット カード、運転免許証、社会保障番号を含むアイテムなど、アイテムに適用するポリシーに一致する必要がある条件。
- 監査、アクティビティのブロック、オーバーライドによるアクティビティのブロックなど、一致が見つかったときに実行するアクション。

### <a name="manage-your-data-lifecycle"></a>データ ライフサイクルを管理する

[Microsoft Purview データ ライフサイクル管理](/microsoft-365/compliance/manage-data-governance#microsoft-purview-data-lifecycle-management) (旧称 Microsoft Information Governance) には、Exchange、SharePoint、OneDrive、Microsoft 365 グループ、Teams、Yammer 全体でコンテンツを保持および削除するためのツールと機能が用意されています。 電子メール、ドキュメント、メッセージの保持と削除は、多くの場合、コンプライアンスと規制の要件に必要です。 ただし、ビジネス価値がなくなったコンテンツを削除すると、攻撃面も減少します。

詳細については、「 [データ ライフサイクル管理の詳細](/microsoft-365/compliance/data-lifecycle-management)」を参照してください。

### <a name="encrypt-your-data-and-control-your-encryption-keys"></a>データを暗号化し、暗号化キーを制御する

[暗号化](/microsoft-365/compliance/encryption) は、ファイル保護と情報保護戦略の重要な部分です。 暗号化プロセスでは、データ (プレーンテキストと呼ばれます) が暗号テキストにエンコードされます。 プレーンテキストとは異なり、暗号化テキストが暗号化解除されるまで、人やコンピューターでは暗号テキストを使用できません。 復号化には、承認されたユーザーのみが持つ暗号化キーが必要です。 暗号化を使用すると、承認された受信者のみがコンテンツの暗号化を解除できるようになります。

[Microsoft Purview Double Key Encryption](/microsoft-365/compliance/double-key-encryption) は、最も厳しい保護要件の対象となる最も機密性の高いデータをセキュリティで保護するのに役立ちます。 [Microsoft Purview カスタマー キー](/microsoft-365/compliance/customer-key-overview) は、ルート キーを制御するための規制またはコンプライアンスの義務を満たすのに役立ちます。 Microsoft 365 サービスが暗号化キーを使用して、電子情報開示、マルウェア対策、スパム対策、検索インデックス作成などの付加価値クラウド サービスを提供することを明示的に承認します。

## <a name="identify-data-risks-and-manage-regulatory-compliance-requirements"></a>データ リスクを特定し、規制コンプライアンス要件を管理する

インサイダー リスクは、現代の職場におけるセキュリティとコンプライアンスの専門家の最大の懸念事項の 1 つです。 業界調査によると、インサイダー リスクは、多くの場合、特定のユーザー イベントやアクティビティに関連しています。 このようなリスクから組織を保護することは、特定が困難で軽減が困難な場合があります。 インサイダー リスクには、さまざまな分野の脆弱性が含まれており、知的財産の損失から職場での嫌がらせなど、組織に大きな問題を引き起こす可能性があります。

Microsoft Purview には、組織がデータ リスクとコンプライアンス要件を管理するのに役立つ次のコンプライアンス ソリューションが用意されています。

- [インサイダー リスク管理](#detect-and-act-on-risk-activities-with-insider-risk-management)
- [通信コンプライアンス](#detect-and-act-on-inappropriate-and-sensitive-messages-with-communication-compliance)
- [情報障壁](#restrict-communication-and-collaboration-between-users-with-information-barriers)
- [レコード管理](#manage-business-legal-or-regulatory-record-keeping-requirements-with-records-management)
- [監査 (Premium) と Audit (Standard)](#log-and-search-for-audited-activities-in-sharepoint-and-onedrive-with-audit-premium-or-audit-standard)
- [電子情報開示 (Premium) と電子情報開示 (Standard)](#identify-and-manage-data-for-legal-cases-with-ediscovery-premium-or-ediscovery-standard)

### <a name="detect-and-act-on-risk-activities-with-insider-risk-management"></a>インサイダー リスク管理を使用してリスク アクティビティを検出して操作する

[Microsoft Purview インサイダー リスク管理](/microsoft-365/compliance/insider-risk-management)では、サービスとサード パーティのインジケーターの全幅を使用して、組織内の危険なユーザー アクティビティをすばやく特定、トリアージ、および操作するのに役立ちます。 Microsoft 365 と Microsoft Graph のログを使用すると、インサイダー リスク管理を使用して、リスク インジケーターを識別するための特定のポリシーを定義できます。 危険なアクティビティを特定した後、これらのリスクを軽減するアクションを実行できます。

### <a name="detect-and-act-on-inappropriate-and-sensitive-messages-with-communication-compliance"></a>コミュニケーション コンプライアンスを使用して、不適切で機密性の高いメッセージを検出して処理する

機密情報を保護し、職場での嫌がらせのインシデントを検出して対処することは、内部のポリシーと基準の遵守の重要な部分です。 [Microsoft Purview コミュニケーション コンプライアンス](/microsoft-365/compliance/communication-compliance-policies)は、電子メールと Microsoft Teams の通信の修復アクションを迅速に検出、キャプチャ、および実行できるようにすることで、これらのリスクを最小限に抑えるのに役立ちます。 これには、組織内外で機密情報を共有する不適切なコミュニケーション、脅威、嫌がらせ、コミュニケーションが含まれます。

### <a name="restrict-communication-and-collaboration-between-users-with-information-barriers"></a>情報バリアを持つユーザー間の通信とコラボレーションを制限する

[Microsoft Purview Information Barriers (IB)](/microsoft-365/compliance/information-barriers) は、Microsoft Teams、SharePoint Online、およびOneDrive for Businessのグループとユーザー間の双方向通信とコラボレーションを制限できるコンプライアンス ソリューションです。 規制の厳しい業界でよく使用される IB は、関心の対立を回避し、ユーザーと組織領域間の内部情報を保護するのに役立ちます。

### <a name="manage-business-legal-or-regulatory-record-keeping-requirements-with-records-management"></a>レコード管理を使用して、ビジネス、法的、または規制上の記録保持要件を管理する

[Microsoft Purview レコード管理](/microsoft-365/compliance/manage-data-governance#microsoft-purview-records-management)は、組織が法的義務を管理し、規制への準拠を示す機能を提供し、保持する必要がなくなったり、価値がなくなったり、ビジネス目的で必要なくなったりするアイテムを定期的に処理することで効率を向上させます。 詳細については、「[レコードの詳細](/microsoft-365/compliance/records-management)」を参照してください。

### <a name="log-and-search-for-audited-activities-in-sharepoint-and-onedrive-with-audit-premium-or-audit-standard"></a>監査 (Premium) または Audit (Standard) を使用して SharePoint と OneDrive で監査されたアクティビティをログに記録して検索する

[Microsoft Purview 監査ソリューション](/microsoft-365/compliance/auditing-solutions-overview) は、組織がセキュリティ イベント、フォレンジック調査、内部調査、コンプライアンス義務に効果的に対応するのに役立つ統合ソリューションを提供します。 何十もの Microsoft 365 サービスやソリューションで実行された何千ものユーザーや管理者の操作は、組織の統一された監査ログにキャプチャされ、記録されて保持されます。 これらのイベントの監査記録は、組織内のセキュリティ オペレーション、IT 管理者、インサイダー リスク チーム、コンプライアンスや法務調査担当者が検索できます。 この機能により、Microsoft 365 の組織全体で行われているアクティビティを可視化することができます。

監査ソリューションの詳細については、「 [監査 (Premium)](/microsoft-365/compliance/advanced-audit) と [監査 (Standard)」](/microsoft-365/compliance/set-up-basic-audit)を参照してください。

### <a name="identify-and-manage-data-for-legal-cases-with-ediscovery-premium-or-ediscovery-standard"></a>電子情報開示 (Premium) または電子情報開示 (Standard) を使用して訴訟のデータを特定して管理する

電子情報開示 (電子情報開示) は、法的、規制上、またはビジネス上の理由から電子情報を特定、収集、監査するプロセスです。 [Microsoft Purview eDiscovery ソリューション](/microsoft-365/compliance/ediscovery)を使用すると、Exchange Online、OneDrive for Business、SharePoint Online、Microsoft Teams、Microsoft 365 グループ、Yammer チームでデータとコンテンツを検索できます。 同じ電子情報開示検索でメールボックスとサイトを検索し、検索結果をエクスポートして分析と確認を行うことができます。

電子情報開示ソリューションの詳細については、「 [電子情報開示 (Premium)](/microsoft-365/compliance/overview-ediscovery-20) と電子情報開示 [(Standard)」](/microsoft-365/compliance/get-started-core-ediscovery)を参照してください。

## <a name="get-started-with-regulatory-compliance"></a>規制コンプライアンスの概要

組織は、ポリシー、業界標準、地域規制の複雑で進化する Web に準拠し、潜在的な非準拠のコストの増加にも対処する必要があります。 実際、何千もの規制機関から 1 日に何百もの更新プログラムがあるため、急速に変化するコンプライアンス環境を最新の状態に保つことは困難です。 Microsoft Purview コンプライアンス マネージャーとコンプライアンス オファリングの詳細なコレクションは、組織がこれらの規制要件を管理するのに役立ちます。

### <a name="get-started-with-compliance-manager"></a>コンプライアンス マネージャーの使用を開始する

[Microsoft Purview コンプライアンス マネージャー](/microsoft-365/compliance/compliance-manager)は、組織のコンプライアンス要件をより簡単かつ便利に管理するのに役立つ、Microsoft Purview コンプライアンス ポータルの機能です。 コンプライアンス マネージャーは、データ保護リスクのインベントリの作成から、複雑な制御の実装の管理、規制や認証の最新情報の入手、監査人への報告まで、コンプライアンスの過程全体を支援します。

### <a name="learn-about-microsoft-regulatory-compliance-offerings"></a>Microsoft の規制コンプライアンス製品について説明する

Microsoft では、データの収集と使用に関する国内、地域、国際、および業界固有の要件に組織が準拠するのに役立つ包括的な [コンプライアンス オファリング](/compliance/regulatory/offering-home) セットを提供しています。

## <a name="deploy-purview-compliance-solutions"></a>Purview コンプライアンス ソリューションを展開する

地域固有のソリューションには、セキュリティで保護されたコンプライアンスデータコラボレーションのための統合コンプライアンス ソリューションを理解し、計画し、実装するために必要な技術ガイダンスがまとめられています。

- [ゼロ トラストでデータを保護する](/security/zero-trust/deploy/data)
- [情報保護ソリューションの展開](/microsoft-365/compliance/information-protection-solution)
- [データ ガバナンス ソリューションをデプロイする](/microsoft-365/compliance/data-governance-solution)
- [データ プライバシー規制用の情報保護の展開](/microsoft-365/solutions/information-protection-deploy)
- [情報保護&コンプライアンスの図を確認する](/microsoft-365/solutions/productivity-illustrations)

## <a name="next-steps-for-organizations-new-to-risk-and-compliance-solutions"></a>リスクソリューションとコンプライアンス ソリューションを使用する組織の次の手順

- [Microsoft Purview ソリューション試用版について学習する](/microsoft-365/compliance/compliance-easy-trials)
- [Microsoft Purview でのコンプライアンスの概要に関するクイック タスク](/microsoft-365/compliance/compliance-quick-tasks)
