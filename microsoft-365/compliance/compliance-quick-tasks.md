---
title: Microsoft 365 コンプライアンスを開始するためのクイック タスク
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- m365-security-compliance
- m365initiative-compliance
localization_priority: Normal
description: Microsoft 365 のコンプライアンスをすばやく開始するのに役立つタスクについて説明します。
ms.openlocfilehash: 36b6e2bd0d0339241748499826edf061a7259317
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928631"
---
# <a name="quick-tasks-for-getting-started-with-microsoft-365-compliance"></a>Microsoft 365 コンプライアンスを開始するためのクイック タスク

Microsoft 365 コンプライアンスを初め、どこから開始していけという疑問を持つ場合は、この記事で基本に関するガイダンスを提供し、重要なコンプライアンス タスクに優先順位を付ける方法について説明します。 この記事では、データの管理と監視、情報の保護、インサイダー リスクの最小化をすばやく開始するのに役立ちます。

この記事は、リスクの管理、データの保護、新しいリモートの従業員による規制や基準への準拠を維持する最善の方法を考える場合にも役立ちます。 従業員は新しい方法で共同作業を行い、互いに接続しています。つまり、既存のコンプライアンス プロセスとコントロールを適応する必要がある場合があります。 組織内でこれらの新しいコンプライアンス リスクを特定して管理するには、データを保護し、脅威とリスクを最小限に抑える上で重要です。

これらの基本的なコンプライアンス タスクを完了したら、追加の Microsoft 365 コンプライアンス ソリューションを実装して、組織のコンプライアンス対応範囲を拡大します。

## <a name="task-1-configure-compliance-permissions"></a>タスク 1: コンプライアンスのアクセス許可を構成する

コンテンツを表示して管理タスクを実行するには、組織内の誰が Microsoft 365 コンプライアンス センターにアクセスできるのか管理することが重要です。 Microsoft 365 は、コンプライアンスに固有の管理役割を提供し、Microsoft 365 コンプライアンス センターに含まれるツールを使用します。

まず、組織内のユーザーにコンプライアンスのアクセス許可を割り当て、これらのタスクを実行し、権限のないユーザーが自分の責任外の領域にアクセスするのを防ぐことから始める必要があります。 Microsoft 365 に含まれるコンプライアンス ソリューションの構成と実装を開始する前に、コンプライアンス データ管理者とコンプライアンス管理者の役割に適切なユーザーを割り当て済みである必要があります。 また、コンプライアンス マネージャーでデータを表示するには、Azure Active Directory グローバル リーダー ロールにユーザーを割り当てる必要があります。

アクセス許可を構成し、管理者の役割にユーザーを割り当てる手順については、「セキュリティ/コンプライアンス センター」の「アクセス許可 [&参照してください](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)。

## <a name="task-2-know-your-state-of-compliance"></a>タスク 2: コンプライアンスの状態を知る

自分の場所が分からない場合は、どこに行く必要なのかを知りにくいです。 コンプライアンスのニーズを満たすには、現在のレベルのリスクと、このような変化する時に必要になる可能性がある更新プログラムについて理解する必要があります。 組織がコンプライアンス要件を初めから使用する場合でも、業界を管理する標準や規制に関して深い経験を持っている場合でも、コンプライアンスを改善するためにできる唯一の最善の方法は、組織がどこに立っているのかを理解することです。

[Microsoft コンプライアンス マネージャーは](compliance-manager.md) 、組織のコンプライアンス体制を理解し、改善が必要な可能性がある分野を強調するのに役立ちます。 コンプライアンス マネージャーは、集中管理されたダッシュボードを使用してリスク ベースのスコアを計算し、データ保護と規制基準に関するリスクを減らすのに役立つアクションの完了の進捗状況を測定します。 コンプライアンス マネージャーをツールとして使用して、すべてのリスク評価を追跡することもできます。 このツールは、共通のツールを使用してリスク評価を効率的に完了するのに役立つワークフロー機能を提供します。

コンプライアンス マネージャーの使用を開始する手順については、「コンプライアンス マネージャーの使用を開始する」 [を参照してください](compliance-manager-setup.md)。

>[!IMPORTANT]
>セキュリティとコンプライアンスは、ほとんどの組織に緊密に統合されています。 セキュリティとコンプライアンスの両方に対する防御の詳細なアプローチを提供するために、組織が基本的なセキュリティ、脅威保護、ID およびアクセス管理領域に対応することが重要です。
>
>Microsoft [365](../security/mtp/microsoft-secure-score.md) セキュリティ センターで Microsoft 365 セキュア スコアを確認し、次の記事に示すタスクを完了します。
>
> - [セキュリティ ロードマップ - 最初の 30 日間、90 日間、およびそれ以降の優先事項](../security/office-365-security/security-roadmap.md)
> - [在宅勤務をサポートするセキュリティ チームの上位 12 のタスク](../security/top-security-tasks-for-remote-work.md)

