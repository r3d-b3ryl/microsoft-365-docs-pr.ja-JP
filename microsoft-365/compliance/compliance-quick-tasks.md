---
title: Microsoft Purview でのコンプライアンスの概要に関するクイック タスク
description: Microsoft Purview でのコンプライアンスの迅速な開始に役立つタスクについて説明します。
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
f1.keywords:
- NOCSH
ms.collection:
- m365-security-compliance
- m365initiative-compliance
ms.custom:
- admindeeplinkDEFENDER
- intro-get-started
ms.localizationpriority: medium
ms.openlocfilehash: cb8471ffea418ac47921777a0ee9594fa73fe4ac
ms.sourcegitcommit: a5e75d7f7651313818bd2de292d5c38b290d8975
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2022
ms.locfileid: "65930221"
---
# <a name="quick-tasks-for-getting-started-with-compliance-in-microsoft-purview"></a>Microsoft Purview でのコンプライアンスの概要に関するクイック タスク

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Microsoft Purview を初めて使用し、どこから始めればいいのか疑問に思う場合は、この記事では基本に関するガイダンスを提供し、重要なコンプライアンス タスクに優先順位を付けます。 この記事は、データの管理と監視、情報の保護、インサイダー リスクの最小化を迅速に開始するのに役立ちます。

この記事は、リスクを管理し、データを保護し、新しくリモートワークフォースを使用して規制や標準に準拠し続ける最善の方法を考え出す場合にも役立ちます。 従業員は新しい方法で共同作業を行い、相互に接続しています。この変更は、既存のコンプライアンス プロセスと制御を適応させる必要がある可能性があることを意味します。 組織内でこれらの新しいコンプライアンス リスクを特定して管理することは、データを保護し、脅威とリスクを最小限に抑えるために重要です。

これらの基本的なコンプライアンス タスクを完了したら、追加の Microsoft Purview ソリューションを実装して、組織内のコンプライアンス 範囲を拡大することを検討してください。

## <a name="task-1-configure-compliance-permissions"></a>タスク 1: コンプライアンスアクセス許可を構成する

組織内のだれが Microsoft Purview コンプライアンス ポータルにアクセスしてコンテンツを表示し、管理タスクを実行するかを管理することが重要です。 Microsoft 365 には、コンプライアンスに固有の管理ロールと、Microsoft Purview コンプライアンス ポータルに含まれるツールを使用するための管理ロールが用意されています。

まず、組織内のユーザーにコンプライアンスアクセス許可を割り当てて、これらのタスクを実行し、承認されていないユーザーが自分の責任の範囲外の領域にアクセスできないようにします。 Microsoft 365 に含まれるコンプライアンス ソリューションの構成と実装を開始する前に、適切なユーザーを **コンプライアンス データ管理者** と **コンプライアンス管理者** の管理者ロールに割り当てる必要があります。 また、コンプライアンス マネージャーでデータを表示するには、Azure Active Directory グローバル リーダー ロールにユーザーを割り当てる必要もあります。

アクセス許可を構成し、管理者ロールにユーザーを割り当てる詳細なガイダンスについては、「 [セキュリティ & コンプライアンス センターのアクセス許可](/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)」を参照してください。

## <a name="task-2-know-your-state-of-compliance"></a>タスク 2: コンプライアンスの状態を把握する

自分がどこにいるかわからない場合、どこに行けばいいかわからないのは難しいです。 コンプライアンスのニーズを満たすには、現在のリスク レベルと、変化し続けるこれらの時代に必要になる可能性のある更新プログラムを理解することが含まれます。 組織がコンプライアンス要件に新しい場合でも、業界を管理する標準や規制に関する豊富な経験を持っている場合でも、コンプライアンスを改善するために実行できる最善の方法は、組織がどこに立っているかを理解することです。

