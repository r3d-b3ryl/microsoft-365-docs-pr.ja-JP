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
ms.openlocfilehash: bddba69ecc8b7b80d2b2c7c48d820ec22d293362
ms.sourcegitcommit: b56a8ff9bb496bf2bc1991000afca3d251f45b72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2021
ms.locfileid: "51418034"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a><span data-ttu-id="cfa60-103">21Vianet がOffice 365 Azure Information Protection のサポート</span><span class="sxs-lookup"><span data-stu-id="cfa60-103">Azure Information Protection support for Office 365 operated by 21Vianet</span></span>

<span data-ttu-id="cfa60-104">この記事では、21Vianet と商用製品が運用する Office 365 の Azure Information Protection (AIP) サポートの違い、および AIP オンプレミス スキャナーのインストール方法やコンテンツ スキャン ジョブの管理方法など、中国のお客様向け AIP を構成するための具体的な手順について説明します。 &mdash;</span><span class="sxs-lookup"><span data-stu-id="cfa60-104">This article covers the differences between Azure Information Protection (AIP) support for Office 365 operated by 21Vianet and commercial offerings, as well as specific instructions for configuring AIP for customers in China&mdash;including how to install the AIP on-premises scanner and manage content scan jobs.</span></span>

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="cfa60-105">21Vianet がOffice 365する AIP と商用サービスの違い</span><span class="sxs-lookup"><span data-stu-id="cfa60-105">Differences between AIP for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="cfa60-106">21Vianet オファーが運用する Office 365 の AIP を使用して、中国のすべての商用機能と機能を中国のお客様に提供しますが、強調表示する機能が不足しています。</span><span class="sxs-lookup"><span data-stu-id="cfa60-106">While our goal is to deliver all commercial features and functionality to customers in China with our AIP for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="cfa60-107">次の一覧には、21Vianet が運用する 2021 Office 365の AIP と 2021 年 1 月の商用製品との間の既存のギャップが含まれます。</span><span class="sxs-lookup"><span data-stu-id="cfa60-107">The following list includes the existing gaps between AIP for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="cfa60-108">Information Rights Management (IRM) は、Microsoft 365 Apps for enterprise (ビルド 11731.10000 以上) でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="cfa60-108">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="cfa60-109">Office 2010、Office 2013、その他Office 2016 バージョンはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="cfa60-109">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="cfa60-110">現在、Active Directory Rights Management サービス (AD RMS) から AIP への移行は使用できません。</span><span class="sxs-lookup"><span data-stu-id="cfa60-110">Migration from Active Directory Rights Management Services (AD RMS) to AIP is currently not available.</span></span>
  
- <span data-ttu-id="cfa60-111">商用クラウド内のユーザーとの保護されたメールの共有がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="cfa60-111">Sharing of protected emails with users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="cfa60-112">現在、商用クラウド内のユーザーとのドキュメントと電子メールの添付ファイルの共有は利用できません。</span><span class="sxs-lookup"><span data-stu-id="cfa60-112">Sharing of documents and email attachments with users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="cfa60-113">これには、Office 365クラウド内の 21Vianet ユーザーが運用するユーザー、商用クラウド内の 21Vianet ユーザーが運用する Office 365 以外のユーザー、および RMS for Individuals ライセンスを持つユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="cfa60-113">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="cfa60-114">IRM と SharePoint (IRM で保護されたサイトとライブラリ) は現在使用できません。</span><span class="sxs-lookup"><span data-stu-id="cfa60-114">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="cfa60-115">現在、RMS のモバイル AD拡張機能は使用できません。</span><span class="sxs-lookup"><span data-stu-id="cfa60-115">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="cfa60-116">モバイル [ビューアーは](/azure/information-protection/rms-client/mobile-app-faq) Azure China 21Vianet ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="cfa60-116">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

- <span data-ttu-id="cfa60-117">Azure ポータルの AIP 領域は、中国のお客様が利用できません。</span><span class="sxs-lookup"><span data-stu-id="cfa60-117">The AIP area of the Azure portal is unavailable to customers in China.</span></span> <span data-ttu-id="cfa60-118">[オンプレミス スキャナーの](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)インストールやコンテンツ スキャン ジョブの管理など、ポータルでアクションを実行する代わりに PowerShell コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="cfa60-118">Use [PowerShell commands](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) instead of performing actions in the portal, such as installing the on-premises scanner and managing your content scan jobs.</span></span>

