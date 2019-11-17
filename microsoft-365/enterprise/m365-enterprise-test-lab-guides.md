---
title: Microsoft 365 Enterprise のテスト ラボ ガイド
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/04/2019
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: 以下のテスト ラボ ガイドを使用して、Microsoft 365 Enterprise のデモ、概念実証、開発/テスト環境を設定します。
ms.openlocfilehash: 2f6fd8c17096c9c25a0f1af886894e68d33e939d
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2019
ms.locfileid: "38672573"
---
# <a name="microsoft-365-enterprise-test-lab-guides"></a><span data-ttu-id="cce08-103">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="cce08-103">Microsoft 365 Enterprise Test Lab Guides</span></span>

<span data-ttu-id="cce08-104">*これは、Microsoft 365 Enterprise と Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="cce08-104">*This applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="cce08-p101">テスト ラボ ガイド (TLG) を活用すれば、Microsoft 製品の概要をいち早く把握することができます。テスト ラボ ガイドは、簡単ではあるものの代表的なテスト環境を構成する方法を説明しています。これらの環境は、試用期間または有料サブスクリプションの期間内に、デモ、カスタマイズ、概念の複合的な証拠の作成に使用できます。</span><span class="sxs-lookup"><span data-stu-id="cce08-p101">Test Lab Guides (TLGs) help you quickly learn about Microsoft products. They provide prescriptive instructions to configure simplified but representative test environments. You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription.</span></span> 

<span data-ttu-id="cce08-p102">TLG はモジュラーとして機能するように設計されています。TLG は、テストしてみたい内容やそのテストに必要な要件にできるだけ一致するように、複数の構成を行える仕組みになっています。この実地体験型ガイドにより、新しい製品やシナリオの展開要件を理解し、運用環境でホストする計画を立てやすくなります。</span><span class="sxs-lookup"><span data-stu-id="cce08-p102">TLGs are designed to be modular. They build upon each other to create multiple configurations that more closely match your learning or test configuration needs. The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario so you can better plan for hosting it in production.</span></span>

<span data-ttu-id="cce08-111">また、TLG を使用すると、アプリケーションの開発およびテスト用の典型的な環境を作成することもできます。これは、開発/テスト環境とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="cce08-111">You can also use TLGs to create representative environments for development and testing of applications, also known as dev/test environments.</span></span>
  
