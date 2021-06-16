---
title: Microsoft Cloud Deutschland からの移行の移行後のアクティビティ
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
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
description: '概要: 移行後のアクティビティは、Microsoft Cloud Germany (Microsoft Cloud Deutschland) から新しいドイツのデータセンター地域Office 365サービスに移行した後です。'
ms.openlocfilehash: 3659ce8ffa3424c3521c8f8954be88c7d53d0a51
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930417"
---
# <a name="post-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="6a197-103">Microsoft Cloud Deutschland からの移行の移行後のアクティビティ</span><span class="sxs-lookup"><span data-stu-id="6a197-103">Post-migration activities for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="6a197-104">次のセクションでは、Microsoft Cloud Germany (Microsoft Cloud Deutschland) から新しいドイツデータセンター地域の Office 365 サービスに移行した後、複数のサービスの移行後のアクティビティを提供します。</span><span class="sxs-lookup"><span data-stu-id="6a197-104">The following sections provide post-migration activities for multiple services after moving from Microsoft Cloud Germany (Microsoft Cloud Deutschland) to Office 365 services in the new German datacenter region.</span></span>

## <a name="azure-ad"></a><span data-ttu-id="6a197-105">Azure AD</span><span class="sxs-lookup"><span data-stu-id="6a197-105">Azure AD</span></span>
<!-- This AAD Endpoints comparison table could be added to the documentation, not finally decided.
### Azure AD Endpoints
**Applies to:** All customers

After the cut over to Azure AD is complete, the organization is fully using Office 365 services and is no longer connected to Microsoft Cloud Deutschland and the endpoints cannot be used anymore. At this point, the customer needs to ensure that all applications are using the endpoints for the new German datacenter region.
The following table provides an overview about which endpoints will replace the previously used endpoints in Microsoft Cloud Germany (Microsoft Cloud Deutschland). 

|Endpoint in Microsoft Cloud Germany  |Endpoint in the new German datacenter region  |
|:---------|:---------|
|becws.microsoftonline.de<br>provisioningapi.microsoftonline.de |becws.microsoftonline.com<br>provisioningapi.microsoftonline.com |
|adminwebservice.microsoftonline.de |adminwebservice.microsoftonline.com |
|login.microsoftonline.de<br>logincert.microsoftonline.de<br>sts.microsoftonline.de |login.microsoftonline.com<br>login.windows.net<br>logincert.microsoftonline.com<br>accounts.accesscontrol.windows.net |
|enterpriseregistration.microsoftonline.de |enterpriseregistration.windows.net |
|graph.cloudapi.de |graph.windows.net |
|graph.microsoft.de |graph.microsoft.com |
|||
-->

### <a name="azure-ad-federated-authentication-with-ad-fs"></a><span data-ttu-id="6a197-106">Azure AD FS とのフェデレーションAD認証</span><span class="sxs-lookup"><span data-stu-id="6a197-106">Azure AD federated authentication with AD FS</span></span>
<span data-ttu-id="6a197-107">**適用対象:** FS とのフェデレーション認証を使用AD顧客</span><span class="sxs-lookup"><span data-stu-id="6a197-107">**Applies to:** All customers using federated authentication with AD FS</span></span>