## <a name="configure-aip-for-customers-in-china"></a><span data-ttu-id="cfa60-119">中国の顧客向け AIP の構成</span><span class="sxs-lookup"><span data-stu-id="cfa60-119">Configure AIP for customers in China</span></span>

<span data-ttu-id="cfa60-120">中国の顧客向け AIP を構成するには、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="cfa60-120">To configure AIP for customers in China:</span></span>
1. <span data-ttu-id="cfa60-121">[テナントの権限管理を有効にします](#step-1-enable-rights-management-for-the-tenant)。</span><span class="sxs-lookup"><span data-stu-id="cfa60-121">[Enable Rights Management for the tenant](#step-1-enable-rights-management-for-the-tenant).</span></span>

2. <span data-ttu-id="cfa60-122">[DNS 暗号化を構成します](#step-2-configure-dns-encryption)。</span><span class="sxs-lookup"><span data-stu-id="cfa60-122">[Configure DNS encryption](#step-2-configure-dns-encryption).</span></span>

3. <span data-ttu-id="cfa60-123">[AIP 統合ラベル 付けクライアントをインストールして構成します](#step-3-install-and-configure-the-aip-unified-labeling-client)。</span><span class="sxs-lookup"><span data-stu-id="cfa60-123">[Install and configure the AIP unified labeling client](#step-3-install-and-configure-the-aip-unified-labeling-client).</span></span>

4. <span data-ttu-id="cfa60-124">[アプリで AIP アプリを構成Windows。](#step-4-configure-aip-apps-on-windows)</span><span class="sxs-lookup"><span data-stu-id="cfa60-124">[Configure AIP apps on Windows](#step-4-configure-aip-apps-on-windows).</span></span>

5. <span data-ttu-id="cfa60-125">[AIP オンプレミス スキャナーをインストールし、コンテンツ スキャン ジョブを管理します](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)。</span><span class="sxs-lookup"><span data-stu-id="cfa60-125">[Install the AIP on-premises scanner and manage content scan jobs](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs).</span></span> 

### <a name="step-1-enable-rights-management-for-the-tenant"></a><span data-ttu-id="cfa60-126">手順 1: テナントの権限管理を有効にする</span><span class="sxs-lookup"><span data-stu-id="cfa60-126">Step 1: Enable Rights Management for the tenant</span></span>

<span data-ttu-id="cfa60-127">暗号化が正しく機能するには、テナントで RMS を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfa60-127">For the encryption to work correctly, RMS must be enabled for the tenant.</span></span>

1. <span data-ttu-id="cfa60-128">RMS が有効になっているか確認します。</span><span class="sxs-lookup"><span data-stu-id="cfa60-128">Check if RMS is enabled:</span></span>

    1. <span data-ttu-id="cfa60-129">管理者として PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="cfa60-129">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="cfa60-130">AIPService モジュールがインストールされていない場合は、実行します `Install-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="cfa60-130">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="cfa60-131">を使用してモジュールをインポート `Import-Module AipService` します。</span><span class="sxs-lookup"><span data-stu-id="cfa60-131">Import the module using `Import-Module AipService`.</span></span>
    4. <span data-ttu-id="cfa60-132">Connectを使用してサービスにアクセスします `Connect-AipService -environmentname azurechinacloud` 。</span><span class="sxs-lookup"><span data-stu-id="cfa60-132">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    5. <span data-ttu-id="cfa60-133">状態 `(Get-AipServiceConfiguration).FunctionalState` が . `Enabled`</span><span class="sxs-lookup"><span data-stu-id="cfa60-133">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

2. <span data-ttu-id="cfa60-134">機能状態がである場合は `Disabled` 、実行します `Enable-AipService` 。</span><span class="sxs-lookup"><span data-stu-id="cfa60-134">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="step-2-configure-dns-encryption"></a><span data-ttu-id="cfa60-135">手順 2: DNS 暗号化を構成する</span><span class="sxs-lookup"><span data-stu-id="cfa60-135">Step 2: Configure DNS encryption</span></span>

<span data-ttu-id="cfa60-136">暗号化が正しく動作するにはOfficeクライアント アプリケーションは、サービスの中国インスタンスに接続し、そこからブートストラップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfa60-136">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="cfa60-137">クライアント アプリケーションを適切なサービス インスタンスにリダイレクトするには、テナント管理者が Azure RMS URL に関する情報を含む DNS SRV レコードを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfa60-137">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="cfa60-138">DNS SRV レコードがない場合、クライアント アプリケーションは既定でパブリック クラウド インスタンスへの接続を試み、失敗します。</span><span class="sxs-lookup"><span data-stu-id="cfa60-138">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="cfa60-139">また、テナントが所有するドメイン (たとえば) に基づいてユーザー名を使用してログインし、ユーザー名 (たとえば) でログインしないという前提 `joe@contoso.cn` `onmschina` があります `joe@contoso.onmschina.cn` 。</span><span class="sxs-lookup"><span data-stu-id="cfa60-139">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="cfa60-140">ユーザー名のドメイン名は、正しいサービス インスタンスへの DNS リダイレクトに使用されます。</span><span class="sxs-lookup"><span data-stu-id="cfa60-140">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

#### <a name="configure-dns-encryption---windows"></a><span data-ttu-id="cfa60-141">DNS 暗号化の構成 - Windows</span><span class="sxs-lookup"><span data-stu-id="cfa60-141">Configure DNS encryption - Windows</span></span>

1. <span data-ttu-id="cfa60-142">RMS ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="cfa60-142">Get the RMS ID:</span></span>

    1. <span data-ttu-id="cfa60-143">管理者として PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="cfa60-143">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="cfa60-144">AIPService モジュールがインストールされていない場合は、実行します `Install-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="cfa60-144">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="cfa60-145">Connectを使用してサービスにアクセスします `Connect-AipService -environmentname azurechinacloud` 。</span><span class="sxs-lookup"><span data-stu-id="cfa60-145">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    4. <span data-ttu-id="cfa60-146">RMS `(Get-AipServiceConfiguration).RightsManagementServiceId` ID を取得するために実行します。</span><span class="sxs-lookup"><span data-stu-id="cfa60-146">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

2. <span data-ttu-id="cfa60-147">DNS プロバイダーにログインし、ドメインの DNS 設定に移動し、新しい SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="cfa60-147">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

    - <span data-ttu-id="cfa60-148">サービス = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="cfa60-148">Service = `_rmsredir`</span></span>
    - <span data-ttu-id="cfa60-149">プロトコル = `_http`</span><span class="sxs-lookup"><span data-stu-id="cfa60-149">Protocol = `_http`</span></span>
    - <span data-ttu-id="cfa60-150">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="cfa60-150">Name = `_tcp`</span></span>
    - <span data-ttu-id="cfa60-151">Target = `[GUID].rms.aadrm.cn` (GUID は RMS ID)</span><span class="sxs-lookup"><span data-stu-id="cfa60-151">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
    - <span data-ttu-id="cfa60-152">優先度、重み、秒、TTL = 既定値</span><span class="sxs-lookup"><span data-stu-id="cfa60-152">Priority, Weight, Seconds, TTL = default values</span></span>

3. <span data-ttu-id="cfa60-153">Azure portal のテナントにカスタム ドメインを関連 [付ける](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)。</span><span class="sxs-lookup"><span data-stu-id="cfa60-153">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="cfa60-154">これにより、DNS のエントリが追加され、DNS 設定に値を追加した後に検証に数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="cfa60-154">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

4. <span data-ttu-id="cfa60-155">対応するグローバル管理者資格情報Microsoft 365管理センターにログインし、ユーザー作成用のドメイン (たとえば `contoso.cn` ) を追加します。</span><span class="sxs-lookup"><span data-stu-id="cfa60-155">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="cfa60-156">検証プロセスでは、追加の DNS 変更が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="cfa60-156">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="cfa60-157">検証が完了すると、ユーザーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="cfa60-157">Once verification is done, users can be created.</span></span>

#### <a name="configure-dns-encryption---mac-ios-android"></a><span data-ttu-id="cfa60-158">DNS 暗号化の構成 - Mac、iOS、Android</span><span class="sxs-lookup"><span data-stu-id="cfa60-158">Configure DNS encryption - Mac, iOS, Android</span></span>

<span data-ttu-id="cfa60-159">DNS プロバイダーにログインし、ドメインの DNS 設定に移動し、新しい SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="cfa60-159">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="cfa60-160">サービス = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="cfa60-160">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="cfa60-161">プロトコル = `_http`</span><span class="sxs-lookup"><span data-stu-id="cfa60-161">Protocol = `_http`</span></span>
- <span data-ttu-id="cfa60-162">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="cfa60-162">Name = `_tcp`</span></span>
- <span data-ttu-id="cfa60-163">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="cfa60-163">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="cfa60-164">Port = `80`</span><span class="sxs-lookup"><span data-stu-id="cfa60-164">Port = `80`</span></span>
- <span data-ttu-id="cfa60-165">優先度、重み、秒、TTL = 既定値</span><span class="sxs-lookup"><span data-stu-id="cfa60-165">Priority, Weight, Seconds, TTL = default values</span></span>

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a><span data-ttu-id="cfa60-166">手順 3: AIP 統合ラベル 付けクライアントをインストールして構成する</span><span class="sxs-lookup"><span data-stu-id="cfa60-166">Step 3: Install and configure the AIP unified labeling client</span></span>

<span data-ttu-id="cfa60-167">AIP 統合ラベル 付けクライアントを Microsoft ダウンロード センター [からダウンロードします](https://www.microsoft.com/download/details.aspx?id=53018)。</span><span class="sxs-lookup"><span data-stu-id="cfa60-167">Download the AIP unified labeling client from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="cfa60-168">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfa60-168">For more information, see:</span></span>

- [<span data-ttu-id="cfa60-169">AIP ドキュメント</span><span class="sxs-lookup"><span data-stu-id="cfa60-169">AIP documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="cfa60-170">AIP バージョンの履歴とサポート ポリシー</span><span class="sxs-lookup"><span data-stu-id="cfa60-170">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="cfa60-171">AIP システム要件</span><span class="sxs-lookup"><span data-stu-id="cfa60-171">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="cfa60-172">AIP クイック スタート: AIP クライアントを展開する</span><span class="sxs-lookup"><span data-stu-id="cfa60-172">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="cfa60-173">AIP 管理者ガイド</span><span class="sxs-lookup"><span data-stu-id="cfa60-173">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="cfa60-174">AIP ユーザー ガイド</span><span class="sxs-lookup"><span data-stu-id="cfa60-174">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="cfa60-175">感度ラベルMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="cfa60-175">Learn about Microsoft 365 sensitivity labels</span></span>](../../compliance/sensitivity-labels.md)

### <a name="step-4-configure-aip-apps-on-windows"></a><span data-ttu-id="cfa60-176">手順 4: アプリで AIP アプリを構成Windows</span><span class="sxs-lookup"><span data-stu-id="cfa60-176">Step 4: Configure AIP apps on Windows</span></span>

<span data-ttu-id="cfa60-177">Azure China のWindowsソブリン クラウドをポイントするには、次のレジストリ キーが必要です。</span><span class="sxs-lookup"><span data-stu-id="cfa60-177">AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="cfa60-178">レジストリ ノード = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="cfa60-178">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="cfa60-179">Name = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="cfa60-179">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="cfa60-180">値 = `6` (既定値 = 0)</span><span class="sxs-lookup"><span data-stu-id="cfa60-180">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="cfa60-181">Type = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="cfa60-181">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cfa60-182">アンインストール後にレジストリ キーを削除しない必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfa60-182">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="cfa60-183">キーが空、正しくない、または存在しない場合、機能は既定値 (商用クラウドの既定値 = 0) として動作します。</span><span class="sxs-lookup"><span data-stu-id="cfa60-183">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="cfa60-184">キーが空または正しくない場合は、印刷エラーもログに追加されます。</span><span class="sxs-lookup"><span data-stu-id="cfa60-184">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a><span data-ttu-id="cfa60-185">手順 5: AIP オンプレミス スキャナーをインストールし、コンテンツ スキャン ジョブを管理する</span><span class="sxs-lookup"><span data-stu-id="cfa60-185">Step 5: Install the AIP on-premises scanner and manage content scan jobs</span></span>

<span data-ttu-id="cfa60-186">AIP オンプレミス スキャナーをインストールして、ネットワークとコンテンツ共有の機密データをスキャンし、組織のポリシーで構成されている分類ラベルと保護ラベルを適用します。</span><span class="sxs-lookup"><span data-stu-id="cfa60-186">Install the AIP on-premises scanner to scan your network and content shares for sensitive data, and apply classification and protection labels as configured in your organization's policy.</span></span>

- <span data-ttu-id="cfa60-187">[Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication)コマンド用に Azure AD アプリケーションを作成および構成する場合、[API のアクセス許可の要求] ウィンドウには **、[Microsoft** **API]** タブではなく [組織で使用する API] タブが表示されます。組織が **使用する API を選択し、[Azure** **Rights Management Services] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cfa60-187">When creating and configuring Azure AD applications for the [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) command, the **Request API permissions** pane shows the **APIs my organization uses** tab instead of the **Microsoft APIs** tab. Select the **APIs my organization uses** to then select **Azure Rights Management Services**.</span></span>

- <span data-ttu-id="cfa60-188">スキャナーをインストールしてコンテンツ スキャン ジョブを管理する場合は、商用製品で使用される Azure ポータル インターフェイスではなく、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="cfa60-188">When installing the scanner and managing your content scan jobs, use the following cmdlets instead of the Azure portal interface that's used by the commercial offerings:</span></span><br><br>

    | <span data-ttu-id="cfa60-189">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="cfa60-189">Cmdlet</span></span> | <span data-ttu-id="cfa60-190">説明</span><span class="sxs-lookup"><span data-stu-id="cfa60-190">Description</span></span> |
    |--|--|
    | [<span data-ttu-id="cfa60-191">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="cfa60-191">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="cfa60-192">コンテンツ スキャン ジョブに新しいリポジトリを追加します。</span><span class="sxs-lookup"><span data-stu-id="cfa60-192">Adds a new repository to your content scan job.</span></span> |
    | [<span data-ttu-id="cfa60-193">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="cfa60-193">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="cfa60-194">コンテンツ スキャン ジョブの詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="cfa60-194">Gets details about your content scan job.</span></span> |
    | [<span data-ttu-id="cfa60-195">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="cfa60-195">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="cfa60-196">コンテンツ スキャン ジョブに定義されているリポジトリの詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="cfa60-196">Gets details about repositories defined for your content scan job.</span></span> |
    | [<span data-ttu-id="cfa60-197">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="cfa60-197">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="cfa60-198">コンテンツ スキャン ジョブを削除します。</span><span class="sxs-lookup"><span data-stu-id="cfa60-198">Deletes your content scan job.</span></span> |
    | [<span data-ttu-id="cfa60-199">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="cfa60-199">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="cfa60-200">コンテンツ スキャン ジョブからリポジトリを削除します。</span><span class="sxs-lookup"><span data-stu-id="cfa60-200">Removes a repository from your content scan job.</span></span> |
    | [<span data-ttu-id="cfa60-201">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="cfa60-201">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="cfa60-202">コンテンツ スキャン ジョブの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="cfa60-202">Defines settings for your content scan job.</span></span> |
    | [<span data-ttu-id="cfa60-203">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="cfa60-203">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="cfa60-204">コンテンツ スキャン ジョブの既存のリポジトリの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="cfa60-204">Defines settings for an existing repository in your content scan job.</span></span> |
    | | |

> [!TIP]
> <span data-ttu-id="cfa60-205">スキャナー[をインストールする場合は](/azure/information-protection/deploy-aip-scanner-configure-install#install-the-scanner)[、Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner)コマンドで同じクラスター名を使用して、複数のスキャナー ノードを同じクラスターに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfa60-205">When [installing the scanner](/azure/information-protection/deploy-aip-scanner-configure-install#install-the-scanner), use the same cluster name in the [Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) command to associate multiple scanner nodes to the same cluster.</span></span> <span data-ttu-id="cfa60-206">複数のスキャナー ノードに同じクラスターを使用すると、複数のスキャナーを組み合わせてスキャンを実行できます。</span><span class="sxs-lookup"><span data-stu-id="cfa60-206">Using the same cluster for multiple scanner nodes enables multiple scanners to work together to perform your scans.</span></span>
> 
> <span data-ttu-id="cfa60-207">[Get-AIPScannerConfiguration](/powershell/module/azureinformationprotection/get-aipscannerconfiguration)コマンドレットを使用して、クラスターに関する詳細を返します。</span><span class="sxs-lookup"><span data-stu-id="cfa60-207">Use the [Get-AIPScannerConfiguration](/powershell/module/azureinformationprotection/get-aipscannerconfiguration) cmdlet to return details about your cluster.</span></span>
> 
<span data-ttu-id="cfa60-208">詳細については、「Azure Information Protection 統合ラベル スキャナーとは」および [「PowerShell](/azure/information-protection/deploy-aip-scanner) のみを使用してコンテンツ スキャン ジョブを管理する」 [を参照してください](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)。</span><span class="sxs-lookup"><span data-stu-id="cfa60-208">For more information, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) and [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>