---
title: SharePoint と OneDrive を Microsoft 365 Enterprise 向けに展開する
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/11/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
ms.custom: ''
description: 組織全体で SharePoint を計画、ロールアウトするプロセス、および SharePoint Online の価値を引き出すプロセスについて、順を追って説明します。
ms.openlocfilehash: 0cad129cdca5f5dcc072f583b2b651a2547fc5fd
ms.sourcegitcommit: 68c54a45dd663027528b99f883c6ef04b04b19b0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/11/2019
ms.locfileid: "37469149"
---
# <a name="deploy-sharepoint-and-onedrive-for-microsoft-365-enterprise"></a>SharePoint と OneDrive を Microsoft 365 Enterprise 向けに展開する

*このワークロードは、Microsoft 365 Enterprise の E3 および E5 の両バージョンに該当します*

SharePoint と Microsoft Teams は、ファイルの保存と共有、コンテンツ管理、コラボレーションの方法を提供するもので、Microsoft 365 Enterprise のチームワーク用ビルドの価値を引き出す重要な要素です。 

SharePoint には、アクセスの制御、アクセス許可、移動中および静的データの暗号化を含む、高度なセキュリティ機能も備わっています。SharePoint のセキュリティは、Microsoft 365 Enterprise のインテリジェント セキュリティの価値を引き出す重要な要素です。

