---
title: Microsoft 365 テスト環境のパススルー認証に必要な ID およびデバイス アクセスの前提条件
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: パススルー認証用の前提条件で ID とデバイスのアクセスをテストするための Microsoft 365 環境を作成します。
ms.openlocfilehash: 71ba116ee45f031b156934e0924a0c3d460110d5
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233764"
---
# <a name="identity-and-device-access-prerequisites-for-pass-through-authentication-in-your-microsoft-365-test-environment"></a><span data-ttu-id="92885-103">Microsoft 365 テスト環境のパススルー認証に必要な ID およびデバイス アクセスの前提条件</span><span class="sxs-lookup"><span data-stu-id="92885-103">Identity and device access prerequisites for pass-through authentication in your Microsoft 365 test environment</span></span>

<span data-ttu-id="92885-104">*このテスト ラボ ガイドは、エンタープライズ テスト環境向け Microsoft 365 でのみ使用できます。*</span><span class="sxs-lookup"><span data-stu-id="92885-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="92885-105">[ID](../security/office-365-security/microsoft-365-policies-configurations.md) とデバイスのアクセス構成は、Azure Active Directory (Azure AD) と統合された Microsoft 365 enterprise のすべてのサービスへのアクセスを保護するための一連の構成と条件付きアクセス ポリシーです。</span><span class="sxs-lookup"><span data-stu-id="92885-105">[Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) are a set of configurations and conditional access policies to protect access to all services in Microsoft 365 for enterprise that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="92885-106">この記事では、ID とデバイス アクセス用の[パススルー認証の前提条件構成](../security/office-365-security/identity-access-prerequisites.md#prerequisites)に関する要件を満たす Microsoft 365 テスト環境を構成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="92885-106">This article describes how you can configure a Microsoft 365 test environment that meets the requirements of the [Pass-through authentication prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="92885-107">このテスト環境を設定するには、10 のフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="92885-107">There are ten phases to setting up this test environment:</span></span>

1. <span data-ttu-id="92885-108">パススルー認証を実装するシミュレーション エンタープライズ Microsoft 365 テスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="92885-108">Build out your simulated enterprise with pass-through authentication Microsoft 365 test environment</span></span>
2. <span data-ttu-id="92885-109">Azure AD シームレス シングル サインオンを構成する</span><span class="sxs-lookup"><span data-stu-id="92885-109">Configure Azure AD seamless single sign-on</span></span>
3. <span data-ttu-id="92885-110">名前付きの場所を構成する</span><span class="sxs-lookup"><span data-stu-id="92885-110">Configure named locations</span></span>
4. <span data-ttu-id="92885-111">パスワード ライトバックを構成する</span><span class="sxs-lookup"><span data-stu-id="92885-111">Configure password writeback</span></span>
5. <span data-ttu-id="92885-112">セルフサービスのパスワードのリセットを構成する</span><span class="sxs-lookup"><span data-stu-id="92885-112">Configure self-service password reset</span></span>
6. <span data-ttu-id="92885-113">多要素認証を構成する</span><span class="sxs-lookup"><span data-stu-id="92885-113">Configure multifactor authentication</span></span>
7. <span data-ttu-id="92885-114">ドメインに参加している Windows コンピューターのデバイスの自動登録を有効にする</span><span class="sxs-lookup"><span data-stu-id="92885-114">Enable automatic device registration of domain-joined Windows computers</span></span>
8. <span data-ttu-id="92885-115">Azure ADパスワード保護を構成する</span><span class="sxs-lookup"><span data-stu-id="92885-115">Configure Azure AD password protection</span></span> 
9. <span data-ttu-id="92885-116">Azure AD Identity Protection を有効化する</span><span class="sxs-lookup"><span data-stu-id="92885-116">Enable Azure AD Identity Protection</span></span>
10. <span data-ttu-id="92885-117">Exchange Online および Skype for Business Online に対して先進認証を有効化する</span><span class="sxs-lookup"><span data-stu-id="92885-117">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-simulated-enterprise-with-pass-through-authentication-microsoft-365-test-environment"></a><span data-ttu-id="92885-118">フェーズ 1: パススルー認証を実装するシミュレーション エンタープライズ Microsoft 365 テスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="92885-118">Phase 1: Build out your simulated enterprise with pass-through authentication Microsoft 365 test environment</span></span>

