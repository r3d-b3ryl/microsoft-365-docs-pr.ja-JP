---
title: 手順 3. ID を保護する
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- ransomware
- m365solution-ransomware
ms.custom: seo-marvel-jun2020
keywords: ランサムウェア、人が操作するランサムウェア、人間が操作するランサムウェア、HumOR、強要攻撃、ランサムウェア攻撃、暗号化、暗号ウイルス学
description: 安全なサインインと条件付きアクセスを使用して、Microsoft 365 リソースをランサムウェア攻撃から保護します。
ms.openlocfilehash: 5761cb402be3fb0be907be8f3677a8e3ecbfd875
ms.sourcegitcommit: 7e7effd8ef4ffe75cdee7bb8517fec8608e4c230
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2021
ms.locfileid: "59444617"
---
# <a name="step-3-protect-identities"></a>手順 3. ID を保護する

次のセクションを使用して、通常、大規模なランサムウェア攻撃の最初の段階である資格情報の侵害から組織を保護します。

## <a name="increase-sign-in-security"></a>サインイン セキュリティを強化する

Azure Active Directory (Azure AD) のユーザー アカウントに[パスワードなしの認証](/azure/active-directory/authentication/howto-authentication-passwordless-deployment)を使用します。

パスワードなしの認証への移行中は、パスワード認証を引き続き使用するユーザー アカウントに対して次のベスト プラクティスを使用します。

- [Azure AD パスワード保護](/azure/active-directory/authentication/concept-password-ban-bad)を使用して、既知の脆弱なカスタム パスワードをブロックします。
- 既知の脆弱なカスタム パスワードのブロックを [Azure AD パスワード保護を使用したオンプレミスの Active Directory ドメイン サービス (AD DS)](/azure/active-directory/authentication/concept-password-ban-bad-on-premises) に拡張します。
- [セルフサービスによるパスワード リセット (SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks) を使用して、ユーザーが自分のパスワードを変更できるようにします。

次に、[共通 ID およびデバイス アクセス ポリシー](/microsoft-365/security/office-365-security/identity-access-policies)を実装します。 これらのポリシーは、Microsoft 365 クラウド サービスへのアクセスに対してより高いセキュリティを提供します。 

ユーザー サインインの場合、これらのポリシーには次のものが含まれます。

- 優先アカウント (直ちに)、最終的にはすべてのユーザー アカウントに MFA を要求する。
- MFA を使用するためにリスクの高いサインインを要求する。
- リスクの高いサインインを持つリスクの高いユーザーにパスワードの変更を要求する。

## <a name="prevent-privilege-escalation"></a>特権エスカレーションを防止する

次のベスト プラクティスを使用します。

- 「サインインにパスワードを使用しているユーザー アカウントの[サインイン セキュリティを強化する](#increase-sign-in-security)」で説明されているように、[最小特権](/windows-server/identity/ad-ds/plan/security-best-practices/implementing-least-privilege-administrative-models)の原則を実装し、パスワード保護を使用します。 
- ドメイン全体の管理者レベルのサービス アカウントの使用は避けてください。 
- ローカル管理者特権を制限して、リモート アクセス トロイの木馬(RAT) やその他の不要なアプリケーションのインストールを制限します。
- 管理ポータルへのアクセスを許可する前に、Azure AD 条件付きアクセスを使用して、ユーザーとワークステーションの信頼を明示的に検証します。 Azure ポータルについては、[この例](/azure/active-directory/conditional-access/howto-conditional-access-policy-azure-management)を参照してください。
- ローカル管理者のパスワード管理を有効にします。
- 特権の高いアカウントがサインインして資格情報を公開している場所を特定します。 特権の高いアカウントは、ワークステーションに存在しないようにする必要があります。
- パスワードと資格情報のローカル ストレージを無効にします。

## <a name="impact-on-users-and-change-management"></a>ユーザーへの影響と変更管理

組織内のユーザーに次のことを認識させる必要があります。

- より強力なパスワードの新しい要件。
- MFA の必要な使用や MFA の二次認証方法の登録など、サインイン プロセスの変更。
- SSPR でのパスワード メンテナンスの使用。 たとえば、パスワードのリセットのためにヘルプデスクを呼び出す必要はもうありません。
- 危険であると判断されたサインインに対して、MFA またはパスワードの変更を要求するプロンプト。

## <a name="resulting-configuration"></a>結果の構成

手順 1 から 3 のテナントのランサムウェア防止を次に示します。

![手順 3 の後の、Microsoft 365 テナントのランサムウェア防止](../media/ransomware-protection-microsoft-365/ransomware-protection-microsoft-365-architecture-step3.png)

## <a name="next-step"></a>次の手順

[![Microsoft 365 によるランサムウェア防止の手順 4](../media/ransomware-protection-microsoft-365/ransomware-protection-microsoft-365-step4.png)](ransomware-protection-microsoft-365-devices.md)

[手順 4](ransomware-protection-microsoft-365-devices.md) に進み、Microsoft 365 テナント内のデバイス (エンドポイント) を保護します。 
