---
title: Mac 上のエンドポイント用 Microsoft Defender の基本設定を設定する
description: エンタープライズ組織で MMicrosoft Defender for Endpoint on Mac を構成します。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, mac, management, preferences, enterprise, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: b706cb8dbd43d545768c1c573021b5ef401e3c09
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346404"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="361b4-104">macOS のエンドポイント用 Microsoft Defender の基本設定を設定する</span><span class="sxs-lookup"><span data-stu-id="361b4-104">Set preferences for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="361b4-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="361b4-105">**Applies to:**</span></span>

- [<span data-ttu-id="361b4-106">macOS 用 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="361b4-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
><span data-ttu-id="361b4-107">この記事では、エンタープライズ組織の macOS で Microsoft Defender for Endpoint の基本設定を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="361b4-107">This article contains instructions for how to set preferences for Microsoft Defender for Endpoint on macOS in enterprise organizations.</span></span> <span data-ttu-id="361b4-108">コマンド ライン インターフェイスを使用して macOS 上の Microsoft Defender for Endpoint を構成するには、「Resources」を [参照してください](mac-resources.md#configuring-from-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="361b4-108">To configure Microsoft Defender for Endpoint on macOS using the command-line interface, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

## <a name="summary"></a><span data-ttu-id="361b4-109">概要</span><span class="sxs-lookup"><span data-stu-id="361b4-109">Summary</span></span>

<span data-ttu-id="361b4-110">エンタープライズ組織では、macOS 上の Microsoft Defender for Endpoint を、いくつかの管理ツールのいずれかを使用して展開される構成プロファイルを介して管理できます。</span><span class="sxs-lookup"><span data-stu-id="361b4-110">In enterprise organizations, Microsoft Defender for Endpoint on macOS can be managed through a configuration profile that is deployed by using one of several management tools.</span></span> <span data-ttu-id="361b4-111">セキュリティ運用チームによって管理される基本設定は、デバイス上でローカルに設定されている基本設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="361b4-111">Preferences that are managed by your security operations team take precedence over preferences that are set locally on the device.</span></span> <span data-ttu-id="361b4-112">構成プロファイルを使用して設定される基本設定を変更するには、エスカレートされた特権が必要であり、管理アクセス許可のないユーザーでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="361b4-112">Changing the preferences that are set through the configuration profile requires escalated privileges and is not available for users without administrative permissions.</span></span>

<span data-ttu-id="361b4-113">この記事では、構成プロファイルの構造、開始に使用できる推奨プロファイル、およびプロファイルの展開方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="361b4-113">This article describes the structure of the configuration profile, includes a recommended profile that you can use to get started, and provides instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="361b4-114">構成プロファイル構造</span><span class="sxs-lookup"><span data-stu-id="361b4-114">Configuration profile structure</span></span>

<span data-ttu-id="361b4-115">構成プロファイルは *.plist* ファイルで、キーによって識別されるエントリ (基本設定の名前を示す) で構成され、その後に、プリファレンスの性質に依存する値が続きます。</span><span class="sxs-lookup"><span data-stu-id="361b4-115">The configuration profile is a *.plist* file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="361b4-116">値は、単純な (数値など) か、入れ子になった基本設定リストなどの複雑な値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="361b4-116">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

>[!CAUTION]
><span data-ttu-id="361b4-117">構成プロファイルのレイアウトは、使用している管理コンソールによって異なります。</span><span class="sxs-lookup"><span data-stu-id="361b4-117">The layout of the configuration profile depends on the management console that you are using.</span></span> <span data-ttu-id="361b4-118">次のセクションでは、JAMF と Intune の構成プロファイルの例を示します。</span><span class="sxs-lookup"><span data-stu-id="361b4-118">The following sections contain examples of configuration profiles for JAMF and Intune.</span></span>

<span data-ttu-id="361b4-119">構成プロファイルのトップ レベルには、製品全体の基本設定と、Microsoft Defender for Endpoint のサブエリアのエントリが含まれています。これは、次のセクションで詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="361b4-119">The top level of the configuration profile includes product-wide preferences and entries for subareas of Microsoft Defender for Endpoint, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="361b4-120">ウイルス対策エンジンの基本設定</span><span class="sxs-lookup"><span data-stu-id="361b4-120">Antivirus engine preferences</span></span>

<span data-ttu-id="361b4-121">構成 *プロファイルの antivirusEngine* セクションは、Microsoft Defender for Endpoint のウイルス対策コンポーネントの基本設定を管理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="361b4-121">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of Microsoft Defender for Endpoint.</span></span>

|<span data-ttu-id="361b4-122">Section</span><span class="sxs-lookup"><span data-stu-id="361b4-122">Section</span></span>|<span data-ttu-id="361b4-123">値</span><span class="sxs-lookup"><span data-stu-id="361b4-123">Value</span></span>|
|:---|:---|
| <span data-ttu-id="361b4-124">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="361b4-124">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="361b4-125">**Key**</span><span class="sxs-lookup"><span data-stu-id="361b4-125">**Key**</span></span> | <span data-ttu-id="361b4-126">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="361b4-126">antivirusEngine</span></span> |
| <span data-ttu-id="361b4-127">**データ型**</span><span class="sxs-lookup"><span data-stu-id="361b4-127">**Data type**</span></span> | <span data-ttu-id="361b4-128">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="361b4-128">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="361b4-129">**コメント**</span><span class="sxs-lookup"><span data-stu-id="361b4-129">**Comments**</span></span> | <span data-ttu-id="361b4-130">辞書の内容の説明については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="361b4-130">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="361b4-131">リアルタイム保護を有効/無効にする</span><span class="sxs-lookup"><span data-stu-id="361b4-131">Enable / disable real-time protection</span></span>

<span data-ttu-id="361b4-132">アクセス時にファイルをスキャンするリアルタイム保護を有効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="361b4-132">Specify whether to enable real-time protection, which scans files as they are accessed.</span></span>

|<span data-ttu-id="361b4-133">Section</span><span class="sxs-lookup"><span data-stu-id="361b4-133">Section</span></span>|<span data-ttu-id="361b4-134">値</span><span class="sxs-lookup"><span data-stu-id="361b4-134">Value</span></span>|
|:---|:---|
| <span data-ttu-id="361b4-135">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="361b4-135">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="361b4-136">**Key**</span><span class="sxs-lookup"><span data-stu-id="361b4-136">**Key**</span></span> | <span data-ttu-id="361b4-137">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="361b4-137">enableRealTimeProtection</span></span> |
| <span data-ttu-id="361b4-138">**データ型**</span><span class="sxs-lookup"><span data-stu-id="361b4-138">**Data type**</span></span> | <span data-ttu-id="361b4-139">Boolean</span><span class="sxs-lookup"><span data-stu-id="361b4-139">Boolean</span></span> |
| <span data-ttu-id="361b4-140">**可能な値**</span><span class="sxs-lookup"><span data-stu-id="361b4-140">**Possible values**</span></span> | <span data-ttu-id="361b4-141">true (既定)</span><span class="sxs-lookup"><span data-stu-id="361b4-141">true (default)</span></span> <br/> <span data-ttu-id="361b4-142">false</span><span class="sxs-lookup"><span data-stu-id="361b4-142">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="361b4-143">パッシブ モードを有効/無効にする</span><span class="sxs-lookup"><span data-stu-id="361b4-143">Enable / disable passive mode</span></span>

<span data-ttu-id="361b4-144">ウイルス対策エンジンをパッシブ モードで実行するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="361b4-144">Specify whether the antivirus engine runs in passive mode.</span></span> <span data-ttu-id="361b4-145">パッシブ モードには、次のような影響があります。</span><span class="sxs-lookup"><span data-stu-id="361b4-145">Passive mode has the following implications:</span></span> 
- <span data-ttu-id="361b4-146">リアルタイム保護がオフになっている</span><span class="sxs-lookup"><span data-stu-id="361b4-146">Real-time protection is turned off</span></span>
- <span data-ttu-id="361b4-147">オンデマンド スキャンが有効になっている</span><span class="sxs-lookup"><span data-stu-id="361b4-147">On-demand scanning is turned on</span></span>
- <span data-ttu-id="361b4-148">脅威の自動修復が無効になっている</span><span class="sxs-lookup"><span data-stu-id="361b4-148">Automatic threat remediation is turned off</span></span>
- <span data-ttu-id="361b4-149">セキュリティ インテリジェンスの更新プログラムが有効になっている</span><span class="sxs-lookup"><span data-stu-id="361b4-149">Security intelligence updates are turned on</span></span>
- <span data-ttu-id="361b4-150">[状態] メニュー アイコンが非表示</span><span class="sxs-lookup"><span data-stu-id="361b4-150">Status menu icon is hidden</span></span>

|<span data-ttu-id="361b4-151">Section</span><span class="sxs-lookup"><span data-stu-id="361b4-151">Section</span></span>|<span data-ttu-id="361b4-152">値</span><span class="sxs-lookup"><span data-stu-id="361b4-152">Value</span></span>|
|:---|:---|
| <span data-ttu-id="361b4-153">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="361b4-153">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="361b4-154">**Key**</span><span class="sxs-lookup"><span data-stu-id="361b4-154">**Key**</span></span> | <span data-ttu-id="361b4-155">passiveMode</span><span class="sxs-lookup"><span data-stu-id="361b4-155">passiveMode</span></span> |
| <span data-ttu-id="361b4-156">**データ型**</span><span class="sxs-lookup"><span data-stu-id="361b4-156">**Data type**</span></span> | <span data-ttu-id="361b4-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="361b4-157">Boolean</span></span> |
| <span data-ttu-id="361b4-158">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="361b4-158">**Possible values**</span></span> | <span data-ttu-id="361b4-159">false (既定)</span><span class="sxs-lookup"><span data-stu-id="361b4-159">false (default)</span></span> <br/> <span data-ttu-id="361b4-160">true</span><span class="sxs-lookup"><span data-stu-id="361b4-160">true</span></span> |
| <span data-ttu-id="361b4-161">**コメント**</span><span class="sxs-lookup"><span data-stu-id="361b4-161">**Comments**</span></span> | <span data-ttu-id="361b4-162">Microsoft Defender for Endpoint version 100.67.60 以上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="361b4-162">Available in Microsoft Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="361b4-163">除外マージ ポリシー</span><span class="sxs-lookup"><span data-stu-id="361b4-163">Exclusion merge policy</span></span>

<span data-ttu-id="361b4-164">除外のマージ ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="361b4-164">Specify the merge policy for exclusions.</span></span> <span data-ttu-id="361b4-165">これには、管理者定義の除外とユーザー定義の除外 ( ) の組み合わせ、または管理者定義の除外 ( ) のみを `merge` 組み合わせて指定できます `admin_only` 。</span><span class="sxs-lookup"><span data-stu-id="361b4-165">This can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="361b4-166">この設定は、ローカル ユーザーが独自の除外を定義するのを制限するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="361b4-166">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|<span data-ttu-id="361b4-167">Section</span><span class="sxs-lookup"><span data-stu-id="361b4-167">Section</span></span>|<span data-ttu-id="361b4-168">値</span><span class="sxs-lookup"><span data-stu-id="361b4-168">Value</span></span>|
|:---|:---|
| <span data-ttu-id="361b4-169">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="361b4-169">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="361b4-170">**Key**</span><span class="sxs-lookup"><span data-stu-id="361b4-170">**Key**</span></span> | <span data-ttu-id="361b4-171">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="361b4-171">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="361b4-172">**データ型**</span><span class="sxs-lookup"><span data-stu-id="361b4-172">**Data type**</span></span> | <span data-ttu-id="361b4-173">String</span><span class="sxs-lookup"><span data-stu-id="361b4-173">String</span></span> |
| <span data-ttu-id="361b4-174">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="361b4-174">**Possible values**</span></span> | <span data-ttu-id="361b4-175">merge (既定)</span><span class="sxs-lookup"><span data-stu-id="361b4-175">merge (default)</span></span> <br/> <span data-ttu-id="361b4-176">admin_only</span><span class="sxs-lookup"><span data-stu-id="361b4-176">admin_only</span></span> |
| <span data-ttu-id="361b4-177">**コメント**</span><span class="sxs-lookup"><span data-stu-id="361b4-177">**Comments**</span></span> | <span data-ttu-id="361b4-178">Microsoft Defender for Endpoint version 100.83.73 以上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="361b4-178">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="361b4-179">スキャンの除外</span><span class="sxs-lookup"><span data-stu-id="361b4-179">Scan exclusions</span></span>

<span data-ttu-id="361b4-180">スキャン対象から除外されるエンティティを指定します。</span><span class="sxs-lookup"><span data-stu-id="361b4-180">Specify entities excluded from being scanned.</span></span> <span data-ttu-id="361b4-181">除外は、完全パス、拡張子、またはファイル名で指定できます。</span><span class="sxs-lookup"><span data-stu-id="361b4-181">Exclusions can be specified by full paths, extensions, or file names.</span></span>
<span data-ttu-id="361b4-182">(除外はアイテムの配列として指定されます。管理者は必要な数の要素を任意の順序で指定できます)。</span><span class="sxs-lookup"><span data-stu-id="361b4-182">(Exclusions are specified as an array of items, administrator can specify as many elements as necessary, in any order.)</span></span>

|<span data-ttu-id="361b4-183">Section</span><span class="sxs-lookup"><span data-stu-id="361b4-183">Section</span></span>|<span data-ttu-id="361b4-184">値</span><span class="sxs-lookup"><span data-stu-id="361b4-184">Value</span></span>|
|:---|:---|
| <span data-ttu-id="361b4-185">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="361b4-185">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="361b4-186">**Key**</span><span class="sxs-lookup"><span data-stu-id="361b4-186">**Key**</span></span> | <span data-ttu-id="361b4-187">除外</span><span class="sxs-lookup"><span data-stu-id="361b4-187">exclusions</span></span> |
| <span data-ttu-id="361b4-188">**データ型**</span><span class="sxs-lookup"><span data-stu-id="361b4-188">**Data type**</span></span> | <span data-ttu-id="361b4-189">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="361b4-189">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="361b4-190">**コメント**</span><span class="sxs-lookup"><span data-stu-id="361b4-190">**Comments**</span></span> | <span data-ttu-id="361b4-191">辞書の内容の説明については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="361b4-191">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-exclusion"></a><span data-ttu-id="361b4-192">除外の種類</span><span class="sxs-lookup"><span data-stu-id="361b4-192">Type of exclusion</span></span>

<span data-ttu-id="361b4-193">種類別にスキャン対象から除外されるコンテンツを指定します。</span><span class="sxs-lookup"><span data-stu-id="361b4-193">Specify content excluded from being scanned by type.</span></span>

|<span data-ttu-id="361b4-194">Section</span><span class="sxs-lookup"><span data-stu-id="361b4-194">Section</span></span>|<span data-ttu-id="361b4-195">値</span><span class="sxs-lookup"><span data-stu-id="361b4-195">Value</span></span>|
|:---|:---|
| <span data-ttu-id="361b4-196">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="361b4-196">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="361b4-197">**Key**</span><span class="sxs-lookup"><span data-stu-id="361b4-197">**Key**</span></span> | <span data-ttu-id="361b4-198">$type</span><span class="sxs-lookup"><span data-stu-id="361b4-198">$type</span></span> |
| <span data-ttu-id="361b4-199">**データ型**</span><span class="sxs-lookup"><span data-stu-id="361b4-199">**Data type**</span></span> | <span data-ttu-id="361b4-200">String</span><span class="sxs-lookup"><span data-stu-id="361b4-200">String</span></span> |
| <span data-ttu-id="361b4-201">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="361b4-201">**Possible values**</span></span> | <span data-ttu-id="361b4-202">excludedPath</span><span class="sxs-lookup"><span data-stu-id="361b4-202">excludedPath</span></span> <br/> <span data-ttu-id="361b4-203">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="361b4-203">excludedFileExtension</span></span> <br/> <span data-ttu-id="361b4-204">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="361b4-204">excludedFileName</span></span> |

##### <a name="path-to-excluded-content"></a><span data-ttu-id="361b4-205">除外されたコンテンツへのパス</span><span class="sxs-lookup"><span data-stu-id="361b4-205">Path to excluded content</span></span>

<span data-ttu-id="361b4-206">完全なファイル パスでスキャンされるコンテンツを除外するを指定します。</span><span class="sxs-lookup"><span data-stu-id="361b4-206">Specify content excluded from being scanned by full file path.</span></span>

|<span data-ttu-id="361b4-207">Section</span><span class="sxs-lookup"><span data-stu-id="361b4-207">Section</span></span>|<span data-ttu-id="361b4-208">値</span><span class="sxs-lookup"><span data-stu-id="361b4-208">Value</span></span>|
|:---|:---|
| <span data-ttu-id="361b4-209">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="361b4-209">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="361b4-210">**Key**</span><span class="sxs-lookup"><span data-stu-id="361b4-210">**Key**</span></span> | <span data-ttu-id="361b4-211">path</span><span class="sxs-lookup"><span data-stu-id="361b4-211">path</span></span> |
| <span data-ttu-id="361b4-212">**データ型**</span><span class="sxs-lookup"><span data-stu-id="361b4-212">**Data type**</span></span> | <span data-ttu-id="361b4-213">String</span><span class="sxs-lookup"><span data-stu-id="361b4-213">String</span></span> |
| <span data-ttu-id="361b4-214">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="361b4-214">**Possible values**</span></span> | <span data-ttu-id="361b4-215">有効なパス</span><span class="sxs-lookup"><span data-stu-id="361b4-215">valid paths</span></span> |
| <span data-ttu-id="361b4-216">**コメント**</span><span class="sxs-lookup"><span data-stu-id="361b4-216">**Comments**</span></span> | <span data-ttu-id="361b4-217">適用 *できるのは、$type\*\*が excludedPath である場合のみです。*</span><span class="sxs-lookup"><span data-stu-id="361b4-217">Applicable only if *$type* is *excludedPath*</span></span> |

## <a name="supported-exclusion-types"></a><span data-ttu-id="361b4-218">サポートされる除外の種類</span><span class="sxs-lookup"><span data-stu-id="361b4-218">Supported exclusion types</span></span>

<span data-ttu-id="361b4-219">次の表に、Defender for Endpoint on Mac でサポートされている除外の種類を示します。</span><span class="sxs-lookup"><span data-stu-id="361b4-219">The follow table shows the exclusion types supported by Defender for Endpoint on Mac.</span></span>

<span data-ttu-id="361b4-220">除外</span><span class="sxs-lookup"><span data-stu-id="361b4-220">Exclusion</span></span> | <span data-ttu-id="361b4-221">定義</span><span class="sxs-lookup"><span data-stu-id="361b4-221">Definition</span></span> | <span data-ttu-id="361b4-222">例</span><span class="sxs-lookup"><span data-stu-id="361b4-222">Examples</span></span>
---|---|---
<span data-ttu-id="361b4-223">ファイル拡張子</span><span class="sxs-lookup"><span data-stu-id="361b4-223">File extension</span></span> | <span data-ttu-id="361b4-224">拡張子が付いたすべてのファイル(デバイス上の任意の場所)</span><span class="sxs-lookup"><span data-stu-id="361b4-224">All files with the extension, anywhere on the device</span></span> | `.test`
<span data-ttu-id="361b4-225">File</span><span class="sxs-lookup"><span data-stu-id="361b4-225">File</span></span> | <span data-ttu-id="361b4-226">完全パスで識別される特定のファイル</span><span class="sxs-lookup"><span data-stu-id="361b4-226">A specific file identified by the full path</span></span> | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
<span data-ttu-id="361b4-227">Folder</span><span class="sxs-lookup"><span data-stu-id="361b4-227">Folder</span></span> | <span data-ttu-id="361b4-228">指定したフォルダーの下のすべてのファイル (再帰的)</span><span class="sxs-lookup"><span data-stu-id="361b4-228">All files under the specified folder (recursively)</span></span> | `/var/log/`<br/>`/var/*/`
<span data-ttu-id="361b4-229">プロセス</span><span class="sxs-lookup"><span data-stu-id="361b4-229">Process</span></span> | <span data-ttu-id="361b4-230">特定のプロセス (完全なパスまたはファイル名で指定) と、そのプロセスで開くすべてのファイル</span><span class="sxs-lookup"><span data-stu-id="361b4-230">A specific process (specified either by the full path or file name) and all files opened by it</span></span> | `/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> <span data-ttu-id="361b4-231">正常に除外するには、上記のパスは、シンボリック リンクではなくハード リンクである必要があります。</span><span class="sxs-lookup"><span data-stu-id="361b4-231">The paths above must be hard links, not symbolic links, in order to be successfully excluded.</span></span> <span data-ttu-id="361b4-232">パスがシンボリック リンクである場合は、実行して確認できます `file <path-name>` 。</span><span class="sxs-lookup"><span data-stu-id="361b4-232">You can check if a path is a symbolic link by running `file <path-name>`.</span></span>

<span data-ttu-id="361b4-233">ファイル、フォルダー、およびプロセスの除外は、次のワイルドカードをサポートします。</span><span class="sxs-lookup"><span data-stu-id="361b4-233">File, folder, and process exclusions support the following wildcards:</span></span>

<span data-ttu-id="361b4-234">ワイルドカード</span><span class="sxs-lookup"><span data-stu-id="361b4-234">Wildcard</span></span> | <span data-ttu-id="361b4-235">説明</span><span class="sxs-lookup"><span data-stu-id="361b4-235">Description</span></span> | <span data-ttu-id="361b4-236">例</span><span class="sxs-lookup"><span data-stu-id="361b4-236">Example</span></span> | <span data-ttu-id="361b4-237">一致</span><span class="sxs-lookup"><span data-stu-id="361b4-237">Matches</span></span> | <span data-ttu-id="361b4-238">一致しない</span><span class="sxs-lookup"><span data-stu-id="361b4-238">Does not match</span></span>
---|---|---|---|---
\* |    <span data-ttu-id="361b4-239">none を含む任意の数の文字と一致します (パス内でこのワイルドカードを使用すると、1 つのフォルダーのみを置き換える点に注意してください)</span><span class="sxs-lookup"><span data-stu-id="361b4-239">Matches any number of any characters including none (note that when this wildcard is used inside a path it will substitute only one folder)</span></span> | `/var/\*/\*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
<span data-ttu-id="361b4-240">?</span><span class="sxs-lookup"><span data-stu-id="361b4-240">?</span></span> | <span data-ttu-id="361b4-241">任意の 1 文字に一致する</span><span class="sxs-lookup"><span data-stu-id="361b4-241">Matches any single character</span></span> | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

##### <a name="path-type-file--directory"></a><span data-ttu-id="361b4-242">パスの種類 (ファイル/ディレクトリ)</span><span class="sxs-lookup"><span data-stu-id="361b4-242">Path type (file / directory)</span></span>

<span data-ttu-id="361b4-243">path プロパティが *ファイル* またはディレクトリを参照しているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="361b4-243">Indicate if the *path* property refers to a file or directory.</span></span> 

|<span data-ttu-id="361b4-244">Section</span><span class="sxs-lookup"><span data-stu-id="361b4-244">Section</span></span>|<span data-ttu-id="361b4-245">値</span><span class="sxs-lookup"><span data-stu-id="361b4-245">Value</span></span>|
|:---|:---|
| <span data-ttu-id="361b4-246">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="361b4-246">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="361b4-247">**Key**</span><span class="sxs-lookup"><span data-stu-id="361b4-247">**Key**</span></span> | <span data-ttu-id="361b4-248">isDirectory</span><span class="sxs-lookup"><span data-stu-id="361b4-248">isDirectory</span></span> |
| <span data-ttu-id="361b4-249">**データ型**</span><span class="sxs-lookup"><span data-stu-id="361b4-249">**Data type**</span></span> | <span data-ttu-id="361b4-250">Boolean</span><span class="sxs-lookup"><span data-stu-id="361b4-250">Boolean</span></span> |
| <span data-ttu-id="361b4-251">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="361b4-251">**Possible values**</span></span> | <span data-ttu-id="361b4-252">false (既定)</span><span class="sxs-lookup"><span data-stu-id="361b4-252">false (default)</span></span> <br/> <span data-ttu-id="361b4-253">true</span><span class="sxs-lookup"><span data-stu-id="361b4-253">true</span></span> |
| <span data-ttu-id="361b4-254">**コメント**</span><span class="sxs-lookup"><span data-stu-id="361b4-254">**Comments**</span></span> | <span data-ttu-id="361b4-255">適用 *できるのは、$type\*\*が excludedPath である場合のみです。*</span><span class="sxs-lookup"><span data-stu-id="361b4-255">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="361b4-256">スキャンから除外されたファイル拡張子</span><span class="sxs-lookup"><span data-stu-id="361b4-256">File extension excluded from the scan</span></span>

<span data-ttu-id="361b4-257">ファイル拡張子によるスキャン対象から除外されるコンテンツを指定します。</span><span class="sxs-lookup"><span data-stu-id="361b4-257">Specify content excluded from being scanned by file extension.</span></span>

|<span data-ttu-id="361b4-258">Section</span><span class="sxs-lookup"><span data-stu-id="361b4-258">Section</span></span>|<span data-ttu-id="361b4-259">値</span><span class="sxs-lookup"><span data-stu-id="361b4-259">Value</span></span>|
|:---|:---|
| <span data-ttu-id="361b4-260">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="361b4-260">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="361b4-261">**Key**</span><span class="sxs-lookup"><span data-stu-id="361b4-261">**Key**</span></span> | <span data-ttu-id="361b4-262">拡張機能</span><span class="sxs-lookup"><span data-stu-id="361b4-262">extension</span></span> |
| <span data-ttu-id="361b4-263">**データ型**</span><span class="sxs-lookup"><span data-stu-id="361b4-263">**Data type**</span></span> | <span data-ttu-id="361b4-264">String</span><span class="sxs-lookup"><span data-stu-id="361b4-264">String</span></span> |
| <span data-ttu-id="361b4-265">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="361b4-265">**Possible values**</span></span> | <span data-ttu-id="361b4-266">有効なファイル拡張子</span><span class="sxs-lookup"><span data-stu-id="361b4-266">valid file extensions</span></span> |
| <span data-ttu-id="361b4-267">**コメント**</span><span class="sxs-lookup"><span data-stu-id="361b4-267">**Comments**</span></span> | <span data-ttu-id="361b4-268">適用 *できるのは* 、$type FileExtension が *除外されている場合のみです。*</span><span class="sxs-lookup"><span data-stu-id="361b4-268">Applicable only if *$type* is *excludedFileExtension*</span></span> |

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="361b4-269">スキャンから除外されるプロセス</span><span class="sxs-lookup"><span data-stu-id="361b4-269">Process excluded from the scan</span></span>

<span data-ttu-id="361b4-270">すべてのファイル アクティビティがスキャンから除外されるプロセスを指定します。</span><span class="sxs-lookup"><span data-stu-id="361b4-270">Specify a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="361b4-271">プロセスは、名前 (例: ) または完全 `cat` パス (例: ) で指定できます `/bin/cat` 。</span><span class="sxs-lookup"><span data-stu-id="361b4-271">The process can be specified either by its name (e.g. `cat`) or full path (e.g. `/bin/cat`).</span></span>

|<span data-ttu-id="361b4-272">Section</span><span class="sxs-lookup"><span data-stu-id="361b4-272">Section</span></span>|<span data-ttu-id="361b4-273">値</span><span class="sxs-lookup"><span data-stu-id="361b4-273">Value</span></span>|
|:---|:---|
| <span data-ttu-id="361b4-274">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="361b4-274">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="361b4-275">**Key**</span><span class="sxs-lookup"><span data-stu-id="361b4-275">**Key**</span></span> | <span data-ttu-id="361b4-276">name</span><span class="sxs-lookup"><span data-stu-id="361b4-276">name</span></span> |
| <span data-ttu-id="361b4-277">**データ型**</span><span class="sxs-lookup"><span data-stu-id="361b4-277">**Data type**</span></span> | <span data-ttu-id="361b4-278">String</span><span class="sxs-lookup"><span data-stu-id="361b4-278">String</span></span> |
| <span data-ttu-id="361b4-279">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="361b4-279">**Possible values**</span></span> | <span data-ttu-id="361b4-280">任意の文字列</span><span class="sxs-lookup"><span data-stu-id="361b4-280">any string</span></span> |
| <span data-ttu-id="361b4-281">**コメント**</span><span class="sxs-lookup"><span data-stu-id="361b4-281">**Comments**</span></span> | <span data-ttu-id="361b4-282">ファイルが excludedFileName *$type\*\*場合にのみ適用されます。*</span><span class="sxs-lookup"><span data-stu-id="361b4-282">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="361b4-283">許可される脅威</span><span class="sxs-lookup"><span data-stu-id="361b4-283">Allowed threats</span></span>

<span data-ttu-id="361b4-284">Defender for Endpoint on Mac でブロックされない脅威を名前で指定します。</span><span class="sxs-lookup"><span data-stu-id="361b4-284">Specify threats by name that are not blocked by Defender for Endpoint on Mac.</span></span> <span data-ttu-id="361b4-285">これらの脅威の実行が許可されます。</span><span class="sxs-lookup"><span data-stu-id="361b4-285">These threats will be allowed to run.</span></span>

|<span data-ttu-id="361b4-286">Section</span><span class="sxs-lookup"><span data-stu-id="361b4-286">Section</span></span>|<span data-ttu-id="361b4-287">値</span><span class="sxs-lookup"><span data-stu-id="361b4-287">Value</span></span>|
|:---|:---|
| <span data-ttu-id="361b4-288">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="361b4-288">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="361b4-289">**Key**</span><span class="sxs-lookup"><span data-stu-id="361b4-289">**Key**</span></span> | <span data-ttu-id="361b4-290">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="361b4-290">allowedThreats</span></span> |
| <span data-ttu-id="361b4-291">**データ型**</span><span class="sxs-lookup"><span data-stu-id="361b4-291">**Data type**</span></span> | <span data-ttu-id="361b4-292">文字列の配列</span><span class="sxs-lookup"><span data-stu-id="361b4-292">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="361b4-293">禁止された脅威アクション</span><span class="sxs-lookup"><span data-stu-id="361b4-293">Disallowed threat actions</span></span>

<span data-ttu-id="361b4-294">脅威が検出された場合にデバイスのローカル ユーザーが実行できるアクションを制限します。</span><span class="sxs-lookup"><span data-stu-id="361b4-294">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="361b4-295">この一覧に含まれるアクションは、ユーザー インターフェイスには表示されません。</span><span class="sxs-lookup"><span data-stu-id="361b4-295">The actions included in this list are not displayed in the user interface.</span></span>

|<span data-ttu-id="361b4-296">Section</span><span class="sxs-lookup"><span data-stu-id="361b4-296">Section</span></span>|<span data-ttu-id="361b4-297">値</span><span class="sxs-lookup"><span data-stu-id="361b4-297">Value</span></span>|
|:---|:---|
| <span data-ttu-id="361b4-298">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="361b4-298">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="361b4-299">**Key**</span><span class="sxs-lookup"><span data-stu-id="361b4-299">**Key**</span></span> | <span data-ttu-id="361b4-300">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="361b4-300">disallowedThreatActions</span></span> |
| <span data-ttu-id="361b4-301">**データ型**</span><span class="sxs-lookup"><span data-stu-id="361b4-301">**Data type**</span></span> | <span data-ttu-id="361b4-302">文字列の配列</span><span class="sxs-lookup"><span data-stu-id="361b4-302">Array of strings</span></span> |
| <span data-ttu-id="361b4-303">**可能な値**</span><span class="sxs-lookup"><span data-stu-id="361b4-303">**Possible values**</span></span> | <span data-ttu-id="361b4-304">allow (ユーザーによる脅威の許可を制限する)</span><span class="sxs-lookup"><span data-stu-id="361b4-304">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="361b4-305">復元 (検疫からの脅威の復元をユーザーに制限する)</span><span class="sxs-lookup"><span data-stu-id="361b4-305">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="361b4-306">**コメント**</span><span class="sxs-lookup"><span data-stu-id="361b4-306">**Comments**</span></span> | <span data-ttu-id="361b4-307">Microsoft Defender for Endpoint version 100.83.73 以上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="361b4-307">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="361b4-308">脅威の種類の設定</span><span class="sxs-lookup"><span data-stu-id="361b4-308">Threat type settings</span></span>

<span data-ttu-id="361b4-309">特定の脅威の種類を macOS 上の Microsoft Defender for Endpoint で処理する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="361b4-309">Specify how certain threat types are handled by Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="361b4-310">Section</span><span class="sxs-lookup"><span data-stu-id="361b4-310">Section</span></span>|<span data-ttu-id="361b4-311">値</span><span class="sxs-lookup"><span data-stu-id="361b4-311">Value</span></span>|
|:---|:---|
| <span data-ttu-id="361b4-312">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="361b4-312">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="361b4-313">**Key**</span><span class="sxs-lookup"><span data-stu-id="361b4-313">**Key**</span></span> | <span data-ttu-id="361b4-314">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="361b4-314">threatTypeSettings</span></span> |
| <span data-ttu-id="361b4-315">**データ型**</span><span class="sxs-lookup"><span data-stu-id="361b4-315">**Data type**</span></span> | <span data-ttu-id="361b4-316">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="361b4-316">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="361b4-317">**コメント**</span><span class="sxs-lookup"><span data-stu-id="361b4-317">**Comments**</span></span> | <span data-ttu-id="361b4-318">辞書の内容の説明については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="361b4-318">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="threat-type"></a><span data-ttu-id="361b4-319">脅威の種類</span><span class="sxs-lookup"><span data-stu-id="361b4-319">Threat type</span></span>

<span data-ttu-id="361b4-320">脅威の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="361b4-320">Specify threat types.</span></span>

|<span data-ttu-id="361b4-321">Section</span><span class="sxs-lookup"><span data-stu-id="361b4-321">Section</span></span>|<span data-ttu-id="361b4-322">値</span><span class="sxs-lookup"><span data-stu-id="361b4-322">Value</span></span>|
|:---|:---|
| <span data-ttu-id="361b4-323">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="361b4-323">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="361b4-324">**Key**</span><span class="sxs-lookup"><span data-stu-id="361b4-324">**Key**</span></span> | <span data-ttu-id="361b4-325">キー</span><span class="sxs-lookup"><span data-stu-id="361b4-325">key</span></span> |
| <span data-ttu-id="361b4-326">**データ型**</span><span class="sxs-lookup"><span data-stu-id="361b4-326">**Data type**</span></span> | <span data-ttu-id="361b4-327">String</span><span class="sxs-lookup"><span data-stu-id="361b4-327">String</span></span> |
| <span data-ttu-id="361b4-328">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="361b4-328">**Possible values**</span></span> | <span data-ttu-id="361b4-329">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="361b4-329">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="361b4-330">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="361b4-330">archive_bomb</span></span> |

##### <a name="action-to-take"></a><span data-ttu-id="361b4-331">実行する操作</span><span class="sxs-lookup"><span data-stu-id="361b4-331">Action to take</span></span>

<span data-ttu-id="361b4-332">前のセクションで指定した種類の脅威が検出された場合に実行するアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="361b4-332">Specify what action to take when a threat of the type specified in the preceding section is detected.</span></span> <span data-ttu-id="361b4-333">次のオプションから選択します。</span><span class="sxs-lookup"><span data-stu-id="361b4-333">Choose from the following options:</span></span>

- <span data-ttu-id="361b4-334">**監査**: デバイスは、この種類の脅威から保護されませんが、脅威に関するエントリがログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="361b4-334">**Audit**: your device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="361b4-335">**ブロック**: デバイスは、この種類の脅威から保護され、ユーザー インターフェイスとセキュリティ コンソールで通知されます。</span><span class="sxs-lookup"><span data-stu-id="361b4-335">**Block**: your device is protected against this type of threat and you are notified in the user interface and the security console.</span></span>
- <span data-ttu-id="361b4-336">**オフ**: デバイスは、この種類の脅威から保護され、何もログに記録されません。</span><span class="sxs-lookup"><span data-stu-id="361b4-336">**Off**: your device is not protected against this type of threat and nothing is logged.</span></span>

|<span data-ttu-id="361b4-337">Section</span><span class="sxs-lookup"><span data-stu-id="361b4-337">Section</span></span>|<span data-ttu-id="361b4-338">値</span><span class="sxs-lookup"><span data-stu-id="361b4-338">Value</span></span>|
|:---|:---|
| <span data-ttu-id="361b4-339">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="361b4-339">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="361b4-340">**Key**</span><span class="sxs-lookup"><span data-stu-id="361b4-340">**Key**</span></span> | <span data-ttu-id="361b4-341">値</span><span class="sxs-lookup"><span data-stu-id="361b4-341">value</span></span> |
| <span data-ttu-id="361b4-342">**データ型**</span><span class="sxs-lookup"><span data-stu-id="361b4-342">**Data type**</span></span> | <span data-ttu-id="361b4-343">String</span><span class="sxs-lookup"><span data-stu-id="361b4-343">String</span></span> |
| <span data-ttu-id="361b4-344">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="361b4-344">**Possible values**</span></span> | <span data-ttu-id="361b4-345">監査 (既定)</span><span class="sxs-lookup"><span data-stu-id="361b4-345">audit (default)</span></span> <br/> <span data-ttu-id="361b4-346">block</span><span class="sxs-lookup"><span data-stu-id="361b4-346">block</span></span> <br/> <span data-ttu-id="361b4-347">off</span><span class="sxs-lookup"><span data-stu-id="361b4-347">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="361b4-348">脅威の種類の設定の差し込みポリシー</span><span class="sxs-lookup"><span data-stu-id="361b4-348">Threat type settings merge policy</span></span>

<span data-ttu-id="361b4-349">脅威の種類の設定のマージ ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="361b4-349">Specify the merge policy for threat type settings.</span></span> <span data-ttu-id="361b4-350">これは、管理者定義設定とユーザー定義設定 ( ) の組み合わせか、管理者定義の設定 ( ) のみを `merge` 組み合わせて使用できます `admin_only` 。</span><span class="sxs-lookup"><span data-stu-id="361b4-350">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="361b4-351">この設定を使用すると、ローカル ユーザーがさまざまな脅威の種類に対して独自の設定を定義するのを制限できます。</span><span class="sxs-lookup"><span data-stu-id="361b4-351">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|<span data-ttu-id="361b4-352">Section</span><span class="sxs-lookup"><span data-stu-id="361b4-352">Section</span></span>|<span data-ttu-id="361b4-353">値</span><span class="sxs-lookup"><span data-stu-id="361b4-353">Value</span></span>|
|:---|:---|
| <span data-ttu-id="361b4-354">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="361b4-354">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="361b4-355">**Key**</span><span class="sxs-lookup"><span data-stu-id="361b4-355">**Key**</span></span> | <span data-ttu-id="361b4-356">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="361b4-356">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="361b4-357">**データ型**</span><span class="sxs-lookup"><span data-stu-id="361b4-357">**Data type**</span></span> | <span data-ttu-id="361b4-358">String</span><span class="sxs-lookup"><span data-stu-id="361b4-358">String</span></span> |
| <span data-ttu-id="361b4-359">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="361b4-359">**Possible values**</span></span> | <span data-ttu-id="361b4-360">merge (既定)</span><span class="sxs-lookup"><span data-stu-id="361b4-360">merge (default)</span></span> <br/> <span data-ttu-id="361b4-361">admin_only</span><span class="sxs-lookup"><span data-stu-id="361b4-361">admin_only</span></span> |
| <span data-ttu-id="361b4-362">**コメント**</span><span class="sxs-lookup"><span data-stu-id="361b4-362">**Comments**</span></span> | <span data-ttu-id="361b4-363">Microsoft Defender for Endpoint version 100.83.73 以上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="361b4-363">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="361b4-364">ウイルス対策スキャン履歴の保持 (日数)</span><span class="sxs-lookup"><span data-stu-id="361b4-364">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="361b4-365">デバイスのスキャン履歴に結果が保持される日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="361b4-365">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="361b4-366">古いスキャン結果は履歴から削除されます。</span><span class="sxs-lookup"><span data-stu-id="361b4-366">Old scan results are removed from the history.</span></span> <span data-ttu-id="361b4-367">ディスクから削除された古い検疫済みファイル。</span><span class="sxs-lookup"><span data-stu-id="361b4-367">Old quarantined files that are also removed from the disk.</span></span>

|<span data-ttu-id="361b4-368">Section</span><span class="sxs-lookup"><span data-stu-id="361b4-368">Section</span></span>|<span data-ttu-id="361b4-369">値</span><span class="sxs-lookup"><span data-stu-id="361b4-369">Value</span></span>|
|:---|:---|
| <span data-ttu-id="361b4-370">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="361b4-370">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="361b4-371">**Key**</span><span class="sxs-lookup"><span data-stu-id="361b4-371">**Key**</span></span> | <span data-ttu-id="361b4-372">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="361b4-372">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="361b4-373">**データ型**</span><span class="sxs-lookup"><span data-stu-id="361b4-373">**Data type**</span></span> | <span data-ttu-id="361b4-374">String</span><span class="sxs-lookup"><span data-stu-id="361b4-374">String</span></span> |
| <span data-ttu-id="361b4-375">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="361b4-375">**Possible values**</span></span> | <span data-ttu-id="361b4-376">90 (既定)。</span><span class="sxs-lookup"><span data-stu-id="361b4-376">90 (default).</span></span> <span data-ttu-id="361b4-377">使用できる値は、1 日から 180 日です。</span><span class="sxs-lookup"><span data-stu-id="361b4-377">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="361b4-378">**コメント**</span><span class="sxs-lookup"><span data-stu-id="361b4-378">**Comments**</span></span> | <span data-ttu-id="361b4-379">エンドポイント バージョン 101.07.23 以上の Microsoft Defender で使用できます。</span><span class="sxs-lookup"><span data-stu-id="361b4-379">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="361b4-380">ウイルス対策スキャン履歴内のアイテムの最大数</span><span class="sxs-lookup"><span data-stu-id="361b4-380">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="361b4-381">スキャン履歴に保持するエントリの最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="361b4-381">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="361b4-382">エントリには、過去に実行されたオンデマンド スキャンとすべてのウイルス対策検出が含まれます。</span><span class="sxs-lookup"><span data-stu-id="361b4-382">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|<span data-ttu-id="361b4-383">Section</span><span class="sxs-lookup"><span data-stu-id="361b4-383">Section</span></span>|<span data-ttu-id="361b4-384">値</span><span class="sxs-lookup"><span data-stu-id="361b4-384">Value</span></span>|
|:---|:---|
| <span data-ttu-id="361b4-385">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="361b4-385">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="361b4-386">**Key**</span><span class="sxs-lookup"><span data-stu-id="361b4-386">**Key**</span></span> | <span data-ttu-id="361b4-387">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="361b4-387">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="361b4-388">**データ型**</span><span class="sxs-lookup"><span data-stu-id="361b4-388">**Data type**</span></span> | <span data-ttu-id="361b4-389">String</span><span class="sxs-lookup"><span data-stu-id="361b4-389">String</span></span> |
| <span data-ttu-id="361b4-390">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="361b4-390">**Possible values**</span></span> | <span data-ttu-id="361b4-391">10000 (既定値)。</span><span class="sxs-lookup"><span data-stu-id="361b4-391">10000 (default).</span></span> <span data-ttu-id="361b4-392">許可される値は、5000 アイテムから 15,000 アイテムまでです。</span><span class="sxs-lookup"><span data-stu-id="361b4-392">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="361b4-393">**コメント**</span><span class="sxs-lookup"><span data-stu-id="361b4-393">**Comments**</span></span> | <span data-ttu-id="361b4-394">エンドポイント バージョン 101.07.23 以上の Microsoft Defender で使用できます。</span><span class="sxs-lookup"><span data-stu-id="361b4-394">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="361b4-395">クラウドによる保護の基本設定</span><span class="sxs-lookup"><span data-stu-id="361b4-395">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="361b4-396">macOS 上の Microsoft Defender for Endpoint のクラウド駆動型保護機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="361b4-396">Configure the cloud-driven protection features of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="361b4-397">Section</span><span class="sxs-lookup"><span data-stu-id="361b4-397">Section</span></span>|<span data-ttu-id="361b4-398">値</span><span class="sxs-lookup"><span data-stu-id="361b4-398">Value</span></span>|
|:---|:---|
| <span data-ttu-id="361b4-399">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="361b4-399">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="361b4-400">**Key**</span><span class="sxs-lookup"><span data-stu-id="361b4-400">**Key**</span></span> | <span data-ttu-id="361b4-401">cloudService</span><span class="sxs-lookup"><span data-stu-id="361b4-401">cloudService</span></span> |
| <span data-ttu-id="361b4-402">**データ型**</span><span class="sxs-lookup"><span data-stu-id="361b4-402">**Data type**</span></span> | <span data-ttu-id="361b4-403">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="361b4-403">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="361b4-404">**コメント**</span><span class="sxs-lookup"><span data-stu-id="361b4-404">**Comments**</span></span> | <span data-ttu-id="361b4-405">辞書の内容の説明については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="361b4-405">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="361b4-406">クラウド配信の保護を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="361b4-406">Enable / disable cloud-delivered protection</span></span>

<span data-ttu-id="361b4-407">デバイスのクラウド配信保護を有効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="361b4-407">Specify whether to enable cloud-delivered protection the device or not.</span></span> <span data-ttu-id="361b4-408">サービスのセキュリティを向上させるために、この機能を有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="361b4-408">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|<span data-ttu-id="361b4-409">Section</span><span class="sxs-lookup"><span data-stu-id="361b4-409">Section</span></span>|<span data-ttu-id="361b4-410">値</span><span class="sxs-lookup"><span data-stu-id="361b4-410">Value</span></span>|
|:---|:---|
| <span data-ttu-id="361b4-411">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="361b4-411">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="361b4-412">**Key**</span><span class="sxs-lookup"><span data-stu-id="361b4-412">**Key**</span></span> | <span data-ttu-id="361b4-413">enabled</span><span class="sxs-lookup"><span data-stu-id="361b4-413">enabled</span></span> |
| <span data-ttu-id="361b4-414">**データ型**</span><span class="sxs-lookup"><span data-stu-id="361b4-414">**Data type**</span></span> | <span data-ttu-id="361b4-415">Boolean</span><span class="sxs-lookup"><span data-stu-id="361b4-415">Boolean</span></span> |
| <span data-ttu-id="361b4-416">**可能な値**</span><span class="sxs-lookup"><span data-stu-id="361b4-416">**Possible values**</span></span> | <span data-ttu-id="361b4-417">true (既定)</span><span class="sxs-lookup"><span data-stu-id="361b4-417">true (default)</span></span> <br/> <span data-ttu-id="361b4-418">false</span><span class="sxs-lookup"><span data-stu-id="361b4-418">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="361b4-419">診断コレクション レベル</span><span class="sxs-lookup"><span data-stu-id="361b4-419">Diagnostic collection level</span></span>

<span data-ttu-id="361b4-420">診断データは、Microsoft Defender for Endpoint を安全かつ最新の状態に保ち、問題を検出、診断、修正し、製品の改善を行う場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="361b4-420">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="361b4-421">この設定は、Microsoft Defender for Endpoint から Microsoft に送信される診断のレベルを決定します。</span><span class="sxs-lookup"><span data-stu-id="361b4-421">This setting determines the level of diagnostics sent by Microsoft Defender for Endpoint to Microsoft.</span></span>

|<span data-ttu-id="361b4-422">Section</span><span class="sxs-lookup"><span data-stu-id="361b4-422">Section</span></span>|<span data-ttu-id="361b4-423">値</span><span class="sxs-lookup"><span data-stu-id="361b4-423">Value</span></span>|
|:---|:---|
| <span data-ttu-id="361b4-424">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="361b4-424">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="361b4-425">**Key**</span><span class="sxs-lookup"><span data-stu-id="361b4-425">**Key**</span></span> | <span data-ttu-id="361b4-426">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="361b4-426">diagnosticLevel</span></span> |
| <span data-ttu-id="361b4-427">**データ型**</span><span class="sxs-lookup"><span data-stu-id="361b4-427">**Data type**</span></span> | <span data-ttu-id="361b4-428">String</span><span class="sxs-lookup"><span data-stu-id="361b4-428">String</span></span> |
| <span data-ttu-id="361b4-429">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="361b4-429">**Possible values**</span></span> | <span data-ttu-id="361b4-430">省略可能 (既定)</span><span class="sxs-lookup"><span data-stu-id="361b4-430">optional (default)</span></span> <br/> <span data-ttu-id="361b4-431">必須</span><span class="sxs-lookup"><span data-stu-id="361b4-431">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="361b4-432">自動サンプル申請を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="361b4-432">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="361b4-433">疑わしいサンプル (脅威を含む可能性が高い) を Microsoft に送信するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="361b4-433">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="361b4-434">送信されたファイルに個人情報が含まれている可能性が高い場合は、メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="361b4-434">You are prompted if the submitted file is likely to contain personal information.</span></span>

|<span data-ttu-id="361b4-435">Section</span><span class="sxs-lookup"><span data-stu-id="361b4-435">Section</span></span>|<span data-ttu-id="361b4-436">値</span><span class="sxs-lookup"><span data-stu-id="361b4-436">Value</span></span>|
|:---|:---|
| <span data-ttu-id="361b4-437">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="361b4-437">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="361b4-438">**Key**</span><span class="sxs-lookup"><span data-stu-id="361b4-438">**Key**</span></span> | <span data-ttu-id="361b4-439">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="361b4-439">automaticSampleSubmission</span></span> |
| <span data-ttu-id="361b4-440">**データ型**</span><span class="sxs-lookup"><span data-stu-id="361b4-440">**Data type**</span></span> | <span data-ttu-id="361b4-441">Boolean</span><span class="sxs-lookup"><span data-stu-id="361b4-441">Boolean</span></span> |
| <span data-ttu-id="361b4-442">**可能な値**</span><span class="sxs-lookup"><span data-stu-id="361b4-442">**Possible values**</span></span> | <span data-ttu-id="361b4-443">true (既定)</span><span class="sxs-lookup"><span data-stu-id="361b4-443">true (default)</span></span> <br/> <span data-ttu-id="361b4-444">false</span><span class="sxs-lookup"><span data-stu-id="361b4-444">false</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="361b4-445">セキュリティ インテリジェンスの自動更新を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="361b4-445">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="361b4-446">セキュリティ インテリジェンスの更新プログラムが自動的にインストールされるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="361b4-446">Determines whether security intelligence updates are installed automatically:</span></span>

|<span data-ttu-id="361b4-447">Section</span><span class="sxs-lookup"><span data-stu-id="361b4-447">Section</span></span>|<span data-ttu-id="361b4-448">値</span><span class="sxs-lookup"><span data-stu-id="361b4-448">Value</span></span>|
|:---|:---|
| <span data-ttu-id="361b4-449">**Key**</span><span class="sxs-lookup"><span data-stu-id="361b4-449">**Key**</span></span> | <span data-ttu-id="361b4-450">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="361b4-450">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="361b4-451">**データ型**</span><span class="sxs-lookup"><span data-stu-id="361b4-451">**Data type**</span></span> | <span data-ttu-id="361b4-452">Boolean</span><span class="sxs-lookup"><span data-stu-id="361b4-452">Boolean</span></span> |
| <span data-ttu-id="361b4-453">**可能な値**</span><span class="sxs-lookup"><span data-stu-id="361b4-453">**Possible values**</span></span> | <span data-ttu-id="361b4-454">true (既定)</span><span class="sxs-lookup"><span data-stu-id="361b4-454">true (default)</span></span> <br/> <span data-ttu-id="361b4-455">false</span><span class="sxs-lookup"><span data-stu-id="361b4-455">false</span></span> |

### <a name="user-interface-preferences"></a><span data-ttu-id="361b4-456">ユーザー インターフェイスの基本設定</span><span class="sxs-lookup"><span data-stu-id="361b4-456">User interface preferences</span></span>

<span data-ttu-id="361b4-457">macOS 上の Microsoft Defender for Endpoint のユーザー インターフェイスの基本設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="361b4-457">Manage the preferences for the user interface of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="361b4-458">Section</span><span class="sxs-lookup"><span data-stu-id="361b4-458">Section</span></span>|<span data-ttu-id="361b4-459">値</span><span class="sxs-lookup"><span data-stu-id="361b4-459">Value</span></span>|
|:---|:---|
| <span data-ttu-id="361b4-460">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="361b4-460">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="361b4-461">**Key**</span><span class="sxs-lookup"><span data-stu-id="361b4-461">**Key**</span></span> | <span data-ttu-id="361b4-462">userInterface</span><span class="sxs-lookup"><span data-stu-id="361b4-462">userInterface</span></span> |
| <span data-ttu-id="361b4-463">**データ型**</span><span class="sxs-lookup"><span data-stu-id="361b4-463">**Data type**</span></span> | <span data-ttu-id="361b4-464">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="361b4-464">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="361b4-465">**コメント**</span><span class="sxs-lookup"><span data-stu-id="361b4-465">**Comments**</span></span> | <span data-ttu-id="361b4-466">辞書の内容の説明については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="361b4-466">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="show--hide-status-menu-icon"></a><span data-ttu-id="361b4-467">状態メニューアイコンの表示/非表示</span><span class="sxs-lookup"><span data-stu-id="361b4-467">Show / hide status menu icon</span></span>

<span data-ttu-id="361b4-468">画面の右上隅にある状態メニュー アイコンを表示または非表示にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="361b4-468">Specify whether to show or hide the status menu icon in the top-right corner of the screen.</span></span>

|<span data-ttu-id="361b4-469">Section</span><span class="sxs-lookup"><span data-stu-id="361b4-469">Section</span></span>|<span data-ttu-id="361b4-470">値</span><span class="sxs-lookup"><span data-stu-id="361b4-470">Value</span></span>|
|:---|:---|
| <span data-ttu-id="361b4-471">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="361b4-471">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="361b4-472">**Key**</span><span class="sxs-lookup"><span data-stu-id="361b4-472">**Key**</span></span> | <span data-ttu-id="361b4-473">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="361b4-473">hideStatusMenuIcon</span></span> |
| <span data-ttu-id="361b4-474">**データ型**</span><span class="sxs-lookup"><span data-stu-id="361b4-474">**Data type**</span></span> | <span data-ttu-id="361b4-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="361b4-475">Boolean</span></span> |
| <span data-ttu-id="361b4-476">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="361b4-476">**Possible values**</span></span> | <span data-ttu-id="361b4-477">false (既定)</span><span class="sxs-lookup"><span data-stu-id="361b4-477">false (default)</span></span> <br/> <span data-ttu-id="361b4-478">true</span><span class="sxs-lookup"><span data-stu-id="361b4-478">true</span></span> |

#### <a name="show--hide-option-to-send-feedback"></a><span data-ttu-id="361b4-479">フィードバックを送信するオプションを表示/非表示にする</span><span class="sxs-lookup"><span data-stu-id="361b4-479">Show / hide option to send feedback</span></span>

<span data-ttu-id="361b4-480">にアクセスしてユーザーが Microsoft にフィードバックを送信できるかどうかを指定します `Help`  >  `Send Feedback` 。</span><span class="sxs-lookup"><span data-stu-id="361b4-480">Specify whether users can submit feedback to Microsoft by going to `Help` > `Send Feedback`.</span></span>

|<span data-ttu-id="361b4-481">Section</span><span class="sxs-lookup"><span data-stu-id="361b4-481">Section</span></span>|<span data-ttu-id="361b4-482">値</span><span class="sxs-lookup"><span data-stu-id="361b4-482">Value</span></span>|
|:---|:---|
| <span data-ttu-id="361b4-483">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="361b4-483">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="361b4-484">**Key**</span><span class="sxs-lookup"><span data-stu-id="361b4-484">**Key**</span></span> | <span data-ttu-id="361b4-485">userInitiatedFeedback</span><span class="sxs-lookup"><span data-stu-id="361b4-485">userInitiatedFeedback</span></span> |
| <span data-ttu-id="361b4-486">**データ型**</span><span class="sxs-lookup"><span data-stu-id="361b4-486">**Data type**</span></span> | <span data-ttu-id="361b4-487">String</span><span class="sxs-lookup"><span data-stu-id="361b4-487">String</span></span> |
| <span data-ttu-id="361b4-488">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="361b4-488">**Possible values**</span></span> | <span data-ttu-id="361b4-489">有効 (既定)</span><span class="sxs-lookup"><span data-stu-id="361b4-489">enabled (default)</span></span> <br/> <span data-ttu-id="361b4-490">disabled</span><span class="sxs-lookup"><span data-stu-id="361b4-490">disabled</span></span> |
| <span data-ttu-id="361b4-491">**コメント**</span><span class="sxs-lookup"><span data-stu-id="361b4-491">**Comments**</span></span> | <span data-ttu-id="361b4-492">Microsoft Defender for Endpoint version 101.19.61 以上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="361b4-492">Available in Microsoft Defender for Endpoint version 101.19.61 or higher.</span></span> |

### <a name="endpoint-detection-and-response-preferences"></a><span data-ttu-id="361b4-493">エンドポイントの検出と応答の基本設定</span><span class="sxs-lookup"><span data-stu-id="361b4-493">Endpoint detection and response preferences</span></span>

<span data-ttu-id="361b4-494">macOS 上の Microsoft Defender for Endpoint のエンドポイント検出および応答 (EDR) コンポーネントの基本設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="361b4-494">Manage the preferences of the endpoint detection and response (EDR) component of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="361b4-495">Section</span><span class="sxs-lookup"><span data-stu-id="361b4-495">Section</span></span>|<span data-ttu-id="361b4-496">値</span><span class="sxs-lookup"><span data-stu-id="361b4-496">Value</span></span>|
|:---|:---|
| <span data-ttu-id="361b4-497">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="361b4-497">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="361b4-498">**Key**</span><span class="sxs-lookup"><span data-stu-id="361b4-498">**Key**</span></span> | <span data-ttu-id="361b4-499">edr</span><span class="sxs-lookup"><span data-stu-id="361b4-499">edr</span></span> |
| <span data-ttu-id="361b4-500">**データ型**</span><span class="sxs-lookup"><span data-stu-id="361b4-500">**Data type**</span></span> | <span data-ttu-id="361b4-501">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="361b4-501">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="361b4-502">**コメント**</span><span class="sxs-lookup"><span data-stu-id="361b4-502">**Comments**</span></span> | <span data-ttu-id="361b4-503">辞書の内容の説明については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="361b4-503">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="device-tags"></a><span data-ttu-id="361b4-504">デバイス タグ</span><span class="sxs-lookup"><span data-stu-id="361b4-504">Device tags</span></span>

<span data-ttu-id="361b4-505">タグ名とその値を指定します。</span><span class="sxs-lookup"><span data-stu-id="361b4-505">Specify a tag name and its value.</span></span> 

- <span data-ttu-id="361b4-506">GROUP タグは、デバイスに指定された値をタグ付けします。</span><span class="sxs-lookup"><span data-stu-id="361b4-506">The GROUP tag, tags the device with the specified value.</span></span> <span data-ttu-id="361b4-507">タグは、デバイス ページの下のポータルに反映され、デバイスのフィルター処理とグループ化に使用できます。</span><span class="sxs-lookup"><span data-stu-id="361b4-507">The tag is reflected in the portal under the device page and can be used for filtering and grouping devices.</span></span>

|<span data-ttu-id="361b4-508">Section</span><span class="sxs-lookup"><span data-stu-id="361b4-508">Section</span></span>|<span data-ttu-id="361b4-509">値</span><span class="sxs-lookup"><span data-stu-id="361b4-509">Value</span></span>|
|:---|:---|
| <span data-ttu-id="361b4-510">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="361b4-510">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="361b4-511">**Key**</span><span class="sxs-lookup"><span data-stu-id="361b4-511">**Key**</span></span> | <span data-ttu-id="361b4-512">tags</span><span class="sxs-lookup"><span data-stu-id="361b4-512">tags</span></span> |
| <span data-ttu-id="361b4-513">**データ型**</span><span class="sxs-lookup"><span data-stu-id="361b4-513">**Data type**</span></span> | <span data-ttu-id="361b4-514">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="361b4-514">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="361b4-515">**コメント**</span><span class="sxs-lookup"><span data-stu-id="361b4-515">**Comments**</span></span> | <span data-ttu-id="361b4-516">辞書の内容の説明については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="361b4-516">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-tag"></a><span data-ttu-id="361b4-517">タグの種類</span><span class="sxs-lookup"><span data-stu-id="361b4-517">Type of tag</span></span>

<span data-ttu-id="361b4-518">タグの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="361b4-518">Specifies the type of tag</span></span>

|<span data-ttu-id="361b4-519">Section</span><span class="sxs-lookup"><span data-stu-id="361b4-519">Section</span></span>|<span data-ttu-id="361b4-520">値</span><span class="sxs-lookup"><span data-stu-id="361b4-520">Value</span></span>|
|:---|:---|
| <span data-ttu-id="361b4-521">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="361b4-521">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="361b4-522">**Key**</span><span class="sxs-lookup"><span data-stu-id="361b4-522">**Key**</span></span> | <span data-ttu-id="361b4-523">キー</span><span class="sxs-lookup"><span data-stu-id="361b4-523">key</span></span> |
| <span data-ttu-id="361b4-524">**データ型**</span><span class="sxs-lookup"><span data-stu-id="361b4-524">**Data type**</span></span> | <span data-ttu-id="361b4-525">String</span><span class="sxs-lookup"><span data-stu-id="361b4-525">String</span></span> |
| <span data-ttu-id="361b4-526">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="361b4-526">**Possible values**</span></span> | `GROUP` |

##### <a name="value-of-tag"></a><span data-ttu-id="361b4-527">タグの値</span><span class="sxs-lookup"><span data-stu-id="361b4-527">Value of tag</span></span>

<span data-ttu-id="361b4-528">tag の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="361b4-528">Specifies the value of tag</span></span>

|<span data-ttu-id="361b4-529">Section</span><span class="sxs-lookup"><span data-stu-id="361b4-529">Section</span></span>|<span data-ttu-id="361b4-530">値</span><span class="sxs-lookup"><span data-stu-id="361b4-530">Value</span></span>|
|:---|:---|
| <span data-ttu-id="361b4-531">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="361b4-531">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="361b4-532">**Key**</span><span class="sxs-lookup"><span data-stu-id="361b4-532">**Key**</span></span> | <span data-ttu-id="361b4-533">値</span><span class="sxs-lookup"><span data-stu-id="361b4-533">value</span></span> |
| <span data-ttu-id="361b4-534">**データ型**</span><span class="sxs-lookup"><span data-stu-id="361b4-534">**Data type**</span></span> | <span data-ttu-id="361b4-535">String</span><span class="sxs-lookup"><span data-stu-id="361b4-535">String</span></span> |
| <span data-ttu-id="361b4-536">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="361b4-536">**Possible values**</span></span> | <span data-ttu-id="361b4-537">任意の文字列</span><span class="sxs-lookup"><span data-stu-id="361b4-537">any string</span></span> |

> [!IMPORTANT]  
> - <span data-ttu-id="361b4-538">タグの種類ごとに設定できる値は 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="361b4-538">Only one value per tag type can be set.</span></span>
> - <span data-ttu-id="361b4-539">タグの種類は一意であり、同じ構成プロファイルで繰り返し使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="361b4-539">Type of tags are unique, and should not be repeated in the same configuration profile.</span></span>

## <a name="recommended-configuration-profile"></a><span data-ttu-id="361b4-540">推奨される構成プロファイル</span><span class="sxs-lookup"><span data-stu-id="361b4-540">Recommended configuration profile</span></span>

<span data-ttu-id="361b4-541">開始するには、Microsoft Defender for Endpoint が提供するすべての保護機能を利用するために、企業の次の構成をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="361b4-541">To get started, we recommend the following configuration for your enterprise to take advantage of all protection features that Microsoft Defender for Endpoint provides.</span></span>

<span data-ttu-id="361b4-542">次の構成プロファイル (JAMF の場合は、カスタム設定構成プロファイルにアップロードできるプロパティ リスト) は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="361b4-542">The following configuration profile (or, in case of JAMF, a property list that could be uploaded into the custom settings configuration profile) will:</span></span>
- <span data-ttu-id="361b4-543">リアルタイム保護を有効にする (RTP)</span><span class="sxs-lookup"><span data-stu-id="361b4-543">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="361b4-544">次の脅威の種類の処理方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="361b4-544">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="361b4-545">**望ましくない可能性のあるアプリケーション (PUA) が** ブロックされる</span><span class="sxs-lookup"><span data-stu-id="361b4-545">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="361b4-546">**アーカイブボム** (圧縮率が高いファイル) が Microsoft Defender for Endpoint ログに監査される</span><span class="sxs-lookup"><span data-stu-id="361b4-546">**Archive bombs** (file with a high compression rate) are audited to Microsoft Defender for Endpoint logs</span></span>
- <span data-ttu-id="361b4-547">セキュリティ インテリジェンスの自動更新を有効にする</span><span class="sxs-lookup"><span data-stu-id="361b4-547">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="361b4-548">クラウドによる保護の有効化</span><span class="sxs-lookup"><span data-stu-id="361b4-548">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="361b4-549">自動サンプル申請を有効にする</span><span class="sxs-lookup"><span data-stu-id="361b4-549">Enable automatic sample submission</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="361b4-550">JAMF 構成プロファイルのプロパティ 一覧</span><span class="sxs-lookup"><span data-stu-id="361b4-550">Property list for JAMF configuration profile</span></span>

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a><span data-ttu-id="361b4-551">Intune プロファイル</span><span class="sxs-lookup"><span data-stu-id="361b4-551">Intune profile</span></span>

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.wdav</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
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
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

## <a name="full-configuration-profile-example"></a><span data-ttu-id="361b4-552">完全な構成プロファイルの例</span><span class="sxs-lookup"><span data-stu-id="361b4-552">Full configuration profile example</span></span>

<span data-ttu-id="361b4-553">次のテンプレートには、このドキュメントで説明されているすべての設定のエントリが含まれています。macOS の Microsoft Defender for Endpoint を詳細に制御する高度なシナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="361b4-553">The following templates contain entries for all settings described in this document and can be used for more advanced scenarios where you want more control over Microsoft Defender for Endpoint on macOS.</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="361b4-554">JAMF 構成プロファイルのプロパティ 一覧</span><span class="sxs-lookup"><span data-stu-id="361b4-554">Property list for JAMF configuration profile</span></span>

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>passiveMode</key>
        <false/>
        <key>exclusions</key>
        <array>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <false/>
                <key>path</key>
                <string>/var/log/system.log</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/home</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/Users/*/git</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileExtension</string>
                <key>extension</key>
                <string>pdf</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileName</string>
                <key>name</key>
                <string>cat</string>
            </dict>
        </array>
        <key>exclusionsMergePolicy</key>
        <string>merge</string>
        <key>allowedThreats</key>
        <array>
            <string>EICAR-Test-File (not a virus)</string>
        </array>
        <key>disallowedThreatActions</key>
        <array>
            <string>allow</string>
            <string>restore</string>
        </array>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
        <key>threatTypeSettingsMergePolicy</key>
        <string>merge</string>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>diagnosticLevel</key>
        <string>optional</string>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
    <key>edr</key>
    <dict>
        <key>tags</key>
        <array>
            <dict>
                <key>key</key>
                <string>GROUP</string>
                <key>value</key>
                <string>ExampleTag</string>
            </dict>
        </array>
    </dict>
    <key>userInterface</key>
    <dict>
        <key>hideStatusMenuIcon</key>
        <false/>
        <key>userInitiatedFeedback</key>
        <string>enabled</string>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a><span data-ttu-id="361b4-555">Intune プロファイル</span><span class="sxs-lookup"><span data-stu-id="361b4-555">Intune profile</span></span>

```XML
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
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
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>passiveMode</key>
                    <false/>
                    <key>exclusions</key>
                    <array>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <false/>
                            <key>path</key>
                            <string>/var/log/system.log</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/home</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/Users/*/git</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileExtension</string>
                            <key>extension</key>
                            <string>pdf</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileName</string>
                            <key>name</key>
                            <string>cat</string>
                        </dict>
                    </array>
                    <key>exclusionsMergePolicy</key>
                    <string>merge</string>
                    <key>allowedThreats</key>
                    <array>
                        <string>EICAR-Test-File (not a virus)</string>
                    </array>
                    <key>disallowedThreatActions</key>
                    <array>
                        <string>allow</string>
                        <string>restore</string>
                    </array>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                    <key>threatTypeSettingsMergePolicy</key>
                    <string>merge</string>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>diagnosticLevel</key>
                    <string>optional</string>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
                <key>edr</key>
                <dict>
                    <key>tags</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>GROUP</string>
                            <key>value</key>
                            <string>ExampleTag</string>
                        </dict>
                    </array>
                </dict>
                <key>userInterface</key>
                <dict>
                    <key>hideStatusMenuIcon</key>
                    <false/>
                    <key>userInitiatedFeedback</key>
                    <string>enabled</string>
                </dict>
            </dict>
        </array>
```

## <a name="property-list-validation"></a><span data-ttu-id="361b4-556">プロパティ リストの検証</span><span class="sxs-lookup"><span data-stu-id="361b4-556">Property list validation</span></span>

<span data-ttu-id="361b4-557">プロパティ リストは、有効な *.plist ファイルである必要* があります。</span><span class="sxs-lookup"><span data-stu-id="361b4-557">The property list must be a valid *.plist* file.</span></span> <span data-ttu-id="361b4-558">これを確認するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="361b4-558">This can be checked by executing:</span></span>

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

<span data-ttu-id="361b4-559">ファイルの形式が整っている場合、上記のコマンドは、 の終了 `OK` コードを出力して返します `0` 。</span><span class="sxs-lookup"><span data-stu-id="361b4-559">If the file is well-formed, the above command outputs `OK` and returns an exit code of `0`.</span></span> <span data-ttu-id="361b4-560">それ以外の場合は、問題を説明するエラーが表示され、コマンドは終了コードを返します `1` 。</span><span class="sxs-lookup"><span data-stu-id="361b4-560">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="361b4-561">構成プロファイルの展開</span><span class="sxs-lookup"><span data-stu-id="361b4-561">Configuration profile deployment</span></span>

<span data-ttu-id="361b4-562">エンタープライズの構成プロファイルを構築したら、企業が使用している管理コンソールを使用して展開できます。</span><span class="sxs-lookup"><span data-stu-id="361b4-562">Once you've built the configuration profile for your enterprise, you can deploy it through the management console that your enterprise is using.</span></span> <span data-ttu-id="361b4-563">以下のセクションでは、JAMF と Intune を使用してこのプロファイルを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="361b4-563">The following sections provide instructions on how to deploy this profile using JAMF and Intune.</span></span>

### <a name="jamf-deployment"></a><span data-ttu-id="361b4-564">JAMF の展開</span><span class="sxs-lookup"><span data-stu-id="361b4-564">JAMF deployment</span></span>

<span data-ttu-id="361b4-565">JAMF コンソールで、[**コンピューター** 構成プロファイル] を開き、使用する構成プロファイルに移動し、[カスタム 構成プロファイル] を  >  設定。 </span><span class="sxs-lookup"><span data-stu-id="361b4-565">From the JAMF console, open **Computers** > **Configuration Profiles**, navigate to the configuration profile you'd like to use, then select **Custom Settings**.</span></span> <span data-ttu-id="361b4-566">優先ドメインとしてエントリ `com.microsoft.wdav` を作成し、前に作成した *.plist を* アップロードします。</span><span class="sxs-lookup"><span data-stu-id="361b4-566">Create an entry with `com.microsoft.wdav` as the preference domain and upload the *.plist* produced earlier.</span></span>

>[!CAUTION]
><span data-ttu-id="361b4-567">正しい基本設定ドメイン ( ) を入力する必要があります。それ以外の場合、設定は `com.microsoft.wdav` Microsoft Defender for Endpoint によって認識されません。</span><span class="sxs-lookup"><span data-stu-id="361b4-567">You must enter the correct preference domain (`com.microsoft.wdav`); otherwise, the preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

### <a name="intune-deployment"></a><span data-ttu-id="361b4-568">Intune の展開</span><span class="sxs-lookup"><span data-stu-id="361b4-568">Intune deployment</span></span>

1. <span data-ttu-id="361b4-569">[デバイス **構成**  >  **の管理] を開きます**。</span><span class="sxs-lookup"><span data-stu-id="361b4-569">Open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="361b4-570">[プロファイル **の**  >  **管理] [プロファイルの**  >  **作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="361b4-570">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="361b4-571">プロファイルの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="361b4-571">Choose a name for the profile.</span></span> <span data-ttu-id="361b4-572">**Platform=macOS をプロファイル\*\*\*\*の種類=カスタム に変更します**。</span><span class="sxs-lookup"><span data-stu-id="361b4-572">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="361b4-573">[構成] を選択します。</span><span class="sxs-lookup"><span data-stu-id="361b4-573">Select Configure.</span></span>

3. <span data-ttu-id="361b4-574">以前に作成した .plist を次のように保存します `com.microsoft.wdav.xml` 。</span><span class="sxs-lookup"><span data-stu-id="361b4-574">Save the .plist produced earlier as `com.microsoft.wdav.xml`.</span></span>

4. <span data-ttu-id="361b4-575">カスタム `com.microsoft.wdav` 構成プロファイル **名として入力します**。</span><span class="sxs-lookup"><span data-stu-id="361b4-575">Enter `com.microsoft.wdav` as the **custom configuration profile name**.</span></span>

5. <span data-ttu-id="361b4-576">構成プロファイルを開き、ファイルを `com.microsoft.wdav.xml` アップロードします。</span><span class="sxs-lookup"><span data-stu-id="361b4-576">Open the configuration profile and upload the `com.microsoft.wdav.xml` file.</span></span> <span data-ttu-id="361b4-577">(このファイルは手順 3 で作成されました。</span><span class="sxs-lookup"><span data-stu-id="361b4-577">(This file was created in step 3.)</span></span>

6. <span data-ttu-id="361b4-578">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="361b4-578">Select **OK**.</span></span>

7. <span data-ttu-id="361b4-579">[割 **り当**  >  **ての管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="361b4-579">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="361b4-580">[含める **] タブ** で、[すべてのユーザーに割り当てる] & **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="361b4-580">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

>[!CAUTION]
><span data-ttu-id="361b4-581">正しいカスタム構成プロファイル名を入力する必要があります。それ以外の場合、これらの基本設定は Microsoft Defender for Endpoint によって認識されません。</span><span class="sxs-lookup"><span data-stu-id="361b4-581">You must enter the correct custom configuration profile name; otherwise, these preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

## <a name="resources"></a><span data-ttu-id="361b4-582">関連情報</span><span class="sxs-lookup"><span data-stu-id="361b4-582">Resources</span></span>

- [<span data-ttu-id="361b4-583">プロファイル構成リファレンス (Apple 開発者向けドキュメント)</span><span class="sxs-lookup"><span data-stu-id="361b4-583">Configuration Profile Reference (Apple developer documentation)</span></span>](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
