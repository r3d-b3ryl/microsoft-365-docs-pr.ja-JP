---
title: '手順 3: ハイブリッド ID の構成'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: ID オプションを理解し、Azure AD Connect を構成して、オンプレミス Active Directory Domain Services (AD DS) が Azure AD と同期するようにします。
ms.openlocfilehash: ff4fb889bcd45028be9555342d5fc19c8f5ff421
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2019
ms.locfileid: "36982008"
---
# <a name="step-3-configure-hybrid-identity"></a><span data-ttu-id="a065a-103">手順 3: ハイブリッド ID の構成</span><span class="sxs-lookup"><span data-stu-id="a065a-103">Step 3: Configure hybrid identity</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-sync"></a>
## <a name="synchronize-identities"></a><span data-ttu-id="a065a-104">ID を同期する</span><span class="sxs-lookup"><span data-stu-id="a065a-104">Synchronize identities</span></span>

<span data-ttu-id="a065a-105">*これはハイブリッド環境で必須であり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="a065a-105">*This is required for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="a065a-106">このセクションでは、オンプレミス Active Directory Domain Services (AD DS) を、Office 365、Microsoft Intune、および Microsoft 365 Enterprise に含まれるその他のクラウドベースのサービスで使用される Azure Active Directory (Azure AD) テナントに同期させます。</span><span class="sxs-lookup"><span data-stu-id="a065a-106">In this section, you'll synchronize your on-premises Active Directory Domain Services (AD DS) with the Azure Active Directory (Azure AD) tenant used by your Office 365 and Enterprise Mobility + Security (EMS) subscriptions.</span></span>

<span data-ttu-id="a065a-107">Azure AD Connect は、シングル フォレストまたはマルチフォレスト AD DS 環境の実際に必要な ID のみを、Azure AD テナントと同期できるようにする、サポートされている Microsoft ツールです。</span><span class="sxs-lookup"><span data-stu-id="a065a-107">Azure AD Connect is the supported Microsoft tool that guides you through synchronizing only the identities you really need from single or multi-forest AD DS environments to your Azure AD tenant.</span></span> <span data-ttu-id="a065a-108">次の図は、Azure AD Connect 同期に関する基本的なプロセスを示します。</span><span class="sxs-lookup"><span data-stu-id="a065a-108">The following figure shows the basic process for Azure AD Connect synchronization.</span></span>

![Azure AD Connect によるオンプレミス ディレクトリと Azure AD の同期方法](./media/identity-azure-ad-connect/azure-ad-connect.png)

1. <span data-ttu-id="a065a-110">サーバーで実行している Azure AD Connect は、アカウント、グループ、および連絡先の変更に関して AD DS にポーリングします。</span><span class="sxs-lookup"><span data-stu-id="a065a-110">Azure AD Connect running on a server polls AD DS for changes in accounts, groups, and contacts.</span></span>
2. <span data-ttu-id="a065a-111">Azure AD Connect はそれらの変更を Microsoft 365 サブスクリプションの Azure AD テナントに送信します。</span><span class="sxs-lookup"><span data-stu-id="a065a-111">Azure AD Connect sends those changes to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

<span data-ttu-id="a065a-p102">ハイブリッド ID ソリューションでは、最初に認証の要件を決定します。次にオプションを示します。</span><span class="sxs-lookup"><span data-stu-id="a065a-p102">The first decision in your hybrid identity solution is your authentication requirement. The following options are options:</span></span>

