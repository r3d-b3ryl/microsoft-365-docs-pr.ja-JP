---
title: Application Guard for Office 365 for admins
keywords: application guard, 保護, 分離, 分離コンテナー, ハードウェアの分離
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 最新のハードウェア ベースの分離を取得します。 悪用や悪意のあるリンクなど、現在および新たな攻撃が従業員の生産性や企業のセキュリティを妨害するのを防ぐ。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cf02f6776eb68537486b49c4fe45e8f88eeb38c6
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094881"
---
# <a name="application-guard-for-office-for-admins"></a><span data-ttu-id="98eb9-105">管理者向Office Application Guard</span><span class="sxs-lookup"><span data-stu-id="98eb9-105">Application Guard for Office for admins</span></span>

<span data-ttu-id="98eb9-106">**適用対象:** Word、Excel、PowerPoint for Microsoft 365、Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="98eb9-106">**Applies to:** Word, Excel, and PowerPoint for Microsoft 365, Windows 10 Enterprise</span></span>

<span data-ttu-id="98eb9-107">Microsoft Defender Application Guard for Office (Office 用 Application Guard) は、信頼されていないファイルが信頼できるリソースにアクセスし、新たな攻撃から企業を安全に保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="98eb9-107">Microsoft Defender Application Guard for Office (Application Guard for Office) helps prevent untrusted files from accessing trusted resources, keeping your enterprise safe from new and emerging attacks.</span></span> <span data-ttu-id="98eb9-108">この記事では、管理者が Application Guard for Office のプレビュー用にデバイスをセットアップする方法についてOffice。</span><span class="sxs-lookup"><span data-stu-id="98eb9-108">This article walks admins through setting up devices for a preview of Application Guard for Office.</span></span> <span data-ttu-id="98eb9-109">システム要件とインストール手順に関する情報を提供し、デバイスで Application Guard Officeを有効にします。</span><span class="sxs-lookup"><span data-stu-id="98eb9-109">It provides information about system requirements and installation steps to enable Application Guard for Office on a device.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="98eb9-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="98eb9-110">Prerequisites</span></span>

### <a name="minimum-hardware-requirements"></a><span data-ttu-id="98eb9-111">ハードウェアの最小要件</span><span class="sxs-lookup"><span data-stu-id="98eb9-111">Minimum hardware requirements</span></span>

* <span data-ttu-id="98eb9-112">**CPU**: 64 ビット、4 コア (物理または仮想)、仮想化拡張機能 (Intel VT-x または AMD-V)、Core i5 と同等以上の推奨</span><span class="sxs-lookup"><span data-stu-id="98eb9-112">**CPU**: 64-bit, 4 cores (physical or virtual), virtualization extensions   (Intel VT-x OR AMD-V), Core i5 equivalent or higher recommended</span></span>
* <span data-ttu-id="98eb9-113">**物理メモリ**: 8 GB RAM</span><span class="sxs-lookup"><span data-stu-id="98eb9-113">**Physical memory**: 8-GB RAM</span></span>
* <span data-ttu-id="98eb9-114">**ハード ディスク**: システム ドライブに 10 GB の空き領域 (SSD を推奨)</span><span class="sxs-lookup"><span data-stu-id="98eb9-114">**Hard disk**: 10 GB of free space on the system drive (SSD recommended)</span></span>

### <a name="minimum-software-requirements"></a><span data-ttu-id="98eb9-115">最小ソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="98eb9-115">Minimum software requirements</span></span>

* <span data-ttu-id="98eb9-116">**Windows 10**: Windows 10 Enterprise エディション、クライアント ビルド バージョン 2004 (20H1) ビルド 19041 以降</span><span class="sxs-lookup"><span data-stu-id="98eb9-116">**Windows 10**: Windows 10 Enterprise edition, Client Build version 2004 (20H1) build 19041 or later</span></span>
* <span data-ttu-id="98eb9-117">**Office**: Office Current Channel Build Version 2011 16.0.13530.10000 以降。</span><span class="sxs-lookup"><span data-stu-id="98eb9-117">**Office**: Office Current Channel Build version 2011 16.0.13530.10000 or later.</span></span> <span data-ttu-id="98eb9-118">32 ビットバージョンと 64 ビット バージョンの両方のOfficeサポートされています。</span><span class="sxs-lookup"><span data-stu-id="98eb9-118">Both 32-bit and 64-bit versions of Office are supported.</span></span>
* <span data-ttu-id="98eb9-119">**更新プログラム パッケージ**: Windows 10 の累積的な月次セキュリティ更新 [プログラム KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)</span><span class="sxs-lookup"><span data-stu-id="98eb9-119">**Update package**: Windows 10 cumulative monthly security update [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)</span></span>

