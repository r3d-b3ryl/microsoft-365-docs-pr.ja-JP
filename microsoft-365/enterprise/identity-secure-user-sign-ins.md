---
title: '手順 3: ユーザーのサインインをセキュリティで保護して管理する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: ユーザーの Windows デバイスへのサインインと、Microsoft 365 へのサインインのセキュリティ強化を行うことができます。
ms.openlocfilehash: edf51b344ed8f9c8e13587cc2ccf0ba1ed081da6
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2019
ms.locfileid: "37086411"
---
# <a name="step-3-secure-and-manage-your-user-sign-ins"></a><span data-ttu-id="44ac0-103">手順 3: ユーザーのサインインをセキュリティで保護して管理する</span><span class="sxs-lookup"><span data-stu-id="44ac0-103">Step 3: Secure and manage your user sign-ins</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)


<a name="identity-windows-hello"></a>
## <a name="use-windows-hello-for-business"></a><span data-ttu-id="44ac0-104">Windows Hello for Business を使用する</span><span class="sxs-lookup"><span data-stu-id="44ac0-104">Windows Hello for Business</span></span>

<span data-ttu-id="44ac0-105">*この手順は省略可能であり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="44ac0-105">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="44ac0-106">Windows 10 Enterprise の Windows Hello for Business では、Windows デバイスにサインオンするときのパスワードを強力な 2 要素認証に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="44ac0-106">Windows Hello for Business in Windows 10 Enterprise replaces passwords with strong two-factor authentication when signing on a Windows device.</span></span> <span data-ttu-id="44ac0-107">この 2 要素認証は、デバイスと生体認証または PIN に関連付けられる新しい種類のユーザー資格情報です。</span><span class="sxs-lookup"><span data-stu-id="44ac0-107">The two factors are a new type of user credential that is tied to a device and a biometric or PIN.</span></span>

<span data-ttu-id="44ac0-108">詳しくは、「[Windows Hello for Business の概要](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="44ac0-108">For more information, see [Windows Hello for Business Overview](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).</span></span>


<a name="identity-mfa"></a>
## <a name="set-up-azure-multi-factor-authentication"></a><span data-ttu-id="44ac0-109">Azure Multi-Factor Authentication の設定</span><span class="sxs-lookup"><span data-stu-id="44ac0-109">Set up Azure Multi-Factor Authentication</span></span>

<span data-ttu-id="44ac0-110">*この手順は省略可能であり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="44ac0-110">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="44ac0-111">この手順では、ユーザーのサインインとトランザクションに Azure Multi-Factor Authenticatio (MFA) を設定して、セキュリティの第 2 の層を追加します。</span><span class="sxs-lookup"><span data-stu-id="44ac0-111">In this step, you'll set up Azure Multi-Factor Authentication (MFA) to add a second layer of security to user sign-ins and transactions.</span></span> <span data-ttu-id="44ac0-112">MFA により、ユーザーがパスワードを正しく入力した後に、追加の認証方法が求められます。</span><span class="sxs-lookup"><span data-stu-id="44ac0-112">MFA requires an additional verification method after users have correctly entered their password.</span></span> <span data-ttu-id="44ac0-113">MFA を使わない場合、パスワードが唯一の認証方法になります。</span><span class="sxs-lookup"><span data-stu-id="44ac0-113">Without MFA, the password is the only verification method.</span></span> <span data-ttu-id="44ac0-114">パスワードの問題点は、多くのパスワードが攻撃者が簡単に推測できるものであること、また知らない間に信頼できない人物に共有されてしまうことがあるという点です。</span><span class="sxs-lookup"><span data-stu-id="44ac0-114">The problem with passwords is that many of them are easily guessed by an attacker or unknowingly shared with untrusted parties.</span></span>

<span data-ttu-id="44ac0-115">MFA での 2 番目のセキュリティ層には次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="44ac0-115">With MFA, the second layer of security can be:</span></span>

- <span data-ttu-id="44ac0-116">容易になりすましたり複製することができない信頼性のあるパーソナル デバイス (スマートフォンなど)。</span><span class="sxs-lookup"><span data-stu-id="44ac0-116">A personal and trusted device that isn’t easily spoofed or duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="44ac0-117">指紋認証などの生体認証属性。</span><span class="sxs-lookup"><span data-stu-id="44ac0-117">A biometric attribute, such as a fingerprint.</span></span>

<span data-ttu-id="44ac0-118">ユーザーは、[条件付きアクセス ポリシー](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access)で MFA を有効にして、第 2 の認証方法を構成することができます。これにより、Azure Active Directory (Azure AD) グループを使用して、パイロット ユーザー、地理的地域、部門などのユーザーの指定されたセットに MFA を展開できるようになります。</span><span class="sxs-lookup"><span data-stu-id="44ac0-118">You'll enable MFA and configure the secondary authentication method with [Conditional Access policies](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access), which allow you to use Azure Active Directory (Azure AD) groups to roll out MFA to specified sets of users, such as pilot users, geographical regions, or departments.</span></span> <span data-ttu-id="44ac0-119">MFA が有効になっていることをユーザーに知らせ、その要件 (サインインにスマートフォンを使用することを義務付けるなど) をユーザーが理解し、正常にログインできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="44ac0-119">You'll enable MFA and configure the secondary authentication method on a per-user account basis. Make sure to let users know that MFA is being enabled so they understand the requirements, such as mandatory use of a smart phone to sign in, and can sign in successfully.</span></span> 

<span data-ttu-id="44ac0-120">詳細については、「[クラウドベースの Azure Multi-Factor Authentication の計画](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44ac0-120">For more information, see [Planning a cloud-based Azure Multi-Factor Authentication deployment](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span></span>

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="44ac0-122">テスト ラボ ガイド: Azure Multi-Factor Authentication</span><span class="sxs-lookup"><span data-stu-id="44ac0-122">Test Lab Guide: Azure Multi-Factor Authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="44ac0-123">中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-mfa)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="44ac0-123">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-mfa) for this section.</span></span>

