---
title: Microsoft 365 のグローバル管理者アカウントを保護する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365initiative-coredeploy
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
f1.keywords:
- NOCSH
ms.assetid: 6b4ded77-ac8d-42ed-8606-c014fd947560
description: この記事では、グローバル管理者のアクセスを Microsoft 365 サブスクリプションに保護する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bcc1a09ca8e7c57d4d6c69400925df3531c53c4f
ms.sourcegitcommit: 8589323c1b4ab43aab30597ee66303b0a0eb71ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/05/2020
ms.locfileid: "48357808"
---
# <a name="protect-your-microsoft-365-global-administrator-accounts"></a><span data-ttu-id="fd861-103">Microsoft 365 のグローバル管理者アカウントを保護する</span><span class="sxs-lookup"><span data-stu-id="fd861-103">Protect your Microsoft 365 global administrator accounts</span></span>

<span data-ttu-id="fd861-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="fd861-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="fd861-105">Microsoft 365 サブスクリプションのセキュリティ侵害 (情報の収集、フィッシング攻撃を含む) は、通常、Microsoft 365 のグローバル管理者アカウントの資格情報を侵害することによって行われます。</span><span class="sxs-lookup"><span data-stu-id="fd861-105">Security breaches of a Microsoft 365 subscription, including information harvesting and phishing attacks, are typically done by compromising the credentials of a Microsoft 365 global administrator account.</span></span> <span data-ttu-id="fd861-106">クラウドのセキュリティは、お互いと Microsoft の間のパートナーシップです。</span><span class="sxs-lookup"><span data-stu-id="fd861-106">Security in the cloud is a partnership between you and Microsoft:</span></span>
  
- <span data-ttu-id="fd861-107">Microsoft クラウドサービスは、信頼とセキュリティの基礎に基づいて構築されています。</span><span class="sxs-lookup"><span data-stu-id="fd861-107">Microsoft cloud services are built on a foundation of trust and security.</span></span> <span data-ttu-id="fd861-108">Microsoft は、データとアプリケーションを保護するためのセキュリティ制御と機能を提供しています。</span><span class="sxs-lookup"><span data-stu-id="fd861-108">Microsoft provides you security controls and capabilities to help you protect your data and applications.</span></span>
    
- <span data-ttu-id="fd861-109">データと id、およびそれらを保護する責任、オンプレミスのリソースのセキュリティ、および管理するクラウドコンポーネントのセキュリティを所有しています。</span><span class="sxs-lookup"><span data-stu-id="fd861-109">You own your data and identities and the responsibility for protecting them, the security of your on-premises resources, and the security of cloud components you control.</span></span>
    
<span data-ttu-id="fd861-110">Microsoft は、組織を保護するための機能を提供していますが、使用する場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="fd861-110">Microsoft provides capabilities to help protect your organization, but they are effective only if you use them.</span></span> <span data-ttu-id="fd861-111">これらを使用しないと、攻撃にさらされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fd861-111">If you do not use them, you may be vulnerable to attack.</span></span> <span data-ttu-id="fd861-112">全体管理者アカウントを保護するために、Microsoft は次のことを行うための詳細な指示にお役立てください。</span><span class="sxs-lookup"><span data-stu-id="fd861-112">To protect your global administrator accounts, Microsoft is here to help you with detailed instructions to:</span></span>
  
1. <span data-ttu-id="fd861-113">専用の Microsoft 365 グローバル管理者アカウントを作成し、必要な場合にのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="fd861-113">Create dedicated Microsoft 365 global administrator accounts and use them only when necessary.</span></span>
    
2. <span data-ttu-id="fd861-114">専用の Microsoft 365 グローバル管理者アカウントに対して多要素認証を構成し、最強のセカンダリ認証形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="fd861-114">Configure multi-factor authentication for your dedicated Microsoft 365 global administrator accounts and use the strongest form of secondary authentication.</span></span>
    
