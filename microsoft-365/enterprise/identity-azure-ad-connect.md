---
title: '手順 7: ID を同期する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/09/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: ID オプションを理解し、オンプレミス Windows Server AD を Azure AD と同期するように Azure AD Connect を構成します。
ms.openlocfilehash: 2391ee11a1706bbbfdeb248c5967822d3ea68f72
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869073"
---
# <a name="step-7-synchronize-identities"></a><span data-ttu-id="d21be-103">手順 7: ID を同期する</span><span class="sxs-lookup"><span data-stu-id="d21be-103">Step 2: Synchronize identities</span></span>

<span data-ttu-id="d21be-104">*この手順はハイブリッド環境で必須であり、Microsoft 365 Enterprise のバージョン E3 および E5 に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="d21be-104">*This step is required for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="d21be-105">この手順では、オンプレミス Windows Server Active Directory (AD) と、Office 365 および Enterprise Mobility + Security (EMS) のサブスクリプションで使用される Azure Active Directory (AD) テナントを同期します。</span><span class="sxs-lookup"><span data-stu-id="d21be-105">In Step 2, you'll synchronize your on-premises Windows Server Active Directory (AD) with the Azure Active Directory (AD) tenant used by your Office 365 and Enterprise Mobility + Security (EMS) subscriptions.</span></span>

<span data-ttu-id="d21be-106">Azure AD Connect は、シングル フォレストまたはマルチフォレスト Windows Server AD 環境の実際に必要な ID のみを、Azure AD テナントと同期できるようにする、サポートされている Microsoft ツールです。</span><span class="sxs-lookup"><span data-stu-id="d21be-106">Azure AD Connect is the supported Microsoft tool that guides you through synchronizing only the identities you really need from single or multi-forest Windows Server AD environments to your Azure AD tenant.</span></span>

![Azure AD Connect によるオンプレミス ディレクトリと Azure AD の同期方法](./media/identity-azure-ad-connect/azure-ad-connect.png)

<span data-ttu-id="d21be-108">*Azure AD Connect によるオンプレミス ディレクトリと Azure AD の同期方法*</span><span class="sxs-lookup"><span data-stu-id="d21be-108">*How Azure AD Connect synchronizes your on-premises directory with Azure AD*</span></span>

<span data-ttu-id="d21be-p101">ハイブリッド ID ソリューションでは、最初に認証の要件を決定します。次にオプションを示します。</span><span class="sxs-lookup"><span data-stu-id="d21be-p101">The first decision in your hybrid identity solution is your authentication requirement. The following options are options:</span></span>

