---
title: 21Vianet が運用している Office 365 向け Azure Information Protection と商用サービスの間のパリティ
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
ms.reviewer: arthurj
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
ms.openlocfilehash: 50269749b5f4e544263f790ec9c7e4474af57219
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840303"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="61d4f-103">21Vianet が運用している Office 365 向け Azure Information Protection と商用サービスの間のパリティ</span><span class="sxs-lookup"><span data-stu-id="61d4f-103">Parity between Azure Information Protection for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="61d4f-104">この目標は、21Vianet が運用している Office 365 向け Azure Information Protection (AIP) が提供する中国のお客様に、すべての商用機能を提供することで実現しますが、強調表示する機能が不足しています。</span><span class="sxs-lookup"><span data-stu-id="61d4f-104">While our goal is to deliver all commercial features and functionality to customers in China with our Azure Information Protection (AIP) for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="61d4f-105">次の一覧には、21Vianet が運用している Office 365 向け Azure Information Protection と 2021 年 1 月の商用サービスの間の既存のギャップが含まれています。</span><span class="sxs-lookup"><span data-stu-id="61d4f-105">The following list includes the existing gaps between Azure Information Protection for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="61d4f-106">Information Rights Management (IRM) は、Microsoft 365 Apps for enterprise (ビルド 11731.10000 以上) でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="61d4f-106">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="61d4f-107">Office 2010、Office 2013、その他の Office 2016 バージョンはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="61d4f-107">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="61d4f-108">現在、Active Directory Rights Management サービス (AD RMS) から Azure Information Protection への移行は利用できません。</span><span class="sxs-lookup"><span data-stu-id="61d4f-108">Migration from Active Directory Rights Management Services (AD RMS) to Azure Information Protection is currently not available.</span></span>
  
- <span data-ttu-id="61d4f-109">商用クラウド内のユーザーへの保護された電子メールの共有がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="61d4f-109">Sharing of protected emails to users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="61d4f-110">現在、商用クラウド内のユーザーへのドキュメントとメールの添付ファイルの共有は利用できません。</span><span class="sxs-lookup"><span data-stu-id="61d4f-110">Sharing of documents and email attachments to users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="61d4f-111">これには、商用クラウドで 21Vianet ユーザーが運用している Office 365、商用クラウドの 21Vianet ユーザーが運用している Office 365 以外のユーザー、および個人向け RMS ライセンスを持つユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="61d4f-111">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="61d4f-112">現在、SharePoint での IRM (IRM で保護されたサイトとライブラリ) は使用できません。</span><span class="sxs-lookup"><span data-stu-id="61d4f-112">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="61d4f-113">現在、RMS 用モバイル AD拡張機能は使用できません。</span><span class="sxs-lookup"><span data-stu-id="61d4f-113">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="61d4f-114">モバイル [ビューアーは](/azure/information-protection/rms-client/mobile-app-faq) 、Azure China 21Vianet ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="61d4f-114">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

## <a name="configuring-azure-information-protection-for-customers-in-china"></a><span data-ttu-id="61d4f-115">中国のお客様向け Azure Information Protection の構成</span><span class="sxs-lookup"><span data-stu-id="61d4f-115">Configuring Azure Information Protection for customers in China</span></span>

### <a name="enable-rights-management-for-the-tenant"></a><span data-ttu-id="61d4f-116">テナントの Rights Management を有効にする</span><span class="sxs-lookup"><span data-stu-id="61d4f-116">Enable Rights Management for the tenant</span></span>

<span data-ttu-id="61d4f-117">暗号化が正しく機能するには、テナントに対して RMS を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="61d4f-117">For the encryption to work correctly, the RMS must be enabled for the tenant.</span></span>

