---
title: ゲストおよび外部の B2B アクセスを許可するための id およびデバイスアクセスポリシー-Microsoft 365 for enterprise |Microsoft Docs
description: ゲストおよび外部ユーザーのアクセスを保護するために推奨される条件付きアクセスと関連ポリシーについて説明します。
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
ms.openlocfilehash: 3afc818f9461ad0cc5ca65ea86d5e90f61f64d9b
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327869"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a>ゲストおよび外部の B2B アクセスを許可するためのポリシー

この記事では、Azure Active Directory (Azure AD) の企業間 (B2B) アカウントを持つゲストユーザーと外部ユーザーにアクセスを許可するための、推奨される共通 id およびデバイスアクセスポリシーを調整する方法について説明します。 このガイダンスは、 [共通の id およびデバイスアクセスポリシー](identity-access-policies.md)に基づいて構築されています。

これらの推奨事項は、保護の **ベースライン** 層に適用するように設計されています。 ただし、 **機密性** の **高い規制** 保護に対するニーズの粒度に基づいて、推奨事項を調整することもできます。 

Azure AD テナントを使用して認証するための B2B アカウントのパスを指定しても、これらのアカウントは環境全体にアクセスできません。 B2B ユーザーおよびそのアカウントは、条件付きアクセスポリシーに付与されたサービス内で、ファイルと一緒に共有されているリソースにのみアクセスできます。

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a>ゲストおよび外部アクセスを許可および保護するための共通ポリシーの更新 

Azure AD B2B アカウントを使用してゲストおよび外部アクセスを保護するために、次の図では、共通 id およびデバイスアクセスポリシーで追加または更新するポリシーを示します。 

[![ゲストアクセスを保護するためのポリシー更新の概要](../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

[この画像のより大きいバージョンを表示する](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

次の表に、作成および更新する必要があるポリシーを示します。 共通のポリシーは、 [一般的な id とデバイスアクセスポリシー](identity-access-policies.md) の記事に記載されている関連する構成手順にリンクしています。

|保護レベル|Policies|詳細情報|
|:---------------|:-------|:----------------|
|**Baseline**|[ゲストおよび外部ユーザーに対して MFA を常に要求する](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|この新しいポリシーを作成し、以下を構成します。 <ul><li> **> > ユーザーとグループの割り当て**については、[**ユーザーとグループの選択**] を選択し、[すべての**ゲストおよび外部ユーザー**] を選択します。 </li><li> **> > の割り当て**については、「多要素認証 (MFA) を常に適用するために、すべてのオプションをオフにしておきます。</li>|
|        |[サインインリスクが*中*または*高*の場合は MFA を必須にする](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|ゲストユーザーと外部ユーザーを除外するには、このポリシーを変更します。|
|        |[準拠 PC が必要](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|ゲストユーザーと外部ユーザーを除外するには、このポリシーを変更します。|

条件付きアクセスポリシーにゲストおよび外部ユーザーを含めたり、除外したりするには > 含めるまたは**除外**する**割り当て > ユーザーおよびグループ**の場合は、**すべてのゲストユーザーと外部ユーザー**をチェックします。

![ゲストおよび外部ユーザーを除外するためのコントロールの画面キャプチャ](../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a>詳細情報

### <a name="guest-and-external-access-with-microsoft-teams"></a>Microsoft Teams を使用したゲストおよび外部アクセス

Microsoft Teams では、以下を定義します。

- **ゲストアクセス** では、チームのメンバーとして追加でき、すべての権限がチームの通信とリソースにアクセスできる AZURE AD B2B アカウントを使用します。

- **外部アクセス** は、B2B アカウントを持たない外部ユーザーに対して行われます。 外部アクセスには、通話、チャット、および会議への招待と参加を含めることができますが、チームのメンバーシップやチームのリソースへのアクセスは含まれません。

詳細については、「 [teams のゲストアクセスと外部アクセスの比較](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)」を参照してください。

条件付きアクセスポリシーは、対応する Azure AD B2B アカウントがあるため、Teams でのゲストアクセスにのみ適用されます。

Teams の id およびデバイスアクセスポリシーの保護の詳細については、「 [teams のチャット、グループ、ファイルを保護するためのポリシーの推奨事項](teams-access-policies.md) 」を参照してください。

### <a name="require-mfa-always-for-guest-and-external-users"></a>ゲストおよび外部ユーザーに対して MFA を常に要求する
このポリシーにより、ゲストがホームテナントで MFA に登録されているかどうかにかかわらず、テナント内の MFA を登録するように求められます。 テナント内のリソースにアクセスするとき、ゲストユーザーと外部ユーザーはすべての要求に対して MFA を使用する必要があります。 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a>リスクベースの MFA からゲストユーザーと外部ユーザーを除外する
組織は、Azure AD Id 保護を使用して B2B ユーザーに対してリスクベースのポリシーを適用できますが、ホームディレクトリに存在する id があるため、リソースディレクトリでの B2B コラボレーションユーザーの Azure AD Id 保護の実装には制限があります。 これらの制限により、ゲストユーザーをリスクベースの MFA ポリシーから除外し、これらのユーザーが常に MFA を使用するようにすることをお勧めします。 

詳細については、「 [B2B コラボレーションユーザーの Id 保護の制限事項](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)」を参照してください。 

### <a name="excluding-guest-and-external-users-from-device-management"></a>デバイス管理からゲストユーザーと外部ユーザーを除外する 
1つの組織のみがデバイスを管理できます。 デバイスコンプライアンスを必要とするポリシーからゲストおよび外部ユーザーを除外しない場合、これらのポリシーによってこれらのユーザーがブロックされます。 

## <a name="next-step"></a>次の手順

![手順 4: Microsoft 365 クラウドアプリのポリシー](../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

次の条件付きアクセスポリシーを構成します。

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](secure-email-recommended-policies.md)

