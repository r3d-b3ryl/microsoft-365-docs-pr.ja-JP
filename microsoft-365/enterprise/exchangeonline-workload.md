---
title: Microsoft 365 Enterprise の Exchange Online の展開
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-email-calendar
ms.custom:
- Strat_O365_Enterprise
description: 組織全体で Microsoft 365 Enterprise の Exchange Online の価値を計画、ロールアウト、および促進するプロセスについて順を追って説明します。
ms.openlocfilehash: 9214796c37e9cb5ca9fcb07ced5db7efd8e0f7d0
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634148"
---
# <a name="deploy-exchange-online-for-microsoft-365-enterprise"></a>Microsoft 365 Enterprise の Exchange Online の展開

*このワークロードは、Microsoft 365 Enterprise の E3 および E5 の両バージョンに該当します*

Exchange Online は、ユーザーがリアルタイムのチャットや一元化されたドキュメントの保存を必要としない方法で共同作業を行うことができるようにする、メールおよび予定表用のプライマリ クラウド サービスです。 Exchange Online は、Microsoft 365 Enterprise のチームワークのために構築されたの重要な要素です。 Exchange Online を使用すると、使用しているデバイスに関係なく、既知の Outlook アプリケーションでより効果的に作業を行うことができます。

また、Exchange Online には、メールボックスを保護するためのマルウェア対策およびスパム対策フィルター、ユーザーが機密情報を誤って許可のないユーザーに送信することを防ぐデータ損失防止機能を含む高度なセキュリティ機能もあります。 Exchange Online のセキュリティは、Microsoft 365 Enterprise のインテリジェントセキュリティ価値の重要な要素です。

