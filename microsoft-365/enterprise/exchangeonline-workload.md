---
title: Microsoft 365 Enterprise の Exchange Online の展開
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/29/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-email-calendar
ms.custom:
- Strat_O365_Enterprise
description: 組織全体で Microsoft 365 Enterprise の Exchange Online の価値を計画、ロールアウト、および促進するプロセスについて順を追って説明します。
ms.openlocfilehash: a13cb36dd313ef3e6763c6c48720bb2b3e935880
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981878"
---
# <a name="deploy-exchange-online-for-microsoft-365-enterprise"></a>Microsoft 365 Enterprise の Exchange Online の展開

*このワークロードは、Microsoft 365 Enterprise の E3 および E5 の両バージョンに該当します*

Exchange Online は、電子メールと予定表のプライマリクラウドサービスで、リアルタイムのチャットやドキュメント保存の集中管理を必要としない方法でユーザーを共同作業するのに役立つ情報を備えています。 Exchange Online は、個人および小規模なグループの短時間のコミュニケーションとスケジューリングをどのようにしているのかを示すものであり、Microsoft 365 Enterprise のチームワークの価値を構築するための重要な要素です。 Exchange Online を使用すると、使用しているデバイスに関係なく、既知の Outlook アプリケーションでより効果的に作業を行うことができます。

Exchange Online には、マルウェア対策とスパム対策フィルターを含む高度なセキュリティ機能があり、メールボックスと、ユーザーが誤って機密情報を権限のないユーザーに送信しないようにするデータ損失防止機能を保護します。 Exchange Online のセキュリティは、Microsoft 365 Enterprise のインテリジェントセキュリティ価値の重要な要素です。

