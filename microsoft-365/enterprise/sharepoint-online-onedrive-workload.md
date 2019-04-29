---
title: SharePoint Online と OneDrive for Business を Microsoft 365 Enterprise 向けに展開する
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
ms.custom: ''
description: 組織全体で Microsoft 365 Enterprise の SharePoint Online を計画、ロールアウトするプロセス、および SharePoint Online の価値を引き出すプロセスについて、順を追って説明します。
ms.openlocfilehash: 30fe3a971a869a4609d6b8ef2809692b4d4e5420
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290901"
---
# <a name="deploy-sharepoint-online-and-onedrive-for-business-for-microsoft-365-enterprise"></a>SharePoint Online と OneDrive for Business を Microsoft 365 Enterprise 向けに展開する

*このワークロードは、Microsoft 365 Enterprise の E3 および E5 の両バージョンに該当します*

SharePoint Online と Microsoft Teams は、ファイルの保存と共有、コンテンツ管理、コラボレーションの方法を提供するもので、Microsoft 365 Enterprise のチームワーク用ビルドの価値を引き出す重要な要素です。 

SharePoint Online には、アクセスの制御、アクセス許可、移動中および静的データの暗号化を含む、高度なセキュリティ機能も備わっています。SharePoint Online のセキュリティは、Microsoft 365 Enterprise のインテリジェント セキュリティの価値を引き出す重要な要素です。

