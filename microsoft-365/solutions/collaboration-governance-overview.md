---
title: Microsoft 365のコラボレーション ガバナンス フレームワーク
ms.reviewer: mmclean
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365solution-overview
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: Microsoft 365 グループ、Teams、SharePoint、Yammerなど、Microsoft 365コラボレーション ツールのガバナンスのベスト プラクティスについて説明します。
ms.openlocfilehash: 130342725e8c43b4aeaac116b94704db3046e059
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64941393"
---
# <a name="what-is-collaboration-governance"></a>共同作業のガバナンスとは?

コラボレーション ガバナンスは、ユーザーのリソースへのアクセスを管理し、ビジネス標準に準拠し、データのセキュリティを確保する方法です。

今日の組織は、さまざまなツール セットを使用しています。 チーム チャットを使用する開発者のチーム、メールを送信する幹部、および企業のソーシャルを介して接続する組織全体があります。 複数のコラボレーション ツールが使用されている理由は、すべてのグループが一意であり、独自の機能ニーズと作業スタイルがあるためです。 一部のユーザーはメールのみを使用し、他のユーザーは主にチャットでライブになります。 

ユーザーは、IT が提供するツールがニーズに合わないと思った場合、自分のシナリオに対応するお気に入りのコンシューマー アプリをダウンロードすることになるでしょう。 このプロセスにより、ユーザーはすぐに使い始めることができますが、複数のログイン、共有の困難さ、コンテンツの閲覧場所の不足など、組織全体でユーザー エクスペリエンスが低下します。 この概念は「シャドウ IT」と呼ばれ、組織に重大なリスクをもたらします。 これにより、ユーザー アクセスを均一に管理し、セキュリティとサービス コンプライアンスのニーズを保証できる機能が減ります。

Microsoft 365 グループ、Teams、Yammerなどのサービスは、共同作業に必要なツールを提供することで、ユーザーを支援し、シャドウ IT のリスクを軽減します。 Microsoft 365には、組織が必要とするガバナンス機能を実装するための豊富なツールセットがあります。 

![Microsoft 365のコラボレーション ガバナンス オプションを示すグラフ。](../media/collaboration-governance-overview.png)

この一連の記事は、グループ、チーム、SharePointの設定の相互作用、使用可能なガバナンス機能、およびMicrosoft 365のコラボレーション機能のガバナンス フレームワークを作成して実装する方法を理解するのに役立ちます。

### <a name="setting-up-secure-collaboration-with-microsoft-365"></a>Microsoft 365でセキュリティで保護されたコラボレーションを設定する

組織内でセキュリティで保護されたコラボレーションを行うためのMicrosoft 365 グループとTeamsを展開するためのオプションは多数あります。 このガバナンス コンテンツと共に、[セキュリティで保護されたファイル共有とコラボレーションを設定し、Microsoft Teams](setup-secure-collaboration-with-teams.md)とその関連記事を使用して、組織に最適なコラボレーション ソリューションを作成することをお勧めします。

### <a name="data-residency-governance"></a>データ常駐ガバナンス

組織が複数国籍であり、さまざまな地域のデータ所在地要件がある場合は、コラボレーション ガバナンス計画の一部として[Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo) を含めます。

## <a name="why-microsoft-365-groups-are-important-in-collaboration-governance"></a>コラボレーション ガバナンスでMicrosoft 365 グループが重要な理由

Microsoft 365 グループを使用すると、共同作業を行うユーザーのセットを選択し、それらのユーザーが共有するリソースのコレクションを簡単に設定できます。 グループにメンバーを追加すると、グループによって提供されるすべての資産に必要なアクセス許可が自動的に付与されます。 TeamsとYammerの両方で、Microsoft 365 グループを使用してメンバーシップを管理します。

Microsoft 365 グループには、ユーザーが通信やコラボレーションに使用できるリンクされたリソースのスイートが含まれます。 グループには常に、SharePoint サイト、Planner、Power BI ワークスペース、メールボックスと予定表、Stream が含まれます。 グループの作成方法に応じて、必要に応じて、Teams、Yammer、Projectなどの他のサービスを追加できます。

![Microsoft 365 グループおよび関連するサービスを示す図。](../media/microsoft-365-groups-hub-spoke.png)

