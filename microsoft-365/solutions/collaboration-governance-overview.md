---
title: コラボレーションガバナンスとは
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
description: Microsoft 365 グループ、Teams、SharePoint、Yammer の関連する機能を管理する方法について説明します。
ms.openlocfilehash: 2319a0f5b8c74925569d00eb781d247fe61a5a76
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613034"
---
# <a name="what-is-collaboration-governance"></a>コラボレーションガバナンスとは

コラボレーションガバナンスは、ユーザーがリソースへのアクセスを管理し、ビジネス標準に準拠し、データのセキュリティを確保する方法です。

今日、組織は多様なツールセットを使用しています。 開発者は、チームチャット、メールを送信する役員、およびエンタープライズソーシャルを介して接続する組織全体を使用しています。 グループはそれぞれ一意であり、独自の機能上のニーズと作業スタイルがあるため、複数のコラボレーションツールが使用されています。 一部のユーザーはメールのみを使用し、他のユーザーは主にチャットに住んでいます。 

ユーザーは、IT が提供するツールがニーズに合わないと思った場合、自分のシナリオに対応するお気に入りのコンシューマー アプリをダウンロードすることになるでしょう。 このプロセスにより、ユーザーはすぐに使い始めることができますが、複数のログイン、共有の困難さ、コンテンツの閲覧場所の不足など、組織全体でユーザー エクスペリエンスが低下します。 この概念は「シャドウ IT」と呼ばれ、組織に重大なリスクをもたらします。 これにより、ユーザー アクセスを均一に管理し、セキュリティとサービス コンプライアンスのニーズを保証できる機能が減ります。

Microsoft 365 グループ、Teams、Yammer などのサービスは、ユーザーを強化し、共同作業に必要なツールを提供することで IT のシャドウを軽減します。 Microsoft 365 には、組織で必要となる可能性があるすべてのガバナンス機能を実装するための豊富なツールセットがあります。 

![Microsoft 365 のコラボレーションガバナンスオプションを示す図](../media/collaboration-governance-overview.png)

この一連の記事では、グループ、チーム、および SharePoint の設定がどのように連携するか、使用できるガバナンス機能、Microsoft 365 のコラボレーション機能のガバナンス計画を作成および実装する方法について理解するのに役立ちます。

## <a name="what-are-microsoft-365-groups"></a>Microsoft 365 グループとは

Microsoft 365 グループでは、共同作業を希望するユーザーのセットを選択し、それらのユーザーが共有するリソースのコレクションを簡単にセットアップすることができます。 グループにメンバーを追加すると、グループによって提供されるすべての資産に対して必要なアクセス許可が自動的に付与されます。 Teams と Yammer は、両方とも Microsoft 365 グループを使用してメンバーシップを管理します。

Microsoft 365 グループには、ユーザーがコミュニケーションとコラボレーションに使用できるリンクされたリソースのセットが含まれています。 グループには、常に SharePoint サイト、Planner、Power BI ワークスペース、メールボックスとカレンダー、およびストリームが含まれます。 グループの作成方法によっては、必要に応じて Teams、Yammer、Project などの他のサービスを追加することもできます。

![Microsoft 365 グループと関連サービスを示す図](../media/microsoft-365-groups-hub-spoke.png)