[Microsoft Purview コンプライアンス マネージャー](/microsoft-365/compliance/compliance-manager) は、組織のコンプライアンス体制を理解し、改善が必要な領域を強調するのに役立ちます。 コンプライアンス マネージャーは、一元化されたダッシュボードを使用してリスクベースのスコアを計算し、データ保護と規制基準に関するリスクを軽減するのに役立つアクションの完了の進行状況を測定します。 コンプライアンス マネージャーをツールとして使用して、すべてのリスク評価を追跡することもできます。 一般的なツールを使用してリスク評価を効率的に完了させるためのワークフロー機能を提供します。

コンプライアンス マネージャーの使用を開始するための詳細なガイダンスについては、「コンプライアンス マネージャーの [概要](/microsoft-365/compliance/compliance-manager-setup)」を参照してください。

> [!IMPORTANT]
> セキュリティとコンプライアンスは、ほとんどの組織で緊密に統合されています。 セキュリティとコンプライアンスの両方に対する防御の詳細なアプローチを提供するために、組織が基本的なセキュリティ、脅威保護、ID およびアクセス管理領域に対処することが重要です。
>
> [Microsoft 365 Defender ポータルで Microsoft 365 セキュリティ スコア](/microsoft-365/security/defender/microsoft-secure-score)を確認し、次の記事で説明されているタスクを完了します。<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank"></a>
>
> - [セキュリティ ロードマップ - 最初の 30 日間、90 日間、およびそれ以降の最優先事項](/microsoft-365/security/office-365-security/security-roadmap)
> - [自宅での作業をサポートするセキュリティ チームの上位 12 タスク](/microsoft-365/security/top-security-tasks-for-remote-work)

## <a name="task-3-enable-auditing-for-your-organization"></a>タスク 3: 組織の監査を有効にする

組織の現在の状態とコンプライアンス機能を管理できるユーザーを決定したので、次の手順では、コンプライアンス調査を実施し、組織内のネットワークアクティビティとユーザー アクティビティのレポートを生成するためのデータがあることを確認します。 監査を有効にすることも、この記事の後半で取り上げるコンプライアンス ソリューションの重要な前提条件です。

監査ログによって提供される分析情報は、コンプライアンス要件を、改善が必要なコンプライアンス領域の管理と監視に役立つソリューションと照合するのに役立つ貴重なツールです。 アクティビティを記録する前と監査ログを検索する前に、監査ログを有効にする必要があります。 有効にすると、組織のユーザーと管理者のアクティビティが監査ログに記録され、ユーザーに割り当てられたライセンスに応じて最大 1 年間、90 日間保持されます。

監査を有効にする詳しい手順については、「[監査ログ検索を有効または無効する](/microsoft-365/compliance/turn-audit-log-search-on-or-off)」を参照してください。

## <a name="task-4-create-policies-to-alert-you-about-potential-compliance-issues"></a>タスク 4: 潜在的なコンプライアンスの問題について警告するポリシーを作成する

Microsoft では、管理者のアクセス許可の悪用、マルウェア アクティビティ、潜在的な外部および内部の脅威、データ ライフサイクル管理のリスクを特定するのに役立つ、いくつかの組み込みのアラート ポリシーを提供しています。 これらのポリシーは既定で有効になっていますが、組織固有のコンプライアンス要件を管理するためにカスタム アラートを構成する必要がある場合があります。

アラート ポリシーとアラート ダッシュボード ツールを使用してカスタム アラート ポリシーを作成し、ユーザーがポリシー条件に一致するアクティビティを実行したときに生成されたアラートを表示します。 たとえば、アラート ポリシーを使用して、組織内のコンプライアンス要件、アクセス許可、データ損失インシデントに影響を与えるユーザーと管理者のアクティビティを追跡できます。

カスタム アラート ポリシーを作成するための詳細なガイダンスについては、「 [セキュリティとコンプライアンス センターのアラート ポリシー](/microsoft-365/compliance/alert-policies)」を参照してください。

## <a name="task-5-classify-and-protect-sensitive-data"></a>タスク 5: 機密データを分類して保護する

