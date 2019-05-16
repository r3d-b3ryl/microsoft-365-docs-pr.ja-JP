---
title: Microsoft 365 テスト環境のクラウド専用の ID およびデバイス アクセスの前提条件
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
description: クラウド専用の認証用の前提条件で ID とデバイスのアクセスをテストするための Microsoft 365 環境を作成します。
ms.openlocfilehash: 9721d2972990998ca345f1d48d96494096f9190e
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072567"
---
# <a name="identity-and-device-access-prerequisites-for-cloud-only-in-your-microsoft-365-test-environment"></a><span data-ttu-id="5ee21-103">Microsoft 365 テスト環境のクラウド専用の ID およびデバイス アクセスの前提条件</span><span class="sxs-lookup"><span data-stu-id="5ee21-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="5ee21-104">[ID とデバイスのアクセス構成](microsoft-365-policies-configurations.md)は、構成と条件付きアクセス ポリシーのセットで、Office 365 および Microsoft 365 Enterprise の Enterprise Mobility + Security (EMS) などを含めた、Azure Active Directory (Azure AD) と統合されているすべてのサービスへのアクセスを保護します。</span><span class="sxs-lookup"><span data-stu-id="5ee21-104">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="5ee21-105">この記事では、ID とデバイス アクセス用の[クラウド専用の前提条件構成](identity-access-prerequisites.md#prerequisites)に関する要件を満たす Microsoft 365 テスト環境を構成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="5ee21-105">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [cloud only prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="5ee21-106">このテスト環境は、次に示す 7 つのフェーズで設定します。</span><span class="sxs-lookup"><span data-stu-id="5ee21-106">There are two phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="5ee21-107">軽量なテスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="5ee21-107">Build out your lightweight test environment</span></span>
2.  <span data-ttu-id="5ee21-108">名前付きの場所を構成する</span><span class="sxs-lookup"><span data-stu-id="5ee21-108">Configure named locations</span></span>
3.  <span data-ttu-id="5ee21-109">パスワード ライトバックを構成する</span><span class="sxs-lookup"><span data-stu-id="5ee21-109">Configure password writeback</span></span>
4.  <span data-ttu-id="5ee21-110">セルフサービスのパスワードのリセットを構成する</span><span class="sxs-lookup"><span data-stu-id="5ee21-110">Configure self-service password resets</span></span>
5.  <span data-ttu-id="5ee21-111">多要素認証を構成する</span><span class="sxs-lookup"><span data-stu-id="5ee21-111">Configure multifactor authentication</span></span>
6.  <span data-ttu-id="5ee21-112">Azure AD Identity Protection を有効化する</span><span class="sxs-lookup"><span data-stu-id="5ee21-112">Azure AD Identity Protection</span></span>
7.  <span data-ttu-id="5ee21-113">Exchange Online および Skype for Business Online に対して先進認証を有効化する</span><span class="sxs-lookup"><span data-stu-id="5ee21-113">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-lightweight-microsoft-365-test-environment"></a><span data-ttu-id="5ee21-114">フェーズ 1: 軽量な Microsoft 365 テスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="5ee21-114">Phase 1: Build out your lightweight or simulated enterprise Office 365 dev/test environment</span></span>