SharePoint Online を初めて使用する方は、「[SharePoint Online](https://products.office.com/sharepoint/sharepoint-online-collaboration-software)」と「[SharePoint を使い始める](https://support.office.com/article/Get-started-with-SharePoint-3a26444b-08c5-46ad-b80a-cda82b11b27b#ID0EAABAAA=Basics)」を参照してください。

次に示す各フェーズと手順では、組織における SharePoint Online の役割を想定し、段階的な一連のロールアウトにより組織の研修を行い、それらの使用とエンドユーザーに対する価値を促進するプロセスを説明します。 まず始める前に、SharePoint Online サイトに必要なセキュリティ機能が備わるように、適切な[基礎インフラストラクチャチャ](deploy-foundation-infrastructure.md)のフェーズが設定されていることを確認します。 

OneDrive for Business を Microsoft 365 Enterprise 向けに展開する方法については、[エンタープライズ向けの OneDrive ガイド](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise)を参照してください。

## <a name="phase-1-envision"></a>フェーズ 1: 想定
このフェーズでは、SharePoint Online の展開にあたって関係者を招集し、組織でビジネス ニーズに対応するため、どのようにそれらを利用するかを決定します。

### <a name="step-1-gather-your-sharepoint-online-deployment-members"></a>手順 1: SharePoint Online の展開メンバーを収集する

[Microsoft 365 Enterprise の基礎インフラストラクチャ](deploy-foundation-infrastructure.md)に SharePoint Online を適切に展開するには、意見やフィードバックを得るために適切な関係者を招集する必要があります。主な関係者は、事業部門の意思決定者、IT 担当者 (アーキテクトや実装担当者など)、エンドユーザーの代表者です。 

この 3 つのグループを招集することにより、展開には、ビジネス ニーズを反映した考慮事項と、フォルダーとドキュメントの移行およびセキュリティの技術的側面が反映され、結果は標準的なユーザーが使用するものになります。

#### <a name="result"></a>結果

組織の事業、技術、エンドユーザーの各側面を代表する関係者のリスト。

### <a name="step-2-determine-and-prioritize-your-sharepoint-online-business-scenarios"></a>手順 2: SharePoint Online のビジネス シナリオを決定し、優先順位を付ける

SharePoint Online はさまざまな目的で使用できます。どの目的がビジネス ニーズに当てはまるかを確認する必要があります。SharePoint Online のターゲットとして、チーム、事業部、または組織全体のコラボレーションのニーズに対応する、ドキュメントの保存と共有、コンテンツ管理、コラボレーションを対象とする必要があります。 

[SharePoint Online](https://products.office.com/sharepoint/sharepoint-online-collaboration-software) のシナリオと機能の一覧を参照してください。

ビジネスの柱となる次の要素を、組織のニーズに対応させることができます。

|||
|:-----|:-----|
| 共有と共同作業 | チーム サイトの活用、コラボレーション サイト、および同期。 |
| 情報伝達と連携 | 今後入ってくる情報。 |
| 変換 | フローを使って、ストアまたはワークフローを作成します。 |
| 集合的な知識の利用 | 検索を使用して、組織内で目的とする結果が得られます。 |
| 保護 | 組織がセキュリティで保護されており、適切なコンプライアンスを達成していることを確認します。 |
| 外部/開発 | 開発組織により、SharePoint Framework を使用してソリューションやアプリをカスタマイズします。 |
|||

各自のニーズに合わせて SharePoint Online を構成する方法に関するリソースについては、「[SharePoint Online の管理](https://docs.microsoft.com/sharepoint/sharepoint-online)」を参照してください。

SharePoint Online の利点を調べる 1 つの方法は、個人、チーム、部門、または組織全体が現在、どのようにやり取りしているかを調べたうえで、ファイルの保存と共有の共同作業をより簡単に行う適切なシナリオを探すことです。シナリオによっては、[Microsoft Teams](teams-workload.md) がより良い選択になり得ることを念頭においてください。

SharePoint Online を使用すると、Microsoft 365 Enterprise の次の戦略的なビジネス シナリオが実現可能になります:

- チーム内でコミュニケーションを図って、最新の情報に精通し、意見を求め、団結力と考えの一致を高めます
- 集合的な知識の利用
- ユーザーがビジネス プロセスを変換するよう支援します
- 企業文化を形作る
- プロジェクト、タスク、期限を管理して、ビジネス目標を達成します
- 現場担当者を連携させて、デジタル改革を可能にします
- 業務の習慣を理解して、影響力を増します
- パートナー、同僚、顧客とコミュニケーションをとります。
- 組織内外でファイルを保存および共有して、組織の境界を越えてシームレスに作業を行います
- 柔軟なワーク スタイルを維持しながら、いつでもどこでもデバイスを使って多くのことを安全に成し遂げることができます
- 情報を保護して、データ損失のリスクを軽減します
- 一般データ保護規則 (GDPR) に適合するように、強化されたプライバシーと法令遵守によって組織をサポートします。

詳細については、「[Microsoft 365 を使用したデジタル改革](http://transform.microsoft.com)」を参照してください。 

#### <a name="sharepoint-online-site-for-highly-regulated-data"></a>厳しく規制されたデータに対応した SharePoint Online サイト

厳しく規制されたデータとは、地域の規制の対象になっているデータや、組織にとって最も重要なデータ (営業秘密、財務や人事の情報、組織戦略など) のことです。SharePoint Online サイトは、この種のデータのアクセス制限、データ分類、データ損失保護、暗号化に対応するように構成できます。詳細については、「[Microsoft Teams および SharePoint Online サイトで高度な規制データを扱うには](teams-sharepoint-online-sites-highly-regulated-data.md)」を参照してください。

#### <a name="result"></a>結果
ドキュメントの保存と共有、コンテンツ管理、コラボレーションに関する組織のニーズに対応する SharePoint Online のシナリオの一覧。

## <a name="phase-2-onboard"></a>フェーズ 2: 研修

このフェーズでは、SharePoint Online の展開の技術的な側面を計画した後、選択したユーザー グループへのロールアウトを開始します。

### <a name="prerequisites-identity-and-device-access-configuration"></a>前提条件: ID とデバイスのアクセス構成

SharePoint Online サイトへのアクセスを保護するには、[ID とデバイスのアクセス ポリシー](identity-access-policies.md)と、[推奨される SharePoint Online アクセス ポリシー](sharepoint-file-access-policies.md)を構成していることを確認する必要があります。

### <a name="step-1-complete-your-technical-planning"></a>手順 1: 技術計画を実施する

技術計画を開始する前に、FastTrack を使用するかどうかを決定します。組織のシート数が 50 を超えており、組織が[対象となるプラン](https://technet.microsoft.com/library/dn783224.aspx)に参加している場合、無料で提供されている FastTrack の特典を使用して、計画、展開、サービス導入を順に実施できます。あるいは、FastTrack Onboarding Wizard を使用してこの作業を各自で実施することもできます。FastTrack Onboarding Wizard は、Office 365 アカウントでサインインした後、[FastTrack](https://fasttrack.microsoft.com/) から利用できます。

各自で計画を策定している場合、または FastTrack を使用している場合には、ネットワークと組織が SharePoint Online を導入できる状態にあるかどうかを判断する必要があります。特に、基礎インフラストラクチャのネットワークの終了条件を満たしており、SharePoint Online ベースのドキュメントのための追加トラフィックのパフォーマンスを最大限に引き出すため、インターネット帯域幅、スループット、トラフィック遅延に特別な注意を払うことが重要です。

SharePoint Online のロールアウトの技術的な側面に備えるには、以下のリソースを使用します。 

- [SharePoint Online の計画ガイド](https://support.office.com/article/sharepoint-online-planning-guide-abacd1bb-295d-4235-afdd-15f5e4cc2e6c)
- [SharePoint Online に移行する](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online) 

SharePoint Online でのセキュリティの詳細については、次のリソースを参照してください。

-   [SharePoint Online と OneDrive がクラウド内のデータを保護する方法](https://support.office.com/article/How-SharePoint-Online-and-OneDrive-safeguard-your-data-in-the-cloud-5aa038e8-8ff0-4704-9e6a-fd72af0a2035)
-   [OneDrive for Business および SharePoint Online におけるデータ暗号化](https://support.office.com/article/Data-Encryption-in-OneDrive-for-Business-and-SharePoint-Online-6501B5EF-6BF7-43DF-B60D-F65781847D6C)

#### <a name="result"></a>結果

SharePoint Online サイトとオンプレミス フォルダーおよびドキュメントの移行とセキュリティについて理解し、組織内の選択したグループへの SharePoint Online のロールアウトを開始する準備ができました。

### <a name="step-2-run-an-it-pilot"></a>手順 2: IT パイロットを実施する

中規模～大規模な組織のほとんどでは、フェーズ 1 の関係者、早期導入者、熱心な技術者を集めて IT パイロットを実施する必要があります。IT パイロットでは、次の作業を行います。

- IT パイロット参加者の練習に使用できる SharePoint Online のビジネス シナリオを選択します。
- パイロット参加者に、SharePoint Online ドキュメントの保存/共有/コラボレーション、チーム ベースのスケジューリング、その他の能力をテストするための一連の演習を実施します。
- 変更管理戦略を決定し、組織全体のユーザーによる SharePoint Online の受け入れを促進するための資料を作成します。変更管理資料には、電子メールの発表文、社内トレーニング計画、通路用ポスター、プレゼンテーションなどが含まれます。これらの資料は、SharePoint Online に対する関心を高め、利用を促進することを目標とし、組織全体に Team とそのメリットを伝達します。いくつかのアイディアについては、[Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) の変更管理戦略の記事を参照してください。
- IT パイロットの参加者に、各自の経験に基づく変更管理の資料のレビューを依頼します。参加者から、ベスト プラクティスに関するヒントや、SharePoint Online のメリットを説明する最適な方法、およびコミュニケーションとスケジューリングに SharePoint Online を使用する方法に関するアドバイスを得られる可能性があります。

#### <a name="result"></a>結果

SharePoint Online の IT パイロットが完了し、最初の変更管理資料の作成、レビュー、調整が行われます。

### <a name="step-3-roll-out-to-a-business-group"></a>手順 3: ビジネス グループへロールアウトする

IT パイロットの完了後に、SharePoint Online を組織内のビジネス グループまたは部門にロールアウトします。このロールアウトでは、次の作業を行います。

- ビジネス グループにおける SharePoint Online の重要なビジネス シナリオの決定。
- 部門、作業チーム、プロジェクト チームにおける SharePoint Online の用途の想定事項とタイムラインをユーザーに伝達する広報活動。
- ビジネス グループのメンバーの、オンプレミスのフォルダーとドキュメントの SharePoint Online への移行。
- ユーザー トレーニングの実施、または SharePoint Online とその使用方法を紹介するリソースへのリンクの提供。[SharePoint Online](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23) のビデオ トレーニングを参照してください。
- ビジネス グループのユーザーからコメントを収集し、問題点を指摘するフィードバック メカニズム (ビジネス グループのメンバー全員が含まれている中央の Microsoft Teams チームなど)。
 
ロールアウト中には、組織全体でのロールアウトに備えて変更管理資料を調整できます。

#### <a name="result"></a>結果

ビジネス グループの 1 つは SharePoint Online を運用しており、変更管理資料のテストと調整が完了しています。

## <a name="phase-3-drive-value"></a>フェーズ 3: 価値を引き出す

このフェーズでは、SharePoint Online のロールアウトを完了し、そのメリットの実現を支援するためにユーザーをサポートします。

### <a name="step-1-roll-out-to-the-rest-of-your-organization"></a>手順 1: 組織の他の部分にロールアウトする

組織の残りの部分へのロールアウトには、以下を含める必要があります。

- 別のビジネス グループにおける SharePoint Online の重要なビジネス シナリオの決定。
- 使用上の想定事項とタイムラインを組織に伝達する広報活動での、調整した変更管理資料の使用。
- 組織の残りの部分のフォルダーとドキュメントの、SharePoint Online への移行。
- ユーザー トレーニングの実施、または SharePoint Online とその使用方法を紹介するリソースへのリンクの提供。
- 組織のユーザーからのコメントや問題点を収集するフィードバック メカニズム (すべてのユーザーが含まれている中央チームなど)。組織の従業員数が 2500 人未満の場合は、Teams のパブリック チャネルを使用し、2500 人以上の場合は Yammer のパブリック グループを使用してください。

#### <a name="result"></a>結果
組織は SharePoint Online を運用しており、SharePoint Online の使用を開始するための情報を伝達し、トレーニングを実施し、ユーザーが使用できるようにする変更管理戦略を実施しています。

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>手順 2: 使用状況を測定し、満足度を管理し、導入を促進する

組織全体にロールアウトした後、次の目的で変更管理戦略を引き続き採用する必要があります。

- 指導力を発揮して、SharePoint Online をドキュメントの保存と共有、チーム、部署、または組織全体のコラボレーションのための主要なツールとして推進します。
- ビジネス グループ、部門、作業チーム、プロジェクト チームでのコラボレーションおよび予定管理にそれを使用するよう、各従業員を促します。

推奨されるアクティビティの一部を次に示します。

- 「[Office 365 導入ガイド](https://aka.ms/successfactors)」を参照して、クラウド サービス導入の一般的なベスト プラクティスを理解します。 
- 「[Office 365 アクティビティ レポート](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)」を参照して、組織全体での Office 365 サービスの使用について理解します。組織の Office 365 全体管理者ではない場合は、ユーザー アカウントに Reports Reader 権限を付与できるグローバル管理者に権限の付与を依頼し、アクティビティ レポートにアクセスできるようにしてください。
- フィードバック機能 (中央チームまたは Yammer のパブリック チャネル) を監視し、各メンバーからの SharePoint Online を使用したうえでの問題の指摘やフィードバックがないか確認します。質問や問題には可能な限り迅速に対応してメンバーが不満を抱えるのを避け、ロールアウトをサポートすることを示します。
- 各ビジネス グループのチャンピオンを特定して育成し、SharePoint Online を使用することによって達成できた内容やベスト プラクティスを強調します。チャンピオンの成功事例を組織に反映し、プロジェクトの成功と導入を紹介します。ビジネス グループ内の技術リーダーからの支持は、他のリーダーや同僚に大きな影響を及ぼします。

#### <a name="result"></a>結果

組織は、SharePoint Online をドキュメントの保存とコラボレーションをサポートするサービスとして採用しています。

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft での Microsoft 365 Enterprise の活用方法

Microsoft が実施した SharePoint Online の展開方法についての詳しい説明は、「[SharePoint からクラウドへ: Microsoft が実施した移行方法](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration)」を参照してください。

## <a name="next-steps"></a>次の手順

SharePoint Online の継続的なメンテナンスについては、以下のリソースを参照してください。 

- [SharePoint でのアクセス許可レベルについて](https://support.office.com/article/Understanding-permission-levels-in-SharePoint-87ecbb0e-6550-491a-8826-c075e4859848)
- [SharePoint サイト権限をカスタマイズする](https://support.office.com/article/Customize-SharePoint-site-permissions-b1e3cd23-1a78-4264-9284-87fed7282048)
- [SharePoint Online の外部共有をオンまたはオフにする](https://support.office.com/article/Turn-external-sharing-on-or-off-for-SharePoint-Online-6288296a-b6b7-4ea4-b4ed-c297bf833e30)
- [アクセス要求の設定と管理](https://support.office.com/article/Set-up-and-manage-access-requests-94B26E0B-2822-49D4-929A-8455698654B3)