![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

<span data-ttu-id="cce08-113">[ここ](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="cce08-113">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

<span data-ttu-id="cce08-114">[![The Microsoft 365 Enterprise のテスト ラボ ガイド スタック](./media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="cce08-114">[![The Microsoft 365 Enterprise Test Lab Guide stack](./media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)</span></span>

## <a name="base-configuration"></a><span data-ttu-id="cce08-115">基本構成</span><span class="sxs-lookup"><span data-stu-id="cce08-115">Base configuration</span></span>

<span data-ttu-id="cce08-p103">最初に、Office 365 E5、Enterprise Mobility + Security (EMS) E5、Windows 10 Enterprise を含む [Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) のテスト環境を作成します。基本構成は 2 種類作成できます:</span><span class="sxs-lookup"><span data-stu-id="cce08-p103">First, you create a test environment for [Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) that includes Office 365 E5, Enterprise Mobility + Security (EMS) E5, and Windows 10 Enterprise. You can create two different types of base configurations:</span></span>

- <span data-ttu-id="cce08-118">オンプレミスのコンポーネントを含まないクラウド専用の環境で、Microsoft 365 Enterprise の機能を構成しデモンストレーションする場合は、[軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="cce08-118">Use the [lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 Enterprise features and capabilities in a cloud-only environment, which does not include any on-premises components.</span></span>

- <span data-ttu-id="cce08-119">Active Directory Domain Services (AD DS) ドメインなどのオンプレミスのコンポーネントを使用するハイブリッド クラウド環境で、Microsoft 365 Enterprise の機能を構成しデモンストレーションする場合は、[シミュレートされたエンタープライズ基本構成](simulated-ent-base-configuration-microsoft-365-enterprise.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="cce08-119">Use the [simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 Enterprise features and capabilities in a hybrid cloud environment, which uses on-premises components such as an Active Directory Domain Services (AD DS) domain.</span></span>

<span data-ttu-id="cce08-120">試用版または運用テスト環境に Microsoft 365 E5 ライセンスを追加することなく、Office 365 E5 のテスト環境を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="cce08-120">You can also create test environments for Office 365 E5 by not adding the Microsoft 365 E5 license to your trial or production test environment.</span></span>
    
## <a name="identity"></a><span data-ttu-id="cce08-121">ID</span><span class="sxs-lookup"><span data-stu-id="cce08-121">Identity</span></span>

<span data-ttu-id="cce08-122">ID に関連する機能や能力のデモンストレーションは、以下を参照してください:</span><span class="sxs-lookup"><span data-stu-id="cce08-122">To demonstrate identity-related features and capabilities, see:</span></span>

- [<span data-ttu-id="cce08-123">パスワード ハッシュ同期</span><span class="sxs-lookup"><span data-stu-id="cce08-123">Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)
  
   <span data-ttu-id="cce08-124">AD DS ドメイン コントローラーからのパスワード ハッシュによるディレクトリ同期を有効にしてテストします。</span><span class="sxs-lookup"><span data-stu-id="cce08-124">Enable and test password hash-based directory synchronization from an AD DS domain controller.</span></span>

- [<span data-ttu-id="cce08-125">パススルー認証</span><span class="sxs-lookup"><span data-stu-id="cce08-125">Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md)
  
   <span data-ttu-id="cce08-126">AD DS ドメイン コントローラーへのパススルー認証を有効にしてテストします。</span><span class="sxs-lookup"><span data-stu-id="cce08-126">Enable and test pass-through authentication to an AD DS domain controller.</span></span>

- [<span data-ttu-id="cce08-127">Azure AD シームレス シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="cce08-127">Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md)
  
   <span data-ttu-id="cce08-128">Azure AD シームレス シングル サインオン (SSO) を AD DS ドメイン コントローラーで有効にしてテストします。</span><span class="sxs-lookup"><span data-stu-id="cce08-128">Enable and test Azure AD Seamless Single Sign-on (SSO) with an AD DS domain controller.</span></span>

- [<span data-ttu-id="cce08-129">多要素認証</span><span class="sxs-lookup"><span data-stu-id="cce08-129">Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md)
  
   <span data-ttu-id="cce08-130">特定のユーザー アカウントで、スマートフォンによる多要素認証を有効にしてテストします。</span><span class="sxs-lookup"><span data-stu-id="cce08-130">Enable and test smart phone-based multi-factor authentication for a specific user account.</span></span>

- [<span data-ttu-id="cce08-131">全体管理者アカウントを保護する</span><span class="sxs-lookup"><span data-stu-id="cce08-131">Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md)
 
   <span data-ttu-id="cce08-132">条件付きアクセス ポリシーを使用してグローバル管理者アカウントをロックする。</span><span class="sxs-lookup"><span data-stu-id="cce08-132">Lock down your global administrator accounts with conditional access policies.</span></span>

- [<span data-ttu-id="cce08-133">パスワード ライトバック</span><span class="sxs-lookup"><span data-stu-id="cce08-133">Password writeback</span></span>](password-writeback-m365-ent-test-environment.md)

   <span data-ttu-id="cce08-134">パスワードの書き戻しは、Azure AD から AD DS ユーザー アカウントのパスワードを変更する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="cce08-134">Use password writeback to change the password on your AD DS user account from Azure AD.</span></span>

- [<span data-ttu-id="cce08-135">パスワードのリセット</span><span class="sxs-lookup"><span data-stu-id="cce08-135">Password reset</span></span>](password-reset-m365-ent-test-environment.md)

   <span data-ttu-id="cce08-136">セルフサービスによるパスワードのリセット (SSPR) を使用して、パスワードをリセットします。</span><span class="sxs-lookup"><span data-stu-id="cce08-136">Use self-service password reset (SSPR) to reset your password.</span></span>

- [<span data-ttu-id="cce08-137">ライセンスとグループ メンバーシップの自動管理</span><span class="sxs-lookup"><span data-stu-id="cce08-137">Automatic licensing and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md)

   <span data-ttu-id="cce08-138">自動ライセンス認証と動的なグループ メンバーシップを使用すると、新しいアカウントの管理をこれまでよりも簡単に行えます。</span><span class="sxs-lookup"><span data-stu-id="cce08-138">Make administering new accounts easier than ever with automatic licensing and dynamic group membership.</span></span>

- [<span data-ttu-id="cce08-139">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="cce08-139">Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md)

   <span data-ttu-id="cce08-140">現在のユーザー アカウントの脆弱性を確認します。</span><span class="sxs-lookup"><span data-stu-id="cce08-140">Scan your current user accounts for vulnerabilities.</span></span>

- [<span data-ttu-id="cce08-141">ID と デバイス アクセス</span><span class="sxs-lookup"><span data-stu-id="cce08-141">Identity and device access</span></span>](identity-device-access-m365-test-environment.md)

   <span data-ttu-id="cce08-142">お勧めする ID、デバイス アクセスの構成、および条件付きアクセス ポリシーをテストするための環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="cce08-142">Create an environment to test recommended identity and device access configurations and conditional access policies.</span></span>


## <a name="mobile-device-management"></a><span data-ttu-id="cce08-143">モバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="cce08-143">Mobile device management</span></span>

<span data-ttu-id="cce08-144">モバイル デバイス管理に関連する機能や能力のデモンストレーションは、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cce08-144">To demonstrate mobile device management-related features and capabilities, see:</span></span>

- [<span data-ttu-id="cce08-145">デバイス コンプライアンス ポリシー</span><span class="sxs-lookup"><span data-stu-id="cce08-145">Device compliance policies</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="cce08-146">Windows 10 デバイスのユーザー グループおよびデバイス コンプライアンス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="cce08-146">Create a user group and a device compliance policy for Windows 10 devices.</span></span>
    
- [<span data-ttu-id="cce08-147">iOS および Android デバイスの登録</span><span class="sxs-lookup"><span data-stu-id="cce08-147">Enroll iOS and Android devices</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   <span data-ttu-id="cce08-148">iOS または Android デバイスを登録し、それらをリモートで管理します。</span><span class="sxs-lookup"><span data-stu-id="cce08-148">Enroll iOS or Android devices and manage them remotely.</span></span>


## <a name="information-protection"></a><span data-ttu-id="cce08-149">情報保護</span><span class="sxs-lookup"><span data-stu-id="cce08-149">Information protection</span></span>

<span data-ttu-id="cce08-150">情報保護に関連する機能や能力のデモンストレーションは、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cce08-150">To demonstrate information protection-related features and capabilities, see:</span></span>

- [<span data-ttu-id="cce08-151">Office 365 のセキュリティ強化</span><span class="sxs-lookup"><span data-stu-id="cce08-151">Increased Office 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="cce08-152">強化された Office 365 セキュリティの設定を構成し、組み込みのセキュリティ ツールを調査します。</span><span class="sxs-lookup"><span data-stu-id="cce08-152">Configure settings for increased Office 365 security and investigate built-in security tools.</span></span>
  
- [<span data-ttu-id="cce08-153">データ分類</span><span class="sxs-lookup"><span data-stu-id="cce08-153">Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="cce08-154">Office 365 ラベルを構成し、SharePoint Online チーム サイトのドキュメントに適用します。</span><span class="sxs-lookup"><span data-stu-id="cce08-154">Configure and apply Office 365 labels to a document in a SharePoint Online team site.</span></span>
    
- [<span data-ttu-id="cce08-155">特権アクセスの管理</span><span class="sxs-lookup"><span data-stu-id="cce08-155">Privileged access management</span></span>](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="cce08-156">Office 365 組織の昇格されたタスクと特権タスクへの Just-In-Time アクセスを可能にするため、特権アクセス管理を構成します。</span><span class="sxs-lookup"><span data-stu-id="cce08-156">Configure privileged access management for just-in-time access to elevated and privileged tasks in your Office 365 organization.</span></span>


