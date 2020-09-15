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
- M365-security-compliance
localization_priority: Normal
description: Microsoft 365 のコンプライアンスをすばやく始めるのに役立つタスクについて説明します。
ms.openlocfilehash: 1702c05b271c0e8b5456c1a93f8bf1dc28f7fbd9
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "47816816"
---
# <a name="quick-tasks-for-getting-started-with-microsoft-365-compliance"></a>Microsoft 365 コンプライアンスを開始するためのクイック タスク

Microsoft 365 へのコンプライアンスと、重要なコンプライアンスタスクの優先順位を作成する方法については、この記事で説明しています。 この記事では、データの管理と監視、情報の保護、および insider のリスクの最小化をすぐに始めることができます。

この記事は、リスクの管理、データの保護、および新たにリモートの従業員との規制や基準への準拠を維持するのに最適な方法をお探しの場合にも役立ちます。 新しい方法で従業員が相互に連携して相互に接続されるようになったため、既存のコンプライアンスプロセスや統制が適応しなければならない可能性があります。 組織内でこれらの新しいコンプライアンスリスクを特定して管理することは、データを保護し、脅威とリスクを最小限に抑えるために不可欠です。

これらの基本的なコンプライアンスタスクを完了した後、追加の Microsoft 365 コンプライアンスソリューションを実装して、組織内のコンプライアンスの範囲を拡張することを検討します。

## <a name="task-1-configure-compliance-permissions"></a>タスク 1: コンプライアンス権限を構成する

コンテンツを表示して管理タスクを実行するには、組織内の誰が Microsoft 365 コンプライアンスセンターにアクセスできるかを管理することが重要です。 Microsoft 365 は、コンプライアンスに固有の管理役割を提供し、Microsoft 365 コンプライアンスセンターに含まれるツールを使用します。

最初に、組織内のユーザーにコンプライアンスアクセス許可を割り当てて、これらのタスクを実行できるようにし、権限のないユーザーが自分の責任の範囲外の領域にアクセスできないようにします。 Microsoft 365 に含まれるコンプライアンスソリューションの構成と実装を開始する前に、 **コンプライアンスデータ管理者** およびコンプライアンス **管理者** の管理者ロールに適切なユーザーが割り当てられていることを確認してください。 また、コンプライアンススコアのデータを表示するには、Azure Active Directory のグローバル閲覧者ロールにユーザーを割り当てる必要があります。

アクセス許可を構成し、ユーザーを管理者の役割に割り当てる詳細な手順については、「 [セキュリティ & コンプライアンスセンターのアクセス許可](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)」を参照してください。

## <a name="task-2-know-your-state-of-compliance"></a>作業 2: コンプライアンスの状態を把握する

どこにいるかわからない場合は、どこに移動するかを知るのは困難です。 コンプライアンスのニーズに対応するには、現在のリスクレベルと、このように変化したときに必要になる可能性のある更新プログラムについて理解する必要があります。 組織が法令遵守の要件に対して新しいものであるか、業界を管理する標準や規制に関する深い実績があるかどうかにかかわらず、コンプライアンスを向上させるための単一の最良の方法は、組織の現状を理解することです。

[Microsoft コンプライアンススコア](compliance-score.md) は、組織のコンプライアンスについて理解し、改善が必要になる可能性がある分野を強調するために役立ちます。 コンプライアンススコアは、集中管理されたダッシュボードを使用してリスクベースのスコアを計算し、データ保護と規制基準に関するリスクを軽減するために実行される操作の完了を測定します。 コンプライアンススコアをツールとして使用して、すべてのリスク評価を追跡することもできます。 これにより、一般的なツールを使用してリスク評価を効率的に完了できるようにするためのワークフロー機能が提供されます。

コンプライアンススコアの使用を開始する手順については、「 [コンプライアンススコアの設定](compliance-score-setup.md)」を参照してください。

>[!IMPORTANT]
>セキュリティとコンプライアンスは、ほとんどの組織に密接に統合されています。 セキュリティとコンプライアンスの両方に対して多層防御のアプローチを提供するために、組織では、基本的なセキュリティ、脅威の保護、および id とアクセスの管理領域に対応することが重要です。
>
>Microsoft 365 セキュリティセンターの [microsoft 365 セキュリティスコア](../security/mtp/microsoft-secure-score.md) をチェックし、次の記事で説明されているタスクを完了します。
>
> - [セキュリティロードマップ-最初の30日間、90日以降の優先度](../security/office-365-security/security-roadmap.md)
> - [自宅からの作業をサポートするためのセキュリティチームのトップ12タスク](../security/top-security-tasks-for-remote-work.md)

## <a name="task-3-enable-auditing-for-your-organization"></a>作業 3: 組織の監査を有効にする

