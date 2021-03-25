---
title: 管理セキュリティ サービス プロバイダー (MSSP) へのアクセスを許可する
description: Microsoft Defender ATP との MSSP 統合を構成するために必要な手順を実行する
keywords: マネージド セキュリティ サービス プロバイダー、mssp、構成、統合
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1bb7bc3565bbb7c05f165c5649f3672ff33bb18b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165455"
---
# <a name="grant-managed-security-service-provider-mssp-access-preview"></a><span data-ttu-id="8e228-104">管理セキュリティ サービス プロバイダー (MSSP) アクセス権の付与 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="8e228-104">Grant managed security service provider (MSSP) access (preview)</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8e228-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="8e228-105">**Applies to:**</span></span>
- [<span data-ttu-id="8e228-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8e228-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8e228-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8e228-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="8e228-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="8e228-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8e228-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="8e228-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)

>[!IMPORTANT] 
><span data-ttu-id="8e228-110">一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。</span><span class="sxs-lookup"><span data-stu-id="8e228-110">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="8e228-111">Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="8e228-111">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="8e228-112">マルチテナント委任アクセス ソリューションを実装するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8e228-112">To implement a multi-tenant delegated access solution, take the following steps:</span></span>

1. <span data-ttu-id="8e228-113">Defender for Endpoint [で役割ベースのアクセス制御](rbac.md) を有効にし、Active Directory (AD) グループに接続します。</span><span class="sxs-lookup"><span data-stu-id="8e228-113">Enable [role-based access control](rbac.md) in Defender for Endpoint and connect with Active Directory (AD) groups.</span></span>

2. <span data-ttu-id="8e228-114">アクセス [要求とプロビジョニング用にガバナンス](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) アクセス パッケージを構成します。</span><span class="sxs-lookup"><span data-stu-id="8e228-114">Configure [Governance Access Packages](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) for access request and provisioning.</span></span>

3. <span data-ttu-id="8e228-115">Microsoft Myaccess でアクセス要求と監査 [を管理します](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-request-approve)。</span><span class="sxs-lookup"><span data-stu-id="8e228-115">Manage access requests and audits in [Microsoft Myaccess](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-request-approve).</span></span>

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="8e228-116">Microsoft Defender for Endpoint で役割ベースのアクセス制御を有効にする</span><span class="sxs-lookup"><span data-stu-id="8e228-116">Enable role-based access controls in Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="8e228-117">**顧客 AAD で MSSP リソースのアクセス グループを作成する: グループ**</span><span class="sxs-lookup"><span data-stu-id="8e228-117">**Create access groups for MSSP resources in Customer AAD: Groups**</span></span>

    <span data-ttu-id="8e228-118">これらのグループは、Defender for Endpoint で作成したロールにリンクされます。</span><span class="sxs-lookup"><span data-stu-id="8e228-118">These groups will be linked to the Roles you create in Defender for Endpoint.</span></span> <span data-ttu-id="8e228-119">これを行うには、テナントの顧客AD 3 つのグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="8e228-119">To do so, in the customer AD tenant, create three groups.</span></span> <span data-ttu-id="8e228-120">この例のアプローチでは、次のグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="8e228-120">In our example approach, we create the following groups:</span></span>

    - <span data-ttu-id="8e228-121">Tier 1 Analyst</span><span class="sxs-lookup"><span data-stu-id="8e228-121">Tier 1 Analyst</span></span> 
    - <span data-ttu-id="8e228-122">Tier 2 Analyst</span><span class="sxs-lookup"><span data-stu-id="8e228-122">Tier 2 Analyst</span></span> 
    - <span data-ttu-id="8e228-123">MSSP アナリスト承認者</span><span class="sxs-lookup"><span data-stu-id="8e228-123">MSSP Analyst Approvers</span></span>  


