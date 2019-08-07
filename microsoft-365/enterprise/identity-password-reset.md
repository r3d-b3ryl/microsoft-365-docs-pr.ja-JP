---
title: '手順 5: ユーザーのアクセスを簡素化する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Azure AD のセルフサービスによるパスワードのリセット (SSPR) について理解し、構成します。
ms.openlocfilehash: b57291aabf1b51e7866dba10ba50eacc27291a2a
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073727"
---
# <a name="step-5-simplify-access-for-users"></a><span data-ttu-id="6ddd8-103">手順 5: ユーザーのアクセスを簡素化する</span><span class="sxs-lookup"><span data-stu-id="6ddd8-103">Step 5: Simplify access for users</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)


<a name="identity-pw-writeback"></a>
## <a name="simplify-password-updates"></a><span data-ttu-id="6ddd8-104">パスワードの更新を簡素化する</span><span class="sxs-lookup"><span data-stu-id="6ddd8-104">Simplify password updates</span></span>

<span data-ttu-id="6ddd8-105">*この手順はハイブリッド環境でオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="6ddd8-105">*This is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="6ddd8-106">このセクションでは、ユーザーに Azure Active directory (Azure AD) を通じてパスワードを再設定することを許可します。この再設定はローカル Active Directory Domain Services (AD DS) に複製されます。</span><span class="sxs-lookup"><span data-stu-id="6ddd8-106">In this section, you'll allow users to reset their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="6ddd8-107">このプロセスは、パスワードの書き戻しと呼びます。</span><span class="sxs-lookup"><span data-stu-id="6ddd8-107">This process is known as password writeback.</span></span> <span data-ttu-id="6ddd8-108">ユーザーはパスワードの書き戻しを使用すれば、ユーザー アカウントとその属性が保存されているオンプレミス AD DS を通じてパスワードの更新を行う必要がありません。</span><span class="sxs-lookup"><span data-stu-id="6ddd8-108">With password writeback, users don’t need to update their passwords through the on-premises Active Directory Domain Services (AD DS) where user accounts and their attributes are stored.</span></span> <span data-ttu-id="6ddd8-109">これは、オンプレミスのネットワークへのリモート アクセス接続を持たないローミング ユーザーやリモート ユーザーにとって価値があります。</span><span class="sxs-lookup"><span data-stu-id="6ddd8-109">This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="6ddd8-110">パスワードの書き戻しは、Identity Protection 機能 (アカウント侵害が発生する可能性が高い危険が検出された場合にオンプレミス パスワードの変更をユーザーに義務付けるなど) を最大限に活用するために必要です。</span><span class="sxs-lookup"><span data-stu-id="6ddd8-110">Password writeback is required to fully utilize Identity Protection feature capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="6ddd8-111">その他の情報と構成手順については、「[Azure AD SSPR とパスワード書き戻し](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ddd8-111">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="6ddd8-p102">最適なエクスペリエンスとリリースされた新機能を利用できるようにするため、Azure AD Connect の最新バージョンにアップグレードします。詳細については、「[Azure AD Connect のカスタム インストール](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ddd8-p102">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released. For more information, see [Custom installation of Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="6ddd8-115">テスト ラボ ガイド: パスワードの書き戻し</span><span class="sxs-lookup"><span data-stu-id="6ddd8-115">Test Lab Guide: Password writeback</span></span>](password-writeback-m365-ent-test-environment.md) |
|||

<span data-ttu-id="6ddd8-116">中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-pw-writeback)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="6ddd8-116">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-writeback) for this section.</span></span>

<a name="identity-pw-reset"></a>
## <a name="simplify-password-resets"></a><span data-ttu-id="6ddd8-117">パスワード再設定を簡素化する</span><span class="sxs-lookup"><span data-stu-id="6ddd8-117">Simplify password resets</span></span>

<span data-ttu-id="6ddd8-118">*この手順はオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="6ddd8-118">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="6ddd8-119">このセクションでは、セルフサービスによるパスワードのリセット (SSPR) を有効にして、ユーザーが自分のパスワードやアカウントの再設定やロック解除を行えるようにします。</span><span class="sxs-lookup"><span data-stu-id="6ddd8-119">In this section, you'll enable self-service password reset (SSPR) to allow users to reset or unlock their passwords or accounts.</span></span> <span data-ttu-id="6ddd8-120">誤用または悪用について警告するため、通知と共に、ユーザーがいつシステムにアクセスしたかを追跡する詳細なレポート作成機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6ddd8-120">To alert you to misuse or abuse, you can use the detailed reporting that tracks when users access the system, along with notifications.</span></span> <span data-ttu-id="6ddd8-121">パスワード再設定をデプロイする前にパスワードの書き戻しを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ddd8-121">You must enable password writeback before you can deploy password resets.</span></span>

<span data-ttu-id="6ddd8-122">「[セルフサービスによるパスワードのリセットを適切にロールアウトする方法](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ddd8-122">See the [instructions to roll out password reset](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span></span>

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="6ddd8-124">テスト ラボ ガイド: パスワードのリセット</span><span class="sxs-lookup"><span data-stu-id="6ddd8-124">Test Lab Guide: Password reset</span></span>](password-reset-m365-ent-test-environment.md) |
|||

