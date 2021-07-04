---
title: マネージド セキュリティ サービス プロバイダー (MSSP) アクセスを提供する
description: セキュリティ センターへの変更Microsoft Defender セキュリティ センター詳細Microsoft 365する
keywords: Microsoft 365 セキュリティ センター、microsoft Defender for Office 365、Microsoft Defender for Endpoint、MDO、MDE、単一ウィンドウ のガラス、コンバージド ポータル、セキュリティ ポータル、Defender セキュリティ ポータルの使用を開始する
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
localization_priority: Normal
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
ms.openlocfilehash: ddc28149ca2ab43b7c14d3bdbaeeecdad1b18387
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289765"
---
# <a name="provide-managed-security-service-provider-mssp-access"></a><span data-ttu-id="d0d6e-104">マネージド セキュリティ サービス プロバイダー (MSSP) アクセスを提供する</span><span class="sxs-lookup"><span data-stu-id="d0d6e-104">Provide managed security service provider (MSSP) access</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="d0d6e-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="d0d6e-105">**Applies to:**</span></span>

- [<span data-ttu-id="d0d6e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d0d6e-106">Microsoft 365 Defender</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="d0d6e-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d0d6e-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

<span data-ttu-id="d0d6e-108">マルチテナント委任アクセス ソリューションを実装するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d0d6e-108">To implement a multi-tenant delegated access solution, take the following steps:</span></span>

1. <span data-ttu-id="d0d6e-109">セキュリティ[センターの](/windows/security/threat-protection/microsoft-defender-atp/rbac)Defender for Endpoint で役割ベース Azure Active Directoryのアクセス制御を有効Microsoft 365(Azure AD) グループに接続します。</span><span class="sxs-lookup"><span data-stu-id="d0d6e-109">Enable [role-based access control](/windows/security/threat-protection/microsoft-defender-atp/rbac) in Defender for Endpoint in Microsoft 365 security center and connect with Azure Active Directory (Azure AD) groups.</span></span>

2. <span data-ttu-id="d0d6e-110">アクセス [要求とプロビジョニング用にガバナンス](/azure/active-directory/governance/identity-governance-overview) アクセス パッケージを構成します。</span><span class="sxs-lookup"><span data-stu-id="d0d6e-110">Configure [Governance Access Packages](/azure/active-directory/governance/identity-governance-overview) for access request and provisioning.</span></span>

3. <span data-ttu-id="d0d6e-111">Microsoft Myaccess でアクセス要求と監査 [を管理します](/azure/active-directory/governance/entitlement-management-request-approve)。</span><span class="sxs-lookup"><span data-stu-id="d0d6e-111">Manage access requests and audits in [Microsoft Myaccess](/azure/active-directory/governance/entitlement-management-request-approve).</span></span>

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint-in-microsoft-365-security-center"></a><span data-ttu-id="d0d6e-112">セキュリティ センターで Microsoft Defender for Endpoint で役割ベースのアクセスMicrosoft 365有効にする</span><span class="sxs-lookup"><span data-stu-id="d0d6e-112">Enable role-based access controls in Microsoft Defender for Endpoint in Microsoft 365 security center</span></span>

1. <span data-ttu-id="d0d6e-113">**顧客 AAD で MSSP リソースのアクセス グループを作成する: グループ**</span><span class="sxs-lookup"><span data-stu-id="d0d6e-113">**Create access groups for MSSP resources in Customer AAD: Groups**</span></span>

    <span data-ttu-id="d0d6e-114">これらのグループは、セキュリティ センターの Defender for Endpoint で作成したMicrosoft 365されます。</span><span class="sxs-lookup"><span data-stu-id="d0d6e-114">These groups will be linked to the Roles you create in Defender for Endpoint in Microsoft 365 security center.</span></span> <span data-ttu-id="d0d6e-115">これを行うには、テナントの顧客AD 3 つのグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="d0d6e-115">To do so, in the customer AD tenant, create three groups.</span></span> <span data-ttu-id="d0d6e-116">この例のアプローチでは、次のグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="d0d6e-116">In our example approach, we create the following groups:</span></span>

    - <span data-ttu-id="d0d6e-117">Tier 1 Analyst</span><span class="sxs-lookup"><span data-stu-id="d0d6e-117">Tier 1 Analyst</span></span>
    - <span data-ttu-id="d0d6e-118">Tier 2 Analyst</span><span class="sxs-lookup"><span data-stu-id="d0d6e-118">Tier 2 Analyst</span></span>
    - <span data-ttu-id="d0d6e-119">MSSP アナリスト承認者</span><span class="sxs-lookup"><span data-stu-id="d0d6e-119">MSSP Analyst Approvers</span></span>  

2. <span data-ttu-id="d0d6e-120">セキュリティ センターの役割とグループ内の Customer Defender for Endpoint で適切なアクセス レベルMicrosoft 365 Defender for Endpoint の役割を作成します。</span><span class="sxs-lookup"><span data-stu-id="d0d6e-120">Create Defender for Endpoint roles for appropriate access levels in Customer Defender for Endpoint in Microsoft 365 security center roles and groups.</span></span>

    <span data-ttu-id="d0d6e-121">カスタマー Microsoft 365 セキュリティ センターで RBAC を有効にするには、グローバル管理者またはセキュリティ管理者権限を持つユーザー アカウントを使用して、> **Endpoints** の役割 & > Roles にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="d0d6e-121">To enable RBAC in the customer Microsoft 365 security center, access **Permissions >  Endpoints roles & groups > Roles** with a user account with Global Administrator or Security Administrator rights.</span></span>

    ![MSSP アクセスのイメージ](../../media/mssp-access.png)

    <span data-ttu-id="d0d6e-123">次に、MSSP SOC Tier のニーズを満たす RBAC ロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="d0d6e-123">Then, create RBAC roles to meet MSSP SOC Tier needs.</span></span> <span data-ttu-id="d0d6e-124">[割り当てられたユーザー グループ] を使用して、作成されたユーザー グループにこれらの役割をリンクします。</span><span class="sxs-lookup"><span data-stu-id="d0d6e-124">Link these roles to the created user groups via "Assigned user groups".</span></span>

    <span data-ttu-id="d0d6e-125">2 つの可能な役割:</span><span class="sxs-lookup"><span data-stu-id="d0d6e-125">Two possible roles:</span></span>

    - <span data-ttu-id="d0d6e-126">**Tier 1 Analysts**</span><span class="sxs-lookup"><span data-stu-id="d0d6e-126">**Tier 1 Analysts**</span></span> <br>
      <span data-ttu-id="d0d6e-127">ライブ応答以外のすべてのアクションを実行し、セキュリティ設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="d0d6e-127">Perform all actions except for live response and manage security settings.</span></span>

    - <span data-ttu-id="d0d6e-128">**Tier 2 Analysts**</span><span class="sxs-lookup"><span data-stu-id="d0d6e-128">**Tier 2 Analysts**</span></span> <br>
      <span data-ttu-id="d0d6e-129">ライブ応答に追加された Tier 1 [の機能](/windows/security/threat-protection/microsoft-defender-atp/live-response)</span><span class="sxs-lookup"><span data-stu-id="d0d6e-129">Tier 1 capabilities with the addition to [live response](/windows/security/threat-protection/microsoft-defender-atp/live-response)</span></span>

    <span data-ttu-id="d0d6e-130">詳細については、「役割ベースの [アクセス制御を使用する」を参照してください](/windows/security/threat-protection/microsoft-defender-atp/rbac)。</span><span class="sxs-lookup"><span data-stu-id="d0d6e-130">For more information, see [Use role-based access control](/windows/security/threat-protection/microsoft-defender-atp/rbac).</span></span>

## <a name="configure-governance-access-packages"></a><span data-ttu-id="d0d6e-131">ガバナンス アクセス パッケージの構成</span><span class="sxs-lookup"><span data-stu-id="d0d6e-131">Configure Governance Access Packages</span></span>

1. <span data-ttu-id="d0d6e-132">**顧客 AAD の接続組織として MSSP を追加する: ID ガバナンス**</span><span class="sxs-lookup"><span data-stu-id="d0d6e-132">**Add MSSP as Connected Organization in Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="d0d6e-133">接続された組織として MSSP を追加すると、MSSP は要求し、アクセスが準備されます。</span><span class="sxs-lookup"><span data-stu-id="d0d6e-133">Adding the MSSP as a connected organization will allow the MSSP to request and have accesses provisioned.</span></span> 

    <span data-ttu-id="d0d6e-134">これを行うには、テナントの顧客AD、Identity Governance: Connected organization にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="d0d6e-134">To do so, in the customer AD tenant, access Identity Governance: Connected organization.</span></span> <span data-ttu-id="d0d6e-135">新しい組織を追加し、テナント ID またはドメインを使用して MSSP Analyst テナントを検索します。</span><span class="sxs-lookup"><span data-stu-id="d0d6e-135">Add a new organization and search for your MSSP Analyst tenant via Tenant ID or Domain.</span></span> <span data-ttu-id="d0d6e-136">MSSP Analysts 用に個別のADテナントを作成する方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d0d6e-136">We suggest creating a separate AD tenant for your MSSP Analysts.</span></span>

2. <span data-ttu-id="d0d6e-137">**顧客 AAD でリソース カタログを作成する: ID ガバナンス**</span><span class="sxs-lookup"><span data-stu-id="d0d6e-137">**Create a resource catalog in Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="d0d6e-138">リソース カタログは、テナントの顧客に作成されたアクセス パッケージADです。</span><span class="sxs-lookup"><span data-stu-id="d0d6e-138">Resource catalogs are a logical collection of access packages, created in the customer AD tenant.</span></span>

    <span data-ttu-id="d0d6e-139">これを行うには、テナントの顧客AD、Identity Governance: Catalogs にアクセスし、新しいカタログ **を追加します**。</span><span class="sxs-lookup"><span data-stu-id="d0d6e-139">To do so, in the customer AD tenant,  access Identity Governance: Catalogs, and add **New Catalog**.</span></span> <span data-ttu-id="d0d6e-140">この例では **、MSSP Accesses を呼び出します**。</span><span class="sxs-lookup"><span data-stu-id="d0d6e-140">In our example, we will call it **MSSP Accesses**.</span></span>

    ![新しいカタログのイメージ](../../media/goverance-catalog.png)

    <span data-ttu-id="d0d6e-142">詳細については、「リソースのカタログ [を作成する」を参照してください](/azure/active-directory/governance/entitlement-management-catalog-create)。</span><span class="sxs-lookup"><span data-stu-id="d0d6e-142">Further more information, see [Create a catalog of resources](/azure/active-directory/governance/entitlement-management-catalog-create).</span></span>

3. <span data-ttu-id="d0d6e-143">**MSSP リソースのアクセス パッケージを作成する 顧客 AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="d0d6e-143">**Create access packages for MSSP resources Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="d0d6e-144">アクセス パッケージは、承認時に要求者に付与される権限とアクセスのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="d0d6e-144">Access packages are the collection of rights and accesses that a requestor will be granted upon approval.</span></span> 

    <span data-ttu-id="d0d6e-145">これを行うには、テナントの顧客AD、Identity Governance: Access Package にアクセスし、新しいアクセス パッケージ **を追加します**。</span><span class="sxs-lookup"><span data-stu-id="d0d6e-145">To do so, in the customer AD tenant, access Identity Governance: Access Packages, and add **New Access Package**.</span></span> <span data-ttu-id="d0d6e-146">MSSP 承認者と各アナリスト層のアクセス パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="d0d6e-146">Create an access package for the MSSP approvers and each analyst tier.</span></span> <span data-ttu-id="d0d6e-147">たとえば、次の Tier 1 Analyst 構成によって、次のようなアクセス パッケージが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d0d6e-147">For example, the following Tier 1 Analyst configuration creates an access package that:</span></span>

    - <span data-ttu-id="d0d6e-148">新しい要求を承認するには、AD **MSSP アナリスト承認者** のメンバーが必要です。</span><span class="sxs-lookup"><span data-stu-id="d0d6e-148">Requires a member of the AD group **MSSP Analyst Approvers** to authorize new requests</span></span>
    - <span data-ttu-id="d0d6e-149">SOC アナリストがアクセス拡張機能を要求できる年次アクセス レビューがある</span><span class="sxs-lookup"><span data-stu-id="d0d6e-149">Has annual access reviews, where the SOC analysts can request an access extension</span></span>
    - <span data-ttu-id="d0d6e-150">MSSP SOC テナント内のユーザーだけが要求できる</span><span class="sxs-lookup"><span data-stu-id="d0d6e-150">Can only be requested by users in the MSSP SOC Tenant</span></span>
    - <span data-ttu-id="d0d6e-151">365 日後に自動アクセスが期限切れになる</span><span class="sxs-lookup"><span data-stu-id="d0d6e-151">Access auto expires after 365 days</span></span>

    ![新しいアクセス パッケージのイメージ](../../media/new-access-package.png)

    <span data-ttu-id="d0d6e-153">詳細については、「新しいアクセス [パッケージを作成する」を参照してください](/azure/active-directory/governance/entitlement-management-access-package-create)。</span><span class="sxs-lookup"><span data-stu-id="d0d6e-153">For more information, see [Create a new access package](/azure/active-directory/governance/entitlement-management-access-package-create).</span></span>

4. <span data-ttu-id="d0d6e-154">**顧客 AAD から MSSP リソースへのアクセス要求リンクを提供する: ID ガバナンス**</span><span class="sxs-lookup"><span data-stu-id="d0d6e-154">**Provide access request link to MSSP resources from Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="d0d6e-155">[マイ アクセス ポータル] リンクは、MSSP SOC アナリストが作成したアクセス パッケージを介してアクセスを要求するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d0d6e-155">The My Access portal link is used by MSSP SOC analysts to request access via the access packages created.</span></span> <span data-ttu-id="d0d6e-156">リンクは永続的です。つまり、同じリンクが新しいアナリストのために時間の間に使用される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d0d6e-156">The link is durable, meaning the same link may be used over time for new analysts.</span></span> <span data-ttu-id="d0d6e-157">アナリスト要求は、MSSP アナリスト承認者による承認のためにキュー **に入ります**。</span><span class="sxs-lookup"><span data-stu-id="d0d6e-157">The analyst request goes into a queue for approval by the **MSSP Analyst Approvers**.</span></span>

    ![アクセス プロパティのイメージ](../../media/access-properties.png)

    <span data-ttu-id="d0d6e-159">リンクは、各アクセス パッケージの概要ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0d6e-159">The link is located on the overview page of each access package.</span></span>

## <a name="manage-access"></a><span data-ttu-id="d0d6e-160">アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="d0d6e-160">Manage access</span></span>

1. <span data-ttu-id="d0d6e-161">Customer または MSSP myaccess のアクセス要求を確認および承認します。</span><span class="sxs-lookup"><span data-stu-id="d0d6e-161">Review and authorize access requests in Customer and/or MSSP myaccess.</span></span>

    <span data-ttu-id="d0d6e-162">アクセス要求は、MSSP Analyst Approvers グループのメンバーによって、お客様の My Access で管理されます。</span><span class="sxs-lookup"><span data-stu-id="d0d6e-162">Access requests are managed in the customer My Access, by members of the MSSP Analyst Approvers group.</span></span>

    <span data-ttu-id="d0d6e-163">これを行うには、次を使用して顧客の myaccess にアクセスします `https://myaccess.microsoft.com/@<Customer Domain>` 。</span><span class="sxs-lookup"><span data-stu-id="d0d6e-163">To do so, access the customer's myaccess using: `https://myaccess.microsoft.com/@<Customer Domain>`.</span></span>

    <span data-ttu-id="d0d6e-164">例: `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span><span class="sxs-lookup"><span data-stu-id="d0d6e-164">Example: `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span></span>

2. <span data-ttu-id="d0d6e-165">UI の [承認] セクション **で要求を** 承認または拒否します。</span><span class="sxs-lookup"><span data-stu-id="d0d6e-165">Approve or deny requests in the **Approvals** section of the UI.</span></span>

     <span data-ttu-id="d0d6e-166">この時点でアナリスト アクセスが準備され、各アナリストは顧客のセキュリティ センターにMicrosoft 365があります。</span><span class="sxs-lookup"><span data-stu-id="d0d6e-166">At this point, analyst access has been provisioned, and each analyst should be able to access the customer's Microsoft 365 Security Center:</span></span>

    <span data-ttu-id="d0d6e-167">`https://security.microsoft.com/?tid=<CustomerTenantId>` 割り当てられたアクセス許可とロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="d0d6e-167">`https://security.microsoft.com/?tid=<CustomerTenantId>` with the permissions and roles they were assigned.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d0d6e-168">現在、セキュリティ センターの Microsoft Defender for Endpoint への委任アクセスでは、Microsoft 365ウィンドウごとに 1 つのテナントにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d0d6e-168">Delegated access to Microsoft Defender for Endpoint in the Microsoft 365 security center currently allows access to a single tenant per browser window.</span></span>
