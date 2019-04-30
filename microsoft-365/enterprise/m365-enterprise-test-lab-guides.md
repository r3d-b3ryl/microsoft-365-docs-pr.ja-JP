---
title: Microsoft 365 Enterprise のテスト ラボ ガイド
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/19/2019
ms.audience: ITPro
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
ms.openlocfilehash: 007fac786e7676d219d7e82c435e37fe3c3221df
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2019
ms.locfileid: "33353142"
---
# <a name="microsoft-365-enterprise-test-lab-guides"></a><span data-ttu-id="3a366-103">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="3a366-103">Microsoft 365 Enterprise Test Lab Guides</span></span>

<span data-ttu-id="3a366-p101">テスト ラボ ガイド (TLG) を活用すれば、Microsoft 製品の概要をいち早く把握することができます。テスト ラボ ガイドは、簡単ではあるものの代表的なテスト環境を構成する方法を説明しています。これらの環境は、試用期間または有料サブスクリプションの期間内に、デモ、カスタマイズ、概念の複合的な証拠の作成に使用できます。</span><span class="sxs-lookup"><span data-stu-id="3a366-p101">Test Lab Guides (TLGs) help you quickly learn about Microsoft products. They provide prescriptive instructions to configure simplified but representative test environments. You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription.</span></span> 

<span data-ttu-id="3a366-p102">TLG はモジュラーとして機能するように設計されています。TLG は、テストしてみたい内容やそのテストに必要な要件にできるだけ一致するように、複数の構成を行える仕組みになっています。この実地体験型ガイドにより、新しい製品やシナリオの展開要件を理解し、運用環境でホストする計画を立てやすくなります。</span><span class="sxs-lookup"><span data-stu-id="3a366-p102">TLGs are designed to be modular. They build upon each other to create multiple configurations that more closely match your learning or test configuration needs. The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario so you can better plan for hosting it in production.</span></span>

<span data-ttu-id="3a366-110">また、TLG を使用すると、アプリケーションの開発およびテスト用の典型的な環境を作成することもできます。これは、開発/テスト環境とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="3a366-110">You can also use TLGs to create representative environments for development and testing of applications, also known as dev/test environments.</span></span>
  
