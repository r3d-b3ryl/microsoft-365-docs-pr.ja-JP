---
title: データプライバシー規制の対象となる情報を保護する
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Microsoft 365 のセキュリティ機能とコンプライアンス機能を展開し、個人情報を保護します。
ms.openlocfilehash: 2d3a5baa063e6672760dda60ae6d76ea928ccd16
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500984"
---
# <a name="protect-information-subject-to-data-privacy-regulation"></a>データプライバシー規制の対象となる情報を保護する

データ プライバシーコンプライアンスのニーズと規制に対応するために、サブスクリプションで多数の情報保護制御を使用できます。 これには、一般データ保護規則 (GDPR)、HIPAA-HITECH (米国の医療プライバシー法)、カリフォルニア州消費者保護法 (CCPA)、ブラジルデータ保護法 (LGPD) が含まれます。

これらのコントロールは、次のソリューション領域内に含まれます。

- 秘密度ラベル
- データ損失防止 (DLP)
- Office のメッセージの暗号化 (OME)
- Teams とサイトのアクセス制御

![データプライバシー規制の対象となる個人情報を保護するための主要なサービス](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-grid.png)

>[!Note]
>このソリューションでは、データプライバシー規制の対象となる情報を保護するためのセキュリティおよびコンプライアンス機能について説明します。 Microsoft 365 のセキュリティ機能の完全な一覧については [、「Microsoft 365](../security/index.yml)セキュリティドキュメント」を参照してください。 Microsoft 365 のコンプライアンス機能の完全な一覧については [、「Microsoft 365](../compliance/index.yml)コンプライアンスドキュメント」を参照してください。
>

## <a name="data-privacy-regulations-that-impact-information-protection-controls"></a>情報保護管理に影響を与えるデータプライバシー規制

情報保護制御に関連する可能性があるデータプライバシー規制のサンプル リストを次に示します。

- GDPR 記事 5(1)(f))
- GDPR に関する記事 (32)(1)(a)
- LGPD 第 46 条
- HIPAA-HITECH (45 CFR 164.312(e)(1))
- HIPAA-HITECH (45 C.F.R. 164.312(e)(2)(ii))

上記の [各詳細については、「データのプライバシーリスク](information-protection-deploy-assess.md) を評価し、機密性の高いアイテムを特定する」の記事を参照してください。

情報保護に関するデータプライバシーに関する規制は、次の方法をお勧めします。

- 紛失または不正アクセス、利用状況、または送信に対する保護。
- 保護メカニズムのリスクベースの適用。
- 必要に応じて暗号化を使用します。

組織では、他のコンプライアンスニーズやビジネス上の理由など、他の目的で Microsoft 365 コンテンツを保護することもできます。 データプライバシーのための情報保護スキームの確立は、全体的な情報保護計画、実装、および管理の一環として行う必要があります。

Microsoft 365 の情報保護スキームを開始するために、次のセクションでは、Microsoft 365 の関連機能と改善アクションの短い一覧を示します。 一覧には、データプライバシー規制に適用される機能と改善アクションが含まれています。 ただし、古いテクノロジよりも大きく置き換える新しい機能がある場合、このリストには古いテクノロジは含めされません。 たとえば、SharePoint および OneDrive の Information Rights Management (IRM) はリストに含まれていませんが、感度ラベルが含まれています。

## <a name="managing-information-protection-in-microsoft-365"></a>Microsoft 365 での情報保護の管理

Microsoft [の情報保護ソリューションには](../compliance/information-protection.md) 、Microsoft 365、Microsoft Azure、Microsoft Windows の複数の統合機能が含まれます。 Microsoft 365 では、情報保護ソリューションには次のものが含まれます。

- [カスタマー キーによるサービスの暗号化](../compliance/customer-key-overview.md)
- [機密情報の種類](../compliance/sensitive-information-type-entity-definitions.md)(データプライバシーリスクの評価と機密アイテムの識別に関する記事[で説明)](information-protection-deploy-assess.md)
- [秘密度ラベル](../compliance/sensitivity-labels.md) 
  - サービス/コンテナー レベル
  - クライアント側/コンテンツ レベル
  - SharePoint と OneDrive のデータ保存用に自動化
