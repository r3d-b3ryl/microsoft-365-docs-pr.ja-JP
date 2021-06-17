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
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 6b9814180df2cad2553c4565ebb65891b5cf9bf5
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985422"
---
# <a name="customize-attack-surface-reduction-rules"></a><span data-ttu-id="1d4c0-104">攻撃面の減少ルールをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="1d4c0-104">Customize attack surface reduction rules</span></span>

<span data-ttu-id="1d4c0-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="1d4c0-105">**Applies to:**</span></span>

- [<span data-ttu-id="1d4c0-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1d4c0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1d4c0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1d4c0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="1d4c0-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="1d4c0-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1d4c0-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="1d4c0-110">一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-110">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="1d4c0-111">Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-111">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="1d4c0-112">[攻撃表面の縮小ルールは](enable-attack-surface-reduction.md) 、デバイスやネットワークを侵害するために悪用されるソフトウェアの動作を防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-112">[Attack surface reduction rules](enable-attack-surface-reduction.md) help prevent software behaviors that are often abused to compromise your device or network.</span></span> <span data-ttu-id="1d4c0-113">たとえば、攻撃者が署名されていないスクリプトを USB ドライブから実行したり、Office ドキュメント内のマクロで Win32 API を直接呼び出したりする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-113">For example, an attacker might try to run an unsigned script off of a USB drive, or have a macro in an Office document make calls directly to the Win32 API.</span></span> <span data-ttu-id="1d4c0-114">攻撃表面の縮小ルールは、このような危険な動作を制限し、組織の防御態勢を向上させる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-114">Attack surface reduction rules can constrain these kinds of risky behaviors and improve your organization's defensive posture.</span></span>

<span data-ttu-id="1d4c0-115">ファイルとフォルダーを除外するか、ユーザーの[](#exclude-files-and-folders)コンピューターに表示される通知[](#customize-the-notification)通知にカスタム テキストを追加して、攻撃表面の縮小ルールをカスタマイズする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-115">Learn how to customize attack surface reduction rules by [excluding files and folders](#exclude-files-and-folders) or [adding custom text to the notification](#customize-the-notification) alert that appears on a user's computer.</span></span>

<span data-ttu-id="1d4c0-116">次のエディションとバージョンのデバイスを実行しているデバイスに対して攻撃表面の縮小ルールをWindows。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-116">You can set attack surface reduction rules for devices running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="1d4c0-117">Windows 10 Proバージョン[1709](/windows/whats-new/whats-new-windows-10-version-1709)以降</span><span class="sxs-lookup"><span data-stu-id="1d4c0-117">Windows 10 Pro, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="1d4c0-118">Windows 10 Enterpriseバージョン[1709](/windows/whats-new/whats-new-windows-10-version-1709)以降</span><span class="sxs-lookup"><span data-stu-id="1d4c0-118">Windows 10 Enterprise, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="1d4c0-119">Windowsサーバー、[バージョン 1803 (半期チャネル)](/windows-server/get-started/whats-new-in-windows-server-1803)以降</span><span class="sxs-lookup"><span data-stu-id="1d4c0-119">Windows Server, [version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- <span data-ttu-id="1d4c0-120">[Windows Server 2019](/windows-server/get-started-19/whats-new-19)グループ ポリシー、PowerShell、およびモバイル デバイス管理 (MDM) 構成サービス プロバイダー (CSP) を使用して、これらの設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-120">[Windows Server 2019](/windows-server/get-started-19/whats-new-19) You can use Group Policy, PowerShell, and Mobile Device Management (MDM) configuration service providers (CSP) to configure these settings.</span></span>

## <a name="exclude-files-and-folders"></a><span data-ttu-id="1d4c0-121">ファイルとフォルダーを除外する</span><span class="sxs-lookup"><span data-stu-id="1d4c0-121">Exclude files and folders</span></span>

<span data-ttu-id="1d4c0-122">ファイルとフォルダーを攻撃表面の縮小ルールによって評価される対象から除外できます。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-122">You can choose to exclude files and folders from being evaluated by attack surface reduction rules.</span></span> <span data-ttu-id="1d4c0-123">除外すると、攻撃表面の縮小ルールでファイルに悪意のある動作が含まれていると検出された場合でも、ファイルの実行がブロックされません。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-123">When excluded, the file won't be blocked from running even if an attack surface reduction rule detects that the file contains malicious behavior.</span></span>

<span data-ttu-id="1d4c0-124">たとえば、次のランサムウェア ルールを考え出します。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-124">For example, consider the ransomware rule:</span></span>

<span data-ttu-id="1d4c0-125">ランサムウェア ルールは、企業のお客様がビジネスの継続性を確保しながら、ランサムウェア攻撃のリスクを軽減するために設計されています。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-125">The ransomware rule is designed to help enterprise customers reduce risks of ransomware attacks while ensuring business continuity.</span></span> <span data-ttu-id="1d4c0-126">既定では、ランサムウェア ルールのエラーは注意の側で発生し、まだ十分な評価と信頼を得ていないファイルから保護します。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-126">By default, the ransomware rule errors on the side of caution and protect against files that haven't yet attained sufficient reputation and trust.</span></span> <span data-ttu-id="1d4c0-127">再フェーズを行う場合、ランサムウェア ルールは、何百万人もの顧客の利用状況指標に基づいて、十分な肯定的な評価と普及率を得てないファイルでのみトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-127">To reemphasize, the ransomware rule only triggers on files that have not gained enough positive reputation and prevalence, based on usage metrics of millions of our customers.</span></span> <span data-ttu-id="1d4c0-128">通常、ブロックは自己解決されます。各ファイルの "評価と信頼" の値は、問題ない使用法が増えるほど段階的にアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-128">Usually, the blocks are self resolved, because each file's “reputation and trust” values are incrementally upgraded as non-problematic usage increases.</span></span>

<span data-ttu-id="1d4c0-129">ブロックが自己解決されない場合、お客様は自己のリスクで、セルフサービス メカニズムまたは IOC (IOC) ベースの "許可リスト" 機能を利用して、ファイル自体のブロックを解除できます。 </span><span class="sxs-lookup"><span data-stu-id="1d4c0-129">In cases in which blocks aren’t self resolved in a timely manner, customers can - _at their own risk_ - make use of either the self-service mechanism or an Indicator of Compromise (IOC)-based "allow list" capability to unblock the files themselves.</span></span>  

> [!WARNING]
> <span data-ttu-id="1d4c0-130">ファイルまたはフォルダーのブロックを除外または解除すると、安全でないファイルが実行され、デバイスに感染する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-130">Excluding or unblocking files or folders could potentially allow unsafe files to run and infect your devices.</span></span> <span data-ttu-id="1d4c0-131">ファイルやフォルダーを除外すると、攻撃面の減少ルールで指定された保護機能が著しく低下します。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-131">Excluding files or folders can severely reduce the protection provided by attack surface reduction rules.</span></span> <span data-ttu-id="1d4c0-132">ルールによってブロックされたファイルの実行が許可され、レポートやイベントは記録されません。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-132">Files that would have been blocked by a rule will be allowed to run, and there will be no report or event recorded.</span></span>

<span data-ttu-id="1d4c0-133">除外は、除外を許可するすべてのルールに適用されます。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-133">An exclusion applies to all rules that allow exclusions.</span></span> <span data-ttu-id="1d4c0-134">リソースの個別のファイル、フォルダー パス、または完全修飾ドメイン名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-134">You can specify an individual file, folder path, or the fully qualified domain name for a resource.</span></span> <span data-ttu-id="1d4c0-135">ただし、除外を特定のルールに制限することはできません。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-135">However, you cannot limit an exclusion to a specific rule.</span></span>

<span data-ttu-id="1d4c0-136">除外は、除外されたアプリケーションまたはサービスが開始された場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-136">An exclusion is applied only when the excluded application or service starts.</span></span> <span data-ttu-id="1d4c0-137">たとえば、既に実行されている更新サービスの除外を追加すると、サービスが停止して再起動されるまで、更新サービスはイベントをトリガーし続ける。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-137">For example, if you add an exclusion for an update service that is already running, the update service will continue to trigger events until the service is stopped and restarted.</span></span>

<span data-ttu-id="1d4c0-138">攻撃表面の縮小は、環境変数とワイルドカードをサポートします。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-138">Attack surface reduction supports environment variables and wildcards.</span></span> <span data-ttu-id="1d4c0-139">ワイルドカードの使用の詳細については、「ファイル名とフォルダー パスまたは拡張子の除外リストでワイルドカードを使用する [」を参照してください](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) 。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-139">For information about using wildcards, see [use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) .</span></span>
<span data-ttu-id="1d4c0-140">検出すべきではないと思うファイルを検出するルールで問題が発生した場合は、監査モードを使用して [ルールをテストします](evaluate-attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-140">If you are encountering problems with rules detecting files that you believe should not be detected, [use audit mode to test the rule](evaluate-attack-surface-reduction.md).</span></span>

| <span data-ttu-id="1d4c0-141">ルールの説明</span><span class="sxs-lookup"><span data-stu-id="1d4c0-141">Rule description</span></span> | <span data-ttu-id="1d4c0-142">GUID</span><span class="sxs-lookup"><span data-stu-id="1d4c0-142">GUID</span></span> |
|:----|:----|
| <span data-ttu-id="1d4c0-143">すべてのアプリケーションOffice子プロセスの作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="1d4c0-143">Block all Office applications from creating child processes</span></span> | `D4F940AB-401B-4EFC-AADC-AD5F3C50688A` |
| <span data-ttu-id="1d4c0-144">難読化される可能性のあるスクリプトの実行をブロックする</span><span class="sxs-lookup"><span data-stu-id="1d4c0-144">Block execution of potentially obfuscated scripts</span></span> | `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC` |
| <span data-ttu-id="1d4c0-145">Win32 API 呼び出しをブロックOfficeマクロ</span><span class="sxs-lookup"><span data-stu-id="1d4c0-145">Block Win32 API calls from Office macro</span></span> | `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B` |
| <span data-ttu-id="1d4c0-146">実行可能Office作成するアプリケーションのブロック</span><span class="sxs-lookup"><span data-stu-id="1d4c0-146">Block Office applications from creating executable content</span></span> | `3B576869-A4EC-4529-8536-B80A7769E899` |
| <span data-ttu-id="1d4c0-147">アプリケーションOffice他のプロセスへのコードの挿入をブロックする</span><span class="sxs-lookup"><span data-stu-id="1d4c0-147">Block Office applications from injecting code into other processes</span></span> | `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84` |
| <span data-ttu-id="1d4c0-148">JavaScript または VBScript のダウンロード済み実行可能コンテンツの起動をブロックする</span><span class="sxs-lookup"><span data-stu-id="1d4c0-148">Block JavaScript or VBScript from launching downloaded executable content</span></span> | `D3E037E1-3EB8-44C8-A917-57927947596D` |
| <span data-ttu-id="1d4c0-149">メール クライアントと Web メールから実行可能なコンテンツをブロックする</span><span class="sxs-lookup"><span data-stu-id="1d4c0-149">Block executable content from email client and webmail</span></span> | `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550` |
| <span data-ttu-id="1d4c0-150">有病率、年齢、または信頼できるリスト条件を満たしない限り、実行可能ファイルの実行をブロックする</span><span class="sxs-lookup"><span data-stu-id="1d4c0-150">Block executable files from running unless they meet a prevalence, age, or trusted list criteria</span></span> | `01443614-cd74-433a-b99e-2ecdc07bfc25` |
| <span data-ttu-id="1d4c0-151">ランサムウェアに対する高度な保護の使用</span><span class="sxs-lookup"><span data-stu-id="1d4c0-151">Use advanced protection against ransomware</span></span> | `c1db55ab-c21a-4637-bb3f-a12568109d35` |
| <span data-ttu-id="1d4c0-152">ローカル セキュリティ機関サブシステムからの資格情報のWindowsをブロックする (lsass.exe)</span><span class="sxs-lookup"><span data-stu-id="1d4c0-152">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span> | `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2` |
| <span data-ttu-id="1d4c0-153">PSExec および WMI コマンドから発生するプロセス作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="1d4c0-153">Block process creations originating from PSExec and WMI commands</span></span> | `d1e49aac-8f56-4280-b9ba-993a6d77406c` |
| <span data-ttu-id="1d4c0-154">USB から実行される信頼されていないプロセスと署名されていないプロセスをブロックする</span><span class="sxs-lookup"><span data-stu-id="1d4c0-154">Block untrusted and unsigned processes that run from USB</span></span> | `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4` |
| <span data-ttu-id="1d4c0-155">通信Office子プロセスの作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="1d4c0-155">Block Office communication applications from creating child processes</span></span> | `26190899-1602-49e8-8b27-eb1d0a1ce869` |
| <span data-ttu-id="1d4c0-156">Adobe Reader の子プロセスの作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="1d4c0-156">Block Adobe Reader from creating child processes</span></span> | `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c` |
| <span data-ttu-id="1d4c0-157">WMI イベント サブスクリプションによる永続化のブロック</span><span class="sxs-lookup"><span data-stu-id="1d4c0-157">Block persistence through WMI event subscription</span></span> | `e6db77e5-3df2-4cf1-b95a-636979351e5b` |

<span data-ttu-id="1d4c0-158">各ルールの [詳細については、攻撃表面](attack-surface-reduction.md) の縮小に関するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-158">See the [attack surface reduction](attack-surface-reduction.md) topic for details on each rule.</span></span>

### <a name="use-group-policy-to-exclude-files-and-folders"></a><span data-ttu-id="1d4c0-159">グループ ポリシーを使用してファイルとフォルダーを除外する</span><span class="sxs-lookup"><span data-stu-id="1d4c0-159">Use Group Policy to exclude files and folders</span></span>

1. <span data-ttu-id="1d4c0-160">グループ ポリシー管理コンピューターで、[[グループ ポリシー管理コンソール]](https://technet.microsoft.com/library/cc731212.aspx) を開き、構成するグループ ポリシー オブジェクトを右クリックして、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-160">On your Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="1d4c0-161">グループ ポリシー **管理エディターで、[コンピューター** の構成] に移動 **し、[** 管理用 **テンプレート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-161">In the **Group Policy Management Editor**, go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="1d4c0-162">ツリーを展開して **、Exploit Guard 攻撃Windows縮小**  >    >  **Microsoft Defender ウイルス対策Windows Defenderコンポーネント**  >  **を展開します**。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-162">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Attack surface reduction**.</span></span>

4. <span data-ttu-id="1d4c0-163">[攻撃表面の縮小 **ルールからファイル** とパスを除外する] 設定をダブルクリックし、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-163">Double-click the **Exclude files and paths from Attack surface reduction Rules** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="1d4c0-164">[ **表示] を** 選択し、[値の名前] 列に各ファイル **またはフォルダーを入力** します。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-164">Select **Show** and enter each file or folder in the **Value name** column.</span></span> <span data-ttu-id="1d4c0-165">各 **アイテムの [** 値] **列に 0** を入力します。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-165">Enter **0** in the **Value** column for each item.</span></span>

> [!WARNING]
> <span data-ttu-id="1d4c0-166">[値の名前] 列または [値] 列でサポートされていない引用符は **使用** しません。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-166">Do not use quotes as they are not supported for either the **Value name** column or the **Value** column.</span></span>

### <a name="use-powershell-to-exclude-files-and-folders"></a><span data-ttu-id="1d4c0-167">PowerShell を使用してファイルとフォルダーを除外する</span><span class="sxs-lookup"><span data-stu-id="1d4c0-167">Use PowerShell to exclude files and folders</span></span>

1. <span data-ttu-id="1d4c0-168">**[powershell]** と入力スタート メニューを **右クリックし**、[管理者Windows PowerShell **実行] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="1d4c0-168">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="1d4c0-169">次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-169">Enter the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

<span data-ttu-id="1d4c0-170">引き続き使用 `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` して、リストにフォルダーを追加します。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-170">Continue to use `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` to add more folders to the list.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d4c0-171">リスト `Add-MpPreference` にアプリを追加または追加する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-171">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="1d4c0-172">コマンドレットを `Set-MpPreference` 使用すると、既存のリストが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-172">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-exclude-files-and-folders"></a><span data-ttu-id="1d4c0-173">MDM CSP を使用してファイルとフォルダーを除外する</span><span class="sxs-lookup"><span data-stu-id="1d4c0-173">Use MDM CSPs to exclude files and folders</span></span>

<span data-ttu-id="1d4c0-174">除外を追加するには [、./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) 構成サービス プロバイダー (CSP) を使用します。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-174">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) to add exclusions.</span></span>

## <a name="customize-the-notification"></a><span data-ttu-id="1d4c0-175">通知をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="1d4c0-175">Customize the notification</span></span>

<span data-ttu-id="1d4c0-176">ルールがトリガーされた場合の通知をカスタマイズし、アプリまたはファイルをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-176">You can customize the notification for when a rule is triggered and blocks an app or file.</span></span> <span data-ttu-id="1d4c0-177">詳しくは[、Windows セキュリティをご覧](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center)ください。</span><span class="sxs-lookup"><span data-stu-id="1d4c0-177">See the [Windows Security](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center) article.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1d4c0-178">関連項目</span><span class="sxs-lookup"><span data-stu-id="1d4c0-178">Related topics</span></span>

- [<span data-ttu-id="1d4c0-179">攻撃表面の縮小ルールを使用して攻撃表面を削減する</span><span class="sxs-lookup"><span data-stu-id="1d4c0-179">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)
- [<span data-ttu-id="1d4c0-180">攻撃面の減少ルールを有効にする</span><span class="sxs-lookup"><span data-stu-id="1d4c0-180">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md)
- [<span data-ttu-id="1d4c0-181">攻撃面の減少ルールを評価する</span><span class="sxs-lookup"><span data-stu-id="1d4c0-181">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
- [<span data-ttu-id="1d4c0-182">攻撃面の減少の FAQ</span><span class="sxs-lookup"><span data-stu-id="1d4c0-182">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
