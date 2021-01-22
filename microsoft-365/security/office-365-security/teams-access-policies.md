---
title: 推奨される Teams ポリシー - エンタープライズ向け Microsoft 365 |Microsoft Docs
description: Teams の通信とファイル アクセスをセキュリティで保護する方法に関する Microsoft の推奨事項に関するポリシーについて説明します。
author: MicrosoftHeidi
manager: serdars
ms.prod: m365-security
ms.topic: article
f1.keywords:
- NOCSH
ms.author: heidip
ms.date: 09/30/2020
ms.reviewer: anmorgan
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 7724ef76d905cdbaf48f3122d0df7ef28d0b8385
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931628"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a>Teams のチャット、グループ、ファイルをセキュリティで保護するためのポリシーの推奨事項

この記事では、推奨される ID とデバイス アクセス ポリシーを実装して、Microsoft Teams のチャット、グループ、ファイルや予定表などのコンテンツを保護する方法について説明します。 このガイダンスは、Teams [固有の](identity-access-policies.md)追加情報を含む、共通の ID ポリシーとデバイス アクセス ポリシーに基っています。 Teams は他の製品と統合されます。このため [、SharePoint](sharepoint-file-access-policies.md) サイトとファイルをセキュリティ保護するためのポリシーの推奨事項、および電子メールをセキュリティ保護するためのポリシーの推奨事項 [も参照してください](secure-email-recommended-policies.md)。

これらの推奨事項は、ニーズの粒度に基づいて適用できる Teams のセキュリティと保護の 3 つの異なる層に基づいており、ベースライン、機密、厳しく規制されています。 これらのセキュリティ層と、これらの推奨事項で参照される推奨ポリシーの詳細については、ID とデバイスのアクセス構成 [に関するページを参照してください](microsoft-365-policies-configurations.md)。

Teams の展開に固有のその他の推奨事項については、組織外のユーザーを含む特定の認証環境をカバーするために、この記事に含まれています。 完全なセキュリティ エクスペリエンスを提供するには、このガイダンスに従う必要があります。

## <a name="getting-started-with-teams-before-other-dependent-services"></a>他の依存サービスの前に Teams を使い始める

Microsoft Teams を使い始めるには、依存サービスを有効にする必要があります。 これらはすべて "動作するだけ" です。 ただし、以下を管理する準備が必要です。

- Microsoft 365 グループ
- SharePoint チーム サイト
- OneDrive for Business
- Exchange メールボックス
- Stream ビデオと Planner プラン (これらのサービスが有効な場合)

## <a name="updating-common-policies-to-include-teams"></a>Teams を含める一般的なポリシーの更新

Teams のチャット、グループ、コンテンツを保護するために、次の図は、共通の ID ポリシーとデバイス アクセス ポリシーから更新するポリシーを示しています。 更新するポリシーごとに、Teams と依存するサービスがクラウド アプリの割り当てに含まれている必要があります。

