---
title: Microsoft 365 Enterprise のテスト ラボ ガイド
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/20/2019
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: 以下のテスト ラボ ガイドを使用して、Microsoft 365 Enterprise 向けのデモ、概念実証、または開発/テスト環境を設定します。
ms.openlocfilehash: a006f549d0ac68562faee9c935df7f15161b2f12
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909600"
---
# <a name="microsoft-365-for-enterprise-test-lab-guides"></a><span data-ttu-id="aee67-103">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="aee67-103">Microsoft 365 for enterprise Test Lab Guides</span></span>

<span data-ttu-id="aee67-104">*これは、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="aee67-104">*This applies to both Microsoft 365 for enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="aee67-p101">テスト ラボ ガイド (TLG) を活用すれば、Microsoft 製品の概要をいち早く把握することができます。テスト ラボ ガイドは、簡単ではあるものの代表的なテスト環境を構成する方法を説明しています。これらの環境は、試用期間または有料サブスクリプションの期間内に、デモ、カスタマイズ、概念の複合的な証拠の作成に使用できます。</span><span class="sxs-lookup"><span data-stu-id="aee67-p101">Test Lab Guides (TLGs) help you quickly learn about Microsoft products. They provide prescriptive instructions to configure simplified but representative test environments. You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription.</span></span>

<span data-ttu-id="aee67-108">TLG はモジュール式に設計されています。</span><span class="sxs-lookup"><span data-stu-id="aee67-108">TLGs are designed to be modular.</span></span> <span data-ttu-id="aee67-109">これらの構成は、学習またはテスト構成のニーズにより密接に一致する複数の構成を作成するために、互いに構築されます。</span><span class="sxs-lookup"><span data-stu-id="aee67-109">They build upon each other to create multiple configurations that more closely match your learning or test configuration needs.</span></span> <span data-ttu-id="aee67-110">「自分で構築し、動作します」という実践的なエクスペリエンスは、新しい製品またはシナリオの展開要件を理解し、実稼働環境でのホスティングをよりよく計画するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="aee67-110">The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario, so that you can better plan for hosting it in production.</span></span>

<span data-ttu-id="aee67-111">また、TLG を使用して代表的な環境を作成して、開発/テスト環境とも呼ばれるアプリケーションを開発およびテストすることもできます。</span><span class="sxs-lookup"><span data-stu-id="aee67-111">You can also use TLGs to create representative environments to develop and test applications, also known as dev/test environments.</span></span>
  
