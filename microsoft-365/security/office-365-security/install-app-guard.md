---
title: Application Guard for Office 365 (パブリック プレビュー) (管理者向け)
keywords: application guard, 保護, 分離, 分離コンテナー, ハードウェアの分離
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 最新のハードウェア ベースの分離を取得します。 悪用や悪意のあるリンクなど、現在および新たな攻撃が従業員の生産性や企業のセキュリティを妨害するのを防ぐ。
ms.openlocfilehash: f5a5feb14db75c5baccecf0c6afafe0c42517224
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794510"
---
# <a name="application-guard-for-office-public-preview-for-admins"></a><span data-ttu-id="73617-105">Application Guard for Office (パブリック プレビュー) (管理者向け)</span><span class="sxs-lookup"><span data-stu-id="73617-105">Application Guard for Office (public preview) for admins</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="73617-106">**適用対象:** Word、Excel、PowerPoint for Microsoft 365、Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="73617-106">**Applies to:** Word, Excel, and PowerPoint for Microsoft 365, Windows 10 Enterprise</span></span>

> [!IMPORTANT]
> <span data-ttu-id="73617-107">一部の情報は、リリース前の製品に関連します。製品が商用リリースされる前に大幅に変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="73617-107">Some information relates to a prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="73617-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="73617-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="73617-109">Microsoft Defender Application Guard for Office (Office 用 Application Guard) は、信頼されていないファイルが信頼できるリソースにアクセスし、新たな攻撃から企業を安全に保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="73617-109">Microsoft Defender Application Guard for Office (Application Guard for Office) helps prevent untrusted files from accessing trusted resources, keeping your enterprise safe from new and emerging attacks.</span></span> <span data-ttu-id="73617-110">この記事では、管理者が Application Guard for Office のプレビュー用にデバイスをセットアップする方法についてOffice。</span><span class="sxs-lookup"><span data-stu-id="73617-110">This article walks admins through setting up devices for a preview of Application Guard for Office.</span></span> <span data-ttu-id="73617-111">システム要件とインストール手順に関する情報を提供し、デバイスで Application Guard Officeを有効にします。</span><span class="sxs-lookup"><span data-stu-id="73617-111">It provides information about system requirements and installation steps to enable Application Guard for Office on a device.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="73617-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="73617-112">Prerequisites</span></span>

### <a name="minimum-hardware-requirements"></a><span data-ttu-id="73617-113">ハードウェアの最小要件</span><span class="sxs-lookup"><span data-stu-id="73617-113">Minimum hardware requirements</span></span>

* <span data-ttu-id="73617-114">**CPU**: 64 ビット、4 コア (物理または仮想)、仮想化拡張機能 (Intel VT-x または AMD-V)、Core i5 と同等以上の推奨</span><span class="sxs-lookup"><span data-stu-id="73617-114">**CPU**: 64-bit, 4 cores (physical or virtual), virtualization extensions   (Intel VT-x OR AMD-V), Core i5 equivalent or higher recommended</span></span>
* <span data-ttu-id="73617-115">**物理メモリ**: 8 GB RAM</span><span class="sxs-lookup"><span data-stu-id="73617-115">**Physical memory**: 8-GB RAM</span></span>
* <span data-ttu-id="73617-116">**ハード ディスク**: システム ドライブに 10 GB の空き領域 (SSD を推奨)</span><span class="sxs-lookup"><span data-stu-id="73617-116">**Hard disk**: 10 GB of free space on the system drive (SSD recommended)</span></span>

### <a name="minimum-software-requirements"></a><span data-ttu-id="73617-117">最小ソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="73617-117">Minimum software requirements</span></span>

* <span data-ttu-id="73617-118">**Windows 10**: Windows 10 Enterprise エディション、クライアント ビルド バージョン 2004 (20H1) ビルド 19041</span><span class="sxs-lookup"><span data-stu-id="73617-118">**Windows 10**: Windows 10 Enterprise edition, Client Build version 2004 (20H1) build 19041</span></span>
* <span data-ttu-id="73617-119">**Office**: Office Beta Channel Build バージョン 2008 16.0.13212 以降</span><span class="sxs-lookup"><span data-stu-id="73617-119">**Office**: Office Beta Channel Build version 2008 16.0.13212 or later</span></span>
* <span data-ttu-id="73617-120">**更新プログラム パッケージ**: Windows 10 の累積的な月次セキュリティ更新 [プログラム KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)</span><span class="sxs-lookup"><span data-stu-id="73617-120">**Update package**: Windows 10 cumulative monthly security updates [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)</span></span>

