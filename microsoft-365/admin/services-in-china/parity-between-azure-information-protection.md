---
title: 21Vianet が運用している Office 365
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: mnirkhe
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- MET150
- GEU150
- GEA150
description: 21Vianet が運用している Office 365 の Azure Information Protection と、中国のお客様に対して構成する方法について説明します。
monikerRange: o365-21vianet
ms.openlocfilehash: a4eb8c3370a123b939fdccc53eec3905f79ee806
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42247939"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="11e77-103">21Vianet が運用している Office 365 の Azure Information Protection 間のパリティ</span><span class="sxs-lookup"><span data-stu-id="11e77-103">Parity between Azure Information Protection for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="11e77-104">21Vianet が運用している Office 365 の Azure Information Protection を使用して、中国のお客様にすべての商用機能と機能を提供することを目標としていますが、いくつかの不足している機能を強調したいと考えています。</span><span class="sxs-lookup"><span data-stu-id="11e77-104">While our goal is to deliver all commercial features and functionality to customers in China with our Azure Information Protection for Office 365 operated by 21Vianet offer, there is some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="11e77-105">次に示すのは、21Vianet が運用している Office 365 用の Azure Information Protection と、2007年 7 2019 月の商用オファーリングの間の既存のギャップです。</span><span class="sxs-lookup"><span data-stu-id="11e77-105">These are the existing gaps between Azure Information Protection for Office 365 operated by 21Vianet and our commercial offerings as of July 2019:</span></span>

- <span data-ttu-id="11e77-106">Information Rights Management (IRM) は、Office 365 ProPlus (ビルド11731.10000 以降) に対してのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="11e77-106">Information Rights Management (IRM) is supported only for Office 365 ProPlus (build 11731.10000 or higher).</span></span> <span data-ttu-id="11e77-107">Office 2010、Office 2013、およびその他の Office 2016 バージョンはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="11e77-107">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="11e77-108">Active Directory Rights Management サービス (AD RMS) から Azure Information Protection への移行は現在使用できません。</span><span class="sxs-lookup"><span data-stu-id="11e77-108">Migration from Active Directory Rights Management Services (AD RMS) to Azure Information Protection is currently not available.</span></span>
  
- <span data-ttu-id="11e77-109">保護された電子メールを商用クラウド内のユーザーに共有することがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="11e77-109">Sharing of protected emails to users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="11e77-110">ドキュメントと電子メールの添付ファイルを商用クラウドのユーザーに共有することは現在使用できません。</span><span class="sxs-lookup"><span data-stu-id="11e77-110">Sharing of documents and email attachments to users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="11e77-111">これには、商用クラウドの21Vianet ユーザーが運用している Office 365、商用クラウドの21Vianet ユーザーが運用している非 Office 365、および個人ライセンスの RMS を使用するユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="11e77-111">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="11e77-112">SharePoint を使用した IRM (IRM で保護されたサイトおよびライブラリ) は現在使用できません。</span><span class="sxs-lookup"><span data-stu-id="11e77-112">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="11e77-113">Rights Management コネクタは現在使用できません。</span><span class="sxs-lookup"><span data-stu-id="11e77-113">The Rights Management Connector is currently not available.</span></span>
  
- <span data-ttu-id="11e77-114">AD RMS のモバイルデバイス拡張機能は現在使用できません。</span><span class="sxs-lookup"><span data-stu-id="11e77-114">The Mobile Device Extension for AD RMS is currently not available.</span></span>

## <a name="configuring-azure-information-protection-for-customers-in-china"></a><span data-ttu-id="11e77-115">中国のお客様向けに Azure Information Protection を構成する</span><span class="sxs-lookup"><span data-stu-id="11e77-115">Configuring Azure Information Protection for customers in China</span></span>

### <a name="enable-rights-management-for-the-tenant"></a><span data-ttu-id="11e77-116">テナントの Rights Management を有効にする</span><span class="sxs-lookup"><span data-stu-id="11e77-116">Enable Rights Management for the tenant</span></span>

<span data-ttu-id="11e77-117">暗号化を正しく動作させるには、テナントに対して RMS を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="11e77-117">For the encryption to work correctly, the RMS must be enabled for the tenant.</span></span>

- <span data-ttu-id="11e77-118">RMS が有効になっているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="11e77-118">Check if the RMS is enabled:</span></span>
  1. <span data-ttu-id="11e77-119">PowerShell を管理者として起動します。</span><span class="sxs-lookup"><span data-stu-id="11e77-119">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="11e77-120">AIPService モジュールがインストールされていない `Install-Module AipService`場合は、を実行します。</span><span class="sxs-lookup"><span data-stu-id="11e77-120">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="11e77-121">を使用して`Import-Module AipService`モジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="11e77-121">Import the module using `Import-Module AipService`.</span></span>
  4. <span data-ttu-id="11e77-122">を使用して `Connect-AipService -environmentname azurechinacloud`サービスに接続します。</span><span class="sxs-lookup"><span data-stu-id="11e77-122">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  5. <span data-ttu-id="11e77-123">を `(Get-AipServiceConfiguration).FunctionalState` 実行し、状態が `Enabled`であるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="11e77-123">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