<span data-ttu-id="5ee21-115">「[軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」に説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5ee21-115">Follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
<span data-ttu-id="5ee21-116">最終的な構成は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5ee21-116">Here is the resulting configuration.</span></span>

![軽量な Microsoft 365 Enterprise テスト環境](media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
 

## <a name="phase-2-configure-named-locations"></a><span data-ttu-id="5ee21-118">フェーズ 2: 名前付きの場所を構成する</span><span class="sxs-lookup"><span data-stu-id="5ee21-118">Phase 2: Configure named locations</span></span>

<span data-ttu-id="5ee21-119">最初に、組織で使用されているパブリック IP アドレスまたはアドレス範囲を確認します。</span><span class="sxs-lookup"><span data-stu-id="5ee21-119">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="5ee21-120">次に、「[Azure Active Directory で名前付きの場所を構成する](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations)」の手順に従って、アドレスまたはアドレス範囲を名前付きの場所として追加します。</span><span class="sxs-lookup"><span data-stu-id="5ee21-120">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-3-configure-password-writeback"></a><span data-ttu-id="5ee21-121">フェーズ 3: パスワード ライトバックを構成する</span><span class="sxs-lookup"><span data-stu-id="5ee21-121">Phase 3: Configure password writeback</span></span>

<span data-ttu-id="5ee21-122">[テスト ラボ ガイドの「パスワード ライトバック」のフェーズ 2](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) に説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5ee21-122">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-4-configure-self-service-password-reset"></a><span data-ttu-id="5ee21-123">フェーズ 4: セルフサービスのパスワードのリセットを構成する</span><span class="sxs-lookup"><span data-stu-id="5ee21-123">Phase 4: Configure self-service password reset</span></span>

<span data-ttu-id="5ee21-124">次に、テスト ラボ ガイドの[「パスワードのリセット」のフェーズ 3](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset) に説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5ee21-124">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="5ee21-125">特定の Azure AD グループに含まれるアカウントのパスワード リセットを有効にする場合は、それらのアカウントを**パスワードのリセット** グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="5ee21-125">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="5ee21-126">ユーザー 2</span><span class="sxs-lookup"><span data-stu-id="5ee21-126">User: %2</span></span>
- <span data-ttu-id="5ee21-127">ユーザー 3</span><span class="sxs-lookup"><span data-stu-id="5ee21-127">User Defined 3</span></span>
- <span data-ttu-id="5ee21-128">ユーザー 4</span><span class="sxs-lookup"><span data-stu-id="5ee21-128">User: %4</span></span>
- <span data-ttu-id="5ee21-129">ユーザー 5</span><span class="sxs-lookup"><span data-stu-id="5ee21-129">User 5</span></span>

<span data-ttu-id="5ee21-130">User 2 アカウントのパスワードのリセットのみテストします。</span><span class="sxs-lookup"><span data-stu-id="5ee21-130">Next, you test password reset for the User 2 account.</span></span>

## <a name="phase-5-configure-multi-factor-authentication"></a><span data-ttu-id="5ee21-131">フェーズ 5: 多要素認証を構成する</span><span class="sxs-lookup"><span data-stu-id="5ee21-131">Phase 5: Configure multi-factor authentication</span></span>

<span data-ttu-id="5ee21-132">次のユーザー アカウントについて、[テスト ラボ ガイドの「多要素認証」のフェーズ 2](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) に説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5ee21-132">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="5ee21-133">ユーザー 2</span><span class="sxs-lookup"><span data-stu-id="5ee21-133">User: %2</span></span>
- <span data-ttu-id="5ee21-134">ユーザー 3</span><span class="sxs-lookup"><span data-stu-id="5ee21-134">User Defined 3</span></span>
- <span data-ttu-id="5ee21-135">ユーザー 4</span><span class="sxs-lookup"><span data-stu-id="5ee21-135">User: %4</span></span>
- <span data-ttu-id="5ee21-136">ユーザー 5</span><span class="sxs-lookup"><span data-stu-id="5ee21-136">User 5</span></span>

<span data-ttu-id="5ee21-137">User 2 アカウントの多要素認証のみテストします。</span><span class="sxs-lookup"><span data-stu-id="5ee21-137">Enable and test multi-factor authentication for the User 2 account.</span></span>

## <a name="phase-6-enable-azure-ad-identity-protection"></a><span data-ttu-id="5ee21-138">フェーズ 6: Azure AD Identity Protection を有効化する</span><span class="sxs-lookup"><span data-stu-id="5ee21-138">Phase 6: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="5ee21-139">[テスト ラボ ガイドの「Azure AD Identity Protection」のフェーズ 2](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-enable-and-use-azure-ad-identity-protection) に説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5ee21-139">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-enable-and-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-7-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="5ee21-140">フェーズ 7: Exchange Online および Skype for Business Online に対して先進認証を有効化する</span><span class="sxs-lookup"><span data-stu-id="5ee21-140">Phase 7: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="5ee21-141">Exchange Online については、[こちら](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later)で説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5ee21-141">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="5ee21-142">Skype for Business Online については、</span><span class="sxs-lookup"><span data-stu-id="5ee21-142">Skype for Business Online</span></span>

1. <span data-ttu-id="5ee21-143">[Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) に接続します。</span><span class="sxs-lookup"><span data-stu-id="5ee21-143">[](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)Step 5: Connect to Skype for Business Online</span></span>

2. <span data-ttu-id="5ee21-144">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5ee21-144">Run this command.</span></span>

  ```
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="5ee21-145">次のコマンドを使用して、変更が成功したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="5ee21-145">Ensure that the download was successful with this command.</span></span>

  ```
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="5ee21-146">上述の手順により、ID とデバイス アクセス用の[クラウド専用の前提条件構成](identity-access-prerequisites.md#prerequisites)に関する要件を満たすテスト環境が作成されます。</span><span class="sxs-lookup"><span data-stu-id="5ee21-146">The result is a test environment that meets the requirements of the [cloud only prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="5ee21-147">次の手順</span><span class="sxs-lookup"><span data-stu-id="5ee21-147">Next step</span></span>

<span data-ttu-id="5ee21-148">[共通 ID とデバイスのアクセス ポリシー](identity-access-policies.md)を使用して、前提条件に基づいて構築し ID とデバイスを保護するポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="5ee21-148">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and test protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="5ee21-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="5ee21-149">See also</span></span>

[<span data-ttu-id="5ee21-150">その他の ID のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="5ee21-150">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="5ee21-151">フェーズ 2: ID</span><span class="sxs-lookup"><span data-stu-id="5ee21-151">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="5ee21-152">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="5ee21-152">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="5ee21-153">Microsoft 365 Enterprise を展開する</span><span class="sxs-lookup"><span data-stu-id="5ee21-153">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="5ee21-154">Microsoft 365 Enterprise のドキュメントとリソース</span><span class="sxs-lookup"><span data-stu-id="5ee21-154">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