<span data-ttu-id="73617-121">システム要件の詳細については、「Microsoft Defender Application Guard のシステム要件」 [を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard)。</span><span class="sxs-lookup"><span data-stu-id="73617-121">For detailed system requirements, refer to [System requirements for Microsoft Defender Application Guard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard).</span></span> <span data-ttu-id="73617-122">Insider Preview ビルドのOffice詳細については、「Insider ビルドの展開の概要 [Office参照してください](https://insider.office.com/business/deploy)。</span><span class="sxs-lookup"><span data-stu-id="73617-122">To learn more about Office Insider Preview builds, refer to [Getting started on deploying Office Insider builds](https://insider.office.com/business/deploy).</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="73617-123">ライセンスの要件</span><span class="sxs-lookup"><span data-stu-id="73617-123">Licensing requirements</span></span>

* <span data-ttu-id="73617-124">Microsoft 365 E5 または Microsoft 365 E5 セキュリティ</span><span class="sxs-lookup"><span data-stu-id="73617-124">Microsoft 365 E5 or Microsoft 365 E5 Security</span></span>

## <a name="deploy-application-guard-for-office"></a><span data-ttu-id="73617-125">Application Guard を展開してOffice</span><span class="sxs-lookup"><span data-stu-id="73617-125">Deploy Application Guard for Office</span></span>

### <a name="enable-application-guard-for-office"></a><span data-ttu-id="73617-126">アプリケーションの Application Guard を有効Office</span><span class="sxs-lookup"><span data-stu-id="73617-126">Enable Application Guard for Office</span></span>

1. <span data-ttu-id="73617-127">Windows 10 の累積的な月次セキュリティ更新プログラム **KB4571756 をダウンロードしてインストールします**。</span><span class="sxs-lookup"><span data-stu-id="73617-127">Download and install **Windows 10 cumulative monthly security updates KB4571756**.</span></span>

2. <span data-ttu-id="73617-128">Windows の **機能で Microsoft Defender Application Guard** を選択し **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="73617-128">Select **Microsoft Defender Application Guard** under Windows Features and  select **OK**.</span></span> <span data-ttu-id="73617-129">Application Guard 機能を有効にすると、システムの再起動を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="73617-129">Enabling the Application Guard feature will prompt a system reboot.</span></span> <span data-ttu-id="73617-130">今すぐ再起動するか、手順 3. の後で再起動することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="73617-130">You can choose to reboot now or after step 3.</span></span>

   ![AG を示す [Windows の機能] ダイアログ ボックス](../../media/ag03-deploy.png)

   <span data-ttu-id="73617-132">この機能は、管理者として次の PowerShell コマンドを実行して有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="73617-132">The feature can also be enabled by running the following PowerShell command as administrator:</span></span>

   ```powershell
   Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard
   ```

3. <span data-ttu-id="73617-133">コンピューターの構成管理用テンプレート Windows コンポーネント Microsoft Defender Application Guard にある管理モードグループ ポリシーで **Microsoft Defender Application Guard \\ \\ \\ を探します**。</span><span class="sxs-lookup"><span data-stu-id="73617-133">Look for the Microsoft Defender Application Guard in Managed Mode group policy located at **Computer Configuration\\Administrative Templates\\Windows Components\\Microsoft Defender Application Guard**.</span></span> <span data-ttu-id="73617-134">[オプション] の値を **2** または **3** に設定し **、[OK]** または [適用] を選択して、このポリシーを有効 **にします**。</span><span class="sxs-lookup"><span data-stu-id="73617-134">Turn this policy on by setting the value under Options as **2** or **3** then selecting **OK** or **Apply**.</span></span>

   ![管理モードで AG を有効にする](../../media/ag04-deploy.png)

   <span data-ttu-id="73617-136">または、対応する CSP ポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="73617-136">Alternatively, you can set the corresponding CSP policy:</span></span>

   > <span data-ttu-id="73617-137">OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard**</span><span class="sxs-lookup"><span data-stu-id="73617-137">OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard**</span></span> <br> <span data-ttu-id="73617-138">データ型: **整数**</span><span class="sxs-lookup"><span data-stu-id="73617-138">Data type: **Integer**</span></span> <br> <span data-ttu-id="73617-139">値: **2**</span><span class="sxs-lookup"><span data-stu-id="73617-139">Value: **2**</span></span>

4. <span data-ttu-id="73617-140">システムを再起動します。</span><span class="sxs-lookup"><span data-stu-id="73617-140">Reboot the system.</span></span>

### <a name="set-diagnostics--feedback-to-send-full-data"></a><span data-ttu-id="73617-141">完全なデータ&送信する診断データのフィードバックを設定する</span><span class="sxs-lookup"><span data-stu-id="73617-141">Set Diagnostics & feedback to send full data</span></span>

<span data-ttu-id="73617-142">この手順により、問題の特定と修正に必要なデータが Microsoft に到達することを保証します。</span><span class="sxs-lookup"><span data-stu-id="73617-142">This step ensures that the data necessary to identify and fix problems is reaching Microsoft.</span></span> <span data-ttu-id="73617-143">Windows デバイスで診断を有効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="73617-143">Follow these steps to enable diagnostics on your Windows device:</span></span>

1. <span data-ttu-id="73617-144">スタート **メニューから [** 設定] を開きます。</span><span class="sxs-lookup"><span data-stu-id="73617-144">Open **Settings** from the Start menu.</span></span>

   ![[スタート] メニュー](../../media/ag05-diagnostic.png)

2. <span data-ttu-id="73617-146">**[Windows の設定] で、[** プライバシー] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="73617-146">On **Windows Settings**, select **Privacy**.</span></span>

   ![[Windows の設定] メニュー](../../media/ag06-diagnostic.png)

3. <span data-ttu-id="73617-148">[プライバシー] で、フィードバック **に対して [&] を選択し** 、[オプションの診断 **データ] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="73617-148">Under Privacy, select **Diagnostics & feedback** and select **Optional diagnostic data**.</span></span>

   ![[診断とフィードバック] メニュー](../../media/ag07a-diagnostic.png)

<span data-ttu-id="73617-150">Windows 診断設定の構成の詳細については、「組織内での Windows 診断データの [構成」を参照してください](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management)。</span><span class="sxs-lookup"><span data-stu-id="73617-150">For more on configuring Windows diagnostic settings, refer to [Configuring Windows diagnostic data in your organization](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management).</span></span>

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a><span data-ttu-id="73617-151">アプリケーションの Application Guard が有効Office機能を確認する</span><span class="sxs-lookup"><span data-stu-id="73617-151">Confirm that Application Guard for Office is enabled and working</span></span>

<span data-ttu-id="73617-152">Application Guard for Office が有効になっているか確認する前に、ポリシーが展開されているデバイスで Word、Excel、または PowerPoint を起動します。</span><span class="sxs-lookup"><span data-stu-id="73617-152">Before confirming that the Application Guard for Office is enabled, launch Word, Excel, or PowerPoint on a device where the policies have been deployed.</span></span> <span data-ttu-id="73617-153">アクティブ化Office確認します。</span><span class="sxs-lookup"><span data-stu-id="73617-153">Make sure Office is activated.</span></span> <span data-ttu-id="73617-154">作業 ID を使用して、最初に製品のライセンス認証Office必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="73617-154">You may need to use your work identity to activate the Office product first.</span></span>

<span data-ttu-id="73617-155">Application Guard for Officeが有効にされたのを確認するには、Word、Excel、または PowerPoint を起動し、信頼されていないドキュメントを開きます。</span><span class="sxs-lookup"><span data-stu-id="73617-155">To confirm that Application Guard for Office is now enabled, launch Word, Excel, or PowerPoint and open an untrusted document.</span></span> <span data-ttu-id="73617-156">たとえば、インターネットからダウンロードしたドキュメントや、組織外のユーザーからの電子メールの添付ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="73617-156">For example, you can open a document downloaded from the internet or an email attachment from someone outside your organization.</span></span>

<span data-ttu-id="73617-157">信頼されていないファイルを最初に起動すると、次のようなOfficeスプラッシュ画面が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="73617-157">On the first launch of an untrusted file, you may see an Office splash screen like the one below.</span></span> <span data-ttu-id="73617-158">Application Guard for Officeがアクティブ化され、ファイルが開いている間、しばらくの間表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="73617-158">It might show for some time while Application Guard for Office is being activated and the file is being opened.</span></span> <span data-ttu-id="73617-159">それ以降の信頼されていないファイルの起動は、より高速である必要があります。</span><span class="sxs-lookup"><span data-stu-id="73617-159">Subsequent launches of untrusted files should be faster.</span></span>

![Officeスプラッシュ画面](../../media/ag08-confirm.png)

<span data-ttu-id="73617-161">ファイルを開いた後、ファイルが Application Guard 内でファイルを開いたという視覚的なインジケーターが表示Office。</span><span class="sxs-lookup"><span data-stu-id="73617-161">Upon being opened, the file should display a few visual indicators that the file was opened inside Application Guard for Office:</span></span>

* <span data-ttu-id="73617-162">リボン内の吹き出し</span><span class="sxs-lookup"><span data-stu-id="73617-162">A callout in the ribbon</span></span>

  ![小さな App Guard のメモを示すドキュメント ファイル](../../media/ag09-confirm.png)

* <span data-ttu-id="73617-164">タスク バーに盾が表示されたアプリケーション アイコン</span><span class="sxs-lookup"><span data-stu-id="73617-164">The application icon with a shield in the taskbar</span></span>

  ![タスク バーのアイコン](../../media/ag12-limitations.png)

## <a name="configure-application-guard-for-office"></a><span data-ttu-id="73617-166">アプリケーション用に Application Guard をOffice</span><span class="sxs-lookup"><span data-stu-id="73617-166">Configure Application Guard for Office</span></span>

<span data-ttu-id="73617-167">Office次のポリシーをサポートし、アプリケーションの Application Guard の機能を構成Office。</span><span class="sxs-lookup"><span data-stu-id="73617-167">Office supports the following policies to enable you to configure the capabilities of Application Guard for Office.</span></span> <span data-ttu-id="73617-168">これらのポリシーは、グループ ポリシーまたはクラウド ポリシー サービスOffice構成できます。</span><span class="sxs-lookup"><span data-stu-id="73617-168">These policies can be configured through Group policies or through the Office cloud policy service.</span></span>

> [!NOTE]
> <span data-ttu-id="73617-169">これらのポリシーは間もなく使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="73617-169">These policies will become available soon.</span></span>
> <span data-ttu-id="73617-170">また、これらのポリシーを構成すると、アプリケーション の Application Guard で開いたファイルの一部の機能Office。</span><span class="sxs-lookup"><span data-stu-id="73617-170">Also, configuring these policies can disable some functionalities for files opened in Application Guard for Office.</span></span>

|<span data-ttu-id="73617-171">ポリシー</span><span class="sxs-lookup"><span data-stu-id="73617-171">Policy</span></span>|<span data-ttu-id="73617-172">説明</span><span class="sxs-lookup"><span data-stu-id="73617-172">Description</span></span>|
|---|---|
|<span data-ttu-id="73617-173">アプリケーションの Application Guard を無効Office</span><span class="sxs-lookup"><span data-stu-id="73617-173">Disable Application Guard for Office</span></span>|<span data-ttu-id="73617-174">このポリシーを有効にすると、Word、Excel、および PowerPoint は、Application Guard for Office の代わりに保護ビュー分離コンテナーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73617-174">Enabling this policy will force Word, Excel, and PowerPoint to use the Protected View isolation container instead of Application Guard for Office.</span></span> <span data-ttu-id="73617-175">このポリシーを使用すると、Edge で Application Guard を有効Office問題がある場合に、アプリケーション の Application Guard を一時的に無効にできます。</span><span class="sxs-lookup"><span data-stu-id="73617-175">This policy can be used to temporarily disable Application Guard for Office when there are issues in leaving it enabled for Edge.</span></span>|
|<span data-ttu-id="73617-176">Application Guard で開いたドキュメントのコピー/貼り付けを無効にする</span><span class="sxs-lookup"><span data-stu-id="73617-176">Disable copy/paste for documents opened in Application Guard</span></span>|<span data-ttu-id="73617-177">このポリシーを有効にすると、Application Guard for Office で開いたドキュメントから、外部で開いたドキュメントにコンテンツをコピーして貼り付けできません。</span><span class="sxs-lookup"><span data-stu-id="73617-177">Enabling this policy will prevent a user from copying and pasting content from a document opened in Application Guard for Office to a document opened outside it.</span></span>|
|<span data-ttu-id="73617-178">ユーザーがファイルに対する Application Guard 保護を削除する</span><span class="sxs-lookup"><span data-stu-id="73617-178">Prevent users from removing Application Guard protection on files</span></span>|<span data-ttu-id="73617-179">このポリシーを有効にすると、(Office アプリケーション エクスペリエンス内で) Application Guard 保護を無効にするか、Application Guard の外部でファイルを開くオプションが削除されます。</span><span class="sxs-lookup"><span data-stu-id="73617-179">Enabling this policy will remove the option (within the Office application experience) to disable Application Guard protection or open a file outside Application Guard.</span></span> <p> <span data-ttu-id="73617-180">**注:** このポリシーは、ファイルから手動で削除するか、ドキュメントを信頼できる場所に移動することでバイパスできます。</span><span class="sxs-lookup"><span data-stu-id="73617-180">**Note:** Users can still bypass this policy by manually removing the mark-of-the-web property from the file or by moving a document to a Trusted location.</span></span>|
|<span data-ttu-id="73617-181">Application Guard で開いたドキュメントからの印刷を制限する</span><span class="sxs-lookup"><span data-stu-id="73617-181">Restrict printing from documents opened in Application Guard</span></span>|<span data-ttu-id="73617-182">このポリシーを有効にすると、ユーザーが Application Guard で開いたファイルから印刷できるプリンターがOffice。</span><span class="sxs-lookup"><span data-stu-id="73617-182">Enabling this policy will limit printers a user can print to from a file opened in Application Guard for Office.</span></span> <span data-ttu-id="73617-183">たとえば、このポリシーを使用して、ユーザーが PDF にのみ印刷できるよう制限できます。</span><span class="sxs-lookup"><span data-stu-id="73617-183">For example, you can use this policy to restrict users to only print to PDF.</span></span>|
|<span data-ttu-id="73617-184">Application Guard で開いたドキュメントのカメラとマイクへのアクセスをオフにする</span><span class="sxs-lookup"><span data-stu-id="73617-184">Turn off camera and microphone access for documents opened in Application Guard</span></span>|<span data-ttu-id="73617-185">このポリシーを有効にすると、Officeの Application Guard 内のカメラとマイクへのアクセスがOffice。</span><span class="sxs-lookup"><span data-stu-id="73617-185">Enabling this policy will remove Office access to Camera and Microphone inside Application Guard for Office.</span></span>|
|

> [!NOTE]
> <span data-ttu-id="73617-186">次のポリシーを有効にするには、ユーザーがログオフして Windows に再ログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="73617-186">The following policies will require the user to log off and re-login to Windows to take effect:</span></span>
>
> * <span data-ttu-id="73617-187">Application Guard で開いたドキュメントのコピー/貼り付けを無効にする</span><span class="sxs-lookup"><span data-stu-id="73617-187">Disable copy/paste for documents opened in Application Guard</span></span>
> * <span data-ttu-id="73617-188">Application Guard で開いたドキュメントの印刷を制限する</span><span class="sxs-lookup"><span data-stu-id="73617-188">Restrict printing for documents opened in Application Guard</span></span>
> * <span data-ttu-id="73617-189">Application Guard で開いたドキュメントへのカメラとマイクのアクセスをオフにする</span><span class="sxs-lookup"><span data-stu-id="73617-189">Turn off camera and mic access to documents opened in Application Guard</span></span>

## <a name="submit-feedback"></a><span data-ttu-id="73617-190">フィードバックの送信</span><span class="sxs-lookup"><span data-stu-id="73617-190">Submit feedback</span></span>

### <a name="submit-feedback-via-feedback-hub"></a><span data-ttu-id="73617-191">フィードバック Hub 経由でフィードバックを送信する</span><span class="sxs-lookup"><span data-stu-id="73617-191">Submit feedback via Feedback Hub</span></span>

<span data-ttu-id="73617-192">Application Guard for Office を起動するときに問題が発生した場合は、フィードバック Hub からフィードバックを送信してください。</span><span class="sxs-lookup"><span data-stu-id="73617-192">If you encounter any issues when launching Application Guard for Office, you are encouraged to submit your feedback via Feedback Hub:</span></span>

1. <span data-ttu-id="73617-193">フィードバック Hub **アプリを開き** 、サインインします。</span><span class="sxs-lookup"><span data-stu-id="73617-193">Open the **Feedback Hub app** and sign in.</span></span>

2. <span data-ttu-id="73617-194">Application Guard の起動中にエラー ダイアログが表示された場合は、エラー ダイアログで **[Microsoft** に報告] を選択して、新しいフィードバックの送信を開始します。</span><span class="sxs-lookup"><span data-stu-id="73617-194">If you get an error dialog while launching Application Guard, select **Report to Microsoft** in the error dialog to start a new feedback submission.</span></span> <span data-ttu-id="73617-195">それ以外の場合は、Application Guard の適切なカテゴリを選択するために移動し、+[新しいフィードバックの追加] を右 <https://aka.ms/mdagoffice-fb> に選択します。 </span><span class="sxs-lookup"><span data-stu-id="73617-195">Otherwise, navigate to <https://aka.ms/mdagoffice-fb> to select the correct category for Application Guard, then select **+ Add new feedback** near the top right.</span></span>

3. <span data-ttu-id="73617-196">まだ入力 **されていない場合は、[** フィードバックの要約] ボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="73617-196">Fill in the **Summarize your feedback** box if it isn't already filled in for you.</span></span>

4. <span data-ttu-id="73617-197">発生した **問題と** 実行した手順の詳細な説明を [詳細に説明] ボックスに入力し、[次へ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="73617-197">Fill in the **Explain in more detail** box with a detailed description of the issue you experienced and what steps you took, then select **Next**.</span></span>

5. <span data-ttu-id="73617-198">問題の横にあるバブルを選択します。</span><span class="sxs-lookup"><span data-stu-id="73617-198">Select the bubble next to Problem.</span></span> <span data-ttu-id="73617-199">選択したカテゴリがセキュリティとプライバシーに関する Microsoft Defender Application Guard Officeし、[ **\> 次へ**] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="73617-199">Make sure the category selected is **Security and Privacy \> Microsoft Defender Application Guard – Office**, then select **Next**.</span></span>

6. <span data-ttu-id="73617-200">[新 **しいフィードバック] を選択し**、[次へ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="73617-200">Select **New feedback**, then **Next**.</span></span>

7. <span data-ttu-id="73617-201">問題に関するトレースを収集します。</span><span class="sxs-lookup"><span data-stu-id="73617-201">Collect traces about the issue:</span></span>

   1. <span data-ttu-id="73617-202">[問題 **の再作成] タイルを展開** します。</span><span class="sxs-lookup"><span data-stu-id="73617-202">Expand the **Recreate my problem** tile.</span></span>

   2. <span data-ttu-id="73617-203">Application Guard の実行中に問題が発生した場合は、Application Guard インスタンスを開きます。</span><span class="sxs-lookup"><span data-stu-id="73617-203">If the issue you're experiencing occurs while Application Guard is running, open an Application Guard instance.</span></span> <span data-ttu-id="73617-204">これにより、Application Guard コンテナー内から追加のトレースを収集できます。</span><span class="sxs-lookup"><span data-stu-id="73617-204">Doing this allows additional traces to be collected from within the Application Guard container.</span></span>

   3. <span data-ttu-id="73617-205">[Start **recording] (** レコーディングの開始) を選び、タイルの回転が止まるのを待ち、[記録を停止] と *言います*。</span><span class="sxs-lookup"><span data-stu-id="73617-205">Select **Start recording** and wait for the tile to stop spinning and say *Stop recording*.</span></span>

   4. <span data-ttu-id="73617-206">Application Guard の問題を完全に再現します。</span><span class="sxs-lookup"><span data-stu-id="73617-206">Fully reproduce the issue with Application Guard.</span></span> <span data-ttu-id="73617-207">これには、Application Guard インスタンスを起動しようとして失敗するまで待機したり、実行中の Application Guard インスタンスで問題を再現したりすることがあります。</span><span class="sxs-lookup"><span data-stu-id="73617-207">This might include attempting to launch an Application Guard instance and waiting until it fails, or reproducing an issue in a running Application Guard instance.</span></span>

   5. <span data-ttu-id="73617-208">[記録の **停止] タイルを選択** します。</span><span class="sxs-lookup"><span data-stu-id="73617-208">Select the **Stop recording** tile.</span></span>

   6. <span data-ttu-id="73617-209">実行中の Application Guard インスタンスは、申請の数分後まで開いた状態にしておき、コンテナー診断も収集できます。</span><span class="sxs-lookup"><span data-stu-id="73617-209">Keep any running Application Guard instance/s open, even until a few minutes after submission, so that container diagnostics can also be collected.</span></span>

8. <span data-ttu-id="73617-210">問題に関連するスクリーンショットやファイルを添付します。</span><span class="sxs-lookup"><span data-stu-id="73617-210">Attach any relevant screenshots or files related to the problem.</span></span>

9. <span data-ttu-id="73617-211">**[送信]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="73617-211">Select **Submit**.</span></span>

### <a name="submit-feedback-via-office-customer-voice"></a><span data-ttu-id="73617-212">カスタマー ボイスを使用してOfficeを送信する</span><span class="sxs-lookup"><span data-stu-id="73617-212">Submit feedback via Office Customer Voice</span></span>

<span data-ttu-id="73617-213">また、Application Guard でドキュメントを開Office問題が発生した場合は、Officeからフィードバックを送信できます。</span><span class="sxs-lookup"><span data-stu-id="73617-213">You may also submit feedback from within Office if the issue happens when Office documents are opened in Application Guard.</span></span> <span data-ttu-id="73617-214">フィードバックの提出 [についてはOffice Insider ハンド](https://insider.office.com/handbook) ブックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="73617-214">Refer to the [Office Insider Handbook](https://insider.office.com/handbook) for submitting feedback.</span></span>

## <a name="integration-with-microsoft-defender-for-endpoint-and-microsoft-defender-for-office-365"></a><span data-ttu-id="73617-215">Microsoft Defender for Endpoint および Microsoft Defender for Office 365 との統合</span><span class="sxs-lookup"><span data-stu-id="73617-215">Integration with Microsoft Defender for Endpoint and Microsoft Defender for Office 365</span></span>

<span data-ttu-id="73617-216">Application Guard for Office Microsoft Defender for Endpoint と統合され、分離された環境で発生する悪意のあるアクティビティの監視と警告を提供します。</span><span class="sxs-lookup"><span data-stu-id="73617-216">Application Guard for Office is integrated with Microsoft Defender for Endpoint to provide monitoring and alerting on malicious activity happening in the isolated environment.</span></span>

<span data-ttu-id="73617-217">Microsoft Defender for Endpoint は、エンタープライズ ネットワークが高度な脅威を防止、検出、調査、および対応するために設計されたセキュリティ プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="73617-217">Microsoft Defender for Endpoint is a security platform designed to help enterprise networks prevent, detect, investigate, and respond to advanced threats.</span></span> <span data-ttu-id="73617-218">このプラットフォームについて詳しくは [、Microsoft Defender for Endpoint のページをご覧](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp) ください。</span><span class="sxs-lookup"><span data-stu-id="73617-218">For more details about this platform, visit the [Microsoft Defender for Endpoint](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp) page.</span></span> <span data-ttu-id="73617-219">このプラットフォームへのデバイスのオンボードについて詳しくは、デバイスを Microsoft Defender for Endpoint サービス [にオンボードする方法をご覧ください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure)。</span><span class="sxs-lookup"><span data-stu-id="73617-219">Learn more about onboarding devices to this platform at [Onboard devices to the Microsoft Defender for Endpoint service](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure).</span></span>

<span data-ttu-id="73617-220">また、Office 365 用に Microsoft Defender をエンドポイント用の Defender と組み合Office構成できます。</span><span class="sxs-lookup"><span data-stu-id="73617-220">You can also configure Microsoft Defender for Office 365 to work with Defender for Endpoint.</span></span> <span data-ttu-id="73617-221">「Microsoft [Defender for Endpoint と Office 365 の Defender の統合」をご覧ください](integrate-office-365-ti-with-wdatp.md)。</span><span class="sxs-lookup"><span data-stu-id="73617-221">Refer to [Integrate Defender for Office 365 with Microsoft Defender for Endpoint](integrate-office-365-ti-with-wdatp.md).</span></span>

## <a name="limitations-and-considerations"></a><span data-ttu-id="73617-222">制限事項と考慮事項</span><span class="sxs-lookup"><span data-stu-id="73617-222">Limitations and considerations</span></span>

* <span data-ttu-id="73617-223">Office 用 Application Guard は、信頼できる企業リソース、イントラネット、ユーザーの ID、およびコンピューターに存在する任意のファイルへの信頼されていないドキュメントのアクセスを分離する制限付きモードです。</span><span class="sxs-lookup"><span data-stu-id="73617-223">Application Guard for Office is a restricted mode that isolates untrusted documents from accessing trusted corporate resources, intranet, the user's identity, and arbitrary files present on the computer.</span></span> <span data-ttu-id="73617-224">その結果、たとえばディスク上のローカル ファイルから画像を挿入するなどのアクセスに依存する機能にユーザーがアクセスしようとすると、エラーが発生し、次のようなプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="73617-224">As a result, if a user tries to access a feature that has a dependency on such access, for example, inserting a picture from a local file on disk, it will fail and produce a prompt like the one below.</span></span> <span data-ttu-id="73617-225">信頼されていないドキュメントが信頼できるリソースにアクセスするには、ユーザーがドキュメントから Application Guard 保護を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73617-225">To enable an untrusted document to access trusted resources, users must remove Application Guard protection from the document.</span></span>

  ![[安全に保つために、この機能は使用できません] というダイアログ ボックス](../../media/ag10-limitations.png)

  > [!NOTE]
  > <span data-ttu-id="73617-227">ファイルとそのソース、またはファイルの送信元を信頼している場合にのみ、保護を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73617-227">Advise users to only remove protection if they trust the file and its source or where it came from.</span></span>

* <span data-ttu-id="73617-228">Application Guard では、マクロやコントロールActiveXドキュメント内のアクティブなコンテンツが無効Office。</span><span class="sxs-lookup"><span data-stu-id="73617-228">Active content in documents like macros and ActiveX controls are disabled in Application Guard for Office.</span></span> <span data-ttu-id="73617-229">アクティブなコンテンツを有効にするには、Application Guard 保護を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73617-229">Users need to remove Application Guard protection to enable active content.</span></span>

* <span data-ttu-id="73617-230">ネットワーク共有から開いた信頼できないファイルや、別の組織の OneDrive、OneDrive for Business、または SharePoint Online から共有されたファイルは、Application Guard で読み取り専用として開きます。</span><span class="sxs-lookup"><span data-stu-id="73617-230">Untrusted files opened from network shares or files shared from OneDrive, OneDrive for Business, or SharePoint Online from a different organization open as read-only in Application Guard.</span></span> <span data-ttu-id="73617-231">ユーザーは、そのようなファイルのローカル コピーを保存してコンテナー内で作業を続行したり、元のファイルを直接操作する保護を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="73617-231">Users can save a local copy of such files to continue working in the container or remove protection to directly work with the original file.</span></span>

* <span data-ttu-id="73617-232">Information Rights Management (IRM) によって保護されているファイルは、引き続き保護ビューで開きます。</span><span class="sxs-lookup"><span data-stu-id="73617-232">Files that are protected by Information Rights Management (IRM) continue to open in Protected View.</span></span>

* <span data-ttu-id="73617-233">Application Guard for Office アプリケーションをOfficeしたカスタマイズは、ユーザーがログオフしてデバイスにログインまたは再起動した後も保持されません。</span><span class="sxs-lookup"><span data-stu-id="73617-233">Any customizations to Office applications in Application Guard for Office will not persist after a user logs off and logs back in or reboots the device.</span></span>

* <span data-ttu-id="73617-234">UIA フレームワークを使うアクセシビリティ ツールだけが、アプリ用 Application Guard で開いたファイルにアクセシビリティ対応のエクスペリエンスOffice。</span><span class="sxs-lookup"><span data-stu-id="73617-234">Only Accessibility tools that use the UIA framework can provide an accessible experience for files opened in Application Guard for Office.</span></span>

* <span data-ttu-id="73617-235">インストール後に Application Guard を初めて起動するには、ネットワーク接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="73617-235">Network connectivity is required for the first launch of Application Guard after installation.</span></span> <span data-ttu-id="73617-236">これは、Application Guard がライセンスを検証するために必要です。</span><span class="sxs-lookup"><span data-stu-id="73617-236">This is required for Application Guard to validate the license.</span></span>

* <span data-ttu-id="73617-237">ドキュメントの情報セクションでは、 *最終* 変更者プロパティにユーザーとして WDAGUtilityAccount が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="73617-237">In the document's info section, the *Last Modified By* property may display WDAGUtilityAccount as the user.</span></span> <span data-ttu-id="73617-238">デスクトップ ユーザーの ID が Application Guard コンテナー内で共有されていない場合、これは Application Guard で構成された匿名ユーザーです。</span><span class="sxs-lookup"><span data-stu-id="73617-238">This is the anonymous user configured in Application Guard given that the desktop user's identity is not shared inside the Application Guard container.</span></span>

## <a name="performance-optimizations-for-application-guard"></a><span data-ttu-id="73617-239">Application Guard のパフォーマンスの最適化</span><span class="sxs-lookup"><span data-stu-id="73617-239">Performance optimizations for Application Guard</span></span>

<span data-ttu-id="73617-240">このセクションでは、Application Guard で使用されるパフォーマンスの最適化の概要をOffice。</span><span class="sxs-lookup"><span data-stu-id="73617-240">This section provides an overview of the performance optimizations used in Application Guard for Office.</span></span> <span data-ttu-id="73617-241">この情報は、Application Guard が有効な場合に、管理者が Office またはシステム全体のパフォーマンスに関連するユーザーからのレポートを診断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="73617-241">This information can help administrators diagnose reports from users related to the performance of Office or the overall system when Application Guard is enabled.</span></span>

<span data-ttu-id="73617-242">Application Guard は、仮想化されたコンテナーを使用して、信頼されていないドキュメントをシステムから分離します。</span><span class="sxs-lookup"><span data-stu-id="73617-242">Application Guard uses a virtualized container to isolate untrusted documents away from the system.</span></span> <span data-ttu-id="73617-243">コンテナーを作成し、application Guard コンテナーを設定して Office ドキュメントを開くプロセスでは、パフォーマンスのオーバーヘッドが発生し、ユーザーが信頼されていないドキュメントを開く際のユーザー エクスペリエンスに悪影響を及ぼす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="73617-243">The process of creating a container and setting up the Application Guard container to open Office documents has a performance overhead that might negatively impact user experience when users open an  untrusted document.</span></span>

<span data-ttu-id="73617-244">ユーザーに期待されるファイルを開くエクスペリエンスを提供するために、Application Guard はロジックを使用して、システムで次のヒューリスティックが満たされた場合にコンテナーを事前に作成します。ユーザーが過去 28 日間に保護ビューまたは Application Guard でファイルを開いている。</span><span class="sxs-lookup"><span data-stu-id="73617-244">To provide users with the expected file opening experience, Application Guard uses logic to pre-create a container when the following heuristic is met on a system: A user has opened a file in either Protected View or Application Guard in the past 28 days.</span></span>

<span data-ttu-id="73617-245">このヒューリスティックが満たされたOffice、ユーザーが Windows にログインした後に、ユーザーの Application Guard コンテナーが事前に作成されます。</span><span class="sxs-lookup"><span data-stu-id="73617-245">When this heuristic is met, Office will pre-create an Application Guard container for the user after they log in to Windows.</span></span> <span data-ttu-id="73617-246">この作成前操作が進行中の場合、システムのパフォーマンスが低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="73617-246">When this pre-create operation is in progress, the system may experience slow performance.</span></span> <span data-ttu-id="73617-247">これは、操作が完了するとすぐに解決されます。</span><span class="sxs-lookup"><span data-stu-id="73617-247">This will resolve as soon as the operation completes.</span></span>

> [!NOTE]
> <span data-ttu-id="73617-248">コンテナーの事前作成に使用されるヒューリスティックに必要なヒントは、ユーザーがコンテナーを使用するOfficeアプリケーションによって生成されます。</span><span class="sxs-lookup"><span data-stu-id="73617-248">The hints needed for the heuristic used to pre-create the container are generated by Office applications as a user uses them.</span></span> <span data-ttu-id="73617-249">Application Guard が有効になっている新しいシステムに Office をインストールした場合、Office は、ユーザーがシステム上で信頼されていないドキュメントを初めて開くまでコンテナーを事前に作成しません。</span><span class="sxs-lookup"><span data-stu-id="73617-249">If a user installs Office on a new system where Application Guard is enabled, Office will not pre-create the container until after the first time a user opens an untrusted document on the system.</span></span> <span data-ttu-id="73617-250">ユーザーは、この最初のファイルが Application Guard で開くのに時間がかかるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="73617-250">The user will observe that this first file takes longer to open in Application Guard.</span></span>

## <a name="known-issues-in-preview"></a><span data-ttu-id="73617-251">プレビューでの既知の問題</span><span class="sxs-lookup"><span data-stu-id="73617-251">Known issues in preview</span></span>

* <span data-ttu-id="73617-252">Web リンク (または) をクリック `http` `https` しても、ブラウザーは開かれません。</span><span class="sxs-lookup"><span data-stu-id="73617-252">Clicking on web links (`http` or `https`) does not open the browser.</span></span>
* <span data-ttu-id="73617-253">.NET 更新プログラムを実行すると、Application Guard でファイルが開かれません。</span><span class="sxs-lookup"><span data-stu-id="73617-253">.NET updates cause files to fail to open in Application Guard.</span></span> <span data-ttu-id="73617-254">回避策として、この問題が発生した場合、ユーザーはデバイスを再起動できます。</span><span class="sxs-lookup"><span data-stu-id="73617-254">As a workaround, users can reboot their device when this issue is encountered.</span></span> <span data-ttu-id="73617-255">Application Guard または Windows サンドボックスを開こうとすると、エラー メッセージを受信するWindows Defender [詳細を確認してください](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap)。</span><span class="sxs-lookup"><span data-stu-id="73617-255">Learn more about the issue at [Receiving an error message when attempting to open Windows Defender Application Guard or Windows Sandbox](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap).</span></span>
