---
title: Microsoft Cloud Deutschland からの移行に関するその他の Azure Active Directory 情報
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
description: '概要: Microsoft Cloud Germany (Microsoft Cloud Deutschland) から新しいドイツデータセンター リージョンの Office 365 サービスに移行する場合の追加の Azure Active Directory 情報。'
ms.openlocfilehash: 4fc5dda95e5e7afc4d69141a9a4debd0a74c492b
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688801"
---
# <a name="additional-azure-active-directory-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="384eb-103">Microsoft Cloud Deutschland からの移行に関するその他の Azure Active Directory 情報</span><span class="sxs-lookup"><span data-stu-id="384eb-103">Additional Azure Active Directory information for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="384eb-104">Azure German クラウドから Azure パブリック クラウドへの移行を完了するには、OpenID Connect (OIDC) エンドポイントが商用クラウド エンドポイントのレポートを開始するときに、アプリケーションの認証エンドポイント、Azure Active Directory (Azure AD) Graph、および MS Graph エンドポイントを商用クラウドのエンドポイントに更新することをお勧めします。 `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration`</span><span class="sxs-lookup"><span data-stu-id="384eb-104">To complete the move from the Azure German cloud to the Azure public cloud we recommend that the authentication endpoint, Azure Active Directory (Azure AD) Graph, and MS Graph endpoints for your applications be updated to those of the commercial cloud when the OpenID Connect (OIDC) endpoint, `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration`, starts reporting commercial cloud endpoints.</span></span> 
 
<span data-ttu-id="384eb-105">**この変更は、いつ行う必要がありますか?**</span><span class="sxs-lookup"><span data-stu-id="384eb-105">**When should I make this change?**</span></span>

<span data-ttu-id="384eb-106">テナントがドイツのクラウドから商用クラウドへの移行を完了すると、Azure/Office ポータルで通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="384eb-106">You'll receive a notification in Azure/Office portal when your tenant completes migration from German cloud to the commercial cloud.</span></span> <span data-ttu-id="384eb-107">Azure Germany クラウドから Azure Public cloud に移行されたテナントでアプリが引き続き動作するように、これらの更新を完了するには、この通知を受信して 30 日後になります。</span><span class="sxs-lookup"><span data-stu-id="384eb-107">You have 30 days after receiving this notification to complete these updates so that your app continues to work for tenants that are migrated from Azure Germany cloud to Azure Public cloud.</span></span>
 
<span data-ttu-id="384eb-108">サインイン機関の更新には、次の 3 つの事前条件があります。</span><span class="sxs-lookup"><span data-stu-id="384eb-108">There are three preconditions to updating your sign-in authority:</span></span>

 - <span data-ttu-id="384eb-109">テナントの OIDC 検出エンドポイントは `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` 、Azure ADパブリック クラウド エンドポイントを返します。</span><span class="sxs-lookup"><span data-stu-id="384eb-109">OIDC discovery endpoint for your tenant `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` returns Azure AD public cloud endpoints.</span></span>

 - <span data-ttu-id="384eb-110">テナントがフェデレーション用に設定されている場合、Active Directory フェデレーション サービス (AD FS) が更新され、Azure AD Public と同期されます。</span><span class="sxs-lookup"><span data-stu-id="384eb-110">If your tenant is set up for federation, Active Directory Federation Services (AD FS) is updated to sync with Azure AD Public.</span></span> <span data-ttu-id="384eb-111">この変更を行う手順に従って、Azure AD Connect の設定を更新できます。</span><span class="sxs-lookup"><span data-stu-id="384eb-111">You can follow instructions to update Azure AD Connect settings for making this change.</span></span>

 - <span data-ttu-id="384eb-112">アプリケーションで使用されるリソース アプリケーションがある場合は、Azure AD Germany と Azure AD Public の両方によって署名されたトークンを受け入ADされます。</span><span class="sxs-lookup"><span data-stu-id="384eb-112">Resource applications, if any, used by your applications are modified to accept tokens that are signed by both Azure AD Germany and Azure AD Public.</span></span>
 
<span data-ttu-id="384eb-113">**どのような種類のアプリケーションですか?**</span><span class="sxs-lookup"><span data-stu-id="384eb-113">**What kind of applications?**</span></span>

