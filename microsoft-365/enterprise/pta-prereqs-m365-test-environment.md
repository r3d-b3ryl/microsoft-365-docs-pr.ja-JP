---
title: Microsoft 365 テスト環境のパススルー認証に必要な ID およびデバイス アクセスの前提条件
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: パススルー認証用の前提条件で ID とデバイスのアクセスをテストするための Microsoft 365 環境を作成します。
ms.openlocfilehash: 7741b38a947e58d81192326c412760487d803e36
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399183"
---
# <a name="identity-and-device-access-prerequisites-for-pass-through-authentication-in-your-microsoft-365-test-environment"></a><span data-ttu-id="cf3fe-103">Microsoft 365 テスト環境のパススルー認証に必要な ID およびデバイス アクセスの前提条件</span><span class="sxs-lookup"><span data-stu-id="cf3fe-103">Identity and device access prerequisites for pass-through authentication in your Microsoft 365 test environment</span></span>

<span data-ttu-id="cf3fe-104">*このテストラボガイドは、エンタープライズテスト環境の Microsoft 365 にのみ使用できます。*</span><span class="sxs-lookup"><span data-stu-id="cf3fe-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="cf3fe-105">[Id およびデバイスアクセス構成](../security/office-365-security/microsoft-365-policies-configurations.md) とは、Azure Active Directory (azure AD) と統合された Microsoft 365 for enterprise のすべてのサービスへのアクセスを保護する一連の構成および条件付きアクセスポリシーです。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-105">[Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) are a set of configurations and conditional access policies to protect access to all services in Microsoft 365 for enterprise that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="cf3fe-106">この記事では、ID とデバイス アクセス用の[パススルー認証の前提条件構成](../security/office-365-security/identity-access-prerequisites.md#prerequisites)に関する要件を満たす Microsoft 365 テスト環境を構成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-106">This article describes how you can configure a Microsoft 365 test environment that meets the requirements of the [Pass-through authentication prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="cf3fe-107">このテスト環境は、次に示す 8 つのフェーズで設定します。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-107">There are eight phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="cf3fe-108">パススルー認証を実装するシミュレーション エンタープライズ Microsoft 365 テスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="cf3fe-108">Build out your simulated enterprise with pass-through authentication Microsoft 365 test environment</span></span>
2.  <span data-ttu-id="cf3fe-109">Azure AD シームレス シングル サインオンを構成する</span><span class="sxs-lookup"><span data-stu-id="cf3fe-109">Configure Azure AD seamless single sign-on</span></span>
3.  <span data-ttu-id="cf3fe-110">名前付きの場所を構成する</span><span class="sxs-lookup"><span data-stu-id="cf3fe-110">Configure named locations</span></span>
4.  <span data-ttu-id="cf3fe-111">パスワード ライトバックを構成する</span><span class="sxs-lookup"><span data-stu-id="cf3fe-111">Configure password writeback</span></span>
5.  <span data-ttu-id="cf3fe-112">セルフサービスのパスワードのリセットを構成する</span><span class="sxs-lookup"><span data-stu-id="cf3fe-112">Configure self-service password reset</span></span>
6.  <span data-ttu-id="cf3fe-113">多要素認証を構成する</span><span class="sxs-lookup"><span data-stu-id="cf3fe-113">Configure multifactor authentication</span></span>
7.  <span data-ttu-id="cf3fe-114">Azure AD Identity Protection を有効化する</span><span class="sxs-lookup"><span data-stu-id="cf3fe-114">Enable Azure AD Identity Protection</span></span>
8.  <span data-ttu-id="cf3fe-115">Exchange Online および Skype for Business Online に対して先進認証を有効化する</span><span class="sxs-lookup"><span data-stu-id="cf3fe-115">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-simulated-enterprise-with-pass-through-authentication-microsoft-365-test-environment"></a><span data-ttu-id="cf3fe-116">フェーズ 1: パススルー認証を実装するシミュレーション エンタープライズ Microsoft 365 テスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="cf3fe-116">Phase 1: Build out your simulated enterprise with pass-through authentication Microsoft 365 test environment</span></span>

<span data-ttu-id="cf3fe-117">「[パススルー認証](pass-through-auth-m365-ent-test-environment.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-117">Follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>

<span data-ttu-id="cf3fe-118">最終的な構成は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-118">Here is the resulting configuration.</span></span>

![パススルー認証を実装するシミュレーション エンタープライズ テスト環境](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="cf3fe-120">フェーズ 2: Azure AD シームレス シングル サインオンを構成する</span><span class="sxs-lookup"><span data-stu-id="cf3fe-120">Phase 2: Configure Azure AD seamless single sign-on</span></span>

<span data-ttu-id="cf3fe-121">[テスト ラボ ガイドの「Azure AD シームレス シングル サインオン」のフェーズ 2](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso) に説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-121">Follow the instructions in [Phase 2 of the Azure AD Seamless Single Sign-on Test Lab Guide](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span></span>

## <a name="phase-3-configure-named-locations"></a><span data-ttu-id="cf3fe-122">フェーズ 3: 名前付きの場所を構成する</span><span class="sxs-lookup"><span data-stu-id="cf3fe-122">Phase 3: Configure named locations</span></span>

<span data-ttu-id="cf3fe-123">最初に、組織で使用されているパブリック IP アドレスまたはアドレス範囲を確認します。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-123">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="cf3fe-124">次に、「[Azure Active Directory で名前付きの場所を構成する](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations)」の手順に従って、アドレスまたはアドレス範囲を名前付きの場所として追加します。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-124">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-4-configure-password-writeback"></a><span data-ttu-id="cf3fe-125">フェーズ 4: パスワード ライトバックを構成する</span><span class="sxs-lookup"><span data-stu-id="cf3fe-125">Phase 4: Configure password writeback</span></span>

<span data-ttu-id="cf3fe-126">[テスト ラボ ガイドの「パスワード ライトバック」のフェーズ 2](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) に説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-126">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-5-configure-self-service-password-reset"></a><span data-ttu-id="cf3fe-127">フェーズ 5: セルフサービスのパスワードのリセットを構成する</span><span class="sxs-lookup"><span data-stu-id="cf3fe-127">Phase 5: Configure self-service password reset</span></span>

<span data-ttu-id="cf3fe-128">次に、テスト ラボ ガイドの[「パスワードのリセット」のフェーズ 3](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset) に説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-128">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="cf3fe-129">特定の Azure AD グループに含まれるアカウントのパスワード リセットを有効にする場合は、それらのアカウントを**パスワードのリセット** グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-129">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="cf3fe-130">ユーザー 2</span><span class="sxs-lookup"><span data-stu-id="cf3fe-130">User 2</span></span>
- <span data-ttu-id="cf3fe-131">ユーザー 3</span><span class="sxs-lookup"><span data-stu-id="cf3fe-131">User 3</span></span>
- <span data-ttu-id="cf3fe-132">ユーザー 4</span><span class="sxs-lookup"><span data-stu-id="cf3fe-132">User 4</span></span>
- <span data-ttu-id="cf3fe-133">ユーザー 5</span><span class="sxs-lookup"><span data-stu-id="cf3fe-133">User 5</span></span>

<span data-ttu-id="cf3fe-134">User 2 アカウントのパスワードのリセットのみテストします。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-134">Test password reset only for the User 2 account.</span></span>

## <a name="phase-6-configure-multi-factor-authentication"></a><span data-ttu-id="cf3fe-135">フェーズ 6: 多要素認証を構成する</span><span class="sxs-lookup"><span data-stu-id="cf3fe-135">Phase 6: Configure multi-factor authentication</span></span>

<span data-ttu-id="cf3fe-136">次のユーザー アカウントについて、[テスト ラボ ガイドの「多要素認証」のフェーズ 2](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) に説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-136">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="cf3fe-137">ユーザー 2</span><span class="sxs-lookup"><span data-stu-id="cf3fe-137">User 2</span></span>
- <span data-ttu-id="cf3fe-138">ユーザー 3</span><span class="sxs-lookup"><span data-stu-id="cf3fe-138">User 3</span></span>
- <span data-ttu-id="cf3fe-139">ユーザー 4</span><span class="sxs-lookup"><span data-stu-id="cf3fe-139">User 4</span></span>
- <span data-ttu-id="cf3fe-140">ユーザー 5</span><span class="sxs-lookup"><span data-stu-id="cf3fe-140">User 5</span></span>

<span data-ttu-id="cf3fe-141">User 2 アカウントの多要素認証のみテストします。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-141">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-7-enable-azure-ad-identity-protection"></a><span data-ttu-id="cf3fe-142">フェーズ 7: Azure AD Identity Protection を有効化する</span><span class="sxs-lookup"><span data-stu-id="cf3fe-142">Phase 7: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="cf3fe-143">[テスト ラボ ガイドの「Azure AD Identity Protection」のフェーズ 2](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection) に説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-143">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="cf3fe-144">フェーズ 8: Exchange Online および Skype for Business Online に対して先進認証を有効化する</span><span class="sxs-lookup"><span data-stu-id="cf3fe-144">Phase 8: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="cf3fe-145">Exchange Online については、[こちら](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later)で説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-145">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="cf3fe-146">Skype for Business Online については、</span><span class="sxs-lookup"><span data-stu-id="cf3fe-146">For Skype for Business Online:</span></span>

1. <span data-ttu-id="cf3fe-147">[Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) に接続します。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-147">Connect to [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="cf3fe-148">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-148">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="cf3fe-149">次のコマンドを使用して、変更が成功したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-149">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="cf3fe-150">上述の手順により、ID とデバイス アクセス用の[パススルー認証の前提条件構成](../security/office-365-security/identity-access-prerequisites.md#prerequisites)に関する要件を満たすテスト環境が作成されます。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-150">The result is a test environment that meets the requirements of the [Pass-through authentication prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="cf3fe-151">次の手順</span><span class="sxs-lookup"><span data-stu-id="cf3fe-151">Next step</span></span>

<span data-ttu-id="cf3fe-152">[共通 ID とデバイスのアクセス ポリシー](identity-access-policies.md)を使用して、前提条件に基づいて構築し ID とデバイスを保護するポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-152">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf3fe-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf3fe-153">See also</span></span>

[<span data-ttu-id="cf3fe-154">その他の ID のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="cf3fe-154">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="cf3fe-155">Identity ロードマップ</span><span class="sxs-lookup"><span data-stu-id="cf3fe-155">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="cf3fe-156">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="cf3fe-156">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="cf3fe-157">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="cf3fe-157">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="cf3fe-158">エンタープライズドキュメントの Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cf3fe-158">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

