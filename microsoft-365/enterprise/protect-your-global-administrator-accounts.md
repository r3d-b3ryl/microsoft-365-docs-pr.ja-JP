---
title: グローバル管理者Microsoft 365アカウントを保護する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- m365initiative-coredeploy
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
f1.keywords:
- NOCSH
ms.assetid: 6b4ded77-ac8d-42ed-8606-c014fd947560
description: この記事では、サブスクリプションへのグローバル管理者アクセスの保護に関Microsoft 365します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1c929651f3e70a1aeef16cdf48d853d675820833
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926549"
---
# <a name="protect-your-microsoft-365-global-administrator-accounts"></a><span data-ttu-id="77e17-103">グローバル管理者Microsoft 365アカウントを保護する</span><span class="sxs-lookup"><span data-stu-id="77e17-103">Protect your Microsoft 365 global administrator accounts</span></span>

<span data-ttu-id="77e17-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="77e17-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="77e17-105">Microsoft 365 サブスクリプションのセキュリティ侵害 (情報の収集やフィッシング攻撃など) は、通常、Microsoft 365 グローバル管理者アカウントの資格情報を侵害することで行われます。</span><span class="sxs-lookup"><span data-stu-id="77e17-105">Security breaches of a Microsoft 365 subscription, including information harvesting and phishing attacks, are typically done by compromising the credentials of a Microsoft 365 global administrator account.</span></span> <span data-ttu-id="77e17-106">クラウドのセキュリティは、お客様と Microsoft のパートナーシップです。</span><span class="sxs-lookup"><span data-stu-id="77e17-106">Security in the cloud is a partnership between you and Microsoft:</span></span>
  
- <span data-ttu-id="77e17-107">Microsoft クラウド サービスは、信頼とセキュリティの基盤の上に構築されています。</span><span class="sxs-lookup"><span data-stu-id="77e17-107">Microsoft cloud services are built on a foundation of trust and security.</span></span> <span data-ttu-id="77e17-108">Microsoft は、データとアプリケーションの保護に役立つセキュリティ制御と機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="77e17-108">Microsoft provides you security controls and capabilities to help you protect your data and applications.</span></span>
    
- <span data-ttu-id="77e17-109">ユーザーは、データと ID、およびデータを保護する責任、オンプレミス リソースのセキュリティ、および制御するクラウド コンポーネントのセキュリティを所有します。</span><span class="sxs-lookup"><span data-stu-id="77e17-109">You own your data and identities and the responsibility for protecting them, the security of your on-premises resources, and the security of cloud components you control.</span></span>
    
<span data-ttu-id="77e17-110">Microsoft では、組織の保護に役立つ機能を提供していますが、組織を使用する場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="77e17-110">Microsoft provides capabilities to help protect your organization, but they are effective only if you use them.</span></span> <span data-ttu-id="77e17-111">それらを使用しない場合は、攻撃に対して脆弱になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="77e17-111">If you do not use them, you may be vulnerable to attack.</span></span> <span data-ttu-id="77e17-112">グローバル管理者アカウントを保護するために、Microsoft は以下の詳細な手順を支援します。</span><span class="sxs-lookup"><span data-stu-id="77e17-112">To protect your global administrator accounts, Microsoft is here to help you with detailed instructions to:</span></span>
  
1. <span data-ttu-id="77e17-113">グローバル管理者アカウントMicrosoft 365作成し、必要な場合にのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="77e17-113">Create dedicated Microsoft 365 global administrator accounts and use them only when necessary.</span></span>
    
2. <span data-ttu-id="77e17-114">グローバル管理者アカウントに対して専用のMicrosoft 365を構成し、最も強力な形式のセカンダリ認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="77e17-114">Configure multi-factor authentication for your dedicated Microsoft 365 global administrator accounts and use the strongest form of secondary authentication.</span></span>
    
> [!Note]
> <span data-ttu-id="77e17-115">この記事ではグローバル管理者アカウントを中心に説明しますが、電子情報開示管理者やセキュリティ管理者アカウント、コンプライアンス管理者アカウントなど、サブスクリプション内のデータにアクセスするための広範なアクセス許可を持つ追加のアカウントを同じ方法で保護するかどうかを検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77e17-115">Although this article is focused on global administrator accounts, you should consider whether additional accounts with wide-ranging permissions to access the data in your subscription, such as eDiscovery administrator or security or compliance administrator accounts, should be protected in the same way.</span></span> <br > <span data-ttu-id="77e17-116">グローバル管理者アカウントは、ライセンスを追加せずに作成できます。</span><span class="sxs-lookup"><span data-stu-id="77e17-116">A global administrator account can be created without adding any licenses.</span></span>
  
