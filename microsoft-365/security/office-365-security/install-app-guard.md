---
title: Office 365 用 Application Guard (パブリックプレビュー) (管理者向け)
keywords: application guard、保護、分離、分離したコンテナー、ハードウェアの分離
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
description: ハードウェアベースの分離の最新情報を取得します。 悪用または悪意のあるリンクのような最新の攻撃や、従業員の生産性や企業のセキュリティを阻止できないようにします。
ms.openlocfilehash: c9b31ff91521b6badda31b6eb3202f370769a0fd
ms.sourcegitcommit: 9546708a5506fdbadbfe2500cbf1bd1aeaec6fcb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "49021075"
---
# <a name="application-guard-for-office-public-preview-for-admins"></a><span data-ttu-id="01582-105">管理者向けの Office 用アプリケーションガード (パブリックプレビュー)</span><span class="sxs-lookup"><span data-stu-id="01582-105">Application Guard for Office (public preview) for admins</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="01582-106">**適用対象:** Word、Excel、および PowerPoint for Microsoft 365、Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="01582-106">**Applies to:** Word, Excel, and PowerPoint for Microsoft 365, Windows 10 Enterprise</span></span>

>[!IMPORTANT]
><span data-ttu-id="01582-107">一部の情報は、市販される前に大幅に変更される可能性がある prereleased 製品に関連しています。</span><span class="sxs-lookup"><span data-stu-id="01582-107">Some information relates to a prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="01582-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="01582-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="01582-109">Microsoft Defender Application Guard for Office (Application Guard for Office) は、信頼されていないファイルが信頼されたリソースにアクセスしないようにすることにより、新しい攻撃や新たな攻撃からエンタープライズを保護します。</span><span class="sxs-lookup"><span data-stu-id="01582-109">Microsoft Defender Application Guard for Office (Application Guard for Office) helps prevent untrusted files from accessing trusted resources, keeping your enterprise safe from new and emerging attacks.</span></span> <span data-ttu-id="01582-110">この記事では、管理者が Office 用 Application Guard のプレビュー用のデバイスをセットアップする手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="01582-110">This article walks admins through setting up devices for a preview of Application Guard for Office.</span></span> <span data-ttu-id="01582-111">デバイス上の Office 用 Application Guard を有効にするためのシステム要件とインストール手順に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="01582-111">It provides information about system requirements and installation steps to enable Application Guard for Office on a device.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="01582-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="01582-112">Prerequisites</span></span>

### <a name="minimum-hardware-requirements"></a><span data-ttu-id="01582-113">ハードウェアの最小要件</span><span class="sxs-lookup"><span data-stu-id="01582-113">Minimum hardware requirements</span></span>

* <span data-ttu-id="01582-114">**CPU** :64 ビット、4コア (物理または仮想)、仮想化拡張機能 (Intel VT-x または AMD-V)、コア i5 同等またはそれ以上推奨</span><span class="sxs-lookup"><span data-stu-id="01582-114">**CPU** : 64-bit, 4 cores (physical or virtual), virtualization extensions   (Intel VT-x OR AMD-V), Core i5 equivalent or higher recommended</span></span>
* <span data-ttu-id="01582-115">**物理メモリ** : 8 GB の RAM</span><span class="sxs-lookup"><span data-stu-id="01582-115">**Physical memory** : 8-GB RAM</span></span>
* <span data-ttu-id="01582-116">**ハードディスク** : システムドライブに 10 GB の空き領域 (SSD を推奨)</span><span class="sxs-lookup"><span data-stu-id="01582-116">**Hard disk** : 10 GB of free space on the system drive (SSD recommended)</span></span>

### <a name="minimum-software-requirements"></a><span data-ttu-id="01582-117">最小ソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="01582-117">Minimum software requirements</span></span>

* <span data-ttu-id="01582-118">**Windows 10** : Windows 10 Enterprise Edition、クライアントビルドバージョン 2004 (20H1) ビルド19041</span><span class="sxs-lookup"><span data-stu-id="01582-118">**Windows 10** : Windows 10 Enterprise edition, Client Build version 2004 (20H1) build 19041</span></span>
* <span data-ttu-id="01582-119">**Office** : Office ベータチャネルビルドバージョン 2008 16.0.13212 以降</span><span class="sxs-lookup"><span data-stu-id="01582-119">**Office** : Office Beta Channel Build version 2008 16.0.13212 or later</span></span>
* <span data-ttu-id="01582-120">**更新プログラムパッケージ** : 毎月の Windows 10 累積セキュリティ更新プログラム [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)</span><span class="sxs-lookup"><span data-stu-id="01582-120">**Update package** : Windows 10 cumulative monthly security updates [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)</span></span>

