---
title: Azure Active Directory テナントの詳細
description: このトピックでは、Microsoft マネージドデスクトップに登録するときに AAD アカウントに加えられた変更について説明します。
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: 6b2b30d8dedba1086bfa9268fb0fdbce20367c20
ms.sourcegitcommit: dd426c686b52cf79325f11022b2d99bc45285577
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2019
ms.locfileid: "35643948"
---
# <a name="azure-active-directory-tenant-details"></a><span data-ttu-id="cc75e-104">Azure Active Directory テナントの詳細</span><span class="sxs-lookup"><span data-stu-id="cc75e-104">Azure Active Directory tenant details</span></span>
<span data-ttu-id="cc75e-105">{gory (アカウント、API 呼び出し、アクセス許可など) についての詳細。</span><span class="sxs-lookup"><span data-stu-id="cc75e-105">{gory details about accounts, API calls, perms, etc., etc.}</span></span>


## <a name="data-transmitted-to-and-from-your-aad-account"></a><span data-ttu-id="cc75e-106">AAD アカウントとの間で転送されるデータ</span><span class="sxs-lookup"><span data-stu-id="cc75e-106">Data transmitted to and from your AAD account</span></span>


<span data-ttu-id="cc75e-107">Microsoft からアカウントに送信されるデータは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cc75e-107">Data sent to your account from Microsoft:</span></span>

- <span data-ttu-id="cc75e-108">グループ名</span><span class="sxs-lookup"><span data-stu-id="cc75e-108">Group names</span></span>
- <span data-ttu-id="cc75e-109">セキュリティポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="cc75e-109">Security policy configuration</span></span>
- <span data-ttu-id="cc75e-110">デバイスの注文</span><span class="sxs-lookup"><span data-stu-id="cc75e-110">Device orders</span></span>
- <span data-ttu-id="cc75e-111">ユーザーアカウント (msadmin、mstest、mwaas_soc_ro、mwaas_wdgsoc)</span><span class="sxs-lookup"><span data-stu-id="cc75e-111">User accounts (msadmin, mstest, mwaas_soc_ro, mwaas_wdgsoc)</span></span>
- <span data-ttu-id="cc75e-112">ユーザーアカウントへの E5 ライセンスの割り当て</span><span class="sxs-lookup"><span data-stu-id="cc75e-112">E5 License assignment to the user accounts</span></span>
- <span data-ttu-id="cc75e-113">更新リングの Windows update ポリシー</span><span class="sxs-lookup"><span data-stu-id="cc75e-113">Windows update policies for update rings</span></span>

<span data-ttu-id="cc75e-114">お客様のアカウントから Microsoft に送信されるデータは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cc75e-114">Data sent to Microsoft from your account:</span></span>

- <span data-ttu-id="cc75e-115">デバイスの更新、使用状況、および信頼性のデータ</span><span class="sxs-lookup"><span data-stu-id="cc75e-115">Device update, usage and reliability data</span></span>
- <span data-ttu-id="cc75e-116">アプリの展開と信頼性のデータ</span><span class="sxs-lookup"><span data-stu-id="cc75e-116">App deployment and reliability data</span></span>
- <span data-ttu-id="cc75e-117">更新およびセキュリティポリシーの展開データ</span><span class="sxs-lookup"><span data-stu-id="cc75e-117">Update and security policy deployment data</span></span>
- <span data-ttu-id="cc75e-118">デバイスに割り当てられているユーザー</span><span class="sxs-lookup"><span data-stu-id="cc75e-118">Users assigned to devices</span></span>  

<span data-ttu-id="cc75e-119">アカウントから送信されるデータは、米国でホストされている Microsoft テナントの Azure SQL データベースに格納されます。</span><span class="sxs-lookup"><span data-stu-id="cc75e-119">Data transmitted from your account is stored in Azure SQL databases in the Microsoft tenant hosted in the USA.</span></span> <span data-ttu-id="cc75e-120">データは、「Microsoft Azure セキュリティ}」に記載されているポリシーに従って保存および処理されます。</span><span class="sxs-lookup"><span data-stu-id="cc75e-120">Data is stored and handled in accordance the policies described in {Microsoft Azure security}.</span></span> 

## <a name="api-permissions-and-calls"></a><span data-ttu-id="cc75e-121">API のアクセス許可と呼び出し</span><span class="sxs-lookup"><span data-stu-id="cc75e-121">API permissions and calls</span></span>

<span data-ttu-id="cc75e-122">**登録中:**</span><span class="sxs-lookup"><span data-stu-id="cc75e-122">**During enrollment:**</span></span>