- <span data-ttu-id="61d4f-118">RMS が有効になっているか確認します。</span><span class="sxs-lookup"><span data-stu-id="61d4f-118">Check if the RMS is enabled:</span></span>
  1. <span data-ttu-id="61d4f-119">管理者として PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="61d4f-119">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="61d4f-120">AIPService モジュールがインストールされていない場合は、実行します `Install-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="61d4f-120">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="61d4f-121">を使用してモジュールをインポートします `Import-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="61d4f-121">Import the module using `Import-Module AipService`.</span></span>
  4. <span data-ttu-id="61d4f-122">を使用してサービスに接続します `Connect-AipService -environmentname azurechinacloud` 。</span><span class="sxs-lookup"><span data-stu-id="61d4f-122">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  5. <span data-ttu-id="61d4f-123">状態 `(Get-AipServiceConfiguration).FunctionalState` が次の場合は、実行して確認します `Enabled` 。</span><span class="sxs-lookup"><span data-stu-id="61d4f-123">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

- <span data-ttu-id="61d4f-124">機能状態が次の場合 `Disabled` は、実行します `Enable-AipService` 。</span><span class="sxs-lookup"><span data-stu-id="61d4f-124">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="dns-configuration-for-encryption-windows"></a><span data-ttu-id="61d4f-125">暗号化用の DNS 構成 (Windows)</span><span class="sxs-lookup"><span data-stu-id="61d4f-125">DNS configuration for encryption (Windows)</span></span>

<span data-ttu-id="61d4f-126">暗号化を正しく機能Officeクライアント アプリケーションは、サービスの中国のインスタンスに接続し、そこからブートストラップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="61d4f-126">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="61d4f-127">クライアント アプリケーションを適切なサービス インスタンスにリダイレクトするには、テナント管理者が Azure RMS URL に関する情報を含む DNS SRV レコードを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61d4f-127">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="61d4f-128">DNS SRV レコードがない場合、クライアント アプリケーションは既定でパブリック クラウド インスタンスへの接続を試み、失敗します。</span><span class="sxs-lookup"><span data-stu-id="61d4f-128">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="61d4f-129">また、ユーザーは、ユーザー名ではなく、テナント所有のドメインに基づくユーザー名 (たとえば、) を使用してログインすると想定 `joe@contoso.cn` `onmschina` しています `joe@contoso.onmschina.cn` 。</span><span class="sxs-lookup"><span data-stu-id="61d4f-129">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="61d4f-130">ユーザー名のドメイン名は、正しいサービス インスタンスへの DNS リダイレクトに使用されます。</span><span class="sxs-lookup"><span data-stu-id="61d4f-130">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

