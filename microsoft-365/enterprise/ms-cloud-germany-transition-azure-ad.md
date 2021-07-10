---
title: Microsoft Cloud deutschland Azure Active Directory移行に関する追加情報
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/15/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: '概要: Azure Active Directory Microsoft Cloud Germany (Microsoft Cloud Deutschland) から新しいドイツのデータセンター地域Office 365サービスに移行する際の追加情報。'
ms.openlocfilehash: 0e7abd68945a9b685a33c120ff1e92fda62b2c56
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362728"
---
# <a name="additional-azure-active-directory-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="5de43-103">Microsoft Cloud deutschland Azure Active Directory移行に関する追加情報</span><span class="sxs-lookup"><span data-stu-id="5de43-103">Additional Azure Active Directory information for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="5de43-104">Azure German クラウドから Azure パブリック クラウドへの移行を完了するには、OpenID Connect (OIDC) エンドポイントが商用クラウド エンドポイントの報告を開始するときに、アプリケーションの認証エンドポイント、Azure Active Directory (Azure AD) Graph、および MS Graph エンドポイントを商用クラウドのエンドポイントに更新することをお勧めします。 `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration`</span><span class="sxs-lookup"><span data-stu-id="5de43-104">To complete the move from the Azure German cloud to the Azure public cloud we recommend that the authentication endpoint, Azure Active Directory (Azure AD) Graph, and MS Graph endpoints for your applications be updated to those of the commercial cloud when the OpenID Connect (OIDC) endpoint, `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration`, starts reporting commercial cloud endpoints.</span></span> 
 
<span data-ttu-id="5de43-105">**いつこの変更を行う必要がありますか?**</span><span class="sxs-lookup"><span data-stu-id="5de43-105">**When should I make this change?**</span></span>

<span data-ttu-id="5de43-106">テナントがドイツのクラウドから商用クラウドへの移行を完了すると、Azure/Office ポータルで通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="5de43-106">You'll receive a notification in Azure/Office portal when your tenant completes migration from German cloud to the commercial cloud.</span></span> <span data-ttu-id="5de43-107">これらの更新プログラムを完了するには、この通知を受信して 30 日後に、Azure Germany クラウドから Azure Public cloud に移行されたテナントでアプリが引き続き動作するようにします。</span><span class="sxs-lookup"><span data-stu-id="5de43-107">You have 30 days after receiving this notification to complete these updates so that your app continues to work for tenants that are migrated from Azure Germany cloud to Azure Public cloud.</span></span>
 
<span data-ttu-id="5de43-108">サインイン機関の更新には、次の 3 つの条件があります。</span><span class="sxs-lookup"><span data-stu-id="5de43-108">There are three preconditions to updating your sign-in authority:</span></span>

 - <span data-ttu-id="5de43-109">テナントの OIDC 検出エンドポイントは `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` 、Azure ADパブリック クラウド エンドポイントを返します。</span><span class="sxs-lookup"><span data-stu-id="5de43-109">OIDC discovery endpoint for your tenant `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` returns Azure AD public cloud endpoints.</span></span>

 - <span data-ttu-id="5de43-110">テナントがフェデレーション用に設定されている場合は、Active Directory フェデレーション サービス (AD FS) が更新され、Azure ADパブリックと同期されます。</span><span class="sxs-lookup"><span data-stu-id="5de43-110">If your tenant is set up for federation, Active Directory Federation Services (AD FS) is updated to sync with Azure AD Public.</span></span> <span data-ttu-id="5de43-111">この変更を行う手順に従って Azure AD Connect設定を更新できます。</span><span class="sxs-lookup"><span data-stu-id="5de43-111">You can follow instructions to update Azure AD Connect settings for making this change.</span></span>

 - <span data-ttu-id="5de43-112">アプリケーションで使用されているリソース アプリケーションがある場合は、Azure AD および Azure AD Public の両方によって署名されたトークンを受け入ADされます。</span><span class="sxs-lookup"><span data-stu-id="5de43-112">Resource applications, if any, used by your applications are modified to accept tokens that are signed by both Azure AD Germany and Azure AD Public.</span></span>
 
<span data-ttu-id="5de43-113">**どのような種類のアプリケーションですか?**</span><span class="sxs-lookup"><span data-stu-id="5de43-113">**What kind of applications?**</span></span>

<span data-ttu-id="5de43-114">アプリケーションには、次に示す任意のアプリケーションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="5de43-114">An application could be any of the following:</span></span>