2. <span data-ttu-id="8e228-124">エンドポイントの Customer Defender で適切なアクセス レベルの Defender for Endpoint ロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="8e228-124">Create Defender for Endpoint roles for appropriate access levels in Customer Defender for Endpoint.</span></span>

    <span data-ttu-id="8e228-125">お客様の Microsoft Defender セキュリティ センターで RBAC を有効にするには、グローバル管理者またはセキュリティ管理者の権限を持つユーザー アカウントから、[設定] > アクセス許可 **>** ロールと "ロールを有効にする" にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="8e228-125">To enable RBAC in the customer Microsoft Defender Security Center, access **Settings > Permissions > Roles** and "Turn on roles", from a user account with Global Administrator or Security Administrator rights.</span></span>

    ![MSSP アクセスのイメージ](images/mssp-access.png)

    <span data-ttu-id="8e228-127">次に、MSSP SOC Tier のニーズを満たす RBAC ロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="8e228-127">Then, create RBAC roles to meet MSSP SOC Tier needs.</span></span> <span data-ttu-id="8e228-128">[割り当てられたユーザー グループ] を使用して、作成されたユーザー グループにこれらの役割をリンクします。</span><span class="sxs-lookup"><span data-stu-id="8e228-128">Link these roles to the created user groups via "Assigned user groups".</span></span>

    <span data-ttu-id="8e228-129">2 つの可能な役割:</span><span class="sxs-lookup"><span data-stu-id="8e228-129">Two possible roles:</span></span>

    - <span data-ttu-id="8e228-130">**Tier 1 Analysts**</span><span class="sxs-lookup"><span data-stu-id="8e228-130">**Tier 1 Analysts**</span></span> <br>
      <span data-ttu-id="8e228-131">ライブ応答以外のすべてのアクションを実行し、セキュリティ設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="8e228-131">Perform all actions except for live response and manage security settings.</span></span>

    - <span data-ttu-id="8e228-132">**Tier 2 Analysts**</span><span class="sxs-lookup"><span data-stu-id="8e228-132">**Tier 2 Analysts**</span></span> <br>
      <span data-ttu-id="8e228-133">ライブ応答に追加された Tier 1 [の機能](live-response.md)</span><span class="sxs-lookup"><span data-stu-id="8e228-133">Tier 1 capabilities with the addition to [live response](live-response.md)</span></span>

    <span data-ttu-id="8e228-134">詳細については、「役割ベースの [アクセス制御を使用する」を参照してください](rbac.md)。</span><span class="sxs-lookup"><span data-stu-id="8e228-134">For more information, see [Use role-based access control](rbac.md).</span></span>



## <a name="configure-governance-access-packages"></a><span data-ttu-id="8e228-135">ガバナンス アクセス パッケージの構成</span><span class="sxs-lookup"><span data-stu-id="8e228-135">Configure Governance Access Packages</span></span>

1.  <span data-ttu-id="8e228-136">**顧客 AAD の接続組織として MSSP を追加する: ID ガバナンス**</span><span class="sxs-lookup"><span data-stu-id="8e228-136">**Add MSSP as Connected Organization in Customer AAD: Identity Governance**</span></span>
    
    <span data-ttu-id="8e228-137">接続された組織として MSSP を追加すると、MSSP は要求し、アクセスが準備されます。</span><span class="sxs-lookup"><span data-stu-id="8e228-137">Adding the MSSP as a connected organization will allow the MSSP to request and have accesses provisioned.</span></span> 

    <span data-ttu-id="8e228-138">これを行うには、テナントの顧客AD、Identity Governance: Connected organization にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="8e228-138">To do so, in the customer AD tenant, access Identity Governance: Connected organization.</span></span> <span data-ttu-id="8e228-139">新しい組織を追加し、テナント ID またはドメインを使用して MSSP Analyst テナントを検索します。</span><span class="sxs-lookup"><span data-stu-id="8e228-139">Add a new organization and search for your MSSP Analyst tenant via Tenant ID or Domain.</span></span> <span data-ttu-id="8e228-140">MSSP Analysts 用に個別のADテナントを作成する方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8e228-140">We suggest creating a separate AD tenant for your MSSP Analysts.</span></span>