|関連情報|説明|
|:------|:----------|
|[Calendar](https://support.office.com/article/schedule-a-meeting-on-a-group-calendar-in-outlook-0cf1ad68-1034-4306-b367-d75e9818376a)|グループに関連するイベントをスケジュールする場合|
|[[Inbox (受信トレイ)](https://support.office.com/article/have-a-group-conversation-in-outlook-a0482e24-a769-4e39-a5ba-a7c56e828b22)]|グループ メンバー間の電子メール会話の場合。 この受信トレイにはメール アドレスがあり、従来の配布リストと同様に、グループ外のユーザーや組織外のユーザーからのメッセージを受け入れるように設定できます。|
|[ノートブックをOneNoteする](https://support.office.com/article/get-started-with-onenote-e768fafa-8f9b-4eac-8600-65aa10b2fe97)|アイデア、リサーチ、情報を収集する場合|
|[Planner](https://support.office.com/article/microsoft-planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc)|グループ メンバー間でのプロジェクト タスクの割り当てと管理|
|[Power BI ワークスペース](/power-bi/collaborate-share/service-new-workspaces)|ダッシュボードとレポートを含むデータ コラボレーション空間|
|[Projectとロードマップ](https://support.microsoft.com/project)|Web ベースのプロジェクト管理ツール|
|[SharePoint チーム サイト](https://support.office.com/article/what-is-a-sharepoint-team-site-75545757-36c3-46a7-beed-0aaa74f0401e)|グループに関連する情報、リンク、コンテンツの中央リポジトリ|
|[Stream](https://support.microsoft.com/microsoft-stream)|ビデオ ストリーミング サービス|
|[Teams](https://support.microsoft.com/teams)|Microsoft 365のチャット ベースのワークスペース|
|[Yammer グループ](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)|会話を行い、情報を共有する一般的な場所|

Microsoft 365 グループには、組織内のグループの管理に役立つ、有効期限ポリシー、名前付け規則、ブロックされた単語ポリシーなど、さまざまなガバナンス制御が含まれています。 グループはメンバーシップとこの一連のリソースへのアクセスを制御するため、グループの管理は、Microsoft 365でのコラボレーションの管理の重要な部分です。

## <a name="define-collaboration-governance-best-practices-for-your-organization"></a>組織のコラボレーション ガバナンスのベスト プラクティスを定義する

共同作業を行い、Microsoft 365内で会話を行う場所は複数あります。 ユーザーが会話を開始できる場所を理解することは、コミュニケーションの戦略を定義するのに役立ちます。

Microsoft 365では、次の 3 つの主要な通信方法がサポートされています。

- Outlook: グループの受信トレイと予定表が共有される電子メールを通じた共同作業
- Microsoft Teams: 特定のサブグループで編成された、さまざまなトピックに関する非公式でリアルタイムの会話を行うことができる常設チャット ベースのワークスペース
- Yammer: 共同作業のためのエンタープライズ ソーシャル エクスペリエンス

![Teams、Yammer、Outlookをいつ使用するかを示す図。](../media/inner-loop-outer-loop.png)

- Teams: チャット ベースのワークスペース (高速なコミュケーション) – 内部ループ
  - ユーザーが毎日作業するユーザーとのコラボレーション用に構築された
  - 単一のエクスペリエンスでユーザーが簡単に情報を得られるようにします
  - タブ、コネクタおよびボットを追加します
  - ライブ チャット、オーディオ/ビデオ会議、録画された会議

- Yammer: 組織全体をつなぐ (エンタープライズ ソーシャル) – 外部ループ
  - 実践のコミュニティ - 共通の関心や専門知識を共有しているが、日常的に連携しているとは限らない人々の機能をまたがるグループ
  - リーダーのつながり、学習コミュニティ、役割ベースのコミュニティ

- メールボックスと予定表 (電子メール ベースのコラボレーション)
  - ユーザーのグループとのターゲットを絞った通信に使用されます
  - 他のグループ メンバーとの会議の共有予定表
 
Microsoft 365でコラボレーション機能を使用する方法を決定する際に、これらのコミュニケーション方法と、ユーザーがさまざまなシナリオで使用する可能性が高い方法を検討します。

> [!NOTE]
> Yammer または Teams によって作成された新しい Office 365 グループは、そのグループのユーザー間の主なコミュニケーションが各自の個別のクライアントで行われるため、Outlook やアドレス帳には表示されません。 Yammer グループをTeamsに接続できません。

## <a name="collaboration-governance-best-practices-checklist"></a>コラボレーション ガバナンスのベスト プラクティスチェックリスト

ガバナンス計画プロセスを開始するときは、次のベスト プラクティスに留意してください。

- **ユーザーと話し** 合う - コラボレーション機能の最大のユーザーを特定し、そのユーザーと一緒に会って、主要なビジネス要件とユース ケース シナリオを理解します。

- **リスクと利点のバランス** を取る - ビジネス、規制、法的、コンプライアンスのニーズを確認し、すべての結果を最適化するソリューションを計画します。

- **さまざまな組織やさまざまな種類のコンテンツやシナリオに適応** する - イントラネット コンテンツやユーザーのOneDrive コンテンツなど、さまざまなグループや部署、さまざまな種類のコンテンツに対するさまざまなニーズを考慮してください。

- **ビジネスの優先順位に合わせる** - ビジネス目標は、ガバナンスに投資するために必要な時間とエネルギーの量を定義するのに役立ちます。

- **作成したソリューションにガバナンスの決定を直接埋め込みます**。多くのガバナンスの決定は、Microsoft 365の機能をオンまたはオフにすることで実装できます。


- **段階的なアプローチを使用する** - コラボレーション機能を最初に少数のユーザー グループに展開します。 大規模なグループに進む前に、フィードバックを受け取り、ヘルプ デスク チケットを確認し、必要な設定やプロセスを更新します。

- **トレーニングを強化する** - [Microsoft 365ラーニング パス](/office365/customlearning)などのソリューションを調整して、組織固有の期待が Microsoft 提供のトレーニングで強化されるようにします。

- **組織内でガバナンス ポリシーとガイドラインを伝達するための戦略を立て、** SharePointコミュニケーション サイトにMicrosoft 365導入センターを作成し、ポリシーと手順を伝えます。

- **役割と責任を定義** する - ガバナンス コア チームを特定し、最初にプロビジョニングと名前付けと外部アクセスに関する重要なガバナンスの決定を行い、残りの決定を実行します。

- **ビジネスとテクノロジの変化に合わせて意思決定を見直す** - 定期的に会議を行い、新しい機能と新しいビジネスの期待を確認します。

これらのプラクティスの詳細については、「 [コラボレーション ガバナンス 計画の作成」を参照してください](collaboration-governance-first.md)。

## <a name="end-user-impact-and-change-management"></a>エンド ユーザーの影響と変更管理

グループとチームは複数の方法で作成できるため、組織に最適な方法を使用するようにユーザーをトレーニングすることをお勧めします。

- 組織が電子メールを使用してほとんどの通信を行う場合は、Outlookでグループを作成するようにユーザーに指示します。
- 組織がSharePointを頻繁に使用している場合、またはオンプレミスから移行SharePoint場合は、共同作業のためにSharePointチーム サイトを作成するようにユーザーに指示します。
- 組織がTeams展開している場合は、コラボレーションスペースが必要なときにチームを作成するようにユーザーに指示します。

これにより、ユーザーがグループと関連するサービスとの関係に慣れていない場合に混乱を回避できます。 グループについてユーザーと話す方法の詳細については、「ユーザーに[対するMicrosoft 365 グループの説明」を参照してください](../admin/create-groups/explain-groups-knowledge-worker.md)。

## <a name="key-collaboration-governance-capabilities-and-licensing-requirements"></a>主要なコラボレーション ガバナンス機能とライセンス要件

Microsoft 365でのコラボレーションのガバナンス機能には、Microsoft 365、Teams、SharePoint、Azure Active Directoryの機能が含まれます。

| 機能 | 説明 | ライセンス |
|:----------------------|:------------|:----------|
|チームとサイトの共有|チーム、グループ、サイトを組織外のユーザーと共有できるかどうかを制御します。|Microsoft 365 E5または E3|
|ドメインの許可/ブロック|組織外のユーザーとの共有を、特定のドメインのユーザーに制限します。|Microsoft 365 E5または E3|
|セルフサービス サイト作成|ユーザーが独自のSharePoint サイトを作成できないようにします。|Microsoft 365 E5または E3|
|制限付きサイトとファイル共有|サイト、ファイル、フォルダーの共有を特定のセキュリティ グループのメンバーに制限します。|Microsoft 365 E5または E3|
|制限付きグループの作成|チームとグループの作成を特定のセキュリティ グループのメンバーに制限します。|Azure AD Premiumまたは Azure AD Basic EDU ライセンスのMicrosoft 365 E5または E3|
|グループの名前付けポリシー|グループ名とチーム名にプレフィックスまたはサフィックスを適用します。|Azure AD Premiumまたは Azure AD Basic EDU ライセンスのMicrosoft 365 E5または E3|
|グループの有効期限ポリシー|非アクティブなグループとチームを期限切れに設定し、指定した期間後に削除します。|Azure AD Premium ライセンスを持つMicrosoft 365 E5または E3|
|グループごとのゲスト アクセス|グループごとに組織外のユーザーとのチームとグループの共有を許可または禁止します。|Microsoft 365 E5または E3|

## <a name="collaboration-governance-planning-recommendations"></a>おすすめのコラボレーション ガバナンス計画

次の基本的な手順に従って、ガバナンス計画を作成します。

1. 主要なビジネス目標とプロセスを検討してください。ビジネスのニーズに合わせて [ガバナンス計画を作成します](collaboration-governance-first.md) 。
2. グループ、[SharePoint、SharePoint Teams、その他の](groups-sharepoint-governance.md)[サービス](groups-services-interactions.md)の設定と同様に、サービス[の設定](groups-sharepoint-teams-governance.md)について理解します。 ガバナンス戦略を計画するときは、これらの相互作用を必ず理解してください。
3. ユーザー アクセスの管理を計画する - [グループ、SharePoint、およびTeamsのユーザーに付与するアクセスレベルを](groups-teams-access-governance.md)計画します。
4. コンプライアンス設定の管理を計画する - [Microsoft 365 グループ、Teams、およびSharePointコラボレーションで使用可能なコンプライアンス オプションを](groups-teams-compliance-governance.md)確認します。
5. 通信の管理を計画する - [コラボレーション シナリオで使用可能な通信ガバナンス オプションを確認します](groups-teams-communication-governance.md)。
6. 組織とライフサイクルガバナンスを計画する - [グループとチームの作成、名前付け、有効期限、アーカイブに使用するポリシーを](plan-organization-lifecycle-governance.md)選択します。 また、グループ、[チーム、Yammerのライフサイクルの終了オプションについても](end-life-cycle-groups-teams-sites-yammer.md)理解します。

![推奨されるガバナンス手順の図。](../media/collaboration-governance-steps.png)

## <a name="training-for-administrators"></a>管理者向けのトレーニング

Microsoft Learn のこれらのトレーニング モジュールは、Microsoft 365のガバナンス機能を学習するのに役立ちます。

#### <a name="information-protection"></a>情報保護

|トレーニング: |情報保護とガバナンスを管理する|
|:---|:---|
|![情報保護トレーニング アイコン。](../media/information-protection-governance.svg)|今日、生成されるデータ量はかつてないほど急速に増加し、従業員はあらゆる場所で仕事をしたいと考えており、規制の状況は常に変化しています。 情報保護とガバナンスに関するMicrosoft のソリューションで、企業はデータの保護と従業員の生産性との適切なバランスの実現を保つことができます。 このラーニングパスはMicrosoft 365 認定: セキュリティ管理者  と Microsoft 365 認定: エンタープライズ管理エキスパート  の認定のための準備を行うことが出来ます。<br><br>5 時間 13 分 - ラーニング パス - 7 モジュール|

> [!div class="nextstepaction"]
> [スタート>](/learn/modules/m365-compliance-information-governance/introduction/)

<br><br>

|トレーニング: |Microsoft 365 で企業情報を保護する|
|:---|:---|
|![Teamsトレーニング アイコン。](../media/protect-enterprise-information-microsoft-365.svg)|組織の情報を保護することは、かつてないほど困難になっています。 「Microsoft 365 で社内の情報を保護する」のラーニング パスでは、機密情報を不用意な共有や誤用から保護する方法、データを検出して分類する方法、秘密度ラベルを使用して保護する方法、損失から保護するために機密情報を監視および分析する方法について説明します。 このラーニング パスは、Microsoft 365認定: セキュリティ管理者アソシエイトおよびMicrosoft 365認定: Enterprise Administration Expert 認定資格の準備に役立ちます。<br><br>1 時間 - ラーニング パス - 5 モジュール|

> [!div class="nextstepaction"]
> [スタート>](/learn/modules/m365-security-info-overview/introduction/)

#### <a name="security-and-compliance"></a>セキュリティとコンプライアンス

|トレーニング: |Microsoft 365 のセキュリティおよびコンプライアンス機能の基本的な知識を示します|
|:---|:---|
|![セキュリティとコンプライアンスのトレーニング アイコン。](../media/microsoft-365-security-and-compliance-capabilities.svg)|エンタープライズをセキュリティで保護し、規制要件に対応できるようにするために、365 Microsoft のセキュリティおよびコンプライアンス ソリューション エリアに関する情報を参照します。 基本的なクラウド コンピューティングの概念に慣れていない場合は、 [クラウドの概念 - クラウド コンピューティングの原則を](/learn/modules/principles-cloud-computing/index)取ることをお勧めします。<br><br>3 時間 11 分 - ラーニング パス - 8 モジュール|

> [!div class="nextstepaction"]
> [スタート>](/learn/modules/what-is-m365/1-introduction/)

## <a name="illustrations"></a>イラスト

これらの図は、グループやチームがMicrosoft 365で他のサービスとやり取りする方法と、組織内でこれらのサービスを管理するのに役立つガバナンスとコンプライアンス機能を理解するのに役立ちます。

### <a name="groups-in-microsoft-365-for-it-architects"></a>IT アーキテクト向け Microsoft 365 のグループ
IT アーキテクトが Microsoft 365 のグループについて知っておくべきこと

|**アイテム**|**説明**|
|:-----|:-----|
|[![グループインフォグラフィックのサム イメージ。](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx) <br> 更新日: 2019 年 6 月|これらの図は、さまざまな種類のグループがどのように作成および管理されているか、そしていくつかのガバナンスの推奨事項を詳述しています。|

### <a name="microsoft-teams-and-related-productivity-services-in-microsoft-365-for-it-architects"></a>IT アーキテクト向け Microsoft 365 の Microsoft Teams と関連生産性サービス
Microsoft Teamsをリードする Microsoft 365 での生産性サービスの論理的なアーキテクチャ。

|**アイテム**|**説明**|
|:-----|:-----|
|[![Teams論理アーキテクチャポスターのサム イメージ。](../downloads/msft-teams-logical-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-teams-logical-architecture.vsdx)  <br>更新日: 2019 年 4 月   |マイクロソフトは、連携してデータ ガバナンス、セキュリティ、およびコンプライアンス機能を備えたコラボレーション エクスペリエンスを提供する、一連の生産性サービスを提供しています。 <br/> <br/>この一連の図は、Microsoft Teams をはじめとする、エンタープライ ズアーキテクト向けの生産性サービスの論理アーキテクチャを概説したものです。|

### <a name="microsoft-365-information-protection-and-compliance-capabilities"></a>Microsoft 365情報保護とコンプライアンス機能

Microsoft 365には、広範な情報保護とコンプライアンス機能のセットが含まれています。 これらの機能は、Microsoft の生産性ツールと共に、厳格な規制コンプライアンス フレームワークに準拠しながら、組織がリアルタイムで共同作業できるように設計されています。 

この一連の図では、最も規制の厳しい業界の 1 つである金融サービスを使用して、一般的な規制要件に対処するためにこれらの機能を適用する方法を示します。 これらのイラストを自分の用途に合わせて自由にアレンジしてください。 


| アイテム | 説明 |
|:-----|:-----|
|[![モデル ポスター: Microsoft Purview の情報保護とコンプライアンス機能。](../media/solutions-architecture-center/m365-compliance-illustrations-thumb.png)](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf) <br/> 英語: [PDF としてダウンロードする](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf)  \| [Visio としてダウンロードする](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.vsdx) <br/> 日本語: [PDF としてダウンロードする](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.pdf)  \| [Visio としてダウンロードする](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.vsdx) <br/> 更新日: 2020 年 11 月|含まれる内容: <ul><li>  Microsoft Purview Information Protection と Microsoft Purview データ損失防止</li><li>アイテム保持ポリシーと保持ラベル </li><li>情報バリア</li><li>コミュニケーション コンプライアンス</li><li>インサイダー リスク</li><li>サードパーティのデータの取り込み</li>|

## <a name="conference-sessions"></a>会議セッション

Microsoft 365 グループとTeamsのガバナンスの詳細については、次の会議セッションをご覧ください。

**基礎**

大規模な管理とガバナンス、使用と導入を促進するためのベスト プラクティス、セルフサービスなど、Microsoft 365 グループの基礎と新しいイノベーションについて説明します。

- [Microsoft 365 グループを受け入れる](https://www.youtube.com/watch?v=dAamBF1gb7M)

**ガバナンス**

グループの有効期限ライフサイクル、名前付けポリシー、分類ラベル、外部ゲストとのコラボレーション、グループ作成アクセス許可の管理を設定する方法について説明します。

- [コラボレーションを変革し、Office 365 グループでシャドウ IT と戦う](https://www.youtube.com/watch?v=Bhf_bKx3lAg)

**顧客の例**

Microsoft 365 グループ、SharePoint、Teams、Yammerが連携してグローバル コラボレーション プラットフォームを提供する方法の背後にある例を参照してください。

- [Office 365 グループ、SharePoint、Teams、Yammerでコラボレーションのスイート スポットを見つける](https://www.youtube.com/watch?v=Rx9eVwqXeQk)

## <a name="see-also"></a>関連項目

[Microsoft 365 のセキュリティに関するドキュメント](../security/index.yml)

[Microsoft Purview のドキュメント](../compliance/index.yml)