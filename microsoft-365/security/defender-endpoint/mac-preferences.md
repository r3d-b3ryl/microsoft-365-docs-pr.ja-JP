---
title: Microsoft Defender for Endpoint for Mac の基本設定を設定する
description: エンタープライズ組織で Microsoft Defender for Endpoint for Mac を構成します。
keywords: microsoft、defender、atp、mac、management、preferences、enterprise、intune、jamf、macos、catalina、mojave、high sierra
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
ms.openlocfilehash: d2bea469031e2c5932e859fbad7d442ebe4d34ed
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860925"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="5911f-104">macOS のエンドポイント用 Microsoft Defender の基本設定を設定する</span><span class="sxs-lookup"><span data-stu-id="5911f-104">Set preferences for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5911f-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="5911f-105">**Applies to:**</span></span>

- [<span data-ttu-id="5911f-106">macOS 用 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5911f-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
><span data-ttu-id="5911f-107">この記事では、エンタープライズ組織の macOS で Microsoft Defender for Endpoint の基本設定を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5911f-107">This article contains instructions for how to set preferences for Microsoft Defender for Endpoint on macOS in enterprise organizations.</span></span> <span data-ttu-id="5911f-108">コマンド ライン インターフェイスを使用して macOS 上の Microsoft Defender for Endpoint を構成するには、「Resources」を [参照してください](mac-resources.md#configuring-from-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="5911f-108">To configure Microsoft Defender for Endpoint on macOS using the command-line interface, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

## <a name="summary"></a><span data-ttu-id="5911f-109">概要</span><span class="sxs-lookup"><span data-stu-id="5911f-109">Summary</span></span>

<span data-ttu-id="5911f-110">エンタープライズ組織では、macOS 上の Microsoft Defender for Endpoint を、いくつかの管理ツールのいずれかを使用して展開される構成プロファイルを介して管理できます。</span><span class="sxs-lookup"><span data-stu-id="5911f-110">In enterprise organizations, Microsoft Defender for Endpoint on macOS can be managed through a configuration profile that is deployed by using one of several management tools.</span></span> <span data-ttu-id="5911f-111">セキュリティ運用チームによって管理される基本設定は、デバイス上でローカルに設定されている基本設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="5911f-111">Preferences that are managed by your security operations team take precedence over preferences that are set locally on the device.</span></span> <span data-ttu-id="5911f-112">構成プロファイルを使用して設定される基本設定を変更するには、エスカレートされた特権が必要であり、管理アクセス許可のないユーザーでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="5911f-112">Changing the preferences that are set through the configuration profile requires escalated privileges and is not available for users without administrative permissions.</span></span>

<span data-ttu-id="5911f-113">この記事では、構成プロファイルの構造、開始に使用できる推奨プロファイル、およびプロファイルの展開方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5911f-113">This article describes the structure of the configuration profile, includes a recommended profile that you can use to get started, and provides instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="5911f-114">構成プロファイル構造</span><span class="sxs-lookup"><span data-stu-id="5911f-114">Configuration profile structure</span></span>

<span data-ttu-id="5911f-115">構成プロファイルは *.plist* ファイルで、キーによって識別されるエントリ (基本設定の名前を示す) で構成され、その後に、プリファレンスの性質に依存する値が続きます。</span><span class="sxs-lookup"><span data-stu-id="5911f-115">The configuration profile is a *.plist* file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="5911f-116">値は、単純な (数値など) か、入れ子になった基本設定リストなどの複雑な値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5911f-116">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

>[!CAUTION]
><span data-ttu-id="5911f-117">構成プロファイルのレイアウトは、使用している管理コンソールによって異なります。</span><span class="sxs-lookup"><span data-stu-id="5911f-117">The layout of the configuration profile depends on the management console that you are using.</span></span> <span data-ttu-id="5911f-118">次のセクションでは、JAMF と Intune の構成プロファイルの例を示します。</span><span class="sxs-lookup"><span data-stu-id="5911f-118">The following sections contain examples of configuration profiles for JAMF and Intune.</span></span>

<span data-ttu-id="5911f-119">構成プロファイルのトップ レベルには、製品全体の基本設定と、Microsoft Defender for Endpoint のサブエリアのエントリが含まれています。これは、次のセクションで詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="5911f-119">The top level of the configuration profile includes product-wide preferences and entries for subareas of Microsoft Defender for Endpoint, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="5911f-120">ウイルス対策エンジンの基本設定</span><span class="sxs-lookup"><span data-stu-id="5911f-120">Antivirus engine preferences</span></span>

<span data-ttu-id="5911f-121">構成 *プロファイルの antivirusEngine* セクションは、Microsoft Defender for Endpoint のウイルス対策コンポーネントの基本設定を管理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="5911f-121">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of Microsoft Defender for Endpoint.</span></span>

|<span data-ttu-id="5911f-122">Section</span><span class="sxs-lookup"><span data-stu-id="5911f-122">Section</span></span>|<span data-ttu-id="5911f-123">値</span><span class="sxs-lookup"><span data-stu-id="5911f-123">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5911f-124">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="5911f-124">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5911f-125">**Key**</span><span class="sxs-lookup"><span data-stu-id="5911f-125">**Key**</span></span> | <span data-ttu-id="5911f-126">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="5911f-126">antivirusEngine</span></span> |
| <span data-ttu-id="5911f-127">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5911f-127">**Data type**</span></span> | <span data-ttu-id="5911f-128">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="5911f-128">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="5911f-129">**コメント**</span><span class="sxs-lookup"><span data-stu-id="5911f-129">**Comments**</span></span> | <span data-ttu-id="5911f-130">辞書の内容の説明については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5911f-130">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="5911f-131">リアルタイム保護を有効/無効にする</span><span class="sxs-lookup"><span data-stu-id="5911f-131">Enable / disable real-time protection</span></span>

<span data-ttu-id="5911f-132">アクセス時にファイルをスキャンするリアルタイム保護を有効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="5911f-132">Specify whether to enable real-time protection, which scans files as they are accessed.</span></span>

|<span data-ttu-id="5911f-133">Section</span><span class="sxs-lookup"><span data-stu-id="5911f-133">Section</span></span>|<span data-ttu-id="5911f-134">値</span><span class="sxs-lookup"><span data-stu-id="5911f-134">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5911f-135">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="5911f-135">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5911f-136">**Key**</span><span class="sxs-lookup"><span data-stu-id="5911f-136">**Key**</span></span> | <span data-ttu-id="5911f-137">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="5911f-137">enableRealTimeProtection</span></span> |
| <span data-ttu-id="5911f-138">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5911f-138">**Data type**</span></span> | <span data-ttu-id="5911f-139">Boolean</span><span class="sxs-lookup"><span data-stu-id="5911f-139">Boolean</span></span> |
| <span data-ttu-id="5911f-140">**可能な値**</span><span class="sxs-lookup"><span data-stu-id="5911f-140">**Possible values**</span></span> | <span data-ttu-id="5911f-141">true (既定)</span><span class="sxs-lookup"><span data-stu-id="5911f-141">true (default)</span></span> <br/> <span data-ttu-id="5911f-142">false</span><span class="sxs-lookup"><span data-stu-id="5911f-142">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="5911f-143">パッシブ モードを有効/無効にする</span><span class="sxs-lookup"><span data-stu-id="5911f-143">Enable / disable passive mode</span></span>

<span data-ttu-id="5911f-144">ウイルス対策エンジンをパッシブ モードで実行するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="5911f-144">Specify whether the antivirus engine runs in passive mode.</span></span> <span data-ttu-id="5911f-145">パッシブ モードには、次のような影響があります。</span><span class="sxs-lookup"><span data-stu-id="5911f-145">Passive mode has the following implications:</span></span> 
- <span data-ttu-id="5911f-146">リアルタイム保護がオフになっている</span><span class="sxs-lookup"><span data-stu-id="5911f-146">Real-time protection is turned off</span></span>
- <span data-ttu-id="5911f-147">オンデマンド スキャンが有効になっている</span><span class="sxs-lookup"><span data-stu-id="5911f-147">On-demand scanning is turned on</span></span>
- <span data-ttu-id="5911f-148">脅威の自動修復が無効になっている</span><span class="sxs-lookup"><span data-stu-id="5911f-148">Automatic threat remediation is turned off</span></span>
- <span data-ttu-id="5911f-149">セキュリティ インテリジェンスの更新プログラムが有効になっている</span><span class="sxs-lookup"><span data-stu-id="5911f-149">Security intelligence updates are turned on</span></span>
- <span data-ttu-id="5911f-150">[状態] メニュー アイコンが非表示</span><span class="sxs-lookup"><span data-stu-id="5911f-150">Status menu icon is hidden</span></span>

|<span data-ttu-id="5911f-151">Section</span><span class="sxs-lookup"><span data-stu-id="5911f-151">Section</span></span>|<span data-ttu-id="5911f-152">値</span><span class="sxs-lookup"><span data-stu-id="5911f-152">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5911f-153">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="5911f-153">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5911f-154">**Key**</span><span class="sxs-lookup"><span data-stu-id="5911f-154">**Key**</span></span> | <span data-ttu-id="5911f-155">passiveMode</span><span class="sxs-lookup"><span data-stu-id="5911f-155">passiveMode</span></span> |
| <span data-ttu-id="5911f-156">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5911f-156">**Data type**</span></span> | <span data-ttu-id="5911f-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="5911f-157">Boolean</span></span> |
| <span data-ttu-id="5911f-158">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="5911f-158">**Possible values**</span></span> | <span data-ttu-id="5911f-159">false (既定)</span><span class="sxs-lookup"><span data-stu-id="5911f-159">false (default)</span></span> <br/> <span data-ttu-id="5911f-160">true</span><span class="sxs-lookup"><span data-stu-id="5911f-160">true</span></span> |
| <span data-ttu-id="5911f-161">**コメント**</span><span class="sxs-lookup"><span data-stu-id="5911f-161">**Comments**</span></span> | <span data-ttu-id="5911f-162">Microsoft Defender for Endpoint version 100.67.60 以上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="5911f-162">Available in Microsoft Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="5911f-163">除外マージ ポリシー</span><span class="sxs-lookup"><span data-stu-id="5911f-163">Exclusion merge policy</span></span>

<span data-ttu-id="5911f-164">除外のマージ ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="5911f-164">Specify the merge policy for exclusions.</span></span> <span data-ttu-id="5911f-165">これには、管理者定義の除外とユーザー定義の除外 ( ) の組み合わせ、または管理者定義の除外 ( ) のみを `merge` 組み合わせて指定できます `admin_only` 。</span><span class="sxs-lookup"><span data-stu-id="5911f-165">This can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="5911f-166">この設定は、ローカル ユーザーが独自の除外を定義するのを制限するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="5911f-166">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|<span data-ttu-id="5911f-167">Section</span><span class="sxs-lookup"><span data-stu-id="5911f-167">Section</span></span>|<span data-ttu-id="5911f-168">値</span><span class="sxs-lookup"><span data-stu-id="5911f-168">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5911f-169">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="5911f-169">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5911f-170">**Key**</span><span class="sxs-lookup"><span data-stu-id="5911f-170">**Key**</span></span> | <span data-ttu-id="5911f-171">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="5911f-171">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="5911f-172">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5911f-172">**Data type**</span></span> | <span data-ttu-id="5911f-173">String</span><span class="sxs-lookup"><span data-stu-id="5911f-173">String</span></span> |
| <span data-ttu-id="5911f-174">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="5911f-174">**Possible values**</span></span> | <span data-ttu-id="5911f-175">merge (既定)</span><span class="sxs-lookup"><span data-stu-id="5911f-175">merge (default)</span></span> <br/> <span data-ttu-id="5911f-176">admin_only</span><span class="sxs-lookup"><span data-stu-id="5911f-176">admin_only</span></span> |
| <span data-ttu-id="5911f-177">**コメント**</span><span class="sxs-lookup"><span data-stu-id="5911f-177">**Comments**</span></span> | <span data-ttu-id="5911f-178">Microsoft Defender for Endpoint version 100.83.73 以上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="5911f-178">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="5911f-179">スキャンの除外</span><span class="sxs-lookup"><span data-stu-id="5911f-179">Scan exclusions</span></span>

<span data-ttu-id="5911f-180">スキャン対象から除外されるエンティティを指定します。</span><span class="sxs-lookup"><span data-stu-id="5911f-180">Specify entities excluded from being scanned.</span></span> <span data-ttu-id="5911f-181">除外は、完全パス、拡張子、またはファイル名で指定できます。</span><span class="sxs-lookup"><span data-stu-id="5911f-181">Exclusions can be specified by full paths, extensions, or file names.</span></span>

|<span data-ttu-id="5911f-182">Section</span><span class="sxs-lookup"><span data-stu-id="5911f-182">Section</span></span>|<span data-ttu-id="5911f-183">値</span><span class="sxs-lookup"><span data-stu-id="5911f-183">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5911f-184">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="5911f-184">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5911f-185">**Key**</span><span class="sxs-lookup"><span data-stu-id="5911f-185">**Key**</span></span> | <span data-ttu-id="5911f-186">除外</span><span class="sxs-lookup"><span data-stu-id="5911f-186">exclusions</span></span> |
| <span data-ttu-id="5911f-187">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5911f-187">**Data type**</span></span> | <span data-ttu-id="5911f-188">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="5911f-188">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="5911f-189">**コメント**</span><span class="sxs-lookup"><span data-stu-id="5911f-189">**Comments**</span></span> | <span data-ttu-id="5911f-190">辞書の内容の説明については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5911f-190">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-exclusion"></a><span data-ttu-id="5911f-191">除外の種類</span><span class="sxs-lookup"><span data-stu-id="5911f-191">Type of exclusion</span></span>

<span data-ttu-id="5911f-192">種類別にスキャン対象から除外されるコンテンツを指定します。</span><span class="sxs-lookup"><span data-stu-id="5911f-192">Specify content excluded from being scanned by type.</span></span>

|<span data-ttu-id="5911f-193">Section</span><span class="sxs-lookup"><span data-stu-id="5911f-193">Section</span></span>|<span data-ttu-id="5911f-194">値</span><span class="sxs-lookup"><span data-stu-id="5911f-194">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5911f-195">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="5911f-195">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5911f-196">**Key**</span><span class="sxs-lookup"><span data-stu-id="5911f-196">**Key**</span></span> | <span data-ttu-id="5911f-197">$type</span><span class="sxs-lookup"><span data-stu-id="5911f-197">$type</span></span> |
| <span data-ttu-id="5911f-198">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5911f-198">**Data type**</span></span> | <span data-ttu-id="5911f-199">String</span><span class="sxs-lookup"><span data-stu-id="5911f-199">String</span></span> |
| <span data-ttu-id="5911f-200">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="5911f-200">**Possible values**</span></span> | <span data-ttu-id="5911f-201">excludedPath</span><span class="sxs-lookup"><span data-stu-id="5911f-201">excludedPath</span></span> <br/> <span data-ttu-id="5911f-202">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="5911f-202">excludedFileExtension</span></span> <br/> <span data-ttu-id="5911f-203">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="5911f-203">excludedFileName</span></span> |

##### <a name="path-to-excluded-content"></a><span data-ttu-id="5911f-204">除外されたコンテンツへのパス</span><span class="sxs-lookup"><span data-stu-id="5911f-204">Path to excluded content</span></span>

<span data-ttu-id="5911f-205">完全なファイル パスでスキャンされるコンテンツを除外するを指定します。</span><span class="sxs-lookup"><span data-stu-id="5911f-205">Specify content excluded from being scanned by full file path.</span></span>

|<span data-ttu-id="5911f-206">Section</span><span class="sxs-lookup"><span data-stu-id="5911f-206">Section</span></span>|<span data-ttu-id="5911f-207">値</span><span class="sxs-lookup"><span data-stu-id="5911f-207">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5911f-208">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="5911f-208">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5911f-209">**Key**</span><span class="sxs-lookup"><span data-stu-id="5911f-209">**Key**</span></span> | <span data-ttu-id="5911f-210">path</span><span class="sxs-lookup"><span data-stu-id="5911f-210">path</span></span> |
| <span data-ttu-id="5911f-211">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5911f-211">**Data type**</span></span> | <span data-ttu-id="5911f-212">String</span><span class="sxs-lookup"><span data-stu-id="5911f-212">String</span></span> |
| <span data-ttu-id="5911f-213">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="5911f-213">**Possible values**</span></span> | <span data-ttu-id="5911f-214">有効なパス</span><span class="sxs-lookup"><span data-stu-id="5911f-214">valid paths</span></span> |
| <span data-ttu-id="5911f-215">**コメント**</span><span class="sxs-lookup"><span data-stu-id="5911f-215">**Comments**</span></span> | <span data-ttu-id="5911f-216">適用 *できるのは、$type\*\*が excludedPath である場合のみです。*</span><span class="sxs-lookup"><span data-stu-id="5911f-216">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="path-type-file--directory"></a><span data-ttu-id="5911f-217">パスの種類 (ファイル/ディレクトリ)</span><span class="sxs-lookup"><span data-stu-id="5911f-217">Path type (file / directory)</span></span>

<span data-ttu-id="5911f-218">path プロパティが *ファイル* またはディレクトリを参照しているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="5911f-218">Indicate if the *path* property refers to a file or directory.</span></span> 

|<span data-ttu-id="5911f-219">Section</span><span class="sxs-lookup"><span data-stu-id="5911f-219">Section</span></span>|<span data-ttu-id="5911f-220">値</span><span class="sxs-lookup"><span data-stu-id="5911f-220">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5911f-221">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="5911f-221">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5911f-222">**Key**</span><span class="sxs-lookup"><span data-stu-id="5911f-222">**Key**</span></span> | <span data-ttu-id="5911f-223">isDirectory</span><span class="sxs-lookup"><span data-stu-id="5911f-223">isDirectory</span></span> |
| <span data-ttu-id="5911f-224">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5911f-224">**Data type**</span></span> | <span data-ttu-id="5911f-225">Boolean</span><span class="sxs-lookup"><span data-stu-id="5911f-225">Boolean</span></span> |
| <span data-ttu-id="5911f-226">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="5911f-226">**Possible values**</span></span> | <span data-ttu-id="5911f-227">false (既定)</span><span class="sxs-lookup"><span data-stu-id="5911f-227">false (default)</span></span> <br/> <span data-ttu-id="5911f-228">true</span><span class="sxs-lookup"><span data-stu-id="5911f-228">true</span></span> |
| <span data-ttu-id="5911f-229">**コメント**</span><span class="sxs-lookup"><span data-stu-id="5911f-229">**Comments**</span></span> | <span data-ttu-id="5911f-230">適用 *できるのは、$type\*\*が excludedPath である場合のみです。*</span><span class="sxs-lookup"><span data-stu-id="5911f-230">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="5911f-231">スキャンから除外されたファイル拡張子</span><span class="sxs-lookup"><span data-stu-id="5911f-231">File extension excluded from the scan</span></span>

<span data-ttu-id="5911f-232">ファイル拡張子によるスキャン対象から除外されるコンテンツを指定します。</span><span class="sxs-lookup"><span data-stu-id="5911f-232">Specify content excluded from being scanned by file extension.</span></span>

|<span data-ttu-id="5911f-233">Section</span><span class="sxs-lookup"><span data-stu-id="5911f-233">Section</span></span>|<span data-ttu-id="5911f-234">値</span><span class="sxs-lookup"><span data-stu-id="5911f-234">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5911f-235">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="5911f-235">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5911f-236">**Key**</span><span class="sxs-lookup"><span data-stu-id="5911f-236">**Key**</span></span> | <span data-ttu-id="5911f-237">拡張機能</span><span class="sxs-lookup"><span data-stu-id="5911f-237">extension</span></span> |
| <span data-ttu-id="5911f-238">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5911f-238">**Data type**</span></span> | <span data-ttu-id="5911f-239">String</span><span class="sxs-lookup"><span data-stu-id="5911f-239">String</span></span> |
| <span data-ttu-id="5911f-240">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="5911f-240">**Possible values**</span></span> | <span data-ttu-id="5911f-241">有効なファイル拡張子</span><span class="sxs-lookup"><span data-stu-id="5911f-241">valid file extensions</span></span> |
| <span data-ttu-id="5911f-242">**コメント**</span><span class="sxs-lookup"><span data-stu-id="5911f-242">**Comments**</span></span> | <span data-ttu-id="5911f-243">適用 *できるのは* 、$type FileExtension が *除外されている場合のみです。*</span><span class="sxs-lookup"><span data-stu-id="5911f-243">Applicable only if *$type* is *excludedFileExtension*</span></span> |

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="5911f-244">スキャンから除外されるプロセス</span><span class="sxs-lookup"><span data-stu-id="5911f-244">Process excluded from the scan</span></span>

<span data-ttu-id="5911f-245">すべてのファイル アクティビティがスキャンから除外されるプロセスを指定します。</span><span class="sxs-lookup"><span data-stu-id="5911f-245">Specify a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="5911f-246">プロセスは、名前 (例: ) または完全 `cat` パス (例: ) で指定できます `/bin/cat` 。</span><span class="sxs-lookup"><span data-stu-id="5911f-246">The process can be specified either by its name (e.g. `cat`) or full path (e.g. `/bin/cat`).</span></span>

|<span data-ttu-id="5911f-247">Section</span><span class="sxs-lookup"><span data-stu-id="5911f-247">Section</span></span>|<span data-ttu-id="5911f-248">値</span><span class="sxs-lookup"><span data-stu-id="5911f-248">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5911f-249">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="5911f-249">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5911f-250">**Key**</span><span class="sxs-lookup"><span data-stu-id="5911f-250">**Key**</span></span> | <span data-ttu-id="5911f-251">name</span><span class="sxs-lookup"><span data-stu-id="5911f-251">name</span></span> |
| <span data-ttu-id="5911f-252">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5911f-252">**Data type**</span></span> | <span data-ttu-id="5911f-253">String</span><span class="sxs-lookup"><span data-stu-id="5911f-253">String</span></span> |
| <span data-ttu-id="5911f-254">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="5911f-254">**Possible values**</span></span> | <span data-ttu-id="5911f-255">任意の文字列</span><span class="sxs-lookup"><span data-stu-id="5911f-255">any string</span></span> |
| <span data-ttu-id="5911f-256">**コメント**</span><span class="sxs-lookup"><span data-stu-id="5911f-256">**Comments**</span></span> | <span data-ttu-id="5911f-257">ファイルが excludedFileName *$type\*\*場合にのみ適用されます。*</span><span class="sxs-lookup"><span data-stu-id="5911f-257">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="5911f-258">許可される脅威</span><span class="sxs-lookup"><span data-stu-id="5911f-258">Allowed threats</span></span>

<span data-ttu-id="5911f-259">Defender for Endpoint for Mac でブロックされない脅威を名前で指定します。</span><span class="sxs-lookup"><span data-stu-id="5911f-259">Specify threats by name that are not blocked by Defender for Endpoint for Mac.</span></span> <span data-ttu-id="5911f-260">これらの脅威の実行が許可されます。</span><span class="sxs-lookup"><span data-stu-id="5911f-260">These threats will be allowed to run.</span></span>

|<span data-ttu-id="5911f-261">Section</span><span class="sxs-lookup"><span data-stu-id="5911f-261">Section</span></span>|<span data-ttu-id="5911f-262">値</span><span class="sxs-lookup"><span data-stu-id="5911f-262">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5911f-263">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="5911f-263">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5911f-264">**Key**</span><span class="sxs-lookup"><span data-stu-id="5911f-264">**Key**</span></span> | <span data-ttu-id="5911f-265">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="5911f-265">allowedThreats</span></span> |
| <span data-ttu-id="5911f-266">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5911f-266">**Data type**</span></span> | <span data-ttu-id="5911f-267">文字列の配列</span><span class="sxs-lookup"><span data-stu-id="5911f-267">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="5911f-268">禁止された脅威アクション</span><span class="sxs-lookup"><span data-stu-id="5911f-268">Disallowed threat actions</span></span>

<span data-ttu-id="5911f-269">脅威が検出された場合にデバイスのローカル ユーザーが実行できるアクションを制限します。</span><span class="sxs-lookup"><span data-stu-id="5911f-269">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="5911f-270">この一覧に含まれるアクションは、ユーザー インターフェイスには表示されません。</span><span class="sxs-lookup"><span data-stu-id="5911f-270">The actions included in this list are not displayed in the user interface.</span></span>

|<span data-ttu-id="5911f-271">Section</span><span class="sxs-lookup"><span data-stu-id="5911f-271">Section</span></span>|<span data-ttu-id="5911f-272">値</span><span class="sxs-lookup"><span data-stu-id="5911f-272">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5911f-273">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="5911f-273">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5911f-274">**Key**</span><span class="sxs-lookup"><span data-stu-id="5911f-274">**Key**</span></span> | <span data-ttu-id="5911f-275">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="5911f-275">disallowedThreatActions</span></span> |
| <span data-ttu-id="5911f-276">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5911f-276">**Data type**</span></span> | <span data-ttu-id="5911f-277">文字列の配列</span><span class="sxs-lookup"><span data-stu-id="5911f-277">Array of strings</span></span> |
| <span data-ttu-id="5911f-278">**可能な値**</span><span class="sxs-lookup"><span data-stu-id="5911f-278">**Possible values**</span></span> | <span data-ttu-id="5911f-279">allow (ユーザーによる脅威の許可を制限する)</span><span class="sxs-lookup"><span data-stu-id="5911f-279">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="5911f-280">復元 (検疫からの脅威の復元をユーザーに制限する)</span><span class="sxs-lookup"><span data-stu-id="5911f-280">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="5911f-281">**コメント**</span><span class="sxs-lookup"><span data-stu-id="5911f-281">**Comments**</span></span> | <span data-ttu-id="5911f-282">Microsoft Defender for Endpoint version 100.83.73 以上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="5911f-282">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="5911f-283">脅威の種類の設定</span><span class="sxs-lookup"><span data-stu-id="5911f-283">Threat type settings</span></span>

<span data-ttu-id="5911f-284">特定の脅威の種類を macOS 上の Microsoft Defender for Endpoint で処理する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="5911f-284">Specify how certain threat types are handled by Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="5911f-285">Section</span><span class="sxs-lookup"><span data-stu-id="5911f-285">Section</span></span>|<span data-ttu-id="5911f-286">値</span><span class="sxs-lookup"><span data-stu-id="5911f-286">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5911f-287">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="5911f-287">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5911f-288">**Key**</span><span class="sxs-lookup"><span data-stu-id="5911f-288">**Key**</span></span> | <span data-ttu-id="5911f-289">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="5911f-289">threatTypeSettings</span></span> |
| <span data-ttu-id="5911f-290">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5911f-290">**Data type**</span></span> | <span data-ttu-id="5911f-291">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="5911f-291">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="5911f-292">**コメント**</span><span class="sxs-lookup"><span data-stu-id="5911f-292">**Comments**</span></span> | <span data-ttu-id="5911f-293">辞書の内容の説明については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5911f-293">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="threat-type"></a><span data-ttu-id="5911f-294">脅威の種類</span><span class="sxs-lookup"><span data-stu-id="5911f-294">Threat type</span></span>

<span data-ttu-id="5911f-295">脅威の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="5911f-295">Specify threat types.</span></span>

|<span data-ttu-id="5911f-296">Section</span><span class="sxs-lookup"><span data-stu-id="5911f-296">Section</span></span>|<span data-ttu-id="5911f-297">値</span><span class="sxs-lookup"><span data-stu-id="5911f-297">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5911f-298">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="5911f-298">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5911f-299">**Key**</span><span class="sxs-lookup"><span data-stu-id="5911f-299">**Key**</span></span> | <span data-ttu-id="5911f-300">キー</span><span class="sxs-lookup"><span data-stu-id="5911f-300">key</span></span> |
| <span data-ttu-id="5911f-301">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5911f-301">**Data type**</span></span> | <span data-ttu-id="5911f-302">String</span><span class="sxs-lookup"><span data-stu-id="5911f-302">String</span></span> |
| <span data-ttu-id="5911f-303">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="5911f-303">**Possible values**</span></span> | <span data-ttu-id="5911f-304">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="5911f-304">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="5911f-305">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="5911f-305">archive_bomb</span></span> |

##### <a name="action-to-take"></a><span data-ttu-id="5911f-306">実行する操作</span><span class="sxs-lookup"><span data-stu-id="5911f-306">Action to take</span></span>

<span data-ttu-id="5911f-307">前のセクションで指定した種類の脅威が検出された場合に実行するアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="5911f-307">Specify what action to take when a threat of the type specified in the preceding section is detected.</span></span> <span data-ttu-id="5911f-308">次のオプションから選択します。</span><span class="sxs-lookup"><span data-stu-id="5911f-308">Choose from the following options:</span></span>

- <span data-ttu-id="5911f-309">**監査**: デバイスは、この種類の脅威から保護されませんが、脅威に関するエントリがログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="5911f-309">**Audit**: your device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="5911f-310">**ブロック**: デバイスは、この種類の脅威から保護され、ユーザー インターフェイスとセキュリティ コンソールで通知されます。</span><span class="sxs-lookup"><span data-stu-id="5911f-310">**Block**: your device is protected against this type of threat and you are notified in the user interface and the security console.</span></span>
- <span data-ttu-id="5911f-311">**オフ**: デバイスは、この種類の脅威から保護され、何もログに記録されません。</span><span class="sxs-lookup"><span data-stu-id="5911f-311">**Off**: your device is not protected against this type of threat and nothing is logged.</span></span>

|<span data-ttu-id="5911f-312">Section</span><span class="sxs-lookup"><span data-stu-id="5911f-312">Section</span></span>|<span data-ttu-id="5911f-313">値</span><span class="sxs-lookup"><span data-stu-id="5911f-313">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5911f-314">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="5911f-314">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5911f-315">**Key**</span><span class="sxs-lookup"><span data-stu-id="5911f-315">**Key**</span></span> | <span data-ttu-id="5911f-316">値</span><span class="sxs-lookup"><span data-stu-id="5911f-316">value</span></span> |
| <span data-ttu-id="5911f-317">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5911f-317">**Data type**</span></span> | <span data-ttu-id="5911f-318">String</span><span class="sxs-lookup"><span data-stu-id="5911f-318">String</span></span> |
| <span data-ttu-id="5911f-319">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="5911f-319">**Possible values**</span></span> | <span data-ttu-id="5911f-320">監査 (既定)</span><span class="sxs-lookup"><span data-stu-id="5911f-320">audit (default)</span></span> <br/> <span data-ttu-id="5911f-321">block</span><span class="sxs-lookup"><span data-stu-id="5911f-321">block</span></span> <br/> <span data-ttu-id="5911f-322">off</span><span class="sxs-lookup"><span data-stu-id="5911f-322">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="5911f-323">脅威の種類の設定の差し込みポリシー</span><span class="sxs-lookup"><span data-stu-id="5911f-323">Threat type settings merge policy</span></span>

<span data-ttu-id="5911f-324">脅威の種類の設定のマージ ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="5911f-324">Specify the merge policy for threat type settings.</span></span> <span data-ttu-id="5911f-325">これは、管理者定義設定とユーザー定義設定 ( ) の組み合わせか、管理者定義の設定 ( ) のみを `merge` 組み合わせて使用できます `admin_only` 。</span><span class="sxs-lookup"><span data-stu-id="5911f-325">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="5911f-326">この設定を使用すると、ローカル ユーザーがさまざまな脅威の種類に対して独自の設定を定義するのを制限できます。</span><span class="sxs-lookup"><span data-stu-id="5911f-326">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|<span data-ttu-id="5911f-327">Section</span><span class="sxs-lookup"><span data-stu-id="5911f-327">Section</span></span>|<span data-ttu-id="5911f-328">値</span><span class="sxs-lookup"><span data-stu-id="5911f-328">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5911f-329">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="5911f-329">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5911f-330">**Key**</span><span class="sxs-lookup"><span data-stu-id="5911f-330">**Key**</span></span> | <span data-ttu-id="5911f-331">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="5911f-331">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="5911f-332">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5911f-332">**Data type**</span></span> | <span data-ttu-id="5911f-333">String</span><span class="sxs-lookup"><span data-stu-id="5911f-333">String</span></span> |
| <span data-ttu-id="5911f-334">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="5911f-334">**Possible values**</span></span> | <span data-ttu-id="5911f-335">merge (既定)</span><span class="sxs-lookup"><span data-stu-id="5911f-335">merge (default)</span></span> <br/> <span data-ttu-id="5911f-336">admin_only</span><span class="sxs-lookup"><span data-stu-id="5911f-336">admin_only</span></span> |
| <span data-ttu-id="5911f-337">**コメント**</span><span class="sxs-lookup"><span data-stu-id="5911f-337">**Comments**</span></span> | <span data-ttu-id="5911f-338">Microsoft Defender for Endpoint version 100.83.73 以上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="5911f-338">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="5911f-339">ウイルス対策スキャン履歴の保持 (日数)</span><span class="sxs-lookup"><span data-stu-id="5911f-339">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="5911f-340">デバイスのスキャン履歴に結果が保持される日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="5911f-340">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="5911f-341">古いスキャン結果は履歴から削除されます。</span><span class="sxs-lookup"><span data-stu-id="5911f-341">Old scan results are removed from the history.</span></span> <span data-ttu-id="5911f-342">ディスクから削除された古い検疫済みファイル。</span><span class="sxs-lookup"><span data-stu-id="5911f-342">Old quarantined files that are also removed from the disk.</span></span>

|<span data-ttu-id="5911f-343">Section</span><span class="sxs-lookup"><span data-stu-id="5911f-343">Section</span></span>|<span data-ttu-id="5911f-344">値</span><span class="sxs-lookup"><span data-stu-id="5911f-344">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5911f-345">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="5911f-345">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5911f-346">**Key**</span><span class="sxs-lookup"><span data-stu-id="5911f-346">**Key**</span></span> | <span data-ttu-id="5911f-347">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="5911f-347">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="5911f-348">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5911f-348">**Data type**</span></span> | <span data-ttu-id="5911f-349">String</span><span class="sxs-lookup"><span data-stu-id="5911f-349">String</span></span> |
| <span data-ttu-id="5911f-350">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="5911f-350">**Possible values**</span></span> | <span data-ttu-id="5911f-351">90 (既定)。</span><span class="sxs-lookup"><span data-stu-id="5911f-351">90 (default).</span></span> <span data-ttu-id="5911f-352">使用できる値は、1 日から 180 日です。</span><span class="sxs-lookup"><span data-stu-id="5911f-352">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="5911f-353">**コメント**</span><span class="sxs-lookup"><span data-stu-id="5911f-353">**Comments**</span></span> | <span data-ttu-id="5911f-354">エンドポイント バージョン 101.07.23 以上の Microsoft Defender で使用できます。</span><span class="sxs-lookup"><span data-stu-id="5911f-354">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="5911f-355">ウイルス対策スキャン履歴内のアイテムの最大数</span><span class="sxs-lookup"><span data-stu-id="5911f-355">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="5911f-356">スキャン履歴に保持するエントリの最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="5911f-356">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="5911f-357">エントリには、過去に実行されたオンデマンド スキャンとすべてのウイルス対策検出が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5911f-357">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|<span data-ttu-id="5911f-358">Section</span><span class="sxs-lookup"><span data-stu-id="5911f-358">Section</span></span>|<span data-ttu-id="5911f-359">値</span><span class="sxs-lookup"><span data-stu-id="5911f-359">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5911f-360">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="5911f-360">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5911f-361">**Key**</span><span class="sxs-lookup"><span data-stu-id="5911f-361">**Key**</span></span> | <span data-ttu-id="5911f-362">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="5911f-362">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="5911f-363">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5911f-363">**Data type**</span></span> | <span data-ttu-id="5911f-364">String</span><span class="sxs-lookup"><span data-stu-id="5911f-364">String</span></span> |
| <span data-ttu-id="5911f-365">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="5911f-365">**Possible values**</span></span> | <span data-ttu-id="5911f-366">10000 (既定値)。</span><span class="sxs-lookup"><span data-stu-id="5911f-366">10000 (default).</span></span> <span data-ttu-id="5911f-367">許可される値は、5000 アイテムから 15,000 アイテムまでです。</span><span class="sxs-lookup"><span data-stu-id="5911f-367">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="5911f-368">**コメント**</span><span class="sxs-lookup"><span data-stu-id="5911f-368">**Comments**</span></span> | <span data-ttu-id="5911f-369">エンドポイント バージョン 101.07.23 以上の Microsoft Defender で使用できます。</span><span class="sxs-lookup"><span data-stu-id="5911f-369">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="5911f-370">クラウドによる保護の基本設定</span><span class="sxs-lookup"><span data-stu-id="5911f-370">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="5911f-371">macOS 上の Microsoft Defender for Endpoint のクラウド駆動型保護機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="5911f-371">Configure the cloud-driven protection features of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="5911f-372">Section</span><span class="sxs-lookup"><span data-stu-id="5911f-372">Section</span></span>|<span data-ttu-id="5911f-373">値</span><span class="sxs-lookup"><span data-stu-id="5911f-373">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5911f-374">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="5911f-374">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5911f-375">**Key**</span><span class="sxs-lookup"><span data-stu-id="5911f-375">**Key**</span></span> | <span data-ttu-id="5911f-376">cloudService</span><span class="sxs-lookup"><span data-stu-id="5911f-376">cloudService</span></span> |
| <span data-ttu-id="5911f-377">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5911f-377">**Data type**</span></span> | <span data-ttu-id="5911f-378">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="5911f-378">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="5911f-379">**コメント**</span><span class="sxs-lookup"><span data-stu-id="5911f-379">**Comments**</span></span> | <span data-ttu-id="5911f-380">辞書の内容の説明については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5911f-380">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="5911f-381">クラウド配信の保護を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="5911f-381">Enable / disable cloud-delivered protection</span></span>

<span data-ttu-id="5911f-382">デバイスのクラウド配信保護を有効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="5911f-382">Specify whether to enable cloud-delivered protection the device or not.</span></span> <span data-ttu-id="5911f-383">サービスのセキュリティを向上させるために、この機能を有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5911f-383">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|<span data-ttu-id="5911f-384">Section</span><span class="sxs-lookup"><span data-stu-id="5911f-384">Section</span></span>|<span data-ttu-id="5911f-385">値</span><span class="sxs-lookup"><span data-stu-id="5911f-385">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5911f-386">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="5911f-386">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5911f-387">**Key**</span><span class="sxs-lookup"><span data-stu-id="5911f-387">**Key**</span></span> | <span data-ttu-id="5911f-388">enabled</span><span class="sxs-lookup"><span data-stu-id="5911f-388">enabled</span></span> |
| <span data-ttu-id="5911f-389">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5911f-389">**Data type**</span></span> | <span data-ttu-id="5911f-390">Boolean</span><span class="sxs-lookup"><span data-stu-id="5911f-390">Boolean</span></span> |
| <span data-ttu-id="5911f-391">**可能な値**</span><span class="sxs-lookup"><span data-stu-id="5911f-391">**Possible values**</span></span> | <span data-ttu-id="5911f-392">true (既定)</span><span class="sxs-lookup"><span data-stu-id="5911f-392">true (default)</span></span> <br/> <span data-ttu-id="5911f-393">false</span><span class="sxs-lookup"><span data-stu-id="5911f-393">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="5911f-394">診断コレクション レベル</span><span class="sxs-lookup"><span data-stu-id="5911f-394">Diagnostic collection level</span></span>

<span data-ttu-id="5911f-395">診断データは、Microsoft Defender for Endpoint を安全かつ最新の状態に保ち、問題を検出、診断、修正し、製品の改善を行う場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="5911f-395">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="5911f-396">この設定は、Microsoft Defender for Endpoint から Microsoft に送信される診断のレベルを決定します。</span><span class="sxs-lookup"><span data-stu-id="5911f-396">This setting determines the level of diagnostics sent by Microsoft Defender for Endpoint to Microsoft.</span></span>

|<span data-ttu-id="5911f-397">Section</span><span class="sxs-lookup"><span data-stu-id="5911f-397">Section</span></span>|<span data-ttu-id="5911f-398">値</span><span class="sxs-lookup"><span data-stu-id="5911f-398">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5911f-399">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="5911f-399">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5911f-400">**Key**</span><span class="sxs-lookup"><span data-stu-id="5911f-400">**Key**</span></span> | <span data-ttu-id="5911f-401">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="5911f-401">diagnosticLevel</span></span> |
| <span data-ttu-id="5911f-402">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5911f-402">**Data type**</span></span> | <span data-ttu-id="5911f-403">String</span><span class="sxs-lookup"><span data-stu-id="5911f-403">String</span></span> |
| <span data-ttu-id="5911f-404">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="5911f-404">**Possible values**</span></span> | <span data-ttu-id="5911f-405">省略可能 (既定)</span><span class="sxs-lookup"><span data-stu-id="5911f-405">optional (default)</span></span> <br/> <span data-ttu-id="5911f-406">必須</span><span class="sxs-lookup"><span data-stu-id="5911f-406">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="5911f-407">自動サンプル申請を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="5911f-407">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="5911f-408">疑わしいサンプル (脅威を含む可能性が高い) を Microsoft に送信するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="5911f-408">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="5911f-409">送信されたファイルに個人情報が含まれている可能性が高い場合は、メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5911f-409">You are prompted if the submitted file is likely to contain personal information.</span></span>

|<span data-ttu-id="5911f-410">Section</span><span class="sxs-lookup"><span data-stu-id="5911f-410">Section</span></span>|<span data-ttu-id="5911f-411">値</span><span class="sxs-lookup"><span data-stu-id="5911f-411">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5911f-412">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="5911f-412">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5911f-413">**Key**</span><span class="sxs-lookup"><span data-stu-id="5911f-413">**Key**</span></span> | <span data-ttu-id="5911f-414">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="5911f-414">automaticSampleSubmission</span></span> |
| <span data-ttu-id="5911f-415">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5911f-415">**Data type**</span></span> | <span data-ttu-id="5911f-416">Boolean</span><span class="sxs-lookup"><span data-stu-id="5911f-416">Boolean</span></span> |
| <span data-ttu-id="5911f-417">**可能な値**</span><span class="sxs-lookup"><span data-stu-id="5911f-417">**Possible values**</span></span> | <span data-ttu-id="5911f-418">true (既定)</span><span class="sxs-lookup"><span data-stu-id="5911f-418">true (default)</span></span> <br/> <span data-ttu-id="5911f-419">false</span><span class="sxs-lookup"><span data-stu-id="5911f-419">false</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="5911f-420">セキュリティ インテリジェンスの自動更新を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="5911f-420">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="5911f-421">セキュリティ インテリジェンスの更新プログラムが自動的にインストールされるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="5911f-421">Determines whether security intelligence updates are installed automatically:</span></span>

|<span data-ttu-id="5911f-422">Section</span><span class="sxs-lookup"><span data-stu-id="5911f-422">Section</span></span>|<span data-ttu-id="5911f-423">値</span><span class="sxs-lookup"><span data-stu-id="5911f-423">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5911f-424">**Key**</span><span class="sxs-lookup"><span data-stu-id="5911f-424">**Key**</span></span> | <span data-ttu-id="5911f-425">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="5911f-425">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="5911f-426">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5911f-426">**Data type**</span></span> | <span data-ttu-id="5911f-427">Boolean</span><span class="sxs-lookup"><span data-stu-id="5911f-427">Boolean</span></span> |
| <span data-ttu-id="5911f-428">**可能な値**</span><span class="sxs-lookup"><span data-stu-id="5911f-428">**Possible values**</span></span> | <span data-ttu-id="5911f-429">true (既定)</span><span class="sxs-lookup"><span data-stu-id="5911f-429">true (default)</span></span> <br/> <span data-ttu-id="5911f-430">false</span><span class="sxs-lookup"><span data-stu-id="5911f-430">false</span></span> |

### <a name="user-interface-preferences"></a><span data-ttu-id="5911f-431">ユーザー インターフェイスの基本設定</span><span class="sxs-lookup"><span data-stu-id="5911f-431">User interface preferences</span></span>

<span data-ttu-id="5911f-432">macOS 上の Microsoft Defender for Endpoint のユーザー インターフェイスの基本設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="5911f-432">Manage the preferences for the user interface of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="5911f-433">Section</span><span class="sxs-lookup"><span data-stu-id="5911f-433">Section</span></span>|<span data-ttu-id="5911f-434">値</span><span class="sxs-lookup"><span data-stu-id="5911f-434">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5911f-435">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="5911f-435">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5911f-436">**Key**</span><span class="sxs-lookup"><span data-stu-id="5911f-436">**Key**</span></span> | <span data-ttu-id="5911f-437">userInterface</span><span class="sxs-lookup"><span data-stu-id="5911f-437">userInterface</span></span> |
| <span data-ttu-id="5911f-438">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5911f-438">**Data type**</span></span> | <span data-ttu-id="5911f-439">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="5911f-439">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="5911f-440">**コメント**</span><span class="sxs-lookup"><span data-stu-id="5911f-440">**Comments**</span></span> | <span data-ttu-id="5911f-441">辞書の内容の説明については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5911f-441">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="show--hide-status-menu-icon"></a><span data-ttu-id="5911f-442">状態メニューアイコンの表示/非表示</span><span class="sxs-lookup"><span data-stu-id="5911f-442">Show / hide status menu icon</span></span>

<span data-ttu-id="5911f-443">画面の右上隅にある状態メニュー アイコンを表示または非表示にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="5911f-443">Specify whether to show or hide the status menu icon in the top-right corner of the screen.</span></span>

|<span data-ttu-id="5911f-444">Section</span><span class="sxs-lookup"><span data-stu-id="5911f-444">Section</span></span>|<span data-ttu-id="5911f-445">値</span><span class="sxs-lookup"><span data-stu-id="5911f-445">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5911f-446">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="5911f-446">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5911f-447">**Key**</span><span class="sxs-lookup"><span data-stu-id="5911f-447">**Key**</span></span> | <span data-ttu-id="5911f-448">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="5911f-448">hideStatusMenuIcon</span></span> |
| <span data-ttu-id="5911f-449">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5911f-449">**Data type**</span></span> | <span data-ttu-id="5911f-450">Boolean</span><span class="sxs-lookup"><span data-stu-id="5911f-450">Boolean</span></span> |
| <span data-ttu-id="5911f-451">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="5911f-451">**Possible values**</span></span> | <span data-ttu-id="5911f-452">false (既定)</span><span class="sxs-lookup"><span data-stu-id="5911f-452">false (default)</span></span> <br/> <span data-ttu-id="5911f-453">true</span><span class="sxs-lookup"><span data-stu-id="5911f-453">true</span></span> |

#### <a name="show--hide-option-to-send-feedback"></a><span data-ttu-id="5911f-454">フィードバックを送信するオプションを表示/非表示にする</span><span class="sxs-lookup"><span data-stu-id="5911f-454">Show / hide option to send feedback</span></span>

<span data-ttu-id="5911f-455">にアクセスしてユーザーが Microsoft にフィードバックを送信できるかどうかを指定します `Help`  >  `Send Feedback` 。</span><span class="sxs-lookup"><span data-stu-id="5911f-455">Specify whether users can submit feedback to Microsoft by going to `Help` > `Send Feedback`.</span></span>

|<span data-ttu-id="5911f-456">Section</span><span class="sxs-lookup"><span data-stu-id="5911f-456">Section</span></span>|<span data-ttu-id="5911f-457">値</span><span class="sxs-lookup"><span data-stu-id="5911f-457">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5911f-458">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="5911f-458">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5911f-459">**Key**</span><span class="sxs-lookup"><span data-stu-id="5911f-459">**Key**</span></span> | <span data-ttu-id="5911f-460">userInitiatedFeedback</span><span class="sxs-lookup"><span data-stu-id="5911f-460">userInitiatedFeedback</span></span> |
| <span data-ttu-id="5911f-461">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5911f-461">**Data type**</span></span> | <span data-ttu-id="5911f-462">String</span><span class="sxs-lookup"><span data-stu-id="5911f-462">String</span></span> |
| <span data-ttu-id="5911f-463">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="5911f-463">**Possible values**</span></span> | <span data-ttu-id="5911f-464">有効 (既定)</span><span class="sxs-lookup"><span data-stu-id="5911f-464">enabled (default)</span></span> <br/> <span data-ttu-id="5911f-465">disabled</span><span class="sxs-lookup"><span data-stu-id="5911f-465">disabled</span></span> |
| <span data-ttu-id="5911f-466">**コメント**</span><span class="sxs-lookup"><span data-stu-id="5911f-466">**Comments**</span></span> | <span data-ttu-id="5911f-467">Microsoft Defender for Endpoint version 101.19.61 以上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="5911f-467">Available in Microsoft Defender for Endpoint version 101.19.61 or higher.</span></span> |

### <a name="endpoint-detection-and-response-preferences"></a><span data-ttu-id="5911f-468">エンドポイントの検出と応答の基本設定</span><span class="sxs-lookup"><span data-stu-id="5911f-468">Endpoint detection and response preferences</span></span>

<span data-ttu-id="5911f-469">macOS 上の Microsoft Defender for Endpoint のエンドポイント検出および応答 (EDR) コンポーネントの基本設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="5911f-469">Manage the preferences of the endpoint detection and response (EDR) component of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="5911f-470">Section</span><span class="sxs-lookup"><span data-stu-id="5911f-470">Section</span></span>|<span data-ttu-id="5911f-471">値</span><span class="sxs-lookup"><span data-stu-id="5911f-471">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5911f-472">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="5911f-472">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5911f-473">**Key**</span><span class="sxs-lookup"><span data-stu-id="5911f-473">**Key**</span></span> | <span data-ttu-id="5911f-474">edr</span><span class="sxs-lookup"><span data-stu-id="5911f-474">edr</span></span> |
| <span data-ttu-id="5911f-475">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5911f-475">**Data type**</span></span> | <span data-ttu-id="5911f-476">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="5911f-476">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="5911f-477">**コメント**</span><span class="sxs-lookup"><span data-stu-id="5911f-477">**Comments**</span></span> | <span data-ttu-id="5911f-478">辞書の内容の説明については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5911f-478">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="device-tags"></a><span data-ttu-id="5911f-479">デバイス タグ</span><span class="sxs-lookup"><span data-stu-id="5911f-479">Device tags</span></span>

<span data-ttu-id="5911f-480">タグ名とその値を指定します。</span><span class="sxs-lookup"><span data-stu-id="5911f-480">Specify a tag name and its value.</span></span> 

- <span data-ttu-id="5911f-481">GROUP タグは、デバイスに指定された値をタグ付けします。</span><span class="sxs-lookup"><span data-stu-id="5911f-481">The GROUP tag, tags the device with the specified value.</span></span> <span data-ttu-id="5911f-482">タグは、デバイス ページの下のポータルに反映され、デバイスのフィルター処理とグループ化に使用できます。</span><span class="sxs-lookup"><span data-stu-id="5911f-482">The tag is reflected in the portal under the device page and can be used for filtering and grouping devices.</span></span>

|<span data-ttu-id="5911f-483">Section</span><span class="sxs-lookup"><span data-stu-id="5911f-483">Section</span></span>|<span data-ttu-id="5911f-484">値</span><span class="sxs-lookup"><span data-stu-id="5911f-484">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5911f-485">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="5911f-485">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5911f-486">**Key**</span><span class="sxs-lookup"><span data-stu-id="5911f-486">**Key**</span></span> | <span data-ttu-id="5911f-487">tags</span><span class="sxs-lookup"><span data-stu-id="5911f-487">tags</span></span> |
| <span data-ttu-id="5911f-488">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5911f-488">**Data type**</span></span> | <span data-ttu-id="5911f-489">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="5911f-489">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="5911f-490">**コメント**</span><span class="sxs-lookup"><span data-stu-id="5911f-490">**Comments**</span></span> | <span data-ttu-id="5911f-491">辞書の内容の説明については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5911f-491">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-tag"></a><span data-ttu-id="5911f-492">タグの種類</span><span class="sxs-lookup"><span data-stu-id="5911f-492">Type of tag</span></span>

<span data-ttu-id="5911f-493">タグの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="5911f-493">Specifies the type of tag</span></span>

|<span data-ttu-id="5911f-494">Section</span><span class="sxs-lookup"><span data-stu-id="5911f-494">Section</span></span>|<span data-ttu-id="5911f-495">値</span><span class="sxs-lookup"><span data-stu-id="5911f-495">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5911f-496">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="5911f-496">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5911f-497">**Key**</span><span class="sxs-lookup"><span data-stu-id="5911f-497">**Key**</span></span> | <span data-ttu-id="5911f-498">キー</span><span class="sxs-lookup"><span data-stu-id="5911f-498">key</span></span> |
| <span data-ttu-id="5911f-499">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5911f-499">**Data type**</span></span> | <span data-ttu-id="5911f-500">String</span><span class="sxs-lookup"><span data-stu-id="5911f-500">String</span></span> |
| <span data-ttu-id="5911f-501">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="5911f-501">**Possible values**</span></span> | `GROUP` |

##### <a name="value-of-tag"></a><span data-ttu-id="5911f-502">タグの値</span><span class="sxs-lookup"><span data-stu-id="5911f-502">Value of tag</span></span>

<span data-ttu-id="5911f-503">tag の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="5911f-503">Specifies the value of tag</span></span>

|<span data-ttu-id="5911f-504">Section</span><span class="sxs-lookup"><span data-stu-id="5911f-504">Section</span></span>|<span data-ttu-id="5911f-505">値</span><span class="sxs-lookup"><span data-stu-id="5911f-505">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5911f-506">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="5911f-506">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5911f-507">**Key**</span><span class="sxs-lookup"><span data-stu-id="5911f-507">**Key**</span></span> | <span data-ttu-id="5911f-508">値</span><span class="sxs-lookup"><span data-stu-id="5911f-508">value</span></span> |
| <span data-ttu-id="5911f-509">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5911f-509">**Data type**</span></span> | <span data-ttu-id="5911f-510">String</span><span class="sxs-lookup"><span data-stu-id="5911f-510">String</span></span> |
| <span data-ttu-id="5911f-511">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="5911f-511">**Possible values**</span></span> | <span data-ttu-id="5911f-512">任意の文字列</span><span class="sxs-lookup"><span data-stu-id="5911f-512">any string</span></span> |

> [!IMPORTANT]  
> - <span data-ttu-id="5911f-513">タグの種類ごとに設定できる値は 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="5911f-513">Only one value per tag type can be set.</span></span>
> - <span data-ttu-id="5911f-514">タグの種類は一意であり、同じ構成プロファイルで繰り返し使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5911f-514">Type of tags are unique, and should not be repeated in the same configuration profile.</span></span>

## <a name="recommended-configuration-profile"></a><span data-ttu-id="5911f-515">推奨される構成プロファイル</span><span class="sxs-lookup"><span data-stu-id="5911f-515">Recommended configuration profile</span></span>

<span data-ttu-id="5911f-516">開始するには、Microsoft Defender for Endpoint が提供するすべての保護機能を利用するために、企業の次の構成をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5911f-516">To get started, we recommend the following configuration for your enterprise to take advantage of all protection features that Microsoft Defender for Endpoint provides.</span></span>

<span data-ttu-id="5911f-517">次の構成プロファイル (JAMF の場合は、カスタム設定構成プロファイルにアップロードできるプロパティ リスト) は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5911f-517">The following configuration profile (or, in case of JAMF, a property list that could be uploaded into the custom settings configuration profile) will:</span></span>
- <span data-ttu-id="5911f-518">リアルタイム保護を有効にする (RTP)</span><span class="sxs-lookup"><span data-stu-id="5911f-518">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="5911f-519">次の脅威の種類の処理方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="5911f-519">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="5911f-520">**望ましくない可能性のあるアプリケーション (PUA) が** ブロックされる</span><span class="sxs-lookup"><span data-stu-id="5911f-520">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="5911f-521">**アーカイブボム** (圧縮率が高いファイル) が Microsoft Defender for Endpoint ログに監査される</span><span class="sxs-lookup"><span data-stu-id="5911f-521">**Archive bombs** (file with a high compression rate) are audited to Microsoft Defender for Endpoint logs</span></span>
- <span data-ttu-id="5911f-522">セキュリティ インテリジェンスの自動更新を有効にする</span><span class="sxs-lookup"><span data-stu-id="5911f-522">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="5911f-523">クラウドによる保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="5911f-523">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="5911f-524">自動サンプル申請を有効にする</span><span class="sxs-lookup"><span data-stu-id="5911f-524">Enable automatic sample submission</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="5911f-525">JAMF 構成プロファイルのプロパティ 一覧</span><span class="sxs-lookup"><span data-stu-id="5911f-525">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="5911f-526">Intune プロファイル</span><span class="sxs-lookup"><span data-stu-id="5911f-526">Intune profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="5911f-527">完全な構成プロファイルの例</span><span class="sxs-lookup"><span data-stu-id="5911f-527">Full configuration profile example</span></span>

<span data-ttu-id="5911f-528">次のテンプレートには、このドキュメントで説明されているすべての設定のエントリが含まれています。macOS の Microsoft Defender for Endpoint を詳細に制御する高度なシナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="5911f-528">The following templates contain entries for all settings described in this document and can be used for more advanced scenarios where you want more control over Microsoft Defender for Endpoint on macOS.</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="5911f-529">JAMF 構成プロファイルのプロパティ 一覧</span><span class="sxs-lookup"><span data-stu-id="5911f-529">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="5911f-530">Intune プロファイル</span><span class="sxs-lookup"><span data-stu-id="5911f-530">Intune profile</span></span>

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

## <a name="property-list-validation"></a><span data-ttu-id="5911f-531">プロパティ リストの検証</span><span class="sxs-lookup"><span data-stu-id="5911f-531">Property list validation</span></span>

<span data-ttu-id="5911f-532">プロパティ リストは、有効な *.plist ファイルである必要* があります。</span><span class="sxs-lookup"><span data-stu-id="5911f-532">The property list must be a valid *.plist* file.</span></span> <span data-ttu-id="5911f-533">これを確認するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5911f-533">This can be checked by executing:</span></span>

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

<span data-ttu-id="5911f-534">ファイルの形式が整っている場合、上記のコマンドは、 の終了 `OK` コードを出力して返します `0` 。</span><span class="sxs-lookup"><span data-stu-id="5911f-534">If the file is well-formed, the above command outputs `OK` and returns an exit code of `0`.</span></span> <span data-ttu-id="5911f-535">それ以外の場合は、問題を説明するエラーが表示され、コマンドは終了コードを返します `1` 。</span><span class="sxs-lookup"><span data-stu-id="5911f-535">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="5911f-536">構成プロファイルの展開</span><span class="sxs-lookup"><span data-stu-id="5911f-536">Configuration profile deployment</span></span>

<span data-ttu-id="5911f-537">エンタープライズの構成プロファイルを構築したら、企業が使用している管理コンソールを使用して展開できます。</span><span class="sxs-lookup"><span data-stu-id="5911f-537">Once you've built the configuration profile for your enterprise, you can deploy it through the management console that your enterprise is using.</span></span> <span data-ttu-id="5911f-538">以下のセクションでは、JAMF と Intune を使用してこのプロファイルを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5911f-538">The following sections provide instructions on how to deploy this profile using JAMF and Intune.</span></span>

### <a name="jamf-deployment"></a><span data-ttu-id="5911f-539">JAMF の展開</span><span class="sxs-lookup"><span data-stu-id="5911f-539">JAMF deployment</span></span>

<span data-ttu-id="5911f-540">JAMF コンソールで、[**コンピューター** 構成プロファイル] を開き、使用する構成プロファイルに移動し、[カスタム設定  >  ]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5911f-540">From the JAMF console, open **Computers** > **Configuration Profiles**, navigate to the configuration profile you'd like to use, then select **Custom Settings**.</span></span> <span data-ttu-id="5911f-541">優先ドメインとしてエントリ `com.microsoft.wdav` を作成し、前に作成した *.plist を* アップロードします。</span><span class="sxs-lookup"><span data-stu-id="5911f-541">Create an entry with `com.microsoft.wdav` as the preference domain and upload the *.plist* produced earlier.</span></span>

>[!CAUTION]
><span data-ttu-id="5911f-542">正しい基本設定ドメイン ( ) を入力する必要があります。それ以外の場合、設定は `com.microsoft.wdav` Microsoft Defender for Endpoint によって認識されません。</span><span class="sxs-lookup"><span data-stu-id="5911f-542">You must enter the correct preference domain (`com.microsoft.wdav`); otherwise, the preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

### <a name="intune-deployment"></a><span data-ttu-id="5911f-543">Intune の展開</span><span class="sxs-lookup"><span data-stu-id="5911f-543">Intune deployment</span></span>

1. <span data-ttu-id="5911f-544">[デバイス **構成**  >  **の管理] を開きます**。</span><span class="sxs-lookup"><span data-stu-id="5911f-544">Open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="5911f-545">[プロファイル **の**  >  **管理] [プロファイルの**  >  **作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5911f-545">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="5911f-546">プロファイルの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="5911f-546">Choose a name for the profile.</span></span> <span data-ttu-id="5911f-547">**Platform=macOS をプロファイル\*\*\*\*の種類=カスタム に変更します**。</span><span class="sxs-lookup"><span data-stu-id="5911f-547">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="5911f-548">[構成] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5911f-548">Select Configure.</span></span>

3. <span data-ttu-id="5911f-549">以前に作成した .plist を次のように保存します `com.microsoft.wdav.xml` 。</span><span class="sxs-lookup"><span data-stu-id="5911f-549">Save the .plist produced earlier as `com.microsoft.wdav.xml`.</span></span>

4. <span data-ttu-id="5911f-550">カスタム `com.microsoft.wdav` 構成プロファイル **名として入力します**。</span><span class="sxs-lookup"><span data-stu-id="5911f-550">Enter `com.microsoft.wdav` as the **custom configuration profile name**.</span></span>

5. <span data-ttu-id="5911f-551">構成プロファイルを開き、ファイルを `com.microsoft.wdav.xml` アップロードします。</span><span class="sxs-lookup"><span data-stu-id="5911f-551">Open the configuration profile and upload the `com.microsoft.wdav.xml` file.</span></span> <span data-ttu-id="5911f-552">(このファイルは手順 3 で作成されました。</span><span class="sxs-lookup"><span data-stu-id="5911f-552">(This file was created in step 3.)</span></span>

6. <span data-ttu-id="5911f-553">[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5911f-553">Select **OK**.</span></span>

7. <span data-ttu-id="5911f-554">[割 **り当**  >  **ての管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5911f-554">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="5911f-555">[含める **] タブ** で、[すべてのユーザーに割り当てる] & **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5911f-555">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

>[!CAUTION]
><span data-ttu-id="5911f-556">正しいカスタム構成プロファイル名を入力する必要があります。それ以外の場合、これらの基本設定は Microsoft Defender for Endpoint によって認識されません。</span><span class="sxs-lookup"><span data-stu-id="5911f-556">You must enter the correct custom configuration profile name; otherwise, these preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

## <a name="resources"></a><span data-ttu-id="5911f-557">リソース</span><span class="sxs-lookup"><span data-stu-id="5911f-557">Resources</span></span>

- [<span data-ttu-id="5911f-558">プロファイル構成リファレンス (Apple 開発者向けドキュメント)</span><span class="sxs-lookup"><span data-stu-id="5911f-558">Configuration Profile Reference (Apple developer documentation)</span></span>](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
