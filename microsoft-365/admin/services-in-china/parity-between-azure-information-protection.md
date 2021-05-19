---
title: 21Vianet がOffice 365 Azure Information Protection のサポート
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
description: 21Vianet が運用する 21Vianet Office 365 Azure Information Protection (AIP) の詳細と、中国の顧客向け構成方法について説明します。
monikerRange: o365-21vianet
ms.openlocfilehash: 8b85ae43df31bb1947b841d616cc83c3a0b614e4
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535844"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a><span data-ttu-id="fe4dc-103">21Vianet がOffice 365 Azure Information Protection のサポート</span><span class="sxs-lookup"><span data-stu-id="fe4dc-103">Azure Information Protection support for Office 365 operated by 21Vianet</span></span>

<span data-ttu-id="fe4dc-104">この記事では、21Vianet と商用製品が運用する Office 365 の Azure Information Protection (AIP) サポートの違い、および AIP オンプレミス スキャナーのインストール方法やコンテンツ スキャン ジョブの管理方法など、中国のお客様向け AIP を構成するための具体的な手順について説明します。 &mdash;</span><span class="sxs-lookup"><span data-stu-id="fe4dc-104">This article covers the differences between Azure Information Protection (AIP) support for Office 365 operated by 21Vianet and commercial offerings, as well as specific instructions for configuring AIP for customers in China&mdash;including how to install the AIP on-premises scanner and manage content scan jobs.</span></span>

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="fe4dc-105">21Vianet がOffice 365する AIP と商用サービスの違い</span><span class="sxs-lookup"><span data-stu-id="fe4dc-105">Differences between AIP for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="fe4dc-106">21Vianet オファーが運用する Office 365 の AIP を使用して、中国のすべての商用機能と機能を中国のお客様に提供しますが、強調表示する機能が不足しています。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-106">While our goal is to deliver all commercial features and functionality to customers in China with our AIP for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="fe4dc-107">次の一覧には、21Vianet が運用する 2021 Office 365の AIP と 2021 年 1 月の商用製品との間の既存のギャップが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-107">The following list includes the existing gaps between AIP for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="fe4dc-108">Information Rights Management (IRM) は、Microsoft 365 Apps for enterprise (ビルド 11731.10000 以上) でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-108">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="fe4dc-109">Office 2010、Office 2013、その他Office 2016 バージョンはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-109">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="fe4dc-110">現在、Active Directory Rights Management サービス (AD RMS) から AIP への移行は使用できません。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-110">Migration from Active Directory Rights Management Services (AD RMS) to AIP is currently not available.</span></span>
  
- <span data-ttu-id="fe4dc-111">商用クラウド内のユーザーとの保護されたメールの共有がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-111">Sharing of protected emails with users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="fe4dc-112">現在、商用クラウド内のユーザーとのドキュメントと電子メールの添付ファイルの共有は利用できません。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-112">Sharing of documents and email attachments with users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="fe4dc-113">これには、Office 365クラウド内の 21Vianet ユーザーが運用するユーザー、商用クラウド内の 21Vianet ユーザーが運用する Office 365 以外のユーザー、および RMS for Individuals ライセンスを持つユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-113">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="fe4dc-114">IRM と SharePoint (IRM で保護されたサイトとライブラリ) は現在使用できません。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-114">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="fe4dc-115">現在、RMS のモバイル AD拡張機能は使用できません。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-115">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="fe4dc-116">モバイル [ビューアーは](/azure/information-protection/rms-client/mobile-app-faq) Azure China 21Vianet ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-116">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

- <span data-ttu-id="fe4dc-117">Azure ポータルの AIP 領域は、中国のお客様が利用できません。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-117">The AIP area of the Azure portal is unavailable to customers in China.</span></span> <span data-ttu-id="fe4dc-118">コンテンツ [スキャン ジョブの](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) 管理や実行など、ポータルでアクションを実行する代わりに PowerShell コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-118">Use [PowerShell commands](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) instead of performing actions in the portal, such as managing and running your content scan jobs.</span></span>

## <a name="configure-aip-for-customers-in-china"></a><span data-ttu-id="fe4dc-119">中国の顧客向け AIP の構成</span><span class="sxs-lookup"><span data-stu-id="fe4dc-119">Configure AIP for customers in China</span></span>

