---
title: Microsoft 365 テスト環境のクラウド専用の ID およびデバイス アクセスの前提条件
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
description: クラウド専用の認証用の前提条件で ID とデバイスのアクセスをテストするための Microsoft 365 環境を作成します。
ms.openlocfilehash: a8025a2543a53a229be13d19c246165fe88ad433
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685786"
---
# <a name="identity-and-device-access-prerequisites-for-cloud-only-in-your-microsoft-365-test-environment"></a><span data-ttu-id="c21a5-103">Microsoft 365 テスト環境のクラウド専用の ID およびデバイス アクセスの前提条件</span><span class="sxs-lookup"><span data-stu-id="c21a5-103">Identity and device access prerequisites for cloud only in your Microsoft 365 test environment</span></span>

<span data-ttu-id="c21a5-104">*このテストラボガイドは、エンタープライズテスト環境の Microsoft 365 にのみ使用できます。*</span><span class="sxs-lookup"><span data-stu-id="c21a5-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="c21a5-105">[Id およびデバイスアクセス構成](microsoft-365-policies-configurations.md) は、Azure Active Directory (azure AD) と統合されたすべてのサービスへのアクセスを保護するための一連の構成および条件付きアクセスポリシーです。</span><span class="sxs-lookup"><span data-stu-id="c21a5-105">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="c21a5-106">この記事では、ID とデバイス アクセス用の[クラウド専用の前提条件構成](identity-access-prerequisites.md#prerequisites)に関する要件を満たす Microsoft 365 テスト環境を構成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="c21a5-106">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [cloud only prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="c21a5-107">このテスト環境は、次に示す 7 つのフェーズで設定します。</span><span class="sxs-lookup"><span data-stu-id="c21a5-107">There are seven phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="c21a5-108">軽量なテスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="c21a5-108">Build out your lightweight test environment</span></span>
2.  <span data-ttu-id="c21a5-109">名前付きの場所を構成する</span><span class="sxs-lookup"><span data-stu-id="c21a5-109">Configure named locations</span></span>
3.  <span data-ttu-id="c21a5-110">パスワード ライトバックを構成する</span><span class="sxs-lookup"><span data-stu-id="c21a5-110">Configure password writeback</span></span>
4.  <span data-ttu-id="c21a5-111">セルフサービスのパスワードのリセットを構成する</span><span class="sxs-lookup"><span data-stu-id="c21a5-111">Configure self-service password resets</span></span>
5.  <span data-ttu-id="c21a5-112">多要素認証を構成する</span><span class="sxs-lookup"><span data-stu-id="c21a5-112">Configure multifactor authentication</span></span>
6.  <span data-ttu-id="c21a5-113">Azure AD Identity Protection を有効化する</span><span class="sxs-lookup"><span data-stu-id="c21a5-113">Enable Azure AD Identity Protection</span></span>
7.  <span data-ttu-id="c21a5-114">Exchange Online および Skype for Business Online に対して先進認証を有効化する</span><span class="sxs-lookup"><span data-stu-id="c21a5-114">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-lightweight-microsoft-365-test-environment"></a><span data-ttu-id="c21a5-115">フェーズ 1: 軽量な Microsoft 365 テスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="c21a5-115">Phase 1: Build out your lightweight Microsoft 365 test environment</span></span>

