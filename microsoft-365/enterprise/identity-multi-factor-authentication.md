---
title: '手順 5: 多要素認証をセットアップする'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/05/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: ユーザー アカウントの多要素認証について理解し、構成します。
ms.openlocfilehash: a54eb047c94430a2b3f61d06500c929e400e3d82
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869483"
---
# <a name="step-5-set-up-multi-factor-authentication"></a>手順 5: 多要素認証をセットアップする

*この手順はオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

この手順では、ユーザー サインインとトランザクションに 2 番目のセキュリティ層を追加するため、多要素認証 (MFA) をセットアップします。MFA では、ユーザーがパスワードを正しく入力した後に別の検証方式が必要になります。MFA を使用しない場合、パスワードが唯一の検証方式となります。パスワードの問題点は、多くのパスワードが攻撃者が簡単に推測できるものであることと、また知らない間に信頼できない人物と共有してしまうことがあるという点です。

MFA での 2 番目のセキュリティ層には次のものがあります。

- 容易になりすましたり複製することができない信頼性のあるパーソナル デバイス (スマートフォンなど)。
- 指紋認証などの生体認証属性。

MFA を有効にして、ユーザー アカウントごとにセカンダリ認証方式を構成します。MFA が有効になっていることをユーザーに知らせ、その要件 (サインインにスマートフォンを使用することを義務付けるなど) をユーザーが理解し、正常にログインできるようにしてください。

詳細については、「[Office 365 展開用の多要素認証の計画](https://support.office.com/article/Plan-for-multifactor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba)」を参照してください。

多要素認証を構成するには、[Office 365 ユーザーに多要素認証をセットアップします](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6)。

条件付きアクセス ポリシーで MFA を義務付けることができます。たとえば、認証に中または高レベルのリスクがあると判別された場合に MFA を必要とするポリシーを構成できます。詳細については、[共通 ID とデバイスのアクセス ポリシー](identity-access-policies.md#require-mfa-based-on-sign-in-risk)に関するページを参照してください。

>[!Note]
>Microsoft Office 2010 以前や Apple Mail などの一部のアプリケーションでは MFA を使用できません。このようなアプリを使用するには、従来のパスワードの代わりに「アプリ パスワード」を使用する必要があります。アプリ パスワードでは、アプリが MFA をバイパスして処理を続行できます。アプリ パスワードについては、「[Office 365 のアプリ パスワードを作成する](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183)」を参照してください。
>

|||
|:-------|:-----|
|![Microsoft クラウド のテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [テスト ラボ ガイド: 多要素認証](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

中間チェックポイントとして、この手順の[終了条件](identity-exit-criteria.md#crit-identity-mfa)を確認できます。

## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)| [資格情報が侵害されないように保護する](identity-azure-ad-identity-protection.md) |