## <a name="task-3-enable-auditing-for-your-organization"></a>タスク 3: 組織の監査を有効にする

組織の現在の状態とコンプライアンス機能を管理できるユーザーを決定しました。次の手順では、コンプライアンス調査を実施し、組織内のネットワークとユーザーのアクティビティに関するレポートを生成するデータを取得します。 監査を有効にすることが、この記事で後で説明するコンプライアンス ソリューションの重要な前提条件にもなっています。

監査ログによって提供される分析情報は、コンプライアンス要件をソリューションに適合するのに役立つツールであり、改善が必要なコンプライアンス領域の管理と監視に役立ちます。 アクティビティを記録する前、および監査ログを検索する前に、監査ログを有効にする必要があります。 有効にすると、組織のユーザーと管理者のアクティビティが監査ログに記録され、ユーザーに割り当てられたライセンスに応じて 90 日間、最大 1 年間保持されます。

監査を有効にする詳しい手順については、「監査ログ検索を有効またはオフにする」 [を参照してください](turn-audit-log-search-on-or-off.md)。

## <a name="task-4-create-policies-to-alert-you-about-potential-compliance-issues"></a>タスク 4: 潜在的なコンプライアンスの問題について警告するポリシーを作成する

Microsoft は、管理アクセス許可の不正使用、マルウェア アクティビティ、潜在的な外部および内部の脅威、および情報ガバナンスのリスクを特定するのに役立つ、いくつかの組み込みのアラート ポリシーを提供しています。 これらのポリシーは既定で有効になっていますが、組織固有のコンプライアンス要件の管理に役立つカスタムアラートの構成が必要な場合があります。

アラート ポリシーとアラート ダッシュボード ツールを使用して、カスタムアラート ポリシーを作成し、ユーザーがポリシー条件に一致するアクティビティを実行するときに生成されたアラートを表示します。 たとえば、アラート ポリシーを使用して、組織内のコンプライアンス要件、アクセス許可、およびデータ損失インシデントに影響を与えるユーザーと管理者のアクティビティを追跡する場合があります。

カスタムアラート ポリシーを作成する詳しい手順については、セキュリティ/コンプライアンス センターのアラート [ポリシーを参照してください](alert-policies.md)。

## <a name="task-5-classify-and-protect-sensitive-data"></a>タスク 5: 機密データを分類して保護する

組織の従業員は、業務を行うために組織内外の関係者と共同作業を行います。このためコンテンツはファイアウォールの内側だけでなく、さまざまなデバイス、アプリ、サービスを越えて存在することになります。この場合、組織のビジネス ポリシーとコンプライアンス ポリシーを満たす安全な方法でコンテンツを保護することが必要です。

[感度ラベルを](sensitivity-labels.md) 使用すると、組織のデータを分類して保護しながら、ユーザーの生産性と共同作業の能力が低下しないでお客様のデータを保護できます。 暗号化と使用の制限を適用するには、機度ラベルを使用して視覚的なマーキングを適用し、オンプレミスとクラウドのプラットフォームやデバイス間で情報を保護します。

感度ラベルを構成して使用する詳しい手順については、「ラベルの使用を開始する」 [を参照してください](get-started-with-sensitivity-labels.md)。 セキュリティとコンプライアンスに関する Microsoft [365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)ライセンス ガイダンスを参照して、&してください。

## <a name="task-6-configure-a-retention-policy"></a>タスク 6: アイテム保持ポリシーを構成する

アイテム [保持ポリシーを](retention.md) 使用すると、指定した保持期間の終わりにコンテンツを保持するか、コンテンツを削除するか、または両方を保持するか、その両方を事前に決定できます。 これらのアクションは、業界の規制や内部ポリシーに準拠し、訴訟やセキュリティ違反が発生した場合のリスクを軽減するために必要な場合があります。

コンテンツがアイテム保持ポリシーの対象になる場合、ユーザーは何も変更しない場合と同様に、コンテンツの編集と作業を続行できます。 コンテンツは元の場所に保持されます。 ただし、アイテム保持ポリシーの対象となるコンテンツを編集または削除した場合、元のコンテンツのコピーは、そのコンテンツのアイテム保持ポリシーが有効な間、そのコンテンツが保持される安全な場所に保存されます。