- <span data-ttu-id="d21be-p102">**管理認証**では、Azure AD はユーザー サインインの認証プロセスを処理します。管理認証方式は 2 種類あります。</span><span class="sxs-lookup"><span data-stu-id="d21be-p102">With **managed authentication**, Azure AD handles the authentication process for user sign-in. There are two methods for managed authentication:</span></span> 
    - <span data-ttu-id="d21be-p103">**パスワード ハッシュ同期 (PHS)**: (一部のプレミアム機能で推奨または必須) Azure AD でオンプレミス ディレクトリ オブジェクトの認証を有効にする最も簡単な方法です。Azure AD Connect は Windows Server AD からハッシュ化されたパスワードを抽出し、パスワードに対し追加のセキュリティ処理を実行し、パスワードを Azure AD に保存します。詳細については、「[Azure AD Connect 同期を使用したパスワード ハッシュ同期の実装](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d21be-p103">**Password Hash Sync (PHS)** [Recommended and required for some premium features]. This is the simplest way to enable authentication for on-premises directory objects in Azure AD. Azure AD Connect extracts the hashed password from Active Directory, does extra security processing on the password, and saves it in Azure AD. For more information, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization).</span></span>
    - <span data-ttu-id="d21be-p104">**パススルー認証 (PTA)**: Azure AD ベース サービスのためのシンプルなパスワード検証ソリューションです。PTA は 1 つ以上のオンプレミス サーバーで実行されているエージェントを使用して、オンプレミス Windows Server AD に対し直接ユーザー認証を検証します。詳細については、「[Azure Active Directory パススルー認証によるユーザー サインイン](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d21be-p104">**Pass-through Authentication (PTA)** provides a simple password validation solution for Azure AD-based services. PTA uses an agent running on one or more on-premises servers to validate the user authentications directly with your on-premises Windows Server AD. For more information, see [User sign-in with Azure Active Directory Pass-through Authentication](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).</span></span>
- <span data-ttu-id="d21be-p105">**フェデレーション認証**では、ユーザーのサインインで、認証プロセスが ID フェデレーション サーバー (Active Directory フェデレーション サービス (AD FS) など) を介して別の ID プロバイダーにリダイレクトされます。ID プロバイダーは、その他の認証方式 (スマートカード ベースの認証など) を提供できます。詳細については、「[Azure Active Directory ハイブリッド ID ソリューションの適切な認証方法を選択する](https://docs.microsoft.com/azure/security/azure-ad-choose-authn)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d21be-p105">With **federated authentication**, the authentication process is redirected to another identity provider through an identity federation server, such as Active Directory Federation Services (AD FS), for a user’s sign-in. The identity provider can provide additional authentication methods, such as smartcard-based authentication. For more information, see [Choosing the right authentication method for your Azure Active Directory hybrid identity solution](https://docs.microsoft.com/azure/security/azure-ad-choose-authn).</span></span>

<span data-ttu-id="d21be-123">ハイブリッド ID ソリューションが決定したら、[IdFix Directory Synchronization Error Remediation Tool](https://www.microsoft.com/download/details.aspx?id=36832) をダウンロードして実行し、Windows Server AD を分析して問題がないかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="d21be-123">After you've determined your hybrid identity solution, download and run the [IdFix Directory Synchronization Error Remediation Tool](https://www.microsoft.com/download/details.aspx?id=36832) to analyze your Windows Server AD for issues.</span></span>

<span data-ttu-id="d21be-p106">IdFix ツールで検出されたすべての問題を解決したら、「[パスワード ハッシュ同期を実装する](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization)」を参照し、Azure AD Connect ツールのインストールと、Office 365 および EMS サブスクリプションのオンプレミス Windows Server AD と Azure AD テナント間のディレクトリ同期の構成について確認してください。同期開始後は、オンプレミス ID プロバイダー (Windows Server AD など) でユーザー アカウントとグループを維持できます。</span><span class="sxs-lookup"><span data-stu-id="d21be-p106">After resolving all of the issues identified by the IdFix tool, see [Implement password hash synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization) for guidance on installing the Azure AD Connect tool and configuring directory synchronization between your on-premises Windows Server AD and the Azure AD tenant for your Office 365 and EMS subscriptions. After synchronization starts, you'll maintain your user accounts and groups with your on-premises identity provider, such as Windows Server AD.</span></span>

<span data-ttu-id="d21be-126">Microsoft では、セキュアで生産性の高い労働力を確保するために [ID とデバイスのアクセス](microsoft-365-policies-configurations.md)に関する一連の推奨事項を提供しています。</span><span class="sxs-lookup"><span data-stu-id="d21be-126">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> 
- <span data-ttu-id="d21be-127">ハイブリッド環境で推奨されている要件については、[前提条件](identity-access-prerequisites.md#prerequisites)の**パスワード ハッシュ同期を使用した Active Directory** をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d21be-127">For recommended requirements for hybrid environments, see the **Active Directory with password hash sync** column in [prerequisites](identity-access-prerequisites.md#prerequisites).</span></span> 

- <span data-ttu-id="d21be-128">クラウド専用環境で推奨されている要件については、[前提条件](identity-access-prerequisites.md#prerequisites)の**クラウドのみ**列をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d21be-128">For recommended requirements for cloud only environments, see the **Cloud only** column in [prerequisites](identity-access-prerequisites.md#prerequisites).</span></span>

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="d21be-130">テスト ラボ ガイド: パスワード ハッシュ同期</span><span class="sxs-lookup"><span data-stu-id="d21be-130">Test Lab Guide: Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)<br> [<span data-ttu-id="d21be-131">テスト ラボ ガイド: パススルー認証</span><span class="sxs-lookup"><span data-stu-id="d21be-131">Test Lab Guide: Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md) |
|||

<span data-ttu-id="d21be-132">中間チェックポイントとして、この手順に対応する[終了条件](identity-exit-criteria.md#crit-identity-sync)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="d21be-132">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="d21be-133">次の手順</span><span class="sxs-lookup"><span data-stu-id="d21be-133">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step8.png)| [<span data-ttu-id="d21be-134">同期の状態を監視する</span><span class="sxs-lookup"><span data-stu-id="d21be-134">Monitor synchronization health</span></span>](identity-azure-ad-connect-health.md) |

