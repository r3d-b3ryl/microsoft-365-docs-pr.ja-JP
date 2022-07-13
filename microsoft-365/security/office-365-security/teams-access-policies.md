---
title: 推奨される Teams ポリシー - Microsoft 365 for enterprise |Microsoft Docs
description: Teams の通信とファイル アクセスをセキュリティで保護する方法に関する Microsoft の推奨事項のポリシーについて説明します。
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
- zerotrust-solution
ms.technology: mdo
ms.openlocfilehash: 0e26923925416db48b0547bd9d044e367b56cef7
ms.sourcegitcommit: 61b22df76e0f81e5ef11c587b129287886151c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2022
ms.locfileid: "66750036"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a>Teams チャット、グループ、ファイルをセキュリティで保護するためのポリシーの推奨事項

この記事では、Microsoft Teams のチャット、グループ、ファイルや予定表などのコンテンツを保護するために、推奨されるゼロ トラスト ID とデバイス アクセス ポリシーを実装する方法について説明します。 このガイダンスは、Teams 固有の追加情報を含む [、一般的な ID およびデバイス アクセス ポリシー](identity-access-policies.md)に基づいています。 Teams は他の製品と統合されているため、[SharePoint サイトとファイルをセキュリティで保護するためのポリシーの推奨事項と](sharepoint-file-access-policies.md)[、電子メールをセキュリティで保護するためのポリシーの推奨事項](secure-email-recommended-policies.md)も参照してください。

これらの推奨事項は、ニーズの粒度 (開始点、エンタープライズ、特殊なセキュリティ) に基づいて適用できる Teams のセキュリティと保護の 3 つの異なるレベルに基づいています。 これらのセキュリティレベルと、これらの推奨事項によって参照される推奨ポリシーの詳細については、 [ID とデバイスのアクセス構成](microsoft-365-policies-configurations.md)を参照してください。

組織外のユーザーを含め、特定の認証状況を取り上げる目的で、Teams 展開に固有のその他の推奨事項をこの記事に含めます。 完全なセキュリティ エクスペリエンスを実現するには、このガイダンスに従う必要があります。

## <a name="getting-started-with-teams-before-other-dependent-services"></a>他の依存サービスの前に Teams を使用する

Microsoft Teams の使用を開始するために、依存サービスを有効にする必要はありません。 これらのサービスはすべて "機能する" ことになります。 ただし、次のサービス関連の要素を管理する準備が必要です。

- Microsoft 365 グループ
- SharePoint チーム サイト
- OneDrive for Business
- Exchange メールボックス
- ストリーミング ビデオと Planner プラン (これらのサービスが有効になっている場合)

## <a name="updating-common-policies-to-include-teams"></a>Teams を含めるために一般的なポリシーを更新する

Teams のチャット、グループ、コンテンツを保護するために、次の図は、共通 ID ポリシーとデバイス アクセス ポリシーから更新するポリシーを示しています。 更新するポリシーごとに、クラウド アプリの割り当てに Teams と依存サービスが含まれていることを確認します。

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png" alt-text="Teams とその依存サービスへのアクセスを保護するためのポリシー更新プログラムの概要" lightbox="../../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png":::

これらのサービスは、Teams のクラウド アプリの割り当てに含める依存サービスです。

- Microsoft Teams
- SharePoint および OneDrive for Business
- Exchange Online
- Skype for Business Online
- Microsoft Stream (会議の記録)
- Microsoft Planner (Planner タスクとプラン データ)

次の表に、再確認する必要があるポリシーと、すべての Office アプリケーションに対してより広範なポリシーが設定されている [共通 ID およびデバイス アクセス ポリシー](identity-access-policies.md)内の各ポリシーへのリンクを示します。