- [<span data-ttu-id="5de43-115">シングル ページ アプリ (SPA)</span><span class="sxs-lookup"><span data-stu-id="5de43-115">Single-page app (SPA)</span></span>](/azure/active-directory/develop/scenario-spa-overview)
- [<span data-ttu-id="5de43-116">ユーザーにサインインする Web アプリ</span><span class="sxs-lookup"><span data-stu-id="5de43-116">Web app that signs in users</span></span>](/azure/active-directory/develop/scenario-web-app-sign-user-overview)
- [<span data-ttu-id="5de43-117">Web API を呼び出す Web アプリ</span><span class="sxs-lookup"><span data-stu-id="5de43-117">Web app that calls web APIs</span></span>](/azure/active-directory/develop/scenario-web-app-call-api-overview)
- [<span data-ttu-id="5de43-118">保護された Web API</span><span class="sxs-lookup"><span data-stu-id="5de43-118">Protected web API</span></span>](/azure/active-directory/develop/scenario-protected-web-api-overview)
- [<span data-ttu-id="5de43-119">Web API を呼び出す Web API</span><span class="sxs-lookup"><span data-stu-id="5de43-119">Web API that calls web APIs</span></span>](/azure/active-directory/develop/scenario-web-api-call-api-overview)
- [<span data-ttu-id="5de43-120">デスクトップ アプリ</span><span class="sxs-lookup"><span data-stu-id="5de43-120">Desktop app</span></span>](/azure/active-directory/develop/scenario-desktop-overview)
- [<span data-ttu-id="5de43-121">Daemon アプリ</span><span class="sxs-lookup"><span data-stu-id="5de43-121">Daemon app</span></span>](/azure/active-directory/develop/scenario-daemon-overview)
- [<span data-ttu-id="5de43-122">モバイル アプリ</span><span class="sxs-lookup"><span data-stu-id="5de43-122">Mobile app</span></span>](/azure/active-directory/develop/scenario-mobile-overview)
 
> [!NOTE] 
> <span data-ttu-id="5de43-123">アプリケーションが権限として使用に `login.microsoftonline.com` 切り替えた場合、トークンはこの新しい機関によって署名されます。</span><span class="sxs-lookup"><span data-stu-id="5de43-123">When an application switches to using `login.microsoftonline.com` as your authority, the tokens will be signed by this new authority.</span></span> <span data-ttu-id="5de43-124">他のアプリが呼び出すリソース アプリケーションをホストする場合は、時間の少ないトークンの検証を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5de43-124">If you host any resource applications that other apps call into, you will need to allow for lax token validation.</span></span> <span data-ttu-id="5de43-125">つまり、アプリは、Azure とドイツと Azure の両方のパブリック クラウドADトークンAD必要があります。</span><span class="sxs-lookup"><span data-stu-id="5de43-125">This means that your app needs to allow tokens that are signed by both the Azure AD Germany and Azure AD public clouds.</span></span> <span data-ttu-id="5de43-126">この時間の少ないトークン検証は、サービスを呼び出すすべてのクライアント アプリケーションがパブリック クラウドの Azure ADされるまで必要です。</span><span class="sxs-lookup"><span data-stu-id="5de43-126">This lax token validation is needed until all client applications that call your service are fully migrated to the Azure AD public cloud.</span></span> <span data-ttu-id="5de43-127">移行後、リソース アプリケーションは、Azure によって署名されたトークンをパブリック クラウドAD受け入れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5de43-127">After migration, your resource application only needs to accept tokens signed by the Azure AD public cloud.</span></span>

<span data-ttu-id="5de43-128">**更新する必要があるもの**</span><span class="sxs-lookup"><span data-stu-id="5de43-128">**What do I need to update?**</span></span>

1. <span data-ttu-id="5de43-129">Azure Germany または Office 365 ドイツ のユーザーの認証に使用されるアプリケーションを Azure Germany でホストしている場合は、認証コンテキストの機関として使用してください `https://login.microsoftonline.com` 。</span><span class="sxs-lookup"><span data-stu-id="5de43-129">If you're hosting an application in Azure Germany that is used to authenticate Azure Germany or Office 365 Germany users, ensure that `https://login.microsoftonline.com` is used as the authority in the authentication context.</span></span>

    - <span data-ttu-id="5de43-130">「Azure AD認証コンテキスト」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5de43-130">See Azure AD authentication contexts.</span></span>
    - <span data-ttu-id="5de43-131">これは、アプリケーションの認証と、アプリケーションが呼び出す可能性がある任意の API (Microsoft Graph、Azure AD Graph、Azure Resource Manager) への認証の両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="5de43-131">This applies both to authentication to your application as well as authentication to any APIs that your application may be calling (that is, Microsoft Graph, Azure AD Graph, Azure Resource Manager).</span></span>