組織の従業員は、業務を行うために組織内外の関係者と共同作業を行います。このためコンテンツはファイアウォールの内側だけでなく、さまざまなデバイス、アプリ、サービスを越えて存在することになります。この場合、組織のビジネス ポリシーとコンプライアンス ポリシーを満たす安全な方法でコンテンツを保護することが必要です。

[秘密度ラベル](/microsoft-365/compliance/sensitivity-labels) を使用すると、組織のデータを分類して保護しながら、ユーザーの生産性と共同作業能力が妨げられないことを確認できます。 秘密度ラベルを使用して、暗号化と使用制限を適用すると、視覚的なマーキングが適用され、プラットフォームやデバイス、オンプレミス、クラウド内の情報が保護されます。

秘密度ラベルを構成して使用するための詳細なガイダンスについては、「秘密度ラベルの [概要](/microsoft-365/compliance/get-started-with-sensitivity-labels)」を参照してください。

## <a name="task-6-configure-retention-policies"></a>タスク 6: アイテム保持ポリシーを構成する

[アイテム保持ポリシー](/microsoft-365/compliance/retention)を使用すると、コンテンツを保持するか、コンテンツを削除するか、またはその両方を保持してから、指定した保持期間の終わりにコンテンツを削除するかを事前に決定できます。 これらのアクションは、業界の規制や内部ポリシーに準拠し、訴訟やセキュリティ違反が発生した場合のリスクを軽減するために必要な場合があります。

コンテンツがアイテム保持ポリシーの対象になると、ユーザーは何も変更されていないかのようにコンテンツを編集して操作し続けることができます。 コンテンツは元の場所に保持されます。 ただし、アイテム保持ポリシーの対象となるコンテンツを他のユーザーが編集または削除した場合、元のコンテンツのコピーは、そのコンテンツのアイテム保持ポリシーが有効な間、保持される安全な場所に保存されます。

Teams と Yammer メッセージ、Exchange メール、SharePoint サイト、OneDrive アカウントを含む、Microsoft 365 環境内の複数のサービスに対してアイテム保持ポリシーをすばやく設定できます。 アイテム保持ポリシーに自動的に含めることができるユーザー、メールボックス、またはサイトの数に制限はありません。 ただし、より選択的になる必要がある場合は、特定のインスタンスを動的にターゲットにするクエリ ベースのアダプティブ スコープ、または常に含めるか常に除外する特定のインスタンスを指定する静的スコープを構成することで、これを行うことができます。

アイテム保持ポリシーを構成するための詳細なガイダンスについては、「アイテム保持ポリシー [の作成と構成」を](/microsoft-365/compliance/create-retention-policies)参照してください。 アイテム保持ポリシーは、Microsoft 365 アプリとサービスのデータ ライフサイクル管理戦略の基礎を形成するため、 [データ ライフサイクル管理の概要](/microsoft-365/compliance/get-started-with-data-lifecycle-management)に関するページも参照してください。

## <a name="task-7-configure-sensitive-information-and-inappropriate-language-policies"></a>タスク 7: 機密情報と不適切な言語ポリシーを構成する

機密情報を保護し、職場での嫌がらせのインシデントを検出して対処することは、内部のポリシーと基準の遵守の重要な部分です。 Microsoft Purview の[通信コンプライアンス](/microsoft-365/compliance/communication-compliance)は、電子メールと Microsoft Teams 通信の修復アクションを迅速に検出、キャプチャ、および実行できるようにすることで、これらのリスクを最小限に抑えるのに役立ちます。 これには、組織内外で機密情報を共有する不適切なコミュニケーション、脅威、嫌がらせ、コミュニケーションが含まれます。

定義済みの *不適切なテキスト* ポリシー テンプレートを検出すると、ポリシーの一致について内部および外部の通信をスキャンして、指定されたレビュー担当者が調べられるようにすることができます。 校閲者は、組織内のスキャンされた電子メール、Microsoft Teams、Yammer、またはサードパーティの通信を調査し、適切な修復アクションを実行して、組織の標準に準拠していることを確認できます。

