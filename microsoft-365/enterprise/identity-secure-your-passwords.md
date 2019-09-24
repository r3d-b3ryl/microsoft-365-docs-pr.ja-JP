---
title: '手順 2: パスワードをセキュリティで保護する'
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
description: 組織全体でパスワードを強力かつ管理しやすいものにする必要があります。
ms.openlocfilehash: 06d936a68432b55912b1c10839336dc94e698f51
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2019
ms.locfileid: "37086410"
---
# <a name="step-2-secure-your-passwords"></a><span data-ttu-id="7a15e-103">手順 2: パスワードをセキュリティで保護する</span><span class="sxs-lookup"><span data-stu-id="7a15e-103">Step 2: Secure your privileged identities</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-password-prot"></a>
## <a name="prevent-bad-passwords"></a><span data-ttu-id="7a15e-104">脆弱なパスワードを防止する</span><span class="sxs-lookup"><span data-stu-id="7a15e-104">Prevent bad passwords</span></span>

<span data-ttu-id="7a15e-105">*この手順は省略可能であり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="7a15e-105">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="7a15e-106">すべてのユーザーが [Microsoft のパスワードのガイダンス](https://www.microsoft.com/research/publication/password-guidance/)を使用してユーザー アカウントのパスワードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a15e-106">All you users should be using [Microsoft's password guidance](https://www.microsoft.com/research/publication/password-guidance/) to create their user account passwords.</span></span>

<span data-ttu-id="7a15e-107">ユーザーがパスワードを容易に作成するのを防ぐため、Azure AD のパスワード保護を使用します。この機能では、グローバル禁止パスワード リストと指定したカスタムの禁止パスワード リスト (省略可能) の両方を使用します。</span><span class="sxs-lookup"><span data-stu-id="7a15e-107">To prevent users from creating easily determined password, use Azure AD password protection, which uses both a global banned password list and an optional custom banned password list that you specify.</span></span> <span data-ttu-id="7a15e-108">たとえば、次のような組織固有の用語を指定できます。</span><span class="sxs-lookup"><span data-stu-id="7a15e-108">For example, you can specify terms that are specific to your organization, such as:</span></span>

- <span data-ttu-id="7a15e-109">ブランド名</span><span class="sxs-lookup"><span data-stu-id="7a15e-109">Brand names</span></span>
- <span data-ttu-id="7a15e-110">製品名</span><span class="sxs-lookup"><span data-stu-id="7a15e-110">Product names</span></span>
- <span data-ttu-id="7a15e-111">場所 (たとえば、会社の本部など)</span><span class="sxs-lookup"><span data-stu-id="7a15e-111">Locations (for example, such as company headquarters)</span></span>
- <span data-ttu-id="7a15e-112">会社固有の内部用語</span><span class="sxs-lookup"><span data-stu-id="7a15e-112">Company-specific internal terms</span></span>
- <span data-ttu-id="7a15e-113">会社固有の意味を持つ略語</span><span class="sxs-lookup"><span data-stu-id="7a15e-113">Abbreviations that have specific company meaning</span></span>

<span data-ttu-id="7a15e-114">[クラウド内](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)および[オンプレミスの Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) に対する脆弱なパスワードを禁止できます。</span><span class="sxs-lookup"><span data-stu-id="7a15e-114">You can ban bad passwords [in the cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span></span>

<span data-ttu-id="7a15e-115">中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-password-prot)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="7a15e-115">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-password-prot) for this section.</span></span>

<a name="identity-pw-reset"></a>
## <a name="simplify-password-resets"></a><span data-ttu-id="7a15e-116">パスワード再設定を簡素化する</span><span class="sxs-lookup"><span data-stu-id="7a15e-116">Simplify password resets</span></span>

<span data-ttu-id="7a15e-117">*この手順はオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="7a15e-117">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="7a15e-118">このセクションでは、セルフサービスによるパスワードのリセット (SSPR) を有効にして、ユーザーが自分のパスワードやアカウントの再設定やロック解除を行えるようにします。</span><span class="sxs-lookup"><span data-stu-id="7a15e-118">In this section, you'll enable self-service password reset (SSPR) to allow users to reset or unlock their passwords or accounts.</span></span> <span data-ttu-id="7a15e-119">誤用または悪用について警告するため、通知と共に、ユーザーがいつシステムにアクセスしたかを追跡する詳細なレポート作成機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7a15e-119">To alert you to misuse or abuse, you can use the detailed reporting that tracks when users access the system, along with notifications.</span></span> <span data-ttu-id="7a15e-120">パスワード再設定をデプロイする前にパスワードの書き戻しを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a15e-120">You must enable password writeback before you can deploy password resets.</span></span>

