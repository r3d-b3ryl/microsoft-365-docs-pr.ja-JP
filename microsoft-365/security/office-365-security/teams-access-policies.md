---
title: 推奨される Teams ポリシー - Microsoft 365 for enterprise |Microsoft Docs
description: Teams 通信とファイル アクセスをセキュリティで保護する方法に関する Microsoft 推奨事項のポリシーについて説明します。
author: MicrosoftHeidi
manager: serdars
ms.prod: m365-security
ms.topic: article
audience: Admin
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
ms.openlocfilehash: 52e6709d18bd5ecbc91755a6c0e7be336d346f0c
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599605"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a>Teams のチャット、グループ、ファイルのセキュリティ保護に関するポリシーの推奨事項

この記事では、Microsoft Teams のチャット、グループ、およびファイルや予定表などのコンテンツを保護するために、推奨される ID ポリシーとデバイス アクセス ポリシーを実装する方法について説明します。 このガイダンスは、Teams[](identity-access-policies.md)固有の追加情報を含む、共通の ID およびデバイス アクセス ポリシーに基わっています。 Teams は他の製品と統合されますので [、SharePoint](sharepoint-file-access-policies.md) サイトとファイルのセキュリティ保護に関するポリシーの推奨事項と、電子メールのセキュリティ保護に関するポリシーの推奨事項も [参照してください](secure-email-recommended-policies.md)。

これらの推奨事項は、ニーズの細分性に基づいて適用できる Teams のセキュリティと保護の 3 つの層に基づいて行います。ベースライン、機密性の高い、高度に規制されています。 これらのセキュリティ層と、これらの推奨事項で参照される推奨ポリシーの詳細については、「Identity and [device access configurations」を参照してください](microsoft-365-policies-configurations.md)。

Teams の展開に固有の推奨事項については、組織外のユーザーを含む特定の認証状況をカバーするために、この記事に含まれています。 完全なセキュリティ エクスペリエンスを提供するには、このガイダンスに従う必要があります。

## <a name="getting-started-with-teams-before-other-dependent-services"></a>他の依存サービスの前に Teams を使い始める

Microsoft Teams を使い始めるには、依存サービスを有効にする必要はない。 これらのサービスはすべて "単なる動作" になります。 ただし、次のサービス関連の要素を管理するために準備する必要があります。

- Microsoft 365 グループ
- SharePoint チーム サイト
- OneDrive for Business
- Exchange メールボックス
- ビデオと Planner プランのストリーミング (これらのサービスが有効な場合)

## <a name="updating-common-policies-to-include-teams"></a>Teams を含める一般的なポリシーの更新

Teams のチャット、グループ、コンテンツを保護するために、次の図は、共通の ID およびデバイス アクセス ポリシーから更新するポリシーを示しています。 更新するポリシーごとに、Teams と依存サービスがクラウド アプリの割り当てに含まれているか確認します。

