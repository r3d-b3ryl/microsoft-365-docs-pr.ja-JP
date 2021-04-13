---
title: Microsoft Defender ATP for Mac の更新プログラムを展開する
description: エンタープライズ環境での Microsoft Defender ATP for Mac の更新プログラムを制御します。
keywords: microsoft、Defender、atp、mac、更新プログラム、展開
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
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
ms.technology: mde
ms.openlocfilehash: 3321c1bd181b89c53e2618fc20fa7f733a20cfc1
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689055"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="d3054-104">macOS で Microsoft Defender for Endpoint の更新プログラムを展開する</span><span class="sxs-lookup"><span data-stu-id="d3054-104">Deploy updates for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d3054-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="d3054-105">**Applies to:**</span></span>

- [<span data-ttu-id="d3054-106">macOS 上のエンドポイント用 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d3054-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="d3054-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d3054-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d3054-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d3054-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d3054-109">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="d3054-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d3054-110">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="d3054-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="d3054-111">Microsoft は、パフォーマンス、セキュリティ、および新機能の提供を行うソフトウェア更新プログラムを定期的に発行しています。</span><span class="sxs-lookup"><span data-stu-id="d3054-111">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

<span data-ttu-id="d3054-112">macOS のエンドポイント用 Microsoft Defender を更新するには、Microsoft AutoUpdate (MAU) という名前のプログラムが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d3054-112">To update Microsoft Defender for Endpoint on macOS, a program named Microsoft AutoUpdate (MAU) is used.</span></span> <span data-ttu-id="d3054-113">既定では、MAU は更新プログラムを毎日自動的にチェックしますが、毎週、月次、または手動に変更できます。</span><span class="sxs-lookup"><span data-stu-id="d3054-113">By default, MAU automatically checks for updates daily, but you can change that to weekly, monthly, or manually.</span></span>

![MAU のスクリーンショット](images/MDATP-34-MAU.png)

<span data-ttu-id="d3054-115">ソフトウェア配布ツールを使用して更新プログラムを展開する場合は、ソフトウェア更新プログラムを手動で確認する MAU を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3054-115">If you decide to deploy updates by using your software distribution tools, you should configure MAU to manually check for software updates.</span></span> <span data-ttu-id="d3054-116">組織の Mac の更新プログラムを MAU がチェックする方法と時間を構成する基本設定を展開できます。</span><span class="sxs-lookup"><span data-stu-id="d3054-116">You can deploy preferences to configure how and when MAU checks for updates for the Macs in your organization.</span></span>

## <a name="use-msupdate"></a><span data-ttu-id="d3054-117">Msupdate の使用</span><span class="sxs-lookup"><span data-stu-id="d3054-117">Use msupdate</span></span>

<span data-ttu-id="d3054-118">MAU には *msupdate* と呼ばれるコマンド ライン ツールが含まれています。このツールは、IT 管理者向けに設計され、更新プログラムの適用時間を正確に制御できます。</span><span class="sxs-lookup"><span data-stu-id="d3054-118">MAU includes a command-line tool, called *msupdate*, that is designed for IT administrators so that they have more precise control over when updates are applied.</span></span> <span data-ttu-id="d3054-119">このツールの使い方については、「msupdate を使用した更新プログラムOffice for Mac [を参照してください](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate)。</span><span class="sxs-lookup"><span data-stu-id="d3054-119">Instructions for how to use this tool can be found in [Update Office for Mac by using msupdate](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate).</span></span>

<span data-ttu-id="d3054-120">MAU では、macOS 上のエンドポイント用 Microsoft Defender のアプリケーション識別子は *WDAV00 です*。</span><span class="sxs-lookup"><span data-stu-id="d3054-120">In MAU, the application identifier for Microsoft Defender for Endpoint on macOS is *WDAV00*.</span></span> <span data-ttu-id="d3054-121">macOS の Microsoft Defender for Endpoint の最新の更新プログラムをダウンロードしてインストールするには、ターミナル ウィンドウから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d3054-121">To download and install the latest updates for Microsoft Defender for Endpoint on macOS, execute the following command from a Terminal window:</span></span>

```
./msupdate --install --apps wdav00
```

## <a name="set-preferences-for-microsoft-autoupdate"></a><span data-ttu-id="d3054-122">Microsoft AutoUpdate の基本設定を設定する</span><span class="sxs-lookup"><span data-stu-id="d3054-122">Set preferences for Microsoft AutoUpdate</span></span>

<span data-ttu-id="d3054-123">このセクションでは、MAU の構成に使用できる最も一般的な基本設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="d3054-123">This section describes the most common preferences that can be used to configure MAU.</span></span> <span data-ttu-id="d3054-124">これらの設定は、企業が使用している管理コンソールを介して構成プロファイルとして展開できます。</span><span class="sxs-lookup"><span data-stu-id="d3054-124">These settings can be deployed as a configuration profile through the management console that your enterprise is using.</span></span> <span data-ttu-id="d3054-125">構成プロファイルの例を次のセクションに示します。</span><span class="sxs-lookup"><span data-stu-id="d3054-125">An example of a configuration profile is shown in the following sections.</span></span>

### <a name="set-the-channel-name"></a><span data-ttu-id="d3054-126">チャネル名を設定する</span><span class="sxs-lookup"><span data-stu-id="d3054-126">Set the channel name</span></span>

<span data-ttu-id="d3054-127">チャネルは、MAU を通じて提供される更新プログラムの種類と頻度を決定します。</span><span class="sxs-lookup"><span data-stu-id="d3054-127">The channel determines the type and frequency of updates that are offered through MAU.</span></span> <span data-ttu-id="d3054-128">デバイスは `Beta` 、デバイスの前に新しい機能を試 `Preview` し `Current` 、.</span><span class="sxs-lookup"><span data-stu-id="d3054-128">Devices in `Beta` can try out new features before devices in `Preview` and `Current`.</span></span> 

<span data-ttu-id="d3054-129">チャネル `Current` には、製品の最も安定したバージョンが含まれている。</span><span class="sxs-lookup"><span data-stu-id="d3054-129">The `Current` channel contains the most stable version of the product.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="d3054-130">Microsoft AutoUpdate バージョン 4.29 より前のチャネルの名前は異なります。</span><span class="sxs-lookup"><span data-stu-id="d3054-130">Prior to Microsoft AutoUpdate version 4.29, channels had different names:</span></span> 
> 
> - <span data-ttu-id="d3054-131">`Beta` という名前 `InsiderFast` が付けられた (Insider Fast)</span><span class="sxs-lookup"><span data-stu-id="d3054-131">`Beta` was named `InsiderFast` (Insider Fast)</span></span>
> - <span data-ttu-id="d3054-132">`Preview` という名前 `External` が付けられた (Insider Slow)</span><span class="sxs-lookup"><span data-stu-id="d3054-132">`Preview` was named `External` (Insider Slow)</span></span>
> - <span data-ttu-id="d3054-133">`Current` という名前が付けられた `Production`</span><span class="sxs-lookup"><span data-stu-id="d3054-133">`Current` was named `Production`</span></span>

>[!TIP]
><span data-ttu-id="d3054-134">新機能をプレビューし、早期のフィードバックを提供するには、企業内の一部のデバイスを構成するか、またはに構成をお `Beta` 勧めします `Preview` 。</span><span class="sxs-lookup"><span data-stu-id="d3054-134">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to `Beta` or `Preview`.</span></span>

|<span data-ttu-id="d3054-135">Section</span><span class="sxs-lookup"><span data-stu-id="d3054-135">Section</span></span>|<span data-ttu-id="d3054-136">値</span><span class="sxs-lookup"><span data-stu-id="d3054-136">Value</span></span>|
|:--|:--|
| <span data-ttu-id="d3054-137">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="d3054-137">**Domain**</span></span> | <span data-ttu-id="d3054-138">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="d3054-138">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="d3054-139">**Key**</span><span class="sxs-lookup"><span data-stu-id="d3054-139">**Key**</span></span> | <span data-ttu-id="d3054-140">ChannelName</span><span class="sxs-lookup"><span data-stu-id="d3054-140">ChannelName</span></span> |
| <span data-ttu-id="d3054-141">**データ型**</span><span class="sxs-lookup"><span data-stu-id="d3054-141">**Data type**</span></span> | <span data-ttu-id="d3054-142">String</span><span class="sxs-lookup"><span data-stu-id="d3054-142">String</span></span> |
| <span data-ttu-id="d3054-143">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="d3054-143">**Possible values**</span></span> | <span data-ttu-id="d3054-144">ベータ版</span><span class="sxs-lookup"><span data-stu-id="d3054-144">Beta</span></span> <br/> <span data-ttu-id="d3054-145">Preview</span><span class="sxs-lookup"><span data-stu-id="d3054-145">Preview</span></span> <br/> <span data-ttu-id="d3054-146">Current</span><span class="sxs-lookup"><span data-stu-id="d3054-146">Current</span></span> |
|||

>[!WARNING]
><span data-ttu-id="d3054-147">この設定は、Microsoft AutoUpdate を通じて更新されるすべてのアプリケーションのチャネルを変更します。</span><span class="sxs-lookup"><span data-stu-id="d3054-147">This setting changes the channel for all applications that are updated through Microsoft AutoUpdate.</span></span> <span data-ttu-id="d3054-148">macOS 上の Microsoft Defender for Endpoint のチャネルのみを変更するには、目的のチャネルに置き換えた後、次のコマンド `[channel-name]` を実行します。</span><span class="sxs-lookup"><span data-stu-id="d3054-148">To change the channel only for Microsoft Defender for Endpoint on macOS, execute the following command after replacing `[channel-name]` with the desired channel:</span></span>
> ```bash
> defaults write com.microsoft.autoupdate2 Applications -dict-add "/Applications/Microsoft Defender ATP.app" " { 'Application ID' = 'WDAV00' ; 'App Domain' = 'com.microsoft.wdav' ; LCID = 1033 ; ChannelName = '[channel-name]' ; }"
> ```

### <a name="set-update-check-frequency"></a><span data-ttu-id="d3054-149">更新チェックの頻度を設定する</span><span class="sxs-lookup"><span data-stu-id="d3054-149">Set update check frequency</span></span>

<span data-ttu-id="d3054-150">MAU が更新プログラムを検索する頻度を変更します。</span><span class="sxs-lookup"><span data-stu-id="d3054-150">Change how often MAU searches for updates.</span></span>

|<span data-ttu-id="d3054-151">Section</span><span class="sxs-lookup"><span data-stu-id="d3054-151">Section</span></span>|<span data-ttu-id="d3054-152">値</span><span class="sxs-lookup"><span data-stu-id="d3054-152">Value</span></span>|
|:--|:--|
| <span data-ttu-id="d3054-153">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="d3054-153">**Domain**</span></span> | <span data-ttu-id="d3054-154">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="d3054-154">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="d3054-155">**Key**</span><span class="sxs-lookup"><span data-stu-id="d3054-155">**Key**</span></span> | <span data-ttu-id="d3054-156">UpdateCheckFrequency</span><span class="sxs-lookup"><span data-stu-id="d3054-156">UpdateCheckFrequency</span></span> |
| <span data-ttu-id="d3054-157">**データ型**</span><span class="sxs-lookup"><span data-stu-id="d3054-157">**Data type**</span></span> | <span data-ttu-id="d3054-158">整数</span><span class="sxs-lookup"><span data-stu-id="d3054-158">Integer</span></span> |
| <span data-ttu-id="d3054-159">**既定値**</span><span class="sxs-lookup"><span data-stu-id="d3054-159">**Default value**</span></span> | <span data-ttu-id="d3054-160">720 (分)</span><span class="sxs-lookup"><span data-stu-id="d3054-160">720 (minutes)</span></span> |
| <span data-ttu-id="d3054-161">**Comment**</span><span class="sxs-lookup"><span data-stu-id="d3054-161">**Comment**</span></span> | <span data-ttu-id="d3054-162">この値は分で設定されます。</span><span class="sxs-lookup"><span data-stu-id="d3054-162">This value is set in minutes.</span></span> |


### <a name="change-how-mau-interacts-with-updates"></a><span data-ttu-id="d3054-163">MAU と更新プログラムのやり取り方法を変更する</span><span class="sxs-lookup"><span data-stu-id="d3054-163">Change how MAU interacts with updates</span></span>

<span data-ttu-id="d3054-164">MAU が更新プログラムを検索する方法を変更します。</span><span class="sxs-lookup"><span data-stu-id="d3054-164">Change how MAU searches for updates.</span></span>

|<span data-ttu-id="d3054-165">Section</span><span class="sxs-lookup"><span data-stu-id="d3054-165">Section</span></span>|<span data-ttu-id="d3054-166">値</span><span class="sxs-lookup"><span data-stu-id="d3054-166">Value</span></span>|
|:--|:--|
| <span data-ttu-id="d3054-167">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="d3054-167">**Domain**</span></span> | <span data-ttu-id="d3054-168">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="d3054-168">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="d3054-169">**Key**</span><span class="sxs-lookup"><span data-stu-id="d3054-169">**Key**</span></span> | <span data-ttu-id="d3054-170">HowToCheck</span><span class="sxs-lookup"><span data-stu-id="d3054-170">HowToCheck</span></span> |
| <span data-ttu-id="d3054-171">**データ型**</span><span class="sxs-lookup"><span data-stu-id="d3054-171">**Data type**</span></span> | <span data-ttu-id="d3054-172">String</span><span class="sxs-lookup"><span data-stu-id="d3054-172">String</span></span> |
| <span data-ttu-id="d3054-173">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="d3054-173">**Possible values**</span></span> | <span data-ttu-id="d3054-174">手動</span><span class="sxs-lookup"><span data-stu-id="d3054-174">Manual</span></span> <br/> <span data-ttu-id="d3054-175">AutomaticCheck</span><span class="sxs-lookup"><span data-stu-id="d3054-175">AutomaticCheck</span></span> <br/> <span data-ttu-id="d3054-176">AutomaticDownload</span><span class="sxs-lookup"><span data-stu-id="d3054-176">AutomaticDownload</span></span> |
| <span data-ttu-id="d3054-177">**Comment**</span><span class="sxs-lookup"><span data-stu-id="d3054-177">**Comment**</span></span> |  <span data-ttu-id="d3054-178">AutomaticDownload はダウンロードを実行し、可能であればサイレント インストールします。</span><span class="sxs-lookup"><span data-stu-id="d3054-178">Note that AutomaticDownload will do a download and install silently if possible.</span></span> |


### <a name="change-whether-the-check-for-updates-button-is-enabled"></a><span data-ttu-id="d3054-179">[更新プログラムの確認] ボタンが有効になっているかどうかを変更する</span><span class="sxs-lookup"><span data-stu-id="d3054-179">Change whether the "Check for Updates" button is enabled</span></span>

<span data-ttu-id="d3054-180">ローカル ユーザーが Microsoft AutoUpdate ユーザー インターフェイスの [更新プログラムの確認] オプションをクリックできるかどうかを変更します。</span><span class="sxs-lookup"><span data-stu-id="d3054-180">Change whether local users will be able to click the "Check for Updates" option in the Microsoft AutoUpdate user interface.</span></span>

|<span data-ttu-id="d3054-181">Section</span><span class="sxs-lookup"><span data-stu-id="d3054-181">Section</span></span>|<span data-ttu-id="d3054-182">値</span><span class="sxs-lookup"><span data-stu-id="d3054-182">Value</span></span>|
|:--|:--|
| <span data-ttu-id="d3054-183">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="d3054-183">**Domain**</span></span> | <span data-ttu-id="d3054-184">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="d3054-184">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="d3054-185">**Key**</span><span class="sxs-lookup"><span data-stu-id="d3054-185">**Key**</span></span> | <span data-ttu-id="d3054-186">EnableCheckForUpdatesButton</span><span class="sxs-lookup"><span data-stu-id="d3054-186">EnableCheckForUpdatesButton</span></span> |
| <span data-ttu-id="d3054-187">**データ型**</span><span class="sxs-lookup"><span data-stu-id="d3054-187">**Data type**</span></span> | <span data-ttu-id="d3054-188">Boolean</span><span class="sxs-lookup"><span data-stu-id="d3054-188">Boolean</span></span> |
| <span data-ttu-id="d3054-189">**可能な値**</span><span class="sxs-lookup"><span data-stu-id="d3054-189">**Possible values**</span></span> | <span data-ttu-id="d3054-190">True (既定)</span><span class="sxs-lookup"><span data-stu-id="d3054-190">True (default)</span></span> <br/> <span data-ttu-id="d3054-191">False</span><span class="sxs-lookup"><span data-stu-id="d3054-191">False</span></span> |


### <a name="disable-insider-checkbox"></a><span data-ttu-id="d3054-192">Insider チェック ボックスを無効にする</span><span class="sxs-lookup"><span data-stu-id="d3054-192">Disable Insider checkbox</span></span>

<span data-ttu-id="d3054-193">true に設定すると、"Insider Program.Office参加" になります。チェックボックスが使用できない/ユーザーにグレー表示されます。</span><span class="sxs-lookup"><span data-stu-id="d3054-193">Set to true to make the "Join the Office Insider Program..." checkbox unavailable / greyed out to users.</span></span>

|<span data-ttu-id="d3054-194">Section</span><span class="sxs-lookup"><span data-stu-id="d3054-194">Section</span></span>|<span data-ttu-id="d3054-195">値</span><span class="sxs-lookup"><span data-stu-id="d3054-195">Value</span></span>|
|:--|:--|
| <span data-ttu-id="d3054-196">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="d3054-196">**Domain**</span></span> | <span data-ttu-id="d3054-197">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="d3054-197">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="d3054-198">**Key**</span><span class="sxs-lookup"><span data-stu-id="d3054-198">**Key**</span></span> | <span data-ttu-id="d3054-199">DisableInsiderCheckbox</span><span class="sxs-lookup"><span data-stu-id="d3054-199">DisableInsiderCheckbox</span></span> |
| <span data-ttu-id="d3054-200">**データ型**</span><span class="sxs-lookup"><span data-stu-id="d3054-200">**Data type**</span></span> | <span data-ttu-id="d3054-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="d3054-201">Boolean</span></span> |
| <span data-ttu-id="d3054-202">**可能な値**</span><span class="sxs-lookup"><span data-stu-id="d3054-202">**Possible values**</span></span> | <span data-ttu-id="d3054-203">False (既定)</span><span class="sxs-lookup"><span data-stu-id="d3054-203">False (default)</span></span> <br/> <span data-ttu-id="d3054-204">True</span><span class="sxs-lookup"><span data-stu-id="d3054-204">True</span></span> |


### <a name="limit-the-telemetry-that-is-sent-from-mau"></a><span data-ttu-id="d3054-205">MAU から送信されるテレメトリを制限する</span><span class="sxs-lookup"><span data-stu-id="d3054-205">Limit the telemetry that is sent from MAU</span></span>

<span data-ttu-id="d3054-206">最小限のハートビート データ、アプリケーションの使用状況、および環境の詳細を送信するには、false に設定します。</span><span class="sxs-lookup"><span data-stu-id="d3054-206">Set to false to send minimal heartbeat data, no application usage, and no environment details.</span></span>

|<span data-ttu-id="d3054-207">Section</span><span class="sxs-lookup"><span data-stu-id="d3054-207">Section</span></span>|<span data-ttu-id="d3054-208">値</span><span class="sxs-lookup"><span data-stu-id="d3054-208">Value</span></span>|
|:--|:--|
| <span data-ttu-id="d3054-209">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="d3054-209">**Domain**</span></span> | <span data-ttu-id="d3054-210">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="d3054-210">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="d3054-211">**Key**</span><span class="sxs-lookup"><span data-stu-id="d3054-211">**Key**</span></span> | <span data-ttu-id="d3054-212">SendAllTelemetryEnabled</span><span class="sxs-lookup"><span data-stu-id="d3054-212">SendAllTelemetryEnabled</span></span> |
| <span data-ttu-id="d3054-213">**データ型**</span><span class="sxs-lookup"><span data-stu-id="d3054-213">**Data type**</span></span> | <span data-ttu-id="d3054-214">Boolean</span><span class="sxs-lookup"><span data-stu-id="d3054-214">Boolean</span></span> |
| <span data-ttu-id="d3054-215">**可能な値**</span><span class="sxs-lookup"><span data-stu-id="d3054-215">**Possible values**</span></span> | <span data-ttu-id="d3054-216">True (既定)</span><span class="sxs-lookup"><span data-stu-id="d3054-216">True (default)</span></span> <br/> <span data-ttu-id="d3054-217">False</span><span class="sxs-lookup"><span data-stu-id="d3054-217">False</span></span> |


## <a name="example-configuration-profile"></a><span data-ttu-id="d3054-218">構成プロファイルの例</span><span class="sxs-lookup"><span data-stu-id="d3054-218">Example configuration profile</span></span>

<span data-ttu-id="d3054-219">次の構成プロファイルを使用して、次の構成プロファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="d3054-219">The following configuration profile is used to:</span></span>
- <span data-ttu-id="d3054-220">ベータ チャネルにデバイスを配置する</span><span class="sxs-lookup"><span data-stu-id="d3054-220">Place the device in the Beta channel</span></span>
- <span data-ttu-id="d3054-221">更新プログラムを自動的にダウンロードしてインストールする</span><span class="sxs-lookup"><span data-stu-id="d3054-221">Automatically download and install updates</span></span>
- <span data-ttu-id="d3054-222">ユーザー インターフェイスで [更新プログラムの確認] ボタンを有効にする</span><span class="sxs-lookup"><span data-stu-id="d3054-222">Enable the "Check for updates" button in the user interface</span></span>
- <span data-ttu-id="d3054-223">デバイス上のユーザーが Insider チャネルに登録を許可する</span><span class="sxs-lookup"><span data-stu-id="d3054-223">Allow users on the device to enroll into the Insider channels</span></span>

### <a name="jamf"></a><span data-ttu-id="d3054-224">JAMF</span><span class="sxs-lookup"><span data-stu-id="d3054-224">JAMF</span></span>

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>ChannelName</key>
    <string>Beta</string>
    <key>HowToCheck</key>
    <string>AutomaticDownload</string>
    <key>EnableCheckForUpdatesButton</key>
    <true/>
    <key>DisableInsiderCheckbox</key>
    <false/>
    <key>SendAllTelemetryEnabled</key>
    <true/>
</dict>
</plist>
```

### <a name="intune"></a><span data-ttu-id="d3054-225">Intune</span><span class="sxs-lookup"><span data-stu-id="d3054-225">Intune</span></span>

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>B762FF60-6ACB-4A72-9E72-459D00C936F3</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.autoupdate2</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft AutoUpdate settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft AutoUpdate configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
            <key>PayloadUUID</key>
            <string>5A6F350A-CC2C-440B-A074-68E3F34EBAE9</string>
            <key>PayloadType</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadOrganization</key>
            <string>Microsoft</string>
            <key>PayloadIdentifier</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadDisplayName</key>
            <string>Microsoft AutoUpdate configuration settings</string>
            <key>PayloadDescription</key>
            <string/>
            <key>PayloadVersion</key>
            <integer>1</integer>
            <key>PayloadEnabled</key>
            <true/>
            <key>ChannelName</key>
            <string>Beta</string>
            <key>HowToCheck</key>
            <string>AutomaticDownload</string>
            <key>EnableCheckForUpdatesButton</key>
            <true/>
            <key>DisableInsiderCheckbox</key>
            <false/>
            <key>SendAllTelemetryEnabled</key>
            <true/>
            </dict>
        </array>
    </dict>
</plist>
```

<span data-ttu-id="d3054-226">MAU を構成するには、企業が使用している管理ツールからこの構成プロファイルを展開できます。</span><span class="sxs-lookup"><span data-stu-id="d3054-226">To configure MAU, you can deploy this configuration profile from the management tool that your enterprise is using:</span></span>
- <span data-ttu-id="d3054-227">JAMF から、この構成プロファイルをアップロードし、Preference ドメインを *com.microsoft.autoupdate2 に設定します*。</span><span class="sxs-lookup"><span data-stu-id="d3054-227">From JAMF, upload this configuration profile and set the Preference Domain to *com.microsoft.autoupdate2*.</span></span>
- <span data-ttu-id="d3054-228">Intune から、この構成プロファイルをアップロードし、カスタム構成プロファイル名を *com.microsoft.autoupdate2 に設定します*。</span><span class="sxs-lookup"><span data-stu-id="d3054-228">From Intune, upload this configuration profile and set the custom configuration profile name to *com.microsoft.autoupdate2*.</span></span>

## <a name="resources"></a><span data-ttu-id="d3054-229">リソース</span><span class="sxs-lookup"><span data-stu-id="d3054-229">Resources</span></span>

- [<span data-ttu-id="d3054-230">msupdate リファレンス</span><span class="sxs-lookup"><span data-stu-id="d3054-230">msupdate reference</span></span>](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate)
