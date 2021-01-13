---
title: 新しい Microsoft Edge
description: 新しいエッジ ブラウザーの展開方法と更新方法について説明します。
keywords: ブラウザー, Microsoft マネージド デスクトップ, Microsoft 365, サービス, ドキュメント
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 42ff665e8ba9c369e29eeeafd27affff04b40966
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841341"
---
# <a name="new-microsoft-edge-app"></a><span data-ttu-id="3683b-104">新しい Microsoft Edge アプリ</span><span class="sxs-lookup"><span data-stu-id="3683b-104">New Microsoft Edge app</span></span>

<span data-ttu-id="3683b-105">新しい [Microsoft Edge ブラウザーは](https://www.microsoft.com/edge) 、閲覧中のプライバシーの向上、生産性の向上、価値の向上により、世界クラスのパフォーマンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="3683b-105">The new [Microsoft Edge browser](https://www.microsoft.com/edge) provides world-class performance with more privacy, more productivity, and more value while you browse.</span></span> <span data-ttu-id="3683b-106">Microsoft マネージド デスクトップは、環境内での新しい Edge ブラウザーの展開のパブリック プレビューを提供しています。</span><span class="sxs-lookup"><span data-stu-id="3683b-106">Microsoft Managed Desktop is offering a public preview of deployment of the new Edge browser in your environment.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="3683b-107">初期展開</span><span class="sxs-lookup"><span data-stu-id="3683b-107">Initial deployment</span></span>

<span data-ttu-id="3683b-108">Microsoft マネージド デスクトップ デバイスを新しい Microsoft Edge ブラウザーに移行するには、Microsoft マネージド デスクトップ ポータルから IT サポート チケットを作成します。</span><span class="sxs-lookup"><span data-stu-id="3683b-108">To migrate your Microsoft Managed Desktop devices to the new Microsoft Edge browser, file an IT Support Ticket through the Microsoft Managed Desktop Portal.</span></span> <span data-ttu-id="3683b-109">チケットをファイルするときに Edge Stable チャネルをテスト グループに展開し、24 時間ごとに後続の各展開グループに展開します。</span><span class="sxs-lookup"><span data-stu-id="3683b-109">We will deploy the Edge Stable channel to the Test Group when you file the ticket, and then deploy it in each subsequent deployment group every 24 hours.</span></span> <span data-ttu-id="3683b-110">展開を一時停止するには、Operations に保留を求める別のチケットを作成します。</span><span class="sxs-lookup"><span data-stu-id="3683b-110">To pause the deployment, file another ticket asking Operations to hold.</span></span>

<span data-ttu-id="3683b-111">Beta [チャネルは、](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) 組織内の代表的な検証を要求された場合にも利用できます。</span><span class="sxs-lookup"><span data-stu-id="3683b-111">The [Beta Channel](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) is also available upon request for representative validation within your organization.</span></span> <span data-ttu-id="3683b-112">Microsoft マネージド デスクトップは、必要に応じてアプリケーションをテスト グループと最初のグループに展開し、これらのユーザー全員が Stable チャネルに加えてベータ チャネルを利用できます。</span><span class="sxs-lookup"><span data-stu-id="3683b-112">Microsoft Managed Desktop will deploy the application as required to the Test and First Groups so that all of those users have the Beta Channel in addition to the Stable Channel.</span></span> <span data-ttu-id="3683b-113">ベータ チャネルにアクセスする必要がある他のユーザーの場合は、そのユーザーを **モダン Workplace - Edge Beta Users** グループに追加し、ポータル サイトからインストールします。</span><span class="sxs-lookup"><span data-stu-id="3683b-113">For any other users who need access to the Beta Channel, add them to the **Modern Workplace - Edge Beta Users** group and have them install it from the Company Portal</span></span>

## <a name="updates-to-microsoft-edge"></a><span data-ttu-id="3683b-114">Microsoft Edge の更新</span><span class="sxs-lookup"><span data-stu-id="3683b-114">Updates to Microsoft Edge</span></span>

<span data-ttu-id="3683b-115">Microsoft マネージド デスクトップは、約 6 週間ごとに自動更新される Microsoft Edge の [Stable](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) チャネルを展開します。</span><span class="sxs-lookup"><span data-stu-id="3683b-115">Microsoft Managed Desktop deploys the [Stable channel](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) of Microsoft Edge, which is auto-updated about every six weeks.</span></span> <span data-ttu-id="3683b-116">Stable チャネルの更新プログラムは、[](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout)お客様に最適なエクスペリエンスを保証するために、Microsoft Edge 製品グループによって段階的に展開されます。</span><span class="sxs-lookup"><span data-stu-id="3683b-116">Updates on the Stable channel are rolled out [progressively](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) by the Microsoft Edge product group in order to ensure the best experience for customers.</span></span> 

<span data-ttu-id="3683b-117">Beta [チャネルは、](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) 組織内の代表的な検証のために Test グループと First グループの両方のデバイスに展開されます。</span><span class="sxs-lookup"><span data-stu-id="3683b-117">The [Beta Channel](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) is deployed to devices in both the Test and First groups for representative validation within the organization.</span></span> <span data-ttu-id="3683b-118">このチャネルは完全にサポートされ、約 6 週間ごとに新機能で自動更新されます。</span><span class="sxs-lookup"><span data-stu-id="3683b-118">This channel is fully supported and is auto-updated with new features approximately every six weeks.</span></span>

<span data-ttu-id="3683b-119">Microsoft Edge が正しく更新されるようにするには、Microsoft Edge の更新ポリシーを [変更しません](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)。</span><span class="sxs-lookup"><span data-stu-id="3683b-119">To ensure that Microsoft Edge updates correctly, do not modify the Microsoft Edge [update policies](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies).</span></span>



## <a name="settings-managed-by-microsoft-managed-desktop"></a><span data-ttu-id="3683b-120">Microsoft マネージド デスクトップで管理される設定</span><span class="sxs-lookup"><span data-stu-id="3683b-120">Settings managed by Microsoft Managed Desktop</span></span>

<span data-ttu-id="3683b-121">Microsoft マネージド デスクトップでは、ブラウザーをセキュリティで保護するための Microsoft Edge の既定のポリシー セットが作成されています。</span><span class="sxs-lookup"><span data-stu-id="3683b-121">Microsoft Managed Desktop has created a default set of policies for Microsoft Edge to secure the browser.</span></span> <span data-ttu-id="3683b-122">既定のブラウザー設定は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3683b-122">The default browser settings are as follows:</span></span>

### <a name="microsoft-edge-extensions"></a><span data-ttu-id="3683b-123">Microsoft Edge 拡張機能</span><span class="sxs-lookup"><span data-stu-id="3683b-123">Microsoft Edge extensions</span></span>

<span data-ttu-id="3683b-124">Microsoft マネージド デスクトップ デバイス上の Microsoft Edge のセキュリティ基本計画では、すべての Chrome 拡張機能を無効にし、ユーザーをセキュリティで保護する 2 つのポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="3683b-124">The security baseline for Microsoft Edge on Microsoft Managed Desktop devices sets two policies to disable all Chrome extensions and secure users.</span></span> <span data-ttu-id="3683b-125">環境で拡張機能を有効にして展開するには、「管理する設定」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3683b-125">To enable and deploy extensions in your environment, see Settings you manage.</span></span> 

#### <a name="extension-installation-blocklist"></a><span data-ttu-id="3683b-126">拡張機能のインストールのブロックリスト</span><span class="sxs-lookup"><span data-stu-id="3683b-126">Extension installation blocklist</span></span>
<span data-ttu-id="3683b-127">**既定値:** すべての</span><span class="sxs-lookup"><span data-stu-id="3683b-127">**Default value:** All</span></span>

<span data-ttu-id="3683b-128">Microsoft マネージド デスクトップでは、Chrome 拡張機能が管理エンドポイントにインストールされるのを防ぐために、このポリシーが設定されています。</span><span class="sxs-lookup"><span data-stu-id="3683b-128">Microsoft Managed Desktop sets this policy to prevent Chrome extensions from being installed on managed endpoints.</span></span> <span data-ttu-id="3683b-129">Chromium 拡張機能モデルには、データ損失防止、プライバシー、デバイスを侵害する可能性のあるその他のリスクなど、既知のリスクがあります。</span><span class="sxs-lookup"><span data-stu-id="3683b-129">There are known risks associated with the Chromium extension model including data loss protection, privacy, and other risks that can compromise devices.</span></span> 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a><span data-ttu-id="3683b-130">ユーザー レベルのネイティブ メッセージング ホストを許可する (管理者のアクセス許可なしでインストールされる)</span><span class="sxs-lookup"><span data-stu-id="3683b-130">Allow user-level native messaging hosts (installed without admin permissions)</span></span>

<span data-ttu-id="3683b-131">**既定値:** 無効</span><span class="sxs-lookup"><span data-stu-id="3683b-131">**Default value:** Disabled</span></span>

<span data-ttu-id="3683b-132">このポリシーを無効にすると、Microsoft Edge はシステム レベルにインストールされているネイティブ メッセージング ホストのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="3683b-132">By disabling this policy, Microsoft Edge will only use native messaging hosts installed on the system level.</span></span> <span data-ttu-id="3683b-133">ネイティブ メッセージング ホストは Chrome 拡張機能の一部で、ブラウザーがユーザーのエンドポイントの他の部分と対話し、さまざまなセキュリティ上の問題を引き起こす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3683b-133">Native messaging hosts are a part of Chrome extensions, which allow for the browser to interact with other parts of user’s endpoint, creating a variety of security concerns.</span></span>  

### <a name="secure-sockets-layer-tlsssl"></a><span data-ttu-id="3683b-134">Secure Sockets Layer (TLS/SSL)</span><span class="sxs-lookup"><span data-stu-id="3683b-134">Secure Sockets Layer (TLS/SSL)</span></span>

#### <a name="minimum-tls-version"></a><span data-ttu-id="3683b-135">TLS の最小バージョン</span><span class="sxs-lookup"><span data-stu-id="3683b-135">Minimum TLS version</span></span>

<span data-ttu-id="3683b-136">**既定値:** サポートされる TLS 1.2 以上</span><span class="sxs-lookup"><span data-stu-id="3683b-136">**Default value:** Minimum TLS 1.2 supported</span></span>

<span data-ttu-id="3683b-137">セキュリティが低い TLS 1.1 を使用する場合は、要求を送信できます。</span><span class="sxs-lookup"><span data-stu-id="3683b-137">If you want to use the less secure TLS 1.1, you can file a request to do so.</span></span>

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a><span data-ttu-id="3683b-138">ユーザーが SSL 警告ページから続行できます。</span><span class="sxs-lookup"><span data-stu-id="3683b-138">Allows users to proceed from the SSL warning page</span></span>

<span data-ttu-id="3683b-139">**既定値:** 無効</span><span class="sxs-lookup"><span data-stu-id="3683b-139">**Default value:** Disabled</span></span>

<span data-ttu-id="3683b-140">この設定を有効にすると、ユーザーは TSL エラーが発生したサイトにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3683b-140">We don't recommend enabling this setting since it allows users to visit sites with TSL errors.</span></span>

### <a name="microsoft-defender-smartscreen"></a><span data-ttu-id="3683b-141">Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="3683b-141">Microsoft Defender SmartScreen</span></span>

#### <a name="configure-windows-defender-smartscreen"></a><span data-ttu-id="3683b-142">SmartScreen Windows Defender構成する</span><span class="sxs-lookup"><span data-stu-id="3683b-142">Configure Windows Defender SmartScreen</span></span>

<span data-ttu-id="3683b-143">**既定値:** 有効</span><span class="sxs-lookup"><span data-stu-id="3683b-143">**Default value:** Enabled</span></span>

<span data-ttu-id="3683b-144">ユーザーを保護するために既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="3683b-144">Enabled by default to help protect users.</span></span>

#### <a name="windows-defender-smartscreen-prompts-for-sites"></a><span data-ttu-id="3683b-145">Windows Defender SmartScreen プロンプトを表示する</span><span class="sxs-lookup"><span data-stu-id="3683b-145">Windows Defender SmartScreen prompts for sites</span></span>

<span data-ttu-id="3683b-146">**既定値:** 有効</span><span class="sxs-lookup"><span data-stu-id="3683b-146">**Default value:** Enabled</span></span>

<span data-ttu-id="3683b-147">この設定を無効にすることで、ユーザーは警告を無視し、悪意のある可能性のあるサイトを引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="3683b-147">We do not recommend disabling this setting since that would allow users to ignore warnings and continue to potentially malicious sites.</span></span>

#### <a name="prevent-bypassing-of-windows-defender-smartscreen-warnings-about-downloads"></a><span data-ttu-id="3683b-148">ダウンロードに関する SmartScreen Windows Defenderのバイパスを回避する</span><span class="sxs-lookup"><span data-stu-id="3683b-148">Prevent bypassing of Windows Defender SmartScreen warnings about downloads</span></span>

<span data-ttu-id="3683b-149">**既定値:** 有効</span><span class="sxs-lookup"><span data-stu-id="3683b-149">**Default value:** Enabled</span></span>

<span data-ttu-id="3683b-150">この設定を無効にすることで、ユーザーは警告を無視して未確認のダウンロードを完了できます。</span><span class="sxs-lookup"><span data-stu-id="3683b-150">We do not recommend disabling this setting since that would allow users to ignore warnings and complete unverified downloads.</span></span>

### <a name="adobe-flash"></a><span data-ttu-id="3683b-151">Adobe Flash</span><span class="sxs-lookup"><span data-stu-id="3683b-151">Adobe Flash</span></span>

#### <a name="default-adobe-flash-setting"></a><span data-ttu-id="3683b-152">Adobe Flash の既定の設定</span><span class="sxs-lookup"><span data-stu-id="3683b-152">Default Adobe Flash setting</span></span>

<span data-ttu-id="3683b-153">**既定値:** 無効</span><span class="sxs-lookup"><span data-stu-id="3683b-153">**Default value:** Disabled</span></span>

<span data-ttu-id="3683b-154">関連するセキュリティ リスクのため、Flash の使用はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="3683b-154">We don't recommend using Flash because of associated security risks.</span></span> <span data-ttu-id="3683b-155">Flash に依存するプロセスがまだ存在する場合は **[、PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** ポリシーを設定して、必要なサイトで Flash を有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="3683b-155">If you still have processes that depend on Flash, set the **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** policy to enable Flash for sites that need it.</span></span> <span data-ttu-id="3683b-156">Flash を使用するサイトの許可リストを保持できない場合は、変更要求を送信して値を Click **to Play** に変更します。これにより、ユーザーは Flash を実行する適切なときに選択できます。</span><span class="sxs-lookup"><span data-stu-id="3683b-156">If you can't maintain an allowed list of sites to use Flash, file a change request to change the value to **Click to Play**, which allows users choose when it's appropriate to run Flash.</span></span>

### <a name="password-manager"></a><span data-ttu-id="3683b-157">パスワード マネージャー</span><span class="sxs-lookup"><span data-stu-id="3683b-157">Password manager</span></span>

#### <a name="enable-saving-passwords-to-the-password-manager"></a><span data-ttu-id="3683b-158">パスワード マネージャーへのパスワードの保存を有効にする</span><span class="sxs-lookup"><span data-stu-id="3683b-158">Enable saving passwords to the password manager</span></span>

<span data-ttu-id="3683b-159">**既定値:** 無効</span><span class="sxs-lookup"><span data-stu-id="3683b-159">**Default value:** Disabled</span></span>

<span data-ttu-id="3683b-160">ユーザーがデバイスにパスワードを保存することを許可はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="3683b-160">We do not recommend allowing users to save passwords on their device.</span></span>

### <a name="internet-explorer-mode-in-microsoft-edge"></a><span data-ttu-id="3683b-161">Microsoft Edge Internet Explorerモード</span><span class="sxs-lookup"><span data-stu-id="3683b-161">Internet Explorer Mode in Microsoft Edge</span></span>
<span data-ttu-id="3683b-162">Microsoft Edge で IE モードを利用すると、組織が必要とするすべてのサイトを 1 つのブラウザーで簡単に使用できます。</span><span class="sxs-lookup"><span data-stu-id="3683b-162">IE mode on Microsoft Edge makes it easy to use all of the sites your organization needs in a single browser.</span></span> <span data-ttu-id="3683b-163">Chromium レンダリング エンジンと互換性のあるサイトには統合 Chromium エンジンを使用し、IE の機能に依存していないサイトや IE 機能に依存しないサイトには Internet Explorer 11 (IE11) の Trident MSHTML エンジンを使用します。</span><span class="sxs-lookup"><span data-stu-id="3683b-163">It uses the integrated Chromium engine for sites that are compatible with the Chromium rendering engine and it uses the Trident MSHTML engine from Internet Explorer 11 (IE11) for sites that aren't or have dependencies on IE functionality.</span></span> <span data-ttu-id="3683b-164">[詳細](https://docs.microsoft.com/DeployEdge/edge-ie-mode)</span><span class="sxs-lookup"><span data-stu-id="3683b-164">[Learn more] (https://docs.microsoft.com/DeployEdge/edge-ie-mode)</span></span> 

<span data-ttu-id="3683b-165">Microsoft マネージド デスクトップでは、デバイスInternet Explorerモードが既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="3683b-165">Microsoft Managed Desktop enables Internet Explorer mode for your devices by default</span></span> 

#### <a name="internet-explorer-mode-integration"></a><span data-ttu-id="3683b-166">Internet Explorerモードの統合</span><span class="sxs-lookup"><span data-stu-id="3683b-166">Internet Explorer mode integration</span></span>
<span data-ttu-id="3683b-167">**既定値:** Internet Explorer モード</span><span class="sxs-lookup"><span data-stu-id="3683b-167">**Default Value:** Internet Explorer mode</span></span>

<span data-ttu-id="3683b-168">既定では、デバイスは Internet Explorer モードを使用する設定になっていますが、代わりにスタンドアロンの Internet Explorer 11 ウィンドウでサイトを開Internet Explorer設定できます。</span><span class="sxs-lookup"><span data-stu-id="3683b-168">By default, devices are set to use Internet Explorer mode, but you can set them to open sites in a standalone Internet Explorer 11 window instead.</span></span> <span data-ttu-id="3683b-169">この動作を変更するには、サポート要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="3683b-169">To change this behavior, file a support request.</span></span>

#### <a name="add-sites-to-the-enterprise-mode-site-list"></a><span data-ttu-id="3683b-170">エンタープライズ モード サイト一覧にサイトを追加する</span><span class="sxs-lookup"><span data-stu-id="3683b-170">Add sites to the Enterprise Mode Site list</span></span>
<span data-ttu-id="3683b-171">サイトをエンタープライズ サイト 一Internet Explorerモードで開く場合は、それらをエンタープライズ サイト一覧に [含める必要があります](https://docs.microsoft.com/DeployEdge/edge-ie-mode-sitelist)。</span><span class="sxs-lookup"><span data-stu-id="3683b-171">For sites to open in Internet Explorer mode you must include them on the [Enterprise Site list](https://docs.microsoft.com/DeployEdge/edge-ie-mode-sitelist).</span></span> <span data-ttu-id="3683b-172">エンタープライズ サイト一覧の保守と展開は、お客様の責任において行います。</span><span class="sxs-lookup"><span data-stu-id="3683b-172">Maintaining and deploying the Enterprise Site list is your responsibility.</span></span> <span data-ttu-id="3683b-173">詳細については、「エンタープライズ モード サイト [一覧の構成」ポリシーを使用した構成に関するページを参照してください。](https://docs.microsoft.com/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)</span><span class="sxs-lookup"><span data-stu-id="3683b-173">For details, see [Configure using the Configure Enterprise Mode Site List policy](https://docs.microsoft.com/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)</span></span>

### <a name="other-settings"></a><span data-ttu-id="3683b-174">その他の設定</span><span class="sxs-lookup"><span data-stu-id="3683b-174">Other settings</span></span>

#### <a name="enable-site-isolation-for-every-site"></a><span data-ttu-id="3683b-175">すべてのサイトでサイトの分離を有効にする</span><span class="sxs-lookup"><span data-stu-id="3683b-175">Enable site isolation for every site</span></span>

<span data-ttu-id="3683b-176">**既定値:** 有効</span><span class="sxs-lookup"><span data-stu-id="3683b-176">**Default value:** Enabled</span></span>

<span data-ttu-id="3683b-177">このポリシーを有効にすると、ユーザーは各サイトが独自のプロセスで実行される既定の動作を無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3683b-177">When this policy is enabled, users can't opt out of the default behavior in which each site runs in its own process.</span></span>

#### <a name="supported-authentication-schemes"></a><span data-ttu-id="3683b-178">サポートされる認証スキーム</span><span class="sxs-lookup"><span data-stu-id="3683b-178">Supported authentication schemes</span></span>

<span data-ttu-id="3683b-179">**既定値:** NTLM、ネゴシエート</span><span class="sxs-lookup"><span data-stu-id="3683b-179">**Default value:** NTLM, Negotiate</span></span>

<span data-ttu-id="3683b-180">Microsoft マネージド デスクトップでは、基本認証スキームまたはダイジェスト認証スキームはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3683b-180">Microsoft Managed Desktop doesn't support Basic or Digest Authentication schemes.</span></span>

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a><span data-ttu-id="3683b-181">最初の実行時に別のブラウザーのデータと設定を自動的にインポートする</span><span class="sxs-lookup"><span data-stu-id="3683b-181">Automatically import another browser's data and settings at first run</span></span>

<span data-ttu-id="3683b-182">**既定値:** サポートされているデータ型と設定を既定のブラウザーから自動的にインポートする</span><span class="sxs-lookup"><span data-stu-id="3683b-182">**Default value:** Automatically import all supported datatypes and settings from the default browser</span></span> 

<span data-ttu-id="3683b-183">このポリシーが適用されると、最初の実行エクスペリエンスはインポート セクションをスキップし、ユーザーの操作を最小限に抑える必要があります。</span><span class="sxs-lookup"><span data-stu-id="3683b-183">With this policy applied, the First Run Experience will skip the import section, minimizing user interaction.</span></span> <span data-ttu-id="3683b-184">以前のバージョンの Microsoft Edge のブラウザー データは、この設定に関係なく、最初の実行時に常に自動的に移行されます。</span><span class="sxs-lookup"><span data-stu-id="3683b-184">The browser data from older versions of Microsoft Edge will always be silently migrated at the first run, regardless of this setting.</span></span> 


## <a name="settings-you-manage"></a><span data-ttu-id="3683b-185">管理する設定</span><span class="sxs-lookup"><span data-stu-id="3683b-185">Settings you manage</span></span>

<span data-ttu-id="3683b-186">Microsoft Intune の管理用テンプレート プロファイルを使用して、前に説明した Microsoft Edge の設定を展開できます。</span><span class="sxs-lookup"><span data-stu-id="3683b-186">You can deploy any Microsoft Edge settings not previously described by using the Administrative Templates profile in Microsoft Intune.</span></span> <span data-ttu-id="3683b-187">詳細については [、「Microsoft Intune で Microsoft Edge ポリシー設定を構成する」を参照してください](https://docs.microsoft.com/deployedge/configure-edge-with-intune)。</span><span class="sxs-lookup"><span data-stu-id="3683b-187">For details, see [Configure Microsoft Edge policy settings with Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune).</span></span> <span data-ttu-id="3683b-188">Intune の Microsoft Edge 管理用テンプレートに現在含まれていないポリシーを評価する場合は、Intune で Windows 10 デバイスのカスタム設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3683b-188">If you want to evaluate a policy that is not currently included in the Microsoft Edge Administrative Templates in Intune, you can use custom settings for Windows 10 devices in Intune.</span></span>

### <a name="enabling-specific-chrome-extensions"></a><span data-ttu-id="3683b-189">特定の Chrome 拡張機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="3683b-189">Enabling specific Chrome extensions</span></span>

<span data-ttu-id="3683b-190">管理用テンプレートには、Microsoft Intune で特定の Chrome 拡張機能を展開する設定が用意されています。</span><span class="sxs-lookup"><span data-stu-id="3683b-190">The Administrative Template offers a setting to deploy particular Chrome extensions with Microsoft Intune.</span></span> <span data-ttu-id="3683b-191">この機能は、Microsoft Edge の [コンピューターの構成] **>[>拡張機能**] >特定の拡張機能のインストールを許可する] にあります。</span><span class="sxs-lookup"><span data-stu-id="3683b-191">You can find it in **Computer Configuration > Microsoft Edge > Extensions > Allow Specific Extensions to be installed**.</span></span>

### <a name="install-extensions-silently"></a><span data-ttu-id="3683b-192">拡張機能をサイレント インストールする</span><span class="sxs-lookup"><span data-stu-id="3683b-192">Install extensions silently</span></span>

<span data-ttu-id="3683b-193">管理用テンプレートを使用して、ユーザーに警告せずに拡張機能をインストールするように Microsoft Edge を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="3683b-193">You can also use the Administrative Template to set Microsoft Edge to install extensions without alerting the user.</span></span> <span data-ttu-id="3683b-194">[コンピューターの構成] > Microsoft Edge >拡張機能>サイレント インストールされる拡張機能 **を制御します**。</span><span class="sxs-lookup"><span data-stu-id="3683b-194">You can find it in **Computer Configuration > Microsoft Edge > Extensions > Control which extensions are installed silently**.</span></span>

### <a name="microsoft-edge-update-policies"></a><span data-ttu-id="3683b-195">Microsoft Edge 更新ポリシー</span><span class="sxs-lookup"><span data-stu-id="3683b-195">Microsoft Edge update policies</span></span>
<span data-ttu-id="3683b-196">Microsoft Edge が正しく更新されるようにするには、Microsoft Edge の更新ポリシーを [変更しません](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)。</span><span class="sxs-lookup"><span data-stu-id="3683b-196">To ensure that Microsoft Edge updates correctly, do not modify the Microsoft Edge [update policies](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies).</span></span>

### <a name="other-common-enterprise-policies"></a><span data-ttu-id="3683b-197">その他の一般的なエンタープライズ ポリシー</span><span class="sxs-lookup"><span data-stu-id="3683b-197">Other common enterprise policies</span></span>

<span data-ttu-id="3683b-198">Microsoft Edge には、他にも多くのポリシーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="3683b-198">Microsoft Edge offers a great many other policies.</span></span> <span data-ttu-id="3683b-199">以下に、より一般的な機能の一部を示します。</span><span class="sxs-lookup"><span data-stu-id="3683b-199">These are some of the more common ones:</span></span>
 
- [<span data-ttu-id="3683b-200">エンタープライズ サイト一覧と IE モードでサイトを構成する</span><span class="sxs-lookup"><span data-stu-id="3683b-200">Configure Sites on the Enterprise Site List and IE Mode</span></span>](https://docs.microsoft.com/deployedge/edge-ie-mode-sitelist)
- [<span data-ttu-id="3683b-201">起動、ホーム ページ、および新しいタブ ページの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="3683b-201">Configure start-up, home page, and new tab page settings</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [<span data-ttu-id="3683b-202">ゲームの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="3683b-202">Configure Surf game setting</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowsurfgame)
- [<span data-ttu-id="3683b-203">プロキシ サーバーの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="3683b-203">Configure proxy server settings</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proxy-server)