<span data-ttu-id="fe4dc-120">中国の顧客向け AIP を構成するには、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-120">To configure AIP for customers in China:</span></span>
1. <span data-ttu-id="fe4dc-121">[テナントの権限管理を有効にします](#step-1-enable-rights-management-for-the-tenant)。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-121">[Enable Rights Management for the tenant](#step-1-enable-rights-management-for-the-tenant).</span></span>

1. <span data-ttu-id="fe4dc-122">[Microsoft Information Protection Sync Service サービス プリンシパルを追加します](#step-2-add-the-microsoft-information-protection-sync-service-service-principal)。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-122">[Add the Microsoft Information Protection Sync Service service principal](#step-2-add-the-microsoft-information-protection-sync-service-service-principal).</span></span>

1. <span data-ttu-id="fe4dc-123">[DNS 暗号化を構成します](#step-3-configure-dns-encryption)。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-123">[Configure DNS encryption](#step-3-configure-dns-encryption).</span></span>

1. <span data-ttu-id="fe4dc-124">[AIP 統合ラベル 付けクライアントをインストールして構成します](#step-4-install-and-configure-the-aip-unified-labeling-client)。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-124">[Install and configure the AIP unified labeling client](#step-4-install-and-configure-the-aip-unified-labeling-client).</span></span>

1. <span data-ttu-id="fe4dc-125">[アプリで AIP アプリを構成Windows。](#step-5-configure-aip-apps-on-windows)</span><span class="sxs-lookup"><span data-stu-id="fe4dc-125">[Configure AIP apps on Windows](#step-5-configure-aip-apps-on-windows).</span></span>

1. <span data-ttu-id="fe4dc-126">[AIP オンプレミス スキャナーをインストールし、コンテンツ スキャン ジョブを管理します](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-126">[Install the AIP on-premises scanner and manage content scan jobs](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs).</span></span> 

### <a name="step-1-enable-rights-management-for-the-tenant"></a><span data-ttu-id="fe4dc-127">手順 1: テナントの権限管理を有効にする</span><span class="sxs-lookup"><span data-stu-id="fe4dc-127">Step 1: Enable Rights Management for the tenant</span></span>

<span data-ttu-id="fe4dc-128">暗号化が正しく機能するには、テナントで RMS を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-128">For the encryption to work correctly, RMS must be enabled for the tenant.</span></span>

1. <span data-ttu-id="fe4dc-129">RMS が有効になっているか確認します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-129">Check if RMS is enabled:</span></span>

    1. <span data-ttu-id="fe4dc-130">管理者として PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-130">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="fe4dc-131">AIPService モジュールがインストールされていない場合は、実行します `Install-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-131">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="fe4dc-132">を使用してモジュールをインポート `Import-Module AipService` します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-132">Import the module using `Import-Module AipService`.</span></span>
    4. <span data-ttu-id="fe4dc-133">Connectを使用してサービスにアクセスします `Connect-AipService -environmentname azurechinacloud` 。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-133">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    5. <span data-ttu-id="fe4dc-134">状態 `(Get-AipServiceConfiguration).FunctionalState` が . `Enabled`</span><span class="sxs-lookup"><span data-stu-id="fe4dc-134">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

2. <span data-ttu-id="fe4dc-135">機能状態がである場合は `Disabled` 、実行します `Enable-AipService` 。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-135">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="step-2-add-the-microsoft-information-protection-sync-service-service-principal"></a><span data-ttu-id="fe4dc-136">手順 2: Microsoft Information Protection Sync Service サービス プリンシパルを追加する</span><span class="sxs-lookup"><span data-stu-id="fe4dc-136">Step 2: Add the Microsoft Information Protection Sync Service service principal</span></span>

<span data-ttu-id="fe4dc-137">**Microsoft Information Protection Sync Service サービス** プリンシパルは、Azure China テナントでは既定では使用できません。Azure Information Protection では必須です。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-137">The **Microsoft Information Protection Sync Service** service principal is not available in Azure China tenants by default, and is required for Azure Information Protection.</span></span>

1. <span data-ttu-id="fe4dc-138">[New-AzADServicePrincipal](/powershell/module/az.resources/new-azadserviceprincipal)コマンドレットと Microsoft Information Protection Sync Service のアプリケーション ID を使用して、このサービス プリンシパルを手動 `870c4f2e-85b6-4d43-bdda-6ed9a579b725` で作成します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-138">Create this service principal manually using the [New-AzADServicePrincipal](/powershell/module/az.resources/new-azadserviceprincipal) cmdlet and the `870c4f2e-85b6-4d43-bdda-6ed9a579b725` application ID for the Microsoft Information Protection Sync Service.</span></span> 

    ```powershell 
    New-AzADServicePrincipal -ApplicationId 870c4f2e-85b6-4d43-bdda-6ed9a579b725
    ```

1. <span data-ttu-id="fe4dc-139">サービス プリンシパルを追加した後、サービスに必要な関連するアクセス許可を追加します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-139">After adding the service principal, add the relevant permissions required to the service.</span></span>

### <a name="step-3-configure-dns-encryption"></a><span data-ttu-id="fe4dc-140">手順 3: DNS 暗号化を構成する</span><span class="sxs-lookup"><span data-stu-id="fe4dc-140">Step 3: Configure DNS encryption</span></span>

<span data-ttu-id="fe4dc-141">暗号化が正しく動作するにはOfficeクライアント アプリケーションは、サービスの中国インスタンスに接続し、そこからブートストラップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-141">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="fe4dc-142">クライアント アプリケーションを適切なサービス インスタンスにリダイレクトするには、テナント管理者が Azure RMS URL に関する情報を含む DNS SRV レコードを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-142">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="fe4dc-143">DNS SRV レコードがない場合、クライアント アプリケーションは既定でパブリック クラウド インスタンスへの接続を試み、失敗します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-143">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="fe4dc-144">また、テナントが所有するドメイン (たとえば) に基づいてユーザー名を使用してログインし、ユーザー名 (たとえば) でログインしないという前提 `joe@contoso.cn` `onmschina` があります `joe@contoso.onmschina.cn` 。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-144">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="fe4dc-145">ユーザー名のドメイン名は、正しいサービス インスタンスへの DNS リダイレクトに使用されます。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-145">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

#### <a name="configure-dns-encryption---windows"></a><span data-ttu-id="fe4dc-146">DNS 暗号化の構成 - Windows</span><span class="sxs-lookup"><span data-stu-id="fe4dc-146">Configure DNS encryption - Windows</span></span>

1. <span data-ttu-id="fe4dc-147">RMS ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-147">Get the RMS ID:</span></span>

    1. <span data-ttu-id="fe4dc-148">管理者として PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-148">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="fe4dc-149">AIPService モジュールがインストールされていない場合は、実行します `Install-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-149">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="fe4dc-150">Connectを使用してサービスにアクセスします `Connect-AipService -environmentname azurechinacloud` 。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-150">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    4. <span data-ttu-id="fe4dc-151">RMS `(Get-AipServiceConfiguration).RightsManagementServiceId` ID を取得するために実行します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-151">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

2. <span data-ttu-id="fe4dc-152">DNS プロバイダーにログインし、ドメインの DNS 設定に移動し、新しい SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-152">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

    - <span data-ttu-id="fe4dc-153">サービス = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="fe4dc-153">Service = `_rmsredir`</span></span>
    - <span data-ttu-id="fe4dc-154">プロトコル = `_http`</span><span class="sxs-lookup"><span data-stu-id="fe4dc-154">Protocol = `_http`</span></span>
    - <span data-ttu-id="fe4dc-155">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="fe4dc-155">Name = `_tcp`</span></span>
    - <span data-ttu-id="fe4dc-156">Target = `[GUID].rms.aadrm.cn` (GUID は RMS ID)</span><span class="sxs-lookup"><span data-stu-id="fe4dc-156">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
    - <span data-ttu-id="fe4dc-157">優先度、重み、秒、TTL = 既定値</span><span class="sxs-lookup"><span data-stu-id="fe4dc-157">Priority, Weight, Seconds, TTL = default values</span></span>

3. <span data-ttu-id="fe4dc-158">Azure portal のテナントにカスタム ドメインを関連 [付ける](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-158">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="fe4dc-159">これにより、DNS のエントリが追加され、DNS 設定に値を追加した後に検証に数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-159">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

4. <span data-ttu-id="fe4dc-160">対応するグローバル管理者資格情報Microsoft 365管理センターにログインし、ユーザー作成用のドメイン (たとえば `contoso.cn` ) を追加します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-160">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="fe4dc-161">検証プロセスでは、追加の DNS 変更が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-161">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="fe4dc-162">検証が完了すると、ユーザーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-162">Once verification is done, users can be created.</span></span>

#### <a name="configure-dns-encryption---mac-ios-android"></a><span data-ttu-id="fe4dc-163">DNS 暗号化の構成 - Mac、iOS、Android</span><span class="sxs-lookup"><span data-stu-id="fe4dc-163">Configure DNS encryption - Mac, iOS, Android</span></span>

<span data-ttu-id="fe4dc-164">DNS プロバイダーにログインし、ドメインの DNS 設定に移動し、新しい SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-164">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="fe4dc-165">サービス = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="fe4dc-165">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="fe4dc-166">プロトコル = `_http`</span><span class="sxs-lookup"><span data-stu-id="fe4dc-166">Protocol = `_http`</span></span>
- <span data-ttu-id="fe4dc-167">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="fe4dc-167">Name = `_tcp`</span></span>
- <span data-ttu-id="fe4dc-168">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="fe4dc-168">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="fe4dc-169">Port = `80`</span><span class="sxs-lookup"><span data-stu-id="fe4dc-169">Port = `80`</span></span>
- <span data-ttu-id="fe4dc-170">優先度、重み、秒、TTL = 既定値</span><span class="sxs-lookup"><span data-stu-id="fe4dc-170">Priority, Weight, Seconds, TTL = default values</span></span>


### <a name="step-4-install-and-configure-the-aip-unified-labeling-client"></a><span data-ttu-id="fe4dc-171">手順 4: AIP 統合ラベル 付けクライアントをインストールして構成する</span><span class="sxs-lookup"><span data-stu-id="fe4dc-171">Step 4: Install and configure the AIP unified labeling client</span></span>

<span data-ttu-id="fe4dc-172">Microsoft ダウンロード センターから AIP 統合ラベル 付けクライアントを [ダウンロードしてインストールします](https://www.microsoft.com/download/details.aspx?id=53018)。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-172">Download and install the AIP unified labeling client from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="fe4dc-173">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-173">For more information, see:</span></span>

- [<span data-ttu-id="fe4dc-174">AIP ドキュメント</span><span class="sxs-lookup"><span data-stu-id="fe4dc-174">AIP documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="fe4dc-175">AIP バージョンの履歴とサポート ポリシー</span><span class="sxs-lookup"><span data-stu-id="fe4dc-175">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="fe4dc-176">AIP システム要件</span><span class="sxs-lookup"><span data-stu-id="fe4dc-176">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="fe4dc-177">AIP クイック スタート: AIP クライアントを展開する</span><span class="sxs-lookup"><span data-stu-id="fe4dc-177">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="fe4dc-178">AIP 管理者ガイド</span><span class="sxs-lookup"><span data-stu-id="fe4dc-178">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="fe4dc-179">AIP ユーザー ガイド</span><span class="sxs-lookup"><span data-stu-id="fe4dc-179">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="fe4dc-180">感度ラベルMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="fe4dc-180">Learn about Microsoft 365 sensitivity labels</span></span>](../../compliance/sensitivity-labels.md)

### <a name="step-5-configure-aip-apps-on-windows"></a><span data-ttu-id="fe4dc-181">手順 5: アプリで AIP アプリを構成Windows</span><span class="sxs-lookup"><span data-stu-id="fe4dc-181">Step 5: Configure AIP apps on Windows</span></span>

<span data-ttu-id="fe4dc-182">Azure China のWindowsソブリン クラウドをポイントするには、次のレジストリ キーが必要です。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-182">AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="fe4dc-183">レジストリ ノード = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="fe4dc-183">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="fe4dc-184">Name = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="fe4dc-184">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="fe4dc-185">値 = `6` (既定値 = 0)</span><span class="sxs-lookup"><span data-stu-id="fe4dc-185">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="fe4dc-186">Type = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="fe4dc-186">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fe4dc-187">アンインストール後にレジストリ キーを削除しない必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-187">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="fe4dc-188">キーが空、正しくない、または存在しない場合、機能は既定値 (商用クラウドの既定値 = 0) として動作します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-188">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="fe4dc-189">キーが空または正しくない場合は、印刷エラーもログに追加されます。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-189">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a><span data-ttu-id="fe4dc-190">手順 6: AIP オンプレミス スキャナーをインストールし、コンテンツ スキャン ジョブを管理する</span><span class="sxs-lookup"><span data-stu-id="fe4dc-190">Step 6: Install the AIP on-premises scanner and manage content scan jobs</span></span>

<span data-ttu-id="fe4dc-191">AIP オンプレミス スキャナーをインストールして、ネットワークとコンテンツ共有の機密データをスキャンし、組織のポリシーで構成されている分類ラベルと保護ラベルを適用します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-191">Install the AIP on-premises scanner to scan your network and content shares for sensitive data, and apply classification and protection labels as configured in your organization's policy.</span></span>

<span data-ttu-id="fe4dc-192">コンテンツ スキャン ジョブを構成および管理する場合は、商用サービスで使用される [Azure ポータル](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only) インターフェイスの代わりに、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-192">When configuring and managing your content scan jobs, use the following procedure instead of the [Azure portal interface](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only) that's used by the commercial offerings.</span></span>

<span data-ttu-id="fe4dc-193">詳細については、「Azure Information Protection 統合ラベル スキャナーとは」および [「PowerShell](/azure/information-protection/deploy-aip-scanner) のみを使用してコンテンツ スキャン ジョブを管理する」 [を参照してください](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-193">For more information, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) and [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>

<span data-ttu-id="fe4dc-194">**スキャナーをインストールして構成するには、次の手順を実行します**。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-194">**To install and configure your scanner**:</span></span>

1. <span data-ttu-id="fe4dc-195">スキャナーを実行するWindowsサーバー コンピューターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-195">Sign in to the Windows Server computer that will run the scanner.</span></span> <span data-ttu-id="fe4dc-196">ローカル管理者権限を持ち、マスター データベースに書き込む権限を持つアカウントSQL Server使用します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-196">Use an account that has local administrator rights and that has permissions to write to the SQL Server master database.</span></span>

1. <span data-ttu-id="fe4dc-197">PowerShell を閉じた状態で開始します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-197">Start with PowerShell closed.</span></span> <span data-ttu-id="fe4dc-198">以前に AIP クライアントとスキャナーをインストールした場合は **、AIPScanner** サービスが停止されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-198">If you've previously installed the AIP client and scanner, make sure that the **AIPScanner** service is stopped.</span></span>

1. <span data-ttu-id="fe4dc-199">[管理者としてWindows PowerShell] オプションを使用して、**セッションを開** きます。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-199">Open a Windows PowerShell session with the **Run as an administrator** option.</span></span>

1. <span data-ttu-id="fe4dc-200">[Install-AIPScanner](/powershell/module/azureinformationprotection/Install-AIPScanner)コマンドレットを実行し、Azure Information Protection スキャナー用のデータベースを作成する SQL Server インスタンスと、スキャナー クラスターのわかりやすい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-200">Run the [Install-AIPScanner](/powershell/module/azureinformationprotection/Install-AIPScanner) cmdlet, specifying your SQL Server instance on which to create a database for the Azure Information Protection scanner, and a meaningful name for your scanner cluster.</span></span>

    ```PowerShell
    Install-AIPScanner -SqlServerInstance <name> -Cluster <cluster name>
    ```

    > [!TIP]
    > <span data-ttu-id="fe4dc-201">[Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner)コマンドで同じクラスター名を使用して、複数のスキャナー ノードを同じクラスターに関連付けできます。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-201">You can use the same cluster name in the [Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) command to associate multiple scanner nodes to the same cluster.</span></span> <span data-ttu-id="fe4dc-202">複数のスキャナー ノードに同じクラスターを使用すると、複数のスキャナーを組み合わせてスキャンを実行できます。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-202">Using the same cluster for multiple scanner nodes enables multiple scanners to work together to perform your scans.</span></span>
    > 

1. <span data-ttu-id="fe4dc-203">管理ツール サービスを使用してサービスがインストール **されていることを確認**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-203">Verify that the service is now installed by using **Administrative Tools** > **Services**.</span></span>

    <span data-ttu-id="fe4dc-204">インストールされているサービスの名前は **Azure Information Protection Scanner** で、作成したスキャナー サービス アカウントを使用して実行するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-204">The installed service is named **Azure Information Protection Scanner** and is configured to run by using the scanner service account that you created.</span></span>

1. <span data-ttu-id="fe4dc-205">スキャナーで使用する Azure トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-205">Get an Azure token to use with your scanner.</span></span> <span data-ttu-id="fe4dc-206">Azure ADトークンを使用すると、スキャナーは Azure Information Protection サービスに対して認証を行い、スキャナーを非対話的に実行できます。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-206">An Azure AD token allows the scanner to authenticate to the Azure Information Protection service, enabling the scanner to run non-interactively.</span></span> 

    1. <span data-ttu-id="fe4dc-207">Azure portal を開き、Azure ADアプリケーションを作成して、認証用のアクセス トークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-207">Open the Azure portal and create an Azure AD application to specify an access token for authentication.</span></span> <span data-ttu-id="fe4dc-208">詳細については [、「Azure Information Protection 用に対話](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)的にファイルにラベルを付ける方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-208">For more information, see [How to label files non-interactively for Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).</span></span>
    
        > [!TIP]
        > <span data-ttu-id="fe4dc-209">[Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication)コマンド用に Azure AD アプリケーションを作成および構成する場合、[API のアクセス許可の要求] ウィンドウには **、[Microsoft** **API]** タブではなく [組織で使用する API] タブが表示されます。組織が **使用する API を選択し、[Azure** **Rights Management Services] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-209">When creating and configuring Azure AD applications for the [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) command, the **Request API permissions** pane shows the **APIs my organization uses** tab instead of the **Microsoft APIs** tab. Select the **APIs my organization uses** to then select **Azure Rights Management Services**.</span></span> 
        >

    1. <span data-ttu-id="fe4dc-210">Windows サーバー コンピューターから、スキャナー サービス アカウントにインストールに対するローカルログオン権限が付与されている場合は、このアカウントでサインインし、PowerShell セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-210">From the Windows Server computer, if your scanner service account has been granted the **Log on locally** right for the installation, sign in with this account and start a PowerShell session.</span></span> 
    
        <span data-ttu-id="fe4dc-211">スキャナー サービス アカウントにインストールに対してローカルにログオンする権限を付与できない場合は [、「Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)用に対話的にファイルにラベルを付ける方法」の説明に従って [、Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication)を使用して *OnBehalfOf* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-211">If your scanner service account cannot be granted the **Log on locally** right for the installation, use the *OnBehalfOf* parameter with [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), as described in [How to label files non-interactively for Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).</span></span>

    1. <span data-ttu-id="fe4dc-212">[Set-AIPAuthentication を実行](/powershell/module/azureinformationprotection/set-aipauthentication)し、Azure アプリケーションからコピーされた値ADします。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-212">Run [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), specifying values copied from your Azure AD application:</span></span>

      ```PowerShell
      Set-AIPAuthentication -AppId <ID of the registered app> -AppSecret <client secret sting> -TenantId <your tenant ID> -DelegatedUser <Azure AD account>
      ```

      <span data-ttu-id="fe4dc-213">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-213">For example:</span></span>

      ```PowerShell
      $pscreds = Get-Credential CONTOSO\scanner
      Set-AIPAuthentication -AppId "77c3c1c3-abf9-404e-8b2b-4652836c8c66" -AppSecret "OAkk+rnuYc/u+]ah2kNxVbtrDGbS47L4" -DelegatedUser scanner@contoso.com -TenantId "9c11c87a-ac8b-46a3-8d5c-f4d0b72ee29a" -OnBehalfOf $pscreds
      Acquired application access token on behalf of CONTOSO\scanner.
      ```

    <span data-ttu-id="fe4dc-214">これで、スキャナーに Azure サーバーに対する認証トークンがAD。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-214">The scanner now has a token to authenticate to Azure AD.</span></span> <span data-ttu-id="fe4dc-215">このトークンは、Azure アプリの Web アプリ **/API** クライアント シークレットの構成に従って、1 年、2 年、または 2 年間有効AD。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-215">This token is valid for one year, two years, or never, according to your configuration of the **Web app /API** client secret in Azure AD.</span></span> <span data-ttu-id="fe4dc-216">トークンの有効期限が切れたら、この手順を繰り返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-216">When the token expires, you must repeat this procedure.</span></span>

1. <span data-ttu-id="fe4dc-217">[Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration)コマンドレットを実行して、スキャナーをオフライン モードで機能に設定します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-217">Run the [Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) cmdlet to set the scanner to function in offline mode.</span></span> <span data-ttu-id="fe4dc-218">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-218">Run:</span></span>

    ```powershell
    Set-AIPScannerConfiguration -OnlineConfiguration Off
    ```

1. <span data-ttu-id="fe4dc-219">[Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob)コマンドレットを実行して、既定のコンテンツ スキャン ジョブを作成します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-219">Run the [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) cmdlet to create a default content scan job.</span></span>

    <span data-ttu-id="fe4dc-220">**Set-AIPScannerContentScanJob** コマンドレットで必要なパラメーターは、強制 **のみです**。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-220">The only required parameter in the **Set-AIPScannerContentScanJob** cmdlet is **Enforce**.</span></span> <span data-ttu-id="fe4dc-221">ただし、この時点でコンテンツ スキャン ジョブの他の設定を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-221">However, you may want to define other settings for your content scan job at this time.</span></span> <span data-ttu-id="fe4dc-222">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-222">For example:</span></span>

    ```powershell
    Set-AIPScannerContentScanJob -Schedule Manual -DiscoverInformationTypes PolicyOnly -Enforce Off -DefaultLabelType PolicyDefault -RelabelFiles Off -PreserveFileDetails On -IncludeFileTypes '' -ExcludeFileTypes '.msg,.tmp' -DefaultOwner <account running the scanner>
    ```

    <span data-ttu-id="fe4dc-223">上記の構文は、構成を続行する間に次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-223">The syntax above configures the following settings while you continue the configuration:</span></span>

    - <span data-ttu-id="fe4dc-224">スキャナーの実行スケジュールを手動に *保持する*</span><span class="sxs-lookup"><span data-stu-id="fe4dc-224">Keeps the scanner run scheduling to *manual*</span></span>
    - <span data-ttu-id="fe4dc-225">感度ラベル付けポリシーに基づいて検出される情報の種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-225">Sets the information types to be discovered based on the sensitivity labeling policy</span></span>
    - <span data-ttu-id="fe4dc-226">感度 *ラベル* 付けポリシーを適用しない</span><span class="sxs-lookup"><span data-stu-id="fe4dc-226">Does *not* enforce a sensitivity labeling policy</span></span>
    - <span data-ttu-id="fe4dc-227">感度ラベル付けポリシーに定義されている既定のラベルを使用して、コンテンツに基づいてファイルに自動的にラベルを付ける</span><span class="sxs-lookup"><span data-stu-id="fe4dc-227">Automatically labels files based on content, using the default label defined for the sensitivity labeling policy</span></span>
    - <span data-ttu-id="fe4dc-228">ファイル *の* 再ラベル付けは許可しない</span><span class="sxs-lookup"><span data-stu-id="fe4dc-228">Does *not* allow for relabeling files</span></span>
    - <span data-ttu-id="fe4dc-229">値によって変更された日付、最後に変更された日付、および変更を含む、スキャンと自動ラベル付け中にファイル *の詳細を保持* します</span><span class="sxs-lookup"><span data-stu-id="fe4dc-229">Preserves file details while scanning and auto-labeling, including *date modified*, *last modified*, and *modified by* values</span></span>
    - <span data-ttu-id="fe4dc-230">実行中に .msg ファイルと .tmp ファイルを除外するスキャナーを設定します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-230">Sets the scanner to exclude .msg and .tmp files when running</span></span>
    - <span data-ttu-id="fe4dc-231">スキャナーの実行時に使用するアカウントに既定の所有者を設定します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-231">Sets the default owner to the account you want to use when running the scanner</span></span>

1. <span data-ttu-id="fe4dc-232">[Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository)コマンドレットを使用して、コンテンツ スキャン ジョブでスキャンするリポジトリを定義します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-232">Use the [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) cmdlet to define the repositories you want to scan in your content scan job.</span></span> <span data-ttu-id="fe4dc-233">たとえば、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-233">For example, run:</span></span>

    ```powershell
    Add-AIPScannerRepository -OverrideContentScanJob Off -Path 'c:\repoToScan'
    ```
    
    <span data-ttu-id="fe4dc-234">追加するリポジトリの種類に応じて、次のいずれかの構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-234">Use one of the following syntaxes, depending on the type of repository you're adding:</span></span>

    - <span data-ttu-id="fe4dc-235">ネットワーク共有の場合は、 を使用します `\\Server\Folder` 。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-235">For a network share, use `\\Server\Folder`.</span></span>
    - <span data-ttu-id="fe4dc-236">ライブラリの場合SharePointを使用します `http://sharepoint.contoso.com/Shared%20Documents/Folder` 。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-236">For a SharePoint library, use `http://sharepoint.contoso.com/Shared%20Documents/Folder`.</span></span>
    - <span data-ttu-id="fe4dc-237">ローカル パスの場合: `C:\Folder`</span><span class="sxs-lookup"><span data-stu-id="fe4dc-237">For a local path: `C:\Folder`</span></span>
    - <span data-ttu-id="fe4dc-238">UNC パスの場合: `\\Server\Folder`</span><span class="sxs-lookup"><span data-stu-id="fe4dc-238">For a UNC path: `\\Server\Folder`</span></span>

    > [!NOTE]
    > <span data-ttu-id="fe4dc-239">ワイルドカードはサポートされていません。WebDav の場所はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-239">Wildcards are not supported and WebDav locations are not supported.</span></span>
    >
    > <span data-ttu-id="fe4dc-240">後でリポジトリを変更するには、代わりに [Set-AIPScannerRepository コマンドレット](/powershell/module/azureinformationprotection/set-aipscannerrepository) を使用します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-240">To modify the repository later on, use the [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) cmdlet instead.</span></span> 


<span data-ttu-id="fe4dc-241">必要に応じて、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-241">Continue with the following steps as needed:</span></span>

- [<span data-ttu-id="fe4dc-242">検出サイクルを実行して、スキャナーのレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="fe4dc-242">Run a discovery cycle and view reports for the scanner</span></span>](/azure/information-protection/deploy-aip-scanner-manage#run-a-discovery-cycle-and-view-reports-for-the-scanner)
- [<span data-ttu-id="fe4dc-243">PowerShell を使用して分類と保護を適用するスキャナーを構成する</span><span class="sxs-lookup"><span data-stu-id="fe4dc-243">Use PowerShell to configure the scanner to apply classification and protection</span></span>](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-the-scanner-to-apply-classification-and-protection)
- [<span data-ttu-id="fe4dc-244">PowerShell を使用してスキャナーで DLP ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="fe4dc-244">Use PowerShell to configure a DLP policy with the scanner</span></span>](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-a-dlp-policy-with-the-scanner)

<span data-ttu-id="fe4dc-245">次の表に、スキャナーのインストールとコンテンツ スキャン ジョブの管理に関連する PowerShell コマンドレットの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-245">The following table lists PowerShell cmdlets that are relevant for installing the scanner and managing your content scan jobs:</span></span>

| <span data-ttu-id="fe4dc-246">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="fe4dc-246">Cmdlet</span></span> | <span data-ttu-id="fe4dc-247">説明</span><span class="sxs-lookup"><span data-stu-id="fe4dc-247">Description</span></span> |
|--|--|
| [<span data-ttu-id="fe4dc-248">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="fe4dc-248">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="fe4dc-249">コンテンツ スキャン ジョブに新しいリポジトリを追加します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-249">Adds a new repository to your content scan job.</span></span> |
| [<span data-ttu-id="fe4dc-250">Get-AIPScannerConfiguration</span><span class="sxs-lookup"><span data-stu-id="fe4dc-250">Get-AIPScannerConfiguration</span></span>](/powershell/module/azureinformationprotection/get-aipscannerconfiguration)|<span data-ttu-id="fe4dc-251">クラスターに関する詳細を返します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-251">Returns details about your cluster.</span></span> |
| [<span data-ttu-id="fe4dc-252">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="fe4dc-252">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="fe4dc-253">コンテンツ スキャン ジョブの詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-253">Gets details about your content scan job.</span></span> |
| [<span data-ttu-id="fe4dc-254">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="fe4dc-254">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="fe4dc-255">コンテンツ スキャン ジョブに定義されているリポジトリの詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-255">Gets details about repositories defined for your content scan job.</span></span> |
| [<span data-ttu-id="fe4dc-256">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="fe4dc-256">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="fe4dc-257">コンテンツ スキャン ジョブを削除します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-257">Deletes your content scan job.</span></span> |
| [<span data-ttu-id="fe4dc-258">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="fe4dc-258">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="fe4dc-259">コンテンツ スキャン ジョブからリポジトリを削除します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-259">Removes a repository from your content scan job.</span></span> |
| [<span data-ttu-id="fe4dc-260">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="fe4dc-260">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="fe4dc-261">コンテンツ スキャン ジョブの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-261">Defines settings for your content scan job.</span></span> |
| [<span data-ttu-id="fe4dc-262">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="fe4dc-262">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="fe4dc-263">コンテンツ スキャン ジョブの既存のリポジトリの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-263">Defines settings for an existing repository in your content scan job.</span></span> |
| | |

<span data-ttu-id="fe4dc-264">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-264">For more information, see:</span></span>

- [<span data-ttu-id="fe4dc-265">Azure Information Protection 統合ラベル スキャナーとは</span><span class="sxs-lookup"><span data-stu-id="fe4dc-265">What is the Azure Information Protection unified labeling scanner?</span></span>](/azure/information-protection/deploy-aip-scanner)
- [<span data-ttu-id="fe4dc-266">Azure Information Protection (AIP) 統合ラベル スキャナーの構成とインストール</span><span class="sxs-lookup"><span data-stu-id="fe4dc-266">Configuring and installing the Azure Information Protection (AIP) unified labeling scanner</span></span>](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=powershell-only)
- <span data-ttu-id="fe4dc-267">[PowerShell のみを使用してコンテンツ スキャン ジョブを管理します](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)。</span><span class="sxs-lookup"><span data-stu-id="fe4dc-267">[Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>
