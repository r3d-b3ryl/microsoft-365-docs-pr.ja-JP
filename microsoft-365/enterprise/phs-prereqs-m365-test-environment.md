---
title: Microsoft 365 テスト環境のパスワード ハッシュ同期に必要な ID およびデバイス アクセスの前提条件
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
description: パスワード ハッシュ同期の認証用の前提条件で ID とデバイスのアクセスをテストするための Microsoft 365 環境を作成します。
ms.openlocfilehash: a3b02167bc3c1d2e7bc809d227ce5537114ffff9
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199443"
---
# <a name="identity-and-device-access-prerequisites-for-password-hash-synchronization-in-your-microsoft-365-test-environment"></a><span data-ttu-id="fa719-103">Microsoft 365 テスト環境のパスワード ハッシュ同期に必要な ID およびデバイス アクセスの前提条件</span><span class="sxs-lookup"><span data-stu-id="fa719-103">Identity and device access prerequisites for password hash synchronization in your Microsoft 365 test environment</span></span>

<span data-ttu-id="fa719-104">*このテスト ラボ ガイドは、エンタープライズ テスト環境の Microsoft 365 でのみ使用できます。*</span><span class="sxs-lookup"><span data-stu-id="fa719-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="fa719-105">[ID およびデバイス](../security/office-365-security/microsoft-365-policies-configurations.md) アクセス構成は、Azure Active Directory (Azure Active Directory )と統合されたエンタープライズ向け Microsoft 365 のすべてのサービスへのアクセスを保護するための一連の構成と条件付きアクセス ポリシーです。AD。</span><span class="sxs-lookup"><span data-stu-id="fa719-105">[Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) are a set of configurations and conditional access policies to protect access to all services in Microsoft 365 for enterprise that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="fa719-106">この記事では、ID およびデバイス アクセス用のパスワード ハッシュ同期認証前提条件構成を使用して、[](../security/office-365-security/identity-access-prerequisites.md#prerequisites)ハイブリッドの要件を満たす Microsoft 365 テスト環境を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fa719-106">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [hybrid with password hash sync authentication prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="fa719-107">このテスト環境をセットアップするには、10 のフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="fa719-107">There are ten phases to setting up this test environment:</span></span>

1. <span data-ttu-id="fa719-108">パスワード ハッシュ同期テスト環境でシミュレートされたエンタープライズを作成する</span><span class="sxs-lookup"><span data-stu-id="fa719-108">Create a simulated enterprise with password hash sync test environment</span></span>
2. <span data-ttu-id="fa719-109">Azure AD シームレス シングル サインオンを構成する</span><span class="sxs-lookup"><span data-stu-id="fa719-109">Configure Azure AD seamless single sign-on</span></span>
3. <span data-ttu-id="fa719-110">名前付きの場所を構成する</span><span class="sxs-lookup"><span data-stu-id="fa719-110">Configure named locations</span></span>
4. <span data-ttu-id="fa719-111">パスワードの書き戻しを構成する</span><span class="sxs-lookup"><span data-stu-id="fa719-111">Configure password writeback</span></span>
5. <span data-ttu-id="fa719-112">すべてのユーザー アカウントのセルフ サービスによるパスワードのリセットを構成する</span><span class="sxs-lookup"><span data-stu-id="fa719-112">Configure self-service password reset for all user accounts</span></span>
6. <span data-ttu-id="fa719-113">すべてのユーザー アカウントに対する多要素認証を構成する</span><span class="sxs-lookup"><span data-stu-id="fa719-113">Configure multifactor authentication for all user accounts</span></span>
7. <span data-ttu-id="fa719-114">ドメインに参加している Windows コンピューターのデバイスの自動登録を有効にする</span><span class="sxs-lookup"><span data-stu-id="fa719-114">Enable automatic device registration of domain-joined Windows computers</span></span>
8. <span data-ttu-id="fa719-115">Azure ADパスワード保護を構成する</span><span class="sxs-lookup"><span data-stu-id="fa719-115">Configure Azure AD password protection</span></span> 
9. <span data-ttu-id="fa719-116">Azure AD Identity Protection を有効化する</span><span class="sxs-lookup"><span data-stu-id="fa719-116">Enable Azure AD Identity Protection</span></span>
10. <span data-ttu-id="fa719-117">Exchange Online および Skype for Business Online に対して先進認証を有効化する</span><span class="sxs-lookup"><span data-stu-id="fa719-117">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-simulated-enterprise-with-password-hash-sync-microsoft-365-test-environment"></a><span data-ttu-id="fa719-118">フェーズ 1: パスワード ハッシュ同期 Microsoft 365 テスト環境でシミュレートされたエンタープライズを構築する</span><span class="sxs-lookup"><span data-stu-id="fa719-118">Phase 1: Build out your simulated enterprise with password hash sync Microsoft 365 test environment</span></span>

<span data-ttu-id="fa719-119">パスワード ハッシュ同期テスト ラボ ガイド [の手順](password-hash-sync-m365-ent-test-environment.md) に従います。</span><span class="sxs-lookup"><span data-stu-id="fa719-119">Follow the instructions in [the password hash synchronization](password-hash-sync-m365-ent-test-environment.md) Test Lab Guide.</span></span>
<span data-ttu-id="fa719-120">最終的な構成は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="fa719-120">Here is the resulting configuration.</span></span>

![パスワード ハッシュ同期テスト環境があるシミュレートされたエンタープライズ](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="fa719-122">フェーズ 2: Azure AD シームレス シングル サインオンを構成する</span><span class="sxs-lookup"><span data-stu-id="fa719-122">Phase 2: Configure Azure AD seamless single sign-on</span></span>

<span data-ttu-id="fa719-123">[テスト ラボ ガイドの「Azure AD シームレス シングル サインオン」のフェーズ 2](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso) に説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="fa719-123">Follow the instructions in [Phase 2 of the Azure AD Seamless Single Sign-on Test Lab Guide](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span></span>

## <a name="phase-3-configure-named-locations"></a><span data-ttu-id="fa719-124">フェーズ 3: 名前付きの場所を構成する</span><span class="sxs-lookup"><span data-stu-id="fa719-124">Phase 3: Configure named locations</span></span>

<span data-ttu-id="fa719-125">最初に、組織で使用されているパブリック IP アドレスまたはアドレス範囲を確認します。</span><span class="sxs-lookup"><span data-stu-id="fa719-125">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="fa719-126">次に、「[Azure Active Directory で名前付きの場所を構成する](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations)」の手順に従って、アドレスまたはアドレス範囲を名前付きの場所として追加します。</span><span class="sxs-lookup"><span data-stu-id="fa719-126">Next, follow the instructions in [Configure named locations in Azure Active Directory](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-4-configure-password-writeback"></a><span data-ttu-id="fa719-127">フェーズ 4: パスワード ライトバックを構成する</span><span class="sxs-lookup"><span data-stu-id="fa719-127">Phase 4: Configure password writeback</span></span>

<span data-ttu-id="fa719-128">[テスト ラボ ガイドの「パスワード ライトバック」のフェーズ 2](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) に説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="fa719-128">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-5-configure-self-service-password-reset"></a><span data-ttu-id="fa719-129">フェーズ 5: セルフサービスのパスワードのリセットを構成する</span><span class="sxs-lookup"><span data-stu-id="fa719-129">Phase 5: Configure self-service password reset</span></span>

<span data-ttu-id="fa719-130">次に、テスト ラボ ガイドの[「パスワードのリセット」のフェーズ 3](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset) に説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="fa719-130">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="fa719-131">特定の Azure AD グループに含まれるアカウントのパスワード リセットを有効にする場合は、それらのアカウントを **パスワードのリセット** グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="fa719-131">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="fa719-132">ユーザー 2</span><span class="sxs-lookup"><span data-stu-id="fa719-132">User 2</span></span>
- <span data-ttu-id="fa719-133">ユーザー 3</span><span class="sxs-lookup"><span data-stu-id="fa719-133">User 3</span></span>
- <span data-ttu-id="fa719-134">ユーザー 4</span><span class="sxs-lookup"><span data-stu-id="fa719-134">User 4</span></span>
- <span data-ttu-id="fa719-135">ユーザー 5</span><span class="sxs-lookup"><span data-stu-id="fa719-135">User 5</span></span>

<span data-ttu-id="fa719-136">User 2 アカウントのパスワードのリセットのみテストします。</span><span class="sxs-lookup"><span data-stu-id="fa719-136">Test password reset only for the User 2 account.</span></span>

## <a name="phase-6-configure-multi-factor-authentication"></a><span data-ttu-id="fa719-137">フェーズ 6: 多要素認証を構成する</span><span class="sxs-lookup"><span data-stu-id="fa719-137">Phase 6: Configure multi-factor authentication</span></span>

<span data-ttu-id="fa719-138">次のユーザー アカウントについて、[テスト ラボ ガイドの「多要素認証」のフェーズ 2](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) に説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="fa719-138">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="fa719-139">ユーザー 2</span><span class="sxs-lookup"><span data-stu-id="fa719-139">User 2</span></span>
- <span data-ttu-id="fa719-140">ユーザー 3</span><span class="sxs-lookup"><span data-stu-id="fa719-140">User 3</span></span>
- <span data-ttu-id="fa719-141">ユーザー 4</span><span class="sxs-lookup"><span data-stu-id="fa719-141">User 4</span></span>
- <span data-ttu-id="fa719-142">ユーザー 5</span><span class="sxs-lookup"><span data-stu-id="fa719-142">User 5</span></span>

<span data-ttu-id="fa719-143">User 2 アカウントの多要素認証のみテストします。</span><span class="sxs-lookup"><span data-stu-id="fa719-143">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-7-enable-automatic-device-registration-of-domain-joined-windows-computers"></a><span data-ttu-id="fa719-144">フェーズ 7: ドメインに参加している Windows コンピューターのデバイスの自動登録を有効にする</span><span class="sxs-lookup"><span data-stu-id="fa719-144">Phase 7: Enable automatic device registration of domain-joined Windows computers</span></span> 

<span data-ttu-id="fa719-145">ドメイン [に参加している Windows コンピューター](/azure/active-directory/devices/hybrid-azuread-join-plan) のデバイスの自動登録を有効にするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="fa719-145">Follow [these instructions](/azure/active-directory/devices/hybrid-azuread-join-plan) to enable automatic device registration of domain-joined Windows computers.</span></span>

## <a name="phase-8-configure-azure-ad-password-protection"></a><span data-ttu-id="fa719-146">フェーズ 8: Azure のパスワード保護AD構成する</span><span class="sxs-lookup"><span data-stu-id="fa719-146">Phase 8: Configure Azure AD password protection</span></span> 

<span data-ttu-id="fa719-147">既知 [の脆弱なパスワードとその](/azure/active-directory/authentication/concept-password-ban-bad) バリアントをブロックするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="fa719-147">Follow [these instructions](/azure/active-directory/authentication/concept-password-ban-bad) to block known weak passwords and their variants.</span></span>

## <a name="phase-9-enable-azure-ad-identity-protection"></a><span data-ttu-id="fa719-148">フェーズ 9: Azure AD ID 保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="fa719-148">Phase 9: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="fa719-149">[テスト ラボ ガイドの「Azure AD Identity Protection」のフェーズ 2](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection) に説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="fa719-149">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-10-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="fa719-150">フェーズ 10: Exchange Online と Skype for Business Online のモダン認証を有効にする</span><span class="sxs-lookup"><span data-stu-id="fa719-150">Phase 10: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="fa719-151">Exchange Online については、[こちら](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later)で説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="fa719-151">For Exchange Online, follow [these instructions](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="fa719-152">Skype for Business Online については、</span><span class="sxs-lookup"><span data-stu-id="fa719-152">For Skype for Business Online:</span></span>

1. <span data-ttu-id="fa719-153">[Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) に接続します。</span><span class="sxs-lookup"><span data-stu-id="fa719-153">Connect to [Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="fa719-154">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fa719-154">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="fa719-155">このコマンドを使用して、変更が成功したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="fa719-155">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="fa719-156">上述の手順により、ID とデバイス アクセス用の[パスワード ハッシュ同期付き Active Directory の前提条件構成](../security/office-365-security/identity-access-prerequisites.md#prerequisites)に関する要件を満たすテスト環境が作成されます。</span><span class="sxs-lookup"><span data-stu-id="fa719-156">The result is a test environment that meets the requirements of the [Active Directory with password hash sync prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="fa719-157">次の手順</span><span class="sxs-lookup"><span data-stu-id="fa719-157">Next step</span></span>

<span data-ttu-id="fa719-158">[共通 ID とデバイスのアクセス ポリシー](../security/office-365-security/identity-access-policies.md)を使用して、前提条件に基づいて構築し ID とデバイスを保護するポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="fa719-158">Use [Common identity and device access policies](../security/office-365-security/identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="fa719-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa719-159">See also</span></span>

[<span data-ttu-id="fa719-160">その他の ID のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="fa719-160">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="fa719-161">ID ロードマップ</span><span class="sxs-lookup"><span data-stu-id="fa719-161">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="fa719-162">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="fa719-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="fa719-163">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="fa719-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="fa719-164">Microsoft 365 for enterprise のドキュメント</span><span class="sxs-lookup"><span data-stu-id="fa719-164">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)
