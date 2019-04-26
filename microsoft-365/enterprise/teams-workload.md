---
title: Microsoft 365 Enterprise の Microsoft Teams を展開する
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
ms.custom: ''
description: 組織全体で Microsoft 365 Enterprise の Microsoft Teams を計画、ロールアウトするプロセス、および Microsoft Teams の価値を引き出すプロセスについて、順を追って説明します。
ms.openlocfilehash: 646062babf525be176386264b4ef3c4a3a21647a
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291661"
---
# <a name="deploy-microsoft-teams-for-microsoft-365-enterprise"></a>Microsoft 365 Enterprise の Microsoft Teams を展開する

*このワークロードは、Microsoft 365 Enterprise の E3 および E5 の両バージョンに該当します*

Microsoft Teams には、チャット、会議、ドキュメント共有、会話スレッド機能が組み込まれており、コンテンツの作成とグループ間でのコンテンツの共有を容易にします。Teams は、Microsoft 365 Enterprise でチーム作業とコラボレーションを行うためのコンポーネントであり、Microsoft 365 の Built for Teamwork の価値を構成する重要な要素です。Teams を初めて利用する場合は、「[Microsoft Teams の概要](https://docs.microsoft.com/MicrosoftTeams/teams-overview)」を参照してください。
 
現在 Skype for Business を利用しているお客様には、現在 Microsoft は Teams への Skype for Business 機能の組み込みに取り組んでいることをお知らせします。少し時間をいただくことになるかもしれませんが、Teams は最終的にはシングル クライアント エクスペリエンスとなる予定です。Microsoft は、Skype for Business を利用しているお客様をサポートいたします。詳細については、「[Skype for Business から Microsoft Teams への移行](https://docs.microsoft.com/microsoftteams/journey-skypeforbusiness-teams)」を参照してください。

次に示すフェーズと手順では、組織における Teams の役割を想定し、段階的な一連のロールアウトにより組織が Teams の研修を行い、Teams の用途とエンドユーザーに対する Teams の価値を促進するプロセスを説明します。 

まず始める前に、チームに必要なセキュリティ機能が備わるように、適切な[基礎インフラストラクチャチャ](deploy-foundation-infrastructure.md)のフェーズが設定されていることを確認します。

## <a name="phase-1-envision"></a>フェーズ 1: 想定

このフェーズでは、Teams の展開にあたって関係者を招集し、組織でビジネス ニーズに対応するためどのように Teams を利用するかを決定します。

### <a name="step-1-gather-your-teams-deployment-members"></a>手順 1: Teams 展開メンバーを招集する
Microsoft 365 [基礎インフラストラクチャ](deploy-foundation-infrastructure.md)に Teams を適切に展開するには、意見やフィードバックを得るために適切な関係者を招集する必要があります。主な関係者は、事業部門の意思決定者、IT 担当者 (アーキテクトや実装担当者など)、エンドユーザーの代表者です。 

この 3 つのグループを招集することにより、Teams の展開に、ビジネス ニーズを反映した考慮事項と、ライセンスおよびセキュリティの技術的側面が反映され、Teams は標準的なユーザーが使用するアプリケーションになります。

#### <a name="result"></a>結果

組織の事業、技術、エンドユーザーの各側面を代表する関係者のリスト。

### <a name="step-2-determine-and-prioritize-your-teams-business-scenarios"></a>手順 2: Teams のビジネス シナリオを決定し優先順位を付ける
Teams はさまざまな目的に使用できます。ビジネス グループ、部門、個々の作業チームとプロジェクト チームといった組織の各レベルのビジネス ニーズと目的の対応関係を特定する必要があります。Teams のシナリオの定義に役立つ例については、「[Microsoft 365 Productivity Library](https://www.microsoft.com/en-us/microsoft-365/success/?rtc=1)」を参照してください。 

機敏で極めてコラボレーティブであり、密接に連携し、Exchange Online のメールにとどまらずさまざまな機能 (履歴記録機能を備えたライブ グループ チャット、一般的で見つけやすいファイルとメモの保存場所など) を必要とするチームに対処することを、Teams の目標とします。 

Teams のメリットを確認できる方法の 1 つとして、現在のチーム間のコミュニケーション方法を調べ、そのコミュニケーションを置き換えて共同作業を容易にする方法を提示する適切な Teams のシナリオを見つけ、追加機能を提供する方法があります。

Teams を使用すると、Microsoft 365 Enterprise の次の戦略的なビジネス シナリオを実現可能にします:

- チーム内でコミュニケーションを図って、最新の情報に精通し、意見を求め、団結力と考えの一致を高めます
- 現場担当者を連携させて、デジタル改革を可能にします
- 業務の習慣を理解して、影響力を増します

詳細については、「[Microsoft 365 を使用したデジタル改革](http://transform.microsoft.com)」を参照してください。 

#### <a name="microsoft-teams-for-highly-regulated-data"></a>厳しく規制されたデータに対応した Microsoft Teams

厳しく規制されたデータとは、地域の規制の対象になっているデータや、組織にとって最も重要なデータ (営業秘密、財務や人事の情報、組織戦略など) のことです。チームは、この種のデータのアクセス制限、データ分類、データ損失保護、暗号化に対応するように構成できます。詳細については、「[Microsoft Teams および SharePoint Online サイトで高度な規制データを扱うには](teams-sharepoint-online-sites-highly-regulated-data.md)」を参照してください。

#### <a name="result"></a>結果

組織における共同作業とチームワークのニーズに対応する一連の Teams のシナリオ。

## <a name="phase-2-onboard"></a>フェーズ 2: 研修

このフェーズでは、Teams の展開の技術的な側面を計画し、一部のユーザー グループへの Teams のロールアウトを開始します。

### <a name="prerequisites-identity-and-device-access-configuration"></a>前提条件: ID とデバイスのアクセス構成

チームへのアクセスを保護するには、[ID とデバイスのアクセス ポリシー](identity-access-policies.md)と、[推奨される SharePoint Online アクセス ポリシー](sharepoint-file-access-policies.md)を構成していることを確認します。

### <a name="step-1-complete-your-technical-planning"></a>手順 1: 技術計画を実施する

技術計画を開始する前に、FastTrack を使用するかどうかを決定します。組織のシート数が 50 を超えており、組織が[対象となるプラン](https://technet.microsoft.com/library/dn783224.aspx)に参加している場合、無料で提供されている [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365) を使用して、計画、展開、サービス導入を順に実施できます。あるいは、FastTrack Onboarding Wizard を使用してこの作業を各自で実施することもできます。FastTrack Onboarding Wizard は、Office 365 アカウントでサインインした後、[FastTrack](https://fasttrack.microsoft.com/) から利用できます。

各自で計画を策定している場合 (または FastTrack を使用している場合) には、ネットワークと組織が Teams を導入できる状態にあるかどうかを判断する必要があります。特に、[基礎インフラストラクチャ](deploy-foundation-infrastructure.md)のネットワークの終了条件を満たしており、Teams を使用した会議のパフォーマンスを最大限に引き出すため、帯域幅、スループット、トラフィック遅延に特別な注意を払うことが重要です。

次のリソースを使用して、Teams のロールアウトに向けた組織の技術的な側面を準備します。 

- [Teams の導入に向けた環境の準備を確認する](https://docs.microsoft.com/MicrosoftTeams/environment-readiness)
- [Teams 用に組織のネットワークを準備する](https://docs.microsoft.com/MicrosoftTeams/prepare-network)
- [Office 365 の URL と IP アドレス範囲](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges)

Teams のセキュリティについての理解を深めるには、次の追加リソースを参照してください。

- [Teams のセキュリティとコンプライアンスの概要](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview)
- [Office 365 グループと Teams](https://docs.microsoft.com/MicrosoftTeams/office-365-groups)
- [Teams でのゲスト アクセス](https://docs.microsoft.com/MicrosoftTeams/office-365-groups)

次に、以下のリソースを使用して、Team のライセンスを理解し、組織で Teams をセットアップします。

- [Teams の Office 365 ライセンス](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing)
- [Microsoft Teams へのユーザー アクセスを管理する](https://docs.microsoft.com/MicrosoftTeams/user-access)
- [Microsoft Teams のクライアントを取得する](https://docs.microsoft.com/MicrosoftTeams/get-clients)
- [Office 365 の組織で Microsoft Teams を有効にする](https://docs.microsoft.com/MicrosoftTeams/office-365-set-up)
- [Office 365 の組織で Microsoft Teams の機能を管理する](https://docs.microsoft.com/microsoftteams/enable-features-office-365)

#### <a name="result"></a>結果

ネットワーク、セキュリティ、Office 365 ライセンスの計画が完了し、組織内の一部のグループへの Teams のロールアウトを開始する準備ができています。

### <a name="step-2-run-an-it-pilot"></a>手順 2: IT パイロットを実施する

中規模～大規模な組織のほとんどでは、フェーズ 1 の関係者、早期導入者、熱心な技術者を集めて IT パイロットを実施する必要があります。IT パイロットでは、次の作業を行います。

- IT パイロット参加者が試すことができる Teams ビジネス シナリオを選択します。アイディアについては、「[Microsoft Teams 作業開始キット](http://microsoft.com/download/56505)」を参照してください。
- パイロット参加者に対し、Teams を使用したチャット、ファイル保存、会議などの機能をテストするための演習課題を提示します。
- 変更管理戦略を決定し、組織全体のユーザーによる受け入れを促進するための資料を作成します。変更管理資料には、電子メールの発表文、社内トレーニング計画、通路用ポスター、プレゼンテーションなどが含まれます。これらの資料は、Teams に対する関心を高め、利用を促進することを目標とし、組織全体に Team とそのメリットを伝達します。いくつかのアイディアについては、「[Microsoft Teams の変更管理戦略](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy)」を参照してください。
- IT パイロットの参加者に、各自の経験に基づく変更管理戦略の資料のレビューを依頼します。参加者から、ベスト プラクティスに関するヒントや、Teams のメリットを説明する最適な方法および共同作業とチームワークに Teams を使用する方法に関するアドバイスを得られる可能性があります。

#### <a name="result"></a>結果

Teams の IT パイロットが完了し、最初の変更管理資料の作成、レビュー、調整が行われます。

### <a name="step-3-roll-out-to-a-business-group"></a>手順 3: ビジネス グループへロールアウトする

IT パイロットの完了後に、Teams を組織内のビジネス グループまたは部門にロールアウトします。このロールアウトでは、次の作業を行います。

- ビジネス グループにおける Teams の重要なビジネス シナリオの決定。
- 部門、作業チーム、プロジェクト チームにおける Teams の用途の想定事項とタイムラインをユーザーに伝達するアナウンスメント アクティビティ。
- Teams に関する直接的なユーザー トレーニング、または Teams とその使用法を紹介するリソースへのリンク。
- ビジネス グループのユーザーからのコメントや問題点の指摘を収集するフィードバック メカニズム (ビジネス グループのメンバー全員が含まれている中央チームなど)。

ロールアウト中には、組織全体でのロールアウトに備えて変更管理資料を調整できます。

#### <a name="result"></a>結果

ビジネス グループの 1 つは Teams を運用しており、変更管理資料のテストと調整が完了しています。

## <a name="phase-3-drive-value"></a>フェーズ 3: 価値を引き出す

このフェーズでは、組織への Teams のロールアウトを実施し、ユーザーが Teams のメリットを実感できるようにユーザーをサポートします。

### <a name="step-1-roll-out-teams-to-the-rest-of-your-organization"></a>手順 1: 組織のその他の部分に Teams をロールアウトする

対象となるビジネス グループへのロールアウトが完了したら、Teams を組織のその他の部分にロールアウトします。このロールアウトでは、次の作業を行います。

- 個々のビジネス グループにおける Teams の重要なビジネス シナリオの決定。
- 部門、作業チーム、プロジェクト チームにおける Teams の用途の想定事項とタイムラインをユーザーに伝達するアナウンスメント アクティビティに、調整した変更管理資料を使用する。
- Teams のユーザー トレーニングまたは Teams とその使用法を紹介するリソースへのリンクを提供する。「[Microsoft Teams のエンド ユーザー トレーニング](https://docs.microsoft.com/microsoftteams/enduser-training)」にあるトレーニング リソースを参照してください。
- 組織のユーザーからのコメントや問題点の指摘を収集するフィードバック メカニズム (すべてのユーザーが含まれている中央チームなど)。組織の従業員数が 2500 人未満の場合は、Teams のパブリック チャネルを使用し、2500 人以上の場合は Yammer のパブリック グループを使用してください。

#### <a name="result"></a>結果

組織は Teams を運用しており、Teams の使用を開始するための情報を伝達し、トレーニングを実施し、使用を開始できるようにする変更管理戦略を実施しています。

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>手順 2: 使用状況を測定し、満足度を管理し、導入を促進する

Teams を組織全体にロールアウトしたら、次の目的で変更管理戦略を引き続き採用する必要があります。

- Teams を組織のチームワークおよびコラボレーション ツールとして推進する点でリーダーシップを発揮する。
- ビジネス グループ、部門、作業チーム、プロジェクト チームでのコミュニケーションおよびコラボレーションに Teams を使用するよう各従業員を促す。

推奨されるアクティビティの一部を次に示します。

- 「[Office 365 導入ガイド](https://aka.ms/successfactors)」を参照して、クラウド サービス導入の一般的なベスト プラクティスを理解します。 
- 「[Office 365 アクティビティ レポート](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)」を参照して、組織全体での Office 365 サービスの使用について理解します。組織の Office 365 全体管理者ではない場合は、ユーザー アカウントに Reports Reader 権限を付与できる管理者に権限の付与を依頼し、アクティビティ レポートにアクセスできるようにしてください。
- フィードバック機能 (中央チームまたは Yammer のパブリック チャネル) を監視し、各メンバーからの Teams を使用した上での問題の指摘やフィードバックがないか確認します。質問や問題には可能な限り迅速に対応し、メンバーが Teams に対し不満を抱えたり Teams を放棄したりすることがないようにします。
- 各ビジネス グループのチャンピオンを特定して育成し、Teams を使用して達成できた内容やベスト プラクティスを強調します。チャンピオンの成功事例を組織に反映し、プロジェクトの成功と導入を紹介します。ビジネス グループ内の技術リーダーからの支持は、他のリーダーや同僚に大きな影響を及ぼします。

#### <a name="result"></a>結果

組織のコラボレーションおよびチームワーク ツールとして Teams が導入されます。

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft での Microsoft 365 Enterprise の活用方法

Microsoft がどのように Microsoft Teams を展開し、コラボレーションに使用しているかについては下記を参照してください。

- [Microsoft Teams の展開により、コラボレーションが効率化し、チームワークが向上する](https://www.microsoft.com/itshowcase/Article/Content/1013/Deploying-Microsoft-Teams-streamlines-collaboration-and-improves-teamwork)
- [Microsoft Teams は Microsoft の最新の職場でのコラボレーションを向上させる](https://www.microsoft.com/itshowcase/Article/Content/1012/Microsoft-Teams-increases-collaboration-in-the-modern-workplace-at-Microsoft)

## <a name="next-steps"></a>次の手順

- [Office 365 の組織で Microsoft Teams の機能を管理する](https://docs.microsoft.com/microsoftteams/enable-features-office-365)
- [Microsoft Teams の管理者トレーニング](https://docs.microsoft.com/microsoftteams/itadmin-readiness)