| <span data-ttu-id="6a197-108">Step(s)</span><span class="sxs-lookup"><span data-stu-id="6a197-108">Step(s)</span></span> | <span data-ttu-id="6a197-109">説明</span><span class="sxs-lookup"><span data-stu-id="6a197-109">Description</span></span> | <span data-ttu-id="6a197-110">影響</span><span class="sxs-lookup"><span data-stu-id="6a197-110">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="6a197-111">Microsoft Cloud Deutschland および FS から証明書利用者の信頼AD削除します。</span><span class="sxs-lookup"><span data-stu-id="6a197-111">Remove relying party trusts from Microsoft Cloud Deutschland AD FS.</span></span> | <span data-ttu-id="6a197-112">Azure への切りADが完了すると、組織は Office 365 サービスを完全に使用し、Microsoft Cloud Deutschland に接続されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="6a197-112">After the cut-over to Azure AD is complete, the organization is fully using Office 365 services and is no longer connected to Microsoft Cloud Deutschland.</span></span> <span data-ttu-id="6a197-113">この時点で、顧客は Microsoft Cloud Deutschland エンドポイントに対する証明書利用者の信頼を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a197-113">At this point, the customer needs to remove the relying party trust to the Microsoft Cloud Deutschland endpoints.</span></span> <span data-ttu-id="6a197-114">これは、Azure AD が ID プロバイダー (IdP) として活用されている場合にのみ、お客様のアプリケーションが Microsoft Cloud Deutschland エンドポイントをポイントしない場合にのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="6a197-114">This can only be done when none of the customer's applications points to Microsoft Cloud Deutschland endpoints when Azure AD is leveraged as an Identity Provider (IdP).</span></span> | <span data-ttu-id="6a197-115">フェデレーション認証組織</span><span class="sxs-lookup"><span data-stu-id="6a197-115">Federated Authentication organizations</span></span> | 
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
### <a name="group-approvals"></a><span data-ttu-id="6a197-116">グループの承認</span><span class="sxs-lookup"><span data-stu-id="6a197-116">Group approvals</span></span>
<span data-ttu-id="6a197-117">**適用対象:** 移行前の過去 30 日間に Azure AD承認要求が承認されなかったエンド ユーザー</span><span class="sxs-lookup"><span data-stu-id="6a197-117">**Applies to:** End-users whose Azure AD group approval requests weren't approved in the last 30 days before migration</span></span> 

| <span data-ttu-id="6a197-118">Step(s)</span><span class="sxs-lookup"><span data-stu-id="6a197-118">Step(s)</span></span> | <span data-ttu-id="6a197-119">説明</span><span class="sxs-lookup"><span data-stu-id="6a197-119">Description</span></span> | <span data-ttu-id="6a197-120">影響</span><span class="sxs-lookup"><span data-stu-id="6a197-120">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="6a197-121">移行前の過去 30 日間に Azure AD グループに参加する要求は、元の要求が承認されなかった場合は、再度要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a197-121">Requests to join an Azure AD group in the last 30 days before migration will need to be requested again if the original request wasn't approved.</span></span> | <span data-ttu-id="6a197-122">移行前の過去 30 日間にこれらの要求が承認されなかった場合、エンドユーザーのお客様は Access パネルを使用して Azure AD グループに再度参加する要求を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a197-122">End-user customers will need to use the Access panel to submit a request to join an Azure AD group again if those requests weren't approved in the last 30 days before the migration.</span></span> |  <span data-ttu-id="6a197-123">エンド ユーザーとして次の情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="6a197-123">As an end-user:</span></span> <ol><li><span data-ttu-id="6a197-124">[アクセス] [パネルに移動します](https://account.activedirectory.windowsazure.com/r#/joinGroups)。</span><span class="sxs-lookup"><span data-stu-id="6a197-124">Navigate to [Access panel](https://account.activedirectory.windowsazure.com/r#/joinGroups).</span></span></li><li><span data-ttu-id="6a197-125">移行前 30 ADの間にメンバーシップの承認が保留された Azure ユーザー グループを検索します。</span><span class="sxs-lookup"><span data-stu-id="6a197-125">Find an Azure AD group for which membership approval was pending during the 30 days before migration.</span></span></li><li><span data-ttu-id="6a197-126">Azure ADへの参加を要求します。</span><span class="sxs-lookup"><span data-stu-id="6a197-126">Request to join the Azure AD group again.</span></span></li></ol> <span data-ttu-id="6a197-127">移行の 30 日未満前にアクティブなグループに参加する要求は、移行後に再度要求されていない限り、承認できません。</span><span class="sxs-lookup"><span data-stu-id="6a197-127">Requests to join a group that are active less than 30 days before migration cannot be approved, unless they're requested again after migration.</span></span> |
||||

## <a name="custom-dns-updates"></a><span data-ttu-id="6a197-128">カスタム DNS 更新プログラム</span><span class="sxs-lookup"><span data-stu-id="6a197-128">Custom DNS updates</span></span>
<span data-ttu-id="6a197-129">**適用対象:**  自分の DNS ゾーンを管理しているすべての顧客</span><span class="sxs-lookup"><span data-stu-id="6a197-129">**Applies to:**  All customer managing their own DNS zones</span></span>

