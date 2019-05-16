---
title: '手順 4: セキュリティで保護されたユーザー認証を構成する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/17/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: ユーザー アカウントの多要素認証について理解し、構成します。
ms.openlocfilehash: 73e884802329765fd6a89cfb7d0e04116c17968c
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072087"
---
# <a name="step-4-configure-secure-user-authentication"></a><span data-ttu-id="75123-103">手順 4: セキュリティで保護されたユーザー認証を構成する</span><span class="sxs-lookup"><span data-stu-id="75123-103">Step 4: Configure secure user authentication</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-mfa"></a>
## <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="75123-104">多要素認証をセットアップする</span><span class="sxs-lookup"><span data-stu-id="75123-104">Set up multi-factor authentication</span></span>

<span data-ttu-id="75123-105">*この手順はオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="75123-105">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="75123-p101">この手順では、ユーザー サインインとトランザクションに 2 番目のセキュリティ層を追加するため、多要素認証 (MFA) をセットアップします。MFA では、ユーザーがパスワードを正しく入力した後に別の検証方式が必要になります。MFA を使用しない場合、パスワードが唯一の検証方式となります。パスワードの問題点は、多くのパスワードが攻撃者が簡単に推測できるものであることと、また知らない間に信頼できない人物と共有してしまうことがあるという点です。</span><span class="sxs-lookup"><span data-stu-id="75123-p101">In this step, you'll set up multi-factor authentication (MFA) to add a second layer of security to user sign-ins and transactions. MFA requires an additional verification method after users have correctly entered their password. Without MFA, the password is the only verification method. The problem with passwords is that many of them are easily guessed by an attacker or unknowingly shared with untrusted parties.</span></span>

<span data-ttu-id="75123-110">MFA での 2 番目のセキュリティ層には次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="75123-110">With MFA, the second layer of security can be:</span></span>

- <span data-ttu-id="75123-111">容易になりすましたり複製することができない信頼性のあるパーソナル デバイス (スマートフォンなど)。</span><span class="sxs-lookup"><span data-stu-id="75123-111">A personal and trusted device that isn’t easily spoofed or duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="75123-112">指紋認証などの生体認証属性。</span><span class="sxs-lookup"><span data-stu-id="75123-112">A biometric attribute, such as a fingerprint.</span></span>

<span data-ttu-id="75123-p102">MFA を有効にして、ユーザー アカウントごとにセカンダリ認証方式を構成します。MFA が有効になっていることをユーザーに知らせ、その要件 (サインインにスマートフォンを使用することを義務付けるなど) をユーザーが理解し、正常にログインできるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="75123-p102">You'll enable MFA and configure the secondary authentication method on a per-user account basis. Make sure to let users know that MFA is being enabled so they understand the requirements, such as mandatory use of a smart phone to sign in, and can sign in successfully.</span></span>