Exchange メール、SharePoint サイト、OneDrive アカウント、Microsoft 365 グループなど、Microsoft 365 環境内の複数の場所に対してアイテム保持ポリシーをすばやく設定できます。 このポリシーに自動的に含め可能なメールボックスまたはサイトの数に制限はありません。 ただし、より選択的に選択する必要がある場合は、特定の場所に対してアイテム保持ポリシーを構成し、サイトまたはユーザーを含めるか除外します。

アイテム保持ポリシーを構成する手順については、「アイテム保持ポリシーの作成と構成」 [を参照してください](create-retention-policies.md)。 Microsoft 365 で保持を構成するのが初めての場合は、「[アイテム保持ポリシーと保持ラベルの使用を開始する](get-started-with-retention.md)」を参照してください。

## <a name="task-7-configure-sensitive-information-and-offensive-language-policies"></a>タスク 7: 機密情報と不快言語ポリシーを構成する

機密情報を保護し、職場のハラスメント インシデントを検出して対応することが、内部のポリシーと基準を遵守する上で重要な部分です。 [](communication-compliance-feature-reference.md) Microsoft 365 の通信コンプライアンスは、電子メールと Microsoft Teams 通信の修復アクションをすばやく検出、キャプチャ、実行するのに役立ち、これらのリスクを最小限に抑えるのに役立ちます。 これには、不適切な情報、脅威、組織の内部と外部の機密情報を共有するメッセージや通信が含まれる不適切な通信が含まれます。

定義済みの不快言語とスパム対策ポリシー テンプレートを使用すると、ポリシーの一致について内部通信と外部通信をスキャンして、指定されたレビュー担当者が確認できます。 レビュー担当者は、組織内のスキャンされたメール、Microsoft Teams、Yammer、またはサード パーティの通信を調査し、適切な修復アクションを実行して、組織の標準に準拠している必要があります。

定義済みの機密情報ポリシーテンプレートを使用すると、定義済みの機密情報の種類またはキーワードを含む電子メールと Microsoft Teams 通信をスキャンするポリシーをすばやく作成し、重要なデータがアクセスできないユーザーと共有されるのを確実にするのに役立ちます。 これらの活動には、機密プロジェクトに関する不正な通信や、インサイダー取引や他の部下活動に関する業界固有のルールが含まれる可能性があります。

通信コンプライアンスを計画および構成する手順については、「通信コンプライアンスの計画」[](communication-compliance-plan.md)と「通信コンプライアンスの開始[」を参照してください](communication-compliance-configure.md)。 通信コンプライアンスのライセンス情報については、セキュリティとコンプライアンスに関する [Microsoft 365 ライセンス ガイダンス&覧ください](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-compliance)。

## <a name="task-8-see-whats-happening-with-your-sensitive-items"></a>タスク 8: 機密性の高いアイテムの処理を確認する

機密ラベル、機密情報の種類、保持ラベルとポリシー、およびトレーニング可能な分類子を使用して、Exchange、SharePoint、OneDrive 全体の機密アイテムを前のタスクで確認した方法で分類およびラベル付けできます。 クイック タスクの手順の最後の手順は、ラベルが付けられているアイテムと、ユーザーが機密アイテムに対して行っているアクションを確認する手順です。 [コンテンツ エクスプローラーと](data-classification-content-explorer.md)[アクティビティ エクスプローラーによって](data-classification-activity-explorer.md)、この可視性が提供されます。

### <a name="content-explorer"></a>コンテンツ エクスプローラー
 コンテンツ エクスプローラーを使用すると、機密情報の種類として分類された、またはトレーニング可能な分類子によって特定の分類に属しているすべてのアイテムと、機密ラベルまたは保持ラベルが適用されているすべてのアイテムをネイティブ形式で表示できます。

コンテンツ エクスプローラーを使用する手順については、「データを知る [-](data-classification-overview.md)データ分類の概要」および「コンテンツ エクスプローラーの使用を開始する」を [参照してください](data-classification-content-explorer.md)。

### <a name="activity-explorer"></a>アクティビティ エクスプローラー
アクティビティ エクスプローラーは、機密アイテムとラベル付けされた機密アイテムの実行を監視するのに役立ちます。
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

アクティビティ エクスプローラーを使用する手順については、「アクティビティ エクスプローラーの使用を開始する [」を参照してください](data-classification-activity-explorer.md)。

## <a name="next-steps"></a>次の手順