<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a><span data-ttu-id="44ac0-124">資格情報が侵害されないように保護する</span><span class="sxs-lookup"><span data-stu-id="44ac0-124">Protect against credential compromise</span></span>

<span data-ttu-id="44ac0-125">*これはオプションであり、Microsoft 365 Enterprise の E5 バージョンにのみ適用されます*</span><span class="sxs-lookup"><span data-stu-id="44ac0-125">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="44ac0-126">このセクションでは、資格情報が侵害されないように保護するポリシーを構成する方法を学習します。攻撃者は組織のクラウド サービスとデータにアクセスするため、ユーザーのアカウント名とパスワードを突き止めて、資格情報を侵害しようとします。</span><span class="sxs-lookup"><span data-stu-id="44ac0-126">In this section, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data.</span></span> <span data-ttu-id="44ac0-127">Azure AD Identity Protection は、攻撃者によるユーザー アカウントの資格情報の侵害を防ぐさまざまな方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="44ac0-127">Azure AD Identity Protection provides a number of ways to help prevent an attacker from compromising a user account's credentials.</span></span>

<span data-ttu-id="44ac0-128">Azure AD Identity Protection では次の作業を実行できます。</span><span class="sxs-lookup"><span data-stu-id="44ac0-128">With Azure AD Identity Protection, you can:</span></span>

|||
|:---------|:---------|
|<span data-ttu-id="44ac0-129">組織の ID における潜在的な脆弱性の洗い出しと対処</span><span class="sxs-lookup"><span data-stu-id="44ac0-129">Determine and address potential vulnerabilities in your organization’s identities</span></span>|<span data-ttu-id="44ac0-130">Azure AD では機械学習を使用して、サインインやサインイン後のアクティビティなどの異常や不審なアクティビティを検出します。</span><span class="sxs-lookup"><span data-stu-id="44ac0-130">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities. Using this data, Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span> <span data-ttu-id="44ac0-131">このデータを使用して、Azure AD Identity Protection でレポートとアラートを生成すると、ユーザーによる問題の評価と措置に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="44ac0-131">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities. Using this data, Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="44ac0-132">組織の ID に関連する不審なアクションの検出と自動対応</span><span class="sxs-lookup"><span data-stu-id="44ac0-132">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="44ac0-133">特定のリスク レベルに到達すると自動的に検出された問題に対処するよう、リスクベースのポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="44ac0-133">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached.</span></span> <span data-ttu-id="44ac0-134">Azure AD および Microsoft Intune で提供されている他の条件付きアクセス コントロールにこれらのポリシーが加わると、その次のサインイン用のパスワードのリセットや Azure Multi-Factor Authentication を含め、自動的にアクセスをブロックしたり、修正処置を取ったりすることができます。</span><span class="sxs-lookup"><span data-stu-id="44ac0-134">These policies, in addition to other Conditional Access controls provided by Azure AD and Microsoft Intune, can either automatically block access or take corrective actions, including password resets and requiring Azure Multi-Factor Authentication for subsequent sign-ins.</span></span>|
|<span data-ttu-id="44ac0-135">不審なインシデントを調査し、管理操作によって解決する</span><span class="sxs-lookup"><span data-stu-id="44ac0-135">Investigate suspicious incidents and resolve them with administrative actions</span></span>|<span data-ttu-id="44ac0-p107">セキュリティ インシデントに関する情報を使用して、リスク イベントを調査できます。調査の追跡と修復処理 (パスワードのリセットなど) の開始のための基本的なワークフローを利用できます。</span><span class="sxs-lookup"><span data-stu-id="44ac0-p107">You can investigate risk events using information about the security incident. Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span>|

<span data-ttu-id="44ac0-138">[Azure AD Identity Protection の詳細情報](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44ac0-138">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="44ac0-139">[Azure AD Identity Protection を有効にする手順](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44ac0-139">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

<span data-ttu-id="44ac0-140">この手順の結果として、Azure AD Identity Protection が有効になり、次の目的で Azure AD Identity Protection を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="44ac0-140">The results of this step are that you've enabled Azure AD Identity protection and you are using it to:</span></span>

- <span data-ttu-id="44ac0-141">潜在的な ID の脆弱性に対処する。</span><span class="sxs-lookup"><span data-stu-id="44ac0-141">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="44ac0-142">資格情報の侵害の疑いがあるものを検出する。</span><span class="sxs-lookup"><span data-stu-id="44ac0-142">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="44ac0-143">発生している不審な ID インシデントを調査して対処する。</span><span class="sxs-lookup"><span data-stu-id="44ac0-143">Investigate and address ongoing suspicious identity incidents.</span></span>

|||
|:-------|:-----|
|![Microsoft クラウド のテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="44ac0-145">テスト ラボ ガイド: Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="44ac0-145">Test Lab Guide: Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="44ac0-146">中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-ident-prot)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="44ac0-146">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-ident-prot) for this section.</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="44ac0-147">ユーザー アカウントを追加する</span><span class="sxs-lookup"><span data-stu-id="44ac0-147">Add your user accounts</span></span>](identity-add-user-accounts.md) |