<span data-ttu-id="92885-119">「[パススルー認証](pass-through-auth-m365-ent-test-environment.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="92885-119">Follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>

<span data-ttu-id="92885-120">最終的な構成は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="92885-120">Here is the resulting configuration.</span></span>

![パススルー認証を実装するシミュレーション エンタープライズ テスト環境](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="92885-122">フェーズ 2: Azure AD シームレス シングル サインオンを構成する</span><span class="sxs-lookup"><span data-stu-id="92885-122">Phase 2: Configure Azure AD seamless single sign-on</span></span>

<span data-ttu-id="92885-123">[テスト ラボ ガイドの「Azure AD シームレス シングル サインオン」のフェーズ 2](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso) に説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="92885-123">Follow the instructions in [Phase 2 of the Azure AD Seamless Single Sign-on Test Lab Guide](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span></span>

## <a name="phase-3-configure-named-locations"></a><span data-ttu-id="92885-124">フェーズ 3: 名前付きの場所を構成する</span><span class="sxs-lookup"><span data-stu-id="92885-124">Phase 3: Configure named locations</span></span>

<span data-ttu-id="92885-125">最初に、組織で使用されているパブリック IP アドレスまたはアドレス範囲を確認します。</span><span class="sxs-lookup"><span data-stu-id="92885-125">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="92885-126">次に、「[Azure Active Directory で名前付きの場所を構成する](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations)」の手順に従って、アドレスまたはアドレス範囲を名前付きの場所として追加します。</span><span class="sxs-lookup"><span data-stu-id="92885-126">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-4-configure-password-writeback"></a><span data-ttu-id="92885-127">フェーズ 4: パスワード ライトバックを構成する</span><span class="sxs-lookup"><span data-stu-id="92885-127">Phase 4: Configure password writeback</span></span>

<span data-ttu-id="92885-128">[テスト ラボ ガイドの「パスワード ライトバック」のフェーズ 2](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) に説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="92885-128">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-5-configure-self-service-password-reset"></a><span data-ttu-id="92885-129">フェーズ 5: セルフサービスのパスワードのリセットを構成する</span><span class="sxs-lookup"><span data-stu-id="92885-129">Phase 5: Configure self-service password reset</span></span>

<span data-ttu-id="92885-130">次に、テスト ラボ ガイドの[「パスワードのリセット」のフェーズ 3](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset) に説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="92885-130">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="92885-131">特定の Azure AD グループに含まれるアカウントのパスワード リセットを有効にする場合は、それらのアカウントを **パスワードのリセット** グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="92885-131">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="92885-132">ユーザー 2</span><span class="sxs-lookup"><span data-stu-id="92885-132">User 2</span></span>
- <span data-ttu-id="92885-133">ユーザー 3</span><span class="sxs-lookup"><span data-stu-id="92885-133">User 3</span></span>
- <span data-ttu-id="92885-134">ユーザー 4</span><span class="sxs-lookup"><span data-stu-id="92885-134">User 4</span></span>
- <span data-ttu-id="92885-135">ユーザー 5</span><span class="sxs-lookup"><span data-stu-id="92885-135">User 5</span></span>

<span data-ttu-id="92885-136">User 2 アカウントのパスワードのリセットのみテストします。</span><span class="sxs-lookup"><span data-stu-id="92885-136">Test password reset only for the User 2 account.</span></span>

## <a name="phase-6-configure-multi-factor-authentication"></a><span data-ttu-id="92885-137">フェーズ 6: 多要素認証を構成する</span><span class="sxs-lookup"><span data-stu-id="92885-137">Phase 6: Configure multi-factor authentication</span></span>

<span data-ttu-id="92885-138">次のユーザー アカウントについて、[テスト ラボ ガイドの「多要素認証」のフェーズ 2](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) に説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="92885-138">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="92885-139">ユーザー 2</span><span class="sxs-lookup"><span data-stu-id="92885-139">User 2</span></span>
- <span data-ttu-id="92885-140">ユーザー 3</span><span class="sxs-lookup"><span data-stu-id="92885-140">User 3</span></span>
- <span data-ttu-id="92885-141">ユーザー 4</span><span class="sxs-lookup"><span data-stu-id="92885-141">User 4</span></span>
- <span data-ttu-id="92885-142">ユーザー 5</span><span class="sxs-lookup"><span data-stu-id="92885-142">User 5</span></span>

<span data-ttu-id="92885-143">User 2 アカウントの多要素認証のみテストします。</span><span class="sxs-lookup"><span data-stu-id="92885-143">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-7-enable-automatic-device-registration-of-domain-joined-windows-computers"></a><span data-ttu-id="92885-144">フェーズ 7: ドメインに参加している Windows コンピューターのデバイスの自動登録を有効にする</span><span class="sxs-lookup"><span data-stu-id="92885-144">Phase 7: Enable automatic device registration of domain-joined Windows computers</span></span> 

<span data-ttu-id="92885-145">ドメイン [に参加している](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan) Windows コンピューターのデバイスの自動登録を有効にするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="92885-145">Follow [these instructions](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan) to enable automatic device registration of domain-joined Windows computers.</span></span>

## <a name="phase-8-configure-azure-ad-password-protection"></a><span data-ttu-id="92885-146">フェーズ 8: Azure ADパスワード保護を構成する</span><span class="sxs-lookup"><span data-stu-id="92885-146">Phase 8: Configure Azure AD password protection</span></span> 

<span data-ttu-id="92885-147">既知 [の脆弱なパスワード](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) とそのバリアントをブロックするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="92885-147">Follow [these instructions](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) to block known weak passwords and their variants.</span></span>

## <a name="phase-9-enable-azure-ad-identity-protection"></a><span data-ttu-id="92885-148">フェーズ 9: Azure AD Identity Protection を有効にする</span><span class="sxs-lookup"><span data-stu-id="92885-148">Phase 9: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="92885-149">[テスト ラボ ガイドの「Azure AD Identity Protection」のフェーズ 2](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection) に説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="92885-149">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-10-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="92885-150">フェーズ 10: Exchange Online と Skype for Business Online のモダン認証を有効にする</span><span class="sxs-lookup"><span data-stu-id="92885-150">Phase 10: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="92885-151">Exchange Online については、[こちら](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later)で説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="92885-151">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="92885-152">Skype for Business Online については、</span><span class="sxs-lookup"><span data-stu-id="92885-152">For Skype for Business Online:</span></span>

1. <span data-ttu-id="92885-153">[Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) に接続します。</span><span class="sxs-lookup"><span data-stu-id="92885-153">Connect to [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="92885-154">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="92885-154">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="92885-155">次のコマンドを使用して、変更が成功したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="92885-155">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="92885-156">上述の手順により、ID とデバイス アクセス用の[パススルー認証の前提条件構成](../security/office-365-security/identity-access-prerequisites.md#prerequisites)に関する要件を満たすテスト環境が作成されます。</span><span class="sxs-lookup"><span data-stu-id="92885-156">The result is a test environment that meets the requirements of the [Pass-through authentication prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="92885-157">次の手順</span><span class="sxs-lookup"><span data-stu-id="92885-157">Next step</span></span>

<span data-ttu-id="92885-158">[共通 ID とデバイスのアクセス ポリシー](identity-access-policies.md)を使用して、前提条件に基づいて構築し ID とデバイスを保護するポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="92885-158">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="92885-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="92885-159">See also</span></span>

[<span data-ttu-id="92885-160">その他の ID のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="92885-160">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="92885-161">ID ロードマップ</span><span class="sxs-lookup"><span data-stu-id="92885-161">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="92885-162">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="92885-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="92885-163">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="92885-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="92885-164">Microsoft 365 for enterprise のドキュメント</span><span class="sxs-lookup"><span data-stu-id="92885-164">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