|関連情報|説明|
|:------|:----------|
|[Calendar](https://support.office.com/article/schedule-a-meeting-on-a-group-calendar-in-outlook-0cf1ad68-1034-4306-b367-d75e9818376a)|グループに関連するイベントのスケジューリング|
|[[Inbox (受信トレイ)](https://support.office.com/article/have-a-group-conversation-in-outlook-a0482e24-a769-4e39-a5ba-a7c56e828b22)]|グループメンバー間の電子メールの会話の場合。 この受信トレイにはメールアドレスが設定されており、従来の配布リストのように、グループ外のユーザーや組織外からのメッセージを受け付けるように設定できます。|
|[OneNote ノートブック](https://support.office.com/article/get-started-with-onenote-e768fafa-8f9b-4eac-8600-65aa10b2fe97)|アイデア、研究、情報を収集するための情報|
|[Planner](https://support.office.com/article/microsoft-planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc)|グループメンバー間でのプロジェクトタスクの割り当ておよび管理について|
|[Power BI ワークスペース](https://docs.microsoft.com/power-bi/collaborate-share/service-new-workspaces)|ダッシュボードとレポートを使用したデータコラボレーションスペース|
|[プロジェクトとロードマップ](https://support.microsoft.com/project)|Web ベースのプロジェクト管理ツール|
|[SharePoint チーム サイト](https://support.office.com/article/what-is-a-sharepoint-team-site-75545757-36c3-46a7-beed-0aaa74f0401e)|グループに関連する情報、リンク、およびコンテンツの中央リポジトリ|
|[Stream](https://support.microsoft.com/microsoft-stream)|ビデオストリーミングサービス|
|[Teams](https://support.microsoft.com/teams)|Microsoft 365 のチャットベースのワークスペース|
|[Yammer グループ](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)|会話を行い、情報を共有するための共通の場所|

Microsoft 365 グループには、組織内のグループの管理に役立つ、有効期限ポリシー、命名規則、ブロックされた単語ポリシーなど、さまざまなガバナンスコントロールが含まれています。 グループはメンバーシップを制御し、この一連のリソースにアクセスするため、グループの管理は Microsoft 365 でのグループ作業の重要な部分です。

## <a name="define-a-collaboration-strategy-for-your-organization"></a>組織のグループ作業戦略を定義する

複数の場所で共同作業を行ったり、Microsoft 365 内で会話したりすることができます。 ユーザーが会話を開始できる場所を理解することは、コミュニケーションの戦略を定義するのに役立ちます。

Microsoft 365 では、次の3つの主要な通信方法がサポートされています。

- Outlook: グループの受信トレイと予定表が共有される電子メールを通じた共同作業
- Microsoft Teams: 特定のサブグループによって開催される、さまざまなトピックに関する非公式でリアルタイム会話を可能にする常設チャットベースのワークスペース。
- Yammer: 共同作業のためのエンタープライズ ソーシャル エクスペリエンス

![Teams、Yammer、Outlook をいつ使用するかを示す図](../media/inner-loop-outer-loop.png)

- Teams: チャット ベースのワークスペース (高速なコミュケーション) – 内部ループ
  - ユーザーが毎日操作するユーザーとの共同作業のために構築されています。
  - 単一のエクスペリエンスでユーザーが簡単に情報を得られるようにします
  - タブ、コネクタおよびボットを追加します
  - Live chat、音声ビデオ会議、レコーディングされた会議

- Yammer: 組織全体をつなぐ (エンタープライズ ソーシャル) – 外部ループ
  - 共通の利息や専門知識を共有しているが、必ずしも日常的に共同作業するわけではないユーザーの、社内で働くグループのコミュニティ。
  - リーダーのつながり、学習コミュニティ、役割ベースのコミュニティ

- メールボックスと予定表 (電子メールベースのコラボレーション)
  - ユーザーグループとの対象指定した通信に使用されます。
  - 他のグループメンバーとの会議の共有予定表
 
Microsoft 365 でコラボレーション機能を使用する方法を決定する際には、これらの通信方法と、ユーザーがさまざまなシナリオで使用する可能性があることを検討してください。

> [!NOTE]
> Yammer または Teams によって作成された新しい Office 365 グループは、そのグループのユーザー間の主なコミュニケーションが各自の個別のクライアントで行われるため、Outlook やアドレス帳には表示されません。 Yammer グループを Teams に接続することはできません。


## <a name="best-practices"></a>ベスト プラクティス

ガバナンス計画プロセスを開始する際には、次のベストプラクティスに留意してください。

- **ユーザーに** 連絡して、グループ作業機能の最大ユーザーを特定し、ビジネス上の重要な要件とユースケースシナリオを理解できるようにします。

- **リスクとメリットのバランス** -ビジネス、規制、法律、およびコンプライアンスのニーズを確認し、すべての結果を最適化するソリューションを計画します。

- さまざまな **組織やさまざまな種類のコンテンツとシナリオに適応** します。さまざまなグループまたは部署のさまざまなニーズと、イントラネットコンテンツとユーザーの OneDrive コンテンツとの異なる種類のコンテンツについて考慮します。

- **ビジネスの優先度に合わせる** -ビジネス目標は、ガバナンスに投資するために必要な時間と労力を定義するのに役立ちます。

- **作成するソリューションに、ガバナンスに関する決定を直接埋め込む** -Microsoft 365 の機能をオンまたはオフにすることで、多くのガバナンス決定を実装できます。

- Microsoft が提供するトレーニングを使用して組織固有の予想を強化するために、トレーニングに適応するソリューション ( [microsoft 365 learning](https://docs.microsoft.com/office365/customlearning)の方法) を **補強** してください。

- **組織内のガバナンスポリシーとガイドラインを伝える戦略があり** ます。ポリシーと手順を伝達するために、SharePoint コミュニケーションサイトに Microsoft 365 導入センターを作成します。

- **役割と責任の定義** -ガバナンスコアチームを特定し、最初にプロビジョニングと名前付けと外部アクセスに関する重要なガバナンス上の決定を行って作業を進め、次に残りの決定について説明します。

- **ビジネスとテクノロジの変更に応じて** 、定期的に会議を見直し、新しい機能と新しいビジネスの期待を確認します。

これらのベストプラクティスの詳細については、「 [共同作業ガバナンス計画を作成](collaboration-governance-first.md)する」を参照してください。

## <a name="end-user-impact-and-change-management"></a>エンドユーザーへの影響と変更の管理

グループと teams はいくつかの方法で作成できるので、組織に最適な方法を使用するようにユーザーをトレーニングすることをお勧めします。

- 組織が電子メールを使用して通信の大部分を行う場合は、Outlook でグループを作成するようにユーザーに指示します。
- 組織が SharePoint を頻繁に使用している場合やオンプレミスの SharePoint から移行している場合は、ユーザーに共同作業用の SharePoint チームサイトを作成するように指示します。
- 組織で Teams を展開している場合は、チームを作成するようにユーザーに指示します。グループ作業スペースが必要な場合。

これにより、ユーザーが関連するサービスにグループを関連付ける方法に不慣れな場合に混乱を避けることができます。 ユーザーにグループについての会話を行う方法の詳細については、「 [ユーザーへの Microsoft 365 グループの説明](../admin/create-groups/explain-groups-knowledge-worker.md)」を参照してください。

## <a name="key-governance-capabilities-and-licensing-requirements"></a>主要なガバナンス機能とライセンス要件

Microsoft 365 のコラボレーションのためのガバナンス機能には、Microsoft 365、Teams、SharePoint、Azure Active Directory の機能が含まれています。

| 機能 | 説明 | ライセンス |
|:----------------------|:------------|:----------|
|チームとサイトの共有|チーム、グループ、およびサイトを組織外のユーザーと共有できるかどうかを制御します。|Microsoft 365 E5 または E3|
|ドメイン許可/ブロック|組織外のユーザーと特定のドメインのユーザーとの共有を制限します。|Microsoft 365 E5 または E3|
|セルフサービス サイト作成|ユーザーが自分の SharePoint サイトを作成することを許可または禁止します。|Microsoft 365 E5 または E3|
|制限されたサイトとファイル共有|サイト、ファイル、およびフォルダーの共有を特定のセキュリティグループのメンバーに制限します。|Microsoft 365 E5 または E3|
|制限されたグループの作成|チームおよびグループの作成を特定のセキュリティグループのメンバーに制限します。|Microsoft 365 E5 または E3 (Azure AD Premium または Azure AD Basic EDU ライセンス)|
|グループの名前付けポリシー|グループ名とチーム名に接頭辞または接尾辞を適用します。|Microsoft 365 E5 または E3 (Azure AD Premium または Azure AD Basic EDU ライセンス)|
|グループの有効期限ポリシー|非アクティブなグループと teams を期限切れにし、指定した期間が経過した後に削除するように設定します。|Microsoft 365 E5 または E3 (Azure AD Premium ライセンスを使用)|
|グループごとのゲスト アクセス|グループごとに、組織外のユーザーとのチームおよびグループの共有を許可または禁止します。|Microsoft 365 E5 または E3|

## <a name="collaboration-governance-planning-step-by-step"></a>コラボレーションガバナンスの計画のステップバイステップ

ガバナンス計画を作成するには、次の基本的な手順に従います。

1. 主なビジネス目標とプロセスを検討し、ビジネスのニーズを満たすための [ガバナンス計画を作成](collaboration-governance-first.md) します。
2. Groups および sharepoint[および Teams](groups-sharepoint-teams-governance.md)および[その他のサービス](groups-services-interactions.md)の設定と同様に、[グループおよび sharepoint で](groups-sharepoint-governance.md)の設定については、「サービスの設定について」を確認してください。 ガバナンス戦略を計画する際には、これらの相互作用について理解しておいてください。
3. ユーザーアクセスの管理を計画する- [グループ、SharePoint、および Teams でユーザーに付与するアクセスレベル](groups-teams-access-governance.md)を計画します。
4. コンプライアンス設定の管理を計画する- [Microsoft 365 グループ、チーム、および SharePoint グループ作業のため](groups-teams-compliance-governance.md)に利用可能なコンプライアンスオプションを確認します。
5. 通信の管理を計画する- [グループ作業のシナリオ](groups-teams-communication-governance.md)で利用可能なコミュニケーションガバナンスオプションを確認します。
6. 組織およびライフサイクル管理の計画- [グループおよびチームの作成、名前付け、有効期限、アーカイブに使用するポリシー](plan-organization-lifecycle-governance.md)を選択します。 また、[グループ、teams、Yammer のライフサイクルオプションの終了](end-life-cycle-groups-teams-sites-yammer.md)について理解します。

![推奨されるガバナンス手順の図](../media/collaboration-governance-steps.png)

## <a name="training-for-administrators"></a>管理者向けのトレーニング

これらのトレーニングモジュールは、Teams と SharePoint のコラボレーション機能を理解するのに役立ちます。

#### <a name="teams"></a>Teams

|用|Microsoft Teams を使用してチームの共同作業を管理する|
|:---|:---|
|![Teams トレーニングアイコン](../media/manage-team-collaboration-with-microsoft-teams.svg)|「Microsoft Teams を使用してチームの共同作業を管理する」では、Microsoft 365 でのチームの共同作業の中央のハブである Microsoft Teams の機能について説明します。 Teams を使用して、Office 365 アプリケーションの充実した機能を最大限に活用しながらオンプレミスとオフプレミスの両方で、デスクトップからタブレット、携帯電話までさまざまなデバイス上で組織内のチームワークとコミュニケーションを円滑に進める方法を習得できます。 Teams が、共同作業のための包括的で柔軟な環境をさまざまなアプリケーションやデバイスで提供する方法について説明します。 このラーニングパスはMicrosoft 365 認定: Teams 管理者 の認定の準備を行うことができます。<br><br>2時間17分の低学習パス-5 モジュール|

> [!div class="nextstepaction"]
> [開始 >](https://docs.microsoft.com/learn/modules/m365-teams-collab-prepare-deployment/introduction/)

#### <a name="sharepoint"></a>SharePoint

|用|Microsoft 365 で SharePoint を使用して共同作業する|
|:---|:---|
|![SharePoint トレーニングアイコン](../media/collaborate-with-sharepoint-in-microsoft-365.svg)|「Microsoft SharePoint で共有コンテンツを管理する」では、SharePoint の特徴と機能および Microsoft 365 と連携する仕組みについて紹介します。 ハブ サイトなど、さまざまな種類の SharePoint サイトだけでなく、情報保護、レポート、監視についても説明します。 さらに、SharePoint のファイルとフォルダーの共有を使用してコラボレーションを最適化する方法、外部でファイルを共有する方法、SharePoint 管理センターで SharePoint サイトを管理する方法も説明します。 このラーニングパスはMicrosoft 365 認定: チームワーク管理者の関連付け の認定の準備を行うことができます。<br><br>1時間14分-学習パス-4 モジュール|

> [!div class="nextstepaction"]
> [開始 >](https://docs.microsoft.com/learn/modules/m365-teams-sharepoint-plan-sharepoint/introduction/)

## <a name="training-for-end-users"></a>エンド ユーザー向けのトレーニング

これらのトレーニングモジュールは、ユーザーが Microsoft 365 の共同作業に Teams、グループ、SharePoint を使用するのに役立ちます。

|Teams|SharePoint|
|:---|:---|
|![チームトレーニングアイコンを設定およびカスタマイズする](../media/set-up-customize-team-training.png)<br>**[チームをセットアップしてカスタマイズする](https://support.microsoft.com/office/702a2977-e662-4038-bef5-bdf8ee47b17b)**|![SharePoint 共有と同期トレーニングアイコン](../media/sharepoint-share-sync-training.png)<br>**[共有と同期](https://support.microsoft.com/office/98cb2ff2-c27e-42ea-b055-c2d895f8a5de)**|
|![Teams のアップロードとファイルの検索トレーニングアイコン](../media/smc-teams-upload-find-files-training.png)<br>**[ファイルをアップロードして検索する](https://support.microsoft.com/office/57b669db-678e-424e-b0a0-15d19215cb12)**||
|![Teams およびチャネルでのコラボレーションアイコン](../media/teams-collaborate-channels-training.png)<br>**[Teams およびチャネルでの共同作業](https://support.microsoft.com/office/c3d63c10-77d5-4204-a566-53ddcf723b46)**|||

## <a name="illustrations"></a>示さ

これらの図は、グループと teams が Microsoft 365 の他のサービスとどのように関係しているかを理解するのに役立ちます。また、組織でこれらのサービスを管理するために利用できるガバナンスとコンプライアンスの機能についても説明します。

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

### <a name="microsoft-365-information-protection-and-compliance-capabilities"></a>Microsoft 365 の情報保護とコンプライアンスの機能

Microsoft 365 には、幅広い情報保護とコンプライアンス機能が含まれています。 Microsoft の生産性ツールと共に、これらの機能は、組織がリアルタイムで共同作業を行って、厳格な規制コンプライアンスフレームワークに準拠できるように設計されています。 

この一連の図では、最も規制されている業界の金融サービスの1つを使用して、これらの機能を適用して一般的な規制要件に対応する方法を示します。 これらのイラストを自分の用途に合わせて自由にアレンジしてください。 


| アイテム | 説明 |
|:-----|:-----|
|[![モデル ポスター: Microsoft 365 の情報保護とコンプライアンスの機能](../media/solutions-architecture-center/m365-compliance-illustrations-thumb.png)](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf) <br/> 英語: [PDF としてダウンロードする](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf)  \| [Visio としてダウンロードする](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.vsdx) <br/> 日本語: [PDF としてダウンロードする](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.pdf)  \| [Visio としてダウンロードする](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.vsdx) <br/> 更新日: 2020 年 11 月|含まれる内容: <ul><li>  Microsoft の情報保護およびデータ損失防止</li><li>アイテム保持ポリシーと保持ラベル </li><li>情報バリア</li><li>コミュニケーション コンプライアンス</li><li>インサイダー リスク</li><li>サードパーティのデータの取り込み</li>|

## <a name="conference-sessions"></a>会議セッション

Microsoft 365 グループと Teams のガバナンスの詳細については、これらの電話会議セッションをご覧ください。

**事柄**

スケールでの管理とガバナンス、使用方法と導入のためのベストプラクティス、セルフサービスなど、Microsoft 365 グループの基本技術および新技術技術について説明します。

- [Microsoft 365 グループを採用する](https://www.youtube.com/watch?v=dAamBF1gb7M)

**ガバナンス**

グループの有効期限のライフサイクル、命名ポリシー、分類ラベル、外部ゲストとのコラボレーション、グループ作成のアクセス許可の管理方法について説明します。

- [コラボレーションを変革し、Office 365 グループとの統合を促進する](https://www.youtube.com/watch?v=Bhf_bKx3lAg)

**お客様の例**

グローバルなコラボレーションプラットフォームを提供するために、Microsoft 365 グループ、SharePoint、Teams、Yammer がどのように連携するかについて、舞台裏の例を参照してください。

- [Office 365 グループ、SharePoint、Teams、Yammer を使用してコラボレーションを検索する](https://www.youtube.com/watch?v=Rx9eVwqXeQk)