Exchange Online を初めて使用する場合は、「 [Microsoft Exchange online](https://products.office.com/exchange/exchange-online)」を参照してください。

次のフェーズと手順に従って、組織内の Exchange Online の役割を構想し、組織を一連の段階的な展開によって Exchange Online にオンボードし、Exchange Online およびそのエンドユーザーへの値。

>[!Note]
>これらの展開手順は、Microsoft 365 Enterprise foundation インフラストラクチャの[フェーズ2の id](identity-infrastructure.md)を完了した後にのみ実行する必要があります。
>

## <a name="phase-1-envision"></a>フェーズ 1: 想定

このフェーズでは、Exchange Online の展開に関するユーザーを収集し、組織が Exchange Online を使用してビジネスニーズに対処する方法を決定します。

### <a name="step-1-gather-your-exchange-online-deployment-members"></a>手順 1: Exchange Online の展開メンバーを収集する

Microsoft 365 Enterprise foundation インフラストラクチャの[フェーズ 2-id](identity-infrastructure.md)の上に Exchange Online を正常に展開するには、入力とフィードバックのための適切な人物を入手する必要があります。 主要な人物としては、ビジネス意思決定者、アーキテクトや実装者などの IT スタッフ、およびエンドユーザーの支持者が挙げられます。 

これら3つのグループにより、Exchange Online の展開には、ビジネスニーズ、メールボックスの移行とセキュリティの技術的な側面についての考慮事項、および一般的なユーザーが使用するものになることが保証されます。

#### <a name="result"></a>結果

組織の事業、技術、エンドユーザーの各側面を代表する関係者のリスト。

### <a name="step-2-determine-and-prioritize-your-exchange-online-business-scenarios"></a>手順 2: Exchange Online のビジネスシナリオを決定し、優先順位を付ける

Exchange Online はさまざまな目的に使用できます。 組織のさまざまなレベル、ビジネスグループ、部門、または個別の作業およびプロジェクトチームについて、ビジネスニーズに対応する目的を判断する必要があります。 個人および小規模グループの短時間の通信およびスケジュールのニーズを解決するには、Exchange Online を対象にする必要があります。 

Exchange Online の利点を確認する方法の1つは、個人、チーム、または v チームが現在どのように連携しているかを調べて、より簡単にコミュニケーションを行い、会議を計画し、共同作業を行うための適切なシナリオを見つけることです。 グループ作業のシナリオによっては、 [Microsoft Teams](teams-workload.md)が適している場合があることに注意してください。

#### <a name="result"></a>結果
コミュニケーション、スケジュール、および短時間のコラボレーションに関する組織のニーズに対応する Exchange Online のシナリオの一覧。

## <a name="phase-2-onboard"></a>フェーズ 2: 研修

このフェーズでは、Exchange Online 展開の技術的な側面を計画し、選択したユーザーグループへのロールアウトを開始します。

### <a name="prerequisites-identity-and-device-access-configuration"></a>前提条件: ID とデバイスのアクセス構成

Exchange Online メールボックスへのアクセスを保護するには、 [id とデバイスのアクセスポリシー](identity-access-policies.md)と、推奨される[exchange online アクセスポリシー](secure-email-recommended-policies.md)を構成していることを確認してください。

### <a name="step-1-complete-your-technical-planning"></a>手順 1: 技術計画を実施する

技術的な計画を開始する前に、FastTrack を使用するかどうかを決定します。 組織が50を超える座席を持ち、対象となる[プラン](https://technet.microsoft.com/library/dn783224.aspx)に参加している場合は、計画、展開、およびサービスの導入に関する追加費用をかけずに、 [Microsoft 365 に fasttrack](https://fasttrack.microsoft.com/microsoft365)を使用できます。 または、Office 365 アカウントでサインインした後に[fasttrack](https://fasttrack.microsoft.com/)から利用できる、Fasttrack のオンボードウィザードを使用して、この作業を自分で行うことができます。

独自の計画を行っている場合や、FastTrack と連携している場合は、ネットワークと組織が Exchange Online の準備ができているかどうかを判断する必要があります。 Exchange の追加のトラフィックに対するパフォーマンスを最大化するために、インターネット帯域幅、スループット、トラフィック遅延に特に注意を向けることで、基礎インフラストラクチャのネットワークの終了条件を満たすことは特に重要です。オンラインベースの電子メールと添付ファイル。

これらのリソースを使用して、Exchange Online ロールアウトの技術的な側面を準備します。 

- [複数のメール アカウントを Office 365 に移行する方法](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)
- [Exchange Online でのコラボレーション](https://technet.microsoft.com/library/jj983794(v=exchg.150).aspx)
- [Exchange Online の受信者](https://technet.microsoft.com/library/jj200702(v=exchg.150).aspx)

Exchange Online のセキュリティをより深く理解するには、次のリソースを確認してください。

- [Exchange Online でのアクセス許可](https://technet.microsoft.com/library/jj200692(v=exchg.150).aspx) 
- [Exchange Online のセキュリティとコンプライアンス](https://technet.microsoft.com/library/jj200706(v=exchg.150).aspx) 
- [スパム対策とマルウェア対策の保護](https://technet.microsoft.com/library/jj200731(v=exchg.150).aspx)

次に、これらのリソースを使用して Exchange Online メールボックス管理について理解します。

- [Exchange Online でユーザーメールボックスを作成する](https://technet.microsoft.com/library/jj907304(v=exchg.150).aspx)
- [ユーザー メールボックスの管理](https://technet.microsoft.com/library/bb123809(v=exchg.150).aspx) 
- [配布グループを作成および管理する](https://technet.microsoft.com/library/bb124513%28v=exchg.150%29.aspx)

#### <a name="result"></a>結果

メールボックスの移行、セキュリティ、および管理について理解し、組織内の選択したグループへの Exchange Online のロールアウトを開始する準備ができました。

### <a name="step-2-run-an-it-pilot"></a>手順 2: IT パイロットを実施する

中規模～大規模な組織のほとんどでは、フェーズ 1 の関係者、早期導入者、熱心な技術者を集めて IT パイロットを実施する必要があります。IT パイロットでは、次の作業を行います。

- IT パイロットの参加者が実習できる Exchange Online ビジネスシナリオを選択します。
- パイロット参加者に Office 365 のライセンスを付与し、オンプレミスのメールボックスを Exchange Online に移行します。
- パイロット参加者に、Exchange Online の電子メール、スケジュール、およびその他の機能をテストするための一連の実習を用意します。
- 変更管理戦略を決定し、組織全体にわたるユーザーの Exchange Online の導入を促進するための資料を作成します。 変更管理資料には、電子メールアナウンステキスト、内部トレーニングプラン、hallway ポスター、プレゼンテーションを含めることができます。 これらの資料は、組織に Exchange Online に関する情報を提供し、認識を向上させ、使用を推進することの目標を達成したものとします。 いくつかのアイデアについては、 [Microsoft Teams の変更管理戦略](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy)の記事を参照してください。
- IT パイロット参加者に、エクスペリエンスに基づいて変更管理資料をレビューしてもらいます。 また、Exchange Online の利点について説明するためのヒントや、コミュニケーションやスケジュール設定に使用する方法についてのヒントを提供することができます。

#### <a name="result"></a>結果

Exchange Online IT パイロットは完成し、最初の変更管理資料が開発、レビュー、および調整されています。

### <a name="step-3-roll-out-to-a-business-group"></a>手順 3: ビジネス グループへロールアウトする

IT パイロットを完了した後、組織内のビジネスグループまたは部署に Exchange Online をロールアウトします。 組織が Exchange Server などの社内電子メールサービスを使用している場合、このロールアウトはメールボックスの移行で構成されます。 このロールアウトには、次のものが含まれます。

- ビジネスグループ内の Exchange Online の主要なビジネスシナリオの識別。
- 部署や作業またはプロジェクトチームのための、Exchange Online の使用状況についての要望とタイムラインをユーザーに通知するアナウンスアクティビティ。
- ビジネスグループのメンバーの社内メールボックスを Exchange Online に移行します。
- Exchange Online でユーザートレーニングを実施するか、Exchange Online を紹介するリソースへのリンクを提供し、その使用方法について説明します。
- ビジネス グループのユーザーからコメントを収集し、問題点を指摘するフィードバック メカニズム (ビジネス グループのメンバー全員が含まれている中央の Microsoft Teams チームなど)。

ロールアウト中には、組織全体でのロールアウトに備えて変更管理資料を調整できます。

#### <a name="result"></a>結果

ビジネスグループは Exchange Online で稼働しており、変更管理資料のテストと調整が行われています。

## <a name="phase-3-drive-value"></a>フェーズ 3: 価値を引き出す

このフェーズでは、Exchange Online のロールアウトを完了し、ユーザーによるメリットの実現を支援するためにユーザーをサポートします。

### <a name="step-1-roll-out-exchange-online-to-the-rest-of-your-organization"></a>手順 1: 組織の他の部分に Exchange Online をロールアウトする

組織の残りの部分へのロールアウトには、以下を含める必要があります。

- 個別のビジネスグループ内の Exchange Online の主要なビジネスシナリオの識別。
- Exchange Online の使用状況に関する期待値とタイムラインを組織に通知するために、改訂の変更管理資料をアナウンス活動に使用します。
- 組織の残りの部分のメールボックスを Exchange Online に移行します。
- Exchange Online でユーザートレーニングを実施するか、Exchange Online を紹介するリソースへのリンクとその使用方法について説明します。
- 組織のユーザーからのコメントや問題点を収集するフィードバック メカニズム (すべてのユーザーが含まれている中央チームなど)。組織の従業員数が 2500 人未満の場合は、Teams のパブリック チャネルを使用し、2500 人以上の場合は Yammer のパブリック グループを使用してください。

#### <a name="result"></a>結果

組織が稼働しており、ユーザーが Exchange Online を使用できるようにするために、変更管理戦略が実施されています。

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>手順 2: 使用状況を測定し、満足度を管理し、導入を促進する

Exchange Online を組織全体にロールアウトした後、次のことを行うために、変更管理戦略を引き続き採用する必要があります。

- リーダーシップを発揮して、個々の、および短期間のコミュニケーションとスケジューリングのための主要なツールとして Exchange Online を促進します。
- ビジネスグループ、部門、作業、およびプロジェクトチームのコミュニケーション、予定表作成、グループ作業に使用することをお勧めします。

推奨されるアクティビティの一部を次に示します。

- 「[Office 365 導入ガイド](https://aka.ms/successfactors)」を参照して、クラウド サービス導入の一般的なベスト プラクティスを理解します。 
- 「[Office 365 アクティビティ レポート](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports)」を参照して、組織全体での Office 365 サービスの使用について理解します。組織の Office 365 全体管理者ではない場合は、ユーザー アカウントに Reports Reader 権限を付与できるグローバル管理者に権限の付与を依頼し、アクティビティ レポートにアクセスできるようにしてください。
- Exchange Online でのエクスペリエンスに関する問題とフィードバックについて、フィードバック会場 (中央チームのチームまたは Yammer のパブリックチャネル) を監視します。 問題の解決を防ぎ、ロールアウトのサポートをデモンストレーションできるように、質疑応答します。
- 各ビジネスグループのチャンピオンを特定して育成し、Exchange Online を使用してその業績とベストプラクティスを強調します。 プロジェクトの成功と導入を示すために、その成功を組織に反映します。 ビジネスグループ内の技術リーダーによる裏書は、リーダーとピアに大きな影響を与える可能性があります。

#### <a name="result"></a>結果

組織は、プライマリ個人と小規模なグループの短時間のコミュニケーションとスケジューリングツールとして Exchange Online を採用しています。

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft での Microsoft 365 Enterprise の活用方法

Microsoft の内部をピークし、exchange Online に移行し、Exchange Online Protection を使用してサイバー攻撃から保護する方法については、以下を参照してください。

- [Microsoft では 150,000 のメールボックスを Exchange Online に移行](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [Microsoft は脅威からの保護、脅威の検出、脅威への対応に脅威インテリジェンスを使用する](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [Microsoft の Office 365 を使用したフィッシング阻止の試み](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

## <a name="next-steps"></a>次の手順

Exchange Online の継続的なメンテナンスについては、次のリソースを参照してください。

- [Exchange Online の Exchange 管理センター](https://technet.microsoft.com/library/jj200743(v=exchg.150).aspx) 
- [Exchange Online での監視、レポート、メッセージ追跡](https://technet.microsoft.com/library/jj200725(v=exchg.150).aspx)
- [Exchange Online の電子メールのバックアップ](https://technet.microsoft.com/library/dn440734(v=exchg.150).aspx) 