<span data-ttu-id="7a15e-121">「[セルフサービスによるパスワードのリセットを適切にロールアウトする方法](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a15e-121">See the [instructions to roll out password reset](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span></span>

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="7a15e-123">テスト ラボ ガイド: パスワードのリセット</span><span class="sxs-lookup"><span data-stu-id="7a15e-123">Test Lab Guide: Password reset</span></span>](password-reset-m365-ent-test-environment.md) |
|||

<span data-ttu-id="7a15e-124">中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-pw-reset)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="7a15e-124">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-reset) for this section.</span></span>


<a name="identity-sso"></a>
## <a name="simplify-user-sign-in"></a><span data-ttu-id="7a15e-125">ユーザー サインインを簡素化する</span><span class="sxs-lookup"><span data-stu-id="7a15e-125">Simplify user sign-in</span></span>

<span data-ttu-id="7a15e-126">*この手順はハイブリッド環境でオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="7a15e-126">*This is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="7a15e-127">このセクションでは、Azure Active Directory シームレス シングル サインオン (Azure AD シームレス SSO) をセットアップして、パスワード ハッシュ同期 (PHS) とパススルー認証 (PTA) と連携することにより、ユーザーがパスワードを (さらに、多くの場合ユーザー名も) 入力せずに Azure AD ユーザー アカウントを使用するサービスにサインインできるようにします。</span><span class="sxs-lookup"><span data-stu-id="7a15e-127">In this section, you'll set up Azure Active Directory Seamless Single Sign-On (Azure AD Seamless SSO) to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames.</span></span> <span data-ttu-id="7a15e-128">これにより、ユーザーは Office 365 などのクラウド ベースのアプリケーションに簡単にアクセスできるようになります。ID フェデレーション サーバーのような追加のオンプレミス コンポーネントは不要です。</span><span class="sxs-lookup"><span data-stu-id="7a15e-128">This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="7a15e-129">Azure AD Connect ツールを使用して Azure AD シームレス SSO を構成します。</span><span class="sxs-lookup"><span data-stu-id="7a15e-129">You'll configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span>

<span data-ttu-id="7a15e-130">「[Azure Active Directory シームレス シングル サインオン: クイック スタート](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a15e-130">See the [instructions to configure Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="7a15e-132">テスト ラボ ガイド: Azure AD シームレス シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="7a15e-132">Test Lab Guide: Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md) |
|||

<span data-ttu-id="7a15e-133">中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-sso)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="7a15e-133">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sso) for this section.</span></span>


<a name="identity-custom-sign-in"></a>
## <a name="customize-the-office-365-sign-in-page"></a><span data-ttu-id="7a15e-134">Office 365 サインイン ページをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="7a15e-134">Customize the Office 365 sign-in page</span></span>

<span data-ttu-id="7a15e-135">*この手順はオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="7a15e-135">*This is optional and for both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="7a15e-136">このセクションでは、ユーザーが組織のサインイン ページを認識できるように、企業名やロゴなどの認識できる要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="7a15e-136">In this section, you'll help users recognize your organization’s sign-in page by adding your company name, logo, and other recognizable elements.</span></span> 

<span data-ttu-id="7a15e-137">Microsoft 365 Enterprise では、サイン ページと [アクセス パネル] ページの外観をカスタマイズして、企業ロゴ、配色、カスタム ユーザー情報を組み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="7a15e-137">With Microsoft 365 Enterprise, you can customize the appearance of the sign-in and Access Panel pages so they include your company logo, color schemes, and custom user information.</span></span> 

<span data-ttu-id="7a15e-138">詳細については、「[会社のブランドを Office 365 サインイン ページに追加する](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a15e-138">For more information, see [Add your company branding to Office 365 Sign In page](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).</span></span>

<span data-ttu-id="7a15e-139">構成手順については、「[サインイン ページと [アクセス パネル ページ] に会社のブランドを追加する](http://aka.ms/aadpaddbranding)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a15e-139">For configuration instructions, see [Add company branding to your sign-in and Access Panel pages](http://aka.ms/aadpaddbranding).</span></span>

<span data-ttu-id="7a15e-140">中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-custom-sign-in)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="7a15e-140">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-custom-sign-in) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="7a15e-141">次の手順</span><span class="sxs-lookup"><span data-stu-id="7a15e-141">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="7a15e-142">ユーザーのサインインをセキュリティで保護して管理する</span><span class="sxs-lookup"><span data-stu-id="7a15e-142">Secure and manage your user sign-ins</span></span>](identity-secure-user-sign-ins.md) |