定義済みの機密情報の *検出* ポリシー テンプレートを使用すると、定義済みの機密情報の種類やキーワードを含む電子メールや Microsoft Teams の通信をスキャンするポリシーをすばやく作成し、重要なデータがアクセス権を持つ必要がないユーザーと共有されないようにするのに役立ちます。 これらのアクティビティには、機密プロジェクトに関する未承認の通信、インサイダー取引やその他の共謀活動に関する業界固有の規則が含まれる場合があります。

通信コンプライアンスの計画と構成に関する詳細なガイダンスについては、「 [通信コンプライアンスの計画](/microsoft-365/compliance/communication-compliance-plan) 」と「 [コミュニケーション コンプライアンスの概要](/microsoft-365/compliance/communication-compliance-configure)」を参照してください。 通信コンプライアンス ライセンス情報については、 [セキュリティ&コンプライアンスに関する Microsoft 365 ライセンス ガイダンスを](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-compliance)参照してください。

## <a name="task-8-see-whats-happening-with-your-sensitive-items"></a>タスク 8: 機密アイテムで何が起こっているかを確認する

機密ラベル、機密情報の種類、保持ラベルとポリシー、トレーニング可能な分類子は、前のタスクで見てきたように、Exchange、SharePoint、OneDrive 全体で機密アイテムを分類およびラベル付けするために使用できます。 クイック タスク体験の最後の手順は、ラベルが付けられているアイテムと、ユーザーが機密アイテムに対して実行しているアクションを確認することです。 [コンテンツ エクスプローラー](/microsoft-365/compliance/data-classification-content-explorer) と [アクティビティ エクスプローラーは](/microsoft-365/compliance/data-classification-activity-explorer) 、この可視性を提供します。

### <a name="content-explorer"></a>コンテンツ エクスプローラー

コンテンツ エクスプローラーを使用すると、ネイティブ形式で、機密情報の種類として分類されているか、トレーニング可能な分類子によって特定の分類に属しているすべてのアイテム、および機密ラベルまたは保持ラベルが適用されているすべてのアイテムを表示できます。

コンテンツ エクスプローラーの使用に関する詳細なガイダンスについては、「 [データの概要 - データ分類の概要](/microsoft-365/compliance/data-classification-overview)」と「 [コンテンツ エクスプローラーの概要](/microsoft-365/compliance/data-classification-content-explorer)」を参照してください。

### <a name="activity-explorer"></a>アクティビティ エクスプローラー

アクティビティ エクスプローラーを使用すると、分類済みの機密アイテムとラベル付けされた機密アイテムの実行内容を監視できます。

- SharePoint
- Exchange
- OneDrive

使用可能なフィルターは 30 種類以上あり、以下がその一例です。

- 日付の範囲
- アクティビティの種類
- 場所
- ユーザー
- 機密ラベル
- 保持ラベル
- ファイル パス
- DLP ポリシー

アクティビティ エクスプローラーの使用に関する詳細なガイダンスについては、「アクティビティ エクスプローラーの概要」を参照 [してください](/microsoft-365/compliance/data-classification-activity-explorer)。

## <a name="next-steps"></a>次の手順

組織のコンプライアンス管理の基本を構成したので、Microsoft Purview で次のコンプライアンス ソリューションを検討し、機密情報を保護し、追加のインサイダー リスクを検出して対処できるようにします。

### <a name="configure-retention-labels"></a>保持ラベルを構成する