<span data-ttu-id="01582-121">システム要件の詳細については、「 [Microsoft Defender Application Guard のシステム要件](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01582-121">For detailed system requirements, refer to [System requirements for Microsoft Defender Application Guard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard).</span></span> <span data-ttu-id="01582-122">Office Insider Preview ビルドの詳細については、「 [Office insider ビルドの展開の](https://insider.office.com/business/deploy)概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01582-122">To learn more about Office Insider Preview builds, refer to [Getting started on deploying Office Insider builds](https://insider.office.com/business/deploy).</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="01582-123">ライセンスの要件</span><span class="sxs-lookup"><span data-stu-id="01582-123">Licensing requirements</span></span>

* <span data-ttu-id="01582-124">Microsoft 365 E5 または Microsoft 365 E5 セキュリティ</span><span class="sxs-lookup"><span data-stu-id="01582-124">Microsoft 365 E5 or Microsoft 365 E5 Security</span></span>

## <a name="deploy-application-guard-for-office"></a><span data-ttu-id="01582-125">Office 用 Application Guard を展開する</span><span class="sxs-lookup"><span data-stu-id="01582-125">Deploy Application Guard for Office</span></span>

### <a name="enable-application-guard-for-office"></a><span data-ttu-id="01582-126">Office 用 Application Guard を有効にする</span><span class="sxs-lookup"><span data-stu-id="01582-126">Enable Application Guard for Office</span></span>

1. <span data-ttu-id="01582-127">**Windows 10 累積された毎月のセキュリティ更新プログラム KB4571756** をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="01582-127">Download and install **Windows 10 cumulative monthly security updates KB4571756**.</span></span>

2. <span data-ttu-id="01582-128">[Windows の機能] の下にある [ **Microsoft Defender Application Guard** ] を選択し、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="01582-128">Select **Microsoft Defender Application Guard** under Windows Features and  select **OK**.</span></span> <span data-ttu-id="01582-129">Application Guard 機能を有効にすると、システムの再起動が求められます。</span><span class="sxs-lookup"><span data-stu-id="01582-129">Enabling the Application Guard feature will prompt a system reboot.</span></span> <span data-ttu-id="01582-130">今すぐ再起動するか、手順3の後で再起動するかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="01582-130">You can choose to reboot now or after step 3.</span></span>

   ![AG が表示されている [Windows の機能] ダイアログボックス](../../media/ag03-deploy.png)

   <span data-ttu-id="01582-132">この機能は、管理者として次の PowerShell コマンドを実行することによって有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="01582-132">The feature can also be enabled by running the following PowerShell command as administrator:</span></span>

   ```powershell
   Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard
   ```

3. <span data-ttu-id="01582-133">「 **コンピューターの構成 \\ 管理用テンプレート \\ Windows コンポーネント \\ microsoft defender application guard** 」にある「管理モードグループポリシー」の「microsoft defender application Guard」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01582-133">Look for the Microsoft Defender Application Guard in Managed Mode group policy located at **Computer Configuration\\Administrative Templates\\Windows Components\\Microsoft Defender Application Guard**.</span></span> <span data-ttu-id="01582-134">[オプション] の値を **2** または **3** に設定し、[ **OK]** または [ **適用** ] を選択して、このポリシーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="01582-134">Turn this policy on by setting the value under Options as **2** or **3** then selecting **OK** or **Apply**.</span></span>

   ![管理モードで AG を有効にする](../../media/ag04-deploy.png)

   <span data-ttu-id="01582-136">または、対応する CSP ポリシーを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="01582-136">Alternatively, you can set the corresponding CSP policy:</span></span>

   <span data-ttu-id="01582-137">OMA URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard**</span><span class="sxs-lookup"><span data-stu-id="01582-137">OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard**</span></span><br/>
   <span data-ttu-id="01582-138">データ型: **Integer**</span><span class="sxs-lookup"><span data-stu-id="01582-138">Data type: **Integer**</span></span><br/>
   <span data-ttu-id="01582-139">値: **2**</span><span class="sxs-lookup"><span data-stu-id="01582-139">Value: **2**</span></span>

4. <span data-ttu-id="01582-140">システムを再起動します。</span><span class="sxs-lookup"><span data-stu-id="01582-140">Reboot the system.</span></span>

### <a name="set-diagnostics--feedback-to-send-full-data"></a><span data-ttu-id="01582-141">完全なデータを送信するための診断 & フィードバックの設定</span><span class="sxs-lookup"><span data-stu-id="01582-141">Set Diagnostics & feedback to send full data</span></span>

<span data-ttu-id="01582-142">この手順により、問題を特定して修正するために必要なデータが Microsoft に届くことが保証されます。</span><span class="sxs-lookup"><span data-stu-id="01582-142">This step ensures that the data necessary to identify and fix problems is reaching Microsoft.</span></span> <span data-ttu-id="01582-143">Windows デバイスで診断を有効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="01582-143">Follow these steps to enable diagnostics on your Windows device:</span></span>

1. <span data-ttu-id="01582-144">[スタート] メニューから [ **設定** ] を開きます。</span><span class="sxs-lookup"><span data-stu-id="01582-144">Open **Settings** from the Start menu.</span></span>

   ![[スタート] メニュー](../../media/ag05-diagnostic.png)

2. <span data-ttu-id="01582-146">[ **Windows の設定** ] で、[ **プライバシー** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="01582-146">On **Windows Settings** , select **Privacy**.</span></span>

   ![[Windows の設定] メニュー](../../media/ag06-diagnostic.png)

3. <span data-ttu-id="01582-148">[プライバシー] で [ **診断 &** ] を選択し、[ **オプションの診断データ** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="01582-148">Under Privacy, select **Diagnostics & feedback** and select **Optional diagnostic data**.</span></span>

   ![[診断とフィードバック] メニュー](../../media/ag07a-diagnostic.png)

<span data-ttu-id="01582-150">Windows 診断設定の構成の詳細については、「 [組織で windows 診断データを構成する」](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01582-150">For more on configuring Windows diagnostic settings, refer to [Configuring Windows diagnostic data in your organization](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management).</span></span>

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a><span data-ttu-id="01582-151">Office 用アプリケーションガードが有効で動作していることを確認する</span><span class="sxs-lookup"><span data-stu-id="01582-151">Confirm that Application Guard for Office is enabled and working</span></span>

<span data-ttu-id="01582-152">Office の Application Guard が有効になっていることを確認する前に、ポリシーが展開されているデバイスで Word、Excel、または PowerPoint を起動します。</span><span class="sxs-lookup"><span data-stu-id="01582-152">Before confirming that the Application Guard for Office is enabled, launch Word, Excel, or PowerPoint on a device where the policies have been deployed.</span></span> <span data-ttu-id="01582-153">Office がライセンス認証されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="01582-153">Make sure Office is activated.</span></span> <span data-ttu-id="01582-154">最初に Office 製品のライセンス認証を行うには、職場の id を使用する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="01582-154">You may need to use your work identity to activate the Office product first.</span></span>

<span data-ttu-id="01582-155">Office 用アプリケーションキラーが有効になっていることを確認するために、Word、Excel、または PowerPoint を起動して、信頼されていないドキュメントを開きます。</span><span class="sxs-lookup"><span data-stu-id="01582-155">To confirm that Application Guard for Office is now enabled, launch Word, Excel, or PowerPoint and open an untrusted document.</span></span> <span data-ttu-id="01582-156">たとえば、インターネットからダウンロードしたドキュメントや、組織外のユーザーからの電子メール添付ファイルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="01582-156">For example, you can open a document downloaded from the internet or an email attachment from someone outside your organization.</span></span>

<span data-ttu-id="01582-157">信頼されていないファイルが初めて起動されたときに、次のような Office スプラッシュスクリーンが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="01582-157">On the first launch of an untrusted file, you may see an Office splash screen like the one below.</span></span> <span data-ttu-id="01582-158">Application Guard for Office がアクティブ化され、ファイルが開かれている間、しばらくの間は表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="01582-158">It might show for some time while Application Guard for Office is being activated and the file is being opened.</span></span> <span data-ttu-id="01582-159">信頼されていないファイルの以降の起動は高速になります。</span><span class="sxs-lookup"><span data-stu-id="01582-159">Subsequent launches of untrusted files should be faster.</span></span>

![Office アプリのスプラッシュ画面](../../media/ag08-confirm.png)

<span data-ttu-id="01582-161">ファイルを開くときに、ファイルが Application Guard for Office の内部で開かれたことを示す視覚的なインジケーターがいくつか表示されます。</span><span class="sxs-lookup"><span data-stu-id="01582-161">Upon being opened, the file should display a few visual indicators that the file was opened inside Application Guard for Office:</span></span>

* <span data-ttu-id="01582-162">リボンの吹き出し</span><span class="sxs-lookup"><span data-stu-id="01582-162">A callout in the ribbon</span></span>

  ![小規模 App Guard に関するメモを示す Doc ファイル](../../media/ag09-confirm.png)

* <span data-ttu-id="01582-164">タスクバーに盾があるアプリケーションアイコン</span><span class="sxs-lookup"><span data-stu-id="01582-164">The application icon with a shield in the taskbar</span></span>

  ![タスクバーのアイコン](../../media/ag12-limitations.png)

## <a name="configure-application-guard-for-office"></a><span data-ttu-id="01582-166">Office 用 Application Guard を構成する</span><span class="sxs-lookup"><span data-stu-id="01582-166">Configure Application Guard for Office</span></span>

<span data-ttu-id="01582-167">Office では、次のポリシーをサポートして、Office 用 Application Guard の機能を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="01582-167">Office supports the following policies to enable you to configure the capabilities of Application Guard for Office.</span></span> <span data-ttu-id="01582-168">これらのポリシーは、グループポリシーまたは Office クラウドポリシーサービスを使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="01582-168">These policies can be configured through Group policies or through the Office cloud policy service.</span></span>

> [!NOTE]
> <span data-ttu-id="01582-169">これらのポリシーは近日中に利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="01582-169">These policies will become available soon.</span></span>
> <span data-ttu-id="01582-170">また、これらのポリシーを構成すると、Application Guard for Office で開かれたファイルの一部の機能を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="01582-170">Also, configuring these policies can disable some functionalities for files opened in Application Guard for Office.</span></span>

|<span data-ttu-id="01582-171">ポリシー</span><span class="sxs-lookup"><span data-stu-id="01582-171">Policy</span></span>|<span data-ttu-id="01582-172">説明</span><span class="sxs-lookup"><span data-stu-id="01582-172">Description</span></span>|
|---|---|
|<span data-ttu-id="01582-173">Office 用 Application Guard を無効にする</span><span class="sxs-lookup"><span data-stu-id="01582-173">Disable Application Guard for Office</span></span>|<span data-ttu-id="01582-174">このポリシーを有効にすると、Word、Excel、および PowerPoint で、Office の Application Guard ではなく、保護されたビューの分離コンテナーが使用されるようになります。</span><span class="sxs-lookup"><span data-stu-id="01582-174">Enabling this policy will force Word, Excel, and PowerPoint to use the Protected View isolation container instead of Application Guard for Office.</span></span> <span data-ttu-id="01582-175">このポリシーを使用すると、エッジを有効にしたままでも問題が発生した場合に、Office の Application Guard を一時的に無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="01582-175">This policy can be used to temporarily disable Application Guard for Office when there are issues in leaving it enabled for Edge.</span></span>|
|<span data-ttu-id="01582-176">Application Guard で開いたドキュメントのコピー/貼り付けを無効にする</span><span class="sxs-lookup"><span data-stu-id="01582-176">Disable copy/paste for documents opened in Application Guard</span></span>|<span data-ttu-id="01582-177">このポリシーを有効にすると、ユーザーは Application Guard for Office で開かれているドキュメントから外部で開いているドキュメントにコンテンツをコピーして貼り付けることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="01582-177">Enabling this policy will prevent a user from copying and pasting content from a document opened in Application Guard for Office to a document opened outside it.</span></span>|
|<span data-ttu-id="01582-178">ユーザーがファイルの Application Guard 保護を削除できないようにする</span><span class="sxs-lookup"><span data-stu-id="01582-178">Prevent users from removing Application Guard protection on files</span></span>|<span data-ttu-id="01582-179">このポリシーを有効にすると、(Office アプリケーションの環境内) のオプションが削除され、Application Guard 保護を無効にするか、Application Guard の外部でファイルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="01582-179">Enabling this policy will remove the option (within the Office application experience) to disable Application Guard protection or open a file outside Application Guard.</span></span> <p> <span data-ttu-id="01582-180">**注:** ユーザーは、このポリシーを引き続きバイパスできます。このプロパティは、ファイルから手動で削除するか、ドキュメントを信頼できる場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="01582-180">**Note:** Users can still bypass this policy by manually removing the mark-of-the-web property from the file or by moving a document to a Trusted location.</span></span>|
|<span data-ttu-id="01582-181">Application Guard で開いたドキュメントからの印刷を制限する</span><span class="sxs-lookup"><span data-stu-id="01582-181">Restrict printing from documents opened in Application Guard</span></span>|<span data-ttu-id="01582-182">このポリシーを有効にすると、ユーザーが Application Guard for Office で開いているファイルから印刷できるプリンターが制限されます。</span><span class="sxs-lookup"><span data-stu-id="01582-182">Enabling this policy will limit printers a user can print to from a file opened in Application Guard for Office.</span></span> <span data-ttu-id="01582-183">たとえば、このポリシーを使用すると、ユーザーが PDF のみに印刷されるように制限することができます。</span><span class="sxs-lookup"><span data-stu-id="01582-183">For example, you can use this policy to restrict users to only print to PDF.</span></span>|
|<span data-ttu-id="01582-184">Application Guard で開いたドキュメントのカメラとマイクへのアクセスをオフにする</span><span class="sxs-lookup"><span data-stu-id="01582-184">Turn off camera and microphone access for documents opened in Application Guard</span></span>|<span data-ttu-id="01582-185">このポリシーを有効にすると、office の Application Guard 内のカメラおよびマイクへの Office アクセスが削除されます。</span><span class="sxs-lookup"><span data-stu-id="01582-185">Enabling this policy will remove Office access to Camera and Microphone inside Application Guard for Office.</span></span>|
|

> [!NOTE]
> <span data-ttu-id="01582-186">次のポリシーでは、ユーザーがログオフし、Windows に再ログインして有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="01582-186">The following policies will require the user to log off and re-login to Windows to take effect:</span></span>
>
> * <span data-ttu-id="01582-187">Application Guard で開いたドキュメントのコピー/貼り付けを無効にする</span><span class="sxs-lookup"><span data-stu-id="01582-187">Disable copy/paste for documents opened in Application Guard</span></span>
> * <span data-ttu-id="01582-188">Application Guard で開いたドキュメントの印刷を制限する</span><span class="sxs-lookup"><span data-stu-id="01582-188">Restrict printing for documents opened in Application Guard</span></span>
> * <span data-ttu-id="01582-189">Application Guard で開かれたドキュメントへのカメラおよびマイクアクセスをオフにする</span><span class="sxs-lookup"><span data-stu-id="01582-189">Turn off camera and mic access to documents opened in Application Guard</span></span>

## <a name="submit-feedback"></a><span data-ttu-id="01582-190">フィードバックの送信</span><span class="sxs-lookup"><span data-stu-id="01582-190">Submit feedback</span></span>

### <a name="submit-feedback-via-feedback-hub"></a><span data-ttu-id="01582-191">フィードバックハブ経由でフィードバックを送信する</span><span class="sxs-lookup"><span data-stu-id="01582-191">Submit feedback via Feedback Hub</span></span>

<span data-ttu-id="01582-192">Office の Application Guard を起動するときに問題が発生した場合は、フィードバックハブからフィードバックを送信することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="01582-192">If you encounter any issues when launching Application Guard for Office, you are encouraged to submit your feedback via Feedback Hub:</span></span>

1. <span data-ttu-id="01582-193">[ **フィードバックハブアプリ** ] を開き、サインインします。</span><span class="sxs-lookup"><span data-stu-id="01582-193">Open the **Feedback Hub app** and sign in.</span></span>

2. <span data-ttu-id="01582-194">Application Guard の起動中にエラーダイアログが表示された場合は、[エラー] ダイアログで [ **Microsoft に報告** する] を選択して、新しいフィードバック提出を開始します。</span><span class="sxs-lookup"><span data-stu-id="01582-194">If you get an error dialog while launching Application Guard, select **Report to Microsoft** in the error dialog to start a new feedback submission.</span></span> <span data-ttu-id="01582-195">それ以外の場合は、に移動して <https://aka.ms/wdagoffice-fb> Application Guard の適切なカテゴリを選択し、右上にある [ **+ 新しいフィードバックの追加** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="01582-195">Otherwise, navigate to <https://aka.ms/wdagoffice-fb> to select the correct category for Application Guard, then select **+ Add new feedback** near the top right.</span></span>

3. <span data-ttu-id="01582-196">[フィードバックを **要約** する] ボックスに入力します (まだ入力されていない場合)。</span><span class="sxs-lookup"><span data-stu-id="01582-196">Fill in the **Summarize your feedback** box if it isn't already filled in for you.</span></span>

4. <span data-ttu-id="01582-197">発生した問題についての詳細な説明と必要な手順を記入し **て、[** **次へ** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="01582-197">Fill in the **Explain in more detail** box with a detailed description of the issue you experienced and what steps you took, then select **Next**.</span></span>

5. <span data-ttu-id="01582-198">[問題] の横にある [バブル] を選択します。</span><span class="sxs-lookup"><span data-stu-id="01582-198">Select the bubble next to Problem.</span></span> <span data-ttu-id="01582-199">選択したカテゴリが [ **セキュリティとプライバシー] \> Microsoft Defender Application Guard – Office** ] であることを確認して、[ **次へ** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="01582-199">Make sure the category selected is **Security and Privacy \> Microsoft Defender Application Guard – Office** , then select **Next**.</span></span>

6. <span data-ttu-id="01582-200">[ **新しいフィードバック** ] を選択し、[ **次へ** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01582-200">Select **New feedback** , then **Next**.</span></span>

7. <span data-ttu-id="01582-201">次の問題に関するトレースを収集します。</span><span class="sxs-lookup"><span data-stu-id="01582-201">Collect traces about the issue:</span></span>

   1. <span data-ttu-id="01582-202">**[問題の再作成** ] タイルを展開します。</span><span class="sxs-lookup"><span data-stu-id="01582-202">Expand the **Recreate my problem** tile.</span></span>

   2. <span data-ttu-id="01582-203">Application Guard の実行中に発生している問題が発生した場合は、Application Guard インスタンスを開きます。</span><span class="sxs-lookup"><span data-stu-id="01582-203">If the issue you're experiencing occurs while Application Guard is running, open an Application Guard instance.</span></span> <span data-ttu-id="01582-204">これにより、Application Guard コンテナー内から追加のトレースを収集できます。</span><span class="sxs-lookup"><span data-stu-id="01582-204">Doing this allows additional traces to be collected from within the Application Guard container.</span></span>

   3. <span data-ttu-id="01582-205">[ **録音を開始** する] を選択し、タイルが回転を停止するのを待ち、 *録音を停止* します。</span><span class="sxs-lookup"><span data-stu-id="01582-205">Select **Start recording** and wait for the tile to stop spinning and say *Stop recording*.</span></span>

   4. <span data-ttu-id="01582-206">問題を Application Guard に完全に再現します。</span><span class="sxs-lookup"><span data-stu-id="01582-206">Fully reproduce the issue with Application Guard.</span></span> <span data-ttu-id="01582-207">これには、Application Guard インスタンスを起動し、障害が発生するまで待機する、または実行中の Application Guard インスタンスで問題を再現しようとする場合があります。</span><span class="sxs-lookup"><span data-stu-id="01582-207">This might include attempting to launch an Application Guard instance and waiting until it fails, or reproducing an issue in a running Application Guard instance.</span></span>

   5. <span data-ttu-id="01582-208">[ **記録終了** ] タイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="01582-208">Select the **Stop recording** tile.</span></span>

   6. <span data-ttu-id="01582-209">実行中の Application Guard インスタンス/s は、送信後数分まで開いたままにしておき、コンテナーの診断を収集することもできます。</span><span class="sxs-lookup"><span data-stu-id="01582-209">Keep any running Application Guard instance/s open, even until a few minutes after submission, so that container diagnostics can also be collected.</span></span>

8. <span data-ttu-id="01582-210">問題に関連するすべてのスクリーンショットまたはファイルを添付します。</span><span class="sxs-lookup"><span data-stu-id="01582-210">Attach any relevant screenshots or files related to the problem.</span></span>

9. <span data-ttu-id="01582-211">**[送信]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="01582-211">Select **Submit**.</span></span>

### <a name="submit-feedback-via-office-customer-voice"></a><span data-ttu-id="01582-212">Office のお客様の声でフィードバックを送信する</span><span class="sxs-lookup"><span data-stu-id="01582-212">Submit feedback via Office Customer Voice</span></span>

<span data-ttu-id="01582-213">Office ドキュメントを Application Guard で開いたときに問題が発生した場合は、Office からフィードバックを送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="01582-213">You may also submit feedback from within Office if the issue happens when Office documents are opened in Application Guard.</span></span> <span data-ttu-id="01582-214">フィードバックを送信するには、「 [Office Insider ハンドブック](https://insider.office.com/handbook) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01582-214">Refer to the [Office Insider Handbook](https://insider.office.com/handbook) for submitting feedback.</span></span>

## <a name="integration-with-microsoft-defender-for-endpoint-and-microsoft-defender-for-office-365"></a><span data-ttu-id="01582-215">エンドポイントと microsoft Defender for Office 365 の統合</span><span class="sxs-lookup"><span data-stu-id="01582-215">Integration with Microsoft Defender for Endpoint and Microsoft Defender for Office 365</span></span>

<span data-ttu-id="01582-216">Office 用 Application Guard は、エンドポイントの Microsoft Defender と統合されており、分離された環境で発生した悪意のあるアクティビティについての監視と警告を提供します。</span><span class="sxs-lookup"><span data-stu-id="01582-216">Application Guard for Office is integrated with Microsoft Defender for Endpoint to provide monitoring and alerting on malicious activity happening in the isolated environment.</span></span>

<span data-ttu-id="01582-217">エンドポイント用 Microsoft Defender は、企業ネットワークによる、高度な脅威の防止、検出、調査、応答を支援するように設計されたセキュリティプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="01582-217">Microsoft Defender for Endpoint is a security platform designed to help enterprise networks prevent, detect, investigate, and respond to advanced threats.</span></span> <span data-ttu-id="01582-218">このプラットフォームの詳細については、「 [エンドポイントの Microsoft Defender](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp) 」ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="01582-218">For more details about this platform, visit the [Microsoft Defender for Endpoint](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp) page.</span></span> <span data-ttu-id="01582-219">エンドポイントデバイスのこのプラットフォームへのオンボードデバイスの詳細について [は、「Microsoft Defender For Endpoint service」を](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure)参照してください。</span><span class="sxs-lookup"><span data-stu-id="01582-219">Learn more about onboarding devices to this platform at [Onboard devices to the Microsoft Defender for Endpoint service](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure).</span></span>

<span data-ttu-id="01582-220">エンドポイントの Defender と連携するように Microsoft Defender for Office 365 を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="01582-220">You can also configure Microsoft Defender for Office 365 to work with Defender for Endpoint.</span></span> <span data-ttu-id="01582-221">[エンドポイントに Microsoft defender を使用した Office 365 の統合 Defender](integrate-office-365-ti-with-wdatp.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01582-221">Refer to [Integrate Defender for Office 365 with Microsoft Defender for Endpoint](integrate-office-365-ti-with-wdatp.md).</span></span>

## <a name="limitations-and-considerations"></a><span data-ttu-id="01582-222">制限事項と考慮事項</span><span class="sxs-lookup"><span data-stu-id="01582-222">Limitations and considerations</span></span>

* <span data-ttu-id="01582-223">Office の Application Guard は、信頼されていないドキュメントを分離して、信頼された企業リソース、イントラネット、ユーザーの id、およびコンピューター上に存在する任意のファイルにアクセスする制限モードです。</span><span class="sxs-lookup"><span data-stu-id="01582-223">Application Guard for Office is a restricted mode that isolates untrusted documents from accessing trusted corporate resources, intranet, the user's identity, and arbitrary files present on the computer.</span></span> <span data-ttu-id="01582-224">そのため、ユーザーがそのようなアクセスに依存している機能にアクセスしようとすると、たとえば、ディスク上のローカルファイルから画像を挿入しようとしたときに、エラーが発生し、次のようなプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="01582-224">As a result, if a user tries to access a feature that has a dependency on such access, for example, inserting a picture from a local file on disk, it will fail and produce a prompt like the one below.</span></span> <span data-ttu-id="01582-225">信頼されていないドキュメントが信頼できるリソースにアクセスできるようにするには、ユーザーはドキュメントから Application Guard protection を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01582-225">To enable an untrusted document to access trusted resources, users must remove Application Guard protection from the document.</span></span>

  ![安全な状態を維持するためのダイアログボックスこの機能は使用できません](../../media/ag10-limitations.png)

  > [!NOTE]
  > <span data-ttu-id="01582-227">ファイルとそのソースまたはそのソースが信頼されている場合にのみ保護を解除するようにユーザーにアドバイスします。</span><span class="sxs-lookup"><span data-stu-id="01582-227">Advise users to only remove protection if they trust the file and its source or where it came from.</span></span>

* <span data-ttu-id="01582-228">Application Guard for Office では、マクロや ActiveX コントロールなどのドキュメント内のアクティブコンテンツは無効になります。</span><span class="sxs-lookup"><span data-stu-id="01582-228">Active content in documents like macros and ActiveX controls are disabled in Application Guard for Office.</span></span> <span data-ttu-id="01582-229">ユーザーは、active コンテンツを有効にするために Application Guard protection を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01582-229">Users need to remove Application Guard protection to enable active content.</span></span>

* <span data-ttu-id="01582-230">ネットワーク共有または OneDrive、OneDrive for Business、または別の組織から共有されているファイルから開かれた信頼されていないファイルは、Application Guard で読み取り専用として開きます。</span><span class="sxs-lookup"><span data-stu-id="01582-230">Untrusted files opened from network shares or files shared from OneDrive, OneDrive for Business, or SharePoint Online from a different organization open as read-only in Application Guard.</span></span> <span data-ttu-id="01582-231">ユーザーは、そのようなファイルのローカルコピーを保存して、コンテナーで作業を続けたり、保護を解除して元のファイルを直接操作したりできます。</span><span class="sxs-lookup"><span data-stu-id="01582-231">Users can save a local copy of such files to continue working in the container or remove protection to directly work with the original file.</span></span>

* <span data-ttu-id="01582-232">Information Rights Management (IRM) で保護されているファイルは、引き続き保護されたビューで開きます。</span><span class="sxs-lookup"><span data-stu-id="01582-232">Files that are protected by Information Rights Management (IRM) continue to open in Protected View.</span></span>

* <span data-ttu-id="01582-233">Application Guard for Office の Office アプリケーションに対するカスタマイズは、ユーザーがログオフし、デバイスを再度ログインまたは再起動した後に保持されません。</span><span class="sxs-lookup"><span data-stu-id="01582-233">Any customizations to Office applications in Application Guard for Office will not persist after a user logs off and logs back in or reboots the device.</span></span>

* <span data-ttu-id="01582-234">UIA framework を使用するアクセシビリティツールのみが、Application Guard for Office で開かれたファイルにアクセスできる操作を提供できます。</span><span class="sxs-lookup"><span data-stu-id="01582-234">Only Accessibility tools that use the UIA framework can provide an accessible experience for files opened in Application Guard for Office.</span></span>

* <span data-ttu-id="01582-235">インストール後に Application Guard を最初に起動するには、ネットワーク接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="01582-235">Network connectivity is required for the first launch of Application Guard after installation.</span></span> <span data-ttu-id="01582-236">これは、Application Guard がライセンスを検証するために必要です。</span><span class="sxs-lookup"><span data-stu-id="01582-236">This is required for Application Guard to validate the license.</span></span>

* <span data-ttu-id="01582-237">ドキュメントの [情報] セクションの [ *最終更新者* ] プロパティには、ユーザーとして Wdagutility アカウントが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="01582-237">In the document's info section, the *Last Modified By* property may display WDAGUtilityAccount as the user.</span></span> <span data-ttu-id="01582-238">これは、デスクトップユーザーの id が Application Guard コンテナー内で共有されていない場合に、Application Guard で構成された匿名ユーザーです。</span><span class="sxs-lookup"><span data-stu-id="01582-238">This is the anonymous user configured in Application Guard given that the desktop user's identity is not shared inside the Application Guard container.</span></span>

## <a name="performance-optimizations-for-application-guard"></a><span data-ttu-id="01582-239">Application Guard のパフォーマンスの最適化</span><span class="sxs-lookup"><span data-stu-id="01582-239">Performance optimizations for Application Guard</span></span>

<span data-ttu-id="01582-240">このセクションでは、Office 用 Application Guard で使用されるパフォーマンス最適化の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="01582-240">This section provides an overview of the performance optimizations used in Application Guard for Office.</span></span> <span data-ttu-id="01582-241">この情報は、Application Guard が有効になっている場合に、Office またはシステム全体のパフォーマンスに関連するユーザーからレポートを診断するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="01582-241">This information can help administrators diagnose reports from users related to the performance of Office or the overall system when Application Guard is enabled.</span></span>

<span data-ttu-id="01582-242">Application Guard は、仮想化されたコンテナーを使用して、信頼されていないドキュメントをシステムから分離します。</span><span class="sxs-lookup"><span data-stu-id="01582-242">Application Guard uses a virtualized container to isolate untrusted documents away from the system.</span></span> <span data-ttu-id="01582-243">コンテナーを作成し、Application Guard コンテナーを設定して Office ドキュメントを開くプロセスでは、ユーザーが信頼されていないドキュメントを開くときに、ユーザーの操作に悪影響を及ぼす可能性のあるパフォーマンスオーバーヘッドが発生します。</span><span class="sxs-lookup"><span data-stu-id="01582-243">The process of creating a container and setting up the Application Guard container to open Office documents has a performance overhead that might negatively impact user experience when users open an  untrusted document.</span></span>

<span data-ttu-id="01582-244">アプリケーションガードは、予想されるファイルを開く操作をユーザーに提供するために、ロジックを使用して、次のヒューリスティックがシステムで満たされている場合に、コンテナーを事前に作成します。ユーザーが過去28日間に、保護ビューまたは Application Guard のいずれかでファイルを開いた。</span><span class="sxs-lookup"><span data-stu-id="01582-244">To provide users with the expected file opening experience, Application Guard uses logic to pre-create a container when the following heuristic is met on a system: A user has opened a file in either Protected View or Application Guard in the past 28 days.</span></span>

<span data-ttu-id="01582-245">このヒューリスティックが満たされている場合、Office は Windows にログインした後に、ユーザーの Application Guard コンテナーを事前に作成します。</span><span class="sxs-lookup"><span data-stu-id="01582-245">When this heuristic is met, Office will pre-create an Application Guard container for the user after they log in to Windows.</span></span> <span data-ttu-id="01582-246">この作成前操作が進行中の場合、システムのパフォーマンスが低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="01582-246">When this pre-create operation is in progress, the system may experience slow performance.</span></span> <span data-ttu-id="01582-247">操作が完了すると、これはすぐに解決されます。</span><span class="sxs-lookup"><span data-stu-id="01582-247">This will resolve as soon as the operation completes.</span></span>

> [!NOTE]
> <span data-ttu-id="01582-248">コンテナーを事前に作成するために使用されるヒューリスティックに必要なヒントは、ユーザーが Office アプリケーションを使用しているときに生成されます。</span><span class="sxs-lookup"><span data-stu-id="01582-248">The hints needed for the heuristic used to pre-create the container are generated by Office applications as a user uses them.</span></span> <span data-ttu-id="01582-249">ユーザーが、Application Guard が有効になっている新しいシステムに Office をインストールした場合、Office は、ユーザーがシステム上で信頼されていないドキュメントを初めて開いたときまで、コンテナーを事前に作成しません。</span><span class="sxs-lookup"><span data-stu-id="01582-249">If a user installs Office on a new system where Application Guard is enabled, Office will not pre-create the container until after the first time a user opens an untrusted document on the system.</span></span> <span data-ttu-id="01582-250">この最初のファイルは Application Guard で開くのに時間がかかることをユーザーに確認します。</span><span class="sxs-lookup"><span data-stu-id="01582-250">The user will observe that this first file takes longer to open in Application Guard.</span></span>

## <a name="known-issues-in-preview"></a><span data-ttu-id="01582-251">プレビューでの既知の問題</span><span class="sxs-lookup"><span data-stu-id="01582-251">Known issues in preview</span></span>

* <span data-ttu-id="01582-252">[Web リンク] を `http` クリック `https` しても、ブラウザーは開きません。</span><span class="sxs-lookup"><span data-stu-id="01582-252">Clicking on web links (`http` or `https`) does not open the browser.</span></span>
* <span data-ttu-id="01582-253">.NET の更新により、Application Guard でファイルが開くことができなくなります。</span><span class="sxs-lookup"><span data-stu-id="01582-253">.NET updates cause files to fail to open in Application Guard.</span></span> <span data-ttu-id="01582-254">回避策として、この問題が発生したときにユーザーがデバイスを再起動することができます。</span><span class="sxs-lookup"><span data-stu-id="01582-254">As a workaround, users can reboot their device when this issue is encountered.</span></span> <span data-ttu-id="01582-255">[Windows Defender Application Guard または Windows サンドボックスを開こうとすると、エラーメッセージが表示](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap)される問題の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="01582-255">Learn more about the issue at [Receiving an error message when attempting to open Windows Defender Application Guard or Windows Sandbox](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap).</span></span>
