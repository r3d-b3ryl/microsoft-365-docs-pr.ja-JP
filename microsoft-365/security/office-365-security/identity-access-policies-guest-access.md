---
title: ゲストユーザーと外部ユーザーの B2B アクセスを許可する ID とデバイスのアクセス ポリシー - Microsoft 365 enterprise |Microsoft Docs
description: ゲストおよび外部ユーザーのアクセスを保護するために推奨される条件付きアクセスと関連するポリシーについて説明します。
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
ms.openlocfilehash: 4ee6cb93e5c943d704950e28ba4dc70a246429a6
ms.sourcegitcommit: 89097fb648987567b9493b9d94c85c5990562874
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49845078"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a>ゲスト アクセスと B2B 外部ユーザー アクセスを許可するポリシー

この記事では、Azure Active Directory (Azure AD) Business-to-Business (B2B) アカウントを持つゲストおよび外部ユーザーにアクセスを許可するように、推奨されるデバイスと ID アクセス ポリシーを調整する方法について説明します。 このガイダンスは、共通の [ID ポリシーとデバイス アクセス ポリシーに基っています](identity-access-policies.md)。

これらの推奨事項は、保護のベースライン層 **に** 適用するように設計されています。 ただし、機密性の高い厳しく規制された保護に関する特定のニーズに基づいて推奨事項 **を調整** することもできます。

Azure AD テナントで認証する B2B アカウントのパスを指定しても、これらのアカウントは環境全体にアクセスできません。 B2B ユーザーとそのアカウントは、条件付きアクセス ポリシーによって共有されるサービスやリソース (ファイルなど) にアクセスできます。

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a>ゲストおよび外部ユーザー アクセスを許可および保護するための共通ポリシーの更新

この図は、B2B ゲスト および外部ユーザー アクセスの共通 ID ポリシーとデバイス アクセス ポリシーの中で追加または更新するポリシーを示しています。

[![ゲスト アクセスを保護するためのポリシー更新プログラムの概要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

[このイメージのより大きなバージョンを表示する](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

次の表に、作成して更新する必要があるポリシーを示します。 共通ポリシーは、共通 ID とデバイス アクセス ポリシーの記事に関連する構成手順 [にリンク](identity-access-policies.md) しています。

|保護レベル|Policies|詳細|
|---|---|---|
|**Baseline**|[ゲストと外部ユーザーに対して常に MFA を要求する](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|この新しいポリシーを作成し、次の構成を行います。 <ul><li>[ **Assignments > Users and groups > Include**] で、[ **ユーザー** とグループの選択] を選択し、[ すべてのゲスト ユーザーと外部ユーザー] **を選択します**。</li><li>**[Assignments > Conditions > サインイン**] では、すべてのオプションをオフのままにして、常に多要素認証 (MFA) を適用します。</li></ul>|
||[サインイン リスクが中程度または高の場合に MFA *を* 要求 *する*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|ゲストと外部ユーザーを除外するには、このポリシーを変更します。|
||[準拠 PC が必要](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|ゲストと外部ユーザーを除外するには、このポリシーを変更します。|

条件付きアクセス ポリシーにゲストと外部ユーザーを含める、または除外するには、[割り当て **] > [** ユーザーとグループ] > [含める] または [除外] の [すべてのゲスト ユーザーと外部ユーザー] をオン **にしてください**。

![ゲストと外部ユーザーを除外するコントロールの画面キャプチャ](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a>詳細

### <a name="guests-and-external-user-access-with-microsoft-teams"></a>Microsoft Teams を使用したゲストおよび外部ユーザー アクセス

Microsoft Teams は、次のユーザーを定義します。

- **ゲスト アクセス** では、Azure AD B2B アカウントを使用します。このアカウントは、チームのメンバーとして追加され、チームの通信とリソースにアクセスできます。

- **外部アクセス** は、B2B アカウントを持つ外部ユーザー用です。 外部ユーザー アクセスには、招待、通話、チャット、会議が含まれますが、チーム メンバーシップとチームのリソースへのアクセスは含まれます。

詳細については、ゲストとチームの [外部ユーザー アクセスの比較を参照してください](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)。

Teams の ID およびデバイス アクセス ポリシーのセキュリティ保護の詳細については、「Teams のチャット、グループ、およびファイルをセキュリティ保護するためのポリシーの推奨事項」を [参照してください](teams-access-policies.md)。

### <a name="require-mfa-always-for-guest-and-external-users"></a>ゲストユーザーと外部ユーザーに対して常に MFA を要求する

このポリシーは、ゲストがホーム テナントで MFA に登録されているかどうかに関係なく、テナントで MFA を登録するように求めるメッセージを表示します。 テナント内のリソースにアクセスする場合、ゲストと外部ユーザーは要求ごとに MFA を使用する必要があります。

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a>ゲストと外部ユーザーをリスクベースの MFA から除外する

組織は Azure AD Identity Protection を使用して B2B ユーザーにリスクベースのポリシーを適用することができますが、ホーム ディレクトリに存在する ID のため、リソース ディレクトリでの B2B コラボレーション ユーザー向け Azure AD Identity Protection の実装には制限があります。 これらの制限により、Microsoft はゲストをリスクベースの MFA ポリシーから除外し、これらのユーザーに常に MFA を使用する必要があります。

詳細については [、「B2B コラボレーション ユーザーの ID 保護の制限事項」を参照してください](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)。

### <a name="excluding-guests-and-external-users-from-device-management"></a>ゲストと外部ユーザーをデバイス管理から除外する

デバイスを管理できるのは 1 つの組織のみです。 デバイスの準拠を必要とするポリシーからゲストと外部ユーザーを除外しない場合、これらのポリシーによってこれらのユーザーがブロックされます。

## <a name="next-step"></a>次の手順

![手順 4: Microsoft 365 クラウド アプリのポリシー](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

次の条件に合ったアクセス ポリシーを構成します。

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