<span data-ttu-id="6ddd8-125">中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-pw-reset)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="6ddd8-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-reset) for this section.</span></span>


<a name="identity-sso"></a>
## <a name="simplify-user-sign-in"></a><span data-ttu-id="6ddd8-126">ユーザー サインインを簡素化する</span><span class="sxs-lookup"><span data-stu-id="6ddd8-126">Simplify user sign-in</span></span>

<span data-ttu-id="6ddd8-127">*この手順はハイブリッド環境でオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="6ddd8-127">*This is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="6ddd8-128">このセクションでは、Azure Active Directory シームレス シングル サインオンをセットアップして、ユーザーがパスワードを (さらに、多くの場合ユーザー名も) 入力せずに Azure AD ユーザー アカウントを使用するサービスにサインインできるようにします。</span><span class="sxs-lookup"><span data-stu-id="6ddd8-128">In this section, you'll set up Azure Active Directory Seamless Single Sign-On (Azure AD Seamless SSO) to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames.</span></span> <span data-ttu-id="6ddd8-129">これにより、ユーザーは Office 365 などのクラウド ベースのアプリケーションに簡単にアクセスできるようになります。ID フェデレーション サーバーのような追加のオンプレミス コンポーネントは不要です。</span><span class="sxs-lookup"><span data-stu-id="6ddd8-129">This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="6ddd8-130">Azure AD Connect ツールを使用して Azure AD シームレス SSO を構成します。</span><span class="sxs-lookup"><span data-stu-id="6ddd8-130">You'll configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span>

<span data-ttu-id="6ddd8-131">「[Azure Active Directory シームレス シングル サインオン: クイック スタート](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ddd8-131">See the [instructions to configure Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="6ddd8-133">テスト ラボ ガイド: Azure AD シームレス シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="6ddd8-133">Test Lab Guide: Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md) |
|||

<span data-ttu-id="6ddd8-134">中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-sso)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="6ddd8-134">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sso) for this section.</span></span>


<a name="identity-custom-sign-in"></a>
## <a name="customize-the-office-365-sign-in-page"></a><span data-ttu-id="6ddd8-135">Office 365 サインイン ページをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="6ddd8-135">Customize the Office 365 sign-in page</span></span>

<span data-ttu-id="6ddd8-136">*この手順はオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="6ddd8-136">*This is optional and for both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="6ddd8-137">このセクションでは、ユーザーが組織のサインイン ページを認識できるように、企業名やロゴなどの認識できる要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="6ddd8-137">In this section, you'll help users recognize your organization’s sign-in page by adding your company name, logo, and other recognizable elements.</span></span> 

<span data-ttu-id="6ddd8-138">Microsoft 365 Enterprise では、サイン ページと [アクセス パネル] ページの外観をカスタマイズして、企業ロゴ、配色、カスタム ユーザー情報を組み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="6ddd8-138">With Microsoft 365 Enterprise, you can customize the appearance of the sign-in and Access Panel pages so they include your company logo, color schemes, and custom user information.</span></span> 

<span data-ttu-id="6ddd8-139">*カスタマイズ前*は、ユーザーがデバイスからサインインしようとすると、次の例に示すような Office 365 サインイン ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6ddd8-139">When a user attempts to sign in from a device, they see something like the following example on the Office 365 sign-in page *before customization*.</span></span>

![カスタマイズ前の Office 365 サインイン ページの例](./media/identity-customize-office-365-sign-in/id-step01-sign-in-before.png)

<span data-ttu-id="6ddd8-141">次に、Contoso Corporation の同じユーザーに対して*カスタマイズ後*に表示されるページを示します。</span><span class="sxs-lookup"><span data-stu-id="6ddd8-141">And here is what the same user of the Contoso Corporation would see *after customization*.</span></span>

![カスタマイズ後の Office 365 サインイン ページの例](./media/identity-customize-office-365-sign-in/id-step01-sign-in-after.png)

<span data-ttu-id="6ddd8-143">詳細については、「[会社のブランドを Office 365 サインイン ページに追加する](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ddd8-143">For more information, see [Add your company branding to Office 365 Sign In page](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).</span></span>

<span data-ttu-id="6ddd8-144">構成手順については、「[サインイン ページと [アクセス パネル ページ] に会社のブランドを追加する](http://aka.ms/aadpaddbranding)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ddd8-144">For configuration instructions, see [Add company branding to your sign-in and Access Panel pages](http://aka.ms/aadpaddbranding).</span></span>

<span data-ttu-id="6ddd8-145">中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-custom-sign-in)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="6ddd8-145">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-custom-sign-in) for this section.</span></span>


## <a name="next-step"></a><span data-ttu-id="6ddd8-146">次の手順</span><span class="sxs-lookup"><span data-stu-id="6ddd8-146">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="6ddd8-147">管理を容易にするためのグループの使用</span><span class="sxs-lookup"><span data-stu-id="6ddd8-147">Use groups for easier management</span></span>](identity-self-service-group-management.md) |


