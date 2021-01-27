---
title: 21Vianet が運用Office 365 に対する Azure Information Protection のサポート
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
description: 21Vianet が運用している Office 365 の Azure Information Protection (AIP) と、中国のお客様向け構成方法について説明します。
monikerRange: o365-21vianet
ms.openlocfilehash: cee50384587ffc3e1e43eb9c6bb07d2e0ced7e13
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988046"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a><span data-ttu-id="ddfbd-103">21Vianet が運用Office 365 に対する Azure Information Protection のサポート</span><span class="sxs-lookup"><span data-stu-id="ddfbd-103">Azure Information Protection support for Office 365 operated by 21Vianet</span></span>

<span data-ttu-id="ddfbd-104">この記事では、21Vianet が運用している Office 365 の Azure Information Protection (AIP) サポートと商用製品の違い、および AIP オンプレミス スキャナーのインストール方法やコンテンツ スキャン ジョブの管理方法など、中国のお客様向け AIP を構成する具体的な手順について説明します。 &mdash;</span><span class="sxs-lookup"><span data-stu-id="ddfbd-104">This article covers the differences between Azure Information Protection (AIP) support for Office 365 operated by 21Vianet and commercial offerings, as well as specific instructions for configuring AIP for customers in China&mdash;including how to install the AIP on-premises scanner and manage content scan jobs.</span></span>

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="ddfbd-105">21Vianet が運用Office 365 の AIP と商用製品の相違点</span><span class="sxs-lookup"><span data-stu-id="ddfbd-105">Differences between AIP for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="ddfbd-106">この目標は、21Vianet が運用している Office 365 用の AIP を使用して、中国のお客様にすべての商用機能を提供することで実現しますが、強調表示する機能が不足しています。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-106">While our goal is to deliver all commercial features and functionality to customers in China with our AIP for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="ddfbd-107">次の一覧には、21Vianet が運用している Office 365 用の AIP と 2021 年 1 月の商用サービスの既存のギャップが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-107">The following list includes the existing gaps between AIP for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="ddfbd-108">Information Rights Management (IRM) は、Microsoft 365 Apps for enterprise (ビルド 11731.10000 以上) でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-108">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="ddfbd-109">Office 2010、Office 2013、その他の Office 2016 バージョンはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-109">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="ddfbd-110">現在、Active Directory Rights Management サービス (AD RMS) から AIP への移行は使用できません。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-110">Migration from Active Directory Rights Management Services (AD RMS) to AIP is currently not available.</span></span>
  
- <span data-ttu-id="ddfbd-111">商用クラウドのユーザーとの保護されたメールの共有がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-111">Sharing of protected emails with users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="ddfbd-112">現在、商用クラウドのユーザーとのドキュメントとメールの添付ファイルの共有は利用できません。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-112">Sharing of documents and email attachments with users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="ddfbd-113">これには、商用クラウドで 21Vianet ユーザーが運用している Office 365、商用クラウドの 21Vianet ユーザーが運用している Office 365 以外のユーザー、および個人向け RMS ライセンスを持つユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-113">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="ddfbd-114">現在、SharePoint での IRM (IRM で保護されたサイトとライブラリ) は使用できません。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-114">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="ddfbd-115">現在、RMS 用モバイル AD拡張機能は使用できません。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-115">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="ddfbd-116">モバイル [ビューアーは](/azure/information-protection/rms-client/mobile-app-faq) 、Azure China 21Vianet ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-116">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

## <a name="configure-aip-for-customers-in-china"></a><span data-ttu-id="ddfbd-117">中国のお客様向け AIP の構成</span><span class="sxs-lookup"><span data-stu-id="ddfbd-117">Configure AIP for customers in China</span></span>