- <span data-ttu-id="11e77-124">機能状態がの場合 `Disabled`は、 `Enable-AipService`を実行します。</span><span class="sxs-lookup"><span data-stu-id="11e77-124">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="dns-configuration-for-encryption-windows"></a><span data-ttu-id="11e77-125">暗号化の DNS 構成 (Windows)</span><span class="sxs-lookup"><span data-stu-id="11e77-125">DNS configuration for encryption (Windows)</span></span>

<span data-ttu-id="11e77-126">暗号化が正常に機能するためには、Office クライアントアプリケーションは、サービスの中国のインスタンスと、そこからブートストラップに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="11e77-126">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="11e77-127">クライアントアプリケーションを適切なサービスインスタンスにリダイレクトするには、テナント管理者が Azure RMS URL に関する情報を使用して DNS SRV レコードを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="11e77-127">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="11e77-128">DNS SRV レコードがない場合、クライアントアプリケーションは既定でパブリッククラウドインスタンスへの接続を試行しますが、失敗します。</span><span class="sxs-lookup"><span data-stu-id="11e77-128">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="11e77-129">また、ユーザーはテナント所有のドメイン (たとえば、 `joe@contoso.cn`) ではなく`onmschina` 、ユーザー名を使用してログインすることを前提としています (例`joe@contoso.onmschina.cn`:)。</span><span class="sxs-lookup"><span data-stu-id="11e77-129">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="11e77-130">Username のドメイン名は、適切なサービスインスタンスへの DNS リダイレクトに使用されます。</span><span class="sxs-lookup"><span data-stu-id="11e77-130">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

- <span data-ttu-id="11e77-131">RMS ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="11e77-131">Get the RMS ID:</span></span>
  1. <span data-ttu-id="11e77-132">PowerShell を管理者として起動します。</span><span class="sxs-lookup"><span data-stu-id="11e77-132">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="11e77-133">AIPService モジュールがインストールされていない `Install-Module AipService`場合は、を実行します。</span><span class="sxs-lookup"><span data-stu-id="11e77-133">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="11e77-134">を使用して `Connect-AipService -environmentname azurechinacloud`サービスに接続します。</span><span class="sxs-lookup"><span data-stu-id="11e77-134">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  4. <span data-ttu-id="11e77-135">を `(Get-AipServiceConfiguration).RightsManagementServiceId` 実行して RMS ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="11e77-135">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

- <span data-ttu-id="11e77-136">DNS プロバイダーにログインし、ドメインの DNS 設定に移動して、新しい SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="11e77-136">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="11e77-137">サービス = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="11e77-137">Service = `_rmsredir`</span></span>
  - <span data-ttu-id="11e77-138">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="11e77-138">Protocol = `_http`</span></span>
  - <span data-ttu-id="11e77-139">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="11e77-139">Name = `_tcp`</span></span>
  - <span data-ttu-id="11e77-140">Target = `[GUID].rms.aadrm.cn` (GUID は RMS ID です)</span><span class="sxs-lookup"><span data-stu-id="11e77-140">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
  - <span data-ttu-id="11e77-141">Priority、Weight、Seconds、TTL = 既定値</span><span class="sxs-lookup"><span data-stu-id="11e77-141">Priority, Weight, Seconds, TTL = default values</span></span>

- <span data-ttu-id="11e77-142"> [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)のテナントにカスタムドメインを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="11e77-142">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="11e77-143">DNS にエントリが追加されます。これにより、DNS 設定に値を追加した後に、確認に数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="11e77-143">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

- <span data-ttu-id="11e77-144">対応するグローバル管理者の資格情報を使用して Microsoft 365 管理センターにログインし、ドメインを`contoso.cn`追加します (例:)。</span><span class="sxs-lookup"><span data-stu-id="11e77-144">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="11e77-145">検証プロセスでは、追加の DNS 変更が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="11e77-145">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="11e77-146">確認が完了したら、ユーザーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="11e77-146">Once verification is done, users can be created.</span></span>

### <a name="dns-configuration-for-encryption-mac-ios-android"></a><span data-ttu-id="11e77-147">暗号化の DNS 構成 (Mac、iOS、Android)</span><span class="sxs-lookup"><span data-stu-id="11e77-147">DNS configuration for encryption (Mac, iOS, Android)</span></span>

- <span data-ttu-id="11e77-148">DNS プロバイダーにログインし、ドメインの DNS 設定に移動して、新しい SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="11e77-148">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="11e77-149">サービス = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="11e77-149">Service = `_rmsdisco`</span></span>
  - <span data-ttu-id="11e77-150">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="11e77-150">Protocol = `_http`</span></span>
  - <span data-ttu-id="11e77-151">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="11e77-151">Name = `_tcp`</span></span>
  - <span data-ttu-id="11e77-152">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="11e77-152">Target = `api.aadrm.cn`</span></span>
  - <span data-ttu-id="11e77-153">ポート = `80`</span><span class="sxs-lookup"><span data-stu-id="11e77-153">Port = `80`</span></span>
  - <span data-ttu-id="11e77-154">Priority、Weight、Seconds、TTL = 既定値</span><span class="sxs-lookup"><span data-stu-id="11e77-154">Priority, Weight, Seconds, TTL = default values</span></span>