## <a name="step-1-create-dedicated-microsoft-365-global-administrator-accounts-and-use-them-only-when-necessary"></a><span data-ttu-id="77e17-117">手順 1.</span><span class="sxs-lookup"><span data-stu-id="77e17-117">Step 1.</span></span> <span data-ttu-id="77e17-118">グローバル管理者アカウントMicrosoft 365専用のアカウントを作成し、必要な場合にのみ使用する</span><span class="sxs-lookup"><span data-stu-id="77e17-118">Create dedicated Microsoft 365 global administrator accounts and use them only when necessary</span></span>

<span data-ttu-id="77e17-119">役割をユーザー アカウントに割り当てるなど、グローバル管理者特権を必要とする管理タスクは比較的少ない。</span><span class="sxs-lookup"><span data-stu-id="77e17-119">There are relatively few administrative tasks, such as assigning roles to user accounts, that require global administrator privileges.</span></span> <span data-ttu-id="77e17-120">したがって、グローバル管理者の役割が割り当てられている日常のユーザー アカウントを使用する代わりに、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="77e17-120">Therefore, instead of using everyday user accounts that have been assigned the global admin role, do these steps:</span></span>
  
1. <span data-ttu-id="77e17-121">グローバル管理者の役割が割り当てられているユーザー アカウントのセットを決定します。</span><span class="sxs-lookup"><span data-stu-id="77e17-121">Determine the set of user accounts that have been assigned the global admin role.</span></span> <span data-ttu-id="77e17-122">この操作は、管理センター Microsoft 365、または次の Azure Active (Azure AD) Directory PowerShell を使用して、Graphできます。</span><span class="sxs-lookup"><span data-stu-id="77e17-122">You can do this in the Microsoft 365 admin center or with the following Azure Active (Azure AD) Directory PowerShell for Graph command:</span></span>
  
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Global Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

2. <span data-ttu-id="77e17-123">グローバル管理者ロールMicrosoft 365されているユーザー アカウントを使用して、サブスクリプションにサインインします。</span><span class="sxs-lookup"><span data-stu-id="77e17-123">Sign into your Microsoft 365 subscription with a user account that has been assigned the global admin role.</span></span>
    
