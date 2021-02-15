---
title: Microsoft 365 セキュリティ センターのエンドポイント用 Microsoft Defender
description: Microsoft Defender セキュリティ センターから Microsoft 365 セキュリティ センターへの変更点について説明します。
keywords: Microsoft 365 セキュリティ センター、OATP、MDATP、MDO、MDE、単一ウィンドウ、統合ポータル、セキュリティ ポータル、Defender セキュリティ ポータルの使用を開始する
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
manager: dansimp
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: 96d5a3bdbd0acbf428f01cc3bb5afefaa95950b4
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242965"
---
# <a name="provide-managed-security-service-provider-mssp-access"></a><span data-ttu-id="e64c7-104">マネージ セキュリティ サービス プロバイダー (MSSP) アクセスを提供する</span><span class="sxs-lookup"><span data-stu-id="e64c7-104">Provide managed security service provider (MSSP) access</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="e64c7-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="e64c7-105">**Applies to:**</span></span>

- [<span data-ttu-id="e64c7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e64c7-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="e64c7-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e64c7-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)

<span data-ttu-id="e64c7-108">マルチテナントの委任アクセス ソリューションを実装するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e64c7-108">To implement a multi-tenant delegated access solution, take the following steps:</span></span>

1. <span data-ttu-id="e64c7-109">Microsoft [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac) 365 セキュリティ センターのエンドポイント用 Defender で役割ベースのアクセス制御を有効にし、Azure Active Directory (Azure AD) グループに接続します。</span><span class="sxs-lookup"><span data-stu-id="e64c7-109">Enable [role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac) in Defender for Endpoint in Microsoft 365 security center and connect with Azure Active Directory (Azure AD) groups.</span></span>

2. <span data-ttu-id="e64c7-110">アクセス [要求とプロビジョニング用にガバナンス](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) アクセス パッケージを構成します。</span><span class="sxs-lookup"><span data-stu-id="e64c7-110">Configure [Governance Access Packages](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) for access request and provisioning.</span></span>

3. <span data-ttu-id="e64c7-111">Microsoft Myaccess でアクセス要求と監査 [を管理します](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-request-approve)。</span><span class="sxs-lookup"><span data-stu-id="e64c7-111">Manage access requests and audits in [Microsoft Myaccess](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-request-approve).</span></span>

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint-in-microsoft-365-security-center"></a><span data-ttu-id="e64c7-112">Microsoft 365 セキュリティ センターのエンドポイント用 Microsoft Defender で役割ベースのアクセス制御を有効にする</span><span class="sxs-lookup"><span data-stu-id="e64c7-112">Enable role-based access controls in Microsoft Defender for Endpoint in Microsoft 365 security center</span></span>

1. <span data-ttu-id="e64c7-113">**顧客 AAD で MSSP リソースのアクセス グループを作成する: グループ**</span><span class="sxs-lookup"><span data-stu-id="e64c7-113">**Create access groups for MSSP resources in Customer AAD: Groups**</span></span>

    <span data-ttu-id="e64c7-114">これらのグループは、Microsoft 365 セキュリティ センターの Defender for Endpoint で作成した役割にリンクされます。</span><span class="sxs-lookup"><span data-stu-id="e64c7-114">These groups will be linked to the Roles you create in Defender for Endpoint in Microsoft 365 security center.</span></span> <span data-ttu-id="e64c7-115">これを行うには、テナントの顧客AD 3 つのグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="e64c7-115">To do so, in the customer AD tenant, create three groups.</span></span> <span data-ttu-id="e64c7-116">この例のアプローチでは、次のグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="e64c7-116">In our example approach, we create the following groups:</span></span>

    - <span data-ttu-id="e64c7-117">第 1 層アナリスト</span><span class="sxs-lookup"><span data-stu-id="e64c7-117">Tier 1 Analyst</span></span> 
    - <span data-ttu-id="e64c7-118">第 2 層アナリスト</span><span class="sxs-lookup"><span data-stu-id="e64c7-118">Tier 2 Analyst</span></span> 
    - <span data-ttu-id="e64c7-119">MSSP アナリスト承認者</span><span class="sxs-lookup"><span data-stu-id="e64c7-119">MSSP Analyst Approvers</span></span>  