[![Teams とその依存サービスへのアクセスを保護するためのポリシー更新プログラムの概要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)

[このイメージのより大きなバージョンを表示する](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)

Teams 用のクラウド アプリの割り当てに含める依存サービスは次のとおりです。

- Microsoft Teams
- SharePoint および OneDrive for Business
- Exchange Online
- Skype for Business Online
- Microsoft Stream (会議のレコーディング)
- Microsoft Planner (Planner のタスクと計画データ)

次の表に、再検討が必要なポリシーと、共通 ID ポリシーとデバイス[](identity-access-policies.md)アクセス ポリシー内の各ポリシーへのリンクを示します。このポリシーには、すべての Office アプリケーションに対して広範なポリシーが設定されています。

|保護レベル|Policies|Teams の実装に関するその他の情報|
|---|---|---|
|**Baseline**|[サインイン リスクが中程度または高の場合に MFA *を* 要求 *する*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Teams と依存するサービスがアプリの一覧に含まれている必要があります。 Teams にはゲスト アクセスと外部アクセスのルールも考慮する必要があります。これらの詳細については、この記事の後半で説明します。|
||[先進認証をサポートしないクライアントはブロックする](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|クラウド アプリの割り当てに Teams と依存サービスを含める。|
||[高リスク ユーザーはパスワードを変更する必要がある](identity-access-policies.md#high-risk-users-must-change-password)|自分のアカウントで危険度の高いアクティビティが検出された場合、サインイン時に Teams ユーザーにパスワードの変更を強制的に行います。 Teams と依存するサービスがアプリの一覧に含まれている必要があります。|
||[アプリ データ保護ポリシーの適用](identity-access-policies.md#apply-app-data-protection-policies)|Teams と依存するサービスがアプリの一覧に含まれている必要があります。 各プラットフォーム (iOS、Android、Windows) のポリシーを更新します。|
||[デバイス コンプライアンス ポリシーの定義](identity-access-policies.md#define-device-compliance-policies)|このポリシーに Teams と依存サービスを含める。|
||[準拠 PC が必要](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|このポリシーに Teams と依存サービスを含める。|
|**機密**|[サインインリスクが低、中、高 *の* 場合 *に* MFA を要求 *する*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Teams にはゲスト アクセスと外部アクセスのルールも考慮する必要があります。これらの詳細については、この記事の後半で説明します。 このポリシーに Teams と依存サービスを含める。|
||[準拠した PC とモバイル *デバイスが* 必要](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|このポリシーに Teams と依存サービスを含める。|
|**厳しく規制**|[*常に* MFA を要求する](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|ユーザー ID に関係なく、MFA は組織で使用されます。 このポリシーに Teams と依存サービスを含める。 |
|

## <a name="teams-dependent-services-architecture"></a>Teams 依存サービスのアーキテクチャ

参考までに、次の図は Teams が依存するサービスを示しています。 詳細と追加の図については、IT アーキテクト向け [Microsoft 365](../../solutions/productivity-illustrations.md)の Microsoft Teams および関連する生産性サービスを参照してください。

[![SharePoint、OneDrive for Business、Exchange に対する Teams の依存関係を示す図](../../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

[このイメージのより大きなバージョンを表示する](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

## <a name="guest-and-external-access-for-teams"></a>Teams のゲストアクセスと外部アクセス

Microsoft Teams では、次の定義を行います。

- **ゲスト** アクセスは、チームのメンバーとして追加できるゲストユーザーまたは外部ユーザーに対して Azure AD B2B アカウントを使用し、チームのコミュニケーションとリソースへのアクセス許可が付与されます。

- **外部アクセス** は、Azure アカウントまたは B2B アカウントを持ADユーザー用です。 外部アクセスには、招待と通話、チャット、会議への参加を含めできますが、チーム メンバーシップとチームのリソースへのアクセスは含め込めではありません。

条件付きアクセス ポリシーは、対応する Azure アカウントと B2B アカウントAD Teams のゲスト アクセスにのみ適用されます。

<!--
In Azure AD, guest and external users are the same. The user type for both of these is Guest. Guest users are B2B users. Microsoft Teams differentiates between guest users and external users in the app. While it's important to understand how each of these are treated in Teams, both types of users are B2B users in Azure AD and the recommended policies for B2B users apply to both.

-->

Azure AD B2B アカウントを持つゲスト ユーザーと外部ユーザーのアクセスを許可する推奨ポリシーについては、「ゲストと外部の [B2B](identity-access-policies-guest-access.md)アカウント アクセスを許可するポリシー」を参照してください。

### <a name="guest-access-in-teams"></a>Teams でのゲスト アクセス

管理者は、企業や組織の内部に所属するユーザーのポリシーに加えて、ユーザー単位でゲスト アクセスを有効にし、ビジネスや組織の外部のユーザーが Teams リソースにアクセスしたり、グループ会話、チャット、会議などについて内部の人と対話したりできる場合があります。

ゲスト アクセスとゲスト アクセスの実装方法の詳細については、「Teams のゲスト アクセス」  [を参照してください](https://docs.microsoft.com/microsoftteams/guest-access)。

### <a name="external-access-in-teams"></a>Teams での外部アクセス

外部アクセスはゲスト アクセスと混同される場合があります。そのため、これら 2 つの内部以外のアクセス メカニズムが実際には大異なっているのは明らかです。

外部アクセスは、外部ドメイン全体の Teams ユーザーが Teams のユーザーとの会議を検索、通話、チャット、およびセットアップするための方法です。 Teams 管理者は、組織レベルで外部アクセスを構成します。 詳細については [、「Microsoft Teams での外部アクセスの管理」を参照してください](https://docs.microsoft.com/microsoftteams/manage-external-access)。

外部アクセス ユーザーは、ゲスト アクセスによって追加されたユーザーよりもアクセスと機能が低い。 たとえば、外部アクセス ユーザーは Teams を使用して内部ユーザーとチャットできますが、チーム チャネル、ファイル、その他のリソースにはアクセスできません。

外部アクセスでは、B2B ユーザー AD Azure を使用し、条件付きアクセス ポリシーは使用できません。

## <a name="teams-policies"></a>Teams ポリシー

上記の一般的なポリシー以外にも、さまざまな Teams 機能を管理するために構成する必要がある Teams 固有のポリシーがあります。

### <a name="teams-and-channels-policies"></a>Teams とチャネルのポリシー

Teams とチャネルは、Microsoft Teams で一般的に使用される 2 つの要素であり、チームとチャネルを使用するときにユーザーが実行できる操作と実行できない操作を制御するポリシーを設定できます。 グローバル チームを作成することもできますが、組織のユーザー数が 5,000 以下の場合は、組織のニーズに合った、特定の目的に合った小規模なチームとチャネルを持つ方が役立ちます。

既定のポリシーの変更またはカスタム ポリシーの作成をお勧めします。ポリシーの管理の詳細については [、「Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-policies)でチーム ポリシーを管理する」のリンクを参照してください。

### <a name="messaging-policies"></a>メッセージング ポリシー

メッセージング (チャット) は、既定のグローバル ポリシーまたはカスタム ポリシーを通じて管理することもできます。これにより、ユーザーは組織に適した方法で相互に通信できます。 この情報は、「Teams でのメッセージング [ポリシーの管理」で確認できます](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams)。

### <a name="meeting-policies"></a>ミーティング ポリシー

Teams 会議に関するポリシーを計画して実装しない場合、Teams の議論は完了しない。 会議は Teams の不可欠なコンポーネントであり、ユーザーは一度に多数のユーザーに正式に会議して発表を行い、会議に関連するコンテンツを共有できます。 会議に関する組織に適切なポリシーを設定する必要があります。

詳細については [、「Teams での会議ポリシーの管理](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams) 」を参照してください。

### <a name="app-permission-policies"></a>アプリのアクセス許可ポリシー

Teams では、チャネルや個人用チャットなど、さまざまな場所でアプリを使用することもできます。 どのアプリを追加して使用できるのか、どこで、どこに追加できるのかというポリシーを持つことは、セキュリティも確保されたコンテンツが豊富な環境を維持するために不可欠です。

アプリのアクセス許可ポリシーの詳細については、「Microsoft Teams でのアプリのアクセス許可ポリシーの [管理」を参照してください](https://docs.microsoft.com/microsoftteams/teams-app-permission-policies)。

## <a name="next-steps"></a>次の手順

![手順 4: Microsoft 365 クラウド アプリのポリシー](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

次の条件に合ったアクセス ポリシーを構成します。

- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
