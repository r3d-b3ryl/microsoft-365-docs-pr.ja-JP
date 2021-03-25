---
title: Microsoft Defender ATP for Mac の基本設定を設定する
description: エンタープライズ組織で Microsoft Defender ATP for Mac を構成します。
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
ms.openlocfilehash: 578830d44a9a69c3ccafd78ceaf59ddfe100e43f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068892"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="ae78d-104">Microsoft Defender for Endpoint for Mac の基本設定を設定する</span><span class="sxs-lookup"><span data-stu-id="ae78d-104">Set preferences for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ae78d-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="ae78d-105">**Applies to:**</span></span>

- [<span data-ttu-id="ae78d-106">Microsoft Defender for Endpoint for Mac</span><span class="sxs-lookup"><span data-stu-id="ae78d-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
><span data-ttu-id="ae78d-107">この記事では、エンタープライズ組織で Microsoft Defender for Endpoint for Mac の基本設定を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ae78d-107">This article contains instructions for how to set preferences for Microsoft Defender for Endpoint for Mac in enterprise organizations.</span></span> <span data-ttu-id="ae78d-108">コマンド ライン インターフェイスを使用して Microsoft Defender for Endpoint for Mac を構成するには [、「Resources」を参照してください](mac-resources.md#configuring-from-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="ae78d-108">To configure Microsoft Defender for Endpoint for Mac using the command-line interface, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

## <a name="summary"></a><span data-ttu-id="ae78d-109">要約</span><span class="sxs-lookup"><span data-stu-id="ae78d-109">Summary</span></span>

<span data-ttu-id="ae78d-110">エンタープライズ組織では、Microsoft Defender for Endpoint for Mac は、いくつかの管理ツールのいずれかを使用して展開される構成プロファイルを介して管理できます。</span><span class="sxs-lookup"><span data-stu-id="ae78d-110">In enterprise organizations, Microsoft Defender for Endpoint for Mac can be managed through a configuration profile that is deployed by using one of several management tools.</span></span> <span data-ttu-id="ae78d-111">セキュリティ運用チームによって管理される基本設定は、デバイス上でローカルに設定されている基本設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="ae78d-111">Preferences that are managed by your security operations team take precedence over preferences that are set locally on the device.</span></span> <span data-ttu-id="ae78d-112">構成プロファイルを使用して設定される基本設定を変更するには、エスカレートされた特権が必要であり、管理アクセス許可のないユーザーでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="ae78d-112">Changing the preferences that are set through the configuration profile requires escalated privileges and is not available for users without administrative permissions.</span></span>

<span data-ttu-id="ae78d-113">この記事では、構成プロファイルの構造、開始に使用できる推奨プロファイル、およびプロファイルの展開方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ae78d-113">This article describes the structure of the configuration profile, includes a recommended profile that you can use to get started, and provides instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="ae78d-114">構成プロファイル構造</span><span class="sxs-lookup"><span data-stu-id="ae78d-114">Configuration profile structure</span></span>

<span data-ttu-id="ae78d-115">構成プロファイルは *.plist* ファイルで、キーによって識別されるエントリ (基本設定の名前を示す) で構成され、その後に、プリファレンスの性質に依存する値が続きます。</span><span class="sxs-lookup"><span data-stu-id="ae78d-115">The configuration profile is a *.plist* file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="ae78d-116">値は、単純な (数値など) か、入れ子になった基本設定リストなどの複雑な値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="ae78d-116">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

>[!CAUTION]
><span data-ttu-id="ae78d-117">構成プロファイルのレイアウトは、使用している管理コンソールによって異なります。</span><span class="sxs-lookup"><span data-stu-id="ae78d-117">The layout of the configuration profile depends on the management console that you are using.</span></span> <span data-ttu-id="ae78d-118">次のセクションでは、JAMF と Intune の構成プロファイルの例を示します。</span><span class="sxs-lookup"><span data-stu-id="ae78d-118">The following sections contain examples of configuration profiles for JAMF and Intune.</span></span>

<span data-ttu-id="ae78d-119">構成プロファイルのトップ レベルには、製品全体の基本設定と、Microsoft Defender for Endpoint のサブエリアのエントリが含まれています。これは、次のセクションで詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="ae78d-119">The top level of the configuration profile includes product-wide preferences and entries for subareas of Microsoft Defender for Endpoint, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="ae78d-120">ウイルス対策エンジンの基本設定</span><span class="sxs-lookup"><span data-stu-id="ae78d-120">Antivirus engine preferences</span></span>

<span data-ttu-id="ae78d-121">構成 *プロファイルの antivirusEngine* セクションは、Microsoft Defender for Endpoint のウイルス対策コンポーネントの基本設定を管理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ae78d-121">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of Microsoft Defender for Endpoint.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ae78d-122">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ae78d-122">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ae78d-123">**キー**</span><span class="sxs-lookup"><span data-stu-id="ae78d-123">**Key**</span></span> | <span data-ttu-id="ae78d-124">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="ae78d-124">antivirusEngine</span></span> |
| <span data-ttu-id="ae78d-125">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ae78d-125">**Data type**</span></span> | <span data-ttu-id="ae78d-126">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="ae78d-126">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="ae78d-127">**コメント**</span><span class="sxs-lookup"><span data-stu-id="ae78d-127">**Comments**</span></span> | <span data-ttu-id="ae78d-128">辞書の内容の説明については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae78d-128">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="ae78d-129">リアルタイム保護を有効/無効にする</span><span class="sxs-lookup"><span data-stu-id="ae78d-129">Enable / disable real-time protection</span></span>

<span data-ttu-id="ae78d-130">アクセス時にファイルをスキャンするリアルタイム保護を有効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="ae78d-130">Specify whether to enable real-time protection, which scans files as they are accessed.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ae78d-131">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ae78d-131">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ae78d-132">**キー**</span><span class="sxs-lookup"><span data-stu-id="ae78d-132">**Key**</span></span> | <span data-ttu-id="ae78d-133">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="ae78d-133">enableRealTimeProtection</span></span> |
| <span data-ttu-id="ae78d-134">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ae78d-134">**Data type**</span></span> | <span data-ttu-id="ae78d-135">Boolean</span><span class="sxs-lookup"><span data-stu-id="ae78d-135">Boolean</span></span> |
| <span data-ttu-id="ae78d-136">**可能な値**</span><span class="sxs-lookup"><span data-stu-id="ae78d-136">**Possible values**</span></span> | <span data-ttu-id="ae78d-137">true (既定)</span><span class="sxs-lookup"><span data-stu-id="ae78d-137">true (default)</span></span> <br/> <span data-ttu-id="ae78d-138">false</span><span class="sxs-lookup"><span data-stu-id="ae78d-138">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="ae78d-139">パッシブ モードを有効/無効にする</span><span class="sxs-lookup"><span data-stu-id="ae78d-139">Enable / disable passive mode</span></span>

<span data-ttu-id="ae78d-140">ウイルス対策エンジンをパッシブ モードで実行するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="ae78d-140">Specify whether the antivirus engine runs in passive mode.</span></span> <span data-ttu-id="ae78d-141">パッシブ モードには、次のような影響があります。</span><span class="sxs-lookup"><span data-stu-id="ae78d-141">Passive mode has the following implications:</span></span> 
- <span data-ttu-id="ae78d-142">リアルタイム保護がオフになっている</span><span class="sxs-lookup"><span data-stu-id="ae78d-142">Real-time protection is turned off</span></span>
- <span data-ttu-id="ae78d-143">オンデマンド スキャンが有効になっている</span><span class="sxs-lookup"><span data-stu-id="ae78d-143">On-demand scanning is turned on</span></span>
- <span data-ttu-id="ae78d-144">脅威の自動修復が無効になっている</span><span class="sxs-lookup"><span data-stu-id="ae78d-144">Automatic threat remediation is turned off</span></span>
- <span data-ttu-id="ae78d-145">セキュリティ インテリジェンスの更新プログラムが有効になっている</span><span class="sxs-lookup"><span data-stu-id="ae78d-145">Security intelligence updates are turned on</span></span>
- <span data-ttu-id="ae78d-146">[状態] メニュー アイコンが非表示</span><span class="sxs-lookup"><span data-stu-id="ae78d-146">Status menu icon is hidden</span></span>

|||
|:---|:---|
| <span data-ttu-id="ae78d-147">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ae78d-147">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ae78d-148">**キー**</span><span class="sxs-lookup"><span data-stu-id="ae78d-148">**Key**</span></span> | <span data-ttu-id="ae78d-149">passiveMode</span><span class="sxs-lookup"><span data-stu-id="ae78d-149">passiveMode</span></span> |
| <span data-ttu-id="ae78d-150">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ae78d-150">**Data type**</span></span> | <span data-ttu-id="ae78d-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="ae78d-151">Boolean</span></span> |
| <span data-ttu-id="ae78d-152">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="ae78d-152">**Possible values**</span></span> | <span data-ttu-id="ae78d-153">false (既定)</span><span class="sxs-lookup"><span data-stu-id="ae78d-153">false (default)</span></span> <br/> <span data-ttu-id="ae78d-154">true</span><span class="sxs-lookup"><span data-stu-id="ae78d-154">true</span></span> |
| <span data-ttu-id="ae78d-155">**コメント**</span><span class="sxs-lookup"><span data-stu-id="ae78d-155">**Comments**</span></span> | <span data-ttu-id="ae78d-156">Microsoft Defender for Endpoint version 100.67.60 以上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="ae78d-156">Available in Microsoft Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="ae78d-157">除外マージ ポリシー</span><span class="sxs-lookup"><span data-stu-id="ae78d-157">Exclusion merge policy</span></span>

<span data-ttu-id="ae78d-158">除外のマージ ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="ae78d-158">Specify the merge policy for exclusions.</span></span> <span data-ttu-id="ae78d-159">これには、管理者定義の除外とユーザー定義の除外 ( ) の組み合わせ、または管理者定義の除外 ( ) のみを `merge` 組み合わせて指定できます `admin_only` 。</span><span class="sxs-lookup"><span data-stu-id="ae78d-159">This can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="ae78d-160">この設定は、ローカル ユーザーが独自の除外を定義するのを制限するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="ae78d-160">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ae78d-161">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ae78d-161">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ae78d-162">**キー**</span><span class="sxs-lookup"><span data-stu-id="ae78d-162">**Key**</span></span> | <span data-ttu-id="ae78d-163">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="ae78d-163">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="ae78d-164">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ae78d-164">**Data type**</span></span> | <span data-ttu-id="ae78d-165">String</span><span class="sxs-lookup"><span data-stu-id="ae78d-165">String</span></span> |
| <span data-ttu-id="ae78d-166">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="ae78d-166">**Possible values**</span></span> | <span data-ttu-id="ae78d-167">merge (既定)</span><span class="sxs-lookup"><span data-stu-id="ae78d-167">merge (default)</span></span> <br/> <span data-ttu-id="ae78d-168">admin_only</span><span class="sxs-lookup"><span data-stu-id="ae78d-168">admin_only</span></span> |
| <span data-ttu-id="ae78d-169">**コメント**</span><span class="sxs-lookup"><span data-stu-id="ae78d-169">**Comments**</span></span> | <span data-ttu-id="ae78d-170">Microsoft Defender for Endpoint version 100.83.73 以上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="ae78d-170">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="ae78d-171">スキャンの除外</span><span class="sxs-lookup"><span data-stu-id="ae78d-171">Scan exclusions</span></span>

<span data-ttu-id="ae78d-172">スキャン対象から除外されるエンティティを指定します。</span><span class="sxs-lookup"><span data-stu-id="ae78d-172">Specify entities excluded from being scanned.</span></span> <span data-ttu-id="ae78d-173">除外は、完全パス、拡張子、またはファイル名で指定できます。</span><span class="sxs-lookup"><span data-stu-id="ae78d-173">Exclusions can be specified by full paths, extensions, or file names.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ae78d-174">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ae78d-174">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ae78d-175">**キー**</span><span class="sxs-lookup"><span data-stu-id="ae78d-175">**Key**</span></span> | <span data-ttu-id="ae78d-176">除外</span><span class="sxs-lookup"><span data-stu-id="ae78d-176">exclusions</span></span> |
| <span data-ttu-id="ae78d-177">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ae78d-177">**Data type**</span></span> | <span data-ttu-id="ae78d-178">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="ae78d-178">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="ae78d-179">**コメント**</span><span class="sxs-lookup"><span data-stu-id="ae78d-179">**Comments**</span></span> | <span data-ttu-id="ae78d-180">辞書の内容の説明については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae78d-180">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-exclusion"></a><span data-ttu-id="ae78d-181">除外の種類</span><span class="sxs-lookup"><span data-stu-id="ae78d-181">Type of exclusion</span></span>

<span data-ttu-id="ae78d-182">種類別にスキャン対象から除外されるコンテンツを指定します。</span><span class="sxs-lookup"><span data-stu-id="ae78d-182">Specify content excluded from being scanned by type.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ae78d-183">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ae78d-183">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ae78d-184">**キー**</span><span class="sxs-lookup"><span data-stu-id="ae78d-184">**Key**</span></span> | <span data-ttu-id="ae78d-185">$type</span><span class="sxs-lookup"><span data-stu-id="ae78d-185">$type</span></span> |
| <span data-ttu-id="ae78d-186">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ae78d-186">**Data type**</span></span> | <span data-ttu-id="ae78d-187">String</span><span class="sxs-lookup"><span data-stu-id="ae78d-187">String</span></span> |
| <span data-ttu-id="ae78d-188">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="ae78d-188">**Possible values**</span></span> | <span data-ttu-id="ae78d-189">excludedPath</span><span class="sxs-lookup"><span data-stu-id="ae78d-189">excludedPath</span></span> <br/> <span data-ttu-id="ae78d-190">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="ae78d-190">excludedFileExtension</span></span> <br/> <span data-ttu-id="ae78d-191">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="ae78d-191">excludedFileName</span></span> |

##### <a name="path-to-excluded-content"></a><span data-ttu-id="ae78d-192">除外されたコンテンツへのパス</span><span class="sxs-lookup"><span data-stu-id="ae78d-192">Path to excluded content</span></span>

<span data-ttu-id="ae78d-193">完全なファイル パスでスキャンされるコンテンツを除外するを指定します。</span><span class="sxs-lookup"><span data-stu-id="ae78d-193">Specify content excluded from being scanned by full file path.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ae78d-194">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ae78d-194">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ae78d-195">**キー**</span><span class="sxs-lookup"><span data-stu-id="ae78d-195">**Key**</span></span> | <span data-ttu-id="ae78d-196">path</span><span class="sxs-lookup"><span data-stu-id="ae78d-196">path</span></span> |
| <span data-ttu-id="ae78d-197">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ae78d-197">**Data type**</span></span> | <span data-ttu-id="ae78d-198">String</span><span class="sxs-lookup"><span data-stu-id="ae78d-198">String</span></span> |
| <span data-ttu-id="ae78d-199">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="ae78d-199">**Possible values**</span></span> | <span data-ttu-id="ae78d-200">有効なパス</span><span class="sxs-lookup"><span data-stu-id="ae78d-200">valid paths</span></span> |
| <span data-ttu-id="ae78d-201">**コメント**</span><span class="sxs-lookup"><span data-stu-id="ae78d-201">**Comments**</span></span> | <span data-ttu-id="ae78d-202">適用 *できるのは、$type\*\*が excludedPath である場合のみです。*</span><span class="sxs-lookup"><span data-stu-id="ae78d-202">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="path-type-file--directory"></a><span data-ttu-id="ae78d-203">パスの種類 (ファイル/ディレクトリ)</span><span class="sxs-lookup"><span data-stu-id="ae78d-203">Path type (file / directory)</span></span>

<span data-ttu-id="ae78d-204">path プロパティが *ファイル* またはディレクトリを参照しているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="ae78d-204">Indicate if the *path* property refers to a file or directory.</span></span> 

|||
|:---|:---|
| <span data-ttu-id="ae78d-205">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ae78d-205">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ae78d-206">**キー**</span><span class="sxs-lookup"><span data-stu-id="ae78d-206">**Key**</span></span> | <span data-ttu-id="ae78d-207">isDirectory</span><span class="sxs-lookup"><span data-stu-id="ae78d-207">isDirectory</span></span> |
| <span data-ttu-id="ae78d-208">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ae78d-208">**Data type**</span></span> | <span data-ttu-id="ae78d-209">Boolean</span><span class="sxs-lookup"><span data-stu-id="ae78d-209">Boolean</span></span> |
| <span data-ttu-id="ae78d-210">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="ae78d-210">**Possible values**</span></span> | <span data-ttu-id="ae78d-211">false (既定)</span><span class="sxs-lookup"><span data-stu-id="ae78d-211">false (default)</span></span> <br/> <span data-ttu-id="ae78d-212">true</span><span class="sxs-lookup"><span data-stu-id="ae78d-212">true</span></span> |
| <span data-ttu-id="ae78d-213">**コメント**</span><span class="sxs-lookup"><span data-stu-id="ae78d-213">**Comments**</span></span> | <span data-ttu-id="ae78d-214">適用 *できるのは、$type\*\*が excludedPath である場合のみです。*</span><span class="sxs-lookup"><span data-stu-id="ae78d-214">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="ae78d-215">スキャンから除外されたファイル拡張子</span><span class="sxs-lookup"><span data-stu-id="ae78d-215">File extension excluded from the scan</span></span>

<span data-ttu-id="ae78d-216">ファイル拡張子によるスキャン対象から除外されるコンテンツを指定します。</span><span class="sxs-lookup"><span data-stu-id="ae78d-216">Specify content excluded from being scanned by file extension.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ae78d-217">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ae78d-217">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ae78d-218">**キー**</span><span class="sxs-lookup"><span data-stu-id="ae78d-218">**Key**</span></span> | <span data-ttu-id="ae78d-219">拡張機能</span><span class="sxs-lookup"><span data-stu-id="ae78d-219">extension</span></span> |
| <span data-ttu-id="ae78d-220">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ae78d-220">**Data type**</span></span> | <span data-ttu-id="ae78d-221">String</span><span class="sxs-lookup"><span data-stu-id="ae78d-221">String</span></span> |
| <span data-ttu-id="ae78d-222">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="ae78d-222">**Possible values**</span></span> | <span data-ttu-id="ae78d-223">有効なファイル拡張子</span><span class="sxs-lookup"><span data-stu-id="ae78d-223">valid file extensions</span></span> |
| <span data-ttu-id="ae78d-224">**コメント**</span><span class="sxs-lookup"><span data-stu-id="ae78d-224">**Comments**</span></span> | <span data-ttu-id="ae78d-225">適用 *できるのは* 、$type FileExtension が *除外されている場合のみです。*</span><span class="sxs-lookup"><span data-stu-id="ae78d-225">Applicable only if *$type* is *excludedFileExtension*</span></span> |

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="ae78d-226">スキャンから除外されるプロセス</span><span class="sxs-lookup"><span data-stu-id="ae78d-226">Process excluded from the scan</span></span>

<span data-ttu-id="ae78d-227">すべてのファイル アクティビティがスキャンから除外されるプロセスを指定します。</span><span class="sxs-lookup"><span data-stu-id="ae78d-227">Specify a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="ae78d-228">プロセスは、名前 (例: ) または完全 `cat` パス (例: ) で指定できます `/bin/cat` 。</span><span class="sxs-lookup"><span data-stu-id="ae78d-228">The process can be specified either by its name (e.g. `cat`) or full path (e.g. `/bin/cat`).</span></span>

|||
|:---|:---|
| <span data-ttu-id="ae78d-229">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ae78d-229">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ae78d-230">**キー**</span><span class="sxs-lookup"><span data-stu-id="ae78d-230">**Key**</span></span> | <span data-ttu-id="ae78d-231">name</span><span class="sxs-lookup"><span data-stu-id="ae78d-231">name</span></span> |
| <span data-ttu-id="ae78d-232">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ae78d-232">**Data type**</span></span> | <span data-ttu-id="ae78d-233">String</span><span class="sxs-lookup"><span data-stu-id="ae78d-233">String</span></span> |
| <span data-ttu-id="ae78d-234">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="ae78d-234">**Possible values**</span></span> | <span data-ttu-id="ae78d-235">任意の文字列</span><span class="sxs-lookup"><span data-stu-id="ae78d-235">any string</span></span> |
| <span data-ttu-id="ae78d-236">**コメント**</span><span class="sxs-lookup"><span data-stu-id="ae78d-236">**Comments**</span></span> | <span data-ttu-id="ae78d-237">ファイルが excludedFileName *$type\*\*場合にのみ適用されます。*</span><span class="sxs-lookup"><span data-stu-id="ae78d-237">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="ae78d-238">許可される脅威</span><span class="sxs-lookup"><span data-stu-id="ae78d-238">Allowed threats</span></span>

<span data-ttu-id="ae78d-239">Defender for Endpoint for Mac でブロックされない脅威を名前で指定します。</span><span class="sxs-lookup"><span data-stu-id="ae78d-239">Specify threats by name that are not blocked by Defender for Endpoint for Mac.</span></span> <span data-ttu-id="ae78d-240">これらの脅威の実行が許可されます。</span><span class="sxs-lookup"><span data-stu-id="ae78d-240">These threats will be allowed to run.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ae78d-241">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ae78d-241">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ae78d-242">**キー**</span><span class="sxs-lookup"><span data-stu-id="ae78d-242">**Key**</span></span> | <span data-ttu-id="ae78d-243">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="ae78d-243">allowedThreats</span></span> |
| <span data-ttu-id="ae78d-244">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ae78d-244">**Data type**</span></span> | <span data-ttu-id="ae78d-245">文字列の配列</span><span class="sxs-lookup"><span data-stu-id="ae78d-245">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="ae78d-246">禁止された脅威アクション</span><span class="sxs-lookup"><span data-stu-id="ae78d-246">Disallowed threat actions</span></span>

<span data-ttu-id="ae78d-247">脅威が検出された場合にデバイスのローカル ユーザーが実行できるアクションを制限します。</span><span class="sxs-lookup"><span data-stu-id="ae78d-247">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="ae78d-248">この一覧に含まれるアクションは、ユーザー インターフェイスには表示されません。</span><span class="sxs-lookup"><span data-stu-id="ae78d-248">The actions included in this list are not displayed in the user interface.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ae78d-249">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ae78d-249">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ae78d-250">**キー**</span><span class="sxs-lookup"><span data-stu-id="ae78d-250">**Key**</span></span> | <span data-ttu-id="ae78d-251">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="ae78d-251">disallowedThreatActions</span></span> |
| <span data-ttu-id="ae78d-252">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ae78d-252">**Data type**</span></span> | <span data-ttu-id="ae78d-253">文字列の配列</span><span class="sxs-lookup"><span data-stu-id="ae78d-253">Array of strings</span></span> |
| <span data-ttu-id="ae78d-254">**可能な値**</span><span class="sxs-lookup"><span data-stu-id="ae78d-254">**Possible values**</span></span> | <span data-ttu-id="ae78d-255">allow (ユーザーによる脅威の許可を制限する)</span><span class="sxs-lookup"><span data-stu-id="ae78d-255">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="ae78d-256">復元 (検疫からの脅威の復元をユーザーに制限する)</span><span class="sxs-lookup"><span data-stu-id="ae78d-256">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="ae78d-257">**コメント**</span><span class="sxs-lookup"><span data-stu-id="ae78d-257">**Comments**</span></span> | <span data-ttu-id="ae78d-258">Microsoft Defender for Endpoint version 100.83.73 以上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="ae78d-258">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="ae78d-259">脅威の種類の設定</span><span class="sxs-lookup"><span data-stu-id="ae78d-259">Threat type settings</span></span>

<span data-ttu-id="ae78d-260">特定の脅威の種類を Microsoft Defender for Endpoint for Mac で処理する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="ae78d-260">Specify how certain threat types are handled by Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ae78d-261">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ae78d-261">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ae78d-262">**キー**</span><span class="sxs-lookup"><span data-stu-id="ae78d-262">**Key**</span></span> | <span data-ttu-id="ae78d-263">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="ae78d-263">threatTypeSettings</span></span> |
| <span data-ttu-id="ae78d-264">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ae78d-264">**Data type**</span></span> | <span data-ttu-id="ae78d-265">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="ae78d-265">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="ae78d-266">**コメント**</span><span class="sxs-lookup"><span data-stu-id="ae78d-266">**Comments**</span></span> | <span data-ttu-id="ae78d-267">辞書の内容の説明については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae78d-267">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="threat-type"></a><span data-ttu-id="ae78d-268">脅威の種類</span><span class="sxs-lookup"><span data-stu-id="ae78d-268">Threat type</span></span>

<span data-ttu-id="ae78d-269">脅威の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="ae78d-269">Specify threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ae78d-270">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ae78d-270">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ae78d-271">**キー**</span><span class="sxs-lookup"><span data-stu-id="ae78d-271">**Key**</span></span> | <span data-ttu-id="ae78d-272">キー</span><span class="sxs-lookup"><span data-stu-id="ae78d-272">key</span></span> |
| <span data-ttu-id="ae78d-273">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ae78d-273">**Data type**</span></span> | <span data-ttu-id="ae78d-274">String</span><span class="sxs-lookup"><span data-stu-id="ae78d-274">String</span></span> |
| <span data-ttu-id="ae78d-275">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="ae78d-275">**Possible values**</span></span> | <span data-ttu-id="ae78d-276">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="ae78d-276">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="ae78d-277">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="ae78d-277">archive_bomb</span></span> |

##### <a name="action-to-take"></a><span data-ttu-id="ae78d-278">実行する操作</span><span class="sxs-lookup"><span data-stu-id="ae78d-278">Action to take</span></span>

<span data-ttu-id="ae78d-279">前のセクションで指定した種類の脅威が検出された場合に実行するアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="ae78d-279">Specify what action to take when a threat of the type specified in the preceding section is detected.</span></span> <span data-ttu-id="ae78d-280">次のオプションから選択します。</span><span class="sxs-lookup"><span data-stu-id="ae78d-280">Choose from the following options:</span></span>

- <span data-ttu-id="ae78d-281">**監査**: デバイスは、この種類の脅威から保護されませんが、脅威に関するエントリがログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="ae78d-281">**Audit**: your device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="ae78d-282">**ブロック**: デバイスは、この種類の脅威から保護され、ユーザー インターフェイスとセキュリティ コンソールで通知されます。</span><span class="sxs-lookup"><span data-stu-id="ae78d-282">**Block**: your device is protected against this type of threat and you are notified in the user interface and the security console.</span></span>
- <span data-ttu-id="ae78d-283">**オフ**: デバイスは、この種類の脅威から保護され、何もログに記録されません。</span><span class="sxs-lookup"><span data-stu-id="ae78d-283">**Off**: your device is not protected against this type of threat and nothing is logged.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ae78d-284">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ae78d-284">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ae78d-285">**キー**</span><span class="sxs-lookup"><span data-stu-id="ae78d-285">**Key**</span></span> | <span data-ttu-id="ae78d-286">値</span><span class="sxs-lookup"><span data-stu-id="ae78d-286">value</span></span> |
| <span data-ttu-id="ae78d-287">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ae78d-287">**Data type**</span></span> | <span data-ttu-id="ae78d-288">String</span><span class="sxs-lookup"><span data-stu-id="ae78d-288">String</span></span> |
| <span data-ttu-id="ae78d-289">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="ae78d-289">**Possible values**</span></span> | <span data-ttu-id="ae78d-290">監査 (既定)</span><span class="sxs-lookup"><span data-stu-id="ae78d-290">audit (default)</span></span> <br/> <span data-ttu-id="ae78d-291">block</span><span class="sxs-lookup"><span data-stu-id="ae78d-291">block</span></span> <br/> <span data-ttu-id="ae78d-292">off</span><span class="sxs-lookup"><span data-stu-id="ae78d-292">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="ae78d-293">脅威の種類の設定の差し込みポリシー</span><span class="sxs-lookup"><span data-stu-id="ae78d-293">Threat type settings merge policy</span></span>

<span data-ttu-id="ae78d-294">脅威の種類の設定のマージ ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="ae78d-294">Specify the merge policy for threat type settings.</span></span> <span data-ttu-id="ae78d-295">これは、管理者定義設定とユーザー定義設定 ( ) の組み合わせか、管理者定義の設定 ( ) のみを `merge` 組み合わせて使用できます `admin_only` 。</span><span class="sxs-lookup"><span data-stu-id="ae78d-295">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="ae78d-296">この設定を使用すると、ローカル ユーザーがさまざまな脅威の種類に対して独自の設定を定義するのを制限できます。</span><span class="sxs-lookup"><span data-stu-id="ae78d-296">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ae78d-297">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ae78d-297">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ae78d-298">**キー**</span><span class="sxs-lookup"><span data-stu-id="ae78d-298">**Key**</span></span> | <span data-ttu-id="ae78d-299">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="ae78d-299">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="ae78d-300">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ae78d-300">**Data type**</span></span> | <span data-ttu-id="ae78d-301">String</span><span class="sxs-lookup"><span data-stu-id="ae78d-301">String</span></span> |
| <span data-ttu-id="ae78d-302">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="ae78d-302">**Possible values**</span></span> | <span data-ttu-id="ae78d-303">merge (既定)</span><span class="sxs-lookup"><span data-stu-id="ae78d-303">merge (default)</span></span> <br/> <span data-ttu-id="ae78d-304">admin_only</span><span class="sxs-lookup"><span data-stu-id="ae78d-304">admin_only</span></span> |
| <span data-ttu-id="ae78d-305">**コメント**</span><span class="sxs-lookup"><span data-stu-id="ae78d-305">**Comments**</span></span> | <span data-ttu-id="ae78d-306">Microsoft Defender for Endpoint version 100.83.73 以上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="ae78d-306">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="ae78d-307">ウイルス対策スキャン履歴の保持 (日数)</span><span class="sxs-lookup"><span data-stu-id="ae78d-307">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="ae78d-308">デバイスのスキャン履歴に結果が保持される日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="ae78d-308">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="ae78d-309">古いスキャン結果は履歴から削除されます。</span><span class="sxs-lookup"><span data-stu-id="ae78d-309">Old scan results are removed from the history.</span></span> <span data-ttu-id="ae78d-310">ディスクから削除された古い検疫済みファイル。</span><span class="sxs-lookup"><span data-stu-id="ae78d-310">Old quarantined files that are also removed from the disk.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ae78d-311">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ae78d-311">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ae78d-312">**キー**</span><span class="sxs-lookup"><span data-stu-id="ae78d-312">**Key**</span></span> | <span data-ttu-id="ae78d-313">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="ae78d-313">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="ae78d-314">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ae78d-314">**Data type**</span></span> | <span data-ttu-id="ae78d-315">String</span><span class="sxs-lookup"><span data-stu-id="ae78d-315">String</span></span> |
| <span data-ttu-id="ae78d-316">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="ae78d-316">**Possible values**</span></span> | <span data-ttu-id="ae78d-317">90 (既定)。</span><span class="sxs-lookup"><span data-stu-id="ae78d-317">90 (default).</span></span> <span data-ttu-id="ae78d-318">使用できる値は、1 日から 180 日です。</span><span class="sxs-lookup"><span data-stu-id="ae78d-318">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="ae78d-319">**コメント**</span><span class="sxs-lookup"><span data-stu-id="ae78d-319">**Comments**</span></span> | <span data-ttu-id="ae78d-320">エンドポイント バージョン 101.07.23 以上の Microsoft Defender で使用できます。</span><span class="sxs-lookup"><span data-stu-id="ae78d-320">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="ae78d-321">ウイルス対策スキャン履歴内のアイテムの最大数</span><span class="sxs-lookup"><span data-stu-id="ae78d-321">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="ae78d-322">スキャン履歴に保持するエントリの最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="ae78d-322">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="ae78d-323">エントリには、過去に実行されたオンデマンド スキャンとすべてのウイルス対策検出が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ae78d-323">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ae78d-324">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ae78d-324">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ae78d-325">**キー**</span><span class="sxs-lookup"><span data-stu-id="ae78d-325">**Key**</span></span> | <span data-ttu-id="ae78d-326">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="ae78d-326">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="ae78d-327">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ae78d-327">**Data type**</span></span> | <span data-ttu-id="ae78d-328">String</span><span class="sxs-lookup"><span data-stu-id="ae78d-328">String</span></span> |
| <span data-ttu-id="ae78d-329">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="ae78d-329">**Possible values**</span></span> | <span data-ttu-id="ae78d-330">10000 (既定値)。</span><span class="sxs-lookup"><span data-stu-id="ae78d-330">10000 (default).</span></span> <span data-ttu-id="ae78d-331">許可される値は、5000 アイテムから 15,000 アイテムまでです。</span><span class="sxs-lookup"><span data-stu-id="ae78d-331">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="ae78d-332">**コメント**</span><span class="sxs-lookup"><span data-stu-id="ae78d-332">**Comments**</span></span> | <span data-ttu-id="ae78d-333">エンドポイント バージョン 101.07.23 以上の Microsoft Defender で使用できます。</span><span class="sxs-lookup"><span data-stu-id="ae78d-333">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="ae78d-334">クラウドによる保護の基本設定</span><span class="sxs-lookup"><span data-stu-id="ae78d-334">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="ae78d-335">Microsoft Defender for Endpoint for Mac のクラウド駆動型保護機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="ae78d-335">Configure the cloud-driven protection features of Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ae78d-336">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ae78d-336">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ae78d-337">**キー**</span><span class="sxs-lookup"><span data-stu-id="ae78d-337">**Key**</span></span> | <span data-ttu-id="ae78d-338">cloudService</span><span class="sxs-lookup"><span data-stu-id="ae78d-338">cloudService</span></span> |
| <span data-ttu-id="ae78d-339">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ae78d-339">**Data type**</span></span> | <span data-ttu-id="ae78d-340">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="ae78d-340">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="ae78d-341">**コメント**</span><span class="sxs-lookup"><span data-stu-id="ae78d-341">**Comments**</span></span> | <span data-ttu-id="ae78d-342">辞書の内容の説明については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae78d-342">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="ae78d-343">クラウド配信の保護を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="ae78d-343">Enable / disable cloud-delivered protection</span></span>

<span data-ttu-id="ae78d-344">デバイスのクラウド配信保護を有効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="ae78d-344">Specify whether to enable cloud-delivered protection the device or not.</span></span> <span data-ttu-id="ae78d-345">サービスのセキュリティを向上させるために、この機能を有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ae78d-345">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ae78d-346">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ae78d-346">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ae78d-347">**キー**</span><span class="sxs-lookup"><span data-stu-id="ae78d-347">**Key**</span></span> | <span data-ttu-id="ae78d-348">enabled</span><span class="sxs-lookup"><span data-stu-id="ae78d-348">enabled</span></span> |
| <span data-ttu-id="ae78d-349">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ae78d-349">**Data type**</span></span> | <span data-ttu-id="ae78d-350">Boolean</span><span class="sxs-lookup"><span data-stu-id="ae78d-350">Boolean</span></span> |
| <span data-ttu-id="ae78d-351">**可能な値**</span><span class="sxs-lookup"><span data-stu-id="ae78d-351">**Possible values**</span></span> | <span data-ttu-id="ae78d-352">true (既定)</span><span class="sxs-lookup"><span data-stu-id="ae78d-352">true (default)</span></span> <br/> <span data-ttu-id="ae78d-353">false</span><span class="sxs-lookup"><span data-stu-id="ae78d-353">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="ae78d-354">診断コレクション レベル</span><span class="sxs-lookup"><span data-stu-id="ae78d-354">Diagnostic collection level</span></span>

<span data-ttu-id="ae78d-355">診断データは、Microsoft Defender for Endpoint を安全かつ最新の状態に保ち、問題を検出、診断、修正し、製品の改善を行う場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="ae78d-355">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="ae78d-356">この設定は、Microsoft Defender for Endpoint から Microsoft に送信される診断のレベルを決定します。</span><span class="sxs-lookup"><span data-stu-id="ae78d-356">This setting determines the level of diagnostics sent by Microsoft Defender for Endpoint to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ae78d-357">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ae78d-357">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ae78d-358">**キー**</span><span class="sxs-lookup"><span data-stu-id="ae78d-358">**Key**</span></span> | <span data-ttu-id="ae78d-359">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="ae78d-359">diagnosticLevel</span></span> |
| <span data-ttu-id="ae78d-360">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ae78d-360">**Data type**</span></span> | <span data-ttu-id="ae78d-361">String</span><span class="sxs-lookup"><span data-stu-id="ae78d-361">String</span></span> |
| <span data-ttu-id="ae78d-362">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="ae78d-362">**Possible values**</span></span> | <span data-ttu-id="ae78d-363">省略可能 (既定)</span><span class="sxs-lookup"><span data-stu-id="ae78d-363">optional (default)</span></span> <br/> <span data-ttu-id="ae78d-364">必須</span><span class="sxs-lookup"><span data-stu-id="ae78d-364">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="ae78d-365">自動サンプル申請を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="ae78d-365">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="ae78d-366">疑わしいサンプル (脅威を含む可能性が高い) を Microsoft に送信するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="ae78d-366">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="ae78d-367">送信されたファイルに個人情報が含まれている可能性が高い場合は、メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae78d-367">You are prompted if the submitted file is likely to contain personal information.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ae78d-368">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ae78d-368">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ae78d-369">**キー**</span><span class="sxs-lookup"><span data-stu-id="ae78d-369">**Key**</span></span> | <span data-ttu-id="ae78d-370">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="ae78d-370">automaticSampleSubmission</span></span> |
| <span data-ttu-id="ae78d-371">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ae78d-371">**Data type**</span></span> | <span data-ttu-id="ae78d-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="ae78d-372">Boolean</span></span> |
| <span data-ttu-id="ae78d-373">**可能な値**</span><span class="sxs-lookup"><span data-stu-id="ae78d-373">**Possible values**</span></span> | <span data-ttu-id="ae78d-374">true (既定)</span><span class="sxs-lookup"><span data-stu-id="ae78d-374">true (default)</span></span> <br/> <span data-ttu-id="ae78d-375">false</span><span class="sxs-lookup"><span data-stu-id="ae78d-375">false</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="ae78d-376">セキュリティ インテリジェンスの自動更新を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="ae78d-376">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="ae78d-377">セキュリティ インテリジェンスの更新プログラムが自動的にインストールされるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="ae78d-377">Determines whether security intelligence updates are installed automatically:</span></span>

|||
|:---|:---|
| <span data-ttu-id="ae78d-378">**キー**</span><span class="sxs-lookup"><span data-stu-id="ae78d-378">**Key**</span></span> | <span data-ttu-id="ae78d-379">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="ae78d-379">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="ae78d-380">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ae78d-380">**Data type**</span></span> | <span data-ttu-id="ae78d-381">Boolean</span><span class="sxs-lookup"><span data-stu-id="ae78d-381">Boolean</span></span> |
| <span data-ttu-id="ae78d-382">**可能な値**</span><span class="sxs-lookup"><span data-stu-id="ae78d-382">**Possible values**</span></span> | <span data-ttu-id="ae78d-383">true (既定)</span><span class="sxs-lookup"><span data-stu-id="ae78d-383">true (default)</span></span> <br/> <span data-ttu-id="ae78d-384">false</span><span class="sxs-lookup"><span data-stu-id="ae78d-384">false</span></span> |

### <a name="user-interface-preferences"></a><span data-ttu-id="ae78d-385">ユーザー インターフェイスの基本設定</span><span class="sxs-lookup"><span data-stu-id="ae78d-385">User interface preferences</span></span>

<span data-ttu-id="ae78d-386">Microsoft Defender for Endpoint for Mac のユーザー インターフェイスの基本設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="ae78d-386">Manage the preferences for the user interface of Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ae78d-387">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ae78d-387">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ae78d-388">**キー**</span><span class="sxs-lookup"><span data-stu-id="ae78d-388">**Key**</span></span> | <span data-ttu-id="ae78d-389">userInterface</span><span class="sxs-lookup"><span data-stu-id="ae78d-389">userInterface</span></span> |
| <span data-ttu-id="ae78d-390">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ae78d-390">**Data type**</span></span> | <span data-ttu-id="ae78d-391">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="ae78d-391">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="ae78d-392">**コメント**</span><span class="sxs-lookup"><span data-stu-id="ae78d-392">**Comments**</span></span> | <span data-ttu-id="ae78d-393">辞書の内容の説明については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae78d-393">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="show--hide-status-menu-icon"></a><span data-ttu-id="ae78d-394">状態メニューアイコンの表示/非表示</span><span class="sxs-lookup"><span data-stu-id="ae78d-394">Show / hide status menu icon</span></span>

<span data-ttu-id="ae78d-395">画面の右上隅にある状態メニュー アイコンを表示または非表示にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="ae78d-395">Specify whether to show or hide the status menu icon in the top-right corner of the screen.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ae78d-396">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ae78d-396">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ae78d-397">**キー**</span><span class="sxs-lookup"><span data-stu-id="ae78d-397">**Key**</span></span> | <span data-ttu-id="ae78d-398">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="ae78d-398">hideStatusMenuIcon</span></span> |
| <span data-ttu-id="ae78d-399">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ae78d-399">**Data type**</span></span> | <span data-ttu-id="ae78d-400">Boolean</span><span class="sxs-lookup"><span data-stu-id="ae78d-400">Boolean</span></span> |
| <span data-ttu-id="ae78d-401">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="ae78d-401">**Possible values**</span></span> | <span data-ttu-id="ae78d-402">false (既定)</span><span class="sxs-lookup"><span data-stu-id="ae78d-402">false (default)</span></span> <br/> <span data-ttu-id="ae78d-403">true</span><span class="sxs-lookup"><span data-stu-id="ae78d-403">true</span></span> |

#### <a name="show--hide-option-to-send-feedback"></a><span data-ttu-id="ae78d-404">フィードバックを送信するオプションを表示/非表示にする</span><span class="sxs-lookup"><span data-stu-id="ae78d-404">Show / hide option to send feedback</span></span>

<span data-ttu-id="ae78d-405">にアクセスしてユーザーが Microsoft にフィードバックを送信できるかどうかを指定します `Help`  >  `Send Feedback` 。</span><span class="sxs-lookup"><span data-stu-id="ae78d-405">Specify whether users can submit feedback to Microsoft by going to `Help` > `Send Feedback`.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ae78d-406">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ae78d-406">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ae78d-407">**キー**</span><span class="sxs-lookup"><span data-stu-id="ae78d-407">**Key**</span></span> | <span data-ttu-id="ae78d-408">userInitiatedFeedback</span><span class="sxs-lookup"><span data-stu-id="ae78d-408">userInitiatedFeedback</span></span> |
| <span data-ttu-id="ae78d-409">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ae78d-409">**Data type**</span></span> | <span data-ttu-id="ae78d-410">String</span><span class="sxs-lookup"><span data-stu-id="ae78d-410">String</span></span> |
| <span data-ttu-id="ae78d-411">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="ae78d-411">**Possible values**</span></span> | <span data-ttu-id="ae78d-412">有効 (既定)</span><span class="sxs-lookup"><span data-stu-id="ae78d-412">enabled (default)</span></span> <br/> <span data-ttu-id="ae78d-413">disabled</span><span class="sxs-lookup"><span data-stu-id="ae78d-413">disabled</span></span> |
| <span data-ttu-id="ae78d-414">**コメント**</span><span class="sxs-lookup"><span data-stu-id="ae78d-414">**Comments**</span></span> | <span data-ttu-id="ae78d-415">Microsoft Defender for Endpoint version 101.19.61 以上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="ae78d-415">Available in Microsoft Defender for Endpoint version 101.19.61 or higher.</span></span> |

### <a name="endpoint-detection-and-response-preferences"></a><span data-ttu-id="ae78d-416">エンドポイントの検出と応答の基本設定</span><span class="sxs-lookup"><span data-stu-id="ae78d-416">Endpoint detection and response preferences</span></span>

<span data-ttu-id="ae78d-417">Microsoft Defender for Endpoint for Mac のエンドポイント検出および応答 (EDR) コンポーネントの基本設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="ae78d-417">Manage the preferences of the endpoint detection and response (EDR) component of Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ae78d-418">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ae78d-418">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ae78d-419">**キー**</span><span class="sxs-lookup"><span data-stu-id="ae78d-419">**Key**</span></span> | <span data-ttu-id="ae78d-420">edr</span><span class="sxs-lookup"><span data-stu-id="ae78d-420">edr</span></span> |
| <span data-ttu-id="ae78d-421">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ae78d-421">**Data type**</span></span> | <span data-ttu-id="ae78d-422">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="ae78d-422">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="ae78d-423">**コメント**</span><span class="sxs-lookup"><span data-stu-id="ae78d-423">**Comments**</span></span> | <span data-ttu-id="ae78d-424">辞書の内容の説明については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae78d-424">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="device-tags"></a><span data-ttu-id="ae78d-425">デバイス タグ</span><span class="sxs-lookup"><span data-stu-id="ae78d-425">Device tags</span></span>

<span data-ttu-id="ae78d-426">タグ名とその値を指定します。</span><span class="sxs-lookup"><span data-stu-id="ae78d-426">Specify a tag name and its value.</span></span> 

- <span data-ttu-id="ae78d-427">GROUP タグは、デバイスに指定された値をタグ付けします。</span><span class="sxs-lookup"><span data-stu-id="ae78d-427">The GROUP tag, tags the device with the specified value.</span></span> <span data-ttu-id="ae78d-428">タグは、デバイス ページの下のポータルに反映され、デバイスのフィルター処理とグループ化に使用できます。</span><span class="sxs-lookup"><span data-stu-id="ae78d-428">The tag is reflected in the portal under the device page and can be used for filtering and grouping devices.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ae78d-429">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ae78d-429">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ae78d-430">**キー**</span><span class="sxs-lookup"><span data-stu-id="ae78d-430">**Key**</span></span> | <span data-ttu-id="ae78d-431">tags</span><span class="sxs-lookup"><span data-stu-id="ae78d-431">tags</span></span> |
| <span data-ttu-id="ae78d-432">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ae78d-432">**Data type**</span></span> | <span data-ttu-id="ae78d-433">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="ae78d-433">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="ae78d-434">**コメント**</span><span class="sxs-lookup"><span data-stu-id="ae78d-434">**Comments**</span></span> | <span data-ttu-id="ae78d-435">辞書の内容の説明については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae78d-435">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-tag"></a><span data-ttu-id="ae78d-436">タグの種類</span><span class="sxs-lookup"><span data-stu-id="ae78d-436">Type of tag</span></span>

<span data-ttu-id="ae78d-437">タグの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="ae78d-437">Specifies the type of tag</span></span>

|||
|:---|:---|
| <span data-ttu-id="ae78d-438">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ae78d-438">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ae78d-439">**キー**</span><span class="sxs-lookup"><span data-stu-id="ae78d-439">**Key**</span></span> | <span data-ttu-id="ae78d-440">キー</span><span class="sxs-lookup"><span data-stu-id="ae78d-440">key</span></span> |
| <span data-ttu-id="ae78d-441">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ae78d-441">**Data type**</span></span> | <span data-ttu-id="ae78d-442">String</span><span class="sxs-lookup"><span data-stu-id="ae78d-442">String</span></span> |
| <span data-ttu-id="ae78d-443">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="ae78d-443">**Possible values**</span></span> | `GROUP` |

##### <a name="value-of-tag"></a><span data-ttu-id="ae78d-444">タグの値</span><span class="sxs-lookup"><span data-stu-id="ae78d-444">Value of tag</span></span>

<span data-ttu-id="ae78d-445">tag の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="ae78d-445">Specifies the value of tag</span></span>

|||
|:---|:---|
| <span data-ttu-id="ae78d-446">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ae78d-446">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ae78d-447">**キー**</span><span class="sxs-lookup"><span data-stu-id="ae78d-447">**Key**</span></span> | <span data-ttu-id="ae78d-448">値</span><span class="sxs-lookup"><span data-stu-id="ae78d-448">value</span></span> |
| <span data-ttu-id="ae78d-449">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ae78d-449">**Data type**</span></span> | <span data-ttu-id="ae78d-450">String</span><span class="sxs-lookup"><span data-stu-id="ae78d-450">String</span></span> |
| <span data-ttu-id="ae78d-451">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="ae78d-451">**Possible values**</span></span> | <span data-ttu-id="ae78d-452">任意の文字列</span><span class="sxs-lookup"><span data-stu-id="ae78d-452">any string</span></span> |

> [!IMPORTANT]  
> - <span data-ttu-id="ae78d-453">タグの種類ごとに設定できる値は 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="ae78d-453">Only one value per tag type can be set.</span></span>
> - <span data-ttu-id="ae78d-454">タグの種類は一意であり、同じ構成プロファイルで繰り返し使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae78d-454">Type of tags are unique, and should not be repeated in the same configuration profile.</span></span>

## <a name="recommended-configuration-profile"></a><span data-ttu-id="ae78d-455">推奨される構成プロファイル</span><span class="sxs-lookup"><span data-stu-id="ae78d-455">Recommended configuration profile</span></span>

<span data-ttu-id="ae78d-456">開始するには、Microsoft Defender for Endpoint が提供するすべての保護機能を利用するために、企業の次の構成をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ae78d-456">To get started, we recommend the following configuration for your enterprise to take advantage of all protection features that Microsoft Defender for Endpoint provides.</span></span>

<span data-ttu-id="ae78d-457">次の構成プロファイル (JAMF の場合は、カスタム設定構成プロファイルにアップロードできるプロパティ リスト) は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ae78d-457">The following configuration profile (or, in case of JAMF, a property list that could be uploaded into the custom settings configuration profile) will:</span></span>
- <span data-ttu-id="ae78d-458">リアルタイム保護を有効にする (RTP)</span><span class="sxs-lookup"><span data-stu-id="ae78d-458">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="ae78d-459">次の脅威の種類の処理方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="ae78d-459">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="ae78d-460">**望ましくない可能性のあるアプリケーション (PUA) が** ブロックされる</span><span class="sxs-lookup"><span data-stu-id="ae78d-460">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="ae78d-461">**アーカイブボム** (圧縮率が高いファイル) が Microsoft Defender for Endpoint ログに監査される</span><span class="sxs-lookup"><span data-stu-id="ae78d-461">**Archive bombs** (file with a high compression rate) are audited to Microsoft Defender for Endpoint logs</span></span>
- <span data-ttu-id="ae78d-462">セキュリティ インテリジェンスの自動更新を有効にする</span><span class="sxs-lookup"><span data-stu-id="ae78d-462">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="ae78d-463">クラウドによる保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="ae78d-463">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="ae78d-464">自動サンプル申請を有効にする</span><span class="sxs-lookup"><span data-stu-id="ae78d-464">Enable automatic sample submission</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="ae78d-465">JAMF 構成プロファイルのプロパティ 一覧</span><span class="sxs-lookup"><span data-stu-id="ae78d-465">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="ae78d-466">Intune プロファイル</span><span class="sxs-lookup"><span data-stu-id="ae78d-466">Intune profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="ae78d-467">完全な構成プロファイルの例</span><span class="sxs-lookup"><span data-stu-id="ae78d-467">Full configuration profile example</span></span>

<span data-ttu-id="ae78d-468">次のテンプレートには、このドキュメントで説明されているすべての設定のエントリが含まれています。Microsoft Defender for Endpoint for Mac を詳細に制御する高度なシナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="ae78d-468">The following templates contain entries for all settings described in this document and can be used for more advanced scenarios where you want more control over Microsoft Defender for Endpoint for Mac.</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="ae78d-469">JAMF 構成プロファイルのプロパティ 一覧</span><span class="sxs-lookup"><span data-stu-id="ae78d-469">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="ae78d-470">Intune プロファイル</span><span class="sxs-lookup"><span data-stu-id="ae78d-470">Intune profile</span></span>

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

## <a name="property-list-validation"></a><span data-ttu-id="ae78d-471">プロパティ リストの検証</span><span class="sxs-lookup"><span data-stu-id="ae78d-471">Property list validation</span></span>

<span data-ttu-id="ae78d-472">プロパティ リストは、有効な *.plist ファイルである必要* があります。</span><span class="sxs-lookup"><span data-stu-id="ae78d-472">The property list must be a valid *.plist* file.</span></span> <span data-ttu-id="ae78d-473">これを確認するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ae78d-473">This can be checked by executing:</span></span>

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

<span data-ttu-id="ae78d-474">ファイルの形式が整っている場合、上記のコマンドは、 の終了 `OK` コードを出力して返します `0` 。</span><span class="sxs-lookup"><span data-stu-id="ae78d-474">If the file is well-formed, the above command outputs `OK` and returns an exit code of `0`.</span></span> <span data-ttu-id="ae78d-475">それ以外の場合は、問題を説明するエラーが表示され、コマンドは終了コードを返します `1` 。</span><span class="sxs-lookup"><span data-stu-id="ae78d-475">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="ae78d-476">構成プロファイルの展開</span><span class="sxs-lookup"><span data-stu-id="ae78d-476">Configuration profile deployment</span></span>

<span data-ttu-id="ae78d-477">エンタープライズの構成プロファイルを構築したら、企業が使用している管理コンソールを使用して展開できます。</span><span class="sxs-lookup"><span data-stu-id="ae78d-477">Once you've built the configuration profile for your enterprise, you can deploy it through the management console that your enterprise is using.</span></span> <span data-ttu-id="ae78d-478">以下のセクションでは、JAMF と Intune を使用してこのプロファイルを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ae78d-478">The following sections provide instructions on how to deploy this profile using JAMF and Intune.</span></span>

### <a name="jamf-deployment"></a><span data-ttu-id="ae78d-479">JAMF の展開</span><span class="sxs-lookup"><span data-stu-id="ae78d-479">JAMF deployment</span></span>

<span data-ttu-id="ae78d-480">JAMF コンソールで、[**コンピューター** 構成プロファイル] を開き、使用する構成プロファイルに移動し、[カスタム設定  >  ]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ae78d-480">From the JAMF console, open **Computers** > **Configuration Profiles**, navigate to the configuration profile you'd like to use, then select **Custom Settings**.</span></span> <span data-ttu-id="ae78d-481">優先ドメインとしてエントリ `com.microsoft.wdav` を作成し、前に作成した *.plist を* アップロードします。</span><span class="sxs-lookup"><span data-stu-id="ae78d-481">Create an entry with `com.microsoft.wdav` as the preference domain and upload the *.plist* produced earlier.</span></span>

>[!CAUTION]
><span data-ttu-id="ae78d-482">正しい基本設定ドメイン ( ) を入力する必要があります。それ以外の場合、設定は `com.microsoft.wdav` Microsoft Defender for Endpoint によって認識されません。</span><span class="sxs-lookup"><span data-stu-id="ae78d-482">You must enter the correct preference domain (`com.microsoft.wdav`); otherwise, the preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

### <a name="intune-deployment"></a><span data-ttu-id="ae78d-483">Intune の展開</span><span class="sxs-lookup"><span data-stu-id="ae78d-483">Intune deployment</span></span>

1. <span data-ttu-id="ae78d-484">[デバイス **構成**  >  **の管理] を開きます**。</span><span class="sxs-lookup"><span data-stu-id="ae78d-484">Open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="ae78d-485">[プロファイル **の**  >  **管理] [プロファイルの**  >  **作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ae78d-485">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="ae78d-486">プロファイルの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae78d-486">Choose a name for the profile.</span></span> <span data-ttu-id="ae78d-487">**Platform=macOS をプロファイル\*\*\*\*の種類=カスタム に変更します**。</span><span class="sxs-lookup"><span data-stu-id="ae78d-487">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="ae78d-488">[構成] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae78d-488">Select Configure.</span></span>

3. <span data-ttu-id="ae78d-489">以前に作成した .plist を次のように保存します `com.microsoft.wdav.xml` 。</span><span class="sxs-lookup"><span data-stu-id="ae78d-489">Save the .plist produced earlier as `com.microsoft.wdav.xml`.</span></span>

4. <span data-ttu-id="ae78d-490">カスタム `com.microsoft.wdav` 構成プロファイル **名として入力します**。</span><span class="sxs-lookup"><span data-stu-id="ae78d-490">Enter `com.microsoft.wdav` as the **custom configuration profile name**.</span></span>

5. <span data-ttu-id="ae78d-491">構成プロファイルを開き、ファイルを `com.microsoft.wdav.xml` アップロードします。</span><span class="sxs-lookup"><span data-stu-id="ae78d-491">Open the configuration profile and upload the `com.microsoft.wdav.xml` file.</span></span> <span data-ttu-id="ae78d-492">(このファイルは手順 3 で作成されました。</span><span class="sxs-lookup"><span data-stu-id="ae78d-492">(This file was created in step 3.)</span></span>

6. <span data-ttu-id="ae78d-493">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae78d-493">Select **OK**.</span></span>

7. <span data-ttu-id="ae78d-494">[割 **り当**  >  **ての管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ae78d-494">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="ae78d-495">[含める **] タブ** で、[すべてのユーザーに割り当てる] & **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ae78d-495">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

>[!CAUTION]
><span data-ttu-id="ae78d-496">正しいカスタム構成プロファイル名を入力する必要があります。それ以外の場合、これらの基本設定は Microsoft Defender for Endpoint によって認識されません。</span><span class="sxs-lookup"><span data-stu-id="ae78d-496">You must enter the correct custom configuration profile name; otherwise, these preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

## <a name="resources"></a><span data-ttu-id="ae78d-497">リソース</span><span class="sxs-lookup"><span data-stu-id="ae78d-497">Resources</span></span>

- [<span data-ttu-id="ae78d-498">プロファイル構成リファレンス (Apple 開発者向けドキュメント)</span><span class="sxs-lookup"><span data-stu-id="ae78d-498">Configuration Profile Reference (Apple developer documentation)</span></span>](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