> [!Note]
> <span data-ttu-id="fd861-115">この記事ではグローバル管理者アカウントに重点を置いていますが、電子情報開示管理者やセキュリティまたはコンプライアンス管理者アカウントなど、さまざまな範囲のアクセス許可を持つその他のアカウントを同じ方法で保護する必要があるかどうかを検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd861-115">Although this article is focused on global administrator accounts, you should consider whether additional accounts with wide-ranging permissions to access the data in your subscription, such as eDiscovery administrator or security or compliance administrator accounts, should be protected in the same way.</span></span> <br > <span data-ttu-id="fd861-116">グローバル管理者アカウントは、ライセンスを追加することなく作成できます。</span><span class="sxs-lookup"><span data-stu-id="fd861-116">A global administrator account can be created without adding any licenses.</span></span>
  
## <a name="step-1-create-dedicated-microsoft-365-global-administrator-accounts-and-use-them-only-when-necessary"></a><span data-ttu-id="fd861-117">手順 1.</span><span class="sxs-lookup"><span data-stu-id="fd861-117">Step 1.</span></span> <span data-ttu-id="fd861-118">専用の Microsoft 365 グローバル管理者アカウントを作成し、必要な場合にのみ使用する</span><span class="sxs-lookup"><span data-stu-id="fd861-118">Create dedicated Microsoft 365 global administrator accounts and use them only when necessary</span></span>

<span data-ttu-id="fd861-119">グローバル管理者特権を必要とする、ユーザーアカウントへの役割の割り当てなど、比較的少数の管理タスクがあります。</span><span class="sxs-lookup"><span data-stu-id="fd861-119">There are relatively few administrative tasks, such as assigning roles to user accounts, that require global administrator privileges.</span></span> <span data-ttu-id="fd861-120">そのため、グローバル管理者の役割が割り当てられている日常のユーザーアカウントを使用する代わりに、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="fd861-120">Therefore, instead of using everyday user accounts that have been assigned the global admin role, do these steps:</span></span>
  
1. <span data-ttu-id="fd861-121">グローバル管理者の役割が割り当てられているユーザーアカウントのセットを決定します。</span><span class="sxs-lookup"><span data-stu-id="fd861-121">Determine the set of user accounts that have been assigned the global admin role.</span></span> <span data-ttu-id="fd861-122">これは、Microsoft 365 管理センターで行うか、次の Azure Active (Azure AD) Directory PowerShell for Graph コマンドを使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="fd861-122">You can do this in the Microsoft 365 admin center or with the following Azure Active (Azure AD) Directory PowerShell for Graph command:</span></span>
  
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

2. <span data-ttu-id="fd861-123">グローバル管理者の役割が割り当てられているユーザーアカウントを使用して、Microsoft 365 サブスクリプションにサインインします。</span><span class="sxs-lookup"><span data-stu-id="fd861-123">Sign into your Microsoft 365 subscription with a user account that has been assigned the global admin role.</span></span>
    