- データ損失防止 (DLP)
- [Microsoft 365 Endpoint データ損失防止](../compliance/endpoint-dlp-learn-about.md)
- [Office 365 メッセージ暗号化の新機能 (OME)](../compliance/ome.md) と OME [Advanced Message Encryption](../compliance/ome-advanced-message-encryption.md)

さらに、サイトおよびライブラリ レベルの保護は、任意の保護スキームに含める重要なメカニズムです。

Microsoft 365 以外の他の情報保護機能の詳細については、以下を参照してください。

- [Microsoft Cloud Application Security (MCAS)](/cloud-app-security/)
- [Azure Information Protection](/azure/information-protection/what-is-information-protection)
- [Microsoft エンドポイント マネージャー](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)
- [Windows 情報保護](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)

## <a name="sensitivity-labels"></a>秘密度ラベル

Microsoft Information Protection フレームワークの感度ラベルを使用すると、ユーザーの生産性と共同作業能力を妨げることなく、組織のデータを分類して保護できます。

> [!div class="mx-imgBorder"]
> ![Microsoft 365 の感度ラベル](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-labels.png)

### <a name="prerequisites-for-sensitivity-labels"></a>感度ラベルの前提条件

以下に示す感度ラベル ベースの機能を実装する前に、これらのアクティビティを完了します。

1. 次の情報を理解します。
   - **ビジネス要件。** 企業に感度ラベルを適用するビジネス上の理由を確立します。 たとえば、情報保護のためのデータ プライバシー要件。
   - **感度ラベルの機能。** 感度ラベル付けは複雑になりますので、作業を始める[](../compliance/sensitivity-labels.md)前に、必ず感度ラベルのドキュメントを読んでおく必要があります。
   - **覚えておく必要の重要なポイント** 感度ラベルは Microsoft コンプライアンス管理センターで管理されますが、ターゲット設定とアプリケーションのオプションは大きく異なります。
      - コンテナー レベルには、サイト、グループ、および Teams の感度ラベルがあります (設定はコンテナー内のコンテンツには適用されません)。 これらは、サイト、グループ、またはチームの準備時に適用するユーザーおよびグループに公開されます。
      - アクティブ なコンテンツには、感度ラベルがあります。 これらは、手動で適用するか、次の場合に自動的に適用されるユーザーまたはグループにも公開されます。
        - ファイルは、ユーザーのデスクトップまたは SharePoint サイトに対して開き、編集、保存されます。
        - メールが下書きされ、送信されます。
      - Exchange 経由で転送中のメールに加えて、SharePoint および OneDrive で保存中のファイルに対する自動アプリケーションの感度ラベルがあります。 これらは、すべてのサイトまたは特定のサイトを対象とし、これらの環境で保存されているファイルに自動的に適用されます。

