---
title: ゲストと外部の B2B アクセスを許可する ID とデバイスのアクセス ポリシー - Microsoft 365 for enterprise |Microsoft Docs
description: ゲストユーザーと外部ユーザーのアクセスを保護するための、推奨される条件付きアクセスと関連するポリシーについて説明します。
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.openlocfilehash: 376845d8e3657b91b9efe0357e94f4bec3a84078
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688287"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a>ゲストと外部の B2B アクセスを許可するポリシー

この記事では、Azure Active Directory (Azure AD) Business-to-Business (B2B) アカウントを持つゲストユーザーと外部ユーザーにアクセスを許可するように、推奨される共通 ID およびデバイス アクセス ポリシーを調整する方法について説明します。 このガイダンスは、共通の [ID ポリシーとデバイス アクセス ポリシーに基っています](identity-access-policies.md)。

これらの推奨事項は、保護のベースライン層 **に** 適用するように設計されています。 ただし、機密性の高い厳しく規制された保護のニーズの粒度に基づいて推奨事項 **を調整** することもできます。

Azure AD テナントで認証する B2B アカウントのパスを指定しても、これらのアカウントは環境全体にアクセスできません。 B2B ユーザーとそのアカウントは、条件付きアクセス ポリシーで付与されたサービス内で共有されているリソース (ファイルなど) にのみアクセスできます。

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a>ゲストアクセスと外部アクセスを許可および保護するための共通ポリシーの更新

Azure AD B2B アカウントを使用してゲストおよび外部アクセスを保護するために、次の図は、共通の ID およびデバイス アクセス ポリシーに対して追加または更新するポリシーを示しています。

[![ゲスト アクセスを保護するためのポリシー更新プログラムの概要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

[このイメージのより大きなバージョンを表示する](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

次の表に、作成および更新する必要があるポリシーを示します。 共通ポリシーは、共通 ID とデバイス アクセス ポリシーに関する記事に関連する構成手順 [にリンク](identity-access-policies.md) しています。

|保護レベル|Policies|詳細情報|
|---|---|---|
|**Baseline**|[ゲストユーザーと外部ユーザーに対して常に MFA を要求する](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|この新しいポリシーを作成し、次の構成を行います。 <ul><li>[ **Assignments > Users and groups > Include**] で、[ **ユーザー** とグループの選択] を選択し、[ All guest and external users ] (すべてのゲスト ユーザーと外部ユーザー **) を選択します**。</li><li>**[Assignments > Conditions > サインイン**] では、すべてのオプションをオフのままにして、常に多要素認証 (MFA) を適用します。</li></ul>|
||[サインイン リスクが中程度または高の場合に MFA *を* 要求 *する*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|ゲスト ユーザーと外部ユーザーを除外するには、このポリシーを変更します。|
||[準拠 PC が必要](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|ゲスト ユーザーと外部ユーザーを除外するには、このポリシーを変更します。|

条件付きアクセス ポリシーにゲスト ユーザーと外部ユーザーを含める、または除外するには、[割り当て] >  **[** ユーザーとグループ] > [含める] または [除外] を選択し、[すべてのゲスト ユーザーと外部ユーザー] をオン **にしてください**。

![ゲストユーザーと外部ユーザーを除外するコントロールの画面キャプチャ](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a>詳細情報

### <a name="guest-and-external-access-with-microsoft-teams"></a>Microsoft Teams を使用したゲストおよび外部アクセス

Microsoft Teams では、次の定義を行います。

- **ゲスト アクセス** では、Azure AD B2B アカウントを使用します。このアカウントは、チームのメンバーとして追加され、チームの通信とリソースへのアクセス許可を持つすべてのアクセス許可を持っています。

- **外部アクセス** は、B2B アカウントを持つ外部ユーザー用です。 外部アクセスには、招待と通話、チャット、会議への参加を含めできますが、チーム メンバーシップとチームのリソースへのアクセスは含め込めではありません。

詳細については、チームのゲスト [アクセスと外部アクセスの比較を参照してください](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)。

Teams [の ID とデバイス アクセス](teams-access-policies.md) ポリシーのセキュリティ保護の詳細については、Teams のチャット、グループ、ファイルをセキュリティ保護するためのポリシーの推奨事項を参照してください。

### <a name="require-mfa-always-for-guest-and-external-users"></a>ゲストユーザーと外部ユーザーに対して常に MFA を要求する

このポリシーは、ゲストがホーム テナントで MFA に登録されているかどうかに関係なく、テナントで MFA を登録するように求めるメッセージを表示します。 テナント内のリソースにアクセスする場合、ゲスト ユーザーと外部ユーザーは要求ごとに MFA を使用する必要があります。

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a>ゲストユーザーと外部ユーザーをリスクベースの MFA から除外する

組織は Azure AD Identity Protection を使用して B2B ユーザーにリスクベースのポリシーを適用することができますが、ホーム ディレクトリに存在する ID のため、リソース ディレクトリに B2B コラボレーション ユーザー用の Azure AD Identity Protection を実装する場合には制限があります。 これらの制限により、Microsoft ではゲスト ユーザーをリスクベースの MFA ポリシーから除外し、常に MFA を使用する必要があります。

詳細については [、「B2B コラボレーション ユーザーの Id 保護の制限事項」を参照してください](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)。

### <a name="excluding-guest-and-external-users-from-device-management"></a>ゲスト ユーザーと外部ユーザーをデバイス管理から除外する

デバイスを管理できるのは 1 つの組織のみです。 デバイスの準拠を必要とするポリシーからゲスト ユーザーと外部ユーザーを除外しない場合、これらのポリシーによってこれらのユーザーがブロックされます。

## <a name="next-step"></a>次の手順

![手順 4: Microsoft 365 クラウド アプリのポリシー](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

次の条件に合ったアクセス ポリシーを構成します。

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
