---
title: 共同作業のガバナンスとは?
ms.reviewer: mmclean
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-overview
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Microsoft 365 グループ、Teams、SharePoint、およびグループ内の関連機能を管理する方法についてYammer。
ms.openlocfilehash: b31e9bf1cd46f94343a489497fb5eb00e138ce60
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916444"
---
# <a name="what-is-collaboration-governance"></a>共同作業のガバナンスとは?

コラボレーション ガバナンスは、ユーザーによるリソースへのアクセス、ビジネス標準への準拠、データのセキュリティの確保を管理する方法です。

今日の組織では、さまざまなツール セットが使用されています。 チーム チャットを使用する開発者チーム、電子メールを送信する役員、企業のソーシャルを通して接続する組織全体があります。 複数のコラボレーション ツールが使用されているのは、すべてのグループが一意であり、独自の機能ニーズと作業スタイルを持つためです。 一部のユーザーはメールのみを使用し、他のユーザーは主にチャットに住む場合があります。 

ユーザーは、IT が提供するツールがニーズに合わないと思った場合、自分のシナリオに対応するお気に入りのコンシューマー アプリをダウンロードすることになるでしょう。 このプロセスにより、ユーザーはすぐに使い始めることができますが、複数のログイン、共有の困難さ、コンテンツの閲覧場所の不足など、組織全体でユーザー エクスペリエンスが低下します。 この概念は「シャドウ IT」と呼ばれ、組織に重大なリスクをもたらします。 これにより、ユーザー アクセスを均一に管理し、セキュリティとサービス コンプライアンスのニーズを保証できる機能が減ります。

Microsoft 365 グループ、Teams、Yammerなどのサービスは、共同作業に必要なツールを提供することで、ユーザーを支援し、シャドウ IT のリスクを軽減します。 Microsoft 365 には、組織が必要とするガバナンス機能を実装するための豊富なツールセットがあります。 

![Microsoft 365 のコラボレーション ガバナンス オプションを示すグラフ](../media/collaboration-governance-overview.png)

この一連の記事は、グループ、チーム、および SharePoint 設定の相互作用、使用可能なガバナンス機能、および Microsoft 365 のコラボレーション機能のガバナンス 計画を作成および実装する方法を理解するのに役立ちます。

### <a name="setting-up-secure-collaboration-with-microsoft-365"></a>Microsoft 365 との安全なコラボレーションのセットアップ

組織内の安全なコラボレーションのために Microsoft 365 グループと Teams を展開するための多くのオプションがあります。 組織に最適なコラボレーション ソリューションを作成するには [、Microsoft 365](setup-secure-collaboration-with-teams.md) とその関連記事とのセキュリティで保護されたコラボレーションをセットアップするとともに、このガバナンス コンテンツを使用することをお勧めします。

### <a name="data-residency"></a>データの保存場所

組織が複数国間で、地域ごとにデータ常駐要件がある場合は、コラボレーション ガバナンス 計画の一部として [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo) を含める必要があります。

## <a name="why-microsoft-365-groups-are-important"></a>Microsoft 365 グループが重要な理由

Microsoft 365 グループでは、共同作業を行うユーザーのセットを選択し、それらのユーザーが共有するリソースのコレクションを簡単に設定できます。 グループにメンバーを追加すると、グループによって提供されるすべてのアセットに必要なアクセス許可が自動的に付与されます。 Teams とユーザー Yammer、Microsoft 365 グループを使用してメンバーシップを管理します。

Microsoft 365 グループには、ユーザーが通信と共同作業に使用できるリンクされたリソースのスイートが含まれます。 グループには、常に SharePoint サイト、Planner、Power BI ワークスペース、メールボックスと予定表、ストリームが含まれます。 グループの作成方法に応じて、Teams、Yammer、Project などの他のサービスを追加できます。

![Microsoft 365 グループと関連サービスを示す図](../media/microsoft-365-groups-hub-spoke.png)