![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

<span data-ttu-id="aee67-113">Microsoft 365 for enterprise Test Lab Guide スタックのすべての記事へのビジュアル マップについては、次の図を展開するか [、Microsoft 365 for enterprise](../downloads/Microsoft365EnterpriseTLGStack.pdf)Test Lab Guide Stack に移動します。</span><span class="sxs-lookup"><span data-stu-id="aee67-113">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, expand the following graphic or go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

<span data-ttu-id="aee67-114">[![The Microsoft 365 Enterprise のテスト ラボ ガイド スタック](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="aee67-114">[![The Microsoft 365 for enterprise Test Lab Guide stack](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span></span>

## <a name="base-configuration"></a><span data-ttu-id="aee67-115">基本構成</span><span class="sxs-lookup"><span data-stu-id="aee67-115">Base configuration</span></span>

<span data-ttu-id="aee67-116">まず、Microsoft [365 for enterprise のテスト環境を作成します](/microsoft-365-enterprise/)。</span><span class="sxs-lookup"><span data-stu-id="aee67-116">First, create a test environment for [Microsoft 365 for enterprise](/microsoft-365-enterprise/).</span></span> <span data-ttu-id="aee67-117">次の 2 種類の基本構成を作成できます。</span><span class="sxs-lookup"><span data-stu-id="aee67-117">You can create two different types of base configurations:</span></span>

- <span data-ttu-id="aee67-118">[軽量な](lightweight-base-configuration-microsoft-365-enterprise.md) 基本構成 - クラウド専用環境で Microsoft 365 のエンタープライズ機能と機能を構成およびデモンストレーションする場合に使用します。これには、オンプレミス コンポーネントは含まれます。</span><span class="sxs-lookup"><span data-stu-id="aee67-118">[Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md) - Use this when you want to configure and demonstrate Microsoft 365 for enterprise features and capabilities in a cloud-only environment, which does not include any on-premises components.</span></span>

- <span data-ttu-id="aee67-119">[シミュレート](simulated-ent-base-configuration-microsoft-365-enterprise.md) されたエンタープライズ ベース構成 - Active Directory ドメイン サービス (AD DS) ドメインなどのオンプレミス コンポーネントを使用するハイブリッド クラウド環境で Microsoft 365 のエンタープライズ機能を構成およびデモンストレーションする場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="aee67-119">[Simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) - Use this when you want to configure and demonstrate Microsoft 365 for enterprise features and capabilities in a hybrid cloud environment, which uses on-premises components such as an Active Directory Domain Services (AD DS) domain.</span></span>

<span data-ttu-id="aee67-120">試用版または運用テスト環境に Microsoft 365 E5 ライセンスを追加することなく、Office 365 E5 のテスト環境を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="aee67-120">You can also create test environments for Office 365 E5 by not adding the Microsoft 365 E5 license to your trial or production test environment.</span></span>
    
## <a name="identity"></a><span data-ttu-id="aee67-121">ID</span><span class="sxs-lookup"><span data-stu-id="aee67-121">Identity</span></span>

<span data-ttu-id="aee67-122">ID に関連する機能や能力のデモンストレーションは、以下を参照してください:</span><span class="sxs-lookup"><span data-stu-id="aee67-122">To demonstrate identity-related features and capabilities, see:</span></span>

- [<span data-ttu-id="aee67-123">パスワード ハッシュ同期</span><span class="sxs-lookup"><span data-stu-id="aee67-123">Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)
  
   <span data-ttu-id="aee67-124">AD DS ドメイン コントローラーからのパスワード ハッシュによるディレクトリ同期を有効にしてテストします。</span><span class="sxs-lookup"><span data-stu-id="aee67-124">Enable and test password hash-based directory synchronization from an AD DS domain controller.</span></span>

- [<span data-ttu-id="aee67-125">パススルー認証</span><span class="sxs-lookup"><span data-stu-id="aee67-125">Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md)
  
   <span data-ttu-id="aee67-126">AD DS ドメイン コントローラーへのパススルー認証を有効にしてテストします。</span><span class="sxs-lookup"><span data-stu-id="aee67-126">Enable and test pass-through authentication to an AD DS domain controller.</span></span>

- [<span data-ttu-id="aee67-127">フェデレーション認証</span><span class="sxs-lookup"><span data-stu-id="aee67-127">Federated authentication</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
   <span data-ttu-id="aee67-128">AD DS ドメイン コントローラーへのフェデレーション認証を有効にしてテストします。</span><span class="sxs-lookup"><span data-stu-id="aee67-128">Enable and test federated authentication to an AD DS domain controller.</span></span>

- [<span data-ttu-id="aee67-129">Azure AD シームレス シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="aee67-129">Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md)
  
   <span data-ttu-id="aee67-130">Azure ドメイン コントローラーを使用ADシームレス シングル サインオン (シームレス SSO) を有効ADテストします。</span><span class="sxs-lookup"><span data-stu-id="aee67-130">Enable and test Azure AD Seamless Single Sign-on (Seamless SSO) with an AD DS domain controller.</span></span>

- [<span data-ttu-id="aee67-131">多要素認証</span><span class="sxs-lookup"><span data-stu-id="aee67-131">Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md)
  
   <span data-ttu-id="aee67-132">特定のユーザー アカウントで、スマートフォンによる多要素認証を有効にしてテストします。</span><span class="sxs-lookup"><span data-stu-id="aee67-132">Enable and test smart phone-based multi-factor authentication for a specific user account.</span></span>

- [<span data-ttu-id="aee67-133">全体管理者アカウントを保護する</span><span class="sxs-lookup"><span data-stu-id="aee67-133">Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md)

   <span data-ttu-id="aee67-134">条件付きアクセス ポリシーを使用してグローバル管理者アカウントをロックする。</span><span class="sxs-lookup"><span data-stu-id="aee67-134">Lock down your global administrator accounts with conditional access policies.</span></span>

- [<span data-ttu-id="aee67-135">パスワード ライトバック</span><span class="sxs-lookup"><span data-stu-id="aee67-135">Password writeback</span></span>](password-writeback-m365-ent-test-environment.md)

   <span data-ttu-id="aee67-136">パスワードの書き戻しは、Azure AD から AD DS ユーザー アカウントのパスワードを変更する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="aee67-136">Use password writeback to change the password on your AD DS user account from Azure AD.</span></span>

- [<span data-ttu-id="aee67-137">パスワードのリセット</span><span class="sxs-lookup"><span data-stu-id="aee67-137">Password reset</span></span>](password-reset-m365-ent-test-environment.md)

   <span data-ttu-id="aee67-138">セルフサービスのパスワードリセットを使用してパスワードをリセットします。</span><span class="sxs-lookup"><span data-stu-id="aee67-138">Use self-service password reset to reset your password.</span></span>

- [<span data-ttu-id="aee67-139">ライセンスとグループ メンバーシップの自動管理</span><span class="sxs-lookup"><span data-stu-id="aee67-139">Automatic licensing and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md)

   <span data-ttu-id="aee67-140">自動ライセンス認証と動的なグループ メンバーシップを使用すると、新しいアカウントの管理をこれまでよりも簡単に行えます。</span><span class="sxs-lookup"><span data-stu-id="aee67-140">Make administering new accounts easier than ever with automatic licensing and dynamic group membership.</span></span>

- [<span data-ttu-id="aee67-141">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="aee67-141">Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md)

   <span data-ttu-id="aee67-142">現在のユーザー アカウントの脆弱性を確認します。</span><span class="sxs-lookup"><span data-stu-id="aee67-142">Scan your current user accounts for vulnerabilities.</span></span>

- [<span data-ttu-id="aee67-143">ID と デバイス アクセス</span><span class="sxs-lookup"><span data-stu-id="aee67-143">Identity and device access</span></span>](identity-device-access-m365-test-environment.md)

   <span data-ttu-id="aee67-144">お勧めする ID、デバイス アクセスの構成、および条件付きアクセス ポリシーをテストするための環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="aee67-144">Create an environment to test recommended identity and device access configurations and conditional access policies.</span></span>

## <a name="mobile-device-management"></a><span data-ttu-id="aee67-145">モバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="aee67-145">Mobile device management</span></span>

<span data-ttu-id="aee67-146">モバイル デバイス管理に関連する機能や能力のデモンストレーションは、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aee67-146">To demonstrate mobile device management-related features and capabilities, see:</span></span>

- [<span data-ttu-id="aee67-147">デバイス コンプライアンス ポリシー</span><span class="sxs-lookup"><span data-stu-id="aee67-147">Device compliance policies</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="aee67-148">Windows 10 デバイスのユーザー グループおよびデバイス コンプライアンス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="aee67-148">Create a user group and a device compliance policy for Windows 10 devices.</span></span>
    
- [<span data-ttu-id="aee67-149">iOS および Android デバイスの登録</span><span class="sxs-lookup"><span data-stu-id="aee67-149">Enroll iOS and Android devices</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   <span data-ttu-id="aee67-150">iOS または Android デバイスを登録し、それらをリモートで管理します。</span><span class="sxs-lookup"><span data-stu-id="aee67-150">Enroll iOS or Android devices and manage them remotely.</span></span>

## <a name="information-protection"></a><span data-ttu-id="aee67-151">情報保護</span><span class="sxs-lookup"><span data-stu-id="aee67-151">Information protection</span></span>

<span data-ttu-id="aee67-152">情報保護に関連する機能や能力のデモンストレーションは、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aee67-152">To demonstrate information protection-related features and capabilities, see:</span></span>

- [<span data-ttu-id="aee67-153">強化された Microsoft 365 のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="aee67-153">Increased Microsoft 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="aee67-154">強化された Microsoft 365 セキュリティの設定を構成し、組み込みのセキュリティ ツールを調査します。</span><span class="sxs-lookup"><span data-stu-id="aee67-154">Configure settings for increased Microsoft 365 security and investigate built-in security tools.</span></span>
  
- [<span data-ttu-id="aee67-155">データ分類</span><span class="sxs-lookup"><span data-stu-id="aee67-155">Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="aee67-156">ラベルを構成し、SharePoint Online チーム サイトのドキュメントに適用します。</span><span class="sxs-lookup"><span data-stu-id="aee67-156">Configure and apply labels to a document in a SharePoint Online team site.</span></span>
    
- [<span data-ttu-id="aee67-157">特権アクセスの管理</span><span class="sxs-lookup"><span data-stu-id="aee67-157">Privileged access management</span></span>](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="aee67-158">組織の昇格されたタスクと特権タスクへの Just-In-Time アクセスを可能にするため、特権アクセス管理を構成します。</span><span class="sxs-lookup"><span data-stu-id="aee67-158">Configure privileged access management for just-in-time access to elevated and privileged tasks in your organization.</span></span>