組織の現在の状態とコンプライアンス機能を管理できるユーザーを決定したので、次の手順として、コンプライアンス調査を実施し、組織内のネットワークおよびユーザーアクティビティに関するレポートを生成するためのデータがあることを確認します。 監査を有効にすることは、この記事で後述するコンプライアンスソリューションにとって重要な前提条件となります。

監査ログによって提供される洞察は、コンプライアンスの要件を、改善する必要のあるコンプライアンス領域の管理と監視に役立つソリューションに適合させるために役立つツールです。 監査ログを有効にしてから、監査ログを検索する前に、アクティビティを記録しておく必要があります。 有効にすると、組織のユーザーおよび管理者のアクティビティが監査ログに記録され、ユーザーに割り当てられているライセンスに応じて、90日間、および最大1年間保持されます。

監査を有効にするための詳細な手順について [は、「監査ログの検索を有効または無効](turn-audit-log-search-on-or-off.md)にする」を参照してください。

## <a name="task-4-create-policies-to-alert-you-about-potential-compliance-issues"></a>タスク 4: 潜在的なコンプライアンス問題について警告するポリシーを作成する

Microsoft では、管理者アクセス許可の悪用、マルウェアアクティビティ、外部および内部の脅威、および情報ガバナンスのリスクを特定するのに役立ついくつかの組み込み通知ポリシーを提供しています。 これらのポリシーは既定で有効になっていますが、組織固有のコンプライアンス要件を管理するためにカスタム通知を構成する必要がある場合があります。

アラートポリシーとアラートダッシュボードツールを使用して、カスタム通知ポリシーを作成し、そのポリシー条件に一致するアクティビティをユーザーが実行したときに生成されるアラートを表示します。 通知ポリシーを使用して、組織内のコンプライアンス要件、アクセス許可、データ損失のインシデントに影響するユーザーおよび管理者のアクティビティを追跡することもできます。

カスタム通知ポリシーを作成するためのステップバイステップのガイダンスについて [は、「セキュリティ/コンプライアンスセンターのアラートポリシー](alert-policies.md)」を参照してください。

## <a name="task-5-configure-just-in-time-access-for-your-administrators"></a>作業 5: 管理者に対してジャストインタイムアクセスを構成する

一部のユーザーに機密情報や重要なネットワーク構成設定へのアクセスを許可することは、侵害されたアカウントまたは内部の脅威のアクティビティに対して潜在的な経路です。 [特権アクセス管理](privileged-access-management-overview.md) は、機密データへのアクセスを制限したり、重要な構成設定にアクセスしたりすることによって、違反から組織を保護し、コンプライアンスのベストプラクティスに準拠するために役に立ちます。 管理者が継続的にアクセスするのではなく、管理者特権を必要とするタスクに対してジャストインタイムのアクセスルールが実装されています。 Microsoft 365 で特権アクセス管理を有効にすることで、組織はゼロに立った権限で運用し、管理者アクセスの脆弱性に対する防御層を提供できます。

