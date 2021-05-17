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
ms.openlocfilehash: 103f5d0ad9d12a37f3a3b8065f39c24d592cc252
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995059"
---
# <a name="create-indicators-for-files"></a><span data-ttu-id="5696b-104">ファイルのインジケーターを作成 </span><span class="sxs-lookup"><span data-stu-id="5696b-104">Create indicators for files</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5696b-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="5696b-105">**Applies to:**</span></span>
- [<span data-ttu-id="5696b-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5696b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5696b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5696b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="5696b-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="5696b-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5696b-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="5696b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="5696b-110">悪意のある可能性のあるファイルやマルウェアの疑いを禁止することで、組織での攻撃の伝播をさらに防ぐ。</span><span class="sxs-lookup"><span data-stu-id="5696b-110">Prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="5696b-111">悪意のある可能性のあるポータブル実行可能ファイル (PE) ファイルが分かっている場合は、そのファイルをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="5696b-111">If you know a potentially malicious portable executable (PE) file, you can block it.</span></span> <span data-ttu-id="5696b-112">この操作によって、組織内のデバイスで読み取り、書き込み、または実行されるのを防ぐ。</span><span class="sxs-lookup"><span data-stu-id="5696b-112">This operation will prevent it from being read, written, or executed on devices in your organization.</span></span>

<span data-ttu-id="5696b-113">ファイルのインジケーターを作成するには、次の 3 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="5696b-113">There are three ways you can create indicators for files:</span></span>

- <span data-ttu-id="5696b-114">設定ページからインジケーターを作成する</span><span class="sxs-lookup"><span data-stu-id="5696b-114">By creating an indicator through the settings page</span></span>
- <span data-ttu-id="5696b-115">ファイルの詳細ページからインジケーターの追加ボタンを使用してコンテキスト インジケーターを作成する</span><span class="sxs-lookup"><span data-stu-id="5696b-115">By creating a contextual indicator using the add indicator button from the file details page</span></span>
- <span data-ttu-id="5696b-116">インジケーター API を使用してインジケーター [を作成する](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="5696b-116">By creating an indicator through the [Indicator API](ti-indicator.md)</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="5696b-117">はじめに</span><span class="sxs-lookup"><span data-stu-id="5696b-117">Before you begin</span></span>

<span data-ttu-id="5696b-118">ファイルのインジケーターを作成する前に、次の前提条件を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="5696b-118">It's important to understand the following prerequisites prior to creating indicators for files:</span></span>

- <span data-ttu-id="5696b-119">この機能は、組織が (アクティブ モードで **)** Microsoft Defender ウイルス対策を使用し、クラウドベースの保護が有効 **になっている場合に使用できます**。</span><span class="sxs-lookup"><span data-stu-id="5696b-119">This feature is available if your organization uses **Microsoft Defender Antivirus (in active mode)** and **Cloud-based protection is enabled**.</span></span> <span data-ttu-id="5696b-120">詳細については、「クラウドベースの保護 [を管理する」を参照してください](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="5696b-120">For more information, see [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span></span>

- <span data-ttu-id="5696b-121">マルウェア対策クライアントのバージョンは、4.18.1901.x 以降である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5696b-121">The Antimalware client version must be 4.18.1901.x or later.</span></span> <span data-ttu-id="5696b-122">「 [月次プラットフォームとエンジンのバージョン」を参照してください。](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)</span><span class="sxs-lookup"><span data-stu-id="5696b-122">See [Monthly platform and engine versions](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)</span></span>

- <span data-ttu-id="5696b-123">2019 年Windows 10バージョン 1703 以降のデバイスWindows Server 2016サポートされています。</span><span class="sxs-lookup"><span data-stu-id="5696b-123">Supported on devices with Windows 10, version 1703 or later, Windows Server 2016 and 2019.</span></span>

- <span data-ttu-id="5696b-124">ファイルのブロックを開始するには、まず、ファイルのブロックまたは許可 [機能](advanced-features.md)を有効にする設定。</span><span class="sxs-lookup"><span data-stu-id="5696b-124">To start blocking files, you first need to [turn on the "block or allow" feature](advanced-features.md) in Settings.</span></span>

<span data-ttu-id="5696b-125">この機能は、疑わしいマルウェア (または悪意のある可能性のあるファイル) が Web からダウンロードされるのを防ぐために設計されています。</span><span class="sxs-lookup"><span data-stu-id="5696b-125">This feature is designed to prevent suspected malware (or potentially malicious files) from being downloaded from the web.</span></span> <span data-ttu-id="5696b-126">現在、ポータブル実行可能ファイル (PE) ファイルがサポートされています 。このファイルには、.exeファイル.dllがあります。</span><span class="sxs-lookup"><span data-stu-id="5696b-126">It currently supports portable executable (PE) files, including .exe and .dll files.</span></span> <span data-ttu-id="5696b-127">対象範囲は時間の長い期間延長されます。</span><span class="sxs-lookup"><span data-stu-id="5696b-127">The coverage will be extended over time.</span></span>

## <a name="create-an-indicator-for-files-from-the-settings-page"></a><span data-ttu-id="5696b-128">設定ページからファイルのインジケーターを作成する</span><span class="sxs-lookup"><span data-stu-id="5696b-128">Create an indicator for files from the settings page</span></span>

1. <span data-ttu-id="5696b-129">ナビゲーション ウィンドウで、[インジケーター] **を設定 >します**。</span><span class="sxs-lookup"><span data-stu-id="5696b-129">In the navigation pane, select **Settings > Indicators**.</span></span>

2. <span data-ttu-id="5696b-130">[ファイル ハッシュ **] タブを選択**   します。</span><span class="sxs-lookup"><span data-stu-id="5696b-130">Select the **File hash** tab.</span></span>

3. <span data-ttu-id="5696b-131">[インジケーター **の追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5696b-131">Select **Add indicator**.</span></span>

4. <span data-ttu-id="5696b-132">次の詳細を指定します。</span><span class="sxs-lookup"><span data-stu-id="5696b-132">Specify the following details:</span></span>
    - <span data-ttu-id="5696b-133">Indicator - エンティティの詳細を指定し、インジケーターの有効期限を定義します。</span><span class="sxs-lookup"><span data-stu-id="5696b-133">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
    - <span data-ttu-id="5696b-134">Action - 実行するアクションを指定し、説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="5696b-134">Action - Specify the action to be taken and provide a description.</span></span>
    - <span data-ttu-id="5696b-135">Scope - デバイス グループのスコープを定義します。</span><span class="sxs-lookup"><span data-stu-id="5696b-135">Scope - Define the scope of the device group.</span></span>

5. <span data-ttu-id="5696b-136">[概要] タブで詳細を確認し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="5696b-136">Review the details in the Summary tab, then select **Save**.</span></span>

## <a name="create-a-contextual-indicator-from-the-file-details-page"></a><span data-ttu-id="5696b-137">ファイルの詳細ページからコンテキスト インジケーターを作成する</span><span class="sxs-lookup"><span data-stu-id="5696b-137">Create a contextual indicator from the file details page</span></span>

<span data-ttu-id="5696b-138">ファイルに対して応答アクションを実行 [する場合のオプションの 1](respond-file-alerts.md)つは   、ファイルのインジケーターを追加することです。</span><span class="sxs-lookup"><span data-stu-id="5696b-138">One of the options when taking [response actions on a file](respond-file-alerts.md) is adding an indicator for the file.</span></span> <span data-ttu-id="5696b-139">ファイルのインジケーター ハッシュを追加すると、組織内のデバイスがファイルの実行を試みるたびに、アラートを発生してファイルをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="5696b-139">When you add an indicator hash for a file, you can choose to raise an alert and block the file whenever a device in your organization attempts to run it.</span></span>

<span data-ttu-id="5696b-140">インジケーターによって自動的にブロックされたファイルは、ファイルのアクション センターには表示されませんが、アラートはアラート キューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5696b-140">Files automatically blocked by an indicator won't show up in the file's Action center, but the alerts will still be visible in the Alerts queue.</span></span>

>[!IMPORTANT]
>- <span data-ttu-id="5696b-141">通常、ファイル ブロックは数分以内に適用および削除されますが、30 分以上かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5696b-141">Typically, file blocks are enforced and removed within a couple of minutes, but can take upwards of 30 minutes.</span></span>
>- <span data-ttu-id="5696b-142">ファイル インジケーター ポリシーが競合している場合は、より安全なポリシーの適用ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="5696b-142">If there are conflicting file indicator policies, the enforcement policy of the more secure policy is applied.</span></span> <span data-ttu-id="5696b-143">たとえば、両方のハッシュの種類が同じファイルを定義している場合、SHA-256 ファイル ハッシュ インジケーター ポリシーが MD5 ファイル ハッシュ インジケーター ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="5696b-143">For example, a SHA-256 file hash indicator policy takes precedence over an MD5 file hash indicator policy if both hash types define the same file.</span></span>
>- <span data-ttu-id="5696b-144">EnableFileHashComputation グループ ポリシーを無効にすると、ファイル IoC のブロック精度が低下します。</span><span class="sxs-lookup"><span data-stu-id="5696b-144">If EnableFileHashComputation group policy is disabled, the blocking accuracy of the file IoC is reduced.</span></span> <span data-ttu-id="5696b-145">ただし、EnableFileHashComputation を有効にすると、デバイスのパフォーマンスに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5696b-145">However, enabling EnableFileHashComputation may impact device performance.</span></span>
>    - <span data-ttu-id="5696b-146">たとえば、ネットワーク共有からローカル デバイス (特に VPN 接続を使用して) に大きなファイルをコピーすると、デバイスのパフォーマンスに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5696b-146">For example, copying large files from a network share onto your local device, especially over a VPN connection, may have an effect on device performance.</span></span>
>    - <span data-ttu-id="5696b-147">EnableFileHashComputation グループ ポリシーの詳細については [、「Defender CSP」を参照してください。](/windows/client-management/mdm/defender-csp)</span><span class="sxs-lookup"><span data-stu-id="5696b-147">For more information about the EnableFileHashComputation group policy, see [Defender CSP](/windows/client-management/mdm/defender-csp)</span></span>

## <a name="policy-conflict-handling"></a><span data-ttu-id="5696b-148">ポリシーの競合の処理</span><span class="sxs-lookup"><span data-stu-id="5696b-148">Policy conflict handling</span></span>  

<span data-ttu-id="5696b-149">Cert および File IoC ポリシー処理の競合は、次の順序に従います。</span><span class="sxs-lookup"><span data-stu-id="5696b-149">Cert and File IoC policy handling conflict will follow the below order:</span></span>

- <span data-ttu-id="5696b-150">アプリケーションコントロールと AppLocker の強制モード ポリシー/Windows Defenderによってファイルが許可されていない場合は、[**ブロック**]</span><span class="sxs-lookup"><span data-stu-id="5696b-150">If the file is not allowed by Windows Defender Application Control and AppLocker enforce mode policy/policies, then **Block**</span></span>

- <span data-ttu-id="5696b-151">それ以外の場合は、Defender ウイルス対策除外でファイルが許可されている場合は、[ **許可]**</span><span class="sxs-lookup"><span data-stu-id="5696b-151">Else if the file is allowed by the Defender Anti-Virus Exclusion, then **Allow**</span></span>

- <span data-ttu-id="5696b-152">それ以外の場合、ファイルがブロックまたは警告ファイル IoC によってブロックまたは警告される場合は、ブロック **/警告**</span><span class="sxs-lookup"><span data-stu-id="5696b-152">Else if the file is blocked or warned by a block or warn file IoC, then **Block/Warn**</span></span>

- <span data-ttu-id="5696b-153">それ以外の場合は、ファイルが許可ファイル IOC ポリシーで許可されている場合は、[**許可**]</span><span class="sxs-lookup"><span data-stu-id="5696b-153">Else if the file is allowed by an allow file IOC policy, then **Allow**</span></span>

- <span data-ttu-id="5696b-154">それ以外の場合は、ASR ルール、CFA、AV、SmartScreen、その後ブロックによってファイルがブロック **されます**。</span><span class="sxs-lookup"><span data-stu-id="5696b-154">Else if the file is blocked by ASR rules, CFA, AV, SmartScreen, then **Block**</span></span>  

- <span data-ttu-id="5696b-155">Else **Allow** (アプリケーション制御Windows Defender AppLocker &に渡す場合、IoC ルールは適用されません)</span><span class="sxs-lookup"><span data-stu-id="5696b-155">Else **Allow** (passes Windows Defender Application Control & AppLocker policy, no IoC rules apply to it)</span></span>

<span data-ttu-id="5696b-156">同じ適用の種類とターゲットを持つファイル IoC ポリシーが競合している場合は、より安全な (長い) ハッシュのポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="5696b-156">If there are conflicting file IoC policies with the same enforcement type and target, the policy of the more secure (meaning longer) hash will be applied.</span></span> <span data-ttu-id="5696b-157">たとえば、SHA-256 ファイル ハッシュ IoC ポリシーは、両方のハッシュの種類が同じファイルを定義している場合、MD5 ファイル ハッシュ IoC ポリシーに勝ちます。</span><span class="sxs-lookup"><span data-stu-id="5696b-157">For example, a SHA-256 file hash IoC policy will win over a MD5 file hash IoC policy if both hash types define the same file.</span></span>

<span data-ttu-id="5696b-158">このブロック脅威と脆弱性の管理脆弱なアプリケーション機能は、ファイル IoC を適用に使用し、上記の競合処理順序に従います。</span><span class="sxs-lookup"><span data-stu-id="5696b-158">Note that threat and vulnerability management's block vulnerable application features uses the file IoCs for enforcement and will follow the above conflict handling order.</span></span>

### <a name="examples"></a><span data-ttu-id="5696b-159">例</span><span class="sxs-lookup"><span data-stu-id="5696b-159">Examples</span></span>

|<span data-ttu-id="5696b-160">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5696b-160">Component</span></span> |<span data-ttu-id="5696b-161">コンポーネントの適用</span><span class="sxs-lookup"><span data-stu-id="5696b-161">Component enforcement</span></span> |<span data-ttu-id="5696b-162">ファイル インジケーター アクション</span><span class="sxs-lookup"><span data-stu-id="5696b-162">File indicator Action</span></span> |<span data-ttu-id="5696b-163">結果</span><span class="sxs-lookup"><span data-stu-id="5696b-163">Result</span></span>
|--|--|--|--|
|<span data-ttu-id="5696b-164">攻撃表面の縮小ファイル パスの除外</span><span class="sxs-lookup"><span data-stu-id="5696b-164">Attack surface reduction file path exclusion</span></span> |<span data-ttu-id="5696b-165">許可</span><span class="sxs-lookup"><span data-stu-id="5696b-165">Allow</span></span> |<span data-ttu-id="5696b-166">ブロック</span><span class="sxs-lookup"><span data-stu-id="5696b-166">Block</span></span> |<span data-ttu-id="5696b-167">ブロック</span><span class="sxs-lookup"><span data-stu-id="5696b-167">Block</span></span>
|<span data-ttu-id="5696b-168">攻撃表面の縮小ルール</span><span class="sxs-lookup"><span data-stu-id="5696b-168">Attack surface reduction rule</span></span> |<span data-ttu-id="5696b-169">ブロック</span><span class="sxs-lookup"><span data-stu-id="5696b-169">Block</span></span> |<span data-ttu-id="5696b-170">許可</span><span class="sxs-lookup"><span data-stu-id="5696b-170">Allow</span></span> |<span data-ttu-id="5696b-171">許可</span><span class="sxs-lookup"><span data-stu-id="5696b-171">Allow</span></span>
|<span data-ttu-id="5696b-172">Windows Defender Application Control</span><span class="sxs-lookup"><span data-stu-id="5696b-172">Windows Defender Application Control</span></span> |<span data-ttu-id="5696b-173">許可</span><span class="sxs-lookup"><span data-stu-id="5696b-173">Allow</span></span> |<span data-ttu-id="5696b-174">ブロック</span><span class="sxs-lookup"><span data-stu-id="5696b-174">Block</span></span> |<span data-ttu-id="5696b-175">許可</span><span class="sxs-lookup"><span data-stu-id="5696b-175">Allow</span></span> |
|<span data-ttu-id="5696b-176">Windows Defender Application Control</span><span class="sxs-lookup"><span data-stu-id="5696b-176">Windows Defender Application Control</span></span> |<span data-ttu-id="5696b-177">ブロック</span><span class="sxs-lookup"><span data-stu-id="5696b-177">Block</span></span> |<span data-ttu-id="5696b-178">許可</span><span class="sxs-lookup"><span data-stu-id="5696b-178">Allow</span></span> |<span data-ttu-id="5696b-179">ブロック</span><span class="sxs-lookup"><span data-stu-id="5696b-179">Block</span></span>
|<span data-ttu-id="5696b-180">Microsoft Defender ウイルス対策除外</span><span class="sxs-lookup"><span data-stu-id="5696b-180">Microsoft Defender Antivirus exclusion</span></span> |<span data-ttu-id="5696b-181">許可</span><span class="sxs-lookup"><span data-stu-id="5696b-181">Allow</span></span> |<span data-ttu-id="5696b-182">ブロック</span><span class="sxs-lookup"><span data-stu-id="5696b-182">Block</span></span> |<span data-ttu-id="5696b-183">許可</span><span class="sxs-lookup"><span data-stu-id="5696b-183">Allow</span></span>

## <a name="see-also"></a><span data-ttu-id="5696b-184">関連項目</span><span class="sxs-lookup"><span data-stu-id="5696b-184">See also</span></span>

- [<span data-ttu-id="5696b-185">インジケーターの作成</span><span class="sxs-lookup"><span data-stu-id="5696b-185">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="5696b-186">IP および URL/ドメインのインジケーターを作成</span><span class="sxs-lookup"><span data-stu-id="5696b-186">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="5696b-187">証明書に基づいてインジケーターを作成する</span><span class="sxs-lookup"><span data-stu-id="5696b-187">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="5696b-188">インジケーターの管理</span><span class="sxs-lookup"><span data-stu-id="5696b-188">Manage indicators</span></span>](indicator-manage.md)
