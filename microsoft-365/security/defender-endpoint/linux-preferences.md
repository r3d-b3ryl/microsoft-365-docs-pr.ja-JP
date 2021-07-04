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
ms.openlocfilehash: 7998e878ad03fdfb64c314dc8b7234ece46164ce
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289495"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="9b4da-104">Linux 上のエンドポイント用 Microsoft Defender の基本設定を設定する</span><span class="sxs-lookup"><span data-stu-id="9b4da-104">Set preferences for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9b4da-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="9b4da-105">**Applies to:**</span></span>
- [<span data-ttu-id="9b4da-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9b4da-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9b4da-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9b4da-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9b4da-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="9b4da-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9b4da-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="9b4da-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="9b4da-110">このトピックでは、エンタープライズ環境で Defender for Endpoint on Linux の基本設定を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9b4da-110">This topic contains instructions for how to set preferences for Defender for Endpoint on Linux in enterprise environments.</span></span> <span data-ttu-id="9b4da-111">コマンド ラインからデバイスで製品を構成する場合は、「Resources」を参照 [してください](linux-resources.md#configure-from-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="9b4da-111">If you are interested in configuring the product on a device from the command-line, see [Resources](linux-resources.md#configure-from-the-command-line).</span></span>

<span data-ttu-id="9b4da-112">エンタープライズ環境では、Defender for Endpoint on Linux を構成プロファイルで管理できます。</span><span class="sxs-lookup"><span data-stu-id="9b4da-112">In enterprise environments, Defender for Endpoint on Linux can be managed through a configuration profile.</span></span> <span data-ttu-id="9b4da-113">このプロファイルは、選択した管理ツールから展開されます。</span><span class="sxs-lookup"><span data-stu-id="9b4da-113">This profile is deployed from the management tool of your choice.</span></span> <span data-ttu-id="9b4da-114">企業が管理する基本設定は、デバイス上でローカルに設定された基本設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="9b4da-114">Preferences managed by the enterprise take precedence over the ones set locally on the device.</span></span> <span data-ttu-id="9b4da-115">つまり、企業のユーザーは、この構成プロファイルを介して設定された基本設定を変更できないのです。</span><span class="sxs-lookup"><span data-stu-id="9b4da-115">In other words, users in your enterprise are not able to change preferences that are set through this configuration profile.</span></span>

<span data-ttu-id="9b4da-116">この記事では、このプロファイルの構造 (開始に使用できる推奨プロファイルを含む) と、プロファイルを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9b4da-116">This article describes the structure of this profile (including a recommended profile that you can use to get started) and instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="9b4da-117">構成プロファイル構造</span><span class="sxs-lookup"><span data-stu-id="9b4da-117">Configuration profile structure</span></span>

<span data-ttu-id="9b4da-118">構成プロファイルは 、キーで識別されるエントリ (基本設定の名前を示す) で構成される .json ファイルで、その後に、基本設定の性質に依存する値が続きます。</span><span class="sxs-lookup"><span data-stu-id="9b4da-118">The configuration profile is a .json file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="9b4da-119">数値などの単純な値や、入れ子になった基本設定のリストなどの複雑な値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="9b4da-119">Values can be simple, such as a numerical value, or complex, such as a nested list of preferences.</span></span>

<span data-ttu-id="9b4da-120">通常、構成管理ツールを使用して、名前を持つファイルを場所 ```mdatp_managed.json``` にプッシュします ```/etc/opt/microsoft/mdatp/managed/``` 。</span><span class="sxs-lookup"><span data-stu-id="9b4da-120">Typically, you would use a configuration management tool to push a file with the name ```mdatp_managed.json``` at the location ```/etc/opt/microsoft/mdatp/managed/```.</span></span>

<span data-ttu-id="9b4da-121">構成プロファイルのトップ レベルには、製品全体の基本設定と、製品のサブエリアのエントリが含まれています。これは、次のセクションで詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="9b4da-121">The top level of the configuration profile includes product-wide preferences and entries for subareas of the product, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="9b4da-122">ウイルス対策エンジンの基本設定</span><span class="sxs-lookup"><span data-stu-id="9b4da-122">Antivirus engine preferences</span></span>

<span data-ttu-id="9b4da-123">構成 *プロファイルの antivirusEngine* セクションを使用して、製品のウイルス対策コンポーネントの基本設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="9b4da-123">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of the product.</span></span>

<br>

****

|<span data-ttu-id="9b4da-124">説明</span><span class="sxs-lookup"><span data-stu-id="9b4da-124">Description</span></span>|<span data-ttu-id="9b4da-125">値</span><span class="sxs-lookup"><span data-stu-id="9b4da-125">Value</span></span>|
|---|---|
|<span data-ttu-id="9b4da-126">**Key**</span><span class="sxs-lookup"><span data-stu-id="9b4da-126">**Key**</span></span>|<span data-ttu-id="9b4da-127">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="9b4da-127">antivirusEngine</span></span>|
|<span data-ttu-id="9b4da-128">**データ型**</span><span class="sxs-lookup"><span data-stu-id="9b4da-128">**Data type**</span></span>|<span data-ttu-id="9b4da-129">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="9b4da-129">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="9b4da-130">**コメント**</span><span class="sxs-lookup"><span data-stu-id="9b4da-130">**Comments**</span></span>|<span data-ttu-id="9b4da-131">辞書の内容の説明については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b4da-131">See the following sections for a description of the dictionary contents.</span></span>|
|

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="9b4da-132">リアルタイム保護を有効/無効にする</span><span class="sxs-lookup"><span data-stu-id="9b4da-132">Enable / disable real-time protection</span></span>

<span data-ttu-id="9b4da-133">リアルタイム保護 (アクセス時のファイルのスキャン) を有効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="9b4da-133">Determines whether real-time protection (scan files as they are accessed) is enabled or not.</span></span>

<br>

****

|<span data-ttu-id="9b4da-134">説明</span><span class="sxs-lookup"><span data-stu-id="9b4da-134">Description</span></span>|<span data-ttu-id="9b4da-135">値</span><span class="sxs-lookup"><span data-stu-id="9b4da-135">Value</span></span>|
|---|---|
|<span data-ttu-id="9b4da-136">**Key**</span><span class="sxs-lookup"><span data-stu-id="9b4da-136">**Key**</span></span>|<span data-ttu-id="9b4da-137">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="9b4da-137">enableRealTimeProtection</span></span>|
|<span data-ttu-id="9b4da-138">**データ型**</span><span class="sxs-lookup"><span data-stu-id="9b4da-138">**Data type**</span></span>|<span data-ttu-id="9b4da-139">ブール型</span><span class="sxs-lookup"><span data-stu-id="9b4da-139">Boolean</span></span>|
|<span data-ttu-id="9b4da-140">**可能な値**</span><span class="sxs-lookup"><span data-stu-id="9b4da-140">**Possible values**</span></span>|<span data-ttu-id="9b4da-141">true (既定)</span><span class="sxs-lookup"><span data-stu-id="9b4da-141">true (default)</span></span> <p> <span data-ttu-id="9b4da-142">false</span><span class="sxs-lookup"><span data-stu-id="9b4da-142">false</span></span>|
|

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="9b4da-143">パッシブ モードを有効/無効にする</span><span class="sxs-lookup"><span data-stu-id="9b4da-143">Enable / disable passive mode</span></span>

<span data-ttu-id="9b4da-144">ウイルス対策エンジンがパッシブ モードで実行されるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="9b4da-144">Determines whether the antivirus engine runs in passive mode or not.</span></span> <span data-ttu-id="9b4da-145">パッシブ モードの場合:</span><span class="sxs-lookup"><span data-stu-id="9b4da-145">In passive mode:</span></span>

- <span data-ttu-id="9b4da-146">リアルタイム保護はオフです。</span><span class="sxs-lookup"><span data-stu-id="9b4da-146">Real-time protection is turned off.</span></span>
- <span data-ttu-id="9b4da-147">オンデマンド スキャンが有効です。</span><span class="sxs-lookup"><span data-stu-id="9b4da-147">On-demand scanning is turned on.</span></span>
- <span data-ttu-id="9b4da-148">脅威の自動修復が無効になります。</span><span class="sxs-lookup"><span data-stu-id="9b4da-148">Automatic threat remediation is turned off.</span></span>
- <span data-ttu-id="9b4da-149">セキュリティ インテリジェンスの更新プログラムが有効になっている。</span><span class="sxs-lookup"><span data-stu-id="9b4da-149">Security intelligence updates are turned on.</span></span>
- <span data-ttu-id="9b4da-150">[状態] メニュー アイコンは非表示です。</span><span class="sxs-lookup"><span data-stu-id="9b4da-150">Status menu icon is hidden.</span></span>

<br>

****

|<span data-ttu-id="9b4da-151">説明</span><span class="sxs-lookup"><span data-stu-id="9b4da-151">Description</span></span>|<span data-ttu-id="9b4da-152">値</span><span class="sxs-lookup"><span data-stu-id="9b4da-152">Value</span></span>|
|---|---|
|<span data-ttu-id="9b4da-153">**Key**</span><span class="sxs-lookup"><span data-stu-id="9b4da-153">**Key**</span></span>|<span data-ttu-id="9b4da-154">passiveMode</span><span class="sxs-lookup"><span data-stu-id="9b4da-154">passiveMode</span></span>|
|<span data-ttu-id="9b4da-155">**データ型**</span><span class="sxs-lookup"><span data-stu-id="9b4da-155">**Data type**</span></span>|<span data-ttu-id="9b4da-156">ブール型</span><span class="sxs-lookup"><span data-stu-id="9b4da-156">Boolean</span></span>|
|<span data-ttu-id="9b4da-157">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="9b4da-157">**Possible values**</span></span>|<span data-ttu-id="9b4da-158">false (既定)</span><span class="sxs-lookup"><span data-stu-id="9b4da-158">false (default)</span></span> <p> <span data-ttu-id="9b4da-159">true</span><span class="sxs-lookup"><span data-stu-id="9b4da-159">true</span></span>|
|<span data-ttu-id="9b4da-160">**コメント**</span><span class="sxs-lookup"><span data-stu-id="9b4da-160">**Comments**</span></span>|<span data-ttu-id="9b4da-161">Defender for Endpoint version 100.67.60 以上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="9b4da-161">Available in Defender for Endpoint version 100.67.60 or higher.</span></span>|
|

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="9b4da-162">除外マージ ポリシー</span><span class="sxs-lookup"><span data-stu-id="9b4da-162">Exclusion merge policy</span></span>

<span data-ttu-id="9b4da-163">除外のマージ ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="9b4da-163">Specifies the merge policy for exclusions.</span></span> <span data-ttu-id="9b4da-164">管理者定義の除外とユーザー定義の除外 ( ) の組み合わせ、または管理者定義の除外 ( ) のみを `merge` 組み合わせて指定できます `admin_only` 。</span><span class="sxs-lookup"><span data-stu-id="9b4da-164">It can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="9b4da-165">この設定は、ローカル ユーザーが独自の除外を定義するのを制限するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="9b4da-165">This setting can be used to restrict local users from defining their own exclusions.</span></span>

<br>

****

|<span data-ttu-id="9b4da-166">説明</span><span class="sxs-lookup"><span data-stu-id="9b4da-166">Description</span></span>|<span data-ttu-id="9b4da-167">値</span><span class="sxs-lookup"><span data-stu-id="9b4da-167">Value</span></span>|
|---|---|
|<span data-ttu-id="9b4da-168">**Key**</span><span class="sxs-lookup"><span data-stu-id="9b4da-168">**Key**</span></span>|<span data-ttu-id="9b4da-169">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="9b4da-169">exclusionsMergePolicy</span></span>|
|<span data-ttu-id="9b4da-170">**データ型**</span><span class="sxs-lookup"><span data-stu-id="9b4da-170">**Data type**</span></span>|<span data-ttu-id="9b4da-171">String</span><span class="sxs-lookup"><span data-stu-id="9b4da-171">String</span></span>|
|<span data-ttu-id="9b4da-172">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="9b4da-172">**Possible values**</span></span>|<span data-ttu-id="9b4da-173">merge (既定)</span><span class="sxs-lookup"><span data-stu-id="9b4da-173">merge (default)</span></span> <p> <span data-ttu-id="9b4da-174">admin_only</span><span class="sxs-lookup"><span data-stu-id="9b4da-174">admin_only</span></span>|
|<span data-ttu-id="9b4da-175">**コメント**</span><span class="sxs-lookup"><span data-stu-id="9b4da-175">**Comments**</span></span>|<span data-ttu-id="9b4da-176">Defender for Endpoint version 100.83.73 以上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="9b4da-176">Available in Defender for Endpoint version 100.83.73 or higher.</span></span>|
|

#### <a name="scan-exclusions"></a><span data-ttu-id="9b4da-177">スキャンの除外</span><span class="sxs-lookup"><span data-stu-id="9b4da-177">Scan exclusions</span></span>

<span data-ttu-id="9b4da-178">スキャンから除外されたエンティティ。</span><span class="sxs-lookup"><span data-stu-id="9b4da-178">Entities that have been excluded from the scan.</span></span> <span data-ttu-id="9b4da-179">除外は、完全パス、拡張子、またはファイル名で指定できます。</span><span class="sxs-lookup"><span data-stu-id="9b4da-179">Exclusions can be specified by full paths, extensions, or file names.</span></span>
<span data-ttu-id="9b4da-180">(除外はアイテムの配列として指定されます。管理者は必要な数の要素を任意の順序で指定できます)。</span><span class="sxs-lookup"><span data-stu-id="9b4da-180">(Exclusions are specified as an array of items, administrator can specify as many elements as necessary, in any order.)</span></span>

<br>

****

|<span data-ttu-id="9b4da-181">説明</span><span class="sxs-lookup"><span data-stu-id="9b4da-181">Description</span></span>|<span data-ttu-id="9b4da-182">値</span><span class="sxs-lookup"><span data-stu-id="9b4da-182">Value</span></span>|
|---|---|
|<span data-ttu-id="9b4da-183">**Key**</span><span class="sxs-lookup"><span data-stu-id="9b4da-183">**Key**</span></span>|<span data-ttu-id="9b4da-184">除外</span><span class="sxs-lookup"><span data-stu-id="9b4da-184">exclusions</span></span>|
|<span data-ttu-id="9b4da-185">**データ型**</span><span class="sxs-lookup"><span data-stu-id="9b4da-185">**Data type**</span></span>|<span data-ttu-id="9b4da-186">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="9b4da-186">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="9b4da-187">**コメント**</span><span class="sxs-lookup"><span data-stu-id="9b4da-187">**Comments**</span></span>|<span data-ttu-id="9b4da-188">辞書の内容の説明については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b4da-188">See the following sections for a description of the dictionary contents.</span></span>|
|

##### <a name="type-of-exclusion"></a><span data-ttu-id="9b4da-189">除外の種類</span><span class="sxs-lookup"><span data-stu-id="9b4da-189">Type of exclusion</span></span>

<span data-ttu-id="9b4da-190">スキャンから除外されるコンテンツの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="9b4da-190">Specifies the type of content excluded from the scan.</span></span>

<br>

****

|<span data-ttu-id="9b4da-191">説明</span><span class="sxs-lookup"><span data-stu-id="9b4da-191">Description</span></span>|<span data-ttu-id="9b4da-192">値</span><span class="sxs-lookup"><span data-stu-id="9b4da-192">Value</span></span>|
|---|---|
|<span data-ttu-id="9b4da-193">**Key**</span><span class="sxs-lookup"><span data-stu-id="9b4da-193">**Key**</span></span>|<span data-ttu-id="9b4da-194">$type</span><span class="sxs-lookup"><span data-stu-id="9b4da-194">$type</span></span>|
|<span data-ttu-id="9b4da-195">**データ型**</span><span class="sxs-lookup"><span data-stu-id="9b4da-195">**Data type**</span></span>|<span data-ttu-id="9b4da-196">String</span><span class="sxs-lookup"><span data-stu-id="9b4da-196">String</span></span>|
|<span data-ttu-id="9b4da-197">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="9b4da-197">**Possible values**</span></span>|<span data-ttu-id="9b4da-198">excludedPath</span><span class="sxs-lookup"><span data-stu-id="9b4da-198">excludedPath</span></span> <p> <span data-ttu-id="9b4da-199">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="9b4da-199">excludedFileExtension</span></span> <p> <span data-ttu-id="9b4da-200">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="9b4da-200">excludedFileName</span></span>|
|

##### <a name="path-to-excluded-content"></a><span data-ttu-id="9b4da-201">除外されたコンテンツへのパス</span><span class="sxs-lookup"><span data-stu-id="9b4da-201">Path to excluded content</span></span>

<span data-ttu-id="9b4da-202">完全なファイル パスでスキャンからコンテンツを除外するために使用します。</span><span class="sxs-lookup"><span data-stu-id="9b4da-202">Used to exclude content from the scan by full file path.</span></span>

<br>

****

|<span data-ttu-id="9b4da-203">説明</span><span class="sxs-lookup"><span data-stu-id="9b4da-203">Description</span></span>|<span data-ttu-id="9b4da-204">値</span><span class="sxs-lookup"><span data-stu-id="9b4da-204">Value</span></span>|
|---|---|
|<span data-ttu-id="9b4da-205">**Key**</span><span class="sxs-lookup"><span data-stu-id="9b4da-205">**Key**</span></span>|<span data-ttu-id="9b4da-206">path</span><span class="sxs-lookup"><span data-stu-id="9b4da-206">path</span></span>|
|<span data-ttu-id="9b4da-207">**データ型**</span><span class="sxs-lookup"><span data-stu-id="9b4da-207">**Data type**</span></span>|<span data-ttu-id="9b4da-208">String</span><span class="sxs-lookup"><span data-stu-id="9b4da-208">String</span></span>|
|<span data-ttu-id="9b4da-209">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="9b4da-209">**Possible values**</span></span>|<span data-ttu-id="9b4da-210">有効なパス</span><span class="sxs-lookup"><span data-stu-id="9b4da-210">valid paths</span></span>|
|<span data-ttu-id="9b4da-211">**コメント**</span><span class="sxs-lookup"><span data-stu-id="9b4da-211">**Comments**</span></span>|<span data-ttu-id="9b4da-212">適用 *できるのは、$type\*\*が excludedPath である場合のみです。*</span><span class="sxs-lookup"><span data-stu-id="9b4da-212">Applicable only if *$type* is *excludedPath*</span></span>|
|

##### <a name="path-type-file--directory"></a><span data-ttu-id="9b4da-213">パスの種類 (ファイル/ディレクトリ)</span><span class="sxs-lookup"><span data-stu-id="9b4da-213">Path type (file / directory)</span></span>

<span data-ttu-id="9b4da-214">*path* プロパティがファイルまたはディレクトリを参照しているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="9b4da-214">Indicates if the *path* property refers to a file or directory.</span></span>

<br>

****

|<span data-ttu-id="9b4da-215">説明</span><span class="sxs-lookup"><span data-stu-id="9b4da-215">Description</span></span>|<span data-ttu-id="9b4da-216">値</span><span class="sxs-lookup"><span data-stu-id="9b4da-216">Value</span></span>|
|---|---|
|<span data-ttu-id="9b4da-217">**Key**</span><span class="sxs-lookup"><span data-stu-id="9b4da-217">**Key**</span></span>|<span data-ttu-id="9b4da-218">isDirectory</span><span class="sxs-lookup"><span data-stu-id="9b4da-218">isDirectory</span></span>|
|<span data-ttu-id="9b4da-219">**データ型**</span><span class="sxs-lookup"><span data-stu-id="9b4da-219">**Data type**</span></span>|<span data-ttu-id="9b4da-220">ブール型</span><span class="sxs-lookup"><span data-stu-id="9b4da-220">Boolean</span></span>|
|<span data-ttu-id="9b4da-221">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="9b4da-221">**Possible values**</span></span>|<span data-ttu-id="9b4da-222">false (既定)</span><span class="sxs-lookup"><span data-stu-id="9b4da-222">false (default)</span></span> <p> <span data-ttu-id="9b4da-223">true</span><span class="sxs-lookup"><span data-stu-id="9b4da-223">true</span></span>|
|<span data-ttu-id="9b4da-224">**コメント**</span><span class="sxs-lookup"><span data-stu-id="9b4da-224">**Comments**</span></span>|<span data-ttu-id="9b4da-225">適用 *できるのは、$type\*\*が excludedPath である場合のみです。*</span><span class="sxs-lookup"><span data-stu-id="9b4da-225">Applicable only if *$type* is *excludedPath*</span></span>|
|

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="9b4da-226">スキャンから除外されたファイル拡張子</span><span class="sxs-lookup"><span data-stu-id="9b4da-226">File extension excluded from the scan</span></span>

<span data-ttu-id="9b4da-227">ファイル拡張子でスキャンからコンテンツを除外するために使用します。</span><span class="sxs-lookup"><span data-stu-id="9b4da-227">Used to exclude content from the scan by file extension.</span></span>

<br>

****

|<span data-ttu-id="9b4da-228">説明</span><span class="sxs-lookup"><span data-stu-id="9b4da-228">Description</span></span>|<span data-ttu-id="9b4da-229">値</span><span class="sxs-lookup"><span data-stu-id="9b4da-229">Value</span></span>|
|---|---|
|<span data-ttu-id="9b4da-230">**Key**</span><span class="sxs-lookup"><span data-stu-id="9b4da-230">**Key**</span></span>|<span data-ttu-id="9b4da-231">拡張機能</span><span class="sxs-lookup"><span data-stu-id="9b4da-231">extension</span></span>|
|<span data-ttu-id="9b4da-232">**データ型**</span><span class="sxs-lookup"><span data-stu-id="9b4da-232">**Data type**</span></span>|<span data-ttu-id="9b4da-233">String</span><span class="sxs-lookup"><span data-stu-id="9b4da-233">String</span></span>|
|<span data-ttu-id="9b4da-234">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="9b4da-234">**Possible values**</span></span>|<span data-ttu-id="9b4da-235">有効なファイル拡張子</span><span class="sxs-lookup"><span data-stu-id="9b4da-235">valid file extensions</span></span>|
|<span data-ttu-id="9b4da-236">**コメント**</span><span class="sxs-lookup"><span data-stu-id="9b4da-236">**Comments**</span></span>|<span data-ttu-id="9b4da-237">適用 *できるのは* 、$type FileExtension が *除外されている場合のみです。*</span><span class="sxs-lookup"><span data-stu-id="9b4da-237">Applicable only if *$type* is *excludedFileExtension*</span></span>|
|

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="9b4da-238">スキャンから除外されるプロセス\*</span><span class="sxs-lookup"><span data-stu-id="9b4da-238">Process excluded from the scan\*</span></span>

<span data-ttu-id="9b4da-239">すべてのファイル アクティビティがスキャンから除外されるプロセスを指定します。</span><span class="sxs-lookup"><span data-stu-id="9b4da-239">Specifies a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="9b4da-240">プロセスは、名前 (たとえば) または完全パス `cat` (たとえば) で指定できます `/bin/cat` 。</span><span class="sxs-lookup"><span data-stu-id="9b4da-240">The process can be specified either by its name (for example, `cat`) or full path (for example, `/bin/cat`).</span></span>

<br>

****

|<span data-ttu-id="9b4da-241">説明</span><span class="sxs-lookup"><span data-stu-id="9b4da-241">Description</span></span>|<span data-ttu-id="9b4da-242">値</span><span class="sxs-lookup"><span data-stu-id="9b4da-242">Value</span></span>|
|---|---|
|<span data-ttu-id="9b4da-243">**Key**</span><span class="sxs-lookup"><span data-stu-id="9b4da-243">**Key**</span></span>|<span data-ttu-id="9b4da-244">name</span><span class="sxs-lookup"><span data-stu-id="9b4da-244">name</span></span>|
|<span data-ttu-id="9b4da-245">**データ型**</span><span class="sxs-lookup"><span data-stu-id="9b4da-245">**Data type**</span></span>|<span data-ttu-id="9b4da-246">String</span><span class="sxs-lookup"><span data-stu-id="9b4da-246">String</span></span>|
|<span data-ttu-id="9b4da-247">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="9b4da-247">**Possible values**</span></span>|<span data-ttu-id="9b4da-248">任意の文字列</span><span class="sxs-lookup"><span data-stu-id="9b4da-248">any string</span></span>|
|<span data-ttu-id="9b4da-249">**コメント**</span><span class="sxs-lookup"><span data-stu-id="9b4da-249">**Comments**</span></span>|<span data-ttu-id="9b4da-250">ファイルが excludedFileName *$type\*\*場合にのみ適用されます。*</span><span class="sxs-lookup"><span data-stu-id="9b4da-250">Applicable only if *$type* is *excludedFileName*</span></span>|
|

#### <a name="allowed-threats"></a><span data-ttu-id="9b4da-251">許可される脅威</span><span class="sxs-lookup"><span data-stu-id="9b4da-251">Allowed threats</span></span>

<span data-ttu-id="9b4da-252">製品によってブロックされ、代わりに実行が許可されている脅威の一覧 (名前で識別されます)。</span><span class="sxs-lookup"><span data-stu-id="9b4da-252">List of threats (identified by their name) that are not blocked by the product and are instead allowed to run.</span></span>

<br>

****

|<span data-ttu-id="9b4da-253">説明</span><span class="sxs-lookup"><span data-stu-id="9b4da-253">Description</span></span>|<span data-ttu-id="9b4da-254">値</span><span class="sxs-lookup"><span data-stu-id="9b4da-254">Value</span></span>|
|---|---|
|<span data-ttu-id="9b4da-255">**Key**</span><span class="sxs-lookup"><span data-stu-id="9b4da-255">**Key**</span></span>|<span data-ttu-id="9b4da-256">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="9b4da-256">allowedThreats</span></span>|
|<span data-ttu-id="9b4da-257">**データ型**</span><span class="sxs-lookup"><span data-stu-id="9b4da-257">**Data type**</span></span>|<span data-ttu-id="9b4da-258">文字列の配列</span><span class="sxs-lookup"><span data-stu-id="9b4da-258">Array of strings</span></span>|
|

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="9b4da-259">禁止された脅威アクション</span><span class="sxs-lookup"><span data-stu-id="9b4da-259">Disallowed threat actions</span></span>

<span data-ttu-id="9b4da-260">脅威が検出された場合にデバイスのローカル ユーザーが実行できるアクションを制限します。</span><span class="sxs-lookup"><span data-stu-id="9b4da-260">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="9b4da-261">この一覧に含まれるアクションは、ユーザー インターフェイスには表示されません。</span><span class="sxs-lookup"><span data-stu-id="9b4da-261">The actions included in this list are not displayed in the user interface.</span></span>

<br>

****

|<span data-ttu-id="9b4da-262">説明</span><span class="sxs-lookup"><span data-stu-id="9b4da-262">Description</span></span>|<span data-ttu-id="9b4da-263">値</span><span class="sxs-lookup"><span data-stu-id="9b4da-263">Value</span></span>|
|---|---|
|<span data-ttu-id="9b4da-264">**Key**</span><span class="sxs-lookup"><span data-stu-id="9b4da-264">**Key**</span></span>|<span data-ttu-id="9b4da-265">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="9b4da-265">disallowedThreatActions</span></span>|
|<span data-ttu-id="9b4da-266">**データ型**</span><span class="sxs-lookup"><span data-stu-id="9b4da-266">**Data type**</span></span>|<span data-ttu-id="9b4da-267">文字列の配列</span><span class="sxs-lookup"><span data-stu-id="9b4da-267">Array of strings</span></span>|
|<span data-ttu-id="9b4da-268">**可能な値**</span><span class="sxs-lookup"><span data-stu-id="9b4da-268">**Possible values**</span></span>|<span data-ttu-id="9b4da-269">allow (ユーザーによる脅威の許可を制限する)</span><span class="sxs-lookup"><span data-stu-id="9b4da-269">allow (restricts users from allowing threats)</span></span> <p> <span data-ttu-id="9b4da-270">復元 (検疫からの脅威の復元をユーザーに制限する)</span><span class="sxs-lookup"><span data-stu-id="9b4da-270">restore (restricts users from restoring threats from the quarantine)</span></span>|
|<span data-ttu-id="9b4da-271">**コメント**</span><span class="sxs-lookup"><span data-stu-id="9b4da-271">**Comments**</span></span>|<span data-ttu-id="9b4da-272">Defender for Endpoint version 100.83.73 以上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="9b4da-272">Available in Defender for Endpoint version 100.83.73 or higher.</span></span>|
|

#### <a name="threat-type-settings"></a><span data-ttu-id="9b4da-273">脅威の種類の設定</span><span class="sxs-lookup"><span data-stu-id="9b4da-273">Threat type settings</span></span>

<span data-ttu-id="9b4da-274">ウイルス *対策エンジンの threatTypeSettings* 基本設定は、製品による特定の脅威の種類の処理方法を制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9b4da-274">The *threatTypeSettings* preference in the antivirus engine is used to control how certain threat types are handled by the product.</span></span>

<br>

****

|<span data-ttu-id="9b4da-275">説明</span><span class="sxs-lookup"><span data-stu-id="9b4da-275">Description</span></span>|<span data-ttu-id="9b4da-276">値</span><span class="sxs-lookup"><span data-stu-id="9b4da-276">Value</span></span>|
|---|---|
|<span data-ttu-id="9b4da-277">**Key**</span><span class="sxs-lookup"><span data-stu-id="9b4da-277">**Key**</span></span>|<span data-ttu-id="9b4da-278">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="9b4da-278">threatTypeSettings</span></span>|
|<span data-ttu-id="9b4da-279">**データ型**</span><span class="sxs-lookup"><span data-stu-id="9b4da-279">**Data type**</span></span>|<span data-ttu-id="9b4da-280">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="9b4da-280">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="9b4da-281">**コメント**</span><span class="sxs-lookup"><span data-stu-id="9b4da-281">**Comments**</span></span>|<span data-ttu-id="9b4da-282">辞書の内容の説明については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b4da-282">See the following sections for a description of the dictionary contents.</span></span>|
|

##### <a name="threat-type"></a><span data-ttu-id="9b4da-283">脅威の種類</span><span class="sxs-lookup"><span data-stu-id="9b4da-283">Threat type</span></span>

<span data-ttu-id="9b4da-284">動作が構成されている脅威の種類。</span><span class="sxs-lookup"><span data-stu-id="9b4da-284">Type of threat for which the behavior is configured.</span></span>

<br>

****

|<span data-ttu-id="9b4da-285">説明</span><span class="sxs-lookup"><span data-stu-id="9b4da-285">Description</span></span>|<span data-ttu-id="9b4da-286">値</span><span class="sxs-lookup"><span data-stu-id="9b4da-286">Value</span></span>|
|---|---|
|<span data-ttu-id="9b4da-287">**Key**</span><span class="sxs-lookup"><span data-stu-id="9b4da-287">**Key**</span></span>|<span data-ttu-id="9b4da-288">キー</span><span class="sxs-lookup"><span data-stu-id="9b4da-288">key</span></span>|
|<span data-ttu-id="9b4da-289">**データ型**</span><span class="sxs-lookup"><span data-stu-id="9b4da-289">**Data type**</span></span>|<span data-ttu-id="9b4da-290">String</span><span class="sxs-lookup"><span data-stu-id="9b4da-290">String</span></span>|
|<span data-ttu-id="9b4da-291">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="9b4da-291">**Possible values**</span></span>|<span data-ttu-id="9b4da-292">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="9b4da-292">potentially_unwanted_application</span></span> <p> <span data-ttu-id="9b4da-293">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="9b4da-293">archive_bomb</span></span>|
|

##### <a name="action-to-take"></a><span data-ttu-id="9b4da-294">実行する操作</span><span class="sxs-lookup"><span data-stu-id="9b4da-294">Action to take</span></span>

<span data-ttu-id="9b4da-295">前のセクションで指定した種類の脅威に出く際に実行するアクション。</span><span class="sxs-lookup"><span data-stu-id="9b4da-295">Action to take when coming across a threat of the type specified in the preceding section.</span></span> <span data-ttu-id="9b4da-296">次の指定が可能です。</span><span class="sxs-lookup"><span data-stu-id="9b4da-296">Can be:</span></span>

- <span data-ttu-id="9b4da-297">**監査**: デバイスは、この種類の脅威から保護されませんが、脅威に関するエントリがログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="9b4da-297">**Audit**: The device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="9b4da-298">**ブロック**: デバイスは、この種類の脅威から保護され、セキュリティ コンソールで通知されます。</span><span class="sxs-lookup"><span data-stu-id="9b4da-298">**Block**: The device is protected against this type of threat and you are notified in the security console.</span></span>
- <span data-ttu-id="9b4da-299">**オフ**: デバイスは、この種類の脅威から保護され、何もログに記録されません。</span><span class="sxs-lookup"><span data-stu-id="9b4da-299">**Off**: The device is not protected against this type of threat and nothing is logged.</span></span>

<br>

****

|<span data-ttu-id="9b4da-300">説明</span><span class="sxs-lookup"><span data-stu-id="9b4da-300">Description</span></span>|<span data-ttu-id="9b4da-301">値</span><span class="sxs-lookup"><span data-stu-id="9b4da-301">Value</span></span>|
|---|---|
|<span data-ttu-id="9b4da-302">**Key**</span><span class="sxs-lookup"><span data-stu-id="9b4da-302">**Key**</span></span>|<span data-ttu-id="9b4da-303">値</span><span class="sxs-lookup"><span data-stu-id="9b4da-303">value</span></span>|
|<span data-ttu-id="9b4da-304">**データ型**</span><span class="sxs-lookup"><span data-stu-id="9b4da-304">**Data type**</span></span>|<span data-ttu-id="9b4da-305">String</span><span class="sxs-lookup"><span data-stu-id="9b4da-305">String</span></span>|
|<span data-ttu-id="9b4da-306">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="9b4da-306">**Possible values**</span></span>|<span data-ttu-id="9b4da-307">監査 (既定)</span><span class="sxs-lookup"><span data-stu-id="9b4da-307">audit (default)</span></span> <p> <span data-ttu-id="9b4da-308">block</span><span class="sxs-lookup"><span data-stu-id="9b4da-308">block</span></span> <p> <span data-ttu-id="9b4da-309">off</span><span class="sxs-lookup"><span data-stu-id="9b4da-309">off</span></span>|
|

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="9b4da-310">脅威の種類の設定の差し込みポリシー</span><span class="sxs-lookup"><span data-stu-id="9b4da-310">Threat type settings merge policy</span></span>

<span data-ttu-id="9b4da-311">脅威の種類の設定のマージ ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="9b4da-311">Specifies the merge policy for threat type settings.</span></span> <span data-ttu-id="9b4da-312">これは、管理者定義設定とユーザー定義設定 ( ) の組み合わせか、管理者定義の設定 ( ) のみを `merge` 組み合わせて使用できます `admin_only` 。</span><span class="sxs-lookup"><span data-stu-id="9b4da-312">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="9b4da-313">この設定を使用すると、ローカル ユーザーがさまざまな脅威の種類に対して独自の設定を定義するのを制限できます。</span><span class="sxs-lookup"><span data-stu-id="9b4da-313">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

<br>

****

|<span data-ttu-id="9b4da-314">説明</span><span class="sxs-lookup"><span data-stu-id="9b4da-314">Description</span></span>|<span data-ttu-id="9b4da-315">値</span><span class="sxs-lookup"><span data-stu-id="9b4da-315">Value</span></span>|
|---|---|
|<span data-ttu-id="9b4da-316">**Key**</span><span class="sxs-lookup"><span data-stu-id="9b4da-316">**Key**</span></span>|<span data-ttu-id="9b4da-317">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="9b4da-317">threatTypeSettingsMergePolicy</span></span>|
|<span data-ttu-id="9b4da-318">**データ型**</span><span class="sxs-lookup"><span data-stu-id="9b4da-318">**Data type**</span></span>|<span data-ttu-id="9b4da-319">String</span><span class="sxs-lookup"><span data-stu-id="9b4da-319">String</span></span>|
|<span data-ttu-id="9b4da-320">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="9b4da-320">**Possible values**</span></span>|<span data-ttu-id="9b4da-321">merge (既定)</span><span class="sxs-lookup"><span data-stu-id="9b4da-321">merge (default)</span></span> <p> <span data-ttu-id="9b4da-322">admin_only</span><span class="sxs-lookup"><span data-stu-id="9b4da-322">admin_only</span></span>|
|<span data-ttu-id="9b4da-323">**コメント**</span><span class="sxs-lookup"><span data-stu-id="9b4da-323">**Comments**</span></span>|<span data-ttu-id="9b4da-324">Defender for Endpoint version 100.83.73 以上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="9b4da-324">Available in Defender for Endpoint version 100.83.73 or higher.</span></span>|
|

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="9b4da-325">ウイルス対策スキャン履歴の保持 (日数)</span><span class="sxs-lookup"><span data-stu-id="9b4da-325">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="9b4da-326">デバイスのスキャン履歴に結果が保持される日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="9b4da-326">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="9b4da-327">古いスキャン結果は履歴から削除されます。</span><span class="sxs-lookup"><span data-stu-id="9b4da-327">Old scan results are removed from the history.</span></span> <span data-ttu-id="9b4da-328">ディスクから削除された古い検疫済みファイル。</span><span class="sxs-lookup"><span data-stu-id="9b4da-328">Old quarantined files that are also removed from the disk.</span></span>

<br>

****

|<span data-ttu-id="9b4da-329">説明</span><span class="sxs-lookup"><span data-stu-id="9b4da-329">Description</span></span>|<span data-ttu-id="9b4da-330">値</span><span class="sxs-lookup"><span data-stu-id="9b4da-330">Value</span></span>|
|---|---|
|<span data-ttu-id="9b4da-331">**Key**</span><span class="sxs-lookup"><span data-stu-id="9b4da-331">**Key**</span></span>|<span data-ttu-id="9b4da-332">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="9b4da-332">scanResultsRetentionDays</span></span>|
|<span data-ttu-id="9b4da-333">**データ型**</span><span class="sxs-lookup"><span data-stu-id="9b4da-333">**Data type**</span></span>|<span data-ttu-id="9b4da-334">String</span><span class="sxs-lookup"><span data-stu-id="9b4da-334">String</span></span>|
|<span data-ttu-id="9b4da-335">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="9b4da-335">**Possible values**</span></span>|<span data-ttu-id="9b4da-336">90 (既定)。</span><span class="sxs-lookup"><span data-stu-id="9b4da-336">90 (default).</span></span> <span data-ttu-id="9b4da-337">使用できる値は、1 日から 180 日です。</span><span class="sxs-lookup"><span data-stu-id="9b4da-337">Allowed values are from 1 day to 180 days.</span></span>|
|<span data-ttu-id="9b4da-338">**コメント**</span><span class="sxs-lookup"><span data-stu-id="9b4da-338">**Comments**</span></span>|<span data-ttu-id="9b4da-339">Defender for Endpoint version 101.04.76 以上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="9b4da-339">Available in Defender for Endpoint version 101.04.76 or higher.</span></span>|
|

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="9b4da-340">ウイルス対策スキャン履歴内のアイテムの最大数</span><span class="sxs-lookup"><span data-stu-id="9b4da-340">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="9b4da-341">スキャン履歴に保持するエントリの最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="9b4da-341">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="9b4da-342">エントリには、過去に実行されたオンデマンド スキャンとすべてのウイルス対策検出が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9b4da-342">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

<br>

****

|<span data-ttu-id="9b4da-343">説明</span><span class="sxs-lookup"><span data-stu-id="9b4da-343">Description</span></span>|<span data-ttu-id="9b4da-344">値</span><span class="sxs-lookup"><span data-stu-id="9b4da-344">Value</span></span>|
|---|---|
|<span data-ttu-id="9b4da-345">**Key**</span><span class="sxs-lookup"><span data-stu-id="9b4da-345">**Key**</span></span>|<span data-ttu-id="9b4da-346">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="9b4da-346">scanHistoryMaximumItems</span></span>|
|<span data-ttu-id="9b4da-347">**データ型**</span><span class="sxs-lookup"><span data-stu-id="9b4da-347">**Data type**</span></span>|<span data-ttu-id="9b4da-348">String</span><span class="sxs-lookup"><span data-stu-id="9b4da-348">String</span></span>|
|<span data-ttu-id="9b4da-349">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="9b4da-349">**Possible values**</span></span>|<span data-ttu-id="9b4da-350">10000 (既定値)。</span><span class="sxs-lookup"><span data-stu-id="9b4da-350">10000 (default).</span></span> <span data-ttu-id="9b4da-351">許可される値は、5000 アイテムから 15,000 アイテムまでです。</span><span class="sxs-lookup"><span data-stu-id="9b4da-351">Allowed values are from 5000 items to 15000 items.</span></span>|
|<span data-ttu-id="9b4da-352">**コメント**</span><span class="sxs-lookup"><span data-stu-id="9b4da-352">**Comments**</span></span>|<span data-ttu-id="9b4da-353">Defender for Endpoint version 101.04.76 以上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="9b4da-353">Available in Defender for Endpoint version 101.04.76 or higher.</span></span>|
|

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="9b4da-354">クラウドによる保護の基本設定</span><span class="sxs-lookup"><span data-stu-id="9b4da-354">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="9b4da-355">構成 *プロファイルの cloudService* エントリを使用して、製品のクラウド駆動型保護機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="9b4da-355">The *cloudService* entry in the configuration profile is used to configure the cloud-driven protection feature of the product.</span></span>

<br>

****

|<span data-ttu-id="9b4da-356">説明</span><span class="sxs-lookup"><span data-stu-id="9b4da-356">Description</span></span>|<span data-ttu-id="9b4da-357">値</span><span class="sxs-lookup"><span data-stu-id="9b4da-357">Value</span></span>|
|---|---|
|<span data-ttu-id="9b4da-358">**Key**</span><span class="sxs-lookup"><span data-stu-id="9b4da-358">**Key**</span></span>|<span data-ttu-id="9b4da-359">cloudService</span><span class="sxs-lookup"><span data-stu-id="9b4da-359">cloudService</span></span>|
|<span data-ttu-id="9b4da-360">**データ型**</span><span class="sxs-lookup"><span data-stu-id="9b4da-360">**Data type**</span></span>|<span data-ttu-id="9b4da-361">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="9b4da-361">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="9b4da-362">**コメント**</span><span class="sxs-lookup"><span data-stu-id="9b4da-362">**Comments**</span></span>|<span data-ttu-id="9b4da-363">辞書の内容の説明については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b4da-363">See the following sections for a description of the dictionary contents.</span></span>|
|

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="9b4da-364">クラウド配信保護を有効/無効にする</span><span class="sxs-lookup"><span data-stu-id="9b4da-364">Enable / disable cloud delivered protection</span></span>

<span data-ttu-id="9b4da-365">デバイスでクラウド配信の保護を有効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="9b4da-365">Determines whether cloud-delivered protection is enabled on the device or not.</span></span> <span data-ttu-id="9b4da-366">サービスのセキュリティを向上させるために、この機能を有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9b4da-366">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

<br>

****

|<span data-ttu-id="9b4da-367">説明</span><span class="sxs-lookup"><span data-stu-id="9b4da-367">Description</span></span>|<span data-ttu-id="9b4da-368">値</span><span class="sxs-lookup"><span data-stu-id="9b4da-368">Value</span></span>|
|---|---|
|<span data-ttu-id="9b4da-369">**Key**</span><span class="sxs-lookup"><span data-stu-id="9b4da-369">**Key**</span></span>|<span data-ttu-id="9b4da-370">enabled</span><span class="sxs-lookup"><span data-stu-id="9b4da-370">enabled</span></span>|
|<span data-ttu-id="9b4da-371">**データ型**</span><span class="sxs-lookup"><span data-stu-id="9b4da-371">**Data type**</span></span>|<span data-ttu-id="9b4da-372">ブール型</span><span class="sxs-lookup"><span data-stu-id="9b4da-372">Boolean</span></span>|
|<span data-ttu-id="9b4da-373">**可能な値**</span><span class="sxs-lookup"><span data-stu-id="9b4da-373">**Possible values**</span></span>|<span data-ttu-id="9b4da-374">true (既定)</span><span class="sxs-lookup"><span data-stu-id="9b4da-374">true (default)</span></span> <p> <span data-ttu-id="9b4da-375">false</span><span class="sxs-lookup"><span data-stu-id="9b4da-375">false</span></span>|
|

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="9b4da-376">診断コレクション レベル</span><span class="sxs-lookup"><span data-stu-id="9b4da-376">Diagnostic collection level</span></span>

<span data-ttu-id="9b4da-377">診断データは、Defender for Endpoint を安全かつ最新の状態に保ち、問題を検出、診断、修正し、製品の改善を行う場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="9b4da-377">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="9b4da-378">この設定は、製品から Microsoft に送信される診断のレベルを決定します。</span><span class="sxs-lookup"><span data-stu-id="9b4da-378">This setting determines the level of diagnostics sent by the product to Microsoft.</span></span>

<br>

****

|<span data-ttu-id="9b4da-379">説明</span><span class="sxs-lookup"><span data-stu-id="9b4da-379">Description</span></span>|<span data-ttu-id="9b4da-380">値</span><span class="sxs-lookup"><span data-stu-id="9b4da-380">Value</span></span>|
|---|---|
|<span data-ttu-id="9b4da-381">**Key**</span><span class="sxs-lookup"><span data-stu-id="9b4da-381">**Key**</span></span>|<span data-ttu-id="9b4da-382">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="9b4da-382">diagnosticLevel</span></span>|
|<span data-ttu-id="9b4da-383">**データ型**</span><span class="sxs-lookup"><span data-stu-id="9b4da-383">**Data type**</span></span>|<span data-ttu-id="9b4da-384">String</span><span class="sxs-lookup"><span data-stu-id="9b4da-384">String</span></span>|
|<span data-ttu-id="9b4da-385">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="9b4da-385">**Possible values**</span></span>|<span data-ttu-id="9b4da-386">省略可能 (既定)</span><span class="sxs-lookup"><span data-stu-id="9b4da-386">optional (default)</span></span> <p> <span data-ttu-id="9b4da-387">必須</span><span class="sxs-lookup"><span data-stu-id="9b4da-387">required</span></span>|
|

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="9b4da-388">自動サンプル申請を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="9b4da-388">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="9b4da-389">疑わしいサンプル (脅威を含む可能性が高い) を Microsoft に送信するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="9b4da-389">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="9b4da-390">サンプル申請を制御するには、次の 3 つのレベルがあります。</span><span class="sxs-lookup"><span data-stu-id="9b4da-390">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="9b4da-391">**なし**: 疑わしいサンプルは Microsoft に送信されません。</span><span class="sxs-lookup"><span data-stu-id="9b4da-391">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="9b4da-392">**セーフ**: 個人を特定できる情報 (PII) を含む疑わしいサンプルだけが自動的に送信されます。</span><span class="sxs-lookup"><span data-stu-id="9b4da-392">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="9b4da-393">これは、この設定の既定値です。</span><span class="sxs-lookup"><span data-stu-id="9b4da-393">This is the default value for this setting.</span></span>
- <span data-ttu-id="9b4da-394">**すべて**: すべての疑わしいサンプルが Microsoft に送信されます。</span><span class="sxs-lookup"><span data-stu-id="9b4da-394">**All**: all suspicious samples are submitted to Microsoft.</span></span>

<br>

****

|<span data-ttu-id="9b4da-395">説明</span><span class="sxs-lookup"><span data-stu-id="9b4da-395">Description</span></span>|<span data-ttu-id="9b4da-396">値</span><span class="sxs-lookup"><span data-stu-id="9b4da-396">Value</span></span>|
|---|---|
|<span data-ttu-id="9b4da-397">**Key**</span><span class="sxs-lookup"><span data-stu-id="9b4da-397">**Key**</span></span>|<span data-ttu-id="9b4da-398">automaticSampleSubmissionConsent</span><span class="sxs-lookup"><span data-stu-id="9b4da-398">automaticSampleSubmissionConsent</span></span>|
|<span data-ttu-id="9b4da-399">**データ型**</span><span class="sxs-lookup"><span data-stu-id="9b4da-399">**Data type**</span></span>|<span data-ttu-id="9b4da-400">String</span><span class="sxs-lookup"><span data-stu-id="9b4da-400">String</span></span>|
|<span data-ttu-id="9b4da-401">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="9b4da-401">**Possible values**</span></span>|<span data-ttu-id="9b4da-402">none</span><span class="sxs-lookup"><span data-stu-id="9b4da-402">none</span></span> <p> <span data-ttu-id="9b4da-403">safe (既定)</span><span class="sxs-lookup"><span data-stu-id="9b4da-403">safe (default)</span></span> <p> <span data-ttu-id="9b4da-404">すべての</span><span class="sxs-lookup"><span data-stu-id="9b4da-404">all</span></span>|
|

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="9b4da-405">セキュリティ インテリジェンスの自動更新を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="9b4da-405">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="9b4da-406">セキュリティ インテリジェンスの更新プログラムが自動的にインストールされるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="9b4da-406">Determines whether security intelligence updates are installed automatically:</span></span>

<br>

****

|<span data-ttu-id="9b4da-407">説明</span><span class="sxs-lookup"><span data-stu-id="9b4da-407">Description</span></span>|<span data-ttu-id="9b4da-408">値</span><span class="sxs-lookup"><span data-stu-id="9b4da-408">Value</span></span>|
|---|---|
|<span data-ttu-id="9b4da-409">**Key**</span><span class="sxs-lookup"><span data-stu-id="9b4da-409">**Key**</span></span>|<span data-ttu-id="9b4da-410">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="9b4da-410">automaticDefinitionUpdateEnabled</span></span>|
|<span data-ttu-id="9b4da-411">**データ型**</span><span class="sxs-lookup"><span data-stu-id="9b4da-411">**Data type**</span></span>|<span data-ttu-id="9b4da-412">ブール型</span><span class="sxs-lookup"><span data-stu-id="9b4da-412">Boolean</span></span>|
|<span data-ttu-id="9b4da-413">**可能な値**</span><span class="sxs-lookup"><span data-stu-id="9b4da-413">**Possible values**</span></span>|<span data-ttu-id="9b4da-414">true (既定)</span><span class="sxs-lookup"><span data-stu-id="9b4da-414">true (default)</span></span> <p> <span data-ttu-id="9b4da-415">false</span><span class="sxs-lookup"><span data-stu-id="9b4da-415">false</span></span>|
|

## <a name="recommended-configuration-profile"></a><span data-ttu-id="9b4da-416">推奨される構成プロファイル</span><span class="sxs-lookup"><span data-stu-id="9b4da-416">Recommended configuration profile</span></span>

<span data-ttu-id="9b4da-417">開始するには、Defender for Endpoint が提供するすべての保護機能を利用するために、企業の次の構成プロファイルをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9b4da-417">To get started, we recommend the following configuration profile for your enterprise to take advantage of all protection features that Defender for Endpoint provides.</span></span>

<span data-ttu-id="9b4da-418">次の構成プロファイルは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9b4da-418">The following configuration profile will:</span></span>

- <span data-ttu-id="9b4da-419">リアルタイム保護を有効にする (RTP)</span><span class="sxs-lookup"><span data-stu-id="9b4da-419">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="9b4da-420">次の脅威の種類の処理方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="9b4da-420">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="9b4da-421">**望ましくない可能性のあるアプリケーション (PUA) が** ブロックされる</span><span class="sxs-lookup"><span data-stu-id="9b4da-421">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="9b4da-422">**アーカイブボム** (圧縮率が高いファイル) は、製品ログに対して監査されます</span><span class="sxs-lookup"><span data-stu-id="9b4da-422">**Archive bombs** (file with a high compression rate) are audited to the product logs</span></span>
- <span data-ttu-id="9b4da-423">セキュリティ インテリジェンスの自動更新を有効にする</span><span class="sxs-lookup"><span data-stu-id="9b4da-423">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="9b4da-424">クラウドによる保護の有効化</span><span class="sxs-lookup"><span data-stu-id="9b4da-424">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="9b4da-425">レベルで自動サンプル提出を `safe` 有効にする</span><span class="sxs-lookup"><span data-stu-id="9b4da-425">Enable automatic sample submission at `safe` level</span></span>

### <a name="sample-profile"></a><span data-ttu-id="9b4da-426">サンプル プロファイル</span><span class="sxs-lookup"><span data-stu-id="9b4da-426">Sample profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="9b4da-427">完全な構成プロファイルの例</span><span class="sxs-lookup"><span data-stu-id="9b4da-427">Full configuration profile example</span></span>

<span data-ttu-id="9b4da-428">次の構成プロファイルには、このドキュメントで説明されているすべての設定のエントリが含まれています。製品を詳細に制御する高度なシナリオに使用できます。</span><span class="sxs-lookup"><span data-stu-id="9b4da-428">The following configuration profile contains entries for all settings described in this document and can be used for more advanced scenarios where you want more control over the product.</span></span>

### <a name="full-profile"></a><span data-ttu-id="9b4da-429">フル プロファイル</span><span class="sxs-lookup"><span data-stu-id="9b4da-429">Full profile</span></span>

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
            "extension":".pdf"
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

## <a name="configuration-profile-validation"></a><span data-ttu-id="9b4da-430">構成プロファイルの検証</span><span class="sxs-lookup"><span data-stu-id="9b4da-430">Configuration profile validation</span></span>

<span data-ttu-id="9b4da-431">構成プロファイルは、有効な JSON 形式のファイルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b4da-431">The configuration profile must be a valid JSON-formatted file.</span></span> <span data-ttu-id="9b4da-432">これを確認するために使用できるツールは多数ある。</span><span class="sxs-lookup"><span data-stu-id="9b4da-432">There are a number of tools that can be used to verify this.</span></span> <span data-ttu-id="9b4da-433">たとえば、デバイスにインストール `python` されている場合は、次の情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="9b4da-433">For example, if you have `python` installed on your device:</span></span>

```bash
python -m json.tool mdatp_managed.json
```

<span data-ttu-id="9b4da-434">JSON が整形式の場合、上記のコマンドはターミナルに出力し、終了コードを返します `0` 。</span><span class="sxs-lookup"><span data-stu-id="9b4da-434">If the JSON is well-formed, the above command outputs it back to the Terminal and returns an exit code of `0`.</span></span> <span data-ttu-id="9b4da-435">それ以外の場合は、問題を説明するエラーが表示され、コマンドは終了コードを返します `1` 。</span><span class="sxs-lookup"><span data-stu-id="9b4da-435">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a><span data-ttu-id="9b4da-436">ファイル上のmdatp_managed.jsが正常に動作しているのを確認する</span><span class="sxs-lookup"><span data-stu-id="9b4da-436">Verifying that the mdatp_managed.json file is working as expected</span></span>

<span data-ttu-id="9b4da-437">/etc/opt/microsoft/mdatp/managed/mdatp_managed.jsが正しく動作することを確認するには、次の設定の横に "[managed]" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b4da-437">To verify that your /etc/opt/microsoft/mdatp/managed/mdatp_managed.json is working properly, you should see "[managed]" next to these settings:</span></span>

- <span data-ttu-id="9b4da-438">cloud_enabled</span><span class="sxs-lookup"><span data-stu-id="9b4da-438">cloud_enabled</span></span>
- <span data-ttu-id="9b4da-439">cloud_automatic_sample_submission_consent</span><span class="sxs-lookup"><span data-stu-id="9b4da-439">cloud_automatic_sample_submission_consent</span></span>
- <span data-ttu-id="9b4da-440">passive_mode_enabled</span><span class="sxs-lookup"><span data-stu-id="9b4da-440">passive_mode_enabled</span></span>
- <span data-ttu-id="9b4da-441">real_time_protection_enabled</span><span class="sxs-lookup"><span data-stu-id="9b4da-441">real_time_protection_enabled</span></span>
- <span data-ttu-id="9b4da-442">automatic_definition_update_enabled</span><span class="sxs-lookup"><span data-stu-id="9b4da-442">automatic_definition_update_enabled</span></span>

> [!NOTE]
> <span data-ttu-id="9b4da-443">有効にmdatp_managed.js、wdavdaemon の再起動は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="9b4da-443">For the mdatp_managed.json to take effect, no restart of the wdavdaemon is required.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="9b4da-444">構成プロファイルの展開</span><span class="sxs-lookup"><span data-stu-id="9b4da-444">Configuration profile deployment</span></span>

<span data-ttu-id="9b4da-445">企業の構成プロファイルを構築したら、企業が使用している管理ツールを使用して展開できます。</span><span class="sxs-lookup"><span data-stu-id="9b4da-445">Once you've built the configuration profile for your enterprise, you can deploy it through the management tool that your enterprise is using.</span></span> <span data-ttu-id="9b4da-446">Defender for Endpoint on Linux は *、/etc/opt/microsoft/mdatp/managed/mdatp_managed.jsファイルから管理構成を読み取* ります。</span><span class="sxs-lookup"><span data-stu-id="9b4da-446">Defender for Endpoint on Linux reads the managed configuration from the */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* file.</span></span>
