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
# <a name="step-5-set-up-multi-factor-authentication"></a><span data-ttu-id="2c347-103">手順 5: 多要素認証をセットアップする</span><span class="sxs-lookup"><span data-stu-id="2c347-103">Step 5: Set up multi-factor authentication</span></span>

<span data-ttu-id="2c347-104">*この手順はオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="2c347-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="2c347-p101">この手順では、ユーザー サインインとトランザクションに 2 番目のセキュリティ層を追加するため、多要素認証 (MFA) をセットアップします。MFA では、ユーザーがパスワードを正しく入力した後に別の検証方式が必要になります。MFA を使用しない場合、パスワードが唯一の検証方式となります。パスワードの問題点は、多くのパスワードが攻撃者が簡単に推測できるものであることと、また知らない間に信頼できない人物と共有してしまうことがあるという点です。</span><span class="sxs-lookup"><span data-stu-id="2c347-p101">In Step 7, you'll set up multi-factor authentication (MFA) to add a second layer of security to user sign-ins and transactions. MFA requires an additional verification method after users have correctly entered their password. Without MFA, the password is the only verification method. The problem with passwords is that many of them are easily guessed by an attacker or unknowingly shared with untrusted parties.</span></span>

<span data-ttu-id="2c347-109">MFA での 2 番目のセキュリティ層には次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="2c347-109">With MFA, the second layer of security can be:</span></span>

- <span data-ttu-id="2c347-110">容易になりすましたり複製することができない信頼性のあるパーソナル デバイス (スマートフォンなど)。</span><span class="sxs-lookup"><span data-stu-id="2c347-110">A personal and trusted device that isn’t easily spoofed or duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="2c347-111">指紋認証などの生体認証属性。</span><span class="sxs-lookup"><span data-stu-id="2c347-111">A biometric attribute, such as a fingerprint.</span></span>

<span data-ttu-id="2c347-p102">MFA を有効にして、ユーザー アカウントごとにセカンダリ認証方式を構成します。MFA が有効になっていることをユーザーに知らせ、その要件 (サインインにスマートフォンを使用することを義務付けるなど) をユーザーが理解し、正常にログインできるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="2c347-p102">You'll enable MFA and configure the secondary authentication method on a per-user account basis. Make sure to let users know that MFA is being enabled so they understand the requirements (such as mandatory use of a smart phone to sign in) and can sign in successfully.</span></span>

<span data-ttu-id="2c347-114">詳細については、「[Office 365 展開用の多要素認証の計画](https://support.office.com/article/Plan-for-multifactor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c347-114">For more information, see [Plan for multi-factor authentication for Office 365 Deployments](https://support.office.com/article/Plan-for-multifactor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba).</span></span>

<span data-ttu-id="2c347-115">多要素認証を構成するには、[Office 365 ユーザーに多要素認証をセットアップします](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6)。</span><span class="sxs-lookup"><span data-stu-id="2c347-115">To configure multifactor authentication, [Set up multi-factor authentication for Office 365 users](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6).</span></span>

<span data-ttu-id="2c347-p103">条件付きアクセス ポリシーで MFA を義務付けることができます。たとえば、認証に中または高レベルのリスクがあると判別された場合に MFA を必要とするポリシーを構成できます。詳細については、[共通 ID とデバイスのアクセス ポリシー](identity-access-policies.md#require-mfa-based-on-sign-in-risk)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c347-p103">You can also require MFA with conditional access policies. For example, you can configure a policy that required MFA when the authentication is determined to be of medium or high risk. For more information, see [Step 2: Configure conditional access policy settings](identity-access-policies.md#require-mfa-based-on-sign-in-risk) in the Information Protection phase.</span></span>

>[!Note]
><span data-ttu-id="2c347-p104">Microsoft Office 2010 以前や Apple Mail などの一部のアプリケーションでは MFA を使用できません。このようなアプリを使用するには、従来のパスワードの代わりに「アプリ パスワード」を使用する必要があります。アプリ パスワードでは、アプリが MFA をバイパスして処理を続行できます。アプリ パスワードについては、「[Office 365 のアプリ パスワードを作成する](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c347-p104">In some applications, such as Microsoft Office 2010 or older and Apple Mail, you can’t use MFA. To use these apps, you’ll need to use “app passwords” in place of your traditional password. The app password allows the app to bypass MFA and continue working. To learn more about app passwords, see [Create an app password for Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).</span></span>
>

|||
|:-------|:-----|
|![Microsoft クラウド のテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="2c347-124">テスト ラボ ガイド: 多要素認証</span><span class="sxs-lookup"><span data-stu-id="2c347-124">Test Lab Guide: Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="2c347-125">中間チェックポイントとして、この手順の[終了条件](identity-exit-criteria.md#crit-identity-mfa)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="2c347-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-mfa) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="2c347-126">次の手順</span><span class="sxs-lookup"><span data-stu-id="2c347-126">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="2c347-127">資格情報が侵害されないように保護する</span><span class="sxs-lookup"><span data-stu-id="2c347-127">Protect against credential compromise</span></span>](identity-azure-ad-identity-protection.md) |

