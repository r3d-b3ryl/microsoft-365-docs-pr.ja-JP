---
title: Microsoft 365 テスト環境のパスワード ハッシュ同期に必要な ID およびデバイス アクセスの前提条件
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 04/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: パスワード ハッシュ同期の認証用の前提条件で ID とデバイスのアクセスをテストするための Microsoft 365 環境を作成します。
ms.openlocfilehash: 274f73b1cd6a925b972ab14417c9d854c48c2f00
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074157"
---
# <a name="identity-and-device-access-prerequisites-for-password-hash-synchronization-in-your-microsoft-365-test-environment"></a><span data-ttu-id="a1c8e-103">Microsoft 365 テスト環境のパスワード ハッシュ同期に必要な ID およびデバイス アクセスの前提条件</span><span class="sxs-lookup"><span data-stu-id="a1c8e-103">Identity and device access prerequisites for password hash synchronization in your Microsoft 365 test environment</span></span>

<span data-ttu-id="a1c8e-104">[ID とデバイスのアクセス構成](microsoft-365-policies-configurations.md)は、構成と条件付きアクセス ポリシーのセットで、Office 365 および Microsoft 365 Enterprise の Enterprise Mobility + Security (EMS) などを含めた、Azure Active Directory (Azure AD) と統合されているすべてのサービスへのアクセスを保護します。</span><span class="sxs-lookup"><span data-stu-id="a1c8e-104">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="a1c8e-105">この記事では、ID とデバイス アクセス用の[パスワード ハッシュ同期付き Active Directory の前提条件構成](identity-access-prerequisites.md#prerequisites)に関する要件を満たす Microsoft 365 テスト環境を構成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="a1c8e-105">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [Active Directory with password hash sync prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="a1c8e-106">このテスト環境は、次に示す 8 つのフェーズで設定します。</span><span class="sxs-lookup"><span data-stu-id="a1c8e-106">There are two phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="a1c8e-107">パスワード ハッシュ同期テスト環境でシミュレートされたエンタープライズを作成する</span><span class="sxs-lookup"><span data-stu-id="a1c8e-107">Create a simulated enterprise with password hash sync test environment</span></span>
2.  <span data-ttu-id="a1c8e-108">Azure AD シームレス シングル サインオンを構成する</span><span class="sxs-lookup"><span data-stu-id="a1c8e-108">Configure Azure AD single sign-on</span></span>
3.  <span data-ttu-id="a1c8e-109">名前付きの場所を構成する</span><span class="sxs-lookup"><span data-stu-id="a1c8e-109">Configure named locations</span></span>
4.  <span data-ttu-id="a1c8e-110">パスワードの書き戻しを構成する</span><span class="sxs-lookup"><span data-stu-id="a1c8e-110">Configure password writeback</span></span>
5.  <span data-ttu-id="a1c8e-111">すべてのユーザー アカウントのセルフ サービスによるパスワードのリセットを構成する</span><span class="sxs-lookup"><span data-stu-id="a1c8e-111">Configure self-service password reset for all user accounts</span></span>
6.  <span data-ttu-id="a1c8e-112">すべてのユーザー アカウントに対する多要素認証を構成する</span><span class="sxs-lookup"><span data-stu-id="a1c8e-112">Configure multifactor authentication for all user accounts</span></span>
7.  <span data-ttu-id="a1c8e-113">Azure AD Identity Protection を有効化する</span><span class="sxs-lookup"><span data-stu-id="a1c8e-113">Azure AD Identity Protection</span></span>
8.  <span data-ttu-id="a1c8e-114">Exchange Online および Skype for Business Online に対して先進認証を有効化する</span><span class="sxs-lookup"><span data-stu-id="a1c8e-114">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-simulated-enterprise-with-password-hash-sync-microsoft-365-test-environment"></a><span data-ttu-id="a1c8e-115">フェーズ 1: パスワード ハッシュ同期 Microsoft 365 テスト環境でシミュレートされたエンタープライズを構築する</span><span class="sxs-lookup"><span data-stu-id="a1c8e-115">Phase 1: Build out your simulated enterprise with password hash sync Microsoft 365 test environment</span></span>

<span data-ttu-id="a1c8e-116">[パスワード ハッシュ同期](password-hash-sync-m365-ent-test-environment.md)の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a1c8e-116">Follow the instructions in [Password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span>
<span data-ttu-id="a1c8e-117">最終的な構成は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="a1c8e-117">Here is the resulting configuration.</span></span>

![パスワード ハッシュ同期テスト環境があるシミュレートされたエンタープライズ](media/password-hash-sync-m365-ent-test-environment/Phase3.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="a1c8e-119">フェーズ 2: Azure AD シームレス シングル サインオンを構成する</span><span class="sxs-lookup"><span data-stu-id="a1c8e-119">Phase 2: Configure Azure AD seamless single sign-on</span></span>

<span data-ttu-id="a1c8e-120">[テスト ラボ ガイドの「Azure AD シームレス シングル サインオン」のフェーズ 2](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso) に説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a1c8e-120">Follow the instructions in [Phase 2 of the Azure AD Seamless Single Sign-on Test Lab Guide](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span></span>

## <a name="phase-3-configure-named-locations"></a><span data-ttu-id="a1c8e-121">フェーズ 3: 名前付きの場所を構成する</span><span class="sxs-lookup"><span data-stu-id="a1c8e-121">Phase 3: Configure named locations</span></span>

<span data-ttu-id="a1c8e-122">最初に、組織で使用されているパブリック IP アドレスまたはアドレス範囲を確認します。</span><span class="sxs-lookup"><span data-stu-id="a1c8e-122">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="a1c8e-123">次に、「[Azure Active Directory で名前付きの場所を構成する](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations)」の手順に従って、アドレスまたはアドレス範囲を名前付きの場所として追加します。</span><span class="sxs-lookup"><span data-stu-id="a1c8e-123">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-4-configure-password-writeback"></a><span data-ttu-id="a1c8e-124">フェーズ 4: パスワード ライトバックを構成する</span><span class="sxs-lookup"><span data-stu-id="a1c8e-124">Phase 4: Configure password writeback</span></span>

<span data-ttu-id="a1c8e-125">[テスト ラボ ガイドの「パスワード ライトバック」のフェーズ 2](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) に説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a1c8e-125">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-5-configure-self-service-password-reset"></a><span data-ttu-id="a1c8e-126">フェーズ 5: セルフサービスのパスワードのリセットを構成する</span><span class="sxs-lookup"><span data-stu-id="a1c8e-126">Phase 5: Configure self-service password reset</span></span>

<span data-ttu-id="a1c8e-127">次に、テスト ラボ ガイドの[「パスワードのリセット」のフェーズ 3](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset) に説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a1c8e-127">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="a1c8e-128">特定の Azure AD グループに含まれるアカウントのパスワード リセットを有効にする場合は、それらのアカウントを**パスワードのリセット** グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="a1c8e-128">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="a1c8e-129">ユーザー 2</span><span class="sxs-lookup"><span data-stu-id="a1c8e-129">User: %2</span></span>
- <span data-ttu-id="a1c8e-130">ユーザー 3</span><span class="sxs-lookup"><span data-stu-id="a1c8e-130">User Defined 3</span></span>
- <span data-ttu-id="a1c8e-131">ユーザー 4</span><span class="sxs-lookup"><span data-stu-id="a1c8e-131">User: %4</span></span>
- <span data-ttu-id="a1c8e-132">ユーザー 5</span><span class="sxs-lookup"><span data-stu-id="a1c8e-132">User 5</span></span>

<span data-ttu-id="a1c8e-133">User 2 アカウントのパスワードのリセットのみテストします。</span><span class="sxs-lookup"><span data-stu-id="a1c8e-133">Next, you test password reset for the User 2 account.</span></span>

## <a name="phase-6-configure-multi-factor-authentication"></a><span data-ttu-id="a1c8e-134">フェーズ 6: 多要素認証を構成する</span><span class="sxs-lookup"><span data-stu-id="a1c8e-134">Phase 6: Configure multi-factor authentication</span></span>

<span data-ttu-id="a1c8e-135">次のユーザー アカウントについて、[テスト ラボ ガイドの「多要素認証」のフェーズ 2](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) に説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a1c8e-135">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="a1c8e-136">ユーザー 2</span><span class="sxs-lookup"><span data-stu-id="a1c8e-136">User: %2</span></span>
- <span data-ttu-id="a1c8e-137">ユーザー 3</span><span class="sxs-lookup"><span data-stu-id="a1c8e-137">User Defined 3</span></span>
- <span data-ttu-id="a1c8e-138">ユーザー 4</span><span class="sxs-lookup"><span data-stu-id="a1c8e-138">User: %4</span></span>
- <span data-ttu-id="a1c8e-139">ユーザー 5</span><span class="sxs-lookup"><span data-stu-id="a1c8e-139">User 5</span></span>

<span data-ttu-id="a1c8e-140">User 2 アカウントの多要素認証のみテストします。</span><span class="sxs-lookup"><span data-stu-id="a1c8e-140">Enable and test multi-factor authentication for the User 2 account.</span></span>

## <a name="phase-7-enable-azure-ad-identity-protection"></a><span data-ttu-id="a1c8e-141">フェーズ 7: Azure AD Identity Protection を有効化する</span><span class="sxs-lookup"><span data-stu-id="a1c8e-141">Phase 7: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="a1c8e-142">[テスト ラボ ガイドの「Azure AD Identity Protection」のフェーズ 2](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-enable-and-use-azure-ad-identity-protection) に説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a1c8e-142">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-enable-and-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="a1c8e-143">フェーズ 8: Exchange Online および Skype for Business Online に対して先進認証を有効化する</span><span class="sxs-lookup"><span data-stu-id="a1c8e-143">Phase 8: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="a1c8e-144">Exchange Online については、[こちら](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later)で説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a1c8e-144">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="a1c8e-145">Skype for Business Online については、</span><span class="sxs-lookup"><span data-stu-id="a1c8e-145">Skype for Business Online</span></span>

1. <span data-ttu-id="a1c8e-146">[Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) に接続します。</span><span class="sxs-lookup"><span data-stu-id="a1c8e-146">[](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)Step 5: Connect to Skype for Business Online</span></span>

2. <span data-ttu-id="a1c8e-147">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a1c8e-147">Run this command.</span></span>

  ```
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="a1c8e-148">このコマンドを使用して、変更が成功したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a1c8e-148">Ensure that the download was successful with this command.</span></span>

  ```
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="a1c8e-149">上述の手順により、ID とデバイス アクセス用の[パスワード ハッシュ同期付き Active Directory の前提条件構成](identity-access-prerequisites.md#prerequisites)に関する要件を満たすテスト環境が作成されます。</span><span class="sxs-lookup"><span data-stu-id="a1c8e-149">The result is a test environment that meets the requirements of the [Active Directory with password hash sync prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="a1c8e-150">次の手順</span><span class="sxs-lookup"><span data-stu-id="a1c8e-150">Next step</span></span>

<span data-ttu-id="a1c8e-151">[共通 ID とデバイスのアクセス ポリシー](identity-access-policies.md)を使用して、前提条件に基づいて構築し ID とデバイスを保護するポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="a1c8e-151">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and test protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="a1c8e-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1c8e-152">See also</span></span>

[<span data-ttu-id="a1c8e-153">その他の ID のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="a1c8e-153">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="a1c8e-154">フェーズ 2: ID</span><span class="sxs-lookup"><span data-stu-id="a1c8e-154">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="a1c8e-155">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="a1c8e-155">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="a1c8e-156">Microsoft 365 Enterprise を展開する</span><span class="sxs-lookup"><span data-stu-id="a1c8e-156">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="a1c8e-157">Microsoft 365 Enterprise のドキュメントとリソース</span><span class="sxs-lookup"><span data-stu-id="a1c8e-157">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