|保護レベル|ポリシー|Teams の実装に関する詳細情報|
|---|---|---|
|**開始点**|[サインインのリスクが *中*、または *高* のときに MFA を要求する](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Teams と依存サービスがアプリの一覧に含まれていることを確認します。 Teams にはゲスト アクセス規則と外部アクセス規則も考慮する必要があります。これらのルールの詳細については、この記事の後半で説明します。|
||[先進認証をサポートしないクライアントはブロックする](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|クラウド アプリの割り当てに Teams と依存サービスを含めます。|
||[高リスク ユーザーはパスワードを変更する必要がある](identity-access-policies.md#high-risk-users-must-change-password)|アカウントのリスクの高いアクティビティが検出された場合、サインイン時に Teams ユーザーにパスワードの変更を強制します。 Teams と依存サービスがアプリの一覧に含まれていることを確認します。|
||[アプリ データ保護ポリシーを適用する](identity-access-policies.md#apply-app-data-protection-policies)|Teams と依存サービスがアプリの一覧に含まれていることを確認します。 各プラットフォーム (iOS、Android、Windows) のポリシーを更新します。|
|**エンタープライズ**|[サインインのリスクが *低*、*中*、または *高* のときに MFA を要求する](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Teams にはゲスト アクセス規則と外部アクセス規則も考慮する必要があります。これらのルールの詳細については、この記事の後半で説明します。 このポリシーには、Teams と依存サービスを含めます。|
||[デバイス コンプライアンス ポリシーを定義する](identity-access-policies.md#define-device-compliance-policies)|このポリシーには、Teams と依存サービスを含めます。|
||[準拠した PC *と* モバイル デバイスが必要](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|このポリシーには、Teams と依存サービスを含めます。|
|**特殊なセキュリティ**|[*常に* MFA が必要](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|ユーザー ID に関係なく、MFA は組織によって使用されます。 このポリシーには、Teams と依存サービスを含めます。 |

## <a name="teams-dependent-services-architecture"></a>Teams 依存のサービス アーキテクチャ

参考までに、Teams が依存するサービスを次の図に示します。 詳細と図については、 [IT アーキテクト向けの Microsoft Teams と Microsoft 365 の関連する生産性サービスに関するページを](../../solutions/productivity-illustrations.md)参照してください。

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png" alt-text="SharePoint、OneDrive for Business、および Exchange に対する Teams の依存関係を示す図" lightbox="../../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png":::

## <a name="guest-and-external-access-for-teams"></a>Teams のゲストアクセスと外部アクセス

Microsoft Teams では、次のアクセスの種類が定義されています。

- **ゲスト アクセス** は、チームのメンバーとして追加でき、チームの通信とリソースに対するすべてのアクセス許可を持つゲストまたは外部ユーザーに対して Azure AD B2B アカウントを使用します。

- **外部アクセス** は、Azure AD B2B アカウントを持たない外部ユーザー向けです。 外部アクセスには、招待や通話、チャット、会議への参加を含めることができますが、チーム メンバーシップやチームのリソースへのアクセスは含まれません。

条件付きアクセス ポリシーは、対応する Azure AD B2B アカウントがあるため、Teams のゲスト アクセスにのみ適用されます。

<!--
In Azure AD, guest and external users are the same. The user type for both of these is Guest. Guest users are B2B users. Microsoft Teams differentiates between guest users and external users in the app. While it's important to understand how each of these are treated in Teams, both types of users are B2B users in Azure AD and the recommended policies for B2B users apply to both.

-->

Azure AD B2B アカウントを使用してゲストユーザーと外部ユーザーのアクセスを許可する推奨ポリシーについては、「 [ゲストと外部の B2B アカウントへのアクセスを許可するためのポリシー](identity-access-policies-guest-access.md)」を参照してください。

### <a name="guest-access-in-teams"></a>Teams でのゲスト アクセス

管理者は、ビジネスや組織の内部にいるユーザーに対するポリシーに加えて、ユーザー単位で、ビジネスまたは組織の外部にいるユーザーが Teams リソースにアクセスし、グループの会話、チャット、会議などの内部ユーザーと対話することを許可するようにゲスト アクセスを有効にできます。

ゲスト アクセスと実装方法の詳細については、「  [Teams ゲスト アクセス」を](/microsoftteams/guest-access)参照してください。

### <a name="external-access-in-teams"></a>Teams の外部アクセス

外部アクセスはゲスト アクセスと混同されることがあるため、これら 2 つの非内部アクセス メカニズムが異なる種類のアクセスであることを明確にすることが重要です。

外部アクセスは、外部ドメイン全体の Teams ユーザーが Teams 内のユーザーと会議を検索、通話、チャット、設定する方法です。 Teams 管理者は、組織レベルで外部アクセスを構成します。 詳細については、「 [Microsoft Teams での外部アクセスの管理」を参照してください](/microsoftteams/manage-external-access)。

外部アクセス ユーザーは、ゲスト アクセスを介して追加された個人よりもアクセスと機能が少なくなります。 たとえば、外部アクセス ユーザーは Teams を使用して内部ユーザーとチャットできますが、チーム チャネル、ファイル、またはその他のリソースにはアクセスできません。

外部アクセスでは Azure AD B2B ユーザー アカウントが使用されないため、条件付きアクセス ポリシーは使用されません。

## <a name="teams-policies"></a>Teams ポリシー

上記の一般的なポリシーの外部には、さまざまな Teams 機能を管理するように構成できる Teams 固有のポリシーがあります。

### <a name="teams-and-channels-policies"></a>Teams とチャネルのポリシー

Teams とチャネルは、Microsoft Teams で一般的に使用される 2 つの要素であり、チームとチャネルを使用する場合にユーザーができることとできないことを制御するためのポリシーがあります。 グローバル チームを作成できますが、組織に 5,000 人以下のユーザーがいる場合は、組織のニーズに合わせて、特定の目的に合わせて小さなチームとチャネルを用意すると役に立つ可能性があります。

既定のポリシーを変更するか、カスタム ポリシーを作成することをお勧めします。ポリシーの管理の詳細については、「 [Microsoft Teams でチーム ポリシーを管理する」](/microsoftteams/teams-policies)のリンクを参照してください。

### <a name="messaging-policies"></a>メッセージング ポリシー

メッセージングまたはチャットは、既定のグローバル ポリシーまたはカスタム ポリシーを使用して管理することもできます。これにより、ユーザーは組織に適した方法で相互に通信できます。 この情報は、 [Teams のメッセージング ポリシーの管理で](/microsoftteams/messaging-policies-in-teams)確認できます。

### <a name="meeting-policies"></a>ミーティング ポリシー

Teams 会議に関するポリシーを計画して実装しないと、Teams のディスカッションは完了しません。 会議は Teams の重要な要素であり、多くのユーザーに一度に正式に会ってプレゼンテーションを行い、会議に関連するコンテンツを共有することができます。 会議を中心に組織に適切なポリシーを設定することが不可欠です。

詳細については、「 [Teams での会議ポリシーの管理」を参照してください](/microsoftteams/meeting-policies-in-teams)。

### <a name="app-permission-policies"></a>アプリのアクセス許可ポリシー

Teams では、チャネルや個人用チャットなど、さまざまな場所でアプリを使用することもできます。 セキュリティで保護されたコンテンツ豊富な環境を維持するには、アプリを追加および使用できる場所と場所に関するポリシーを設定することが不可欠です。

アプリのアクセス許可ポリシーの詳細については、「 [Microsoft Teams でアプリのアクセス許可ポリシーを管理](/microsoftteams/teams-app-permission-policies)する」を参照してください。

## <a name="next-steps"></a>次の手順

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png" alt-text="手順 4: Microsoft 365 クラウド アプリのポリシー" lightbox="../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png":::

次の条件付きアクセス ポリシーを構成する:

- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