2. <span data-ttu-id="8e228-141">**顧客 AAD でリソース カタログを作成する: ID ガバナンス**</span><span class="sxs-lookup"><span data-stu-id="8e228-141">**Create a resource catalog in Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="8e228-142">リソース カタログは、テナントの顧客に作成されたアクセス パッケージADです。</span><span class="sxs-lookup"><span data-stu-id="8e228-142">Resource catalogs are a logical collection of access packages, created in the customer AD tenant.</span></span>

    <span data-ttu-id="8e228-143">これを行うには、テナントの顧客AD、Identity Governance: Catalogs にアクセスし、新しいカタログ **を追加します**。</span><span class="sxs-lookup"><span data-stu-id="8e228-143">To do so, in the customer AD tenant,  access Identity Governance: Catalogs, and add **New Catalog**.</span></span> <span data-ttu-id="8e228-144">この例では **、MSSP Accesses を呼び出します**。</span><span class="sxs-lookup"><span data-stu-id="8e228-144">In our example, we will call it **MSSP Accesses**.</span></span> 

    ![新しいカタログのイメージ](images/goverance-catalog.png)

    <span data-ttu-id="8e228-146">詳細については、「リソースのカタログ [を作成する」を参照してください](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-catalog-create)。</span><span class="sxs-lookup"><span data-stu-id="8e228-146">Further more information, see [Create a catalog of resources](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-catalog-create).</span></span>


3. <span data-ttu-id="8e228-147">**MSSP リソースのアクセス パッケージを作成する 顧客 AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="8e228-147">**Create access packages for MSSP resources Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="8e228-148">アクセス パッケージは、承認時に要求者に付与される権限とアクセスのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="8e228-148">Access packages are the collection of rights and accesses that a requestor will be granted upon approval.</span></span> 

    <span data-ttu-id="8e228-149">これを行うには、テナントの顧客AD、Identity Governance: Access Package にアクセスし、新しいアクセス パッケージ **を追加します**。</span><span class="sxs-lookup"><span data-stu-id="8e228-149">To do so, in the customer AD tenant, access Identity Governance: Access Packages, and add **New Access Package**.</span></span> <span data-ttu-id="8e228-150">MSSP 承認者と各アナリスト層のアクセス パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="8e228-150">Create an access package for the MSSP approvers and each analyst tier.</span></span> <span data-ttu-id="8e228-151">たとえば、次の Tier 1 Analyst 構成によって、次のようなアクセス パッケージが作成されます。</span><span class="sxs-lookup"><span data-stu-id="8e228-151">For example, the following Tier 1 Analyst configuration creates an access package that:</span></span>

    - <span data-ttu-id="8e228-152">新しい要求を承認するには、AD **MSSP アナリスト承認者** のメンバーが必要です。</span><span class="sxs-lookup"><span data-stu-id="8e228-152">Requires a member of the AD group **MSSP Analyst Approvers** to authorize new requests</span></span>
    - <span data-ttu-id="8e228-153">SOC アナリストがアクセス拡張機能を要求できる年次アクセス レビューがある</span><span class="sxs-lookup"><span data-stu-id="8e228-153">Has annual access reviews, where the SOC analysts can request an access extension</span></span>
    - <span data-ttu-id="8e228-154">MSSP SOC テナント内のユーザーだけが要求できる</span><span class="sxs-lookup"><span data-stu-id="8e228-154">Can only be requested by users in the MSSP SOC Tenant</span></span>
    - <span data-ttu-id="8e228-155">365 日後に自動アクセスが期限切れになる</span><span class="sxs-lookup"><span data-stu-id="8e228-155">Access auto expires after 365 days</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8e228-156">![新しいアクセス パッケージのイメージ](images/new-access-package.png)</span><span class="sxs-lookup"><span data-stu-id="8e228-156">![Image of new access package](images/new-access-package.png)</span></span>

    <span data-ttu-id="8e228-157">詳細については、「新しいアクセス [パッケージを作成する」を参照してください](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-access-package-create)。</span><span class="sxs-lookup"><span data-stu-id="8e228-157">For more information, see [Create a new access package](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-access-package-create).</span></span>


