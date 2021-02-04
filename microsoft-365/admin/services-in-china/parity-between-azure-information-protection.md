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
ms.openlocfilehash: 300e7633237511fb9de64199ae7cf54594f2239e
ms.sourcegitcommit: 3b369a44b71540c8b8214ce588a7aa6f47c3bb1e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099680"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a><span data-ttu-id="63f6b-103">21Vianet が運用Office 365 に対する Azure Information Protection のサポート</span><span class="sxs-lookup"><span data-stu-id="63f6b-103">Azure Information Protection support for Office 365 operated by 21Vianet</span></span>

<span data-ttu-id="63f6b-104">この記事では、21Vianet が運用している Office 365 の Azure Information Protection (AIP) サポートと商用製品の違い、および AIP オンプレミス スキャナーのインストール方法やコンテンツ スキャン ジョブの管理方法など、中国のお客様向け AIP を構成する具体的な手順について説明します。 &mdash;</span><span class="sxs-lookup"><span data-stu-id="63f6b-104">This article covers the differences between Azure Information Protection (AIP) support for Office 365 operated by 21Vianet and commercial offerings, as well as specific instructions for configuring AIP for customers in China&mdash;including how to install the AIP on-premises scanner and manage content scan jobs.</span></span>

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="63f6b-105">21Vianet が運用Office 365 の AIP と商用製品の相違点</span><span class="sxs-lookup"><span data-stu-id="63f6b-105">Differences between AIP for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="63f6b-106">この目標は、21Vianet が運用している Office 365 用の AIP を使用して、中国のお客様にすべての商用機能を提供することで実現しますが、強調表示する機能が不足しています。</span><span class="sxs-lookup"><span data-stu-id="63f6b-106">While our goal is to deliver all commercial features and functionality to customers in China with our AIP for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="63f6b-107">以下に、21Vianet が運用している Office 365 用の AIP と、2021 年 1 月の商用サービスの間の既存のギャップを示します。</span><span class="sxs-lookup"><span data-stu-id="63f6b-107">The following list includes the existing gaps between AIP for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="63f6b-108">Information Rights Management (IRM) は、Microsoft 365 Apps for enterprise (ビルド 11731.10000 以上) でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="63f6b-108">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="63f6b-109">Office 2010、Office 2013、その他の Office 2016 バージョンはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="63f6b-109">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="63f6b-110">現在、Active Directory Rights Management サービス (AD RMS) から AIP への移行は使用できません。</span><span class="sxs-lookup"><span data-stu-id="63f6b-110">Migration from Active Directory Rights Management Services (AD RMS) to AIP is currently not available.</span></span>
  
- <span data-ttu-id="63f6b-111">商用クラウドのユーザーとの保護されたメールの共有がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="63f6b-111">Sharing of protected emails with users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="63f6b-112">現在、商用クラウドのユーザーとのドキュメントとメールの添付ファイルの共有は利用できません。</span><span class="sxs-lookup"><span data-stu-id="63f6b-112">Sharing of documents and email attachments with users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="63f6b-113">これには、商用クラウドで 21Vianet ユーザーが運用している Office 365、商用クラウドの 21Vianet ユーザーが運用している Office 365 以外のユーザー、および個人向け RMS ライセンスを持つユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="63f6b-113">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="63f6b-114">現在、SharePoint での IRM (IRM で保護されたサイトとライブラリ) は使用できません。</span><span class="sxs-lookup"><span data-stu-id="63f6b-114">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="63f6b-115">現在、RMS 用モバイル AD拡張機能は使用できません。</span><span class="sxs-lookup"><span data-stu-id="63f6b-115">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="63f6b-116">モバイル [ビューアーは](/azure/information-protection/rms-client/mobile-app-faq) 、Azure China 21Vianet ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="63f6b-116">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

