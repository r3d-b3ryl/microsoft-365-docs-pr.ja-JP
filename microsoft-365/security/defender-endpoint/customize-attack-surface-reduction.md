---
title: 攻撃面の減少ルールをカスタマイズする
description: 監査モード、ブロック モード、または無効モードでルールを個別に設定し、攻撃表面の縮小ルールから除外する必要があるファイルとフォルダーを追加する
keywords: 攻撃表面の縮小、腰、ホスト侵入防止システム、保護ルール、悪用防止、脆弱性対策、悪用、感染防止、カスタマイズ、構成、除外
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 52a51b1035f1aa0fb152cf17dc9561cce378d59d
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570353"
---
# <a name="customize-attack-surface-reduction-rules"></a><span data-ttu-id="c95c3-104">攻撃面の減少ルールをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="c95c3-104">Customize attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c95c3-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="c95c3-105">**Applies to:**</span></span>
- [<span data-ttu-id="c95c3-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c95c3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c95c3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c95c3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="c95c3-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="c95c3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c95c3-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="c95c3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="c95c3-110">一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。</span><span class="sxs-lookup"><span data-stu-id="c95c3-110">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="c95c3-111">Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="c95c3-111">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="c95c3-112">[攻撃表面の縮小ルールは](enable-attack-surface-reduction.md) 、デバイスやネットワークを侵害するために悪用されるソフトウェアの動作を防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c95c3-112">[Attack surface reduction rules](enable-attack-surface-reduction.md) help prevent software behaviors that are often abused to compromise your device or network.</span></span> <span data-ttu-id="c95c3-113">たとえば、攻撃者が署名されていないスクリプトを USB ドライブから実行したり、Office ドキュメント内のマクロで Win32 API を直接呼び出したりする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c95c3-113">For example, an attacker might try to run an unsigned script off of a USB drive, or have a macro in an Office document make calls directly to the Win32 API.</span></span> <span data-ttu-id="c95c3-114">攻撃表面の縮小ルールは、このような危険な動作を制限し、組織の防御態勢を向上させる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c95c3-114">Attack surface reduction rules can constrain these kinds of risky behaviors and improve your organization's defensive posture.</span></span>

<span data-ttu-id="c95c3-115">ファイルとフォルダーを除外するか、ユーザーの[](#exclude-files-and-folders)コンピューターに表示される通知[](#customize-the-notification)通知にカスタム テキストを追加して、攻撃表面の縮小ルールをカスタマイズする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c95c3-115">Learn how to customize attack surface reduction rules by [excluding files and folders](#exclude-files-and-folders) or [adding custom text to the notification](#customize-the-notification) alert that appears on a user's computer.</span></span>

<span data-ttu-id="c95c3-116">次のエディションとバージョンのデバイスを実行しているデバイスに対して攻撃表面の縮小ルールをWindows。</span><span class="sxs-lookup"><span data-stu-id="c95c3-116">You can set attack surface reduction rules for devices running any of the following editions and versions of Windows:</span></span>
- <span data-ttu-id="c95c3-117">Windows 10 Proバージョン[1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)以降</span><span class="sxs-lookup"><span data-stu-id="c95c3-117">Windows 10 Pro, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="c95c3-118">Windows 10 Enterpriseバージョン[1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)以降</span><span class="sxs-lookup"><span data-stu-id="c95c3-118">Windows 10 Enterprise, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="c95c3-119">Windowsサーバー、[バージョン 1803 (半期チャネル)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803)以降</span><span class="sxs-lookup"><span data-stu-id="c95c3-119">Windows Server, [version 1803 (Semi-Annual Channel)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- <span data-ttu-id="c95c3-120">[Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)グループ ポリシー、PowerShell、およびモバイル デバイス管理 (MDM) 構成サービス プロバイダー (CSP) を使用して、これらの設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="c95c3-120">[Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19) You can use Group Policy, PowerShell, and Mobile Device Management (MDM) configuration service providers (CSP) to configure these settings.</span></span>

## <a name="exclude-files-and-folders"></a><span data-ttu-id="c95c3-121">ファイルとフォルダーを除外する</span><span class="sxs-lookup"><span data-stu-id="c95c3-121">Exclude files and folders</span></span>

<span data-ttu-id="c95c3-122">ファイルとフォルダーを攻撃表面の縮小ルールによって評価される対象から除外できます。</span><span class="sxs-lookup"><span data-stu-id="c95c3-122">You can choose to exclude files and folders from being evaluated by attack surface reduction rules.</span></span> <span data-ttu-id="c95c3-123">除外されると、攻撃表面の縮小ルールでファイルに悪意のある動作が含まれていると検出された場合でも、ファイルの実行がブロックされません。</span><span class="sxs-lookup"><span data-stu-id="c95c3-123">Once excluded, the file won't be blocked from running even if an attack surface reduction rule detects that the file contains malicious behavior.</span></span>

> [!WARNING]
> <span data-ttu-id="c95c3-124">これにより、安全でないファイルを実行してデバイスに感染する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c95c3-124">This could potentially allow unsafe files to run and infect your devices.</span></span> <span data-ttu-id="c95c3-125">ファイルやフォルダーを除外すると、攻撃表面の縮小ルールによって提供される保護が大幅に低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c95c3-125">Excluding files or folders can severely reduce the protection provided by attack surface reduction rules.</span></span> <span data-ttu-id="c95c3-126">ルールによってブロックされたファイルの実行が許可され、レポートやイベントは記録されません。</span><span class="sxs-lookup"><span data-stu-id="c95c3-126">Files that would have been blocked by a rule will be allowed to run, and there will be no report or event recorded.</span></span>

<span data-ttu-id="c95c3-127">除外は、除外を許可するすべてのルールに適用されます。</span><span class="sxs-lookup"><span data-stu-id="c95c3-127">An exclusion applies to all rules that allow exclusions.</span></span> <span data-ttu-id="c95c3-128">リソースの個別のファイル、フォルダー パス、または完全修飾ドメイン名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c95c3-128">You can specify an individual file, folder path, or the fully qualified domain name for a resource.</span></span> <span data-ttu-id="c95c3-129">ただし、除外を特定のルールに制限することはできません。</span><span class="sxs-lookup"><span data-stu-id="c95c3-129">However, you cannot limit an exclusion to a specific rule.</span></span>

<span data-ttu-id="c95c3-130">除外は、除外されたアプリケーションまたはサービスが開始された場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="c95c3-130">An exclusion is applied only when the excluded application or service starts.</span></span> <span data-ttu-id="c95c3-131">たとえば、既に実行されている更新サービスの除外を追加すると、サービスが停止して再起動されるまで、更新サービスはイベントをトリガーし続ける。</span><span class="sxs-lookup"><span data-stu-id="c95c3-131">For example, if you add an exclusion for an update service that is already running, the update service will continue to trigger events until the service is stopped and restarted.</span></span>

<span data-ttu-id="c95c3-132">攻撃表面の縮小は、環境変数とワイルドカードをサポートします。</span><span class="sxs-lookup"><span data-stu-id="c95c3-132">Attack surface reduction supports environment variables and wildcards.</span></span> <span data-ttu-id="c95c3-133">ワイルドカードの使用の詳細については、「ファイル名とフォルダー パスまたは拡張子の除外リストでワイルドカードを使用する [」を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)。</span><span class="sxs-lookup"><span data-stu-id="c95c3-133">For information about using wildcards, see [use wildcards in the file name and folder path or extension exclusion lists](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>
<span data-ttu-id="c95c3-134">検出すべきではないと思うファイルを検出するルールで問題が発生した場合は、監査モードを使用して [ルールをテストします](evaluate-attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="c95c3-134">If you are encountering problems with rules detecting files that you believe should not be detected, [use audit mode to test the rule](evaluate-attack-surface-reduction.md).</span></span>

<span data-ttu-id="c95c3-135">ルールの説明</span><span class="sxs-lookup"><span data-stu-id="c95c3-135">Rule description</span></span> | <span data-ttu-id="c95c3-136">GUID</span><span class="sxs-lookup"><span data-stu-id="c95c3-136">GUID</span></span>
-|-|-
<span data-ttu-id="c95c3-137">すべてのアプリケーションOffice子プロセスの作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="c95c3-137">Block all Office applications from creating child processes</span></span> | <span data-ttu-id="c95c3-138">D4F940AB-401B-4EFC-AADC-AD5F3C50688A</span><span class="sxs-lookup"><span data-stu-id="c95c3-138">D4F940AB-401B-4EFC-AADC-AD5F3C50688A</span></span>
<span data-ttu-id="c95c3-139">難読化される可能性のあるスクリプトの実行をブロックする</span><span class="sxs-lookup"><span data-stu-id="c95c3-139">Block execution of potentially obfuscated scripts</span></span> | <span data-ttu-id="c95c3-140">5BEB7EFE-FD9A-4556-801D-275E5FFC04CC</span><span class="sxs-lookup"><span data-stu-id="c95c3-140">5BEB7EFE-FD9A-4556-801D-275E5FFC04CC</span></span>
<span data-ttu-id="c95c3-141">Win32 API 呼び出しをブロックOfficeマクロ</span><span class="sxs-lookup"><span data-stu-id="c95c3-141">Block Win32 API calls from Office macro</span></span> | <span data-ttu-id="c95c3-142">92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B</span><span class="sxs-lookup"><span data-stu-id="c95c3-142">92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B</span></span>
<span data-ttu-id="c95c3-143">実行可能Office作成するアプリケーションのブロック</span><span class="sxs-lookup"><span data-stu-id="c95c3-143">Block Office applications from creating executable content</span></span> | <span data-ttu-id="c95c3-144">3B576869-A4EC-4529-8536-B80A7769E899</span><span class="sxs-lookup"><span data-stu-id="c95c3-144">3B576869-A4EC-4529-8536-B80A7769E899</span></span>
<span data-ttu-id="c95c3-145">アプリケーションOffice他のプロセスへのコードの挿入をブロックする</span><span class="sxs-lookup"><span data-stu-id="c95c3-145">Block Office applications from injecting code into other processes</span></span> | <span data-ttu-id="c95c3-146">75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84</span><span class="sxs-lookup"><span data-stu-id="c95c3-146">75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84</span></span>
<span data-ttu-id="c95c3-147">JavaScript または VBScript のダウンロード済み実行可能コンテンツの起動をブロックする</span><span class="sxs-lookup"><span data-stu-id="c95c3-147">Block JavaScript or VBScript from launching downloaded executable content</span></span> | <span data-ttu-id="c95c3-148">D3E037E1-3EB8-44C8-A917-57927947596D</span><span class="sxs-lookup"><span data-stu-id="c95c3-148">D3E037E1-3EB8-44C8-A917-57927947596D</span></span>
<span data-ttu-id="c95c3-149">メール クライアントと Web メールから実行可能なコンテンツをブロックする</span><span class="sxs-lookup"><span data-stu-id="c95c3-149">Block executable content from email client and webmail</span></span> | <span data-ttu-id="c95c3-150">BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550</span><span class="sxs-lookup"><span data-stu-id="c95c3-150">BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550</span></span>
<span data-ttu-id="c95c3-151">有病率、年齢、または信頼できるリスト条件を満たしない限り、実行可能ファイルの実行をブロックする</span><span class="sxs-lookup"><span data-stu-id="c95c3-151">Block executable files from running unless they meet a prevalence, age, or trusted list criteria</span></span> | <span data-ttu-id="c95c3-152">01443614-cd74-433a-b99e-2ecdc07bfc25</span><span class="sxs-lookup"><span data-stu-id="c95c3-152">01443614-cd74-433a-b99e-2ecdc07bfc25</span></span>
<span data-ttu-id="c95c3-153">ランサムウェアに対する高度な保護の使用</span><span class="sxs-lookup"><span data-stu-id="c95c3-153">Use advanced protection against ransomware</span></span> | <span data-ttu-id="c95c3-154">c1db55ab-c21a-4637-bb3f-a12568109d35</span><span class="sxs-lookup"><span data-stu-id="c95c3-154">c1db55ab-c21a-4637-bb3f-a12568109d35</span></span>
<span data-ttu-id="c95c3-155">ローカル セキュリティ機関サブシステムからの資格情報のWindowsをブロックする (lsass.exe)</span><span class="sxs-lookup"><span data-stu-id="c95c3-155">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span> | <span data-ttu-id="c95c3-156">9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2</span><span class="sxs-lookup"><span data-stu-id="c95c3-156">9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2</span></span>
<span data-ttu-id="c95c3-157">PSExec および WMI コマンドから発生するプロセス作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="c95c3-157">Block process creations originating from PSExec and WMI commands</span></span> | <span data-ttu-id="c95c3-158">d1e49aac-8f56-4280-b9ba-993a6d77406c</span><span class="sxs-lookup"><span data-stu-id="c95c3-158">d1e49aac-8f56-4280-b9ba-993a6d77406c</span></span>
<span data-ttu-id="c95c3-159">USB から実行される信頼されていないプロセスと署名されていないプロセスをブロックする</span><span class="sxs-lookup"><span data-stu-id="c95c3-159">Block untrusted and unsigned processes that run from USB</span></span> | <span data-ttu-id="c95c3-160">b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4</span><span class="sxs-lookup"><span data-stu-id="c95c3-160">b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4</span></span>
<span data-ttu-id="c95c3-161">通信Office子プロセスの作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="c95c3-161">Block Office communication applications from creating child processes</span></span> | <span data-ttu-id="c95c3-162">26190899-1602-49e8-8b27-eb1d0a1ce869</span><span class="sxs-lookup"><span data-stu-id="c95c3-162">26190899-1602-49e8-8b27-eb1d0a1ce869</span></span>
<span data-ttu-id="c95c3-163">Adobe Reader の子プロセスの作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="c95c3-163">Block Adobe Reader from creating child processes</span></span> | <span data-ttu-id="c95c3-164">7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c</span><span class="sxs-lookup"><span data-stu-id="c95c3-164">7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c</span></span>
<span data-ttu-id="c95c3-165">WMI イベント サブスクリプションによる永続化のブロック</span><span class="sxs-lookup"><span data-stu-id="c95c3-165">Block persistence through WMI event subscription</span></span> | <span data-ttu-id="c95c3-166">e6db77e5-3df2-4cf1-b95a-636979351e5b</span><span class="sxs-lookup"><span data-stu-id="c95c3-166">e6db77e5-3df2-4cf1-b95a-636979351e5b</span></span>

<span data-ttu-id="c95c3-167">各ルールの [詳細については、攻撃表面](attack-surface-reduction.md) の縮小に関するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c95c3-167">See the [attack surface reduction](attack-surface-reduction.md) topic for details on each rule.</span></span>

### <a name="use-group-policy-to-exclude-files-and-folders"></a><span data-ttu-id="c95c3-168">グループ ポリシーを使用してファイルとフォルダーを除外する</span><span class="sxs-lookup"><span data-stu-id="c95c3-168">Use Group Policy to exclude files and folders</span></span>

1. <span data-ttu-id="c95c3-169">グループ ポリシー管理コンピューターで、[[グループ ポリシー管理コンソール]](https://technet.microsoft.com/library/cc731212.aspx) を開き、構成するグループ ポリシー オブジェクトを右クリックして、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c95c3-169">On your Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="c95c3-170">グループ ポリシー **管理エディターで、[コンピューター** の構成] に移動 **し、[** 管理用 **テンプレート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c95c3-170">In the **Group Policy Management Editor**, go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="c95c3-171">ツリーを展開して **、Exploit Guard 攻撃Windows縮小**  >    >  **Microsoft Defender ウイルス対策Windows Defenderコンポーネント**  >  **を展開します**。</span><span class="sxs-lookup"><span data-stu-id="c95c3-171">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Attack surface reduction**.</span></span>

4. <span data-ttu-id="c95c3-172">[攻撃表面の縮小 **ルールからファイル** とパスを除外する] 設定をダブルクリックし、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="c95c3-172">Double-click the **Exclude files and paths from Attack surface reduction Rules** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="c95c3-173">[ **表示] を** 選択し、[値の名前] 列に各ファイル **またはフォルダーを入力** します。</span><span class="sxs-lookup"><span data-stu-id="c95c3-173">Select **Show** and enter each file or folder in the **Value name** column.</span></span> <span data-ttu-id="c95c3-174">各 **アイテムの [** 値] **列に 0** を入力します。</span><span class="sxs-lookup"><span data-stu-id="c95c3-174">Enter **0** in the **Value** column for each item.</span></span>

> [!WARNING]
> <span data-ttu-id="c95c3-175">[値の名前] 列または [値] 列でサポートされていない引用符は **使用** しません。</span><span class="sxs-lookup"><span data-stu-id="c95c3-175">Do not use quotes as they are not supported for either the **Value name** column or the **Value** column.</span></span>

### <a name="use-powershell-to-exclude-files-and-folders"></a><span data-ttu-id="c95c3-176">PowerShell を使用してファイルとフォルダーを除外する</span><span class="sxs-lookup"><span data-stu-id="c95c3-176">Use PowerShell to exclude files and folders</span></span>

1. <span data-ttu-id="c95c3-177">[**スタート] メニューに「powershell」** と入力し、[管理者 **Windows PowerShellを右** クリックし、[管理者として **実行] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="c95c3-177">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="c95c3-178">次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="c95c3-178">Enter the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

<span data-ttu-id="c95c3-179">引き続き使用 `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` して、リストにフォルダーを追加します。</span><span class="sxs-lookup"><span data-stu-id="c95c3-179">Continue to use `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` to add more folders to the list.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c95c3-180">リスト `Add-MpPreference` にアプリを追加または追加する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="c95c3-180">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="c95c3-181">コマンドレットを `Set-MpPreference` 使用すると、既存のリストが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="c95c3-181">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-exclude-files-and-folders"></a><span data-ttu-id="c95c3-182">MDM CSP を使用してファイルとフォルダーを除外する</span><span class="sxs-lookup"><span data-stu-id="c95c3-182">Use MDM CSPs to exclude files and folders</span></span>

<span data-ttu-id="c95c3-183">除外を追加するには [、./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) 構成サービス プロバイダー (CSP) を使用します。</span><span class="sxs-lookup"><span data-stu-id="c95c3-183">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) to add exclusions.</span></span>

## <a name="customize-the-notification"></a><span data-ttu-id="c95c3-184">通知をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="c95c3-184">Customize the notification</span></span>

<span data-ttu-id="c95c3-185">ルールがトリガーされた場合の通知をカスタマイズし、アプリまたはファイルをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="c95c3-185">You can customize the notification for when a rule is triggered and blocks an app or file.</span></span> <span data-ttu-id="c95c3-186">詳しくは[、Windows セキュリティをご覧](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center)ください。</span><span class="sxs-lookup"><span data-stu-id="c95c3-186">See the [Windows Security](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center) article.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c95c3-187">関連項目</span><span class="sxs-lookup"><span data-stu-id="c95c3-187">Related topics</span></span>

* [<span data-ttu-id="c95c3-188">攻撃表面の縮小ルールを使用して攻撃表面を削減する</span><span class="sxs-lookup"><span data-stu-id="c95c3-188">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)
* [<span data-ttu-id="c95c3-189">攻撃面の減少ルールを有効にする</span><span class="sxs-lookup"><span data-stu-id="c95c3-189">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md)
* [<span data-ttu-id="c95c3-190">攻撃面の減少ルールを評価する</span><span class="sxs-lookup"><span data-stu-id="c95c3-190">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
* [<span data-ttu-id="c95c3-191">攻撃面の減少の FAQ</span><span class="sxs-lookup"><span data-stu-id="c95c3-191">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
