---
title: 'ファイルのインジケーターを作成 '
ms.reviewer: ''
description: エンティティの検出、防止、除外を定義するファイル ハッシュのインジケーターを作成します。
keywords: ファイル、ハッシュ、管理、許可、ブロック、ブロック、クリーン、悪意のある、ファイル ハッシュ、IP アドレス、URL、ドメイン
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b56a18e1b35b65629318ab29f2189ef1f73373f5
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256917"
---
# <a name="create-indicators-for-files"></a><span data-ttu-id="fea2c-104">ファイルのインジケーターを作成 </span><span class="sxs-lookup"><span data-stu-id="fea2c-104">Create indicators for files</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fea2c-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="fea2c-105">**Applies to:**</span></span>
- [<span data-ttu-id="fea2c-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="fea2c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fea2c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fea2c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="fea2c-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="fea2c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fea2c-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="fea2c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="fea2c-110">悪意のある可能性のあるファイルやマルウェアの疑いを禁止することで、組織での攻撃の伝播をさらに防ぐ。</span><span class="sxs-lookup"><span data-stu-id="fea2c-110">Prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="fea2c-111">悪意のある可能性のあるポータブル実行可能ファイル (PE) ファイルが分かっている場合は、そのファイルをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="fea2c-111">If you know a potentially malicious portable executable (PE) file, you can block it.</span></span> <span data-ttu-id="fea2c-112">この操作によって、組織内のデバイスで読み取り、書き込み、または実行されるのを防ぐ。</span><span class="sxs-lookup"><span data-stu-id="fea2c-112">This operation will prevent it from being read, written, or executed on devices in your organization.</span></span>

<span data-ttu-id="fea2c-113">ファイルのインジケーターを作成するには、次の 3 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="fea2c-113">There are three ways you can create indicators for files:</span></span>

- <span data-ttu-id="fea2c-114">設定ページからインジケーターを作成する</span><span class="sxs-lookup"><span data-stu-id="fea2c-114">By creating an indicator through the settings page</span></span>
- <span data-ttu-id="fea2c-115">ファイルの詳細ページからインジケーターの追加ボタンを使用してコンテキスト インジケーターを作成する</span><span class="sxs-lookup"><span data-stu-id="fea2c-115">By creating a contextual indicator using the add indicator button from the file details page</span></span>
- <span data-ttu-id="fea2c-116">インジケーター API を使用してインジケーター [を作成する](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="fea2c-116">By creating an indicator through the [Indicator API](ti-indicator.md)</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="fea2c-117">はじめに</span><span class="sxs-lookup"><span data-stu-id="fea2c-117">Before you begin</span></span>

<span data-ttu-id="fea2c-118">ファイルのインジケーターを作成する前に、次の前提条件を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="fea2c-118">It's important to understand the following prerequisites prior to creating indicators for files:</span></span>

- <span data-ttu-id="fea2c-119">この機能は、組織が (アクティブ モードで **)** Microsoft Defender ウイルス対策を使用し、クラウドベースの保護が有効 **になっている場合に使用できます**。</span><span class="sxs-lookup"><span data-stu-id="fea2c-119">This feature is available if your organization uses **Microsoft Defender Antivirus (in active mode)** and **Cloud-based protection is enabled**.</span></span> <span data-ttu-id="fea2c-120">詳細については、「クラウドベースの保護 [を管理する」を参照してください](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="fea2c-120">For more information, see [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span></span>

- <span data-ttu-id="fea2c-121">マルウェア対策クライアントのバージョンは、4.18.1901.x 以降である必要があります。</span><span class="sxs-lookup"><span data-stu-id="fea2c-121">The Antimalware client version must be 4.18.1901.x or later.</span></span> <span data-ttu-id="fea2c-122">「 [月次プラットフォームとエンジンのバージョン」を参照してください。](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)</span><span class="sxs-lookup"><span data-stu-id="fea2c-122">See [Monthly platform and engine versions](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)</span></span>

- <span data-ttu-id="fea2c-123">2019 年Windows 10バージョン 1703 以降のデバイスWindows Server 2016サポートされています。</span><span class="sxs-lookup"><span data-stu-id="fea2c-123">Supported on devices with Windows 10, version 1703 or later, Windows Server 2016 and 2019.</span></span>

- <span data-ttu-id="fea2c-124">ファイルのブロックを開始するには、まず、ファイルのブロックまたは許可 [機能](advanced-features.md)を有効にする設定。</span><span class="sxs-lookup"><span data-stu-id="fea2c-124">To start blocking files, you first need to [turn on the "block or allow" feature](advanced-features.md) in Settings.</span></span>

<span data-ttu-id="fea2c-125">この機能は、疑わしいマルウェア (または悪意のある可能性のあるファイル) が Web からダウンロードされるのを防ぐために設計されています。</span><span class="sxs-lookup"><span data-stu-id="fea2c-125">This feature is designed to prevent suspected malware (or potentially malicious files) from being downloaded from the web.</span></span> <span data-ttu-id="fea2c-126">現在、ポータブル実行可能ファイル (PE) ファイルがサポートされています 。このファイルには、.exeファイル.dllがあります。</span><span class="sxs-lookup"><span data-stu-id="fea2c-126">It currently supports portable executable (PE) files, including .exe and .dll files.</span></span> <span data-ttu-id="fea2c-127">対象範囲は時間の長い期間延長されます。</span><span class="sxs-lookup"><span data-stu-id="fea2c-127">The coverage will be extended over time.</span></span>

## <a name="create-an-indicator-for-files-from-the-settings-page"></a><span data-ttu-id="fea2c-128">設定ページからファイルのインジケーターを作成する</span><span class="sxs-lookup"><span data-stu-id="fea2c-128">Create an indicator for files from the settings page</span></span>

1. <span data-ttu-id="fea2c-129">ナビゲーション ウィンドウで、[インジケーター] **を設定 >します**。</span><span class="sxs-lookup"><span data-stu-id="fea2c-129">In the navigation pane, select **Settings > Indicators**.</span></span>

2. <span data-ttu-id="fea2c-130">[ファイル ハッシュ **] タブを選択**   します。</span><span class="sxs-lookup"><span data-stu-id="fea2c-130">Select the **File hash** tab.</span></span>

3. <span data-ttu-id="fea2c-131">[インジケーター **の追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fea2c-131">Select **Add indicator**.</span></span>

4. <span data-ttu-id="fea2c-132">次の詳細を指定します。</span><span class="sxs-lookup"><span data-stu-id="fea2c-132">Specify the following details:</span></span>
    - <span data-ttu-id="fea2c-133">Indicator - エンティティの詳細を指定し、インジケーターの有効期限を定義します。</span><span class="sxs-lookup"><span data-stu-id="fea2c-133">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
    - <span data-ttu-id="fea2c-134">Action - 実行するアクションを指定し、説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="fea2c-134">Action - Specify the action to be taken and provide a description.</span></span>
    - <span data-ttu-id="fea2c-135">Scope - デバイス グループのスコープを定義します。</span><span class="sxs-lookup"><span data-stu-id="fea2c-135">Scope - Define the scope of the device group.</span></span>

5. <span data-ttu-id="fea2c-136">[概要] タブで詳細を確認し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="fea2c-136">Review the details in the Summary tab, then select **Save**.</span></span>

## <a name="create-a-contextual-indicator-from-the-file-details-page"></a><span data-ttu-id="fea2c-137">ファイルの詳細ページからコンテキスト インジケーターを作成する</span><span class="sxs-lookup"><span data-stu-id="fea2c-137">Create a contextual indicator from the file details page</span></span>

<span data-ttu-id="fea2c-138">ファイルに対して応答アクションを実行 [する場合のオプションの 1](respond-file-alerts.md)つは   、ファイルのインジケーターを追加することです。</span><span class="sxs-lookup"><span data-stu-id="fea2c-138">One of the options when taking [response actions on a file](respond-file-alerts.md) is adding an indicator for the file.</span></span> <span data-ttu-id="fea2c-139">ファイルのインジケーター ハッシュを追加すると、組織内のデバイスがファイルの実行を試みるたびに、アラートを発生してファイルをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="fea2c-139">When you add an indicator hash for a file, you can choose to raise an alert and block the file whenever a device in your organization attempts to run it.</span></span>

<span data-ttu-id="fea2c-140">インジケーターによって自動的にブロックされたファイルは、ファイルのアクション センターには表示されませんが、アラートはアラート キューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="fea2c-140">Files automatically blocked by an indicator won't show up in the file's Action center, but the alerts will still be visible in the Alerts queue.</span></span>

>[!IMPORTANT]
>- <span data-ttu-id="fea2c-141">通常、ファイル ブロックは数分以内に適用および削除されますが、30 分以上かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="fea2c-141">Typically, file blocks are enforced and removed within a couple of minutes, but can take upwards of 30 minutes.</span></span>
> 
>- <span data-ttu-id="fea2c-142">同じ適用の種類とターゲットを持つファイル IoC ポリシーが競合している場合は、より安全なハッシュのポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="fea2c-142">If there are conflicting file IoC policies with the same enforcement type and target, the policy of the more secure hash will be applied.</span></span> <span data-ttu-id="fea2c-143">SHA-256 ファイル ハッシュ IoC ポリシーは SHA-1 ファイル ハッシュ IoC ポリシーに勝ちます。ハッシュの種類が同じファイルを定義している場合、MD5 ファイル ハッシュ IoC ポリシーに勝ちます。</span><span class="sxs-lookup"><span data-stu-id="fea2c-143">An SHA-256 file hash IoC policy will win over an SHA-1 file hash IoC policy, which will win over an MD5 file hash IoC policy if the hash types define the same file.</span></span> <span data-ttu-id="fea2c-144">これは、デバイス グループに関係なく常に true です。</span><span class="sxs-lookup"><span data-stu-id="fea2c-144">This is always true regardless of the device group.</span></span> 
>   <span data-ttu-id="fea2c-145">それ以外のすべての場合、同じ適用ターゲットを持つ競合するファイル IoC ポリシーがすべてのデバイスとデバイスのグループに適用されると、デバイスの場合、デバイス グループ内のポリシーが勝ちます。</span><span class="sxs-lookup"><span data-stu-id="fea2c-145">In all other cases, if conflicting file IoC policies with the same enforcement target are applied to all devices and to the device’s group, then for a device, the policy in the device group will win.</span></span> 
>   
>- <span data-ttu-id="fea2c-146">EnableFileHashComputation グループ ポリシーを無効にすると、ファイル IoC のブロック精度が低下します。</span><span class="sxs-lookup"><span data-stu-id="fea2c-146">If the EnableFileHashComputation group policy is disabled, the blocking accuracy of the file IoC is reduced.</span></span> <span data-ttu-id="fea2c-147">ただし、有効にすると、 `EnableFileHashComputation` デバイスのパフォーマンスに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fea2c-147">However, enabling `EnableFileHashComputation` may impact device performance.</span></span> <span data-ttu-id="fea2c-148">たとえば、ネットワーク共有からローカル デバイス (特に VPN 接続を使用して) に大きなファイルをコピーすると、デバイスのパフォーマンスに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fea2c-148">For example, copying large files from a network share onto your local device, especially over a VPN connection, might have an effect on device performance.</span></span>
>
>   <span data-ttu-id="fea2c-149">EnableFileHashComputation グループ ポリシーの詳細については [、「Defender CSP」を参照してください。](/windows/client-management/mdm/defender-csp)</span><span class="sxs-lookup"><span data-stu-id="fea2c-149">For more information about the EnableFileHashComputation group policy, see [Defender CSP](/windows/client-management/mdm/defender-csp)</span></span>

## <a name="policy-conflict-handling"></a><span data-ttu-id="fea2c-150">ポリシーの競合の処理</span><span class="sxs-lookup"><span data-stu-id="fea2c-150">Policy conflict handling</span></span>  

<span data-ttu-id="fea2c-151">Cert および File IoC ポリシー処理の競合は、次の順序に従います。</span><span class="sxs-lookup"><span data-stu-id="fea2c-151">Cert and File IoC policy handling conflict will follow the below order:</span></span>

- <span data-ttu-id="fea2c-152">アプリケーションコントロールと AppLocker の強制モード ポリシー/Windows Defenderによってファイルが許可されていない場合は、[**ブロック**]</span><span class="sxs-lookup"><span data-stu-id="fea2c-152">If the file is not allowed by Windows Defender Application Control and AppLocker enforce mode policy/policies, then **Block**</span></span>

- <span data-ttu-id="fea2c-153">それ以外の場合は、ファイルが除外によって許可されている場合Microsoft Defender ウイルス対策許可する</span><span class="sxs-lookup"><span data-stu-id="fea2c-153">Else if the file is allowed by the Microsoft Defender Antivirus exclusion, then **Allow**</span></span>

- <span data-ttu-id="fea2c-154">それ以外の場合、ファイルがブロックまたは警告ファイル IoC によってブロックまたは警告される場合は、ブロック **/警告**</span><span class="sxs-lookup"><span data-stu-id="fea2c-154">Else if the file is blocked or warned by a block or warn file IoC, then **Block/Warn**</span></span>

- <span data-ttu-id="fea2c-155">それ以外の場合は、ファイルが許可ファイルの IoC ポリシーで許可されている場合は、[**許可**]</span><span class="sxs-lookup"><span data-stu-id="fea2c-155">Else if the file is allowed by an allow file IoC policy, then **Allow**</span></span>

- <span data-ttu-id="fea2c-156">それ以外の場合は、ASR ルール、CFA、AV、SmartScreen、その後ブロックによってファイルがブロック **されます**。</span><span class="sxs-lookup"><span data-stu-id="fea2c-156">Else if the file is blocked by ASR rules, CFA, AV, SmartScreen, then **Block**</span></span>  

- <span data-ttu-id="fea2c-157">Else **Allow** (アプリケーション制御Windows Defender AppLocker &に渡す場合、IoC ルールは適用されません)</span><span class="sxs-lookup"><span data-stu-id="fea2c-157">Else **Allow** (passes Windows Defender Application Control & AppLocker policy, no IoC rules apply to it)</span></span>

<span data-ttu-id="fea2c-158">同じ適用の種類とターゲットを持つファイル IoC ポリシーが競合している場合は、より安全な (長い) ハッシュのポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="fea2c-158">If there are conflicting file IoC policies with the same enforcement type and target, the policy of the more secure (meaning longer) hash will be applied.</span></span> <span data-ttu-id="fea2c-159">たとえば、SHA-256 ファイル ハッシュ IoC ポリシーは、両方のハッシュの種類が同じファイルを定義している場合、MD5 ファイル ハッシュ IoC ポリシーに勝ちます。</span><span class="sxs-lookup"><span data-stu-id="fea2c-159">For example, an SHA-256 file hash IoC policy will win over an MD5 file hash IoC policy if both hash types define the same file.</span></span>

<span data-ttu-id="fea2c-160">脅威と脆弱性の管理のブロック脆弱なアプリケーション機能は、ファイル IoC を適用に使用し、上記の競合処理順序に従います。</span><span class="sxs-lookup"><span data-stu-id="fea2c-160">Threat and vulnerability management's block vulnerable application features uses the file IoCs for enforcement and will follow the above conflict handling order.</span></span>

### <a name="examples"></a><span data-ttu-id="fea2c-161">例</span><span class="sxs-lookup"><span data-stu-id="fea2c-161">Examples</span></span>

|<span data-ttu-id="fea2c-162">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="fea2c-162">Component</span></span> |<span data-ttu-id="fea2c-163">コンポーネントの適用</span><span class="sxs-lookup"><span data-stu-id="fea2c-163">Component enforcement</span></span> |<span data-ttu-id="fea2c-164">ファイル インジケーター アクション</span><span class="sxs-lookup"><span data-stu-id="fea2c-164">File indicator Action</span></span> |<span data-ttu-id="fea2c-165">結果</span><span class="sxs-lookup"><span data-stu-id="fea2c-165">Result</span></span>
|--|--|--|--|
|<span data-ttu-id="fea2c-166">攻撃表面の縮小ファイル パスの除外</span><span class="sxs-lookup"><span data-stu-id="fea2c-166">Attack surface reduction file path exclusion</span></span> |<span data-ttu-id="fea2c-167">許可</span><span class="sxs-lookup"><span data-stu-id="fea2c-167">Allow</span></span> |<span data-ttu-id="fea2c-168">ブロック</span><span class="sxs-lookup"><span data-stu-id="fea2c-168">Block</span></span> |<span data-ttu-id="fea2c-169">ブロック</span><span class="sxs-lookup"><span data-stu-id="fea2c-169">Block</span></span>
|<span data-ttu-id="fea2c-170">攻撃表面の縮小ルール</span><span class="sxs-lookup"><span data-stu-id="fea2c-170">Attack surface reduction rule</span></span> |<span data-ttu-id="fea2c-171">ブロック</span><span class="sxs-lookup"><span data-stu-id="fea2c-171">Block</span></span> |<span data-ttu-id="fea2c-172">許可</span><span class="sxs-lookup"><span data-stu-id="fea2c-172">Allow</span></span> |<span data-ttu-id="fea2c-173">許可</span><span class="sxs-lookup"><span data-stu-id="fea2c-173">Allow</span></span>
|<span data-ttu-id="fea2c-174">Windows Defender Application Control</span><span class="sxs-lookup"><span data-stu-id="fea2c-174">Windows Defender Application Control</span></span> |<span data-ttu-id="fea2c-175">許可</span><span class="sxs-lookup"><span data-stu-id="fea2c-175">Allow</span></span> |<span data-ttu-id="fea2c-176">ブロック</span><span class="sxs-lookup"><span data-stu-id="fea2c-176">Block</span></span> |<span data-ttu-id="fea2c-177">許可</span><span class="sxs-lookup"><span data-stu-id="fea2c-177">Allow</span></span> |
|<span data-ttu-id="fea2c-178">Windows Defender Application Control</span><span class="sxs-lookup"><span data-stu-id="fea2c-178">Windows Defender Application Control</span></span> |<span data-ttu-id="fea2c-179">ブロック</span><span class="sxs-lookup"><span data-stu-id="fea2c-179">Block</span></span> |<span data-ttu-id="fea2c-180">許可</span><span class="sxs-lookup"><span data-stu-id="fea2c-180">Allow</span></span> |<span data-ttu-id="fea2c-181">ブロック</span><span class="sxs-lookup"><span data-stu-id="fea2c-181">Block</span></span>
|<span data-ttu-id="fea2c-182">Microsoft Defender ウイルス対策除外</span><span class="sxs-lookup"><span data-stu-id="fea2c-182">Microsoft Defender Antivirus exclusion</span></span> |<span data-ttu-id="fea2c-183">許可</span><span class="sxs-lookup"><span data-stu-id="fea2c-183">Allow</span></span> |<span data-ttu-id="fea2c-184">ブロック</span><span class="sxs-lookup"><span data-stu-id="fea2c-184">Block</span></span> |<span data-ttu-id="fea2c-185">許可</span><span class="sxs-lookup"><span data-stu-id="fea2c-185">Allow</span></span>

## <a name="see-also"></a><span data-ttu-id="fea2c-186">関連項目</span><span class="sxs-lookup"><span data-stu-id="fea2c-186">See also</span></span>

- [<span data-ttu-id="fea2c-187">インジケーターの作成</span><span class="sxs-lookup"><span data-stu-id="fea2c-187">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="fea2c-188">IP および URL/ドメインのインジケーターを作成</span><span class="sxs-lookup"><span data-stu-id="fea2c-188">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="fea2c-189">証明書に基づいてインジケーターを作成する</span><span class="sxs-lookup"><span data-stu-id="fea2c-189">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="fea2c-190">インジケーターの管理</span><span class="sxs-lookup"><span data-stu-id="fea2c-190">Manage indicators</span></span>](indicator-manage.md)
