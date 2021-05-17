---
title: 保護機能を有効Microsoft Defender ウイルス対策構成する
description: 動作の監視Microsoft Defender ウイルス対策機械学習などのリアルタイム保護機能を有効にして構成する
keywords: ウイルス対策、リアルタイム保護、rtp、機械学習、動作監視、ヒューリスティック
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 12/16/2019
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 1e39e42b79a2a767473c4473434da249a0d07228
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275134"
---
# <a name="enable-and-configure-microsoft-defender-antivirus-always-on-protection-in-group-policy"></a><span data-ttu-id="cf34e-104">グループ ポリシーで Microsoft Defender ウイルス対策を常時保護を有効にして構成する</span><span class="sxs-lookup"><span data-stu-id="cf34e-104">Enable and configure Microsoft Defender Antivirus always-on protection in Group Policy</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="cf34e-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="cf34e-105">**Applies to:**</span></span>

- [<span data-ttu-id="cf34e-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="cf34e-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="cf34e-107">常時保護は、既知の疑わしいアクティビティや悪意のあるアクティビティに基づいてマルウェアを識別するためのリアルタイム保護、動作監視、ヒューリスティックで構成されます。</span><span class="sxs-lookup"><span data-stu-id="cf34e-107">Always-on protection consists of real-time protection, behavior monitoring, and heuristics to identify malware based on known suspicious and malicious activities.</span></span>

<span data-ttu-id="cf34e-108">これらのアクティビティには、既存のファイルに異常な変更を加えるプロセス、自動スタートアップ レジストリ キーの変更または作成、スタートアップの場所 (自動開始機能拡張ポイントまたは ASEPs とも呼ばれる) などのイベントや、ファイル システムまたはファイル構造に対するその他の変更が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cf34e-108">These activities include events, such as processes making unusual changes to existing files, modifying or creating automatic startup registry keys and startup locations (also known as auto-start extensibility points, or ASEPs), and other changes to the file system or file structure.</span></span>

## <a name="enable-and-configure-always-on-protection-in-group-policy"></a><span data-ttu-id="cf34e-109">グループ ポリシーで常時オン保護を有効にして構成する</span><span class="sxs-lookup"><span data-stu-id="cf34e-109">Enable and configure always-on protection in Group Policy</span></span>

<span data-ttu-id="cf34e-110">ローカル グループ ポリシー **エディターを使用して**、常にオンMicrosoft Defender ウイルス対策設定を有効にして構成できます。</span><span class="sxs-lookup"><span data-stu-id="cf34e-110">You can use **Local Group Policy Editor** to enable and configure Microsoft Defender Antivirus always-on protection settings.</span></span>

<span data-ttu-id="cf34e-111">常時保護を有効にして構成するには、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="cf34e-111">To enable and configure always-on protection:</span></span>

1. <span data-ttu-id="cf34e-112">[ローカル **グループ ポリシー エディター] を開きます**。</span><span class="sxs-lookup"><span data-stu-id="cf34e-112">Open **Local Group Policy Editor**.</span></span> <span data-ttu-id="cf34e-113">これを行うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cf34e-113">To do this:</span></span>  

    1. <span data-ttu-id="cf34e-114">[タスク バー Windows 10] ボックスに **「gpedit」と入力します**。</span><span class="sxs-lookup"><span data-stu-id="cf34e-114">In your Windows 10 taskbar search box, type **gpedit**.</span></span>
    
    1. <span data-ttu-id="cf34e-115">[最適 **な一致]** で、[グループ ポリシー **の編集] をクリックして** ローカル **グループ ポリシー エディターを起動します**。</span><span class="sxs-lookup"><span data-stu-id="cf34e-115">Under **Best match**, click **Edit group policy** to launch **Local Group Policy Editor**.</span></span>
    
       ![GPEdit タスク バーの検索結果](images/gpedit-search.png)

2. <span data-ttu-id="cf34e-117">ローカル グループ ポリシー エディターの **左側のウィンドウ** で、ツリーを [コンピューター構成] [管理用テンプレート] Windows  >    >  **展開**  >  Microsoft Defender ウイルス対策。</span><span class="sxs-lookup"><span data-stu-id="cf34e-117">In the left pane of **Local Group Policy Editor**, expand the tree to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus**.</span></span> 

3. <span data-ttu-id="cf34e-118">マルウェア対策サービス Microsoft Defender ウイルス対策設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="cf34e-118">Configure the Microsoft Defender Antivirus antimalware service policy settings.</span></span> <span data-ttu-id="cf34e-119">これを行うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cf34e-119">To do this:</span></span>  

    1. <span data-ttu-id="cf34e-120">右側の **Microsoft Defender ウイルス対策** ウィンドウで、次の表で指定したポリシー設定をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf34e-120">In the **Microsoft Defender Antivirus** details pane on right, double-click the policy setting as specified in the following table:</span></span>

       | <span data-ttu-id="cf34e-121">Setting</span><span class="sxs-lookup"><span data-stu-id="cf34e-121">Setting</span></span> | <span data-ttu-id="cf34e-122">説明</span><span class="sxs-lookup"><span data-stu-id="cf34e-122">Description</span></span> | <span data-ttu-id="cf34e-123">既定の設定</span><span class="sxs-lookup"><span data-stu-id="cf34e-123">Default setting</span></span> |
       |-----------------------------|------------------------|-------------------------------|
       | <span data-ttu-id="cf34e-124">マルウェア対策サービスが通常の優先度で起動を許可する</span><span class="sxs-lookup"><span data-stu-id="cf34e-124">Allow antimalware service to startup with normal priority</span></span> | <span data-ttu-id="cf34e-125">エンジンの優先度を下Microsoft Defender ウイルス対策、スタートアップ プロセスを可能な限りリーンにする軽量な展開に役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="cf34e-125">You can lower the priority of the Microsoft Defender Antivirus engine, which may be useful in lightweight deployments where you want to have as lean a startup process as possible.</span></span> <span data-ttu-id="cf34e-126">これは、エンドポイントの保護に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cf34e-126">This may impact protection on the endpoint.</span></span> | <span data-ttu-id="cf34e-127">Enabled</span><span class="sxs-lookup"><span data-stu-id="cf34e-127">Enabled</span></span>
       | <span data-ttu-id="cf34e-128">マルウェア対策サービスの実行を常に許可する</span><span class="sxs-lookup"><span data-stu-id="cf34e-128">Allow antimalware service to remain running always</span></span> | <span data-ttu-id="cf34e-129">保護更新プログラムが無効になっている場合は、引き続き実行Microsoft Defender ウイルス対策設定できます。</span><span class="sxs-lookup"><span data-stu-id="cf34e-129">If protection updates have been disabled, you can set Microsoft Defender Antivirus to still run.</span></span> <span data-ttu-id="cf34e-130">これにより、エンドポイントの保護が低下します。</span><span class="sxs-lookup"><span data-stu-id="cf34e-130">This lowers the protection on the endpoint.</span></span> | <span data-ttu-id="cf34e-131">無効</span><span class="sxs-lookup"><span data-stu-id="cf34e-131">Disabled</span></span> |
    
    1. <span data-ttu-id="cf34e-132">必要に応じて設定を構成し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="cf34e-132">Configure the setting as appropriate, and click **OK**.</span></span>
    
    1. <span data-ttu-id="cf34e-133">表の各設定について、前の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="cf34e-133">Repeat the previous steps for each setting in the table.</span></span>

4. <span data-ttu-id="cf34e-134">リアルタイム保護Microsoft Defender ウイルス対策設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="cf34e-134">Configure the Microsoft Defender Antivirus real-time protection policy settings.</span></span> <span data-ttu-id="cf34e-135">これを行うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cf34e-135">To do this:</span></span>

    1. <span data-ttu-id="cf34e-136">[詳細Microsoft Defender ウイルス対策] ウィンドウで、[リアルタイム保護]**をダブルクリックします**。</span><span class="sxs-lookup"><span data-stu-id="cf34e-136">In the **Microsoft Defender Antivirus** details pane, double-click **Real-time Protection**.</span></span> <span data-ttu-id="cf34e-137">または、**左側のウィンドウ** Microsoft Defender ウイルス対策の [リアルタイム保護]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="cf34e-137">Or, from the **Microsoft Defender Antivirus** tree on left pane, click **Real-time Protection**.</span></span>
    
    1. <span data-ttu-id="cf34e-138">右側の **[リアルタイム保護の詳細]** ウィンドウで、次の表で指定したポリシー設定をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf34e-138">In the **Real-time Protection** details pane on right, double-click the policy setting as specified in the following table:</span></span>  

       | <span data-ttu-id="cf34e-139">Setting</span><span class="sxs-lookup"><span data-stu-id="cf34e-139">Setting</span></span> | <span data-ttu-id="cf34e-140">説明</span><span class="sxs-lookup"><span data-stu-id="cf34e-140">Description</span></span> | <span data-ttu-id="cf34e-141">既定の設定</span><span class="sxs-lookup"><span data-stu-id="cf34e-141">Default setting</span></span> |
       |-----------------------------|------------------------|-------------------------------|
       | <span data-ttu-id="cf34e-142">動作の監視を有効にする</span><span class="sxs-lookup"><span data-stu-id="cf34e-142">Turn on behavior monitoring</span></span> | <span data-ttu-id="cf34e-143">AV エンジンは、ファイル プロセス、ファイルとレジストリの変更、およびエンドポイント上の他のイベントを監視し、疑わしい悪意のあるアクティビティや既知の悪意のあるアクティビティを監視します。</span><span class="sxs-lookup"><span data-stu-id="cf34e-143">The AV engine will monitor file processes, file and registry changes, and other events on your endpoints for suspicious and known malicious activity.</span></span> | <span data-ttu-id="cf34e-144">Enabled</span><span class="sxs-lookup"><span data-stu-id="cf34e-144">Enabled</span></span> |
       | <span data-ttu-id="cf34e-145">ダウンロードしたファイルと添付ファイルをスキャンする</span><span class="sxs-lookup"><span data-stu-id="cf34e-145">Scan all downloaded files and attachments</span></span> | <span data-ttu-id="cf34e-146">ダウンロードしたファイルと添付ファイルは自動的にスキャンされます。</span><span class="sxs-lookup"><span data-stu-id="cf34e-146">Downloaded files and attachments are automatically scanned.</span></span> <span data-ttu-id="cf34e-147">これは、ダウンロード前とダウンロード中Windows Defenderスキャンする SmartScreen フィルターの機能に加えて動作します。</span><span class="sxs-lookup"><span data-stu-id="cf34e-147">This operates in addition to the Windows Defender SmartScreen filter, which scans files before and during downloading.</span></span> | <span data-ttu-id="cf34e-148">Enabled</span><span class="sxs-lookup"><span data-stu-id="cf34e-148">Enabled</span></span> |
       | <span data-ttu-id="cf34e-149">コンピューター上のファイルとプログラムのアクティビティを監視する</span><span class="sxs-lookup"><span data-stu-id="cf34e-149">Monitor file and program activity on your computer</span></span> | <span data-ttu-id="cf34e-150">Microsoft Defender ウイルス対策 エンジンは、ファイルの変更 (ファイルの書き込み (移動、コピー、変更など) と一般的なプログラム アクティビティ (開いているか実行され、他のプログラムが実行されるプログラム) を記録します。</span><span class="sxs-lookup"><span data-stu-id="cf34e-150">The Microsoft Defender Antivirus engine makes note of any file changes (file writes, such as moves, copies, or modifications) and general program activity (programs that are opened or running and that cause other programs to run).</span></span> | <span data-ttu-id="cf34e-151">Enabled</span><span class="sxs-lookup"><span data-stu-id="cf34e-151">Enabled</span></span> |
       | <span data-ttu-id="cf34e-152">生のボリューム書き込み通知を有効にする</span><span class="sxs-lookup"><span data-stu-id="cf34e-152">Turn on raw volume write notifications</span></span> | <span data-ttu-id="cf34e-153">生のボリューム書き込みに関する情報は、動作の監視によって分析されます。</span><span class="sxs-lookup"><span data-stu-id="cf34e-153">Information about raw volume writes will be analyzed by behavior monitoring.</span></span> | <span data-ttu-id="cf34e-154">Enabled</span><span class="sxs-lookup"><span data-stu-id="cf34e-154">Enabled</span></span> |
       | <span data-ttu-id="cf34e-155">リアルタイム保護が有効な場合は常にプロセス スキャンを有効にする</span><span class="sxs-lookup"><span data-stu-id="cf34e-155">Turn on process scanning whenever real-time protection is enabled</span></span> | <span data-ttu-id="cf34e-156">システム エンジンが実行中のプロセスMicrosoft Defender ウイルス対策、疑わしい変更や動作をスキャンする機能を個別に有効にできます。</span><span class="sxs-lookup"><span data-stu-id="cf34e-156">You can independently enable the Microsoft Defender Antivirus engine to scan running processes for suspicious modifications or behaviors.</span></span> <span data-ttu-id="cf34e-157">これは、リアルタイム保護を一時的に無効にし、無効になっている間に開始されたプロセスを自動的にスキャンする場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="cf34e-157">This is useful if you have temporarily disabled real-time protection and want to automatically scan processes that started while it was disabled.</span></span> | <span data-ttu-id="cf34e-158">Enabled</span><span class="sxs-lookup"><span data-stu-id="cf34e-158">Enabled</span></span> |
       | <span data-ttu-id="cf34e-159">スキャンするダウンロード ファイルと添付ファイルの最大サイズを定義する</span><span class="sxs-lookup"><span data-stu-id="cf34e-159">Define the maximum size of downloaded files and attachments to be scanned</span></span> | <span data-ttu-id="cf34e-160">サイズはキロバイト単位で定義できます。</span><span class="sxs-lookup"><span data-stu-id="cf34e-160">You can define the size in kilobytes.</span></span> | <span data-ttu-id="cf34e-161">Enabled</span><span class="sxs-lookup"><span data-stu-id="cf34e-161">Enabled</span></span> |
       | <span data-ttu-id="cf34e-162">オンの動作監視用にローカル設定の上書きを構成する</span><span class="sxs-lookup"><span data-stu-id="cf34e-162">Configure local setting override for turn on behavior monitoring</span></span> | <span data-ttu-id="cf34e-163">動作監視の構成に対してローカルオーバーライドを構成します。</span><span class="sxs-lookup"><span data-stu-id="cf34e-163">Configure a local override for the configuration of behavior monitoring.</span></span> <span data-ttu-id="cf34e-164">この設定は、グループ ポリシーでのみ設定できます。</span><span class="sxs-lookup"><span data-stu-id="cf34e-164">This setting can only be set by Group Policy.</span></span> <span data-ttu-id="cf34e-165">この設定を有効にすると、ローカルの基本設定がグループ ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="cf34e-165">If you enable this setting, the local preference setting will take priority over Group Policy.</span></span> <span data-ttu-id="cf34e-166">この設定を無効にするか構成しない場合、グループ ポリシーはローカルの基本設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="cf34e-166">If you disable or do not configure this setting, Group Policy will take priority over the local preference setting.</span></span>| <span data-ttu-id="cf34e-167">Enabled</span><span class="sxs-lookup"><span data-stu-id="cf34e-167">Enabled</span></span> |
       | <span data-ttu-id="cf34e-168">ダウンロードしたファイルと添付ファイルをスキャンするローカル設定の上書きを構成する</span><span class="sxs-lookup"><span data-stu-id="cf34e-168">Configure local setting override for scanning all downloaded files and attachments</span></span> | <span data-ttu-id="cf34e-169">ダウンロードしたファイルと添付ファイルのスキャンの構成に対してローカルオーバーライドを構成します。</span><span class="sxs-lookup"><span data-stu-id="cf34e-169">Configure a local override for the configuration of scanning for all downloaded files and attachments.</span></span> <span data-ttu-id="cf34e-170">この設定は、グループ ポリシーでのみ設定できます。</span><span class="sxs-lookup"><span data-stu-id="cf34e-170">This setting can only be set by Group Policy.</span></span> <span data-ttu-id="cf34e-171">この設定を有効にすると、ローカルの基本設定がグループ ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="cf34e-171">If you enable this setting, the local preference setting will take priority over Group Policy.</span></span> <span data-ttu-id="cf34e-172">この設定を無効にするか構成しない場合、グループ ポリシーはローカルの基本設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="cf34e-172">If you disable or do not configure this setting, Group Policy will take priority over the local preference setting.</span></span>| <span data-ttu-id="cf34e-173">Enabled</span><span class="sxs-lookup"><span data-stu-id="cf34e-173">Enabled</span></span> |
       | <span data-ttu-id="cf34e-174">コンピューター上のファイルとプログラムのアクティビティを監視するローカル設定の上書きを構成する</span><span class="sxs-lookup"><span data-stu-id="cf34e-174">Configure local setting override for monitoring file and program activity on your computer</span></span> | <span data-ttu-id="cf34e-175">コンピューター上のファイルとプログラムのアクティビティを監視する構成のローカル オーバーライドを構成します。</span><span class="sxs-lookup"><span data-stu-id="cf34e-175">Configure a local override for the configuration of monitoring for file and program activity on your computer.</span></span> <span data-ttu-id="cf34e-176">この設定は、グループ ポリシーでのみ設定できます。</span><span class="sxs-lookup"><span data-stu-id="cf34e-176">This setting can only be set by Group Policy.</span></span> <span data-ttu-id="cf34e-177">この設定を有効にすると、ローカルの基本設定がグループ ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="cf34e-177">If you enable this setting, the local preference setting will take priority over Group Policy.</span></span> <span data-ttu-id="cf34e-178">この設定を無効にするか構成しない場合、グループ ポリシーはローカルの基本設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="cf34e-178">If you disable or do not configure this setting, Group Policy will take priority over the local preference setting.</span></span>| <span data-ttu-id="cf34e-179">Enabled</span><span class="sxs-lookup"><span data-stu-id="cf34e-179">Enabled</span></span> |
       | <span data-ttu-id="cf34e-180">ローカル設定の上書きを構成してリアルタイム保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="cf34e-180">Configure local setting override to turn on real-time protection</span></span> | <span data-ttu-id="cf34e-181">リアルタイム保護を有効にする構成のローカルオーバーライドを構成します。</span><span class="sxs-lookup"><span data-stu-id="cf34e-181">Configure a local override for the configuration to turn on real-time protection.</span></span> <span data-ttu-id="cf34e-182">この設定は、グループ ポリシーでのみ設定できます。</span><span class="sxs-lookup"><span data-stu-id="cf34e-182">This setting can only be set by Group Policy.</span></span> <span data-ttu-id="cf34e-183">この設定を有効にすると、ローカルの基本設定がグループ ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="cf34e-183">If you enable this setting, the local preference setting will take priority over Group Policy.</span></span> <span data-ttu-id="cf34e-184">この設定を無効にするか構成しない場合、グループ ポリシーはローカルの基本設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="cf34e-184">If you disable or do not configure this setting, Group Policy will take priority over the local preference setting.</span></span>| <span data-ttu-id="cf34e-185">Enabled</span><span class="sxs-lookup"><span data-stu-id="cf34e-185">Enabled</span></span> |
       | <span data-ttu-id="cf34e-186">受信および送信ファイルのアクティビティを監視するローカル設定の上書きを構成する</span><span class="sxs-lookup"><span data-stu-id="cf34e-186">Configure local setting override for monitoring for incoming and outgoing file activity</span></span> | <span data-ttu-id="cf34e-187">受信および送信ファイルアクティビティの監視の構成に対してローカルオーバーライドを構成します。</span><span class="sxs-lookup"><span data-stu-id="cf34e-187">Configure a local override for the configuration of monitoring for incoming and outgoing file activity.</span></span> <span data-ttu-id="cf34e-188">この設定は、グループ ポリシーでのみ設定できます。</span><span class="sxs-lookup"><span data-stu-id="cf34e-188">This setting can only be set by Group Policy.</span></span> <span data-ttu-id="cf34e-189">この設定を有効にすると、ローカルの基本設定がグループ ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="cf34e-189">If you enable this setting, the local preference setting will take priority over Group Policy.</span></span> <span data-ttu-id="cf34e-190">この設定を無効にするか構成しない場合、グループ ポリシーはローカルの基本設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="cf34e-190">If you disable or do not configure this setting, Group Policy will take priority over the local preference setting.</span></span> | <span data-ttu-id="cf34e-191">Enabled</span><span class="sxs-lookup"><span data-stu-id="cf34e-191">Enabled</span></span> |
       | <span data-ttu-id="cf34e-192">受信および送信のファイルとプログラムのアクティビティの監視を構成する</span><span class="sxs-lookup"><span data-stu-id="cf34e-192">Configure monitoring for incoming and outgoing file and program activity</span></span> | <span data-ttu-id="cf34e-193">受信方向、発信方向、両方方向、どちらの方向でも監視を行う必要があるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="cf34e-193">Specify whether monitoring should occur on incoming, outgoing, both, or neither direction.</span></span> <span data-ttu-id="cf34e-194">これは、特定のサーバー Windows定義したサーバーまたはサーバーの役割が 1 つの方向にのみ大量のファイル変更を表示し、ネットワーク パフォーマンスを向上させる必要があるサーバー インストールに関連します。</span><span class="sxs-lookup"><span data-stu-id="cf34e-194">This is relevant for Windows Server installations where you have defined specific servers or Server Roles that see large amounts of file changes in only one direction and you want to improve network performance.</span></span> <span data-ttu-id="cf34e-195">ネットワーク上の完全に更新されたエンドポイント (およびサーバー) は、ファイルの変更の数や方向に関係なく、パフォーマンスにほとんど影響しません。</span><span class="sxs-lookup"><span data-stu-id="cf34e-195">Fully updated endpoints (and servers) on a network will see little performance impact irrespective of the number or direction of file changes.</span></span> | <span data-ttu-id="cf34e-196">有効 (両方向)</span><span class="sxs-lookup"><span data-stu-id="cf34e-196">Enabled (both directions)</span></span> |

    1. <span data-ttu-id="cf34e-197">必要に応じて設定を構成し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="cf34e-197">Configure the setting as appropriate, and click **OK**.</span></span>
    
    1. <span data-ttu-id="cf34e-198">表の各設定について、前の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="cf34e-198">Repeat the previous steps for each setting in the table.</span></span>

5. <span data-ttu-id="cf34e-199">[スキャン ポリシー Microsoft Defender ウイルス対策構成します。</span><span class="sxs-lookup"><span data-stu-id="cf34e-199">Configure the Microsoft Defender Antivirus scanning policy setting.</span></span> <span data-ttu-id="cf34e-200">これを行うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cf34e-200">To do this:</span></span>  

    1. <span data-ttu-id="cf34e-201">左側のウィンドウ **Microsoft Defender ウイルス対策** ツリーで、[スキャン] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="cf34e-201">From the **Microsoft Defender Antivirus** tree on left pane, click **Scan**.</span></span>
    
       ![Microsoft Defender ウイルス対策スキャン オプション](images/gpedit-windows-defender-antivirus-scan.png)

    1. <span data-ttu-id="cf34e-203">右側の **[スキャン** の詳細] ウィンドウで、次の表で指定したポリシー設定をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf34e-203">In the **Scan** details pane on right, double-click the policy setting as specified in the following table:</span></span>

       | <span data-ttu-id="cf34e-204">Setting</span><span class="sxs-lookup"><span data-stu-id="cf34e-204">Setting</span></span> | <span data-ttu-id="cf34e-205">説明</span><span class="sxs-lookup"><span data-stu-id="cf34e-205">Description</span></span> | <span data-ttu-id="cf34e-206">既定の設定</span><span class="sxs-lookup"><span data-stu-id="cf34e-206">Default setting</span></span> |
       |-----------------------------|------------------------|-------------------------------|    
       | <span data-ttu-id="cf34e-207">ヒューリスティックを有効にする</span><span class="sxs-lookup"><span data-stu-id="cf34e-207">Turn on heuristics</span></span> | <span data-ttu-id="cf34e-208">ヒューリスティック保護は、アクティビティの検出を求Microsoft Defender ウイルス対策される直前に、疑わしいアクティビティを無効またはブロックします。</span><span class="sxs-lookup"><span data-stu-id="cf34e-208">Heuristic protection will disable or block suspicious activity immediately before the Microsoft Defender Antivirus engine is asked to detect the activity.</span></span> | <span data-ttu-id="cf34e-209">Enabled</span><span class="sxs-lookup"><span data-stu-id="cf34e-209">Enabled</span></span> |

    1. <span data-ttu-id="cf34e-210">必要に応じて設定を構成し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="cf34e-210">Configure the setting as appropriate, and click **OK**.</span></span>
    
6. <span data-ttu-id="cf34e-211">[ローカル **グループ ポリシー エディターを閉じる] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="cf34e-211">Close **Local Group Policy Editor**.</span></span>


## <a name="disable-real-time-protection-in-group-policy"></a><span data-ttu-id="cf34e-212">グループ ポリシーでリアルタイム保護を無効にする</span><span class="sxs-lookup"><span data-stu-id="cf34e-212">Disable real-time protection in Group Policy</span></span>

> [!WARNING]
> <span data-ttu-id="cf34e-213">リアルタイム保護を無効にすると、エンドポイントの保護が大幅に低下し、推奨されません。</span><span class="sxs-lookup"><span data-stu-id="cf34e-213">Disabling real-time protection drastically reduces the protection on your endpoints and is not recommended.</span></span>

<span data-ttu-id="cf34e-214">メインのリアルタイム保護機能は既定で有効になっていますが、ローカル グループ ポリシー エディターを使用 **して無効にできます**。</span><span class="sxs-lookup"><span data-stu-id="cf34e-214">The main real-time protection capability is enabled by default, but you can disable it by using **Local Group Policy Editor**.</span></span>

<span data-ttu-id="cf34e-215">グループ ポリシーでリアルタイム保護を無効にするには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="cf34e-215">To disable real-time protection in Group policy:</span></span>

1. <span data-ttu-id="cf34e-216">[ローカル **グループ ポリシー エディター] を開きます**。</span><span class="sxs-lookup"><span data-stu-id="cf34e-216">Open **Local Group Policy Editor**.</span></span>

   1. <span data-ttu-id="cf34e-217">[タスク バー Windows 10] ボックスに **「gpedit」と入力します**。</span><span class="sxs-lookup"><span data-stu-id="cf34e-217">In your Windows 10 taskbar search box, type **gpedit**.</span></span>
   
   1. <span data-ttu-id="cf34e-218">[最適 **な一致]** で、[グループ ポリシー **の編集] をクリックして** ローカル **グループ ポリシー エディターを起動します**。</span><span class="sxs-lookup"><span data-stu-id="cf34e-218">Under **Best match**, click **Edit group policy** to launch **Local Group Policy Editor**.</span></span>

2.  <span data-ttu-id="cf34e-219">ローカル グループ ポリシー エディターの **左側のウィンドウ** で、ツリーを [コンピューターの構成] [管理用テンプレート] Windows[Microsoft Defender ウイルス対策リアルタイム保護] に  >    >    >    >  **展開します**。</span><span class="sxs-lookup"><span data-stu-id="cf34e-219">In the left pane of **Local Group Policy Editor**, expand the tree to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Real-time Protection**.</span></span>

3. <span data-ttu-id="cf34e-220">右側の **[リアルタイム保護の詳細]** ウィンドウで、[リアルタイム保護をオフ **にする] をダブルクリックします**。</span><span class="sxs-lookup"><span data-stu-id="cf34e-220">In the **Real-time Protection** details pane on right, double-click **Turn off real-time protection**.</span></span>

   ![リアルタイム保護をオフにする](images/gpedit-turn-off-real-time-protection.png)

4. <span data-ttu-id="cf34e-222">[リアルタイム **保護をオフにする] 設定** ウィンドウで、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="cf34e-222">In the **Turn off real-time protection** setting window, set the option to **Enabled**.</span></span>

   ![リアルタイム保護を有効にする](images/gpedit-turn-off-real-time-protection-enabled.png)
   
5. <span data-ttu-id="cf34e-224">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf34e-224">Click **OK**.</span></span>

6. <span data-ttu-id="cf34e-225">[ローカル **グループ ポリシー エディターを閉じる] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="cf34e-225">Close **Local Group Policy Editor**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="cf34e-226">関連記事</span><span class="sxs-lookup"><span data-stu-id="cf34e-226">Related articles</span></span>

- [<span data-ttu-id="cf34e-227">行動、ヒューリスティック、リアルタイム保護を構成する</span><span class="sxs-lookup"><span data-stu-id="cf34e-227">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)
- [<span data-ttu-id="cf34e-228">Microsoft Defender ウイルス対策 (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="cf34e-228">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)