| <span data-ttu-id="6a197-130">Step(s)</span><span class="sxs-lookup"><span data-stu-id="6a197-130">Step(s)</span></span> | <span data-ttu-id="6a197-131">説明</span><span class="sxs-lookup"><span data-stu-id="6a197-131">Description</span></span> | <span data-ttu-id="6a197-132">影響</span><span class="sxs-lookup"><span data-stu-id="6a197-132">Impact</span></span> |
|:------|:-------|:-------|
| <span data-ttu-id="6a197-133">サービス エンドポイントのオンプレミス DNS サービスOffice 365更新します。</span><span class="sxs-lookup"><span data-stu-id="6a197-133">Update on-premises DNS services for Office 365 services endpoints.</span></span> | <span data-ttu-id="6a197-134">Microsoft Cloud Deutschland を指す顧客管理 DNS エントリは、グローバル サービス エンドポイントをポイントOffice 365更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a197-134">Customer-managed DNS entries that point to Microsoft Cloud Deutschland need to be updated to point to the Office 365 Global services endpoints.</span></span> <span data-ttu-id="6a197-135">管理センターの[[ドメイン] Microsoft 365参照し](https://admin.microsoft.com/Adminportal/Home#/Domains)、DNS 構成に変更を適用してください。</span><span class="sxs-lookup"><span data-stu-id="6a197-135">Please refer to [Domains in the Microsoft 365 admin center](https://admin.microsoft.com/Adminportal/Home#/Domains) and apply the changes in your DNS configuration.</span></span> | <span data-ttu-id="6a197-136">サービスまたはソフトウェア クライアントの障害が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6a197-136">Failure to do so may result in failure of the service or of software clients.</span></span> |
||||

## <a name="third-party-services"></a><span data-ttu-id="6a197-137">サード パーティのサービス</span><span class="sxs-lookup"><span data-stu-id="6a197-137">Third-party services</span></span>
<span data-ttu-id="6a197-138">**適用対象:** サービス エンドポイントにサードパーティ サービスを使用Office 365顧客</span><span class="sxs-lookup"><span data-stu-id="6a197-138">**Applies to:** Customers using third-party services for Office 365 services endpoints</span></span>

| <span data-ttu-id="6a197-139">Step(s)</span><span class="sxs-lookup"><span data-stu-id="6a197-139">Step(s)</span></span> | <span data-ttu-id="6a197-140">説明</span><span class="sxs-lookup"><span data-stu-id="6a197-140">Description</span></span> | <span data-ttu-id="6a197-141">影響</span><span class="sxs-lookup"><span data-stu-id="6a197-141">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="6a197-142">パートナーとサード パーティのサービスを、Office 365エンドポイントに更新します。</span><span class="sxs-lookup"><span data-stu-id="6a197-142">Update partners and third-party services for Office 365 services endpoints.</span></span> | <ul><li><span data-ttu-id="6a197-143">ドイツを指すサードパーティのサービスOffice 365パートナーは、サービス エンドポイントをポイントOffice 365する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a197-143">Third-party services and partners that point to Office 365 Germany need to be updated to point to the Office 365 services endpoints.</span></span> <span data-ttu-id="6a197-144">例: 利用可能な場合は、ベンダーやパートナーと連携して、ギャラリー アプリのバージョンのアプリケーションを再登録します。</span><span class="sxs-lookup"><span data-stu-id="6a197-144">Example: Re-register, in alignment with your vendors and partners, the gallery app version of applications, if available.</span></span> </li><li><span data-ttu-id="6a197-145">API を利用するカスタム アプリケーションGraphをポイント `graph.microsoft.de` します `graph.microsoft.com` 。</span><span class="sxs-lookup"><span data-stu-id="6a197-145">Point all custom applications that leverage Graph API from `graph.microsoft.de` to `graph.microsoft.com`.</span></span> <span data-ttu-id="6a197-146">エンドポイントが変更された他の API も、活用する場合は更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a197-146">Other APIs with changed endpoints also need to be updated, if leveraged.</span></span> </li><li><span data-ttu-id="6a197-147">すべてのファースト パーティ以外のエンタープライズ アプリケーションを変更して、世界中のエンドポイントにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="6a197-147">Change all non-first-party enterprise applications to redirect to the worldwide endpoints.</span></span> </li></ul>| <span data-ttu-id="6a197-148">必須のアクション。</span><span class="sxs-lookup"><span data-stu-id="6a197-148">Required action.</span></span> <span data-ttu-id="6a197-149">サービスまたはソフトウェア クライアントの障害が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6a197-149">Failure to do so may result in failure of the service or of software clients.</span></span> |
||||