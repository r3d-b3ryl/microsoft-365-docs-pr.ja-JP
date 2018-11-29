---
title: Microsoft 365 Enterprise のテスト ラボ ガイド
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2018
ms.audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: 以下のテスト ラボ ガイドを使用して、Microsoft 365 Enterprise のデモ、概念実証、開発/テスト環境を設定します。
ms.openlocfilehash: df723647748532936e40bbdb4e34ff698b9fa650
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869499"
---
# <a name="microsoft-365-enterprise-test-lab-guides"></a><span data-ttu-id="b3ee1-103">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="b3ee1-103">Microsoft 365 Enterprise Test Lab Guides</span></span>

<span data-ttu-id="b3ee1-p101">テスト ラボ ガイド (TLG) を活用すれば、Microsoft 製品の概要をいち早く把握することができます。テスト ラボ ガイドは、簡単ではあるものの代表的なテスト環境を構成する方法を説明しています。これらの環境は、試用期間または有料サブスクリプションの期間内に、デモ、カスタマイズ、概念の複合的な証拠の作成に使用できます。</span><span class="sxs-lookup"><span data-stu-id="b3ee1-p101">Test Lab Guides (TLGs) help you quickly learn about Microsoft products. They provide prescriptive instructions to configure simplified but representative test environments. You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription.</span></span> 

<span data-ttu-id="b3ee1-p102">TLG はモジュラーとして機能するように設計されています。TLG は、テストしてみたい内容やそのテストに必要な要件にできるだけ一致するように、複数の構成を行える仕組みになっています。この実地体験型ガイドにより、新しい製品やシナリオの展開要件を理解し、運用環境でホストする計画を立てやすくなります。</span><span class="sxs-lookup"><span data-stu-id="b3ee1-p102">TLGs are designed to be modular. They build upon each other to create multiple configurations that more closely match your learning or test configuration needs. The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario so you can better plan for hosting it in production.</span></span>

<span data-ttu-id="b3ee1-110">また、TLG を使用すると、アプリケーションの開発およびテスト用の典型的な環境を作成することもできます。これは、開発/テスト環境とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="b3ee1-110">You can also use TLGs to create representative environments for development and testing of applications, also known as dev/test environments.</span></span>
  