[![Teams とその依存サービスへのアクセスを保護するためのポリシー更新プログラムの概要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)

これらのサービスは、Teams のクラウド アプリの割り当てに含める依存サービスです。

- Microsoft Teams
- SharePoint および OneDrive for Business
- Exchange Online
- Skype for Business Online
- Microsoft Stream (会議の記録)
- Microsoft Planner (Planner タスクと計画データ)

次の表に、再訪する必要があるポリシーと、共通 ID およびデバイス[](identity-access-policies.md)アクセス ポリシー内の各ポリシーへのリンクを示します。このポリシーは、すべての Office アプリケーションに対してより広範に設定されています。

|保護レベル|ポリシー|Teams の実装の詳細|
|---|---|---|
|**Baseline**|[サインイン リスクが中程度または高の場合に MFA *を* 要求 *する*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Teams と依存サービスがアプリの一覧に含まれている必要があります。 Teams には、ゲスト アクセスルールと外部アクセス ルールも考慮する必要があります。これらのルールの詳細については、この記事の後半で説明します。|
||[先進認証をサポートしないクライアントはブロックする](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|クラウド アプリの割り当てに Teams と依存サービスを含める。|
||[高リスク ユーザーはパスワードを変更する必要がある](identity-access-policies.md#high-risk-users-must-change-password)|アカウントでリスクの高いアクティビティが検出された場合、サインイン時に Teams ユーザーにパスワードの変更を強制的に行います。 Teams と依存サービスがアプリの一覧に含まれている必要があります。|
||[APP データ保護ポリシーの適用](identity-access-policies.md#apply-app-data-protection-policies)|Teams と依存サービスがアプリの一覧に含まれている必要があります。 各プラットフォーム (iOS、Android、Windows) のポリシーを更新します。|
||[デバイス コンプライアンス ポリシーの定義](identity-access-policies.md#define-device-compliance-policies)|このポリシーに Teams と依存サービスを含める。|
||[準拠 PC が必要](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|このポリシーに Teams と依存サービスを含める。|
|**機密**|[サインイン リスクが低い、中程度、または高い場合に MFA *を* 要求 *する*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Teams には、ゲスト アクセスルールと外部アクセス ルールも考慮する必要があります。これらのルールの詳細については、この記事の後半で説明します。 このポリシーに Teams と依存サービスを含める。|
||[準拠している PC とモバイル *デバイスを* 要求する](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|このポリシーに Teams と依存サービスを含める。|
|**厳しく規制**|[*常に* MFA を要求する](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|ユーザー ID に関係なく、MFA は組織で使用されます。 このポリシーに Teams と依存サービスを含める。 |
|

## <a name="teams-dependent-services-architecture"></a>Teams 依存サービスのアーキテクチャ

参考までに、次の図は Teams が依存するサービスを示しています。 詳細と図については、「Microsoft Teams および関連する生産性サービス in [Microsoft 365 for IT アー](../../solutions/productivity-illustrations.md)キテクト」を参照してください。

[![SharePoint、OneDrive for Business、Exchange での Teams の依存関係を示す図](../../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

[このイメージのより大きなバージョンを表示する](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

## <a name="guest-and-external-access-for-teams"></a>Teams のゲストアクセスと外部アクセス

Microsoft Teams では、次のアクセスの種類を定義します。

- ゲスト **アクセス** は、チームのメンバーとして追加できるゲストまたは外部ユーザーに対して Azure AD B2B アカウントを使用し、チームの通信とリソースへのすべてのアクセス許可を持っています。

- **外部アクセス** は、Azure アカウント B2B アカウントを持ADユーザー用です。 外部アクセスには、招待と通話、チャット、会議への参加を含めできますが、チーム メンバーシップとチームのリソースへのアクセスは含めではありません。

条件付きアクセス ポリシーは、対応する Azure アカウントと B2B アカウントが存在AD Teams のゲスト アクセスにのみ適用されます。

<!--
In Azure AD, guest and external users are the same. The user type for both of these is Guest. Guest users are B2B users. Microsoft Teams differentiates between guest users and external users in the app. While it's important to understand how each of these are treated in Teams, both types of users are B2B users in Azure AD and the recommended policies for B2B users apply to both.

-->

Azure AD B2B アカウントを持つゲストユーザーと外部ユーザーのアクセスを許可する推奨ポリシーについては、「ゲストアカウントと外部 [B2B](identity-access-policies-guest-access.md)アカウントアクセスを許可するポリシー」を参照してください。

### <a name="guest-access-in-teams"></a>Teams でのゲスト アクセス

管理者は、ビジネスや組織の内部に所属するユーザーのポリシーに加えて、ビジネスや組織の外部のユーザーが Teams リソースにアクセスしたり、グループの会話、チャット、会議などについて内部のユーザーとやり取りしたりできるゲスト アクセスをユーザー単位で許可できます。

ゲスト アクセスとそれを実装する方法の詳細については、「Teams ゲスト アクセス  [」を参照してください](/microsoftteams/guest-access)。

### <a name="external-access-in-teams"></a>Teams の外部アクセス

外部アクセスはゲスト アクセスと混同される場合があります。そのため、これら 2 つの内部以外のアクセス メカニズムが異なる種類のアクセスである点を明確にすることが重要です。

外部アクセスは、外部ドメイン全体の Teams ユーザーが Teams 内のユーザーとの会議を検索、呼び出し、チャット、セットアップするための方法です。 Teams 管理者は、組織レベルで外部アクセスを構成します。 詳細については [、「Microsoft Teams で外部アクセスを管理する」を参照してください](/microsoftteams/manage-external-access)。

外部アクセス ユーザーは、ゲスト アクセスを介して追加された個人よりもアクセスと機能が少ない。 たとえば、外部アクセス ユーザーは Teams を使用して内部ユーザーとチャットできますが、チーム チャネル、ファイル、その他のリソースにはアクセスできません。

外部アクセスでは、Azure AD B2B ユーザー アカウントは使用されないので、条件付きアクセス ポリシーは使用できません。

## <a name="teams-policies"></a>Teams ポリシー

上記の一般的なポリシーの外部には、さまざまな Teams 機能を管理するために構成できる、および構成する必要がある Teams 固有のポリシーがあります。

### <a name="teams-and-channels-policies"></a>Teams とチャネルのポリシー

Teams とチャネルは、Microsoft Teams でよく使用される 2 つの要素であり、チームとチャネルを使用するときにユーザーが実行できる操作と実行できない操作を制御するポリシーがあります。 グローバル チームを作成することもできますが、組織のユーザー数が 5,000 人以下の場合は、組織のニーズに合った、特定の目的で小規模なチームとチャネルを持つ方が役立つ可能性があります。

既定のポリシーの変更やカスタム ポリシーの作成をお勧めします。ポリシーの管理の詳細については [、「Microsoft Teams](/microsoftteams/teams-policies)でのチーム ポリシーの管理」を参照してください。

### <a name="messaging-policies"></a>メッセージング ポリシー

メッセージング (チャット) は、既定のグローバル ポリシーまたはカスタム ポリシーを使用して管理することもできます。これにより、ユーザーは組織に適した方法で相互に通信できます。 この情報は、「Teams のメッセージング [ポリシーの管理」で確認できます](/microsoftteams/messaging-policies-in-teams)。

### <a name="meeting-policies"></a>ミーティング ポリシー

Teams 会議に関するポリシーを計画して実装しない場合、Teams の議論は完了しない。 会議は Teams の重要な要素であり、ユーザーは一度に多くのユーザーに正式に会って提示し、会議に関連するコンテンツを共有できます。 会議に関する組織に適切なポリシーを設定する必要があります。

詳細については、「Teams での会議 [ポリシーの管理」を参照してください](/microsoftteams/meeting-policies-in-teams)。

### <a name="app-permission-policies"></a>アプリのアクセス許可ポリシー

Teams では、チャネルや個人用チャットなど、さまざまな場所でアプリを使用することもできます。 どのアプリを追加して使用できるのか、どこで使用できるのかというポリシーを持つことは、セキュリティで保護されたコンテンツ豊富な環境を維持するために不可欠です。

アプリのアクセス許可ポリシーの詳細については、「Microsoft Teams でアプリのアクセス許可 [ポリシーを管理する」を参照してください](/microsoftteams/teams-app-permission-policies)。

## <a name="next-steps"></a>次の手順

![手順 4: Microsoft 365 クラウド アプリのポリシー](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

次の条件付きアクセス ポリシーを構成します。

- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)