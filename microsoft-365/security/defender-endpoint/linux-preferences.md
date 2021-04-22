---
title: Linux 上のエンドポイント用 Microsoft Defender の基本設定を設定する
ms.reviewer: ''
description: エンタープライズで Microsoft Defender for Endpoint on Linux を構成する方法について説明します。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, Linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 42b15edd933d80dd397f4681c4f0fdb035f030f2
ms.sourcegitcommit: 682ed2c4e2bc6979025cdb89094866cef6c8751a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2021
ms.locfileid: "51943019"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="04aa1-104">Linux 上のエンドポイント用 Microsoft Defender の基本設定を設定する</span><span class="sxs-lookup"><span data-stu-id="04aa1-104">Set preferences for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="04aa1-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="04aa1-105">**Applies to:**</span></span>
- [<span data-ttu-id="04aa1-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="04aa1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="04aa1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="04aa1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="04aa1-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="04aa1-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="04aa1-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="04aa1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

>[!IMPORTANT]
><span data-ttu-id="04aa1-110">このトピックでは、エンタープライズ環境で Defender for Endpoint on Linux の基本設定を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="04aa1-110">This topic contains instructions for how to set preferences for Defender for Endpoint on Linux in enterprise environments.</span></span> <span data-ttu-id="04aa1-111">コマンド ラインからデバイスで製品を構成する場合は、「Resources」を参照 [してください](linux-resources.md#configure-from-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="04aa1-111">If you are interested in configuring the product on a device from the command-line, see [Resources](linux-resources.md#configure-from-the-command-line).</span></span>

<span data-ttu-id="04aa1-112">エンタープライズ環境では、Defender for Endpoint on Linux を構成プロファイルで管理できます。</span><span class="sxs-lookup"><span data-stu-id="04aa1-112">In enterprise environments, Defender for Endpoint on Linux can be managed through a configuration profile.</span></span> <span data-ttu-id="04aa1-113">このプロファイルは、選択した管理ツールから展開されます。</span><span class="sxs-lookup"><span data-stu-id="04aa1-113">This profile is deployed from the management tool of your choice.</span></span> <span data-ttu-id="04aa1-114">企業が管理する基本設定は、デバイス上でローカルに設定された基本設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="04aa1-114">Preferences managed by the enterprise take precedence over the ones set locally on the device.</span></span> <span data-ttu-id="04aa1-115">つまり、企業のユーザーは、この構成プロファイルを介して設定された基本設定を変更できないのです。</span><span class="sxs-lookup"><span data-stu-id="04aa1-115">In other words, users in your enterprise are not able to change preferences that are set through this configuration profile.</span></span>

<span data-ttu-id="04aa1-116">この記事では、このプロファイルの構造 (開始に使用できる推奨プロファイルを含む) と、プロファイルを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="04aa1-116">This article describes the structure of this profile (including a recommended profile that you can use to get started) and instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="04aa1-117">構成プロファイル構造</span><span class="sxs-lookup"><span data-stu-id="04aa1-117">Configuration profile structure</span></span>

<span data-ttu-id="04aa1-118">構成プロファイルは 、キーで識別されるエントリ (基本設定の名前を示す) で構成される .json ファイルで、その後に、基本設定の性質に依存する値が続きます。</span><span class="sxs-lookup"><span data-stu-id="04aa1-118">The configuration profile is a .json file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="04aa1-119">数値などの単純な値や、入れ子になった基本設定のリストなどの複雑な値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="04aa1-119">Values can be simple, such as a numerical value, or complex, such as a nested list of preferences.</span></span>

<span data-ttu-id="04aa1-120">通常、構成管理ツールを使用して、名前を持つファイルを場所 ```mdatp_managed.json``` にプッシュします ```/etc/opt/microsoft/mdatp/managed/``` 。</span><span class="sxs-lookup"><span data-stu-id="04aa1-120">Typically, you would use a configuration management tool to push a file with the name ```mdatp_managed.json``` at the location ```/etc/opt/microsoft/mdatp/managed/```.</span></span>

<span data-ttu-id="04aa1-121">構成プロファイルのトップ レベルには、製品全体の基本設定と、製品のサブエリアのエントリが含まれています。これは、次のセクションで詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="04aa1-121">The top level of the configuration profile includes product-wide preferences and entries for subareas of the product, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="04aa1-122">ウイルス対策エンジンの基本設定</span><span class="sxs-lookup"><span data-stu-id="04aa1-122">Antivirus engine preferences</span></span>

<span data-ttu-id="04aa1-123">構成 *プロファイルの antivirusEngine* セクションを使用して、製品のウイルス対策コンポーネントの基本設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="04aa1-123">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="04aa1-124">**Key**</span><span class="sxs-lookup"><span data-stu-id="04aa1-124">**Key**</span></span> | <span data-ttu-id="04aa1-125">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="04aa1-125">antivirusEngine</span></span> |
| <span data-ttu-id="04aa1-126">**データ型**</span><span class="sxs-lookup"><span data-stu-id="04aa1-126">**Data type**</span></span> | <span data-ttu-id="04aa1-127">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="04aa1-127">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="04aa1-128">**コメント**</span><span class="sxs-lookup"><span data-stu-id="04aa1-128">**Comments**</span></span> | <span data-ttu-id="04aa1-129">辞書の内容の説明については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="04aa1-129">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="04aa1-130">リアルタイム保護を有効/無効にする</span><span class="sxs-lookup"><span data-stu-id="04aa1-130">Enable / disable real-time protection</span></span>

<span data-ttu-id="04aa1-131">リアルタイム保護 (アクセス時のファイルのスキャン) を有効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="04aa1-131">Determines whether real-time protection (scan files as they are accessed) is enabled or not.</span></span>

|||
|:---|:---|
| <span data-ttu-id="04aa1-132">**Key**</span><span class="sxs-lookup"><span data-stu-id="04aa1-132">**Key**</span></span> | <span data-ttu-id="04aa1-133">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="04aa1-133">enableRealTimeProtection</span></span> |
| <span data-ttu-id="04aa1-134">**データ型**</span><span class="sxs-lookup"><span data-stu-id="04aa1-134">**Data type**</span></span> | <span data-ttu-id="04aa1-135">Boolean</span><span class="sxs-lookup"><span data-stu-id="04aa1-135">Boolean</span></span> |
| <span data-ttu-id="04aa1-136">**可能な値**</span><span class="sxs-lookup"><span data-stu-id="04aa1-136">**Possible values**</span></span> | <span data-ttu-id="04aa1-137">true (既定)</span><span class="sxs-lookup"><span data-stu-id="04aa1-137">true (default)</span></span> <br/> <span data-ttu-id="04aa1-138">false</span><span class="sxs-lookup"><span data-stu-id="04aa1-138">false</span></span> |
|||

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="04aa1-139">パッシブ モードを有効/無効にする</span><span class="sxs-lookup"><span data-stu-id="04aa1-139">Enable / disable passive mode</span></span>

<span data-ttu-id="04aa1-140">ウイルス対策エンジンがパッシブ モードで実行されるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="04aa1-140">Determines whether the antivirus engine runs in passive mode or not.</span></span> <span data-ttu-id="04aa1-141">パッシブ モードの場合:</span><span class="sxs-lookup"><span data-stu-id="04aa1-141">In passive mode:</span></span>
- <span data-ttu-id="04aa1-142">リアルタイム保護はオフです。</span><span class="sxs-lookup"><span data-stu-id="04aa1-142">Real-time protection is turned off.</span></span>
- <span data-ttu-id="04aa1-143">オンデマンド スキャンが有効です。</span><span class="sxs-lookup"><span data-stu-id="04aa1-143">On-demand scanning is turned on.</span></span>
- <span data-ttu-id="04aa1-144">脅威の自動修復が無効になります。</span><span class="sxs-lookup"><span data-stu-id="04aa1-144">Automatic threat remediation is turned off.</span></span>
- <span data-ttu-id="04aa1-145">セキュリティ インテリジェンスの更新プログラムが有効になっている。</span><span class="sxs-lookup"><span data-stu-id="04aa1-145">Security intelligence updates are turned on.</span></span>
- <span data-ttu-id="04aa1-146">[状態] メニュー アイコンは非表示です。</span><span class="sxs-lookup"><span data-stu-id="04aa1-146">Status menu icon is hidden.</span></span>

|||
|:---|:---|
| <span data-ttu-id="04aa1-147">**Key**</span><span class="sxs-lookup"><span data-stu-id="04aa1-147">**Key**</span></span> | <span data-ttu-id="04aa1-148">passiveMode</span><span class="sxs-lookup"><span data-stu-id="04aa1-148">passiveMode</span></span> |
| <span data-ttu-id="04aa1-149">**データ型**</span><span class="sxs-lookup"><span data-stu-id="04aa1-149">**Data type**</span></span> | <span data-ttu-id="04aa1-150">Boolean</span><span class="sxs-lookup"><span data-stu-id="04aa1-150">Boolean</span></span> |
| <span data-ttu-id="04aa1-151">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="04aa1-151">**Possible values**</span></span> | <span data-ttu-id="04aa1-152">false (既定)</span><span class="sxs-lookup"><span data-stu-id="04aa1-152">false (default)</span></span> <br/> <span data-ttu-id="04aa1-153">true</span><span class="sxs-lookup"><span data-stu-id="04aa1-153">true</span></span> |
| <span data-ttu-id="04aa1-154">**コメント**</span><span class="sxs-lookup"><span data-stu-id="04aa1-154">**Comments**</span></span> | <span data-ttu-id="04aa1-155">Defender for Endpoint version 100.67.60 以上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="04aa1-155">Available in Defender for Endpoint version 100.67.60 or higher.</span></span> |
|||

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="04aa1-156">除外マージ ポリシー</span><span class="sxs-lookup"><span data-stu-id="04aa1-156">Exclusion merge policy</span></span>

<span data-ttu-id="04aa1-157">除外のマージ ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="04aa1-157">Specifies the merge policy for exclusions.</span></span> <span data-ttu-id="04aa1-158">管理者定義の除外とユーザー定義の除外 ( ) の組み合わせ、または管理者定義の除外 ( ) のみを `merge` 組み合わせて指定できます `admin_only` 。</span><span class="sxs-lookup"><span data-stu-id="04aa1-158">It can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="04aa1-159">この設定は、ローカル ユーザーが独自の除外を定義するのを制限するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="04aa1-159">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|||
|:---|:---|
| <span data-ttu-id="04aa1-160">**Key**</span><span class="sxs-lookup"><span data-stu-id="04aa1-160">**Key**</span></span> | <span data-ttu-id="04aa1-161">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="04aa1-161">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="04aa1-162">**データ型**</span><span class="sxs-lookup"><span data-stu-id="04aa1-162">**Data type**</span></span> | <span data-ttu-id="04aa1-163">String</span><span class="sxs-lookup"><span data-stu-id="04aa1-163">String</span></span> |
| <span data-ttu-id="04aa1-164">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="04aa1-164">**Possible values**</span></span> | <span data-ttu-id="04aa1-165">merge (既定)</span><span class="sxs-lookup"><span data-stu-id="04aa1-165">merge (default)</span></span> <br/> <span data-ttu-id="04aa1-166">admin_only</span><span class="sxs-lookup"><span data-stu-id="04aa1-166">admin_only</span></span> |
| <span data-ttu-id="04aa1-167">**コメント**</span><span class="sxs-lookup"><span data-stu-id="04aa1-167">**Comments**</span></span> | <span data-ttu-id="04aa1-168">Defender for Endpoint version 100.83.73 以上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="04aa1-168">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="scan-exclusions"></a><span data-ttu-id="04aa1-169">スキャンの除外</span><span class="sxs-lookup"><span data-stu-id="04aa1-169">Scan exclusions</span></span>

<span data-ttu-id="04aa1-170">スキャンから除外されたエンティティ。</span><span class="sxs-lookup"><span data-stu-id="04aa1-170">Entities that have been excluded from the scan.</span></span> <span data-ttu-id="04aa1-171">除外は、完全パス、拡張子、またはファイル名で指定できます。</span><span class="sxs-lookup"><span data-stu-id="04aa1-171">Exclusions can be specified by full paths, extensions, or file names.</span></span>

|||
|:---|:---|
| <span data-ttu-id="04aa1-172">**Key**</span><span class="sxs-lookup"><span data-stu-id="04aa1-172">**Key**</span></span> | <span data-ttu-id="04aa1-173">除外</span><span class="sxs-lookup"><span data-stu-id="04aa1-173">exclusions</span></span> |
| <span data-ttu-id="04aa1-174">**データ型**</span><span class="sxs-lookup"><span data-stu-id="04aa1-174">**Data type**</span></span> | <span data-ttu-id="04aa1-175">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="04aa1-175">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="04aa1-176">**コメント**</span><span class="sxs-lookup"><span data-stu-id="04aa1-176">**Comments**</span></span> | <span data-ttu-id="04aa1-177">辞書の内容の説明については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="04aa1-177">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="04aa1-178">**除外の種類**</span><span class="sxs-lookup"><span data-stu-id="04aa1-178">**Type of exclusion**</span></span>

<span data-ttu-id="04aa1-179">スキャンから除外されるコンテンツの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="04aa1-179">Specifies the type of content excluded from the scan.</span></span>

|||
|:---|:---|
| <span data-ttu-id="04aa1-180">**Key**</span><span class="sxs-lookup"><span data-stu-id="04aa1-180">**Key**</span></span> | <span data-ttu-id="04aa1-181">$type</span><span class="sxs-lookup"><span data-stu-id="04aa1-181">$type</span></span> |
| <span data-ttu-id="04aa1-182">**データ型**</span><span class="sxs-lookup"><span data-stu-id="04aa1-182">**Data type**</span></span> | <span data-ttu-id="04aa1-183">String</span><span class="sxs-lookup"><span data-stu-id="04aa1-183">String</span></span> |
| <span data-ttu-id="04aa1-184">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="04aa1-184">**Possible values**</span></span> | <span data-ttu-id="04aa1-185">excludedPath</span><span class="sxs-lookup"><span data-stu-id="04aa1-185">excludedPath</span></span> <br/> <span data-ttu-id="04aa1-186">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="04aa1-186">excludedFileExtension</span></span> <br/> <span data-ttu-id="04aa1-187">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="04aa1-187">excludedFileName</span></span> |
|||

<span data-ttu-id="04aa1-188">**除外されたコンテンツへのパス**</span><span class="sxs-lookup"><span data-stu-id="04aa1-188">**Path to excluded content**</span></span>

<span data-ttu-id="04aa1-189">完全なファイル パスでスキャンからコンテンツを除外するために使用します。</span><span class="sxs-lookup"><span data-stu-id="04aa1-189">Used to exclude content from the scan by full file path.</span></span>

|||
|:---|:---|
| <span data-ttu-id="04aa1-190">**Key**</span><span class="sxs-lookup"><span data-stu-id="04aa1-190">**Key**</span></span> | <span data-ttu-id="04aa1-191">path</span><span class="sxs-lookup"><span data-stu-id="04aa1-191">path</span></span> |
| <span data-ttu-id="04aa1-192">**データ型**</span><span class="sxs-lookup"><span data-stu-id="04aa1-192">**Data type**</span></span> | <span data-ttu-id="04aa1-193">String</span><span class="sxs-lookup"><span data-stu-id="04aa1-193">String</span></span> |
| <span data-ttu-id="04aa1-194">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="04aa1-194">**Possible values**</span></span> | <span data-ttu-id="04aa1-195">有効なパス</span><span class="sxs-lookup"><span data-stu-id="04aa1-195">valid paths</span></span> |
| <span data-ttu-id="04aa1-196">**コメント**</span><span class="sxs-lookup"><span data-stu-id="04aa1-196">**Comments**</span></span> | <span data-ttu-id="04aa1-197">適用 *できるのは、$type\*\*が excludedPath である場合のみです。*</span><span class="sxs-lookup"><span data-stu-id="04aa1-197">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="04aa1-198">**パスの種類 (ファイル/ディレクトリ)**</span><span class="sxs-lookup"><span data-stu-id="04aa1-198">**Path type (file / directory)**</span></span>

<span data-ttu-id="04aa1-199">*path* プロパティがファイルまたはディレクトリを参照しているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="04aa1-199">Indicates if the *path* property refers to a file or directory.</span></span> 

|||
|:---|:---|
| <span data-ttu-id="04aa1-200">**Key**</span><span class="sxs-lookup"><span data-stu-id="04aa1-200">**Key**</span></span> | <span data-ttu-id="04aa1-201">isDirectory</span><span class="sxs-lookup"><span data-stu-id="04aa1-201">isDirectory</span></span> |
| <span data-ttu-id="04aa1-202">**データ型**</span><span class="sxs-lookup"><span data-stu-id="04aa1-202">**Data type**</span></span> | <span data-ttu-id="04aa1-203">Boolean</span><span class="sxs-lookup"><span data-stu-id="04aa1-203">Boolean</span></span> |
| <span data-ttu-id="04aa1-204">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="04aa1-204">**Possible values**</span></span> | <span data-ttu-id="04aa1-205">false (既定)</span><span class="sxs-lookup"><span data-stu-id="04aa1-205">false (default)</span></span> <br/> <span data-ttu-id="04aa1-206">true</span><span class="sxs-lookup"><span data-stu-id="04aa1-206">true</span></span> |
| <span data-ttu-id="04aa1-207">**コメント**</span><span class="sxs-lookup"><span data-stu-id="04aa1-207">**Comments**</span></span> | <span data-ttu-id="04aa1-208">適用 *できるのは、$type\*\*が excludedPath である場合のみです。*</span><span class="sxs-lookup"><span data-stu-id="04aa1-208">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="04aa1-209">**スキャンから除外されたファイル拡張子**</span><span class="sxs-lookup"><span data-stu-id="04aa1-209">**File extension excluded from the scan**</span></span>

<span data-ttu-id="04aa1-210">ファイル拡張子でスキャンからコンテンツを除外するために使用します。</span><span class="sxs-lookup"><span data-stu-id="04aa1-210">Used to exclude content from the scan by file extension.</span></span>

|||
|:---|:---|
| <span data-ttu-id="04aa1-211">**Key**</span><span class="sxs-lookup"><span data-stu-id="04aa1-211">**Key**</span></span> | <span data-ttu-id="04aa1-212">拡張機能</span><span class="sxs-lookup"><span data-stu-id="04aa1-212">extension</span></span> |
| <span data-ttu-id="04aa1-213">**データ型**</span><span class="sxs-lookup"><span data-stu-id="04aa1-213">**Data type**</span></span> | <span data-ttu-id="04aa1-214">String</span><span class="sxs-lookup"><span data-stu-id="04aa1-214">String</span></span> |
| <span data-ttu-id="04aa1-215">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="04aa1-215">**Possible values**</span></span> | <span data-ttu-id="04aa1-216">有効なファイル拡張子</span><span class="sxs-lookup"><span data-stu-id="04aa1-216">valid file extensions</span></span> |
| <span data-ttu-id="04aa1-217">**コメント**</span><span class="sxs-lookup"><span data-stu-id="04aa1-217">**Comments**</span></span> | <span data-ttu-id="04aa1-218">適用 *できるのは* 、$type FileExtension が *除外されている場合のみです。*</span><span class="sxs-lookup"><span data-stu-id="04aa1-218">Applicable only if *$type* is *excludedFileExtension*</span></span> |
|||

<span data-ttu-id="04aa1-219">**スキャンから除外されるプロセス**</span><span class="sxs-lookup"><span data-stu-id="04aa1-219">**Process excluded from the scan**</span></span>

<span data-ttu-id="04aa1-220">すべてのファイル アクティビティがスキャンから除外されるプロセスを指定します。</span><span class="sxs-lookup"><span data-stu-id="04aa1-220">Specifies a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="04aa1-221">プロセスは、名前 (たとえば) または完全パス `cat` (たとえば) で指定できます `/bin/cat` 。</span><span class="sxs-lookup"><span data-stu-id="04aa1-221">The process can be specified either by its name (for example, `cat`) or full path (for example, `/bin/cat`).</span></span>

|||
|:---|:---|
| <span data-ttu-id="04aa1-222">**Key**</span><span class="sxs-lookup"><span data-stu-id="04aa1-222">**Key**</span></span> | <span data-ttu-id="04aa1-223">name</span><span class="sxs-lookup"><span data-stu-id="04aa1-223">name</span></span> |
| <span data-ttu-id="04aa1-224">**データ型**</span><span class="sxs-lookup"><span data-stu-id="04aa1-224">**Data type**</span></span> | <span data-ttu-id="04aa1-225">String</span><span class="sxs-lookup"><span data-stu-id="04aa1-225">String</span></span> |
| <span data-ttu-id="04aa1-226">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="04aa1-226">**Possible values**</span></span> | <span data-ttu-id="04aa1-227">任意の文字列</span><span class="sxs-lookup"><span data-stu-id="04aa1-227">any string</span></span> |
| <span data-ttu-id="04aa1-228">**コメント**</span><span class="sxs-lookup"><span data-stu-id="04aa1-228">**Comments**</span></span> | <span data-ttu-id="04aa1-229">ファイルが excludedFileName *$type\*\*場合にのみ適用されます。*</span><span class="sxs-lookup"><span data-stu-id="04aa1-229">Applicable only if *$type* is *excludedFileName*</span></span> |
|||

#### <a name="allowed-threats"></a><span data-ttu-id="04aa1-230">許可される脅威</span><span class="sxs-lookup"><span data-stu-id="04aa1-230">Allowed threats</span></span>

<span data-ttu-id="04aa1-231">製品によってブロックされ、代わりに実行が許可されている脅威の一覧 (名前で識別されます)。</span><span class="sxs-lookup"><span data-stu-id="04aa1-231">List of threats (identified by their name) that are not blocked by the product and are instead allowed to run.</span></span>

|||
|:---|:---|
| <span data-ttu-id="04aa1-232">**Key**</span><span class="sxs-lookup"><span data-stu-id="04aa1-232">**Key**</span></span> | <span data-ttu-id="04aa1-233">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="04aa1-233">allowedThreats</span></span> |
| <span data-ttu-id="04aa1-234">**データ型**</span><span class="sxs-lookup"><span data-stu-id="04aa1-234">**Data type**</span></span> | <span data-ttu-id="04aa1-235">文字列の配列</span><span class="sxs-lookup"><span data-stu-id="04aa1-235">Array of strings</span></span> |
|||

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="04aa1-236">禁止された脅威アクション</span><span class="sxs-lookup"><span data-stu-id="04aa1-236">Disallowed threat actions</span></span>

<span data-ttu-id="04aa1-237">脅威が検出された場合にデバイスのローカル ユーザーが実行できるアクションを制限します。</span><span class="sxs-lookup"><span data-stu-id="04aa1-237">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="04aa1-238">この一覧に含まれるアクションは、ユーザー インターフェイスには表示されません。</span><span class="sxs-lookup"><span data-stu-id="04aa1-238">The actions included in this list are not displayed in the user interface.</span></span>

|||
|:---|:---|
| <span data-ttu-id="04aa1-239">**Key**</span><span class="sxs-lookup"><span data-stu-id="04aa1-239">**Key**</span></span> | <span data-ttu-id="04aa1-240">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="04aa1-240">disallowedThreatActions</span></span> |
| <span data-ttu-id="04aa1-241">**データ型**</span><span class="sxs-lookup"><span data-stu-id="04aa1-241">**Data type**</span></span> | <span data-ttu-id="04aa1-242">文字列の配列</span><span class="sxs-lookup"><span data-stu-id="04aa1-242">Array of strings</span></span> |
| <span data-ttu-id="04aa1-243">**可能な値**</span><span class="sxs-lookup"><span data-stu-id="04aa1-243">**Possible values**</span></span> | <span data-ttu-id="04aa1-244">allow (ユーザーによる脅威の許可を制限する)</span><span class="sxs-lookup"><span data-stu-id="04aa1-244">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="04aa1-245">復元 (検疫からの脅威の復元をユーザーに制限する)</span><span class="sxs-lookup"><span data-stu-id="04aa1-245">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="04aa1-246">**コメント**</span><span class="sxs-lookup"><span data-stu-id="04aa1-246">**Comments**</span></span> | <span data-ttu-id="04aa1-247">Defender for Endpoint version 100.83.73 以上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="04aa1-247">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="threat-type-settings"></a><span data-ttu-id="04aa1-248">脅威の種類の設定</span><span class="sxs-lookup"><span data-stu-id="04aa1-248">Threat type settings</span></span>

<span data-ttu-id="04aa1-249">ウイルス *対策エンジンの threatTypeSettings* 基本設定は、製品による特定の脅威の種類の処理方法を制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="04aa1-249">The *threatTypeSettings* preference in the antivirus engine is used to control how certain threat types are handled by the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="04aa1-250">**Key**</span><span class="sxs-lookup"><span data-stu-id="04aa1-250">**Key**</span></span> | <span data-ttu-id="04aa1-251">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="04aa1-251">threatTypeSettings</span></span> |
| <span data-ttu-id="04aa1-252">**データ型**</span><span class="sxs-lookup"><span data-stu-id="04aa1-252">**Data type**</span></span> | <span data-ttu-id="04aa1-253">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="04aa1-253">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="04aa1-254">**コメント**</span><span class="sxs-lookup"><span data-stu-id="04aa1-254">**Comments**</span></span> | <span data-ttu-id="04aa1-255">辞書の内容の説明については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="04aa1-255">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="04aa1-256">**脅威の種類**</span><span class="sxs-lookup"><span data-stu-id="04aa1-256">**Threat type**</span></span>

<span data-ttu-id="04aa1-257">動作が構成されている脅威の種類。</span><span class="sxs-lookup"><span data-stu-id="04aa1-257">Type of threat for which the behavior is configured.</span></span>

|||
|:---|:---|
| <span data-ttu-id="04aa1-258">**Key**</span><span class="sxs-lookup"><span data-stu-id="04aa1-258">**Key**</span></span> | <span data-ttu-id="04aa1-259">キー</span><span class="sxs-lookup"><span data-stu-id="04aa1-259">key</span></span> |
| <span data-ttu-id="04aa1-260">**データ型**</span><span class="sxs-lookup"><span data-stu-id="04aa1-260">**Data type**</span></span> | <span data-ttu-id="04aa1-261">String</span><span class="sxs-lookup"><span data-stu-id="04aa1-261">String</span></span> |
| <span data-ttu-id="04aa1-262">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="04aa1-262">**Possible values**</span></span> | <span data-ttu-id="04aa1-263">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="04aa1-263">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="04aa1-264">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="04aa1-264">archive_bomb</span></span> |
|||

<span data-ttu-id="04aa1-265">**実行する操作**</span><span class="sxs-lookup"><span data-stu-id="04aa1-265">**Action to take**</span></span>

<span data-ttu-id="04aa1-266">前のセクションで指定した種類の脅威に出く際に実行するアクション。</span><span class="sxs-lookup"><span data-stu-id="04aa1-266">Action to take when coming across a threat of the type specified in the preceding section.</span></span> <span data-ttu-id="04aa1-267">次の指定が可能です。</span><span class="sxs-lookup"><span data-stu-id="04aa1-267">Can be:</span></span>

- <span data-ttu-id="04aa1-268">**監査**: デバイスは、この種類の脅威から保護されませんが、脅威に関するエントリがログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="04aa1-268">**Audit**: The device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="04aa1-269">**ブロック**: デバイスは、この種類の脅威から保護され、セキュリティ コンソールで通知されます。</span><span class="sxs-lookup"><span data-stu-id="04aa1-269">**Block**: The device is protected against this type of threat and you are notified in the security console.</span></span>
- <span data-ttu-id="04aa1-270">**オフ**: デバイスは、この種類の脅威から保護され、何もログに記録されません。</span><span class="sxs-lookup"><span data-stu-id="04aa1-270">**Off**: The device is not protected against this type of threat and nothing is logged.</span></span>

|||
|:---|:---|
| <span data-ttu-id="04aa1-271">**Key**</span><span class="sxs-lookup"><span data-stu-id="04aa1-271">**Key**</span></span> | <span data-ttu-id="04aa1-272">値</span><span class="sxs-lookup"><span data-stu-id="04aa1-272">value</span></span> |
| <span data-ttu-id="04aa1-273">**データ型**</span><span class="sxs-lookup"><span data-stu-id="04aa1-273">**Data type**</span></span> | <span data-ttu-id="04aa1-274">String</span><span class="sxs-lookup"><span data-stu-id="04aa1-274">String</span></span> |
| <span data-ttu-id="04aa1-275">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="04aa1-275">**Possible values**</span></span> | <span data-ttu-id="04aa1-276">監査 (既定)</span><span class="sxs-lookup"><span data-stu-id="04aa1-276">audit (default)</span></span> <br/> <span data-ttu-id="04aa1-277">block</span><span class="sxs-lookup"><span data-stu-id="04aa1-277">block</span></span> <br/> <span data-ttu-id="04aa1-278">off</span><span class="sxs-lookup"><span data-stu-id="04aa1-278">off</span></span> |
|||

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="04aa1-279">脅威の種類の設定の差し込みポリシー</span><span class="sxs-lookup"><span data-stu-id="04aa1-279">Threat type settings merge policy</span></span>

<span data-ttu-id="04aa1-280">脅威の種類の設定のマージ ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="04aa1-280">Specifies the merge policy for threat type settings.</span></span> <span data-ttu-id="04aa1-281">これは、管理者定義設定とユーザー定義設定 ( ) の組み合わせか、管理者定義の設定 ( ) のみを `merge` 組み合わせて使用できます `admin_only` 。</span><span class="sxs-lookup"><span data-stu-id="04aa1-281">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="04aa1-282">この設定を使用すると、ローカル ユーザーがさまざまな脅威の種類に対して独自の設定を定義するのを制限できます。</span><span class="sxs-lookup"><span data-stu-id="04aa1-282">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="04aa1-283">**Key**</span><span class="sxs-lookup"><span data-stu-id="04aa1-283">**Key**</span></span> | <span data-ttu-id="04aa1-284">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="04aa1-284">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="04aa1-285">**データ型**</span><span class="sxs-lookup"><span data-stu-id="04aa1-285">**Data type**</span></span> | <span data-ttu-id="04aa1-286">String</span><span class="sxs-lookup"><span data-stu-id="04aa1-286">String</span></span> |
| <span data-ttu-id="04aa1-287">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="04aa1-287">**Possible values**</span></span> | <span data-ttu-id="04aa1-288">merge (既定)</span><span class="sxs-lookup"><span data-stu-id="04aa1-288">merge (default)</span></span> <br/> <span data-ttu-id="04aa1-289">admin_only</span><span class="sxs-lookup"><span data-stu-id="04aa1-289">admin_only</span></span> |
| <span data-ttu-id="04aa1-290">**コメント**</span><span class="sxs-lookup"><span data-stu-id="04aa1-290">**Comments**</span></span> | <span data-ttu-id="04aa1-291">Defender for Endpoint version 100.83.73 以上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="04aa1-291">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="04aa1-292">ウイルス対策スキャン履歴の保持 (日数)</span><span class="sxs-lookup"><span data-stu-id="04aa1-292">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="04aa1-293">デバイスのスキャン履歴に結果が保持される日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="04aa1-293">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="04aa1-294">古いスキャン結果は履歴から削除されます。</span><span class="sxs-lookup"><span data-stu-id="04aa1-294">Old scan results are removed from the history.</span></span> <span data-ttu-id="04aa1-295">ディスクから削除された古い検疫済みファイル。</span><span class="sxs-lookup"><span data-stu-id="04aa1-295">Old quarantined files that are also removed from the disk.</span></span>

|||
|:---|:---|
| <span data-ttu-id="04aa1-296">**Key**</span><span class="sxs-lookup"><span data-stu-id="04aa1-296">**Key**</span></span> | <span data-ttu-id="04aa1-297">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="04aa1-297">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="04aa1-298">**データ型**</span><span class="sxs-lookup"><span data-stu-id="04aa1-298">**Data type**</span></span> | <span data-ttu-id="04aa1-299">String</span><span class="sxs-lookup"><span data-stu-id="04aa1-299">String</span></span> |
| <span data-ttu-id="04aa1-300">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="04aa1-300">**Possible values**</span></span> | <span data-ttu-id="04aa1-301">90 (既定)。</span><span class="sxs-lookup"><span data-stu-id="04aa1-301">90 (default).</span></span> <span data-ttu-id="04aa1-302">使用できる値は、1 日から 180 日です。</span><span class="sxs-lookup"><span data-stu-id="04aa1-302">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="04aa1-303">**コメント**</span><span class="sxs-lookup"><span data-stu-id="04aa1-303">**Comments**</span></span> | <span data-ttu-id="04aa1-304">Defender for Endpoint version 101.04.76 以上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="04aa1-304">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="04aa1-305">ウイルス対策スキャン履歴内のアイテムの最大数</span><span class="sxs-lookup"><span data-stu-id="04aa1-305">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="04aa1-306">スキャン履歴に保持するエントリの最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="04aa1-306">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="04aa1-307">エントリには、過去に実行されたオンデマンド スキャンとすべてのウイルス対策検出が含まれます。</span><span class="sxs-lookup"><span data-stu-id="04aa1-307">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|||
|:---|:---|
| <span data-ttu-id="04aa1-308">**Key**</span><span class="sxs-lookup"><span data-stu-id="04aa1-308">**Key**</span></span> | <span data-ttu-id="04aa1-309">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="04aa1-309">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="04aa1-310">**データ型**</span><span class="sxs-lookup"><span data-stu-id="04aa1-310">**Data type**</span></span> | <span data-ttu-id="04aa1-311">String</span><span class="sxs-lookup"><span data-stu-id="04aa1-311">String</span></span> |
| <span data-ttu-id="04aa1-312">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="04aa1-312">**Possible values**</span></span> | <span data-ttu-id="04aa1-313">10000 (既定値)。</span><span class="sxs-lookup"><span data-stu-id="04aa1-313">10000 (default).</span></span> <span data-ttu-id="04aa1-314">許可される値は、5000 アイテムから 15,000 アイテムまでです。</span><span class="sxs-lookup"><span data-stu-id="04aa1-314">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="04aa1-315">**コメント**</span><span class="sxs-lookup"><span data-stu-id="04aa1-315">**Comments**</span></span> | <span data-ttu-id="04aa1-316">Defender for Endpoint version 101.04.76 以上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="04aa1-316">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="04aa1-317">クラウドによる保護の基本設定</span><span class="sxs-lookup"><span data-stu-id="04aa1-317">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="04aa1-318">構成 *プロファイルの cloudService* エントリを使用して、製品のクラウド駆動型保護機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="04aa1-318">The *cloudService* entry in the configuration profile is used to configure the cloud-driven protection feature of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="04aa1-319">**Key**</span><span class="sxs-lookup"><span data-stu-id="04aa1-319">**Key**</span></span> | <span data-ttu-id="04aa1-320">cloudService</span><span class="sxs-lookup"><span data-stu-id="04aa1-320">cloudService</span></span> |
| <span data-ttu-id="04aa1-321">**データ型**</span><span class="sxs-lookup"><span data-stu-id="04aa1-321">**Data type**</span></span> | <span data-ttu-id="04aa1-322">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="04aa1-322">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="04aa1-323">**コメント**</span><span class="sxs-lookup"><span data-stu-id="04aa1-323">**Comments**</span></span> | <span data-ttu-id="04aa1-324">辞書の内容の説明については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="04aa1-324">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="04aa1-325">クラウド配信保護を有効/無効にする</span><span class="sxs-lookup"><span data-stu-id="04aa1-325">Enable / disable cloud delivered protection</span></span>

<span data-ttu-id="04aa1-326">デバイスでクラウド配信の保護を有効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="04aa1-326">Determines whether cloud-delivered protection is enabled on the device or not.</span></span> <span data-ttu-id="04aa1-327">サービスのセキュリティを向上させるために、この機能を有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="04aa1-327">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|||
|:---|:---|
| <span data-ttu-id="04aa1-328">**Key**</span><span class="sxs-lookup"><span data-stu-id="04aa1-328">**Key**</span></span> | <span data-ttu-id="04aa1-329">enabled</span><span class="sxs-lookup"><span data-stu-id="04aa1-329">enabled</span></span> |
| <span data-ttu-id="04aa1-330">**データ型**</span><span class="sxs-lookup"><span data-stu-id="04aa1-330">**Data type**</span></span> | <span data-ttu-id="04aa1-331">Boolean</span><span class="sxs-lookup"><span data-stu-id="04aa1-331">Boolean</span></span> |
| <span data-ttu-id="04aa1-332">**可能な値**</span><span class="sxs-lookup"><span data-stu-id="04aa1-332">**Possible values**</span></span> | <span data-ttu-id="04aa1-333">true (既定)</span><span class="sxs-lookup"><span data-stu-id="04aa1-333">true (default)</span></span> <br/> <span data-ttu-id="04aa1-334">false</span><span class="sxs-lookup"><span data-stu-id="04aa1-334">false</span></span> |
|||

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="04aa1-335">診断コレクション レベル</span><span class="sxs-lookup"><span data-stu-id="04aa1-335">Diagnostic collection level</span></span>

<span data-ttu-id="04aa1-336">診断データは、Defender for Endpoint を安全かつ最新の状態に保ち、問題を検出、診断、修正し、製品の改善を行う場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="04aa1-336">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="04aa1-337">この設定は、製品から Microsoft に送信される診断のレベルを決定します。</span><span class="sxs-lookup"><span data-stu-id="04aa1-337">This setting determines the level of diagnostics sent by the product to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="04aa1-338">**Key**</span><span class="sxs-lookup"><span data-stu-id="04aa1-338">**Key**</span></span> | <span data-ttu-id="04aa1-339">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="04aa1-339">diagnosticLevel</span></span> |
| <span data-ttu-id="04aa1-340">**データ型**</span><span class="sxs-lookup"><span data-stu-id="04aa1-340">**Data type**</span></span> | <span data-ttu-id="04aa1-341">String</span><span class="sxs-lookup"><span data-stu-id="04aa1-341">String</span></span> |
| <span data-ttu-id="04aa1-342">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="04aa1-342">**Possible values**</span></span> | <span data-ttu-id="04aa1-343">省略可能 (既定)</span><span class="sxs-lookup"><span data-stu-id="04aa1-343">optional (default)</span></span> <br/> <span data-ttu-id="04aa1-344">必須</span><span class="sxs-lookup"><span data-stu-id="04aa1-344">required</span></span> |
|||

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="04aa1-345">自動サンプル申請を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="04aa1-345">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="04aa1-346">疑わしいサンプル (脅威を含む可能性が高い) を Microsoft に送信するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="04aa1-346">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="04aa1-347">サンプル申請を制御するには、次の 3 つのレベルがあります。</span><span class="sxs-lookup"><span data-stu-id="04aa1-347">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="04aa1-348">**なし**: 疑わしいサンプルは Microsoft に送信されません。</span><span class="sxs-lookup"><span data-stu-id="04aa1-348">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="04aa1-349">**安全**: 個人を特定できる情報 (PII) を含む疑わしいサンプルだけが自動的に送信されます。</span><span class="sxs-lookup"><span data-stu-id="04aa1-349">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="04aa1-350">これは、この設定の既定値です。</span><span class="sxs-lookup"><span data-stu-id="04aa1-350">This is the default value for this setting.</span></span>
- <span data-ttu-id="04aa1-351">**すべて**: すべての疑わしいサンプルが Microsoft に送信されます。</span><span class="sxs-lookup"><span data-stu-id="04aa1-351">**All**: all suspicious samples are submitted to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="04aa1-352">**Key**</span><span class="sxs-lookup"><span data-stu-id="04aa1-352">**Key**</span></span> | <span data-ttu-id="04aa1-353">automaticSampleSubmissionConsent</span><span class="sxs-lookup"><span data-stu-id="04aa1-353">automaticSampleSubmissionConsent</span></span> |
| <span data-ttu-id="04aa1-354">**データ型**</span><span class="sxs-lookup"><span data-stu-id="04aa1-354">**Data type**</span></span> | <span data-ttu-id="04aa1-355">String</span><span class="sxs-lookup"><span data-stu-id="04aa1-355">String</span></span> |
| <span data-ttu-id="04aa1-356">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="04aa1-356">**Possible values**</span></span> | <span data-ttu-id="04aa1-357">none</span><span class="sxs-lookup"><span data-stu-id="04aa1-357">none</span></span> <br/> <span data-ttu-id="04aa1-358">safe (既定)</span><span class="sxs-lookup"><span data-stu-id="04aa1-358">safe (default)</span></span> <br/> <span data-ttu-id="04aa1-359">すべての</span><span class="sxs-lookup"><span data-stu-id="04aa1-359">all</span></span> |
|||

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="04aa1-360">セキュリティ インテリジェンスの自動更新を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="04aa1-360">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="04aa1-361">セキュリティ インテリジェンスの更新プログラムが自動的にインストールされるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="04aa1-361">Determines whether security intelligence updates are installed automatically:</span></span>

|||
|:---|:---|
| <span data-ttu-id="04aa1-362">**Key**</span><span class="sxs-lookup"><span data-stu-id="04aa1-362">**Key**</span></span> | <span data-ttu-id="04aa1-363">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="04aa1-363">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="04aa1-364">**データ型**</span><span class="sxs-lookup"><span data-stu-id="04aa1-364">**Data type**</span></span> | <span data-ttu-id="04aa1-365">Boolean</span><span class="sxs-lookup"><span data-stu-id="04aa1-365">Boolean</span></span> |
| <span data-ttu-id="04aa1-366">**可能な値**</span><span class="sxs-lookup"><span data-stu-id="04aa1-366">**Possible values**</span></span> | <span data-ttu-id="04aa1-367">true (既定)</span><span class="sxs-lookup"><span data-stu-id="04aa1-367">true (default)</span></span> <br/> <span data-ttu-id="04aa1-368">false</span><span class="sxs-lookup"><span data-stu-id="04aa1-368">false</span></span> |
|||

## <a name="recommended-configuration-profile"></a><span data-ttu-id="04aa1-369">推奨される構成プロファイル</span><span class="sxs-lookup"><span data-stu-id="04aa1-369">Recommended configuration profile</span></span>

<span data-ttu-id="04aa1-370">開始するには、Defender for Endpoint が提供するすべての保護機能を利用するために、企業の次の構成プロファイルをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="04aa1-370">To get started, we recommend the following configuration profile for your enterprise to take advantage of all protection features that Defender for Endpoint provides.</span></span>

<span data-ttu-id="04aa1-371">次の構成プロファイルは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="04aa1-371">The following configuration profile will:</span></span>

- <span data-ttu-id="04aa1-372">リアルタイム保護を有効にする (RTP)</span><span class="sxs-lookup"><span data-stu-id="04aa1-372">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="04aa1-373">次の脅威の種類の処理方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="04aa1-373">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="04aa1-374">**望ましくない可能性のあるアプリケーション (PUA) が** ブロックされる</span><span class="sxs-lookup"><span data-stu-id="04aa1-374">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="04aa1-375">**アーカイブボム** (圧縮率が高いファイル) は、製品ログに対して監査されます</span><span class="sxs-lookup"><span data-stu-id="04aa1-375">**Archive bombs** (file with a high compression rate) are audited to the product logs</span></span>
- <span data-ttu-id="04aa1-376">セキュリティ インテリジェンスの自動更新を有効にする</span><span class="sxs-lookup"><span data-stu-id="04aa1-376">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="04aa1-377">クラウドによる保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="04aa1-377">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="04aa1-378">レベルで自動サンプル提出を `safe` 有効にする</span><span class="sxs-lookup"><span data-stu-id="04aa1-378">Enable automatic sample submission at `safe` level</span></span>

### <a name="sample-profile"></a><span data-ttu-id="04aa1-379">サンプル プロファイル</span><span class="sxs-lookup"><span data-stu-id="04aa1-379">Sample profile</span></span>

```JSON
{
   "antivirusEngine":{
      "enableRealTimeProtection":true,
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "automaticDefinitionUpdateEnabled":true,
      "automaticSampleSubmissionConsent":"safe",
      "enabled":true,
      "proxy":"http://proxy.server:port/"
   }
}
```

## <a name="full-configuration-profile-example"></a><span data-ttu-id="04aa1-380">完全な構成プロファイルの例</span><span class="sxs-lookup"><span data-stu-id="04aa1-380">Full configuration profile example</span></span>

<span data-ttu-id="04aa1-381">次の構成プロファイルには、このドキュメントで説明されているすべての設定のエントリが含まれています。製品を詳細に制御する高度なシナリオに使用できます。</span><span class="sxs-lookup"><span data-stu-id="04aa1-381">The following configuration profile contains entries for all settings described in this document and can be used for more advanced scenarios where you want more control over the product.</span></span>

### <a name="full-profile"></a><span data-ttu-id="04aa1-382">フル プロファイル</span><span class="sxs-lookup"><span data-stu-id="04aa1-382">Full profile</span></span>

```JSON
{
   "antivirusEngine":{
      "enableRealTimeProtection":true,
      "passiveMode":false,
      "exclusionsMergePolicy":"merge",
      "exclusions":[
         {
            "$type":"excludedPath",
            "isDirectory":false,
            "path":"/var/log/system.log"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/home"
         },
         {
            "$type":"excludedFileExtension",
            "extension":"pdf"
         },
         {
            "$type":"excludedFileName",
            "name":"cat"
         }
      ],
      "allowedThreats":[
         "EICAR-Test-File (not a virus)"
      ],
      "disallowedThreatActions":[
         "allow",
         "restore"
      ],
      "threatTypeSettingsMergePolicy":"merge",
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "enabled":true,
      "diagnosticLevel":"optional",
      "automaticSampleSubmissionConsent":"safe",
      "automaticDefinitionUpdateEnabled":true,
      "proxy": "http://proxy.server:port/"
   }
}
```

## <a name="configuration-profile-validation"></a><span data-ttu-id="04aa1-383">構成プロファイルの検証</span><span class="sxs-lookup"><span data-stu-id="04aa1-383">Configuration profile validation</span></span>

<span data-ttu-id="04aa1-384">構成プロファイルは、有効な JSON 形式のファイルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="04aa1-384">The configuration profile must be a valid JSON-formatted file.</span></span> <span data-ttu-id="04aa1-385">これを確認するために使用できるツールは多数ある。</span><span class="sxs-lookup"><span data-stu-id="04aa1-385">There are a number of tools that can be used to verify this.</span></span> <span data-ttu-id="04aa1-386">たとえば、デバイスにインストール `python` されている場合は、次の情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="04aa1-386">For example, if you have `python` installed on your device:</span></span>

```bash
python -m json.tool mdatp_managed.json
```

<span data-ttu-id="04aa1-387">JSON が整形式の場合、上記のコマンドはターミナルに出力し、終了コードを返します `0` 。</span><span class="sxs-lookup"><span data-stu-id="04aa1-387">If the JSON is well-formed, the above command outputs it back to the Terminal and returns an exit code of `0`.</span></span> <span data-ttu-id="04aa1-388">それ以外の場合は、問題を説明するエラーが表示され、コマンドは終了コードを返します `1` 。</span><span class="sxs-lookup"><span data-stu-id="04aa1-388">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a><span data-ttu-id="04aa1-389">ファイル上のmdatp_managed.jsが正常に動作しているのを確認する</span><span class="sxs-lookup"><span data-stu-id="04aa1-389">Verifying that the mdatp_managed.json file is working as expected</span></span>
<span data-ttu-id="04aa1-390">/etc/opt/microsoft/mdatp/managed/mdatp_managed.jsが正しく動作することを確認するには、次の設定の横に "[managed]" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="04aa1-390">To verify that your /etc/opt/microsoft/mdatp/managed/mdatp_managed.json is working properly, you should see "[managed]" next to these settings:</span></span>  
- <span data-ttu-id="04aa1-391">cloud_enabled</span><span class="sxs-lookup"><span data-stu-id="04aa1-391">cloud_enabled</span></span>
- <span data-ttu-id="04aa1-392">cloud_automatic_sample_submission_consent</span><span class="sxs-lookup"><span data-stu-id="04aa1-392">cloud_automatic_sample_submission_consent</span></span>
- <span data-ttu-id="04aa1-393">passice_mode_enabled</span><span class="sxs-lookup"><span data-stu-id="04aa1-393">passice_mode_enabled</span></span>
- <span data-ttu-id="04aa1-394">real_time_protection_enabled</span><span class="sxs-lookup"><span data-stu-id="04aa1-394">real_time_protection_enabled</span></span>
- <span data-ttu-id="04aa1-395">automatic_definition_update_enabled</span><span class="sxs-lookup"><span data-stu-id="04aa1-395">automatic_definition_update_enabled</span></span>

> [!NOTE]
> <span data-ttu-id="04aa1-396">有効にmdatp_managed.js、wdavdaemon の再起動は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="04aa1-396">For the mdatp_managed.json to take effect, no restart of the wdavdaemon is required.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="04aa1-397">構成プロファイルの展開</span><span class="sxs-lookup"><span data-stu-id="04aa1-397">Configuration profile deployment</span></span>

<span data-ttu-id="04aa1-398">企業の構成プロファイルを構築したら、企業が使用している管理ツールを使用して展開できます。</span><span class="sxs-lookup"><span data-stu-id="04aa1-398">Once you've built the configuration profile for your enterprise, you can deploy it through the management tool that your enterprise is using.</span></span> <span data-ttu-id="04aa1-399">Defender for Endpoint on Linux は *、/etc/opt/microsoft/mdatp/managed/mdatp_managed.jsファイルから管理構成を読み取* ります。</span><span class="sxs-lookup"><span data-stu-id="04aa1-399">Defender for Endpoint on Linux reads the managed configuration from the */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* file.</span></span>