![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="b3ee1-112">[ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b3ee1-112">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="base-configuration"></a><span data-ttu-id="b3ee1-113">基本構成</span><span class="sxs-lookup"><span data-stu-id="b3ee1-113">Base configuration</span></span>

<span data-ttu-id="b3ee1-p103">最初に、Office 365 E5、Enterprise Mobility + Security (EMS) E5、Windows 10 Enterprise を含む [Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) のテスト環境を作成します。基本構成は 2 種類作成できます:</span><span class="sxs-lookup"><span data-stu-id="b3ee1-p103">First, you create a test environment for [Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) that includes Office 365 E5, Enterprise Mobility + Security (EMS) E5, and Windows 10 Enterprise. You can create two different types of base configurations:</span></span>

- <span data-ttu-id="b3ee1-116">オンプレミスのコンポーネントを含まないクラウド専用の環境で、Microsoft 365 Enterprise の機能を構成しデモンストレーションする場合は、[軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="b3ee1-116">Use the [lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 Enterprise features and capabilities in a cloud-only environment, which does not include any on-premises components.</span></span>

- <span data-ttu-id="b3ee1-117">Windows Server Active Directory (AD) ドメインなどのオンプレミスのコンポーネントを使用するハイブリッド クラウド環境で、Microsoft 365 Enterprise の機能を構成しデモンストレーションする場合は、[シミュレートされたエンタープライズ基本構成](simulated-ent-base-configuration-microsoft-365-enterprise.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="b3ee1-117">Use the [simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 Enterprise features and capabilities in a hybrid cloud environment, which uses on-premises components such as a Windows Server Active Directory (AD) domain.</span></span>
    
## <a name="identity"></a><span data-ttu-id="b3ee1-118">ID</span><span class="sxs-lookup"><span data-stu-id="b3ee1-118">Identity</span></span>

<span data-ttu-id="b3ee1-119">ID に関連する機能や能力のデモンストレーションは、以下を参照してください:</span><span class="sxs-lookup"><span data-stu-id="b3ee1-119">To demonstrate identity-related features and capabilities, see:</span></span>

- [<span data-ttu-id="b3ee1-120">パスワード ハッシュ同期</span><span class="sxs-lookup"><span data-stu-id="b3ee1-120">Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)
  
   <span data-ttu-id="b3ee1-121">Windows Server AD ドメイン コントローラーからのパスワード ハッシュによるディレクトリ同期を有効にしてテストします。</span><span class="sxs-lookup"><span data-stu-id="b3ee1-121">Enable and test password hash-based directory synchronization from a Windows Server AD domain controller.</span></span>

- [<span data-ttu-id="b3ee1-122">パススルー認証</span><span class="sxs-lookup"><span data-stu-id="b3ee1-122">Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md)
  
   <span data-ttu-id="b3ee1-123">Windows Server AD ドメイン コントローラーへのパススルー認証を有効にしてテストします。</span><span class="sxs-lookup"><span data-stu-id="b3ee1-123">Enable and test pass-through authentication to a Windows Server AD domain controller.</span></span>

- [<span data-ttu-id="b3ee1-124">Azure AD シームレス シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="b3ee1-124">Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md)
  
   <span data-ttu-id="b3ee1-125">Azure AD シームレス シングル サインオン (SSO) をWindows Server AD ドメイン コントローラーで有効にし、テストします。</span><span class="sxs-lookup"><span data-stu-id="b3ee1-125">Enable and test Azure AD Seamless Single Sign-on (SSO) with a Windows Server AD domain controller.</span></span>

- [<span data-ttu-id="b3ee1-126">多要素認証</span><span class="sxs-lookup"><span data-stu-id="b3ee1-126">Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md)
  
   <span data-ttu-id="b3ee1-127">特定のユーザー アカウントで、スマートフォンによる多要素認証を有効にしてテストします。</span><span class="sxs-lookup"><span data-stu-id="b3ee1-127">Enable and test smart phone-based multi-factor authentication for a specific user account.</span></span>

- [<span data-ttu-id="b3ee1-128">全体管理者アカウントを保護する</span><span class="sxs-lookup"><span data-stu-id="b3ee1-128">Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md)
 
   <span data-ttu-id="b3ee1-129">Office 365 Cloud App Security と条件付きアクセス ポリシーを使用して、全体管理者アカウントをロックします。</span><span class="sxs-lookup"><span data-stu-id="b3ee1-129">Lock down your global administrator accounts with Office 365 Cloud App Security and conditional access policies.</span></span>

- [<span data-ttu-id="b3ee1-130">パスワードのリセット</span><span class="sxs-lookup"><span data-stu-id="b3ee1-130">Password reset</span></span>](password-reset-m365-ent-test-environment.md)

   <span data-ttu-id="b3ee1-131">セルフサービスによるパスワードのリセット (SSPR) を使用して、パスワードをリセットします。</span><span class="sxs-lookup"><span data-stu-id="b3ee1-131">Use self-service password reset (SSPR) to reset your password.</span></span>

- [<span data-ttu-id="b3ee1-132">ライセンスとグループ メンバーシップの自動管理</span><span class="sxs-lookup"><span data-stu-id="b3ee1-132">Automatic licensing and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md)

   <span data-ttu-id="b3ee1-133">自動ライセンス認証と動的なグループ メンバーシップを使用すると、新しいアカウントの管理をこれまでよりも簡単に行えます。</span><span class="sxs-lookup"><span data-stu-id="b3ee1-133">Make administering new accounts easier than ever with automatic licensing and dynamic group membership.</span></span>

- [<span data-ttu-id="b3ee1-134">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="b3ee1-134">Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md)

   <span data-ttu-id="b3ee1-135">現在のユーザー アカウントの脆弱性を確認します。</span><span class="sxs-lookup"><span data-stu-id="b3ee1-135">Scan your current user accounts for vulnerabilities.</span></span>

## <a name="mobile-device-management"></a><span data-ttu-id="b3ee1-136">モバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="b3ee1-136">Mobile device management</span></span>

<span data-ttu-id="b3ee1-137">モバイル デバイス管理に関連する機能や能力のデモンストレーションは、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3ee1-137">To demonstrate mobile device management-related features and capabilities, see:</span></span>

- [<span data-ttu-id="b3ee1-138">MAM ポリシー</span><span class="sxs-lookup"><span data-stu-id="b3ee1-138">MAM policies</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="b3ee1-139">iOS および Android デバイスのユーザー グループとモバイル アプリケーション管理 (MAM) のポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="b3ee1-139">Create user groups and mobile application management (MAM) policies for iOS and Android devices.</span></span>
    
- [<span data-ttu-id="b3ee1-140">iOS および Android デバイスの登録</span><span class="sxs-lookup"><span data-stu-id="b3ee1-140">Enroll iOS and Android devices</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   <span data-ttu-id="b3ee1-141">iOS または Android デバイスを登録し、それらをリモートで管理します。</span><span class="sxs-lookup"><span data-stu-id="b3ee1-141">Enroll iOS or Android devices and manage them remotely.</span></span>


## <a name="information-protection"></a><span data-ttu-id="b3ee1-142">情報保護</span><span class="sxs-lookup"><span data-stu-id="b3ee1-142">Information protection</span></span>

<span data-ttu-id="b3ee1-143">情報保護に関連する機能や能力のデモンストレーションは、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3ee1-143">To demonstrate information protection-related features and capabilities, see:</span></span>

- [<span data-ttu-id="b3ee1-144">Office 365 のセキュリティ強化</span><span class="sxs-lookup"><span data-stu-id="b3ee1-144">Increased Office 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="b3ee1-145">強化された Office 365 セキュリティの設定を構成し、組み込みのセキュリティ ツールを調査します。</span><span class="sxs-lookup"><span data-stu-id="b3ee1-145">Configure settings for increased Office 365 security and investigate built-in security tools.</span></span>
  
- [<span data-ttu-id="b3ee1-146">データ分類</span><span class="sxs-lookup"><span data-stu-id="b3ee1-146">Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="b3ee1-147">Office 365 ラベルを構成し、SharePoint Online チーム サイトのドキュメントに適用します。</span><span class="sxs-lookup"><span data-stu-id="b3ee1-147">Configure and apply Office 365 labels to a document in a SharePoint Online team site.</span></span>
    
- [<span data-ttu-id="b3ee1-148">Microsoft 365 Enterprise テスト環境の特権アクセスの管理</span><span class="sxs-lookup"><span data-stu-id="b3ee1-148">Privileged access management for your Microsoft 365 Enterprise test environment</span></span>](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="b3ee1-149">Office 365 組織の昇格されたタスクと特権タスクへの Just-In-Time アクセスを可能にするため、特権アクセス管理を構成します。</span><span class="sxs-lookup"><span data-stu-id="b3ee1-149">Configure privileged acccess management for just-in-time access to elevated and privileged tasks in your Office 365 organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="b3ee1-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3ee1-150">See also</span></span>

[<span data-ttu-id="b3ee1-151">クラウド導入のテスト ラボ ガイドを使用して Microsoft Cloud を体験する</span><span class="sxs-lookup"><span data-stu-id="b3ee1-151">Experience the Microsoft Cloud with Cloud Adoption Test Lab Guides</span></span>](https://mva.microsoft.com/training-courses/experience-the-microsoft-cloud-with-cloud-adoption-test-lab-guides-17960?l=LXNRdhSLE_1000115881)
    
[<span data-ttu-id="b3ee1-152">One Microsoft Cloud テスト ラボ ガイド一式</span><span class="sxs-lookup"><span data-stu-id="b3ee1-152">One Microsoft Cloud Test Lab Guide stack</span></span>](http://aka.ms/catlgstack)