<span data-ttu-id="384eb-114">アプリケーションには、次の種類があります。</span><span class="sxs-lookup"><span data-stu-id="384eb-114">An application could be any of the following:</span></span>

- [<span data-ttu-id="384eb-115">シングルページ アプリ (SPA)</span><span class="sxs-lookup"><span data-stu-id="384eb-115">Single-page app (SPA)</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-spa-overview)
- [<span data-ttu-id="384eb-116">ユーザーにサインインする Web アプリ</span><span class="sxs-lookup"><span data-stu-id="384eb-116">Web app that signs in users</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-app-sign-user-overview)
- [<span data-ttu-id="384eb-117">Web API を呼び出す Web アプリ</span><span class="sxs-lookup"><span data-stu-id="384eb-117">Web app that calls web APIs</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-app-call-api-overview)
- [<span data-ttu-id="384eb-118">保護された Web API</span><span class="sxs-lookup"><span data-stu-id="384eb-118">Protected web API</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-protected-web-api-overview)
- [<span data-ttu-id="384eb-119">Web API を呼び出す Web API</span><span class="sxs-lookup"><span data-stu-id="384eb-119">Web API that calls web APIs</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-api-call-api-overview)
- [<span data-ttu-id="384eb-120">デスクトップ アプリ</span><span class="sxs-lookup"><span data-stu-id="384eb-120">Desktop app</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-desktop-overview)
- [<span data-ttu-id="384eb-121">デーモン アプリ</span><span class="sxs-lookup"><span data-stu-id="384eb-121">Daemon app</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-daemon-overview)
- [<span data-ttu-id="384eb-122">モバイル アプリ</span><span class="sxs-lookup"><span data-stu-id="384eb-122">Mobile app</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-mobile-overview)
 
> [!NOTE] 
> <span data-ttu-id="384eb-123">アプリケーションが権限としての使用に切 `login.microsoftonline.com` り替えた場合、トークンはこの新しい機関によって署名されます。</span><span class="sxs-lookup"><span data-stu-id="384eb-123">When an application switches to using `login.microsoftonline.com` as your authority, the tokens will be signed by this new authority.</span></span> <span data-ttu-id="384eb-124">他のアプリが呼び出すリソース アプリケーションをホストする場合は、lax トークンの検証を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="384eb-124">If you host any resource applications that other apps call into, you will need to allow for lax token validation.</span></span> <span data-ttu-id="384eb-125">つまり、アプリは、Azure AD Germany と Azure ADパブリック クラウドの両方によって署名されたトークンを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="384eb-125">This means that your app needs to allow tokens that are signed by both the Azure AD Germany and Azure AD public clouds.</span></span> <span data-ttu-id="384eb-126">この時間不足トークンの検証は、サービスを呼び出すすべてのクライアント アプリケーションがパブリック クラウドの Azure ADされるまで必要です。</span><span class="sxs-lookup"><span data-stu-id="384eb-126">This lax token validation is needed until all client applications that call your service are fully migrated to the Azure AD public cloud.</span></span> <span data-ttu-id="384eb-127">移行後、リソース アプリケーションは、Azure によって署名されたトークンをパブリック クラウドAD受け入れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="384eb-127">After migration, your resource application only needs to accept tokens signed by the Azure AD public cloud.</span></span>

<span data-ttu-id="384eb-128">**更新する必要があるもの**</span><span class="sxs-lookup"><span data-stu-id="384eb-128">**What do I need to update?**</span></span>

1. <span data-ttu-id="384eb-129">Azure Germany または Office 365 Germany ユーザーの認証に使用されるアプリケーションを Azure Germany でホストしている場合は、認証コンテキストで権限として使用してください。 `https://login.microsoftonline.com`</span><span class="sxs-lookup"><span data-stu-id="384eb-129">If you're hosting an application in Azure Germany that is used to authenticate Azure Germany or Office 365 Germany users, ensure that `https://login.microsoftonline.com` is used as the authority in the authentication context.</span></span>

    - <span data-ttu-id="384eb-130">Azure 認証コンテキストAD参照してください。</span><span class="sxs-lookup"><span data-stu-id="384eb-130">See Azure AD authentication contexts.</span></span>
    - <span data-ttu-id="384eb-131">これは、アプリケーションの認証と、アプリケーションが呼び出している可能性がある API (Microsoft Graph、Azure AD Graph、Azure Resource Manager) に対する認証の両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="384eb-131">This applies both to authentication to your application as well as authentication to any APIs that your application may be calling (that is, Microsoft Graph, Azure AD Graph, Azure Resource Manager).</span></span>

