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
ms.openlocfilehash: 29505a6e975fdfa2283efe3391c615e40e678164
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346380"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="24501-104">Linux 上のエンドポイント用 Microsoft Defender の基本設定を設定する</span><span class="sxs-lookup"><span data-stu-id="24501-104">Set preferences for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="24501-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="24501-105">**Applies to:**</span></span>
- [<span data-ttu-id="24501-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="24501-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="24501-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="24501-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="24501-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="24501-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="24501-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="24501-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

>[!IMPORTANT]
><span data-ttu-id="24501-110">このトピックでは、エンタープライズ環境で Defender for Endpoint on Linux の基本設定を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="24501-110">This topic contains instructions for how to set preferences for Defender for Endpoint on Linux in enterprise environments.</span></span> <span data-ttu-id="24501-111">コマンド ラインからデバイスで製品を構成する場合は、「Resources」を参照 [してください](linux-resources.md#configure-from-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="24501-111">If you are interested in configuring the product on a device from the command-line, see [Resources](linux-resources.md#configure-from-the-command-line).</span></span>

<span data-ttu-id="24501-112">エンタープライズ環境では、Defender for Endpoint on Linux を構成プロファイルで管理できます。</span><span class="sxs-lookup"><span data-stu-id="24501-112">In enterprise environments, Defender for Endpoint on Linux can be managed through a configuration profile.</span></span> <span data-ttu-id="24501-113">このプロファイルは、選択した管理ツールから展開されます。</span><span class="sxs-lookup"><span data-stu-id="24501-113">This profile is deployed from the management tool of your choice.</span></span> <span data-ttu-id="24501-114">企業が管理する基本設定は、デバイス上でローカルに設定された基本設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="24501-114">Preferences managed by the enterprise take precedence over the ones set locally on the device.</span></span> <span data-ttu-id="24501-115">つまり、企業のユーザーは、この構成プロファイルを介して設定された基本設定を変更できないのです。</span><span class="sxs-lookup"><span data-stu-id="24501-115">In other words, users in your enterprise are not able to change preferences that are set through this configuration profile.</span></span>

<span data-ttu-id="24501-116">この記事では、このプロファイルの構造 (開始に使用できる推奨プロファイルを含む) と、プロファイルを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="24501-116">This article describes the structure of this profile (including a recommended profile that you can use to get started) and instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="24501-117">構成プロファイル構造</span><span class="sxs-lookup"><span data-stu-id="24501-117">Configuration profile structure</span></span>

<span data-ttu-id="24501-118">構成プロファイルは 、キーで識別されるエントリ (基本設定の名前を示す) で構成される .json ファイルで、その後に、基本設定の性質に依存する値が続きます。</span><span class="sxs-lookup"><span data-stu-id="24501-118">The configuration profile is a .json file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="24501-119">数値などの単純な値や、入れ子になった基本設定のリストなどの複雑な値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="24501-119">Values can be simple, such as a numerical value, or complex, such as a nested list of preferences.</span></span>

<span data-ttu-id="24501-120">通常、構成管理ツールを使用して、名前を持つファイルを場所 ```mdatp_managed.json``` にプッシュします ```/etc/opt/microsoft/mdatp/managed/``` 。</span><span class="sxs-lookup"><span data-stu-id="24501-120">Typically, you would use a configuration management tool to push a file with the name ```mdatp_managed.json``` at the location ```/etc/opt/microsoft/mdatp/managed/```.</span></span>

<span data-ttu-id="24501-121">構成プロファイルのトップ レベルには、製品全体の基本設定と、製品のサブエリアのエントリが含まれています。これは、次のセクションで詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="24501-121">The top level of the configuration profile includes product-wide preferences and entries for subareas of the product, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="24501-122">ウイルス対策エンジンの基本設定</span><span class="sxs-lookup"><span data-stu-id="24501-122">Antivirus engine preferences</span></span>

<span data-ttu-id="24501-123">構成 *プロファイルの antivirusEngine* セクションを使用して、製品のウイルス対策コンポーネントの基本設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="24501-123">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="24501-124">**Key**</span><span class="sxs-lookup"><span data-stu-id="24501-124">**Key**</span></span> | <span data-ttu-id="24501-125">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="24501-125">antivirusEngine</span></span> |
| <span data-ttu-id="24501-126">**データ型**</span><span class="sxs-lookup"><span data-stu-id="24501-126">**Data type**</span></span> | <span data-ttu-id="24501-127">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="24501-127">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="24501-128">**コメント**</span><span class="sxs-lookup"><span data-stu-id="24501-128">**Comments**</span></span> | <span data-ttu-id="24501-129">辞書の内容の説明については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="24501-129">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="24501-130">リアルタイム保護を有効/無効にする</span><span class="sxs-lookup"><span data-stu-id="24501-130">Enable / disable real-time protection</span></span>

<span data-ttu-id="24501-131">リアルタイム保護 (アクセス時のファイルのスキャン) を有効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="24501-131">Determines whether real-time protection (scan files as they are accessed) is enabled or not.</span></span>

|||
|:---|:---|
| <span data-ttu-id="24501-132">**Key**</span><span class="sxs-lookup"><span data-stu-id="24501-132">**Key**</span></span> | <span data-ttu-id="24501-133">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="24501-133">enableRealTimeProtection</span></span> |
| <span data-ttu-id="24501-134">**データ型**</span><span class="sxs-lookup"><span data-stu-id="24501-134">**Data type**</span></span> | <span data-ttu-id="24501-135">Boolean</span><span class="sxs-lookup"><span data-stu-id="24501-135">Boolean</span></span> |
| <span data-ttu-id="24501-136">**可能な値**</span><span class="sxs-lookup"><span data-stu-id="24501-136">**Possible values**</span></span> | <span data-ttu-id="24501-137">true (既定)</span><span class="sxs-lookup"><span data-stu-id="24501-137">true (default)</span></span> <br/> <span data-ttu-id="24501-138">false</span><span class="sxs-lookup"><span data-stu-id="24501-138">false</span></span> |
|||

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="24501-139">パッシブ モードを有効/無効にする</span><span class="sxs-lookup"><span data-stu-id="24501-139">Enable / disable passive mode</span></span>

<span data-ttu-id="24501-140">ウイルス対策エンジンがパッシブ モードで実行されるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="24501-140">Determines whether the antivirus engine runs in passive mode or not.</span></span> <span data-ttu-id="24501-141">パッシブ モードの場合:</span><span class="sxs-lookup"><span data-stu-id="24501-141">In passive mode:</span></span>
- <span data-ttu-id="24501-142">リアルタイム保護はオフです。</span><span class="sxs-lookup"><span data-stu-id="24501-142">Real-time protection is turned off.</span></span>
- <span data-ttu-id="24501-143">オンデマンド スキャンが有効です。</span><span class="sxs-lookup"><span data-stu-id="24501-143">On-demand scanning is turned on.</span></span>
- <span data-ttu-id="24501-144">脅威の自動修復が無効になります。</span><span class="sxs-lookup"><span data-stu-id="24501-144">Automatic threat remediation is turned off.</span></span>
- <span data-ttu-id="24501-145">セキュリティ インテリジェンスの更新プログラムが有効になっている。</span><span class="sxs-lookup"><span data-stu-id="24501-145">Security intelligence updates are turned on.</span></span>
- <span data-ttu-id="24501-146">[状態] メニュー アイコンは非表示です。</span><span class="sxs-lookup"><span data-stu-id="24501-146">Status menu icon is hidden.</span></span>

|||
|:---|:---|
| <span data-ttu-id="24501-147">**Key**</span><span class="sxs-lookup"><span data-stu-id="24501-147">**Key**</span></span> | <span data-ttu-id="24501-148">passiveMode</span><span class="sxs-lookup"><span data-stu-id="24501-148">passiveMode</span></span> |
| <span data-ttu-id="24501-149">**データ型**</span><span class="sxs-lookup"><span data-stu-id="24501-149">**Data type**</span></span> | <span data-ttu-id="24501-150">Boolean</span><span class="sxs-lookup"><span data-stu-id="24501-150">Boolean</span></span> |
| <span data-ttu-id="24501-151">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="24501-151">**Possible values**</span></span> | <span data-ttu-id="24501-152">false (既定)</span><span class="sxs-lookup"><span data-stu-id="24501-152">false (default)</span></span> <br/> <span data-ttu-id="24501-153">true</span><span class="sxs-lookup"><span data-stu-id="24501-153">true</span></span> |
| <span data-ttu-id="24501-154">**コメント**</span><span class="sxs-lookup"><span data-stu-id="24501-154">**Comments**</span></span> | <span data-ttu-id="24501-155">Defender for Endpoint version 100.67.60 以上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="24501-155">Available in Defender for Endpoint version 100.67.60 or higher.</span></span> |
|||

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="24501-156">除外マージ ポリシー</span><span class="sxs-lookup"><span data-stu-id="24501-156">Exclusion merge policy</span></span>

<span data-ttu-id="24501-157">除外のマージ ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="24501-157">Specifies the merge policy for exclusions.</span></span> <span data-ttu-id="24501-158">管理者定義の除外とユーザー定義の除外 ( ) の組み合わせ、または管理者定義の除外 ( ) のみを `merge` 組み合わせて指定できます `admin_only` 。</span><span class="sxs-lookup"><span data-stu-id="24501-158">It can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="24501-159">この設定は、ローカル ユーザーが独自の除外を定義するのを制限するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="24501-159">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|||
|:---|:---|
| <span data-ttu-id="24501-160">**Key**</span><span class="sxs-lookup"><span data-stu-id="24501-160">**Key**</span></span> | <span data-ttu-id="24501-161">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="24501-161">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="24501-162">**データ型**</span><span class="sxs-lookup"><span data-stu-id="24501-162">**Data type**</span></span> | <span data-ttu-id="24501-163">String</span><span class="sxs-lookup"><span data-stu-id="24501-163">String</span></span> |
| <span data-ttu-id="24501-164">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="24501-164">**Possible values**</span></span> | <span data-ttu-id="24501-165">merge (既定)</span><span class="sxs-lookup"><span data-stu-id="24501-165">merge (default)</span></span> <br/> <span data-ttu-id="24501-166">admin_only</span><span class="sxs-lookup"><span data-stu-id="24501-166">admin_only</span></span> |
| <span data-ttu-id="24501-167">**コメント**</span><span class="sxs-lookup"><span data-stu-id="24501-167">**Comments**</span></span> | <span data-ttu-id="24501-168">Defender for Endpoint version 100.83.73 以上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="24501-168">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="scan-exclusions"></a><span data-ttu-id="24501-169">スキャンの除外</span><span class="sxs-lookup"><span data-stu-id="24501-169">Scan exclusions</span></span>

<span data-ttu-id="24501-170">スキャンから除外されたエンティティ。</span><span class="sxs-lookup"><span data-stu-id="24501-170">Entities that have been excluded from the scan.</span></span> <span data-ttu-id="24501-171">除外は、完全パス、拡張子、またはファイル名で指定できます。</span><span class="sxs-lookup"><span data-stu-id="24501-171">Exclusions can be specified by full paths, extensions, or file names.</span></span>
<span data-ttu-id="24501-172">(除外はアイテムの配列として指定されます。管理者は必要な数の要素を任意の順序で指定できます)。</span><span class="sxs-lookup"><span data-stu-id="24501-172">(Exclusions are specified as an array of items, administrator can specify as many elements as necessary, in any order.)</span></span>

|||
|:---|:---|
| <span data-ttu-id="24501-173">**Key**</span><span class="sxs-lookup"><span data-stu-id="24501-173">**Key**</span></span> | <span data-ttu-id="24501-174">除外</span><span class="sxs-lookup"><span data-stu-id="24501-174">exclusions</span></span> |
| <span data-ttu-id="24501-175">**データ型**</span><span class="sxs-lookup"><span data-stu-id="24501-175">**Data type**</span></span> | <span data-ttu-id="24501-176">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="24501-176">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="24501-177">**コメント**</span><span class="sxs-lookup"><span data-stu-id="24501-177">**Comments**</span></span> | <span data-ttu-id="24501-178">辞書の内容の説明については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="24501-178">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="24501-179">**除外の種類**</span><span class="sxs-lookup"><span data-stu-id="24501-179">**Type of exclusion**</span></span>

<span data-ttu-id="24501-180">スキャンから除外されるコンテンツの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="24501-180">Specifies the type of content excluded from the scan.</span></span>

|||
|:---|:---|
| <span data-ttu-id="24501-181">**Key**</span><span class="sxs-lookup"><span data-stu-id="24501-181">**Key**</span></span> | <span data-ttu-id="24501-182">$type</span><span class="sxs-lookup"><span data-stu-id="24501-182">$type</span></span> |
| <span data-ttu-id="24501-183">**データ型**</span><span class="sxs-lookup"><span data-stu-id="24501-183">**Data type**</span></span> | <span data-ttu-id="24501-184">String</span><span class="sxs-lookup"><span data-stu-id="24501-184">String</span></span> |
| <span data-ttu-id="24501-185">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="24501-185">**Possible values**</span></span> | <span data-ttu-id="24501-186">excludedPath</span><span class="sxs-lookup"><span data-stu-id="24501-186">excludedPath</span></span> <br/> <span data-ttu-id="24501-187">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="24501-187">excludedFileExtension</span></span> <br/> <span data-ttu-id="24501-188">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="24501-188">excludedFileName</span></span> |
|||

<span data-ttu-id="24501-189">**除外されたコンテンツへのパス**</span><span class="sxs-lookup"><span data-stu-id="24501-189">**Path to excluded content**</span></span>

<span data-ttu-id="24501-190">完全なファイル パスでスキャンからコンテンツを除外するために使用します。</span><span class="sxs-lookup"><span data-stu-id="24501-190">Used to exclude content from the scan by full file path.</span></span>

|||
|:---|:---|
| <span data-ttu-id="24501-191">**Key**</span><span class="sxs-lookup"><span data-stu-id="24501-191">**Key**</span></span> | <span data-ttu-id="24501-192">path</span><span class="sxs-lookup"><span data-stu-id="24501-192">path</span></span> |
| <span data-ttu-id="24501-193">**データ型**</span><span class="sxs-lookup"><span data-stu-id="24501-193">**Data type**</span></span> | <span data-ttu-id="24501-194">String</span><span class="sxs-lookup"><span data-stu-id="24501-194">String</span></span> |
| <span data-ttu-id="24501-195">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="24501-195">**Possible values**</span></span> | <span data-ttu-id="24501-196">有効なパス</span><span class="sxs-lookup"><span data-stu-id="24501-196">valid paths</span></span> |
| <span data-ttu-id="24501-197">**コメント**</span><span class="sxs-lookup"><span data-stu-id="24501-197">**Comments**</span></span> | <span data-ttu-id="24501-198">適用 *できるのは、$type\*\*が excludedPath である場合のみです。*</span><span class="sxs-lookup"><span data-stu-id="24501-198">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="24501-199">**パスの種類 (ファイル/ディレクトリ)**</span><span class="sxs-lookup"><span data-stu-id="24501-199">**Path type (file / directory)**</span></span>

<span data-ttu-id="24501-200">*path* プロパティがファイルまたはディレクトリを参照しているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="24501-200">Indicates if the *path* property refers to a file or directory.</span></span> 

|||
|:---|:---|
| <span data-ttu-id="24501-201">**Key**</span><span class="sxs-lookup"><span data-stu-id="24501-201">**Key**</span></span> | <span data-ttu-id="24501-202">isDirectory</span><span class="sxs-lookup"><span data-stu-id="24501-202">isDirectory</span></span> |
| <span data-ttu-id="24501-203">**データ型**</span><span class="sxs-lookup"><span data-stu-id="24501-203">**Data type**</span></span> | <span data-ttu-id="24501-204">Boolean</span><span class="sxs-lookup"><span data-stu-id="24501-204">Boolean</span></span> |
| <span data-ttu-id="24501-205">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="24501-205">**Possible values**</span></span> | <span data-ttu-id="24501-206">false (既定)</span><span class="sxs-lookup"><span data-stu-id="24501-206">false (default)</span></span> <br/> <span data-ttu-id="24501-207">true</span><span class="sxs-lookup"><span data-stu-id="24501-207">true</span></span> |
| <span data-ttu-id="24501-208">**コメント**</span><span class="sxs-lookup"><span data-stu-id="24501-208">**Comments**</span></span> | <span data-ttu-id="24501-209">適用 *できるのは、$type\*\*が excludedPath である場合のみです。*</span><span class="sxs-lookup"><span data-stu-id="24501-209">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="24501-210">**スキャンから除外されたファイル拡張子**</span><span class="sxs-lookup"><span data-stu-id="24501-210">**File extension excluded from the scan**</span></span>

<span data-ttu-id="24501-211">ファイル拡張子でスキャンからコンテンツを除外するために使用します。</span><span class="sxs-lookup"><span data-stu-id="24501-211">Used to exclude content from the scan by file extension.</span></span>

|||
|:---|:---|
| <span data-ttu-id="24501-212">**Key**</span><span class="sxs-lookup"><span data-stu-id="24501-212">**Key**</span></span> | <span data-ttu-id="24501-213">拡張機能</span><span class="sxs-lookup"><span data-stu-id="24501-213">extension</span></span> |
| <span data-ttu-id="24501-214">**データ型**</span><span class="sxs-lookup"><span data-stu-id="24501-214">**Data type**</span></span> | <span data-ttu-id="24501-215">String</span><span class="sxs-lookup"><span data-stu-id="24501-215">String</span></span> |
| <span data-ttu-id="24501-216">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="24501-216">**Possible values**</span></span> | <span data-ttu-id="24501-217">有効なファイル拡張子</span><span class="sxs-lookup"><span data-stu-id="24501-217">valid file extensions</span></span> |
| <span data-ttu-id="24501-218">**コメント**</span><span class="sxs-lookup"><span data-stu-id="24501-218">**Comments**</span></span> | <span data-ttu-id="24501-219">適用 *できるのは* 、$type FileExtension が *除外されている場合のみです。*</span><span class="sxs-lookup"><span data-stu-id="24501-219">Applicable only if *$type* is *excludedFileExtension*</span></span> |
|||

<span data-ttu-id="24501-220">**スキャンから除外されるプロセス**</span><span class="sxs-lookup"><span data-stu-id="24501-220">**Process excluded from the scan**</span></span>

<span data-ttu-id="24501-221">すべてのファイル アクティビティがスキャンから除外されるプロセスを指定します。</span><span class="sxs-lookup"><span data-stu-id="24501-221">Specifies a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="24501-222">プロセスは、名前 (たとえば) または完全パス `cat` (たとえば) で指定できます `/bin/cat` 。</span><span class="sxs-lookup"><span data-stu-id="24501-222">The process can be specified either by its name (for example, `cat`) or full path (for example, `/bin/cat`).</span></span>

|||
|:---|:---|
| <span data-ttu-id="24501-223">**Key**</span><span class="sxs-lookup"><span data-stu-id="24501-223">**Key**</span></span> | <span data-ttu-id="24501-224">name</span><span class="sxs-lookup"><span data-stu-id="24501-224">name</span></span> |
| <span data-ttu-id="24501-225">**データ型**</span><span class="sxs-lookup"><span data-stu-id="24501-225">**Data type**</span></span> | <span data-ttu-id="24501-226">String</span><span class="sxs-lookup"><span data-stu-id="24501-226">String</span></span> |
| <span data-ttu-id="24501-227">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="24501-227">**Possible values**</span></span> | <span data-ttu-id="24501-228">任意の文字列</span><span class="sxs-lookup"><span data-stu-id="24501-228">any string</span></span> |
| <span data-ttu-id="24501-229">**コメント**</span><span class="sxs-lookup"><span data-stu-id="24501-229">**Comments**</span></span> | <span data-ttu-id="24501-230">ファイルが excludedFileName *$type\*\*場合にのみ適用されます。*</span><span class="sxs-lookup"><span data-stu-id="24501-230">Applicable only if *$type* is *excludedFileName*</span></span> |
|||

#### <a name="allowed-threats"></a><span data-ttu-id="24501-231">許可される脅威</span><span class="sxs-lookup"><span data-stu-id="24501-231">Allowed threats</span></span>

<span data-ttu-id="24501-232">製品によってブロックされ、代わりに実行が許可されている脅威の一覧 (名前で識別されます)。</span><span class="sxs-lookup"><span data-stu-id="24501-232">List of threats (identified by their name) that are not blocked by the product and are instead allowed to run.</span></span>

|||
|:---|:---|
| <span data-ttu-id="24501-233">**Key**</span><span class="sxs-lookup"><span data-stu-id="24501-233">**Key**</span></span> | <span data-ttu-id="24501-234">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="24501-234">allowedThreats</span></span> |
| <span data-ttu-id="24501-235">**データ型**</span><span class="sxs-lookup"><span data-stu-id="24501-235">**Data type**</span></span> | <span data-ttu-id="24501-236">文字列の配列</span><span class="sxs-lookup"><span data-stu-id="24501-236">Array of strings</span></span> |
|||

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="24501-237">禁止された脅威アクション</span><span class="sxs-lookup"><span data-stu-id="24501-237">Disallowed threat actions</span></span>

<span data-ttu-id="24501-238">脅威が検出された場合にデバイスのローカル ユーザーが実行できるアクションを制限します。</span><span class="sxs-lookup"><span data-stu-id="24501-238">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="24501-239">この一覧に含まれるアクションは、ユーザー インターフェイスには表示されません。</span><span class="sxs-lookup"><span data-stu-id="24501-239">The actions included in this list are not displayed in the user interface.</span></span>

|||
|:---|:---|
| <span data-ttu-id="24501-240">**Key**</span><span class="sxs-lookup"><span data-stu-id="24501-240">**Key**</span></span> | <span data-ttu-id="24501-241">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="24501-241">disallowedThreatActions</span></span> |
| <span data-ttu-id="24501-242">**データ型**</span><span class="sxs-lookup"><span data-stu-id="24501-242">**Data type**</span></span> | <span data-ttu-id="24501-243">文字列の配列</span><span class="sxs-lookup"><span data-stu-id="24501-243">Array of strings</span></span> |
| <span data-ttu-id="24501-244">**可能な値**</span><span class="sxs-lookup"><span data-stu-id="24501-244">**Possible values**</span></span> | <span data-ttu-id="24501-245">allow (ユーザーによる脅威の許可を制限する)</span><span class="sxs-lookup"><span data-stu-id="24501-245">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="24501-246">復元 (検疫からの脅威の復元をユーザーに制限する)</span><span class="sxs-lookup"><span data-stu-id="24501-246">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="24501-247">**コメント**</span><span class="sxs-lookup"><span data-stu-id="24501-247">**Comments**</span></span> | <span data-ttu-id="24501-248">Defender for Endpoint version 100.83.73 以上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="24501-248">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="threat-type-settings"></a><span data-ttu-id="24501-249">脅威の種類の設定</span><span class="sxs-lookup"><span data-stu-id="24501-249">Threat type settings</span></span>

<span data-ttu-id="24501-250">ウイルス *対策エンジンの threatTypeSettings* 基本設定は、製品による特定の脅威の種類の処理方法を制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="24501-250">The *threatTypeSettings* preference in the antivirus engine is used to control how certain threat types are handled by the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="24501-251">**Key**</span><span class="sxs-lookup"><span data-stu-id="24501-251">**Key**</span></span> | <span data-ttu-id="24501-252">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="24501-252">threatTypeSettings</span></span> |
| <span data-ttu-id="24501-253">**データ型**</span><span class="sxs-lookup"><span data-stu-id="24501-253">**Data type**</span></span> | <span data-ttu-id="24501-254">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="24501-254">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="24501-255">**コメント**</span><span class="sxs-lookup"><span data-stu-id="24501-255">**Comments**</span></span> | <span data-ttu-id="24501-256">辞書の内容の説明については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="24501-256">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="24501-257">**脅威の種類**</span><span class="sxs-lookup"><span data-stu-id="24501-257">**Threat type**</span></span>

<span data-ttu-id="24501-258">動作が構成されている脅威の種類。</span><span class="sxs-lookup"><span data-stu-id="24501-258">Type of threat for which the behavior is configured.</span></span>

|||
|:---|:---|
| <span data-ttu-id="24501-259">**Key**</span><span class="sxs-lookup"><span data-stu-id="24501-259">**Key**</span></span> | <span data-ttu-id="24501-260">キー</span><span class="sxs-lookup"><span data-stu-id="24501-260">key</span></span> |
| <span data-ttu-id="24501-261">**データ型**</span><span class="sxs-lookup"><span data-stu-id="24501-261">**Data type**</span></span> | <span data-ttu-id="24501-262">String</span><span class="sxs-lookup"><span data-stu-id="24501-262">String</span></span> |
| <span data-ttu-id="24501-263">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="24501-263">**Possible values**</span></span> | <span data-ttu-id="24501-264">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="24501-264">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="24501-265">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="24501-265">archive_bomb</span></span> |
|||

<span data-ttu-id="24501-266">**実行する操作**</span><span class="sxs-lookup"><span data-stu-id="24501-266">**Action to take**</span></span>

<span data-ttu-id="24501-267">前のセクションで指定した種類の脅威に出く際に実行するアクション。</span><span class="sxs-lookup"><span data-stu-id="24501-267">Action to take when coming across a threat of the type specified in the preceding section.</span></span> <span data-ttu-id="24501-268">次の指定が可能です。</span><span class="sxs-lookup"><span data-stu-id="24501-268">Can be:</span></span>

- <span data-ttu-id="24501-269">**監査**: デバイスは、この種類の脅威から保護されませんが、脅威に関するエントリがログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="24501-269">**Audit**: The device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="24501-270">**ブロック**: デバイスは、この種類の脅威から保護され、セキュリティ コンソールで通知されます。</span><span class="sxs-lookup"><span data-stu-id="24501-270">**Block**: The device is protected against this type of threat and you are notified in the security console.</span></span>
- <span data-ttu-id="24501-271">**オフ**: デバイスは、この種類の脅威から保護され、何もログに記録されません。</span><span class="sxs-lookup"><span data-stu-id="24501-271">**Off**: The device is not protected against this type of threat and nothing is logged.</span></span>

|||
|:---|:---|
| <span data-ttu-id="24501-272">**Key**</span><span class="sxs-lookup"><span data-stu-id="24501-272">**Key**</span></span> | <span data-ttu-id="24501-273">値</span><span class="sxs-lookup"><span data-stu-id="24501-273">value</span></span> |
| <span data-ttu-id="24501-274">**データ型**</span><span class="sxs-lookup"><span data-stu-id="24501-274">**Data type**</span></span> | <span data-ttu-id="24501-275">String</span><span class="sxs-lookup"><span data-stu-id="24501-275">String</span></span> |
| <span data-ttu-id="24501-276">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="24501-276">**Possible values**</span></span> | <span data-ttu-id="24501-277">監査 (既定)</span><span class="sxs-lookup"><span data-stu-id="24501-277">audit (default)</span></span> <br/> <span data-ttu-id="24501-278">block</span><span class="sxs-lookup"><span data-stu-id="24501-278">block</span></span> <br/> <span data-ttu-id="24501-279">off</span><span class="sxs-lookup"><span data-stu-id="24501-279">off</span></span> |
|||

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="24501-280">脅威の種類の設定の差し込みポリシー</span><span class="sxs-lookup"><span data-stu-id="24501-280">Threat type settings merge policy</span></span>

<span data-ttu-id="24501-281">脅威の種類の設定のマージ ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="24501-281">Specifies the merge policy for threat type settings.</span></span> <span data-ttu-id="24501-282">これは、管理者定義設定とユーザー定義設定 ( ) の組み合わせか、管理者定義の設定 ( ) のみを `merge` 組み合わせて使用できます `admin_only` 。</span><span class="sxs-lookup"><span data-stu-id="24501-282">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="24501-283">この設定を使用すると、ローカル ユーザーがさまざまな脅威の種類に対して独自の設定を定義するのを制限できます。</span><span class="sxs-lookup"><span data-stu-id="24501-283">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="24501-284">**Key**</span><span class="sxs-lookup"><span data-stu-id="24501-284">**Key**</span></span> | <span data-ttu-id="24501-285">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="24501-285">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="24501-286">**データ型**</span><span class="sxs-lookup"><span data-stu-id="24501-286">**Data type**</span></span> | <span data-ttu-id="24501-287">String</span><span class="sxs-lookup"><span data-stu-id="24501-287">String</span></span> |
| <span data-ttu-id="24501-288">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="24501-288">**Possible values**</span></span> | <span data-ttu-id="24501-289">merge (既定)</span><span class="sxs-lookup"><span data-stu-id="24501-289">merge (default)</span></span> <br/> <span data-ttu-id="24501-290">admin_only</span><span class="sxs-lookup"><span data-stu-id="24501-290">admin_only</span></span> |
| <span data-ttu-id="24501-291">**コメント**</span><span class="sxs-lookup"><span data-stu-id="24501-291">**Comments**</span></span> | <span data-ttu-id="24501-292">Defender for Endpoint version 100.83.73 以上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="24501-292">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="24501-293">ウイルス対策スキャン履歴の保持 (日数)</span><span class="sxs-lookup"><span data-stu-id="24501-293">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="24501-294">デバイスのスキャン履歴に結果が保持される日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="24501-294">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="24501-295">古いスキャン結果は履歴から削除されます。</span><span class="sxs-lookup"><span data-stu-id="24501-295">Old scan results are removed from the history.</span></span> <span data-ttu-id="24501-296">ディスクから削除された古い検疫済みファイル。</span><span class="sxs-lookup"><span data-stu-id="24501-296">Old quarantined files that are also removed from the disk.</span></span>

|||
|:---|:---|
| <span data-ttu-id="24501-297">**Key**</span><span class="sxs-lookup"><span data-stu-id="24501-297">**Key**</span></span> | <span data-ttu-id="24501-298">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="24501-298">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="24501-299">**データ型**</span><span class="sxs-lookup"><span data-stu-id="24501-299">**Data type**</span></span> | <span data-ttu-id="24501-300">String</span><span class="sxs-lookup"><span data-stu-id="24501-300">String</span></span> |
| <span data-ttu-id="24501-301">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="24501-301">**Possible values**</span></span> | <span data-ttu-id="24501-302">90 (既定)。</span><span class="sxs-lookup"><span data-stu-id="24501-302">90 (default).</span></span> <span data-ttu-id="24501-303">使用できる値は、1 日から 180 日です。</span><span class="sxs-lookup"><span data-stu-id="24501-303">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="24501-304">**コメント**</span><span class="sxs-lookup"><span data-stu-id="24501-304">**Comments**</span></span> | <span data-ttu-id="24501-305">Defender for Endpoint version 101.04.76 以上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="24501-305">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="24501-306">ウイルス対策スキャン履歴内のアイテムの最大数</span><span class="sxs-lookup"><span data-stu-id="24501-306">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="24501-307">スキャン履歴に保持するエントリの最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="24501-307">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="24501-308">エントリには、過去に実行されたオンデマンド スキャンとすべてのウイルス対策検出が含まれます。</span><span class="sxs-lookup"><span data-stu-id="24501-308">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|||
|:---|:---|
| <span data-ttu-id="24501-309">**Key**</span><span class="sxs-lookup"><span data-stu-id="24501-309">**Key**</span></span> | <span data-ttu-id="24501-310">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="24501-310">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="24501-311">**データ型**</span><span class="sxs-lookup"><span data-stu-id="24501-311">**Data type**</span></span> | <span data-ttu-id="24501-312">String</span><span class="sxs-lookup"><span data-stu-id="24501-312">String</span></span> |
| <span data-ttu-id="24501-313">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="24501-313">**Possible values**</span></span> | <span data-ttu-id="24501-314">10000 (既定値)。</span><span class="sxs-lookup"><span data-stu-id="24501-314">10000 (default).</span></span> <span data-ttu-id="24501-315">許可される値は、5000 アイテムから 15,000 アイテムまでです。</span><span class="sxs-lookup"><span data-stu-id="24501-315">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="24501-316">**コメント**</span><span class="sxs-lookup"><span data-stu-id="24501-316">**Comments**</span></span> | <span data-ttu-id="24501-317">Defender for Endpoint version 101.04.76 以上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="24501-317">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="24501-318">クラウドによる保護の基本設定</span><span class="sxs-lookup"><span data-stu-id="24501-318">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="24501-319">構成 *プロファイルの cloudService* エントリを使用して、製品のクラウド駆動型保護機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="24501-319">The *cloudService* entry in the configuration profile is used to configure the cloud-driven protection feature of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="24501-320">**Key**</span><span class="sxs-lookup"><span data-stu-id="24501-320">**Key**</span></span> | <span data-ttu-id="24501-321">cloudService</span><span class="sxs-lookup"><span data-stu-id="24501-321">cloudService</span></span> |
| <span data-ttu-id="24501-322">**データ型**</span><span class="sxs-lookup"><span data-stu-id="24501-322">**Data type**</span></span> | <span data-ttu-id="24501-323">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="24501-323">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="24501-324">**コメント**</span><span class="sxs-lookup"><span data-stu-id="24501-324">**Comments**</span></span> | <span data-ttu-id="24501-325">辞書の内容の説明については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="24501-325">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="24501-326">クラウド配信保護を有効/無効にする</span><span class="sxs-lookup"><span data-stu-id="24501-326">Enable / disable cloud delivered protection</span></span>

<span data-ttu-id="24501-327">デバイスでクラウド配信の保護を有効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="24501-327">Determines whether cloud-delivered protection is enabled on the device or not.</span></span> <span data-ttu-id="24501-328">サービスのセキュリティを向上させるために、この機能を有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="24501-328">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|||
|:---|:---|
| <span data-ttu-id="24501-329">**Key**</span><span class="sxs-lookup"><span data-stu-id="24501-329">**Key**</span></span> | <span data-ttu-id="24501-330">enabled</span><span class="sxs-lookup"><span data-stu-id="24501-330">enabled</span></span> |
| <span data-ttu-id="24501-331">**データ型**</span><span class="sxs-lookup"><span data-stu-id="24501-331">**Data type**</span></span> | <span data-ttu-id="24501-332">Boolean</span><span class="sxs-lookup"><span data-stu-id="24501-332">Boolean</span></span> |
| <span data-ttu-id="24501-333">**可能な値**</span><span class="sxs-lookup"><span data-stu-id="24501-333">**Possible values**</span></span> | <span data-ttu-id="24501-334">true (既定)</span><span class="sxs-lookup"><span data-stu-id="24501-334">true (default)</span></span> <br/> <span data-ttu-id="24501-335">false</span><span class="sxs-lookup"><span data-stu-id="24501-335">false</span></span> |
|||

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="24501-336">診断コレクション レベル</span><span class="sxs-lookup"><span data-stu-id="24501-336">Diagnostic collection level</span></span>

<span data-ttu-id="24501-337">診断データは、Defender for Endpoint を安全かつ最新の状態に保ち、問題を検出、診断、修正し、製品の改善を行う場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="24501-337">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="24501-338">この設定は、製品から Microsoft に送信される診断のレベルを決定します。</span><span class="sxs-lookup"><span data-stu-id="24501-338">This setting determines the level of diagnostics sent by the product to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="24501-339">**Key**</span><span class="sxs-lookup"><span data-stu-id="24501-339">**Key**</span></span> | <span data-ttu-id="24501-340">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="24501-340">diagnosticLevel</span></span> |
| <span data-ttu-id="24501-341">**データ型**</span><span class="sxs-lookup"><span data-stu-id="24501-341">**Data type**</span></span> | <span data-ttu-id="24501-342">String</span><span class="sxs-lookup"><span data-stu-id="24501-342">String</span></span> |
| <span data-ttu-id="24501-343">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="24501-343">**Possible values**</span></span> | <span data-ttu-id="24501-344">省略可能 (既定)</span><span class="sxs-lookup"><span data-stu-id="24501-344">optional (default)</span></span> <br/> <span data-ttu-id="24501-345">必須</span><span class="sxs-lookup"><span data-stu-id="24501-345">required</span></span> |
|||

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="24501-346">自動サンプル申請を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="24501-346">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="24501-347">疑わしいサンプル (脅威を含む可能性が高い) を Microsoft に送信するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="24501-347">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="24501-348">サンプル申請を制御するには、次の 3 つのレベルがあります。</span><span class="sxs-lookup"><span data-stu-id="24501-348">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="24501-349">**なし**: 疑わしいサンプルは Microsoft に送信されません。</span><span class="sxs-lookup"><span data-stu-id="24501-349">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="24501-350">**セーフ**: 個人を特定できる情報 (PII) を含む疑わしいサンプルだけが自動的に送信されます。</span><span class="sxs-lookup"><span data-stu-id="24501-350">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="24501-351">これは、この設定の既定値です。</span><span class="sxs-lookup"><span data-stu-id="24501-351">This is the default value for this setting.</span></span>
- <span data-ttu-id="24501-352">**すべて**: すべての疑わしいサンプルが Microsoft に送信されます。</span><span class="sxs-lookup"><span data-stu-id="24501-352">**All**: all suspicious samples are submitted to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="24501-353">**Key**</span><span class="sxs-lookup"><span data-stu-id="24501-353">**Key**</span></span> | <span data-ttu-id="24501-354">automaticSampleSubmissionConsent</span><span class="sxs-lookup"><span data-stu-id="24501-354">automaticSampleSubmissionConsent</span></span> |
| <span data-ttu-id="24501-355">**データ型**</span><span class="sxs-lookup"><span data-stu-id="24501-355">**Data type**</span></span> | <span data-ttu-id="24501-356">String</span><span class="sxs-lookup"><span data-stu-id="24501-356">String</span></span> |
| <span data-ttu-id="24501-357">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="24501-357">**Possible values**</span></span> | <span data-ttu-id="24501-358">none</span><span class="sxs-lookup"><span data-stu-id="24501-358">none</span></span> <br/> <span data-ttu-id="24501-359">safe (既定)</span><span class="sxs-lookup"><span data-stu-id="24501-359">safe (default)</span></span> <br/> <span data-ttu-id="24501-360">すべての</span><span class="sxs-lookup"><span data-stu-id="24501-360">all</span></span> |
|||

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="24501-361">セキュリティ インテリジェンスの自動更新を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="24501-361">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="24501-362">セキュリティ インテリジェンスの更新プログラムが自動的にインストールされるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="24501-362">Determines whether security intelligence updates are installed automatically:</span></span>

|||
|:---|:---|
| <span data-ttu-id="24501-363">**Key**</span><span class="sxs-lookup"><span data-stu-id="24501-363">**Key**</span></span> | <span data-ttu-id="24501-364">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="24501-364">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="24501-365">**データ型**</span><span class="sxs-lookup"><span data-stu-id="24501-365">**Data type**</span></span> | <span data-ttu-id="24501-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="24501-366">Boolean</span></span> |
| <span data-ttu-id="24501-367">**可能な値**</span><span class="sxs-lookup"><span data-stu-id="24501-367">**Possible values**</span></span> | <span data-ttu-id="24501-368">true (既定)</span><span class="sxs-lookup"><span data-stu-id="24501-368">true (default)</span></span> <br/> <span data-ttu-id="24501-369">false</span><span class="sxs-lookup"><span data-stu-id="24501-369">false</span></span> |
|||

## <a name="recommended-configuration-profile"></a><span data-ttu-id="24501-370">推奨される構成プロファイル</span><span class="sxs-lookup"><span data-stu-id="24501-370">Recommended configuration profile</span></span>

<span data-ttu-id="24501-371">開始するには、Defender for Endpoint が提供するすべての保護機能を利用するために、企業の次の構成プロファイルをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="24501-371">To get started, we recommend the following configuration profile for your enterprise to take advantage of all protection features that Defender for Endpoint provides.</span></span>

<span data-ttu-id="24501-372">次の構成プロファイルは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="24501-372">The following configuration profile will:</span></span>

- <span data-ttu-id="24501-373">リアルタイム保護を有効にする (RTP)</span><span class="sxs-lookup"><span data-stu-id="24501-373">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="24501-374">次の脅威の種類の処理方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="24501-374">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="24501-375">**望ましくない可能性のあるアプリケーション (PUA) が** ブロックされる</span><span class="sxs-lookup"><span data-stu-id="24501-375">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="24501-376">**アーカイブボム** (圧縮率が高いファイル) は、製品ログに対して監査されます</span><span class="sxs-lookup"><span data-stu-id="24501-376">**Archive bombs** (file with a high compression rate) are audited to the product logs</span></span>
- <span data-ttu-id="24501-377">セキュリティ インテリジェンスの自動更新を有効にする</span><span class="sxs-lookup"><span data-stu-id="24501-377">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="24501-378">クラウドによる保護の有効化</span><span class="sxs-lookup"><span data-stu-id="24501-378">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="24501-379">レベルで自動サンプル提出を `safe` 有効にする</span><span class="sxs-lookup"><span data-stu-id="24501-379">Enable automatic sample submission at `safe` level</span></span>

### <a name="sample-profile"></a><span data-ttu-id="24501-380">サンプル プロファイル</span><span class="sxs-lookup"><span data-stu-id="24501-380">Sample profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="24501-381">完全な構成プロファイルの例</span><span class="sxs-lookup"><span data-stu-id="24501-381">Full configuration profile example</span></span>

<span data-ttu-id="24501-382">次の構成プロファイルには、このドキュメントで説明されているすべての設定のエントリが含まれています。製品を詳細に制御する高度なシナリオに使用できます。</span><span class="sxs-lookup"><span data-stu-id="24501-382">The following configuration profile contains entries for all settings described in this document and can be used for more advanced scenarios where you want more control over the product.</span></span>

### <a name="full-profile"></a><span data-ttu-id="24501-383">フル プロファイル</span><span class="sxs-lookup"><span data-stu-id="24501-383">Full profile</span></span>

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
            "path":"/run"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/home/*/git"
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

## <a name="configuration-profile-validation"></a><span data-ttu-id="24501-384">構成プロファイルの検証</span><span class="sxs-lookup"><span data-stu-id="24501-384">Configuration profile validation</span></span>

<span data-ttu-id="24501-385">構成プロファイルは、有効な JSON 形式のファイルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="24501-385">The configuration profile must be a valid JSON-formatted file.</span></span> <span data-ttu-id="24501-386">これを確認するために使用できるツールは多数ある。</span><span class="sxs-lookup"><span data-stu-id="24501-386">There are a number of tools that can be used to verify this.</span></span> <span data-ttu-id="24501-387">たとえば、デバイスにインストール `python` されている場合は、次の情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="24501-387">For example, if you have `python` installed on your device:</span></span>

```bash
python -m json.tool mdatp_managed.json
```

<span data-ttu-id="24501-388">JSON が整形式の場合、上記のコマンドはターミナルに出力し、終了コードを返します `0` 。</span><span class="sxs-lookup"><span data-stu-id="24501-388">If the JSON is well-formed, the above command outputs it back to the Terminal and returns an exit code of `0`.</span></span> <span data-ttu-id="24501-389">それ以外の場合は、問題を説明するエラーが表示され、コマンドは終了コードを返します `1` 。</span><span class="sxs-lookup"><span data-stu-id="24501-389">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a><span data-ttu-id="24501-390">ファイル上のmdatp_managed.jsが正常に動作しているのを確認する</span><span class="sxs-lookup"><span data-stu-id="24501-390">Verifying that the mdatp_managed.json file is working as expected</span></span>
<span data-ttu-id="24501-391">/etc/opt/microsoft/mdatp/managed/mdatp_managed.jsが正しく動作することを確認するには、次の設定の横に "[managed]" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="24501-391">To verify that your /etc/opt/microsoft/mdatp/managed/mdatp_managed.json is working properly, you should see "[managed]" next to these settings:</span></span>  
- <span data-ttu-id="24501-392">cloud_enabled</span><span class="sxs-lookup"><span data-stu-id="24501-392">cloud_enabled</span></span>
- <span data-ttu-id="24501-393">cloud_automatic_sample_submission_consent</span><span class="sxs-lookup"><span data-stu-id="24501-393">cloud_automatic_sample_submission_consent</span></span>
- <span data-ttu-id="24501-394">passice_mode_enabled</span><span class="sxs-lookup"><span data-stu-id="24501-394">passice_mode_enabled</span></span>
- <span data-ttu-id="24501-395">real_time_protection_enabled</span><span class="sxs-lookup"><span data-stu-id="24501-395">real_time_protection_enabled</span></span>
- <span data-ttu-id="24501-396">automatic_definition_update_enabled</span><span class="sxs-lookup"><span data-stu-id="24501-396">automatic_definition_update_enabled</span></span>

> [!NOTE]
> <span data-ttu-id="24501-397">有効にmdatp_managed.js、wdavdaemon の再起動は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="24501-397">For the mdatp_managed.json to take effect, no restart of the wdavdaemon is required.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="24501-398">構成プロファイルの展開</span><span class="sxs-lookup"><span data-stu-id="24501-398">Configuration profile deployment</span></span>

<span data-ttu-id="24501-399">企業の構成プロファイルを構築したら、企業が使用している管理ツールを使用して展開できます。</span><span class="sxs-lookup"><span data-stu-id="24501-399">Once you've built the configuration profile for your enterprise, you can deploy it through the management tool that your enterprise is using.</span></span> <span data-ttu-id="24501-400">Defender for Endpoint on Linux は *、/etc/opt/microsoft/mdatp/managed/mdatp_managed.jsファイルから管理構成を読み取* ります。</span><span class="sxs-lookup"><span data-stu-id="24501-400">Defender for Endpoint on Linux reads the managed configuration from the */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* file.</span></span>
