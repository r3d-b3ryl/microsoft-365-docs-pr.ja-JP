---
title: 21Vianet が運用している Office 365 の Azure Information Protection 間のパリティ
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEU150
- GEA150
description: 21Vianet が運用している Office 365 の Azure Information Protection と、中国のお客様に対して構成する方法について説明します。
monikerRange: o365-21vianet
ms.openlocfilehash: 7be40466c43a49cf51a2a2c1c273cef035bee831
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519343"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="4d867-103">21Vianet が運用している Office 365 の Azure Information Protection 間のパリティ</span><span class="sxs-lookup"><span data-stu-id="4d867-103">Parity between Azure Information Protection for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="4d867-104">21Vianet が運用している Office 365 の Azure Information Protection を使用して、中国のお客様にすべての商用機能と機能を提供することを目標としていますが、いくつかの不足している機能を強調したいと考えています。</span><span class="sxs-lookup"><span data-stu-id="4d867-104">While our goal is to deliver all commercial features and functionality to customers in China with our Azure Information Protection for Office 365 operated by 21Vianet offer, there is some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="4d867-105">次の一覧には、21Vianet が運用している Office 365 用の Azure Information Protection と、2007 2019 年7月の商用オファーリングの間の既存のギャップが記載されています。</span><span class="sxs-lookup"><span data-stu-id="4d867-105">The following list includes the existing gaps between Azure Information Protection for Office 365 operated by 21Vianet and our commercial offerings as of July 2019:</span></span>

- <span data-ttu-id="4d867-106">Information Rights Management (IRM) は、Microsoft 365 Apps for enterprise (ビルド11731.10000 以降) に対してのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4d867-106">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="4d867-107">Office 2010、Office 2013、およびその他の Office 2016 バージョンはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4d867-107">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="4d867-108">Active Directory Rights Management サービス (AD RMS) から Azure Information Protection への移行は現在使用できません。</span><span class="sxs-lookup"><span data-stu-id="4d867-108">Migration from Active Directory Rights Management Services (AD RMS) to Azure Information Protection is currently not available.</span></span>
  
- <span data-ttu-id="4d867-109">保護された電子メールを商用クラウド内のユーザーに共有することがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4d867-109">Sharing of protected emails to users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="4d867-110">ドキュメントと電子メールの添付ファイルを商用クラウドのユーザーに共有することは現在使用できません。</span><span class="sxs-lookup"><span data-stu-id="4d867-110">Sharing of documents and email attachments to users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="4d867-111">これには、商用クラウドの21Vianet ユーザーが運用している Office 365、商用クラウドの21Vianet ユーザーが運用している非 Office 365、および個人ライセンスの RMS を使用するユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4d867-111">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="4d867-112">SharePoint を使用した IRM (IRM で保護されたサイトおよびライブラリ) は現在使用できません。</span><span class="sxs-lookup"><span data-stu-id="4d867-112">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="4d867-113">AD RMS のモバイルデバイス拡張機能は現在使用できません。</span><span class="sxs-lookup"><span data-stu-id="4d867-113">The Mobile Device Extension for AD RMS is currently not available.</span></span>

## <a name="configuring-azure-information-protection-for-customers-in-china"></a><span data-ttu-id="4d867-114">中国のお客様向けに Azure Information Protection を構成する</span><span class="sxs-lookup"><span data-stu-id="4d867-114">Configuring Azure Information Protection for customers in China</span></span>

### <a name="enable-rights-management-for-the-tenant"></a><span data-ttu-id="4d867-115">テナントの Rights Management を有効にする</span><span class="sxs-lookup"><span data-stu-id="4d867-115">Enable Rights Management for the tenant</span></span>

<span data-ttu-id="4d867-116">暗号化を正しく動作させるには、テナントに対して RMS を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d867-116">For the encryption to work correctly, the RMS must be enabled for the tenant.</span></span>

- <span data-ttu-id="4d867-117">RMS が有効になっているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="4d867-117">Check if the RMS is enabled:</span></span>
  1. <span data-ttu-id="4d867-118">PowerShell を管理者として起動します。</span><span class="sxs-lookup"><span data-stu-id="4d867-118">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="4d867-119">AIPService モジュールがインストールされていない場合は、を実行 `Install-Module AipService` します。</span><span class="sxs-lookup"><span data-stu-id="4d867-119">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="4d867-120">を使用してモジュールをインポートし `Import-Module AipService` ます。</span><span class="sxs-lookup"><span data-stu-id="4d867-120">Import the module using `Import-Module AipService`.</span></span>
  4. <span data-ttu-id="4d867-121">を使用してサービスに接続し `Connect-AipService -environmentname azurechinacloud` ます。</span><span class="sxs-lookup"><span data-stu-id="4d867-121">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  5. <span data-ttu-id="4d867-122">を実行 `(Get-AipServiceConfiguration).FunctionalState` し、状態がであるかどうかを確認し `Enabled` ます。</span><span class="sxs-lookup"><span data-stu-id="4d867-122">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