3. <span data-ttu-id="77e17-124">最大 4 つの専用グローバル管理者ユーザー アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="77e17-124">Create up to a maximum of four dedicated global administrator user accounts.</span></span> <span data-ttu-id="77e17-125">**12 文字以上の強力なパスワードを使用します。**</span><span class="sxs-lookup"><span data-stu-id="77e17-125">**Use strong passwords at least 12 characters long.**</span></span> <span data-ttu-id="77e17-126">詳細については [、「強力なパスワードを作成する](https://support.microsoft.com/help/4026406/microsoft-account-create-a-strong-password) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77e17-126">See [Create a strong password](https://support.microsoft.com/help/4026406/microsoft-account-create-a-strong-password) for more information.</span></span> <span data-ttu-id="77e17-127">新しいアカウントのパスワードを安全な場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="77e17-127">Store the passwords for the new accounts in a secure location.</span></span> 
    
4. <span data-ttu-id="77e17-128">新しい専用のグローバル管理者ユーザー アカウントのそれぞれにグローバル管理者役割を割り当てる。</span><span class="sxs-lookup"><span data-stu-id="77e17-128">Assign the global admin role to each of the new dedicated global administrator user accounts.</span></span>
    
5. <span data-ttu-id="77e17-129">アカウントからサインアウトMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="77e17-129">Sign out of Microsoft 365.</span></span>
    
6. <span data-ttu-id="77e17-130">新しい専用のグローバル管理者ユーザー アカウントのいずれかを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="77e17-130">Sign in with one of the new dedicated global administrator user accounts.</span></span>
    
7. <span data-ttu-id="77e17-131">手順 1 からグローバル管理者ロールが割り当てられた既存のユーザー アカウントごとに、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="77e17-131">For each existing user account that had been assigned the global admin role from step 1:</span></span>
    
  - <span data-ttu-id="77e17-132">グローバル管理者の役割を削除します。</span><span class="sxs-lookup"><span data-stu-id="77e17-132">Remove the global admin role.</span></span>
    
  - <span data-ttu-id="77e17-133">そのユーザーのジョブ機能と責任に適したアカウントに管理者の役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="77e17-133">Assign admin roles to the account that are appropriate to that user's job function and responsibility.</span></span> <span data-ttu-id="77e17-134">管理者ロールの詳細については、「管理役割[Microsoft 365」を参照してください](/office365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="77e17-134">For more information about various admin roles in Microsoft 365, see [About admin roles](/office365/admin/add-users/about-admin-roles).</span></span>
    
8. <span data-ttu-id="77e17-135">アカウントからサインアウトMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="77e17-135">Sign out of Microsoft 365.</span></span>
    
<span data-ttu-id="77e17-136">結果は次の値になります。</span><span class="sxs-lookup"><span data-stu-id="77e17-136">The results should be:</span></span>
  
- <span data-ttu-id="77e17-137">グローバル管理者ロールを持つ、サブスクリプションのユーザー アカウントのみが、新しい専用のグローバル管理者アカウント セットとなります。</span><span class="sxs-lookup"><span data-stu-id="77e17-137">The only user accounts in your subscription that have the global admin role are the new set of dedicated global administrator accounts.</span></span> <span data-ttu-id="77e17-138">これを確認するには、次の PowerShell コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="77e17-138">Verify this with the following PowerShell command:</span></span>
    
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

- <span data-ttu-id="77e17-139">サブスクリプションを管理するその他の通常のユーザー アカウントには、各自の職務に関連する管理ロールが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="77e17-139">All other everyday user accounts that manage your subscription have admin roles assigned that are associated with their job responsibilities.</span></span>
    
<span data-ttu-id="77e17-140">この瞬間以降は、グローバル管理者特権を必要とするタスクに対してのみ、専用のグローバル管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="77e17-140">From this moment onward, you sign in with the dedicated global administrator accounts only for tasks that require global administrator privileges.</span></span> <span data-ttu-id="77e17-141">他のすべての管理Microsoft 365、他の管理役割をユーザー アカウントに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="77e17-141">All other Microsoft 365 administration must be done by assigning other administration roles to user accounts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="77e17-142">これには、日常のユーザー アカウントとしてサインアウトし、専用のグローバル管理者アカウントでサインインするための追加の手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="77e17-142">This does require additional steps to sign out as your everyday user account and sign in with a dedicated global administrator account.</span></span> <span data-ttu-id="77e17-143">ただし、これはグローバル管理者の操作に対して時折行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="77e17-143">But this only needs to be done occasionally for global administrator operations.</span></span> <span data-ttu-id="77e17-144">グローバル管理者アカウント侵害後にMicrosoft 365サブスクリプションを回復するには、さらに多くの手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="77e17-144">Consider that recovering your Microsoft 365 subscription after a global administrator account breach requires a lot more steps.</span></span>
  
## <a name="step-2-configure-multi-factor-authentication-for-your-dedicated-microsoft-365-global-administrator-accounts"></a><span data-ttu-id="77e17-145">手順 2.</span><span class="sxs-lookup"><span data-stu-id="77e17-145">Step 2.</span></span> <span data-ttu-id="77e17-146">グローバル管理者アカウント専用の複数要素認証Microsoft 365構成する</span><span class="sxs-lookup"><span data-stu-id="77e17-146">Configure multi-factor authentication for your dedicated Microsoft 365 global administrator accounts</span></span>

<span data-ttu-id="77e17-147">多要素認証 (MFA) には、アカウント名とパスワード以外の追加情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="77e17-147">Multi-factor authentication (MFA) requires additional information beyond the account name and password.</span></span> <span data-ttu-id="77e17-148">Microsoft 365は、次の追加の検証方法をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="77e17-148">Microsoft 365 supports these additional verification methods:</span></span>
  
- <span data-ttu-id="77e17-149">Microsoft Authenticator アプリ</span><span class="sxs-lookup"><span data-stu-id="77e17-149">The Microsoft Authenticator app</span></span>

- <span data-ttu-id="77e17-150">電話</span><span class="sxs-lookup"><span data-stu-id="77e17-150">A phone call</span></span>
    
- <span data-ttu-id="77e17-151">テキスト メッセージを介して送信されるランダムに生成された検証コード</span><span class="sxs-lookup"><span data-stu-id="77e17-151">A randomly generated verification code sent through a text message</span></span>
    
- <span data-ttu-id="77e17-152">スマート カード (仮想または物理)</span><span class="sxs-lookup"><span data-stu-id="77e17-152">A smart card (virtual or physical)</span></span>
    
- <span data-ttu-id="77e17-153">生体認証デバイス</span><span class="sxs-lookup"><span data-stu-id="77e17-153">A biometric device</span></span>
    
>[!Note]
><span data-ttu-id="77e17-154">国立標準技術研究所 (NIST) の標準に準拠する必要がある組織では、電話またはテキスト メッセージベースの追加検証方法の使用が制限されます。</span><span class="sxs-lookup"><span data-stu-id="77e17-154">For organizations that must adhere to National Institute of Standards and Technology (NIST) standards, the use of a phone call or text message-based additional verification methods are restricted.</span></span> <span data-ttu-id="77e17-155">詳細 [については、](https://pages.nist.gov/800-63-FAQ/#q-b01) ここをクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="77e17-155">Click [here](https://pages.nist.gov/800-63-FAQ/#q-b01) for the details.</span></span>
>

<span data-ttu-id="77e17-156">クラウドにのみ保存されているユーザー アカウント (クラウド専用 ID モデル) を使用している小規模企業の場合は、MFA を設定して、電話または専用のグローバル管理者アカウントごとにスマートフォンに送信されるテキスト メッセージ検証コードを使用して [MFA](/office365/admin/security-and-compliance/set-up-multi-factor-authentication) を構成します。</span><span class="sxs-lookup"><span data-stu-id="77e17-156">If you are a small business that is using user accounts stored only in the cloud (the cloud-only identity model), [set up MFA](/office365/admin/security-and-compliance/set-up-multi-factor-authentication) to configure MFA using a phone call or a text message verification code sent to a smart phone for each dedicated global administrator account.</span></span>
    
<span data-ttu-id="77e17-157">ハイブリッド ID モデルを使用している大規模な組織Microsoft 365、より多くの検証オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="77e17-157">If you are a larger organization that is using a Microsoft 365 hybrid identity model, you have more verification options.</span></span> <span data-ttu-id="77e17-158">より強力なセカンダリ認証方法のセキュリティ インフラストラクチャが既に用意されている場合は [、MFA](../admin/security-and-compliance/set-up-multi-factor-authentication.md) をセットアップし、各専用のグローバル管理者アカウントを適切な検証方法用に構成します。</span><span class="sxs-lookup"><span data-stu-id="77e17-158">If you have the security infrastructure already in place for a stronger secondary authentication method, [set up MFA](../admin/security-and-compliance/set-up-multi-factor-authentication.md) and configure each dedicated global administrator account for the appropriate verification method.</span></span>
  
<span data-ttu-id="77e17-159">必要な強力な検証方法のセキュリティ インフラストラクチャが Microsoft 365 MFA に対して機能していない場合は、Microsoft Authenticator アプリ、電話、または暫定的なセキュリティ対策として、グローバル管理者アカウント用にスマートフォンに送信されるテキスト メッセージ検証コードを使用して、MFA を使用して専用のグローバル管理者アカウントを構成することを強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="77e17-159">If the security infrastructure for the desired stronger verification method is not in place and functioning for Microsoft 365 MFA, we strongly recommend that you configure dedicated global administrator accounts with MFA using the Microsoft Authenticator app, a phone call, or a text message verification code sent to a smart phone for your global administrator accounts as an interim security measure.</span></span> <span data-ttu-id="77e17-160">MFA によって提供される追加の保護がない場合は、専用のグローバル管理者アカウントを残しません。</span><span class="sxs-lookup"><span data-stu-id="77e17-160">Do not leave your dedicated global administrator accounts without the additional protection provided by MFA.</span></span>
  
<span data-ttu-id="77e17-161">詳細については[、「MFA for Microsoft 365」 を参照してください](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)。</span><span class="sxs-lookup"><span data-stu-id="77e17-161">For more information, see [MFA for Microsoft 365](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md).</span></span>
  
<span data-ttu-id="77e17-162">MFA と PowerShell Microsoft 365サービスに接続するには、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77e17-162">To connect to Microsoft 365 services with MFA and PowerShell, see these articles:</span></span>

- [<span data-ttu-id="77e17-163">ユーザー アカウントMicrosoft 365ライセンスの PowerShell</span><span class="sxs-lookup"><span data-stu-id="77e17-163">PowerShell for Microsoft 365 for user accounts, groups, and licenses</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="77e17-164">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="77e17-164">Microsoft Teams</span></span>](/microsoftteams/teams-powershell-install)
- [<span data-ttu-id="77e17-165">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="77e17-165">Exchange Online</span></span>](/powershell/exchange/mfa-connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa)
- [<span data-ttu-id="77e17-166">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="77e17-166">SharePoint Online</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online#to-connect-with-multifactor-authentication-mfa)
- [<span data-ttu-id="77e17-167">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="77e17-167">Skype for Business Online</span></span>](manage-skype-for-business-online-with-microsoft-365-powershell.md#connect-using-an-admin-account-with-multi-factor-authentication)

## <a name="additional-protections-for-enterprise-organizations"></a><span data-ttu-id="77e17-168">エンタープライズ組織の追加の保護</span><span class="sxs-lookup"><span data-stu-id="77e17-168">Additional protections for enterprise organizations</span></span>

<span data-ttu-id="77e17-169">これらの追加の方法を使用して、グローバル管理者アカウントと、それを使用して実行する構成が可能な限り安全に保護されます。</span><span class="sxs-lookup"><span data-stu-id="77e17-169">Use these additional methods to ensure that your global administrator account, and the configuration that you perform using it, are as secure as possible.</span></span>
  
### <a name="privileged-access-workstation"></a><span data-ttu-id="77e17-170">特権アクセス ワークステーション</span><span class="sxs-lookup"><span data-stu-id="77e17-170">Privileged access workstation</span></span>

<span data-ttu-id="77e17-171">高い特権を持つタスクの実行を可能な限り安全に実行するには、特権アクセス ワークステーション (PAW) を使用します。</span><span class="sxs-lookup"><span data-stu-id="77e17-171">To ensure that the execution of highly privileged tasks is as secure as possible, use a privileged access workstation (PAW).</span></span> <span data-ttu-id="77e17-172">PAW は、グローバル管理者アカウントを必要とする構成などの機密性の高い構成タスクMicrosoft 365専用のコンピューターです。</span><span class="sxs-lookup"><span data-stu-id="77e17-172">A PAW is a dedicated computer that is only used for sensitive configuration tasks, such as Microsoft 365 configuration that requires a global administrator account.</span></span> <span data-ttu-id="77e17-173">このコンピューターはインターネットの閲覧や電子メールには毎日使用されないので、インターネット攻撃や脅威から保護されます。</span><span class="sxs-lookup"><span data-stu-id="77e17-173">Because this computer is not used daily for Internet browsing or email, it is better protected from Internet attacks and threats.</span></span>
  
<span data-ttu-id="77e17-174">PAW を設定する方法の手順については、「. [https://aka.ms/cyberpaw](/security/compass/privileged-access-devices)</span><span class="sxs-lookup"><span data-stu-id="77e17-174">For instructions on how to set up a PAW, see [https://aka.ms/cyberpaw](/security/compass/privileged-access-devices).</span></span>

<span data-ttu-id="77e17-175">Azure AD テナントと管理者アカウントに対して Azure PIM を有効にする場合は、[PIM の構成手順](/azure/active-directory/active-directory-privileged-identity-management-configure)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77e17-175">To enable Azure PIM for your Azure AD tenant and administrator accounts, see the [steps to configure PIM](/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>

<span data-ttu-id="77e17-176">サイバー攻撃者から特権アクセスをセキュリティで保護する包括的なロードマップを作成する場合は、「[Azure AD でのハイブリッドおよびクラウド デプロイ用の特権アクセスをセキュリティで保護する](/azure/active-directory/admin-roles-best-practices)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77e17-176">To develop a comprehensive roadmap to secure privileged access against cyber attackers, see [Securing privileged access for hybrid and cloud deployments in Azure AD](/azure/active-directory/admin-roles-best-practices).</span></span>

### <a name="azure-ad-privileged-identity-management"></a><span data-ttu-id="77e17-177">Azure AD Privileged Identity Management</span><span class="sxs-lookup"><span data-stu-id="77e17-177">Azure AD Privileged Identity Management</span></span>

<span data-ttu-id="77e17-178">グローバル管理者アカウントにグローバル管理者ロールを完全に割り当てるのではなく、Azure AD Privileged Identity Management (PIM) を使用して、必要に応じてグローバル管理者ロールのオンデマンドの Just-in-time 割り当てを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="77e17-178">Rather than having your global administrator accounts be permanently assigned the global administrator role, you can use Azure AD Privileged Identity Management (PIM) to enable on-demand, just-in-time assignment of the global administrator role when it is needed.</span></span>
  
<span data-ttu-id="77e17-179">グローバル管理者アカウントは、永続的な管理者から対象となる管理者に移動します。</span><span class="sxs-lookup"><span data-stu-id="77e17-179">Your global administrator accounts go from being permanent admins to eligible admins.</span></span> <span data-ttu-id="77e17-180">グローバル管理者の役割は、誰かが必要とするまで非アクティブです。</span><span class="sxs-lookup"><span data-stu-id="77e17-180">The global administrator role is inactive until someone needs it.</span></span> <span data-ttu-id="77e17-181">その後、アクティブ化プロセスを完了して、グローバル管理者の役割を所定の時間グローバル管理者アカウントに追加します。</span><span class="sxs-lookup"><span data-stu-id="77e17-181">You then complete an activation process to add the global administrator role to the global administrator account for a predetermined amount of time.</span></span> <span data-ttu-id="77e17-182">時間が経過すると、PIM はグローバル管理者アカウントからグローバル管理者の役割を削除します。</span><span class="sxs-lookup"><span data-stu-id="77e17-182">When the time expires, PIM removes the global administrator role from the global administrator account.</span></span>
  
<span data-ttu-id="77e17-183">PIM とこのプロセスを使用すると、グローバル管理者アカウントが悪意のあるユーザーによる攻撃や使用に対して脆弱になる時間が大幅に短縮されます。</span><span class="sxs-lookup"><span data-stu-id="77e17-183">Using PIM and this process significantly reduces the amount of time that your global administrator accounts are vulnerable to attack and use by malicious users.</span></span>

<span data-ttu-id="77e17-184">PIM は、Microsoft 365 E5 に含まれている Azure Active Directory Premium P2 で使用できます。</span><span class="sxs-lookup"><span data-stu-id="77e17-184">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 E5.</span></span> <span data-ttu-id="77e17-185">または、管理者アカウントの Azure Active Directory Premium P2 ライセンスを個別に購入できます。</span><span class="sxs-lookup"><span data-stu-id="77e17-185">Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your administrator accounts.</span></span>
  
<span data-ttu-id="77e17-186">詳細については、「Azure AD Privileged Identity Management」[を参照してください](/azure/active-directory/active-directory-privileged-identity-management-configure)。</span><span class="sxs-lookup"><span data-stu-id="77e17-186">For more information, see [Azure AD Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>
  

### <a name="privileged-access-management"></a><span data-ttu-id="77e17-187">特権アクセス管理</span><span class="sxs-lookup"><span data-stu-id="77e17-187">Privileged access management</span></span>

<span data-ttu-id="77e17-p121">特権アクセス管理は、テナントでのタスクベースのアクティビティに対して Just-In-Time アクセスを指定するポリシーを構成することで有効になります。これは、機密性の高いデータへの継続的なアクセスや重要な構成設定へのアクセスに、既存の特権管理者アカウントが使用される可能性のある侵害から組織を保護するために役立ちます。たとえば、テナント内の組織のメールボックス設定にアクセスして変更する際には、明示的な承認が必要になる特権アクセス管理ポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="77e17-p121">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your tenant. It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings. For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your tenant.</span></span>

<span data-ttu-id="77e17-p122">この手順では、テナントの特権アクセス管理を有効にして、組織のデータおよび構成設定へのタスクベースのアクセスに対するセキュリティを強化する特権アクセスポリシーを構成します。組織の特権アクセスは、次の 3 つの基本的な手順で開始します。</span><span class="sxs-lookup"><span data-stu-id="77e17-p122">In this step, you'll enable privileged access management in your tenant and configure privileged access policies that provide additional security for task-based access to data and configuration settings for your organization. There are three basic steps to get started with privileged access in your organization:</span></span>

- <span data-ttu-id="77e17-193">承認者のグループを作成する</span><span class="sxs-lookup"><span data-stu-id="77e17-193">Creating an approver's group</span></span>
- <span data-ttu-id="77e17-194">特権アクセスを有効にする</span><span class="sxs-lookup"><span data-stu-id="77e17-194">Enabling privileged access</span></span>
- <span data-ttu-id="77e17-195">承認ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="77e17-195">Creating approval policies</span></span>

<span data-ttu-id="77e17-196">特権アクセス管理を使用すると、組織はゼロの特権で運用し、このような永続的な管理アクセスのために発生する脆弱性に対する防御層を提供できます。</span><span class="sxs-lookup"><span data-stu-id="77e17-196">Privileged access management enables your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access.</span></span> <span data-ttu-id="77e17-197">特権アクセスには、関連付けられた承認ポリシーが定義されているタスクを実行する承認が必要です。</span><span class="sxs-lookup"><span data-stu-id="77e17-197">Privileged access requires approvals for executing any task that has an associated approval policy defined.</span></span> <span data-ttu-id="77e17-198">承認ポリシーに含まれるタスクを実行する必要があるユーザーは、アクセス承認を要求して付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77e17-198">Users needing to execute tasks included in the approval policy must request and be granted access approval.</span></span>

<span data-ttu-id="77e17-199">特権アクセス管理を有効にするには、「Configure [privileged access management」を参照してください](/office365/securitycompliance/privileged-access-management-configuration)。</span><span class="sxs-lookup"><span data-stu-id="77e17-199">To enable privileged access management, see [Configure privileged access management](/office365/securitycompliance/privileged-access-management-configuration).</span></span>

<span data-ttu-id="77e17-200">詳細については [、「Privileged access management」を参照してください](/office365/securitycompliance/privileged-access-management-overview)。</span><span class="sxs-lookup"><span data-stu-id="77e17-200">For more information, see [Privileged access management](/office365/securitycompliance/privileged-access-management-overview).</span></span>

### <a name="security-information-and-event-management-siem-software-for-microsoft-365-logging"></a><span data-ttu-id="77e17-201">セキュリティ情報とイベント管理 (SIEM) ソフトウェアをMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="77e17-201">Security information and event management (SIEM) software for Microsoft 365 logging</span></span>

<span data-ttu-id="77e17-202">サーバー上で実行される SIEM ソフトウェアは、アプリケーションとネットワーク ハードウェアによって作成されたセキュリティアラートとイベントのリアルタイム分析を実行します。</span><span class="sxs-lookup"><span data-stu-id="77e17-202">SIEM software run on a server performs real-time analysis of security alerts and events created by applications and network hardware.</span></span> <span data-ttu-id="77e17-203">SIEM サーバーが分析およびレポート機能にMicrosoft 365のセキュリティ 通知とイベントを含めるには、Azure サーバーを SEIM AD統合します。</span><span class="sxs-lookup"><span data-stu-id="77e17-203">To allow your SIEM server to include Microsoft 365 security alerts and events in its analysis and reporting functions, integrate Azure AD into you SEIM.</span></span> <span data-ttu-id="77e17-204">「[概要」を参照Azure Log Integration。](/azure/security/security-azure-log-integration-overview)</span><span class="sxs-lookup"><span data-stu-id="77e17-204">See [Introduction to Azure Log Integration](/azure/security/security-azure-log-integration-overview).</span></span>

## <a name="next-step"></a><span data-ttu-id="77e17-205">次の手順</span><span class="sxs-lookup"><span data-stu-id="77e17-205">Next step</span></span>

<span data-ttu-id="77e17-206">サブスクリプションの ID を設定する場合Microsoft 365を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77e17-206">If you're setting up identity for your Microsoft 365 subscription, see:</span></span>

- <span data-ttu-id="77e17-207">[クラウド専用 ID を](cloud-only-identities.md) 使用している場合のクラウド専用 ID</span><span class="sxs-lookup"><span data-stu-id="77e17-207">[Cloud-only identities](cloud-only-identities.md) if you're using cloud-only identity</span></span>
- <span data-ttu-id="77e17-208">[ハイブリッド ID を使用している場合](prepare-for-directory-synchronization.md) は、ディレクトリ同期の準備を行う</span><span class="sxs-lookup"><span data-stu-id="77e17-208">[Prepare for directory synchronization](prepare-for-directory-synchronization.md) if you're using hybrid identity</span></span>

  
## <a name="see-also"></a><span data-ttu-id="77e17-209">関連項目</span><span class="sxs-lookup"><span data-stu-id="77e17-209">See also</span></span>

[<span data-ttu-id="77e17-210">Microsoft 365のロードマップ</span><span class="sxs-lookup"><span data-stu-id="77e17-210">Microsoft 365 security roadmap</span></span>](/office365/securitycompliance/security-roadmap)