- <span data-ttu-id="63f6b-117">Azure ポータルの AIP 領域は、中国のお客様は利用できません。</span><span class="sxs-lookup"><span data-stu-id="63f6b-117">The AIP area of the Azure portal is unavailable to customers in China.</span></span> <span data-ttu-id="63f6b-118">オンプレミス スキャナーのインストールやコンテンツ スキャン ジョブの管理など、ポータルでアクションを実行する代わりに [PowerShell](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="63f6b-118">Use [PowerShell commands](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) instead of performing actions in the portal, such as installing the on-premises scanner and managing your content scan jobs.</span></span>

## <a name="configure-aip-for-customers-in-china"></a><span data-ttu-id="63f6b-119">中国のお客様向け AIP の構成</span><span class="sxs-lookup"><span data-stu-id="63f6b-119">Configure AIP for customers in China</span></span>

<span data-ttu-id="63f6b-120">中国のお客様向け AIP を構成するには:</span><span class="sxs-lookup"><span data-stu-id="63f6b-120">To configure AIP for customers in China:</span></span>
1. <span data-ttu-id="63f6b-121">[テナントの Rights Management を有効にします](#step-1-enable-rights-management-for-the-tenant)。</span><span class="sxs-lookup"><span data-stu-id="63f6b-121">[Enable Rights Management for the tenant](#step-1-enable-rights-management-for-the-tenant).</span></span>

2. <span data-ttu-id="63f6b-122">[DNS 暗号化を構成します](#step-2-configure-dns-encryption)。</span><span class="sxs-lookup"><span data-stu-id="63f6b-122">[Configure DNS encryption](#step-2-configure-dns-encryption).</span></span>

3. <span data-ttu-id="63f6b-123">[AIP 統合ラベル付けクライアントをインストールして構成します](#step-3-install-and-configure-the-aip-unified-labeling-client)。</span><span class="sxs-lookup"><span data-stu-id="63f6b-123">[Install and configure the AIP unified labeling client](#step-3-install-and-configure-the-aip-unified-labeling-client).</span></span>

4. <span data-ttu-id="63f6b-124">[Windows で AIP アプリを構成します](#step-4-configure-aip-apps-on-windows)。</span><span class="sxs-lookup"><span data-stu-id="63f6b-124">[Configure AIP apps on Windows](#step-4-configure-aip-apps-on-windows).</span></span>

5. <span data-ttu-id="63f6b-125">[AIP オンプレミス スキャナーをインストールし、コンテンツ スキャン ジョブを管理します](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)。</span><span class="sxs-lookup"><span data-stu-id="63f6b-125">[Install the AIP on-premises scanner and manage content scan jobs](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs).</span></span> 

### <a name="step-1-enable-rights-management-for-the-tenant"></a><span data-ttu-id="63f6b-126">手順 1: テナントの Rights Management を有効にする</span><span class="sxs-lookup"><span data-stu-id="63f6b-126">Step 1: Enable Rights Management for the tenant</span></span>

<span data-ttu-id="63f6b-127">暗号化が正しく機能するには、テナントに対して RMS を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="63f6b-127">For the encryption to work correctly, RMS must be enabled for the tenant.</span></span>

1. <span data-ttu-id="63f6b-128">RMS が有効になっているか確認します。</span><span class="sxs-lookup"><span data-stu-id="63f6b-128">Check if RMS is enabled:</span></span>

    1. <span data-ttu-id="63f6b-129">管理者として PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="63f6b-129">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="63f6b-130">AIPService モジュールがインストールされていない場合は、実行します `Install-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="63f6b-130">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="63f6b-131">を使用してモジュールをインポートします `Import-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="63f6b-131">Import the module using `Import-Module AipService`.</span></span>
    4. <span data-ttu-id="63f6b-132">を使用してサービスに接続します `Connect-AipService -environmentname azurechinacloud` 。</span><span class="sxs-lookup"><span data-stu-id="63f6b-132">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    5. <span data-ttu-id="63f6b-133">状態 `(Get-AipServiceConfiguration).FunctionalState` が次の場合は、実行して確認します `Enabled` 。</span><span class="sxs-lookup"><span data-stu-id="63f6b-133">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

2. <span data-ttu-id="63f6b-134">機能状態が次の場合 `Disabled` は、実行します `Enable-AipService` 。</span><span class="sxs-lookup"><span data-stu-id="63f6b-134">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="step-2-configure-dns-encryption"></a><span data-ttu-id="63f6b-135">手順 2: DNS 暗号化を構成する</span><span class="sxs-lookup"><span data-stu-id="63f6b-135">Step 2: Configure DNS encryption</span></span>

<span data-ttu-id="63f6b-136">暗号化を正しく機能Officeクライアント アプリケーションは、サービスの中国のインスタンスに接続し、そこからブートストラップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="63f6b-136">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="63f6b-137">クライアント アプリケーションを適切なサービス インスタンスにリダイレクトするには、テナント管理者が Azure RMS URL に関する情報を含む DNS SRV レコードを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63f6b-137">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="63f6b-138">DNS SRV レコードがない場合、クライアント アプリケーションは既定でパブリック クラウド インスタンスへの接続を試み、失敗します。</span><span class="sxs-lookup"><span data-stu-id="63f6b-138">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="63f6b-139">また、ユーザーは、ユーザー名ではなく、テナント所有のドメインに基づくユーザー名 (たとえば、) を使用してログインすると想定 `joe@contoso.cn` `onmschina` しています `joe@contoso.onmschina.cn` 。</span><span class="sxs-lookup"><span data-stu-id="63f6b-139">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="63f6b-140">ユーザー名のドメイン名は、正しいサービス インスタンスへの DNS リダイレクトに使用されます。</span><span class="sxs-lookup"><span data-stu-id="63f6b-140">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

#### <a name="configure-dns-encryption---windows"></a><span data-ttu-id="63f6b-141">DNS 暗号化の構成 - Windows</span><span class="sxs-lookup"><span data-stu-id="63f6b-141">Configure DNS encryption - Windows</span></span>

1. <span data-ttu-id="63f6b-142">RMS ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="63f6b-142">Get the RMS ID:</span></span>

    1. <span data-ttu-id="63f6b-143">管理者として PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="63f6b-143">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="63f6b-144">AIPService モジュールがインストールされていない場合は、実行します `Install-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="63f6b-144">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="63f6b-145">を使用してサービスに接続します `Connect-AipService -environmentname azurechinacloud` 。</span><span class="sxs-lookup"><span data-stu-id="63f6b-145">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    4. <span data-ttu-id="63f6b-146">RMS `(Get-AipServiceConfiguration).RightsManagementServiceId` ID を取得するために実行します。</span><span class="sxs-lookup"><span data-stu-id="63f6b-146">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

2. <span data-ttu-id="63f6b-147">DNS プロバイダーにログインし、ドメインの DNS 設定に移動して、新しい SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="63f6b-147">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

    - <span data-ttu-id="63f6b-148">サービス = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="63f6b-148">Service = `_rmsredir`</span></span>
    - <span data-ttu-id="63f6b-149">プロトコル = `_http`</span><span class="sxs-lookup"><span data-stu-id="63f6b-149">Protocol = `_http`</span></span>
    - <span data-ttu-id="63f6b-150">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="63f6b-150">Name = `_tcp`</span></span>
    - <span data-ttu-id="63f6b-151">Target = `[GUID].rms.aadrm.cn` (GUID は RMS ID)</span><span class="sxs-lookup"><span data-stu-id="63f6b-151">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
    - <span data-ttu-id="63f6b-152">Priority、Weight、Seconds、TTL = 既定値</span><span class="sxs-lookup"><span data-stu-id="63f6b-152">Priority, Weight, Seconds, TTL = default values</span></span>

3. <span data-ttu-id="63f6b-153">Azure portal でカスタム ドメインをテナントに [関連付ける](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)。</span><span class="sxs-lookup"><span data-stu-id="63f6b-153">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="63f6b-154">これにより、DNS にエントリが追加されます。DNS 設定に値を追加した後、検証に数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="63f6b-154">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

4. <span data-ttu-id="63f6b-155">対応するグローバル管理者の資格情報を使用して Microsoft 365 管理センターにログインし、ユーザー作成用のドメイン (たとえば `contoso.cn` ) を追加します。</span><span class="sxs-lookup"><span data-stu-id="63f6b-155">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="63f6b-156">検証プロセスでは、追加の DNS 変更が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="63f6b-156">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="63f6b-157">確認が完了すると、ユーザーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="63f6b-157">Once verification is done, users can be created.</span></span>

#### <a name="configure-dns-encryption---mac-ios-android"></a><span data-ttu-id="63f6b-158">DNS 暗号化の構成 - Mac、iOS、Android</span><span class="sxs-lookup"><span data-stu-id="63f6b-158">Configure DNS encryption - Mac, iOS, Android</span></span>

<span data-ttu-id="63f6b-159">DNS プロバイダーにログインし、ドメインの DNS 設定に移動して、新しい SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="63f6b-159">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="63f6b-160">サービス = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="63f6b-160">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="63f6b-161">プロトコル = `_http`</span><span class="sxs-lookup"><span data-stu-id="63f6b-161">Protocol = `_http`</span></span>
- <span data-ttu-id="63f6b-162">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="63f6b-162">Name = `_tcp`</span></span>
- <span data-ttu-id="63f6b-163">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="63f6b-163">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="63f6b-164">ポート = `80`</span><span class="sxs-lookup"><span data-stu-id="63f6b-164">Port = `80`</span></span>
- <span data-ttu-id="63f6b-165">Priority、Weight、Seconds、TTL = 既定値</span><span class="sxs-lookup"><span data-stu-id="63f6b-165">Priority, Weight, Seconds, TTL = default values</span></span>

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a><span data-ttu-id="63f6b-166">手順 3: AIP 統合ラベル付けクライアントをインストールおよび構成する</span><span class="sxs-lookup"><span data-stu-id="63f6b-166">Step 3: Install and configure the AIP unified labeling client</span></span>

<span data-ttu-id="63f6b-167">Microsoft ダウンロード センターから AIP 統合ラベル付け [クライアントをダウンロードします](https://www.microsoft.com/download/details.aspx?id=53018)。</span><span class="sxs-lookup"><span data-stu-id="63f6b-167">Download the AIP unified labeling client from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="63f6b-168">詳しくは、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63f6b-168">For more information, see:</span></span>

- [<span data-ttu-id="63f6b-169">AIP ドキュメント</span><span class="sxs-lookup"><span data-stu-id="63f6b-169">AIP documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="63f6b-170">AIP バージョン履歴とサポート ポリシー</span><span class="sxs-lookup"><span data-stu-id="63f6b-170">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="63f6b-171">AIP システム要件</span><span class="sxs-lookup"><span data-stu-id="63f6b-171">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="63f6b-172">AIP クイック スタート: AIP クライアントを展開する</span><span class="sxs-lookup"><span data-stu-id="63f6b-172">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="63f6b-173">AIP 管理者ガイド</span><span class="sxs-lookup"><span data-stu-id="63f6b-173">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="63f6b-174">AIP ユーザー ガイド</span><span class="sxs-lookup"><span data-stu-id="63f6b-174">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="63f6b-175">Microsoft 365 の感度ラベルについて</span><span class="sxs-lookup"><span data-stu-id="63f6b-175">Learn about Microsoft 365 sensitivity labels</span></span>](/microsoft-365/compliance/sensitivity-labels)

### <a name="step-4-configure-aip-apps-on-windows"></a><span data-ttu-id="63f6b-176">手順 4: Windows で AIP アプリを構成する</span><span class="sxs-lookup"><span data-stu-id="63f6b-176">Step 4: Configure AIP apps on Windows</span></span>

<span data-ttu-id="63f6b-177">Windows 上の AIP アプリは、Azure China の正しい主権クラウドを指し示す次のレジストリ キーを必要とします。</span><span class="sxs-lookup"><span data-stu-id="63f6b-177">AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="63f6b-178">レジストリ ノード = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="63f6b-178">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="63f6b-179">Name = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="63f6b-179">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="63f6b-180">値 = `6` (既定値 = 0)</span><span class="sxs-lookup"><span data-stu-id="63f6b-180">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="63f6b-181">Type = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="63f6b-181">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="63f6b-182">アンインストール後にレジストリ キーが削除されるのを確認してください。</span><span class="sxs-lookup"><span data-stu-id="63f6b-182">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="63f6b-183">キーが空、正しくない、または存在しない場合、機能は既定値として動作します (商用クラウドの既定値は 0 です)。</span><span class="sxs-lookup"><span data-stu-id="63f6b-183">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="63f6b-184">キーが空または正しくない場合は、印刷エラーもログに追加されます。</span><span class="sxs-lookup"><span data-stu-id="63f6b-184">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a><span data-ttu-id="63f6b-185">手順 5: AIP オンプレミス スキャナーをインストールし、コンテンツ スキャン ジョブを管理する</span><span class="sxs-lookup"><span data-stu-id="63f6b-185">Step 5: Install the AIP on-premises scanner and manage content scan jobs</span></span>

<span data-ttu-id="63f6b-186">AIP オンプレミス スキャナーをインストールして、ネットワークとコンテンツ共有で機密データをスキャンし、組織のポリシーで構成されている分類ラベルと保護ラベルを適用します。</span><span class="sxs-lookup"><span data-stu-id="63f6b-186">Install the AIP on-premises scanner to scan your network and content shares for sensitive data, and apply classification and protection labels as configured in your organization's policy.</span></span>

<span data-ttu-id="63f6b-187">スキャナーをインストールしてコンテンツ スキャン ジョブを管理する場合は、商用製品で使用される Azure ポータル インターフェイスの代わりに、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="63f6b-187">When installing the scanner and managing your content scan jobs, use the following cmdlets instead of the Azure portal interface that's used by the commercial offerings:</span></span><br><br>

| <span data-ttu-id="63f6b-188">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="63f6b-188">Cmdlet</span></span> | <span data-ttu-id="63f6b-189">説明</span><span class="sxs-lookup"><span data-stu-id="63f6b-189">Description</span></span> |
|--|--|
| [<span data-ttu-id="63f6b-190">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="63f6b-190">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="63f6b-191">コンテンツ スキャン ジョブに新しいリポジトリを追加します。</span><span class="sxs-lookup"><span data-stu-id="63f6b-191">Adds a new repository to your content scan job.</span></span> |
| [<span data-ttu-id="63f6b-192">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="63f6b-192">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="63f6b-193">コンテンツ スキャン ジョブに関する詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="63f6b-193">Gets details about your content scan job.</span></span> |
| [<span data-ttu-id="63f6b-194">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="63f6b-194">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="63f6b-195">コンテンツ スキャン ジョブに対して定義されているリポジトリに関する詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="63f6b-195">Gets details about repositories defined for your content scan job.</span></span> |
| [<span data-ttu-id="63f6b-196">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="63f6b-196">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="63f6b-197">コンテンツ スキャン ジョブを削除します。</span><span class="sxs-lookup"><span data-stu-id="63f6b-197">Deletes your content scan job.</span></span> |
| [<span data-ttu-id="63f6b-198">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="63f6b-198">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="63f6b-199">コンテンツ スキャン ジョブからリポジトリを削除します。</span><span class="sxs-lookup"><span data-stu-id="63f6b-199">Removes a repository from your content scan job.</span></span> |
| [<span data-ttu-id="63f6b-200">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="63f6b-200">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="63f6b-201">コンテンツ スキャン ジョブの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="63f6b-201">Defines settings for your content scan job.</span></span> |
| [<span data-ttu-id="63f6b-202">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="63f6b-202">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="63f6b-203">コンテンツ スキャン ジョブの既存のリポジトリの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="63f6b-203">Defines settings for an existing repository in your content scan job.</span></span> |

<span data-ttu-id="63f6b-204">詳細については [、「Azure Information Protection](/azure/information-protection/deploy-aip-scanner) 統合ラベルスキャナーとは」および [「PowerShell](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)のみを使用してコンテンツ スキャン ジョブを管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63f6b-204">For more information, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) and [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>