特権アクセス管理を構成するためのステップごとのガイダンスについては、「 [特権アクセス管理の概要](privileged-access-management-configuration.md)」を参照してください。 特権アクセス管理のライセンス情報については、「 [Microsoft 365 licensing ガイダンス for security & 法令遵守](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#privileged-access-management-in-office-365)」を参照してください。

## <a name="task-6-classify-and-protect-sensitive-data"></a>作業 6: 機密データを分類して保護する

組織の従業員は、業務を行うために組織内外の関係者と共同作業を行います。このためコンテンツはファイアウォールの内側だけでなく、さまざまなデバイス、アプリ、サービスを越えて存在することになります。この場合、組織のビジネス ポリシーとコンプライアンス ポリシーを満たす安全な方法でコンテンツを保護することが必要です。

[機密ラベル](sensitivity-labels.md) を使用すると、組織のデータを分類して保護すると同時に、ユーザーの生産性とその機能の連携が妨げられないようにすることができます。 機密ラベルを使用して暗号化と使用制限を適用する。視覚的マーキングを適用し、プラットフォームとデバイス、社内およびクラウドの間で情報を保護します。

機密ラベルを構成して使用するための詳細なガイダンスについては、「まず、 [機密ラベルの概要](get-started-with-sensitivity-labels.md)」を参照してください。 機密ラベルライセンス情報については、「 [Microsoft 365 licensing ガイダンス for security & 法令遵守](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)」を参照してください。

## <a name="task-7-configure-a-retention-policy"></a>タスク 7: アイテム保持ポリシーを構成する

[アイテム保持ポリシー](retention.md)を使用すると、コンテンツを保持するか、コンテンツを削除するか、またはその両方を事前に決定して、指定した保持期間の最後にコンテンツを保持して削除することができます。 これらのアクションは、業界の規制や内部ポリシーに準拠し、訴訟やセキュリティ違反の発生時にリスクを軽減するために必要な場合があります。

コンテンツがアイテム保持ポリシーの対象となる場合は、何も変更されていない場合と同様に、コンテンツの編集や操作を続けることができます。 コンテンツは、元の場所に保持されます。 ただし、ユーザーがアイテム保持ポリシーの対象となるコンテンツを編集または削除すると、元のコンテンツのコピーが、そのコンテンツのアイテム保持ポリシーが有効になっている間に保持される安全な場所に保存されます。

Exchange メール、SharePoint サイト、OneDrive アカウント、Microsoft 365 グループなど、Microsoft 365 環境の複数の場所に対して、アイテム保持ポリシーをすばやく配置することができます。 このポリシーに自動的に含めることができるメールボックスまたはサイトの数に制限はありません。 ただし、選択をさらに強化する必要がある場合は、特定の場所のアイテム保持ポリシーを構成し、サイトまたはユーザーを含めたり、除外したりできます。

アイテム保持ポリシーを構成する詳細な手順については、「 [アイテム保持ポリシーを作成および構成](create-retention-policies.md)する」を参照してください。 Microsoft 365 で保持を構成するのが初めての場合は、「[アイテム保持ポリシーと保持ラベルの使用を開始する](get-started-with-retention.md)」を参照してください。

## <a name="task-8-configure-sensitive-information-and-offensive-language-policies"></a>タスク 8: 機密情報と不快な言語ポリシーを構成する

機密情報の保護と workplace 嫌がらせインシデントの検出と処理は、内部ポリシーおよび標準への準拠の重要な部分です。 Microsoft 365 の[コミュニケーションコンプライアンス](communication-compliance-feature-reference.md)では、電子メールと Microsoft Teams 通信の修復措置を迅速に検出、取得、および実行できるようにすることで、これらのリスクを最小限に抑えることができます。 これには、プロファニティ、脅威、嫌がらせ、および組織の内部および外部の機密情報を共有する通信を含む不適切なコミュニケーションが含まれます。

事前に定義された不快な言葉 *と嫌がらせ対策* のポリシーテンプレートを使用すると、ポリシーの一致に関する内部通信と外部通信をスキャンして、指定したレビュー担当者がそれらを調査できるようにすることができます。 レビューアーは、スキャンされた電子メール、Microsoft Teams、Yammer、または組織内のサードパーティの通信を調査し、適切な修復処置を行って、組織の標準に準拠していることを確認できます。

事前に定義された *機密情報* ポリシーテンプレートを使用すると、定義された機密情報の種類やキーワードを含む電子メールや Microsoft Teams 通信をスキャンするポリシーをすばやく作成することができ、重要なデータがアクセスを必要としない人と共有されないようにするのに役立ちます。 これらのアクティビティには、内部者取引またはその他の collusion 活動に関する機密プロジェクトや業界固有のルールに関する、承認されていない通信が含まれる可能性があります。

通信のコンプライアンスを計画して構成するための詳細なガイダンスについては、「 [plan for communication コンプライアンス](communication-compliance-plan.md) 」と「 [コミュニケーションを開始](communication-compliance-configure.md)する」を参照してください。 通信コンプライアンスライセンスの情報については、「 [Microsoft 365 licensing ガイダンス for security & 法令遵守](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-compliance)」を参照してください。

## <a name="task-9-see-whats-happening-with-your-sensitive-items"></a>タスク 9: 機密アイテムの処理状況を確認する

機密ラベル、機密情報の種類、アイテム保持ラベル、および trainable 分類子を使用すると、前のタスクで見たように、Exchange、SharePoint、OneDrive 間で機密アイテムの分類とラベル付けを行うことができます。 クイックタスクへの移行の最後の手順では、ラベル付けされたアイテム、およびそれらの機密アイテムに対してユーザーが実行しているアクションを確認します。 この可視性は、[コンテンツエクスプローラー](data-classification-content-explorer.md)と[アクティビティエクスプローラー](data-classification-activity-explorer.md)によって提供されます。

### <a name="content-explorer"></a>コンテンツ エクスプローラー
 コンテンツエクスプローラーを使用すると、機密情報の種類として分類されたすべてのアイテム、または trainable 分類子によって特定の分類に分類されたすべてのアイテム、および感度解析または保持ラベルが適用されているすべてのアイテムをネイティブ形式で表示できます。

コンテンツエクスプローラーを使用するための詳細なガイダンスについては、「 [データのデータ分類の概要](data-classification-overview.md)」と「 [コンテンツエクスプローラーを使い始める](data-classification-content-explorer.md)」を参照してください。

### <a name="activity-explorer"></a>アクティビティ エクスプローラー
アクティビティエクスプローラーを使用すると、分類済みでラベル付けされた機密アイテムに対して行われた処理を監視することができます。
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

アクティビティエクスプローラーを使用する詳細な手順については、「 [アクティビティエクスプローラーの概要](data-classification-activity-explorer.md)」を参照してください。

## <a name="next-steps"></a>次の手順

これで、組織のコンプライアンス管理の基本が構成されました。機密情報を保護し、その他の insider のリスクを検出して操作するために役立つ、Microsoft 365 の以下のコンプライアンスソリューションを検討してください。

### <a name="configure-retention-labels"></a>保持ラベルを構成する

保持ポリシーは、SharePoint サイトや Exchange メールボックスなどの場所にコンテナーレベルで適用されますが、保持 [ラベル](retention.md#retention-labels) を使用すると、保持ポリシーと削除ポリシーにより具体的な対象化を行うことができます。 たとえば、ドキュメントまたは電子メールメッセージレベルでは、エンドユーザーは管理者による自動アプリケーションに加えて手動で適用することができます。 また、SharePoint のドキュメントライブラリ、フォルダー、またはドキュメントセットに保持ラベルを適用して、その場所に格納されているすべてのドキュメントが既定の保持ラベルを継承するようにすることもできます。

さらに、保持ラベルは、レコード [管理](records-management.md) をサポートして、コンテンツをレコードとしてマークします。 これが発生すると、組織が規制要件に準拠するために必要になる可能性があるコンテンツに、ラベルによって追加の制限が課されます。

保持ラベルを作成して発行する詳細な手順については、以下のガイダンスを参照してください。
- [アイテム保持ラベルを作成してアプリに適用する](create-apply-retention-labels.md)
- [保持ラベルをコンテンツに自動的に適用する](apply-retention-labels-automatically.md)

レコード管理の概要については、「 [レコード管理の概要](get-started-with-records-management.md)」を参照してください。

### <a name="identify-and-define-sensitive-information-types"></a>機密情報の種類を識別して定義する

組織のデータ内の情報に含まれるパターンに基づいて、機密情報の種類を定義します。 [組み込みの機密情報の種類](what-the-sensitive-information-types-look-for.md)を使用することで、クレジットカード番号、銀行口座番号、パスポート番号などを識別し、保護することができます。 または、組織に固有の [カスタムの機密情報の種類](custom-sensitive-info-types.md) を作成します。

カスタムの機密情報の種類を定義するための詳細なガイダンスについては、「 [セキュリティ & コンプライアンスセンターでカスタムの機密情報の種類を作成](https://docs.microsoft.com/microsoft-365/compliance/create-a-custom-sensitive-information-type)する」を参照してください。

### <a name="prevent-data-loss"></a>データの損失を防止する

[データ損失防止 (DLP) ポリシー](data-loss-prevention-policies.md) を使用すると、Microsoft 365 組織全体の機密情報を識別、監視、および自動保護することができます。 DLP ポリシーを使用して、Microsoft サービス全体の機密アイテムを識別し、機密性の高いアイテムが偶発的に共有されないようにし、ワークフローを中断せずに準拠を維持する方法をユーザーが理解できるようにします。

DLP ポリシーを構成するためのステップごとのガイダンスについては、「 [dlp ポリシーの推奨事項の概要](get-started-with-dlp-policy-recommendations.md) 」と「 [既定の dlp ポリシーの概要](get-started-with-the-default-dlp-policy.md)」を参照してください。 データ損失管理のライセンス情報については、「 [Microsoft 365 licensing ガイダンス for security & 法令遵守](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#office-365-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business)」を参照してください。

### <a name="detect-and-act-on-insider-risks"></a>Insider のリスクを検出して操作する

多くの従業員は、さまざまなプラットフォームとサービスにわたってデータを作成、管理、共有するためのアクセスが向上しています。 ほとんどの場合、組織には、コンプライアンス要件と従業員のプライバシー基準を満たす一方で、組織全体のリスクを特定して軽減するためのリソースとツールが制限されています。 これらのリスクには、偶発的な共有または悪意のある意図により、従業員や組織外の情報のデータ漏洩によってデータが盗まれることがあります。

Microsoft 365 の[Insider リスク管理](insider-risk-management-policies.md)では、すべてのサービスとサードパーティのインジケーターが使用され、リスクの高いユーザーアクティビティをすばやく特定、トリアージ、および操作することができます。 Microsoft 365 および Microsoft Graph のログを使用することにより、insider リスク管理では、リスク指標を識別し、これらのリスクを軽減するアクションを実行する特定のポリシーを定義できます。

Insider リスク管理ポリシーの計画と構成の詳細な手順については、「 [plan for insider リスク管理](insider-risk-management-plan.md) 」と「 [insider リスク管理の概要](insider-risk-management-configure.md)」を参照してください。 Insider リスク管理のライセンス情報については、「 [Microsoft 365 licensing ガイダンス for security & 法令遵守](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#insider-risk-management)」を参照してください。