- <span data-ttu-id="a065a-p103">**管理認証**では、Azure AD はユーザー サインインの認証プロセスを処理します。管理認証方式は 2 種類あります。</span><span class="sxs-lookup"><span data-stu-id="a065a-p103">With **managed authentication**, Azure AD handles the authentication process for user sign-in. There are two methods for managed authentication:</span></span> 
    - <span data-ttu-id="a065a-116">**パスワード ハッシュ同期 (PHS)**: (一部のプレミアム機能で推奨または必須)</span><span class="sxs-lookup"><span data-stu-id="a065a-116">**Password Hash Sync (PHS)** [Recommended and required for some premium features].</span></span> <span data-ttu-id="a065a-117">Azure AD でオンプレミス ディレクトリ オブジェクトの認証を有効にする最も簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="a065a-117">This is the simplest way to enable authentication for on-premises directory objects in Azure AD.</span></span> <span data-ttu-id="a065a-118">Azure AD Connect は AD DS からハッシュ化されたパスワードを抽出し、パスワードに対し追加のセキュリティ処理を実行し、パスワードを Azure AD に保存します。</span><span class="sxs-lookup"><span data-stu-id="a065a-118">Azure AD Connect extracts the hashed password from AD DS, does extra security processing on the password, and saves it in Azure AD.</span></span> <span data-ttu-id="a065a-119">詳細については、「[Azure AD Connect 同期を使用したパスワード ハッシュ同期の実装](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a065a-119">For more information, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span></span>
    - <span data-ttu-id="a065a-120">**パススルー認証 (PTA)**: Azure AD ベース サービスのためのシンプルなパスワード検証ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="a065a-120">**Pass-through Authentication (PTA)** provides a simple password validation solution for Azure AD-based services.</span></span> <span data-ttu-id="a065a-121">PTA は 1 つ以上のオンプレミス サーバーで実行されているエージェントを使用して、オンプレミス AD DS に対し直接ユーザー認証を検証します。</span><span class="sxs-lookup"><span data-stu-id="a065a-121">PTA uses an agent running on one or more on-premises servers to validate the user authentications directly with your on-premises AD DS.</span></span> <span data-ttu-id="a065a-122">詳細については、「[Azure Active Directory パススルー認証によるユーザー サインイン](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a065a-122">For more information, see [User sign-in with Azure Active Directory Pass-through Authentication](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).</span></span>
- <span data-ttu-id="a065a-p106">**フェデレーション認証**では、ユーザーのサインインで、認証プロセスが ID フェデレーション サーバー (Active Directory フェデレーション サービス (AD FS) など) を介して別の ID プロバイダーにリダイレクトされます。ID プロバイダーは、その他の認証方式 (スマートカード ベースの認証など) を提供できます。詳細については、「[Azure Active Directory ハイブリッド ID ソリューションの適切な認証方法を選択する](https://docs.microsoft.com/azure/security/azure-ad-choose-authn)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a065a-p106">With **federated authentication**, the authentication process is redirected to another identity provider through an identity federation server, such as Active Directory Federation Services (AD FS), for a user’s sign-in. The identity provider can provide additional authentication methods, such as smartcard-based authentication. For more information, see [Choosing the right authentication method for your Azure Active Directory hybrid identity solution](https://docs.microsoft.com/azure/security/azure-ad-choose-authn).</span></span>

<span data-ttu-id="a065a-126">Microsoft 365 Enterprise の ID モデルと認証の概要については、このビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a065a-126">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

<span data-ttu-id="a065a-127">ハイブリッド ID ソリューションが決定したら、[IdFix Directory Synchronization Error Remediation Tool](https://www.microsoft.com/download/details.aspx?id=36832) をダウンロードして実行し、AD DS を分析して問題がないかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="a065a-127">After you've determined your hybrid identity solution, download and run the [IdFix Directory Synchronization Error Remediation Tool](https://www.microsoft.com/download/details.aspx?id=36832) to analyze your AD DS for issues.</span></span>

<span data-ttu-id="a065a-128">IdFix ツールで検出されたすべての問題を解決したら、Azure AD Connect ツールのインストール、および Microsoft 365 サブスクリプションのオンプレミス AD DS と Azure AD テナント間のディレクトリ同期の構成に関するガイダンスとして「[パスワード ハッシュ同期の実装](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a065a-128">After resolving all of the issues identified by the IdFix tool, see [Implement password hash synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization) for guidance on installing the Azure AD Connect tool and configuring directory synchronization between your on-premises AD DS and the Azure AD tenant for your Office 365 and EMS subscriptions.</span></span> <span data-ttu-id="a065a-129">同期開始後は、オンプレミス ID プロバイダー (AD DS など) でユーザー アカウントとグループを維持できます。</span><span class="sxs-lookup"><span data-stu-id="a065a-129">After synchronization starts, you'll maintain your user accounts and groups with your on-premises identity provider, such as AD DS.</span></span>

<span data-ttu-id="a065a-130">Microsoft では、セキュアで生産性の高い労働力を確保するために [ID とデバイスのアクセス](microsoft-365-policies-configurations.md)に関する一連の推奨事項を提供しています。</span><span class="sxs-lookup"><span data-stu-id="a065a-130">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> 

- <span data-ttu-id="a065a-131">ハイブリッド環境で推奨されている要件については、[前提条件](identity-access-prerequisites.md#prerequisites)の**パスワード ハッシュ同期を使用した Active Directory** をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a065a-131">For recommended requirements for hybrid environments, see the **Active Directory with password hash sync** column in [prerequisites](identity-access-prerequisites.md#prerequisites).</span></span> 

- <span data-ttu-id="a065a-132">クラウド専用環境で推奨されている要件については、[前提条件](identity-access-prerequisites.md#prerequisites)の**クラウドのみ**列をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a065a-132">For recommended requirements for cloud only environments, see the **Cloud only** column in [prerequisites](identity-access-prerequisites.md#prerequisites).</span></span>

<span data-ttu-id="a065a-133">Azure AD にオンプレミスのユーザーとグループが作成されると、 OneDrive for Business や Exchange Online などのライセンスの割り当てと、生産性ワークロードの使用を開始できます。</span><span class="sxs-lookup"><span data-stu-id="a065a-133">Once your on-premises users and groups are present in Azure AD, you can start assigning licenses and using Exchange Online.</span></span>

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="a065a-135">テスト ラボ ガイド: パスワード ハッシュ同期</span><span class="sxs-lookup"><span data-stu-id="a065a-135">Test Lab Guide: Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)<br> [<span data-ttu-id="a065a-136">テスト ラボ ガイド: パススルー認証</span><span class="sxs-lookup"><span data-stu-id="a065a-136">Test Lab Guide: Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md) |
|||

<span data-ttu-id="a065a-137">中間チェックポイントとして、このセクションに対応する[終了条件](identity-exit-criteria.md#crit-identity-sync)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="a065a-137">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync) corresponding to this section.</span></span>

<a name="identity-sync-health"></a>
## <a name="monitor-synchronization-health"></a><span data-ttu-id="a065a-138">同期の状態を監視する</span><span class="sxs-lookup"><span data-stu-id="a065a-138">Monitor synchronization health</span></span>

<span data-ttu-id="a065a-139">*この手順はオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="a065a-139">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="a065a-140">このセクションでは、Azure AD Connect Health エージェントを各オンプレミス AD DS ドメイン コントローラーにインストールして、Azure AD Connect によって提供されている ID インフラストラクチャと 同期サービスを監視します。</span><span class="sxs-lookup"><span data-stu-id="a065a-140">In this section, you'll install an Azure AD Connect Health agent on each of your on-premises identity servers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect.</span></span> <span data-ttu-id="a065a-141">監視情報は Azure AD Connect Health ポータルで使用可能になります。このポータルでは、アラート、パフォーマンス監視、使用状況分析などの情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="a065a-141">The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

![Azure AD Connect Health のコンポーネント](./media/identity-azure-ad-connect-health/identity-azure-ad-connect-health.png)

<span data-ttu-id="a065a-143">Azure AD Connect Health の使用法に関する重要な設計上の決定は、Azure AD Connect をどのように使用しているかに応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="a065a-143">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="a065a-144">**管理認証**オプションを使用している場合は、最初に「[Azure AD Connect Health を使用した Azure AD Connect の同期の監視](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync)」を参照し、Azure AD Connect Health について理解し、構成します。</span><span class="sxs-lookup"><span data-stu-id="a065a-144">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="a065a-145">Active Directory フェデレーション サービス (AD FS) で**フェデレーション認証**を使用してアカウントとグループの名前だけを同期している場合は、最初に「[Azure AD Connect Health を使用した AD FS の監視](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs)」を参照し Azure AD Connect Health について理解し、構成します。</span><span class="sxs-lookup"><span data-stu-id="a065a-145">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="a065a-146">このセクションの完了後の成果物は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a065a-146">When you complete this section, you’ll have:</span></span>

- <span data-ttu-id="a065a-147">Azure AD Connect Health エージェントがオンプレミス ID プロバイダー サーバーにインストールされている。</span><span class="sxs-lookup"><span data-stu-id="a065a-147">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="a065a-148">Azure AD Connect Health ポータルでは、Microsoft 365 サブスクリプションの Azure AD テナントでオンプレミス インフラストラクチャの現在の状態と同期アクティビティを表示しています。</span><span class="sxs-lookup"><span data-stu-id="a065a-148">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Office 365 and EMS subscriptions.</span></span>

<span data-ttu-id="a065a-149">中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-sync-health)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="a065a-149">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync-health) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="a065a-150">次の手順</span><span class="sxs-lookup"><span data-stu-id="a065a-150">Next step</span></span>

|||
|:-------|:-----|
![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="a065a-151">セキュリティで保護されたユーザー認証を構成する</span><span class="sxs-lookup"><span data-stu-id="a065a-151">Configure secure user authentication</span></span>](identity-multi-factor-authentication.md)