2. <span data-ttu-id="5de43-132">Azure AD Graphエンドポイントを更新します `https://graph.windows.net` 。</span><span class="sxs-lookup"><span data-stu-id="5de43-132">Update Azure AD Graph endpoint to be `https://graph.windows.net`.</span></span>

3. <span data-ttu-id="5de43-133">MS Graphエンドポイントを更新します `https://graph.microsoft.com` 。</span><span class="sxs-lookup"><span data-stu-id="5de43-133">Update MS Graph endpoint to be `https://graph.microsoft.com`.</span></span>

4. <span data-ttu-id="5de43-134">アプリケーションがパブリック クラウドとして使用するドイツのクラウド エンドポイント (Exchange Online および SharePoint Online 用など) を更新します。</span><span class="sxs-lookup"><span data-stu-id="5de43-134">Update any German cloud endpoints (such as those for Exchange Online and SharePoint Online) that are used by your applications to be those of the public cloud.</span></span>

5. <span data-ttu-id="5de43-135">管理ツールとスクリプトの `AzurePublic` 環境パラメーターを (代わりに) 更新 `AzureGermany` します。</span><span class="sxs-lookup"><span data-stu-id="5de43-135">Update environment parameters to be `AzurePublic` (instead of `AzureGermany`) in administrative tools and scripts for:</span></span>

    - [<span data-ttu-id="5de43-136">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="5de43-136">Azure PowerShell</span></span>](/powershell/azure/install-az-ps)
    - [<span data-ttu-id="5de43-137">Azure AD PowerShell (MSOnline)</span><span class="sxs-lookup"><span data-stu-id="5de43-137">Azure AD PowerShell (MSOnline)</span></span>](/powershell/azure/active-directory/overview)
    - [<span data-ttu-id="5de43-138">Azure AD PowerShell (AzureAD)</span><span class="sxs-lookup"><span data-stu-id="5de43-138">Azure AD PowerShell (AzureAD)</span></span>](/powershell/azure/active-directory/install-adv2)
    - [<span data-ttu-id="5de43-139">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="5de43-139">Azure CLI</span></span>](/cli/azure/install-azure-cli)
 
<span data-ttu-id="5de43-140">**発行するアプリケーションについて**</span><span class="sxs-lookup"><span data-stu-id="5de43-140">**What about applications that I publish?**</span></span>

<span data-ttu-id="5de43-141">テナント外のユーザーが利用できるアプリケーションを発行する場合は、継続性を確保するためにアプリケーションの登録を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5de43-141">If you publish an application that is available to users who are outside of your tenant, you may need to change your application registration to ensure continuity.</span></span> <span data-ttu-id="5de43-142">アプリケーションを使用する他のテナントは、テナントとは異なる時刻に移動される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5de43-142">Other tenants that use your application may be moved at a different time than your tenant.</span></span> <span data-ttu-id="5de43-143">アプリケーションへのアクセスが失われるのを確実に行わないには、アプリが Azure Germany から Azure Public に同期されている状態に同意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5de43-143">To ensure that they never lose access to your application, you'll need to consent to your app being synchronized from Azure Germany to Azure public.</span></span>

<span data-ttu-id="5de43-144">**移行中に新しいマルチテナント アプリケーションを追加する方法は?**</span><span class="sxs-lookup"><span data-stu-id="5de43-144">**What about adding new multi-tenant applications during migration?**</span></span>

<span data-ttu-id="5de43-145">別の組織 (マルチテナント アプリケーション) によって発行された新しいアプリケーションを使用する場合は、移行プロセス (フェーズ 2 ~ フェーズ 9) 中にアプリケーションの追加を制限されます。</span><span class="sxs-lookup"><span data-stu-id="5de43-145">If you want to consume a new application that is published by another organization (multi-tenant application) you will be restricted from adding that application during the migration process (phases 2 through phase 9).</span></span>  <span data-ttu-id="5de43-146">組織がフェーズ 9 を完了し、Azure パブリック インスタンスに完全に移行するときに、このタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="5de43-146">You may execute this task when your organization completes phase 9 and is fully transitioned to the Azure public instance.</span></span>

## <a name="additional-considerations"></a><span data-ttu-id="5de43-147">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="5de43-147">Additional considerations</span></span>