3. <span data-ttu-id="fd861-124">最大4つの専用のグローバル管理者ユーザーアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="fd861-124">Create up to a maximum of four dedicated global administrator user accounts.</span></span> <span data-ttu-id="fd861-125">**少なくとも12文字の強力なパスワードを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="fd861-125">**Use strong passwords at least 12 characters long.**</span></span> <span data-ttu-id="fd861-126">詳細について [は、「強力なパスワードを作成する](https://support.microsoft.com/help/4026406/microsoft-account-create-a-strong-password) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd861-126">See [Create a strong password](https://support.microsoft.com/help/4026406/microsoft-account-create-a-strong-password) for more information.</span></span> <span data-ttu-id="fd861-127">新しいアカウントのパスワードを安全な場所に格納します。</span><span class="sxs-lookup"><span data-stu-id="fd861-127">Store the passwords for the new accounts in a secure location.</span></span> 
    
4. <span data-ttu-id="fd861-128">新しい専用のグローバル管理者ユーザーアカウントに、グローバル管理者の役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="fd861-128">Assign the global admin role to each of the new dedicated global administrator user accounts.</span></span>
    
5. <span data-ttu-id="fd861-129">Microsoft 365 からサインアウトします。</span><span class="sxs-lookup"><span data-stu-id="fd861-129">Sign out of Microsoft 365.</span></span>
    
6. <span data-ttu-id="fd861-130">新しい専用のグローバル管理者ユーザーアカウントのいずれかを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="fd861-130">Sign in with one of the new dedicated global administrator user accounts.</span></span>
    
7. <span data-ttu-id="fd861-131">手順1でグローバル管理者の役割が割り当てられている既存のユーザーアカウントごとに、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="fd861-131">For each existing user account that had been assigned the global admin role from step 1:</span></span>
    
  - <span data-ttu-id="fd861-132">グローバル管理者ロールを削除します。</span><span class="sxs-lookup"><span data-stu-id="fd861-132">Remove the global admin role.</span></span>
    
  - <span data-ttu-id="fd861-133">そのユーザーのジョブ機能と責任に応じて、管理者の役割をアカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="fd861-133">Assign admin roles to the account that are appropriate to that user's job function and responsibility.</span></span> <span data-ttu-id="fd861-134">Microsoft 365 のさまざまな管理者ロールの詳細については、「 [管理者の役割につい](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd861-134">For more information about various admin roles in Microsoft 365, see [About admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).</span></span>
    
8. <span data-ttu-id="fd861-135">Microsoft 365 からサインアウトします。</span><span class="sxs-lookup"><span data-stu-id="fd861-135">Sign out of Microsoft 365.</span></span>
    
<span data-ttu-id="fd861-136">結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="fd861-136">The results should be:</span></span>
  
- <span data-ttu-id="fd861-137">グローバル管理者ロールを持つ、サブスクリプションのユーザー アカウントのみが、新しい専用のグローバル管理者アカウント セットとなります。</span><span class="sxs-lookup"><span data-stu-id="fd861-137">The only user accounts in your subscription that have the global admin role are the new set of dedicated global administrator accounts.</span></span> <span data-ttu-id="fd861-138">このことを確認するには、次の PowerShell コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="fd861-138">Verify this with the following PowerShell command:</span></span>
    
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

- <span data-ttu-id="fd861-139">サブスクリプションを管理するその他の通常のユーザー アカウントには、各自の職務に関連する管理ロールが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="fd861-139">All other everyday user accounts that manage your subscription have admin roles assigned that are associated with their job responsibilities.</span></span>
    
<span data-ttu-id="fd861-140">この時点から、グローバル管理者特権を必要とするタスクに対してのみ、専用のグローバル管理者アカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="fd861-140">From this moment onward, you sign in with the dedicated global administrator accounts only for tasks that require global administrator privileges.</span></span> <span data-ttu-id="fd861-141">他のすべての Microsoft 365 管理は、他の管理役割をユーザーアカウントに割り当てることによって実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd861-141">All other Microsoft 365 administration must be done by assigning other administration roles to user accounts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fd861-142">これには、日常のユーザーアカウントとしてサインアウトし、専用のグローバル管理者アカウントでサインインするための追加の手順が必要になります。</span><span class="sxs-lookup"><span data-stu-id="fd861-142">This does require additional steps to sign out as your everyday user account and sign in with a dedicated global administrator account.</span></span> <span data-ttu-id="fd861-143">ただし、この操作を実行する必要があるのは、全体管理者の操作の場合だけです。</span><span class="sxs-lookup"><span data-stu-id="fd861-143">But this only needs to be done occasionally for global administrator operations.</span></span> <span data-ttu-id="fd861-144">グローバル管理者アカウント違反がある場合は、さらに多くの手順を実行する必要があるため、Microsoft 365 サブスクリプションを復元することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="fd861-144">Consider that recovering your Microsoft 365 subscription after a global administrator account breach requires a lot more steps.</span></span>
  
## <a name="step-2-configure-multi-factor-authentication-for-your-dedicated-microsoft-365-global-administrator-accounts"></a><span data-ttu-id="fd861-145">手順 2.</span><span class="sxs-lookup"><span data-stu-id="fd861-145">Step 2.</span></span> <span data-ttu-id="fd861-146">専用の Microsoft 365 グローバル管理者アカウントに対して多要素認証を構成する</span><span class="sxs-lookup"><span data-stu-id="fd861-146">Configure multi-factor authentication for your dedicated Microsoft 365 global administrator accounts</span></span>

<span data-ttu-id="fd861-147">多要素認証 (MFA) には、アカウント名とパスワード以外の追加情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="fd861-147">Multi-factor authentication (MFA) requires additional information beyond the account name and password.</span></span> <span data-ttu-id="fd861-148">Microsoft 365 では、次の追加の検証方法がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="fd861-148">Microsoft 365 supports these additional verification methods:</span></span>
  
- <span data-ttu-id="fd861-149">Microsoft Authenticator アプリ</span><span class="sxs-lookup"><span data-stu-id="fd861-149">The Microsoft Authenticator app</span></span>

- <span data-ttu-id="fd861-150">電話</span><span class="sxs-lookup"><span data-stu-id="fd861-150">A phone call</span></span>
    
- <span data-ttu-id="fd861-151">テキストメッセージを使用して送信された、ランダムに生成された検証コード</span><span class="sxs-lookup"><span data-stu-id="fd861-151">A randomly generated verification code sent through a text message</span></span>
    
- <span data-ttu-id="fd861-152">スマート カード (仮想または物理)</span><span class="sxs-lookup"><span data-stu-id="fd861-152">A smart card (virtual or physical)</span></span>
    
- <span data-ttu-id="fd861-153">生体認証デバイス</span><span class="sxs-lookup"><span data-stu-id="fd861-153">A biometric device</span></span>
    
>[!Note]
><span data-ttu-id="fd861-154">米国標準規格とテクノロジ (NIST) 標準に準拠する必要がある組織では、電話またはテキストメッセージベースの追加の検証方法を使用することは制限されています。</span><span class="sxs-lookup"><span data-stu-id="fd861-154">For organizations that must adhere to National Institute of Standards and Technology (NIST) standards, the use of a phone call or text message-based additional verification methods are restricted.</span></span> <span data-ttu-id="fd861-155">詳細については、 [ここ](https://pages.nist.gov/800-63-FAQ/#q-b01) をクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="fd861-155">Click [here](https://pages.nist.gov/800-63-FAQ/#q-b01) for the details.</span></span>
>

<span data-ttu-id="fd861-156">クラウドのみに格納されているユーザーアカウントを使用している小規模な企業 (クラウドのみの id モデル) の場合は、 [mfa を設定](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) して、電話を使用して mfa を構成するか、専用のグローバル管理者アカウントごとにスマートフォンに送信されるテキストメッセージの検証コードを使用します。</span><span class="sxs-lookup"><span data-stu-id="fd861-156">If you are a small business that is using user accounts stored only in the cloud (the cloud-only identity model), [set up MFA](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) to configure MFA using a phone call or a text message verification code sent to a smart phone for each dedicated global administrator account.</span></span>
    
<span data-ttu-id="fd861-157">Microsoft 365 ハイブリッド id モデルを使用している大規模な組織の場合は、さらに多くの検証オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="fd861-157">If you are a larger organization that is using a Microsoft 365 hybrid identity model, you have more verification options.</span></span> <span data-ttu-id="fd861-158">より強力なセカンダリ認証方法に対してセキュリティインフラストラクチャが既に配置されている場合は、 [MFA を設定](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication) し、適切な検証方法にそれぞれの専用のグローバル管理者アカウントを構成します。</span><span class="sxs-lookup"><span data-stu-id="fd861-158">If you have the security infrastructure already in place for a stronger secondary authentication method, [set up MFA](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication) and configure each dedicated global administrator account for the appropriate verification method.</span></span>
  
<span data-ttu-id="fd861-159">目的の強力な検証方法のセキュリティインフラストラクチャが、Microsoft 365 MFA 用に設置されておらず、機能していない場合は、一時的なセキュリティ対策として、Microsoft Authenticator アプリ、電話、または全体管理者アカウントのスマートフォンに送信されるテキストメッセージ検証コードを使用して、専用のグローバル管理者アカウントを MFA で構成することを</span><span class="sxs-lookup"><span data-stu-id="fd861-159">If the security infrastructure for the desired stronger verification method is not in place and functioning for Microsoft 365 MFA, we strongly recommend that you configure dedicated global administrator accounts with MFA using the Microsoft Authenticator app, a phone call, or a text message verification code sent to a smart phone for your global administrator accounts as an interim security measure.</span></span> <span data-ttu-id="fd861-160">MFA で提供される追加の保護を行わずに、専用のグローバル管理者アカウントを残さないようにします。</span><span class="sxs-lookup"><span data-stu-id="fd861-160">Do not leave your dedicated global administrator accounts without the additional protection provided by MFA.</span></span>
  
<span data-ttu-id="fd861-161">詳細については、「 [Microsoft 365 の MFA](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd861-161">For more information, see [MFA for Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365).</span></span>
  
<span data-ttu-id="fd861-162">MFA と PowerShell を使用して Microsoft 365 サービスに接続するには、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd861-162">To connect to Microsoft 365 services with MFA and PowerShell, see these articles:</span></span>

- [<span data-ttu-id="fd861-163">ユーザーアカウント、グループ、ライセンスのための Microsoft 365 の PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd861-163">PowerShell for Microsoft 365 for user accounts, groups, and licenses</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="fd861-164">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fd861-164">Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-install)
- [<span data-ttu-id="fd861-165">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="fd861-165">Exchange Online</span></span>](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa)
- [<span data-ttu-id="fd861-166">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="fd861-166">SharePoint Online</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online#to-connect-with-multifactor-authentication-mfa)
- [<span data-ttu-id="fd861-167">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="fd861-167">Skype for Business Online</span></span>](manage-skype-for-business-online-with-microsoft-365-powershell.md#connect-using-an-admin-account-with-multi-factor-authentication)

## <a name="additional-protections-for-enterprise-organizations"></a><span data-ttu-id="fd861-168">エンタープライズ組織のための追加の保護</span><span class="sxs-lookup"><span data-stu-id="fd861-168">Additional protections for enterprise organizations</span></span>

<span data-ttu-id="fd861-169">これらの追加の方法を使用して、全体管理者アカウントと、それを使用して実行する構成を可能な限り安全なものにすることができます。</span><span class="sxs-lookup"><span data-stu-id="fd861-169">Use these additional methods to ensure that your global administrator account, and the configuration that you perform using it, are as secure as possible.</span></span>
  
### <a name="privileged-access-workstation"></a><span data-ttu-id="fd861-170">特権アクセスワークステーション</span><span class="sxs-lookup"><span data-stu-id="fd861-170">Privileged access workstation</span></span>

<span data-ttu-id="fd861-171">高い権限を持つタスクの実行が可能な限り安全であることを確認するには、特権アクセスワークステーション (PAW) を使用します。</span><span class="sxs-lookup"><span data-stu-id="fd861-171">To ensure that the execution of highly privileged tasks is as secure as possible, use a privileged access workstation (PAW).</span></span> <span data-ttu-id="fd861-172">PAW は、グローバル管理者アカウントを必要とする Microsoft 365 構成などの機密性の高い構成タスクにのみ使用される専用のコンピューターです。</span><span class="sxs-lookup"><span data-stu-id="fd861-172">A PAW is a dedicated computer that is only used for sensitive configuration tasks, such as Microsoft 365 configuration that requires a global administrator account.</span></span> <span data-ttu-id="fd861-173">このコンピューターはインターネットブラウジングや電子メールで毎日使用されていないため、インターネット攻撃および脅威から保護するのが適切です。</span><span class="sxs-lookup"><span data-stu-id="fd861-173">Because this computer is not used daily for Internet browsing or email, it is better protected from Internet attacks and threats.</span></span>
  
<span data-ttu-id="fd861-174">PAW をセットアップする方法については、「」を参照してください [https://aka.ms/cyberpaw](https://aka.ms/cyberpaw) 。</span><span class="sxs-lookup"><span data-stu-id="fd861-174">For instructions on how to set up a PAW, see [https://aka.ms/cyberpaw](https://aka.ms/cyberpaw).</span></span>

<span data-ttu-id="fd861-175">Azure AD テナントと管理者アカウントに対して Azure PIM を有効にする場合は、[PIM の構成手順](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd861-175">To enable Azure PIM for your Azure AD tenant and administrator accounts, see the [steps to configure PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>

<span data-ttu-id="fd861-176">サイバー攻撃者から特権アクセスをセキュリティで保護する包括的なロードマップを作成する場合は、「[Azure AD でのハイブリッドおよびクラウド デプロイ用の特権アクセスをセキュリティで保護する](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd861-176">To develop a comprehensive roadmap to secure privileged access against cyber attackers, see [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span></span>

### <a name="azure-ad-privileged-identity-management"></a><span data-ttu-id="fd861-177">Azure AD Privileged Identity Management</span><span class="sxs-lookup"><span data-stu-id="fd861-177">Azure AD Privileged Identity Management</span></span>

<span data-ttu-id="fd861-178">グローバル管理者アカウントにグローバル管理者の役割を永続的に割り当てるのではなく、Azure AD Privileged Identity Management (PIM) を使用して、必要に応じて、グローバル管理者の役割をオンデマンドで一度だけ割り当てられるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="fd861-178">Rather than having your global administrator accounts be permanently assigned the global administrator role, you can use Azure AD Privileged Identity Management (PIM) to enable on-demand, just-in-time assignment of the global administrator role when it is needed.</span></span>
  
<span data-ttu-id="fd861-179">グローバル管理者アカウントは、永続的な管理者から適格な管理者に移動します。</span><span class="sxs-lookup"><span data-stu-id="fd861-179">Your global administrator accounts go from being permanent admins to eligible admins.</span></span> <span data-ttu-id="fd861-180">グローバル管理者の役割は、ユーザーが必要とするまで非アクティブです。</span><span class="sxs-lookup"><span data-stu-id="fd861-180">The global administrator role is inactive until someone needs it.</span></span> <span data-ttu-id="fd861-181">次に、アクティブ化プロセスを完了して、グローバル管理者の役割を、あらかじめ決められた時間だけグローバル管理者アカウントに追加します。</span><span class="sxs-lookup"><span data-stu-id="fd861-181">You then complete an activation process to add the global administrator role to the global administrator account for a predetermined amount of time.</span></span> <span data-ttu-id="fd861-182">時間が経過すると、PIM はグローバル管理者アカウントから全体管理者の役割を削除します。</span><span class="sxs-lookup"><span data-stu-id="fd861-182">When the time expires, PIM removes the global administrator role from the global administrator account.</span></span>
  
<span data-ttu-id="fd861-183">PIM を使用すると、このプロセスによって、グローバル管理者アカウントが悪意のあるユーザーの攻撃および使用に対して脆弱になる時間が大幅に短縮されます。</span><span class="sxs-lookup"><span data-stu-id="fd861-183">Using PIM and this process significantly reduces the amount of time that your global administrator accounts are vulnerable to attack and use by malicious users.</span></span>

<span data-ttu-id="fd861-184">PIM は、Microsoft 365 E5 に含まれている Azure Active Directory Premium P2 で使用できます。</span><span class="sxs-lookup"><span data-stu-id="fd861-184">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 E5.</span></span> <span data-ttu-id="fd861-185">または、管理者アカウントの Azure Active Directory Premium P2 ライセンスを個別に購入できます。</span><span class="sxs-lookup"><span data-stu-id="fd861-185">Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your administrator accounts.</span></span>
  
<span data-ttu-id="fd861-186">詳細については、「 [AZURE AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd861-186">For more information, see [Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>
  

### <a name="privileged-access-management"></a><span data-ttu-id="fd861-187">特権アクセス管理</span><span class="sxs-lookup"><span data-stu-id="fd861-187">Privileged access management</span></span>

<span data-ttu-id="fd861-p121">特権アクセス管理は、テナントでのタスクベースのアクティビティに対して Just-In-Time アクセスを指定するポリシーを構成することで有効になります。これは、機密性の高いデータへの継続的なアクセスや重要な構成設定へのアクセスに、既存の特権管理者アカウントが使用される可能性のある侵害から組織を保護するために役立ちます。たとえば、テナント内の組織のメールボックス設定にアクセスして変更する際には、明示的な承認が必要になる特権アクセス管理ポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="fd861-p121">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your tenant. It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings. For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your tenant.</span></span>

<span data-ttu-id="fd861-p122">この手順では、テナントの特権アクセス管理を有効にして、組織のデータおよび構成設定へのタスクベースのアクセスに対するセキュリティを強化する特権アクセスポリシーを構成します。組織の特権アクセスは、次の 3 つの基本的な手順で開始します。</span><span class="sxs-lookup"><span data-stu-id="fd861-p122">In this step, you'll enable privileged access management in your tenant and configure privileged access policies that provide additional security for task-based access to data and configuration settings for your organization. There are three basic steps to get started with privileged access in your organization:</span></span>

- <span data-ttu-id="fd861-193">承認者のグループを作成する</span><span class="sxs-lookup"><span data-stu-id="fd861-193">Creating an approver's group</span></span>
- <span data-ttu-id="fd861-194">特権アクセスを有効にする</span><span class="sxs-lookup"><span data-stu-id="fd861-194">Enabling privileged access</span></span>
- <span data-ttu-id="fd861-195">承認ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="fd861-195">Creating approval policies</span></span>

<span data-ttu-id="fd861-196">特権アクセス管理を使用すると、組織はゼロに立った特権で運用し、そのような管理アクセスのために発生する脆弱性に対する防御層を提供することができます。</span><span class="sxs-lookup"><span data-stu-id="fd861-196">Privileged access management enables your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access.</span></span> <span data-ttu-id="fd861-197">特権アクセスには、関連付けられている承認ポリシーが定義されているタスクを実行するための承認が必要です。</span><span class="sxs-lookup"><span data-stu-id="fd861-197">Privileged access requires approvals for executing any task that has an associated approval policy defined.</span></span> <span data-ttu-id="fd861-198">承認ポリシーに含まれるタスクを実行する必要があるユーザーは、要求を行い、アクセス承認を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd861-198">Users needing to execute tasks included in the approval policy must request and be granted access approval.</span></span>

<span data-ttu-id="fd861-199">特権アクセス管理を有効にするには、「 [Configure privileged access management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd861-199">To enable privileged access management, see [Configure privileged access management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration).</span></span>

<span data-ttu-id="fd861-200">詳細については、「 [特権アクセス管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd861-200">For more information, see [Privileged access management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span></span>

### <a name="security-information-and-event-management-siem-software-for-microsoft-365-logging"></a><span data-ttu-id="fd861-201">Microsoft 365 ログのセキュリティ情報およびイベント管理 (SIEM) ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="fd861-201">Security information and event management (SIEM) software for Microsoft 365 logging</span></span>

<span data-ttu-id="fd861-202">サーバー上での SIEM ソフトウェア実行では、アプリケーションとネットワークハードウェアによって作成されたセキュリティ通知とイベントのリアルタイム分析を実行します。</span><span class="sxs-lookup"><span data-stu-id="fd861-202">SIEM software run on a server performs real-time analysis of security alerts and events created by applications and network hardware.</span></span> <span data-ttu-id="fd861-203">SIEM サーバーに Microsoft 365 のセキュリティの警告とイベントを分析およびレポート機能に含めることができるようにするには、Azure AD をお客様の SEIM に統合します。</span><span class="sxs-lookup"><span data-stu-id="fd861-203">To allow your SIEM server to include Microsoft 365 security alerts and events in its analysis and reporting functions, integrate Azure AD into you SEIM.</span></span> <span data-ttu-id="fd861-204">「 [Azure ログ統合の概要」を](https://docs.microsoft.com/azure/security/security-azure-log-integration-overview)参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd861-204">See [Introduction to Azure Log Integration](https://docs.microsoft.com/azure/security/security-azure-log-integration-overview).</span></span>

## <a name="next-step"></a><span data-ttu-id="fd861-205">次のステップ</span><span class="sxs-lookup"><span data-stu-id="fd861-205">Next step</span></span>

<span data-ttu-id="fd861-206">Microsoft 365 サブスクリプションの id を設定している場合は、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd861-206">If you're setting up identity for your Microsoft 365 subscription, see:</span></span>

- <span data-ttu-id="fd861-207">クラウドのみの id を使用している場合は、[クラウドのみの id](cloud-only-identities.md)</span><span class="sxs-lookup"><span data-stu-id="fd861-207">[Cloud-only identities](cloud-only-identities.md) if you're using cloud-only identity</span></span>
- <span data-ttu-id="fd861-208">ハイブリッド id を使用している場合[にディレクトリ同期を準備](prepare-for-directory-synchronization.md)する</span><span class="sxs-lookup"><span data-stu-id="fd861-208">[Prepare for directory synchronization](prepare-for-directory-synchronization.md) if you're using hybrid identity</span></span>

  
## <a name="see-also"></a><span data-ttu-id="fd861-209">関連項目</span><span class="sxs-lookup"><span data-stu-id="fd861-209">See also</span></span>

[<span data-ttu-id="fd861-210">Microsoft 365 セキュリティロードマップ</span><span class="sxs-lookup"><span data-stu-id="fd861-210">Microsoft 365 security roadmap</span></span>](https://docs.microsoft.com/office365/securitycompliance/security-roadmap)