<span data-ttu-id="c21a5-116">「[軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」に説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="c21a5-116">Follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
<span data-ttu-id="c21a5-117">最終的な構成は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="c21a5-117">Here is the resulting configuration.</span></span>

![軽量な Microsoft 365 Enterprise テスト環境](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
 

## <a name="phase-2-configure-named-locations"></a><span data-ttu-id="c21a5-119">フェーズ 2: 名前付きの場所を構成する</span><span class="sxs-lookup"><span data-stu-id="c21a5-119">Phase 2: Configure named locations</span></span>

<span data-ttu-id="c21a5-120">最初に、組織で使用されているパブリック IP アドレスまたはアドレス範囲を確認します。</span><span class="sxs-lookup"><span data-stu-id="c21a5-120">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="c21a5-121">次に、「[Azure Active Directory で名前付きの場所を構成する](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations)」の手順に従って、アドレスまたはアドレス範囲を名前付きの場所として追加します。</span><span class="sxs-lookup"><span data-stu-id="c21a5-121">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-3-configure-password-writeback"></a><span data-ttu-id="c21a5-122">フェーズ 3: パスワード ライトバックを構成する</span><span class="sxs-lookup"><span data-stu-id="c21a5-122">Phase 3: Configure password writeback</span></span>

<span data-ttu-id="c21a5-123">[テスト ラボ ガイドの「パスワード ライトバック」のフェーズ 2](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) に説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="c21a5-123">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-4-configure-self-service-password-reset"></a><span data-ttu-id="c21a5-124">フェーズ 4: セルフサービスのパスワードのリセットを構成する</span><span class="sxs-lookup"><span data-stu-id="c21a5-124">Phase 4: Configure self-service password reset</span></span>

<span data-ttu-id="c21a5-125">次に、テスト ラボ ガイドの[「パスワードのリセット」のフェーズ 3](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset) に説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="c21a5-125">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="c21a5-126">特定の Azure AD グループに含まれるアカウントのパスワード リセットを有効にする場合は、それらのアカウントを**パスワードのリセット** グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="c21a5-126">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="c21a5-127">ユーザー 2</span><span class="sxs-lookup"><span data-stu-id="c21a5-127">User 2</span></span>
- <span data-ttu-id="c21a5-128">ユーザー 3</span><span class="sxs-lookup"><span data-stu-id="c21a5-128">User 3</span></span>
- <span data-ttu-id="c21a5-129">ユーザー 4</span><span class="sxs-lookup"><span data-stu-id="c21a5-129">User 4</span></span>
- <span data-ttu-id="c21a5-130">ユーザー 5</span><span class="sxs-lookup"><span data-stu-id="c21a5-130">User 5</span></span>

<span data-ttu-id="c21a5-131">User 2 アカウントのパスワードのリセットのみテストします。</span><span class="sxs-lookup"><span data-stu-id="c21a5-131">Test password reset only for the User 2 account.</span></span>

## <a name="phase-5-configure-multi-factor-authentication"></a><span data-ttu-id="c21a5-132">フェーズ 5: 多要素認証を構成する</span><span class="sxs-lookup"><span data-stu-id="c21a5-132">Phase 5: Configure multi-factor authentication</span></span>

<span data-ttu-id="c21a5-133">次のユーザー アカウントについて、[テスト ラボ ガイドの「多要素認証」のフェーズ 2](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) に説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="c21a5-133">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="c21a5-134">ユーザー 2</span><span class="sxs-lookup"><span data-stu-id="c21a5-134">User 2</span></span>
- <span data-ttu-id="c21a5-135">ユーザー 3</span><span class="sxs-lookup"><span data-stu-id="c21a5-135">User 3</span></span>
- <span data-ttu-id="c21a5-136">ユーザー 4</span><span class="sxs-lookup"><span data-stu-id="c21a5-136">User 4</span></span>
- <span data-ttu-id="c21a5-137">ユーザー 5</span><span class="sxs-lookup"><span data-stu-id="c21a5-137">User 5</span></span>

<span data-ttu-id="c21a5-138">User 2 アカウントの多要素認証のみテストします。</span><span class="sxs-lookup"><span data-stu-id="c21a5-138">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-6-enable-azure-ad-identity-protection"></a><span data-ttu-id="c21a5-139">フェーズ 6: Azure AD Identity Protection を有効化する</span><span class="sxs-lookup"><span data-stu-id="c21a5-139">Phase 6: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="c21a5-140">[テスト ラボ ガイドの「Azure AD Identity Protection」のフェーズ 2](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection) に説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="c21a5-140">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-7-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="c21a5-141">フェーズ 7: Exchange Online および Skype for Business Online に対して先進認証を有効化する</span><span class="sxs-lookup"><span data-stu-id="c21a5-141">Phase 7: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="c21a5-142">Exchange Online については、[こちら](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later)で説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="c21a5-142">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="c21a5-143">Skype for Business Online については、</span><span class="sxs-lookup"><span data-stu-id="c21a5-143">For Skype for Business Online:</span></span>

1. <span data-ttu-id="c21a5-144">[Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) に接続します。</span><span class="sxs-lookup"><span data-stu-id="c21a5-144">Connect to [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="c21a5-145">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c21a5-145">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="c21a5-146">次のコマンドを使用して、変更が成功したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="c21a5-146">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="c21a5-147">上述の手順により、ID とデバイス アクセス用の[クラウド専用の前提条件構成](identity-access-prerequisites.md#prerequisites)に関する要件を満たすテスト環境が作成されます。</span><span class="sxs-lookup"><span data-stu-id="c21a5-147">The result is a test environment that meets the requirements of the [cloud only prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="c21a5-148">次の手順</span><span class="sxs-lookup"><span data-stu-id="c21a5-148">Next step</span></span>

<span data-ttu-id="c21a5-149">[共通 ID とデバイスのアクセス ポリシー](identity-access-policies.md)を使用して、前提条件に基づいて構築し ID とデバイスを保護するポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="c21a5-149">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="c21a5-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="c21a5-150">See also</span></span>

[<span data-ttu-id="c21a5-151">その他の ID のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="c21a5-151">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="c21a5-152">Identity ロードマップ</span><span class="sxs-lookup"><span data-stu-id="c21a5-152">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="c21a5-153">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="c21a5-153">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="c21a5-154">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="c21a5-154">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="c21a5-155">エンタープライズドキュメントの Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c21a5-155">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
