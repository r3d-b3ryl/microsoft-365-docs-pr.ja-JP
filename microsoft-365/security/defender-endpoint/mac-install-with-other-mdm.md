---
title: Microsoft Defender ATP for Mac 用の別のモバイル デバイス管理 (MDM) システムによる展開
description: Microsoft Defender ATP for Mac を他の管理ソリューションにインストールします。
keywords: microsoft、 defender, atp, mac, installation, deploy, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: mavel
author: maximvelichko
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e3a20f0a356a32eddc05b3792c0c04c23197a7b0
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185697"
---
# <a name="deployment-with-a-different-mobile-device-management-mdm-system-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="f7688-104">Microsoft Defender for Endpoint for Mac 用に異なるモバイル デバイス管理 (MDM) システムを使用した展開</span><span class="sxs-lookup"><span data-stu-id="f7688-104">Deployment with a different Mobile Device Management (MDM) system for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f7688-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="f7688-105">**Applies to:**</span></span>
- [<span data-ttu-id="f7688-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f7688-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f7688-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f7688-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f7688-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="f7688-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f7688-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="f7688-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)
 
## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="f7688-110">前提条件とシステム要件</span><span class="sxs-lookup"><span data-stu-id="f7688-110">Prerequisites and system requirements</span></span>

<span data-ttu-id="f7688-111">開始する前に、現在のソフトウェア バージョンの前提条件とシステム要件の説明については、 [メインの Microsoft Defender for Endpoint for Mac](microsoft-defender-endpoint-mac.md) ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7688-111">Before you get started, see [the main Microsoft Defender for Endpoint for Mac page](microsoft-defender-endpoint-mac.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="approach"></a><span data-ttu-id="f7688-112">方法</span><span class="sxs-lookup"><span data-stu-id="f7688-112">Approach</span></span>

> [!CAUTION]
> <span data-ttu-id="f7688-113">現在、Microsoft oficially は、Microsoft Defender for Endpoint for Mac の展開と管理のために Intune と JAMF のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="f7688-113">Currently, Microsoft oficially supports only Intune and JAMF for the deployment and management of Microsoft Defender for Endpoint for Mac.</span></span> <span data-ttu-id="f7688-114">Microsoft は、以下に示す情報に関して、明示または黙示を問わず一切の保証を行いません。</span><span class="sxs-lookup"><span data-stu-id="f7688-114">Microsoft makes no warranties, express or implied, with respect to the information provided below.</span></span>

<span data-ttu-id="f7688-115">組織で正式にサポートされていないモバイル デバイス管理 (MDM) ソリューションを使用している場合、Microsoft Defender for Endpoint for Mac を展開または実行できないという意味ではありません。</span><span class="sxs-lookup"><span data-stu-id="f7688-115">If your organization uses a Mobile Device Management (MDM) solution that is not officially supported, this does not mean you are unable to deploy or run Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="f7688-116">Microsoft Defender for Endpoint for Mac は、ベンダー固有の機能に依存しない。</span><span class="sxs-lookup"><span data-stu-id="f7688-116">Microsoft Defender for Endpoint for Mac does not depend on any vendor-specific features.</span></span> <span data-ttu-id="f7688-117">これは、次の機能をサポートする MDM ソリューションと一緒に使用できます。</span><span class="sxs-lookup"><span data-stu-id="f7688-117">It can be used with any MDM solution that supports the following features:</span></span>

- <span data-ttu-id="f7688-118">管理対象デバイスに macOS .pkg を展開します。</span><span class="sxs-lookup"><span data-stu-id="f7688-118">Deploy a macOS .pkg to managed devices.</span></span>
- <span data-ttu-id="f7688-119">管理対象デバイスに macOS システム構成プロファイルを展開します。</span><span class="sxs-lookup"><span data-stu-id="f7688-119">Deploy macOS system configuration profiles to managed devices.</span></span>
- <span data-ttu-id="f7688-120">管理デバイスで任意の管理者が構成したツール/スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="f7688-120">Run an arbitrary admin-configured tool/script on managed devices.</span></span>

<span data-ttu-id="f7688-121">最新の MDM ソリューションの多くは、これらの機能が含まれますが、呼び出し方が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f7688-121">Most modern MDM solutions include these features, however, they may call them differently.</span></span>

<span data-ttu-id="f7688-122">ただし、前のリストから最後の要件を満たさずに Defender を展開できます。</span><span class="sxs-lookup"><span data-stu-id="f7688-122">You can deploy Defender without the last requirement from the preceding list, however:</span></span>

- <span data-ttu-id="f7688-123">一元的な方法で状態を収集できない</span><span class="sxs-lookup"><span data-stu-id="f7688-123">You will not be able to collect status in a centralized way</span></span>
- <span data-ttu-id="f7688-124">Defender をアンインストールする場合は、管理者としてクライアント デバイスにローカルでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7688-124">If you decide to uninstall Defender, you will need to log on to the client device locally as an administrator</span></span>

## <a name="deployment"></a><span data-ttu-id="f7688-125">展開</span><span class="sxs-lookup"><span data-stu-id="f7688-125">Deployment</span></span>

<span data-ttu-id="f7688-126">ほとんどの MDM ソリューションでは、同様の用語を使用して macOS デバイスを管理するために同じモデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="f7688-126">Most MDM solutions use the same model for managing macOS devices, with similar terminology.</span></span> <span data-ttu-id="f7688-127">[JAMF ベースの展開をテンプレート](mac-install-with-jamf.md)として使用します。</span><span class="sxs-lookup"><span data-stu-id="f7688-127">Use [JAMF-based deployment](mac-install-with-jamf.md) as a template.</span></span>

### <a name="package"></a><span data-ttu-id="f7688-128">パッケージ</span><span class="sxs-lookup"><span data-stu-id="f7688-128">Package</span></span>

<span data-ttu-id="f7688-129">Microsoft Defender [](mac-install-with-jamf.md)Security Center からダウンロードしたインストール パッケージ (wdav.pkg) を使用して、必要なアプリケーション パッケージの展開[を構成します](mac-install-with-jamf.md)。</span><span class="sxs-lookup"><span data-stu-id="f7688-129">Configure deployment of a [required application package](mac-install-with-jamf.md), with the installation package (wdav.pkg) downloaded from [Microsoft Defender Security Center](mac-install-with-jamf.md).</span></span>

<span data-ttu-id="f7688-130">パッケージを企業に展開するには、MDM ソリューションに関連付けられている手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="f7688-130">In order to deploy the package to your enterprise, use the instructions associated with your MDM solution.</span></span>

### <a name="license-settings"></a><span data-ttu-id="f7688-131">ライセンス設定</span><span class="sxs-lookup"><span data-stu-id="f7688-131">License settings</span></span>

<span data-ttu-id="f7688-132">システム構成 [プロファイルを設定します](mac-install-with-jamf.md)。</span><span class="sxs-lookup"><span data-stu-id="f7688-132">Set up [a system configuration profile](mac-install-with-jamf.md).</span></span> <span data-ttu-id="f7688-133">Microsoft Defender for Endpoint for Mac は macOS の一部ではなされていないので、MDM ソリューションでは"カスタム設定プロファイル" と呼ばれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f7688-133">Your MDM solution may call it something like "Custom Settings Profile", as Microsoft Defender for Endpoint for Mac is not part of macOS.</span></span>

<span data-ttu-id="f7688-134">プロパティ リスト jamf/WindowsDefenderATPOnboarding.plist を使用します。これは [、Microsoft Defender](mac-install-with-jamf.md)セキュリティ センターからダウンロードしたオンボーディング パッケージから抽出できます。</span><span class="sxs-lookup"><span data-stu-id="f7688-134">Use the property list, jamf/WindowsDefenderATPOnboarding.plist, which can be extracted from an onboarding package downloaded from [Microsoft Defender Security Center](mac-install-with-jamf.md).</span></span>
<span data-ttu-id="f7688-135">システムが XML 形式の任意のプロパティ リストをサポートしている場合があります。</span><span class="sxs-lookup"><span data-stu-id="f7688-135">Your system may support an arbitrary property list in XML format.</span></span> <span data-ttu-id="f7688-136">その場合は、jamf/WindowsDefenderATPOnboarding.plist ファイルを as-is でアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="f7688-136">You can upload the jamf/WindowsDefenderATPOnboarding.plist file as-is in that case.</span></span>
<span data-ttu-id="f7688-137">または、最初にプロパティ リストを別の形式に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7688-137">Alternatively, it may require you to convert the property list to a different format first.</span></span>

<span data-ttu-id="f7688-138">通常、カスタム プロファイルには ID、名前、またはドメイン属性があります。</span><span class="sxs-lookup"><span data-stu-id="f7688-138">Typically, your custom profile has an ID, name, or domain attribute.</span></span> <span data-ttu-id="f7688-139">この値には、正確に "com.microsoft.wdav.atp" を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7688-139">You must use exactly "com.microsoft.wdav.atp" for this value.</span></span>
<span data-ttu-id="f7688-140">MDM はこれを使用して、設定ファイルをクライアント デバイスの **/Library/Managed Preferences/com.microsoft.wdav.atp.plist** に展開し、Defender はこのファイルを使用してオンボーディング情報を読み込む。</span><span class="sxs-lookup"><span data-stu-id="f7688-140">MDM uses it to deploy the settings file to **/Library/Managed Preferences/com.microsoft.wdav.atp.plist** on a client device, and Defender uses this file for loading the onboarding information.</span></span>

### <a name="kernel-extension-policy"></a><span data-ttu-id="f7688-141">カーネル拡張機能ポリシー</span><span class="sxs-lookup"><span data-stu-id="f7688-141">Kernel extension policy</span></span>

<span data-ttu-id="f7688-142">KEXT またはカーネル拡張ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="f7688-142">Set up a KEXT or kernel extension policy.</span></span> <span data-ttu-id="f7688-143">Microsoft が提供するカーネル拡張機能を許可するには、チーム識別子 **UBF8T346G9** を使用します。</span><span class="sxs-lookup"><span data-stu-id="f7688-143">Use team identifier **UBF8T346G9** to allow kernel extensions provided by Microsoft.</span></span>

### <a name="system-extension-policy"></a><span data-ttu-id="f7688-144">システム拡張ポリシー</span><span class="sxs-lookup"><span data-stu-id="f7688-144">System extension policy</span></span>

<span data-ttu-id="f7688-145">システム拡張ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="f7688-145">Set up a system extension policy.</span></span> <span data-ttu-id="f7688-146">チーム識別子 **UBF8T346G9** を使用し、次のバンドル識別子を承認します。</span><span class="sxs-lookup"><span data-stu-id="f7688-146">Use team identifier **UBF8T346G9** and approve the following bundle identifiers:</span></span>

- <span data-ttu-id="f7688-147">com.microsoft.wdav.epsext</span><span class="sxs-lookup"><span data-stu-id="f7688-147">com.microsoft.wdav.epsext</span></span>
- <span data-ttu-id="f7688-148">com.microsoft.wdav.netext</span><span class="sxs-lookup"><span data-stu-id="f7688-148">com.microsoft.wdav.netext</span></span>

### <a name="full-disk-access-policy"></a><span data-ttu-id="f7688-149">フル ディスク アクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="f7688-149">Full disk access policy</span></span>

<span data-ttu-id="f7688-150">次のコンポーネントにフル ディスク アクセスを付与します。</span><span class="sxs-lookup"><span data-stu-id="f7688-150">Grant Full Disk Access to the following components:</span></span>

- <span data-ttu-id="f7688-151">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f7688-151">Microsoft Defender for Endpoint</span></span>
    - <span data-ttu-id="f7688-152">識別子: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="f7688-152">Identifier: `com.microsoft.wdav`</span></span>
    - <span data-ttu-id="f7688-153">識別子の種類: バンドル ID</span><span class="sxs-lookup"><span data-stu-id="f7688-153">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="f7688-154">コード要件: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="f7688-154">Code Requirement: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

- <span data-ttu-id="f7688-155">Microsoft Defender for Endpoint Security Extension</span><span class="sxs-lookup"><span data-stu-id="f7688-155">Microsoft Defender for Endpoint Security Extension</span></span>
    - <span data-ttu-id="f7688-156">識別子: `com.microsoft.wdav.epsext`</span><span class="sxs-lookup"><span data-stu-id="f7688-156">Identifier: `com.microsoft.wdav.epsext`</span></span>
    - <span data-ttu-id="f7688-157">識別子の種類: バンドル ID</span><span class="sxs-lookup"><span data-stu-id="f7688-157">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="f7688-158">コード要件: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="f7688-158">Code Requirement: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

### <a name="network-extension-policy"></a><span data-ttu-id="f7688-159">ネットワーク拡張ポリシー</span><span class="sxs-lookup"><span data-stu-id="f7688-159">Network extension policy</span></span>

<span data-ttu-id="f7688-160">エンドポイント検出と応答機能の一環として、Microsoft Defender for Endpoint for Mac はソケット トラフィックを検査し、この情報を Microsoft Defender セキュリティ センター ポータルに報告します。</span><span class="sxs-lookup"><span data-stu-id="f7688-160">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint for Mac inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="f7688-161">次のポリシーでは、ネットワーク拡張機能でこの機能を実行できます。</span><span class="sxs-lookup"><span data-stu-id="f7688-161">The following policy allows the network extension to perform this functionality.</span></span>

- <span data-ttu-id="f7688-162">フィルターの種類: プラグイン</span><span class="sxs-lookup"><span data-stu-id="f7688-162">Filter type: Plugin</span></span>
- <span data-ttu-id="f7688-163">プラグイン バンドル識別子: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="f7688-163">Plugin bundle identifier: `com.microsoft.wdav`</span></span>
- <span data-ttu-id="f7688-164">フィルター データ プロバイダーのバンドル識別子: `com.microsoft.wdav.netext`</span><span class="sxs-lookup"><span data-stu-id="f7688-164">Filter data provider bundle identifier: `com.microsoft.wdav.netext`</span></span>
- <span data-ttu-id="f7688-165">フィルター データ プロバイダーの指定要件: `identifier "com.microsoft.wdav.tunnelext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="f7688-165">Filter data provider designated requirement: `identifier "com.microsoft.wdav.tunnelext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>
- <span data-ttu-id="f7688-166">フィルター ソケット: `true`</span><span class="sxs-lookup"><span data-stu-id="f7688-166">Filter sockets: `true`</span></span>

## <a name="check-installation-status"></a><span data-ttu-id="f7688-167">インストールの状態を確認する</span><span class="sxs-lookup"><span data-stu-id="f7688-167">Check installation status</span></span>

<span data-ttu-id="f7688-168">クライアント [デバイスで Microsoft Defender for Endpoint](mac-install-with-jamf.md) を実行し、オンボーディングの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="f7688-168">Run [Microsoft Defender for Endpoint](mac-install-with-jamf.md) on a client device to check the onboarding status.</span></span>