<span data-ttu-id="75123-115">詳細については、[多要素認証の計画](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75123-115">For more information, see [Plan for multi-factor authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span></span>

>[!Note]
><span data-ttu-id="75123-p103">Microsoft Office 2010 以前や Apple Mail などの一部のアプリケーションでは MFA を使用できません。このようなアプリを使用するには、従来のパスワードの代わりに「アプリ パスワード」を使用する必要があります。アプリ パスワードでは、アプリが MFA をバイパスして処理を続行できます。アプリ パスワードについては、「[Office 365 のアプリ パスワードを作成する](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75123-p103">In some applications, such as Microsoft Office 2010 or older and Apple Mail, you can’t use MFA. To use these apps, you’ll need to use “app passwords” in place of your traditional password. The app password allows the app to bypass MFA and continue working. To learn more about app passwords, see [Create an app password for Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).</span></span>
>

|||
|:-------|:-----|
|![Microsoft クラウド のテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="75123-121">テスト ラボ ガイド: 多要素認証</span><span class="sxs-lookup"><span data-stu-id="75123-121">Test Lab Guide: Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="75123-122">中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-mfa)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="75123-122">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-mfa) for this section.</span></span>



<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a><span data-ttu-id="75123-123">資格情報が侵害されないように保護する</span><span class="sxs-lookup"><span data-stu-id="75123-123">Protect against credential compromise</span></span>

<span data-ttu-id="75123-124">*これはオプションであり、Microsoft 365 Enterprise の E5 バージョンにのみ適用されます*</span><span class="sxs-lookup"><span data-stu-id="75123-124">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="75123-125">このセクションでは、資格情報が侵害されないように保護するポリシーを構成する方法を学習します。攻撃者は組織のクラウド サービスとデータにアクセスするため、ユーザーのアカウント名とパスワードを突き止めて、資格情報を侵害しようとします。</span><span class="sxs-lookup"><span data-stu-id="75123-125">In this section, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data.</span></span> <span data-ttu-id="75123-126">Azure AD Identity Protection は、攻撃者が複数のアカウントやグループを横方向に移動し、最終的に最も重要なデータにたどり着くのを防ぐさまざまな方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="75123-126">Azure AD Identity Protection provides a number of ways to help prevent an attacker from moving laterally through your accounts and groups, and subsequently, to your most valuable data.</span></span>

<span data-ttu-id="75123-127">Azure AD Identity Protection では次の作業を実行できます。</span><span class="sxs-lookup"><span data-stu-id="75123-127">With Azure AD Identity Protection, you can:</span></span>

|||
|:---------|:---------|
|<span data-ttu-id="75123-128">組織の ID における潜在的な脆弱性の洗い出しと対処</span><span class="sxs-lookup"><span data-stu-id="75123-128">Determine and address potential vulnerabilities in your organization’s identities</span></span>|<span data-ttu-id="75123-p105">Azure AD では、機械学習を使用して異常や不審なアクティビティ (サインインとサインイン後の活動など) を検出します。Identity Protection はこのデータを使用して、問題の評価と対処の実施に役立つレポートとアラートを生成します。</span><span class="sxs-lookup"><span data-stu-id="75123-p105">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities. Using this data, Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="75123-131">組織の ID に関連する不審なアクションの検出と自動対応</span><span class="sxs-lookup"><span data-stu-id="75123-131">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="75123-p106">指定されているリスク レベルに達した時点で、検出された問題に対し自動的に対応するリスクベースのポリシーを構成できます。このリスクベースのポリシーと、Azure Active Directory および Enterprise Mobility + Security (EMS) の他の条件付きアクセス制御との組み合わせにより、自動的にアクセスをブロックするか、または修正処置 (パスワード リセットと後続のサインインでの多要素認証の義務付けなど) を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="75123-p106">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached. These policies, in addition to other conditional access controls provided by Azure Active Directory and Enterprise Mobility + Security (EMS), can either automatically block access or take corrective actions, including password resets and requiring multi-factor authentication for subsequent sign-ins.</span></span>|
|<span data-ttu-id="75123-134">不審なインシデントを調査し、管理操作によって解決する</span><span class="sxs-lookup"><span data-stu-id="75123-134">Investigate suspicious incidents and resolve them with administrative actions</span></span>|<span data-ttu-id="75123-p107">セキュリティ インシデントに関する情報を使用して、リスク イベントを調査できます。調査の追跡と修復処理 (パスワードのリセットなど) の開始のための基本的なワークフローを利用できます。</span><span class="sxs-lookup"><span data-stu-id="75123-p107">You can investigate risk events using information about the security incident. Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span>|

<span data-ttu-id="75123-137">[Azure AD Identity Protection の詳細情報](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75123-137">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="75123-138">[Azure AD Identity Protection を有効にする手順](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75123-138">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

<span data-ttu-id="75123-139">この手順の結果として、Azure AD Identity Protection が有効になり、次の目的で Azure AD Identity Protection を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="75123-139">The results of this step are that you've enabled Azure AD Identity protection and you are using it to:</span></span>

- <span data-ttu-id="75123-140">潜在的な ID の脆弱性に対処する。</span><span class="sxs-lookup"><span data-stu-id="75123-140">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="75123-141">資格情報の侵害の疑いがあるものを検出する。</span><span class="sxs-lookup"><span data-stu-id="75123-141">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="75123-142">発生している不審な ID インシデントを調査して対処する。</span><span class="sxs-lookup"><span data-stu-id="75123-142">Investigate and address ongoing suspicious identity incidents.</span></span>

|||
|:-------|:-----|
|![Microsoft クラウド のテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="75123-144">テスト ラボ ガイド: Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="75123-144">Test Lab Guide: Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="75123-145">中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-ident-prot)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="75123-145">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-ident-prot) for this section.</span></span>

## <a name="monitor-tenant-and-sign-in-activity"></a><span data-ttu-id="75123-146">テナントとサインイン アクティビティを監視する</span><span class="sxs-lookup"><span data-stu-id="75123-146">Monitor tenant and sign-in activity</span></span>

<span data-ttu-id="75123-147">*この手順はオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="75123-147">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="75123-p108">この手順では、Azure AD のレポートを使用して監査ログおよびサインイン アクティビティを確認します。2 種類のレポートを利用できます。</span><span class="sxs-lookup"><span data-stu-id="75123-p108">In this step, you'll review audit logs and sign-in activity using Azure AD reporting. Two types of reports are available.</span></span>

<span data-ttu-id="75123-p109">**監査ログ アクティビティ レポート**には、Azure AD テナントで実行されたすべてのタスクの履歴が記録されます。このレポートから、次のような情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="75123-p109">The **Audit logs activity report** records the history of every task performed in your Azure AD tenant. This report answers questions like:</span></span>

- <span data-ttu-id="75123-152">管理者グループにユーザーを追加したユーザー</span><span class="sxs-lookup"><span data-stu-id="75123-152">Who added someone to an admin group?</span></span>
- <span data-ttu-id="75123-153">特定のアプリにサインインしたユーザー</span><span class="sxs-lookup"><span data-stu-id="75123-153">Which users are signing into a specific app?</span></span>
- <span data-ttu-id="75123-154">パスワード リセットの実行回数</span><span class="sxs-lookup"><span data-stu-id="75123-154">How many password resets are happening?</span></span>

<span data-ttu-id="75123-p110">**サインイン アクティビティ レポート**には、監査ログ レポートで報告されたタスクを実行したユーザーが記録されます。このレポートから、次のような情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="75123-p110">The **Sign-ins activity report** records who performed the tasks reported by the audit logs report. This report answers questions like:</span></span>

- <span data-ttu-id="75123-157">調査中の特定のユーザーのサインイン パターン</span><span class="sxs-lookup"><span data-stu-id="75123-157">For a specific user under investigation, what is their sign-in pattern?</span></span>
- <span data-ttu-id="75123-158">日、週、月あたりのサインインの回数</span><span class="sxs-lookup"><span data-stu-id="75123-158">What is my volume of sign-ins over a day, week, or month?</span></span>
- <span data-ttu-id="75123-159">失敗したサインインの回数とそのアカウント</span><span class="sxs-lookup"><span data-stu-id="75123-159">How many of these sign-in attempts were not successful, and for which accounts?</span></span>

<span data-ttu-id="75123-160">レポートとレポートへのアクセス方法の詳細については、「[Azure Active Directory レポート](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75123-160">For more information about the reports and how to access them, see [Azure Active Directory reporting](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).</span></span>

<span data-ttu-id="75123-161">この手順を実行すると、これらのレポートを認識でき、また計画とセキュリティの目的でレポートを使用して Azure AD のイベントとアクティビティに関する情報を把握する方法を理解できます。</span><span class="sxs-lookup"><span data-stu-id="75123-161">As a result of this step, you'll gain awareness of these reports and an understanding of how you can use them to gain insights on Azure AD events and activities for planning and security purposes.</span></span>



## <a name="next-step"></a><span data-ttu-id="75123-162">次の手順</span><span class="sxs-lookup"><span data-stu-id="75123-162">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="75123-163">ユーザーのアクセスを簡素化する</span><span class="sxs-lookup"><span data-stu-id="75123-163">Simplify access for users</span></span>](identity-password-reset.md) |