<span data-ttu-id="5de43-148">Azure の追加の考慮事項を次に示AD。</span><span class="sxs-lookup"><span data-stu-id="5de43-148">Here are some additional considerations for Azure AD:</span></span>

- <span data-ttu-id="5de43-149">フェデレーション認証の場合:</span><span class="sxs-lookup"><span data-stu-id="5de43-149">For federated authentication:</span></span>

  - <span data-ttu-id="5de43-150">テナント移行の実行中は、フェデレーション ドメインを作成、昇格、または降格できません。</span><span class="sxs-lookup"><span data-stu-id="5de43-150">You must not create, promote, or demote a federated domain while the tenant transition is in process.</span></span> <span data-ttu-id="5de43-151">Azure AD サービスへの移行が完了した後 (テナントが完全に完了)、フェデレーション ドメインの管理を再開できます。</span><span class="sxs-lookup"><span data-stu-id="5de43-151">After the migration to the Azure AD service is complete (the tenant is fully complete), you can resume managing federated domains.</span></span>

  - <span data-ttu-id="5de43-152">Active Directory フェデレーション サービス (AD FS) でフェデレーション認証を使用している場合は、移行中にオンプレミスの Active Directory ドメイン サービス (AD DS) ですべての認証に使用される発行者 URI を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5de43-152">If you're using federated authentication with Active Directory Federation Services (AD FS), you shouldn't make changes to Issuer URIs used for all authentication with your on-premises Active Directory Domain Services (AD DS) during migration.</span></span> <span data-ttu-id="5de43-153">発行者 URI を変更すると、ドメイン内のユーザーの認証エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="5de43-153">Changing issuer URIs will lead to authentication failures for users in the domain.</span></span> <span data-ttu-id="5de43-154">発行者 URI は、FS またはドメインAD管理からフェデレーションに変換される場合、またはその逆に直接変更できます。</span><span class="sxs-lookup"><span data-stu-id="5de43-154">Issuer URIs can be changed directly in AD FS or when a domain is converted from managed to federated and vice versa.</span></span> <span data-ttu-id="5de43-155">移行する Azure ドメインのフェデレーション ドメインを追加、削除、または変換AD推奨します。</span><span class="sxs-lookup"><span data-stu-id="5de43-155">Microsoft recommends customers don't add, remove, or convert a federated domain in the Azure AD tenant being migrated.</span></span> <span data-ttu-id="5de43-156">発行者 URI は、移行が完全に完了した後で変更できます。</span><span class="sxs-lookup"><span data-stu-id="5de43-156">Issuer URIs can be changed after the migration is fully complete.</span></span>

- <span data-ttu-id="5de43-157">ネットワークの場合:</span><span class="sxs-lookup"><span data-stu-id="5de43-157">For networking:</span></span>

  - <span data-ttu-id="5de43-158">IPv6 名前付きネットワークの作成は、Azure portal では機能しません `http://portal.microsoftazure.de/` 。</span><span class="sxs-lookup"><span data-stu-id="5de43-158">Creating IPv6-named networks doesn't work in the Azure portal, `http://portal.microsoftazure.de/`.</span></span> <span data-ttu-id="5de43-159">Azure portal を使用して `https://portal.azure.com` 、IPv6 名前付きネットワークを作成します。</span><span class="sxs-lookup"><span data-stu-id="5de43-159">Use the Azure portal at `https://portal.azure.com` to create IPv6-named networks.</span></span>
 
   - <span data-ttu-id="5de43-160">Microsoft Cloud Deutschland ポータルから Azure 多要素認証 (MFA) サービス設定の信頼できる IP アドレス範囲を作成できません。</span><span class="sxs-lookup"><span data-stu-id="5de43-160">You can't create trusted IP address ranges for Azure Multi-Factor Authentication (MFA) service settings from the Microsoft Cloud Deutschland portal.</span></span> <span data-ttu-id="5de43-161">Azure MFA の信頼AD IP アドレスOffice 365作成するには、Azure Office 365 ポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="5de43-161">Use the Azure AD portal for Office 365 services to create Azure MFA trusted IP address ranges.</span></span>