<span data-ttu-id="ddfbd-118">中国のお客様向け AIP を構成するには:</span><span class="sxs-lookup"><span data-stu-id="ddfbd-118">To configure AIP for customers in China:</span></span>
1. <span data-ttu-id="ddfbd-119">[テナントの Rights Management を有効にします](#step-1-enable-rights-management-for-the-tenant)。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-119">[Enable Rights Management for the tenant](#step-1-enable-rights-management-for-the-tenant).</span></span>

2. <span data-ttu-id="ddfbd-120">[DNS 暗号化を構成します](#step-2-configure-dns-encryption)。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-120">[Configure DNS encryption](#step-2-configure-dns-encryption).</span></span>

3. <span data-ttu-id="ddfbd-121">[AIP 統合ラベル付けクライアントをインストールして構成します](#step-3-install-and-configure-the-aip-unified-labeling-client)。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-121">[Install and configure the AIP unified labeling client](#step-3-install-and-configure-the-aip-unified-labeling-client).</span></span>

4. <span data-ttu-id="ddfbd-122">[Windows で AIP アプリを構成します](#step-4-configure-aip-apps-on-windows)。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-122">[Configure AIP apps on Windows](#step-4-configure-aip-apps-on-windows).</span></span>

5. <span data-ttu-id="ddfbd-123">[AIP オンプレミス スキャナーをインストールし、コンテンツ スキャン ジョブを管理します](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-123">[Install the AIP on-premises scanner and manage content scan jobs](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs).</span></span> 

### <a name="step-1-enable-rights-management-for-the-tenant"></a><span data-ttu-id="ddfbd-124">手順 1: テナントの Rights Management を有効にする</span><span class="sxs-lookup"><span data-stu-id="ddfbd-124">Step 1: Enable Rights Management for the tenant</span></span>

<span data-ttu-id="ddfbd-125">暗号化が正しく機能するには、テナントに対して RMS を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-125">For the encryption to work correctly, RMS must be enabled for the tenant.</span></span>

1. <span data-ttu-id="ddfbd-126">RMS が有効になっているか確認します。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-126">Check if RMS is enabled:</span></span>

    1. <span data-ttu-id="ddfbd-127">管理者として PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-127">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="ddfbd-128">AIPService モジュールがインストールされていない場合は、実行します `Install-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-128">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="ddfbd-129">を使用してモジュールをインポートします `Import-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-129">Import the module using `Import-Module AipService`.</span></span>
    4. <span data-ttu-id="ddfbd-130">を使用してサービスに接続します `Connect-AipService -environmentname azurechinacloud` 。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-130">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    5. <span data-ttu-id="ddfbd-131">状態 `(Get-AipServiceConfiguration).FunctionalState` が次の場合は、実行して確認します `Enabled` 。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-131">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

2. <span data-ttu-id="ddfbd-132">機能状態が次の場合 `Disabled` は、実行します `Enable-AipService` 。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-132">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="step-2-configure-dns-encryption"></a><span data-ttu-id="ddfbd-133">手順 2: DNS 暗号化を構成する</span><span class="sxs-lookup"><span data-stu-id="ddfbd-133">Step 2: Configure DNS encryption</span></span>

<span data-ttu-id="ddfbd-134">暗号化を正しく機能Officeクライアント アプリケーションは、サービスの中国のインスタンスに接続し、そこからブートストラップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-134">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="ddfbd-135">クライアント アプリケーションを適切なサービス インスタンスにリダイレクトするには、テナント管理者が Azure RMS URL に関する情報を含む DNS SRV レコードを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-135">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="ddfbd-136">DNS SRV レコードがない場合、クライアント アプリケーションは既定でパブリック クラウド インスタンスへの接続を試み、失敗します。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-136">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="ddfbd-137">また、ユーザーは、ユーザー名ではなく、テナント所有のドメインに基づくユーザー名 (たとえば、) を使用してログインすると想定 `joe@contoso.cn` `onmschina` しています `joe@contoso.onmschina.cn` 。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-137">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="ddfbd-138">ユーザー名のドメイン名は、正しいサービス インスタンスへの DNS リダイレクトに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-138">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

#### <a name="configure-dns-encryption---windows"></a><span data-ttu-id="ddfbd-139">DNS 暗号化の構成 - Windows</span><span class="sxs-lookup"><span data-stu-id="ddfbd-139">Configure DNS encryption - Windows</span></span>

1. <span data-ttu-id="ddfbd-140">RMS ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-140">Get the RMS ID:</span></span>

    1. <span data-ttu-id="ddfbd-141">管理者として PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-141">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="ddfbd-142">AIPService モジュールがインストールされていない場合は、実行します `Install-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-142">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="ddfbd-143">を使用してサービスに接続します `Connect-AipService -environmentname azurechinacloud` 。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-143">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    4. <span data-ttu-id="ddfbd-144">RMS `(Get-AipServiceConfiguration).RightsManagementServiceId` ID を取得するために実行します。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-144">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

2. <span data-ttu-id="ddfbd-145">DNS プロバイダーにログインし、ドメインの DNS 設定に移動して、新しい SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-145">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

    - <span data-ttu-id="ddfbd-146">サービス = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="ddfbd-146">Service = `_rmsredir`</span></span>
    - <span data-ttu-id="ddfbd-147">プロトコル = `_http`</span><span class="sxs-lookup"><span data-stu-id="ddfbd-147">Protocol = `_http`</span></span>
    - <span data-ttu-id="ddfbd-148">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="ddfbd-148">Name = `_tcp`</span></span>
    - <span data-ttu-id="ddfbd-149">Target = `[GUID].rms.aadrm.cn` (GUID は RMS ID)</span><span class="sxs-lookup"><span data-stu-id="ddfbd-149">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
    - <span data-ttu-id="ddfbd-150">Priority、Weight、Seconds、TTL = 既定値</span><span class="sxs-lookup"><span data-stu-id="ddfbd-150">Priority, Weight, Seconds, TTL = default values</span></span>

3. <span data-ttu-id="ddfbd-151">Azure portal でカスタム ドメインをテナントに [関連付ける](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-151">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="ddfbd-152">これにより、DNS のエントリが追加されます。DNS 設定に値を追加した後、検証に数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-152">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

4. <span data-ttu-id="ddfbd-153">対応するグローバル管理者の資格情報を使用して Microsoft 365 管理センターにログインし、ユーザー作成用のドメイン (たとえば `contoso.cn` ) を追加します。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-153">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="ddfbd-154">検証プロセスでは、追加の DNS 変更が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-154">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="ddfbd-155">確認が完了すると、ユーザーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-155">Once verification is done, users can be created.</span></span>

#### <a name="configure-dns-encryption---mac-ios-android"></a><span data-ttu-id="ddfbd-156">DNS 暗号化の構成 - Mac、iOS、Android</span><span class="sxs-lookup"><span data-stu-id="ddfbd-156">Configure DNS encryption - Mac, iOS, Android</span></span>

<span data-ttu-id="ddfbd-157">DNS プロバイダーにログインし、ドメインの DNS 設定に移動して、新しい SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-157">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="ddfbd-158">サービス = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="ddfbd-158">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="ddfbd-159">プロトコル = `_http`</span><span class="sxs-lookup"><span data-stu-id="ddfbd-159">Protocol = `_http`</span></span>
- <span data-ttu-id="ddfbd-160">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="ddfbd-160">Name = `_tcp`</span></span>
- <span data-ttu-id="ddfbd-161">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="ddfbd-161">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="ddfbd-162">ポート = `80`</span><span class="sxs-lookup"><span data-stu-id="ddfbd-162">Port = `80`</span></span>
- <span data-ttu-id="ddfbd-163">Priority、Weight、Seconds、TTL = 既定値</span><span class="sxs-lookup"><span data-stu-id="ddfbd-163">Priority, Weight, Seconds, TTL = default values</span></span>

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a><span data-ttu-id="ddfbd-164">手順 3: AIP 統合ラベル付けクライアントをインストールおよび構成する</span><span class="sxs-lookup"><span data-stu-id="ddfbd-164">Step 3: Install and configure the AIP unified labeling client</span></span>

<span data-ttu-id="ddfbd-165">Microsoft ダウンロード センターから AIP 統合ラベル付け [クライアントをダウンロードします](https://www.microsoft.com/download/details.aspx?id=53018)。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-165">Download the AIP unified labeling client from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="ddfbd-166">詳しくは、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-166">For more information, see:</span></span>

- [<span data-ttu-id="ddfbd-167">AIP ドキュメント</span><span class="sxs-lookup"><span data-stu-id="ddfbd-167">AIP documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="ddfbd-168">AIP バージョン履歴とサポート ポリシー</span><span class="sxs-lookup"><span data-stu-id="ddfbd-168">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="ddfbd-169">AIP システム要件</span><span class="sxs-lookup"><span data-stu-id="ddfbd-169">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="ddfbd-170">AIP クイック スタート: AIP クライアントを展開する</span><span class="sxs-lookup"><span data-stu-id="ddfbd-170">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="ddfbd-171">AIP 管理者ガイド</span><span class="sxs-lookup"><span data-stu-id="ddfbd-171">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="ddfbd-172">AIP ユーザー ガイド</span><span class="sxs-lookup"><span data-stu-id="ddfbd-172">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="ddfbd-173">Microsoft 365 の感度ラベルについて</span><span class="sxs-lookup"><span data-stu-id="ddfbd-173">Learn about Microsoft 365 sensitivity labels</span></span>](/microsoft-365/compliance/sensitivity-labels)

### <a name="step-4-configure-aip-apps-on-windows"></a><span data-ttu-id="ddfbd-174">手順 4: Windows で AIP アプリを構成する</span><span class="sxs-lookup"><span data-stu-id="ddfbd-174">Step 4: Configure AIP apps on Windows</span></span>

<span data-ttu-id="ddfbd-175">Windows 上の AIP アプリは、Azure China の正しい主権クラウドを指す次のレジストリ キーを必要とします。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-175">AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="ddfbd-176">レジストリ ノード = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="ddfbd-176">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="ddfbd-177">Name = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="ddfbd-177">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="ddfbd-178">値 = `6` (既定値 = 0)</span><span class="sxs-lookup"><span data-stu-id="ddfbd-178">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="ddfbd-179">Type = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="ddfbd-179">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ddfbd-180">アンインストール後にレジストリ キーが削除されるのを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-180">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="ddfbd-181">キーが空、正しくない、または存在しない場合、機能は既定値 (商用クラウドの既定値 = 0) として動作します。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-181">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="ddfbd-182">キーが空または正しくない場合は、印刷エラーもログに追加されます。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-182">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a><span data-ttu-id="ddfbd-183">手順 5: AIP オンプレミス スキャナーをインストールし、コンテンツ スキャン ジョブを管理する</span><span class="sxs-lookup"><span data-stu-id="ddfbd-183">Step 5: Install the AIP on-premises scanner and manage content scan jobs</span></span>

<span data-ttu-id="ddfbd-184">AIP オンプレミス スキャナーをインストールして、ネットワークとコンテンツ共有で機密データをスキャンし、組織のポリシーで構成されている分類ラベルと保護ラベルを適用します。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-184">Install the AIP on-premises scanner to scan your network and content shares for sensitive data, and apply classification and protection labels as configured in your organization's policy.</span></span>

<span data-ttu-id="ddfbd-185">スキャナーをインストールしてコンテンツ スキャン ジョブを管理する場合は、商用製品で使用される Azure ポータル インターフェイスの代わりに、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-185">When installing the scanner and managing your content scan jobs, use the following cmdlets instead of the Azure portal interface that's used by the commercial offerings:</span></span><br><br>

| <span data-ttu-id="ddfbd-186">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="ddfbd-186">Cmdlet</span></span> | <span data-ttu-id="ddfbd-187">説明</span><span class="sxs-lookup"><span data-stu-id="ddfbd-187">Description</span></span> |
|--|--|
| [<span data-ttu-id="ddfbd-188">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="ddfbd-188">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="ddfbd-189">コンテンツ スキャン ジョブに新しいリポジトリを追加します。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-189">Adds a new repository to your content scan job.</span></span> |
| [<span data-ttu-id="ddfbd-190">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="ddfbd-190">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="ddfbd-191">コンテンツ スキャン ジョブに関する詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-191">Gets details about your content scan job.</span></span> |
| [<span data-ttu-id="ddfbd-192">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="ddfbd-192">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="ddfbd-193">コンテンツ スキャン ジョブに対して定義されているリポジトリに関する詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-193">Gets details about repositories defined for your content scan job.</span></span> |
| [<span data-ttu-id="ddfbd-194">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="ddfbd-194">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="ddfbd-195">コンテンツ スキャン ジョブを削除します。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-195">Deletes your content scan job.</span></span> |
| [<span data-ttu-id="ddfbd-196">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="ddfbd-196">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="ddfbd-197">コンテンツ スキャン ジョブからリポジトリを削除します。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-197">Removes a repository from your content scan job.</span></span> |
| [<span data-ttu-id="ddfbd-198">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="ddfbd-198">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="ddfbd-199">コンテンツ スキャン ジョブの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-199">Defines settings for your content scan job.</span></span> |
| [<span data-ttu-id="ddfbd-200">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="ddfbd-200">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="ddfbd-201">コンテンツ スキャン ジョブの既存のリポジトリの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-201">Defines settings for an existing repository in your content scan job.</span></span> |

<span data-ttu-id="ddfbd-202">詳細については [、「Azure Information Protection](/azure/information-protection/deploy-aip-scanner) 統合ラベル付けスキャナーとは」および [「PowerShell](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)のみを使用してコンテンツ スキャン ジョブを管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ddfbd-202">For more information, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) and [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>