---
title: ゲストおよび外部の B2B アクセスを許可するための id およびデバイスアクセスポリシー-Microsoft 365 for enterprise |Microsoft Docs
description: ゲストおよび外部ユーザーのアクセスを保護するために推奨される条件付きアクセスと関連ポリシーについて説明します。
author: BrendaCarter
manager: johmar
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 0ab4a2d48a1ac90f48bbfee82239fc0c4c1d55d5
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686828"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a>ゲストおよび外部の B2B アクセスを許可するためのポリシー
この記事では、推奨される一般的な id およびデバイスアクセスポリシーを調整して、B2B アカウントアクセス (ゲストおよび外部ユーザー) を許可する方法について説明します。 このガイダンスは、 [共通の id およびデバイスアクセスポリシー](identity-access-policies.md)に基づいて構築されています。

これらの推奨事項は、保護の **ベースライン** 層に適用するように設計されています。 ただし、 **機密性** の **高い規制** 保護に対するニーズの粒度に基づいて、推奨事項を調整することができます。 

Azure AD テナントを使用して認証するための B2B ユーザーのパスを指定しても、ユーザーは環境全体にアクセスできません。 B2B ユーザーは、条件付きアクセスポリシーに付与されているサービス内のファイルと共有されているリソースにのみアクセスできます。

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a>ゲストおよび外部アクセスを許可および保護するための共通ポリシーの更新 

次の図は、一般的な id とデバイスのアクセスポリシーと、ゲストおよび外部アクセスを保護するために追加または更新するポリシー (鉛筆アイコン) を示しています。 

![ゲストアクセスを保護するためのポリシー更新の概要](../media/identity-access-ruleset-guest.png)

次の表に、更新または新規作成のどちらかを行う必要があるポリシーを示します。 共通のポリシーは、 [一般的な id とデバイスアクセスポリシー](identity-access-policies.md) の記事に記載されている関連する構成手順にリンクしています。

|保護レベル|ポリシー|詳細情報|
|:---------------|:-------|:----------------|
|**Baseline**|[ゲストおよび外部ユーザーに対して MFA を常に要求する](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|この新しいルールを作成し、ゲストおよび外部ユーザーにのみ適用します。 [サインインリスク] で、[すべてのオプション] をオフのままにして、常に MFA を適用します。|
|        |[サインインリスクが*中*または*高*の場合は MFA を必須にする](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|ゲストユーザーと外部ユーザーを除外するには、このルールを変更します。|
|        |[準拠 PC が必要](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|ゲストユーザーと外部ユーザーを除外するには、このルールを変更します。|

条件付きアクセスルールにゲストと外部ユーザーを含めたり、除外したりするには、[包含または除外] タブをクリックして、 **すべてのゲストと外部ユーザー**をチェックします。

![ゲストを除外するためのコントロールの画面キャプチャ](../media/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a>詳細情報

### <a name="guests-vs-external-users"></a>ゲストおよび外部ユーザー
Azure AD では、ゲストユーザーと外部ユーザーは同じです。 これらの両方のユーザーの種類は Guest です。 ゲストユーザーは B2B ユーザーです。

Microsoft Teams では、アプリ内のゲストユーザーと外部ユーザーを区別しますが、認証時には B2B ユーザーになります。 Teams ゲストおよび外部ユーザーの詳細については、「 [teams のゲストおよび外部アクセスを有効にする](teams-access-policies.md#enabling-guest-and-external-access-for-teams)」を参照してください。

### <a name="require-mfa-always-for-guest-and-external-users"></a>ゲストおよび外部ユーザーに対して MFA を常に要求する
このルールは、ゲストのホームテナントに MFA が登録されているかどうかに関係なく、ゲストをテナントに登録することを確認します。 テナント内のリソースにアクセスする場合、ゲストおよび外部ユーザーはすべての要求に対して MFA を使用する必要があります。 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a>リスクベースの MFA からゲストユーザーと外部ユーザーを除外する
組織では Id 保護を使用して B2B ユーザーに対してリスクベースのポリシーを適用することができますが、ホームディレクトリに存在する id があるため、リソースディレクトリでの B2B コラボレーションユーザーの Id 保護の実装には制限があります。 これらの制限により、ゲストユーザーをリスクベースの MFA ポリシーから除外し、これらのユーザーが常に MFA を使用するようにすることをお勧めします。 

詳細については、「 [B2B コラボレーションユーザーの Id 保護の制限事項](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)」を参照してください。 

### <a name="excluding-guest-and-external-users-from-device-management"></a>デバイス管理からゲストユーザーと外部ユーザーを除外する 
1つの組織のみがデバイスを管理できます。 デバイスコンプライアンスを必要とするポリシーからゲストおよび外部ユーザーを除外しない場合、これらのポリシーによってこれらのユーザーがブロックされます。 

## <a name="next-steps"></a>次の手順

[Teams の条件付きアクセスを有効にする方法について説明します。](teams-access-policies.md)