|関連情報|説明|
|:------|:----------|
|[Calendar](https://support.office.com/article/schedule-a-meeting-on-a-group-calendar-in-outlook-0cf1ad68-1034-4306-b367-d75e9818376a)|グループに関連するイベントをスケジュールする場合|
|[[Inbox (受信トレイ)](https://support.office.com/article/have-a-group-conversation-in-outlook-a0482e24-a769-4e39-a5ba-a7c56e828b22)]|グループ メンバー間の電子メールの会話の場合。 この受信トレイには電子メール アドレスが含まれるので、従来の配布リストと同様に、グループ外のユーザーや組織外のユーザーからのメッセージを受け入れる設定が可能です。|
|[OneNote ノートブック](https://support.office.com/article/get-started-with-onenote-e768fafa-8f9b-4eac-8600-65aa10b2fe97)|アイデア、研究、情報を収集する|
|[Planner](https://support.office.com/article/microsoft-planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc)|グループ メンバー間でプロジェクト タスクを割り当て、管理する場合|
|[Power BI Workspace](/power-bi/collaborate-share/service-new-workspaces)|ダッシュボードとレポートを使用したデータコラボレーションスペース|
|[プロジェクトとロードマップ](https://support.microsoft.com/project)|Web ベースのプロジェクト管理ツール|
|[SharePoint チーム サイト](https://support.office.com/article/what-is-a-sharepoint-team-site-75545757-36c3-46a7-beed-0aaa74f0401e)|グループに関連する情報、リンク、およびコンテンツの中央リポジトリ|
|[Stream](https://support.microsoft.com/microsoft-stream)|ビデオ ストリーミング サービス|
|[Teams](https://support.microsoft.com/teams)|Microsoft 365 のチャット ベースのワークスペース|
|[Yammer グループ](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)|会話を行い、情報を共有する一般的な場所|

Microsoft 365 グループには、組織内のグループを管理するのに役立つ、有効期限ポリシー、名前付け規則、ブロックされた単語ポリシーなど、さまざまなガバナンス制御が含まれています。 グループは、このリソース スイートへのメンバーシップとアクセスを制御します。グループの管理は、Microsoft 365 でのコラボレーションを管理する重要な部分です。

## <a name="define-a-collaboration-strategy-for-your-organization"></a>組織のコラボレーション戦略を定義する

Microsoft 365 内には、共同作業や会話を行う場所が複数ある。 ユーザーが会話を開始できる場所を理解すると、コミュニケーションの戦略を定義するのに役立ちます。

Microsoft 365 でサポートされる主な通信方法は次の 3 つがあります。

- Outlook: グループの受信トレイと予定表が共有される電子メールを通じた共同作業
- Microsoft Teams: 特定のサブグループ別に編成された、さまざまなトピックに関する非公式でリアルタイムの会話を行える常設チャット ベースのワークスペース
- Yammer: 共同作業のためのエンタープライズ ソーシャル エクスペリエンス

![Teams、Yammer、Outlook を使用する場合を示す図](../media/inner-loop-outer-loop.png)

- Teams: チャット ベースのワークスペース (高速なコミュケーション) – 内部ループ
  - ユーザーが毎日作業するユーザーとの共同作業のために構築されています
  - 単一のエクスペリエンスでユーザーが簡単に情報を得られるようにします
  - タブ、コネクタおよびボットを追加します
  - ライブ チャット、音声/ビデオ会議、録画された会議

- Yammer: 組織全体をつなぐ (エンタープライズ ソーシャル) – 外部ループ
  - 実践コミュニティ - 共通の関心や専門知識を共有しているが、必ずしも日単位で一緒に作業しているわけではない人々のクロス機能的なグループ
  - リーダーのつながり、学習コミュニティ、役割ベースのコミュニティ

- メールボックスと予定表 (電子メール ベースのコラボレーション)
  - グループのユーザーとのターゲット通信に使用されます。
  - 他のグループ メンバーとの会議の共有予定表
 
Microsoft 365 でコラボレーション機能を使用する方法を決定する際には、これらの通信方法と、ユーザーがさまざまなシナリオで使用する可能性がある方法を検討してください。

> [!NOTE]
> Yammer または Teams によって作成された新しい Office 365 グループは、そのグループのユーザー間の主なコミュニケーションが各自の個別のクライアントで行われるため、Outlook やアドレス帳には表示されません。 Yammer Teams に接続することはできません。


## <a name="best-practices"></a>ベスト プラクティス

ガバナンス計画プロセスを開始する場合は、以下のベスト プラクティスに注意してください。

- **ユーザーと話す** - コラボレーション機能の最大のユーザーを特定し、それらのユーザーと会って、コアビジネス要件と使用例のシナリオを理解します。

- **リスクとメリットのバランス** を取る - ビジネス、規制、法務、コンプライアンスのニーズを確認し、すべての結果を最適化するソリューションを計画します。

- **さまざまな組織やさまざまな種類** のコンテンツやシナリオに適応する - さまざまなグループや部署、イントラネット コンテンツなどのさまざまな種類のコンテンツとユーザーの OneDrive コンテンツに対するさまざまなニーズを考慮します。

- **ビジネスの優先順位に合** わせて調整する - ビジネス目標は、ガバナンスに投資する必要がある時間とエネルギーを定義するのに役立ちます。

- **作成するソリューションに** ガバナンスの決定を直接埋め込む - Microsoft 365 の機能をオンまたはオフにすることで、多くのガバナンス決定を実装できます。


- **段階的なアプローチを使用する** - 最初に小さなグループのユーザーにコラボレーション機能をロールアウトします。 より大きなグループに進む前に、フィードバックを受け取り、ヘルプ デスク のチケットを監視し、必要な設定やプロセスを更新します。

- **トレーニングの強化** - Microsoft [365](/office365/customlearning) ラーニング パスなどのソリューションを調整して、組織固有の期待を Microsoft 提供のトレーニングで強化します。

- **組織でガバナンス ポリシー** とガイドラインを伝達するための戦略を策定する - ポリシーと手順を伝える SharePoint コミュニケーション サイトに Microsoft 365 導入センターを作成します。

- **役割と責任を定義** する - ガバナンスの中核チームを特定し、プロビジョニングと名前付けと外部アクセスに関する主要なガバナンス決定を最初に実行し、残りの決定を実行します。

- **ビジネスとテクノロジの変更に** 合わせて意思決定を再検討する - 定期的に満たして、新しい機能と新しいビジネスの期待を確認します。

これらのプラクティスの詳細については、「コラボレーション ガバナンス 計画の作成 [」を参照してください](collaboration-governance-first.md)。

## <a name="end-user-impact-and-change-management"></a>エンド ユーザーの影響と変更管理

グループとチームはいくつかの方法で作成できますので、組織に最適な方法を使用するユーザーをトレーニングすることをお勧めします。

- 組織が電子メールを使用してほとんどの通信を行う場合は、Outlook でグループを作成するようにユーザーに指示します。
- 組織で SharePoint を大量に使用している場合、または SharePoint オンプレミスから移行する場合は、共同作業用に SharePoint チーム サイトを作成するようにユーザーに指示します。
- 組織が Teams を展開している場合は、共同作業スペースが必要なときにチームを作成するようにユーザーに指示します。

これにより、ユーザーがグループと関連するサービスとの関係に慣れていない場合に混乱を避けるのに役立ちます。 グループについてユーザーと話す方法の詳細については [、「Microsoft 365 グループ](../admin/create-groups/explain-groups-knowledge-worker.md)をユーザーに説明する」を参照してください。

## <a name="key-governance-capabilities-and-licensing-requirements"></a>主なガバナンス機能とライセンス要件

Microsoft 365 でのコラボレーションのガバナンス機能には、Microsoft 365、Teams、SharePoint、Azure Active Directory の機能が含まれます。

| 機能 | 説明 | ライセンス |
|:----------------------|:------------|:----------|
|チームとサイトの共有|チーム、グループ、サイトを組織外のユーザーと共有できる場合に制御します。|Microsoft 365 E5 または E3|
|ドメインの許可/ブロック|組織外のユーザーとの共有を、特定のドメインのユーザーに制限します。|Microsoft 365 E5 または E3|
|セルフサービス サイト作成|ユーザーが自分の SharePoint サイトを作成するを許可または防止します。|Microsoft 365 E5 または E3|
|制限付きサイトとファイル共有|サイト、ファイル、およびフォルダー共有を特定のセキュリティ グループのメンバーに制限します。|Microsoft 365 E5 または E3|
|制限付きグループの作成|チームとグループの作成を特定のセキュリティ グループのメンバーに制限します。|Microsoft 365 E5 または E3 と Azure ADプレミアムまたは Azure AD EDU ライセンス|
|グループの名前付けポリシー|グループ名とチーム名にプレフィックスまたはサフィックスを適用します。|Microsoft 365 E5 または E3 と Azure ADプレミアムまたは Azure AD EDU ライセンス|
|グループの有効期限ポリシー|非アクティブなグループとチームの有効期限を設定し、指定した期間が経過すると削除されます。|Microsoft 365 E5 または E3 と Azure AD プレミアム ライセンス|
|グループごとのゲスト アクセス|グループ単位で組織外のユーザーとのチームとグループの共有を許可または防止します。|Microsoft 365 E5 または E3|

## <a name="collaboration-governance-planning-step-by-step"></a>コラボレーション ガバナンス計画のステップ バイ ステップ

ガバナンス 計画を作成するには、次の基本的な手順に従います。

1. 重要なビジネス目標とプロセスを検討する - ビジネスのニーズを [満](collaboration-governance-first.md) たすガバナンス計画を作成します。
2. グループ[](groups-services-interactions.md)[、SharePoint、Teams、](groups-sharepoint-governance.md)その他のサービスの設定と同様に、サービス[](groups-sharepoint-teams-governance.md)の設定について理解します。 ガバナンス戦略を計画する場合は、必ずこれらのやり取りを理解してください。
3. ユーザー アクセスの管理を計画する - グループ [、SharePoint、Teams](groups-teams-access-governance.md)でユーザーに付与するアクセスのレベルを計画します。
4. コンプライアンス設定の管理を計画する - [Microsoft 365 グループ、Teams、および SharePoint](groups-teams-compliance-governance.md)コラボレーションで使用可能なコンプライアンス オプションを確認します。
5. 通信の管理を計画する - コラボレーション シナリオで使用可能 [な通信ガバナンス オプションを確認します](groups-teams-communication-governance.md)。
6. 組織とライフサイクルのガバナンスを計画する - グループとチームの作成、名前付け、有効期限、アーカイブに使用するポリシー [を選択します](plan-organization-lifecycle-governance.md)。 また、グループ、[チーム、](end-life-cycle-groups-teams-sites-yammer.md)およびグループのライフサイクルの終了オプションYammer

![推奨されるガバナンス手順の図](../media/collaboration-governance-steps.png)

## <a name="training-for-administrators"></a>管理者向けトレーニング

Microsoft Learn のこれらのトレーニング モジュールは、Microsoft 365 のガバナンス機能を学習するのに役立ちます。

#### <a name="information-protection"></a>情報保護

|トレーニング:|情報保護とガバナンスを管理する|
|:---|:---|
|![情報保護トレーニング アイコン](../media/information-protection-governance.svg)|今日、生成されるデータ量はかつてないほど急速に増加し、従業員はあらゆる場所で仕事をしたいと考えており、規制の状況は常に変化しています。 情報保護とガバナンスに関するMicrosoft のソリューションで、企業はデータの保護と従業員の生産性との適切なバランスの実現を保つことができます。 このラーニングパスはMicrosoft 365 認定: セキュリティ管理者  と Microsoft 365 認定: エンタープライズ管理エキスパート  の認定のための準備を行うことが出来ます。<br><br>5 時間 13 分 - ラーニング パス - 7 モジュール|

> [!div class="nextstepaction"]
> [スタート>](/learn/modules/m365-compliance-information-governance/introduction/)

<br><br>

|トレーニング:|Microsoft 365 で企業情報を保護する|
|:---|:---|
|![Teams トレーニング アイコン](../media/protect-enterprise-information-microsoft-365.svg)|組織の情報を保護することは、かつてないほど困難になっています。 「Microsoft 365 で社内の情報を保護する」のラーニング パスでは、機密情報を不用意な共有や誤用から保護する方法、データを検出して分類する方法、秘密度ラベルを使用して保護する方法、損失から保護するために機密情報を監視および分析する方法について説明します。 この学習パスは、Microsoft 365 Certified: Security Administrator Associate と Microsoft 365 Certified: Enterprise Administration Expert 認定の準備に役立ちます。<br><br>1 時間 - ラーニング パス - 5 モジュール|

> [!div class="nextstepaction"]
> [スタート>](/learn/modules/m365-security-info-overview/introduction/)

#### <a name="security-and-compliance"></a>セキュリティとコンプライアンス

|トレーニング:|Microsoft 365 のセキュリティおよびコンプライアンス機能の基本的な知識を示します|
|:---|:---|
|![セキュリティとコンプライアンスのトレーニング アイコン](../media/microsoft-365-security-and-compliance-capabilities.svg)|エンタープライズをセキュリティで保護し、規制要件に対応できるようにするために、365 Microsoft のセキュリティおよびコンプライアンス ソリューション エリアに関する情報を参照します。 基本的なクラウド コンピューティングの概念に慣れていない場合は、クラウド 概念 - クラウド コンピューティングの原則を [使用することをお勧めします](/learn/modules/principles-cloud-computing/index)。<br><br>3 時間 11 分 - ラーニング パス - 8 モジュール|

> [!div class="nextstepaction"]
> [スタート>](/learn/modules/what-is-m365/1-introduction/)

## <a name="illustrations"></a>図

これらの図は、グループとチームが Microsoft 365 の他のサービスとどのようにやり取りし、組織でこれらのサービスを管理するのに役立つガバナンスおよびコンプライアンス機能を理解するのに役立ちます。

### <a name="groups-in-microsoft-365-for-it-architects"></a>IT アーキテクト向け Microsoft 365 のグループ
IT アーキテクトが Microsoft 365 のグループについて知っておくべきこと

|**アイテム**|**説明**|
|:-----|:-----|
|[![グループ インフォグラフィックのサムネイル](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx) <br> 更新日: 2019 年 6 月|これらの図は、さまざまな種類のグループがどのように作成および管理されているか、そしていくつかのガバナンスの推奨事項を詳述しています。|

### <a name="microsoft-teams-and-related-productivity-services-in-microsoft-365-for-it-architects"></a>IT アーキテクト向け Microsoft 365 の Microsoft Teams と関連生産性サービス
Microsoft Teamsをリードする Microsoft 365 での生産性サービスの論理的なアーキテクチャ。

|**アイテム**|**説明**|
|:-----|:-----|
|[![Teams の論理的なアーキテクチャ ポスターのサムネイル](../downloads/msft-teams-logical-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-teams-logical-architecture.vsdx)  <br>更新日: 2019 年 4 月   |マイクロソフトは、連携してデータ ガバナンス、セキュリティ、およびコンプライアンス機能を備えたコラボレーション エクスペリエンスを提供する、一連の生産性サービスを提供しています。 <br/> <br/>この一連の図は、Microsoft Teams をはじめとする、エンタープライ ズアーキテクト向けの生産性サービスの論理アーキテクチャを概説したものです。|

### <a name="microsoft-365-information-protection-and-compliance-capabilities"></a>Microsoft 365 の情報保護とコンプライアンス機能

Microsoft 365 には、情報保護とコンプライアンス機能の広範なセットが含まれています。 Microsoft の生産性向上ツールと共に、これらの機能は、厳しい規制コンプライアンス フレームワークを遵守しながら、組織がリアルタイムで共同作業を行うのを支援するように設計されています。 

この一連の図では、最も規制の厳しい業界の 1 つである金融サービスを使用して、一般的な規制要件に対応するためにこれらの機能を適用する方法を示します。 これらのイラストを自分の用途に合わせて自由にアレンジしてください。 


| アイテム | 説明 |
|:-----|:-----|
|[![モデル ポスター: Microsoft 365 の情報保護とコンプライアンスの機能](../media/solutions-architecture-center/m365-compliance-illustrations-thumb.png)](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf) <br/> 英語: [PDF としてダウンロードする](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf)  \| [Visio としてダウンロードする](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.vsdx) <br/> 日本語: [PDF としてダウンロードする](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.pdf)  \| [Visio としてダウンロードする](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.vsdx) <br/> 更新日: 2020 年 11 月|含まれる内容: <ul><li>  Microsoft の情報保護およびデータ損失防止</li><li>アイテム保持ポリシーと保持ラベル </li><li>情報バリア</li><li>コミュニケーション コンプライアンス</li><li>インサイダー リスク</li><li>サードパーティのデータの取り込み</li>|

## <a name="conference-sessions"></a>会議セッション

Microsoft 365 グループと Teams のガバナンスの詳細については、次の会議セッションをご覧ください。

**基礎**

Microsoft 365 グループの基本と新しいイノベーションについて説明します。大規模な管理とガバナンス、使用状況と導入を促進するためのベスト プラクティス、セルフサービスを含む。

- [Microsoft 365 グループを受け入れる](https://www.youtube.com/watch?v=dAamBF1gb7M)

**ガバナンス**

グループの有効期限ライフサイクル、名前付けポリシー、分類ラベル、外部ゲストとのコラボレーションを設定し、グループ作成のアクセス許可を管理する方法について説明します。

- [365 グループでコラボレーションを変革し、シャドウ IT をOfficeする](https://www.youtube.com/watch?v=Bhf_bKx3lAg)

**顧客の例**

Microsoft 365 グループ、SharePoint、Teams、およびグループがどのように連携してグローバル なコラボレーション プラットフォームを提供Yammerの舞台裏の例を参照してください。

- [365 グループ、SharePoint、Teams、Officeグループとの共同作業のスイート スポットを見Yammer](https://www.youtube.com/watch?v=Rx9eVwqXeQk)

## <a name="see-also"></a>関連項目

[Microsoft 365 のセキュリティに関するドキュメント](../security/index.yml)

[Microsoft 365 コンプライアンスのドキュメント](../compliance/index.yml)