2. <span data-ttu-id="e64c7-120">Microsoft 365 セキュリティ センターの役割とグループの Customer Defender for Endpoint で、適切なアクセス レベルに対応したエンドポイント用 Defender の役割を作成します。</span><span class="sxs-lookup"><span data-stu-id="e64c7-120">Create Defender for Endpoint roles for appropriate access levels in Customer Defender for Endpoint in Microsoft 365 security center roles and groups.</span></span>

    <span data-ttu-id="e64c7-121">お客様の Microsoft 365 セキュリティ センターで RBAC を有効にするには、グローバル管理者またはセキュリティ管理者の権限を持つユーザー アカウントを使用して、アクセス許可 > エンドポイントの役割 & グループ **> の** 役割にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="e64c7-121">To enable RBAC in the customer Microsoft 365 security center, access **Permissions >  Endpoints roles & groups > Roles** with a user account with Global Administrator or Security Administrator rights.</span></span>

    ![MSSP アクセスの画像](../../media/mssp-access.png)

    <span data-ttu-id="e64c7-123">次に、MSSP SOC 層のニーズを満たす RBAC の役割を作成します。</span><span class="sxs-lookup"><span data-stu-id="e64c7-123">Then, create RBAC roles to meet MSSP SOC Tier needs.</span></span> <span data-ttu-id="e64c7-124">"割り当てられたユーザー グループ" を使用して、作成されたユーザー グループにこれらの役割をリンクします。</span><span class="sxs-lookup"><span data-stu-id="e64c7-124">Link these roles to the created user groups via "Assigned user groups".</span></span>

    <span data-ttu-id="e64c7-125">次の 2 つの役割を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e64c7-125">Two possible roles:</span></span>

    - <span data-ttu-id="e64c7-126">**第 1 層アナリスト**</span><span class="sxs-lookup"><span data-stu-id="e64c7-126">**Tier 1 Analysts**</span></span> <br>
      <span data-ttu-id="e64c7-127">ライブ応答以外のすべてのアクションを実行し、セキュリティ設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="e64c7-127">Perform all actions except for live response and manage security settings.</span></span>

    - <span data-ttu-id="e64c7-128">**第 2 層アナリスト**</span><span class="sxs-lookup"><span data-stu-id="e64c7-128">**Tier 2 Analysts**</span></span> <br>
      <span data-ttu-id="e64c7-129">ライブ応答に追加された階層 1 [の機能](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)</span><span class="sxs-lookup"><span data-stu-id="e64c7-129">Tier 1 capabilities with the addition to [live response](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)</span></span>

    <span data-ttu-id="e64c7-130">詳細については、「役割ベースの [アクセス制御を使用する」を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)。</span><span class="sxs-lookup"><span data-stu-id="e64c7-130">For more information, see [Use role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac).</span></span>



## <a name="configure-governance-access-packages"></a><span data-ttu-id="e64c7-131">ガバナンス アクセス パッケージを構成する</span><span class="sxs-lookup"><span data-stu-id="e64c7-131">Configure Governance Access Packages</span></span>

1.  <span data-ttu-id="e64c7-132">**顧客 AAD で接続された組織として MSSP を追加する: ID ガバナンス**</span><span class="sxs-lookup"><span data-stu-id="e64c7-132">**Add MSSP as Connected Organization in Customer AAD: Identity Governance**</span></span>
    
    <span data-ttu-id="e64c7-133">接続された組織として MSSP を追加すると、MSSP が要求し、アクセスが準備されます。</span><span class="sxs-lookup"><span data-stu-id="e64c7-133">Adding the MSSP as a connected organization will allow the MSSP to request and have accesses provisioned.</span></span> 

    <span data-ttu-id="e64c7-134">これを行うには、テナントの顧客AD、Identity Governance: Connected organization にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="e64c7-134">To do so, in the customer AD tenant, access Identity Governance: Connected organization.</span></span> <span data-ttu-id="e64c7-135">新しい組織を追加し、テナント ID またはドメインを使用して MSSP アナリストのテナントを検索します。</span><span class="sxs-lookup"><span data-stu-id="e64c7-135">Add a new organization and search for your MSSP Analyst tenant via Tenant ID or Domain.</span></span> <span data-ttu-id="e64c7-136">MSSP アナリスト用にADテナントを作成してください。</span><span class="sxs-lookup"><span data-stu-id="e64c7-136">We suggest creating a separate AD tenant for your MSSP Analysts.</span></span>