Exchange online を初めて使用する場合は、「[Microsoft Exchange Online](https://products.office.com/exchange/exchange-online)」を参照してください。

次のフェーズと手順は、組織内の Exchange Online の役割を構想するプロセス、一連のプログレッシブ展開によって exchange Online をオンボードにして、Exchange Online とその価値をエンドユーザーに使用するプロセスを中心に説明します。

>[!Note]
>これらの展開手順は[、Microsoft 365 Enterprise foundation インフラストラクチャのフェーズ2の id](identity-infrastructure.md)を完了した後にのみ実行する必要があります。
>

## <a name="phase-1-envision-your-exchange-online-deployment"></a>フェーズ 1: Exchange Online の展開の構想を作成する

このフェーズでは、Exchange Online の展開に関するユーザーを収集し、組織が Exchange Online を使用してビジネスニーズに対処する方法を決定します。

### <a name="step-1-gather-your-exchange-online-deployment-members"></a>手順 1: Exchange Online の展開メンバーを収集する

Microsoft 365 Enterprise foundation インフラストラクチャの[フェーズ 2-id](identity-infrastructure.md)の上に Exchange Online を正常に展開するには、入力とフィードバックのための適切な人物を集める必要があります。 主要な人物としては、ビジネス意思決定者、アーキテクトや実装者などの IT スタッフ、およびエンドユーザーの支持者が挙げられます。 

これら3つのグループにより、Exchange Online の展開には、ビジネスニーズ、メールボックスの移行とセキュリティの技術的な側面についての考慮事項、および一般的なユーザーが使用するような結果が得られることが保証されます。

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

技術計画を始める前に、FastTrack を使用するかどうかを決定します。 組織が50を超える座席を持ち、対象となる[プラン](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365)に参加している場合は、計画、展開、およびサービスの導入に関する*追加費用*をかけずに、 [Microsoft 365 に fasttrack](https://fasttrack.microsoft.com/microsoft365)を使用できます。 また、この作業をお客様自身で完了することもできます。その場合は、Microsoft 365 アカウントでサインインすると [FastTrack](https://fasttrack.microsoft.com/) から利用できるようになる FastTrack オンボーディング ウィザードを使用します。

独自の計画を行っている場合や、FastTrack と連携している場合は、ネットワークと組織が Exchange Online の準備ができているかどうかを判断する必要があります。 組織のネットワークに接続しているユーザーのために、基礎インフラストラクチャにおける[ネットワーク](networking-infrastructure.md)の終了条件を満たすことは特に重要です。 Exchange Online ベースの電子メールおよび添付ファイルに対する追加のトラフィックのパフォーマンスを最大にするために、インターネット帯域幅、スループット、トラフィック遅延に特に注意してください。

これらのリソースを使用して、Exchange Online ロールアウトの技術的な側面を準備します。 

- [複数のメール アカウントを Office 365 に移行する方法](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)
- [Exchange Server のパブリックフォルダーを Exchange Online に移行する](https://docs.microsoft.com/Exchange/collaboration/public-folders/migrate-to-exchange-online?view=exchserver-2019)
- [Exchange Server のパブリックフォルダーを Microsoft 365 グループに移行する](https://docs.microsoft.com/Exchange/collaboration/public-folders/batch-migration-to-office-365-groups?view=exchserver-2019)
- [Exchange Online でのコラボレーション](https://docs.microsoft.com/exchange/collaboration-exo/collaboration-exo)
- [Exchange Online の受信者](https://docs.microsoft.com/exchange/recipients-in-exchange-online/recipients-in-exchange-online)
- [iOS 版および Android 版 Outlook](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android)

Exchange Online のセキュリティをより深く理解するには、次のリソースを確認してください。

- [Exchange Online のアクセス許可](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) 
- [Exchange Online のセキュリティとコンプライアンス](https://docs.microsoft.com/exchange/security-and-compliance/security-and-compliance) 
- [スパム対策とマルウェア対策の保護](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection)

次に、これらのリソースを使用して Exchange Online メールボックス管理について理解します。

- [Exchange Online でユーザーメールボックスを作成する](https://docs.microsoft.com/exchange/recipients-in-exchange-online/create-user-mailboxes)
- [ユーザー メールボックスの管理](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes) 
- [配布グループを作成して管理する](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)

#### <a name="result"></a>結果

メールボックスの移行、セキュリティ、および管理について理解し、組織内の選択したグループへの Exchange Online のロールアウトを開始する準備ができました。

### <a name="step-2-run-an-it-pilot"></a>手順 2: IT パイロットを実施する

中規模および大規模な組織では、通常、フェーズ1、初期採用者、テクニカル愛好家から、関係者と共に IT パイロットを実行する必要があります。 IT パイロットでは、次の作業を行います。

- パイロットに Microsoft 365 のライセンスを付与し、オンプレミスのメールボックスを Exchange Online に移行します。
- パイロット参加者に、Exchange Online の電子メール、スケジュール、およびその他の機能をテストするための一連の実習を用意します。
- 変更管理戦略を決定し、組織全体のユーザーによる Outlook および Exchange Online の導入を促進するための資料を作成します。 
 
  変更管理に関する資料には、メールによる発表テキスト、社内トレーニング プラン、廊下のポスター、プレゼンテーションを入れることができます。 これらの資料は、組織に Exchange Online に関する情報を提供し、認識を向上させ、使用を推進することの目標を達成したものとします。 いくつかのアイデアについては、 [Microsoft Teams の変更管理戦略](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy)の記事を参照してください。

- IT パイロットの参加者には、自信の体験に基づいて変更管理の資料をレビューしてもらいます。 これらのヒントには、Outlook と Exchange Online の利点についての最適な説明と、コミュニケーションとスケジュール設定に使用する方法についてのヒントが提供されています。

#### <a name="result"></a>結果

Exchange Online IT パイロットは完成し、最初の変更管理資料が開発、レビュー、および調整されています。

### <a name="step-3-roll-out-to-a-business-group"></a>手順 3: ビジネス グループに展開する

IT パイロットを完了した後、組織内のビジネスグループまたは部署に Exchange Online をロールアウトします。 組織が Exchange Server などの社内電子メールサービスを使用している場合、このロールアウトはメールボックスの移行で構成されます。 この展開では、次の作業を行います。

- ビジネスグループ内の Exchange Online の主要なビジネスシナリオの識別。
- 部署や作業またはプロジェクトチームのための、Exchange Online の使用状況についての要望とタイムラインをユーザーに通知するアナウンスアクティビティ。
- ビジネスグループのメンバーの社内メールボックスを Exchange Online に移行します。
- Outlook で[ユーザートレーニングを実施](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca)するか、outlook およびその使用方法を紹介するリソースへのリンクを提供します。
- ビジネス グループのユーザーからコメントを収集し、問題点を指摘するフィードバック メカニズム (ビジネス グループのメンバー全員が含まれている中央の Microsoft Teams チームなど)。

ロールアウト中には、組織全体でのロールアウトに備えて変更管理資料を調整できます。

#### <a name="result"></a>結果

ビジネスグループは Outlook と Exchange Online を使用して稼働しており、変更管理資料のテストと調整が行われています。

## <a name="phase-3-drive-value"></a>フェーズ 3: 価値を引き出す

このフェーズでは、Exchange Online のロールアウトを完了し、ユーザーによるメリットの実現を支援するためにユーザーをサポートします。

### <a name="step-1-roll-out-exchange-online-to-the-rest-of-your-organization"></a>手順 1: 組織の他の部分に Exchange Online をロールアウトする

組織の残りの部分へのロールアウトには、以下を含める必要があります。

- 個別のビジネスグループ内の Exchange Online の主要なビジネスシナリオの識別。
- Exchange Online の使用状況に関する期待値とタイムラインを組織に通知するために、改訂の変更管理資料をアナウンス活動に使用します。
- 組織の残りの部分のメールボックスを Exchange Online に移行します。
- Outlook で[ユーザートレーニング](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca)を実施するか、outlook およびその使用方法を紹介するリソースへのリンクを提供します。
- 組織のユーザーからのコメントや問題点を収集するフィードバック メカニズム (すべてのユーザーが含まれている中央チームなど)。組織の従業員数が 2500 人未満の場合は、Teams のパブリック チャネルを使用し、2500 人以上の場合は Yammer のパブリック グループを使用してください。

#### <a name="result"></a>結果

組織が稼働しており、ユーザーが Exchange Online を使用できるようにするために、変更管理戦略が実施されています。

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>手順 2: 使用状況を測定し、満足度を管理し、導入を促進する

Exchange Online を組織全体にロールアウトした後、次のことを行うために、変更管理戦略を引き続き採用する必要があります。

- リーダーシップを発揮して、個々の、および短期間のコミュニケーションとスケジューリングのための主要なツールとして Exchange Online を促進します。
- ビジネスグループ、部門、作業、およびプロジェクトチームのコミュニケーション、予定表作成、グループ作業に使用することをお勧めします。

推奨されるアクティビティの一部をいくつか紹介します。

- クラウドサービスの導入に関する一般的なベストプラクティスについては、「 [Microsoft 365 の成功要因](https://aka.ms/successfactors)」を参照してください。 
- 組織全体でのサービスの利用状況を理解するに[は、管理センターの Microsoft 365 レポート](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports)を参照してください。 組織のグローバル管理者ではない場合は、アクティビティレポートにアクセスできるように、グローバル管理者がユーザーアカウントに対してレポートリーダーアクセス許可を付与するように依頼してください。
- Exchange Online でのエクスペリエンスに関する問題とフィードバックについて、フィードバック会場 (中央チームのチームまたは Yammer のパブリックチャネル) を監視します。 ユーザーの不満を防ぎ、展開のサポートを実施できるように、質問と問題にすばやく対処します。
- 各ビジネスグループのエキスパートを特定して育成、Outlook を使用してベストプラクティスを強調表示します。 組織に彼らの成果を反映させて、プロジェクトの成功と導入を示します。 ビジネスグループ内の技術リーダーによる裏書は、リーダーとピアに大きな影響を与える可能性があります。

#### <a name="result"></a>結果

組織は、Exchange Online と Outlook を、短時間の主要なコミュニケーションとスケジューリングツールとして採用しています。

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft での Microsoft 365 Enterprise の活用方法

Microsoft の内部を見て、exchange Online に移行し、Exchange Online Protection を使用してサイバー攻撃から保護する方法については、以下を参照してください。

- [Microsoft では 150,000 のメールボックスを Exchange Online に移行](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [Microsoft は脅威からの保護、脅威の検出、脅威への対応に脅威インテリジェンスを使用する](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [Microsoft の Office 365 を使用したフィッシング阻止の試み](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

## <a name="next-steps"></a>次の手順

Exchange Online の継続的なメンテナンスについては、次のリソースを参照してください。

- [Exchange Online の Exchange 管理センター](https://docs.microsoft.com/exchange/exchange-admin-center) 
- [Exchange Online での監視、レポート、メッセージ追跡](https://docs.microsoft.com/exchange/monitoring/monitoring)
- [Exchange Online での電子メールのバックアップ](https://docs.microsoft.com/exchange/back-up-email) 