- <span data-ttu-id="5de43-162">条件付きアクセスの場合:</span><span class="sxs-lookup"><span data-stu-id="5de43-162">For Conditional Access:</span></span> 

  - <span data-ttu-id="5de43-163">次の付与制御を持つ条件付きアクセス ポリシーは、Office 365 サービスへの移行が完了するまでサポートされません[(Finalize Azure](ms-cloud-germany-transition.md#how-is-the-migration-organized) AD移行フェーズの後)。</span><span class="sxs-lookup"><span data-stu-id="5de43-163">Conditional Access policies with the following grant controls aren't supported until migration to Office 365 services is complete (after the [Finalize Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase):</span></span>

    - <span data-ttu-id="5de43-164">準拠デバイスを要求する</span><span class="sxs-lookup"><span data-stu-id="5de43-164">Require Compliant Device</span></span>
    - <span data-ttu-id="5de43-165">承認済みアプリを要求する</span><span class="sxs-lookup"><span data-stu-id="5de43-165">Require Approved App</span></span>
    - <span data-ttu-id="5de43-166">アプリ保護ポリシーを要求する</span><span class="sxs-lookup"><span data-stu-id="5de43-166">Require App Protection Policy</span></span>
    
  - <span data-ttu-id="5de43-167">条件付きアクセス ポリシー インターフェイスは、無効になっている場合でもテナントに対して有効になっているセキュリティの既定値に関する誤った警告を表示し、条件付きアクセス ポリシーはテナントに対して既に存在します。</span><span class="sxs-lookup"><span data-stu-id="5de43-167">The Conditional Access policy interface gives a false warning about security defaults being enabled for the tenant even when it's disabled, and Conditional Access policies already exist for the tenant.</span></span> <span data-ttu-id="5de43-168">警告を無視するか、サービス ポータルOffice 365条件付きアクセス ポリシーを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5de43-168">You should ignore the warning or use the Office 365 services portal to manage Conditional Access policies.</span></span> 

- <span data-ttu-id="5de43-169">Intune のシナリオは、テナントの移行が完了した後、すべての Office ワークロードの移行を含む、世界中のエンドポイントに対してのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="5de43-169">Intune scenarios are supported only against worldwide endpoints after tenant migration is complete, including all office workloads migrations.</span></span>

- <span data-ttu-id="5de43-170">MFA 要求にモバイル アプリ通知メソッドを使用する Microsoft Cloud Deutschland ユーザーには、Microsoft Authenticator アプリのユーザー プリンシパル名 (UPN) の代わりに、ユーザーの ObjectId (GUID) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5de43-170">Microsoft Cloud Deutschland users who use the Mobile App Notification method for MFA requests see the user's ObjectId (a GUID) instead of the user principal name (UPN) in the Microsoft Authenticator app.</span></span> <span data-ttu-id="5de43-171">Azure ADテナントの移行がAD Office 365サービスでホストされた後、新しいライセンス認証Microsoft Authenticatorユーザーの UPN が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5de43-171">After migration of the Azure AD tenant is complete and hosted in Office 365 services, new Microsoft Authenticator activations will display users' UPNs.</span></span> <span data-ttu-id="5de43-172">既存のMicrosoft Authenticatorユーザー ObjectId は引き続き表示されますが、モバイル アプリ通知では引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="5de43-172">Existing Microsoft Authenticator accounts will continue to display the user ObjectId, but they'll continue to work for mobile app notifications.</span></span> 

- <span data-ttu-id="5de43-173">2019 年 10 月 22 日以降に作成されたテナントの場合、Office 365 サービスに移行するときに、テナントのセキュリティの既定値が自動的に有効になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5de43-173">For tenants that are created after October 22, 2019, security defaults may be auto-enabled for the tenant when it's migrated to the Office 365 service.</span></span> <span data-ttu-id="5de43-174">テナント管理者は、セキュリティの既定値を有効のままにして MFA に登録するか、機能を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="5de43-174">Tenant admins can choose to leave security defaults enabled and register for MFA, or they can disable the feature.</span></span> <span data-ttu-id="5de43-175">詳細については、「セキュリティの既定値 [を無効にする」を参照してください](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="5de43-175">For more information, see [Disabling security defaults](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults).</span></span> 

  > [!NOTE]
  > <span data-ttu-id="5de43-176">移行中に自動有効化されていない組織は、セキュリティの既定値を有効にする機能が Office 365 サービスに展開される場合があります。</span><span class="sxs-lookup"><span data-stu-id="5de43-176">Organizations that are not auto-enabled during migration may still be auto-enrolled in the future as the feature to enable security defaults is rolled out in the Office 365 service.</span></span> <span data-ttu-id="5de43-177">セキュリティの既定値を明示的に無効または有効にした管理者は、[プロパティ] の下の機能を更新Azure Active Directory >**があります**。</span><span class="sxs-lookup"><span data-stu-id="5de43-177">Admins who choose to explicitly disable or enable security defaults may do so by updating the feature under **Azure Active Directory > Properties**.</span></span> <span data-ttu-id="5de43-178">管理者が機能を明示的に有効にした後は、自動的に有効になりません。</span><span class="sxs-lookup"><span data-stu-id="5de43-178">After the feature is explicitly enabled by the admin, it will not be auto-enabled.</span></span>

- <span data-ttu-id="5de43-179">テナントの移行が完了すると、Office 365 ドイツ のポータルと Office 365 ポータルの Azure AD Connect のバージョンに関する警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5de43-179">There will be warning about the version of Azure AD Connect in the Office 365 Germany portal as well as in the Office 365 portal once the tenant is in migration.</span></span> <span data-ttu-id="5de43-180">移行の完了後にバージョンの警告が警告を表示しなくなった場合は、これを無視できます。</span><span class="sxs-lookup"><span data-stu-id="5de43-180">This can be ignored if the version warning is no longer showing the warning after the migration is complete.</span></span> <span data-ttu-id="5de43-181">移行の前または移行後に、いずれかのポータルで警告が表示される場合は、Azure AD Connect更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5de43-181">If there's a warning, either before or after migration, in either portal, Azure AD Connect must be updated.</span></span> <span data-ttu-id="5de43-182">警告メッセージには、「古いディレクトリ同期ツールを使用しているのが検出されました。</span><span class="sxs-lookup"><span data-stu-id="5de43-182">The warning message says: "We detected you're using an outdated directory sync tool.</span></span> <span data-ttu-id="5de43-183">Microsoft ダウンロード センターにアクセスして、Azure の最新バージョンを取得することをお勧AD Connect。</span><span class="sxs-lookup"><span data-stu-id="5de43-183">We recommend you go to the Microsoft Download Center to get the latest version of Azure AD Connect."</span></span>

## <a name="more-information"></a><span data-ttu-id="5de43-184">詳細情報</span><span class="sxs-lookup"><span data-stu-id="5de43-184">More information</span></span>

<span data-ttu-id="5de43-185">はじめに:</span><span class="sxs-lookup"><span data-stu-id="5de43-185">Getting started:</span></span>

- [<span data-ttu-id="5de43-186">Microsoft Cloud Deutschland から新しいドイツのデータセンター地域Office 365サービスへの移行</span><span class="sxs-lookup"><span data-stu-id="5de43-186">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="5de43-187">Microsoft Cloud Deutschland 移行アシスタント</span><span class="sxs-lookup"><span data-stu-id="5de43-187">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="5de43-188">移行のオプトイン方法</span><span class="sxs-lookup"><span data-stu-id="5de43-188">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="5de43-189">移行中のカスタマー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="5de43-189">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="5de43-190">切り替えの移動:</span><span class="sxs-lookup"><span data-stu-id="5de43-190">Moving through the transition:</span></span>

- [<span data-ttu-id="5de43-191">移行フェーズのアクションと影響</span><span class="sxs-lookup"><span data-stu-id="5de43-191">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="5de43-192">その他の作業前</span><span class="sxs-lookup"><span data-stu-id="5de43-192">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="5de43-193">Azure [AD、デバイス](ms-cloud-germany-transition-add-devices.md)[、](ms-cloud-germany-transition-azure-ad.md)[エクスペリエンス](ms-cloud-germany-transition-add-experience.md)、および FS のAD[情報](ms-cloud-germany-transition-add-adfs.md)です。</span><span class="sxs-lookup"><span data-stu-id="5de43-193">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="5de43-194">クラウド アプリ:</span><span class="sxs-lookup"><span data-stu-id="5de43-194">Cloud apps:</span></span>

- [<span data-ttu-id="5de43-195">Dynamics 365 移行プログラム情報</span><span class="sxs-lookup"><span data-stu-id="5de43-195">Dynamics 365 migration program information</span></span>](/dynamics365/get-started/migrate-data-german-region)
- [<span data-ttu-id="5de43-196">Power BI 移行プログラム情報</span><span class="sxs-lookup"><span data-stu-id="5de43-196">Power BI migration program information</span></span>](/power-bi/admin/service-admin-migrate-data-germany)
- [<span data-ttu-id="5de43-197">Microsoft Teams へのアップグレードを開始する</span><span class="sxs-lookup"><span data-stu-id="5de43-197">Getting started with your Microsoft Teams upgrade</span></span>](/microsoftteams/upgrade-start-here)