2. <span data-ttu-id="e64c7-137">**顧客 AAD でリソース カタログを作成する: ID ガバナンス**</span><span class="sxs-lookup"><span data-stu-id="e64c7-137">**Create a resource catalog in Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="e64c7-138">リソース カタログはアクセス パッケージの論理コレクションで、テナントの顧客ADされます。</span><span class="sxs-lookup"><span data-stu-id="e64c7-138">Resource catalogs are a logical collection of access packages, created in the customer AD tenant.</span></span>

    <span data-ttu-id="e64c7-139">これを行うには、顧客管理テナントでADガバナンス: カタログにアクセスし、新しいカタログ **を追加します**。</span><span class="sxs-lookup"><span data-stu-id="e64c7-139">To do so, in the customer AD tenant,  access Identity Governance: Catalogs, and add **New Catalog**.</span></span> <span data-ttu-id="e64c7-140">この例では **、MSSP Accesses と呼び出します**。</span><span class="sxs-lookup"><span data-stu-id="e64c7-140">In our example, we will call it **MSSP Accesses**.</span></span> 

    ![新しいカタログの画像](../../media/goverance-catalog.png)

    <span data-ttu-id="e64c7-142">詳細については、「リソースのカタログ [を作成する」を参照してください](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-catalog-create)。</span><span class="sxs-lookup"><span data-stu-id="e64c7-142">Further more information, see [Create a catalog of resources](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-catalog-create).</span></span>


3. <span data-ttu-id="e64c7-143">**MSSP リソース Customer AAD: Identity Governance 用のアクセス パッケージを作成する**</span><span class="sxs-lookup"><span data-stu-id="e64c7-143">**Create access packages for MSSP resources Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="e64c7-144">アクセス パッケージは、承認時に要求者に付与される権限とアクセスのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="e64c7-144">Access packages are the collection of rights and accesses that a requestor will be granted upon approval.</span></span> 

    <span data-ttu-id="e64c7-145">これを行うには、顧客管理テナントでADガバナンス: アクセス パッケージにアクセスし、新しいアクセス パッケージ **を追加します**。</span><span class="sxs-lookup"><span data-stu-id="e64c7-145">To do so, in the customer AD tenant, access Identity Governance: Access Packages, and add **New Access Package**.</span></span> <span data-ttu-id="e64c7-146">MSSP 承認者と各アナリスト層のアクセス パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="e64c7-146">Create an access package for the MSSP approvers and each analyst tier.</span></span> <span data-ttu-id="e64c7-147">たとえば、次の階層 1 アナリストの構成では、次のようなアクセス パッケージが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e64c7-147">For example, the following Tier 1 Analyst configuration creates an access package that:</span></span>

    - <span data-ttu-id="e64c7-148">新しい要求を承認するにはAD **MSSP アナリスト承認者** グループのメンバーが必要です。</span><span class="sxs-lookup"><span data-stu-id="e64c7-148">Requires a member of the AD group **MSSP Analyst Approvers** to authorize new requests</span></span>
    - <span data-ttu-id="e64c7-149">SOC アナリストがアクセスの延長を要求できる年次アクセス レビューがある</span><span class="sxs-lookup"><span data-stu-id="e64c7-149">Has annual access reviews, where the SOC analysts can request an access extension</span></span>
    - <span data-ttu-id="e64c7-150">MSSP SOC テナント内のユーザーだけが要求できます</span><span class="sxs-lookup"><span data-stu-id="e64c7-150">Can only be requested by users in the MSSP SOC Tenant</span></span>
    - <span data-ttu-id="e64c7-151">Access auto expires after 365 days</span><span class="sxs-lookup"><span data-stu-id="e64c7-151">Access auto expires after 365 days</span></span>

    ![新しいアクセス パッケージの画像](../../media/new-access-package.png)

    <span data-ttu-id="e64c7-153">詳細については、「新しいアクセス パッケージ [を作成する」を参照してください](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-access-package-create)。</span><span class="sxs-lookup"><span data-stu-id="e64c7-153">For more information, see [Create a new access package](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-access-package-create).</span></span>