SharePoint を初めて使用する方は、「[SharePoint](https://products.office.com/sharepoint/collaboration)」と「[SharePoint を使い始める](https://support.office.com/article/video-what-is-sharepoint-online-c17b6824-cc22-478f-8757-497cc6b57121)」を参照してください。

次に示す各フェーズと手順では、組織における SharePoint の役割を想定し、段階的な一連のロールアウトにより組織の研修を行い、それらの使用とエンドユーザーに対する価値を促進するプロセスを説明します。 まず始める前に、SharePoint サイトに必要なセキュリティ機能が備わるように、適切な[基礎インフラストラクチャチャ](deploy-workloads.md#foundation-infrastructure-prerequisites)のフェーズが設定されていることを確認します。 

OneDrive を Microsoft 365 Enterprise 向けに展開する方法については、「[エンタープライズ向けの OneDrive ガイド](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise)」を参照してください。

## <a name="phase-1-envision"></a>フェーズ 1: 想定
このフェーズでは、SharePoint の展開にあたって組織パートナーを招集し、組織でビジネス ニーズに対応するため、どのように SharePoint を利用するかを決定します。

### <a name="step-1-gather-your-sharepoint-deployment-members"></a>手順 1: SharePoint の展開メンバーを収集する

[Microsoft 365 Enterprise の基礎インフラストラクチャ](deploy-foundation-infrastructure.md)に SharePoint を適切に展開するには、意見やフィードバックを得るために適切な関係者を招集する必要があります。主な関係者は、事業部門の意思決定者、IT 担当者 (アーキテクトや実装担当者など)、エンドユーザーの代表者です。 

この 3 つのグループを招集することにより、展開には、ビジネス ニーズを反映した考慮事項と、フォルダーとドキュメントの移行およびセキュリティの技術的側面が反映され、結果は標準的なユーザーが使用するものになります。

#### <a name="result"></a>結果

組織の事業、技術、エンドユーザーの各視点を代表する関係者のリスト。

### <a name="step-2-determine-and-prioritize-your-sharepoint-business-scenarios"></a>手順 2: SharePoint のビジネス シナリオを決定し、優先順位を付ける

SharePoint はさまざまな目的で使用できます。どの目的がビジネス ニーズに当てはまるかを確認する必要があります。SharePoint のターゲットとして、チーム、事業部、または組織全体のコラボレーションのニーズに対応する、ドキュメントの保存と共有、コンテンツ管理、コラボレーションを対象とする必要があります。 

[SharePoint](https://products.office.com/sharepoint/collaboration ) のシナリオと機能のリストを参照してください。

ビジネスの柱となる次の要素を、組織のニーズに対応させることができます。

|||
|:-----|:-----|
| 共有と共同作業 | チーム サイト、コミュニケーション サイト、および同期を活用します。 |
| 情報伝達と連携 | 今後入ってくる情報。 |
| 変換 | Flow を使用して、アプリとサービス間の自動化されたワークフローを作成します。 |
| 集合的な知識の利用 | 検索を使用して、組織内で目的とする結果が得られます。 |
| 保護 | 組織がセキュリティで保護されており、適切なコンプライアンスを達成していることを確認します。 |
|||

各自のニーズに合わせて SharePoint を構成する方法に関するリソースについては、「[SharePoint の管理](https://docs.microsoft.com/sharepoint/sharepoint-online)」を参照してください。

SharePoint の利点を調べる 1 つの方法は、個人、チーム、部門、または組織全体が現在、どのようにやり取りしているかを調べたうえで、ファイルの保存と共有をより簡単に行う適切なシナリオを探すことです。シナリオによっては、[Microsoft Teams](teams-workload.md) がより良い選択になり得ることを念頭においてください。

#### <a name="sharepoint-site-for-highly-regulated-data"></a>厳しく規制されたデータ用の SharePoint サイト

厳しく規制されたデータは地域の規制対象であるか、企業秘密、財務情報、人事情報、組織戦略など、組織にとって最も重要なデータです。 このようなデータに対して、アクセスの制限、データの分類、データ損失の防止、暗号化を行うための SharePoint サイトを構成できます。 詳細については、「[Microsoft Teams および SharePoint サイトで高度な規制データを扱うには](teams-sharepoint-online-sites-highly-regulated-data.md)」を参照してください。

#### <a name="result"></a>結果
ドキュメントの保存と共有、コンテンツ管理、コラボレーション、セキュリティに関する組織のニーズに対応する SharePoint のシナリオのリスト。

## <a name="phase-2-onboard"></a>フェーズ 2: 研修

このフェーズでは、SharePoint の展開の技術的な側面を計画した後、選択したユーザー グループへの展開を開始します。

### <a name="prerequisites-identity-and-device-access-configuration"></a>前提条件: ID とデバイスのアクセス構成

SharePoint サイトへのアクセスを保護するには、[ID とデバイスのアクセス ポリシー](identity-access-policies.md)と、[推奨される SharePoint アクセス ポリシー](sharepoint-file-access-policies.md)を構成していることを確認する必要があります。

### <a name="step-1-complete-your-technical-planning"></a>手順 1: 技術計画を実施する

技術計画を始める前に、FastTrack を使用するかどうかを決定します。 所属する組織が所有しているライセンスが 50 シートを超えていて、[対象となるプラン](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365)に参加している場合は、FastTrack の特典を利用することができます。この特典は、追加で費用がかからずに、計画、展開、サービス導入にいたるまでのガイドとして利用できます。 また、この作業をお客様自身で完了することもできます。その場合は、Microsoft 365 アカウントでサインインすると [FastTrack](https://docs.microsoft.com/fasttrack/m365-fasttrack-benefit-overview) から利用できるようになる FastTrack オンボーディング ウィザードを使用します。

各自で計画を策定している場合、または FastTrack を使用している場合には、ネットワークと組織が SharePoint を導入できる状態にあるかどうかを判断する必要があります。 特に、基礎インフラストラクチャの[ネットワークの終了条件](networking-exit-criteria.md)を満たしており、SharePoint ベースのドキュメントのための追加トラフィックのパフォーマンスを最大限に引き出すため、インターネット帯域幅、スループット、トラフィック遅延に特別な注意を払うことが重要です。

[[SharePoint に移行する](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)] を使用して、SharePoint ロールアウトを準備します。 

SharePoint でのセキュリティの詳細については、次のリソースを参照してください。

-   [SharePoint と OneDrive がクラウド内のデータを保護する方法](https://docs.microsoft.com/sharepoint/safeguarding-your-data)
-   [OneDrive および SharePoint におけるデータ暗号化](https://docs.microsoft.com/microsoft-365/compliance/data-encryption-in-odb-and-spo)

#### <a name="result"></a>結果

SharePoint サイトとオンプレミス フォルダーおよびドキュメントの移行とセキュリティについて理解し、組織内の選択したグループへの SharePoint の展開を開始する準備ができました。

### <a name="step-2-run-an-it-pilot"></a>手順 2: IT パイロットを実施する

中規模～大規模な組織のほとんどでは、フェーズ 1 の関係者、早期導入者、熱心な技術者を集めて IT パイロットを実施する必要があります。 IT パイロットでは、次の作業を行います。

- IT パイロット参加者の練習に使用できる SharePoint のビジネス シナリオを選択します。
- パイロット参加者に、SharePoint ドキュメントの保存、共有、共同作業、その他の能力をテストするための一連の演習を実施します。
- 変更管理戦略を決定し、資料を作成して、組織全体のユーザーによる SharePoint の導入を推進します。 変更管理に関する資料には、メールによる発表テキスト、社内トレーニング プラン、廊下のポスター、プレゼンテーションを入れることができます。 この資料で、SharePoint と意識を高めて使用を推進するという目標によるメリットについて組織に伝えます。 開始するには、「[SharePoint 導入のためのリソース](https://resources.techcommunity.microsoft.com/resources/SharePoint-adoption/)」を参照してください。
- IT パイロットの参加者には、自信の体験に基づいて変更管理の資料をレビューしてもらいます。 その資料にはベスト プラクティスに関するヒントが記載されており、SharePoint の利点とその使用方法についての最適な説明がされています。

#### <a name="result"></a>結果

SharePoint の IT パイロットが完了し、最初の変更管理資料の作成、レビュー、調整が行われます。

### <a name="step-3-roll-out-to-a-business-group"></a>手順 3: ビジネス グループに展開する

IT パイロットの完了後に、SharePoint を組織内のビジネス グループまたは部門に展開します。 この展開では、次の作業を行います。

- ビジネス グループにおける SharePoint の重要なビジネス シナリオの決定。
- 部門と作業チームやプロジェクト チームにおける SharePoint の用途の想定事項とタイムラインをユーザーに伝達する広報活動。
- ビジネス グループのメンバーの、オンプレミスのフォルダーとドキュメントの SharePoint への移行。
- ユーザー トレーニングまたは SharePoint とその使用方法を紹介するリソースへのリンクの提供。 [SharePoint](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23) のビデオ トレーニングを参照してください。
- ビジネス グループのユーザーからコメントを収集し、問題点を指摘するフィードバック メカニズム (ビジネス グループのメンバー全員が含まれている中央の Microsoft Teams チームなど)。
 
ロールアウト中には、組織全体でのロールアウトに備えて変更管理資料を調整できます。

#### <a name="result"></a>結果

ビジネス グループの 1 つは SharePoint を運用しており、変更管理資料のテストと調整が完了しています。

## <a name="phase-3-drive-value"></a>フェーズ 3: 価値を引き出す

このフェーズでは、SharePoint の展開を完了し、ユーザーがそのメリットを得られるようにします。

### <a name="step-1-roll-out-to-the-rest-of-your-organization"></a>手順 1: 組織の他の部分にロールアウトする

組織の残りの部分へのロールアウトには、以下を含める必要があります。

- 別のビジネス グループにおける SharePoint の重要なビジネス シナリオの決定。
- 使用上の想定事項とタイムラインを組織に伝える広報活動に対し再定義した変更管理資料の使用。
- 組織の残りの部分のフォルダーとドキュメントの、SharePoint への移行。
- ユーザー トレーニングの実施、または SharePoint とその使用方法を紹介するリソースへのリンクの提供。
- 組織のユーザーからのコメントや問題点を収集するフィードバック メカニズム (すべてのユーザーが含まれている中央チームなど)。組織の従業員数が 2500 人未満の場合は、Teams のパブリック チャネルを使用し、2500 人以上の場合は Yammer のパブリック グループを使用してください。

#### <a name="result"></a>結果
組織は SharePoint を運用しており、SharePoint の使用を開始するための情報を伝え、トレーニングを実施し、ユーザーが使用できるようにする変更管理戦略を実施しています。

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>手順 2: 使用状況を測定し、満足度を管理し、導入を促進する

組織全体にロールアウトした後、次の目的で変更管理戦略を引き続き採用する必要があります。

- ドキュメントの保管と共有の主要ツールとして、リーダーに SharePoint を宣伝してもらいます。
- ビジネス グループ、部署、プロジェクト チームでのドキュメントの保管と共有に、SharePoint の使用を個人に促します。

推奨されるアクティビティの一部をいくつか紹介します。

- 「[Office 365 の成功要因](https://aka.ms/successfactors)」を参照して、クラウド サービス導入の一般的なベスト プラクティスを理解します。 
- 「[Office 365 アクティビティ レポート](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports)」を参照して、組織全体での Office 365 サービスの使用について理解します。組織の Office 365 全体管理者ではない場合は、ユーザー アカウントに Reports Reader 権限を付与できるグローバル管理者に権限の付与を依頼し、アクティビティ レポートにアクセスできるようにしてください。
- フィードバック会場 (セントラル Teams チームまたは Yammer のパブリック チャネル) に SharePoint での体験について、ユーザーからの問題とフィードバックがないことを確認します。 ユーザーの不満を防ぎ、展開のサポートを実施できるように、質問と問題にすばやく対処します。
- SharePoint を使用している場合は、各ビジネス グループの優秀者を特定、育成し、その業績やベスト プラクティスを強く示します。 組織に彼らの成果を反映させて、プロジェクトの成功と導入を示します。 ビジネス グループの技術リーダーによる推奨は、リーダーと仲間に大きく影響します。

#### <a name="result"></a>結果

組織は Microsoft 365 Enterprise の SharePoint を採用し、ドキュメントの保存と共同作業をサポートしています。

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft での Microsoft 365 Enterprise の活用方法

Microsoft が実施した SharePoint の展開方法についての詳しい説明は、「[SharePoint からクラウドへ: Microsoft が実施した移行方法](https://www.microsoft.com/ja-JP/itshowcase/sharepoint-to-the-cloud-learn-how-microsoft-ran-its-own-migration)」を参照してください。

## <a name="next-steps"></a>次の手順

SharePoint の継続的なメンテナンスについては、以下のリソースを参照してください。 

- [SharePoint でのアクセス許可レベルについて](https://docs.microsoft.com/sharepoint/understanding-permission-levels)
- [SharePoint サイト権限をカスタマイズする](https://docs.microsoft.com/sharepoint/customize-sharepoint-site-permissions)
- [SharePoint の外部共有をオンまたはオフにする](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)
- [アクセス要求の設定と管理](https://support.office.com/article/Set-up-and-manage-access-requests-94B26E0B-2822-49D4-929A-8455698654B3)