2. <span data-ttu-id="384eb-132">Azure AD Graph エンドポイントを更新します `https://graph.windows.net` 。</span><span class="sxs-lookup"><span data-stu-id="384eb-132">Update Azure AD Graph endpoint to be `https://graph.windows.net`.</span></span>

3. <span data-ttu-id="384eb-133">MS Graph エンドポイントを更新します `https://graph.microsoft.com` 。</span><span class="sxs-lookup"><span data-stu-id="384eb-133">Update MS Graph endpoint to be `https://graph.microsoft.com`.</span></span>

4. <span data-ttu-id="384eb-134">アプリケーションで使用されているドイツのクラウド エンドポイント (Exchange Online や SharePoint Online 用など) をパブリック クラウドのエンドポイントに更新します。</span><span class="sxs-lookup"><span data-stu-id="384eb-134">Update any German cloud endpoints (such as those for Exchange Online and SharePoint Online) that are used by your applications to be those of the public cloud.</span></span>

5. <span data-ttu-id="384eb-135">管理ツールとスクリプトの `AzurePublic` 環境パラメーターを (代わりに) 次 `AzureGermany` の値に更新します。</span><span class="sxs-lookup"><span data-stu-id="384eb-135">Update environment parameters to be `AzurePublic` (instead of `AzureGermany`) in administrative tools and scripts for:</span></span>

    - [<span data-ttu-id="384eb-136">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="384eb-136">Azure PowerShell</span></span>](https://docs.microsoft.com/powershell/azure/install-az-ps)
    - [<span data-ttu-id="384eb-137">Azure AD PowerShell (MSOnline)</span><span class="sxs-lookup"><span data-stu-id="384eb-137">Azure AD PowerShell (MSOnline)</span></span>](https://docs.microsoft.com/powershell/azure/active-directory/overview)
    - [<span data-ttu-id="384eb-138">Azure AD PowerShell (AzureAD)</span><span class="sxs-lookup"><span data-stu-id="384eb-138">Azure AD PowerShell (AzureAD)</span></span>](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?)
    - [<span data-ttu-id="384eb-139">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="384eb-139">Azure CLI</span></span>](https://docs.microsoft.com/cli/azure/install-azure-cli)
 
<span data-ttu-id="384eb-140">**発行するアプリケーションについて**</span><span class="sxs-lookup"><span data-stu-id="384eb-140">**What about applications that I publish?**</span></span>

<span data-ttu-id="384eb-141">テナント外のユーザーが利用できるアプリケーションを公開する場合は、継続性を確保するためにアプリケーションの登録を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="384eb-141">If you publish an application that is available to users who are outside of your tenant, you may need to change your application registration to ensure continuity.</span></span> <span data-ttu-id="384eb-142">アプリケーションを使用する他のテナントは、テナントとは異なる時刻に移動される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="384eb-142">Other tenants that use your application may be moved at a different time than your tenant.</span></span> <span data-ttu-id="384eb-143">アプリケーションへのアクセス権が失われるのを確実に行わないには、アプリが Azure Germany から Azure パブリックに同期されるのに同意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="384eb-143">To ensure that they never lose access to your application, you'll need to consent to your app being synchronized from Azure Germany to Azure public.</span></span>

## <a name="additional-considerations"></a><span data-ttu-id="384eb-144">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="384eb-144">Additional considerations</span></span>

<span data-ttu-id="384eb-145">Azure AD に関するその他の考慮事項を以下に示AD。</span><span class="sxs-lookup"><span data-stu-id="384eb-145">Here are some additional considerations for Azure AD:</span></span>

- <span data-ttu-id="384eb-146">フェデレーション認証の場合:</span><span class="sxs-lookup"><span data-stu-id="384eb-146">For federated authentication:</span></span>

  - <span data-ttu-id="384eb-147">テナント移行の実行中は、フェデレーション ドメインの作成、昇格、または降格を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="384eb-147">You must not create, promote, or demote a federated domain while the tenant transition is in process.</span></span> <span data-ttu-id="384eb-148">Azure AD サービスへの移行が完了した後 (テナントは完全に完了しています)、フェデレーション ドメインの管理を再開できます。</span><span class="sxs-lookup"><span data-stu-id="384eb-148">After the migration to the Azure AD service is complete (the tenant is fully complete), you can resume managing federated domains.</span></span>

  - <span data-ttu-id="384eb-149">Active Directory フェデレーション サービス (AD FS) でフェデレーション認証を使用している場合は、移行中にオンプレミスの Active Directory ドメイン サービス (AD DS) ですべての認証に使用される発行者 URI を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="384eb-149">If you're using federated authentication with Active Directory Federation Services (AD FS), you shouldn't make changes to Issuer URIs used for all authentication with your on-premises Active Directory Domain Services (AD DS) during migration.</span></span> <span data-ttu-id="384eb-150">発行者 URI を変更すると、ドメイン内のユーザーの認証エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="384eb-150">Changing issuer URIs will lead to authentication failures for users in the domain.</span></span> <span data-ttu-id="384eb-151">発行者 URI は、AD FS で直接変更したり、ドメインを管理からフェデレーションに変換したり、その逆に変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="384eb-151">Issuer URIs can be changed directly in AD FS or when a domain is converted from managed to federated and vice versa.</span></span> <span data-ttu-id="384eb-152">Microsoft では、移行する Azure テナントのフェデレーション ドメインを追加、削除、または変換AD勧めします。</span><span class="sxs-lookup"><span data-stu-id="384eb-152">Microsoft recommends customers don't add, remove, or convert a federated domain in the Azure AD tenant being migrated.</span></span> <span data-ttu-id="384eb-153">発行者 URI は、移行が完全に完了した後で変更できます。</span><span class="sxs-lookup"><span data-stu-id="384eb-153">Issuer URIs can be changed after the migration is fully complete.</span></span>

- <span data-ttu-id="384eb-154">ネットワークの場合:</span><span class="sxs-lookup"><span data-stu-id="384eb-154">For networking:</span></span>

  - <span data-ttu-id="384eb-155">IPv6 名のネットワークの作成は、Azure portal では機能しません `http://portal.microsoftazure.de/` 。</span><span class="sxs-lookup"><span data-stu-id="384eb-155">Creating IPv6-named networks doesn't work in the Azure portal, `http://portal.microsoftazure.de/`.</span></span> <span data-ttu-id="384eb-156">Azure ポータルを使用して `https://portal.azure.com` IPv6 名のネットワークを作成します。</span><span class="sxs-lookup"><span data-stu-id="384eb-156">Use the Azure portal at `https://portal.azure.com` to create IPv6-named networks.</span></span>
 
   - <span data-ttu-id="384eb-157">Microsoft Cloud Deutschland ポータルから Azure Multi-Factor Authentication (MFA) サービス設定の信頼できる IP アドレス範囲を作成できません。</span><span class="sxs-lookup"><span data-stu-id="384eb-157">You can't create trusted IP address ranges for Azure Multi-Factor Authentication (MFA) service settings from the Microsoft Cloud Deutschland portal.</span></span> <span data-ttu-id="384eb-158">365 サービス用の Azure AD ポータルをOffice Azure MFA の信頼できる IP アドレス範囲を作成します。</span><span class="sxs-lookup"><span data-stu-id="384eb-158">Use the Azure AD portal for Office 365 services to create Azure MFA trusted IP address ranges.</span></span>


- <span data-ttu-id="384eb-159">条件付きアクセスの場合:</span><span class="sxs-lookup"><span data-stu-id="384eb-159">For Conditional Access:</span></span> 

  - <span data-ttu-id="384eb-160">Office 365 サービスへの移行が完了するまで [(Azure](ms-cloud-germany-transition.md#how-is-the-migration-organized) 365 移行フェーズの最終処理後)、次の付与制御を持つ条件付きアクセス ポリシー ADされません。</span><span class="sxs-lookup"><span data-stu-id="384eb-160">Conditional Access policies with the following grant controls aren't supported until migration to Office 365 services is complete (after the [Finalize Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase):</span></span>

    - <span data-ttu-id="384eb-161">準拠デバイスが必要</span><span class="sxs-lookup"><span data-stu-id="384eb-161">Require Compliant Device</span></span>
    - <span data-ttu-id="384eb-162">承認済みアプリを要求する</span><span class="sxs-lookup"><span data-stu-id="384eb-162">Require Approved App</span></span>
    - <span data-ttu-id="384eb-163">アプリ保護ポリシーを要求する</span><span class="sxs-lookup"><span data-stu-id="384eb-163">Require App Protection Policy</span></span>
    
  - <span data-ttu-id="384eb-164">条件付きアクセス ポリシー インターフェイスは、無効になっている場合でもテナントに対して有効になっているセキュリティの既定値に関する誤った警告を表示し、条件付きアクセス ポリシーはテナントに対して既に存在します。</span><span class="sxs-lookup"><span data-stu-id="384eb-164">The Conditional Access policy interface gives a false warning about security defaults being enabled for the tenant even when it's disabled, and Conditional Access policies already exist for the tenant.</span></span> <span data-ttu-id="384eb-165">この警告は無視するか、Office 365 サービス ポータルを使用して条件付きアクセス ポリシーを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="384eb-165">You should ignore the warning or use the Office 365 services portal to manage Conditional Access policies.</span></span> 

- <span data-ttu-id="384eb-166">Intune のシナリオは、テナントの移行が完了した後、すべての Office ワークロードの移行を含む、世界中のエンドポイントに対してだけサポートされます。</span><span class="sxs-lookup"><span data-stu-id="384eb-166">Intune scenarios are supported only against worldwide endpoints after tenant migration is complete, including all office workloads migrations.</span></span>

- <span data-ttu-id="384eb-167">MFA 要求にモバイル アプリ通知メソッドを使用する Microsoft Cloud Deutschland ユーザーには、Microsoft Authenticator アプリのユーザー プリンシパル名 (UPN) の代わりにユーザーの ObjectId (GUID) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="384eb-167">Microsoft Cloud Deutschland users who use the Mobile App Notification method for MFA requests see the user's ObjectId (a GUID) instead of the user principal name (UPN) in the Microsoft Authenticator app.</span></span> <span data-ttu-id="384eb-168">Azure AD テナントの移行が完了し、Office 365 サービスでホストされると、新しい Microsoft Authenticator ライセンス認証にユーザーの UPN が表示されます。</span><span class="sxs-lookup"><span data-stu-id="384eb-168">After migration of the Azure AD tenant is complete and hosted in Office 365 services, new Microsoft Authenticator activations will display users' UPNs.</span></span> <span data-ttu-id="384eb-169">既存の Microsoft Authenticator アカウントは引き続きユーザー ObjectId を表示しますが、モバイル アプリ通知では引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="384eb-169">Existing Microsoft Authenticator accounts will continue to display the user ObjectId, but they'll continue to work for mobile app notifications.</span></span> 

- <span data-ttu-id="384eb-170">2019 年 10 月 22 日より後に作成されたテナントの場合、Office 365 サービスに移行するときに、そのテナントのセキュリティの既定値が自動的に有効になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="384eb-170">For tenants that are created after October 22, 2019, security defaults may be auto-enabled for the tenant when it's migrated to the Office 365 service.</span></span> <span data-ttu-id="384eb-171">テナント管理者は、セキュリティの既定値を有効のままにして MFA に登録するか、機能を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="384eb-171">Tenant admins can choose to leave security defaults enabled and register for MFA, or they can disable the feature.</span></span> <span data-ttu-id="384eb-172">詳細については、「セキュリティの既定値 [を無効にする」を参照してください](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="384eb-172">For more information, see [Disabling security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults).</span></span> 

  > [!NOTE]
  > <span data-ttu-id="384eb-173">移行中に自動有効になっていない組織は、将来、セキュリティの既定値を有効にする機能が Office 365 サービスに展開される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="384eb-173">Organizations that are not auto-enabled during migration may still be auto-enrolled in the future as the feature to enable security defaults is rolled out in the Office 365 service.</span></span> <span data-ttu-id="384eb-174">セキュリティの既定値を明示的に無効または有効にした管理者は **、Azure Active Directory** の [プロパティ] で機能を更新>できます。</span><span class="sxs-lookup"><span data-stu-id="384eb-174">Admins who choose to explicitly disable or enable security defaults may do so by updating the feature under **Azure Active Directory > Properties**.</span></span> <span data-ttu-id="384eb-175">管理者が機能を明示的に有効にすると、その機能は自動有効になりません。</span><span class="sxs-lookup"><span data-stu-id="384eb-175">After the feature is explicitly enabled by the admin, it will not be auto-enabled.</span></span>

- <span data-ttu-id="384eb-176">テナントの移行が完了すると、Office 365 Germany ポータルと Office 365 ポータルの Azure AD Connect のバージョンに関する警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="384eb-176">There will be warning about the version of Azure AD Connect in the Office 365 Germany portal as well as in the Office 365 portal once the tenant is in migration.</span></span> <span data-ttu-id="384eb-177">移行の完了後にバージョンの警告に警告が表示されなくなった場合は、無視できます。</span><span class="sxs-lookup"><span data-stu-id="384eb-177">This can be ignored if the version warning is no longer showing the warning after the migration is complete.</span></span> <span data-ttu-id="384eb-178">移行前または移行後にいずれかのポータルで警告がある場合は、Azure AD Connect を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="384eb-178">If there's a warning, either before or after migration, in either portal, Azure AD Connect must be updated.</span></span> <span data-ttu-id="384eb-179">警告メッセージには、「古いディレクトリ同期ツールを使用しているのが検出されました。</span><span class="sxs-lookup"><span data-stu-id="384eb-179">The warning message says: "We detected you're using an outdated directory sync tool.</span></span> <span data-ttu-id="384eb-180">Microsoft ダウンロード センターにアクセスして、Azure AD Connect の最新バージョンを取得することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="384eb-180">We recommend you go to the Microsoft Download Center to get the latest version of Azure AD Connect."</span></span>

## <a name="more-information"></a><span data-ttu-id="384eb-181">詳細</span><span class="sxs-lookup"><span data-stu-id="384eb-181">More information</span></span>

<span data-ttu-id="384eb-182">はじめに:</span><span class="sxs-lookup"><span data-stu-id="384eb-182">Getting started:</span></span>

- [<span data-ttu-id="384eb-183">Microsoft Cloud Deutschland から新しいドイツのデータセンター リージョンOffice 365 サービスへの移行</span><span class="sxs-lookup"><span data-stu-id="384eb-183">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="384eb-184">Microsoft Cloud Deutschland 移行アシスタント</span><span class="sxs-lookup"><span data-stu-id="384eb-184">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="384eb-185">移行のオプトイン方法</span><span class="sxs-lookup"><span data-stu-id="384eb-185">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="384eb-186">移行中のカスタマー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="384eb-186">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="384eb-187">移行を進む:</span><span class="sxs-lookup"><span data-stu-id="384eb-187">Moving through the transition:</span></span>

- [<span data-ttu-id="384eb-188">移行フェーズのアクションと影響</span><span class="sxs-lookup"><span data-stu-id="384eb-188">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="384eb-189">追加の作業前作業</span><span class="sxs-lookup"><span data-stu-id="384eb-189">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="384eb-190">Azure [AD、](ms-cloud-germany-transition-add-devices.md)[デバイス](ms-cloud-germany-transition-azure-ad.md)、[エクスペリエンス、および](ms-cloud-germany-transition-add-experience.md)AD FS[に関する追加情報](ms-cloud-germany-transition-add-adfs.md)。</span><span class="sxs-lookup"><span data-stu-id="384eb-190">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="384eb-191">クラウド アプリ:</span><span class="sxs-lookup"><span data-stu-id="384eb-191">Cloud apps:</span></span>

- [<span data-ttu-id="384eb-192">Dynamics 365 移行プログラム情報</span><span class="sxs-lookup"><span data-stu-id="384eb-192">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="384eb-193">Power BI 移行プログラム情報</span><span class="sxs-lookup"><span data-stu-id="384eb-193">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="384eb-194">Microsoft Teams へのアップグレードを開始する</span><span class="sxs-lookup"><span data-stu-id="384eb-194">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