<span data-ttu-id="cc75e-123">API のアクセス許可:</span><span class="sxs-lookup"><span data-stu-id="cc75e-123">API permissions:</span></span>
- <span data-ttu-id="cc75e-124">DeviceManagementServiceConfig.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="cc75e-124">DeviceManagementServiceConfig.ReadWrite.All</span></span>
- <span data-ttu-id="cc75e-125">Directory.AccessAsUser.All</span><span class="sxs-lookup"><span data-stu-id="cc75e-125">Directory.AccessAsUser.All</span></span>
- <span data-ttu-id="cc75e-126">User.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="cc75e-126">User.ReadWrite.All</span></span>
- <span data-ttu-id="cc75e-127">DeviceManagementConfiguration.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="cc75e-127">DeviceManagementConfiguration.ReadWrite.All</span></span>
- <span data-ttu-id="cc75e-128">DeviceManagementManagedDevices.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="cc75e-128">DeviceManagementManagedDevices.ReadWrite.All</span></span>
- <span data-ttu-id="cc75e-129">Group.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="cc75e-129">Group.ReadWrite.All</span></span>

<span data-ttu-id="cc75e-130">API 呼び出し:</span><span class="sxs-lookup"><span data-stu-id="cc75e-130">API calls:</span></span>
- <span data-ttu-id="cc75e-131">POST/organization/{organizationId}/setMobileDeviceManagementAuthority</span><span class="sxs-lookup"><span data-stu-id="cc75e-131">POST /organization/{organizationId}/setMobileDeviceManagementAuthority</span></span>
- <span data-ttu-id="cc75e-132">メンバーの取得/投稿/ディレクトリの取得/{2}</span><span class="sxs-lookup"><span data-stu-id="cc75e-132">GET/POST /directoryRoles/{id}/members</span></span>
- <span data-ttu-id="cc75e-133">GET/POST/users</span><span class="sxs-lookup"><span data-stu-id="cc75e-133">GET/POST /users</span></span>
- <span data-ttu-id="cc75e-134">取得/投稿/グループ</span><span class="sxs-lookup"><span data-stu-id="cc75e-134">GET/POST /groups</span></span>
- <span data-ttu-id="cc75e-135">PATCH/グループ/{\* id}</span><span class="sxs-lookup"><span data-stu-id="cc75e-135">PATCH /groups/{id}</span></span>
- <span data-ttu-id="cc75e-136">取得/ポスト/Devicemanagement/deviceconfigurた。</span><span class="sxs-lookup"><span data-stu-id="cc75e-136">GET/POST /deviceManagement/deviceConfigurations</span></span>
- <span data-ttu-id="cc75e-137">/DeviceManagement/detectedApps を取得する</span><span class="sxs-lookup"><span data-stu-id="cc75e-137">GET /deviceManagement/detectedApps</span></span>

<span data-ttu-id="cc75e-138">**登録後、通常の管理では、次のようになります。**</span><span class="sxs-lookup"><span data-stu-id="cc75e-138">**After enrollment, during ordinary management:**</span></span>

<span data-ttu-id="cc75e-139">API のアクセス許可:</span><span class="sxs-lookup"><span data-stu-id="cc75e-139">API permissions:</span></span>
- <span data-ttu-id="cc75e-140">DeviceManagementManagedDevices.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="cc75e-140">DeviceManagementManagedDevices.ReadWrite.All</span></span>
- <span data-ttu-id="cc75e-141">DeviceManagementApps.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="cc75e-141">DeviceManagementApps.ReadWrite.All</span></span>
- <span data-ttu-id="cc75e-142">DeviceManagementConfiguration.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="cc75e-142">DeviceManagementConfiguration.ReadWrite.All</span></span>
- <span data-ttu-id="cc75e-143">Reports.Read.All</span><span class="sxs-lookup"><span data-stu-id="cc75e-143">Reports.Read.All</span></span>
- <span data-ttu-id="cc75e-144">User.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="cc75e-144">User.ReadWrite.All</span></span>
- <span data-ttu-id="cc75e-145">Group.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="cc75e-145">Group.ReadWrite.All</span></span>
- <span data-ttu-id="cc75e-146">Directory.AccessAsUser.All</span><span class="sxs-lookup"><span data-stu-id="cc75e-146">Directory.AccessAsUser.All</span></span>

