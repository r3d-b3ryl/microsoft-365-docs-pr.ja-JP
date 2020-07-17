---
title: 新しい Microsoft Edge
description: ''
keywords: ブラウザー、Microsoft Managed Desktop、Microsoft 365、service、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: f4bc5f85b21148c5a923ca1fc18879a193191c4b
ms.sourcegitcommit: 09a500a44d8723f8f2be87d9ad4ce7e453c5192b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2020
ms.locfileid: "45094788"
---
# <a name="new-microsoft-edge-app"></a><span data-ttu-id="7f706-103">新しい Microsoft Edge アプリ</span><span class="sxs-lookup"><span data-stu-id="7f706-103">New Microsoft Edge app</span></span>

<span data-ttu-id="7f706-104">新しい[Microsoft Edge ブラウザー](https://www.microsoft.com/edge)は、閲覧時に、プライバシー、生産性、および価値の高い世界クラスのパフォーマンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="7f706-104">The new [Microsoft Edge browser](https://www.microsoft.com/edge) provides world-class performance with more privacy, more productivity, and more value while you browse.</span></span> <span data-ttu-id="7f706-105">Microsoft マネージドデスクトップは、お客様の環境に新しいエッジブラウザーを展開するためのパブリックプレビューを提供しています。</span><span class="sxs-lookup"><span data-stu-id="7f706-105">Microsoft Managed Desktop is offering a public preview of deployment of the new Edge browser in your environment.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="7f706-106">初期展開</span><span class="sxs-lookup"><span data-stu-id="7f706-106">Initial deployment</span></span>

<span data-ttu-id="7f706-107">Microsoft マネージドデスクトップデバイスを新しい Microsoft Edge ブラウザーに移行するには、Microsoft マネージドデスクトップポータルを使用して、IT サポートチケットをファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="7f706-107">To migrate your Microsoft Managed Desktop devices to the new Microsoft Edge browser, file an IT Support Ticket through the Microsoft Managed Desktop Portal.</span></span> <span data-ttu-id="7f706-108">チケットをファイル化した後、24時間ごとに展開グループに展開すると、エッジ安定チャネルがテストグループに展開されます。</span><span class="sxs-lookup"><span data-stu-id="7f706-108">We will deploy the Edge Stable channel to the Test Group when you file the ticket, and then deploy it in each subsequent deployment group every 24 hours.</span></span> <span data-ttu-id="7f706-109">展開を一時停止するには、別のチケットをファイルに保存する操作を要求します。</span><span class="sxs-lookup"><span data-stu-id="7f706-109">To pause the deployment, file another ticket asking Operations to hold.</span></span>

## <a name="updates-to-microsoft-edge"></a><span data-ttu-id="7f706-110">Microsoft Edge への更新</span><span class="sxs-lookup"><span data-stu-id="7f706-110">Updates to Microsoft Edge</span></span>

<span data-ttu-id="7f706-111">Microsoft マネージドデスクトップは、6週間ごとに自動更新される、Microsoft Edge の安定した[チャネル](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel)を展開します。</span><span class="sxs-lookup"><span data-stu-id="7f706-111">Microsoft Managed Desktop deploys the [Stable channel](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) of Microsoft Edge which is auto-updated about every six weeks.</span></span> <span data-ttu-id="7f706-112">お客様に最適な環境を実現するために、安定したチャネルでの更新は、Microsoft Edge 製品グループによって[段階的](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout)にロールアウトされています。</span><span class="sxs-lookup"><span data-stu-id="7f706-112">Updates on the Stable channel are rolled out [progressively](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) by the Microsoft Edge product group in order to ensure the best experience for customers.</span></span> <span data-ttu-id="7f706-113">Microsoft Edge ベータチャネルは現在使用できません。</span><span class="sxs-lookup"><span data-stu-id="7f706-113">The Microsoft Edge Beta channel is not currently available.</span></span>

<span data-ttu-id="7f706-114">Microsoft Edge が正しく更新されるように、Microsoft Edge[更新ポリシー](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)を変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="7f706-114">To ensure that Microsoft Edge updates correctly, do not modify the Microsoft Edge [update policies](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies).</span></span>

## <a name="settings-managed-by-microsoft-managed-desktop"></a><span data-ttu-id="7f706-115">Microsoft マネージドデスクトップによって管理される設定</span><span class="sxs-lookup"><span data-stu-id="7f706-115">Settings managed by Microsoft Managed Desktop</span></span>

<span data-ttu-id="7f706-116">Microsoft マネージドデスクトップでは、ブラウザーをセキュリティで保護するために、Microsoft Edge の既定のポリシーセットが作成されています。</span><span class="sxs-lookup"><span data-stu-id="7f706-116">Microsoft Managed Desktop has created a default set of policies for Microsoft Edge to secure the browser.</span></span> <span data-ttu-id="7f706-117">既定のブラウザーの設定は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7f706-117">The default browser settings are as follows:</span></span>

### <a name="microsoft-edge-extensions"></a><span data-ttu-id="7f706-118">Microsoft Edge 拡張機能</span><span class="sxs-lookup"><span data-stu-id="7f706-118">Microsoft Edge extensions</span></span>

<span data-ttu-id="7f706-119">Microsoft マネージドデスクトップデバイス上の Microsoft Edge のセキュリティベースラインは、2つのポリシーを設定して、Chrome 拡張およびセキュリティで保護されたエンドユーザーをすべて無効にします。</span><span class="sxs-lookup"><span data-stu-id="7f706-119">The security baseline for Microsoft Edge on Microsoft Managed Desktop devices sets two policies to disable all Chrome extensions and secure end users.</span></span> <span data-ttu-id="7f706-120">環境で拡張機能を有効にして展開するには、「管理する設定」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f706-120">To enable and deploy extensions in your environment, see Settings you manage.</span></span> 

#### <a name="extension-installation-blocklist"></a><span data-ttu-id="7f706-121">拡張機能のインストール blocklist</span><span class="sxs-lookup"><span data-stu-id="7f706-121">Extension installation blocklist</span></span>
<span data-ttu-id="7f706-122">**既定値:** すべての</span><span class="sxs-lookup"><span data-stu-id="7f706-122">**Default value:** All</span></span>

<span data-ttu-id="7f706-123">Microsoft Managed Desktop は、このポリシーを設定して、管理されたエンドポイントに Chrome 拡張機能がインストールされないようにします。</span><span class="sxs-lookup"><span data-stu-id="7f706-123">Microsoft Managed Desktop sets this policy to prevent Chrome extensions from being installed on managed endpoints.</span></span> <span data-ttu-id="7f706-124">Chromium 拡張モデルには、データ損失防止、プライバシー、およびデバイスを侵害する可能性があるその他のリスクを含む、既知の risksassociated があります。</span><span class="sxs-lookup"><span data-stu-id="7f706-124">There are known risksassociated with the Chromium extension model including data loss protection, privacy, and other risks that can compromise devices.</span></span> 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a><span data-ttu-id="7f706-125">ユーザーレベルのネイティブメッセージングホストを許可する (管理者権限なしでインストールされる)</span><span class="sxs-lookup"><span data-stu-id="7f706-125">Allow user-level native messaging hosts (installed without admin permissions)</span></span>

<span data-ttu-id="7f706-126">**既定値:** 党</span><span class="sxs-lookup"><span data-stu-id="7f706-126">**Default value:** Disabled</span></span>

<span data-ttu-id="7f706-127">このポリシーを無効にすると、Microsoft Edge はシステムレベルでインストールされているネイティブメッセージングホストのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="7f706-127">By disabling this policy, Microsoft Edge will only use native messaging hosts installed on the system level.</span></span> <span data-ttu-id="7f706-128">ネイティブメッセージングホストは、Chrome 拡張機能の一部であり、ブラウザーはユーザーのエンドポイントの他の部分と対話し、さまざまなセキュリティ上の問題を作成できます。</span><span class="sxs-lookup"><span data-stu-id="7f706-128">Native messaging hosts are a part of Chrome extensions which allow for the browser to interact with other parts of user’s endpoint, creating a variety of security concerns.</span></span>  

### <a name="secure-sockets-layer-ssl"></a><span data-ttu-id="7f706-129">Secure Sockets Layer (SSL)</span><span class="sxs-lookup"><span data-stu-id="7f706-129">Secure Sockets Layer (SSL)</span></span>

#### <a name="minimum-ssl-version"></a><span data-ttu-id="7f706-130">最小 SSL バージョン</span><span class="sxs-lookup"><span data-stu-id="7f706-130">Minimum SSL version</span></span>

<span data-ttu-id="7f706-131">**既定値:** サポートされる最低限の TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="7f706-131">**Default value:** Minimum TLS 1.2 supported</span></span>

<span data-ttu-id="7f706-132">安全性の低い TLS 1.1 を使用する場合は、これを要求できます。</span><span class="sxs-lookup"><span data-stu-id="7f706-132">If you want to use the less secure TLS 1.1, you can request this.</span></span>

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a><span data-ttu-id="7f706-133">ユーザーが SSL の警告ページから先に進むことができるようにする</span><span class="sxs-lookup"><span data-stu-id="7f706-133">Allows users to proceed from the SSL warning page</span></span>

<span data-ttu-id="7f706-134">**既定値:** 党</span><span class="sxs-lookup"><span data-stu-id="7f706-134">**Default value:** Disabled</span></span>

<span data-ttu-id="7f706-135">SSL エラーが発生しているサイトにユーザーがアクセスできるようにするため、この設定を有効にすることはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="7f706-135">We don't recommend enabling this setting since it allows users to visit sites with SSL errors.</span></span>

### <a name="microsoft-defender-smart-screen"></a><span data-ttu-id="7f706-136">Microsoft Defender Smart 画面</span><span class="sxs-lookup"><span data-stu-id="7f706-136">Microsoft Defender Smart Screen</span></span>

#### <a name="configure-microsoft-defender-smartscreen"></a><span data-ttu-id="7f706-137">Microsoft Defender SmartScreen を構成する</span><span class="sxs-lookup"><span data-stu-id="7f706-137">Configure Microsoft Defender SmartScreen</span></span>

<span data-ttu-id="7f706-138">**既定値:** い</span><span class="sxs-lookup"><span data-stu-id="7f706-138">**Default value:** Enabled</span></span>

<span data-ttu-id="7f706-139">エンドユーザーを保護するために、既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="7f706-139">Enabled by default to help protect end users.</span></span>

#### <a name="microsoft-defender-smartscreen-prompts-for-sites"></a><span data-ttu-id="7f706-140">サイトの Microsoft Defender SmartScreen プロンプト</span><span class="sxs-lookup"><span data-stu-id="7f706-140">Microsoft Defender SmartScreen prompts for sites</span></span>

<span data-ttu-id="7f706-141">**既定値:** い</span><span class="sxs-lookup"><span data-stu-id="7f706-141">**Default value:** Enabled</span></span>

<span data-ttu-id="7f706-142">この設定を無効にすることをお勧めします。これにより、ユーザーは警告を無視し、潜在的な悪意のあるサイトに進むことができるようになります。</span><span class="sxs-lookup"><span data-stu-id="7f706-142">We do not recommend disabling this setting since that would allow users to ignore warnings and continue to potentially malicious sites.</span></span>

#### <a name="prevent-bypassing-of-microsoft-defender-smartscreen-warnings-about-downloads"></a><span data-ttu-id="7f706-143">ダウンロードに関する Microsoft Defender SmartScreen の警告をバイパスできないようにする</span><span class="sxs-lookup"><span data-stu-id="7f706-143">Prevent bypassing of Microsoft Defender SmartScreen warnings about downloads</span></span>

<span data-ttu-id="7f706-144">**既定値:** い</span><span class="sxs-lookup"><span data-stu-id="7f706-144">**Default value:** Enabled</span></span>

<span data-ttu-id="7f706-145">この設定を無効にして、ユーザーが警告を無視し、検証されていないダウンロードを完了できるようにすることをお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="7f706-145">We do not recommend disabling this setting since that would allow users to ignore warnings and complete unverified downloads.</span></span>

### <a name="adobe-flash"></a><span data-ttu-id="7f706-146">Adobe Flash</span><span class="sxs-lookup"><span data-stu-id="7f706-146">Adobe Flash</span></span>

#### <a name="default-adobe-flash-setting"></a><span data-ttu-id="7f706-147">既定の Adobe Flash 設定</span><span class="sxs-lookup"><span data-stu-id="7f706-147">Default Adobe Flash setting</span></span>

<span data-ttu-id="7f706-148">**既定値:** 党</span><span class="sxs-lookup"><span data-stu-id="7f706-148">**Default value:** Disabled</span></span>

<span data-ttu-id="7f706-149">関連するセキュリティリスクがあるため、Flash の使用はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="7f706-149">We don't recommend using Flash because of associated security risks.</span></span> <span data-ttu-id="7f706-150">フラッシュに依存するプロセスがまだある場合は、 **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** ポリシーを設定して、必要なサイトでフラッシュを有効にします。</span><span class="sxs-lookup"><span data-stu-id="7f706-150">If you still have processes which depend on Flash, set the **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** policy to enable Flash for sites which need it.</span></span> <span data-ttu-id="7f706-151">許可されているサイトのリストを保持してフラッシュを使用できない場合は、変更要求を開始して、 **[再生する]** の値を変更します。これにより、ユーザーはフラッシュを実行する必要がある場合に選択できるようになります。</span><span class="sxs-lookup"><span data-stu-id="7f706-151">If you can't maintain an allowed list of sites to use Flash, file a change request to change the value to **Click to Play**, which allows users choose when it's appropriate to run Flash.</span></span>

### <a name="password-manager"></a><span data-ttu-id="7f706-152">パスワードマネージャー</span><span class="sxs-lookup"><span data-stu-id="7f706-152">Password manager</span></span>

#### <a name="enable-saving-passwords-to-the-password-manager"></a><span data-ttu-id="7f706-153">パスワードをパスワードマネージャーに保存できるようにする</span><span class="sxs-lookup"><span data-stu-id="7f706-153">Enable saving passwords to the password manager</span></span>

<span data-ttu-id="7f706-154">**既定値:** 党</span><span class="sxs-lookup"><span data-stu-id="7f706-154">**Default value:** Disabled</span></span>

<span data-ttu-id="7f706-155">エンドユーザーが自分のデバイスにパスワードを保存することを許可することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="7f706-155">We do not recommend allowing end users to save passwords on their device.</span></span>

### <a name="other-settings"></a><span data-ttu-id="7f706-156">その他の設定</span><span class="sxs-lookup"><span data-stu-id="7f706-156">Other settings</span></span>

#### <a name="enable-site-isolation-for-every-site"></a><span data-ttu-id="7f706-157">サイトごとにサイト分離を有効にする</span><span class="sxs-lookup"><span data-stu-id="7f706-157">Enable site isolation for every site</span></span>

<span data-ttu-id="7f706-158">**既定値:** い</span><span class="sxs-lookup"><span data-stu-id="7f706-158">**Default value:** Enabled</span></span>

<span data-ttu-id="7f706-159">このポリシーが有効になっている場合、ユーザーは、各サイトが独自のプロセスで実行される既定の動作をオプトアウトできません。</span><span class="sxs-lookup"><span data-stu-id="7f706-159">When this policy is enabled, users can't opt out of the default behavior in which each site runs in its own process.</span></span>

#### <a name="supported-authentication-schemes"></a><span data-ttu-id="7f706-160">サポートされる認証スキーム</span><span class="sxs-lookup"><span data-stu-id="7f706-160">Supported authentication schemes</span></span>

<span data-ttu-id="7f706-161">**既定値:** NTLM、ネゴシエート</span><span class="sxs-lookup"><span data-stu-id="7f706-161">**Default value:** NTLM, Negotiate</span></span>

<span data-ttu-id="7f706-162">Microsoft マネージドデスクトップは、基本認証スキームまたはダイジェスト認証スキームをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="7f706-162">Microsoft Managed Desktop doesn't support Basic or Digest Authentication schemes.</span></span>

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a><span data-ttu-id="7f706-163">初回実行時に別のブラウザーのデータと設定を自動的にインポートする</span><span class="sxs-lookup"><span data-stu-id="7f706-163">Automatically import another browser's data and settings at first run</span></span>

<span data-ttu-id="7f706-164">**既定値:** サポートされているすべてのデータ型と設定を既定のブラウザーから自動的にインポートする</span><span class="sxs-lookup"><span data-stu-id="7f706-164">**Default value:** Automatically import all supported datatypes and settings from the default browser</span></span> 

<span data-ttu-id="7f706-165">このポリシーを適用すると、最初の実行環境で [インポート] セクションがスキップされ、ユーザーの操作が最小限になります。</span><span class="sxs-lookup"><span data-stu-id="7f706-165">With this policy applied, the First Run Experience will skip the import section, minimizing user interaction.</span></span> <span data-ttu-id="7f706-166">以前のバージョンの Microsoft Edge のブラウザーデータは、この設定に関係なく、常に最初の実行時に自動的に移行されます。</span><span class="sxs-lookup"><span data-stu-id="7f706-166">The browser data from older versions of Microsoft Edge will always be silently migrated at the first run, regardless of this setting.</span></span> 


## <a name="settings-you-manage"></a><span data-ttu-id="7f706-167">管理する設定</span><span class="sxs-lookup"><span data-stu-id="7f706-167">Settings you manage</span></span>

<span data-ttu-id="7f706-168">Microsoft Intune の管理用テンプレートプロファイルを使用していないマイクロ Sft エッジ設定を展開することができます。</span><span class="sxs-lookup"><span data-stu-id="7f706-168">You can deploy any Microsft Edge settings not previously described by using the Administrative Templates profile in Microsoft Intune.</span></span> <span data-ttu-id="7f706-169">詳細については、「microsoft [Edge ポリシー設定を Microsoft Intune で構成する](https://docs.microsoft.com/deployedge/configure-edge-with-intune)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f706-169">For details, see [Configure Microsoft Edge policy settings with Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune).</span></span> <span data-ttu-id="7f706-170">Intune の Microsoft Edge 管理用テンプレートに現在含まれていないポリシーを評価する場合は、Intune で Windows 10 デバイスのカスタム設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7f706-170">If you want to evaluate a policy that is not currently included in the Microsoft Edge Administrative Templates in Intune you can use custom settings for Windows 10 devices in Intune.</span></span>

### <a name="enabling-specific-chrome-extensions"></a><span data-ttu-id="7f706-171">特定の Chrome 拡張機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="7f706-171">Enabling specific Chrome extensions</span></span>

<span data-ttu-id="7f706-172">管理用テンプレートは、Microsoft Intune に特定の Chrome 拡張機能を展開するための設定を提供します。</span><span class="sxs-lookup"><span data-stu-id="7f706-172">The Administrative Template offers a setting to deploy particular Chrome extensions with Microsoft Intune.</span></span> <span data-ttu-id="7f706-173">**Microsoft Edge > 拡張機能を使用して、特定の拡張機能をインストール >** ことができます >、[コンピューターの構成] で見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="7f706-173">You can find it in **Computer Configuration > Microsoft Edge > Extensions > Allow Specific Extensions to be installed**.</span></span>

### <a name="install-extensions-silently"></a><span data-ttu-id="7f706-174">拡張機能をサイレントインストールする</span><span class="sxs-lookup"><span data-stu-id="7f706-174">Install extensions silently</span></span>

<span data-ttu-id="7f706-175">管理用テンプレートを使用して Microsoft Edge を設定し、ユーザーに通知せずに拡張機能をインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7f706-175">You can also use the Administrative Template to set Microsoft Edge to install extensions without alerting the user.</span></span> <span data-ttu-id="7f706-176">**Microsoft Edge > 拡張 > 機能を使用して、サイレントモードでインストールされる拡張機能を制御する >**、[コンピューターの構成の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="7f706-176">You can find it in **Computer Configuration > Microsoft Edge > Extensions > Control which extensions are installed silently**.</span></span>

### <a name="other-common-enterprise-policies"></a><span data-ttu-id="7f706-177">その他の一般的なエンタープライズポリシー</span><span class="sxs-lookup"><span data-stu-id="7f706-177">Other common enterprise policies</span></span>

<span data-ttu-id="7f706-178">Microsoft Edge では、非常に多くの追加ポリシーが提供されています。</span><span class="sxs-lookup"><span data-stu-id="7f706-178">Microsoft Edge offers a great many additional policies.</span></span> <span data-ttu-id="7f706-179">一般的なもののいくつかを次に示します。</span><span class="sxs-lookup"><span data-stu-id="7f706-179">These are some of the more common ones:</span></span>
 
- [<span data-ttu-id="7f706-180">エンタープライズサイトリストと IE モードのサイトを構成する</span><span class="sxs-lookup"><span data-stu-id="7f706-180">Configure Sites on the Enterprise Site List and IE Mode</span></span>](https://docs.microsoft.com/deployedge/edge-ie-mode-sitelist)
- [<span data-ttu-id="7f706-181">スタートアップ、ホームページ、および新しいタブページの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="7f706-181">Configure start-up, home page, and new tab page settings</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [<span data-ttu-id="7f706-182">サーフィンゲームの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="7f706-182">Configure Surf game setting</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowsurfgame)
- [<span data-ttu-id="7f706-183">プロキシサーバーの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="7f706-183">Configure proxy server settings</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proxy-server)