組織のコンプライアンス管理の基本を構成しました。次に、機密情報を保護し、追加のインサイダー リスクを検出して操作するのに役立つ Microsoft 365 のコンプライアンス ソリューションを検討します。

### <a name="configure-retention-labels"></a>保持ラベルを構成する

アイテム保持ポリシーは、SharePoint サイトや Exchange メールボックスなどの場所にコンテナー レベルで適用[](retention.md#retention-labels)しますが、保持ラベルを使用すると、保持ポリシーと削除ポリシーに対するより具体的なターゲット設定が可能になります。 たとえば、管理者による自動アプリケーションに加えて、エンド ユーザーが手動で適用できるドキュメントまたは電子メール メッセージ レベルなどです。 また、SharePoint のドキュメント ライブラリ、フォルダー、またはドキュメント セットに保持ラベルを適用して、その場所に保存されているドキュメントすべてが既定の保持ラベルを継承することもできます。

さらに、保持ラベルは、コンテンツ [をレコードとして](records-management.md) マークするレコード管理をサポートします。 このような場合、ラベルは、組織が規制要件に準拠するために必要になる可能性があるコンテンツに対して追加の制限を適用します。

保持ラベルを作成および発行する手順については、次のガイダンスを参照してください。
- [アイテム保持ラベルを作成してアプリに適用する](create-apply-retention-labels.md)
- [保持ラベルをコンテンツに自動的に適用する](apply-retention-labels-automatically.md)

レコード管理を開始するには、「レコード管理の開始 [」を参照してください](get-started-with-records-management.md)。

### <a name="identify-and-define-sensitive-information-types"></a>機密情報の種類を特定して定義する

組織のデータの情報に含まれるパターンに基づいて、機密情報の種類を定義します。 組 [み込みの機密情報の種類を](what-the-sensitive-information-types-look-for.md) 使用すると、クレジット カード番号、銀行口座番号、パスポート番号などの識別と保護に役立ちます。 または、組織に固有 [の独自のカスタム](create-a-custom-sensitive-information-type.md) の感度情報の種類を作成します。

カスタムの機密情報の種類を定義する詳しい手順については、「セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を作成する [&参照してください](https://docs.microsoft.com/microsoft-365/compliance/create-a-custom-sensitive-information-type)。

### <a name="prevent-data-loss"></a>データの損失を防止する

[データ損失防止 (DLP)](data-loss-prevention-policies.md) ポリシーを使用すると、Microsoft 365 組織全体の機密情報を特定、監視、および自動的に保護できます。 DLP ポリシーを使用して、Microsoft サービス全体で機密性の高いアイテムを識別し、機密性の高いアイテムが誤って共有されるのを防ぎ、ユーザーがワークフローを中断せずに準拠を維持する方法を学習するのに役立ちます。

DLP ポリシーの構成、DLP ポリシーの作成、テスト、調整を行う [手順について説明します](create-test-tune-dlp-policy.md)。 データ損失管理のライセンス情報については、セキュリティとコンプライアンスに関する [Microsoft 365 ライセンス &参照してください](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#office-365-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business)。

### <a name="detect-and-act-on-insider-risks"></a>インサイダー リスクの検出と対応

ますます多くの従業員が、広範なプラットフォームとサービスでデータを作成、管理、および共有するためのアクセスを増やしています。 ほとんどの場合、組織には、コンプライアンス要件と従業員のプライバシー基準を満たす一方で、組織全体のリスクを特定および軽減するためのリソースとツールが限られています。 このようなリスクには、不当な従業員によるデータの盗難や、偶発的な過剰共有や悪意による組織外の情報のデータ漏洩が含まれる場合があります。

[](insider-risk-management-policies.md) Microsoft 365 のインサイダー リスク管理では、サービスとサードパーティのインジケーターを使用して、リスクの高いユーザー アクティビティをすばやく特定、トリアージ、および行動するのに役立ちます。 Microsoft 365 と Microsoft Graph のログを使用すると、インサイダー リスク管理を使用して、リスク インジケーターを特定し、これらのリスクを軽減するためのアクションを実行する特定のポリシーを定義できます。

インサイダー リスク管理ポリシーを計画および構成する手順については、「インサイダー[](insider-risk-management-plan.md)リスク管理を計画する」および「インサイダー リスク管理の概要」を[参照してください](insider-risk-management-configure.md)。 インサイダー リスク管理のライセンス情報については、セキュリティとコンプライアンスに関する [Microsoft 365 ライセンス ガイダンス&覧ください](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#insider-risk-management)。