アイテム保持ポリシーはコンテナー レベルのすべてのアイテム (SharePoint サイト、ユーザー メールボックスなど) に自動的に適用されますが、 [保持ラベル](/microsoft-365/compliance/retention#retention-labels) は SharePoint ドキュメントや電子メール メッセージなどの個々のアイテムに適用されます。 これらのラベルは、手動または自動で適用できます。

保持ラベルは、必要なものを保持し、不要なものを削除するために、データ ガバナンス戦略の一部として使用できます。 これらのラベルは、特定のドキュメントまたはメールで異なる保持設定または削除設定が必要な場合に、アイテム保持ポリシーの例外が必要な場合に使用します。 たとえば、SharePoint ポリシーではすべてのドキュメントが 3 年間保持されますが、特定のビジネス ドキュメントは 5 年間保持する必要があります。 詳細については、「 [アイテム保持ポリシーに対する例外の保持ラベルを作成する」を参照してください](/microsoft-365/compliance/create-retention-labels-data-lifecycle-management)。

ただし、保持ラベルは、 [レコード管理](/microsoft-365/compliance/records-management)と共に使用する場合、アイテム レベルでドキュメントや電子メールをサポートするために、さらに多くの管理オプションを提供します。 このレベルのデータ管理は、ビジネス、法的、または規制上の記録保持要件の価値の高い項目に適しています。 詳細については、「 [レコード管理の概要](/microsoft-365/compliance/get-started-with-records-management)」を参照してください。

### <a name="identify-and-define-sensitive-information-types"></a>機密情報の種類を特定して定義する

組織のデータに含まれる情報に含まれるパターンに基づいて、機密情報の種類を定義します。 [組み込みの機密情報の種類を](./sensitive-information-type-entity-definitions.md)使用すると、クレジット カード番号、銀行口座番号、パスポート番号などを識別して保護できます。 または、組織に固有の [独自の秘密度情報の種類](/microsoft-365/compliance/create-a-custom-sensitive-information-type) を作成します。

カスタム機密情報の種類を定義するための詳細なガイダンスについては、「 [セキュリティ & コンプライアンス センターでカスタム機密情報の種類を作成](./create-a-custom-sensitive-information-type.md)する」を参照してください。

### <a name="prevent-data-loss"></a>データの損失を防止する

[Microsoft Purview データ損失防止 (DLP) ポリシー](/microsoft-365/compliance/dlp-learn-about-dlp) を使用すると、Microsoft 365 組織全体の機密情報を識別、監視、および自動的に保護できます。 DLP ポリシーを使用して、Microsoft サービス全体の機密アイテムを識別し、機密アイテムの偶発的な共有を防ぎ、ユーザーがワークフローを中断することなくコンプライアンスを維持する方法を学習できるようにします。

DLP ポリシーを構成するための詳細なガイダンスについては、DLP ポリシーの [作成、テスト、および調整を行います](/microsoft-365/compliance/create-test-tune-dlp-policy)。 データ損失管理のライセンス情報については、 [セキュリティ&コンプライアンスに関する Microsoft 365 ライセンス ガイダンスを](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#office-365-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business)参照してください。

### <a name="detect-and-act-on-insider-risks"></a>インサイダー リスクを検出して対処する

より多くの従業員が、さまざまなプラットフォームやサービスでデータを作成、管理、共有するためのアクセスを増やしています。 ほとんどの場合、組織には、組織全体のリスクを特定して軽減するためのリソースとツールが限られていますが、コンプライアンス要件と従業員のプライバシー基準も満たしています。 これらのリスクには、従業員の退職によるデータ盗難や、偶発的な過剰共有や悪意による組織外の情報のデータ漏えいが含まれる場合があります。

[Insider リスク管理](/microsoft-365/compliance/insider-risk-management-policies) では、サービスとサード パーティのインジケーターの全幅を使用して、リスクの高いユーザー アクティビティを迅速に特定、トリアージ、および行動するのに役立ちます。 Microsoft 365 および Microsoft Graph のログを使用することにより、インサイダー リスク管理では、特定のポリシーを定義してリスク指標を特定し、これらのリスクを軽減するためのアクションを実行できます。

インサイダー リスク管理ポリシーを計画および構成するための詳細なガイダンスについては、「 [インサイダー リスク管理の計画](/microsoft-365/compliance/insider-risk-management-plan) 」と「 [インサイダー リスク](/microsoft-365/compliance/insider-risk-management-configure)管理の概要」を参照してください。 インサイダー リスク管理のライセンス情報については、 [セキュリティ&コンプライアンスに関する Microsoft 365 ライセンス ガイダンスを](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#insider-risk-management)参照してください。
