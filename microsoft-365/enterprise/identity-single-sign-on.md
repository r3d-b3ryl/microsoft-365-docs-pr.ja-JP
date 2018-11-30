---
title: '手順 10: ユーザー サインインを簡素化する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Azure AD シームレス シングル サインオン (シームレス SSO) について理解し、構成します。
ms.openlocfilehash: 9d18cb559d3a4a9ee401e0f94fb53bc6360d88c8
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869542"
---
# <a name="step-10-simplify-user-sign-in"></a><span data-ttu-id="95f5c-103">手順 10: ユーザー サインインを簡素化する</span><span class="sxs-lookup"><span data-stu-id="95f5c-103">Step 10: Simplify user sign-in</span></span>

<span data-ttu-id="95f5c-104">*この手順はハイブリッド環境でオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="95f5c-104">*This step is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="95f5c-p101">この手順では、Azure Active Directory シームレス シングル サインオン (Azure AD シームレス SSO) を設定し、Azure AD ユーザー アカウントを使用するサービスにユーザーがパスワードを入力せずに (また多くの場合、ユーザー名を入力せずに) サインインできるようにします。これにより、ID フェデレーション サーバーなどのオンプレミス コンポーネントを追加せずに、ユーザーが Office 365 などのクラウドベース アプリケーションに簡単にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="95f5c-p101">In Step 8, you'll set up Azure Active Directory Seamless Single Sign-On (Azure AD Seamless SSO) to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames. This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="95f5c-107">Azure AD Connect ツールを使用して Azure AD シームレス SSO を構成します。</span><span class="sxs-lookup"><span data-stu-id="95f5c-107">You'll configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span>

<span data-ttu-id="95f5c-108">「[Azure Active Directory シームレス シングル サインオン: クイック スタート](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95f5c-108">See the [instructions to configure Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="95f5c-110">テスト ラボ ガイド: Azure AD シームレス シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="95f5c-110">Test Lab Guide: Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md) |
|||

<span data-ttu-id="95f5c-111">中間チェックポイントとして、この手順の[終了条件](identity-exit-criteria.md#crit-identity-sso)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="95f5c-111">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sso) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="95f5c-112">次の手順</span><span class="sxs-lookup"><span data-stu-id="95f5c-112">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step11.png)| [<span data-ttu-id="95f5c-113">Office 365 サインイン ページをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="95f5c-113">Customize the Office 365 sign-in page</span></span>](identity-customize-office-365-sign-in.md) |