4. <span data-ttu-id="8e228-158">**顧客 AAD から MSSP リソースへのアクセス要求リンクを提供する: ID ガバナンス**</span><span class="sxs-lookup"><span data-stu-id="8e228-158">**Provide access request link to MSSP resources from Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="8e228-159">[マイ アクセス ポータル] リンクは、MSSP SOC アナリストが作成したアクセス パッケージを介してアクセスを要求するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="8e228-159">The My Access portal link is used by MSSP SOC analysts to request access via the access packages created.</span></span> <span data-ttu-id="8e228-160">リンクは永続的です。つまり、同じリンクが新しいアナリストのために時間の間に使用される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8e228-160">The link is durable, meaning the same link may be used over time for new analysts.</span></span> <span data-ttu-id="8e228-161">アナリスト要求は、MSSP アナリスト承認者による承認のためにキュー **に入ります**。</span><span class="sxs-lookup"><span data-stu-id="8e228-161">The analyst request goes into a queue for approval by the **MSSP Analyst Approvers**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8e228-162">![アクセス プロパティのイメージ](images/access-properties.png)</span><span class="sxs-lookup"><span data-stu-id="8e228-162">![Image of access properties](images/access-properties.png)</span></span>

    <span data-ttu-id="8e228-163">リンクは、各アクセス パッケージの概要ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8e228-163">The link is located on the overview page of each access package.</span></span>

## <a name="manage-access"></a><span data-ttu-id="8e228-164">アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="8e228-164">Manage access</span></span> 

1. <span data-ttu-id="8e228-165">Customer または MSSP myaccess のアクセス要求を確認および承認します。</span><span class="sxs-lookup"><span data-stu-id="8e228-165">Review and authorize access requests in Customer and/or MSSP myaccess.</span></span>

    <span data-ttu-id="8e228-166">アクセス要求は、MSSP Analyst Approvers グループのメンバーによって、お客様の My Access で管理されます。</span><span class="sxs-lookup"><span data-stu-id="8e228-166">Access requests are managed in the customer My Access, by members of the MSSP Analyst Approvers group.</span></span>

    <span data-ttu-id="8e228-167">これを行うには、次を使用して顧客の myaccess にアクセスします  `https://myaccess.microsoft.com/@<Customer Domain >` 。</span><span class="sxs-lookup"><span data-stu-id="8e228-167">To do so, access the customer's myaccess using:  `https://myaccess.microsoft.com/@<Customer Domain >`.</span></span> 

    <span data-ttu-id="8e228-168">例:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span><span class="sxs-lookup"><span data-stu-id="8e228-168">Example:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span></span>   
2. <span data-ttu-id="8e228-169">UI の [承認] セクション **で要求を** 承認または拒否します。</span><span class="sxs-lookup"><span data-stu-id="8e228-169">Approve or deny requests in the **Approvals** section of the UI.</span></span>

    <span data-ttu-id="8e228-170">この時点で、アナリスト アクセスが準備され、各アナリストが顧客の Microsoft Defender セキュリティ センターにアクセスできる必要があります。 `https://securitycenter.Microsoft.com/?tid=<CustomerTenantId>`</span><span class="sxs-lookup"><span data-stu-id="8e228-170">At this point, analyst access has been provisioned, and each analyst should be able to access the customer's Microsoft Defender Security Center: `https://securitycenter.Microsoft.com/?tid=<CustomerTenantId>`</span></span>

## <a name="related-topics"></a><span data-ttu-id="8e228-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e228-171">Related topics</span></span>
- [<span data-ttu-id="8e228-172">MSSP カスタマー ポータルにアクセスする</span><span class="sxs-lookup"><span data-stu-id="8e228-172">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="8e228-173">アラート通知の構成</span><span class="sxs-lookup"><span data-stu-id="8e228-173">Configure alert notifications</span></span>](configure-mssp-notifications.md)
- [<span data-ttu-id="8e228-174">顧客テナントからアラートを取得する</span><span class="sxs-lookup"><span data-stu-id="8e228-174">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)



 