<span data-ttu-id="cc75e-147">API 呼び出し:</span><span class="sxs-lookup"><span data-stu-id="cc75e-147">API calls:</span></span>
- <span data-ttu-id="cc75e-148">メンバーの取得/投稿/ディレクトリの取得/{2}</span><span class="sxs-lookup"><span data-stu-id="cc75e-148">GET/POST /directoryRoles/{id}/members</span></span>
- <span data-ttu-id="cc75e-149">GET/PATCH/POST/users</span><span class="sxs-lookup"><span data-stu-id="cc75e-149">GET/PATCH/POST /users</span></span>
- <span data-ttu-id="cc75e-150">取得/投稿/グループ</span><span class="sxs-lookup"><span data-stu-id="cc75e-150">GET/POST /groups</span></span>
- <span data-ttu-id="cc75e-151">PATCH/グループ/{\* id}</span><span class="sxs-lookup"><span data-stu-id="cc75e-151">PATCH /groups/{id}</span></span>
- <span data-ttu-id="cc75e-152">取得/ポスト/Devicemanagement/deviceconfigurた。</span><span class="sxs-lookup"><span data-stu-id="cc75e-152">GET/POST /deviceManagement/deviceConfigurations</span></span>
- <span data-ttu-id="cc75e-153">GET/POST/deviceAppManagement/mobileApps</span><span class="sxs-lookup"><span data-stu-id="cc75e-153">GET/POST /deviceAppManagement/mobileApps</span></span>
- <span data-ttu-id="cc75e-154">/DeviceManagement/detectedApps を取得する</span><span class="sxs-lookup"><span data-stu-id="cc75e-154">GET /deviceManagement/detectedApps</span></span>
- <span data-ttu-id="cc75e-155">/Devices を取得する</span><span class="sxs-lookup"><span data-stu-id="cc75e-155">GET /devices</span></span>
- <span data-ttu-id="cc75e-156">投稿/ユーザー/{id | userPrincipalName}/割り当てライセンス</span><span class="sxs-lookup"><span data-stu-id="cc75e-156">POST /users/{id | userPrincipalName}/assignLicense</span></span>
- <span data-ttu-id="cc75e-157">/SubscribedSkus を取得する</span><span class="sxs-lookup"><span data-stu-id="cc75e-157">GET /subscribedSkus</span></span>

## <a name="accounts-used-by-microsoft-managed-desktop"></a><span data-ttu-id="cc75e-158">Microsoft マネージドデスクトップで使用されるアカウント</span><span class="sxs-lookup"><span data-stu-id="cc75e-158">Accounts used by Microsoft Managed Desktop</span></span>





| <span data-ttu-id="cc75e-159">アカウント</span><span class="sxs-lookup"><span data-stu-id="cc75e-159">Account</span></span> | <span data-ttu-id="cc75e-160">説明</span><span class="sxs-lookup"><span data-stu-id="cc75e-160">Description</span></span>  | <span data-ttu-id="cc75e-161">条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="cc75e-161">Conditional access</span></span>  | <span data-ttu-id="cc75e-162">多要素認証</span><span class="sxs-lookup"><span data-stu-id="cc75e-162">Multi-factor authentication</span></span>  | <span data-ttu-id="cc75e-163">これが OK な理由</span><span class="sxs-lookup"><span data-stu-id="cc75e-163">Why this is OK</span></span> |
|---------|---------|---------|---------|--------------|
| <span data-ttu-id="cc75e-164">msadmin @ \* onmmicrosoft .com</span><span class="sxs-lookup"><span data-stu-id="cc75e-164">msadmin@\*onmmicrosoft.com</span></span> | <span data-ttu-id="cc75e-165">管理者特権を持つ制限付きサービスアカウント。 Microsoft Intune およびユーザー管理者として使用されます。 {これは何ですか?}</span><span class="sxs-lookup"><span data-stu-id="cc75e-165">Limited service account with administrator privileges, used as a Microsoft Intune and User administrator {what's this?}</span></span> <span data-ttu-id="cc75e-166">Microsoft モダンデスクトップデバイスのテナントを定義して構成するには</span><span class="sxs-lookup"><span data-stu-id="cc75e-166">to define and configure the tenant for Microsoft Modern Desktop devices.</span></span><span data-ttu-id="cc75e-167">には、対話的なログイン権限がありません。サービスを使用してのみ操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="cc75e-167">  Does not have interactive login permissions; performs operations only through the service.</span></span>  | <span data-ttu-id="cc75e-168">ネットワークで発生しないため、除外されます。</span><span class="sxs-lookup"><span data-stu-id="cc75e-168">Excluded, because it doesn't originate in your network</span></span>        | <span data-ttu-id="cc75e-169">対話型ログオンがないため、除外されます。</span><span class="sxs-lookup"><span data-stu-id="cc75e-169">Excluded because there is no interactive logon</span></span>        | <span data-ttu-id="cc75e-170">Azure Key Vault に格納されたパスワード</span><span class="sxs-lookup"><span data-stu-id="cc75e-170">Password stored in Azure Key Vault</span></span> |
| <span data-ttu-id="cc75e-171">mstest @ \* onmmicrosoft .com</span><span class="sxs-lookup"><span data-stu-id="cc75e-171">mstest@\*onmmicrosoft.com</span></span>     |         |         |         |
| <span data-ttu-id="cc75e-172">mssupport @ \* onmmicrosoft .com</span><span class="sxs-lookup"><span data-stu-id="cc75e-172">mssupport@\*onmmicrosoft.com</span></span>     |         |         |         |
| <span data-ttu-id="cc75e-173">msadminint @ \* onmmicrosoft .com</span><span class="sxs-lookup"><span data-stu-id="cc75e-173">msadminint@\*onmmicrosoft.com</span></span>     |         |         |         |
