---
title: Microsoft Defender ATP for Mac - システム拡張機能 (プレビュー)
description: この記事では、Microsoft Defender ATP for Mac のシステム拡張機能の機能を試す手順について説明します。 この機能は現在パブリック プレビュー中です。
keywords: microsoft, defender, atp, mac, kernel, system, extensions, catalina
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ROBOTS: noindex,nofollow
ms.technology: mde
ms.openlocfilehash: 8b644e27c5a36d2175ab18ae92424e7c70f39d0f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062228"
---
# <a name="microsoft-defender-for-endpoint-for-mac---system-extensions-public-preview"></a><span data-ttu-id="912a3-105">Microsoft Defender for Endpoint for Mac - システム拡張機能のパブリック プレビュー)</span><span class="sxs-lookup"><span data-stu-id="912a3-105">Microsoft Defender for Endpoint for Mac - system extensions public preview)</span></span>

<span data-ttu-id="912a3-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="912a3-106">**Applies to:**</span></span>
- [<span data-ttu-id="912a3-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="912a3-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="912a3-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="912a3-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="912a3-109">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="912a3-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="912a3-110">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="912a3-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="912a3-111">macOS の進化に合わせ、カーネル拡張機能ではなくシステム拡張機能を活用する Defender for Endpoint for Mac 更新プログラムを準備しています。</span><span class="sxs-lookup"><span data-stu-id="912a3-111">In alignment with macOS evolution, we are preparing a Defender for Endpoint for Mac update that leverages system extensions instead of kernel extensions.</span></span> <span data-ttu-id="912a3-112">この更新プログラムは、macOS Catalina (10.15.4) 以降のバージョンの macOS にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="912a3-112">This update will only apply to macOS Catalina (10.15.4) and later versions of macOS.</span></span>

<span data-ttu-id="912a3-113">この機能は現在パブリック プレビュー中です。</span><span class="sxs-lookup"><span data-stu-id="912a3-113">This functionality is currently in public preview.</span></span> <span data-ttu-id="912a3-114">この記事では、デバイスでこの機能を有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="912a3-114">This article describes how to enable this functionality on your device.</span></span> <span data-ttu-id="912a3-115">この機能は、独自のデバイスでローカルで試したり、管理ツールを使用してリモートで構成することができます。</span><span class="sxs-lookup"><span data-stu-id="912a3-115">You can try out this feature locally on your own device or configure it remotely through a management tool.</span></span>

<span data-ttu-id="912a3-116">これらの手順では、デバイスで Defender for Endpoint が既に実行済みである必要があります。</span><span class="sxs-lookup"><span data-stu-id="912a3-116">These steps assume you already have Defender for Endpoint running on your device.</span></span> <span data-ttu-id="912a3-117">詳細については、「[このページ](microsoft-defender-endpoint-mac.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="912a3-117">For more information, see [this page](microsoft-defender-endpoint-mac.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="912a3-118">既知の問題</span><span class="sxs-lookup"><span data-stu-id="912a3-118">Known issues</span></span>

- <span data-ttu-id="912a3-119">ネットワーク拡張機能が Apple SSO Kerberos 拡張機能に干渉しているという報告を受け取っています。</span><span class="sxs-lookup"><span data-stu-id="912a3-119">We’ve received reports of the network extension interfering with the Apple SSO Kerberos extension.</span></span>
- <span data-ttu-id="912a3-120">製品の現在のバージョンでは、カーネル拡張機能がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="912a3-120">The current version of the product still installs a kernel extension.</span></span> <span data-ttu-id="912a3-121">カーネル拡張機能はフォールバック メカニズムとしてのみ使用され、この機能がパブリック プレビューに達する前に削除されます。</span><span class="sxs-lookup"><span data-stu-id="912a3-121">The kernel extension is only used as a fallback mechanism and will be removed before this feature reaches public preview.</span></span>
- <span data-ttu-id="912a3-122">現在も、macOS 11 Big Sur で適切に展開および機能する製品バージョンに取り組まれています。</span><span class="sxs-lookup"><span data-stu-id="912a3-122">We're still working on a product version that deploys and functions properly on macOS 11 Big Sur.</span></span>

## <a name="deployment-prerequisites"></a><span data-ttu-id="912a3-123">展開の前提条件</span><span class="sxs-lookup"><span data-stu-id="912a3-123">Deployment prerequisites</span></span>

- <span data-ttu-id="912a3-124">macOS オペレーティング システムの最小バージョン: **10.15.4**</span><span class="sxs-lookup"><span data-stu-id="912a3-124">Minimum macOS operating system version: **10.15.4**</span></span>
- <span data-ttu-id="912a3-125">最小製品バージョン: **101.03.73**</span><span class="sxs-lookup"><span data-stu-id="912a3-125">Minimum product version: **101.03.73**</span></span>
- <span data-ttu-id="912a3-126">デバイスが Insider Fast 更新チャネル **にある必要があります**。</span><span class="sxs-lookup"><span data-stu-id="912a3-126">Your device must be in the **Insider Fast update channel**.</span></span> <span data-ttu-id="912a3-127">次のコマンドを使用して更新チャネルを確認できます。</span><span class="sxs-lookup"><span data-stu-id="912a3-127">You can check the update channel by using the following command:</span></span>

  ```bash
  mdatp health --field release_ring
  ```

  <span data-ttu-id="912a3-128">デバイスが Insider Fast 更新チャネルにまだ存在しない場合は、ターミナルから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="912a3-128">If your device isn't already in the Insider Fast update channel, execute the following command from the Terminal.</span></span> <span data-ttu-id="912a3-129">チャネル更新プログラムは、次に製品を起動するときに有効になります (次の製品更新プログラムがインストールされている場合、またはデバイスが再起動された場合)。</span><span class="sxs-lookup"><span data-stu-id="912a3-129">The channel update takes effect the next time the product starts (when the next product update is installed, or when the device is rebooted).</span></span>

  ```bash
  defaults write com.microsoft.autoupdate2 ChannelName -string Beta
  ```

  <span data-ttu-id="912a3-130">または、管理環境 (JAMF または Intune) を使用している場合は、更新プログラム チャネルをリモートで構成できます。</span><span class="sxs-lookup"><span data-stu-id="912a3-130">Alternatively, if you're in a managed environment (JAMF or Intune), you can configure the update channel remotely.</span></span> <span data-ttu-id="912a3-131">詳細については [、「Deploy updates for Microsoft Defender ATP for Mac: Set the channel name 」を参照してください](mac-updates.md#set-the-channel-name)。</span><span class="sxs-lookup"><span data-stu-id="912a3-131">For more information, see [Deploy updates for Microsoft Defender ATP for Mac: Set the channel name](mac-updates.md#set-the-channel-name).</span></span>

## <a name="deployment-steps"></a><span data-ttu-id="912a3-132">展開手順</span><span class="sxs-lookup"><span data-stu-id="912a3-132">Deployment steps</span></span>

<span data-ttu-id="912a3-133">環境に対応する展開手順と、この機能を試す方法に従います。</span><span class="sxs-lookup"><span data-stu-id="912a3-133">Follow the deployment steps that correspond to your environment and your preferred method of trying out this feature.</span></span>

### <a name="manual-deployment"></a><span data-ttu-id="912a3-134">手動展開</span><span class="sxs-lookup"><span data-stu-id="912a3-134">Manual deployment</span></span>

#### <a name="approve-the-system-extensions-and-enable-the-network-extension"></a><span data-ttu-id="912a3-135">システム拡張機能を承認し、ネットワーク拡張機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="912a3-135">Approve the system extensions and enable the network extension</span></span>

1. <span data-ttu-id="912a3-136">すべての展開の前提条件が満たされた後、デバイスを再起動して、システム拡張の承認とライセンス認証プロセスを起動します。</span><span class="sxs-lookup"><span data-stu-id="912a3-136">After all deployment prerequisites are met, restart your device to launch the system extension approval and activation process.</span></span>

   <span data-ttu-id="912a3-137">Defender for Endpoint システム拡張機能を承認する一連のシステム プロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="912a3-137">You'll see a series of system prompts to approve the Defender for Endpoint system extensions.</span></span> <span data-ttu-id="912a3-138">シリーズのすべてのプロンプト **を** 承認する必要があります。macOS では、Defender for Endpoint for Mac がデバイスにインストールする拡張機能ごとに明示的な承認が必要です。</span><span class="sxs-lookup"><span data-stu-id="912a3-138">You must approve **all** prompts from the series, because macOS requires an explicit approval for each extension that Defender for Endpoint for Mac installs on the device.</span></span>
   
   <span data-ttu-id="912a3-139">承認ごとに、[Open **Security Preferences]** を選択し、[許可] を選択してシステム拡張機能の実行を許可します。</span><span class="sxs-lookup"><span data-stu-id="912a3-139">For each approval, select **Open Security Preferences** and then select **Allow** to allow the system extension to run.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="912a3-140">後続の承認の間に **、[System Preferences**  >  **Security] ウィンドウを閉じて&再度** 開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="912a3-140">You must close and reopen the **System Preferences** > **Security & Privacy** window between subsequent approvals.</span></span> <span data-ttu-id="912a3-141">それ以外の場合、macOS では次の承認は表示されません。</span><span class="sxs-lookup"><span data-stu-id="912a3-141">Otherwise, macOS will not display the next approval.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="912a3-142">製品がカーネル拡張機能に戻る前に 1 分のタイムアウトがあります。</span><span class="sxs-lookup"><span data-stu-id="912a3-142">There is a one-minute timeout before the product falls back to the kernel extension.</span></span> <span data-ttu-id="912a3-143">これにより、デバイスが保護されます。</span><span class="sxs-lookup"><span data-stu-id="912a3-143">This ensures that the device is protected.</span></span>
   >
   > <span data-ttu-id="912a3-144">1 分以上経過した場合は、デバイスを再起動するか、承認フローを再度トリガーするために使用してデーモン `sudo killall -9 wdavdaemon` を再起動します。</span><span class="sxs-lookup"><span data-stu-id="912a3-144">If more than one minute elapses, restart the daemon by rebooting the device or by using `sudo killall -9 wdavdaemon` to trigger the approval flow again.</span></span>

   ![システム拡張機能の承認ポップアップ](images/mac-system-extension-approval.png)

   ![システム拡張機能の承認ウィンドウ](images/mac-system-extension-pref.png)

1. <span data-ttu-id="912a3-147">システム拡張機能が承認されると、macOS はネットワーク トラフィックのフィルター処理を許可する承認を求めるメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="912a3-147">After the system extensions are approved, macOS prompts for an approval to allow network traffic to be filtered.</span></span> <span data-ttu-id="912a3-148">**[許可]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="912a3-148">Click **Allow**.</span></span>

   ![ネットワーク拡張機能の承認ポップアップ](images/mac-system-extension-filter.png)

#### <a name="grant-full-disk-access-to-the-endpoint-security-system-extension"></a><span data-ttu-id="912a3-150">エンドポイント セキュリティ システム拡張機能へのフル ディスク アクセスの付与</span><span class="sxs-lookup"><span data-stu-id="912a3-150">Grant Full Disk Access to the Endpoint Security system extension</span></span>

<span data-ttu-id="912a3-151">[System **Preferences** Security &プライバシー] タブを開き、Microsoft Defender Endpoint Security Extension へのフル ディスク アクセス  >    >  **を許可します**。 </span><span class="sxs-lookup"><span data-stu-id="912a3-151">Open the **System Preferences** > **Security & Privacy** > **Privacy** tab and grant **Full Disk Access** to the **Microsoft Defender Endpoint Security Extension**.</span></span>

![Endpoint Security システム拡張機能の完全なディスク アクセス](images/mac-system-extension-fda.png)

#### <a name="reboot-your-device"></a><span data-ttu-id="912a3-153">デバイスを再起動する</span><span class="sxs-lookup"><span data-stu-id="912a3-153">Reboot your device</span></span>

<span data-ttu-id="912a3-154">変更を有効にするには、デバイスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="912a3-154">In order for the changes to take effect, you must reboot your device.</span></span>

#### <a name="verify-that-the-system-extensions-are-running"></a><span data-ttu-id="912a3-155">システム拡張機能が実行されているのを確認する</span><span class="sxs-lookup"><span data-stu-id="912a3-155">Verify that the system extensions are running</span></span>

<span data-ttu-id="912a3-156">ターミナルから、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="912a3-156">From the Terminal, run the following command:</span></span>

```bash
mdatp health --field real_time_protection_subsystem
```

<span data-ttu-id="912a3-157">ターミナル出力 `endpoint_security_extension` は、製品がシステム拡張機能機能を使用している状態を示します。</span><span class="sxs-lookup"><span data-stu-id="912a3-157">Terminal output `endpoint_security_extension` indicates the product is using the system extensions functionality.</span></span>

### <a name="managed-deployment"></a><span data-ttu-id="912a3-158">管理された展開</span><span class="sxs-lookup"><span data-stu-id="912a3-158">Managed deployment</span></span>

<span data-ttu-id="912a3-159">この新機能のために展開する必要がある新しい構成プロファイルについては、「macOS Catalina および新しいバージョンの [macOS: JAMF」](mac-sysext-policies.md#jamf) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="912a3-159">Refer to [New configuration profiles for macOS Catalina and newer versions of macOS: JAMF](mac-sysext-policies.md#jamf) for the new configuration profiles you must deploy for this new feature.</span></span>

<span data-ttu-id="912a3-160">これらのプロファイルに加えて、「展開の前提条件」の説明に従って、ターゲット デバイスを Insider Fast update チャネルに配置するように [構成してください](#deployment-prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="912a3-160">In addition to those profiles, make sure to configure the target devices to be in the Insider Fast update channel, as described in [Deployment prerequisites](#deployment-prerequisites).</span></span>

<span data-ttu-id="912a3-161">すべての前提条件が満たされ、新しい構成プロファイルが展開されているデバイスで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="912a3-161">On a device where all prerequisites are met and the new configuration profiles have been deployed, run the following command:</span></span>

```bash
$ mdatp health --field real_time_protection_subsystem
```

<span data-ttu-id="912a3-162">このコマンドが印刷される `endpoint_security_extension` 場合、製品はシステム拡張機能の機能を使用しています。</span><span class="sxs-lookup"><span data-stu-id="912a3-162">If this command prints `endpoint_security_extension`, the product is using the system extensions functionality.</span></span>

## <a name="validate-basic-scenarios"></a><span data-ttu-id="912a3-163">基本的なシナリオの検証</span><span class="sxs-lookup"><span data-stu-id="912a3-163">Validate basic scenarios</span></span>

1. <span data-ttu-id="912a3-164">ヨーロッパコンピューターウイルス対策研究所 (EICAR) の検出をテストします。</span><span class="sxs-lookup"><span data-stu-id="912a3-164">Test European Institute for Computer Antivirus Research (EICAR) detection.</span></span> <span data-ttu-id="912a3-165">ターミナル ウィンドウで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="912a3-165">From a Terminal window, run the following command:</span></span>

   ```bash
   curl -o eicar.txt https://secure.eicar.org/eicar.com.txt
   ```

   <span data-ttu-id="912a3-166">EICAR ファイルが検疫済みである必要があります。</span><span class="sxs-lookup"><span data-stu-id="912a3-166">Verify that the EICAR file is quarantined.</span></span> <span data-ttu-id="912a3-167">次のコマンドを使用して、ユーザー インターフェイスの [保護履歴] ページまたはコマンド ラインからファイルの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="912a3-167">You can verify the file's status on the Protection History page in the user interface, or from a command line by using the following command:</span></span>

    ```bash
    mdatp threat list
    ```

2. <span data-ttu-id="912a3-168">エンドポイント検出と応答 (EDR) DIY シナリオをテストします。</span><span class="sxs-lookup"><span data-stu-id="912a3-168">Test the Endpoint Detection and Response (EDR) DIY scenario.</span></span> <span data-ttu-id="912a3-169">ターミナル ウィンドウから、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="912a3-169">From a terminal window, run the following command:</span></span>

   ```bash
   curl -o "MDATP MacOS DIY.zip" https://aka.ms/mdatpmacosdiy
   ```

   <span data-ttu-id="912a3-170">EICAR および EDR DIY シナリオのコンピューター ページのポータルに 2 つのアラートがポップアップしたと検証します。</span><span class="sxs-lookup"><span data-stu-id="912a3-170">Validate that two alerts popped up in the portal on the machine page for EICAR and EDR DIY scenarios.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="912a3-171">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="912a3-171">Frequently asked questions</span></span>

- <span data-ttu-id="912a3-172">Q: 実行するときにまだ表示 `kernel_extension` される理由 `mdatp health --field real_time_protection_subsystem` は何ですか?</span><span class="sxs-lookup"><span data-stu-id="912a3-172">Q: Why am I still seeing `kernel_extension` when I run `mdatp health --field real_time_protection_subsystem`?</span></span>

    <span data-ttu-id="912a3-173">A: [展開の前提条件] [セクションを](#deployment-prerequisites) 参照し、すべての前提条件が満たされていることをもう一度確認します。</span><span class="sxs-lookup"><span data-stu-id="912a3-173">A: Refer back to the [Deployment prerequisites](#deployment-prerequisites) section and double-check that all prerequisites are met.</span></span> <span data-ttu-id="912a3-174">すべての前提条件が満たされている場合は、デバイスを再起動し、もう一度確認します。</span><span class="sxs-lookup"><span data-stu-id="912a3-174">If all prerequisites are met, restart your device and check again.</span></span>

- <span data-ttu-id="912a3-175">Q: macOS 11 Big Sur がサポートされるのは、いつですか?</span><span class="sxs-lookup"><span data-stu-id="912a3-175">Q: When will macOS 11 Big Sur be supported?</span></span>

    <span data-ttu-id="912a3-176">A: macOS 11 のサポートの追加に積極的に取り組む予定です。</span><span class="sxs-lookup"><span data-stu-id="912a3-176">A: We are actively working on adding support for macOS 11.</span></span> <span data-ttu-id="912a3-177">詳細については、[新しい情報 [] ページに投稿](mac-whatsnew.md) します。</span><span class="sxs-lookup"><span data-stu-id="912a3-177">We will post more information to the [What's new](mac-whatsnew.md) page.</span></span>