- <span data-ttu-id="61d4f-131">RMS ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="61d4f-131">Get the RMS ID:</span></span>
  1. <span data-ttu-id="61d4f-132">管理者として PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="61d4f-132">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="61d4f-133">AIPService モジュールがインストールされていない場合は、実行します `Install-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="61d4f-133">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="61d4f-134">を使用してサービスに接続します `Connect-AipService -environmentname azurechinacloud` 。</span><span class="sxs-lookup"><span data-stu-id="61d4f-134">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  4. <span data-ttu-id="61d4f-135">RMS `(Get-AipServiceConfiguration).RightsManagementServiceId` ID を取得するために実行します。</span><span class="sxs-lookup"><span data-stu-id="61d4f-135">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

- <span data-ttu-id="61d4f-136">DNS プロバイダーにログインし、ドメインの DNS 設定に移動して、新しい SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="61d4f-136">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="61d4f-137">サービス = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="61d4f-137">Service = `_rmsredir`</span></span>
  - <span data-ttu-id="61d4f-138">プロトコル = `_http`</span><span class="sxs-lookup"><span data-stu-id="61d4f-138">Protocol = `_http`</span></span>
  - <span data-ttu-id="61d4f-139">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="61d4f-139">Name = `_tcp`</span></span>
  - <span data-ttu-id="61d4f-140">Target = `[GUID].rms.aadrm.cn` (GUID は RMS ID)</span><span class="sxs-lookup"><span data-stu-id="61d4f-140">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
  - <span data-ttu-id="61d4f-141">Priority、Weight、Seconds、TTL = 既定値</span><span class="sxs-lookup"><span data-stu-id="61d4f-141">Priority, Weight, Seconds, TTL = default values</span></span>

- <span data-ttu-id="61d4f-142">Azure portal でカスタム ドメインをテナントに [関連付ける](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)。</span><span class="sxs-lookup"><span data-stu-id="61d4f-142">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="61d4f-143">これにより、DNS にエントリが追加されます。DNS 設定に値を追加した後、検証に数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="61d4f-143">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

- <span data-ttu-id="61d4f-144">対応するグローバル管理者の資格情報を使用して Microsoft 365 管理センターにログインし、ユーザー作成用のドメイン (たとえば `contoso.cn` ) を追加します。</span><span class="sxs-lookup"><span data-stu-id="61d4f-144">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="61d4f-145">検証プロセスでは、追加の DNS 変更が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="61d4f-145">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="61d4f-146">確認が完了すると、ユーザーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="61d4f-146">Once verification is done, users can be created.</span></span>

### <a name="dns-configuration-for-encryption-mac-ios-android"></a><span data-ttu-id="61d4f-147">暗号化用の DNS 構成 (Mac、iOS、Android)</span><span class="sxs-lookup"><span data-stu-id="61d4f-147">DNS configuration for encryption (Mac, iOS, Android)</span></span>

<span data-ttu-id="61d4f-148">DNS プロバイダーにログインし、ドメインの DNS 設定に移動して、新しい SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="61d4f-148">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="61d4f-149">サービス = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="61d4f-149">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="61d4f-150">プロトコル = `_http`</span><span class="sxs-lookup"><span data-stu-id="61d4f-150">Protocol = `_http`</span></span>
- <span data-ttu-id="61d4f-151">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="61d4f-151">Name = `_tcp`</span></span>
- <span data-ttu-id="61d4f-152">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="61d4f-152">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="61d4f-153">ポート = `80`</span><span class="sxs-lookup"><span data-stu-id="61d4f-153">Port = `80`</span></span>
- <span data-ttu-id="61d4f-154">Priority、Weight、Seconds、TTL = 既定値</span><span class="sxs-lookup"><span data-stu-id="61d4f-154">Priority, Weight, Seconds, TTL = default values</span></span>

### <a name="aip-client-configuration"></a><span data-ttu-id="61d4f-155">AIP クライアント構成</span><span class="sxs-lookup"><span data-stu-id="61d4f-155">AIP client configuration</span></span>

<span data-ttu-id="61d4f-156">統合 AIP クライアントは、Microsoft ダウンロード センター [からダウンロードできます](https://www.microsoft.com/download/details.aspx?id=53018)。</span><span class="sxs-lookup"><span data-stu-id="61d4f-156">The unified AIP client can be downloaded from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="61d4f-157">詳しくは、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61d4f-157">For more information, see:</span></span>

- [<span data-ttu-id="61d4f-158">Azure Information Protection のドキュメント</span><span class="sxs-lookup"><span data-stu-id="61d4f-158">Azure Information Protection documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="61d4f-159">AIP バージョン履歴とサポート ポリシー</span><span class="sxs-lookup"><span data-stu-id="61d4f-159">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="61d4f-160">AIP システム要件</span><span class="sxs-lookup"><span data-stu-id="61d4f-160">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="61d4f-161">AIP クイック スタート: AIP クライアントを展開する</span><span class="sxs-lookup"><span data-stu-id="61d4f-161">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="61d4f-162">AIP 管理者ガイド</span><span class="sxs-lookup"><span data-stu-id="61d4f-162">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="61d4f-163">AIP ユーザー ガイド</span><span class="sxs-lookup"><span data-stu-id="61d4f-163">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="61d4f-164">Microsoft 365 の感度ラベルについて</span><span class="sxs-lookup"><span data-stu-id="61d4f-164">Learn about Microsoft 365 sensitivity labels</span></span>](/microsoft-365/compliance/sensitivity-labels)

### <a name="aip-apps-configuration-unified-labeling-client-only"></a><span data-ttu-id="61d4f-165">AIP アプリの構成 (統合ラベル付けクライアントのみ)</span><span class="sxs-lookup"><span data-stu-id="61d4f-165">AIP apps configuration (unified labeling client only)</span></span>

<span data-ttu-id="61d4f-166">統合ラベル付けソリューションでは、Windows 上の AIP アプリが Azure China 用の正しい主権クラウドを指し示す次のレジストリ キーを必要とします。</span><span class="sxs-lookup"><span data-stu-id="61d4f-166">For the unified labeling solution, AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="61d4f-167">レジストリ ノード = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="61d4f-167">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="61d4f-168">Name = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="61d4f-168">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="61d4f-169">値 = `6` (既定値 = 0)</span><span class="sxs-lookup"><span data-stu-id="61d4f-169">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="61d4f-170">Type = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="61d4f-170">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="61d4f-171">アンインストール後にレジストリ キーが削除されるのを確認してください。</span><span class="sxs-lookup"><span data-stu-id="61d4f-171">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="61d4f-172">キーが空、正しくない、または存在しない場合、機能は既定値として動作します (商用クラウドの既定値は 0 です)。</span><span class="sxs-lookup"><span data-stu-id="61d4f-172">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="61d4f-173">キーが空または正しくない場合は、印刷エラーもログに追加されます。</span><span class="sxs-lookup"><span data-stu-id="61d4f-173">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="manage-azure-information-protection-content-scan-jobs"></a><span data-ttu-id="61d4f-174">Azure Information Protection コンテンツ スキャン ジョブを管理する</span><span class="sxs-lookup"><span data-stu-id="61d4f-174">Manage Azure Information Protection content scan jobs</span></span>

<span data-ttu-id="61d4f-175">Azure Information Protection コンテンツ スキャン ジョブを Azure China スキャナー サーバーで管理するには、Azure Portal の代わりに次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="61d4f-175">To manage your Azure Information Protection content scan jobs with an Azure China scanner server, use the following cmdlets instead of the Azure portal:</span></span><br><br>

| <span data-ttu-id="61d4f-176">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="61d4f-176">Cmdlet</span></span> | <span data-ttu-id="61d4f-177">説明</span><span class="sxs-lookup"><span data-stu-id="61d4f-177">Description</span></span> |
|--|--|
| [<span data-ttu-id="61d4f-178">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="61d4f-178">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="61d4f-179">コンテンツ スキャン ジョブに新しいリポジトリを追加します。</span><span class="sxs-lookup"><span data-stu-id="61d4f-179">Adds a new repository to your content scan job.</span></span> |
| [<span data-ttu-id="61d4f-180">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="61d4f-180">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="61d4f-181">コンテンツ スキャン ジョブに関する詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="61d4f-181">Gets details about your content scan job.</span></span> |
| [<span data-ttu-id="61d4f-182">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="61d4f-182">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="61d4f-183">コンテンツ スキャン ジョブに対して定義されているリポジトリに関する詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="61d4f-183">Gets details about repositories defined for your content scan job.</span></span> |
| [<span data-ttu-id="61d4f-184">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="61d4f-184">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="61d4f-185">コンテンツ スキャン ジョブを削除します。</span><span class="sxs-lookup"><span data-stu-id="61d4f-185">Deletes your content scan job.</span></span> |
| [<span data-ttu-id="61d4f-186">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="61d4f-186">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="61d4f-187">コンテンツ スキャン ジョブからリポジトリを削除します。</span><span class="sxs-lookup"><span data-stu-id="61d4f-187">Removes a repository from your content scan job.</span></span> |
| [<span data-ttu-id="61d4f-188">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="61d4f-188">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="61d4f-189">コンテンツ スキャン ジョブの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="61d4f-189">Defines settings for your content scan job.</span></span> |
| [<span data-ttu-id="61d4f-190">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="61d4f-190">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="61d4f-191">コンテンツ スキャン ジョブの既存のリポジトリの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="61d4f-191">Defines settings for an existing repository in your content scan job.</span></span> |

<span data-ttu-id="61d4f-192">詳細については [、「PowerShell のみを使用してコンテンツ スキャン ジョブを管理する」を参照してください](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)。</span><span class="sxs-lookup"><span data-stu-id="61d4f-192">For more information, see [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>