![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="3a366-112">[ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3a366-112">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="base-configuration"></a><span data-ttu-id="3a366-113">基本構成</span><span class="sxs-lookup"><span data-stu-id="3a366-113">Base configuration</span></span>

<span data-ttu-id="3a366-p103">最初に、Office 365 E5、Enterprise Mobility + Security (EMS) E5、Windows 10 Enterprise を含む [Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) のテスト環境を作成します。基本構成は 2 種類作成できます:</span><span class="sxs-lookup"><span data-stu-id="3a366-p103">First, you create a test environment for [Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) that includes Office 365 E5, Enterprise Mobility + Security (EMS) E5, and Windows 10 Enterprise. You can create two different types of base configurations:</span></span>

- <span data-ttu-id="3a366-116">オンプレミスのコンポーネントを含まないクラウド専用の環境で、Microsoft 365 Enterprise の機能を構成しデモンストレーションする場合は、[軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="3a366-116">Use the [lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 Enterprise features and capabilities in a cloud-only environment, which does not include any on-premises components.</span></span>

- <span data-ttu-id="3a366-117">Active Directory Domain Services (AD DS) ドメインなどのオンプレミスのコンポーネントを使用するハイブリッド クラウド環境で、Microsoft 365 Enterprise の機能を構成しデモンストレーションする場合は、[シミュレートされたエンタープライズ基本構成](simulated-ent-base-configuration-microsoft-365-enterprise.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="3a366-117">Use the [simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 Enterprise features and capabilities in a hybrid cloud environment, which uses on-premises components such as a Windows Server Active Directory (AD) domain.</span></span>
    
## <a name="identity"></a><span data-ttu-id="3a366-118">ID</span><span class="sxs-lookup"><span data-stu-id="3a366-118">Identity</span></span>

<span data-ttu-id="3a366-119">ID に関連する機能や能力のデモンストレーションは、以下を参照してください:</span><span class="sxs-lookup"><span data-stu-id="3a366-119">To demonstrate identity-related features and capabilities, see:</span></span>

- [<span data-ttu-id="3a366-120">パスワード ハッシュ同期</span><span class="sxs-lookup"><span data-stu-id="3a366-120">Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)
  
   <span data-ttu-id="3a366-121">Active Directory Domain Services (AD DS) ドメイン コントローラーからのパスワード ハッシュによるディレクトリ同期を有効にしてテストします。</span><span class="sxs-lookup"><span data-stu-id="3a366-121">Enable and test password hash-based directory synchronization from a Active Directory Domain Services (AD DS) domain controller.</span></span>

- [<span data-ttu-id="3a366-122">パススルー認証</span><span class="sxs-lookup"><span data-stu-id="3a366-122">Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md)
  
   <span data-ttu-id="3a366-123">AD DS ドメイン コントローラーへのパススルー認証を有効にしてテストします。</span><span class="sxs-lookup"><span data-stu-id="3a366-123">Enable and test pass-through authentication to a Windows Server AD domain controller.</span></span>

- [<span data-ttu-id="3a366-124">Azure AD シームレス シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="3a366-124">Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md)
  
   <span data-ttu-id="3a366-125">Azure AD シームレス シングル サインオン (SSO) を AD DS ドメイン コントローラーで有効にし、テストします。</span><span class="sxs-lookup"><span data-stu-id="3a366-125">Enable and test Azure AD Seamless Single Sign-on (SSO) with a Windows Server AD domain controller.</span></span>

- [<span data-ttu-id="3a366-126">多要素認証</span><span class="sxs-lookup"><span data-stu-id="3a366-126">Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md)
  
   <span data-ttu-id="3a366-127">特定のユーザー アカウントで、スマートフォンによる多要素認証を有効にしてテストします。</span><span class="sxs-lookup"><span data-stu-id="3a366-127">Enable and test smart phone-based multi-factor authentication for a specific user account.</span></span>

- [<span data-ttu-id="3a366-128">全体管理者アカウントを保護する</span><span class="sxs-lookup"><span data-stu-id="3a366-128">Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md)
 
   <span data-ttu-id="3a366-129">条件付きアクセス ポリシーを使用してグローバル管理者アカウントをロックする。</span><span class="sxs-lookup"><span data-stu-id="3a366-129">Lock down your global administrator accounts with Office 365 Cloud App Security and conditional access policies.</span></span>

- [<span data-ttu-id="3a366-130">パスワード ライトバック</span><span class="sxs-lookup"><span data-stu-id="3a366-130">Password writeback</span></span>](password-writeback-m365-ent-test-environment.md)

   <span data-ttu-id="3a366-131">パスワードの書き戻しは、Azure AD から AD DS ユーザー アカウントのパスワードを変更する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="3a366-131">Use password writeback to change the password on your AD DS user account from Azure AD.</span></span>

- [<span data-ttu-id="3a366-132">パスワードのリセット</span><span class="sxs-lookup"><span data-stu-id="3a366-132">Password reset</span></span>](password-reset-m365-ent-test-environment.md)

   <span data-ttu-id="3a366-133">セルフサービスによるパスワードのリセット (SSPR) を使用して、パスワードをリセットします。</span><span class="sxs-lookup"><span data-stu-id="3a366-133">Use self-service password reset (SSPR) to reset your password.</span></span>

- [<span data-ttu-id="3a366-134">ライセンスとグループ メンバーシップの自動管理</span><span class="sxs-lookup"><span data-stu-id="3a366-134">Automatic licensing and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md)

   <span data-ttu-id="3a366-135">自動ライセンス認証と動的なグループ メンバーシップを使用すると、新しいアカウントの管理をこれまでよりも簡単に行えます。</span><span class="sxs-lookup"><span data-stu-id="3a366-135">Make administering new accounts easier than ever with automatic licensing and dynamic group membership.</span></span>

- [<span data-ttu-id="3a366-136">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="3a366-136">Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md)

   <span data-ttu-id="3a366-137">現在のユーザー アカウントの脆弱性を確認します。</span><span class="sxs-lookup"><span data-stu-id="3a366-137">Scan your current user accounts for vulnerabilities.</span></span>

- [<span data-ttu-id="3a366-138">ID と デバイス アクセス</span><span class="sxs-lookup"><span data-stu-id="3a366-138">Identity and device access configurations</span></span>](identity-device-access-m365-test-environment.md)

   <span data-ttu-id="3a366-139">お勧めする ID、デバイス アクセスの構成、および条件付きアクセス ポリシーをテストするための環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="3a366-139">Create an environment to test recommended identity and device access configurations and conditional access policies.</span></span>


## <a name="mobile-device-management"></a><span data-ttu-id="3a366-140">モバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="3a366-140">Mobile device management</span></span>

<span data-ttu-id="3a366-141">モバイル デバイス管理に関連する機能や能力のデモンストレーションは、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a366-141">To demonstrate mobile device management-related features and capabilities, see:</span></span>

- [<span data-ttu-id="3a366-142">デバイス コンプライアンス ポリシー</span><span class="sxs-lookup"><span data-stu-id="3a366-142">Device compliance policies</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="3a366-143">Windows 10 デバイスのユーザー グループおよびデバイス コンプライアンス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="3a366-143">Create a user group and a device compliance policy for Windows 10 devices.</span></span>
    
- [<span data-ttu-id="3a366-144">iOS および Android デバイスの登録</span><span class="sxs-lookup"><span data-stu-id="3a366-144">Enroll iOS and Android devices</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   <span data-ttu-id="3a366-145">iOS または Android デバイスを登録し、それらをリモートで管理します。</span><span class="sxs-lookup"><span data-stu-id="3a366-145">Enroll iOS or Android devices and manage them remotely.</span></span>


## <a name="information-protection"></a><span data-ttu-id="3a366-146">情報保護</span><span class="sxs-lookup"><span data-stu-id="3a366-146">Information protection</span></span>

<span data-ttu-id="3a366-147">情報保護に関連する機能や能力のデモンストレーションは、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a366-147">To demonstrate information protection-related features and capabilities, see:</span></span>

- [<span data-ttu-id="3a366-148">Office 365 のセキュリティ強化</span><span class="sxs-lookup"><span data-stu-id="3a366-148">Increased Office 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="3a366-149">強化された Office 365 セキュリティの設定を構成し、組み込みのセキュリティ ツールを調査します。</span><span class="sxs-lookup"><span data-stu-id="3a366-149">Configure settings for increased Office 365 security and investigate built-in security tools.</span></span>
  
- [<span data-ttu-id="3a366-150">データ分類</span><span class="sxs-lookup"><span data-stu-id="3a366-150">Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="3a366-151">Office 365 ラベルを構成し、SharePoint Online チーム サイトのドキュメントに適用します。</span><span class="sxs-lookup"><span data-stu-id="3a366-151">Configure and apply Office 365 labels to a document in a SharePoint Online team site.</span></span>
    
- [<span data-ttu-id="3a366-152">特権アクセスの管理</span><span class="sxs-lookup"><span data-stu-id="3a366-152">Privileged access management</span></span>](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="3a366-153">Office 365 組織の昇格されたタスクと特権タスクへの Just-In-Time アクセスを可能にするため、特権アクセス管理を構成します。</span><span class="sxs-lookup"><span data-stu-id="3a366-153">Configure privileged acccess management for just-in-time access to elevated and privileged tasks in your Office 365 organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="3a366-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a366-154">See also</span></span>

[<span data-ttu-id="3a366-155">クラウド導入 TLG を使用した Office 365 のテスト</span><span class="sxs-lookup"><span data-stu-id="3a366-155">Test Office 365 with cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)
