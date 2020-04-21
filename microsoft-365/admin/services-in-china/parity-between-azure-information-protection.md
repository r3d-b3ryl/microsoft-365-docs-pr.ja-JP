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
ms.openlocfilehash: 3d24b450cc9ba9a6427732d408e35af1394b4a34
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627656"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="aeece-103">21Vianet が運用している Office 365 の Azure Information Protection 間のパリティ</span><span class="sxs-lookup"><span data-stu-id="aeece-103">Parity between Azure Information Protection for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="aeece-104">21Vianet が運用している Office 365 の Azure Information Protection を使用して、中国のお客様にすべての商用機能と機能を提供することを目標としていますが、いくつかの不足している機能を強調したいと考えています。</span><span class="sxs-lookup"><span data-stu-id="aeece-104">While our goal is to deliver all commercial features and functionality to customers in China with our Azure Information Protection for Office 365 operated by 21Vianet offer, there is some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="aeece-105">次に示すのは、21Vianet が運用している Office 365 用の Azure Information Protection と、2007年 7 2019 月の商用オファーリングの間の既存のギャップです。</span><span class="sxs-lookup"><span data-stu-id="aeece-105">These are the existing gaps between Azure Information Protection for Office 365 operated by 21Vianet and our commercial offerings as of July 2019:</span></span>

- <span data-ttu-id="aeece-106">Information Rights Management (IRM) は、Microsoft 365 Apps for enterprise (ビルド11731.10000 以降) に対してのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="aeece-106">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="aeece-107">Office 2010、Office 2013、およびその他の Office 2016 バージョンはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="aeece-107">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="aeece-108">Active Directory Rights Management サービス (AD RMS) から Azure Information Protection への移行は現在使用できません。</span><span class="sxs-lookup"><span data-stu-id="aeece-108">Migration from Active Directory Rights Management Services (AD RMS) to Azure Information Protection is currently not available.</span></span>
  
- <span data-ttu-id="aeece-109">保護された電子メールを商用クラウド内のユーザーに共有することがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="aeece-109">Sharing of protected emails to users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="aeece-110">ドキュメントと電子メールの添付ファイルを商用クラウドのユーザーに共有することは現在使用できません。</span><span class="sxs-lookup"><span data-stu-id="aeece-110">Sharing of documents and email attachments to users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="aeece-111">これには、商用クラウドの21Vianet ユーザーが運用している Office 365、商用クラウドの21Vianet ユーザーが運用している非 Office 365、および個人ライセンスの RMS を使用するユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="aeece-111">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="aeece-112">SharePoint を使用した IRM (IRM で保護されたサイトおよびライブラリ) は現在使用できません。</span><span class="sxs-lookup"><span data-stu-id="aeece-112">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="aeece-113">Rights Management コネクタは現在使用できません。</span><span class="sxs-lookup"><span data-stu-id="aeece-113">The Rights Management Connector is currently not available.</span></span>
  
- <span data-ttu-id="aeece-114">AD RMS のモバイルデバイス拡張機能は現在使用できません。</span><span class="sxs-lookup"><span data-stu-id="aeece-114">The Mobile Device Extension for AD RMS is currently not available.</span></span>

## <a name="configuring-azure-information-protection-for-customers-in-china"></a><span data-ttu-id="aeece-115">中国のお客様向けに Azure Information Protection を構成する</span><span class="sxs-lookup"><span data-stu-id="aeece-115">Configuring Azure Information Protection for customers in China</span></span>

### <a name="enable-rights-management-for-the-tenant"></a><span data-ttu-id="aeece-116">テナントの Rights Management を有効にする</span><span class="sxs-lookup"><span data-stu-id="aeece-116">Enable Rights Management for the tenant</span></span>

<span data-ttu-id="aeece-117">暗号化を正しく動作させるには、テナントに対して RMS を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="aeece-117">For the encryption to work correctly, the RMS must be enabled for the tenant.</span></span>

- <span data-ttu-id="aeece-118">RMS が有効になっているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="aeece-118">Check if the RMS is enabled:</span></span>
  1. <span data-ttu-id="aeece-119">PowerShell を管理者として起動します。</span><span class="sxs-lookup"><span data-stu-id="aeece-119">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="aeece-120">AIPService モジュールがインストールされていない `Install-Module AipService`場合は、を実行します。</span><span class="sxs-lookup"><span data-stu-id="aeece-120">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="aeece-121">を使用して`Import-Module AipService`モジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="aeece-121">Import the module using `Import-Module AipService`.</span></span>
  4. <span data-ttu-id="aeece-122">を使用して `Connect-AipService -environmentname azurechinacloud`サービスに接続します。</span><span class="sxs-lookup"><span data-stu-id="aeece-122">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  5. <span data-ttu-id="aeece-123">を `(Get-AipServiceConfiguration).FunctionalState` 実行し、状態が `Enabled`であるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="aeece-123">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

