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
ms.openlocfilehash: a88fc5f46a6dafda72a24ba5e80587b24a216955
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546482"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a>ゲストおよび外部の B2B アクセスを許可するためのポリシー

この記事では、ビジネス間 (B2B) アカウントアクセス (ゲストおよび外部ユーザー) を許可するために、推奨される一般的な id およびデバイスアクセスポリシーを調整する方法について説明します。 このガイダンスは、 [共通の id およびデバイスアクセスポリシー](identity-access-policies.md)に基づいて構築されています。

これらの推奨事項は、保護の **ベースライン** 層に適用するように設計されています。 ただし、 **機密性** の **高い規制** 保護に対するニーズの粒度に基づいて、推奨事項を調整することもできます。 

B2B ユーザーが Azure Active Directory (Azure AD) テナントを使用して認証するためのパスを指定しても、ユーザーは環境全体にアクセスすることはできません。 B2B ユーザーは、条件付きアクセスポリシーに付与されているサービス内のファイルと共有されているリソースにのみアクセスできます。

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a>ゲストおよび外部アクセスを許可および保護するための共通ポリシーの更新 

ゲストおよび外部アクセスを保護するために、次の図は、共通 id およびデバイスアクセスポリシーで追加または更新するポリシーを示しています。 

[![ゲストアクセスを保護するためのポリシー更新の概要](../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

[この画像のより大きいバージョンを表示する](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

次の表に、更新または新規作成のどちらかを行う必要があるポリシーを示します。 共通のポリシーは、 [一般的な id とデバイスアクセスポリシー](identity-access-policies.md) の記事に記載されている関連する構成手順にリンクしています。

|保護レベル|ポリシー|詳細情報|
|:---------------|:-------|:----------------|
|**Baseline**|[ゲストおよび外部ユーザーに対して MFA を常に要求する](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|この新しいポリシーを作成し、ゲストおよび外部ユーザーにのみ適用します。 [ **サインインリスク**] で、[多要素認証 (MFA) を常に適用する] チェックボックスをオフのままにします。|
|        |[サインインリスクが*中*または*高*の場合は MFA を必須にする](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|ゲストユーザーと外部ユーザーを除外するには、このポリシーを変更します。|
|        |[準拠 PC が必要](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|ゲストユーザーと外部ユーザーを除外するには、このポリシーを変更します。|

条件付きアクセスポリシーにゲストおよび外部ユーザーを含めたり、除外したりするには、[ **包含** または **除外** ] タブをクリックして、 **すべてのゲストと外部ユーザー**をチェックします。

![ゲストを除外するためのコントロールの画面キャプチャ](../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a>詳細情報

### <a name="guests-vs-external-users"></a>ゲストおよび外部ユーザー
Azure AD では、ゲストユーザーと外部ユーザーは同じです。 これらの両方のユーザーの種類は Guest です。 ゲストユーザーは B2B ユーザーです。

Microsoft Teams では、アプリ内のゲストユーザーと外部ユーザーを区別しますが、認証時には B2B ユーザーになります。 Teams ゲストおよび外部ユーザーの詳細については、「 [teams のゲストおよび外部アクセスを有効にする](teams-access-policies.md#enabling-guest-and-external-access-for-teams)」を参照してください。

### <a name="require-mfa-always-for-guest-and-external-users"></a>ゲストおよび外部ユーザーに対して MFA を常に要求する
このポリシーにより、ゲストがホームテナントで MFA に登録されているかどうかにかかわらず、テナント内の MFA を登録するように求められます。 テナント内のリソースにアクセスする場合、ゲストおよび外部ユーザーはすべての要求に対して MFA を使用する必要があります。 

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