- <span data-ttu-id="4d867-123">機能状態がの場合は `Disabled` 、を実行 `Enable-AipService` します。</span><span class="sxs-lookup"><span data-stu-id="4d867-123">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="dns-configuration-for-encryption-windows"></a><span data-ttu-id="4d867-124">暗号化の DNS 構成 (Windows)</span><span class="sxs-lookup"><span data-stu-id="4d867-124">DNS configuration for encryption (Windows)</span></span>

<span data-ttu-id="4d867-125">暗号化が正常に機能するためには、Office クライアントアプリケーションは、サービスの中国のインスタンスと、そこからブートストラップに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d867-125">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="4d867-126">クライアントアプリケーションを適切なサービスインスタンスにリダイレクトするには、テナント管理者が Azure RMS URL に関する情報を使用して DNS SRV レコードを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d867-126">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="4d867-127">DNS SRV レコードがない場合、クライアントアプリケーションは既定でパブリッククラウドインスタンスへの接続を試行しますが、失敗します。</span><span class="sxs-lookup"><span data-stu-id="4d867-127">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="4d867-128">また、ユーザーはテナント所有のドメイン (たとえば、) ではなく、ユーザー名を使用してログインすることを前提としています (例:) `joe@contoso.cn` `onmschina` `joe@contoso.onmschina.cn` 。</span><span class="sxs-lookup"><span data-stu-id="4d867-128">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="4d867-129">Username のドメイン名は、適切なサービスインスタンスへの DNS リダイレクトに使用されます。</span><span class="sxs-lookup"><span data-stu-id="4d867-129">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

- <span data-ttu-id="4d867-130">RMS ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="4d867-130">Get the RMS ID:</span></span>
  1. <span data-ttu-id="4d867-131">PowerShell を管理者として起動します。</span><span class="sxs-lookup"><span data-stu-id="4d867-131">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="4d867-132">AIPService モジュールがインストールされていない場合は、を実行 `Install-Module AipService` します。</span><span class="sxs-lookup"><span data-stu-id="4d867-132">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="4d867-133">を使用してサービスに接続し `Connect-AipService -environmentname azurechinacloud` ます。</span><span class="sxs-lookup"><span data-stu-id="4d867-133">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  4. <span data-ttu-id="4d867-134">を実行し `(Get-AipServiceConfiguration).RightsManagementServiceId` て RMS ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="4d867-134">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

- <span data-ttu-id="4d867-135">DNS プロバイダーにログインし、ドメインの DNS 設定に移動して、新しい SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="4d867-135">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="4d867-136">サービス = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="4d867-136">Service = `_rmsredir`</span></span>
  - <span data-ttu-id="4d867-137">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="4d867-137">Protocol = `_http`</span></span>
  - <span data-ttu-id="4d867-138">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="4d867-138">Name = `_tcp`</span></span>
  - <span data-ttu-id="4d867-139">Target = `[GUID].rms.aadrm.cn` (GUID は RMS ID です)</span><span class="sxs-lookup"><span data-stu-id="4d867-139">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
  - <span data-ttu-id="4d867-140">Priority、Weight、Seconds、TTL = 既定値</span><span class="sxs-lookup"><span data-stu-id="4d867-140">Priority, Weight, Seconds, TTL = default values</span></span>

- <span data-ttu-id="4d867-141">[Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)のテナントにカスタムドメインを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="4d867-141">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="4d867-142">DNS にエントリが追加されます。これにより、DNS 設定に値を追加した後に、確認に数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4d867-142">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

- <span data-ttu-id="4d867-143">対応するグローバル管理者の資格情報を使用して Microsoft 365 管理センターにログインし、ドメインを追加します (例: `contoso.cn` )。</span><span class="sxs-lookup"><span data-stu-id="4d867-143">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="4d867-144">検証プロセスでは、追加の DNS 変更が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="4d867-144">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="4d867-145">確認が完了したら、ユーザーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="4d867-145">Once verification is done, users can be created.</span></span>

### <a name="dns-configuration-for-encryption-mac-ios-android"></a><span data-ttu-id="4d867-146">暗号化の DNS 構成 (Mac、iOS、Android)</span><span class="sxs-lookup"><span data-stu-id="4d867-146">DNS configuration for encryption (Mac, iOS, Android)</span></span>

- <span data-ttu-id="4d867-147">DNS プロバイダーにログインし、ドメインの DNS 設定に移動して、新しい SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="4d867-147">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="4d867-148">サービス = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="4d867-148">Service = `_rmsdisco`</span></span>
  - <span data-ttu-id="4d867-149">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="4d867-149">Protocol = `_http`</span></span>
  - <span data-ttu-id="4d867-150">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="4d867-150">Name = `_tcp`</span></span>
  - <span data-ttu-id="4d867-151">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="4d867-151">Target = `api.aadrm.cn`</span></span>
  - <span data-ttu-id="4d867-152">ポート = `80`</span><span class="sxs-lookup"><span data-stu-id="4d867-152">Port = `80`</span></span>
  - <span data-ttu-id="4d867-153">Priority、Weight、Seconds、TTL = 既定値</span><span class="sxs-lookup"><span data-stu-id="4d867-153">Priority, Weight, Seconds, TTL = default values</span></span>