4. <span data-ttu-id="e64c7-154">**顧客 AAD から MSSP リソースへのアクセス要求リンクを提供する: ID ガバナンス**</span><span class="sxs-lookup"><span data-stu-id="e64c7-154">**Provide access request link to MSSP resources from Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="e64c7-155">マイ アクセス ポータルリンクは、MSSP SOC アナリストが作成したアクセス パッケージを介したアクセスを要求するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e64c7-155">The My Access portal link is used by MSSP SOC analysts to request access via the access packages created.</span></span> <span data-ttu-id="e64c7-156">リンクは永続的です。つまり、新しいアナリストにも同じリンクが使用される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e64c7-156">The link is durable, meaning the same link may be used over time for new analysts.</span></span> <span data-ttu-id="e64c7-157">アナリストの要求は、MSSP アナリスト承認者による承認を得 **るキューに入ります**。</span><span class="sxs-lookup"><span data-stu-id="e64c7-157">The analyst request goes into a queue for approval by the **MSSP Analyst Approvers**.</span></span>


    ![アクセス プロパティの画像](../../media/access-properties.png)

    <span data-ttu-id="e64c7-159">リンクは、各アクセス パッケージの概要ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e64c7-159">The link is located on the overview page of each access package.</span></span>

## <a name="manage-access"></a><span data-ttu-id="e64c7-160">アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="e64c7-160">Manage access</span></span> 

1. <span data-ttu-id="e64c7-161">Customer または MSSP myaccess のアクセス要求を確認および承認します。</span><span class="sxs-lookup"><span data-stu-id="e64c7-161">Review and authorize access requests in Customer and/or MSSP myaccess.</span></span>

    <span data-ttu-id="e64c7-162">アクセス要求は、MSSP アナリスト承認者グループのメンバーによって、お客様のマイ アクセスで管理されます。</span><span class="sxs-lookup"><span data-stu-id="e64c7-162">Access requests are managed in the customer My Access, by members of the MSSP Analyst Approvers group.</span></span>

    <span data-ttu-id="e64c7-163">これを行うには、次を使用して顧客のマイアクセスにアクセスします  `https://myaccess.microsoft.com/@<Customer Domain >` 。</span><span class="sxs-lookup"><span data-stu-id="e64c7-163">To do so, access the customer's myaccess using:  `https://myaccess.microsoft.com/@<Customer Domain >`.</span></span> 

    <span data-ttu-id="e64c7-164">例:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span><span class="sxs-lookup"><span data-stu-id="e64c7-164">Example:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span></span>   
2. <span data-ttu-id="e64c7-165">UI の [承認] セクションで要求 **を** 承認または拒否します。</span><span class="sxs-lookup"><span data-stu-id="e64c7-165">Approve or deny requests in the **Approvals** section of the UI.</span></span>

     <span data-ttu-id="e64c7-166">この時点で、アナリストのアクセスがプロビジョニングされ、各アナリストは顧客の Microsoft 365 セキュリティ センターにアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e64c7-166">At this point, analyst access has been provisioned, and each analyst should be able to access the customer's Microsoft 365 Security Center:</span></span> 

    <span data-ttu-id="e64c7-167">`https://security.microsoft.com/?tid=<CustomerTenantId>` 割り当てられたアクセス許可と役割を使用します。</span><span class="sxs-lookup"><span data-stu-id="e64c7-167">`https://security.microsoft.com/?tid=<CustomerTenantId>` with the permissions and roles they were assigned.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e64c7-168">Microsoft 365 セキュリティ センターのエンドポイント用 Microsoft Defender への委任されたアクセスでは、現在、ブラウザーウィンドウごとに 1 つのテナントにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e64c7-168">Delegated access to Microsoft Defender for Endpoint in the Microsoft 365 security center currently allows access to a single tenant per browser window.</span></span> 