<span data-ttu-id="98eb9-120">システム要件の詳細については、「Microsoft Defender Application Guard のシステム要件」 [を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard)。</span><span class="sxs-lookup"><span data-stu-id="98eb9-120">For detailed system requirements, refer to [System requirements for Microsoft Defender Application Guard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard).</span></span> <span data-ttu-id="98eb9-121">更新プログラム チャネルの詳細Office Microsoft [365](https://docs.microsoft.com/deployoffice/overview-update-channels)の更新プログラム チャネルの概要を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98eb9-121">To learn more about Office update channels, see [Overview of update channels for Microsoft 365](https://docs.microsoft.com/deployoffice/overview-update-channels).</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="98eb9-122">ライセンスの要件</span><span class="sxs-lookup"><span data-stu-id="98eb9-122">Licensing requirements</span></span>

* <span data-ttu-id="98eb9-123">Microsoft 365 E5 または Microsoft 365 E5 セキュリティ</span><span class="sxs-lookup"><span data-stu-id="98eb9-123">Microsoft 365 E5 or Microsoft 365 E5 Security</span></span>

## <a name="deploy-application-guard-for-office"></a><span data-ttu-id="98eb9-124">Application Guard を展開してOffice</span><span class="sxs-lookup"><span data-stu-id="98eb9-124">Deploy Application Guard for Office</span></span>

### <a name="enable-application-guard-for-office"></a><span data-ttu-id="98eb9-125">アプリケーションの Application Guard を有効Office</span><span class="sxs-lookup"><span data-stu-id="98eb9-125">Enable Application Guard for Office</span></span>

1. <span data-ttu-id="98eb9-126">Windows 10 の累積的な月次セキュリティ更新プログラム **KB4571756 をダウンロードしてインストールします**。</span><span class="sxs-lookup"><span data-stu-id="98eb9-126">Download and install **Windows 10 cumulative monthly security updates KB4571756**.</span></span>

2. <span data-ttu-id="98eb9-127">Windows の **機能で Microsoft Defender Application Guard** を選択し **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="98eb9-127">Select **Microsoft Defender Application Guard** under Windows Features and  select **OK**.</span></span> <span data-ttu-id="98eb9-128">Application Guard 機能を有効にすると、システムの再起動を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="98eb9-128">Enabling the Application Guard feature will prompt a system reboot.</span></span> <span data-ttu-id="98eb9-129">今すぐ再起動するか、手順 3. の後で再起動することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="98eb9-129">You can choose to reboot now or after step 3.</span></span>

   ![AG を示す [Windows の機能] ダイアログ ボックス](../../media/ag03-deploy.png)

   <span data-ttu-id="98eb9-131">この機能は、管理者として次の PowerShell コマンドを実行して有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="98eb9-131">The feature can also be enabled by running the following PowerShell command as administrator:</span></span>

   ```powershell
   Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard
   ```

3. <span data-ttu-id="98eb9-132">管理モード **で Microsoft Defender Application Guard を検索** します。グループ ポリシーは、[コンピューターの構成管理用テンプレート **] Windows コンポーネント Microsoft Defender Application Guard \\ \\ \\ で行います**。</span><span class="sxs-lookup"><span data-stu-id="98eb9-132">Search for **Microsoft Defender Application Guard in Managed Mode**, a group policy in **Computer Configuration\\Administrative Templates\\Windows Components\\Microsoft Defender Application Guard**.</span></span> <span data-ttu-id="98eb9-133">[オプション] の値を **2** または **3** に設定し **、[OK]** または [適用] を選択して、このポリシーを有効 **にします**。</span><span class="sxs-lookup"><span data-stu-id="98eb9-133">Turn on this policy by setting the value under Options as **2** or **3**, and then selecting **OK** or **Apply**.</span></span>

   ![管理モードで AG を有効にする](../../media/ag04-deploy.png)

   <span data-ttu-id="98eb9-135">代わりに、対応する CSP ポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="98eb9-135">Instead, you can set the corresponding CSP policy:</span></span>

   > <span data-ttu-id="98eb9-136">OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard**</span><span class="sxs-lookup"><span data-stu-id="98eb9-136">OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard**</span></span> <br> <span data-ttu-id="98eb9-137">データ型: **整数**</span><span class="sxs-lookup"><span data-stu-id="98eb9-137">Data type: **Integer**</span></span> <br> <span data-ttu-id="98eb9-138">値: **2**</span><span class="sxs-lookup"><span data-stu-id="98eb9-138">Value: **2**</span></span>

4. <span data-ttu-id="98eb9-139">システムを再起動します。</span><span class="sxs-lookup"><span data-stu-id="98eb9-139">Restart the system.</span></span>

### <a name="set-diagnostics--feedback-to-send-full-data"></a><span data-ttu-id="98eb9-140">完全なデータ&送信する診断データのフィードバックを設定する</span><span class="sxs-lookup"><span data-stu-id="98eb9-140">Set Diagnostics & feedback to send full data</span></span>

<span data-ttu-id="98eb9-141">この手順により、問題の特定と修正に必要なデータが Microsoft に到達することを保証します。</span><span class="sxs-lookup"><span data-stu-id="98eb9-141">This step ensures that the data necessary to identify and fix problems is reaching Microsoft.</span></span> <span data-ttu-id="98eb9-142">Windows デバイスで診断を有効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="98eb9-142">Follow these steps to enable diagnostics on your Windows device:</span></span>

1. <span data-ttu-id="98eb9-143">スタート **メニューから [** 設定] を開きます。</span><span class="sxs-lookup"><span data-stu-id="98eb9-143">Open **Settings** from the Start menu.</span></span>

   ![[スタート] メニュー](../../media/ag05-diagnostic.png)

2. <span data-ttu-id="98eb9-145">**[Windows の設定] で、[** プライバシー] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="98eb9-145">On **Windows Settings**, select **Privacy**.</span></span>

   ![[Windows の設定] メニュー](../../media/ag06-diagnostic.png)

3. <span data-ttu-id="98eb9-147">[プライバシー] で、フィードバック **に対して [診断&を選択し、** オプションの **診断データを選択します**。</span><span class="sxs-lookup"><span data-stu-id="98eb9-147">Under Privacy, select **Diagnostics & feedback** and select **Optional diagnostic data**.</span></span>

   ![[診断とフィードバック] メニュー](../../media/ag07a-diagnostic.png)

<span data-ttu-id="98eb9-149">Windows 診断設定の構成の詳細については、「組織内での Windows 診断データの [構成」を参照してください](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management)。</span><span class="sxs-lookup"><span data-stu-id="98eb9-149">For more on configuring Windows diagnostic settings, refer to [Configuring Windows diagnostic data in your organization](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management).</span></span>

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a><span data-ttu-id="98eb9-150">アプリケーションの Application Guard が有効Office機能を確認する</span><span class="sxs-lookup"><span data-stu-id="98eb9-150">Confirm that Application Guard for Office is enabled and working</span></span>

<span data-ttu-id="98eb9-151">Application Guard for Office が有効になっているか確認する前に、ポリシーが展開されているデバイスで Word、Excel、または PowerPoint を起動します。</span><span class="sxs-lookup"><span data-stu-id="98eb9-151">Before confirming that Application Guard for Office is enabled, launch Word, Excel, or PowerPoint on a device where the policies have been deployed.</span></span> <span data-ttu-id="98eb9-152">アクティブ化Office確認します。</span><span class="sxs-lookup"><span data-stu-id="98eb9-152">Make sure Office is activated.</span></span> <span data-ttu-id="98eb9-153">作業 ID を使用して、最初に製品のライセンス認証Office必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="98eb9-153">You may need to use your work identity to activate the Office product first.</span></span>

<span data-ttu-id="98eb9-154">Application Guard for Office有効になっているか確認するには、Word、Excel、または PowerPoint を起動し、信頼されていないドキュメントを開きます。</span><span class="sxs-lookup"><span data-stu-id="98eb9-154">To confirm that Application Guard for Office is enabled, launch Word, Excel, or PowerPoint, and then open an untrusted document.</span></span> <span data-ttu-id="98eb9-155">たとえば、インターネットからダウンロードされたドキュメントや、組織外のユーザーからのメールの添付ファイルを開く場合があります。</span><span class="sxs-lookup"><span data-stu-id="98eb9-155">For example, you can open a document that was downloaded from the internet or an email attachment from someone outside your organization.</span></span>

<span data-ttu-id="98eb9-156">信頼されていないファイルを初めて開いた場合、次のOfficeスプラッシュ画面が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="98eb9-156">When you first open an untrusted file, you may see an Office splash screen like the following example.</span></span> <span data-ttu-id="98eb9-157">Application Guard for Officeがアクティブ化され、ファイルが開いている間、しばらくの間表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="98eb9-157">It might be displayed for some time while Application Guard for Office is being activated and the file is being opened.</span></span> <span data-ttu-id="98eb9-158">信頼されていないファイルをそれ以降に開く方が速くなります。</span><span class="sxs-lookup"><span data-stu-id="98eb9-158">Subsequent openings of untrusted files should be faster.</span></span>

![Officeスプラッシュ画面](../../media/ag08-confirm.png)

<span data-ttu-id="98eb9-160">ファイルを開いた後、ファイルが Application Guard 内でファイルを開いたという視覚的なインジケーターが表示Office。</span><span class="sxs-lookup"><span data-stu-id="98eb9-160">Upon being opened, the file should display a few visual indicators that the file was opened inside Application Guard for Office:</span></span>

* <span data-ttu-id="98eb9-161">リボン内の吹き出し</span><span class="sxs-lookup"><span data-stu-id="98eb9-161">A callout in the ribbon</span></span>

  ![小さな App Guard のメモを示すドキュメント ファイル](../../media/ag09-confirm.png)

* <span data-ttu-id="98eb9-163">タスク バーに盾が表示されたアプリケーション アイコン</span><span class="sxs-lookup"><span data-stu-id="98eb9-163">The application icon with a shield in the taskbar</span></span>

  ![タスク バーのアイコン](../../media/ag12-limitations.png)

## <a name="configure-application-guard-for-office"></a><span data-ttu-id="98eb9-165">アプリケーション用に Application Guard をOffice</span><span class="sxs-lookup"><span data-stu-id="98eb9-165">Configure Application Guard for Office</span></span>

<span data-ttu-id="98eb9-166">Office次のポリシーをサポートし、アプリケーションの Application Guard の機能を構成Office。</span><span class="sxs-lookup"><span data-stu-id="98eb9-166">Office supports the following policies to enable you to configure the capabilities of Application Guard for Office.</span></span> <span data-ttu-id="98eb9-167">これらのポリシーは、グループ ポリシーまたはクラウド ポリシー サービスOffice構成できます。</span><span class="sxs-lookup"><span data-stu-id="98eb9-167">These policies can be configured through Group policies or through the Office cloud policy service.</span></span>

> [!NOTE]
> <span data-ttu-id="98eb9-168">これらのポリシーを構成すると、Application Guard で開いたファイルの一部の機能が無効Office。</span><span class="sxs-lookup"><span data-stu-id="98eb9-168">Configuring these policies can disable some functionalities for files opened in Application Guard for Office.</span></span>

|<span data-ttu-id="98eb9-169">ポリシー</span><span class="sxs-lookup"><span data-stu-id="98eb9-169">Policy</span></span>|<span data-ttu-id="98eb9-170">説明</span><span class="sxs-lookup"><span data-stu-id="98eb9-170">Description</span></span>|
|---|---|
|<span data-ttu-id="98eb9-171">アプリケーションに Application Guard を使用Office</span><span class="sxs-lookup"><span data-stu-id="98eb9-171">Don't use Application Guard for Office</span></span>|<span data-ttu-id="98eb9-172">このポリシーを有効にすると、Word、Excel、および PowerPoint は、Application Guard for Office の代わりに保護ビュー分離コンテナーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98eb9-172">Enabling this policy will force Word, Excel, and PowerPoint to use the Protected View isolation container instead of Application Guard for Office.</span></span> <span data-ttu-id="98eb9-173">このポリシーを使用すると、Microsoft Edge で Application Guard を有効Office問題がある場合に、アプリケーションの Application Guard を一時的に無効にできます。</span><span class="sxs-lookup"><span data-stu-id="98eb9-173">This policy can be used to temporarily disable Application Guard for Office when there are issues in leaving it enabled for Microsoft Edge.</span></span>|
|<span data-ttu-id="98eb9-174">コンテナーの事前作成Office Application Guard を構成する</span><span class="sxs-lookup"><span data-stu-id="98eb9-174">Configure Application Guard for Office container pre-creation</span></span>|<span data-ttu-id="98eb9-175">このポリシーは、信頼されていないファイルを分離する Office コンテナー用の Application Guard が、実行時のパフォーマンスを向上するために事前に作成されたかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="98eb9-175">This policy determines if the Application Guard for Office container, for isolating untrusted files, is pre-created for improved run-time performance.</span></span> <span data-ttu-id="98eb9-176">この設定を有効にした場合、コンテナーの事前作成を続行する日数を指定するか、Office 組み込みのヒューリスティックでコンテナーを事前に作成できます。</span><span class="sxs-lookup"><span data-stu-id="98eb9-176">If you enable this setting, you can specify the number of days to continue pre-creating a container or let the Office built-in heuristic pre-create the container.</span></span>
|<span data-ttu-id="98eb9-177">Application Guard で開いたドキュメントのコピー/貼りOfficeを許可Office</span><span class="sxs-lookup"><span data-stu-id="98eb9-177">Don't allow copy/paste for Office documents opened in Application Guard for Office</span></span>|<span data-ttu-id="98eb9-178">このポリシーを有効にすると、Application Guard for Office で開いたドキュメントから、外部で開いたドキュメントにコンテンツをコピーして貼り付けできません。</span><span class="sxs-lookup"><span data-stu-id="98eb9-178">Enabling this policy will prevent a user from copying and pasting content from a document opened in Application Guard for Office to a document opened outside of it.</span></span>|
|<span data-ttu-id="98eb9-179">Application Guard でハードウェア アクセラレータを無効にしてOffice</span><span class="sxs-lookup"><span data-stu-id="98eb9-179">Disable hardware acceleration in Application Guard for Office</span></span>|<span data-ttu-id="98eb9-180">このポリシーは、Application Guard for Officeグラフィックスのレンダリングにハードウェア アクセラレータを使用するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="98eb9-180">This policy controls whether Application Guard for Office uses hardware acceleration to render graphics.</span></span> <span data-ttu-id="98eb9-181">この設定を有効にした場合、Office 用 Application Guard はソフトウェア ベース (CPU) レンダリングを使用し、サード パーティ製のグラフィックス ドライバーを読み込み、接続されているグラフィックス ハードウェアを操作しません。</span><span class="sxs-lookup"><span data-stu-id="98eb9-181">If you enable this setting, Application Guard for Office uses software-based (CPU) rendering and won't load any third-party graphics drivers or interact with any connected graphics hardware.</span></span>
|<span data-ttu-id="98eb9-182">Application Guard でサポートされていないファイルの種類の保護を無効Office</span><span class="sxs-lookup"><span data-stu-id="98eb9-182">Disable unsupported file types protection in Application Guard for Office</span></span>|<span data-ttu-id="98eb9-183">このポリシーは、Application Guard for Office がサポートされていないファイルの種類を開くのをブロックするか、または保護されたビューへのリダイレクトを有効にするかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="98eb9-183">This policy controls whether Application Guard for Office will block unsupported file types from being opened or if it will enable the redirection to Protected View.</span></span>
|<span data-ttu-id="98eb9-184">Application Guard で開いたドキュメントのカメラとマイクへのアクセスをオフOffice</span><span class="sxs-lookup"><span data-stu-id="98eb9-184">Turn off camera and microphone access for documents opened in Application Guard for Office</span></span>|<span data-ttu-id="98eb9-185">このポリシーを有効にすると、Officeの Application Guard 内のカメラとマイクへのアクセスがOffice。</span><span class="sxs-lookup"><span data-stu-id="98eb9-185">Enabling this policy will remove Office access to the camera and microphone inside Application Guard for Office.</span></span>|
|<span data-ttu-id="98eb9-186">Application Guard で開いているドキュメントからの印刷を制限Office</span><span class="sxs-lookup"><span data-stu-id="98eb9-186">Restrict printing from documents opened in Application Guard for Office</span></span>|<span data-ttu-id="98eb9-187">このポリシーを有効にすると、Application Guard で開いたファイルからユーザーが印刷できるプリンターがOffice。</span><span class="sxs-lookup"><span data-stu-id="98eb9-187">Enabling this policy will limit the printers that a user can print to from a file opened in Application Guard for Office.</span></span> <span data-ttu-id="98eb9-188">たとえば、このポリシーを使用して、ユーザーが PDF にのみ印刷できるよう制限できます。</span><span class="sxs-lookup"><span data-stu-id="98eb9-188">For example, you can use this policy to restrict users to only print to PDF.</span></span>|
|<span data-ttu-id="98eb9-189">ユーザーが Application Guard を削除してファイルを保護Office防ぐ</span><span class="sxs-lookup"><span data-stu-id="98eb9-189">Prevent users from removing Application Guard for Office protection on files</span></span>|<span data-ttu-id="98eb9-190">このポリシーを有効にすると、(Office アプリケーション エクスペリエンス内で) Office 保護のために Application Guard を無効にしたり、Application Guard for Office の外部でファイルを開くオプションが削除されます。</span><span class="sxs-lookup"><span data-stu-id="98eb9-190">Enabling this policy will remove the option (within the Office application experience) to disable Application Guard for Office protection or to open a file outside Application Guard for Office.</span></span> <p> <span data-ttu-id="98eb9-191">**注:** このポリシーは、ファイルから手動で削除するか、ドキュメントを信頼できる場所に移動することでバイパスできます。</span><span class="sxs-lookup"><span data-stu-id="98eb9-191">**Note:** Users can still bypass this policy by manually removing the mark-of-the-web property from the file or by moving a document to a Trusted location.</span></span>|
|

> [!NOTE]
> <span data-ttu-id="98eb9-192">次のポリシーを有効にするには、ユーザーがサインアウトして Windows に再びサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="98eb9-192">The following policies will require the user to sign out and sign in again to Windows to take effect:</span></span>
>
> * <span data-ttu-id="98eb9-193">Application Guard で開いたドキュメントのコピー/貼り付けを無効にして、Office</span><span class="sxs-lookup"><span data-stu-id="98eb9-193">Disable copy/paste for documents opened in Application Guard for Office</span></span>
> * <span data-ttu-id="98eb9-194">Application Guard で開いているドキュメントの印刷を制限Office</span><span class="sxs-lookup"><span data-stu-id="98eb9-194">Restrict printing for documents opened in Application Guard for Office</span></span>
> * <span data-ttu-id="98eb9-195">Application Guard で開いたドキュメントへのカメラとマイクのアクセスをオフOffice</span><span class="sxs-lookup"><span data-stu-id="98eb9-195">Turn off camera and mic access to documents opened in Application Guard for Office</span></span>

## <a name="submit-feedback"></a><span data-ttu-id="98eb9-196">フィードバックの送信</span><span class="sxs-lookup"><span data-stu-id="98eb9-196">Submit feedback</span></span>

### <a name="submit-feedback-via-feedback-hub"></a><span data-ttu-id="98eb9-197">フィードバック Hub 経由でフィードバックを送信する</span><span class="sxs-lookup"><span data-stu-id="98eb9-197">Submit feedback via Feedback Hub</span></span>

<span data-ttu-id="98eb9-198">Application Guard for Office を起動するときに問題が発生した場合は、フィードバック Hub からフィードバックを送信してください。</span><span class="sxs-lookup"><span data-stu-id="98eb9-198">If you encounter any issues when launching Application Guard for Office, you're encouraged to submit your feedback via Feedback Hub:</span></span>

1. <span data-ttu-id="98eb9-199">フィードバック Hub **アプリを開き** 、サインインします。</span><span class="sxs-lookup"><span data-stu-id="98eb9-199">Open the **Feedback Hub app** and sign in.</span></span>

2. <span data-ttu-id="98eb9-200">Application Guard の起動中にエラー ダイアログが表示された場合は、エラー ダイアログで **[Microsoft** に報告] を選択して、新しいフィードバックの送信を開始します。</span><span class="sxs-lookup"><span data-stu-id="98eb9-200">If you get an error dialog while launching Application Guard, select **Report to Microsoft** in the error dialog to start a new feedback submission.</span></span> <span data-ttu-id="98eb9-201">それ以外の場合は、Application Guard の適切なカテゴリを選択するために移動し、右側にある [新しいフィードバックの追加 <https://aka.ms/mdagoffice-fb> ] を **+ &nbsp;** 選択します。</span><span class="sxs-lookup"><span data-stu-id="98eb9-201">Otherwise, navigate to <https://aka.ms/mdagoffice-fb> to select the correct category for Application Guard, then select **+&nbsp;Add new feedback** near the top right.</span></span>

3. <span data-ttu-id="98eb9-202">[フィードバックの要約]ボックスに概要を入力します (まだ入力されていない場合)。</span><span class="sxs-lookup"><span data-stu-id="98eb9-202">Enter a summary in the **Summarize your feedback** box if it isn't already filled in for you.</span></span>

4. <span data-ttu-id="98eb9-203">発生した問題の詳細な説明と実行した手順を [詳細] ボックスに入力し、[次へ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="98eb9-203">Enter a detailed description of the issue that you experienced and what steps you took in the **Explain in more detail** box, then select **Next**.</span></span>

5. <span data-ttu-id="98eb9-204">[問題] の横にあるバブルを **選択します**。</span><span class="sxs-lookup"><span data-stu-id="98eb9-204">Select the bubble next to **Problem**.</span></span> <span data-ttu-id="98eb9-205">選択したカテゴリがセキュリティとプライバシーに関する Microsoft Defender Application Guard Officeし、[ **\> 次へ**] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="98eb9-205">Make sure the category selected is **Security and Privacy \> Microsoft Defender Application Guard – Office**, then select **Next**.</span></span>

6. <span data-ttu-id="98eb9-206">[新 **しいフィードバック] を選択し**、[次へ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="98eb9-206">Select **New feedback**, then **Next**.</span></span>

7. <span data-ttu-id="98eb9-207">問題に関するトレースを収集します。</span><span class="sxs-lookup"><span data-stu-id="98eb9-207">Collect traces about the issue:</span></span>

   1. <span data-ttu-id="98eb9-208">[問題 **の再作成] タイルを展開** します。</span><span class="sxs-lookup"><span data-stu-id="98eb9-208">Expand the **Recreate my problem** tile.</span></span>

   2. <span data-ttu-id="98eb9-209">Application Guard の実行中に問題が発生した場合は、Application Guard インスタンスを開きます。</span><span class="sxs-lookup"><span data-stu-id="98eb9-209">If the issue you're experiencing occurs while Application Guard is running, open an Application Guard instance.</span></span> <span data-ttu-id="98eb9-210">インスタンスを開く場合、Application Guard コンテナー内から追加のトレースを収集できます。</span><span class="sxs-lookup"><span data-stu-id="98eb9-210">Opening an instance allows additional traces to be collected from within the Application Guard container.</span></span>

   3. <span data-ttu-id="98eb9-211">[Start **recording] (** レコーディングの開始) を選び、タイルの回転が止まるのを待ち、[記録の停止] と *言います*。</span><span class="sxs-lookup"><span data-stu-id="98eb9-211">Select **Start recording**, and wait for the tile to stop spinning and say *Stop recording*.</span></span>

   4. <span data-ttu-id="98eb9-212">Application Guard の問題を完全に再現します。</span><span class="sxs-lookup"><span data-stu-id="98eb9-212">Fully reproduce the issue with Application Guard.</span></span> <span data-ttu-id="98eb9-213">再現には、Application Guard インスタンスを起動しようとして失敗するまで待機したり、実行中の Application Guard インスタンスで問題を再現したりすることがあります。</span><span class="sxs-lookup"><span data-stu-id="98eb9-213">Reproduction might include attempting to launch an Application Guard instance and waiting until it fails, or reproducing an issue in a running Application Guard instance.</span></span>

   5. <span data-ttu-id="98eb9-214">[記録の **停止] タイルを選択** します。</span><span class="sxs-lookup"><span data-stu-id="98eb9-214">Select the **Stop recording** tile.</span></span>

   6. <span data-ttu-id="98eb9-215">実行中の Application Guard インスタンスは、申請後数分間でも開いた状態にしておき、コンテナー診断も収集できます。</span><span class="sxs-lookup"><span data-stu-id="98eb9-215">Keep any running Application Guard instance(s) open, even for a few minutes after submission, so that container diagnostics can also be collected.</span></span>

8. <span data-ttu-id="98eb9-216">問題に関連するスクリーンショットまたはファイルを添付します。</span><span class="sxs-lookup"><span data-stu-id="98eb9-216">Attach any relevant screenshots or files related to the problem.</span></span>

9. <span data-ttu-id="98eb9-217">**[送信]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="98eb9-217">Select **Submit**.</span></span>

### <a name="submit-feedback-via-office-customer-voice"></a><span data-ttu-id="98eb9-218">カスタマー ボイスを使用してOfficeを送信する</span><span class="sxs-lookup"><span data-stu-id="98eb9-218">Submit feedback via Office Customer Voice</span></span>

<span data-ttu-id="98eb9-219">また、Application Guard でドキュメントを開Office問題が発生した場合は、Officeからフィードバックを送信できます。</span><span class="sxs-lookup"><span data-stu-id="98eb9-219">You may also submit feedback from within Office if the issue happens when Office documents are opened in Application Guard.</span></span> <span data-ttu-id="98eb9-220">フィードバックの提出 [についてはOffice Insider ハンド](https://insider.office.com/handbook) ブックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="98eb9-220">Refer to the [Office Insider Handbook](https://insider.office.com/handbook) for submitting feedback.</span></span>

## <a name="integration-with-microsoft-defender-for-endpoint-and-microsoft-defender-for-office-365"></a><span data-ttu-id="98eb9-221">Microsoft Defender for Endpoint および Microsoft Defender for Office 365 との統合</span><span class="sxs-lookup"><span data-stu-id="98eb9-221">Integration with Microsoft Defender for Endpoint and Microsoft Defender for Office 365</span></span>

<span data-ttu-id="98eb9-222">Application Guard for Office Microsoft Defender for Endpoint と統合され、分離された環境で発生する悪意のあるアクティビティの監視と警告を提供します。</span><span class="sxs-lookup"><span data-stu-id="98eb9-222">Application Guard for Office is integrated with Microsoft Defender for Endpoint to provide monitoring and alerting on malicious activity that happens in the isolated environment.</span></span>

<span data-ttu-id="98eb9-223">Microsoft Defender for Endpoint は、エンタープライズ ネットワークが高度な脅威を防止、検出、調査、および対応するために設計されたセキュリティ プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="98eb9-223">Microsoft Defender for Endpoint is a security platform designed to help enterprise networks prevent, detect, investigate, and respond to advanced threats.</span></span> <span data-ttu-id="98eb9-224">このプラットフォームについて詳しくは [、「Microsoft Defender for Endpoint」をご覧ください](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp)。</span><span class="sxs-lookup"><span data-stu-id="98eb9-224">For more details about this platform, see [Microsoft Defender for Endpoint](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp).</span></span> <span data-ttu-id="98eb9-225">このプラットフォームへのデバイスのオンボードについて詳しくは、「エンドポイント向け Microsoft Defender サービスへのデバイスのオンボード」 [をご覧ください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure)。</span><span class="sxs-lookup"><span data-stu-id="98eb9-225">To learn more about onboarding devices to this platform, see [Onboard devices to the Microsoft Defender for Endpoint service](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure).</span></span>

<span data-ttu-id="98eb9-226">また、Office 365 用に Microsoft Defender をエンドポイント用の Defender と組み合Office構成できます。</span><span class="sxs-lookup"><span data-stu-id="98eb9-226">You can also configure Microsoft Defender for Office 365 to work with Defender for Endpoint.</span></span> <span data-ttu-id="98eb9-227">詳しくは、「Microsoft Defender for Endpoint と [Office 365](integrate-office-365-ti-with-wdatp.md)の Defender の統合」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="98eb9-227">For more info, refer to [Integrate Defender for Office 365 with Microsoft Defender for Endpoint](integrate-office-365-ti-with-wdatp.md).</span></span>

## <a name="limitations-and-considerations"></a><span data-ttu-id="98eb9-228">制限事項と考慮事項</span><span class="sxs-lookup"><span data-stu-id="98eb9-228">Limitations and considerations</span></span>

* <span data-ttu-id="98eb9-229">Office 用 Application Guard は、信頼できる企業リソース、イントラネット、ユーザーの ID、およびコンピューター上の任意のファイルにアクセスできない、信頼されていないドキュメントを分離する制限付きモードです。</span><span class="sxs-lookup"><span data-stu-id="98eb9-229">Application Guard for Office is a restricted mode that isolates untrusted documents so that they can't access trusted corporate resources, an intranet, the user's identity, and arbitrary files on the computer.</span></span> <span data-ttu-id="98eb9-230">その結果、ユーザーがこのようなアクセスに依存する機能 (ディスク上のローカル ファイルから画像を挿入するなど) にアクセスしようとすると、アクセスが失敗し、次の例のようなプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="98eb9-230">As a result, if a user tries to access a feature that has a dependency on such access—for example, inserting a picture from a local file on disk—the access will fail and produce a prompt like the following example.</span></span> <span data-ttu-id="98eb9-231">信頼されていないドキュメントが信頼できるリソースにアクセスするには、ユーザーがドキュメントから Application Guard 保護を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98eb9-231">To enable an untrusted document to access trusted resources, users must remove Application Guard protection from the document.</span></span>

  ![[安全に保つために、この機能は使用できません] というダイアログ ボックス](../../media/ag10-limitations.png)

  > [!NOTE]
  > <span data-ttu-id="98eb9-233">ファイルとそのソース、またはファイルの送信元を信頼している場合にのみ、保護を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98eb9-233">Advise users to only remove protection if they trust the file and its source or where it came from.</span></span>

* <span data-ttu-id="98eb9-234">Application Guard では、マクロやコントロールActiveXドキュメント内のアクティブなコンテンツが無効Office。</span><span class="sxs-lookup"><span data-stu-id="98eb9-234">Active content in documents like macros and ActiveX controls are disabled in Application Guard for Office.</span></span> <span data-ttu-id="98eb9-235">アクティブなコンテンツを有効にするには、Application Guard 保護を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98eb9-235">Users need to remove Application Guard protection to enable active content.</span></span>

* <span data-ttu-id="98eb9-236">ネットワーク共有からの信頼できないファイル、または別の組織の OneDrive、OneDrive for Business、または SharePoint Online から共有されたファイルは、Application Guard で読み取り専用として開きます。</span><span class="sxs-lookup"><span data-stu-id="98eb9-236">Untrusted files from network shares or files shared from OneDrive, OneDrive for Business, or SharePoint Online from a different organization open as read-only in Application Guard.</span></span> <span data-ttu-id="98eb9-237">ユーザーは、そのようなファイルのローカル コピーを保存してコンテナー内で作業を続行したり、元のファイルを直接操作する保護を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="98eb9-237">Users can save a local copy of such files to continue working in the container or remove protection to directly work with the original file.</span></span>

* <span data-ttu-id="98eb9-238">Information Rights Management (IRM) によって保護されているファイルは、既定でブロックされます。</span><span class="sxs-lookup"><span data-stu-id="98eb9-238">Files that are protected by Information Rights Management (IRM) are blocked by default.</span></span> <span data-ttu-id="98eb9-239">このようなファイルを保護ビューで開く場合、管理者は、組織でサポートされていないファイルの種類のポリシー設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98eb9-239">If users want to open such files in Protected View, an administrator must configure policy settings for unsupported file types for the organization.</span></span>

* <span data-ttu-id="98eb9-240">Office の Application Guard で Office アプリケーションに対するカスタマイズは、ユーザーがサインアウトして再びサインインした後、またはデバイスの再起動後に保持されません。</span><span class="sxs-lookup"><span data-stu-id="98eb9-240">Any customizations to Office applications in Application Guard for Office won't persist after a user signs out and signs in again or after the device restarts.</span></span>

* <span data-ttu-id="98eb9-241">UIA フレームワークを使うアクセシビリティ ツールだけが、アプリ用 Application Guard で開いたファイルにアクセシビリティ対応のエクスペリエンスOffice。</span><span class="sxs-lookup"><span data-stu-id="98eb9-241">Only Accessibility tools that use the UIA framework can provide an accessible experience for files opened in Application Guard for Office.</span></span>

* <span data-ttu-id="98eb9-242">インストール後に Application Guard を初めて起動するには、ネットワーク接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="98eb9-242">Network connectivity is required for the first launch of Application Guard after installation.</span></span> <span data-ttu-id="98eb9-243">Application Guard がライセンスを検証するには、接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="98eb9-243">Connectivity is required for Application Guard to validate the license.</span></span>

* <span data-ttu-id="98eb9-244">ドキュメントの情報セクションでは、[ *最終* 変更者] プロパティにユーザーとして **WDAGUtilityAccount** が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="98eb9-244">In the document's info section, the *Last Modified By* property may display **WDAGUtilityAccount** as the user.</span></span> <span data-ttu-id="98eb9-245">WDAGUtilityAccount は、Application Guard で構成された匿名ユーザーです。</span><span class="sxs-lookup"><span data-stu-id="98eb9-245">WDAGUtilityAccount is the anonymous user configured in Application Guard.</span></span> <span data-ttu-id="98eb9-246">デスクトップ ユーザーの ID は、Application Guard コンテナー内では共有されます。</span><span class="sxs-lookup"><span data-stu-id="98eb9-246">The desktop user's identity isn't shared inside the Application Guard container.</span></span>

## <a name="performance-optimizations-for-application-guard-for-office"></a><span data-ttu-id="98eb9-247">Application Guard for Office のパフォーマンスの最適化</span><span class="sxs-lookup"><span data-stu-id="98eb9-247">Performance optimizations for Application Guard for Office</span></span>

<span data-ttu-id="98eb9-248">このセクションでは、Application Guard for Office で使用されるパフォーマンスの最適化の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="98eb9-248">This section provides an overview of the performance optimizations used in Application Guard for Office.</span></span> <span data-ttu-id="98eb9-249">この情報は、Application Guard が有効な場合に、管理者が Office またはシステム全体のパフォーマンスに関連するユーザーからのレポートを診断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="98eb9-249">This information can help administrators diagnose reports from users related to the performance of Office or the overall system when Application Guard is enabled.</span></span>

<span data-ttu-id="98eb9-250">Application Guard は、仮想化されたコンテナーを使用して、信頼されていないドキュメントをシステムから分離します。</span><span class="sxs-lookup"><span data-stu-id="98eb9-250">Application Guard uses a virtualized container to isolate untrusted documents away from the system.</span></span> <span data-ttu-id="98eb9-251">コンテナーを作成し、application Guard コンテナーを設定して Office ドキュメントを開くプロセスでは、パフォーマンスのオーバーヘッドが発生し、ユーザーが信頼されていないドキュメントを開く際のユーザー エクスペリエンスに悪影響を及ぼす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="98eb9-251">The process of creating a container and setting up the Application Guard container to open Office documents has a performance overhead that might negatively affect user experience when users open an untrusted document.</span></span>

<span data-ttu-id="98eb9-252">ユーザーに期待されるファイルを開くエクスペリエンスを提供するために、Application Guard はロジックを使用して、システムで次のヒューリスティックが満たされた場合にコンテナーを事前に作成します。ユーザーが過去 28 日間に保護ビューまたは Application Guard でファイルを開いている。</span><span class="sxs-lookup"><span data-stu-id="98eb9-252">To provide users with the expected file-opening experience, Application Guard uses logic to pre-create a container when the following heuristic is met on a system: A user has opened a file in either Protected View or Application Guard in the past 28 days.</span></span>

<span data-ttu-id="98eb9-253">このヒューリスティックが満たOffice、ユーザーが Windows にサインインした後、ユーザーの Application Guard コンテナーが事前に作成されます。</span><span class="sxs-lookup"><span data-stu-id="98eb9-253">When this heuristic is met, Office will pre-create an Application Guard container for the user after they sign in to Windows.</span></span> <span data-ttu-id="98eb9-254">この作成前操作の進行中は、システムのパフォーマンスが低下する可能性がありますが、操作が完了するとすぐに効果が解決されます。</span><span class="sxs-lookup"><span data-stu-id="98eb9-254">While this pre-create operation is in progress, the system may experience slow performance, but the effect will resolve as soon as the operation completes.</span></span>

> [!NOTE]
> <span data-ttu-id="98eb9-255">ヒューリスティックがコンテナーを事前に作成するために必要なヒントは、ユーザーがコンテナーを使用Officeアプリケーションによって生成されます。</span><span class="sxs-lookup"><span data-stu-id="98eb9-255">The hints needed for the heuristic to pre-create the container are generated by Office applications as a user uses them.</span></span> <span data-ttu-id="98eb9-256">Application Guard が有効になっている新しいシステムに Office をインストールした場合、Office は、ユーザーが信頼されていないドキュメントをシステムで初めて開くまでコンテナーを事前に作成しません。</span><span class="sxs-lookup"><span data-stu-id="98eb9-256">If a user installs Office on a new system where Application Guard is enabled, Office will not pre-create the container until after the first time a user opens an untrusted document on the system.</span></span> <span data-ttu-id="98eb9-257">ユーザーは、この最初のファイルが Application Guard で開くのに時間がかかるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="98eb9-257">The user will observe that this first file takes longer to open in Application Guard.</span></span>

## <a name="known-issues"></a><span data-ttu-id="98eb9-258">既知の問題</span><span class="sxs-lookup"><span data-stu-id="98eb9-258">Known issues</span></span>

* <span data-ttu-id="98eb9-259">Web リンク (または `http` ) を選択 `https` しても、ブラウザーは開かれません。</span><span class="sxs-lookup"><span data-stu-id="98eb9-259">Selecting web links (`http` or `https`) doesn't open the browser.</span></span>
* <span data-ttu-id="98eb9-260">現時点では、Application Guard で開Officeドキュメントにリッチ テキスト形式 (RTF) コンテンツまたは画像を貼り付けはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="98eb9-260">Pasting rich text format (RTF) content or images in Office documents opened with Application Guard isn't supported at this time.</span></span>
* <span data-ttu-id="98eb9-261">.NET 原因ファイルの更新が Application Guard で開くことができません。</span><span class="sxs-lookup"><span data-stu-id="98eb9-261">Updates to .NET cause files to fail to open in Application Guard.</span></span> <span data-ttu-id="98eb9-262">回避策として、ユーザーは、このエラーが発生した場合にデバイスを再起動できます。</span><span class="sxs-lookup"><span data-stu-id="98eb9-262">As a workaround, users can restart their device when they come across this failure.</span></span> <span data-ttu-id="98eb9-263">Application Guard または Windows サンドボックスを開こうとすると、エラー メッセージを受信するWindows Defender [詳細を確認してください](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap)。</span><span class="sxs-lookup"><span data-stu-id="98eb9-263">Learn more about the issue at [Receiving an error message when attempting to open Windows Defender Application Guard or Windows Sandbox](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap).</span></span>