- <span data-ttu-id="aeece-124">機能状態がの場合 `Disabled`は、 `Enable-AipService`を実行します。</span><span class="sxs-lookup"><span data-stu-id="aeece-124">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="dns-configuration-for-encryption-windows"></a><span data-ttu-id="aeece-125">暗号化の DNS 構成 (Windows)</span><span class="sxs-lookup"><span data-stu-id="aeece-125">DNS configuration for encryption (Windows)</span></span>

<span data-ttu-id="aeece-126">暗号化が正常に機能するためには、Office クライアントアプリケーションは、サービスの中国のインスタンスと、そこからブートストラップに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aeece-126">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="aeece-127">クライアントアプリケーションを適切なサービスインスタンスにリダイレクトするには、テナント管理者が Azure RMS URL に関する情報を使用して DNS SRV レコードを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aeece-127">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="aeece-128">DNS SRV レコードがない場合、クライアントアプリケーションは既定でパブリッククラウドインスタンスへの接続を試行しますが、失敗します。</span><span class="sxs-lookup"><span data-stu-id="aeece-128">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="aeece-129">また、ユーザーはテナント所有のドメイン (たとえば、 `joe@contoso.cn`) ではなく`onmschina` 、ユーザー名を使用してログインすることを前提としています (例`joe@contoso.onmschina.cn`:)。</span><span class="sxs-lookup"><span data-stu-id="aeece-129">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="aeece-130">Username のドメイン名は、適切なサービスインスタンスへの DNS リダイレクトに使用されます。</span><span class="sxs-lookup"><span data-stu-id="aeece-130">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

- <span data-ttu-id="aeece-131">RMS ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="aeece-131">Get the RMS ID:</span></span>
  1. <span data-ttu-id="aeece-132">PowerShell を管理者として起動します。</span><span class="sxs-lookup"><span data-stu-id="aeece-132">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="aeece-133">AIPService モジュールがインストールされていない `Install-Module AipService`場合は、を実行します。</span><span class="sxs-lookup"><span data-stu-id="aeece-133">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="aeece-134">を使用して `Connect-AipService -environmentname azurechinacloud`サービスに接続します。</span><span class="sxs-lookup"><span data-stu-id="aeece-134">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  4. <span data-ttu-id="aeece-135">を `(Get-AipServiceConfiguration).RightsManagementServiceId` 実行して RMS ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="aeece-135">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

- <span data-ttu-id="aeece-136">DNS プロバイダーにログインし、ドメインの DNS 設定に移動して、新しい SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="aeece-136">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="aeece-137">サービス = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="aeece-137">Service = `_rmsredir`</span></span>
  - <span data-ttu-id="aeece-138">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="aeece-138">Protocol = `_http`</span></span>
  - <span data-ttu-id="aeece-139">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="aeece-139">Name = `_tcp`</span></span>
  - <span data-ttu-id="aeece-140">Target = `[GUID].rms.aadrm.cn` (GUID は RMS ID です)</span><span class="sxs-lookup"><span data-stu-id="aeece-140">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
  - <span data-ttu-id="aeece-141">Priority、Weight、Seconds、TTL = 既定値</span><span class="sxs-lookup"><span data-stu-id="aeece-141">Priority, Weight, Seconds, TTL = default values</span></span>

- <span data-ttu-id="aeece-142"> [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)のテナントにカスタムドメインを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="aeece-142">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="aeece-143">DNS にエントリが追加されます。これにより、DNS 設定に値を追加した後に、確認に数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="aeece-143">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

- <span data-ttu-id="aeece-144">対応するグローバル管理者の資格情報を使用して Microsoft 365 管理センターにログインし、ドメインを`contoso.cn`追加します (例:)。</span><span class="sxs-lookup"><span data-stu-id="aeece-144">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="aeece-145">検証プロセスでは、追加の DNS 変更が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="aeece-145">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="aeece-146">確認が完了したら、ユーザーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="aeece-146">Once verification is done, users can be created.</span></span>

### <a name="dns-configuration-for-encryption-mac-ios-android"></a><span data-ttu-id="aeece-147">暗号化の DNS 構成 (Mac、iOS、Android)</span><span class="sxs-lookup"><span data-stu-id="aeece-147">DNS configuration for encryption (Mac, iOS, Android)</span></span>

- <span data-ttu-id="aeece-148">DNS プロバイダーにログインし、ドメインの DNS 設定に移動して、新しい SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="aeece-148">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="aeece-149">サービス = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="aeece-149">Service = `_rmsdisco`</span></span>
  - <span data-ttu-id="aeece-150">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="aeece-150">Protocol = `_http`</span></span>
  - <span data-ttu-id="aeece-151">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="aeece-151">Name = `_tcp`</span></span>
  - <span data-ttu-id="aeece-152">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="aeece-152">Target = `api.aadrm.cn`</span></span>
  - <span data-ttu-id="aeece-153">ポート = `80`</span><span class="sxs-lookup"><span data-stu-id="aeece-153">Port = `80`</span></span>
  - <span data-ttu-id="aeece-154">Priority、Weight、Seconds、TTL = 既定値</span><span class="sxs-lookup"><span data-stu-id="aeece-154">Priority, Weight, Seconds, TTL = default values</span></span>