2. 過去または別の方法で現在の感度ラベルを合理化する

   - Azure Information Protection

      現在の感度ラベル付けスキームは、既存の [Azure Information Protection](../compliance/sensitivity-labels.md#sensitivity-labels-and-azure-information-protection) ラベル付け実装と調整する必要がある場合があります。
   - OME

      電子メール保護に最新の感度ラベル付けを使用する予定で、OME のような既存の電子メール暗号化方法を使用する場合は、同じ機能を使用できますが、どちらを適用するかのシナリオを理解する必要があります。 最新のOfficeタイプの保護と OME ベースの保護を比較する表を含む、365 Message Encryption の新機能 [(OME)](#office-365-message-encryption-ome-new-capabilities)を参照してください。

3. より広範な情報保護スキームへの統合を計画します。 OME との共存の上に、Microsoft 365 データ損失防止 (DLP) や Microsoft Cloud App Security など、一方で感度ラベルを使用できます。 データプライバシー関連の情報保護の目標を達成するには [、「Microsoft 365](../compliance/information-protection.md) の Microsoft Information Protection」を参照してください。

4. 感度ラベルの分類と制御スキームを開発します。 「 [データ分類と感度ラベル分類」を参照してください](https://aka.ms/dataclassificationwhitepaper)。

### <a name="general-guidance"></a>一般的なガイダンス

1. **スキーマ定義。** 技術的な機能を使用してラベルと保護を適用する前に、組織全体で作業して分類スキーマを定義します。 分類スキーマが既に存在する可能性があります。これにより、個人データの追加が容易になります。 
2. **開始します。** まず、実装するラベルの数と名前を決定します。 どのテクノロジを使用し、ラベルを適用する方法を気にすることなく、このアクティビティを実行します。 オンプレミスや他のクラウド サービスに存在するデータを含め、組織全体でこのスキーマを汎用的に適用します。
3. **その他の推奨事項** ポリシー、ラベル、および条件を設計および実装する場合は、次の推奨事項を検討してください。

   - **既存の分類スキーマを使用します (必要な場合)。** 多くの組織では、何らかの形式でデータ分類が既に使用されています。 既存のラベル スキーマを慎重に評価し、可能であれば、このスキーマを使用します。 エンド ユーザーが認識できる使い慣れたラベルを使用すると、導入が促進されます。
   - **小さく開始します。** 作成できるラベルの数には、事実上制限はありません。 ただし、多数のラベルとサブラベルは導入が遅くなる可能性があります。
   - **シナリオと使用例を使用します。** 組織内の一般的な使用例を特定し、対象となるデータ プライバシー規制から派生したシナリオを使用します。 想定されるラベルと分類の構成が実際に機能する場合に確認します。
   - **新しいラベルのすべての要求に質問します。** すべてのシナリオまたは使用例に新しいラベルが本当に必要か、既に使用しているラベルを使用できますか? ラベルの数を最小限に抑え、導入を改善します。
   - **主要な部署にはサブラベルを使用します。** 一部の部署では、特定のラベルを必要とする特定のニーズがあります。 これらのラベルを既存のラベルのサブラベルとして定義し、グローバルではなくユーザー グループに割り当てられたスコープポリシーの使用を検討します。
   - **スコープ付きポリシーを検討します。** ユーザーのサブセットを対象としたポリシーは、ラベルのオーバーロードを防止します。 スコープ付きポリシーを使用すると、役割または部署固有のラベルまたはサブラベルを、その特定の部署で働く従業員に割り当てできます。 
   - **わかりやすいラベル名を使用します。** ラベル名として専門用語、標準語、頭字語を使用しない。 エンド ユーザーに響く名前を使用して、導入を改善してください。 PII、PCI、HIPAA、LBI、MBI、HBI のようなラベルを使用する代わりに、Non-Business、Public、General、Confidential、Highly Confidential のような名前を検討してください。

### <a name="create-and-deploy-sensitivity-labels-for-sites-groups-and-teams"></a>サイト、グループ、およびチームの感度ラベルを作成および展開する

Microsoft 365 コンプライアンス センターで感度ラベルを作成すると、次のコンテナーに適用できます。 [](../compliance/sensitivity-labels-teams-groups-sites.md)

- Microsoft Teams サイト
- Microsoft 365 グループ (以前Office 365 グループ)
- SharePoint サイト

これらのコンテナーのコンテンツを保護するには、次のラベル設定を使用します。

- Microsoft 365 グループ接続 Teams サイトのプライバシー (パブリックまたはプライベート)
- 外部ユーザーのアクセス
- 非管理対象デバイスからのアクセス

データのプライバシーを保護するには、機密の個人データを含むコンテンツを格納するために使用されるコンテナーの外部共有を防止するために、データを含むファイルをプライベートとしてマークし、管理対象デバイスを必要とします。

### <a name="create-and-deploy-sensitivity-labels-for-content"></a>コンテンツの感度ラベルを作成して展開する

ファイルに適用される感度ラベルを使用すると、コンテンツを暗号化し、コンテンツに透かしを付け、Office アプリケーション コンテンツの他のコントロール (Outlook や web 上の Office など) を定義できます。

感度ラベルを使用して組織のデータの保護を開始する準備ができたら、次の処理を行います。

1. **ラベルを作成する。** コンテンツのさまざまなレベルに対する組織の分類方法に従って、秘密度ラベルを作成して名前を付けます。 分類分類の開発の詳細については、「データ分類と感度ラベル分類」のホワイト ペーパー [を参照してください](https://aka.ms/dataclassificationwhitepaper)。
2. **各ラベルの機能を定義する。** 各ラベルに関連付ける必要がある保護設定を構成します。 たとえば、機密性の低いコンテンツ ("General" ラベルなど) にヘッダーまたはフッターを適用する必要がある一方で、機密性の高いコンテンツ ("Confidential" ラベルなど) は透かしを持ち、暗号化を有効にする必要があります。
3. **ラベルを発行する。** 秘密度ラベルの構成が完了したら、ラベル ポリシーを使用してラベルを公開します。 ラベルを使用する必要があるユーザーとグループおよび使用するポリシー設定を決定します。 1 つのラベルは再利用可能です。 一度定義した後、別のユーザーに割り当てられた複数のラベル ポリシーに含めできます。

Microsoft 365 コンプライアンス センターから感度ラベルを発行すると、ユーザーがコンテンツの作成または編集時にコンテンツを分類および保護するための [Office](../compliance/sensitivity-labels-office-apps.md) アプリに表示され始める。

![Microsoft 365 の感度ラベル展開フロー](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-label-flow.png)

データのプライバシーを保護するには、暗号化などのルールを含む機密ラベルを、機密情報を含む電子メールまたはコンテンツに手動で適用します。

>[!Note]
>電子メールに適用される暗号化を有効にした感度ラベルには、OME と重複する機能があります。 [「OME と感度ラベルとのセキュリティで保護された電子メール シナリオの比較」を参照してください](#secure-email-scenarios-comparison-with-ome-and-sensitivity-labels)。

### <a name="client-side-auto-labeling-when-users-edit-documents-or-compose-emails"></a>ユーザーがドキュメントを編集したり、メールを作成したりするときにクライアント側の自動ラベル付け

感応ラベルを作成すると、指定した条件[](../compliance/apply-sensitivity-label-automatically.md)と一致する場合に、電子メールを含むコンテンツにラベルを自動的に割り当てできます。

機密ラベルを自動的にコンテンツに適用する機能が重要である理由は次のとおりです。

- ユーザーのトレーニングは、一部の分類方法をいつ使用するかについてのみ必要。
- ユーザーへの依存は、一部のコンテンツを正しく分類するためにのみ必要。
- ユーザーはポリシーについて把握する必要がなくなり、自分たちの仕事に集中できます。

自動ラベル付けでは、ユーザーへのラベルの推奨、およびラベルの自動適用がサポートされています。 ただし、どちらの場合も、ユーザーはラベルを承諾または拒否するかどうかを決定し、コンテンツの正しいラベル付けを行います。

このクライアント側のラベル付けでは、ドキュメントを保存する前であってもラベルを適用できるため、ドキュメントの遅延が最小限に抑えられます。 ただし、すべてのクライアント アプリが自動ラベル付けをサポートしているわけではありません。 この機能は、Azure Information Protection 統合ラベル付けクライアント、および一部のバージョンのアプリ [でOfficeされます](../compliance/sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)。

構成手順については、「アプリの自動ラベル付けを構成する方法」 [をOfficeしてください](../compliance/sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)。

データのプライバシーを保護するには、機密情報を含むコンテンツに対して機密ラベルを自動適用します。

### <a name="service-side-auto-labeling-when-content-is-already-saved"></a>コンテンツが既に保存されている場合のサービス側の自動ラベル付け

この方法は、機密ラベルを使用した自動分類と呼ばれます。 また、保存中のデータ (SharePoint および OneDrive のドキュメントの場合) および転送中のデータ (Exchange によって送信または受信される電子メールの場合) の自動ラベル付けとも呼ばれる場合があります。 Exchange では、残りのメールボックスに電子メールは含めされません。
 
このラベル付けは、ユーザー アプリケーションではなくサービス自体によって適用されますので、ユーザーが持っているアプリとバージョンを心配する必要はありません。 その結果、この機能は、組織全体ですぐに使用できるようになります。また、規模に応じたラベル付けに適しています。 自動ラベル付けポリシーでは、ユーザーがラベル付けプロセスを操作しないので、推奨されるラベル付けをサポートしていません。 代わりに、管理者は、実際にラベルを適用する前に、コンテンツの正しいラベル付けを行うために、シミュレーション モードでポリシーを実行します。

構成手順については [、「SharePoint、OneDrive、Exchange](../compliance/apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)の自動ラベル付けポリシーを構成する方法」を参照してください。

懸念されるサイト内のデータプライバシーについては、機密情報を含むコンテンツの自動暗号化用の機密ラベルをプッシュします。

## <a name="data-loss-prevention"></a>データ損失防止 

Microsoft 365 のデータ損失防止 [(DLP)](../compliance/data-loss-prevention-policies.md) を使用すると、内部と外部の両方で個人情報を含むデータの共有など、危険な、不注意、または不適切な共有を検出、警告、ブロックできます。

DLP を使用すると、次の操作を実行できます。

- リスクの高い共有アクティビティを特定して監視します。
- 適切な意思決定を行うコンテキスト内ガイダンスをユーザーに教育します。
- 生産性を阻害することなく、コンテンツにデータ使用ポリシーを適用します。
- 分類とラベル付けと統合して、共有時にデータを検出して保護します。

### <a name="supported-workloads-for-dlp"></a>DLP でサポートされているワークロード

Microsoft 365 コンプライアンス センターの DLP ポリシーを使用すると、Exchange Online、SharePoint、OneDrive、Microsoft Teams など、Microsoft 365 の多くの場所で機密性の高いアイテムを特定、監視、および自動的に保護できます。

たとえば、OneDrive サイトに保存されているクレジット カード番号を含むドキュメントを特定したり、特定のユーザーの OneDrive サイトを監視することができます。

また、ローカルにインストールされたバージョンの Excel、PowerPoint、および Word の機密アイテムを監視および保護することもできます。この中には、機密性の高いアイテムを識別し、DLP ポリシーを適用する機能が含まれます。 DLP は、ユーザーがこれらのアプリからコンテンツを共有するときにOfficeします。

> [!div class="mx-imgBorder"]
> ![DLP でサポートされているワークロード](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-supported-workloads.png)

次の図は、個人データを保護する DLP の例を示しています。

> [!div class="mx-imgBorder"]
> ![DLP を使用して個人データを保護する例](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-example-use.png)

DLP は、正常性レコードを含むドキュメントまたは電子メールを識別し、そのドキュメントへのアクセスを自動的にブロックするか、電子メールの送信をブロックするために使用されます。 その後、DLP は受信者にポリシー ヒントを通知し、エンド ユーザーと管理者にアラートを送信します。

### <a name="planning-for-dlp"></a>DLP の計画

DLP ポリシーの計画は、次の場合に行います。 

- ビジネス要件。

- 「データのプライバシーリスクの評価と機密項目の特定」の記事で説明されている組織のリスクベース [の評価](information-protection-deploy-assess.md)。

- その他の情報保護とガバナンスのメカニズムは、データのプライバシーを計画する際に実施されています。

- 評価作業に基づいて個人データに対して識別した機密情報の種類については、「データのプライバシーリスクの評価と機密性の高いアイテムの識別」の記事 [で説明されています](information-protection-deploy-assess.md)。 DLP ポリシーの条件は、機密情報の種類と保持ラベルの両方に基づいて設定できます。

- DLP 条件を指定する必要がある保持ラベル。 詳細については [、組織の記事の「データプライバシー](information-protection-deploy-govern.md) 規制の対象となる管理情報」を参照してください。

- 継続的な DLP ポリシー管理。組織内の誰かが機密情報の種類、保持ラベル、規制、コンプライアンス ポリシーの変更に関するポリシーを運用および調整する必要があります。

機密ラベルは DLP ポリシー条件では使用できませんが、アクセスを防止するための特定の保護シナリオは、機密情報の種類に基づいて自動適用できる機密ラベルだけで実現できます。 堅牢な感度ラベル付けが行われる場合は、次の理由で DLP を使用して保護を強化する必要があるかどうかを検討してください。

  - DLP は、ファイルの共有を防止できます。 感度ラベルは、アクセスを妨げるだけである可能性があります。

  - DLP には、ルール、条件、およびアクションに関するより詳細なレベルの制御があります。

  - DLP ポリシーは、Teams チャットおよびチャネル メッセージに適用できます。 感度ラベルは、ドキュメントと電子メールにのみ適用できます。


### <a name="dlp-policies"></a>DLP ポリシー

DLP ポリシーは、Microsoft Compliance 管理センターで構成され、保護のレベル、ポリシーが探している機密情報の種類、およびターゲット ワークロードを指定します。 基本的なコンポーネントは、保護とデータの種類を識別することです。

> [!div class="mx-imgBorder"]
> ![Microsoft 365 での DLP ポリシー構成](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-config.png)

GDPR を認識する DLP ポリシーの例を次に示します。

![GDPR を認識する DLP ポリシーの例](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-example-policy.png)

DLP [ポリシーの作成](../compliance/create-test-tune-dlp-policy.md) と適用の詳細については、この記事を参照してください。

### <a name="protection-levels-for-data-privacy"></a>データプライバシーの保護レベル

次の表に、DLP を使用して保護を強化する 3 つの構成を示します。

![DLP によるデータプライバシーの保護レベル](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-protection-levels.png)

最初の構成である Awareness は、データプライバシー規制のコンプライアンスニーズに対応するために、開始点と最小レベルの保護として使用できます。

>[!Note]
>保護のレベルが上がった場合、ユーザーが情報を共有してアクセスする能力が低下し、生産性や毎日のタスクを完了する能力に影響を与える可能性があります。


従業員が保護レベルを上げるときに、より安全な環境で生産性を維持するために、時間を取って新しいセキュリティ ポリシーと手順をトレーニングし、教育します。

### <a name="example-of-using-sensitivity-labels-with-dlp"></a>DLP で感度ラベルを使用する例

感度ラベルは DLP と組み合わせて動作し、規制の厳しい環境でデータのプライバシーを提供できます。 統合展開の主な手順は次のとおりです。

1. データプライバシーに関する規制その他のビジネス要件が文書化されています。
2. ターゲット データ ソース、種類、および所有権は、データのプライバシーに関する懸念に関連して特徴付けされます。
3. 要件に対処し、データプライバシーホットスポットを保護および管理するための全体的な戦略が確立されています。
4. データ プライバシー管理戦略に対処する段階的なアクション プランが実行されます。

これらの要素が決定したら、機密情報の種類、分類の機密ラベル付け、および DLP ポリシーを一緒に使用できます。 次の図は、例を示しています。

> [!div class="mx-imgBorder"]
> ![DLP を操作する感度ラベルの例](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-sensitivity-lables-dlp.png)

[このイメージのより大きなバージョンを表示する](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-sensitivity-lables-dlp.png)

図に示すように、DLP ラベルと感度ラベルを組み合わせて使用するデータ保護のシナリオを次に示します。

| シナリオ | プロセス |
|:-------|:-----|
| A | <ol><li>コンテンツの感度ラベルは、管理者がユーザーとグループに公開し、手動または自動でコンテンツや電子メールに適用します。 </li><li>ユーザー A は、暗号化などの設定が適用されたコンテンツを操作するときに、手動または自動でラベルを適用します。 </li><li>ユーザー A は、保護された電子メールまたはファイルをゲスト ユーザーであるユーザー B に送信します。 </li></ol> |
| B | 管理者がユーザー A に公開した DLP ポリシーは、ユーザー A が電子メールやファイルをユーザー B に送信するのをブロックします。 |
| C |  "所有者がゲストを招待できない" 設定を持つ感度ラベルは、Teams チームまたは SharePoint サイトを準備するユーザー A に発行されます。 サイトの別のユーザーは、ユーザー B とファイルの共有を選択的に試行しますが、DLP はファイルをブロックします。 |
| D | サイト コンテンツに対する自動アプリケーションの感度ラベルが 1 つ以上のサイトに公開され、別の保護層が提供され、保護されたサイトが作成されます。 |
|||

## <a name="office-365-message-encryption-ome-new-capabilities"></a>Office 365 メッセージ暗号化 (OME) の新機能

多くの場合、ユーザーは電子メールを使用して、患者の健康情報や顧客情報や従業員情報などの機密情報を交換します。 メール メッセージの暗号化を使用すると、意図した受信者のみがメッセージの内容を表示できるようになります。

[OME を使用](../compliance/ome.md)すると、組織内外のユーザー間で暗号化されたメッセージを送受信できます。 OME は、Outlook.com Yahoo!、Gmail、その他のメール サービスと連携します。 OME を使用すると、目的の受信者だけがメッセージ コンテンツを表示できます。

データのプライバシーを保護するには、OME を使用して、機密性の高いアイテムを含む内部メッセージを保護します。 Office 365 Message Encryption は、Azure Information Protection の一部である Microsoft Azure Rights Management (Azure RMS) 上に構築されたオンライン サービスです。 このサービスには、メールをセキュリティで保護するための暗号化、ID、および認証ポリシーが含まれています。 メッセージを暗号化するには、アクセス許可管理のテンプレートである転送不可オプションおよび暗号化のみオプションを使用します。

この保護を適用するメール フロー ルールを定義することもできます。 たとえば、特定の受信者にアドレス指定されたメッセージの暗号化を必要とするルール、または件名行に特定のキーワード単語を含むルールを作成し、受信者がメッセージの内容をコピーまたは印刷できないと指定できます。

さらに、OME [Advanced Message Encryption](../compliance/ome-advanced-message-encryption.md) は、外部受信者に対するより柔軟な制御と暗号化された電子メールへのアクセスを必要とするコンプライアンス義務を満たすのに役立ちます。 Microsoft 365 の OME Advanced Message Encryption を使用すると、機密情報の種類を検出する自動ポリシーを使用して、組織外で共有される機密メールを制御できます。 

データのプライバシーを保護するために、外部のユーザーと電子メールを共有する必要がある場合は、有効期限を指定してメッセージを取り消します。 外部受信者に送信されるメッセージの有効期限は、取り消して設定できます。

### <a name="secure-email-scenarios-comparison-with-ome-and-sensitivity-labels"></a>OME ラベルと感度ラベルとのセキュリティで保護された電子メール シナリオの比較

暗号化を使用してメールに適用される OME ラベルと感度ラベルには重複が含まれるので、次の表に示すように、どのシナリオに適用されるかを理解することが重要です。

| シナリオ | 機密ラベル | OME |
|:-------|:-----|:-------|
| 内部 + パートナー <br> 内部ユーザーと信頼できるパートナーとの間で安全にコミュニケーションと共同作業を行う | おすすめ – 完全にカスタマイズされた分類と保護を持つラベル | はい – 暗号化のみまたは分類なし保護を転送しない |
| 外部関係者 <br> 外部/コンシューマー ユーザーと安全に通信し、共同作業を行う | はい - ラベル内の定義済みの受信者 | 推奨 – 受信者に基づく Just-in-time 保護 |
| 内部 + パートナー(有効期限/失効あり) <br> 期限切れと失効を持つ内部ユーザーと信頼できるパートナーとのメールとコンテンツのアクセスを制御する | 推奨 - アクセス期間を使用して完全にカスタマイズされた保護、ユーザーは手動でファイルの追跡と取り消しを行うことができます | いいえ - 内部メールの失効または有効期限なし |
| 有効期限/失効を持つ外部関係者 <br> 期限切れと失効を持つ外部/コンシューマー ユーザーによるメールとコンテンツのアクセスを制御する | はい - ユーザーは手動でファイルを追跡できます | 推奨 (E5) – 管理者がセキュリティ センターからメールを取り消&コンプライアンス センター |
| 自動ラベル付け <br> 特定の機密性の高いコンテンツや特定の受信者を含むメール/添付ファイルを自動的に保護する組織 | 推奨 (E5) - Exchange クライアントと Outlook クライアントでの自動ラベル付け、メール フロー ルールと DLP ポリシーの強化 | はい - 暗号化のみまたは転送しない保護を使用したメール フロー ルールと DLP ポリシー |
||||

また、これら 2 つの方法では、エンドユーザーと管理者のエクスペリエンスに違いがあります。

## <a name="teams-with-protection-for-highly-sensitive-data"></a>機密性の高いデータを保護するチーム

Teams のデータプライバシー規制の対象となる個人データを格納する組織については、「[](secure-teams-security-isolation.md)セキュリティ分離を使用してチームを構成する」を参照してください。詳細なガイダンスと構成手順を以下に示します。

- ID と デバイス アクセス
- プライベート チームの作成
- 基になるチーム サイトのアクセス許可のロックダウン
- 暗号化を使用したグループベースの感度ラベル